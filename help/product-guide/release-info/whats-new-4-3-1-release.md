---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 4.3.1
description: Läs om de nya och förbättrade funktionerna i 4.3.1-utgåvorna av Adobe Experience Manager Guides
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Nyheter i version 4.3.1 av Adobe Experience Manager Guides (oktober 2023)

I den här artikeln beskrivs de nya och förbättrade funktionerna i version 4.3.1 av Adobe Experience Manager Guides (kallas senare *Experience Manager Guides*).

Mer information om uppgraderingsinstruktioner, kompatibilitetsmatris och problemen som åtgärdas i den här versionen finns i [Versionsinformation](./release-notes-4-3-1.md).

## Ansluta till en datakälla och infoga ämnen

Experience Manager Guides har färdiga anslutningar som hjälper dig att ansluta till dina datakällor, vilket gör Experience Manager Guides till ett verkligt innehållsnav. Detta ger dig en fördel av att spara tid och arbete som annars skulle ha ägnats åt manuell datainmatning eller replikering.

Tillsammans med de befintliga färdiga anslutningarna som JIRA och SQL (MySQL, PostgreSQL, SQL Server, SQLite) kan administratören även konfigurera anslutningarna för databaserna MariaDB, H2DB, Adobe Commerce och Elasticsearch. De kan även lägga till andra kopplingar genom att utöka standardgränssnitten.

Du kan visa de konfigurerade anslutningarna under panelen **Datakällor** i Web Editor.

<img src="assets/data-sources.png" alt="Lista med datakällor i panelen" width="300">

*Visa anslutna datakällor.*

Nu kan du även skapa ett ämne från en ansluten datakälla. Ett ämne kan innehålla data i olika format, som tabeller, listor och stycken. Du kan också skapa en DITA-karta för alla ämnen. Du kan koppla metadata till ämnet när du drar från en datakälla.

Mer information finns i [Använd data från datakällan](../user-guide/web-editor-content-snippet.md).

## Konfigurera en datakällanslutning från användargränssnittet

Experience Manager Guides har nu också ett **datakällverktyg** som hjälper dig att konfigurera färdiga anslutningar för datakällor. Du kan enkelt skapa kopplingar för databaserna JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce och Elasticsearch.

Du kan också enkelt redigera, återansluta, duplicera eller ta bort en datakällkoppling. Läs mer om hur du [enkelt konfigurerar en datakällanslutning från användargränssnittet](../install-guide/conf-data-source-connector-tools.md).

![datakällanslutningar listade på panelen Datakällor](assets/data-sources-create-window.png){width="550" align="left"}

*Skapa och visa datakällanslutningarna från datakällpanelen.*

## Visa loggar för ämnesgeneratorn

Nu kan du även visa loggfilen för innehållsgenerering. Loggfilen hjälper dig att kontrollera varningar, fel och undantag.  Läs mer om hur [alternativen för ämnesgenerator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) hjälper dig att enkelt generera och hantera ämnesgeneratorer.

## Stöd för snabbverktyg i datakällmallarna

Nu kan du använda snabbverktygen i Experience Manager Guides-mallarna. Med de här verktygen kan du använda olika funktioner för data som du hämtar från datakällorna. Du kan använda mallarna när du skapar ett innehållsutdrag eller ett ämne. Med den här funktionen kan du spara tid och arbete med att manuellt använda samma funktion för varje datauppsättning.  Det ger också korrekta resultat.
Du kan till exempel använda $mathTool för att utföra matematiska funktioner.
Läs mer om hur du [använder snabbverktyg i datakällmallarna](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Förbättringar av inbyggda PDF

Följande förbättringar av ursprungligt PDF har gjorts i oktober 2023-versionen:

### Återställ sidnumret för den första sidan i en layout

I utdata från PDF kan du starta om sidnumren och ange från vilket nummer numreringen börjar. Nu kan du också börja numreringen endast för den första förekomsten av ett avsnitt.
Läs mer om hur du [arbetar med sidegenskaperna i en sidlayout](../native-pdf/design-page-layout.md#page-props-page-layout).


### Visa kapitel utan automatiska nummer i innehållsförteckningen

I Experience Manager Guides visas kapitelnumren tillsammans med kapitelnamnen i innehållsförteckningen. Nu kan du välja att publicera enbart kapitelnamnen utan kapitelnumren. Visa mer information om hur du konfigurerar de [avancerade PDF-inställningarna för en mall](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Hämta en karta från Web Editor

Nu kan du inte bara redigera en karta i kartvyn i Web Editor utan även hämta den. Du kan välja att hämta kartan med en viss baslinje. Du kan också förenkla hierarkin och spara alla filer och mappar i en enda mapp.

Mer information finns i funktionsbeskrivningen för **Kartvyn** i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).

![alternativmeny för en fil i databasvyn](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Välj en fil i databasvyn och välj alternativet för att utföra en åtgärd på filen.*


## Stöd för olika ämnesdefinitioner i en och samma uppräkningsdefinition

Du kan nu definiera en eller flera ämnesdefinitioner i en karta och uppräkningsdefinitionerna i en annan karta och sedan lägga till kartreferensen. Ämnesuppräkningsreferenserna löses i samma karta eller i den refererade kartan.

Du kan nu även definiera villkor och använda dem för vissa specifika element i ett ämne.  Villkoren visas bara för dessa specifika element och inte för alla andra element.

Mer information om hur du hanterar hierarkiska definitioner för ämnesdefinitioner och uppräkningar finns i objektschemats funktionsbeskrivning i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).




## Förbättrad förhandsgranskning på snabbmenyn

Använd snabbmenyn för att snabbt förhandsgranska filen (.dita, .xml, audio, video eller image) utan att öppna den. Du kan nu ändra storlek på förhandsgranskningsfönstret, och om innehållet innehåller en referenslänk kan du markera den och öppna den på en ny flik.

![Förhandsgranskningsfönster ](assets/quick-preview_cs.png){width="800" align="left"}

*Förhandsgranska filen i rutan.*

Mer information om snabbmenyn finns i beskrivningen av funktionen **Alternativ för en fil** i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Redigera en fil i syrgasanslutningens plugin

I Experience Manager Guides kan du nu välja en fil i Web Editor och sedan välja att redigera filen i plugin-programmet för syreanslutning. Det här alternativet är inte aktiverat som en del av det färdiga stödet.

Mer information finns i **Alternativ för en fil**-funktionsbeskrivning i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Använd variabler för aktuellt datum och aktuell tid i alternativen Målsökväg, Platsnamn eller Filnamn

När du genererar utdata AEM plats eller PDF kan du använda variabler för att ställa in alternativen **Målsökväg**, **Platsnamn** eller **Filnamn**. Du kan nu även använda variablerna `${system_date}` och `${system_time}`. Dessa variabler hjälper dig att lägga till aktuellt datum och aktuell tid till dessa alternativ.

Lär dig hur du [använder variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](../user-guide/generate-output-use-variables.md).


## Kortkommandon för att flytta markören i Web Editor

I Experience Manager Guides kan du nu även använda kortkommandon för att flytta markören i Web Editor. Du kan använda kortkommandona för att snabbt flytta ett ord åt vänster eller höger. Du kan också gå till början eller slutet av raden med hjälp av kortkommandona.

Läs mer om [kortkommandona i Web Editor](../user-guide/web-editor-keyboard-shortcuts.md).
