---
title: Konvertera icke-UID-innehåll med versioner till UUID-innehåll från användargränssnittet
description: Lär dig hur du migrerar icke-UID-innehåll med 4.3.x-versioner.
source-git-commit: f18c19eb493cd4d2003f68b082e71ebe7b3e6b7a
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Migrera icke-UID-innehåll med versioner från användargränssnittet

Om du använder version 4.3.x eller senare utför du de här stegen för att migrera icke-UID-innehåll med versioner till UUID-innehåll.

## Kompatibilitetsmatris

| Aktuell version AEM stödlinjer (ej UUID) | Version som krävs för att migrera till UUID | Uppgraderingssökväg som stöds |
|---|---|---|
| 4.3.x eller högre | 4.3.0 ej UUID | Installera 4.3.1 (UUID) |

## Obligatoriska paket

1. **Rensa version**: `com.adobe.guides.version-purge-1.0.11.zip` (valfritt)
1. **Före migrering**: `com.adobe.guides.pre-uuid-migration-1.1.2 .zip`
1. **Migrering**: `com.adobe.guides.uuid-upgrade-1.1.13.zip`



## Före migrering

1. (Valfritt) Rensa innehållet i version för att ta bort onödiga versioner och snabba upp migreringsprocessen. Installera paketet om du vill rensa version på version 4.1 (stöds INTE på 4.0) `com.adobe.guides.version-purge-1.0.11.zip`och gå till användargränssnittet med denna URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Verktyget tar inte bort versioner som används i baslinjer eller granskningar och har inga etiketter.
1. Installera paketet före migrering (`ccom.adobe.guides.pre-uuid-migration-1.1.2 .zip`).

   >[!NOTE]
   >
   >* Du måste ha administratörsbehörighet för att kunna utföra migreringen.
   >* Du bör åtgärda filerna med fel innan du fortsätter med migreringen.

1. Välj **Kompatibilitetsbedömning**  från den vänstra panelen och bläddra i en mappsökväg.
1. Kontrollera kompatibiliteten för att lista följande information:
   * Totalt antal filer
   * Totalt antal versioner
   * Beräknad tid för migrering
   * Antal filer med fel



![fliken för kompatibilitetsbedömning i migrering](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Välj **Konfigurera valideringar** från den vänstra panelen. Sedan **Markera karta** och **Välj förinställning** av kartan för att konfigurera dem. Den aktuella utdatavalideringslistan visar de utdatafiler som finns före migreringen och kan valideras mot de utdatafiler som genereras efter migreringen senare.

![Konfigurera fliken Valideringar i migrering](assets/migration-configure-validation.png){width="800" align="left"}




## Migrering

### Steg 1: Uppdatera konfigurationen

1. Se till att det lediga utrymmet är minst 10 gånger så stort som det utrymme som AEM (crx-quickstart directory) tar under migreringen. När du är klar med migreringen kan du återvinna det mesta av diskutrymmet genom att köra en komprimering (se [Revision Cleanup](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Aktivera *Aktivera startprogram för arbetsflöde efter bearbetning* in `com.adobe.fmdita.config.ConfigManager` och *Aktivera efterbearbetning av version* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installera UUID-versionen av den version som stöds över den version som inte är UUID. Om du till exempel använder en 4.0-version som inte är UUID eller en 4.1-version som inte är UID måste du installera UUID version 4.1.

1. Installera det nya paketet för uuid-migrering (`com.adobe.guides.uuid-upgrade-1.1.13`).

1. Inaktivera följande arbetsflöden och andra arbetsflöden som körs på `/content/dam` använda starter i `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Arbetsflöde för DAM-uppdatering
   * Arbetsflöde för DAM-metadataåterställning

1. Inaktivera *Aktivera startprogram för arbetsflöde efter bearbetning* in `com.adobe.fmdita.config.ConfigManager` och inaktivera *Aktivera efterbearbetning av version* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Inaktivera egenskapen Aktivera validering (`validation.enabled`) in Day CQ Tagging Service.

1. Se till att `uuid.regex` egenskapsmappen är korrekt inställd i `com.adobe.fmdita.config.ConfigManager`. Om det är tomt anger du standardvärdet - `^GUID-(?<id>.*)`.
1. Lägg till en separat loggare för `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` Webbläsarsvaret finns också på `/content/uuid-upgrade/logs`.

### Steg 2: Kör migreringen och validera

#### Installera migreringspaketet

![Fliken Systemuppgradering vid migrering](assets/migration-system-upgrade.png){width="800" align="left"}

* Välj **Systemuppgradering** från den vänstra panelen för att köra migreringen. Börja med en mapp med mindre data innan du kör den `/content/dam`.

* Välj **Ladda ned rapport** när migreringen körs för att kontrollera om alla filer i mappen är korrekt uppgraderade och om alla funktioner bara fungerar för den mappen.


>[!NOTE]
>
> Innehållsmigreringen kan köras på mappnivå eller på hela `/content/dam` eller i samma mapp (kör migreringen igen).

Dessutom är det viktigt att se till att innehållsmigreringen också görs för alla medieresurser, till exempel bilder och grafik som du har använt i DITA-innehållet.

#### Migrering av baslinje och granskning

Välj **Originalplan/Granska uppgradering** från den vänstra panelen för att migrera baslinjerna och granska på mappnivå.

![Baslinje och granskning i migrering](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Steg 3: Återställ konfigurationen

När servern har migrerats kan du aktivera efterbearbetning, taggning och följande arbetsflöden (inklusive alla andra arbetsflöden som inaktiveras från början under migreringen) för att fortsätta arbeta på servern.

* Arbetsflöde för DAM-uppdatering
* Arbetsflöde för DAM-metadata

>[!NOTE]
>
>Om vissa filer inte bearbetas eller är skadade före migreringen kommer de att skadas före migreringen och förbli skadade även efter migreringen.

## Migreringsvalidering

När migreringen är klar väljer du **Validera systemuppgradering** från den vänstra panelen och validera utdatafilerna före och efter migreringen för att säkerställa att migreringen lyckas.

![Validera fliken för systemuppgradering vid migrering](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. När migreringen är klar kan större delen av diskutrymmet återvinnas genom att köra en komprimering (se `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

