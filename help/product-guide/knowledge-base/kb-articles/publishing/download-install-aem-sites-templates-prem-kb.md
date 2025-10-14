---
title: Hämta och installera AEM Sites-mallar för On-Premise-tjänster
description: Lär dig hur du hämtar och installerar AEM Sites-mallar för på Prem Services
feature: Installation
role: Admin
level: Experienced
source-git-commit: 20ba7f4582f1d155e555c9ff3ac58e1e3c400765
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Hämta och installera AEM Sites-mallar (lokala tjänster)

Den här guiden innehåller stegvisa instruktioner för att ställa in och konfigurera den senaste AEM Guides-mallen för att generera AEM Sites. Följ de här stegen för att installera de paket som krävs, skapa och konfigurera förinställningar och generera AEM Sites.

## Förutsättningar

Innan du fortsätter med installationen bör du kontrollera att följande krav är uppfyllda:

- **Adobe Experience Manager (AEM):** En instans av **AEM 6.5** som körs med **Service Pack** 21, 20 och 19 samt **AEM Guides 4.6.0** eller senare versioner installerade.

- **Nödvändiga behörigheter**: Kontrollera att du har följande behörigheter:

   - Åtkomst till **portalen för programvarudistribution** för hämtning av nödvändiga paket
   - Åtkomst till **CRX Package Manager** för att installera paket i AEM.
   - Behörighet att skapa och ändra förinställningar i AEM Guides.

- **Hämta paket**: Hämta följande paket från **portalen för programdistribution**:

   - Komponentpaket: on-prem-guides-components.all-1.x.0.zip
   - Webbplatspaket: aemg-docs.all-1.x.0.zip

## Paketinstallation med CRX Package Manager

1. **Installera komponentpaketet:**
   1. Navigera till [**CRX Package Manager**](http://&lt;your-aem-instance>/crx/packmgr).
   2. Ladda upp och installera paketet on-prem-guides-components.all-1.x.0.zip.

2. **Installera platspaketet:** Överför och installera paketet aemg-docs.all-1.x.0.zip med CRX Package Manager.


## Skapa och konfigurera AEM Site Preset

1. **Skapa en ny förinställning:**
   1. Öppna en DITA-karta i AEM Guides och gå till panelen **Utdata**.
   2. Välj **Skapa förinställning**.
   3. Välj typen som **AEM Sites**.
   4. Ange ett namn för förinställningen.
   5. Avmarkera inställningen **Använd äldre komponentmappning**.
   6. Välj **Lägg till** om du vill skapa förinställningen.

      ![Dialogrutan Ny förinställning för utdata](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Konfigurera förinställning för AEM-webbplats:** Det finns två alternativ för att konfigurera OTB-webbplatsen:

   **Alternativ 1: Använd listrutan Plats**

   1. Välj **Plats** som **AEMG-dokument**.
   2. Kontrollera att **publiceringssökvägen** och **ämnessidmallen** automatiskt är inställda på:
      - Publiceringssökväg: aemg-docs/en/docs/product1
      - Ämnessidmall: Ämnessida.

      ![Använd listrutan Plats](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

   **Alternativ 2: Använd webbplatssökvägen**

   1. Ange **webbplatssökvägen** manuellt som /content/aemg-docs/en/docs/product1.
   2. Kontrollera att mallen **Ämnessida** automatiskt är inställd på Ämnessida.

      ![Använd webbplatssökväg](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Spara förinställningen:** Spara ändringarna i förinställningen.

## Generera AEM Sites

1. **Generera plats:**
   1. När förinställningen är konfigurerad kan du nu skapa AEM Site för motsvarande DITA-karta.
   2. Den genererade webbplatsen finns på sökvägen: /content/aemg-docs/en/docs/product1.
2. **Ändra standardsökväg för generering (valfritt):** Utför följande steg om du vill ändra standardsökvägen för webbplatsgenerering:

   1. Navigera till **AEM Sites**.
   2. Skapa en ny produktsida under OTB-webbplatsens struktur.
   3. Navigera till **AEMG-dokument** > **Engelska** > **Dokument**.

      ![Skapa sida i AEM platsstruktur &#x200B;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

   4. Markera rutan **Hemsida** och välj sedan **Nästa**.

      ![Välj startsidesruta](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

   5. Ange sidans **titel** och **namn**.
   6. Välj **Skapa**.

