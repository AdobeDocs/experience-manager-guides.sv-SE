---
title: Konfigurera alternativet för redigering i syrgas
description: Lär dig hur du konfigurerar alternativet att redigera i plugin-programmet för syreanslutning.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# Konfigurera alternativet att redigera i Syrgas för Cloud Service

AEM Guides tillåter även användare att redigera sina DITA-avsnitt och DITA-kartor i insticksprogrammet för syreanslutning.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet **Redigera i syre**:



| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolean \(true/false\). **Standardvärde**: false |

>[!NOTE]
>
> Den här konfigurationen är inaktiverad som standard och alternativet är inte tillgängligt i Web Editor.

**Överordnat ämne:**[ Anpassa Web Editor](customize-overview.md)
