---
title: Konfigurera Guides-assistenten för att söka efter innehåll
description: Lär dig konfigurera Guides Assistant för att söka efter innehåll
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---


# Konfigurera den AI-baserade Guides Assistant för att söka efter innehåll

Som administratör kan du konfigurera Guides Assistant-funktionen för författarna. Guides Assistant-tjänsten skyddas av automatisk autentisering med Adobe IMS. Integrera din miljö med Adobe säkra tokenbaserade autentiseringsarbetsflöden och börja använda den nya funktionen Guides Assistant. Följande konfigurationer hjälper dig att lägga till **AI-konfiguration** till en mappprofil. När du har lagt till den kan du använda Guides Assistant i Web Editor.

## Skapa IMS-konfigurationer i Adobe Developer Console

Så här skapar du IMS-konfigurationer i Adobe Developer Console:

>[!NOTE]
>
>Om du redan har skapat ett OAuth-projekt för att konfigurera funktionen Smarta förslag eller den mikrotjänstbaserade publiceringen kan du hoppa över följande steg för att skapa projektet.

1. Starta [Adobe Developer Console](https://developer.adobe.com/console).
1. När du har loggat in på Developer Console visas **Startsida** skärm. The **Startsida** är där du enkelt kan hitta information och snabblänkar, inklusive länkar till projekt och nedladdningar.
1. Om du vill skapa ett nytt tomt projekt väljer du **Skapa nytt projekt** från **Snabbstart** länkar.
   ![Snabblänkar](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Skapa ett nytt projekt.*

1. Välj **Lägg till API** från **Projekt** skärm.  The **Lägg till ett API** visas. På den här skärmen visas alla tillgängliga API:er, händelser och tjänster för Adobe-produkter och -tekniker som du kan använda för att utveckla program.

1. Välj **API för I/O-hantering** för att lägga till den i ditt projekt.
   ![API för IO-hantering](assets/confi-ss-io-management.png)
   *Lägg till API för I/O-hantering i ditt projekt.*

1. Skapa ett nytt **OAuth-autentiseringsuppgifter** och spara det.
   ![Autentiseringsuppgiftsruta för OAuth i konfigurations-API](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Konfigurera OAuth-autentiseringsuppgifter för ditt API.*

1. I  **Projekt** väljer du **OAuth-server till server** och välj sedan de nya inloggningsuppgifterna.

1. Välj **OAuth Server-till-server** om du vill visa projektinformation.

   ![anslutna autentiseringsuppgifter](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Anslut till projektet för att visa informationen om autentiseringsuppgifter.*

1. Återgå till **Projekt** och markera **Projektöversikt** till vänster.

   <img src="assets/project-overview.png" alt="projektöversikt" width="500">

   *Kom igång med det nya projektet.*

1. Klicka på **Ladda ned** överst för att hämta JSON-tjänsten.

   <img src="assets/download-json.png" alt="ladda ned json" width="500">

   *Ladda ned information om JSON-tjänsten.*

Du har konfigurerat OAuth-autentiseringsinformationen och laddat ned JSON-tjänstinformationen. Ha den här filen till hands så som det behövs i nästa avsnitt.

### Lägg till IMS-konfiguration i miljön

Utför följande steg för att lägga till IMS-konfiguration i miljön:

1. Öppna Experience Manager och välj sedan det program som innehåller den miljö som du vill konfigurera.
1. Växla till **Miljö** -fliken.
1. Välj det miljönamn som du vill konfigurera. Du bör navigera till **Miljöinformation** sida.
1. Växla till **Konfiguration** -fliken.
1. Uppdatera JSON-fältet SERVICE_ACCOUNT_DETAILS. Se till att du använder samma namn och konfiguration som i skärmbilden nedan.

![konfiguration av ims-tjänstkonto](assets/ims-service-account-config.png){width="800" align="left"}


*Lägg till information om miljökonfigurationen.*




När du har lagt till IMS-konfigurationen i miljön utför du följande steg för att länka dessa egenskaper med AEM stödlinjer med OSGi:

1. Lägg till följande två filer (för filinnehåll, se [Bilaga](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Se till att de nya filerna täcks av dina `filter.xml`.
1. Verkställ och skicka Git-ändringarna.
1. Kör pipeline för att tillämpa ändringarna på miljön.

När detta är klart ska du kunna använda **Guides Assistant** -funktion.



## Bilaga {#appendix}

**Fil**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Innehåll**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


När du har konfigurerat **Guides Assistant** ![Guides Assistant](assets/guides-assistant-icon.svg) visas i den högra panelen i Web Editor. Välj ikonen om du vill visa **Guides Assistant** -panelen.
Mer information finns i [AI-baserad Guides Assistant för sökning av innehåll](../user-guide/ai-based-guides-assistant.md) i användarhandboken för Experience Manager.
