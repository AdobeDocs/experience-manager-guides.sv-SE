---
title: Överför befintligt DITA-innehåll
description: Lär dig hur du överför befintligt DITA-innehåll i Experience Manager Guides med WebDAV-verktyget och FrameMaker
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Ladda upp befintligt DITA-material med WebDAV-verktyget och FrameMaker för lokalt

Troligen har du en databas med befintligt DITA-innehåll som du vill använda med AEM Guides. Om du har sådant innehåll kan du använda någon av följande metoder för att massöverföra ditt innehåll till AEM-databasen.

- [Använda ett WebDAV-verktyg](#use-a-webdav-tool)
- [Använd FrameMaker](#use-framemaker)

## Använda ett WebDAV-verktyg

Om du redigerar ämnen och kartor i en annan DITA-redigerare kan du använda valfritt WebDAV-verktyg för att överföra filerna. I proceduren i det här avsnittet används WinSCP som WebDAV-verktyg för att överföra innehåll.

Utför följande steg för att använda WinSCP för att överföra filer:

1. Hämta och installera WinSCP på datorn.

1. Starta WinSCP-appen.

   Dialogrutan Inloggning visas.

1. I inloggningsdialogrutan anger du en ny platsinställning genom att välja WebDAV som **filprotokoll** och ange annan anslutningsinformation, till exempel:

   - URL:en där din AEM-server finns,

   - portnumret `\(default is 4502\)`, och

   - användarnamn och lösenord för att komma åt din AEM-server.

1. Välj **Logga in**.

   När anslutningen är klar visas innehållet i AEM Assets i WinSCP-användargränssnittet. Du kan enkelt bläddra bland, skapa, uppdatera eller ta bort innehåll med WinSCP-filutforskaren.

## Överföra innehåll med UUID med ett WebDav-verktyg {#id201MI0I04Y4}

Du kan använda någon av följande metoder för att överföra ditt innehåll med UUID:

- Dra-och-släpp innehåll från det lokala systemet.
- Använd arbetsflödet **Skapa** \> **Filer** från AEM Assets-gränssnitt.
- Använd ett verktyg som WinSCP.

Om du använder ett verktyg som WinSCP kan du definiera åtgärden som ska utföras på en dubblettfil genom att ange alternativet **Flytta gammal fil med samma UUID till ny mapp** i configMgr. Det här alternativet definierar vilken åtgärd som utförs på en fil som är tillgänglig på någon annan plats i AEM-databasen. Den här inställningen är tillgänglig i paketet `*com.adobe.fmdita.config.ConfigManager*` i configMgr.

Som standard är alternativet **Flytta gammal fil med samma UUID till ny mapp** aktiverat. Det innebär att när filen som överförs finns i någon annan mapp i databasen flyttas den befintliga filen till den aktuella platsen och skrivs över med filen som överförs. Om du inte markerar det här alternativet skrivs filen över på sin befintliga plats.

**Ytterligare information om att arbeta med UUID-baserade filer**:

Följande punkter måste beaktas när innehåll flyttas eller kopieras inom AEM-databasen:

- När du kopierar en eller flera filer från en plats till en annan skapas ett nytt UUID för filer som inte har något UUID. Detta UUID läggs till i filens metadata.

- Om en fil har en konflikt eller har en dubblett, genereras ett unikt filnamn för den nya filen som kopieras eller flyttas.

- Två filer kan inte ha samma UUID. Alla nya filer tilldelas ett unikt UUID.


Följande punkter måste beaktas när du flyttar eller kopierar innehåll från ditt lokala system till AEM-databasen:

- Om en fil överförs av två olika användare samtidigt, kommer den fil som bearbetas senare att skriva över den tidigare filen. En sådan metod är dock sällsynt och bör undvikas.

- När du checkar ut innehåll från AEM-databasen och gör ändringar i det lokala systemet, kontrollerar du att filnamnet inte ändras när du överför filen.

## Använd FrameMaker

Adobe FrameMaker har en kraftfull AEM-anslutning som gör att du enkelt kan överföra dina befintliga DITA-dokument och andra FrameMaker-dokument `\(.book and .fm\)` till AEM. Du kan använda olika funktioner för filöverföring, till exempel för att överföra en fil, överföra en hel mapp med eller utan beroenden \(som innehållsreferenser, korsreferenser och bilder\).

Så här använder du FrameMaker AEM Connector för att överföra innehåll:

1. Starta FrameMaker.

1. Öppna dialogrutan **Anslutningshanteraren**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Ange följande information för att ansluta till AEM-databasen:

   - **Namn**: Ange ett beskrivande namn som identifierar anslutningen till din AEM-server.
   - **Server**: Ange URL-adressen och portnumret för din AEM-server.

   - **Användarnamn**/**Lösenord**: Ange användarnamn och lösenord för att komma åt AEM-servern.

1. Välj **Anslut**.

   När anslutningen har upprättats visas Assets från AEM-databasen i Databashanteraren.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Om du högerklickar på en fil eller mapp kan du utföra relaterade åtgärder. Om du till exempel högerklickar på en mapp får du alternativ för att överföra en fil, överföra filen med beroenden, överföra en hel mapp och så vidare.






**Överordnat ämne:**[ Migrera befintligt innehåll](migrate-content.md)
