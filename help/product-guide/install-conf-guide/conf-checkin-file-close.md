---
title: Konfigurera en uppmaning om att checka in en fil vid stängning
description: Lär dig hur du konfigurerar uppmaningen att checka in en fil vid stängning
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Konfigurera en uppmaning om att checka in en fil vid stängning {#id222HC040PE8}

När användaren försöker stänga en fil som har öppnats i Web Editor med knappen **Stäng** på filens flik eller med alternativet **Stäng** på Alternativ-menyn, visas en dialogruta om filen innehåller data som inte har sparats eller en version som inte har sparats. Användaren uppmanas att låsa upp filen om den är låst.

Följande flikar innehåller anvisningar om hur du konfigurerar uppmaningar att checka in en fil vid stängning som standard i Web Editor baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera en uppmaning att checka in en fil vid stängning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolean \( true/ false\).<br> **Standardvärde**: false |

När den här konfigurationen är aktiverad är kryssrutan **Lås upp filen** markerad som standard i dialogrutan.

Mer information finns i avsnittet *Stäng och spara scenarier* i guiden Använda Adobe Experience Manager Guides as a Cloud Service.

>[!TAB Lokal]

>[!NOTE]
>
>Kryssrutan **Lås upp filen** är inte aktiverad som standard och du måste aktivera den från configMgr. Följ de här stegen för att aktivera alternativet som standard i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Välj alternativet **Fråga efter incheckning vid stängning**.

1. Klicka på **Spara**.


När den här konfigurationen är aktiverad är kryssrutan **Lås upp filen** markerad som standard i dialogrutan.

Mer information finns i avsnittet *Stäng och spara scenarier* i guiden Använda Adobe Experience Manager Guides as a Cloud Service.

>[!ENDTABS]

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
