---
title: Använd DITAVAL-redigerare
description: Lär dig skapa och redigera DITAVAL-filer med DIVATAL Editor i Adobe Experience Manager Guides. Ta reda på hur DITAVAL-redigeraren stöder DITAVAL-filer i skribent- och källvyer.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: cbc9cd59e36dad63b25866b2d5c52a7380dc7d26
workflow-type: tm+mt
source-wordcount: '1501'
ht-degree: 0%

---

# DITAVAL editor {#ditaval-editor}

DITAVAL-filer används för att generera villkorsstyrda utdata. I ett enskilt ämne kan du lägga till villkor med elementattribut för att villkorsanpassa innehållet. Sedan skapar du en DITAVAL-fil där du anger villkoren som ska plockas upp för att generera innehåll och vilket villkor som ska utelämnas från det slutliga resultatet.

Med Adobe Experience Manager Guides kan du enkelt skapa och redigera DITAVAL-filer med DITAVAL-redigeraren. DITAVAL-redigeraren hämtar attributen (som kan användas som villkor) som definierats i systemet, och du kan använda dem för att skapa eller redigera DITAVAL-filer. Mer information om hur du skapar och hanterar villkor i Adobe Experience Manager finns i avsnittet [Administrera taggar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=sv-SE) i Adobe Experience Manager-dokumentationen.

I följande avsnitt beskrivs de alternativ som är tillgängliga för en DITAVAL-fil i Experience Manager Guides.

- [Skapa DITAVAL-fil](#create-ditaval-file)
- [Redigera DITAVAL-fil](#edit-ditaval-file)
- [DITAVAl filredigeringsvyer](#ditaval-editor-views)
- [Arbeta med DITAVAL-filen i Assets-gränssnittet](#working-with-ditaval-files-in-the-assets-ui)

## Skapa DITAVAL-fil

Så här skapar du en DITAVAL-fil:

1. På panelen Databas markerar du ikonen **Ny fil** och väljer sedan **Ämne** i listrutan.

   ![](images/new-file-option.png){width="350" align="left"}

   Du kan även komma åt det här alternativet från [Experience Manager Guides hemsida](./intro-home-page.md) och alternativmenyn för en mapp i databasvyn.

2. Dialogrutan **Nytt ämne** visas.

3. Ange följande information i dialogrutan **Nytt ämne**:
   - En rubrik för ämnet.
   - \(Valfritt\)* Ämnets filnamn. Filnamnet föreslås automatiskt baserat på ämnet Titel. Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen, kommer du inte att visa namnfältet.
   - En mall som ämnet baseras på. För en DITAVAL-fil väljer du **Ditaval** i listrutan.
   - Sökväg där du vill spara ämnesfilen. Som standard visas sökvägen till den markerade mappen i databasen i fältet Sökväg.

   ![](images/new-topic-dialog-ditaval.png){width="350" align="left"}


4. Välj **Skapa**.

Ämnet skapas på den angivna sökvägen. Dessutom öppnas ämnet i Redigeraren för redigering.

![](images/ditaval-file-editor.png){align="left"}

## Redigera DITAVAL-fil

När du skapar ett DITAVAL-ämne öppnas det i Redigeraren för redigering. Om du vill redigera ett befintligt DITAVAL-ämne går du till den mapp eller karta där DITAVAL-avsnittet finns och väljer sedan **Redigera** på **Alternativ** -menyn.

Med DITAVAL-redigeraren kan du utföra flera åtgärder enligt nedan med alternativen i redigerarens verktygsfält.

### Alternativ i verktygsfältet Redigerare

#### Meny-listruta

Menyn ger åtkomst till redigeringsåtgärderna Sök och ersätt, Versionshistorik, Versionsetikett, Sammanfoga, Skapa granskning, Spåra ändringar och Taggar.
Mer information finns i [Alternativ för listrutor på menyn](./web-editor-toolbar.md#menu-dropdown)

#### Lägg till egenskap

Lägg till en enda egenskap i DITAVAL-filen.

![](images/ditaval-editor-props-new.png){width="650" align="left"}

I den första listrutan visas de tillåtna DITA-attribut som du kan använda i DITAVAL-filen.

I den andra listrutan visas de värden som konfigurerats för det valda attributet. I nästa nedrullningsbara lista visas de åtgärder som du kan konfigurera för det valda attributet. De tillåtna värdena i åtgärdslistrutan är - `include`, `exclude`, `passthrough` och `flag`. Mer information om dessa värden finns i definitionen av elementet [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) i dokumentationen för OASIS DITA. Mer information om åtgärden för egenskaperna som lagts till i attributen finns i [Åtgärder för egenskapen](#actions-for-property).

#### Lägg till Rev Prop

Om du vill lägga till ett specifikt versionsnummer i en tagg i XML kan du använda alternativet Lägg till rev.-förinställning. Detta lägger till ett varv-attribut till taggen, med det värde som definieras i fältet Värde tillsammans med den valda åtgärden för egenskapen. Det här revideringsattributet kan senare användas för att filtrera relevant XML-innehåll baserat på det angivna revisionsnumret när utdata genereras.

![](images/ditaval-rev-props.png){width="650" align="left"}

#### Lägg till alla utkast

Om du vill lägga till alla villkorliga egenskaper eller attribut som definieras i systemet med ett enda klick använder du funktionen Lägg till alla uttryck. De tillåtna värdena i åtgärdslistrutan är - `include`, `exclude`, `passthrough` och `flag` . Detaljerna för dessa åtgärder anges nedan.

>[!NOTE]
>
> Om alla definierade villkorliga egenskaper redan finns i DITAVAL-filen kan du inte lägga till fler egenskaper. Du får ett felmeddelande i det här scenariot.


![](images/ditaval-all-props-new.png){width="650" align="left"}



##### Åtgärder för egenskap

Det finns i huvudsak fyra tillgängliga åtgärder för en viss egenskap som kan användas och som listas enligt följande:

**Inkludera:** Inkludera innehållet i utdata. Det här är standardbeteendet om inget annat anges.

**Exkludera:** Uteslut innehållet från utdata (om alla värden i det särskilda attributet utelämnas).

**Genomströmning:** Inkludera innehållet i utdata och bevara attributvärdet som en del av utdataströmmen för vidare bearbetning av en körningsmotor, till exempel körtidsfiltrering baserad på individuella användarinställningar.

**Lägg till flaggor:** Om du vill flagga innehåll i utdata kan du ange flagga som åtgärd för det önskade attributet i filen. Du kan också använda olika flaggformat med hjälp av listrutan **Flaggformat**, som visas i utdraget nedan.


![](images/ditaval-flag-style.png){width="650" align="left"}


- **Bakgrundsfärg**: Välj nyans, mättnad, kontrast från bakgrundsfärgen. Motsvarande HEX-värde uppdateras automatiskt baserat på ditt val. Du kan också växla färgrymdsformat med listrutan och välja mellan HEX, RGB och HSB.


  ![](images/ditaval-background-color.png){width="350" align="left"}



- **Textfärg**: Välj nyans, mättnad, kontrast från textfärgen. Motsvarande HEX-värde uppdateras automatiskt baserat på ditt val. Du kan också växla färgrymdsformat med listrutan och välja mellan HEX, RGB och HSB.


  ![](images/ditaval-text-color.png){width="350" align="left"}



- **Formateringsalternativ**: Du kan lägga till vissa formateringsalternativ, t.ex. Fet, Kursiv, Understruken, Överstruken och Dubbel understrykning.


  ![](images/ditaval-styling-option.png){width="350" align="left"}



- **Start- och slutflaggor**: Du kan infoga bilder som start- och slutflaggor med knappen **Lägg till flagga** . Om du vill välja bilder kan du antingen använda **Bläddra i Assets** och välja från databasen med stödlinjer eller **Lägg till fil** att överföra från ditt lokala system. Dessutom kan du ange alternativ text för bilderna.


  ![](images/ditaval-start-end-flags.png){width="350" align="left"}



- **Formatkonflikt**: Den löser de konflikter som uppstår när ett enskilt element innehåller flera egenskaper med olika flaggformat. I sådana fall väljs det värde som definieras i formategenskaperna, vilket i praktiken fungerar som standardvärdesväljare för bakgrunds- och textfärger.


  ![](images/ditaval-style-conflict.png){width="650" align="left"}


#### Versionsinformation och Spara som ny version

Versionsinformation och Spara som ny version kombinerar versionshantering och innehållssparande i en enda funktion.
Mer information finns i [Spara som ny version](./web-editor-toolbar.md#version-information-and-save-as-new-version)


#### Lås/lås upp

Låser eller låser upp den aktuella filen. Genom att låsa en fil får du exklusiv skrivåtkomst till filen.
Mer information finns i [Lås upp filen](./web-editor-toolbar.md#lockunlock)


### Spara innehållet

När du är klar med redigeringen av DITAVAL-filen väljer du **Spara** på flikfältet.

>[!NOTE]
>
> Om du stänger filen utan att spara kommer ändringarna att gå förlorade. Om du inte vill spara ändringarna i Adobe Experience Manager-databasen väljer du **Stäng** och sedan **Stäng utan att spara** i dialogrutan **Osparade ändringar**.

## DITAVAL-redigeringsvyer

Adobe Experience Manager Guides DITAVAL-redigerare har stöd för att visa DITAVAL-filer i två olika lägen eller vyer:

**Författare**:   Detta är ett typiskt exempel på vad du ser i vyn What You Get \(WYSISYG\) i DITAVAL-redigeraren. Du kan lägga till eller ta bort egenskaper med det enkla användargränssnittet, som visar egenskaperna, dess värden och åtgärder i listrutan. I redigeringsvyn kan du infoga en enskild egenskap och infoga alla egenskaper med ett enda klick.

Du kan också hitta den version av DITAVAL-filen som du arbetar med genom att hålla pekaren över filnamnet.

**Source**:   I Source-vyn visas den underliggande XML-filen som utgör DITAVAL-filen. Förutom att göra vanliga textredigeringar i den här vyn kan en författare även lägga till eller redigera egenskaper med den smarta katalogen.

Om du vill anropa den smarta katalogen placerar du markören i slutet av en egenskapsdefinition och skriver &quot;&lt;&quot;. Redigeraren visar en lista över alla giltiga XML-element som du kan infoga på den platsen.

![](images/ditaval-source-view-new.png)


## Arbeta med DITAVAL-filer i Assets användargränssnitt

Du kan också skapa en DITAVAL-fil från Assets-gränssnittet. Så här skapar du ett nytt DITAVAL-ämne:

1. I Assets-gränssnittet navigerar du till den plats där du vill skapa DITAVAL-filen.

1. Välj **Skapa** \> **DITA-ämne**.

1. På sidan Design väljer du DITAVAL-filmall och väljer **Nästa**.

1. På sidan Egenskaper anger du **Title** och **Name** för DITAVAL-filen.

   >[!NOTE]
   >
   > Namnet föreslås automatiskt baserat på filens namn. Om du vill ange filnamnet manuellt kontrollerar du att namnet inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med .ditaval.

1. Välj **Skapa**.

   Meddelandet Ämnet har skapats visas.

Du kan välja att öppna DITAVAL-filen för redigering i DITAVAL-redigeraren eller att spara ämnesfilen i Adobe Experience Manager-databasen.

Utför följande steg för att redigera en befintlig DITAVAL-fil:

1. I Assets-gränssnittet navigerar du till den DITAVAL-fil som du vill redigera.

1. Om du vill låsa filen exklusivt markerar du filen och väljer **Checka ut**.

1. Markera filen och välj **Redigera** för att öppna filen i Adobe Experience Manager Guides DITAVAL-redigeraren.



