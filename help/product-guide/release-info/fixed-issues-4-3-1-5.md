---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides 4.3.1.5
description: Läs mer om felkorrigeringarna i version 4.3.1.5 av Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%

---

# Åtgärdade problem i version 4.3.1.5


Den här artikeln behandlar buggar som har åtgärdats i olika områden i version 4.3.1.5 av Adobe Experience Manager Guides.



Läs mer om [uppgraderingsinstruktioner för version 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Redigering

- Om du lägger till blanksteg mellan infogade element i `<codeblock>` uppstår en radbrytning i de genererade utdata. (15247)
- Det uppstår problem när element läggs till från dialogrutan Infoga element. (15108)

## Publicering

- Felloggar visar felaktig information om publicering av innehåll med externa omfattningar. (15242)
- Interna länkar till DITA-filer som börjar med `HTTP` behandlas som externa länkar och orsakar omfattningsfel. (15155)
- AEM Site regeneration misslyckas för DITA-kartor. 14369)

## Förvaltning

- Egenskapen **fmditaTopicrefs** visar relativa sökvägar i stället för absoluta sökvägar. 15341
