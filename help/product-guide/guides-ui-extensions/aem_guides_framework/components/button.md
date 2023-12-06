---
sidebar_position: 1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 0%

---


# Knapp

För att visa en knapp använder vi komponenten, button.
Knappkomponenten i JUI representerar en html `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Då skapas en knapp med etiketten `Yes, login`. De andra egenskaperna innehåller, men är inte begränsade till, variant, etikett och klicka.
> **_OBS!_**  The `on-<events>` är syntaxen för att anropa kommandona i kontrollenheterna.

Den återgivna knappen ser ut så här:

![knapp](imgs/yes_login_button.png "Knapp")
