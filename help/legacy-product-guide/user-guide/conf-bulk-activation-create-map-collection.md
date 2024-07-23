---
title: Skapa en gruppaktiveringskarta
description: Lär dig hur du skapar en gruppaktiveringskarta i AEM.
feature: Publishing, Bulk Activation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Skapa en gruppaktiveringskarta {#id214GG0E90EV}

Så här skapar du en gruppaktiveringskarta:

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Markera rutan **Massvis med Publish Dashboard**.

   För första gången visas en tom samlingssida. Om du har skapat gruppaktiveringssamlingar tidigare visas de på den här sidan.

1. Klicka på **Skapa**.

1. Ange en titel för din gruppaktiveringskarta och klicka på **Skapa**.

   Ett meddelande om att åtgärden lyckades visas när den gruppaktiverade kartsamlingen skapades.

1. Klicka på **Öppna** i meddelandet om att åtgärden lyckades.

1. Välj **Redigera** och sedan **Lägg till kartor**.

1. Leta reda på och lägg till de DITA-kartor som du vill lägga till i den gruppaktiveringskarta.

   Som standard läggs alla förinställningar och språkinställningar som är kopplade till kartan till automatiskt.

1. Välj önskade utdata genom att aktivera eller inaktivera skjutknappen.

   Du kan välja flera förinställningar för olika språk.

1. Klicka på **Klar**.

DITA-kartfilerna läggs till i din gruppaktiveringskarta.

![ skapade massaktiveringssamlingen ](images/bulk-activation-collection-created.png){width="800" align="left"}

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
- **Mål**: Om du genererar utdata på Experience Manager Guides as a Cloud Service kan du visa utdatans mål som Publish eller Förhandsgranska.

  >[!NOTE]
  >
  > Den lilla ikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

- **Ändrad**: Anger om DITA-kartan uppdaterades efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill aktivera utdata för den här DITA-kartan.
- **Publicerad**: Visar datum och tid för det senaste publicerade (eller aktiverade) resultatet. Om du markerar länken visas sidan Aktiveringsresultat, som innehåller loggarna med information om rotsökvägen där innehållet aktiveras.
  ![ skapade en samlingens granskningshistorik för gruppaktivering ](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Visa information om aktiverade mapputdata på fliken **Granskningshistorik**.*


  >[!NOTE]
  >
  > Utdata på fliken **Granskningshistorik** sorteras baserat på kolumnen **Publicerad** .



## Vänster panel

Följande filteralternativ är tillgängliga på den vänstra panelen:

- **Ändrad**: Du kan välja Ja eller Nej. Om du väljer ja visas bara de ändrade DITA-kartorna. En ändrad karta är en karta som har genererats sedan den publicerades senast.
- **Förinställning**: Välj en förinställning som du vill filtrera ut kartfilerna för. I den här kolumnen visas rubriken på förinställningen för utdata som är konfigurerad på kartfilen. Om du t.ex. väljer *AEM Plats* -förinställning visas bara de kartor som har *AEM Platsens* förinställning konfigurerad för.
- **Språk**: Du kan välja någon av de tillgängliga språkkoderna och endast visa det valda språket på fliken Kartor och förinställningar.

Filtren uppdateras när du växlar från fliken **Kartor och förinställningar** till fliken **Granskningshistorik** och vice versa.

**Överordnat ämne: **[Massaktivering av publicerat innehåll](conf-bulk-activation.md)
