---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2025.11.0
description: Läs om de nya och förbättrade funktionerna i version 2025.11.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: a13fdb36efb5cfb548f8e128977469763836537a
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Nyheter i version 2025.11.0 (november 2025)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2025.11.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2025.11.0](fixed-issues-2025-11-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Nu kommer nya databasen på startsidan och en förbättrad sökupplevelse

Databasen, som nu är tillgänglig direkt från hemsidan, är ett centralt utrymme som gör det enklare att identifiera mappar och filer. Den har en dedikerad **mappnavigeringspanel** och en anpassningsbar **tabellvy av databasen**. Den förbättrade söknings- och filterupplevelsen gör det betydligt enklare att hitta och hitta filer. Mer information finns i [Lär dig mer om databasgränssnittet](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png){align="left"}

I redigeraren är söknings- och filterupplevelsen för filer nu konsekvent med hemsidan. En ny [sökpanel](../user-guide/search-panel-explorer.md) som finns längst ned i redigeringsgränssnittet har lagts till för att visa sökresultaten. Databasen har nu bytt namn till **Utforskaren** i Redigeraren så att du kan bläddra bland mappar och filer som tidigare.

![](assets/search-panel-explorer.png){align="left"}


## Förbättrad indexering för smarta förslag i AI Assistant

Du kan nu enkelt spåra status för varje indexeringsförsök för smarta förslag i AI Assistant med nya statusindikatorer: Indexeringen har slutförts, Inte synkroniserad, Pågår och Indexeringen misslyckades. Tidsstämpeln för den senaste indexeringen registreras nu på mappprofilnivå för bättre spårbarhet. Begränsningar för överordnade och underordnade mappar tillämpas dessutom när du anger en mapp- eller filsökväg för indexering.

Mer information finns i [Konfigurera AI Assistant för smart hjälp och redigering](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Prestandaförbättringar

### Automatisk rensning av B-träd för optimala prestanda

För att upprätthålla systemets effektivitet och förhindra resursstockning rensas regelbundet B-träd på systemnivå med en ny bakgrundsprocess. Detta garanterar att resurser som inte längre finns eller som har lagts till tillfälligt inte tar upp onödigt utrymme.

Systemet identifierar på ett intelligent sätt kandidater för rensning och utför automatisk borttagning. Dessutom är den här funktionen konfigurerbar, vilket ger administratörerna kontroll över dess beteende utifrån de operativa behoven.

Mer information finns i [Konfigurera rensning av B-träd](../cs-install-guide/configure-btree-cleanup-cs.md).

### Förbättrad hantering av DITA-kartor med ett stort antal tangenter

Nu kan du arbeta smidigt med DITA-kartor som innehåller ett stort antal nycklar. Den här förbättringen ger snabbare inläsning och förbättrade prestanda, vilket gör det enklare att hantera komplexa kartor utan avbrott.

Efter uppgraderingen kan systemet få en tillfällig ökning av belastningen, vilket kan fördröja efterbearbetningen av nyligen överförda data. Detta beror på att ett automatiskt engångsskript (OTS) körs i bakgrunden. När skriptet är klart återgår systemprestandan till det normala.

### Förbättrad bearbetning av resurser

En automatiserad process introduceras för att hålla resurser i `/content/dam` uppdaterade. Systemet utlöser en ombearbetning av resurser var 15:e minut. Under varje cykel hämtas och bearbetas resurser som nyligen har lagts till eller förblivit obearbetade inom det senaste 15-minutersperioden, vilket förbättrar effektiviteten och enhetligheten i ert innehållslager.

Mer information finns i [Bearbeta resurser](../user-guide/asset-processor.md).




