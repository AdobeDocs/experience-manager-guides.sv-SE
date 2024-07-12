---
title: Lägga till [!DNL Experience Manager Guides] i din [!DNL Experience Manager as a Cloud Service] miljö
description: Lär dig hur du lägger till [!DNL AEM Guides] i din [!DNL AEM as a Cloud Service] miljö
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] as a Cloud Service distribution

Lär dig hur du lägger till [!DNL Experience Manager Guides] i din [!DNL Experience Manager as a Cloud Service]-miljö.


>[!NOTE]
>
> Från och med version 2024.2.0 är Experience Manager Guides endast tillgängligt som ett automatiserat tillägg för Experience Manager as a Cloud Service. Om du använder manuella distributioner för Experience Manager Guides ska du ta bort raden `<module>dox.installer</module> from file dox/pom.xml` i din molnhanterade Git-kodbas innan du aktiverar Experience Manager Guides för ditt program.

1. Logga in på [!UICONTROL Cloud Manager].

1. Redigera programmet som du vill konfigurera [!DNL Experience Manager Guides] för.

1. Växla till fliken **[!UICONTROL Solutions and Add-ons]**.

1. Klicka på **[!UICONTROL Assets]** i tabellen **[!UICONTROL Solutions and Add-ons]**.

1. Välj **[!UICONTROL Guides]** och välj **[!UICONTROL Save]**.

Du har konfigurerat ditt program för automatisk etablering av Experience Manager Guides-lösning.

![Konfigurerar Experience Manager Guides-lösning](assets/addon-configuration.png)

>[!NOTE]
>
>Om du vill installera [!DNL Experience Manager Guides] i någon miljö i det integrerade programmet måste du köra den pipeline som är associerad med miljön. Ingen ytterligare konfiguration krävs i CM Git-kodbasen för installation av [!DNL Experience Manager Guides].
