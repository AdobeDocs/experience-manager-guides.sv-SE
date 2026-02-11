---
title: Migrera icke-DITA-innehåll
description: Lär dig hur du migrerar icke-DITA-innehåll
exl-id: 4597d1be-5426-4eba-8490-e42d0e565427
feature: Migration
role: Admin
level: Experienced
source-git-commit: 2c20191ba998ad7da98587f1832e1fe8499d023c
workflow-type: tm+mt
source-wordcount: '2392'
ht-degree: 0%

---

# Migrera icke-DITA-innehåll {#id181AH0R02HT}

I det här avsnittet får du hjälp med att migrera icke-DITA-dokument till DITA-format. AEM Guides erbjuder migrering från följande källor:

- [Microsoft Word](#id1949B040Z5Z)

- [InDesign dokument](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Ostrukturerade FrameMaker-dokument](#id1949B050VUI)

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

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/config/w2d_io.xml`

1. Skapa en överläggsnod av mappen `config` i noden `apps`.

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/w2d_io.xml`

   Filen `w2d_io.xml` innehåller följande konfigurerbara parametrar:

   - I elementet `inputDir` anger du platsen för indatamappen där dina Word-källdokument är tillgängliga. Om dina Word-dokument till exempel lagras i en mapp med namnet `wordtodita` i mappen `projects` anger du platsen som: `/content/dam/projects/wordtodita/`

   - I elementet `outputDir` anger du platsen för utdatamappen eller behåller standardplatsen för utdata för att spara det konverterade DITA-dokumentet. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - Ange om en ny version av det konverterade DITA-avsnittet ska skapas \(`createRev`\) eller inte \(`true`\) för elementet `false`.

   - I elementet `s2tMap` anger du platsen för den mappningsfil som innehåller mappningar för Word-dokumentformat till DITA-element. Standardmappningen sparas i filen som finns på:

     ```XML
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Mer information om strukturen för filen `word-builtin-styles-style2tagmap.xml` och hur du kan anpassa den finns i [Koppla format till tagg](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) i *DITA för utgivare*.

   - I elementet props2Propagate anger du de egenskaper som ska överföras till DITA-kartan. Den här egenskapen krävs för att skicka standardmetadata som dc:title,dc:subject,dam:keywords,dam:category från dokumentmetadata till konverterade DITA-resurser.

1. Spara filen `w2d_io.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `w2d_io.xml` loggar du in på AEM och öppnar användargränssnittet i Assets.

1. Navigera till indatamappens plats \(`wordtodita`\).

1. Överför Word-källdokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


Med blocket `config` `/config` kan du definiera ett eller flera block med konfigurationer för konvertering. Konverteringsarbetsflödet körs och det slutliga resultatet i form av ett DITA-avsnitt sparas på den plats som anges i `outputDir`-elementet.

## Migrera Adobe InDesign-dokument {#id195AD0B0K5Z}

Med AEM Guides kan du konvertera InDesign-dokument. På samma sätt som i FrameMaker kan du i InDesign även skapa ostrukturerade och strukturerade dokument. I det ostrukturerade dokumentet används stycke- och teckenformat för att formatera innehåll. I det strukturerade dokumentet används element och deras motsvarande attribut.

Vid konverteringen måste stycke- och teckenformatsformaten mappas till relevanta DITA-element. På samma sätt kommer mappningsfilen att innehålla en-till-en-mappning av InDesign-element och -attribut med DITA-element och -attribut i strukturerade dokument.

Konverteringsprocessen omfattar följande åtgärder i serverdelen:

- Filen *InDesign Markup Language* \(IDML\) är packad i en arbetskatalog.
- Filen designmap.xml läses för att hitta de enskilda InDesign-artiklarna.
- Alla artiklar sammanfogas till en enda XML-instans, tomma artiklar ignoreras.
- Alla inbäddade bilder exporteras.
- Förkonvertering av standardstrukturer som tabeller och grafik till DITA-format.
- Koppling format eller struktur till slutliga utdata baserat på mappningsfilen.
- Skapa och validera enskilda DITA-ämnen och DITA-kartfiler.
- Borttagning av temporära filer.

Konverteringsprocessen kräver dessutom [Förbered InDesign-filer för konvertering](appendix.md#id195DBF0045Z) och [Förbered mappningsfilen för InDesign till DITA-migrering](appendix.md#id194AF0003HT). Sedan måste du följa den angivna proceduren för att köra konverteringsprocessen.

Så här konverterar du dina InDesign-dokument till ämnesdokument i DITA:

1. Logga in på AEM och öppna CRXDE Lite-läget.

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
   <entry key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

Konfigurera följande parametrar i filen `idml2dita_io.xml`:

- I elementet `inputDir` anger du platsen för indatamappen där dina InDesign-källdokument är tillgängliga. Om dina InDesign-dokument till exempel lagras i en mapp med namnet `indesigntodita` i mappen `projects` anger du platsen som: `/content/dam/idmlfiles/indesigntodita/`

- I elementet `outputDir` anger du platsen för utdatamappen eller behåller standardplatsen för utdata för att spara det konverterade DITA-dokumentet. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

- I elementet `mapStyle` anger du platsen för mappningsfilen som innehåller mappningar för InDesign-dokumentformat till DITA-element. Standardmappningen sparas i filen som finns på:

```XML
    /stmap.adobeidml.xml
```

>[!NOTE]
>
> Mer information om strukturen för filen `stmap.adobeidml.xml` och hur du kan anpassa den finns i avsnittet [Förbered mappningsfilen för InDesign till DITA-migrering](appendix.md#id194AF0003HT) i *Bilaga*.

1. Spara filen `idml2dita_io.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `idml2dita_io.xml` loggar du in på AEM och öppnar användargränssnittet i Assets.

1. Navigera till indatamappens plats \(`indesigntodita`\).

1. Överför InDesign-källdokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


## Migrera XHTML-dokument {#id1949B04L0Y4}

Med AEM Guides kan du konvertera befintliga XHTML-dokument till ämnesdokument i DITA. Du måste ange mapplatser för in- och utdata tillsammans med andra parametrar och dokumenten konverteras till DITA-format. Du kan konvertera dina strukturerade HTML-dokument på två sätt:

- Överför alla dokument till indatamappen, eller
- Skapa en ZIP-adress för alla dokument tillsammans med mediefilerna och överför den till indatamappen. Detta används vanligtvis för en uppsättning HTML-filer som är länkade till varandra och det finns en innehållsförteckning \(index.html\). Filen index.html innehåller länkar till alla HTML-filer i uppsättningen.

Oavsett om du överför alla filer individuellt eller paketerat i en ZIP-fil skapas en 1:1-mappning mellan HTML-filerna och de resulterande DITA-filerna. Det betyder i stort sett att det finns en .dita-fil skapad för varje .html-fil i indatamappen.

Följande punkter måste beaktas när du överför dokument i en ZIP-fil:

- Alla ämnen som refereras ska placeras i ZIP-filen.

- Alla refererade mediefiler ska refereras inom ämnesfilerna med hjälp av den relativa länken.

- Skapa en index.html-fil och lägg till länkar till de ämnen som du vill lägga till i innehållsförteckningen. Den här index.html-filen används för att skapa DITA-mappningsfilen. I filen index.html kan du även skapa kapslade avsnitt som i följande kodexempel:

  ```XML
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

  Observera att varje `ul`-tagg måste ha attributet `class` inställt på `book`. På samma sätt måste varje `li`-taggs `class` anges till `topicref`.

- Om du använder infogade format konverterar du de infogade formaten till CSS-baserade formatklasser i XHTML-filen. Använd sedan stilattributsmappning för att konvertera dessa klassbaserade stilar till DITA `outputclass`-attribut i den konverterade DITA-filen.

  När du genererar utdata från HTML eller AEM Site från dessa DITA-filer kan attributen `outputclass` användas för att tillämpa formatklass på genererad HTML- eller AEM Site för att matcha HTML-källinnehållet.


Förutom att tänka på när du skapar ZIP-filen måste XHTML-dokumentet också vara välstrukturerat. Dokumentet ska t.ex. ha en *rubrik* följt av *Rubrik 1*, *Rubrik 2* och så vidare. Varje rubrik ska ha lite innehåll. Om dokumentet inte är välstrukturerat kanske migreringsprocessen inte fungerar som förväntat.

Så här konverterar du ditt befintliga XHTML-dokument till ett DITA-avsnitt:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/config/h2d_io.xml`

1. Skapa en överläggsnod av mappen `config` i noden `apps`.

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/h2d_io.xml`

   Filen `h2d_io.xml` innehåller följande konfigurerbara parametrar:

   - I elementet `inputDir` anger du platsen för indatamappen där XHTML-källdokumenten är tillgängliga. Om dina XHTML-dokument till exempel lagras i en mapp med namnet `xhtmltodita` i mappen `projects` anger du platsen som: `/content/dam/projects/xhtmltodita/`

   - Ange platsen för utdatamappen eller behåll standardplatsen för utdata i elementet `outputDir`. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - Ange om en ny version av det konverterade DITA-avsnittet ska skapas \(`createRev`\) eller inte \(`true`\) för elementet `false`.

1. Spara filen `h2d_io.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `h2d_io.xml` loggar du in på AEM och öppnar användargränssnittet i Assets.

1. *\(Valfritt\)* Du kan även lägga till relaterade länkavsnitt i de konverterade dokumenten. Gör så här för att aktivera den här funktionen:

   >[!NOTE]
   >
   > Som standard skapas inte avsnittet med relaterade länkar i de konverterade dokumenten.

   1. Navigera till h2d.xsl-filen på följande plats:

      /libs/fmdita/html2dita/

   2. Sök efter följande parameter:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Ange värdet för ovanstående parameter till `true()`.
   4. Spara och stäng filen.
1. Navigera till indatamappens plats \(`xhtmltodita`\).

1. Överför XHTML-källdokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


Med `<config> </config>`-blocket kan du definiera ett eller flera block med konfigurationer för konvertering. Konverteringsarbetsflödet körs och det slutliga resultatet i form av ett DITA-avsnitt sparas på den plats som anges i `outputDir`-elementet.

## Migrera ostrukturerade FrameMaker-dokument {#id1949B050VUI}

Om du vill konvertera ostrukturerat Adobe FrameMaker-innehåll (.fm och .book) till strukturerat DITA kan du använda FrameMaker konverteringstabellmekanism. Processen fokuserar på att utvärdera befintligt innehåll, använda en mallbaserad metod och mappa FrameMaker-format till DITA via konverteringstabeller. Mer information finns i [Migrerar teknisk dokumentation från ostrukturerad till DITA i Adobe FrameMaker](https://migrate-from-unstructured-to-dita-step-by-step-guide.meetus.adobeevents.com/).

Efter konverteringen kan det strukturerade innehållet migreras till AEM Guides.  Mer information finns i [Överför befintligt DITA-innehåll](./migrate-content-upload-existing-dita-content.md).

<!-- Deprecated information -
 //The first step is to create style mappings using FrameMaker and save those settings in a .sts file. Next, if you are using custom DITA, then you can map your custom elements with the source FrameMaker formats in the `ditaElems.xml` file. For example, if you have created a custom element named `impnote` to handle all important notes, then you can define this custom element in the `ditaElems.xml` file. Once this custom element is defined, AEM Guides would not raise an error while converting FrameMaker document containing `impnote` element.

Also, If you want to specify some additional attributes with your custom or valid DITA element, you can define those in the style2attrMap.xml file. For example, you can specify the `type` attribute with the value of `important` to be passed on with the `impnote` element. This additional information can be specified in the style2attrMap.xml file.

In addition to specifying

To convert your existing unstructured FrameMaker documents into DITA format, perform the following steps:

1.  Create style mappings in FrameMaker and save those settings in a .sts file.

1.  Log into AEM and open the CRXDE Lite mode.

1.  If you have custom DITA elements, define those in the `ditaElems.xml` file available at the following location:

    `/libs/fmdita/config/ditaElems.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/ditaElems.xml`

    The `ditaElems.xml` file contains a single configurable parameter:

    -   In the `elem` parameter, specify the name of the custom element that you want to use in your converted DITA documents. This element would be passed on as is in the generated DITA documents.

1.  If you want to specify additional attributes, define those in the `style2attrMap.xml` file available at the following location:

    `/libs/fmdita/config/style2attrMap.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/style2attrMap.xml`

    The `style2attrMap.xml` file contains the following configurable parameters:

    -   In the `fmStyle` parameter, specify the source format used in the FrameMaker document that you want to map.

    -   In the`ditaAttr` element, specify the DITA attribute that you want to map with the source format.

    -   In the `ditaVal` element, specify the value for the mapped attribute. If you don't have any value, you can leave this entry blank.

1.  Save the `style2attrMap.xml` file.

1. After configuring the required parameters in the `style2attrMap.xml` file, log into AEM and open the Assets UI.

1. Navigate to and click on the FrameMaker document that you want to convert.

    The DITA map console appears showing the list of Output Presets available to generate output.

1. Select DITA output format and configure the required parameters.

    >[!NOTE]
    >
    > You must use the same settings file \(.sts\) that you created in FrameMaker. Also, specify the Settings Name and Destination Path.

1. Click the **Generate** icon to start the output generation process.


Using the `<attrMap> </attrMap>` block, you can define one or multiple blocks of configurations for conversion. Depending on the content, you could have a .dita file and a .ditamap file as the converted files.

-->

## Migrera andra strukturerade dokument {#id1949B0590YK}

Med AEM Guides kan du konvertera befintliga strukturerade dokument till giltiga DITA-dokument. Du måste ange mapplatser för in- och utdata, platsen för omvandlingsfilen, det tillägg som slutresultatet sparas med och om en ny version av dokumentet krävs eller inte.

Så här konverterar du dina befintliga strukturerade dokument till DITA-format:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till standardkonfigurationsfilen som finns på följande plats:

   `/libs/fmdita/config/XSLConfig.xml`

1. Skapa en överläggsnod av mappen `config` i noden `apps`.

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/XSLConfig.xml`

   Filen `XSLConfig.xml` innehåller följande konfigurerbara parametrar:

   - I elementet `inputDir` anger du platsen för indatamappen där dina strukturerade källdokument är tillgängliga. Om dina strukturerade dokument till exempel lagras i en mapp med namnet `xsltodita` i mappen `projects` anger du platsen som: `/content/dam/projects/xsltodita/`

   - Ange platsen för utdatamappen eller behåll standardplatsen för utdata i elementet `outputDir`. Om den angivna utdatamappen inte finns på DAM skapar konverteringsarbetsflödet utdatamappen.

   - Ange platsen för mappen där XSL-omvandlingsfilerna lagras i elementet `xslFolder`.

   - I elementet ``xslPath`` anger du platsen för den primära XSL-filen som används för att initiera konverteringsprocessen.

   - I elementet ``outputExt`` anger du filtilläggen för den slutliga utdatafilen som skapas från transformeringsströmmen.

   - Ange om en ny version av det konverterade DITA-avsnittet ska skapas \(`createRev`\) eller inte \(`true`\) för elementet `false`.

1. Spara filen `XSLConfig.xml`.

1. När du har konfigurerat de obligatoriska parametrarna i filen `XSLConfig.xml` loggar du in på AEM och öppnar användargränssnittet i Assets.

1. Navigera till indatamappens plats \(`xsltodita`\).

1. Överför de källstrukturerade dokumenten till den här mappen. Mer information om hur du överför innehåll på DAM finns i [Överför befintligt DITA-innehåll](migrate-content-upload-existing-dita-content.md#).


Med `<config> </config>`-blocket kan du definiera ett eller flera block med konfigurationer för konvertering. Konverteringsarbetsflödet körs och det slutliga resultatet i form av ett DITA-avsnitt sparas på den plats som anges i `outputDir`-elementet.

**Överordnat ämne:**[ Migrera befintligt innehåll](migrate-content.md)
