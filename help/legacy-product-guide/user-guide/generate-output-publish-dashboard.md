---
title: Hantera publiceringsuppgifter med Publish Dashboard
description: Hantera publiceringsuppgifter med Publish Dashboard i AEM Guides. Lär dig hur du kommer åt kontrollpanelen för publicering och avbryter en publiceringsåtgärd.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Hantera publiceringsuppgifter med Publish Dashboard {#id205CC08305Z}

När du har ett stort antal publiceringsuppgifter som körs på datorn blir det praktiskt taget omöjligt att kontrollera varje DITA-karta individuellt för att övervaka dess publiceringsuppgift. AEM Guides ger administratörer och utgivare en enhetlig vy över alla publiceringsuppgifter som körs i systemet. En lista över alla aktiva publiceringsåtgärder finns i Publish Dashboard.

Publish Dashboard ger en fullständig översikt över alla publiceringsuppgifter som för närvarande körs i systemet.

![](images/publish-dashboard.png){width="800" align="left"}

Publish Dashboard innehåller följande information:

- **Karttitel** - titeln på en kartfil som publiceras eller finns i publiceringskön.

- **Filnamn** - DITA-mappningens filnamn.

- **Utdataförinställning** - Namnet på den förinställning som används för att generera utdata.

- **Initierad av** - Användarnamn för användaren som initierade publiceringsaktiviteten.

- **Startades den** - datum och tid när publiceringsaktiviteten startades.

- **Förfluten tid** - Tid sedan publiceringsaktiviteten kördes i systemet.

- **Ta bort ikon** - Avbryt eller avsluta en publiceringsaktivitet.

Den vänstra panelen i Publish Dashboard innehåller följande filtreringsalternativ:

- **Utdataförinställning** - Välj en eller flera förinställningar för vilka du vill se de publiceringsåtgärder som är aktiva. På följande skärmbild filtreras publiceringsaktiviteterna så att de endast visar de uppgifter som använder AEM webbplatsens utdataförinställning:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Initierad av** - Välj ett användarnamn i listan för att visa de publiceringsåtgärder som initierats av den valda användaren.

- **Karta** - Välj en kartfil i listan för att visa de publiceringsåtgärder som körs för den valda kartan.

## Öppna Publish Dashboard {#id205CC100DY4}

Utför följande steg för att komma åt Publish Dashboard:

>[!NOTE]
>
> Endast en administratör eller en utgivare har åtkomst till Publish Dashboard.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på panelen **Publish Dashboard**.

   Publish Dashboard öppnas med en lista över alla aktiva publiceringsåtgärder i systemet.

   Om du klickar på länken Filnamn visas DITA-kartkonsolen för den valda kartan.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Du kan även komma åt Publish Dashboard från fliken Utdata när du genererar utdata från kartkontrollpanelen. Mer information finns i [Visa status för utdatagenereringsaktiviteten](generate-output-for-a-dita-map.md#viewing_output_history).

## Avbryta en publiceringsaktivitet

Utför följande steg för att avbryta en utdatagenereringsuppgift från Publish Dashboard:

1. [Öppna Publish Dashboard](#id205CC100DY4).

1. I listan med aktiva publiceringsuppgifter klickar du på ikonen Ta bort för en uppgift som du vill avbryta.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Klicka på **Ja** i meddelandet Bekräfta annullering.

   Kommandot Avbryt accepteras och ett försök att avbryta görs så länge som aktiviteten är aktiv. När aktiviteten har avslutats tas den bort från den aktiva uppgiftslistan. Aktivitetens status uppdateras även i DITA-kartkonsolen som Avbruten. I skärmbilden nedan avbryts aktiviteten *HTML5* från Publish Dashboard och dess status ändras även i DITA-kartkonsolen.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
