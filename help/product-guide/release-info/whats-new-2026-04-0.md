---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2026.04.0
description: Läs om de nya och förbättrade funktionerna i version 2026.04.0 av Adobe Experience Manager Guides
role: Leader
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 0%

---

# Nyheter i version 2026.04.0 (april 2026)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2026.04.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2026.04.0](fixed-issues-2026-04-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2026.04.0](../release-info/upgrade-instructions-2026-04-0.md).

## Nu kommer produktutbildningar och kursmaterial i Experience Manager Guides

Innehållsfunktionen **Produktutbildning och inlärning** i Experience Manager Guides gör det möjligt för utbildningsteam och instruktionsdesigners att skapa interaktiva e-learning-kurser direkt från Experience Manager Guides gränssnitt.

![](assets/lc-overview.png)

Med malldriven redigering, interaktiva kurskomponenter och stöd för utvärderingar kan man utveckla högkvalitativt kursmaterial som är anpassat efter organisationens mål.

>[!NOTE]
> 
> Funktionen för produktutbildning och utbildningsinnehåll är inaktiverad som standard för alla instanser av Experience Manager Guides as a Cloud Service. Administratörer kan aktivera den här funktionen på mappprofilnivå från **Workspace-inställningar** > **Allmänt**.

De viktigaste funktionerna är följande:

- Centraliserad hantering av utbildningsmaterial
- Malldriven redigering
- Stöd för återanvändning av innehåll
- Utvärderingsskapande och -hantering
- Webbaserade granskningsflöden
- Branschledande översättningshantering
- Flerkanalspublicering med färdiga SCORM- och PDF-format

Mer information finns i [Komma igång-guiden](../learning-content/course-overview.md) och [Konfigurationsguiden](../lc-config-guide/introduction.md).


## Förbättringar i redigeraren

Följande redigeringsförbättringar har gjorts i den här versionen:

### Förbättringar av panelen Schematron-validering

Följande förbättringar har gjorts i användargränssnittet i Schematron för att ge bättre tydlighet, användbarhet och valideringsresultat:

- På valideringspanelen visas ett meddelande om tomt läge när ingen Schematron-fil läggs till, vilket ger bättre tydlighet och riktning för nästa steg.

  ![](assets/schematron-panel.png){width="350" align="left"}
- När flera Schematron-filer läggs till är de ordnade i ett konsoliderat dragspel, vilket ger bättre synlighet i de konfigurerade Schematron-filerna.

  ![](assets/schematron-panel-error.png){width="350" align="left"}
- Valideringsresultaten kategoriseras nu som `Fatal`, `Error`, `Warn` eller `Info` baserat på det rollattribut som definierats i schemafilen. Varje kategori innehåller ett synligt antal tillsammans med ett sammanhangsberoende verktygstips för tydligare tolkning.

  ![](assets/schematron-validation-errors.png){width="350" align="left"}

Mer information om hur du använder Schematron-filer i Experience Manager Guides finns i [Stöd för Schematron-filer](../user-guide/support-schematron-file.md).

### Översättningsspråkskopior är nu tillgängliga på den högra panelen i redigeringsgränssnittet

Ett nytt **översättningsavsnitt** är nu tillgängligt på den högra panelen under *Filegenskaper* i redigeraren. I det här avsnittet får du direktåtkomst till alla tillgängliga språkkopior för den resurs som är öppen (karta, ämne, bild osv.). Du behöver inte längre navigera till användargränssnittet i Assets för att visa eller komma åt dessa språkkopior.

![](assets/translations-right-panel.png){width="350" align="left"}

För varje språkkopia kan du hovra över filen för att hitta sökvägen i databasen eller helt enkelt markera den för att öppna den i Redigeraren. Förutom att öppna filer kan du även utföra många åtgärder via menyn **Alternativ** . Några av de åtgärder du kan utföra är Redigera, Förhandsgranska, Kopiera UUID, Kopiera sökväg, Lägg till i samlingar och Egenskaper.

Mer information finns i [Högerpanelen i redigeraren](../user-guide/web-editor-right-panel.md#file-properties).


### Sök citat i alla journalfält

Nu kan du söka efter citat i alla journalfält, t.ex. *Titel*, *Journaltitel*, *Författare*, *År*, *Volym*, *Nummer* och *Sidor*, med alternativet **Valfritt fält** i **16}Lägg till citat** . Sökningen returnerar det närmaste matchande citattecknet baserat på den angivna texten.

Mer information om hur du lägger till citat i Experience Manager Guides finns i [Lägg till och hantera citat i ditt innehåll](../user-guide/web-editor-apply-citations.md).

![](assets/add-citations.png){width="350" align="left"}



## Förbättrade granskningar

Följande förbättringar är tillgängliga för granskningsfunktionen i den här versionen:

- När du tilldelar en granskare till en granskningsuppgift beror det nu på ett aktivt projektval. Fältet **Tilldela till** på sidan *Skapa granskningsaktivitet* är inaktiverat tills ett aktivt projekt har valts. När ett projekt har valts aktiveras fältet **Tilldela till** och endast de användare och användargrupper som är associerade med projektet visas. Detta säkerställer att granskningsåtgärder endast tilldelas giltiga projektmedlemmar och förhindrar oavsiktligt val av granskare.

  ![](assets/create-review-task-023.png)

- Fältet **Tilldela till** har nu stöd för typsnittssökning, så att du snabbt kan hitta användare eller användargrupper genom att skriva text.

Tillsammans gör dessa förbättringar att granskningsprocessen blir mer exakt, effektiv och anpassad efter projektspecifika granskningsflöden.

Mer information finns i [Skicka ämnen för granskning](../user-guide/review-send-topics-for-review.md).

## Förbättrad resurshantering

Den här versionen innehåller följande förbättringar av resurshantering:

### Använd Förenkla filhierarki för att hämta kartor med originalfilnamn och associerade metadata

Nu kan du använda filhierarkialternativet Förenkla för att hämta en karta med det ursprungliga filnamnet. Dessutom innehåller det hämtade paketet en `metadata.json`-fil, vilket gör de associerade metadata enkla att komma åt och återanvända utanför Experience Manager Guides.

Mer information om hur du hämtar filer i Experience Manager Guides finns i [Hämta filer](../user-guide/authoring-download-assets.md).

### Använd regex för att aktivera eller inaktivera efterbearbetning

Nu kan du använda regex för att aktivera eller inaktivera efterbearbetning för mappar. Den här förbättringen gör att administratörer kan definiera regler för efterbearbetning som gäller för flera mappar eller hela mapphierarkier med en enda konfiguration, i stället för att ange enskilda mappsökvägar.

Mer information finns i [Använd regex för att aktivera eller inaktivera efterbearbetning](../cs-install-guide/conf-folder-post-processing.md#use-regex-to-enable-or-disable-post-processing).
