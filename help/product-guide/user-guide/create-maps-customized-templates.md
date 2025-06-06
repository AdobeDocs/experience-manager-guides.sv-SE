---
title: Skapa kartor baserade på anpassade mallar
description: Lär dig att skapa en egen mall, använda dem för att skapa nya kartfiler och skicka den definierade titeln till en DITA-karta i Experience Manager Guides.
exl-id: 9cb0035f-bf81-4ab5-a575-53851bbff494
feature: Authoring, Map Editor
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 0%

---

# Skapa kartor baserade på anpassade mallar {#id225VF0808MP}

Du kan skapa anpassade mappningsmallar och använda dem för att skapa DITA-kartor tillsammans med ämnesmallarna och mappningsmallarna som refereras i kartmallen

Du kan referera till andra mappningsmallar och ämnesmallar från den anpassade mappningsmallen. De refererade mappningsmallarna kan hänvisa till olika mappningsmallar, ämnesmallar, ämnen, kartor, bilder, videor och andra resurser. Den anpassade mappningsmallen kan hjälpa dig att enkelt replikera mappningsmallarna och hela den refererade mappstrukturen. Dessa anpassade mallar är särskilt användbara när du vill skapa och återskapa flera kartor med rekursiva strukturer och referenser.

>[!NOTE]
>
> Ämnesmallar skapas inte rekursivt. Det är bara ämnesmallar som är direkt inuti mappningsmallen som genereras och alla ämnesmallar i en ämnesmall som refereras direkt till i den överordnade mallen.

## Skapa anpassade mallar

Med Adobe Experience Manager Guides kan du skapa anpassade kartor och ämnen från mappen Dita-templates. Du kan använda de här anpassade mallarna för att skapa en karta och ett ämne. Du kan också dela mallarna med författarna och de kan använda dem för att skapa sina filer. Med hjälp av de här mallarna kan du tillåta författarna att behålla separata kopior av vissa resurser som finns i mallmappen.

>[!NOTE]
>
> Alla resurser som bara ska refereras och behållas över måste hållas utanför mallmappen.


Du kan skapa mappnings- och ämnesmallar på följande sätt:
- [Skapa anpassade mallar från Redigeraren](#create-customized-templates-from-the-editor)
- [Skapa anpassade mallar från Assets användargränssnitt](#create-customized-templates-from-the-assets-ui)


### Skapa anpassade mallar från Redigeraren

Funktionen **Mallar** finns i den vänstra panelen i redigeraren[&#128279;](./web-editor-features.md#left-panel) och är bara tillgänglig för administratörer.  Med den här panelen kan administratören enkelt skapa och hantera mallar som sedan kan användas av författarna. Som standard är mallarna kategoriserade under mallarna *map* och *topic* .

![](images/templates-panel_cs.png){width="300" align="left"}

Som standard kan du visa filerna efter namn. När du för muspekaren över en mall kan du visa filens namn och filnamnet som ett verktygstips.

>[!NOTE]
>
> Som administratör kan du även välja att visa fillistan i Redigeraren. Välj alternativet **Filnamn** för **redigeringsfilerna visar konfigurationsavsnittet** i **Användarinställningar**.

Så här skapar du ett ämne eller en karta från redigeraren:

1. Öppna panelen **Mallar** i redigeraren och välj ikonen **Skapa DITA-mall** .

   ![](images/create-dita-template-option.png){width="500" align="left"}

1. Välj **Ämnesmall** eller **Kartmall** i listrutan baserat på den typ av mall som du vill skapa.
1. Om du väljer **Ämnesmall** visas dialogrutan **Ny ämnesmall**.

   ![](images/new-topic-template-dialog.png){width="300" align="left"}

   Om du väljer **Kartmall** visas dialogrutan **Ny kartmall**.

   ![](images/map-template-dialog.png){width="300" align="left"}

   Du kan också välja **Mapp** i listrutan om du först vill skapa en mapp i mappen **topic** eller **map**.

1. I dialogrutan **Ny ämnesmall**/ **Ny mappningsmall** anger du **Rubrik**, som visas på panelen **Mallar**. Mallens **namn** föreslås automatiskt baserat på titeln, men du kan ange ett annat filnamn.
Välj också den typ av mall som du vill skapa i listrutan **Mall**.

   >[!NOTE]
   >
   > Om administratören har aktiverat automatiska filnamn baserat på UUID-inställningen, kommer du inte att visa namnfältet.

1. Välj **Skapa**.

När mallen har skapats måste du lägga till den i din globala profil eller mappnivåprofil. När mallen har lagts till börjar författarna visa den nya mallen i processen för att skapa ämnen/kartor.

Med menyn **Alternativ** på en befintlig mall kan du välja att **redigera** eller **duplicera** den. Vid duplicering behålls mallens struktur och typ \(av dokument\) och du kan återanvända den för att skapa en annan mall från den.

![](images/template-options-menu-editor.png){width="500" align="left"}

### Skapa anpassade mallar från Assets användargränssnitt

Följ de här stegen för att skapa en karta eller ämnesmall från användargränssnittet i Assets:

1. Gå till mappen Dita-templates i **Assets-gränssnittet**.

   ![](images/dita-templates.png){align="left"}

1. Öppna mappen **topics** om du vill skapa en **Ämne** -mall. Öppna mappen **maps** om du vill skapa en **Map**-mall.
1. Välj **Skapa \> DITA-mall**.

   ![](images/create-dita-template.png){width="300" align="left"}
1. Skapa en ämnesmall genom att välja **Ämne \> Nästa** på sidan Design. Annars väljer du **Karta \> Nästa** för att skapa en kartmall.
1. På sidan Egenskaper anger du mallen **Title**.
1. Ange filen **Namn**.

   >[!NOTE]
   >
   > Filnamnet måste ha filtillägget .dita.

1. \(Valfritt\) Lägg till en beskrivning.
1. Välj **Skapa**.

   Meddelandet Ämnesmallen som skapas visas. Du kan sedan öppna mallen och redigera den. För en mappningsmall kan du även lägga till referenser för ämnesmallarna, mappningsmallarna och andra resurser i mappningsmallen.


**Alternativ-menyn i Assets UI**

Så här skapar du en karta eller ämnesmall med Alternativ-menyn i Assets-gränssnittet:

1. Markera mappen **Karta** eller **Ämne** i den aktuella mallmappen. Till exempel, mappen `dita-templates`.
1. Välj **Skapa mappningsmall** eller **Skapa ämnesmall** på menyn **Alternativ**.

   Dialogrutan **Skapa ny mappningsmall** eller **Skapa ny ämnesmall** öppnas.
1. Ange den nya mallens rubrik och namn.
1. Välj den typ av mall som du vill skapa i listrutan **Mall**.

Meddelandet som du skapade med kartmallen visas. Du kan lägga till mallen i din globala profil eller mappnivåprofil. Den nya mallen visas sedan i processen för att skapa avsnitt eller kartor och du kan skapa kartor eller ämnen med hjälp av den.

Administratören kan också skapa en mapp och konfigurera den så att den blir den mapp där du kan skapa och spara mallarna.

Lär dig hur du konfigurerar en anpassad sökväg till en DITA-mallmapp baserat på konfigurationen:
<details>
    <summary> Molntjänster </summary>

Lär dig hur du [konfigurerar en anpassad sökväg till en DITA-mallmapp](../install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) i installations- och konfigureringshandboken för molntjänster.
</details>

<details>
    <summary> Lokal programvara</summary>

Lär dig hur du [konfigurerar en anpassad DITA-mallmappsökväg](../cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) i installations- och konfigureringshandboken på plats.
</details>

## Skicka den titel som definieras i mallarna

Om du vill skicka titeln för det ämne eller den karta som används i mallen till DITA-kartor som skapats med den mallen använder du klammerparenteser runt titeln.

Exempel

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> Endast den första förekomsten av klammerparenteser ersätts med rubrik.

Om du inte använder klammerparenteser runt titeln kommer den resulterande DITA-kartan endast att plockas ut med det första elementet och kapslingen av titeln kommer inte att plockas från mallen och ser ut så här:

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> Du kan också använda klammerparenteserna runt texten för att överföra den kapslade strukturen från de anpassade mallarna till dina DITA-kartor.

Exempel

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```

## Använd kartmallen för att skapa nya kartor

>[!NOTE]
>
> Kartmallen måste konfigureras och göras tillgänglig för redigering av administratören. Mer information finns i avsnittet *Konfigurera redigeringsmallar* i Installera och konfigurera Adobe Experience Manager Guides as a Cloud Service.

Utför följande steg i **redigeraren** för att skapa en karta med hjälp av den anpassade mappningsmallen:

1. Gå till mappen där du vill skapa kartan i **redigeraren**.
1. Välj **Ny \> DITA-karta** på Alternativ-menyn i mappen.

   ![](images/add-custom-template-dita-map.png){width="500" align="left"}
1. Dialogrutan **Ny karta** visas.
1. I dialogrutan **Ny karta** anger du kartan **Titel**, filen **Namn** och väljer den kartmall som du vill använda.

   Om du t.ex. har skapat en mappningsmall som är &quot;test-template&quot;, markerar du den.

1. Välj **Skapa**.

   Det meddelande som kartan skapade visas.

I **Assets-gränssnittet** gör du följande för att skapa en karta med hjälp av den anpassade mappningsmallen:

1. I **Assets-gränssnittet** navigerar du till den mapp där du vill skapa kartan.
1. Välj **Skapa \> DITA-karta**.
1. Markera den kartmall som du vill använda på sidan Utskrift och välj **Nästa**. Om du t.ex. har skapat en mappningsmall som är &quot;test-template&quot;, markerar du den.
1. Ange kartan **Titel** på sidan Egenskaper.
1. Ange filen **Namn**.

   >[!NOTE]
   >
   > Filnamnet måste ha filtillägget .ditamap.

1. Välj **Skapa**. Det meddelande som kartan skapade visas.

## Ytterligare information om DITA-kartor som skapats med anpassade mallar


Kartan genererar alla resurser som refereras till inuti mallmappen. En del typer av tillgångar som refereras till på en karta kan vara följande:

- Om kartan innehåller referensen till en ämnesmall skapas en kopia av den i mappen, i samma hierarki som i ämnesmappen i mappen `dita-templates`.
- Om kartan innehåller referensen till en mappningsmall skapas en kopia av den i mappen, i samma hierarki som i mappningsmappen i mappen `dita-templates`.
- Om kartan innehåller den generiska referensen till ett ämne eller en karta utanför mappen `dita-templates/topics` eller `dita-templates/maps`, refereras endast samma ämne och ingen kopia skapas.

  >[!NOTE]
  >
  > `dita-templates/topics` och `dita-templates/maps` är standardsökvägar i stödlinjer och kan konfigureras.


  Om det finns en ämnesmallnyckeldefinition inuti mappningsmallen skapas en ny nyckel \(därför nytt ämne\) som refereras till på kartan.

- Om en annan karta eller ett annat ämne skapas på samma nivå i mappen läggs namnen på de nyskapade resurserna till med 0,1,2 och så vidare. Du kan välja att öppna kartan för redigering eller spara kartfilen i databasen.

**Överordnat ämne:**&#x200B;[ Introduktion till kartredigeraren](map-editor.md)
