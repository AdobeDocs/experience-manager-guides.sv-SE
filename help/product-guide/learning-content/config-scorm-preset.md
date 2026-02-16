---
title: SCORM-förinställd konfiguration
description: Läs mer om de olika SCORM-förinställda konfigurationerna i produktutbildning och -inlärning
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
source-git-commit: 3fdedee6e07908632bcf1b804805fcac7925c4e0
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Konfigurera förinställning för SCORM-utdata

När du har skapat förinställningen konfigurerar du inställningarna för SCORM-förinställningen. De förinställda konfigurationsalternativen är ordnade på flikarna Allmänt, Innehåll och Publicera.

- **Allmänt:** Används för att ange grundläggande utdatainställningar, t.ex. vilken version som stöds, utdatasökväg, ZIP-filnamn, utdatamall och andra alternativ som är relaterade till lärarens upplevelse.

  ![](assets/scorm-general-tab-v3.png){width="650" align="left"}

  **Lärarens upplevelse**

   - **Eleverna måste gå igenom innehållet i sekventiell ordning**: Garanterar att eleverna går igenom frågeformuläret i en fast sekvens och kan inte hoppa fram eller hoppa mellan frågorna.
   - **Eleverna måste försöka att fortsätta med varje fråga**: Eleverna måste försöka med alla frågor innan de kan skicka in frågeformuläret, vilket förhindrar ofullständiga svar.
   - **Slumpmässigt frågeordning för varje försök**: Visar frågor i olika ordning för varje försök, vilket minskar förutsägbarheten.
   - **Slumpmässigt svarsalternativ för varje försök**: Blandar svarsalternativen för varje fråga vid varje försök och minskar därmed risken för gissning baserat på position.
   - **Använd fråge-ID i frågerapportering**: Inkluderar det unika fråge-ID:t i frågerapporter, vilket gör det enklare att spåra, analysera och mappa resultat tillbaka till specifika frågor.
   - **Arbetsflöde efter generering**: När du väljer det här alternativet visas en ny arbetsflödeslista efter generering som innehåller alla konfigurerade arbetsflöden.

- **Innehåll:** Används för att ange tillgänglig villkorsstyrd filtrering (med DITAVAL eller med någon villkorsförinställning) och variabeluppsättningen.

  ![](assets/scorm-content-tab.png){width="650" align="left"}

- **Publicera:** Använd bara den här inställningen om du vill publicera utdata till SCORM Cloud för direkt åtkomst.

  ![](assets/scorm-publish-tab.png){width="650" align="left"}

När alla ändringar har konfigurerats sparar du ändringarna för SCORM-förinställningen med **Spara** till höger i verktygsfältet på sidan SCORM-förinställning.
