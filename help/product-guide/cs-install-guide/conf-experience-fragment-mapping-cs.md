---
title: Konfigurera den JSON-baserade mappningen mellan ett ämne och en Experience Fragment-mall.
description: Lär dig hur du konfigurerar den JSON-baserade mappningen mellan ett ämne och en Experience Fragment-mall.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 2b59db60-61b5-4a7e-bbf1-35cab8b89323
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Skapa en mappning mellan ett ämne och ett Experience Fragment

Adobe Experience Manager Guides tillhandahåller funktionen för att skapa en JSON-baserad mappning mellan ett ämne och en Experience Fragment-mall. Du kan använda den här mappningen för att publicera innehåll som finns i vissa eller alla element i ett ämne till ett Experience Fragment.

1. Om du vill hämta *experienceFragmentMapping.json* loggar du in på Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj Stödlinjer i listan med verktyg och välj **Mappprofiler**.
1. Markera profilrutan som du vill konfigurera. Du kan konfigurera mappningen för den globala profilen eller en mappnivåprofil. Välj till exempel rutan **Global profil**.
1. Välj fliken **XML-redigerarkonfiguration** och välj ikonen **Redigera** överst.
1. Välj ikonen **Download** om du vill hämta filen *experienceFragmentMapping.json* på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.

1. Du måste följa följande valideringar:

   1. Det ska vara en JSON-fil
   2. Den ska innehålla en array som innehåller minst ett objekt och varje objekt ska innehålla följande:


      `"template": string `

      `"mapping": array`

      Varje mappningsobjekt måste innehålla följande:

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Spara filen och överför den.

Experience Manager Guides konverterar hela avsnittet till HTML som sedan kan mappas till kärnkomponenterna som används i Experience Fragment. Innehållet i en `<p>`-tagg kan till exempel mappas för att skapa en textkomponent i Experience Fragment.
* `name`: Ange elementet HTML. Till exempel `<div>`, `<img>`
* `class`: Ange den DITA-elementtagg som motsvarar elementet HTML. Till exempel `<p>` `<image>`
* `resourceType`: Ange den resurstyp som gäller för komponenten som används i Experience Fragment. `wcm/foundation/components/text` är till exempel resourceType för wcm `text`-komponenten.
* `attributeMap`: Ange ytterligare information för komponenten, t.ex. om en textkomponent ska återges som `RichText` eller innehåller `fileReference` för en bildkomponent.




Exempelfil:

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



När du publicerar Experience Fragments från Web Editor väljer du `Template` i listrutan i dialogrutan **Generera Experience Fragment** för att visa mappningen som är tillgänglig för mallen i fältet **Mappning**. Om det inte finns någon anpassad mappning för en mall visas standardmappningen. Du kan använda standardmappningen för att publicera hela ämnet som ett Experience Fragment.

Mer information finns i [Publish Experience Fragments](../user-guide/publish-experience-fragment.md).
