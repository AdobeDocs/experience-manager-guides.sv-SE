---
title: Recommendations för prestandaoptimering
description: Lär dig Recommendations för prestandaoptimering
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: b28b7d96cce69f677b0bcf891b94d7ac84eb1eb0
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Recommendations för prestandaoptimering {#id213BD0JG0XA}

## Konfigurera datalager \(obligatoriskt\)

**Vad är ändringen?**
Ställ in egenskapen `minRecordLength` på värdet `100` under konfigurationen `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` Mer information om fillagring och S3-datalager finns i artikeln [Konfigurera nodarkiv och datalager i AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html) .

>[!NOTE]
>
> Kostnaden för att underhålla innehåll i datalagret beror också på antalet förfrågningar för S3-datalagret. När du gör den här inställningen med S3 bör därför även installationskostnaden per begäran och cachestorleken beaktas.

**När ska jag konfigurera?**
Efter den första konfigurationen, men innan något innehåll migreras. Du måste utföra den här ändringen även på ett befintligt system, vilket garanterar att allt nytt innehåll lagras i datalagret i stället för i segmentlagret.

**Resultat av den här ändringen**
DITA-filerna sparas i datalagret i stället för segmentlagret. Detta håller segmentlagrets storlek under rekommenderade gränser, vilket förbättrar systemets svarstider.

## Uppdatera Lucene-index \(obligatoriskt\)

**Vad är ändringen?**
Uteslut /var/dxml från ek:index/lucene.

>[!NOTE]
>
> AEM Guides använder aldrig Lucene-index för att söka efter innehåll i noden /var/dxml.

**När ska jag konfigurera?**
Om du gör den här ändringen på ett nytt system innan du migrerar innehåll behöver du bara uppdatera eken:index/lucene. I annat fall kan du återskapa index för Lucene \(*som kan ta några timmar att slutföra*\) efter att ha gjort ändringen i eke:index/lucene på ett befintligt system där innehållet redan har migrerats.

**Resultat av den här ändringen**
Den här ändringen förhindrar att /var/dxml-noden indexeras och lagras i segmentlagret.

## Java-minnesoptimering \(obligatoriskt\)

**Vad är ändringen?**
Parametrarna för JVM-start bör justeras noggrant baserat på infrastrukturen och diskstorleken. Vi rekommenderar att du kontaktar Adobe Support för att få hjälp med att komma åt den idealiska konfigurationen. Du kan dock själv prova följande konfigurationer:

- Ställ in JVM-stackstorleken på minst 1/4 av det totala tillgängliga minnet. Använd parametern `-Xmx<size>` för att ange heap-minnesstorleken. Ange värdet för -`Xms` är lika med `-Xmx`.

- Aktivera `-XX:+HeapDumpOnOutOfMemoryError` och ange sökvägen för `-XX:HeapDumpPath=</path/to/folder``>`.

- Aktivera Java GC-logg som:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- I Java 11 använder du G1GC \(`-XX:+UseG1GC`\) och för Java 8 använder du CMS \(-`XX:+UseConcMarkSweepGC`\).

- Använd `-XX:NewRatio` för att kontrollera storleken på den unga generationens minnesstorlek. Standardvärdet är 2, vilket innebär att 1/3 av minnet används för ung generering. Eftersom det finns många objekt som snabbt skapas och förstörs kommer 1/2 av minnet att tilldelas den unga generationen med värdet 1.

- Kontrollera antalet objekt som befordras till den gamla genereringen med `-XX:MaxTenuringThreshold`. Använd värdet 15 \(standard\) för att fördröja när objekt befordras till den gamla genereringen.

**När ska jag konfigurera?**
Om du gör den här ändringen på ett befintligt system måste du starta om systemet. Vid en ny installation bör den här ändringen göras i startskriptet \(.bat eller .sh\) innan systemet startas.

**Resultat av den här ändringen**
Detta resulterar i optimal stackstorlek och reglerad körning av global katalog.

## Miniatyr av klientbibliotek på författarinstans \(valfritt\)

**Vad är ändringen?**
Klientbiblioteken ska ställas in på minify i Authoring-instanserna. På så sätt ser du till att det finns färre byte att hämta när en användare bläddrar i systemet från olika platser. Om du vill göra den här ändringen anger du konfigurationen i **HTML Library Manager** från Felix-konsolen.

**När ska jag konfigurera?**
Detta kan göras vid körning via Felix Console eller via koddistribution.

**Resultat av den här ändringen**
Den här ändringen förbättrar inläsningstiden för sidor på Author-instansen eftersom färre byte överförs för inläsning av klientbiblioteken.

## Konfigurera samtidiga publiceringstrådar \(Obligatoriskt, beroende på användningsfall\)

**Vad är ändringen?**
Den här ändringen är nödvändig om du använder DITA-OT för att publicera utdata och ett antal samtidiga publiceringstrådar definieras också.

Som standard ställer AEM Guides in publiceringstrådarna på antalet CPU+1. Vi rekommenderar dock att du anger det här värdet till hälften \(1/2\) eller en tredjedel \(1/3\) av det totala antalet processorer. Det gör du genom att ställa in egenskapen **Generationspoolstorlek** under konfigurationen `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` enligt rekommendationerna.

**När ska jag konfigurera?**
Detta kan göras vid körning via Felix Console eller via koddistribution.

**Resultat av den här ändringen**
Ändringen säkerställer att inga resurser allokeras för publiceringsåtgärderna på en författarinstans som körs. Detta gör att systemresurserna är tillgängliga även för författare, vilket ger en bättre användarupplevelse.

## Konfigurera gruppstorlek för noder för generering AEM platsutdata \(obligatoriskt, beroende på användningsfall\)

**vad är ändringen?**
Den här ändringen krävs om du genererar AEM Sites-utdata.

Ange **Begränsa AEM webbplatssidor i egenskapen Heap** under `com.adobe.fmdita.config.ConfigManager` till ett nummer baserat på systemets konfiguration. Den här egenskapen definierar gruppstorleken för noder som ska verkställas när webbplatssidorna genereras. På ett system med ett större antal processorer och stackstorlek kan du öka standardvärdet från `500` till ett större värde. Du måste testa körningen med det ändrade värdet för att få ett optimalt värde för den här egenskapen.

**När ska jag konfigurera?**
Detta kan göras vid körning via Felix Console eller via koddistribution.

**Resultat av den här ändringen**
Ett ökat antal **Begränsa AEM webbplatssidor i heap** -egenskapen optimerar genereringsprocessen för AEM.


**Överordnat ämne:**[ Hämta och installera](download-install.md)
