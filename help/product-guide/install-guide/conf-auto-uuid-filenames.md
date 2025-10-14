---
title: Konfigurera automatiska filnamn baserat på UUID
description: Lär dig konfigurera automatiska filnamn baserat på UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Konfigurera automatiska filnamn baserat på UUID {#id205QG070D5Z}

När ett ämne eller en kartfil skapas får författare som standard ett alternativ för att även ange filnamnet. Författare kan fritt tilldela filnamnen enligt sina önskemål. Detta kan dock leda till inkonsekvens och ett stort antal filnamn kan ses i ett stort dokumentationssystem. Som administratör kan du hindra författarna från att tilldela filnamn till de filer de skapar i systemet. För varje nytt ämne eller mappningsfil kan du välja att tilldela UUID-baserade filnamn automatiskt.

Utför följande steg för att automatiskt tilldela det UUID-baserade filnamnet till alla nya filer som skapas i systemet:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet *com.adobe.fmdita.xmleditor.config.XmlEditorConfig*.

1. Välj alternativet **Använd UUID-baserade systemfilnamn**.

1. Klicka på **Spara**.


>[!NOTE]
>
> Som standard är det här alternativet inaktiverat. När det här alternativet är aktiverat kan författare inte ange filnamnet när de skapar ett nytt ämne eller en ny mappningsfil. Du kan skapa ett nytt ämne eller en ny mappfil från Assets-gränssnittet och webbredigeraren.

**Överordnat ämne:**&#x200B;[&#x200B; Konfigurera filnamn](conf-file-names.md)
