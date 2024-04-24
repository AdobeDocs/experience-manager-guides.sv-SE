---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, version 2024.04.0
description: Läs mer om kompatibilitetsmatrisen och hur du uppgraderar till 2024.04.0-utgåvan av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för 2024.04.0

I den här artikeln beskrivs uppgraderingsinstruktionerna och kompatibilitetsmatrisen för 2024.04.0-utgåvan av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2024.04.0](whats-new-2024-04-0.md).

En lista över problem som har åtgärdats i den här versionen finns på [Åtgärdade problem i version 2024.04.0](fixed-issues-2024-04-0.md).

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds i version 2024.04.0 av Experience Manager Guides as a Cloud Service.

### FrameMaker och FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.04.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| Experience Manager Guides as a Cloud Release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2024.04.0 | 3.5-uuid 1 | 3.5-uuid 1 | 2,3 | 2,3 |
|  |  |  |  |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Uppgradera till version 2024.04.0

Guiderna för Experience Manager uppgraderas automatiskt när den aktuella (senaste) versionen av Experience Manager as a Cloud Service uppgraderas.


Utför följande steg för as a Cloud Service stödlinjer för Experience Manager om du inte har gjort det tidigare för den befintliga versionen:

### Steg för att aktivera utlösaren för ett skript via en serverlet

(Endast om du är på en release före juni 2023-versionen av Experience Manager Guides as a Cloud Service)

När du har slutfört installationen kan du välja att HIT-aktivera utlösaren för att starta översättningsjobbet:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Svar:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

I det tidigare svaret på JSON, nyckeln `lockNodePath` innehåller sökvägen till den nod som skapas i databasen som pekar på det skickade jobbet. Den tas automatiskt bort när jobbet är klart, så du kan referera till den här noden för jobbstatus.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du är på en release före juni 2023-versionen av Experience Manager Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 DITA-filer i systemet uppdaterar du `queryLimitReads` och `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och sedan distribuera om.

   - Använd instruktionerna i *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera `queryLimitReads` och `queryLimitInMemory` alternativ:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan felet visas i serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för `queryLimitReads` om du har ändrat den i steg 1.

### Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du är på en release före juni 2023-versionen av Experience Manager Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar|| Till exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Till exempel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Till exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan felet visas i serverloggarna.

### Steg som ska hantera `'fmdita rewriter'` konflikt

Experience Manager Guides har en [**egen sling-omskrivare**](../cs-install-guide/conf-output-generation.md#custom-rewriter) för hantering av länkar som genereras vid korsmappningar (länkar mellan ämnen i två olika kartor).

Om du har en annan anpassad Sing Rewriter i kodbasen använder du en `'order'` värdet är större än 50, eftersom Experience Manager Guides sling rewriter använder `'order'` 50. Om du vill åsidosätta detta måste du ange ett värde > 50. Mer information finns i [Omskrivningsförlopp för utdata](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Under uppgraderingen har `'order'` värdet ändras från 1 000 till 50, du måste sammanfoga den befintliga anpassade omskrivaren, om det finns någon, med `fmdita-rewriter`.

