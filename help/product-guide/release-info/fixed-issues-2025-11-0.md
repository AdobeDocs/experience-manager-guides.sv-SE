---
title: Versionsinformation | Korrigerade problem i Adobe Experience Manager Guides 2025.11.0
description: Läs mer om felkorrigeringarna i version 2025.11.0 av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: d9a46a009477b1110208a509d4ad8c0616139661
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Åtgärdade problem i version 2025.11.0

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2025.11.0 av Adobe Experience Manager Guides as a Cloud Service.

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i version 2025.11.0](whats-new-2025-11-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.11.0](upgrade-instructions-2025-11-0.md).

## Redigering

- Om ett tomt `prop`-element utan attribut eller värden läggs till i en DITAVAL-fil kan ytterligare `prop`-element inte läggas till. (GUIDES-33597)
- När du har uppgraderat Experience Manager Guides till version 2025.08.0 visas inte längre alternativet att aktivera eller inaktivera den anpassade fliken **Acrobat** i **Workspace-inställningarna**. (GUIDES-35261)
- Anpassad CSS som används på en mappnivåprofil för ämnen eller kartor återställs till standardformatet i förhandsgranskningsläget när webbläsaren uppdateras. (GUIDES-31098)
- **Ångra**- och **Gör om**-åtgärder fungerar inte som väntat i Source-vyn i redigeraren för DITA-filer. (GUIDES-24914, GUIDES-25034)
- När du refererar till en DITA-karta i ett ämne med elementet `Xref` visas filnamnet för den refererade kartan i stället för kartans titel. (GUIDES-21759)
- När du lägger till flera Schematron-filer för validering via den högra panelen i redigeringsgränssnittet, finns inte felet **Schematron-filer eller så visas fel** även om de tillagda filerna är giltiga och inte innehåller några fel. (GUIDES-33731)
- Stora eller komplexa MathML-ekvationer kan inte visas i redigeraren. (GUIDES-29095)

## Resurshantering

- När du överför en redigerad bild på nytt via Experience Manager Guides-gränssnittet uppdateras bildens ursprungliga återgivning, men det tillhörande DITA-innehållet fortsätter att visa den tidigare versionen av bilden. (GUIDES-33693)
- När du försöker flytta två eller flera mappar från deras källplats till en annan plats (med verktyget för flyttning av grupp) misslyckas åtgärden om mappnamnen börjar med samma sträng (t.ex. Produkt och Produktbilder). (GUIDES-29096)
- Om du tar bort en sökd resurs från omforsknings-Assets-gränssnittet kringgås varningsmeddelandet **Tvinga borttagning** och resursen tas bort direkt, även om det finns referenser till den i befintligt DITA-innehåll. (GUIDES-17232)

## Publicering

- När du publicerar en DITA-karta med baslinje på AEM Sites (med äldre komponentmappning) publiceras även mappningselementen med attributet `processing-role = resource-only`. (GUIDES-37649)
- I vissa fall saknas egenskapen `jcr:content/fmUuidOfSource` på AEM Sites utdatasidor (med äldre komponentmappning), vilket gör att nya innehållssidor inte kan identifieras.
- Innehållsfiltrering via DITAVal-filter och villkorsstyrda förinställningar fungerar inte för Salesforce-publicering. (GUIDES-33515)
- Det går inte att skapa en inbyggd PDF-förinställning för en karta om det finns en mapp med samma namn i innehållshierarkin. (GUIDES-33012)
- När inbyggda PDF-utdata genereras med en dynamisk baslinje visas termen **PDFProject** som PDF-titel i stället för den faktiska karttiteln. (GUIDES-31102)
- Generering av inbyggda PDF-utdata med vissa `print`-attributvärden i ämnesreferenser fungerar inte som förväntat. (GUIDES-31101)
- När en mapp som innehåller DITA-kartor flyttas med Assets-gränssnittet eller alternativet **Massflyttning** går det inte att läsa in befintliga kartsamlingar och gruppaktiveringssamlingar som refererar till dessa kartor. (GUIDES-28355)
- När du flyttar en mapp som innehåller en karta med villkorsförinställningar används inte villkoren i de genererade utdata efter flytten. (GUIDES-28352)
- När du genererar AEM Sites-utdata med äldre komponentmappning publiceras ämnen som använder attributet `copy-to` med namnet på `copy-from` -avsnittet i stället för det namn som angetts i attributet `copy-to`. (GUIDES-22155)
- Om du aktiverar en eller flera DITA-kartor från **Kontrollpanelen för masspublicering** genereras mycket stora loggar. (GUIDES-20746)

## Plattform

- Felloggar som genereras när en resurs överförs via Assets-gränssnittet eller när en ny fil skapas från redigeringsgränssnittet, använder felaktigt termen `predecessor` i stället för `successor` i loggmeddelandet. (GUIDES-35607)

## Kända fel

Adobe har identifierat följande kända fel i version 2025.11.0:

- Om du skapar ett duplicerat ämne med attributet `copy-to` och refererar till det med attributet `scope=peer` uppstår omdirigeringsproblem i AEM Sites-utdata, där länkar omdirigeras från AEM Sites (med sammansatt komponentmappning) till AEM Sites (med äldre komponentmappning) och vice versa. (GUIDES-37656)











