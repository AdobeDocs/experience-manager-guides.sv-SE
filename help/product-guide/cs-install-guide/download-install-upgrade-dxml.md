---
title: AEM
description: Lär dig hur du uppgraderar AEM
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# AEM {#id213BD050YPH}

1. Gå till din Cloud Managers Git-databas.

1. Uppdatera dox/dox.installer/pom.xml.

1. Uppdatera värdet för dox.version-variabeln till versionsinformationen som tillhandahålls av Adobe.

1. Genomför ändringarna och kör Cloud Manager-pipeline för att distribuera det uppgraderade paketet.


>[!NOTE]
>
> Mer information om att använda CI/CD-pipeline finns i [Använda CI/CD-pipeline i Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Rensa webbläsarcache

När uppgraderingen är klar måste alla användare rensa webbläsarens cache innan de kan använda den uppgraderade versionen av AEM.

**Överordnat ämne:**[ Hämta och installera](download-install.md)
