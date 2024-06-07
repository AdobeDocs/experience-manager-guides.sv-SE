---
title: Redigera ämnen i Web Editor
description: Lär dig redigera ämnen i webbredigeraren. Lär dig olika redigeringsfunktioner för att ändra ämnesfilerna i AEM.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
feature: Authoring, Web Editor
role: User
source-git-commit: d30f05ff614693beca5d9cf7f206a36f3dadfc8b
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%

---

# Redigera ämnen i Web Editor {#id2056B040VUI}

Webbredigeraren innehåller en rad redigeringsfunktioner som du kan använda för att enkelt skapa och ändra ämnesfiler. Dessutom utför du följande steg för att redigera ett ämne i Web Editor.

>[!IMPORTANT]
>
> Om du råkar ut för ett programfel när du arbetar i Web Editor uppdaterar du sidan för att fortsätta arbeta.

1. Om du vill göra ändringar i ditt ämne klickar du inom textgränsen för det önskade elementet och börjar redigera.

1. Om du vill infoga ett visst element klickar du i slutet av det element efter vilket du vill infoga det nya elementet och klickar på motsvarande elementikon i verktygsfältet. Du kan också använda kortkommandot `Alt+Enter` för att anropa **Infoga element** popup.

   En lista över element som kan användas i ämnet visas. AEM Guides gör en smart placering av element utifrån deras giltiga plats i ämnet.

   >[!NOTE]
   >
   > Du kan också välja vilken ikon som ska visas i verktygsfältet genom att konfigurera `ui_config.json` filen finns på - `/etc/designs/fmdita/clientlibs/xmleditor/`. Kontakta systemadministratören om du vill ha mer information om hur du anpassar funktioner.

1. När du har redigerat dokumentet klickar du **Spara**.

   >[!NOTE]
   >
   > Om du inte vill spara ändringarna i AEM databas klickar du på **Stäng** och klicka sedan på **Stäng utan att spara** i dialogrutan Osparade ändringar.


## Delvis markering av innehåll mellan element

Med stödlinjerna i Experience Manager kan du även markera innehåll över flera element. När du har markerat innehållet kan du utföra följande åtgärder:
- Formatering och borttagning: Gör det markerade innehållet fet, kursiv, understruken eller ta bort det markerade innehållet. Innehållet från de giltiga öppna taggarna sammanfogas sedan och visas under ett enskilt element. Du kan till exempel markera innehållet i ett stycke och utöka markeringen till ett annat stycke. Om du sedan gör det markerade innehållet fetstilt sammanfogas allt fetstilt innehåll från de öppna märkorden och visas under ett enskilt styckeelement.

Om du tar bort det markerade innehållet sammanfogas det återstående innehållet efter borttagningen i de öppna taggarna.

- Omge innehållet med ett giltigt element: Utför följande steg för att omsluta innehållet med ett giltigt element:
   - Markera innehållet i ett element.
   - Välj ![lägg till](images/Add_icon.svg) ikonen från det sekundära verktygsfältet längst upp för att visa **Surround med element** -dialogrutan. I dialogrutan visas giltiga element för det markerade innehållet.
     >[!NOTE]
     >
     > Du kan också visa dialogrutan Surround med element genom att välja snabbmenyn för det markerade innehållet.

   - Välj ett element i dialogrutan. Det markerade innehållet kapslas under det elementet. Om du till exempel markerar innehållet i ett stycke och sedan väljer `<note>` -element från **Omge med element** visas det markerade innehållet under en anteckning.\
     ![dialogrutan för surroundelement](./images/surround-element.png) {width="300" align="left"}

## Uppdatera webbläsaren när filerna redigeras

Guiderna i Experience Manager har stöd för att uppdatera webbläsaren medan du redigerar innehåll i Web Editor. Med den här funktionen kan du fortsätta redigera innehåll om ett programfel skulle uppstå när du arbetar. Om du trycker på Uppdatera i webbläsaren medan en eller flera filer med osparade ändringar öppnas för redigering, får du ett varningsmeddelande om att de osparade ändringarna kan gå förlorade. Du får ett alternativ för att avbryta uppdateringsåtgärden och spara filerna för att bevara ändringarna.

Även när du uppdaterar webbläsaren behålls vyerna till vänster och till höger i webbredigeraren. Stödlinjerna i Experience Manager återställer det senast sparade läget för de filer som öppnats i webbredigeraren när du uppdaterar webbläsaren. De filer som öppnas i databaspanelen öppnas till exempel igen. Kartpanelen behålls tillsammans med den tidigare öppnade kartan.

Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

Den högra panelen öppnas också igen och visar samma vy som före uppdateringen.

## Arbetskopia

AEM innehåller en indikator för arbetskopiering som visar om den aktuella \(arbetskopia\) av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar i den aktuella kopian och inte har sparat filen, visas ett \*-märke tillsammans med titeln på ämnesfliken. Den här indikatorn fungerar som en påminnelse om att spara ändringarna och försvinner när du sparar filen.

![indikator för arbetskopia](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM visar också om den senast sparade kopian av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar som inte har sparats mellan arbetskopian och den senast sparade versionen visas en \*-markering tillsammans med versionsinformationen som visas i det övre högra hörnet på avsnittets filflik. Den här indikatorn fungerar som en påminnelse om att spara och skapa en version av din aktuella \(arbetskopia\) av filen.

![Indikator för versionsuppdatering](images/version-update-indicator.png){width="550" align="left"}




## Leta reda på en öppen fil i databasvyn

När du öppnar en fil i webbredigeraren kan du hitta filen i databasvyn med hjälp av Experience Manager-stödlinjer. Det söker till exempel efter det aktuella ämnet när du redigerar det.

Du kan inaktivera funktionen för att hitta filen med **Hitta alltid filer i databasen** från **Utseende** -fliken i **Användarinställningar**.


**Överordnat ämne:**[ Arbeta med webbredigeraren](web-editor.md)
