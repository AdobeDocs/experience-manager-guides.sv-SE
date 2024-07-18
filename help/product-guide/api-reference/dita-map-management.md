---
title: REST API för arbete med DITA-kartor
description: Läs mer om REST API för DITA-kartor
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
source-git-commit: d0196ffbe5a779445d627871c2940f7eea40f1ce
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# REST API för arbete med DITA-kartor {#id175UB30E05Z}

Med följande REST API kan du arbeta med DITA-kartor i AEM Guides.

## Ladda ned DITA-karta med beroenden

En GET-metod som laddar ned en DITA-karta med alla dess beroenden, t.ex. refererade ämnen, delkartor, bilder och DTD:er som används på kartan och i avsnitten.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/exportditamap

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `ditamap` | Sträng | Ja | Absolut sökväg för DITA-mappningsfilen i AEM. |
| `baseline` | Sträng | Nej | Titeln på baslinjen som används för att hämta versionsinnehållet. <br> **Obs!** Värdet är skiftlägeskänsligt. |

**Svarsvärden**:
En ZIP-fil vars innehåll skrivs till svarets utdataström.

## Initiera export för DITA-karta med beroenden

En metod som initierar en export av en DITA-POST med alla dess beroenden, t.ex. refererade ämnen, underkartor, bilder och DTD:er, som används på kartan och i avsnitten. Status kan efterfrågas senare och URL:en för nedladdningen kan hämtas när den är klar.

**Begär URL**:
http:*//&lt;aem-guides-server\>: &lt;portnummer\>/bin/dxml/async-export*

**Parametrar**:
|Namn|Typ|Obligatorisk|Beskrivning|
|—|—|—|—|
|`ditamap`|String|Yes|Absolut sökväg för DITA-mappningsfilen i AEM.|
|`baseline`|Sträng|Nej|Titeln på baslinjen som används för att hämta versionsinnehållet. <br> **Obs!** Värdet är skiftlägeskänsligt.|
|`flatFS`|Boolean|Nej|\(Valfritt\) Om värdet är true returneras en platt filstruktur i ZIP-filen. Om din DITA-karta till exempel refererar till innehåll i flera mappar, hämtas alla refererade filer till en enda mapp. Om det finns filer med samma namn byter dessa namn namn genom att lägga till ett numeriskt suffix. Alla referenser \(i DITA-scheman och -ämnen\) hanteras automatiskt när de uppdateras baserat på den nya platsen för filer i den platta mappstrukturen. Om värdet är false bevaras mappstrukturen som den är i ZIP-filen. Om DITA-kartan refererar till filer från flera platser skapas även alla dessa platser i ZIP-filen. När du återställer ZIP-filen skapas den exakta mappstrukturen på målplatsen. <br> Standardvärdet för den här parametern är false.|

**Svarsvärden**:
|Element|Beskrivning|
|—|—|
|`status`|Returstatus för åtgärden som utfördes. Möjliga alternativ är: STARTAD, MISSLYCKAD, INPROGRESS, LYCKAD, SAKNAD, BORTTAGEN|
|`jobId`|Jobbets unika ID. Kan användas senare för att fråga efter status.|
|errorMessage|Felmeddelandet för jobbet vid fel \(om statusen MISSLYCKAS, SAKNAS eller DELETED\).|
|`filePath`|Filsökvägen för ZIP. Den visas endast när jobbet har slutförts och statusen har LYCKATS. Detta kan användas för att hämta ZIP-filen.|

## Läsa DITA-mappningsstatus för export

En GET-metod som hämtar exportstatus för en DITA-karta med alla dess beroenden. Den kan avfrågas med ett intervall om statusen är STARTED eller INPROGRESS tills den är klar \(lyckades eller med ett fel\).

**Begär URL**:
http:*//&lt;aem-guides-server\>: &lt;portnummer\>/bin/dxml/async-export*

**Parametrar**
|Namn|Typ|Obligatorisk|Beskrivning|
|—|—|—|—|
|`jobId`|Sträng|Ja|Jobb-ID som hämtades när exportjobbet initierades.|

**Svarsvärden**:
|Element|Beskrivning|
|—|—|
|`status`|Exportjobbets status. Möjliga alternativ är: STARTAD, MISSLYCKAD, INPROGRESS, LYCKAD, SAKNAD, BORTTAGEN|
|`jobId`|Jobbets unika ID. Kan användas senare för att fråga efter status.|
|`errorMessage`|Felmeddelandet för jobbet vid fel \(om statusen MISSLYCKAS, SAKNAS eller DELETED\).|
|`filePath`|Filsökvägen för ZIP. Den visas endast när jobbet har slutförts och statusen har LYCKATS. Detta kan användas för att hämta ZIP-filen.|
