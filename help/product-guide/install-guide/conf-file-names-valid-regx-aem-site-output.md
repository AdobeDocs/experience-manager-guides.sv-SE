---
title: Konfigurera giltiga filnamn för AEM
description: Lär dig hur du konfigurerar giltiga filnamn för AEM webbplatsutdata
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Konfigurera giltiga filnamn för AEM {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för AEM. Vissa av de kända tecken som inte tillåts i en URL är: ```'<>`@$```. Dessa tecken konverteras automatiskt till understreck&quot;_&quot; när de påträffas när AEM webbplatsens utdatafilnamn genereras. Konfigurationen som gör att du kan ange giltiga tecken i AEM platsutdata finns i paketet `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Ange inställningen Otillåten teckenuppsättning för publicering till AEM Sites** om du vill inkludera tecken som du vill ersätta med ett understreck i AEM för webbplatsens utdatafiler.

**Överordnat ämne:**&#x200B;[&#x200B; Konfigurera filnamn](conf-file-names.md)
