---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 4.4.0
description: Läs om de nya och förbättrade funktionerna i version 4.4.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: 57c3b39f0ab0fde5b18e4d4ae0e1501738997e68
workflow-type: tm+mt
source-wordcount: '3050'
ht-degree: 0%

---

# Nyheter i version 4.6.0 (september 2024)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 4.6.0 av Adobe Experience Manager Guides.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 4.6.0](../release-info/fixed-issues-4-6-0.md).

Läs mer om [uppgraderingsinstruktioner för version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).


## Förbättrad publicering

Följande förbättringar av innehållspublicering har gjorts i version 4.6.0:



### Publish ett ämne eller dess element till ett Experience Fragment

En Experience Fragment är en modulär innehållsenhet inom Adobe Experience Manager som integrerar innehåll och layout. Experience Fragments är avgörande för att skapa enhetliga och engagerande upplevelser, som kan återanvändas i flera kanaler. Du kan till exempel skapa upplevelsefragment för sidhuvuden och sidfötter med varumärkeselement, reklambanners, kundutlåtanden och eventkampanjer.

![fliken med alternativ för filegenskaper](./assets/file-properties-outputs-4-6.png) {width="300" align="left"}

*Publish och visa Experience Fragments för ett ämne från avsnittet **Outputs**&#x200B;i **File Properties**.*

Nu kan du publicera ett ämne eller dess element i ett Experience Fragment i Experience Manager Guides. Du kan skapa en JSON-baserad mappning mellan ett ämne eller dess element och en Experience Fragment-mall. Du kan också skapa Experience Fragment-variationer genom att använda villkorsfiltren.

Läs mer om hur du [Publish Experience Fragments](../user-guide/publish-experience-fragment.md).



### Förbättringar i Content Fragment-publiceringen

Experience Manager Guides har även några praktiska förbättringar i Content Fragments:

- Med Experience Manager Guides kan du publicera ett ämne eller dess element i ett innehållsfragment.

- Du kan publicera och visa innehållsfragment för ett ämne i avsnittet **Utdata** i **Filegenskaper**.


- Du kan enkelt skapa varianter av innehållsfragment genom att filtrera innehåll med villkor när du publicerar till ett innehållsfragment.

- Använd det nya mappningsgränssnittet för att enkelt markera och publicera elementen i ett innehållsfragment.

Nu ersätter Content Fragment-publicering bara det mappade innehållet i stället för att skriva över hela innehållsfragmentet. Med den här funktionen kan ett innehållsfragment innehålla data från flera källor, till exempel flera ämnen eller innehållsfragmentets redigerare.

![Lägg till fragmentmodellen och mappningsinformation i dialogrutan Publish som innehållsfragment](assets/content-fragment-mapping.png)

Mer information finns i [Publish Content Fragments](../user-guide/publish-content-fragment.md).

### AEM Sites förinställning har omorganiserats för att bli enkel att använda

Inställningarna har organiserats om för att du snabbt ska kunna konfigurera förinställningarna och generera utdata från AEM Sites.
Du kan skapa de befintliga förinställningarna för AEM Sites genom att välja alternativet **Använd äldre komponentmappning** i dialogrutan **Ny förinställning** .

Visa flikarna **Allmänt**, **Innehåll** och **Korsmappsreferens** i AEM Sites-förinställningarna:
- **Allmänt**: Innehåller allmänna konfigurationer för att generera utdata. Du kan ange plats- och utdatasökväg, ta bort eller skriva över befintliga utdatasidor, ta bort tidigare genererade sidor för borttagna ämnen, välja designmallen, behålla de tillfälliga filerna och ange arbetsflödet efter genereringen.
- **Innehåll**: Innehåller de inställningar som gäller för innehållet för utdatagenerering. Du kan välja filter, baslinje för DITA-kartan och metadataegenskaper för publicering.
- **Tvärmappningsreferenser**: Den här listan innehåller ämnen som innehåller korsmappningsreferenser med scope =&quot;peer&quot;. Du kan ange publiceringskontext för en lista över korsmappsreferenser med scope=&quot;peer&quot; för ämnen som finns i andra DITA-kartor. Den här fliken visas om du använder Experience Manager Guides-versionen (UUID).



### Korsmappsreferenser från AEM Sites-förinställningar i Web Editor

Den senaste förbättringen av Experience Manager Guides innehåller korsmappsreferenser i AEM Sites-förinställningarna i Web Editor.
Korsmappsreferenser i Experience Manager Guides hjälper till att förbättra innehållsnavigeringen, öka återanvändningen av innehåll och förbättra användarupplevelsen.


Du kan ange publiceringskontext för en lista med korsmappningsreferenser till ämnen som är tillgängliga i andra DITA-kartor med scope=&quot;peer&quot;. Ämne 1 i karta A innehåller till exempel en referens till ämne 2. Ämne 2 kan finnas på en eller flera kartor.  Du kan välja den överordnade kartan och en viss förinställning eller de senast publicerade utdata för varje länk.

Om samma ämne refereras till mer än en gång i en fil kan du lägga till olika publiceringskontexter för varje instans. Detta ger större flexibilitet och kontroll över innehållet. Ämne 3 finns t.ex. i både karta B och karta C. Ämne 1 innehåller två referenser till avsnitt 3. Du kan välja Map B som överordnad karta för den första länken och Map C som överordnad för den andra länken.

![Äldre AEM Sites-förinställning](assets/aem-sites-legacy.png)

*Ange publiceringskontext för de länkade avsnitten på fliken **Korsmappningsreferenser**&#x200B;i **AEM Sites**-förinställningen.*






### Möjlighet att skicka metadata från ämnesfilegenskaper till utdata från Native PDF

Nu kan du i Experience Manager Guides lägga till metadata från ett ämnes filegenskaper i sidlayouten när du genererar utdata från PDF. Använd den här funktionen för att lägga till ämnesspecifika metadata som rubrik, taggar och beskrivning i sidlayouterna. Du kan också anpassa det publicerade PDF baserat på ämnets metadata, till exempel lägga till en vattenstämpel till ämnets bakgrund baserat på ämnets dokumenttillstånd.

![lägg till inbyggda metadata-pdf](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Lägg till metadata i fälten i sidlayouterna.*

Lär dig [lägga till fält och metadata](../native-pdf/design-page-layout.md#add-fields-metadata) i en sidlayout.





### Stöd för Markdown-dokument i Native PDF

Experience Manager Guides har också stöd för Markdown-dokument i Native PDF. Den här funktionen är användbar och hjälper dig att generera PDF för Markdown-filerna på DITA-kartan.

Mer information finns i [Stöd för markeringsdokument](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


### Hämta den temporära filen medan du genererar utdata via DITA-OT

Du kan också hämta de temporära filer som genereras när du publicerar utdata från AEM Sites, HTML, Custom, JSON eller PDF via DITA-OT. Med den här funktionen kan du analysera problem som kan uppstå under genereringsprocessen och felsöka effektivt.  
Du kan också hämta filen metadata.xml om du har valt metadataegenskaper som har skickats till utdata som genererats med DITA-OT. 

Mer information om förinställningarna finns i [Om förinställningarna](../user-guide/generate-output-understand-presets.md).


### Alternativ för att antingen välja en platt eller kapslad filhierarki för utdata från HTML5

Nu kan du använda Experience Manager Guides för att behålla den platta mapphierarkin för temporära filer där hela innehållet publiceras i utdataformatet HTML 5 och sparas i en enda mapp.
Om du inte väljer att förenkla filhierarkin skapas utdata från HTML5 i en kapslad mapphierarki. Detta innebär att innehållets ursprungliga mappstruktur, med filer ordnade i undermappar, replikeras i utdata. Den här kapslade mapphierarkin gör det enklare att hantera och navigera i stora datavolymer och det blir därför enklare att ordna och kategorisera filer.


Läs mer om hur du [genererar HTML5-utdata](../user-guide/generate-output-html5.md)


## Förbättringar i redigeraren

Följande redigeringsförbättringar har lagts till i version 4.6.0:

### Skrivskyddad åtkomst till redigerings- och Source-läge för låsta filer

Om en DITA- eller Markdown-fil är låst eller utcheckad av en annan användare kan du inte redigera eller ändra innehållet. Förutom Förhandsgranska kan du även visa den som en skrivskyddad fil i redigeringsläge eller Source-läge.
I skrivskyddat läge kan du visa innehållet tillsammans med taggarna och attributen i **författarläget** eller **Source** och redigera filegenskaperna.

Du kan även komma åt vyn **Layout** för skrivskyddade DITA-kartor.
>[!NOTE]
>
> Mappprofiladministratörerna måste uppdatera *ui_config.json* så att du kan komma åt de skrivskyddade filerna i redigeringsläget, Source- och layoutläget.

![låst filredigerare](./assets/locked-file-editor.png)
*Visa låsta filer i redigeringsläge och Source-läge.*


Lär dig hur du [öppnar låsta filer i redigeringsläge och Source-läge](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).



### Markera delar av innehåll mellan element för åtgärder

Experience Manager Guides gör det enklare att markera innehåll i olika element i Web Editor. Du kan enkelt markera innehåll i olika element och utföra åtgärder som att göra det fet, kursiv och understruken.

Med den här funktionen kan du använda eller ta bort formateringen för delvis markerat innehåll. Du kan också snabbt ta bort innehåll som du har markerat över flera element. När innehållet har tagits bort sammanfogas vid behov det återstående innehållet automatiskt under ett enda giltigt element. Du kan också markera delar av innehåll i flera element och sedan omge innehållet under ett giltigt DITA-element.

På det hela taget ger dessa förbättringar en bättre upplevelse och hjälper dig att arbeta effektivare när du redigerar dokument.
Mer information finns i [Delvis urval av innehåll över element](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).



### Segmenterad lista för att visa och infoga giltiga element utifrån deras position

När du redigerar ett dokument i Web Editor kan du nu visa en delad lista med element som är giltiga på den aktuella platsen och utanför den aktuella platsen. Beroende på dina behov kan du välja ett element bland följande alternativ:

- **Giltiga element på den aktuella platsen** som du kan infoga på den aktuella markörplatsen.
- **Giltiga element utanför den aktuella platsen** som du kan infoga efter någon av de överordnade elementen för det aktuella elementet i elementhierarkin.

![Dialogrutan Infoga element](assets/insert-element-dialog.png){width="300" align="left"}

*Visa de separerade listorna med giltiga element för att infoga ett element på den aktuella platsen.*


Den här delade listan med giltiga element hjälper dig att underhålla innehållsstrukturen och följa DITA-standarderna.

Läs mer om funktionen **Infoga element** i avsnittet [Sekundärt verktygsfält](../user-guide/web-editor-features.md#2051ea0j0y4).


### Förbättrad upplevelse för att söka efter och filtrera filer i databasvyn

Nu får du en bättre upplevelse när du filtrerar filer. Den förbättrade funktionen för att filtrera filer är ett bättre sätt att enkelt söka efter och navigera bland filer.


![söka efter filer i databasvyn](assets/repository-filter-search-2404.png){width="300" align="left"}

*Sök efter filer som innehåller texten`general purpose.`*

Få snabbare åtkomst till relevanta filer och ett mer intuitivt användargränssnitt, vilket gör sökningen smidigare och effektivare.

![snabbsökningsfilter &#x200B;](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Använd snabbfiltren för att söka efter DITA- och icke-DITA-filer.*


>[!NOTE]
>
> Mappprofiladministratörerna måste uppdatera *ui_config.json* så att du kan komma åt den här funktionen på ett harmoniskt sätt.

Läs mer om funktionen **Filtersökning** i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Grupperade villkor för förbättrad innehållsorganisation

I Experience Manager Guides kan du nu gruppera villkor och presentera dem i en kapslad hierarki, så att du kan lägga till flera villkor i en enda grupp. Genom att gruppera villkor kan du bättre ordna och använda dem i hela innehållet.

![villkor ordnade i en kapslad hierarki](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Läs mer om funktionsbeskrivningen för **Villkor** i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Anpassa Web Editor med ett nytt användargränssnitt

Dialogrutan **Användarinställningar** i Web Editor innehåller nu en ny **Utseende**-flik. Med den här nya fliken kan du enkelt konfigurera de vanligaste inställningarna för utseende och känsla i Web Editor-gränssnittet.

Du kan konfigurera så att filerna visas efter namn eller filnamn och ändra temat för programmet och källvyn. Det hjälper dig även att konfigurera inställningarna för att hitta en öppen fil i databasvyn och för att hantera de fasta mellanrummen.

![utseendefliken i användarinställningarna](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Anpassa utseendet enligt dina inställningar.*

Läs mer om funktionsbeskrivningen för **användarinställningar** i avsnittet [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS).


### Leta reda på en öppen fil i databasvyn i Web Editor

Välj alternativet **Leta alltid reda på filer i databasen** i **användarinställningarna** om du snabbt vill navigera och leta reda på filen i databasvyn. Du behöver inte söka manuellt efter den.

När du redigerar kan du med den här funktionen även enkelt visa filens plats i databashierarkin.

Mer information finns i [leta upp en öppen fil i databasvyn](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).

### Förbättrad hantering av hårda blanksteg i Web Editor

I Experience Manager Guides kan du visa en fast mellanslag när du redigerar dokument i Web Editor. Det förbättrar också hanteringen av fasta mellanslag.
Den konverterar flera på varandra följande blanksteg till ett enda blanksteg för att bevara WYSIWYG-vyn av dokumentet i Web Editor. Den här funktionen förbättrar också dokumentets utseende och professionalism.


Mer information finns i [övriga funktioner i Web Editor](../user-guide/web-editor-other-features.md).


### Möjlighet att visa egenskaper för element från elementhierarkin

Innehållsegenskaperna **Typ** visas nu som en listruta. Du kan visa och välja taggarna i hela hierarkin för den aktuella taggen i listrutan.

Med den här listrutan kommer du snabbt åt innehållsegenskaperna för den markerade taggen.


![typmeny i innehållsegenskaper](assets/content-properties-type.png){width="300" align="left"}

*Välj en tagg i hierarkin för den aktuella taggen.*

Läs mer om funktionen **Innehållsegenskaper** i avsnittet [Högerpanel](../user-guide/web-editor-features.md#id2051eb003yk).



### Förbättrade prestanda när flera filer checkas in samtidigt från kartredigeraren

Experience Manager Guides förbättrar prestanda och upplevelsen av incheckningsfunktionen för massfiler i kartredigeraren. Den här förbättringen hjälper dig att checka in flera filer samtidigt snabbare.
Du kan också visa incheckningsförloppet för filerna i dialogrutan **Spara som ny version och Lås upp**. Slutligen visas meddelandet om att åtgärden har slutförts och alla markerade utcheckade filer checkas in.

![Spara som ny version och lås upp dialogruta](./assets/save-version-lock.png){width="300" align="left"}

*Visa listan och statusen för de filer som har checkats in samtidigt från kartredigeraren.*

[Arbeta med den avancerade kartredigeraren](../user-guide/map-editor-advanced-map-editor.md)





## Förbättrad innehållshantering

Hanteringen av innehållets livscykel har förbättrats på följande sätt:

### Möjlighet att översätta innehåll till flera språk med förkonfigurerade språkgrupper

Med Experience Manager Guides kan du nu skapa språkgrupper och enkelt översätta innehåll till flera språk. Med den här funktionen kan du ordna och hantera översättningar efter organisationens behov.

Om du till exempel behöver översätta innehåll för vissa länder i Europa kan du skapa en språkgrupp för europeiska språk som engelska (EN), franska (FR), tyska (DE), spanska (ES) och italienska (IT).



![översättningspanelen](assets/translation-languages-2404.png){width="300" align="left"}

*Välj de språkgrupper eller språk som du vill översätta dina dokument.*

>[!NOTE]
>
>Om målmappen för ett språk saknas eller målspråket är samma som källan, är den nedtonad och visar ett varningstecken.

Som administratör kan du skapa språkgrupper och konfigurera dem till flera mappprofiler. Som författare kan du visa språkgrupperna som är konfigurerade för din mappprofil.


Generellt sett förbättrar möjligheten att skapa språkgrupper effektiviteten och produktiviteten i översättningsprojekt, vilket i slutänden förbättrar lokaliseringsprocessen för flera språk.


Lär dig hur du [översätter dokument från webbredigeraren](../user-guide/translate-documents-web-editor.md).


### Förbättrade prestanda och skalbarhet för stora översättningsprojekt

Översättningsfunktionen är snabbare och mer skalbar än någonsin. Den har en ny arkitektur som ger bättre prestanda. Tiden det tog att skapa projektet är nu snabbare än tidigare och konflikterna under processen är nästan obefintliga. Detta förbättrade resultat hjälper dig med snabbare översättningar och säkerställer smidig drift även för stora översättningsprojekt.

Den här förbättringen är mycket fördelaktig eftersom den förbättrar produktiviteten och den övergripande upplevelsen.

Läs mer om hur du [översätter dokument från webbredigeraren](../user-guide/translate-documents-web-editor.md).

### Ta bort eller inaktivera översättningsprojektet automatiskt efter översättningen

Som administratör kan du nu konfigurera översättningsprojekten så att de inaktiveras eller tas bort automatiskt när översättningen är klar. Med den här funktionen kan du effektivt använda resurser och hantera filer när översättningen är klar.

Om du tar bort ett projekt tas alla filer och mappar i projektet bort permanent. Om du tar bort översättningsprojekten kan du frigöra diskutrymme.

Du kan inaktivera översättningsprojekten om du vill använda dem senare.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Konfigurera språkgrupper och rensningsinställningar för översättningsprojekt.*


Läs mer om hur du [tar bort eller inaktiverar översättningsprojektet](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project) automatiskt.


### Inaktivera efterbearbetning för selektiva mappar i Adobe Experience Manager Assets


Som administratör kan du nu inaktivera efterbearbetning och generering av UUID för selektiva mappar på Experience Manager Assets. Den här konfigurationen kan vara användbar, särskilt när du hanterar många resurser eller komplexa mappstrukturer. Det hjälper även flera användare att snabbt överföra resurserna samtidigt utan att störa varandra.  

Om du inaktiverar efterbearbetning för en mapp påverkas även alla dess underordnade mappar. Experience Manager Guides erbjuder nu möjlighet att selektivt aktivera efterbearbetning för enskilda underordnade mappar i den ignorerade mappen.

Lär dig hur du [inaktiverar efterbearbetning för en mapp](../cs-install-guide/conf-folder-post-processing.md).


## Förbättringar av datakällanslutningar

Följande förbättringar har gjorts i datakällanslutningarna för version 2024.4.0:

### Anslut till datakällorna Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO)

Förutom de befintliga färdiga anslutningarna tillhandahåller Experience Manager Guides även kopplingar för datakällorna Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO). Som administratör kan du hämta och installera dessa anslutningar. Konfigurera sedan de installerade anslutningarna.

### Kopiera och klistra in exempelfrågan för att skapa ett innehållsavdrag eller ämne

Du kan enkelt kopiera och klistra in en exempeldatafråga i generatorn för att skapa ett innehållsavdrag eller ämne. Med den här funktionen behöver du inte komma ihåg syntaxen eller skapa en fråga manuellt. I stället för att skriva frågan manuellt kan du kopiera och klistra in en exempelfråga, redigera den och använda den för att hämta data efter dina behov.

![Dialogrutan Infoga innehållsavdrag](assets/insert-content-snippet.png){width="800" align="left"}

*Kopiera och redigera en exempelfråga för att skapa innehållsavsnittet.*

### Ansluta till JSON-datafiler med en filkoppling


Som administratör kan du nu konfigurera en JSON-filkoppling så att JSON-datafiler används som datakälla. Använd anslutningen för att importera JSON-filerna från datorn eller Adobe Experience Manager Assets. Som författare kan du sedan skapa innehållsfragment eller ämnen med hjälp av generatorerna.

Den här funktionen hjälper dig att använda data som lagras i dina JSON-filer och återanvända dem i olika fragment. Innehållet uppdateras också dynamiskt när du uppdaterar JSON-filerna.

### Konfigurera flera resurs-URL:er för en koppling för att skapa innehållsfragment eller ämnen

Som administratör kan du konfigurera flera resurs-URL:er för vissa anslutningar som Generic REST Client, Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO).

Som författare kan du sedan ansluta till datakällorna för att skapa innehållsfragment eller ämnen med generatorerna. Den här funktionen är användbar eftersom du inte behöver skapa en datakälla för varje URL. Det hjälper dig att snabbt hämta data från någon av resurserna för en viss datakälla i ett enda innehållskuvert eller ämne.

Visa mer information om datakällanslutningarna och hur du [konfigurerar en datakällkoppling från användargränssnittet](../cs-install-guide/conf-data-source-connector-tools.md).

Lär dig hur du [använder data från din datakälla](../user-guide/web-editor-content-snippet.md).

