---
Demo:
    title: 'Microsoft Sentinel'
    module: 'Modulo 3. Lezione 3. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: Descrivere le funzionalità di sicurezza di Microsoft Sentinel'
---


# Demo: Microsoft Sentinel 

### Scenario demo
Questa demo illustrerà il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Una volta terminata la configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati, usando le funzionalità di analisi predefinite per ricevere notifiche di eventuali eventi sospetti e, infine, si esamineranno le funzionalità di automazione.  

#### Demo Parte 1:  Creare un'istanza di Microsoft Sentinel

1. Aprire la scheda del browser **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** nei risultati della ricerca.

1. Dalla pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

1. Dalla pagina Aggiungi Microsoft Sentinel a un'area di lavoro, selezionare **Crea una nuova area di lavoro**.

1. Nella scheda Informazioni di base di Crea area di lavoro Log Analytics immettere quanto segue:
    1. Sottoscrizione:  **Azure Pass – Sponsorizzazione**
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi inserire il nome **SC900-Sentinel-RG** e selezionare **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (lasciare questa impostazione predefinita)
    1. Selezionare **Avanti: Piano tariffario >**

1. Per il piano tariffario, lasciare le impostazioni predefinite: **Con pagamento in base al consumo (per GB 2018)**, quindi selezionare **Avanti: Tag >**.

1. Per i Tag, è possibile lasciare questo campo vuoto, quindi selezionare **Verifica + Crea**.

1. Verificare le informazioni inserite e selezionare **Crea**.

1. Potrebbe volerci un minuto o due perché la nuova area di lavoro compaia nell'elenco; se non compare, selezionare **Aggiorna**, quindi selezionare **Aggiungi**.

1. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina | Notizie e guide di Microsoft Sentinel.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Demo Parte 2:  Dopo aver creato l'istanza di Microsoft Sentinel, assicurarsi di disporre dell'accesso necessario alle risorse distribuite per il supporto di Microsoft Sentinel.  In questa attività si accederà alla pagina del controllo di accesso (IAM) per il gruppo di risorse creato con l'istanza di Microsoft Sentinel, verranno visualizzati i ruoli disponibili e ci si assegnerà (amministratore MOD) il ruolo richiesto. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppi di risorse** quindi selezionare **Gruppi di risorse** dai risultati della ricerca.

1. Dalla pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla pagina SC900-Sentinel-RG, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento sinistro.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Notare che il ruolo corrente è Amministratore del servizio.  Chiudere la finestra delle assegnazioni di Amministratore MOD selezionando la **X** nell'angolo in alto a destra della finestra.

1. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

1. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Selezionare la freccia a discesa nel campo Seleziona un ruolo per visualizzare i ruoli disponibili. Nella casella di ricerca Seleziona un ruolo, immettere **Microsoft Sentinel** per visualizzare i 4 ruoli associati a Microsoft Sentinel. Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  Ai fini di questa esercitazione, inserire **Proprietario** nella casella di ricerca e selezionare **Proprietario** dai risultati.  Per riferimento, controllare le autorizzazioni in Microsoft Sentinel:  https://docs.microsoft.com/it-it/azure/sentinel/roles

1. Dall'elenco degli utenti visualizzati, selezionare **Amministratore MOD**.

1. Selezionare **Salva** nella parte inferiore della pagina.

1. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale** per confermare che il ruolo è stato aggiunto, quindi chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

#### Demo Parte 3:  Questa parte della demo illustrerà il processo di connessione di Microsoft Sentinel all'origine dati per iniziare la raccolta dei dati.  Nota: la visualizzazione dello stato connesso per un connettore può richiedere un po' di tempo (circa 30 minuti, a seconda del tenant).

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure immettere **Microsoft Sentinel** e quindi selezionare **Microsoft Sentinel** nei risultati della ricerca.

1. Dalla pagina di Microsoft Sentinel selezionare l'area di lavoro creata con l'istanza di Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. Il primo passaggio con Microsoft Sentinel è quello di essere in grado di raccogliere dati. Dal riquadro di spostamento sinistro selezionare **Connettori dati**, elencati sotto la configurazione.

1. Dalla pagina Connettori dati, scorrere verso il basso nella finestra principale per visualizzare l'elenco completo dei connettori disponibili. Nella casella di ricerca della pagina dei connettori dati, immettere **Azure** e poi dall'elenco selezionare **Azure Active Directory**.

1. Verrà aperta la finestra del connettore di Azure Active Directory.  Selezionare **Apri pagina connettori**.

1. Dalla pagina del connettore di Azure Active Directory, esaminare la descrizione e notare il contenuto correlato che include cartelle di lavoro, query e modelli di regole analitiche.  

1. La scheda delle istruzioni nella finestra principale illustra i prerequisiti per l'integrazione di Microsoft Sentinel con Azure Active Directory.   In Configurazione selezionare **Log di accesso**, quindi selezionare Applica modifiche (è possibile scegliere più connettori).  Nota: possono volerci alcuni minuti per vedere lo stato connesso del connettore (circa 30 minuti).  Per riferimento:
    1. Controllare le autorizzazioni in Microsoft Sentinel:  https://docs.microsoft.com/it-it/azure/sentinel/roles
    1. Connettersi ad Azure Active Directory:  https://docs.microsoft.com/it-it/azure/sentinel/connect-azure-active-directory

1. Dalla scheda Passaggi successivi, notare l'elenco delle cartelle di lavoro raccomandate.   Sotto alle cartelle di lavoro raccomandate, selezionare **Log di accesso di Azure** (è possibile scegliere cartelle di lavoro aggiuntive).

1. Dalla pagina delle cartelle di lavoro e con la scheda dei modelli selezionata (sottolineata), selezionare **Log di accesso di Azure**.

1. Dalla finestra Log di accesso di Azure AD che si apre, esaminare la descrizione e selezionare **Visualizza modello**.  Uscire dal modello selezionando la **X** nell'angolo in alto a destra dello schermo.  Selezionare **Salva** dalla parte inferiore della pagina, quindi selezionare **OK** per salvare la cartella di lavoro nella posizione predefinita.

1. Dall'angolo in alto a sinistra della pagina Cartelle di lavoro, sopra Cartelle di lavoro, selezionare **Microsoft Sentinel**. In questo modo si torna alla pagina Connettori di dati di Microsoft Sentinel.

1. Nella parte superiore della pagina dei connettori dati dovrebbe esserne indicato 1 connesso, a conferma che si è ora connessi ad Azure Active Directory.

1. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**.

1. Dalla pagina Cartelle di lavoro, selezionare la scheda **Cartelle di lavoro personali** sopra la casella di ricerca.  La cartella di lavoro appena salvata è elencata e disponibile per visualizzare e monitorare i dati.  Gli accessi successivi si rifletteranno nella cartella di lavoro, quindi si può scegliere di mostrarli.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Demo Parte 4 (opzionale):  Questa parte della demo illustrerà il processo di utilizzo di un modello di regola di analisi integrata per creare una regola per ricevere una notifica quando si verifica un evento sospetto.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.

1. La pagina Analisi mostrerà le regole attive (il rilevamento avanzato degli attacchi multistadio è abilitato per impostazione predefinita) e fornirà anche l'accesso ai Modelli di regola.  Selezionare la scheda **Modelli di regola**.  Notare l'elenco dei modelli disponibili e i diversi modi per filtrare l'elenco.  Usando gli avvisi di analisi predefiniti all'interno dell'area di lavoro di Microsoft Sentinel è possibile ricevere una notifica quando si verifica qualcosa di sospetto.

1. Nella barra di ricerca immettere **Portale di Azure**.  Selezionare **Tentativi di accesso non riusciti al portale di Azure**.  

1. Dalla finestra che si apre, leggere la descrizione ed esaminare le informazioni associate al modello.  Selezionare **Crea regola** nella parte inferiore della pagina.
    1. Dalla procedura guidata delle regole di analisi, esaminare le informazioni, quindi selezionare **Avanti: Imposta logica regola >**.
    1. Nella pagina Imposta logica regola è possibile definire la logica per la nuova regola di analisi. Il modello offre già alcune logiche e impostazioni predefinite.  Scorrere la pagina per visualizzare le impostazioni disponibili.  Lasciare i valori predefiniti. Selezionare **Avanti: Impostazioni degli eventi imprevisti (anteprima)>**.
    1. Con Impostazioni degli eventi imprevisti, gli avvisi di Microsoft Sentinel possono essere raggruppati in un evento imprevisto che dovrebbe essere esaminato. È possibile impostare se gli avvisi che vengono attivati da questa regola di analisi devono generare eventi imprevisti.  Lasciare le impostazioni predefinite e selezionare **Avanti: Risposta automatica >**.
    1. Nella scheda Risposta automatica è possibile aggiungere un playbook per automatizzare la risposta.  Analogamente, è possibile creare una regola di automazione dell'evento imprevisto.  Selezionare **+Aggiungi nuovo** sotto Automazione dell'evento imprevisto.  Viene aperta una finestra per creare una nuova regola di automazione.  Ogni regola di automazione creata su questa pagina viene attivata tramite la regola di analisi selezionata in origine, in questo caso, Tentativi di accesso non riusciti al portale di Azure.  Tenere presente che è possibile aggiungere condizioni e impostare azioni per la regola.   Selezionare **Annulla** per uscire dalla finestra.
    1. Selezionare **Avanti: Verifica>** per esaminare tutti i dettagli associati alla regola e basati sul modello selezionato. A questo punto, è possibile scegliere di creare la regola, selezionando **Crea** o uscire senza creare la regola selezionando **X** nell'angolo in alto a destra della pagina.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Demo Passaggio 5 (opzionale):  Nel passaggio precedente è stata creata una regola di analisi per ricevere un avviso in caso di attività sospette.  Incorporata in questa procedura guidata c'è l'opzione per automatizzare la risposta a un incidente in base alla regola specifica.  Ma è anche possibile creare regole di automazione andando direttamente all'opzione di configurazione dell'automazione.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  

1. Selezionare **+ Crea**. Dal menu a discesa notare come è possibile selezionare o aggiungere un nuovo playbook o aggiungere una nuova regola.  Selezionare **Aggiungi nuova regola**.  
    1. Viene aperta una finestra per creare una nuova regola di automazione.  Tenere presente che è possibile aggiungere condizioni e impostare azioni per la regola.  L'unica distinzione è che la prima condizione è quella di associare la regola o le regole di analisi a cui si vuole applicare questa regola di automazione.  Compare in grigio nell'attività precedente perché l'automazione è stata configurata per la regola specifica.  Selezionare **Annulla** per uscire dalla finestra Crea nuova regola di automazione.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Passaggio 6: ELIMINARE - L'istruttore esegue questo passaggio dopo la lezione. Eliminare il gruppo di risorse di Microsoft Sentinel.  La fatturazione per Microsoft Sentinel avviene in base al volume di dati inseriti per l'analisi in Microsoft Sentinel. Sebbene la quantità di dati inseriti con questo lab sia minima, è consigliabile eliminare il gruppo di risorse di Microsoft Sentinel dopo aver completato l'esplorazione delle funzionalità di Microsoft Sentinel.

1. Nell'angolo in alto a sinistra della pagina di Microsoft Sentinel, sopra a dove è visualizzato Microsoft Sentinel, selezionare **Tutti i servizi**.

1. Nella casella per filtrare i servizi immettere gruppi di risorse, quindi selezionare **Gruppi di risorse** nell'elenco visualizzato.

1. Dalla pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Dalla parte centrale in alto della pagina selezionare **Elimina gruppo di risorse**.  Esaminare l'avviso.  Inserire il nome del gruppo di risorse, **SC900-Sentinel-RG**, quindi selezionare **Elimina** dalla parte inferiore della pagina.  L'eliminazione del gruppo di risorse impiegherà diversi minuti.

1. Una volta verificato che il gruppo di risorse è stato eliminato, chiudere la pagina del browser. 

#### Verifica

Questa demo ha illustrato il processo di creazione di un'istanza di Microsoft Sentinel.  Si è visto come configurare le autorizzazioni per garantire l'accesso alle risorse associate all'istanza di Microsoft Sentinel.  Dopo aver creato l'istanza di Microsoft Sentinel, sono stati eseguiti i passaggi per connettere Microsoft Sentinel alle origini dati, si è visto come usare le regole di analisi predefinite per ricevere una notifica di eventuali eventi sospetti e infine sono state esaminate le funzionalità di automazione. La demo è terminata eliminando il gruppo di risorse associato all'istanza di Microsoft Sentinel creata.