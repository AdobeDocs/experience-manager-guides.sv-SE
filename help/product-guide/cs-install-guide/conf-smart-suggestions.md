---
title: Konfigurera smarta förslag för redigering
description: Lär dig konfigurera smarta förslag för redigering
source-git-commit: f0bb8e29748ab6820d772225d1689bd5ce6f4c09
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 0%

---

# Konfigurera smarta förslag för redigering

Som administratör kan du konfigurera funktionen Smarta förslag för författarna. Eftersom den smarta förslagstjänsten skyddas av autofunktionsautentisering med Adobe IMS integrerar dina miljöer med Adobe säkra tokenbaserade autentiseringsarbetsflöden och börjar använda den nya lösningen för smarta förslag. Följande konfiguration hjälper dig att lägga till fliken för AI-konfiguration i mappprofilen. När du har lagt till den kan du använda funktionen för smarta förslag i Web Editor.

## Skapa IMS-konfigurationer i Adobe Developer Console

Så här skapar du IMS-konfigurationer i Adobe Developer Console:
1. Starta [Adobe Developer Console](https://developer.adobe.com/console).
1. När du har loggat in på Developer Console visas **Startsida** skärm. The **Startsida** är där du enkelt kan hitta information och snabblänkar, inklusive länkar till projekt och nedladdningar.
1. Om du vill skapa ett nytt tomt projekt väljer du  **Skapa nytt projekt** från  **Snabbstart** länkar.
   ![Snabblänkar](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Skapa ett nytt projekt.*

1. Välj  **Lägg till API**  från  **Projekt** skärm.  The **Lägg till ett API** visas. På den här skärmen visas alla tillgängliga API:er, händelser och tjänster för Adobe-produkter och -tekniker som du kan använda för att utveckla program.

1. Välj **API för IO-hantering** för att lägga till den i ditt projekt.
   ![API för IO-hantering](assets/confi-ss-io-management.png)
   *Lägg till API för IO-hantering i ditt projekt.*

1. Skapa ett nytt **OAuth-autentiseringsuppgifter** och spara det.
   ![Autentiseringsuppgiftsruta för OAuth i konfigurations-API](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Konfigurera OAuth-autentiseringsuppgifter för ditt API.*

1. I  **Projekt** väljer du de nya inloggningsuppgifterna.

1. Välj **OAuth Server-till-server** om du vill visa projektinformation.

![anslutna autentiseringsuppgifter](assets/conf-ss-connected-credentials.png) {width="800" align="left"}
*Anslut till projektet för att visa informationen om autentiseringsuppgifter.*
1. Kopiera knapparna CLIENT_ID och CLIENT_SECRET.

Du har nu konfigurerat informationen för OAuth-autentisering. Ha de här två tangenterna till hands eftersom de behövs i nästa avsnitt.

### Lägg till IMS-konfiguration i miljön

Utför följande steg för att lägga till IMS-konfiguration i miljön:

1. Öppna Experience Manager och välj sedan det program som innehåller den miljö du vill konfigurera.
1. Växla till **Miljö** -fliken.
1. Välj det miljönamn som du vill konfigurera. Du bör navigera till sidan Miljöinformation.
1. Växla till **Konfiguration** -fliken.
1. Lägg till knapparna CLIENT_ID och CLIENT_SECRET så som visas på följande skärmbild. Se till att du använder samma namn och konfiguration som markeras nedan.
   ![Miljökonfiguration](assets/conf-ss-environment.png) {width="800" align="left"}
   *Lägg till information om miljökonfigurationen.*




När du har lagt till IMS-konfigurationen i miljön utför du följande steg för att länka dessa egenskaper med AEM stödlinjer med OSGi:

1. I din molnhanterares Git-projektkod lägger du till följande två filer (för filinnehåll, se [Bilaga](#appendix).

   * `com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Se till att de nya filerna täcks av dina `filter.xml`.
1. Verkställ och skicka Git-ändringarna.
1. Kör pipeline för att tillämpa ändringarna på miljön.

När detta är klart bör du kunna använda den nya mikrotjänstbaserade molnpubliceringen.



## Bilaga {#appendix}

**Fil**:
`com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`

**Innehåll**:

```
{
  "client.id": "$[secret:CLIENT_ID]",
  "client.secret": "$[secret:CLIENT_SECRET]",
  "ims.url": "https://ims-na1.adobelogin.com"
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

## Konfigurationsinformation för smart förslagskonfiguration

| Nyckel | Beskrivning | Tillåtna värden |
|---|---|---|
| smart.suggestion.flag | Anger om smarta förslag är aktiverade eller inte | true/false |
| conref.inline.threshold | Tröskelvärde som styr precision/återkallande av förslag som hämtats för taggen som användaren skriver in just nu. | -1.0 &lt;= x &lt;= 1.0 |
| conref.block.threshold | Tröskelvärde som styr precision/återkallande av förslag som hämtats för taggar i hela filen. | -1.0 &lt;= x &lt;= 1.0 |
| emerald.url | Slutpunkt för Emerald-vektordatabas | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Typ av AEM. Se till att detta är unikt för varje AEM som smarta förslag har konfigurerats på. Ett användningsexempel skulle vara att testa funktionen i scenmiljön med &quot;instance.type&quot; = &quot;stage&quot;, medan funktionen samtidigt är konfigurerad för &quot;prod&quot;. | En unik nyckel som identifierar miljön &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; |

När du har konfigurerat visas ikonen för smarta förslag på den högra panelen i Web Editor. Du kan visa listan med smarta förslag när du redigerar ämnen. Mer information finns i [AI-baserade smarta förslag för redigering](../user-guide/web-editor-content-snippet.md).
