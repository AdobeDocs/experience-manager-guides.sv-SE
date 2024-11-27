---
title: Statusrapport för konvertering
description: Konvertera dokument i olika format till DITA i AEM Guides. Lär dig hur du lägger till filter och visar en konverteringsstatusrapport.
feature: Report Generation
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Statusrapport för konvertering {#id205BBA00WZZ}

AEM Guides har en robust konverteringsfunktion för att konvertera dokument i olika format till DITA. I Conversion Status Report finns en samlad vy över alla konverteringsåtgärder som utförs av AEM Guides.

Följ de här stegen för att visa rapporten om konverteringsstatus:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på rutan **Konverteringsstatusrapport**.

   Statusrapporten för konvertering visas för alla konverteringsåtgärder som körs i systemet.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. Rapportsidan är uppdelad i två delar:

   - **Filter:**

     Du kan filtrera rapportdata baserat på filtyp och konverteringsstatus. I filtypen kan du välja att visa rapportdata för Word-dokument, dokument av typen strukturerad HTML, XML och DocBook. I Status kan du välja att visa rapportdata för aktiviteter som har körts utan fel, misslyckats, aktiverats eller placerats i kö.

     På följande skärmbild visas rapportdata för konverteringsåtgärder som har statusen Misslyckad, Aktiv och Köad.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Rapportera data:**

     Rapportdata innehåller följande kolumner:

      - **Filnamn**: Namnet på källfilen som konverteringsprocessen kördes på. När du klickar på länken Filnamn kommer du till källdokumentets plats.

      - **Filtyp**: Typ av källdokument, som kan vara Word, strukturerad HTML, XML och DocBook.

      - **Tillagd av**: Namnet på användaren som utförde konverteringsåtgärden.

      - **Datum tillagt**: Datum när aktiviteten kördes. Loggfilen hämtas när du klickar på länken Tillagt den.

      - **Sökväg**: Källdokumentets fullständiga sökväg.

      - **Status**: Status för konverteringsaktiviteterna - Slutfört, Misslyckat, Aktivt eller Köat.

      - **Utdata**: Sökväg till det konverterade dokumentet. Om du klickar på länken Utdata kommer du till den plats där utdata sparas.


**Överordnat ämne:**[ Rapporter](reports-intro.md)
