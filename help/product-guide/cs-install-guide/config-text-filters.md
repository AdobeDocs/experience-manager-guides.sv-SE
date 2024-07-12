---
title: Konfigurera textfilter
description: Lär dig hur du konfigurerar textfilter
exl-id: 0963606c-010e-4a72-b7bf-850b86b34a84
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Konfigurera textfilter {#id21BPD0FK0XA}

I AEM Guides finns en funktion för att söka efter text i de filer som finns på den valda sökvägen i AEM. Du kan använda filtersökningar för att söka efter filer från databaspanelen eller för att bläddra bland filer. När du arbetar i Web Editor måste du använda dialogrutan för filbläddring för att infoga element som bild, referens eller nyckelreferens.

Som standard kan du använda vissa förbättrade filter för att söka efter filer i AEM. Du kan filtrera alla DITA-filer eller icke-DITA-filer som finns på den valda sökvägen. Du kan också söka efter specifika värden i attributen för DITA-element. Du kan också söka efter filer som har checkats ut av den angivna användaren.

>[!NOTE]
>
> Du kan också konfigurera den globala profilen och lägga till fler filter för sökning.

Så här konfigurerar du textfiltren:

1. Logga in i Adobe Experience Manager som administratör.
1. Klicka på länken Adobe Experience Manager överst och välj **Verktyg**.
1. Välj **Stödlinjer** i listan över verktyg och klicka på **Mappprofiler**.
1. Klicka på rutan **Global profil**.
1. Klicka på **XML-redigerarkonfiguration**.
1. Klicka på ikonen **Redigera** överst.
1. Klicka på ikonen **Hämta** för att hämta filen ui\_config.json på din lokala dator. Du kan sedan göra ändringar i filen och sedan överföra samma fil.
   1. Konfigurera filtren i filen. Du kan också lägga till egna filter enligt exemplet nedan:

      Följande kodutdrag visar hur du lägger till filtreringsalternativ, DITA-filer, icke-DITA, DITA-element och utcheckade av filer. Den innehåller även ett anpassat filter -Tags.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      I ovanstående kodfragment är det första filtret för DITA-filer. Filterdefinitionen har följande parametrar:

      ****Titel****: Filtrets visningsnamn. Titeln visas som filtreringsalternativ i dialogrutan för filbläddring.

      ****Egenskap****: Den egenskap som ska matchas i filens metadata. Om du till exempel bara vill tillåta de filer som har metadata för dita\_class i sin egenskap, använder egenskapsfiltret värdet&quot;jcr:content/metadata/dita\_class&quot;.

      ****Åtgärd **:**Ange &quot;finns&quot; för att matcha om värdet som anges i egenskapsparametern finns

1. Överför den uppdaterade filen ui\_config.json som innehåller de tillagda filtren.

De konfigurerade filtren är tillgängliga på filterpanelen.

**Överordnat ämne:**[ Anpassa Web Editor](conf-web-editor.md)
