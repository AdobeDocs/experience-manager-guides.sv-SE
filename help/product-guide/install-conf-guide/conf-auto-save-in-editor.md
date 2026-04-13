---
title: Konfigurera autosparande av filer i Web Editor
description: Lär dig hur du konfigurerar autosparande av filer i Web Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
source-git-commit: 2749c0df3bd5640c9491dce3ab6c96f707625969
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Konfigurera autosparande av filer i Web Editor {#id199CC0J0M5Z}

En av de vanligaste funktionerna i den webbläsarbaserade redigeraren är möjligheten att spara data efter en viss tidsperiod. AEM Guides Web Editor har även stöd för att automatiskt spara ämne- och mappfiler med angivet tidsintervall. När den här funktionen aktiveras sparas arbetskopian av ämnet eller kartan. Ingen ny version av ämnet eller kartan skapas. Om du vill skapa en ny version måste du klicka på ikonen Spara ändring i webbredigerarens verktygsfält.

Funktionen för att spara automatiskt är inte aktiverad som standard och du måste aktivera den med konfigurationsfilen för Cloud Service och från `configMgr` för lokal installation.

Följande flikar innehåller anvisningar om hur du aktiverar funktionen för att spara automatiskt i Web Editor baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera tidsintervallet för autosparande och autosparande av filer:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolean \(true/false\).<br> **Standardvärde**: false |
| `xmleditor.autosaveinterval` | Ange tidsintervallet i sekunder för att aktivera funktionen för autosparande. |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Välj alternativet *Spara automatiskt* i inställningarna för **XmlEditorConfig** .

1. I fältet **Intervall för automatiskt sparande** anger du tidsintervallet i sekunder för att aktivera funktionen för automatiskt sparande.

1. Klicka på **Spara**.

>[!ENDTABS]
