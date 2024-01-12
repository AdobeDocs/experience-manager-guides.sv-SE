---
title: REST API:er för konverteringsarbetsflöde
description: Läs mer om REST API:er för konverteringsarbetsflöde
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# REST API:er för konverteringsarbetsflöde {#id175UB30E05Z}

Med följande REST API:er kan du konvertera Word-, HTML- och InDesign-dokument till DITA-format.

## Konvertera Word-dokument

A GET method that converts Word documents to DITA format.

**Begär URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parametrar**: |Namn|Typ|Obligatorisk|Beskrivning| |—|—|—|—| |``operation``|String|Yes|Namnet på den åtgärd som anropas. Värdet för den här parametern är ``word2dita``. <br> **Obs!** Värdet är inte skiftlägeskänsligt. | |`inputFile`|String|Ja|Absolut sökväg för Word-källfilerna i AEM.| |`destPath`|String|Ja|Absolut sökväg till målplatsen där de konverterade DITA-filerna ska sparas.| |`createRev`|Boolean|Ja|Ange om en version av filerna skapas \( `true`\) vid det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna.| |`style2tagMap`|String|Ja|Absolut sökväg till den formatmappningsfil som ska användas för konvertering.|

**Svarsvärden**: Returnerar ett HTTP 200-svar \(Klart\).

## Konvertera HTML-dokument

En GET-metod som konverterar HTML-dokument till DITA-format.

**Begär URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parametrar**: |Namn|Typ|Obligatorisk|Beskrivning| |—|—|—|—| |`operation`|String|Yes|Namnet på den åtgärd som anropas. Värdet för den här parametern är ``html2dita``. <br> **Obs!** Värdet är inte skiftlägeskänsligt.| |`inputFile`|String|Yes|Absolut sökväg för HTML-källfilerna i AEM.| |`destPath`|String|Ja|Absolut sökväg till målplatsen där de konverterade DITA-filerna ska sparas.| |`createRev`|Boolean|Ja|Ange om en version av filerna skapas \( `true`\) vid det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna.|

**Svarsvärden**: Returnerar ett HTTP 200-svar \(Klart\).

## Konvertera InDesign-dokument

En GET-metod som konverterar InDesigner till DITA-format.

**Begär URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parametrar**: |Namn|Typ|Obligatorisk|Beskrivning| |—|—|—|—| |``operation``|String|Yes|Namnet på den åtgärd som anropas. Värdet för den här parametern är ``idml2dita``. <br> **Obs!** Värdet är inte skiftlägeskänsligt.| |`inputFile`|String|Yes|Absolut sökväg för källfilerna i AEM InDesign-databasen.| |`destPath`|String|Ja|Absolut sökväg till målplatsen där de konverterade DITA-filerna ska sparas.| |`createRev`|Boolean|Ja|Ange om en version av filerna skapas \( `true`\) vid det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna.|

**Svarsvärden**: Returnerar ett HTTP 200-svar \(Klart\).
