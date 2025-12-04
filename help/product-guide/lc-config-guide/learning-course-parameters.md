---
title: SCORM nyckeltal för elevens framsteg och kursslutförande
description: Läs om nyckelmätvärden för SCORM för elevens framsteg och kursslutförande
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 0dff380131dadc971f257eb464700392328164e5
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# SCORM nyckeltal för elevens framsteg och kursslutförande

I artikeln listas de nyckelparametrar som hämtats i ett SCORM-paket, tillsammans med motsvarande fält och exempel. Dessa parametrar ger viktiga insikter om elevernas framsteg, slutförande av kurser, interaktionsdetaljer och frågeprestanda. Administratörer kan använda den här informationen för att validera spårning, konfigurera rapportering och säkerställa korrekta analyser i LMS-miljön. Nedan visas exempelvärden för varje parameter så som den visas i SCORM-paketet.

| **Parameternamn** | **Beskrivning** | **Fält** | **Exempel** |
|---|---|---|---|
| **Slutförandestatus för kurs** | Anger om kursen är slutförd eller inte | cmi.completion_status | ofullständig |
| **Antal försök** | Antal försök som gjorts av den studerande | Räknare/innehåll för försök på LMS-sidan | Försök: 1 |
| **Plats för SCORM-paket** | Aktuellt bokmärke eller kursplats | cmi.location | - |
| **Slutförande av förlopp** | Elevernas framsteg | cmi.progress_measure | 0,87 |
| **Total tid (försök)** | Total tid som har använts i det aktuella försöket | cmi.total_time | 0000:01:09.87 |
| **Synlighet för innehållsförteckning och ämnesantal** | Visar information om innehållsförteckningens synlighet och ämnesslutförande | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
| **Status per ämne** | Slutförings- och godkännandestatus för varje ämne | Anpassat läge per lektion | - |
| **Per frågeväljläge** | Spårar elevens val per fråga | värde, genererat_id, markerat | - |
| **Samlat poängvärde för frågor** | Resultat som uppnåtts på frågenivå och aggregat | {&quot;score&quot;:0,&quot;maxScore&quot;:1} och % | &quot;score&quot;:33.33,&quot;maxScore&quot;:100,&quot;minScore&quot;:0 |
| **Interaktioner på varje frågenivå** | Information om hur eleverna interagerar per fråga | id/type/timestamp/correct_response/learner_response/result/latency | - |
| **Allmän kursstatus** | Anger godkänt/misslyckat och totalt förlopp | success_status, complete_status, score, progress_measure | Om det gick eller misslyckades |
| **Information om elever** | Identifierar eleven efter ID och namn | cmi.learner_id, cmi.learner_name | Albert |
| **Frågeparametrar** | Konfigurationer för frågetidning och bakgrundsmusik | cmi.max_time_allowed, cmi.scaled_Pass_score, cmi.time_limit_action | Odefinierade eller konfigurerade värden |