---
title: Frågor och svar om publiceringsprestanda och skalbarhet i Adobe Experience Manager Guides
description: Läs mer om de vanliga frågorna om publiceringsprestanda och skalbarhet i Adobe Experience Manager Guides.
source-git-commit: d128860bdff78c100ba348b54a237b237171635f
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Vanliga frågor

Nedan följer en lista med svar på vanliga frågor som ger detaljerad information om hur Adobe Experience Manager Guides hanterar publiceringsarbetsflöden, skalningsbeteende och infrastrukturprestanda. Det är avsett för användare, administratörer och dokumentationsteam som använder Experience Manager Guides för storskalig publicering. Bilden förklarar det övergripande arbetsflödet i Experience Manager Guides Publishing Architecture.

![](images/IO_runtime.drawio.png){align="left"}


## Hur många publiceringsförfrågningar kan Experience Manager Guides köra per dag?

Antalet publiceringsbegäranden som Experience Manager Guides kan behandla per dag beror på innehållets storlek och typ. Enligt konfigurationen tillåter systemet ett publiceringsjobb per processorkärna. I den aktuella konfigurationen kan 20 publiceringsjobb köras parallellt (2 pod × 10 kärnor vardera).

När produktionsmiljön skalas automatiskt kan det här antalet öka till 40 samtidiga publiceringsjobb när poderna skalas upp till 4.

## Hur många publiceringsbegäranden kan köras samtidigt innan de köas?

- Minimivärde (standard): 20 publiceringsjobb (2 pod)
- Maximalt (skalat): 40 publiceringsjobb (4 pod)

Antalet kan variera beroende på serverbelastningen. Om andra Sling-jobb i bakgrunden körs delar de processorkärnor, vilket kan minska samtidigheten till under 20.

## Påverkar körning av flera publiceringsbegäranden andra programfunktioner, som redigering av .dita-filer?

Prestandan kan påverkas, men är i allmänhet minimal. Den största bearbetningen görs i IO-miljön (serverlös publiceringstjänst), medan AEM-instansen huvudsakligen utför I/O-åtgärder för beroendegenerering och statusavsökning. Därför är användningen av CPU i AEM fortfarande låg, och redigerings-/redigeringsupplevelserna påverkas i stort sett inte.

## Hur hanterar Experience Manager Guides stora filer och grafik som SVG- eller DITA-filer som överstiger 500 kB?

Alla stora filer komprimeras och lagras i JCR (Java Content Repository). IO-miljön hämtar det fullständiga zip-paketet innan publiceringen initieras. Även vid hantering av flera stora filer (t.ex. 500 kB var) påverkar detta inte nedladdnings- eller överföringshastigheten nämnvärt på grund av optimerad paketering och parallell I/O-hantering.

## Vilken publiceringsinfrastruktur och konfiguration använder Experience Manager Guides?

Experience Manager Guides använder serverlösa mikrotjänster utan behållare för publicering. Varje ny version av publiceringstjänsten släpps som en Docker-bild som automatiskt distribueras i Adobe molnmiljö. Den här designen säkerställer:

- Inget dedikerat infrastrukturunderhåll för kunder
- Automatisk skalning för att hantera publiceringskrav
- Snabba uppdateringar och minimala driftavbrott

## Om publiceringskön eller hanteringssystemet kraschar på grund av överbelastning, kommer andra AEM-funktioner att påverkas?

Nej, Experience Manager Guides har en feltolerant arkitektur. Om publiceringskön överbelastas görs nya försök att utföra begäranden automatiskt och pods autoscale för att hantera den ytterligare belastningen. Efter ett visst tröskelvärde används belastningsbegränsning för att bibehålla stabiliteten. Övriga programområden (redigering, granskning, resurshantering) påverkas inte.

## Finns det något övervakningsverktyg eller loggåtkomst som kan identifiera när Experience Manager Guides är tungt belastat (liknande Jenkins-övervakning)?

Nej, för närvarande har du inte tillgång till interna övervakningsverktyg. För Adobe interna team kan man övervaka med:

- Splunk för logg och felspårning
- Kubernetes (K8s) CLI för kontroll av prestanda och skalningsbeteende på pod-nivå

Om prestandan försämras bör man kontakta Adobe Support för att få igång en undersökning och analys.

## Vilken bearbetning utförs innan en publiceringsbegäran skickas till mikrotjänsten?

När du utlöser en publiceringsbegäran från fliken Förinställningar i kartkonsolen utförs följande steg:

1. Systemet godkänner begäran och validerar förinställningarna för baslinje och villkor.
2. AEM samlar alla kvalificerande DITA-resurser och beroenden.
3. Dessa resurser paketeras i ett zip-paket.
4. Publiceringstjänsten utan server snurrar upp en Docker-behållare, laddar ned materialet, utför publiceringsåtgärden och placerar tillbaka de genererade utdataartefakterna i Experience Manager Guides.

Det här arbetsflödet säkerställer tillförlitlig, isolerad och skalbar publicering.

## Hur lång tid tar en karta innan den börjar publiceras i mikrotjänstbehållaren och vilka faktorer definierar den här tiden?

En publiceringsbegäran tar normalt några minuter innan den skickas till mikrotjänstbehållaren. Den här starttiden används för beroendeaggregering inom AEM.

När begäran har tagits emot på den serverlösa publiceringstjänsten beror den totala publiceringstiden på:

- DITA-kartans storlek
- Antal ämnen och medieresurser
- Komplexitet i villkorat innehåll och formateringsregler

Större eller mer komplexa kartor kan ta proportionellt lång tid att publicera.

## Kan Experience Manager Guides prioritera publiceringsförfrågningar i kön (istället för First-Kom, First-Serve)?

För närvarande behandlas alla publiceringsjobb på samma sätt och enligt FCFS-modellen (First-Kom, First-Serve). Det finns för närvarande ingen prioriteringsmekanism.

I framtida releaser kan dock prioriteringslogik (t.ex. baserad på jobbstorlek eller affärsmässig betydelse) introduceras som en del av förbättringen av köoptimeringen.

## Hur hanterar Experience Manager Guides automatisk skalning för publiceringsbegäranden?

Experience Manager Guides publiceringsinfrastruktur har stöd för automatisk skalning baserat på inläsning. Efterfrågan på publicering ökar:

- Ytterligare rutor (behållare) snurras automatiskt.
- Varje ruta kan bearbeta flera publiceringsjobb parallellt.
- När belastningen minskar skalas rutorna ned för att optimera kostnader och prestanda.

Detta garanterar hög tillgänglighet, konsekventa prestanda och minimal kötid vid toppbelastning.

## Vad händer om ett publiceringsjobb misslyckas eller om tidsgränsen överskrids?

Om en publiceringsbegäran misslyckas på grund av ett tillfälligt problem (till exempel nätverksavbrott, tidsgräns för tjänsten):

- försök görs automatiskt på nytt baserat på återförsökslogik som konfigurerats i publiceringstjänsten.
- loggar och felmeddelanden samlas in i backend-modulen för diagnostik.
- kan du visa felstatus och försöka publicera manuellt från kartkonsolen vid behov.

## Kan du övervaka eller spåra förloppet för ett publiceringsjobb?

Ja, Experience Manager Guides tillhandahåller statusuppdateringar i realtid på fliken Förinställningar i kartkonsolen, inklusive:

- Jobbstart och slutförandetid
- Aktuell fas (komprimering, utskick, publicering eller överföring av resultat)
- Felmeddelanden (om sådana finns)

Detta hjälper er att förstå hur arbetet fortskrider och identifiera eventuella förseningar.

## Vilka är de bästa sätten att förbättra publiceringsprestanda i Experience Manager Guides?

Följ dessa standarder för att få optimal publiceringshastighet:

- Undvik onödiga stora bildfiler och ämnen som inte refereras
- Använd baslinjer för att begränsa publiceringens omfattning
- Se till att DITA-mappningshierarkier är hanterbara och välorganiserade
- Schemalägg omfattande publicering under lågtider
- Använd villkorsstyrda filter effektivt för att minska bearbetningsbelastningen




