---
title: Konfigurera resursbearbetning för lokala tjänster
description: Konfigurera resursbearbetning för lokala tjänster
feature: Output Generation
role: Admin
level: Experienced
exl-id: 9d771bba-aa90-4726-a75f-1cb7b804a192
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '66'
ht-degree: 0%

---

# Konfigurera funktionen för bearbetning av resurser

Utför följande steg för att konfigurera funktionen för bearbetning av resurser:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Konfigurera inställningen `Enable Guides asset processing scheduled job` enligt dina krav. Som standard är inställningen aktiverad.

1. Välj **Spara**.
