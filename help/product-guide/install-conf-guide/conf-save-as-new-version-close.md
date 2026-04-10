---
title: Konfigurera uppmaningen att spara som en ny version vid stängning
description: Lär dig hur du konfigurerar uppmaningen att spara som en ny version vid stängning
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Konfigurera uppmaningen att spara som en ny version vid stängning {#id222HBI00XXA}

När användaren försöker stänga en fil som har öppnats i Web Editor med knappen **Stäng** på filens flik eller med alternativet **Stäng** på Alternativ-menyn, visas en dialogruta om filen innehåller data som inte har sparats eller en version som inte har sparats. Användaren uppmanas att spara filen som en ny version om versionen inte sparas.

På följande flikar finns instruktioner som baseras på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera en uppmaning att spara som en ny version vid stängning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolean \( true/ false\). <br>  **Standardvärde**: true |

När den här konfigurationen är aktiverad är kryssrutan **Spara som ny version** markerad som standard i dialogrutan.

Mer information finns i avsnittet *Stäng och spara scenarier* i guiden Använda Adobe Experience Manager Guides as a Cloud Service.

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Välj alternativet **Fråga efter ny version vid stängning**.

1. Klicka på **Spara**.


Kryssrutan **Spara som ny version** är inte aktiverad som standard och du måste aktivera den från configMgr.

När det här alternativet är markerat är kryssrutan **Spara som ny version** markerad som standard i dialogrutan.

Mer information finns i avsnittet *Stäng och spara scenarier* i guiden Använda Adobe Experience Manager Guides as a Cloud Service.

>[!ENDTABS]