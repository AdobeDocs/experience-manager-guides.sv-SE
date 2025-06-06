---
title: Hantera förinställningar för utdata för global profil och mappprofil
description: Lär dig hur du skapar, redigerar, byter namn på, duplicerar och tar bort förinställningar för utdata i global profil och mappprofil som administrativa användare i AEM Guides.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Hantera förinställningar för utdata för global profil och mappprofil {#id22BLJ0D0V1U}

Förinställningarna för global profil och mappprofil är bara tillgängliga för administratörer på mappnivå.

Som administratör kan du med Adobe Experience Manager Guides skapa och hantera utdatapresentationer för globala profiler och mappprofiler. Sedan kan du enkelt använda de här förinställningarna för att generera utdata för alla kartor som är relaterade till den globala profilen eller mappprofilen.

Så här skapar du en förinställning för globala profiler och mappprofiler:

1. Välj den DITA-karta som du vill skapa en förinställning för.
1. Välj alternativet **Redigera ämnen** på menyn **Alternativ** i kartfilen. Kartfilen öppnas för redigering i Redigeraren.
1. Välj ikonen **Öppna i kartkonsol** för att öppna kartfilen i kartkonsolen.
1. Gå till fliken **Utdataförinställningar** i kartkonsolen och välj ikonen + för att skapa en förinställning för DITA-kartan.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Ange följande information i dialogrutan **Lägg till förinställning**:
   - Typ
   - Namn
   - Mål \(för kunskapsbasförinställning\)
1. Markera kryssrutan **Lägg till i mappprofil** om du vill skapa en förinställning för den relaterade mappprofilen och välj sedan **Lägg till**. Förinställningen skapas och visas under fliken **Utdatainställningar** för alla relaterade kartor. \( ![](images/global-preset-icon.svg)\) indikerar ikonen en förinställning på mappprofilnivå.
1. Ange konfigurationsinformationen. Mer information om förinställningar för utdata finns i [Om förinställningarna](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Dessa förinställningar som läggs till i mappprofilen är inte beroende av kartorna, så de kartspecifika konfigurationerna finns inte för de här förinställningarna.

1. Du kan välja ikonen **Generera utdata** i det övre högra hörnet om du vill generera utdata för kartor som hör till den skapade utdataförinställningen. Du kan visa status för utdatagenereringsprocessen. Om du vill visa utdata väljer du **Visa utdata** i dialogrutan **Slutfört**.

>[!NOTE]
>
> Experience Manager Guides har också en färdig PDF-utdatainställning som genererar utdata för dina DITA-kartor.

**Andra åtgärder på Alternativ-menyn**

Du kan även utföra följande åtgärder på förinställningen på Alternativ-menyn:

- **Generera utdata**: Gör att du kan generera utdata för en befintlig förinställning.
- **Visa utdata** och **Visa logg**: Snabblänkar för att visa genererade utdata och loggar.
- **Byt namn på**, **Duplicera** eller **Ta bort** en befintlig förinställning på menyn **Alternativ**.
- **Standardförinställning för PDF**: Gör att du kan välja den befintliga förinställningen för PDF som standardförinställning för PDF. Den valda förinställningen används sedan som standardförinställning för att generera PDF-utdata med alternativet **Hämta som PDF** för en karta.

>[!NOTE]
>
> När en förinställning för utdata i globala profiler och mappprofiler tas bort återspeglas den i alla relaterade kartor och visas inte på fliken **Utdatainställningar** .

**Överordnat ämne:**&#x200B;[ Arbeta med webbredigeraren](web-editor.md)
