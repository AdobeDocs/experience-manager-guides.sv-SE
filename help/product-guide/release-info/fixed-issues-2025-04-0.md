---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides 2025.04.0
description: Läs mer om felkorrigeringarna i version 2025.04.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
source-git-commit: 70078864379eedd82ae21da70614055c60f0b114
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 0%

---

# Åtgärdade problem i version 2025.04.0

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2025.04.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2025.04.0](whats-new-2025-04-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.04.0](upgrade-instructions-2025-04-0.md).

## Redigering

- Rutan för infogning av specialtecken i redigeraren kan inte läsas in för tyska språk. 24537
- Kommentarer och etiketter som läggs till när en ny version av en DITAVAL-fil sparas inte i versionshistoriken med den nya versionen. 24076
- Utgående och inkommande referenser under **File properties** i den högra panelen uppdateras inte korrekt när du växlar mellan mappningsfiler. Detta problem inträffar särskilt när kartfilerna innehåller ett stort antal referenser. 23344)
- Databasfiltret behåller inte ordningen för anpassade filter som definierats i `ui_config.json`. (21193)
- Om du tar bort flera textrader i ett `codeblock`-element skapas ett tomt utrymme som inte kan tas bort från redigeringsvyn. (20672)
- Nya ID:n kan inte genereras för element när sådana element läggs till via fragment eller skapas via mallar, även när alternativet **för automatiskt genererings-ID** är aktiverat i `XMLEditorConfig`. 21734
- Om du skapar en ny DITA-resurs från DITA-mallar kopieras replikeringsegenskaperna från motsvarande DITA-mallar. (25145)
- Det går inte att komma åt filegenskaper från databaspanelen om den överordnade mappens namn innehåller tecknet &quot;&amp;&quot;. 25762
- Om du stänger en ämnesfil kan den sparas som en ny version, även när ämnet är låst. Problemet inträffar specifikt när alternativet **Fråga efter ny version vid stängning** är aktiverat i `XMLEditorConfig`. 23875
- Databaspanelens aktuella maximala bredd döljer ämne- och mappningsrubriker när innehållshierarkin är djupt inkapslad. 27751

## Publicering

- I tidigare utdata från AEM Sites går det inte att tolka avsnittslänkar i kapslade avsnitt i en karta korrekt när du anger det manuellt i Source-läge eller när innehållet importeras från en extern källa. I stället för att navigera till det avsedda avsnittet, dirigeras de om till huvudämnet som innehåller det kapslade ämnet. 26103
- Om attributet `scope=external` saknas i externa länkar i ett DITA-avsnitt misslyckas publiceringen i HTML5 utan att ange de filer där attributet saknas i felloggarna, särskilt när mikrotjänsten är aktiverad. (25969)
- Det går inte att bädda in videolänkar i PDF även när alternativet **Bädda in multimediafiler** är aktiverat i PDF-förinställningen. (9989)
- Det går inte att skicka metadataegenskaperna för att mappa landningssidor som genererats med den nya AEM Sites-publiceringen. 27288

## Förvaltning

- Dokumentstatus från arbetskopian av ett ämne visas mot alla versioner av det ämnet i översättnings- och baslinjegränssnittet. (20674)


## Granska

- Om du uppdaterar informationen för en granskningsåtgärd på kontrollpanelen kan du inte bekräfta om uppdateringen lyckades eller inte. 8051

## Översättning

- Översättningar som skickas via Experience Manager Guides innehåller inte bifogade resurser, vilket gör att knappen **Start** för översättningsjobb inte är tillgänglig för användare.

## Kända fel

Adobe har identifierat följande kända fel i version 2025.04.0:

- Referensantalet i baslinjegränssnittet uppdateras inte när baslinjen redigeras. Det uppdateras bara när ändringarna sparas. (28015)
- När flera flikar är öppna i redigeraren återställs den senaste redigeringen när du utför en **Ångra** -åtgärd i **Source** -vyn av en fil, men även den tidigare öppnade fliken växlas. 27891
- Alternativet **AEM-stavningskontroll** visas i listrutan **Meny**, även när alternativet **Stavningskontroll för webbläsare** har aktiverats i redigeringsinställningarna. 27993
- En extra version skapas och visas på panelen **Versionshistorik** när du redigerar en bild i Assets-gränssnittet och sparar den. 28001
- En tom rad infogas automatiskt när nytt innehåll klistras in på en ny rad i ett `codeblock`-element.27842
- Om du växlar mellan förinställningar som använder samma baslinje inaktiveras knappen **Spara** för den aktuella förinställningen. 28025
- Ett ämne i en DITA-karta kan inte publiceras i AEM Sites-utdata när det används både som `keydef` och `topicref` i dess undermappar. (22269)
- Ett programfel inträffar när flera avsnitt i en karta redigeras och sedan stängs med alternativet **Stäng alla**, med inställningen **Fråga vid spara version vid stängning** aktiverad.27931

Adobe har identifierat följande kända problem med en lösning:

+++I AEM Sites-utdata bryts bilder när Baslinje inte används vid publicering. 28043
***Tillfällig lösning:*** Du kan publicera sådana resurser från **Assets-gränssnittet**, där länken kan användas.
+++