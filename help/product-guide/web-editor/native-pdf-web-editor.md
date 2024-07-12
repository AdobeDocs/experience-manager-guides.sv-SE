---
title: PDF | Generering av utdata från PDF
description: Lär dig hur du använder publicering i PDF, skapar och genererar en förinställning för utdata i PDF, hämtar tillfälliga filer efter att utdata för PDF har genererats och använder språkvariabler i AEM Guides.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Web Editor, Native PDF Output
role: User
source-git-commit: e78749b1d5b4ba944cbca69ba65c6d28355b2c34
workflow-type: tm+mt
source-wordcount: '3362'
ht-degree: 0%

---

# Utdata från Publish PDF

Med AEM Guides kan du generera PDF för enskilda ämnen eller en hel kartfil. Du kan publicera ditt innehåll i PDF-format på något av följande tre sätt:

* **DITA-OT**

Använd den här metoden om du vill generera utdata från PDF för en karta från kontrollpanelen för kartor. Du kan ange publiceringsegenskaper innan du genererar PDF genom att skapa en förinställning för kartan som är öppen på kartkontrollpanelen. Om du vill skapa eller redigera en förinställning för utdata *Förstå förinställningarna* i [AEM Guides as a Cloud Service användarhandbok](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Mer information om hur du genererar ett PDF med DITA-OT-metoden finns i [Generera PDF med DITA-OT](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server (FMPS)**

Använd den här metoden om du vill generera utdata från PDF inte bara DITA-innehåll, utan även FrameMaker-dokument (.book och .fm) som finns i din AEM. Du kan skapa PDF genom att konfigurera en förinställning och publicera den med FrameMaker Publishing Server (FMPS). Du kan utforma och konfigurera utdatafilens utseende och känsla för PDF och andra format och lagra samma i en inställningsfil (.sts). Inställningsfilen används sedan av FMPS för att generera utdata för en DITA-karta eller en .book-fil. Mer information om hur du skapar eller redigerar en förinställning finns i avsnittet *Förinställningar för utdata* i [AEM Guides as a Cloud Service User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf) .

Mer information om hur du konfigurerar FMPS finns i [Generera utdata från FrameMaker-dokument](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **Inbyggd PDF-publicering**

Använd den här metoden om du vill generera funktionsrika utdata för PDF baserat på W3C CSS3- och CSS-sidorienterade mediestandarder. Med Native PDF kan du använda mallar för att ange layout och format för ditt innehåll och använda olika inställningar för att finjustera PDF. Dessutom kan du ändra och skapa egna mallar med mallredigeraren.

Mer information om Native PDF finns i [Använda Native PDF-publicering](#native-pdf-publishing).


## Använda Native PDF {#native-pdf-publishing}

När du skapar innehåll är det viktigt att se till att innehållet är optimerat för visning, redigering och utskrift. Med hjälp av standarder som W3C CSS3 för innehållsformatering och CSS-sidstandarder för siddefinitionsegenskaper som storlek, marginaler, orientering, sidbrytningar, sidhuvuden, sidfötter och sidnumrering kan du ange PDF-dokumentets vy och layout för att säkerställa konsekvens och användbarhet. Publiceringsfunktionen i PDF använder dessa standarder för att skapa en PDF.

Med den inbyggda PDF-publiceringen kan du använda fördefinierade mallar för att säkerställa en enhetlig innehållslayout och struktur, använda formatmallar för att ändra utdatautdatafilens utseende och känsla, optimera PDF, ange skrivarmärken, tillåta skärmläsarstöd, ange PDF-överensstämmelse, bädda in teckensnitt och mycket annat.

Att generera en PDF med hjälp av Native PDF har två aspekter:

* Använd mallar för att formatera innehåll, ange sidlayouter och olika inställningar för att finjustera PDF. Författare kan välja att använda/ändra exempelmallarna eller skapa egna mallar och ange avancerade konfigurationsalternativ som används av utgivare och utvecklare.

* Skapa eller konfigurera en förinställning för utdata från PDF för att styra inställningarna för PDF. När du har skapat en förinställning för PDF kan du generera PDF.

Mer information finns i [Skapa utdata i PDF](#generate-pdf-output).

## Skapa en förinställning för PDF {#create-output-preset}

Det första steget i att skapa utdata för PDF är att skapa en förinställning för utdata från PDF, som är en samling publiceringsegenskaper som tilldelats en karta. Du kan skapa en förinställning för utdata för en karta som är öppen på panelen Kartvy eller konfigurera en befintlig förinställning för att snabbt generera ett PDF för samma karta.

Från förinställningen för PDF-utdata kan du välja en mall, använda villkor, ange begränsningar för hur en användare interagerar med PDF, konfigurera avancerade inställningar som komprimering, överensstämmelse med mera.

Så här skapar eller konfigurerar du en förinställning för PDF:

1. Klicka på **Förinställningar** i det vänstra sidofältet på fliken Utdata.
Förinställningspanelen öppnas. <br>
<img src="assets/preset-panel.png" alt="förinställningspanelen" width="600">

1. Gör något av följande på panelen **Förinställningar**:
   * Dubbelklicka på en fördefinierad förinställning för PDF för att visa den.
   * Klicka på ikonen + mot **Förinställningar** för att lägga till en ny förinställning av **Typ: PDF**

1. Så här konfigurerar du inställningar för en befintlig förinställning för PDF:
   * Klicka på ikonen **Alternativ** ![options](assets/options.svg) bredvid den önskade förinställningen och välj **Redigera**.
Du kan använda följande inställningar på flikarna **Allmänt**, **Metadata**, **Layout**, **Säkerhet** och **Avancerat** för att konfigurera en förinställning för PDF-utdata:

**Allmänt**

Används för att ange grundläggande utdatainställningar, t.ex. en utdatasökväg, ett PDF-filnamn med mera.

| Inställning | Beskrivning |
| --- | --- |
| **Utdatasökväg** | Sökvägen i AEM där utdata från PDF lagras. Kontrollera att utdatasökvägen inte finns inuti projektmappen. Om du inte anger något värde genereras utdata på standardplatsen för DITA-mappningsutdata.<br>Du kan också använda följande variabler som inte finns i kartongen för att definiera utdatasökvägen. Du kan definiera det här alternativet med en eller flera variabler. <br> `${map_filename}`: Använder DITA-mappningsfilens namn för att skapa målsökvägen. <br> `${map_title}`: Använder DITA-mappningsrubriken för att skapa målsökvägen. <br>`${preset_name}`: Använder namnet på förinställningen för utdata för att skapa målsökvägen. <br> `${language_code}`: Använder språkkoden där mappningsfilen finns för att skapa målsökvägen. <br> `${map_parentpath}`: Använder den fullständiga sökvägen för kartfilen för att skapa målsökvägen.  <br>`${path_after_langfolder}`: Mappningsfilens sökväg används efter språkmappen för att skapa målsökvägen. |
| **PDF-fil** | Ange ett filnamn för att spara PDF. Som standard lägger filnamnet PDF till DITA-mappningsnamnet tillsammans med förinställningsnamnet. Diditamap är till exempel TestMap och förinställningens namn är preset1. Standardnamnet för pdf är TestMap_preset1.pdf. <br>Du kan också använda följande variabler som inte finns i kartongen för att definiera filen PDF. Du kan definiera det här alternativet med en eller flera variabler. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Använd villkor med** | För villkorat innehåll väljer du bland alternativen nedan för att skapa utdata i PDF baserat på dessa villkor: <br><ul> <li> **Inget använt** Välj det här alternativet om du inte vill använda något villkor på kartan och källinnehållet. <br><li> **Ditaval-fil** Välj en DITAVAL-fil för att generera villkorat innehåll. Markera genom att klicka på Villkorsförinställning och leta reda på filen. <br> <li> **Villkorsförinställning** Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Det här alternativet är synligt om du har lagt till ett villkor för DITA-kartfilen. De villkorliga inställningarna finns på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om villkorsförinställningar finns i [Använda villkorsförinställningar](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Använd baslinje** | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera. Mer information finns i [Arbeta med baslinje](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html). |
| **Skapa PDF med ändringsfältet mellan publicerade versioner** | Använd följande alternativ för att skapa en PDF som visar skillnader i innehåll mellan två versioner med hjälp av ändringsfält:   <br><ul><li> **Baslinje för föregående version** Välj den baslinjeversion som du vill jämföra med den aktuella versionen eller en annan baslinje. Ett ändringsfält visas i PDF för att ange det ändrade innehållet. Ett ändringsfält är en lodrät linje som visuellt identifierar nytt eller ändrat innehåll. Ändringsfältet visas till vänster om innehållet som har infogats, ändrats eller tagits bort. <br> **Obs!** Om du väljer **Använd baslinje** och väljer en baslinje att publicera, görs jämförelsen mellan de två valda baslinjeversionerna. Om du till exempel väljer baslinje version 1.3 under **Använd baslinje** och version 1.1 under **Baslinje i föregående version**, görs jämförelsen mellan baslinje version 1.1 och baslinje version 1.3. <br><li> **Visa tillagd text** Markera om du vill visa den infogade texten i grön färg och understruken. Det här alternativet är markerat som standard. <br> <li> **Visa borttagen text** Markera om du vill visa borttagen text i röd färg och markerad med genomstrykning. Det här alternativet är markerat som standard. <br>**Obs!** Du kan också anpassa formateringen för ändringsfältet, infogat innehåll eller borttaget innehåll med formatmallen.<br></ul> |
| **Post Generation Workflow** | Välj det här alternativet om du vill visa en nedrullningsbar lista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du kan välja det arbetsflöde som du vill köra när arbetsflödet för generering av PDF har slutförts. |

**Metadata**

Metadata är beskrivningen eller definitionen av ditt innehåll. Metadata hjälper till vid innehållshantering och hjälper till att söka efter filer på Internet.

Använd fliken Metadata för att ange metadatafält som författarens namn, dokumenttitel, nyckelord, copyrightinformation och andra datafält för utdata från PDF. Du kan också lägga till anpassade metadata för utdata från PDF.

Dessa metadata mappas till metadata på fliken **Beskrivning** i **Dokumentegenskaper** för PDF.



<img src="assets/pdf-metadata.png" alt="metadata, flik" width="600">

Välj **PDF** > **Native-PDF** > **Metadata** i Utdatainställningarna om du vill lägga till och anpassa metadataalternativ.
* **Använd metadata som lagts till i topicmeta**

  Det här alternativet är markerat som standard. Du kan använda de metadata som du har lagt till i topicmeta-elementet i DITA-kartan för att fylla i metadatafälten i utdata från PDF.

* **Ange XMP fil**

  Du kan också fylla i metadatafälten direkt genom att importera filen [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform). Här kan du hämta ett XMP.

[Ladda ned](assets/SampleXMP.xmp)

  Du kan också generera en XMP med Adobe Acrobat.
   1. Klicka på **Arkiv** > **Egenskaper** i Acrobat.
   1. Klicka på **Övriga metadata** under **Beskrivning**.
   1. Välj **Avancerat** i den vänstra panelen.
   1. Klicka på **Spara**.

  XMP sparas på enheten.

* **Ange metadatanamn och värden**

   1. Lägg till namn genom att välja i listrutan eller lägg till egna metadata genom att skriva direkt i namnfältet.
   1. Ange värdet för metadata och klicka på plustecknet (+).
Metadata läggs till i listan med metadata för PDF.

Du kan också använda variabler för att definiera metadatavärden.  Du kan använda metadata som definierats för DITA-kartan eller bokmappsfilen som variabler. Metadata finns under noden `/jcr:content/metadata` i DITA-mappnings- eller bokmappfilen.
När du använder en variabel hämtas dess värde från metadataegenskaperna.

Om du vill använda en variabel måste du definiera den i formatet `${<variable>}`.

En av metadataegenskaperna som definieras i noden /`jcr:content/metadata` är
`dc:title`. Du kan ange `${dc:title}` och titelvärdet används i det slutliga resultatet.

Du kan använda en enskild variabel eller en kombination av variabler för att definiera metadata. Exempel: `${dc:title} ${dc:docstate}`. Du kan också använda kombinationen av en variabel och en sträng.  Exempel: `View ${dc:title} in ${dc:language}`.

Använd språkvariabler för att definiera det lokaliserade värdet för metadataegenskaper. Beroende på vilket språk du väljer hämtas det lokaliserade värdet automatiskt i utdata från PDF. Du kan till exempel skriva ut&quot;Författare&quot; som metadatavärde på engelska och&quot;Autorin&quot; på tyska.

Format: `${lng:<variable name>}`. `${lng:author-label}` där `author-label` är en språkvariabel.

Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära alternativet om du vill visa mer information om det.


**Layout**

Används för att ange sidlayouter och ange alternativ för sidvisning för utdata från PDF, till exempel Sidvisning och ange zoomnivåer.

| Inställning | Beskrivning |
| --- | --- |
| **PDF-mall** | PDF-mallar har en tydlig struktur för att definiera sidlayouter, formatera innehåll och tillämpa olika inställningar på utdata från PDF. Välj en mall i listrutan PDF. <br> Du kan också välja **Bläddra efter mall** <img src="./assets/browse-templates-icon.svg"  alt= "bläddra bland mallar, ikon" width="25"> om du vill välja en mall. I dialogrutan **Välj PDF-mall** kan du även förhandsgranska miniatyrbilden och visa den markerade mallens rubrik och beskrivning. |
| **Sidvisning** | Använd sidvisningen för sidvyn som visar hur PDF visas när den öppnas. Välj en önskad vy i listrutan Sidvisning. <br><ul><li> **Standard** visas som standardinställningen för PDF-visningsprogrammet på en användares dator.  <br> <li> **Enkelsidig vy** Visar en sida i taget.   <br> <li> **Enkelsidig rullning** Visar en sida i en kontinuerlig lodrät kolumn.  <br> <li> **Dubbelsidig vy** Visar tvåsidigt uppslag sida vid sida. . <br> <li> **Dubbelsidig rullning** Visar tvåsidigt uppslag sida vid sida med kontinuerlig rullning. </ul> |
| **Zooma** | Välj det här alternativet om du vill ändra storlek på sidvyn som visar hur PDF visas när den öppnas.  <br><ul><li> **Standard** visas som standardinställningen för PDF-visningsprogrammet på en användares dator    <br> <li> **100%** Visar sidan i verklig storlek.     <br> <li> **Anpassa sida** Anpassa sidans bredd och höjd så att den passar i dokumentrutan.   . <br> <li> **Anpassa sidbredd** Gör sidans bredd lika bred som dokumentfönstret.  <br> <li> **Anpassa sidhöjd** Gör sidhöjden till dokumentfönstrets höjd. </ul> |

**Säkerhet**

Protect PDF genom att lägga till begränsningar för att öppna och läsa filen. Använd alternativen nedan för att undvika obehörig åtkomst.

| Inställning | Beskrivning |
| --- | --- |
| **Ange lösenord för att öppna dokumentet** | Markera det här alternativet om du vill lägga till ett säkert lösenord för att visa din PDF-fil. Ange ett lösenord i fältet **Användarlösenord**. Användare kan bara öppna PDF genom att ange lösenordet som anges i det här fältet. |
| **Ange dokumentbegränsningar** | Markera det här alternativet om du vill begränsa hur användare kan interagera med PDF. Ange ett lösenord i fältet **Ägarlösenord** för att nedanstående begränsningsinställningar ska fungera.  <br><ul><li> **Skriver ut** Markera det här alternativet om du vill att en användare ska kunna skriva ut PDF. <br> <li> **Utskriftskvalitet för utkast** Markera det här alternativet om du vill att en användare ska kunna skriva ut PDF i en lägre upplösning.  <br> <li> **Innehållskopiering** Markera om du vill tillåta en användare att kopiera innehåll från PDF.   <br> <li> **Anteckningar** Markera om du vill att en användare ska kunna lägga till en anteckning eller kommentar i PDF. <br> <li> **Innehållsändringar** Markera om du vill att en användare ska kunna ändra innehållet i PDF. <br> <li> **Innehållskopiering för hjälpmedel** Markera det här alternativet om du vill tillåta skärmläsare att läsa och navigera i innehåll i PDF. <br>  **Dokumentsammansättning** Markera om du vill tillåta användare att infoga sidor i PDF. <br> **Obs!**: Användarna måste ange ägarlösenordet för att kunna ändra eventuella begränsningar från Arkiv > Egenskaper i Adobe Acrobat. |

**Avancerat**

Använd följande alternativ för att ange avancerade inställningar för att sammanfoga PDF, använda komprimering, välja kompatibilitetsstandard och mycket annat.

| Inställning | Beskrivning |
| --- | --- |
| **Skapa tillgänglig (taggad) PDF** | Välj det här alternativet om du vill generera en PDF med taggar. Ett PDF med märkord gör det enklare för skärmläsare att läsa och navigera i innehåll, hyperlänkar, bokmärken och så vidare. Om en tabell till exempel är taggad vet skärmläsaren att den läser tabellen och inte bara rader och text. |
| **Lägg samman PDF ingår i innehållsförteckningen** | Välj det här alternativet om du vill sammanfoga befintlig PDF med dina utdata genom att lägga till dem på DITA-kartan som en resursfil. PDF infogas på den plats som visas på kartan och sidorna ökas därefter. |
| **Bädda in använda teckensnitt** | Välj det här alternativet när du använder teckensnitt som kanske inte är installerade på slutanvändarens dator. När det här alternativet är markerat bäddas de använda teckensnitten in i PDF så att användaren kan se PDF som det är tänkt, även om teckensnitten inte är installerade på datorn. <br> **Obs!**: Ett teckensnitt kan bara bäddas in om det innehåller en inställning från teckensnittsleverantören som tillåter att det bäddas in. Kontrollera att du har rätt inställning eller licens innan du bäddar in ett teckensnitt. |
| **Använd automatisk avstavning** | När automatisk avstavning är aktiverat bryts ord i slutet av rader grammatiskt till rätt ställen med ett bindestreck. |
| **Aktivera JavaScript** | Aktivera det här alternativet om du har en JavaScript-kod som du vill använda för att omforma ditt innehåll dynamiskt innan du genererar ett PDF. |
| **Bädda in multimediefiler** | Markera det här alternativet om du vill inkludera ljud, video och allt interaktivt innehåll i PDF. |
| **Använd fullständig komprimering för att optimera PDF-storleken** | Välj det här alternativet om du vill komprimera/minska storleken på ett stort PDF. Kom ihåg att om du komprimerar PDF kan filkvaliteten försämras. |
| **Använd bildkomprimering för att optimera PDF-storleken** | Markera det här alternativet om du vill komprimera/minska storleken på de bilder som används i PDF. Kom ihåg att bildkvaliteten kan försämras om du komprimerar en bild. |
| **Använd anpassad upplösning (pixlar per tum)** | Det är sidans visningsupplösning i pixlar per tum. Ange ett önskat värde i fältet som visas när det här alternativet är markerat. Standardvärdet är 96 pixlar per tum. Ange ett högre värde om du vill passa in mer innehåll på en tum och tvärtom om du anger ett lägre värde. |
| **Visa vattenstämpel** | Välj det här alternativet om du vill lägga en vattenstämpel ovanpå dina utdata. Du kan ange en ny textsträng i textrutan med en teckenplacering som du vill. <br><br>Använd statisk text eller språkvariabler för att publicera den lokaliserade versionen av vattenstämpeln.  Beroende på vilket språk du väljer hämtas det lokaliserade värdet automatiskt i utdata från PDF. Du kan t.ex. skriva ut&quot;Utgivare&quot; som en vattenstämpel på engelska och&quot;Autentisering&quot; på franska.  <br>-format: `${lng:<variable name>}`. `$ {lng:publisher-label}` där `publisher-label` är en språkvariabel. <br> Hovra över <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära alternativet om du vill visa mer information om det. |
| **Aktivera MathML-ekvationer** | Välj det här alternativet om du vill återge MathML-ekvationer i innehållet. Ekvationerna ignoreras annars som standard. |
| **Hämta temporära filer** | Markera det här alternativet om du vill hämta de mellanliggande HTML-filer som skapas när utdata för PDF skapas. Du kan hämta de tillfälliga filerna senare när du har genererat utdata. |
| **PDF-överensstämmelse** | Det är den standard som du tänker spara PDF för att säkerställa att den är kompatibel. Välj i listrutan om du vill välja i listan över tillgängliga PDF-standarder. Mer information om vilka standarder som stöds finns i [Om PDF-standarder](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Filegenskaper** | Markera de metadata som du vill skicka till Native PDF. I listrutan visas både de anpassade egenskaperna och standardegenskaperna. Till exempel är `dc:description`, `dc:language`, `dc:title` och `docstate` standardegenskaper medan du kan ha `author` som anpassad egenskap. De markerade metadataegenskaperna skickas till PDF-filen som skapats med PDF. <br> De här egenskaperna hämtas från `metadataList`-filen som är tillgänglig på:`/libs/fmdita/config/metadataList`. <br>Den här filen kan överlappas: `/apps/fmdita/config/metadataList`. |


## Generera utdata för PDF {#generate-pdf-output}

När du har konfigurerat förinställningen kan du generera utdata från panelen Förinställningar med funktionen **Generera förinställning** .

1. Under fliken **Författare** väljer du vyn **Databas** .\
   Databaspanelen öppnas.

1. Öppna DITA-mappningsfilen i **Kartvyn** på databaspanelen.

1. Klicka på **Förinställningar** på fliken **Utdata** för att visa panelen Förinställningar.
Mer information om hur du skapar eller konfigurerar en förinställning för utdata finns i [Skapa en förinställning för PDF](#create-output-preset).
1. Om du vill spara inställningarna klickar du på ikonen **Spara alla** ![spara alla](assets/SaveFloppy_icon.svg) i det övre vänstra hörnet av standardverktygsfältet i utdatavyn.
1. Klicka på ikonen **Generera förinställning** ![generera förinställning](assets/generate-output.svg) i det övre fältet.
Du kan visa en förloppsindikator bredvid den valda förinställningen på panelen Utdatainställningar.
1. När utdatagenereringen är klar klickar du på ikonen **Visa utdata** ![visa utdata](assets/view-output.svg) i det övre fältet för att visa utdata.\
   En dialogruta **Slutfört** visas längst ned till höger på skärmen.
Om utdata inte lyckas visas felmeddelandet nedan.
<img src="assets/error-log.png" alt="fellogg" width="250">

Om du vill visa felloggen klickar du på **Stäng**, håller pekaren över den valda förinställningsfliken och klickar på ![Alternativ](assets/options.svg) **Alternativ** > **Visa logg**.

### Ladda ned temporära filer när du har genererat Native PDF

Om du väljer alternativet **Hämta temporära filer** i de avancerade inställningarna kan du även hämta de temporära HTML-filer som skapas när du genererar utdata för PDF. När du har genererat utdata kan du hämta de tillfälliga filerna med ikonen **Hämta temporära filer** ![Hämta temporära filer](assets/native-pdf-download-temporary-files-icon.svg)i det övre fältet. Med den här funktionen kan du visa dina tillfälliga HTML-format och -layouter och du kan korrigera eller ändra dina CSS-format efter dina behov.


>[!NOTE]
>
> Ikonen **Hämta temporära filer** ![Hämta temporära filer](assets/native-pdf-download-temporary-files-icon.svg) visas bara om du har genererat de senaste PDF-utdata med den förinställning där du har valt alternativet på fliken **Avancerat** .



### Använd språkvariabler

AEM Guides har också stöd för språkvariabler. Välj **språkvariabler** <img src="./assets/language-variables.svg" width="25"> i den vänstra panelen om du vill definiera en lokaliserad version av de körklara etiketterna som Anteckning, Varning och Varning eller statisk text i utdata från PDF. Mer information finns i [Stöd för språkvariabler](../native-pdf/native-pdf-language-variables.md).



### Stöd för markeringsdokument

Experience Manager Guides har också stöd för dina Markdown-dokument.  Markeringsfiler är enkla att skapa och även
innehåller en mängd formateringsalternativ. Lär dig hur du [redigerar Markdown-dokument från webbredigeraren](../user-guide/web-editor-markdown-topic.md).

Du kan lägga till Markdown-avsnitten på DITA-kartan och generera utdata för PDF med hjälp av de inbyggda PDF-utdatainställningarna.  Lär dig hur du konfigurerar eller [skapar en förinställning för utdata från PDF](#create-a-pdf-output-preset-create-output-preset).