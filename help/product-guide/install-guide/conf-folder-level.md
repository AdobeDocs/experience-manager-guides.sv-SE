---
title: Konfigurera globala profiler eller profiler på mappnivå
description: Lär dig hur du konfigurerar globala profiler eller profiler på mappnivå
exl-id: d7bf7e69-fe12-4c48-8ce4-17b74a6c61e7
feature: Profiles
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '3896'
ht-degree: 0%

---

# Konfigurera globala profiler eller profiler på mappnivå {#id181AH2003PF}

I ett företag kan olika grupper eller produkter använda olika redigeringsmallar, utdatamallar, villkorsattributprofiler \(eller ämnesscheman\) och Web Editor-konfigurationer. Om du konfigurerar dessa endast på Enterprise \(eller global\)-nivå kan det vara svårt för skribenterna eftersom de kommer att se mallar eller profiler som inte är relevanta för dem.

I AEM Guides kan du konfigurera mallar för att skapa \(ämne eller karta\), utdatamallar, villkorsattribut och Web Editor-konfigurationer på global nivå samt på mappnivå. På så sätt kan du dela upp konfigurationerna för olika avdelningar eller produkter i företaget.

Du kan även delegera mappspecifika konfigurationer till en avdelning eller produktadministratörer för att decentralisera administrationen.

Med hjälp av panelen Mappprofiler i inställningarna för stödlinjer kan du konfigurera inställningarna på följande flikar:

![](assets/folder-profile-tabs.png){width="800" align="left"}

- **Allmänt**: Fliken Allmänt är bara tillgänglig när du konfigurerar inställningar på mappnivå \(eller projekt/produkt\). Du kan konfigurera inställningar som mappsökvägar som inställningarna ska gälla för och användare som ska ha administratörsbehörighet för att skapa eller uppdatera konfigurationer.

- **Villkorliga attribut**: Använd den här fliken om du vill konfigurera villkorliga attribut på global nivå eller mappnivå. Ett villkorsattribut är en kombination av attributnamnet och värdet, och du kan också definiera en etikett för det. Du kan använda DITA-standardattributen eller dina egna anpassade attribut. De villkorliga attribut som du definierar på global nivå är tillgängliga för alla användare i alla projekt. Om du har definierat villkorliga attribut på mappnivå sammanfogas de med de globalt definierade villkorliga attributen.

- **Redigeringsmall**: Använd den här fliken för att konfigurera mallarna som dina författare ska använda för att skapa DITA-innehåll. Följande ämnesmallar är tillgängliga:

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

  Förutom ämnesmallar kan du också definiera kartmallar som ska vara tillgängliga för författarna. Följande kartmallar finns färdiga:

   - Karta

   - Bookmap

- **Utdataförinställning**: På samma sätt som för redigeringsmallar finns det fem förkonfigurerade utdataförinställningar:

   - AEM

   - PDF

   - HTML5

   - EPUB

   - Egen

  Utgivare kan publicera innehåll med hjälp av de här förinställningarna för färdiga utdata. Dessa förinställningar kan konfigureras av en administratör för den globala profilen eller profilen på mappnivå. När publiceringsförinställningarna har konfigurerats blir de tillgängliga för utgivaren för nya DITA-kartor. Du kan också använda förinställningar för publicering på befintliga DITA-kartor. Mer information finns i [Använda förinställda ändringar](#id18AGD0K0OHS).

- **Konfigurationer för XML-redigeraren**: Använd den här fliken om du vill anpassa utseendet och de olika funktionerna i Web Editor. Följande konfigurerbara inställningar är tillgängliga för Web Editor:

   - Användargränssnittskonfiguration för XML-redigerare
   - CSS-mallayout
   - XML-redigerarkodfragment
   - Versionsetiketter för XML-innehåll
   - Rootmap \(endast på mappnivå\)

Du kan konfigurera både den globala profilen och profilen på mappnivå. I en mappnivåprofil kan du definiera de mappar som inställningarna ska gälla för. Dessa inställningar omfattar villkorsattribut, redigeringsmallar, förinställningar för utdata och inställningar för XML-redigeraren. De villkorliga förinställningarna, redigeringsmallarna och XML-redigerarkonfigurationerna görs sedan tillgängliga för författare som arbetar i de konfigurerade mapparna. Utgivare får på samma sätt tillgång till de konfigurerade förinställningarna som definierats i de konfigurerade mapparna.

En profil på mappnivå åsidosätter inställningarna som konfigurerats i den globala profilen. Om en mapp har en mappnivåprofil visar den med andra ord redigeringsmallarna, utdatamallarna och inställningarna för XML-redigeraren som är konfigurerade i motsvarande mappprofil. Den visar inte inställningarna som konfigurerats i den globala profilen. Detta gäller dock inte villkorsattributen. Om du har villkorsattribut sammanfogas de på global nivå och på mappnivå.

I följande avsnitt beskrivs hur du konfigurerar globala profiler och profiler på mappnivå.

## Konfigurera global profil

Så här konfigurerar du den globala profilen:

1. Logga in i Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.

   För första gången visas sidan Mappprofiler med endast rutan Global profil.

   ![](assets/folder-profile-global.png){width="800" align="left"}

1. Klicka på rutan **Global profil**.

1. Mer information om hur du konfigurerar **villkorliga attribut** finns i [Konfigurera villkorliga attribut för globala profiler och profiler på mappnivå](#id1889D0I305Z).

1. Mer information om hur du konfigurerar **redigeringsmallen** finns i [Konfigurera redigeringsmallar](#id1889D0IL0Y4).

1. Mer information om hur du konfigurerar **Utdataförinställningar** finns i [Konfigurera förinställningar för utdata](#id18AGD0IH0Y4).

1. Information om hur du konfigurerar XML-redigerarkonfigurationen finns i [Konfigurera och anpassa XML-webbredigeraren](#id2065G300O5Z).

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
   > Användare som du lägger till här har administratörsbehörighet för att uppdatera villkorsattributen, redigeringsmallen och förinställningarna för utdata som är konfigurerade för den här mappprofilen.

1. Om du vill lägga till en mapp klickar du på ikonen Bläddra i mappsökvägen och navigerar till och väljer en mapp. Klicka sedan på Lägg till för att lägga till mappen i profilen.

   >[!NOTE]
   >
   > Se till att mappen som du väljer här inte har någon annan mappnivåprofil kopplad till sig.

1. Om du vill lägga till en användare väljer du en användare i listrutan **Administratörsanvändare** och klickar på **Lägg till**.

   >[!NOTE]
   >
   > Du kan lägga till flera användare till mappprofilen från listrutan. Du kan också ta bort en befintlig admin-användare från listan genom att klicka på borttagningsikonen bredvid användar-ID:t.

1. När du har lagt till alla nödvändiga mappar och användare i mappprofilen klickar du på **Spara**.


Nu kan du konfigurera villkorsattribut, redigeringsmallar, utdatainställningar och XML-redigeraren.

>[!IMPORTANT]
>
> När du skapar en mappprofil innehåller den som standard inga redigeringsmallar. Du måste lägga till de nödvändiga redigeringsmallarna i mappprofilen för att göra dem tillgängliga för författarna.

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

   ![](assets/add_profile.png){width="650" align="left"}

1. Om du vill lägga till fler värden för samma attribut klickar du på ikonen **+** och anger ytterligare värde och etikett.

1. Om du vill lägga till fler attribut klickar du på **Lägg till**.

1. Klicka på **Spara**.


**Använd anpassade attribut**

Om du använder ett anpassat attribut måste det vara ett giltigt DITA-attribut som stöds av DTD:n. Om du vill använda ett attribut, som inte är ett standard-DITA-attribut, utför du följande ytterligare steg:

1. Lägg till det anpassade attributet i DTD-filen. Om din DTD-fil till exempel är commonElements.mod måste du leta reda på filen i DTD-katalogen. Standardsökvägen för systemets DTD-fil är:

   /libs/fmdita/dita\_resources/DITA-1.3/dtd/base/dtd/commonElements.mod

   >[!IMPORTANT]
   >
   > Den specialiserade DTD-filen bör ingå i den anpassade koddistributionen. DTD-filer under /etc ingår i produktdistributionen och skrivs därför över med installation av nya releaser. Vi rekommenderar att du lägger till en särskild DTD-fil under /apps i projektmappen och inkluderar DTD-/katalogsökvägen i DITA-profilen. Mer information finns i [Integrera DITA-specialisering](dita-ot-specialization.md#id211MB0E00XA).

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

1. Sök efter och klicka på paketet *com.adobe.fmdita.config.ConfigManager*.

1. Spara konfigurationen.

   Detta rensar bort systemcachen.

1. Navigera till filen condAttrList.xml som finns på följande plats:

   /libs/fmdita/config/condAttrList.xml

1. Skapa en överläggsnod av mappen `config` i noden `apps`.

1. Navigera till och lägg till anpassade attribut i filen condAttrList.xml i noden `apps`:

   `/apps/fmdita/config/condAttrList.xml`

1. Spara filen.

1. Lägg till anpassade attribut i den globala profilen eller mappnivåprofilen.


## Konfigurera redigeringsmallar {#id1889D0IL0Y4}

AEM Guides levereras med 7 färdiga mallar och 2 DITA-mallar. Du kan välja att bara ha ett fåtal mallar tillgängliga för författarna. Om du använder en anpassad mall kan samma mall konfigureras och göras tillgänglig för redigering. Du använder fliken Redigeringsmall i konfigurationen Mappprofiler för att lägga till eller ta bort ämne- eller mappmallar från globala profiler eller mappnivåprofiler.

Även innan du konfigurerar teman- eller mappmallarna på global nivå eller mappnivå kan du definiera en plats där du kan spara dina anpassade redigeringsmallar. Mer information om hur du konfigurerar en anpassad plats för att lagra redigeringsmallar finns i [Konfigurera en anpassad DITA-mallmappsökväg](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z).

Gör så här för att lägga till ämne- eller mappmallar i en mappprofil:

1. Logga in på Adobe Experience Manager som administratör eller som användare med administratörsbehörighet för en mappnivåprofil.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

1. Klicka på den profilruta som du vill konfigurera.

   >[!NOTE]
   >
   > Du kan välja att konfigurera redigeringsmallen i den globala profilen eller en profil på mappnivå.

1. Klicka på fliken **Redigeringsmall** på profilsidan.
1. Klicka på **Redigera**.

   Du kan lägga till mallar för avsnitt och kartor genom att söka från standardplatsen eller söka efter den.

   >[!NOTE]
   >
   > Som standard lagras alla redigeringsmallar i mappen /content/dam/dita-templates. Mappen `dita-templates` innehåller undermapparna `topics` och `maps` för att lagra ämne- och mappningsmallarna. Du kan lägga till dina egna mallar \(.dita,.xml eller .ditamapfiles\) i standardmallmapparna. När du har lagt till mallen i standardmappen kan du lägga till dem i den globala profilen eller mappprofilen. Mer information om hur du skapar egna mallar med Web Editor finns i [Skapa anpassad redigeringsmall](#id1917D0EG0HJ).

   ![](assets/search-author-temp.png){width="550" align="left"}

1. Lägg till önskade avsnitt och mappningsmallar i din profil.

   Gör något av följande om du vill lägga till en mall:

   - Välj **Sök eller Typ** och ange eller välj namnet på en mall i listrutan. Listrutan består av alla standardmallar och alla nya mallar som du har skapat.

     ![](assets/default-template-list.png){width="350" align="left"}

   - Klicka på **Bläddra** och välj en mall från DAM.

1. Klicka på **Lägg till**.

   De valda mallarna läggs till i malllistan.

   ![](assets/author-templ-added-list.png){width="550" align="left"}

   >[!NOTE]
   >
   > Du kan ändra ordningen på mallarna genom att dra och släppa dem på önskad plats i listan. Mallarnas placering styr i vilken ordning de visas på sidan Utskrift i arbetsflödet för att skapa ämnen eller kartor.

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

Förutom förinställningarna som konfigurerats på global nivå eller företagsnivå har utgivaren fortfarande behörighet att skapa fler förinställningar. Dessa förinställningar är dock kopplade till den DITA-karta som de skapas för. Mer information om hur du skapar förinställningar för vanliga utdata för en DITA-karta finns i *Skapa, redigera, duplicera eller ta bort en förinställning för utdata* i *Använda Adobe Experience Manager Guides*.

Utför följande steg för att konfigurera globala eller mappspecifika förinställningar för utdata:

1. Logga in på Adobe Experience Manager som administratör eller som användare med administratörsbehörighet för en mappspecifik profil.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan med verktyg och klicka på rutan **Mappprofiler** .

1. Klicka på den profilruta som du vill konfigurera.

   >[!NOTE]
   >
   > Du kan välja att konfigurera förinställningar för utdata i den globala profilen eller en mappspecifik profil.

1. På profilsidan. klicka på fliken **Utdatainställningar**.

   En lista med färdiga förinställningar visas, som AEM Site, PDF, HTML 5, EPUB och CUSTOM.

1. Gör något av följande om du vill skapa eller redigera en förinställning för utdata:

   - Klicka på **Skapa** om du vill skapa en ny förinställning från början.
   - Klicka på Duplicera om du vill skapa en kopia av den markerade förinställningen. Du kan ändra den duplicerade förinställningen och spara den.

   - Klicka på **Redigera** för att öppna den markerade förinställningens konfiguration för redigering.

     Mer information om inställningar för förinställningar för utdata finns i *Om förinställningar* i Använda Adobe Experience Manager Guides.

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

   En lista med färdiga förinställningar visas, som AEM Site, PDF, HTML 5, EPUB och CUSTOM.

1. Välj den förinställning för utdata som du vill använda på befintliga DITA-kartor.

1. Klicka på **Använd förinställda ändringar** i huvudverktygsfältet.

1. I dialogrutan Använd förinställda ändringar kan du välja mellan:

   - **Om du väljer alternativet Skriv över befintlig förinställning**: Om du väljer det här alternativet skrivs alla uppdateringar som du har gjort i de befintliga förinställningarna över inställningarna i alla befintliga DITA-mappar där den förinställningen används. Om du gör det förlorar du alla befintliga villkorsstyrda förinställningar och baslinjeinformation som är kopplade till kartan.

   - **Det går inte att välja alternativet Skriv över befintlig förinställning**: Om du inte markerar det här alternativet kommer uppdateringar som du har gjort i de befintliga förinställningarna inte att påverka befintliga DITA-kartor. Endast de nya förinställningarna läggs till i befintliga DITA-kartor. Observera att den nya DITA-kartan får båda, de uppdaterade förinställningarna och de nya förinställningarna.

1. Klicka på **OK** om du vill använda ändringarna från de valda förinställningarna på alla befintliga DITA-kartor.


## Konfigurera och anpassa XML Web Editor {#id2065G300O5Z}

Som standard har XML-webbredigeraren många funktioner som hjälper dina författare att skapa DITA-dokument. Om du arbetar i en begränsande miljö kan du välja vilka funktioner som ska visas för författarna. På fliken Konfiguration i XML-redigeraren kan du enkelt styra funktionerna och även ändra utseendet på Web Editor. Som administratör kan du anpassa följande komponenter i Web Editor:

**Konfiguration av användargränssnitt i XML-redigeraren**

Den här inställningen styr verktygsfältet och andra element i användargränssnittet i Web Editor. Klicka på ikonen **Hämta** för att hämta den senaste filen ui\_config.json på din lokala dator. Du kan sedan ändra filen och överföra den på samma sätt. Klicka på ikonen **Hämta standard** för att hämta standardfilen ui\_config.json på din lokala dator. Du kan alltid hämta standardfilen, göra ändringar i den och överföra den.Beroende på var du överför filen på, global nivå eller på mappnivå tillämpas ändringarna därefter. Mer information om hur du anpassar XML-redigeraren med filen ui\_config.json finns i [Anpassa verktygsfältet](conf-web-editor-customize-toolbar.md#).

**CSS-mallayout**

Ladda ned filen som finns i det här avsnittet för att anpassa dokumentets utseende och känsla när det förhandsgranskas eller öppnas för redigering i Web Editor. CSS-standardfilen som är tillgänglig för hämtning är bara en testfil som inte ska användas för anpassning. Du kan skapa en CSS-fil med anpassningar för Web Editor och överföra samma fil. Du kan till exempel skapa en CSS-fil med följande kod:

```css
.title {    font-size: 9em;}
```

Spara den här filen och överför den i CSS-mallayoutavsnittet. Nästa gång du hämtar filen får du den senaste CSS-filen som används i Web Editor.

**XML-redigerarkodfragment**

Med hjälp av konfigurationsfilen i det här avsnittet kan du skapa vissa standardfragment och dela dem med författarna. Filens standardstruktur anges nedan:

```css
{
   "snippetID": {
      "name": "snippet Name",
      "description": "snippet Description",
      "value": "<i>this is snippet value</i>"
  }
}
```

Följande information krävs för att skapa ett fragment:

- **snippetID:**   Ett unikt ID för fragmentet. Det kan ta ett alfanumeriskt värde.

- **namn:**   Ett beskrivande namn som identifierar fragmentet. Namnet visas på fragmentpanelen.

- **description:**   Lägg till en beskrivande information för fragmentet.

- **värde:**   Ange XML-koden för fragmentet.

>[!NOTE]
>
> Du kan lägga till fler fragment genom att lägga till kommatecken \(,\) i slutet av fragmentdefinitionen och upprepa samma struktur för nästa fragment.

**Versionsetiketter för XML-innehåll**

Som standard kan författare skapa egna etiketter och associera dem med ämnesfilerna. Detta kan dock leda till många variationer av en och samma etikett, t.ex. att etiketterna &quot;Release 1.0&quot;, &quot;Release-1.0&quot; och &quot;release 1&quot; kan användas för att identifiera samma steg i ett ämne. För att undvika sådana inkonsekventa etiketter i systemet kan du skapa en fördefinierad lista med etiketter som författare sedan kan välja mellan. Enhetliga etiketter ger bättre filhantering i systemet.

Med versionsetikettkonfigurationen kan du överföra en lista över giltiga etiketter för din organisation. Hämta filen label.json och ändra den enligt nedan:

```css
{
"label1":"Draft",
"label2":"PM-Review",
"label3":"Engg-Review",
"label4":"QE-Review",
"label5":"Ready for Loc",
"label6":"Ready for Publish"
}
```

I ovanstående exempel är &quot;label1&quot; identifieraren för etikettsekvensen och den läggs till av etiketten som visas för författarna där en etikett behövs. Spara den här filen och ladda upp den i avsnittet Etiketter för XML-innehållsversion.

>[!IMPORTANT]
>
> För att konfigurationer på mappnivå ska börja gälla måste användarna välja profilen under sina användarinställningar i Web Editor.

**Rootmap**

Om dina författare arbetar med en viss rotkarta kan du bläddra till och välja den rotkartan här. Observera att du bara kan definiera rotmappen för en profil på mappnivå.
