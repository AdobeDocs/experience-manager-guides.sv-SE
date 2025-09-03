---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 5.1.0 har åtgärdats
description: Läs mer om felkorrigeringarna i version 5.1.0 av Adobe Experience Manager Guides.
source-git-commit: 64df76f371867469d738f59a174e7931176e8591
workflow-type: tm+mt
source-wordcount: '1796'
ht-degree: 0%

---

# Åtgärdade problem i version 5.1.0 (september 2025)

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 5.1.0 av Adobe Experience Manager Guides.


Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 5.1.0](whats-new-5-1-0.md).

Läs mer om [uppgraderingsinstruktioner för version 5.1.0](upgrade-instructions-5-1-0.md).


## Redigering

- **CSS**- och **sidlayoutfiler** i PDF-mallar uppvisar ett inkonsekvent fillåsningsbeteende, vilket tillåter redigeringar även när filerna är låsta. (GUIDES-26688)
- När du uppdaterar sidan efter att du har lagt till anpassade knappar på den vänstra panelen skapas dubblettflikar. (GUIDES-30899)
- När XML-innehåll som innehåller vinkelparenteser (till exempel &lt;/ eller />) läggs till i ett `code block`-element i ett ämne, visas kodblockselementet som tomt i det slutliga resultatet. (GUIDES-31007)
- Värdena för globala variabler `canCheckIn` och `canCheckOut` ställs inte in korrekt när en fil checkas ut och checkas in från redigeringsverktygsfältet.(GUIDES-29890)
- När en DITA-karta är markerad i Kartvyn visas markeringsantalet felaktigt i början eftersom mappningens underordnade noder inte är markerade. Rätt antal markeringar och inkludering av alla underordnade noder visas endast vid efterföljande markering. (GUIDES-25663)
- Markeringsfiler hämtas inte vid sökning i databaspanelen med **DITA-ämnesfiltret**. **Sök och ersätt** fungerar inte heller för Markdown-filer och relaterat innehåll. (GUIDES-27133)
- Det går inte att anpassa listrutan **Meny** i redigerarens verktygsfält med hjälp av tilläggsramverket. Det innebär att du inte kan dölja eller visa befintliga knappar eller lägga till nya knappar i listrutan Meny. (GUIDES-28748)
- När en XML-kommentar läggs till i ett element i vyn Source, försvinner inledande och avslutande blanksteg runt kommentaren när du växlar vy. (GUIDES-29781)
- Multimediaalternativen fungerar inte när de finns inuti ellipsikonen (menyn **Mer**) i verktygsfältet. (GUIDES-29583)
- När du skapar ett nytt ämne via Assets-gränssnittet eller redigeraren öppnas inte ämnet automatiskt i redigeraren om inställningen `xmleditor.uniquefilenames` har värdet true i `XMLEditorConfig`. (GUIDES-28171)
- Blanksteg som läggs till i en MathML-ekvation i Source-vyn behålls inte när du växlar redigeringsvyn. (GUIDES-26111)
- Om det inte går att stänga JCR-sessionsanslutningar när ämnen uppdateras eller skapas resulterar detta i minnesläckor och driftavbrott. (GUIDES-26282)
- Om du drar kolumnerna ändras deras bredd från procent till pixelvärden, vilket resulterar i förvrängda eller feljusterade tabeller.(GUIDES-23128)
- När innehåll klistras in i en `code block` eller när mellanslag läggs till i `code block` och vyn växlas, försvinner mellanrummet. (GUIDES-27478)
- När du lägger till en karta till `bookmap` lagras den i `fmditatopicrefs` i stället för i `fmditamaprefs`. (GUIDES-25480)
- Dialogrutan **Infoga bild** återges inte korrekt på en högupplöst eller utzoomad skärm, vilket gör att figurens rubrik och alternativa textfält försvinner. (GUIDES-26459)
- Rutan för infogning av specialtecken i redigeraren kan inte läsas in för tyska språk. (GUIDES-24537)
- Kommentarer och etiketter som läggs till när en ny version av en DITAVAL-fil sparas inte i versionshistoriken med den nya versionen. (GUIDES-24076)
- Utgående och inkommande referenser under **File properties** i den högra panelen uppdateras inte korrekt när du växlar mellan mappningsfiler. Detta problem inträffar särskilt när kartfilerna innehåller ett stort antal referenser. (GUIDES-23344)
- Databasfiltret behåller inte ordningen för anpassade filter som definierats i `ui_config.json`. (GUIDES-21193)
- Om du tar bort flera textrader i ett `codeblock`-element skapas ett tomt utrymme som inte kan tas bort från redigeringsvyn. (GUIDES-20672)
- Nya ID:n kan inte genereras för element när sådana element läggs till via fragment eller skapas via mallar, även när alternativet **för automatiskt genererings-ID** är aktiverat i `XMLEditorConfig`. (GUIDES-21734)
- Om du skapar en ny DITA-resurs från DITA-mallar kopieras replikeringsegenskaperna från motsvarande DITA-mallar. (GUIDES-25145)
- Det går inte att komma åt filegenskaper från databaspanelen om den överordnade mappens namn innehåller tecknet &quot;&amp;&quot;. (GUIDES-25762)
- Om du stänger en ämnesfil kan den sparas som en ny version, även när ämnet är låst. Problemet inträffar specifikt när alternativet **Fråga efter ny version vid stängning** är aktiverat i `XMLEditorConfig`. (GUIDES-23875)
- Databaspanelens aktuella maximala bredd döljer ämne- och mappningsrubriker när innehållshierarkin är djupt inkapslad. (GUIDES-27751)

## Resurshantering

- Om du kopierar en mapp med ett stort antal resurser från Assets UI så skapas en API-timeout. Åtgärden fortsätter att köras i serverdelen och slutförs efter en stund, men inget meddelande om att åtgärden lyckades eller misslyckades visas eller inget meddelande visas i användargränssnittet. (GUIDES-30900)
- Kopiera-klistra in-åtgärden som utförs på en mapp i Assets-gränssnittet misslyckas på grund av efterbearbetningsfel. (GUIDES-30840)
- Kopiera och klistra in-åtgärden misslyckas för mappar som innehåller sammansatta resurser (resurser med delresurser) i Assets-gränssnittet. (GUIDES-28107)
- Mappar med ett stort antal resurser kan inte läsas in korrekt i databasen. (GUIDES-32500)
- Mappnodnamn visas felaktigt i stället för mapptitlar i Redigeraren. (GUIDES-32402)
- Ett fel inträffar när resurser som inte stöds eller inte får innehålla tecken i filnamnen överförs. (GUIDES-28845)
- När du öppnar ett ämne i redigeringsvyn efter en webbläsaruppdatering behålls inte tidigare använda taggar i panelen Filegenskaper. Om du lägger till nya taggar skrivs de befintliga taggarna över, särskilt när ett stort antal taggar är tillgängliga för markering. (GUIDES-29078)
- När du genererar en metadatarapport för en DITA-karta som innehåller ett stort antal resurser, svarar inte knappen **Hantera** eller får ett fördröjt svar. (GUIDES-28443)
- Dokumentstatus från arbetskopian av ett ämne visas mot alla versioner av det ämnet i översättnings- och baslinjegränssnittet. (GUIDES-20674)

## Granska

- Försök att skapa granskningsåtgärder via AEM-arbetsflödet misslyckas konsekvent eftersom granskningsnoden inte skapas. (GUIDES-28214)
- Dokumentvyn i granskningsgränssnittet figursätter inte innehållet för vissa skärmstorlekar, vilket kräver att användarna rullar vågrätt för att se det fullständiga innehållet. (GUIDES-25292)
- Om du uppdaterar informationen för en granskningsåtgärd på kontrollpanelen kan du inte bekräfta om uppdateringen lyckades eller inte. (GUIDES-8051)

## Översättning

- Översättningar som skickas via Experience Manager Guides innehåller inte bifogade resurser, vilket gör att knappen **Start** för översättningsjobb inte är tillgänglig för användare. (GUIDES-28237)

## Publicering

- I utdata från PDF visas LOI (List of Index) i icke-alfabetisk ordning och kapslade indextermer grupperas inte korrekt, vilket gör indexet svårt att navigera. (GUIDES-29090)
- Listrutan **Kartsidmall** och **Ämnessidmall** i AEM Sites-komponentmappningens utdatamappningsförinställningssida visas tom när målsökvägen innehåller en variabel med kolon. (GUIDES-28119)
- När en DITA-karta innehåller olika typer av ämnesreferenser, t.ex. Concept, Reference eller Task, och sammanfogas med attributet `chunk=to-content` för att generera enkelsidiga utdata på AEM Sites med komponentmappning, publiceras inte innehållet korrekt på grund av publiceringsfel. (GUIDES-28118)
- Om du publicerar en DITA-karta med attributet `chunk=to-content` skapas dubbletter av JCR-noder i den nya AEM Sites-utdatafilen, vilket leder till en överflödig innehållsstruktur i AEM Sites. (GUIDES-28104)
- Om ett ämne har attributet `chunk =to-content` och utdata är inställt på att använda ämnesrubriker som sidnamn, visar det genererade sidnamnet felaktigt ordet **chunk** i stället för att det ursprungliga ämnesnamnet behålls när du publicerar en DITA-karta med de nya AEM Sites-utdata. (GUIDES-28102)
- Egenskapen `cq:template` som angetts i AEM Guides ämnesmall för ny AEM Sites-publicering visar ett felaktigt värde, vilket påverkar mallstrukturen och återgivningen av innehåll. (GUIDES-27789)
- Den inbyggda PDF-publiceringen fortsätter oavbrutet om DITA-innehållet har en webblänk utan omfång som `external`. (GUIDES-26434)
- Publicering av inbyggda PDF-filer och AEM-webbplatser stoppas och köas om det finns fel i innehållet. (GUIDES-26516)
- När du genererar AEM Site-sidor med rubriker som innehåller flera ord avgränsade med blanksteg, visas bindestreck i stället för blanksteg. (GUIDES-27903)
- Ett ogiltigt metadataegenskapsnamn kommer inte att matchas för Native PDF och visas som `unresolved property name` i **dokumentegenskaper**. (GUIDES-25680)
- Flerradstext i `codeblock` orsakar textspillproblem under generering av PDF. (GUIDES-15541)
- När du lägger till kartor i kartsamlingen visas andra resurser än kartor (till exempel ämnen) och de översatta kartspråken sorteras inte heller korrekt.(GUIDES-25085)
- I tidigare utdata från AEM Sites går det inte att tolka avsnittslänkar i kapslade avsnitt i en karta korrekt när du anger det manuellt i Source-läge eller när innehållet importeras från en extern källa. I stället för att navigera till det avsedda avsnittet, dirigeras de om till huvudämnet som innehåller det kapslade ämnet. (GUIDES-26103)
- Om attributet `scope=external` saknas i externa länkar i ett DITA-avsnitt misslyckas publiceringen i HTML5 utan att ange de filer där attributet saknas i felloggarna. (GUIDES-25969)
- Det går inte att bädda in videolänkar i PDF även när alternativet **Bädda in multimediafiler** är aktiverat i PDF-förinställningen. (GUIDES-9989)
- Det går inte att skicka metadataegenskaperna för att mappa landningssidor som genererats med den nya AEM Sites-publiceringen. (GUIDES-27288)

## Baslinje

- Om du kopierar en DITA-karta från Assets-gränssnittet kopieras även den kopplade baslinjen till den nya kartan. (GUIDES-11227)
- När du skapar en ny baslinje med ett stort antal etiketter kommer alla etiketter inte att kunna hämtas. (GUIDES-16232)

## Startsida

- Hemsidan blir tom när en av filerna som listas i widgeten **Senaste filer** är baserad på en mall vars källmall inte innehåller någon miniatyrbild. (GUIDES-31506)

## Plattform

- Prestandaproblem som längre inläsningstider och återkommande tidsgränser observeras när du arbetar med stora samlingar. (GUIDES-29065, GUIDES-28793)
- Sårbarheter som är kopplade till det borttagna Guava-biblioteket som används i AEM Guides-komponenter som överförts till Experience Manager Guides.(GUIDES-27402)

## Kända fel

Adobe har identifierat följande kända problem i version 5.1.0:


- Den senaste åtgärdsnivåkommentaren visas i e-postmeddelandet till aktivitetsinitieraren om granskaren slutför uppgiften utan att lägga till någon kommentar. (GUIDES-33590)
- I dialogrutan Sammanfoga visas huvudinnehållet felaktigt i listrutan i stället för de tillgängliga versionerna av det markerade ämnet. (GUIDES-30820)
som länken blir operativ. (GUIDES-30820)
- Om du växlar mellan förinställningar som använder samma baslinje inaktiveras knappen Spara för den aktuella förinställningen. (GUIDES-28025)
- En tom rad infogas automatiskt när nytt innehåll klistras in på en ny rad i ett kodblockselement.(GUIDES-27842)
- Ett ämne på en DITA-karta kan inte publiceras i AEM Sites-utdata när det används som både keydef och topicref i dess underpunkter. (GUIDES-2269)
- På panelen Innehållsegenskaper stängs attributfältet automatiskt när du försöker uppdatera en referens från dialogrutan Uppdatera länk, vilket förhindrar att länken uppdateras. (GUIDES-17767)