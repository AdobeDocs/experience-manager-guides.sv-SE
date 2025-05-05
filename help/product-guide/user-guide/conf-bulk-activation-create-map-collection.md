---
title: Skapa en gruppaktiveringskarta
description: Lär dig hur du skapar en gruppaktiveringskarta i AEM guides.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# Skapa en gruppaktiveringskarta {#id214GG0E90EV}

Så här skapar du en gruppaktiveringskarta:

1. Markera Adobe Experience Manager logotyp överst och välj **Verktyg**.

1. Välj **Stödlinjer** på panelen **Verktyg**.

1. Välj panelen **Masspubliceringspanel**.

   Kontrollpanelen Publicera gruppvis visas. Du kan även komma åt den här instrumentpanelen från den vänstra panelen på [Adobe Experience Manager Guides hemsida](intro-home-page.md).

   För första gången visas en tom samlingssida. Om du har skapat gruppaktiveringssamlingar tidigare visas de på den här sidan.


1. Välj **Skapa**.

1. Ange en titel för din gruppaktiveringskarta och välj **Skapa**.

   Ett meddelande om att åtgärden lyckades visas när den gruppaktiverade kartsamlingen skapades.

1. Välj **Öppna** i meddelandet om att åtgärden lyckades.

1. Välj **Redigera** och sedan **Lägg till kartor**.

1. Leta reda på och lägg till de DITA-kartor som du vill lägga till i den gruppaktiveringskarta.

   Som standard läggs alla förinställningar och språkinställningar som är kopplade till kartan till automatiskt.

1. Välj önskade utdata genom att aktivera eller inaktivera skjutknappen.

   Du kan välja flera förinställningar för olika språk.

1. Välj **Klar**.

DITA-kartfilerna läggs till i din gruppaktiveringskarta.

![ skapade massaktiveringssamlingen ](images/bulk-activation-collection-created.png){align="left"}

## Fliken Kartor och förinställningar

Fliken **Kartor och förinställningar** innehåller information i följande kolumner:

- **Karta**: Visar titeln på DITA-kartfilen.
- **Mappningssökväg**: Visar den fullständiga sökvägen till DITA-mappningsfilen.

- **UID**: Visar den unika identifierare som är associerad med filen.

- **Språk**: Visar språkkoden för DITA-kartan.
- **Förinställning**: Visar titeln på förinställningen som konfigurerats på kartfilen. Ikonen visas också baserat på vilken typ av förinställning som används.

  >[!NOTE]
  >
  > Den lilla ikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

- **Ändrad**: Anger om DITA-kartan uppdateras efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill aktivera utdata för den här DITA-kartan eller inte.
- **Genererad**: Visar datum och tid för den senaste genererade utdata.
- **Publicerad**: Visar datum och tid för det senaste publicerade (eller aktiverade) resultatet. Om du markerar länken visas sidan **Aktiveringsresultat** som innehåller loggarna med information om rotsökvägen där innehållet aktiveras.

## Fliken Granska historik

Fliken **Granskningshistorik** innehåller information om aktiverade mapputdata i följande kolumner:
- **Karta**: Visar titeln på DITA-kartfilen.
- **Mappningssökväg**: Visar den fullständiga sökvägen till DITA-mappningsfilen.
- **UID** : Visar den unika identifierare som är associerad med filen.
- **Språk**: Visar språkkoden för DITA-kartan.
- **Förinställning**: Visar titeln på förinställningen som konfigurerats på kartfilen. Ikonen visas också baserat på vilken typ av förinställning som används.
- **Status**: Visar status för aktiveringen som slutförd eller misslyckad.
- **Mål**: Om du genererar utdata på Experience Manager Guides as a Cloud Service kan du visa utdatans mål som Publicera eller Förhandsgranska.

  >[!NOTE]
  >
  > Den lilla ikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

- **Ändrad**: Anger om DITA-kartan uppdaterades efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill aktivera utdata för den här DITA-kartan.
- **Publicerad**: Visar datum och tid för det senaste publicerade (eller aktiverade) resultatet. Om du markerar länken visas sidan Aktiveringsresultat, som innehåller loggarna med information om rotsökvägen där innehållet aktiveras.
  ![ skapade en samlingens granskningshistorik för gruppaktivering ](images/bulk-collection-audit-history.png){align="left"}

  *Visa information om aktiverade mapputdata på fliken **Granskningshistorik**.*


  >[!NOTE]
  >
  > Utdata på fliken **Granskningshistorik** sorteras baserat på kolumnen **Publicerad** .



## Vänster panel

Följande filteralternativ är tillgängliga på den vänstra panelen:

- **Ändrad**: Du kan välja Ja eller Nej. Om du väljer ja visas bara de ändrade DITA-kartorna. En ändrad karta är en karta som har genererats sedan den publicerades senast.
- **Förinställning**: Välj en förinställning som du vill filtrera ut kartfilerna för. I den här kolumnen visas rubriken på förinställningen för utdata som är konfigurerad på kartfilen. Om du t.ex. väljer förinställningen *AEM Site* visas bara de kartor som har förinställningen *AEM Site* konfigurerad.
- **Språk**: Du kan välja någon av de tillgängliga språkkoderna och endast visa det valda språket på fliken Kartor och förinställningar.

Filtren uppdateras när du växlar från fliken **Kartor och förinställningar** till fliken **Granskningshistorik** och vice versa.

**Överordnat ämne: &#x200B;** [Massaktivering av publicerat innehåll](conf-bulk-activation.md)
