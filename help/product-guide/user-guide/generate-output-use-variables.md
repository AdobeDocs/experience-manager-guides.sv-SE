---
title: Använd variabler för att ange alternativen Målsökväg, Platssökväg, Platsnamn eller Filnamn
description: Lär dig hur du använder variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn. Ta reda på vilka variabler som finns i AEM Guides.
exl-id: 3396c971-6332-45b5-b2ef-b07f0abf97f7
feature: Publishing
role: User
source-git-commit: 358d38ca761661eaee7aeac2cc7d46c53105c543
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# Använd variabler för att ange alternativen Målsökväg, Platssökväg, Platsnamn eller Filnamn


När du genererar utdata i AEM Sites eller PDF-filer kan du använda variabler för att definiera alternativen Målsökväg, Platssökväg, AEM Platsnamn eller PDF Filnamn. Du kan använda en enda eller en kombination av variabler för att definiera dessa alternativ.

I följande tabell visas de variabler som stöds i paketet:

| Variabel | Slutgiltig målsökväg | Exempel |
| --- | --- | --- |
| `${map_filename}` | Använder DITA-mappningsfilens namn för att skapa målsökvägen. | **DITA-mappningsfilens namn**:<br>`AEMGuides.ditamap`<br><br>**Målsökvägen** har konfigurerats som:<br>`/content/output/sites/${map_filename}`<br><br>**Slutlig utdataplats**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Använder DITA-kartans titel för att skapa målsökvägen. | **DITA-mappningsfilnamn**:<br>`AEMGuides.ditamap`<br><br>**DITA-mappningstitel**:<br>`AEMGuides`<br><br>**Målsökväg** konfigurerad som:<br>`/content/output/sites/${map_title}`<br><br>**Slutlig utdataplats**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Använder förinställningsnamnet för utdata för att skapa målsökvägen. | **Namn på förinställning för utdata**:<br>`AEM Guides PDF Output`<br><br>**Namn på DITA-mappningsfil**:<br>`SampleDita.ditamap`<br><br>**Målsökväg** konfigurerad som:<br>`/content/output/sites/${preset_name}`<br><br>**Slutlig utdataplats**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Använder språkkoden där kartfilen finns för att skapa målsökvägen. | **DITA-mappningsfilens namn**:<br>`SampleDita.ditamap`<br><br>**DITA-mappningsfilens sökväg**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Målsökvägen** har konfigurerats som:<br>`/content/output/sites/${language_code}`<br><br>**Slutlig utdataplats**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Använder den fullständiga sökvägen för kartfilen för att skapa målsökvägen.Variabeln <br><br>**Obs!**:This kan inte användas för att ange AEM-webbplatsnamn eller PDF-filnamn. | **DITA-mappningsfilens namn**:<br>`SampleDita.ditamap`<br><br>**DITA-mappningsfilens sökväg**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Målsökvägen** har konfigurerats som:<br>`/content/output/sites/${map_parentpath}`<br><br>**Slutlig utdataplats**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Mappningsfilens sökväg används efter språkmappen för att skapa målsökvägen.<br><br>**Obs!**: Det går inte att använda den här variabeln för att ange AEM-webbplatsnamn eller PDF-filnamn. | **DITA-mappningsfilens namn**:<br>`SampleDita.ditamap`<br><br>**DITA-mappningsfilens sökväg**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Målsökvägen** har konfigurerats som:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Slutlig utdataplats**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Använder det aktuella serverdatumet för att skapa målsökvägen. | **DITA-mappningsfilens namn**: <br> `SampleDita.ditamap` <br><br> **Sökväg till DITA-mappningsfil:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Målsökväg** har konfigurerats som: <br> `/content/output/sites/${system_date}` <br> <br> **Slutlig utdataplats:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Använder den aktuella servertiden för att skapa målsökvägen. | **DITA-mappningsfilens namn:** <br>`SampleDita.ditamap` <br> <br> **Sökväg till DITA-mappningsfil:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Målsökväg** konfigurerad som: <br> `/content/output/sites/${system_time}`<br><br>**Slutlig utdataplats:**<br>`/content/output/sites/055612/SampleDita.html` |

Dessutom kan du använda metadata som definierats för DITA-kartan eller bokmappsfilen som variabler. Metadata finns under noden `/jcr:content/metadata` i DITA-mappnings- eller bokmappfilen. En av metadataegenskaperna som definieras i noden `/jcr:content/metadata` är till exempel `dc:title`. Du kan ange `${dc:title}` och titelvärdet används i det slutliga resultatet.
**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
