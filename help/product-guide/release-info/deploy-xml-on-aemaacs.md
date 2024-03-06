---
title: Lägga till [!DNL Experience Manager Guides] till [!DNL Experience Manager as a Cloud Service] miljö
description: Lär dig hur du lägger till [!DNL AEM Guides] till [!DNL AEM as a Cloud Service] miljö
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] as a Cloud Service driftsättning

Lär dig hur du lägger till [!DNL Experience Manager Guides] till [!DNL Experience Manager as a Cloud Service] miljö.


>[!NOTE]
>
> Från och med version 2024.2.0 är Experience Manager-stödlinjerna bara tillgängliga som ett automatiskt tillägg för Experience Manager as a Cloud Service. Om du använder manuell driftsättning för Experience Manager Guides ska du ta bort raden `<module>dox.installer</module> from file dox/pom.xml` i ditt moln hantera Git-kodbas innan du aktiverar Experience Manager-guider för ditt program.

1. Logga in på [!UICONTROL Cloud Manager].

1. Redigera programmet som du vill konfigurera [!DNL Experience Manager Guides].

1. Växla till **[!UICONTROL Solutions and Add-ons]** -fliken.

1. I **[!UICONTROL Solutions and Add-ons]** tabell, klicka på **[!UICONTROL Assets]**.

1. Välj **[!UICONTROL Guides]** och markera **[!UICONTROL Save]**.

Du har konfigurerat ditt program för automatisk etablering av Experience Manager Guides-lösningen.

![Konfigurera Experience Manager Guides Solution](assets/addon-configuration.png)

>[!NOTE]
>
>Installera [!DNL Experience Manager Guides] i alla miljöer som omfattas av det integrerade programmet måste du köra den pipeline som är kopplad till miljön. Ingen ytterligare konfiguration krävs i Git-kodbasen för CM för installation [!DNL Experience Manager Guides].
