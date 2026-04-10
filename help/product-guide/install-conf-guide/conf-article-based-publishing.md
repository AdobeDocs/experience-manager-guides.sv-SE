---
title: Installera paket för artikelbaserad publicering
description: Lär dig hur du installerar paket för artikelbaserad publicering
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Installera paket för artikelbaserad publicering {#id21BNL02052Z}

AEM Guides har en kraftfull artikelbaserad publiceringsfunktion som är integrerad med Web Editor. Med den här funktionen kan du publicera ett eller flera ämnen samtidigt. När du har öppnat en karta i kartredigeraren kan du navigera till fliken Utdata för att skapa en förinställning och sedan välja ett eller flera avsnitt för att generera utdata. Du kan använda den artikelbaserade publiceringsfunktionen för att stegvis generera utdata för ett eller flera ämnen eller publicera innehållet på en kunskapsbasplattform på ett artikel-för-artikel-sätt. Mer information finns i *Artikelbaserad publicering från Web Editor-avsnittet* i användarhandboken.

Följande flikar innehåller anvisningar om hur du skapar en AEM-webbplats för publicering av artikelbaserade utdata baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Hämta **XML Documentation Components Content Package för Cloud Service** från din [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Öppna AEM Package Manager. Standardwebbadressen för åtkomst till pakethanteraren är: `https://<hostname>/crx/packmgr/index.jsp`
1. Ladda upp XML Documentation Components Content Package för Cloud Service och installera det sedan.
1. Hämta filen `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` från din [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Välj **Webbplatser** i Global Navigation.
1. Klicka på knappen **Skapa** i det övre högra hörnet i webbplatsens användargränssnitt.
1. Välj **Plats från mall** i listrutan **Skapa**.
1. Klicka på knappen **Importera** och välj sedan den `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` som du har hämtat till datorn. När platsmallen har importerats visas den längst ned.

   >[!NOTE]
   >
   > Du behöver bara importera ZIP-filen för första gången. När du har importerat webbplatsmallen är den tillgänglig i listan.

   Välj **Kunskapsbasmall för artikelbaserad publicering** för att skapa AEM-webbplatsen och klicka på **Nästa** i det övre högra hörnet.

1. Ange **webbplatsrubriken** och **platsnamnet** och klicka på **Skapa** i det övre högra hörnet. En AEM-webbplats skapas med Tragopan-webbplatsmallen. \(Tragopan site är ett exempel på en kunskapsbas-AEM-webbplats med mallar för en kategori, avsnitt och artikelsidor.\)

   >[!NOTE]
   >
   > Du kan skapa flera AEM-webbplatser med samma mall.


Du kan använda AEM webbplats för att publicera artikeln med hjälp av förinställningarna från Web Editor.

>[!TAB Lokal]

Om du vill aktivera artikelbaserad publicering hämtar och installerar du följande paket från Adobe Software Distribution Portal. Installera dem för att skapa en Tragopan-plats. \(Tragopan site är ett exempel på en kunskapsbas-AEM-webbplats med mallar för en kategori, avsnitt och artikelsidor.\) Uppdatera Tragopan-webbplatsen för att generera utdata från AEM-webbplatsen med hjälp av förinställningarna från Web Editor.

- Kunskapsbasmall för artikelbaserad publicering
- Komponentpaket för artikelbaserad publicering

>[!ENDTABS]


**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
