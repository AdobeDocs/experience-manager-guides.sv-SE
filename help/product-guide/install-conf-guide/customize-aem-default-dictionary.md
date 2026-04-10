---
title: Anpassa AEM standardordlista
description: Lär dig hur du anpassar AEM standardordlista
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Anpassa AEM standardordlista {#id209SD8000WU}

Webbredigeraren kan konfigureras att använda AEM stavningskontroll eller webbläsarens stavningskontroll. Om du väljer att arbeta med AEM stavningskontroll får du flexibilitet att definiera din egen ordlista. Dessa anpassade ord läggs sedan till i AEM-ordlistan och de här orden får inte flaggan \(som felaktiga\) i Web Editor.

På följande flikar finns instruktioner om hur du skapar en egen ordlista som läggs till i AEM ordlista baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Skapa filen user\_dictionary.txt med en lista med ord som du vill definiera i din egen ordlista.

   >[!NOTE]
   >
   > Varje eget ord måste definieras på en ny rad.

1. Spara filen på följande plats i Cloud Manager Git-databasen:

   /apps/fmdita/config

1. Spara filen.

   Genomför ändringarna och kör Cloud Manager \(CI/CD\)-pipeline för att distribuera konfigurationsändringar.


Författare måste starta om sin Web Editor-session för att den anpassade ordlistan ska uppdateras i AEM ordlista.

>[!TAB Lokal]

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till följande nod:

   /apps/fmdita/config

1. Skapa en ny fil med namnet user\_dictionary.txt.

1. Öppna filen och lägg till en lista med ord som du vill definiera i din egen ordlista.

   På följande skärmbild visas en lista med egna ord som lagts till i filen user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Spara och stäng filen.


Författare måste starta om sin Web Editor-session för att den anpassade ordlistan ska uppdateras i AEM ordlista.

>[!ENDTABS]

**Överordnat ämne:**[ Anpassa Web Editor](customize-overview.md)
