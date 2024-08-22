---
title: Sprid AEM Assets-metadata till utdata som genereras av DITA-OT-plugin
description: Konfigurera DITA-OT-plugin och -innehåll i AEM för att överföra metadata till genererade utdata
source-git-commit: d1694535e27b0b605111f71f1f11c47ddb30536e
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 0%

---


# Om den här artikeln

I den här artikeln förklarar vi hur du implementerar ändringar i DITA-OT-plugin-programmet för att läsa metadata.xml _(tillgängligt i temporära filer)_ och använda egenskaperna, som skickas i AEM Guides publiceringsarbetsflöde, i DITA-OT-plugin-program och ställer in dem i genererade utdata.

Här nedan beskrivs de steg som du kommer att lära dig i den här artikeln:
- Ställa in metadata för utdataförinställningen för en diamap i AEM Guides
- Vid generering av utdata kommer du åt denna metadata.xml i den tillfälliga katalogen DITA-OT
- Implementering i DITA-OT-plugin-programmet för att läsa denna _metadata.xml_ och använda de tillgängliga egenskaperna i de genererade utdata
- Kontrollera genererade utdata för att se de spridda metadata

## Bakgrund

Med AEM Guides kan du använda DITA-OT-plugin-program för att publicera i valfritt utdataformat med de konfigurerade plugin-programmen, och
du kan också skicka metadata för resurser som hanteras i AEM DAM till DITA-OT-processen för att använda den i genererade utdata - se dokumentationen om [hur du ställer in diemap/avsnitt för att skicka metadata via utdatapanelen](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/output-gen/pass-metadata-dita-ot)


## Antaganden

Du har en AEM med AEM Guides version 4.4.0/2024.6 eller senare
Du har tidigare kunskap om hur DITA-OT fungerar och dess katalogstruktur


## Angivna steg

### Ange metadata för resursen

Med AEM Assets Metadata Schema kan du skapa anpassade egenskapsfält för Assets i AEM, och användare kan tilldela metadata till resurserna. Ta ett exempel på en _topic_-resurs där en metadata med namnet _customprop_ kan anges för ett exempel - se skärmbilden nedan:

![Ange egenskaper i metadataredigeraren för en resurs](../../assets/publishing/assets-metadata-properties-ui-customprop.png)


### Konfigurera metadata för diamap-utdata som ska skickas till DITA-OT

Konfigurera den förinställning du vill använda på kartan för att exportera metadata och skicka till DITA-OT
Låt oss säga att vi genererar HTML5-utdata med ett DITA-OT-plugin-program som _adobe.html_.
På skärmbilden nedan ser du hur du konfigurerar förinställningen för utdata för en karta som skickar metadata till plugin-programmet DITA-OT.
1. Öppna en karta och bläddra till fliken _Utdata_ för den här kartan och öppna förinställningen HTML5. Klicka sedan på fliken _Avancerat_ och ange Transformation-namnet som _adobe.html_ (det här är det plugin-program som vi ska konfigurera och använda, till exempel, kan du även definiera ditt anpassade plugin-program).
2. Ange _Behåll temporära filer_ om du vill kunna hämta temporära filer och kontrollera hur metadata.xml har formaterats, så kan du använda den här för utveckling
3. Välj de metadataegenskaper som du vill skicka till DITA-OT via metadata.xml. I det här exemplet kan vi säga att vi vill skicka _dc:title_ och _customprop_
4. Spara förinställningen och generera utdata
5. Hämta den tillfälliga filen med den knapp som visas på förinställningen

Se skärmbilden nedan för att förstå stegen ovan:
![Konfigurera förinställning för utdata för en karta som skickar metadata](../../assets/publishing/map-outputpreset-html5-customprop.png)


### Implementera plugin-programmet DITA-OT

#### Åtkomst till metadata.xml i en tillfällig katalog

I det hämtade paketet med temporära filer finns en metadata.xml-fil där du kan se egenskapernas och värdenas struktur (se skärmbilden nedan)
Struktur och konstruktioner för ![metadata.xml](../../assets/publishing/publish-tempfiles-metadata-structure.png)

##### Förstå metadata.xml

- Den här filen innehåller en lista över alla publicerade resurser som var och en har:
   - sökväg för filen i DITA-katalogen [id-attributet för Path-elementet]
   - och lista med metadataegenskapens värdepar [under _metadata_-elementet]

```
        <Path id="topics\about-this-document.dita">
            <sourceProps>
                ...
            </sourceProps>
            <metadata>
                <meta isArray="false" key="dc:title">About This Document</meta>
                <meta isArray="false" key="customprop">customval</meta>
            </metadata>
        </Path>
```

#### Åtkomst till metadata för varje resurs i DITA-OT-plugin

För att DITA-OT-plugin-programmet ska kunna läsa _metadata.xml_ och tillgängliga egenskaper måste vi göra följande:
- Definiera anpassade plugin-inställningar i _plugins.xml_, där parametrarna och integratorn definieras för plugin-initiering, kommer exempelfilen att se ut så här:

```
<?xml version="1.0" encoding="UTF-8"?>
<plugin id="com.adobe.html">
    <require plugin="org.dita.html5"/>
    <feature extension="dita.conductor.transtype.check" value="adobe.html"/>
    <feature extension="ant.import" file="integrator.xml"/>
    <feature extension="dita.conductor.html5.param" file="params.xml"/>
    <feature extension="package.version" value="2024.1"/>
</plugin>
```

- Vid initiering av plugin-program:
   - ange en variabel som pekar på filen metadata.xml, d.v.s. i _integrator.xml_ under plugin-programmet anger en egenskap som definierar sökvägen till metadatafilen, och
   - Definiera filen som kör anpassade xsl-omformningsregler, dvs. _args.xsl_ som i vårt fall pekar på filen _xsl/adobe-html5.xsl_.
Se koden nedan:

```
    <property name="adobe.html.xsl.dir" value="${dita.plugin.com.adobe.html.dir}${file.separator}xsl${file.separator}"/>
    <property name="args.xsl" location="${adobe.html.xsl.dir}adobe-html5.xsl" />
    <dirname property="input.dirname" file="${args.input}"/>
    <makeurl file="${input.dirname}/metadata.xml" property="metadata.url"/>
```

- Skicka värdet för variabeln _metadata.url_ till den anpassade XSL-filen för att använda den som du behöver, d.v.s. i den befintliga/skapade _param.xml_ skickar parametern till plugin-programmet, se nedan en exempelparams.xml-fil:

```
    <?xml version="1.0" encoding="UTF-8"?>
    <params xmlns:if="ant:if">
        <param name="metadata.url" expression="${metadata.url}" if:set="metadata.url"/>
    </params>
```

- I den anpassade XSL-omvandlingsfilen _xsl/adobe-html5.xsl_ kan du läsa metadatavärdena från metadatafilen och ange dem i utdata som du vill. I det här exemplet lägger vi till metadatavärdena i html head > meta-taggar. Se koden nedan:

```
<xsl:import href="plugin:org.dita.html5:xsl/dita2html5.xsl"/>
    <xsl:param name="metadata.url"/>
    <xsl:template name="copyright">
        <xsl:if test="doc-available( $metadata.url )">
            <xsl:variable name="docName" select="tokenize( base-uri(), '/' )[ last() ]"/>
            <xsl:variable name="doc" select="doc( $metadata.url )"/>
            <xsl:for-each select="$doc//Path[ ends-with( @id, concat( '\', $docName ) ) ]/metadata/meta">
                <meta name="{ @key }" content="{ . }"/>
            </xsl:for-each>
        </xsl:if>
    </xsl:template>
```

Se skärmbilden nedan och markera stegen ovan
![steg för att implementera ett plugin-program för dita-ot](../../assets/publishing/publishing-metadata-dita-ot-plugin-implementation.png)


### Testa plugin-implementeringen

Du kan testa plugin-programmet genom att köra följande kommando för att testa det med de temporära filerna som hämtas från AEM (som har kartinnehåll och dess metadata.xml)

```
./dita --input=docsrc/samples/HTML5/aem_forms_documentation.ditamap --format=adobe.html
```

Anta att du har kopierat de hämtade temporära filerna under katalogen DITA-OT/docsrc/samples/HTML5.
Du kan även hämta det exempel som ges i resursavsnittet nedan.

När ovanstående kommando körs kan du kontrollera utdata i katalogen DITA-OT/bin/out, där du kan kontrollera HTML-filerna som genereras för ämnet about-this-document.dita, som har anpassade metadata i elementet _head_

```
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <meta charset="UTF-8">
    <meta name="copyright" content="(C) Copyright 2024">
    <meta name="DC.format" content="HTML5">
    <meta name="DC.identifier" content="GUID-f193ea85-989d-4d80-99e2-2f5dea3d5310">
    <meta name="DC.language" content="en-US">
    <meta name="dc:title" content="About This Document">
    <meta name="customprop" content="customval">
    <title>About This Document</title>
</head>
```

### Distribution

När du har utvecklat plugin-programmet DITA-OT kan du integrera det i DITA-OT med kommandot _dita —install_ under katalogen DITA-OT och distribuera det till AEM [se den här artikeln för mer information](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/steps-to-setup-a-custom-dita-ot/td-p/407659)


## Resurser

1. Exempel på tillfälliga filer som hämtats från exempelredigeringsprogram - [hämtas med den här länken](../../assets/publishing/sample-temp-html5-adobe.html-content.zip)
2. DITA-OT-plugin med den ovan beskrivna implementeringen [hämtas med den här länken](../../assets/publishing/sample-custom-plugin-com.adobe.html.zip)