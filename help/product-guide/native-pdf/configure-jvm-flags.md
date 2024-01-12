---
title: PDF | Konfigurera JVM-flaggor för Native PDF Publishing
description: Konfigurera JVM-flaggor för Native PDF Publishing
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---

# Konfigurera JVM-flaggor för Native PDF Publishing

Inbyggd PDF-publicering startar en separat JVM-process för att generera en PDF. Du kan behöva justera konfigurationerna för denna JVM för att stödja olika scenarier. Om du till exempel vill köra större arbetsbelastningar bör du öka den maximala stackstorleken som är tillgänglig för den skapade JVM-processen.

Utför följande steg för att konfigurera AEM Guides Native PDF Publishing JVM-flaggor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj *com.adobe.fmdita.config.ConfigManager* paket.

1. Uppdatera egenskapen **Java-kommandoradsalternativ för inbyggd PDF-fil** (*native.pdf.java.opts*) för att skicka alla vanliga JVM-flaggor.



1. Klicka **Spara**.
