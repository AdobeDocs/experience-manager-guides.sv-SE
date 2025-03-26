---
title: Återanvänd innehåll - rapport
description: Lär dig hur du visar rapporten om återanvändning av innehåll i AEM Guides. Generera rapporten för att hitta procentsatsen för återanvändning av innehåll.
exl-id: ccae4303-75b1-4077-829a-7ef6a14fd8ad
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Återanvänd innehåll - rapport {#id205BB900OQD}

En annan användbar rapport som du kan generera är återanvändningsrapporten för innehåll. Den här rapporten beräknar den genomsnittliga användningen av innehåll, vilket är mycket användbart för projektledare och affärsägare för att se hur mycket innehåll som återanvänds.

>[!TIP]
>
> För att återanvändningsrapporten för innehåll ska fungera på rätt sätt måste du aktivera efterbearbetningsarbetsflödet. Kontakta systemadministratören för att aktivera efterbearbetningsarbetsflöden.

Utför följande steg för att visa rapporten för återanvändning av innehåll:

1. Markera Adobe Experience Manager logotyp överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Markera rutan **Återanvänd rapport** för innehåll.

1. Välj **Bläddra** om du vill välja en sökväg där dina ämnen finns eller ange sökvägen manuellt.

   Rapporten skapas genom att innehållet i den överordnade och alla underordnade mappar genomsöks.

1. Välj **Generera rapport** för att hämta rapporten för återanvändning av innehåll.

   ![](images/content-reuse-uuid.png){align="left"}

   Rapportsidan är uppdelad i två delar:

   - **Rapportsammanfattning:**

     Visar en lista över genomsnittlig återanvändning av innehåll, som beräknas som Instansen för återanvändning av innehåll/totalt ämnesantal. Den här rapporten tar hänsyn till alla direkta innehållsreferenser på första nivån och ämnesreferenser för beräkning. Instanserna för återanvändning av innehåll beräknas som summan av värdena i fältet Antal gånger som återanvänds. Det ämne som återanvänds mest finns också med i rapportsammanfattningen. Om du markerar temats länk i avsnittet Senast återanvänt ämne öppnas ämnesens förhandsgranskning.

   - **Information:**

     Avsnittet Detaljer innehåller följande kolumner:

      - **Titel**: Ämnets namn. Om du väljer avsnittets titellänk öppnas ämnesförhandsvisningen.

      - **UID**: Den universellt unika identifieraren \(UUID\) för filen.

      - **Storlek**: Filstorleken i byte.

      - **Status**: Dokumentets aktuella status - Utkast, Under granskning eller Granskad.

      - **Antal gånger som återanvänds**: Antal gånger som motsvarande ämne har återanvänts. Detta beräknas som summan av posterna i Refererad av kolumner minus 1.

      - **Refererad av**: De ämnen i vilka motsvarande ämne har refererats. Här beaktas endast de direkta \(första nivån\) referenserna. Flera ämnen avgränsas med kommatecken. Den refererade filens UUID anges också inom parentes. Om du väljer ämneslänken öppnas ämnesförhandsvisningen.


>[!NOTE]
>
> Du kan också exportera återanvändningsrapporten för innehåll i CSV-format. Om du vill göra det väljer du Exportera till CSV-länk längst upp till vänster på skärmen och väljer en plats där du vill spara CSV-filen. Du kan sedan öppna den här CSV-filen i valfri CSV-redigerare.

**Överordnat ämne:**[ Introduktion till rapporter](reports-intro.md)
