---
title: Verifiera installation av AEM Guides
description: Lär dig verifiera AEM Guides-installationen
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verifiera installation av AEM Guides {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte. Verifiera installationen genom att utföra följande steg:

1. Få tillgång till din Cloud Service Developer Console.

   Mer information om hur du får åtkomst till Developer Console finns i [Developer Console-åtkomst](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) i dokumentationen för AEM.

1. Gå till listan över OSGi Bundles i AEM.

   Mer information om hur du får åtkomst till paket finns i [Paket](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) i AEM-dokumentationen.

1. Sök efter fmdita i paketlistan och kontrollera status.

   Statusen ska visa *Aktiv* för distribuerade paket. Om något av paketet inte har statusen Aktiv kontrollerar du AEM loggar för att felsöka installationsproblemet.


**Överordnat ämne:**[ Hämta och installera](download-install.md)
