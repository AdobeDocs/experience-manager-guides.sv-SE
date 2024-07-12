---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2024.06.0
description: Läs mer om felkorrigeringarna i version 2024.06.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 0%

---

# Problem i version 2024.06.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2024.06.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2024.06.0](whats-new-2024-06-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Redigering

- Kopiering och inklistring av ämnen som överstiger 15 kB misslyckas med ett oväntat fel. 17171
- Funktionen för att ändra dokumentläget från panelen **Filegenskaper** fungerar inte som den ska och ändras till läget *Utkast* . 17088
- När du ändrar inställningarna för XML-redigeraren med en anpassad mappprofil uppdateras `ui_config.json` med en felaktig fil. 17011
- I panelen **Databas** behåller sökningen **Filter** inte värdet för fältet **Utcheckad av** när dialogrutan **Avancerat filter** öppnas igen. 16935
- Länkade bilder från ämnena visas inte i baslinjen efter att versionen har skapats. 16931
- Återanvändbara innehållspaneler listar inte element när **användarinställningarna** är inställda på att visa filer efter **filnamn**. 16896
- Delelement i tabelltitelelementet kan inte återges i **förhandsgranskningsläget** i Experience Manager Guides. 16691
- Körningen av efterprocessskriptet misslyckades på grund av undantaget **FileNotFoundException**. 16517
- Vimeo-videofilmer har inte stöd för helskärmsfunktioner i Experience Manager Guides. (15996)
- Om du klistrar in långa förformaterade textsekvenser i `<pre>` eller `<codeblock>` -element kommer texten att trunkeras. 15859
- Innehållsborttagning sker på grund av dubbletter av GUID:n när mallar installeras via kod men förblir obearbetade. 15858
- Experience Manager Guides kan inte följa attributet **Bearbetningsroll** i läget **Förhandsgranska**. 15787
- Redigeraren tar då och då bort extra text utanför det markerade området.  15708
- Det går inte att kopiera och klistra in stora tabeller från Word-dokument eller HTML i Web Editor. 15369)
- Funktionen **Kopiera** fungerar inte för tomma mappar i Experience Manager Guides as a Cloud Service. 15353
- Brist på API:er eller händelser för att hämta attribut som lagts till ett element eller infogats i ett nytt element. 15351
- Det går inte att lägga till taggen `<data>` i taggen `<ol>` i webbredigeraren. (15161)
- När Unified Shell är aktiverat visas **Huvudinnehåll** felaktigt för versioner utan etiketter i dialogrutan **Hantering av versionsetiketter**. 15039
- Stora filer läses in långsamt i Web Editor, med en fördröjning på några sekunder. 14958
- Om du trycker på **Retur** i en tabellcell i texten delas inte stycket som förväntat. 14251
- Experience Manager DITA Guide kan inte aktivera funktionen **Spara** efter att funktionen för automatiskt indrag har använts. 16482
- Granskningsämnen visas inte i rätt ordning. 16319
- I vyn **Författare** uppstår ett problem med att kopiera och klistra in när fasta mellanslag används, vilket leder till att texten flödar över. (15541)

- I elementet `<othermeta>` i `<topicmeta>` läggs även mappnings-ID:t till tillsammans med elementets ID när en `<conref>` läggs till i en annan DITA-karta. (15226)
- `<conref>` kan inte uppdateras från panelen **Attribut** när du gör ändringar. (15209)
- När du markerar en bild i en tabellcell markeras hela cellen. (15188)

## Publicering


- Crossmap-länkning kan inte visa alla överordnade kartor i publiceringskontextinställningarna för en länk som har `peer @scope`. (16700)
- När du lägger till nya eller tar bort befintliga attribut behålls de gamla attributen i **villkorsförinställningarna**. (15890)
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

- Felaktigt antal **Ämneslista** i Experience Manager Guides-gränssnittet på grund av ej patchade egenskaper när DITA-resurser kopieras påverkar rapporterna som genereras för en DTIA-karta. (15529)
- Ämnen som innehåller externa referenser med *%20* i URL:en visar brutna filreferenser. 15347


## Kända fel

Adobe har identifierat följande kända fel i version 2024.06.0:

- Publicering i PDF misslyckas när Vimeo-innehåll läggs till i ämnet.
- **Ämnesegenskaperna** visas inte enligt det valda formatet i metadatafälten i en sidlayout.
- `xrefs` kan inte klickas i vyn **Assets** när Dynamic Media är aktiverat.
