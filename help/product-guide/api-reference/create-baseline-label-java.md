---
title: Java-baserade API:er som fungerar med baslinje och etiketter
description: Lär dig mer om Java-baserade API:er som fungerar med baslinjer och etiketter
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 0%

---

# Java-baserade API:er som fungerar med baslinje och etiketter {#id175UB30E05Z}

>[!NOTE]
>
> Du kan använda Java-baserade API:er som finns i Experience Manager Guides för att skapa anpassade plugin-program och utöka färdiga arbetsflöden. Den här artikeln arkiveras i november 2024.
> Visa [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) för den senaste och detaljerade dokumentationen om hur du använder det Java-baserade API:t.


Med följande Java-baserade API:er kan du skapa baslinjer och lägga till etiketter i filer i en baslinje. Dessa API:er är tillgängliga i form av ett paket. Du måste inkludera det här paketet i koden för att kunna använda dessa API:er.

Paketinformation:

- Grupp-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.5**

- Paket: **com.adobe.fmdita.api.baselines**

- Klassinformation:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  Klassen **BaselineUtils** innehåller metoder för att skapa baslinjer och tillämpa etiketter på filer i en baslinje.


## Skapa en baslinje

Metoden för att skapa baslinje har två versioner - en för XML Documentation-lösning version 3.5 och en för tidigare versioner än 3.5 \(som innehåller version 3.4, 3.3 och 3.2\). API:t för version 3.5 gör det möjligt att skapa baslinjen med hjälp av en etikett, direkta referenser och indirekta referenser i en mappningsfil.

I den andra versionen av API används datum och tid för att skapa en baslinje. Detta API bevaras för bakåtkompatibilitet med system som använder XML Documentation 3.4, 3.3 eller 3.2.

**Syntax \(för version 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. Användarsessionen måste ha både läs- och skrivbehörighet för DITA-kartan och läsbehörighet för alla referensfiler som ingår i baslinjen. |
| `sourcePath` | Sträng | Absolut sökväg för DITA-mappningsfilen i AEM. |
| `baselineTitle` | Sträng | En unik rubrik för baslinjen. |
| `label` | Sträng | Välj den version av ett ämne som har den angivna etiketten. |
| `directContext` | LinkedHashMap&lt;String, Object\> | De konfigurationer som ligger till grund för valet av det direkt refererade ämnet \(innehåll\) följs den ordning som anges på kartan för att matcha en version. <br> Om det inte går att hitta någon version efter upprepning på alla nycklar för kartan misslyckas skapandet av baslinjen. <br> Om HashMap är tom \(skicka tom och inte null-mappning för standard\) fylls den som standard i som: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Om du vill att baslinjen bara ska välja version av en viss etikett och misslyckas om det inte finns någon sådan version, placerar du `label`-tangenten och den etikett som du vill skapa baslinjen på. |
| `indirectContext` | LinkedHashMap&lt;String, Object\> | De konfigurationer på grundval av vilka det indirekt refererade ämnet \(refererat innehåll\) väljs följs ordningen som anges på kartan för att matcha en version. <br> Om det inte går att hitta någon version efter upprepning på alla nycklar för kartan misslyckas skapandet av baslinjen. <br> Om HashMap är tom \(skicka tom och inte null-mappning för standard\) fylls den som standard i som: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Om du vill att den ska vara den senaste versionen i stället för att hämta en version automatiskt, ersätter du: <br>`indirectContext.put("pickAutomatically", null);` <br> _med:_ <br>`indirectContext.put("latest", true)` |

**Returnerar**:
Baslinjens namn, som är nodnamnet för baslinjen i JCR-databasen. Titeln på den nyskapade baslinjen visas för användaren på sidan Baslinje för DITA-kartan.

**Undantag**:
Returnerar ``ItemExistExceptiom`` om det redan finns en baslinje med samma titel.

**Syntax \(för version 3.4, 3.3 och 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. Användarsessionen måste ha både läs- och skrivbehörighet för DITA-kartan och läsbehörighet för alla referensfiler som ingår i baslinjen. |
| ``sourcePath`` | Sträng | Absolut sökväg för DITA-mappningsfilen i AEM. |
| `baselineTitle` | Sträng | En unik rubrik för baslinjen. |
| `versionDate` | Datum | Baslinjen skapas med de olika versionerna av avsnitten\(som refereras direkt från DITA-kartan\) det här datumet. Ange datumet i formatet `d-MM-yyyy H:mm`. |

**Returnerar**:
Baslinjens namn, som är nodnamnet för baslinjen i JCR-databasen. Titeln på den nyskapade baslinjen visas för användaren på sidan Baslinje för DITA-kartan.

**Undantag**:
Throws ``RepositoryException.``

## Använd etiketter

Metoden ``applyLabel`` använder en eller flera etiketter på filerna i en baslinje.

**Syntax**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. |
| `sourcePath` | Sträng | Absolut sökväg för DITA-mappningsfilen i AEM. |
| ``baselineName`` | Sträng | Namnet på baslinjenoden som etiketten ska tillämpas på. Om du vill hämta namnet på baslinjenoden kan du använda metoden [\#id185NFF0085Z](#id185NFF0085Z) eller kontrollera baslinjenoden för DITA-kartan i CRXDE.<br> **Obs!** Etikett används på filversioner som refereras direkt från kartfilen i baslinjen. |
| `label` | Sträng | En etikett som används på filer i baslinjen. Kontrollera att etiketten inte innehåller följande tecken: &sol; &komma; &kolon; &komma; komma; &lbrack; &komma; &rbrack; &komma; amp; &vert; &komma; &amp; amp;ast; <br> Om du vill ange flera etiketter ska du separera etiketterna med kommatecken, till exempel etikett 1, Etikett2. |

**Undantag**:
Utlöser `RepositoryException` .

## Ta bort etiketter

Metoden ``deleteLabel`` tar bort en eller flera etiketter från filerna i en baslinje.

**Syntax**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parametrar**:

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `session` | javax.jcr.Session | En giltig JCR-session. |
| `sourcePath` | Sträng | Absolut sökväg för DITA-mappningsfilen i AEM. |
| `baselineName` | Sträng | Namnet på baslinjen som etiketten ska tas bort från. <br> **Obs!** Etikett tas bort från den version av filer som är direkt refererade från kartfilen i baslinjen. |
| `label` | Sträng | En etikett som ska tas bort från filer i baslinjen. <br> Om du vill ta bort flera etiketter avgränsar du dem med kommatecken, till exempel Label1, Label2. |

**Returnerar**:
Mappningen med *key:value* pair of `path:deletedlabels` för alla filer i baslinjen.

**Undantag**:
Utlöser ``RepositoryException`, `VersionException`, `Exception`` .
