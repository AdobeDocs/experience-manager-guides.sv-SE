---
title: Konfigurera basutdataplats för publicering av utdata för lokala tjänster
description: Konfigurera basutdataplats för publicering av utdata för lokala tjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%

---

# Konfigurera basutdataplats för publicering av utdata för lokala tjänster

Utför följande steg för att konfigurera basutdataplatsen:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Uppdatera egenskapen **Base Output Location** för att ange standardsökvägen i AEM-databasen där PDF ska sparas efter publicering. Om en ogiltig sökväg anges återgår den automatiskt till standardsökvägen: /content/dam/fmdita-outputs.

1. Klicka på **Spara**.


