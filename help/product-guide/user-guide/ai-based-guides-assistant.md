---
title: AI-baserad Guides Assist för sökning av innehåll
description: Lär dig hur du visar och använder AI-driven Guides Assistant i Web Editor.
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---


# AI-baserad Guides Assistant för sökning av innehåll



När du redigerar dokument i Web Editor kan du använda den GenAI-baserade Guides Assistant. Med den här konversationssökfunktionen kan du hitta relevant innehåll från [Adobe Experience Manager Guides-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview).
Du kan ställa frågor och få svar på ett informativt sätt. Svaret på din fråga baseras på innehållet i produktdokumentationen. Den här sökningen är helt konversationell. Du kan ställa frågor och sedan, baserat på svaret, ställa ytterligare frågor. Svaret innehåller även länkar till källdokument, som du kan referera till för mer information.

Du kan till exempel skapa ett ämne i Experience Manager Guides för din dokumentation. Du kan fråga, *Hur skapar du ett ämne?* Du får ett svar och länkar för de relaterade artiklarna. Om du sedan vill lära dig hur du genererar utdata från PDF för dokumentet kan du ställa frågor om det. *Så här publicerar du ett ämne till en PDF?* eller *Hur skapar jag utdata i PDF för ett ämne?*



När du öppnar Web Editor visas panelen **Guides Assistant** till höger.



>[!NOTE]
>
> Administratören måste konfigurera funktionen **Guides Assistant**. Mer information finns i avsnittet [Konfigurera den AI-baserade Guides Assistant för att söka efter Cloud Service](../cs-install-guide/conf-guides-assistant.md) i installations- och konfigurationshandboken.

![Guides Assistant-panelen](images/guides-assistant-panel.png){width="300" align="left"}

*Visa panelen **Guides Assistant**.*

Utför följande steg för att använda konversationssökningen för att hitta rätt innehåll och lösa dina frågor:

1. Välj **Guides Assistant** ![Guides Assistant-ikon](images/guides-assistant-icon.svg) för att öppna panelen.



   >[!NOTE]
   >
   > I de [globala profilerna eller mappnivåprofilerna](../cs-install-guide/conf-folder-level.md#conf-ai-guides-assistant) måste administratören definiera standardfrågorna som visas på panelen.

1. Skriv frågan för att hitta det relaterade innehållet i Experience Manager Guides-dokumentationen. Du kan välja standardfrågan på panelen eller skriva frågan i textrutan.

1. Välj **Skicka** ![Ikonen Skicka](images/send-icon.svg) eller tryck på **Retur** om du vill visa svaret på dina frågor.

   Beroende på din fråga kan du visa innehållet, tillämpliga bilder och länkar till artiklarna.

   ![Guides Assist-panelsvar](images/guides-assistant-panel-response.png){width="300" align="left"}


   *Välj exempelfrågan och visa innehållet och bilderna som svar.*





1. Markera länkarna till artiklarna i slutet och visa detaljerad information om din fråga.


1. Välj **Rensa konversation** ![Rensa konversation](images/clear-conversation-icon.svg) om du vill ta bort konversationshistoriken från panelen. Du kan sedan starta en ny konversation och hitta relevant innehåll.

Den här smarta funktionen hjälper dig att hitta lösningar snabbt och låter dig fokusera på dokumentationen och slutföra dina uppgifter på ett effektivt sätt.