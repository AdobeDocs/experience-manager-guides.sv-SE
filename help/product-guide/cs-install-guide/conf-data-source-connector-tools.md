---
title: Konfigurera en datakällanslutning med verktyg
description: Lär dig hur du konfigurerar en datakällanslutning med verktygen.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Konfigurera en datakällanslutning från användargränssnittet

Experience Manager Guides har verktyget **Datakällor** som hjälper dig att konfigurera färdiga anslutningar för datakällor. Du kan konfigurera JIRA-, SQL- (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch och allmänna REST-klientanslutningar.


Förutom dessa färdiga anslutningar tillhandahåller Experience Manager Guides anslutningarna för datakällorna Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO). Du kan hämta och installera dessa öppen källkod-anslutningar från [Maven Central-databasen](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Användarna kan sedan konfigurera dessa anslutningar.
Lär dig hur du [installerar en öppen källkodsanslutning](#install-open-source-connector).



Du kan också ansluta till JSON-datafiler med hjälp av en filkoppling. Ladda upp JSON-filen från datorn eller bläddra i den från Adobe Experience Manager resurser. Skapa sedan innehållsutdrag eller ämnen med generatorerna.

Så här konfigurerar du en koppling:

1. Klicka på länken **Adobe Experience Manager** överst och välj Verktyg.
1. Välj **Stödlinjer** i listan över verktyg.
1. Markera rutan **Datakällor**. Sidan **Datakällor** visas. Du kan visa de anslutna datakällorna.

   Du kan växla mellan **listvyn** och **vyn sida vid sida** om du vill visa de olika anslutna datakällorna som en lista eller som rutor.

   <img src="./assets/data-sources-create-window.png" alt= "datakällor som listas på sidan med datakällor" width="800">

   *Visa eller skapa en datakällkoppling.*

1. Klicka på **Skapa**.
1. Välj den databas som du vill skapa kopplingen för. Exempel: Elasticsearch Connector.

   >[!NOTE]
   >
   >Alla tillgängliga färdiga databaser visas.

1. Klicka på **Nästa**.
1. Ange konfigurations- och anslutningsinformation enligt databasen.

   >[!TIP]
   >
   >* Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära fältet om du vill visa mer information om det.
   >* Fält med * är obligatoriska. Du kan till exempel ange följande information för Elasticsearch-anslutningen.

   * **Namn**: Ange namnet på datakällan.
   * **Autentiseringstyp**: Välj autentiseringstyp i listrutan. Grundläggande autentisering av användarnamn och lösenord
   * **Användarnamn**: Ange ditt användarnamn.
   * **Lösenord**: Ange ditt användarnamn och lösenord.
   * **URL**: Lägg till API-URL:en.


1. Välj alternativet **Uteslut fabriksmallar** om du vill exkludera fabriksmallarna från att användas för ämnesgenerering och fragmentgenerering. De visas inte i listrutan **Datamappningsmall** i **Skapa innehållsfragment** eller i dialogrutan **Lägg till ämnesgenerator**.
1. Välj **Testa anslutningen**. Du kan bara visa knappen **Testa anslutning** när du har lagt till den information som krävs. Visa ett meddelande om att anslutningen är korrekt. Annars kan du visa ett felmeddelande.
1. Välj **Spara** längst upp för att spara kopplingen.     Visa knappen **Spara** aktiverad när du har fyllt i all information och anslutningen har upprättats.


   Om anslutningen har sparats kan du visa den anslutna datakällan på sidan.

**Anslut till flera resurser**

Du kan lägga till eller använda flera resurser baserat på olika URL:er för vissa anslutningar, som Generic REST Client, Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO). Koppla sedan samman med dem för att skapa innehållsfragment eller ämnen med hjälp av generatorerna för dem.

Så här skapar du en resurs:

1. Välj ![Lägg till ikon](assets/Add_icon.svg) i **URL-resursavsnittet** om du vill lägga till en resurs för varje URL.
1. Konfigurera all information i dialogrutan **Lägg till resurs**.
1. Klicka på **Lägg till**.
1. Du kan redigera ![redigeringsikonen](assets/edit_pencil_icon.svg) eller ta bort ![ta bort](assets/Delete_icon.svg) resursen från URL-resurslistan.
1. Du kan också använda standardresurserna som är tillgängliga för datakällor som Salsify, Akeneo och Microsoft ADO. Växla alternativen AV för den resurs som du inte vill konfigurera för en datakälla.

Detta hjälper dig att snabbt hämta data från någon av resurserna för en viss datakälla i ett enda innehållskuvert eller ämne.



## Installera en anslutning med öppen källkod{#install-open-source-connector}

Om du vill publicera ett beroende på [Maven Central-databasen](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) till molntjänsterna måste du inkludera och bädda in beroendet för en öppen källkodsanslutning.

1. Lägg till beroendet i `all/pom.xml` i Git-projektkoden för din molnhanterare. Du kan till exempel lägga till följande beroende för datakällkopplingen för Microsoft Azure DevOps-kort.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Bädda in det tillagda beroendet.

   ```
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <type>jar</type>
       <target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install</target>
   </embedded> 
   ```

1. Kör pipelinen för att tillämpa ändringarna i molntjänsterna.
Kopplingen är installerad i din miljö.


## Tillgängliga funktioner för en koppling

* Växla mellan **listvyn** eller **vyn sida vid sida** om du vill visa de olika anslutna datakällorna som en lista eller som rutor.
* Markera kryssrutan för en enskild koppling. Klicka på **Markera alla** för att markera alla anslutningar. Du kan klicka på **Avmarkera alla** när alla kopplingar är markerade.

<img src="./assets/data-sources-features.png" alt= "funktioner för datakällorna på sidan med datakällor" width="800">

*Redigera, återansluta, duplicera eller ta bort en datakällkoppling.*

Du kan använda följande funktioner för kopplingen på sidan **Datakällor**:

* **Redigera**: Redigera konfigurationsinformationen för den valda kopplingen.

* **Återanslut**: Återanslut till en frånkopplad koppling.

* **Duplicera**: Skapa en ny dubblettkoppling med den aktuella kopplingen som bas. Den duplicerade kopplingen skapas som standard med ett suffix (som connectorname_1). Exempel: elastic-search_1.
Du kan visa ett fel om det finns en koppling med samma namn.

* **Ta bort**: Ta bort den markerade kopplingen.


När du har konfigurerat datakällan visas kopplingen under panelen **Datakällor** i webbredigeraren. Sedan kan du ansluta till datakällan och infoga ett innehållskuvert i dina ämnen. Mer information finns i [Infoga ett innehållsfragment från datakällan](../user-guide/web-editor-content-snippet.md).
