---
title: Anpassa mappning av dataelement med AEM-komponenter
description: Lär dig hur du anpassar Dita-elementmappning med AEM-komponenter
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 1%

---


# Anpassa DITA-elementmappning med AEM-komponenter {#id1679J600HEL}

DITA-element i AEM Guides mappas till motsvarande AEM-komponenter. AEM Guides använder den här mappningen i arbetsflöden som publicering och granskning för att konvertera DITA-element till en motsvarande AEM-komponent. Mappningen definieras i filen `elementmapping.xml`, som du kommer åt med hjälp av pakethanteraren för Cloud Service-installationen och från URL:en `/libs/fmdita/config/elementmapping.xml` i CRXDE Lite-läget för lokal installation.

>[!NOTE]
>
> Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i noden ``libs``. Du måste skapa en övertäckning av noden ``libs`` i noden ``apps`` och endast uppdatera de filer som krävs i noden ``apps``.

Du kan använda de fördefinierade DITA-elementmappningarna eller mappa DITA-element till dina anpassade AEM-komponenter. Om du vill använda dina anpassade AEM-komponenter måste du förstå strukturen för filen `elementmapping.xml`.

## elementmapping.xml-struktur

En översikt på hög nivå av strukturen `elementmapping.xml` förklaras nedan:

1. Alla DITA-element söks först efter en motsvarande komponentmappning baserat på elementnamnet. Till exempel:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   I ovanstående exempel återges alla `substeps` DITA-element med komponenten `dita/components/ditaolist`.

1. Om ett DITA-element inte hittar någon matchning baserat på namnet görs en matchning utifrån `class`. Till exempel:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Om ingen mappning har definierats för elementet `task` i ovanstående exempel mappas elementet `task` till ovanstående komponent eftersom `task` ärvs från komponenten `topic`.

1. När ett element har en motsvarande komponentmappning bestäms vidare bearbetning av dess underordnade element av `type`. Till exempel:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` har följande värden:

   - COMPOSITE: Mappningen av element till komponent *fortsätter även för underordnade element*.

   - STANDALONE: underordnade element för det aktuella elementet har *inte mappats ytterligare*.

   Om elementet `<title>` har några underordnade element mappas de inte till någon annan komponent i ovanstående exempel. Komponenten för elementet `<title>` ansvarar för återgivningen av alla underordnade element i elementet `<title>`.

1. Om det finns flera komponenter som är mappade till ett enskilt DITA-element väljs den bästa matchningen för elementet. För att välja den bästa matchningskomponenten övervägs domän- och strukturexSpecialisering för DITA-element.

   Om det finns DITA-element med domänspecialisering och en komponent mappas för domänspecialisering får den komponenten hög prioritet.

   Om det finns DITA-element med strukturell specialisering och en komponent mappas för strukturell specialisering får den komponenten hög prioritet.

1. Du kan använda `<attributemap>` i elementmappningen för att mappa attributvärden till motsvarande nodegenskaper.
1. `textprop` kan användas för att serialisera textinnehållet i ett DITA-element till en nodegenskap. Dessutom kan den användas flera gånger i en elementtagg för att serialisera textinnehållet på flera platser i den publicerade hierarkin. Du kan också anpassa platsen och namnet för målegenskapen. Till exempel:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   Ovanstående elementmappning anger att textinnehållet i elementet `<title>` kommer att sparas som värdet för en egenskap med namnet `jcr:title` på utdatanoden.

1. `xmlprop` kan användas för serialisering av hela XML för ett givet element till en nodegenskap. Komponenten kan sedan läsa den här nodegenskapen och göra anpassad återgivning. Till exempel:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   Ovanstående elementmappning anger att hela XML-koden för elementet `<svg-container>` kommer att sparas som ett värde för egenskapen `data` på utdatanoden.

1. Det finns en särskild attributmappning som hanterar sökvägsupplösning i utdatagenereringsprocessen. Till exempel:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   För ovanstående `attributemap` mappas attributet `href` i DITA-elementet till en nodegenskap med namnet `fileReference`. Eftersom `ispath` är inställt på `true` löser utdatagenereringsprocessen den här sökvägen och anger den sedan i nodegenskapen `fileReference`.

   Hur den här upplösningen sker bestäms utifrån värdet för attributet `rel` i attributmappningen.

   - Om `rel=source`, löses värdet för `href` med avseende på DITA-källfilen som bearbetas just nu. Värdet för `href` tolkas och placeras i värdet för egenskapen `fileReference`.

   - Om `rel=target` tolkas värdet för `href` med avseende på rotpubliceringsplatsen. Värdet för `href` tolkas och placeras i värdet för egenskapen `fileReference`.

   Om du inte vill att någon förbearbetning eller upplösning ska ske för sökvägsattribut behöver du inte ange attributet `ispath`. Värdet kopieras som det är och komponenten kan utföra den önskade upplösningen.


## DITA-elementschema

Följande är ett exempel på DITA-elementschemat i filen `elementmapping.xml`:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

I följande tabell beskrivs elementen i DITA-elementschemat:

| Element | Beskrivning |
|-------|-----------|
| `<ditaelement>` | Den översta noden för varje mappningselement. |
| `<class>` | Klassattributet för det DITA-målelement som du skriver komponenten för.<br> Klassattributet för DITA-ämnet är till exempel: <br> `- topic/topic` |
| `<componentpath>` | CRXDE-sökvägen för den mappade AEM-komponenten. |
| `<type>` | Möjliga värden:<br> -   **COMPOSITE**: Bearbeta även underordnade element <br> -   **STANDALONE**: Hoppar över bearbetning av underordnade element |
| `<attributeprop>` | Används för att mappa serialiserade DITA-attribut och -värden till AEM-noder som egenskap. Om du till exempel har elementet `<note type="Caution">` och komponenten som är mappad för det här elementet har `<attributeprop>attr_t</ attributeprop>` serialiseras nodens attribut och värde till egenskapen `attr_t` för motsvarande AEM-nod \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Spara `getTextContent()`-utdata till en egenskap som definieras av `propname_t.` <br> **Obs!** Det här är en optimerad egenskap. |
| `<xmlprop>propname_x </xmlprop>` | Spara serialiserad XML för den här noden i egenskap som definierats av `propname_x.<br> `**Obs!** Detta är en optimerad egenskap. |
| `<xpath>` | Om XPath-elementet anges i elementmappningen ska XPath-villkoret också uppfyllas tillsammans med elementnamnet och klassen för att komponentmappningen ska användas. |
| `<target>` | Placera DITA-elementet i crx-databasen på den angivna platsen.<br> Möjliga värden: <br> - **head**: Under huvudnoden <br> - **text**: Under styckenoden |
| `<wrapelement>` | Det HTML-element som innehållet ska radbrytas i. |
| `<wrapclass>` | Elementvärdet för egenskapen `wrapclass.` |
| `<attributemap>` | Behållarnod som innehåller en eller flera `<attribute>`-noder. |
| `<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />` | Mappar DITA-attributen till AEM-egenskaper: <br> -   **`from`**: DITA-attributnamn <br> -   **`to`**: AEM-komponentens egenskapsnamn <br> -   **`ispath`**: Om attributet är ett sökvägsvärde \(till exempel: *image*\) <br> -   **`rel`**: Om sökvägen är källan eller målet <br> **Obs!** Om `attrname` börjar med `%` mappar du `attrname minus '%'` till prop `propname`. |

**Ytterligare information**

- Om du tänker åsidosätta standardelementmappningen rekommenderar vi att du inte gör ändringarna i standardfilen `elementmapping.xml`. Du bör skapa en ny XML-mappningsfil och placera filen på en annan plats, helst i en anpassad programmapp som du skapar.

- I filen `elementmapping.xml` finns det många mappningsposter som refererar till komponenten fmdita/components/dita/wrapper. Wrapper är en generisk komponent som återger relativt enkla DITA-konstruktioner med hjälp av egenskaper på webbplatsnoden för att generera relevanta HTML. Egenskapen `wrapelement` används för att generera omslutande taggar och för att delegera den underordnade återgivningen till motsvarande komponenter. Detta är användbart om du bara vill ha en behållarkomponent. I stället för att skapa en ny komponent som återger en viss behållartagg som `div` eller `p` kan du använda komponenten Wrapper med egenskaperna `wrapelement` och `wrapclass` för att uppnå samma effekt.

- Du bör inte spara stora mängder text i JCR-egenskaper för strängar. Beräkningen av den optimerade egenskapstypen i utdatagenereringen säkerställer att stort textinnehåll inte sparas som strängtyp. Om innehåll som är större än ett visst tröskelvärde behöver sparas, ändras egenskapstypen till binär. Som standard är det här tröskelvärdet konfigurerat till 512 byte, men du kan ändra det i Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) genom att ändra inställningen **Spara som binärt tröskelvärde** .

- Om du tänker åsidosätta en del \(och inte alla\) av elementmappningarna behöver du inte replikera hela `elementmapping.xml`-filen. Du måste skapa en ny XML-mappningsfil och definiera endast de element som du åsidosätter.

- När du har skapat XML-filen på den anpassade platsen uppdaterar du inställningen `Override Element Mapping` i `com.adobe.fmdita.config.ConfigManager`-paketet.


