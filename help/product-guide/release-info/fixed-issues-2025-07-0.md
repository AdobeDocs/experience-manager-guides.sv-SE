---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides 2025.07.0
description: Läs mer om felkorrigeringarna i version 2025.07.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: bf8b295444a1e21fc19bfbc04efaa20fe78f71bb
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---

# Problem i version 2025.07.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2025.07.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2025.07.0](whats-new-2025-07-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.07.0](upgrade-instructions-2025-07-0.md).

## Redigering

- När en XML-kommentar läggs till i ett element i vyn Source, försvinner inledande och avslutande blanksteg runt kommentaren när du växlar vy. (GUIDES-29781)
- Multimediaalternativen fungerar inte när de finns inuti ellipsikonen (menyn **Mer**) i verktygsfältet. (GUIDES-29583)
- När du skapar ett nytt ämne via Assets-gränssnittet eller redigeraren öppnas inte ämnet automatiskt i redigeraren om inställningen `xmleditor.uniquefilenames` har värdet true i `XMLEditorConfig`. (GUIDES-28171)
- Blanksteg som läggs till i en MathML-ekvation i Source-vyn behålls inte när du växlar redigeringsvyn. (GUIDES-26111)

## Resurshantering

- När du öppnar ett ämne i redigeringsvyn efter en webbläsaruppdatering behålls inte tidigare använda taggar i panelen Filegenskaper. Om du lägger till nya taggar skrivs de befintliga taggarna över, särskilt när ett stort antal taggar är tillgängliga för markering. (GUIDES-29078)
- När du genererar en metadatarapport för en DITA-karta som innehåller ett stort antal resurser, svarar inte knappen **Hantera** eller får ett fördröjt svar. (GUIDES-28443)

## Granska

- Försök att skapa granskningsåtgärder via AEM-arbetsflödet misslyckas konsekvent eftersom granskningsnoden inte skapas. (GUIDES-28214)

## Publicering

- Kodkvalitetsfel inträffar när komponentpaketet `guides-components.all-1.3.0.zip` för AEM Sites-publicering distribueras via Cloud Manager. (GUIDES-28873)
- Om du publicerar en DITA-karta med attributet `chunk=to-content` skapas dubbletter av JCR-noder i den nya AEM Sites-utdatafilen, vilket leder till en överflödig innehållsstruktur i AEM Sites. (GUIDES-28104)
- Om ett ämne har attributet `chunk =to-content` och utdata är inställt på att använda ämnesrubriker som sidnamn, visar det genererade sidnamnet felaktigt ordet **chunk** i stället för att det ursprungliga ämnesnamnet behålls när du publicerar en DITA-karta med de nya AEM Sites-utdata. (GUIDES-28102)
- Egenskapen `cq:template` som angetts i AEM Guides ämnesmall för ny AEM Sites-publicering visar ett felaktigt värde, vilket påverkar mallstrukturen och återgivningen av innehåll. (GUIDES-27789)


## Plattform

- Prestandaproblem som längre inläsningstider och återkommande tidsgränser observeras när du arbetar med stora samlingar. (GUIDES-29065, GUIDES-28793)
- Sårbarheter som är kopplade till det borttagna Guava-biblioteket som används i AEM Guides-komponenter som överförts till Experience Manager Guides.(GUIDES-27402)

## Kända fel

Adobe har identifierat följande kända fel i version 2025.07.0:

- När du arbetar med markeringsämnen visas en **ämnesreferens**-knapp i redigerarens verktygsfält, men den fungerar inte. (GUIDES-31038)
- När mappar med versaler överförs med Adobe Experience Manager-datorprogrammet behålls inte versalerna och namnen visas med gemener i Editor. (GUIDES-30909)
- I dialogrutan **Koppla** visas **Huvudinnehåll** felaktigt i listrutan i stället för de tillgängliga versionerna av det markerade ämnet. (GUIDES-30820)
- När du öppnar en DITA-karta med det enhetliga skalet aktiverat uppdateras redigeraren regelbundet.(GUIDES-26919)