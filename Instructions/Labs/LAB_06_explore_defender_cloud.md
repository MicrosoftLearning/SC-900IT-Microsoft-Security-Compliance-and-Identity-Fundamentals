---
lab:
    title: 'Esplorare Microsoft Defender for Cloud'
    module: 'Modulo 3. Lezione 2. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione delle funzionalità di gestione della sicurezza di Azure'
---

# Lab: Esplorare Microsoft Defender for Cloud

## Scenario del lab
In questo lab verrà esplorato Microsoft Defender for Cloud e si apprenderà in che modo Azure Secure Score può essere usato per migliorare il profilo di sicurezza dell'organizzazione.

**Tempo stimato**: 30 minuti

#### Attività 1. Questa attività fornirà una breve presentazione di Microsoft Defender for Cloud.
1.	Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra Accedi immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Nell'angolo in alto a sinistra della schermata, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi nel riquadro di spostamento sinistro selezionare **Microsoft Defender for Cloud** in Preferiti.  Se non è incluso nell'elenco dei preferiti, immettere **Microsoft Defender for Cloud** nella casella di ricerca e quindi selezionare **Microsoft Defender for Cloud** nell'elenco dei risultati.

1. Osservare le informazioni disponibili nella pagina Panoramica di Microsoft Defender for Cloud.  

1. Potrebbe essere visualizzata una casella di informazioni blu in alto nella pagina, la quale indica che la visualizzazione delle informazioni potrebbe essere limitata.  Selezionare **fare clic qui**.
    1. Per assicurarsi di ottenere la visibilità a livello di tenant, assegnarsi il ruolo necessario.  Selezionare **Amministratore sicurezza**, quindi selezionare **Get access** (Ottieni accesso) nella parte inferiore della pagina.
    1. Verrà probabilmente visualizzato un messaggio del tipo "Il gruppo di gestione radice non esiste".  In base alla descrizione, verrà creato dal sistema il gruppo per conto dell'utente.  Per il completamento possono essere richiesti fino a 15 minuti, ma l'operazione è in genere più veloce.  Una volta concesso l'accesso, selezionare **Microsoft Defender for Cloud** nell'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Get permissions (Ottieni autorizzazioni), quindi aggiornare la pagina Panoramica di Microsoft Defender for Cloud.

1. Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede che rappresentano Punteggio di sicurezza, Conformità alle normative, Informazioni dettagliate, Azure Defender e altro.  

1. Nella parte superiore della pagina selezionare **Assessed resources** (Risorse valutate).  (Si noti che questo equivale alla selezione di Inventario nel riquadro di spostamento sinistro della home page di Microsoft Defender for Cloud).
    1. In questo modo si verrà reindirizzati alla pagina **Inventario** che mostra la sottoscrizione di Azure Pass.  Selezionare **Azure Pass – Sponsorizzazione**.
    1. La pagina Integrità risorse offre un elenco di raccomandazioni.  Dall'elenco disponibile, selezionare **There should be more than one owner assigned to your subscription** (È consigliabile assegnare più di un proprietario all'abbonamento).
    1. Selezionare la freccia a discesa accanto a Procedura di correzione. Osservare in che modo sono forniti i passaggi di correzione insieme all'opzione per intraprendere un'azione.  
    1. Selezionare **Microsoft Defender for Cloud** nell'angolo in alto a sinistra della schermata per tornare alla pagina Panoramica di Microsoft Defender for Cloud.

1. Dalla parte superiore della pagina selezionare **Raccomandazioni attive**.  (Si noti che questo equivale alla selezione di Raccomandazioni nel riquadro di spostamento sinistro della home page di Microsoft Defender for Cloud).
    1. La pagina delle raccomandazioni mostra il dashboard del punteggio di sicurezza.
    1. Sotto alla Dashboard del punteggio di sicurezza è presente un elenco di controlli. Ciascun controllo di sicurezza rappresenta un rischio di sicurezza che deve essere mitigato e include anche informazioni sul punteggio massimo associato al rispettivo controllo, il punteggio attuale, il potenziale aumento del punteggio e lo stato di integrità della risorsa.  
    1. Selezionare uno dei controlli, ad esempio **Abilita MFA**.  Selezionare una delle voci secondarie **È consigliabile abilitare MFA negli account con autorizzazioni di tipo proprietario per la sottoscrizione**.  Nella pagina che si apre saranno presenti una descrizione, la procedura di correzione e le risorse interessate. Uscire da questa pagina selezionando la **X** nell'angolo in alto a destra dello schermo.
    1. Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Dalla pagina principale selezionare **Conformità alle normative**. La pagina della conformità alle normative offre un elenco di controlli di conformità.  Sotto ciascun controllo è riportata una serie di valutazioni che sono basate su Azure Security Benchmark che offre raccomandazioni su come proteggere le soluzioni cloud su Azure.
    1. Selezionare **IM. Identity Management** (Gestione identità) e quindi selezionare **IM-6 Use strong authentication controls** (Usa controlli di autenticazione avanzati).  L'elenco mostra le azioni di responsabilità che il cliente può intraprendere per migliorare il profilo di conformità.
    1. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la pagina e tornare alla pagina Panoramica di Microsoft Defender for Cloud. 
    1. Lasciare aperta la pagina Panoramica di Microsoft Defender for Cloud aperta, perché verrà usata nell'attività successiva.


#### Attività 2. Con questa attività verranno esplorati Azure Secure Score e le raccomandazioni per migliorare il proprio punteggio di sicurezza. 

1. Dalla pagina Panoramica di Microsoft Defender for Cloud selezionare la scheda **Punteggio di sicurezza**.
1. Selezionare **Azure Pass – Sponsorizzazione**.  Annotarsi il proprio punteggio di sicurezza.
1. Dalla pagina delle raccomandazioni selezionare **Implement security best practices** (Implementa procedure consigliate di sicurezza) per espandere l'elenco. Notare che lo stato di integrità delle risorse è ora visualizzato in rosso.
1. Selezionare l'elemento **Devono essere presenti più proprietari assegnati alla propria sottoscrizione**, che mostra lo stato di integrità delle risorse in rosso. 
1. Sotto, nella sezione **Risorse interessate**, assicurarsi che l'opzione Risorse non integre sia selezionata/sottolineata e quindi selezionare la sottoscrizione di Azure elencata.
1. Dalla parte superiore della pagina del Controllo di accesso (IAM) selezionare **+ Aggiungi**, quindi dal menu a discesa selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).
    1. Dal lato sinistro della pagina selezionare **Proprietario** (dovrebbe essere la prima voce elencata) in modo che la riga risulti evidenziata in grigio, quindi selezionare **Avanti** in basso nella pagina.
    1. Accanto all'opzione Membri selezionare **+ Seleziona membri**. 
    1. Nella finestra Seleziona membri aperta sul lato destro della schermata selezionare **Alex Wilber**, quindi premere **Seleziona** in basso nella pagina.  
    1. Nella pagina Aggiungi assegnazione di ruolo verificare che Alex Wilber sia elencato come membro, quindi selezionare **Avanti** e poi **Rivedi e assegna**.
    1. L'aggiornamento dello stato potrebbe richiedere fino a 24 ore, dopodiché verrà aggiornato anche il punteggio di sicurezza in quanto tutti gli elementi nel gruppo Manage access and permissions (Gestisci accesso e autorizzazioni) sono soddisfatti.
    1. Dall'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Azure Pass, selezionare **Microsoft Defender for Cloud** per tornare alla pagina Panoramica di Microsoft Defender for Cloud.
1. Lasciare la pagina aperta per l'attività successiva.


#### Attività 3.  Ricordarsi che Microsoft Defender for Cloud viene offerto in due modalità: senza funzionalità di sicurezza avanzate (gratuitamente) e con funzionalità di sicurezza avanzate disponibili tramite i piani per Microsoft Defender for Cloud. In questa attività di scoprirà come abilitare/disabilitare i vari piani di Microsoft Defender for Cloud.

1.	Dalla pagina Panoramica di Microsoft Defender for Cloud selezionare **Impostazioni ambiente** dal riquadro di spostamento sinistro.
1. Selezionare il simbolo di maggiore **>** accanto a Gruppo radice tenant per espandere le informazioni (non selezionare direttamente Gruppo radice tenant perché si verrebbe reindirizzati a una pagina diversa), quindi selezionare **Azure Pass - Sponsorizzazione**.
1.	Nella pagina Piani di Defender notare che è possibile selezionare Abilita tutti oppure selezionare singoli piani di Defender. Lasciare le impostazioni esistenti con tutti i piani impostati su Off.
1.	Ora è possibile chiudere la scheda del browser per uscire dal portale di Azure.


#### Verifica
In questo lab è stato esplorato Microsoft Defender for Cloud e si è appreso in che modo Azure Secure Score può essere usato per migliorare il comportamento di sicurezza dell'organizzazione.
