---
title: Konfigurera antalet LimitReads för en fråga
description: Lär dig hur du konfigurerar antalet LimitReads för en fråga
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 0%

---

# Konfigurera antalet LimitReads för en fråga om lokal åtkomst

Utför följande steg om du vill öka antalet noder som en fråga kan läsa samtidigt:

1. Öppna Adobe Experience Manager Web Console JMX-sidan.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Sök efter och klicka på **QueryEngineSettings**.

1. Ändra attributvärdet för attributet **LimitReads**.

1. Klicka på **Spara**.


När du ökar det här attributvärdet hjälper det dig att generera rapporten för större DITA-kartor.

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
