---
title: Generera PDF med DITA-OT
description: Lär dig hur du skapar en PDF-förinställning med DITA-OT från kartkonsolen och kartkontrollpanelen. Konfigurera förinställningen för PDF-utdata i AEM Guides.
feature: Publishing
role: User
source-git-commit: b970df013a24ca256d7cbd07308367b1207e9163
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 0%

---

# Skapa DITA-OT PDF-utdataförinställning {#id205BE600HAH}

Du kan skapa DITA-OT-förinställningen för PDF-utdata på två sätt:

- [Skapa DITA-OT PDF-förinställningen från kartkonsolen](#create-the-dita-ot-pdf-preset-from-the-map-console)
- [Skapa DITA-OT PDF-förinställningen från kartpanelen](#create-the-dita-ot-pdf-preset-from-the-map-dashboard)

## Skapa DITA-OT PDF-förinställningen från kartkonsolen

Följ de här stegen för att skapa förinställningen för PDF från kartkonsolen:

1. [Öppna en DITA-kartfil i kartkonsolen](./open-files-map-console.md).

   Du kan även komma åt kartfilen från widgeten **Senaste filer** i avsnittet [Översikt](./intro-home-page.md#overview). Den markerade kartfilen öppnas i kartkonsolen.
1. Välj ikonen + på fliken **Utdataförinställningar** för att skapa en förinställning.
1. Välj **PDF** i listrutan Typ i dialogrutan **Ny förinställning** .
1. Ange ett namn för den här förinställningen i fältet **Namn**.
1. I fältet **Skapa PDF med** väljer du **DITA-OT**.
1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning i den aktuella mappprofilen. Mappprofilsikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   Förinställningen för PDF skapas.

   ![](./images/pdf-preset-map-console.png){width="350" align="left"}

I kartkonsolen ordnas de förinställda konfigurationsalternativen för DITA-OT under flikarna **Allmänt** och **Avancerat** i kartkonsolen.

![](./images/dita-ot-preset-config.png){width="350" align="left"}

**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationsalternativ:

- Utdatasökväg
- Kommandoradsargument för DITA-OT
- PDF-filnamn
- Villkorsfiltrering \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken **Avancerat** innehåller följande konfigurationsalternativ:

- Aktivera versionshantering
- Behåll tillfälliga filer
- Filegenskaper

Mer information om konfigurationsalternativ för förinställningar finns i avsnittet [PDF-förinställningskonfiguration](#pdf-preset-configuration).


## Skapa DITA-OT PDF-förinställningen från kartpanelen

Så här skapar du förinställningen för PDF från kartpanelen:

1. I Assets-gränssnittet navigerar du till och väljer DITA-kartan för att öppna den på kartkontrollpanelen.
1. Kontrollera att fliken **Utdatainställningar** är markerad.
1. Välj **Skapa** i verktygsfältet.

   Ett nytt formulär för att skapa förinställningar för utdata visas.

1. Ange nödvändig konfigurationsinformation för PDF-förinställningen.
1. Välj **Klar** om du vill spara förinställningarna.

## PDF-förinställd konfiguration

Konfigurationsalternativen varierar något beroende på om du konfigurerar förinställningen från kartkonsolen eller kartkontrollpanelen. Vissa alternativ gäller bara för kontrollpanelen Karta, medan andra gäller båda.

I de fall där samma konfiguration har två olika fältetiketter avgränsar en **/** dem i tabellen nedan. Den första representerar etiketten i kartkonsolen och den andra representerar etiketten på kartkontrollpanelen.

Exempel: **Utdatasökväg/Målsökväg** - Här är **Utdatasökväg** den etikett som används i kartkonsolen, medan **Målsökväg** är den etikett som används i kartkontrollpanelen för samma konfiguration.

| PDF-alternativ | Beskrivning |
| --- | --- |
| Utdatatyp (*Gäller endast för kontrollpanelen Karta*) | Den typ av utdata som du vill generera. Om du vill generera utdata från PDF väljer du alternativet PDF. |
| Inställningsnamn (*Gäller endast för kartkontrollpanelen*) | Ange ett beskrivande namn för de PDF-utdatainställningar som du skapar. Du kan till exempel ange _interna kunders utdata_ eller _slutanvändares utdata_. |
| Generera PDF med (*Gäller endast för kartpanelen*) | Välj **DITA-OT** om du vill generera PDF-utdata. Välj **FrameMaker Publishing Server** om administratören har konfigurerat det här alternativet. Vissa konfigurationsalternativ varierar när du väljer FMPS. Dessutom är konfigurationsalternativet för FMPS bara tillgängligt på kontrollpanelen för kartor. |
| Utdatasökväg/målsökväg | Sökvägen i AEM-databasen där PDF lagras.<br><br>Du kan också använda variabler när du anger målsökvägen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om vilka kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/). |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över omvandlingar som är tillgängliga i DITA-OT finns i [DITA-OT-omvandlingar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) i användarhandboken för OASIS DITA-OT. |
| PDF filnamn/filnamn | Ange filnamnet som du vill spara PDF med.<br><br>Du kan också använda variabler när du anger filnamnet för PDF. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Obs!** Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga PDF-filnamnet. Om kartan inte har någon titel används DITA-kartans filnamn som namn för den slutliga PDF-filen. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Villkorsstyrd filtrering/Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMaker Publishing Server stöder inte flera DITAVAL-filer.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!** Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i Anpassa arbetsflödet för efterhandsgenerering i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.png) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |
| Filegenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>Obs! Du kan också skicka metadata till utdata med DITA-OT-publicering. Om du vill ha mer information kan du [skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |


**Överordnat ämne:**&#x200B;[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
