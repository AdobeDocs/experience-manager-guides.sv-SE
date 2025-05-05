---
title: Hantera innehåll
description: Hantera innehåll och identifiera roller och behörigheter i AEM Guides. Lär dig de viktigaste begreppen för innehållshantering och att arbeta med globala profiler eller profiler på mappnivå.
exl-id: 84926dc2-1180-48ef-85d0-50e3478bf26a
feature: Content Management
role: User
source-git-commit: 461692ce786f914dd196f289efef726e42bf9660
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Hantera innehåll {#id164JBG0M0T1}

Innan du börjar med själva innehållsskapandet måste du bekanta dig med några grundläggande begrepp för innehållshantering i Adobe Experience Manager Guides. Börja sedan med att skapa olika användargrupper och ordna era resurser.

## Viktiga begrepp

Några viktiga begrepp inom innehållshantering i Adobe Experience Manager är följande:

**Resurshantering**

Experience Manager Guides använder Adobe Experience Manager digitala resurshantering \(DAM\) för att hantera dina DITA-filer. Filerna som du överför eller checkar in i DAM lagras som digitala resurser. Du kan hantera och redigera dina resurser i Adobe Experience Manager Assets. Mer information om resurshantering finns i [Hantera resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=sv-SE).

**Länkhantering**

Flytta eller byt namn på filer eller ändra mappstrukturen i innehållsdatabasen, utan att oroa dig för brutna referenser. Alla referenser till och från det påverkade innehållet uppdateras automatiskt. Få varningar när du tar bort innehåll som refereras någon annanstans för att förhindra oavsiktliga avbrott.

**Hantera versioner**

Experience Manager Guides tillhandahåller versionshantering för digitala resurser. Du kan enkelt aktivera den här funktionen från ett valfritt DITA-redigeringsprogram. Låta skribenterna utföra standardversionskontrollfunktioner som in- och utcheckning.

Mer information om hur du skapar versioner eller återgår till en viss version finns i [Gren, återställ och efterföljande versionshantering](web-editor-preview-topics.md#branch-revert-and-subsequent-versioning).

**Inbyggd DITA-hantering**

Experience Manager Guides bibehåller strukturen i dina DITA-filer, men gör det även möjligt för Adobe Experience Manager att hantera DITA direkt med hjälp av elementmappning för att mappa DITA-elementen till Adobe Experience Manager-komponenter. Den inbyggda DITA-hanteringen används i funktioner som ämnesförhandsgranskning, Adobe Experience Manager Sites-publicering och granskningsarbetsflöden.

## Identifiera din roll och dina behörigheter {#id181TF0K0MHT}

Experience Manager Guides har tre färdiga grupper. Dessa grupper är: *Författare*, *Granskare* och *Utgivare*. Beroende på vilken grupp du är kopplad till har du behörighet att utföra specifika åtgärder enligt tabellen nedan. Publiceringsuppgifterna kan till exempel bara utföras av en utgivare, men inte av en författare eller granskare. På samma sätt kan en författare skapa ett nytt ämne, och en granskare kan bara granska ett ämne.

>[!TIP]
>
> Visa avsnittet *Behörigheter* i guiden Bästa metoder för att ange användarbehörigheter.

I följande tabell visas olika uppgifter och grupper som kan utföra dessa uppgifter:

| Uppgift | Författare | Granskare | Utgivare |
|----|-------|---------|----------|
| Skapa DITA-ämne | Ja |   | Ja |
| Skapa DITA-karta | Ja |   | Ja |
| Kartsamlingar | Ja |   | Ja |
| Skapa granskningsaktivitet | Ja |   | Ja |
| Granska ämne[1](#fntarg_1) | Ja | Ja | Ja |
| Nyckelupplösning | Ja |   | Ja |
| Checka ut/Checka in | Ja |   | Ja |
| Redigera ämne | Ja |   | Ja |
| Flytta ämne | Ja |   | Ja |
| Redigera ämnesegenskaper | Ja |   | Ja |
| Kopiera | Ja |   | Ja |
| Ta bort | Ja |   | Ja |
| Dela | Ja |   | Ja |
| **Dokumentläge** |
| Skapa/redigera dokumenttillståndsprofil |   |   | Ja |
| Ändra dokumentläge[2](#fntarg_2) | Ja | Ja | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Utdatainställningar\)** |
| Generera |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Skapa |   |   | Ja |
| Ta bort förinställning |   |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Utdata\)** |
| Visa genererade utdata | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Ämnen\)** |
| Skapa granskningsaktivitet | Ja |   | Ja |
| Redigera | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Baslinjer\)** |
| Skapa |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Ta bort |   |   | Ja |
| DITA map console \(Reports tab\) | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(Villkorsförinställningar\)** |
| Skapa/redigera villkorsförinställning |   |   | Ja |

[1](#fnsrc_1) Om *Författare* och *Utgivare* bjuds in till en granskning.

[2](#fnsrc_2) Beroende på vilka rättigheter användaren har i dokumentets tillståndsprofil.
