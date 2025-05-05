---
title: Konfigurera tillåtna specialtecken
description: Lär dig konfigurera tillåtna specialtecken
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Konfigurera tillåtna specialtecken {#id20CIL600035}

I Web Editor kan du infoga vissa specialtecken som inte finns installerade. Du kan dock anpassa listan med specialtecken som författarna kan infoga i sina dokument. Om du anpassar teckenlistan skrivs standarduppsättningen med specialtecken över. Endast de specialtecken som du lägger till i konfigurationen blir tillgängliga för författarna.

Utför följande steg för att skriva över standardlistan med specialtecken:

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


**Överordnat ämne:**&#x200B;[ Anpassa Web Editor](conf-web-editor.md)
