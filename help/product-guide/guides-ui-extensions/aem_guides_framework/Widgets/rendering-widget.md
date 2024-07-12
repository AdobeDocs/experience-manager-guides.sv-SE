---
title: Återgivningswidgetar
description: Hur återgivning fungerar i JUI-widgetar
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Återgivningswidgetar

Vi kan återge en widget genom att referera till den med hjälp av dess `id`

Om du vill återge widgeten `widget_languages` var som helst i appen kan vi använda den enkla syntaxen:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Widgetar kan också användas för att återge komplexa objekt, till exempel för att återge listan med medverkande till varje fil.
Här kan widgeten konstrueras som:

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

För att återge en lista över medverkande för varje fil skriver vi listan som:

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Här `@files` finns en lista med filobjekt som innehåller fält

```typescript
- fileName: string
- contributors: Array<String>
```
