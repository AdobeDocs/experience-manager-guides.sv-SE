---
title: PDF | Generering av PDF-filer
description: Lär dig hur du använder PDF-publicering, skapar och genererar en förinställning för PDF-utdata, hämtar tillfälliga filer efter generering av PDF-utdata och använder språkvariabler i Adobe Experience Manager Guides.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Native PDF Output
role: User
source-git-commit: 9ae2690c52ab5408a9d17e9a40a89fe1f902042f
workflow-type: tm+mt
source-wordcount: '3083'
ht-degree: 0%

---

# Inbyggd förinställning för PDF-utdata

När du skapar innehåll är det viktigt att se till att innehållet är optimerat för visning, redigering och utskrift. Med hjälp av standarder som W3C CSS3 för innehållsformatering och CSS-sidstandarder för siddefinitionsegenskaper som storlek, marginaler, orientering, sidbrytningar, sidhuvuden, sidfötter och sidnumrering kan du ställa in vyn och layouten för dina PDF-dokument så att de blir enhetliga och användbara. Publiceringsfunktionen i PDF använder dessa standarder för att generera en PDF.

Med den inbyggda PDF-publiceringen kan du använda fördefinierade mallar för att säkerställa enhetlighet i innehållslayout och -struktur, använda formatmallar för att ändra utseendet, optimera PDF, ange skrivarmärken, tillåta skärmläsarstöd, ställa in PDF-överensstämmelse, bädda in teckensnitt och mycket annat.

Att generera en PDF med hjälp av PDF-publicering har två aspekter:

* Använd mallar för att formatera innehåll, ange sidlayouter och olika inställningar för att finjustera din PDF. Författare kan välja att använda/ändra exempelmallarna eller skapa egna mallar och ange avancerade konfigurationsalternativ som används av utgivare och utvecklare.

* Skapa eller konfigurera en förinställning för utdata från PDF för att styra PDF-inställningarna. När du har skapat en förinställning för PDF-utdata kan du generera PDF.

## Skapa en förinställning för utdata

Följ de här stegen för att skapa förinställningen för PDF från kartkonsolen:

1. [Öppna en DITA-kartfil i kartkonsolen](../user-guide/open-files-map-console.md).

   Du kan även komma åt kartfilen från widgeten **Senaste filer** i avsnittet [Översikt](../user-guide/intro-home-page.md#overview). Den markerade kartfilen öppnas i kartkonsolen.
1. Välj ikonen + på fliken **Utdataförinställningar** för att skapa en förinställning.
1. Välj **PDF** i listrutan Typ i dialogrutan **Ny förinställning** .
1. Ange ett namn för den här förinställningen i fältet **Namn**.
1. I fältet **Generera PDF med** väljer du **Native-PDF**.
1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning i den aktuella mappprofilen. Mappprofilsikonen ![](./assets/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](../user-guide/web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   Förinställningen för PDF skapas.

## Inbyggd förinställd konfiguration för PDF

När du har skapat förinställningen konfigurerar du inställningarna för den inbyggda PDF-förinställningen. De förinställda konfigurationsalternativen för DITA-OT är ordnade under flikarna **Allmänt**, **Metadata**, **Layout**, **Säkerhet**, **Skriv ut** och **Avancerat** .

<img src="assets/preset-panel.png" alt="förinställningspanelen" width="800">

**Allmänt**

Används för att ange grundläggande utdatainställningar, t.ex. en utdatasökväg, PDF-filnamn med mera.

| Inställning | Beskrivning |
| --- | --- |
| **Utdatasökväg** | Sökvägen i AEM-databasen där PDF-utdata lagras. Kontrollera att utdatasökvägen inte finns inuti projektmappen. Om du inte anger något värde genereras utdata på standardplatsen för DITA-mappningsutdata.<br>Du kan också använda följande variabler som inte finns i kartongen för att definiera utdatasökvägen. Du kan definiera det här alternativet med en eller flera variabler. <br> `${map_filename}`: Använder DITA-mappningsfilens namn för att skapa målsökvägen. <br> `${map_title}`: Använder DITA-mappningsrubriken för att skapa målsökvägen. <br>`${preset_name}`: Använder namnet på förinställningen för utdata för att skapa målsökvägen. <br> `${language_code}`: Använder språkkoden där mappningsfilen finns för att skapa målsökvägen. <br> `${map_parentpath}`: Använder den fullständiga sökvägen för kartfilen för att skapa målsökvägen.  <br>`${path_after_langfolder}`: Mappningsfilens sökväg används efter språkmappen för att skapa målsökvägen. |
| **PDF-fil** | Ange ett filnamn för att spara PDF. Som standard lägger PDF-filnamnet till DITA-schemanamnet tillsammans med förinställningsnamnet. Diditamap är till exempel TestMap och förinställningens namn är preset1. Standardnamnet för pdf är TestMap_preset1.pdf. <br>Du kan även använda följande variabler som inte finns i kartongen för att definiera PDF-filen. Du kan definiera det här alternativet med en eller flera variabler. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Använd villkor med** | För villkorat innehåll väljer du bland följande alternativ för att skapa en PDF-utdatafil baserat på dessa villkor: <br><ul> <li> **Inget använt** Välj det här alternativet om du inte vill använda något villkor på kartan och källinnehållet. <br><li> **Ditaval-fil** Välj en DITAVAL-fil för att generera villkorat innehåll. Välj Villkorsförinställning och leta reda på filen. <br> <li> **Villkorsförinställning** Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd villkorsförinställningar](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html) om du vill veta mer om villkorsförinställningar. <br> </ul> |
| **Använd baslinje** | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera. Visa [Arbeta med baslinjen](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) om du vill ha mer information. |
| **Skapa PDF med ändringsfältet mellan publicerade versioner** | Använd följande alternativ för att skapa en PDF som visar skillnaden i innehåll mellan två versioner med hjälp av ändringsfält:   <br><ul><li> **Baslinje för föregående version** Välj den baslinjeversion som du vill jämföra med den aktuella versionen eller en annan baslinje. Ett ändringsfält visas i PDF för att ange det ändrade innehållet. Ett ändringsfält är en lodrät linje som visuellt identifierar nytt eller ändrat innehåll. Ändringsfältet visas till vänster om innehållet som har infogats, ändrats eller tagits bort. <br> **Obs!** Om du väljer **Använd baslinje** och väljer en baslinje att publicera, görs jämförelsen mellan de två valda baslinjeversionerna. Om du till exempel väljer baslinje version 1.3 under **Använd baslinje** och version 1.1 under **Baslinje i föregående version**, görs jämförelsen mellan baslinje version 1.1 och baslinje version 1.3. <br><li> **Visa tillagd text** Markera om du vill visa den infogade texten i grön färg och understruken. Det här alternativet är markerat som standard. <br> <li> **Visa borttagen text** Markera om du vill visa borttagen text i röd färg och markerad med genomstrykning. Det här alternativet är markerat som standard. <br>**Obs!** Du kan också anpassa formateringen för ändringsfältet, infogat innehåll eller borttaget innehåll med formatmallen.<br></ul> |
| **Arbetsflöde efter generering** | Välj det här alternativet om du vill visa en nedrullningsbar lista som innehåller alla arbetsflöden som har konfigurerats i AEM. Du kan välja vilket arbetsflöde du vill köra när arbetsflödet för att skapa PDF har slutförts. |

**Metadata**

Metadata är beskrivningen eller definitionen av ditt innehåll. Metadata hjälper till vid innehållshantering och hjälper till att söka efter filer på Internet.

Använd fliken Metadata för att ange metadatafält som författarens namn, dokumenttitel, nyckelord, copyrightinformation och andra datafält för PDF-utdata. Du kan också lägga till anpassade metadata för dina PDF-utdata.

Dessa metadata mappas till metadata på fliken **Beskrivning** i **dokumentegenskaperna** för utdata-PDF.



<img src="assets/pdf-metadata.png" alt="metadata, flik" width="600">

Välj **PDF** > **Native-PDF** > **Metadata** i Utdataförinställningarna om du vill lägga till och anpassa metadataalternativ.
* **Använd metadata som lagts till i topicmeta**

  Det här alternativet är markerat som standard. Du kan använda de metadata som du har lagt till i topicmetaelementet i DITA-kartan för att fylla i metadatafälten i PDF-utdata.

* **Ange XMP-fil**

  Du kan också fylla i metadatafälten direkt genom att importera filen [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform). Här kan du hämta en exempelfil för XMP.

[Ladda ned](assets/SampleXMP.xmp)

  Du kan också generera en XMP-fil med Adobe Acrobat.
   1. Välj **Arkiv** > **Egenskaper** i Acrobat.
   1. Välj **Övriga metadata** under **Beskrivning**.
   1. Välj **Avancerat** i den vänstra panelen.
   1. Välj **Spara**.

  XMP-filen sparas på enheten.

* **Ange metadatanamn och värden**

   1. Lägg till namn genom att välja i listrutan eller lägg till egna metadata genom att skriva direkt i namnfältet.
   1. Ange värdet för metadata och välj ikonen +.
Metadata läggs till i listan över metadata för PDF.

Du kan också använda variabler för att definiera metadatavärden.  Du kan använda metadata som definierats för DITA-kartan eller bokmappsfilen som variabler. Metadata finns under noden `/jcr:content/metadata` i DITA-mappnings- eller bokmappfilen.
När du använder en variabel hämtas dess värde från metadataegenskaperna.

Om du vill använda en variabel måste du definiera den i formatet `${<variable>}`.

En av metadataegenskaperna som definieras i noden /`jcr:content/metadata` är
`dc:title`. Du kan ange `${dc:title}` och titelvärdet används i det slutliga resultatet.

Du kan använda en enskild variabel eller en kombination av variabler för att definiera metadata. Exempel: `${dc:title} ${dc:docstate}`. Du kan också använda kombinationen av en variabel och en sträng.  Exempel: `View ${dc:title} in ${dc:language}`.

Använd språkvariabler för att definiera det lokaliserade värdet för metadataegenskaper. Beroende på vilket språk du väljer hämtas det lokaliserade värdet automatiskt i PDF-utdata. Du kan till exempel skriva ut&quot;Författare&quot; som metadatavärde på engelska och&quot;Autorin&quot; på tyska.

Format: `${lng:<variable name>}`. `${lng:author-label}` där `author-label` är en språkvariabel.

Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära alternativet om du vill visa mer information om det.


**Layout**

Används för att ange sidlayouter och ange alternativ för sidvisning för PDF-utdata, till exempel Sidvisning och ange zoomnivåer.

| Inställning | Beskrivning |
| --- | --- |
| **PDF-mall** | PDF-mallar har en tydlig struktur för att definiera sidlayouter, formatera innehåll och tillämpa olika inställningar på dina PDF-utdata. Välj en mall i listrutan PDF-mall. <br> Du kan också välja **Bläddra efter mall** <img src="./assets/browse-templates-icon.svg"  alt= "bläddra bland mallar, ikon" width="25"> om du vill välja en mall. I dialogrutan **Välj PDF-mall** kan du även förhandsgranska miniatyrbilden och visa den markerade mallens rubrik och beskrivning. |
| **Sidvisning** | Använd Sidvisning för sidvyn som visar hur PDF visas när det öppnas. Välj en önskad vy i listrutan Sidvisning. <br><ul><li> **Standard** visas som standardinställningen för PDF-visningsprogrammet på en användares dator.  <br> <li> **Enkelsidig vy** Visar en sida i taget.   <br> <li> **Enkelsidig rullning** Visar en sida i en kontinuerlig lodrät kolumn.  <br> <li> **Dubbelsidig vy** Visar tvåsidigt uppslag sida vid sida. . <br> <li> **Dubbelsidig rullning** Visar tvåsidigt uppslag sida vid sida med kontinuerlig rullning. </ul> |
| **Zooma** | Välj det här alternativet om du vill ändra storlek på sidvyn som visar hur PDF visas när det öppnas.  <br><ul><li> **Standard** visas som standardinställningen för PDF-visningsprogrammet på en användares dator    <br> <li> **100%** Visar sidan i verklig storlek.     <br> <li> **Anpassa sida** Anpassa sidans bredd och höjd så att den passar i dokumentrutan.   . <br> <li> **Anpassa sidbredd** Gör sidans bredd lika bred som dokumentfönstret.  <br> <li> **Anpassa sidhöjd** Gör sidhöjden till dokumentfönstrets höjd. </ul> |

**Säkerhet**

Skydda din PDF genom att lägga till begränsningar för att öppna och läsa filen. Använd alternativen nedan för att undvika obehörig åtkomst.

| Inställning | Beskrivning |
| --- | --- |
| **Ange lösenord för att öppna dokumentet** | Välj det här alternativet om du vill lägga till ett säkert lösenord för att visa din PDF-fil. Ange ett lösenord i fältet **Användarlösenord**. Användare kan bara öppna PDF genom att ange lösenordet som anges i det här fältet. |
| **Ange dokumentbegränsningar** | Välj det här alternativet om du vill begränsa hur användare kan interagera med din PDF. Ange ett lösenord i fältet **Ägarlösenord** för att nedanstående begränsningsinställningar ska fungera.  <br><ul><li> **Skriver ut** Markera det här alternativet om du vill att en användare ska kunna skriva ut PDF. <br> <li> **Utskriftskvalitet för utkast** Markera om du vill att användare ska kunna skriva ut PDF med lägre upplösning.  <br> <li> **Innehållskopiering** Markera om du vill tillåta en användare att kopiera innehåll från PDF.   <br> <li> **Anteckningar** Markera om du vill att en användare ska kunna lägga till en anteckning eller kommentar i PDF. <br> <li> **Innehållsändringar** Markera om du vill att en användare ska kunna ändra innehållet i PDF. <br> <li> **Innehållskopiering för hjälpmedel** Markera det här alternativet om du vill tillåta skärmläsare att läsa och navigera i innehåll i PDF. <br>  **Dokumentsammansättning** Markera om du vill tillåta användare att infoga sidor i PDF. <br> **Obs!**: Användarna måste ange ägarlösenordet för att kunna ändra eventuella begränsningar från Arkiv > Egenskaper i Adobe Acrobat. |

**Skriv ut**

>[!NOTE]
>
> Från och med Experience Manager Guides 5.0/2025.02.0 är avsnittet Skriv ut nu en del av den **inbyggda PDF-utdataförinställningen**. För befintliga mallar med sparade utskriftsinställningar förblir utskriftsdata intakta men visas inte längre i användargränssnittet eller används vid utskrift. Om du vill fortsätta att använda de här inställningarna måste du konfigurera om dem i den inbyggda förinställningen för PDF-utdata.

Konfigurera utskriftsinställningarna för att tilldela skrivarmärken, välja färgmodeller och ange egenskaper för utskrift av PDF-utdata.

* **Skrivarmärken**: När du förbereder ett dokument för tryckproduktion läggs skrivarmärken till i sidgränserna för att underlätta korrekt justering, beskärning och färgval vid utskrift. Genom att välja ett skrivarmärke utökas sidgränsen så att den passar markeringen, som beskärs vid utskrift. Du kan välja att visa följande skrivarmärken i utdata från PDF:
   * **Ytmärken**: Välj alternativet att placera ett märke i varje hörn av ytområdet för att ange var papperet behöver beskäras efter utskrift.
   * **Utfallsmärken**: Markera för att placera ett märke i varje hörn av utfallsrutan för att ange den utökade bildens ytområde.
   * **Registreringsmärken**: Markera för att placera ett märke utanför beskärningsområdet för att justera de olika separationerna i ett färgdokument.
   * **Färgremsor**: Välj det här alternativet om du vill lägga till en färgremsa utanför det trimmade området för att behålla färgkonsekvensen och justera tryckfärgens densitet vid utskrift.

  Ange mått för de valda skrivarmärkena med alternativen **Linjens bredd**, **Linjefärg** och **Bredd för utfallsruta**.

* **Storlek på medieruta**: Detta är den totala sidstorleken inklusive det utökade område som används av skrivarmärken. Använd listrutan för att välja sidstorlek för dina PDF-utdata eller skapa en egen anpassad storlek.

* **Färgrymd**: Du kan välja mellan RGB- eller CMYK-färgrymder för utskrift av PDF-dokument. Välj RGB om du vill visa den genererade PDF digitalt och CMYK för fysisk utskrift. Färger som definieras i dokumentet konverteras till den valda färgrymden.

* **ICC-profil**: Här kan du hantera färgprecision på olika enheter genom att ange en ICC-profil. Detta garanterar enhetlig färgåtergivning i utskriften.

Om du vill konfigurera den här inställningen anger du ICC-profilens filsökväg på servern och anger ICC-profilens namn för att underlätta identifiering. Om ICC-profilen lagras online kan du ange dess URL i stället för filsökvägen.

>[!NOTE]
>
> En ICC-färgprofil krävs för att skapa PDF/A om CMYK-färgmodellen används.

<!--For more information on applying these print settings, see *Printing preferences*.-->

**Avancerat**

Använd följande alternativ för att ange avancerade inställningar för att sammanfoga PDF-filer, använda komprimering, välja kompatibilitetsstandard och mycket annat.

| Inställning | Beskrivning |
| --- | --- |
| **Skapa tillgänglig (taggad) PDF** | Välj det här alternativet om du vill generera en PDF med taggar. En taggad PDF gör det enklare för skärmläsare att läsa och navigera i innehåll, hyperlänkar, bokmärken osv. Om en tabell till exempel är taggad vet skärmläsaren att den läser tabellen och inte bara rader och text. |
| **Sammanfoga PDF-filer i innehållsförteckningen** | Välj det här alternativet om du vill sammanfoga befintliga PDF-filer i dina utdata genom att lägga till dem på DITA-kartan som en resursfil. PDF-filerna infogas på den plats som visas på kartan och sidorna ökas i enlighet med detta. |
| **Bädda in använda teckensnitt** | Välj det här alternativet när du använder teckensnitt som kanske inte är installerade på slutanvändarens dator. När det här alternativet är markerat bäddas de använda teckensnitten in i PDF så att användaren kan visa PDF som det är tänkt, även om teckensnitten inte är installerade på datorn. <br> **Obs!**: Ett teckensnitt kan bara bäddas in om det innehåller en inställning från teckensnittsleverantören som tillåter att det bäddas in. Kontrollera att du har rätt inställning eller licens innan du bäddar in ett teckensnitt. |
| **Använd automatisk avstavning** | När automatisk avstavning är aktiverat bryts ord i slutet av rader grammatiskt till rätt ställen med ett bindestreck. |
| **Aktivera JavaScript** | Aktivera det här alternativet om du har en JavaScript-kod som du vill använda för att omforma ditt innehåll dynamiskt innan du genererar en PDF. |
| **Bädda in multimediefiler** | Välj det här alternativet om du vill inkludera ljud, video och allt interaktivt innehåll i PDF. |
| **Använd fullständig komprimering för att optimera PDF-storleken** | Välj det här alternativet om du vill komprimera/minska storleken på en stor PDF. Kom ihåg att om du komprimerar PDF kan filkvaliteten försämras. |
| **Använd bildkomprimering för att optimera PDF-storleken** | Välj det här alternativet om du vill komprimera/minska storleken på bilder som används i din PDF. Kom ihåg att bildkvaliteten kan försämras om du komprimerar en bild. |
| **Använd anpassad upplösning (pixlar per tum)** | Det är sidans visningsupplösning i pixlar per tum. Ange ett önskat värde i fältet som visas när det här alternativet är markerat. Standardvärdet är 96 pixlar per tum. Ange ett högre värde om du vill passa in mer innehåll på en tum och tvärtom om du anger ett lägre värde. |
| **Visa vattenstämpel** | Välj det här alternativet om du vill lägga en vattenstämpel ovanpå dina utdata. Du kan ange en ny textsträng i textrutan med en teckenplacering som du vill. <br><br>Använd statisk text eller språkvariabler för att publicera den lokaliserade versionen av vattenstämpeln.  Beroende på vilket språk du väljer hämtas det lokaliserade värdet automatiskt i PDF-utdata. Du kan t.ex. skriva ut&quot;Utgivare&quot; som en vattenstämpel på engelska och&quot;Autentisering&quot; på franska.  <br>-format: `${lng:<variable name>}`. `$ {lng:publisher-label}` där `publisher-label` är en språkvariabel. <br> Hovra över <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära alternativet om du vill visa mer information om det. |
| **Aktivera MathML-ekvationer** | Välj det här alternativet om du vill återge MathML-ekvationer i ditt innehåll. Ekvationerna ignoreras annars som standard. |
| **Skapa interaktivt PDF-formulär** | Välj det här alternativet om du vill inkludera interaktiva och anpassningsbara PDF-formulärfält för förbättrad användarinmatning i genererade PDF-utdata. |
| **Inkludera spårningsändringar** | Välj det här alternativet om du vill inkludera spårade ändringar i den genererade PDF-filen för enkel granskning och jämförelse. |
| **Behåll temporära filer** | Välj det här alternativet om du vill behålla de mellanliggande HTML-filer som skapas när de ursprungliga PDF-utdata skapas. Du kan hämta de tillfälliga filerna senare när du har genererat utdata. De hämtade filerna innehåller även `system_config.json`-fil med information om författarens URL, lokal URL och publicerings-URL. |
| **PDF-överensstämmelse** | Det är den standard som du tänker spara din PDF så att den uppfyller kraven. I listrutan väljer du bland de tillgängliga PDF-standarderna. Mer information om vilka standarder som stöds finns i [Om PDF-standarder](https://helpx.adobe.com/se/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Filegenskaper** | Välj de metadata som du vill skicka till PDF-publicering. I listrutan visas både de anpassade egenskaperna och standardegenskaperna. Till exempel är `dc:description`, `dc:language`, `dc:title` och `docstate` standardegenskaper medan du kan ha `author` som anpassad egenskap. De valda metadataegenskaperna skickas till PDF-filen som genereras med den inbyggda PDF-filen. <br> De här egenskaperna hämtas från `metadataList`-filen som är tillgänglig på:`/libs/fmdita/config/metadataList`. <br>Den här filen kan överlappas: `/apps/fmdita/config/metadataList`. |



<!--------------


### Additional notes for PDF output

**Download temporary files after generating the Native PDF output**

If you select the **Download temporary files** option in the Advanced settings, you can also download the interim HTML files created while generating the Native PDF output. Once you’ve generated the output, you can download the temporary files using the **Download temporary files** ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg)icon on the top bar. This feature helps you view your interim HTML styles and layouts and helps you correct or change your CSS styles according to your requirements.


>[!NOTE]
>
> The **Download temporary files**  ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg) icon appears only if you have generated the last PDF output using the preset wherein you have selected the option in the **Advanced** tab. 


**Use language variables**

AEM Guides also provides the support for language variables. Select **Language Variables** <img src="assets/language-variables.svg" width="25">  in the left panel to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output. For more details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).


**Support for Markdown documents**

Experience Manager Guides also provides support for your Markdown documents.  Markdown files are easy to author and also provide a variety of formatting options. Learn how to [author Markdown documents from the Editor](../user-guide/web-editor-markdown-topic.md). 

You can add the Markdown topics to your DITA map and generate the PDF output using the Native PDF output presets.  Learn how to configure or [create a PDF output preset](#create-a-pdf-output-preset-create-output-preset). 

--------------->