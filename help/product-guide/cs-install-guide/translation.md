---
title: Översätta innehåll
description: Lär dig hur du översätter innehåll
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: bcb61127f5f69ac39860a90eac2e1a56ecd1de31
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 0%

---

# Översätta innehåll {#id181GB0400UI}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera arbetsflöden för översättning integrerar du översättare med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

- Översättning till människor: Innehållet skickas till din översättningsleverantör och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM utbyts innehåll automatiskt mellan AEM och översättningsleverantören

- Maskinöversättning: Maskinöversättningstjänsten översätter omedelbart ditt innehåll


Översättning av innehåll omfattar följande steg:

1. Anslut AEM till din [översättningstjänstleverantör](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) och skapa konfigurationer för ramverk för översättningsintegrering.

1. Koppla sidorna i din språkinställning till översättningstjänsten och ramverkskonfigurationerna.

1. Identifiera typen av [innehåll som ska översättas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Förbered innehållet för översättning](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) genom att skapa språkinställningen och skapa rotsidorna för språkkopior.

1. Skapa [översättningsprojekt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) om du vill samla in innehållet som ska översättas och förbereda översättningsprocessen.

1. Använd översättningsprojekten för att [hantera innehållsöversättningsprocessen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en).


När översättningstjänstleverantören inte tillhandahåller någon koppling till integrering med AEM stöder AEM manuell export och import av översatt innehåll i XML-format.

>[!TIP]
>
> Mer information om de bästa sätten att översätta innehåll finns i avsnittet *Översättning* i guiden om bästa praxis.

## Konfigurera översättningsfliken på DITA-kartpanelen

Så här döljer du översättningsfliken på DITA-kartkontrollpanelen:

1. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen.
1. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera översättningsfliken på kartkontrollpanelen:

   | PID | Egenskapsnyckel | Egenskapsvärde |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolean \( true/ false\).<br> **Standardvärde**: `true` |

   >[!NOTE]
   >
   > Den här konfigurationen är aktiverad som standard och översättningsfliken är inte tillgänglig på kartkontrollpanelen.


## Konfigurera komponentbaserat översättningsarbetsflöde

Om kopplingen för översättningsleverantören inte stöder DITA-innehåll måste det komponentbaserade översättningsarbetsflödet aktiveras. När det är aktiverat skickas det översättningsbara innehållet som metadata för resursen. Kopplingen måste dock ha stöd för översättning av metadata för resurser för att det här arbetsflödet ska fungera.

Baserat på det översättningsarbetsflöde som används i konfigurationen bör det komponentbaserade arbetsflödesalternativet för översättning konfigureras. Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera komponentbaserat översättningsarbetsflöde:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolean: <br> -   Om du använder mänsklig översättning *Inaktivera* \( `false`\) alternativet **Komponentbaserat översättningsarbetsflöde** . <br> -   Om du använder maskinöversättning *Aktivera \( `true`\)* alternativet **Komponentbaserat översättningsarbetsflöde** . |



## Konfigurera det äldre arbetsflödet för översättning

Vi rekommenderar att du använder det senaste arbetsflödet för översättning, vilket ger bättre prestanda. Om du vill använda det äldre arbetsflödet för översättning kan du konfigurera det.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande (egenskap) information i konfigurationsfilen för att konfigurera det äldre arbetsflödet för översättning:




| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booleskt: <br> - Om du använder det senaste översättningsarbetsflödet *Inaktivera* \( `false`\) alternativet **Kör gammalt översättningsarbetsflöde**. Det senaste arbetsflödet för översättning är aktiverat som standard. <br> -   Om du använder den äldre översättningen *Aktivera \( `true`\)* alternativet **Kör äldre översättningsarbetsflöde** . |



>[!NOTE]
>
> Om du använder översättningskoppling kontrollerar du att du har konfigurerat kopplingen enligt beskrivningen i avsnittet *[Konfigurera översättningsintegreringsramverket](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* i Adobe Experience Manager-dokumentationen.

>[!IMPORTANT]
>
> När du har konfigurerat översättningskonfigurationerna kontrollerar du att du har konfigurerat rätt molnkonfiguration för språkmapparna.

## Konfigurera efterbearbetning av tillfälliga språkkopior

När du initierar översättningsarbetsflödet skapas tillfälliga språkkopior av källinnehållet. Du kan välja att aktivera eller inaktivera efterbearbetningen för dessa tillfälliga filer. I efterbearbetningen löses de inkommande och utgående referenserna från filerna, dokumentläget ställs in tillsammans med andra åtgärder. Om du aktiverar efterbearbetning för de här temporära filerna kan översättningsprocessen ta längre tid att slutföra. Därför rekommenderar vi att alternativet för efterbearbetning är inaktiverat.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera efterbearbetning av tillfälliga språkkopior:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolean: <br> -   Om du inte vill köra efterbearbetningen av de temporära filerna *Inaktivera* \( false\) alternativet **Post-processspråkkopior** .<br> -   Om du vill köra efterbearbetningen av de temporära filerna *Enable* \( true\) the **Post-process language copies** .<br> **Standardvärde**: false |

