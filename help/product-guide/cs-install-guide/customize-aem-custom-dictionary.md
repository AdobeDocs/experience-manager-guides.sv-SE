---
title: Anpassa AEM standardordlista
description: Lär dig hur du anpassar AEM standardordlista
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Anpassa AEM standardordlista {#id209SD8000WU}

Webbredigeraren kan konfigureras att använda AEM stavningskontroll eller webbläsarens stavningskontroll. Om du väljer att arbeta med AEM stavningskontroll får du flexibilitet att definiera din egen ordlista. Dessa anpassade ord läggs sedan till i AEM-ordlistan och de här orden får inte flaggan \(som felaktiga\) i Web Editor.

Så här skapar du en lista med egna ord som läggs till i AEM ordlista:

1. Skapa filen user\_dictionary.txt med en lista med ord som du vill definiera i din egen ordlista.

   >[!NOTE]
   >
   > Varje eget ord måste definieras på en ny rad.

1. Spara filen på följande plats i Cloud Manager Git-databasen:

   /apps/fmdita/config

1. Spara filen.

   Genomför ändringarna och kör Cloud Manager \(CI/CD\)-pipeline för att distribuera konfigurationsändringar.


Författare måste starta om sin Web Editor-session för att den anpassade ordlistan ska uppdateras i AEM ordlista.

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](conf-web-editor.md)
