---
title: Konfigurera ikon för anpassade datatyper
description: Lär dig hur du definierar ikoner för anpassade datatyper för att visa deras ikoner i olika gränssnitt i AEM
source-git-commit: de281989de21d8bf4ba771670d7cb871a089b1e1
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Konfigurera ikon för anpassade/specialiserade datatyper (ämne eller karta)


## Problemöversikt

Om du använder ett anpassat schema i AEM guider kan du skapa anpassade ämne- eller mappningstyper och då kan du lägga märke till att de anpassade avsnitten/mappningstyperna inte visar ikonen i webbredigeraren eller i Assets-gränssnittet. Se skärmbilden nedan för referens

![skärmbild för referens](../assets/authoring/custom-ditatype-icon-notshown.png)


Så om du vill tilldela en ikon till de anpassade avsnitten/mappningstyperna måste du göra följande:
- Söka efter en anpassad ämne/karttyp
- Skriv format för att lägga till önskad ikon för den anpassade typen


Vi kan implementera ovanstående steg för att visa ikonen i webbredigeraren (databasvyn) och i resursgränssnittet. Nedan beskrivs stegen för båda


## Visa ikon för anpassade ämnen/kartor i webbredigeringsvyn

_Steg 1:_ Bestämma datatypen för det anpassade datatypsnittet/appen
- Öppna databasvyn i webbredigeraren > öppna utvecklarkonsolen i webbläsaren
- Inspect ikonutrymmet bredvid det listade ämnet/kartan
- Kontrollera klassen som har tilldelats det anpassade ämnet
- Se skärmbilden nedan för mer information ![Se skärmbilden](../assets/authoring/custom-ditatype-icon-knowditatype.png)
- Vi använder den här klassen för att tilldela ikoner och skriva css för den

_Steg 2:_ Skapa css och tilldela ikoner till den här datatypen
- Skapa ett klientbibliotek under /apps, låt säga att du skapar en cq:ClientLibraryFolder under önskad sökväg
   - lägg till kategorierna&quot;apps.fmdita.xml_editor.page&quot; i den
- skapa en mapp &quot;assets&quot; i den här katalogen och lägga till alla ikoner som du vill använda för anpassade datatyper
- lägg till en css-fil i klientbiblioteksmappen, säg &quot;tree-icons.css&quot;
   - lägg till följande kod

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

- lägg till css.txt under klientbiblioteksmappen och lägg till referens till&quot;tree-icon.css&quot; som just skapats
- spara/distribuera dessa ändringar

Se skärmbilden nedan för mer information.
![Se skärmbild](../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png)

Slutresultatet visas i skärmbilden nedan
![visas i skärmbild](../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Visar ikon för anpassade ämnen/kartor i resursgränssnittet

_Steg 1:_ fastställa datatypen för det anpassade datatecknet/datamappningen
- detta förklaras i föregående metods steg 1

_Steg 2:_ Skapa JavaScript för att definiera vilka ikoner som ska läsas in för den anpassade datatypen för anpassade ämne/karttyper
- Skapa ett klientbibliotek under /apps, låt säga att du skapar en cq:ClientLibraryFolder under önskad sökväg
   - lägga till följande egenskaper i den:
      - &quot;categories&quot;(multivalue string) value as &quot;dam.gui.admin.coral&quot;
      - &quot;beroenden&quot;(multivärdesträng) som &quot;libs.fmdita.versioncontrol&quot;
- Skapa en kopia av filen&quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; till den här /apps-katalogen
   - redigera det kopierade&quot;topic_type.js&quot; och ändra/lägg till anpassadType under variabeln &quot;typeImageNameMap&quot;
   - Du kan också ändra sökvägen till bildmappen genom att ändra värdet för variabeln &quot;parentImagePath&quot; till den plats där anpassade ikoner sparas
- Skapa en fil med namnet js.txt i klientbiblioteksmappen och lägg till referens till topic_type.js
- spara/distribuera dessa ändringar Se skärmbilden nedan för mer information.
  ![Se skärmbild](../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png)

Och slutresultatet visas som på skärmbilden ![visas i skärmbild](../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)