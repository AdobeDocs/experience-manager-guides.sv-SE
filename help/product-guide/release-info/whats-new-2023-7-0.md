---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, juli 2023
description: Läs om de nya och förbättrade funktionerna i juli 2023-versionen av Adobe Experience Manager Guides as a Cloud Service
exl-id: 4b907729-4fbf-48ed-a2e1-014bd1101c73
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Nyheter i juli 2023-utgåvan av Adobe Experience Manager Guides as a Cloud Service

I den här artikeln beskrivs de nya och förbättrade funktionerna i Adobe Experience Manager Guides version från juli 2023 (kallas senare *AEM Guides as a Cloud Service*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](release-notes-2023-7-0.md).

## Ansluta till en datakälla och infoga data i dina ämnen

Nu kan du snabbt ansluta till dina datakällor med färdiga anslutningar från AEM Guides. Om du ansluter till en datakälla kan du synkronisera informationen med källan, och alla uppdateringar av data återspeglas automatiskt, vilket gör AEM Guides till ett verkligt innehållsnav. Den här funktionen hjälper dig att spara tid och arbete med att manuellt lägga till eller kopiera data.

Nu kan AEM Guides ge administratören konfigurera färdiga anslutningar för JIRA- och SQL-databaser (MySQL, PostgreSQL, SQL Server, SQLite). De kan även lägga till andra kopplingar genom att utöka standardgränssnitten.

När du har lagt till dem kan du visa de konfigurerade anslutningarna som listas under panelen **Datakällor** i webbredigeraren.

![](assets/code-snippet-generator.png){width="300" align="left"}

Du kan skapa en generator för innehållsavdrag som hämtar data från en ansluten datakälla. Sedan kan du infoga data i dina ämnen och redigera dem.

När du har skapat en generator för innehållsfragment kan du återanvända den för att infoga data i alla ämnen. Mer information finns i [Infoga ett innehållsfragment från datakällan](../user-guide/web-editor-content-snippet.md).



## Granskningspanelen för att visa granskningsprojekt och aktiva granskningsåtgärder

Nu gör AEM Guides granskningarna smidigare. Här finns panelen Recensioner i Web Editor. På panelen Granska visas alla granskningsprojekt och de aktiva granskningsåtgärderna i granskningsprojekten som du är en del av.

Som författare kan du använda den här funktionen för att enkelt öppna granskningsuppgifterna, visa kommentarerna och snabbt hantera kommentarerna i en centraliserad vy.
![](assets/active-review-task-comments.png){width="800" align="left"}
Mer information finns i beskrivningen av funktionen **Granska** i avsnittet [ Vänster panel ](../user-guide/web-editor-features.md#id2051EA0M0HS) .


## Förbättringar av kartsamling

Med en kartsamling kan du ordna flera kartor och grupppublicera dem. Många nya förbättringar har gjorts i kartsamlingen:

- Nu kan du även lägga till förinställningar för inbyggda PDF-utdata i en kartsamling och använda dem för att generera utdata från PDF.
- Du kan visa de förinställningar för global profil och mappprofil som har skapats av administratören och använda dem för att generera utdata från PDF.
- Nu kan du inte bara välja en enskild förinställning, utan även aktivera alla förinställningar för mappprofiler för en DITA-karta på en gång.
  ![](assets/edit-map-collection.png){width="800" align="left"}

Mer information finns i [Använd kartsamling för generering av utdata](../user-guide/generate-output-use-map-collection-output-generation.md).

## Möjlighet att få åtkomst till temporära HTML-filer när du genererar PDF-utdata

Nu kan du ladda ned de temporära HTML-filer som skapas när du genererar utdata från PDF. Välj alternativet att hämta de temporära filerna i inställningarna för förinställningar för utdata.  I AEM Guides kan du sedan hämta de temporära filer som skapas när du genererar utdata med den förinställningen.

Den här funktionen ger bättre insikter i genereringsprocessen med tillgång till tillfälliga format och layouter och hjälper dig att korrigera eller ändra dina CSS-format efter dina behov.

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Mer information finns i [Skapa en förinställning för utdata från PDF](../web-editor/native-pdf-web-editor.md#create-output-preset).

## Microservice-baserad publicering för att generera utdata för HTML5 och Custom

Med den nya publiceringsmikrotjänsten kan du köra stora publiceringsarbetsbelastningar samtidigt på AEM Guides as a Cloud Service och utnyttja den branschledande Adobe I/O Runtime serverlösa plattform. Med mikrotjänsten kan du nu också generera utdata för HTML5 och Custom.
Du kan köra flera publiceringsbegäranden och få bättre prestanda för att generera dessa utdataformat.
Mer information finns i [Konfigurera mikrotjänstbaserad publicering för AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).

## Visa versionsinformation om AEM Guides i Om-informationen

Nu kan du tillsammans med AEM **Om**-information även visa versionsinformation för AEM Guides. Du kan visa den aktuella versionsinformationen i alternativet **Om** i **hjälpen** på AEM navigeringssida.

![](assets/about-aem-help.png)(width=&quot;800&quot; align=&quot;left&quot;)
