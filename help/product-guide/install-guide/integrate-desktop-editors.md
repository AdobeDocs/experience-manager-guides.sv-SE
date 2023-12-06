---
title: Integrera skrivbordsbaserade XML-redigerare
description: Lär dig integrera skrivbordsbaserade XML-redigerare
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Integrera skrivbordsbaserade XML-redigerare {#id181GB01G0HS}

Det finns många XML-redigerare på marknaden och du skulle kunna använda en redan. Adobe FrameMaker är en av de kraftfullaste XML-redigeringsprogrammen som medföljer AEM. Med AEM connector in FrameMaker kan du enkelt ansluta till AEM, checka ut och in filer samt redigera filer direkt i FrameMakerna. Du kan också konfigurera AEM för att starta FrameMaker från Web Editor. När du har öppnat filen i FrameMaker kan du redigera och checka in den i AEM.

## Aktivera filredigering i FrameMaker från Web Editor

Du kan använda FrameMaker eller någon annan DITA-redigerare för att skapa och uppdatera DITA-innehåll. Om din organisation använder FrameMaker som DITA-redigerare kan du ge dina användare möjlighet att öppna DITA-dokument direkt i FrameMaker från AEM.

Som standard visas inte **Öppna i FrameMaker** på AEM verktygsfält. Gör så här för att lägga till den här knappen i AEM verktygsfält:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paket.

   ![](assets/open-in-fm-toolbar.png){width="550" align="left"}

1. Välj **Visa Öppna i FrameMaker** alternativ.

1. Klicka **Spara**.


När du aktiverar **Visa Öppna i FrameMaker** och sedan **Öppna i FrameMaker** visas när du väljer en DITA-fil i AEM. När det här alternativet är *inte aktiverad*, **Öppna i FrameMaker** visas bara när du väljer en .fm- eller .book-fil i databasen.
