---
title: Anpassa verktygsfältet
description: Lär dig hur du anpassar verktygsfältet
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '989'
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

Gör så här för att lägga till en funktion i Web Editor-verktygsfältet:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. I filen `ui_config.json` lägger du till definitionen för den nya funktionen i verktygsfältsavsnittet. Spara filen och överför den.

   Vanligtvis kan du skapa en ny verktygsfältsknappgrupp och lägga till en eller flera knappar i den. Du kan också lägga till en ny verktygsfältsknapp i en befintlig verktygsfältgrupp. Följande information krävs för att skapa en ny verktygsfältgrupp:

   **typ**:   Ange `blockGroup` som `type` -värde. Detta värde anger att du skapar en blockgrupp som skulle innehålla en eller flera verktygsfältsgrupper.

   **extraclass**:   Namnet på klassen eller klasserna avgränsade med blanksteg.

   **objekt**:   Ange definitionen för alla grupper i verktygsfältet. Varje grupp kan innehålla en eller flera verktygsfältsikoner. Om du vill definiera ikoner i en verktygsfältsgrupp måste du definiera attributet `type` igen i `items` och ange dess värde som `buttonGroup`. Ange ett eller flera klassnamn i egenskapen `extraclass`. Ange funktionsnamnet i egenskapen `label`. I följande utdrag från filen `ui_config.json` visas definitionen för huvudverktygsfältets block, följt av definitionen `buttonGroup`:

   ```
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

   **typ**:   Ange `button` som `type` -värde. Detta värde anger att du lägger till en verktygsfältsknapp.

   **ikon**:   Ange namnet på den korallikon som du vill använda i verktygsfältet.

   **variant**:   Ange `quiet` som `variant` -värde.

   **titel**:   Ange verktygstipset för ikonen.

   **on-click**:   Ange kommandonamnet som är definierat för funktionen i JavaScript-filen. Om kommandot kräver indataparametrar anger du kommandonamnet som:

   ```Javascript
   "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
   ```

   **visa eller dölj**:   Om du definierar egenskapen `show` anger du de lägen som ikonen ska visas i. Möjliga värden är - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visa i alla lägen\) eller `false` \(dölj i alla lägen\).

   I stället för `show` kan du också definiera egenskapen `hide`. Möjliga värden är desamma som i egenskapen `show` med den enda skillnaden att ikonen inte visas för det angivna läget.

   I följande exempel visas AEM Guides versionsnummer när användaren klickar på ikonen Visa version i verktygsfältet.

   Lägg till följande kod i en JavaScript-fil:

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Lägg till funktionen i filen *ui\_config.json* som:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Skapa en *clientlib*-mapp och lägg till din JavaScript i den här mappen.

1. Uppdatera egenskapen categories i mappen *clientlib* genom att tilldela den värdet för *apps.fmdita.xml\_editor.page\_overrides*.

1. Spara filen *ui\_config.json* och läs in webbredigeraren igen.


## Ta bort en funktion från verktygsfältet

Ibland kanske du inte vill ge alla funktioner som är tillgängliga i Web Editor, och då kan du ta bort den oönskade funktionen från Web Editor.

Så här tar du bort oönskade funktioner från verktygsfältet:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.

   Filen `ui_config.json` har tre avsnitt:

   1. **verktygsfält**:   Det här avsnittet innehåller en definition av alla funktioner som är tillgängliga i redigerarens verktygsfält, t.ex. Infoga/ta bort numrerad lista, Stäng, Spara, Kommentarer med mera.

   1. **genvägar**:   I det här avsnittet finns en definition av kortkommandon för en viss funktion i redigeraren.

   1. **mallar**:   Det här avsnittet innehåller den fördefinierade strukturen för DITA-element som du kan använda i ditt dokument. Som standard innehåller mallavsnittet malldefinitioner för ett stycke-, enkel tabell-, tabell- och body-element. Du kan skapa en malldefinition för vilket element som helst genom att lägga till en giltig XML-struktur för det önskade elementet. Om du till exempel vill lägga till ett `p`-element med alla nya `li`-element i en lista kan du lägga till följande kod i slutet av mallavsnittet för att uppnå detta:

   ```css
   "li": "<li><p></p></li>"
   ```

1. I verktygsfältsavsnittet tar du bort den funktion som du inte vill visa för användarna.

1. Spara filen *ui\_config.json* och läs in webbredigeraren igen.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
