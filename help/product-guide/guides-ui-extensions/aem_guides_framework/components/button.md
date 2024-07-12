---
title: Knapp
description: Knapp
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 0%

---

# Knapp

För att visa en knapp använder vi komponenten, button.
Knappkomponenten i JUI representerar HTML `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Detta skapar en knapp med etiketten `Yes, login`. De andra egenskaperna innehåller, men är inte begränsade till, variant, etikett och klicka.
> **_OBS!_** `on-<events>` är syntaxen för att anropa kommandona i kontrollenheterna.

Den återgivna knappen ser ut så här:

![button](imgs/yes_login_button.png "Button")
