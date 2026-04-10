---
title: Uppgradera Adobe Experience Manager Guides på tidigare versioner
description: Så här uppgraderar du Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3159'
ht-degree: 0%

---

# Uppgradera Adobe Experience Manager Guides On Premise (version 4.4.0 och tidigare)

Den här artikeln innehåller anvisningar om hur du uppgraderar **Adobe Experience Manager Guides** versioner **före 4.6.0** (till och med **4.4.0**).

Om du har en version **som är tidigare än 3.8.5** kan du läsa avsnittet **Uppgradera Experience Manager Guides** i den produktspecifika installationsguiden som finns i [Adobe Experience Manager Guides Help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Uppgraderingsinstruktioner för nyare versioner finns i [Uppgradera Adobe Experience Manager Guides för version 4.6.0 och senare](./upgrade-aemg-latest-version.md).

## Innan du börjar

>[!NOTE]
>
> Du måste uppgradera den licensierade versionen av produkten och installera AEM Service Pack innan du uppgraderar Experience Manager Guides.

>[!IMPORTANT]
>
> Innan du börjar uppgradera bör du göra en **fullständig systemsäkerhetskopiering** för att undvika dataförluster.

## Uppgraderingssökvägar som omfattas av den här artikeln

Denna artikel innehåller procedurer för

- [Uppgradera till version 4.4.0](#upgrade-to-version-440)
- [Uppgradera till version 4.3.1.5](#upgrade-to-version-4315)
- [Uppgradera till version 4.3.1](#upgrade-to-version-431)
- [Uppgradera till version 4.3.0](#upgrade-to-version-430)
- [Uppgradera till version 4.2.1](#upgrade-to-version-421)
- [Uppgradera till version 4.2](#upgrade-to-version-42)
- [Uppgradera från 3.8.5 till version 4.0](#upgrade-from-version-385-to-version-40)


## Globala förutsättningar (gäller för alla uppgraderingar om inte annat anges i proceduren)

Utför följande uppgifter innan du kör uppgraderingsprocessen:

1. Importera granskningskommentarer i ämnen som är öppna för granskning.
2. Stäng alla aktiva granskningar.
3. Stäng alla översättningsåtgärder.
4. Avinstallera eventuella Experience Manager Guides-snabbkorrigeringar som installerats ovanpå den tidigare versionen (större version eller korrigeringsversion).

Vissa uppgraderingar kräver också att loggnivån ställs in på `INFO` för en uppgraderingsklass för översättning och loggning till en separat fil. Dessa krav anges i de relevanta uppgraderingsprocedurerna.

## Uppgradera från version 3.8.5 till version 4.0

>[!NOTE]
>
> Den här uppgraderingsprocessen gäller **endast** från **3.8.5** till **4.0**. För uppgraderingar från **3.4 eller senare** till **3.8.5**, se den produktspecifika installationsguiden som finns i [Adobe Experience Manager Guides Help PDF Archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Om du använder Experience Manager Guides version **3.8.5** kan du uppgradera till version **4.0** utan att avinstallera den tidigare versionen.

### Innan du installerar version 4.0

1. Kontrollera att Experience Manager Guides är i version **3.8.5**.
2. Hämta uppgraderingsskriptpaketet: sök efter **&quot;XML Documentation solution 4.0 Upgrade Package&quot;** på Adobe Software Distribution Portal (hämtar ett `.zip`).
3. Överför paketet till AEM via **Package Manager** och installera det.
4. När uppgraderingspaketet har installerats kör du skripten i den ordning som beskrivs nedan.

**Kontrollera API:t för uppgraderingskompatibilitet**

Detta API är utformat för att utvärdera den aktuella systemstatusen och rapportera om uppgraderingen är möjlig eller inte. Om du vill köra det här skriptet utlöser du slutpunkten nedan:

| Slutpunkt | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Typ av begäran | **GET** <br> **Obs!** Du kan använda en webbläsare där du är inloggad som administratör på AEM-instansen. |
| Förväntat svar | -   Om alla nödvändiga noder kan flyttas får du en kontroll som du godkänt. <br>-   Om det finns en nod på målplatsen får du ett relevant fel. Rensa databasen \(delete node /var/dxml\) och installera om uppgraderingspaketet och utlösa sedan den här slutpunkten igen. <br>**Obs!** Detta är inte ett vanligt fel eftersom målplatsen inte används tidigare av 3.x Experience Manager Guides. <br> -   Om det här manuset inte lyckas ska du inte fortsätta och rapportera till ditt kundframgångsteam. |

**API för systemdatamigrering**

Detta API är utformat för att migrera systemdata enligt avsnittet **Migreringsmappning**.

1. Kör inte det här skriptet om API:t för kontroll av kompatibilitet misslyckas \(fortsätt inte\).
1. När API:t för kontroll av uppgraderingskompatibilitet returneras kan du köra uppgraderingsskriptet.

| Slutpunkt | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Typ av begäran | **POST** <br>**Obs!** Det här skriptet är en POST-begäran och ska därför köras via agenter som Postman. |
| Förväntat svar | -   När migreringen är klar kan du installera XML Documentation-lösningen version 4.0.<br>-   Om fel uppstår återställer du till den senaste kontrollpunkten och delar felloggarna med API-utdata till kundens framgångsgrupp. |


**Migreringsmappning**

Detta API migrerar alla data under källplatsen till målplatsen.

| Source | Target |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

### Installera version 4.0

1. Installera endast version 4.0 om uppgraderingsstegen lyckades.
1. Hämta versionspaket 4.0 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

   - Om du använder UUID-versionen av programmet söker du efter&quot;4.0 UID Release for XML Documentation solution for AEM 6.5&quot;.
   - Om du använder en icke-UID-version av programmet söker du efter&quot;4.0 Non-UUID Release for XML Documentation solution for AEM 6.5&quot;.
Överför paketet till den befintliga AEM-serverinstansen med CRX Package Manager och installera det.

     >[!NOTE]
     >
     > Vänta tills alla systemkomponenter har startats.

1. Rensa webbläsarcachen när paketet har installerats.
1. Om en dispatcher har konfigurerats på en AEM Author-instans utför du följande steg:
   - Kontrollera att följande hanteras i dispatcherregler:
   - URL-mönstret /home/users/\*/preferences är vitlistat.
   - URL-mönstret /libs/cq/security/userinfo.json är inte cachelagrat.
1. Rensa dispatchercachen \(för att rensa alla `clientlibs` cachelagrade\).

## Uppgradera till version 4.2

Du kan uppgradera till version **4.2** direkt om du använder version **4.0**, **4.1** eller **4.1.x**.

### Innan du installerar version 4.2

Innan du startar uppgraderingsprocessen för Experience Manager Guides 4.2 bör du kontrollera att du har:

1. Uppgraderat till Experience Manager Guides **4.0**, **4.1** eller **4.1.x**.
2. Alla översättningsuppgifter stängdes.
3. Ange loggnivån till `INFO` för `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och logga till en ny loggfil (till exempel `logs/translation_upgrade.log`).

   >[!NOTE]
   > 
   > Du bör stänga alla aktiva granskningar. Om granskningarna inte stängs när du uppgraderar till 4.2 kan äldre pågående granskningsuppgifter fortsätta att öppna äldre granskningssidor. Nya granskningsuppgifter som skapas efter uppgraderingen visar de senaste funktionsuppdateringarna.

### Installera version 4.2

1. Hämta paketet **4.2** från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installera 4.2-paketet.
3. Efter installationen väntar du på följande meddelande i loggarna:

   `Completed the post deployment setup script`

   Ovanstående meddelande anger att alla installationssteg har slutförts.

   Om du råkar ut för något av följande fel ska du rapportera dem till Customer Success:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`

4. (Valfritt) Plugin-programmet för uppgradering av syreanslutning släppt med version 4.2.
5. Rensa webbläsarcachen när paketet har installerats.
6. Fortsätt uppgradera anpassningarna enligt anvisningarna i nästa avsnitt.

### Efter installation av version 4.2

>[!IMPORTANT]
>
> Hi-tech-mallar visas inte på uppgraderad server. Om du vill inkludera hi-tech-mallen på servern kan du kopiera den: Source: `/libs/fmdita/pdf/Hi-Tech` Mål: `/content/dam/dita-templates/pdf`.

Fortsätt sedan med de delade efteruppgraderingsuppgifterna i [Vanliga efteruppgraderingsuppgifter (alla versioner)](#common-postupgrade-tasks-all-versions).

## Uppgradera till version 4.2.1

>[!TIP]
>
> Vi rekommenderar att du installerar **hotfix4.2.1.3** ovanpå version **4.2.1**.

Du kan uppgradera till version **4.2.1** direkt om du använder **4.1**, **4.1.x** eller **4.2**.

>[!NOTE]
>
> Efterbearbetning och indexering kan ta några timmar. Starta uppgraderingen under tider med låg belastning.

### Innan du installerar version 4.2.1

1. Uppgradera till Experience Manager Guides **4.1**, **4.1.x** eller **4.2**.
2. Stäng alla översättningsåtgärder.
3. Ange loggnivån till `INFO` för `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och logga till en ny fil (till exempel `logs/translation_upgrade.log`).

>[!NOTE]
>
> Du bör stänga alla aktiva granskningar (samma beteende som 4.2).

### Installera version 4.2.1

1. Hämta paketet **4.2.1** från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installera 4.2.1-paketet.
3. Du kan också aktivera uppgraderingsjobbet för översättningskartan. Mer information finns i [Aktivera utlösare för skript via en server](#enable-trigger-of-script-via-a-servlet).

4. Efter installationen väntar du på: `Completed the post deployment setup script` i loggar.

   Rapportera felen till Kundens framgång:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Valfritt) Plugin-programmet för uppgradering av syreanslutning har släppts med version **4.2**
6. Rensa webbläsarcachen.
7. Fortsätt med [Vanliga efteruppgraderingsuppgifter (alla versioner)](#common-postupgrade-tasks-all-versions).

### Efter installation av version 4.2.1

>[!IMPORTANT]
>
> Hi-tech-mallar visas inte på uppgraderad server. Om du vill inkludera hi-tech-mallen på servern kan du kopiera den: Source: `/libs/fmdita/pdf/Hi-Tech` Mål: `/content/dam/dita-templates/pdf`.

Fortsätt med [Vanliga efteruppgraderingsuppgifter (alla versioner)](#common-postupgrade-tasks-all-versions) och (om det behövs) [Indexera befintligt innehåll för kartsökning och ersättning](#index-existing-content-for-map-find-and-replace).


## Uppgradera till version 4.3.0

Uppgradering till version 4.3.0 beror på vilken version av Experience Manager Guides du har. Om du använder version 4.2 eller 4.2.x kan du uppgradera direkt till version 4.3.0.

>[!NOTE]
>
>Efterbearbetningen och indexeringen kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

### Innan du installerar version 4.3.0

Innan du startar uppgraderingsprocessen för Experience Manager Guides 4.3.0 bör du kontrollera att du har:

1. Uppgraderat till Experience Manager Guides version 4.2 eller 4.2.x och slutfört respektive installationssteg.
1. Alla översättningsuppgifter stängdes.

### Installera version 4.3.0

1. Hämta versionspaket 4.3.0 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installera paket för version 4.3.0.
1. Rensa webbläsarcachen när paketet har installerats.
1. Uppgradera filen `ui_config.json` från fliken **XML-redigerarkonfiguration** i mappprofilen.

### Efter installation av version 4.3.0

Fortsätt med:

- [Vanliga efteruppgraderingsuppgifter (alla versioner)](#common-postupgrade-tasks-all-versions)
- Om tillämpligt: [Publicera befintligt innehåll för rapport om bruten länk](#post-process-existing-content-for-broken-link-report)

## Uppgradera till version 4.3.1

Uppgradering till version 4.3.1 beror på vilken version av Experience Manager Guides som är aktuell. Om du använder version 4.3.0, 4.2 eller 4.2.1 kan du uppgradera direkt till version 4.3.1.

>[!NOTE]
>
>Efterbearbetningen och indexeringen kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

### Innan du installerar version 4.3.1

Innan du startar uppgraderingsprocessen för Experience Manager Guides 4.3.1 bör du kontrollera att du har:

1. Uppgraderat till Experience Manager Guides version 4.3.0, 4.2 eller 4.2.1 och slutfört respektive installationssteg.
1. (Valfritt) Avslutade alla översättningsuppgifter.
1. Loggnivån har ändrats till **INFO** för klassen `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och loggarna läggs till i en ny loggfil, till exempel `logs/translation_upgrade.log`.

### Installera version 4.3.1

1. Hämta versionspaketet 4.3.1 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installera paket för version 4.3.1.
1. Du kan också aktivera uppgraderingsjobbet för översättningskartan. Mer information finns i [Aktivera utlösare för skript via en server](#enable-trigger-of-script-via-a-servlet).
1. Efter installationen väntar du på: `Completed the post deployment setup script` i loggar.
Rapportera felen till Kundens framgång:\
   `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property`
1. (Valfritt) Plugin-programmet för uppgradering av syreanslutning släpptes med version **4.2**.
1. Rensa webbläsarcachen.

### Efter installation av version 4.3.1

Fortsätt med:

- [Vanliga efteruppgraderingsuppgifter (alla versioner)](#common-postupgrade-tasks-all-versions)
- Om tillämpligt: [Indexera befintligt innehåll för kartans sök- och ersätt](#index-existing-content-for-map-find-and-replace)
- Om tillämpligt: [Publicera befintligt innehåll för rapport om bruten länk](#post-process-existing-content-for-broken-link-report)


## Uppgradera till version 4.3.1.5

Du kan uppgradera till **4.3.1.5** direkt om du använder version **4.3.1**.

### Installera version 4.3.1.5

1. Hämta paketet **4.3.1.5** från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installera paketet 4.3.1.5.
3. Vänta tills installationsprocessen har slutförts.
4. Fortsätt uppgradera anpassningarna enligt anvisningarna i nästa avsnitt.

## Efter installation av version 4.3.1.5

>[!NOTE]
>
>Om du vill använda paketet org.apache.velocity utför du följande steg innan du överför paketet:
> 1. Gå till `<server>:<port>/system/console/bundles`
> 1. Sök efter org.apache.speed.
> 1. Avinstallera det sökta paketet.
> 1. Installera det hastighetspaket som krävs.

1. När uppgraderingen är klar kontrollerar du att alla anpassningar/övertäckningar har validerats och uppdaterats så att de matchar den nya programkoden. Nedan följer några exempel:
   - Alla komponenter som överlappas från `/libs/fmdita` eller ` /libs` ska jämföras med den nya produktkoden och uppdateringar ska göras i överlagrade filer under `/apps` .
   - Alla kategorier av klientlib som används från produkten bör granskas för ändringar. Alla åsidosatta konfigurationer \(exempel nedan\) bör jämföras med de senaste för att få de senaste funktionerna:
   - `elementmapping.xml`
   - `ui\_config.json\` (kan ha angetts i mappprofiler\)
   - ändrade `com.adobe.fmdita.config.ConfigManager`


## Uppgradera till version 4.4.0

Du kan uppgradera till **4.4.0** direkt om du använder: **4.3.1**, **4.3.0**, **4.2** eller **4.2.1 (programfix 4.2.1.3)**.

>[!NOTE]
>
>Efterbearbetningen och indexeringen kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

### Innan du installerar version 4.4.0

Innan du startar uppgraderingsprocessen för Experience Manager Guides 4.4.0 bör du kontrollera att du har:

1. Uppgraderat till Experience Manager Guides version 4.3.1, 4.3.0 eller 4.2.1 (programfix 4.2.1.3) och slutförde respektive installationssteg.
1. (Valfritt) Avslutade alla översättningsuppgifter.
1. Loggnivån har ändrats till **INFO** för klassen `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och loggarna läggs till i en ny loggfil, till exempel `logs/translation_upgrade.log`.

### Installera version 4.4.0

1. Hämta versionspaketet 4.4.0 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installera 4.4.0-paketet.
3. Du kan också aktivera uppgraderingsjobbet för översättningskartan. Mer information finns i [Aktivera utlösare för skript via en server](#enable-trigger-of-script-via-a-servlet).
4. När du har slutfört paketinstallationen väntar du på följande meddelande i loggarna:

   `Completed the post deployment setup script`

   Ovanstående meddelande anger att alla installationssteg är slutförda.

   Om du råkar ut för något av följande felkorrigeringar ska du rapportera dem till ditt kundteam:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Valfritt) Plugin-programmet för uppgradering av syreanslutning släpptes med version **4.4.0**.
6. Rensa webbläsarcachen.
7. Fortsätt med:

   - [Vanliga uppgifter efter uppgradering (alla versioner)](#common-ppostupgrade-tasks-all-versions)
   - [Indexera befintligt innehåll för kartans sök och ersätt](#index-existing-content-for-map-find-and-replace) (endast om tillämpligt)
   - [Efterbearbeta befintligt innehåll för rapport om brutna länkar](#post-process-existing-content-for-broken-link-report) (endast om tillämpligt)
   - [Uppgradering av översättningskarta (serverutlösare)](#translation-map-upgrade-servlet-trigger) (endast om tillämpligt)


## Vanliga uppgifter efter uppgradering (alla versioner)

När du har installerat Experience Manager Guides kan du behöva sammanfoga konfigurationer som gäller från den nyinstallerade versionen till din installation.

>[!NOTE]
>
> Arbetsflödesmodellen **DAM Update Asset** kan anpassas. Om du har anpassningar kan du synkronisera dem med Experience Manager Guides-ändringar i arbetskopian av modellen.

### Validera arbetsflödet för DAM-uppdatering (ändringar efter bearbetning)

1. Öppna användargränssnittet för AEM Workflow Models (exemplet visas i källan):\
   `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html`
2. Välj **DAM-uppdateringsarbetsflöde**.
3. Välj **Redigera**.
4. Om komponenten **DXML Post Process Initiator** finns kontrollerar du att anpassningarna synkroniseras.
5. Om komponenten inte finns infogar du den:
   1. Klicka på **Infoga komponent** (ansvarar för efterbearbetning av stödlinjer som det sista steget).
   2. Konfigurera **processsteget**:
      **fliken Allmänt**
- Titel: `DXML Post Process Initiator`
- Beskrivning: `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset`
      **Fliken Process**
- Process: välj `DXML Post Process Initiator`
- Välj `Handler Advance`
- Välj `Done`
   3. Klicka på **Synkronisera** överst till höger när du har slutfört ändringarna. Du får ett meddelande om att åtgärden lyckades.

>[!NOTE]
>
> Uppdatera och verifiera att anpassade ändringar och Experience Manager Guides efterbearbetningssteg finns i den slutliga arbetsflödesmodellen.

### Validera startkonfigurationer

1. Gå till AEM Workflow-gränssnittet och öppna **Startprogram**.

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Sök efter och ändra \(om det behövs\) till följande två startprogram \(som ska vara aktiva\) som motsvarar **DAM Update Asset workflow**:

1. Startprogrammet för *noden har skapats* för arbetsflödet **DAM Update Asset** - för villkoret `"jcr:content/jcr:mimeType!=video"` ska värdet Globbing vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` ska ha `"event-user-data:changedByWorkflowProcess"`.
   - Startprogram för *Nod ändrad* för **DAM Update Asset workflow -** för villkoret `jcr:content/jcr:mimeType!=video`. Värdet Globbing ska vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` ska ha `"event-user-data:changedByWorkflowProcess"`.

### Validera övertäckningar och anpassningar

När uppgraderingen är klar:

1. När uppgraderingen är klar kontrollerar du att alla anpassningar/övertäckningar har validerats och uppdaterats så att de matchar den nya programkoden. Nedan följer några exempel:
   - Alla komponenter som överlappas av/libs/fmditor/libsska jämföras med den nya produktkoden och uppdateringar ska göras i överlagrade filer under/i appar.
   - Alla kategorier av klientlib som används från produkten bör granskas för ändringar. Alla åsidosatta konfigurationer \(exempel nedan\) bör jämföras med de senaste för att få de senaste funktionerna:
   - elementmapping.xml
   - ui\_config.json\(kan ha angetts i mappprofiler\)
   - ändrade `com.adobe.fmdita.config.ConfigManager`

1. Om du har lagt till anpassningar i damAssetLucene kan du behöva använda dem igen. När du har gjort ändringarna anger du reindex som true. Detta indexerar om alla befintliga noder med anpassningarna. När du är klar anges omindexeringsflaggan till false igen. Detta kan ta några timmar beroende på antalet resurser i systemet.

## Indexera befintligt innehåll för att söka och ersätta kartor

I det här avsnittet konsolideras den upprepade **indexeringsproceduren** som används för att aktivera de nya **mappningsnivåfunktionerna för sök och ersätt**.

**När du kan hoppa över indexering**

Källan innehåller&quot;hoppa över&quot;-anteckningar beroende på din uppgraderingssökväg (t.ex.&quot;Du behöver inte utföra dessa steg om du uppgraderar från 4.3.0 eller 4.3.1&quot; och liknande anteckningar). Följ överhoppningsanvisningarna som finns i uppgraderingsavsnittet.

Utför följande steg för att indexera det befintliga innehållet och använd den nya sök- och ersätt-texten på mappningsnivå:

1. Kör en POST-begäran (med autentisering):

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Valfria parametrar som stöds i källan:

- Indexera specifika mappningssökvägar (som standard indexeras alla mappningar):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
  ```

- Indexera DITA-mappningar under en rotmapp (och dess undermappar):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
  ```

  >[!NOTE]
  >
  > Om både `paths` och `root` skickas beaktas bara `paths`.

1. API:t returnerar `jobId`. Skicka en GET-förfrågan om du vill kontrollera status:

   ```http
   GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
   ```

   Förväntat slutförandebeteende:

   - När allt är klart svarar GET med framgång och anger om några kartor misslyckades.
   - Indexerade mappningar i serverloggar har bekräftats.

### Kontrollera att damAssetLucene-indexeringen är slutförd (där det är tillämpligt)

Källan noterar att indexering av damAssetLucene kan ta timmar beroende på datastorleken, och du kan bekräfta slutförandet när `reindex` är `false` under:

`http://<server:port>/oak:index/damAssetLucene`

Om du har lagt till anpassningar i `damAssetLucene` kan du behöva tillämpa dem igen när indexeringen har slutförts.

### Tillfällig lösning för&quot;fråga som har lästs eller gått igenom mer än 100000 noder&quot; (om jobbet misslyckas)

Om indexeringsjobbet misslyckas och felet visar:

&quot;Frågan läste eller gick igenom mer än 100000 noder. Bearbetningen avbröts för att undvika att andra uppgifter påverkas.&quot;

Prova den här lösningen från källan:

1. Lägg till den booleska egenskapen `damAssetLucene` i `indexNodeName=true` i `/oak:index/damAssetLucene/indexRules/dam:Asset`-ekindexet.
2. Lägg till en ny nod med namnet `excerpt` under `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` och ange egenskaper som visas i källan:
   - `name=rep:excerpt`
   - `propertyIndex=true`
   - `notNullCheckEnabled=true`
3. Indexera om `damAssetLucene` genom att ange `reindex=true` och vänta tills det blir `false` igen (kan ta timmar).
4. Kör indexeringsskriptet igen (upprepa POST och jobbspårning).

## Efterbearbeta befintligt innehåll för rapport om bruten länk

I det här avsnittet konsolideras den upprepade **efterbearbetningsproceduren** som används för att aktivera den **brutna länkrapporten**.

**När du kan hoppa över efterbearbetning**

Källan innehåller&quot;hoppa över&quot;-anteckningar beroende på din uppgraderingssökväg (t.ex.&quot;Du behöver inte utföra dessa steg om du uppgraderar från 4.3.0&quot; eller&quot;från 4.3.0 eller 4.3.1&quot;). Följ överhoppningsanvisningarna som finns i uppgraderingsavsnittet.

Följ de här stegen för att aktivera rapporten för bruten länk:

1. (Valfritt) Öka Oak queryLimitReads för stora databaser

   Om det finns fler än **100 000 DITA-filer** uppdaterar du `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` till ett värde som är större än antalet resurser (exempel: `200000`), omdistribuerar och fortsätter.

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Värde: 200000 <br> standardvärde: 100000 |

1. Kör följande API:er för efterbearbetning av alla filer:

   | Slutpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Typ av begäran | **POST** Det här skriptet är en POST-begäran och ska därför köras via agenter som Postman. |
   | Förväntat svar | API:t returnerar ett jobId. Om du vill kontrollera jobbets status kan du skicka en GET-förfrågan med jobb-ID till samma slutpunkt.<br> Exempel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Slutpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Typ av begäran | **GET** |
   | Param | jobId: Skicka det jobId som togs emot från föregående post-begäran. |
   | Förväntat svar | - När jobbet är klart svarar GET-begäran med framgång. <br> - Om det uppstår fel kan du dela felloggarna tillsammans med API-utdata med kundens framgångsgrupp.  <br>Exempel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Återgå till standardvärdet eller det tidigare befintliga värdet `queryLimitReads` om du har ändrat det i steg 1.

## Aktivera utlösare för skript via en serverenhet

Flera versioner innehåller ett valfritt steg som utlöser ett uppgraderingsjobb för översättningskarta via en server. I det här avsnittet konsolideras den upprepade proceduren och innehåller alla detaljer som anges i källan.


>[!NOTE]
>
> Du behöver inte utföra dessa steg om du uppgraderar från 4.3.0 eller 4.3.1.

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

I ovanstående svar-JSON innehåller nyckeln `lockNodePath` sökvägen till noden som skapades i databasen som pekar på jobbet som skickats. Den tas automatiskt bort när jobbet är klart, tills dess kan du referera till den här noden för aktuell status för jobbet.

Sök efter `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` och `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` innan du fortsätter till nästa steg.

>[!NOTE]
>
> Du bör kontrollera om noden fortfarande finns och jobbens status.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`


### Steg för att hantera konflikten med &quot;fmdita rewriter&quot;

Experience Manager Guides innehåller en anpassad modul för Sling-omskrivning (`fmditarewriter`) för hantering av länkar som genererats för korsmappslänkning.

Om du har en annan anpassad Sling-rewriter i din kodbas:

- Använd ett `order`-värde **som är större än 50** eftersom stödlinjerna använder `order=50`.
- Under den här uppgraderingen ändras värdet `order` från `1000` till `50`, så du måste sammanfoga din befintliga anpassade omskrivare (om sådan finns) med `fmditarewriter`.

