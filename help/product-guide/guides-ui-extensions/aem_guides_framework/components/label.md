---
title: Etikett
description: Etikett
role: User, Admin
exl-id: aceefb08-3198-4c3a-90ec-ac1cdde28582
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 0%

---

# Etikett

Om du vill visa text eller strängar använder vi komponenten, label.
Etikettkomponenten i JUI representerar HTML `<label/>`.

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

![label](./imgs/label.png "Label")
