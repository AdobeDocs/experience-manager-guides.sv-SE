---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, mars 2023-versionen
description: Mars-utgåvan av Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Mars 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i Adobe Experience Manager Guides version mars 2023 (kallas senare *AEM Guides as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i mars 2023-utgåvan av AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Uppgradera till mars 2023-versionen

Uppgradera din nuvarande AEM Guides as a Cloud Service-konfiguration genom att utföra följande steg:

1. Ta en titt på Git-koden för molntjänster och växla till den gren som konfigurerats i molntjänstflödet för den miljö som du vill uppgradera.
1. Uppdatera egenskapen `<dox.version>` i `/dox/dox.installer/pom.xml`-filen för Git-koden för molntjänster till 2023.3.242.
1. Genomför ändringarna och kör Cloud Services-pipeline för att uppgradera till mars 2023-utgåvan av AEM Guides as a Cloud Service.

## Steg för att indexera befintligt innehåll (endast om du använder en version som är tidigare än september-versionen av AEM Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använda den nya texten för att söka och ersätta på mappnivå:

* Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-begäran med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c (42_678)

* När jobbet är klart kommer ovanstående GET-förfrågan att besvaras med framgång och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM Guides as a Cloud Service mars 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM Guides som Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| AEM Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* Ladda ned PDF-processen fungerar inte korrekt i Web Editor. (11496)
* JSON-utdata | Mappningsmetadata med egenskapsvärdet `"value in spaces and double quotes"` leder till ett publiceringsfel. (11438)
* Det går inte att infoga multimediefiler för ljud och video i YouTube-format med ikonen **Infoga multimedia** . (11320)
* Valideringsfel uppstår när en karta skapas med mallen som har ett specialiserat rubrikelement. (11212)
* PDF | fotnot i tabellrubrik leder till fet och centrerad text i motsvarande sidfot i PDF-utdata. 10610
>[!NOTE]
>
>Om du vill spegla ändringen i PDF tar du bort PDF-mappen som finns i /content/dam/dita-templates och uppgraderar sedan till den senaste versionen. 10610

### Känt problem med tillfälliga lösningar

Adobe har identifierat följande kända problem i AEM Guides as a Cloud Service mars 2023-utgåvan.

* Användarna kan inte spara eller skapa en version av en duplicerad resurs.

**Tillfällig lösning**: Innan du gör några ändringar i den duplicerade resursen bearbetar du om den från Assets-gränssnittet.
