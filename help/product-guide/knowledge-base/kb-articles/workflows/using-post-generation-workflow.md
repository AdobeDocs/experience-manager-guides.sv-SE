---
title: Post Generation Workflow
description: En översikt över arbetsflödet efter generering med ett exempel
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# AEM Guides publishing - Post Generation Workflow

AEM Guides ger dig flexibilitet att ange ett arbetsflöde för postutdata. Du kan utföra vissa efterbehandlingsåtgärder på utdata som genereras med AEM Guides.
Du kan till exempel ange vissa egenskaper för utdata från PDF eller skicka ett e-postmeddelande till en uppsättning användare när utdata har genererats.


## Vilka steg ingår för att utnyttja arbetsflödena för att skapa Post?

### Skapa en arbetsflödesprocess

Skapa en Java- eller ECMA-baserad arbetsflödesprocess som utför åtgärden på genererade utdata. Du kan till exempel kopiera vissa metadata från källan till det genererade innehållet eller ändra metadata för genererade utdata.
- Vi tar ett exempel på hur man skapar en sådan process med ECMA-skript (du kan referera till det bifogade paketet)
- För Java-baserad arbetsflödesprocess, se avsnittet *Anpassa arbetsflöde för efterhandsgenerering* i [Installations- och konfigurationshandbok](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Skapa en arbetsflödesmodell

Skapa en arbetsflödesmodell och lägg till det steget i med den anpassade arbetsflödesprocessen som du skapade i föregående steg.
- Du måste också lägga till ett obligatoriskt processsteg, *Slutför Post-generering*, som det sista steget i arbetsflödet.

Se exempelarbetsflödesmodellen nedan:

![Arbetsflödesmodell för Post-generering](../assets/workflows/pgwf-workflow-model.png)


### Använd det här arbetsflödet efter generering på en karta

Arbetsflödet för Post-generering är en egenskap som kan konfigureras för alla förinställningar i AEM Guides publiceringsmekanism. Exempel:

![Arbetsflöde för Post-generering på förinställning för utdata](../assets/workflows/pgwf-preset-settings.png)


Anta att den valda modellen redan har skapats.


### Testning

Nu kan du köra publiceringen med den här förinställningen och validera processstegets utdata


## Exempel

Som referens kan du använda paketet nedan och installera det via pakethanteraren för att testa arbetsflödet för eftergenerering (*enligt skärmbilderna ovan*)

[Exempel på ECMA-baserad arbetsflödesmodell för postgenerering](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
