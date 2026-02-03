---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2026.01.0
description: Läs om de nya och förbättrade funktionerna i version 2026.01.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 0%

---

# Nyheter i version 2026.01.0 (februari 2026)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2026.01.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2026.01.0](fixed-issues-2026-01-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2026.01.0](../release-info/upgrade-instructions-2026-01-0.md).


## Nu kommer sökning i Source-läge i Sök och ersätt

Experience Manager Guides har introducerat flera förbättringar av funktionen Sök och ersätt som finns i den vänstra panelen i redigeringsgränssnittet. I den här versionen, tillsammans med ett förbättrat användargränssnitt, introduceras en ny växlingsknapp för **Använd källäge** i panelen **Sök och ersätt**.

Om du aktiverar det här läget kan du utföra global sökning inte bara på det synliga innehållet utan även på det underliggande källinnehållet (XML-struktur, inklusive element, taggar och attributvärden) för den sökda strängen. Detta läge garanterar en omfattande sökning i hela innehållet.

![](assets/map-find-replace-with-source-mode.png){width="650" align="left"}

I det här läget kan du använda filter för att begränsa sökningen efter filtyp, dokumentläge, datum för senaste ändring med mera. Du kan också hämta en detaljerad CSV-rapport när du har utfört åtgärden Ersätt alla, som innehåller en ögonblicksbild av alla ersättningsåtgärder som har utförts tillsammans med deras status för slutförande och fel.

Mer information finns i avsnittet [Sök och ersätt](../user-guide/web-editor-left-panel.md#find-and-replace) i _vänsterpanelen i redigeraren_.

>[!NOTE]
>
> För funktionen **Använd källäge** på panelen Sök och ersätt måste en anpassad indexdistribution först slutföras. När indexeringen är klar kontaktar du ditt Customer Success-team för att aktivera den här funktionen.

## Förbättrad bläddring i filer och mappar

Den här versionen har ett renare och mer intuitivt gränssnitt för att bläddra bland filer och mappsökvägar i Experience Manager Guides.

När du bläddrar bland filer innehåller den omgjorda dialogrutan **Välj fil** nu en fliklayout med två vyer - **Databas** för navigering i hela innehållsdatabasen i tabellformat och **Samlingar** för snabb åtkomst till ofta använda ämnen, kartor och bilder.

![](assets/select-file.png){width="650" align="left"}

Några viktiga förbättringar:

- Tabellvy över filer och mappar för strukturerad navigering.
- Bläddra bland mapparna och navigeringspanelen för att enkelt flytta mellan mapparna.
- Stöd för markering av flera filer för återanvändbart innehåll, ämnesreferenser, schematron, utdatainställningar (med DITAVAL) och Workfront.
- Förhandsgranska markerade filer för enkel granskning; för flera markeringar kan du förhandsgranska alla filer och ta bort alla filer från förhandsgranskningspanelen efter behov.
- Sök- och filtreringsalternativ för att begränsa resultaten efter namn, titel, filtyp, dokumenttillstånd och taggar.

Dialogrutan **Välj sökväg** innehåller också en förbättrad trädstrukturerad vy för mappnavigering, vilket ger ett mer organiserat och effektivt sätt att välja sökvägar i innehållsdatabasen.

![](assets/select-path-dialog-new.png){width="350" align="left"}

Mer information finns i avsnittet [Bläddra bland filer och mappar i Experience Manager Guides](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides) i _Andra funktioner i Redigeraren_.

## Förbättringar av arkivsökning och filtrering

### Stöd för dokumenttillståndsfilter

Filtrera sökresultaten för databasen baserat på filernas aktuella dokumenttillstånd. Med det nya filtret **Dokumenttillstånd** kan du begränsa sökningen med hjälp av de tillgängliga filtervärdena som definieras i filen `ui_config.json` i mappprofilen.

![](assets/document-state-filter-repository.png){align="left"}

Standardfiltervärdena som är tillgängliga för dokumentläget är: Utkast, Redigera, Granskning, Godkänd, Granskad och Klar. Mer information om hur du anpassar standardvärden för dokumenttillståndsfilter finns i [Konfigurera dokumenttillståndsfilter](../cs-install-guide/config-doc-state-filters.md).

>[!NOTE]
>
> Om du använder anpassade inställningar för `ui_config.json` måste du säkerhetskopiera dessa innan du uppgraderar. Efter uppdateringen granskar och justerar du inställningarna så att de överensstämmer med ändringarna i den senaste versionen.

### Miniatyrbildikon för multimedia

Alla multimediafiler visas nu med miniatyrbildikoner, vilket gör det enklare att visuellt identifiera och hitta bilder i **databasen**. Den här förbättringen gäller även när du söker efter filer på **sökpanelen**, vilket gör att du snabbt kan skilja multimedieresurser från andra filtyper.

![](assets/thumbnail-repository.png){align="left"}

## Förbättringar i redigeraren

Följande redigeringsförbättringar har gjorts i den här versionen:

### Uppdatera ämnen eller karta i förhandsgranskningsläget

Den nya funktionen **Uppdatera** introduceras för kartor som redan har öppnats i förhandsgranskningsläget. Med den här nya funktionen kan du enkelt uppdatera innehållet i hela kartan eller enskilda ämnen som finns i den.

- Om du vill uppdatera hela kartan (inklusive alla ämnen) visas en ny **Uppdatera**-knapp i det övre vänstra hörnet av redigeraren.

  ![](assets/refresh-map.png){width="600" align="left"}

- Om du vill uppdatera innehållet i enskilda ämnen har ett nytt **Uppdatera ämne** lagts till på snabbmenyn.

  ![](assets/refresh-topic.png){width="600" align="left"}

Mer information finns i [Karteditorfunktioner](../user-guide/map-editor-advanced-map-editor.md).

### Indikator för arbetskopia för metadataändringar

Alla ändringar i metadatafälten som är tillgängliga under **Filegenskaper** utlöser nu indikatorn för arbetskopia. En dokumentversion markeras som _smutsig (*)_ när du lägger till, tar bort eller ändrar standardfält eller anpassade metadatafält. Den här förbättringen säkerställer att alla metadataändringar spåras korrekt, vilket ger bättre synlighet och kontroll över dokumentversioner.

### Räkna ord för ämnen och kartor

Nu kan du spåra antalet ord som finns i en karta eller ämnesfil. Det nya fältet **Antal ord** i den högra panelen visar det totala antalet ord i ett ämne (eller en karta), där ord avgränsade med blanksteg räknas som enskilda ord. Den uppdateras automatiskt varje gång du sparar ändringar. För korsreferenser inkluderas bara visningstexten, medan tangenter exkluderas.

![](assets/file-properties-new.png){width="350" align="left"}

Mer information finns i [Högerpanelen i redigeraren](../user-guide/web-editor-right-panel.md#file-properties).

### Förbättrad hantering av skrivskyddade filer

Redigering av filegenskaper är nu begränsad för filer i läget **Skrivskyddad**. Om en fil är låst av en annan användare (tillgänglig i skrivskyddat läge) kan du inte ändra någon metadataegenskap, vare sig det är från [högerpanelen](../user-guide/web-editor-right-panel.md#file-properties), alternativet **Egenskaper** på snabbmenyn [för en fil](../user-guide/web-editor-other-features.md#context-menu-functions-on-a-files-tab) eller [metadatarapport](../user-guide/reports-web-editor.md#metadata-report) . Detta förhindrar oavsiktliga ändringar i skrivskyddade filer.

## Förbättrade granskningar

### Lägga till eller ta bort ämnen från en pågående granskningsåtgärd

Nu kan du lägga till nya ämnen i en pågående granskningsåtgärd (om de inte har skickats för granskning tidigare) eller ta bort ämnen från en pågående granskningsåtgärd utan att det påverkar granskningsflödet.

På sidan **Uppgiftsinformation** kan du välja eller avmarkera ämnen som du vill ändra ämneslistan. Granskarna meddelas (via AEM och e-post) om eventuella ändringar av deras tilldelade ämnen via AEM och e-postmeddelanden. Mer information finns i [Skicka ämnen för granskning](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Översättningsförbättringar

### Indikator för resurser utan versionshantering som skickats för översättning

När du hanterar översättningar är det viktigt att se till att allt innehåll versionshanteras innan det skickas för behandling. För att underlätta med detta har Experience Manager Guides nu en tydlig indikator för ämnen som har sparat ändringar men som ännu inte är versionshanterade.

Om en fil innehåller ändringar utan versionsnummer (som inte har sparats som en ny version på kartan) visas en _info_ -ikon bredvid filen som anger att det finns uppdateringar. Om du snabbt vill fokusera på de här filerna aktiverar du alternativet **Visa resurser med endast ändringar utan versionsnummer** på panelen Filter.

Mer information finns i [Översätt dokument från kartkonsolen](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Förbättrad publicering

### Anpassade bildåtergivningar för särskilda förinställningar

Du kan nu konfigurera olika bildåtergivningar för enskilda förinställningar under samma utdatatyp genom att använda attributet `outputName` i `renditionmapping.xml`. Den här förbättringen ger större flexibilitet vid publicering av innehåll som kräver olika bildupplösningar för olika scenarier. Du kanske vill ha en högupplöst bild för HTML5-utdata samtidigt som du använder en mindre miniatyrbild för en förinställning med låg upplösning.

Mer information finns i [Hantera bildåtergivning i utdatagenerering](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Hämta loggar för genererade utdata

När du genererar utdata via Assets-gränssnittet finns nu en ny **hämtningsloggar**-knapp som gör att du kan hämta logg till den lokala enheten för enklare åtkomst och granskning.


### Språkvariabler för korsreferenser i ursprungliga PDF Output

När du publicerar inbyggda PDF-utdata kan du använda [språkvariabler](../native-pdf/native-pdf-language-variables.md) för att översätta statisk korsreferenstext som _Se i kapitel_ eller _Se på sida_. Variabeln använder det språk som definierats i ämnet via attributet `xml:lang`.

Mer information om hur du konfigurerar inbyggda PDF-utdatainställningar och korsreferensinställningar finns i [Inbyggd PDF-utdatainställning](../web-editor/native-pdf-web-editor.md).


### Stöd för komponentmappning på elementnivå i publicering i nya AEM Sites (med hjälp av komponentmappning på sammansatt nivå)

Experience Manager Guides har nu stöd för komponentmappning på elementnivå i AEM Sites-utdata (med hjälp av sammansatt komponentmappning), vilket ger team exakt kontroll över hur DITA-element återges med `componentmapping.json`. Genom att mappa `topicref`, titlar, bilder, tabeller med mera till rätt AEM Core-komponenter får du en renare struktur i stället för allt som är standard till Text-komponenten. Detta resulterar i bättre prestanda och ger en rikare och modernare webbplatsupplevelse.

## Förbättrad tillgångsbearbetning

I den här versionen presenteras följande förbättringar av bearbetningen av resurser:

- Kör resursbearbetning på både mapp- och filnivå
- Filtrera resurser genom att välja specifika resurstyper som ämnen, kartor, markeringar, HTML/CSS, DITAVAL eller andra filer som stöds, för att bearbeta endast de filer du behöver.
- Använd datumbaserade filter för att begränsa bearbetningsomfånget för en angiven tidsram.
- Bearbeta resurser direkt med det nya alternativet (**Bearbeta resurser igen**) som finns på snabbmenyn för filer och mappar i databasvyn och Utforskaren.

Mer information om hur du bearbetar resurser finns i [Bearbeta resurser](../user-guide/asset-processor.md).

## API-förbättringar

Följande API-förbättringar har gjorts i den här versionen:

- Nya API:er introduceras för att skapa nya översättningsprojekt och spåra deras status. Dessa API:er hjälper till att automatisera översättningsprocessen, minska den manuella ansträngningen och förbättra effektiviteten. Mer information finns i [Skapa översättningsprojekt](../api-reference/translation-project.md)
- Förbättrade API:er för materialbearbetning med förbättrad filtreringsmöjlighet för filer och mappar. Mer information finns i [Bearbeta resurser](../api-reference/bulk-assets-processing.md).
















