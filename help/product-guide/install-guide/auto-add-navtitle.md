---
title: Inkludera @navtitle-attribut som standard
description: Lär dig hur du inkluderar @navtitle-attribut som standard
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Inkludera @navtitle-attribut som standard {#id2115BC0J0XA}

Du kan lägga till olika typer av referensfiler på en karta, till exempel avsnitt-, referens-, uppgift-, \(sub\)-kartor. De flesta av dessa filer stöder attributet `@navtitle`. Men det är inte många som använder det konsekvent. Om du vill framtvinga användning av attributet `@navtitle` i alla refererade filer på en karta kan du göra det med en enkel konfiguration.

När den är aktiverad läggs attributet `@navtitle` automatiskt till i egenskaperna för varje referensfil som du lägger till på en karta. `@navtitle` hämtar även värdet för elementet `title` i det refererade innehållet.

Så här tar du med attributet `@navtitle` som standard i referensfilens egenskaper:

1. Hämta filen ui\_config.json.

   Du kan göra ändringen på global nivå eller på en mappnivåprofil. Beroende på var du vill göra den här ändringen måste du hämta respektive ui\_config.json-fil. Mer information om hur du hämtar filen ui\_config.json finns i [Konfigurera och anpassa XML-webbredigeraren](conf-folder-level.md#id2065G300O5Z).

1. Sök efter definitionen `ditaAttributes`.

   Standarddefinitionen för `ditaAttributes` är:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Ändra parametern `required` som:

   ```json
   "required": {"navtitle": true}
   ```

1. Spara filen.

1. Överför filen i motsvarande profil \(global eller mapp\).


Med den här konfigurationen kommer alla referensfiler som du lägger till på en karta att innehålla attributet `@navtitle` som standard.
