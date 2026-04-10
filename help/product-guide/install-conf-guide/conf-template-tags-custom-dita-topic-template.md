---
title: Konfigurera anpassad ämnesmall för DITA
description: Lär dig hur du konfigurerar en anpassad ämnesmall för DITA
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '488'
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

1. [Skapa en anpassad redigeringsmall](conf-profiles.md#id1917D0EG0HJ)

1. Lägg till en anpassad mall i den globala profilen eller mappnivåprofilen enligt beskrivningen i avsnittet [Konfigurera redigeringsmallar](conf-profiles.md#id1889D0IL0Y4)


## Konfigurera anpassad sökväg till DITA-mallmapp {#id191LCF0095Z}

Med AEM Guides kan du konfigurera en mapp för lagring av dina anpassade DITA-kartor och mallar. Som standard lagras mallfilerna i följande mapp i DAM:

`/content/dam/dita-templates/`

Om du vill hantera ämne- och mappningsmallfiler finns det dedikerade mappar för att lagra ämne- och mappmallar. Som standard lagras alla ämnesmallar under `/content/dam/dita-templates/topics`

mapp. Alla mappningsmallar lagras i mappen `/content/dam/dita-templates/maps`.

Som administratör kan du välja att skapa anpassade mappnings- eller ämnesmallar i standardmappen eller skapa en egen mapp där du kan lagra egna mallar. Om du tänker använda standardmappen kan du hoppa över den här processen.

På följande flikar finns anvisningar om hur du konfigurerar en anpassad DITA-mallmappsökväg baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera en mapp för dina anpassade DITA-ämnesmallar:

>[!IMPORTANT]
>
> Du kan hoppa över den här processen om du vill använda standardmappen för att lagra egna mallar.

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Ange en plats där du vill lagra anpassade mallar.<br> Om den angivna platsen finns i DAM kopieras alla standardmappnings- och ämnesmallar till den mappen. Om platsen inte finns, skapas mappen med alla standardmallar för kartor och ämnen. |

>[!TAB Lokal]

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


>[!ENDTABS]


**Överordnat ämne:**[ Konfigurera ämne- och mappningsmallar](conf-template-tags.md)
