---
title: Anpassa appen
description: Anpassa appen
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 3615928117ce1be527dc3c6d2ec8ddd115b78b0a
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Anpassa appen

## Exponerad funktionalitet i tilläggsramverket

Vi har exponerat en uppsättning funktioner och get-metoder under en `proxy` som kan användas för att komma åt data, config och utlösande händelser. Nedan finns en lista och hur du kommer åt dem.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

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
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Nedanför GIF visas koden ovan i aktion
![basic_customization](imgs/basic_customisation.gif "Knappen Grundläggande anpassning")


### Visa konfigurationsexempel

I det här fallet får vi åtkomst till söklägeshändelsen med `viewConfig` och utlöser en händelse för att uppdatera den

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Exempel på prenumeration

I det här fallet lägger vi till en prenumeration vid filnamnsändring i konsolloggen när du klickar på alternativet för filnamnsändring

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Exempel på apphändelse

I det här fallet har loggen för det aktiva dokumentet ändrats (flikar i redigerarens användargränssnitt ändras)

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Exempel på händelser i appmodell

Exempel på prenumerationshändelser för appmodell som `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Exempel på händelser för överordnad styrenhet

I det här exemplet lägger vi till en prenumeration på `tabChange`-händelsen som är en händelse för `left_panel_container`-kontrollanten som fungerar
som överordnad styrenhet för `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### Appmodell och appkontroll nästa gång

De kan aktiveras direkt genom att man vet att det är rätt händelse att utlöses och dess data

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
