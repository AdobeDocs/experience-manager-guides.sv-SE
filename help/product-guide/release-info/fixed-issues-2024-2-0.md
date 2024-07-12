---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2024.2.0
description: Läs mer om felkorrigeringarna i version 2024.2.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Problem i version 2024.2.0 har korrigerats

Den här artikeln handlar om buggar som har korrigerats i olika delar av version 2024.2.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2024.2.0](whats-new-2024-2-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Redigering

- Stavningskontrollen i Redigeraren tillåter inte val av förslag. 15045
- Den globala navigeringsknappen fungerar inte och instrumentpanelen kan inte läsas in. 14968
- I Web Editor kan funktionen för hämtning av karta inte utlösa ett popup-meddelande när den är klar att hämtas. 14626
- I Web Editor kan funktionen för hämtning av karta inte hämta en karta med baslinjen. (14622)
- Ogiltigt DTD-fel i oktober 2023-versionen av Experience Manager Guides as a Cloud Service. 14482
- Om du drar ett ordlisteämne från databasen till en ordlista skapas `topicref`. (10767)
- Förhandsgranskningsskärmen för fragment fryses. (14840)
- Etiketter från filen `labels.json` visas i slumpmässig ordning i webbredigeraren. (10508)

## Publicering

- Vid publicering i Native PDF fungerar inte anpassade attribut i villkorsförinställningar för publicering i Native PDF. 14943
- Vid publicering i PDF löses inte nyckelreferenser i december 2023-utgåvan av Adobe Experience Manager Guides. 15085
- AEM Sites publicering misslyckas och orsakar definitionsfel för filer med `xref` till DITA-filen som börjar med HTTP. (15154)
- Det går inte att lägga till en anpassad mall från fliken **Utdata** i redigeraren. 14846
- **AEM Site**-förinställningen fungerar inte på grund av en tom mallsökväg. 14804
- AEM Site regeneration misslyckas för DITA-kartor med ämnen som innehåller MathML-ekvationer. (14790)
- Vid ursprunglig PDF-publicering genererar PDF-generering fel vid hämtning av beroenden för `Node.js`-publicering. 14445
- AEM tillåter inte val av en mall utanför hierarkin `/content` i Web Editor. (14260)
- I AEM Sites-utdata förlorades formatet eller radbrytningarna för elementet `<lines>` med underelement. (12542)
- Anpassade metadata är inte tillgängliga i det slutliga resultatet. (12116)
- I Native PDF kan inte DITA-mappningens metadataegenskaper användas för att fylla i metadata för utdata från PDF. (15159)



## Förvaltning

- **Originalfilterfiler** fungerar inte med filnamn i webbredigeraren. 13486
- Om du inaktiverar indexeringen av den överordnade DITA-kartan för att få bättre prestanda kan vissa funktioner påverkas.(12213)


## Granska

- Snabbmenyn för högerklickning fungerar inte för **Acceptera** eller **Ignorera** - spåra ändringar. 14607
- Växla till att stänga DITA-ämnen i Granskningsskärmen fungerar inte i december 2023-utgåvan av Adobe Experience Manager Guides. 14537
- Det går inte att anpassa e-postmallar för granskningsarbetsflöden med övertäckning. 13954

## Känt fel

Adobe har identifierat följande kända fel i version 2024.2.0:

- Version 1.0 visas inte i användargränssnittet för den duplicerade DITA-filen.
- Spridning av metadata för resurser fungerar inte för version 2024.2.0 med mikrotjänst aktiverad för förinställningar.
