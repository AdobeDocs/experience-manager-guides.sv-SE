---
title: Jui Framework
description: Förstå Jui Framework
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# Jui Framework

Innan vi går in på hur vi skriver tillägg kommer vi att förstå ramverkets arkitektur.
Så att vi kan utöka den effektivt.

## Introduktion

JUI är ett MVC-ramverk ovanpå komponenterna React och Adobe React Spectrum. JUI är JSON-användargränssnittet. Det består av flera Git-databaser.

JUI-Core är huvudbiblioteket med all logik för att konvertera JSON-konfigurationen till fungerande reaktionskomponenter och länka den till en relevant instans i kontrollenhetsklassen.
JUI-React-Spectrum  biblioteket har wrapper-widgetar för Adobe React Spectrum-komponenter

## JUI Core Design

### MVC UI Design

![JUI MVC-flöde](./imgs/jui-mvc-flow.png)

### Widget

- Har ett unikt ID.
- Har en enskild JSON-fil för visning.
- Kan ha en egen eller delad styrenhet.
- Kan använda överordnad modell eller ny modell.
- Kan innehålla gränssnittselement (React Components)
- Kan ha andra widgetar
- Appen är en widget

![JUI-widget](./imgs/jui-widget.png)

### Element

- Är en HTML/React-komponent.
- Har ingen modell, använder den överordnade widgetmodellen.

### Händelsehanterare

- Next(eventOpts)
   - Så här utlöser du en händelse med vissa punkter
- Prenumerera (återanrop)
   - Få ett meddelande om att händelsen utlöses med konfigurationen

### App/global modell

- Nästa (nytt värde)
   - Publicera nytt värde
- Prenumerera (återanrop)
   - För att få meddelanden om ändrat värde
   - Första gången du får gammalt värde
- GetValue()
   - Hämta aktuellt värde

### Styrenhet

- Den ska utökas från klassen Controller
- API:er
- CreateModel
   - Skapa en separat modell för underordnad widget
- InitEventHandler
   - Skapa en separat händelsehanterare för en underordnad widget
- RegisterCommands
   - Registrera lokala händelser, överordnade händelser eller programhändelser
- Next(eventName, eventHandler)
   - Utlösa en händelse för händelsehanteraren för den underordnade widgeten, händelsehanteraren för den överordnade widgeten eller händelsehanteraren app
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Exempel på appdesign

![Exempelapp](./imgs/jui-sample-app.png)
