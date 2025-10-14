---
title: Konfigurera Regx för giltiga filnamnstecken
description: Lär dig hur du konfigurerar Regx för giltiga filnamnstecken
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Konfigurera Regx för giltiga filnamnstecken {#id214BD0550E8}

Från och med AEM Guides 3.8 kan du som administratör definiera en lista med giltiga specialtecken som tillåts i filnamn. I tidigare versioner tilläts användare att definiera filnamn som innehåller specialtecken som `@`, `$`, `>` med flera. Specialtecknen orsakade problem när ämnen öppnades från DITA-kartpanelen eller när man klickade på länken till ett ämne i innehållsförteckningen, vilket ofta ledde till att sidan inte öppnades på grund av specialtecken i URL:en.

Med den konfiguration som gör att du kan definiera en regx för giltiga filnamnstecken har du full kontroll över hur filerna namnges internt i systemet. Du kan definiera en lista med specialtecken som tillåts i filnamnen. Som standard innehåller den giltiga filnamnskonfigurationen `a-z A-Z 0-9 - _`. När du skapar en ny fil kan du ha ett specialtecken i filens titel, men internt ersätts det med `-` i filnamnet. Du kan t.ex. ha filens namn som&quot;Introduktion 1&quot; eller&quot;Introduction@1&quot;, och motsvarande filnamn som genereras för båda dessa fall blir&quot;Introduktion-1&quot;.

När du definierar en lista med giltiga tecken måste du komma ihåg att de här tecknen `*/:[\]|#%{}?&<>"/+` alltid kommer att ersättas med `-`.

Om du inte konfigurerar den giltiga specialteckenlistan kan det hända att du får oväntade resultat när du skapar filen. För att undvika sådana fel rekommenderar vi att du gör den här konfigurationsändringen.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera regex för giltiga filnamnstecken:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | Värdet är ett regex-mönster. Den måste ha tre grundläggande tecken och listan måste börja med ett bindestreck \(-\).<br> **Standardvärde**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> På samma sätt som i listan med giltiga filnamnstecken kan du även ange en lista med giltiga filnamnstecken för AEM. Mer information finns i [Konfigurera giltiga filnamn för AEM &#x200B;](conf-file-names-valid-regx-aem-site-output.md#).

**Överordnat ämne:**&#x200B;[&#x200B; Konfigurera filnamn](conf-file-names.md)
