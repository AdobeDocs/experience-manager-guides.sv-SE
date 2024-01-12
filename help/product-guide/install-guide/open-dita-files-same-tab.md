---
title: Öppna DITA-avsnitt eller DITA-kartfiler på samma flik
description: Lär dig hur du öppnar DITA-avsnitt eller kartfiler på samma flik
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Öppna DITA-avsnitt eller DITA-kartfiler på samma flik {#id223HI0P202H}

När du klickar på en länk till ett ämne eller en kartfil i vissa arbetsflöden öppnas den på en ny flik. Detta kan leda till att många flikar öppnas i webbläsaren, vilket kan påverka din produktivitet. Du kan ändra det här beteendet genom att öppna ett ämne eller en kartfil på en ny flik och tvinga det att öppnas på den aktuella fliken. Gör så här:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

1. Välj **Öppna DITA-avsnitt/karta på samma flik** alternativ.

1. Klicka **Spara**.


Den här inställningen påverkar följande platser där du kan komma åt ämne- eller mappfilerna:

- Skapa DITA-avsnitt \(i slutet av arbetsflödet när du klickar på **Öppna ämne** knapp\)

- Skapa DITA-karta \(i slutet av arbetsflödet när du klickar på **Öppna karta** knapp\)

- Fliken Ämnen i DITA-kartkonsolen

- Fliken Baslinjer i DITA-kartkonsolen

- Fliken Rapporter i DITA-kartkonsolen


**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
