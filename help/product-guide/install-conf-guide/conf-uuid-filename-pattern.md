---
title: Konfigurera UUID-filnamnsmönster
description: Lär dig hur du konfigurerar filnamnsmönstret UUID
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Konfigurera UUID-filnamnsmönster

När du importerar innehåll behöver inte filnamnen baseras på UUID. I ett system som använder UUID-baserade filnamn är det obligatoriskt att referera till alla filer med deras UUID i stället för deras ursprungliga filnamn. Om en importerad fil inte har UUID-baserade filnamn kan du konfigurera systemet så att det lägger till ett UUID i filegenskapen. Detta UUID används sedan för att referera till sådana filer där UUID inte används för att namnge filerna.

## Steg för att konfigurera UUID-filnamnsmönster

Följande flikar innehåller anvisningar om hur du konfigurerar UUID-filnamnsmönster baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera filnamnsmönstret UUID:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Sträng som anger regex för UUID-filnamnsmönster. <br> Om en fil inte följer det angivna mönstret läggs ett UUID till i filens egenskap och alla referenser till filen uppdateras med filens UUID. <br> **Standardvärde**: `"^GUID-(?<id>.*)"` |

>[!TAB Lokal]

Utför följande steg för att kontrollera filnamn mot ett UUID-mönster och tilldela UUID till filer som inte har tilldelats ett UUID:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. I egenskapen **UID-filnamnsmönster** anger du ett mönster som kontrollerar den importerade filens namn.

   Om en fil inte följer det angivna mönstret läggs ett UUID till i filens egenskap och alla referenser till filen uppdateras med filens UUID.

1. Välj **Spara**.

>[!ENDTABS]





