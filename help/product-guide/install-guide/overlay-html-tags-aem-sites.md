---
title: Täck över HTML-taggar i icke-äldre AEM Sites-utdata
description: Konfigurera videon och bildinställningarna för utdata från aem-webbplatser baserat på mappning av kärnkomponenter
feature: Installation
role: Admin
level: Experienced
exl-id: 726420e0-fe52-4334-b72a-8eb8bcae4d6c
source-git-commit: e0b0df19b7ec691a894130eb42df827921b4890c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Lägg över HTML-taggar i AEM Sites-utdata

Du kan lägga till och anpassa HTML-taggar i AEM Sites-utdata som genereras med AEM Sites-förinställningen baserat på mappningen av kärnkomponenter i Web Editor. Om du vill anpassa HTML-taggarna kan du täcka över filen `config.xml`. Du kan till exempel konfigurera video- och bildscheman i AEM Sites-utdata.

Utför följande steg för att täcka över och uppdatera filen `config.xml`:

1. Logga in på AEM och öppna CRXDE Lite-läget.

1. Navigera till konfigurationsfilen som finns på följande plats:

   `/libs/cq/xssprotection/config.xml`

1. Skapa en överläggsnod av mappen `xssprotection` i appnoden.

1. Navigera till konfigurationsfilen som finns i noden `apps`:

   `/apps/fmdita/config/config.xml`

1. Uppdatera följande taggar för videoklipp och bilder. Spara sedan filen.

Videor:

```XML
    <tag name="video" action="validate">
    <attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Bildscheman:

```XML
        <tag name="map" action="validate">
    <attribute    name="name">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
    <attribute name="src" onInvalid="removeTag">
        <regexp-list>
            <regexp name="onsiteURL"/>
            <regexp name="offsiteURL"/>
        </regexp-list>
    </attribute>
    <attribute name="name"/>
    <attribute name="alt"/>
    <attribute name="height"/>
    <attribute name="width"/>
    <attribute name="border"/>
    <attribute name="align"/>
    <attribute name="usemap">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="hspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    <attribute name="vspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="area" action="validate">
    <attribute name="shape">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="coords">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="href">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
   </tag>
```




Läs mer om de bästa sätten att använda [Security](https://experienceleague.adobe.com/sv/docs/experience-manager-65/content/implementing/developing/introduction/security).
