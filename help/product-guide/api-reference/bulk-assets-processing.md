---
title: API för att starta massbearbetning av resurser
description: Läs mer om API för att starta massbearbetning av resurser
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: e2eca63a5dd56e358aeea047b37f4b0f88dc720b
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# API för att starta massbearbetning av resurser

En POST-metod som initierar massbearbetning av resurser för en angiven sökväg. Detta API stöder både JCR-baserad och databasbaserad bearbetning av resurser. Det startar ett asynkront jobb som bearbetar alla resurser under den angivna sökvägen och dess undersökvägar. Vid start returnerar API:t ett unikt processingID, som kan användas för att spåra jobbstatusen.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Begär parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `path` | Sträng | Ja | Absolut sökväg till den mapp eller resurs i AEM-databasen som ska bearbetas. |
| `excludedPaths` | Sträng | Nej | Lista över sökvägar som ska uteslutas från bearbetning |
| `type` | Sträng | Ja | Typ av bearbetning som ska utföras. Exempel: ASSET_PROCESSING. |

**Exempel på begäran**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING"
}
```

**Svarsvärden**

processingId att avfråga för att få status för asynkront jobb.

```JSON
{
  "processingId": "akjhdfalkj1132"
}
```

**Svarskoder**

- 200 lyckades
- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 internt serverfel

## Kontrollera jobbstatus

En GET-metod som hämtar aktuell status för ett resurshanteringsjobb som har startats tidigare.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Begär parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `processingId` | Sträng | Ja | Unikt ID för det jobb vars status efterfrågas. |

**Exempel på svar**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}
```

**Svarskoder**

- 200 lyckades
- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 internt serverfel

## Visa jobbloggar

En GET-metod som hämtar loggar för ett givet jobb-ID. Detta API hämtar loggarna för resursbearbetningsjobbet. Bearbetnings-ID är obligatoriskt. API:t innehåller parametrar för offset och begränsning samt en anpassningsstrategi.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Begär parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `processingId` | Sträng | Ja | Unikt ID för det jobb vars loggar ska visas. |
| `offset` | Heltal | Nej | Startpunkten (radnummer) från vilken loggarna ska läsas. Används för sidnumrering för att hoppa över de första N raderna. |
| `limit` | Heltal | Nej | Det maximala antalet loggrader som ska hämtas. |
| `tail` | Heltal | Nej | Antal loggrader som ska hämtas från slutet. |


**Exempel på svar**

```JSON
{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}
```

**Svarskoder**

- 200 lyckades
- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 Internt serverfel


## Hämta jobbloggar

En GET-metod som hämtar loggfilen för ett visst jobb som en ZIP-fil.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Begär parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `processingId` | Sträng | Ja | Unikt ID för det jobb vars loggfil måste hämtas. |


**Exempel på svar**

```JSON
{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Svarskoder**

- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 Internt serverfel

## Avbryt jobb

Ett POST-API som avbryter en pågående begäran om gruppbearbetning av resurser. Om jobbet inte hittas returneras ett fel.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Begär parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `processingId` | Sträng | Ja | Unikt ID för det jobb vars status efterfrågas. |


**Svarskoder**

- 200 lyckades
- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 Internt serverfel


## Återuppta jobb

Ett POST-API som startar om en tidigare avbruten eller misslyckad gruppresursbearbetningsbegäran. Bearbetningen fortsätter från den senaste kontrollpunkten. Om jobbet inte hittas eller körs returnerar API:t ett fel.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Begär parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `processingId` | Sträng | Ja | Unikt ID för det jobb vars status efterfrågas. |


**Svarskoder**

- 200 lyckades
- 400 Ogiltig inmatning
- 401 Obehörig åtkomst
- 500 Internt serverfel

## Visa jobbhistorik

Ett GET-API som returnerar de sista N-körningarna av tillgångarnas efterbearbetning.

**Begär URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Begär parametrar**

Ingen. Denna GET-begäran hämtar jobbhistorik utan att indataparametrar behövs.

**Exempel på svar**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```



