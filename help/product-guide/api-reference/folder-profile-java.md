---
title: Java-baserat API för att arbeta med mappprofiler
description: Lär dig mer om det Java-baserade API:t för att arbeta med mappprofiler
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Java-baserat API för att arbeta med mappprofiler {#id175UB30E05Z}

>[!NOTE]
>
> Du kan använda Java-baserade API:er som finns i Experience Manager Guides för att skapa anpassade plugin-program och utöka färdiga arbetsflöden. Den här artikeln arkiveras i november 2024.
> Visa [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) för den senaste och detaljerade dokumentationen om hur du använder det Java-baserade API:t.




Med följande Java-baserade API kan du lägga till villkorsstyrda attribut i en mappnivåprofil. Detta API är tillgängligt i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.profiles**

- Klassinformation:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  Klassen **`FolderProfileUtils`** innehåller en metod för att lägga till villkorliga attribut i en mappprofil.


## Lägga till villkorliga attribut i en mappprofil

Metoden ``addAttributeProfiles`` lägger till villkorliga attribut i en mappnivåprofil.

**Syntax**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| ``attributeNames`` | Sträng | En lista med attributnamn. |
| ``values`` | Sträng | En lista med värden för angivna attribut. |
| `labels` | Sträng | En lista med etiketter för paren `attribute`- `value`. [1](#fntarg_1) |
| `profileName` | Sträng | Namnet på den mappnivåprofil som attributen, värdena och etiketterna ska användas på. **Viktigt!** Alla befintliga attribut-value-labels som definierats i profilen skrivs över. |
| `session` | javax.jcr.Session | En giltig JCR-session. |

**Returnerar**:
`true` för att lyckas. Om ett fel uppstår genereras ett undantag.

**Undantag**:
Utlöses ``java.lang.Exception`` i följande scenarier:

- Om API:t inte kunde hämta `resourceResolverFactory`-objektet. I så fall bör du starta om paketet.
- Om parametrar som skickats till API är ogiltiga.
- Om API:t anropas via obehörig användarsession, till exempel den användare som inte är administratör för den angivna mappprofilen.

[1](#fnsrc_1) `attributeNames`, `values` och `labels` vid samma index i en matrislista måste motsvara samma post.
