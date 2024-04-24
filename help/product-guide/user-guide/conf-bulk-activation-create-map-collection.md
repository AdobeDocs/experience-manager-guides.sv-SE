---
title: Skapa en gruppaktiveringskarta
description: Lär dig hur du skapar en gruppaktiveringskarta i AEM.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: 1be8cddcbf58696a53bfccf887a04e5807f2198e
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Skapa en gruppaktiveringskarta {#id214GG0E90EV}

Så här skapar du en gruppaktiveringskarta:

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.

1. Välj **Publish Dashboard** platta.

   För första gången visas en tom samlingssida. Om du har skapat gruppaktiveringssamlingar tidigare visas de på den här sidan.

1. Klicka **Skapa**.

1. Ange en titel för din gruppaktiveringskarta och klicka på **Skapa**.

   Ett meddelande om att åtgärden lyckades visas när den gruppaktiverade kartsamlingen skapades.

1. Klicka **Öppna** på meddelandet om att åtgärden lyckades.

1. Välj **Redigera** och sedan **Lägg till kartor**.

1. Leta reda på och lägg till de DITA-kartor som du vill lägga till i den gruppaktiveringskarta.

   Som standard läggs alla förinställningar och språkinställningar som är kopplade till kartan till automatiskt.

1. Välj önskade utdata genom att aktivera eller inaktivera skjutknappen.

   Du kan välja flera förinställningar för olika språk.

1. Klicka **Klar**.

DITA-kartfilerna läggs till i din gruppaktiveringskarta.

![ skapad massaktiveringssamling](images/bulk-activation-collection-created.png){width="800" align="left"}

## Fliken Kartor och förinställningar

The **Kartor och förinställningar** -fliken innehåller information i följande kolumner:

- **Karta**: Visar DITA-kartfilens namn.
- **Kartsökväg**: Visar den fullständiga sökvägen till DITA-mappningsfilen.

- **UUID**: Visar den unika identifierare som är associerad med filen.

- **Språk**: Visar språkkoden för DITA-kartan.
- **Förinställning**: Visar titeln på förinställningen som konfigurerats på kartfilen. Ikonen visas också baserat på vilken typ av förinställning som används.

  >[!NOTE]
  >
  > Den lilla ![](images/global-preset-icon.svg) anger en förinställning på mappprofilnivå.

- **Ändrad**: Anger om DITA-kartan uppdateras efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill aktivera utdata för den här DITA-kartan eller inte.
- **Genererad**: Visar datum och tid för den senaste genererade utdata.
- **Publicerad**: Visar datum och tid för det senaste publicerade (eller aktiverade) resultatet. Om du markerar länken visas **Aktiveringsresultat** visas, som innehåller loggarna med information om rotsökvägen där innehållet är aktiverat.

## Fliken Granska historik

The **Granska historik** -fliken innehåller information om utdata för aktiverade kartor i följande kolumner:
- **Karta**: Visar DITA-kartfilens namn.
- **Kartsökväg**: Visar den fullständiga sökvägen till DITA-mappningsfilen.
- **UUID** : Visar den unika identifierare som är associerad med filen.
- **Språk**: Visar språkkoden för DITA-kartan.
- **Förinställning**: Visar titeln på förinställningen som konfigurerats på kartfilen. Ikonen visas också baserat på vilken typ av förinställning som används.
- **Status**: Visar status för aktiveringen som slutförd eller misslyckad.
- **Mål**: Om du genererar utdata på as a Cloud Service för stödlinjer i Experience Manager kan du visa utdatans mål som Publicera eller Förhandsgranska.

  >[!NOTE]
  >
  > Den lilla ![](images/global-preset-icon.svg) anger en förinställning på mappprofilnivå.

- **Ändrad**: Anger om DITA-kartan uppdaterades efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill aktivera utdata för den här DITA-kartan.
- **Publicerad**: Visar datum och tid för det senaste publicerade (eller aktiverade) resultatet. Om du markerar länken visas sidan Aktiveringsresultat, som innehåller loggarna med information om rotsökvägen där innehållet aktiveras.
  ![ skapad granskningsflik för massaktiveringssamling](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Visa information om aktiverade kartutdata i dialogrutan **Granska historik**-fliken.*


  >[!NOTE]
  >
  > Utdata i **Granska historik** -fliken sorteras baserat på **Publicerad** kolumn.



## Vänster panel

Följande filteralternativ är tillgängliga på den vänstra panelen:

- **Ändrad**: Välj Ja eller Nej. Om du väljer ja visas bara de ändrade DITA-kartorna. En ändrad karta är en karta som har genererats sedan den publicerades senast.
- **Förinställning**: Välj en förinställning som du vill filtrera ut kartfilerna för. I den här kolumnen visas rubriken på förinställningen för utdata som är konfigurerad på kartfilen. Om du till exempel väljer *AEM* förinställning visas bara de kartor som har *AEM* förinställning för utdata konfigurerad för dem.
- **Språk**: Du kan välja någon av de tillgängliga språkkoderna och endast visa det valda språket på fliken Kartor och förinställningar.

Filtren uppdateras när du växlar från **Kartor och förinställningar** till **Granska historik** och vice versa.

**Överordnat ämne: **[Massaktivering av publicerat innehåll](conf-bulk-activation.md)
