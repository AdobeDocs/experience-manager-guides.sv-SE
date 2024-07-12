---
title: Introduktion till tilläggslagringsplats
description: Katalogstruktur för AEM Guides-tilläggspaket
role: User, Admin
exl-id: 99a00b3e-a5c9-41d8-a73d-8690d587277e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Katalogstruktur för AEM Guides-tilläggspaket

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

Källkatalogen innehåller tilläggets typskript- eller javascript-filer. Filen index.ts är startpunkten för tillägget. Du kan importera alla komponenter här och exportera dem som ett enda objekt. Objektet kommer att användas av tillägget för att återge komponenterna.

### /dist

Det här är den sista byggkatalogen. Detta innehåller den slutliga JS och CSS som måste kopieras till AEM

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /json

Den här katalogen innehåller JSON för de olika vyerna. Du kan använda dessa JSON för att identifiera målen och anpassa vyn.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
