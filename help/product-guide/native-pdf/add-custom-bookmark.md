---
title: PDF Publish-funktion | Lägga till ett eget bokmärke i utdata från PDF
description: Lär dig hur du skapar formatmallar och skapar format för ditt innehåll.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Lägga till ett eget bokmärke i utdata från PDF

Vanligtvis återges innehållsförteckningen i en DITA-karta som bokmärken i den slutliga utskriften för PDF. Innehållsförteckningen skapas utifrån avsnittet eller avsnittsrubrikerna på din DITA-karta. Ibland kanske du vill lägga till ett eget bokmärke för ett visst innehåll i utdata från PDF för enkel navigering. Detta kan uppnås genom att lägga till ett `outputclass`-attribut i elementet och tillämpa följande attribut på det:

`bookmark-level: 3`

Här är `bookmark-level` ett attribut och nummer `3` är det värde som anger nivån i bokmärkeshierarkin där bokmärket läggs till. I följande exempel innehåller ämnet Kontakter på första nivån en tabell, Kontaktlista, där vi har lagt till ett `outputclass`-attribut med värdet `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

Följande definition av klassen `custom-bookmark` har lagts till i CSS-filen:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

I utdata från PDF läggs tabellen *Kontaktlista* till på den andra nivån i PDF-bokmärkeslistan enligt nedan:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>Du måste välja rätt nivå där det anpassade bokmärket ska läggas till. Om du anger ett tal som är mindre än det överordnade objektets bokmärke, får det anpassade bokmärket det överordnade bokmärkets position och alla andra bokmärken visas som underordnade. Detta kan leda till oväntad bokmärkesstruktur.
