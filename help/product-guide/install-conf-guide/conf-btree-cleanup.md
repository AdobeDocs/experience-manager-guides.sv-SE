---
title: Konfigurera rensningsjobb för B-träd för molntjänster
description: Konfigurera rensningsjobb för B-träd för molntjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Konfigurera rensning av B-träd

Konfigurera rensningsjobbet för B-trädet och hantera inställningen `Guides BTree deletion` så att systemet förblir optimerat och lagringen rensas.

## Konfigurera rensningsjobb för B-träd

På följande flikar finns anvisningar om hur du konfigurerar rensningsjobb för B-träd baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Standardvärde:** &quot;0 0 0 * ?&quot; |

>[!TAB Lokal]

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

>[!ENDTABS]

## Aktivera inställning för borttagning av stödlinjer i B-träd

Följande flikar innehåller instruktioner om hur du aktiverar inställningen baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Standardvärde:** &quot;Sant&quot; |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.
1. Aktivera inställningen `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Välj **Spara**.

>[!ENDTABS]