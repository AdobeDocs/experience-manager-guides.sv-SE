---
title: Innehållsförteckningspublicering med NativePDF
description: Publicera innehållsförteckning och andra boklistor för din digitala bokmapp med hjälp av NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
source-git-commit: 7638f3634ad45bbadda64ec6e3f706cbb65d696c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Generera bokmappens innehållsförteckning i PDF

## Konfigurera din bokkarta

Inkludera elementet `<toc>`:
Leta reda på `<booklists>` -elementet i bokmappningens `<frontmatter>` -element.  Kapsla in ett `<toc>`-element inuti `<booklists>` så här:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

DITA-specifikationen tillåter även att innehållsförteckningen och boklistorna placeras i avsnittet `<backmatter>`.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Exempelstruktur för bokmappning med innehållsförteckning, illustrationslista och tabelllista i förgrunden och indexlista i bakgrunden.

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

Innehållsförteckningarna och boklistorna genereras automatiskt baserat på den struktur som du har definierat i bokmappen.

När bokmappen är klar använder du PDF för att generera utdata från PDF. Den behandlar bokmappens struktur och referenser, inklusive innehållsförteckning och boklistor.

## Innehållsförteckningens design och dess ordning i PDF

Inbyggd PDF är en praktisk metod för att anpassa innehållsförteckningens layout och design.

Du kan styra designen via olika sidlayouter för innehållsförteckning och format via layout.css.

Innehållsförteckningsordningen och andra boklisteordningen i PDF baseras endast på bokmappens struktur.

![dec](../assets/publishing/toc.png)


## Vanliga frågor

- ### Inkludera en Ditamap-innehållsförteckning i en PDF

Själva Ditamaps har inte direkt en innehållsförteckning (TOC) som en bokmapp. Diffamappar spelar dock en viktig roll när det gäller att definiera strukturen för ditt innehåll och bidrar indirekt till innehållsförteckningsprocessen.

Om du publicerar Ditamap har Native PDF funktioner för att automatiskt generera innehållsförteckningar och boklistor. Du kan aktivera/inaktivera generering av innehållsförteckning på fjärrbasis från inställningarna för Native PDF.

![Aktivera Inaktivera innehållsförteckning](../assets/publishing/pageorder.png)

## Ytterligare resurser:

- [Dokumentation för layout för PDF-design](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Grundläggande PDF-sessioner med förinspelade experter](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Post på AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) för alla frågor.



