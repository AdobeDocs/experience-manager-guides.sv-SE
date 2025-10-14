---
title: Använd kartsamling för generering av utdata
description: Lär dig skapa och ta bort en kartsamling och lägga till eller ta bort en DITA-karta. Konfigurera, generera och avbryta en utdatagenereringsaktivitet från en kartsamling i AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 4215618f-2203-4c55-adba-cdec76322e9e
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Använd kartsamling för generering av utdata {#id1723F20G0HS}

I alla organisationer kan en produkt ha flera typer av dokumentation. Som publiceringsspecialist vill du kontrollera vilka utdata du vill generera för vilket dokument. Det bör också finnas ett sätt att grupppublicera flera dokument med ett enda klick.

Med AEM Guides kan du ordna ditt innehåll för publicering med hjälp av en kontrollpanel som heter Map Collection. Med en kartsamling kan du samla alla olika typer av dokument i en enda enhet. Du kan välja vilken typ av utdata som du vill generera för varje dokument i kartsamlingen. Dessutom kan du generera utdata och se hur utdatagenereringen fortskrider på publiceringspanelen.

Med Kartsamling kan du visa om det finns några ändringar i kartor från den senaste publicerade utdata. Du kan visa informationen på fliken Kartor och förinställningar i din kartsamling och sedan publicera utdata igen om det behövs. Mer information finns i Lägga till en karta i en kartsamling.

## Skapa en kartsamling och lägg till DITA-kartor

Så här skapar du en kartsamling och lägger till DITA-kartor i samlingen:

1. Klicka på **Mappa samlingar** i Assets-gränssnittet.

   Om länken Kartsamlingar inte är tillgänglig väljer du alternativet **Navigering** i den vänstra listen och klickar sedan på **Kartsamlingar**.

   ![](images/access-map-collection-left-rail.png){width="350" align="left"}

1. Ange en titel för kartsamlingen.
1. Klicka på **Skapa**.

   Ett meddelande om att det lyckades visas när kartsamlingen skapades.

1. Klicka på **Stäng** i meddelandet Slutfört.

   Den nyligen skapade kartfilen visas på sidan Kartsamlingar.

1. Klicka på den grå rutan i den del av samlingen som du vill redigera.
1. Klicka på **Redigera** och sedan på **Lägg till kartor**.
1. Leta reda på och lägg till de DITA-kartor som du vill lägga till i kartsamlingen.

   Som standard läggs alla förinställningar och språkinställningar som är kopplade till kartan till automatiskt.

1. Välj önskade utdata genom att aktivera eller inaktivera skjutknappen.
1. Klicka på **Klar**.

   DITA-kartfilerna läggs till i din kartsamling.

   ![kartsamlingens kontrollpanel](./images/map-collection-dashboard.png){width="800" align="left"}

Följande filtreringsalternativ och mappningsinformation visas på samlingssidan:

- **Filter:** I den senaste rälen visas följande filter:
   - **Ändrad**: Du kan välja Ja eller Nej. Om du väljer ja visas endast de ändrade DITA-kartorna i tabellen Kartor och förinställningar.
   - **Förinställning**: Välj en förinställning som du vill filtrera ut kartfilerna för. Om du t.ex. väljer förinställningen *AEM Site* visas bara de kartor som har förinställningen *AEM Site* konfigurerad.
   - **Språk**: Du kan välja någon av de tillgängliga språkkoderna och endast visa det valda språket i tabellen Kartor och förinställningar.
- Tabellen **Kartor och förinställningar**: Tabellen Kartor och förinställningar innehåller information i följande kolumner:
   - **Karta**: Visar titeln på DITA-kartfilen.
   - **Filnamn**: Visar filnamnet för DITA-kartan.
   - **Språk**: Visar språket för DITA-kartan.
   - **Förinställning**: Visar förinställningstypen som konfigurerats för kartfilen.
   - **Baslinje**: Visar den baslinje som används av förinställningen för utdata.  Om ingen baslinje används visas ett bindestreck &#39;-&#39;
   - **Ändrad**: Anger om DITA-kartan uppdateras efter den senaste publikationen. Baserat på den här informationen kan du bestämma om du vill publicera om utdata för den här DITA-kartan eller inte.
   - **Senast genererad**: Visar datum och tid för den senaste genererade utdata.

## Konfigurera och generera utdata med en kartsamling

Så här konfigurerar och genererar du utdata med en kartsamling:

1. Öppna Kartsamlingen.Du kan visa olika förinställningar, t.ex. AEM Site, PDF (inklusive Native PDF), HTML5, EPUB och Custom. Du kan även visa de förinställningar för global profil och mappprofil som har skapats av administratören.

   Ikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.
1. \(Valfritt\) Gör något av följande beroende på dina behov:
   - Använd filter från den vänstra listen för att filtrera ändrade kartor, förinställningar eller språk.
   - Om det behövs klickar du på **Redigera** och ändrar önskade utdata genom att aktivera eller inaktivera skjutknappen.



     >[!NOTE]
     >  
     > Som standard är alla nya förinställningar inaktiverade.

1. Du kan aktivera förinställningarna för en DITA-karta på följande sätt:

   - Aktivera alla enskilda förinställningar.
   - Aktivera **Alla förinställningar** för en DITA-karta om du vill välja alla förinställningar på en gång. Det här alternativet är inaktiverat som standard.
   - Aktivera **mappprofilförinställningar** för en DITA-karta om du vill välja alla mappprofilförinställningar för den. Det här alternativet är inaktiverat som standard.

     ![redigera en kartsamling i molntjänster](images/edit-map-collection-cs.png){width="800" align="left"}



1. Gör något av följande:

   - Om du vill generera utdata för markerade kartor markerar du kartfilerna och klickar på **Generera markerade**.
   - Om du vill generera utdata för alla DITA-kartor med deras konfigurerade förinställningar klickar du på **Generera alla**.

   >[!IMPORTANT]
   >
   > Om en utdatagenereringsprocess för en förinställning eller ett DITA-schema finns i kön eller pågår kan du inte initiera en annan utdatagenereringsåtgärd för samma förinställning eller karta.

## Konfigurera metadataegenskaperna

I kartsamlingen kan du konfigurera flera metadataegenskaper för DITA-kartorna. Välj **Konfigurera metadata** för att öppna sidan **Resursmetadata**. På sidan **Resursmetadata** visas alla kartor som finns i samlingen till vänster.

![konfigurera metadata](images/map-collection-asset-metadata.png){width="800" align="left"}

Utför följande steg för att konfigurera metadataegenskaperna:

1. Du kan välja de kartor som du vill uppdatera metadata för. Som standard är alla DITA-kartor markerade.

1. När du har valt DITA-kartor kan du visa egenskaper som metadata, schemaaktivering (de), referenser, dokumenttillstånd med mera.

1. Uppdatera metadataegenskaperna.

1. Klicka på **Spara och stäng** överst för att spara uppdateringarna.
1. (Valfritt) När du uppdaterar taggarna kan du även välja Lägg till i listrutan **Spara och stäng** för att lägga till de nya taggarna i den befintliga listan.
1. Klicka på **Skicka** i listrutan **Spara och stäng**.
Metadataegenskaperna uppdateras för de DITA-kartor som du väljer gruppvis i kartsamlingen.

>[!NOTE]
> 
>I listrutan **Dokumenttillstånd** kan du bara välja de dokumentlägen som är tillåtna för alla markerade DITA-kartor. Mer information finns i [**Dokumenttillstånd**](./web-editor-document-states.md).

Metadataegenskaperna är synkroniserade med filegenskaperna. När du har uppdaterat dem kan du visa dem på panelen **Filegenskaper** i webbredigeraren.



## Ta bort en kartsamling eller en DITA-karta från kartsamlingen

- Om du vill ta bort en kartsamling markerar du en samling på sidan Kartsamling och klickar på **Ta bort**.
- Om du vill ta bort en DITA-karta från en kartsamling öppnar du kartsamlingen i redigeringsläge, markerar DITA-kartfilen och klickar på **Ta bort från samling**.

Detta tar även bort alla förinställningar eller språkområden som är kopplade till DITA-kartan från kartsamlingen.


## Avbryt en utdatagenereringsaktivitet från en kartsamling

På samma sätt som du avbryter en utdatagenereringsaktivitet från [DITA-kartkonsolen](generate-output-for-a-dita-map.md#id2061H100T5Z) eller [Publish Dashboard](generate-output-publish-dashboard.md#) kan du avbryta en utdatagenereringsaktivitet från en kartsamling. Gå till fliken Utdata i en kartsamling, gå till den publiceringsaktivitet som du vill avbryta och klicka på ikonen **Avbryt det här jobbet** för att avbryta publiceringsaktiviteten.

![](images/cancel-publish-task-map-collection.png){width="800" align="left"}

**Överordnat ämne:**&#x200B;[&#x200B; Utdatagenerering](generate-output.md)
