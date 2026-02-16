---
title: Versionsinformation | Nyheter i februari 2026 av produktutbildnings- och utbildningsmaterial
description: Läs om de nya och förbättrade funktionerna i februari 2026-versionen av produktutbildnings- och utbildningsmaterial
role: Leader
hidefromtoc: true
source-git-commit: 5ba7ba00cbc9209aad9f17f0793d621f1f1838e2
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Februari 2026-versionen av produktutbildnings- och utbildningsinnehåll

Den här versionsinformationen innehåller de nya funktionsförbättringarna och problemen som korrigerades i februari 2026-versionen av produktutbildnings- och utbildningsinnehåll.

## Nya funktionsförbättringar

Följande funktioner introducerades i februari 2026-versionen av produktutbildnings- och utbildningsinnehåll:

- **Stöd för underrubriker**: Nu kan du lägga till underrubriker i ditt utbildningsinnehåll med det nya alternativet **Lägg till underrubrik** i **Filegenskaper**. Detta ökar skärpan och förbättrar sökbarheten i hela kursinnehållet.

  Mer information finns i [Lägg till titel och undertitel i utbildningsinnehåll](../learning-content/lc-basic-blocks.md#add-title-and-subtitle-to-learning-content).

  ![](assets/add-subtitles.png)

- **Aktivera eller inaktivera slutlig negativ poäng**: När du konfigurerar frågez-egenskaper kan du styra negativ poäng med alternativet **Tillåt negativ slutlig poäng**. När det här alternativet är aktiverat får de studerande minst värdet noll, även om negativa markeringar används. Detta gör att eleverna blir motiverade genom att poängen aldrig sjunker under noll.

  Läs mer om [Quiz-egenskaper](../learning-content/quiz-properties.md).

  ![](assets/negative-scores-lc.png)

- **Ta bort widgetar genom att högerklicka**: Förutom att ta bort frågor kan du nu ta bort widgetar som dragspelspaneler, Flip-kort och flikar med **Högerklicka > Ta bort objekt**. Den här förbättringen utökar den befintliga funktionen *Ta bort fråga* till widgetar, så att du kan ta bort dem med färre klick och minimal navigering.

  Läs mer om [Använd interaktiva widgetar](../learning-content/lc-widgets.md).

  ![](assets/delete-widget-items.png)
- **Fäst svarsalternativ**: Du kan nu fästa specifika svarsalternativ så att deras position förblir oförändrad, även när svaren slumpmässigt väljs under generering av SCORM-utdata. Det här är särskilt användbart för alternativ som *Alla ovan* eller *Inget av ovanstående*.

  ![](assets/pin-question.png)
- **Kort svarstyp**: Med den korta svarstypen kan eleverna svara med korta, beskrivande alfanumeriska svar i stället för att välja fördefinierade alternativ. Denna frågetyp uppmuntrar eleverna att aktivt uttrycka sin förståelse för sina egna ord och göra bedömningar mer engagerande för eleverna.

  Läs mer om [frågetyper](../learning-content/quiz-insert-questions.md#question-types).


  ![](assets/short-answer.png)
- **Sekventiellt försök med frågor**: Du kan nu framtvinga sekventiella frågeformulärsförsök för SCORM-utdata med alternativet **Eleverna måste försöka att fortsätta med varje fråga** i SCORM-utdataförinställningen. När det här alternativet är aktiverat måste eleverna besvara varje fråga innan de går vidare, och navigeringen begränsas tills den aktuella frågan är slutförd. Detta ger ett guidat, stegvis bedömningsflöde och en konsekvent inlärningssituation.

  Mer information finns i [Konfigurera förinställning för SCORM-utdata](../learning-content/config-scorm-preset.md).

  ![](assets/scorm-general-tab-v3.png)

## Åtgärdade problem

Följande problem har åtgärdats i februari 2026-versionen av produktutbildnings- och utbildningsinnehåll:

- När SCORM-utdata publiceras och distribueras på ALM visar L2 Quiz-rapporten felaktiga totalt- och maxpoäng för frågor som använder flera försök och slumpmässigt urval av frågebanker. (GUIDES-38855)
- När en kurs genereras på molnservern visas ett oavsiktligt tomt utrymme under copyrightsidfoten på grund av formatmallen `coralui3.css`, vilket orsakar inkonsekvenser i layouten. (GUIDES-38853)
- När du navigerar i en utbildning med ett dragspel med tangentbordet markeras inte plustecknet eller tabbtiteln, vilket förhindrar visuell identifiering av det aktiva elementet. (GUIDES-38852)
- För kurser som genereras med SCORM-mallen eller standardmallen visas inte modullänkar som förhindrar navigering när de öppnas på en mobil enhet i liggande läge. (GUIDES-38851)
- När du replikerar hierarkin för en kurs i Experience Manager Guides måste du först skapa en Learning-grupp för att kunna skapa ett Learning-objekt, eftersom tillägg på objektnivå inte stöds. (GUIDES-38849)
- Ett försök att komma åt listrutealternativen i Matcha följande frågetyp med tangentbordet misslyckas eftersom alternativen inte svarar på tabb- eller piltangenterna som förhindrar navigering. (GUIDES-38985)
- Om du använder en förinställning för rubrikformat försvinner den markerade texten, troligen på grund av att teckensnittsfärgen ändras till vitt, vilket gör att texten inte kan markeras och inte visas. (GUIDES-39981)
- När du använder Experience Manager Guides i Mozilla Firefox visar Vänd-kortet texten på framsidan bakåt efter vändning. (GUIDES-39983)
- När du klickar på Innehållsförteckning i den vänstra rutan för kursen fortsätter kursen att visa en slutförandestatus även om frågeformuläret har misslyckats. (GUIDES-40398)
- Om du försöker att Matcha följande frågetyp i ett frågeformulär felaktigt i ALM visas inte de valda alternativen i rapporten. (GUIDES-38640)
- När du genererar PDF-utdata bevaras inte de använda redigeringsformaten, vilket resulterar i inkonsekvenser i designen.(GUIDES-38642)

