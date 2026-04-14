---
title: Innehållsförteckningspublicering med NativePDF
description: Publicera innehållsförteckning och andra boklistor för din digitala bokmapp med hjälp av NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Generera bokmappens innehållsförteckning i PDF-publicering

## Konfigurera din bokkarta

Inkludera elementet `<toc>`:
Leta reda på `<frontmatter>` -elementet i bokmappningens `<booklists>` -element.  Kapsla in ett `<toc>`-element inuti `<booklists>` så här:

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

När bokmappen är klar kan du använda PDF för att generera PDF-utdata. Den behandlar bokmappens struktur och referenser, inklusive innehållsförteckning och boklistor.

## Innehållsförteckningsdesign och dess beställning i PDF

Inbyggda PDF-funktioner är ett praktiskt sätt att anpassa layouten och designen för innehållsförteckningen.

Du kan styra designen via olika sidlayouter för innehållsförteckning och format via layout.css.

Innehållsförteckningsordningen och andra boklistorderordningar i PDF baseras endast på bokmappens struktur.

![dec](../assets/publishing/toc.png)


## Vanliga frågor

### Inkludera en Ditamap-innehållsförteckning i en PDF

Själva Ditamaps har inte direkt en innehållsförteckning (TOC) som en bokmapp. Diffamappar spelar dock en viktig roll när det gäller att definiera strukturen för ditt innehåll och bidrar indirekt till innehållsförteckningsprocessen.

Om du publicerar Ditamap har Native PDF funktioner för att automatiskt generera innehållsförteckningar och boklistor. Du kan aktivera/inaktivera generering av innehållsförteckningar på fjärrbasis från inställningarna för Native PDF.

![Aktivera Inaktivera innehållsförteckning](../assets/publishing/pageorder.png)

## Ytterligare resurser:

- [Dokumentation för PDF designsidor](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Inbyggd PDF Essentials-session med en förinspelad expert](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Lägg upp [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) på AEM Guides Community för frågor.



