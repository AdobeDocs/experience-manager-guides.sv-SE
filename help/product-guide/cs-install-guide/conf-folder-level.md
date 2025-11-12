---
title: Konfigurera globala profiler eller profiler på mappnivå
description: Lär dig hur du konfigurerar globala profiler eller profiler på mappnivå
exl-id: 19f63d67-89ef-4c5e-bc9a-cf40dd8d7979
feature: Profiles
role: Admin
level: Experienced
source-git-commit: 1ea27a0ca99e61049d08f89a0cf5e0584b38edae
workflow-type: tm+mt
source-wordcount: '5127'
ht-degree: 0%

---

# Konfigurera globala profiler eller profiler på mappnivå {#id181AH2003PF}

I ett företag kan olika grupper eller produkter använda olika redigeringsmallar, utdatamallar, villkorsattributprofiler \(eller ämnesscheman\) och Web Editor-konfigurationer. Om du konfigurerar dessa endast på Enterprise \(eller global\)-nivå kan det bli svårt för författare eftersom de kommer att se mallar eller profiler som inte är relevanta för dem.

I AEM Guides kan du konfigurera mallar för att skapa \(ämne eller karta\), utdatamallar, villkorsattribut och Web Editor-konfigurationer på global nivå samt på mappnivå. På så sätt kan du dela upp konfigurationerna för olika avdelningar eller produkter i företaget.

Du kan även delegera mappspecifika konfigurationer till en avdelning eller produktadministratörer för att decentralisera administrationen.

Med hjälp av panelen Mappprofiler i inställningarna för stödlinjer kan du konfigurera inställningarna på följande flikar:

![](assets/folder-profile-tabs.png){width="800" align="left"}

- **Allmänt**: Fliken Allmänt är bara tillgänglig när du konfigurerar inställningar på mappnivå \(eller projekt/produkt\). Du kan konfigurera inställningar som mappsökvägar som inställningarna ska gälla för och användare som ska ha administratörsbehörighet för att skapa eller uppdatera konfigurationer.

- **Villkorliga attribut**: Använd den här fliken om du vill konfigurera villkorliga attribut på global nivå eller mappnivå. Ett villkorsattribut är en kombination av attributnamnet och värdet, och du kan också definiera en etikett för det. Du kan använda DITA-standardattributen eller dina egna anpassade attribut. De villkorliga attribut som du definierar på global nivå är tillgängliga för alla användare i alla projekt. Om du har definierat villkorliga attribut på mappnivå sammanfogas de med de globalt definierade villkorliga attributen.

- **Mallar**: Använd den här fliken för att konfigurera mallarna som författarna ska använda för att skapa eller publicera DITA-innehåll. Följande ämnesmallar är tillgängliga:

   - Ordlista

   - Referens

   - Ämne

   - Koncept

   - Uppgift

   - Felsökning

   - Tom

   - DITAVAL

  >[!NOTE]
  >
  > Du kan använda någon av de befintliga mallarna som bas för att skapa nya mallar. Den tomma DITA-mallen innehåller inga strukturer eller element som de andra mallarna. Du kan använda valfri OTB DITA-mall som bas, göra ändringar i den och spara den med ett annat namn. När du har gjort de ändringar som krävs lägger du till den uppdaterade mallen i den globala mallkonfigurationen eller redigeringsmallkonfigurationen på mappnivå. Mallen blir sedan tillgänglig för redigering.

  Förutom ämnesmallar kan du också definiera kartmallar som ska vara tillgängliga för författare. Följande kartmallar finns färdiga:

   - Karta

   - Bookmap

- **Utdataförinställning**: På samma sätt som mallar finns det fem förkonfigurerade utdataförinställningar:

   - AEM Site

   - PDF

   - HTML5

   - EPUB

   - Egen

  Utgivare kan publicera innehåll med hjälp av de här förinställningarna för färdiga utdata. Dessa förinställningar kan konfigureras av en administratör för den globala profilen eller profilen på mappnivå. När publiceringsförinställningarna har konfigurerats blir de tillgängliga för utgivaren för nya DITA-kartor. Du kan också använda förinställningar för publicering på befintliga DITA-kartor. Mer information finns i [Använda förinställda ändringar](#id18AGD0K0OHS).

- **Konfigurationer för XML-redigeraren**: Använd den här fliken om du vill anpassa utseendet och de olika funktionerna i Web Editor. Följande konfigurerbara inställningar är tillgängliga för Web Editor:

   - Användargränssnittskonfiguration för XML-redigerare
   - XML-redigerarens sidlayout
   - Konfiguration av XML-redigerare
   - CSS-mallayout
   - XML-redigerarkodfragment
   - Versionsetiketter för XML-innehåll
   - Rootmap \(endast på mappnivå\)

Du kan konfigurera både den globala profilen och profilen på mappnivå. I en mappnivåprofil kan du definiera de mappar som inställningarna ska gälla för. De här inställningarna innehåller villkorsattribut, mallar, förinställningar för utdata och inställningar för XML-redigeraren. De villkorliga förinställningarna, mallarna och XML-redigeringskonfigurationerna görs sedan tillgängliga för författare som arbetar i de konfigurerade mapparna. Utgivare får på samma sätt tillgång till de konfigurerade förinställningarna som definierats i de konfigurerade mapparna.

En profil på mappnivå åsidosätter inställningarna som konfigurerats i den globala profilen. Om en mapp har en mappnivåprofil visar den med andra ord mallarna, utdatamallarna och inställningarna för XML-redigeraren som är konfigurerade i motsvarande mappprofil. Den visar inte inställningarna som konfigurerats i den globala profilen. Detta gäller dock inte villkorsattributen. Om du har villkorsattribut sammanfogas de på global nivå och på mappnivå.

I följande avsnitt beskrivs hur du konfigurerar globala profiler och profiler på mappnivå.

## Konfigurera global profil

Så här konfigurerar du den globala profilen:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

   För första gången visas sidan Mappprofiler med endast rutan Global profil.

   ![](assets/folder-profile-global.png){width="800" align="left"}

1. Klicka på rutan **Global profil**.

1. Mer information om hur du konfigurerar **villkorliga attribut** finns i [Konfigurera villkorliga attribut för globala profiler och profiler på mappnivå](#id1889D0I305Z).

1. Mer information om hur du konfigurerar **mallar** finns i [Konfigurera redigeringsmallar](#id1889D0IL0Y4).

1. Mer information om hur du konfigurerar **Utdataförinställningar** finns i [Konfigurera förinställningar för utdata](#id18AGD0IH0Y4).

1. Information om hur du konfigurerar XML-redigerarkonfigurationen finns i [Konfigurera och anpassa XML-redigeraren](#id2065G300O5Z).

1. När du har gjort alla nödvändiga uppdateringar sparar och stänger du den **globala profilen**.


## Skapa och konfigurera en mappnivåprofil

Så här konfigurerar du en profil på mappnivå:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

   För första gången visas sidan Mappprofiler endast med standardrutan Global profil.

1. Klicka på **Skapa**.

   ![](assets/create-folder-profile.png){width="300" align="left"}

1. Ange följande information i dialogrutan **Skapa mappprofil**:
   - Namn på mappprofilen.
   - Sökväg till mappen där profilen ska användas.

     >[!NOTE]
     >
     > Du kan inte använda flera mappprofiler på en mapp. Se till att mappen som du väljer här inte har någon annan profil. Om en överordnad-underordnad mapp har sina egna specifika profiler, kommer den underordnade mappen att använda konfigurationerna från sin egen profil. Konfigurationerna från den överordnade mappen åsidosätter inte konfigurationerna för en underordnad mapp.

1. Klicka på **Skapa**.

   En ny platta med namnet på mappprofilen skapas på sidan Mappprofiler

1. Klicka på mappprofilpanelen för att redigera.

   En allmän flik med mappprofilens namn och konfigurerad mappinformation visas.

1. Klicka på **Redigera** om du vill lägga till flera mappar och användare som har administratörsbehörighet för att ändra mappprofilen.

   >[!NOTE]
   >
   > Användare som du lägger till här har administratörsbehörighet för att uppdatera villkorsattributen, mallen och utdatainställningarna som är konfigurerade för den här mappprofilen.

1. Om du vill lägga till en mapp klickar du på ikonen Bläddra i mappsökvägen och navigerar till och väljer en mapp. Klicka sedan på Lägg till för att lägga till mappen i profilen.

   >[!NOTE]
   >
   > Se till att mappen som du väljer här inte har någon annan mappnivåprofil kopplad till sig.

1. Om du vill lägga till en användare väljer du en användare i listrutan **Administratörsanvändare** och klickar på **Lägg till**.

   >[!NOTE]
   >
   > Du kan lägga till flera användare till mappprofilen från listrutan. Du kan också ta bort en befintlig admin-användare från listan genom att klicka på borttagningsikonen bredvid användar-ID:t.

1. När du har lagt till alla nödvändiga mappar och användare i mappprofilen klickar du på **Spara**.


Nu kan du konfigurera villkorsattribut, mallar, förinställningar för utdata och XML-redigeraren.

>[!IMPORTANT]
>
> När du skapar en mappprofil innehåller den som standard inga mallar. Du måste lägga till de nödvändiga mallarna i mappprofilen för att göra dem tillgängliga för författarna.

## Konfigurera villkorliga attribut för globala profiler eller profiler på mappnivå {#id1889D0I305Z}

Utför följande steg för att konfigurera villkorliga attribut som stöds av DITA på global nivå eller mappnivå:

1. Logga in på Adobe Experience Manager som administratör eller som användare med administratörsbehörighet för en mappnivåprofil.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

1. Klicka på den profilruta som du vill konfigurera.

   >[!NOTE]
   >
   > Du kan välja att konfigurera villkorliga attribut i den globala profilen eller en profil på mappnivå.

1. Klicka på fliken **Villkorliga attribut** på profilsidan.

1. Klicka på **Redigera**.

1. Klicka på **Lägg till**.

1. Ange **Namn**, **Värde** och **Etikett** för villkorsattributet.

   Du kan spara en profil med endast attributnamnet. Ett attribut kan dock bara användas när det har ett angivet värde. Om du anger både värde och etikett för ett attribut visas etiketten för villkorsattributet i Web Editor. Etiketten visas också för publiceringsadministratören när en villkorlig förinställning skapas.

   I följande skärmbild visas definitionen för attributet `platform` med möjliga värden och etiketter.

   ![](assets/add_profile.png)

1. Om du vill lägga till fler värden för samma attribut klickar du på ikonen **+** och anger ytterligare värde och etikett.

1. Om du vill lägga till fler attribut klickar du på **Lägg till**.

1. Klicka på **Spara**.


Om du använder ett anpassat attribut måste det vara ett giltigt DITA-attribut som stöds av DTD:n. Om du vill använda ett attribut, som inte är ett standard-DITA-attribut, utför du följande ytterligare steg:

1. Lägg till det anpassade attributet i DTD-filen. Om din DTD-fil till exempel är commonElements.mod måste du leta reda på filen i DTD-katalogen. Standardsökvägen för systemets DTD-fil är:

   /libs/fmdita/dita\_resources/DITA-1.3/dtd/base/dtd/commonElements.mod

   >[!IMPORTANT]
   >
   > Den specialiserade DTD-filen bör ingå i den anpassade koddistributionen. DTD-filer under /apps ingår i produktdistributionen och skrivs därför över med installation av nya releaser. Vi rekommenderar att du lägger till en särskild DTD-fil under /var/dxml/dita\_resources i projektmappen och inkluderar DTD-/katalogsökvägen i DITA-profilen. Mer information finns i [Integrera DITA-specialisering](dita-ot-specialization.md#id211MB0E00XA).

1. Använd Package Manager för att hämta /libs/fmdita/config/condAttrList.xml:

1. Skapa en kopia av filen condAttrList.xml på följande plats i Cloud Manager Git-databasen:

   `/apps/fmdfmdita/config/condAttrList.xml`

1. Spara filen.

1. Lägg till anpassade attribut i den globala profilen eller mappnivåprofilen.


## Konfigurera mallar {#id1889D0IL0Y4}

AEM Guides innehåller 7 färdiga ämnesmallar, 2 DITA-mallar och 3 PDF-mallar. Du kan välja att endast ha ett fåtal mallar tillgängliga för författare och utgivare. Om du använder en anpassad mall kan samma mall konfigureras och göras tillgänglig för redigering och publicering. Använd fliken **Mallar** i konfigurationen för mappprofiler om du vill lägga till eller ta bort ämnen, kartor eller PDF-mallar från globala profiler eller mappnivåprofiler.

Även innan du konfigurerar teman, kartor eller PDF-mallar på global nivå eller på mappnivå kan du definiera en plats där du kan lagra dina anpassade mallar. Mer information om hur du konfigurerar en anpassad plats att lagra mallarna på finns i [Konfigurera en anpassad DITA-mallmappsökväg](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z).

Gör så här för att lägga till teman, kartor eller PDF-mallar i en mappprofil:

1. Logga in på Adobe Experience Manager som administratör eller som användare med administratörsbehörighet för en mappnivåprofil.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

1. Klicka på den profilruta som du vill konfigurera.

   >[!NOTE]
   >
   > Du kan välja att konfigurera en mall i den globala profilen eller en profil på mappnivå.

1. Klicka på fliken **Mallar** på profilsidan.
1. Klicka på **Redigera**.

   Du kan lägga till mallar för ämnen, kartor och PDF genom att söka på standardplatsen eller söka efter den.

   >[!NOTE]
   >
   > Som standard lagras alla mallar i mappen /content/dam/dita-templates. Mappen `dita-templates` innehåller undermapparna `topics`, `maps` och `PDF` för att lagra ämne, karta och PDF-mallar. Du kan lägga till dina egna mallar \(.dita,.xml eller .ditamapfiles\) i standardmallmapparna. När du har lagt till mallen i standardmappen kan du lägga till dem i den globala profilen eller mappprofilen. Mer information om hur du skapar egna mallar med Web Editor finns i [Skapa anpassad redigeringsmall](#id1917D0EG0HJ).

   ![](assets/search-author-temp.png){width="800" align="left"}

1. Lägg till de önskade avsnitten, kartorna och PDF-mallarna i din profil.

   Gör något av följande om du vill lägga till en mall:

   - Välj **Sök eller Typ** och ange eller välj namnet på en mall i listrutan. Listrutan består av alla standardmallar och alla nya mallar som du har skapat.

     ![](assets/default-template-list.png){width="800" align="left"}

   - Klicka på **Bläddra** och välj en mall från DAM.

1. Klicka på **Lägg till**.

   De valda mallarna läggs till i malllistan.

   ![](assets/author-templ-added-list.png){width="800" align="left"}

   >[!NOTE]
   >
   > Du kan ändra ordningen på mallarna genom att dra och släppa dem på önskad plats i listan. Mallarnas placering styr i vilken ordning de visas på sidan Utskrift i arbetsflödet för att skapa ämnen eller kartor.

1. Om du vill ange översättningsreglerna bläddrar du till SRX-platsen för att hitta mappen som innehåller SRX-filerna. SRX-formatet \(Segmenteringsregler eXchange\) är en standard för utbyte av segmenteringsregler mellan olika användare och olika översättningsmiljöer. Du kan skapa en mapp och lägga till dina anpassade SRX-filer i den.

   När du har skapat mappen som innehåller SRX-filerna kan du lägga till mappsökvägen i konfigurationen **Translation SRX location** i mappprofilen.

   AEM Guides väljer SRX-reglerna enligt översättningsprojektets källspråk. Den söker efter en anpassad SRX-fil för ett språk, och om du inte definierar en anpassad SRX-fil väljs reglerna enligt reglerna för översättning utanför rutan.

1. Klicka på **Spara**.


Om du har konfigurerat mallarna för en mappnivåprofil kopplas de konfigurerade mallarna till den konfigurerade mappen. Alla projekt som skapas i den konfigurerade mappen har endast åtkomst till de mallar som är konfigurerade under profilen på mappnivå.

## Skapa en anpassad redigeringsmall {#id1917D0EG0HJ}

AEM Guides är ett enkelt sätt att skapa mallar. Som systemadministratör kan du använda webbredigeraren för att skapa redigeringsmallar från grunden. Du kan sedan lägga till den nya mallen i den globala profilen eller tilldela den till en viss mapp med den mappspecifika profilen.

Så här skapar du en anpassad redigeringsmall:

1. Logga in i Adobe Experience Manager som administratör.

1. I Assets-gränssnittet navigerar du till den mapp som konfigurerats för att lagra mallfilerna. Som standard lagras alla ämnesmallar i mappen /content/dam/dita-templates/topics.

   >[!NOTE]
   >
   > Information om hur du konfigurerar en anpassad plats för att lagra ämne- eller mappmallar finns i [Konfigurera anpassad DITA-mallmappsökväg](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Klicka på **Skapa** \> **DITA-mall**.

1. På sidan Design väljer du den typ av DITA-ämnesmall som du vill skapa.

   >[!NOTE]
   >
   > Du kan använda mallen Tom för att börja från början. Den tomma mallen innehåller ingen struktur eller några element.

1. Klicka på **Nästa**.

1. På den nya mallegenskapssidan anger du en **rubrik**, **namn** och **beskrivning** för mallen.

   >[!NOTE]
   >
   > Namnet föreslås automatiskt baserat på mallens rubrik. Om du vill ange namnet manuellt kontrollerar du att namnet inte innehåller blanksteg, apostrof eller klammerparenteser och slutar med .dita.

1. *\(Valfritt\)* Klicka på knappen **Lägg till en miniatyrbild** i webbläsaren för att markera en miniatyrbild som du vill associera med mallen.

1. Klicka på **Skapa**.

   Meddelandet Ämnet har skapats visas.

   Du kan välja att öppna mallen för redigering i Web Editor eller spara mallfilen på malllagringsplatsen. När mallen har skapats kan du använda webbredigeraren för att anpassa mallen efter dina behov. När du har skapat en mall måste du associera den med en global profil eller en profil på mappnivå.


## Konfigurera förinställningar för utdata {#id18AGD0IH0Y4}

I en typisk företagsmiljö kan olika utdatamallar användas för olika produkter eller användarhandböcker. Det kan också finnas några vanliga processer för generering av utdata som ska användas av alla utgivare och en uppsättning specifika processer för generering av utdata för en viss grupp utgivare eller projekt.

Med AEM Guides kan administratören skapa förinställningar för utdata med specifika inställningar som sedan kan användas av alla eller en viss uppsättning utgivare för att generera utdata. Administratören kan till exempel skapa en förinställning för utdata för att generera en användarhandbok som är gemensam för alla utgivare. Och ytterligare en för att skapa användarhandböcker för programmering som är specifika för en uppsättning utgivare. Båda dessa förinställningar kan konfigureras för att använda olika utdatamallar. I det här exemplet kan den vanliga publiceringsförinställningen för generering av användarhandboken konfigureras på global nivå. Dessutom kan förinställningen för att generera användarhandboken för programmering konfigureras på mappnivå.

När standardförinställningarna för utdata har skapats i systemet kommer alla DITA-scheman som skapas därefter att använda standardförinställningarna för att generera utdata. Alla befintliga DITA-kartor kommer dock att fortsätta använda de förinställningar som tidigare konfigurerats med dem. Om du vill använda den nya förinställningen på alla befintliga DITA-kartor måste du köra arbetsflödet Använd förinställda ändringar.

Förutom förinställningarna som konfigurerats på global nivå eller företagsnivå har utgivaren fortfarande behörighet att skapa fler förinställningar. Dessa förinställningar är dock kopplade till den DITA-karta som de skapas för. Mer information om hur du skapar förinställningar för vanliga utdata för en DITA-karta finns i *Skapa, redigera, duplicera eller ta bort en förinställning för utdata* i guiden Använda Adobe Experience Manager Guides as a Cloud Service.

Utför följande steg för att konfigurera globala eller mappspecifika förinställningar för utdata:

1. Logga in på Adobe Experience Manager som administratör eller som användare med administratörsbehörighet för en mappspecifik profil.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

1. Klicka på den profilruta som du vill konfigurera.

   >[!NOTE]
   >
   > Du kan välja att konfigurera förinställningar för utdata i den globala profilen eller en mappspecifik profil.

1. På profilsidan. klicka på fliken **Utdatainställningar**.

   En lista med färdiga förinställningar visas, t.ex. AEM Site, PDF, HTML5, EPUB och CUSTOM.

1. Gör något av följande om du vill skapa eller redigera en förinställning för utdata:

   - Klicka på **Skapa** om du vill skapa en ny förinställning från början.
   - Klicka på Duplicera om du vill skapa en kopia av den markerade förinställningen. Du kan ändra den duplicerade förinställningen och spara den.

   - Klicka på **Redigera** för att öppna den markerade förinställningens konfiguration för redigering.

     Mer information om inställningar för förinställningar för utdata finns i *Förstå förinställningarna* i guiden Använda Adobe Experience Manager Guides as a Cloud Service.

1. Klicka på **Spara** om du vill spara förinställningarna.


Alla DITA-kartor som skapas eller överförs efter detta har den nya eller uppdaterade förinställningen.

## Använda förinställda ändringar {#id18AGD0K0OHS}

En ny förinställning som skapas på global nivå blir tillgänglig för alla nya DITA-kartor som du skapar framöver. Om en ny förinställning skapas på mappnivå, blir den förinställningen tillgänglig för alla kartor som skapas i den konfigurerade mappen. Som standard görs ingen ny förinställning tillgänglig för någon befintlig DITA-karta.

Om du har uppdaterat en befintlig förinställning eller vill göra en ny förinställning tillgänglig för befintliga DITA-kartor utför du följande steg:

1. Logga in på Adobe Experience Manager som administratör eller som användare med administratörsbehörighet för en mappspecifik profil.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

1. Klicka på den profilruta som du vill konfigurera.

   >[!NOTE]
   >
   > Du kan välja att konfigurera förinställningar för utdata i den globala profilen eller en mappspecifik profil.

1. På profilsidan. klicka på fliken **Utdatainställningar**.

   En lista med färdiga förinställningar visas, t.ex. AEM Site, PDF, HTML5, EPUB och CUSTOM.

1. Välj den förinställning för utdata som du vill använda på befintliga DITA-kartor.

1. Klicka på **Använd förinställda ändringar** i huvudverktygsfältet.

1. I dialogrutan Använd förinställda ändringar kan du välja mellan:

   - **Om du väljer alternativet Skriv över befintlig förinställning**: Om du väljer det här alternativet skrivs alla uppdateringar som du har gjort i de befintliga förinställningarna över inställningarna i alla befintliga DITA-mappar där den förinställningen används. Om du gör det förlorar du alla befintliga villkorsstyrda förinställningar och baslinjeinformation som är kopplade till kartan.

   - **Det går inte att välja alternativet Skriv över befintlig förinställning**: Om du inte markerar det här alternativet kommer uppdateringar som du har gjort i de befintliga förinställningarna inte att påverka befintliga DITA-kartor. Endast de nya förinställningarna läggs till i befintliga DITA-kartor. Observera att den nya DITA-kartan får båda, de uppdaterade förinställningarna och de nya förinställningarna.

1. Klicka på **OK** om du vill använda ändringarna från de valda förinställningarna på alla befintliga DITA-kartor.



## Konfigurera AI Assistant för smart hjälp och redigering

För Experience Manager Guides as a Cloud Service (![AEM cloud ](assets/aem-cloud-icon.svg)).

AI Assistant i Adobe Experience Manager Guides är ett kraftfullt, AI-drivet verktyg som har utformats för att förbättra ditt innehåll genom smart redigering och återanvändning av innehåll. Här finns två kraftfulla AI-funktioner - **Redigering** och **Hjälp** - i Experience Manager Guides-gränssnittet, så att du kan autentisera dokument och få tillgång till information snabbare och effektivare.

Mer konfigurationsinformation finns i [AI Assistant-konfigurationen](./conf-smart-suggestions.md).

**Konfigurera AI-baserade smarta förslag**

Du kan konfigurera de AI-baserade smarta förslagen och hjälpa författarna att återanvända det befintliga innehållet och enkelt skapa korrekta och konsekventa innehållsreferenser. På fliken **AI-konfiguration** kan du styra inställningarna för **Föreslå återanvändbart innehåll** från AI-assistentpanelen i Redigeraren.

Utför följande steg för att konfigurera AI-standardkonfigurationen på global nivå eller på mappnivå:
1. Logga in i Adobe Experience Manager som administratör eller användare med administratörsbehörighet för en mappnivåprofil.
1. Markera länken **Adobe Experience Manager** överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och välj **Mappprofiler**.
1. Markera profilrutan som du vill konfigurera.

   >[!NOTE]
   >
   >Du kan konfigurera AI-baserade smarta förslag till den globala profilen eller en profil på mappnivå.

1. Välj fliken **AI-konfiguration** på profilsidan.

   ![Konfigurationsfliken för AI i den globala profilen](assets/global-profile-AI-configuration-cs.png) {width="800" align="left"}

1. Välj **Redigera**.
1. Som administratör kan du konfigurera följande inställningar:

   **Minsta antal tecken**: Ange det minsta antal tecken som författaren måste välja för att få förslag. Om talet till exempel är 40 måste författaren markera minst 40 tecken för att kunna visa ett smart förslag.

   För markeringar som inte uppfyller minimikraven för tecken visas följande meddelande på AI-assistentpanelen:

   ![](assets/smart-suggestions-character-limit.png)

   För allmänna val där det inte finns några förslag visas dock följande meddelande:

   ![](assets/smart-suggestions-select-another-text-message.png)

   Detta hjälper författare att förstå om förslag inte är tillgängliga på grund av otillräcklig teckenmarkering eller egentligen inget matchande innehåll.

   **Maximalt antal förslag**: Ange maximalt antal förslag som författare kan få när innehållet redigeras. Om talet till exempel är 5 kan författaren visa fem eller färre smarta förslag.

   **Filer och mappar**: Välj de mappar som smarta förslag ska visas från. Det går endast att markera underordnade mappar med den angivna mappsökvägen i en mappprofil. Mer information finns i [Begränsningar för mappprofiler](#folder-profile-restrictions).

   *För att innehållet ska vara konsekvent rekommenderar vi att inga två poster i listan har gemensamma filer mellan dem*. När du har valt filer och mappar visas de.

1. Klicka på **Spara**.

   >[!NOTE]
   >
   > Mappprofilens senaste indexstatus visas högst upp när du har sparat filen.

Läs mer om hur du visar och lägger till [AI-baserade smarta förslag](../user-guide/authoring-ai-based-smart-suggestions.md) för att lägga till innehållsreferenser vid redigering i webbredigeraren.

### Begränsningar för mappprofiler

Om du vill att smarta förslag ska fungera effektivt bör du tänka på följande när du indexerar mappar:

1. Innehållet måste indexeras via mappprofiler för AI-assistenten för att kunna ge smarta förslag till författare.
2. När du anger en mapp för indexering kan bara mappar som ligger under den aktuella mappprofilen läggas till. Om du försöker lägga till mappar utanför den här mappprofilen utlöses en varning.

   ![](assets/warning-message-indexing.png)

   Den här begränsningen gäller endast profiler på mappnivå. Den globala profilen tillämpar inga sökvägsbegränsningar och kan indexera mappar som inte finns i någon annan mappprofil.
3. Om en överordnad mapp läggs till för indexering tas alla underordnade mappar som redan finns med automatiskt bort för att undvika duplicering. Om du lägger till en underordnad mapp till en redan indexerad överordnad mapp utlöses också en varning.

   ![](assets/parent-child-warning-message-indexing.png)
4. Eventuella uppdateringar, flyttningar eller borttagningar av filer i indexerade mappar utlöser automatisk omindexering eller borttagning från indexet.
5. För varje indexeringsförsök visas följande indexeringsstatus:

   - Pågår: Anger att indexeringen pågår.
   - Indexeringen har slutförts: Anger att indexeringen har slutförts.
   - Indexeringen misslyckades: Anger att indexeringen misslyckades.
   - Inte synkroniserad: Anger att indexeringen inte är synkroniserad, vilket oftast visas efter en uppgradering eller migrering, när det inte gick att verifiera den aktuella indexeringsstatusen. Du kan försöka indexera igen för att uppdatera och uppdatera statusen.

   När indexeringen misslyckas får du alternativen **Visa felloggar** och **Försök indexera igen** för att felsöka och lösa problemet.

   ![](assets/indexing-failed-options.png)

   Felloggarna visas enligt nedan:

   ![Alt-text](index-error-log.png)

6. En tidsstämpel för den senaste indextiden visas för varje mappprofil.

**Anpassa standardfrågorna för smart hjälp**

För Experience Manager Guides as a Cloud Service (![AEM cloud ](assets/aem-cloud-icon.svg)).

Du kan konfigurera den AI-baserade smarta **hjälpen** så att författarna kan ställa frågor och enkelt hitta det innehåll som krävs från [Experience Manager Guides-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview).

På fliken **XML-redigerarkonfiguration** kan du konfigurera standardfrågorna på panelen **Hjälp**.

>[!NOTE]
>
>Du kan konfigurera upp till tio standardfrågor.

Så här konfigurerar du standardfrågorna:

1. Logga in i Adobe Experience Manager som administratör eller användare med administratörsbehörighet för en mappnivåprofil.
1. Markera länken **Adobe Experience Manager** överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och välj **Mappprofiler**.
1. Markera profilrutan som du vill konfigurera.

   >[!NOTE]
   >
   >Du kan konfigurera standardfrågor för den **smarta hjälppanelen** till den globala profilen eller en mappnivåprofil.

1. Välj fliken **XML-redigerarkonfiguration**.

1. Klicka på ikonen **Redigera** överst.
1. I avsnittet **Gränssnittskonfiguration för XML-redigeraren** väljer du ikonen **Hämta** för att hämta filen `ui_config.json` på din lokala dator.
1. Lägg till exempelfrågorna i filen `ui_config.json`.

   **Exempel på exempelfrågor**:

   ```json
   "assistantSampleQuestions": [
   "How to create a new topic",
   "How to create a new map",
   "What is a baseline" ]
   ```

1. Spara filen och överför den.

   >[!NOTE]
   >
   > Standardfrågorna visas på panelen **Smart hjälp** när du har sparat filen.


Läs mer om hur du använder den [AI-baserade smarta hjälpen](../user-guide/ai-based-smart-help.md) för att hitta det innehåll som krävs från Experience Manager Guides-dokumentationen.


## Konfigurera och anpassa XML-redigeraren {#id2065G300O5Z}

Som standard har XML-redigeraren många funktioner som hjälper dina författare att skapa DITA-dokument. Om du arbetar i en begränsande miljö kan du välja vilka funktioner som ska visas för författarna. På fliken Konfiguration i XML-redigeraren kan du enkelt styra funktionerna och även ändra utseendet på redigeraren. Som administratör kan du anpassa följande komponenter i redigeraren:

**Konfiguration av användargränssnitt i XML-redigeraren**

Med den här inställningen kan du skapa JSON-tillägg som återspeglar ändringar som gjorts i filen `ui_config.json`. Du kan överföra dessa tillägg oberoende av varandra på mappprofilnivå, vilket ger ökad flexibilitet och anpassning. Om du till exempel ändrar **XML-redigerarkonfigurationen**, till exempel uppdaterar en knapp, identifieras skillnaderna automatiskt i systemet. Genom att överföra dessa ändringar till **XML-redigerarens gränssnittskonfiguration** och konvertera dem till JSON-tillägg med knappen **Konvertera gränssnittskonfiguration till JSON**, genererar systemet ett tillägg som innehåller den nya funktionen.

Läs mer om [att anpassa JSON-konfigurationer och konvertera gränssnittskonfigurationer för den nya AEM Guides Editor](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

>[!NOTE]
>
> När du anpassar programmet med hjälp av tilläggsramverket bör du bara använda de nödvändiga React Spectrum-komponenter som stöds, till exempel Tree, Table, Checkbox, radio button och radio group, för att undvika problem under distributionen.

**XML-redigerarens sidlayout**

Med den här funktionen kan du överföra CSS-filer för att formatera de nya tillägg som har överförts under **gränssnittskonfigurationen för XML-redigeraren**. Den överförda CSS-koden används på ett enhetligt sätt i alla relevanta program, vilket ger ett enhetligt och prydligt utseende för användargränssnittets anpassningar.

**Konfiguration av XML-redigerare**

Den här inställningen styr verktygsfältet och andra element i användargränssnittet i redigeraren. Välj ikonen **Hämta** om du vill hämta filen `ui\_config.json` på din lokala dator. Du kan sedan ändra filen och överföra den på samma sätt. Beroende på var du överför filen på, global nivå eller mappnivå tillämpas ändringarna därefter. Mer information om hur du anpassar XML-redigeraren med `ui\_config.json file` finns i [Anpassa verktygsfältet](conf-web-editor-customize-toolbar.md#).

>[!NOTE]
>
> För AEM Guides 2502 och senare versioner rekommenderar vi att du använder JSON-tillägget i stället för `ui_config.json` för anpassning. Mer information finns i avsnittet **Konfiguration av användargränssnitt i XML-redigeraren** ovan.

**CSS-mallayout**

Ladda ned filen som finns i det här avsnittet för att anpassa dokumentets utseende och känsla när det förhandsgranskas eller öppnas för redigering i Web Editor. CSS-standardfilen som är tillgänglig för hämtning är bara en testfil som inte ska användas för anpassning. Du kan skapa en CSS-fil med anpassningar för Web Editor och överföra samma fil. Du kan till exempel skapa en CSS-fil med följande kod:

```
.title {    font-size: 9em;}
```

Spara den här filen och överför den i CSS-mallayoutavsnittet. Nästa gång du hämtar filen får du den senaste CSS-filen som används i Web Editor.

**XML-redigerarkodfragment**

Med hjälp av konfigurationsfilen i det här avsnittet kan du skapa vissa standardfragment och dela dem med författarna. Filens standardstruktur anges nedan:

```
{
   "snippetID": {
      "name": "snippet Name",
      "description": "snippet Description",
      "value": "<i>this is snippet value</i>"
  }
}
```

Följande information krävs för att skapa ett fragment:

**snippetID** - Ett unikt ID för fragmentet. Det kan ta ett alfanumeriskt värde.

**name** - Ett beskrivande namn som identifierar fragmentet. Namnet visas på fragmentpanelen.

**description** - Lägg till en beskrivande information för fragmentet.

**value** - Ange XML-koden för fragmentet.

>[!NOTE]
>
> Du kan lägga till fler fragment genom att lägga till kommatecken \(,\) i slutet av fragmentdefinitionen och upprepa samma struktur för nästa fragment.

**Versionsetiketter för XML-innehåll**

Som standard kan författare skapa egna etiketter och associera dem med ämnesfilerna. Detta kan dock leda till många variationer av en och samma etikett, t.ex. att etiketterna &quot;Release 1.0&quot;, &quot;Release-1.0&quot; och &quot;release 1&quot; kan användas för att identifiera samma steg i ett ämne. För att undvika sådana inkonsekventa etiketter i systemet kan du skapa en fördefinierad lista med etiketter som författare sedan kan välja mellan. Enhetliga etiketter ger bättre filhantering i systemet.

Med versionsetikettkonfigurationen kan du överföra en lista över giltiga etiketter för din organisation. Hämta filen label.json och ändra den enligt nedan:

```
{
"label1":"Draft",
"label2":"PM-Review",
"label3":"Engg-Review",
"label4":"QE-Review",
"label5":"Ready for Loc",
"label6":"Ready for Publish"
}
```

I exemplet ovan är &quot;label1&quot; identifieraren för etikettsekvensen och den läggs till av etiketten som visas för författarna där en etikett behövs. Spara den här filen och ladda upp den i avsnittet Etiketter för XML-innehållsversion.

>[!IMPORTANT]
>
> För att konfigurationer på mappnivå ska börja gälla måste användarna välja profilen under sina användarinställningar i Web Editor.

**Rootmap**

Om dina författare arbetar med en viss rotkarta kan du bläddra till och välja den rotkartan här. Observera att du bara kan definiera rotmappen för en profil på mappnivå.
