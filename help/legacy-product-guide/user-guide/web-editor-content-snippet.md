---
title: Infoga ett innehållssfragment från datakällan
description: Använd data från datakällan i AEM Guides. Lär dig hur du infogar ett innehållsavdrag från datakällan. Skapa ett ämne med ämnesgeneratorn.
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '2389'
ht-degree: 0%

---

# Använd data från datakällan

En **datakälla** är ett system där du lagrar och hanterar data för din organisation. Det här är databassystem som JIRA, SQL-databaser, PIM eller PLM. AEM Guides tillhandahåller en funktion för att ansluta till din datakälla och använda data från den.

Du kan också ansluta till JSON-datafiler med hjälp av en filkoppling. Ladda upp JSON-filen från datorn eller bläddra i den från Adobe Experience Manager resurser. Skapa sedan innehållsutdrag eller ämnen med generatorerna.

## Panelen Datakällor

Välj **Datakällor** ![datakälla](images/data-source-icon.svg) i den vänstra panelen för att visa de anslutna datakällorna. Panelen Datakällor öppnas och visar alla anslutna datakällor.

Beroende på din konfiguration kan administratören konfigurera en datakällanslutning:

<details>
<summary> Cloud Service </summary>


- Om du använder versionen från oktober 2023 eller senare, ska du lära dig hur du [konfigurerar en datakällanslutning från användargränssnittet](/help/product-guide/cs-install-guide/conf-data-source-connector-tools.md) i Cloud Servicens installations- och konfigureringshandbok.

- Om du använder versionen från juli 2023 eller september 2023 ska du lära dig hur du [konfigurerar en datakällanslutning](/help/product-guide/cs-install-guide/conf-data-source-connector.md) i Cloud Servicens installations- och konfigureringshandbok.

</details>

<details>    
<summary>  Lokal programvara </summary>

- Om du använder version 4.3.1 eller senare ska du lära dig hur du [konfigurerar en datakällanslutning från användargränssnittet](/help/product-guide/cs-install-guide/conf-data-source-connector-tools.md) i installations- och konfigureringshandboken på plats.

- Om du använder version 4.3 ska du lära dig hur du [konfigurerar en datakällanslutning](/help/product-guide/cs-install-guide/conf-data-source-connector.md) i installations- och konfigureringshandboken på plats.
</details>


>[!NOTE]
>
> Du ser de datakällor som administratören har konfigurerat anslutningen för.


## Visa listvy eller rutvy

Du kan växla mellan listvyn och rutvyn om du vill visa de olika datakällorna i form av en lista eller som rutor.

Välj en datakälla om du vill visa generatorerna för innehållsavdrag och ämnesgeneratorerna som är tillgängliga för den valda datakällan.

### Listvy ![](images/data-sources-list-view-icon.svg)

![](images/data-sources-list-view.png){width="300" align="left"}

*Lista över anslutna datakällor.*

### Panelvy   ![](images/data-sources-tile-view-icon.svg)

![](images/data-sources-tile-view.png){width="300" align="left"}

*Visa de anslutna datakällorna som rutor.*

Du kan använda data från datakällor på två sätt:
- Infoga ett innehållsavdrag
- Skapa ett ämne



## Infoga ett innehållssfragment från datakällan

AEM Guides har en funktion för att ansluta till din datakälla. Du kan hämta dina data, infoga dem i dina ämnen och redigera dem. Du kan enkelt skapa ett innehållsavdrag med generatorn för innehållsavdrag och återanvända det i dina ämnen.

Utför följande steg för att skapa ett innehållskfragment med hjälp av generatorn för innehållsfragment och infoga det i ditt avsnitt:

1. Välj **Datakällor** ![](images/data-source-icon.svg)   i den vänstra panelen för att visa de anslutna datakällorna.

1. Välj en datakälla om du vill visa de innehållsfragmentgeneratorer som är tillgängliga för den valda datakällan.

   ![](images/code-snippet-generator.png){width="300" align="left"}

   *På panelen Datakällor visas tillgängliga generatorer för innehållsfragment.*

1. Välj **Lägg till** om du vill lägga till en ny generator för innehållsfragment. Panelen **Lägg till generator för innehållsfragment** öppnas.

1. Ange frågan i textrutan **Datafråga**.  Välj **Kopiera exempelfråga** om du snabbt vill kopiera en datafråga. I stället för att skapa frågan manuellt kan du kopiera och klistra in exempelfrågan i textrutan **Datafråga**. Redigera sedan frågan efter datakraven.

   >[!NOTE]
   >
   >Experience Manager tillhandahåller olika exempelfrågor för alla resurser i de olika datakällorna. Dessa mappas till datakällan som du hämtar data från.

1. Om du använder en filkoppling kan du överföra JSON-filen från datorn eller bläddra i en JSON-fil från Adobe Experience Manager-resurser.

   >[!NOTE]
   >
   > Om du använder en filkoppling visas alternativen för att överföra eller bläddra bland filer istället för en datafråga.

1. Välj den mall som mappar med datakällan i listrutan **Datamappningsmall**.
De färdiga mallarna för den valda datakällan visas i listrutan. Du kan till exempel visa mallen &quot;sql-table&quot; för datakällan med namnet &quot;PostgreSQL&quot;-datakälla.

   >[!NOTE]
   >  
   > Om administratören har konfigurerat anpassade mallar visas även dessa mallar i listrutan (baserat på mallsökvägskonfigurationerna som din administratör har konfigurerat).
   >   
   >Du kan också använda snabbhetsverktygen i mallarna. Läs mer om hur du [använder snabbverktyg](#use-velocity-tools).

1. Listrutan **Resurs** visas för vissa anslutningar som REST Client, Salsify, Akeneo och Microsoft ADO.  Välj en resurs i listrutan och anslut till den för att skapa ett innehållskuvert eller ett ämne som använder generatorn för det.

   >[!NOTE]
   >
   > Administratören kan konfigurera standardresurser eller lägga till resurser för flera URL:er när datakällanslutningarna konfigureras.

1. Klicka på **Hämta** för att hämta data från datakällan och tillämpa mallen på data som är resultat av SQL-frågan.

1. Du kan visa data i förhandsgranskningen eller i DITA-källvyn.

   1. I förhandsgranskningen visas hur data visas när de infogas i innehållet. I förhandsvisningen visas en liten del av data i den valda mallens format.
Till exempel:
      - Om du har valt en SQL-tabellmall kan du visa SQL-data i tabellformat.
      - Om du har valt mallen Jira-ordered-list kan du visa en ordnad lista för Jira-problemen.

   1. I källvyn visas data i DITA-källvyn.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
      *Lägg till en generator för innehållsfragment. Visa data i käll- eller förhandsgranskningsläge.*

1. Om du vill spara resultatet av frågan anger du namnet på generatorn och klickar sedan på **ADD**.   En ny generator för innehållsfragment läggs till i listan.

   >[!NOTE]
   >
   > Du måste följa namnkonventionen för den nya innehållsgeneratorns namn. Du kan inte ha ett mellanslag i namnet på generatorn för innehållsfragment. Du kan inte heller spara en ny innehållsgenerator med namnet på en befintlig innehållsgenerator. Ett fel inträffar.

### Alternativ för generering av innehållsfragment

Högerklicka på en generator för innehållsfragment för att öppna Alternativ. Med alternativen kan du utföra följande åtgärder:

- **Förhandsgranska**: Använd det här alternativet om du vill öppna en ruta och visa en liten del av hur data visas i utdata.
- **Infoga**: Använd det här alternativet om du vill infoga det markerade innehållsfragmentet i det ämne som öppnats för redigering i webbredigeraren. När data infogas som utdrag kan du även redigera data i ämnet i Web Editor.

  >[!NOTE]
  > 
  > Alternativet Infoga visas bara när du redigerar ett ämne.

- **Redigera**: Använd det här alternativet om du vill göra ändringar i generatorn för innehållsfragment och spara den.
- **Ta bort**: Använd det här alternativet om du vill ta bort den markerade generatorn för innehållsfragment.
- **Duplicera**: Använd det här alternativet om du vill skapa en dubblett eller en kopia av den markerade generatorn för innehållsfragment. Dupliceringen skapas med ett suffix (som generator_1) som standard.

### Infoga ett frågesfragment

Du kan också använda **Infoga frågesfragment** ![](images/data-source-icon.svg)   i huvudverktygsfältet för att infoga datagreppet i avsnitten.  Du kan välja en generator i listrutan, redigera frågan eller ändra mallen och infoga data i avsnittet.

![](images/insert-content-snippet.png){width="800" align="left"}

*Redigera och infoga ett datafragment.*

## Skapa ett ämne med ämnesgeneratorn

Med en ämnesgenerator kan du skapa ämnen som innehåller data från dina källor. Du kan snabbt skapa en ämnesgenerator och sedan generera ämnen med generatorn. Varje avsnitt kan innehålla data i olika format, som tabeller, listor och stycken.   I ett avsnitt kan du till exempel lägga till en tabell som innehåller information om alla nya produkter och en lista över alla produkter som ska upphöra att säljas.

Ämnesgeneratorn kan skapa ämnen som innehåller data och en DITA-karta för alla ämnen. Du kan även `<conref>` dessa ämnen i ditt innehåll. Detta gör att du kan synkronisera data med datakällan och enkelt uppdatera dem.





### Skapa ett ämne

Så här skapar du ett ämne med ämnesgeneratorn:

1. Välj en datakälla om du vill visa generatorerna för innehållsavdrag och ämnesgeneratorerna som är tillgängliga för den valda datakällan.

   ![](images/data-sources.png){width="300" align="left"}

   *Lägg till en ämnesgenerator för en ansluten datakälla.*

1. Välj **Lägg till** ![](images/Add_icon.svg) och välj **Ämnesgenerator** i listrutan för att lägga till en ny ämnesgenerator. Panelen **Lägg till ämnesgenerator** öppnas.



1. Ange värdena i fälten under följande tre flikar på panelen **Lägg till ämnesgenerator**:

   **Hämta konfiguration**

   ![](images/topic-generator-fetch-configuration.png){width="300" align="left"}

   *Lägg till datafrågan, datamappningsmallen och rotnodinformationen för ämnesgeneratorn och ge den ett unikt namn på panelen Hämta konfiguration.*

   1. Ange frågan i textrutan **Datafråga**. Välj **Kopiera exempelfråga** om du snabbt vill kopiera en datafråga. I stället för att skapa frågan manuellt kan du kopiera och klistra in exempelfrågan i textrutan **Datafråga**. Redigera sedan frågan efter datakraven.

      >[!NOTE]
      >
      >Experience Manager tillhandahåller olika exempelfrågor för alla resurser i de olika datakällorna. Dessa mappas till datakällan som du hämtar data från.

   1. Om du använder en filkoppling kan du överföra JSON-filen från datorn eller bläddra i en JSON-fil från Adobe Experience Manager-resurser.

      >[!NOTE]
      >
      > Om du använder en filkoppling visas alternativen för att överföra eller bläddra bland filer istället för en datafråga.

   1. Välj den mall som mappar med datakällan i listrutan **Datamappningsmall**.

      >[!NOTE]
      >
      > Om administratören har konfigurerat anpassade mallar visas även dessa mallar i listrutan (baserat på mallsökvägskonfigurationerna som din administratör har konfigurerat). Du kan till exempel skapa en ämnesmall som innehåller en ordnad lista, tabeller, stycken eller andra DITA-element.

   1. Ange **rotnoden**. Det här är noden där du vill komma åt dina data. Ämnesgeneratorn skapar sedan varje ämne på den nivå som definieras i rotnoden. Du kan till exempel lägga till&quot;issues&quot; som rotnod i Jira. Om en fråga returnerar 13 utgåvor får du alltså 13 ämnen, ett avsnitt för varje utgåva.

   1. Klicka på **Hämta** för att hämta data från datakällan och tillämpa mallen på data som är resultat av SQL-frågan. Förhandsgranskningen visar en liten del av hur ämnet visas i den valda mallens format. Du kan till exempel visa ett enstaka Jira-problem med alla fält som är ett resultat av frågan.
   1. Ange namnet på ämnesgeneratorn.

      >[!NOTE]
      > 
      > Du måste följa namnkonventionen för den nya ämnesgeneratorn. Du kan inte ha ett mellanslag i ämnesgeneratorns namn. Du kan inte heller spara en ny ämnesgenerator med namnet på en befintlig ämnesgenerator. Ett fel inträffar.

   **Utdatakonfiguration**

   ![](images/topic-generator-output-configuration.png){width="300" align="left"}

   *Ange utdatasökväg och information om ämnesnamngivningskonvention på panelen Utdatakonfiguration. Skapa en DITA-karta och ge den ett namn.*

   1. Ange den **utdatasökväg**-information där du vill spara dina ämnen.
   1. I **ämnesnamnkonventionen** kan du ange ett värde eller en variabel med hastighetstaggar. De nya ämnena kommer att följa konventionen. Du kan till exempel ange `$key` för att skapa avsnitt baserat på Jira-nycklar.
   1. Aktivera alternativet **Generera en karta** om du vill skapa en karta som innehåller alla genererade ämnen.
   1. Ange namnet på den nya DITA-kartan.

   >[!NOTE]
   >
   > Ämnesgeneratorn genererar DITA-kartan på samma utdatasökväg som avsnitten.

   **Metadata**

   Välj metadataegenskaperna i listrutan för att skicka till avsnitten. I listrutan **Namn** visas både de anpassade egenskaperna och standardegenskaperna.

   I följande skärmbild är till exempel `dc:description`, `dc:language`, `dc:title` och `docstate` standardegenskaper som du kan definiera värdena för. Du kan skapa en anpassad egenskap som författare och definiera dess värde.

   ![](images/topic-generator-metadata.png){width="300" align="left"}

   *Lägg till metadataegenskaperna på panelen Metadata för att skicka till ämnena.*

1. Ange generatorns namn och klicka på **Spara** för att spara frågeresultaten. En ny ämnesgenerator läggs till i listan.

1. Klicka på **Spara och generera** för att spara ämnesgeneratorn och generera nya ämnen från ämnesgeneratorn.



   ![](images/edit-topic-generator.png){width="650" align="left"}

   *Generera nya ämnen från en befintlig ämnesgenerator.*

   >[!NOTE]
   >
   > Om ämnena redan finns uppdaterar generatorn data i de befintliga avsnitten.

### Alternativ för ämnesgenerator

Högerklicka på en ämnesgenerator för att öppna **Alternativ**. Med alternativen kan du utföra följande åtgärder:

- **Generera**: Det här alternativet genererar ämnen för den valda ämnesgeneratorn. Du kan också använda det här alternativet för att uppdatera befintliga ämnen. Den ansluter till datakällan och hämtar uppdaterade data. När du genererar innehållet är det här alternativet inaktiverat och du kan visa en inläsare.
  >[!NOTE]
  >
  >Om ämnet redan finns kan du antingen skriva över informationen i ämnet eller spara den som en ny version.

  ![](images/generate-topic-options.png)

  *Generera ett ämne och om filen redan finns sparar du den som en ny version eller skriver över den.*
- **Visa logg**: Välj det här alternativet om du vill visa loggfilen för innehållsgenerering. Loggfilen öppnas på en ny flik. Du kan visa fel, varningar, informationsmeddelanden och undantag i loggfilen. Det här alternativet aktiveras om du har genererat innehållet för den valda ämnesgeneratorn.

- **Förhandsgranska**: Använd det här alternativet om du vill öppna en ruta och visa en liten del av hur data visas i utdata.



- **Redigera**: Använd det här alternativet om du vill ändra och spara ämnesgeneratorn. Det här alternativet är inaktiverat när du genererar innehållet.
- **Ta bort**: Använd det här alternativet om du vill ta bort den valda ämnesgeneratorn. Det här alternativet är inaktiverat när du genererar innehållet.
- **Duplicera**: Det här alternativet skapar en dubblett eller en kopia av den valda ämnesgeneratorn. Dupliceringen skapas med ett suffix (till exempel `topic-sample_1`) som standard.



## Använd snabbhetsverktygen i datakällmallarna {#use-velocity-tools}

Experience Manager-mallar har också stöd för snabbhetsverktygen (version 2.0). Med de här verktygen kan du använda olika funktioner för data som du hämtar från datakällorna. Läs mer om hur du använder [snabbverktygen](https://velocity.apache.org/tools/2.0/generic.html) och de funktioner du kan använda.

Utför följande steg om du vill använda ett snabbverktyg i en mall:
1. Redigera en snabbmeddelandemall i webbredigeraren.
1. Lägg till ett verktyg och dess funktion i formatet `<tool.function>`. Till exempel:
   - Använd `$mathTool.random` om du vill generera ett slumpmässigt tal med matematiska verktyg.
   - Använd `$mathTool.add(num1, num2)` om du vill generera summan av tal med matematiska verktyg.
1. Använd mallen för att skapa ett innehållskuvert eller ämne.
1. När du har tillämpat mallen på data kan du visa data i förhandsvisningen eller i DITA-källvyn.




Du kan använda följande verktyg i hastighetsmallarna för att tillämpa olika funktioner på data som du hämtar från kopplingen:
-`$alternatorTool`
- `$classTool`
- `$contextTool`
- `$conversionTool`
- `$dateTool`
- `$comparisonDateTool`
- `$displayTool`
- `$escapeTool`
- `$fieldTool`
- `$loopTool`
- `$linkTool`
- `$listTool`
- `$mathTool`
- `$numberTool`
- `$renderTool`
- `$resourceTool`
- `$sortTool`
