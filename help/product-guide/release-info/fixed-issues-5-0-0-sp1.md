---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 5.0.0 Service Pack 1 har åtgärdats
description: Läs mer om felkorrigeringarna i version 5.0.0 Service Pack 1 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 083a8e16b9d3cd6c3894d7eaa2fee489b1dc0bb8
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Åtgärdade problem i version 5.0.0 Service Pack 1 (juni 2025)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av 5.0.0 Service Pack 1-utgåvan av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 5.0.0 Service Pack 1](upgrade-instructions-5-0-0-sp1.md).

## Redigering

- När innehåll klistras in i en `codeblock` eller när mellanslag läggs till i `codeblock` och vyn växlas, försvinner mellanrummet. (GUIDES-29347)
- När en XML-kommentar läggs till i ett element i vyn **Source** försvinner inledande och avslutande blanksteg runt kommentaren när du byter vy. (GUIDES-28188)

## Resurshantering

- När du öppnar ett ämne i vyn **Författare** efter en webbläsaruppdatering behålls inte tidigare använda taggar i panelen **Filegenskaper** och om du lägger till nya taggar skrivs befintliga över, särskilt när ett stort antal taggar är tillgängliga för markering. (GUIDES-29078)
- När du genererar en metadatarapport för en DITA-karta som innehåller ett stort antal resurser, svarar inte knappen **Hantera** eller uppvisar fördröjt svar. (GUIDES-29778)

## Översättning

- När du skickar resurser för översättning från Experience Manager Guides läggs resurserna inte till i översättningsjobbet, vilket förhindrar att knappen **Start** visas och hindrar dig från att starta översättningsjobbet. (GUIDES-28237)

## Publicering

- När du ändrar inställningarna för en förinställning i mappprofilen och väljer **Använd förinställda ändringar** sprids inte ändringarna till förinställningarna som finns i DITA-kartan. (GUIDES-26694)

## Granska

- Försök att skapa granskningsåtgärder via AEM-arbetsflödet misslyckas konsekvent eftersom granskningsnoden inte skapas. (GUIDES-28214)
