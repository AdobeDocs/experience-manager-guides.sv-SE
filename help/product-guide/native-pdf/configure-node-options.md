---
title: PDF | Konfigurera nodprocess för Native PDF Publishing
description: Lär dig hur du konfigurerar nodprocessen för Native PDF Publishing
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 0%

---

# Konfigurera nodprocess för PDF-publicering

Publicering i PDF påbörjar en separat NodeJs-process för att konvertera filer som genererats i publiceringsprocessen till PDF. Du kanske måste ändra konfigurationerna för den här nodprocessen som kör Native PDF för att stödja olika scenarier. Om du till exempel vill köra större arbetsbelastningar bör du öka den maximala stackstorleken som är tillgänglig för den sparade NodeJs-processen.

Använd instruktionerna i [Konfigurationsåsidosättningar](../cs-install-guide/download-install-additional-config-override.md) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Strängvärde som anger standard `NODE_OPTIONS`.<BR> Standardvärde: &quot;&quot; |
