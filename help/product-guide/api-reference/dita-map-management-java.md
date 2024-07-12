---
title: Java-baserade API:er för DITA-kartor
description: Lär dig mer om Java-baserade API:er för DITA-kartor
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 0%

---

# Java-baserade API:er för DITA-kartor {#id175UB30E05Z}

Med följande Java-baserade API:er kan du arbeta med DITA-kartor i AEM Guides. Dessa API:er är tillgängliga i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.maps**

- Klassinformation:

  ```JAVA
  public class MapUtilities extends Object
  ```

  Klassen MapUtilities innehåller metoder för att hämta metadatainformation från en DITA-mappningsfil.


## Ladda ned DITA-karta med beroenden

Metoden `zipMapWithDependents` skapar en ZIP-fil som innehåller en DITA-karta tillsammans med alla dess beroenden, till exempel refererade ämnen, undermappar, bilder och DTD:er. ZIP-filen för DITA-kartan skapas utifrån en given baslinje.

Du kan också antingen behålla samma struktur, \(överordnade och underordnade mappar\) eller skapa en platt filstruktur i en enda mapp för alla beroende filer.

>[!IMPORTANT]
>
> API:t genererar ett undantag och kan inte skapa en ZIP-fil om någon av de beroende filerna saknas.

**Syntax**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`session`|javax.jcr.Session|En giltig JCR-session.|
|`sourcePath`|Sträng|Sökväg \(i den AEM databasen\) för den DITA-mappningsfil som ska hämtas.|
|`outputStream`|java.io.OutputStream|Strömmen som ZIP ska skrivas till.|
|`baseline`|String|Titeln på baslinjen som används för att hämta versionsinnehållet. <br> **Obs!** Värdet är skiftlägeskänsligt.|
|flatFS|Boolean|\(Valfritt\) Om värdet är true returneras en platt filstruktur i ZIP-filen. Om din DITA-karta till exempel refererar till innehåll i flera mappar, hämtas alla refererade filer till en enda mapp. Om det finns filer med samma namn byter dessa namn namn genom att lägga till ett numeriskt suffix. Alla referenser \(i DITA-scheman och -ämnen\) hanteras automatiskt när de uppdateras baserat på den nya platsen för filer i den platta mappstrukturen. Om värdet är false bevaras mappstrukturen som den är i ZIP-filen. Om DITA-kartan refererar till filer från flera platser skapas även alla dessa platser i ZIP-filen. När du återställer ZIP-filen skapas den exakta mappstrukturen på målplatsen. <br> Standardvärdet för den här parametern är false.|

**Returnerar**:
Innehållet i ZIP skrivs till `outputStream` .

**Undantag**:
Aktiverar ``javax.jcr.RepositoryException``, `java.io.IOException` .

## Hämta DITA-karta med beroenden \(asynkront\)

Du kan också hämta DITA-kartan med underordnade i asynkront läge. Detta är mer användbart för större DITA-kartor.

Metoden `zipMapWithDependents` skapar en ZIP-fil som innehåller en DITA-karta tillsammans med alla dess beroenden, till exempel refererade ämnen, undermappar, bilder och DTD:er. ZIP-filen för DITA-kartan skapas utifrån en given baslinje.

Du kan också antingen behålla samma struktur, \(överordnade och underordnade mappar\) eller skapa en platt filstruktur i en enda mapp för alla beroende filer.

>[!NOTE]
>
> Den här noden tas bort automatiskt efter en tid baserat på konfigurationen output.history.purgetime, om den är definierad, eller 5 dagar som standard.

**Syntax**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`session`|javax.jcr.Session|En giltig JCR-session.|
|`sourcePath`|Sträng|Sökväg \(i den AEM databasen\) för den DITA-mappningsfil som ska hämtas.|
|`baseline`|String|Titeln på baslinjen som används för att hämta versionsinnehållet. <br> **Obs!** Värdet är skiftlägeskänsligt.|
|flatFS|Boolean|\(Valfritt\) Om värdet är true returneras en platt filstruktur i ZIP-filen. Om din DITA-karta till exempel refererar till innehåll i flera mappar, hämtas alla refererade filer till en enda mapp. Om det finns filer med samma namn byter dessa namn namn genom att lägga till ett numeriskt suffix. Alla referenser \(i DITA-scheman och -ämnen\) hanteras automatiskt när de uppdateras baserat på den nya platsen för filer i den platta mappstrukturen. Om värdet är false bevaras mappstrukturen som den är i ZIP-filen. Om DITA-kartan refererar till filer från flera platser skapas även alla dessa platser i ZIP-filen. När du återställer ZIP-filen skapas den exakta mappstrukturen på målplatsen.<br> Standardvärdet för den här parametern är false.|

**Returnerar**:
ZIP-filens nod kapslas i klassen `CompletableFuture` . Användaren kan fortsätta att hantera den asynkront och kan använda metoden `.get()` i framtiden för att blockera tråden när noden behövs. Det returnerade värdet kan också sluta med ett fel och det kan hanteras med metoden `.exceptionally()`.

## Hämta en lista med baslinjer

Metoden ``getBaselineList`` hämtar en lista över alla baslinjer som finns för en given DITA-karta.

**Syntax**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`session`|javax.jcr.Session|En giltig JCR-session.|
|`sourcePath`|Sträng|Sökväg \(i den AEM databasen\) för den DITA-mappningsfil som baslinjeinformationen ska hämtas för.|

**Returnerar**:
En lista med `HashMap` -objekt. Varje `HashMap`-objekt representerar en baslinje och innehåller baslinjens namn och rubrik.

**Undantag**:
Utlöser ``javax.jcr.RepositoryException`` .

## Hämta en lista med villkorliga förinställningar

Metoden ``getConditionalPresetList`` hämtar en lista med alla villkorliga förinställningar som finns för en given DITA-karta.

**Syntax**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`session`|javax.jcr.Session|En giltig JCR-session.|
|`sourcePath`|Sträng|Sökväg \(i den AEM databasen\) till den DITA-mappningsfil som informationen om villkorsförinställningen ska hämtas för.|

**Returnerar**:
En lista med `HashMap` -objekt. Varje `HashMap`-objekt representerar en villkorlig förinställning och innehåller namnet och titeln på den villkorliga förinställningen.

**Undantag**:
Utlöser ``javax.jcr.RepositoryException`` .

## Hämta DITAVAL-filinformation för en villkorsstyrd förinställning

Metoden ``getDitavalFromConditionalPreset`` hämtar sökvägen till DITAVAL-filen som motsvarar en villkorlig förinställning för en given DITA-karta.

**Syntax**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`session`|javax.jcr.Session|En giltig JCR-session.|
|`sourcePath`|Sträng|Sökväg \(i den AEM databasen\) för DITA-mappningsfilen som DITAVAL-filen ska hämtas för.|
|`cpName`|Sträng|Namnet på den villkorliga förinställningen i DITA-kartan som DITAVAL-filen ska hämtas för.|

**Returnerar**:
Sökvägen till DITAVAL-filen som motsvarar den villkorliga förinställning som definierats i DITA-mappningsfilen.

## Hämta alla beroenden för en nod

Metoden ``getAllDependencies`` returnerar alla beroenden för en angiven nod.

**Syntax**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parametrar**:
|Namn|Typ|Beskrivning|
|—|—|—|
|`rootNode`|javax.jcr.Node|Rotnoden som alla beroenden ska hämtas för.|

**Returnerar**:
En nodlista som innehåller alla beroenden för rotnoden.
