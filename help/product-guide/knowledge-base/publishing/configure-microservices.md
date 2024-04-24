---
title: Konfigurera ny mikrotjänstbaserad publicering för AEM Guides as a Cloud Service
description: Lär dig hur du konfigurerar ny mikrotjänstbaserad publicering för AEM.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
feature: Microservice in AEM Guides
role: User, Admin
source-git-commit: f929d4fd74e98e2025d80c14dbef6aeb464c0dd5
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 0%

---

# Konfigurera mikrotjänstbaserad publicering med JWT-autentisering

[!BADGE Cloud Service]{type=Informative}

>[!NOTE]
>
> JWT-autentiseringsuppgifterna (Service Account) har ersatts med autentiseringsuppgifterna för OAuth Server-till-Server. Dina program som använder JWT-inloggningsuppgifterna (Service Account) slutar fungera efter 1 januari 2025. Du måste migrera till de nya autentiseringsuppgifterna senast 1 januari 2025 för att programmet ska fortsätta fungera. Läs mer om [migrera från JWT-autentiseringsuppgifter (Service Account) till OAuth Server-till-Server-autentiseringsuppgifter](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/).



Microservice-baserad publicering i för Adobe Experience Manager Guides as a Cloud Service har stöd för PDF (både Native- och DITA-OT-baserade), HTML5, JSON och CUSTOM för olika utdatapresentationer.

Eftersom JWT-autentiseringsuppgifterna (Service Account) har tagits bort rekommenderar vi att du använder OAuth-baserad autentisering med Adobe IMS. Lär dig hur [konfigurera mikrotjänstbaserad publicering med OAuth-autentisering](configure-microservices-imt-config.md).

För molnpubliceringstjänsten som skyddas av Adobe IMS JWT-baserad autentisering ska kunderna följa stegen nedan för att integrera sina miljöer med Adobe säkra tokenbaserade autentiseringsarbetsflöden och börja använda den nya molnbaserade skalbara publiceringslösningen.


## Skapa IMS-konfigurationer i Adobe Developer Console

**Roll som krävs för att skapa konfigurationer**: Systemadministratör

Så här skapar du IMS-konfigurationer i Adobe Developer Console:

1. Öppna Developer Console: `https://developer.adobe.com/console`.

1. Växla till **Projekt** från början.

   <img src="assets/projects-tab.png" alt="fliken Projekt" width="500">

1. Om du vill skapa ett nytt tomt projekt väljer du **Tomt projekt** från **Skapa nytt projekt** nedrullningsbar meny.

   <img src="assets/create-new-project.png" alt="skapa nytt projekt" width="500">

1. Välj **API** från **Lägg till i projekt** listruta för att lägga till API för IO-hantering i ditt projekt.

   <img src="assets/add-project.png" alt="lägg till projekt" width="300">

   <img src="assets/io-management-api.png" alt="iohantering" width="500">

1. Skapa ett nytt nyckelpar för privat/offentlig nyckel när du lägger till API:t. Då hämtas den privata nyckeln automatiskt till ditt system.

   <img src="assets/generate-key-pair.png" alt="generera nyckelpar" width="500">

1. Spara det konfigurerade API:t.

   <img src="assets/save-api.png" alt="spara api" width="600">

1. Gå tillbaka till **Projekt** och klicka **Projektöversikt** till vänster.

   <img src="assets/project-overview.png" alt="projektöversikt" width="500">

1. Klicka **Ladda ned** överst för att hämta JSON-tjänsten.

   <img src="assets/download-json.png" alt="ladda ned json" width="500">

Du har nu konfigurerat informationen om JWT-autentisering och har även hämtat den privata nyckeln och tjänstinformationen JSON. Ha dessa två filer till hands eftersom de behövs i nästa avsnitt.

### Lägg till IMS-konfiguration i miljön

Utför följande steg för att lägga till IMS-konfiguration i miljön:

1. Öppna Experience Manager och välj sedan det program som innehåller den miljö som du vill konfigurera.
1. Växla till **Miljö** -fliken.
1. Klicka på det miljönamn som du vill konfigurera. Du bör navigera till sidan Miljöinformation.
1. Växla till **Konfiguration** -fliken.
1. Ladda upp den privata nyckeln och projekt-JSON så som visas på skärmbilden nedan. Se till att du använder samma namn och konfiguration som markeras nedan.

   <img src="assets/ims-config-environment.png" alt="IMS-konfigurationer" width="500">

>[!NOTE]
>
> Du måste öppna, kopiera och klistra in innehållet i JSON-filen för den privata nyckeln och tjänstinformation i värdekolumnen på konfigurationspanelen enligt skärmbilden ovan.

När du har lagt till IMS-konfigurationen i miljön följer du de här stegen för att länka dessa egenskaper till Experience Manager-guider med OSGi:

1. Lägg till följande två filer (för filinnehåll, se [Bilaga](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Se till att de nya filerna täcks av dina `filter.xml`.
1. Verkställ och skicka Git-ändringarna.
1. Kör pipeline för att tillämpa ändringarna på miljön.

När detta är klart bör du kunna använda den nya mikrotjänstbaserade molnpubliceringen.

## Vanliga frågor

1. Kan en enskild nyckel användas i flera molnmiljöer?
   * Ja, du kan generera en privat nyckel och använda den för alla miljöer, men du måste konfigurera miljövariabler för alla miljöer och använda samma nyckel.
1. Om OSGi-konfigurationer som ska använda mikrotjänsten är aktiverade, kommer publiceringsprocessen att fungera på den lokala AEM servern med samma kodbas?
   * Nej, om flaggan `dxml.use.publish.microservice` är inställd på `true` söker programmet alltid efter mikrotjänstkonfigurationer. Ange `dxml.use.publish.microservice` till `false` för att publicera lokalt.
1. Hur mycket minne tilldelas DITA-processen vid användning av mikrotjänstbaserad publicering? Drivs detta via parametrar för DITA-profilant?
   * Med mikrotjänstbaserad publicering styrs minnesallokeringen inte av DITA-profilens ant-parametrar. Det totala tillgängliga minnet för tjänstbehållaren är 8 GB, varav 6 GB tilldelas till DITA-OT-processen.


## Bilaga {#appendix}

**Fil**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Innehåll**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
}
```

**Fil**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Innehåll**:
* `dxml.use.publish.microservice`: Växla för att aktivera mikrotjänstbaserad publicering med DITA-OT
* `dxml.use.publish.microservice.native.pdf`: Växla för att aktivera mikrotjänstbaserad publicering i PDF

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
