---
title: PDF publiceringsfunktion | Designa en sidlayout
description: Lär dig hur du utformar sidlayouten för att presentera information i olika delar av PDF-utdata.
exl-id: b4d3bdc4-0d01-46eb-b182-540380220485
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e8aecbdca448c321ac36804255416a4fb2561f79
workflow-type: tm+mt
source-wordcount: '5017'
ht-degree: 0%

---


# Designa en sidlayout {#design-page-layout}

När du skapar ett PDF-dokument har du olika avsnitt för att visa olika typer av information. Ett PDF-dokument kan till exempel börja med en framsida eller en försättssida, som skulle ha företagets logotyp, boktitel eller versionsinformation. Då finns det kapitel, bilagor eller ordlistor. Varje avsnitt i ett PDF-dokument ser olika ut och det uppnås genom att sidlayouten skapas och anpassas.

När du utformar en sidlayout kan du definiera de olika elementen som utgör en sida. Du kan till exempel definiera sidstorlek, marginaler, sidhuvud och sidfot, orientering och andra sidspecifikationer på en sida. Med den inbyggda PDF-publiceringsfunktionen kan du utforma din sida enligt [sidmediestandarden](https://www.w3.org/TR/css-page-3/). De flesta inställningar som omfattas av standarderna för sidindelad media kan enkelt anpassas med hjälp av PDF inbyggda publiceringsfunktioner. För viss annan formatering på avancerad nivå kan du använda Source-vyn för att skriva egen CSS-kod.

När du har utformat sidlayouten måste du koppla de här layouterna till deras respektive avsnitt i inställningarna för sidlayout i PDF. I avsnittet [Skapa och anpassa sidlayouter](components-pdf-template.md#create-customize-page-layout) finns mer information om hur du skapar och öppnar en sidlayout för anpassning.

## Typer av sidlayouter {#types-of-page-layout}

Ett PDF-dokument innehåller vanligtvis följande avsnitt:

* Försättssida
* Innehållsförteckning
* Sifferlyft
* Tabellens lyft
* Kapitel- eller ämnessidor
* Ordlista
* Index
* Baksida

Dessa avsnitt behöver en motsvarande sidlayout för att visa informationen i ett visst format. Dessutom kan du ha en tom sida som används som utfyllnadstecken för att starta ett nytt kapitel från en udda eller jämn sida. I så fall kan du antingen använda standardsidlayouten eller skapa en sidlayout för en tom sida. Mer information finns i [Skapa en ny sidlayout](components-pdf-template.md#create-page-layout).

Med sidlayoutsinställningarna under avsnittet **Mall>Inställningar** kan du definiera vilken sidlayout som ska användas för olika avsnitt i PDF. Varje sidlayout kan ha olika varianter för första, högra och vänstra sidan.

### Skapa de första, högra eller vänstra sidlayoutvarianterna {#page-layout-variants}

Olika sidlayouter i din PDF-mall kan anpassas ytterligare genom att ha olika layoutvarianter för första, högra och vänstra sidan. Du kan utforma dessa sidor på ett annat sätt med hjälp av layoutdesignern.

>[!NOTE]
>
>Om du vill ha en enda sidlayout för ett avsnitt i boken behöver du inte skapa sidlayouterna Första, Höger eller Vänster.

Tänk på följande när du skapar sidlayouterna:

>[!NOTE]
>
>Följande punkter har tagit kapitelsidlayouten som exempel. Dessa punkter gäller dock även för andra sidlayouter.

* Om du vill använda en enda sidlayout för alla sidor i ett kapitel skapar du bara en enda kapitelsidlayout utan någon variant.

* Om du vill ha ett annat utseende och en annan känsla för den första sidan för kapitel i boken måste du skapa en layout för första sidan för kapitlen.

* Om du vill ha ett annat utseende och en annan känsla för alla sidor på vänster och höger sida i boken måste du skapa varianterna på vänster och höger sida för kapitelsidans layout.

* Om du vill att kapitlen ska börja från en udda eller jämn sida kan du välja att skapa en sidlayout för den tomma sidan. Den här sidlayouten används för att fylla mellanrummet mellan två kapitel så att kapitlet börjar från önskad udda eller jämn sida.

  >[!NOTE]
  >
  >Om du inte skapar en separat tom sidlayout används standardsidlayouten. Mer information om hur du skapar en sidlayout finns i [Skapa en ny sidlayout](components-pdf-template.md#create-page-layout).

I följande exempel får du hjälp med att skapa varianter av en sidlayout:

1. Skapa en kapitelsidlayout med hjälp av stegen under Skapa en ny sidlayout.

   En tom kapitelsidlayout skapas och läggs till under Sidlayouter.

   När du skapar en sidlayout öppnas den som standard även för redigering. På följande skärmbild visas en tom (standard) sidlayout:

   <img src="./assets/default-blank-page-layout.png" width="300">

   Sidhuvudet, sidfoten och innehållsområdet i en mall skapas som standard. Du kan enkelt anpassa dessa områden med de sidegenskaper, innehållsegenskaper och olika verktyg (som att infoga bilder, fält med mera) som finns i användargränssnittet.

   >[!NOTE]
   >
   >För avancerad konfiguration kan du använda Source-vyn och lägga till din egen HTML- och CSS-kod.

1. Håll muspekaren över layouten **Kapitel** och klicka på **Alternativ** för att visa snabbmenyn.

1. Klicka eller håll muspekaren över **Lägg till layoutvariant** och välj önskad sidlayout (första, vänster eller höger) som du vill skapa.

Den valda sidlayouten skapas med en kopia av den grundläggande kapitellayouten. Det innebär att om du har gjort några ändringar i standardlayouten för kapitelsidor, kommer samma ändringar att replikeras i variantsidlayouten när sidlayouten skapas.

## Arbeta med sidegenskaperna för en sidlayout {#page-props-page-layout}

När du utformar en sidlayout är det viktigt att du har kontroll över olika sidegenskaper. Funktionen för PDF Publishing innehåller alla egenskaper för de vanligaste sidorna på panelen Sidegenskaper. På panelen Sidegenskaper finns olika egenskaper i följande avsnitt:

>[!NOTE]
>
>Panelen Sidegenskaper kapslar in egenskaperna och följer regler som definierats under [Page Media-standarden](https://www.w3.org/TR/css-page-3/).

* **Sidstorlek** : Ange den sidstorlek som du vill använda för sidlayouten. I listrutan Sidstorlek kan du välja mellan över 15 sidstorlekar. Du kan också skapa en sidlayout med en anpassad sidstorlek. Mer information finns i [Ange sidstorleken](#set-page-size).

* **Orientering** : Ange den sidorientering som ska användas för sidlayouten. Du kan välja mellan stående eller liggande sidorientering. Observera att du kan välja att använda olika orienteringar för olika sidvarianter i en sidlayout. Om innehållet till exempel innehåller en bred tabell eller en stor bild kan du skapa en liggande sidlayout och använda den layouten på den bredare tabellen eller bilden.

* **Vyrotation** : Ange den sida eller riktning som den ursprungliga översta sidan visas i efter rotation. Du kan välja mellan 90 grader medsols, 90 grader moturs eller 180 grader moturs. Detta är mycket användbart i en situation där du vill använda en kombination av stående och liggande layouter i utdata. Du kan till exempel använda stående som allmän sidlayout och du kan ange en liggande sidlayout för att återge breda tabeller. I så fall kan du ange att tabellinnehållet ska visas medsols 90 grader. På så sätt orienteras sidan liggande och innehållet roteras 90 grader för att kontinuiteten ska kunna bibehållas. Vi kommer att se hur detta uppnås som ett exempel senare i detta avsnitt.

* **Sidnumrering**:Sidnumreringen är som standard kontinuerlig i en PDF. En PDF med 100 sidor kan till exempel ha kontinuerliga sidnummer mellan 1 och 100. Du kan också starta om numreringen från ett visst nummer i alla olika avsnitt eller den första förekomsten av ett avsnitt.
   * **Starta om från** : Ange det sidnummer från vilket sidlayouten ska börja. Du kan till exempel ange att sidnumret ska startas om för varje kapitel. I så fall måste du ställa in omstarten från egenskap till 1 på layoutvarianten för första sidan i kapitelsidans layout. Som standard fortsätter sidnumreringen från föregående sida.

   * **Använd endast på den första förekomsten**: Du kan också starta från ett visst nummer för den första förekomsten av ett avsnitt. Du kan t.ex. starta endast det första kapitlet från 1 och fortsätta med sidnumren för andra kapitel.

* **Layout** : Ange sidmarginaler tillsammans med utfyllnad för övre, nedre, vänstra och högra sidor. Följande bild förklarar hur marginaler, utfyllnad och kanter återges runt innehållet. Observera att marginalen längst upp och längst ned på en sida innehåller sidhuvudet och sidfoten.

  <img src="./assets/margins-padding-illustration.png" width="300">

* **Bakgrund** : Inkludera en bild eller en färg som bakgrund i sidlayouten. För en bild kan du ange bildens höjd och bredd tillsammans med repeterings- och positionsegenskaper.

* **Fotnot** : Ange de egenskaper som fotnoterna ska visas i utdata. Du kan ange marginaler och utfyllnadsegenskaper tillsammans med ett kantlinjeformat.

### Ange sidstorlek {#set-page-size}

Det första du behöver definiera i en sidlayout är sidstorleken. I Sidegenskaper finns det över 15 sidstorlekar som du kan välja för en sidlayout. Du kan också skapa en anpassad sidstorlek genom att utföra följande steg:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på **Sidegenskaper** i den högra panelen.
1. I listrutan **Sidstorlek** väljer du **Egen**.

   Fälten Sidbredd och Sidhöjd visas.

1. Ange önskade sidmått i fälten **Sidbredd** och **Sidhöjd**.

   >[!NOTE]
   >
   >Några av de vanligaste enheterna är px (pixlar), pt (punkter), rem, em, % (procent) och in (tum).

### Använda sidorientering och vyrotation {#page-orientation-rotation}

Låt oss titta på ett exempel där en kombination av stående och liggande sidorientering och vyrotationsegenskaper används. I det här exemplet skapar vi en PDF med stående orientering som standard, men en tabell återges i liggande orientering med innehåll i 90-gradersvyn medurs. Resultatet ser ut ungefär så här:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

I ovanstående utdata visas informationen i kontaktlistan i liggande läge med innehållet roterat i 90 grader. Det återstående innehållet visas i normalt stående läge.

För att uppnå den här typen av utdata måste vi utföra följande huvudsakliga uppgifter:

1. Skapa en sidlayout med liggande orientering.

1. Ändra egenskapen **Visa rotation** om du vill återge innehåll i 90°.

1. Skapa ett anpassat format för den nya sidlayouten.

1. Lägg till formatet i utdataklassdefinitionen för den tabell som ska återges i liggande sidlayout.

Utför följande steg för att utföra ovanstående åtgärder:

1. Skapa en sidlayout med liggande orientering.
   1. Skapa en liggande sidlayout med hjälp av stegen under Skapa en ny sidlayout.

   1. Klicka på **Sidegenskaper** i den högra panelen.

      <img src="./assets/page-properties-panel.png" width="300">
   1. Ändra **orienteringen** till **Liggande**.

1. Ändra egenskapen Visa rotation om du vill återge innehåll 90° medsols.

   1. Välj **Medsols 90°** i listrutan Vyrotation.

   <img src="./assets/view-rotation-page-props.png" width="300">

   1. Klicka på **Spara alla** för att spara de uppdaterade sidlayoutegenskaperna.

1. Skapa ett anpassat format för den nya sidlayouten.
   1. Expandera den vänstra sidlisten och dubbelklicka på mallen som du vill skapa formatet i.

   1. Expandera avsnittet Formatmallar.

   1. Håll pekaren över layoutformatmallen och klicka på ikonen (_Alternativ_ ) ... och välj Redigera.

      Layoutformatmallen öppnas för redigering.

   1. Högerklicka på **Andra format** och välj **Nytt format**.

      <img src="./assets/stylesheet-other-new-style.png" width="300">

   1. Ange **liggande stil** i **klassnamnet** i popup-fönstret Lägg till stil.

      <img src="./assets/stylesheet-new-landscape-style.png" width="400">

   1. Klicka på **Klar**.

      Ett nytt format med namnet `.landscape-style` skapas och läggs till i slutet av listan Andra format.

   1. Dubbelklicka på formatet `.landscape-style` för att öppna det för redigering.

   1. Expandera egenskapen **Sidnumrering**.

   1. Ange `Landscape` i egenskapen **Sidlayout**.

      <img src="./assets/new-style-with-landscape-layout.png" width="500">

   1. Klicka på **Spara alla** om du vill spara de uppdaterade formategenskaperna.

1. Lägg till formatet i definitionen `outputclass` för tabellen som ska återges i liggande sidlayout.
   1. Öppna filen där du vill använda den nya sidlayouten i en DITA-filredigerare.

   1. Hitta elementet `<table>` som ska återges i liggande läge.

   1. Markera tabellen genom att klicka på tabellelementet i den synliga sökvägen.

      <img src="./assets/new-style-table-element.png" width="400">

   1. Klicka på och öppna panelen Innehållsegenskaper i den högra panelen.

   1. Lägg till en ny **outputClass** -egenskap med **landscape-style** som egenskapsvärde på panelen Innehållsegenskaper.

      <img src="./assets/new-style-table-outputclass.png" width="300">

1. Klicka på **Spara alla** för att spara den uppdaterade filen.
1. Generera PDF-utdata.

På den slutliga PDF återges tabellinnehållet i liggande läge, vilket visas i början av exemplet.

### Lägga till en bakgrundsbild {#add-bg-image}

Beroende på dina behov kan det vara bra att lägga till en bakgrundsbild som visas på varje första sida i ett kapitel (PDF). Med bakgrundsegenskaperna under Sidegenskaper kan du enkelt lägga till en bakgrundsbild. Du kan välja att replikera bilden över en sida och placera bilden var som helst i sidans övre, nedre eller mitt.

Om du till exempel vill infoga en bakgrundsbild i mitten av innehållsområdet utför du följande steg:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka var som helst i innehållsområdet.

1. Klicka på **Sidegenskaper** i den högra panelen.

1. Expandera avsnittet **Bakgrund**.

1. Klicka på bläddringsknappen i fältet **Bildsökväg**.

1. Bläddra till och välj den bild som du vill använda som bakgrundsbild.

   Bilden infogas och replikeras för att täcka hela sidan.

1. Ändra bildstorleken genom att justera egenskaperna height och width.

   >[!NOTE]
   >
   >Du kan ange egenskaperna height eller width eftersom bilden skalas automatiskt för att behålla proportionerna.

1. Ange de andra egenskaperna för att justera hur du vill att bakgrundsbilden ska visas.

   * **Upprepa bakgrund** : Ange om du vill att bakgrunden ska upprepas eller inte.

   * **Bakgrundsposition** : Ange en position för bakgrundsbilden på sidan.

På följande skärmbild visas bakgrundsbilden med egenskapen Upprepa bakgrund inställd på _ingen upprepning_ och egenskapen Background Position inställd på _center_.

<img src="./assets/background-image.png" width="500">

## Arbeta med sidhuvud och sidfot {#work-header-footer}

När du tar med information i ett sidhuvud eller en sidfot i en sidlayout upprepas informationen på alla sidor som använder den sidlayouten. Vanligtvis används sidhuvudsområdet för kapitel- eller ämnesrubriker och sidfotsområdet används för att visa sidnummer.

När du skapar en ny sidlayout skapas sidhuvuds- och sidfotsområdet som standard. Du kan göra många anpassningar i sidhuvuds- och sidfotsområdet i en sidlayout. Du kan till exempel infoga en bild (som en logotyp), variabler (som innehåller dynamisk information) eller statiskt innehåll.

### Ändra marginaler och linjer för sidhuvud och sidfot {#header-footer-margins}

Som standard är sidhuvud- och sidfotsmarginalerna inställda på 1 tum. Du kan ändra standardvärdet genom att ändra inställningen Marginal på panelen Sidegenskaper. Gör så här för att ändra sidhuvuds- och sidfotsstorlek:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på **Sidegenskaper** i den högra panelen.
1. Expandera avsnittet **Layout**.
1. Klicka på låsikonen bredvid egenskapen **Marginal** .
1. Om du vill ändra rubrikstorleken anger du det önskade värdet i fältet Övre marginal.

   >[!NOTE]
   >
   >Några av de vanligaste enheterna är px (pixlar), pt (punkter), rem, em, % (procent) och in (tum).

1. Om du vill ändra sidfotsstorleken anger du det önskade värdet i fältet Undre marginal.

Du kan utforma sidhuvuds- och sidfotsområdet så att det innehåller flera rader. Om du vill göra det lägger du till en \&lt;p\>-tagg med hjälp av Infoga HTML Elements (<img src="./assets/insert-html-element-2.svg" width="25">) i sidhuvuds- eller sidfotsområdet.

| _Developer Corner_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Om du vill arbeta direkt med CSS- och HTML-koden kan du ändra marginalvärdena enligt följande kodfragment:

```css
…

<meta name="page-style" content="size:A4 portrait;margin-top:3cm;margin-right:30pt;margin-bottom:1in;margin-left:90px;" />

…
```

>[!NOTE]
>
>I ovanstående exempel används olika enheter för att ange marginalvärden.

### Ta bort sidhuvud och sidfot {#remove-header-footer}

Sidhuvudet och sidfoten överlagras i de övre och nedre marginalerna. Tekniskt sett innebär det att om du vill ha ett sidhuvud och en sidfot i sidlayouten måste du reservera det utrymme som behövs i de övre och nedre marginalerna.

Om du inte vill att en sidlayout ska ha ett sidhuvud och en sidfot, finns det två sätt att uppnå detta:

* Om du vill behålla de övre och nedre marginalerna lämnar du sidhuvuds- och sidfotsområdet tomt.
* Om du inte vill behålla de övre och nedre marginalerna (som att utforma fram- och bakomliggande omslag för ett magasin) kan du ta bort marginalerna genom att ange egenskaperna för den övre och den nedre marginalen till 0. Detta lämnar inget utrymme för sidhuvudet och sidfoten.

### Lägga till en bild eller logotyp i sidhuvudet {#add-image-header}

Beroende på dina behov kan du lägga till en bild som visas i sidhuvudsområdet (eller någon annan del) i sidlayouten. Det finns två sätt att lägga till en bild i sidlayouten:

* Använd en bild från mallresurserna.
* Använd verktyget \&lt;Lägg till bild\> i sidlayoutredigeraren.

>[!NOTE]
>
>Vi rekommenderar att du använder resursmappen för att hantera alla mallresurser, som bilder och teckensnitt.

Så här infogar du en bild som ditt företags logotyp i sidhuvudsområdet:

1. Öppna önskad sidlayout för redigering.

>[!NOTE]
>
>Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på Redigera sidhuvud (<img src="./assets/header-icon.svg" width="25">) för att föra markören i sidhuvudsområdet.

   Du kan också klicka inuti sidhuvudsområdet.

1. Om du vill lägga till en bild väljer du någon av följande metoder:
1. Klicka på **Infoga bild** (<img src="./assets/insert-image-icon.svg" width="25">) i verktygsfältet. I popup-fönstret **Välj sökväg** bläddrar du till bildplatsen och klickar på **Markera** för att infoga den i sidhuvudsområdet.
1. Dra och släpp en bild från resursmappen i sidhuvudsområdet.

I följande skärmbild visas en exempelbild som lagts till i sidhuvudsområdet.

<img src="./assets/image-in-header-area.png" width="500">

När en bild har infogats kan du ändra dess attribut så att den ser ut som du vill ha den. Det enklaste sättet att ändra hur en bild eller något annat element på sidlayouten ser ut är att använda panelen Innehållsegenskaper. Se [Arbeta med panelen Innehållsegenskaper](#work-with-content-props) för de olika egenskaper som är tillgängliga via gränssnittet för att anpassas.

### Lägga till fält och metadata {#add-fields-metadata}

Fält är mycket användbara när du vill infoga en del av informationen som är fördefinierad. Du kan till exempel inkludera ett fält för kapitelrubrik i kapitlets rubrikområde som ersätts med det verkliga kapitlets rubrik när det publiceras.

Det finns följande kategorier för fält som du kan infoga i sidlayouten:

* Metadata
* Ämnestitel
* Kapitelrubrik
* Karttitel
* Sidnummer
* Kapitelnummer
* Totalt antal sidor
* Datum
* Tid


Var och en av dessa fältkategorier innehåller olika variationer där fältinformationen kan infogas. Ett datumfält kan t.ex. ha olika variationer som `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY` o.s.v. På samma sätt kan sidnummer ha variationer i form av latinska, decimala eller till och med språkspecifika format som _arabiska_, _devanagari_, _hebreiska_ med flera.


Förutom de fördefinierade fälten kan du även lägga till metadatainformation som variabler eller fält i sidlayouten. Dessa metadata kan lagras i DITA-källans **kartinnehåll**, **ämnesinnehåll** eller hämtas från DITA-filens **mappningsegenskaper**, **ämnesfilsegenskaper**.

Du kan välja metadata bland följande alternativ:

* **Kartinnehåll** innehåller metadata som du har definierat i elementet `<topicmeta>` i DITA-kartan.
* **Kartfilsegenskaperna** innehåller metadata som du kan få åtkomst till från sidan **Egenskaper** på en DITA-karta.
* **Ämnesinnehåll** innehåller metadata som definierats i elementet `<prolog>` i ett DITA-ämne, till exempel copyright, författare och annan information. Om du vill hämta enskilda `<prolog>`-element kan du använda enkla XPath-uttryck (t.ex. //author som författarnamn). För attributmetadata inkluderar du symbolen `@` i XPath (t.ex. //requirements/revised/@modified for the modified date).
* **Egenskaper för ämnesfiler** innehåller metadata som du kommer åt från sidan **Egenskaper** i ett ämne.


Du kan kombinera metadata från **egenskaper för kartfiler** och **egenskaper för ämnesfiler** i ett enda dokument. Du kan t.ex. publicera en PDF-fil med karttiteln på försättsbladet och ämnestiteln i sidhuvudet på andra sidor. Det gör du genom att lägga till mappningens rubrikmetadata från egenskaperna för **mappfilen** i försättsbladets layout. Lägg sedan till metadata för ämnesrubriken från **ämnesfilegenskaperna** i rubriken på sidlayouten för kapitel och avsnitt.

Om ett avsnitt slutar på en sida och det andra börjar på samma sida, väljs metadata för det första avsnittet. Du kan också lägga till anpassade egenskaper och sedan infoga dem som fält i sidlayouten.


>[!NOTE]
>
> Metadatafälten visas enligt ditt val av resurs eller karta i listrutan **Från**.




<!--For more information, see [Add fields and metadata](design-page-layout.md#add-fields-and-metadata).-->

I följande exempel infogar vi ett sidnummer och en kapitelrubrik i sidfotsområdet i en sidlayout.

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Klicka på ikonen **Redigera sidfot** (![](./assets/footer-icon.svg)) för att placera markören i sidfotsområdet.

   Du kan också klicka inuti sidfotsområdet.

1. Infoga ett styckeelement genom att klicka på **Infoga HTML Elements** (<img src="./assets/insert-html-element-2.svg" width="25">) och väljer Stycke i listan med element.

1. Klicka på ikonen **Infoga fält** (![](./assets/insert-fields-icon.svg)).

   Popup-fönstret Fält visas.

1. Välj kategorin **Sidnummer** i fältlistan, sidnummerformatet **default(1)** i formatlistan och klicka på **Infoga**.

   <img src="./assets/insert-page-number-field.png" width="400">

   >[!NOTE]
   >
   >Du kan också redigera formatet för alla fält, förutom standardformatet. Om du vill göra det klickar du på ikonen Redigera bredvid formatet som du vill redigera, gör ändringar och klickar på OK. Mer information finns i [Lägg till fält och metadata](#add-fields-metadata).

   Standardsidnummerfältet infogas i sidfotsområdet i sidlayouten.

   <img src="./assets/page-number-field-in-footer.png" width="400">

   Den översta vägledningen visar de element som informationen lagras i.

1. Ange ett tomt utrymme efter sidnummerfältet och klicka på ikonen **Infoga fält** .

1. Välj kategorin **Kapiteltitel** i fältlistan, formatet **Kapiteltitel** i formatlistan och klicka på **Infoga**.

   Fältet _Kapitelrubrik_, som fylls i med kapitlets rubrik vid publiceringstillfället, infogas i sidfotsområdet. För närvarande är sidnummerfälten och kapiteltitelfälten avgränsade med ett blanksteg.

   <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. Så här högerjusterar du kapiteltiteln:

   1. Klicka på fältelementet på vägbeskrivningssidan för att välja fältet Kapitelrubrik.

   1. Klicka på **Innehållsegenskaper** i den högra panelen (<img src="./assets/content-properties-icon.png" width="25">).

   1. Expandera egenskapsavsnittet **Layout** och ange **Float**-egenskapsvärdet till **right**.

      <img src="./assets/float-prop-html-content.png" width="400">

      Fältet Kapiteltitel är justerat mot sidfotens högra sida.
      <img src="./assets/topic-title-moved-right-footer.png" width="500">


| _Developer Corner_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Om du vill arbeta direkt med CSS- och HTML-koden kan du även göra det genom att gå till Source-vyn av sidlayouten och göra ändringar i koden. I följande kodutdrag visas samma sidfotsinställning som i koden:

```css
…
<p>

<span data-field="page-number" data-format="default">1</span>

<span data-field="chapter-title" data-format="default" style="float: right">Chapter Title</span>

</p>
…
```

## Arbeta med innehållsområdet {#content-area}

Innehållsområdet är det största området när det gäller innehållsområdet. Innehållsområdet fylls i med innehållet i ditt ämne. I vissa speciella fall kan du lägga till mallinnehåll i innehållsområdet. Det här innehållet publiceras på den angivna platsen i sidlayouten. Rubriken i innehållsförteckningen, ordlistan och indexet kan t.ex. läggas till som mallinnehåll, som publiceras &quot;i befintligt skick&quot; i det slutliga resultatet. Ett annat exempel är kapitelinnehållsförteckningen, som vanligtvis läggs till på den första sidan i varje kapitel.

En av de vanligaste anpassningarna i innehållsområdet är layouten med flera kolumner. Med den kraftfulla layoutaren kan du anpassa specifika sidor som ska återges i flera kolumner samtidigt som innehållet på andra sidor behålls i en enda kolumn.

I följande avsnitt beskriver vi olika scenarier för att anpassa innehållsområdet.

### Lägga till en kapitelinnehållsförteckning {#add-chapter-toc}

En kapitelinnehållsförteckning fungerar som en snabb referens för läsarna så att de vet vad som finns i kapitlet. Vanligtvis läggs ett kapitel till i början av ett kapitel. Om du vill använda en kapitelinnehållsförteckning kan du lägga till den i innehållsområdet för huvudkapitelsidans layout eller den första sidlayoutvarianten för ett kapitel.

I följande exempel infogar vi en kapitelinnehållsförteckning i den första sidlayouten i ett kapitel:

>[!NOTE]
>
>I den här proceduren antas att du har skapat varianten Första sidan för en kapitelsidlayout. Instruktioner om hur du skapar en sidvariant finns i [Skapa de första, högra eller vänstra sidlayoutvarianterna](#page-layout-variants).

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-a-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Placera markören i innehållsområdet i sidlayouten.

1. Klicka på kapitelinnehållet (<img src="./assets/chapter-toc-icon.svg">).

   Standardkapitelinnehållsförteckningen infogas i innehållsområdet.

   <img src="./assets/chapter-toc-default.png" width="400">

   >[!NOTE]
   >
   >Standardkapitlet innehåller rubrikerna 1 till 4. Här är rubrik 1 kapitelrubriken. Du kanske inte vill ha kapiteltiteln igen i innehållsförteckningen eller du kanske vill öka nivån på rubrikerna i innehållsförteckningen. Du kan anpassa innehållsförteckningen genom att ändra egenskaperna.

1. Öppna panelen Innehållsegenskaper för att anpassa rubriknivåerna i innehållsförteckningen.

   Om du till exempel vill börja med Rubrik 2, ändrar du den första listrutan till att börja med 2.

   <img src="./assets/customize-chapter-toc.png" width="400">

   Om du vill ha rubriker upp till nivå 5 ändrar du den andra listrutan till 5. Den uppdaterade innehållsförteckningen kommer att se ut så som visas nedan:

   <img src="./assets/chapter-toc-updated.png" width="400">

   >[!NOTE]
   >
   >I den slutliga publicerade PDF visas bara innehållsförteckningsposterna baserat på innehållet i dina kapitel. Om du inte har rubriker på nivå 5 i ett kapitel visas det inte i det slutliga resultatet.

Utseendet på standardinnehållsförteckningen kan anpassas med hjälp av formatmallarna. Det format som börjar med `chaptoc-level-#` (till exempel `chaptoc-level-1`, `chaptoc-level-2`) används för att anpassa formaten för kapitelinnehållsförteckningen. <!--For more details on the stylesheet elements used in the TOC and how to customize them, see _Customize default chapter TOC_-->.

>[!IMPORTANT]
>
>Om du uppdaterar en formatmall i en formatmall kanske den inte visas i innehållsförhandsvisningen. Utdata återges dock med de uppdaterade formaten.

### Arbeta med sidlayout med flera kolumner {#multi-column-layout}

Layouter med flera spalter är mycket vanliga när du publicerar tidskrifter eller index i en bok. Med den inbyggda PDF Publishing-funktionen kan du enkelt dela upp dokument i flera kolumner. Om du använder olika sidlayouter kan du välja att bara behålla ett visst avsnitt uppdelat i flera kolumner samtidigt som de andra avsnitten behålls i en enda spalt (eller normal) layout.

Så här skapar du en sidlayout med flera kolumner:

1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   >Se [Anpassa en sidlayout](components-pdf-template.md#customize-a-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. När layouten med flera kolumner används på innehållet, med undantag för sidhuvud och sidfot, måste du markera innehållselementet i sidhuvudet.

   När du har markerat innehållets kolumnbredd visas egenskaperna för flera kolumner på panelen Innehållsegenskaper.

   <img src="./assets/multiple-columns-properties.png" width="400">

1. Använd egenskaperna för flera kolumner för att anpassa sidlayouten med flera kolumner:

   * **Antal kolumner:** Ange antalet kolumner som sidan ska delas upp i. Använd upp- och nedpilsikonerna eller ange ett tal för att ange antalet kolumner.

   * **Kolumnbredd:** Ange bredden på en kolumn i en layout med flera kolumner. Som standard anges storleken i pixlar (px), och du kan även ange den i pt, rem, em, % eller i enheter.

     >[!NOTE]
     >
     >Om du inte anger någon storlek delas kolumnerna jämnt så att de passar på den angivna sidan. I de flesta fall behöver du inte ange det här värdet.

   * **Kolumnmellanrum** : Ange mellanrum mellan enskilda kolumner.

   * **Kolumnintervall** : Om du vill att ett element på sidlayouten ska spänna över flera kolumner måste du använda den här egenskapen. Detta uppnås genom att du ändrar formatet för det önskade elementet med formatmallarna. <!--for more information see _Section explaining style customization_-->.

   Om du i sidlayouten vill att en viss text ska visas på den första sidan i alla kapitelsidlayouter, kan du lägga till den i varianten för den första sidan i kapitelsidlayouten.

   Som framgår av följande exempel är egenskapen Spänn över spalt för rubriktexten inställd på alla. Detta garanterar att även om dokumentet är flerspaltig, sträcker sig rubriken över flera spalter.

   <img src="./assets/element-span-across-columns.png" width="400">

   >[!IMPORTANT]
   >
   >Du kan använda Span Column-egenskapen för alla DITA-element med hjälp av attributet outputClass.

   * **Kolumnfyllning** : Ange hur innehåll fyller kolumner. Som standard är det inställt på Balans, vilket fyller varje kolumn med samma mängd innehåll.

   * **Kolumnregel** : Om du vill ha en linje mellan kolumnerna använder du den här egenskapen för att definiera linje- eller linjestilar. Ange värden för linjens format, färg och bredd om du vill lägga till en linje mellan kolumnerna.

## Arbeta med panelen Innehållsegenskaper {#work-with-content-props}

Med panelen Innehållsegenskaper kan du enkelt uppdatera utseendet och känslan hos elementen i sidlayouten. Egenskaperna under panelen Innehållsegenskaper är uppdelade i följande avsnitt:

* **Teckensnitt** : Innehåller textrelaterade egenskaper. Du kan ange Teckensnittsfamilj, Teckenbredd, Storlek, Textdekoration (som understrykning, överstrykning, genomstrykning), Textformat (som fet, Kursiv med mera), Textjustering (som vänster, höger, mitten eller marginaljusterad), Hantera blanksteg (som fördefinierat format, ingen radbrytning, radmellanrum med mera), Radhöjd, Teckenavstånd och Textindrag.

* **Kant** : Innehåller egenskaper för att lägga till och formatera en kantlinje i ett element i sidlayouten. Du kan ange Kantsida (som alla, översta, nedersta, högra eller vänstra), Kantformat (som heldragen, streckad, prickade linjer eller fler), Kantfärg, Bredd och Radius för en böjd kant. I följande exempel har en böjd kantlinje lagts till i sidhuvudsområdet på sidan.

  <img src="./assets/border-properties.png" width="500">

* **Layout** : Innehåller egenskaper för att konfigurera layouten för ett element i sidlayouten. Du kan ange Höjd, Bredd, Marginaler och Utfyllnad (för överkant, nederkant, vänster eller höger), Vågrät eller Lodrät justering, Flyt (som vänster, höger eller ingen), Rensa (som vänster, höger, båda eller ingen), Elementets position (som absolut, fast, relativ eller mer), Visa (som block, innehåll, korrigera eller mer), Z-index, Genomskinlighet, Omforma (genom att rotera eller rotera skalförändring) och Omforma ursprung (med X- och Y-förskjutning).

* **Bakgrund** : Innehåller egenskaper för att inkludera en bakgrundsbild eller färgskugga. Du kan ställa in bildstorlek (genom att ställa in höjd eller bredd), Upprepa bakgrund (som upprepning, ingen upprepning, rund eller mer) och Bakgrundsposition (som vänster överkant, höger mittpunkt, centrera nederkant eller mer).
* **Flera kolumner** : Innehåller egenskaper för att konfigurera flerkolumnegenskaper för sidan eller andra specifika element, som kapitelinnehållsförteckning. Mer information om egenskaperna och hur du använder dem finns i [Arbeta med sidlayout med flera kolumner](#multi-column-layout).
