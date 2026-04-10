---
title: PDF | Konfigurera basutdataplats för publicering av PDF för molntjänster
description: Konfigurera basutdataplats för publicering av PDF för molntjänster
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
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
