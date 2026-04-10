---
title: Konfigurera DITA Assets Replication för lokala tjänster
description: Lär dig hur du konfigurerar replikering av datatillgångar för lokala tjänster
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 0%

---

# Konfigurera DITA-resursreplikering

Utför följande steg för att konfigurera funktionen för bearbetning av resurser:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Konfigurera inställningen `Replicate DITA assets` enligt dina krav. Som standard är inställningen aktiverad.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Välj **Spara**.
