---
title: Widgetar
description: Om widgetar
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---


# Widgetar

Flera grundläggande komponenter, som beskrivs i avsnittet Komponenter, kan kombineras för att skapa en widget.
Widgetar kan användas för att göra en ny&quot;mer komplex&quot; komponent eller för att ge struktur åt objekt i en komponent.

Låt oss fördjupa oss i konceptet med en widget!

Vi börjar med att göra en enkel widget för att visa en lista över språk.

```js title="basicWidget.js"
const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Här, `@languages` är en array som definieras i modellen av `widget_languages` as: [&quot;English&quot;, &quot;French&quot;, &quot;Hindi&quot;, &quot;Spanish&quot;, &quot;Urdu&quot;]

Den återgivna grundläggande widgeten ser ut så här:

![basic_widget](imgs/basic_widget.png "Grundläggande widget")
