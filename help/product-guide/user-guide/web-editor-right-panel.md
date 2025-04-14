---
title: Högerpanelen i redigeraren
description: Lär känna den högra panelen i redigeraren. Läs mer om redigeringsgränssnittet och funktionerna i Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 6e7d600da4373cb046e6adad3c5afe3164c9d0fa
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 0%

---

# Högerpanelen i Redigeraren

Den högra panelen innehåller information om det markerade dokumentet.

>[!NOTE]
>
> Du kan ändra storlek på den högra panelen. Om du vill ändra storlek på panelen placerar du markören på panelkanten, pekaren ändras till en dubbelriktad pil, markerar och drar för att ändra storlek på panelbredden.

Den högra panelen ger dig tillgång till följande funktioner:

- [Innehållsegenskaper](#content-properties)
- [Filegenskaper](#file-properties)
- [Granska](#review)
- [Spåra ändringar](#track-changes)
- [Schematron](#schematron)

## Innehållsegenskaper

Du kommer åt funktionen **Innehållsegenskaper** genom att välja ikonen **Innehållsegenskaper** i den högra panelen. Panelen **Innehållsegenskaper** innehåller information om typen av markerat element i dokumentet och dess attribut.

**Typ**: Du kan visa och välja taggarna i hela hierarkin för den aktuella taggen i listrutan.

**Attribut**: Listrutan **Attribut** är tillgänglig i layoutvyn, författarvyn och Source-vyn. Du kan enkelt lägga till, redigera eller ta bort attribut.

<details>
    <summary> Steg för att lägga till attribut </summary>


1. Välj **Lägg till**.

   ![attribut i innehållsegenskaper](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. I listrutan **Attribut** väljer du attributet i listrutan och anger ett attributvärde.  Välj sedan **Lägg till**.

   ![attributpanel med flera attribut ](images/attributes-multiple-properties.png){width="300" align="left"}

1. Om du vill redigera attributet för du pekaren över det och väljer **Redigera** ![redigeringsikon](images/edit_pencil_icon.svg) .

1. Om du vill ta bort attributet för du pekaren över det och väljer **Ta bort** ![ta bort-ikon](images/Delete_icon.svg).

</details>


>[!NOTE]
>
> Även om ämnet innehåller refererat innehåll kan du lägga till attribut på det med egenskapspanelen.

Om administratören har skapat en profil för attribut får du dessa attribut tillsammans med deras konfigurerade värden. Med innehållsegenskapspanelen kan du välja dessa attribut och tilldela dem till relevant innehåll i ditt ämne. På så sätt kan du också skapa villkorsstyrt innehåll som sedan kan användas för att skapa villkorsstyrda utdata. Mer information om hur du skapar utdata med hjälp av villkorliga förinställningar finns i [Använda villkorsförinställningar](generate-output-use-condition-presets.md#).



## Filegenskaper

Visa egenskaperna för den markerade filen genom att välja ikonen för filegenskaper i den högra panelen. Funktionen för filegenskaper är tillgänglig i alla fyra lägen eller vyer: Layout, Författare, Source och Förhandsgranska.

File-egenskaperna har följande två avsnitt:

**Allmänt**

I avsnittet Allmänt får du tillgång till följande funktioner:

![file-properties](images/file-properties-general.png){width="300" align="left"}

- **Filnamn**: Visar filnamnet för det markerade ämnet. Filnamnet är hyperlänkat till egenskapssidan för den markerade filen.
- **ID**: Visar ID:t för det markerade ämnet.
- **Taggar**: Detta är metadatataggar för ämnet. De anges från taggfältet på egenskapssidan. Du kan skriva eller välja dem i listrutan.  Taggarna visas under listrutan. Om du vill ta bort en tagg markerar du kryssikonen bredvid taggen.
- **Redigera fler egenskaper**: Du kan redigera fler egenskaper på sidan för filegenskaper.
- **Språk**: Visar språket för ämnet. Den ställs in från språkfältet på egenskapssidan.
- **Skapad**: Visar datum och tid då ämnet skapades.
- **Ändrad**: Visar datum och tid då ämnet ändrades.
- **Låst av**: Visar användaren som låste ämnet.
- **Dokumentläge**: Du kan välja och uppdatera dokumenttillståndet för det öppna ämnet. Mer information finns i [Dokumenttillstånd](web-editor-document-states.md#).

>[!NOTE]
>
> Du kan kopiera attributvärdena för de olika fälten i filegenskaperna till Urklipp.

**Referenser**

I avsnittet Referenser får du tillgång till följande funktioner:

![](images/file-properties-references.png){width="300" align="left"}

- **Används i**: De dokument som används i referenser listar de dokument där den aktuella filen refereras eller används.
- **Utgående länkar:** Utgående länkar listar de dokument som refereras till i det aktuella dokumentet.

Som standard kan du visa filerna efter namn. När du för muspekaren över en fil kan du visa filens namn och sökväg som ett verktygstips.

>[!NOTE]
>
> Som administratör kan du även välja att visa fillistan efter filnamn i Redigeraren. Välj alternativet **Filnamn** för **redigeringsfilerna visar konfigurationsavsnittet** i **Användarinställningar**.

>[!NOTE]
>
> Alla Använd in- och utgående referenser är hyperlänkade till dokumenten. Du kan enkelt öppna och redigera länkade dokument.

Förutom att öppna filer kan du även utföra många åtgärder via menyn **Alternativ** i avsnittet Referenser. Några av de åtgärder du kan utföra är Redigera, Förhandsgranska, Kopiera UUID, Kopiera sökväg, Lägg till i samlingar, Egenskaper.

## Granska

Om du väljer ikonen Granska öppnas panelen Granska där du kan välja en granskningsuppgift för det dokument som är öppet och visa kommentarer.

![](images/review-panel-before-opening.png){width="300" align="left"}

Om du har skapat flera granskningsprojekt kan du välja ett i listrutan och få tillgång till granskningskommentarerna.

Med hjälp av granskningspanelen kan du visa och publicera svar på kommentarer som ges i ämnet. Du kan godkänna eller avvisa kommentarerna en i taget.

>[!NOTE]
>
> Kommentarsrutan och svarsrutan har stöd för flerradiga poster, och användarna kan expandera den efter behov för att kunna lämna omfattande kommentarer samt detaljerade svar på kommentarerna. Du kan använda **Skift** + **Retur** för att gå till nästa rad medan du skriver kommentarer eller svar.

Mer information finns i [Adressgranskningskommentarer](review-address-review-comments.md#).

## Spåra ändringar

Med funktionen Spårade ändringar i den högra panelen kan du visa information om alla uppdateringar som gjorts i ett dokument. Du kan även söka efter specifika uppdateringar av dokumentet.

>[!NOTE]
>
> Funktionen för spårade ändringar visar alla uppdateringar som har spårats med funktionen Aktivera/inaktivera spåra ändringar i [flikfältet](#tab-bar).

## Schematron

&quot;Schematron&quot; avser ett regelbaserat valideringsspråk som används för att definiera tester för en XML-fil. Redigeraren stöder Schematron-filer. Du kan importera schemafilerna och redigera dem i Redigeraren. Med en Schematron-fil kan du definiera vissa regler och sedan validera dem för ett DITA-avsnitt eller en karta.

Läs mer om hur du arbetar med Schematron-filer i Experience Manager Guides i [Stöd för Schematron-filer](./support-schematron-file.md).



**Överordnat ämne:**[ Introduktion till redigeraren](web-editor.md)
