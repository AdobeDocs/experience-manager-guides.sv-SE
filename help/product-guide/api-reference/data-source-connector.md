---
title: REST API för att registrera en datakällkoppling
description: Läs mer om REST API för att registrera en datakällkoppling
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 1%

---

# REST API för att registrera en datakällkoppling {#id236LG0Y0CXA}

Med följande REST API kan du registrera en datakällkoppling.

## Registrera en datakällkoppling

En GET-metod som registrerar en datakällkoppling.

**Begär URL**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parametrar**:

| Namn | Typ | Obligatoriskt | Beskrivning |
|----|----|--------|-----------|
| `path` | Sträng | Ja | En sträng som pekar på en sökväg i AEM. Det kan vara en sökväg i `/content/dam or /var/dxml`. |

**Exempel**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
