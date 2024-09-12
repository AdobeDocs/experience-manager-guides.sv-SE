---
title: Java-baserade API:er för konverteringsarbetsflöde
description: Läs mer om Java-baserade API:er för konverteringsarbetsflöde
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Java-baserade API:er för konverteringsarbetsflöde {#id175UB30E05Z}

>[!NOTE]
>
> Du kan använda Java-baserade API:er som finns i Experience Manager Guides för att skapa anpassade plugin-program och utöka färdiga arbetsflöden. Den här artikeln arkiveras i november 2024.
> Visa [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) för den senaste och detaljerade dokumentationen om hur du använder det Java-baserade API:t.




Med följande Java-baserade API:er kan du konvertera HTML- och Word-dokument till DITA-format. Dessa API:er är tillgängliga i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

**Paketinformation**:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.conversion**

- Klassinformation:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  Klassen **ConversionUtils** innehåller metoder för konvertering av HTML- och Word-dokument till DITA-format.


## Konvertera HTML-dokument

Metoden `convertHtmlToDita` konverterar HTML-dokument till DITA-format.

**Syntax**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. |
| `inputFile` | Sträng | Absolut sökväg för HTML-källfilerna i AEM. |
| `destPath` | Sträng | Absolut sökväg för målplatsen där de konverterade DITA-filerna ska sparas. |
| `createRev` | Boolean | Ange om en revision av filerna skapas \( `true`\) på det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna. |

**Undantag**:
Utlöser `RepositoryException` .

## Konvertera Word-dokument

Metoden ``convertWordToDita`` konverterar Word-dokument till DITA-format.

**Syntax**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. |
| `inputFile` | Sträng | Absolut sökväg för Word-källfilerna i AEM. |
| `destPath` | Sträng | Absolut sökväg för målplatsen där de konverterade DITA-filerna ska sparas. |
| `style2tagMap` | Sträng | Absolut sökväg till den formatmappningsfil som ska användas för konvertering. |
| `createRev` | Boolean | Ange om en revision av filerna skapas \( `true`\) på det angivna målet eller inte \( `false`\). Detta gäller endast när målplatsen innehåller en befintlig version av de konverterade filerna. |

**Undantag**:
Utlöser `RepositoryException` .
