---
title: Ange avancerad kartredigerare som standard
description: Lär dig hur du anger den avancerade kartredigeraren som standard
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Ange avancerad kartredigerare som standard {#id181AI0003PN}

AEM innehåller en grundläggande kartredigerare och en avancerad kartredigerare. Med den grundläggande kartredigeraren får du alla funktioner som behövs för att skapa kartfilen. Avancerad kartredigerare har mycket fler funktioner och är integrerad i webbredigeraren. Med Advanced Map Editor kan man skapa och redigera DITA-kartfiler i ett lättanvänt gränssnitt.

När en ny kartfil skapas öppnas den som standard i den grundläggande kartredigeraren. Du kan ändra det här beteendet genom att aktivera inställningen för att öppna den avancerade kartredigeraren som standard.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att aktivera redigeraren för grundläggande mappning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Boolean \(true/false\). Om du vill använda den avancerade kartredigeraren som standard anger du den här egenskapen till true.<br> **Standardvärde**: false |

>[!NOTE]
>
> När en författare skapar en kartfil och väljer att öppna den för redigering startas som standard redigeringsprogrammet för grundläggande karta. När alternativet Redigera har valts för en kartfil i resursgränssnittet öppnas den också i den grundläggande kartredigeraren.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
