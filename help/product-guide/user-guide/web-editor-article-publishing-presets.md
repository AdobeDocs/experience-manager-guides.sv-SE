---
title: Skapa förinställningar från Web Editor
description: Skapa förinställningar från webbredigeraren. Lär dig hur du redigerar, byter namn på, duplicerar och tar bort en förinställning AEM stödlinjer.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Skapa förinställningar från Web Editor {#id218CL400JW3}

Följ de här stegen för att skapa förinställningar för DITA-kartan:

1. Navigera i resursgränssnittet till den kartfil som du vill redigera.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och klickar på **Checka ut**.

1. Välj **Redigera ämnen** på kartfilens åtgärdsmeny.

   Kartfilen öppnas för redigering i Web Editor.

   >[!NOTE]
   >
   > Du kan lägga till eller ta bort alla ämnen från kartan med hjälp av den avancerade kartredigeraren. Mer information finns i [Arbeta med den avancerade kartredigeraren](map-editor-advanced-map-editor.md#).

1. I **Utdata** väljer du ikonen + för att skapa en förinställning för DITA-kartan.

   ![](images/output-tab-preset_cs.png){width="350" align="left"}

1. Ange namnet på förinställningen i dialogrutan Lägg till förinställning och klicka sedan på **Lägg till**.

1. Ange följande konfigurationsinformation.

   1. Välj önskade alternativ i dialogrutan **Allmänt** -fliken. Du kan välja att skapa en förinställning med eller utan villkor. Du kan också använda en DITVAL-fil. Med AEM kan du även välja en baslinje för publicering av en specifik version av DITA-kartan.
   1. Ange AEM platsinformation i dialogrutan **AEM** -fliken. **Plats** I visas en lista med de AEM Sites som finns i din AEM. **Kategori**, **Avsnittsmall** och **Artikelmall** är de strukturella komponenter som används för att ordna utdatafilens utseende och känsla. Dessa är fördefinierade i AEM platsmall.

      >[!NOTE]
      >
      > Uppdatera varje listruta för att få ytterligare klassificering i nästa listruta.

   1. Från **Artiklar** väljer du de ämnen som du vill generera utdata för.
1. Välj **Generera förinställning** längst upp för att generera utdata.

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. Du ser status för genereringsprocessen för utdata. The **Ämnen** -kolumnen listar de ämnen som utdata genereras för när **Status** -kolumnen visar publiceringsstatusen för varje ämne.

   Om du vill visa utdata för du muspekaren över avsnittet och klickar på Visa utdata.

   ![](images/add-preset-output-generated_cs.png){width="800" align="left"}


>[!NOTE]
>
> Du kan också redigera, byta namn på, duplicera eller ta bort en befintlig förinställning på Alternativ-menyn.

![](images/edit-preset_cs.png){width="550" align="left"}

**Överordnat ämne:**[ Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md)
