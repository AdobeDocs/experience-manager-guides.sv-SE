---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 5.0.0
description: Läs om de nya och förbättrade funktionerna i 5.0.0-utgåvan av Adobe Experience Manager Guides
role: Leader
source-git-commit: a5c18c228f68db9a3282a004dc56c8a0735e4926
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 0%

---

# Nyheter i version 5.0.0 (mars 2025)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 5.0.0 av Adobe Experience Manager Guides.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 5.0.0](../release-info/fixed-issues-5-0-0.md).

Läs mer om [uppgraderingsinstruktioner för version 5.0.0](../release-info/upgrade-instructions-5-0-0.md).

## Förbättrat användargränssnitt i Experience Manager Guides för ökad produktivitet och upplevelse

Adobe Experience Manager Guides har nu en förbättrad design och förbättrade funktioner som hjälper dig att arbeta snabbare och effektivare än någonsin. Det nya gränssnittet ger en intuitiv och förbättrad användarupplevelse med en helt ny hemsida, ett renare och mer organiserat redigeringsverktygsfält, dedikerad kartkonsol och förbättrade funktioner.

De viktigaste högdagrarna är följande:

- **Introduktion till startsidan**: Experience Manager Guides har nu en hemsida som ger en intuitiv välkomstskärm, inklusive en snabb översikt över de filer du nyligen har öppnat, samlingar med mera.

  Mer information finns i [Adobe Experience Manager Guides hemsida](../user-guide/intro-home-page.md).

  ![](assets/aem-home-page-new.png){width="800" align="left"}


- **Ny redigeringsupplevelse**: Upplev nu redigeraren med ett nytt utseende och en ny känsla. Det omgjorda redigeringsgränssnittet har ett renare och mer organiserat verktygsfält, smidig navigering och en övergripande intuitiv upplevelse som hjälper dig att skapa dokument snabbare och effektivare.

  Gå till [om du vill veta mer om redigeringsfunktionerna](../user-guide/web-editor-features.md).

  ![](assets/editor-new-ui-whats-new.png){width="800" align="left"}

- **Dedikerad kartkonsol**: Vi presenterar kartkonsolen, en dedikerad konsol där alla karthanterings- och publiceringsfunktioner klumpar. Nu får du alternativ för att generera utdata, översätta innehåll, skapa rapporter och mycket mer - allt i ett och samma gränssnitt.

  Läs mer om [karthantering och publicering](../user-guide/map-console-overview.md).

  ![](assets/map-console-new-ui-whats-new.png){width="800" align="left"}



## Integrering med Adobe Workfront för robusta arbetshanteringsfunktioner

Experience Manager Guides kan nu integreras smidigt med Adobe Workfront och ger dig tillgång till robusta projekthanteringsfunktioner utöver Experience Manager Guides centrala CCMS-funktioner.

Med den här integreringen kan du skapa och hantera Adobe Workfront-uppgifter direkt från Experience Manager Guides. Som författare kan du till exempel skapa en granskningsuppgift (med ett eller flera DITA-avsnitt eller -kartor tillagda) direkt i Experience Manager Guides-gränssnittet och tilldela den till en granskare. Som granskare kan du arbeta med tilldelade uppgifter i användargränssnittet för Experience Manager Guides Review och returnera dem till författaren med kommentarer. På samma sätt kan du skapa en publicerings- och översättningsåtgärd och sedan tilldela den till de användare som ska arbeta med den.

Integreringen ger dig även möjlighet att övervaka arbetsköerna så att du är organiserad och överordnad alla dina uppgifter (tilldelade uppgifter). Man kan också utnyttja Adobe Workfront för projektledning i Experience Manager Guides.

Mer information finns i [Integrering med Workfront](../user-guide/workfront-integration.md).

![](assets/workfront-new-ui-whats-new.png){width="800" align="left"}


## Snabbare och skalbar Ny publiceringsmotor från AEM Sites

Få snabbare och skalbar publicering till AEM Sites med den helt nya publiceringsmotorn som är optimerad med sammansatt komponentmappning för snabbare framtagning och rendering av sidor. Det finns med nya färdiga redigerbara mallar som kan anpassas efter dina behov med hjälp av AEM mallredigerare. Mallarna använder en blandning av WCM-komponenter och specialiserade Guides-komponenter för att säkerställa att slutanvändarna får den bästa upplevelsen på era AEM Sites-sidor. Du kan också anpassa dina befintliga mallar för att utnyttja den nya publiceringsmotorn.

Läs mer om [AEM Sites-publicering](../user-guide/generate-output-aem-site-web-editor.md).

![](assets/new-aem-sites-preset.png){width="500" align="left"}


## Publicera smidigt fristående material till AEM Sites med Single topic publishing

Vi presenterar ämnespublicering på AEM Sites-sidor där du kan publicera enskilda ämnen direkt på AEM Sites-sidor utan att behöva publicera en hel karta.  Detta effektiviserar publiceringsprocessen och gör den mer effektiv när du arbetar med fristående innehåll som marknadsföringsmaterial, tekniska bulletiner eller annat fristående innehåll. Det förenklar också innehållsunderhåll genom att eliminera behovet av att skapa kartor för publicering av enstaka ämnen.

Mer information finns i [Publicera AEM Sites-sidor](../user-guide/publish-aem-sites.md).

![](assets/aem-sites-page-generate.png){width="500" align="left"}



## Den helt nya Markdown-redigeraren för avancerad redigering

Upplev nu ett renare, effektivare och kraftfullare sätt att skapa markeringsämnen. Experience Manager Guides introducerar ett nytt gränssnitt för markeringsredigering med ett välorganiserat verktygsfält och avancerade funktioner, inklusive en **sida vid sida** -vy där du kan skapa och förhandsgranska innehåll samtidigt. Det möjliggör också smidig publicering av Markdown-ämnen som är en del av en karta till flera kanaler.

Mer information finns i [Markeringsredigering](../user-guide/web-editor-markdown-topic.md).

![](assets/markdown-editor.png){width="800" align="left"}

## Förbättringar i redigeraren

Följande redigeringsförbättringar har gjorts som en del av den nya versionen:

**Förbättringar av tabellinfogning**

- Möjlighet att konfigurera standardvärden för rubrikrader, innehållsrader och kolumner i tabellen eller förenklad infogningsdialogruta.
- Möjlighet att konfigurera tabellinställningarna så att tabeller som kopierats från externa källor klistras in som enkla eller som en tabell.

  Mer information finns i avsnittet Tabeller i [Lär dig mer om redigeringsfunktionerna](../user-guide/web-editor-features.md#content-insertion-options).

**Förbättrad egen namnfunktion för DITA-element**

Funktionen för egna namn för DITA-element har förbättrats. Nu behålls uppräknade standardvärden när ett eget namn tilldelas till ett element och det uppdaterade namnet återspeglas i vägbeskrivningar, innehållsegenskaper, panelen Återanvändbart innehåll, ordlistepanelen och andra relevanta platser.

**Förbättrad upplevelse för filtrerade sökningar**

Resursvisningsgränsen för filtrerade sökresultat i Adobe Experience Manager Guides-databasen har ökats. Sökresultaten returnerar nu alla relevanta resurser eller filer som matchar sökvillkoren. Du kan bläddra igenom listan för att läsa in fler resultat, vilket eliminerar behovet av att utföra upprepade sökningar för att hitta de nödvändiga resurserna.

**Alternativ text för bilder som nu lagts till som element**

I bilder används nu elementet `<alt>` för alternativ text enligt de senaste DITA-standarderna. Användningen av attributet `@alt` för alternativ text har tagits bort men stöds fortfarande i tidigare DITA-versioner.

**Anpassa korsreferens i redigeringsverktygsfältet**

Skapa nu en anpassad verktygsfältsknapp för **korsreferens** för att få direkt åtkomst till ett av menyalternativen. Du kan till exempel konfigurera det här alternativet så att du direkt kan gå till en webblänk, e-postlänk, filreferens eller andra tillgängliga alternativ beroende på vad som krävs.

Mer information finns i [anpassa överkanten och verktygsfältet](../guides-ui-extensions/customisations/toolbar-topbar.md).

## Förbättrade granskningar

Följande granskningsförbättringar har gjorts som en del av den nya versionen:

- När du skapar en granskningsåtgärd kan du nu skriva in ett projektnamn för att snabbt hitta och markera den i listrutan Projekt. Den här förbättringen eliminerar behovet av att bläddra igenom långa projektlistor, vilket gör det snabbare och effektivare att tilldela granskningsuppgifter, särskilt när du hanterar flera projekt.

- I redigerings- och granskningsgränssnittet har rutan **Svar** nu stöd för flerradiga poster. Du kan använda **Skift**+**Retur** för att gå till nästa rad. Du kan också expandera kommentarsrutan när du skriver kommentaren.

  Mer information finns i [Granska ämnen](../user-guide/review-topics.md).

- Nu kan författare komma åt granskningskommentarerna i Redigeraren även när granskningsåtgärden är markerad som stängd. Med de senaste förbättringarna har granskningspanelen både aktiva och slutna granskningsuppgifter för varje projekt i redigeraren. När du väljer en sluten granskningsåtgärd visas motsvarande kommentarer i panelen Kommentarer till höger, vilket ger kontinuerlig åtkomst till viktiga granskningskommentarer även när en åtgärd har stängts.

  Mer information finns i avsnittet Granska i [Känn till redigeringsfunktionerna](../user-guide/web-editor-features.md).

## Förbättrad publicering

Följande publiceringsförbättringar har gjorts i den nya versionen:

**Förbättringar av den inbyggda PDF**

- Möjlighet att inkludera metadata från ett ämnes `prolog`-element, t.ex. copyright, författare och annan information, i sidlayouterna när du genererar PDF-utdata. Detta gör att de genererade PDF-filerna är mer detaljerade och ger ett viktigt sammanhang, vilket gör dem mer informativa för läsaren.

  Mer information finns i [Lägg till fält och metadata i sidlayouten](../native-pdf/design-page-layout.md#add-fields-and-metadata-add-fields-metadata).

  ![](assets/metadata-topic-content.png){width="300" align="left"}


- Introducerade ett alternativ för att aktivera eller inaktivera DITA-OT-förbearbetning för PDF-utdata. Aktivera det här alternativet om ditt innehåll kräver DITA-OT-baserad normalisering eller anpassade DITA-OT-plugin-program under bearbetningen. Detta ger dig större kontroll över hur innehåll bearbetas för PDF. Som standard är inställningen **Aktiverad**.

  Mer information finns i [Arbeta med PDF-förinställning](../user-guide/generate-output-pdf.md)

  ![](assets/ditaot-setting-enabled.png){width="500" align="left"}

- Utskriftsinställningarna för generering av inbyggda PDF-utdata har flyttats från inställningen **Mallar** till förinställningen **Inbyggda PDF-utdata** för bättre användbarhet. Nu kan du använda samma mall för online- och utskrifts-PDF:er med olika utskriftsinställningar, till exempel färgprofiler.

  Mer information finns i [Inbyggd förinställning för PDF](../web-editor/native-pdf-web-editor.md)

- Möjlighet att lägga till ett bokmärke för innehållsförteckningssidan i PDF-utdata för smidig sidnavigering, särskilt i långa PDF-filer.

  Mer information finns i [Lägg till ett anpassat bokmärke i PDF-utdata](../native-pdf/add-custom-bookmark.md).

## Förbättrad innehållshantering

Följande förbättringar av innehållshanteringen har gjorts som en del av den nya versionen:

**Anpassade metadatafält i rapporter**

Med den här funktionen kan du konfigurera anpassade metadatafält för rapporter via **Inställningar**. När du har konfigurerat dem kan du visa de här fälten under **Kolumner** på rapportpanelen, där du kan markera eller avmarkera dem för att kontrollera deras synlighet.

Mer information finns i [DITA-kartrapporten från kartkonsolen](../user-guide/reports-web-editor.md).

**Knappen Uppdatera i översättningsgränssnittet**

En uppdateringsknapp visas i översättningsgränssnittet där du kan uppdatera översättningsinstrumentpanelen med uppdaterade filer och status.

**Förbättring av arbetsflödet för efterbearbetning av resurser**

Stödet för efterbearbetning av resurser har tillhandahållits via REST API och API SDK. Nu utlöses resurshanteringshändelsen och den kan avlyssnas för att definiera ytterligare arbetsflöde.

Mer information finns i [Efterbearbetningshändelsehanteraren](../api-reference/post-process-event.md).


## Föråldrade funktioner

**Snabbgenerering**

Experience Manager Guides stöder inte längre funktionen **Snabbgenerering** för att generera utdata direkt från databasvyn eller kartvyn.

Den här funktionen har tagits bort från panelerna Databas och Kartvy. Vi rekommenderar att du använder **kartkonsolen** för alla mapphanterings- och publiceringsrelaterade åtgärder.

Mer information finns i [Karthantering och publicering](../user-guide/map-console-overview.md).

**Skicka metadataargument för rotmappning till DITA-OT-kommandoraden**

Möjligheten att skicka metadataargument för rotmappning via DITA-OT-kommandoraden har tagits bort som en del av releasen. Nu bör du använda fältet **File property** eller **Metadata** i förinställningen för att skicka de DITA-OT-metadata som krävs.

Om du vill fortsätta skicka metadata i DITA-OT-kommandoraden måste du uppdatera `pass.metadata.args.cmd.line` i `Config.Manager`.

Mer information finns i [Konfigurera inställningar för utdatagenerering](../cs-install-guide/conf-output-generation.md#configure-the-dita-ot-command-line-argument-field-to-accept-root-map-metadata).
