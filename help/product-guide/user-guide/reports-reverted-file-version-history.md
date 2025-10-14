---
title: Rapport över versionshistorik för återskapade filer
description: Visa rapporter om versionshistorik för återskapade filer i AEM Guides. Lär dig hur du får åtkomst till loggar för återversioner från Assets användargränssnitt, förhandsgranskning av ämnen och val av AEM-verktyg.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Rapport över versionshistorik för återskapade filer {#id205BBC00PRK}

När du arbetar med flera samtidiga utgåvor tillsammans med flera författare måste innehållet ha flera versioner. Det kan finnas viss gemensam information i flera versioner, som olika författare kan använda i sitt projekt. För att hantera sådana arbetsuppgifter kan författarna få flera versioner av filerna. Sådana versioner kan helt enkelt vara en nyare version av en fil eller en återställning till en tidigare version. Det är en komplex uppgift att identifiera när en fil har återställts och varför.

Med Adobe Experience Manager Guides kan du generera en versionshistorik för en enskild fil eller för alla filer i en mapp. Den här versionshistoriken ger dig en sammanslagen vy över alla versioner av en fil som har återförts och vem som har skapat dessa versioner, samt orsaken till att de har skapats.

Du kommer åt den här rapporten från följande platser:

- **Assets-gränssnitt**: genom att markera en fil och öppna **Versionshistorik** från den vänstra listen. Vyn **Versionshistorik** innehåller länken **Återställ versionsloggar** längst ned på panelen. När du väljer den här länken visas historiken för den valda filen för de återskapade versionerna.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Förhandsgranskning av ämne**: När du förhandsgranskar ett ämne kan du även visa panelen **Versionshistorik** från den vänstra listen. Du får en panel som liknar användargränssnittet i Assets där du kan välja länken **Återställ versionsloggar** för att få åtkomst till det aktiva dokumentets återförda versionshistorik.

- **Adobe Experience Manager Tools section**: du kan även komma åt den här rapporten från Experience Manager Tools-sektionen. I proceduren nedan beskrivs hur du får åtkomst till historiken för återversioner från Experience Manager Tools-avsnittet.


Utför följande steg för att komma åt rapporten Återgå historik:

1. Välj Adobe Experience Manager logotyp längst upp och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Markera rutan **Återgå till tidigare version**.

   En tom sida för att återställa versionshistorik visas där du behöver bläddra till och välja en fil eller mapp för att generera rapporten.

1. Välj **Visa loggar** om du vill generera rapporten för den valda filen eller mappen.

   ![](images/revert-version-history-report.png){align="left"}

   Rapporten innehåller följande information:

   - **Filnamn**: Ämnets namn. Om du väljer avsnittets titellänk öppnas ämnesförhandsvisningen.

   - **Tidsstämpel**: Datum och tid då ämnet återgick till en tidigare version.

   - **Användare**: Namnet på den användare som återgick till en tidigare version.

   - **Återgå från**: Det ursprungliga versionsnumret för filen som den återskapades från.

   - **Återgå till**: Versionen som filen återgick till.

   - **Kommentar**: Alla kommentarer från den användare som återställde filen.


**Överordnat ämne:**&#x200B;[&#x200B; Introduktion till rapporter](reports-intro.md)
