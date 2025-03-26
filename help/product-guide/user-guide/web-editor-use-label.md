---
title: Använd etiketter
description: Upptäck användningen av etiketter för olika versioner av en fil i Adobe Experience Manager Guides. Lär dig hur du lägger till eller tar bort en etikett i en version av ett ämne.
exl-id: d116906d-b469-4a97-b0af-4fadbe15222b
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Använd etiketter {#id164JBG0M0T1}

I Adobe Experience Manager Guides kan du lägga till etiketter i olika versioner av en fil. Du kan använda dessa etiketter för att ange vilken version du vill ta med i en baslinje för publicering. Mer information om hur du använder etiketter för att skapa en baslinje finns i [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#).

Om du till exempel vill använda *version 1.0* av ett ämne i *release 1.0* och *version 1.1* av samma ämne i *release 2.0* kan du lägga till etiketten *release 1.0* i *version 1.0* och *release 2.0{1* -etikett på *version 1.1* .

När du har lagt till etiketterna kan du skapa en baslinje och ange vilken version av ämnet som ska inkluderas för publicering med den baslinjen. Om du vill visa vilken version som ska inkluderas eller exkluderas i en baslinje kan du använda alternativet Versionshistorik.

## Lägga till en etikett från Redigeraren

Utför följande steg för att lägga till en etikett i ämnet från Redigeraren:

1. Navigera till ett ämne på panelen Databas och öppna det i Redigeraren.
1. Välj **Versionsetikett** i listrutan **Meny**.

   ![](images/version-label-option.png){width="400" align="left"}

   Dialogrutan **Hantering av versionsetikett** visas.

1. I dialogrutan **Hantering av versionsetiketter** väljer du en version där du vill lägga till en etikett.
1. Välj en etikett för den valda versionen och välj **Lägg till etikett**.

   ![](images/version-label-management-dialog-new.png){width="650" align="left"}

   >[!NOTE]
   >
   > Du kan inte lägga till samma etikett till olika versioner av ett ämne. Du kan dock lägga till flera etiketter till samma version av ett ämne.
1. Bekräfta att etiketterna ska användas i bekräftelserutan.

   Etiketterna visas i versionshistoriken för det valda ämnet.

   ![](images/label-comparison-version-history.png){width="650" align="left"}

   >[!NOTE]
   >
   > Med hjälp av en baslinje kan du lägga till en etikett till flera ämnen. Mer information om hur du lägger till etiketter med baslinje finns i [Lägg till etiketter i en baslinje](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

Om du vill ta bort en versionsetikett från ett ämne använder du ikonen **Ta bort** för varje etikett som läggs till i dialogrutan Hantering av versionsetikett.

![](images/remove-version-label.png){align="left"}


## Arbeta med etiketter från användargränssnittet i Assets

Du kan också lägga till etiketter i ett ämne och ta bort dem efter behov från Assets-gränssnittet.

Följ de här stegen för att lägga till en etikett från användargränssnittet i Assets till ditt ämne:

1. I Assets-gränssnittet markerar du ett ämne och öppnar det.
1. Välj ikonen för vänster rälselektor och välj **Versionshistorik**.
1. I listrutan Versionshistorik väljer du en version där du vill lägga till en etikett.
1. Ange en etikett för den valda versionen och tryck på Retur. Exempel: *2.6 Release*.

   >[!NOTE]
   >
   > Du kan inte lägga till samma etikett till olika versioner av ett ämne. Du kan dock lägga till flera etiketter till samma version av ett ämne.

   Etiketterna visas i versionshistoriken för det valda ämnet. På följande skärmbild visas etiketterna *x.x Release* och *User Guide* som lagts till i den markerade versionen av ämnet.

   ![](images/labels.png){width="300" align="left"}

>[!NOTE]
>
> Med hjälp av en baslinje kan du lägga till en etikett till flera ämnen. Mer information om hur du lägger till etiketter med baslinje finns i [Lägg till etiketter i en baslinje](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

Om du vill ta bort en versionsetikett från ett ämne använder du knappen **Ta bort** för varje etikett på panelen Versionshistorik.

![](images/delete-labels.png){width="300" align="left"}


**Överordnat ämne:**[ Introduktion till redigeraren](web-editor.md)
