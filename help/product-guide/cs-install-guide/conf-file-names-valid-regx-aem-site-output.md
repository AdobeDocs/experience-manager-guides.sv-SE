---
title: Konfigurera giltiga filnamn för utdata från AEM Site
description: Lär dig hur du konfigurerar giltiga filnamn för utdata från AEM Site
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Konfigurera giltiga filnamn för utdata från AEM Site {#id214GK0X0KXA}

På samma sätt som listan med giltiga filnamnstecken som tillåts för DITA-avsnitt kan du även konfigurera en lista med giltiga filnamnstecken för utdata från AEM Site. Vissa av de kända tecken som inte tillåts i en URL är: ``'<>`@$``. Dessa tecken konverteras automatiskt till understreck `_` när de påträffas när utdatafilnamn för AEM Site genereras.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att ange giltiga tecken i utdata för AEM Site:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Lägg till tecken som du vill ersätta med ett understreck i utdatafilnamnen för AEM Site. <br> **Standardvärde**: ``'<\>\`@$`` |

**Överordnat ämne:**&#x200B;[&#x200B; Konfigurera filnamn](conf-file-names.md)
