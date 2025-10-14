---
title: Överför filer
description: Lär dig hur du överför filer till AEM-databasen och hanterar fel. Lär dig konsolens användargränssnitt, AEM-datorprogram, massinhämtning av resurser och använd FrameMaker för massöverföring.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: 0259c0c0b7270d860198f17e6ea5f5829df038d5
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Överför filer {#id176FF000JUI}

Troligen har du en databas med befintligt DITA-innehåll som du vill använda med Adobe Experience Manager Guides. Om du har sådant innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till Adobe Experience Manager-databasen.

>[!IMPORTANT]
>
> Visa [Lägg till digitala resurser i Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE) om du vill ha mer information om de innehållsöverföringsmetoder som stöds i Adobe Experience Manager.

## Användargränssnittet i Assets Console

Om du vill [lägga till digitala resurser i Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE#filename-handling?lang=sv-SE#upload-assets) med användargränssnittet i Assets Console markerar du den önskade resursen på skrivbordet och drar i Adobe Experience Manager användargränssnitt \(webbläsare\) till målmappen. När du överför resurser ska du se till att filnamnen inte innehåller tecken som inte stöds eller inte tillåts.

Mer information finns i avsnittet [Filnamnshantering och förbjudna tecken](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE#filename-handling) i Adobe Experience Manager-dokumentationen.

## Adobe Experience Manager datorprogram

Använd Adobe Experience Manager datorprogram om du är kreatör och vill hantera mediefiler på din dator. Du kan öppna och redigera dessa resurser med skrivbordsprogrammen. Du kan också underhålla versioner och dela filer med andra användare. Mer information finns i [Adobe Experience Manager-datorprogrammet](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=sv-SE).

## Massinhämtning av resurser

Om du har storskalig migrering och ibland massimporteringar använder du Resursimport för att överföra ditt innehåll. Med det här verktyget kan du överföra massinnehåll från datalager som stöds, som Azure eller S3. Mer information finns i [Massinhämtning av resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE#asset-bulk-ingestor).

## Använd FrameMaker för massöverföring

Adobe FrameMaker har en kraftfull Adobe Experience Manager-anslutning som gör att du enkelt kan överföra dina befintliga DITA-dokument och andra FrameMaker-dokument \(`.book` och `.fm`\) till Adobe Experience Manager. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Mer information om hur du använder massöverföring i FrameMaker finns i avsnittet *Skapa en CRX-mapp och överföra filer* i FrameMaker användarhandbok.

## Felhantering vid överföring av innehåll {#id201MI0I04Y4}

Om det inte går att överföra en eller flera filer visas ett meddelande i slutet av överföringsprocessen med en lista över filer som inte gick att överföra enligt utdraget nedan.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Mer information om hur de olika scenarierna för filöverföring fungerar finns i [Hantera filer och mappar](authoring-file-management.md#).

Om du använder ett verktyg som Adobe Experience Manager-skrivbordsprogram eller Resursprogram, styrs åtgärden som utförs på en duplicerad fil av en inställning på Adobe Experience Manager-servern. Kontakta systemadministratören om du vill veta mer om den här konfigurationen.

**Överordnat ämne:**&#x200B;[&#x200B; Hantera innehåll](authoring.md)
