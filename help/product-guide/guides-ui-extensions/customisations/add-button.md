---
title: Enkel anpassning
description: Exempel på enkel anpassning
role: User, Admin
exl-id: 7f19f0b0-2a1b-4a8b-b28c-3918a1bc9096
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Exempel på enkel anpassning

Låt oss nu se hur vi kan integrera dessa anpassningar i vår AEM Guides-app.

Vi vill lägga till den här knappen i en befintlig vy av appen.
Därför behöver vi tre grundläggande saker:

1. `id` för den vy-JSON som vi vill lägga till komponenten i.
2. `target`, d.v.s. platsen i JSON som den nya komponenten ska läggas till i. `target` definieras med en `key` och `value`. Nyckel-värde-paret kan vara vilket attribut som helst som används för att definiera komponenten som kan hjälpa till att identifiera den unikt.
Vi kan också använda index för att referera till målet.
Vi har tre viewState: `APPEND`, `PREPEND`, `REPLACE`.
3. JSON för den nyskapade komponenten och motsvarande metoder.

Säg att vi vill lägga till en knapp i anteckningsverktygslådan som används vid granskningen, som öppnar filen i AEM.

```typescript
export default {
  id: 'annotation_toolbox', 
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'Open topic in Assets view',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND

        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
        const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
        const {allTopics = {}} = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
        tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

I exemplet ovan har vi:

1. `id` för den JSON som vi vill infoga vår komponent i, dvs. `annotation_toolbox`
2. målet är knappen `addcomment`. Vi lägger till knappen efter knappen `addcomment` med viewState `append`.
3. Vi definierar händelsen on-click för knappen i kontrollenheten.

JSON för &quot;annotation_toolbox&quot; `.src/jsons/review_app/annotation_toolbox.json`

Före anpassning såg anteckningsverktygslådan ut så här:

![anteckningsverktygslådan](imgs/annotation_toolbox.png "Anteckningsverktygslådan")

Efter anpassningen ser anteckningsverktygslådan ut så här:

![anpassad-annotation-toolbox](imgs/customised_annotation_toolbox.png "Anpassad anteckningsverktygslåda")

## Lägga till CSS

För att uppnå enhetlighet tillhandahåller vi den komponent som redan är formaterad. Den infogade JSON-filen kommer att ha inbyggda format
Det primära sättet att hantera css är genom extraClass-nyckeln i tilläggen.

```js
{    
    "view":{
        items:[
            {
                compoenent:"button",
                extraClass:"underline bg-red",
            }
        ]
    }
}
```

Du kan lägga till anpassade format med CSS-klasser genom att lägga till en CSS-fil i klientlibs. Under bygget skapar vi också [Tailwind](https://tailwindcss.com/docs/utility-first)-utdata för verktygsklasserna i tailwind. Konfigurationen för samma sak finns på tilläggets `tailwind.config.js` vid `./tailwind.config.js`
