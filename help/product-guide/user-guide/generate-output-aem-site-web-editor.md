---
title: AEM Sites
description: Skapa och konfigurera AEM Sites-förinställningen i kartkonsolen med hjälp av komponentmappning och äldre komponentmappning.
feature: Publishing
role: User
exl-id: f3657268-9dee-43af-b643-499dbc3ca948
source-git-commit: 358d38ca761661eaee7aeac2cc7d46c53105c543
workflow-type: tm+mt
source-wordcount: '3592'
ht-degree: 0%

---

# AEM Sites-förinställning i kartkonsolen

Du kan skapa förinställningar för AEM Sites från kartkonsolen och konfigurera dem för att generera AEM Sites-utdata. Det finns två sätt att skapa AEM Sites-utdata:

- [Använd sammansatt komponentmappning](#use-composite-component-mapping)
- [Använd äldre komponentmappning](#use-legacy-component-mapping)

>[!TIP]
>
> Vi rekommenderar att du använder den sammansatta komponentmappningen, som finns i Experience Manager Guides 2502, och senare versioner, för att få bättre prestanda.

## Använd sammansatt komponentmappning

Komponentmappningen ger snabbare och skalbar publicering till AEM Sites jämfört med äldre komponentmappning. Den innehåller färdiga redigerbara mallar som kan anpassas efter dina behov med AEM mallredigerare. Mallarna använder en blandning av WCM-kärnkomponenter och specialiserade `guides-components` för att säkerställa att slutanvändarna får bästa möjliga upplevelse på dina AEM Sites-sidor. Du kan också anpassa befintliga mallar med hjälp av metoden för sammansatt komponentmappning.

Experience Manager Guides innehåller fördefinierade mallar för att skapa AEM Sites. De här mallarna hjälper dig att säkerställa en konsekvent innehållslayout och struktur.
- [Skapa hemsidor](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) baserat på dessa fördefinierade mallar.
- Du kan [redigera ämnesmallar](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) och använda format enligt dina önskemål.
- Du kan också [anpassa befintliga AEM Sites-mallar](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).


**Skapa AEM Sites-förinställning**

Så här skapar du AEM Sites-förinställningen med hjälp av sammansatt komponentmappning:

1. [Öppna DITA-mappningsfilen i kartkonsolen](./open-files-map-console.md).
1. Välj ikonen + på panelen **Utdataförinställningar** om du vill skapa en förinställning.
1. Välj **AEM Sites** i listrutan **Typ** i dialogrutan **Ny förinställning**.
1. Avmarkera alternativet **Använd äldre komponentmappning**.
1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning i den aktuella mappprofilen. Mappprofilsikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   Förinställningen för AEM Sites skapas.


   ![Nytt ](images/new-aem-sites-dialog-box.png){width="300" align="left"}

<!-----------------------
### Generate the AEM Sites output using the templates

Once, the preset is created, you can configure the various options available for AEM Sites output generation. Experience Manager Guides allows you to use the out of the box templates or add your own AEM Sites templates.

You can configure the Out-of-the-box Sites template  in two ways:

- In the **Sites** field, select the AEM sites where you want to publish your output.  For example, `AEMG Docs`.

    The **Publish path** and the **Topic page template** options are automatically set in the dropdown.  For example,  `AEMG-Docs-Site/en/docs/product1` and `Topic page` are set respectively. You can also choose the other options from the dropdown.

- Or, Select the **Use Sites path** option to select the complete Sites path, and then select a **Map page template**. 

    You can browse a predefined Sites path or specify a custom path even if the specified path has not been pre-created within the AEM Sites structure. In such cases, the system creates the necessary structure during the publishing process by using the selected map homepage template.

   For example, you can specify the path `/content/AEMG-Docs-Site/en/docs/product4` where the `product4`does not exist in the strcuture. In this case, the system automatically creates `product4` using the selected **Map page template** and publish the output within this newly created page. 
   
   The **Topic page template** is automatically set as `Topic Page`. However, you can choose to select other available options in the dropdown.

--->

### AEM Sites-förinställd konfiguration för sammansatt komponentmappning

>[!NOTE]
>
> Innan du konfigurerar AEM Sites-förinställningen för Experience Manager Guides måste administratören skapa en AEM Sites-struktur med hjälp av mallarna.

- **Lokal programvara**: Läs mer om hur du [hämtar och installerar AEM Sites-mallar](../install-guide/download-install-aem-sites-templates.md) för lokal programvara.
- **Cloud Service**: Läs mer om hur du [hämtar och installerar AEM Sites-mallar](../cs-install-guide/download-install-aem-sites-templates-cs.md) för Cloud Service.

I kartkonsolen ordnas de förinställda konfigurationsalternativen för sammansatt komponentmappning på följande flikar:

- Allmänt
- Innehåll
- Ämneslista
- Korsmappningsreferenser

![Nytt ](images/aem-sites-new-config.png){width="650" align="left"}

**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationsalternativ:

| AEM Sites-alternativ | Beskrivning |
| --- | --- |
| Använd webbplatssökväg | Använd det här alternativet om du vill publicera ditt innehåll på en Experience Manager-webbplats. |
| Platssökväg | **Det här alternativet visas om du väljer alternativet** Använd webbplatssökväg **&#x200B;**. Bläddra i den fördefinierade sökvägen till Experience Manager-webbplatsen eller ange en anpassad sökväg där du vill att utdata ska publiceras. Med alternativet **Använd platser** kan du ange hela publiceringssökvägen även om den angivna sökvägen inte har skapats i förväg i AEM Sites-strukturen. I så fall skapar systemet den nödvändiga strukturen under publiceringsprocessen med hjälp av den valda mallen för kartstartsida.<br><br>Du kan också använda variabler när du anger platssökvägen. Mer information finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](./generate-output-use-variables.md) |
| Mall för mappningssida | **Det här alternativet visas om du väljer alternativet** Använd webbplatssökväg **&#x200B;**. Välj en mall som du vill använda för att mappa hemsidor. |
| Plats | Namnet på den Experience Manager Sites som du vill publicera ditt innehåll på. Alternativen i listrutan fylls i baserat på listan med webbplatser som är tillgängliga i AEM Sites. <br>Välj **Uppdatera** ![referensikon](images/navtitle-refresh-icon.svg) om du vill hämta en ny lista med alternativ och spegla de uppdaterade data. |
| Publiceringssökväg | Den sökväg i AEM-databasen där utdata lagras. Publiceringssökvägen fylls i med alla sökvägar som innehåller sidor som skapats baserat på hemsidmallen. AEM Sites-utdata från DITA-kartan genereras under den här sökvägen.  Om du till exempel anger platsen som `AEMG-Docs` och publiceringssökvägen som `aemg-docs-en/docs/product-abc.`, genereras AEM Sites-utdata under noden `aemg-docs-en/docs/product-abc/` i `crx/de`. |
| Ämnessidmall | Välj den mall som du vill använda för alla utdataämnen. |
| Generera sidnamn baserat på | **Ämnesfilnamn**: Använder DITA-avsnittets filnamn för att skapa URL:en för platsen. <br> **Ämnestitel**: Använder DITA-avsnittets titel för att skapa Experience Manager-webbplatsnamnen. |
| Rensa tidigare genererade sidor | - **Ta bort tidigare genererade sidor för ämne som tagits bort från kartan**: Om strukturen för DTIA-kartan ändras kan du använda det här alternativet för att ta bort tidigare genererade sidor för de borttagna ämnena. Den här funktionen är endast tillgänglig för fullständig kartpublicering.<br><br>Säg att du har publicerat en DITA-karta som innehåller avsnitten a.dita, b.dita och c.dita. Innan du publicerade kartan igen tog du bort b.dita-ämnet från kartan. Om du har valt det här alternativet tas nu allt innehåll som är relaterat till b.dita bort från AEM Sites-utdata och bara a.dita och c.dita publiceras.<br><br>**Obs!**: Information om borttagna sidor hämtas också i loggarna för utdatagenerering. Mer information om åtkomst till loggfilerna finns i [Visa och kontrollera loggfilen](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Varning**: När du tar bort ämnen blir sidorna otillgängliga från den publicerade webbplatsen. Innan ämnena tas bort visas en varning. Du måste bekräfta att du vill ta bort dem.<br><br>- **Ta bort alla sidor som skapats av andra källor på den här sökvägen**: Om du väljer det här alternativet tas alla sidor som publicerats på den här sökvägen bort från andra kartor, enskilda ämnen eller andra källor. Sidorna blir också otillgängliga från den publicerade webbplatsen. Innan ämnena tas bort visas en varning. Du måste bekräfta att du vill ta bort dem. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |

**Innehåll**

Fliken **Innehåll** innehåller följande konfigurationsalternativ:

| AEM Sites-alternativ | Beskrivning |
| --- | --- |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Villkorlig filtrering | Välj ett av följande alternativ:<br><br>**Inget**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>**Använder DITAVAL**: Välj DITAVal-filer för att generera villkorat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du väljer någon annan filtyp.<br>**Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Ytterligare DITA-OT-kommandoradsargument | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om vilka kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/). |
| Metadata <br> <br>Filegenskaper (Assets) | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>**Obs!** Metadataegenskaperna är skiftlägeskänsliga.<br><br>*Om du har valt en baslinje baseras värdena för egenskaperna på versionen av den valda baslinjen.<br>* Om du inte har valt en baslinje baseras värdena för egenskaperna på den senaste versionen.<br><br>Du kan också skicka metadata till utdata med DITA-OT-publicering. Om du vill ha mer information kan du [skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Obs!**: Om du inte har definierat `cq:tags` i alternativet Egenskaper hämtas värdena för `cq:tags` från den aktuella arbetskopian, även om du har valt en baslinje för publicering. |
| Metadata <br> <br>Använd mappningsegenskaper som reserv | Om du väljer det här alternativet kopieras även de egenskaper som definierats för kartfilen till de avsnitt där sådana egenskaper inte har definierats. Tänk på följande när du använder det här alternativet:<br><br>*Endast egenskaperna String, Date eller Long (en och flera värden) kan skickas till AEM Site-sidorna.<br>* Metadatavärdena för en String-typegenskap stöder inte några specialtecken (till exempel `@, #, " "`).<br>* Det här alternativet bör användas tillsammans med alternativet `Properties`. |

**Ämneslista**

Fliken **Ämneslista** visar en lista med ämnen som finns i den aktuella arbetskopian av DITA-kartan. Som standard inkluderas alla ämnen. Du kan välja ut specifika ämnen och generera utdata från AEM Sites endast för dem. Du har till exempel uppdaterat vissa avsnitt så att du bara kan publicera dessa ämnen i stället för att publicera hela DITA-kartan.

![Ämneslista för objektwebbplatser](images/aem-presets-topic-list.png) {align="left"}


>[!NOTE]
>
> När du har valt en baslinje på fliken **Innehåll** visas ämnen och deras versioner från den kopplade baslinjen i ämneslistan. Dessutom bör den inkrementella publiceringen från ämneslistan endast användas när kartans struktur inte ändras. Om mappningsstrukturen/innehållsförteckningen ändras ska hela kartan publiceras en gång för att uppdatera innehållsförteckningen.

**Korskartmappsreferenser**

Den här listan innehåller ämnen som innehåller korsmappsreferenser med `scope ="peer"`. Du kan ange publiceringskontext för en lista över korsmappsreferenser med `scope="peer"` till ämnen som är tillgängliga i andra DITA-kartor. Den här fliken visas om du använder Experience Manager Guides-versionen (UUID).

Mer information finns i avsnittet [Arbeta med länkade ämnen](#working-with-linked-topics) nedan.

När du har konfigurerat inställningarna sparar du ändringarna i förinställningen och väljer **Generera** för att generera AEM Sites för motsvarande karta.

>[!NOTE]
>
> Om du publicerar innehåll på AEM webbplatser för första gången bör du publicera sidorna på webbplatsnivå. Detta garanterar att utdata visas korrekt på instansen **Publish** utan några CSS-avbrott.

## Använd äldre komponentmappning

Stegen för att skapa AEM Sites-förinställningen med äldre komponentmappning är desamma som beskrivs i avsnittet [Sammansatt komponentmappning](#use-composite-component-mapping) ovan. När du skapar förinställningen måste du dock markera alternativet **Använd äldre komponentmappning** i dialogrutan **Ny förinställning** .

![](images/aem-sites-output-legacy.png) {width="300" align="left"}

I kartkonsolen ordnas de förinställda konfigurationsalternativen för äldre komponentmappning på följande flikar:

- Allmänt
- Innehåll
- Korsmappningsreferenser

![Nytt ](images/aem-sites-preset-legacy-config.png){width="500" align="left"}

**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationsalternativ:

| AEM Sites-alternativ | Beskrivning |
| --- | --- |
| Platsnamn | Ett platsnamn där utdata lagras i din AEM-databas.<br><br>En nod i AEM-databasen skapas med det namn som anges här. Om du inte anger platsnamnet skapas platsnoden med DITA-mappningsfilens namn.<br><br>Webbplatsnamnet som du anger här används också som rubrik på fliken Webbläsare.<br><br>Du kan också använda variabler när du anger platsnamn. Mer information finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](./generate-output-use-variables.md) |
| Utdatasökväg | Den sökväg i AEM-databasen där utdata lagras. När du genererar det slutliga resultatet kombineras platsnamnet och utdatasökvägen. Om du till exempel anger platsnamnet som `user-guide` och utdatasökvägen som `/content/output/aem-guides`, genereras slutresultatet under noden `/content/output/aem-guides/user-guide`.<br><br>Du kan också använda variabler när du anger utdatasökvägen. Mer information finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](./generate-output-use-variables.md) |
| Befintliga utdatasidor | Markera alternativet **Skriv över innehåll** om du vill skriva över innehåll på befintliga sidor. Det här alternativet skriver bara över innehåll som finns under sidans innehåll och head-noder. Det här alternativet möjliggör blandad publicering av innehåll. Om du väljer det här alternativet kan du välja att ta bort överblivna sidor från publicerade utdata. Det här är också *standardalternativet* för att skapa AEM Sites-utdata.<br><br>Markera alternativet **Ta bort och skapa** om du vill framtvinga borttagning av befintliga sidor under publiceringen. Med det här alternativet tas sidnoden bort tillsammans med innehållet och alla underordnade sidor under den. Använd det här alternativet om du har ändrat designmallen för förinställningen för utdata eller om du vill att eventuella extra sidor som redan finns i målet ska tas bort. |
| Ta bort tidigare genererade sidor för ämnen som tagits bort från kartan | Om DTIA-schemats struktur ändras kan du använda det här alternativet för att ta bort tidigare genererade sidor för de borttagna avsnitten. Den här funktionen är endast tillgänglig för fullständig kartpublicering.<br><br>Säg att du har publicerat en DITA-karta som innehåller avsnitten a.dita, b.dita och c.dita. Innan du publicerade kartan igen tog du bort b.dita-ämnet från kartan. Om du har valt det här alternativet tas nu allt innehåll som är relaterat till b.dita bort från AEM Sites-utdata och bara a.dita och c.dita publiceras.<br><br>**Obs!**: Information om borttagna sidor hämtas också i loggarna för utdatagenerering. Mer information om åtkomst till loggfilerna finns i [Visa och kontrollera loggfilen](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Varning**: När du tar bort ämnen blir sidorna otillgängliga från den publicerade webbplatsen. Innan ämnena tas bort visas en varning. Du måste bekräfta att du vill ta bort dem. |
| Design | Välj den designmall som du vill använda för att generera utdata.<br><br>Kontakta publiceringsadministratören om du vill ha mer information om hur du använder anpassade designmallar för att generera utdata. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.svg) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |

**Innehåll**

![Nytt ](images/aem-sites-content-tab.png){width="650" align="left"}

Fliken **Innehåll** innehåller följande konfigurationsalternativ:

| AEM Sites-alternativ | Beskrivning |
| --- | --- |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](./web-editor-baseline.md) om du vill ha mer information. |
| Villkorlig filtrering | Välj ett av följande alternativ:<br><br>**Inget**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>**Använder DITAVAL**: Välj DITAVal-filer för att generera villkorat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du väljer någon annan filtyp.<br>**Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Metadata <br> <br>Filegenskaper (Assets) | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>**Obs!** Metadataegenskaperna är skiftlägeskänsliga.<br><br>*Om du har valt en baslinje baseras värdena för egenskaperna på versionen av den valda baslinjen.<br>* Om du inte har valt en baslinje baseras värdena för egenskaperna på den senaste versionen.<br><br>Du kan också skicka metadata till utdata med DITA-OT-publicering. Om du vill ha mer information kan du [skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Obs!**: Om du inte har definierat `cq:tags` i alternativet Egenskaper hämtas värdena för `cq:tags` från den aktuella arbetskopian, även om du har valt en baslinje för publicering. |
| Metadata <br> <br>Använd mappningsegenskaper som reserv | Om du väljer det här alternativet kopieras även de egenskaper som definierats för kartfilen till de avsnitt där sådana egenskaper inte har definierats. Tänk på följande när du använder det här alternativet:<br><br>*Endast egenskaperna String, Date eller Long (en och flera värden) kan skickas till AEM Site-sidorna.<br>* Metadatavärdena för en String-typegenskap stöder inte några specialtecken (till exempel `@, #, " "`).<br>* Det här alternativet bör användas tillsammans med alternativet `Properties`. |

**Korskartmappsreferenser**

Den här listan innehåller ämnen som innehåller korsmappsreferenser med `scope ="peer"`. Du kan ange publiceringskontext för en lista över korsmappsreferenser med `scope="peer"` till ämnen som är tillgängliga i andra DITA-kartor. Den här fliken visas om du använder Experience Manager Guides-versionen (UUID).

Mer information finns i avsnittet [Arbeta med länkade ämnen](#working-with-linked-topics) nedan.

## Arbeta med länkade ämnen

Med Experience Manager Guides kan du skapa ämnesreferenser med `peer @scope`. Du kan sedan definiera publiceringskontexten för dessa referenser från AEM Sites-förinställningar och slutligen generera utdata för de länkade avsnitten.

Mer information finns i [Generera utdata för att länka ämnen från andra kartor](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).


Gör så här för att ange publiceringskontext för korslänkade filer:

1. Öppna fliken **Korsmappningsreferenser**. Se till att `<xrefs>` har unika ID:n om du vill visa den här fliken. Unika ID:n för `<xrefs>` genereras automatiskt när det äldre innehållet redigeras/sparas om ID:t inte finns där.

   Du kommer inte att kunna visa länken för tvärschemat i följande fall:
   - För de förinställningar som skapades före version 4.6 inaktiveras fliken Korsreferenser och ett verktygstips, **Se kartpanelen**, visas.
   - För förinställningar som skapats från kartkontrollpanelen visas verktygstipset **Se Kartkontrollpanelen**.
   - För OTB-förinställningar visas verktygstipset **Se Map dashboard**.
   - För globala förinställningar skapar du en lokal kopia av den här globala förinställningen för att ange korsmappningsreferenser.


1. En lista med ämnen och deras referenser visas

   >[!NOTE]
   >
   >Fliken **Korskartmappsreferenser** visar ämnen som endast är länkade med `scope="peer"`. För länkar med `scope="local"` behöver du inte ange publiceringskontext.

   Alla länkade ämnen har den senaste förinställningen och kartan för utdata markerat som standard. Publiceringskontexten för alla länkade ämnen är inställd på `<Most recently generated>`-karta som standard.

   ![Korskartmappsreferenser](images/aem-sites-preset-cross-map-references.png)

1. Om du vill använda de senast publicerade utdata för varje beroende fil på kartan väljer du **Använd den senast genererade** publiceringskontexten för alla beroende ämnen.
Du bör publicera kartan som valts som överordnad karta innan du publicerar kartan som innehåller länkade ämnen. Om kartan med länkade ämnen inte publiceras visas länkarna som normal text i stället för hyperlänkar i AEM Sites-utdata.
Du bör välja samma typ av förinställning för AEM Sites för det länkade ämnet. Om den aktuella AEM Sites-förinställningen till exempel använder äldre komponentmappning väljer du en liknande AEM Sites-förinställning för det länkade avsnittet.
1. I listrutan Överordnad karta markerar du den kartfil vars utdata du vill länka den aktuella kartan till.
Om du väljer en kartfil visas kartans UUID i kolumnen Överordnad karta. De förinställningar för utdata som är associerade med den valda kartan visas i listan Förinställningar för överordnad karta. Ämne 1 i karta A innehåller till exempel en referens till ämne 2. Ämne 2 kan finnas på en eller flera kartor. Du kan välja den överordnade kartan och en viss förinställning eller de senast publicerade utdata för varje länk.

1. Om samma ämne refereras till mer än en gång i en fil kan du lägga till olika publiceringskontexter för varje instans. Detta ger större flexibilitet och kontroll över innehållet. Ämne 3 finns t.ex. i både karta B och karta C. Ämne 1 innehåller två referenser till avsnitt 3. Du kan välja Map B som överordnad karta för den första länken och Map C som överordnad för den andra länken.

1. I listrutan Förinställning för överordnad karta väljer du den förinställning som du vill länka den aktuella kartans utdata med.
   >[!NOTE]
   >
   > De olika AEM Sites-förinställningarna för den aktuella kartan visas i listrutan. Om du inte väljer en förinställning visas en varningsikon och utdatagenereringen misslyckas.

1. Välj önskad karta och dess förinställning för alla källämnen och välj **Generera**.




**Överordnat ämne:** [Förstå förinställningarna för utdata](generate-output-understand-presets.md)