---
title: Inbyggd PDF | Använda variabler i PDF-utdata
description: Använda variabler i PDF-utdata- och utdatamallarna
source-git-commit: f1fd9c9e3fd3f228feeff469d04221fc3b0ab30f
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variabler i PDF-utdata

En variabel är ett namn/värde-par med data som fungerar som en återanvändbar information. Detta gör ditt innehåll portabelt och enkelt att uppdatera. När du ändrar en variabel eller dess värde uppdateras varje förekomst av variabeln eller värdet.



## Skapa en ny variabel

Så här skapar du en variabel:

![Skapa en ny variabel](assets/add-variable-default.png){width="800" align="left"}

*Skapa variabler och definiera värden för dem.*


1. Gå till webbredigeraren **Utdata** -fliken.
1. Välj **Variabel** <img alt= "variabelikon" src="./assets/variables-icon.svg" width="25"> till vänster.
1. Välj **Redigera** <img alt= "Ikonen Redigera penna" src="./assets/edit_pencil_icon.svg" width="25"> för att öppna **Variabel** redigerare.
Variablerna listas i alfabetisk ordning.
1. Ange variabelnamnet i dialogrutan **Namn** -kolumnen och dess värde i **Värde** kolumn.
   >[!TIP]
   >
   >Du kan använda valfritt HTML-innehåll som ett variabelvärde om du vill visa variabelvärdet i en viss formatering. Du kan till exempel lägga till en `<b>` -taggen till variabelvärdet som ska visa värdet **Stödlinjer för Experience Manager** i fet stil. Du kan också lägga till bilder från databasen som värden.

1. Välj **Lägg till variabel** <img alt= "Ikonen Lägg till" src="./assets/add-icon.svg" width="25"> om du vill lägga till en ny variabel. Du kan inte skapa en variabel med samma namn som en befintlig variabel. Ett fel visas.

   >[!NOTE]
   >
   >Om du inte markerar **Lägg till variabel** <img alt= "Ikonen Lägg till" src="./assets/add-icon.svg" width="25">, skapas och läggs variabeln inte till i listan.

På så sätt kan du skapa variabler med standardvärden. Till exempel:
* ProductName: Experience Manager Guides
* Versionsnummer: 2300
* Releasedatum: 01/01/2023


### Redigera en variabel

Du kan redigera en variabel på två sätt:

**Från variabelpanelen till vänster**

1. Välj en variabel i **Variabel** -panelen.
1. Håll pekaren över variabeln för att visa **Alternativ** väljer du **Redigera** alternativ.
1. I **Redigera variabel** kan du redigera standardvärdet för den valda variabeln.
1. Klicka **Klar**.

**Från Variables-redigeraren**

1. Välj **Variabel** <img alt= "variabelikon" src="./assets/variables-icon.svg" width="25"> till vänster.
1. Välj Redigera **** <img alt= "Ikonen Redigera penna" src="./assets/edit_pencil_icon.svg" width="25">för att öppna variabelredigeraren ****.

1. I variabelredigeraren **kan du redigera värdet för den valda variabeln** .

Du måste spara alla ändringar du gör från variabelredigeraren **för att kunna visa dem i** variabelpanelen **** till vänster.

>[!NOTE]
>
> Om du redigerar ett variabelvärde uppdaterar Adobe Experience Manager Guides samtidigt alla referenser där det är tillämpligt.

### Söka efter och förhandsgranska en variabel

Du kan söka efter och förhandsvisa värdet för en variabel. Ange en sträng i sökrutan i **Variabel** -panelen. Det söker igenom båda baserat på variabelnamnet och dess värde.
Du kan förhandsgranska en variabel på två sätt:

I förhandsvisningen av variabeln visas standardvärdet. Om du till exempel har definierat standardvärdet för produktvariabeln som &quot;Adobe Experience Manager Guides&quot; visas det här värdet i förhandsvisningen.

**Från variabelpanelen till vänster**


1. Välj en variabel i **Variabel** -panelen.
1. Håll pekaren över variabeln för att visa **Alternativ** väljer du **Förhandsgranska** alternativ.

![variabelförhandsgranskning från variabelpanelen](assets/variables-panel-preview-default.png){width="550" align="left"}

*Förhandsgranska standardvärdet för en variabel.*

**Från Variables-redigeraren**

1. Håll pekaren över variabeln i listan för att visa **Alternativ** -menyn.
1. Välj **Förhandsgranska**.




### Duplicera en variabel

Du kan duplicera en variabel och ändra värdet enligt dina krav.


1. Håll muspekaren över variabeln i listan för att visa **menyn Alternativ** .
1. Välj **Duplicera**.

Variabelns standardnamn är `<selected variable name>` (som &quot;exempel&quot;). Du kan ändra namnet enligt dina önskemål.

### Ta bort en variabel

Du kan ta bort en variabel på två sätt:

**Från variabelpanelen till vänster**

1. Välj en variabel i **Variabel** -panelen.
1. Håll pekaren över variabeln för att visa **Alternativ** väljer du **Ta bort** alternativ.

**Från Variables-redigeraren**

1. Håll pekaren över variabeln i listan för att visa **Alternativ** -menyn.
1. Välj **Ta bort** alternativ.

Variabeln tas bort från alla variabeluppsättningar.

## Variabeluppsättningar för förinställningar för utdata

Adobe Experience Manager Guides har även stöd för variabeluppsättningar, vilket gör att du kan tilldela variablerna alternativa värden. Ett företag kan till exempel sälja två produkter, A och B. Det har olika specifikationer för var och en av dem. Dessa specifikationer kan innehålla produktnamn, versionsnummer och utgivningsdatum. Det kan finnas andra skillnader när det gäller varumärken. Med variabeluppsättningar kan du definiera en annan uppsättning värden för dina variabler. När du genererar utdata väljer du lämplig variabeluppsättning och skapar önskade utdata.

### Konfigurera variabeluppsättningar

Du måste konfigurera variabeluppsättningar innan du lägger till några variabler i dem.



1. Välj **Inställningar** <img alt= "Ikonen Inställningar" src="./assets/settings-icon.svg" width="25"> för att öppna **Konfigurera variabeluppsättningar** -dialogrutan.
   ![konfigurera variabeluppsättning](assets/configure-variable-set.png){width="550" align="left"}
1. Ange namnet på variabeluppsättningen i dialogrutan **Namn** kolumn.
1. Välj **Lägg till variabel** <img alt= "Ikonen Lägg till" src="./assets/add-icon.svg" width="25"> om du vill lägga till en ny variabeluppsättning. Variabeluppsättningarna visas i bokstavsordning.
1. Du kan välja **Ta bort** för att ta bort en variabeluppsättning.

### Variabeluppsättningsåtgärder

Alla variabeluppsättningar har samma variabler men kan ha olika värden.

Du kan visa, redigera och förhandsvisa värden för en viss variabeluppsättning. Välj en variabeluppsättning på menyn **Variabeluppsättningar** nedrullningsbar meny. Värdena visas enligt den valda variabeluppsättningen.
När du redigerar värdena för variablerna i specifika variabeluppsättningar åsidosätts standardvärdena och värdena för den valda variabeluppsättningen ändras.
Du kan till exempel ange följande värden för variabeluppsättningarna: *Adobe-set1* och *Adobe-set2* .


**Variabeluppsättning 1**: *Adobe-set1*

* ProductName: ProductA
* Versionsnummer: 2311
* Releasedatum: 2023-11-02


**Variabeluppsättning 2**: *Adobe-set2*

* ProductName: ProductB
* Versionsnummer: 2310
* Releasedatum: 09/07/2023

Varje ny variabel läggs till i alla variabeluppsättningar. När du tar bort eller duplicerar en variabel uppdateras den för alla variabeluppsättningar.

Du kan också förhandsgranska värdena för en variabeluppsättning.
Till exempel för variabeluppsättningen *Adobe-Set1* har du definierat värdet för ProductName-variabeln som &quot;ProductA&quot; och sedan visas värdet i förhandsvisningen i Variabler-redigeraren.

![variabelförhandsgranskning från variabelredigeraren](assets/variables-editor-preview.png){width="550" align="left"}

*Förhandsgranska värdet som du har definierat i den valda variabeluppsättningen.*

### Återställ värdet för en variabel

Om du har redigerat värdet kan du även återställa en variabel till standardvärdet.
Återställ <img alt= "återställningsikon" src="./assets/application-variable-revert.svg" width="25"> visas för en variabel med ett ändrat värde.
Du kan till exempel återställa värdet för variabeln ProductName till standardvärdet Experence Manager Guides.

## Använda variabler i mallarna för inbyggda PDF

Du kan lägga till variabler medan du genererar utdata från dina produktdokument för att göra dem portabla och enkla att uppdatera. Du kan infoga de här variablerna i sidlayouten som visas på de olika sidorna i dina dokument. Du kan till exempel lägga till variabeln ProductName som visas i sidlayoutens sidhuvudsområde (eller andra delar som sidfoten eller brödtexten).



Så här infogar du en variabel som ditt ProductName i sidhuvudsområdet:
1. Öppna önskad sidlayout för redigering.

   >[!NOTE]
   >
   > Visa [Anpassa en sidlayout](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) för att öppna en sidlayout för anpassning eller redigering.

1. Markera rubriken för att aktivera den för att infoga en variabel.

1. Du kan infoga variabeln på två sätt:

   **Från variabelpanelen till vänster**

   * Dra en variabel från **** variabelpanelen och släpp den i rubrikområdet.

   **Från verktygsfältet**

   1. Välj **Infoga variabel/fält** <img alt= "variabelikon" src="./assets/variables-icon.svg" width="25">.
   1. I **Variabel** markerar du namnet på variabeln för att infoga den i sidhuvudsområdet.
   1. Du kan också ange söksträngen i textrutan. Variabelnamnen som innehåller den angivna strängen filtreras och visas i listan. Den markerade variabeln infogas i sidhuvudsområdet. Du kan visa standardvärdet för variabeln.
   1. Om du vill ersätta en variabel dubbelklickar du på variabelvärdet och väljer en annan variabel i **Variabel** -dialogrutan. Variabeln ersätts.


## Generera PDF-utdata med variabler

Du kan generera utdata i PDF med värden från olika variabler. Innan du genererar layouten väljer du en variabeluppsättning bland en förinställd utdatafil **Variabeluppsättning** i den nedrullningsbara listan för att välja dess värden.

![listruta för variabeluppsättning](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Välj en variabeluppsättning i listrutan i den förinställning som du vill använda för att generera PDF-utdata.*

>[!NOTE]
>
> Du kan också välja (Standard) i listrutan för att publicera standardvärdena för alla variabler.

Beroende på vilken variabeluppsättning du väljer får du utdata som motsvarar de variabelvärden som definieras i variabeluppsättningen. Om du till exempel väljer variabeluppsättningen *Adobe-set1* visar utdata variabelns värden enligt definitionen i den här uppsättningen.


<img src="assets/variable-pdf-output.png" alt="utdata från PDF med variabler" width="500" border="2px">

*Generera utdata från PDF med hjälp av variabler i sidlayouten.*

Du kan också snabbt uppdatera värdena för variabeluppsättningar när det behövs och återskapa utdata. Om du till exempel behöver uppdatera informationen för en version kan du uppdatera värdet för versionen i variabeln VersionNumber och generera om utdata.


