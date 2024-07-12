---
title: Java-baserat API för att skapa och aktivera paket
description: Läs mer om det Java-baserade API:t för att skapa och aktivera paket
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
source-git-commit: 4ce78061ddb193d3c16241ff32fa87060c9c7bd6
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Java-baserat API för att skapa och aktivera paket {#id175UB30E05Z}

Med följande Java-baserade API kan du skapa och aktivera CRX-paket. Detta API är tillgängligt i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.3**

- Paket: **com.adobe.fmdita.api.crxactivate**

- Klassinformation:

  ```JAVA
  public class CRXActivator
  ```

  Klassen **`CRXActivator`** innehåller en metod för att skapa CRX-paket och replikera det på publiceringsinstansen.


## Skapa och aktivera paket

Metoden `activate` skapar ett CRX-paket på författarinstansen och replikerar det vid behov på publiceringsinstansen. AEM replikeringsparametrar har redan konfigurerats för författarinstansen. Den här metoden skapar CRX-paketet baserat på en lista med regler som tillhandahålls som indataparametrar i en JSON-sträng.
>[!NOTE]
>
> Fel som påträffades under skapande eller aktivering skrivs till `outputstream`.

### Exempel med två parametrar

**Syntax**:


```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

### Exempel med tredje valfria parameter

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream,
  String activationTarget, 
  Session session
) 
throws GuidesApiException
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`json`|String|JSON-sträng som bestämmer vilket CRX-paket som ska skapas. Använd följande format för att skapa JSON-strängen: <br>- `activate`: Är av typen Boolean \(`true`/`false`\). Avgör om det CRX-paket som skapas i författarinstansen replikeras till publiceringsinstansen. <br> - `rules`: Är av typen JSON-matris. En array med JSON-regler som bearbetas sekventiellt för att skapa CRX-paketet. <br> - `rootPath`: Är av typen String. Bassökvägen som nod-/egenskapsfrågorna körs på. Om det inte finns några nod-/egenskapsfrågor inkluderas rotsökvägen och alla noder som finns under rotsökvägen i CRX-paketet. <br> - `nodeQueries`: Är av typen Regex Array. En array med reguljära uttryck som används för att inkludera specifika filer under rotsökvägen. <br> - `propertyQueries`: Är av typen JSON-matris. En array med JSON-objekt med varje JSON-objekt som består av en XPath-fråga som ska köras på rotsökvägen och namnet på en egenskap som finns i varje JCR-nod efter att frågan har körts. Värdet för egenskapen i varje JCR-nod ska vara en sökväg eller en array med sökvägar. Sökvägarna i den här egenskapen läggs till i CRX-paketet.|
|`outputstream`|java.io.OutputStream|Detta används för att skriva resultatet från olika stadier, till exempel frågekörning, filinkludering, skapande av CRX-paket eller aktivering. Alla fel som påträffas under skapande eller aktiveringsprocessen skrivs till `outputstream`. Detta är användbart vid felsökning.|
|`session`|Sträng|En giltig JCR-session med aktiveringsbehörighet.|
|`activationTarget`|String|(*Valfri*) `preview` eller `publish` för Cloud Service och `publish` för lokal programvara <br> - Om parametern innehåller ett ogiltigt värde misslyckas paketaktiveringen för Cloud Service. <br> - Om parametern innehåller ett ogiltigt värde loggas felet för Lokal programvara och publiceringen görs med standardvärdet `publish`. |

**Undantag**:

Aktiverar `java.io.IOException` och `java.io.IllegalArgumentException`


Om du inte definierar den valfria parametern, `activationTarget`, aktiveras den med standardagenten för publicering för både Cloud Service och lokal programvara.


**Exempel**:
I följande exempel visas hur du skapar en JSON-fråga:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

Exempelfrågan för JSON består av följande regler:

- Endast PNG-, JPG- och GIF-bilder under /content/dam/nested path inkluderas i paketet.
- Alla noder under /content/output/sites/archy\_ditamap inkluderas i paketet.
- Sökvägarna som finns i egenskapen `fileReference` för noder under /content/output/sites/archy\_ditamap ingår i paketet.
