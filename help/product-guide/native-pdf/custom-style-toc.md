---
title: Publiceringsfunktion för PDF | Tillämpa egna format på innehållsförteckningsposter och ämnesinnehåll
description: Lär dig hur du skapar formatmallar och skapar format för ditt innehåll.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Tillämpa egna format på innehållsförteckningsposter och ämnesinnehåll

Ibland kanske du vill använda en egen formatering för innehållsförteckningsposterna eller ett visst ämne. Detta kan uppnås genom att associera en `outputclass` attributet med `<topicref>` -element på din DITA-karta. Om du vill använda ett anpassat format för ett helt ämne kan du även göra det genom att utöka attributets formatdefinition i CSS.

Låt oss ta ett exempel på ett nytt ämne som du vill skicka för granskning. För att det uppdaterade ämnet ska bli lätt att identifiera måste du lägga till en `outputclass` attributet till `<topicref>` -elementet i DITA-kartan och definiera sedan en anpassad formatering för det i CSS.

I följande exempel *Flyghistorik* har tilldelats ett `outputclass` attribut med värdet för `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

Klassdefinitionen för `new-topic` i en CSS kan du definiera formatet för följande objekt:
* Huvudposten i innehållsförteckningen eller miniinnehållsförteckningen
* Titeln på ämnet i huvudinnehållet
* Hela innehållet i ämnet, inklusive titeln

Låt oss se hur vart och ett av dessa scenarier kan definieras i CSS. I följande CSS-definition av `new-topic` -klassen har textfärgen ändrats.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Den här definitionen styr färgen på texten i innehållsförteckningen och ämnestiteln. Följande PDF-utdata visar de olika färger som används för posten i innehållsförteckningen:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

Ämnets titel är också formaterad med samma färg.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Om du vill att innehållsförteckningsposten och ämnesrubriken ska ha olika format, kan du definiera dem separat så som visas nedan:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Slutligen kan du också använda format på hela innehållet i ämnet. Därför måste du lägga till ett suffix`-content`&quot; till klassnamnet. I följande exempel har ett ändringsfält lagts till för hela innehållet i ämnet:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Med formatattributen ovan läggs ett ändringsfält till till vänster om *Flyghistorik* ämne, enligt nedan:

<img src="./assets/pdf-output-topic-content.jpg" width="500">
