---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2024.06.0
description: Läs mer om felkorrigeringarna i version 2024.06.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: dff625a841ea9fc758de83b1d830ddffa15646cd
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 0%

---


# Problem i version 2024.06.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av 2024.06.0-utgåvan av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2024.06.0](whats-new-2024-06-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Redigering

- Kopiering och inklistring av ämnen som överstiger 15 kB misslyckas med ett oväntat fel. 17171
- Funktionen som används för att ändra dokumentstatus från  **Filegenskaper** panelen fungerar inte som den ska och ändringar i *Utkast* tillstånd. 17088
- När du ändrar inställningarna för XML-redigeraren med hjälp av en anpassad mappprofil visas `ui_config.json` uppdateras med en felaktig fil. 17011
- I **Databas** panelen, **Filter** sökningen behåller inte värdet för **Utcheckad av** fält när du öppnar **Avancerat filter** -dialogrutan. 16935
- Länkade bilder från ämnena visas inte i baslinjen efter att versionen har skapats. 16931
- Återanvändbara innehållspaneler listar inte element när **Användarinställningar** är inställda på att visa filer efter **Filnamn**. 16896
- Delelementen i tabellrubrikelementet kan inte återges i **Förhandsgranska** läge för stödlinjer för Experience Manager. 16691
- Körning av efterbearbetningsskript misslyckas på grund av **FileNotFoundException** undantag. 16517
- Vimeo-videofilmer har inte stöd för helskärmsfunktioner i Experience Manager-stödlinjer. (15996)
- Klistra in långa förformaterade textsekvenser i `<pre>` eller `<codeblock>` leder till trunkerad text. 15859
- Innehållsborttagning sker på grund av dubbletter av GUID:n när mallar installeras via kod men förblir obearbetade. 15858
- Stödlinjerna för Experience Manager kan inte följa **Bearbetar roll** attribute in **Förhandsgranska** läge. 15787
- Redigeraren tar då och då bort extra text utanför det markerade området.  15708
- Det går inte att kopiera och klistra in stora tabeller från Word-dokument eller HTML i Web Editor. 15369)
- The **Kopiera** funktionen misslyckas för tomma mappar i as a Cloud Service för stödlinjer i Experience Manager. 15353
- Brist på API:er eller händelser för att hämta attribut som lagts till ett element eller infogats i ett nytt element. 15351
- Oförmåga att lägga till `<data>` tagga inuti `<ol>` i Web Editor. (15161)
- När Unified Shell är aktiverat visas **Hantering av versionsetiketter** visas felaktigt **Huvudinnehåll** för versioner utan etiketter. 15039
- Stora filer läses in långsamt i Web Editor, med en fördröjning på några sekunder. 14958
- Tryck på **Retur** i en tabellcell i texten delas inte stycket som förväntat. 14251
- Experience Manager DITA-guiden kan inte aktivera **Spara** efter att du har använt funktionen för automatiskt indrag. 16482
- Granskningsämnen visas inte i rätt ordning. 16319
- I **Upphovsman** en kopiera och klistra in-åtgärd inträffar om du använder fasta mellanslag och resultatet blir att texten flödar över. (15541)

- I `<othermeta>` element inuti `<topicmeta>`när du lägger till en `<conref>`på en annan DITA-karta läggs även mappnings-ID:t till tillsammans med elementets ID. (15226)
- The `<conref>` kan inte uppdateras från **Attribut** när du gör ändringar. (15209)
- När du markerar en bild i en tabellcell markeras hela cellen. (15188)

## Publicering


- Det går inte att visa alla överordnade kartor i publiceringskontextinställningarna för en länk som har `peer @scope`. (16700)
- När du lägger till nya eller tar bort befintliga attribut behålls de gamla attributen i **Förinställningar för villkor**. (15890)
- RTL-språkinnehållet hanteras inte korrekt i Native PDF. 15709
- Den första versionen av PDF skapas inte när en utdatafil för inbyggda PDF skapas. (10305)
- I Native PDF visas kapslade DITA-ämnen felaktigt i innehållsförteckningen. 16742
- Miniatyrbilder som genererats från Dynamic Media för videofiler bevaras inte i publicerade utdata. 15656
- Utdatagenereringen misslyckas för Native PDF Publishing på en ARM64-processor. 16968

## Förvaltning

- Om du redigerar en befintlig baslinje och väljer en viss version utlöses programfel. 14451

## Översättning

- Översättningsprojekt kan inte lägga till nya språkjobb i Adobe Experience Manager 6.5 SP18 i oktober 2023-versionen av Experience Manager Guides. 15398)

## Cloud Service

- Navigeringen i Adobe Experience Manager Tools svarar inte. 17118
- Bygg transformeringsfasen i distributionen av Cloud Service misslyckas med fel från DITA-kodbasen. 14432

## Rapporter

- Felaktig **Ämneslista** antal i användargränssnittet för stödlinjer på grund av ej patchade egenskaper när DITA-resurser kopieras påverkar de rapporter som genereras för en DTIA-karta. (15529)
- Ämnen som innehåller externa referenser med *%20* i URL:en visar brutna filreferenser. 15347


## Kända fel

Adobe har identifierat följande kända fel i version 2024.06.0:

- Publicering i PDF misslyckas när Vimeo-innehåll läggs till i ämnet.
- The **Ämnesegenskaper** visas inte enligt det valda formatet i metadatafälten i en sidlayout.
- `xrefs` går inte att klicka på i **Resurser** visa när Dynamic Media är aktiverat.
