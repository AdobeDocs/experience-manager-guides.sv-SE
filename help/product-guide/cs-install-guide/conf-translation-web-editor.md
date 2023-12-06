---
title: Konfigurera översättningsfunktionen i webbredigeraren
description: Lär dig hur du konfigurerar översättningsfunktionen i Web Editor
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Konfigurera översättningsfunktionen i webbredigeraren {#id21BONI0J0YR}

Webbredigeraren har en kraftfull översättningsfunktion som översätter ditt innehåll till flera språk.

Du kan använda **Hantera** -fliken i Web Editor för att översätta innehållet. Fliken är som standard tillgänglig.

Dölj **Hantera** utför följande steg på fliken i Web Editor:

1. Logga in **Adobe Experience Manager** som administratör.
1. Klicka på **Adobe Experience Manager** överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Klicka på **Konfiguration av XML-redigerare**.
1. Klicka på **Redigera** överst.
1. Ladda ned `ui\_config.json` file.Ta bort följande kodfragment från den hämtade filen:

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

Observera att **Hantera** filtret är inte längre tillgängligt.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
