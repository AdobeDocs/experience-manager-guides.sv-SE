---
title: Konfigurera automatiska filnamn baserat på UUID
description: Lär dig konfigurera automatiska filnamn baserat på UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# Konfigurera automatiska filnamn baserat på UUID {#id205QG070D5Z}

När ett ämne eller en kartfil skapas får författare som standard ett alternativ för att även ange filnamnet. Författare kan fritt tilldela filnamnen enligt sina önskemål. Detta kan dock leda till inkonsekvens och ett stort antal filnamn kan ses i ett stort dokumentationssystem. Som administratör kan du hindra författarna från att tilldela filnamn till de filer de skapar i systemet. För varje nytt ämne eller mappningsfil kan du välja att tilldela UUID-baserade filnamn automatiskt.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera automatiska filnamn baserat på UUID:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Boolean \(true/false\).<br> **Standardvärde**: false |

>[!NOTE]
>
> När det här alternativet är aktiverat kan författare inte ange filnamnet när de skapar ett nytt ämne eller en ny mappningsfil. Du kan skapa ett nytt ämne eller en ny mappfil från resursgränssnittet och webbredigeraren.

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)
