---
title: Java-baserat API för att arbeta med mappprofiler
description: Lär dig mer om det Java-baserade API:t för att arbeta med mappprofiler
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Java-baserat API för att arbeta med mappprofiler {#id175UB30E05Z}

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

  The **`FolderProfileUtils`** -klassen innehåller en metod för att lägga till villkorliga attribut i en mappprofil.


## Lägga till villkorliga attribut i en mappprofil

The ``addAttributeProfiles`` metoden lägger till villkorliga attribut i en mappnivåprofil.

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

**Parametrar**: |Namn|Typ|Beskrivning| |—|—|—| |``attributeNames``|String|En lista med attributnamn.| |``values``|String|En lista med värden för angivna attribut.| |`labels`|Sträng|En lista med etiketter för `attribute`- `value` par. [1](#fntarg_1)| |`profileName`|String|Namnet på mappnivåprofilen som attributen, värdena och etiketterna ska användas på. **Viktigt:** Alla befintliga attribut-values-labels som definieras i profilen skrivs över.| |`session`|javax.jcr.Session|En giltig JCR-session.|

**Returnerar**:
`true` för framgång. Om ett fel uppstår genereras ett undantag.

**Undantag**: Throws ``java.lang.Exception`` i följande scenarier:

- Om API:t inte kunde hämtas `resourceResolverFactory` -objekt. I så fall bör du starta om paketet.
- Om parametrar som skickats till API är ogiltiga.
- Om API:t anropas via obehörig användarsession, till exempel den användare som inte är administratör för den angivna mappprofilen.

[1](#fnsrc_1) The `attributeNames`, `values`och `labels` vid samma index i en matrislista måste motsvara samma post.
