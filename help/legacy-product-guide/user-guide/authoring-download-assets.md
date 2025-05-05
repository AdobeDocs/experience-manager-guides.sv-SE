---
title: Hämta filer
description: Lär dig hur du hämtar filer från DITA-kartkonsolen i AEM Guides och exporterar en DITA-kartfil i AEM-databasen.
feature: Content Management
role: User
hide: true
exl-id: b04a0abe-a029-44ac-b8f4-138d78908d44
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Hämta filer {#id216MC0H0BE8}

Du kan hämta resurser, inklusive DITA-filer och andra filer. Du kan hämta resurser på flera olika sätt. Vissa metoder är inbyggda i AEM och andra stöds av AEM Guides. Inbyggd hämtningsinformation för AEM-resurser finns i [Hämta resurser från Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) i AEM-dokumentationen. I följande avsnitt förklaras hur du hämtar filer via DITA-kartkonsolen i AEM Guides.

## Exportera en DITA-kartfil

När du har DITA-kartfilen i AEM-databasen kan du hämta kartfilen tillsammans med dess underordnade filer. Detta ger dig flexibilitet att dela hela kartfilen för offlineredigering, validering, granskning eller att helt enkelt skapa en säkerhetskopia.

Följ de här stegen för att hämta en DITA-kartfil tillsammans med de beroende filerna:

1. Navigera till den DITA-karta som du vill hämta i Assets-gränssnittet.

1. Klicka på DITA-kartan för att öppna den i DITA-kartkonsolen.

1. Välj fliken **Ämnen** om du vill visa en lista med ämnen som är tillgängliga på DITA-kartan.

1. Klicka på **Hämta karta** i huvudverktygsfältet.

   Dialogrutan Hämta karta visas.

   ![](images/download-map.png){width="300" align="left"}

1. Klicka på **Hämta**. I dialogrutan Hämta karta kan du välja följande alternativ:

   - **Använd baslinje**: Välj det här alternativet om du vill visa en lista över baslinjer som skapats för DITA-kartan. Om du vill hämta kartfilen och dess innehåll baserat på en viss baslinje väljer du Baslinje i listrutan. Mer information om att arbeta med baslinjer finns i [Arbeta med baslinje](generate-output-use-baseline-for-publishing.md#).
   - **Förenkla filhierarkin**: Välj det här alternativet om du vill spara alla refererade ämnen och mediefiler i en enda mapp.

   >[!NOTE]
   >
   > Du kan även hämta kartfilen utan att välja något alternativ. I så fall hämtas den senaste beständiga versionen av de ämnen och mediefiler som refereras.

1. När du har klickat på knappen **Hämta** köas begäran om karthämtning. Du får följande meddelande när kartan är klar att hämtas.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Klicka på **Hämta** om du vill hämta kartfilen i zip-format.

   - Klicka på **Hämta senare** om du vill hämta kartfilen vid ett senare tillfälle. Du kommer åt nedladdningslänken via AEM meddelandeinkorg. Klicka på det genererade kartmeddelandet i Inkorgen för att hämta kartan i ZIP-format.

   >[!NOTE]
   >
   > Som standard finns de hämtade kartorna kvar i fem dagar i AEM meddelandeinkorg.

![](images/download-map-inbox.png){width="300" align="left"}

När kartan har laddats ned kan du markera kartan och använda ikonen Öppna längst upp för att öppna den markerade rapporten.

**Överordnat ämne:**&#x200B;[ Hantera innehåll](authoring.md)
