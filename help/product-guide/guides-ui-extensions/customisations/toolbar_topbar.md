---
sidebar_position: 3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 0%

---


# Anpassa verktygsfältet

Anpassa `topbar` och `toolbar`kommer vi att använda ID:n: `topbar` eller `toolbar`och följer samma vy, kontrollenhetsstruktur.

Nedan finns ett enkelt exempel på anpassning av verktygsfält. Här har vi tagit bort `Insert Numbered List` och ersatte `Insert Paragraph` med vår egen komponent med en anpassad klickhanterare.

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

