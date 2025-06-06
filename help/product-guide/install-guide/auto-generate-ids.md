---
title: Generera element-ID automatiskt
description: Lär dig generera element-ID automatiskt
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Generera element-ID automatiskt {#id20CIL40016I}

AEM Guides genererar ett dokument-ID för alla nya dokument som du skapar. När du till exempel skapar en DITA-karta tilldelas ett ID som `map.ditamap_random_digits` till kartans ID. Du kan också definiera element som ett ID genereras och tilldelas automatiskt på.

AEM Guides har enkla konfigurationsinställningar där du behöver definiera elementen som ett ID genereras automatiskt på och ett mönster för ID:t. Som standard är vissa element som `section`, `table`, `ul`, `ol` konfigurerade för automatisk generering av ID. Du kan lägga till andra element i den här listan så att när dessa element infogas i ett dokument, genererar och tilldelar AEM Guides ett ID baserat på det angivna mönstret

Utför följande steg för att konfigurera element så att de har ett autogenererat ID:

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


**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
