---
title: Integrera skrivbordsbaserade XML-redigerare
description: Lär dig integrera skrivbordsbaserade XML-redigerare
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 434d7efd24147af23b4c65aeebf4c144ce3adda7
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Integrera skrivbordsbaserade XML-redigerare {#id181GB01G0HS}

Det finns många XML-redigerare på marknaden och du skulle kunna använda en redan. Adobe FrameMaker är en av de kraftfullaste XML-redigeringsprogrammen som medföljer AEM. Med AEM connector in FrameMaker kan du enkelt ansluta till AEM, checka ut och in filer samt redigera filer direkt i FrameMakerna. Du kan också konfigurera Experience Manager Guides så att FrameMakerna startas från Web Editor. När du har öppnat filen i FrameMaker kan du redigera och checka in den i AEM.

## Aktivera filredigering i FrameMaker från Web Editor

Du kan använda FrameMaker eller någon annan DITA-redigerare för att skapa och uppdatera DITA-innehåll. Om din organisation använder FrameMaker som DITA-redigerare kan du ge dina användare möjlighet att öppna DITA-dokument direkt i FrameMaker från AEM.

Som standard visas inte knappen **Öppna i FrameMaker** i AEM verktygsfält. Gör så här för att lägga till den här knappen i AEM verktygsfält:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.
   ![](assets/open-in-fm-config.png)

1. Markera alternativet **Visa Öppna i FrameMaker-knapp**.

1. Om du använder version 4.6 och FrameMaker 2022 från september - uppdatering 3, måste du aktivera konfigurationen **FrameMaker version 2022 uppdatering 3 eller senare** så att dina användare kan skicka information om Experience Manager Guides-servern till FrameMakerna. Som standard är den inaktiverad.


1. Klicka på **Spara**.


När du aktiverar alternativet **Visa Öppna i FrameMaker-knapp** visas knappen **Öppna i FrameMaker** när du markerar en DITA-fil i AEM. När det här alternativet *inte är aktiverat* visas knappen **Öppna i FrameMaker** bara när du markerar en .fm- eller .book-fil i databasen.



