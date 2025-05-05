---
title: Redigerarvyer för ämnen
description: Visa ämnen i redigeringsläge, källläge och förhandsgranskningsläge. Lär dig hur du visar innehåll baserat på villkorsstyrda filter, visar ändringsmarkeringar och exporterar ett ämne som PDF i AEM Guides.
exl-id: 74db2902-4507-4904-85d8-6b52e4af4c55
feature: Authoring, Features of Web Editor
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1447'
ht-degree: 0%

---

# Redigerarvyer för ämnen {#id204GK0D0V5Z}

Redigerargränssnittet i Adobe Experience Manager har stöd för att visa ämnen i tre olika lägen eller vyer:

* [Författare](#author)
* [Source](#source)
* [Förhandsgranska](#preview)

## Författare

Det här är en typisk **Du ser vyn What You Get** \(WYSISYG\) i Redigeraren. Du kan redigera ämnen på samma sätt som i vanliga RTF-redigerare. I redigeringsvyn har du möjlighet att spara en revision av dokumentet, söka och ersätta innehåll, infoga element, infoga hyperlänk, infoga innehållsreferens och mycket annat.

>[!NOTE]
>
> När du använder innehållsreferensen visas även det refererade innehållet i redigeringsvyn i blå färg. Det refererade innehållet går inte att redigera.

## Source

I Source-vyn visas den underliggande XML-koden som avsnittet består av. Om du känner dig trygg när du arbetar med XML direkt bör du använda vyn Source. Förutom att göra vanliga textredigeringar i den här vyn kan du även lägga till element och attribut med den smarta katalogen eller söka och ersätta text, element eller attribut.

* Om du vill anropa den smarta katalogen placerar du markören i slutet av en elementtagg där du vill infoga det nya elementet och skriver &quot;&lt;&quot;. Redigeraren visar en lista med alla giltiga XML-element som du kan infoga på den platsen. Använd piltangenterna för att markera det element som du vill infoga och tryck på Retur. När du anger avslutande parentes &quot;\> läggs sluttaggen för elementet till automatiskt.

  ![](images/smart-catalog-elements.png){width="400" align="left"}

* Du kan också enkelt ändra ett element i vyn Source. Om du till exempel ändrar starttaggen för ett `p`-element till `note` ändras den avslutande `p`-taggen automatiskt till `/note`. Om du ersätter ett element med ett felaktigt element visas valideringsfelet omedelbart.

* Om du vill lägga till ett attribut i ett element placerar du markören inuti elementtaggen och trycker på blankstegstangenten. En lista med giltiga attribut för det elementet visas i den smarta katalogen. Använd piltangenterna för att markera det önskade elementet och tryck på Retur för att infoga elementet. Om du vill ange ett värde för attributet anger du lika med-tecknet \(=\) och redigeraren anger automatiskt inledande och avslutande citattecken &quot;&quot;, där du kan ange attributets värde.

  ![](images/smart-catalog-attribute.png){width="350" align="left"}

* I vyn Source finns det ett alternativ för automatiskt indrag som ordnar om XML-koden i ett presenterbart och lättläst format. Om du markerar en text och växlar från författare till Source eller från Source till redigeringsvy, markeras den markerade texten även i den andra vyn.
* En annan kraftfull funktion i Source-vyn är XML-valideringen i ditt dokument. Om du öppnar ett dokument som innehåller ogiltig XML öppnas det i Source-vyn med information om ogiltig XML. I följande skärmbild visas den exakta informationen om den felaktiga XML:en i popup-fönstret Tolkningsfel.

  ![](images/invalid-topic-xml.png){width="650" align="left"}

  På skärmbilden ovan används en markering som pekar på raden som innehåller felaktig XML.

* Med funktionen Sök och ersätt kan du söka efter text, element eller attribut i Source-vyn.
Mer information finns i funktionsbeskrivningen för **Sök och ersätt** i avsnittet [Flikfält](web-editor-features.md#tab-bar).

* I Source-vyn finns många kortkommandon som du kan använda för att snabbt navigera och arbeta med dokument. I följande tabell visas vilka åtgärder som stöds och deras kortkommandon:

  | För att göra detta | Använd den här genvägen |
  |----------|-----------------|
  | Lägga till flera markörer | **Ctrl**+Vänsterklicka |
  | Flera textmarkeringar som inte följer varandra | **Ctrl**+vänsterklicka för att dra och markera text |
  | Markera text över och mellan rader | **Alt**+vänsterklicka för att dra och markera text |
  | Ångra flera markeringar eller avsluta helskärmsläge | **Esc** |
  | Visa automatisk komplettering | **Ctrl**+**Blanksteg** |
  | Gå till den aktuella taggens öppningstagg eller avslutande tagg | **Ctrl**+**J** |
  | Expandera eller komprimera den aktuella taggen och dess innehåll | **Ctrl**+**Q** |
  | Markera det aktuella elementet och dess innehåll | **Ctrl**+**L** |
  | Dra ut aktuellt element | **Skift**+**Tabb** |
  | Ta bort det aktuella elementet och dess innehåll | **Skift**+**Ctrl**+**K** |
  | Flytta markören ett ord åt vänster | **Alt**+**Vänsterpil** |
  | Flytta markören ett ord åt höger | **Alt**+**Högerpil** |
  | Rulla en rad uppåt utan att ändra markörens plats | **Ctrl**+**Uppåtpil** |
  | Bläddra en rad nedåt utan att ändra markörens plats | **Ctrl**+**Nedåtpil** |
  | Växla helskärm | **F11** |
  | Infoga en ny rad efter aktuellt element | **Ctrl**+**Retur** |
  | Infoga en ny rad före aktuellt element | **Skift**+**Ctrl**+**Retur** |
  | Sök efter och markera nästa förekomst av det aktuella ordet | **Ctrl**+**D** |
  | Flytta det aktuella elementet och dess innehåll ett element uppåt | **Skift**+**Ctrl**+**Uppåtpil** |
  | Flytta det aktuella elementet och dess innehåll ett element nedåt | **Skift**+**Ctrl**+**Nedåtpil** |
  | Radbryt det aktuella elementet i kommentartaggen | **Ctrl**+**/** |
  | Duplicera det aktuella elementet och dess innehåll | **Skift**+**Ctrl**+**D** |
  | Ta bort text efter markören. Om markören står före ett öppningselement tas hela elementet bort. | **Ctrl**+**K**+**K** |
  | Radera text till vänster om markören på den aktuella raden. Om markören står efter den avslutande taggen för ett element tas hela elementet bort. | **Ctrl**+**K**+**Backsteg** |
  | Konvertera den aktuella texten till versaler | **Ctrl**+**K**+**U** |
  | Konvertera den aktuella texten till gemener | **Ctrl**+**K**+**L** |
  | Bläddra det aktuella elementet till mitten av redigeraren | **Ctrl**+**K**+**C** |
  | Lägg till en markör ovanför den aktuella positionen | **Ctrl**+**Alt**+**Uppåtpil** |
  | Lägg till en markör under den aktuella positionen | **Ctrl**+**Alt**+**Nedåtpil** |
  | Hitta det aktuella ordet rekursivt \(i framåtriktning\) | **Ctrl**+**F3** |
  | Hitta det aktuella ordet rekursivt \(i bakåtriktning\) | **Skift**+**Ctrl**+**F3** |


## Förhandsgranska

När du öppnar ett ämne i förhandsgranskningsläget visas hur ett ämne kommer att visas när det visas av en användare i webbläsaren. Om det är en DITA-karta visas en förhandsvisning av kartan där ett sammansatt dokument med alla ämnen på kartan visas.

I förhandsgranskningsläget kan du använda följande funktioner:

* [Visa innehåll baserat på villkorsstyrda filter](#id2114BI00VXA)
* [Visa ändringsmarkeringar för spår](#id2114BJ00CE8)
* [Exportera ett ämne som PDF](#id2114BL00B5U)

### Visa innehåll baserat på villkorsstyrda filter {#id2114BI00VXA}

Om du har använt villkor i ett ämne eller en karta visas dessa villkor på panelen Filter. Som standard markeras alla villkor och hela innehållet visas. Om du avmarkerar ett villkor tas innehållet med det villkoret bort från vyn. Du kan också välja att markera villkorsstyrt innehåll.

I följande bild visas ett ämne som använder två villkor: `Audience` och `Product`. Det villkorade innehållet markeras med gul bakgrund.

![](images/preview-filters.png){align="left"}

### Visa ändringsmarkeringar för spår {#id2114BJ00CE8}

Om ett dokument innehåller spåra ändringar av markeringar \(eller visuella tecken\) kan du även förhandsgranska dokumentet med eller utan dessa markeringar. När du förhandsgranskar ett dokument innehåller den högra panelen alternativen Filter och Spärra/knip.

![](images/preview-tracking_cs.png){width="400" align="left"}

Det finns tre **spårningsalternativ** som du kan välja mellan:

* **Ingen markering**: I den här vyn accepteras alla infogningar och borttagningar och en enkel vy av dokumentet visas. I den här vyn kan du inte visa några ändringsmarkeringar för spår.
* **Original**: I den här vyn avvisas alla infogningar och alla borttagningar återställs och en förhandsvisning visas. Du får helt enkelt originalformuläret för dokumentet innan du aktiverade läget för spårändringar.
* **Visa markering**: I den här vyn får du alla markeringar för infogat och borttaget innehåll.

  I följande bild visas förhandsgranskningen av en kartfil med markeringar:

  ![](images/preview-map-with-track-changes.png){width="300" align="left"}


### Exportera ett ämne som PDF {#id2114BL00B5U}

PDF är ett av de vanligaste utdataformaten som används i alla möjliga faser av dokumentutvecklingscykeln. Med Experience Manager Guides kan du skapa en PDF av ett enskilt ämne eller en hel kartfil. Med funktionen Exportera som PDF kan författaren, utgivaren eller en administratör enkelt generera PDF-utdata för ett enskilt ämne. Den använder de DITA-OT-konfigurationer som har sparats i mappnivåprofilen för att generera PDF.

Den här funktionen har stöd för följande funktioner:

* Generera en PDF av den aktuella arbetskopian av ett ämne.
* Acceptera DITA-OT-transformeringsnamnet och kommandoradsargumenten för att generera PDF.
* Spara genererade utdata på det lokala systemet.
* Lös de nyckel- och innehållsreferenser som används i avsnittet innan utdata genereras.

Så här exporterar du ett ämne som PDF:

1. Öppna ämnet i förhandsgranskningsläget. Kontrollera att ämnet är en del av en kartfil.

1. Välj alternativet **Hämta som PDF** längst upp.

   ![](images/download-as-pdf-preview.png)-ikon.

   >[!NOTE]
   >
   > Kontrollera att du har aktiverat popup-fönstret i webbläsarkonfigurationen, annars hämtas inte PDF.

   PDF genereras och öppnas på en ny flik eller så visas en dialogruta där du kan spara PDF på din dator.


**Överordnat ämne:**&#x200B;[ Introduktion till redigeraren](web-editor.md)
