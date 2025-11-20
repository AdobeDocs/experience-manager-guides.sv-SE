---
title: Versionshistorikrapport för återställda filer
description: Visa rapporter om versionshistorik från återställda filer i AEM Guides. Lär dig hur du kommer åt loggar för återställningsversionen från Assets UI, ämnesförhandsgranskning och AEMs-verktygsval.
feature: Report Generation
role: User
hide: true
exl-id: c787947a-b235-4c12-a9cc-eac5136d31db
source-git-commit: 5081aa032c13ca684c6882149448b05c77028a90
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Versionshistorikrapport för återställda filer {#id205BBC00PRK}

När du arbetar med flera samtidiga utgåvor tillsammans med flera författare är ditt innehåll oundvikligt att ha flera versioner. Det kan finnas gemensam information över flera utgåvor, som olika författare kan använda i sitt projekt. För att hantera sådana arbetsuppgifter kunde författare sluta med flera versioner av filer. Sådana versioner kan helt enkelt vara en nyare version av en fil eller en återgång till en tidigare version. Det är en komplex uppgift att identifiera när en fil återställdes och varför.

AEM Guides låter dig generera en versionshistorikrapport för en enskild fil eller för alla filer i en mapp. Denna versionshistorik ger dig en sammanslagen vy av alla versioner av en fil som återställdes, vem som skapade dessa versioner och anledningen till att de gjordes.

{{$include /help/_includes/overview.md}}

Du kan få tillgång till denna rapport från följande platser:

- **Assets UI:** genom att välja en fil och öppna versionshistoriken **&#x200B;**&#x200B;från vänster sken. Versionshistorikvyn **&#x200B;**&#x200B;innehåller länken **Återställ versionsloggar** längst ner i panelen. När du klickar på denna länk visas den valda filens historik för de återställda versionerna.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Ämnesförhandsvisning**: när du förhandsgranskar ett ämne kan du också öppna panelen **Version History** från vänster sken. Du får en panel liknande Assets UI där du kan klicka på länken **Återställ versionsloggar** för att komma åt den återställda versionshistoriken för det aktiva dokumentet.

- **AEM:s Verktygssektion**: du kan också komma åt denna rapport från AEM:s Verktygssektion. Följande procedur förklarar hur du kan komma åt versionshistoriken för återställning från AEM:s Verktygssektion.


Utför följande steg för att komma åt rapporten om återställ historik:

1. Klicka på länken Adobe Experience Manager högst upp och välj **Verktyg.**

1. Välj **guider** från verktygslistan.

1. Klicka på rutan Version **Revert History** (versionsåterställning).

   En tom sida för Återställ versionshistorik visas där du behöver bläddra till och välja en fil eller mapp för att generera rapporten.

1. Klicka på **Visa loggar** för att generera rapporten för den valda filen eller mappen.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   Rapporten innehåller följande detaljer:

   - **Filnamn**: Ämnets titel. Genom att klicka på ämnets titellänk öppnas ämnesförhandsvisningen.

   - **Tidsstämpel**: Datum och tid då ämnet återgick till en tidigare version.

   - **Användare: Namnet** på användaren som återgick till en tidigare version.

   - **Återställ från**: Det ursprungliga versionsnumret för filen där den återställdes.

   - **Återställ till**: Den version som filen återställdes till.

   - **Kommentar**: Alla kommentarer från användaren som återställde filen.



**Föräldraämne:**&#x200B;[&#x200B; Rapporter](reports-intro.md)
