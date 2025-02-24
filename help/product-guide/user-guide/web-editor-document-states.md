---
title: Dokumenttillstånd
description: Lär dig olika typer av dokumentlägen i Adobe Experience Manager Guides. Lär dig hur du ändrar eller visar dokumentläget och använder dokumentläget i DDLC.
exl-id: 3a68b2ed-b917-4f05-8b2b-d2722a740502
feature: Authoring, Features of Web Editor, Document State
role: User
source-git-commit: b8f3756e0e8f0338942efb77f00600703be8f6d8
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Dokumenttillstånd {#id1821HC00URO}

För att hantera dokumentens beredskap tillhandahåller Adobe Experience Manager Guides en dokumentlägesegenskap som anger dokumentets aktuella tillstånd. Med dokumentlägen kan du snabbt ta reda på om ett dokument är nytt, håller på att granskas eller granskas som färdigt.

## Typer av dokumentlägen

Ett dokument kan ha något av dokumenttillstånden definierade i profilen **Dokumenttillstånd** . Ett dokument kan till exempel ha något av följande dokumentlägen:

- Utkast - Anger att dokumentet har skapats och sparats med nya ändringar.
- Granskning - Anger att ett granskningsarbetsflöde har initierats för dokumentet.
- Granskad - Anger att dokumentet har granskats av de avsedda användarna.

Dessa lägen ställs in manuellt eller automatiskt enligt dokumentlägesprofilinställningarna. Om dokumentets tillståndsprofil till exempel är konfigurerad med startläge som Utkast och läget Under granskning är definierat för dokument som granskas. När du sedan skapar ett dokument ställs dokumentläget in på *Utkast*. Om du initierar en granskningsåtgärd ändras dokumentets status till Under granskning.

Du kan också ändra dokumentläget manuellt för ett eller flera dokument. Om du väljer att ändra dokumentläget för flera dokument bestäms emellertid det tillåtna läget av de gemensamma lägena som är tillåtna för de markerade dokumenten. Anta att du har definierat dokumentlägena som Utkast, Granskning, Granskad och Klart att publicera i samma ordning. I dokument ett.dita är läget inställt på *Utkast* och i dokument två.dita är läget inställt på Granskad. När du väljer både one.dita och two.dita blir det tillåtna dokumentläget *Klar att publicera*. Eftersom läget two.dita är i läget *Granskad* är nästa möjliga läge för two.dita bara *Klar att publicera*, som visas när båda dokumenten är markerade.

>[!NOTE]
>
> Ett dokument kan bara finnas i ett läge åt gången.

## Ändra dokumentstatus från Redigeraren

Så här ändrar du ett dokuments status:

1. Öppna dokumentet i Redigeraren och välj sedan File-egenskaper i den högra panelen.
1. Välj det nya läget i listrutan **Dokumentläge** på panelen File-egenskaper. Du kan bara markera de dokumentlägen som är tillåtna i avsnittet Tillståndsövergång i dokumentlägesprofilen.

   >[!NOTE]
   >
   >Administratörer kan visa alla dokumentlägen och ändra dokumentet till valfritt läge.

1. Välj **Spara** i bekräftelserutan.

## Ändra dokumentstatus från Assets användargränssnitt

1. I Assets-gränssnittet markerar du ett eller flera dokument som du vill ändra dokumentstatus för.
1. Välj **Egenskaper** i huvudverktygsfältet.
1. Välj det nya läget i listrutan **Dokumenttillstånd**. Du kan bara markera de dokumentlägen som är tillåtna i avsnittet Tillståndsövergång i dokumentlägesprofilen.

   >[!NOTE]
   >
   >Administratörer kan visa alla dokumentlägen och ändra dokumentet till valfritt läge.

1. Välj **Spara och stäng**.

### Visa dokumentläge

Kortvyn i Assets UI visar det aktuella läget tillsammans med datum och storlek för när respektive DITA-avsnitt eller DITA-karta skapades.

![](images/document_state.png){width="800" align="left"}

## Använd dokumentlägen i DDLC

Dokumenttillstånd spelar en viktig roll när det gäller att hantera dokumentens livscykel i DDLC. Om organisationen följer DDLC:n strikt blir det en viktig funktion att ha en funktion för att styra redigering av dokument baserat på deras tillstånd. Du kan till exempel tillåta redigering av dokument när de är i läget *Utkast* eller *Under granskning* . När ett dokument har granskats och är klart att publiceras bör det dock finnas ett sätt att förhindra ytterligare ändringar av dokumentet.

Experience Manager Guides tillhandahåller ett arbetsflöde för dokumentgodkännande som hjälper dig att styra dokumentutvecklingsprocessens livscykel. När ett dokument är klart att publiceras eller har nått det näst sista läget kan du markera det som godkänt. När ett dokument har godkänts skapar Experience Manager Guides en ny version av dokumentet och gör det skrivskyddat. Du kan sedan flytta dokumentet för publicering eller skapa en baslinje för vidare bearbetning.

Om du vill starta ett nytt releaseformulär för de dokument som har markerats som godkända måste en författare starta en ny release. Om du startar en ny version ändras dokumentläget till *Utkast* igen. Genom att ändra dokumentläget till *Utkast* kan dokumentet redigeras igen och du kan fortsätta arbeta med nästa version.

Så här använder du funktionen för dokumentgodkännande:

>[!NOTE]
>
> Arbetsflödesfunktionen för godkännande måste aktiveras av administratören. Mer information finns i avsnittet *Aktivera arbetsflöde för godkännande* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

1. Öppna det dokument som du vill markera för godkännande i Editor.

1. Välj ikonen **Markera som godkänd**![](images/mark_approve_icon.svg).

1. Om dokumentet är i ett läge som ska markeras som godkänt visas följande dialogruta:

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   Om dokumentet inte kan markeras som godkänt visas följande meddelande:

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. Om dokumentet är klart att markeras som godkänt väljer du en etikett i listrutan och väljer **Godkänn**.

   >[!NOTE]
   >
   > Om administratören inte har konfigurerat en fördefinierad lista med etiketter visas ett friformstextfält där du kan ange en etikett.

1. När dokumentet har markerats som godkänt visas en **förhandsgranskning** av dokumentet i skrivskyddat läge. Alla redigeringsalternativ tas bort från alla tre lägena - Författare, Source och Förhandsgranska. Du får dock fortfarande tillgång till listrutan **Meny** med alternativen **Versionshistorik** och **Taggar** .

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > I förhandsgranskningsläget har listrutan Meny med versionshistorik och taggalternativ tagits bort från verktygsfältet.


När ett dokument har markerats som godkänt går det inte längre att redigera. Om du vill använda dokumentet för nästa version måste du återställa det till läget *Utkast*. Så här ändrar du dokumentläget för ett godkänt dokument till läget *Utkast*:

1. I ett godkänt dokument väljer du ikonen **Starta en ny version** ![](images/approved-restart-draft-mode-icon.svg) .

   Meddelandet Starta ny release visas.

1. Välj **Bekräfta**.

   Dokumentets läge ändras till Utkast och dokumentet öppnas i Redigeraren i redigeringsläge.


**Överordnat ämne:**[ Introduktion till redigeraren](web-editor.md)
