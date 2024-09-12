---
title: Ange avancerad kartredigerare som standard
description: Lär dig hur du anger den avancerade kartredigeraren som standard
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Ange avancerad kartredigerare som standard {#id181AI0003PN}

>[!NOTE]
>
> Redigeraren för den grundläggande kartan, som tidigare fanns i Experience Manager Guides, har tagits bort från version 4.3 och 2307. Du har inte åtkomst till redigeraren för grundläggande kartor för att skapa och hantera DITA-kartor.
>Du rekommenderas att använda den avancerade kartredigeraren. Avancerad kartredigerare har förbättrade funktioner och bättre alternativ för anpassning. Läs mer om hur du arbetar med [Avancerad kartredigerare](../user-guide/map-editor-advanced-map-editor.md).

För tidigare versioner än 4.3 och 2307 har Experience Manager Guides en grundläggande kartredigerare och en avancerad kartredigerare. Med den grundläggande kartredigeraren får du alla funktioner som behövs för att skapa kartfilen. Avancerad kartredigerare har mycket fler funktioner och är integrerad i webbredigeraren. Med Advanced Map Editor kan man skapa och redigera DITA-kartfiler i ett lättanvänt gränssnitt.

När en ny kartfil skapas öppnas den som standard i den grundläggande kartredigeraren. Du kan ändra det här beteendet genom att aktivera inställningen för att öppna den avancerade kartredigeraren som standard.

Utför följande steg för att göra den avancerade kartredigeraren till standardredigerare för kartfilerna:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Välj alternativet **Dölj redigeraren för grundläggande karta**.

   När det här alternativet är markerat visas inte länken för redigeringsprogrammet för grundläggande kartor någonstans i användargränssnittet. Som standard öppnas kartfiler i Avancerad kartredigerare.
