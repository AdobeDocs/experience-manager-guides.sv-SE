---
title: Verktygsfält och verktygsfält
description: Anpassa verktygsfältet
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---

# Anpassa verktygsfältet

Om du vill anpassa `topbar` och `toolbar` använder vi ID:n `topbar` eller `toolbar` och följer samma vy, kontrollenhetsstruktur.

Nedan finns ett enkelt exempel på anpassning av verktygsfält. Här har vi tagit bort knappen `Insert Numbered List` och ersatt knappen `Insert Paragraph` med vår egen komponent med en anpassad klickhanterare.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {

        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
