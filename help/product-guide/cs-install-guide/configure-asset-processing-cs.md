---
title: Konfigurera resursbearbetning för molntjänsten
description: Lär dig hur du konfigurerar resursbearbetning för molntjänster
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 5b29b2b5f725b5d9a2029fb232e62f387a5338fd
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 0%

---

# Konfigurera funktionen för bearbetning av resurser

Så här konfigurerar du funktionen för bearbetning av resurser:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](../cs-install-guide/download-install-additional-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Standardvärde:** &quot;true&quot; |
