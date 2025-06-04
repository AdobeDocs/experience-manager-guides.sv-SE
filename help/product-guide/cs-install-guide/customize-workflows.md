---
title: Konfigurera och anpassa arbetsflöden
description: Lär dig konfigurera och anpassa arbetsflöden
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 026d75e69ef002607ac375cf1af7d055fcc22b38
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 0%

---

# Konfigurera och anpassa arbetsflöden {#id181AI0OJ0RO}

Med arbetsflöden kan du automatisera Adobe Experience Manager \(AEM\)-aktiviteter. Ett arbetsflöde består av en serie steg som körs i en viss ordning. Du kan definiera en distinkt aktivitet som ska köras i varje steg. Du kan till exempel skicka ett e-postmeddelande till alla granskare i en grupp när en ämnesgranskning skapas. Eller skicka ett meddelande till utgivaren när en utdatagenereringsåtgärd har slutförts.

Mer information om arbetsflöden i AEM finns i:

- [Administrerar arbetsflödesinstanser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html)

- Tillämpar och deltar i arbetsflöden: [Arbeta med projektarbetsflöden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html).


Avsnitten i det här avsnittet visar olika anpassningar som du kan göra i de standardarbetsflöden som levereras i AEM Guides.

## Anpassa granskningsarbetsflödet {#id176NE0C00HS}

Alla organisationers skribenter arbetar på ett specifikt sätt för att uppfylla sina verksamhetskrav. I vissa organisationer finns det en dedikerad redigerare, medan andra organisationer kan ha ett automatiserat system för redaktionell granskning. I en organisation kan t.ex. ett vanligt arbetsflöde för redigering och publicering omfatta uppgifter som - när en författare har redigerat innehållet går det automatiskt till granskarna och när granskningen är klar går det till utgivaren för att generera det slutliga resultatet. I AEM kan aktiviteter som du gör med ditt innehåll och dina resurser kombineras i form av en process och mappas till ett AEM-arbetsflöde. Mer information om arbetsflöden i AEM finns i [Administrera arbetsflöden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html) i AEM-dokumentationen.

Med AEM Guides kan du anpassa standardarbetsflödet för granskning. Du kan använda följande fyra anpassade granskningsrelaterade processer tillsammans med dina andra arbetsflöden för redigering och publicering.

- **Skapa granskning**: Den här processen förbereder de metadata som krävs för att skapa en granskningsaktivitet. Den tilldelar till exempel granskarna granskningsbehörighet, ställer in status för de ämnen som ska granskas, ställer in tidslinjer för granskningen med mera. Av de fyra processerna är detta den enda obligatoriska processen som måste ingå i ditt anpassade arbetsflöde. I ditt arbetsflöde kan du välja att inkludera eller exkludera de andra tre processerna.

- **Tilldela granskningsaktivitet**: Den här processen skapar granskningsaktiviteten och skickar aktivitetsmeddelandet till initieraren och granskarna.

- **Skicka e-post för granskning**: Den här processen skickar e-postmeddelandet till initieraren och granskarna.

- **Schemalägg jobb för att stänga granskning**: Den här processen ser till att granskningsprocessen slutförs när tidsgränsen nås.


När du skapar ett anpassat granskningsarbetsflöde är den första uppgiften att ange de metadata som behövs för att skapa granskningsprocessen. Om du vill göra det kan du skapa ett ECMA-skript. Ett exempel på ECMA-skript som tilldelar metadata ges nedan för både ämne och karta.

**För ämne**

```javascript
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
```

**För karta**

```javascript
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
```

Du kan skapa dessa skript i noden `/etc/workflows/scripts`. I följande tabell beskrivs de egenskaper som tilldelas av båda de ovannämnda ECMA-skripten.

| Egenskap | Typ | Beskrivning |
|--------|----|-----------|
| `initiator` | Sträng | Användar-ID för den användare som initierar granskningsaktiviteten. |
| `operation` | Sträng | Ett statiskt värde angett som `AEM_REVIEW`. |
| `orgTopics` | Sträng | Sökväg till de ämnen som delas för granskning. Ange flera ämnen avgränsade med kommatecken. |
| `payloadJson` | JSON-objekt | Ange följande värden: -   `base`: sökväg till den överordnade mappen som innehåller det ämne som skickats för granskning. <br> -   `asset`: sökväg till ämnet som skickats för granskning. <br> -   `referrer`: lämna det tomt. |
| `deadline` | Sträng | Ange tiden i formatet `yyyy-MM-dd'T'HH:mm:ss.SSSXXX`. |
| `title` | Sträng | Ange en rubrik för granskningsaktiviteten. |
| `description` | Sträng | Ange en beskrivning för granskningsaktiviteten. |
| `assignee` | Sträng | Användar-ID för de användare till vilka du vill skicka ämnet för granskning. |
| `status` | Heltal | Ett statiskt värde angett som 1. |
| `startTime` | Lång | Använd funktionen `System.currentTimeMillis()` för att hämta den aktuella systemtiden. |
| `projectPath` | Sträng | Sökväg till det granskningsprojekt som granskningsaktiviteten ska tilldelas till, t.ex.: /content/projects/samples_review project. |
| `reviewType` | Sträng | Statiskt värde&quot;AEM&quot;. |
| `versionJson` | JSON-objekt | versionJson är en lista med ämnen som ska behandlas i granskningen där varje ämnesobjekt har följande struktur: {path}: &quot;/content/dam/1-topic.dita&quot;, &quot;version&quot;: &quot;1.1&quot;, &quot;review&quot;: true, &quot;reviewers&quot;: [&quot;projects-we_retail-editor&quot;] &rbrace; |
| `isDitamap` | Boolean | false/true |
| `ditamapHierarchy` | JSON-objekt | Om kartan skickas för granskning bör värdet här vara:[ { &quot;path&quot;: &quot;GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap&quot;, &quot;items&quot;: [ { &quot;path&quot;: &quot;GUID-99 747e8ab-8cf1-45dd-9e20-d47d482f667d.dita&quot;, &quot;title&quot;: &quot;&quot;, &quot;items&quot;: [] } ] } ]. |
| `ditamap` | Sträng | Ange sökvägen för ändringslistan för granskningsaktiviteten |
| `allowAllReviewers` | Boolean | false/true |
| `notifyViaEmail` | Boolean | false/true |


När du har skapat skriptet anropar du det innan du anropar processen Skapa granskning i arbetsflödet. Beroende på dina behov kan du sedan anropa de andra granskningsarbetsflödena.

### Ta bort granskningsarbetsflöde från rensningskonfigurationen

Om du vill förbättra arbetsflödesmotorns prestanda kan du regelbundet rensa färdiga arbetsflödesinstanser från AEM-databasen. Om du använder AEM standardkonfigurationer rensas alla färdiga arbetsflödesinstanser efter en viss tidsperiod. Detta resulterar även i att alla granskningsarbetsflöden rensas från AEM-databasen.

Du kan förhindra att granskningsarbetsflöden rensas automatiskt genom att ta bort granskningsarbetsflödesmodellen \(information\) från den automatiska rensningskonfigurationen. Du måste använda **Adobe Granite Workflow Renge Configuration** för att ta bort arbetsflödesmodellerna för granskning från listan för automatisk rensning.

Kontrollera att du har angett minst ett arbetsflöde som du kan rensa i **Adobe Granite Workflow Renge Configuration**. Du kan till exempel använda något av följande arbetsflöden som skapats av AEM Guides:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Genom att lägga till ett arbetsflöde i **Adobe Granite Workflow Renge Configuration** kan du vara säker på att AEM bara tömmer de arbetsflöden som finns i konfigurationen. Detta förhindrar att AEM rensar granskningsarbetsflödesinformationen.

Mer information om hur du konfigurerar **Adobe Granite Workflow Renge Configuration** finns i *Administrera arbetsflödesinstanser* i AEM-dokumentationen.

### Anpassa e-postmallar

I ett antal av AEM Guides arbetsflöden används e-postmeddelanden. Om du till exempel initierar en granskningsåtgärd skickas ett e-postmeddelande till granskarna. Om du vill vara säker på att e-postmeddelandet skickas måste du aktivera den här funktionen i AEM. Mer information om hur du aktiverar e-postmeddelanden i AEM finns i artikeln [Skicka e-post](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) i AEM-dokumentationen.

AEM Guides innehåller en uppsättning e-postmallar som du kan anpassa. Följ de här stegen för att anpassa de här mallarna:

1. Hämta filen `/libs/fmdita/mail` med pakethanteraren.

   >[!NOTE]
   >
   > Gör inga anpassningar i standardkonfigurationsfilerna tillgängliga i noden ``libs``. Du måste skapa en övertäckning av noden ``libs`` i noden ``apps`` och endast uppdatera de filer som krävs i noden ``apps``.

1. E-postmappen innehåller följande anpassningsbara mallar:

   | Mallfilnamn | Beskrivning |
   |-----------------|-----------|
   | closereview.html | Den här e-postmallen används när en granskningsuppgift stängs. |
   | createreview.html | Den här e-postmallen används när en ny granskningsuppgift skapas. |
   | reviewapproval.css | Den här CSS-filen innehåller formateringen för e-postmallar. |


## Anpassa arbetsflödet för efterhandsproduktion {#id17A6GI004Y4}

AEM Guides ger dig flexibilitet att ange ett arbetsflöde för postutdata. Du kan utföra vissa efterbehandlingsåtgärder på utdata som genereras med AEM Guides. Du kan till exempel använda vissa CQ-taggar på utdata från AEM Site, ange vissa egenskaper för PDF-utdata eller skicka ett e-postmeddelande till en uppsättning användare när utdata har genererats.

Du kan skapa en ny arbetsflödesmodell som du kan använda som arbetsflöde för att skapa utdata. När ett arbetsflöde för generering efter utdata aktiveras, delar arbetsflödet kontextuell information via arbetsflödets metadatamappning, som du kan använda för att utföra bearbetning av genererade utdata. I följande tabell beskrivs den sammanhangsberoende information som delas som metadata:

| Egenskap | Typ | Beskrivning |
|--------|----|-----------|
| ``outputName`` | Sträng | Namnet på den förinställning som används för att generera utdata. |
| `generatedPath` | Sträng | Sökväg i DAM där genererade utdata lagras. |
| `outputType` | com.adobe.fmdita.output.OutputType | Typ av förinställning för utdata. |
| `outputTitle` | Sträng | Namnet på förinställningen för utdata. |
| `outputHistoryPath` | Sträng | Databassökväg för noden history. |
| `isSuccess` | Boolean | En flagga som visar slutstatusen för utdatagenereringsprocessen - om den lyckades eller inte. |
| `logPath` | Sträng | Sökväg i DAM där loggarna för utdatagenerering sparas. |
| `generatedTime` | Lång | Tid då utdatagenereringsprocessen utlöstes. |
| `initiator` | Sträng | Användar-ID för användaren som utlöste arbetsflödet för generering av utdata. |

Om du vill använda metadata för generering av utdata kan du skapa ett ECMA-skript eller ett OSGi-paket. Ett exempel på ECMA-skript som använder metadata ges nedan:

>[!NOTE]
>
> Du kan skapa skriptet i noden ``/etc/workflows/scripts``.

```javascript
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

När du har skapat skriptet anropar du det anpassade skriptet i arbetsflödet. Beroende på dina behov kan du sedan anropa de andra arbetsflödesprocesserna. När du har utformat ditt anpassade arbetsflöde anropar du *Slutför eftergenerering* som det sista steget i arbetsflödesprocessen. Steget *Slutför eftergenerering* säkerställer att statusen för utdatagenereringsaktiviteten uppdateras till *Slutförd* när utdatagenereringsprocessen har slutförts. När du har skapat ett anpassat arbetsflöde för postutdata kan du konfigurera det med alla förinställningar för utdatagenerering. Välj önskat arbetsflöde i egenskapen *Kör arbetsflöde efter generering* för den önskade förinställningen. När du kör en utdatagenereringsuppgift med den konfigurerade förinställningen ändras aktivitetsstatusen \(på fliken Utdata\) till *Efterbearbetning*.
