---
title: Konfigurera Regx för giltiga filnamnstecken
description: Lär dig hur du konfigurerar Regx för giltiga filnamnstecken
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Konfigurera Regx för giltiga filnamnstecken {#id214BD0550E8}

Från och med AEM Guides 3.8 kan du som administratör definiera en lista med giltiga specialtecken som tillåts i filnamn. I tidigare versioner tilläts användare att definiera filnamn som innehåller specialtecken som `@`, `$`, `>` med flera. Specialtecknen orsakade problem när ämnen öppnades från DITA Map Dashboard eller när man klickade på länken till ett ämne i innehållsförteckningen, vilket ofta ledde till att sidan inte öppnades på grund av specialtecken i URL:en.

Med den konfiguration som gör att du kan definiera en regx för giltiga filnamnstecken har du full kontroll över hur filerna namnges internt i systemet. Du kan definiera en lista med specialtecken som tillåts i filnamnen. Som standard innehåller den giltiga filnamnskonfigurationen `a-z A-Z 0-9 - _`. När du skapar en ny fil kan du ha ett specialtecken i filens titel, men internt ersätts det med `-` i filnamnet. Du kan t.ex. ha filens namn som&quot;Introduktion 1&quot; eller&quot;Introduction@1&quot;, och motsvarande filnamn som genereras för båda dessa fall blir&quot;Introduktion-1&quot;.

När du definierar en lista med giltiga tecken måste du komma ihåg att de här tecknen `*/:[\]|#%{}?&<>"/+` alltid kommer att ersättas med `-`.

Om du inte konfigurerar den giltiga specialteckenlistan kan det hända att du får oväntade resultat när du skapar filen. För att undvika sådana fel rekommenderar vi att du gör den här konfigurationsändringen omedelbart efter att du har uppgraderat din version till 3.8.

Så här konfigurerar du regx för giltiga \(eller tillåtna\) tecken i filnamn:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet *com.adobe.fmdita.config.ConfigManager*.

1. Kontrollera att egenskapen är inställd på \[-a-zA-Z0-9\_] i egenskapen **Regex för giltiga tecken**. Du kan lägga till fler tecken i den här listan, men den måste innehålla dessa grundläggande tecken och listan måste börja med ett bindestreck &quot;-&quot;.

   >[!NOTE]
   >
   > Den här egenskapen gäller bara för filnamn, inte för mappnamn.

1. Klicka på **Spara**.


>[!NOTE]
>
> På samma sätt som i listan med giltiga filnamnstecken kan du även ange en lista med giltiga filnamnstecken för AEM. Mer information finns i [Konfigurera giltiga filnamn för AEM ](conf-file-names-valid-regx-aem-site-output.md#).

**Överordnat ämne:**[ Konfigurera filnamn](conf-file-names.md)
