---
title: Konfigurera dokumentlägen
description: Lär dig hur du konfigurerar dokumenttillstånd
exl-id: ab155879-4472-464d-ab25-6075088d718b
feature: Document State
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Konfigurera dokumentlägen {#id181GB0400UI}

Med AEM Guides kan du definiera dokumenttillstånd för dina DITA-ämnen enligt organisationens krav. Du kan definiera olika lägen för dokumentet från början till slut. Det första läget kan till exempel vara Utkast och det kan gå till Granskning, Godkänd, Översatt och slutligen Publicerad.

Det finns två sätt som ett ämne kan övergå från ett läge till ett annat - manuellt och automatiskt. Dokumentlägena som definieras i en profil kan användas för att manuellt ändra dokumentläget. Detta kan du göra på egenskapssidan för en ämnesfil. Du kan också definiera vem som kan flytta dokumentet från ett läge till ett annat. En författare kan t.ex. skapa ett dokument och standardläget för dokumentet kan vara Utkast. När författaren skickar dokumentet för granskning kan hon ändra dokumentläget till Granskning. Granskaren kan ändra dokumentstatus till Godkänd eller Utkast igen baserat på granskningsprocessen. Om dokumentet är godkänt kan utgivaren ändra dokumentläget till Översatt eller Publicerat beroende på arbetsflödet.

>[!NOTE]
>
> Om en användare tillhör gruppen *administratörer* kan användaren ändra ett dokuments tillstånd från vilket läge som helst, oavsett vilka dokumenttillståndsövergångar som har definierats i systemet.

## Skapa ett dokumentläge

AEM Guides levereras med en uppsättning standarddokumenttillstånd. Dessa lägen är:

- Utkast
- Redigera
- Granskning
- Godkänd
- Granskad
- Klar

Dessa standardlägen är tillgängliga för alla DITA-ämnen som skapas under DAM. Du kan skapa egna dokumentlägen och tilldela dem till en viss mapp. Alla DITA-filer som skapas under den mappen har sedan åtkomst till de nya dokumenttillstånden.

Så här skapar du dokumentlägen med hjälp av Mappprofil:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg.
1. Klicka på panelen Dokumentlägen.

   Sidan Lägen i Assets visas. Som standard visas en standardprofil på sidan.

1. Klicka på **Skapa profil** och ange följande information:
   - Ange profilens namn i fältet Profil.
   - Ange den sökväg där du vill använda den nya profilen.
   - Ange dokumentets lägen i **Tillåtna lägen** under **Lägen**. Standarddokumentlägena är Utkast, Redigera, Under granskning, Godkänd och Klar.-

     Klicka på knappen **Lägg till** om du vill lägga till ett dokumentläge.

      - Klicka på ikonen Ta bort om du vill ta bort ett dokumentläge.

     >[!NOTE]
     >
     > Ta inte bort ett dokumentläge om dokumenten fortfarande är i det läget. Om du tar bort ett dokumenttillstånd kan du inte ändra dokumenttillståndet för sådana dokument såvida du inte tillhör användargruppen *administrator* .

   - Ange startstatus för dokumentet i **Startläge**.
   - Ange slutläget för dokumentet i **slutläget**.
   - Ange dokumentets lägesövergång i **Från** och **Till** under **Lägesövergång**.

      - Ange de användare och användargrupper som kan ändra dokumenttillståndet i **Grupper**.

      - Klicka på knappen **Lägg till** för att lägga till en lägesövergång.

      - Klicka på ikonen Ta bort om du vill ta bort en lägesövergång.

     >[!NOTE]
     >
     > Ta inte bort en lägesövergång om dokumenten fortfarande är i läget `From`. Om du tar bort en lägesövergång kan du inte ändra dokumenttillståndet för sådana dokument såvida du inte tillhör användargruppen *administrator* .

1. Klicka på **Klar**.

## Skapa en kopia av en dokumenttillståndsprofil

Beroende på dina behov kan du skapa en kopia av en befintlig dokumenttillståndsprofil. Du kan använda kopian som bas när du skapar en annan dokumentprofil.

Så här skapar du en kopia av en dokumenttillståndsprofil:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg.
1. Klicka på panelen Dokumentlägen.

   Sidan Lägen i Assets visas.

1. Markera den dokumenttillståndsprofil som du vill duplicera och klicka på **Duplicera profil**.
1. Gör de ändringar som krävs och klicka på **Klar**.

## Ta bort ett dokumentläge eller en lägesövergång

>[!NOTE]
>
> Ta inte bort ett dokumentläge eller en lägesövergång om dokumenten fortfarande är i läget eller i lägesövergången. Om du tar bort ett läge eller en tillståndsövergång kan du inte ändra dokumenttillståndet för sådana dokument såvida du inte tillhör användargruppen *administrator* .

Så här tar du bort ett dokumentläge eller en lägesövergång från en dokumenttillståndsprofil:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg.
1. Klicka på panelen Dokumentlägen.

   Sidan Lägen i Assets visas.

1. Välj den dokumenttillståndsprofil från vilken du vill ta bort dokumentläget och klicka på **Redigera profil**.
1. Ta bort dokumentläget eller tillståndsövergången och klicka på **Klar**.

## Ta bort en dokumenttillståndsprofil

Så här tar du bort en dokumenttillståndsprofil:

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg.
1. Klicka på rutan **Dokumentlägen**.

   Sidan Lägen i Assets visas.

1. Markera den dokumenttillståndsprofil som du vill ta bort och klicka på **Ta bort profil**.

## Automatisera ändring av dokumentstatus

Om du inte vill ändra dokumentens tillstånd manuellt kan du skapa ett arbetsflöde och automatisera ändringen av dokumentets tillstånd.

>[!NOTE]
>
> Automatiska arbetsflöden ska följa de dokumenttillstånd och övergångar som definieras i konfigurationen. Systemet utför inga kontroller för lägesändringar som gjorts via automatiserade arbetsflöden.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Arbetsflöde** i listan över verktyg.

1. Klicka på rutan **Modeller**.

1. Välj arbetsflöde, till exempel Granska ämnen.

1. Klicka på **Redigera**.

   Arbetsflödet öppnas på en ny flik.

1. Klicka på **Redigera** \(övre högra\).

1. Öppna webbläsaren **Steg** och använd **växlingspanelen** längst till vänster i det övre verktygsfältet

1. Dra lämpliga steg till önskad plats i modellen.

1. Klicka på det nya steget som du lade till i arbetsflödesmodellen och välj **Konfigurera** i komponentverktygsfältet

1. Öppna fliken **Process**.

1. I listrutan **Process** väljer du **Ange dokumentstatus för en DAM-resurs**.

1. Välj alternativet **Avancerat för hanterare**.

   ![](assets/update-workflow-doc-state_cs.png)

1. I textrutan **Argument** anger du ett dokumenttillstånd som du vill övergå från det valda arbetsflödet till.

   >[!NOTE]
   >
   > Se till att du anger rätt dokumenttillstånd i textrutan Argument. Om du anger ett felaktigt värde ställs dokumentet in på ett felaktigt läge.

1. Bekräfta ändringen med **Spara och stäng**.


## Aktivera arbetsflöde för godkännande

AEM Guides tillhandahåller ett arbetsflöde för dokumentgodkännande som hjälper dig att styra dokumentutvecklingsprocessens livscykel. Så här aktiverar du arbetsflödet för godkännande:

1. Om du vill hämta UI-konfigurationsfilen loggar du in på Adobe Experience Manager som administratör.

1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. Aktivera arbetsflödesfunktionen för godkännande i filen `ui_config.json` genom att ändra avsnittet *features* enligt nedan:

   ```
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```

1. Spara filen och överför den.
