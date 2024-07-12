---
title: PDF Publish-funktion | Använda JavaScript för att arbeta med innehåll eller stil
description: Lär dig hur du skapar formatmallar och skapar format för ditt innehåll.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# Använda JavaScript för att arbeta med innehåll eller stil

Med publiceringsfunktionen för PDF kan du köra JavaScript för att ändra innehåll eller format som används på innehåll innan det slutliga PDF skapas. Med den här funktionen får du fullständig kontroll över hur det slutliga resultatet genereras. Du kan till exempel lägga till juridisk information till utdata från PDF, som finns i andra PDF. Med JavaScript kan du lägga till juridisk information när PDF har skapats för basinnehållet, men innan det slutgiltiga PDF skapas.\
Som stöd för JavaScript-körning ger publiceringsfunktionen Native PDF följande återanropsfunktioner:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: Den här återanropsfunktionen körs innan innehållsförteckningen genereras.
* `window.pdfLayout.onBeforePagination(callback)`: Den här återanropsfunktionen körs efter att innehållsförteckningen har genererats, men innan sidbrytningar läggs till i PDF.
* `window.pdfLayout.onAfterPagination(callback)`: Den här återanropsfunktionen körs efter innehållsförteckningen och sidbrytningarna läggs till i PDF.

>[!NOTE]
>
>Internt underhålls en körningssekvens för dessa bildtextfunktioner. Först körs onBeforeCreateTOC, följt av onBeforePagination och slutligen körs onAfterPagination.

Beroende på vilken typ av innehåll eller formatändring du vill utföra kan du välja vilken callback-funktion som ska användas. Om du till exempel vill lägga till innehåll bör du göra det innan innehållsförteckningen genereras. Om du vill göra vissa formatuppdateringar kan de göras antingen före eller efter sidnumreringen.

I följande exempel ändras positionen för figurtitlarna från ovanför bilderna till under bilderna. Därför måste du aktivera körningsalternativet JavaScript i förinställningen. Gör så här:

1. Öppna förinställningen för redigering.
1. Gå till fliken **Avancerat**.
1. Välj alternativet **Aktivera JavaScript**.
1. Spara förinställningen och stäng den.

Skapa sedan en JavaScript-fil med följande kod och spara den i mappen Resources i mallen:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>Funktionen `window.addEventListener('DOMContentLoaded', function ()` måste anropas innan återanropsfunktionerna används.

Sedan måste skriptet anropas från en mallfil som används för att generera utdata från PDF. Vi kommer till exempel att lägga till det i innehållsförteckningsmallen. Kontrollera att taggen `<script>` läggs till i en fördefinierad `<div>` -tagg inuti taggen `<body>`. Om du lägger till det i taggen `<head>` eller utanför taggen `<body>` körs inte skriptet.

<img src="./assets/js-added-resources-template.png" width="500">

De utdata som skapas med den här koden och mallen visar figurtiteln nedanför bilden:

<img src="./assets/fig-title-below-image.png" width="500">

## Lägga till en vattenstämpel i PDF för utkast till dokument {#watermark-draft-document}

Du kan också använda JavaScript för att lägga till villkorliga vattenstämplar. Dessa vattenstämplar läggs till i dokumentet när det definierade villkoret är uppfyllt.\
Du kan t.ex. skapa en JavaScript-fil med följande kod för att skapa en vattenstämpel till utdata från PDF i dokumentet som ännu inte har godkänts. Den här vattenstämpeln visas inte om du genererar PDF för dokumentet i dokumentet Godkänt.

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

De PDF-utdata som skapas med den här koden visar en vattenstämpel, *Utkast*, på dokumentets försättssida:

<img src="./assets/draft-watermark.png" width="500">
