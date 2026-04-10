---
title: Konfigurera rubrik för ikonerna för att checka in och checka ut
description: Lär dig hur du konfigurerar titeln för ikoner för in- och utcheckning
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Konfigurera titeln för ikonerna Checka in och Checka ut för lokal installation

I AEM Guides kan du konfigurera titeln för ikonerna Checka in och Checka ut i webbredigeraren. Följ de här stegen för att konfigurera titeln för ikonerna Checka in och Checka ut:

1. Hämta UI-konfigurationsfilen genom att logga in i Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Välj fliken **XML-redigerarkonfiguration** och klicka på ikonen **Redigera** överst.
1. Klicka på ikonen **Hämta** i **gränssnittskonfigurationen för XML-redigeraren** för att hämta filen `ui_config.json` på din lokala dator.
1. I filen `ui_config.json` ändrar du titeln i avsnittet &quot;topbar&quot;. Du kan ändra följande värden:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Spara filen och överför den.
