---
title: Publiceringsfunktion för PDF | Komponenter i en PDF-mall
description: Lär dig de olika komponenterna i en PDF-mall och hur du anpassar och konfigurerar dem.
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '4975'
ht-degree: 0%

---

# Komponenter i en PDF-mall {#components-pdf-template}

En PDF-mall har fyra komponenter: Sidlayouter, Formatmallar, Resurser och Inställningar. Du kan skapa en mall genom att anpassa de här enskilda komponenterna och koppla mallen till en förinställning för utdata när du genererar utdata för PDF. I följande avsnitt beskrivs dessa komponenter och deras anpassningsprocess i detalj.


## Skapa och anpassa sidlayouter {#create-customize-page-layout}

Med inställningarna i komponenten Sidlayout kan du utforma strukturen för en sida genom att definiera sidhuvudet, sidfoten och innehållsområdet på en sida. Med layoutredigeraren i WYSIWYG kan du skapa en sidlayout för olika avsnitt i en PDF, t.ex. framsidan och baksidan av försättsbladet, kapitel, innehållsförteckning (TOC), index, tom sida, framsidan av sidorna, baksidan av sidorna, figurlistan (LOF), listan över tabeller (LOT), ordlistan eller skapa en layout för en anpassad sida. I mallinställningarna för PDF kan du tilldela en sidlayout med olika avsnitt i PDF, som sedan används för att generera utdata från PDF.

### Skapa en ny sidlayout {#create-page-layout}

>[!NOTE]
>
>Det finns exempelsidlayouter som levereras utanför kartongen. Du kan anpassa dessa eller skapa nya sidlayouter.

1. Gå till webbredigeraren **Utdata** -fliken.
1. Expandera den vänstra sidlisten och klicka **Mallar**.
1. Öppna mallen som du vill arbeta med.

   >[!NOTE]
   >
   >Du kan öppna en mall genom att dubbelklicka på dess namn eller klicka på >-ikonen bredvid dess namn.

1. Om du vill skapa en ny sidlayout gör du något av följande:

   * Hovring **Sidlayouter** och klicka på&#x200B;*Alternativ* ikon) **...** och välja **Ny sidlayout**.


   * I **Mallar** klickar du på **+** ikon bredvid **Mallar** och välja **Sidlayout** på snabbmenyn.


     Då öppnas **Lägg till layout** -dialogrutan.

     <img src="assets/add-layout-2.png" alt="Dialogrutan Lägg till layout" width="250">

1. Ange ett namn för den nya sidlayouten.
   >[!NOTE]
   >
   >Undvik att använda specialtecken när du namnger en sidlayout. Ett blanksteg i namnet ersätts med understrecket&quot;_&quot;.

1. Klicka **Klar**.

   Den nya layouten skapas och läggs till under Sidlayouter.


### Duplicera en sidlayout {#duplicate-page-layout}

1. I **Mallar** i mallen som du vill duplicera dubbelklickar du  **Sidlayouter** eller klicka på **>** ikon före **Sidlayouter**.

   Då visas en lista med sidlayouter i mallen.

1. Håll pekaren över den sidlayout som du vill duplicera och klicka på (*Alternativ* ikon) **...** och markera **Duplicera** på snabbmenyn.

1. I _Duplicera layout_ anger du ett namn för sidlayouten.

1. Klicka **Klar**.
En kopia av den valda sidlayouten skapas och läggs till under Sidlayouter.

### Anpassa en sidlayout {#customize-page-layout}

1. I **Mallar** i mallen som du vill redigera dubbelklickar du **Sidlayouter** eller klicka på **>** ikon före **Sidlayouter**.

   Då visas en lista med sidlayouter i mallen.
1. Gör något av följande om du vill anpassa en sidlayout:
   * Dubbelklicka på en sidlayout.
   * Håll pekaren över en sidlayout och klicka på (*Alternativ* ikon) **...** och markera **Redigera** på snabbmenyn.

   Då öppnas sidlayoutredigeraren för anpassning.
1. När du har gjort ändringarna klickar du på *Spara alla* (eller `Crl+S`).

   Mer information om hur du definierar enskilda layoutelement som sidhuvud, sidfot, sidnummer, rubrik med mera finns i [Designa en sidlayout](design-page-layout.md).

## Anpassa PDF med formatmallar {#stylesheet-customization}

Med inställningarna i formatmallskomponenten kan du formatera sidlayoutskomponenterna och DITA-innehållet med WYSIWYG-redigeraren eller arbeta direkt med CSS-filen. Du kan skapa egna format eller anpassa standardformategenskaperna. WYSIWYG-redigeraren ger dig tillgång till de flesta egenskaper som du behöver för att formatera din sidlayout eller DITA-innehåll. För avancerade anpassningar kan du arbeta direkt i källvyn.

### Skapa en ny formatmall {#create-stylesheet}

CSS-filer tillhandahålls för innehåll och layout, men du kan skapa en ny formatmall som använder flera anpassningar för en viss formattyp som sedan kan användas för en målkomponent. Som standard paketeras CSS-exempelfiler i produkten. Dessa CSS-filer är avsedda att hjälpa dig att ordna formatinformation för innehåll och layout. Du kan välja att sammanfoga dessa format i en eller flera CSS-filer.

När du skapar en ny sidlayout är `layout.css` filen inkluderas i den nya sidlayouten. Om du vill att sidlayouten ska innehålla format från en annan CSS-fil kan du helt enkelt dra och släppa önskad CSS-fil i den nya sidlayoutens innehållredigeringsområde. Om du vill verifiera om CSS-filen har bäddats in i sidlayouten växlar du till källvyn så att du hittar en länk till CSS-filen i `<head>` -element.


Så här skapar du en formatmall:
1. I **Mallar** gör du något av följande:
   * Hovra över **Formatmallar** och klicka på (*Alternativ* ikon) **...** och välja **Ny formatmall**.
   * Klicka på **+** ikon bredvid **Mallar** och välja **Formatmall** på snabbmenyn.

   Dialogrutan Lägg till formatmall öppnas.

   <img src="assets/add-stylesheet.png" alt="Lägg till formatmall" width="250">
1. Ange ett namn för den nya formatmallen.
1. Klicka **Klar**.

   En ny formatmall skapas och läggs till under formatmallsavsnittet.

### Skapa ett nytt format {#create-style}

Som standard innehåller CSS-filerna som finns i mallen format för rubriker, stycken, tecken, hyperlänkar, bilder, tabeller, div, sidor och andra format. Du kan åsidosätta standardformatet eller skapa ett nytt format.


Du kan skapa ett nytt format och använda det i mallens sidlayout eller använda ett anpassat format för ett DITA-element. Om du vill använda dessa anpassade format på DITA-elementet måste du se till att formatets klassnamn är detsamma som DITA-elementets namn eller `outputclass` -attribut.  Till exempel: `<div>` i DITA styrs av `.div {}` i CSS eller `outputclass` -attribut. Om du använder `<div outputclass="my-div">` i DITA styrs den av `.div {}` eller `.my-div {}` i CSS.



Så här skapar du ett nytt format:
1. Expandera den vänstra sidlisten och dubbelklicka på mallen som du vill skapa formatet i.
1. Expandera **Formatmallar** -avsnitt. Den öppnar **Stilar** som innehåller alla formateringsalternativ.
1. Välj ikonen + om du vill lägga till ett nytt format.

   **Lägg till format** öppnas.


   <img src="assets/add-style.png" alt="Lägg till nytt format" width="500"/>

1. Ange en **Klass** namn. Om du vill använda ett format på DITA-elementet kontrollerar du att formatets klassnamn är detsamma som DITA-elementets namn eller `outputclass` -attribut.
1. I **Tagg** väljer du ett märkord som du vill skapa ett nytt format för (valfritt).


1. Välj en **Pseudo-klass** om du vill formatera ett element. Med en pseudoklass kan du definiera ett speciellt läge för elementet. Använd till exempel pseudoklassen för att formatera ett element när du håller muspekaren över det eller när du fokuserar över det. Du kan också välja flera pseudoklasser. Du kan till exempel använda pseudoklassen `a::visited {color: blue;}` för att utforma besökta länkar.

1. Lägg till väljaren för det nya formatet. The **Väljare** I kan du lägga till anpassade väljare förutom kombinationen Klass, Tagg och Pseudo-klass. Du kan till exempel skapa `table a.link` format för alla hyperlänkar i en tabell.

   Mer information om CSS-taggar finns i [Se grammatik i CSS-format](https://www.w3.org/TR/CSS21/syndata.html#characters).

1. Klicka **Klar**.

   Ett nytt format skapas och läggs till i formatlistan.

### Anpassa ett fördefinierat eller nytt format {#customize-style}

När du har skapat en ny CSS-fil med standardformat eller vill anpassa format i en befintlig CSS-fil kan du använda formatredigeraren för att göra det.

Följ stegen nedan för att anpassa en stil:
1. Dubbelklicka **Formatmallar** eller klicka på **>** ikon före **Formatmallar**.

   Detta visar standardfilerna (Innehåll och layout) och anpassade CSS-filer.
1. Öppna en formatmall för redigering.

   Gör något av följande om du vill öppna en formatmall för redigering:
   * Dubbelklicka på formatmallens namn.
   * Håll muspekaren över formatmallens namn och klicka på (alternativikonen) ... och välj Redigera.

   Då öppnas formatmallen för redigering och formatlistan visas på formatpanelen.

   <img src="assets/customize-style.png" alt="Anpassa stil" width="800">

1. Om du vill anpassa ett format markerar du det för att visa och anpassa det med stilredigeraren.


### Egenskaper för format

I mittpanelen kan du redigera egenskaperna, men det kan vara svårt att få en ögonblicksbild av vilka värden som finns.  The **Egenskaper** I visas alla attribut och värden för formatet.

På mittpanelen kan du redigera de vanligaste egenskaperna, men inte alla de egenskaper som CSS stöder. I **Egenskaper** kan du redigera alla egenskaper som CSS har stöd för och förhandsgranska dem. Du behöver inte växla till källvyn för att redigera några egenskaper.


Läs mer om hur du använder formateditorn för att [arbeta med vanliga innehållsformat](stylesheet.md).

## Arbeta med resurser {#work-with-resources}

Detta är en behållare för alla resurser som används för att utforma en mall. Du kan tänka dig det som en mapp som innehåller resurser som bakgrundsbilder, anpassade teckensnitt, logotyper med mera. När du lägger till en resurs i mallen överförs den eller checkas in i resursmappen. Du kan sedan använda dessa resurser för att anpassa eller utforma dina PDF-mallar.

Följ stegen nedan för att lägga till en resursfil i resursmappen:

1. Håll muspekaren över fliken Resursmapp, klicka på (alternativikonen) ... och välj Importera.

   Dialogrutan Överför resurser öppnas.

   <img src="assets/resources-import-assets.png" alt="Överför resurser" width="300">

   Sökvägen dit resursfilen ska överföras visas i **Välj resursmapp** fält.
   >[!NOTE]
   >
   >Du kan inte ändra sökvägen för överföring av resurser. Som standard lagras alla resurser under `/content/dam/dita-templates/pdf/<PDF-template-name>` mapp.

1. Klicka **Välj filer** för att bläddra i resursfilen från din lokala dator

1. Klicka **Överför**.
Den valda filen importeras och visas under mappen Resurser.

## Avancerade PDF-inställningar {#advanced-pdf-settings}

Använd avsnittet Inställningar för att konfigurera de avancerade inställningarna för sidlayout, med början från PDF från udda eller jämn PDF, format för korsreferenserna och aktivering av utskriftsmärken i det slutliga PDF som genereras med mallen.

Konfigurera genom att klicka på **Inställningar** i **Mallar** för att visa följande alternativ:

### Allmänt

Ange de grundläggande konfigurationsinställningarna för att starta ett kapitel från udda eller jämn sida, innehållsförteckningsstrukturen och definiera ledarradformatet för posterna i innehållsförteckningen. Du kan definiera följande inställning:

* **Starta ett nytt kapitel från**: Används för att definiera hur varje kapitel ska publiceras i den slutliga PDF. Du kan välja bland en **Ny sida**, **Udda sida**, **Jämn sida**, eller **Aktuell sida**  alternativ. Om du väljer att starta ett nytt kapitel från en udda sida infogas en tom sida efter ett kapitel som slutar på en udda sida. Om kapitlet avslutas på sidan 15 infogas ett tomt nummer 16<sup>th</sup> så att det nya kapitlet kan börja från 17<sup>th</sup> sida.  Om du väljer **Aktuell sida** så publiceras alla kapitel utan sidbrytningar. Om ett kapitel t.ex. avslutas mitt på sidan 15, kommer nästa kapitel också att startas från den 15:e sidan.

* **Starta varje ämne från en ny sida**: Om du vill att varje ämne i kapitlet ska börja från en ny sida väljer du **Starta varje ämne från en ny sida** alternativ. Om du vill att dina ämnen ska fortsätta utan sidmellanrum avmarkerar du det här alternativet.

* **Innehållsförteckningsstruktur**: Används för att anpassa innehållsförteckningens hierarki. Följande ytterligare inställningar används:

   * **Använd rubriker upp till nivå**: Du kan justera antalet rubriknivåer som ska visas i innehållsförteckningsstrukturen på PDF.
   * **Visa inte sidnummer för den första nivån i innehållsförteckningen**: Välj det här alternativet om du vill dölja motsvarande sidnummer för alla kapitel som innehåller kapslade eller underordnade ämnen. Titta på följande exempel där en utdatafil skapas utan att markera det här alternativet.

  <img src="assets/page-number-in-toc.png" alt="Överför resurser" width="250">

  I ovanstående exempel är Avancerade PDF-inställningar, Bilaga och Legal ämnesrubriker på första nivån eller kapitelrubriker. Alla rubriker tilldelas ett sidnummer.

  Om du väljer det här alternativet och genererar utdata får du nu följande innehållsförteckning:

  <img src="assets/page-number-missing-in-toc.png" alt="Överför resurser" width="250">

  Här ser du att det första kapitlet Avancerade PDF-inställningar inte får något sidnummer, som det har kapslade eller underordnade avsnitt. Ett sidnummer om det tilldelas till Bilaga och Rättslig information eftersom de är fristående ämnen utan något underordnat ämne.

* **Visa inte kapitelnummer i innehållsförteckningen** : Välj det här alternativet om du vill visa kapitelnamnen utan kapitelnumren i innehållsförteckningen.   Som standard visas kapitelnumren i innehållsförteckningen för dina PDF-utdata.
* **Ledarformat**: Använd listrutan för att välja prickade, heldragna eller mellanslag för att koppla rubriknivåer till motsvarande sidnummer.
Information om hur du använder rubriknivåer för innehållsförteckningens struktur och format finns i [Lägga till en kapitelinnehållsförteckning](design-page-layout.md#add-chapter-toc).

  >[!NOTE]
  >
  >Om du är CSS-utvecklare kan du definiera ledarformatet direkt i CSS-filen också.

* **Använd fortsättningsmarkör för register**: Välj det här alternativet om du vill definiera markörer för långa tabeller som sprids över flera sidor.
Du kan definiera texten som ska visas före och efter brytningen. En tabell bryts till exempel på sidan 5 och du definierar `<Continued on page %page-num%>` for **Text före brytning**.  Texten visas&quot;Fortsättning på sidan 6&quot; längst ned på sidan 5.

  Använd språkvariabler för att definiera fortsättningsmarkörtexten före och efter brytningen. Beroende på vilket språk du väljer hämtas det lokaliserade värdet automatiskt i utdata från PDF. Du kan till exempel publicera `Continued on page %page-num%` som en text på engelska och `Fortsetzung auf Seite %page-num%` på tyska.

  Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära alternativet om du vill visa mer information om det.
* **Länka ordlistetermer till ordbokssidan**: Välj det här alternativet om du vill visa ordlistorna som hyperlänkar i innehållet och länka dem till termerna på ordlistan. Det gör att läsarna snabbt kan se definitionen av en term som definierats i ordlistan.

  Om du vill konvertera ordlistan till hyperlänkar måste du:
   * Aktivera **Ordlista** i **Layoutordning** för en DITA-karta.
   * Lägg till ordlistan på sidan Bakåt Matcha sidor för en bokkarta.

  Om du inte aktiverar ordbokssidan konverteras inte de ordlistliga termerna i innehållet till hyperlänkar i utdata från PDF.
  <!--For more information on using table continuation markers, see Use table continuation markers.-->

### Sidlayouter {#page-layouts}

Inställningarna för sidlayout ger dig fullständig kontroll över hur du anger vilken sidlayout som ska användas för ett visst avsnitt i dokumentet. Om du till exempel vill välja en layout för innehållsförteckningen klickar du på listrutan under innehållsförteckningsfältet och väljer den layout som du har utformat för att generera innehållsförteckningen.

Observera att bokmappsinställningarna har företräde framför sidlayoutsinställningarna.

Följande inställningar är tillgängliga under avsnittet Sidlayout:

<img src="assets/template-page-layout.png" alt="Sidlayouter" width="550">


**Standardsidlayout**: Välj en sidlayout som fungerar som standardlayout för alla sidor i PDF. Det här är den grundläggande sidlayouten som används i avsnitt eller ämnen där du inte har skapat en dedikerad sidlayout.

**Sidlayout för olika avsnitt**: Du kan mappa en sidlayout med följande avsnitt av utdata från PDF. Om du har utformat en sidlayout för det relaterade avsnittet väljer du det i listrutan. Om ingen sidlayout har skapats för ett visst avsnitt används standardsidlayouten.

* **Kapitel och ämnen**: Du kan ange sidlayout för kapitlet och avsnitten. Den valda layouten används för alla kapitel och avsnitt.

* **Innehåll**: Om du har utformat sidlayouten för innehållsförteckningen väljer du **Innehåll** i listrutan och alla innehållsförteckningssidor i dokumentet kommer att ha sidlayouten för innehållsförteckningen.

* **Figurförteckning och förteckning över tabeller**: Du kan också ange sidlayout för figurer och tabeller. Den valda layouten används på alla figurer och tabeller.

* **Index**: Om du har utformat en indexsidlayout kan du mappa den till alternativet Index. Med formatmallarna kan du formatera olika indexelement i utdata från PDF. Använda indexformat `.idx-header`, `.idx-footer`, `.idx-body`, `.idx-title`, `.idx-keyword-group`, `.idx-unit`,  `.idx-keyword`, `.idx-name`, `.idx-link` och `.idx-child` om du vill anpassa formaten för indexelementen.

* **Ordlista**: Om du har en ordlista mappas den till alternativet Ordlista.

  Termerna i ordlistan för dina PDF-utdata sorteras alltid i alfabetisk ordning.

  Du kan också lägga till taggen `sort-as` om du vill definiera en sorteringsnyckel för ordlistorna. Stödlinjerna i Experience Manager använder sedan sorteringsnyckeln för att sortera de ordlistor som ersätter de ordlistor som används. Om du inte har definierat sorteringsnyckeln används ordlistetermer för sortering. Du kan till exempel lägga till taggen `sort-as` till `glossterm` och ange värdet till `A` för termen &quot;USB&quot; (till exempel `<glossterm>USB<sort-as>A</sort-as></glossterm>`). På samma sätt kan du lägga till `sort-as` tagga och ange dess värde som `B` för termen &quot;Pen Drive&quot;. När du sorterar de här ordlistorna används sorteringsnyckeln `A` för ordlistan visas &quot;USB&quot; före sorteringsnyckeln `B` i ordlistan &quot;Pen Drive&quot;. I utdata från PDF kommer &quot;USB&quot; före &quot;Pen Drive&quot; på ordlistan.

  Med formatmallarna kan du formatera olika ordlisteelement i utdata från PDF. Använda ordlisteformat `.glo-header`, `.glo-footer`, `.glo-body`, `.glo-title`, `.glo-unit`, `.glo-link`och `.glo-term` om du vill anpassa formaten för ordlistans element.

  Läs mer om hur du använder formateditorn för att [arbeta med vanliga innehållsformat](stylesheet.md).

* **Sidor med inledande och bakre innehåll**: Dessa sidlayouter definierar formatet för framsidan eller baksidan av boken. Om du har utformat layouten på framsidan kan du mappa den till **Front Matter Pages** alternativ. När du väljer layouten på framsidan i listrutan används layouten på alla ämnen som finns på framsidan.

  Om du har utformat bakomliggande layout kan du mappa den till **Bakåt - viktiga sidor** alternativ. När du väljer bakgrundslayout i listrutan används bakomliggande layout på alla ämnen som finns i bakgrunden.

  **Front Matter Pages** används också som grundlayout för **Innehåll**, **Lista över figurer** och Lista över tabeller.  På samma sätt **Bakåt - viktiga sidor** används också som grundlayout för **Index** och **Ordlista** layouter. Om du inte har valt layouten för dessa används den valda layouten för fram- eller bakåtsidor.  Om du inte har valt layouten för sidhuvud och baksida tillämpas standardsidlayouten på dem.

* **Sidlayout för tomma sidor**: Du kan också ange sidlayout för de tomma sidorna. Den valda layouten används på alla tomma sidor. Om du till exempel har utformat en tom sidlayout för alla tomma sidor väljer du **Tom** i listrutan och alla tomma sidor i dokumentet har en tom sidlayout.

* **Försättsblad och Baksida**: Om du har utformat en omslagssidlayout kan du mappa den till **Försättsblad** alternativ. Om du har en baksideslayout kopplar du den till **Baksida** alternativ. Om ingen layout för omslag eller baksidor har skapats används standardsidlayouten.



Mer information om sidlayouter finns i [Designa en sidlayout](design-page-layout.md).

### Layoutordning {#page-order}

Du kan visa eller dölja följande avsnitt i PDF och även ordna i vilken ordning de ska visas i det slutliga PDF-resultatet:



* Innehåll
* Kapitel och ämnen
* Lista över figurer
* Lista över tabeller
* Index
* Ordlista
* Citat

  <img src="assets/page-order-advance-settings.png" alt="Layoutordning" width="550">

  Om du inte vill visa ett visst avsnitt i utdata för PDF kan du dölja det genom att stänga av växlingsknappen.

  Du kan också ange i vilken ordning de olika avsnitten ska genereras i PDF. Om du vill ändra standardordningen för de här avsnitten markerar du de prickade strecken för att dra och släppa avsnitten på önskad plats.

  >[!NOTE]
  >
  > Inställningarna för ordning och inkludering gäller bara för en DITA-karta. Dessa inställningar gäller inte för bokmappar. Sidorna i en bokmapp visas enligt ordningen i avsnitten i bokmappen.


.
**Kapitel och ämnen** layout är alltid aktiverat som standard. Du kan inte växla den.

**Sammanfoga sidor**

Som standard börjar alla avsnitt på en ny sida. Välj **Föregående sida** eller **Nästa sida** från **Sammanfoga med** för att sammanfoga ett avsnitt med en föregående eller nästa sida. Detta kommer att publicera avsnittet tillsammans med den valda sidan i utdata från PDF. Med det här blir det ingen sidbrytning däremellan.

>[!NOTE]
>
> Den här inställningen gäller endast avsnittet och inte dess komponenter.  Om du t.ex. väljer **Föregående sida** alternativ för **Kapitel och ämnen**, **Kapitel och ämnen** -avsnittet sammanfogas med föregående sida. De olika kapitlen och ämnena publiceras enligt **Allmänt** settings.T.ex. om **Starta ett nytt kapitel från inställningen** väljer du **Udda sida** infogas en tom sida efter ett kapitel som slutar på en udda sida.

När du sammanfogar ett avsnitt till föregående eller nästa sida sammanfogas innehållet och formatet för målavsnittet där innehållet sammanfogas används.

Om du till exempel aktiverar **Innehåll** och **Kapitel och ämnen** och väljer **Nästa sida** for **Innehåll**, **Innehåll** sammanfogar med nästa avsnitt, som är **Kapitel och ämnen**. Formatet på **Kapitel och ämnen** -avsnittet används på det sammanfogade innehållet i båda avsnitten.

Sammanfogningsalternativet fungerar stegvis, så om du har valt **Nästa sida** för flera sammanhängande avsnitt sammanfogas de alla med det första avsnittet (i nästa riktning), som inte har den här egenskapen inställd. Du kan till exempel aktivera **Innehåll**, **Kapitel och ämnen**, **Lista över figurer** och **Index**. Om du sedan anger **Nästa sida** for **Innehåll**, **Kapitel och ämnen**, **Lista över figurer** och **Ingen** for **Index** sammanfogar de alla med  **Index**.


**Statiska sidor**

De olika sidlayouterna hjälper dig att utforma utdata från de olika avsnitten. Dessa avsnitt genereras från DITA-kartan när du publicerar utdata.
Du kan också skapa anpassade sidlayouter och publicera dem som statiska sidor i utdata från PDF. Detta hjälper dig att lägga till statiskt innehåll som anteckningar eller tomma sidor.

Utför följande steg för att lägga till en anpassad sidlayout:

1. Välj **Lägg till** ![](assets/add-icon.svg) för att lägga till en ny sidlayout. Panelen Lägg till sidlayout öppnas.
2. Markera sidlayouten i listan och klicka på Lägg till. Den nya sidlayouten läggs till i listan över sidlayouter.


Du kan även utföra följande åtgärder:

* Markera de prickade strecken för att dra och släppa sidlayouten på önskad plats.

* Välj **Ta bort layout** ![](assets/delete-icon.svg)  för att ta bort en layout.

* Du kan också sammanfoga en statisk sida med föregående sida eller nästa sida.

* Du kan också lägga till en anpassad layout flera gånger och ordna dem. Det gör att du kan publicera statiskt innehåll i enlighet med detta.

  Du kan till exempel använda en anpassad layout för att publicera en statisk varning flera gånger i PDF-utdata.



### Sidorganisation

Sidorna i ett PDF-dokument publiceras vanligtvis enligt det innehåll som är organiserat i DITA-kartan eller bokmappsfilen. Du kan också ändra ordningen på sidorna i PDF-dokumentet. Du kan till exempel skriva ut ett flersidigt dokument som ett häfte. När du sorterar, viker och häftar arken blir resultatet en enda bok med rätt sidordning.  Sedan kan du läsa det publicerade häftet som en bok.

<img src="assets/template-page-organization.png" alt="Sidorganisation" width="550">


Följande inställningar är tillgängliga under **Sidorganisation** avsnitt:

#### Sidordning

Välj en sidordning som bestämmer sidordningen i PDF-dokumentet. Du kan välja följande alternativ i listrutan:

* **Standard**: Standardordningen för sidorna enligt källfilen.
* **Udda sidor först**: Alla udda sidor flyttas före alla jämna sidor.
* **Jämna sidor först**: Alla jämna sidor flyttas före alla udda sidor.
* **Invertera**: Sidordningen inverteras.
* **Häfte**: Alla sidor ordnas som i ett häfte.
* **Häfte från höger till vänster**: Alla sidor är i häftesordning från höger till vänster.
* **Egen**: Definiera en anpassad sidordning i stället för en fördefinierad ordning.
   * &quot;a..b&quot; - Alla på varandra följande sidor från a till b.
   * &quot;a,b,c&quot; - Ny sidordning a, b, c.
   * &quot;a*b&quot; - Sidan a upprepas b gånger.
   * &quot;-a&quot; - Negativa sidnummer räknas bakåt från den sista sidan och kan kombineras med andra anpassade ordningsnummer.
   * &quot;X&quot; - Alla sidor i dokumentet. Samma resultat som &quot;1..-1&quot;.

Du kan t.ex. skapa en anpassad ordning som &quot;2,3,5*2,7.10,-1,-2.
Den angivna sidordningen resulterar i att PDF har följande sidnummer från det ursprungliga dokumentet, förutsatt att det har totalt 25 sidor: 2, 3, 5, 5, 7, 8, 9, 10, 25, 24.

#### Konfigurera mer än en sida per ark

Välj det här alternativet om du vill publicera flera sidor på ett enda pappersark.  Markera sedan antalet rader och kolumner och publicera sidorna som ett rutnät på ett enda ark. Du kan till exempel publicera sidorna som ett rutnät med 2 rader och 4 kolumner.

Definiera målarkets storlek och den orientering i vilken du vill publicera kalkylbladet. Du kan också ange marginal- och utfyllnadsegenskaperna för bladet.




### Skriv ut

Konfigurera utskriftsinställningarna för att tilldela skrivarmärken, välja färgmodeller och ange egenskaper för utskrift av PDF.

* **Skrivarmärken**: När du förbereder ett dokument för tryckproduktion läggs skrivarmärken till på sidgränserna för att underlätta korrekt justering, beskärning och färgval vid utskrift. Genom att välja ett skrivarmärke utökas sidgränsen så att den passar markeringen, som beskärs vid utskrift. Du kan välja att visa följande skrivarmärken i utdata från PDF:
   * **Ytmärken**: Välj alternativet att placera ett märke i varje hörn av det beskurna området för att ange var papperet behöver beskäras efter utskrift.
   * **Utfallsmärken**: Välj det här alternativet om du vill placera ett märke i varje hörn av utfallsrutan för att ange den utökade bildens ytområde.
   * **Registreringsmärken**: Välj det här alternativet om du vill placera ett märke utanför beskärningsområdet för att justera de olika separationerna i ett färgdokument.
   * **Färgremsor**: Välj det här alternativet om du vill lägga till en rad färger utanför det trimningsbara området för att bibehålla en konsekvent färg och justera tryckfärgens densitet vid utskrift.

  Ange mått för de valda skrivarmärkena med hjälp av **Linjebredd**, **Linjefärg** och **Bredd på utfallsruta** alternativ.

* **Media Box-storlek**: Detta är den totala sidstorleken inklusive utökat område som används av skrivarmärken. Använd rullgardinsmenyn för att välja sidstorlek för utdata från PDF eller skapa en egen anpassad storlek.

* **Färgmodell**: Du kan välja mellan RGB eller CMYK-färgrymder för att skriva ut PDF-dokumentet. Välj RGB om du vill visa det genererade PDF digitalt och CMYK för fysisk utskrift. Färger som definieras i dokumentet konverteras till den valda färgrymden.
  >[!NOTE]
  >
  >En ICC-färgprofil krävs för att skapa PDF/A om CMYK-färgmodellen används.

  <!--For more information on applying these print settings, see *Printing preferences*.-->

### Korsreferenser {#cross-references}

Använd **Korsreferens** för att definiera hur korsreferenserna ska publiceras i PDF. Du kan formatera korsreferenserna för ämnesrubrik, tabeller, figurer och mycket annat.

>[!NOTE]
>
> Om du har definierat länktexten när du infogar korsreferensen, prioriteras den framför korsreferensformatet som har definierats i mallen för PDF.

Du kan också använda variabler för att definiera en korsreferens.  När du använder en variabel hämtas dess värde från egenskaperna. Du kan använda en enda eller en kombination av variabler för att definiera en korsreferens. Du kan också använda en kombination av en sträng och en variabel.

Du kan till exempel använda `View details on {chapter}`. Om kapitelnamnet är &quot;Allmänna inställningar&quot; är korsreferensen i utdata &quot;Se information om Allmänna inställningar&quot;.

AEM innehåller följande variabler:

* {title}: Skapar en korsreferens till ämnestiteln. Exempel: Se Användbara länkar på sidan 2.
* {page} Lägger till en korsreferens till sidnumren. Se till exempel på sidan 1.
* {description}: Lägger till en korsreferens till texten i beskrivningen. Se t.ex. information om AEM.
* {chapter}: Lägger till en korsreferens till kapitelnumren. Se till exempel Kapitel 1.
* {bookmarkText}: Skapar en korsreferens till den bokmärkta texten. Se till exempel stop_words på sidan 5.
* {captionText}: Skapar en korsreferens till bildtexten för figuren eller tabellen i ditt ämne. Se till exempel Luftflöde på sidan 2.
* {figure}: Lägger till en korsreferens till bildnumret. Hämtar nummertalet från de automatiska nummerformat som du har definierat för bildtext.  Du kan till exempel använda &quot;Se {figure} på sidan {page}&quot;. Korsreferensen i utdata innehåller det automatiskt genererade bildnumret och dess sidnummer, &quot;Se figur 1 på sidan 5&quot;.
* {table}: Lägger till en korsreferens till tabellnumret. Hämtar tabellnumret från de automatiska nummerformat som du har definierat för bildtext. Du kan till exempel använda &quot;Se {table} på sidan {page}&quot;. Korsreferensen i utdata innehåller det automatiskt genererade tabellnumret och dess sidnummer, &quot;Se tabell 1 på sidan 5&quot;.



  >[!NOTE]
  >
  >Du kan skapa automatiska nummerformat för bildtext- och bildtexttaggar.

#### Standardkorsreferensformat

Om du låter textfältet vara tomt och du inte har definierat länktexten när du infogar en korsreferens, läggs följande variabler till i Experience Manager-stödlinjerna för respektive korsreferens:

* **Titel**: `{title}`
* **Beskrivning**: `{description}`
* **Stycke**: `{bookmarkText}`
* **Bokmärke**: `{bookmarkText}`
* **Figur**: `{captionText}`
* **Tabell**: `{captionText}`

Prioritetsordningen för korsreferenser är:
* Länktext i korsreferenserna
* Korsreferensformat som definieras i mallen för ursprungliga PDF
* Standardkorsreferensformat


#### Språkvariabler i korsreferenser

Du kan också använda språkvariabler för att definiera lokaliserade korsreferenser. Beroende på vilket språk du väljer hämtas det lokaliserade värdet automatiskt i utdata från PDF.

Du kan till exempel lägga till en språkvariabel,&quot;reference-label&quot;, och definiera värdena på engelska och tyska.

* Engelska -&quot;Visa på sidan {page}&quot;
* Tyska -&quot;Einzelheiten finden Sie auf der Seite {page}&quot;


När du lägger till `${lng:<variable name>}` till avsnittet Stycke innehåller korsreferenserna i styckena i utdata den lokaliserade texten och sidnumret.\
På följande skärmbilder visas korsreferenserna &quot;Visa på sidan 1&quot; på engelska och &quot;Einzelheiten finden Sie auf der Seite 1&quot; på tyska.

<img src="./assets/english-output-corss-reference.png" alt="Engelska utdata för en korsreferens i en pragrah" width ="800" border="2px">

*En korsreferens i ett stycke när den publiceras på engelska.*

<img src="./assets/german-output-corss-reference.png" alt="Tyska utdata av en korsreferens i en pragrah" width ="800" border="2px">


*En korsreferens inom ett stycke när den publiceras på tyska.*

<!--For more information, see *Format cross-references*.-->
