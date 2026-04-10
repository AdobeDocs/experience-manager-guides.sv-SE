---
title: Konfigurationsåsidosättningar för Cloud Service
description: Lär dig hur du åsidosätter konfigurationer
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Konfigurationsåsidosättningar för Cloud Service {#id216IFC003XA}

Följande allmänna tillvägagångssätt bör användas för att göra konfigurationsuppdateringar i Experience Manager Guides as a Cloud Service:

1. Få tillgång till din Cloud Manager Git-databas.

1. Skapa en ny JSON-fil på följande plats:

   `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1. Namnge filen i följande format:

   `$\{PID\}.cfg.json`

   Här är PID:t process-ID:t för konfigurationen.

1. Lägg till egenskaper i JSON-filen i följande format:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Genomför ändringarna och kör Cloud Manager pipeline för att distribuera den uppdaterade konfigurationen.

