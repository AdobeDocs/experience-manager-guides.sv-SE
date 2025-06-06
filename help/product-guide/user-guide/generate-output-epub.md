---
title: EPUB-förinställning
description: Lär dig hur du skapar en förinställning för EPUB från kartpanelen. Konfigurera förinställningen för EPUB-utdata i Experience Manager Guides.
exl-id: b6fb5483-064e-4552-84c7-b6723b79d8c5
feature: Publishing
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---

# EPUB {#id205BED020YT}

Du kan skapa förinställningen för EPUB från kartkontrollpanelen.

>[!NOTE]
>
> Du kan välja vilken metod som ska användas för att generera EPUB med DITA-OT eller FMPS \(om systemadministratören har konfigurerat det\).

Så här skapar du förinställningen för EPUB från kartpanelen:

1. I Assets-gränssnittet navigerar du till och väljer DITA-kartan för att öppna den på kartkontrollpanelen.
1. Kontrollera att fliken **Utdatainställningar** är markerad.
1. Välj **Skapa** i verktygsfältet.

   Ett nytt formulär för att skapa förinställningar för utdata visas.

1. Ange nödvändig konfigurationsinformation för EPUB-förinställningen.
1. Välj **Klar** om du vill spara förinställningarna.

Följande konfigurationsalternativ är tillgängliga för EPUB-förinställningar:

| EPUB-alternativ | Beskrivning |
| --- | --- |
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata från EPUB väljer du alternativet EPUB. |
| Inställningsnamn | Ange ett beskrivande namn för de EPUB-utdatainställningar som du skapar. Du kan till exempel ange _interna kunders utdata_ eller _slutanvändares utdata_. |
| Kommandoradsargument för DITA-OT | Ange de ytterligare argument som du vill att DITA-OT ska behandla när du genererar utdata. Mer information om vilka kommandoradsargument som stöds i DITA-OT finns i [DITA-OT-dokumentationen](https://www.dita-ot.org/). |
| Generera EPUB med | Välj DITA-OT för att generera EPUB-utdata. |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVal-fil**: Välj DITAVal-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVal-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVal-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchande villkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVal-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVal-filer och ett fel visas om du har valt någon annan filtyp. FrameMaker Publishing Server stöder inte flera DITAVAL-filer.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Målsökväg | Sökvägen i AEM-databasen där EPUB-utdata lagras. |
| Filnamn | Ange det filnamn som du vill spara EPUB-utdata med.<br><br>**Obs!** Om du inte anger något filnamn används DITA-kartans titel för att generera det slutliga EPUB-utdatafilnamnet. Om kartan inte har någon titel används DITA-kartans filnamn för att namnge det slutliga EPUB-resultatet. Filnamnet sanaliseras med de regler som konfigurerats i systemet för att hantera ogiltiga tecken. |
| Transformeringsnamn | Ange vilken typ av utdata du vill generera. Detta är nödvändigt om du vill generera utdata med ett eget anpassat plugin-program, som är integrerat i DITA-OT-plugin-programmet. Om du till exempel vill generera XHTML-utdata anger du `xhtml`. En lista över omvandlingar som är tillgängliga i DITA-OT finns i [DITA-OT-omvandlingar (utdataformat)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) i användarhandboken för OASIS DITA-OT. |
| Rensa tillfälliga DITA-OT-filer | Välj det här alternativet om du vill rensa de temporära filer som genererats av DITA-OT. Platsen där tillfälliga filer lagras i DITA-OT finns i loggen för generering av utdata.<br><br>Om det uppstår fel när du genererar utdata via DITA-OT kan du avmarkera det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!** Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i _Anpassa arbetsflöde för efterhandsgenerering_ i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Egenskaper | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper och tas bort från listrutan. När de har angetts kopieras även dessa egenskaper till avsnitten på kartan.<br><br>**Obs!**: Du kan också skicka metadata till utdata med DITA-OT-publicering. Om du vill ha mer information kan du [skicka metadata till utdata med DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Överordnat ämne:**&#x200B;[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
