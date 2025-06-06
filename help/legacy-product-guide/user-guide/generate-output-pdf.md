---
title: Generera PDF
description: Lär dig hur du skapar en förinställning för PDF från webbredigeraren och kartpanelen. Konfigurera förinställningen för PDF-utdata i AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: fae55104-fef6-4994-911a-139598332b96
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 0%

---

# PDF {#id205BE600HAH}

Du kan skapa förinställningen för PDF på två sätt:

**Öppna DITA-mappningsfilen i Kartvyn i webbredigeraren:** Öppna DITA-mappningsfilen på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan PDF i listrutan Typ i dialogrutan Lägg till förinställning.

>[!NOTE]
>
> Du kan välja vilken metod som ska användas för att generera PDF med DITA-OT, PDF eller FMPS \(om systemadministratören har konfigurerat det\).

I webbredigeraren har konfigurationerna ordnats under flikarna Allmänt och Avancerat:

**Allmänt**

Fliken **Allmänt** innehåller följande konfigurationer:

- Utdatasökväg
- Kommandoradsargument för DITA-OT
- Transformeringsnamn
- PDF Filnamn
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Arbetsflöde efter generering

**Avancerat**

Fliken Avancerat innehåller följande konfigurationer:

- Aktivera versionshantering
- Behåll tillfälliga filer

Mer information finns i [PDF-konfiguration](#id231KIM004X1).

**Från kartkontrollpanelen**

Om du vill öppna förinställningar för utdata för PDF klickar du på en DITA-kartfil i Assets användargränssnitt, klickar på Utdatainställningar och sedan på alternativet PDF. Uppdatera de olika konfigurationerna genom att klicka på **Redigera** högst upp på kartkontrollpanelen och sedan på **Spara**.

**PDF-konfiguration**

Följande alternativ är tillgängliga för PDF Output:

| PDF-alternativ | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata från PDF väljer du alternativet PDF. |
| Inställningsnamn | Ange ett beskrivande namn för de PDF-utdatainställningar som du skapar. Du kan till exempel ange _interna kunders utdata_ eller _slutanvändares utdata_. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om vilka kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/). |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMaker Publishing Server stöder inte flera DITAVAL-filer.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om villkorsförinställningar finns i [Använda villkorsförinställningar](generate-output-use-condition-presets.md#id1825FL004PN). |
| Generera PDF med | Välj DITA-OT för att generera PDF. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!**: Mer information om hur du skapar ett anpassat arbetsflöde för postutdatagenerering finns i Anpassa arbetsflödet för efterutdatagenerering i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över de omvandlingar som är tillgängliga i DITA-OT finns i [DITA-OT-omvandlingar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) i användarhandboken för OASIS DITA-OT. |
| Filnamn | Ange filnamnet som du vill spara PDF med.<br><br>Du kan också använda variabler när du anger filnamnet för PDF. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Obs!** Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga PDF-filnamnet. Om kartan inte har någon titel används DITA-kartans filnamn som namn för den slutliga PDF-filen. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Målsökväg | Sökvägen i AEM-databasen där PDF lagras.<br><br>Du kan också använda variabler när du anger målsökvägen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.png) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Mer information finns i [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF). |
| Filegenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet **Filegenskaper**. Markera kryssikonen bredvid egenskapen för att ta bort den. <br><br>Obs! Du kan också skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Överordnat ämne:**&#x200B;[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
