---
title: Rapport över versionshistorik för återskapade filer
description: Visa rapporter om versionshistorik för återskapade filer AEM guider. Lär dig hur du får åtkomst till loggar för återversioner från resursgränssnittet, förhandsgranskning av ämnen och AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Rapport över versionshistorik för återskapade filer {#id205BBC00PRK}

När du arbetar med flera samtidiga utgåvor tillsammans med flera författare måste innehållet ha flera versioner. Det kan finnas viss gemensam information i flera versioner, som olika författare kan använda i sitt projekt. För att hantera sådana arbetsuppgifter kan författarna få flera versioner av filerna. Sådana versioner kan helt enkelt vara en nyare version av en fil eller en återställning till en tidigare version. Det är en komplex uppgift att identifiera när en fil har återställts och varför.

Med AEM Guides kan du generera en versionshistorik för en enskild fil eller för alla filer i en mapp. Den här versionshistoriken ger dig en sammanslagen vy över alla versioner av en fil som har återförts och vem som har skapat dessa versioner, samt orsaken till att de har skapats.

Du kommer åt den här rapporten från följande platser:

- **Resursgränssnitt**: genom att markera en fil och öppna **Tidigare versioner** från den vänstra listen. The **Tidigare versioner** vyn innehåller **Återställ versionsloggar** längst ned på panelen. När du klickar på den här länken visas den markerade filens historik för de återskapade versionerna.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Förhandsgranskning av ämne**: när du förhandsgranskar ett ämne kan du även visa **Tidigare versioner** från den vänstra listen. Du får en panel som liknar resursgränssnittet där du kan klicka på **Återställ versionsloggar** om du vill komma åt det aktiva dokumentets versionshistorik.

- **AEM**: du kan även komma åt den här rapporten AEM verktygsavsnittet. I proceduren nedan beskrivs hur du får åtkomst till historiken för återställningsversioner i AEM Verktyg.


Utför följande steg för att komma åt rapporten Återgå historik:

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på **Historik för versionsåterställning** platta.

   En tom sida för att återställa versionshistorik visas där du behöver bläddra till och välja en fil eller mapp för att generera rapporten.

1. Klicka **Visa loggar** för att generera rapporten för den valda filen eller mappen.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   Rapporten innehåller följande information:

   - **Filnamn**: Ämnets namn. Om du klickar på ämneslänken öppnas ämnesförhandsgranskningen.

   - **Tidsstämpel**: Datum och tid då ämnet återgick till en tidigare version.

   - **Användare**: Namnet på den användare som återgick till en tidigare version.

   - **Återställ från**: Det ursprungliga versionsnumret för filen som filen återskapades från.

   - **Återställ till**: Versionen som filen återgick till.

   - **Kommentar**: Alla kommentarer från användaren som återskapade filen.


**Överordnat ämne:**[ Rapporter](reports-intro.md)
