---
title: Konfigurera visning av UUID-baserade länkar
description: Lär dig hur du konfigurerar visning av UUID-baserade länkar
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Konfigurera visning av UUID-baserade länkar {#id2035G20M0QN}

Som standard skapas länken med UUID för det refererade innehållet när du skapar en länk med alternativet Infoga referens eller Infoga återanvänd innehåll i webbredigeraren. The **Länk** egenskapen \(i egenskapspanelen\) för det refererade innehållet kan konfigureras så att den relativa filsökvägen för det refererade innehållet eller UUID:t visas. Den här visningen styrs av **Aktivera UUID** i configMgr. Som standard är den PÅ, vilket betyder att UUID för det refererade innehållet visas på egenskapspanelen.

Utför följande steg för att visa den relativa sökvägen eller UUID för det refererade innehållet i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. I *XmlEditorConfig* inställningar, **Aktivera UUID** är aktiverat som standard. Det innebär att UUID för det refererade innehållet visas i **Länk** i egenskapspanelen.

   Om du vill visa den relativa sökvägen för det länkade innehållet avmarkerar du **Aktivera UUID** alternativ.

1. Klicka **Spara**.


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
