---
title: Konfigurera generering av PDF för ett enskilt ämne
description: Lär dig hur du konfigurerar generering av enskilda ämnen i PDF
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Konfigurera generering av PDF för ett enskilt ämne {#id22ADC70M0XA}

Med AEM Guides kan du skapa PDF för enskilda ämnen eller en hel kartfil. Du kan publicera ämnen i PDF-format med den inbyggda PDF- eller DITA-OT-metoden. Använd inbyggd PDF-metod för att generera funktionsrika utdata för PDF baserat på W3C CSS3 och CSS-sidindelad mediestandard. Du kan använda metoden DITA-OT för att generera utdata från PDF för en karta från kontrollpanelen för kartan.

>[!NOTE]
>
> Native PDF är standardmetoden för att skapa en PDF i den aktuella versionen av AEM Guides.

Så här aktiverar du den gamla PDF-genereringen via DITA-OT i läget för ämnesförhandsgranskning:

1. Logga in på Adobe Experience Manager som administratör och hämta UI-konfigurationsfilen.

1. Det gör du genom att klicka på länken Adobe Experience Manager överst och välja **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **Konfiguration av XML-redigerare** och klicka på ikonen **Redigera** överst
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
1. Sök efter följande konfiguration i filen `ui_config.json`:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   och ersätta den med

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Spara filen och överför den.

När du har utfört stegen ovan och väljer samma mappprofil i Användarinställningar i Web Editor visas alternativet för generering av PDF i ett ämnes förhandsgranskningsläge.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
