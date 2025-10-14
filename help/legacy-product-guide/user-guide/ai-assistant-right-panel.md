---
title: Använd AI-assistenten för att skapa dokument smart `
description: Lär dig hur du använder AI Assistant för att skapa dokument på ett smart sätt i Web Editor.
hide: true
exl-id: c7d37da8-e838-47a2-b469-287bcd841933
source-git-commit: 8659035c57ce2b6f760b342fa9d88d656fcabf23
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 0%

---

# AI Assistant för att skapa dokument med smart effektivitet

Experience Manager Guides har ett AI Assistant-verktyg som hjälper dig att skapa smartare och snabbare. Ni får en förenklad dokumenthantering genom intelligenta förslag och optimering. Använd det här verktyget för att visa de smarta förslagen för att återanvända innehållet från den befintliga innehållsdatabasen. Använd textpromptfunktionen för att få en fråga och ändra innehållet eller generera utdata enligt dina önskemål. Använd AI Assistant för att konvertera ett stycke till en lista på ett smart sätt. Du kan skapa en kort beskrivning av det aktuella ämnet. Den här funktionen hjälper dig även att enkelt förbättra och översätta det markerade innehållet.


>[!NOTE]
>
> Om du vill lägga till AI-assistentfunktionen på den högra panelen måste systemadministratören markera alternativet **AI-assistenten** på fliken **Paneler** i ikonen för **Workspace-inställningar** ![Workspace-inställningar](./images/editor_settings_icon.svg) .
> > Du måste även checka ut dokumentet för att visa AI Assistant-ikonen.

Den här funktionen är endast tillgänglig för DITA-avsnitt. När du har markerat texten i ett ämne kan du välja att utföra någon av AI-assistentåtgärderna:

![ai-assistent](./images/ai-assistant-panel.png)



## Föreslå återanvändbart innehåll


Använd funktionen **Föreslå återanvändbart innehåll** ![ai föreslår återanvändbar innehållsikon ](./images/ai-suggest-reusable-content-icon.svg) för att skapa innehåll på ett konsekvent och korrekt sätt. Du kan markera innehållet och Experience Manager Guides ger förslag på hur du kan återanvända det befintliga innehållet i din databas.
Läs mer om hur du använder [AI-baserade smarta förslag för att skapa innehåll](authoring-ai-based-smart-suggestions.md).





## Använd textfråga


En textprompt är en instruktion, fråga eller programsats som hjälper AI-assistenten att generera ett specifikt svar eller utdata.

Du kan använda en textprompt för att ändra innehållet och generera utdata.  Du kan till exempel generera en sammanfattning av funktionerna i en produkt och använda den i rapporten för att visa upp produkten. Du kan också använda den här funktionen för att jämföra två produkter. Du kan till exempel även skapa en jämförelsetabell för funktionerna i två produkter.


1. Markera den text som du vill använda textprompten för.
1. Välj **Använd textprompt** ![Använd textpromptikonen](./images/ai-use-text-prompt.svg) på **AI-assistentpanelen**.
1. Gör en fråga på något av följande sätt:

   - Välj en fråga bland de föreslagna uppmaningarna.
   - Granska eller redigera en föreslagen fråga för att skapa en anpassad fråga enligt dina önskemål.

     >[!NOTE]
     >
     > De föreslagna uppmaningarna har konfigurerats i `ui_config.json` av din administratör.

   - Skriv uppmaningen i textrutan.


1. Välj **Återskapa** ![Återskapa ikon](./images/refresh-icon.svg) för ytterligare svar eller utdata baserat på uppmaningen, som AI-verktygen.

1. (Valfritt) Välj **Expandera** ![tillägg](./images/expand-icon.svg) för att öppna redigeraren för **Använd textprompt**. Den visar det aktuella och det genererade innehållet. Du kan redigera innehållet i källayouten och kontrollera förhandsvisningen.


   >[!NOTE]
   >
   > Svaren genereras baserat på det valda innehållet.



1. Du kan också redigera uppmaningen i redigeraren och generera om svaret. Du kan till exempel ändra uppmaningen så att texten blir mer kortfattad till ungefär 40 ord.

   ![AI-textredigerare](./images/ai-assisstant-text-prompt.png)

1. Du kan verifiera källan för det genererade innehållet och redigera den om det behövs.

1. Välj **Acceptera** om du vill ersätta det markerade innehållet i ämnet med det genererade innehållet.
1. **Avbryt**: Avbryter textpromptåtgärden. Återgår till panelens ursprungliga läge.

   >[!NOTE]
   >
   > Om du väljer ikonen **Avbryt** på funktionspanelen återgår du även till det ursprungliga läget.

## Förbättra innehållet


Förbättrar det markerade innehållet. Kontrollera stavning, språk och grammatisk struktur och föreslå en bättre version av innehållet. Det förbättrar också meningens kvalitet.

1. Markera innehållet.
1. Välj **Förbättra innehåll** ![Förbättra innehåll-ikonen](./images/ai-improve-icon.svg) om du vill hitta förslag på det förbättrade innehållet.
1. Välj **Återskapa** om du vill ha ett annat förslag på förbättrat innehåll.

1. (Valfritt) Välj **Expandera** för att öppna den förbättrade innehållsredigeraren. Den visar aktuellt och genererat innehåll. Du kan redigera innehållet i källayouten och även kontrollera förhandsvisningen.



![AI-assistenten förbättrar innehållsredigeraren](./images/ai-assisstant-improve-content.png)

Acceptera förslaget, eller återskapa för ett annat svar, eller avbryt åtgärden för att gå tillbaka till föregående läge.





## Skapa kortkommandon

Skapa en kort beskrivning av ämnet baserat på det valda innehållet med ca 30-50 ord. Den korta beskrivningen hjälper användarna att söka efter och hitta relevant innehåll.
Du kan till exempel lista systemkraven och generera en kort beskrivning utifrån detta.



1. Markera innehållet.
1. Välj **Skapa genvägar** ![ai skapa kort beskrivningsikon](./images/ai-create-shortdesc-icon.svg) om du vill skapa en kort beskrivning av det aktuella ämnet.
1. Välj **Acceptera** om du vill skapa en ny kort beskrivning om den korta beskrivningen inte redan finns. Om det finns en kort beskrivning måste du bekräfta den innan du ersätter den med den nya korta beskrivningen.

Du kan även utföra följande åtgärder:

- Välj **Generera om** om du vill generera en annan kort beskrivning av ämnet, som AI-verktygen.
- Välj **Expandera** för att öppna redigeraren för **Skapa genvägar**.

![ai-assistenten skapar en kort beskrivningsredigerare](./images/ai-assistant-create-short-desc.png)




## Specificera innehåll

Med den här funktionen konverteras ett markerat stycke till en lista på ett intelligent sätt.  Innehållet analyseras och en logisk lista med objekt skapas. Du behöver inte skapa objekten manuellt. Om du t.ex. har ett stycke med information om stegen för att skapa ett användarkonto, kan verktyget omvandla detta till en stegvis lista, vilket eliminerar behovet av att manuellt skapa objekten en i taget.

![Ikon för att specificera innehåll i en hjälpfunktion](./images/ai-assisstant-itemise-content.png)



1. Markera innehållet.
1. Välj **Specificera innehåll** ![Anpassa innehållsikonen](./images/ai-itemize-icon.svg) om du vill konvertera det markerade innehållet till en lista.
Med AI-assistentverktyget kan du konvertera innehållet på ett smart sätt till en lista med objekt.
1. (Valfritt) Välj **Expandera** för att öppna redigeraren **Specificera innehåll**.
1. När listan är klar godkänner du ändringarna i det genererade innehållet. Det genererade innehållet ersätter det markerade innehållet.



## Översätta innehåll

Använd den här intelligenta funktionen för att översätta det markerade innehållet till målspråket. Du kan till exempel lägga till innehåll på engelska och snabbt översätta det till tyska.
Utför följande steg för att översätta innehållet:

1. Markera innehållet som du vill översätta.
1. Välj **Översätt innehåll** ![ai-översättningsikon](./images/ai-translate-content-icon.svg) på AI-assistentpanelen.
1. Välj målspråk i listrutan. Det översatta innehållet visas på AI-assistentpanelen.

1. (Valfritt) Välj **Expandera** för att öppna redigeraren för **Översätt innehåll**.
1. Du kan också välja ett annat språk i listrutan och återskapa innehållet på det valda språket. Om du t.ex. väljer franska och sedan **Återskapa** översätts innehållet till franska.

![AI-assistenten översätter innehåll](./images/ai-assisstant-translate-content.png)
