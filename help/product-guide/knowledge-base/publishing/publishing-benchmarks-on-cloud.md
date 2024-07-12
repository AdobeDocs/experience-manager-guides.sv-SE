---
title: Guides Publishing Benchmarks on AEMaaCS
description: Förstå systembegränsningar för publicering på AEM Cloud.
exl-id: 2cb4dfa4-dafc-409a-8d29-dbb00fabeae5
feature: Publishing
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%

---

# AEM Guides Publishing Benchmarks on AEMaaCS

AEM Guides molntjänst har för närvarande vissa begränsningar för publiceringskartor som Guidad-teamet arbetar med att lösa.

Guides Team har introducerat en skalbar publiceringsmikrotjänst för stöd till stora kartor och flera samtidiga publiceringstillfällen. Mer information om den nya publiceringsmikrotjänsten finns i [publiceringsarkitekturen för mikrotjänster](publish-microservice-architecture-and-performance.md)

Information om hur du konfigurerar den nya publiceringstjänsten för AEM molnmiljö finns i [Konfigurera ny mikrotjänstbaserad publicering](configure-microservices.md)


## Körningsmiljö

    AEM utgåva: 2023.5.11983.20230511T173830Z
    Guiden Lägg till i utgåva: 2023.6.0
    AEM Webbplatsmall: AEM Guides OTB-mall
    DITA-OT version: 3 .5.4
    Publish Workflow Type: Split Publish Workflow
    Output supported by microservice: Native PDF, PDF (Dita-OT)

## Genereringsnummer för utdata

| Utdatatyp | Kartstorlek (ämnesreferenser) | Körningstid (i sekunder) | Publishing Microservice |
|---------------|------------------------------|----------------------------|-----------------------|
| AEM | 3500 | 5220 | Nej |
| PDF | 3500 | 780 | Ja |
| PDF (DITA-OT) | 11000 | 960 | Ja |
| HTML5 | 3500 | 240 | Nej |
| Egen | 300 | 300 | Nej |

## Viktiga punkter att komma ihåg

- AEM Site skapar många cq:Page-noder och förenklar genom att återge dem individuellt under genereringstiden. Därför är det tillrådligt att undvika att köra flera stora parallella publiceringar AEM webbplatsen eftersom det kan belasta systemet.
- AEM tid beror på vilken mall som används. Körningstiden kan öka om komplexa mallar används.
- Anpassad publiceringstid är för ett exempel på anpassade utdata. Anpassad publiceringstid beror enbart på kundens egen omvandlingslogik.
