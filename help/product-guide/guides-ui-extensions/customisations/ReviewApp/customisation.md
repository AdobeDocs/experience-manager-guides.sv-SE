---
title: Anpassa
description: Anpassa granskningsappen
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Anpassa granskningsappen

För att göra det enklare att anpassa granskningsappen har vi tagit fram några krokar som listas och förklaras nedan:

## Review-Comment

- id: `review_comment`
- krok: `this.next('updateExtraProps')`:

Som nämndes [här](../../aem_guides_framework/basic-customisation.md) hamnar alla nya attribut som läggs till under anpassningen under `this.model.extraProps`. Med metoden `updateExtraProps` kan du lägga till attribut i en granskningskommentar och även hantera uppdateringen och lagringen av det tillagda attributet på servern.

### Exempel på användning

Du vill till exempel lägga till fält `commentRationale` och `severity` i dina kommentarer.
Låt oss uppdatera `commentRationale` till&quot;This is an important sentence.&quot; och `severity` till&quot;CRITICAL&quot;.
Detta kan göras med syntaxen:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

Ovanstående kodfragment hanterar uppdatering och sparande av värdena. De sparade värdena kan återges i användargränssnittet genom att definiera vyn.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Panelen Textbunden granskning

- id: `inline_review_panel`

1. krok: `onNewCommentEvent`
Med kroken `onNewCommentEvent` kan du utlösa en händelse eller anropa en metod för en ny kommentar eller svarshändelse.
De argument som tas emot i `onNewCommentEvent` är:
   - händelser: den kommentar/svarshändelse som skickades.
   - newComment: boolesk
Om händelsen som skickades var en ny kommentarshändelse, dvs. `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleskt
Om händelsen som skickades var en ny svarshändelse.

2. krok: `sendExtraProps`

Den här kroken är bra om du vill utöka en `event` och skicka `extraProps` från den interna granskningspanelen. Vi kommer att förklara användningen av de här två krokarna nedan.

### Exempel på intern granskningspanel

Anta att vi vill skicka en extraProp, `userInfo`, varje gång en ny kommentar eller ett nytt svar skickas. Detta görs nu via den interna granskningspanelen, men vi har inte en referens till commentId för den nyligen genererade kommentaren, och därför kan vi skriva följande kod för att uppnå detta.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

I ovanstående kodfragment kontrollerar vi om den skickade händelsen var en ny kommentar eller ett nytt svar. Om det finns en ny kommentar eller ett nytt svar anropar vi metoden `setUserInfo`

```typescript
    const getUserInfo = (userId) => {
      return $.ajax({
        url: '/bin/dxml/xmleditor/userinfo',
        data: {
          username: userId,
        },
        success: (data) => {
          return data
        }
      })
    }

    setUserInfo(event) {
      getUserInfo(event.user).done(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

I ovanstående metod utökar vi händelsen till att skicka extraProps som innehåller användarens förnamn, e-postadress, titel osv. Genom att utöka händelsen på det här sättet ser du till att extraProps skickas med rätt commentId och ser till att de bifogas till rätt kommentar.

Haken `updateExtraProps` anropar automatiskt kroken `sendExtraProps`, så när ska du använda vad?

Vi använder `updateExtraProps` i kontrollenheten `review_comment` som redan har kommentarens `id` och därför behöver du bara ange `extraProps.`

`inline_review_panel` har dock inte åtkomst till kommentarens ID. Därför kommer `sendExtraProps` att vara användbart varje gång du behöver skicka en händelse från den interna granskningspanelen.
