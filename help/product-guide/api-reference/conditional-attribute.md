---
title: REST API för att arbeta med villkorsattribut
description: Läs mer om REST API för att arbeta med villkorsattribut
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 6184bb98c9897e980a6fba2f97476570228188af
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# REST API för att arbeta med villkorsattribut {#id175UB30E05Z}

Med följande REST API kan du lägga till villkorsattribut i en mappprofil.

## Lägg till villkorsattribut i en mappnivåprofil

En mappmetod som lägger till villkorsstyrda attribut i en viss mappnivåprofil.

**Begär URL**:\
http://*&lt;aem-guides-server\>*: *&lt;portnummer\>*/bin/fmdita/folderprofiles

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `:operation` | Sträng | Ja | Namnet på den åtgärd som anropas. Värdet för den här parametern är ``ADDATTRIBUTEPROFILES``. <br> **Obs!** Värdet är inte skiftlägeskänsligt. |
| `profilename` | Sträng | Ja | Visningsnamn för den mappnivåprofil där villkorsattributen ska läggas till. |
| `conditionalprofiles` | JSON-array | Ja | En JSON-array som består av det villkorliga attributnamnet och värdena. Följande kodexempel visar JSON-arrayen med två attribut - `platform` och `product` med flera värden tilldelade. |

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Svarsvärden**:\
Returnerar ett HTTP 200 \(Slutförd\)-svar.
