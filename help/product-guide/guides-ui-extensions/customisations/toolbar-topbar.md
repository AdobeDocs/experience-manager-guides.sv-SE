---
title: Verktygsfält och verktygsfält
description: Anpassa verktygsfältet
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: 4f41609368b64415993b93be27162b069e7b2e32
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# Anpassa verktygsfältet

Om du vill anpassa `topbar` och `toolbar` använder vi ID:n `topbar` eller `toolbar` och följer samma vy, kontrollenhetsstruktur.

Nedan finns ett enkelt exempel på anpassning av verktygsfält. Här har vi tagit bort knappen `Insert Numbered List` och ersatt knappen `Insert Paragraph` med vår egen komponent med en anpassad klickhanterare.

För att komma åt funktioner som exponeras under objektet `proxy` måste vi komma åt det med hjälp av `this.proxy.getValue` låt säga för att hämta ett värde.

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
        init: function() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
