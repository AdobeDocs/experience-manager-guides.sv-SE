---
title: Konvertera icke-UID-innehåll med versioner till UUID-innehåll
description: Lär dig hur du migrerar icke-UID-innehåll med versioner till UUID-innehåll.
source-git-commit: 0d985688af601ca51822b116ea4baafce19f0658
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# Migrera versionshanterat innehåll

Utför de här stegen för att migrera ditt icke-UID-versionshanterade innehåll till UUID-innehåll.

>[!NOTE]
>
>Följ [uppgraderingsinstruktioner](./upgrade-xml-documentation.md) specifikt för den licensierade versionen av din produkt.

## Kompatibilitetsmatris

| Aktuell version av stödlinjer för Experience Manager (ej UUID) | Version som krävs för att migrera till UUID | Uppgraderingssökväg som stöds |
|---|---|---|
| 3.8.5, 4.0.x eller 4.1.x | 4.1 ej UUID | Installera 4.1 (UUID) och kör migreringen |
| 4.2, 4.2.x eller 4.3 | 4.3.0 ej UUID | Installera 4.3.1 (UUID) och kör migreringen |
| 4.3.1 | NA | NA |

## Paketinstallation

Hämta de paket som behövs från Adobe Software Distribution Portal, baserat på din version:
<details>
<summary>  Paket för uppgraderingssökväg till version 4.1</summary>

1. **Före migrering**: [com.adobe.guides.pre-uid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migrering**: [com.adobe.guides.uid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Paket för uppgraderingssökväg till version 4.3.1</summary>

1. **Före migrering**: [com.adobe.guides.pre-uid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migrering**: [com.adobe.guides.uid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Före migrering

Utför följande kontroller för den version som inte är UUID (4.1 icke-UID eller 4.3.0 icke-UUID):

1. Installera förmigreringspaketet enligt din version.

   >[!NOTE]
   >
   >* Du måste ha administratörsbehörighet för att kunna utföra migreringen.
   >* Du bör åtgärda filerna med fel innan du fortsätter med migreringen.
1. (Valfritt) Rensa innehållet i version för att ta bort onödiga versioner och snabba upp migreringsprocessen. Markera alternativet om du vill rensa versionen **Rensa version** från migreringsskärmen och gå till användargränssnittet med URL:en `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Verktyget tar inte bort versioner som används i baslinjer eller granskningar och har inga etiketter.
1. Starta `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
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

1. Se till att det lediga utrymmet är minst tio gånger så stort som det utrymme som AEM (crx-quickstart directory) tar under migreringen. När du är klar med migreringen kan du återvinna det mesta av diskutrymmet genom att köra en komprimering (se [Revision Cleanup](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Aktivera *Aktivera startprogram för arbetsflöde efter bearbetning* in `com.adobe.fmdita.config.ConfigManager` och *Aktivera efterbearbetning av version* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installera UUID-versionen av den version som stöds över den version som inte är UUID. Om du till exempel använder 4.1-version som inte är UUID måste du installera UUID version 4.1 och köra migreringen.

1. Installera det nya paketet för uuid-migrering.

1. Inaktivera följande arbetsflöden och andra arbetsflöden som körs på `/content/dam` använda starter i `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Arbetsflöde för DAM-uppdatering
   * Arbetsflöde för DAM-metadataåterställning

1. Inaktivera *Aktivera startprogram för arbetsflöde efter bearbetning* in `com.adobe.fmdita.config.ConfigManager` och inaktivera *Aktivera efterbearbetning av version* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Inaktivera egenskapen Aktivera validering (`validation.enabled`) in Day CQ Tagging Service.

1. Se till att `uuid.regex` egenskapsmappen är korrekt inställd i `com.adobe.fmdita.config.ConfigManager`. Om det är tomt anger du standardvärdet - `^GUID-(?<id>.*)`.
1. Lägg till en separat loggare för `com.adobe.fmdita.uuid` Webbläsarsvaret finns också på `/content/uuid-upgrade/logs`.

### Steg 2: Kör migreringen och validera

#### Installera migreringspaketet

1. Starta `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Fliken Systemuppgradering vid migrering](assets/migration-system-upgrade.png){width="800" align="left"}

1. Välj **Systemuppgradering** från den vänstra panelen för att köra migreringen. Börja med en mapp med mindre data innan du kör den `/content/dam`.

1. Välj **Ladda ned rapport** när migreringen körs för att kontrollera om alla filer i mappen är korrekt uppgraderade och om alla funktioner bara fungerar för den mappen.


>[!NOTE]
>
> Innehållsmigreringen kan köras på mappnivå, den fullständiga `/content/dam`eller samma mapp (kör migreringen igen).

Det är också viktigt att se till att innehållsmigreringen görs för alla medieresurser, till exempel bilder och grafik som du har använt i DITA-innehållet.

#### Migrering av baslinje och granskning

Välj **Originalplan/Granska uppgradering** från den vänstra panelen för att migrera baslinjerna och granska på mappnivå.

![Baslinje och granskning i migrering](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Steg 3: Återställ konfigurationen

När servern har migrerats kan du aktivera efterbearbetning, taggning och följande arbetsflöden (inklusive alla andra arbetsflöden som inaktiverades från början under migreringen) för att fortsätta arbeta på servern.

* Arbetsflöde för DAM-uppdatering
* Arbetsflöde för DAM-metadata

>[!NOTE]
>
>Om vissa filer inte bearbetas eller skadas före migreringen kommer de att skadas före migreringen och förbli skadade även efter migreringen.

## Migreringsvalidering

1. När migreringen är klar väljer du **Validera systemuppgradering** från den vänstra panelen och validera utdatafilerna före och efter migreringen för att säkerställa att migreringen lyckas.

   ![Validera fliken för systemuppgradering vid migrering](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. När valideringen är klar kan större delen av diskutrymmet frigöras genom att köra en komprimering (se `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

