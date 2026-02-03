---
title: Redigera ämnen i Redigeraren
description: Lär dig redigera ämnen i Redigeraren. Lär dig olika redigeringsfunktioner för att ändra ämnesfilerna i AEM Guides.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
feature: Authoring, Web Editor
role: User
source-git-commit: df3da8a0b4dd50ac177c3b51f04a855e9638058e
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# Redigera ämnen i Redigeraren {#id2056B040VUI}

Redigeraren innehåller en rad redigeringsfunktioner som du kan använda för att enkelt skapa och ändra ämnesfiler. Dessutom utför du följande steg för att redigera ett ämne i redigeraren.

>[!IMPORTANT]
>
> Om du råkar ut för ett programfel när du arbetar i redigeraren uppdaterar du sidan för att fortsätta arbeta.

1. Om du vill göra ändringar i ditt ämne klickar du inom textgränsen för det önskade elementet och börjar redigera.

1. Om du vill infoga ett visst element flyttar du markören i slutet av det element efter vilket du vill infoga det nya elementet och väljer önskad elementikon i verktygsfältet. Du kan också använda kortkommandot `Alt+1` för att öppna popup-fönstret **Infoga element**.

   En lista över element som kan användas i ämnet visas. Experience Manager Guides placerar element på ett intelligent sätt beroende på var de är placerade i ämnet.

   >[!NOTE]
   >
   > Du kan också välja vilken ikon som ska visas i verktygsfältet genom att konfigurera filen `ui_config.json` som finns på - `/etc/designs/fmdita/clientlibs/xmleditor/`. Kontakta systemadministratören om du vill ha mer information om hur du anpassar funktioner.

1. När du är klar med redigeringen av dokumentet väljer du **Spara alla**.

   >[!NOTE]
   >
   > Om du inte vill spara ändringarna i Adobe Experience Manager-databasen väljer du **Stäng** och sedan **Stäng utan att spara** i dialogrutan Osparade ändringar.


## Delvis markering av innehåll mellan element

Med Experience Manager Guides kan du också markera innehåll över flera element. När du har markerat innehållet kan du utföra följande åtgärder:

- Formatering och borttagning: Gör det markerade innehållet fet, kursiv, understruken eller ta bort det markerade innehållet. Innehållet från de giltiga öppna taggarna sammanfogas sedan och visas under ett enskilt element. Du kan till exempel markera innehållet i ett stycke och utöka markeringen till ett annat stycke. Om du sedan gör det markerade innehållet fetstilt sammanfogas allt fetstilt innehåll från de öppna märkorden och visas under ett enskilt styckeelement.

Om du tar bort det markerade innehållet sammanfogas det återstående innehållet efter borttagningen i de öppna taggarna.

- Omge innehållet med ett giltigt element: Utför följande steg för att omsluta innehållet med ett giltigt element:

   - Markera innehållet i ett element.
   - Välj ikonen ![lägg till](images/Add_icon.svg) i verktygsfältet högst upp för att visa dialogrutan **Infoga element** . I dialogrutan visas giltiga element för det markerade innehållet.
     >[!NOTE]
     >
     > Du kan också visa dialogrutan Infoga element genom att välja snabbmenyn för det markerade innehållet.

   - Välj ett element i dialogrutan. Det markerade innehållet kapslas under det elementet. Om du till exempel markerar innehållet i ett stycke och sedan väljer elementet `<note>` i dialogrutan **Infoga element** visas det markerade innehållet under en anteckning.

     ![Dialogrutan Infoga element](./images/insert-element-editor.png) {width="300" align="left"}

## Uppdatera webbläsaren när filerna redigeras

Experience Manager Guides har stöd för att uppdatera webbläsaren medan du redigerar innehållet i Redigeraren. Med den här funktionen kan du fortsätta redigera innehåll om ett programfel skulle uppstå när du arbetar. Om du trycker på Uppdatera i webbläsaren medan en eller flera filer med osparade ändringar öppnas för redigering, får du ett varningsmeddelande om att de osparade ändringarna kan gå förlorade. Du får ett alternativ för att avbryta uppdateringsåtgärden och spara filerna för att bevara ändringarna.

Även när du uppdaterar webbläsaren behålls vyerna till vänster och till höger i Editor. Experience Manager Guides återställer det senast sparade läget för de filer som öppnats i Redigeraren när du uppdaterar webbläsaren. De filer som öppnas i databaspanelen öppnas till exempel igen. Kartpanelen behålls tillsammans med den tidigare öppnade kartan.

Det aktiva ämnet eller DITA-kartan öppnas på nytt i området för innehållsredigering.

Den högra panelen öppnas också igen och visar samma vy som före uppdateringen.

## Arbetskopia

Experience Manager Guides tillhandahåller en indikator för arbetskopian som visar om aktuell \(arbetskopia\) av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar i den aktuella kopian och inte har sparat filen, visas ett \*-märke tillsammans med titeln på ämnesfliken. Den här indikatorn fungerar som en påminnelse om att spara ändringarna och försvinner när du sparar filen.

![indikator för arbetskopia](images/working-copy-text-update-indicator.png){width="550" align="left"}

Experience Manager Guides anger också om den senast sparade \(arbets\) kopian av filen är synkroniserad med den sparade versionen eller inte. Om du har gjort ändringar som inte har sparats mellan arbetskopian och den senast sparade versionen visas en \*-markering tillsammans med versionsinformationen som visas i det övre högra hörnet på avsnittets filflik. Den här indikatorn fungerar som en påminnelse om att spara och skapa en version av din aktuella \(arbetskopia\) av filen.

>[!NOTE]
>
> Alla ändringar i metadatafälten som är tillgängliga under [Filegenskaper](./web-editor-right-panel.md#file-properties) utlöser också indikatorn för arbetskopia i dokumentversionen.

![Versionsuppdateringsindikator](images/version-update-indicator.png){width="550" align="left"}

## Åtkomst till låsta filer i redigeringsläge och Source-läge

När en DITA- eller Markdown-fil är låst eller utcheckad av en annan användare går det inte att redigera eller ändra innehållet. Du kan dock fortfarande visa filen i ett skrivskyddat format i både läget **Författare** och **Source**, utöver läget **Förhandsgranska**.

I skrivskyddat läge kan du visa innehåll, taggar och attribut i **Författarläget** eller **Source** . Du kan också ändra filegenskaperna.

>[!NOTE]
>
> Som administratör får du åtkomst till funktionen **Tvinga upplåsning** som gör att du kan låsa upp en fil som är låst av någon annan.

<!-- This is no more available -->
<!--
The toolbar displays the following icons for read-only access:

- Toggle Tags view
- Version History
- Version Label

Experience Manager Guides also displays a **Read only access** indicator near the version number.
 
![view read only file in author mode](images/locked-file-editor.png)

You can access the **Layout** view for read-only DITA maps. This view lets you see the DITA map and its properties but prevents edits.

>[!NOTE]
>
> Your folder-level administrative users must update *ui_config.json* so that you can harmoniously access the read-only files in the  Author, Source, and Layout modes.

 -->

## Leta reda på en öppen fil i Utforskaren

När du öppnar en fil i Redigeraren innehåller Experience Manager Guides en funktion för att hitta filen i Utforskaren. Det söker till exempel efter det aktuella ämnet när du redigerar det.

Du kan inaktivera funktionen för att hitta filen med alternativet **Hitta alltid filer i Utforskaren** på fliken **Utseende** i **Användarinställningarna**.

>[!NOTE]
>
>Från och med version 2025.11.0 har inställningen **Hitta alltid filer i databasen** bytt namn till **Hitta alltid filer i utforskaren**. Vid lokal installation är den fortfarande tillgänglig som Hitta alltid filer i databasen till version 5.1 av Experience Manager Guides.

**Överordnat ämne:**[ Arbeta med redigeraren](web-editor.md)
