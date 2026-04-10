---
title: PDF | Configure Node process for Native PDF Publishing
description: Lär dig konfigurera nodprocessen för PDF Publishing
feature: Output Generation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%

---

# Konfigurera nodprocess för PDF-publicering för Cloud Service

PDF-publicering startar en separat NodeJs-process för att konvertera de filer som genereras i publiceringsprocessen till en slutgiltig PDF. Du kan behöva justera konfigurationerna för den här nodprocessen genom att köra PDF-publicering för att stödja olika scenarier. Om du till exempel vill köra större arbetsbelastningar bör du öka den maximala stackstorleken som är tillgänglig för den sparade NodeJs-processen.

Använd instruktionerna i [Konfigurationsåsidosättningar](../install-conf-guide/download-install-config-override.md) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Strängvärde som anger standard `NODE_OPTIONS`.<BR> Standardvärde: &quot;&quot; |
