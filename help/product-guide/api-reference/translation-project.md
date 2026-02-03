---
title: Skapa översättningsprojekt
description: Läs om hur du skapar API-översättningsprojekt
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 41dd3dee5f9d64fb5c58b5b302cc9759e48e3631
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%

---

# Skapa översättningsprojekt

En POST-metod som hjälper dig att skapa ett översättningsprojekt genom att acceptera nödvändig projektinformation.

## Begär URL

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Typ av begäran

POST

## Begär parametrar

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `type` | Sträng | newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject |
| `versionDetails`, `versionSelector` | Sträng | Baslinje, senaste version, versionEfterDatum |
| `language` | Sträng | Kommaseparerade språk &quot;de&quot;, &quot;fr&quot; |
| `map.id` | Sträng | GUID för källmappningen som ska översättas |
| `map.path` | Sträng | Sökväg till den källmappning som ska översättas |
| `referenceType` | Sträng | Indirekt, direkt |
| `fileType` | Sträng | Karta, ämne, övrigt |
| `documentState` | Sträng | kan vara en av listorna som tilldelats av användaren på kartans profil |
| `translationStatus` | Sträng | Osynkroniserad, Synkroniserad, Uppdaterad, Inaktuell, Pågående, Kopia saknas, INGEN, INGEN |

>[!NOTE]
>
>Du kan antingen använda `map.id` eller `map.path` när du skapar ett översättningsprojekt.

## Exempel på begäran

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]
```

## Svarsvärden

```JSON
{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}
```

**Svarskoder**

- 200 lyckades
- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 internt serverfel

## Exempelbegäranden

### Lägg till i befintligt projekt

```json
{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

### Lägg till i befintligt projekt med baslinje

```json
{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

## Status för skapande av översättningsprojekt

Ett GET-API som spårar översättningsstatusen för ett nyligen skapat översättningsprojekt.

## Begär URL

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Typ av begäran

GET

## Begär parametrar

| Namn | Typ | Beskrivning |
|----|----|-----------|
| `path` | Sträng | Sökväg till projektet |
| `languageStatusMap` | Sträng | Returnerar slutförandestatus för varje begärt språk: Pågår, Slutförd, Misslyckad, Överhoppad |


## Exempel på begäran

```json
{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}
```



