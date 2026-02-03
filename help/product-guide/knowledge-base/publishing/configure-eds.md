---
title: Experience Manager Guides och Edge Delivery Services (Beta)
description: Förstå hur Edge Delivery Services (Beta) utvidgar möjligheterna för redigering och publicering i Experience Manager Guides.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 7ca2eeb0356f3c82a8d970f291006fc6d19aca23
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# Experience Manager Guides och Edge Delivery Services (Beta)

Med Adobe Experience Manager Guides kan du publicera ditt DITA-innehåll direkt till Edge Delivery Services (EDS), som för närvarande är tillgängligt i *Beta*, via en dedikerad GitHub-baserad publiceringsprofil. Med den här funktionen kan organisationer leverera högpresterande, responsiva dokumentationsupplevelser samtidigt som DITA-baserade arbetsflöden i Experience Manager Guides upprätthålls.

Mer information om hur du använder EDS i Adobe Experience Manager finns i [Edge Delivery Services Overview](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/edge-delivery/overview).

Om du vill aktivera publicering från Experience Manager Guides till EDS (Beta) måste du slutföra en serie konfigurationssteg i GitHub och Experience Manager Guides. I avsnitten nedan beskrivs varje steg i sekvensen och hur de fungerar tillsammans i det övergripande publiceringsarbetsflödet.

1. [Konfigurera GitHub för EDS (Beta)](#set-up-and-configure-github-for-eds-beta)
2. [Skapa och konfigurera en publiceringsprofil för EDS (Beta) i Experience Manager Guides](#create-and-configure-a-publish-profile-for-eds-beta-in-experience-manager)
3. [Anpassa utdata med EDS-block](#customize-output-using-eds-blocks)

Om du vill få en snabb genomgång av videon kan du visa [Publicera i AEM Guides](https://experienceleague.adobe.com/sv/docs/experience-manager-guides/using/knowledge-base/expert-session/publishing-in-aem-guides-aug25).



## Konfigurera GitHub för EDS (Beta)

I det här avsnittet beskrivs hur du konfigurerar och konfigurerar GitHub för EDS (Beta). Det handlar om att skapa en databas med Adobe-standardmallen, ansluta GitHub till Adobe Experience Manager via AEM Code Sync, konfigurera nödvändiga GitHub- och OAuth-program och definiera databasens monteringspunkt som används för publicering av innehåll.

### Skapa en GitHub-databas för EDS (Beta)

EDS (Beta) kräver en GitHub-databas med en fördefinierad struktur. Adobe har ett officiellt standardarkiv för Experience Manager Guides-användare.

Så här skapar du din databas:

1. Öppna Experience Manager Guides malldatabas [`aem-guides-boilerplate`](https://github.com/adobe/aem-guides-boilerplate).
   ![](assets/eds-boilerplate-template.png){align="left"}

2. Skapa en ny databas med den här mallen. Läs om [Skapa en databas från en mall](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template). Kontrollera att databassynligheten är inställd på *Offentlig* så att EDS kan komma åt den.

   ![](assets/eds-create-new-repo.png){align="left"}

Databasen skapas nu och justeras efter mallstrukturen för mallar.

![](assets/eds-repo-created-github-view.png){align="left"}

### Anslut GitHub till Adobe via AEM Code Sync

Adobe Experience Manager använder ett GitHub-program med namnet **AEM Code Sync** för att överföra innehåll från Experience Manager Guides till GitHub.

Så här installerar och konfigurerar du programmet *AEM Code Sync*:

1. Gå till sidan [AEM Code Sync](https://github.com/apps/aem-code-sync) och välj **Install**.
2. *AEM Code Sync* övervakar databasändringar och ser till att uppdateringar överförs korrekt till GitHub.

   >[!NOTE]
   >
   > Se till att du använder samma GitHub-konto som äger databasen när du installerar programmet.

   ![](assets/eds-aem-code-sync-page.png){align="left"}
3. På nästa sida ger du åtkomst till den databas du har skapat. Om du vill göra det väljer du alternativet **Markera endast databaser** och väljer sedan din databas i listrutan.

   ![](assets/eds-aem-code-sync-install-authorize.png){width="350" align="left"}
4. Välj **Installera och auktorisera**.

Du omdirigeras till installationssidan för GitHub, vilket bekräftar att registreringen av *AEM Code Sync* har slutförts. Du kan också spara URL:erna för förhandsgranskning och live för webbplatsen från den här sidan.

![](assets/eds-aem-code-sync-registered.png){align="left"}

### Skapa en ny GitHub-app

1. På GitHub går du till vänster sidofält och väljer **Utvecklarinställningar**.
2. Välj **GitHub-appar** i den vänstra sidofältet.
3. Välj **Ny GitHub-app**.

   ![](assets/eds-new-github-app.png){width="650" align="left"}
4. Ange följande information på sidan **Registrera ny GitHub-app**:
   - **GitHub-appnamn**: Ange ett namn för din app. Till exempel `USERNAME-eds-app` där USERNAME är ditt GitHub-användarnamn.
   - **URL för hemsida**: Ange URL:en till Experience Manager Guides-instansen.

     Exempel-URL (format): `https://<aem-author-url>/libs/fmdita/clientlibs/xmleditor/page.html`

     Exempel-URL: `https://author-p16602-e335172-cmstg.adobeaemcloud.com/libs/fmdita/clientlibs/xmleditor/page.html`
   - **Återanrops-URL**: Samma som URL:en för hemsidan.
   - **Webkroks-URL**: Inaktivera det här alternativet.
   - **Databasbehörigheter**: Ange **läs- och skrivbehörigheter** för *åtgärder, administration och attestering*.
5. Välj **Skapa GitHub-app**.

Din app är nu klar. Du omdirigeras till sidan **Inställningar** i din GitHub-app.

![](assets/eds-github-app-registered-page.png){align="left"}

### Skapa en ny OAuth-app

En OAuth-app krävs för att autentisera användare när en EDS-publiceringsprofil (Beta) skapas i Experience Manager Guides. Det aktiverar ett säkert inloggningsflöde med ett *klient-ID* och *klienthemlighet*.

Så här skapar du en ny OAuth-app:

1. På GitHub går du till vänster sidofält och väljer **Utvecklarinställningar**.
2. Välj **OAuth Apps** i den vänstra sidofältet.
3. Välj **Ny OAuth-app**.

   ![](assets/eds-new-oauth-app.png){width="650" align="left"}
4. Registrera din ansökan genom att ange följande obligatoriska uppgifter:
   - **Programnamn**: Ange namnet på din EDS-databas
   - **URL för hemsida**: Ange URL:en till Experience Manager Guides-instansen. (Exempel på URL-format finns i steg 4 i [Skapa ett nytt GitHub App](#create-a-new-github-app) -avsnitt).
   - **URL för auktoriseringsåteranrop**: Samma som URL för hemsida
5. Välj alternativet **Aktivera enhetsflöde** och välj sedan **Registrera program** för att slutföra registreringen.

   ![](assets/eds-new-github-app-register.png){width="650" align="left"}

Din app är nu klar. Anteckna *klient-ID*. Du kan generera upp till fem *klienthemligheter* nu eller senare när du konfigurerar publiceringsprofilen i Experience Manager Guides.

![](assets/eds-new-oauth-app-page.png){align="left"}


### Konfigurera monteringspunktens URL i EDS-databasen (Beta)

EDS (Beta) läser innehåll från en GitHub-databassökväg som definieras som en *monteringspunkt* -URL i `fstab.yaml`-filen.

Så här konfigurerar du monteringspunktens URL i filen `fstab.yaml`:

1. Öppna filen `fstab.yaml` i databasen och uppdatera följande:
   - `your-user-name`
   - `your-repo-name`

   >[!NOTE]
   >
   > I URL:en för monteringspunkten anger `main` den gren där du vill publicera innehållet och `docs` anger rotmappen för den EDS-databas (Beta) som du arbetar med. Om du föredrar att ändra filialnamnet på GitHub måste du uppdatera samma filialnamn i URL:en *Mountpoint* (i filen `fstab.yaml`) och motsvarande EDS-publiceringsprofil i Experience Manager Guides.

   ![](assets/eds-fstab-yaml-file.png){width="650" align="left"}
2. Välj **Verkställ ändringar**, ange implementeringsinformation och bekräfta.
3. Gå tillbaka till [Utvecklarinställningar](https://github.com/settings/apps), leta upp ditt program och välj **Redigera**.

   ![](assets/eds-edit-github-app.png){width="650" align="left"}
4. Navigera till sidan **Installera app** och välj **Installera**.

   ![](assets/eds-install-eds-app.png){width="650" align="left"}
5. Upprepa steg 2 och 3 i avsnittet [Anslut GitHub till Adobe via AEM Code Sync](#connect-github-to-adobe-via-aem-code-sync) för att auktorisera databasen.

## Skapa och konfigurera en publiceringsprofil för EDS (Beta) i Experience Manager

I avsnitten nedan beskrivs varje steg i sekvensen och hur du konfigurerar EDS-publiceringsprofilen (Beta), konfigurerar en förinställning för utdata och genererar utdata med EDS (Beta) i Experience Manager Guides.

### Skapa EDS-publiceringsprofilen (Beta)

1. Gå till **[Workspace-inställningar](/help/product-guide/cs-install-guide/workspace-settings.md)** **>** **Publiceringsprofiler**.
2. Välj ikonen **+** om du vill skapa en ny publiceringsprofil och ange följande information:
   - **Servertyp**: Välj **GitHub Edge Delivery Services (Beta)** i listrutan.
   - **Namn**: Ange ett namn för profilen.
   - **Databasnamn**: Använd GitHub-databasnamnet som har skapats från standardmallen.
   - **Användarnamn**: Ange ditt GitHub-användarnamn.
   - **Huvudgrenen**: Ange som huvudgrenen (standard).
   - **Rotmapp**: Ange som docs (standard).
   - **Klient-ID och klienthemlighet**: Hämta dessa från din GitHub-app (Mer information finns i [Skapa en ny OAuth-app](#create-a-new-oauth-app)).
3. Välj **Inloggning** för autentisering.

   ![](assets/eds-publish-profile.png){width="650" align="left"}
4. Välj **Spara** när autentiseringen är klar.

Din EDS-publiceringsprofil (Beta) är nu konfigurerad.

### Skapa en utdataförinställning för EDS (Beta) och generera utdata

1. Öppna kartan i kartkonsolen.
2. Välj **+** på fliken **Utdataförinställningar** om du vill skapa en ny utdataförinställning.
3. Ange följande information i dialogrutan **Ny förinställning**:
   - **Typ**: Välj **Edge Delivery-tjänst (Beta)**
   - **Namn**: Ange ett namn för förinställningen
4. Välj **Lägg till**.

   ![](assets/eds-output-preset.png){width="650" align="left"}
5. Öppna den nya EDS-förinställningen (Beta) och gå till fliken **Konfiguration**.
   - Välj den publiceringsprofil som skapades i föregående steg.
   - Aktivera **Push to live**.

   När **Push to live** är aktiverat verkställs de genererade utdata till GitHub, och motsvarande uppdateringar sprids omedelbart till den aktiva webbplatsen.

   ![](assets/eds-output-preset-config-tab.png){width="650" align="left"}

6. Välj **Spara** och sedan **Generera utdata**.

>[!NOTE]
>
> De genererade utdata lagras i mappen **docs** i EDS-databasen (Beta).

EDS-utdata (Beta) genereras nu. Innehållet presenteras i en ren, responsiv layout. Den innehåller vanliga element som sidtitel, vägbeskrivningar, brödtext och eventuella block som används i ämnet. Innehållsförteckningen till vänster (genereras från kartan) hjälper dig att navigera mellan ämnen, medan en miniinnehållsförteckning till höger markerar avsnitten på den aktuella sidan. Hela resultatet är helt responsivt, vilket ger en optimerad och enhetlig läsupplevelse på alla enheter.

![](assets/eds-site-output.png){align="left"}

## Anpassa utdata med EDS-block

EDS använder `blocks` för att styra hur olika delar av ditt innehåll formateras och visas. Du kan ändra befintliga block eller skapa anpassade.

De exempel som beskrivs nedan visar hur du anpassar ett befintligt block och skapar ett nytt block som formaterar det slutliga EDS-resultatet (Beta) i Experience Manager Guides.

### Anpassa ett vägbeskrivningsblock för att uppdatera textfärgen

Brödkrummar används på flera sidor för att hjälpa användarna att förstå var de finns i dokumentationen. Eftersom det här blocket visas enhetligt på hela webbplatsen kan en enhetlig designuppdatering göras om formatet uppdateras.

Följ de här stegen för att anpassa ett vägbeskrivningsblock för att uppdatera textfärgen:

1. Gå till din GitHub-databas och öppna mappen `blocks`.
2. Markera blocket **breadcrumbs**.

   ![](assets/eds-breadcrumbs.png){width="650" align="left"}
3. Öppna filen `css` och uppdatera textfärgen.
4. Verkställ ändringarna av GitHub.
5. Uppdatera den publicerade webbplatsen för att visa uppdateringarna.

### Uppdatera EDS-skript (Beta) för att skapa anpassade element i publicerade utdata

I vissa fall kanske du bara vill formatera en viss del av innehållet. Utför följande steg för att uppnå detta med ett anpassat block.

1. Öppna ämnesfilen och markera texten i ett taggelement.

   På följande skärmbild markeras innehållet i taggen `example`.
   ![](assets/eds-example-tag-org-output.png){width="650" align="left"}
2. Så här konfigurerar du texten i taggen `example`:
   - Navigera till **Innehållsegenskaper**.
   - Lägg till attributet `outputclass`.
   - Ange värdet till `example eds-force-block`.
   - Välj **Lägg till**.
     ![](assets/eds-example-tag.png){width="650" align="left"}
3. Spara och generera om utdata.
4. Skapa en ny mapp med samma namn som `outputclass` i katalogen `blocks`. Lär dig mer om att [lägga till filer i en databas](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository#adding-a-file-to-a-repository-using-the-command-line).

   ![](assets/eds-example-folder.png){width="650" align="left"}
5. Lägg till de nödvändiga `css`- och valfria `js`-filerna.

   ![](assets/eds-example-folder-subfolders.png){width="650" align="left"}
6. Genomför ändringar och återskapa utdata.

Det markerade innehållet visar nu den anpassade formateringen som definierats i blocket.

![](assets/eds-example-output.png){width="650" align="left"}