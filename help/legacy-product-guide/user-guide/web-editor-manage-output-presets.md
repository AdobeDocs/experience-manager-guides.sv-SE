---
title: Hantera förinställningar för utdata för global profil och mappprofil
description: Lär dig hur du skapar, redigerar, byter namn på, duplicerar och tar bort förinställningar för utdata i global profil och mappprofil som administrativa användare i AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Hantera förinställningar för utdata för global profil och mappprofil {#id22BLJ0D0V1U}

Förinställningarna för global profil och mappprofil är bara tillgängliga för administratörer på mappnivå.

Som administratör kan du med AEM Guides skapa och hantera utdatapresentationer för globala profiler och mappprofiler. Sedan kan du enkelt använda de här förinställningarna för att generera utdata för alla kartor som är relaterade till den globala profilen eller mappprofilen.

Så här skapar du en förinställning för globala profiler och mappprofiler:

1. Välj den DITA-karta som du vill skapa en förinställning för.
1. Välj alternativet **Redigera ämnen** på menyn **Alternativ** i kartfilen. Kartfilen öppnas för redigering i Web Editor.
1. Välj ikonen + på fliken **Utdata** om du vill skapa en förinställning för DITA-kartan.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Ange följande information i dialogrutan **Lägg till förinställning**:
   - Typ
   - Namn
   - Mål \(för kunskapsbasförinställning\)
1. Markera kryssrutan **Lägg till i mappprofil** om du vill skapa en förinställning för den relaterade mappprofilen och klicka sedan på **Lägg till**. Förinställningen skapas och visas under fliken **Utdata** för alla relaterade kartor. \( ![](images/global-preset-icon.svg)\) indikerar ikonen en förinställning på mappprofilnivå.
1. Ange konfigurationsinformationen. Mer information om förinställningar för utdata finns i [Om förinställningarna](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Dessa förinställningar som läggs till i mappprofilen är inte beroende av kartorna, så de kartspecifika konfigurationerna finns inte för de här förinställningarna.

1. Du kan välja ikonen **Skapa förinställning** längst upp för att generera utdata för de kartor som hör till den skapade förinställningen. Du ser status för genereringsprocessen för utdata. Håll muspekaren över ämnet och klicka på **Visa utdata** om du vill visa utdata.

>[!NOTE]
>
> AEM Guides har också en färdig förinställning för PDF för att generera utdata för dina DITA-kartor.

**Andra åtgärder på Alternativ-menyn**

Du kan även utföra följande åtgärder på förinställningen på Alternativ-menyn:

- Välj förinställningen som standardförinställning för PDF. Sedan används den valda förinställningen som standardförinställning för att generera utdata från PDF med alternativet **Hämta som PDF** för en karta.
- **Redigera**, **Byt namn på**, **Duplicera** eller **Ta bort** en befintlig förinställning på menyn **Alternativ** .

>[!NOTE]
>
> När en förinställning för utdata i globala profiler och mappprofiler tas bort återspeglas den i alla relaterade kartor och visas inte under fliken **Utdata**.

**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
