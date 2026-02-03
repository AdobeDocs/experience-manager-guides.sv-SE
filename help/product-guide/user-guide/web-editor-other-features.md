---
title: Ytterligare funktioner i Editor
description: Utforska andra funktioner i redigeraren i Adobe Experience Manager Guides. Lär dig hur du använder dessa funktioner för förbättrad redigering i Experience Manager Guides.
exl-id: 1833b1e3-c7f1-4f2c-be35-235b65ba2f36
feature: Authoring, Web Editor
role: User
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '3653'
ht-degree: 0%

---

# Ytterligare funktioner i Editor {#id2056B0B0YPF}

Det finns några andra användbara funktioner i Editor som du kan använda för att:

## Snabbmenyfunktioner på en fils flik

När du öppnar en fil i Redigeraren kan du utföra olika åtgärder på snabbmenyn. Du kan visa olika alternativ beroende på om du öppnar en mediefil, en DITA-fil eller flera filer.

**Mediefil**

Du får följande funktioner på snabbmenyn för en öppnad mediefils flik:

![](images/media-file-context-menu.png){width="300" align="left"}


**En DITA-fil**

Du får följande funktioner på snabbmenyn för en öppen fils flik:

![](images/single-file-context-menu.png){width="400" align="left"}

**Flera filer**

När du har flera filer öppna får du fler alternativ på snabbmenyn:

![](images/multiple-files-context-menu.png){width="550" align="left"}

De olika alternativen på snabbmenyn förklaras nedan:

***Spara***: Du kan välja bland följande alternativ:

- **Spara**: Om du vill spara en fil utan att skapa en ny version väljer du **Spara**. När du skapar ett nytt ämne skapas en versionslös arbetskopia av ämnet i DAM. När du sparar dokumentet uppdateras arbetskopian av dokumentet i DAM. När du sparar en version på ett enkelt sätt skapas ingen ny version av ett ämne. Om ditt ämne är under granskning kan inte dina granskare få åtkomst till det ändrade ämnesinnehållet om du sparar ett ämne.

- **Spara alla**: Om det finns flera dokument öppna i redigeraren får du även ett alternativ för att **Spara alla** öppnade dokument.


***Spara som ny version***

Om du vill skapa en ny version av filen väljer du **Spara som ny version**. Mer information om **Spara** och **Spara som ny version** finns i [Verktygsfältet i redigeraren](web-editor-toolbar.md).

***Kopiera***: Du kan välja bland följande alternativ:

- **Kopiera UUID**: Om du vill kopiera UUID för den aktiva filen till Urklipp väljer du **Kopiera \> Kopiera UUID**.
- **Kopiera sökväg**: Om du vill kopiera den fullständiga sökvägen för den aktiva filen till Urklipp väljer du **Kopiera \> Kopiera sökväg**.


***Hitta i***: Du kan välja bland följande alternativ:

- **Karta**: Om du har öppnat en stor DITA-karta och vill hitta den exakta platsen för en fil på kartan väljer du **Hitta i \> Karta**. När du väljer alternativet Hitta i karta, placeras filen \(från vilken alternativet anropas\) och markeras i karthierarkin. Om du vill kunna använda den här funktionen måste du öppna kartfilen i Redigeraren. Om Kartvyn är dold visas kartvyn när funktionen anropas och filen markeras i karthierarkin.

- **Utforskaren**: På samma sätt som när du söker efter på kartan visar **Hitta i \> Utforskaren** platsen för filen i Utforskaren \(eller DAM\). Utforskaren-vyn öppnas och den markerade filen markeras i Utforskaren. Om filen finns i en mapp expanderas den mappen så att den visar den valda filens plats i Utforskaren.

  >[!NOTE]
  >
  >Från version 2025.11.0 har **databasnamnet** ändrats till **Utforskaren**. För lokal installation är den fortfarande tillgänglig som databas till version 5.1 av Experience Manager Guides.

***Lägg till i***: Du kan välja bland följande alternativ:

- **Samlingar**: Om du vill lägga till den markerade filen i samlingar väljer du **Lägg till i \> Samlingar**. Mer information finns i funktionsbeskrivningen för **samlingar** i avsnittet [Vänster panel](web-editor-left-panel.md).

- **Återanvändbart innehåll**: Om du vill kopiera den markerade filen till listan över återanvändbart innehåll väljer du **Lägg till i \> Återanvändbart innehåll**. Mer information finns i funktionsbeskrivningen för **Återanvändbart innehåll** i avsnittet [Vänster panel](web-editor-left-panel.md).

***Egenskaper***

Om du vill visa AEM-egenskapssidan för den markerade filen väljer du **Egenskaper**.

***Dela***: Du kan välja mellan följande alternativ:

**Upp, Ned, Vänster eller Höger**

Som standard kan du visa ett avsnitt i taget i Redigeraren. Det kan finnas tillfällen då du vill visa två eller flera ämnen samtidigt. Genom att dela redigerarens skärm kan du visa flera ämnen samtidigt. Om du till exempel har två ämnen - A och B öppnade i redigeraren. Om du högerklickar på ämnet B och väljer **Dela \> Uppåt** delas redigeringsfönstret upp i två delar. Ämne B visas i den övre halvan och ämne A visas i den nedre halvan. Du kan också dela skärmen vågrätt genom att välja **Dela \> Vänster** eller **Dela \> Höger**. Du kan flytta dokument från en skärm till en annan genom att dra filfliken och släppa den på skärmen där du vill placera den. På samma sätt kan du ändra ordning på filflikarna genom att dra och flytta dem som du vill.



<!--------------------------------------------

***Quick Generate***

Generate the output for the selected file. Output can be generated only for files that are a part of an output preset. For more details, view [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).

--->

***Stäng***: Du kan välja bland följande alternativ:

**Stäng**, **Stäng andra** eller **Stäng alla**

Om du vill stänga filen som du anropade snabbmenyn från väljer du **Stäng \> Stäng**. Använd **Stäng \> Stäng andra** om du vill stänga alla andra öppna filer förutom den aktiva filen. Om du vill stänga alla öppna filer väljer du alternativet **Stäng \> Stäng alla** på snabbmenyn eller också kan du välja att stänga redigeraren. Om det finns filer som inte har sparats i sessionen uppmanas du att spara dessa filer.

**Stäng och spara scenarier**

När du försöker stänga en fil som har öppnats i Redigeraren med knappen **Stäng** på filens flik eller med alternativet **Stäng** på Alternativ-menyn ber Experience Manager Guides dig att spara ändringarna och låsa upp en låst fil.

Frågorna baseras på följande konfigurationer som valts av administratören:

- **Be om upplåsning vid stängning:** Du kan låsa upp filen \(som du har låst\) när du stänger redigeraren.
- **Be om en ny version när du stänger**: Du kan välja att spara filen \(som du har redigerat\) som en ny version när du stänger redigeraren.

Hur du sparar filer beror på följande tre scenarier:

- Har inte gjort några ändringar i innehållet.
- Redigerade innehållet och sparade ändringarna.
- Innehållet har redigerats men ändringarna har inte sparats.

Du kan visa följande alternativ beroende på om filen är låst/olåst och har sparade eller osparade ändringar:

- **Lås upp och stäng**: Lås upp filen och filen stängs.
- **Spara som ny version**: Detta sparar ändringarna som du har gjort i innehållet och skapar en ny version av filen. Du kan också lägga till etiketter och kommentarer för den nyligen sparade versionen. Mer information om hur du sparar en ny version finns i [Spara som ny version](web-editor-toolbar.md#version-information-and-save-as-new-version).

- **Lås upp filen**: Om du väljer att låsa upp en fil kommer den att låsa upp filen och ändringarna sparas i den aktuella versionen av filen.

  >[!NOTE]
  >
  > Om du avmarkerar alternativet att låsa upp filen får du också ett alternativ för att stänga filen utan att spara ändringarna.

  Till exempel visas en av uppmaningarna på följande skärmbild:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Visuella Cues för brutna referenser**

Om ditt ämne innehåller brutna korsreferenser eller innehållsreferenser visas de i röd text.

**Smart copy-paste**

Du kan enkelt kopiera och klistra in innehåll inom och mellan ämnen. Källelementets struktur bevaras på målet. Om det kopierade innehållet innehåller innehållsreferenser kopieras även dessa.

**Kom ihåg den senast bläddrade platsen**

Redigeraren innehåller en smart dialogruta för filbläddring. Redigeraren kommer ihåg den senast använda platsen när en referens eller ett innehåll infogas. Första gången du öppnar dialogrutan för filbläddring, \(via Infoga referens eller Infoga återanvänd innehåll\), flyttas du till den plats där det aktuella dokumentet sparas. Om du under samma session försöker infoga en annan referens navigerar dialogrutan för filbläddring automatiskt till den plats där du infogade den senaste referensen.

>[!NOTE]
>
> Om det gäller en bild-, ljud- eller videofil används filens plats som standard i dialogrutan för filbläddring, inte den plats som användes senast.

## Bläddra bland filer och mappar i Experience Manager Guides

Experience Manager Guides innehåller intuitiva dialogrutor - **Välj fil** och **Välj sökväg** - som hjälper dig att effektivt bläddra bland och välja filer eller mappar i innehållsdatabasen.

>[!NOTE]
>
> Webbläsaren för fil- och mappsökväg introduceras med ett omgjort användargränssnitt i version 2601 av Experience Manager Guides as a Cloud Service. Det nya gränssnittet är aktiverat som standard. Om du föredrar att fortsätta använda det befintliga användargränssnittet utan dessa uppdateringar kontaktar du ditt Customer Success-team för att inaktivera den nya förbättringen.

### Bläddra bland filer i Experience Manager Guides

Med filläsaren kan du snabbt hitta och välja specifika filer i innehållsdatabasen. Den här funktionen är tillgänglig för uppgifter som att lägga till ett ämne på en karta, länka en bild eller korsreferens, skapa återanvändbart innehåll med mera.

![](images/select-file-dialog-new.png){width="350" align="left"}

När du startar filläsaren öppnas dialogrutan **Välj fil**. Den här dialogrutan innehåller två flikar: **Databas** och **Samlingar**. Fliken Databas är som standard markerad.

![](images/select-file.png){width="650" align="left"}

**Tillgängliga funktioner på fliken Databas för filbläddring**

**Tabellvy över filer och mappar**

På fliken Databas finns en tabellvy över filer och mappar från innehållsdatabasen, vilket gör det enklare att hitta rätt filsökväg. Du kan också använda de synliga kolumnerna högst upp och mappnavigeringspanelen till vänster för att flytta mellan mapparna.

![](images/select-file-dialog-navigate-files.png){width="650" align="left"}

**Markera en och flera filer**

Om du vill använda en fil markerar du filen och väljer **Markera**.

![](images/select-file-single-file-selection.png){width="650" align="left"}

I vissa fall kan du även välja flera filer från den här sökvägsläsardialogrutan. Om du till exempel bläddrar bland filer för återanvändbart innehåll kan du markera flera filer och göra dem till en del av det återanvändbara innehållet.

![](images/select-file-multiple-file-selection.png){width="650" align="left"}

Det finns för närvarande flera filval för återanvändbart innehåll, ämnesreferenser, Schematron, Utdatainställningar (med DITAVAL) och Workfront.

>[!NOTE]
>
> När du väljer filer från sökvägsläsarens dialogruta kan det finnas vissa mappar som är inaktiverade. Detta beteende begränsar åtkomsten till specifika filtyper för att säkerställa giltiga val. När du till exempel skapar återanvändbart innehåll får endast avsnitt- och mappfiler användas. Om du vill förhindra att en ogiltig filtyp används, till exempel en bild, visas inte motsvarande filer eller så är de inaktiverade för val i sökvägsläsaren.

**Förhandsgranska markerade filer**

Du kan förhandsgranska de filer du har markerat med knappen **Förhandsgranska** enligt nedan:

![](images/select-file-preview-button.png){width="650" align="left"}

Förhandsgranskningen av den valda filen visas till höger.

![](images/select-file-dialog-preview.png){width="650" align="left"}

För flera markeringar visas en förhandsvisning av alla markerade filer på förhandsgranskningspanelen för enkel granskning.

![](images/reusable-content-selection-left-panel.png){width="650" align="left"}

Du kan också använda ikonen **Ta bort** för att avmarkera vissa filer i förhandsvisningen.

![](images/resusable-content-remove-preview.png){width="650" align="left"}

**Sök och filtrera upplevelsen**

När du bläddrar bland filer i databasen kan du söka efter filer efter namn, titel eller innehåll i den valda sökvägen. Du kan använda ett, två eller alla tre villkor för sökningen. Om inget av villkoren är markerat, kommer resultatet att innehålla gemensamma värden för alla tre kriterierna.

![](images/select-file-search.png){width="650" align="left"}

Välj ikonen **Filtersökning** \(![Sökfilterikon](images/filter-search-icon.svg)\) för att öppna filterpanelen till höger.

![](images/select-file-filters.png){align="left"}

Du har följande alternativ för att filtrera filerna och begränsa sökningen:

- **Sök i**: Välj den sökväg där du vill söka efter filerna som finns i databasen.

- **Filtyp**: Filtrera sökningen baserat på en viss filtyp. Tillgängliga alternativ är: **Ämne**, **Karta**, **DITAVAL**, **Bild**, **Multimedia**, **Dokument** och **Övriga**.

  >[!NOTE]
  >
  > I vissa fall tillämpas filtret **Filtyp** i förväg på specifika filtyper baserat på uppgiften och kan inte ändras. När du t.ex. bläddrar efter en bild är filtret inställt på att endast visa bildfiler, och när du skapar återanvändbart innehåll är det inställt på att endast visa ämne- och mappfiler. Du kan fortfarande justera andra filter som dokumentläge, taggar eller datum för senaste ändring för att förfina sökresultaten.

- **Dokumenttillstånd**: Du kan filtrera sökningen baserat på filernas aktuella dokumenttillstånd. De tillgängliga filtervärdena definieras i fältet `repositoryFilters` i `ui_config.json file` och är associerade med den mappprofil som du använder för närvarande.

  Detta innebär:

   - Om du använder den globala profilen tillämpas filtervärdena som konfigurerats i den globala profilen.
   - Om du väljer en viss mappprofil hämtas filtervärdena som definierats i den profilen.

  Standardfiltervärdena som är tillgängliga för dokumentläget är: Utkast, Redigera, Granskning, Godkänd, Granskad och Klar. Mer information om hur du anpassar filtervärden för dokumentlägen finns i [Konfigurera dokumenttillståndsfilter](../cs-install-guide/config-doc-state-filters.md).

- **Låst av**: Visar en lista över användare. Listan sidnumreras och läses in asynkront, med en begränsad uppsättning användare åt gången och fler hämtas när du rullar eller navigerar. Detta förbättrar inläsningshastigheten och övergripande prestanda, särskilt när du arbetar med ett stort antal användare.

- **Senast ändrad**: Filtrera innehåll baserat på ändringsdatum. Välj ett datumintervall i kalendern eller välj något av följande alternativ för tidsram:
   - I förra veckan
   - Under den senaste månaden
   - Under förra året

- **Taggar**: Filtrera innehåll baserat på taggar.

- **DITA-element**: Filtrera innehåll baserat på olika DITA-element.

När du har använt alla nödvändiga filter väljer du **Använd** längst ned till höger på panelen Filter.

**Tillgängliga funktioner på fliken Samlingar för filbläddring**

Fliken **Samlingar** innehåller en välstrukturerad vy med filer som är tillgängliga i dina samlingar så att du snabbt kan komma åt och återanvända dem. Till skillnad från fliken Databas, som visar hela mapphierarkin, kan du med samlingar välja ämnen, kartor och bilder som du använder ofta utan att behöva navigera i flera mappar.

![](images/select-file-collections.png)

På fliken Samlingar kan du:

- Navigera smidigt genom dina samlingar med hjälp av länkarna längst upp och på mappnavigeringspanelen till höger.

  ![](images/collections-folder-navigation-panel.png)
- Markera filer som finns i en viss samlingssökväg och förhandsgranska dem i den högra panelen.

  ![](images/collections-file-preview.png)



### Webbläsarmappar i databasen

Genom att bläddra bland mappar med dialogrutan **Välj mapp** kan du fokusera på att välja rätt mappsökväg i databasen för uppgifter som att skapa nya ämnen eller ange utdataplatser för publicerat innehåll. Den ger en tydlig, trädstrukturerad vy över mappar, vilket gör navigeringen intuitiv och säkerställer att innehållet placeras på rätt plats.

![](images/select-path-dialog-new.png){width="300" align="left"}


## Stöd för artikelbaserad publicering

I redigeraren kan du generera utdata för ett eller flera ämnen, eller för hela DITA-kartan. Du måste skapa förinställningar för DITA-kartan och sedan enkelt generera utdata för ett eller flera ämnen. Om du har uppdaterat några avsnitt på kartan kan du även generera utdata endast för dessa ämnen från redigeraren. Mer information finns i [Artikelbaserad publicering](web-editor-article-publishing.md#id218CK0U019I).

## Stöd för markeringsdokument

I redigeraren kan du använda Markdown-dokument \(.md\) tillsammans med DITA-dokument. Du kan enkelt skapa och förhandsgranska ett markeringsdokument i redigeraren och även lägga till det i kartfilen via DITA-kartredigeraren. Mer information finns i [Författarmarkeringsdokument från redigeraren](web-editor-markdown-topic.md#).

## Stöd för DITA ordlistetema

Redigeraren stöder DITA-ordlistor som du kan infoga genom att lägga till `term`- eller `abbreviated-form`-element.

## Arbeta med MathML-ekvationer

### Infoga MathML-ekvationer

Experience Manager Guides har ett körklart stöd för att infoga MathML-ekvationer genom integrering med [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro) -programmet. Om du vill infoga en MathML-ekvation väljer du ikonen **Element** och skriver mathml. När du väljer matematiska element i listan visas dialogrutan **Infoga MathML**:

![infoga matematisk ekvation i matematisk redigerare](images/insert-mathml-equation.png){width="550" align="left"}

Skapa ekvationen med MathML ekvationsverktyg och välj **Infoga** för att lägga till den i dokumentet. Ekvationen infogas med ljusgrå bakgrund.

Du kan när som helst uppdatera en ekvation genom att högerklicka på en befintlig ekvation och välja **Redigera MathML** på snabbmenyn.

### Validering av ekvationer i MathML Editor

Experience Manager Guides validerar MathML ekvationer när du sparar ett ämne som innehåller dem.
När du infogar en ekvation med MathML Editor markeras ekvationen i rött om det finns syntaxproblem i Experience Manager Guides. Du kan korrigera det innan du infogar det. Om du inte gör några ändringar men väljer **Infoga** visas en varning.

![validera matematisk ekvation](images/validate-mathml-equation.png){width="400" align="left"}

Om du infogar den MathML-ekvation som innehåller ett syntaxfel inträffar ett valideringsfel när du försöker spara ämnet.


## Infoga fotnoter

Infoga fotnot i innehållet med elementet `fn`. I redigeringsläget visas fotnotens värde i linje med innehållet. När du byter förhandsgranskningsläge eller publicerar dokumentet visas dock fotnoten i slutet av avsnittet.


## Byta namn på eller ersätta ett element

Elementets vägbeskrivningar visas längst ned till vänster i avsnittet. Om du vill byta ut eller ersätta ett element mot ett annat element kan du göra det på snabbmenyn för vägbeskrivningsfilen. Du kan till exempel växla elementet `p` med `note` eller något annat giltigt element i kontexten.

![](images/rename-element.png){width="400" align="left"}

Högerklicka på namnet på ett element som du vill ersätta på sidlisten och välj sedan Byt namn på element på snabbmenyn. I dialogrutan Byt namn på element visas alla giltiga element som är tillåtna på den aktuella platsen. I dialogrutan Ändra namn på element markerar du det element som du vill använda. Det ursprungliga elementet ersätts med det nya elementet.

Förutom snabbmenyn för den synliga sökvägen kan du även öppna dialogrutan Byt namn på element från andra platser:

- Markera elementnamnet på den synliga sökvägen för att markera innehållet i elementet och högerklicka på det markerade innehållet för att visa snabbmenyn.

- Aktivera taggvyn, markera öppningstaggen för ett element och högerklicka sedan på det markerade innehållet för att visa snabbmenyn.

- Du kommer åt dialogrutan Byt namn på element genom att öppna Alternativ-menyn för ett element på panelen Kontur.

## Bryta och dela upp ett element

### Radbryta ett element

- När du kapslar ett element kan du lägga till en elementtagg i den markerade texten. Du kan radbryta texten till vilket underordnat element som helst enligt DITA-standarder. Om du till exempel har text under ett `note`-element kan du kapsla in texten i ett `p` -element.

- Alternativet **Radbryt element** är tillgängligt på snabbmenyn för avsnittets vägbeskrivningar. Om du vill kapsla in ett element högerklickar du på elementet och öppnar snabbmenyn. Markera elementet i dialogrutan **Radbryt element**. Texten visas i det nya elementet.

- Du kan också markera texten eller elementet i innehållet och sedan välja alternativet **Radbryt element** på snabbmenyn.

### Dela upp ett element

Om du tar bort ett element kan du ta bort elementtaggen från den markerade texten och sammanfoga den med det överordnade elementet. Om du till exempel har ett `p`-element i ett `note` -element kan du dela upp `p`-elementet och sammanfoga texten direkt i `note` -elementet. Alternativet **Bryt upp element** är tillgängligt på snabbmenyn för avsnittets synliga del. Om du vill dela upp ett element högerklickar du på elementet för att öppna snabbmenyn och väljer sedan **Dela upp element** för att ta bort elementet och sammanfoga elementets text med dess överordnade element.

## Hantering av tomt utrymme för DITA-element

I XML-format innehåller blanksteg, tabbar, radbrytningar och tomma rader. Experience Manager Guides konverterar flera efterföljande blanksteg till ett blanksteg. Detta gör att du kan bevara WYSIWYG-vyn i Redigeraren.

>[!NOTE]
>
> I vissa element där blanktecken måste bevaras enligt DITA-reglerna behålls de efterföljande blanktecknen. Exempel: `<pre>` och `<codeblock>` element.


## Bevara radbrytningar och indrag

DITA-element som innehåller radbrytningar och blanksteg stöds och återges enligt definitionen i redigeringsläget, Source- eller förhandsgranskningsläget samt i det slutliga publicerade resultatet. På följande skärmbild visas innehållet i elementet `msgblock` där radbrytningarna och mellanrummen \(indrag\) har bevarats:

![](images/new-line-support_cs.png){align="left"}



## Hantera fasta mellanslag i redigeraren

- Du kan infoga fasta mellanslag i dokumentet med hjälp av ikonen **Symbol** ![](images/symbol-icon.svg) eller kortkommandona **Alt** + **Blanksteg** .  Dessa fasta mellanslag visas som en indikator när du redigerar ett ämne i redigeraren. Du kan inaktivera visningen av fasta mellanslag med alternativet **Visa fasta mellanslag i redigeringsläget** på fliken **Utseende** i [Användarinställningar](./intro-home-page.md#user-preferences).

- Om du kopierar och klistrar in innehåll med fast mellanslag från externa källor i vyn **Författare** konverteras det fasta utrymmet till ett mellanslag.
Om du kopierar och klistrar in innehåll med fast mellanslag från vyn **Författare** bevaras det.


## Generera element-ID automatiskt

Du kan automatiskt generera ID:n för elementen i ditt DITA-avsnitt. Dessa ID:n är unika inom ett DITA-avsnitt. Om du till exempel genererar ID:n för ett styckeelement kommer ID:n att vara p\_1, p2, p\_3 och så vidare. Du kan välja flera element och generera ID:n för varje markerat element.

Gör följande för att automatiskt generera ID för ett eller flera element:

1. Öppna ämnet i Redigeraren.
1. Markera innehållet som du vill tilldela ID:n till.
1. Högerklicka och välj **Generera ID:n** på snabbmenyn.

Du kan också högerklicka i vägbeskrivningsfilen och välja **Generera ID**.

## Identifiera duplicerade ID:n för element i en karta eller ett ämne i redigeringsvyn

Om ett visst ämne eller en viss karta innehåller element med duplicerade ID:n visas knappen **Duplicera ID:n** längst ned till höger i området för innehållsredigering bredvid redigeringsvyerna.

![](images/duplicate-element-IDs.png){width="350" align="left"}

Om du väljer **Duplicerade ID:n** öppnas en portfölj med alla dubblett-ID:n. Du kan välja det visade ID:t från porten för att navigera till motsvarande element och uppdatera det med ett unikt ID.

>[!NOTE]
>
> Knappen **Duplicera ID:n** är bara tillgänglig i vyn **Författare** och liknande element-ID:n tillåts i olika kapslade ämnen.


## Hantera stora filer i Redigeraren

De viktigaste funktionerna för att förbättra hanteringen av stora filer är följande:

- För att förbättra prestanda är vissa funktioner som Ångra, Gör om, konturpanelen och den smutsiga markören inaktiverade. Vi rekommenderar att du delar upp ämnen i mindre ämnen för att få en optimal upplevelse.

- Ett varningsmeddelande visas längst upp för stora filer, vilket visas i utdraget nedan. Den här varningen markerar antalet element baserat på det värde som anges i parametern **largeFileTagCount** i filen uiconfig.json. Som standard är **largeFileTagCount** inställt på 2 500.

![](images/add-toast-notification.png){width="600" align="left"}


- Dessutom visas antalet taggar i det nedre fältet i gränssnittet. När du hovrar över det här värdet för taggantal visas ett verktygstips. Om du väljer fliken **Läs mer** får du information om hur du hanterar stora filer.

![](images/add-toast-tag-count.png){width="600" align="left"}


- Varningsmeddelandet är bara tillgängligt för DITA-filer och är synligt i alla vyer: Författare, Source och Layout.

**Överordnat ämne:**[ Introduktion till redigeraren](web-editor.md)
