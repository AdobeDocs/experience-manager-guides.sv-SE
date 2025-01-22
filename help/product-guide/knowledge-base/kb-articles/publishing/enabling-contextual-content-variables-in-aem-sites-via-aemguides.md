---
title: Aktivera CCVAR (Contextual Content Variables) på AEM Sites-sidor som genererats från AEM Guides
description: Arbeta med CCVAR (Contextual Content Variables) på AEM Sites-sidor som genererats från AEM Guides
feature: Web Editor
role: User, Admin
exl-id: f9adbb3f-6c1c-4d6f-b55d-1fb45acca91a
source-git-commit: 4020534552bdb77545c2a283f2a90adc3aebc729
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Aktivera CCVAR (Contextual Content Variables) på AEM Sites-sidor som genererats från AEM Guides

Contextual Content Variables (CCVAR) är en ACS Commons-funktion som gör att författare kan använda dynamiska innehållsvariabler direkt i den text de skriver. CCVAR används ofta i AEM Sites, men i den här artikeln beskrivs hur du uppnår liknande funktionalitet via sidor som genereras från innehåll som skapats i **AEM Guides** *primärt genom att använda nyckelord som definieras i DITA-kartan*.


## Vad är sammanhangsberoende innehållsvariabler (CCVAR)?

Med CCVAR kan författare infoga dynamiska variabler i sitt innehåll, som löses vid körning baserat på sammanhanget. Variabler som `((page_properties.pageTitle))` kan till exempel hämta sidtiteln dynamiskt under innehållsåtergivning.


## Hur aktiverar man CCVAR på AEM Sites-sidor som genererats från AEM Guides?

Om du tänker på att AEM Guides används som källa för allt innehåll (inklusive AEM Sites, PDF eller HTML5) måste du använda nyckelord för att definiera CCVAR-namnet för sidor som genereras från AEM Guides. Om du vill göra det i guider definierar du **nyckelord** i DITA-kartan med `<keydef>` -element. Dessa nyckelord kan motsvara dynamiska värden (eller CCVAR-namn), vilket gör att du kan referera till dem i dina DITA-avsnitt.


## Krav

Innan du fortsätter bör du kontrollera att följande krav är uppfyllda:

1. **AEM ACS-kommandon installerade**:
   - Kontrollera att **ACS AEM Commons** är installerat på din AEM. Detta krävs för att använda CCVAR.

2. **Kontextuell variabelkonfiguration**:
   - Slutför konfigurationen för **Sammanhangsberoende innehållsvariabler** i AEM med den [officiella dokumentationen](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). Detta omfattar följande:
      - Aktiverar **egenskapsaggregering**.
      - Konfigurerar **HTML Rewriting** (om utdata från HTML används).
      - Konfigurerar **JSON-omskrivning** (om JSON-utdata används).



## Steg för att aktivera CCVAR i AEM Guides

### 1. Definiera nyckelord i DITA-kartan

- I AEM Guides definierar du nyckelord med hjälp av `<keydef>`-element i DITA-kartan så att de motsvarar CCVAR.
- Till exempel:

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```

- Attributet `keys` (`product` i det här exemplet) används för att referera till den här variabeln i dina DITA-avsnitt.


## 2. Använd nyckelord i DITA-avsnitt

- I det här avsnittet använder du nyckelordet där CCVar ska användas.
- Till exempel:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- Attributet `keyref` pekar på värdet `keys` som definieras i elementet `<keydef>` (`product` i det här fallet).
- Vid generering av utdata ersätts nyckelordet med motsvarande CCVar-värde.


## 3. Generera utdata

- När du genererar utdata för AEM Sites tolkas nyckelordsreferenserna till motsvarande dynamiska värden.
- Till exempel:
   - Om `((page_properties.pageTitle))` matchar `My Product` visas utdata:

```xml
   This is the title of the product: My Product.
```


## Exempel på användningsfall

Anta att du dynamiskt vill infoga sidans språk i dina DITA-avsnitt. Så här kan du uppnå detta:

**Definiera nyckelordet i DITA-kartan**:

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

**Referera nyckelordet i ett DITA-ämne**:

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

**Genererade utdata**:

Om `((inherited_page_properties.jcr:language))` matchar `en` visas utdata:

```
     The language of this page is: en.
```


### Resurser

Mer information om **Sammanhangsberoende innehållsvariabler** finns i den officiella dokumentationen:\
[Sammanhangsberoende innehållsvariabler i AEM ](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)
