---
title: Anpassa verktygsfältet
description: Lär dig hur du anpassar verktygsfältet
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5778ed2855287d1010728e689abbe6020ad56574
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 0%

---

# Anpassa verktygsfältet {#id172FB00L0V6}

Som standard levereras webbredigeraren med de vanligaste redigeringsfunktionerna som krävs av alla DITA-redigerare. Du kan använda funktioner som att infoga element av typen lista \(numrerad eller punktad\), korsreferens, innehållsreferens, tabell-, stycke- och teckenformatering i redigeraren. Förutom dessa grundläggande element kan du anpassa Web Editor för att infoga element som används i redigeringsmiljön.

>[!NOTE]
>
> När du migrerar från det gamla användargränssnittet till det nya användargränssnittet i AEM Guides (som gäller från version 2502 och version 5.0 av AEM Guides) måste uppdateringarna av `ui_config` konverteras till mer flexibla och modulära användargränssnittskonfigurationer. Det här ramverket gör det enklare att implementera ändringar i editor_toolbar och andra målwidgetar efter behov. Mer information finns i [Översikt över konfigurationen för konvertering av användargränssnitt](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Det finns två sätt att anpassa Web Editors verktygsfält:

- Lägga till en ny funktion i verktygsfältet

- Ta bort alla befintliga funktioner från verktygsfältet


## Lägga till en funktion i verktygsfältet

Om du lägger till en funktion i Web Editor innebär det två primära åtgärder - att lägga till en ikon för funktionen i filen *ui\_config.json* och lägga till bakgrundsfunktionen i JavaScript.

**Lägg till en ikon i verktygsfältet**

Gör så här för att lägga till en funktion i Web Editor-verktygsfältet:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Skapa en kopia av standardkonfigurationsfilen på följande plats:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigera till och öppna filen `ui_config.json` i noden `apps` för redigering.

1. I filen `ui_config.json` lägger du till definitionen för den nya funktionen i verktygsfältsavsnittet. Vanligtvis kan du skapa en ny verktygsfältsknappgrupp och lägga till en eller flera knappar i den. Du kan också lägga till en ny verktygsfältsknapp i en befintlig verktygsfältgrupp. Följande information krävs för att skapa en ny verktygsfältgrupp:

   - **type:**Ange `blockGroup` som `type`-värde. Detta värde anger att du skapar en blockgrupp som skulle innehålla en eller flera verktygsfältsgrupper.

   - **extraclass:** Namnet på klassen eller klasserna avgränsade med blanksteg.

   - **objekt:** Ange definitionen för alla grupper i verktygsfältet. Varje grupp kan innehålla en eller flera verktygsfältsikoner. Om du vill definiera ikoner i en verktygsfältsgrupp måste du definiera attributet `type` igen i `items` och ange dess värde som `buttonGroup`. Ange ett eller flera klassnamn i egenskapen `extraclass`. Ange funktionsnamnet i egenskapen `label`. I följande utdrag från filen `ui_config.json` visas definitionen för huvudverktygsfältets block, följt av definitionen `buttonGroup`:

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     I samlingen `items` måste du ange definitionen för en eller flera verktygsfältsikoner.
Du måste definiera följande egenskaper för att lägga till en verktygsfältsikon:

   - **type:** Ange `button` som `type`-värde. Detta värde anger att du lägger till en verktygsfältsknapp.

   - **ikon:** Ange namnet på den korallikon som du vill använda i verktygsfältet.

   - **variant:** Ange `quiet` som `variant`-värde.

   - **title:** Ange verktygstipset för ikonen.

   - **on-click:** Ange kommandonamnet som definierats för funktionen i JavaScript-filen. Om kommandot kräver indataparametrar anger du kommandonamnet som:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **visa eller dölj:** Om du definierar egenskapen `show` anger du de lägen som ikonen ska visas i. Möjliga värden är - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visa i alla lägen\) eller `false` \(dölj i alla lägen\).

   I stället för `show` kan du också definiera egenskapen `hide`. Möjliga värden är desamma som i egenskapen `show` med den enda skillnaden att ikonen inte visas för det angivna läget.

1. Skapa en *clientlib*-mapp och lägg till din JavaScript i den här mappen.

1. Uppdatera egenskapen categories i mappen *clientlib* genom att tilldela den värdet för *apps.fmdita.xml\_editor.page\_overrides*.

1. Spara filen *ui\_config.json* och läs in webbredigeraren igen.


**JavaScript-kodexempel**

I det här avsnittet finns två exempel på JavaScript-kod som hjälper dig att komma igång med att lägga till anpassade funktioner. I följande exempel visas AEM Guides versionsnummer när en användare klickar på ikonen Visa version i verktygsfältet.

Lägg till följande kod i en JavaScript-fil:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Lägg till funktionen i filen ui\_config.json som:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

I följande exempel visas hur du ändrar ett dokuments tillstånd för en aktiv fil till&quot;Under granskning&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Lägg till funktionen i filen ui\_config.json som:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Ta bort en funktion från verktygsfältet

Ibland kanske du inte vill ge alla funktioner som är tillgängliga i Web Editor, och då kan du ta bort den oönskade funktionen från Web Editor.

Så här tar du bort oönskade funktioner från verktygsfältet:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till standardkonfigurationsfilen på följande plats:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Skapa en kopia av standardkonfigurationsfilen på följande plats:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigera till och öppna filen `ui_config.json` i noden `apps` för redigering.
Filen `ui_config.json` har tre avsnitt:

- **verktygsfält:**   Det här avsnittet innehåller en definition av alla funktioner som är tillgängliga i redigerarens verktygsfält, t.ex. Infoga/ta bort numrerad lista, Stäng, Spara, Kommentarer med mera.

- **genvägar:**   I det här avsnittet finns en definition av kortkommandon för en viss funktion i redigeraren.

- **mallar:**   Det här avsnittet innehåller den fördefinierade strukturen för DITA-element som du kan använda i ditt dokument. Som standard innehåller mallavsnittet malldefinitioner för ett stycke-, enkel tabell-, tabell- och body-element. Du kan skapa en malldefinition för vilket element som helst genom att lägga till en giltig XML-struktur för det önskade elementet. Om du till exempel vill lägga till ett `p`-element med alla nya `li`-element i en lista kan du lägga till följande kod i slutet av mallavsnittet för att uppnå detta:

```HTML
"li": "<li><p></p></li>"
```

1. I verktygsfältsavsnittet tar du bort den funktion som du inte vill visa för användarna.

1. Spara filen *ui\_config.json* och läs in webbredigeraren igen.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
