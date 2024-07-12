---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, aprilversion 2023
description: April 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# April 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i Adobe Experience Manager Guides version april 2023 (kallas senare *AEM Guides as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i april 2023-utgåvan av AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Uppgradera till aprilversionen 2023

Uppgradera din nuvarande AEM Guides as a Cloud Service-konfiguration genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>`-egenskapen i `/dox/dox.installer/pom.xml`-filen för dina Cloud Services Git-kod till 2023.4.249.
3. Genomför ändringarna och kör Cloud Servicen för att uppgradera till AEM Guides as a Cloud Service från april 2023.

## Steg för att indexera befintligt innehåll (endast om du använder en version som är tidigare än september-versionen av AEM Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använda den nya texten för att söka och ersätta på mappnivå:

* Kör en POST-förfrågan till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`.
(Valfritt: Du kan skicka specifika sökvägar för mappningarna för att indexera dem. Som standard indexeras alla mappningar || Exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* API:t returnerar ett jobId. Om du vill kontrollera statusen för jobbet kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Exempel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c183 79f11c42_678)

* När jobbet är klart kommer ovanstående GET-förfrågan att svara och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds i AEM Guides as a Cloud Service version från april 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM Guides som Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| AEM Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |



## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* PDF | Publicering av innehåll som har en utdataklass med hakparenteser() resulterar i en publiceringsfrysning. (11596)
* Problem uppstår när du flyttar (drar och släpper) i stället för ett befintligt listobjekt med Spåra ändringar aktiverat. (11570)
* Problem uppstår när du flyttar (drar och släpper) som ett nytt listobjekt med Spåra ändringar aktiverat. (11569)
* Indrag eller indrag i listobjekt fungerar inte som väntat med Spåra ändringar. (11568)
* Om du lägger till innehåll på en linje med Spåra ändringar aktiverat och sedan stänger av Spåra ändringar inaktiveras det inte. (11567)
* Det är svårt att dra och släppa ett listobjekt. Texten flyttas istället för listobjektet. (11566)
* Den slutförda granskningen öppnas inte i skrivskyddat läge. (11387)
* Problem uppstår AEM webbplatssökningen (fungerar inte längre än 2-3 nivånoder). (11352)
* Vid redigering i det element som visas i grönt (Spåra ändringar) visas det nya innehållet som spåra ändringar även om spårändringen är inaktiverad. 7021

### Känt problem med tillfälliga lösningar

Adobe har identifierat följande kända fel i AEM Guides as a Cloud Service April 2023-utgåvan.

* PDF | Gamla metadata fylls inte i förrän förinställningen för utdata öppnas explicit.
