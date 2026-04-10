---
title: Användaradministration och -säkerhet
description: Se hur användaradministration och säkerhet fungerar
exl-id: 10ab0f3c-97dc-4293-ab73-75b438c03d99
feature: User Management
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 0%

---

# Användaradministration och -säkerhet {#id181AED00G5Z}

Om du vill komma åt och konfigurera funktioner i AEM Guides måste du skapa användare. Dessa användare kan sedan tilldelas behörighet att komma åt alla eller vissa funktioner i AEM Guides. Lär dig konfigurera och underhålla användarauktorisering och förstå också teorin bakom hur autentisering och auktorisering fungerar i AEM.

Följande avsnitt i AEM-dokumentationen hjälper dig att förstå användaradministration och säkerhetsrelaterade koncept och funktioner:

- [AEM användare, grupper och behörigheter](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html?lang=sv-SE)

- [Användaradministration och -säkerhet](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=sv-SE)


## Användargrupper skapade av AEM Guides {#id181TF0K0MHT}

AEM Guides har tre färdiga grupper. Dessa grupper är: *Författare*, *Granskare* och *Utgivare*. Beroende på vilken grupp en användare är kopplad till, kan de utföra specifika åtgärder. Publiceringsuppgifterna kan till exempel bara utföras av en utgivare, men inte av en författare eller granskare. På samma sätt kan en författare skapa ett nytt ämne, och en granskare kan bara granska ett ämne.

>[!TIP]
>
> Avsnittet *Behörigheter* i guiden Bästa metoder innehåller tips om hur du anger användarbehörigheter.

I följande tabell visas olika uppgifter och grupper som kan utföra dessa uppgifter:

| Uppgift | Författare | Granskare | Utgivare |
|----|-------|---------|----------|
| Skapa DITA-ämne | Ja |   | Ja |
| Skapa DITA-karta | Ja |   | Ja |
| Kartsamlingar | Ja |   | Ja |
| Skapa granskningsaktivitet | Ja |   | Ja |
| Granska ämne[1](#fntarg_1) | Ja | Ja | Ja |
| Nyckelupplösning | Ja |   | Ja |
| Checka ut/Checka in | Ja |   | Ja |
| Redigera ämne | Ja |   | Ja |
| Flytta ämne | Ja |   | Ja |
| Redigera ämnesegenskaper | Ja |   | Ja |
| Kopiera | Ja |   | Ja |
| Ta bort | Ja |   | Ja |
| Dela | Ja |   | Ja |
| **Dokumentläge** |  |  |  |
| Skapa/redigera dokumenttillståndsprofil |   |   | Ja |
| Ändra dokumentläge[2](#fntarg_2) | Ja | Ja | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Utdatainställningar\)** |  |  |  |
| Generera |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Skapa |   |   | Ja |
| Ta bort förinställning |   |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Utdata\)** |  |  |  |
| Visa genererade utdata | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Ämnen\)** |  |  |  |
| Skapa granskningsaktivitet | Ja |   | Ja |
| Redigera | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(fliken Baslinjer\)** |  |  |  |
| Skapa |   |   | Ja |
| Redigera |   |   | Ja |
| Duplicera |   |   | Ja |
| Ta bort |   |   | Ja |
| DITA map console \(Reports tab\) | Ja |   | Ja |
| **Tillgängliga funktioner i DITA-kartkonsolen \(Villkorsförinställningar\)** |  |  |  |
| Skapa/redigera villkorsförinställning |   |   | Ja |

## Ytterligare information om användargrupper

Följande lista innehåller rekommendationer och punkter som rör användargrupper och motsvarande behörigheter:

- Om du vill att en användare ska starta översättnings- eller granskningsarbetsflödet kontrollerar du att användaren är medlem i gruppen *Utgivare* och *projekt-administratörer*.

- Användarna måste ha behörighet att läsa, skapa, ta bort och ändra på käll- och målspråksmapparna som de behöver arbeta med.

- Om du skapar ett projekt är du ägare av projektet med *Utgivare*-behörigheter. För att andra användare i ett projekt ska kunna se sina teammedlemmar, skapa uppgifter eller skapa arbetsflöden måste de ha läsåtkomst på `/home/users`- och `/home/groups`-noder. Ett sätt att ge läsåtkomst på `/home/users`- och `/home/groups`-noder är att ge läsåtkomst till gruppen `projects-users`.

- *Granskare* kan komma åt och lägga till granskningskommentarer för ett ämne som granskas via projektkonsolen eller via inkorgens meddelandelänk. Dessutom är den här åtkomsten bara tillgänglig tills granskningsaktiviteten är öppen.

- Som standard får *Utgivare* åtkomst och behörigheter till följande mappar i DAM:

   - `/content/fmdita` -\> Läs och skriv

   - `/content/dam/fmdita-outputs` -\> Läs och skriv

   - `/content/output/sites` -\> Läs och skriv

  Du måste ge explicit läs- och skrivbehörighet till utgivaren om du använder någon annan plats än de standardpubliceringsplatser som nämns ovan.

- Alla användare under grupperna *Författare*, *Granskare* och *Utgivare* har läsåtkomst för allt innehåll i DAM.

- Behörigheter på mappnivå måste tilldelas användare via sidan för användaradministration.

- Om du vill att dina användare ska kunna utföra sökåtgärder på DAM ska du göra användarna till medlemmar i gruppen *dam-users*.

- Om du vill ge administratörsbehörighet till en användare kan du göra det genom att ge dem åtkomst via AEM standardgrupper som *administratörer*, *projects-administrators* eller OSGI-konfigurationen \(Felix console\).

- Om du vill ge en användare behörighet att ändra ett dokumenttillstånd måste du lägga till användaren i avsnittet om tillståndsövergång i dokumentets tillståndsprofil.

[1](#fnsrc_1) Om *Författare* och *Utgivare* bjuds in till en granskning.[2](#fnsrc_2) Beroende på vilka rättigheter användaren har i dokumentets tillståndsprofil.
