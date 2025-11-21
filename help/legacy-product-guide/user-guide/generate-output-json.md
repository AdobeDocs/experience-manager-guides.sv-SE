---
title: JSON
description: Lär dig hur du skapar JSON-förinställningar från webbredigeraren och kartkontrollpanelen. Konfigurera förinställning för JSON-utdata i AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: dbc082e9-e75e-414d-a1d1-41f919b345af
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Du kan skapa JSON-förinställningen från Web Editor:

Öppna DITA-schemafilen i Kartvyn på panelen Databas, välj ikonen + på fliken Utdata för att skapa en förinställning och välj sedan JSON i listrutan typ i dialogrutan Lägg till förinställning.

Följande konfigurationer har organiserats under fliken **Allmänt** i webbredigeraren:

- Utdatasökväg
- Indexfil
- Använd villkor med \(Om villkoren är definierade för en karta\)
- Använd baslinje \(Om en baslinje skapas för en karta\)
- Behåll tillfälliga filer
- Egenskaper att sprida i utdata
- Arbetsflöde efter generering

Mer information finns i [JSON-konfiguration](#id231KJA00REJ).


**JSON-konfiguration**

Följande alternativ är tillgängliga för JSON-förinställningen:

>[!NOTE]
>
> Du kan också redigera JSON-filen i Web Editor.

| JSON-alternativ | Beskrivning |
| --- | --- |
| Utdatasökväg | Den sökväg i din AEM-databas där JSON-utdata lagras. |
| Indexfil | Du kan ge indexfilen ett namn som du skapar för JSON-utdata. Som standard väljs filnamnet för DITA-kartan och ett suffix läggs till (till exempel `map_filename_index.json`).<br><br>Du kan också använda variabler när du ställer in indexfilen. Mer information om hur du använder variabler finns i [Använd variabler för att ange alternativen Målsökväg, Platsnamn eller Filnamn](generate-output-use-variables.md#id18BUG70K05Z). |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVAL-fil**: Välj DITAVAL-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVAL-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVAL-filen flyttas till en annan plats eller tas bort, tas den inte automatiskt bort från kartkontrollpanelen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att se sökvägen i AEM-databasen där filen lagras. Du kan bara välja DITAVAL-filer och ett fel visas om du har valt någon annan filtyp.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Mer information om villkorsförinställningar finns i [Använda villkorsförinställningar](generate-output-use-condition-presets.md#id1825FL004PN). |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Mer information finns i [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF). |
| Behåll tillfälliga filer | Välj det här alternativet om du vill behålla de temporära filer som genererats av DITA-OT. Om du får problem när du genererar utdata via DITA-OT väljer du det här alternativet om du vill behålla de tillfälliga filerna. Du kan sedan använda dessa filer för att felsöka fel vid generering av utdata.<br> <br> När du har skapat utdata väljer du ikonen **Hämta temporära filer** ![Hämta temporära filer](images/download-temp-files-icon.png) för att hämta ZIP-mappen som innehåller de temporära filerna. <br><br> **Obs!** Om filegenskaper läggs till under genereringen innehåller de tillfälliga utdatafilerna även en *metadata.xml*-fil som innehåller dessa egenskaper. |
| Egenskaper att sprida i utdata | Välj de egenskaper som du vill bearbeta som metadata. Dessa egenskaper ställs in från sidan Egenskaper i DITA-kartan eller bokmappningsfilen. Egenskaperna som du väljer i listrutan visas under fältet Egenskaper.<br><br>**Obs!**: Du kan också definiera anpassade egenskaper och skicka metadata till utdata med DITA-OT-publicering. Mer information finns i [Arbeta med metadata](metadata-dita.md#id21BJ00QD0XA). |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br><br>**Obs!**: Mer information om hur du skapar ett anpassat arbetsflöde för postutdatagenerering finns i _Anpassa arbetsflöde för efterutdatagenerering_ i guiden Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service. |

**Överordnat ämne:**[ Förstå förinställningarna för utdata](generate-output-understand-presets.md)
