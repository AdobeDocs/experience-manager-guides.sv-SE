---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 5.0.0 har åtgärdats
description: Läs mer om felkorrigeringarna i version 5.0.0 av Adobe Experience Manager Guides.
source-git-commit: 5ae05935d254b03ad99221bd5f65dbb6a3580c5f
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 0%

---

# Åtgärdade problem i version 5.0.0 (mars 2025)

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 5.0.0 av Adobe Experience Manager Guides.


Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 5.0.0](whats-new-5-0-0.md).

Läs mer om [uppgraderingsinstruktioner för version 5.0.0](upgrade-instructions-5-0-0.md).


## Redigering

- När du uppdaterar villkor från mappprofilen går alla villkorsgrupper förlorade och villkoren förenklas. 23526
- Om du ändrar värdet för rubrikraderna för en tabell på panelen **Innehållsegenskaper** tillämpas inte det uppdaterade värdet. 23213
- För efterföljande övergångar för dokumentläget Stödlinjer krävs en uppdatering av sidan. (19421)
- När du lägger till ämnen i DITA-kartan med hjälp av dialogrutan **Ämnesreferens** i vyn **Författare** infogas de markerade avsnitten i omvänd ordning om de markeras. 8031
- När du växlar mellan vyn **Författare** och vyn **Source** tas radavståndet i elementen `<pre>` eller `<codeblock>` bort och filen sparas med den här borttagningen. (1987)
- Dokumentläget som är markerat som **Klar** återgår till **Utkast** innan en ny version sparas, vilket resulterar i att läget **Klar** inte bevaras i någon dokumentversion. (2006)
- När listobjekt flyttas utanför paragrafen, försvinner innehållet i listobjektet. (22764)
- När du lägger till ämnen i DITA-kartan med hjälp av dialogrutan **Ämnesreferens** i vyn **Författare** infogas de markerade avsnitten i omvänd ordning om de markeras. (22858)
- När du lägger till nya ämnesreferenser i DITA-kartan med hjälp av dialogrutan för elementet för ämnesreferens **i vyn** Layout **visas de tillagda referenserna som brutna länkar.** (22859)
- När du högerklickar på taggen `<simpletable>` i ett ämne visas inte alternativet **Byt namn** . (22860)
- När du infogar en `xref` som använder nyckelbaserad referens med länktext, visas inte länktexten i Experience Manager Guides. 18775
- Om du drar och släpper en bild i ett ämne i vyn **Författare** bryts bildreferensen, vilket leder till dataförlust. 25769
- Om du söker efter filer i databasen med funktionen **Sök och filtrera** kan du inte markera flera filer. (25104)
- När du kopierar en bild från en extern produkt (till exempel MS PowerPoint) och klistrar in den i stödlinjer, bryts funktionen att överföra resursen direkt för användning i filen. 24983
- Om du drar en `topicref` över en annan (i vyn **Författare** eller **Layout**) uppmanas du att bekräfta ersättningen i stället för att kapsla. Om du väljer **Nej** i bekräftelsedialogrutan ersätts ändå innehållet, vilket leder till dataförlust. 18602
- Du kan inte lägga till flera kortkommandon i en enskild händelse, och du kan inte lägga till ett argument i en händelse när du utlöser den från ett kortkommando. (19066)
- När du läser in webbläsaren öppnas den tidigare stängda bildfliken igen. (267)
- Om du delvis markerar text i ett stycke eller listelement och drar den utanför elementet, försvinner innehållet när du växlar mellan vyerna **Författare** och **Source**. (25790)

## Publicering

- Publicering till Salesforce misslyckas om innehållet innehåller fasta mellanslag. (23664)
- För kartor med trasiga länkar misslyckas Salesforce publicering och förloppsindikatorn visas i oändlighet. 24963
- För ämnen som innehåller fel som brutna länkar misslyckas Salesforce publicering och förloppsindikatorn visas i oändlighet. (22985)
- Den inbyggda PDF-publiceringen misslyckas för **PDF/X-4**-överensstämmelsealternativet. Ett fel uppstod när **PDF/X-4-dokument kräver en titel som inte är tom**. 16904
- När platshållartext används går det inte att matcha korsreferenser som använder `<keyref>` i PDF. (19365)
- Inbyggd PDF-generering misslyckas för innehåll med **segmentattributet** inställt på **till-innehåll**. 21772
- När du genererar inbyggda PDF-utdata stöds inte elementet `ditavalref`. 16320)
- När du redigerar stora CSS-filer i den inbyggda PDF CSS-redigeraren ser du en avsevärd fördröjning. 16915
- Vid HTML5-baserad publicering används flaggan generate.copy.outer automatiskt i DITA-OT. (24299)
- Korsreferensen konverteras till relativ länk även när länkens **scope** är inställt på **external**. 23059
- När en ICC-fil är tillgänglig på en intern sökväg kan den inte markeras i **Utskrift** -inställningarna för den inbyggda PDF-förinställningen. 14741
- Publiceringen misslyckas när flera publiceringsbegäranden initieras för olika kartor med samma förinställning för mappprofil. (18800)
- Publiceringen misslyckas för ämnen som har metadata/egenskap med flera värden när de skickas till DITA OT. (19001)
- Dialogrutan **Redigera egenskaper** för en baslinje visar inte tidigare sparade villkor för dynamisk baslinje.  23964
- Baslinjen inkluderar inte indirekta referenser när innehållet är i det slutliga dokumentläget. (19148)
- Inställningen **Sanera sidnamn och filnamn för AEM Sites och andra utdataformat** kan användas för alla utdataformat. 7651
- Om en extern länk innehåller ett UUID, fortsätter den efterbearbetningen och konverterar den externa länken till UUID-länken, vilket bryter länken i webbredigeraren och även på publiceringswebbplatserna. (22574)


## Förvaltning

- Titeln och ikonen för dialogrutan **Tvinga borttagning** är feljusterade i användargränssnittet i Assets. 21933
- När en JSON uppdateras i mappprofilen för XML-redigerarkonfigurationen stör sparåtgärden konfigurationen av XML-redigeraren. (22414)
- När du duplicerar en mappprofil kopieras även dess administratörsanvändarlista från den ursprungliga mappprofilen. (19067)
- Ett fel inträffar när stora mappar (som innehåller en stor mängd DITA-innehåll, upp till 200 000 objekt) flyttas från Assets UI. (20107)
- Om du redigerar **mappprofilen** med ett enhetligt gränssnitt aktiverat, blir gränssnittet tomt. (22212)
- När du tar bort mappar som innehåller ett stort antal filer misslyckas åtgärden. 17107
- När du avbryter/tar bort översättningsjobbet eller tar bort projektet visas statusen **Pågår** på översättningspanelen. 18417
- När du skickar två versioner av ett oöversatt ämne samtidigt med en icke-äldre översättning och godkänner den andra versionen före den första, bryts översättningsprojektet med den första versionen. (22200)


## Granska

- När du väljer flera ämnen för granskning på en karta visar det e-postmeddelande som granskaren får att alla ämnen på kartan är tillgängliga för granskning, inte bara de markerade. 23214
- Ämnestitel och -ikon är feljusterade i gränssnittet för att skapa en granskning. (11670)


## API:er

- Ett fel inträffar när du skapar en **baslinje** med hjälp av API:t för stödlinjer genom att utlösa tjänsten **BaslinUtlis**. (19385)

## Kända fel

Adobe har identifierat följande kända problem i version 5.0.0:

- I vissa fall fungerar inte låsfunktionen för CSS-filer som förväntat, vilket gör att andra användare kan redigera och spara filerna även när de är låsta av en annan användare.
- Det går inte att stänga Kartkonsolvyn när Baslinjen är smutsig med autosparläge aktiverat.
- När du tillämpar förinställda ändringar återspeglas de inte i förinställningarna som redan har skapats på kartan om förinställningsnamnet innehåller något versaltecken.
- Positionen för bakgrundsfärgen är feljusterad i gränssnittet för **villkorspanelen**.
- När du använder bilden som `<keyref>` visas inte bildens **referenstyp** i **multimedierapporten**.
- När du använder bilder som variabler i PDF-mallen löses den inte i utdata.
- I rapporter för **ämneslista** misslyckas sortering efter titel för resurser med `<conref>` eller `<conkeyref>` i titeln, vilket gör att posterna alltid visas överst.
- När du byter mappprofil återspeglas inte direkt ändringar i användargränssnittet utan att webbläsaren uppdateras.
- De anpassningar av tilläggsramverket som gjordes före Guides 5.0.0 kanske inte fungerar som de ska.
- Den fullständiga innehållsförteckningen för kartan uppdateras inte när du selektivt publicerar ämnen från kartan.
- Publicering av en karta som innehåller en markeringsfil med interna bildreferenser misslyckas på Windows-servrar.
- Punktlistan konverteras inte till numrerad lista i Markdown.
- Publicering till AEM-webbplats misslyckas när markeringsfiler hänvisas till på en karta.


