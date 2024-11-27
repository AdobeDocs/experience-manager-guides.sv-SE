---
title: Skapa förinställningar från Web Editor
description: Skapa förinställningar från webbredigeraren. Lär dig hur du redigerar, byter namn på, duplicerar och tar bort en förinställning för utdata i AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Skapa förinställningar från Web Editor {#id218CL400JW3}

Följ de här stegen för att skapa förinställningar för DITA-kartan:

1. Navigera i Assets-gränssnittet till den kartfil som du vill redigera.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och klickar på **Checka ut**.

1. Välj alternativet **Redigera ämnen** på Åtgärdsmenyn i kartfilen.

   Kartfilen öppnas för redigering i Web Editor.

   >[!NOTE]
   >
   > Du kan lägga till eller ta bort alla ämnen från kartan med hjälp av den avancerade kartredigeraren. Mer information finns i [Arbeta med den avancerade kartredigeraren](map-editor-advanced-map-editor.md#).

1. Välj ikonen + på fliken **Utdata** om du vill skapa en förinställning för DITA-kartan.

   ![](images/output-tab-preset_cs.png){width="350" align="left"}

1. Ange namnet på förinställningen i dialogrutan Lägg till förinställning och klicka sedan på **Lägg till**.

1. Ange följande konfigurationsinformation.

   1. Välj önskade alternativ på fliken **Allmänt**. Du kan välja att skapa en förinställning med eller utan villkor. Du kan också använda en DITVAL-fil. I AEM Guides kan du också välja en baslinje för publicering av en specifik version av din DITA-karta.
   1. Ange AEM webbplatsinformation på fliken **AEM**. **Plats** visar en lista över de AEM Sites som finns i din AEM. **Kategori**, **Avsnittsmall** och **Artikelmall** är de strukturella komponenter som används för att ordna utdatafilens utseende och känsla. Dessa är fördefinierade i AEM platsmall.

      >[!NOTE]
      >
      > Uppdatera varje listruta för att få ytterligare klassificering i nästa listruta.

   1. På fliken **Artiklar** väljer du de ämnen som du vill generera utdata för.
1. Välj ikonen **Generera förinställning** längst upp för att generera utdata.

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. Du ser status för genereringsprocessen för utdata. Kolumnen **Ämnen** visar ämnen som utdata genereras för medan kolumnen **Status** visar publiceringsstatusen för varje ämne.

   Om du vill visa utdata för du muspekaren över avsnittet och klickar på Visa utdata.

   ![](images/add-preset-output-generated_cs.png){width="800" align="left"}


>[!NOTE]
>
> Du kan också redigera, byta namn på, duplicera eller ta bort en befintlig förinställning på Alternativ-menyn.

![](images/edit-preset_cs.png){width="550" align="left"}

**Överordnat ämne:**[ Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md)
