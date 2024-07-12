---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 4.4.0 har åtgärdats
description: Läs om felkorrigeringarna i version 4.4.0 av Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Åtgärdade problem i version 4.4.0 (januari 2024)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 4.4.0 av Adobe Experience Manager Guides.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.4.0](./whats-new-4-4.md).

Läs mer om [uppgraderingsinstruktioner för version 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Redigering

- Stavningskontrollen i Redigeraren tillåter inte val av förslag. 15045
- Den globala navigeringsknappen fungerar inte och instrumentpanelen kan inte läsas in. 14968
- I Web Editor kan funktionen för hämtning av karta inte utlösa ett popup-meddelande när den är klar att hämtas. 14626
- I Web Editor kan funktionen för hämtning av karta inte hämta en karta med baslinjen. (14622)
- Ogiltigt DTD-fel i Experience Manager Guides. 14482
- Titeln på webbredigeringsfliken trunkeras efter en punkt (.) tecken. 14372
- Felmeddelanden för duplicerade mappningsnamn i Assets-användargränssnittet har inte uppdaterats. (14320)
- Ett fel inträffar i logiken för att skapa versioner när resurser dras och släpps. 14291
- Återanvändbart innehåll hoppar över element-ID:n. 14213
- Inställningskontrollen för att dölja panelen **Språkvariabler** på fliken **Utdata** saknas. (14194)
- Webbredigeraren genererar programfel när en ny referens eller ett nytt ämne läggs till med ett specialschema i **layoutvyn** . 14094
- Utrymmet efter conref `<ph>`-elementet försvinner när ämnet sparas. 13642
- Ett programfel inträffar när DITA-filer sparas innan efterbearbetningen är klar. 13571
- En ankarlänk till `<dlentry>` eller `<dt>`-elementet kan inte visa länktexten. 13543
- Det går inte att läsa in samlingen **Favoriter** i webbredigeraren. 13495
- Om titeln för ett ämne innehåller ett snedstreck `/`, visas bara de bokstäver som kommer efter det på fliken i Web Editor. 13455
- Förhandsvisningen av bilden försvinner inte när du har visat förhandsvisningen i webbredigeraren. 13454
- Citat visar länkar som inte går att klicka på när de skapas med ett unikt ID med blanksteg. 13447
- När du stänger ett ämne efter att du har redigerat det omdirigeras du till AEM hemsida i stället för att gå tillbaka till mappvyn. (13306)
- Popup-fönstret Infoga nyckelord visas inte när rotmappsdefinierade nycklar används i andra ämnen. (12950)
- Stängningsikoner visas inte när mycket stora bilder förhandsvisas på panelen **Versionshistorik** . 12867
- Det går inte att ändra tidszonen för kolumnen **Version skapad den** för baslinjerna. 12711
- Zip-filer känns inte igen i Web Editor och du kan inte dra och släppa dem. (12709)
- Panelen **Versionshistorik** i Assets-gränssnittet visar en felaktig tidsstämpel för fältet **Aktuell**. 12624
- I **layoutvyn** för en bokmapp fungerar inte ett underelement om du använder **Flytta åt höger** för att göra ett markerat kapitel till ett underelement. 12567
- Om du skapar en DITA-fil från en mall med ett filnamn som börjar med numeriska tecken resulterar det i ett namnutrymmesfel. (12188)
- Rotmappsinställningen finns kvar i Web Editor även om användaren inte har angett den explicit från **användarinställningarna**. (11551)
- Innehållet med vissa attribut som används markeras inte i läget **Författare** eller **Förhandsgranska**. (11063)
- Fönstret **Nyckelreferenser** öppnas i Web Editor när taggen `varname` infogas. (10940)
- Om du drar ett ordlisteämne från databasen till en ordlista skapas `topicref`. (10767)
- Förhandsgranskningsfönstret i XML-redigeraren är trunkerat i webbläsarna Google Chrome och Microsoft Edge. (10755)
- Webbredigeraren saknar möjlighet att kapsla in ett element inuti de överordnade elementen. 8791
- Web Editor avinstalleras efter ominstallation av Adobe Experience Manager Guides version 4.3.1. 14519
- Installationsprogrammet för version 4.3.1 påträffar en filterkonflikt, vilket resulterar i att `apps/cq/core/content/projects/properties` åsidosätts. 14517
- En självreferenslänk visas under listan med **brutna länkar** i rapporter. 13539
- Förhandsgranskningsskärmen för fragment fryses. (14840)
- Brutna tecken visas när fragment skapas på koreanska. 13489

## Publicering

- AEM Sites publicering misslyckas och orsakar definitionsfel för filer med `xref` till DITA-filen som börjar med HTTP. (15154)
- I Native PDF kan inte DITA-mappningens metadataegenskaper användas för att fylla i metadata för utdata från PDF. (15159)
- Vid publicering i Native PDF fungerar inte anpassade attribut i villkorsförinställningar för publicering i Native PDF. 14943
- Det går inte att lägga till en anpassad mall från fliken **Utdata** i redigeraren. 14846
- **AEM Site**-förinställningen fungerar inte på grund av en tom mallsökväg. 14804
- AEM Site regeneration misslyckas för DITA-kartor med ämnen som innehåller MathML-ekvationer. (14790)
- Vid ursprunglig PDF-publicering genererar PDF-generering fel vid hämtning av beroenden för `Node.js`-publicering. 14445
- **AEM**-förinställningen tillåter inte val av en mall utanför `/content`-hierarkin i Web Editor. (14260)
- Funktionen för att publicera som innehållsfragment fungerar inte för filer som listas i sökresultaten. (14090)
- Fmdita-komponenter har den hårdkodade sökvägen `delegator.jsp`, vilket förhindrar övertäckningen av AEM Sites-komponenter. (13993)
- Den taggade vyn av PDF-reaktorn i Native PDF fungerar inte som förväntat. (13622)
- Vid ursprunglig PDF-publicering kräver bakgrundsfärgvalet för layouten **Template** en sidinläsning vid återställning till `None`. 13621
- Vid publicering av AEM påträffas ett problem vid implementering i datalagret för stora kartor med scope-peer-länkar. 13531
- Ett problem uppstod vid implementering av datastore för en stor DITA-karta med scope-peer-länkar AEM Site-publicering. (13530)
- Felaktiga ikoner och verktygstips visas för alternativet **Redigera innehåll** i verktygsfältet **Sidlayouter** i mallarna som används vid publicering i PDF. 13492
- Det går inte att aktivera en webbplats med Experience Manager Guides **Massor av Publish Dashboard**. 13439
- I Native PDF-publicering äventyras tillgängligheten eftersom bilder i sidhuvud och sidfot inte visar alternativ text. (12829)
- I AEM Sites-utdata förlorades formatet eller radbrytningarna för elementet `<lines>` med underelement.(12542)
- Det går inte att duplicera sidlayout i PDF utan att lägga till något tillägg automatiskt. (12534)
- Elementetiketternas lokalisering fungerar inte korrekt i AEM Sites-utdata. (12144)
- Anpassade metadata är inte tillgängliga i det slutliga resultatet. (12116)
- `fmdita rewriter` står i konflikt med användarens omskrivarkonfiguration och leder till att långa URL-adresser visas i stället för länkarna. (12076)
- Alternativet **ditaval** saknas i förinställningar på mappprofilnivå som skapats via webbredigerarens gränssnitt. (11903)
- I förinställningen **AEM Plats** fungerar inte alternativet att **generera separata PDF för varje avsnitt**. (11555)
- Inbyggd PDF-publicering saknar stöd för CMYK-färgmodellskonvertering. (10754)
- Vid uppgradering till version 4.3.1 inträffar vissa undantag i noden Native PDF. 14492
- När du genererar utdata från PDF med Native PDF-publicering kommer filnamnet att trunkeras efter en viss period. (13620)


## Förvaltning

- Innehållsreferensen bryts vid kopiering och inklistring av DITA-filer med självreferenslänkar utan GUID. (13540)
- **Originalfilterfiler** fungerar inte med filnamn i webbredigeraren. 13486
- Baslinjen i Web Editor visar titeln för den föregående versionen i stället för den valda versionen av DITA-filen. 13444)
- Om du inaktiverar indexeringen av den överordnade DITA-kartan för att få bättre prestanda kan vissa funktioner påverkas.(12213)
- Villkorsförinställningar för stora DITA-kartor skapas inte. (10936)
- Det går inte att redigera förinställningarna för samlingens första kartor när en kartsamling redigeras. (10649)
- Etiketter från filen `labels.json` visas i slumpmässig ordning i webbredigeraren. (10508)
- Dynamiska baslinjeanrop använder namnet i stället för titeln, vilket leder till att det inte går att exportera DITA-mappnings-API. 14268

## Granska

- Snabbmenyn för högerklickning fungerar inte för **Acceptera** eller **Ignorera** - spåra ändringar. 14607
- Växla till att stänga DITA-avsnitt på Granskningsskärmen fungerar inte i version 4.3.1 av Adobe Experience Manager Guides. 14537
- Symmetriproblem uppstår i den föregående och den aktuella versionen av Web Editor, sida vid sida-granskningspanelen. (14156)
- Det går inte att anpassa e-postmallar för granskningsarbetsflöden med övertäckning. 13954
- Det går inte att klicka på koreanska bilagor på Experience Manager Guides Review-skärmen. 13436
- Karttitel klipps av på skärmen för granskning och samarbete, utan möjlighet att visa hela titeln. (13012)

## Översättning

- Knapparna **Acceptera/avvisa** visas felaktigt för automatisk godkänd mänsklig översättning. 14318
- Internationaliseringsproblem (i18n) inträffar under omvandlingen av icke-engelska DITA-filer till AEM sidor. 14286
- Automatisk godkännande fungerar inte ibland, och undantag uppstår om ett felaktigt värde har angetts för **Översättningsstatus**. 13607
- Baslinjen som exporteras från översättningsinstrumentpanelen misslyckas och öppnas inte på målspråket. (12993)
- Översatt innehåll kan inte synkroniseras från temporära översättningsprojekt, och översättningsguiden för DITA XML-redigeraren visar felaktigt statusen **Pågår** för godkända jobb. (9938)

## Känt fel

Adobe har identifierat följande kända fel i version 4.4.0:

- Version 1.0 visas inte i användargränssnittet för den duplicerade DITA-filen.
