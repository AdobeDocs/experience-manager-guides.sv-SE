---
title: Konfigurera rubrik för ikonerna för att checka in och checka ut
description: Lär dig hur du konfigurerar titeln för ikoner för in- och utcheckning
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Konfigurera titeln för ikonerna Checka in och Checka ut

I AEM kan du konfigurera titeln för ikonerna Checka in och Checka ut i webbredigeraren. Följ de här stegen för att konfigurera titeln för ikonerna Checka in och Checka ut:

1. Hämta UI-konfigurationsfilen genom att logga in i Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **verktyg**.
1. Välj **Stödlinjer** i listan med verktyg och klicka på **Mappprofiler**.
1. Klicka på **Global profil** platta.
1. Välj **Konfiguration av XML-redigerare** och klicka på **Redigera** överst.
1. I **Användargränssnittskonfiguration för XML-redigering** klickar du på **Ladda ned** för att ladda ned `ui_config.json` på din lokala dator.
1. I `ui_config.json` ändrar du titeln i avsnittet &quot;topbar&quot;. Du kan ändra följande värden:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Spara filen och överför den.
