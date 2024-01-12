---
title: Verifiera installation av AEM
description: Lär dig hur du verifierar installationen av AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verifiera installation av AEM {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte. Verifiera installationen genom att utföra följande steg:

1. Gå till Developer Console för Cloud Servicen.

   Mer information om hur du använder Developer Console finns i [Åtkomst till Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) i AEM.

1. Gå till listan över OSGi Bundles i AEM.

   Mer information om hur du får åtkomst till paket finns i [Paket](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) i AEM.

1. Sök efter fmdita i paketlistan och kontrollera status.

   Statusen ska visas *Aktiv* för lyckade distribuerade paket. Om något av paketet inte har statusen Aktiv kontrollerar du AEM loggar för att felsöka installationsproblemet.


**Överordnat ämne:**[ Hämta och installera](download-install.md)
