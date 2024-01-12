---
title: Återgivningswidgetar
description: Hur återgivning fungerar i JUI-widgetar
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Återgivningswidgetar

Vi kan återge en widget genom att referera till den med dess `id`

Återge widgeten `widget_languages` var som helst i appen kan vi använda den enkla syntaxen:

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

Här `@files` är en lista med filobjekt som innehåller fält

```typescript
- fileName: string
- contributors: Array<String>
```
