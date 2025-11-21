---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, juli 2023
description: Läs om felkorrigeringarna och hur du uppgraderar till juliversionen 2023 av Adobe Experience Manager Guides as a Cloud Service
exl-id: f1765c6a-cb8e-4a06-a6f4-f5c225b6bc88
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# juliversion 2023 av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i Adobe Experience Manager Guides version juli 2023 (kallas senare *AEM Guides as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i juli 2023-utgåvan av AEM Guides as a Cloud Service](whats-new-2023-7-0.md).

## Uppgradera till juliversionen 2023

Uppgradera din nuvarande AEM Guides as a Cloud Service-konfiguration genom att utföra följande steg:

1. Ta en titt på Git-koden för molntjänster och växla till den gren som konfigurerats i molntjänstflödet för den miljö som du vill uppgradera.
2. Uppdatera egenskapen `<dox.version>` i `/dox/dox.installer/pom.xml`-filen för Git-koden för molntjänster till 2023.7.0.314.
3. Genomför ändringarna och kör Cloud Services-pipeline för att uppgradera till juli 2023-utgåvan av AEM Guides as a Cloud Service.

## Steg för att aktivera utlösaren för ett skript via en serverlet

(Endast om du har en version som är tidigare än version från juni 2023 av AEM Guides as a Cloud Service)

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

I föregående svar-JSON innehåller nyckeln `lockNodePath` sökvägen till noden som skapades i databasen som pekar på jobbet som skickades. Den tas automatiskt bort när jobbet är klart, tills dess kan du referera till den här noden för aktuell status för jobbet.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du har en version som är tidigare än version från juni 2023 av AEM Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 dita-filer i systemet uppdaterar du `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och distribuerar sedan om.

   - Använd instruktionerna i avsnittet *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides
as a Cloud Service, för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet queryLimitReads:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-begäran med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart kommer den tidigare GET-förfrågan att besvaras. Om jobbet misslyckas av någon anledning kan fel ses från serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet `queryLimitReads` om du har ändrat det i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du har en version som är tidigare än version från juni 2023 av AEM Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST-begäran till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika banor för mappningarna för att indexera dem. Som standard indexeras alla mappningar \|\| Till exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Exempel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-begäran med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. När jobbet är klart kommer den tidigare GET-förfrågan att besvaras och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds av AEM Guides as a Cloud Service juliversion 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM Guides som Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.07.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| AEM Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.07.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |


## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Textbundna attribut/visningsattribut visas inte i layoutvyn i Web Editor. 12498
- Ladda upp filer i Sygen Plugin för AEM Guides fungerar inte i molntjänster om du har! i filnamnet. (12207)
- DITA-kartpublicering är mycket långsam med redigerbar mall. (12075)
- Konfigurationen för det globala profilanvändargränssnittet matchar inte mappprofilen. (11970)
- Innehållsreferenser bryts när DITA-filer kopieras och klistras in. (11959)
- Det går inte att redigera innehållsfragment i kolumnvyn när AEM Guides är installerat. 7342
- Innehållet förloras när en unwrapped xref finns under en underordnad elementtagg. (12532)

### Publicering

- Arbetsflödet för godkännande fungerar inte när dokumentläget ändras till slutläge från filegenskaperna på den högra panelen. (11026)
