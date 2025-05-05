---
title: Generera kunskapsbasutdata
description: Lär dig hur du publicerar en eller flera artiklar från kartkonsolen. Generera utdata för ett eller flera ämnen i en DITA-karta i AEM Guides.
exl-id: d89ce69d-8d4c-4265-bfca-60763f561afd
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Generera kunskapsbasutdata {#id218CL05J0M1}

Adobe Experience Manager Guides har en artikelbaserad publiceringsfunktion som gör att användare kan publicera en eller flera kunskapsbasartiklar samtidigt.

Den här motorn har också en OOTB-innehållsmall, som bygger på Adobe Experience Manager kärnkomponenter, med vilken man kan skapa ett kunskapsbaserat arkiv med det tekniska materialet. Den här mallen kan anpassas efter kundernas behov.Med den här motorn kan användarna skapa DITA-kartan på ett additivt sätt och publicera ämnen när de är klara.

Om du bara har uppdaterat innehållet för ett fåtal ämnen på din DITA-karta behöver du inte alltid publicera hela kartan. Du kan bara välja och publicera de uppdaterade avsnitten.

För artikelbaserad publicering måste du skapa förinställningen för din Knowledge Base DITA-karta. Kartan måste innehålla de ämnen som du vill publicera. Du kan också använda villkor och ange AEM Sites-information för förinställningen. Sedan kan du generera utdata med funktionen **Generera utdata** .

Utför följande steg för att generera artikelbaserade utdata:

1. [Skapa kunskapsbasförinställningen](./generate-output-knowledge-base.md) för artikelbaserade utdata.
1. Navigera till fliken **Artiklar** och markera de ämnen som du vill generera utdata för.
1. Välj **Generera utdata** längst upp för att generera utdata.

   ![](images/add-preset-articles-tab_cs.png){align="left"}

1. Markera de filer som du vill publicera och bekräfta genom att välja **Publicera** i **Bekräfta filer för publicering** .

   ![Nytt ](images/knowledge-base-confirm-files-for-publishing.png){align="left"}

   Du visar status för genereringsprocessen för utdata. Kolumnen **Ämnen** visar ämnen som utdata genereras för medan kolumnen **Status** visar publiceringsstatusen för varje ämne.


   ![](images/add-preset-output-generated_cs.png){align="left"}

   Om du vill visa utdata stänger du dialogrutan **Utdata genererade** och väljer **Visa utdata** på förinställningssidan.


   >[!NOTE]
   >
   > Du kan också byta namn på, duplicera eller ta bort en befintlig förinställning på Alternativ-menyn.


**Överordnat ämne:**&#x200B;[ Arbeta med redigeraren](web-editor.md)
