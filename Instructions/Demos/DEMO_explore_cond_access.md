---
Demo:
    title: 'Accesso condizionale ad Azure Active Directory'
    module: 'Modulo 2. Lezione 3. Descrizione delle funzionalità delle soluzioni Microsoft per la gestione delle identità e degli accessi: esplorazione delle funzionalità di gestione degli accessi di Azure AD'
---


# Demo: Accesso condizionale ad Azure Active Directory

### Scenario demo
Questa demo illustra le varie opzioni disponibili per un criterio di accesso condizionale.

1. Passare alla scheda **Contoso – Microsoft Azure** aperta nel browser. Se la scheda era stata chiusa, aprire una pagina del browser e, nella barra degli indirizzi, inserire portal.azure.com e selezionare Azure Active Directory. Occorre aver effettuato l'accesso come amministratore nel portale di Azure. In caso contrario, eseguire di nuovo l'accesso.

1. Dal riquadro di spostamento sinistro, selezionare **Sicurezza**.

1. Dal riquadro di spostamento sinistro, selezionare **Accesso condizionale**.

1. Compare la schermata Criteri di accesso condizionale. Qualsiasi criterio di accesso condizionale esistente è elencato qui. Per mostrare le impostazioni associate all'accesso condizionale, selezionare **+ Nuovo criterio**.

1. Nel campo **Nome**, basta inserire un nome per il criterio.

1. Sotto **Assegnazioni** sono disponibili diverse opzioni.  Poiché i criteri di accesso condizionale sono come le istruzioni if/then, le impostazioni di assegnazione sono come le istruzioni "if".
    1. **Utenti e gruppi** - passare il mouse sull'icona delle informazioni accanto a "Utenti e gruppi"; qui che è possibile impostare gli utenti e i gruppi nella directory a cui si applica il criterio. Selezionare **0 utenti e gruppi selezionati**.  Ora sarà visibile l'opzione per includere o escludere utenti o gruppi. Selezionare le impostazioni disponibili per la scheda **Includi** e selezionare le impostazioni disponibili per la scheda **Escludi**.
    1. **App o azioni del cloud** - passare il mouse sull'icona delle informazioni accanto ad "App o azioni del cloud"; qui è dove è possibile impostare le applicazioni usate o le azioni eseguite dall'utente per i criteri di accesso condizionale.  Selezionare **Nessuna app o azione del cloud selezionata**.
        1. Selezionare la freccia a discesa nella casella sotto a **Selezionare a cosa si applica questo criterio** e notare le opzioni.  Lasciare l'impostazione predefinita "App cloud".
        1. Selezionare e richiamare le impostazioni disponibili per la scheda Includi. Sotto la scheda **Includi**, scegliere **Seleziona app**.  Si apre una finestra dove è possibile scegliere tra un elenco di applicazioni.  Non selezionare nulla, chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra. Tornare indietro per scegliere **Nessuna** per rimuovere l'errore.
        1. Selezionare le impostazioni disponibili per la **scheda Escludi**.  Di nuovo, qui è possibile selezionare le app specifiche da escludere.
    1. **Condizioni** - passare il mouse sull'icona delle informazioni accanto a "Condizioni"; queste stabiliscono quando si applica il criterio. Selezionare **0 condizioni selezionate**. Considerare i diversi "segnali" elencati.   Selezionare alcune delle opzioni selezionando prima l'icona delle informazioni per definire cos'è e poi selezionando **Non configurato** per la voce specifica per mostrare le varie opzioni.
        1. **Rischio utente** - Un rischio utente rappresenta la probabilità che una data identità o account siano compromessi. Questi rischi sono calcolati offline usando le fonti di intelligence sulle minacce interne ed esterne di Microsoft.
        1. **Rischio di accesso** - Un rischio di accesso rappresenta la probabilità che una data richiesta di autenticazione non sia autorizzata dal proprietario dell'identità. Gli esempi possono includere se l'accesso è da un indirizzo IP anonimo o uno spostamento fisico atipico, ecc.
        1. **Piattaforma del dispositivo** - Piattaforma da cui l'utente sta effettuando l'accesso. Ad esempio, "iOS".
        1. **Posizione** - Posizione (determinata utilizzando l'intervallo di indirizzi IP) da cui l'utente sta accedendo
        1. **App cliente** - Software usato dell'utente per accedere all'app cloud. Ad esempio, "Browser".

1. **Controlli di accesso**: tornando all'analogia che i criteri di accesso condizionale sono come le istruzioni if/then, i controlli di accesso sono analoghi all'istruzione "then".
    1. **Concessione** - passare il mouse sull'icona delle informazioni accanto a "Concessione" per la descrizione.  Selezionare **0 controlli selezionati** per mostrare le diverse opzioni.  Considerarne alcuni.  In particolare richiamare l'opzione **Richiedi autenticazione a più fattori**, sotto Concedi accesso e come questa può essere usata per fornire un controllo estremamente granulare su quando richiedere la MFA.   Ricordare inoltre che è possibile impostare più controlli e richiedere tutti o solo uno dei controlli selezionati.
    1. **Sessione** - passare il mouse sull'icona delle informazioni accanto a "Sessione" per la descrizione.  Ricordare che i Controlli sessione permettono un'esperienza limitata all'interno di un'applicazione cloud.  Ad esempio, l'utente può essere in grado di accedere all'app cloud ma non potrà eseguire il download di eventuali contenuti né stampare.  Questo è un argomento più complesso, quindi deve essere spiegato in modo semplice.

1. Una volta configurato un criterio, è possibile attivare un criterio selezionando **Attiva**, quindi premere il pulsante **Crea** per creare un criterio.

1. Selezionare la **X** nell'angolo in alto a destra della pagina per chiudere il criterio, quindi selezionare Microsoft Azure sulla barra blu nella parte superiore della pagina per tornare alla home page del portale di Azure.

1. Tenere aperta questa pagina del browser per la prossima demo.

### Verifica

Questa demo ha illustrato le varie opzioni disponibili per un criterio di accesso condizionale.
