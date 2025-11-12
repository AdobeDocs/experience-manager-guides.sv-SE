---
title: Konfigurera rensningsjobb för B-träd för lokala tjänster
description: Konfigurera rensningsjobb för B-träd för lokala tjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# Konfigurera rensning av B-träd

Konfigurera rensningsjobbet för B-trädet och hantera inställningen `Guides B-tree deletion` så att systemet förblir optimerat och lagringen rensas.

## Konfigurera rensningsjobb för B-träd

Utför följande steg för att konfigurera rensningsjobb för B-träd:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.guides.utils.edulers.GuidesBTreesCleanupSchedulerJob*.

1. Uppdatera cron-uttrycket för att ställa in jobbkörningsfrekvensen för schemaläggning av B-träd.

1. Konfigurera schemaläggaren för rensning av B-träd enligt nedan.

   ![](assets/btree-cleanup-config.png){align="left"}

1. Välj **Spara**.


## Aktivera inställning för borttagning av stödlinjer i B-träd

Aktivera inställningen genom att utföra följande steg:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.
1. Aktivera inställningen `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Välj **Spara**.

