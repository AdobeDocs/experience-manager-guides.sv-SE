---
title: Rekommendationer för prestandaoptimering för Cloud Service
description: Lär dig rekommendationer för prestandaoptimering
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Rekommendationer för prestandaoptimering för Cloud Service {#id213BD0JG0XA}

Tänk på följande för prestandaoptimering:

- Information om hur du optimerar innehåll och indexering finns i [Optimera innehållssökning och indexering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=sv-SE) i AEM-dokumentationen.

- Patch Xerces Jar när anpassad DITA-OT används för publicering. Detta är en obligatorisk konfiguration, beroende på ditt användningssätt. Den här ändringen krävs bara om du använder anpassad DITA-OT för publicering av utdata.

  *Nödvändig konfiguration*: Ersätt Xerces Jar-filen i ditt anpassade DITA-OT-paket med den som levererades OTB. OTB `xercesImpl-2.11.0.jar`-standardfilen är tillgänglig i filen `/libs/fmdita/dita\_resources/DITA-OT.zip`. Se till att du byter namn på filen `xercesImpl-2.11.0.jar` så att den matchar den gamla Xerces JAR-filen som ersätts. Detta kan göras vid körning.

  Ändringen minskar publiceringstiden och minnesanvändningen när DITA-kartor publiceras med ett stort antal ämnen.

