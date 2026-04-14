---
title: Lägg till anpassade teckensnitt i din DITA PDF
description: Få anpassad teckensnittsintegrering för att stärka varumärkesidentiteten och den visuella enhetligheten i allt innehåll i PDF-filer från DITA.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Lägg till anpassade teckensnitt i din DITA-PDF

## Denna artikel omfattar

Lägg till det anpassade teckensnittet för att stärka varumärkesidentiteten och den visuella enhetligheten i allt innehåll.

Den här processen omfattar tre steg:

- [Överför det anpassade teckensnittet](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Gör nödvändiga ändringar i PDF-mallarnas formatmall](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Bädda in använda teckensnitt (valfritt)](#step-3-optional--embed-used-font-in-pdf)

## Steg 1: Överför det anpassade teckensnittet till mallens resursmapp

![Anpassad teckensnittsuppladdning och import ](../assets/publishing/custom-font1.png)

## Steg 2: Gör nödvändiga ändringar i PDF-mallarnas formatmall

![Teckensnitt i PDF mallens formatmall ](../assets/publishing/custom-font2.png)

## Steg 3 (valfritt): Bädda in använt teckensnitt i PDF

![Anpassad teckensnittsinbäddning i DITA PDF ](../assets/publishing/custom-font3.png)

## Vanliga frågor

### Kan jag använda Adobe Fonts?

> Ja, gå till fonts.adobe.com och klicka på&quot;Lägg till i webbprojekt&quot;.
> 
> Kopiera importkod som `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Klistra in CSS-innehållet och gör önskade ändringar i CSS-filen.

![Använd Adobe-teckensnitt i DITA PDF](../assets/publishing/custom-font4.png)


### Mitt teckensnitt visas inte i PDF

> Dubbelkontrollera stavning av teckensnittsnamn (vanligaste fel)
>
> Se till att du bäddar in teckensnitt om teckensnitten inte är tillgängliga i det system där PDF är öppet

## Kontakta dina respektive CSM för andra frågor


## Andra resurser:

- [Inkludera DITA-bokmappens innehållsförteckning i PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Lägga in innehållsförteckning i PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Video från expertsessioner på PDF](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
