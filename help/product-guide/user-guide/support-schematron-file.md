---
title: Stöd för Schematron-filer
description: Lär dig hur du importerar och validerar ett DITA-ämne, använder assert-rapportsatser för att kontrollera regler, använder regex-uttryck och definierar abstrakta mönster i Schematron-filer i AEM Guides.
exl-id: ed07a5ec-6adc-43a3-8f03-248b8c963e9a
feature: Authoring, Features of Web Editor
role: User
source-git-commit: dd058ef30707716054279f16527adb286a9deb8d
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 0%

---

# Stöd för Schematron-filer

&quot;Schematron&quot; avser ett regelbaserat valideringsspråk som används för att definiera tester för en XML-fil. Redigeraren stöder Schematron-filer. Du kan importera schemafilerna och redigera dem i Redigeraren. Med en Schematron-fil kan du definiera vissa regler och sedan validera dem för ett DITA-avsnitt eller en karta.

>[!NOTE]
>
> Redigeraren stöder ISO-schematron.


## Importera Schematron-filer

Så här importerar du Schematron-filerna:

1. Navigera till önskad mapp (där du vill överföra filerna) i *databasen*.
1. Välj ikonen **Alternativ** för att öppna snabbmenyn och välj **Överför resurser**.
1. I dialogrutan **Överför resurser** kan du ändra målmappen i fältet **Välj resursmapp**.
1. Välj **Välj filer** och bläddra till schemafilerna. Du kan välja en eller flera schemafiler och sedan välja **Överför**.

## Validera ett DITA-ämne eller en DITA-karta med Schematron

När du har importerat Schematron-filer kan du redigera dem i Redigeraren. Du kan använda Schematron-filerna för att validera ämnen eller en DITA-karta. Du kan till exempel skapa följande regler för ett DITA-schema eller -ämne:

* En titel definieras för en DITA-karta.
* En kort beskrivning av en viss längd har lagts till.
* Det ska finnas minst en topicref på kartan.

När du öppnar ett ämne i Redigeraren visas en schematrons valideringspanel till höger. Utför följande steg för att lägga till och validera ett ämne eller en karta med en Schematron-fil:

![](images/schematron-panel.png){width="350" align="left"}

1. Välj ikonen Schematron för att öppna panelen Schematron.
1. Använd **Lägg till schemafil** för att lägga till schemafiler.

   >[!NOTE]
   >
   > När en ogiltig schemaläggarfil läggs till visas ett felmeddelande på valideringspanelen.

   ![](images/schematron-panel-error.png){width="350" align="left"}

1. Om det inte finns några fel i schemaläggarfilen läggs den till och visas på valideringspanelen. Ett felmeddelande visas för Schematron-filen som innehåller fel.

   >[!NOTE]
   >
   >Du kan använda kryssikonen bredvid Schematron-filnamnet för att ta bort den.

1. Välj **Validera** om du vill validera ämnet med de tillagda Schematron-filerna.

   * Om inga regler bryts visas ett meddelande om att valideringen lyckades för filen.
   * Om ämnet bryter en regel, till exempel om det inte innehåller någon titel och valideras för schematronen ovan, visas ett valideringsfel.

   >[!NOTE]
   >
   > Valideringsresultaten visas baserat på rollattributet som är definierat i Schematron-filen. Mer information finns i [Förstå valideringsresultat och servernivåer](#understanding-validation-results-and-serverity-levels).

1. Markera felmeddelandet för att markera elementet som innehåller felet i det öppna ämnet/kartan.

Stödet för schemat i redigeraren hjälper dig att validera filerna mot en uppsättning regler och bibehålla konsekvens och korrekthet i alla ämnen.

## Förstå valideringsresultat och servernivåer

Valideringsresultaten visas baserat på rollattributet som är definierat i Schematron-filen. Ärendena kategoriseras som `Fatal`, `Error`, `Warn` eller `Info`, med ett synligt antal för varje kategori på valideringspanelen.

![](images/schematron-validation-errors.png){width="350" align="left"}

För att avgöra allvarlighetsgraden för ett problem utvärderas det _skiftlägeskänsliga_-värdet för rollattributet som är definierat i motsvarande Schematron-fil.

Följande utdrag visar vilka rollattributvärden som stöds och som definierats i en schematransregel:

* `<sch:assert role="error" test="@id">Element must have an ID.</sch:assert>`
* `<sch:report role="info" test="not(@alt)">Image should have an alt attribute.</sch:report>`
* `<sch:assert role= "fatal" test="b"> Bold must be there in <sch:name/> element</sch:assert>`
* `<sch:assert role= "warn" test="b"> Recommended formatting is missing in <sch:name/> element</sch:assert>`

Om rollattributet inte har angetts, eller om ett värde som inte stöds används, kategoriseras problemet som `Error` på valideringspanelen. Det här beteendet gäller även befintliga schematron-filer som inte definierar ett rollattribut. I sådana fall grupperas alla utgåvor under `Error`.

**Scenarier för att spara filer**

Om du vill spara en fil beror på **Kör valideringskontrollen innan du sparar filen** i [Workspace-inställningarna](../cs-install-guide/workspace-settings.md#validation):

* När det här alternativet är aktiverat kan du inte spara filen förrän problemen på `Fatal`- eller `Error`-nivå inte har lösts.
* När det är inaktiverat utförs inte valideringskontrollerna och filerna kan sparas även om det finns `Fatal`- eller `Error`-nivåproblem.

## Använd assert- och report-satser för att kontrollera regler{#schematron-assert-report}

Experience Manager Guides stöder även programsatserna assert och report i Schematron. Dessa satser hjälper dig att validera dina DITA-avsnitt.

### Programsatsen Assert

En assert-programsats genererar ett meddelande när en test-programsats utvärderas till false. Om du till exempel vill att titeln ska vara fet kan du definiera en assert-sats för den.

```XML
<sch:rule context="title"> 
    <sch:assert test = "b"> Title should be bold </sch:assert>
  </sch:rule>
```

När du validerar dina DITA-ämnen med Schematron får du ett meddelande om de ämnen där titeln inte är fet.

### Rapport

En rapportprogramsats genererar ett meddelande när en testprogramsats utvärderas till true. Om du till exempel vill att den korta beskrivningen ska innehålla högst 150 tecken kan du definiera en rapportsats för att kontrollera ämnen där den korta beskrivningen innehåller mer än 150 tecken.
När du validerar dina DITA-ämnen med Schematron får du en fullständig rapport över reglerna där rapportsatsen utvärderas till true. Du får därför ett meddelande om de ämnen där den korta beskrivningen innehåller fler än 150 tecken.


```XML
<sch:rule context="shortdesc"> 
        <sch:let name="characters" value="string-length(.)"/> 
        <sch:report test="$characters &gt; 150">  
        The short description has <sch:value-of select="$characters"/> characters. It should contain more than 150 characters.      
        </sch:report>   
    </sch:rule> 
```

>[!NOTE]
>
> Använd bara Xpath 2.0-uttryck när du skriver schematron-regler.

## Använd Regex-uttryck{#schematron-regex-espressions}

Du kan också använda Regex-uttryck för att definiera en regel med funktionen match() och sedan utföra valideringen med filen Schematron.

Du kan till exempel använda den för att visa ett meddelande om titeln bara innehåller ett ord.

```XML
<assert test="not(matches(.,'^\w+$'))"> 
No one word titles.
</assert>  
```


## Definiera abstrakta mönster{#schematron-abstract-patterns}

Experience Manager Guides har även stöd för abstrakta mönster i Schematron. Du kan definiera allmänna abstrakta mönster som återanvänder dessa abstrakta mönster.  Du kan skapa platshållarparametrar som anger det faktiska mönstret.


Genom att använda abstrakta mönster kan du förenkla schemat genom att minska antalet regler och göra det enklare att hantera och uppdatera valideringslogiken. Det kan också göra ditt schema lättare att förstå, eftersom du kan definiera komplex valideringslogik i ett enda abstrakt mönster som kan återanvändas i hela schemat.


Följande XML-kod skapar till exempel ett abstrakt mönster och sedan refererar det faktiska mönstret till det med id:t.

```XML
<sch:pattern abstract="true" id="LimitNoOfWords"> 

<sch:rule context="$parentElement"> 

<sch:let name="words" value="string-length(.)"/> 

<sch:assert test="$words &lt; $maxWords"> 

You have <sch:value-of select="$words"/> letters. This should be lesser than <sch:value-of select="$maxWords"/>. 

</sch:assert>  

<sch:assert test="$words &gt; $minWords"> 

You have <sch:value-of select="$words"/> letters. This should be greater than <sch:value-of select="$minWords"/>. 

</sch:assert>  

</sch:rule> 

</sch:pattern> 

<sch:pattern is-a="LimitNoOfWords" id="extend-LimitNoOfWords"> 

<sch:param name="parentElement" value="title"/> 

<param name="minWords" value="1"/> 

<param name="maxWords" value="8"/> 

</sch:pattern> 
```
