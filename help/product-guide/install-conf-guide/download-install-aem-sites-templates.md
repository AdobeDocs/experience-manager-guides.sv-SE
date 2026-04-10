---
title: Hämta och installera AEM Sites-mallar för molntjänster
description: Lär dig hur du hämtar och installerar AEM Sites-mallar för molntjänster
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---

# Hämta och installera AEM Sites-mallar

Den här guiden innehåller stegvisa instruktioner för att konfigurera och konfigurera den senaste AEM Guides-mallen för att generera AEM Sites-sidor i en molnmiljö. Följ de här stegen för att installera de paket som krävs, skapa och konfigurera förinställningar och generera AEM Sites.

## Förutsättningar

På följande flikar finns nödvändiga förutsättningar som baseras på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

- **Adobe Experience Manager (AEM) Cloud**: En instans av **AEM as a Cloud Service** som körs med **AEM Guides 2502 eller senare versioner**.

- **Nödvändiga behörigheter**: Du måste ha följande behörigheter:

   - Åtkomst till **Cloud Manager** för att distribuera paket.
   - Åtkomst till **Git-databasen** som är kopplad till din miljö.
   - Behörighet att skapa och ändra förinställningar i AEM Guides.

- **Hämta paket**: Hämta följande paket från portalen för distribution av programvara:

   - Komponentpaket: guides-components.all-1.x.0.zip
   - Platsmall: aemg-docs-1.x.0.zip

>[!TAB Lokal]

- **Adobe Experience Manager (AEM):** En instans av **AEM 6.5** som körs med **Service Pack** 21, 20 och 19 samt **AEM Guides 4.6.0** eller senare versioner installerade.

- **Nödvändiga behörigheter**: Kontrollera att du har följande behörigheter:

   - Åtkomst till **portalen för programvarudistribution** för hämtning av nödvändiga paket
   - Åtkomst till **CRX Package Manager** för att installera paket i AEM.
   - Behörighet att skapa och ändra förinställningar i AEM Guides.

- **Hämta paket**: Hämta följande paket från **portalen för programdistribution**:

   - Komponentpaket: on-prem-guides-components.all-1.x.0.zip
   - Webbplatspaket: aemg-docs.all-1.x.0.zip

>[!ENDTABS]


## Paketinstallation

Följande flikar innehåller anvisningar för paketinstallation baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Installera **komponentpaketet (guides-components.all-1.x.zip)** och utför följande steg:

1. **Klona Git-databas:**
   1. Navigera till **Databaser** i den vänstra panelen i Cloud Manager.
   2. Välj **Åtkomst till repo-information** och kopiera Git-klonkommandot.

      ![Välj Åtkomst till repo-information](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350" align="left"}

   3. Klona databasen till ditt lokala system med det angivna användarnamnet och lösenordet (generera lösenord om det behövs).
2. **Lägg till paket i Maven Bundle:**
   1. Skapa ett nytt Maven-paket eller lägg till ett befintligt i din lokalt klonade databas.
   2. Kontrollera att installationen av strukturen `/jcr_root/apps/fmdita/` finns i Maven-projektet.

      ![Struktur i Maven-projekt](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650" align="left"}


   3. Placera filen guides-components.all-1.x.x.zip i installationsmappen.

3. **Uppdatera filters.xml:**

   1. Öppna filen filters.xml som finns i META-INF-mappen i den överordnade innehållskatalogen.
   2. Lägg till följande filter: filterrot=`/apps/fmdita` läge=`merge`/


      ![Lägg till filter](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650" align="left"}


4. **Konfigurera pom.xml:** Uppdatera filen pom.xml enligt dina miljökrav.
5. **Skjut in ändringar och kör pipeline:**
   1. Överför ändringarna till Git-huvuddatabasen.
   2. Navigera till **Pipelines** i Cloud Manager och kör pipelinen för den önskade miljön.
6. **Verifiera installationen:** När distributionen är klar installeras komponentpaketet i AEM Cloud-miljön.

>[!TAB Lokal]

1. **Installera komponentpaketet:**
   1. Navigera till [**CRX Package Manager**](http://<your-aem-instance>/crx/packmgr).
   2. Ladda upp och installera paketet on-prem-guides-components.all-1.x.0.zip.

2. **Installera platspaketet:** Överför och installera paketet aemg-docs.all-1.x.0.zip med CRX Package Manager.

>[!ENDTABS]

## Skapa webbplats med installerade mallar (för Cloud Service)

1. **Importera platsmall:**
   1. Gå till AEM Sites (servername/sites.html/content).
   2. Välj **Skapa** > **Plats** från mall.
   3. Importera webbplatsmallen aemg-docs-1.x.x.zip med alternativet **Importera**.
2. **Välj mall:** Välj **AEMG Docs 1.x.x** och välj sedan **Next**.
3. **Ange webbplatsinformation:** Ange **webbplatstiteln** och **platsnamnet**.

   ![Skapa plats](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350" align="left"}

4. Välj **Skapa**.

## Skapa förinställning för AEM-webbplats

1. **Skapa en ny förinställning:**
   1. Öppna en DITA-karta i AEM Guides och gå till panelen **Utdata**.
   2. Välj **Skapa förinställning**.
   3. Välj typen som **AEM Sites**.
   4. Ange ett namn för förinställningen.
   5. Avmarkera inställningen **Använd äldre komponentmappning**.
   6. Välj **Lägg till** om du vill skapa förinställningen.

      ![Skapa ny förinställning för AEM Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Konfigurera förinställning för AEM-webbplats:** Det finns två alternativ för att konfigurera OTB-webbplatsen:

   **Alternativ 1: Använd listrutan Plats**

   1. Välj **Plats** som den som skapades ovan (t.ex. AEMG Docs Site).
   2. Kontrollera att mallen **Publiceringssökväg** och **Ämnessida** automatiskt är inställda på:
      - Publiceringssökväg: Cloud Service: `/content/AEMG-Docs-Site/en/docs/product` och lokal: `aemg-docs/en/docs/product1`
      - Ämnessidmall: Ämnessida

      ![Använd listrutan Plats för att konfigurera AEM Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

   **Alternativ 2: Använd webbplatssökvägen**

   1. Ange **webbplatssökvägen** manuellt som `/content/AEMG-Docs-Site/en/docs/product` för Cloud Service och `/content/aemg-docs/en/docs/product1` för lokal.
   2. Kontrollera att mallen **Ämnessida** automatiskt är inställd på Ämnessida.

      För Cloud Service:

      ![Använd webbplatssökvägen för att konfigurera AEM-webbplatsen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

      För lokal användning:

      ![Använd webbplatssökväg](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Spara förinställningen:** Spara ändringarna i förinställningen.

## Generera AEM Sites

1. **Generera plats:**
   1. När förinställningen är konfigurerad genererar du AEM Site för motsvarande DITA-karta.
   2. Den genererade webbplatsen kommer att vara tillgänglig på sökvägen `/content/AEMG-Docs-Site/en/docs/product` för Cloud Service och `/content/aemg-docs/en/docs/product1` för On-Premise.
2. **Ändra standardsökväg för generering (valfritt):** Utför följande steg om du vill ändra standardsökvägen för webbplatsgenerering:
   1. Navigera till **AEM Sites**.
   2. Skapa en ny produktsida under OTB-webbplatsens struktur.
   3. Navigera till **AEMG-dokument** > **Engelska** > **Dokument**.

      ![Skapa sida](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650" align="left"}

   4. Markera rutan **Hemsida** och välj sedan **Nästa**.

      ![Välj hempanel](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650" align="left"}

   5. Ange sidans **titel** och **namn**.
   6. Välj **Skapa**.

>[!NOTE]
>
> Vid installation av Cloud Service ska du se till att alla konfigurationer testas i en icke-produktionsmiljö innan de distribueras till produktionen. <br><br> Mer information finns i den officiella [Distribuera till AEM as a Cloud Service-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview).
