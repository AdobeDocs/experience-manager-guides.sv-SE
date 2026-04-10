---
title: Anpassa AEM standardordlista
description: Lär dig hur du anpassar AEM standardordlista
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Anpassa AEM standardordlista {#id209SD8000WU}

Webbredigeraren kan konfigureras att använda AEM stavningskontroll eller webbläsarens stavningskontroll. Om du väljer att arbeta med AEM stavningskontroll får du flexibilitet att definiera din egen ordlista. Dessa anpassade ord läggs sedan till i AEM-ordlistan och de här orden får inte flaggan \(som felaktiga\) i Web Editor.

Så här skapar du en lista med egna ord som läggs till i AEM ordlista:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till följande nod:

   /apps/fmdita/config

1. Skapa en ny fil med namnet user\_dictionary.txt.

1. Öppna filen och lägg till en lista med ord som du vill definiera i din egen ordlista.

   På följande skärmbild visas en lista med egna ord som lagts till i filen user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Spara och stäng filen.


Författare måste starta om sin Web Editor-session för att den anpassade ordlistan ska uppdateras i AEM ordlista.

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](conf-web-editor.md)
