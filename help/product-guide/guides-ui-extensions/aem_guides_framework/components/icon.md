---
sidebar_position: 4
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 0%

---


# Ikon

För att visa en ikon använder vi komponenten, icon.
Textområdeskomponenten i JUI representerar en html `<icon/>`.

Ikoner finns på [Adobe-spektrumikoner](https://spectrum.adobe.com/page/icons/) är kompatibla med vår app.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

ikoner kan också läggas till knappar.

Den återgivna ikonen ser ut så här:

![icon](./imgs/info_icon.png "Ikon")
