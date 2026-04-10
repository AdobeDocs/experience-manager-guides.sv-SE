---
title: Distributions- och dispatcherkonfiguration
description: Lär dig driftsättning och konfiguration av dispatcher i Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 3%

---

# Distributions- och dispatcherkonfiguration

Den här artikeln innehåller information om hur du distribuerar Experience Manager Guides as a Cloud Service och konfigurerar dispatcher.

## Distribuera Experience Manager Guides as a Cloud Service

Du kan börja med att distribuera Experience Manager Guides via Cloud Manager. Följ instruktionerna i [AEM Guides as a Cloud Service-distributionen](../release-info/deploy-xml-on-aemaacs.md) för att distribuera modulen.

>[!NOTE]
>
> Från och med version 2024.2.0 är Experience Manager Guides endast tillgängligt som ett automatiserat tillägg för Experience Manager as a Cloud Service. Om du använder december 2023 eller tidigare versioner kan du hämta Adobe Experience Manager Guides från GitHub-databasen och installera den. Om du använder manuella distributioner för Experience Manager Guides tar du bort raden `<module>dox.installer</module> from file dox/pom.xml` i din molnhanterade Git-kodbas innan du aktiverar Experience Manager Guides för ditt program.

Så här distribuerar du Experience Manager Guides-modulen:

1. Logga in på [!UICONTROL Cloud Manager].

1. Redigera programmet som du vill konfigurera [!DNL Experience Manager Guides] för.

1. Växla till fliken **[!UICONTROL Solutions and Add-ons]**.

1. Klicka på **[!UICONTROL Solutions and Add-ons]** i tabellen **[!UICONTROL Assets]**.

1. Välj **[!UICONTROL Guides]** och välj **[!UICONTROL Save]**.

Du har konfigurerat ditt program för automatisk etablering av Experience Manager Guides-lösning.

![Konfigurerar Experience Manager Guides-lösning](assets/addon-configuration.png)

>[!NOTE]
>
>Om du vill installera [!DNL Experience Manager Guides] i någon miljö i det integrerade programmet måste du köra den pipeline som är associerad med miljön. Ingen ytterligare konfiguration krävs i CM Git-kodbasen för installation av [!DNL Experience Manager Guides].


## Konfigurera dispatcher

Dispatcher är Adobe Experience Managers verktyg för cachelagring och/eller belastningsutjämning. Mer information finns i [Dispatcher i molnet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=en).

1. Information om hur du migrerar dispatcherkonfigurationen från AMS till molntjänsten finns i [Migrera Dispatcher-konfigurationen från AMS till AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=en).
1. Mer information om hur du konfigurerar dispatcher finns i [Konfigurera Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en).

>[!NOTE]
>
> AEM as a Cloud Service stöder inte dispatcher för författarinstansen.
