---
title: Översätta innehåll i AEM Guides
description: Lär dig hur du översätter innehåll
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: bc2348ae3342addf9ab05a3e3898fa485dba9bcf
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 0%

---

# Översätta innehåll {#id181GB0400UI}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera arbetsflöden för översättning integrerar du översättare med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

- Översättning till människor: Innehållet skickas till din översättningsleverantör och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM utbyts innehåll automatiskt mellan AEM och översättningsleverantören

- Maskinöversättning: Maskinöversättningstjänsten översätter omedelbart ditt innehåll


Översättning av innehåll omfattar följande steg:

1. Anslut AEM till din [översättningstjänstleverantör](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) och skapa [konfigurationer för översättningsintegreringsramverk](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associera sidorna i din språkinställning med [översättningstjänsten och ramverkskonfigurationerna](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifiera typen av [innehåll som ska översättas](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Förbered innehållet för översättning](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) genom att skapa språkinställningen och skapa rotsidorna för språkkopior.

1. Skapa [översättningsprojekt](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) om du vill samla in innehållet som ska översättas och förbereda översättningsprocessen.

1. Använd översättningsprojekten för att [hantera innehållsöversättningsprocessen](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html).


När översättningstjänstleverantören inte tillhandahåller någon koppling till integrering med AEM stöder AEM manuell export och import av översatt innehåll i XML-format.

>[!TIP]
>
> Se avsnittet *Översättning* s i guiden om bästa praxis för översättning av innehåll.

## Konfigurera översättningsfliken på DITA-kartpanelen

Alternativet Dölj översättningsflik är inte aktiverat som standard och du måste aktivera det från configMgr. Så här döljer du översättningsfliken på DITA-kartkontrollpanelen:

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

## Konfigurera komponentbaserat översättningsarbetsflöde

Om kopplingen för översättningsleverantören inte stöder DITA-innehåll måste det komponentbaserade översättningsarbetsflödet aktiveras. När det är aktiverat skickas det översättningsbara innehållet som metadata för resursen. Kopplingen måste dock ha stöd för översättning av metadata för resurser för att det här arbetsflödet ska fungera.

Baserat på det översättningsarbetsflöde som används i konfigurationen bör det komponentbaserade arbetsflödesalternativet för översättning konfigureras enligt följande:

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
   > Om du använder översättningskoppling kontrollerar du att du har konfigurerat kopplingen enligt beskrivningen i avsnittet *[Konfigurera översättningsintegreringsramverket](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* i AEM.

1. Klicka på **Spara**.

<!---

This was added for 2406 CS IG

## Configure the legacy translation workflow 

It is recommended that you use the latest translation workflow, which provides enhanced performance. However, you can configure the legacy translation workflow if necessary.

Based on the translation workflow used in your setup, provide the following (property) details to configure the legacy translation workflow: the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ! Add the syntax of http as given in previous config

    Note: Configure htttp code as given in previous sample
    

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.



1.  Configure the **Run legacy translation workflow** option as per your setup:

    -   If you use the latest translation workflow, then *Disable* \( `false`\) the **Run legacy translation workflow** option. The latest translation workflow is enabled by default. <br> 

    -   If you use the legacy translation, then *Enable \( `true`\)* the **Run legacy translation workflow** option.

1.  Click **Save**.


--->
>[!IMPORTANT]
>
> När du har konfigurerat översättningskonfigurationerna kontrollerar du att du har konfigurerat rätt molnkonfiguration för språkmapparna.

## Konfigurera efterbearbetning av tillfälliga språkkopior

När du initierar översättningsarbetsflödet skapas tillfälliga språkkopior av källinnehållet. Du kan välja att aktivera eller inaktivera efterbearbetningen för dessa tillfälliga filer. I efterbearbetningen löses de inkommande och utgående referenserna från filerna, dokumentläget ställs in tillsammans med andra åtgärder. Om du aktiverar efterbearbetning för de här temporära filerna kan översättningsprocessen ta längre tid att slutföra. Därför rekommenderar vi att alternativet för efterbearbetning är inaktiverat.

Som standard är alternativet för efterbearbetning av tillfälliga filer inaktiverat. Du kan konfigurera det här alternativet genom att utföra följande steg:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet **com.adobe.fmdita.config.ConfigManager**.

1. Konfigurera alternativet **Post-bearbeta språkkopior** enligt dina inställningar:

   - \(*Standard*\) Om du inte vill köra efterbearbetningsåtgärden för de temporära filerna *Inaktivera* alternativet **Post-processspråk kopieras**.

   - Om du vill köra efterbearbetningen av de temporära filerna *Aktivera* alternativet **Post-processspråkkopior**.

1. Klicka på **Spara**.
