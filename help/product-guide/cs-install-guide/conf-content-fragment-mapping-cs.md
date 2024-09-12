---
title: Konfigurera den JSON-baserade mappningen mellan ett ämne och en innehållsfragmentmodell.
description: Lär dig hur du konfigurerar den JSON-baserade mappningen mellan ett ämne och en innehållsfragmentmodell.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97d7776c81e7776d0248d6711ae5d05c46c44239
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Skapa en mappning mellan ett ämne och ett innehållsfragment



Med Adobe Experience Manager Guides kan du skapa en JSON-baserad mappning mellan ett ämne och en innehållsfragmentmodell. Du kan använda JSON-baserad mappning för att publicera innehåll som finns i vissa eller alla element i ett ämne till ett innehållsfragment.

>[!NOTE]
> 
> Om du använder 4.6 eller senare versioner behöver du inte skapa den här mappningen, kan du dra ämneselementen till fälten som finns i innehållsfragmentmodellen.
> Läs mer om hur du [publicerar innehållsfragment](../user-guide/publish-content-fragment.md).


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

Du kan publicera hela avsnittet med standardmappningen. Välj mappningen `Full Topic` i listrutan **Generera innehållsfragment** och ha fältet&quot;topicData&quot; i innehållsfragmentmodellen.
