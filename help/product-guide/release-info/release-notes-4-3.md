---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides 4.3.0
description: Läs om felkorrigeringarna och hur du uppgraderar till 4.3.0-utgåvor av Adobe Experience Manager Guides
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 0%

---

# 4.3.0-utgåvan av Adobe Experience Manager Guides (juli 2023)

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som har åtgärdats i version 4.3.0 av Adobe Experience Manager Guides (kallas senare *AEM Guides*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i 4.3.0-utgåvan av Adobe Experience Manager Guides](./whats-new-4-3-release.md).

## Uppgradera till version 4.3.0 av AEM Guides


Du kan enkelt uppgradera din nuvarande version av AEM Guides till version 4.3.0. Innan du uppgraderar till version 4.3.0 av AEM Guides måste du tänka på följande:
Du kan uppgradera din nuvarande version av AEM Guides till version 4.3.0

- Om du använder version 4.2 eller 4.2.x kan du uppgradera direkt till version 4.3.0.
- Om du använder version 4.1 eller 4.1.x måste du uppgradera till version 4.2 eller 4.2.x innan du uppgraderar till version 4.3.0.
- Om du använder version 4.0 måste du uppgradera till version 4.2 innan du uppgraderar till version 4.3.0.
- Om du använder version 3.8.5 måste du uppgradera till version 4.0 innan du uppgraderar till version 4.2.
- Om du har en tidigare version än 3.8.5, se avsnittet Uppgradera AEM Guides i den produktspecifika installationsguiden.



>[!NOTE]
>
>Du måste installera AEM Service Pack innan du uppgraderar AEM Guides-versionen.

Mer information finns i [Uppgraderingsinstruktioner](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM Guides 4.3.0.

### Adobe Experience Manager

**4.3.0 icke-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 eller 14

**4.3.0 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 eller 14

Mer information finns i avsnittet *Tekniska krav* i guiden Installera och konfigurera Adobe Experience Manager Guides.

### FrameMaker och FrameMaker Publishing Server

| Frigör | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (ej UUID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.3 eller senare |
| 4.3.0 (UID) | 2022 eller senare | 2020.2 eller senare* | 2022 eller senare | 2020.4 eller senare |
| | | | | |

*Baslinje och villkor som skapats i AEM stöds i FMPS-versioner från och med 2020.2.

### Syrgasanslutning

| Frigör | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (ej UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.0 (UID) | 3.0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |  |  |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Ämnesfilen är inte olåst i Web Editor, även om alternativet Lås upp fil och alternativet Spara inte är markerat. (12558)
- Det går inte att checka ut en fil i webbredigeraren, trots att du har valt alternativet NEJ för att ignorera ändringarna före incheckning. 12557
- Verktygstipsen för filikonerna Lås och lås upp i huvudverktygsfältet i Web Editor är inte konsekventa med de ikoner som visas i databasvyn.(12555)
- Alternativet Avbryt utcheckning och Lås upp visas för en fil i Web Editor som ännu inte är utcheckad i Kartvyn. (12556)
- Det går inte att välja PDF-resurser i de befintliga topicref-länkarna. (12477)
- När du sammanfogar och delar i tabeller genererar AEM Guides 4.2 ytterligare tabellceller. 11793
- I databasvyn kan du inte dra ämnen eller bilder efter att du har använt funktionerna Sök/Filter. 12396)
- Sökresultaten inaktiveras på panelen Sök och ersätt när du har öppnat en sökad fil. (12142)
- Siffertangenten &quot;8&quot; på tangentbordet fungerar inte i AEM Guides Editor. (12106)
- Textbundna attribut/visningsattribut visas inte i layoutvyn i Web Editor. 12498
- Konfigurationen för det globala profilanvändargränssnittet matchar inte mappprofilen. (11970)
- Innehållsreferenser bryts när DITA-filer kopieras och klistras in. (11959)
- Det går inte att redigera innehållsfragment i kolumnvyn när AEM Guides är installerat. 7342
- Innehållet förloras när en unwrapped xref finns under en underordnad elementtagg. (12532)
- Arbetsflödet för godkännande fungerar inte när dokumentläget ändras till slutläge från filegenskaperna på den högra panelen. (11026)
- Resursgränssnitt | I listvyn kan de överlagrade tillgängliga kolumnerna inte sammanfogas. (11528)
- Keyref är inte löst i kartvyn. (11490)
- Den övre menyn visas inte när du navigerar i XML-redigeraren. (10868)
- `conref` i ph-taggen | Den visade bläddringsdialogrutan är felaktig. 9481
- Lokala länkar till andra element kan inte lösas i Web Editor. (8790)
- Funktionen Matches() fungerar inte i funktionen Schematron. (11224)



### Förvaltning

- Fältet &quot;title&quot; i DITA-mappningens metadataegenskaper skrivs över av `<title>`-elementet för kartan. (10702)
- När du försöker öppna eller uppdatera versionen av ämnen i baslinjen körs inläsaren &quot;Hämtning av information från servern&quot; oavbrutet.12478


### Granska

- Nytt gränssnitt för granskning | Villkoren markerar och visar hur de fungerar annorlunda än i Web Editor. (11628)

### Publicering

- Publiceringen misslyckas när namnet på en intern PDF-förinställning ändras. (12564)
- När du duplicerar en ursprunglig PDF-mall dupliceras den till standardmallplatsen i stället för den angivna anpassade mallplatsen. 12563
- PDF | Språkmetadata kan inte anges i den genererade PDF så att de överensstämmer med WCAG 2.0. 12407
- Publicering på AEM-webbplats misslyckas när temporära filer från pod som kan ha uppdaterats eller startats om läses. (12113)
- PDF | Anpassade attribut sprids inte till en temporär HTML- eller PDF-motor. (DXML-12005)
- PDF |  Java OutOfMemoryError inträffar vid publicering av stort innehåll. 11789
- PDF | Xref skriver ut innehållet i href-ämnesrubriken i stället för Xref-etiketten. (11322)
- PDF | Det går inte att spara mallinställningarna för PDF. (10751)
- PDF | Texten sträcker sig utanför kolumnbredden och inkluderar flera xrefs. (10876)
- PDF | Elementet `<note>` `</note>` genererar inte någon extra intervalltitel av sin typ. (10549)
- JSON-utdata | Egenskapen `fmUuid` i JSON-noden jcr:content skiljer sig från id:t i JSON. (11564)
- JSON-utdata | Om kartan och ämnet med samma filnamn finns, tas JSON bort för kartan. (11524)

## Känt fel

Adobe har identifierat följande kända problem i AEM Guides 4.3.0:

- En gemensam sidlayout som definieras i den grundläggande mallen används inte som standardmall.

  Lösning:
Lägg till gemensam sidlayout som fram- och baksida och börja sedan komma för varje sida.
- Ett problem uppstår i Webbplatssökning när du söker på AEM webbplats utdatasida i AEM Service Pack 16 eller 17.

  Lösning:

   1. Öppna filen med sökvägen: `/libs/foundation/components/search/search.jsp` i `crx/de`
   1. Ersätt radnummer 234 med följande kod:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Spara filen.
