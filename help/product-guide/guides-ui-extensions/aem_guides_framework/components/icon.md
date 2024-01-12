---
title: Ikon
description: Ikon
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '49'
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
