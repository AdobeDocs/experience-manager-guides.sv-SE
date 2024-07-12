---
title: Arbeta med villkorligt innehåll
description: Lär dig hur du skapar villkor och sedan konfigurerar generering av villkorligt innehåll i  [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Arbeta med villkorligt innehåll

**Använd skiftläge**

* Författare kan ange villkor för en del av innehållet så att de kan kontrollera om det visas i utdata.

* Författare kan välja att visa/dölja olika villkor vid publiceringen.

* Författare kan till exempel lägga till attribut som version 1.0 och version 2.0 i innehållet och använda villkor för att inkludera version 1.0 för version 1.0 och exkludera version 2.0.

**Steg 1**

Definiera villkor som är relevanta för dokumentationen i [!UICONTROL Folder Profiles]:
Se avsnittet **Konfigurera villkorliga attribut för globala profiler eller profiler på mappnivå** på [sidan 69 i installations- och konfigurationshandboken ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Konfigurera villkor i mappprofiler](assets/conditions-in-profiles.png)

**Steg 2**

Markera **[!UICONTROL Folder Profile]** som definieras i steg 1 i **Användarinställningar** i XML-redigeraren:
Se avsnittet **Användarinställningar** i [sidan 41 i användarhandboken ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Steg 3**

Använd villkoren för att villkoralisera innehållsavsnitt:
Se avsnittet **Villkor** i [Sidan 90 i användarhandboken](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Använd villkor i Web Editor](assets/conditions-in-web-editor.png)

**Steg 4**

Definiera villkorsförinställningar på mappningsnivå för att välja vilka villkor som ska aktiveras i utdata:
Se avsnittet **Använd förinställningar för villkor** i [Sidan 249 i användarhandboken](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
