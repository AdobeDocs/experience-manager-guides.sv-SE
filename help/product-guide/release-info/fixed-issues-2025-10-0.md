---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2025.10.0
description: Läs mer om felkorrigeringarna i version 2025.10.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ff3cf777bd348edded29d780031df59bbb03035d
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# Problem i version 2025.10.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2025.10.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2025.10.0](whats-new-2025-10-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.10.0](upgrade-instructions-2025-10-0.md).

## Redigering

- När flera DITA-kartor eller -ämnen är öppna och ett av ämnena stängs, överlappas knappen **>>** som visar alla öppna flikar med de återstående öppna flikarna på flikfältet. (GUIDES-31421)
- När **godkännandearbetsflödet** är aktiverat visas inte knappen **Starta en ny release** i redigerarens verktygsfält om både den vänstra panelen och panelen Innehållsegenskaper är öppna. (GUIDES-29093)
- När fragmentnamnen överskrider fragmentpanelens bredd radbryts de felaktigt på nästa rad, vilket resulterar i överlappning med intilliggande fragment och påverkar läsbarheten. (GUIDES-22685)
- När du lägger till samma referens flera gånger till en DITA-karta visar vyn **Karta** endast titeln för den senaste förekomsten, medan de föregående visar referensens UUID. (GUIDES-9699)
- DITAVAL-filerna förblir redigerbara även om de är låsta av en annan användare eller om servern har **Inaktivera redigering utan att låsa filen** och filen öppnas i skrivskyddat läge. (GUIDES-27754)
- Loggar för noder som saknas genereras från interna rensningsjobb som inte är obligatoriska och felaktigt markeras som fel, vilket resulterar i röriga loggfiler. (GUIDES-31765)


## Publicering

- När du genererar PDF-filer ignoreras filterreglerna i en DITAVAL-fil om något egenskapsnamn innehåller en punkt. (GUIDES-33229)
- Salesforce publicering misslyckas med ett programfel, när det redan finns ett ämne med samma namn och URL. (GUIDES-32390)
- Salesforce-publicering visar en lyckad status på användargränssnittet även när en DITA-karta som innehåller ett `topichead`-element inte kan publicera avsnitten i det. (GUIDES-32143)
- För utdataförinställningen för HTML5 fungerar inte sökfilterfunktionen i AEM Assets för DITAVAL-filtrering eftersom motsvarande filer inte visas när DITAVAL-filtret har valts. (GUIDES-28231)
- När du genererar ett inbyggt PDF-objekt för en DITA-karta med flera ämnen, och om något ämne innehåller ett `fig`-element i en `figgroup` tillsammans med en `title`, återges `figgroup`-titeln felaktigt som en kapitelrubrik i innehållsförteckningen. (GUIDES-23223)
- När du duplicerar PDF-mallar från användargränssnittet dupliceras även UUID, vilket gör att mallfiler tas bort och leder till felaktiga PDF-utdata. (GUIDES-30456)
- När du genererar ett ursprungligt PDF för en DITA-karta återges titeln för elementet `example` som `h1` rubriknivå, vilket leder till visuell inkonsekvens och felaktig innehållsförteckningsstruktur. (GUIDES-19958)

## Översättning

- När du zoomar in skärmen för översättningsgränssnittet flyttas knappen **Skicka för översättning** under ellipsen och aktiveras även utan att någon resurs markeras. (GUIDES-33720)
- När du väljer filer med statusen **Efter synkronisering** i översättningsgränssnittet och skärmbredden begränsas på grund av öppna paneler till vänster och höger, kortas etiketten **Skicka för översättning** av. (GUIDES-33692)

## Granska

- När en granskare slutför en granskningsuppgift eller initieraren uppdaterar en granskningsuppgift utan att skriva in kommentarer, visas den senaste föregående kommentaren i e-postmeddelandet. (GUIDES-33590)

## Kända fel

Adobe har identifierat följande kända fel i version 2025.10.0:

- När du öppnar en URL med ett tidigare öppnat DITA-avsnitt eller uppdaterar ett öppet DITA-avsnitt går det inte att hitta ämnet i databasen trots att inställningen **Hitta alltid filer i databasen** är aktiverad i användarinställningarna. (GUIDES-35565)<br>**Tillfällig lösning**: Välj ämnesfliken för att leta upp filen i databasen.

- När du skapar en ny fil i redigeringsvyn med flera filer som redan är öppna, uppdateras inte den högra panelen och felaktiga data visas om markören placeras i en elementtagg i en annan fil. (GUIDES-35450)<br>**Tillfällig lösning**: Byt flikar eller uppdatera sidan för att lösa problemet.

- När du växlar till redigeringsvyn från Source-vyn för ett nyligen öppnat ämne (som först öppnas i Source-läge), blir ämnesinnehållet tomt. (GUIDES-35000)<br>**Tillfällig lösning**: Uppdatera sidan eller öppna ämnet på nytt för att lösa problemet.

- Knappen **Uppdatera navigering** visas för DITA-ämnesfiler, men den bör bara vara tillgänglig för DITA-kartor, bokkartor och ämnesscheman. (GUIDES-35452)






