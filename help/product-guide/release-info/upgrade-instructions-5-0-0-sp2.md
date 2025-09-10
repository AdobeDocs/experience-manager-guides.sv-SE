---
title: Versionsinformation | Uppgraderingsinstruktioner för Adobe Experience Manager Guides 5.0.0 Service Pack 2
description: Läs mer om kompatibilitetsmatrisen och hur du uppgraderar till version 5.0.0 Service Pack 2 av Adobe Experience Manager Guides.
source-git-commit: b5b4c5484593a2f7d9121da1c7bfb28dd2c36a57
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för version 5.0.0 Service Pack 2 (september 2025)

Den här artikeln handlar om uppgraderingsinstruktioner och kompatibilitetsmatrisen för version 5.0.0 Service Pack 2 av Adobe Experience Manager Guides.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 5.0.0 Service Pack 2](../release-info/fixed-issues-5-0-0-sp2.md).

## Kompatibilitetsmatris

I det här avsnittet listas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides 5.0.0 Service Pack 2.

### Adobe Experience Manager

**5.0.0 Service Pack 2 UUID**

Version 6.5 Service Pack 22, Service Pack 21 och Service Pack 20

Mer information finns i avsnittet [Tekniska krav](../install-guide/download-install-technical-requirements.md) i Installations- och konfigureringshandboken på plats.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS | FM |
| --- | --- | --- |
| 5.0.0 Service Pack 2 (UUID) | Stöds | 2022 eller senare |

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 5.0.0 Service Pack 2 (UUID) | 3.7-uuid.2 | 3.7-uuid.2 | 2,3 | 2,3 |

### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Ny mallversion för AEM Site


| Komponentversion | Webbplatsversion |
|---|---|
| guides-components.all-1.3.0 | aemg-docs.all-1.2.0 |


## Uppgradera till version 5.0.0 av Service Pack 2 av Experience Manager Guides

Du kan enkelt uppgradera din nuvarande version av Guides till version 5.0.0 Service Pack 2. Innan du uppgraderar till version 5.0.0 Service Pack 2 av Experience Manager Guides måste du tänka på följande:

- Om du använder version 5.0.0 Service Pack 1 eller 5.0.0 kan du uppgradera direkt till version 5.0.0 Service Pack 2.
- Om du använder version 5.0.0 kan du uppgradera direkt till 5.0.0 Service Pack 1.
- Om du använder version 4.6.x kan du uppgradera direkt till version 5.0.0.
- Om du använder version 4.3.x, 4.2, 4.2.1 (programfix 4.2.1.3), 4.1 eller 4.1.x måste du uppgradera till version 4.4 innan du uppgraderar till version 5.0.0.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.x.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5 kan du läsa mer i avsnittet Uppgradera Experience Manager Guides i den produktspecifika installationsguiden för [Adobe Experience Manager Guides Help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner för de lokala versionerna](../install-guide/upgrade-xml-documentation.md) av Experience Manager Guides.
