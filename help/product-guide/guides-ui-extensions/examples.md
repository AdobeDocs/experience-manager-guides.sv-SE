---
sidebar_position: 8
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Exempel

I det här paketet har vi även tillhandahållit några exempel på anpassning (finns på `guides_extension/src`). Nedan följer en kort beskrivning av var och en av dem.

1. [Snabbmeny](./../../src/file_options.ts)
I det här exemplet har vi anpassat snabbmenyn i `file_options` för att ta bort alternativen `Delete` och `Edit` och ersätta alternativet `Duplicate` med ett `Download` -alternativ.

2. [Vänster panel](../../src/left_panel_container.ts)
I det här exemplet har vi anpassat `left tab panel` så att en annan `tab` heter TEST EXTENSION och en motsvarande `tab panel` som har etiketten `Test Tab Panel` .

3. [Högerpanel](../../src/right_panel_container.ts)
I det här exemplet har vi anpassat `right tab panel` så att en annan `tab` med namnet&quot;TEST EXTENSION&quot; och en motsvarande `tab panel` med etiketten: `New Tab Panel`

4. [Databaspanel](../../src/repository_panel.ts)

5. [Verktygsfält](../../src/toolbar.ts)
I det här exemplet har knapparna `Insert Element`, `Insert Paragraph`, `Insert Numbered List` och `Insert Bulleted List` ersatts med en enda `More Insert Options` -knapp som innehåller alla dessa.

[Granska appexempel]

1. [Anteckningsverktygslåda](../../src/review_app_examples/annotation_extension.ts)
I det här exemplet har vi lagt till ytterligare en knapp i anteckningsverktygslådan som öppnar det aktuella granskningsämnet i AEM.

2. [Granska kommentar](../../src/review_app_examples/review_comment.ts)
I det här exemplet har vi lagt till ersatt användarnamnet med användarinformation (som består av kommentarens fullständiga namn och titel), lagt till ett unikt kommentar-ID, en mailTo-ikon och lagt till inmatningsfält för omnämnande av kommentarens allvarlighetsgrad och logiska grund.
Vi har också lagt till en `accept with modification`-knapp på kommentarer på XMLEditor-sidan som öppnar en dialogruta.

3. [Kommentarsvar](../../src/review_app_examples/comment_reply.ts)
I det här exemplet har vi lagt till en ersatt användarnamn med användarinformation (som består av kommentarens fullständiga namn och titel) och lagt till en mailTo-ikon i kommentarhuvudet.

4. [Panelen Textbunden granskning](../../src/review_app_examples/inline_review_panel.ts)
I den här filen beräknar och tilldelar vi det unika kommentar-ID som nämns i exemplen `Review Comment` och `Comment Reply` .
   - Metoden `setCommentId` anger det unika kommentar-ID:t för varje kommentar beroende på antalet kommentarer.

   - `setUserInfo` anger värdet för userInfo med det fullständiga namnet och titeln för varje kommentar.

   - `onNewCommentEvent` ser till att metoden `setUserInfo` anropas för varje ny kommentar eller svar.

   - Funktionen `updatedProcessComments` körs för varje ny kommentarhändelse och ser till att `setCommentId` anropas om vi får en ny kommentarhändelse.

5. [Panelen Ämnesgranskningar](../../src/review_app_examples/topic_reviews.ts): Den här filen utökar [panelen Inline Review](../../src/review_app_examples/inline_review_panel.ts) så att tillagda anpassningar även fungerar på sidan Review App (Granskningsapp).

6. [Acceptera med ändringsdialogrutan](../../src/review_app_examples/accept_with_modification_dialog.ts)
Det här är ett exempel på hur du lägger till nya widgetar i programmet. Här har vi skapat en ny dialogruta med två inmatningsfält: `Revised Text` och `Adjudicator Comment Rationale`

![Acceptera med ändringsdialogruta](./imgs/accept_with_modification_dialogue.png)

Här är granskningsfönstret före och efter anpassning:

![Granskningspanel;](./imgs/review_panel.png)
![Acceptera med ändringsdialogruta](./imgs/customised_review_panel.png)
