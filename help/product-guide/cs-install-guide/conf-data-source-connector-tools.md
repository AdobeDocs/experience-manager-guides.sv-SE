---
title: Konfigurera en datakällanslutning med verktyg
description: Lär dig hur du konfigurerar en datakällanslutning med verktygen.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 873542cb2e8e1b7e80e0ecc113cae4f603b18592
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 0%

---

# Konfigurera en datakällanslutning från användargränssnittet

Experience Manager Guides har **Datakällor** som hjälper dig att konfigurera färdiga anslutningar för datakällor. Du kan konfigurera JIRA-, SQL- (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch och allmänna REST-klientanslutningar.


Förutom dessa färdiga anslutningar kan du använda Experience Manager Guides för att skapa kopplingar för datakällorna Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO). Du kan hämta och installera dessa öppen källkod-anslutningar från [Maven Central-arkivet](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Användarna kan sedan konfigurera dessa anslutningar.
Lär dig hur [installera en anslutning med öppen källkod](#install-open-source-connector).



Du kan också ansluta till JSON-datafiler med hjälp av en filkoppling. Ladda upp JSON-filen från datorn eller bläddra i den från Adobe Experience Manager resurser. Skapa sedan innehållsutdrag eller ämnen med generatorerna.

Så här konfigurerar du en koppling:

1. Välj **Adobe Experience Manager** överst och välj Verktyg.
1. Välj **Stödlinjer** i listan över verktyg.
1. Välj **Datakällor** platta. The **Datakällor** visas. Du kan visa de anslutna datakällorna.

   Du kan växla mellan **Listvy** eller **Panelvy** för att visa de olika anslutna datakällorna som en lista eller som rutor.

   <img src="./assets/data-sources-create-window.png" alt= "datakällor som listas på sidan med datakällor" width="800">

   *Visa eller skapa en datakällkoppling.*
1. Klicka **Skapa**.
1. Välj den databas som du vill skapa kopplingen för. Exempel: Elasticsearch-kopplingen.
   >[!NOTE]
   >
   >Alla tillgängliga färdiga databaser visas.

1. Klicka på **Nästa**.
1. Ange konfigurations- och anslutningsinformation enligt databasen.

   >[!TIP]
   >
   >* Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> i närheten av fältet för att visa mer information om det.
   > * Fält med * är obligatoriska. Du kan till exempel ange följande information för Elasticsearch-kopplingen.

   * **Namn**: Ange namnet på datakällan.
   * **Autentiseringstyp**: Välj typ av autentisering i listrutan. Grundläggande autentisering av användarnamn och lösenord
   * **Användarnamn**: Ange ditt användarnamn.
   * **Lösenord**: Ange ditt användarnamn och lösenord.
   * **URL**: Lägg till API-URL:en.


1. Välj **Exkludera fabriksmallar** om du inte vill att fabriksmallarna ska kunna användas för att generera avsnitt och fragment. De visas inte under **Datamappningsmall** listrutan i  **Lägg till generator för innehållsfragment** eller **Lägg till ämnesgenerator** -dialogrutan.


1. Välj **Testanslutning**. Du kan visa **Testanslutning** bara aktiverad när du har lagt till den obligatoriska informationen. Visa ett meddelande om att anslutningen är korrekt. Annars kan du visa ett felmeddelande.



1. Välj **Spara** längst upp för att spara kopplingen.     Visa **Spara** när du fyllt i alla detaljer och anslutningen lyckades.


   Om anslutningen har sparats kan du visa den anslutna datakällan på sidan.

**Anslut till flera resurser**

Du kan lägga till eller använda flera resurser baserat på olika URL:er för vissa anslutningar, som Generic REST Client, Salsify, Akeneo och Microsoft Azure DevOps Boards (ADO). Koppla sedan samman med dem för att skapa innehållsfragment eller ämnen med hjälp av generatorerna för dem.

Så här skapar du en resurs:

1. Välj ![lägg till ikon](assets/Add_icon.svg) i **URL-resursavsnitt** om du vill lägga till en resurs för varje URL.
1. Konfigurera all information i **Lägg till resurs** -dialogrutan.
1. Klicka **Lägg till**.
1. Du kan redigera ![redigeringsikon](assets/edit_pencil_icon.svg) eller ta bort ![delete](assets/Delete_icon.svg) resursen från URL-resurslistan.

1. Du kan också använda standardresurserna som är tillgängliga för datakällor som Salsify, Akeneo och Microsoft ADO. Växla alternativen AV för den resurs som du inte vill konfigurera för en datakälla.

Detta hjälper dig att snabbt hämta data från någon av resurserna för en viss datakälla i ett enda innehållskuvert eller ämne.



## Installera en anslutning med öppen källkod{#install-open-source-connector}

Publicera ett beroende som finns på [Maven Central-arkivet](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) till Cloud Servicen måste du inkludera och bädda in beroendet för en öppen källkodsanslutning.

1. Lägg till beroendet i `all/pom.xml`  i din molnhanterares Git-projektkod. Du kan till exempel lägga till följande beroende för datakällkopplingen för Microsoft Azure DevOps-kort.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Bädda in det tillagda beroendet.

       &quot;
       &lt;embedded>
       &lt;groupid>com.adobe.aem.addon.guides&lt;/groupid>
       &lt;artifactid>konnect-azure-devops&lt;/artifactid>
       &lt;type>jar&lt;/type>
       &lt;target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install&lt;/target>
       &lt;/embedded>
       &quot;
   
1. Kör pipeline för att tillämpa ändringarna i Cloud Servicen.
Kopplingen är installerad i din miljö.


## Tillgängliga funktioner för en koppling

* Växla mellan **Listvy** eller **Panelvy**  för att visa de olika anslutna datakällorna som en lista eller som rutor.
* Markera kryssrutan för en enskild koppling. Klicka **Markera alla** för att välja alla anslutningar. Klicka **Avmarkera allt** när alla kopplingar är markerade.

<img src="./assets/data-sources-features.png" alt= "funktioner för datakällorna på sidan med datakällor" width="800">

*Redigera, återansluta, duplicera eller ta bort en datakällkoppling.*

Du kan använda följande funktioner för kontakten på **Datakällor** sida:

* **Redigera**: Redigera konfigurationsinformationen för den valda kopplingen.

* **Återanslut**: Återanslut till en frånkopplad koppling.

* **Duplicera**: Skapa en ny dubblettkoppling med den aktuella kopplingen som bas. Den duplicerade kopplingen skapas som standard med ett suffix (som connectorname_1). Exempel: elastic-search_1.
Du kan visa ett fel om det finns en koppling med samma namn.

* **Ta bort**: Ta bort den markerade kopplingen.


När du har konfigurerat datakällan visas anslutningen under **Panelen Datakällor** i webbredigeraren. Sedan kan du ansluta till datakällan och infoga ett innehållskuvert i dina ämnen. Mer information finns i [Infoga ett innehållssfragment från datakällan](../user-guide/web-editor-content-snippet.md).
