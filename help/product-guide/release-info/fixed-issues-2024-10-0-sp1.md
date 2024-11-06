---
title: Versionsinformation | Problem i version 2024.10.0 Service Pack 1 av Adobe Experience Manager Guides har korrigerats
description: Läs mer om felkorrigeringarna i 2024.10.0 Service Pack 1 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Problem i version 2024.10.0 Service Pack 1 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av 2024.10.0 Service Pack 1 av Adobe Experience Manager Guides as a Cloud Service.

## Redigering

- Det går inte att skapa DITA-kartor på en UUID-instans när `xmleditor.uniquefilenames` är aktiverat i `XMLEditorConfig`. (21201)
- När du stänger en fil sparas inte kommentarer och etiketter som lagts till i dialogrutan **Spara ändringar och Lås upp fil** i versionshistoriken med den nya versionen. Detta gäller ett användningsfall där **Fråga efter incheckning vid stängning** eller **Fråga efter ny version vid stängning** är aktiverat i `XMLEditorConfig`. (20065)
- Dokumentläget markerat som **Klar** återgår till **Utkast** innan en ny version sparas, vilket resulterar i att läget **Klar** inte bevaras i någon dokumentversion. (2006)
- Det går inte att lägga till en PDF-fil som bildreferens i ett avsnitt i Web Editor. (21206)
- Om du väljer en DITA-fil i Assets-gränssnittet visas alternativet **Öppna i FrameMaker**, även om det är inaktiverat i konfigurationen. (20082)

## Publicering

- I utdata från PDF saknas kapitelrubriker i innehållsförteckningen, vilket leder till en felaktig hierarki. (21840)


## Förvaltning

- Resursläckor inträffar på grund av **oavslutade ResourceResolver**-fel i loggar. 18488
- När du skapar en ny eller duplicerad baslinje visas etiketterna i slumpmässig ordning. (19307)


## Baslinje

- När du har redigerat och sedan sparat en baslinje i en molnkonfiguration tar det 1 minut om baslinjen har ett stort antal ämnen eller kartor. (19558)

## Översättning

- Omvandling av kartor med Baslinje blir långsam och kan inte läsa in listan över alla associerade ämnen och kartor. (19733)