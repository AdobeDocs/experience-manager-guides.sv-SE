---
title: Syrgas-plugin för Adobe Experience Manager Guides
description: Lär dig hur du använder Syre Plugin för Adobe Experience Manager Guides för att skapa och hantera ditt innehåll.
hide: true
hidefromtoc: true
exl-id: 9a140564-27eb-404e-93a5-f5c81364e7f7
feature: Oxygen Plugin, Authoring, Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '6294'
ht-degree: 0%

---

# Syrgas-plugin för Adobe Experience Manager Guides {#id1645H6010Q5}

Med Syrgas-pluginen för Adobe Experience Manager Guides \(kallas senare för Syrgas-plugin för AEM Guides i guiden\) kan du ansluta Syrgas-XML-författaren till Adobe Experience Manager \(AEM\)-databasen för att skapa och hantera innehåll. Du kan använda plugin-programmet för att bläddra bland, söka efter och öppna filer, checka ut och in filer, överföra mappar och filer AEM databasen. På panelen AEM stödlinjer i skrivbordsprogrammet kan du markera önskade mappar \(från AEM databas\) i listan med favoritmappar så att du snabbt kommer åt dem. Dessutom kan du installera ett paket i AEM webbgränssnitt och öppna DITA-filerna i Sygen XML Author direkt från AEM webbgränssnitt.

## Hämta och installera {#id1826M0L0PUI}

Syrgas-pluginen för AEM-guider är tillgänglig via Adobe Software Distribution Portal. Sök efter&quot;syre&quot; på fliken Experience Manager och hämta plugin-installationsprogrammet från [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).

>[!NOTE]
>
>Kontrollera versionskompatibiliteten för Syrgasanslutning i versionsinformationen för de specifika Adobe Experience Manager-guiderna.

När du har installerat installationsprogrammet installerar du det på den lokala datorn där syre-XML-författaren är installerad. Innan du påbörjar installationen måste du se till att systemet uppfyller de tekniska kraven för att installera syrgas-plugin för AEM.

### Tekniska krav

- Syrgas-XML-författare version 25.1

- Adobe Experience Manager Guides version 4.3 eller senare

- Adobe Experience Manager version 6.5 med Service Pack 14, 15, 16 och 17

- Operativsystem som stöds av Sygen XML Author version 25.1

- Java Development Kit
   - Oracle SE 8 JRE 1.8

### Installera plugin-programmet i Windows

>[!IMPORTANT]
>
>Om du har en äldre version av plugin-programmet installerad på datorn måste du avinstallera det innan du startar installationsprocessen. Se **Avinstallerar paket** i [Så här arbetar du med paket](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) artikel för avinstallationsanvisningar.

Utför följande steg på datorn där Oxygen XML Author är installerat:

1. Starta installationsprogrammets `.exe` -fil.

   Installationsguidens välkomstskärm visas.

1. Klicka **Nästa** och bläddra till den plats där .exe-filen för Sygen XML Author finns tillgänglig.

1. Markera filen och klicka på **Öppna**.

   Den valda filens plats läggs till i installationsguiden.

1. Klicka på **Nästa**.

1. Klicka **Installera**.

1. Klicka **Slutför** för att stänga installationsguiden.
1. Starta Syrgas XML Author.

   Panelen AEM stödlinjer visas i Syrgas XML-författare.

   ![AEM](images/oxygen-aem-connector.png){width="800" align="left"}

   >[!NOTE]
   >
   >Om du inte ser panelen AEM stödlinjer läser du i felsökningsavsnittet -[Panelen AEM stödlinjer saknas](#id192BH200ZAX).


### Installera plugin-programmet på Mac

>[!IMPORTANT]
>
>Om du har en äldre version av plugin-programmet installerad på datorn måste du avinstallera det innan du startar installationsprocessen. Se **Avinstallerar paket** i [Så här arbetar du med paket](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) anvisningar för artikelavinstallation.

Utför följande steg på datorn där Oxygen XML Author är installerat:

1. Leta reda på plugin-programmets .dmg-fil på datorn.

1. Dubbelklicka på .dmg-filen för att öppna filinnehållet.

   DMG-filen innehåller en mapp av typen aem-connector-x.x och en aem-connector-x.x-setup.

   >[!NOTE]
   >
   >x.x i filnamnet är plugin-programmets versionsnummer.

1. Kopiera mappen aem-connector-x.x i mappen plugins i Oxygen XML Author.
1. Dubbelklicka på filen aem-connector-x.x-setup för att starta installationsprogrammet.

1. Starta Syrgas XML Author.

   Panelen AEM stödlinjer visas i Syrgas XML-författare.

   ![AEM Connector Mac](images/oxygen-aem-connector-mac.png) {width="800" align="left"}

   >[!NOTE]
   >
   >Om du inte ser panelen AEM stödlinjer läser du i felsökningsavsnittet -[Panelen AEM stödlinjer saknas](#id192BH200ZAX).


### Installera paketet för att aktivera dokumentredigeringsfunktionen från AEM webbgränssnitt {#id182CE0Q0TY4}

Som författare kan du öppna och redigera dina DITA-kartor eller ämnen i Sygen XML Author direkt från AEM webbgränssnitt. Om du vill aktivera den här funktionen i AEM webbgränssnitt måste AEM-administratören installera ett paket i den AEM utvecklingsinstansen.

Som AEM administratör följer du de här stegen för att installera paketet:

1. Hämta paketets ZIP-fil från IT-avdelningen.
1. Logga in i AEM *\(som administratör\)* och navigera till CRX Package Manager. Standardwebbadressen för att få åtkomst till pakethanteraren är

   `http://<server name>:<port>/crx/packmgr/index.jsp`

   Pakethanteraren hanterar paketen i din lokala AEM. Mer information om hur du arbetar med Pakethanteraren finns i [Så här arbetar du med paket](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developer-tools/package-manager.html?lang=en) i AEM.

   ![Pakethanterare](images/package-manager.png) {width="650" align="left"}

1. Om du vill ladda upp syrgaspaketet klickar du på **Överför paket**.
1. I dialogrutan Överför paket navigerar du till syrepaketfilen som du hämtade i steg 1 och klickar på OK.

   Paketet överförs till din AEM.

1. Klicka på **Installera**.

   ![Syrgaspaket](images/oxygen-package.png){width="650" align="left"}

1. I dialogrutan Installera paket klickar du på **Installera**.
1. När installationen är klar klickar du på hemknappen i det övre vänstra hörnet av CRX Package Manager.
1. Välj en DITA-fil i resursmappen.

   **Redigera i syrgas** är tillgängligt i verktygsfältet. Mer information om hur du använder det här alternativet finns i [Öppna DITA-avsnittet i Sygen XML Author från AEM webbgränssnitt](#id182CE0I905Z).

   >[!NOTE]
   >
   >The **Redigera i syrgas** är synligt när du markerar ett DITA-avsnitt. Om du markerar flera ämnen visas inte alternativet.


## Konfigurera syrgas-plugin-programmet för AEM {#id1826KF00AHS}

När du har hämtat och installerat plugin-programmet måste du konfigurera följande så att det fungerar med plugin-programmet:

- **Inställningar för webbautentisering**: Inställningar för SSO-autentisering i plugin-programmet för AEM guider.
- **Allmänna inställningar**: Anslutningsinställningar för plugin-programmet, till exempel AEM server-URL, inloggningsinformation osv.
- **Inställningar för anpassning av profilattribut och filnamn i korsreferenser**: Den här konfigurationen krävs för profileringsattributscheman för dokumentationsuppsättningarna.

### Inställningar för webbautentisering

JxBrowser används för SSO-autentisering av syreanslutningens plugin. Det är en krombaserad webbläsare. För java 9+ krävs åtkomst till icke-publika API:er, och du måste uttryckligen ge åtkomst till JxBrowser. Mer information finns i [JxBrowser - felsökning](https://jxbrowser-support.teamdev.com/docs/guides/troubleshooting/issues.html).

Uppdatera de angivna filerna för att konfigurera inställningarna för webbautentisering i Syrgas-pluginprogrammet för AEM stödlinjer:

>[!NOTE]
>
>Säkerhetskopiera filen innan du uppdaterar den.

**För Mac och syrgas 25.1**

Lägg till följande rader i env.sh

```java
--illegal-access=permit\
--add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED\
--add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED\
--add-exports=java.desktop/sun.awt=ALL-UNNAMED\
--add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Lägg till följande rader i syreAuthor.sh

```java
-Djdk.module.illegalAccess=permit\-Djava.ipc.external=true\
```

**För Windows och syrgas 25.1**

Lägg till följande rader i env.bat

```java
--illegal-access=permit --add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED --add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED --add-exports=java.desktop/sun.awt=ALL-UNNAMED --add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Lägg till följande rader i syreAuthor.bat

```java
-Djdk.module.illegalAccess=permit -Djava.ipc.external=true
```

>[!NOTE]
>
>Du måste köra syre från syreAuthor.sh för Mac och syreAuthor.bat för Windows som administratör.

### Allmänna inställningar

Utför följande steg för att konfigurera anslutningsinställningarna i Syrgas-plugin-programmet för Adobe Experience Manager-guider:

1. Klicka på inställningsikonen på panelen AEM stödlinjer och välj sedan **Inställningar**.

   ![Anslutningsinställningar ](images/settings.png){width="800" align="left"}

1. Ange följande information:
   - **Server-URL**: URL för AEM server, till exempel:

     ```http
     http[s]://<host>:<port>
     ```

     Ange värdnamnet och porten för servern där AEM distribueras i ovanstående URL.

     >[!IMPORTANT]
     >
     >Om AEM distribueras på port 80 eller 443 behöver du inte ange den i URL:en.

   - **Autentisering:** Välj från **Grundläggande \(användarnamn/lösenord\)** eller **Webbautentisering**. Om du väljer **Grundläggande** autentisering som du måste ange **Användarnamn** och **Lösenord** i dialogrutan Inställningar.

     Om du väljer Webbautentisering visas AEM inloggningsskärm. Ange dina inloggningsuppgifter och klicka på **Logga in** -knappen. När inloggningen är klar stängs AEM inloggningsskärmen och panelen AEM guider visar fillistan från den AEM servern.

   - **Tidsgräns för anslutning**: Ange hur många sekunder klienten ska vänta på ett svar från AEM server. Om inget svar från servern tas emot inom den angivna tiden avslutas begäran. Standardvärdet är 20 sekunder.

   - **Lokal mapp**: Plats på din lokala dator där filerna från AEM sparas efter utcheckning. Om du anger en plats som inte finns på enheten skapas platsen av plugin-programmet.
   - **Öppna fil när utcheckad**: Om du väljer det här alternativet öppnas filerna i kassan.
   - **Stäng filen vid incheckning**: Om du väljer det här alternativet stängs filerna vid incheckning. Innan du stänger filen visas ett popup-fönster där du kan ange versionskommentarerna.
   - **Visa dialogrutan Checka in när filen stängs**: Om du väljer det här alternativet visas ett popup-fönster när du stänger en fil. I popup-fönstret kan du välja att checka in filen eller stänga filen utan att checka in den.
   - **Automatisk utcheckning av fil när den öppnas**: Om det här alternativet är markerat checkas den ut automatiskt när du dubbelklickar på en fil och öppnas för redigering. Om filen redan är utcheckad öppnas den helt enkelt för redigering. Om det här alternativet inte är markerat öppnas en fil som du inte har ett lås i skrivskyddat läge när du öppnar den.
1. Klicka **OK**.

### Inställningar för anpassning av profilattribut och filnamn i korsreferenser {#id1827K0D0OHT}

Du måste konfigurera inställningarna i Sygen XML Author för att använda profileringsattributet som är kopplat till DITA-avsnitten i AEM. Du måste också konfigurera inställningen för att visa filnamn i stället för GUID i korsreferenserna.

Utför följande steg för att konfigurera profileringsattribut och korsreferenser:

1. I Syrgas XML Author klickar du på **Alternativ** \> **Inställningar**.
1. I **Dokumenttypsassociation** flik, välja **DITA** och klicka sedan på **Utöka**.

   ![dokumenttypsassociation](images/document_type_association.png){width="650" align="left"}

1. I **Klassökväg** flik, välja `com.adobe.o2.connector` i **Använd inläsare för överordnad klass från plugin-program med ID** nedrullningsbar meny.

   ![Fliken Klasssökväg](images/dita-extension.png){width="650" align="left"}

1. I **Tillägg** gör du följande ändringar:

   - Klicka **Välj** bredvid **Tillägg** och markera   `LinkResolverExtensionBundle - com.adobe.o2.framework.extn` i **Klass** lista. Klicka **OK**.
     ![Konfigurerat tillägg för DITA-avsnitt](images/dita-map-extenstion-link-resolve.png) {width="650" align="left"}
   - Klicka **Välj** bredvid **Avlyssnare för författartilläggsstatus** under **Individuella tillägg** och markera `CustomAuthorExtensionStateListener - com.adobe.o2.framework.extn` i **Klass** lista. Klicka **OK**.
   - Klicka **Välj** bredvid **Redigerare för anpassat attributvärde** under **Individuella tillägg** och markera `CustomValueEditor - com.adobe.o2.framework.extn` i **Klass** lista. Klicka **OK**.
   - Klicka **Välj** bredvid **Skapa en extern hanterare för objektinfogning** under **Individuella tillägg** och markera `CustomURLInsertionHandler - com.adobe.o2.ui ` i **Klass** lista. Klicka **OK**.


   På följande skärmbild visas den konfigurerade **Tillägg** för DITA-ämnen:
   <img src="images/dita-topic-extension-tab.png" alt="Konfigurerat tillägg för DITA-avsnitt" width="650" border="2px">
1. Klicka **OK** i alla dialogrutor för att spara ändringarna.

### Konfigurera DITA-mappningstillägg

Konfiguration av DITA-mappningstillägg krävs för att aktivera öppning av mappningsfiler i Sygen XML Author direkt från AEM webbgränssnitt. Dessa konfigurationer liknar konfigurationerna för profileringsattribut som gjordes i föregående procedur.

Utför följande steg för att konfigurera DITA-mappningstillägget:

1. I Syrgas XML Author klickar du på **Alternativ** \> **Inställningar**.
1. I **Dokumenttypsassociation** flik, välja **DITA-karta** och klicka sedan på **Utöka**.
1. I **Klassökväg** väljer du com.adobe.o2.connector i **Använd inläsare för överordnad klass från plugin-program med ID** nedrullningsbar meny.
1. I **Tillägg** gör du följande ändringar:
   - Klicka **Välj** bredvid **Tillägg** och markera   `com.adobe.o2.framework.extn.LinkResolverDITAMapExtensionBundle` i **Klass** lista. Klicka **OK**.

   - Klicka **Välj** bredvid **Avlyssnare för författartilläggsstatus** under **Individuella tillägg** och markera `CustomDITAMapAuthorExtensionStateListener - com.adobe.o2.framework.extn` i **Klass** lista. Klicka **OK**.

   - Klicka **Välj** bredvid **Skapa en extern hanterare för objektinfogning** under **Individuella tillägg** och markera `CustomURLInsertionHandler - com.adobe.o2.ui ` i **Klass** lista. Klicka **OK**.

   - Klicka **Välj** bredvid **Redigerare för anpassat attributvärde** under **Individuella tillägg** och markera `CustomValueEditor - com.adobe.o2.framework.extn` i **Klass** lista. Klicka **OK**.

   - Klicka **Välj** bredvid **Referenslösare** under **Individuella tillägg** och markera `CustomDITAMapReferenceResolver - com.adobe.o2` i **Klass** lista. Klicka **OK**.
   - *\(Valfritt\)* Om du inte vill lösa referenser när du öppnar en kartfil måste du göra följande ytterligare konfiguration:

   På följande skärmbild visas den konfigurerade **Tillägg** tab:
   <img src="images/dita-map-extension-tab.png" alt="Konfigurerat tillägg för DITA-karta" width="650" border="2px">

1. Klicka **OK** i alla dialogrutor för att spara ändringarna.

## Arbeta med Sygen Plugin för AEM Guides {#id1826JG00WY4}

### AEM stödlinjer, panel

På följande skärm visas AEM stödlinjepanelen.

![kopplingspanelen](images/connector-panel.png){width="550" align="left"}

**A**\) Visar sökfältet.

**B**\) Visar mappen Favoriter. Som standard är den tom. Du kan lägga till mappar från AEM databas som favoriter. Favoritmappar visas här.

**C**\) DAM-mappen visar AEM. Du kan expandera och komprimera mappvyn.

**D**\) Ikonen Inställningar \(kugghjul\) med följande alternativ:

- **Anslut**: Välj det här alternativet om du vill ansluta till AEM. Alternativet är inaktiverat när Sygen XML Author är ansluten till AEM Server.
- **Uppdatera**: Välj det här alternativet om du vill få den senaste statusen för filerna och mappen från AEM.

  >[!NOTE]
  >
  >Spara filerna innan du uppdaterar dem. När du väljer **Uppdatera** får du en varning om att spara filerna innan du uppdaterar dem. Om du inte har sparat dina filer kan du klicka på **Avbryt** och spara dem.

- **Inställningar**: Du kan använda det här alternativet för att öppna den allmänna dialogrutan Inställningar för plugin-programmet.
- **Utloggning**: Välj det här alternativet om du vill stänga AEM serveranslutning. Det här alternativet är bara tillgängligt om du använder läget Webbautentisering.

### Funktioner på snabbmenyn

Funktionerna för Sygen-plugin-programmet för AEM stödlinjer är tillgängliga när du högerklickar på en mapp eller fil i AEM. De funktioner som är tillgängliga för mapparna skiljer sig från filerna. Här är en fullständig lista över funktioner i Sygen Plugin för AEM Guides-snabbmenyn:

- **Öppna**: Öppnar den markerade filen eller visar den markerade mappen.
- **Öppna i**: Du kan välja att öppna den markerade filen i AEM webbredigeraren eller kartkontrollpanelen, eller i kartredigeraren. Mer information om de här alternativen finns i [Öppna filen i AEM redigerare](#id195GH0V30KX).
- **Checka ut**: Checkar ut en fil från AEM. Mer information finns i [Checka ut filer](#id195HC020TS4).
- **Checka ut med beroenden**: Checkar ut en fil med dess direkta referenser. Mer information finns i [Checka ut filer](#id195HC020TS4).
- **Checka ut med skrivskyddade beroenden**: Checkar ut den markerade filen tillsammans med tillhörande beroenden. Du kan inte göra några ändringar i de beroende filerna. Mer information finns i [Checka ut filer](#id195HC020TS4).
- **Avbryt utcheckning**: Avbryter den utcheckade filen, stänger filen från redigeraren och återställer ändringarna till den senaste versionen av filen som sparats på servern.
- **Uppdatera**: Om det är en fil, hämtar den senaste kopian av filen från AEM. För en mapp hämtas mappstrukturen och filens status. Det innebär att en fil läggs till och sedan visas den i vyn AEM stödlinjer. Om en fil är utcheckad på AEM server visas filen som utcheckad när du uppdaterar i Syrgasförfattaren. Detta uppdaterar dock inte fillistan i *Utcheckade filer i AEM* Visa.
- **Uppdatera utcheckade filer**: Uppdaterar listan över utcheckade filer i *Utcheckade filer i AEM* Visa. Om en fil är utcheckad på AEM server uppdateras listan med utcheckade filer i *Utcheckade filer i AEM* Visa. Om en ny fil har lagts till eller status för en fil har ändrats, uppdateras den inte i trädvyn AEM stödlinjer. Om du vill uppdatera status för filer på AEM måste du göra en uppdatering.
- **Checka in**: Checkar in filer som du har checkat ut. Mer information finns i [Checka in en fil](#id182CF0J0FHS).
- **Checka in med beroenden**: Om du har checkat ut filer med beroenden checkar det här alternativet in huvudfilen tillsammans med tillhörande beroenden. Mer information finns i [Checka in en fil](#id182CF0J0FHS).
- **Skapa mapp**: Skapar en mapp i AEM. Det här alternativet är bara tillgängligt på mappnivå.
- **Överför fil\(er\)**: Överför en eller flera filer. Mer information finns i [Överför filer och mappar](#id195HC03F03J).
- **Överför med beroenden**: Överför DITA-filer \(XML, DITA, Book map eller DITA map\) med tillhörande beroenden. Mer information finns i [Överför filer och mappar](#id195HC03F03J).
- **Överför mapp**: Överför en mapp till AEM. Mer information finns i [Överför filer och mappar](#id195HC03F03J).
- **Lägg till i Favoriter**: Lägger till en mapp i *Favoriter* i AEM på stödlinjepanelen. Vi rekommenderar att du lägger till din arbetsmapp här, vilket gör det enklare att synkronisera filer och filens status från AEM.
- **Ta bort från Favoriter**: Tar bort en mapp från *Favoriter*. Mer information finns i [Lägg till eller ta bort favoriter](#id195HC04405P).
- **Visa metadata**: Visar metadata som DITA-klass, dokumentets titel, typ, UUID och annan information som är kopplad till en fil. Mer information finns i [Visa metadata för en fil](#id195GHN0H05C).
- **Visa versioner**: Visar versionshistoriken för en fil. Mer information finns i [Visa versionshistorik för en fil](#id195GI000D5Q).

### Öppna en fil i Sygen XML Author {#id195GHJ0A0UB}

När du har anslutit till AEM kan du öppna filer för redigering i Sygen XML Author. Så här öppnar du en fil för redigering i Sygen XML Author:

1. Högerklicka på en fil på panelen AEM stödlinjer som du vill öppna för redigering.

1. Välj **Öppna** på snabbmenyn.

   Filen öppnas i redigeraren i Sygen XML Author.

   ![Guid i filflik](images/guid-in-file-tab.png) {width="800" align="left"}

   När du håller muspekaren över en fils flik visas serversökvägen tillsammans med dess UUID. I skärmbilden ovan markeras dokumentets UUID.


Om du har valt **Automatisk utcheckning av fil när den öppnas** när du öppnar en fil, blir filen automatiskt utcheckad och tillgänglig för redigering. Om du vill öppna en fil kan du antingen dubbelklicka på ett filnamn eller högerklicka på filnamnet och välja **Öppna** på snabbmenyn. Om det här alternativet inte är markerat öppnas filen i skrivskyddat läge.

>[!NOTE]
>
>Du kan också dubbelklicka på en fil för att öppna den.

### Öppna filen i AEM redigerare {#id195GH0V30KX}

Om du vill använda de redigeringsprogram som är tillgängliga AEM stödlinjerna kan du göra det genom att välja önskat alternativ på snabbmenyn. Utför följande steg för att använda AEM Guides redigerare i stället för Sygen XML Authors redigerare:

1. Högerklicka på en fil på panelen AEM stödlinjer som du vill öppna för redigering.

1. Välj **Öppna i** på snabbmenyn och välj bland följande alternativ:

   - **Webbämnesredigerare**: Om filen du öppnar är en .xml- eller .dita-fil kan du öppna den för redigering i webbredigeraren. Välj **Webbämnesredigerare** om du vill öppna den markerade filen för redigering i Web Editor.

   - **Kartkontrollpanel**: Du kan välja att redigera en .ditamap-fil på kartkontrollpanelen, där du kan utföra olika åtgärder på kartfilen. De här åtgärderna är beroende av rollen/gruppen som du tillhör.

   - **Web DITA Map Editor**: Om du vill öppna .ditamap-filen för redigering i kartredigeraren väljer du det här alternativet. Med alternativet DITA Map Editor kan du lägga till eller ta bort ämnen, lägga till relationstabeller och utföra andra åtgärder på kartan.


### Checka ut filer {#id195HC020TS4}

När du checkar ut en fil lagras den lokalt på datorn och låses för redigering i AEM. Så här checkar du ut en fil:

1. Du kan checka ut dina filer på något av följande sätt:
   - Högerklicka på en fil på panelen AEM stödlinjer.
   - Högerklicka på kartfliken på panelen DITA Maps Manager.
   - Högerklicka på en fil på DITA Maps Manager-panelen.
   - Högerklicka på filfliken när du öppnar en karta eller ett ämne i Redigeraren.

1. Välj något av följande alternativ:
   - **Checka ut:** Checkar ut en fil AEM databasen och gör den tillgänglig för redigering.
   - **Checka ut med beroenden**: Checkar ut en fil med dess direkta referenser. Du kan göra ändringar på överordnade och underordnade sidor med det här alternativet. Syrgas-plugin för AEM stödlinjer har stöd för att checka ut en nivå av beroende. Karta A refererar till exempel till ämne A och ämne A refererar till ämne B. Om du checkar ut karta A checkas ämne A ut oavsett nivå i TOC-hierarkin. Ämne B kommer dock inte att checkas ut eftersom det inte är direkt länkat från A-karta.
   - **Checka ut med skrivskyddade beroenden**: Checkar ut en fil och hämtar dess beroenden till den lokala datorn som skrivskyddade kopior. Du kan inte göra några ändringar i de beroende filerna.

Om du har valt **Öppna filer vid utcheckning** om du väljer \(i dialogrutan Inställningar\) öppnas filen automatiskt för redigering när du checkar ut en fil.

Om du har valt **Automatisk utcheckning av fil när den öppnas** när du öppnar filen checkas filen ut automatiskt och blir tillgänglig för redigering. Om du vill öppna en fil kan du antingen dubbelklicka på ett filnamn eller högerklicka på filnamnet och välja **Öppna** på snabbmenyn.

När en fil är utcheckad ändras ikonen för filen så att dess låsta status visas.

![Checka ut en fil](images/check-out-file.png){width="650" align="left"}

På skärmbilden ovan visas en fil som har checkats ut av en annan användare med en svart låsikon \(A\). Filen som har checkats ut av den aktuella användaren visas med ett grönt lås \(B\).

>[!NOTE]
>
>Om den utcheckade filen tas bort eller flyttas till en annan mapp i AEM visas ett felmeddelande när du checkar in filen. Kontrollera att den utcheckade filen inte flyttas eller tas bort med AEM webbgränssnitt.

### Checka in en fil {#id182CF0J0FHS}

När du checkar in en fil lagras den lokala kopian från systemet i AEM och fillåset tas bort. Utför följande steg för att checka in en fil:

1. Spara filen genom att klicka på **Fil** \> **Spara**.

1. Högerklicka på en utcheckad fil eller karta på någon av följande platser:
   - AEM stödlinjer, panel
   - Panelen DITA Maps Manager
   - Filfliken när du öppnar en karta eller ett ämne i Redigeraren.
   - Fliken Karta i DITA Maps Manager-panelen.

1. Välj mellan följande två alternativ:

   - **Checka in**: Checkar in den valda filen från ditt lokala system i AEM.
   - **Checka in med beroende:** Om du har checkat ut en fil tillsammans med dess underordnade filer, använder du det här alternativet för att checka in alla beroende filer i en enda åtgärd. När du väljer det här alternativet visas dialogrutan Checka in med alla beroende filer. Klicka på OK om du vill checka in alla filer samtidigt.

   Om du inte har checkat ut beroende filer och sedan väljer det här alternativet checkas bara de beroende filerna som du har \(separat\) utcheckade in. En lista över filer som inte kunde checkas in visas:

   ![incheckningsfel](images/check-in-error.png){width="800" align="left"}

   Vi rekommenderar att du inte flyttar en fil som är utcheckad. Om en utcheckad fil flyttas till en annan plats måste du dock avbryta utcheckningen av filen. Om du vill uppdatera filen checkar du ut den igen, gör ändringar och checkar sedan in den igen. Om du försöker checka in en fil som har flyttats från den ursprungliga platsen visas ett fel.

   Om en beroende fil är utcheckad i AEM visas inte den beroende filen i dialogrutan Checka in med beroende. Om du vill visa en lista över beroende filer som är utcheckade i AEM måste du göra en mappuppdatering.

   Om du har checkat in en beroende fil via AEM uppdateras inte fillistan i Syrgasförfattaren förrän du uppdaterar mappen Uppdatera och Uppdatera utcheckade filer. Om du gör en incheckning med beroende med vissa filer incheckade AEM visas ett felmeddelande med en lista över de filer som inte kunde checkas in.

1. \(Valfritt\) I dialogrutan **Checka in** eller **Checka in med beroende** dialogruta, lägga till en kommentar i **Versionskommentar** textruta.

   >[!NOTE]
   >
   >Den här kommentaren visas i filens AEM versionshistorik.

1. Lägg till etiketter i **Etikett** textrutan i **Checka in** eller **Checka in med beroende** dialogruta . Ange en etikett och tryck på Enter. Till exempel: *2307 års utgåva*.

   Om administratören har fördefinierat en lista över etiketter och överfört dem till `label.json` så visas etiketterna som en listruta. Du kan välja en eller flera etiketter i listrutan.

   ![Dialogrutan Checka in](images/checkin-dropdown-labels.png){width="550" align="left"}

   Du kan lägga till flera etiketter (avgränsade med kommatecken) i samma version av ett ämne.  Till exempel: *Adobe*, *AEM*, *Stödlinjer*.
Du kan dock inte lägga till samma etikett till olika versioner av ett ämne. Om du lägger till en etikett som du redan har lagt till i en tidigare version läggs den till i den senaste versionen och tas bort från den tidigare versionen.

   >[!NOTE]
   > 
   > Dessa etiketter visas i filens AEM versionshistorik.


1. Klicka **OK**.

>[!NOTE]
>
>Om den utcheckade filen tas bort eller flyttas till en annan mapp i AEM visas ett felmeddelande när du checkar in filen. Kontrollera att den utcheckade filen inte flyttas eller tas bort med AEM webbgränssnitt.

### Utcheckade filer AEM vyn Stödlinjer

När du har flera mappar är det inte lätt att ta reda på hur många filer som är utcheckade i en vy. AEM innehåller utcheckade filer AEM vyn Stödlinjer, som ger en fullständig ögonblicksbild av de utcheckade filerna. I den här vyn kan du enkelt ta reda på vilka filer som har checkats in av dig i AEM med hjälp av AEM. Utför följande steg för att komma åt och arbeta med den här vyn:

1. Klicka **Fönster** \> **Visa vy** \> **Utcheckade filer i AEM**.

   Utcheckad fil AEM vyn Stödlinjer visas.

   ![utcheckade filer](images/files-checkedout-view.png){width="550" align="left"}

1. Högerklicka på en fil i den här vyn för att få följande alternativ:

   - [Öppna](#id195GH0V30KX)
   - [Öppna i](#id195GH0V30KX)
   - Avbryt utcheckning
   - [Checka in](#id182CF0J0FHS)
   - [Checka in med beroende](#id182CF0J0FHS)
   - [Visa metadata](#id195GHN0H05C)
   - [Visa versioner](#id195GI000D5Q)

**Anteckningar om utcheckade filer AEM vyn över stödlinjer:**

- The *Utcheckade filer i AEM* Visa underhåller användarens sessioner. Detta innebär att filer som checkas ut av den aktuella användaren lagras och underhålls i vyn över samma användares sessioner \(eller cache\).

- Om användaren ändrar inloggningsuppgifterna eller AEM server återställs den utcheckade filens data \(eller cache\) i vyn. Användaren måste köra en *Uppdatera utcheckade filer* för varje mapp där filerna tidigare var utcheckade. Du bör lägga till dina arbetsmappar i *Favoriter* där du snabbt kan göra en mappuppdatering.

- Du kan sortera fillistan utifrån filnamn, titel eller sökväg. Om en ny fil är utcheckad visas filen i sorterad ordning i vyn.


### Överför filer och mappar {#id195HC03F03J}

Så här överför du filer eller mappar:

1. Högerklicka på en mapp på panelen AEM stödlinjer.
1. Välj något av följande alternativ:
   - **Överför fil\(er\)**: Välj det här alternativet om du vill överföra en eller flera filer till den valda mappen i AEM. I dialogrutan Välj filer \(er\) att överföra markerar du filerna och klickar på **Öppna**.
   - **Överför med beroenden**: Välj det här alternativet om du vill överföra en DITA-fil med tillhörande beroenden. Markera filerna i dialogrutan Välj den fil som ska överföras och klicka på **Öppna**.
   - **Överför mapp**: Välj det här alternativet om du vill överföra en mapp i AEM. I dialogrutan Välj markerar du mappen och klickar på **Välj**.

**Ytterligare information om att arbeta med UUID-baserade filer**:

Följande punkter måste beaktas när innehåll flyttas eller kopieras från ditt lokala system till AEM:

- När du överför en eller flera filer genereras ett nytt UUID för filer som inte har något UUID. Detta UUID läggs till i `topic id` av en DITA-fil.

- När du kopierar en mapp uppdateras referenserna till filerna \(i mappen\) automatiskt i alla DITA-mappar som refererar till filer i den mappen.

- När du kopierar en DITA-mappningsfil ändras inte UUID-referenserna i mappningsfilen.

- Om en fil eller mapp har en konflikt eller har en dubblett, skapas ett unikt filnamn för den nya filen som kopieras eller flyttas.

- Två filer kan inte ha samma UUID. Alla nya filer tilldelas ett unikt UUID.

- Om en fil överförs av två olika användare samtidigt, kommer den fil som bearbetas senare att skriva över den tidigare filen. En sådan metod bör dock undvikas.

- När du checkar ut innehåll från AEM databas och gör ändringar i det lokala systemet, kontrollerar du att filnamnet inte ändras när du överför filen.

- När du infogar en referens i DITA Maps Manager eller Editor visas filens namn och inte UUID:t. Om titeln inte finns visas filnamnet.

### Lägg till eller ta bort favoriter {#id195HC04405P}

Följ de här stegen för att lägga till eller ta bort en mapp i mappen Favoriter på panelen AEM stödlinjer:

- Högerklicka på en mapp och välj **Lägg till i Favoriter**. Du kan lägga till en mapp i favoriter om den inte finns i Favoriter.
- Du kan ta bort en mapp från favoriter på följande sätt:
   - Högerklicka på en mapp i **Favoriter** mapp och markera **Ta bort från Favoriter**.
   - Högerklicka på en mapp i AEM under **DAM** mapp som redan lagts till som favorit och väljer **Ta bort från Favoriter**.

### Visa versionshistorik för en fil {#id195GI000D5Q}

Följ de här stegen för att visa en fils versionshistorik:

1. Högerklicka på en fil på panelen AEM stödlinjer.

1. Välj **Visa versioner** på snabbmenyn.

   Filens versionshistorik visas i dialogrutan Versioner.

   ![Versionshantering](images/version-history.png){width="550" align="left"}


### Visa metadata för en fil {#id195GHN0H05C}

Så här visar du metadata för en fil:

1. Högerklicka på en fil på panelen AEM stödlinjer.

1. Välj **Visa metadata** på snabbmenyn.

   Filens metadata som DITA-klass, dokumenttillstånd, ändringsdatum, storlek, titel och UUID visas i dialogrutan Metadata.

   ![Visa metadata](images/metadata.png){width="550" align="left"}


## Söka i ett ämne i AEM {#id1826J20405Z}

Du kan söka efter ämnen i den AEM databasen med hjälp av sökfältet på AEM stödlinjepanelen. Du kan söka i hela DAM-mappen eller markera en mapp och sedan söka efter ett ämne i den mappen. Sökresultatet visar de ämnen som har textmatchning med sökfrågan.

Utför följande steg för att söka efter ämnen:

1. Välj en mapp i den AEM databasen där du vill söka efter ett ämne.
1. Ange sökfrågan \(till exempel `introduction`\) i sökfältet i Syrgas-plugin-programmet för AEM stödlinjer.
1. Klicka på sökknappen eller tryck på Retur.

   Resultatet visas på fliken Sökresultat som en lista med filsökvägen. Om det inte finns något matchande resultat för sökfrågan, hittades inga resultat i &lt;path of=&quot;&quot; the=&quot;&quot; selected=&quot;&quot; folder=&quot;&quot;> meddelandet visas.

   ![Sökresultat](images/search.png){width="550" align="left"}

1. \(Valfritt\) Dubbelklicka på en fil i sökresultatet för att öppna den i Sygen XML Author.
1. Gör något av följande om du vill gå tillbaka till AEM.
   - Om du vill visa AEM utan att rensa sökresultaten klickar du på **Bläddra** -fliken.
   - Om du vill ta bort sökresultaten och visa AEM databas klickar du på ikonen Ta bort sökning.

## Öppna DITA-avsnittet i Sygen XML Author från AEM webbgränssnitt {#id182CE0I905Z}

Du kan öppna och redigera ditt DITA-ämne i Sygen XML Author från AEM webbgränssnitt. Du måste installera ett paket i AEM för att kunna aktivera det här alternativet. Mer information om paketinstallation finns i [Installera paketet för att aktivera dokumentredigeringsfunktionen från AEM webbgränssnitt](#id182CE0Q0TY4).

>[!NOTE]
>
>The **Redigera i syrgas** är tillgängligt från olika platser i AEM: när ett ämne markeras, när ett ämne förhandsgranskas eller från fliken Ämnen och rapporter i DITA-kartkonsolen. Om du markerar flera ämnen visas inte alternativet i verktygsfältet.

**Öppna ett DITA-avsnitt**

Gör så här för att öppna ett DITA-ämne i Sygen XML Author:

1. Välj ett ämne i dina resurser och klicka på **Redigera i syrgas** i verktygsfältet.

   >[!NOTE]
   >
   >Om ämnet inte är utcheckat checkas det först ut och öppnas sedan i syrgas i redigeringsläge.

1. Välj Syrgas-XML-författare *&lt;version>* i **Starta program** meddelanderuta. Du kan välja **Kom ihåg mitt val för AEM länkar** för att spara dina inställningar.

**Redigera ett DITA-avsnitt**

Utför följande steg för att redigera ett DITA-ämne i Sygen XML Author:

1. Markera och checka ut ett ämne i dina resurser.
1. Klicka **Redigera i syrgas** i verktygsfältet.

   >[!NOTE]
   >
   >Om ämnet inte är utcheckat checkas det först ut och öppnas sedan i syrgas i redigeringsläge.

1. Välj Syrgas-XML-författare *&lt;version>* i **Starta program** meddelanderuta. Du kan välja **Kom ihåg mitt val för AEM länkar** för att spara dina inställningar.
1. Redigera ämnet i Syrgas XML Author.
1. Kolla in ämnet från Syrgas-pluginen för AEM stödlinjer.

   Mer information om hur du checkar in ett ämne med Syrgas-plugin för AEM finns i [Checka in en fil](#id182CF0J0FHS).

   >[!NOTE]
   >
   >Kontrollera att du checkar in ämnet med Syrgas-plugin för AEM Guides. Om du checkar in från AEM webbgränssnitt sparas inte ändringarna du gör i Sygen XML Author i den incheckade versionen av ämnet.

**Infoga en referens till ett ämne från databasen med stödlinjer i Experience Manager**

Du kan också dra och släppa ett ämne för att infoga referensen i ett ämne eller en DITA-karta.
>[!NOTE]
>
> Du måste checka ut en fil innan du lägger till en referens till den.

Följande element läggs till baserat på typen av referenser:

Om du släpper till Redigeraren med ett öppet ämne:
- En referens läggs till med `<image>` bildelementet.
- Ett objektelement läggs till för en video eller ett ljud.
- The `<xref>`  -element läggs till för alla andra referenser, som ämne, karta, DITAVAL, PDF, ZIP och XML.

Om du släpper till Editor eller DITA Maps Manager med en öppen karta:
- The `<mapref>` -element läggs till för kartreferenser, som innehåller en DITA-karta, en bokkarta eller ett ämnesschema.
- The `<topicref>` -element läggs till för alla andra referenser, som ämne, karta, DITAVAL, PDF, ZIP och XML.


## Arbeta med attributprofiler {#id1827JA002YK}

Med AEM Guides kan du enkelt skapa och associera villkorliga attribut med relevanta DITA-attribut. Du kan definiera villkorliga attribut på global nivå eller på mappnivå. De globalt definierade villkoren visas i alla projekt och på mappnivå visas bara i projekt som skapats i den angivna mappen. Innehållsförfattare kan använda dessa villkorsstyrda attribut för att villkoralisera innehåll i sina DITA-avsnitt eller -kartor som de skapar eller använder. Mer information om hur du skapar villkorliga attribut i AEM med hjälp av AEM stödlinjer finns i *Konfigurera villkorliga attribut för globala profiler eller profiler på mappnivå* i Installera och konfigurera Adobe Experience Manager-guider.

>[!NOTE]
>
>Se till att du har lagt till villkorsattributen i AEM och angett [Inställningar för anpassning av profileringsattribut](#id1827K0D0OHT) innan du lägger till villkorliga attribut i innehållet.

Följ de här stegen för att lägga till villkorliga attribut i innehållet i Sygen XML Author:

1. Checka ut och öppna ett ämne i *Syrgas-plugin för AEM*.
1. Markera den del av innehållet där du vill använda villkorsattributen.
1. Dubbelklicka på villkorsattributet på attributpanelen i Författaren för syrgas-XML.

   ![attributpanel](images/attribute-panel.png){width="300" align="left"}

1. I **Tillgänglig** i dialogrutan Redigera attribut markerar du attributen och klickar på **Lägg till**.

   Följande skärm visar `audience` attribut.

   ![Dialogrutan Redigera attribut](images/edit-attributes.png){width="550" align="left"}

1. Klicka **OK**.

   Attributen läggs till i innehållet.


## Felsöka vanliga problem {#id188ABC00RY4}

Det här avsnittet handlar om några av de vanligaste problemen som du kan stöta på när du arbetar med plugin-programmet, tillsammans med deras lösningar.

### Panelen AEM stödlinjer saknas {#id192BH200ZAX}

**Problem** - Om du inte ser panelen AEM i Sygen XML Author kan du prova följande lösningar:

Lösning 1:

1. Aktivera plugin-programmet i Sygen XML Author.

   Klicka **Alternativ** \> **Inställningar** \> **Plugins** och markera **Syrgas-plugin för Adobe Experience Manager Guides.**

1. Starta om Syrgas XML Author.


Lösning 2:

1. Om du fortfarande inte ser panelen AEM stödlinjer aktiverar du fönstret AEM stödlinjer.

   Klicka på i Författare för Syrgas XML **Fönster** \> **Visa vy** \> **AEM stödlinjer**.

Lösning 3:

1. Avinstallera och installera om Syrgas-plugin-programmet för Adobe Experience Manager Guides.

   - Avinstallera plugin-programmet från Windows **Lägg till eller ta bort program** lista. Installera sedan om plugin-programmet.

   - I Mac går du till mappen aem-connector-x.x i mappen plugins i Oxygen XML Author och flyttar den till **Papperskorgen**. Töm sedan **Papperskorgen** mapp.


### Konfigurera port för DITA-OT-omvandling

**Problem** - När du kör en DITA-OT-omformning på filer som bearbetas av plugin-programmet misslyckas omformningen med följande fel:

![DITA-OT-transformeringsfel](images/proxy-server-path-error-new.png){width="800" align="left"}

**Lösning** - Problemet har åtgärdats genom att en proxyserver har lagts till mellan DITA-OT och plugin-programmet. Den här proxyservern bearbetar och delar alla filer som begärts av DITA-OT för omvandlingar. Standardporten som servern har konfigurerats på är: `5972`. Om du använder den här porten för någon annan server kan du ange en annan port för proxyservern.

Utför följande steg för att ändra standardporten för proxyservern:

1. Bläddra till din \(användarens\) arbetskatalog.
1. Skapa en fil med namnet aem\_connector\_proxy.
1. Öppna filen i valfri textredigerare och lägg till ett tillgängligt portnummer på den första raden i filen.
1. Spara och stäng filen.
1. Starta om Syrgas XML Author och kör DITA-OT-omvandlingen.


### Panelen AEM stödlinjer bläddrar inte till den öppnade filplatsen

Problem: När du väljer att öppna en fil för redigering i Sygen XML Author från AEM server öppnas filen för redigering i Sygen XML Author. AEM på stödlinjepanelen visas dock inte filens plats i navigeringsträdet.

Lösning: Det här problemet har observerats i scenarier där filsökvägen innehåller /content/dam två gånger. Som standard lagras alla resurser i AEM under mappen /content/dam. Om du överför eller skapar en mappstruktur som även innehåller /content/dam i mappen, observeras problemet. Du kan utföra alla normala åtgärder för sådana filer, men deras plats i navigeringsträdet visas inte som standard. Om du vill komma åt den filen i navigeringsträdet måste du bläddra till filens plats manuellt. Observera att dubblettsökvägen /content/dam ersätts med /content/assets i navigeringsträdet.

### Konfigurera loggning

Problem: Som standard genereras inga loggar av Sygen-pluginen för AEM Guides, vilket gör det svårt att felsöka ett felscenario.

Lösning: Utför följande steg för att konfigurera loggarna för Syrgas och JxBrowser:

1. Stäng Författaren av syre-XML

1. Skapa en fil med namnet `logback.xml` med följande:

   ```xml
   <configuration>
       <appender name="R2" class="ch.qos.logback.core.rolling.RollingFileAppender">
           <file>${user.home}/Desktop/oxygenLog/oxygen.log</file>
           <rollingPolicy class="ch.qos.logback.core.rolling.FixedWindowRollingPolicy">
               <fileNamePattern>${user.home}/Desktop/oxygenLog/oxygen%i.log.gz</fileNamePattern>
               <minIndex>1</minIndex>
               <maxIndex>20</maxIndex>
           </rollingPolicy>
           <triggeringPolicy class="ch.qos.logback.core.rolling.SizeBasedTriggeringPolicy">
               <maxFileSize>100MB</maxFileSize>
           </triggeringPolicy>
           <encoder>
               <pattern>%r %marker %p [ %t ] %c - %m%n</pattern>
           </encoder>
       </appender> 
   
       <root level="debug">
           <appender-ref ref="R2" />
       </root>
   </configuration>   
   ```

1. Spara filen i `Oxygen Author 25` katalog. (Sökvägen skulle till exempel vara: `C:\Program Files\Oxygen XML Author 25\logback.xml`)

1. Stäng filen. Detta aktiverar syresloggar som kommer att finnas på sökvägen: `${user.home}/Desktop/oxygenLog/oxygen.log`
1. Öppna `oxygenAuthor.bat` i en textredigerare.
1. Konfigurera JxBrowser-relaterade loggar genom att lägga till parametern
   `-Denable.aem.jx.log=true`. Detta aktiverar JxBrowser-relaterade loggar som du kan visa på sökvägen: `${user.home}\AppData\Local\Temp\Oxygen_Plugin_Javax_Log.log`:




   ```java
   SET OXYGEN_JAVA=java.exe
   if exist "%JAVA_HOME%\bin\java.exe" set OXYGEN_JAVA="%JAVA_HOME%\bin\java.exe"
   if exist "%~dp0\jre\bin\java.exe" SET OXYGEN_JAVA="%~dp0\jre\bin\java.exe"
   rem Set environment variables
   call "%~dp0\env.bat"
   %OXYGEN_JAVA% -XX:-OmitStackTraceInFastThrow -XX:SoftRefLRUPolicyMSPerMB=10 -Djdk.module.illegalAccess=permit -Djava.ipc.external=true 
   -Denable.aem.jx.log=true -Dsun.java2d.noddraw=true -Dsun.awt.nopixfmt=true -Dsun.java2d.dpiaware=true -Dsun.io.useCanonCaches=true -Dsun.io.useCanonPrefixCache=true 
   -Dsun.awt.keepWorkingSetOnMinimize=true -Dcom.oxygenxml.app.descriptor=ro.sync.exml.AuthorFrameDescriptor
    -Dcom.oxygenxml.ApplicationDataFolder="%APPDATA%" -cp %CP% ro.sync.exml.Oxygen %*
   ```


Med föregående steg aktiveras loggarna och du kan använda dem för att felsöka problemen.
