---
title: PDF
description: Generera och konfigurera PDF-utdata för FrameMaker-dokument i AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# PDF {#id205BB0T20RH}

Följande alternativ är tillgängliga för PDF Output:

>[!NOTE]
>
> Om du vill öppna förinställningar för utdata för PDF väljer du en FrameMaker \(`.fm` eller `.book`\)-fil, markerar sedan Utdatainställningar och väljer alternativet PDF Output.

| PDF-alternativ | Beskrivning |
|-----------|-----------|
| Utdatatyp | Den typ av utdata som du vill generera. Om du vill generera utdata från PDF väljer du alternativet PDF. |
| Inställningsnamn | Ange ett beskrivande namn för de PDF-utdatainställningar som du skapar. Du kan till exempel ange *interna kunders utdata* eller *slutanvändares utdata*. |
| **Jobbinställningar** |  |
| Alternativ | Välj den förinställning för PDF som du vill använda för att generera PDF-utdata. |
| Generera taggad PDF | Välj det här alternativet om du vill generera taggade PDF-filer som innehåller information om dokumentets innehåll och struktur. Den här informationen används av skärmläsare. |
| Generera PDF för varje fil i boken | Om du genererar utdata för en bokfil väljer du det här alternativet för att generera ett separat PDF för varje fil i boken. |
| Generera endast PDF för granskning | Välj det här alternativet om du vill generera PDF med kommentarsfunktionen aktiverad. |
| Skapa namngivet mål för alla element och stycken | Välj det här alternativet om du vill skapa namngivna mål baserat på element och stycken. |
| **Visningsinställningar** |  |
| Öppna dokument på sidan | Ange vilket sidnummer som ska visas när du öppnar PDF. |
| Inledande zoomnivå | Välj dokumentets zoomnivå. |
| Registreringsmärke | Om du vill skriva ut ett dokument med skärmärken och passmärken väljer du ett alternativ i listrutan Registreringsmärken. |
| Sidbredd och sidhöjd | Ange sidans bredd och höjd. |
| Sidintervall | Välj om du vill publicera alla sidor i boken eller ett sidintervall. Om du väljer Intervall måste du ange sidintervallet Från och Till. |
| Konvertera CYMK till RGB | Välj det här alternativet om du vill konvertera CMYK-färger till RGB i den genererade PDF. |
| Generera PDF-bokmärken | Skapa tillgängliga PDF som innehåller bokmärken. |
| Målsökväg | Sökvägen i AEM-databasen där PDF-utdata lagras. |
| Kör arbetsflöde efter generering | När du väljer det här alternativet visas en ny arbetsflödeslista som innehåller alla arbetsflöden som konfigurerats i AEM. Du måste välja ett arbetsflöde som du vill köra när arbetsflödet för generering av utdata har slutförts. |

**Överordnat ämne:**&#x200B;[&#x200B; Generera utdata för FrameMaker-dokument](fm-output-generatation.md)
