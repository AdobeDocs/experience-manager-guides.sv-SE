---
title: Om den här guiden
description: Läs om den här guiden
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 2%

---

# Om den här guiden {#id175MC0P0S5Z}

Adobe Experience Manager Guides \(kallas senare *AEM Guides*\) är en kraftfull, molnbaserad innehållshanteringslösning för komponenter i enterpriseklass \(CCMS\). Det möjliggör inbyggt DITA-stöd i Adobe Experience Manager, vilket gör det möjligt för AEM att hantera DITA-baserad framtagning och leverans av innehåll. Man kan skapa material med den inbyggda webbredigeraren som enkelt kan publiceras i olika format.

Den här guiden innehåller anvisningar om hur du hämtar, installerar och konfigurerar AEM Guides. I den här guiden hittar du detaljerade anvisningar för hur du konfigurerar AEM Guides utifrån ditt företags skribent- och publiceringsbehov.

Den här guiden är avsedd för följande typer av målgrupper:

- Administratörer som installerar och hanterar AEM Guides.

- Utgivare, som kör publiceringsaktiviteten för att generera utdata i olika format.


## Innehållsstruktur

Informationen i den här handboken är ordnad enligt följande:

- [Om den här guiden](#id175MC0P0S5Z): Det här avsnittet innehåller en introduktion till den här guiden, den avsedda målgruppen och hur informationen är organiserad i den här handboken.

- [Hämta och installera](download-install.md#): I det här avsnittet beskrivs hur du hämtar, installerar eller uppgraderar AEM Guides.

- [Användaradministration och -säkerhet](user-admin-sec.md#): I det här avsnittet beskrivs grundkonceptet för användare och autentisering i AEM och standardanvändargrupper som skapats av AEM Guides.

- [Använd anpassad DITA-OT- och DITA-specialisering](dita-ot-specialization.md#): I det här avsnittet beskrivs hur du konfigurerar anpassade DITA-OT-plugin-program och använder DITA-specialisering.

- [Konfigurera dokumenttillstånd](customize-doc-state.md#): I det här avsnittet beskrivs hur du konfigurerar anpassade lägen för DITA-dokument.

- [Migrera befintligt innehåll](migrate-content.md#): I det här avsnittet beskrivs hur du infogar befintligt innehåll i AEM.

- [Konfigurera filnamn](conf-file-names.md#): I det här avsnittet beskrivs hur du konfigurerar inställningar för att automatiskt tilldela filnamn och definiera en regex för giltiga filnamnstecken.

- [Konfigurera ämne- och mappningsmallar](conf-template-tags.md#): I det här avsnittet beskrivs hur du konfigurerar ämne- och mappningsmallar så att de uppfyller dina redigeringsbehov. Lär dig mer om taggningssystem i AEM och hur du konfigurerar taggar så att de fungerar med AEM Guides.

- [Anpassa Web Editor](conf-web-editor.md#): I det här avsnittet förklaras de olika anpassningar du kan göra i Web Editor för att förbättra dess funktioner.

- [Inkludera @navtitle-attribut som standard](auto-add-navtitle.md#): I det här avsnittet förklaras hur du lägger till attributet `@navtitle` i en referensfil på en karta som standard.

- [Konfigurera globala profiler eller profiler på mappnivå](conf-folder-level.md#): I det här avsnittet beskrivs hur du skapar mappprofiler och ger behörigheter till specifika användare.

- [Versionshantering](version-management.md#): I det här avsnittet beskrivs hur du konfigurerar automatisk utcheckning av filer som öppnas för redigering i Web Editor.

- [Konfigurera inställningar för generering av utdata](conf-output-generation.md#): I det här avsnittet beskrivs de olika konfigurationer som du kan göra för att anpassa standardprocessen för generering av utdata.

- [Konfigurera och anpassa arbetsflöden](customize-workflows.md#): I det här avsnittet beskrivs olika konfigurationer för att anpassa de standardarbetsflöden som levereras i AEM Guides.

- [Översätt innehåll](translation.md#): I det här avsnittet finns länkar till relevanta hjälpartiklar i AEM för att du ska kunna förstå och konfigurera översättningsramverket. Lär dig även hur du aktiverar komponentbaserade arbetsflöden för översättning.

- [Konfigurera sökning efter AEM Assets-användargränssnitt](conf-dita-search.md#): I det här avsnittet beskrivs hur du konfigurerar DITA-innehållssökning i Assets-användargränssnittet och lägger till anpassade attribut i sökningen.


## Adobe Experience Manager \(AEM\) - översikt

[Adobe Experience Manager \(AEM\)](https://business.adobe.com/products/experience-manager/adobe-experience-manager.html) är en omfattande innehållshanteringslösning för att skapa webbplatser, mobilappar och formulär. AEM hjälper er att hantera ert marknadsföringsinnehåll och era marknadsföringsresurser. AEM finns as a Cloud Service. AEM as a Cloud Service hjälper er att ge era kunder personaliserade, innehållsledda upplevelser genom att kombinera kraften i AEM Content Management System med AEM Digital Asset Management. Några av de viktigaste resurserna som kan hjälpa er att komma igång och driftsätta i AEM as a Cloud Service är följande:

- [as a Cloud Service översikt för Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=sv-SE)
- [Komma igång med migreringsresan till AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=sv-SE)
- [Starta introduktionen till Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=sv-SEhttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
- [Implementera program för AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=sv-SE)
- [Distribuera till AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=sv-SE)
- [Assets as a Cloud Service Guide](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=sv-SE)

## Ytterligare resurser

Nedan följer en lista över andra användbara resurser i AEM Guides som finns på sidan [Lär dig mer och support](https://helpx.adobe.com/se/support/xml-documentation-for-experience-manager.html):

- Användarhandbok
- Referenshandbok för API
