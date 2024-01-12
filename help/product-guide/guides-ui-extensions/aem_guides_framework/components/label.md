---
title: Etikett
description: Etikett
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 0%

---

# Etikett

Om du vill visa text eller strängar använder vi komponenten, label.
Etikettkomponenten i JUI representerar en html `<label/>`.

Nedan visas ett exempel på hur du lägger till en statisk etikett

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Under JSON visas en dynamisk sträng:

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

Den återgivna etiketten ser ut så här:

![label](./imgs/label.png "Etikett")