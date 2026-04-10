---
title: Uppgradera AEM Guides för Cloud Service
description: Så här uppgraderar du AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: b416334318a83e882c32318bc4769d24268cdd1c
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 0%

---

# Uppgradera AEM Guides för Cloud Service {#id213BD050YPH}

Så här uppgraderar du AEM Guides:

1. Få tillgång till din Cloud Manager Git-databas.

1. Uppdatera filen `dox/dox.installer/pom.xml`.

1. Uppdatera värdet för variabeln `dox.version` till versionsinformationen från Adobe.

1. Genomför ändringarna och kör Cloud Manager pipeline för att distribuera det uppgraderade paketet.


>[!NOTE]
>
> Mer information om att använda CI/CD-pipeline finns i [Använda CI/CD-pipeline i Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Rensa webbläsarcache

När uppgraderingen är klar måste alla användare rensa webbläsarens cache innan de kan använda den uppgraderade versionen av AEM Guides.
