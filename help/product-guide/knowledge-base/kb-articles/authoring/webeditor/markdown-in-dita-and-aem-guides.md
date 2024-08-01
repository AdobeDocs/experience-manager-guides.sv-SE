---
title: Använd kod i DITA AEM Guides
description: Migrera och använda markeringar i DITA AEM Guides
source-git-commit: b4235841798fb12b3d0491e33b4466073ac02ef3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Använd markering i AEM Guides

## Tillgängliga alternativ

Det finns två alternativ för att använda markeringsfiler i AEM Guides:

- Alternativ 1: Importera befintlig markering i AEM Guides och använd den direkt i redigeringskartan för publicering

- Alternativ 2: Konvertera befintliga markeringsfiler till DITA

Här kan du prata om de olika alternativen:

### Alternativ 1: Importera befintlig markering i AEM Guides och använd den direkt i redigeringskartan för publicering

Det är enklare att konfigurera och implementera snabbare. Men AEM Guides har begränsad funktionalitet, t.ex. återanvändbarhet.

Användaren måste lägga till attributet `format="markdown" ` eller `format="mdita"` så att publiceringsmotorer förstår filtypen och publicerar den.

Exempelfil: [Markeringsschema](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![skärmbild för referens](../../assets/authoring/markdown_map.png)


#### Publish till PDF och webb

AEM Guides ger både alternativet Web (HTML5/AEM Site) och PDF (Native-PDF/DITA-OT) för att publicera en dagskarta med Markdown-innehåll

### Alternativ 2: Konvertera markering till DITA-format

Fullt utnyttjande av AEM Guides-funktionalitet som återanvändning av innehåll, villkorsstyrd översättning, baslinje osv. Men det måste göras ett försök att konvertera `.md` till `.dita`-format.

Markeringar till DITA kan konverteras med externa verktyg som Adobe FrameMaker och DITA-OT.


För Adobe FrameMaker, se: [Importera kod](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

För DITA-OT, se: [Markering som indata](https://www.dita-ot.org/dev/topics/markdown-input.html)

Exempelfil har konverterats med Adobe FrameMaker: [Markdown till DITA-exempel](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publish till PDF och webb

När markeringsfilerna konverterats till DITA kan man enkelt publicera utdata i alla format som finns i AEM Guides.

Tillgängliga format i AEM Guides: [Utdataformat](../../../../user-guide/generate-output-understand-presets.md)
