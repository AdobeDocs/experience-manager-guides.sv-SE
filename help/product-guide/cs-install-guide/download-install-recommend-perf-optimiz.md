---
title: Recommendations för prestandaoptimering
description: Lär dig Recommendations för prestandaoptimering
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Recommendations för prestandaoptimering {#id213BD0JG0XA}

Tänk på följande för prestandaoptimering:

- Information om hur du optimerar innehåll och indexering finns i [Optimera sökning och indexering av innehåll](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html) i AEM.

- Patch Xerces Jar när anpassad DITA-OT används för publicering. Detta är en obligatorisk konfiguration, beroende på ditt användningssätt. Den här ändringen krävs bara om du använder anpassad DITA-OT för publicering av utdata.

  *Nödvändig konfiguration*: Ersätt Xerces Jar-filen i ditt anpassade DITA-OT-paket med den som levererades OOTB. OTB-standardfilen xercesImpl-2.11.0.jar finns i filen _resources/DITA-OT.zip. Byt namn på filen xercesImpl-2.11.0.jar så att den matchar den gamla Xerces Jar-filen som ska ersättas. Detta kan göras vid körning.

  Ändringen minskar publiceringstiden och minnesanvändningen när DITA-kartor publiceras med ett stort antal ämnen.


**Överordnat ämne:**[ Hämta och installera](download-install.md)
