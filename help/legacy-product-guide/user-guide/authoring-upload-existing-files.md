---
title: Överför filer
description: Lär dig hur du överför filer till AEM-databasen och hanterar fel. Lär dig konsolens användargränssnitt, AEM-datorprogram, massinhämtning av resurser och använd FrameMaker för massöverföring.
feature: Content Management
role: User
hide: true
exl-id: fcb2cc43-6a36-42f2-a695-7a50ae1031a0
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# Överför filer {#id176FF000JUI}

Troligen har du en databas med befintligt DITA-innehåll som du vill använda med AEM Guides. För sådant befintligt innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till AEM-databasen:

>[!IMPORTANT]
>
> Se [Lägga till digitala resurser i Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE) för mer information om de innehållsöverföringsmetoder som stöds i AEM.

## Användargränssnittet i Assets Console

Du kan markera innehåll på skrivbordet och dra AEM användargränssnitt \(webbläsare\) till målmappen. Mer information finns i [Överför resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE#upload-assets) i AEM-dokumentationen.

## AEM datorprogram

Använd AEM datorprogram om du är kreatör och vill hantera mediefiler på din dator. Du kan öppna och redigera dessa resurser med skrivbordsprogrammen. Du kan också underhålla versioner och dela filer med andra användare. Mer information finns i [AEM-datorprogrammet](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=sv-SE).

## Massinhämtning av resurser

Om du har storskalig migrering och ibland massimporteringar använder du Resursimport för att överföra ditt innehåll. Med det här verktyget kan du överföra massinnehåll från datalager som stöds, som Azure eller S3. Mer information finns i [Massinhämtning av resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE#asset-bulk-ingestor).

## Använd FrameMaker för massöverföring

Adobe FrameMaker har en kraftfull AEM-anslutning som gör att du enkelt kan överföra dina befintliga DITA-dokument och andra FrameMaker-dokument \(`.book` och `.fm`\) till AEM. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Mer information om hur du använder massöverföring i FrameMaker finns i avsnittet *Skapa en CRX-mapp och överföra filer* i användarhandboken för FrameMaker.

## Felhantering vid överföring av innehåll {#id201MI0I04Y4}

Om det inte går att överföra en eller flera filer visas ett meddelande i slutet av överföringsprocessen med en lista över filer som inte kunde överföras:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Mer information om hur de olika scenarierna för filöverföring beskrivs i [Överför DITA-innehåll](authoring-file-management.md#).

Om du använder ett verktyg som AEM-skrivbordsprogram eller Resursprogram, styrs åtgärden som utförs på en duplicerad fil av en inställning på AEM-servern. Kontakta systemadministratören om du vill veta mer om den här konfigurationen.

**Överordnat ämne:**&#x200B;[ Hantera innehåll](authoring.md)
