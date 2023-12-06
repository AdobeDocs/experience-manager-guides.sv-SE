---
title: Hantera förinställningar för utdata för global profil och mappprofil
description: Lär dig hur du skapar, redigerar, byter namn på, duplicerar och tar bort förinställningar för utdata i global profil och mappprofil som administrativa användare i AEM.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Hantera förinställningar för utdata för global profil och mappprofil {#id22BLJ0D0V1U}

Förinställningarna för global profil och mappprofil är bara tillgängliga för administratörer på mappnivå.

Som administratör kan du med hjälp av AEM guider skapa och hantera utdataförinställningar för globala profiler och mappprofiler. Sedan kan du enkelt använda de här förinställningarna för att generera utdata för alla kartor som är relaterade till den globala profilen eller mappprofilen.

Så här skapar du en förinställning för globala profiler och mappprofiler:

1. Välj den DITA-karta som du vill skapa en förinställning för.
1. Välj **Redigera ämnen** från **Alternativ** kartfilens meny. Kartfilen öppnas för redigering i Web Editor.
1. I **Utdata** väljer du ikonen + för att skapa en förinställning för DITA-kartan.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Ange följande information i dialogrutan **Lägg till förinställning** dialog:
   - Typ
   - Namn
   - Mål \(för kunskapsbasförinställning\)
1. Välj **Lägg till i mappprofil** om du vill skapa en förinställning för den relaterade mappprofilen och sedan klicka på **Lägg till**. Förinställningen skapas och visas under **Utdata** -fliken för alla relaterade kartor. \( ![](images/global-preset-icon.svg)\) visas en förinställning på mappprofilnivå.
1. Ange konfigurationsinformationen. Mer information om förinställningar för utdata finns i [Förinställningar för utdata](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Dessa förinställningar som läggs till i mappprofilen är inte beroende av kartorna, så de kartspecifika konfigurationerna finns inte för de här förinställningarna.

1. Du kan välja **Generera förinställning** längst upp om du vill generera utdata för de kartor som är kopplade till den skapade förinställningen. Du ser status för genereringsprocessen för utdata. Om du vill visa utdata för du muspekaren över ämnet och klickar på **Visa utdata**.

>[!NOTE]
>
> AEM Guides innehåller också en förinställning för att skapa utdata för dina DITA-kartor för PDF.

**Andra åtgärder på Alternativ-menyn**

Du kan även utföra följande åtgärder på förinställningen på Alternativ-menyn:

- Välj förinställningen som standardförinställning för PDF. Sedan används den valda förinställningen som standardförinställning för att generera utdata från PDF med **Hämta som PDF** för en karta.
- **Redigera**, **Byt namn**, **Duplicera**, eller **Ta bort** en befintlig förinställning från **Alternativ** -menyn.

>[!NOTE]
>
> När en förinställning för utdata i globala profiler och mappprofiler tas bort återspeglas den i alla relaterade kartor och visas inte under **Utdata** -fliken.

**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
