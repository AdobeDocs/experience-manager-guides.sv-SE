---
title: Bearbeta och bearbeta resurser
description: Lär dig hur du bearbetar resurser
feature: Migration
role: Admin
level: Experienced
exl-id: 27786098-119c-4b7a-8275-8a89d435294f
source-git-commit: 851dafc1f17864bf6a295de7be12ffe513c3af57
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Bearbeta eller bearbeta resurser

I dataintensiva arbetsflöden som publicering är effektiv resurshantering avgörande för att upprätthålla prestanda och tillförlitlighet. Processen att bearbeta eller bearbeta resurser är särskilt utformad för att hantera användarspecifika resurser som kräver intensiva dataåtgärder. Den här metoden behandlar två primära scenarier: när den inledande bearbetningen av resurser påträffar fel eller när filer inte bearbetades alls på grund av att det inte finns någon efterbearbetningsutlösare. Genom att aktivera målstyrd bearbetning på mappnivå kan användarna isolera och bearbeta endast de nödvändiga resurserna, och därigenom undvika onödiga beräkningar. Denna selektiva metod förbättrar prestanda avsevärt och minskar tiden som krävs för kritiska operationer som publicering och rapportgenerering. På det hela taget bidrar det till ökad effektivitet och snabbare hantering av komplexa datauppgifter.

>[!NOTE]
>
> För stora datauppsättningar är det bäst att köra bearbetningen under tider med låg belastning för att undvika att påverka systemets prestanda. När bearbetningen är klar kan du granska informationen för att analysera resultaten.

## Bearbetar resurserna

Följ stegen nedan för att bearbeta eller bearbeta om mediefilerna:

1. Markera Adobe Experience Manager logotyp överst och välj **Verktyg**.
1. Välj **Stödlinjer** på panelen **Verktyg**.
1. Välj **resursprocessorpanelen**.

   ![flow-asset-processor](images/flow-asset-processor.png){align="left"}

1. Fönstret Guides Asset Processor öppnas med informationen som visas nedan. I det här fönstret visas bara den information som gäller de senaste fem migreringarna.

   - **Körnings-ID**: Det är det unika ID:t för varje ombearbetningsuppgift som du utför.

   - **Mapp**: Visar den mapp som har valts för ombearbetning.

   - **Exkluderade mappar**: pekar på mappen som inte kan bearbetas om.

   - **Starttid:** Visar datum och tid då ombearbetningen initieras.

   - **Sluttid**: Visar datum och tid då bearbetningen avslutas.

   - **Status**: pekar på status för pågående ombearbetning, slutförd eller Avbruten.

   ![Guides-asset-processor](images/guides-asset-processor.png){align="left"}

1. Välj fliken **Ny process** längst upp till höger i fönstret om du vill starta en ny bearbetningsåtgärd.

   ![New-process-asset-processor](images/new-process-asset-processor.png){width="550" align="left"}

1. Markera den mapp som du vill bearbeta eller bearbeta om. Du kan också markera de mappar (i den överordnade markerade mappen) som du vill utesluta eller ignorera.

   >[!NOTE]
   >
   >Det går endast att markera en mapp åt gången för bearbetning. För specifika åtgärder kan du exkludera flera mappar.

1. Välj **Skapa**. Du får ett popup-fönster som visar **Slutfört och processen har utlösts**, vilket visas i fragmentet. Samma sak visas i listan. Du kan se status för återbearbetningsaktiviteten i fönstret.

   ![Message-asset-processor](images/message-asset-processor.png){width="550" align="left"}


## Ytterligare alternativ för bearbetning av uppgifter

Det finns fler alternativ för bearbetningsuppgiften när den har initierats. Du kan komma åt dessa alternativ genom att hovra över uppgifternas körnings-ID. Mer information om dessa alternativ finns nedan:

- **Starta om** : Startar om den tidigare slutförda resurshanteringsuppgiften.

  ![omstart-asset-processor](images/restart-asset-processor.png){align="left"}

- **Återuppta** : Återupptar den tidigare avbrutna eller misslyckade resurshanteringen.

  ![resume-asset-processor](images/resume-asset-processor.png){align="left"}

- **Avbryt** : Avbryter den pågående resurshanteringen.

  ![cancel-asset-processor](images/cancel-asset-processor.png){align="left"}

- **Visa loggar**: Visar loggarna för resurshanteringsuppgiften. För pågående uppgifter visar loggen detaljerad bearbetningsinformation, inklusive uppskattad återstående tid och resursstatus. Den här logglistan visar upp till de senaste 500 posterna. Den fullständiga loggen kan laddas ned.

  ![logs-asset-processor](images/logs-asset-processor.png){align="left"}
