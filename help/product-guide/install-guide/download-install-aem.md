---
title: Installera Adobe Experience Manager
description: Så här installerar du Adobe Experience Manager
exl-id: 4693b102-b75a-4904-b2d5-914e774305f3
feature: Introduction, Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# Installera Adobe Experience Manager {#id213BCI020E8}

AEM Guides är en plugin som installeras ovanpå Adobe Experience Manager. För installation av AEM krävs att du förstår vissa grundläggande AEM-koncept och rekommenderade installationsscenarier. Följande länkar hjälper dig att komma igång med AEM-installationen:

- [Grundläggande AEM-koncept](https://helpx.adobe.com/se/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Rekommenderade AEM-distributioner](https://helpx.adobe.com/se/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)


>[!IMPORTANT]
>
> Om du använder Java 11 med AEM 6.5.x kan du råka ut för ett problem - *JDK 11 orsakar`NoClassDefFoundError`*. Se artikeln [JDK 11 orsakar NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html) för att lösa problemet.

När du har identifierat den distributionsstrategi som fungerar bäst för din organisation ska du utföra installationsprocessen enligt beskrivningen i avsnittet *[Komma igång](https://helpx.adobe.com/se/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* i AEM-dokumentationen.

Om du tänker uppgradera din AEM-instans måste du följa den angivna sekvensen:

1. Avinstallera AEM Guides.
1. Uppgradera din AEM-instans.
1. Installera AEM Guides.

>[!IMPORTANT]
>
> Det finns ett antal rekommendationer för prestandaoptimering som du kan tänka dig för att förbättra systemets prestanda. Mer information finns i [Rekommendationer för prestandaoptimering](download-install-recommend-perf-optimiz.md#).

**Överordnat ämne:**&#x200B;[&#x200B; Hämta och installera](download-install.md)
