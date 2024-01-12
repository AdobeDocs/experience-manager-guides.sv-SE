---
title: Anpassa AEM standardordlista
description: Lär dig hur du anpassar AEM standardordlista
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Anpassa AEM standardordlista {#id209SD8000WU}

Webbredigeraren kan konfigureras att använda AEM stavningskontroll eller webbläsarens stavningskontroll. Om du väljer att arbeta med AEM stavningskontroll får du flexibilitet att definiera din egen ordlista. Dessa anpassade ord läggs sedan till i AEM ordlista och de här orden får inte flaggan \(som felaktiga\) i Web Editor.

Följ de här stegen för att skapa din egen ordlista som läggs till AEM ordlista:

1. Logga in AEM och öppna läget CRXDE Lite.

1. Navigera till följande nod:

   /apps/fmdita/config

1. Skapa en ny fil med namnet user\_dictionary.txt.

1. Öppna filen och lägg till en lista med ord som du vill definiera i din egen ordlista.

   På följande skärmbild visas en lista med egna ord som lagts till i filen user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Spara och stäng filen.


Författare måste starta om sin Web Editor-session för att den anpassade ordlistan ska uppdateras i AEM ordlista.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
