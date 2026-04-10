---
title: Översätta innehåll
description: Lär dig hur du översätter innehåll
feature: Translation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '1368'
ht-degree: 0%

---

# Översätta innehåll {#id181GB0400UI}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera översättningsarbetsflöden integrerar du översättningstjänster med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning till människor och datorer.

- Översättning till människor: Innehållet skickas till din översättningsleverantör och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM utbyts innehåll automatiskt mellan AEM och översättningsleverantören

- Maskinöversättning: Maskinöversättningstjänsten översätter omedelbart ditt innehåll


Följande flikar innehåller anvisningar för översättning av innehåll baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Anslut AEM till din [översättningstjänstleverantör](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=sv-SE) och skapa konfigurationer för ramverk för översättningsintegrering.

1. Koppla sidorna i din språkinställning till översättningstjänsten och ramverkskonfigurationerna.

1. Identifiera typen av [innehåll som ska översättas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=sv-SE).

1. [Förbered innehållet för översättning](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=sv-SE) genom att skapa språkinställningen och skapa rotsidorna för språkkopior.

1. Skapa [översättningsprojekt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=sv-SE) om du vill samla in innehållet som ska översättas och förbereda översättningsprocessen.

1. Använd översättningsprojekten för att [hantera innehållsöversättningsprocessen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=sv-SE).


>[!TAB Lokal]

1. Anslut AEM till din [översättningstjänstleverantör](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) och skapa [konfigurationer för översättningsintegreringsramverk](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associera sidorna i din språkinställning med [översättningstjänsten och ramverkskonfigurationerna](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifiera typen av [innehåll som ska översättas](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Förbered innehållet för översättning](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-prep.html) genom att skapa språkinställningen och skapa rotsidorna för språkkopior.

1. Skapa [översättningsprojekt](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-manage.html) om du vill samla in innehållet som ska översättas och förbereda översättningsprocessen.

1. Använd översättningsprojekten för att [hantera innehållsöversättningsprocessen](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-manage.html).

>[!ENDTABS]

När översättningstjänsten inte har någon koppling till AEM stöder AEM manuell export och import av översatt innehåll i XML-format.

>[!TIP]
>
> Mer information om de bästa sätten att översätta innehåll finns i avsnittet *Översättning* i guiden om bästa praxis.

## Konfigurera översättningsfliken på DITA-kartpanelen

Följande flikar innehåller anvisningar om hur du döljer översättningsfliken på DITA-kartkontrollpanelen baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera översättningsfliken på kartkontrollpanelen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolean \( true/ false\).<br> **Standardvärde**: `true` |

   >[!NOTE]
   >
   > Den här konfigurationen är aktiverad som standard och översättningsfliken är inte tillgänglig på kartkontrollpanelen.


>[!TAB Lokal]

Alternativet Dölj översättningsflik är inte aktiverat som standard och du måste aktivera det från configMgr.


1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Välj alternativet **Dölj översättningsflik** om du vill dölja översättningsfliken på kartkontrollpanelen.

   >[!NOTE]
   >
   > Den här egenskapen är inaktiverad som standard och översättningsfliken är tillgänglig på kartkontrollpanelen.

1. Klicka på **Spara**.

>[!ENDTABS]


## Konfigurera komponentbaserat översättningsarbetsflöde

Om kopplingen för översättningsleverantören inte stöder DITA-innehåll måste det komponentbaserade översättningsarbetsflödet aktiveras. När det är aktiverat skickas det översättningsbara innehållet som metadata för resursen. Kopplingen måste dock ha stöd för översättning av metadata för resurser för att det här arbetsflödet ska fungera.

Följande flikar innehåller instruktioner för översättningsarbetsflödet baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Baserat på det översättningsarbetsflöde som används i konfigurationen bör det komponentbaserade arbetsflödesalternativet för översättning konfigureras. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera komponentbaserat översättningsarbetsflöde:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolean: <br> -   Om du använder mänsklig översättning *Inaktivera* \( `false`\) alternativet **Komponentbaserat översättningsarbetsflöde** . <br> -   Om du använder maskinöversättning *Aktivera \( `true`\)* alternativet **Komponentbaserat översättningsarbetsflöde** . |

>[!TAB Lokal]

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Konfigurera alternativet **Komponentbaserat DITA-översättningsarbetsflöde** enligt inställningarna:

   - Om du använder mänsklig översättning *Inaktivera* alternativet **Komponentbaserat översättningsarbetsflöde**.

   - Om du använder maskinöversättning *Aktivera* alternativet **Komponentbaserat översättningsarbetsflöde**.

   >[!NOTE]
   >
   > Om du använder översättningskoppling kontrollerar du att du har konfigurerat kopplingen enligt beskrivningen i avsnittet *[Konfigurera översättningsintegreringsramverket](https://helpx.adobe.com/se/experience-manager/6-5/sites/administering/using/tc-tic.html)* i AEM-dokumentationen.

1. Klicka på **Spara**.

>[!IMPORTANT]
>
> När du har konfigurerat översättningskonfigurationerna kontrollerar du att du har konfigurerat rätt molnkonfiguration för språkmapparna.

>[!ENDTABS]


## Konfigurera det äldre arbetsflödet för översättning

Följande flikar innehåller anvisningar om hur du konfigurerar det här alternativet baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

>[!IMPORTANT]
>
> Vi rekommenderar att du använder det senaste översättningsarbetsflödet, som finns i AEM Guides 2024.06.0 och senare, för bättre prestanda. Om du har aktiverat en anpassning i översättningsprocessen och den påverkas av det nya arbetsflödet bör du överväga att återgå till det gamla översättningsarbetsflödet som en tillfällig lösning.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera det äldre arbetsflödet för översättning:


| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booleskt: <br> - Om du använder det senaste översättningsarbetsflödet *Inaktivera* \( `false`\) alternativet **Kör gammalt översättningsarbetsflöde**.  <br> -   Om du använder den äldre översättningen *Aktivera \( `true`\)* alternativet **Kör äldre översättningsarbetsflöde** . <br> **Standardvärde**: false |


>[!NOTE]
>
> Om du använder översättningskoppling kontrollerar du att du har konfigurerat kopplingen enligt beskrivningen i avsnittet *[Konfigurera översättningsintegreringsramverket](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=sv-SE)* i Adobe Experience Manager-dokumentationen.

>[!IMPORTANT]
>
> När du har konfigurerat översättningskonfigurationerna kontrollerar du att du har konfigurerat rätt molnkonfiguration för språkmapparna.

>[!TAB Lokal]

>[!IMPORTANT]
> 
> Vi rekommenderar att du använder det senaste arbetsflödet för översättning, som finns i AEM Guides 4.6.0 och senare, för bättre prestanda. Om du har aktiverat en anpassning i översättningsprocessen och den påverkas av det nya arbetsflödet bör du överväga att återgå till det gamla översättningsarbetsflödet som en tillfällig lösning. Som standard är alternativet för äldre översättningsarbetsflöde inaktiverat.

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Konfigurera det äldre alternativet för översättningsarbetsflöde enligt dina inställningar:

   - (*Standard*) Om du vill använda det senaste översättningsarbetsflödet inaktiverar du alternativet **Kör gammalt översättningsarbetsflöde**.
   - Om du vill använda det äldre översättningsarbetsflödet aktiverar du alternativet **Kör gammalt översättningsarbetsflöde**.

1. Klicka på **Spara**.

>[!ENDTABS]

## Konfigurera efterbearbetning av tillfälliga språkkopior

När du initierar översättningsarbetsflödet skapas tillfälliga språkkopior av källinnehållet. Du kan välja att aktivera eller inaktivera efterbearbetningen för dessa tillfälliga filer. I efterbearbetningen löses de inkommande och utgående referenserna från filerna, dokumentläget ställs in tillsammans med andra åtgärder. Om du aktiverar efterbearbetning för de här temporära filerna kan översättningsprocessen ta längre tid att slutföra. Därför rekommenderar vi att alternativet för efterbearbetning är inaktiverat.

Följande flikar innehåller anvisningar om hur du konfigurerar det här alternativet baserat på din Experience Manager Guides-konfiguration: Cloud Service eller On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera efterbearbetning av tillfälliga språkkopior:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolean: <br> -   Om du inte vill köra efterbearbetningen av de temporära filerna *Inaktivera* \( false\) alternativet **Efterbearbetningsspråk** .<br> -   Om du vill köra efterbearbetningen av de temporära filerna *Enable* \( true\) the **Post-process language copies** .<br> **Standardvärde**: false |

>[!TAB Lokal]

>[!NOTE]
>
> Som standard är alternativet för efterbearbetning av tillfälliga filer inaktiverat.

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Konfigurera alternativet **Efterbearbetning av språkkopior** enligt dina inställningar:

   - \(*Standard*\) Om du inte vill köra efterbearbetningsåtgärden för de temporära filerna *Inaktivera* alternativet **Efterbearbetningsspråk**.

   - Om du vill köra efterbearbetningen av de temporära filerna *Aktivera* alternativet **Efterbearbetning av språkkopior**.

1. Klicka på **Spara**.

>[!ENDTABS]