---
title: PDF | Konfigurera basutdataplats för publicering av PDF för molntjänster
description: Konfigurera basutdataplats för publicering av PDF för molntjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 0%

---

# Konfigurera basutdataplats för publicering av utdata för molntjänster

Så här konfigurerar du basutdataplatsen:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](../cs-install-guide/download-install-additional-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera basutdataplatsen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Standardvärde:** &quot;/content/dam/fmdita-outputs&quot; |
