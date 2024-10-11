---
title: Konfigurera den smarta hjälpen för att söka efter innehåll
description: Lär dig hur du konfigurerar Smart Hjälp för att söka efter innehåll
source-git-commit: 48f7b38448e821a7ad5931a685dedc95303aea95
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---


# Konfigurera den AI-baserade smarta hjälpen för att söka efter innehåll

Som administratör kan du konfigurera funktionen Smart hjälp för författarna. Tjänsten Smart Help skyddas av automatisk autentisering med Adobe IMS. Integrera miljön med Adobe säkra tokenbaserade autentiseringsarbetsflöden och börja använda den nya smarta hjälpfunktionen. Följande konfigurationer hjälper dig att lägga till fliken **AI-konfiguration** i en mappprofil. När du har lagt till den kan du använda funktionen Smart hjälp i Web Editor.

## Skapa IMS-konfigurationer i Adobe Developer Console

Så här skapar du IMS-konfigurationer i Adobe Developer Console:

>[!NOTE]
>
>Om du redan har skapat ett OAuth-projekt för att konfigurera funktionen Smarta förslag eller den mikrotjänstbaserade publiceringen kan du hoppa över följande steg för att skapa projektet. Du kan börja med steg 8.

1. Starta [Adobe Developer Console](https://developer.adobe.com/console).
1. När du har loggat in på Developer Console visas skärmen **Hem**. På skärmen **Hem** kan du enkelt hitta information och snabblänkar, inklusive länkar till projekt och hämtningsbara filer.
1. Om du vill skapa ett nytt tomt projekt väljer du **Skapa nytt projekt** från länkarna **Snabbstart** .
   ![Snabbstartslänkar](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Skapa ett nytt projekt.*

1. Välj **Lägg till API** på skärmen **Projekt**.  Skärmen **Lägg till ett API** visas. På den här skärmen visas alla tillgängliga API:er, händelser och tjänster för Adobe-produkter och -tekniker som du kan använda för att utveckla program.

1. Välj **I/O-hanterings-API:t** för att lägga till det i ditt projekt.
   ![API för IO-hantering](assets/confi-ss-io-management.png)
   *Lägg till API för I/O-hantering i ditt projekt.*

1. Skapa en ny **OAuth-autentiseringsuppgift** och spara den.
   ![Rutan för OAuth-autentiseringsuppgifter i konfigurations-API](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Konfigurera OAuth-autentiseringsuppgifter för ditt API.*

1. På fliken **Projekt** väljer du alternativet **OAuth-server till server** och sedan de nya autentiseringsuppgifterna.

1. Klicka på länken **OAuth Server-to-Server** om du vill visa information om projektets autentiseringsuppgifter.

   ![anslutna autentiseringsuppgifter](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Anslut till projektet om du vill visa autentiseringsuppgifter.*

1. Gå tillbaka till fliken **Projekt** och välj **Projektöversikt** till vänster.

   <img src="assets/project-overview.png" alt="projektöversikt" width="500">

   *Kom igång med det nya projektet.*

1. Klicka på knappen **Hämta** överst för att hämta JSON-tjänsten.

   <img src="assets/download-json.png" alt="ladda ned json" width="500">

   *Hämta JSON-tjänstinformationen.*

Du har konfigurerat OAuth-autentiseringsinformationen och laddat ned JSON-tjänstinformationen. Ha den här filen till hands så som det behövs i nästa avsnitt.

### Lägg till IMS-konfiguration i miljön

Utför följande steg för att lägga till IMS-konfiguration i miljön:

1. Öppna Experience Manager och välj sedan det program som innehåller den miljö som du vill konfigurera.
1. Växla till fliken **Miljö**.
1. Välj det miljönamn som du vill konfigurera. Du bör navigera till sidan **Miljöinformation**.
1. Växla till fliken **Konfiguration**.
1. Uppdatera JSON-fältet SERVICE_ACCOUNT_DETAILS. Se till att du använder samma namn och konfiguration som i skärmbilden nedan.

![konfiguration av ims-tjänstkonto](assets/ims-service-account-config.png){width="800" align="left"}


*Lägg till information om miljökonfiguration.*




När du har lagt till IMS-konfigurationen i miljön utför du följande steg för att länka dessa egenskaper till AEM Guides med OSGi:

1. Lägg till följande två filer (för filinnehåll, se [Bilaga](#appendix)) i Git-projektkoden för din molnhanterare.

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Se till att de nyligen tillagda filerna täcks av din `filter.xml`.
1. Verkställ och skicka Git-ändringarna.
1. Kör pipeline för att tillämpa ändringarna på miljön.

När du är klar bör du kunna använda funktionen **Smart hjälp**.



## Bilaga {#appendix}

**Fil**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Innehåll**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


När du har konfigurerat visas ikonen **Smart hjälp** ![Smart hjälp](assets/smart-help-icon.svg) i den högra panelen i Web Editor. Markera ikonen om du vill visa panelen **Smart hjälp** .
Mer information finns i avsnittet [AI-baserad smart hjälp för att söka efter innehåll](../user-guide/ai-based-smart-help.md) i användarhandboken för Experience Manager.
