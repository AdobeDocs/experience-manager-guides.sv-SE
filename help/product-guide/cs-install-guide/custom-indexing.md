---
title: Anpassad indexering
description: Lär dig hur du anpassar indexinnehåll
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 9a4f0391c464d69ea65ecfdaac6ecdcb17d1a3da
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Distribuera anpassat index för funktionen Sök och ersätt (Source-vyn)

## Ökning

Den här guiden innehåller stegvisa anvisningar för hur du distribuerar det anpassade indexet `guidesAssetLucene‑1‑custom‑1` på Adobe Experience Manager (AEM) as a Cloud Service. Standardfunktionen Sök och ersätt i redigeringsvyn fungerar utan det här indexet, men det anpassade indexet krävs för att du ska kunna aktivera Sök och ersätt i Source-vyn. Med Sök och ersätt (Source-vyn) kan du söka inte bara i det synliga redigerade innehållet utan även i den underliggande XML-strukturen, inklusive element, taggar och attributvärden.

## Förutsättningar

Innan du fortsätter med indexdistributionen måste du se till att:

- **AEM as a Cloud Service-miljö** med AEM Guides installerat
- **Åtkomst till projektets kodbas** (Git-databas)
- **Cloud Manager-åtkomst** med distributionsbehörigheter

## Indexdefinition

Om du vill aktivera funktionen Sök och ersätt (Source-vyn) måste du distribuera ett anpassat index med namnet **`guidesAssetLucene-1-custom-1`** till din AEM Cloud-tjänstmiljö.

### Indexnamn

```
guidesAssetLucene-1-custom-1
```

### Indexdefinition (.content.xml)

Skapa följande indexdefinition i ditt projekt på:

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Distributionssteg

Detaljerade anvisningar om hur du distribuerar anpassade index till AEM as a Cloud Service finns i [Innehållssökning och indexering - AEM as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing).

### Viktiga punkter för detta index

När du följer distributionsguiden använder du följande specifikationer för indexet Sök och ersätt:

- **Indexnamn**: `guidesAssetLucene-1-custom-1`
- **Indextyp**: Helt anpassat index (inte en anpassning av OTB-index)
- **Plats**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Paketegenskaper krävs**:
   - `noIntermediateSaves=true`
   - `allowIndexDefinitions=true`

## Omindexering

Omindexering hanteras **automatiskt** av AEM as a Cloud Service när du distribuerar indexet via Cloud Manager CI/CD-pipeline.

Indexering hanteras vanligtvis automatiskt. Om gamla data inte går att söka efter även efter korrekt distribution och slutförande av indexeringsprocessen, bör indexet indexeras om manuellt en gång.

### Vad som ska förväntas

- Indexeringsjobbet startar automatiskt efter distributionen.
- Du kan övervaka förloppet på Cloud Manager byggsida.
- Miljön är fortfarande fullt fungerande under indexeringen.

## Verifiering

När distributionen och indexeringen är klar kontrollerar du att indexet fungerar som det ska.

### Verifiera indexdistribution

I utvecklingsmiljön (om CRXDE Lite finns):

1. Navigera till `/oak:index/guidesAssetLucene-1-custom-1`.
2. Kontrollera att noden finns med den förväntade konfigurationen.

### Testa funktionen Sök och ersätt

Den primära verifieringen är att testa funktionen:

1. Öppna AEM Guides.
2. Navigera till **Verktyg** > **Stödlinjer** > **Sök och ersätt i databas**.
3. Konfigurera en sökning efter text i DITA- eller Markdown-filer.
4. Kontrollera att sökresultaten returneras korrekt.
5. Testa ersättningsfunktionen i en testfil.

## Ytterligare resurser

- [AEM as a Cloud Service indexeringsdokumentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing)
- [Indexeringshandbok för Apache Jackrabbit Oak](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [AEM Guides-dokumentation](https://experienceleague.adobe.com/en/docs/experience-manager-guides)
- [Dokumentation om Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
