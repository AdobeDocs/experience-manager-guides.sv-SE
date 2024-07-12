---
title: Anpassa appen
description: Anpassa appen
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Anpassa appen

Vår app följer en MVC-struktur (modell, vy, styrenhet)

## Modell

Modellen definierar de olika attributen och lagrar deras värden. Värdena för de olika attribut som lagras i modellen kan nås från kontrollenheten med hjälp av syntaxen

```typescript
this.getValue('attributeName')
```

För anpassning i programmet läggs alla nya attribut till under en karta i modellen.
Om du vill ange ett nytt attribut i modellen använder vi följande syntax i kontrollenheten:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

För att komma åt ett attribut som lagts till i modellen använder vi följande syntax:

```typescript
const value = this.getValue("key")
```

## Visa

Vyn definierar appens användargränssnitt. Vi använder JSON-filer för att definiera visningen av våra filer. Här definierar vi komponenterna, css (som anges i komponenternas extraklass) och återger de värden som lagras i modellen.
I vår app definieras varje vy med en JSON. JSON-objekten refereras med deras unika ID:n som kallas `id`.

## Styrenhet

Kontrollenheten används för att hantera händelser och bearbeta data. Kontrollenheten används för att hämta och skicka data från servern, det är gränssnittet mellan det som visas i användargränssnittet och lagras på serverdelen.

- Vi använder funktionen `init` för att ange värden vid initieringen.
- Om du vill lägga till en metod i kontrollenheten använder vi följande syntax:

```typescript
methodName: function(args){
    // functionality
}
```

`methodName` här fungerar som `key` som referens för metoden i JSON (vyn) eller i andra funktioner

- För att anropa en metod i kontrollenheten använder vi syntaxen

```typescript
this.next('methodName', args)
```

## Exempel

Låt oss nu använda ett enkelt exempel för att visa hur dessa tre komponenter interagerar med varandra.
Vi ska lägga till en knapp som byter etikettvärde med ett klick

### Visa exempel

Här nedan definierar vi JSON för en knapp som visar en dynamisk text som lagras i modellen under variabelnamnet `buttonLabel`.
I det här exemplet ändras etiketten när du klickar på knappen.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Exempel på modell

i det här fallet innehåller `extraProps.buttonLabel` knappens etikett

### Exempel på styrenhet

```typescript
  controller: {
    init: function (context) {
      context.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Nedanför GIF visas koden ovan i aktion
![basic_customization](imgs/basic_customisation.gif "Knappen Grundläggande anpassning")
