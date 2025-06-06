---
title: Lägga till anpassade format i guidade redigeringsprogram
description: Lär dig hur du lägger till anpassade format för att ändra utseendet på webbredigeraren för stödlinjer.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Lägga till anpassade format i guidade redigeringsprogram

I den här artikeln får vi lära oss hur du lägger till anpassade format för att ändra webbdesignerns standardutseende och -känsla.

Detta omfattar följande steg:
- Lägga till anpassade format via XML-redigerarkonfiguration för mappprofil
- Välja respektive mappprofil i webbredigeraren och testa ändringarna


## Implementera med ett exempel

Låt oss förstå detta med ett exempel där vi vill visa den korta beskrivningen och titeln som separata block med vissa formataspekter i redigeraren.

![Förhandsgranska webbredigeraren med anpassade format](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementera


### Lägga till anpassad CSS till mappprofilen

Använd mappprofilerna för att kontrollera *css_layout.css* under fliken XML-redigerarkonfiguration och lägg till CSS med anpassade format

[använd den här länken om du vill veta mer om mappprofilen och hur du konfigurerar CSS-mallayouten](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=sv-SE#customize-the-css-template-layout)

Använd följande för att konfigurera ovanstående format i din webbredigerare:
- Använd [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) och överför den till den önskade mappprofilen
- Installera det bifogade paketet [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) med hjälp AEM pakethanteraren för att installera resurserna som används i ovanstående CSS-fil

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Testning

- Öppna webbredigeraren
- I användarinställningarna väljer du den mappprofil i vilken du har lagt till de anpassade formaten. Om du lade till den i den globala profilen använder du förmodligen redan den.
- Öppna ett ämne och lägg märke till att redigeringsområdet ska ha ett anpassat användargränssnitt

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Referenser

Du kan också vara intresserad av expertsessionen runt webbredigerarkonfigurationer och anpassningar som ingår i [Expertsessionen på webbadministratören](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=sv-SE)
