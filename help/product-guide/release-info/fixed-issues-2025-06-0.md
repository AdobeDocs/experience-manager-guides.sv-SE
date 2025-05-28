---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides, version 2025.06.0
description: Läs mer om felkorrigeringarna i version 2025.06.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 78d8896982ff73e954de6d6daa9832faf30ed3b3
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---

# Problem i version 2025.06.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2025.06.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2025.06.0](whats-new-2025-06-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.06.0](upgrade-instructions-2025-06-0.md).

## Redigering

- När du öppnar en DITA-karta med det enhetliga skalet aktiverat uppdateras redigeraren regelbundet. (GUIDES-26919)
- Om det inte går att stänga JCR-sessionsanslutningar när ämnen uppdateras eller skapas resulterar detta i minnesläckor och driftavbrott. (GUIDES-26282)
- Om du drar kolumnerna ändras deras bredd från procent till pixelvärden, vilket resulterar i förvrängda eller feljusterade tabeller.(GUIDES-23128)
- När innehåll klistras in i en `code block` eller när mellanslag läggs till i `code block` och vyn växlas, försvinner mellanrummet. (GUIDES-27478)
- När du lägger till en karta till `bookmap` lagras den i `fmditatopicrefs` i stället för i `fmditamaprefs`. (GUIDES-25480)
- Dialogrutan **Infoga bild** återges inte korrekt på en högupplöst eller utzoomad skärm, vilket gör att figurens rubrik och alternativa textfält försvinner. (GUIDES-26459)


## Publicering

- Den inbyggda PDF-publiceringen fortsätter oavbrutet om DITA-innehållet har en webblänk utan omfång som `external`. (GUIDES-26434)
- Publicering av inbyggda PDF-filer och AEM-webbplatser stoppas och köas om det finns fel i innehållet. (GUIDES-26516)
- När du skapar en ny baslinje med ett stort antal etiketter kommer alla etiketter inte att kunna hämtas. (GUIDES-16232)
- När du genererar AEM Site-sidor med rubriker som innehåller flera ord avgränsade med blanksteg, visas bindestreck i stället för blanksteg. (GUIDES-27903)
- Ett ogiltigt metadataegenskapsnamn kommer inte att matchas för Native PDF och visas som `unresolved property name` i **dokumentegenskaper**. (GUIDES-25680)
- Flerradstext i `codeblock` orsakar textspillproblem under generering av PDF. (GUIDES-15541)
- När du lägger till kartor i kartsamlingen visas andra resurser än kartor (till exempel ämnen) och de översatta kartspråken sorteras inte heller korrekt.(GUIDES-25085)


## Granska

- Dokumentvyn i granskningsgränssnittet figursätter inte innehållet för vissa skärmstorlekar, vilket kräver att användarna rullar vågrätt för att se det fullständiga innehållet. (GUIDES-25292)


## Kända fel

Adobe har identifierat följande kända fel i version 2025.06.0:

- När du använder alternativet Sök och ersätt kan du inte utföra några fler åtgärder på panelen Sök och ersätt när du har använt åtgärden Ersätt enstaka förekomst på en fil. (GUIDES-28930)

- När en redan indexerad resurs tas bort från användargränssnittet i en mappprofil tas inte motsvarande indexerad sökväg bort och ett försök att indexera om misslyckas med ett felmeddelande. (GUIDES-29147) <br>**Tillfällig lösning:** Du måste ta bort den föråldrade sökvägen som inte längre finns innan du initierar omindexeringen.

- Om en karta innehåller cykliska beroenden och du öppnar förhandsgranskningen av kartan, blir vyerna Source, Författare och Layout otillgängliga tills sidan uppdateras. (GUIDES-28334) <br>**Tillfällig lösning:** Du måste uppdatera sidan för att kunna återställa åtkomsten till dessa vyer.
