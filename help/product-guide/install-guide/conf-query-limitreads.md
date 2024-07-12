---
title: Konfigurera antalet LimitReads för en fråga
description: Lär dig hur du konfigurerar antalet LimitReads för en fråga
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# Konfigurera antalet LimitReads för en fråga {#id231RC0HL0ID}

Utför följande steg om du vill öka antalet noder som en fråga kan läsa samtidigt:

1. Öppna Adobe Experience Manager Web Console JMX-sidan.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Sök efter och klicka på **QueryEngineSettings**.

1. Ändra attributvärdet för attributet **LimitReads**.

1. Klicka på **Spara**.


När du ökar det här attributvärdet hjälper det dig att generera rapporten för större DITA-kartor.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
