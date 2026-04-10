---
title: Anpassad indexeringsdistribution för lokal installation
description: Lär dig hur du anpassar indexinnehåll för lokala inställningar
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Omindexering för funktionen Sök och ersätt (Source-vyn) för lokal

Omindexering krävs för att aktivera funktionen **Sök och ersätt (Source-vyn)** som gör att du kan skanna hela det innehåll som är synligt i redigeringsvyn och även underliggande Source-innehåll (XML-struktur, inklusive element, taggar och attributvärden) för den sökda strängen.

## Omindexering

För lokala inställningar inkluderas indexdefinitionen i paketet. Om du vill aktivera funktionen måste du indexera om innehållet.

Börja omindexera genom att ange egenskapen `reindex=true (Boolean)` på noden ` /oak:index/guidesAssetLucene` för att indexera om tidigare inspelat innehåll.

Omindexeringsprocessen fortsätter tills systemet automatiskt ändrar den här egenskapen till false. Du kan övervaka omindexeringsåtgärdens förlopp i systemloggarna.
