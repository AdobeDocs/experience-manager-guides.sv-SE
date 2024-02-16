---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides 4.4.0
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till 4.4.0-versionen av Adobe Experience Manager Guides
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 0%

---

# 4.4.0-utgåvan av Adobe Experience Manager Guides (februari 2024)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i version 4.4.0 av Adobe Experience Manager Guides (senare kallat *Stödlinjer för Experience Manager*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 4.4.0 av Adobe Experience Manager Guides](./whats-new-4-4.md).

## Uppgradera till version 4.4.0 av Experience Manager Guides


Du kan enkelt uppgradera din nuvarande version av Guides till version 4.4.0. Innan du uppgraderar till version 4.4.0 av handboken för Experience Manager måste du tänka på följande:


- Om du använder version 4.3.1, 4.3.0 eller 4.2.1 (programfix 4.2.1.3) kan du uppgradera direkt till version 4.4.0.
- Om du använder version 4.2, 4.1 eller 4.1.x måste du uppgradera till version 4.3.1, 4.3.0 eller 4.2.1 (programfix 4.2.1.3) innan du uppgraderar till version 4.4.0.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.x.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5 kan du läsa mer i avsnittet Upgrade Experience Manager Guides i den produktspecifika installationsguiden.



>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides 4.4.0.

### Adobe Experience Manager

**4.4.0 Ej UUID**
Version 6.5 Service Pack 19, 18, 17

**4.4.0 UUID**
Version 6.5 Service Pack 19, 18, 17

Mer information finns i *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.4.0 (UID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | |

*Originalplan och villkor skapade i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (ej UUID) | 2.7-regular-1 | 2.7-regular-1 | 1,6 | 1,6 |
| 4.4.0 (UID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Stavningskontrollen i Redigeraren tillåter inte val av förslag. 15045
- Den globala navigeringsknappen fungerar inte och instrumentpanelen kan inte läsas in. 14968
- I Web Editor kan funktionen för hämtning av karta inte utlösa ett popup-meddelande när den är klar att hämtas. 14626
- I Web Editor kan funktionen för hämtning av karta inte hämta en karta med baslinjen. (14622)
- Ogiltigt DTD-fel i stödlinjerna för Experience Manager. 14482
- Titeln på webbredigeringsfliken trunkeras efter en punkt (.) tecken. 14372
- Felmeddelanden för duplicerade mappningsnamn i resursgränssnittet uppdateras inte. (14320)
- Ett fel inträffar i logiken för att skapa versioner när resurser dras och släpps. 14291
- Återanvändbart innehåll hoppar över element-ID:n. 14213
- Inställningskontrollen som ska döljas **Språkvariabler** panel under **Utdata** -fliken saknas. (14194)
- Webbredigeraren genererar programfel när en ny referens eller ett nytt ämne läggs till med hjälp av ett särskilt schema i **Layout** vy. 14094
- Avståndet efter conref `<ph>` -elementet försvinner när avsnittet sparas. 13642
- Ett programfel inträffar när DITA-filer sparas innan efterbearbetningen är klar. 13571
- En ankarlänk till `<dlentry>` eller `<dt>` länktexten visas inte. 13543
- The **Favoriter** det går inte att läsa in samlingen i Web Editor. 13495
- Om titeln på ett ämne innehåller ett snedstreck `/`visas bara bokstäverna som kommer efter på fliken i Web Editor. 13455
- Förhandsvisningen av bilden försvinner inte när du har visat förhandsvisningen i webbredigeraren. 13454
- Citat visar länkar som inte går att klicka på när de skapas med ett unikt ID med blanksteg. 13447
- När du stänger ett ämne efter att du har redigerat det omdirigeras du till AEM hemsida i stället för att gå tillbaka till mappvyn. (13306)
- Popup-fönstret Infoga nyckelord visas inte när rotmappsdefinierade nycklar används i andra ämnen. (12950)
- Stängningsikonerna visas inte när mycket höga bilder förhandsvisas i **Tidigare versioner** -panelen. 12867
- Det går inte att ändra tidszonen för **Version skapad den** kolumnen för baslinjer. 12711
- Zip-filer känns inte igen i Web Editor och du kan inte dra och släppa dem. (12709)
- The **Tidigare versioner** i resursgränssnittet visas en felaktig tidsstämpel för **Aktuell** fält. 12624
- I **Layout** vy för en bokkarta, använda **Flytta åt höger** om du vill göra ett markerat kapitel till ett underelement fungerar inte. 12567
- Om du skapar en DITA-fil från en mall med ett filnamn som börjar med numeriska tecken resulterar det i ett namnutrymmesfel. (12188)
- Rotmappsinställningen finns kvar i Web Editor även om användaren inte har angett den explicit från **Användarinställningar**. (11551)
- Innehållet med vissa attribut som används markeras inte i **Upphovsman** eller **Förhandsgranska** läge. (11063)
- I webbredigeraren **Nyckelreferenser** öppnas när du infogar `varname` -tagg. (10940)
- När du drar ett ordlisteämne från databasen till en ordlista skapas `topicref`. (10767)
- XML Editors förhandsgranskningsfönster är trunkerat i Google Chrome- och Microsoft Edge-webbläsare. (10755)
- Webbredigeraren saknar möjlighet att kapsla in ett element inuti de överordnade elementen. 8791
- Web Editor avinstalleras efter ominstallation av Adobe Experience Manager Guides version 4.3.1. 14519
- Installationsprogrammet för version 4.3.1 påträffar en filterkonflikt, vilket resulterar i att `apps/cq/core/content/projects/properties`. 14517
- En självreferenslänk visas under listan med **Brutna länkar** i rapporter. 13539
- Förhandsgranskningsskärmen för fragment fryses. (14840)
- Brutna tecken visas när fragment skapas på koreanska. 13489

### Publicering

- AEM Sites publicering misslyckas och orsakar definitionsfel för filer som har `xref` till DITA-filen som börjar med HTTP. (15154)
- I Native PDF kan inte DITA-mappningens metadataegenskaper användas för att fylla i metadata för utdata från PDF. (15159)
- Vid publicering i Native PDF fungerar inte anpassade attribut i villkorsförinställningar för publicering i Native PDF. 14943
- Det går inte att lägga till en anpassad mall från **Utdata** i redigeraren. 14846
- **AEM** förinställningen fungerar inte på grund av en tom mallsökväg. 14804
- AEM Site regeneration misslyckas för DITA-kartor med ämnen som innehåller MathML-ekvationer. (14790)
- Vid publicering i PDF genererar PDF fel när det gäller att hämta beroenden för `Node.js` publicering. 14445
- **AEM** förinställningen tillåter inte val av en mall utanför `/content` hierarkin i Web Editor. (14260)
- Funktionen för att publicera som innehållsfragment fungerar inte för filer som listas i sökresultaten. (14090)
- Fmdita-komponenter har en hårdkodad sökväg med `delegator.jsp`, som förhindrar övertäckning av AEM Sites-komponenter. (13993)
- Den taggade vyn av PDF-reaktorn i Native PDF fungerar inte som förväntat. (13622)
- I Native PDF publicering finns bakgrundsfärgvalet på **Mall** layout kräver att sidan laddas om vid återgång till `None`. 13621
- Vid publicering av AEM påträffas ett problem vid implementering i datalagret för stora kartor med scope-peer-länkar. 13531
- Ett problem uppstod vid implementering av datastore för en stor DITA-karta med scope-peer-länkar AEM Site-publicering. (13530)
- Felaktiga ikoner och verktygstips visas för  **Redigera innehåll** i **Sidlayouter** verktygsfältet för mallarna som används vid publicering i Native PDF. 13492
- Det går inte att aktivera en plats med hjälp av Experience Manager-stödlinjer **Publish Dashboard**. 13439
- I Native PDF-publicering äventyras tillgängligheten eftersom bilder i sidhuvud och sidfot inte visar alternativ text. (12829)
- I AEM Sites-utdata har formatet eller radbrytningarna gått förlorade för `<lines>` -element med underelement.(12542)
- Det går inte att duplicera sidlayout i PDF utan att lägga till något tillägg automatiskt. (12534)
- Elementetiketternas lokalisering fungerar inte korrekt i AEM Sites-utdata. (12144)
- Anpassade metadata är inte tillgängliga i det slutliga resultatet. (12116)
- `fmdita rewriter` står i konflikt med användarens omskrivarkonfiguration och leder till att långa URL-adresser visas i stället för länkarna. (12076)
- Saknas **diaval** i förinställningar för utdata på mappprofilnivå som har skapats via webbredigerarens användargränssnitt. (11903)
- I **AEM**  förinställning, möjlighet att **Generera olika PDF för varje ämne** inte fungerar. (11555)
- Inbyggd PDF-publicering saknar stöd för CMYK-färgmodellskonvertering. (10754)
- Vid uppgradering till version 4.3.1 inträffar vissa undantag i noden Native PDF. 14492
- När du genererar utdata från PDF med Native PDF-publicering kommer filnamnet att trunkeras efter en viss period. (13620)


### Förvaltning

- Innehållsreferensen bryts vid kopiering och inklistring av DITA-filer med självreferenslänkar utan GUID. (13540)
- **Baslinjefilter** filer fungerar inte med Filnamn i Web Editor. 13486
- Baslinjen i Web Editor visar titeln för den föregående versionen i stället för den valda versionen av DITA-filen. 13444)
- Om du inaktiverar indexeringen av den överordnade DITA-kartan för att få bättre prestanda kan vissa funktioner påverkas.(12213)
- Villkorsförinställningar för stora DITA-kartor skapas inte. (10936)
- Det går inte att redigera förinställningarna för samlingens första kartor när en kartsamling redigeras. (10649)
- Etiketter från `labels.json` filen visas i slumpmässig ordning i Web Editor. (10508)
- Dynamiska baslinjeanrop använder namnet i stället för titeln, vilket leder till att det inte går att exportera DITA-mappnings-API. 14268

### Granska

- Snabbmenyn för högerklickning fungerar inte för **Acceptera** eller **Avvisa** spåra ändringar. 14607
- Växla till att stänga DITA-avsnitt på Granskningsskärmen fungerar inte i version 4.3.1 av Adobe Experience Manager-guider. 14537
- Symmetriproblem uppstår i den föregående och den aktuella versionen av Web Editor, sida vid sida-granskningspanelen. (14156)
- Det går inte att anpassa e-postmallar för granskningsarbetsflöden med övertäckning. 13954
- Det går inte att klicka på koreanska bilagor på Experience Manager Guides Review-skärmen. 13436
- Karttitel klipps av på skärmen för granskning och samarbete, utan möjlighet att visa hela titeln. (13012)

### Översättning

- The **Acceptera/avvisa** visas felaktigt för automatiskt godkänd mänsklig översättning. 14318
- Internationaliseringsproblem (i18n) inträffar under omvandlingen av icke-engelska DITA-filer till AEM sidor. 14286
- Godkänn automatiskt fungerar inte ibland, och undantag uppstår om ett felaktigt värde är aktiverat **Översättningsstatus**. 13607
- Baslinjen som exporteras från översättningsinstrumentpanelen misslyckas och öppnas inte på målspråket. (12993)
- Översatt innehåll kan inte synkroniseras från temporära översättningsprojekt, och översättningsguiden för DITA XML-redigeraren visar felaktigt **Pågår** status för godkända jobb. (9938)

## Känt fel

Adobe har identifierat följande kända fel i version 4.4.0:

- Version 1.0 visas inte i användargränssnittet för den duplicerade DITA-filen.