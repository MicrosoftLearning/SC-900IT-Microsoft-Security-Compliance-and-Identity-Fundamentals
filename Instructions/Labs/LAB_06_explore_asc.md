---
lab:
    title: 'Esplorazione del Centro sicurezza di Azure'
    module: 'Modulo 3. Lezione 2. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione delle funzionalità di gestione della sicurezza di Azure'
---


# Lab: Esplorazione del Centro sicurezza di Azure 

## Scenario del lab
In questo lab, verrà esplorato il Centro sicurezza di Azure e si apprenderà in che modo Azure Secure Score può essere usato per migliorare il profilo di sicurezza dell'organizzazione.

  

**Tempo stimato**: 10-15 minuti

#### Attività 1. Questa attività fornirà una breve presentazione del Centro sicurezza di Azure.
1.	Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nell'angolo in alto a sinistra della schermata, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi selezionare **Tutti i servizi**.  
1. Nella casella dei servizi di filtro, immettere **Centro sicurezza**, quindi selezionare **Centro sicurezza** dall'elenco dei risultati.
1. Osservare le informazioni disponibili sulla pagina della panoramica del Centro sicurezza.  
1. Potrebbe essere visualizzata una casella di informazioni blu in alto nella pagina la quale indica che la visualizzazione delle informazioni potrebbe essere limitata.  Selezionare **fare clic qui**.
    1. Per assicurarsi di ottenere la visibilità a livello di tenant, assegnarsi il ruolo necessario.  Selezionare **Amministratore sicurezza**, quindi selezionare **Get access** (Ottieni accesso) nella parte inferiore della pagina.
   
     1. Verrà probabilmente visualizzato un messaggio del tipo "Il gruppo di gestione radice non esiste".  In base alla descrizione, verrà creato dal sistema il gruppo per conto dell'utente.  Il completamento dell'operazione potrebbe richiedere fino a 15 minuti (ma solitamente è più rapido), dopodiché è possibile ripetere il processo per ottenere l'accesso.  Una volta concesso l'accesso, selezionare **Centro sicurezza** nell'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Get permissions (Ottieni autorizzazioni), quindi aggiornare la pagina della panoramica del Centro sicurezza.
1. Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede che rappresentano Punteggio di sicurezza, Conformità alle normative, Informazioni dettagliate, Azure Defender e altro.  
1. Nella parte superiore della pagina selezionare **Assessed resources** (Risorse valutate).  In questo modo si verrà reindirizzati alla pagina dell'inventario che mostra la sottoscrizione di Azure Pass.  Selezionare **Azure Pass – Sponsorizzazione**.
1. La pagina Integrità risorse offre un elenco di raccomandazioni.  Dall'elenco disponibile, selezionare **There should be more than one owner assigned to your subscription** (È consigliabile assegnare più di un proprietario all'abbonamento). 
1. Selezionare la freccia a discesa accanto a Procedura di correzione. Osservare in che modo sono forniti i passaggi di correzione insieme all'opzione per intraprendere un'azione.  
1. Selezionare **Centro sicurezza** nell'angolo in alto a sinistra della schermata per tornare alla pagina della panoramica del Centro sicurezza.
1. Dalla parte superiore della pagina selezionare **Raccomandazioni attive**.  
1. La pagina delle raccomandazioni mostra azioni specifiche che possono essere eseguite per aumentare possibilmente il punteggio di sicurezza.  Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra della schermata.
1. Dalla pagina principale, selezionare **Conformità alle normative**.
1. La pagina della conformità alle normative offre un elenco di controlli di conformità.  Sotto ciascun controllo è riportata una serie di valutazioni che sono basate su Azure Security Benchmark che offre raccomandazioni su come proteggere le soluzioni cloud su Azure.
1. Selezionare **IM. Gestione delle identità** quindi selezionare **IM.4 Use strong authentication controls for all Azure Active Directory based access** (Utilizzare controlli di autenticazione forti per tutti gli accessi basati su Azure Active Directory).  L'elenco mostra azioni di responsabilità che il cliente può intraprendere per migliorare il profilo di conformità.
1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la pagina e tornare alla pagina della panoramica del Centro sicurezza. 
1. Lasciare la pagina della panoramica del Centro sicurezza aperta, perché verrà utilizzata nell'attività successiva.


#### Attività 2. Con questa attività verranno esplorati Azure Secure Score e le raccomandazioni per migliorare il proprio punteggio di sicurezza. 

1. Dalla pagina della panoramica del Centro sicurezza, selezionare la scheda **Punteggio di sicurezza**.

2. Selezionare **Azure Pass – Sponsorizzazione**.  Annotarsi il proprio punteggio di sicurezza.
3. Dalla pagina delle raccomandazioni, selezionare **Manage access and permissions** (Gestisci accesso e autorizzazioni). Tenere presente che nel gruppo c'è un elemento rosso.
4. Selezionare l'elemento **Devono essere presenti più proprietari assegnati alla propria sottoscrizione**, che mostra lo stato di integrità risorse in rosso. Se la selezione di questo elemento non funziona.
    1. Dall'angolo in alto a sinistra della pagina, selezionare **Centro sicurezza**, sopra a dove è visualizzato Raccomandazioni.
    
    1. Dal riquadro di spostamento sinistro, selezionare **Raccomandazioni**.
    1. Dalla pagina delle raccomandazioni, selezionare **Manage access and permissions** (Gestisci accesso e autorizzazioni). Tenere presente che nel gruppo c'è un elemento rosso.
    1. Selezionare l'elemento **Devono essere presenti più proprietari assegnati alla propria sottoscrizione**, che mostra lo stato di integrità risorse in rosso. 
5. Selezionare la **sottoscrizione di Azure**.
6. Dalla parte superiore della pagina del Controllo di accesso (IAM), selezionare **+ Aggiungi**, quindi dal menu a discesa selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).
7. Nel campo Ruolo, immettere **Proprietario**, quindi selezionare **Proprietario** dall'elenco in basso.
8. Dall'elenco di utenti, selezionare **Alex Wilber**, quindi selezionare **Salva** nella parte inferiore della pagina.
9. L'aggiornamento dello stato potrebbe richiedere fino a 24 ore, dopodiché verrà aggiornato anche il punteggio di sicurezza in quanto tutti gli elementi nel gruppo Manage access and permissions (Gestisci accesso e autorizzazioni) sono soddisfatti.
10. Dall'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Azure Pass, selezionare **Centro sicurezza**, quindi selezionare **Panoramica** per tornare alla pagina della panoramica del Centro sicurezza.
11. Lasciare la pagina aperta per l'attività successiva.


#### Attività 3.  Ricordarsi che il Centro sicurezza è fornito in due modalità: Azure Defender OFF (gratuito) e Azure Defender ON. In questa attività si apprenderà come abilitare e disabilitare Azure Defender.

1.	Dalla pagina della panoramica del Centro sicurezza, selezionare **Enable Azure Defender** (Abilita Azure Defender) dalla scheda Azure Defender.

2.	Selezionare la casella **Azure Defender - On**.  Osservare in che modo tutti i piani di Defender cambiano stato su On e osservare i prezzi per ogni elemento, quindi selezionare **Salva** dall'angolo in alto a sinistra della pagina.
3.	Tornare alla pagina del Centro sicurezza, selezionando **Centro sicurezza** dall'angolo in alto a sinistra della pagina.   L'applicazione della modifica della scheda di Azure Defender potrebbe richiedere diversi minuti.  Aggiornare la pagina, se necessario.
4.	Per disabilitare Azure Defender, selezionare **Pricing & settings** (Prezzi e impostazioni) dal riquadro di spostamento a sinistra della pagina del Centro sicurezza, selezionare **Sottoscrizione di Azure Pass – Sponsorship**.
5.	Dalla pagina dei piani di Azure Defender, selezionare la casella **Azure Defender - Off**, quindi selezionare **Salva** dall'angolo in alto a sinistra della pagina.
6.	Viene visualizzata una finestra popup che richiede la conferma per il downgrade.  Deselezionare la casella per essere contattati da Microsoft, quindi selezionare **Conferma**.
7.	Ora è possibile chiudere la scheda del browser per uscire dal portale di Azure.


#### Verifica
In questo lab, è stato esplorato il Centro sicurezza di Azure e si è appreso in che modo Azure Secure Score può essere usato per migliorare il profilo di sicurezza dell'organizzazione.
