---
title: Grundläggande felsökning
description: Lös problem med grundläggande felsökning i AEM Guides. Lär dig att visa, kopiera och kontrollera loggfilen i en textredigerare och åtgärda JSP-kompileringsfel.
feature: Publishing, Troubleshooting
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Grundläggande felsökning {#id1821I0Y0G0A}

När du arbetar med AEM Guides kan det uppstå fel när du publicerar eller öppnar dokumentet. Sådana fel kan finnas på DITA-kartan, i ett avsnitt eller i AEM Guides-processen. I det här avsnittet finns information om hur du får åtkomst till och tolkar information i loggfilen för utdatagenerering. Om ditt DITA-avsnitt är för stort kan du se JSP-kompileringsfelet. I det här avsnittet finns även information om hur du löser JSP-kompileringsfelet.

## Visa och kontrollera loggfilen {#id1822G0P0CHS}

Utför följande steg för att visa och kontrollera loggfilen för generering av utdata:

1. När du har initierat genereringsprocessen för utdata klickar du på **Utdata** i DITA-kartkonsolen.

   Kolumnen **Allmänt** i **Genererade utdata** visar ikonerna för att ge en visuell indikator på om utdatagenereringen lyckades eller misslyckades.

   ![](images/output-general-settings.png){width="300" align="left"}

   På skärmbilden ovan visar den första och tredje ikonen misslyckad generering av utdata. Den andra ikonen visar att det gick att generera utdata, men med meddelanden. Den sista genereringen är en lyckad utdatagenerering utan något meddelande.

1. Klicka på länken i kolumnen **Genererad** när jobbet är klart.

   Loggfilen öppnas på en ny flik.

   ![](images/log-file.png){width="800" align="left"}

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

1. När du har initierat genereringsprocessen för utdata klickar du på **Utdata** i DITA-kartkonsolen.

1. Klicka på länken i kolumnen **Genererad** när jobbet är klart.

   Loggfilen öppnas på en ny flik.

1. Klicka på knappen **Kopiera logg**. Loggfilen kopieras till Urklipp.
1. Öppna en textredigerare och klistra in loggfilen i redigeraren.

1. Bläddra igenom loggfilen och sök efter meddelanden.

   Följande information hjälper dig att avgöra om det finns något fel i DITA-filen eller AEM Guides-processen:

   - *DITA-mappningsfilrelaterat fel*: Om ett fel påträffas i DITA-mappningsfilen eller i någon annan fil som finns i DITA-mappningen innehåller loggfilen strängen &quot;BUILD FAILED&quot;. Du kan kontrollera informationen i loggfilen för att hitta den felaktiga filen och åtgärda problemet.

   I följande exempelavsnitt av loggfilen visas meddelandet `BUILD FAILED` tillsammans med orsaken till felet.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *AEM Guides-relaterat fel*: Den andra typen av fel som du kan identifiera i loggfilen är relaterat till själva AEM Guides-processen. I det här fallet tolkas DITA-kartfilen, men utdatagenereringsprocessen misslyckas på grund av ett internt fel i AEM Guides. För sådana fel måste du be om hjälp från det tekniska supportteamet.

   I följande exempelavsnitt av loggfilen visas meddelandet `BUILD SUCCESSFUL`, följt av ett annat tekniskt fel.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## Åtgärda JSP-kompileringsfel

Om DITA-avsnittet är för stort kanske JSP-kompileringsfelet \(`org.apache.sling.api.request.TooManyCallsException`\) visas i webbläsaren. Det här felet kan uppstå när du öppnar ett ämne för redigering, granskning eller publicering.

Utför följande steg för att lösa problemet:

1. I Global Navigation väljer du Tools och väljer Operations \> Web Console.

   Sidan Konfigurera Adobe Experience Manager Web Console visas.

1. Sök efter och klicka på komponenten *Apache Sling Main Servlet* .

   De konfigurerbara alternativen för huvudservern för Apache Sling visas.

1. Öka värdet för parametern *Antal anrop per begäran* enligt dina krav.


**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
