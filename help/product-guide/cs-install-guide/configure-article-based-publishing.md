---
title: Installera paket för artikelbaserad publicering
description: Lär dig hur du installerar paket för artikelbaserad publicering
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Installera paket för artikelbaserad publicering {#id21BNL02052Z}

AEM Guides har en kraftfull artikelbaserad publiceringsfunktion som är integrerad med Web Editor. Med den här funktionen kan du publicera ett eller flera ämnen samtidigt. När du har öppnat en karta i kartredigeraren kan du navigera till fliken Utdata för att skapa en förinställning och sedan välja ett eller flera avsnitt för att generera utdata. Du kan använda den artikelbaserade publiceringsfunktionen för att stegvis generera utdata för ett eller flera ämnen eller publicera innehållet på en kunskapsbasplattform på ett artikel-för-artikel-sätt. Mer information finns i *Artikelbaserad publicering från Web Editor-avsnittet* i användarhandboken.

Så här skapar du en AEM webbplats för publicering av artikelbaserade utdata:

1. Hämta **XML Documentation Components Content Package för Cloud Service** från din [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Öppna AEM. Standardwebbadressen för åtkomst till pakethanteraren är: `https://<hostname>/crx/packmgr/index.jsp`
1. Ladda upp XML Documentation Components Content Package för Cloud Service och installera det sedan.
1. Hämta filen `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` från din [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Välj **Webbplatser** i Global Navigation.
1. Klicka på knappen **Skapa** i det övre högra hörnet i webbplatsens användargränssnitt.
1. Välj **Plats från mall** i listrutan **Skapa**.
1. Klicka på knappen **Importera** och välj sedan den `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` som du har hämtat till datorn. När platsmallen har importerats visas den längst ned.

   >[!NOTE]
   >
   > Du behöver bara importera ZIP-filen för första gången. När du har importerat webbplatsmallen är den tillgänglig i listan.

   Välj **Kunskapsbasmall för artikelbaserad publicering** om du vill skapa AEM webbplats och klicka på **Nästa** i det övre högra hörnet.

1. Ange **webbplatsrubriken** och **platsnamnet** och klicka på **Skapa** i det övre högra hörnet. En AEM skapas med hjälp av en Tragopan-webbplatsmall. \(Tragopan site är ett exempel på en kunskapsbas AEM webbplats med mallar för en kategori, avsnitt och artikelsidor.\)

   >[!NOTE]
   >
   > Du kan skapa flera AEM med samma mall.


Du kan använda den AEM webbplatsen för att publicera artikeln med hjälp av förinställningarna från Web Editor.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
