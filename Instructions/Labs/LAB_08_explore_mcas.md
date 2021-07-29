---
lab:
    title: 'Esplorazione di Microsoft Cloud App Security'
    module: 'Modulo 3. Lezione 4. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione della protezione dalle minacce con Microsoft 365 Defender'
---


# Lab: Esplorazione di Microsoft Cloud App Security

## Scenario del lab
In questo lab, verranno esplorate le funzionalità di Microsoft Cloud App Security.  Verranno esaminate le informazioni disponibili sul dashboard Cloud Discovery nonché le funzionalità disponibili per indagare le scoperte e controllare l'impatto sulla propria organizzazione attraverso criteri.  Nota:  un'organizzazione deve avere una licenza per utilizzare Microsoft Cloud App Security, che è un servizio in abbonamento basato sull'utente. 

**Tempo stimato**: 15-20 minuti

#### Attività 1. Esplorare Cloud Discovery.

1.	Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale Microsoft 365 Defender.  

1. Dalla parte inferiore del riquadro di spostamento sinistro della pagina di Microsoft 365 Defender, selezionare **Altre risorse**.

1. Nella scheda **Microsoft Cloud App Security**, selezionare **Apri**.  Si apre una nuova pagina del browser sul dashboard di Cloud App Security.  Osservare le schede di informazioni disponibili.  È possibile che non sia visibile alcuna informazione sulle schede, dato che questo è un ambiente tenant di laboratorio preconfigurato che non è stato utilizzato attivamente.  

1. Dal riquadro di spostamento sinistro, selezionare **Individua**, quindi dal menu a discesa selezionare **Dashboard Cloud Discovery**.  Il dashboard include una panoramica delle app individuate, categorie di app, livelli di rischio e altro.  
    1. Dalla parte superiore della pagina Cloud Discovery, selezionare la scheda **App individuate**.  La finestra delle app individuate fornisce una vista più dettagliata delle app individuate, inclusi punteggio di rischio, traffico, numero di utenti e altro.
        1. Da qualsiasi voce dell'elenco, selezionare i **puntini di sospensione** nella colonna delle azioni della tabella.  Notare le varie opzioni disponibili, inclusa la funzione di contrassegnare un'app come approvata o non approvata.  Selezionare di nuovo i puntini di sospensione per chiudere la casella delle azioni.
        1. Selezionando una voce specifica si apre una pagina di dettagli per l'applicazione specifica.  Selezionare una voce dall'elenco.  Per la voce selezionata, esaminare ogni scheda nella parte superiore della pagina dei dettagli:  **Utilizzo**, **Info, Indirizzi** **IP**, **Utenti** e **Avvisi**. Dopo aver esaminato la pagina dei dettagli, tornare alle app scoperte selezionando **App individuate** dal riquadro di spostamento sinistro.
    1. Dalla parte superiore della pagina, selezionare la scheda **Indirizzi IP** (questa operazione equivale a selezionare gli indirizzi IP dal riquadro di spostamento a sinistra).  Qui sono riportati i dati tra cui il numero di transazioni, la quantità di traffico e le quantità di upload, per indirizzi IP.  È anche possibile filtrare per indirizzo IP specifico o esportare i dati per ulteriori analisi.
    1. Dalla parte superiore della pagina (o dal riquadro di spostamento sinistro) selezionare **Utenti**.  Questo è lo stesso tipo di informazioni fornite quando si selezionano gli indirizzi IP, ma sono elencate per i singoli utenti.  Anche qui, è possibile filtrare per utente specifico ed esportare i dati per ulteriori analisi.

1. Le informazioni fornite in queste schede si basano su report istantanei dai registri del traffico che caricati manualmente dai firewall e proxy o da report continui che analizzano tutti i registri che vengono inoltrati dalla rete utilizzando Cloud App Security.  Per vedere dove si trova questa impostazione, selezionare i **puntini di sospensione** nell'angolo in alto a destra della pagina.
    1. Selezionare la prima opzione, **Create Cloud Discovery snapshot report** (Crea report snapshot di Cloud Discovery). Qui si compilano i dettagli richiesti e si caricano i registri del traffico per generare e caricare un report.  Selezionare **Annulla**.  I dati visualizzati per il tenant di laboratorio provengono da un report Snapshot; queste informazioni sono riportate nell'angolo in alto a destra dello schermo.
    1. Per vedere l'opzione per i report continui, selezionare i **puntini di sospensione** nell'angolo in alto a destra della pagina e dal menu a tendina selezionare **Configura il caricamento automatico**.  Non ci sono origini dati collegate, ma è qui che si può aggiungere un'origine dati. Selezionare la freccia a discesa **Seleziona appliance** per vedere tutti i tipi di appliance che è possibile connettere come origine dati.  Selezionare **Annulla** per uscire.

1. Un altro punto da sottolineare è che è possibile connettersi alle app direttamente impostando i connettori delle app che offriranno una maggiore visibilità e controllo delle app cloud. Dall'angolo in alto a sinistra dello schermo, selezionare l'**icona dell'ingranaggio Impostazioni** e dall'elenco a discesa, selezionare **Connettori app**.  
    1. Nella pagina delle app collegate, dovrebbe essere visibile Office 365 nell'elenco con uno stato collegato.  Se Office 365 mostra un errore di connessione, molto probabilmente è perché Controllo non è attivato.
    1. Selezionare **+Connetti un'app** e dal menu a discesa selezionare **Microsoft Azure**.  Dalla finestra pop-up di Microsoft Azure, selezionare **Connetti Microsoft Azure**.  Verrà visualizzato lo stato connesso e le informazioni sulla scansione di utenti, dati e attività.  Selezionare il **pulsante Chiudi**.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Attività 2. Esplorare i modi in cui è possibile esaminare le attività registrate.

1. Dal riquadro di spostamento sinistro, sotto Esamina, selezionare **Log attività**.  Qui si ottiene la visibilità in tutte le attività dalle app connesse.   Poiché il connettore di Office 365 è già connesso, dovrebbero essere visibili alcuni dati. Dopo aver collegato Cloud App Security a un'app utilizzando il Connettore app, Cloud App Security scansiona tutte le attività che si sono verificate (il periodo di tempo della scansione retroattiva è diverso per ogni app) e poi viene aggiornato costantemente con nuove attività.  

1. Selezionare una voce per visualizzare informazioni più dettagliate. Nella parte superiore della pagina è presente l'opzione per aggiungere un nuovo criterio dalla ricerca o per esportare i dati per ulteriori analisi.  Selezionare **+Nuovo criterio dalla ricerca**.  È possibile creare un criterio basato su un modello, selezionare una gravità e una categoria del criterio, creare filtri per il criterio, creare avvisi e persino inviare gli avvisi a Power Automate.  Selezionare **Annulla** per uscire dalla finestra di creazione dei criteri.

1. Dal riquadro di spostamento sinistro, selezionare ed esplorare l'opzione **File** e notare le opzioni per filtrare i dati, creare un criterio per i file ed esportare i dati.  Selezionare ed esplorare l'opzione **utente e account**.  Notare le opzioni per filtrare ed esportare i dati.

1. Dal riquadro di spostamento sinistro, selezionare Configurazione di sicurezza. Questa pagina contiene le valutazioni della configurazione di sicurezza per gli account Azure, Amazon Web Services (AWS) e Google Cloud Platform (GCP).

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.


#### Attività 3. In questa attività si esploreranno le pagine dei criteri e degli avvisi in Microsoft Cloud App Security.

1. Dal riquadro di spostamento a sinistra, sotto dove è visualizzato Controllo, selezionare **Criteri**.  I criteri elencati forniscono informazioni sul numero di avvisi generati per criterio, gravità e così via. La selezione di una voce fornisce informazioni più dettagliate relative al criterio. Selezionare una voce dall'elenco, ad esempio, **Accesso a rischio**.  

1. Dal riquadro di spostamento sinistro, selezionare **Avvisi**.  Se sono elencati degli avvisi, selezionare una voce dall'elenco degli avvisi. Esaminare le informazioni fornite.  Dal lato superiore destro della finestra, selezionare **Chiudi avviso** per visualizzare le opzioni di chiusura dell'avviso.  

1. Chiudere la finestra del browser.

#### Verifica
In questo lab, sono state esplorate le funzionalità di Microsoft Cloud App Security.  Sono state esaminate le informazioni disponibili sul dashboard Cloud Discovery nonché le funzionalità disponibili per analizzare le scoperte e controllare l'impatto sulla propria organizzazione attraverso criteri.
