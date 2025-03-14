---
title: Arbeta med den avancerade kartredigeraren
description: Lär dig arbeta med den avancerade kartredigeraren i AEM Guides. Lär dig funktionerna i den avancerade kartredigeraren. Redigera ämnen via en DITA-karta och använd layoutvyn, författarvyn och förhandsgranskningsläget.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: b63d7c0f-9c29-4fb4-b8fe-9790b16f8726
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '3788'
ht-degree: 0%

---

# Arbeta med den avancerade kartredigeraren {#id1942D0S0IHS}

Avancerad kartredigerare har ett intuitivt användargränssnitt och liknar Web Editor. När du öppnar en kartfil i Web Editor får du ett alternativ för att redigera kartfilen med hjälp av gränssnittet Avancerad kartredigerare. Med Avancerad kartredigerare kan du lägga till ämnesreferenser, nyckelreferenser, strukturera innehållet och mycket annat.

Förutom att redigera kartfiler direkt från Web Editor kan du även öppna ämnesfiler i en karta för redigering i Web Editor. I det här avsnittet beskrivs funktionerna i Avancerad kartredigerare och hur du kan öppna och redigera filer i en DITA-karta i webbredigeraren.

## Lägga till ämnen i en kartfil

Utför följande steg för att skapa kartfilen med hjälp av den avancerade kartredigeraren:

1. Navigera i Assets-gränssnittet till den kartfil som du vill redigera.

   >[!NOTE]
   >
   > Kontrollera att du inte har aktiverat resursurvalsläget.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och klickar på **Checka ut**.

   >[!NOTE]
   >
   > När du har ett exklusivt lås på en kartfil kan andra användare inte redigera kartan. De kan dock arbeta med ämnen i kartfilen. Om administratören har konfigurerat Web Editor för att checka ut filer innan du redigerar kommer du inte att kunna redigera en fil förrän du checkar ut den. Om den är konfigurerad blir du ombedd att checka in en utcheckad fil innan du stänger den

1. När kartfilen är markerad klickar du på **Redigera ämnen**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   Du kan också välja alternativet **Redigera ämnen** på Åtgärdsmenyn i kartfilen:

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   Kartfilen öppnas för redigering i webbredigeraren.

1. Klicka på ikonen **Redigera** .

   ![](images/edit-map-icon.png){width="550" align="left"}

   Kartan öppnas i gränssnittet Avancerad kartredigerare. Om du har öppnat en ny kartfil visas endast kartans titel i redigeraren.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Huvudverktygsfältet*\): Det här liknar huvudverktygsfältet i Web Editor. Mer information finns i [Huvudverktygsfältet](web-editor-features.md#id2051EA0G05Z) i webbredigeraren.

   - **B** - \(*Sekundärt verktygsfält*\) Det här är det sekundära verktygsfältet där du kan arbeta med kartfiler. Mer information om de funktioner som är tillgängliga via det sekundära verktygsfältet finns i [Funktioner som är tillgängliga i den avancerade kartredigerarens verktygsfält](#id205DEC0005Z).

   - **C** - \(*Kartvyer*\): Gör att du kan växla mellan layouten, författaren, Source och förhandsgranskningen i Kartredigeraren. I vyn **Layout** kan du ordna ämnen i en DITA-karta. Detta ger kartans träd eller hierarkiska vy. I vyn **Författare** kan du redigera ämnen i Kartredigeraren. Detta ger även en WYSIWYG-vy över kartfilen. I vyn **Source** kan du arbeta med kartfilens underliggande XML. Med Förhandsgranska får du en samlad vy över alla avsnitt och undermappar i kartfilen. Mappningsfilen stängs av länken **Stäng**.

   - **D** - \(*Vänster panel*\): Ger åtkomst till den vänstra panelen, vilket ger dig tillgång till funktionerna Favoriter, Databas, Karta, Kontur och andra. Du kan expandera eller komprimera den genom att klicka på ikonen Expandera sidofält \(![](images/sidebar-expand-icon.svg)\). Mer information om de funktioner som är tillgängliga i den vänstra panelen finns i [Vänster panel](web-editor-features.md#id2051EA0M0HS) i Web Editor.

   - **E** - \(*Mittområde*\): Mappa innehållets redigeringsområde.

   - **F** - \(*Högerpanel*\): Ger åtkomst till panelen Egenskaper. Du kan se innehållsegenskaperna och mappningsegenskaperna för det markerade ämnet eller kartan. Mer information om de funktioner som är tillgängliga på den här panelen finns i [Högerpanelen](web-editor-features.md#id2051EB003YK) i webbredigeraren.

1. I den vänstra panelen växlar du till **databasvyn**.

1. I AEM-databasen navigerar du till den mapp som innehåller de ämnen eller undermappar som du vill lägga till.

1. Markera ämne- eller mappfilen i **databasvyn** och dra och släpp den i redigeringsområdet för kartinnehåll.

   Ämnet läggs till på kartan.

   ![mappningsredigeraren lägger till ämne](images/map-editor-add-topic.png){width="800" align="left"}

1. Om du vill lägga till efterföljande ämnen eller en undermappning drar och släpper du ämnet eller undermappningen till önskad plats på kartan.

   Tänk på följande när du skapar kartfilen:

   - Filen läggs till på en plats där det vågräta fältet visas i kartredigeringsområdet. I följande skärmbild läggs avsnittet *Översikt* till mellan avsnitten *Allmän beskrivning* och *Start och Landing Site*.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - Om du vill ersätta ett ämne placerar du ämnet överst, till vänster eller till höger om det ämne som du vill ersätta. Ett lodrätt fält till vänster eller höger om ett ämne anger att det kommer att ersättas med det ämne som släpps på det.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     Innan du ersätter ett ämne får du dock en bekräftelse. Ämnet ersätts först när du har bekräftat det.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - Om du lägger till en undermapp till din DITA-karta visas underkartan som en länk i DITA-kartan. Om du vill visa alla ämnen i underkartan Ctrl-klickar du på länken för underkartan. Undermappens innehåll visas på en ny flik. Om du vill öppna ett ämne från DITA-kartan Ctrl-klickar du på ämneslänken så öppnas det på den nya fliken.

   - Du kan använda kortkommandona CTRL+Z och CTRL+Y eller deras respektive ikoner i verktygsfältet för att ångra eller göra om ändringar i kartan.

   - Om du vill ändra positionen för ett ämne markerar du ämnet \(genom att klicka på avsnittsikonen\) och drar och släpper det på önskad plats i kartfilen. Kontrollera att det vågräta fältet är synligt på den plats där du vill placera ämnet. På följande skärmbild flyttas ämnet *Start- och landningswebbplats* efter ämnet *Översikt* .

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - Om du vill kontrollera kartfilens egenskaper högerklickar du var som helst i kartredigeringsområdet och väljer **Egenskaper** på snabbmenyn. Baserat på din AEM-version kan du se egenskaper som metadata, schemaaktivering, referenser, dokumenttillstånd med mera.

1. Klicka på **Spara**.


## Funktioner i verktygsfältet i Avancerad kartredigerare {#id205DEC0005Z}

Verktygsfältet i Avancerad kartredigerare liknar avsnittet Webbredigerare. Grundläggande åtgärder som att växla den vänstra panelen, spara karta, skapa en ny version av kartan, ångra/göra om senaste åtgärden och ta bort de markerade elementen är vanliga i båda redigerarna. Mer information om hur de här åtgärderna fungerar finns i avsnittet [Känn till Web Editor-funktioner](web-editor-features.md#).

Följande kartspecifika åtgärder är också tillgängliga i verktygsfältet i layoutvyn och författarvyn:

## Layoutvyn {#id205DEC0005Z_layout_view}

När du öppnar en karta för redigering öppnas layoutvyn i kartredigeraren. I layoutvyn visas karthierarkin i en trädvy där du kan ordna avsnitten i en karta.

>[!NOTE]
>
> I layoutvyn visas endast de referenser som finns i en karta. Om några referenser bryts visas en liten tvärsymbol till vänster om referensen

Du kan utföra följande åtgärder i layoutvyn:

**Infoga ämnesreferens** - ![](images/insert-topic-reference.png)

Visar dialogrutan för ämnessökning. Navigera till avsnittet/mappfilen som du vill infoga och klicka på Välj för att lägga till den på kartan.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Infoga ämnesgrupp** - ![](images/insert-topic-group.png)

Infoga elementet `topicgroup`. Mer information om att gruppera ämnen finns i [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) -dokumentationen i språkspecifikationen för OASIS DITA.

**Infoga nyckeldefinition** - ![](images/Key_icon.svg)

Visar dialogrutan Infoga nyckelord. Använd den här dialogrutan för att definiera en nyckeldefinition som du vill använda på kartan.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Infoga före/infoga efter** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Visar dialogrutan Infoga element. Markera det element som du vill infoga på kartan. Beroende på åtgärden infogas det nya elementet före eller efter det aktuella elementet i kartan.

**Infoga frontpunkt** - ![](images/frontmatter.svg)

Den här ikonen visas när du öppnar ett bokschema för redigering. Du kan infoga komponenter i början av boken som en innehållsförteckning, ett index och en lista med tabeller.

**Infoga Bakgrundsfråga** - ![](images/backmatter.svg)

Den här ikonen visas när du öppnar ett bokschema för redigering. Du kan infoga komponenter för en ände av boken som ett index, en ordlista och en lista med illustrationer.

**Flytta det markerade objektet åt vänster/höger** - ![](images/left-arrow-icon.png) / ![](images/right-arrow-icon.png)

Klicka på vänsterpilen om du vill flytta ämnet mot vänster sida i hierarkin. Detta befordrar i huvudsak respektive ämne en nivå upp i hierarkin. Om du till exempel klickar på vänsterpilen medan ett underordnat ämne är markerat blir det samma ämne som det ovanför. På samma sätt, om du klickar på högerpilen, flyttas ämnet åt höger så att det blir underordnat ämnet ovanför det.

**Flytta det markerade objektet uppåt/nedåt![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Klicka på upp- eller nedpilsikonerna för att flytta ämnet uppåt eller nedåt i hierarkin.

>[!NOTE]
>
> Du kan också dra och släppa referenserna för att flytta dem på en karta.

**Lås/lås upp** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Hämtar ett lås på kartfilen och släpper låset. Om du har osparade ändringar i kartfilen uppmanas du att spara kartfilen när du släpper låset. Ändringarna sparas i den aktuella versionen av kartfilen.

**Sammanfoga** - ![](images/merge-icon.svg)

Mer information om hur du sammanfogar innehåll från en annan version av samma eller en annan fil finns i [Sammanfoga](web-editor-features.md#id205DF04E0HS) i webbredigeraren.

**Versionshistorik** - ![](images/version-history-web-editor-ico.svg)

Kontrollera de tillgängliga versionerna och etiketterna för det aktiva ämnet och gå tillbaka till valfri version från redigeraren.

**Versionsetikett** - ![](images/version-label-icon.svg)

Visar dialogrutan för versionsetiketthantering. Välj en version i listrutan. Välj den etikett som du vill använda för den valda versionen och klicka på **Lägg till etikett** för att lägga till den.

**Visningsalternativ** - ![](images/view-options.svg)

Visar en listruta där du kan välja Visa radnummer, Visa kryssruta och Visa filnamn.

- **Visa radnummer**

Visar eller döljer radnumret för varje ämne. Radnumren visas beroende på nivån i hierarkin.

- **Visa kryssruta**

Visar eller döljer en kryssruta för varje ämne. Du kan använda kryssrutan för att markera ämnet och utföra olika åtgärder på Alternativ-menyn. Mer information finns på menyn [Alternativ](#id228ID8006H8).

- **Visa filnamn**

Visar filnamnet på ämnesrubrikerna.

>[!NOTE]
>
> När du håller pekaren över ett temats titel visas filsökvägen.


**Visa ämnen baserat på villkorliga filter** Om du har tillämpat villkor i ett ämne visas en filterikon till höger om ämnet. När du håller pekaren över en filterikon visas det använda villkoret och dess attributvärde.

**Alternativ-menyn i layoutvyn**

Förutom att ordna ämnen i kartfilen kan du även utföra följande åtgärder med Alternativ-menyn som är tillgänglig för ett element i layoutvyn:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Lägg till**: Du kan välja att lägga till ett nytt ämne eller en tom referens från kartredigeraren:
   - **Tom referens**: Med det här alternativet kan du lägga till en tom referens i DITA-kartan. Du kan dubbelklicka på den infogade tomma referensen senare och lägga till ämnesinformationen. Mer information finns i [Skapa ett ämne](web-editor-features.md#id228ICI0105U) i webbredigeraren.
   - **Nytt ämne**: När du väljer att skapa ett nytt ämne på menyn visas dialogrutan Skapa nytt ämne. Ange nödvändig information i dialogrutan Skapa nytt ämne och klicka på Skapa. Mer information finns i [Skapa ett ämne](web-editor-features.md#id228ICI0105U) i webbredigeraren.
- **Flytta**: Du kan välja att flytta ett ämne uppåt/nedåt/höger/vänster i hierarkin. Du kan också dra och släppa ett ämne eller en karta från databaspanelen till kartan som öppnas i kartredigeraren.
- **Ångra**: Ångra den senaste åtgärden i layoutvyn.
- **Gör om**: Gör om den senaste åtgärden i layoutvyn.
- **Kopiera**: Kopiera den markerade referensen från kartfilen.

  >[!NOTE]
  >
  > Du kan visa och sedan markera kryssrutorna för att kopiera flera referenser.

- **Klistra in**: Klistra in de kopierade referenserna på den aktuella platsen i hierarkin.
- **Ta bort**: Ta bort de markerade referenserna från mappningsfilen.

  >[!NOTE]
  >
  > Du kan visa och sedan markera kryssrutorna för att ta bort flera referenser.


## Högerpanelen i kartredigeraren

På den högra panelen visas Innehållsegenskaper och Kartegenskaper i layoutvyn i kartredigeraren.

**Innehållsegenskaper**

Panelen Innehållsegenskaper innehåller information om vilken typ av ämne som är markerat på kartan, dess länk-URL och dess attribut. Mer information finns i [Innehållsegenskaper](web-editor-features.md#id228IDB00HMM) i webbredigeraren.

- **Andra attribut** Om administratören har skapat en profil för attribut får du dessa attribut tillsammans med deras konfigurerade värden. Med innehållsegenskapspanelen kan du välja dessa attribut och tilldela dem till relevant innehåll i ditt ämne. Du kan också tilldela attribut som konfigurerats av administratören på fliken **Visningsattribut** i redigeringsinställningarna. De attribut som är definierade för ett element visas i layoutvyn och dispositionsvyn. Detta hjälper dig att snabbt få en överblick över alla ämnen i en karta för vilka ett visst attribut har definierats. Alla ämnen som har plattformsattributet definierat som&quot;Android&quot;.

  ![layoutvy](images/layout-inline-attributes.png){width="650" align="left"}


  Mer information finns i *Visningsattribut* i funktionsbeskrivningen för *redigeringsinställningar* i avsnittet [Vänster panel](web-editor-features.md#id2051EA0M0HS).

- **Metadata** Du kan ange metadatainformation med hjälp av metadata. Du kan definiera navigeringsrubriken, länktexten, kortbeskrivningen och nyckelorden.

Mer information om standardämnesattribut och metadata finns i [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) -dokumentationen i språkspecifikationen för OASIS DITA.

**Kartegenskaper**

Visar dialogrutan Kartegenskaper där du kan ange attribut och metadatainformation för kartan.

## Författarvy {#id205DEC0005Z_author_view}

I vyn **Författare** kan du redigera din DITA-karta i webbredigeraren. Detta visar WYSIWYG-vyn i kartredigeraren och några av de ikoner som visas i redigeringsvyn är desamma som layoutvyn. Mer information finns i [Layoutvyn](#id205DEC0005Z_layout_view). Dessutom kan du se följande ikoner och utföra relaterade uppgifter i redigeringsvyn:

**Infoga före/infoga efter** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Visar dialogrutan Infoga element. Markera det element som du vill infoga på kartan. Beroende på åtgärden infogas det nya elementet före eller efter det aktuella elementet i kartan.

**Infoga element** - ![](images/Add_icon.svg)

Visar dialogrutan Infoga element. Markera elementet som du vill infoga. Du kan använda tangentbordet för att bläddra igenom elementlistan och trycka på Retur för att infoga önskat element. Du kan också klicka direkt på elementet för att infoga det på kartan.

**Infoga relationstabell** - ![](images/relationship_table_icon.svg)

Infogar en relationstabell i kartan. Eftersom begreppet att arbeta med relationstabellen är detsamma som beskrivs i avsnittet Grundläggande kartredigerare finns mer information i [Arbeta med relationstabeller i Grundläggande kartredigerare](map-editor-basic-map-editor.md#id1944B0I0COB).

**Infoga återanvändbart innehåll** - ![](images/content-reuse-icon.png)

Visar dialogrutan Återanvänd innehåll. Använd den här dialogrutan för att infoga innehållet som du vill återanvända på kartan.

**Uppdatera navigeringsrubrikattribut** - ![](images/navtitle-refresh-icon.svg)

Synkroniserar elementet `title` i en refererad fil i en karta med det värde som anges i dess `@navtitle`-attribut. Du kan lägga till olika typer av referensfiler på en karta, till exempel avsnitt-, referens-, uppgift-, \(sub\)-kartor. De flesta av dessa filer stöder attributet `@navtitle`. Om en fil innehåller attributet `@navtitle` uppdateras attributet `@navtitle` för samma fil på kartan. Om attributet `@navtitle` inte finns med läggs attributet `@navtitle` till i referensfilen och dess `title` uppdateras även för att visa `@navtitle`.

>[!NOTE]
>
> Administratören kan konfigurera det automatiskt tillagda attributet `@navtitle` för varje referensfil som du lägger till på en karta. Mer information om hur du konfigurerar automatiskt tillagda `@navtitle`-attribut finns i *Inkludera @navtitle-attribut som standard* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Klicka på ikonen Uppdatera navigeringsrubrikattribut för att synkronisera värdena för elementet `title` och attributet `@navtitle`.

**Växla taggvy** - ![](images/Label_icon.svg)

Visar eller döljer XML-märkorden. Taggarna fungerar som visuella tecken som anger ett elements gräns. I det här läget, om du vill infoga en ämne/mappningsreferens, drar och släpper du den önskade filen före eller efter taggen. Det vågräta fältet visas inte i taggvyn.

**Aktivera/inaktivera spåra ändringar** - ![](images/track-change-icon.svg)

Du kan hålla reda på alla uppdateringar som gjorts i kartfilen genom att aktivera läget Spåra ändringar. När du har aktiverat spårändringar hämtas alla infogningar och borttagningar i dokumentet. Mer information finns i [Aktivera/inaktivera spåra ändringar](web-editor-features.md#id205DF0203Y4) i webbredigeraren.

**Skapa granskningsaktivitet** - ![](images/create-review-task-icon.svg)

Du kan skapa en granskningsåtgärd för det aktuella ämnet eller kartan direkt från webbredigeraren. Öppna filen som du vill skapa granskningsaktiviteten för och klicka på Skapa granskningsuppgift för att starta granskningsprocessen. Följ instruktionerna i [Granska avsnitt eller kartor](review.md#) om du vill ha mer information.

## Redigera ämnen via DITA-kartan {#id17ACJ0F0FHS}

Om du redigerar ett enskilt ämne får inte författaren hela kontexten. En författare har ingen information om var ett ämne placeras på en DITA-karta. Utan den här kontextuella informationen blir det lite svårt för författare att skapa innehåll.

Med AEM Guides kan författare öppna en DITA-karta i webbredigeraren och se var ämnen placeras på kartan. Detta hjälper författare att veta exakt var exakt ämnet placeras på kartan och skapa mer relevant innehåll. Om det finns flera författare som arbetar med ett projekt kan de också veta vilka ämnen som är tillgängliga på kartan och återanvända innehållet där det behövs.

Så här redigerar du ämnen via en DITA-karta:

1. I Assets-gränssnittet navigerar du till DITA-kartan som innehåller de ämnen som du vill redigera.
1. Klicka på DITA-kartan för att öppna den i DITA-kartkonsolen.
1. Välj fliken **Ämnen** om du vill visa en lista med ämnen som är tillgängliga på DITA-kartan.

   >[!TIP]
   >
   > På fliken Ämnen kan du hämta kartfilen med tillhörande beroenden. Mer information finns i [Exportera en DITA-kartfil](authoring-download-assets.md#id218UBA00IXA).

1. Klicka på **Redigera ämnen** i huvudverktygsfältet.

   DITA-kartan öppnas i webbredigeraren.

   >[!NOTE]
   >
   > Du kan också välja DITA-kartfilen i Assets-gränssnittet och klicka på **Redigera ämnen** i huvudverktygsfältet för att starta Web Editor.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Valfritt*\) Du kan också välja ett ämne från kartan och checka ut filen innan du redigerar. Om du vill checka ut filen/filerna markerar du en eller flera filer i den vänstra rutan och klickar på **Checka ut**. Du kan också låsa upp en fil genom att markera den utcheckade filen och klicka på ikonen **Avbryt utcheckning och Lås upp** i kartvyn.

   >[!IMPORTANT]
   >
   > Om administratören har konfigurerat alternativet **Inaktivera redigering utan utcheckning** måste du checka ut filen innan du redigerar. Om du inte checkar ut filen öppnas dokumentet i skrivskyddat läge i redigeraren.

   Följande skärmbild markerar ikonerna för utcheckning och låsning \(A\), Avbryt utcheckning och Lås upp \(B\), Spara som ny version och Lås upp \(C\), Redigera \(D\), Förhandsgranska \(E\), olika ikoner med olika filtyper i DITA \(F\) och filer som är utcheckade \(G\).

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Klicka på en ämneslänk för att öppna den i Web Editor för redigering.

   Du kan öppna flera ämnen i redigeraren och varje ämne öppnas på en ny flik i redigeraren. Även om din DITA-karta innehåller underkartor öppnas även ämnen från underkartorna på en ny flik för redigering. Om du vill visa ämnen under en undermappning kan du klicka på och expandera undermappningen.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Om du klickar på en kartfil öppnas kartan på en ny flik i webbläsaren.

1. När du är klar med redigeringen av ämnena kan du göra följande:

   - Du kan spara dem en och en. Om du klickar på **Stäng utan att spara** dina ämnen visas en dialogruta där du uppmanas att spara de osparade avsnitten:

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     Du kan välja att spara alla markerade ämnen eller avmarkera de ämnen som du inte vill spara.

   - Du kan checka in ämnet med knappen **Spara som ny version och Lås upp** . När du sparar en version av ämnet skapas en ny version och låset släpps också.

     Du bör spara ändringarna innan du checkar in filerna.  När du sparar ändringarna valideras XML-filen.

   - Du kan också markera och checka in flera ämnen med knappen **Spara som ny version och Lås upp** . När du sparar en version av ämnena skapas en ny version för varje ämne, och låset släpps också. Du kan även visa förloppet för att checka in ämnen från dialogrutan **Spara som ny version och Lås upp**. Ett meddelande visas när filerna har checkats in.

   - Om administratören har aktiverat alternativet att checka in filer när de stängs visas en uppmaning om att spara filer när de utcheckade filerna stängs. När det här alternativet är aktiverat visas listan med utcheckade filer som behöver sparas när du stänger redigeraren med ändrade filer. De utcheckade filerna visas med en låsikon:

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Om du klickar på knappen **Stäng utan att spara** stängs filerna utan att några ändringar sparas.

      - Om du klickar på knappen **Spara** sparas ändringarna, men filerna checkas inte in.

      - Om du väljer alternativet **Kontrollera filer** och sedan klickar på knappen **Spara** checkas filerna in \(skapar en annan version\) och filerna sparas också.


## Förhandsgranska en karta

Förutom att kunna se positionen för varje ämnesfil i en karta, är det önskvärt att kartinnehållet visas i ett sammanhängande flöde. Med funktionen Förhandsgranska karta kan du se hela innehållet i karfilen med ett enda klick. Du behöver inte generera utdata från kartfilen för att se hur hela kartan kommer att se ut när den har publicerats. Du kan enkelt öppna kartans förhandsgranskning och alla ämnen och undermappar återges i form av en bok.

Du kommer åt förhandsgranskningen av en karta från:

- **Assets-gränssnitt**: Navigera till kartpositionen i Assets-gränssnittet, markera kartfilen och välj **Förhandsgranska karta** i verktygsfältet. Förhandsgranskningen av kartan visas på en ny flik. Du kan visa innehållet i alla ämnen i förhandsgranskningsläget. I den här vyn kan du inte redigera något ämne.

  >[!NOTE]
  >
  > Om alternativet *Förhandsgranskningskarta* inte visas i huvudverktygsfältet kan det ha flyttats under verktygsfältmenyn **Mer**.

- **Avancerad kartredigerare**: Klicka på förhandsgranskningsikonen i Avancerad kartredigerare om du vill visa förhandsgranskningen av den aktuella kartan.

  ![](images/map-preview-icon.png){width="350" align="left"}

  Du kan utföra följande åtgärder i förhandsgranskningsläget:

   - Högerklicka på ett ämne och välj **Redigera** för att öppna ämnet för redigering på en ny flik.

     >[!NOTE]
     >
     > Om du inte har redigeringsbehörighet öppnas avsnittet i skrivskyddat läge.

   - Hoppa till det önskade avsnittet genom att klicka på ämnesrubriken i schematrädet \(i den vänstra panelen\).

   - Det aktuella avsnittet i förhandsvisningen av kartan markeras också i schematrädet.


**Överordnat ämne:** [Arbeta med kartredigeraren](map-editor.md)
