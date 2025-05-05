---
title: Överför befintligt DITA-innehåll
description: Lär dig överföra befintligt DITA-innehåll
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Överför befintligt DITA-innehåll {#id176FF000JUI}

Troligen har du en databas med befintligt DITA-innehåll som du vill använda med AEM Guides. För sådant befintligt innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till AEM.

## Använda ett WebDAV-verktyg

Om du redigerar ämnen och kartor i en annan DITA-redigerare kan du använda valfritt WebDAV-verktyg för att överföra filerna. I proceduren i det här avsnittet används WinSCP som WebDAV-verktyg för att överföra innehåll.

Utför följande steg för att använda WinSCP för att överföra filer:

1. Hämta och installera WinSCP på datorn.

1. Starta WinSCP-appen.

   Dialogrutan Inloggning visas.

1. I inloggningsdialogrutan anger du en ny platsinställning genom att välja WebDAV som **filprotokoll** och ange annan anslutningsinformation, till exempel:

   - URL:en där din AEM är värd,

   - portnumret \(standard är 4502\), och

   - användarnamn och lösenord för att komma åt AEM.

1. Klicka på **Logga in**.

   När anslutningen är klar visas innehållet i AEM Assets i WinSCP-användargränssnittet. Du kan enkelt bläddra bland, skapa, uppdatera eller ta bort innehåll med WinSCP-filutforskaren.


## Använd FrameMaker

Adobe FrameMaker har en kraftfull AEM som gör att du enkelt kan överföra dina befintliga DITA-dokument och andra FrameMaker \(.book och .fm\) till AEM. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Utför följande steg om du vill använda FrameMakernas AEM Connector för att överföra innehåll:

1. Starta FrameMakerna.

1. Öppna dialogrutan **Anslutningshanteraren**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Ange följande information för att ansluta till AEM databas:

   - **Namn**: Ange ett beskrivande namn som identifierar anslutningen till AEM.
   - **Server**: Ange URL-adressen och portnumret för AEM.

   - **Användarnamn**/**Lösenord**: Ange användarnamn och lösenord för att komma åt AEM.

1. Klicka på **Anslut**.

   När anslutningen har upprättats visas Assets från AEM i databashanterarfönstret.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Om du högerklickar på en fil eller mapp kan du utföra relaterade åtgärder. Om du till exempel högerklickar på en mapp får du alternativ för att överföra en fil, överföra filen med beroenden, överföra en hel mapp och så vidare.


## Konfigurera UUID-filnamnsmönster

När du importerar innehåll behöver inte filnamnen baseras på UUID. I ett system som använder UUID-baserade filnamn är det obligatoriskt att referera till alla filer med deras UUID i stället för deras ursprungliga filnamn. Om en importerad fil inte har UUID-baserade filnamn kan du konfigurera systemet så att det lägger till ett UUID i filegenskapen. Detta UUID används sedan för att referera till sådana filer där UUID inte används för att namnge filerna.

Utför följande steg för att kontrollera filnamn mot ett UUID-mönster och tilldela UUID till filer som inte har tilldelats ett UUID:

1. Öppna konfigurationssidan för Adobe Experience Manager Web Console.

   Standardwebbadressen för åtkomst till konfigurationssidan är:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Sök efter och klicka på paketet *com.adobe.fmdita.config.ConfigManager*.

1. I egenskapen **UID-filnamnsmönster** anger du ett mönster som kontrollerar den importerade filens namn.

   Om en fil inte följer det angivna mönstret läggs ett UUID till i filens egenskap och alla referenser till filen uppdateras med filens UUID.

1. Klicka på **Spara**.


## Överföra innehåll med UUID med ett WebDav-verktyg {#id201MI0I04Y4}

Du kan använda någon av följande metoder för att överföra ditt innehåll med UUID:

- Dra-och-släpp innehåll från det lokala systemet.
- Använd arbetsflödet **Skapa** \> **Filer** från AEM Assets-gränssnitt.
- Använd ett verktyg som WinSCP.

Om du använder ett verktyg som WinSCP kan du definiera åtgärden som ska utföras på en dubblettfil genom att ange alternativet **Flytta gammal fil med samma UUID till ny mapp** i configMgr. Det här alternativet definierar vilken åtgärd som utförs på en fil som är tillgänglig på någon annan plats i AEM. Den här inställningen är tillgänglig i paketet *com.adobe.fmdita.config.ConfigManager* i configMgr.

Som standard är alternativet **Flytta gammal fil med samma UUID till ny mapp** aktiverat. Det innebär att när filen som överförs finns i någon annan mapp i databasen flyttas den befintliga filen till den aktuella platsen och skrivs över med filen som överförs. Om du inte markerar det här alternativet skrivs filen över på sin befintliga plats.

**Ytterligare information om att arbeta med UUID-baserade filer**:

Följande punkter måste beaktas när innehåll flyttas eller kopieras i AEM:

- När du kopierar en eller flera filer från en plats till en annan skapas ett nytt UUID för filer som inte har något UUID. Detta UUID läggs till i filens metadata.

- Om en fil har en konflikt eller har en dubblett, genereras ett unikt filnamn för den nya filen som kopieras eller flyttas.

- Två filer kan inte ha samma UUID. Alla nya filer tilldelas ett unikt UUID.


Följande punkter måste beaktas när du flyttar eller kopierar innehåll från ditt lokala system till AEM:

- Om en fil överförs av två olika användare samtidigt, kommer den fil som bearbetas senare att skriva över den tidigare filen. En sådan metod är dock sällsynt och bör undvikas.

- När du checkar ut innehåll från den AEM databasen och gör ändringar i det lokala systemet, kontrollerar du att filnamnet inte ändras när du överför filen.


## Använda vändkommandon

Du kan också använda kontrollkommandon för att skapa en mapp i DAM, överföra filer och lägga till metadata i det överförda innehållet.

**Skapa en mapp**

Kör följande kommando för att skapa en mapp AEM databasen:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Ange följande parametrar för att skapa en mapp:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Användaren måste ha behörighet att skapa mappar.

- `jcr:primaryType=sling:Folder`: Ange den här parametern *som* om du vill skapa en mapptypresurs.

- `<server folder path>`: Fullständig mappsökväg inklusive namnet på den nya mappen som du vill skapa i AEM. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides` skapas mappen `AEM-Guides` i mappen `projects` i DAM.


**Överför en fil**

Kör följande kommando för att överföra en fil i AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Ange följande parametrar för att överföra en fil:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Den här användaren måste ha skrivbehörighet för `server folder path`.

- ``local file path``: Slutför den filsökväg på det lokala systemet som du vill överföra.

- `<server folder path>`: Slutför mappsökvägen på den AEM servern där du vill överföra filen.


**Lägg till metadata**

Kör följande kommando för att lägga till metadata i en fil:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Ange följande parametrar för att lägga till metadatainformation:

- `<username>:<passowrd>`: Ange användarnamn och lösenord för att komma åt AEM. Den här användaren måste ha skrivbehörighet för ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` är namnet på metadataattributet, till exempel `audience` och `<value>` kan vara `internal`. Du kan ange flera attributnamnvärdespar avgränsade med blanksteg.

- `<metadata node path>`: Fullständig mappsökväg inklusive filnamnet och dess metadatanod. Om du till exempel anger sökvägen som `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata` anges den angivna metadatainformationen för filen `intro.xml`.


**Överordnat ämne:**&#x200B;[ Migrera befintligt innehåll](migrate-content.md)
