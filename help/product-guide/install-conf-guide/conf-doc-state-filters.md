---
title: Konfigurera dokumenttillståndsfilter
description: Lär dig hur du konfigurerar dokumenttillståndsfilter
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# Konfigurera dokumenttillståndsfilter för Cloud Service

I Adobe Experience Manager Guides kan du söka efter en fil baserat på dess aktuella dokumenttillstånd. Du kan använda filtersökningar för att söka efter filer från databasgränssnittet för att bläddra bland filer.

Utför följande steg för att konfigurera dokumenttillståndsfilter:

1. Logga in på Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och välj sedan **Mappprofiler**.
1. Öppna rutan **Global profil**. Du kan också välja en viss mappprofilpanel om du vill att dessa ändringar endast ska gälla för den mappen i stället för globalt.
1. Navigera till **XML-redigerarkonfigurationen**.
1. Välj ikonen **Redigera** längst upp.
1. Välj ikonen **Hämta** om du vill hämta filen `ui\_config.json` på din lokala dator.
Se följande avsnitt i den hämtade `ui\_config.json`-filen:

       &quot;
       &quot;databaseFilters&quot;: &lbrack;
       &lbrace;
       &quot;title&quot;: &quot;Document state&quot;,
       &quot;property&quot;: &quot;jcr:content/metadata/docstate&quot;,
       &quot;underordnade&quot;: &lbrack;
&rbrack;       &lbrace;
       &quot;title&quot;: &quot;Draft&quot;, 
       &quot;value&quot;: &quot;Draft&quot; 
       ,
       &lbrace;
       &quot;title&quot;: &quot;Edit&quot;,
       &quot;value&quot;: &quot;Edit&quot; 
       &rbrace;,
       &lbrace;
       &quot;title&quot;: &quot;In-Review&quot;,
       &quot;value&quot;: &quot;In-Review&quot; 
       &rbrace;,
       &lbrace;
       &quot;title&quot;: &quot;Approved&quot;,
       &quot;value&quot;: &quot;Approved&quot;
       &rbrace;,
       &lbrace;
&rbrace;       &quot;title&quot;: &quot;Reviewed&quot;, 
       &quot;value&quot;: &quot;Reviewed&quot; 
       ,
       &lbrace;
       &quot;title&quot;: &quot;Done&quot;,
       &quot;value&quot;: &quot;Done&quot; 
       
       &rbrack;
       
       &rbrack;
       &quot;
   Det här kodutdraget representerar standarddokumentlägesfilter som är tillgängliga i Experience Manager Guides.

1. Du kan anpassa filtervärdena baserat på organisationens arbetsflöde. Om du till exempel vill lägga till ett anpassat dokumentläge **Väntar** infogar du följande post under `children`:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. När filen har uppdaterats sparar du den och överför den.

De konfigurerade filtren visas på panelen **Filter** på startsidan i Databas.

**Överordnat ämne:**&#x200B;[&#x200B; Anpassa Web Editor](customize-overview.md)
