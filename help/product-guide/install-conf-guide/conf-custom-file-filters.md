---
title: Konfigurera filter för filbläddringsdialogrutan
description: Lär dig hur du konfigurerar filter för filbläddringsdialogrutan
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 0%

---

# Konfigurera filter för filbläddringsdialogrutan

När du arbetar i Web Editor måste du använda dialogrutan för filbläddring för att infoga element som bild, referens eller nyckelreferens. I standarddialogrutan för filbläddring finns inga filfiltreringsalternativ. Du kan lägga till egna filter som gör att du enkelt och snabbt kommer åt de filer som behövs.

Följande flikar innehåller anvisningar om hur du lägger till egna filfiltreringsalternativ i dialogrutan för filbläddring baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. Lägg till definitionen för de filter som du vill lägga till i filen `ui_config.json`.

   Följande kodutdrag visar hur du lägger till två filtreringsalternativ - DITA-filer och Bildfiler.

   ```
   "browseFilters": [
                       {
                       "title": "DITA Files",
                       "property": "jcr:content/metadata/dita_class",
                       "operation": "exists"
                       },
                       {
                       "title": "Image Files",
                       "property": "jcr:content/metadata/dc:format",
                       "value": [
                       "image/jpeg",
                       "image/gif",
                       "image/png"
                       ]
                       }
                       ]
   ```

   I ovanstående kodfragment är det första filtret för DITA-filer. Filterdefinitionen har följande parametrar:

   title
:   Filtrets visningsnamn. Titeln visas som filtreringsalternativ i dialogrutan för filbläddring.

   property
:   Den egenskap som ska matchas i filens metadata. Om du till exempel bara vill tillåta de filer som har `dita_class`-metadata i sin egenskap, tar egenskapsfiltret `jcr:content/metadata/dita_class` som värde.

   operation
:   Ange `exists` om du vill matcha om värdet som anges i egenskapsparametern finns.

   Det andra filtret är för bildfiler. Parametrarna liknar det första filtret förutom parametern `value`. Parametern `value` använder en array med bildtyper som värde. Alla filtyper som anges i parametern value söks efter och visas i dialogrutan för filbläddring. Alla andra filtyper ignoreras.

1. Spara filen *ui\_config.json* och överför den. Läs sedan in webbredigeraren igen.

   När du startar dialogrutan för filbläddring visas de filteralternativ som är konfigurerade i filen ui\_config.json.

   ![](assets/file-browse-custom-filters.png)

>[!TAB Lokal]

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Skapa en kopia av standardkonfigurationsfilen på följande plats:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigera till och öppna filen `ui_config.json` i noden `apps` för redigering.

1. Lägg till definitionen för de filter som du vill lägga till i filen `ui_config.json`.

   Följande kodutdrag visar hur du lägger till två filtreringsalternativ - DITA-filer och Bildfiler.

   ```json
   "browseFilters": [
       {
         "title": "DITA Files",
         "property": "jcr:content/metadata/dita_class",
         "operation": "exists"
       },
       {
         "title": "Image Files",
         "property": "jcr:content/metadata/dc:format",
         "value": [        
           "image/jpeg",
           "image/gif",
           "image/png"
         ]
       }
   ]
   ```

   I ovanstående kodfragment är det första filtret för DITA-filer. Filterdefinitionen har följande parametrar:

   - **titel:**   Filtrets visningsnamn. Titeln visas som filtreringsalternativ i dialogrutan för filbläddring.

   - **egenskap:**   Den egenskap som ska matchas i filens metadata. Om du till exempel bara vill tillåta de filer som har `dita_class`-metadata i sin egenskap, tar egenskapsfiltret `jcr:content/metadata/dita_class` som värde.

   - **operation:**   Ange `exists` om du vill matcha om värdet som anges i egenskapsparametern finns.

   Det andra filtret är för bildfiler. Parametrarna liknar det första filtret förutom parametern `value`. Parametern `value` använder en array med bildtyper som värde. Alla filtyper som anges i parametern value söks efter och visas i dialogrutan för filbläddring. Alla andra filtyper ignoreras.

1. Spara filen *ui\_config.json* och läs in webbredigeraren igen.

   När du startar dialogrutan för filbläddring visas de filteralternativ som är konfigurerade i filen ui\_config.json.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}

>[!ENDTABS]


**Överordnat ämne:**[ Anpassa Web Editor](customize-overview.md)
