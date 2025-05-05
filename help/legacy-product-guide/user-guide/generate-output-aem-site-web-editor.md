---
title: AEM Sites
description: Skapa och konfigurera AEM Sites-förinställningen i Web Editor och generera AEM Sites-utdata för DITA-kartor, valda ämnen och länkade ämnen.
feature: Publishing
role: User
hide: true
exl-id: 9a9ae44f-8fed-4a4e-812c-451bcf138d0a
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '2732'
ht-degree: 0%

---

# AEM Sites-förinställningar i Web Editor


Du kan skapa AEM Sites-förinställningar från Web Editor och konfigurera dem för att generera AEM Sites-utdata. Utdata från AEM Sites baseras på den sammansatta komponentmappningen tillsammans med `guides-components`, vilket underlättar skapandet och hanteringen av innehåll.

Experience Manager Guides innehåller fördefinierade mallar för att skapa AEM Sites. Dessa förinställningar hjälper dig att säkerställa en konsekvent innehållslayout och struktur.
- [Skapa hemsidor](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) baserat på dessa fördefinierade mallar.
- Du kan [redigera ämnesmallar](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) och använda format enligt dina önskemål.
- Du kan också [anpassa befintliga AEM Sites-mallar](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).



## Skapa AEM Sites-förinställningar

Så här skapar du AEM Sites-förinställningar i Web Editor:

1. Öppna DITA-schemafilen i Kartvyn på databaspanelen.
1. Välj ikonen + på fliken **Utdata** för att skapa en förinställning för utdata.
1. Välj **AEM Sites** i listrutan **Typ** i dialogrutan **Ny förinställning**.
1. Avmarkera alternativet **Använd äldre komponentmappning** i dialogrutan **Ny förinställning** .

![Nytt ](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Innan du konfigurerar AEM Sites-förinställningarna för Experience Manager Guides måste administratören skapa en AEM Sites-struktur med hjälp av mallarna.
>- **Lokal programvara**: Läs mer om hur du [hämtar och installerar AEM Sites-mallar](/help/product-guide/install-guide/download-install-aem-sites-templates.md) för lokal programvara.
>- **Cloud Service**: Läs mer om hur du [hämtar och installerar AEM Sites-mallar](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md) för Cloud Service.




### Lägga till förinställningar i den aktuella mappprofilen

Som administratör kan du med Experience Manager Guides skapa och hantera utdatapresentationer för globala profiler och mappprofiler. Välj alternativet **Lägg till i aktuell mappprofil** i dialogrutan **Ny förinställning** för att skapa en förinställning för den aktuella mappprofilen. ![mappprofilsikonen](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.  Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

### AEM Sites-förinställningar baserade på äldre komponentmappning

Du kan också skapa AEM Sites-förinställningar med den äldre komponentmappningen. Om du vill skapa AEM Sites-förinställningar baserade på äldre komponentmappning väljer du alternativet **Använd äldre komponentmappning** i dialogrutan **Ny förinställning** .

Vissa alternativ kan skilja sig åt för förinställningar som använder äldre komponentmappning.



## Konfigurera förinställningarna för AEM Sites

Konfigurationerna ordnas under flikarna **Allmänt**, **Innehåll**, **Ämneslista** och **Korskarta**.

![förinställningar för aem-webbplatser](images/aem-sites-new-config.png)
**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationer som är relaterade till generering av utdata:

- Använd webbplatssökväg
- Platssökväg
- Plats
- Publiceringssökväg
- Ämnessidmall
- Generera sidnamn baserat på
   - Ämnesfilnamn
   - Ämnestitel
- Rensa tidigare genererade sidor
   - Ta bort tidigare genererade sidor för ämnen som tagits bort från kartan
   - Ta bort alla sidor som skapats av andra källor på den här sökvägen:
- Arbetsflöde efter generering



**Innehåll**

Fliken **Innehåll** innehåller följande konfigurationer:

- Använd baslinje
- Villkorsfiltrering
- Ytterligare kommandoradsargument för DITA-OT
- Metadata
   - Filegenskaper (Assets)
   - Använd kartegenskaper som reserv


Mer information finns i [AEM Sites-konfiguration](#aem_sites_config).

**Ämneslista**

**Ämneslistan** visar en lista med ämnen som finns i den aktuella arbetskopian av DITA-kartan. Som standard inkluderas alla ämnen. Du kan välja ut specifika ämnen och generera utdata från AEM Sites endast för dem. Du har till exempel uppdaterat vissa avsnitt så att du bara kan publicera dessa ämnen i stället för att publicera hela DITA-kartan.

Fliken **Ämneslista** finns i AEM-förinställningar som inte har skapats baserat på äldre mappning.

**Korsmappningsreferenser**
Den här listan innehåller ämnen som innehåller korsmappsreferenser med `scope ="peer"`. Du kan ange publiceringskontext för en lista över korsmappsreferenser med `scope="peer"` till ämnen som är tillgängliga i andra DITA-kartor. Den här fliken visas om du använder Experience Manager Guides-versionen (UUID).



Läs mer om hur du [publicerar länkade ämnen](#publish-linked-topics).





## AEM Sites-konfiguration {#aem_sites_config}

Följande alternativ är tillgängliga för AEM Sites-utdata:

| AEM Sites-alternativ | Beskrivning |
| --- | --- |
| Använd webbplatssökväg | Använd det här alternativet om du vill publicera ditt innehåll på en Experience Manager-webbplats. Välj det här alternativet om du känner till den exakta platssökvägen där du vill att utdata ska publiceras. Ange också den fullständiga sökvägen i fältet Platssökväg. |
| Platssökväg | Det här alternativet visas om du väljer alternativet **Använd webbplatssökväg**. Bläddra i den exakta Experience Manager Site-sökvägen där du vill att utdata ska publiceras. |
| Plats | Namnet på den Experience Manager Sites som du vill publicera ditt innehåll på. Alternativen i listrutan fylls i baserat på listan med webbplatser som är tillgängliga i AEM Sites. <br>Välj **Uppdatera** ![referensikon](images/navtitle-refresh-icon.svg) om du vill hämta en ny lista med alternativ och spegla de uppdaterade data. |
| Publiceringssökväg | Den sökväg i AEM-databasen där utdata lagras. Publiceringssökvägen fylls i med alla sökvägar som innehåller sidor som skapats baserat på hemsidmallen. AEM Sites-utdata från DITA-kartan genereras under den här sökvägen.  Om du till exempel anger platsen som `AEMG-Docs` och publiceringssökvägen som `aemg-docs-en/docs/product-abc.`, genereras AEM Sites-utdata under noden `aemg-docs-en/docs/product-abc/` i `crx/de`. |
| Ämnessidmall | De strukturella komponenter som du kan använda för att ordna innehåll på ett konsekvent sätt i flera dokument. De här mallarna är fördefinierade i Adobe Experience Manager Site-mallen. Alternativen är ifyllda med alla ämnessidmallar som är tillgängliga för den valda webbplatsen. Välj den mall som du vill använda för alla utdataämnen. |
| Generera sidnamn baserat på | **Ämnesfilnamn**: Använder DITA-avsnittets filnamn för att skapa URL:en för platsen. <br> **Ämnestitel**: Använder DITA-avsnittets titel för att skapa Experience Manager-webbplatsnamnen. |
| Rensa tidigare genererade sidor | - **Ta bort tidigare genererade sidor för ämne som tagits bort från kartan**: Om strukturen för DTIA-kartan ändras kan du använda det här alternativet för att ta bort tidigare genererade sidor för de borttagna ämnena. Den här funktionen är endast tillgänglig för fullständig kartpublicering.<br><br>Säg att du har publicerat en DITA-karta som innehåller avsnitten a.dita, b.dita och c.dita. Innan du publicerade kartan igen tog du bort b.dita-ämnet från kartan. Om du har valt det här alternativet tas nu allt innehåll som är relaterat till b.dita bort från AEM Sites-utdata och bara a.dita och c.dita publiceras.<br><br>**Obs!**: Information om borttagna sidor hämtas också i loggarna för utdatagenerering. Mer information om åtkomst till loggfilerna finns i [Visa och kontrollera loggfilen](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Varning**: När du tar bort ämnen blir sidorna otillgängliga från den publicerade webbplatsen. Innan ämnena tas bort visas en varning. Du måste bekräfta att du vill ta bort dem.<br><br>- **Ta bort alla sidor som skapats av andra källor på den här sökvägen**: Om du väljer det här alternativet tas alla sidor som publicerats på den här sökvägen bort från andra kartor, enskilda ämnen eller andra källor. Sidorna blir också otillgängliga från den publicerade webbplatsen. Innan ämnena tas bort visas en varning. Du måste bekräfta att du vill ta bort dem. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>**Viktigt**: När du genererar inkrementella utdata för AEM Site skapas utdata med den aktuella versionen av filerna och inte med den kopplade baslinjen.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Villkorlig filtrering | Välj ett av följande alternativ:<br><br>**Inget**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>**Använder DITAVAL**: Välj DITAVal-filer för att generera villkorat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du väljer någon annan filtyp.<br>**Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Ytterligare DITA-OT-kommandoradsargument | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om vilka kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/). |
| Metadata <br> <br>Filegenskaper (Assets) | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>**Obs!** Metadataegenskaperna är skiftlägeskänsliga.<br><br>*Om du har valt en baslinje baseras värdena för egenskaperna på versionen av den valda baslinjen.<br>* Om du inte har valt en baslinje baseras värdena för egenskaperna på den senaste versionen.<br><br>Du kan också skicka metadata till utdata med DITA-OT-publicering. Om du vill ha mer information kan du [skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Obs!**: Om du inte har definierat `cq:tags` i alternativet Egenskaper hämtas värdena för `cq:tags` från den aktuella arbetskopian, även om du har valt en baslinje för publicering. |
| Metadata <br> <br>Använd mappningsegenskaper som reserv | Om du väljer det här alternativet kopieras även de egenskaper som definierats för kartfilen till de avsnitt där sådana egenskaper inte har definierats. Tänk på följande när du använder det här alternativet:<br><br>*Endast egenskaperna String, Date eller Long (en och flera värden) kan skickas till AEM Site-sidorna.<br>* Metadatavärdena för en String-typegenskap stöder inte några specialtecken (till exempel `@, #, " "`).<br>* Det här alternativet bör användas tillsammans med alternativet `Properties`. |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.png) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |


### Generera AEM Sites-utdata med hjälp av mallar

Med Experience Manager Guides kan du använda färdiga mallar eller lägga till egna AEM Sites-mallar.

Innan du konfigurerar AEM Sites-förinställningarna måste du skapa en AEM Sites-struktur med hjälp av mallarna.\
Mer information finns i [Hämta och installera AEM Sites-mallar](/help/product-guide/install-guide/download-install-aem-sites-templates.md).



Så här skapar och konfigurerar du en förinställning för AEM Sites:
1. Öppna fliken **Utdatainställningar** i den DITA-karta som du vill publicera.
1. Välj förinställningen **AEM Sites** för utdata.
1. (Valfritt) Avmarkera alternativet **Använd äldre komponentmappning** om du vill skapa en förinställning som inte är äldre för AEM Sites.
1. Klicka på **Lägg till**. Förinställningen för AEM Sites skapas.
1. Du kan konfigurera mallen för användningsklara platser på två sätt:
   1. Välj **Plats** och välj sedan publiceringssökvägen och ämnessidmallarna bland de ifyllda alternativen:
      1. Markera platsen.
      1. Välj **Plats**. Exempel: `AEMG Docs`.
      1. Alternativen **Publiceringssökväg** och **Ämnessidmall** anges automatiskt i listrutan. Du kan också välja alternativ. Till exempel är `AEMG-Docs-Site/en/docs/product1` och `Topic page` inställda.
   1. Välj den fullständiga sökvägen till platsen:
      1. Välj alternativet **Använd webbplatssökväg**.
      1. Markera den fullständiga sökvägen till platsen. Exempel: `/content/AEMG-Docs-Site/en/docs/product1`.
      1. Ämnessidmallen anges automatiskt som `Topic Page`.


1. Spara ändringarna som gjorts i förinställningen.
1. Välj alternativet **Generera**.
1. Generera AEM Sites för motsvarande karta. Exempel: `/content/AEMG-Docs-Site/en/docs/product`.


   >[!NOTE]
   >
   > Om du publicerar innehåll på en AEM-webbplats för första gången bör du publicera sidorna på webbplatsnivå. Detta garanterar att utdata visas korrekt på instansen **Publish** utan några CSS-avbrott.



### Publicera länkade ämnen

Experience Manager Guides förenklar publiceringen av komplexa dokument genom att du kan skapa ämnesreferenser med `peer @scope`. Du kan sedan definiera publiceringskontexten för dessa referenser från AEM Sites-förinställningar och slutligen generera utdata för de länkade avsnitten.
Mer information finns i [Generera utdata för att länka ämnen från andra kartor](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Gör så här för att ange publiceringskontext för korslänkade filer:
1. Öppna fliken **Utdatainställningar** i den DITA-karta som du vill publicera.
1. Välj förinställningen **AEM Sites** för utdata.

   Du kan visa flikarna **Allmänt**, **Innehåll**, **Ämneslista** och **Korsmappningsreferenser**. Fliken **Korsmappningsreferenser** visas om du använder Experience Manager Guides-versionen (UUID).

   Du kommer inte att kunna visa länken för tvärschemat i följande fall:
   - För förinställningar som skapats före version 4.6. Fliken Korsreferenser är inaktiverad och ett verktygstips visas. Mer information finns på kontrollpanelen Karta.
   - För förinställningar som skapas från kartkontrollpanelen. Mer information finns i Kartkontrollpanelens verktygstips.
   - För OTB-förinställningar finns mer information i verktygstipset för kontrollpanelen Karta.
   - För globala förinställningar skapar du en lokal kopia av den här globala förinställningen för att ange korsmappningsreferenser.
Om du vill använda AEM Sites-förinställningar i Web Editor skapar du en ny förinställning eller duplicerar den befintliga förinställningen.

1. Öppna fliken **Korsmappningsreferenser**.

   Du visas en lista med ämnen och deras referenser. Du kan ange publiceringskontext för en lista med korsmappningsreferenser till ämnen som är tillgängliga i andra DITA-kartor med `scope="peer"`.

   Om du vill använda korsmappsreferenspanelen från Web Editor måste `<xrefs>` ha unika ID:n. Unika ID:n för `<xrefs>` genereras automatiskt när det äldre innehållet redigeras/sparas om ID:t inte finns där.

   >[!NOTE]
   >
   >Fliken **Korskartmappsreferenser** visar ämnen som endast är länkade med `scope="peer"`. För länkar med `scope="local"` behöver du inte ange publiceringskontext.

   Alla länkade ämnen har den senaste förinställningen och kartan för utdata markerat som standard. Publiceringskontexten för alla länkade ämnen är inställd på `<Most recently generated>`-karta som standard.

   ![Korskartmappsreferenser](images/aem-sites-cross-map-references.png)

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
