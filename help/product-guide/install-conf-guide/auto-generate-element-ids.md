---
title: Generera element-ID automatiskt
description: Lär dig generera element-ID automatiskt
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Generera element-ID automatiskt {#id20CIL40016I}

AEM Guides genererar ett dokument-ID för alla nya dokument som du skapar. När du till exempel skapar en DITA-karta tilldelas ett ID som `map.ditamap_random_digits` till kartans ID. Du kan också definiera element som ett ID genereras och tilldelas automatiskt på.

AEM Guides har enkla konfigurationsinställningar där du behöver definiera elementen som ett ID genereras automatiskt på och ett mönster för ID:t. Som standard är vissa element som `section`, `table`, `ul`, `ol` konfigurerade för automatisk generering av ID. Du kan lägga till andra element i den här listan så att när dessa element infogas i ett dokument, genererar och tilldelar AEM Guides ett ID baserat på det angivna mönstret.

På följande flikar finns instruktioner om hur du konfigurerar element så att de har ett automatiskt genererat ID baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera autogenererade element-ID:n:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Ange en kommaavgränsad lista med element. <br> **Standardvärde**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Om du vill konfigurera ett mönster för automatiskt genererat ID skapar du en konfigurationsfil med följande egenskaper:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | Standardvärdet för det här fältet är `${elementName}_${id}`. Värdet `${elementName}` ersätts med elementets namn. Variabeln `${id}` genererar ett sekventiellt nummer för elementet. Om du till exempel tilldelar styckeelementet ett automatiskt genererat ID:n får det första stycket i avsnittet eller dokumentet ett ID som p\_1, nästa stycke får p\_2 osv. I ett annat dokument startar dock ID-genereringsprocessen om. Det innebär att i ett annat dokument kan ID:n som p\_1 och p\_2 tilldelas styckeelement. **Standardvärde**: ``${elementName}_${id}`` |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. I inställningarna för *XmlEditorConfig* anger du ett eller flera element i fältet **Autogenerera ID:n för elementtaggar**.

   >[!NOTE]
   >
   > Elementtaggar är DITA-elementnamn som `body`, `title`, `codeblock` och så vidare. Om du vill ange flera element avgränsar du elementnamnen med ett kommatecken.

1. I fältet **Mönster för att generera ID:n** anger du ett mönster för att generera ett ID.

   Standardvärdet för det här fältet är `${elementName}_${id}`. Värdet `${elementName}` ersätts med elementets namn. Variabeln `${id}` genererar ett sekventiellt nummer för elementet. Om du till exempel tilldelar styckeelementet ett automatiskt genererat ID:n får det första stycket i avsnittet eller dokumentet ett ID som p\_1, nästa stycke får p\_2 osv. I ett annat dokument startar dock ID-genereringsprocessen om. Det innebär att i ett annat dokument kan ID:n som p\_1 och p\_2 tilldelas styckeelement.

   Om dokumentet redan innehåller ID:n i det angivna mönstret tilldelas dessa ID:n inte till nya element i den automatiska genereringsprocessen.

1. Klicka på **Spara**.

>[!ENDTABS]

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
