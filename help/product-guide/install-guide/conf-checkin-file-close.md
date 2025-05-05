---
title: Konfigurera en uppmaning om att checka in en fil vid stängning
description: Lär dig hur du konfigurerar uppmaningen att checka in en fil vid stängning
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Konfigurera en uppmaning om att checka in en fil vid stängning {#id222HC040PE8}

När användaren försöker stänga en fil som har öppnats i Web Editor med knappen **Stäng** på filens flik eller med alternativet **Stäng** på Alternativ-menyn, visas en dialogruta om filen innehåller data som inte har sparats eller en version som inte har sparats. Användaren uppmanas att låsa upp filen om den är låst.

Kryssrutan **Lås upp filen** är inte aktiverad som standard och du måste aktivera den från configMgr. Följ de här stegen för att aktivera alternativet som standard i Web Editor:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Välj alternativet **Fråga efter incheckning vid stängning**.

1. Klicka på **Spara**.


När den här konfigurationen är aktiverad är kryssrutan **Lås upp filen** markerad som standard i dialogrutan.

Mer information finns i avsnittet *Stäng och spara scenarier* i Använda Adobe Experience Manager Guides as a Cloud Service Guide.

**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
