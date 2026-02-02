---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 5.0.0 Service Pack 3 har åtgärdats
description: Läs mer om felkorrigeringarna i version 5.0.0 Service Pack 3 av Adobe Experience Manager Guides
role: Leader
source-git-commit: e72bf237352f6007242901c0e409037129459101
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Åtgärdade problem i version 5.0.0 Service Pack 3 (februari 2026)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 5.0.0 av Service Pack 3 av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 5.0.0 Service Pack 3](upgrade-instructions-5-0-0-sp3.md).

## Översättning

- När en bild som initialt hanteras som en språkspecifik resurs med en viss version (till exempel under `/en/`) flyttas ut till en global mapp med en uppdaterad version och baslinjeexport utförs, fortsätter den nya baslinjen att referera till inaktuella språkspecifika versioner av den bilden, vilket leder till en misslyckad baslinjeexport. (GUIDES-39394)
