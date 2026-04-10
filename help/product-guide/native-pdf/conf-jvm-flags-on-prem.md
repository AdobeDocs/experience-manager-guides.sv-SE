---
title: PDF | Konfigurera JVM-flaggor för PDF-publicering
description: Konfigurera JVM-flaggor för PDF Publishing
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---

# Konfigurera JVM-flaggor för inbyggd PDF-publicering för lokal

PDF-publicering startar en separat JVM-process för att generera en PDF. Du kan behöva justera konfigurationerna för denna JVM för att stödja olika scenarier. Om du till exempel vill köra större arbetsbelastningar bör du öka den maximala stackstorleken som är tillgänglig för den skapade JVM-processen.

Utför följande steg för att konfigurera JVM-flaggor för AEM Guides Native PDF Publishing:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Uppdatera egenskapen **Java Command line options för den inbyggda pdf** (*native.pdf.java.opts*) för att skicka alla vanliga JVM-flaggor.



1. Klicka på **Spara**.
