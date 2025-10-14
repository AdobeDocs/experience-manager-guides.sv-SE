---
title: AI-baserade smarta förslag för att skapa innehåll
description: Lär dig hur du visar och använder AI-baserade smarta förslag i Web Editor.
hide: true
exl-id: 30c85d46-61ba-486c-979c-1a2ed95f5a32
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# AI-baserade smarta förslag för att skapa innehåll

Experience Manager Guides tillhandahåller smarta förslag som hjälper dig att skapa enhetligt och korrekt innehåll.

När du skapar innehåll kan funktionen **Föreslå återanvändbart innehåll** i AI-assistentverktyget söka med hjälp av AI och visa det befintliga innehåll som semantiskt liknar ditt innehåll. Du kan sedan välja det bästa matchande innehållet som du vill ta med i det aktuella ämnet som referens.

Detta gör att du kan återanvända befintligt innehåll från dokumentationsdatabasen och skapa enhetligt innehåll. Du skapar till exempel ett dokument som innehåller information om **Adobe Firefly**, inklusive ett stycke om **Adobe**. I så fall kan du snabbt visa och lägga till innehållsreferensen från ett annat ämne, som **Adobe Photoshop**, som innehåller samma stycke.
>[!NOTE]
>
> I de [globala profilerna eller mappnivåprofilerna](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions) måste administratören definiera filerna eller mapparna som ska indexeras för smarta förslag, det minsta antal tecken som du måste ange för att kunna visa förslagen och det högsta antalet förslag som du kan visa i listan.

Följ de här stegen för att visa smarta förslag på hur du lägger till lämpliga innehållsreferenser till ditt ämne:


1. Markera innehållet i avsnittet för att visa relaterade förslag. Kontrollera att innehållets teckenlängd överskrider vad administratören har angett i mappprofilen för att innehållsförslagen ska visas.
1. Välj **Föreslå återanvändningsbart innehåll** ![ai Föreslå återanvändningsbart innehåll &#x200B;](./images/ai-suggest-reusable-content-icon.svg) på AI-assistentpanelen.

1. Markera en tagg om du vill visa redigeringsförslagen för den aktuella taggen.  Förslagen för att visa och lägga till innehållsreferenser från de indexerade filerna visas baserat på innehållet i den aktuella taggen. Du kan också markera flera taggar.


1. Markera alla taggar om du vill visa förslag baserat på innehållet i hela dokumentet.  Ikonen **Föreslå återanvändbart innehåll** ![ai föreslår att återanvändbart innehåll &#x200B;](./images/ai-suggest-reusable-content-icon.svg) visas bredvid innehållet där en lämplig matchning finns.



   >[!NOTE]
   >
   > Du kan bara visa förslagen för den aktuella visningsrutan (det innehåll som visas på skärmen). Om du vill visa förslag på annat innehåll i dokumentet rullar du uppåt eller nedåt för att visa det i visningsrutan och väljer sedan **Föreslå återanvändbart innehåll** ![ai Föreslå återanvändbar innehållsikon &#x200B;](./images/ai-suggest-reusable-content-icon.svg) .


1. Du kan visa smarta förslag på panelen med förslag.  Experience Manager Guides ger förslag på innehåll som i sitt sammanhang liknar eller har samma innebörd. Du kan t.ex. söka efter ämnet som innehåller det exakta versionsnumret, som&quot;release version 2023.03.12&quot;. Du kan också söka efter&quot;Adobe har huvudkontor i San Jose i Kalifornien&quot; och hitta liknande material som&quot;San Jose har huvudkontor för många programvaruföretag som Adobe&quot;.
1. Välj **Innehållsinformation** ![Innehållsinformation](images/smart-suggestions-content-info-icon.svg) om du vill visa informationen.

   ![Panelen Innehållsinformation](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Visa detaljerad information om innehållsreferensen.*

   1. Titeln på det ämne som innehåller innehållsreferensen visas som en hyperlänk.
   1. Sökvägen till filen som innehåller innehållsreferensen.
   1. Den typ av referens där innehållet refereras.
   1. Namnen på DITA-filer där ämnet refereras visas som hyperlänkar.
1. Välj **Förhandsgranska** ![förhandsgranskningsikonen](./images/expand-icon.svg) om du vill jämföra det aktuella innehållet med det föreslagna innehållet. Detta hjälper dig att jämföra skillnaderna och avgöra om du vill lägga till innehållsreferensen för det föreslagna innehållet och göra den konsekvent eller behålla det aktuella innehållet.

   ![Föreslå förhandsgranskning av återanvändbart innehåll](images/ai-assistant-suggest-reusable-content.png)

   *Förhandsgranska jämförelsen mellan det aktuella innehållet och det föreslagna innehållet.*

1. Klicka på **Acceptera** för att lägga till den föreslagna innehållsreferensen i förhandsgranskningen av **Föreslå återanvändningsbart innehåll**.
1. Du kan också välja **Acceptera** eller **Avvisa** på panelen Förslag för lämpliga rekommendationer.


Denna intelligenta funktion är praktisk och minimerar arbetet med manuell innehållssökning, så att du kan koncentrera dig mer på att skapa nytt innehåll. Det underlättar också bättre teamsamarbete och ger enhetlighet i det innehåll som skapas av olika författare.

>[!NOTE]
>
>Smarta förslag bevarar inte dina data efter den aktuella sessionen. För svar förlitar sig smarta förslag enbart på det index som skapas för innehållet i din interna databas. Externa AI-verktyg används inte, vilket säkerställer att data ligger kvar i systemet.
