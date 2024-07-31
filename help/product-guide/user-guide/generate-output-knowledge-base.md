---
title: Knowledge Base
description: Lär dig hur du skapar förinställningar för kunskapsbasen från webbredigeraren och kartpanelen. Konfigurera förinställningen för kunskapsbasutdata i AEM Guides.
feature: Publishing
role: User
exl-id: 31fdfd96-377c-406b-96ed-59a80bf6e03e
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 0%

---

# Knowledge Base {#knowledge-base}

Du kan skapa förinställningen **kunskapsbas** från webbredigeraren:

Öppna DITA-schemafilen i **Kartvyn** på panelen Databas, välj ikonen + på fliken **Utdata** för att skapa en förinställning och välj sedan **Knowledge Base** i listrutan **Typ** i dialogrutan **Ny förinställning** . Du kan namnge förinställningen och välja målet för att generera utdata med **Adobe Experience Manager**, **Salesforce** eller **ServiceNow**.




## Knowledge Base-konfiguration{#knowledge-base-configuration}


I webbredigeraren har följande konfigurationer ordnats under flikarna **Allmänt** och **Artiklar** . Du kan också konfigurera inställningarna för den specifika **kunskapsbas** som du har valt som mål, **Adobe Experience Manager**, **Salesforce** eller **ServiceNow**.


### Allmänt

| Alternativ för kunskapsbas | Beskrivning |
| --- | --- |
| Använd villkor med | Välj ett av följande alternativ:<br><br>* **Inget använt**: Välj det här alternativet om du inte vill använda något villkor på publicerade utdata.<br>* **DITAVAL-fil**: Välj DITAVAL-filer om du vill generera anpassat innehåll. Du kan markera flera DITAVAL-filer i dialogrutan Bläddra eller genom att skriva filsökvägen. Använd kryssikonen bredvid filnamnet för att ta bort den. DITAVAL-filer utvärderas i den ordning som anges, så de villkor som anges i den första filen har företräde framför de matchningsvillkor som anges i senare filer. Du kan behålla filordningen genom att lägga till eller ta bort filer. Om DITAVAL-filen flyttas till en annan plats eller tas bort tas den inte automatiskt bort från förinställningen. Du måste uppdatera platsen om filerna flyttas eller tas bort. Du kan hovra över filnamnet för att visa sökvägen i Adobe Experience Manager-databasen där filen lagras. Du kan bara välja DITAVAL-filer, och ett fel visas om du väljer någon annan filtyp.<br>* **Villkorsförinställning**: Välj en villkorsförinställning i listrutan om du vill använda ett villkor när du publicerar utdata. Alternativet är synligt om du har lagt till ett villkor på fliken Villkorsförinställningar i DITA-kartkonsolen. Visa [Använd villkorsförinställningar](generate-output-use-condition-presets.md#id1825FL004PN) om du vill veta mer om villkorsförinställningar. |
| Använd baslinje | Om du har skapat en baslinje för den valda DITA-kartan väljer du det här alternativet för att ange vilken version du vill publicera.<br><br>Visa [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) om du vill ha mer information. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i Adobe Experience Manager. Du måste välja ett arbetsflöde som du vill köra när utdatagenereringen är klar.<br><br>**Obs!**: Läs mer om hur du [anpassar arbetsflödet för efterhandsgenerering](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) i installations- och konfigureringshandboken för Cloud Service. |

### ServiceNow

| ServiceNow-alternativ | Beskrivning |
| --- | --- |
| Publish-profil | Använd listrutan för att välja bland de ServiceNow-anslutningsprofiler som administratören konfigurerar. Mer information om hur administratören kan skapa en publiceringsprofil finns i funktionsbeskrivningen för **redigeringsinställningar** i avsnittet [Vänster panel](./web-editor-features.md#id2051EA0M0HS). |
| Knowledge Base | Använd det här fältet för att välja önskad ServiceNow Knowledge Base. Du kan konfigurera kunskapsbaser på ServiceNow-webbplatsen för att lagra innehållet baserat på behörigheter. Artiklarna från denna DITA-karta kan publiceras på dessa kunskapsbanker. |
| Kategori och underkategori | Kategorierna är som hierarkiska träd som används för att hitta och klassificera artiklar i ServiceNow Knowledge Base. Lägg till en kategori och underkategori för att publicera ämnen och underämnen i innehållsförteckningen i den kategorin och underkategorin på ServiceNow-webbplatsen. |

### Salesforce

| Salesforce-alternativ | Beskrivning |
| --- | --- |
| Publish-profil | Använd listrutan för att välja bland de Salesforce-anslutningsprofiler som administratören konfigurerar. Mer information om hur administratören kan skapa en publiceringsprofil finns i funktionsbeskrivningen för **redigeringsinställningar** i avsnittet [Vänster panel](./web-editor-features.md#id2051EA0M0HS). |
| Posttyp | Använd listrutan för att välja bland de posttyper som har konfigurerats i Salesforce enligt synlighetsinställningarna som baseras på din användarprofil. Salesforce-posttyper är ett sätt att gruppera flera poster av en typ för det objektet. De definierar hur publikationen är organiserad. Du kan till exempel välja Posttyp för vanliga frågor och publicera enligt sidlayouten och fälten för vanliga frågor. |
| Artikelinnehållsfält | Du kan ha olika fält och en unik layout för varje posttypsmall. Använd dessa fält för att ange specifik information beroende på artikeltyp. Du kan till exempel visa en artikel med vanliga frågor och svar samt en ekvation. |
| Kategorier | Välj en kategori i listrutan för att publicera ämnen i innehållsförteckningen i den kategorin på Salesforce-webbplatsen. |

Du kan även visa följande alternativ i förinställningarna för Salesforce och ServiceNow:

| Alternativ | Beskrivning |
| --- | --- |
| Ta bort ämnesrubriken från artikeltexten. | Välj det här alternativet om du vill ta bort ämnesrubriken från artikeln i publicerade utdata. |
| Överför som utkast | Välj det här alternativet om du vill överföra ämnet för att dela det som ett utkast innan det görs tillgängligt för användarna. |
| Överför bilder | Välj det här alternativet om du vill att bilder i ämnen ska inkluderas i publicerade utdata. |
| Överför länkade dokument | Välj det här alternativet om du vill inkludera de dokument som är länkade i ämnen i publicerade utdata. |


### Adobe Experience Manager

>[!NOTE]
>
>Du kan använda förinställningen för Adobe Experience Manager Knowledge Base om administratören har konfigurerat den. Mer information finns i avsnittet [Artikelbaserad publicering i Web Editor](../install-guide/configure-article-based-publishing.md) i installations- och konfigurationshandboken.

| Adobe Experience Manager-alternativ | Beskrivning |
| --- | --- |
| Använd artikelsökväg | Välj det här alternativet om du vill visa **artikelsökvägen** för mappen som innehåller kunskapsbasmallarna. |
| Artikelsökväg | Det här fältet visas om du väljer alternativet **Använd artikelsökväg**. Bläddra och välj den kunskapsbaswebbplats i Adobe Experience Manager-databasen där utdata lagras. |
| Plats | Använd det här fältet för att välja den Adobe Experience Manager Knowledge Base som behövs. Du kan konfigurera kunskapsbaser på Adobe Experience Manager webbplats så att innehåll lagras baserat på behörigheter. Artiklarna från denna DITA-karta kan publiceras på dessa kunskapsbanker. |
| Kategori | Välj en kategori i listrutan om du vill publicera ämnen i innehållsförteckningen i den kategorin på webbplatsen Adobe Experience Manager. |
| Avsnittsmall och artikelmall | Detta är de strukturella komponenter som används för att ordna innehållet i dina utdata. Dessa är fördefinierade i Adobe Experience Manager Site-mallen. |
| Arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i Adobe Experience Manager. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts.<br>Läs mer om hur du [anpassar arbetsflödet för efterhandsgenerering](../install-guide/customize-workflows.md#id17A6GI004Y4) i installations- och konfigureringshandboken. |

>[!TIP]
> 
>Välj **Uppdatera** ![Uppdatera ikon](images/navtitle-refresh-icon.svg) för att fylla i respektive mallar i fälten enligt den kunskapsbasmall som du har valt.

### Artiklar

På den här fliken visas kartans träd eller hierarkiska vy. Välj de ämnen du vill publicera till en kunskapsbas. Expandera en innehållsförteckningsnod och välj de ämnen som du vill publicera.

**Överordnat ämne:** [Förstå förinställningarna för utdata](generate-output-understand-presets.md)
