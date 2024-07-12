---
title: Java-baserat API som fungerar med utdatagenerering
description: Lär dig mer om det Java-baserade API:t för att arbeta med generering av utdata
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Java-baserat API som fungerar med utdatagenerering {#id175UB30E05Z}

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
|Namn|Typ|Beskrivning|
|—|—|—|
|`session`|javax.jcr.Session|En giltig JCR-session.|
|``sourcePath``|Sträng|Sökväg \(i den AEM databasen\) för den DITA-mappningsfil som utdata ska skapas för.|
|``outputName``|Sträng|Namnet på den förinställning som ska användas för att generera utdata. Du kan ange flera förinställningar med en pipe \(&quot;\|&quot;\)-avgränsare, till exempel `aemsite\|pdfoutput`.|

**Undantag**:
Utlöser ``javax.jcr.RepositoryException``, `java.io.IOException` och `java.lang.Exception`.
