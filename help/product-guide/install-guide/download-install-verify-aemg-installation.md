---
title: Verifiera installation av AEM Guides
description: Lär dig verifiera AEM Guides-installationen
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Verifiera installation av AEM Guides {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte. Verifiera installationsprocessen genom att utföra följande steg:

1. Logga in på din AEM-instans och gå till sidan AEM Web Console Bundles. Standardwebbadressen för åtkomst till paketsidan är:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   En lista över paket visas.

1. Filtrera paketlistan genom att ange fmdita i textrutan för filtrering och tryck på **Retur**.

   Listan över paket filtreras för att visa de paket som har installerats av AEM Guides. Om installationen slutfördes har alla installerade paket **Status** på **Aktiv**.

   Om något av paketen inte har statusen **Active** kontrollerar du AEM loggar för att felsöka installationsproblemet.


>[!IMPORTANT]
>
> Det finns ett antal rekommendationer för prestandaoptimering som du kan tänka dig för att förbättra systemets prestanda. Mer information finns i [Rekommendationer för prestandaoptimering](download-install-recommend-perf-optimiz.md#).

**Överordnat ämne:**[ Hämta och installera](download-install.md)
