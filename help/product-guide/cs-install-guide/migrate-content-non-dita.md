---
title: Migrera icke-DITA-innehåll
description: Lär dig hur du migrerar icke-DITA-innehåll
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
feature: Migration
role: Admin
level: Experienced
source-git-commit: cddbd7a19d4dfaa3f6549ed1bd511eeeb02acbb2
workflow-type: tm+mt
source-wordcount: '2940'
ht-degree: 0%

---

# Migrera icke-DITA-innehåll {#id181AH0R02HT}

I det här avsnittet får du hjälp med att migrera icke-DITA-dokument till DITA-format. AEM Guides erbjuder migrering från följande källor:

- [Microsoft Word](#id1949B040Z5Z)

- [InDesigner](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Ostrukturerade FrameMaker](#id1949B050VUI)

- [Andra strukturerade dokument](#id1949B0590YK)


## Migrera Microsoft Word-dokument {#id1949B040Z5Z}

Med AEM Guides kan du migrera dina befintliga Word-dokument \(`.docx`\) till ämnesdokument för DITA. Du måste ange in- och utdatamappens placering tillsammans med andra parametrar så konverteras dokumentet till DITA-dokument. Beroende på innehållet kan du ha en .dita-fil och en .ditamap-fil.

Om du vill kunna konvertera ett Word-dokument utan problem bör dokumentet vara välstrukturerat. Dokumentet ska t.ex. ha en rubrik följt av Rubrik 1, Rubrik 2 osv. Varje rubrik ska ha lite innehåll. Om dokumentet inte är välstrukturerat kanske processen inte fungerar som förväntat.

Som standard använder AEM Guides omformningsramverket [Word-till-DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Omvandlingen är beroende av konfigurationsfilen [format-till-tagg-mappning](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html). Om du vill kunna använda Word2DITA-omformningen utan problem måste du ta hänsyn till följande riktlinjer när du förbereder Word-dokumentet för konvertering:

>[!NOTE]
>
> Om du gör några ändringar i standardkonfigurationsfilen för format-till-tagg-mappning måste du uppdatera och använda riktlinjerna som bekräftar den uppdaterade formatmappningen.

- Kontrollera att dokumentet börjar med en titel. Den här titeln är mappad till DITA-kartans titel. Titeln måste följas av regelbundet innehåll.

- Efter rubriken ska det stå Rubrik 1, Rubrik 2 och så vidare. Varje rubrik måste ha lite innehåll. Rubrikerna konverteras till nya koncepttyper. Hierarkin för de genererade avsnitten är densamma som för rubriknivåerna i dokumentet, t.ex. kommer Rubrik 1 före Rubrik 2 och Rubrik 2 före innehållet för Rubrik 3.

- Dokumentet måste ha minst ett rubriktypsinnehåll.

- Se till att du inte har några grupperade bilder. Om du har grupperat bilder i dokumentet, ska du dela upp alla sådana bilder.

- Ta bort alla sidhuvud och sidfot.

- Textbundna format som fet, kursiv och understrykning konverteras till elementen `b`, `i` och `u`.

- Alla sorterade och osorterade listor konverteras till elementen `ol` och `ul`. Detta gäller även kapslade listor, listor i tabeller, anteckningar och fotnoter.

- Alla hyperlänkar konverteras till `xref`.

- Filnamnet för de konverterade filerna baseras på rubriktexten följt av ett filnummer. Filnumret är ett sekventiellt nummer baserat på rubrikens position i dokumentet. Om en rubriktext till exempel är &quot;Sample Heading&quot; och den är 10:e rubriken i dokumentet, kommer det resulterande filnamnet för det här avsnittet att likna Sample\_Heading\_10.dita.


Följ de här stegen för att konvertera befintliga Word-dokument till ämnesdokument i DITA:

1. Använd Package Manager för att hämta filen /libs/fmdita/config/w2d\_io.xml.

1. Anpassa den hämtade w2d\_io.xml-filen.

1. Lägg till filen på följande plats i din Cloud Manager Git-databas:

   /apps/fmdita/config/w2d\_io.xml

   Filen `w2d_io.xml` innehåller följande konfigurerbara parametrar:

   - I elementet `inputDir` anger du platsen för indatamappen där dina Word-källdokument är tillgängliga. Om dina Word-dokument till exempel lagras i en mapp med namnet `wordtodita` i mappen `projects` anger du platsen som: `/content/dam/projects/wordtodita/`

   - I elementet `outputDir` anger du platsen för utdatamappen eller behåller standardplatsen för utdata för att spara det konverterade DITA-dokumentet. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - Ange om en ny version av det konverterade DITA-avsnittet ska skapas \(`true`\) eller inte \(`false`\) för elementet `createRev`.

   - I elementet `s2tMap` anger du platsen för den mappningsfil som innehåller mappningar för Word-dokumentformat till DITA-element. Standardmappningen sparas i filen som finns på:

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Mer information om strukturen för filen `word-builtin-styles-style2tagmap.xml` och hur du kan anpassa den finns i [Koppla format till tagg](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) i *DITA för utgivare*.

   - I elementet props2Propagate anger du de egenskaper som ska överföras till DITA-kartan. Den här egenskapen krävs för att skicka standardmetadata som dc:title,dc:subject,dam:keywords,dam:category från dokumentmetadata till konverterade DITA-resurser.

1. Kör Cloud Manager pipeline för att distribuera den uppdaterade konfigurationen.

1. När du har konfigurerat de obligatoriska parametrarna i filen `w2d_io.xml` loggar du in AEM och öppnar Assets-gränssnittet.

1. Navigera till indatamappens plats \(`wordtodita`\).

1. Överför Word-källdokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


Med blocket `config` `/config` kan du definiera ett eller flera block med konfigurationer för konvertering. Konverteringsarbetsflödet körs och det slutliga resultatet i form av ett DITA-avsnitt sparas på den plats som anges i `outputDir`-elementet.

**Anpassningsuppdateringar för befintliga användare**

Om du redan använder AEM Guides as a Cloud Service och uppgraderar från augusti 2021-versionen till januari 2022 eller senare ska du uppdatera de angivna egenskaperna så fort några filer har flyttats.

>[!NOTE]
>
> Den här uppdateringen gäller endast om du redan använder konverteringsarbetsflödet Microsoft Word till DITA.

- Filsökväg: /apps/fmdita/config/w2d\_io.xml
- Ändra värdet för `<s2tMap>` från /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml till /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Gör de ändringar som behövs i din Cloud Manager Git-databas, precis som för molntjänster, så överlagras alla filer i /apps via Cloud Manager Git.

## Migrera Adobe InDesign-dokument {#id195AD0B0K5Z}

Med AEM Guides kan du konvertera InDesigner. På samma sätt som med FrameMaker kan du med InDesign skapa ostrukturerade och strukturerade dokument. I det ostrukturerade dokumentet används stycke- och teckenformat för att formatera innehåll. I det strukturerade dokumentet används element och deras motsvarande attribut.

Vid konverteringen måste stycke- och teckenformatsformaten mappas till relevanta DITA-element. På samma sätt kommer mappningsfilen att innehålla en-till-en-mappning av element och attribut i InDesignen med DITA-element och -attribut i strukturerade dokument.

Konverteringsprocessen omfattar följande åtgärder i serverdelen:

- Filen *InDesign Markup Language* \(IDML\) packas inte upp till en arbetskatalog.
- Filen designmap.xml läses för att hitta de enskilda InDesignerna.
- Alla artiklar sammanfogas till en enda XML-instans, tomma artiklar ignoreras.
- Alla inbäddade bilder exporteras.
- Förkonvertering av standardstrukturer som tabeller och grafik till DITA-format.
- Koppling format eller struktur till slutliga utdata baserat på mappningsfilen.
- Skapa och validera enskilda DITA-ämnen och DITA-kartfiler.
- Borttagning av temporära filer.

I konverteringsprocessen måste du dessutom [Förbered InDesign-filer för konvertering](appendix.md#id195DBF0045Z) [appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) och [Förbered mappningsfilen för InDesign till DITA-migrering](appendix.md#id194AF0003HT) [appendix.md\#id194AF003HT&lbrace;5 &#x200B;](appendix.md#id194AF0003HT) måste du följa den angivna proceduren för att köra konverteringsprocessen.

Följ de här stegen för att konvertera befintliga InDesigner till ämnesdokument i DITA:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/config/idml2dita_io.xml`
1. Om du vill skapa en anpassad konfiguration enligt dina krav skapar du en överläggsnod av mappen `config` i noden `apps`.

1. Kopiera följande filer eller mappar från mappen `libs` till programmappen:

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/idml2dita_io.xml`

1. Lägg till mappningen av konfigurationerna i mappen `idml12dita` i filen `idml2dita_io.xml`.
1. Lägg till följande egenskaper i filen `idml2dita_io.xml`:

   ```
   <entry          key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

1. Skapa en överläggsnod av mappen `config` i noden `apps`.


   Konfigurera följande parametrar i filen `idml2dita_io.xml`:

   - I elementet `inputDir` anger du platsen för indatamappen där källdokumenten är tillgängliga. Om dina InDesign-dokument till exempel lagras i en mapp med namnet `indesigntodita` i mappen `projects` anger du platsen som: `/content/dam/idmlfiles/indesigntodita/`

   - I elementet `outputDir` anger du platsen för utdatamappen eller behåller standardplatsen för utdata för att spara det konverterade DITA-dokumentet. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - I elementet `mapStyle` anger du platsen för den mappningsfil som innehåller mappningar för InDesignens dokumentformat till DITA-element. Standardmappningen sparas i filen som finns på:

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Mer information om strukturen för filen `stmap.adobeidml.xml` och hur du kan anpassa den finns i avsnittet [&#x200B; appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT) i bilagan.

1. Spara filen `idml2dita_io.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `idml2dita_io.xml` loggar du in AEM och öppnar Assets-gränssnittet.

1. Navigera till indatamappens plats \(`indesigntodita`\).

1. Överför källfilerna till den här InDesignen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


## Migrera XHTML-dokument {#id1949B04L0Y4}

Med AEM Guides kan du konvertera befintliga XHTML-dokument till ämnesdokument i DITA. Du måste ange mapplatser för in- och utdata tillsammans med andra parametrar och dokumenten konverteras till DITA-format. Det finns två metoder som du kan använda för att konvertera strukturerade HTML-dokument:

- Överför alla dokument till indatamappen, eller
- Skapa en ZIP-adress för alla dokument tillsammans med mediefilerna och överför den till indatamappen. Det här sättet används vanligtvis för en uppsättning HTML-filer som är länkade till varandra och det finns en innehållsförteckning \(index.html\). Filen index.html innehåller länkar till alla HTML-filer i uppsättningen.

Oavsett om du överför alla filer individuellt eller paketerat i en ZIP-fil skapas en 1:1-mappning mellan HTML-filerna och de resulterande DITA-filerna. Det betyder i stort sett att det finns en .dita-fil skapad för varje .html-fil i indatamappen.

Följande punkter måste beaktas när du överför dokument i en ZIP-fil:

- Alla ämnen som refereras ska placeras i ZIP-filen.

- Alla refererade mediefiler ska refereras inom ämnesfilerna med hjälp av den relativa länken.

- Skapa en index.html-fil och lägg till länkar till de ämnen som du vill lägga till i innehållsförteckningen. Den här index.html-filen används för att skapa DITA-mappningsfilen. I filen index.html kan du även skapa kapslade avsnitt som i följande kodexempel:

  ```
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Observera att varje `ul`-tagg måste ha attributet `class` inställt på `book`. På samma sätt måste varje `class`-taggs `li` anges till `topicref`.

- Om du använder infogade format konverterar du de infogade formaten till CSS-baserade formatklasser i XHTML-filen. Använd sedan stilattributsmappning för att konvertera dessa klassbaserade stilar till DITA `outputclass`-attribut i den konverterade DITA-filen.

  När du genererar utdata från HTML eller AEM för platsen från dessa DITA-filer kan attributen `outputclass` användas för att tillämpa formatklass på den genererade HTML eller AEM platsen för att matcha HTML-källinnehållet.


Förutom att tänka på när du skapar ZIP-filen måste XHTML-dokumentet också vara välstrukturerat. Dokumentet ska t.ex. ha en *rubrik* följt av *Rubrik 1*, *Rubrik 2* och så vidare. Varje rubrik ska ha lite innehåll. Om dokumentet inte är välstrukturerat kanske migreringsprocessen inte fungerar som förväntat.

Så här konverterar du ditt befintliga XHTML-dokument till ett DITA-avsnitt:

1. Använd Package Manager för att hämta filen /libs/fmdita/config/h2d\_io.xml.

1. Anpassa den hämtade h2d\_io.xml-filen.

1. Lägg till filen på följande plats i din Cloud Manager Git-databas:

   /apps/fmdita/config/h2d\_io.xml

   Filen `h2d_io.xml` innehåller följande konfigurerbara parametrar:

   - I elementet `inputDir` anger du platsen för indatamappen där XHTML-källdokumenten är tillgängliga. Om dina XHTML-dokument till exempel lagras i en mapp med namnet `xhtmltodita` i mappen `projects` anger du platsen som: `/content/dam/projects/xhtmltodita/`

   - Ange platsen för utdatamappen eller behåll standardplatsen för utdata i elementet `outputDir`. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - Ange om en ny version av det konverterade DITA-avsnittet ska skapas \(`true`\) eller inte \(`false`\) för elementet `createRev`.

1. Kör Cloud Manager pipeline för att distribuera den uppdaterade konfigurationen.

1. När du har konfigurerat de obligatoriska parametrarna i filen `w2d_io.xml` loggar du in AEM och öppnar Assets-gränssnittet.

1. *\(Valfritt\)* Du kan även lägga till relaterade länkavsnitt i de konverterade dokumenten. Gör så här för att aktivera den här funktionen:

   >[!NOTE]
   >
   > Som standard skapas inte avsnittet med relaterade länkar i de konverterade dokumenten.

   1. Använd Package Manager för att hämta /libs/fmdita/html2dita/h2d.xsl.

   2. Sök efter följande parameter:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Ange värdet för ovanstående parameter till `true()`.

   4. Genomför den uppdaterade filen på följande plats i Cloud Manager Git-databasen:

      /libs/fmdita/html2dita/

   5. Kör Cloud Manager pipeline för att distribuera den uppdaterade konfigurationen.

1. Navigera till indatamappens plats \(`xhtmltodita`\).

1. Överför XHTML-källdokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


Med `<config> </config>`-blocket kan du definiera ett eller flera block med konfigurationer för konvertering. Konverteringsarbetsflödet körs och det slutliga resultatet i form av ett DITA-avsnitt sparas på den plats som anges i `outputDir`-elementet.

## Migrera ostrukturerade FrameMaker {#id1949B050VUI}

Med AEM Guides kan du konvertera dina befintliga ostrukturerade FrameMaker- \(`.fm` och `.book`\)-dokument till DITA-dokument. Det första steget är att skapa formatkopplingar med FrameMaker och spara inställningarna i en .sts-fil. Om du sedan använder anpassad DITA kan du mappa dina anpassade element med källelementsformaten i FrameMakerna `ditaElems.xml`. Om du till exempel har skapat ett anpassat element med namnet `impnote` som hanterar alla viktiga anteckningar, kan du definiera det anpassade elementet i filen `ditaElems.xml`. När det här anpassade elementet har definierats genererar AEM Guides inget fel vid konvertering av FrameMaker-dokument som innehåller `impnote`-element.

Om du vill ange ytterligare attribut med ditt anpassade eller giltiga DITA-element kan du definiera dessa i style2attrMap.xml-filen. Du kan till exempel ange attributet `type` med värdet `important` som ska skickas vidare med elementet `impnote`. Den här extra informationen kan anges i filen style2attrMap.xml.

Förutom att ange

Så här konverterar du ostrukturerade FrameMaker till DITA-format:

1. Skapa formatkopplingar i FrameMaker och spara inställningarna i en .sts-fil.

1. Använd Package Manager för att hämta /libs/fmdita/config/ditaElems.xml.

1. Om du har anpassade DITA-element definierar du de i filen `ditaElems.xml` som finns på följande plats:

   `/libs/fmdita/config/ditaElems.xml`

1. Skapa en kopia av filen ditaElements.xml på följande plats i Cloud Manager Git-databasen:

   `/apps/fmdita/config/ditaElems.xml`

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/ditaElems.xml`

   Filen `ditaElems.xml` innehåller en enda konfigurerbar parameter:

   - I parametern `elem` anger du namnet på det anpassade element som du vill använda i dina konverterade DITA-dokument. Det här elementet skickas vidare på samma sätt som i de genererade DITA-dokumenten.

1. Om du vill ange ytterligare attribut definierar du de i filen `style2attrMap.xml` som finns på följande plats:

   `/libs/fmdita/config/style2attrMap.xml`

1. Skapa en överläggsnod av mappen `config` i noden `apps`.

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/style2attrMap.xml`

   Filen `style2attrMap.xml` innehåller följande konfigurerbara parametrar:

   - I parametern `fmStyle` anger du det källformat som används i det FrameMaker-dokument som du vill mappa.

   - I elementet `ditaAttr` anger du det DITA-attribut som du vill mappa med källformatet.

   - Ange värdet för det mappade attributet i elementet `ditaVal`. Om du inte har något värde kan du lämna den här posten tom.

1. Spara filen `style2attrMap.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `style2attrMap.xml` loggar du in AEM och öppnar Assets-gränssnittet.

1. Navigera till och klicka på det FrameMaker-dokument som du vill konvertera.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj DITA-utdataformat och konfigurera de parametrar som krävs.

   >[!NOTE]
   >
   > Du måste använda samma inställningsfil \(.sts\) som du skapade i FrameMaker. Ange också inställningsnamn och målsökväg.

1. Klicka på ikonen **Generera** för att starta genereringsprocessen för utdata.


Med `<attrMap> </attrMap>`-blocket kan du definiera ett eller flera block med konfigurationer för konvertering. Beroende på innehållet kan du ha en .dita-fil och en .ditamap-fil som konverterade filer.

## Migrera andra strukturerade dokument {#id1949B0590YK}

Med AEM Guides kan du konvertera befintliga strukturerade dokument till giltiga DITA-dokument. Du måste ange mapplatser för in- och utdata, platsen för omvandlingsfilen, det tillägg som slutresultatet sparas med och om en ny version av dokumentet krävs eller inte.

Så här konverterar du dina befintliga strukturerade dokument till DITA-format:

1. Använd Package Manager för att hämta /libs/fmdita/config/XSLConfig.xml.

1. Skapa en kopia av XSLConfig.xml-filen på följande plats i Cloud Manager Git-databasen:

   `/apps/fmdita/config/XSLConfig.xml`

   Filen `XSLConfig.xml` innehåller följande konfigurerbara parametrar:

   - I elementet `inputDir` anger du platsen för indatamappen där dina strukturerade källdokument är tillgängliga. Om dina strukturerade dokument till exempel lagras i en mapp med namnet `xsltodita` i mappen `projects` anger du platsen som: `/content/dam/projects/xsltodita/`

   - Ange platsen för utdatamappen eller behåll standardplatsen för utdata i elementet `outputDir`. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - Ange platsen för mappen där XSL-omvandlingsfilerna lagras i elementet `xslFolder`.

   - I elementet ``xslPath`` anger du platsen för den primära XSL-filen som används för att initiera konverteringsprocessen.

   - I elementet ``outputExt`` anger du filtilläggen för den slutliga utdatafilen som skapas från transformeringsströmmen.

   - Ange om en ny version av det konverterade DITA-avsnittet ska skapas \(`true`\) eller inte \(`false`\) för elementet `createRev`.

1. Spara filen `XSLConfig.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `XSLConfig.xml` loggar du in AEM och öppnar Assets-gränssnittet.

1. Navigera till indatamappens plats \(`xsltodita`\).

1. Överför de källstrukturerade dokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


Med `<config> </config>`-blocket kan du definiera ett eller flera block med konfigurationer för konvertering. Konverteringsarbetsflödet körs och det slutliga resultatet i form av ett DITA-avsnitt sparas på den plats som anges i `outputDir`-elementet.

**Överordnat ämne:**&#x200B;[&#x200B; Migrera befintligt innehåll](migrate-content.md)
