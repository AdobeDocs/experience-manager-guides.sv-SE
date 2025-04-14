---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 4.6.0 Service Pack 4 har åtgärdats
description: Läs mer om felkorrigeringarna i version 4.6.0 av Service Pack 4 av Adobe Experience Manager Guides
role: Leader
source-git-commit: f9a03ae620a362989a36ebaefb264ea28220a4b3
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# Åtgärdade problem i version 4.6.0 av Service Pack 4 (april 2025)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av 4.6.0 Service Pack 4-versionen av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 4.6.0 Service Pack 4](upgrade-instructions-4-6-0-sp4.md).

## Redigering

- Om du drar och släpper en bild i ett ämne i vyn **Författare** bryts bildreferensen, vilket leder till dataförlust. 25769
- Om du drar och släpper en `topicref` i en karta i vyn **Författare** misslyckas den avsedda åtgärden och `topicref` tas bort bredvid den dragna `topicref`. (19460)
- Om det inte går att stänga JCR-sessionsanslutningar när ämnen uppdateras eller skapas resulterar detta i minnesläckor och driftavbrott. 26282

## Publicering

- Den inbyggda PDF-publiceringen fortsätter oavbrutet om DITA-innehållet har en webblänk utan omfång som `external`. 26434
- När du skapar en ny baslinje med ett stort antal etiketter misslyckas etikettinläsaren och etiketterna kan inte hämtas. (16232)
- Publicering av inbyggda PDF-filer och AEM-webbplatser stoppas och köas om det finns fel i innehållet. 26516

## Kända fel

Adobe har identifierat följande kända problem i den här versionen:

- Inbyggd PDF-publicering i Windows stöter på fel när DITA-innehåll innehåller en extern länk som inte innehåller attributet `scope`.
