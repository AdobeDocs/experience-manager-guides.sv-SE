---
title: Anpassa befintliga AEM Site-mallar för AEM Guides
description: Lär dig hur du anpassar befintliga AEM Site-mallar för AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 1cec8975e8aad56184793a023d066aa467d8cec5
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Anpassa befintliga AEM Site-mallar för AEM Guides

Den här guiden innehåller stegvisa instruktioner för att anpassa befintliga AEM Site-mallar för användning med AEM Guides för att generera AEM Sites från DITA-kartor och ämnen.

Om du använder den färdiga AEM Guides-mallen (AEMG Docs) finns konfigurationerna och komponenterna redan på plats och kan användas i befintligt skick för att publicera ditt AEM Guides-innehåll. Om du vill använda dina befintliga AEM Sites-mallar med anpassad profilering för att publicera AEM Guides-innehåll följer du stegen nedan för att anpassa webbplatsmallarna efter AEM Guides renderingskrav.


## Förutsättningar

- Du har rätt behörigheter och åtkomst till AEM-mallar.
- Du förstår AEM redigerbara mallar och AEM Site-struktur.
- Du har en befintlig platshierarki som skapats med redigerbara mallar.
- Du har minst två mallar från ditt befintliga projekt:

   - **Dokumentationsbehållarsidmall** används för att återge DITA-kartan som dokumentationsrot.
   - **Ämnessidmall** används för att återge enskilda DITA-ämnessidor.

## Om mallnamngivning

Mallnamnen varierar beroende på projektinställningarna. I OTB AEMG Docs-konfigurationen:

- Dokumentationsbehållarsida: /conf/AEMG-Docs-Site/settings/wcm/templates/kb-content

- Ämnessida: /conf/AEMG-Docs-Site/settings/wcm/templates/topic-content

**Anpassning:** Anpassningsprocessen omfattar två viktiga steg:

1. Mallinställning: Identifiera och konfigurera de två mallarna (behållare och ämne).
2. Komponenter för återgivningsstödlinjer: Bädda in nödvändiga AEM Guides-komponenter för att aktivera funktioner som innehållsförteckning, navigering och visning av metadata.

## Mallinställningar

Välj och konfigurera två redigerbara mallar på din AEM-webbplats.

### Dokumentationsbehållarsidmall

Mallen Dokumentationsbehållarsida används för att skapa produktdokumentationsbehållarsidan som återger innehållet i en DITA-karta.

- Det fungerar som startpunkt eller hemsida för en specifik dokumentationsuppsättning (till exempel en produkthandbok eller guide).
- Lägg till egenskapen id=&quot;category-page&quot; i jcr:content för mallens inledande nod. Detta garanterar att alla sidor som skapas från den här mallen automatiskt hanteras som dokumentationsbehållare av AEM Guides.

  ![Lägger till id=&quot;category-page&quot;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-id-category-page.png){width="650" align="left"}

- Lägg till en textkomponent med den obligatoriska egenskapen: text=&quot;$category.html$&quot;.

  ![Lägger till textkomponent](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component.png){width="650" align="left"}

- Innehåller vanligtvis navigeringselement, t.ex. länkar till avsnitt eller ämnen i dokumentationen.
- Den kan anpassas så att den omfattar varumärken, sidhuvuden, sidfötter och andra designelement.

**Exempel på användningsfall:**
Om du har en DITA-karta för en produkthandbok, kommer dokumentationsbehållarsidmallen att generera startsidan för den handboken med en översikt och länkar till enskilda ämnen.

### Ämnessidmall

- **Ämnessidmallen** används för att skapa sidor för enskilda **DITA-avsnitt**.
- Varje avsnitt i en DITA-karta återges som en separat sida med den här mallen.
- Innehåller en **textkomponent** med den obligatoriska egenskapen: text=&quot;$topic.content$&quot;.

  ![Lägger till textkomponent med obligatorisk egenskap](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component-mandatory-property.png){width="650" align="left"}

- Den här platshållaren ersätts med det faktiska innehållet i DITA-avsnittet under webbplatsgenereringen.
   - Textkomponenten placeras vanligtvis inuti en **behållarkomponent** för att säkerställa rätt layout och format.
   - Kan anpassas så att de innehåller konsekventa sidhuvuden, sidfötter och navigeringselement för alla ämnessidor.

**Exempel på användningsfall:**
Om du har ett DITA-avsnitt om &quot;Installationsanvisningar&quot;, kommer ämnessidmallen att generera en sida som visar innehållet i det ämnet.

**Behållarkomponent:**

![Lägger till behållarkomponent](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-component.png){width="650" align="left"}

>[!NOTE]
>
> Kontrollera att komponenter som använder sling:resourceType under wcm/Foundation/components migreras till motsvarande core/wcm/components.

Lägg till samma (behållare- och textkomponent) i strukturen för samma mall:

![Lägger till behållare och textkomponent](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-and-text-component.png){width="650" align="left"}

## Återge stödlinjekomponenter i anpassade mallar

Om du vill aktivera viktiga AEM Guides-komponentfunktioner som innehållsförteckning, sidomdirigering, navigering och visning av metadata måste du ta med specifika AEM Guides-komponenter i dina anpassade mallar. Dessa komponenter måste läggas till explicit i motsvarande redigerbara mallar (dokumentationsbehållarsidan eller ämnessidan) för att säkerställa att de avsedda funktionerna är tillgängliga vid generering och körning av webbplatsen.

Se tabellen nedan för en lista över komponenter och deras användning:

| Funktion | Komponentnamn | Beskrivning | Rekommenderad mall |
|---|---|---|---|
| Innehållsförteckning | navigering i guider | Återger fullständig innehållsförteckning från DITA-kartan | Dokumentationsbehållare |
| Sidomdirigering | childDirect | Omdirigerar till den första ämnessidan i kartan | Dokumentationsbehållare |
| Mini TOC | minitoc | Visar innehållsförteckning för det aktuella ämnet | Ämnessida |
| Senast uppdaterad | pageproperty | Visar det senast ändrade datumet | Ämnessida |
| Skrivbordsväljare | personsökare | Tillåter navigering mellan föregående och nästa ämnessidor | Ämnessida |
| Språknavigering | språknavigering | Möjliggör växling mellan olika språkversioner | Antingen mall |


## Komponentanvändningsfall

- **Omdirigeringskomponent (childDirect):** Lägg till detta i dokumentationsbehållarsidmallen så att produktstartsidan som genereras från DITA-kartan automatiskt omdirigeras till den första avsnittssidan. Om dokumentationsbehållarsidan är utformad för att fungera som en fristående hemsida med anpassade komponenter och layouter behövs inte den här komponenten.

- **Innehållsförteckning (guidad beskrivning):** Lägg till detta i ämnessidmallen för att återge en navigeringsbar innehållsförteckning bredvid avsnittsinnehållet. Innehållsförteckningen hämtas från DITA-kartan och hjälper användarna att navigera mellan ämnen på samma nivå.


## Aktivera klientbibliotek för stödlinjer

Som standard används inte klientbiblioteken (klientbibliotek) som finns i AEM Guides-komponentpaketet för anpassade mallar. Så här aktiverar du dem:

1. **Redigera mallen:**

   1. Öppna **produktsidan** i **redigeringsläget**.
   2. Välj **Redigera mall** (en URL som conf/settings/wcm/templates/structure.html öppnas).

      ![Redigera mall](/help/product-guide/knowledge-base/kb-articles/assets/publishing/edit-template.png){width="650" align="left"}

2. **Uppdatera sidprincip:**

   1. Gå till knappen **Sidinformation** och välj **Sidprofil**.
   2. Lägg till följande klientbibliotek:
      - **Klientbibliotek**
      - **Klientbibliotek JavaScript Page Head**

3. **Spara ändringar:** Spara mallen efter att du har lagt till de nödvändiga klientbiblioteken.

   ![Lägg till klientbibliotek](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-client-libraries.png){width="650" align="left"}


>[!NOTE]
>
> Kontrollera att mallarna har testats i en icke-produktionsmiljö innan du distribuerar till produktionen.<br><br>Mer information finns i den officiella dokumentationen för [AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview) och [AEM Sites](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/get-started/authoring).
