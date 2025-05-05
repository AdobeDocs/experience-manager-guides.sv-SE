---
title: Överför filer
description: Lär dig hur du överför filer till AEM-databasen och hanterar fel. Lär dig konsolens användargränssnitt, AEM-datorprogram, massinhämtning av resurser och använd FrameMaker för massöverföring.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: f3858b1694837c7a3fa7bb222ed8ff31ce7103f8
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Överför filer {#id176FF000JUI}

Troligen har du en databas med befintligt DITA-innehåll som du vill använda med Adobe Experience Manager Guides. Om du har sådant innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till Adobe Experience Manager-databasen.

>[!IMPORTANT]
>
> Visa [Lägg till digitala resurser i Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) om du vill ha mer information om de innehållsöverföringsmetoder som stöds i Adobe Experience Manager.

## Användargränssnittet i Assets Console

Du kan markera innehåll på skrivbordet och dra Adobe Experience Manager användargränssnitt \(webbläsare\) till målmappen. Mer information finns i [Överför resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) i Adobe Experience Manager-dokumentationen.

## Adobe Experience Manager datorprogram

Använd Adobe Experience Manager datorprogram om du är kreatör och vill hantera mediefiler på din dator. Du kan öppna och redigera dessa resurser med skrivbordsprogrammen. Du kan också underhålla versioner och dela filer med andra användare. Mer information finns i [Adobe Experience Manager-datorprogrammet](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Massinhämtning av resurser

Om du har storskalig migrering och ibland massimporteringar använder du Resursimport för att överföra ditt innehåll. Med det här verktyget kan du överföra massinnehåll från datalager som stöds, som Azure eller S3. Mer information finns i [Massinhämtning av resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Använd FrameMaker för massöverföring

Adobe FrameMaker har en kraftfull Adobe Experience Manager-anslutning som gör att du enkelt kan överföra dina befintliga DITA-dokument och andra FrameMaker-dokument \(`.book` och `.fm`\) till Adobe Experience Manager. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Mer information om hur du använder massöverföring i FrameMaker finns i avsnittet *Skapa en CRX-mapp och överföra filer* i FrameMaker användarhandbok.

## Felhantering vid överföring av innehåll {#id201MI0I04Y4}

Om det inte går att överföra en eller flera filer visas ett meddelande i slutet av överföringsprocessen med en lista över filer som inte gick att överföra enligt utdraget nedan.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Mer information om hur de olika scenarierna för filöverföring fungerar finns i [Hantera filer och mappar](authoring-file-management.md#).

Om du använder ett verktyg som Adobe Experience Manager-skrivbordsprogram eller Resursprogram, styrs åtgärden som utförs på en duplicerad fil av en inställning på Adobe Experience Manager-servern. Kontakta systemadministratören om du vill veta mer om den här konfigurationen.

**Överordnat ämne:**&#x200B;[ Hantera innehåll](authoring.md)
