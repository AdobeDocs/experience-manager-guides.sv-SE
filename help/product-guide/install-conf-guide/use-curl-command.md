---
title: Använda vändkommandon
description: Lär dig hur du använder kommandon för att kontrollera det överförda innehållet i Experience Manager Guides.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Använda vändkommandon

Du kan också använda kontrollkommandon för att skapa en mapp i DAM, överföra filer och lägga till metadata i det överförda innehållet.

## Skapa en mapp

Kör följande kommando för att skapa en mapp i AEM-databasen:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Ange följande parametrar för att skapa en mapp:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM-databasen. Användaren måste ha behörighet att skapa mappar.

- `jcr:primaryType=sling:Folder`: Ange den här parametern *som* om du vill skapa en mapptypresurs.

- `<server folder path>`: Fullständig mappsökväg inklusive namnet på den nya mappen som du vill skapa i AEM-databasen. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides` skapas mappen `AEM-Guides` i mappen `projects` i DAM.


## Överföra en fil

Kör följande kommando för att överföra en fil i AEM-databasen:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Ange följande parametrar för att överföra en fil:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM-databasen. Den här användaren måste ha skrivbehörighet för `server folder path`.

- ``local file path``: Slutför den filsökväg på det lokala systemet som du vill överföra.

- `<server folder path>`: Slutför mappsökvägen på AEM-servern där du vill överföra filen.


## Lägg till metadata

Kör följande kommando för att lägga till metadata i en fil:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Ange följande parametrar för att lägga till metadatainformation:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM-databasen. Den här användaren måste ha skrivbehörighet för ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` är namnet på metadataattributet, till exempel `audience` och `<value>` kan vara `internal`. Du kan ange flera attributnamnvärdespar avgränsade med blanksteg.

- `<metadata node path>`: Fullständig mappsökväg inklusive filnamnet och dess metadatanod. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata` anges den angivna metadatainformationen för filen `intro.xml`.