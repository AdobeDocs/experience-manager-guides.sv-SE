---
title: Konfigurera rensningsjobb för B-träd för molntjänster
description: Konfigurera rensningsjobb för B-träd för molntjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 5b29b2b5f725b5d9a2029fb232e62f387a5338fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---

# Konfigurera rensning av B-träd

Konfigurera rensningsjobbet för B-trädet och hantera inställningen `Guides BTree deletion` så att systemet förblir optimerat och lagringen rensas.

## Konfigurera rensningsjobb för B-träd

Utför följande steg för att konfigurera rensningsjobb för B-träd:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](../cs-install-guide/download-install-additional-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Standardvärde:** &quot;0 0 0 * ?&quot; |


## Aktivera inställning för borttagning av stödlinjer i B-träd

Aktivera inställningen genom att utföra följande steg:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](../cs-install-guide/download-install-additional-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Standardvärde:** &quot;Sant&quot; |