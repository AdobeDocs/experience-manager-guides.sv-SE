---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2024.10.0
description: Läs mer om felkorrigeringarna i version 2024.10.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 64c5318a064d28a42f3f11d2fe5b7d8548e341d8
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 0%

---

# Problem i version 2024.10.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2024.10.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2024.10.0](whats-new-2024-10-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.10.0](upgrade-instructions-2024-10-0.md).


## Redigering

- Alternativet **Sök** fungerar inte i vyn **Source**. 18610
- Elementet `<title>` läggs automatiskt till när elementet `<fig>` infogas som ett fragment. 18562
- Omgenereringen av ämnen misslyckas på grund av fel i OTB-genereringen av ämne eller inkrementellt publicerings-API. 18452
- Experience Manager Guides-instansen blir instabil och felloggarna ökar i storlek upp till 30-40 GB efter åtkomst till Assets användargränssnitt. 18414
- Ikonerna **Checka ut** och **Checka in** visas tillsammans när `autocheckout` har konfigurerats i redigeraren. 18088
- Kopiera och klistra in bilder från redigeringsvyn fungerar inte i version 2024.06.0 av Adobe Experience Manager Guides as a Cloud Service.18062
- `<conref>` för ett ämne som refereras inom en DITA-karta visas inte i förhandsvisningen i redigeraren. 17794
- Stora DITA-kartor läses in långsamt och tar tid att växla till vyn **Layout**. (17590)
- DITA-versionen visar felaktigt användarnamnet i Assets användargränssnitt. 17580
- Fel i duplicerade bild-ID:n i avsnitten hindrar användaren från att spara eller redigera ett ämne. 17528
- Problem inträffar när ett stort antal filer med kompakta datauppsättningar överförs till Experience Manager Guides.17008
- Återgivningsfunktionen PDF i Experience Manager Guides as a Cloud Service fungerar inte så ofta. 16966
- När du skapar en DITA-karta baserad på en mall orsakar OTB DXML-arbetsflödet processavbrott och leder till 503 fel som inte kan hanteras. (16529)
- **Specialtecken** som skrivits med escape-tecken tas bort från avsnittet när de har överförts till Experience Manager Guides. 16495
- Filen har checkats ut av felmeddelandet&quot;&quot; visas felaktigt när filer flyttas från en annan flik, när tokens har gått ut eller när användaren är utloggad. (15223)
- Stora filer läses inte in i Web Editor och gör att webbläsaren låser sig. 13227
- `<Topicref>` som lagts till med `<keyref>` visas inte i PDF. (11974)
- Komponentsökvägen `/libs/fmdita/components/versions` är hårdkodad och användarna kan inte täcka över den. 8779
- Om du öppnar ett DITA-avsnitt eller en DITA-karta på en ny flik för redigering fryses markeringsnavigeringen i Assets-gränssnittet. 4992
- När du hämtar en DITA-karta med stora videofiler uppstår fel i minnet i loggarna och programmet misslyckas i gränssnittet. 18884
- När du infogar en MathML-ekvation som innehåller symbolen &quot;&lt;&quot; genereras ett **ogiltigt tecken** -fel. 18742
- Felaktig UUID-generering under innehållsöverföringsprocessen leder till brutna undermappsreferenser i den inkapslade kartan. 18308
- I vissa fall uppstår fördröjningar i bearbetningen av ett nytt DITA-avsnitt när det skapas från webbredigeraren. 16836
- Det tar för lång tid att söka efter filer i **databasen** i Web Editor och resultaten läses ibland inte in. 16837

## Publicering

- Korsreferensen till nyckeln löses inte i utdata från PDF. 18087
- Felet **duplicate_value** inträffar ibland när en befintlig artikel publiceras om i Salesforce. 17932
- Format och innehållsformatering i kundmallar ändras automatiskt när layouten innehåller metadatafält, vilket ger felaktig formatering i publicerade PDF. (17900)
- Salesforce-anslutningsverifieringen misslyckas med blixtens URL. 17797
- Det refererade PDF aktiveras inte från **den grupperade Publish-kontrollpanelen** under gruppaktiveringen av publicerat innehåll. 17793
- Massaktivering av publicerat innehåll fungerar inte för lokaliserade kartor. 17638
- När du väljer alternativet **Använd metadata som lagts till i topicmeta** sprids inte metadataegenskaperna i dokumentägarna för Native PDF-utdata. 17283
- Villkorsfiltrering i utdata från PDF fungerar inte som förväntat jämfört med DITA-OT. 17095
- Innehållsförteckningen stöder inte `<sub>`- eller `<sup>`-taggar i utdata från PDF. 17028
- AEM och inkrementellt publicerings-API fungerar inte som förväntat. (16666)
- Genereringen av PDF som är inbyggd misslyckas med ett fel som är relaterat till hämtning av beroenden för Node.js. 14445
- `<Conref>` löses inte i `Preview`-läge för Web Editor och utdata från PDF. 17827
- Innehållsreferenser löses inte korrekt för Native PDF om filen som innehåller nyckeldefinitioner inte finns i samma mapp som DITA-kartan. 15062
- När en DITA-karta innehåller rubriknivåer på upp till 7 eller högre behandlas rubrik 7 felaktigt som rubrik på nivå 1 i utdata från PDF. (19698)
- När en innehållspunkt (text) radbryts i ett element visas inte mellanrummen före och efter texten i formaten Förhandsgranska eller Utdata. (19308)
- Arbetsflöden efter generering som utlöses manuellt misslyckas på grund av ett NULL-PEKARUNDANTAG i arbetsflödet, vilket leder till att innehållet överförs 11 gånger. (18880)
- **Massvisa Publish Dashboard** visar tomt för kartor som fortfarande är i översättningsprocessen. (19352)


## Förvaltning

- Sökvägen för överläggsfunktionen är hårdkodad för den koreanska språkfilen och är inte korrekt vald. 17089
- Ändringar/anpassningar som görs i dialogrutan **Spara version** återspeglas inte när du använder Guides Extension Framework. 17828
- InDesign till DITA-konvertering har en hårdkodad konfigurationssökväg så de anpassade konfigurationsfilerna plockas inte. 16891
- Fullständiga referenser/resurser hämtas inte när en DITA-karta som innehåller stora beroenden/referenser hämtas med Baslinje. (19099)


### Granska

- Hämtning av användarlistan när en granskningsaktivitet skapas misslyckas om användarantalet överstiger 25. 17329
- Om ett uppgiftsämne innehåller taggen `<cmd>` i ett eller flera steg visas attributet `importance` som ett prefix i alla steg som innehåller taggen på granskningspanelen. (1969)

## Översättning

- Referenserna för översatta resurser uppdateras inte. 18086
- Referenser filtreras inte korrekt som direkt eller indirekt när de översätts till flera språk. 17891
- Det går inte att skapa XLIFF-projekt med mänsklig översättning. 16964
- Om du lägger till ett uppdaterat ämne i ett aktivt översättningsprojekt skapas ett duplicerat ämne och processen misslyckas. 7688
- Översättningsprojekten som skapades genom att du valde alternativet **Skapa endast struktur** har inte UUID. 18980
- När du väljer ett översättningsprojekt med **översättningsstatus** som **Pågår** öppnas en felaktig sida. 13248)
- Titeln med `<conref>` går inte att matcha på panelerna Baslinje och Översättning i webbredigeraren. 16961

## Kända fel

- Om du öppnar en förinställning för AEM Sites (ej äldre) markeras ämnet som smutsigt.
- Den valda panelen behålls inte när webbläsaren uppdateras från fliken Utdata.
- Det går inte att dra och släppa avsnitt mellan två ämnesreferenser i vyn **Författare**.
- Villkorsfiltrering som används i förinställningen tillämpas inte via **Hämta som PDF**.
- Generering av ett enda ämne från kartpanelen genererar alla ämnen som valts i AEM Sites-förinställningen (ej äldre).
- Ämnets referens visas som brutet i användargränssnittet när det infogas från det övre verktygsfältet på DITA-kartan.
- Generering av inbyggda PDF misslyckas för en DITA-karta om referenser saknas.
- Publicering av ett enda ämne AEM Webbplatsen med villkor misslyckas i en miljö där mikrotjänster är aktiverade.
- När ett ämnes dokumenttillstånd har uppdaterats till **Klar** är ikonen **Starta en ny version** bara tillgänglig i läget **Förhandsgranska** för ämnet.
