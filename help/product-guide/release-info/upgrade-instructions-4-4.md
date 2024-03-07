---
title: Versionsinformation | Uppgraderingsinstruktioner för Adobe Experience Manager Guides 4.4.0
description: Lär dig hur du uppgraderar till version 4.4.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 2209fd311ca1ad524db35633b8be22f6d303346d
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för version 4.4.0 (januari 2024)

I den här artikeln beskrivs uppgraderingsinstruktionerna och kompatibilitetsmatrisen för version 4.4.0 av Adobe Experience Manager Guides.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.4.0](../release-info/whats-new-4-4.md).

En lista över problem som har åtgärdats i den här versionen finns på [Åtgärdade problem i version 4.4.0](../release-info/fixed-issues-4-4.md).




## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides 4.4.0.

### Adobe Experience Manager

**4.4.0 Ej UUID**
Version 6.5 Service Pack 19, 18, 17

**4.4.0 UUID**
Version 6.5 Service Pack 19, 18, 17


Mer information finns i [Tekniska krav](../install-guide/download-install-technical-requirements.md) i On-Premise Installation and Configuration Guide.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.4.0 (UID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (ej UUID) | 2.7-regular-1 | 2.7-regular-1 | 1,6 | 1,6 |
| 4.4.0 (UID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Uppgradera till version 4.4.0 av Experience Manager Guides


Du kan enkelt uppgradera din nuvarande version av Guides till version 4.4.0. Innan du uppgraderar till version 4.4.0 av handboken för Experience Manager måste du tänka på följande:


- Om du använder version 4.3.1, 4.3.0 eller 4.2.1 (programfix 4.2.1.3) kan du uppgradera direkt till version 4.4.0.
- Om du använder version 4.2, 4.1 eller 4.1.x måste du uppgradera till version 4.3.1, 4.3.0 eller 4.2.1 (programfix 4.2.1.3) innan du uppgraderar till version 4.4.0.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.x.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5 kan du läsa mer i avsnittet Upgrade Experience Manager Guides i den produktspecifika installationsguiden som finns på [Adobe Experience Manager Guides hjälper PDF att arkivera](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner för de lokala versionerna](../install-guide/upgrade-xml-documentation.md) i Experience Manager Guides.

