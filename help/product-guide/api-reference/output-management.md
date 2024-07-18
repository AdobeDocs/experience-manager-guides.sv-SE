---
title: REST API:er för utdatahantering
description: Läs mer om REST API:er för utdatahantering
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 3279640b32041cafe262457c62b8bd34e55f9ccf
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# REST API:er för utdatahantering {#id175UB30E05Z}

Följande REST-API:er är tillgängliga för hantering av utdata i AEM Guides.

## Hämta alla förinställningar för en DITA-karta {#get-output-presets-dita-map}

En POST-metod som hämtar alla förinställningar som konfigurerats för en DITA-karta.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `:operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är `getalloutputs`.<br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `sourcePath` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen. |

**Svarsvärden**:
Returnerar en array med förinställda JSON-utdataobjekt, där varje objekt innehåller följande element:

| Element | Beskrivning |
|-------|-----------|
| `outputName` | Namn på förinställningen. Utdatanamn är unika i DITA-kartans omfång som de definieras i. |
| `outputType` | Typ av utdata som genereras med den här förinställningen, till exempel AEM Site, PDF, EPUB eller annat. De tillgängliga alternativen är:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   ANPASSAD |
| `outputTitle` | Ett beskrivande namn för inställningarna för förinställningen för utdata. Det här används för att definiera värdet för egenskapen Inställningsnamn för utdatafärgen. |
| `ditaValPathList` | En array med DITAVAL-filsökvägar som ska användas för att generera önskade utdata. |
| `targetPath` | Sökväg där utdata publiceras eller lagras. |
| `siteName` | *\(För AEM platsutdata\)* Namnet på den AEM platsen. |
| `templatePath` | *\(För AEM platsutdata\)* Sökväg till mallnoden som ska användas för att generera önskade utdata. |
| `searchScope` | Ange omfattningen för sökåtgärden. Värdet för den här parametern måste anges till `local`. |
| `generateTOC` | *\(För AEM platsutdata\)* Ange om en innehållsförteckning genereras \(true\) eller inte \(false\). |
| `generateBreadcrumbs` | *\(För AEM platsutdata\)* Ange om breadcrumbs ska genereras \(true\) eller inte \(false\). |
| `overwriteStrategy` | *\(För AEM platsutdata\)* Ange om filer på målet ska skrivas över \(true\) eller inte \(false\). |
| `pdfGenerator` | Ange vilken PDF-genereringsmotor som ska användas. Möjliga värden är:<br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> Elementet `DitaValPath` stöds inte längre.

## Skapa förinställning för utdata

En POST-metod som skapar en ny förinställning för en DITA-karta.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `:operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är ``createoutput``.<br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `sourcePath` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen. |
| `outputTitle` | Sträng | Ja | Ett beskrivande namn för inställningarna för förinställningen för utdata. Detta används för att definiera värdet för inställningsnamnsegenskapen för utdatafärgen.<br> **Obs!** När en ny förinställning skapas, kör back-end-systemet ett unikt namn för utdataförinställningen från den angivna titeln. |
| `outputType` | Sträng | Ja | Typ av utdata som genereras med den här förinställningen, till exempel AEM Site, PDF, EPUB eller annat. De tillgängliga alternativen är:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   ANPASSAD |

**Svarsvärden**:

| Element | Beskrivning |
|-------|-----------|
| `outputName` | Ett unikt namn för den nyligen skapade förinställningen. Namnet härleds från värdet för parametern `outputTitle`. |

## Spara förinställning för utdata

En POST-metod som sparar ändringar som gjorts i en förinställning.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `:operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är ``saveoutput``.<br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `sourcePath` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen. |
| `outputObj` | Sträng | Ja | Ett JSON-objekt som innehåller egenskaper för den förinställning som uppdateras. Egenskapen `outputObj.outputName` innehåller namnet på den förinställning som ska uppdateras. JSON-objektets format finns i tabellen **Svarsvärden** i [Hämta alla förinställningar för en DITA-karta](#get-output-presets-dita-map). |

**Svarsvärden**:
Returnerar ett HTTP 200 \(Slutförd\)-svar.

## Hämta en specifik förinställning

En metod som hämtar en befintlig förinställning för POST.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `:operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är `getoutput`. <br>**Obs!** Värdet är inte skiftlägeskänsligt. |
| `sourcePath` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen. |
| `outputName` | Sträng | Ja | Namnet på den förinställning som informationen ska hämtas för. |

**Svarsvärden**:

| Element | Beskrivning |
|-------|-----------|
| `outputName` | Namn på förinställningen. Utdatanamn är unika i DITA-kartans omfång som de definieras i. |
| `outputType` | Typ av utdata som genereras med den här förinställningen, till exempel AEM Site, PDF, EPUB eller annat. De tillgängliga alternativen är:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   ANPASSAD <br> |
| `outputTitle` | Ett beskrivande namn för inställningarna för förinställningen för utdata. Det här används för att definiera värdet för egenskapen Inställningsnamn för utdatafärgen. |
| `ditaValPathList` | En array med DITAVAL-filsökvägar som ska användas för att generera önskade utdata. |
| `targetPath` | Sökväg där utdata publiceras eller lagras. |
| `siteName` | \(För AEM platsutdata\) Namnet på den AEM platsen. |
| `siteTitle` | \(För AEM platsutdata\) Namnet på den AEM webbplatsen. |
| `templatePath` | \(För AEM platsutdata\) Sökväg till mallnoden som ska användas för att generera önskat utvärde. |
| `searchScope` | Ange omfattningen för sökåtgärden. Värdet för den här parametern måste anges till `local`. |
| `generateTOC` | \(För AEM platsutdata\) Ange om en innehållsförteckning genereras \(true\) eller inte \(false\). |
| `generateBreadcrumbs` | \(För AEM platsutdata\) Ange om vägbeskrivningar ska genereras \(true\) eller inte \(false\). |
| `overwriteFiles` | \(För AEM platsutdata\) Ange om filer på målet ska skrivas över \(true\) eller inte \(false\). |
| `pdfGenerator` | Ange vilken PDF-genereringsmotor som ska användas. Möjliga värden är:<br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> Elementet `DitaValPath` stöds inte längre.

## Generera utdata

En GET-metod som genererar utdata med en eller flera förinställningar.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är `GENERATEOUTPUT`.<br> **Obs!** Värdet är skiftlägeskänsligt. |
| `source` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen. |
| `outputName` | Sträng | Ja | Namnet på den/de förinställningar som ska användas för att generera utdata. Du kan ange flera förinställningar med en pipe \(&quot;\|&quot;\)-avgränsare, till exempel `aemsite|pdfoutput`. |

**Svarsvärden**:
Returnerar ett HTTP 200 \(Slutförd\)-svar.

## Generera inkrementella utdata

En GET-metod som genererar inkrementella utdata för en AEM webbplats med en eller flera utdatainställningar.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är `INCREMENTALPUBLISH`. <br>**Obs!** Värdet är skiftlägeskänsligt. |
| `contentPath` | JSON | Ja | Absolut sökväg för DITA-mappningsfilen och ämnesfilerna tillsammans med namnet på förinställningarna för utdata. Använd följande exempel som byggsten: |

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- Attributet `ditamap` har den absoluta sökvägen för den DITA-karta som används för att generera utdata.
- Attributet `topics` innehåller en matris med ämnen som har uppdaterats och måste publiceras på nytt.
- Attributet `fullMaps` innehåller sökvägen till mappningsfilerna \(t.ex. kapslade underpunkter\) som behövs tillsammans med avsnitten för att generera inkrementella utdata.
- Attributet `maps` innehåller sökvägen till mappningsfilerna \(för att matcha nyckelutrymmesreferenser\) som extraheras på disken utan ämnen.
- Attributet `outputs` tar en array med förinställningsnamn för utdata som används för att generera utdata.

**Svarsvärden**:
Returnerar ett HTTP 200 \(Slutförd\)-svar.

## Ta bort förinställning för utdata

En POST som tar bort en förinställning.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/publishlistener

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `:operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är `deleteoutput`.<br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `sourcePath` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen. |
| `outputName` | Sträng | Ja | Namnet på den förinställning som ska tas bort. |

**Svarsvärden**:
Returnerar ett HTTP 200 \(Slutförd\)-svar.
