---
title: Verifiera installation av AEM Guides
description: Lär dig verifiera AEM Guides-installationen
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verifiera installation av AEM Guides {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte. Verifiera installationen genom att utföra följande steg:

1. Få tillgång till Cloud Servicens Developer Console.

   Mer information om hur du får åtkomst till Developer Console finns i [Developer Console-åtkomst](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=sv-SE) i AEM.

1. Gå till listan över OSGi Bundles i AEM.

   Mer information om hur du får åtkomst till paket finns i [Paket](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=sv-SE#bundles) i AEM.

1. Sök efter fmdita i paketlistan och kontrollera status.

   Statusen ska visa *Aktiv* för distribuerade paket. Om något av paketet inte har statusen Aktiv kontrollerar du AEM loggar för att felsöka installationsproblemet.


**Överordnat ämne:**&#x200B;[&#x200B; Hämta och installera](download-install.md)
