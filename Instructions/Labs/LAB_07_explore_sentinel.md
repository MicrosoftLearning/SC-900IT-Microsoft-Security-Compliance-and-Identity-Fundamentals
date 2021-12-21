---
lab:
    title: 'Esplorare Microsoft Sentinel'
    module: 'Modulo 3. Lezione 3. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: Descrivere le funzionalità di sicurezza di Microsoft Sentinel'
---


# Lab: Esplorare Microsoft Sentinel 

## Scenario del lab
Questo lab illustrerà il processo di creazione di un'istanza di Microsoft Sentinel.  Verranno anche configurate le autorizzazioni per garantire l'accesso alle risorse che verranno distribuite per supportare Microsoft Sentinel.  Una volta terminata la configurazione di base, verranno illustrati i passaggi per connettere Microsoft Sentinel alle origini dati, usando le funzionalità di analisi predefinite per ricevere notifiche di eventuali eventi sospetti e, infine, si esamineranno le funzionalità di automazione.  

  

**Tempo stimato**: 30-45 minuti

#### Attività 1.  Creare un'istanza di Microsoft Sentinel.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.azure.com**.

2. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

3. Nell'angolo in alto a sinistra della schermata, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi selezionare **Tutti i servizi**.  

4. Nella casella per filtrare i servizi immettere **Microsoft Sentinel**, quindi selezionare **Microsoft Sentinel** nell'elenco.

5. Dalla pagina di Microsoft Sentinel selezionare **Crea Microsoft Sentinel**.

6. Dalla pagina Aggiungi Microsoft Sentinel a un'area di lavoro, selezionare **Crea una nuova area di lavoro**.

7. Dalla scheda generale di Crea area di lavoro Log Analytics, inserire quanto segue:
    1. Sottoscrizione:  **Azure Pass – Sponsorizzazione**
   
    1. Gruppo di risorse: selezionare **Crea nuovo**, quindi immettere il nome **SC900-ResourceGroup**, selezionare infine **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Area: **Stati Uniti orientali** (lasciare questa impostazione predefinita)
    1. Selezionare **Avanti: Piano tariffario >**

8. Per il piano tariffario, lasciare le impostazioni predefinite: **Con pagamento in base al consumo (per GB 2018)**, quindi selezionare **Avanti: Tag >**.

9. Per i Tag, è possibile lasciare questo campo vuoto, quindi selezionare **Verifica + Crea**.

10. Verificare le informazioni inserite e selezionare **Crea**.

11. Se non si visualizza la nuova area di lavoro nell'elenco, selezionare **Aggiorna**, quindi **Aggiungi**.

12. Dopo aver aggiunto la nuova area di lavoro, verrà visualizzata la pagina | Notizie e guide di Microsoft Sentinel.  Osservare i tre passaggi elencati nella pagina Guida introduttiva.

13. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Attività 2.  Dopo aver creato l'istanza di Microsoft Sentinel, assicurarsi di disporre dell'accesso necessario alle risorse distribuite per il supporto di Microsoft Sentinel.  In questa attività si accederà alla pagina del controllo di accesso (IAM) per il gruppo di risorse creato con l'istanza di Microsoft Sentinel, verranno visualizzati i ruoli disponibili e ci si assegnerà (amministratore MOD) il ruolo richiesto. L'assegnazione del ruolo a livello di gruppo di risorse garantirà che il ruolo venga applicato a tutte le risorse distribuite per il supporto di Microsoft Sentinel.

1. Nell'angolo in alto a sinistra della pagina di Microsoft Sentinel, sopra a dove è visualizzato Microsoft Sentinel, selezionare **Tutti i servizi**.

2. Nella casella dei servizi del filtro, immettere i gruppi di risorse, quindi dall'elenco fornito selezionare **Gruppi di risorse**.

3. Dalla pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-ResourceGroup**.

4. Dalla pagina SC900-ResourceGroup, selezionare **Controllo di accesso (IAM)** dal riquadro di spostamento.

5. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale**.  Notare che il ruolo corrente è Amministratore della sicurezza.  Chiudere la finestra delle assegnazioni di Amministratore MOD selezionando la **X** nell'angolo in alto a destra della finestra.

6. Dalla pagina Controllo di accesso selezionare **+Aggiungi**, quindi selezionare **Add role assignment** (Aggiungi assegnazione di ruolo).

7. Si apre la finestra Add role assignment (Aggiungi assegnazione di ruolo).  Selezionare la freccia a discesa nel campo Seleziona un ruolo per visualizzare i ruoli disponibili.  Per questo lab, selezionare **Proprietario**.  NOTA:  Come procedura consigliata si dovrebbe assegnare il privilegio minimo richiesto per il ruolo.  Per riferimento, controllare le autorizzazioni in Microsoft Sentinel:  https://docs.microsoft.com/it-it/azure/sentinel/roles

8. Dall'elenco degli utenti visualizzati, selezionare **Amministratore MOD**.

9. Selezionare **Salva** nella parte inferiore della pagina.

10. Dalla pagina Controllo di accesso selezionare **Visualizza accesso personale** per confermare che il ruolo è stato aggiunto, quindi chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

11. Tornare alla pagina Tutti i servizi di Azure, selezionando **Tutti i servizi** dall'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Gruppi di risorse.

#### Attività 3.  In questa attività si esaminerà il processo di connessione di Microsoft Sentinel all'origine dati per iniziare a raccogliere dati. Nota: la visualizzazione dello stato connesso per un connettore può richiedere un po' di tempo (circa 30 minuti, a seconda del tenant).

1. Nella casella Filtra servizi della pagina Tutti i servizi immettere **Microsoft Sentinel**, quindi selezionare **Microsoft Sentinel** nell'elenco. 

2. Dalla pagina di Microsoft Sentinel selezionare l'area di lavoro creata con l'istanza di Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

3. Il primo passaggio con Microsoft Sentinel è quello di essere in grado di raccogliere dati. Dal riquadro di spostamento sinistro selezionare **Connettori dati**, elencati sotto la configurazione.

4. Dalla pagina Connettori dati, scorrere verso il basso nella finestra principale per visualizzare l'elenco completo dei connettori disponibili. Nella casella di ricerca della pagina dei connettori dati, immettere **Azure** e poi dall'elenco selezionare **Azure Active Directory**.

5. Verrà aperta la finestra del connettore di Azure Active Directory.  Selezionare **Apri pagina connettori**.

6. Dalla pagina del connettore di Azure Active Directory, esaminare la descrizione e notare il contenuto correlato che include cartelle di lavoro, query e modelli di regole analitiche.  

7. La scheda delle istruzioni nella finestra principale illustra i requisiti per l'integrazione di Microsoft Sentinel con Azure Active Directory.   In Configurazione selezionare **Log di accesso**, quindi selezionare Applica modifiche (è possibile scegliere più connettori).

8. Dalla scheda Passaggi successivi, notare l'elenco delle cartelle di lavoro raccomandate.   Sotto alle cartelle di lavoro raccomandate, selezionare **Log di accesso di Azure** (è possibile scegliere cartelle di lavoro aggiuntive).

9. Dalla pagina delle cartelle di lavoro e con la scheda dei modelli selezionata (sottolineata), selezionare **Log di accesso di Azure**. 

10. Dalla finestra Log di accesso di Azure AD che si apre, esaminare la descrizione e selezionare **Visualizza modello**.  Uscire dal modello selezionando la **X** nell'angolo in alto a destra dello schermo.  Selezionare **Salva** dalla parte inferiore della pagina, quindi selezionare **OK** per salvare la cartella di lavoro nella posizione predefinita.

11. Dall'angolo in alto a sinistra della pagina Cartelle di lavoro, sopra Cartelle di lavoro, selezionare **Microsoft Sentinel**. In questo modo si torna alla pagina Connettori di dati di Microsoft Sentinel.

12. La parte alta della pagina dei connettori dati dovrebbe mostrare 1 connesso, per indicare che si è ora connessi ad Azure Active Directory.

13. Dal riquadro di spostamento sinistro, selezionare **Cartelle di lavoro**.

14. Dalla pagina Cartelle di lavoro, selezionare la scheda **Cartelle di lavoro personali** sopra la casella di ricerca.  La cartella di lavoro appena salvata è elencata e disponibile per visualizzare e monitorare i dati.

15. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Attività 4.  In questa attività verrà esaminato il processo per usare un modello di regola di analisi integrato per creare una regola in modo da ricevere una notifica quando si verifica qualcosa di sospetto.

1. Dal riquadro di spostamento sinistro, selezionare **Analisi**.

2. La pagina Analisi mostrerà le regole attive (il rilevamento avanzato degli attacchi multistadio è abilitato per impostazione predefinita) e fornirà anche l'accesso ai Modelli di regola.  Selezionare la scheda **Modelli di regola**.  Notare l'elenco dei modelli disponibili e i diversi modi per filtrare l'elenco.  Usando gli avvisi di analisi predefiniti all'interno dell'area di lavoro di Microsoft Sentinel, è possibile ricevere una notifica quando si verifica qualcosa di sospetto.

3. Nella barra di ricerca immettere **Portale di Azure**.  Selezionare **Tentativi di accesso non riusciti al portale di Azure**.  

4. Dalla finestra che si apre, leggere la descrizione ed esaminare le informazioni associate al modello.  Selezionare **Crea regola** nella parte inferiore della pagina.

5. Dalla procedura guidata delle regole di analisi, esaminare le informazioni, quindi selezionare **Avanti: Imposta logica regola >**.

6. Nella pagina Imposta logica regola è possibile definire la logica per la nuova regola di analisi. Il modello offre già alcune logiche e impostazioni predefinite.  Scorrere la pagina per visualizzare le impostazioni disponibili.  Lasciare i valori predefiniti. Selezionare **Avanti: Impostazioni degli eventi imprevisti (anteprima)>**.

7. Con Impostazioni degli eventi imprevisti, gli avvisi di Microsoft Sentinel possono essere raggruppati in un evento imprevisto che dovrebbe essere esaminato. È possibile impostare se gli avvisi che vengono attivati da questa regola di analisi devono generare eventi imprevisti.  Lasciare le impostazioni predefinite e selezionare **Avanti: Risposta automatica >**.

8. Nella scheda Risposta automatica è possibile aggiungere un playbook per automatizzare la risposta.  Analogamente, è possibile creare una regola di automazione dell'evento imprevisto.  Selezionare **+Aggiungi nuovo** sotto Automazione dell'evento imprevisto.  Viene aperta una finestra per creare una nuova regola di automazione.  Qualsiasi regola di automazione creata in questa pagina viene attivata dalla regola di analisi che si sta creando. Notare che è possibile aggiungere condizioni e impostare azioni per la regola.   Selezionare **Annulla** per uscire dalla finestra.

9. Selezionare **Avanti: Verifica>** per esaminare tutti i dettagli associati alla regola e basati sul modello selezionato. A questo punto, è possibile scegliere di creare la regola, selezionando **Crea** o uscire senza creare la regola selezionando **X** nell'angolo in alto a destra della pagina.

10. Tenere aperta la pagina poiché verrà usata nell'attività successiva.

#### Attività 5.  Nell'attività precedente è stata creata una regola di analisi per ricevere un avviso in caso di attività sospette.  Incorporata in questa procedura guidata c'è l'opzione per automatizzare la risposta a un incidente in base alla regola specifica.  Ma è anche possibile creare regole di automazione andando direttamente all'opzione di configurazione dell'automazione.

1. Dal riquadro di spostamento sinistro, selezionare **Automazione**.  

2. Selezionare **+ Crea**. Dal menu a discesa notare come è possibile selezionare o aggiungere un nuovo playbook o aggiungere una nuova regola.  Selezionare **Aggiungi nuova regola**.  

3. Viene aperta una finestra per creare una nuova regola di automazione.  Tenere presente che è possibile aggiungere condizioni e impostare azioni per la regola.  L'unica distinzione è che la prima condizione è quella di associare la regola o le regole di analisi a cui si vuole applicare questa regola di automazione.  Compare in grigio nell'attività precedente perché l'automazione è stata configurata per la regola specifica.  Selezionare **Annulla** per uscire dalla finestra Crea nuova regola di automazione.

4. Tenere aperta la pagina poiché verrà usata nell'attività successiva.


#### Attività 6.  Eliminare il gruppo di risorse di Microsoft Sentinel.  La fatturazione per Microsoft Sentinel avviene in base al volume di dati inseriti per l'analisi in Microsoft Sentinel. Sebbene la quantità di dati inseriti come conseguenza a questo lab sia minima, è consigliabile eliminare il gruppo di risorse di Microsoft Sentinel dopo aver completato l'esplorazione delle funzionalità di Microsoft Sentinel.

1. Dalla pagina di Microsoft Sentinel, nell'angolo in alto a sinistra della pagina, sopra a dove è visualizzato Microsoft Sentinel, selezionare **Tutti i servizi**.

2. Nella casella dei servizi del filtro, immettere i gruppi di risorse, quindi dall'elenco fornito selezionare **Gruppi di risorse**.

3. Dalla pagina Gruppi di risorse selezionare il gruppo di risorse creato con Microsoft Sentinel, **SC900-ResourceGroup**.

4. Dalla parte centrale in alto della pagina, selezionare **Elimina gruppo di risorse**.  Esaminare l'avviso.  Immettere il nome del gruppo di risorse, **SC900-ResourceGroup**, quindi selezionare **Elimina** dalla parte inferiore della pagina.  L'eliminazione del gruppo di risorse impiegherà diversi minuti.

5. Una volta verificato che il gruppo di risorse è stato eliminato, chiudere la pagina del browser. 


#### Verifica

In questo lab è stato esaminato il processo per creare un'istanza di Microsoft Sentinel.  Si è visto anche come configurare le autorizzazioni per garantire l'accesso alle risorse associate all'istanza di Microsoft Sentinel.  Dopo aver creato l'istanza di Microsoft Sentinel, sono stati illustrati i passaggi per connettere Microsoft Sentinel alle origini dati e usare le regole di analisi predefinite per ricevere notifiche per un evento sospetto, infine sono state esplorate le funzionalità di automazione. Il lab è terminato eliminando il gruppo di risorse associato all'istanza di Microsoft Sentinel creata.
