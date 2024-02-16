---
title: Versionsinformation | Uppgraderingsinstruktioner och åtgärdade fel i Adobe Experience Manager Guides, februari 2024-versionen
description: Lär dig mer om felkorrigeringarna och hur du uppgraderar till februari 2024-utgåvan av Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 0%

---

# Version av Adobe Experience Manager Guides as a Cloud Service från februari 2024

Den här versionsinformationen innehåller uppgraderingsinstruktioner, kompatibilitetsmatris och problem som åtgärdats i version från februari 2024 av Adobe Experience Manager Guides as a Cloud Service (kallas senare *as a Cloud Service stödlinjer för Experience Manager*).

Mer information om de nya funktionerna och förbättringarna finns i [Nyheter i februari 2024-utgåvan av as a Cloud Service Experience Manager Guides](whats-new-2024-02-0.md).

## Uppgradera till februari 2024-versionen

Uppgradera din nuvarande konfiguration av Experience Manager Guides as a Cloud Service genom att utföra följande steg:

1. Ta en titt på Cloud Servicens Git-kod och växla till den gren som är konfigurerad i Cloud Servicens pipeline för den miljö som du vill uppgradera.
2. Uppdatera `<dox.version>` egenskap i `/dox/dox.installer/pom.xml` fil med dina Cloud Service Git-kod till 2024.02.0.15.
3. Genomför ändringarna och kör Cloud Servicen för att uppgradera till februari 2024-utgåvan av Experience Manager Guides as a Cloud Service.

## Steg för att aktivera utlösaren för ett skript via en serverlet

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

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

I det tidigare svaret på JSON, nyckeln `lockNodePath` innehåller sökvägen till den nod som skapas i databasen som pekar på det skickade jobbet. Den tas automatiskt bort när jobbet är klart, så du kan referera till den här noden för jobbstatus.

Vänta tills jobbet är klart innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steg för att bokföra det befintliga innehållet så att det använder den brutna länkrapporten

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

Utför följande steg för att efterbearbeta befintligt innehåll och använda den nya brutna länkrapporten:

1. (Valfritt) Om det finns fler än 100 000 DITA-filer i systemet uppdaterar du `queryLimitReads` och `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett större värde (vilket värde som helst som är större än antalet resurser, till exempel 200 000) och sedan distribuera om.

   - Använd instruktionerna i *Konfigurationsåsidosättningar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service för att skapa konfigurationsfilen.
   - Ange följande (egenskap) information i konfigurationsfilen för att konfigurera `queryLimitReads` och `queryLimitInMemory` alternativ:

     | PID | Egenskapsnyckel | Egenskapsvärde |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 Standardvärde: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Värde: 200000 Standardvärde: 100000 |

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server>//bin/guides/reports/upgrade`.

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Till exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan felet ses i serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för `queryLimitReads` om du har ändrat den i steg 1.

## Steg för att indexera befintligt innehåll så att det använder den nya sök- och ersätt-listan och ämneslistan på fliken Rapporter:

(Endast om du använder en version som är tidigare än versionen från juni 2023 av Experience Manager Guides as a Cloud Service)

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappnivå och ämneslista på fliken Rapporter:

1. Kör en POST-begäran till servern (med korrekt autentisering) - `http://<server:port>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika sökvägar för kartorna för att indexera dem. Som standard indexeras alla kartor|| Till exempel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Till exempel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. När jobbet är klart svarar den tidigare GETEN med framgång. Om jobbet misslyckas av någon anledning kan fel ses från serverloggarna.

1. Återgå till standardvärdet eller det tidigare befintliga värdet för queryLimitReads om du har ändrat det i steg 1.

## Steg som ska hantera `'fmdita rewriter'` konflikt

Experience Manager Guides har en [**egen sling-omskrivare**](../cs-install-guide/conf-output-generation.md#custom-rewriter) för hantering av länkar som genereras vid korsmappningar (länkar mellan ämnen i två olika kartor).

Om du har en annan anpassad Sing Rewriter i kodbasen använder du en `'order'` värdet är större än 50, eftersom Experience Manager Guides sling rewriter använder `'order'` 50.  Om du vill åsidosätta detta måste du ange ett värde > 50. Mer information finns i [Omskrivningsförlopp för utdata](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Under uppgraderingen har `'order'` värdet ändras från 1 000 till 50, du måste sammanfoga den befintliga anpassade omskrivaren, om det finns någon, med `'fmdita-rewriter'`.


## Kompatibilitetsmatris

I det här avsnittet visas kompatibilitetsmatrisen för de program som stöds av Experience Manager Guides as a Cloud Service från februari 2024.

### FrameMaker och FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | Inte kompatibel | 2022 eller senare |
| | | |


### Syrgasanslutning

| Experience Manager Guides as a Cloud Release | Syrgasanslutningsfönster | Syrgasanslutning Mac | Redigera i syrgasfönster | Redigera i Syrgas Mac |
| --- | --- | --- | --- | --- |
| 2024.02.0 | 3.1-uuid.17 | 3.1-uuid.17 | 2,3 | 2,3 |
|  |  |  |  |


### Kunskapsbasmallens version

| Komponentpaketets namn | Komponentversion | Mallversion |
|---|---|---|
| Innehållspaket för komponenter i Experience Manager-stödlinjer för Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Åtgärdade problem

De buggar som har åtgärdats i olika områden listas nedan:

### Redigering

- Stavningskontrollen i Redigeraren tillåter inte val av förslag. 15045
- Den globala navigeringsknappen fungerar inte och instrumentpanelen kan inte läsas in. 14968
- I Web Editor kan funktionen för hämtning av karta inte utlösa ett popup-meddelande när den är klar att hämtas. 14626
- I Web Editor kan funktionen för hämtning av karta inte hämta en karta med baslinjen. (14622)
- Ogiltigt DTD-fel i den as a Cloud Service versionen 2310 av stödlinjerna för Experience Manager. 14482
- När du drar ett ordlisteämne från databasen till en ordlista skapas `topicref`. (10767)
- Web Editor avinstalleras efter ominstallation av Adobe Experience Manager Guides version 4.3.1. 14519
- Installationsprogrammet för version 4.3.1 påträffar en filterkonflikt, vilket resulterar i att `apps/cq/core/content/projects/properties`. 14517
- Förhandsgranskningsskärmen för fragment fryses. (14840)

### Publicering

- Vid publicering i Native PDF fungerar inte anpassade attribut i villkorsförinställningar för publicering i Native PDF. 14943
- Det går inte att lägga till en anpassad mall från **Utdata** i redigeraren. 14846
- **AEM** förinställningen fungerar inte på grund av en tom mallsökväg. 14804
- AEM Site regeneration misslyckas för DITA-kartor med ämnen som innehåller MathML-ekvationer. (14790)
- Vid publicering i PDF genererar PDF fel när det gäller att hämta beroenden för `Node.js` publicering. 14445
- AEM kan inte välja en mall utanför `/content` hierarkin i Web Editor. (14260)
- I AEM Sites-utdata har formatet eller radbrytningarna gått förlorade för `<lines>` element med delelement .(12542)
- Anpassade metadata är inte tillgängliga i det slutliga resultatet. (12116)
- Vid uppgradering till version 4.3.1 inträffar vissa undantag i noden Native PDF. 14492


### Förvaltning

- **Baslinjefilter** filer fungerar inte med Filnamn i Web Editor. 13486
- Om du inaktiverar indexeringen av den överordnade DITA-kartan för att få bättre prestanda kan vissa funktioner påverkas.(12213)
- Etiketter från `labels.json` filen visas i slumpmässig ordning i Web Editor. (10508)

### Granska

- Snabbmenyn för högerklickning fungerar inte för **Acceptera** eller **Avvisa** spåra ändringar. 14607
- Växla till att stänga DITA-avsnitt på Granskningsskärmen fungerar inte i version 4.3.1 av Adobe Experience Manager-guider. 14537
- Det går inte att anpassa e-postmallar för granskningsarbetsflöden med övertäckning. 13954

## Känt fel

Adobe har identifierat följande kända fel i februari 2024-utgåvan:

- Version 1.0 visas inte i användargränssnittet för den duplicerade DITA-filen.
