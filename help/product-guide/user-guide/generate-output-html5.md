---
title: Använd HTML5
description: Lär dig hur du skapar en förinställning för HTML5 från kartkonsolen och kartkontrollpanelen. Konfigurera förinställningen för HTML5-utdata i AEM Guides.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
feature: Publishing
role: User
source-git-commit: e1d6123991ddd8d25f76ee03befeb95f020a9834
workflow-type: tm+mt
source-wordcount: '1509'
ht-degree: 0%

---

# HTML5 {#id205BE700XO1}

Du kan skapa förinställningen för utdata från HTML5 för att publicera utdata med DITA-OT och FMPS (om det har konfigurerats av administratören).

Du kan skapa förinställningen för HTML5 på två sätt:

- [Skapa förinställning för utdata från HTML5 från kartkonsolen](#create-html5-output-preset-from-the-map-console)
- [Skapa förinställning för utdata från HTML5 från kontrollpanelen för kartor](#create-html5-output-preset-from-the-map-dashboard)

## Skapa förinställning för utdata från HTML5 från kartkonsolen

Så här skapar du förinställningen för HTML5 från kartkonsolen:

1. [Öppna en DITA-kartfil i kartkonsolen](./open-files-map-console.md).

   Du kan även komma åt kartfilen från widgeten **Senaste filer** i avsnittet [Översikt](./intro-home-page.md#overview). Den markerade kartfilen öppnas i kartkonsolen.
1. Välj ikonen + på fliken **Utdataförinställningar** för att skapa en förinställning.
1. Välj **HTML5** i listrutan Typ i dialogrutan **Ny förinställning** .
1. Ange ett namn för den här förinställningen i fältet **Namn**.
1. I fältet **Skapa HTML med** väljer du DITA-OT.
1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning i den aktuella mappprofilen. Mappprofilsikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   Förinställningen för HTML5 skapas.

   ![](images/html5-preset-dialog-new.png){width="300" align="left"}

I kartkonsolen ordnas de förinställda konfigurationsalternativen under flikarna **Allmänt** och **Avancerat**.

Fliken **Allmänt** innehåller följande konfigurationsalternativ:

- Utdatasökväg
- Kommandoradsargument för DITA-OT
- Filnamn
- Villkorsfiltrering \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken Avancerat innehåller följande konfigurationsalternativ:

- Transformeringsnamn
- Behåll tillfälliga filer
- Förenkla filhierarki
- Filegenskaper

Mer information om konfigurationsalternativ för förinställningar finns i avsnittet [HTML5-förinställningskonfiguration](#html5-preset-configuration).

## Skapa förinställning för utdata från HTML5 från kontrollpanelen för kartor

Så här skapar du förinställningen för HTML5 från kontrollpanelen Karta:

1. I Assets-gränssnittet navigerar du till och väljer DITA-kartan för att öppna den på kartkontrollpanelen.
1. Kontrollera att fliken **Utdatainställningar** är markerad.
1. Välj **Skapa** i verktygsfältet.

   Ett nytt formulär för att skapa förinställningar för utdata visas.

1. Ange nödvändig konfigurationsinformation för HTML5-förinställningen.
1. Välj **Klar** om du vill spara förinställningarna.

Mer information om konfigurationsalternativ för förinställningar finns i avsnittet [HTML5-förinställningskonfiguration](#html5-preset-configuration).

## HTML5-förinställningskonfiguration

Konfigurationsalternativen varierar något beroende på om du konfigurerar förinställningen från kartkonsolen eller kartkontrollpanelen. Vissa alternativ gäller bara för kontrollpanelen Karta, medan andra gäller båda.

I de fall där samma konfiguration har två olika fältetiketter avgränsar en **/** dem i tabellen nedan. Den första representerar etiketten i kartkonsolen och den andra representerar etiketten på kartkontrollpanelen.

Exempel: **Utdatasökväg/Målsökväg** - Här är **Utdatasökväg** den etikett som används i kartkonsolen, medan **Målsökväg** är den etikett som används i kartkontrollpanelen för samma konfiguration.

| HTML5-alternativ | Beskrivning |
| --- | --- |
| Utdatatyp (*Gäller endast för kontrollpanelen Karta*) | Den typ av utdata som du vill generera. Om du vill generera utdata från HTML5 väljer du alternativet HTML5. |
| Inställningsnamn (*Gäller endast för kartkontrollpanelen*) | Ange ett beskrivande namn för de HTML5-utdatainställningar som du skapar. Du kan till exempel ange _interna kunders utdata_ eller _slutanvändares utdata_. |
| Generera responsiv med (*Gäller endast för kontrollpanelen Karta*) | Välj **DITA-OT** om du vill generera HTML5-utdata. Välj **FrameMaker Publishing Server** om administratören har konfigurerat det här alternativet. Vissa konfigurationsalternativ varierar när du väljer FMPS. |
| Utdatasökväg/målsökväg | Den sökväg i din AEM-databas där HTML5-utdata lagras. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. <br><br> Obs! Från och med version 2502 av Experience Manager Guides hanteras parametern `generate.copy.outer` inte längre internt. Den här ändringen innebär att om ditt HTML5-innehåll ligger utanför mappningskatalogen måste du explicit ange parametern `-Dgenerate.copy.outer=3` i fältet **DITA-OT Command Line Arguments**. Detta säkerställer att innehållet bearbetas korrekt och inkluderas i utdata. Mer information om hur du hanterar innehåll utanför mappningskatalogen finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/dev/parameters/generate-copy-outer#:~:text=The%20generate.,located%20outside%20the%20map%20directory/). |
| Filnamn | Ange det filnamn med vilket du vill spara HTML5-utdata.<br><br>**Obs!** Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga utdatafilnamnet för HTML5. Om kartan inte har någon titel används DITA-kartans filnamn för att namnge det slutliga HTML5-resultatet. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Villkorsfiltrering/Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMaker Publishing Server stöder inte flera DITAVAL-filer.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar.<br><br>Du kan markera flera DITAVAL-filer i bläddringsdialogrutan eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara spara DITAVAL-filer. Ett fel visas om du har valt en annan fil.<br><br>**Obs!**: FrameMaker Publishing Server stöder inte flera DITAVAL-filer. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!** Om du vill ha mer information om hur du skapar ett anpassat arbetsflöde för postutdatagenerering läser du _Anpassa arbetsflöde för efterhandsutdatagenerering_ i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över omvandlingar som är tillgängliga i DITA-OT finns i [DITA-OT-omvandlingar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) i användarhandboken för OASIS DITA-OT. |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.svg) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Förenkla filhierarki | Välj alternativet för att generera HTML5-utdata i en hierarki med platta mappar. Hela innehållet publiceras i utdataformatet HTML5 i en platt filhierarki och sparas i en enda mapp. <br> Om du avmarkerar det här alternativet genereras utdata i en kapslad mapphierarki och hela mappstrukturen replikeras. |
| Filegenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>**Obs!**: Du kan också skicka metadata till utdata med DITA-OT-publicering. Om du vill ha mer information kan du [skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |







**Överordnat ämne:**&#x200B;[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
