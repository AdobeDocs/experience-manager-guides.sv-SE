---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2024.4.0
description: Läs mer om felkorrigeringarna i version 2024.04.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---

# Åtgärdade problem i version 2024.04.0

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2024.04.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2024.04.0](whats-new-2024-04-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.04.0](upgrade-instructions-2024-04-0.md).

## Redigering

- Funktionen **Kopiera** kan inte duplicera tomma mappar i Adobe Experience Manager as a Cloud Service. 15353
- Web Editor kan inte överföra PPTX-filer. 14837
- När du söker efter en text i Web Editor återgår markören till den första förekomsten av den sökta texten och trycker på Retur. 14820)
- Om du sparar automatiskt skapas flera problem, markören flyttas och manuella klick krävs i dokumentet. 14253
- Sökresultaten inaktiveras efter att en fil som hittats via global **Sök och ersätt** har öppnats. (12142)
- I källvyn infogas `</conbody>` ibland på felaktiga platser. 11305
- I XML-redigeraren kan verktygstipset inte uppdatera Source-fältet. 15847
- Funktionen **Share UUID Link** fungerar inte för bilderna i Adobe Experience Manager. (15598)
- Överlappande textproblem uppstår i `<reltable>`- och `<fig>`-taggar. (15238)
- Flimmer uppstår på panelen **Attribut**. 15237
- När du tar bort ett tecken eller ord i innehållet hoppar markören mellan blockelementen. (15224)
- Panelen **Attribut** visas inte i Source-vyn i webbredigeraren. 14387
- Oönskade, hårda blanksteg läggs till när du redigerar i slutet av en tagg i Web Editor. 11786
- Innehåll tas bort medan stavfel i DITA-filer korrigeras. (11610)


## Publicering

- AEM för webbplatsutdata misslyckas när alternativet **Ta bort överbliven plats** är aktiverat. 15896
- Redigeringsfunktionen fungerar inte när du lägger till filer i kartsamlingen. 15813
- I JSON-utdata sprids inte metadata från DITA-kartan eller ämnen till JSON-utdatafilerna. 15713
- Det går inte att publicera PDF när namnet på förinställningen ändras. 15662
- Egenskapen **sourcePath** är felaktig för publicerade AEM. (15502)
- Val och anpassning av språkvariabler fungerar inte korrekt i den inbyggda förinställningen för PDF. (15399)
- Generering av PDF kan inte utföras när en mall med en stor formatmall eller layout används. 15344)
- Innehållet återges inte korrekt i publicerade utdata om `<conref>` används med en absolut sökväg.
- AEM Sites URL-förkortning fungerar inte på grund av konflikter mellan `fmdita rewriter` och `ResourceResolver`. 14793
- Attributen **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** och **chunk=&quot;to-content&quot;** visas oavsett i AEM Sites-utdata. (14442)
- Om en mapp som innehåller 2 kB-bilder anges i mappsökvägen i en mappprofil misslyckas ändringarna som används i förinställningen.14852

## Förvaltning

- Ostängda **Resurslösningar** orsakar ökat sessionsantal och PathNotFoundException-fel efter oktober 2023-versionen av Experience Manager Guides as a Cloud Service. 15604
- Funktionsflaggan **fmdita.useapproval** fungerar inte som förväntat. 15310
- Det går inte att skapa en baslinje med Java API i juni 2023-versionen av Experience Manager Guides as a Cloud Service. 14787
- API:t `/bin/fmdita/import` har fastnat i väntande begäran i oändlighet när de överförda resurserna överstiger 500 MB. 14743

## Granska

- Om du tar bort granskningsnoder stör det möjligheten att öppna och visa kommentarer i Adobe Experience Manager Guides. 15366)
- Granskningspanelen läses in långsamt i Web Editor. 14680)

## Översättning

- **Acceptera översättning** kan inte slutföra översättningen av temporära filer. (14665)
