---
title: Konfigurera visning av UUID-baserade länkar
description: Lär dig hur du konfigurerar visning av UUID-baserade länkar
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Konfigurera visning av UUID-baserade länkar {#id2035G20M0QN}

När du skapar en länk med alternativet Infoga referens eller Infoga återanvänd innehåll i redigeraren skapas länken som standard med UUID för det refererade innehållet. Egenskapen **Link** \(i egenskapspanelen\) för det refererade innehållet kan konfigureras så att den relativa filsökvägen för det refererade innehållet eller UUID:t visas. För Cloud Service visas som standard UUID för det refererade innehållet på egenskapspanelen. För lokal visning styrs den här visningen av alternativet **Aktivera UUID** i `configMgr`. Som standard är den PÅ, vilket betyder att UUID för det refererade innehållet visas på egenskapspanelen.

På följande flikar finns instruktioner för att visa den relativa sökvägen eller UUID för det refererade innehållet i redigeraren baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att visa den relativa sökvägen eller UUID för det refererade innehållet i redigeraren.

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolean \(true/false\). Om du vill visa den relativa sökvägen för det länkade innehållet anger du egenskapen till false. <br> **Standardvärde**: true |


>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. I inställningarna för *XmlEditorConfig* är alternativet **Aktivera UUID** aktiverat som standard. Det innebär att UUID för det refererade innehållet visas i egenskapen **Link** på egenskapspanelen.

   Om du vill visa den relativa sökvägen för det länkade innehållet avmarkerar du alternativet **Aktivera UUID**.

1. Klicka på **Spara**.

>[!ENDTABS]

**Överordnat ämne:**[ Anpassa Web Editor](customize-overview.md)
