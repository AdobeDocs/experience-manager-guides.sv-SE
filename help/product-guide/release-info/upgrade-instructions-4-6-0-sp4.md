---
title: Versionsinformation | Uppgraderingsinstruktioner för Adobe Experience Manager Guides 4.6.0 Service Pack 4
description: Lär dig hur du uppgraderar till version 4.6.0 av Service Pack 4 av Adobe Experience Manager Guides
role: Leader
exl-id: d0914e8a-7c7f-47da-9655-697f95f7d4ff
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för version 4.6.0 Service Pack 4 (april 2025)

Den här artikeln handlar om uppgraderingsinstruktioner och kompatibilitetsmatrisen för version 4.6.0 av Service Pack 4 av Adobe Experience Manager Guides.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 4.6.0 Service Pack 4](fixed-issues-4-6-0-sp4.md).

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides 4.6.0 Service Pack 4.

### Adobe Experience Manager

**4.6.0 Service Pack 4 - ej UUID**
Version 6.5 Service Pack 21, 20 och 19

**4.6.0 Service Pack 4 UUID**
Version 6.5 Service Pack 21, 20 och 19

Mer information finns i avsnittet [Tekniska krav](../install-guide/download-install-technical-requirements.md) i Installations- och konfigureringshandboken på plats.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 Service Pack 4 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.6.0 Service Pack 4 (UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | | |

*Baslinje och villkor som skapats i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.6.0 Service Pack 4 (ej UUID) | 2.8-regular-10 | 2.8-regular-10 | 1,6 | 1,6 |
| 4.6.0 Service Pack 4 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |  |  |

### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Ny mallversion för AEM Site

| Komponentversion | Webbplatsversion |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Uppgradera till version 4.6.0 av Service Pack 4 av Experience Manager Guides

Du kan enkelt uppgradera din nuvarande version av Guides till 4.6.0 Service Pack 4. Innan du fortsätter med uppgraderingen måste du tänka på följande:

- Om du använder version 4.6.0, 4.6.0 Service Pack 1 eller 4.6.0 Service Pack 3 kan du uppgradera direkt till 4.6.0 Service Pack 4.
- Om du använder version 4.4, 4.3.1 eller 4.3.0 måste du uppgradera till version 4.6.0.
- Om du använder version 4.2, 4.2.1 (programfix 4.2.1.3), 4.1 eller 4.1.x måste du uppgradera till version 4.4 innan du uppgraderar till version 4.6.0.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.x.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5 kan du läsa mer i avsnittet Uppgradera Experience Manager Guides i den produktspecifika installationsguiden för [Adobe Experience Manager Guides Help PDF archive](https://helpx.adobe.com/se/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Uppgraderingsprocessen för version 4.6.0 Service Pack 4 följer samma steg som version 4.6.0. Detaljerade instruktioner finns i [Uppgraderingsinstruktioner för de lokala versionerna](../install-guide/upgrade-xml-documentation.md) av Experience Manager Guides.
