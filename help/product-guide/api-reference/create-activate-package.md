---
title: REST API för att skapa och aktivera paket
description: Läs mer om REST API för att skapa och aktivera paket
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# REST API för att skapa och aktivera paket {#id198CF0260Y4}

Med följande REST API kan du skapa och aktivera CRX-paket.

## Skapa och aktivera paket

En POST-metod som skapar och aktiverar CRX-paket.

**Begär URL**:
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/activate

**Parametrar**:
Frågefrågan består av JSON-regelsträngen. Innehållstypen för POSTEN måste anges till `application/json; charset=UTF-8`.

**Exempel**:
I följande exempel visas API-anropet med kommandot curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Valfri parameter**

`activationTarget`

**Giltiga värden**

`preview` eller `publish` för Cloud Service och `publish` för lokal programvara

- Om Cloud Servicen innehåller ett ogiltigt värde misslyckas paketaktiveringen.

- Om parametern innehåller ett ogiltigt värde för Lokal programvara loggas felet och publiceringen görs med standardvärdet `publish`.

Om du inte definierar den valfria parametern, `activationTarget`, aktiveras den med standardagenten för publicering för både Cloud Service och lokal programvara.



I följande exempel visas API-anropet med kommandot curl med den valfria parametern:


    &quot;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON-regelsträng](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=`&lt;validActivationTargetValue>`
    &quot;
