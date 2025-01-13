---
title: Versionsinformation | Korrigerade problem i version 2024.12.0 av Adobe Experience Manager Guides
description: Läs mer om felkorrigeringarna i version 2024.12.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Problem i version 2024.12.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2024.12.0 av Adobe Experience Manager Guides as a Cloud Service.

Läs mer om [uppgraderingsinstruktioner för version 2024.12.0](./upgrade-instructions-2024-12-0.md).

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

- Om baslinjen har ett stort antal ämnen eller kartor kan du redigera och sedan spara en baslinje i en molnkonfiguration efter 1 minut. (19558)

## Översättning

- Omvandling av kartor med baslinje blir långsam och kan inte läsa in listan över alla associerade ämnen och kartor. (19733)
