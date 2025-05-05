---
title: Konfigurera alternativet för redigering i syrgas
description: Lär dig hur du konfigurerar alternativet att redigera i plugin-programmet för syreanslutning.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# Konfigurera alternativet för redigering i syrgas

AEM Guides tillåter även användare att redigera sina DITA-avsnitt och DITA-kartor i insticksprogrammet för syreanslutning.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet **Redigera i syre**:



| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolean \(true/false\). **Standardvärde**: false |

>[!NOTE]
>
> Den här konfigurationen är inaktiverad som standard och alternativet är inte tillgängligt i Web Editor.

**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
