---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, version 2026.01.0
description: Läs om kompatibilitetsmatrisen och hur du uppgraderar till version 2026.01.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: e6dab21263731b42567729649a11e9d0a74f1dfd
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för version 2026.01.0

I den här artikeln beskrivs uppgraderingsinstruktionerna och kompatibilitetsmatrisen för version 2026.01.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2026.01.0](whats-new-2026-01-0.md).

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2026.01.0](fixed-issues-2026-01-0.md).

## Kompatibilitetsmatris

I det här avsnittet beskrivs kompatibilitetsmatrisen för de program som stöds i version 2026.01.0 av Experience Manager Guides as a Cloud Service.

### FrameMaker och FrameMaker Publishing Server

| Experience Manager Guides som Cloud-release | FMPS | FrameMaker | Syrgasförfattare |
| --- | --- | --- | --- |
| 2026.01.0 | Inte kompatibel | 2022 eller senare | 26,1 |


### Syrgasanslutning

| Experience Manager Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2026.01.0 | 3.8 -uuuid 1 | 3.8 -uuuid 1 | 2,3 | 2,3 |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |


### Ny mallversion för AEM Site

| Komponentversion | Webbplatsversion |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Förutsättningar

Enligt DITA:s standardbeteende får attributet scope=`external` inte tillämpas på interna länkar, eftersom det bara är avsett för referenser till externa resurser. Om du använder det här attributet på interna länkar och flyttar sådana resurser kan arbetsflödena störas. Använd standardscopet=`local` eller nyckelbaserade referenser i stället för innehåll som hanteras i Experience Manager Guides.

## Uppgradera till version 2026.01.0

Experience Manager Guides uppgraderas automatiskt när du uppgraderar till den senaste utgåvan av Experience Manager as a Cloud Service.

>[!NOTE]
>
> Den här versionen innehåller uppdateringar av mappprofilinställningarna (ui_config.json). Om du använder anpassade inställningar bör du göra en säkerhetskopia av dessa innan du uppgraderar. Efter uppdateringen granskar och justerar du inställningarna så att de överensstämmer med ändringarna i den senaste versionen.

Utför följande steg för Experience Manager Guides as a Cloud Service om du inte har gjort det tidigare för din befintliga version:

### Steg för att aktivera utlösaren för ett skript via en serverlet

(Endast om du har en release före juni 2023-versionen av Experience Manager Guides as a Cloud Service)

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

I föregående svar-JSON innehåller nyckeln `lockNodePath` sökvägen till noden som skapades i databasen som pekar på jobbet som skickades. Den tas automatiskt bort när jobbet är klart, så du kan referera till den här noden för jobbstatus.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du har en release före juni 2023-versionen av Experience Manager Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 DITA-filer i systemet uppdaterar du `queryLimitReads` och `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och distribuerar sedan om.

   - Använd instruktionerna i avsnittet *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet `queryLimitReads` och `queryLimitInMemory`:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-begäran med jobb-ID till samma slutpunkt - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GET-förfrågan med framgång. Om jobbet misslyckas av någon anledning kan felet visas i serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet `queryLimitReads` om du har ändrat det i steg 1.

### Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du har en release före juni 2023-versionen av Experience Manager Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar|| Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Exempel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-begäran med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GET-förfrågan med framgång och anger om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggar.

### Steg som ska hantera `'fmdita rewriter'`-konflikten

Experience Manager Guides har en [**anpassad omskrivarmodul**](../cs-install-guide/conf-output-generation.md#custom-rewriter) för hantering av länkar som genereras vid korsmappningar (länkar mellan ämnen på två olika kartor).

Om du har en annan anpassad återskrivningsskrivare i kodbasen använder du ett `'order'`-värde som är större än 50, eftersom Experience Manager Guides återskrivningsprogram använder `'order'` 50. Om du vill åsidosätta detta måste du ange ett värde > 50. Mer information finns i [Skriva om utdata](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Under den här uppgraderingen måste du, eftersom värdet `'order'` ändras från 1 000 till 50, sammanfoga den befintliga anpassade omskrivaren, om sådan finns, med `fmdita-rewriter`.

### Steg för B-trädmigrering för innehållsfragment

Om referenser inte visas för innehållsfragment kan du välja att HIT-aktivera utlösaren för att starta migreringsjobbet:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration
```


Svar:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

I det tidigare svaret, JSON, innehåller nyckeln `lockNodePath` sökvägen till noden som skapades i databasen, vilket pekar på jobbet som skickades. Den tas automatiskt bort när jobbet är klart. Du kan referera till den här noden för jobbstatus.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
>Du bör kontrollera om noden fortfarande finns och jobbens status.

GET:

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```

### Steg för att använda sökfilter på DITAVAL-filer för alla förinställningar för utdata

Uppdatera ui_config.json för att se till att filterfunktionen fungerar korrekt. Ändra egenskaperna som listas under **browseFilters** > **Icke-DITA-filer** > **Ditaval-filer** enligt nedan:

```
{
  "title": "Ditaval Files",
  "property": "LOWER_NAME",
  "operation": "like",
  "value": ".ditaval"
}
```
