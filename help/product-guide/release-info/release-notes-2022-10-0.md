---
title: Versionsinformation | Adobe Experience Manager Guides as a Cloud Service, oktober 2022-utgåvan
description: Oktober-versionen av Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Oktober-versionen av Adobe Experience Manager Guides as a Cloud Service

## Uppgradera till oktoberversionen

Uppgradera din nuvarande Adobe Experience Manager Guides as a Cloud Service-konfiguration (kallas senare *AEM Guides as a Cloud Service*) genom att utföra följande steg:
1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
1. Uppdatera `<dox.version>`-egenskapen i `/dox/dox.installer/pom.xml`-filen för dina Cloud Services Git-kod till 2022.10.183.
1. Genomför ändringarna och kör Cloud Servicens pipeline för att uppgradera till oktoberversionen av AEM Guides as a Cloud Service.

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds i AEM Guides as a Cloud Service version från oktober 2022.

### FrameMaker och FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Inte kompatibel | 2020 uppdatering 4 och senare |
| | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| AEM Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nya funktioner och förbättringar

AEM Guides as a Cloud Service innehåller förbättringar och nya funktioner i oktober-versionen:


### Snabbgenereringspanelen

Nu har AEM Guides panelen **Snabbgenerering** som hjälper dig att snabbt generera och visa utdata för förinställningar som skapats för din DITA-karta.

![Ikon för snabbgenerering](assets/quick-generate-icon.png)

På panelen **Snabbgenerering** kan du se en lista över alla förinställningar som har skapats för din DITA-karta.

![Snabbgenereringspanelen](assets/quick-generate-panel.png)

Välj en eller flera förinställningar och generera snabbt utdata. Du kan också snabbt visa utdata som genererats för förinställningarna. Ett meddelande om att det lyckades visas när utdata genererades. Ett felmeddelande visas om utdatagenereringen misslyckas. Du kan även visa felloggen för att se information om felet som uppstod under genereringsprocessen.


## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

* PDF | Det går inte att ta bort ämnen som bara innehåller resurser från utdata från PDF. (10554)
* PDF | Tomma nyckelrutor visas i utdata från PDF. (10553)
* PDF | `navtitle` för `topichead` respekteras inte. (10509)
* PDF | Stöd krävs för amd64 JDK-versioner. 10465
* PDF | Det går inte att dölja ämnen som ligger före varandra från innehållsförteckningen. (10355)
* PDF | Om du startar om sidnumret i kapitellayouten startas numreringen slumpmässigt från slutet av föregående kapitel. (10154)
* Chrome webbläsare | Skärmen blir tom när du drar och släpper element från gränssnittet. Om du till exempel drar ett villkor från villkorspanelen. (10524)
* Nodegenskaper tas bort efter att en resurs har kopierats och klistrats in. (10053)
* När du klickade på **Stäng** omdirigerades användare till resurser. Funktionen har korrigerats för att ta användare till AEM hemsida. 9654
