---
title: Skapa förinställningar från Web Editor
description: Skapa förinställningar från webbredigeraren. Lär dig hur du redigerar, byter namn på, duplicerar och tar bort en förinställning för utdata i AEM Guides.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: 5011481c25b4888a3e72b0e2238b10d8e2fbc191
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Skapa förinställningar för kunskapsbasen i Redigeraren {#id218CL400JW3}

Följ de här stegen för att skapa förinställningar för DITA-kartan:

1. Navigera i Assets-gränssnittet till den kartfil som du vill redigera.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och väljer **Utcheckning**.

1. Välj alternativet **Redigera ämnen** på Åtgärdsmenyn i kartfilen.

   Kartfilen öppnas för redigering i Redigeraren.

   >[!NOTE]
   >
   > Du kan lägga till eller ta bort alla ämnen från kartan med hjälp av den avancerade kartredigeraren. Mer information finns i [Arbeta med den avancerade kartredigeraren](map-editor-advanced-map-editor.md#).

1. Välj ikonen **Öppna i kartkonsol** . Kartan öppnas i kartkonsolen.

1. Navigera till fliken **Utdataförinställningar** och välj ikonen + för att skapa en förinställning för DITA-kartan.

1. Välj **kunskapsbas** i listrutan **Typ**, ange ett namn och välj **Adobe Experience Manager** i dialogrutan **Ny förinställning**.
1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning för den aktuella mappprofilen. ![mappprofilsikonen](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   Förinställningen för kunskapsbasen skapas.


   ![Nytt ](images/knowledge-base-preset-dialog-box.png){width="800" align="left"}

När du har skapat förinställningen kan du generera utdata för specifika kunskapsbasartiklar. Om du vill göra det går du till fliken **Artiklar** och markerar de ämnen som du vill generera utdata för.
1. Välj **Generera utdata** längst upp för att generera utdata.

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. Markera de filer som du vill publicera och bekräfta genom att välja **Publicera** i **Bekräfta filer för publicering** .

   ![Nytt ](images/knowledge-base-confirm-files-for-publishing.png){width="800" align="left"}

Du visar status för genereringsprocessen för utdata. Kolumnen **Ämnen** visar ämnen som utdata genereras för medan kolumnen **Status** visar publiceringsstatusen för varje ämne.


![](images/add-preset-output-generated_cs.png){width="800" align="left"}

Om du vill visa utdata stänger du dialogrutan Genererade utdata och väljer **Visa utdata** på förinställningssidan.


>[!NOTE]
>
> Du kan också byta namn på, duplicera eller ta bort en befintlig förinställning på Alternativ-menyn.



**Överordnat ämne:**[ Artikelbaserad publicering från redigeraren](web-editor-article-publishing.md)
