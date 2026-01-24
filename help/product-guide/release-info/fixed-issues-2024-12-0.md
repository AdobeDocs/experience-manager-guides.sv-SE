---
title: Versionsinformation | Korrigerade problem i version 2024.12.0 av Adobe Experience Manager Guides
description: Läs mer om felkorrigeringarna i version 2024.12.0 av Adobe Experience Manager Guides as a Cloud Service.
exl-id: 04a57e1a-6e74-46f6-acde-5045d3dcacdc
source-git-commit: dd404c42863f0b4a5f31b54f770c0bf296d68ab9
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# Problem i version 2024.12.0 har korrigerats

Den här artikeln handlar om buggar som har åtgärdats i olika delar av version 2024.12.0 av Adobe Experience Manager Guides as a Cloud Service.

Läs mer om [uppgraderingsinstruktioner för version 2024.12.0](./upgrade-instructions-2024-12-0.md).

## Redigering

- Det går inte att skapa DITA-kartor på en UUID-instans när `xmleditor.uniquefilenames` är aktiverat i `XMLEditorConfig`. (21201)
- När du stänger en fil sparas inte kommentarer och etiketter som lagts till i dialogrutan **Spara ändringar och Lås upp fil** i versionshistoriken med den nya versionen. Detta gäller ett användningsfall där **Fråga efter incheckning vid stängning** eller **Fråga efter ny version vid stängning** är aktiverat i `XMLEditorConfig`. (20065)
- Dokumentläget markerat som **Klar** återgår till **Utkast** innan en ny version sparas, vilket resulterar i att läget **Klar** inte bevaras i någon dokumentversion. (2006)
- Det går inte att lägga till en PDF-fil som bildreferens i ett avsnitt i Web Editor. (21206)
- Om du väljer en DITA-fil i Assets-gränssnittet visas alternativet **Öppna i FrameMaker**, även om det är inaktiverat i konfigurationen. (20082)

## Publicering

- I utdata från PDF saknas kapitelrubriker i innehållsförteckningen, vilket leder till en felaktig hierarki. (21840)


## Förvaltning

- Resursläckor inträffar på grund av **oavslutade ResourceResolver**-fel i loggar. 18488
- När du skapar en ny eller duplicerad baslinje visas etiketterna i slumpmässig ordning. (19307)


## Baslinje

- Om baslinjen har ett stort antal ämnen eller kartor kan du redigera och sedan spara en baslinje i en molnkonfiguration efter 1 minut. (19558)

## Översättning

- Omvandling av kartor med baslinje blir långsam och kan inte läsa in listan över alla associerade ämnen och kartor. (19733)

## Kända problem med lösningar

Adobe har identifierat följande kända problem i version 2024.12.0 av Adobe Experience Manager Guides as a Cloud Service.

**Det går inte att skapa projekt när innehållsöversättning bearbetas**

När du skickar innehåll för översättning misslyckas projektskapandet med följande loggfel:

`com.adobe.cq.wcm.translation.impl.TranslationPrepareResource` Fel vid bearbetning av översättningsprojekt

`com.adobe.cq.projects.api.ProjectException`: Det går inte att skapa projektet

Orsakad av: `org.apache.jackrabbit.oak.api.CommitFailedException`: `OakAccess0000`: Åtkomst nekad


**Tillfällig lösning**: Utför följande steg för att lösa problemet:

1. Lägg till en repoinit-fil. Om filen inte finns skapar du filen genom att utföra stegen [för att skapa konfigurationen för referenspunkter](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-cloud-questions/repoinit-configuration-for-property-set-on-aem-as-cloud-service/m-p/438854?profile.language=sv).
2. Lägg till följande rad i filen och distribuera koden:

   ```
   { "scripts": [ "set principal ACL for translation-job-service\n allow jcr:all on /home/users/system/cq:services/internal/translation\nend" ] }
   ```

3. Testa översättningen efter distributionen.

