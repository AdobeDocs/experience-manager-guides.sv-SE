---
title: Verifiera installation av AEM Guides
description: Lär dig verifiera AEM Guides-installationen
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Verifiera installation av AEM Guides {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte. Verifiera installationsprocessen genom att utföra följande steg:

1. Logga in i AEM och gå till sidan AEM Web Console Bundles. Standardwebbadressen för åtkomst till paketsidan är:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   En lista över paket visas.

1. Filtrera paketlistan genom att ange fmdita i textrutan för filtrering och tryck på **Retur**.

   Listan över paket filtreras för att visa de paket som har installerats av AEM Guides. Om installationen slutfördes har alla installerade paket **Status** på **Aktiv**.

   Om något av paketen inte har statusen **Active** kontrollerar du AEM loggar för att felsöka installationsproblemet.


>[!IMPORTANT]
>
> Det finns ett antal rekommendationer för prestandaoptimering som du kan tänka dig för att förbättra systemets prestanda. Mer information finns i [Recommendations för prestandaoptimering](download-install-recommend-perf-optimiz.md#).

**Överordnat ämne:**[ Hämta och installera](download-install.md)
