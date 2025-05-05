---
title: Konfigurera anpassad ämnesmall för DITA
description: Lär dig hur du konfigurerar en anpassad ämnesmall för DITA
exl-id: a9b2c479-7bf6-4c62-addd-fdfe74dc1f69
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# Konfigurera anpassad ämnesmall för DITA {#id16A7G0O02TD}

AEM Guides innehåller följande ämnesmallar för DITA:

- Ämne

- Uppgift

- Koncept

- Referens

- Ordlista

- Felsökning

- Tom


Du kan använda någon av de här mallarna för att skapa ämnesmallar utifrån dina redigeringskrav. Den tomma DITA-mallen innehåller inga strukturer eller element som de andra mallarna. Du kan använda mallen Tom som bas om mallen är mycket anpassad och inte baseras på några vanliga ämnesmallar i DITA.

Om du vill anpassa en ämnesmall för DITA och använda den för redigering måste du utföra följande tre huvudåtgärder:

1. *\(Valfritt\)* [Konfigurera anpassad DITA-mallmappsökväg](#id191LCF0095Z)

1. [Skapa en anpassad redigeringsmall](conf-folder-level.md#id1917D0EG0HJ)

1. Lägg till en anpassad mall i den globala profilen eller mappnivåprofilen enligt beskrivningen i avsnittet [Konfigurera redigeringsmallar](conf-folder-level.md#id1889D0IL0Y4)


## Konfigurera anpassad sökväg till DITA-mallmapp {#id191LCF0095Z}

Med AEM Guides kan du konfigurera en mapp för lagring av dina anpassade DITA-kartor och mallar. Som standard lagras mallfilerna i följande mapp i DAM:

`/content/dam/dita-templates/`

Om du vill hantera ämne- och mappningsmallfiler finns det dedikerade mappar för att lagra ämne- och mappmallar. Som standard lagras alla ämnesmallar under `/content/dam/dita-templates/topics`

mapp. Alla mappningsmallar lagras i mappen `/content/dam/dita-templates/maps`.

Som administratör kan du välja att skapa anpassade mappnings- eller ämnesmallar i standardmappen eller skapa en egen mapp där du kan lagra egna mallar. Om du tänker använda standardmappen kan du hoppa över den här processen.

Så här konfigurerar du en mapp för dina anpassade ämnesmallar i DITA:

>[!IMPORTANT]
>
> Du kan hoppa över den här processen om du vill använda standardmappen för att lagra egna mallar.

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet *com.adobe.fmdita.config.ConfigManager*.

1. Ange en plats att lagra anpassade mallar på i egenskapen **Mallar, plats**.

1. Klicka på **Spara**.


Om den angivna platsen finns i DAM kopieras alla standardmallar för kartor och ämnen till den mappen. Om platsen inte finns, skapas mappen med alla standardmallar för kartor och ämnen.

**Överordnat ämne:**&#x200B;[ Konfigurera ämne- och mappningsmallar](conf-template-tags.md)
