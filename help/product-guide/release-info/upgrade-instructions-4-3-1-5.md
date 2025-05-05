---
title: Versionsinformation | Uppgraderingsinstruktioner för Adobe Experience Manager Guides 4.3.1.5
description: Lär dig hur du uppgraderar till version 4.3.1.5 av Adobe Experience Manager Guides
role: Leader
exl-id: 856970ef-9f50-4452-b589-ba1f5ee73322
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för version 4.3.1.5

I den här artikeln beskrivs uppgraderingsinstruktionerna och kompatibilitetsmatrisen för version 4.3.1.5 av Adobe Experience Manager Guides.


En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 4.3.1.5](../release-info/fixed-issues-4-3-1-5.md).




## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i Experience Manager Guides 4.3.1.5.

### Adobe Experience Manager

**4.3.1.5 Ej UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

**4.3.1.5 UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

Mer information finns i avsnittet *Tekniska krav* i Installations- och konfigureringshandboken på plats.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1.5 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.3.1.5 (UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.3.1.5 (ej UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.1.5 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Uppgradera till version 4.3.1.5 av Experience Manager Guides


Du kan enkelt uppgradera din nuvarande version av Guides till version 4.3.1.5. Innan du uppgraderar till version 4.3.1.5 av Experience Manager Guides måste du tänka på följande:


- Om du använder version 4.3.1 eller 4.3.1.x kan du uppgradera direkt till version 4.3.1.5.
- Om du använder version 4.3.0 eller 4.2 (programfix 4.2.1.3) måste du uppgradera till version 4.3.1 innan du uppgraderar till version 4.3.1.5.

- Om du använder version 4.1 eller 4.1.x måste du uppgradera till version 4.3.1 innan du uppgraderar till version 4.3.1.5.


- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.x.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5 kan du läsa mer i avsnittet Uppgradera Experience Manager Guides i den produktspecifika installationsguiden som finns i [Adobe Experience Manager Guides Help PDF archive](https://helpx.adobe.com/se/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner för de lokala versionerna](../install-guide/upgrade-xml-documentation.md) av Experience Manager Guides.
