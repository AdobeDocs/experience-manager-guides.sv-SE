---
title: Installation och konfiguration
description: Installera och använda AEM Guides Extension Package
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
source-git-commit: b4d6c1c8c2d413bb4137e58391554abf2fb68b8c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Installera och använda AEM Guides Extension Package

Med tillägg får du möjlighet att anpassa din AEM Guides-app så att den bättre passar dina behov. Det här tilläggsramverket stöds med AEM Guides v4.3 och senare (lokal) och 2310 (moln).

## Krav

Det här paketet kräver [git bash](https://github.com/git-guides/install-git) och npm

## Installation

Det enklaste sättet att starta installationen av AEM Guides-ramverket är via cli

```bash
npx @adobe/create-guides-extension
```

## Lägga till anpassningsbar kod

1. Lägg till kodfiler för varje komponent som du vill utöka i katalogen `src/`. Vissa exempelfiler har redan lagts till.
2. Finns nu i filen `index.ts` i katalogen `src/` :
   - Importera `.ts`-filerna med de anpassningar som du vill lägga till i din version.
   - Lägg till importerna till `window.extension`
   - Registrera den anpassade komponentens `id` och motsvarande import till `tcx extensions`
   - Se exemplet `/src/index.ts`

## Bygga den anpassade koden

- Kör `npm run build` i rotkatalogen. Du får 3 filer i katalogen, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Skapa utdata](./../imgs/build_output.png)

## Lägga till anpassningar i AEM

- Gå till `CRXDE` `crx/de/index.jsp#/`
- Skapa en ny nod av typen `cq:ClientLibraryFolder` i mappen `apps`

![Mappstruktur](./../imgs/crxde_folder_structure.png)

- I nodens `properties` väljer du `Multi` för att lägga till följande egenskap
Namn: `categories`
Typ: `String []`
Värde: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

>[!NOTE]
>
> För det näst sista användargränssnittet är värdena: `apps.fmdita.penultimate.xml_editor.page_overrides` och `apps.fmdita.review_overrides`


![Mappegenskaper](./../imgs/crxde_folder_properties.png)

- Om du vill lägga till de skapade js-filerna skapar du en ny fil, till exempel `tcx1.js`, i noden ovan skapade. Här lägger du till koden från `dist/guides-extension.umd.cjs` eller `dist/guides-extension.js`. Skapa nu en ny fil `js.txt`, här lägger vi till namnet på vår js-fil, som i det här fallet skulle vara:

```t
#base=.
tcx1.js
```

- Om du vill lägga till den skapade css-filen skapar du en ny fil, till exempel `tcx1.css`, i noden ovan skapade. Här lägger du till koden från `dist/build.css`. Skapa nu en ny fil `css.txt`, här lägger vi till namnet på vår CSS-fil, som i det här fallet skulle vara:

```t
#base=.
tcx1.css
```

- Gör en `shift + refresh` för att läsa in appen med anpassningarna!

## Felsökning

Kontrollera att alla ovanstående steg har utförts korrekt.
När du har lagt till koden i tcx.js måste du göra en hård uppdatering (Skift+Uppdatera).
Öppna AEM, högerklicka och klicka sedan på `Inspect`
Gå till Källor och sök efter din `[node_name].js` -fil (till exempel extensions.js). Sök efter filen med Ctrl/Cmd+D. Om filen `.js` finns med den JS-kod som du klistrade in från `dist/guides-extension.umd.cjs` eller `dist/guides-extension.js` är installationen klar
