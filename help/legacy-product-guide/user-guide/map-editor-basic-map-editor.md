---
title: Arbeta med den grundläggande kartredigeraren
description: Lär dig hur du arbetar med den grundläggande kartredigeraren i AEM Guides. Lär dig funktionerna i den grundläggande kartredigeraren på mappnivå och ämnesnivå. Skapa och redigera relationstabeller i en DITA-karta.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 194caf31-15ae-436d-bbd4-3ea4907c7877
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 0%

---

# Arbeta med den grundläggande kartredigeraren {#id1942CM005Y4}

>[!NOTE]
>
> Redigeraren för den grundläggande kartan, som tidigare fanns i Experience Manager Guides, har tagits bort från version 4.3 och 2307. Du har inte åtkomst till redigeraren för grundläggande kartor för att skapa och hantera DITA-kartor.
>Du rekommenderas att använda den avancerade kartredigeraren. Avancerad kartredigerare har förbättrade funktioner och bättre alternativ för anpassning. Läs mer om hur du arbetar med [Avancerad kartredigerare](../user-guide/map-editor-advanced-map-editor.md).

Med den grundläggande redigeringsfunktionen för kartor kan du enkelt dra-och-släppa för att lägga till ämnen från AEM-databasen och skapa en DITA-karta eller en bokkarta. Du kan lägga till kapslade ämnen, relationstabeller, attribut och metadatainformation och även validera kartan för att se om den är korrekt.

>[!NOTE]
>
> Om administratören har aktiverat alternativet Avancerad kartredigerare har du inte tillgång till den grundläggande kartredigeraren. Alla kartfiler öppnas som standard i Avancerad kartredigerare.

I följande avsnitt beskrivs de olika funktioner som är tillgängliga i redigeraren för grundläggande karta.

## Lägga till ämnen i en kartfil {#id193CBL0505Z}

När en kartfil har skapats måste du lägga till ämnen i kartfilen. Med hjälp av den grundläggande kartredigeraren kan du lägga till ämnen, relationstabeller eller andra kartfiler.

Utför följande steg för att skapa kartfilen:

1. Navigera i Assets-gränssnittet till den kartfil som du vill redigera.

1. Om du vill låsa kartfilen exklusivt markerar du kartfilen och klickar på **Checka ut**.

   >[!NOTE]
   >
   > När du har ett exklusivt lås på en kartfil kan andra användare inte redigera kartan. De kan dock arbeta med ämnen i kartfilen.

1. Markera kartfilen och klicka på **Redigera**.

   Kartfilen öppnas för redigering i kartredigeraren. Med hjälp av kartredigeraren kan du skapa en karta med hjälp av de ämnen som för närvarande är tillgängliga och som visas i referensfältet.

   ![](images/dita-map-01.png){width="800" align="left"}

1. Navigera till mappen som innehåller de ämnen eller undermappar som du vill lägga till med hjälp av **referenserna** .

   >[!NOTE]
   >
   > Du kan lägga till ämnen eller undermappar från valfri mapp i referensfältet.

1. Om du vill lägga till det första avsnittet på kartan drar och släpper du ämnet på snabbredigeraren.

   >[!NOTE]
   >
   > När du har lagt till den första länken är länken Lägg till ny referens tillgänglig när du håller muspekaren över ett befintligt ämne på kartan.

1. Om du vill lägga till efterföljande ämnen eller en undermappning drar och släpper du ämnet eller undermappningen till önskad plats på kartan.

   Om du lägger till en undermapp till din DITA-karta visas underkartan som en länk i DITA-kartan. Om du vill visa alla ämnen i underkartan klickar du på länken för underkartan. Undermappens innehåll visas på en ny flik.

   >[!NOTE]
   >
   > Om du släpper ett nytt ämne i ett befintligt ämne på kartan visas ett meddelande om att ersätta ämnet. Klicka på Ja om du vill ersätta ämnet och klicka på Nej om du inte vill ersätta ämnet. Du kan använda CTRL+Z och CTRL+Y för att ångra eller göra om ändringar i kartan.

1. Klicka på **Spara**.


## Funktioner som är tillgängliga i verktygsfältet i redigeraren för grundläggande karta

I huvudverktygsfältet i redigeraren för grundläggande kartor kan du utföra följande åtgärder:

![](images/ditamap-toolbar-actions.png){width="800" align="left"}

**A: Sök**

Du kan söka efter och ta med de ämnen som behövs från DAM. Om du klickar på den här ikonen visas dialogrutan Sök:

![](images/search-dita-map.png){width="800" align="left"}

Ange de nyckelord som du vill söka efter. Dessa nyckelord matchas i ämnets filnamn, innehåll och till och med attributvärden. När sökresultaten är tillgängliga markerar du det önskade ämnet och klickar på knappen Markera för att lägga till de markerade filerna i slutet av kartstrukturen. Du kan filtrera sökresultaten genom att ange parametrar för Ändra datum.

**B: Grupp**

Klicka i kryssrutan till vänster om ämnena och klicka på Gruppera i verktygsfältet för att gruppera de markerade ämnena. Mer information om att gruppera ämnen finns i [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) -dokumentationen i språkspecifikationen för OASIS DITA.

**C: Ta bort**

Klicka i kryssrutan till vänster om ett ämne och klicka på Ta bort i verktygsfältet för att ta bort de markerade ämnena från kartan.

**D: Visa siffror/dölj nummer**

Visa \(eller dölj\)-numrering för avsnitten i kartan.

**E: Validera**

Kontrollera om kartan är giltig eller innehåller fel.

**F: Standardläge/XML-läge**

Om du klickar på en ämneslänk i **standardläget** visas en förhandsgranskning av ämnet på en ny flik. Om du klickar på ikonen **Standardläge** ändras dess läge till **XML-läge**. Om du klickar någonstans i en ämnesrad i **XML-läge** visas den underliggande XML-koden för ämnesreferenserna i avsnittet. I XML-källvyn finns det ett alternativ för **automatiskt indrag** som ordnar om XML-koden i ett presenterbart och lättläst format. Om du redigerar en karta manuellt utför källvyn även valideringskontroller. Om XML-filen innehåller fel markeras samma sak i **XML-läget** och du får inte spara DITA-mappningsfilen. Om du vill visa XML-koden för hela kartan klickar du var som helst utanför ämnesgränsen.


**Obs!** I standardläget kan du använda kortkommandona för att ångra \(`Ctrl+z`\) eller göra om \(`Ctrl+y`\) den senaste åtgärden.


![](images/dita-map-invalid-source.png){width="650" align="left"}

**G: Kartegenskaper**

Visa dialogrutan Kartegenskaper där du kan ange attribut och metadatainformation för kartan. Om du vill lägga till ett attribut klickar du på knappen **Lägg till** längst ned till vänster i dialogrutan för att visa listrutan **Attribut**. Välj det attribut du vill lägga till i listan. Om det markerade attributet har fördefinierade värden som anges i DTD:n visas dessa värden i en ny listruta. Du kan välja önskat värde i listrutan. Om det inte finns något fördefinierat värde visas en textruta där du kan ange ett värde för det valda attributet.

![](images/map-properties.png){width="300" align="left"}

## Funktioner på ämnesnivå i Grundläggande kartredigerare

När du placerar muspekaren över ett ämne eller en undermappsfil i redigeraren för den grundläggande kartan kan du utföra följande åtgärder:

![](images/ditamap-actions.png){width="650" align="left"}

**A: Flytta åt vänster eller Flytta åt höger**

Klicka på vänster- eller högerpilsikonerna för att flytta ämnet åt vänster eller höger. Om du flyttar ett ämne på ett sådant sätt blir det ett underordnat \(kapslat\) eller syskon \(ta bort kapsling\) med avseende på ämnet ovan.

**B: Egenskaper**

Klicka på ikonen Egenskaper för att öppna dialogrutan Egenskaper för utskrift. I den här dialogrutan kan du ange ämnesattribut och metadatainformation. Mer information om standardämnesattribut och metadata finns i [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) -dokumentationen i språkspecifikationen för OASIS DITA.


![](images/map-properties-metadata.png){width="350" align="left"}

**C: Lägg till ny referens**

Klicka på ikonen Lägg till ny referens om du vill lägga till en ny referens på samma nivå som det aktuella ämnet.

**D: Lägg till ny nyckeldefinition**

Klicka på Key-ikonen för att lägga till en ny nyckeldefinition. Alla åsidosatta tangenter eller tangenter som redan har definierats på kartan visas i rött. Om du klickar på egenskapsikonen för en nyckeldefinition visas dialogrutan Egenskaper för nyckelbild.

## Arbeta med relationstabeller i den grundläggande kartredigeraren {#id1944B0I0COB}

AEM Guides karteditorer har en kraftfull funktion som gör att du kan skapa och redigera relationstabeller på din DITA-karta.

Utför följande steg när du vill arbeta med relationstabeller i redigeraren för den grundläggande kartan:

1. I Assets-gränssnittet navigerar du till den DITA-karta som du vill skapa relationstabellen i.

1. Klicka på DITA-kartan för att öppna den i DITA-kartkonsolen.

1. Välj fliken **Ämnen** om du vill visa en lista med ämnen som är tillgängliga på DITA-kartan.

   >[!TIP]
   >
   > På fliken Ämnen kan du hämta kartfilen med tillhörande beroenden. Mer information finns i [Exportera en DITA-kartfil](authoring-download-assets.md#id218UBA00IXA).

1. Klicka på **Redigera** i huvudverktygsfältet.

   Kartfilen öppnas i den grundläggande kartredigeraren.

1. Välj **Relaterbar** i verktygsfältet.

   ![](images/reltable.png){width="650" align="left"}

1. Dra och släpp ämnen från ämneslistan till Reltable-redigeraren.

   >[!NOTE]
   >
   > Du kan lägga till ämnen från valfri mapp i referensfältet.

   ![](images/create-reltable.png){width="550" align="left"}

1. Om du vill lägga till en rubrik i din relationstabell klickar du på **Lägg till ny rubrik**.

1. Om du vill lägga till en kolumn i din relationstabell klickar du på **Lägg till en kolumn**.

   ![](images/complete-reltable.png){width="550" align="left"}

1. Klicka på **Spara**.


Du kan även utföra följande åtgärder från relationstabellredigeraren:

**Ta bort rader eller kolumner**

Om du vill ta bort en kolumn från tabellen markerar du kryssrutan i kolumnrubriken och klickar på Ta bort. Om du vill ta bort en rad från tabellen markerar du kryssrutan i den första kolumnen i respektive rad och klickar på Ta bort.

**Ta bort ett ämne**

Om du vill ta bort ett ämne från tabellen klickar du på kryssikonen bredvid ämnet.

**Ta bort relationstabellen**

Om du vill ta bort relationstabellen klickar du utanför relationstabellen och klickar på Ta bort.

**Överordnat ämne:**[ Arbeta med kartredigeraren](map-editor.md)
