---
title: Konfigurera resursbearbetning för molntjänsten
description: Lär dig hur du konfigurerar resursbearbetning för molntjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---

# Konfigurera funktionen för bearbetning av resurser

Följande flikar innehåller anvisningar om hur du konfigurerar funktionen för bearbetning av resurser baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Standardvärde:** &quot;true&quot; |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Konfigurera inställningen `Enable Guides asset processing scheduled job` enligt dina krav. Som standard är inställningen aktiverad.

1. Välj **Spara**.

>[!ENDTABS]