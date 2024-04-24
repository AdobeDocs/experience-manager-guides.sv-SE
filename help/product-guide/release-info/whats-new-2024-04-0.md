---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides, version 2024.4.0
description: Lär dig de nya och förbättrade funktionerna i 2024.4.0-utgåvan av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 0%

---

# Nyheter i version 2024.4.0

I den här artikeln beskrivs de nya och förbättrade funktionerna i version 2024.4.0 av Adobe Experience Manager Guides.

En lista över problem som har åtgärdats i den här versionen finns på [Åtgärdade problem i version 2024.4.0](fixed-issues-2024-04-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2024.4.0](upgrade-instructions-2024-04-0.md).

## Möjlighet att översätta innehåll till flera språk med förkonfigurerade språkgrupper

Nu kan du skapa språkgrupper och enkelt översätta innehåll till flera språk med hjälp av guiderna i Experience Manager. Med den här funktionen kan du ordna och hantera översättningar efter organisationens behov.

Om du till exempel behöver översätta innehåll för vissa länder i Europa kan du skapa en språkgrupp för europeiska språk som engelska (EN), franska (FR), tyska (DE), spanska (ES) och italienska (IT).



![översättningspanel](assets/translation-languages-2404.png){width="300" align="left"}

*Välj de språkgrupper eller språk som du vill översätta dina dokument.*

>[!NOTE]
>
>Om målmappen för ett språk saknas eller målspråket är samma som källan, är den nedtonad och visar ett varningstecken.

Som administratör kan du skapa språkgrupper och konfigurera dem till flera mappprofiler. Som författare kan du visa språkgrupperna som är konfigurerade för din mappprofil.


Generellt sett förbättrar möjligheten att skapa språkgrupper effektiviteten och produktiviteten i översättningsprojekt, vilket i slutänden förbättrar lokaliseringsprocessen för flera språk.


Lär dig hur [översätta dokument från webbredigeraren](../user-guide/translate-documents-web-editor.md).



## Ta bort eller inaktivera översättningsprojektet automatiskt efter översättningen

Som administratör kan du nu konfigurera översättningsprojekten så att de inaktiveras eller tas bort automatiskt när översättningen är klar. Med den här funktionen kan du effektivt använda resurser och hantera filer när översättningen är klar.

Om du tar bort ett projekt tas alla filer och mappar i projektet bort permanent. Om du tar bort översättningsprojekten kan du frigöra diskutrymme.

Du kan inaktivera översättningsprojekten om du vill använda dem senare.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Konfigurera språkgrupper och rensningsinställningar för översättningsprojekt.*


Läs mer om hur [tar bort eller inaktiverar översättningsprojektet automatiskt](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Aktivera utdata för dina kartor i en gruppaktiveringssamling i Preview-instansen

Förutom att aktivera utdata för din massaktiveringssamling på publiceringsinstansen har Experience Manager Gudies as Cloud Services funktionen som aktiverar den på **Förhandsgranska** -instans.


Med den här funktionen kan du aktivera ditt innehåll till en förhandsvisningsinstans, så att du kan kontrollera hur det ser ut och fungerar innan du aktiverar det till **Publicera** -instans.


![ skapad granskningsflik för massaktiveringssamling](assets/bulk-collection-audit-history.png){width="800" align="left"}

*Visa information om aktiverade kartutdata i dialogrutan **Granska historik**-fliken.*


Läs mer om  [massaktivering](../user-guide/conf-bulk-activation-publish-map-collection.md).

## Förbättringar av datakällanslutningar

Följande förbättringar har gjorts i datakällanslutningarna för version 2024.4.0:

### Anslut till datakällorna Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO)

Förutom de befintliga färdiga anslutningarna har Experience Manager Guides även kopplingar för datakällorna Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO). Som administratör kan du hämta och installera dessa anslutningar. Konfigurera sedan de installerade anslutningarna.

### Kopiera och klistra in exempelfrågan för att skapa ett innehållsavdrag eller ämne

Du kan enkelt kopiera och klistra in en exempeldatafråga i generatorn för att skapa ett innehållsavdrag eller ämne. Med den här funktionen behöver du inte komma ihåg syntaxen eller skapa en fråga manuellt. I stället för att skriva frågan manuellt kan du kopiera och klistra in en exempelfråga, redigera den och använda den för att hämta data efter dina behov.

![Infoga innehållsfragment, dialogruta](assets/insert-content-snippet.png){width="800" align="left"}

*Kopiera och redigera en exempelfråga för att skapa innehållsfragmentet.*

### Ansluta till JSON-datafiler med en filkoppling


Som administratör kan du nu konfigurera en JSON-filkoppling så att JSON-datafiler används som datakälla. Använd anslutningen för att importera JSON-filerna från datorn eller Adobe Experience Manager Assets. Som författare kan du sedan skapa innehållsfragment eller ämnen med hjälp av generatorerna.

Den här funktionen hjälper dig att använda data som lagras i dina JSON-filer och återanvända dem i olika fragment. Innehållet uppdateras också dynamiskt när du uppdaterar JSON-filerna.

### Konfigurera flera resurs-URL:er för en koppling för att skapa innehållsfragment eller ämnen

Som administratör kan du konfigurera flera resurs-URL:er för vissa anslutningar som Generic REST Client, Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO).

Som författare kan du sedan ansluta till datakällorna för att skapa innehållsfragment eller ämnen med generatorerna. Den här funktionen är användbar eftersom du inte behöver skapa en datakälla för varje URL. Det hjälper dig att snabbt hämta data från någon av resurserna för en viss datakälla i ett enda innehållskuvert eller ämne.

Visa mer information om datakällanslutningar och hur [konfigurera en datakällanslutning från användargränssnittet](../cs-install-guide/conf-data-source-connector-tools.md).

Lär dig hur [använda data från datakällan](../user-guide/web-editor-content-snippet.md).

## Anpassa Web Editor med nya användargränssnitt

The **Användarinställningar** i Web Editor finns nu en ny **Utseende** -fliken. Med den här nya fliken kan du enkelt konfigurera de vanligaste inställningarna för utseende och känsla i Web Editor-gränssnittet.

Du kan konfigurera så att filerna visas efter namn eller filnamn och ändra temat för programmet och källvyn. Det hjälper dig även att konfigurera inställningarna för att hitta en öppen fil i databasvyn och för att hantera de fasta mellanrummen.

![utseendeflik i användarinställningar](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Anpassa utseendet enligt dina önskemål.*

Läs mer om **Användarinställningar** funktionsbeskrivning i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

## Leta reda på en öppen fil i databasvyn i Web Editor

Välj **Hitta alltid filer i databasen** i **Användarinställningar** för att snabbt navigera och hitta filen i databasvyn. Du behöver inte söka efter den manuellt.

När du redigerar kan du med den här funktionen även enkelt visa filens plats i databashierarkin.

Mer information finns i [leta upp en öppen fil i databasvyn](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Förbättrad hantering av hårda blanksteg i Web Editor

Med hjälp av stödlinjerna i Experience Manager kan du visa ett fast mellanslag när du redigerar dokument i Web Editor. Det förbättrar också hanteringen av fasta mellanslag.
Den konverterar flera på varandra följande blanksteg till ett enda blanksteg för att bevara dokumentets WYSIWYG-vy i Web Editor. Den här funktionen förbättrar också dokumentets utseende och professionalism.


Mer information finns i [andra funktioner i Web Editor](../user-guide/web-editor-other-features.md).




## Inaktivera efterbearbetning för selektiva mappar i Adobe Experience Manager Assets


Som administratör kan du nu inaktivera efterbearbetning och generering av UUID för selektiva mappar på Experience Manager Assets. Den här konfigurationen kan vara användbar, särskilt när du hanterar många resurser eller komplexa mappstrukturer. Det hjälper även flera användare att snabbt överföra resurserna samtidigt utan att störa varandra.  

Om du inaktiverar efterbearbetning för en mapp påverkas även alla dess underordnade mappar. Nu kan du använda Experience Manager-stödlinjer till att selektivt aktivera efterbearbetning för enskilda underordnade mappar i den ignorerade mappen.

Lär dig hur [inaktivera efterbearbetning för en mapp](../cs-install-guide/conf-folder-post-processing.md).

## Förbättrad upplevelse för att söka efter och filtrera filer i databasvyn

Nu får du en bättre upplevelse när du filtrerar filer. Den förbättrade funktionen för att filtrera filer är ett bättre sätt att enkelt söka efter och navigera bland filer.


![sökfiler i databasvyn](assets/repository-filter-search-2404.png){width="300" align="left"}

*Sök efter filerna som innehåller texten`general purpose.`*

Få snabbare åtkomst till relevanta filer och ett mer intuitivt användargränssnitt, vilket gör sökningen smidigare och effektivare.

![snabbsökningsfilter ](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Använd snabbfiltren för att söka efter DITA- och icke-DITA-filer.*

Läs mer om **Filtersökning** i [Vänster panel](../user-guide/web-editor-features.md#id2051EA0M0HS) -avsnitt.

## Segmenterad lista för att visa och infoga giltiga element utifrån deras position

När du redigerar ett dokument i Web Editor kan du nu visa en delad lista med element som är giltiga på den aktuella platsen och utanför den aktuella platsen. Beroende på dina behov kan du välja ett element bland följande alternativ:

* **Giltiga element på den aktuella platsen** som du kan infoga vid den aktuella markörplatsen.
* **Giltiga element utanför den aktuella platsen** som du kan infoga efter någon av de överordnade elementen för det aktuella elementet i elementhierarkin.

![Dialogrutan Infoga element](assets/insert-element-dialog.png){width="300" align="left"}

*Visa de separerade listorna med giltiga element om du vill infoga ett element på den aktuella platsen.*


Den här delade listan med giltiga element hjälper dig att underhålla innehållsstrukturen och följa DITA-standarderna.

Läs mer om **Infoga element** i [Sekundärt verktygsfält](../user-guide/web-editor-features.md#2051ea0j0y4) -avsnitt.


## Innehållsegenskapstyp visas som en listruta

Innehållsegenskaperna **Typ** visas som en listruta. Du kan visa och välja taggarna i hela hierarkin för den aktuella taggen i listrutan.

Med den här listrutan kommer du snabbt åt de relevanta taggarna i den hierarkiska strukturen.


![listrutemeny av typen i innehållsegenskaper](assets/content-properties-type.png){width="300" align="left"}

*Välj en tagg i hierarkin för den aktuella taggen.*

Läs mer om **Innehållsegenskaper** i [Höger panel](../user-guide/web-editor-features.md#id2051eb003yk) -avsnitt.



## Förbättrade prestanda vid gruppkontroll av filer från kartredigeraren

Experience Manager-stödlinjerna förbättrar prestanda och upplevelsen av incheckningsfunktionen för gruppfiler i kartredigeraren. Den här förbättringen hjälper dig att checka in flera filer samtidigt snabbare.
Du kan även visa incheckningsåtgärdens förlopp för filerna från **Spara som ny version och lås upp** -dialogrutan. Slutligen visas meddelandet om att åtgärden har slutförts och alla markerade utcheckade filer checkas in.

![Spara som ny version och lås upp dialogruta](./assets/save-version-lock.png){width="300" align="left"}

*Visa listan och statusen för de filer som har checkats in samtidigt i kartredigeraren.*

Lär dig hur [arbeta med Avancerad kartredigerare](../user-guide/map-editor-advanced-map-editor.md)

## Hämta den temporära filen medan du genererar utdata via DITA-OT

Du kan också hämta de temporära filer som genereras när du publicerar AEM Site, HTML, Custom, JSON eller PDF via DITA-OT. Med den här funktionen kan du analysera problem som kan uppstå under genereringsprocessen och felsöka effektivt.  
Du kan också hämta filen metadata.xml om du har valt metadataegenskaper som har skickats till utdata som genererats med DITA-OT. 

Mer information om förinställningarna finns i [Förinställningar för utdata](../user-guide/generate-output-understand-presets.md).


## Ersätt IMS JWT-autentiseringsuppgifter med IMS OAuth-autentiseringsuppgifter för Microservice-baserad publicering


JWT-autentiseringsuppgifterna (Service Account) har ersatts med **OAuth Server-till-server** autentiseringsuppgifter. Dina program som använder JWT-inloggningsuppgifterna (Service Account) slutar fungera efter 1 januari 2025. Du måste migrera till de nya autentiseringsuppgifterna senast 1 januari 2025 för att programmet ska fortsätta fungera.


Molnpubliceringstjänsten för Experience Manager Guides skyddas nu av OAuth-baserad autentisering i Adobe IMS. Lär dig hur [konfigurera mikrotjänstbaserad publicering med OAuth-autentisering](../knowledge-base/publishing/configure-microservices-imt-config.md).

