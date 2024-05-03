---
title: Konfigurera ikon för anpassade datatyper
description: Lär dig hur du definierar ikoner för anpassade datatyper för att visa deras ikoner i olika gränssnitt i AEM
source-git-commit: ce2f5e4ab6b05fbce7b8384ff59091ebf9bab7be
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Konfigurera ikon för anpassade datatyper (ämne eller karta)


## Problemöversikt

Om du använder ett anpassat schema i AEM guider kan du skapa anpassade avsnitt eller mappningstyper och på så sätt kan du märka att anpassade avsnitt/kartor inte visar ikonen i webbredigeraren eller i Assets-gränssnittet. Se skärmbild för referens  (../assets/authoring/custom-ditatype-icon-notshown.png)

Så om du vill tilldela en ikon till de anpassade avsnitten/mappningstyperna måste du göra följande:
- Söka efter en anpassad ämne/karttyp
- Skriv format för att lägga till önskad ikon för den anpassade typen


Vi kan implementera ovanstående steg för att visa ikonen i webbredigeraren (databasvyn) och i resursgränssnittet. Nedan beskrivs stegen för båda


## Visa ikon för anpassade ämnen/kartor i webbredigeringsvyn

Steg 1: Bestäm datatypen för det anpassade datatecknet/appen - Öppna databasvyn i webbredigeraren > öppna utvecklarkonsolen i webbläsaren - Inspect ikonutrymmet bredvid det listade ämnet/kartan - Kontrollera klassen som har tilldelats det anpassade ämnet - Se skärmbilden  (../assets/authoring/custom-ditatype-icon-knowditatype.png) för mer information - vi använder den här klassen för att tilldela ikoner och skriva css för den

Steg 2: Skapa css och tilldela ikoner till den här datatypen - Skapa ett klientbibliotek under /apps, låt säga att du skapar en cq:ClientLibraryFolder under önskad sökväg - lägg till kategorierna &quot;apps.fmdita.xml_editor.page&quot; i den - skapa en mapp &quot;assets&quot; under den här katalogen och lägg till alla ikoner du vill använda för anpassade datatyper - lägg till en css-fil under klientbiblioteksmappen, till ett träd -icons.css&quot; - lägg till följande kod

```
            .tree-item-icon {
                &.custommaptype {
                    background-image: url('assets/custommap.svg')
                }
                &.customtopictype {
                    background-image: url('assets/customtopic.svg')
                }
            }
```

    - lägg till css.txt under klientbiblioteksmappen och lägg till referens till &quot;tree-icon.css&quot; som just skapats
    - spara/distribuera dessa ändringar
Se skärmbild  (../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png) om du vill ha mer information.

Och slutresultatet visas i skärmbilden  (../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Visar ikon för anpassade ämnen/kartor i resursgränssnittet

Steg 1: fastställa datatypen för det anpassade datatecknet/datamappningen - detta förklaras i föregående metods steg 1

Steg 2: Skapa JavaScript för att definiera vilka ikoner som ska läsas in för den anpassade datatypen för anpassade avsnitt/mappningstyper - Skapa ett klientbibliotek under /apps, låt säga att du skapar en cq:ClientLibraryFolder under önskad sökväg - lägg till följande egenskaper till det: - &quot;categories&quot; (multivalue string) value as &quot;dam.gui.admin.coral&quot; - &quot;berodencies&quot; (multivalue string string) fmdita.versioncontrol - Skapa en kopia av filen /libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js till den här /apps-katalogen - redigera det kopierade ämnet_type.js och ändra/lägg till anpassad typ under variabeln typeImageNameMap - Du kan också ändra sökvägen till bildmappen genom att ändra värdet för variabeln parentImagePath till den plats där anpassade ikoner lagras - Skapa en fil med namnet js.txt under klientbiblioteksmappen och lägg till referens till &quot;topic_type.js&quot; - spara/distribuera dessa ändringar, skärmbild  (../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png) om du vill ha mer information.

Och slutresultatet visas som på skärmbilden  (../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)