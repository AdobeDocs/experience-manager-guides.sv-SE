---
title: Konfigurera den JSON-baserade mappningen mellan ett ämne och en innehållsfragmentmodell.
description: Lär dig hur du konfigurerar den JSON-baserade mappningen mellan ett ämne och en innehållsfragmentmodell.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Skapa en mappning mellan ett ämne och ett innehållsfragment

AEM Guides tillhandahåller funktionen för att skapa en JSON-baserad mappning mellan ett ämne och en innehållsfragmentmodell. Du kan använda den här mappningen för att publicera innehåll som finns i vissa eller alla element i ett ämne till ett innehållsfragment.

1. Om du vill hämta *contentFragmentMapping.json* loggar du in på Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj Stödlinjer i listan med verktyg och välj **Mappprofiler**.
1. Markera rutan **Global profil**.
1. Välj fliken **XML-redigerarkonfiguration** och välj ikonen **Redigera** överst.
1. Välj ikonen **Download** om du vill hämta filen *contentFragmentMapping.json* på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.

1. Du måste följa följande valideringar:

   1. Det ska vara en JSON-fil
   2. Den ska innehålla en array som innehåller minst ett objekt och varje objekt ska innehålla följande:


      `"name": string `

      `"mapping": array`

      Varje mappningsobjekt måste innehålla följande:

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Spara filen och överför den.

Exempelfil:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

Du kan publicera hela avsnittet med standardmappningen. Välj mappningen `Full Topic` i listrutan i dialogrutan **Publish som innehållsfragment** och ha fältet&quot;topicData&quot; i innehållsfragmentmodellen.
