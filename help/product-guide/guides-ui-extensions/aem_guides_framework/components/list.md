---
title: Lista
description: Lista
role: User, Admin
exl-id: 333b5e24-efba-4a51-8f68-83b5d1d7daec
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 0%

---

# Lista

Vi använder komponentlistan för att visa en lista.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

Här är språk en enkel matris med strängar. `languages = ["English", "Hindi", "French"]`
Om vi vill återge en lista med objekt kan vi ange strukturen med objektkonfigurationen.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

Oftast är itemConfig en `widget`. Om du vill veta mer om widgetar går du till [widgetar](../Widgets/basic-widget.md)

Den återgivna listan ser ut så här:

![list](./imgs/list.png "List")
