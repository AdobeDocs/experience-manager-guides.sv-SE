---
title: Komponentmappning för AEM Sites
description: Lär dig hur du gör komponentmappning för AEM Sites
feature: Installation
role: Admin
level: Experienced
exl-id: 376aea7a-7850-44d4-a620-6b1a798a0801
source-git-commit: beb1ca15fdfb0e7ea30e6e685ac67a2a398cc064
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Komponentmappning för AEM Sites

Artikeln handlar om de olika aspekterna av komponentmappning för AEM-platser (med hjälp av sammansatt komponentmappning).

## Regler för komponentmappning

Använd en JSON-matris med regler (din `componentmapping.json`) för att konvertera HTML till komponenter. Se till att reglerna är så enkla, uttryckliga och specifika som möjligt.

### Ange HTML-elementet och dess klass som mål

- Skriv HTML-taggnamnet i `name`.
- Inkludera den CSS-klass som används för det elementet i `class`, om det finns en klass.
Exempel:

  ```html
  <div class ="sample-class">
  <p> Sample html element </p>
  </div>
  ```

  ```json
  {
  "name": "div",
  "class": "sample-class",
  "resourceType": "guides-components/components/table",
  "attributeMap": []
  }
  ```

När du definierar elementen ovan ska du se till följande:

- `name` kan vara en kommaavgränsad lista (t.ex. `"h1, h2"`).
- `class` måste finnas i elementet (alla angivna klasser måste matcha).
- `resourceType` anger att du tänker använda komponenten `table`. Paketet `guides-components` är ett OOTB som tillhandahålls av guider. Du kan även använda andra komponentpaket, till exempel `core/wcm/`, efter behov.

### Använd attributeMap för att spara egenskaper på JCR-noden

Lägg till poster i `attributeMap` för att ange egenskaper på utdatanoden. Varje post skapar `attrs[to] = value`.
Vanliga mönster:

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

Nedan visas ett exempel för HTML till JSON för ett bildelement.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalisera banor via ett dedikerat inlägg

Om du vill normalisera (göra absoluta) värden, deklarerar du vilka attributnycklar som ska normaliseras med:

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Se till att ta hand om följande viktiga punkter:

- Skriv in listan med egenskapsnamn som du vill normalisera i `value` (t.ex. `["text"]` eller `["href", "src"]`).
- Alla värden som hittas under egenskapsnamnen normaliseras när den slutliga komponenten skapas.


### Extrahera HTML-värden innan de delas upp i komponenter

Använd `from` för att ange hur ett värde från elementet ska läsas innan dokumentet delas upp i separata komponenter:

- `"textContent"`: oformaterad text för elementet
- `"outerHTML"`: elementet och dess inre markering
- `"innerHTML"`: endast elementets inre markering
- Alla andra strängar: behandlas som ett attributnamn (t.ex. `"src"`, `"href"`)


Exempel:

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Minimalt exempel från början till slut i componentMapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "weretail/components/content/heroimage",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Definiera det element och den klass som ska användas som mål, använd `attributeMap` för att ange nodegenskaper, lägg till en `path-attributes`-post för att normalisera sökvägar och välj höger `from` för de värden som du vill extrahera. `heroimage` som används ovan är en komponent på en `we-retail`-plats.

**Obs!**: Det är viktigt att diskutera standardtexten och identifiera de element som den används för.

## Skapa en anpassad komponent

Lär dig hur du skapar en anpassad tabellkomponent som visar bilder i cellerna. Detta tillvägagångssätt garanterar en ren, återanvändbar design för dynamiskt innehåll. Det handlar om vad du ska bygga, varför det är effektivt, de viktigaste förutsättningarna, högnivådesign med mera.

### Vad du ska bygga

En anpassad tabellkomponent som accepterar tabellinnehåll från HTML och ersätter alla `<img>` i den med utdata från AEM Core Image-komponenten. På så sätt kan du återanvända funktionerna i Core Image (responsiva bilder, alternativ-hantering, tillgänglighet) samtidigt som du har full kontroll över tabellkoden.
På det här sättet kan du skapa andra anpassade komponenter för din AEM-webbplats (med hjälp av sammansatt komponentmappning).

### Varför detta tillvägagångssätt

- **Återanvänd**: Utnyttja kärnbildens mogna beteende i stället för att implementera om den.
- **Konsekvens**: Bilder i tabellen fungerar på samma sätt som bilder på andra platser på webbplatsen.
- **Serversidan**: Bilder återges på servern för prestanda, SEO och tillgänglighet.

### Förutsättningar

- AEM SDK körs och projektet är utcheckat.
- Kärnkomponenter som är installerade på din AEM-instans.
- Maven finns att bygga och driftsätta.

### Designa på hög nivå

- Författare tillhandahåller HTML för tabellen i komponentdialogrutan.
- En Sling Model tolkar det som HTML, hittar `<img>`-taggar och för varje bild anropar en tjänst som återger Core Image-komponentens serversida.
- Modellen byter ut originalet `<img>` mot den hämtade Core Image HTML och skickar den färdiga HTML till HTML för utdata.

Tabellen skrivs ut en gång och innehåller redan Core Image-kod. Ingen DOM-manipulering på klientsidan behövs.

### Mappstruktur och nyckelfiler (i denna rapport)

- Komponent-HTML och klientlibs: `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
   - `table.html` (HTML-återgivning)
   - `_cq_editConfig.xml` (uppdatera avlyssnare)
   - `clientlibs/` med `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Sling-modell: `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Bildrenderingstjänst: `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Implementeringssteg

**Definiera tabellkomponenten (komponentnod)**

Skapa komponenten under `apps/guides-components/components/table`. Om du inte redan har en, lägg till en `.content.xml` som nedan för att registrera den på sidopanelen.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Anger för AEM att detta är en komponent som författare kan lägga till på sidor.

**Återge med HTML och inkludera format**

Använd en Sling-modell och skapa den bearbetade HTML-filen. Inkludera din klientlib-kategori för CSS/JS.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

Modellen returnerar en fullständig HTML med en kärnbild som redan renderats, så HTML skriver bara ut den.

**Lägg till segmenteringsmodellen för att bearbeta HTML och återge kärnbilden**

Modellen läser dialogrutefält, tolkar tabellen HTML, hittar varje `<img>` och ersätter den med Core Image HTML via en tjänst.

Nedan följer några viktiga kunskaper om `TableModel`:

- Läser `tableHtml`, `enableResponsive`, `tableStyle` från resursegenskaper.
- Använder Jsoup för att tolka och redigera HTML på ett säkert sätt.
- Anropar `ImageComponentRenderer` att återge Core Image och hämta HTML.
- CSS-klasser och format från originalet `<img>` bevaras.
- Normaliserar DAM-sökvägar (tar bort `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

Detta centraliserar logiken på servern och återanvänder Core Image-funktionen.

**Återge kärnbild via en tjänst (SSI)**

`ImageComponentRenderer` återger kärnavbildningskomponenten och hämtar utdata. Den

- kapslar in en resurs som tvingar `core/wcm/components/image/v2/image`.
- använder `RequestDispatcher#include` för att återge den.
- hämtar svaret som en sträng.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

Detta gör att du kan **släppa in**-kärnbilden var du än behöver den, inte bara som en underordnad komponent.

**Klientbibliotek**

Skapa ett clientlib för små format eller framtida JS. HTL:n ovan läser in kategorin `guides-components.table`.

```java
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
  
```

Detta gör att formaten/skripten är modulära och kan identifieras.

**Dialogrutefält (författarindata)**

Lägg till en dialogruta med minst följande egenskaper:

- **Tabell HTML**: `./tableHtml` (textområde); tabellens HTML.
- **Aktivera responsiv**: `./enableResponsive` (kryssruta); växlar en responsiv wrapper-klass.
- **Tabellformat**: `./tableStyle` (välj); använder en formatmodifieringsklass.

Dessa kartor :1 till Sling-modellens egenskaper och styr återgivningen.

**Tillåt komponenten i mallar**

Redigera Layoutbehållarprincipen > Tillåtna komponenter > Aktivera tabellkomponenten under **Stödlinjer - anpassad** i mallredigeraren.

Författarna kan inte lägga till komponenter förrän de tillåts enligt principerna.

## Designtips

- Klistra in giltig HTML för tabellen. Modellen sanerar och justerar bild-URL:er.
- Använd DAM-resurssökvägar för bilder. Återgivningar normaliseras till den ursprungliga resurssökvägen.
- Ange alt-text i HTML när det är möjligt, annars markeras bilderna som dekorativa.

## Begränsningar

- Tjänsten framtvingar Core Image v2. Uppdatera `IMAGE_RESOURCE_TYPE` om du vill byta version.
- För syntetisk återgivning ersätter modellen de `.coreimg.`-URL:er som genereras av Core Image med direkta DAM-sökvägar och tar bort `srcset` för att undvika brutna URL:er.
- All återgivning sker en gång på servern. JavaScript är valfritt.

## Snabb referens (implementering)

- HTML: `ui.apps/.../components/table/table.html`
- Klientlibs: `ui.apps/.../components/table/clientlibs/`
- Modell: `core/.../models/TableModel.java`
- Tjänst: `core/.../services/ImageComponentRenderer.java`

I det här mönstret visas hur du komponerar en anpassad komponent med en Core Component-server, vilket gör att du kan behålla koden medan Core-logiken återanvänds.
