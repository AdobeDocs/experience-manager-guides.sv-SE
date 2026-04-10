---
title: Anpassad indexeringsdistribution för lokal installation
description: Lär dig hur du anpassar indexinnehåll för lokala inställningar
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 5b9e4936-f674-41d3-a7b2-3d42a2523693
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Indexera om för funktionen Sök och ersätt (Source-vyn)

Omindexering krävs för att aktivera funktionen **Sök och ersätt (Source-vyn)** som gör att du kan skanna hela det innehåll som är synligt i redigeringsvyn och även underliggande Source-innehåll (XML-struktur, inklusive element, taggar och attributvärden) för den sökda strängen.

## Omindexering

För lokala inställningar inkluderas indexdefinitionen i paketet. Om du vill aktivera funktionen måste du indexera om innehållet.

Börja omindexera genom att ange egenskapen `reindex=true (Boolean)` på noden ` /oak:index/guidesAssetLucene` för att indexera om tidigare inspelat innehåll.

Omindexeringsprocessen fortsätter tills systemet automatiskt ändrar den här egenskapen till false. Du kan övervaka omindexeringsåtgärdens förlopp i systemloggarna.
