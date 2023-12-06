---
title: Konfigurationsåsidosättningar
description: Lär dig hur du åsidosätter konfigurationer
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 0%

---

# Konfigurationsåsidosättningar {#id216IFC003XA}

Följande allmänna tillvägagångssätt bör användas för att göra konfigurationsuppdateringar:

1. Gå till din Cloud Managers Git-databas.

1. Skapa en ny JSON-fil på följande plats:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Namnge filen i följande format:

   $\{PID\}.cfg.json

   Här är PID:t process-ID:t för konfigurationen.

1. Lägg till egenskaper i JSON-filen i följande format:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Genomför ändringarna och kör molnhanterarens pipeline för att distribuera den uppdaterade konfigurationen.


**Överordnat ämne:**[ Hämta och installera](download-install.md)
