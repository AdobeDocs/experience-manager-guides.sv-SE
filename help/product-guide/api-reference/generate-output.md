---
title: Java-baserat API som fungerar med utdatagenerering
description: Lär dig mer om det Java-baserade API:t för att arbeta med generering av utdata
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: ee4eb829ebe215315b05cd1f376e934c02a73b1e
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# Java-baserat API som fungerar med utdatagenerering {#id175UB30E05Z}

>[!NOTE]
>
> Du kan använda Java-baserade API:er som finns i Experience Manager Guides för att skapa anpassade plugin-program och utöka färdiga arbetsflöden. Den här artikeln arkiveras i november 2024.
> Visa [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) för den senaste och detaljerade dokumentationen om hur du använder det Java-baserade API:t.

Med följande Java-baserade API kan du generera utdata för en DITA-karta. Detta API är tillgängligt i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.4**

- Paket: ****com.adobe.fmdita.api.maps****

- Klassinformation:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  Klassen **`PublishUtils`** innehåller en metod för att generera utdata för en eller flera förinställningar.


## Generera utdata

Metoden ``generateOutput`` genererar utdata för en DITA-mappningsfil med de angivna förinställningarna.

**Syntax**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. |
| ``sourcePath`` | Sträng | Sökväg \(i AEM databas\) till den DITA-mappningsfil som utdata ska skapas för. |
| ``outputName`` | Sträng | Namnet på den/de förinställningar som ska användas för att generera utdata. Du kan ange flera förinställningar med en pipe \(&quot;\|&quot;\)-avgränsare, till exempel `aemsite\|pdfoutput`. |

**Undantag**:
Utlöser ``javax.jcr.RepositoryException``, `java.io.IOException` och `java.lang.Exception`.
