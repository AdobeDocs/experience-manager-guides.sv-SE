---
title: Redigera ämnen i Web Editor
description: Lär dig redigera ämnen i webbredigeraren. Lär dig olika redigeringsfunktioner för att ändra ämnesfilerna i AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 0341bdec-9635-4ced-b1c6-789b4e1aded8
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 0%

---

# Redigera ämnen i Web Editor {#id2056B040VUI}

Webbredigeraren innehåller en rad redigeringsfunktioner som du kan använda för att enkelt skapa och ändra ämnesfiler. Dessutom utför du följande steg för att redigera ett ämne i Web Editor.

>[!IMPORTANT]
>
> Om du råkar ut för ett programfel när du arbetar i Web Editor uppdaterar du sidan för att fortsätta arbeta.

1. Om du vill göra ändringar i ditt ämne klickar du inom textgränsen för det önskade elementet och börjar redigera.

1. Om du vill infoga ett visst element klickar du i slutet av det element efter vilket du vill infoga det nya elementet och klickar på motsvarande elementikon i verktygsfältet. Du kan också använda kortkommandot `Alt+Enter` för att öppna popup-fönstret **Infoga element**.

   En lista över element som kan användas i ämnet visas. AEM Guides placerar element på ett intelligent sätt beroende på var de är placerade i ämnet.

   >[!NOTE]
   >
   > Du kan också välja vilken ikon som ska visas i verktygsfältet genom att konfigurera filen `ui_config.json` som finns på - `/etc/designs/fmdita/clientlibs/xmleditor/`. Kontakta systemadministratören om du vill ha mer information om hur du anpassar funktioner.

1. När du är klar med redigeringen av dokumentet klickar du på **Spara**.

   >[!NOTE]
   >
   > Om du inte vill spara ändringarna i AEM-databasen klickar du på **Stäng** och sedan på **Stäng utan att spara** i dialogrutan Osparade ändringar.


## Delvis markering av innehåll mellan element

Med Experience Manager Guides kan du också markera innehåll över flera element. När du har markerat innehållet kan du utföra följande åtgärder:

- Formatering och borttagning: Gör det markerade innehållet fet, kursiv, understruken eller ta bort det markerade innehållet. Innehållet från de giltiga öppna taggarna sammanfogas sedan och visas under ett enskilt element. Du kan till exempel markera innehållet i ett stycke och utöka markeringen till ett annat stycke. Om du sedan gör det markerade innehållet fetstilt sammanfogas allt fetstilt innehåll från de öppna märkorden och visas under ett enskilt styckeelement.

Om du tar bort det markerade innehållet sammanfogas det återstående innehållet efter borttagningen i de öppna taggarna.

- Omge innehållet med ett giltigt element: Utför följande steg för att omsluta innehållet med ett giltigt element:

   - Markera innehållet i ett element.
   - Välj ikonen ![lägg till](images/Add_icon.svg) i det sekundära verktygsfältet högst upp för att visa dialogrutan **Surround with Element** . I dialogrutan visas giltiga element för det markerade innehållet.
     >[!NOTE]
     >
     > Du kan också visa dialogrutan Surround med element genom att välja snabbmenyn för det markerade innehållet.

   - Välj ett element i dialogrutan. Det markerade innehållet kapslas under det elementet. Om du till exempel markerar innehållet i ett stycke och sedan väljer elementet `<note>` i dialogrutan **Surround with element** visas det markerade innehållet under en anteckning.\
     ![Dialogrutan för surroundelement](./images/surround-element.png) {width="300" align="left"}

## Uppdatera webbläsaren när filerna redigeras

Experience Manager Guides har stöd för att uppdatera webbläsaren medan du redigerar innehållet i Web Editor. Med den här funktionen kan du fortsätta redigera innehåll om ett programfel skulle uppstå när du arbetar. Om du trycker på Uppdatera i webbläsaren medan en eller flera filer med osparade ändringar öppnas för redigering, får du ett varningsmeddelande om att de osparade ändringarna kan gå förlorade. Du får ett alternativ för att avbryta uppdateringsåtgärden och spara filerna för att bevara ändringarna.

Även när du uppdaterar webbläsaren behålls vyerna till vänster och till höger i webbredigeraren. Experience Manager Guides återställer det senast sparade läget för de filer som öppnats i Web Editor när du uppdaterar webbläsaren. De filer som öppnas i databaspanelen öppnas till exempel igen. Kartpanelen behålls tillsammans med den tidigare öppnade kartan.

Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

Den högra panelen öppnas också igen och visar samma vy som före uppdateringen.

## Arbetskopia

AEM Guides tillhandahåller en indikator för arbetskopian som visar om aktuell \(arbetskopia\) av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar i den aktuella kopian och inte har sparat filen, visas ett \*-märke tillsammans med titeln på ämnesfliken. Den här indikatorn fungerar som en påminnelse om att spara ändringarna och försvinner när du sparar filen.

![indikator för arbetskopia](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM Guides anger också om den senast sparade \(arbets\) kopian av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar som inte har sparats mellan arbetskopian och den senast sparade versionen visas en \*-markering tillsammans med versionsinformationen som visas i det övre högra hörnet på avsnittets filflik. Den här indikatorn fungerar som en påminnelse om att spara och skapa en version av din aktuella \(arbetskopia\) av filen.

![Versionsuppdateringsindikator](images/version-update-indicator.png){width="550" align="left"}


## Öppna låsta filer i redigeringsläge och Source-läge

När en DITA- eller Markdown-fil är låst eller utcheckad av en annan användare går det inte att redigera eller ändra innehållet. Du kan dock fortfarande visa filen i ett skrivskyddat format i både läget **Författare** och **Source**, utöver läget **Förhandsgranska**.

I skrivskyddat läge kan du visa innehåll, taggar och attribut i **Författarläget** eller **Source** . Du kan också ändra filegenskaperna.

I verktygsfältet visas följande ikoner för skrivskyddad åtkomst:

- Växla taggvy
- Tidigare versioner
- Versionsetikett

Experience Manager Guides visar även en **skrivskyddad åtkomstindikator** nära versionsnumret.

![visa skrivskyddad fil i redigeringsläge](images/locked-file-editor.png)

Du kan öppna vyn **Layout** för skrivskyddade DITA-kartor. I den här vyn kan du se DITA-kartan och dess egenskaper, men förhindrar redigeringar.

>[!NOTE]
>
> Administrativa användare på mappnivå måste uppdatera *ui_config.json* så att du kan komma åt de skrivskyddade filerna i redigeringsläget, Source- och layoutläget.

## Leta reda på en öppen fil i databasvyn

När du öppnar en fil i Web Editor kan du använda Experience Manager Guides för att leta upp filen i databasvyn. Det söker till exempel efter det aktuella ämnet när du redigerar det.

Du kan inaktivera funktionen för att hitta filen med alternativet **Hitta alltid filer i databasen** på fliken **Utseende** i **Användarinställningarna**.


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
