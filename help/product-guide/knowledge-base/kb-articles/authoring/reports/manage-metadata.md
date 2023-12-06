---
title: Hantera taggar för DITA-filer i AEM
description: En kort artikel om hur du hanterar cq:taggar i AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Lägga till, ta bort och hantera taggar i DITA-innehåll

Taggar kan vara användbara för att kategorisera innehållet. Om innehållet är taggat på rätt sätt kan det hjälpa dig att hitta exakta ämnen i din dagskarta och slutanvändaren hittar rätt innehåll snabbare i dina publicerade utdata

> **_OBS!_**  Följande artikel gäller AEM Guides Build 4.2 (on-prem) /Feb 2023 (cloud version) eller senare


## Skapa taggar

Taggning är en inbyggd AEM och AEM kan hjälpa dig att skapa och konfigurera dessa taggar i början.


## Lägga till, ta bort och hantera taggar i DITA-innehåll

**Alla taggar som skapas i AEM cq: -taggar kan läggas till, tas bort och hanteras för DITA-innehållet**

Du kan lägga till taggar i DITA-innehåll på flera olika sätt, men den här artikeln kommer att koncentreras till AEM webbredigeringsgränssnittet för stödlinjer.

### Steg:

1. Gå till databasvyn i gränssnittet för guider
2. Dubbelklicka på diamap och öppna i kartvyn
3. Gå till fliken Hantera
4. Gå till alternativet Metadata på fliken Hantera
5. Alla dina direkta och indirekta redigeringsfiler visas här.
6. Markera en eller flera filer och klicka på ikonen Hantera. Här kan du lägga till taggar till markerade filer.
Du kan också ta bort befintliga taggar som är gemensamma för markerade filer.

<img title="Hantera taggar i AEM " alt="Hantera taggar i DITA " src="ManageTags.jpg">

## Felsökning och vanliga frågor

### Listan i manage->metadata är tom eller ofullständig

Om listan är tom eller ofullständig kan du behöva köra indexeringen på din dimap. Du kan läsa [Uppgraderingsinstruktioner (indexera ditt innehåll)](/help/product-guide/install-guide/upgrade-xml-documentation.md#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Anpassade metadata visas inte i listan

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Andra användbara resurser

- [Masstaggning med hjälp av kartkontrollpanelen (resursgränssnittet)](/help/product-guide/user-guide/map-editor-bulk-tagging.md)
- [Ditamap-rapporter i webbredigeraren](/help/product-guide/user-guide/reports-web-editor.md)
- [Tagga i AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Kontakta respektive CSM för andra frågor**
