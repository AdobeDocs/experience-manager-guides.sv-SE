---
title: Lägga till och hantera citat i ditt innehåll
description: Lägg till och hantera citat i AEM Guides. Lär dig hur du använder, importerar, filtrerar, söker, ändrar format för citat, redigerar, förhandsgranskar, infogar, tar bort och genererar innehållsutdata med citationer.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
feature: Authoring, Features of Web Editor
role: User
source-git-commit: b8f3756e0e8f0338942efb77f00600703be8f6d8
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 0%

---

# Lägga till och hantera citat i ditt innehåll

Citat är referenser till den informationskälla som har lagts till i innehållet. Med citat kan du kreditera författarna till källinformationen och hjälpa läsarna att följa upp källinformationen. Genom att lägga till citat blir innehållet mer tillförlitligt och det förhindrar plagiarism. De gör det även möjligt att visa genomtänkt innehåll.

I Adobe Experience Manager Guides kan du lägga till och importera citat och använda dem i ditt innehåll. Du kan lägga till dessa citat från alla typer av böcker, webbplatser och journaler.


Experience Manager Guides hjälper dig att redigera, förhandsgranska och sortera dina citat. När du har lagt till dina citat i innehållet kan du generera utdata med PDF. Du kan också lägga till litteraturförtecknings- eller referenssidan i PDF-utdata.

Experience Manager Guides har stöd för många olika typer av citationer, som Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) och American Heart Association (AHA). Rekommendationen är att använda dem tydligt och konsekvent.


>[!NOTE]
>
>För närvarande stöder Experience Manager Guides endast PDF för citat.


## Lägg till citat

Så här lägger du till citat:

1. Välj ikonen **Citat** ![Citat](images/citations-icon.svg) i den vänstra panelen.

   Panelen **Källhänvisningar** öppnas.

   ![](images/citation-panel.png){width="350" align="left"}

1. Välj ![Lägg till ikon](images/Add_icon.svg) på panelen **Källhänvisningar**. I listrutan kan du välja att lägga till en ny källhänvisning eller att importera en källhänvisning.

1. Välj **Ny källhänvisning** om du vill lägga till en ny källhänvisning.

   Dialogrutan **Lägg till källhänvisning** öppnas.

   ![anspråkspanelen i webbredigeraren](images/citation-add.png) {width="300" align="left"}


1. Fyll i fälten i dialogrutan **Lägg till källhänvisning**.

   >[!NOTE]
   >
   >Du kan också lägga till ISBN- eller DOI- eller PubMed-ID:t. De andra fälten fylls i automatiskt i av AEM Guides.

   | Bok | Webbplats | Journal |
   | --- | ---|---|
   | **Source** <br> I listrutan väljer du källtexten till citatet som en bok. | **Source**<br> I listrutan väljer du källtexten för citattecknet som en webbplats. | **Source** <br> I listrutan väljer du källan för citatet som Journal. |
   | **Sök på** <br> Välj **ISBN** eller **DOI** i listrutan för att söka efter det elektroniska ID som är länkat till citatet.  <br> DOI: ID för digitalt objekt <br> ISBN: Unik identifierare för numerisk bok | **Sök efter** <br> Välj **DOI** i listrutan om du vill söka efter det elektroniska ID som är länkat till citatet. | **Sök på** <br> Välj **DOI** eller PubMed ID i listrutan för att söka efter det elektroniska ID som är länkat till citatet. <br>  <br> |
   | **Författare** <br> Lägg till för- och efternamnet för författaren av citatet. Välj ![](images/Add_icon.svg) om du vill lägga till fler namn. | **Författare** <br> Lägg till för- och efternamnet för författaren av citatet. Välj ![](images/Add_icon.svg) om du vill lägga till fler namn. | **Författare** <br> Lägg till för- och efternamnet för författaren av citatet. Välj ![](images/Add_icon.svg) om du vill lägga till fler namn. |
   | **Titel** <br> Lägg till bokens titel. | **Titel** <br> Lägg till webbsidans rubrik. | **Titel** <br> Lägg till artikelns titel. |
   | **Redigeraren** <br> Lägg till bokens redigerare. | **Webbplatsnamn** <br> Lägg till webbplatsens namn. | **Journaltitel** <br> Lägg till titeln för det arbete som artikeln finns i. |
   | **Utgåva** <br> Lägg till utgåvan av boken. | **URL** <br> Lägg till webblänken för webbplatsen för att bläddra i innehållet. | **År** <br> Lägg till det år då artikeln publicerades. |
   | **Ort** <br> Lägg till publikationens ort. | **Åtkomstdatum**<br> Lägg till det datum då webbplatsens innehåll öppnas. | **Volym** <br> Lägg till arbetsvolymen i serien. |
   | **Utgivare** <br> Lägg till namnet på utgivaren av boken. | **Publicerat den** <br> Lägg till det datum då webbplatsens innehåll publiceras. | **Number** <br> Lägg till numret på volymen i serien. |
   | **År** <br> Lägg till året som boken publiceras i. | **Uppdaterat den** <br> Lägg till det datum då webbplatsens innehåll uppdateras. | **Sidor** <br> Lägg till det sidnummer eller sidintervall där artikeln finns. |
   | **Version** <br> Lägg till bokens version. | **Unikt ID** <br> Lägg till ett unikt ID för citatet. Ett unikt ID är en unik identifierare för den referensen. | **URL** <br>Lägg till webblänken i journalen. |
   | **Serie** <br>Lägg till bokens serie. |  | **Unikt ID** <br> Lägg till ett unikt ID för citatet. Ett unikt ID är en unik identifierare för den referensen. |
   | **URL** <br> Lägg till webblänken i boken. |
   | **Unikt ID** <br> Lägg till ett unikt ID för citatet. Ett unikt ID är en unik identifierare för den referensen. |

1. Välj **Klar**.

   En ny källhänvisning läggs till i citatteckenpanelen.

>[!NOTE]
>
> Det är obligatoriskt att lägga till ett unikt ID för fältet för källhänvisning.  Du kan inte ändra det unika ID:t när citatet har lagts till.

## Importera citat

Så här importerar du citat:

1. I den vänstra panelen väljer du ikonen **Citat** ![Citat](images/citations-icon.svg).

   Panelen **Källhänvisningar** öppnas.

1. Välj ![Lägg till ikon](images/Add_icon.svg) på panelen **Källhänvisningar** och välj sedan **Importera** i listrutan.
1. Bläddra i en bib-fil från datorn och importera den.

   >[!TIP]
   >
   > Ett .bib-filnamnstillägg är en BibTeX Bibliografisk databasfil. Det är en särskilt formaterad textfil som listar referenser om en viss informationskälla.

   När filen har importerats kan du visa referenserna på citationspanelen.

   >[!NOTE]
   > <ol><li> Experience Manager Guides importerar endast de citat som är unika och inte redan finns.
   > &gt; <li> Experience Manager Guides kan importera citat från en bok, journal eller en webbplats. För närvarande stöder den inte citat från andra källor.

## Hantera citat

Citaten sorteras i bokstavsordning i den vänstra panelen. Sök efter citationerna utifrån de källor som ska användas i ditt ämne.

### Filter

Markera ikonen **Filter** ![](images/filter-search-icon.svg) bredvid sökfältet och välj källalternativen i listrutan för att filtrera citatlistan. Det tillåter både en och flera markeringar.

* **Alla källor**: En fullständig lista med citat, inklusive alla källor, visas.

* **Bok**: Här visas en lista med citat från böcker.

* **Webbplats**: Den visar en lista med citat från webbplatser.

* **Journal**: Den visar en lista över citat som har hämtats från journaler.

### Sök

Sök i källtexten efter ditt innehåll.

1. Välj Citat i den vänstra panelen.
Panelen **Källhänvisningar** öppnas.

1. Använd sökfältet för att söka efter lämpliga citat från en lång lista.

### Ändra format för citattecken {#change-citation-style}

Systemadministratören kan ändra formatet på citat från listrutan **Citat** på fliken **Allmänt** i **Inställningar**.
Dessa format styr hur citat visas i förhandsgranskningsfönstret eller i PDF-utdata.

Följande alternativ är tillgängliga i listrutan:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Kopplingsformat för modernt språk <br> | American Psychological Association Style | Chicago Manual of Style | Institute for Electrical and Electronics Engineers Style | American Heart Association Style |
| Exempel: <br> Crawford, Claire, et al. *Emotional Content of Dark Memories*.Edited by Memory, 16, 2010, Amsterdam. | Exempel: <br> Crawford, C., J., &amp;, C. (2010). *Emotionellt innehåll i mörka minnen* (505-16 st.). 10.1080/ 09658210902067289 | Exempel: <br> Crawford, Claire, et al. *Emotionellt innehåll i mörka minnen*. 505-16, 2010. | Exempel: <br> C. Crawford, J. och C. , *Emotional Content of Dark Memories*. Amsterdam 2010. | Exempel: <br> C. Crawford, J. och C. , *Emotional Content of Dark Memories*. Amsterdam 2010. |


## Redigera en källhänvisning

Så här redigerar du citatet:

1. Håll pekaren över namnet på citatet från listan. Välj ![](images/options.svg) ikonen **Alternativ** .

1. Välj **Redigera**.

Dialogrutan **Redigera källhänvisning** öppnas.

1. Gör de ändringar som krävs. Välj **Klar**.
Den markerade citattecknet redigeras.

>[!NOTE]
>
>Du kan inte ändra det unika ID:t när citatet har lagts till.

## Förhandsgranska ett citat

Så här förhandsgranskar du en källhänvisning:

Håll pekaren över namnet på citatet från listan. Välj     Ikonen ![](images/options.svg) **Alternativ** .

1. Välj **Förhandsgranska**.
Du kan förhandsgranska innehållet i och formatet för citatet i förhandsgranskningsfönstret.

   >[!NOTE]
   >
   >Förhandsgranskningen baseras på den typ av källangivelse som administratören har valt i **Inställningar**.

1. Markera var som helst på skärmen för att stänga förhandsvisningsrutan.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Du kan också förhandsgranska en hänvisning som infogats i ett ämne från Assets-gränssnittet eller på fliken Förhandsgranska i Redigeraren.

## Infoga citat

Följ de här stegen för att infoga citat i ett ämne:
1. Markera ämnet på databaspanelen och dubbelklicka sedan på det för att öppna det i redigeringsfönstret.
1. Placera markören på den plats i ämnet där du vill lägga till citatet.



Du kan infoga citat från huvudverktygsfältet eller den vänstra panelen i avsnittet.

### Från huvudverktygsfältet

1. Välj ikonen **Citat** ![ ](images/citations-icon.svg) i huvudverktygsfältet.
1. Välj citat i dialogrutan **Citat**. Du kan också markera flera citat.
   ![citatdialogruta](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Du kan filtrera citat genom att skriva de första alfabeten på sökpanelen i dialogrutan **Citat** .

1. Välj **Klar**.
Den markerade texten läggs till vid markörens plats i ditt ämne.


### Från den vänstra panelen

>[!NOTE]
> 
>Om du vill visa ikonen **Källhänvisningar** från den vänstra panelen måste systemadministratören aktivera alternativet **Källhänvisningar** på fliken **Paneler** i **Inställningar**.

1. Välj ikonen **Citat** ![ ](images/citations-icon.svg) i den vänstra panelen.
1. Dra citatet från panelen **Citat** och släpp det på lämplig plats i avsnittet.

   Du kan också välja **Infoga** från ![](images/options.svg) **Alternativ** om du vill infoga en hänvisning.

   ![infoga citat](images/citation-panel-insert.png)
1. Om du vill markera flera citat högerklickar du på ett citat i avsnittet och väljer **Ändra citat** på snabbmenyn.
1. Markera de citat du vill infoga i dialogrutan **Citat**.
1. Välj **Klar** om du vill lägga till dem i ämnet.

När du har infogat citat i ämnet kan du förhandsgranska dem i webbredigeraren. Du kan även publicera innehåll med citat med hjälp av PDF.



## Ta bort en källhänvisning

Du kan ta bort citat från panelen Citat eller från ett ämne där du har infogat.

### Ta bort en källhänvisning från panelen Citat

Så här tar du bort en källhänvisning från panelen Citat:

1. Håll pekaren över namnet på citatet från listan.
1. Välj ikonen ![](images/options.svg) **Alternativ** .
1. Välj   **Ta bort** ![](images/Delete_icon.svg).
Bekräftelsedialogrutan öppnas.
1. Välj **Ja**.
Den markerade källtexten tas bort från citationspanelen.



### Ta bort en källhänvisning från ett ämne

Så här tar du bort en hänvisning som redan används i ämnet:

Placera markören i slutet av citattecknet.

1. Högerklicka på en hänvisning i ämnet och välj **Ändra källhänvisning** på snabbmenyn. Dialogrutan Citation öppnas.
   ![snabbmeny för en källhänvisning](./images/modify-citation.png)

1. Du kan välja de citat du vill infoga i dokumentet.

   >[!NOTE]
   >
   >De citat som redan används i ämnet ersätts med de citat som du väljer i dialogrutan.


1. Välj **Klar**.

## Generera utdata av innehåll med citationer

När du har infogat citat i ämnet kan du publicera innehåll med citat med hjälp av PDF.

I utdata från PDF visas citaten i det innehåll där du infogat dem. Du kan också skapa en litteraturförteckningssida. När du väljer en källhänvisning omdirigeras du till litteraturförteckningssidan.

Skapa en sidlayout för **Källhänvisningar** i PDF-mallarna och inkludera den i dokumentet. Alla citat som används i boken listas på en sida som visas i PDF-utdata. Mer information om hur du skapar en sidlayout finns i [Skapa en sidlayout](../native-pdf/components-pdf-template.md#create-page-layout).


Visa [Anpassa PDF-mallar](../native-pdf/pdf-template.md) om du vill ändra vyn och känslan för citatsidan.


### Använda innehållsformat på en källhänvisning

Formatera källtexten när den läggs till i avsnittet.

1. Välj **Formatmallar** på panelen **Mallar** i en inbyggd förinställning för PDF-utdata.   Den öppnar panelen **FORMAT** som innehåller alla formatalternativ.

1. Sök efter `<cite>` på sökpanelen.

Om du vill veta mer om format kan du visa [Arbeta med de vanliga innehållsformaten](../native-pdf/stylesheet.md).
