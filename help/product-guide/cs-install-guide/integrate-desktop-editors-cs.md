---
title: Integrera skrivbordsbaserade XML-redigerare
description: Lär dig integrera skrivbordsbaserade XML-redigerare
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---

# Integrera skrivbordsbaserade XML-redigerare

Det finns många XML-redigerare på marknaden och du skulle kunna använda en redan. Adobe FrameMaker är en av de kraftfullaste XML-redigeringsprogrammen som medföljer AEM Connector. Med AEM Connector i FrameMaker kan du enkelt ansluta till AEM-databasen, checka ut och in filer samt redigera filer direkt i FrameMaker. Du kan också konfigurera Experience Manager Guides så att FrameMaker startas från Web Editor. När du har öppnat filen i FrameMaker kan du redigera och checka in den i AEM-databasen igen.

## Aktivera filredigering i FrameMaker från Web Editor

Du kan använda FrameMaker eller någon annan DITA-redigerare för att skapa och uppdatera DITA-innehåll. Men om ni använder FrameMaker som DITA-redigerare kan ni ge användarna möjlighet att öppna DITA-dokument direkt i FrameMaker från AEM.


Som standard visas inte knappen **Öppna i FrameMaker** i AEM verktygsfält. Gör så här för att lägga till den här knappen i verktygsfältet i AEM:

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att lägga till den här knappen i verktygsfältet i AEM:


| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Boolean \(true/false\). Om du vill visa knappen **Öppna i FrameMaker** anger du den här egenskapen till true. <br> **Standardvärde**: false |



Om du använder version 2409 och FrameMaker 2022 från september - uppdatering 3, måste du aktivera konfigurationen **FrameMaker version 2022 uppdatering 3 eller senare** så att dina användare kan skicka information om Experience Manager Guides-servern till FrameMaker.  Som standard är den inaktiverad.


| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Boolean \(true/false\). Om du använder FrameMaker version 2022 från september - uppdatering 3 anger du den här egenskapen som true. <br> **Standardvärde**: false |



När du anger egenskapen *openinframeButtonShow* till true visas knappen **Öppna i FrameMaker** när du väljer en DITA-fil i AEM-databasen. När den här egenskapen inte är inställd på *true* visas knappen **Öppna i FrameMaker** bara när du väljer en .fm- eller .book-fil i databasen.
