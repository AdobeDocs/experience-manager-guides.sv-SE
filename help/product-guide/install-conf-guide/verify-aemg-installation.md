---
title: Verifiera installation av AEM Guides
description: Lär dig verifiera AEM Guides-installationen
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Verifiera installation av AEM Guides {#id213BD030FBE}

När du har installerat AEM Guides måste du kontrollera om installationen lyckades eller inte.

Följande flikar innehåller anvisningar om hur du verifierar AEM Guides-installationen baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verifiera installationen genom att utföra följande steg:

1. Få tillgång till din Cloud Service Developer Console.

   Mer information om hur du får åtkomst till Developer Console finns i [Developer Console-åtkomst](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) i dokumentationen för AEM.

1. Gå till listan över OSGi Bundles i AEM.

   Mer information om hur du får åtkomst till paket finns i [Paket](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) i AEM-dokumentationen.

1. Sök efter fmdita i paketlistan och kontrollera status.

   Statusen ska visa *Aktiv* för distribuerade paket. Om något av paketet inte har statusen Aktiv kontrollerar du AEM loggar för att felsöka installationsproblemet.

>[!TAB Lokal]

Verifiera installationen genom att utföra följande steg:

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
> Det finns ett antal rekommendationer för prestandaoptimering som du kan tänka dig för att förbättra systemets prestanda. Mer information finns i [Rekommendationer för prestandaoptimering](perf-optimization-on-prem.md#).

>[!ENDTABS]


