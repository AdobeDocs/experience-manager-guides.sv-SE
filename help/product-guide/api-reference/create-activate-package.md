---
title: REST API för att skapa och aktivera paket
description: Läs mer om REST API för att skapa och aktivera paket
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# REST API för att skapa och aktivera paket {#id198CF0260Y4}

Med följande REST API kan du skapa och aktivera CRX-paket.

## Skapa och aktivera paket

En POST-metod som skapar och aktiverar CRX-paketet.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/activate

**Parametrar**:
Frågefrågan består av JSON-regelsträngen. Innehållstypen för POST-begäran måste anges till `application/json; charset=UTF-8`.

**Exempel**:
I följande exempel visas API-anropet med kommandot curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Valfri parameter**

`activationTarget`

**Giltiga värden**

`preview` eller `publish` för Cloud Service och `publish` för lokal programvara

- Om parametern innehåller ett ogiltigt värde för Cloud Service misslyckas paketaktiveringen.

- Om parametern innehåller ett ogiltigt värde för Lokal programvara loggas felet och publiceringen görs med standardvärdet `publish`.

Om du inte definierar den valfria parametern, `activationTarget`, aktiveras den med standardagenten för publicering för både Cloud Service och lokal programvara.



I följande exempel visas API-anropet med kommandot curl med den valfria parametern:


```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate?activationTarget=`<validActivationTargetValue>`
```
