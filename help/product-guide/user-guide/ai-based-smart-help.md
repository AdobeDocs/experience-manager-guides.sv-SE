---
title: AI-baserad smart hjälp för att söka efter innehåll
description: Lär dig hur du visar och använder AI-baserad smart hjälp.
exl-id: 61a15208-9600-4bb8-adc0-feca1a0ffef3
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# Förbättra effektiviteten med smart hjälp i AI Assistant (Beta)

Experience Manager Guides tillhandahåller den GenAI-baserade smarta hjälpen, en konversationssökfunktion som hjälper dig att hitta relevant innehåll från [Adobe Experience Manager Guides-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview).

Du kan ställa frågor och få svar på ett informativt sätt. Svaret på din fråga baseras på innehållet i produktdokumentationen. Den här sökningen är helt konversationell. Du kan ställa frågor om de olika funktionerna i Experience Manager Guides eller ställa frågor om felsökning. Beroende på svaret kan du även ställa ytterligare frågor. Svaret innehåller även länkar till källdokument, som du kan referera till för mer information.

Du kanske vill ställa frågor som *Hur publicerar jag en karta?* Du får ett svar och länkar för de relaterade artiklarna. Om du sedan vill lära dig hur du använder en viss metod för att publicera utdata kan du ställa frågor om det. *Hur publicerar jag en karta till PDF?*

När du öppnar **AI Assistant** på startsidan, kartkonsolen eller redigeraren öppnas **hjälppanelen** till höger. När det gäller redigeraren visas även redigeringspanelen som ger dig smarta redigeringsfunktioner. Mer information finns i [AI-assistenten för att skapa dokument på ett smart sätt](./ai-assistant-right-panel.md)

![Smart hjälppanel](images/smart-help-panel.png){width="300" align="left"}

*Visa panelen **Hjälp**.*

Utför följande steg om du vill använda hjälppanelen för att hitta rätt innehåll och lösa dina frågor:

1. Välj **AI-assistenten** för att öppna hjälppanelen.

   >[!NOTE]
   >
   > I de [globala profilerna eller mappnivåprofilerna](../cs-install-guide/conf-folder-level.md#conf-ai-guides-assistant) måste administratören definiera standardfrågorna som visas på panelen.

1. Skriv frågan för att hitta det relaterade innehållet i Experience Manager Guides-dokumentationen. Du kan välja standardfrågan på panelen eller skriva frågan i textrutan.

1. Välj **Skicka** ![Ikonen Skicka](images/send-icon.svg) eller tryck på **Retur** om du vill visa svaret på dina frågor.

   Beroende på din fråga kan du visa innehållet, tillämpliga bilder och länkar till artiklarna.

   ![Panelsvar för smart hjälp](images/smart-help-panel-response.png){width="300" align="left"}


   *Välj exempelfrågan och visa innehållet och bilderna som svar.*

1. Markera länkarna till artiklarna i slutet och visa detaljerad information om svaret på din fråga.


1. Välj **Rensa konversation** ![Rensa konversation](images/clear-conversation-icon.svg) om du vill ta bort konversationshistoriken från panelen. Du kan sedan starta en ny konversation och hitta relevant innehåll.

I stället för att söka i användarhandböcker och referensdokument kan du använda funktionen **Hjälp** för att snabbt hitta relevanta svar på dina frågor. Detta sparar tid och gör att du kan fokusera på att skapa innehåll, vilket ger ökad produktivitet och effektivitet.

## Alternativ för hjälpsvar för AI Assistant

När du får ett svar från AI Assistant på panelen **Hjälp** kan du interagera med den eller ge feedback för att förbättra dess precision och tillförlitlighet. Din feedback hjälper Experience Manager Guides-teamet att förbättra noggrannheten och relevansen i AI Assistant-svaren och förbättra resultatet över tid.

Följande alternativ är tillgängliga för att interagera med eller ge feedback på svar från AI Assistant-panelen **Hjälp**:

![](images/ai-assistant-response-options.png){width="300" align="left"}

- **Kopiera**: Kopiera svaret för användning i dina dokument.
- **Gilla**: Ange att svaret var användbart eller korrekt. Välj gilla-ikonen för att gilla svaret och använd alternativet **Berätta mer** för att ge detaljerad feedback.
- **Ogilla**: Markera svaret som oanvändbart eller felaktigt. Välj ikonen Ogilla för att gilla svaret och använd alternativet **Berätta mer** för att ge detaljerad feedback.
- **Rapport**: Flagga svaret för granskning om det innehåller fel eller felaktigt innehåll. Välj flaggikonen för att öppna dialogrutan **Rapportera resultat**. Välj bland de tillgängliga alternativen eller ge en egen feedback.