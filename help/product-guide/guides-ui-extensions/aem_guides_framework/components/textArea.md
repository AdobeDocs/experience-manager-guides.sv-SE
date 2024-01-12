---
title: Textområde
description: Textområde
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 0%

---

# Textfält och textområde

För att ta text som indata använder vi komponenterna, textfältet och textområdet.
Textområdeskomponenten i JUI representerar en html `<textarea/>`.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

Här, `on-keyup` är syntaxen för att anropa kommandona i kontrollenheterna.
Detta skapar ett textArea där händelsen anropas när du trycker på Retur `submitName`

Det återgivna textområdet ser ut så här:

![textområde](./imgs/text_area.png "Textområde")
