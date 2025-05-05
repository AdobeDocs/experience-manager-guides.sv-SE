---
title: Bilaga
description: Lär dig hur du förbereder InDesigner för konvertering
exl-id: 02da0e61-7a73-4c4c-9bd7-2664d90fa728
feature: InDesign File Conversion
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2851'
ht-degree: 0%

---

# Bilaga {#id195AD0L60Y4}

## Förbered InDesign-filer för konvertering {#id195DBF0045Z}

InDesign ger författarna en mängd funktioner för att skapa attraktiva och komplexa dokument. Det innebär ofta att de olika delarna av ett dokument placeras visuellt på sidan, men att inget försök görs att skapa något flöde mellan dessa textramar. När *läsordningen* för textramarna inte har definierats innehåller IDML-filen artiklar som kanske inte följer någon meningsfull ordning. Slutresultatet blir ett eller flera DITA-avsnitt med stycken, tabeller och bilder i slumpmässig ordning.

Även om det går att redigera DITA-innehåll i en vettig ordning i en DITA-redigerare är det mycket enklare att åtgärda InDesignen innan du skapar IDML-filen. Detta kan du göra utan att ändra utseendet på källdokumentet. Det har också fördelen att göra källdokumentet tillgängligt genom att rätt definiera läsordningen.

***Koppla textramar***

I InDesignen används termen *&#39;threading&#39;* för att länka en bildruta till en annan. Mer information om hur du kopplar textramar finns i avsnittet *[Koppla text](https://helpx.adobe.com/in/indesign/using/threading-text.html)* i InDesignens dokumentation.

***Överlappande bildrutor***

I vissa InDesigner används icke-kopplade överlappande bildrutor av layoutskäl. Det kan vara mycket svårt att sammanfoga det här innehållet i huvudtråden. Det bästa alternativet kan vara att redigera resultatet i DITA-miljön.

***InDesigner***

Varje kopplat innehållsflöde i ett InDesign-dokument kallas *artikel*. För bästa resultat rekommenderar vi att du begränsar antalet artiklar. Det finns dock vissa delar av dokumentet som kanske inte behövs i DITA-utdata. Sidfötter behövs till exempel sällan, men de kan visas mitt i ett avsnitt om de inte hanteras försiktigt.

Det enklaste sättet att exkludera text som inte behövs i dokumentet är att ge den en speciell *stycketagg* som bara används för det oönskade innehållet. I stället för att återanvända ett *\[Allmänt stycke\]* för sidfoten skapar du en dedikerad *sidfot* -tagg. I MapStyle-filen anger du sedan att styckena *Footer* ska tas bort så här:

```XML
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mappning till DITA-dokumenttyper***

Det är viktigt att källdokumentet har minst ett styckeformat eller -element som kan markera början av ett ämne. Det är vanligt att dokument använder *Rubrik1* som namn på rubrikerna på den översta nivån i dokumentet. Du kan sedan skapa en koppling från det formatet till en viss DITA-dokumenttyp. Om dokumentet är välorganiserat och om *Rubrik1* används konstant genomgående får du bra resultat.

***Flera DITA-dokumenttyper***

Om några av styckena *Rubrik1* behöver konverteras till olika DITA-dokumenttyper duplicerar du styckeformatet i InDesignen. Ge dessa format ett enkelt namn som *Rubrik1\_genTask* eller *Rubrik1\_troubleshooting* efter behov. Konfigurera sedan filen mapStyle enligt nedan:

```XML
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Dokument med strukturerad InDesign***

InDesignen har ett löst förhållande till XML. Även om ett dokument kan innehålla en DTD för XML och huvudartikeln kan vara giltig mot DTD-filen, går det också att skapa hybriddokument där en del av innehållet är XML, men inget DTD-dokument inkluderas. Detta är de oönskade fallen vid en lyckad konvertering till DITA. Om ett dokument innehåller XML-delar kan du försöka spara utdata i XML-format och se om resultaten är godtagbara. Annars kommer DITA-innehållet också att innehålla ogiltigt innehåll eller misslyckas helt.

***Tabellformatering***

Konverteringen från tabellformateringsregler för InDesign till motsvarande tabellformatering i DITA är en komplex process. Detta beror på de omfattande formateringsfunktioner som finns i källfilerna jämfört med de grundläggande alternativen i Oasis \(CALS\)-tabellmodellen som används i DITA. Lodrät och vågrät textjustering tillhandahålls och ger liknande resultat, även om Justerad text alltid justeras enligt textriktningen, medan InDesign tillåter Vänsterjusterad och Högerjusterad.

InDesignens hantering av kolumn- och radavgränsare är nu ännu mer användbar än tabellmodellens grundläggande alternativ i Oasis. InDesign har fyra cellkanter - Kantlinjetyp \(heldragen eller mönster\), Kantbredd, Kantfärg, Kantfärg, Kantmellanrumsfärg och Kantmellanrumston. Alla dessa måste mappas nedåt till kantlinjer till höger och nederst i varje cell \(entry element\) där de enda alternativen är 0 eller 1 - dölj kantlinjen eller visa kantlinjen.

Kantlinjering i InDesign kan användas på följande nivåer:

- Tabellformat
- Cellformat
- Lokala åsidosättningar i varje cell

InDesignen till DITA-konverteringsprocessen tillämpar kantlinjalen enligt följande:

- Tabellformat mappas till attributet `colspec/@colsep` för lodräta regler. Vågräta linjer mappas till attributet `row/@rowsep`. I båda fallen skapas inte attributet om kantlinjen inte är definierad.
- Cellformat mappas till attributen `entry/@colsep` och `entry/@rowsep`. Dessa värden åsidosätter alla härledda kanter i tabellformat.
- Med lokala åsidosättningar används formateringen direkt i cellen och tabellformat och cellformat åsidosätts.

***Alternerande mönster***

Med tabellformat för InDesigner kan stapel- och cellinjer följa ett alternerande mönster. Den här funktionen stöds för konvertering, men resultatet blir bara tydligt när en mönstergrupp mappas till reglaget \(1\) och den andra mönstergruppen mappar till att dölja reglaget \(0\).

## Förbered mappningsfilen för InDesign till DITA-migrering {#id194AF0003HT}

För korrekt DITA-konvertering krävs en mappningsfil som matchar innehållet i källdokumentet. För dokument med ostrukturerad InDesign innebär detta att alla tillgängliga styckeformat och teckenformat måste kopplas. För dokument med XML-strukturerad InDesign måste alla element i tillhörande DTD mappas.

Mappningsfilerna för ostrukturerade och strukturerade InDesigner är olika. Detta beror på de mer komplexa bearbetningskrav som ställs för att konvertera ostrukturerat källinnehåll till DITA.

Nedan visas ett exempel på mappningsfilen:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

Kopplingsfilen är en XML-fil med en enkel struktur som visar alla källstyckeformat och teckenformatkoder. Filinnehållet förklaras nedan:

**Formatkoppling**

I elementet `styleMap` kan du ange två valfria attribut - `@map_date` och `@map_version` för att spela in mappningsfilens version.

**Dokumenttyp**

Elementet `doctypes` innehåller en lista med DITA-mappningar och ämnesmappningar som stöds.

**Koppla styckelinjer för dokumenttyp**

Elementet `mapDoctypeParaRule` är obligatoriskt. Det här elementets attribut får inte redigeras eftersom käll-XML:ens rotelement alltid är mappat till DITA-mappningens rotelement `map`.

**Styckelinje för dokumenttyp**

Elementet `doctypeParaRule` är obligatoriskt. Detta ger konverteringsprocessen ett sätt att identifiera början på ett nytt ämne. Normalt används attributet `@style` fristående med attributet `@local` inställt på 0. Om det alltid finns lokala formateringsåsidosättningar i det valda formatet måste du lägga till en regel för varje format plus lokala åsidosättningar. Detta är enkelt att känna igen i den genererade mappningsfilen där det är möjligt att hitta detta eller liknande:

```XML
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

I ovanstående exempel finns två `paraRule`-element för `@style` = &quot;Rubrik1&quot;. Skapa helt enkelt motsvarande `doctypeParaRule`-element med attributet `@mapToDoctype` inställt efter behov.

Attributen som används i `doctypeParaRule` förklaras nedan:

- `@style`: Namnet på ett format i källdokumentet för InDesign.
- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: Namnet på en DITA-ämnestyp från en numrerad lista med alla giltiga `doctypes`.

**Regler för elementomslutning**

Reglerna för elementomslutning definierar hur element i det inkommande dokumentet ska radbrytas eller flyttas till ett fördefinierat element enligt en uppsättning attributvärden.

***`wrap`element***

Detta är ett valfritt element. Elementet `wrap` visar de element som kommer att kapslas eller flyttas. Figursättning används vanligtvis när en serie element måste tilldelas ett gemensamt överordnat element. Flera `li`-element kapslas till exempel i ett `ol`-element. Dessutom kan `wrap` användas för rörliga element som titlar för figurer och tabeller.

Attributen som används i `wrap` förklaras nedan:

- `@element`: Ett plustecken efter ett elementnamn visar att alla intilliggande element med samma namn kommer att kapslas in i elementet som namnges i attributet `@wrapper`.
- `@wrapper`: Radbrytningselementets namn.
- `@context`: Tillhandahåller ett sätt att ytterligare förfina hur ett visst element radbryts. I följande exempel visas ett sätt att mappa en serie med `li` element i antingen en ordnad lista `ol` eller en osorterad lista `ul` enligt `@context`-värdet \(kontexten definieras i `paraRule` -elementet\):

  ```XML
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


I följande exempel visas hur du skapar ett `fig`-element från ett `title`- och ett `image`-element:

- `@elements`: Elementen som anges och avgränsas med kommatecken kapslas in i elementet som namnges i attributet `@wrapper`. På grund av det vanliga sättet att ta med bildtitlar under bilden blir rubriken `title`-elementet omedelbart efter `image`.

  Följande radbrytningsregel:

  ```XML
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konverterar följande mellanliggande XML:

  ```XML
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  I följande giltiga DITA-figurstruktur:

  ```XML
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: Radbrytningselementets namn.
- `@context`: Tillhandahåller ett sätt att ytterligare förfina hur ett givet element radbryts \(kontexten definieras för elementet `paraRule`\).

I följande exempel visas hur du flyttar en `title` till en `table`:

- `@elements`: Elementet `title` som finns antingen omedelbart före eller omedelbart efter en `table` kommer att kapslas i elementet som namnges i attributet `@wrapper`. Ett XPath-predikat kan identifiera positionen för rubrikelementet som `[before]` eller `[after]`.

  Exempel: Följande radbrytningsregel:

  ```XML
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konverterar följande mellanliggande XML:

  ```XML
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  I den här giltiga DITA-figurstrukturen:

  ```XML
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: Radbrytningselementets namn.

- `@context`: Tillhandahåller ett sätt att ytterligare förfina hur ett givet element radbryts \(kontexten definieras för elementet `paraRule`\).


**Styckeformatregler**

`<paragraphStyleRule>`-elementen beskrivs nedan:

***`paraRule`element***

Elementet `paraRule` är obligatoriskt. Detta anger mappningsreglerna för alla styckeformat. I ett styckedokument finns all InDesign i en understruktur till styckeformat, även stycken utan format med namnet `[No paragraph style]`. De här hakparenteserna anger ett inbyggt namn på InDesignen.

>[!NOTE]
>
> Hakparenteserna anger ett inbyggt namn på InDesignen.

Attributen som används i `paraRule` förklaras nedan:

- `@style`: Namnet på ett format i källdokumentet för InDesign.
- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Namnet på ett DITA-målelement.

- `@context`: Det här attributet används för att länka till en specifik **radbrytning**-regel när mer än ett radbrytningsalternativ är tillgängligt. Exempel: `li`-elementet kan kapslas antingen i ett `ol`- eller `ul`-element. Om du vill identifiera de olika listtyperna kan du använda ett specifikt formatnamn eller attributet `@local` som kan visa följande:
   - `local="p[-|-|-|-|-|b|-|-]"` Där `b` i fält 6 anger ett punktlisteobjekt. I det här fallet anger du `@context` till `bullet`.
   - `local="p[-|-|-|-|-|n|-|-]"` Där `n` i fält 6 anger ett numrerat listobjekt. I det här fallet anger du `@context` till `number`.

- `@commentOut`: Det här attributet aktiverar kapsling av målelementet i XML-kommentarer så att informationen inte går förlorad utan kan hanteras manuellt av användaren. Detta är användbart om källinnehållet inte kan tvingas att följa DITA-strukturregler.

- `@refactor`: Det här valfria attributet har två värden:

- `unwrap`: Det matchande elementet tas bort samtidigt som innehållet behålls.

- `drop`: Det matchande elementet och allt dess innehåll tas bort.


**Teckenformatsregler**

`charRule`-elementen beskrivs nedan:

>[!NOTE]
>
> Det kommer inte att finnas någon mappning för det inbyggda teckenformatet `[No character style]` när `local="0"`, eftersom de tas bort under förbearbetningen.

***`charRule`element***

Detta är ett valfritt element.

Detta är mappningsreglerna för alla teckenformat. I ett textdokument finns all InDesign i underordnade element till teckenformat.

Attributen som används i `charRule` förklaras nedan:

- `@style`: Namnet på ett format i källdokumentet för InDesign.
- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Namnet på ett DITA-målelement.
- `@refactor`: Det här valfria attributet har två värden:
   - `unwrap`: Det matchande elementet tas bort samtidigt som innehållet behålls.

   - `drop`: Det matchande elementet och allt dess innehåll tas bort.


**Attributregler**

Det här elementet kan vara underordnat följande elementkontexter:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

Syftet med attributregler är att hantera attributen för de matchade elementen.

Beroende på sammanhanget är följande attribut tillgängliga för elementet `attributeRules`:

- `@createID`: Skapar ett unikt ID för matchande element. Tillåtna värden `true` eller `false`. Finns i alla sammanhang.
- `@copyAll`: Kopierar endast alla attribut från XML-källinnehållet för strukturerade källfiler. Tillåtna värden är `true` eller `false`. Tillgängligt för kontexterna `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` och `elementRule`.


Attributen som används i `attributeRules` förklaras nedan:

>[!NOTE]
>
> Det här elementet kan innehålla flera underordnade element.

- `addNew`: Lägger till ett nytt attribut i det matchade elementet. Tillgängligt för alla kontexter. Den har två attribut:
   - `@name`: Måste vara ett giltigt XML-namn, helst giltigt för DITA-kontexten.
   - `@value`: Kan vara literal text eller ett enkelt XPath-uttryck.
- `copyAtt`: Kopierar ett enskilt attribut till målet, men du kan också ändra namnet på det i processen. Värdet ändras inte. Tillgängligt för kontexterna `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` och `elementRule`. När det här elementet finns antas värdet `@copyAllAtts` vara `false`. Den har två attribut:
   - `@name`: Måste vara namnet på ett attribut som finns i käll-XML-elementet.
   - `@mapTo`: Måste vara ett giltigt XML-namn, helst giltigt för DITA-kontexten.

**Lokala formateringskoder**

I alla slags InDesigner kan det finnas flera hundra olika formatåsidosättningar för styckeformat och teckenformat. De flesta av dessa egenskaper har ingen användbar roll i konverteringsprocessen. Vi har dock identifierat en viktig uppsättning formateringsfunktioner som påverkar dokumentets semantik och som måste påverka konverteringsprocessen.

Attributen `@local` visas som ett särskilt avgränsat format där åtta fält anges tillsammans med ett prefix som visar typen av formateringsåsidosättning. Formateringskodfälten visas nedan:

- Prefixet **p** för lokal åsidosättning av paragrafformat eller **c** för lokal åsidosättning av teckenformat.
- **Teckensnittsformat** som är familjenamnet och egenskaper som ***Fet kondenserad kursiv***.
- **Teckenstorlek** i punkter.
- **Teckenposition** för upphöjd eller nedsänkt text.
- **Under** för understreck.
- **Genomstrykning** för genomstrykning.
- **Visa kod** för att identifiera listtyp som punktlistor eller numrerade - används inte alltid som InDesign.
- **Punktkod** visar alla definierade punkttyper i dokumentet.
- **Nummerkod** visar alla definierade numreringsformat i dokumentet.

Om du använder den här funktionen noggrant kan du spara lokal formatering vilket kan förbättra kvaliteten på en överföring från formaterat innehåll till DITA. Det här exemplet kan tolkas som kursiv, 16 punkter i en punktlista: `p[Italic|16|-|-|-|b|-|-]`.

**Strukturmappning**

Strukturmappningsfilen liknar formatmappningsfilen med en enkel struktur som listar alla källelement och relevanta attributtyper. Två attribut, `@map_date` och `@map_version`, tillhandahålls för inspelning av den version av mappningsfilen som ska användas.

**Dokumenttyp**

Elementet `doctypes` innehåller en lista med DITA-mappningar och ämnesmappningar som stöds.

**Koppla dokumenttypselementregler**

Elementet `mapDoctypeElemRule` är obligatoriskt. Det här elementets attribut får inte redigeras eftersom käll-XML:ens rotelement alltid är mappat till DITA-mappningens rotelement `map`.

**Regler för elementomslutning**

**`elementRules`element** Visar alla element.

**`elementRule`element** Elementet `elementRule` är obligatoriskt. Detta är mappningsreglerna för alla källelement. Ett InDesign-dokument innehåller ostrukturerade formatelement, men dessa ignoreras för strukturerat innehåll om inte ***hybridlägesbearbetningen*** är aktiverad.

Attributen som används i `elementRule` förklaras nedan:

- `@elementName`: Namnet på ett element i källdokumentet för InDesign.

- `@local`: Se [\#id194CG0V005Z](#id194CG0V005Z). \(Endast användbart för hybrid-dokument\).

- `@mapTo`: Namnet på ett DITA-målelement.

- `@refactor`: Det här valfria attributet har två värden:

   - `unwrap`: Det matchande elementet tas bort samtidigt som innehållet behålls.

   - `drop`: Det matchande elementet och allt dess innehåll tas bort.

- `@context`: Det här attributet används för att länka till en specifik radbrytningsregel när mer än ett radbrytningsalternativ är tillgängligt. Exempel: `li`-elementet kan kapslas antingen i ett `ol`- eller `ul`-element.

- `@commentOut`: Det här attributet aktiverar kapsling av målelementet i XML-kommentarer så att informationen inte går förlorad utan kan hanteras manuellt av användaren. Detta är användbart om källinnehållet inte kan tvingas att följa DITA-strukturregler.


## Felsökning av AEM Guides

När du har installerat och konfigurerat AEM Guides kan du felsöka problemen.

## Validera referenser

Du kan köra de angivna skripten för att validera referenserna. Dessa skript kan hjälpa dig att identifiera de brutna referenserna och sedan korrigera eller åtgärda dem.

- `/bin/fmdita/validatebtree?operation=validate` - Rapporterar eventuella brutna innehållsreferenser, men korrigerar dem inte.
- `/bin/fmdita/validatebtree?operation=patch`- visar brutna innehållsreferenser och korrigeringar eller korrigerar dem.

**Validera skript**

Gör så här för att kontrollera referenserna med det valideringsskript som finns i produktpaketet:

1. Kör valideringsskriptet \[`/bin/fmdita/validatebtree?operation=validate`\] för att kontrollera om det finns några nya brutna referenser.
1. Om valideringsskriptet rapporterar fel kan du åtgärda det med hjälp av korrigeringsskriptet.
1. Registrera nedanstående uppgifter och dela dem vid behov med kundens framgångsgrupp:
1. &#x200B;
   - Loggar som skrivs ut med valideringsskript
- Paket med `/content/fmdita/references`
- Övriga obligatoriska uppgifter beroende på scenario som rapporteras

**Lappa skript**

Utför följande steg för att korrigera eventuella brutna referenser med hjälp av det korrigeringsskript som finns i produktpaketet:

1. Kör korrigeringsskriptet `[/bin/fmdita/validatebtree?operation=patch]` för att åtgärda de brutna referenserna. Skriptkörningen tar några minuter och skriver ut loggarna medan den fortsätter. När körningen har slutförts skrivs `Done` ut i slutet.

   **Obs!* Vi rekommenderar att du kopierar och sparar loggarna i referenssyfte.

1. När korrigeringsskriptet har körts kan du utföra följande kontroller:
1. &#x200B;
   - Kontrollera att den nya noden `references_backup_<timestamp>"` har skapats under `/content/fmdita`
- Kontrollera att referenserna har åtgärdats

**Logger**

Du kan också skapa en separat loggare för den här skriptkörningen enligt informationen nedan:

- Lägg till en loggare för klassen `adobe.fmdita.common.BTreeReferenceValidator`
- Ställ in den på `DEBUG`

Den skapade loggfilen registrerar all information som är relaterad till skriptkörning och är användbar om webbläsarens sessionstimeout skulle inträffa medan skriptet utlöses från webbläsaren.
