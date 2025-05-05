---
title: Konfigurera visning av UUID-baserade länkar
description: Lär dig hur du konfigurerar visning av UUID-baserade länkar
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Konfigurera visning av UUID-baserade länkar {#id2035G20M0QN}

Som standard skapas länken med UUID för det refererade innehållet när du skapar en länk med alternativet Infoga referens eller Infoga återanvänd innehåll i webbredigeraren. Egenskapen **Link** \(i egenskapspanelen\) för det refererade innehållet kan konfigureras så att den relativa filsökvägen för det refererade innehållet eller UUID:t visas. Den här visningen styrs av alternativet **Aktivera UUID** i configMgr. Som standard är den PÅ, vilket betyder att UUID för det refererade innehållet visas på egenskapspanelen.

Utför följande steg för att visa den relativa sökvägen eller UUID för det refererade innehållet i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. I inställningarna för *XmlEditorConfig* är alternativet **Aktivera UUID** aktiverat som standard. Det innebär att UUID för det refererade innehållet visas i egenskapen **Link** på egenskapspanelen.

   Om du vill visa den relativa sökvägen för det länkade innehållet avmarkerar du alternativet **Aktivera UUID**.

1. Klicka på **Spara**.


**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
