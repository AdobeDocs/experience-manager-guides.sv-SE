---
title: Använda förinställningar för villkor
description: Lär dig hur du använder förinställda villkor i AEM Guides. Lär dig att skapa, redigera, kopiera och ta bort förinställningar för villkor i AEM.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 0%

---

# Använda förinställningar för villkor {#id1825FL004PN}

Du kan definiera attribut i dina DITA-avsnitt och använda villkorsförinställningen för att ange vad som ska hända med attributet i det slutliga resultatet. Du kan till exempel lägga till attribut som version 1.0 och version 2.0 i ditt innehåll och använda en villkorsförinställning för att inkludera version 1.0 för version 1.0 och exkludera version 2.0. På samma sätt kan du lägga till attribut som OS Windows och OS Linux i ditt innehåll och sedan inkludera eller exkludera det relevanta innehållet för dina slutliga utdata enligt operativsystemet.

Du kan skapa villkorsförinställningar på två sätt:

* Från Web Editor: Gör att du kan skapa och hantera villkorsförinställningar för en DITA-karta från Web Editor.
* Från kartkontrollpanelen: Gör att du kan skapa och hantera villkorsförinställningar för en DITA-karta från kartkontrollpanelen.


## Villkorsförinställningar från Web Editor

I Experience Manager Guides kan du hantera villkorsförinställningar från Web Editor och använda dem i utdatapresentationerna för att generera det slutliga resultatet.
Du kan skapa och visa villkorsförinställningar, visa attribut och hantera åtgärder för den aktuella kartan från vyn **Villkorsförinställningar** i webbredigeraren.

<img src="images//manage-condtions-presets.png" alt= "Förinställningar för villkor i webbredigeraren" width="800" border="1px">



### Skapa en villkorsförinställning

I vyn **Villkorsförinställningar** finns detaljerad information om villkorsförinställningarna, till exempel attribut, värden och åtgärder.
Du kan skapa en villkorsförinställning av ämnena genom att utföra följande steg:

1. Öppna DITA-mappningsfilen i Kartvyn på panelen **Databas**.
1. Välj fliken **Hantera**.
1. Välj **Villkorsförinställningar** till vänster. Listan med villkorsförinställningar som definierats för DITA-kartan visas.
1. Välj ikonen + bredvid **Villkorsförinställningar** för att öppna dialogrutan **Ny villkorsförinställning** .
1. Ange ett unikt namn för förinställningen.

   >[!NOTE]
   >
   > Du kan visa ett fel om namnfältet är tomt eller om du anger ett ogiltigt tecken eller ett namn som är detsamma som en befintlig villkorsförinställning. Du kan använda bindestreck &#39;-&#39; eller understreck &#39;_&#39; som avgränsare.

1. Välj **Skapa**.
Den nya villkorsförinställningen läggs till i listan.
1. Dubbelklicka på en villkorsförinställning för att visa attributen och åtgärderna.
På panelen **Attribut** visas alla attribut som lagts till i alla referenser som finns på kartan. På den högra panelen visas endast de villkor som du har lagt till i villkorsförinställningarna.
1. Gör något av följande för att lägga till attributen:
   * Markera ett eller flera attribut om du vill lägga till alla värden under dem i villkorsförinställningen. Du kan till exempel markera attributet `platform` för att lägga till alla dess värden.
   * Markera ett eller flera attributvärden som du vill lägga till i villkorsförinställningen. Du kan till exempel välja värdena `Unix` och `Win` för plattformsattributet
   * Markera ett attribut- och värdepar och dra det till mittpanelen. Du kan till exempel välja värdet `Unix` för plattformsattributet och dra det.
   * **Markera alla** om du vill lägga till alla attribut och deras värden i villkorsförinställningen.
Som standard är åtgärden för ett attribut `Include`.

1. Välj **Lägg till**. Du kan upprepa det här steget om du vill lägga till fler attribut. De attribut du lägger till flyttas från den centrala till den högra panelen.
1. Välj Ta bort i åtgärdsfältet högst upp om du vill ta bort de markerade attributen på den högra panelen.
1. (Valfritt) Om det behövs kan du åsidosätta den åtgärd som har tillämpats på attributen.
Gör något av följande:
   * För alla attribut väljer du en av följande åtgärder i listrutan Åtgärd.
      * Inkludera
      * Exkludera
      * Genomströmning
      * Flagga
   * Markera flera attributrader på den högra panelen och välj en åtgärd i åtgärdsfältet högst upp. Du kan till exempel välja åtgärden Uteslut för de markerade attributen.
1. Välj **Spara** om du vill spara villkorsförinställningen.

   >[!NOTE]
   >
   > Du kan visa en varning om du väljer en annan förinställning eller stänger förinställningen utan att spara den.

När du har skapat en villkorsförinställning visas den i listrutan **Villkorsförinställningar** i Utdatainställningarna. Läs mer om hur du [skapar utdata för Publish PDF](../web-editor/native-pdf-web-editor.md).

### Byta namn på en villkorsförinställning

Så här byter du namn på en villkorsförinställning:

1. Håll pekaren över en villkorsförinställning på panelen **Villkorsförinställningar** .
1. Välj **Byt namn** på Alternativ-menyn för att öppna dialogrutan **Byt namn på villkorsförinställning**.
1. Redigera namnet på villkorsförinställningen.
1. Klicka på **Byt namn**.

### Duplicera en villkorsförinställning

Så här duplicerar du en villkorsförinställning:

1. Håll pekaren över en villkorsförinställning på panelen **Villkorsförinställningar** .
1. Välj **Duplicera** på Alternativ-menyn för att öppna dialogrutan **Duplicera villkorsförinställning**.
   >[!NOTE]
   >
   > Förinställningens standardnamn är `<selected condition preset name>_1`. Du kan ändra namnet enligt dina önskemål.

1. Klicka på **Duplicera**.

### Ta bort förinställning för villkor

Så här tar du bort villkorsförinställningar:

1. Håll pekaren över en villkorsförinställning på panelen **Villkorsförinställningar** .
1. Välj **Ta bort** på Alternativ-menyn för att öppna dialogrutan **Ta bort villkorsförinställning** .
1. Klicka på **Ta bort**.



## Förinställningar för villkor från kartkontrollpanelen


### Skapa en villkorsförinställning

Så här skapar du en villkorsförinställning:

1. Välj fliken **Villkorsförinställningar** i DITA-kartkonsolen.
1. Klicka på knappen **Skapa**.
1. Ange ett namn för förinställningen i **Namnvillkor**.
1. Välj någon av följande standardåtgärder från listrutan **Ange standardåtgärd till**:

   * Inkludera
   * Exkludera
   * Genomströmning
   * Flagga
Åtgärden anges som standardåtgärd för alla attribut oavsett om de läggs till i villkorsförinställningen eller inte.

   Du har till exempel 15 villkorsattribut i dokumentet och du har tagit med fyra av dem i villkorsförinställningen. Om du väljer **exclude** som standardåtgärd tillämpas den på alla 15 attribut.

1. Gör något av följande för att lägga till attributen:
   * Klicka på **Lägg till** i ett attribut i villkorsförinställningen. Du kan upprepa det här steget om du vill lägga till fler attribut.
   * Klicka på **Lägg till alla** om du vill lägga till alla attribut i villkorsförinställningen.
1. \(Valfritt\) Om det behövs kan du åsidosätta den standardåtgärd som tillämpats på attributen i steg 4. Gör något av följande:
   * Välj flera attribut, välj en åtgärd från **Ange åtgärden för markerade villkor till** och klicka på **Använd**.
   * Välj en åtgärd för ett attribut i listrutan **Åtgärd**.
1. Klicka på **Spara**.

### Redigera en villkorsförinställning

Du kan ändra en befintlig villkorsförinställning om du vill ändra de åtgärder som har tillämpats på attributen i villkorsförinställningen. Så här redigerar du en villkorsförinställning:

1. Välj fliken **Villkorsförinställningar** i DITA-kartkonsolen.
1. Klicka på knappen **Redigera**.
1. Gör nödvändiga ändringar för alla attribut i villkorsförinställningen.
1. Klicka på **Spara**.

### Skapa en kopia av en villkorsförinställning

Du kan skapa en kopia av en villkorsförinställning och sedan ändra den efter behov. Så här skapar du en kopia av en villkorsförinställning:

1. Välj fliken **Villkorsförinställningar** i DITA-kartkonsolen.
1. Klicka på knappen **Duplicera**.

   >[!NOTE]
   >
   > Förinställningens standardnamn är `<selected condition preset name>_Duplicate`

   Du kan ändra namnet efter dina önskemål.

1. \(Valfritt\) Gör nödvändiga ändringar för alla attribut i villkorsförinställningen.
1. Klicka på **Spara**.

### Ta bort förinställning för villkor

Du kan ta bort en eller flera villkorsförinställningar från fliken **Villkorsförinställning** i DITA-kartkonsolen. Så här tar du bort villkorsförinställningar:

1. Välj fliken **Villkorsförinställningar** i DITA-kartkonsolen.
1. Markera den eller de villkorsförinställningar som du vill ta bort.
1. Klicka på knappen **Ta bort**.
1. Bekräfta åtgärden genom att klicka på **Ta bort**.

**Överordnat ämne:**[ Utdatagenerering](generate-output.md)
