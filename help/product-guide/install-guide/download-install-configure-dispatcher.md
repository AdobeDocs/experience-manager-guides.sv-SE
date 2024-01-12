---
title: Konfigurera Dispatcher
description: Lär dig konfigurera Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 3%

---

# Konfigurera Dispatcher {#id213BCM0M05U}

Om du tänker använda en Dispatcher på AEM Author-instans tillsammans med AEM Guides måste du utföra följande ytterligare konfigurationer för att slutföra konfigurationen:

>[!NOTE]
>
> Dispatcher är Adobe Experience Managers verktyg för cachelagring och/eller belastningsutjämning. Mer information om hur du använder Dispatcher finns i [Dispatcher - översikt](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=en).

## Aktivera AllowEncodedSlashes i URL:er

URL-adresser med kodade snedstreck är inte aktiverade som standard i AEM Dispatcher-inställningar, men när du arbetar i AEM Guides måste du aktivera detta. För att kunna göra detta måste du ange parametern AllowEncodedSlash till På i Apache-konfigurationen enligt följande kodutdrag:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Konfigurera filen mime.types för DITA

När du använder en Dispatcher med AEM Guides måste du se till att DITA-kartan och ämnesfilerna återges som HTML för att författarna ska kunna visa innehållet som de förväntar sig \(i stället för i Raw-textformat\).

Så här uppdaterar du filen mime.types:

1. Anslut till Dispatcher-servern med SSH och bläddra till filen httpd.conf.

1. Kontrollera sökvägen till filen mime.types.

1. Öppna filen mime.types och sök efter text/html. Standardmappningen för text/html är:

   `text/html html htm`

1. Uppdatera mappningen genom att lägga till ditamap- och dita-tillägg som:

   `text/html html htm ditamap dita`

1. Spara och stäng filen.


Den här konfigurationsuppdateringen ser till att DITA-kartor och ämnesfiler som återges av Dispatcher visas som HTML i resursgränssnittet.

## Tillåt URL för begäran om användarinställningar

När du använder en Dispatcher med AEM Guides och din Author-instans har en dispatcher framför, ska du göra följande två ändringar:

- Visa en vitlista för POSTENS begärande-URL. Ett exempel &quot; `/filters`&quot; rule is given below - Add this rule to dispatcher configurfile:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Kontrollera att URL-mönstret /libs/cq/security/userinfo.json inte cachas av författardispatchern, så lägg till en regel \(som nedan\) i författaren\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Överordnat ämne:**[ Hämta och installera](download-install.md)
