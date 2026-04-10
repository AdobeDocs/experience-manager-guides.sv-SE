---
title: Konfigurera översättningsfunktionen i webbredigeraren
description: Lär dig hur du konfigurerar översättningsfunktionen i Web Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Konfigurera översättningsfunktionen i Web Editor för Cloud Service

Webbredigeraren har en kraftfull översättningsfunktion som översätter ditt innehåll till flera språk.

Du kan använda fliken **Hantera** i Web Editor för att översätta ditt innehåll. Fliken är som standard tillgänglig.

Så här döljer du fliken **Hantera** i Web Editor:

1. Logga in på **Adobe Experience Manager** som administratör.
1. Klicka på länken **Adobe Experience Manager** överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Klicka på **XML-redigerarkonfiguration**.
1. Klicka på ikonen **Redigera** överst.
1. Hämta filen `ui\_config.json`.Ta bort följande kodfragment från den hämtade filen:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Ladda upp den uppdaterade filen ui\_config.json.

Observera att filtret **Hantera** inte längre är tillgängligt.

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
