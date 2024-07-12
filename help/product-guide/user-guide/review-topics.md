---
title: Granska ämnen
description: Lär dig hur du granskar ämnen och använder funktionerna som granskare, dokumentvy, ämnesvy, sammanhangsberoende verktygsfält, förhandsgranskningsläge, lägger till bilagor till kommentarer och villkorspanelen i AEM Guides.
exl-id: fc87fc37-f1cd-4a19-96c2-3a08a8222002
feature: Reviewing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 0%

---

# Granska ämnen {#id2056B0W0FBI}

Om du är granskare får du ett e-postmeddelande med en länk till granskningsavsnitten. När du klickar på länken kommer du till granskningssidan där du kan lägga till din feedback om de delade ämnena.

Utför följande steg för att granska ett ämne:

1. Klicka på den direkta länken i e-postmeddelandet med granskningsbegäran.

   Ämneslänken eller mappningslänken öppnas i en webbläsare.

   >[!NOTE]
   >
   > Du kan även komma åt ämnesgranskningslänken från meddelandeområdet i Inkorgen i AEM användargränssnitt.

1. Beroende på hur ämnesgranskningen initieras kan du se någon av följande två skärmar:

   >[!NOTE]
   >
   > Gränssnittet kan vara annorlunda om du har skapat granskningen i:
   >
   > - AEM Guides as a Cloud Service november 2022 eller tidigare
   > - AEM Guides version 4.1 eller tidigare



   Följande skärm visas när en DITA-karta används för att initiera granskningsarbetsflödet:

   ![](images/multiple-topics-review.png){width="800" align="left"}

   Följande alternativ är tillgängliga på den här skärmen:

   - **A**: Namnet på granskningsaktiviteten.
   - **B**: Klicka på ämnesvyikonen för att visa eller dölja ämnespanelen.

   - **C**: Du kan söka efter det önskade ämnet genom att ange en del av texten i titeln eller filsökvägen i sökfältet.

     Välj ![](images/view-options.svg) nära sökfältet om du vill visa alla ämnen eller ämnen med kommentarer. Som standard kan du visa alla ämnen som ingår i granskningsaktiviteten.


   - **D**: Siffrorna som markeras med ***F*** kan filtreras genom att välja önskat filteralternativ härifrån. Du kan filtrera kommentarer efter typ, status, granskare eller version. Om du till exempel vill se hur många genomstrukna kommentarer som har gjorts i vart och ett av de undergranskade avsnitten klickar du på filterikonen och väljer sedan **Granskningstyp** \> **Borttagning** .

     >[!NOTE]
     >
     > När du använder filtren visas bara de kommentarer som matchar de valda filtren i kommentarspanelen. Antalet filtrerade kommentarer visas till vänster i ämnespanelen.

   - **E**: Ett ämne som tilldelats den aktuella granskaren för granskning visas i svart och kan klickas. När granskaren klickar på en ämneslänk visas det avsnittet högst upp på skärmen.
   - **F**: Ett ämne som inte är tillgängligt för granskning är nedtonat. Avsnittet visas i skrivskyddat läge och du kan inte lägga till granskningskommentarer om det.

   - **G**: Antal kommentarer som tagits emot i ett ämne. Numret ändras beroende på vilket filter du använder.

   Alla ämnen på kartan visas som ett sammansatt dokument. De ämnen som granskaren får granska visas normalt. De ämnen som granskningen inte får granska visas inte.

   ![](images/review-read-only.png){width="800" align="left"}

   På skärmbilden ovan delas ämnet Allmän beskrivning för granskning av den aktuella granskaren, som visas normalt. Nästa avsnitt, Historik över flyginnehåll, delas dock inte för granskning och visas i skrivskyddat läge. Det ämne som för närvarande är i fokus markeras också i innehållsförteckningen.

   Följande skärm visas när ett eller flera ämnen markeras och delas för granskning:

   ![](images/review-composite-view.png){width="800" align="left"}

   >[!NOTE]
   >
   > Om det finns flera ämnen visas de som ett sammansatt dokument i dokumentvyn. Skärmbilden ovan visar två olika ämnen som visas ett efter ett i en enda vy.

1. Öppna panelen Kommentarer genom att klicka på ikonen **Kommentarer** längst upp till höger i verktygsfältet.

   Skriv granskningskommentarerna genom att välja en lämplig kommentarstyp i verktygsfältet och tryck på Retur för att skicka kommentaren.

   >[!NOTE]
   >
   > Kommentarspanelen visar endast kommentarerna som har getts i det aktuella avsnittet. När du flyttar fokus till ett annat ämne visas kommentarerna som ges i det andra avsnittet.

1. Klicka på knappen **Stäng** när du är klar med granskningen av ämnet. När du klickar på knappen **Stäng** omdirigeras du till sidan som du kom åt granskningsavsnittet från.

## Ytterligare funktioner som finns på granskningsskärmen

**Dokumentvy och ämnesvy** - Om flera ämnen delas för granskning visas som standard en sammansatt dokumentvy med ämnen för granskarna. Vid en DITA-kartgranskning visas alla ämnen på kartan i form av ett enda dokument, som liknar en bokvy. Om du vill kan du även klicka på ett visst ämne, så visas bara det ämnet på granskningsskärmen.

När du visar ett enskilt ämne får du ytterligare ett alternativ för att växla tillbaka till dokumentvyn. På skärmbilden nedan öppnas ett visst ämne från en kartfil för granskning. Det markerade alternativet - **Visa dokumentvy** - gör att användaren kan växla tillbaka till dokumentvyn för mappningsfilen.

![](images/switch-document-view.png){width="800" align="left"}

**Arbeta med olika typer av kommentarverktyg** - Du kan lägga till textbundna kommentarer genom att markera text, stryka över text, infoga text eller lägga till en anteckning. De olika kommentarsverktygen som finns i verktygsfältet Kommentarer beskrivs nedan:

![](images/comments-toolbar.png){width="350" align="left"}

- **Markera** \(![](images/review-highlight-icon.svg)\): Om du vill lägga till en markeringskommentar markerar du texten och klickar på markeringsikonen. Du kan också klicka på markeringsikonen och markera önskad text:

  ![](images/highlight-comment.png){width="650" align="left"}

  Ett popup-fönster visas på panelen Kommentarer där du kan lägga till din kommentar för det markerade innehållet.

- **Genomstruken** \(![](images/review-text-strike-through-icon.svg)\): Om du vill föreslå borttagning av innehåll kan du göra det genom att markera innehållet och klicka på genomstrykningsikonen. Du kan också markera önskad text och klicka på Delete-tangenten:

  Ett popup-fönster visas på panelen Kommentarer där du kan lägga till din kommentar för det borttagna innehållet.

- **Infoga text** \(![](images/review-insert-text-icon.svg)\): Om du vill infoga text klickar du på ikonen Infoga text och placerar markören där du vill infoga texten och skriver i informationen. Du kan också placera markören där du vill infoga text och börja skriva. Den tillagda informationen visas i grönt färgat teckensnitt:

- **Lägg till kommentar**\(![](images/review-comment-icon.svg)\): Om du vill lägga till en anteckningstyp för kommentar klickar du på ikonen Lägg till kommentar och anger kommentaren i popup-fönstret.


**Sammanhangsberoende verktygsfält**

Du kan också markera och genomstryka text snabbt med det sammanhangsberoende verktygsfältet. Utför följande steg för att kommentera med hjälp av det sammanhangsberoende verktygsfältet:

1. Markera den text som du vill markera eller genomstryka. Kontextverktygsfältet visas.

   ![](images/review-quick-launch-toolbar.png){width="550" align="left"}

1. Klicka på ikonen **Markera** eller **Genomstruken** .
1. Du kan lägga till kommentarer i kommentarpanelen för markerings- eller genomstrykningsåtgärden.

**Granska med panelen Kommentarer** - På panelen Kommentarer visas en lista med kommentarer som har angetts i det aktuella avsnittet. I den här panelen visas även kommentarer från andra granskare, om ämnet skickas till flera granskare. Varje kommentar på kommentarspanelen är länkad till motsvarande text i det aktuella ämnet. Den hjälper dig att identifiera kommenterad text. Varje kommentar visar namnet på granskaren som har lagt till kommentaren tillsammans med tidsstämpeln.

Kommentarerna visas i den ordning som de kommenteras i dokumentet. Det finns t.ex. en markeringskommentar på den första meningen och en infogad textkommentar på den andra meningen i det första stycket. Därefter visas markeringstexten före den infogade textkommentaren.

De åtgärder du kan utföra med panelen Kommentarer beskrivs nedan:

- Om du klickar på en kommentar markeras den motsvarande kommentarens plats i dokumentet och visas.
- Du kan lägga till svar på kommentarer.
- Du kan redigera din egen kommentar genom att klicka på den kommenterade texten på panelen Kommentarer och sedan välja **Redigera** på Alternativ-menyn.
- Du kan ta bort dina egna kommentarer genom att klicka på kommentaren på panelen Kommentarer och sedan välja alternativet **Ta bort** på Alternativ-menyn.

  ![](images/review-comment-options-menu.png){width="300" align="left"}

  >[!NOTE]
  >
  > Menyn Alternativ visas bara när du håller muspekaren över dina egna kommentarer. Den visas inte för kommentarer av andra granskare.

- Alla deltagande användare kan svara på kommentarer som lämnats av andra användare. Klicka på **Svara** och tryck på Retur för att skicka ett svar.

**Förhandsgranskningsläge**

- När du öppnar ett ämne i förhandsgranskningsläget visas hur ett ämne kommer att visas när det visas av en författare efter att alla ändringar har gjorts. Till exempel visas all infogad text som normal text och all borttagen \(borttagen\) text tas bort från innehållet.

- På följande skärmbild visas innehållet i *Granskningsläge*:

![](images/review-author-mode.png){width="550" align="left"}

På följande skärmbild visas innehållet i läget *Förhandsgranska*:

![](images/review-preview-mode.png){width="550" align="left"}

**Lägg till bifogade filer i kommentarer** -   Om du vill komplettera din kommentar genom att ange ytterligare information som är tillgänglig i en annan fil, kan du göra det genom att bifoga den med din kommentar. Som granskare kan du enkelt lägga till en eller flera filer från det lokala systemet i kommentaren. En fil kan läggas till i alla kommentarformer som stöds - Markera, Genomstruken, Infoga text eller Kommentar.

När du infogar någon av kommentarerna visas kommentarsfönstret. När du har angett ytterligare kommentarer eller information i popup-fönstret skickar du det genom att klicka på Retur. När kommentaren har lagts till kan du lägga till en bilaga till kommentaren.

![](images/comment-pop-up-panel.png){width="800" align="left"}

På skärmbilden ovan innehåller dokumentet popup-fönstret för markeringskommentaren och kommentaren läggs även till på panelen Kommentarer. Ikonen ![](images/file-attach-review.svg) för bifogad fil är tillgänglig tillsammans med kommentaren på båda platserna.

Utför följande steg för att lägga till en bifogad fil i kommentaren:

1. Klicka på ikonen *Lägg till bifogad fil* ![](images/file-attach-review.svg) för kommentaren som du vill lägga till en bifogad fil med.

   Dialogrutan Öppna fil visas.

1. Markera en eller flera filer som du vill bifoga.

   De markerade filerna visas tillsammans med kommentaren på kommentarpanelen.

   På panelen Kommentarer ser du filnamnet och dess storlek. Du kan också ta bort en fil genom att klicka på borttagningsikonen ![](images/Delete_icon.svg) som är associerad med filnamnet.

1. Klicka på **Skicka**.

   Bifogade filer överförs och läggs till i kommentaren.


**Ytterligare information om att arbeta med bifogade filer:**

- Som standard visas bara två filer som är bifogade med en kommentar. Om det finns fler filer visar knappen **Visa bifogad fil** till höger antalet bifogade filer \(som är fler än två\) som är associerade med kommentaren. Du kan klicka på numret om du vill visa alla bifogade filer. Om du t.ex. har fyra bilagor med en kommentar, visas +2 på knappen.

![](images/review-view-attachment.png){width="550" align="left"}

- När du placerar muspekaren över en bifogad fil kan du hämta eller ta bort den bifogade filen. Det går bara att ta bort den bifogade filen om den aktuella granskaren har lagt till kommentaren, vilket visas på följande skärmbild:

![](images/current-user-comment-options.png){width="550" align="left"}

De andra granskarna eller författarna får endast alternativet för att hämta bifogade filer.

![](images/other-reviewer-download.png){width="550" align="left"}

- Du kan hämta alla bifogade filer som är associerade med en kommentar från dialogrutan **Visa bifogade filer**. Markera de bifogade filerna och klicka på ikonen **Hämta** på kommentarsnivå.

- Du kan också ta bort de bifogade filer som är kopplade till en kommentar från dialogrutan **Visa bifogade filer**. Markera de bifogade filerna och klicka på ikonen **Ta bort** .

![](images/attach-files-comments-panel.png){width="550" align="left"}


**Villkorspanelen** -   Om ditt ämne har villkorsstyrt innehåll visas ikonen **Villkor** \(![](images/conditions-icon.svg)\) till höger. Om du klickar på ikonen **Villkor** öppnas panelen Villkor där du kan markera innehållet enligt de tillgängliga villkoren i avsnittet.

:   Som standard är alternativet **Markera alla villkor** aktiverat, alla villkor är markerade, hela innehållet visas och det villkorade innehållet visas som markerat både i gransknings- och förhandsgranskningsläge.

:   Du kan inaktivera alternativet **Markera alla villkor** och visa allt innehåll i ämnet som normal text utan högdagrar.

![](images/review-conditions-panel.png){width="350" align="left"}

Du kan välja att dölja eller visa ett visst villkor.

- Om du döljer ett villkor markeras inte innehållet som har det villkoret i granskningsläget.
- Om du visar ett villkorsstyrt innehåll markeras i granskningsläget. I följande skärmbild används till exempel bara två villkor för innehållet - `win` och `mac` markeras.


![](images/review-condition-normal-mode.png){width="650" align="left"}

I förhandsgranskningsläget visas det icke-villkorade innehållet och det villkorade innehållet som använder de två visade villkoren - `win` och `mac`. Det återstående villkorade innehållet som villkoren är dolda för visas inte.

**Realtidsgranskning** -   Panelen Kommentarer uppdateras i realtid med kommentarer och den feedback eller åtgärd som författaren har utfört på kommentarerna.

- Flera granskare kan lämna kommentarer eller svara på kommentarer samtidigt i samma dokument. Du kan ta reda på vem som håller på att granska dokumentet genom att hålla muspekaren över användarikonen i skärmens övre högra hörn.

- Om ett ämne ingår i flera granskningsåtgärder visas inte kommentarerna som gjorts i en uppgift i den andra uppgiften.

- Om du klickar på ikonen för inaktuell kommentar \(![](images/outdated-comment-icon.svg)\) visas skillnaderna mellan den senaste och den kommenterade versionen av dokumentet. Versionsnumren \(för de versioner som jämförs\) visas högst upp i dokumenten.

  ![](images/comments-page-review-mode.png){width="800" align="left"}

  >[!NOTE]
  >
  > När du håller pekaren över ikonen för inaktuell kommentar visas versionsnumret för det ämne som kommentaren lades till i. Om en kommentar till exempel har angetts i version 1.0 visas samma sak.

- När du klickar på en inaktuell kommentar öppnas kommentarens version på den vänstra panelen. Den föregående versionen visas på den vänstra panelen och den aktuella versionen visas på den högra panelen. Alla kommentarer i den inaktuella versionen importeras till vänster. Du kan jämföra den tidigare versionen med den aktuella versionen.

**Filtrera kommentarer** -   Du kan filtrera kommentarer i ett dokument om du vill visa specifika kommentarer. Om du vill filtrera kommentarer klickar du på ikonen **Filter** \(![](images/filter-search-icon.svg)\) som visas på menyn till höger om textrutan Sök kommentarer på panelen Kommentarer.

Välj ett eller flera av följande filtreringsalternativ i dialogrutan **Filtertyp** och klicka på **Använd**.

- **Granskningstyp** - Filtrera baserat på kommentartyp - Markering, Borttagning, Infogning eller Kommentar.
- **Granskningsstatus** - Filtrera baserat på status för kommentaren som Godkänd, Avvisad eller Ingen.
- **Granskare** - Filtrera baserat på granskarens namn.

- **Versioner** - Filtrera baserat på kommentarer som har tagits emot för en viss version av ämnet.

  När du använder filtren filtreras kommentarerna på den högra panelen efter markeringen, och antalet kommentarer i den vänstra panelen uppdateras därefter.


Om du vill ta bort filtret och visa alla kommentarer avmarkerar du alla filter i dialogrutan **Filtertyp** och klickar på **Använd**.

**Överordnat ämne:**[ Granska ämnen eller kartor](review.md)
