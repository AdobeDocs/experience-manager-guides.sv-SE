---
title: Rapport över versionshistorik för återskapade filer
description: Visa rapporter om versionshistorik för återskapade filer i AEM Guides. Lär dig hur du får åtkomst till loggar för återversioner från Assets-gränssnittet, förhandsgranskning av ämnen och AEM.
feature: Report Generation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Rapport över versionshistorik för återskapade filer {#id205BBC00PRK}

När du arbetar med flera samtidiga utgåvor tillsammans med flera författare måste innehållet ha flera versioner. Det kan finnas viss gemensam information i flera versioner, som olika författare kan använda i sitt projekt. För att hantera sådana arbetsuppgifter kan författarna få flera versioner av filerna. Sådana versioner kan helt enkelt vara en nyare version av en fil eller en återställning till en tidigare version. Det är en komplex uppgift att identifiera när en fil har återställts och varför.

Med AEM Guides kan du generera en versionshistorik för en enskild fil eller för alla filer i en mapp. Den här versionshistoriken ger dig en sammanslagen vy över alla versioner av en fil som har återförts och vem som har skapat dessa versioner, samt orsaken till att de har skapats.

Du kommer åt den här rapporten från följande platser:

- **Assets-gränssnitt**: genom att markera en fil och öppna **Versionshistorik** från den vänstra listen. Vyn **Versionshistorik** innehåller länken **Återställ versionsloggar** längst ned på panelen. När du klickar på den här länken visas den markerade filens historik för de återskapade versionerna.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Förhandsgranskning av ämne**: När du förhandsgranskar ett ämne kan du även visa panelen **Versionshistorik** från den vänstra listen. Du får en panel som liknar användargränssnittet i Assets där du kan klicka på länken **Återställ versionsloggar** för att få åtkomst till det aktiva dokumentets återförda versionshistorik.

- **AEM Verktyg-avsnittet**: du kan även komma åt den här rapporten från AEM Verktyg-avsnittet. I proceduren nedan beskrivs hur du kan få åtkomst till historiken för återställningsversioner i avsnittet AEM verktyg.


Utför följande steg för att komma åt rapporten Återgå historik:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på rutan **Återgå till tidigare version**.

   En tom sida för att återställa versionshistorik visas där du behöver bläddra till och välja en fil eller mapp för att generera rapporten.

1. Klicka på **Visa loggar** för att generera rapporten för den valda filen eller mappen.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   Rapporten innehåller följande information:

   - **Filnamn**: Ämnets namn. Om du klickar på ämneslänken öppnas ämnesförhandsgranskningen.

   - **Tidsstämpel**: Datum och tid då ämnet återgick till en tidigare version.

   - **Användare**: Namnet på den användare som återgick till en tidigare version.

   - **Återgå från**: Det ursprungliga versionsnumret för filen som den återskapades från.

   - **Återgå till**: Versionen som filen återgick till.

   - **Kommentar**: Alla kommentarer från den användare som återställde filen.


**Överordnat ämne:**[ Rapporter](reports-intro.md)
