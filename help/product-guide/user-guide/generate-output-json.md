---
title: JSON
description: Lär dig hur du skapar JSON-förinställningar från kartkonsolen. Konfigurera förinställning för JSON-utdata i Experience Manager Guides.
exl-id: 9eb426fc-ca0a-4932-8a55-fea731281a0a
feature: Publishing
role: User
source-git-commit: 9ae2690c52ab5408a9d17e9a40a89fe1f902042f
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Så här skapar du JSON-förinställningen från kartkonsolen:

1. [Öppna en DITA-kartfil i kartkonsolen](./open-files-map-console.md).

   Du kan även komma åt kartfilen från widgeten **Senaste filer** i avsnittet [Översikt](./intro-home-page.md#overview). Den markerade kartfilen öppnas i kartkonsolen.
1. Välj ikonen + på fliken **Utdataförinställningar** för att skapa en förinställning.
1. Välj **JSON** i listrutan Typ i dialogrutan **Ny förinställning** .
1. Ange ett namn för den här förinställningen i fältet **Namn**.
1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning i den aktuella mappprofilen. Mappprofilsikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   JSON-förinställningen skapas.

   ![](images/json-preset-dialog-new.png){width="300" align="left"}

När du har skapat förinställningen kan du konfigurera följande förinställda konfigurationer som är tillgängliga på fliken Allmänt.

- Utdatasökväg
- Indexfil
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Behåll tillfälliga filer
- Egenskaper som ska spridas i utdata
- Arbetsflöde efter generering

Mer information finns i [JSON-konfiguration](#json-configuration).

![](images/json-preset-config.png){align="left"}

## JSON-konfiguration

Följande alternativ är tillgängliga för JSON-förinställningen:

>[!NOTE]
>
> Du kan också redigera JSON-filen i Redigeraren.

| JSON-alternativ | Beskrivning |
| --- | --- |
| Utdatasökväg | Den sökväg i din AEM-databas där JSON-utdata lagras. |
| Indexfil | Du kan ge indexfilen ett namn som du skapar för JSON-utdata. Som standard väljs filnamnet för DITA-kartan och ett suffix läggs till (till exempel `map_filename_index.json`).<br><br>Du kan också använda variabler när du ställer in indexfilen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVAL-fil**: Välj DITAVAL-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVAL-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVAL-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVAL-filer och ett fel visas om du har valt någon annan filtyp.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd förinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.svg) för att hämta ZIP-mappen som innehåller de temporära filerna. De hämtade filerna innehåller även `system_config.json`-fil med information om författarens URL, lokal URL och publicerings-URL. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |
| Egenskaper som ska spridas i utdata | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper.<br><br>**Obs!**: Du kan också definiera anpassade egenskaper och skicka metadata till utdata med DITA-OT-publicering. [Arbeta med metadata](metadata-dita.md#id21BJ00QD0XA) om du vill ha mer information. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!** Mer information om hur du skapar ett anpassat arbetsflöde för efterhandsgenerering finns i _Anpassa arbetsflöde för efterhandsgenerering_ i guiden Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |

**Överordnat ämne:**&#x200B;[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
