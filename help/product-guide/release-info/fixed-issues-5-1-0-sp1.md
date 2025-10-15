---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 5.1.0 Service Pack 1 har korrigerats
description: Läs mer om felkorrigeringarna i version 5.1.0 Service Pack 1 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 575488e1b378c17419add75876a8e7f7423d5116
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Åtgärdade problem i version 5.1.0 Service Pack 1 (oktober 2025)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av 5.1.0 Service Pack 1-utgåvan av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 5.1.0 Service Pack 1](upgrade-instructions-5-1-0-sp1.md).


## Plattform

- När du migrerar från icke-UUID till UUID och uppgraderar till den senaste versionen (5.0+) och flyttar refererade bilder mellan mappar och sedan återställer DITA-filerna (där dessa bilder refererades) till tidigare versioner, resulterar det i brutna bildreferenser. (GUIDES-34315)

## Publicering

- När du publicerar en DITA-karta med baslinje på AEM Sites (med äldre komponentmappning) publiceras även mappningselementen med attributet `processing-role = resource-only`. (GUIDES-34298)
