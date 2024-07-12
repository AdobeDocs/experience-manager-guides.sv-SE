---
title: Översätt ändrade ämnen
description: Lär dig hur du översätter ett ändrat ämne på nytt i AEM Guides.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Översätt ändrade ämnen {#id16A5A0B6072}

Om du ändrar något i vissa ämnen måste dessa ämnen översättas på nytt. Du kan hålla reda på ändrade ämnen från DITA-kartan. Klicka på DITA-mappningsfilen i källmappen för språkkopiering och klicka på fliken Översättning. Du kan se statusen för varje ämne oavsett om det kräver omöversättning eller inte.

Utför följande steg för att skicka ett ändrat ämne för omöversättning:

1. Klicka på DITA-mappningsfilen i källspråkets kopieringsmapp.

1. Klicka på fliken **Översättning**.

1. I panelen **Filter** till vänster markerar du **Översätt språk** som du vill kontrollera statusen för och klickar sedan på **Klar**.

   Du kan se översättningsstatusen för varje avsnitt. De ämnen som har en annan version av ämnet tillgänglig än vad som skickades för översättning visar statusen **Inaktuell**.

   >[!NOTE]
   >
   > Översättningsarbetsflödet jämför den senast sparade versionen av ämnesfilen i källspråksmappen med den översatta versionen.

   Om du klickar på pilen visas mer information. du kan se den aktuella språkkopian.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Klicka i kryssrutan för att markera de ämnen som du vill skicka för omöversättning.

   När du väljer ett osynkroniserat datum visas alternativet **Skapa/uppdatera språkkopior** på referenspanelen och knappen **Stäng ur synkroniseringsstatus** ovanför ikonen **Filter** .

   Du kan använda knappen **Stäng ur synkronisering** om du vill åsidosätta statusen Inaktuell för ämnena i DITA-kartan. Om du till exempel har gjort vissa ändringar i den engelska versionen av ämnet som inte behöver översättas kan du använda den här knappen och ändra statusen Inaktuell för det markerade ämnet.

   >[!NOTE]
   >
   > Om du klickar på knappen **Ignorera status för ej synkroniserad** anges Ämnesstatusen till Uppdaterad för de valda avsnitten Inaktuell.

1. Klicka på **Uppdatera språkkopior** och konfigurera översättningsjobbet.

1. Du kan välja att skapa ett nytt översättningsprojekt eller lägga till ämnen i ett befintligt översättningsprojekt. Ange nödvändig information för att konfigurera översättningsprojektet.

1. Klicka på **Start**.

   Ett bekräftelsemeddelande som visar att ämnet har skickats för översättning visas.

1. Navigera till översättningsprojektet i projektkonsolen. Ett nytt översättningsjobbkort skapas i mappen. Klicka på ellipsen för att visa resurserna i mappen.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Starta översättningen genom att klicka på pilen på översättningsjobbkortet och välja **Start** i listan. Ett meddelande meddelar att jobbet har startats.

   Du kan även visa statusen för det ämne som översätts när du klickar på ellipsen längst ned på översättningsjobbkortet.

   >[!NOTE]
   >
   > Om du använder översättningstjänsten för människor måste du exportera innehållet för översättning. När du har det översatta innehållet måste du importera det tillbaka till översättningsprojektet.

1. När översättningen är klar ändras statusen till **Klar att granskas**. Klicka på ellipsen för att se ämnesinformation och gör något av följande i verktygsfältet:

   - Klicka på **Visa i Assets** för att visa och verifiera översättningen.

   - Klicka på **Acceptera översättning** om du tror att ändringarna har översatts korrekt. Ett bekräftelsemeddelande visas.

   - Klicka på **Avvisa översättning** om du tror att jobbet måste utföras om. Ett meddelande om avvisning visas.

   >[!NOTE]
   >
   > Det är viktigt att acceptera eller avvisa den översatta resursen, annars stannar filen kvar på den tillfälliga platsen och kopieras inte till DAM.

1. Gå tillbaka till DITA-mappningsfilen i källspråksmappen i Assets UI. De omöversatta ämnena är nu synkroniserade.


**Överordnat ämne:**[&#x200B;Översätta innehåll](translation.md)
