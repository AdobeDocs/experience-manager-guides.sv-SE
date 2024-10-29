---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 4.6.1 har åtgärdats
description: Läs mer om felkorrigeringarna i version 4.6.1 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 3547eb43977f31dae297ca5cb1f1ab53f7f2b067
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---


# Åtgärdade problem i version 4.6.1 (oktober 2024)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 4.6.1 av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 4.6.1](upgrade-instructions-4-6-1.md).

## Redigering

- Det går inte att skapa DITA-kartor på en UUID-instans när `xmleditor.uniquefilenames` är aktiverat i `XMLEditorConfig`. (21201)
- När du stänger en fil sparas inte kommentarer och etiketter som lagts till i dialogrutan **Spara ändringar och Lås upp fil** i versionshistoriken med den nya versionen. Detta gäller ett användningsfall där **Fråga efter incheckning vid stängning** eller **Fråga efter ny version vid stängning** är aktiverat i `XMLEditorConfig`. (20065)
- Dokumentläget som är markerat som **Klar** återgår till **Utkast** innan en ny version sparas, vilket resulterar i att läget **Klar** inte bevaras i någon dokumentversion. (2006)
- Det går inte att lägga till en PDF-fil som bildreferens i ett avsnitt i Web Editor. (21206)
- Om du väljer en DITA-fil i Assets-gränssnittet visas alternativet **Öppna i FrameMaker**, även om det är inaktiverat i konfigurationen. (20082)


## Publicering

- Det går inte att överföra bifogade filer till Salesforce om sökvägen för bifogade filer överskrider den tillåtna längden. (19420)
- När du publicerar ett ämne på Salesforce går det inte att lösa fillänkarna i PDF. (19304)
- Felet `DUPLICATE_VALUE` inträffar då och då vid försök att publicera om en befintlig artikel i Salesforce. 17932
- I utdata från PDF saknas kapitelrubriker i innehållsförteckningen, vilket leder till en felaktig hierarki. (21840)
- När du publicerar AEM Sites är det bara ett begränsat antal attribut som kan tas med i innehållsförteckningen. 7483

## Förvaltning

- Resursläckor inträffar på grund av oavslutade **ResourceResolver**-fel i loggar. 18488
- När du skapar en ny eller duplicerad baslinje visas etiketterna i slumpmässig ordning. (19307)









