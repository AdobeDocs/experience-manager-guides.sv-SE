---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, 2024.06.0
description: Läs om de nya och förbättrade funktionerna i version 2024.06.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: c885b8ba-5230-4d51-8f38-311b3a33fe0a
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 0%

---

# Nyheter i version 2024.06.0

I den här artikeln beskrivs de nya och förbättrade funktionerna i version 2024.06.0 av Adobe Experience Manager Guides.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2024.06.0](fixed-issues-2024-06-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.06.0](upgrade-instructions-2024-06-0.md).


## Publish ett ämne eller dess element till ett Experience Fragment

En Experience Fragment är en modulär innehållsenhet inom Adobe Experience Manager som integrerar innehåll och layout. Experience Fragments är avgörande för att skapa enhetliga och engagerande upplevelser, som kan återanvändas i flera kanaler.


Nu kan du publicera ett ämne eller dess element i ett Experience Fragment i Experience Manager Guides. Du kan skapa en JSON-baserad mappning mellan ett ämne och dess element i ett Experience Fragment. Du kan till exempel skapa upplevelsefragment för sidhuvuden och sidfötter med varumärkeselement, reklambanners, kundutlåtanden och eventkampanjer.




Mer information finns i [Publish Experience Fragments](../user-guide/publish-experience-fragment.md).


## Förbättringar i Content Fragment-publiceringen

Experience Manager Guides har även några praktiska förbättringar i Content Fragments:

- Du kan enkelt filtrera innehåll med villkor när du publicerar till ett innehållsfragment med hjälp av en DITAVAL-fil eller villkorsattribut.

- Du kan också publicera och visa innehållsfragment för ett ämne i avsnittet **Utdata** i **Filegenskaper**.

Fliken ![Alternativ för filegenskaper](./assets/file-properties-outputs-tab.png){width="300" align="left"}

Mer information finns i [Publish Content Fragments](../user-guide/publish-content-fragment.md).


## Möjlighet att skicka metadata från ämnesfilegenskaper till utdata från Native PDF

Nu kan du i Experience Manager Guides lägga till metadata från ett ämnes filegenskaper i sidlayouten när du genererar utdata från PDF. Använd den här funktionen för att lägga till ämnesspecifika metadata som rubrik, taggar och beskrivning i sidlayouterna. Du kan också anpassa det publicerade PDF baserat på ämnets metadata, till exempel lägga till en vattenstämpel till ämnets bakgrund baserat på ämnets dokumenttillstånd.

![lägg till inbyggda metadata-pdf](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Lägg till metadata i fälten i sidlayouterna.*

Lär dig [lägga till fält och metadata](../native-pdf/design-page-layout.md#add-fields-metadata) i en sidlayout.

## Markera delar av innehåll mellan element för åtgärder

Experience Manager Guides gör det enklare att markera innehåll i olika element i Web Editor. Du kan enkelt markera innehåll i olika element och utföra åtgärder som att göra det fet, kursiv och understruken. Med den här funktionen kan du använda eller ta bort formateringen för delvis markerat innehåll. Du kan också snabbt ta bort innehåll som du har markerat över flera element. När innehållet har tagits bort sammanfogas vid behov det återstående innehållet automatiskt under ett enda giltigt element.

Du kan också markera delar av innehåll i flera element och sedan omge innehållet under ett giltigt DITA-element.
![Dialogrutan för surroundelement](./assets/surround-element.png) {width="300" align="left"}

*Omge det markerade innehållet med ett giltigt element.*

På det hela taget ger dessa förbättringar en bättre upplevelse och hjälper dig att arbeta effektivare när du redigerar dokument.

Mer information finns i [Delvis urval av innehåll över element](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Stöd för Markdown-dokument i Native PDF

Experience Manager Guides har också stöd för Markdown-dokument i Native PDF. Den här funktionen är användbar och hjälper dig att generera PDF för Markdown-filerna på DITA-kartan. Marknadsföringsstöd i Native PDF kan hjälpa er att enkelt skapa, hantera och dela dokument.

Mer information finns i [Stöd för markeringsdokument](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Förbättrade prestanda och skalbarhet för stora översättningsprojekt

Översättningsfunktionen är snabbare och mer skalbar än någonsin. Den har en ny arkitektur som ger bättre prestanda. Tiden det tog att skapa projektet är nu snabbare än tidigare och konflikterna under processen är nästan obefintliga. Detta förbättrade resultat hjälper dig med snabbare översättningar och säkerställer smidig drift även för stora översättningsprojekt.

Den här förbättringen är mycket fördelaktig eftersom den förbättrar produktiviteten och den övergripande upplevelsen.

Läs mer om hur du [översätter dokument från webbredigeraren](../user-guide/translate-documents-web-editor.md).
