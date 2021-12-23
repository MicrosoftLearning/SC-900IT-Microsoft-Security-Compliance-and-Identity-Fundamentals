---
Demo:
    title: 'Reimpostazione della password self-service di Azure Active Directory'
    module: 'Modulo 2. Lezione 2. Descrizione delle funzionalità delle soluzioni Microsoft per la gestione delle identità e degli accessi: descrizione dei vari metodi di autenticazione di Azure AD'
---

# Demo: Reimpostazione della password self-service (SSPR) di Azure Active Directory

### Scenario demo

Questa demo illustra le varie impostazioni associate all'abilitazione della reimpostazione della password self-service.

1. Passare alla scheda Contoso – Microsoft Azure aperta nel browser. Se la scheda era stata chiusa, aprire una pagina del browser e, nella barra degli indirizzi, inserire portal.azure.com e selezionare Azure Active Directory. Occorre aver effettuato l'accesso come amministratore nel portale di Azure. In caso contrario, eseguire di nuovo l'accesso.

1. Dal riquadro di spostamento sinistro, selezionare Reimpostazione della password.

1. Viene evidenziata la scheda delle proprietà.  Nella finestra Proprietà, si noti che la reimpostazione della password self-service può essere abilitata per Nessuno, Selezionati o Tutti.
    1. Posizionare il cursore sull'icona delle informazioni accanto a "Reimpostazione della password self-service abilitata" e ricordare che è possibile scegliere "Selezionati" per limitare la reimpostazione della password della password a un gruppo limitato di utenti, oppure selezionare Nessuno o Tutti.
    1. Posizionare il cursore sull'icona delle informazioni accanto a "seleziona gruppo" e ricordare che è qui che si identifica il gruppo di utenti a cui è permesso resettare le proprie password.   Occorre includere gli utenti nel gruppo, non è possibile selezionare gli utenti individualmente.  Inoltre, se si cambia il gruppo, il gruppo selezionato sostituisce quello attualmente elencato.  Pertanto, si raccomanda di aggiungere semplicemente gli utenti al gruppo di reimpostazione della password self-service.
    1. Si noti il riquadro delle informazioni in azzurro e ricordarlo agli studenti. Queste impostazioni si applicano solo agli utenti finali dell'organizzazione. Gli amministratori possono sempre eseguire la reimpostazione della password self-service e devono usare due metodi di autenticazione per reimpostare la loro password.

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare Metodi di autenticazione.
    1. Posizionare il cursore sull'icona delle informazioni accanto a "Numero di metodi richiesti per la reimpostazione".  Ricordare che in questo modo si imposta il numero di metodi di identificazione alternativi che un utente in questa directory deve avere per reimpostare la propria password.   Non modificare l'impostazione.
    1. Ricordare i diversi "metodi a disposizione degli utenti", compreso il fatto che la reimpostazione della password self-service supporta le domande di sicurezza. Selezionare Domande di sicurezza per mostrare le opzioni per usare le domande di sicurezza. Dopo aver finito di parlare delle opzioni, tornare indietro e selezionare Domande di sicurezza per rimuovere il segno di spunta.

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare Registrazione.
    1. Passare il mouse sull'icona delle informazioni accanto a "Richiedi agli utenti di registrarsi all'accesso".   Ricordarlo agli utenti.  
    1. Passare il mouse sull'icona delle informazioni accanto a: "Numero di giorni prima che all'utente venga chiesto di riconfermare le informazioni di autenticazione".   Ricordarlo agli utenti.  

1. Dal riquadro di spostamento sinistro di Reimpostazione della password, selezionare Notifiche.  Ricordare le due impostazioni: passare il mouse sopra l'icona delle informazioni per la descrizione.

1. Notare come il riquadro di spostamento di Reimpostazione della password include anche le opzioni per visualizzare i log di audit e l'utilizzo e le informazioni dettagliate.

1. Selezionare la X nell'angolo in alto a destra della pagina. In questo modo si torna alla pagina principale per il tenant di Contoso.

1. Tenere aperta questa pagina del browser per la prossima demo.

#### Verifica

Questa demo ha illustrato le impostazioni associate alla reimpostazione della password self-service. 

