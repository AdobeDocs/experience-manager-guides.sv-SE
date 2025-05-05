---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, juni 2023-versionen
description: Läs om felkorrigeringarna och hur du uppgraderar till juni 2023-versionen av Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 0%

---

# Juniversion 2023 av Adobe Experience Manager Guides as a Cloud Service

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i Adobe Experience Manager Guides version juni 2023 (kallas senare *AEM Guides as a Cloud Service*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i juni 2023-utgåvan av AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Uppgradera till juniversionen 2023

Uppgradera din nuvarande AEM Guides as a Cloud Service-konfiguration genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>`-egenskapen i `/dox/dox.installer/pom.xml`-filen för dina Cloud Services Git-kod till 2023.6.297.
3. Genomför ändringarna och kör Cloud Servicen för att uppgradera till versionen från juni 2023 av AEM Guides as a Cloud Service.

## Steg för att aktivera utlösaren för ett skript via en serverlet

När du har slutfört installationen kan du välja att HIT-aktivera utlösaren för att starta översättningsjobbet:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Svar:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

I föregående svar-JSON innehåller nyckeln `lockNodePath` sökvägen till noden som skapades i databasen som pekar på jobbet som skickades. Den tas automatiskt bort när jobbet är klart, tills dess kan du referera till den här noden för aktuell status för jobbet.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du har en version som är tidigare än version från juni 2023 av AEM Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 dita-filer i systemet uppdaterar du `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och distribuerar sedan om.

   - Använd instruktionerna i avsnittet *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides
as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera alternativet queryLimitReads:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-förfrågan till servern (med korrekt autentisering) - `http://<server:port>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera statusen för jobbet kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan fel ses från serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet `queryLimitReads` om du har ändrat det i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du använder en version som är tidigare än september 2022 av AEM Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST-förfrågan till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika banor för mappningarna för att indexera dem. Som standard indexeras alla mappningar \|\| Till exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Du kan också skicka en rotmapp för att indexera DITA-mappningarna för en viss mapp (och dess undermappar). Exempel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Observera, att om både sökvägsparametern och rotparametern skickas, beaktas bara sökvägsparametern.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Exempel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. När jobbet är klart svarar den tidigare GETEN och anger om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.

## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds i AEM Guides as a Cloud Service från juni 2023.

### FrameMaker och FrameMaker Publishing Server

| AEM Guides som Cloud-release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| AEM Guides som Cloud-release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |


## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Navigeringsrubriken tas bort från content33 vid växling från layoutvyn till författaren eller källvyn. (12174)
- Ibland inträffar programfel när du klickar på en DITA-karta. (11842)
- Web Editor | Fast mellanslag läggs till i XML-redigeraren när du redigerar ett ämne. 11786
- Resursgränssnitt | I listvyn kan de överlagrade tillgängliga kolumnerna inte sammanfogas. (11528)
- Keyref är inte löst i kartvyn. (11490)
- Den övre menyn visas inte när du navigerar i XML-redigeraren. (10868)
- `conref` i ph-taggen | Den visade bläddringsdialogrutan är felaktig. 9481
- Lokala länkar till andra element kan inte lösas i Web Editor. (8790)
- Funktionen Matches() fungerar inte i funktionen Schematron. (11224)


### Förvaltning

- Fliken Rapporter i webbredigerarens användargränssnitt visar inte ämneslistan med gamla DITA-kartor som skapats före uppgraderingen till 4.2. 11708

- Knappfunktionen Överför filer i Assets-gränssnittet bryts i version 4.2. (11633)

### Publicering

- Publicering till AEM misslyckas när temporära filer från pod som kan ha uppdaterats eller startats om läses. (12113)
- PDF | Publicering av innehåll som har en utdataklass med hakparenteser() resulterar i en publiceringsfrysning. (11936)
- JSON-utdata | Mappningsmetadata med egenskapsvärdet `"value in spaces and double quotes"` leder till ett publiceringsfel. (11933)
- Web Editor | Det går inte att markera utdatasökväg och -mall i AEM förinställning. (11530)
- PDF | Anpassade attribut sprids inte till motorn för temporära HTML eller PDF. (DXML-12005)
- PDF |  Java OutOfMemoryError inträffar vid publicering av stort innehåll. 11789
- JSON-utdata | Egenskapen `fmUuid` i JSON-noden jcr:content skiljer sig från id:t i JSON. (11564)
- JSON-utdata | Om kartan och ämnet med samma filnamn finns, tas JSON bort för kartan. (11524)
- PDF | Xref skriver ut innehållet i href-ämnesrubriken i stället för Xref-etiketten. (11322)
- PDF | Det går inte att spara mallinställningarna för PDF. (10751)
- PDF | Texten sträcker sig utanför kolumnbredden och inkluderar flera xrefs. (10876)
- PDF | Elementet `<note>` `</note>` genererar inte någon extra intervalltitel av sin typ. (10549)
- PDF | Språkmetadata kan inte anges i det genererade PDF för att uppfylla kraven i WCAG 2.0. (12296)



### Översättning

- Post februari (2302), visar allt översättningsinnehåll Ur synk eller Saknad kopia. (11834)

### Granska

- Nytt gränssnitt för granskning | Villkoren markerar och visar hur de fungerar annorlunda än i Web Editor. (11628)
