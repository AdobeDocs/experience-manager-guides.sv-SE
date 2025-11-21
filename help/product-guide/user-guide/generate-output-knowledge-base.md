---
title: Knowledge Base
description: Lär dig hur du skapar förinställningar för kunskapsbasen från kartkonsolen. Konfigurera förinställningen för kunskapsbasutdata i AEM Guides.
feature: Publishing
role: User
exl-id: 31fdfd96-377c-406b-96ed-59a80bf6e03e
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 0%

---

# Knowledge Base {#knowledge-base}

Utför följande steg för att skapa förinställningen **Knowledge Base** från kartkonsolen:

1. [Öppna en DITA-kartfil i kartkonsolen](./open-files-map-console.md).

   Du kan även komma åt kartfilen från widgeten **Senaste filer** i avsnittet [Översikt](./intro-home-page.md#overview). Den markerade kartfilen öppnas i kartkonsolen.
1. Välj ikonen + på fliken **Utdataförinställningar** för att skapa en förinställning.
1. Välj **kunskapsbas** i listrutan Typ i dialogrutan **Ny förinställning** .
1. Välj ett mål för genererade utdata i fältet **Mål**. De tillgängliga alternativen är: **Adobe Experience Manager**, **Salesforce** och **ServiceNow**.

   ![](./images/knowledge-base-preset-dialog-box.png){width="350" align="left"}

1. Välj alternativet **Lägg till i den aktuella mappprofilen** om du vill skapa en förinställning i den aktuella mappprofilen. Mappprofilsikonen ![](images/global-preset-icon.svg) indikerar en förinställning på mappprofilnivå.

   Läs mer om [Hantera förinställningar för globala utdata och mappprofiler](./web-editor-manage-output-presets.md).

1. Välj **Lägg till**.

   Förinställningen för kunskapsbasen skapas.

## Knowledge Base-konfiguration{#knowledge-base-configuration}


Konfigurationsalternativen för kunskapsbasens förinställningar är ordnade på flikarna **Allmänt**, **Artiklar** och valt mål (**AEM**/ **ServiceNow**/ **Salesforce**).

![](./images/kb-aem-preset.png){width="550" align="left"}

### Allmänt

Följande konfigurationsalternativ är tillgängliga på fliken **Allmänt**:

| Alternativ för kunskapsbas | Beskrivning |
| --- | --- |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVAL-fil**: Välj DITAVAL-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVAL-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVAL-filen flyttas till en annan plats eller tas bort tas den inte automatiskt bort från förinställningen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i Adobe Experience Manager-databasen där filen lagras. Du kan bara välja DITAVAL-filer, och ett fel visas om du väljer någon annan filtyp.<br><br> **Obs!** Tänk på följande när du använder DITAVAL-filtrering för **Salesforce-publicering**: <br> - Endast `Include`- och `Exclude`-åtgärder stöds för varje DITAVAL-egenskap.<br> - Flaggning för att markera eller markera villkorligt innehåll visuellt i utdata stöds inte.<br> - I utdataförinställningarna kan bara en DITAVAL-fil väljas för publicering. Flera DITAVAL-filval stöds inte för Salesforce-publicering. <br>- `ditavalref` referenser i innehållet stöds inte. <br><br> **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd villkorsförinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i Adobe Experience Manager. Du måste välja ett arbetsflöde som du vill köra när utdatagenereringen är klar.<br><br>**Obs!**: Läs mer om hur du [anpassar arbetsflödet för efterhandsgenerering](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) i installations- och konfigureringshandboken för molntjänster. |

### Artiklar

På den här fliken visas kartans träd eller hierarkiska vy. Välj de ämnen du vill publicera till en kunskapsbas. Expandera en innehållsförteckningsnod och välj de ämnen som du vill publicera.

### Mål - Adobe Experience Manager/ServiceNow/Salesforce

Konfigurationsalternativen ändras beroende på vilket mål du väljer.


**Adobe Experience Manager**

Följande konfigurationsalternativ visas som mål för **Adobe Experience Manager**:


>[!NOTE]
>
>Du kan bara använda förinställningen för Adobe Experience Manager Knowledge Base om administratören har konfigurerat den.

| Adobe Experience Manager-alternativ | Beskrivning |
| --- | --- |
| Använd artikelsökväg | Välj det här alternativet om du vill visa **artikelsökvägen** för mappen som innehåller kunskapsbasmallarna. |
| Artikelsökväg | Det här fältet visas om du väljer alternativet **Använd artikelsökväg**. Bläddra och välj den kunskapsbaswebbplats i Adobe Experience Manager-databasen där utdata lagras. |
| Plats | Använd det här fältet för att välja den Adobe Experience Manager Knowledge Base som behövs. Du kan konfigurera kunskapsbaser på Adobe Experience Manager webbplats så att innehåll lagras baserat på behörigheter. Artiklarna från denna DITA-karta kan publiceras på dessa kunskapsbanker. |
| Kategori | Välj en kategori i listrutan om du vill publicera ämnen i innehållsförteckningen i den kategorin på Adobe Experience Manager webbplats. |
| Avsnittsmall och artikelmall | Detta är de strukturella komponenter som används för att ordna innehållet i dina utdata. Dessa är fördefinierade i Adobe Experience Manager Site-mallen. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i Adobe Experience Manager. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br>Läs mer om hur du [anpassar arbetsflödet för efterhandsgenerering](../install-guide/customize-workflows.md#id17A6GI004Y4) i installations- och konfigureringshandboken. |

>[!TIP]
> 
>Välj ikonen **Uppdatera** för att fylla i respektive mallar i fälten enligt den kunskapsbasmall som du har valt.

**ServiceNow**

Följande konfigurationsalternativ visas för **ServiceNow** som mål:

| ServiceNow-alternativ | Beskrivning |
| --- | --- |
| Publicera profil | Använd listrutan för att välja bland de ServiceNow-anslutningsprofiler som administratören konfigurerar. Om du vill veta mer om hur administratören kan skapa en publiceringsprofil kan du visa funktionsbeskrivningen för **Workspace-inställningarna** (visas som **Inställningar** för **On-Prem**) i avsnittet [Vänster panel](./web-editor-features.md#id2051EA0M0HS). |
| Knowledge Base | Använd det här fältet för att välja önskad ServiceNow Knowledge Base. Du kan konfigurera kunskapsbaser på ServiceNow-webbplatsen för att lagra innehållet baserat på behörigheter. Artiklarna från denna DITA-karta kan publiceras på dessa kunskapsbanker. |
| Kategori och underkategori | Kategorierna är som hierarkiska träd som används för att hitta och klassificera artiklar i ServiceNow Knowledge Base. Lägg till en kategori och underkategori för att publicera ämnen och underämnen i innehållsförteckningen i den kategorin och underkategorin på ServiceNow-webbplatsen. |

**Salesforce**

Följande konfigurationsalternativ visas som mål för **Salesforce**:

| Salesforce-alternativ | Beskrivning |
| --- | --- |
| Publicera profil | Använd listrutan för att välja bland de anslutningsprofiler för Salesforce som administratören konfigurerar. Om du vill veta mer om hur administratören kan skapa en publiceringsprofil kan du visa funktionsbeskrivningen för **Workspace-inställningarna** (visas som **Inställningar** för **On-Prem**) i [flikfältet](./web-editor-tab-bar.md). |
| Posttyp | Använd listrutan för att välja bland de posttyper som har konfigurerats i Salesforce enligt synlighetsinställningarna som baseras på din användarprofil. Med posttyper i Salesforce kan du gruppera flera poster av samma typ för det objektet. De definierar hur publikationen är organiserad. Du kan till exempel välja Posttyp för vanliga frågor och publicera enligt sidlayouten och fälten för vanliga frågor. |
| Artikelinnehållsfält | Du kan ha olika fält och en unik layout för varje posttypsmall. Använd dessa fält för att ange specifik information beroende på artikeltyp. Du kan till exempel visa en artikel med vanliga frågor och svar samt en ekvation. |
| Kategorier | Välj en kategori i listrutan om du vill publicera ämnen i innehållsförteckningen i den kategorin på Salesforce webbplats. |

**Fler alternativ**

Du kan även visa följande alternativ i förinställningarna för Salesforce och ServiceNow:

| Alternativ | Beskrivning |
| --- | --- |
| Ta bort ämnesrubriken från artikeltexten. | Välj det här alternativet om du vill ta bort ämnesrubriken från artikeln i publicerade utdata. |
| Överför som utkast | Välj det här alternativet om du vill överföra ämnet för att dela det som ett utkast innan det görs tillgängligt för användarna. |
| Överför bilder | Välj det här alternativet om du vill att bilder i ämnen ska inkluderas i publicerade utdata. |
| Överför länkade dokument | Välj det här alternativet om du vill inkludera de dokument som är länkade i ämnen i publicerade utdata. |





**Överordnat ämne:** [Förstå förinställningarna för utdata](generate-output-understand-presets.md)
