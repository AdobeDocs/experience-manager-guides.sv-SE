---
title: Innehållsförteckningspublicering med NativePDF
description: Publicera innehållsförteckning och andra boklistor för din digitala bokmapp med hjälp av NativePDF
feature: Native PDF Output
role: User, Admin
source-git-commit: 6ccaef5d35d492fe8dbe0f8b52af8d11258f3d2a
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Generera bokmappens innehållsförteckning i PDF

## Konfigurera din bokkarta

Inkludera `<toc>`  element: Inom bokmappens `<frontmatter>`-element, hitta `<booklists>` -element.  Kapsla en `<toc>` element inuti `<booklists>` så här:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

DITA-specifikationen tillåter montering av innehållsförteckningar och boklistor i `<backmatter>` även.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Innehållsförteckningarna och boklistorna genereras automatiskt baserat på den struktur som du har definierat i bokmappen.

När bokmappen är klar använder du PDF för att generera utdata från PDF. Den behandlar bokmappens struktur och referenser, inklusive innehållsförteckning och boklistor.

## Innehållsförteckningens design och dess ordning i PDF

Inbyggd PDF är en praktisk metod för att anpassa innehållsförteckningens layout och design.

Du kan styra designen via olika sidlayouter för innehållsförteckning och format via layout.css.

Innehållsförteckningsordningen och andra boklisteordningen i PDF baseras endast på bokmappens struktur.

![toc](../assets/publishing/toc.png)


## Vanliga frågor

- ### Inkludera en Ditamap-innehållsförteckning i en PDF

Själva Ditamaps har inte direkt en innehållsförteckning (TOC) som en bokmapp. Diffamappar spelar dock en viktig roll när det gäller att definiera strukturen för ditt innehåll och bidrar indirekt till innehållsförteckningsprocessen.

Om du publicerar Ditamap har Native PDF funktioner för att automatiskt generera innehållsförteckningar och boklistor. Du kan aktivera/inaktivera generering av innehållsförteckning på fjärrbasis från inställningarna för Native PDF.

![Aktivera Inaktivera innehållsförteckning](../assets/publishing/pageorder.png)

## Ytterligare resurser:

- [Layoutdokumentation för PDF](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Grundläggande PDF-seminarier med förinspelade experter](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Lägg upp dina frågor på AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) för alla frågor.


