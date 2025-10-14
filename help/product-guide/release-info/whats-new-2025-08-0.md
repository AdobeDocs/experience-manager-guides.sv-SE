---
title: Versionsinformation | Nyheter i Adobe Experience Manager Guides 2025.08.0
description: Läs om de nya och förbättrade funktionerna i version 2025.08.0 av Adobe Experience Manager Guides
role: Leader
exl-id: c3461d0a-6394-4275-9d54-b2b1545d7c18
source-git-commit: 1a44af3522060ebc531393d4d01b1cd00eb02c10
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 0%

---

# Nyheter i version 2025.08.0 (augusti 2025)

I den här artikeln beskrivs de nya och förbättrade funktionerna som introducerades i version 2025.08.0 av Adobe Experience Manager Guides as a Cloud Service.

En lista över problem som har åtgärdats i den här versionen finns i [Åtgärdade problem i version 2025.08.0](fixed-issues-2025-08-0.md).

Läs mer om [uppgraderingsinstruktioner för version 2025.08.0](../release-info/upgrade-instructions-2025-08-0.md).


## Förbättrat granskningsflöde

I den här versionen har granskningsflödet förbättrats avsevärt för att ge bättre stöd för smidig kommunikation mellan författare och granskare. Viktiga uppdateringar är:

- Arbetsflöden för uppgiftshantering med åtgärdbara meddelanden
- Möjlighet att tagga användare för att omedelbart söka uppmärksamhet
- Åtkomst till projekt- och uppgiftsinformation från granskningspanelen för enkel användning

Med dessa förbättringar kan man nu förvänta sig:

- Effektiva granskningsrundor i rätt tid
- Minskad manuell insats vid utbyte av feedback

Mer information finns i [Introduktion till granskning](../user-guide/review.md)

## Konfigurerbara AI Assistant-åtgärder i redigeringsinställningarna

I den senaste uppdateringen introduceras förbättrad konfiguration för **redigering av snabbåtgärder** i AI Assistant, vilket gör att administratörer kan anpassa redigeringsmiljön efter specifika arbetsflöden och inställningar.

När växlingsknappen **AI Assistant** är aktiverad kan administratörer välja vilka snabbåtgärder som ska vara synliga under fliken **Redigering**, vilket underlättar redigeringsinteraktionen. Dessa synlighetsinställningar är specifika för varje mappprofil.

Läs mer om [AI-assistenten i redigeringsinställningarna](../cs-install-guide/workspace-settings.md#general) i Experience Manager Guides.

![](assets/authoring-quick-actions.png){width="350" align="left"}


## Förbättrad upplevelse för att skapa och använda DITAVAL-filer

Uppdateringen innehåller flera förbättringar som gör det enklare att skapa, hantera och använda DITAVAL-filer, vilket ger bättre kontroll över villkorat innehåll och format i olika utdataformat.

De viktigaste högdagrarna är följande:

- **Förbättrat stöd för flaggning i redigering av DITAVAL-filer:** Experience Manager Guides har nya funktioner för anpassning av innehållspublicering tack vare utökat stöd för flaggning i DITAVAL-filer. Du kan nu lägga till start- och slutflaggor runt visst innehåll, inklusive bilder, och utöka flaggade avsnitt med formateringsalternativ som fet, kursiv stil och mycket annat. Om du vill hantera villkorsöverlappningar kan du konfigurera **formatkonflikten**, som bland annat anger en standardbakgrund och en standardtextfärg, vilket ger tydlighet och enhetlighet i utdata. Dessa flaggor stöds fullt ut i PDF-generering, och resultatet återger alla använda formatelement korrekt och fullständigt.
Mer information finns i [Använd DITAVAL-redigeraren](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Flera DITAVAL-filer har stöd för PDF:** För PDF kan nu flera DITAVAL-filer läggas till, som visas som en taggad post för enkel identifiering och borttagning, vilket ger större flexibilitet och kontroll över villkorat innehåll i PDF-utdata

  Uppdateringen förbättrar dessutom framtagningen av förinställningar för utdata genom att aktivera redigerbara DITAVAL-fält i olika format, så att användarna kan ange DITAVAL-sökvägar manuellt.

  Mer information finns i [Förstå förinställningarna](../user-guide/generate-output-understand-presets.md) i Experience Manager Guides.

## Förbättrad loggfiltrering för generering av utdata

Den här versionen har förbättrat användargränssnittet för loggfiltrering av utdatagenerering. Du kan nu filtrera loggarna för utdatagenerering bättre för alla fyra distinkta nivåer: **Info**, **Warn**, **Error** (inklusive både fel och undantag) och **Fatal** med förbättrade och intuitiva färgkodade indikatorer som förenklar analys och skärpesynlighet i loggströmmen. Denna förbättring gör att du kan navigera i loggarna mer effektivt och hitta de kritiska problemen med precision.

Mer information finns i [Grundläggande felsökning](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


## Tillfälliga filer för publicerade utdata inkluderar nu författar- och publicerings-URL:er i en ny konfigurationsfil

De senaste publiceringsförbättringarna av Experience Manager Guides lägger nu till en ny `system_config.xml`-fil till de temporära filer som genereras när HTML-, PDF- och JSON-utdata publiceras med DITA-OT, liksom utdata från PDF. Den här filen inkluderas automatiskt i publiceringsjobbet och är även tillgänglig via temporära filer när du aktiverar alternativet **Behåll temporära filer** för förinställningarna och genererar utdata.

Filen `system_config.xml` innehåller information om AEM-instanser, inklusive författar-URL, lokal URL och publicerings-URL, som ger tydligare kontext och förbättrar spårbarheten för hämtade URL:er.

Mer information finns i [Förstå förinställningarna](../user-guide/generate-output-understand-presets.md).

## Nytt stöd för variabeln output path för generering av utdata

I den här uppdateringen introduceras dynamisk `output path`-konfiguration för utdataförinställningar som PDF, DITA-OT PDF, JSON, HTML5 och Custom. I stället för att använda en fast sökväg kan användare nu definiera utdataplatsen med variabeln `${base_output_path}` under installationen, vilket ger större flexibilitet. Den tidigare standardsökvägen `/content/dam/fmdita-outputs` är inte längre obligatorisk.

Alla utdatasökvägar som är associerade med förinställningarna för den globala mappprofilen migreras automatiskt så att den nya basvariabeln för utdatasökväg används. För anpassade mappprofiler är dock migreringen inte automatisk. Du rekommenderas att kontakta Customer Success-teamet för att få hjälp.

Mer information finns i [Förstå förinställningarna](../user-guide/generate-output-understand-presets.md).

## Förbättringar av användargränssnittet i redigerarens verktygsfält och användarinställningar

I den här versionen har inställningarna på **användarinställningarna** på startsidan för flikarna Allmänt och Utseende omstrukturerats. Det innebär att etiketten **Öppnar inställningar för Kartor** byts namn och att växlingen för hårda blanksteg flyttas till redigerarens verktygsfält.

I redigerarens verktygsfält finns dessutom några snabbredigeringsreglage för att aktivera eller inaktivera Spåra ändringar, Taggar och Ej brytande mellanslag nu grupperade under alternativet **Visa** i menylistrutan för bättre användbarhet.

Mer information finns i [Verktygsfältet i redigeraren](../user-guide/web-editor-toolbar.md#menu-dropdown).
