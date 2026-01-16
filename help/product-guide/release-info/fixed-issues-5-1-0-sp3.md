---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 5.1.0 Service Pack 3 har åtgärdats
description: Läs mer om felkorrigeringarna i version 5.1.0 Service Pack 3 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 82eb0e18eb285006c66b1fe2b6ecc3ca86fefe61
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Åtgärdade problem i version 5.1.0 Service Pack 3 (december 2025)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av 5.1.0 Service Pack 3-utgåvan av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 5.1.0 Service Pack 3](upgrade-instructions-5-1-0-sp3.md).


## Redigering

- Anpassad CSS som används på en mappnivåprofil för ämnen eller kartor återställs till standardformatet i förhandsgranskningsläget när webbläsaren uppdateras. (GUIDES-31098)
- Det går inte att lägga till flera **versionsetiketter** i ett ämne från dialogrutan **Spara som ny version** . (GUIDES-32716)


## Resurshantering

- Det går inte att ta bort versionsetiketter från panelen **Versionshistorik** i Assets-gränssnittet. (GUIDES-38276)


## Granska

- När en granskare slutför en granskningsåtgärd eller initieraren uppdaterar granskningsaktiviteten utan att skriva in kommentarer, visar det skickade e-postmeddelandet den senaste föregående kommentaren. (GUIDES-33590)

## Publicering

- När du genererar AEM Sites-utdata med äldre komponentmappning publiceras ämnen som använder attributet `copy-to` med namnet på `copy-from` -avsnittet i stället för det namn som angetts i attributet `copy-to`. (GUIDES-22155)
- När inbyggda PDF-utdata genereras med en dynamisk baslinje visas termen **PDFProject** som PDF-titel i stället för den faktiska karttiteln. (GUIDES-31102)

## Plattform

- Om du använder `scope="external"` för en referens till DAM-innehåll i ett ämne eller en karta ersätts resursens relativa sökväg med ett GUID. (GUIDES-35605)

## Känt fel

Adobe har identifierat följande kända problem i version 5.1.0 Service Pack 3:

- När du markerar en granskningsuppgift som slutförd på sidan med aktivitetsinformation, slutförs och stängs uppgiften, men dess status fortsätter att visas som **Pågår** på kontrollpanelen. (GUIDES-39375)




