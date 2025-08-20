---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides 2025.08.0
description: Läs mer om felkorrigeringarna i version 2025.08.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 5abe5c153d8cedc7b555d6ca82709557cc38d28f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Problem i version 2025.08.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2025.08.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2025.08.0](whats-new-2025-08-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.08.0](upgrade-instructions-2025-08-0.md).

## Redigering

- **CSS**- och **sidlayoutfiler** i PDF-mallar uppvisar ett inkonsekvent fillåsningsbeteende, vilket tillåter redigeringar även när filerna är låsta. (GUIDES-26688)
- När du uppdaterar sidan efter att du har lagt till anpassade knappar på den vänstra panelen skapas dubblettflikar. (GUIDES-30899)
- När XML-innehåll som innehåller vinkelparenteser (till exempel &lt;/ eller />) läggs till i ett `code block`-element i ett ämne, visas kodblockselementet som tomt i det slutliga resultatet. (GUIDES-31007)
- Värdena för globala variabler `canCheckIn` och `canCheckOut` ställs inte in korrekt när en fil checkas ut och checkas in från redigeringsverktygsfältet.(GUIDES-29890)
- När du öppnar en DITA-karta med det enhetliga skalet aktiverat uppdateras redigeraren regelbundet.(GUIDES-26919)
- När en DITA-karta är markerad i Kartvyn visas markeringsantalet felaktigt i början eftersom mappningens underordnade noder inte är markerade. Rätt antal markeringar och inkludering av alla underordnade noder visas endast vid efterföljande markering. (GUIDES-25663)
- Markeringsfiler hämtas inte vid sökning i databaspanelen med **DITA-ämnesfiltret**. **Sök och ersätt** fungerar inte heller för Markdown-filer och relaterat innehåll. (GUIDES-27133)
- Det går inte att anpassa listrutan **Meny** i redigerarens verktygsfält med hjälp av tilläggsramverket. Det innebär att du inte kan dölja eller visa befintliga knappar eller lägga till nya knappar i listrutan Meny. (GUIDES-28748)

## Resurshantering

- Om du kopierar en mapp med ett stort antal resurser från Assets UI så skapas en API-timeout. Åtgärden fortsätter att köras i serverdelen och slutförs efter en stund, men inget meddelande om att åtgärden lyckades eller misslyckades visas eller inget meddelande visas i användargränssnittet. (GUIDES-30900)
- Kopiera-klistra in-åtgärden som utförs på en mapp i Assets-gränssnittet misslyckas på grund av efterbearbetningsfel. (GUIDES-30840)
- Kopiera och klistra in-åtgärden misslyckas för mappar som innehåller sammansatta resurser (resurser med delresurser) i Assets-gränssnittet. 28107
- Mappar med ett stort antal resurser kan inte läsas in korrekt i databasen. (GUIDES-32500)
- Mappnodnamn visas felaktigt i stället för mapptitlar i Redigeraren. (GUIDES-32402)
- Ett fel inträffar när resurser som inte stöds eller inte får innehålla tecken i filnamnen överförs. (GUIDES-28845)

## Publicering

- I utdata från PDF visas LOI (List of Index) i icke-alfabetisk ordning och kapslade indextermer grupperas inte korrekt, vilket gör indexet svårt att navigera. (GUIDES-29090)
- Listrutan **Kartsidmall** och **Ämnessidmall** i AEM Sites-komponentmappningens utdatamappningsförinställningssida visas tom när målsökvägen innehåller en variabel med kolon. (GUIDES-28119)
- När en DITA-karta innehåller olika typer av ämnesreferenser, t.ex. Concept, Reference eller Task, och sammanfogas med attributet `chunk=to-content` för att generera enkelsidiga utdata på AEM Sites med komponentmappning, publiceras inte innehållet korrekt på grund av publiceringsfel. (GUIDES-28118)

## Baslinje

- Om du kopierar en DITA-karta från Assets-gränssnittet kopieras även den kopplade baslinjen till den nya kartan. (GUIDES-11227)

## Startsida

- Hemsidan blir tom när en av filerna som listas i widgeten **Senaste filer** är baserad på en mall vars källmall inte innehåller någon miniatyrbild. (GUIDES-31506)

## Kända fel

Adobe har identifierat följande kända fel i version 2025.08.0:

- När en fil som öppnas i redigeraren byter namn eller flyttas uppdateras innehållet i redigeringsområdet om du växlar mellan lägena (till exempel **Författare**, **Förhandsgranska** och mer), men det aktiva läget markeras inte visuellt i det nedre högra hörnet. (GUIDES-32719) <br> **Tillfällig lösning**: Uppdatera sidan för att lösa problemet.
- Bilder med blanksteg i filnamn kan inte visas i utdata när de flaggas med villkorsattribut. (GUIDES-33858)
- På panelen **Innehållsegenskaper** stängs attributfältet automatiskt när du försöker uppdatera en referens från dialogrutan **Uppdatera länk**, vilket förhindrar att länken uppdateras. (GUIDES-17767)



