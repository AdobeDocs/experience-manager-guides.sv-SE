---
title: Skapa markeringsdokument
description: Skapa markeringsdokument från Redigeraren. Lär dig hur du skapar, redigerar och förhandsgranskar ett markeringsämne i AEM Guides.
exl-id: def14e35-27c5-4b90-bc3d-eef7e8f317d2
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 779be011c078fb3c2fae4fc6a92e3e2d734672b0
workflow-type: tm+mt
source-wordcount: '1197'
ht-degree: 0%

---

# Skapa markeringsdokument från Redigeraren {#id223MIE0B079}

Markering är ett lättviktigt markeringsspråk som du kan använda för att lägga till formateringselement i vanliga textdokument. I Adobe Experience Manager Guides finns funktioner för att skapa, redigera och förhandsgranska ett markeringsämne \(.md\) från Redigeraren. Du kan också överföra befintliga Markdown-dokument och redigera dem i Editor.

## Skapa ett markeringsämne

Så här skapar du ett markeringsämne från Editor:

1. Välj ![](images/Add_icon.svg) på panelen Databas och välj sedan **Ämne** i listrutan.
2. Ange följande information i dialogrutan **Nytt ämne**:

   ![](images/create-markdown-dialog.png){width="300" align="left"}

   * **Titel**: Ange en rubrik för ämnet.
   * **Namn**: Filnamnet föreslås automatiskt baserat på ämnet Titel. Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen visas inte namnfältet.
   * **Mall**: Välj **Markdown** i listrutan. Mallen **Ämne** är markerad som standard.
   * **Sökväg**: Bläddra i sökvägen där du vill spara ämnesfilen. Som standard visas sökvägen till den markerade mappen i databasen i fältet Sökväg.

   >[!NOTE]
   >
   > Om du uppgraderar måste du lägga till markeringsmallen i den aktuella mappprofilen som används. Du kan [skapa en ny markeringsmall i redigeraren](./web-editor-features.md#templates) eller använda en befintlig mall för markeringsredigering. Mer information om hur du lägger till redigeringsmallar i Experience Manager Guides finns i [Konfigurera globala profiler och profiler på mappnivå](../cs-install-guide/conf-folder-level.md).
3. Välj **Skapa**.

   Avsnittet Markering skapas vid den markerade banan och är öppet för redigering.

   ![](images/markdown-topic-author.png){width="650" align="left"}


>[!NOTE]
>
> Du kan också skapa ett markeringsämne för en mapp på databaspanelen. Markera den mapp i vilken du vill skapa ett markeringsämne och välj **Nytt**. Välj sedan **Ämne** på Alternativ-menyn. Du kan nu skapa ett markeringsämne genom att ange ämnesinformation i dialogrutan **Skapa ämne**.

## Läs om redigeringsfunktionerna för ett markeringsämne

I det här avsnittet går du igenom de olika funktioner som är tillgängliga i redigeraren för ämnesutveckling för markeringar. Utvecklingsgränssnittet är indelat i följande avsnitt eller områden:

* [Verktygsfält](#toolbar)
* [Innehållsredigeringsområde](#content-editing-area)
* [Source, sida vid sida och förhandsgranskningslägen](#source-side-by-side-and-preview-modes)
* [Höger panel](#right-panel)


<!--
### Tab bar 

The tab bar features the file tabs of the topics or maps that are currently opened in the Editor along with other file-level options. 

Features available in the tab bar are explained as follows:

 ![](images/markdown-header.png){width="550" align="left"}




* **Topic tab**: Displays the currently opened topics in a tab. By default, you can view the file titles in the tab. As you hover over a file, you can view the file title and the file path as a tooltip.

    >![NOTE]
    >
    > As an administrator, you can also choose to view the list of files by filenames in the tabs. View [User preferences](./intro-home-page.md#user-preferences) for details.
* **Save all**: Saves the changes you have made in all opened topics. If you have multiple topics opened in the Editor, selecting **Save all** or pressing `Crtl+S` shortcut keys saves all documents in one click. You do not have to individually save each document.
* **AI Assistant**: [AI-powered Smart Help](./ai-based-smart-help.md) feature that helps you find relevant content from the Adobe Experience Manager Guides Documentation.
* **More actions**: Allows you to navigate to the **Assets UI**. As an administrator, you also get an option to navigate to the **Settings** page. Learn how to work with [settings](./web-editor-features.md#main-toolbar) or editor settings. 
* **Expand view**: Allows you to expand the page view using the **Expand** icon. In this view, the header bar is hidden, maximizing the content space. To return to the standard view, use the **Exit the expanded view** icon.

-->

### Verktygsfält

Verktygsfältet finns precis nedanför flikfältet. De funktioner som är tillgängliga i verktygsfältet förklaras på följande sätt:

![](images/markdown-main-toolbar.png){align="left"}

| Funktioner | Beskrivning |
|----------------|----------------|
| Redigera åtgärder | Ger åtkomst till olika dokumentredigeringsfunktioner, inklusive **Klipp ut**  ![](images/S_Cut_18_N.svg), **Ångra**  ![](images/S_Undo_18_N.svg), **Gör om**  ![](images/S_Redo_18_N.svg), **Kopiera**  ![](images/S_Copy_18_N.svg), **Ta bort**  ![](images/S_Delete_18_N.svg) och **Sök och ersätt**  ![](images/S_FindAndReplace_18_N.svg). Du kommer åt de tillgängliga alternativen från listrutan **Meny**. |
| Textformateringsalternativ | Ger åtkomst till olika textformateringsalternativ, inklusive **Rubriker**  ![](images/S_DisplayHeading_18_N.svg), **Fet**  ![](images/S_TextBold_18_N.svg), **Kursiv**  ![](images/S_TextItalic_18_N.svg), **Genomstruken**  ![](images/S_TextStrikethrough_18_N.svg), **Kod**  ![](images/S_Code_18_N.svg) och **Blockcitat**  ![](images/S_BlockQuoteMultipleLines_18_N.svg). |
| Alternativ för att infoga innehåll | Tillhandahåller alternativ för att infoga en **numrerad lista**  ![](images/S_TextNumbered_18_N.svg), **Numrerad lista**  ![](images/S_TextBulleted_18_N.svg), **Tabell**  ![](images/tableAdd.svg), **Bild** ![](images/S_ImageAdd_18_N.svg), **Korsreferens**  ![](images/S_LinkGlobe_18_N.svg) och **Symbol**  ![](images/S_SpecialCharacter_18_N.svg) i ett dokument.<br><br> **Obs!** Du kan också dra och släppa bilder och andra filer till markeringsredigeraren. Filer läggs till som korsreferenslänkar, medan bilder visas som standardbildelement. |
| Versionshantering | Gör att du kan skapa versioner av markeringsfiler och visa ändringshistorik. Du kan jämföra olika versioner och vid behov återställa dem till tidigare versioner. Alternativet Versionshistorik finns i listrutan **Meny**. |
| Spara som ny version | Sparar ändringarna som gjorts i ämnet och skapar även en ny version av ämnet. Om du arbetar med ett nyligen skapat ämne visas versionsinformationen som ingen. |
| Lås/lås upp | Låser eller låser upp den aktuella filen. Genom att låsa en fil får du exklusiv skrivåtkomst till filen. Detta hindrar andra användare från att redigera filen. Lås upp filen om du vill att andra ska ha redigeringsåtkomst. Som administratör får du även åtkomst till funktionen **Tvinga upplåsning** som gör att du kan låsa upp filen som någon annan har låst. |

>[!NOTE]
>
> Funktionen **Versionshistorik** och funktionerna som nämns under redigeringsåtgärder, textformatering och infogning av innehåll kan nås både från **Source** - och **sida vid sida** -vyer av markeringsämnet.

### Innehållsredigeringsområde

I området för innehållsredigering visas markeringskällan för ditt ämne, där du gör alla innehållsredigeringar. I vyn Sida vid sida delas det här området upp i två avsnitt - Markeringskällvyn till vänster och Förhandsvisning till höger. Du kan ha flera ämnen öppna samtidigt, som visas på respektive flik.

### Source, sida vid sida och förhandsgranskningslägen

Redigeraren stöder tre olika visningslägen för framtagning och formatering av innehåll:

![](images/markdown-footer.png){align="left"}

* Source
* Sida vid sida
* Förhandsgranska

**Source**

Det här är kodvyn för redigeraren. Du kan redigera markeringsämnen på samma sätt som i vanliga redigeringsprogram. I vyn Source kan du spara en revision av dokumentet, infoga rubriker, infoga tabeller, infoga bilder med mera.

Använd den här vyn om du endast vill fokusera på att skriva och redigera råmarkeringen utan att visa återgivna utdata.

**Sida vid sida**

I det här läget delas redigeraren upp i två paneler:

* Panelen Source som visar det markeringsämne som du redigerar.
* Panelen Förhandsgranska som visar återgivna utdata för markeringsämnet i realtid.

![](images/markdown-topic-side-by-side.png){width="550" align="left"}

Använd den här vyn om du vill visa återgivna utdata i realtid när du redigerar markeringsämnen.

**Förhandsgranska**

När du öppnar ett markeringsämne i förhandsgranskningsläget visas hur ett ämne kommer att visas när det visas av en användare i webbläsaren. I den här vyn tas alla redigeringsfunktioner bort från verktygsfältet. Du kan dock fortfarande komma åt funktionerna **Spara som nya versioner**, **Lås/lås upp** i verktygsfältet och funktionen **Filegenskaper** i den högra panelen.

### Höger panel

Den högra panelen ger dig tillgång till egenskapspanelen **File.

File Properties har följande två avsnitt:

**Allmänt**

I avsnittet Allmänt får du tillgång till följande funktioner:

* **Filnamn**: Visar filnamnet för det markerade ämnet.
* **ID**: Visar ID:t för det markerade ämnet.
* **Språk**: Visar språket för ämnet. Den ställs in från språkfältet på egenskapssidan.
* **Skapad**: Visar datum och tid då ämnet skapades.
* **Ändrad**: Visar datum och tid då ämnet ändrades.
* **Låst av**: Visar användaren som checkade ut ämnet.
* **Dokumentläge**: Du kan välja och uppdatera dokumenttillståndet för det öppna ämnet. Mer information finns i [Dokumenttillstånd](./web-editor-document-states.md).
* **Taggar**: Detta är metadatataggar för ämnet. De anges från taggfältet på egenskapssidan. Du kan skriva eller välja dem i listrutan. Taggarna visas under listrutan. Om du vill ta bort en tagg markerar du kryssikonen bredvid taggen.
* **Redigera fler egenskaper**: Du kan redigera fler egenskaper på sidan för filegenskaper.

**Referenser**

I avsnittet Referenser får du tillgång till följande funktioner:

* **Används i**: De dokument som används i referenser listar de dokument där den aktuella filen refereras eller används.
* **Utgående länkar**: Utgående länkar listar de dokument som refereras till i det aktuella dokumentet.

>[!NOTE]
>
> Alla länkreferenser som används in och ut är hyperlänkade till dokumenten. Du kan enkelt öppna och redigera länkade dokument.

## Funktionsbegränsningar

Följande Experience Manager Guides-funktioner gäller för närvarande inte för Markdown-redigering:

1. Granska
2. Sammanfoga
3. AI Assistant
4. Spåra ändringar





**Överordnat ämne:**&#x200B;[ Introduktion till redigeraren](web-editor.md)
