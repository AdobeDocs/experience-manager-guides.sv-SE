---
title: REST API för att skapa och aktivera paket
description: Läs mer om REST API för att skapa och aktivera paket
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# REST API för att skapa och aktivera paket {#id198CF0260Y4}

Med följande REST API kan du skapa och aktivera CRX-paket.

## Skapa och aktivera paket

En POST-metod som skapar och aktiverar CRX-paket.

**Begär URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Parametrar**: Begäran-frågan består av JSON-regelsträngen. Innehållstypen för begäran om POST måste anges till `application/json; charset=UTF-8`.

**Exempel**: I följande exempel visas API-anropet med kommandot curl:

    &quot;
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aau em-guides-server*>:&lt;*port-number*>/bin/fmdita/activate
    &quot;
