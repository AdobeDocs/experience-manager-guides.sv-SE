---
title: Återanvänd innehåll - rapport
description: Lär dig hur du visar rapporten om återanvändning av innehåll i AEM Guides. Generera rapporten för att hitta procentsatsen för återanvändning av innehåll.
feature: Report Generation
role: User
hide: true
exl-id: 1a61fc05-b2b4-4665-a15a-0058fbbc2942
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Återanvänd innehåll - rapport {#id205BB900OQD}

En annan användbar rapport som du kan generera är återanvändningsrapporten för innehåll. Den här rapporten beräknar den genomsnittliga användningen av innehåll, vilket är mycket användbart för projektledare och affärsägare för att se hur mycket innehåll som återanvänds.

>[!TIP]
>
> För att återanvändningsrapporten för innehåll ska fungera på rätt sätt måste du aktivera efterbearbetningsarbetsflödet. Kontakta systemadministratören för att aktivera efterbearbetningsarbetsflöden.

Utför följande steg för att visa rapporten för återanvändning av innehåll:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.

1. Välj **Stödlinjer** i listan över verktyg.

1. Klicka på rutan **Återanvänd rapport** för innehåll.

1. Klicka på **Bläddra** om du vill välja en sökväg där dina ämnen finns eller ange sökvägen manuellt.

   Rapporten skapas genom att innehållet i den överordnade och alla underordnade mappar genomsöks.

1. Klicka på **Generera rapport** för att hämta rapporten för återanvändning av innehåll.

   ![](images/content-reuse-uuid.png){width="800" align="left"}

   Rapportsidan är uppdelad i två delar:

   - **Rapportsammanfattning:**

     Visar en lista över genomsnittlig återanvändning av innehåll, som beräknas som Instansen för återanvändning av innehåll/totalt ämnesantal. Den här rapporten tar hänsyn till alla direkta innehållsreferenser på första nivån och ämnesreferenser för beräkning. Instanserna för återanvändning av innehåll beräknas som summan av värdena i fältet Antal gånger som återanvänds. Det ämne som återanvänds mest finns också med i rapportsammanfattningen. Om du klickar på ämneslänken i det mest återanvända ämnet öppnas ämnesens förhandsgranskning.

   - **Information:**

     Avsnittet Detaljer innehåller följande kolumner:

      - **Titel**: Ämnets namn. Om du klickar på ämneslänken öppnas ämnesförhandsgranskningen.

      - **UID**: Den universellt unika identifieraren \(UUID\) för filen.

      - **Storlek**: Filstorleken i byte.

      - **Status**: Dokumentets aktuella status - Utkast, Under granskning eller Granskad.

      - **Antal gånger som återanvänds**: Antal gånger som motsvarande ämne har återanvänts. Detta beräknas som summan av posterna i Refererad av kolumner minus 1.

      - **Refererad av**: De ämnen i vilka motsvarande ämne har refererats. Här beaktas endast de direkta \(första nivån\) referenserna. Flera ämnen avgränsas med kommatecken. UUID för den refererade filen anges också i parenteser. Om du klickar på avsnittets titellänk öppnas ämnesförhandsvisningen.


>[!NOTE]
>
> Du kan också exportera återanvändningsrapporten för innehåll i CSV-format. Klicka på länken Exportera till CSV längst upp till vänster på skärmen och välj en plats där du vill spara CSV-filen. Du kan sedan öppna den här CSV-filen i valfri CSV-redigerare.

**Överordnat ämne:**[ Rapporter](reports-intro.md)
