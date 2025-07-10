---
title: Inkrementell utdatagenerering
description: Lär dig hur inkrementell generering av utdata för AEM Sites fungerar i AEM Guides.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: 05d3246bd8b1e1b1d870b494aa09f6acff8a0f1d
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---


# Inkrementell utdatagenerering

>[!NOTE]
>
> Inkrementell generering av utdata gäller endast för AEM Sites-utdata. Du kan också endast återskapa DITA-avsnitt \(.dita/.xml\) från en DITA-karta eller underkartor. Om du väljer en DITA-karta, delkarta, ämnesgrupp eller ett ämne med `@processing-role="resource-only"` är alternativet för att generera om inte tillgängligt.

Det kan finnas ett antal tillfällen då du bara uppdaterar ett fåtal ämnen på din DITA-karta och bara överför dessa uppdaterade ämnen live. Om du vill hantera sådana scenarier kan du skapa inkrementella utdata i Experience Manager Guides. Om du har uppdaterat några avsnitt behöver du inte generera om hela DITA-kartan. Du kan bara välja de uppdaterade avsnitten och återskapa dem.

Om kartan är hackad och du har uppdaterat ett enskilt ämne på kartan, måste du generera om hela kartan för det uppdaterade ämnet eller innehållet så att det återspeglas i utdata. Du får inte alternativet för omgenerering av utdata på ämnesnivå, det är bara tillgängligt på mappningsnivån \(chunked\). Detta gäller för den överordnade kartan och alla underkartor.

Så här återskapar du utdata för ett visst ämne eller en grupp ämnen:

## Generera inkrementella utdata från kartkonsolen (för AEM-platser med hjälp av sammansatt komponentmappning)

Utför följande steg för att generera inkrementella utdata för AEM Sites med hjälp av karskonsolen:

1. [Öppna DITA-kartfilen i kartkonsolen](./open-files-map-console.md).
1. Välj den förinställning för AEM Sites som du vill generera inkrementella utdata för.
1. Välj de ämnen du vill publicera på fliken **Ämnen**.

   - Utan baslinje

     ![Ämneslista för objektwebbplatser](images/aem-presets-topic-list.png) {align="left"}

   - Med baslinje

     ![Objektwebbplatsens ämneslista med baslinje](images/aem-presets-topic-list-new.png) {align="left"}

   >[!NOTE]
   >
   > När en baslinje har valts på fliken **Innehåll** visas ämnen och deras versioner från den kopplade baslinjen i ämneslistan.<br><br>
   > Den inkrementella publiceringen från ämneslistan bör endast användas när kartans struktur inte ändras. Om mappningsstrukturen/innehållsförteckningen ändras ska hela kartan publiceras en gång för att uppdatera innehållsförteckningen.

1. Välj **Spara** om du vill spara ändringarna.
1. Välj **Generera utdata** för att generera utdata.


## Generera inkrementella utdata från kontrollpanelen för kartor (för AEM-webbplatser som använder äldre komponentmappning)

Utför följande steg för att generera inkrementella utdata för AEM Sites med hjälp av kartpanelen:

1. Navigera till och markera DITA-kartfilen i Assets-gränssnittet.

   DITA-kartkonsolen visas med en lista över tillgängliga utdatapresentationer för att generera utdata.

1. Välj fliken **Ämnen**.

   En lista med ämnen som är tillgängliga på DITA-kartan visas.

1. Markera de ämnen som du vill återskapa.

   >[!NOTE]
   >
   > Om du har lagt till nya ämnen i DITA-kartan kan du inte generera dessa nya ämnen härifrån. Du måste först publicera de nya ämnena med DITA-kartpubliceringsfunktionen.

   ![](images/regenerate-topics.png){align="left"}

1. Välj **Återskapa**.

   Sidan **Återskapa markerade ämnen** visas.

1. Välj den förinställning för utdata som du vill använda för att återskapa de valda ämnena.

   Om du väljer en baslinje används ämnesversionerna som ingår i den valda baslinjen för att generera utdata för AEM Sites-förinställningar som använder äldre komponentmappning. Dessutom bör inkrementell publicering från ämneslistan endast användas när det inte finns några ändringar i kartstrukturen. Om mappningsstrukturen/innehållsförteckningen ändras ska hela kartan publiceras en gång för att uppdatera innehållsförteckningen. Mer information om hur du använder AEM-webbplatsförinställningar finns i [AEM Sites-förinställningar på kartkontrollpanelen](./generate-output-aem-site-map-dashboard.md).


1. Välj **Återskapa** för att starta genereringsprocessen för utdata.


>[!IMPORTANT]
>
> Om du byter namn på ett ämne och genererar om ämnet, återspeglas inte den uppdaterade ämnestiteln i DITA-schemats innehållsförteckning. Om du vill uppdatera ämnestiteln i innehållsförteckningen måste du generera hela DITA-kartan.

Du kan visa aktuell status för begäran om generering av utdata på fliken **Utdata**. Mer information finns i [Visa status för utdatagenereringsaktiviteten](#view-the-status-of-the-output-generation-task).



**Överordnat ämne:** [Förstå förinställningarna för utdata](generate-output-understand-presets.md)
