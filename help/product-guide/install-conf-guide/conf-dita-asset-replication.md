---
title: Konfigurera DITA Assets Replication
description: Lär dig hur du konfigurerar replikering av digitala resurser
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---

# Konfigurera DITA-resursreplikering

Följande flikar innehåller anvisningar om hur du konfigurerar replikeringsfunktionen för DITA-resurser baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](../install-conf-guide/download-install-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Standardvärde:** &quot;true&quot; |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Konfigurera inställningen `Replicate DITA assets` enligt dina krav. Som standard är inställningen aktiverad.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Välj **Spara**.

>[!ENDTABS]
