---
title: Inkludera @navtitle-attribut som standard
description: Lär dig hur du inkluderar @navtitle-attribut som standard
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: a3c7973868549c72e868c05a3fc6ca8bdce9bce3
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# Inkludera @navtitle-attribut som standard {#id2115BC0J0XA}

Du kan lägga till olika typer av referensfiler på en karta, till exempel avsnitt-, referens-, uppgift-, \(sub\)-kartor. De flesta av dessa filer stöder attributet `@navtitle`. Men det är inte många som använder det konsekvent. Om du vill framtvinga användning av attributet `@navtitle` i alla refererade filer på en karta kan du göra det med en enkel konfiguration.

När den är aktiverad läggs attributet `@navtitle` automatiskt till i egenskaperna för varje referensfil som du lägger till på en karta. `@navtitle` hämtar även värdet för elementet `title` i det refererade innehållet.

Så här tar du med attributet `@navtitle` som standard i referensfilens egenskaper:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator.
1. Du kan göra ändringen på global nivå eller på en mappnivåprofil. Beroende på var du vill göra den här ändringen måste du hämta respektive ui\_config.json-fil. Mer information om hur du hämtar filen ui\_config.json finns i [Konfigurera och anpassa XML-webbredigeraren](conf-folder-level.md#id2065G300O5Z).

1. Sök efter definitionen `ditaAttributes`.

   Standarddefinitionen för `ditaAttributes` är:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Ändra parametern `required` enligt nedan:

   ```
   "required": {"navtitle": true}
   ```

   Om `true` anges aktiveras knappen **Uppdatera navigeringsrubrikattribut** så att den visas i redigerarens verktygsfält. Om inställningen är `false` eller om den lämnas tom förblir knappen dold i redigeraren.
1. Spara filen.

1. Överför filen i motsvarande profil \(global eller mapp\).


Med den här konfigurationen kommer alla referensfiler som du lägger till på en karta att innehålla attributet `@navtitle` som standard.



**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](conf-web-editor.md)
