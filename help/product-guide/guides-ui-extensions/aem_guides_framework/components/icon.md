---
title: Ikon
description: Ikon
role: User, Admin
exl-id: 5ba41c77-7329-49fc-bce5-02682261ea8e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 0%

---

# Ikon

För att visa en ikon använder vi komponenten, icon.
Textområdeskomponenten i JUI representerar HTML `<icon/>`.

Ikoner som finns på [Adobe Spectrum Icons](https://spectrum.adobe.com/page/icons/) är kompatibla med vår app.

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

![icon](./imgs/info_icon.png "Icon")
