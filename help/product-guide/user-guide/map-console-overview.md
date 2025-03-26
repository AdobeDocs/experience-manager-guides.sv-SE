---
title: Kartkonsol i Adobe Experience Manager Guides
description: Lär dig mer om kartkonsolen och de olika funktioner som du kan använda för att publicera och hantera kartor i Adobe Experience Manager Guides.
feature: Publishing
role: User
exl-id: b273b1ae-fbb2-4b35-abce-0df78eeb2e11
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 0%

---

# Översikt över kartkonsolen

Adobe Experience Manager Guides erbjuder en dedikerad konsol, som kallas **kartkonsolen**, för att effektivisera alla karthanterings- och publiceringsuppgifter. Detta centraliserade gränssnitt förbättrar produktiviteten och exaktheten i kartrelaterade aktiviteter genom att ge dig möjlighet att generera utdata, översätta innehåll, få åtkomst till rapporter och mycket mer - allt på ett och samma ställe.

Fliken ![Alternativ för filegenskaper](./images/map-console-screen.png){align="left"}

Kartkonsolens gränssnitt är i första hand uppdelat i två avsnitt - **Navigeringsfältet** och **vänsterpanelen**.

![Nytt](images/map-console-sections.png){align="left"}

- (**A**) **Navigeringsfält**: Verktyg för navigeringsfältets ytor för att växla navigering, justera sidvyn och visa namnet på den markerade kartfilen.

  De funktioner som är tillgängliga i navigeringsfältet förklaras på följande sätt:

   - **Navigeringsväxlare**: Gör det möjligt att navigera till andra sidor utan synliga skarvar - redigeraren eller hemsidan:
   - **Markerad mappningsfil**: Visar namnet på den markerade mappningsfilen. Du kan öppna den i redigeraren eller välja en annan kartfil för kartkonsolen.
   - **Fler åtgärder**: Tillhandahåller alternativ för att navigera till **Assets-gränssnittet** och **inställningarna**. Mer information finns i avsnittet **Fler åtgärder** i dokumentet [Känn till redigeringsfunktioner](./web-editor-features.md#tab-bar) .
   - **Expandera vy**: Gör att du kan expandera sidvyn med hjälp av ikonen **Expandera** . I den här vyn är sidhuvudsfältet dolt och innehållsområdet maximeras. Om du vill gå tillbaka till standardvyn använder du ikonen **Avsluta den expanderade vyn** .

  >[!NOTE]
  >
  > Om du använder Adobe Experience Manager Guides as a Cloud Service visas ytterligare en funktion, [AI Assistant](./ai-assistant.md), i navigeringsfältet.

- (**B**) **Vänster panel**: På den vänstra panelen får du snabb åtkomst till funktionerna Generering och hantering av utdata, Rapport, Baslinje, Villkorsförinställningar, Innehållsöversättning och Workfront (endast om de är konfigurerade).

  Mer information finns i avsnittet [Kartkonsolfunktioner](#map-console-features) nedan.

## Kartkonsolfunktioner

Följande funktioner är tillgängliga på den vänstra panelen när du [öppnar en DITA-kartfil i kartkonsolen](./open-files-map-console.md).

**Utdatagenerering**

Med Kartkonsolen kan du effektivt generera utdata i olika format, bland annat AEM Sites, PDF, HTML5, EPUB, JSON och anpassade utdata via DITA-OT, PDF-publicering och FMPS. Du kan generera utdata för en hel DITA-karta eller så kan du selektivt publicera endast ett fåtal ämnen som du har uppdaterat. Du kan också använda publiceringsfunktionen Baslinje för att selektivt publicera en specifik version av DITA-kartan eller -avsnittet.

Mer information finns i [Utdatagenerering](./generate-output.md).

**Skapa och hantera rapporter**

I en organisationsmiljö vill du kontrollera att den tekniska dokumentationen är fullständig innan du börjar arbeta med den eller publicerar dokumenten. Ett sådant behov blir ännu viktigare i fleranvändar- och storskaliga miljöer. Med Kartkonsolen får du tillgång till Experience Manager Guides-rapporter som ger en användbar inblick i det övergripande hälsotillståndet för innehållet i din databas och hur innehåll används i dokumentationsprocessen.

Mer information finns i [Rapporter i Experience Manager Guides](./reports-intro.md).

**Originalplan**

Experience Manager Guides har baslinjefunktionen som gör att du kan skapa en version av dina ämnen och resurser som sedan kan användas för publicering eller översättning. Du kan också publicera flera förinställningar av samma DITA-karta parallellt.

Lär dig hur du [skapar och hanterar baslinjer i Experience Manager Guides](./web-editor-baseline.md).

**Villkorsförinställningar**

I Experience Manager Guides kan du definiera attribut i dina DITA-avsnitt och använda villkorsförinställningen för att ange vad som ska hända med attributet i det slutliga resultatet. Du kan till exempel lägga till attribut som version 1.0 och version 2.0 i ditt innehåll och använda en villkorsförinställning för att inkludera version 1.0 för version 1.0 och exkludera version 2.0. På samma sätt kan du lägga till attribut som OS Windows och OS Linux i ditt innehåll och sedan inkludera eller exkludera det relevanta innehållet för dina slutliga utdata enligt operativsystemet.

Läs mer om [Villkorsförinställningar](./generate-output-use-condition-presets.md).

**Innehållsöversättning**

Experience Manager Guides har kraftfulla funktioner som gör att du kan översätta ditt innehåll till flera språk. Både arbetsflöden för översättning på människa och dator stöds av Experience Manager Guides.

I kartkonsolen får du tillgång till alla alternativ som krävs för att komma igång med översättningsarbetsflöden. Mer information finns i [Översätt innehåll](./translation.md).


**Workfront**

Workfront-funktionen finns också i kartkonsolen där du kan arbeta med Adobe Workfront-uppgifter direkt från Experience Manager Guides.

Läs mer om [Adobe Workfront-integrering i Experience Manager Guides](./workfront-integration.md).

Du kan bara komma åt den här funktionen om din administratör har konfigurerat **Adobe Workfront**-integrering i din Experience Manager Guides-instans.
