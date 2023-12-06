---
title: Verifiera installation av AEM
description: Lär dig hur du verifierar installationen av AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Verifiera installation av AEM {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte. Verifiera installationsprocessen genom att utföra följande steg:

1. Logga in i AEM och gå till sidan AEM Web Console Bundles. Standardwebbadressen för åtkomst till paketsidan är:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   En lista över paket visas.

1. Filtrera paketlistan genom att ange fmdita i textrutan för filtrering och trycka på **Retur**.

   Listan med paket filtreras för att visa de paket som har installerats av AEM. Om installationen lyckades får alla installerade paket en **Status** av **Aktiv**.

   Om något av paketen inte har en **Aktiv** och kontrollera AEM loggar för att felsöka installationsproblemet.


>[!IMPORTANT]
>
> Det finns ett antal rekommendationer för prestandaoptimering som du kan tänka dig för att förbättra systemets prestanda. Se [Recommendations för prestandaoptimering](download-install-recommend-perf-optimiz.md#) för mer information.

**Överordnat ämne:**[ Hämta och installera](download-install.md)
