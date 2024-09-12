---
title: REST API:er för konverteringsarbetsflöde
description: Läs mer om REST API:er för konverteringsarbetsflöde
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---

# REST API:er för konverteringsarbetsflöde {#id175UB30E05Z}

Med följande REST API:er kan du konvertera Word-, HTML- och InDesign-dokument till DITA-format.

## Konvertera Word-dokument

A GET method that converts Word documents to DITA format.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/conversion

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| ``operation`` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är ``word2dita``. <br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `inputFile` | Sträng | Ja | Absolut sökväg för Word-källfilerna i AEM. |
| `destPath` | Sträng | Ja | Absolut sökväg för målplatsen där de konverterade DITA-filerna ska sparas. |
| `createRev` | Boolean | Ja | Ange om en revision av filerna skapas \( `true`\) på det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna. |
| `style2tagMap` | Sträng | Ja | Absolut sökväg till den formatmappningsfil som ska användas för konvertering. |

**Svarsvärden**:
Returnerar ett HTTP 200 \(Slutförd\)-svar.

## Konvertera HTML-dokument

En GET-metod som konverterar HTML-dokument till DITA-format.

**Begär URL**:

http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/conversion

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är ``html2dita``. <br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `inputFile` | Sträng | Ja | Absolut sökväg för HTML-källfilerna i AEM. |
| `destPath` | Sträng | Ja | Absolut sökväg för målplatsen där de konverterade DITA-filerna ska sparas. |
| `createRev` | Boolean | Ja | Ange om en revision av filerna skapas \( `true`\) på det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna. |

**Svarsvärden**:

Returnerar ett HTTP 200 \(Slutförd\)-svar.

## Konvertera InDesign-dokument

En GET-metod som konverterar InDesigner till DITA-format.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/conversion

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| ``operation`` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är ``idml2dita``. <br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `inputFile` | Sträng | Ja | Absolut sökväg för källfilens InDesign i AEM. |
| `destPath` | Sträng | Ja | Absolut sökväg för målplatsen där de konverterade DITA-filerna ska sparas. |
| `createRev` | Boolean | Ja | Ange om en revision av filerna skapas \( `true`\) på det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna. |

**Svarsvärden**:
Returnerar ett HTTP 200 \(Slutförd\)-svar.
