---
title: Versionsinformation | Åtgärdade problem i Adobe Experience Manager Guides, version 2026.03.0
description: Läs mer om felkorrigeringarna i version 2026.03.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: 6eca85f5-d7d3-4486-8b32-8af3a6cce4ee
hidefromtoc: true
source-git-commit: 22ea3fe3ccb974fe3795299f7815e7aae78d41e7
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# Problem i version 2026.03.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2026.03.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2026.03.0](whats-new-2026-03-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2026.03.0](upgrade-instructions-2026-03-0.md).

## Redigering

- När du redigerar en schemafil (`*.sch`) och använder funktionen Sök och ersätt visas panelen Sök och ersätt delvis utanför skärmen längst ned, vilket förhindrar åtkomst till dess inmatningsfält och kontroller. (GUIDES-38412)

## Publicering

- När samma ämne återanvänds på flera kartor med olika villkorsstyrda förinställningar skrivs ämnesinnehållet över när du publicerar den senaste kartan till Salesforce, vilket resulterar i att felaktiga data visas för användare av tidigare publicerade kartor. (GUIDES-37806)
- När du publicerar en ursprunglig PDF för en karta som innehåller villkorsstyrd bearbetning eller vissa kapslade kartor visas inte `dc:title` som definieras i kartan på PDF-omslaget, vilket resulterar i att omslagsrubriken saknas. (GUIDES-37733)
- Generering av utdata för en AEM-plats (med hjälp av sammansatt komponentmappning) för en karta misslyckas och resulterar i ett fel när variabeln `map_title` finns i utdatasökvägen. (GUIDES-36968)
- När en utdatasökväg med ett avslutande snedstreck anges i den ursprungliga PDF-utdatainställningen läggs ytterligare ett avslutande snedstreck automatiskt till, vilket resulterar i en dubbel snedstreckssökväg som gör att PDF-överföringen misslyckas i vissa scenarier. (GUIDES-34932)
- När du publicerar AEM Sites-sidor som genererats från DITA-innehåll via Snabbpublicering eller Hantera publikation publiceras de associerade DITA-resurserna oavsiktligt. (GUIDES-27967)
- När du publicerar en karta till AEM Sites (med äldre komponentmappning) tolkas inte korsreferenser (`xrefs`) med `scope = peer` som aktiverar underordnade element för ett ämne (t.ex. stycken) i en annan karta till det specifika element-ID:t, utan tolkas bara till det överordnade ämnet, vilket gör att sidan läses in i början av ämnet i stället för att bläddras till det avsedda avsnittet. (GUIDES-21802)


## Översättning

- När en bild som initialt hanteras som en språkspecifik resurs med en viss version (till exempel under `/en/`) flyttas ut till en global mapp med en uppdaterad version och baslinjeexport utförs, fortsätter den nya baslinjen att referera till inaktuella språkspecifika versioner av den bilden, vilket leder till en misslyckad baslinjeexport. (GUIDES-39394)
- Vid bearbetning av översättningsprojekt som skapats utanför Experience Manager Guides genereras flera felloggmeddelanden om att egenskapen *`fmTarget`inte hittades*. (GUIDES-37804)

## Baslinje

- När du skapar en dynamisk baslinje slutar ibland redigeraren att svara på flera samtidiga API-begäranden, vilket gör att alla andra åtgärder avbryts. (GUIDES-39054)

## Granska

- När du tilldelar en användare till en granskningsåtgärd visas i listrutan alla användare i stället för bara de som är kopplade till de valda projekten, vilket resulterar i ogiltiga användaralternativ. (GUIDES-37781)

## Rapporter

- När du öppnar en rapport för en karta är inläsningen av filterpanelen fördröjd (GUIDES-39385)

## Kända fel

Adobe har identifierat följande kända fel i version 2026.03.0:

- En tom skärm läses in när en dubblettförinställning för ServiceNow Knowledge Base skapas. (GUIDES-42732)
- API:t för hämtning av dokumenttillstånd returnerar ett null-svar för vissa filer, vilket gör att felaktiga dokumentlägen visas i användargränssnittet. (GUIDES-42561)
- Gränssnittsanpassningar som baseras på fliknamn i Map Dashboard tillämpas inte. (GUIDES-42285)
- När en fil är öppen i både Redigeraren och sökpanelen tas den bort och uppdateras i Utforskarlistan om du tar bort den från Utforskarpanelen, men filen fortsätter att visas på sökpanelen när sidan uppdateras. (GUIDES-41935)
- När en aktiv granskningsaktivitet uppdateras och ett ämne som redan ingår i granskningen tas bort och sedan läggs till igen utan att du behöver klicka på **Uppdatera**, går granskningsinformationen förlorad på fliken Granskare.   (GUIDES-38774)
- Om du väljer ett ämne i förhandsgranskningsläget markeras det inte i kartvyn om ämnet finns inuti bokmappstaggar (förhandsgranskning, kapitel, del eller underrubrik) eller en del av cykliskt innehåll. (GUIDES-42416)
- I Assets-gränssnittet aktiveras inte knappen **Flytta** vid det första försöket när fler än två filer eller mappar är markerade. (GUIDES-42721) <br> **Tillfällig lösning**: När du har markerat fler än två filer eller mappar väntar du några sekunder innan du väljer målmappen.
- När du navigerar till **användarinställningar** i redigeraren och uppdaterar rotkartan när förhandsgranskningsläget är öppet i redigeraren, läses kartan in som en tom skärm när du återgår till redigeraren. (GUIDES-42412) <br> **Tillfällig lösning**: Problemet åtgärdas om du uppdaterar förhandsgranskningen med ikonen **Uppdatera** som finns i förhandsgranskningsläget.
- Om du byter namn på en befintlig mall uppdateras inte namnet på panelen **Utdatamallar** förrän sidan uppdateras manuellt. (GUIDES-42528)<br> **Tillfällig lösning**: Uppdatera webbläsaren för att visa det uppdaterade mallnamnet på panelen Utdatamallar.
