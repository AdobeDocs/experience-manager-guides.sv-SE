---
title: Konfigurera visning av UUID-baserade länkar
description: Lär dig hur du konfigurerar visning av UUID-baserade länkar
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Konfigurera visning av UUID-baserade länkar {#id2035G20M0QN}

Som standard skapas länken med UUID för det refererade innehållet när du skapar en länk med alternativet Infoga referens eller Infoga återanvänd innehåll i webbredigeraren. The **Länk** egenskapen \(i egenskapspanelen\) för det refererade innehållet kan konfigureras så att den relativa filsökvägen för det refererade innehållet eller UUID:t visas. Som standard visas UUID för det refererade innehållet på egenskapspanelen.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att visa den relativa sökvägen eller UUID för det refererade innehållet i Web Editor:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolean \(true/false\). Om du vill visa den relativa sökvägen för det länkade innehållet anger du egenskapen till false. <br> **Standardvärde**: true |

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
