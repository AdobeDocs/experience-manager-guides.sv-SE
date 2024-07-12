---
title: Konfigurera översättningsfunktionen i webbredigeraren
description: Lär dig hur du konfigurerar översättningsfunktionen i Web Editor
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Konfigurera översättningsfunktionen i webbredigeraren {#id21BONI0J0YR}

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

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
