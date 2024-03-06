---
title: AI-baserade smarta förslag för att skapa innehåll
description: Lär dig hur du visar och använder AI-baserade smarta förslag i Web Editor.
source-git-commit: eea4a30b91fd5c28647fd7ea95dd8058ec411adc
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 0%

---



# AI-baserade smarta förslag för att skapa innehåll

Stödlinjerna för Experience Manager innehåller **Smarta förslag** som hjälper er att skapa enhetligt och korrekt innehåll.

När du skapar innehåll kan du **Smarta förslag** kan söka med hjälp av AI och visa befintligt innehåll som semantiskt liknar ditt innehåll. Du kan sedan välja det bästa matchande innehållet som du vill ta med i det aktuella ämnet som referens.

Detta gör att du kan återanvända befintligt innehåll från dokumentationsdatabasen och skapa enhetligt innehåll. Du skapar till exempel ett dokument som innehåller information om **Adobe Firefly**, inklusive ett stycke om **Adobe**. I så fall kan du snabbt visa och lägga till innehållsreferensen från ett annat ämne, som **Adobe Photoshop**, som innehåller samma stycke.





När du öppnar ett ämne i Web Editor visas **Smarta förslag** visas till höger.

>[!NOTE]
>
> Administratören måste konfigurera **Smarta förslag** -funktion. Mer information finns i [Konfigurera AI-baserade smarta förslag för redigering](../cs-install-guide/conf-smart-suggestions.md) i installations- och konfigurationshandboken för Cloud Service.

![Panelen Smarta förslag](images/smart-suggestions-panel.png){width="300" align="left"}

*Visa **Smarta förslag**-panelen.*

Följ de här stegen för att visa smarta förslag på hur du lägger till lämpliga innehållsreferenser till ditt ämne:

1. Välj **Smarta förslag** ![ikon för smarta förslag](images/smart-suggestions-icon.svg) för att öppna panelen.



   >[!NOTE]
   >
   > I [globala profiler eller profiler på mappnivå](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions)måste administratören definiera de filer eller mappar som ska indexeras för smarta förslag, det minsta antal tecken som du måste ange för att kunna visa förslagen och det högsta antalet förslag som du kan visa i listan.

1. Skriv in innehållet i ditt ämne för att visa relaterade förslag. Kontrollera att innehållets teckenlängd överskrider vad administratören har angett i mappprofilen för att innehållsförslagen ska visas.

1. Välj **Förslag för den aktuella taggen** ![ikon för aktuell tagg för smarta förslag](images/smart-suggestions-current-tag-icon.svg) om du vill visa redigeringsförslagen för den aktuella taggen där du placerar muspekaren.  Förslagen för att visa och lägga till innehållsreferenser från de indexerade filerna visas baserat på innehållet i den aktuella taggen.

   Kortkommando: **Windows** (*Ctrl* + *K*),  **macOS** (*Kommando* + *K*)
1. Välj **Förslag för hela dokumentet**  ![ikon för hela dokumentet med smarta förslag](images/smart-suggestions-complete-document-icon.svg) om du vill visa förslag baserat på innehållet i hela dokumentet.  Smarta förslag![ikon för smarta förslag](images/smart-suggestions-complete-document-icon.svg) visas bredvid det innehåll där en lämplig matchning finns.

   Kortkommando: **Windows** ( *Ctrl* + *Skift* +  *K* ),  **macOS** (*Kommando* + *Skift* + *K* )

   >[!NOTE]
   >
   > Du kan bara visa förslagen för den aktuella visningsrutan (det innehåll som visas på skärmen). Om du vill visa förslag på annat innehåll i dokumentet rullar du uppåt eller nedåt för att visa det i visningsrutan och väljer sedan ![ikon för smarta förslag](images/smart-suggestions-complete-document-icon.svg) ikon .

1. Välj **Smarta förslag** ![ikon för smarta förslag](images/smart-suggestions-complete-document-icon.svg) -ikonen bredvid taggarna som du har lagt till i dokumentet för att visa smarta förslag.
1. Du kan visa smarta förslag i **Återanvändning av innehåll** förslagsruta.  Guiderna i Experience Manager ger förslag på exakt matchning av innehåll och innehåll med samma innebörd. Du kan t.ex. söka efter ämnet som innehåller det exakta versionsnumret, som&quot;release version 2023.03.12&quot;. Du kan också söka efter &quot;Adobe har huvudkontor i San Jose i Kalifornien&quot; och hitta liknande material som &quot;San Jose har kvartal av många programvaruföretag som Adobe.&quot;
1. Välj **Innehållsinformation** ![Innehållsinformation](images/smart-suggestions-content-info-icon.svg) för att visa information.
   ![Panelen Innehållsinformation](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Visa detaljerad information om innehållsreferensen.*

   1. Titeln på det ämne som innehåller innehållsreferensen visas som en hyperlänk.
   1. Sökvägen till filen som innehåller innehållsreferensen.
   1. Den typ av referens där innehållet refereras.
   1. Namnen på DITA-filer där ämnet refereras visas som hyperlänkar.
1. Välj **Förhandsgranska föreslaget innehåll** ![ikon för förhandsgranskning av smarta förslag](images/smart-suggestions-preview-icon.svg) för att jämföra det aktuella innehållet med det föreslagna innehållet. Detta hjälper dig att jämföra skillnaderna och avgöra om du vill lägga till innehållsreferensen för det föreslagna innehållet och göra den konsekvent eller behålla det aktuella innehållet.

   ![Förhandsgranska föreslaget innehåll](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Förhandsgranska jämförelsen mellan det aktuella innehållet och det föreslagna innehållet.*

1. Klicka **Acceptera** för att lägga till den föreslagna innehållsreferensen i **Förhandsgranska föreslaget innehåll** -dialogrutan.
1. Du kan också välja **Acceptera** eller **Avböj** i **Återanvändning av innehåll** rutan med förslag för lämpliga rekommendationer.



Denna intelligenta funktion är praktisk och minimerar arbetet med manuell innehållssökning, så att du kan koncentrera dig mer på att skapa nytt innehåll. Det underlättar också bättre teamsamarbete och ger enhetlighet i det innehåll som skapas av olika författare.

