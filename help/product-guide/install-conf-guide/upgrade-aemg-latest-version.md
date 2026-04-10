---
title: Uppgradera Adobe Experience Manager Guides
description: Så här uppgraderar du Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Uppgradera Adobe Experience Manager Guides för version 4.6.0 och senare

Den här artikeln innehåller anvisningar om hur du uppgraderar dina Experience Manager Guides-versioner för version 4.6.0 och senare.

>[!NOTE]
>
> Följ uppgraderingsinstruktionerna för den licensierade versionen av din produkt.

Du kan uppgradera din nuvarande version av Experience Manager Guides till version 5.1.0 Service Pack 3:

- Om du använder version 5.1.0 eller 5.1.x kan du uppgradera direkt till version 5.1.0 Service Pack 3.
- Om du använder version 4.6.0, 4.6.x, 5.0.0 eller 5.0.x måste du uppgradera till version 5.1.0.
- Om du har en tidigare version än 4.6.0 kan du läsa [Uppgradera Adobe Experience Manager Guides för version 4.4.0 och tidigare](./upgrade-aemg-prev-versions.md) för detaljerade uppgraderingsinstruktioner.

>[!NOTE]
>
> Du måste installera AEM Service Pack innan du uppgraderar Experience Manager Guides-versionen.

Mer information finns i följande procedurer:

- [Uppgradera till version 5.1.0](#upgrade-to-version-510)
- [Uppgradera till version 5.0.0](#upgrade-to-version-500)
- [Uppgradera till version 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Innan du börjar uppgradera bör du göra en fullständig säkerhetskopiering av systemet för att undvika dataförluster.


## Uppgradera till version 5.1.0


>[!IMPORTANT]
>
> Om du för närvarande använder AEM 6.5 och tänker gå över till AEM 6.5 LTS måste du först slutföra uppgraderingen av AEM innan du fortsätter med uppgraderingen av Experience Manager Guides 5.1.0. Mer information finns i [Uppgradera till Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/sv/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Förutsättningar**

>[!NOTE]
>
>Om du uppgraderar till 5.1.0 Service Pack 3 måste du ha version 5.1.0 eller 5.1.x av Experience Manager Guides. Uppgraderingsprocessen för version 5.1.0 Service Pack 3 följer samma steg som för version 5.1.0.

Innan du startar uppgraderingsprocessen för Experience Manager Guides 5.1.0 bör du kontrollera att du har:

1. Uppgraderat till Experience Manager Guides version 4.6.3, 4.6.4, 5.0.0 eller 5.0.0 Service Pack 1.
1. (Valfritt) Avslutade alla översättningsuppgifter.
1. Loggnivån har ändrats till **INFO** för klassen `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och loggarna läggs till i en ny loggfil, till exempel `logs/translation_upgrade.log`.

>[!NOTE]
>
> Efterbearbetningen och indexeringen kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

**Installera version 5.1.0**

Ladda ned versionspaketet 5.1.0 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) och följ instruktionerna i [Uppgraderingsarbetsflödet för installation och efterinstallation](#installation-and-post-installation-upgrade-workflow) för att slutföra uppgraderingsprocessen.


## Uppgradera till version 5.0.0

>[!TIP]
>
> Uppgradering till version 5.0.0 Service Pack 3 beror på vilken version av Experience Manager Guides som är aktuell. Om du använder version 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 eller 5.0.0 kan du uppgradera direkt till version 5.0.0 Service Pack 3. Uppgraderingsstegen är desamma som för version 5.0.0.

>[!NOTE]
>
> Efterbearbetningen och indexeringen kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

**Förutsättningar**

Innan du startar uppgraderingsprocessen för Experience Manager Guides 5.0.0 måste du se till att du har:

1. Uppgraderat till Experience Manager Guides version 4.6.3, 4.6.1, 4.6.0 eller 4.4.
1. (Valfritt) Avslutade alla översättningsuppgifter.
1. Loggnivån har ändrats till **INFO** för klassen `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och loggarna läggs till i en ny loggfil, till exempel `logs/translation_upgrade.log`.


**Installera version 5.0.0**

Ladda ned versionspaketet 5.0.0 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) och följ instruktionerna i [Uppgraderingsarbetsflödet för installation och efterinstallation](#installation-and-post-installation-upgrade-workflow) för att slutföra uppgraderingsprocessen.

## Uppgradera till version 4.6.0

>[!TIP]
>
> Vi rekommenderar att du installerar Service Pack 4.6.0 utöver version 4.6.0, 4.6.0 Service Pack 1 eller 4.6.0 Service Pack 3. Uppgraderingsprocessen för version 4.6.0 Service Pack 4 följer samma steg som version 4.6.0.

Uppgradering till version 4.6.0 beror på vilken version av Experience Manager Guides du har. Om du använder version 4.4.0, 4.3.1, 4.3.0, 4.2 eller 4.2.1 (programfix 4.2.1.3) kan du uppgradera direkt till version 4.6.0.

>[!NOTE]
>
> Efterbearbetningen och indexeringen kan ta några timmar. Vi rekommenderar att du startar uppgraderingsprocessen under lågtider.

**Förutsättningar**

Innan du startar uppgraderingsprocessen för Experience Manager Guides 4.6.0 bör du kontrollera att du har:

1. Uppgraderat till Experience Manager Guides version 4.3.1, 4.3.0 eller 4.2.1 (programfix 4.2.1.3).
1. (Valfritt) Avslutade alla översättningsuppgifter.
1. Loggnivån har ändrats till **INFO** för klassen `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` och loggarna läggs till i en ny loggfil, till exempel `logs/translation_upgrade.log`.

**Installera version 4.6.0**

Ladda ned versionspaketet 4.6.0 från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) och följ instruktionerna i [Uppgraderingsarbetsflödet för installation och efterinstallation](#installation-and-post-installation-upgrade-workflow) för att slutföra uppgraderingsprocessen.

## Arbetsflöde för uppgradering och efterinstallation

### Installera versionspaketet

Så här installerar du versionspaketet:

1. Installera det versionspaket som du vill uppgradera till.
1. Du kan välja att trycka på utlösaren för att starta uppgraderingsjobbet för översättningskartan. Mer information finns i [Aktivera utlösare för skript via en server](#enable-trigger-of-script-via-a-servlet).

1. När du har slutfört paketinstallationen väntar du på följande meddelande i loggarna:

   `Completed the post deployment setup script`

   Ovanstående meddelande anger att alla installationssteg är slutförda.

   Om du råkar ut för något av följande fel ska du rapportera dem till ditt Customer Success Team:

   - Fel i installationsskript efter distribution
   - Undantag vid portering av översättnings-MAP
   - Det går inte att portera översättningskarta från v1 till v2 för egenskap
1. (Valfritt) Plugin-programmet för uppgradering av syreanslutning som släpps med den version du uppgraderar till.
1. Rensa webbläsarcachen när paketet har installerats.

### Efterinstallationsprocess

När du har installerat Experience Manager Guides kan du sammanfoga de olika konfigurationer som gäller från den nyinstallerade versionen till din installation.

>[!NOTE]
>
> Modellen för dam-update-asset kan anpassas. Om några anpassningar har gjorts måste vi synkronisera anpassningarna och Experience Manager Guides i arbetskopian av modellen.

**DAM-uppdateringsarbetsflöde för resurs \(Efterbehandlingsändringar\):**

1. Öppna URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Välj **DAM-uppdateringsarbetsflöde**.
1. Välj **Redigera**.
1. Om komponenten **DXML Post Process Initiator** finns kontrollerar du att anpassningarna är synkroniserade.
1. Om komponenten **DXML Post Process Initiator** inte finns utför du följande steg för att infoga den:

   - Välj **Infoga komponent** \(Ansvarig för efterbearbetning av Experience Manager Guides som det sista steget i processen\).
   - Konfigurera **processsteget** med information nedan:

     **Fliken Allmänt:**

      - **Titel:** DXML Post Process Initiator

      - **Beskrivning**: Steg för initiering av DXML-efterbearbetning av den ändrade/skapade resursen som utlöser ett snedjobb för DXML-efterbearbetning

     **Fliken Process**

      - Välj **DXML Post Process Initiator** i listrutan **Process**
      - Välj **Handler Advance**
      - Välj **Klar**

1. Välj **Synkronisera** överst till höger när du har slutfört ändringarna. Du får ett meddelande om att åtgärden lyckades.

   >[!NOTE]
   >
   > Uppdatera och verifiera att anpassade ändringar och Experience Manager Guides efterbearbetningssteg finns i den slutliga arbetsflödesmodellen.

1. När **DAM-uppdateringsarbetsflödet** har validerats kontrollerar du motsvarande startkonfigurationer. Gå till AEM Workflow och öppna startkartor.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Sök efter och ändra \(om det behövs\) till följande två startprogram \(som ska vara aktiva\) som motsvarar **DAM Update Asset workflow**:

1. Startprogrammet för *noden har skapats* för arbetsflödet **DAM Update Asset** - för villkoret `"jcr:content/jcr:mimeType!=video"` ska värdet Globbing vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - excludeList ska ha `"event-user-data:changedByWorkflowProcess"`.
   - Startfunktionen för *Nod ändrad* för **DAM Update Asset workflow -** för villkoret `jcr:content/jcr:mimeType!=video`. Värdet Globbing ska vara:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` ska ha `"event-user-data:changedByWorkflowProcess"`.

1. När uppgraderingen är klar kontrollerar du att alla anpassningar/övertäckningar har validerats och uppdaterats så att de matchar den nya programkoden. Nedan följer några exempel:
   - Alla komponenter som överlappas av `/libs/fmditaor/libsshould` jämförs med den nya produktkoden och uppdateringar ska göras i överlagrade filer under/appar.
   - Alla `clientlib` kategorier som används från produkten bör granskas för ändringar. Alla åsidosatta konfigurationer `\(examples below\)` bör jämföras med de senaste så att du får de senaste funktionerna:
   - elementmapping.xml
   - `ui\_config.json\(may have been set in folder profiles\)`
   - ändrade `com.adobe.fmdita.config.ConfigManager`

1. Om du har lagt till anpassningar i damAssetLucene kan du behöva använda dem igen. När du har gjort ändringarna anger du reindex som true. Detta indexerar om alla befintliga noder med anpassningarna. När du är klar anges omindexeringsflaggan till false igen. Detta kan ta några timmar beroende på antalet resurser i systemet.

### Steg för att indexera om Experience Manager Guides-index

1. Öppna `crx/de` och navigera till indexsökvägen: `/oak:index/guidesAssetProperties`
2. Ange egenskapen reindex som `true` (`false` som standard) och klicka på **Spara alla**.
3. När omindexeringen är klar ställs egenskapen reindex in på `false` igen och antalet omindexeringar ökas med 1.

   >[!NOTE]
   >
   > Detta kan ta några minuter, beroende på mängden data som finns.
4. Följ samma steg för andra tillagda eller ändrade index: `guidesBulkActivation`, `guidesPeerLinkIndex` och `guidesKonnectTemplateIndex`.

### Steg för indexering av befintligt innehåll

Utför följande steg för att indexera det befintliga innehållet:

- Kör en POST-begäran till servern \(med korrekt autentisering\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Valfritt: Du kan skicka specifika sökvägar för kartorna för att indexera dem. Som standard indexeras alla kartor || Exempel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- API:t returnerar `jobId`. Om du vill kontrollera jobbets status kan du skicka en GET-begäran med jobb-ID till samma slutpunkt - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(till exempel: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- När jobbet är klart kommer ovanstående GET-förfrågan att besvaras med framgång och ange om några kartor misslyckades. De korrekt indexerade mappningarna kan bekräftas från serverloggarna.


>[!NOTE]
>
> Om du använder det anpassade schemat måste du definiera sökvägen för de anpassade DTD- och XSD-filerna catalog.xml i AEM-databasen i alternativet **Integrera kataloger**.

### Steg som ska hantera `'fmdita rewriter'`-konflikten

Experience Manager Guides har en [**anpassad omskrivarmodul**](../install-conf-guide/conf-output-generation.md#custom-rewriter) för hantering av länkar som genereras vid korsmappningar (länkar mellan ämnen på två olika kartor).

Om du har en annan anpassad återskrivningsskrivare i kodbasen använder du ett `'order'`-värde som är större än 50, eftersom Experience Manager Guides återskrivningsprogram använder `'order'` 50.  Om du vill åsidosätta detta måste du ange ett värde > 50. Mer information finns i [Skriva om utdata](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Under den här uppgraderingen måste du, eftersom värdet `'order'` ändras från 1 000 till 50, sammanfoga den befintliga anpassade omskrivaren, om sådan finns, med `'fmdita-rewriter'`.


### Steg för att indexera om damAssetLucene

Indexdefinitionen uppdateras för damAssetLucene med AEM Guides. När du har uppgraderat till den version som krävs kan du läsa [den här artikeln](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-16460) för att indexera om damAssetLucene.

>[!NOTE]
>
> När du följer dokumentationen kontrollerar du att båda egenskaperna (`reindex=true` och `reindex-async=true` för `/oak:index/damAssetLucene`) uppdateras samtidigt via åtgärden Spara.

