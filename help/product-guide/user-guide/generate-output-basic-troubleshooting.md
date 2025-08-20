---
title: Grundläggande felsökning
description: Lös problem med grundläggande felsökning i AEM Guides. Lär dig att visa, kopiera och kontrollera loggfilen i en textredigerare och åtgärda JSP-kompileringsfel.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: 262edba89ab4bf65cb6e109bd7c5df177e2e56fe
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 0%

---

# Grundläggande felsökning {#id1821I0Y0G0A}

När du arbetar med Adobe Experience Manager Guides kan det uppstå fel när du publicerar eller öppnar dokumentet. Sådana fel kan finnas på DITA-kartan, i ett avsnitt eller i Experience Manager Guides-processen. I det här avsnittet finns information om hur du får åtkomst till och tolkar information i loggfilen för utdatagenerering. Om ditt DITA-avsnitt är för stort kan du även se JSP-kompileringsfelet. I det här avsnittet finns även information om hur du löser JSP-kompileringsfelet.

## Visa och kontrollera loggfilen {#id1822G0P0CHS}

Utför följande steg för att visa och kontrollera loggfilen för generering av utdata:

1. När du har initierat genereringsprocessen för utdata väljer du **Utdata** i DITA-kartkonsolen.

   Kolumnen **Genereringsinställning** i **Genererade utdata** visar färgen för att ge en visuell indikator på om utdatagenerationen lyckades eller misslyckades för olika utdatainställningar.

   ![](images/output-general-settings-new.png){width="300" align="left"}

   På skärmbilden ovan:

   - Rött indikerar misslyckad utdatagenerering.
   - Grönt är en lyckad utdatagenerering.
   - Amber indikerar en lyckad utdatagenerering med fel.

   >[!NOTE]
   >
   > Färgerna på fliken **Utdata**, som anger status för olika utdataresultat, skiljer sig från färgerna som används för att kategorisera olika typer av fel i loggfilerna.

1. Markera länken i kolumnen **Genererad** när jobbet är klart.

   Loggfilen öppnas på en ny flik.

   ![](images/log-file-new.png){align="left"}

1. Använd följande filter för att markera texten i loggfilen:
   - Allvarligt: markerar de allvarliga felen i loggfilen med mörkröd färg.
   - Fel: Markerar felen i loggfilen med röd färg. Undantag behandlas som fel och markeras på liknande sätt i rött.
   - Varning: Markerar varningarna i loggfilen med gul färg.
   - Info: Markerar informationsmeddelanden i loggfilen med grön färg.

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


**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
