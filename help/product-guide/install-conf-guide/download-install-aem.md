---
title: Installera Adobe Experience Manager
description: Så här installerar du Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Installera Adobe Experience Manager {#id213BCI020E8}

AEM Guides är en plugin som installeras ovanpå Adobe Experience Manager. För installation av AEM krävs att du förstår vissa grundläggande AEM-koncept och rekommenderade installationsscenarier. Följande länkresurser hjälper dig att komma igång med AEM-installationen:

- [Grundläggande AEM-koncept](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Rekommenderade AEM-distributioner](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Om du använder Java 11 med AEM 6.5.x kan du råka ut för ett problem - *JDK 11 orsakar`NoClassDefFoundError`*. Se artikeln [JDK 11 orsakar NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html) för att lösa problemet.

När du har identifierat den distributionsstrategi som fungerar bäst för din organisation ska du utföra installationsprocessen enligt beskrivningen i avsnittet *[Komma igång](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* i AEM-dokumentationen.

Om du tänker uppgradera din AEM-instans måste du följa den angivna sekvensen:

1. Avinstallera AEM Guides.
1. Uppgradera din AEM-instans.
1. Installera om AEM Guides.

>[!IMPORTANT]
>
> Det finns ett antal rekommendationer för prestandaoptimering som du kan tänka dig för att förbättra systemets prestanda. Mer information finns i [Rekommendationer för prestandaoptimering](./perf-optimization-on-prem.md).
