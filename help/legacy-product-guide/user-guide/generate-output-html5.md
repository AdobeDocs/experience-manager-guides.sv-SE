---
title: Använd HTML5
description: Lär dig hur du skapar en förinställning för HTML5 från webbredigeraren och kartpanelen. Konfigurera förinställningen HTML5 för utdata i AEM Guides.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 0%

---

# HTML5 {#id205BE700XO1}

HTML5-utdata genereras i en hierarki med platta mappar. Detta innebär att mappstrukturen som används av innehållet i databasen inte replikeras i utdata från HTML5. Hela innehållet publiceras i utdataformat för HTML5 och sparas i en enda mapp. Filnamnen ersätts också med UUID:n för filerna i de genererade utdata. Den enda fil som inte har något UUID-baserat filnamn är filen index.html.

Du kan skapa förinställningen HTML på två sätt:

**Öppna DITA-mappningsfilen i Kartvyn i webbredigeraren:** Öppna DITA-mappningsfilen på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan HTML5 i typlistrutan i dialogrutan Lägg till förinställning.

>[!NOTE]
>
> Du kan välja vilken metod som ska användas för att generera HTML5 med DITA-OT eller FMPS \(om systemadministratören har konfigurerat det\).

I webbredigeraren har konfigurationerna ordnats under flikarna Allmänt och Avancerat:

**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationer:

- Utdatasökväg
- Kommandoradsargument för DITA-OT
- Filnamn
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken Avancerat innehåller följande konfigurationer:

- Transformeringsnamn
- Behåll tillfälliga filer
- Filegenskaper

Mer information finns i [HTML5-konfigurationen](#id231KJA00REJ).

**Från kartkontrollpanelen**

Om du vill öppna förinställningar för utdata för PDF klickar du på en DITA-kartfil i Assets användargränssnitt, klickar på Utdatainställningar och sedan på alternativet HTML 5. Uppdatera de olika konfigurationerna genom att klicka på **Redigera** högst upp på kartkontrollpanelen och sedan på **Spara**.

**HTML5-konfiguration**

Följande alternativ är tillgängliga för utdata från HTML5:

| HTML5-alternativ | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata för HTML5 väljer du HTML 5. |
| Inställningsnamn | Ange ett beskrivande namn för de utdatainställningar för HTML5 som du skapar. Du kan till exempel ange _interna kunders utdata_ eller _slutanvändares utdata_. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om vilka kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/). |
| Generera responsiv med | Välj DITA-OT för att generera utdata från HTML5. |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMakra Publishing Servern stöder inte flera DITAVAL-filer.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om villkorsförinställningar finns i [Använda villkorsförinställningar](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>Du kan markera flera DITAVAL-filer i bläddringsdialogrutan eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM databas där filen lagras. Du kan bara spara DITAVAL-filer. Ett fel visas om du har valt en annan fil.<br><br>**Obs!**: FrameMakra Publishing Servern stöder inte flera DITAVAL-filer. |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över de omvandlingar som är tillgängliga i DITA-OT finns i [DITA-OT-omvandlingar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) i användarhandboken för OASIS DITA-OT. |
| Filnamn | Ange det filnamn som du vill spara HTML5-utdata med.<br><br>**Obs!** Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga HTML5-utdatafilnamnet. Om kartan inte har någon titel används DITA-kartans filnamn för att namnge det slutliga HTML5-resultatet. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som är konfigurerade i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!**: Mer information om hur du skapar ett anpassat arbetsflöde för postutdatagenerering finns i _Anpassa arbetsflöde för efterutdatagenerering_ i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Målsökväg | Den sökväg i AEM där HTML5-utdata lagras. |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.png) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |
| Förenkla filhierarki | Markera alternativet om du vill generera utdata från HTML 5 i en hierarki med platta mappar. Hela innehållet publiceras i utdataformatet HTML5 i en platt filhierarki och sparas i en enda mapp. <br> Om du avmarkerar det här alternativet genereras utdata i en kapslad mapphierarki och hela mappstrukturen replikeras. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Mer information finns i [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF). |
| Filegenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>**Obs!**: Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Överordnat ämne:**[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
