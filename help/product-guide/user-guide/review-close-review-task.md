---
title: Begär en ny granskning eller stäng en granskningsåtgärd som författare
description: Lär dig mer om arbetsflödet för att stänga en granskningsuppgift eller begära en ny granskning som författare i Experience Manager Guides.
feature: Reviewing
role: User
source-git-commit: b7648fe1d36de3c243ca5a55f42a41f7523056ce
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Begär en ny granskning eller stäng en granskningsåtgärd som författare

>[!IMPORTANT]
>
> De nya funktionerna som beskrivs i den här artikeln är aktiverade som standard med 2508 års utgåva av Experience Manager Guides som molntjänster. Granskningar som skapades före migreringen påverkas inte och fortsätter att använda det tidigare arbetsflödet. Om du föredrar att fortsätta använda de befintliga funktionerna utan dessa uppdateringar kontaktar du ditt Customer Success-team för att inaktivera de nya funktionerna.

När en granskningsuppgift markeras som slutförd av en granskare, utlöses ett meddelande till den som initierar aktiviteten, så att de kan komma åt och granska uppgiften och relaterade kommentarer på aktivitetsnivå.

Som initierare för granskningsaktiviteten kan du sedan bestämma hur du ska gå vidare baserat på feedback. De tillgängliga alternativen är:

- Begär en ny granskning
- Stäng granskningsaktiviteten

## Begär en omgranskning eller stäng en granskningsåtgärd

Utför följande steg för att begära en omgranskning eller stänga en granskningsåtgärd:

1. Öppna granskningsåtgärden i Redigeraren.
2. På granskningspanelen väljer du granskningsaktiviteten i listan **Aktiva aktiviteter**.

   >[!NOTE]
   >
   > Du kan även öppna uppgiften i kontrollpanelen för uppgifter för att få en mer heltäckande bild. Det gör du genom att välja **Öppna i kontrollpanelen för uppgifter** på Alternativ-menyn för en aktiv granskningsåtgärd. Aktivitetsinformationen öppnas i projektkonsolen.

   ![](images/task-dashboard-selection-author-view.png)
3. Välj dialogrutan **Aktivitetskommentarer** för att komma åt och granska de kommentarer på aktivitetsnivå som har lagts till av granskaren.

   ![](images/task-comments-selection-author-view.png).

   Dialogrutan **Uppgiftskommentarer** visas till höger.

   ![](images/task-comments-dialog-editor.png){width="350" align="left"}.
4. Välj **Uppdatera aktivitet** om du vill vidta ytterligare åtgärder för den valda granskningsaktiviteten.
5. Välj en av följande åtgärder i dialogrutan **Uppdatera uppgift**:

   - **Begär en ny granskning**: Initierar en ny granskningsrunda. Du kan välja en annan version av ämnet för granskning. Som standard är den senaste (eller den senast redigerade) versionen av det ämne eller den kartfil som skickats för granskning markerad. Granskare som slutfört den föregående granskningen får ett meddelande om att ge feedback om den uppdaterade versionen. Andra granskare som inte har markerat granskningen som slutförd får meddelanden om ämnesuppdateringen.

   - **Stäng granskning**: Stänger granskningsaktiviteten. Knappen **Uppdatera aktivitet** längst ned på granskningspanelen ändras till **Stängd** och ett meddelande skickas till alla användare som deltar i granskningen som indikerar att den har stängts.

   Mer information om hur granskningsmeddelanden utlöses finns i [Om granskningsmeddelanden](./review-understanding-review-notifications.md).

   ![](images/update-task-dialog.png).

6. Välj **Bekräfta**.


När du stänger en uppgift som författare eller initierare för en granskningsaktivitet ändras knappen **Uppdatera aktivitet** längst ned på granskningspanelen till **Stängd**, vilket anger att aktiviteten inte längre är aktiv.

![](images/review-task-status-closed-review-panel.png){width="350" align="left"}

Knappen **Uppdatera aktivitet** på granskningspanelen är dessutom inaktiverad för andra användare av granskningsuppgiften. Om du till exempel är en av granskarna av en granskningsaktivitet och öppnar uppgiften i Redigeraren inaktiveras aktivitetsknappen Uppdatera med meddelandet **Du har inte behörighet att utföra den här aktiviteten**. Det är bara den som initierar en granskningsåtgärd som har behörighet att uppdatera uppgiften från Redigeraren.

![](images/update-task-button-disabled.png){width="350" align="left"}