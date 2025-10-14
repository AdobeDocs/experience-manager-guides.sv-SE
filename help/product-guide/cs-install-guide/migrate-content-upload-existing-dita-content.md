---
title: Överför befintligt DITA-innehåll
description: Lär dig överföra befintligt DITA-innehåll
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Överför befintligt DITA-innehåll {#id176FF000JUI}

Troligen har du en databas med befintligt DITA-innehåll som du vill använda med AEM Guides. För sådant befintligt innehåll kan du använda någon av de metoder som beskrivs i [Lägg till digitalt material i Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=sv-SE).

## Konfigurera UUID-filnamnsmönster

När du importerar innehåll behöver inte filnamnen baseras på UUID. I ett system som använder UUID-baserade filnamn är det obligatoriskt att referera till alla filer med deras UUID i stället för deras ursprungliga filnamn. Om en importerad fil inte har UUID-baserade filnamn kan du konfigurera systemet så att det lägger till ett UUID i filegenskapen. Detta UUID används sedan för att referera till sådana filer där UUID inte används för att namnge filerna.

Använd instruktionerna i [Konfigurationsåsidosättningar](download-install-additional-config-override.md#) för att skapa konfigurationsfilen. Ange följande \(egenskap\)-information i konfigurationsfilen för att konfigurera filnamnsmönstret UUID:

| PID | Egenskapsnyckel | Egenskapsvärde |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Sträng som anger regex för UUID-filnamnsmönster. <br> Om en fil inte följer det angivna mönstret läggs ett UUID till i filens egenskap och alla referenser till filen uppdateras med filens UUID. <br> **Standardvärde**: `"^GUID-(?<id>.*)"` |

## Använda vändkommandon

Du kan också använda kontrollkommandon för att skapa en mapp i DAM, överföra filer och lägga till metadata i det överförda innehållet.

**Skapa en mapp**

Kör följande kommando för att skapa en mapp AEM databasen:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Ange följande parametrar för att skapa en mapp:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Användaren måste ha behörighet att skapa mappar.

- `jcr:primaryType=sling:Folder`: Ange den här parametern *som* om du vill skapa en mapptypresurs.

- `<server folder path>`: Fullständig mappsökväg inklusive namnet på den nya mappen som du vill skapa i AEM. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides` skapas mappen `AEM-Guides` i mappen `projects` i DAM.


**Överför en fil**

Kör följande kommando för att överföra en fil i AEM:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Ange följande parametrar för att överföra en fil:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Den här användaren måste ha skrivbehörighet för `server folder path`.

- ``local file path``: Slutför den filsökväg på det lokala systemet som du vill överföra.

- `<server folder path>`: Slutför mappsökvägen på den AEM servern där du vill överföra filen.


**Lägg till metadata**

Kör följande kommando för att lägga till metadata i en fil:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Ange följande parametrar för att lägga till metadatainformation:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Den här användaren måste ha skrivbehörighet för ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` är namnet på metadataattributet, till exempel `audience` och `<value>` kan vara `internal`. Du kan ange flera attributnamnvärdespar avgränsade med blanksteg.

- `<metadata node path>`: Fullständig mappsökväg inklusive filnamnet och dess metadatanod. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata` anges den angivna metadatainformationen för filen `intro.xml`.


**Överordnat ämne:**&#x200B;[&#x200B; Migrera befintligt innehåll](migrate-content.md)
