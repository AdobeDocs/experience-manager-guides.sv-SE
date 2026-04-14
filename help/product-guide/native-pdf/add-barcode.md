---
title: PDF publiceringsfunktion | Lägg till streckkod
description: Lär dig hur du lägger till streckkoder.
exl-id: 206bdcf9-2bcd-4bf1-815a-c97cdf0dc415
hidefromtoc: true
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---

# Lägga till en streckkod i PDF-utdata

En streckkod är ett datamönster som datorer kan läsa. Kunderna kan skanna streckkoder med en streckkodsläsare eller en smarttelefonkamera. Kodningsinformation som produktinformation, inventeringsnummer eller webb-URL:er kan vara användbar. Genom att lägga till streckkoder kan ni enkelt hämta in data, förbättra kundupplevelsen och underlätta bättre datahantering och säkerhet.

Du kan skapa ett format för streckkoden. och använda den för att infoga en streckkod i en sidlayout. Du kan använda formatet på en exempelstreckkod i den önskade sidlayouten.


Den här självstudiekursen hjälper dig att lägga till streckkoder i PDF-utdata.

## Steg för att generera en streckkod

Så här genererar du en streckkod:

### Uppdatera mallens CSS för att återge ett streckkodsvärde

Ändra filen `layout.css` om du vill återge en streckkod under PDF-genereringen. Olika streckkodstyper som qrcode och pdf417 stöds.  Mer information finns i [Streckkodstyper](#barcode-types).



```css
...
.barcode { 
-ro-replacedelement: barcode;   
-ro-barcode-type: code128;   
-ro-barcode-size: 100%;   
-ro-barcode-content: content();   
object-fit: contain;   
margin-top: 2mm;
 
}
...
```

### Använd CSS-formatet för att generera streckkoden

Du kan generera streckkoden på olika sätt. Några av exemplen är följande:

**Exempel 1**

Lägg till en streckkodsplatshållare i mallhuvudet och använd formatet:

1. Redigera **mallar** > **Sidlayouter**
1. Välj en sidlayout. Du kan till exempel välja sidlayouten BakåtOmslag, som innehåller sidhuvudet eller sidfoten.
1. Lägg till följande intervall på den plats där du vill infoga streckkoden.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Använd samma klassnamn som du har definierat i `layout.css`.

1. Ersätt `<Sample barcode>` med det värde som du vill att streckkodsläsaren ska läsa.

Du kan visa streckkoden när du genererar utdata-PDF med hjälp av mallen som innehåller sidlayouten. När du har utfört de föregående stegen kan du generera PDF-utdata med en streckkod.

På följande skärmbild visas ett exempel på en streckkod i en utskrift från PDF.

<img src="./assets/barcode-output-sample.png" alt="Exempelutdata med streckkod" width="700" border="2px">

**Exempel 2**

Ändra filen `Common.plt` i mallen **Grundläggande** om du vill lägga till en streckkod efter projekttiteln.

Om du vill skapa en streckkod för ett ISBN-nummer lägger du till ett ISBN-nummer. Använd sedan ISBN-numret för att generera streckkoden.

```html
...

  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode">978-1-56619-909-4</span></p>
  </div>
} 
...
```

**Exempel 3**

Så här skapar du en streckkod med hjälp av mappningsmetadata:

Använd alla metadata som finns i elementet `<topicmeta>` i en DITA-karta som ska visas som streckkod. Se till att du använder rätt XPath. Du kan till exempel lägga till `<resourceid>` i `<topicmeta>` för en DITA-karta.

I följande exempel fungerar resurs-ID som huvudindata för att generera streckkoden.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```



Du kan använda resurs-ID:t i en sidlayout på följande sätt:


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Streckkodstyper {#barcode-types}

Några av de vanligaste streckkoderna är följande:

| Typ | -ro-barcode-type | Ytterligare information |
| ---| --- | --- |
| QR-kod | qrcode | QR-kodens streckkodskodsymbolik enligt ISO/IEC 18004:2015. |
| Kod 128 | kod128 | Streckkodssymbolen Code 128 enligt ISO/IEC 15417 :2007. |
| Kod 32 | code32 | Kod 32, även kallad italiensk farmode. |
| Kod 49 | code49 | Kod 49 enligt ANSI/AIM-BC6-2000. |
| Kod 11 | code11 |                            |
| Kod 93 | code93 |                            |
| Code16k | code16k |                            |
| PDF417 | pdf417 | Streckkodssymbolerna PDF417/MicroPDF417 enligt ISO/IEC 15438:2006 och ISO/IEC 24728:2006. |
| Kod 3 av 9 | code39 | Koden 3 i 9-streckkodssymbolen enligt ISO/IEC 16388:2007. |
| MSI Plessey | msiplessey |                            |
| Kanalkod | channelCode | Kanalkod enligt ANSI/AIM BC12-1998. |
| Codabar | codabar | Codabar barcode symbology enligt BS EN 798:1996. |
| EAN-8 | ean-8 | EAN-streckkodssymbolik enligt BS EN 797:1996. |
| EAN-13 | ean-13 | EAN-streckkodssymbolik enligt BS EN 797:1996. |
| UPC-A | upc-a | UPC-streckkodssymbolik enligt BS EN 797:1996. |
| UPC-E | upc-e | UPC-streckkodssymbolik enligt BS EN 797:1996. |
| Ean/UPC Addon | addon | EAN/UPC-tilläggsstreckkodssymbolik enligt BS EN 797:1996. |
| Telepen | telefonen | Kallas även Telepen Alpha. |
| GS1-databas/databas 14 | databar | GS1 DataBar enligt ISO/IEC 24724 :2011. |
| GS1-databaret har utökats/databas 14 har utökats | databar-expanderad | GS1 DataBar har utökats enligt ISO/IEC 24724 :2011. |
| GS1 Databar Limited | databar-begränsad | GS1 DataBar Limited enligt ISO/IEC 24724 :2011. |
| POSTNET (postnumerisk kodningsteknik) | postnet | Den POSTNET-streckkodssymbol (Postal Numeric Encoding Technique) som används av United States Postal Service. |
| Pharmazentralnummer (PZN-8) | pzn8 | En Code 39-baserad symbolik som används av läkemedelsindustrin i Tyskland. |
| Farmakood | farmakologi |                            |
| Kodablock F | codablockf | Symbolik enligt AIM Europe &quot;Uniform Symbology Specification Codablock F&quot;, 1995. |
| Logmars | logmars | Standarden LOGMARS (Logistics Applications of Automated Marking and Reading Symbols) som används av USA:s försvarsdepartement. |
| Aztec Runes | aztec-runes | Aztec kör en streckkodssymbol enligt ISO/IEC 24778:2008 bilaga A. |
| Aztec Code | aztec-code | Aztec Code bar code symbology Enligt ISO/IEC 24778:2008. |
| DataMatrix | data-matrix | Datamatris ECC 200 streckkodssymbol enligt ISO/IEC 16022 :2006. |
| Kod ett | code-one |                            |
