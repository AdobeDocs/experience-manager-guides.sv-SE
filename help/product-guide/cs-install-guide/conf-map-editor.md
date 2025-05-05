---
title: Ange avancerad kartredigerare som standard
description: Lär dig hur du anger den avancerade kartredigeraren som standard
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Ange avancerad kartredigerare som standard {#id181AI0003PN}

>[!NOTE]
>
> Redigeraren för den grundläggande kartan, som tidigare fanns i Experience Manager Guides, har tagits bort från version 4.3 och 2307. Du har inte åtkomst till redigeraren för grundläggande kartor för att skapa och hantera DITA-kartor.
>Du rekommenderas att använda den avancerade kartredigeraren. Avancerad kartredigerare har förbättrade funktioner och bättre alternativ för anpassning. Läs mer om hur du arbetar med [Avancerad kartredigerare](../user-guide/map-editor-advanced-map-editor.md).

För tidigare versioner än 4.3 och 2307 har Experience Manager Guides en grundläggande kartredigerare och en avancerad kartredigerare. Med den grundläggande kartredigeraren får du alla funktioner som behövs för att skapa kartfilen. Avancerad kartredigerare har mycket fler funktioner och är integrerad i webbredigeraren. Med Advanced Map Editor kan man skapa och redigera DITA-kartfiler i ett lättanvänt gränssnitt.

När en ny kartfil skapas öppnas den som standard i den grundläggande kartredigeraren. Du kan ändra det här beteendet genom att aktivera inställningen för att öppna den avancerade kartredigeraren som standard.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att aktivera redigeraren för grundläggande mappning:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Boolean \(true/false\). Om du vill använda den avancerade kartredigeraren som standard anger du egenskapen till true.<br> **Standardvärde**: false |

>[!NOTE]
>
> När en författare skapar en kartfil och väljer att öppna den för redigering startas som standard redigeringsprogrammet för grundläggande karta. När alternativet Redigera är markerat för en kartfil i Assets-gränssnittet öppnas det också i den grundläggande kartredigeraren.

**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
