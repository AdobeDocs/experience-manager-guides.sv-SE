---
title: AEM
description: Skapa och konfigurera AEM webbplatsförinställning i AEM Guides. Använd AEM webbplatsstöd för att generera artikelbaserade utdata, skapa länkade ämnen för utdata, publicera conref och söka efter en sträng i innehållet.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: b82f1f3b42f85cce8420d3962c69cd3bafc5728d
workflow-type: tm+mt
source-wordcount: '2621'
ht-degree: 0%

---

# AEM {#id205BE3008SW}

Följande alternativ är tillgängliga för AEM platsutdata:

Du kan skapa AEM platsförinställning på två sätt:

**Öppna DITA-mappningsfilen i Kartvyn i webbredigeraren:** Öppna DITA-mappningsfilen på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan AEM Plats i typlistrutan i dialogrutan Lägg till förinställning. I webbredigeraren har konfigurationerna ordnats under flikarna Allmänt och Avancerat:

**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationer:

- Platsnamn
- Utdatasökväg
- Befintliga utdatasidor
- Ta bort enstaka webbplatssidor
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Post Generation Workflow

**Avancerat**

Fliken Avancerat innehåller följande konfigurationer:

- Hämta temporära filer
- Generera separat PDF för varje ämne
- Använd kartegenskaper som standard

Mer information finns i [AEM Platskonfiguration](#id231KIM004X1).

**Från kartkontrollpanelen**

Om du vill öppna förinställningar för AEM webbplats klickar du på en DITA-kartfil i Assets användargränssnitt, sedan på Utdatainställningar och sedan på AEM för webbplatsens utdata. Klicka på **Redigera** överst på kartpanelen för att uppdatera de olika konfigurationerna och klicka sedan på **Spara**.

>[!TIP]
>
> Avsnittet *AEM Webbplatspublicering* i guiden om bästa praxis innehåller information om hur du skapar AEM webbplatsutdata.

## Konfiguration av AEM {#id_aem_site_config}

Följande alternativ är tillgängliga för AEM platsutdata:

| Alternativ för AEM | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera responsiva AEM platsutdata väljer du alternativet AEM plats. |
| Inställningsnamn | Ange ett beskrivande namn för de AEM platsinställningar som du skapar. Du kan till exempel ange *interna kunders utdata* eller *slutanvändares utdata*. |
| Platsnamn | Ett platsnamn där utdata lagras i AEM.<br><br>En nod i AEM skapas med det namn som anges här. Om du inte anger platsnamnet skapas platsnoden med DITA-mappningsfilens namn.<br><br>Webbplatsnamnet som du anger här används också som rubrik på fliken Webbläsare.<br><br>Du kan också använda variabler när du anger platsnamn. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Design | Välj den designmall som du vill använda för att generera utdata.<br><br>Kontakta publiceringsadministratören om du vill ha mer information om hur du använder anpassade designmallar för att generera utdata. |
| Målsökväg | Den sökväg i AEM där utdata lagras. När du genererar det slutliga resultatet kombineras platsnamnet och målsökvägen. Om du till exempel anger platsnamnet som `user-guide` och målsökvägen som `/content/output/aem-guides`, genereras slutresultatet under noden `/content/output/aem-guides/user-guide`.<br><br>Du kan också använda variabler när du anger målsökvägen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Använd villkor med | Välj ett av följande alternativ:<br><br>**Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>**DITAVal-fil**: Välj DITAVal-filer om du vill generera villkorat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du väljer någon annan filtyp.<br>**Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om villkorsförinställningar finns i [Använda villkorsförinställningar](generate-output-use-condition-presets.md#id1825FL004PN). |
| Befintliga utdatasidor | Markera alternativet **Skriv över innehåll** om du vill skriva över innehåll på befintliga sidor. Det här alternativet skriver bara över innehåll som finns under sidans innehåll och head-noder. Det här alternativet möjliggör blandad publicering av innehåll. Om du väljer det här alternativet kan du välja att ta bort överblivna sidor från publicerade utdata. Det här är också *standardalternativet* för att skapa AEM webbplatsutdata.<br><br>Markera alternativet **Ta bort och skapa** om du vill framtvinga borttagning av befintliga sidor under publiceringen. Med det här alternativet tas sidnoden bort tillsammans med innehållet och alla underordnade sidor under den. Använd det här alternativet om du har ändrat designmallen för förinställningen för utdata eller om du vill att eventuella extra sidor som redan finns i målet ska tas bort. |
| Ta bort enstaka webbplatssidor | Om du väljer inställningen **Skriv över innehåll** i inställningen **Befintliga utdatasidor** visas det här alternativet. Om du väljer det här alternativet tas alla sidor som är överblivna bort från den publicerade AEM. För att den här funktionen ska fungera måste du publicera hela DITA-kartan och inte använda den inkrementella publiceringen.<br><br>Säg att du har publicerat en DITA-karta som innehåller avsnitten a.dita, b.dita och c.dita. Innan du publicerade kartan igen tog du bort b.dita-ämnet från kartan. Om du har valt det här alternativet tas nu allt innehåll som är relaterat till b.dita bort från AEM och bara a.dita och c.dita publiceras.<br><br>Den här funktionen tar inte bort någon publicerad underordnad karta. Om den överordnade kartan till exempel innehåller en underordnad karta och du tar bort hela den underordnade kartan tas inte innehållet bort från den publicerade utdata. Om du däremot tar bort ett ämne från en underordnad karta och publicerar om, tas innehållet i det borttagna ämnet bort från webbplatsens utdata.<br><br>Om det finns något refererat innehåll, och det innehållet tas bort innan det publiceras igen, tas det refererade innehållets data inte bort.<br><br>**Obs!**: Information om borttagna överblivna sidor hämtas också i loggarna för utdatagenerering. Mer information om åtkomst till loggfilerna finns i [Visa och kontrollera loggfilen](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Hämta temporära filer | Välj det här alternativet om du vill hämta temporära filer som genererats av DITA-OT. Platsen där tillfälliga filer lagras i DITA-OT finns i loggen för generering av utdata. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.png) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om du väljer filegenskaper och sedan hämtar de temporära filerna, får du även filen *metadata.xml* i ZIP-mappen. |
| Generera separata PDF för varje ämne | Om du väljer det här alternativet skapas även ett PDF för varje avsnitt på DITA-kartan. När du väljer det här alternativet visas ett nytt alternativ för Delad PDF-bana.<br><br>I fältet Delad PDF-sökväg anger du sökvägen för att lagra PDF som genereras för varje ämne.<br><br>**Obs!** AEM Guides använder DITA-OT-plugin-programmet pdfx för att generera PDF för varje ämne. Denna plugin medföljer DITA-OT-paketet som levereras i kartong. Du kan anpassa det här plugin-programmet för att skapa PDF efter dina behov. Om du använder en anpassad DITA-OT-plugin måste du integrera pdfx-pluginen för att kunna skapa PDF på ämnesnivå. |
| Kör Post Generation Workflow | När du väljer det här alternativet visas en ny listruta för Post Generation Workflow som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>**Viktigt**: När du genererar inkrementella utdata för den AEM platsen skapas utdata med den aktuella versionen av filerna och inte med den kopplade baslinjen.<br><br>Mer information finns i [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF). |
| Filegenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>**Obs!** Metadataegenskaperna är skiftlägeskänsliga.<br><br>*Om du har valt en baslinje baseras värdena för egenskaperna på versionen av den valda baslinjen.<br>* Om du inte har valt en baslinje baseras värdena för egenskaperna på den senaste versionen.<br><br>Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Obs!**: Om du inte har definierat `cq:tags` i alternativet Egenskaper hämtas värdena för `cq:tags` från den aktuella arbetskopian, även om du har valt en baslinje för publicering. |
| Använd kartegenskaper om de saknas i ämne | Om du väljer det här alternativet kopieras även de egenskaper som definierats för kartfilen till de avsnitt där sådana egenskaper inte har definierats. Tänk på följande punkter när du använder det här alternativet:<br><br>*Endast egenskaperna String, Date eller Long (en och flera värden) kan skickas till webbplatsens AEM.<br>* Metadatavärdena för en String-typegenskap stöder inte några specialtecken (till exempel `@, #, " "`).<br>* Det här alternativet bör användas tillsammans med alternativet `Properties`. |

## Ytterligare information om AEM

### Generera artikelbaserade utdata från Web Editor

Du kan generera AEM för ett eller flera ämnen eller hela DITA-kartan från Web Editor. Du måste skapa förinställningar för DITA-kartan och sedan enkelt generera AEM för din karta. Om du har uppdaterat några avsnitt på kartan kan du även generera AEM webbplatsutdata endast för dessa ämnen från Web Editor. Mer information finns i [Artikelbaserad publicering från webbredigeraren](web-editor-article-publishing.md#id218CK0U019I).

### Generera utdata som länkar ämnen från andra kartor

Det är ett mycket vanligt scenario att ha en stor uppsättning dokumentation spridda över flera mappar och DITA-kartor. Det blir extremt komplext att publicera innehåll som är länkat från olika platser. Som standard skapas alla länkar `<xref>` med `local` `@scope`. Publicering av sådana ämnen innebär inga utmaningar eftersom den använder direktlänk till ämnet. Om ämnet ligger utanför den aktuella DITA-kartan visas inte det länkade innehållet i länken.

Ett annat sätt att länka innehåll är att skapa en länk med `peer` `@scope`. För sådant innehåll löses länken vid körning genom att filens namn och det konfigurerade sammanhanget för det länkade ämnet väljs från DITA-kartans publiceringskontext. På följande skärmbild visas egenskapspanelen för en länk med `peer` `@scope`:

![](images/peer-link-scope-link.png){width="800" align="left"}

För att förenkla publiceringen av komplexa kartor och ämnen som länkar till andra ämnen i andra kartor kan du med AEM Guides ange publiceringskontext för varje utdatapresentation.

I publiceringssammanhanget kan du ange vilket ämne som ska användas för att publicera ett visst utdataavsnitt. Låt oss förstå detta med hjälp av ett exempel - låt oss säga att du har fyra mappar: exempel a, exempel b, exempel c och exempel d. Varje mapp innehåller en DITA-karta - DITA-karta A, DITA-karta B, DITA-karta C och DITA-karta D. Koppling mellan kartor sker när ett ämne i DITA-karta A länkar till ett ämne på DITA-kartan B, C eller D. I skärmbilden nedan innehåller exempelavsnittet länkar \(eller referenser\) till filer som ingår i andra DITA-kartor.

![](images/sample-concept-link-to-other.png){width="350" align="left"}

När du nu konfigurerar publiceringsinställningarna för AEM webbplats för den kartfil som innehåller det här avsnittet kan du välja vilken publiceringskontext för det länkade innehållet som ska användas vid publiceringen. En publiceringskontext är en kombination av DITA-kartan och dess förinställning för utdata. Utdataförinställningen innehåller i sin tur en specifik version av innehållet och villkorliga förinställningar. Hela den här kombinationen av DITA-kartan, förinställningen för utdata, versionen \(filer\) och villkoren definierar publiceringskontexten för en länkad karta.

Gör så här för att ange publiceringskontext för korslänkade filer:

1. Öppna fliken **Utdatainställningar** i den DITA-karta som du vill publicera.

1. Välj **AEM**-utdatainställningen.

   Du kan hämta AEM förinställningar och Publish-kontextflikar.

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Öppna fliken **Publish Context**.

   Du visas en lista med beroende ämnen. Det här är ämnen som är länkade från något ämne i den aktuella kartan, men de är tillgängliga i vissa andra DITA-kartor.

   >[!NOTE]
   >
   > På fliken Publish Context visas ämnen som bara är länkade med `peer` `@scope`. För länkar med `local` `@scope` behöver du inte ange publiceringskontext.

   Som standard är alla länkade ämnen markerade med sin senaste förinställning och karta för utdata.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Klicka på **Redigera** \(i huvudverktygsfältet\) om du vill ändra standardvalet för DITA-karta och förinställning.

1. Om du vill använda de senast publicerade utdata för varje beroende fil på kartan väljer du **Använd den senast genererade publiceringskontexten för alla beroende ämnen**.

1. I listrutan **Överordnad karta** markerar du den kartfil vars utdata du vill länka den aktuella kartans utdata.

   När du väljer en kartfil visas kartans UUID i kolumnen Överordnad karta. De förinställningar för utdata som är associerade med den valda kartan visas i listan Förinställningar för överordnad karta.

1. I listrutan **Förinställning för överordnad karta** väljer du den förinställning som du vill länka den aktuella kartans utdata med.

1. Välj önskad karta och dess förinställning för alla beroende ämnen och klicka på **Klar**.

   Kontexten för de beroende ämnena ställs nu in. Du kan generera utdata för den aktuella kartan. Mer information om hur du genererar utdata finns i [Generera utdata för en DITA-karta från kartkonsolen](generate-output-for-a-dita-map.md#).

### Blandad publicering

AEM Guides har stöd för publicering av DITA-innehåll på din befintliga AEM. Om du till exempel har en befintlig plats kan du använda AEM webbplatsutdata för att publicera endast DITA-innehållet på den platsen. I den här processen ändras inte det befintliga icke-DITA-innehållet i publiceringsprocessen. Kontakta din publiceringsadministratör om du vill ha mer information om hur du konfigurerar webbplatsen så att endast DITA-innehåll publiceras.

### Publicerar `conref`

Om du använder `conref` i ditt innehåll publiceras det som normalt eller inbäddat innehåll tillsammans med innehållet i källämnet \(eller refererande\). `conref`-innehållet återges tillsammans med huvudinnehållet och ingen separat webbplatssida skapas för det. När du söker efter innehållet som refereras i `conref` visas endast huvudavsnittet eller huvudsidan med `conref` -innehållet i sökresultaten.

>[!NOTE]
>
>Om du har genererat separata sidor för `conref`-innehållet med AEM Guides version 3.5 eller tidigare rekommenderar vi att du rensar/tar bort dessa sidor med alternativet [ Ta bort enstaka webbplatssidor ](#delete-orphan-page-aem-site) .


### Söka efter en sträng i innehållet

Du kan söka efter en sträng i AEM. Som standard kan du bara söka efter strängen i rubrikerna. Om du vill söka efter strängen i innehållet eller innehållet i AEM webbplatsutdata kontaktar du systemadministratören för att aktivera egenskapen flattening.enabled.

![Sök AEM webbplatsutdata](images/aem-output-search.png){width="650" align="left"}

Mer information finns i avsnittet *Konfigurera förenkling AEM platsnodstrukturen* i guiden Installera och konfigurera Adobe Experience Manager Guides.

**Överordnat ämne:**[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
