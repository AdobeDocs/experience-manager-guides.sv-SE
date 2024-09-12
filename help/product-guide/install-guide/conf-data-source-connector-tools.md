---
title: Konfigurera en datakällanslutning med verktyg
description: Lär dig hur du konfigurerar en datakällanslutning med verktygen.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 1eb4fcb33d6f905df3f543232e7040d1da42560b
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Konfigurera en datakällanslutning från användargränssnittet

Experience Manager Guides har verktyget **Datakällor** som hjälper dig att konfigurera färdiga anslutningar för datakällor. Du kan konfigurera anslutningar för databaserna JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce och Elasticsearch.

Så här konfigurerar du en koppling:

1. Klicka på länken **Adobe Experience Manager** överst och välj Verktyg.
1. Välj **Stödlinjer** i listan över verktyg.
1. Markera rutan **Datakällor**. Sidan **Datakällor** visas. Du kan visa de anslutna datakällorna.

   Du kan växla mellan **listvyn** och **vyn sida vid sida** om du vill visa de olika anslutna datakällorna som en lista eller som rutor.

   <img src="./assets/data-sources-create-window.png" alt= "datakällor som listas på sidan med datakällor" width="800">

   *Visa eller skapa en datakällkoppling.*
1. Klicka på **Skapa**.
1. Välj den databas som du vill skapa kopplingen för. Exempel: Elasticsearch-kopplingen.
   >[!NOTE]
   >
   >Alla tillgängliga färdiga databaser visas.

1. Klicka på **Nästa**.
1. Ange konfigurations- och anslutningsinformation enligt databasen.

   >[!TIP]
   >* Hovring <img src="./assets/info-details.svg" alt= "informationsikon" width="25"> nära fältet om du vill visa mer information om det.
   > * Fält med * är obligatoriska. Du kan till exempel ange följande information för Elasticsearch-kopplingen.

   * **Namn**: Ange namnet på datakällan.
   * Autentiseringstyp: Välj autentiseringstyp i listrutan. Grundläggande autentisering av användarnamn och lösenord
   * **Användarnamn**: Ange ditt användarnamn.
   * **Lösenord**: Ange ditt användarnamn och lösenord.
   * **URL**: Lägg till API-URL:en.

1. Välj **Testa anslutningen**. Du kan bara visa knappen **Testa anslutning** när du har lagt till den information som krävs. Visa ett meddelande om att anslutningen är korrekt. Annars kan du visa ett felmeddelande.



1. Välj **Spara** längst upp för att spara kopplingen.     Visa knappen **Spara** aktiverad när du har fyllt i all information och anslutningen har upprättats.


   Om anslutningen har sparats kan du visa den anslutna datakällan på sidan.

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


När du har konfigurerat datakällan visas kopplingen under panelen **Datakällor** i webbredigeraren. Sedan kan du ansluta till datakällan och infoga ett innehållskuvert i dina ämnen. Mer information finns i [Använd data från datakällan](../user-guide/web-editor-content-snippet.md).

>[!NOTE]
>
>Du kan också skapa anpassade kopplingar och använda dem med olika datakällor. Lär dig hur du [konfigurerar anpassade anslutningar](../knowledge-base/kb-articles/data-source/conf-custom-data-source-connector.md).