---
title: Konfigurera inställningar för utdatagenerering
description: Lär dig hur du konfigurerar inställningar för generering av utdata
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3314'
ht-degree: 0%

---

# Konfigurera inställningar för utdatagenerering {#id181AI0B0E30}

AEM Guides har många konfigurationsalternativ som du kan använda för att anpassa processen för generering av utdata. I det här avsnittet beskrivs alla konfigurationer och anpassningar som kan hjälpa dig att skapa utdata.

## Konfigurera fliken Baslinje på kontrollpanelen för DITA-kartor {#id223MD0D0YRM}

Följande flikar innehåller anvisningar om hur du döljer fliken Baslinje på DITA-kartkontrollpanelen baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera baslinjefliken på kartkontrollpanelen.

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `hide.tabs.baseline` | Boolean\(`true/false`\).**Standardvärde**: `true` |

>[!NOTE]
>
> Den här konfigurationen är aktiverad som standard och fliken Baslinje är inte tillgänglig på kartkontrollpanelen.

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Välj alternativet **Dölj fliken Baslinje**.

1. Klicka på **Spara**.

>[!NOTE]
>
> Den här konfigurationen är inaktiverad som standard och fliken Baslinje är tillgänglig på kartkontrollpanelen.

>[!ENDTABS]


## Konfigurera blandad publicering på en befintlig AEM-webbplats {#id1691I0V0MGR}

Om du har en AEM-webbplats som innehåller DITA-innehåll kan du konfigurera dina AEM Site-utdata så att DITA-innehåll publiceras på en fördefinierad plats på webbplatsen. I följande skärmbild på en AEM Site-sida är noden `ditacontent` reserverad för lagring av DITA-innehåll:

![](assets/publish-in-aem-site.png)

De återstående noderna på sidan redigeras direkt i AEM Site Editor. Om du konfigurerar publiceringsinställningen för att publicera DITA-innehåll på en fördefinierad plats, säkerställs att inget av ditt befintliga icke-DITA-innehåll ändras i AEM Guides publiceringsprocess.

Du måste göra följande konfigurationer på din befintliga webbplats för att tillåta publicering av DITA-innehåll till en fördefinierad nod:

- Konfigurera platsens mallegenskaper

- Lägg till noder på webbplatsen för att publicera DITA-innehåll


Följande flikar innehåller anvisningar om hur du konfigurerar mallegenskaper för din befintliga webbplats baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd Package Manager för att hämta /libs/fmdita/config/templates/default-filen.

   >[!NOTE]
   >
   > Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i noden `libs`. Du måste skapa en övertäckning av noden `libs` i noden `apps` och endast uppdatera de filer som krävs i noden `apps`.

1. Lägg till följande egenskaper:

   | Egenskapsnamn | Typ | Värde |
   |-------------|----|-----|
   | `topicContentNode` | Sträng | Ange det nodnamn där du vill publicera DITA-innehållet. Standardnoden där AEM Guides publicerar DITA-innehåll är: <br> `jcr:content/contentnode` |
   | `topicHeadNode` | Sträng | Ange det nodnamn där du vill lagra metadatainformationen för DITA-innehållet. Standardnoden där AEM Guides lagrar metadatainformation är till exempel: <br> `jcr:content/headnode` |


Nästa gång du publicerar DITA-innehåll med mallkonfigurationer för din webbplats publiceras innehållet i de noder som anges i egenskaperna `topicContentNode` och `topicHeadNode`.

>[!TAB Lokal]

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till platsens mallkonfigurationsnod. AEM Guides lagrar till exempel standardmallkonfigurationerna i följande nod:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i noden `libs`. Du måste skapa en övertäckning av noden `libs` i noden `apps` och endast uppdatera de filer som krävs i noden `apps`.

1. Lägg till följande egenskaper:

   | Egenskapsnamn | Typ | Värde |
   |-------------|----|-----|
   | `topicContentNode` | Sträng | Ange det nodnamn där du vill publicera DITA-innehållet. Standardnoden där AEM Guides publicerar DITA-innehåll är: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | Sträng | Ange det nodnamn där du vill lagra metadatainformationen för DITA-innehållet. Standardnoden där AEM Guides lagrar metadatainformation är till exempel: <br>`jcr:content/headnode` |


På följande skärmbild visas de egenskaper som lagts till i standardmallnoden i AEM Guides:

![](assets/add-content-node.png){width="800" align="left"}

Nästa gång du publicerar DITA-innehåll med mallkonfigurationer för din webbplats publiceras innehållet i de noder som anges i egenskaperna `topicContentNode` och `topicHeadNode`.

För befintliga webbplatser måste du dock lägga till noderna `topicContentNode` och `topicHeadNode` manuellt.

Utför följande steg för att lägga till de nödvändiga noderna på din befintliga plats:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Leta reda på `jcr:content` i platsnoden.

1. Lägg till `topicContentNode`- och `topicHeadNode`-noder med samma namn som du angav i platsens mallkonfigurationer.

>[!ENDTABS]

## Konfigurera basutdataplats för publicering

Följande flikar innehåller anvisningar om hur du konfigurerar basutdataplatsen baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md) för att skapa konfigurationsfilen.

1. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera basutdataplatsen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Standardvärde:** &quot;/content/dam/fmdita-outputs&quot; |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och välj paketet *com.adobe.fmdita.config.ConfigManager*.

1. Uppdatera egenskapen **Base Output Location** för att ange standardsökvägen i AEM-databasen där PDF ska sparas efter publicering. Om en ogiltig sökväg anges återgår den automatiskt till standardsökvägen: `/content/dam/fmdita-outputs`.

1. Klicka på **Spara**.

>[!ENDTABS]

## Använda metadata i publicering via DITA-OT {#id191LF0U0TY4}

AEM Guides erbjuder ett sätt att skicka anpassade metadata när utdata publiceras med DITA-OT. Som administratör och utgivare måste du utföra följande uppgifter för att konfigurera och använda anpassade metadata i publicerade utdata:

- Som administratör lägger du till nödvändiga metadata i systemet så att de blir tillgängliga på sidan Egenskaper på DITA-kartan.

- Som administratör lägger du till anpassade metadata i metadatalistan så att den visas i DITA-kartkonsolen.

- Som utgivare konfigurerar och lägger du till anpassade metadata med DITA-kartan och skapar önskade utdata.


Så här lägger du till de metadata som krävs i systemet:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Assets** i listan över verktyg.

1. Klicka på panelen **Metadatascheman**.

   Forms-sidan Metadata Schema visas.

1. Välj **standardformuläret** i listan.

   >[!NOTE]
   >
   > Egenskaperna som visas på egenskapssidan för en DITA-karta hämtas från det här formuläret.

1. Klicka på **Redigera**.

1. Lägg till anpassade metadata som du vill använda i publicerade utdata. Vi lägger till exempel till målgruppsmetadata med följande steg:

   1. Dra och släpp komponenten **Enkelradig text** på formuläret från komponentlistan **Skapa formulär** .

   2. Markera det nya fältet för att öppna fältets **inställningar**.

   3. I **fältetikett** anger du metadatanamnet - målgrupp.

   4. I inställningen **Mappa till egenskap** anger du ./jcr:content/metadata/&lt;namn på metadata\>. Vi kommer till exempel att ställa in den på ./jcr:content/metadata/publik.

   Lägg till alla metadataparametrar som krävs med dessa steg.

1. Klicka på **Spara**.


Den nya parametern visas nu på sidan Egenskaper för alla DITA-kartor.

![](assets/properties-page-custom-metadata.PNG)

Därefter måste du göra anpassade metadata tillgängliga i DITA-kartkonsolen. Följande flikar innehåller anvisningar om hur du gör anpassade metadata tillgängliga på DITA-kartans dashboard baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd pakethanteraren för att komma åt metadatalistfilen som finns på följande plats i din Cloud Manager Git-databas:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Filen metadataList innehåller en lista med egenskaper som visas i listrutan **Egenskaper** för en DITA-karta på kartkontrollpanelen. Som standard visas fyra egenskaper i den här filen - docstate, dc:language, dc:description och dc:title.

1. Lägg till anpassade metadata som du har lagt till på Forms-sidan Metadata Schema. Lägg till exempel till målgruppsparameter i slutet av standardlistan.

>[!TAB Lokal]

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Gå till filen metadataList som finns på följande plats:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Filen metadataList innehåller en lista med egenskaper som visas i listrutan **Egenskaper** för en DITA-karta på kartkontrollpanelen. Som standard visas fyra egenskaper i den här filen - docstate, dc:language, dc:description och dc:title.

1. Lägg till anpassade metadata som du har lagt till på Forms-sidan Metadata Schema. Lägg till exempel till målgruppsparameter i slutet av standardlistan.

1. Klicka på **Spara alla**.

>[!ENDTABS]

Nu visas anpassade metadata i DITA-kartkonsolens **Egenskaper**-listruta.

Som utgivare måste du slutligen inkludera anpassade metadata i publicerade utdata. Så här bearbetar du anpassade metadata när du genererar utdata:

1. Navigera till den DITA-karta som du vill publicera i Assets-gränssnittet.

1. Markera DITA-schemafilen och öppna egenskapssidan.

1. Ange värdet för anpassade metadata på sidan Egenskaper. Vi har till exempel angett värdet External som målgruppsparameter.

   ![](assets/properties-page-custom-metadata-value.png)

1. Klicka på **Spara och stäng**.

1. Klicka på DITA-kartfilen för att öppna DITA-kartkonsolen.

1. Välj den förinställning du vill använda för att generera utdata på fliken **Utdatainställningar**.

1. Klicka på **Redigera**.

1. I listrutan **Egenskaper** väljer du de egenskaper som du vill skicka vidare till publiceringsprocessen.

   ![](assets/props-in-publish-output.PNG)


De valda egenskaperna/metadata skickas vidare till publiceringsprocessen och blir tillgängliga i det slutliga resultatet.

### Validera metadata som skickas till DITA-OT för bearbetning (endast för Cloud Service)

För att validera de metadatavärden som skickas till DITA-OT kan man använda en molnklar burk. Eftersom vi inte har åtkomst till det lokala filsystemet i molnet kan vi bara validera metadatafilen via molnklar behållare.

- Filnamn: metadata.xml
- Filplats: crx-quickstart/profiles/ditamaps/&lt;ditamap-1234\>

  Så här kommer du åt metadata.xml:

   - Logga in på serverplatsen där AEM-instansen körs.
   - Migrera till crx-quickstart/profiles/ditamaps/&lt;recently-directory-name\>/metadata.xml.
- Exempelfilformat:

  **metadata.xml**

  ```XML
  <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  <root>
     <Path id="/absolutePath/sampleMap.ditamap">
        <metadata>
           <meta isArray="false" key="dc:description">This is a file</meta>
           <meta isArray="false" key="dc:title">Myfile</meta>
           <meta isArray="true" key="multivalueText">One;Two;Three</meta>
        </metadata>
     </Path>
     <Path id="/absolutePath/sampleTopic.dita">
        <metadata>
           <meta isArray="false" key="dc:description">description for the accountability</meta>
           <meta isArray="false" key="dc:title">accountability title</meta>
           <meta isArray="true" key="multivalueText">value1</meta>
        </metadata>
     </Path>
  </root>
  ```


- isArray: Ett booleskt attribut som definierar om metadata är ett \(Array\) med flera värden eller inte. Värdena avgränsas av ett semikolon.
- Sökvägs-ID: Absolut sökväg till filen som lagras under den tillfälliga katalogen.

>[!NOTE]
>
> Om det inte finns några metadata för filen visas inte &lt;meta\>-taggen med nyckeln som egenskap för filen i filen metadata.xml.

## Konfigurera kommandoradsargumentfältet DITA-OT så att det accepterar metadata för rotmappning (endast för Cloud Service)

Så här använder du kommandoradsargumentfältet DITA-OT för att skicka metadata för rotmappning:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera kommandoradsargumentfältet DITA-OT i förinställningen:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `pass.metadata.args.cmd.line` | Boolean\(`true/false`\).**Standardvärde**: `true` |

- Om du anger egenskapsvärdet till **true** aktiveras kommandoradsfunktionen DITA-OT, vilket gör att du kan skicka metadata via DITA-OT-kommandoraden.
- Om egenskapsvärdet anges till **false** inaktiveras kommandoradsfunktionen DITA-OT. Du kan sedan använda egenskapsfältet i förinställningen för att skicka metadata.

## Anpassa DITA-kartkonsolen {#id188HC08M0CZ}

AEM Guides ger dig flexibiliteten att utöka funktionerna i DITA-kartkonsolen. Om du t.ex. har en uppsättning rapporter som skiljer sig från vad som finns i AEM Guides kan du lägga till sådana rapporter i kartkonsolen. Om du vill anpassa kartkonsolen måste du skapa ett AEM-klientbibliotek \(eller ClientLib\) som innehåller koden för att kunna utföra de funktioner du behöver.

>[!NOTE]
>
> Direktändringar av sidkomponenter rekommenderas inte eftersom de skrivs över i nya versioner av produkten.

AEM Guides tillhandahåller kategorin `apps.fmdita.dashboard-extn` för att anpassa kartkonsolen. När kartkonsolen läses in körs och läses de funktioner som skapas under kategorin `apps.fmdita.dashboard-extn` in.

>[!NOTE]
>
> Mer information om hur du skapar AEM-klientbibliotek finns i [Använda klientbibliotek](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=en).

## Hantera bildåtergivning under generering av utdata {#id177BF0G0VY4}

AEM innehåller en uppsättning standardarbetsflöden och mediehandtag för att bearbeta resurser. I AEM finns det fördefinierade arbetsflöden för att hantera resurshantering för de vanligaste MIME-typerna. För varje bild som du överför skapas vanligtvis flera återgivningar av samma bild i binärt format i AEM. Dessa återgivningar kan ha olika storlek, med olika upplösning, med vattenstämpel eller någon annan förändrad egenskap. Mer information om hur AEM hanterar resurser finns i [Bearbeta Assets med mediehanterare och arbetsflöden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=en) i dokumentationen för AEM.

Med AEM Guides kan du konfigurera vilken bildåtergivning som ska användas när utdata genereras för dina dokument. Du kan till exempel välja mellan en av standardbildåtergivningarna eller skapa en och använda samma för att publicera dina dokument. Mappning av bildåtergivning för publicering av dina dokument lagras i filen `/libs/fmdita/config/ **renditionmap.xml**`. Ett fragment av filen `renditionmap.xml` är följande:

>[!NOTE]
>
> Vi rekommenderar att du skapar en kopia av filen `renditionmap.xml` i mappen `apps` för alla anpassningar.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="HTML5" outputName="ditahtml5">cq5dam.thumbnail.319.319.png</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

Elementet `mimetype` anger filformatets MIME-typ. Elementet `rendition output` anger vilken typ av utdataformat och namnet på återgivningen \(till exempel `cq5dam.web.1280.1280.jpeg`\) som ska användas för att publicera den angivna utdatafilen. Du kan ange bildåtergivningarna som ska användas för alla utdataformat som stöds - AEMSITE, PDF, HTML5, EPUB och CUSTOM.

Om du vill ange olika bildåtergivningar för en förinställning kan du använda attributet `outputName`, med dess värde inställt på förinställningens titel, för att definiera anpassade återgivningar för specifika förinställningar under samma utdatatyp. Detta är användbart när du behöver olika bildstorlekar eller format för olika publiceringsscenarier.

Till exempel:


```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="HTML5" outputName="ditahtml5">cq5dam.thumbnail.319.319.png</rendition>
      
   </mapelement>
...
</renditionmap>
```

När attributet `outputName` är inställt på `ditahtml5`(förinställningstitel) används miniatyrbilden `ditahtml5` i de ovanstående återgivningarna. `cq5dam.thumbnail.319.319.png` Om attributet `outputName` inte anges används den större bilden `cq5dam.web.1280.1280.jpeg` för alla utdata i HTML5.

Om den angivna återgivningen inte finns söker AEM Guides först efter webbåtergivningen av den angivna bilden. Om inte ens webbåtergivningen hittas används den ursprungliga återgivningen av bilden.

>[!NOTE]
>
> Dessa bildåtergivningar styr endast utdatagenereringen. En bilds webbåtergivning används när du öppnar ett dokument för förhandsgranskning.

## Konfigurera automatisk tömningsperiod för utdathistorik {#id19AAI070V8Q}

När du genererar utdata skapas utdata tillsammans med utdataloggarna. För stora DITA-kartor kan dessa loggar ta mycket plats i din databas. Som standard lagras loggarna på följande plats i databasen:

`/var/dxml/metadata/outputHistory`

Under en tidsperiod kan den sammanlagda storleken på alla loggfiler uppgå till GB. I AEM Guides kan du konfigurera en tidsperiod för att behålla dessa loggfiler i databasen. Efter den angivna tidsperioden tas loggarna och historiken för utdatagenerering bort från databasen.

>[!NOTE]
>
> Historiken för generering av utdata är loggposten i listan Genererade utdata på fliken Utdata.

Om du konfigurerar historikrensningsfunktionen påverkas utdatagenereringen för alla DITA-kartor i databasen. På fliken Utdata i en DITA-karta rensas historiken efter det angivna antalet dagar och vid den tidpunkt som anges i inställningen.

>[!NOTE]
>
> Borttagning av loggfiler och historik för generering av utdata påverkar inte de genererade utdata.

På följande flikar finns instruktioner om hur du ställer in en dag och en tidpunkt för tömning av utdatahistorik och -loggar baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att ange en dag och en tid för att rensa utdatahistorik och -loggar:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager\|output.history.purgeperiod` | Ange efter hur många dagar som utdatahistoriken och utdataloggarna ska rensas. Om du vill inaktivera den här funktionen anger du egenskapen till 0.Daglig vid den angivna tidpunkten när rensningsprocessen körs på utdata som genererats före det antal dagar som anges i den här egenskapen. | **Standardvärde**: 5 |
| `output.history.purgetime` | Ange den tid då rensningsprocessen initieras. | **Standardvärde**: 0:00 \(eller 12:00 midnatt\) |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. I egenskapen **Rensningsperiod för utdatahistorik** anger du efter hur många dagar som utdatahistoriken och utdataloggarna rensas. Som standard är den inställd på 5 dagar. Om du vill inaktivera den här funktionen anger du egenskapen till 0.

1. I egenskapen **Tömningstid för utdatahistorik** anger du den tid då rensningsprocessen initieras. Som standard är den inställd på 0:00 \(eller 12:00 midnatt\). Rensningsprocessen körs dagligen vid den här tidpunkten på utdata som genereras före det antal dagar som anges i egenskapen **Rensningsperiod för utdatahistorik**.

   >[!NOTE]
   >
   > Som standard utförs rensningsfunktionen varje midnatt på utdata som är äldre än 5 dagar.

1. Klicka på **Spara**.

>[!ENDTABS]

## Ändra gränsen för den nyligen genererade utdatalistan {#id1679JH0H0O2}

Du kan ändra det maximala antalet genererade utdata som visas på fliken Utdata för en DITA-karta.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att ändra antalet utdata som ska visas i listan:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.historylimit` | Heltalsvärde.<br> **Standardvärde**: 25 |

>[!TAB Lokal]

Som standard visas en lista med de senaste 25 genererade utdatafilerna. Om du vill ändra antalet utdata som ska visas i listan uppdaterar du inställningen **Utdatalistegräns** i paketet `com.adobe.fmdita.config.ConfigManager`.

>[!ENDTABS]

>[!TIP]
>
> Mer information om hur du arbetar med utdatahistorik finns i avsnittet *Utdatahistorik* i guiden [Bästa tillvägagångssätt](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-mar-22/Adobe-Experience-Manager-Guides_Best-Practices_EN.pdf).

## Prestandaoptimering för utdatagenerering (endast för lokal) {#id176LB050VUI}

Med AEM Guides kan du konfigurera poolstorleken för utdatagenereringsprocesser som styr antalet processer för utdatagenerering som körs samtidigt. Som standard är processpoolens storlek inställd på antalet processorkärnor som är tillgängliga i systemet plus ett. Du kan ändra värdet till 1 om du vill ha sekventiell publicering. I det här fallet körs den första publiceringsaktiviteten och nästa publiceringsåtgärd lagras i publiceringskön.

Om du vill ändra storleken på bearbetningspoolen för utdatagenerering uppdaterar du inställningen **Genereringspoolstorlek** i paketet `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl`.

## Konfigurera FrameMaker Publishing Server (endast för lokal installation) {#id1678G0Z0TN6}

Du kan använda FrameMaker Publishing Server \(FMPS\) för att generera utdata för DITA-innehåll. Om du konfigurerar FMPS kan du generera utdata i flera format som stöds av FMPS.

>[!NOTE]
>
> Om du vill generera utdata med FMPS måste du ha FMPS-servern konfigurerad. Installations- och konfigurationsinformation finns i FrameMaker Publishing Server användarhandbok.

Om du vill konfigurera AEM Guides att använda FMPS uppdaterar du följande egenskaper för paketet `com.adobe.fmdita.config.ConfigManager` i webbkonsolen.

>[!NOTE]
>
> Gå till http://&lt;servernamn\>:&lt;port\>/system/console/configMgr URL för att öppna webbkonsolen.

| Egenskap | Beskrivning |
|--------|-----------|
| FrameMaker Publishing Server inloggningsdomän | Ange domännamnet eller arbetsgruppsnamnet där FrameMaker Publishing Server finns. Ange domännamnet :- baserat på FMPS-versionen   **FMPS 2020**: IP-adress som 192.168.1.101 <br>- **FMPS 2019 och tidigare**: IP-adress eller domännamn |
| FRAMEMAKER PUBLISHING SERVER URL | Ange URL:en för FrameMaker Publishing Server. Baserat på FMPS-versionen anger du FMPS-URL:en som:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 och tidigare**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| FMPS-version | Ange versionsnumret för FrameMaker Publishing Server. Baserat på FMPS-versionen anger du versionsinformationen som: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 och tidigare**: 2019 eller 2017 |
| FrameMaker Publishing Server användarnamn och lösenord | Ange användarnamn och lösenord för att komma åt FrameMaker Publishing Server. |
| FMPS-timeout | \(*Valfritt*\) Ange tiden \(i sekunder\) som AEM Guides väntar på ett svar från FrameMaker Publishing Server. Om inget svar tas emot under den angivna tiden avbryts publiceringsaktiviteten och aktiviteten flaggas som misslyckad. <br> Standardvärde: 300 sekunder \(5 minuter\) |
| Extern AEM-URL | *\(Valfritt\)* Den AEM-URL där FrameMaker Publishing Server ska placera de genererade utdatafilerna. Exempel: `http://<server-name>:<port>/`. |
| Användarnamn och lösenord för AEM Admin | *\(Valfritt\)* Användarnamnet och lösenordet för en administratör för din AEM-konfiguration. Detta används av FrameMaker Publishing Server för att kommunicera med AEM. |
| Timeout för väntan på körning av FMPS-aktivitet | Den här inställningen gäller endast för FMPS 2020. Ange tiden \(i sekunder\) efter vilken FMPS slutar vänta på att den här processen ska köras. |


