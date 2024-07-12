---
title: Konfigurera uppmaningen att spara som en ny version vid stängning
description: Lär dig hur du konfigurerar uppmaningen att spara som en ny version vid stängning
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Konfigurera uppmaningen att spara som en ny version vid stängning {#id222HBI00XXA}

När användaren försöker stänga en fil som har öppnats i Web Editor med knappen **Stäng** på filens flik eller med alternativet **Stäng** på Alternativ-menyn, visas en dialogruta om filen innehåller data som inte har sparats eller en version som inte har sparats. Användaren uppmanas att spara filen som en ny version om versionen inte sparas.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera en uppmaning att spara som en ny version vid stängning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolean \( true/ false\). <br>  **Standardvärde**: true |

När den här konfigurationen är aktiverad är kryssrutan **Spara som ny version** markerad som standard i dialogrutan.

Mer information finns i avsnittet *Stäng och spara scenarier* i Använda Adobe Experience Manager Guides as a Cloud Service Guide.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
