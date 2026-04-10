---
title: Konfigurera tillåtna specialtecken
description: Lär dig konfigurera tillåtna specialtecken
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Konfigurera tillåtna specialtecken {#id20CIL600035}

I Web Editor kan du infoga vissa specialtecken som inte finns installerade. Du kan dock anpassa listan med specialtecken som författarna kan infoga i sina dokument. Om du anpassar teckenlistan skrivs standarduppsättningen med specialtecken över. Endast de specialtecken som du lägger till i konfigurationen blir tillgängliga för författarna.

Följande flikar innehåller instruktioner om hur du skriver över standardlistan med specialtecken baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Skapa filen `symbols.json` på följande plats i din Cloud Manager Git-databas:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Lägg till specialteckendefinitionen i filen `symbols.json` som:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


Strukturen för filen `symbols.json` förklaras nedan:

- `"label": "Arrows"`: Detta anger kategorin för specialtecknen. I fragmentet definieras en kategori med namnet `"Arrows"`.
- `"items"`: Detta definierar samlingen av specialtecken i kategorin.
- `"name": "←", "title": "Left Arrow"`: Detta är definitionen av specialtecknet. Den börjar med etiketten `"name"` som inte får ändras. Namnet följs av specialtecknet. `"title"` är namnet eller titeln på specialtecknet som visas som verktygstips för det specialtecknet.

  Du kan definiera flera definitioner av specialtecken i en kategori.

>[!TAB Lokal]

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. skapa filen `symbols.json` på följande plats:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Lägg till specialteckendefinitionen i filen `symbols.json` som:

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


Strukturen för filen `symbols.json` förklaras nedan:

- `"label": "Arrows"`: Detta anger kategorin för specialtecknen. I fragmentet definieras en kategori med namnet `"Arrows"`.
- `"items"`: Detta definierar samlingen av specialtecken i kategorin.
- `"name": "←", "title": "Left Arrow"`: Detta är definitionen av specialtecknet. Den börjar med etiketten `"name"` som inte får ändras. Namnet följs av specialtecknet. `"title"` är namnet eller titeln på specialtecknet som visas som verktygstips för det specialtecknet.

Du kan definiera flera definitioner av specialtecken i en kategori.

>[!ENDTABS]

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
