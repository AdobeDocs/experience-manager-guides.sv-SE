---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, version 2026.03.0
description: Läs om kompatibilitetsmatrisen och hur du uppgraderar till version 2026.03.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: 5700e649-104d-4caf-a195-6e667a71faee
hidefromtoc: true
source-git-commit: 22ea3fe3ccb974fe3795299f7815e7aae78d41e7
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Uppgraderingsinstruktioner för version 2026.03.0

Den här artikeln handlar om uppgraderingsinstruktioner och kompatibilitetsmatrisen för version 2026.03.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2026.03.0](whats-new-2026-03-0.md).

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2026.03.0](fixed-issues-2026-03-0.md).

## Kompatibilitetsmatris

I det här avsnittet beskrivs kompatibilitetsmatrisen för de program som stöds i version 2026.03.0 av Experience Manager Guides as a Cloud Service.

### FrameMaker och FrameMaker Publishing Server

| Experience Manager Guides som Cloud-release | FMPS | FrameMaker | Syrgasförfattare |
| --- | --- | --- | --- |
| 2026.03.0 | Inte kompatibel | 2022 eller senare | 26,1 |


### Syrgasanslutning

| Experience Manager Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2026.03.0 | 3.8 -uuuid 1 | 3.8 -uuuid 1 | 2,3 | 2,3 |


### AEM Site-mallversion

| Komponentversion | Webbplatsversion |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Uppgradera till version 2026.03.0

Experience Manager Guides uppgraderas automatiskt när du uppgraderar till den senaste utgåvan av Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> Den här versionen innehåller uppdateringar av mappprofilinställningarna (ui_config.json). Om du använder anpassade inställningar bör du göra en säkerhetskopia av dessa innan du uppgraderar. Efter uppdateringen granskar och justerar du inställningarna så att de överensstämmer med ändringarna i den senaste versionen.

Granska och validera konfigurationerna för att bekräfta att de är korrekt implementerade. Om du har gjort några anpassade konfigurationsändringar kan du visa [Ytterligare konfiguration för att uppgradera Cloud Service](../cs-install-guide/additional-config-for-cloud-service.md) för ytterligare procedurer som gäller för den version du uppgraderar från.
