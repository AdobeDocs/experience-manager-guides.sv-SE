---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides 4.2.1
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till 4.2.1-utgåvor av Adobe Experience Manager Guides
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 0%

---

# 4.2.1-utgåvan av Adobe Experience Manager Guides (maj 2023)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som har åtgärdats i version 4.2.1 av Adobe Experience Manager Guides (kallas senare *AEM Guides*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i 4.2.1-utgåvan av Adobe Experience Manager Guides](whats-new-4-2-1-release.md).

## Uppgradera till version 4.2.1 av AEM Guides


Du kan enkelt uppgradera din nuvarande version av AEM Guides till version 4.2.1 Innan du uppgraderar till version 4.2.1 av AEM Guides måste du tänka på följande:
Du kan uppgradera din nuvarande version av AEM Guides till version 4.2.1
* Om du använder version 4.1, 4.1.x eller 4.2 kan du uppgradera direkt till version 4.2.1.
* Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.2.1.
* Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
* Om du har en tidigare version än 3.8.5, se avsnittet Uppgradera AEM Guides i den produktspecifika installationsguiden.

>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar AEM Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM Guides 4.2. 1 release.

### Adobe Experience Manager

**Ej UUID**
Version 6.5 Service Pack 15, 14, 13 eller 12

**UID**
Version 6.5 Service Pack 15, 14, 13 eller 12

Mer information finns i avsnittet *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.2.1 (UID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.2.1 (ej UUID) | 2.2-regular-3 | 2.2-regular-3 | 1,6 | 1,6 |
| 4.2.1 (UID) | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |   |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

* Navigeringsrubriken tas bort från innehållet när du växlar från layoutvyn till författaren eller källvyn. (12174)
* Knappen Stäng i Web Editor leder inte till AEM navigeringssida. (11948)
* Ibland inträffar programfel när du klickar på en DITA-karta. (11842)
* Problem uppstår när du flyttar (drar och släpper) i stället för ett befintligt listobjekt med Spåra ändringar aktiverat. (11570)
* Problem uppstår när du flyttar (drar och släpper) som ett nytt listobjekt med Spåra ändringar aktiverat. (11569)
* Indrag eller indrag i listobjekt fungerar inte som väntat med Spåra ändringar. (11568)
* Om du lägger till innehåll på en linje med Spåra ändringar aktiverat och sedan stänger av Spåra ändringar inaktiveras det inte. (11567)
* Det är svårt att dra och släppa ett listobjekt. Texten flyttas istället för listobjektet. (11566)
* Vid redigering i det element som visas i grönt (Spåra ändringar) visas det nya innehållet som spåra ändringar även om spårändringen är inaktiverad. 7021
* Webbläsaren (webbredigeraren) låser sig när innehåll läses in med ett anpassat schema. (11211)
* PDF | När du skapar en förinställning med alternativet Lägg till i mappprofil misslyckas genereringen av PDF med ett Null-pekarundantag. (10950)
* PDF | Bild-taggen lägger till attribut för inline-visning i alla bilder. (10653)
* Det går inte att infoga multimediefiler för ljud och video i YouTube-format med ikonen **Infoga multimedia** . (11320)
* Valideringsfel uppstår när en karta skapas med mallen som har ett specialiserat rubrikelement. (11212)
* Web Editor | Fast mellanslag läggs till i XML-redigeraren när du redigerar ett ämne. 11786

### Förvaltning

* Fliken Rapporter i webbredigerarens användargränssnitt visar inte ämneslistan med gamla DITA-kartor som skapats före uppgraderingen till 4.2. 11708

* Knappfunktionen Överför filer i Assets-gränssnittet bryts i version 4.2. (11633)


### Publicering

* PDF | Publicering av innehåll som har en utdataklass med hakparenteser() resulterar i en publiceringsfrysning. (11936)
* JSON-utdata | Mappningsmetadata med egenskapsvärdet `"value in spaces and double quotes"` leder till ett publiceringsfel. (11933)
* Problem uppstår AEM webbplatssökningen (fungerar inte längre än 2-3 nivånoder). (11352)
* Web Editor | Det går inte att markera utdatasökväg och -mall i AEM förinställning. (11530)
* Vid uppgradering från 4.1.x till 4.2 fungerar inte motorn för Native PDF och genererar NullPointerException även för det operativsystem som stöds.(11526)
* PDF-nedladdningsprocessen fungerar inte korrekt i Web Editor. (11496)
* PDF | Utkastkommentarer är dolda som standard i genererade utdata. (10560)
* PDF | navtitle stöds inte för topichead. (10509)
* PDF | Om du lägger till `xref` i en bild återges inte bilden på det genererade PDF. (11346)
* PDF | fotnot i tabellhuvudet leder till fet och centrerad text i motsvarande sidfot i PDF-utdata. 10610

### Översättning

* Med uppgraderingen till 4.2 visas allt översättningsinnehåll som är osynkroniserat eller som saknar kopia. (11834)

### Granska

* Den slutförda granskningen öppnas inte i skrivskyddat läge. (11387)
