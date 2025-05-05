---
title: Grundläggande felsökning
description: Lös problem med grundläggande felsökning i AEM Guides. Lär dig att visa, kopiera och kontrollera loggfilen i en textredigerare och åtgärda JSP-kompileringsfel.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# Grundläggande felsökning {#id1821I0Y0G0A}

När du arbetar med Adobe Experience Manager Guides kan det uppstå fel när du publicerar eller öppnar dokumentet. Sådana fel kan finnas på DITA-kartan, i ett avsnitt eller i Experience Manager Guides-processen. I det här avsnittet finns information om hur du får åtkomst till och tolkar information i loggfilen för utdatagenerering. Om ditt DITA-avsnitt är för stort kan du även se JSP-kompileringsfelet. I det här avsnittet finns även information om hur du löser JSP-kompileringsfelet.

## Visa och kontrollera loggfilen {#id1822G0P0CHS}

Utför följande steg för att visa och kontrollera loggfilen för generering av utdata:

1. När du har initierat genereringsprocessen för utdata väljer du **Utdata** i DITA-kartkonsolen.

   Kolumnen **Allmänt** i **Genererade utdata** visar ikonerna för att ge en visuell indikator på om utdatagenereringen lyckades eller misslyckades.

   ![](images/output-general-settings.png){width="300" align="left"}

   På skärmbilden ovan visar den första och tredje ikonen misslyckad generering av utdata. Den andra ikonen visar att det gick att generera utdata, men med meddelanden. Den sista genereringen är en lyckad utdatagenerering utan något meddelande.

1. Markera länken i kolumnen **Genererad** när jobbet är klart.

   Loggfilen öppnas på en ny flik.

   ![](images/log-file.png){align="left"}

1. Använd följande filter för att markera texten i loggfilen:
   - Allvarligt: markerar de allvarliga felen i loggfilen med rosa färg.
   - Fel: Markerar felen i loggfilen med orange färg.
   - Varning: Markerar varningarna i loggfilen med lila färg.
   - Info: Markerar informationsmeddelanden i loggfilen med blå färg.
   - Undantag: Markerar undantagen i loggfilen med gul färg.
1. Använd navigeringsknapparna uppåt och nedåt för att hoppa till den markerade texten i loggfilen.

   Du kan även bläddra igenom loggfilen och kontrollera meddelandena.


## Kopiera och kontrollera loggfilen i en textredigerare

Så här kopierar och kontrollerar du loggfilen för generering av utdata i en textredigerare:

1. När du har initierat genereringsprocessen för utdata väljer du **Utdata** i DITA-kartkonsolen.

1. Markera länken i kolumnen **Genererad** när jobbet är klart.

   Loggfilen öppnas på en ny flik.

1. Välj knappen **Kopiera logg**. Loggfilen kopieras till Urklipp.
1. Öppna en textredigerare och klistra in loggfilen i redigeraren.

1. Bläddra igenom loggfilen och sök efter meddelanden.

   Följande information hjälper dig att avgöra om det finns något fel i DITA-filen eller Experience Manager Guides-processen:

   - *DITA-mappningsfilrelaterat fel*: Om ett fel påträffas i DITA-mappningsfilen eller i någon annan fil som finns i DITA-mappningen innehåller loggfilen strängen &quot;BUILD FAILED&quot;. Du kan kontrollera informationen i loggfilen för att hitta den felaktiga filen och åtgärda problemet.

   I följande exempelavsnitt av loggfilen kan du visa meddelandet `BUILD FAILED` tillsammans med orsaken till felet.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *Experience Manager Guides-relaterat fel*: Den andra typen av fel som du kan identifiera i loggfilen är relaterat till själva Experience Manager Guides-processen. I det här fallet tolkas DITA-kartfilen, men utdatagenereringsprocessen misslyckas på grund av ett internt fel i Experience Manager Guides. För sådana fel måste du be om hjälp från det tekniska supportteamet.

   I följande exempelavsnitt av loggfilen kan du visa meddelandet `BUILD SUCCESSFUL` följt av ett annat tekniskt fel.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## Åtgärda JSP-kompileringsfel

Om DITA-avsnittet är för stort kan du visa JSP-kompileringsfelet \(`org.apache.sling.api.request.TooManyCallsException`\) i webbläsaren. Det här felet kan uppstå när du öppnar ett ämne för redigering, granskning eller publicering.

Utför följande steg för att lösa problemet:

1. I Global Navigation väljer du Tools och väljer Operations \> Web Console.

   Sidan Konfigurera Adobe Experience Manager Web Console visas.

1. Sök efter och välj komponenten *Apache Sling Main Servlet* .

   De konfigurerbara alternativen för huvudservern för Apache Sling visas.

1. Öka värdet för parametern *Antal anrop per begäran* enligt dina krav.


**Överordnat ämne:**&#x200B;[ Utdatagenerering](generate-output.md)
