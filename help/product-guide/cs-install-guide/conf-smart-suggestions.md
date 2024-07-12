---
title: Konfigurera smarta förslag för redigering
description: Lär dig konfigurera smarta förslag för redigering
exl-id: a595ca1f-0123-40d3-a79c-a066bc6517b4
source-git-commit: d3e0c475ebd50a2664ea45c293d34b3a10772633
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Konfigurera AI-baserade smarta förslag för redigering

Som administratör kan du konfigurera funktionen Smarta förslag för författarna. Tjänsten för smarta förslag skyddas av automatisk autentisering med Adobe IMS. Integrera din miljö med Adobe säkra tokenbaserade autentiseringsarbetsflöden och börja använda den nya smarta förslagsfunktionen. Följande konfiguration hjälper dig att lägga till fliken **AI-konfiguration** i mappprofilen. När du har lagt till den kan du använda funktionen för smarta förslag i Web Editor.

## Skapa IMS-konfigurationer i Adobe Developer Console

Så här skapar du IMS-konfigurationer i Adobe Developer Console:

>[!NOTE]
>
>Om du redan har skapat ett OAuth-projekt för att konfigurera den mikrotjänstbaserade publiceringen kan du hoppa över följande steg för att skapa projektet.

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

   ![Autentiseringsuppgiftsruta för OAuth i konfigurations-API](assets/conf-ss-OAuth-credential.png)

   *Konfigurera OAuth-autentiseringsuppgifter för ditt API.*

1. Välj alternativet **OAuth Server till server** på fliken **Projekt** och välj sedan de nya autentiseringsuppgifterna.

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

1. Öppna Experience Manager och välj sedan det program som innehåller den miljö du vill konfigurera.
1. Växla till fliken **Miljö**.
1. Välj det miljönamn som du vill konfigurera. Du bör navigera till sidan **Miljöinformation**.
1. Växla till fliken **Konfiguration**.
1. Uppdatera JSON-fältet SERVICE_ACCOUNT_DETAILS. Se till att du använder samma namn och konfiguration som i skärmbilden nedan.

![konfiguration av ims-tjänstkonto](assets/ims-service-account-config.png){width="800" align="left"}


*Lägg till information om miljökonfiguration.*




När du har lagt till IMS-konfigurationen i miljön utför du följande steg för att länka dessa egenskaper till AEM Guides med OSGi:

1. I Git-projektkoden för din molnhanterare lägger du till följande två filer (för filinnehåll, se [Bilaga](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Se till att de nyligen tillagda filerna täcks av din `filter.xml`.
1. Verkställ och skicka Git-ändringarna.
1. Kör pipeline för att tillämpa ändringarna på miljön.

När du är klar bör du kunna använda funktionen för smarta förslag.



## Bilaga {#appendix}

**Fil**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Innehåll**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Fil**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Innehåll**:

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Konfigurationsinformation för smarta förslag

| Nyckel | Beskrivning | Tillåtna värden | Standardvärde |
|---|---|---|---|
| smart.suggestion.flag | Anger om smarta förslag är aktiverade eller inte | true/false | false |
| conref.inline.threshold | Tröskelvärde som styr precision/återkallande av förslag som hämtats för taggen som användaren skriver in just nu. | Alla värden mellan -1.0 och 1.0. | 0,6 |
| conref.block.threshold | Tröskelvärde som styr precision/återkallande av förslag som hämtats för taggar i hela filen. | Alla värden mellan -1.0 och 1.0. | 0,7 |
| emerald.url | Slutpunkt för Emerald-vektordatabas | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Typ av AEM. Se till att detta är unikt för varje AEM som de smarta förslagen har konfigurerats på. Ett användningsexempel skulle vara att testa funktionen i scenmiljön med &quot;instance.type&quot; = &quot;stage&quot;, medan funktionen samtidigt är konfigurerad för &quot;prod&quot;. | En unik nyckel som identifierar miljön. Endast *alfanumeriska* värden tillåts. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

När du har konfigurerat visas ikonen för smarta förslag på den högra panelen i Web Editor. Du kan visa listan med smarta förslag när du redigerar ämnen. Mer information finns i avsnittet [AI-baserade smarta förslag för redigering](../user-guide/authoring-ai-based-smart-suggestions.md) i användarhandboken för Experience Manager.
