---
title: Uppgradera AEM Guides
description: Så här uppgraderar du AEM Guides
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# Uppgradera AEM Guides {#id213BD050YPH}

1. Få tillgång till din Cloud Manager Git-databas.

1. Uppdatera dox/dox.installer/pom.xml.

1. Uppdatera värdet för dox.version-variabeln till versionsinformationen som tillhandahålls av Adobe.

1. Genomför ändringarna och kör Cloud Manager pipeline för att distribuera det uppgraderade paketet.


>[!NOTE]
>
> Mer information om att använda CI/CD-pipeline finns i [Använda CI/CD-pipeline i Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html?lang=sv-SE).

## Rensa webbläsarcache

När uppgraderingen är klar måste alla användare rensa webbläsarens cache innan de kan använda den uppgraderade versionen av AEM Guides.

**Överordnat ämne:**&#x200B;[ Hämta och installera](download-install.md)
