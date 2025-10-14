---
title: API för att spåra efterbearbetning för en mapp eller en resurs
description: Lär dig mer om API:t för att spåra efterbearbetning av en mapp eller en resurs
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 558108650aeeeda440895972e460fa523b804bb2
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 1%

---

# API för att spåra efterbearbetningsstatus för en mapp eller en resurs

Följande är en POST-metod som startar ett asynkront jobb för att få status för resurser.

## Hitta status för resurser i guider

**Begär URL**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `path` | Sträng | Ja | Mappen eller resurssökvägen som status måste hämtas för. |
| `excludedPaths` | Sträng | Nej | Mappsökvägar som ska uteslutas från ovanstående lista. |

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Svarsvärden**
jobId att avsöka för att hämta status för asynkront jobb.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## Poller-API

En GET-metod som får status för asynkrona jobb som körs med ovanstående API.

**Begär URL**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status`

**Parametrar**

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `jobId` | Sträng | Ja | Jobb-ID som returnerades av ovanstående API. |

**Svarsvärden**

Lista över resurser och deras status.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Statusvärden:** LYCKADES, FEL, BEARBETNING, VÄNTAR
