---
title: Konfigurera DITA Assets Replication för molntjänsten
description: Lär dig hur du konfigurerar replikering av datatillgångar för molntjänsten
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 356ea6edd5e688fb1f77e737c705ed0bd4d2e7f0
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 0%

---

# Konfigurera DITA-resursreplikering

Så här konfigurerar du funktionen för bearbetning av resurser:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](../cs-install-guide/download-install-additional-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Standardvärde:** &quot;true&quot; |
