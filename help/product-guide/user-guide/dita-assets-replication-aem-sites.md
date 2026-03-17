---
title: Hantera replikering av DITA-källresurser
description: Lär dig hur du replikerar DITA-källresurser
feature: Publishing
role: User
source-git-commit: 52921a33d30817434424772ff32b1b31d4878497
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Hantera replikering av DITA-källresurser

När utdata som genereras från DITA-innehåll publiceras med **Snabbpublicering** eller **Hantera publicering** i en publiceringsmiljö, försöker AEM även publicera associerade DITA-källresurser, som DITA-kartor och, i vissa fall, DITA-avsnitt. Detta inträffar eftersom AEM hanterar DITA-resurser som beroenden av de genererade webbplatssidorna.

![](images/quick-publish-site-instance.png){width="350" align="left"}

För att förhindra oavsiktlig replikering av DITA-innehåll till publiceringsmiljön och för att undvika prestandaproblem måste administratörer uttryckligen hantera DITA-resursreplikering via Configuration Manager. Med den här konfigurationen kan administratörer styra replikeringen av DITA-resurstyper som stöds, inklusive DITA-kartor, DITA-avsnitt, XML-filer och Markdown-filer (.md).

Om du vill konfigurera replikeringsfunktionen för DITA-resurser läser du [Konfigurera DITA-resursreplikering för Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) eller [Konfigurera DITA-resursreplikering för lokal &#x200B;](../install-guide/configure-dita-asset-replication.md) beroende på vilken konfiguration du använder

