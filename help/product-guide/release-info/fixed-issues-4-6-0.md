---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 4.6.0 har åtgärdats
description: Läs om felkorrigeringarna i version 4.6.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 5a30d427fa579e37a18b0fca65dea96dc486c594
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 0%

---


# Åtgärdade problem i version 4.6.0 (september 2024)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 4.6.0 av Adobe Experience Manager Guides.


Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.6.0](whats-new-4-6.md).

Läs mer om [uppgraderingsinstruktioner för version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Redigering

- Alternativet **Sök** fungerar inte i vyn **Source**. 18610
- Ikonerna **Checka ut** och **Checka in** visas tillsammans när `autocheckout` har konfigurerats i redigeraren. 18088
- Stora DITA-kartor läses in långsamt och tar tid att växla till vyn **Layout**.  (17590)
- Fel i duplicerade bild-ID:n i avsnitten hindrar användaren från att spara eller redigera ett ämne. 17528
- Kopiering och inklistring av ämnen som överstiger 15 kB misslyckas med ett oväntat fel. 17171
- Funktionen för att ändra dokumentläget från panelen **Filegenskaper** fungerar inte som den ska och ändras till läget *Utkast* . 17088
- När du ändrar inställningarna för XML-redigeraren med en anpassad mappprofil uppdateras `ui_config.json` med en felaktig fil. 17011
- Återanvändbara innehållspaneler listar inte element när **användarinställningarna** är inställda på att visa filer efter **filnamn**. 16896
- Delelement i tabelltitelelementet kan inte återges i **förhandsgranskningsläget** i Experience Manager Guides. 16691
- **Specialtecken** som skrivits med escape-tecken tas bort från avsnittet när de har överförts till Experience Manager Guides. 16495
- Vimeo-videofilmer stöder inte helskärmsfunktioner i Experience Manager Guides. (15996)
- Om du klistrar in långa förformaterade textsekvenser i `<pre>` eller `<codeblock>` -element kommer texten att trunkeras. 15859
- Innehållsborttagning sker på grund av dubbletter av GUID:n när mallar installeras via kod men förblir obearbetade. 15858
- Experience Manager Guides kan inte följa attributet **Bearbetningsroll** i läget **Förhandsgranska**. 15787
- Redigeraren tar då och då bort extra text utanför det markerade området. 15708
- Det går inte att kopiera och klistra in stora tabeller från Word-dokument eller HTML i Web Editor. 15369)
- Brist på API:er eller händelser för att hämta attribut som lagts till ett element eller infogats i ett nytt element. 15351
- Det går inte att lägga till taggen `<data>` i taggen `<ol>` i webbredigeraren. (15161)
- Platshållarkomponenten **Element** gör att användargränssnittet fryser. 14957
- Web Editor kan inte överföra PPTX-filer. 14837
- När du söker efter en text i Web Editor återgår markören till den första förekomsten av den sökta texten och trycker på Retur. 14820)
- Om du sparar automatiskt skapas flera problem, markören flyttas och manuella klick krävs i dokumentet. 14253
- Om du trycker på **Retur** i en tabellcell i texten delas inte stycket som förväntat. 14251
- Stora filer läses inte in i Web Editor och gör att webbläsaren låser sig. 13227
- Sökresultaten inaktiveras efter att en fil som hittats via global **Sök och ersätt** har öppnats. (12142)
- I källvyn infogas `</conbody>` ibland på felaktiga platser. 11305
- Komponentsökvägen `/libs/fmdita/components/versions` är hårdkodad och användarna kan inte täcka över den. 8779
- `<conref>` för ett ämne som refereras inom en DITA-karta visas inte i förhandsvisningen i redigeraren. 17794
- Experience Manager DITA-guiden kan inte aktivera funktionen Spara efter att funktionen för automatiskt indrag har använts. 16482
- Funktionen för funktionsbeskrivning kan inte uppdatera fältet Source i XML-redigeraren. 15847
- Funktionen **Share UUID Link** fungerar inte för bilderna i Adobe Experience Manager. (15598)
- I vyn **Författare** uppstår ett problem med kopiera och klistra in när fasta mellanslag används och textspill uppstår. (15541)
- Överlappande textproblem uppstår i `<reltable>`- och `<fig>`-taggar. (15238)
- Flimmer uppstår på panelen **Attribut**. 15237
- I elementet `<othermeta>` i `<topicmeta>` läggs även mappnings-ID:t till tillsammans med elementets ID när en `<conref>` läggs till i en annan DITA-karta. (15226)
- Markören hoppar mellan blockelementen när du tar bort ett tecken eller ord i innehållet. (15224)
- Filen har checkats ut av felmeddelandet&quot;&quot; visas felaktigt när filer flyttas från en annan flik, när tokens har gått ut eller när användaren är utloggad. (15223)
- `<conref>` kan inte uppdateras från panelen **Attribut** när du gör ändringar. (15209)
- Hela cellen markeras när du markerar en bild i en tabellcell. (15188)
- Panelen **Attribut** visas inte i Source-vyn i webbredigeraren. 14387
- `<Topicref>` som lagts till med `<keyref>` visas inte i PDF. (11974)
- Oönskade, hårda blanksteg läggs till när du redigerar i slutet av en tagg i Web Editor. 11786
- Innehåll tas bort medan stavfel i DITA-filer korrigeras. (11610)
- Om du öppnar ett DITA-avsnitt eller en DITA-karta på en ny flik för redigering fryses markeringsnavigeringen i Assets-gränssnittet. 4992
- Om du tar bort granskningsnoder stör det möjligheten att öppna och visa kommentarer i Adobe Experience Manager Guides. 15366)
- DITA-versionen visar felaktigt användarnamnet i Assets användargränssnitt. 17580
- Elementet `<title>` läggs automatiskt till när elementet `<fig>` infogas som ett fragment. 18562
- Problem inträffar när ett stort antal filer med kompakta datauppsättningar överförs till Experience Manager Guides.17008
- Som standard visas inte rätt nyckelord i webbredigeraren, särskilt om nyckelordet har definierats annorlunda i underordnade kartor. 14748
- **Dokumenttillståndet** visas inte när du redigerar egenskaper för fler än 50 filer samtidigt från kartvyn i Web Editor. 14574
- Stängningsknappens beteende är inkonsekvent när funktionen Spara automatiskt används. (10996)
- Valideringsproblem inträffar i MathML-element när nya element infogas eller ekvationer ändras. 10624
- Funktionen Spåra ändringar fungerar inte med text som börjar med koreanska tecken. 14538



## Publicering

- Korsreferensen till nyckeln löses inte i utdata från PDF. 18087
- Felet **duplicate_value** inträffar ibland när en befintlig artikel publiceras om i Salesforce. 17932
- Salesforce-anslutningsverifieringen misslyckas med blixtens URL. 17797
- När du väljer alternativet **Använd metadata som lagts till i topicmeta** sprids inte metadataegenskaperna i dokumentägarna för Native PDF-utdata.17283
- Villkorsfiltrering i utdata från PDF fungerar inte som förväntat jämfört med DITA-OT. 17095
- Innehållsförteckningen stöder inte `<sub>`- eller `<sup>`-taggar i utdata från PDF. 17028
- Crossmap-länkning visar inte alla överordnade kartor i publiceringskontextinställningarna för en länk som har `scope="peer"`. (16700)
- AEM och inkrementellt publicerings-API fungerar inte som förväntat. (16666)
- AEM för webbplatsutdata misslyckas när alternativet **Ta bort överbliven plats** är aktiverat. 15896
- De gamla attributen behålls i **villkorsförinställningarna** när nya eller befintliga attribut läggs till eller tas bort. (15890)
- I JSON-utdata sprids inte metadata från DITA-kartan eller ämnen till JSON-utdatafilerna. 15713
- RTL-språkinnehållet hanteras inte korrekt i publiceringsutdata för Native PDF. 15709
- Publicering i PDF misslyckas när förinställningen byter namn. 15662
- Egenskapen **sourcePath** är felaktig för publicerade AEM. (15502)
- Val och anpassning av språkvariabler fungerar inte korrekt i den inbyggda förinställningen för PDF. (15399)
- Generering av inbyggda PDF misslyckas när en stor formatmall eller layoutmall används. 15344)
- Innehållet återges inte korrekt i publicerade utdata om `<conref>` används med en absolut sökväg. (15222)
- AEM Sites URL-förkortning fungerar inte på grund av konflikter mellan `fmdita rewriter` och `ResourceResolver`. 14793
- Genereringen av PDF som är inbyggd misslyckas med ett fel som är relaterat till hämtning av beroenden för Node.js. 14445
- Attributen **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** och **chunk=&quot;to-content&quot;** visas oavsett i AEM Sites-utdata. (14442)
- `<Conref>` löses inte i `Preview`-läge för Web Editor och utdata från PDF. 17827
- I Native PDF visas kapslade DITA-ämnen felaktigt i innehållsförteckningen. 16742
- Miniatyrbilder som genererats från **Dynamic Media** för videofiler bevaras inte i publicerade utdata. 15656
- Det refererade PDF aktiveras inte från **den grupperade Publish-kontrollpanelen** under gruppaktiveringen av publicerat innehåll. 17793
- Om en mapp som innehåller 2 kB-bilder anges i mappsökvägen i en mappprofil misslyckas ändringarna som används i förinställningen. 14852
- Omgenereringen av ämnen misslyckas på grund av fel i OTB-genereringen av ämne eller inkrementellt publicerings-API. 18452
- Villkorsförinställningen hämtar inte uppdaterade attribut efter uppgradering av Experience Manager Guides. 18174
- Innehållsreferenser löses inte korrekt för Native PDF om filen som innehåller nyckeldefinitioner inte finns i samma mapp som DITA-kartan. 15062


## Förvaltning


- InDesign till DITA-konvertering har en hårdkodad konfigurationssökväg så de anpassade konfigurationsfilerna plockas inte. 16891
- Ostängda **Resurslösningar** orsakar ökat sessionsantal och `PathNotFoundException` fel efter version 4.3.1 av Experience Manager Guides. 15604
- Fel vid installation av stödlinjelänkar i stora databaser. (15160)
- Att skapa en baslinje med Java API fungerar inte med Experience Manager Guides. 14787
- API:t `/bin/fmdita/import` har fastnat i väntande begäran i oändlighet när de överförda resurserna överstiger 500 MB. 14743
- Om du redigerar en befintlig baslinje och väljer en viss version utlöses programfel. 14451
- Körningen av efterprocessskriptet misslyckades på grund av undantaget **FileNotFoundException**. 16517
- Dynamiska titlar med `<conkeyref>` visas inte i rapportämneslistan. 16967
- Felaktiga antal **Ämneslista** inträffar i användargränssnittet för Experience Manager Guides-rapporter på grund av de ej patchade egenskaperna när DITA-resurser kopieras. (15529)
- Ämnen som innehåller externa referenser med %20 i URL:en visar brutna filreferenser. 15347
- Egenskaperna fmditaMaprefs och fmditakeydefrefs visar relativa sökvägar, trots att absoluta sökvägar har angetts för DITA-kartan och -avsnitten. 18353
- Sökvägen för överläggsfunktionen är hårdkodad för den koreanska språkfilen och är inte korrekt vald. 17089
- Standardtiden för att skapa baslinjen i Web Editor visas som 00:00 i stället för den aktuella tiden. (15215)

## Granska

- Hämtning av användarlistan när en granskningsaktivitet skapas misslyckas om användarantalet överstiger 25. 17329
- Granskningsämnen visas inte i rätt ordning. 16319
- Granskningspanelen läses in långsamt i Web Editor. 14680)
- Granskare kan inte lägga till, markera eller stryka över blanksteg vid dokumentgranskning i Experience Manager Guides. 14752
- När en användare uppdaterar en granskningsuppgift får inte alla tilldelade granskare ett meddelande om uppdateringen. 9496

## Översättning

- Referenserna för översatta resurser uppdateras inte. 18086
- Det går inte att skapa XLIFF-projekt med mänsklig översättning. 16964
- Titeln med `<conref>` eller `<conkeyref>` går inte att matcha på panelerna Baslinje och Översättning i webbredigeraren. 16961, 16879
- Översättningsprojekt kan inte lägga till nya språkjobb i Adobe Experience Manager 6.5 SP18 med version 4.3.1 av Experience Manager Guides. 15398)
- **Acceptera översättning** kan inte slutföra översättningen av temporära filer. (14665)
- Om du lägger till ett uppdaterat ämne i ett aktivt översättningsprojekt skapas ett duplicerat ämne och processen misslyckas. 7688
- Referenser filtreras inte korrekt som direkt eller indirekt när de översätts till flera språk. 17891
- XLIFF-baserad översättning misslyckas med felet för användare som inte är administratörer.17296
- Titeln på översatta filer återgår till engelska efter den andra översättningen, även om innehållet har översatts. (15200)
- När du väljer ett översättningsprojekt med **översättningsstatus** som **Pågår** öppnas en felaktig sida. 13248)
- Översättningsprojekten som skapades genom att du valde alternativet **Skapa endast struktur** har inte UUID. 18980


## Kända fel

Adobe har identifierat följande kända fel i version 4.6.0:
- Om du öppnar en **AEM Sites**-förinställning (ej äldre) markeras ämnet som smutsigt.
- Den valda panelen behålls inte vid webbläsaruppdatering från fliken **Utdata**.
- Det går inte att dra och släppa ämnen mellan två `topicrefs` i vyn **Författare**.
- Villkorsfiltrering som används i förinställningen tillämpas inte via **Hämta som PDF**.
- Generering av ett enda ämne från kartpanelen genererar alla ämnen som valts i förinställningen **AEM Sites** (ej äldre).
- Ämnets referens visas som brutet i användargränssnittet när det infogas från det övre verktygsfältet på DITA-kartan.
- Generering av inbyggda PDF misslyckas för en DITA-karta om referenser saknas.
- När ett ämnes dokumenttillstånd har uppdaterats till **Klar** är ikonen **Starta en ny version** bara tillgänglig i läget **Förhandsgranska** för ämnet.



