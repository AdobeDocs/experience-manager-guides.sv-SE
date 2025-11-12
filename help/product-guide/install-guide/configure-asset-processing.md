---
title: Konfigurera resursbearbetning för lokala tjänster
description: Konfigurera resursbearbetning för lokala tjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
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
