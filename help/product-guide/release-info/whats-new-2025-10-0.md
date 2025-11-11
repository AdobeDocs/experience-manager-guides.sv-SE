---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2025.10.0
description: Läs om de nya och förbättrade funktionerna i version 2025.10.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: bf08a48cd00170bdbe8cde312aac9776f871dbf9
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Nyheter i version 2025.10.0 (oktober 2025)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2025.10.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2025.10.0](fixed-issues-2025-10-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.10.0](../release-info/upgrade-instructions-2025-10-0.md).


## Redigeringsinställningarna har nu bytt namn till Workspace-inställningar och du kommer åt dem på hemsidan

Följande förbättringar har införts för att förbättra navigering och användbarhet:

- **Redigeringsinställningarna** i Experience Manager Guides har bytt namn till **Workspace-inställningar**.
- Menyn **Fler åtgärder** (menyn med tre punkter), som tidigare bara fanns i redigeraren och kartkonsolen, finns nu på [startsidan](../user-guide/intro-home-page.md).

  ![](assets/workspace-settings.png)

## Identifiera och åtgärda enkelt dubbla ID:n i ämnen och kartor i redigeringsvyn

Experience Manager Guides innehåller nu knappen **Duplicera ID:n** i redigeraren som hjälper dig att snabbt identifiera och korrigera dubblett-ID:n som finns i ett och samma ämne eller karta. När dubblett-ID:n identifieras visas den här knappen längst ned till vänster i redigeringsgränssnittet i **redigeringsvyn**. När du väljer knappen visas en lista med alla instanser med duplicerade ID:n i en portfölj. Om du väljer en instans markeras motsvarande innehåll i ämnet eller kartan, vilket gör att du kan hitta och korrigera dubblett-ID:n från den högra panelen.

Mer information finns i [Ytterligare funktioner i redigeraren](../user-guide/web-editor-other-features.md).

![](assets/duplicate-element-IDs.png){width="350" align="left"}

## Förbättringar av filtren Databas och Rapporter

Filtret **Låst av** under de avancerade filtren i databasen och filtret **Författare** i DITA-mappningsrapporter läser nu in användarlistor gradvis när du rullar, i stället för alla samtidigt. Den här sidinlästa inläsningen ökar hastigheten och gör det enklare och smidigare att arbeta med stora användardatauppsättningar.

## Få åtkomst till status för granskningsåtgärder direkt från granskningspanelen

Som initierare av en granskningsåtgärd kan du nu kontrollera statusen för din granskningsåtgärd direkt från granskningspanelen. Med de senaste förbättringarna innehåller dialogrutan **Uppdatera aktivitet** på granskningspanelen ett nytt **Kontrollera granskningsstatus** -alternativ. Om du väljer det här alternativet dirigeras du direkt till kontrollpanelen där du kan visa uppgiftsstatus för varje granskare, vilket ger snabbare åtkomst till uppgiftsförloppet utan att du behöver växla mellan olika sammanhang.

Mer information finns i [Begär en ny granskning eller stäng en granskningsaktivitet som författare](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350" align="left"}



## API för att spåra efterbearbetningsstatus för mappar och resurser

Det finns nu ett nytt API för att spåra efterbearbetningsstatus för enskilda resurser och mappar. Detta är särskilt användbart för team som använder automatiserade arbetsflöden, där publicering bara behöver ske efter att innehållet har bearbetats fullständigt. API:t är ett tillförlitligt sätt att bekräfta beredskapen och minskar risken för publiceringsfel som orsakas av ofullständig bearbetning.

I och med introduktionen av detta API kommer inte heller händelserna efter bearbetning av resurser att utlösas automatiskt. I stället kan administratörer nu aktivera den här händelsen via en inställning i `fmdita config manager`.

Mer information finns i:

- [API för att spåra efterbearbetningsstatus för enskilda resurser och mappar](../api-reference/track-post-processing-status.md)
- [Inställningar för händelsehanterare efter bearbetning i fmdita config Manager](../api-reference/post-process-event.md)

