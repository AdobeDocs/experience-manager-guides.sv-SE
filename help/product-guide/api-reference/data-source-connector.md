---
title: REST API för att registrera en datakällkoppling
description: Läs mer om REST API för att registrera en datakällkoppling
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 0%

---

# REST API för att registrera en datakällkoppling {#id236LG0Y0CXA}

Med följande REST API kan du registrera en datakällkoppling.

## Registrera en datakällkoppling

En GET-metod som registrerar en datakällkoppling.

**Begär URL**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameter**: |Namn|Typ|Obligatorisk|Beskrivning| |—|—|—|—| |`path`|String|Yes|En sträng som pekar på en sökväg i AEM. Det kan vara en bana i `/content/dam or /var/dxml`.|

**Exempel**:\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
