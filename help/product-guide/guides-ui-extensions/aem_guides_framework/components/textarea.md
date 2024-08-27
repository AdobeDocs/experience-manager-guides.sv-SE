---
title: Textområde
description: Textområde
role: User, Admin
exl-id: 4c576acc-fa6a-4c41-9b92-443ba51dc8ee
source-git-commit: 08d379acc98dac425f1c84b0ac2226b0e34f6d8b
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 0%

---

# Textfält och textområde

För att ta text som indata använder vi komponenterna, textfältet och textområdet.
Textområdeskomponenten i JUI representerar HTML `<textarea/>`.

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

Här är `on-keyup` syntaxen för att anropa kommandona i kontrollenheterna.
Detta skapar ett textArea där händelsen `submitName` anropas när du trycker på ENTER.

Det återgivna textområdet ser ut så här:

![textområde](./imgs/text_area.png "Textområde")
