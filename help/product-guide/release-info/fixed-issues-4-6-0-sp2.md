---
title: Versionsinformation | Problem i Adobe Experience Manager Guides 4.6.0 Service Pack 3 har åtgärdats
description: Läs mer om felkorrigeringarna i version 4.6.0 Service Pack 3 av Adobe Experience Manager Guides
role: Leader
source-git-commit: d60fea16831af458c479df24c877ef7095b2fd15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Åtgärdade problem i version 4.6.0 Service Pack 3 (januari 2025)


Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 4.6.0 av Service Pack 3 av Adobe Experience Manager Guides.

Läs mer om [uppgraderingsinstruktioner för version 4.6.0 Service Pack 3](upgrade-instructions-4-6-0-sp2.md).

## Redigering

- Alla villkorsgrupper går förlorade och villkoren förenklas när villkoren uppdateras från mappprofilen. 23526
- Om du ändrar värdet för rubrikraderna för en tabell på panelen **Innehållsegenskaper** tillämpas inte det uppdaterade värdet. 23213
- När du lägger till nya ämnesreferenser i DITA-kartan med hjälp av dialogrutan för elementet för ämnesreferens **i layoutvyn visas de tillagda referenserna som brutna länkar.** (22859)
- När du lägger till ämnen i DITA-kartan med hjälp av dialogrutan **Ämnesreferenselement** i författarvyn, infogas de markerade ämnena i omvänd ordning om de markeras. (22858)
- När du kopierar en bild från en extern produkt (till exempel MS PowerPoint) och klistrar in den i stödlinjer, bryts funktionen att överföra resursen direkt för användning i filen. 24983
- Om du söker efter filer i databasen med funktionen **Sök och filtrera** kan du inte markera flera filer. (25104)

## Publicering

- Publicering till Salesforce misslyckas om innehållet innehåller fasta mellanslag. (23664)
- För ämnen som innehåller fel som brutna länkar misslyckas Salesforce publicering och förloppsindikatorn visas i oändlighet. (22985)
- För kartor med trasiga länkar misslyckas Salesforce publicering och förloppsindikatorn visas i oändlighet. 24963
- Om en extern länk innehåller ett UUID, fortsätter den efterbearbetningen och konverterar den externa länken till UUID-länken, vilket bryter länken i webbredigeraren och även på publiceringswebbplatserna. (22574)
- `xref` konverteras till relativ länk även när länkens **scope** är inställt på **external**. 23059
- Det går inte att skapa inbyggda PDF för innehåll med attributet **chunk** inställt på **to-content**. 21772
- Dialogrutan **Redigera egenskaper** för en baslinje visar inte tidigare sparade villkor för dynamisk baslinje. 23964


## Översättning

- Om du flyttar ett ämne i källsökvägen till en annan mapp för en översättning som inte är äldre (för icke-UID) resulterar det i brutna referenser i målspråket. (24152)
