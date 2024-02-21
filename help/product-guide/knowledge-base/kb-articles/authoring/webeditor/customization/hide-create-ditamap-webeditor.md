---
title: Dölj alternativet Skapa DitaMap på snabbmenyn Mapp för specifika användare eller grupper.
description: Lär dig hur du anpassar webbredigeraren genom att dölja alternativet DitaMap på mappsnabbmenyn för specifika användare/grupper
source-git-commit: ea8fb646287f68676b6530b4cc5f56e7ba2d9b0c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# Visa/dölj Skapa DitaMAP på mappsnabbmenyn i webbredigeraren

I den här artikeln får vi lära oss att anpassa webbredigeraren för stödlinjer så att den döljer eller visar alternativet &quot;Create DitaMap&quot; på mappsnabbmenyn baserat på användar-/gruppbehörigheter.
I det här fallet döljer vi det här alternativet för alla användare som inte är författare.

## Krav

Vi kommer att använda paketet AEM Guides Extension som gör att du kan anpassa gränssnittet för ditt program efter dina behov.
Gå igenom det här [dokumentation](https://github.com/adobe/guides-extension/tree/main) för att få mer information om hur Guides Extension Framework fungerar.

Nu kan du komma igång och lära dig hur du anpassar mappens snabbmeny för att dölja det här alternativet för alla användare som inte är författare.

Som du kan se nedan är alternativet&quot;create DitaMap&quot; synligt för en författaranvändare.

![Visa alternativet Skapa DitaMap](../../../assets/authoring/ditamap-show-author.png)

Låt oss nu se hur vi kan dölja det här alternativet med hjälp av Guides Extension Framework.

## Implementeringssteg

Implementeringen är uppdelad i delar nedan:

- **Ändringar i Folder_options-kontrollenheten**

  Varje snabbmeny har ett kontrollenhets-ID kopplat till sig. Den här kontrollenheten hanterar funktionen vid händelse för de olika alternativen på snabbmenyn.

  I det här exemplet anpassar vi mappens snabbmeny för att dölja alternativet&quot;Create DitaMap&quot; för icke-författare. För detta kommer vi att göra ändringar i filen folder_options.ts som finns under /src i databasen med stödlinjer för tilläggsramverk.

  Vi använder &quot;viewState&quot; som &quot;REPLACE&quot; för att dölja det här alternativet från snabbmenyn.
Vi anropar en ny widget i den här mappen_options via tangenten &#39;id&#39;.

```typescript
const folderOptions = {
  id: "folder_options",
  contextMenuWidget: "repository_panel",
  view: {
    items: [
      {
        component: "widget",
        id: "customditamap",
        target: {
          key: "displayName",
          value: "DITA Map",
          viewState: VIEW_STATE.REPLACE,
        },
      },
    ],
  },
};
```

- **Skapa en ny widget för att hantera logiken**

  En ny widget (custom options.ts) behövs för att skriva logiken som döljer det här alternativet endast för användare som inte är författare. För att uppnå detta har vi använt nyckeln show som fungerar som en växlingsknapp i vår JSON-struktur.

  Du kan skriva en egen extern server för att kontrollera gruppinformationen. På så sätt kan du även anpassa mappmenyalternativ för din anpassade grupp.
I det här exemplet har vi utnyttjat anropet OTB AEM &#39;rolesapi&#39; för att hämta användarinformationen och ange svaret i &#39;isAuthor&#39; enligt ovanstående kodavsnitt.

```typescript
const folderOptions = {
  id: "customditamap",
  view: {
    component: "button",
    quiet: true,
    icon: "breakdownAdd",
    label: "DITA Map",
    "on-click": "createNewDitaMap",
    show: "@extraProps.isAuthor",
  },
};
```

Genom detta kan vi dölja knappen med etiketten&quot;Dita Map&quot; baserat på värdet för&quot;show&quot;.

Vi har lagt till en kontrollenhet för att ställa in attributet isAuthor i modellen. Detta kan göras med följande syntax i kontrollenheten.

```typescript
this.model.extraProps.set("key", value);
```

Här är nyckeln &#39;isAuthor&#39; och värdet är svaret från rolesapi-anropet.
Vi har också definierat händelsen createNewDitaMap för att aktivera alternativet create DitaMap (för författaranvändare).

```typescript
controller: {
    init: function () {
      this.model.extraProps.set("isAuthor", false);

      rolesApiResponse.then((result) => {
        console.log(result);
        this.model.extraProps.set(
          "isAuthor",
          result["/content/dam"].roles.authors
        );

        console.log("testresult" + result["/content/dam"].roles.authors);
      });
    },
    createNewDitaMap() {
      repositoryController && repositoryController.next("create_new.map");
    },
  },
```

- **Lägga till anpassad kod**

  Importera mappen_options.ts och customOptions.ts till filen index.ts under /src.

## Testning

- Logga in på AEM med en användare som inte är en del av författargruppen. Alternativet Skapa DitaMap är dolt på mappens snabbmeny enligt nedan.
Det här användningsfallet har lagts till i GIT, se relaterade resurser nedan.

![Dölj alternativet Skapa DitaMap](../../../assets/authoring/ditamap-hide-non-author.png)

### Relaterade resurser

- **Bas-databas för Extension Framework** - [GIT](https://github.com/adobe/guides-extension/tree/main)

- **Dokumentation** - [på Experience League](../../../../../guides-ui-extensions/aem_guides_framework/basic-customisation.md)

- **Dokumenterade användningsfall** - [på Experience League](../../../../../guides-ui-extensions/aem_guides_framework/jui-framework.md)

- **Offentlig databas med exempel** - [på GIT](https://github.com/adobe/guides-extension/tree/sc-expert-session). Se session mellan en filial och en expert

```

```
