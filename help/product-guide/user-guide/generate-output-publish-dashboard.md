---
title: Hantera publiceringsuppgifter med Publish Dashboard
description: Hantera publiceringsuppgifter med Publish Dashboard i AEM Guides. Lär dig hur du kommer åt kontrollpanelen för publicering och avbryter en publiceringsåtgärd.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Hantera publiceringsuppgifter med Publish Dashboard {#id205CC08305Z}

När du har ett stort antal publiceringsuppgifter som körs på datorn blir det praktiskt taget omöjligt att kontrollera varje DITA-karta individuellt för att övervaka dess publiceringsuppgift. Adobe Experience Manager Guides ger administratörer och utgivare en enhetlig vy över alla publiceringsuppgifter som körs i systemet. En lista över alla aktiva publiceringsåtgärder finns på Publish Dashboard.

På Publish Dashboard finns en fullständig översikt över alla publiceringsåtgärder som för närvarande körs i systemet.

![](images/publish-dashboard.png){align="left"}

Kontrollpanelen för publicering innehåller följande information:

- **Karttitel** - titeln på en kartfil som publiceras eller finns i publiceringskön.

- **Filnamn** - DITA-mappningens filnamn.

- **Utdataförinställning** - Namnet på den förinställning som används för att generera utdata.

- **Initierad av** - Användarnamn för användaren som initierade publiceringsaktiviteten.

- **Startades den** - datum och tid när publiceringsaktiviteten startades.

- **Förfluten tid** - Tid sedan publiceringsaktiviteten kördes i systemet.

- **Ta bort ikon** - Avbryt eller avsluta en publiceringsaktivitet.

Den vänstra panelen på kontrollpanelen Publicera innehåller följande filtreringsalternativ:

- **Utdataförinställning** - Välj en eller flera förinställningar för vilka du vill visa de publiceringsåtgärder som är aktiva. På följande skärmbild filtreras publiceringsaktiviteterna så att endast de uppgifter som använder förinställningen för utdata för AEM Site visas:

  ![](images/publish-dashboard-preset-filter.png){align="left"}

- **Initierad av** - Välj ett användarnamn i listan för att visa de publiceringsåtgärder som initierats av den valda användaren.

- **Karta** - Välj en kartfil i listan för att visa de publiceringsåtgärder som körs för den valda kartan.

## Öppna Publish Dashboard

Du kommer åt **Publish Dashboard** direkt från [Experience Manager Guides hemsida](./intro-home-page.md). Öppna hemsidan och välj alternativet **Publiceringskö** i den vänstra panelen.

>[!NOTE]
>
> Endast en administratör eller en utgivare har åtkomst till Publish Dashboard.

Du kan även komma åt **Publish Dashboard** från Adobe Experience Manager **Tools** -sidan. Så här använder du den här metoden:

1. Välj Adobe Experience Manager logotyp längst upp och välj sedan **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Välj panelen **Publish Dashboard**.

   Publish Dashboard öppnas med en lista över alla aktiva publiceringsåtgärder i systemet.

   Om du väljer länken Filnamn visas DITA-schemats kontrollpanel för den valda kartan.

   ![](images/publish-dashboard-click-filename-link.png){align="left"}


>[!NOTE]
>
> Du kan även komma åt Publish Dashboard från fliken **Outputs** när du genererar utdata från kartkontrollpanelen. Mer information finns i [Visa status för utdatagenereringsaktiviteten](generate-output-for-a-dita-map.md#viewing_output_history).

## Avbryta en publiceringsaktivitet

Utför följande steg för att avbryta en utdatagenereringsåtgärd från Publish Dashboard:

1. [Öppna Publish Dashboard](#access-the-publish-dashboard).

1. I listan med aktiva publiceringsuppgifter väljer du ikonen Ta bort för en uppgift som du vill avbryta.

   ![](images/publish-dashboard-cancel-task.png){align="left"}

1. Välj **Ja** i meddelandet **Bekräfta annullering**.

   Kommandot Avbryt accepteras och ett försök att avbryta görs så länge som aktiviteten är aktiv. När aktiviteten har avslutats tas den bort från den aktiva uppgiftslistan. Aktivitetens status uppdateras även på DITA-kartkontrollpanelen som Avbruten. I skärmbilden nedan avbryts aktiviteten *HTML5* från kontrollpanelen för publicering och dess status ändras även på DITA-kartpanelen.

   ![](images/cancelled-output-task.png){align="left"}


**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
