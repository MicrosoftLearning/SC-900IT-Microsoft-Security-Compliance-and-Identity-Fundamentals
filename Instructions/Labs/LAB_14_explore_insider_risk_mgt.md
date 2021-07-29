---
lab:
    title: 'Esplorazione della Gestione dei rischi Insider in Microsoft 365'
    module: 'Modulo 4. Lezione 3. Descrizione delle funzionalità delle soluzioni di conformità Microsoft: Descrizione delle funzionalità di rischio Insider in Microsoft 365'
---


# Lab: Esplorazione della Gestione dei rischi Insider in Microsoft 365

## Scenario del lab
In questo lab, verrà descritto il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione del rischio Insider.  Nota:  questo lab fornirà soltanto visibilità degli elementi richiesti per impostare la gestione dei rischi Insider e le opzioni associate alla creazione di un criterio.  Questo lab non include un'attività per attivare il criterio, in quanto il numero di eventi necessari per attivare un criterio non rientra nell'ambito di questo esercizio.


**Tempo stimato**: 25-30 minuti

#### Attività 1. In questa attività, l'utente, in qualità di amministratore globale, abiliterà le autorizzazioni per Gestione del rischio Insider.  Specificamente, verranno aggiunti utenti al gruppo di ruoli Gestione dei rischi Insider per assicurare che gli utenti designati possano accedere e gestire le funzionalità di gestione dei rischi Insider.  L'applicazione delle autorizzazioni del gruppo di ruoli agli utenti nell'organizzazione potrebbe impiegare fino a 30 minuti. 

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Sicurezza**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale Microsoft 365 Defender.  

1. Dal riquadro di spostamento del portale di Microsoft 365 Defender, selezionare **Autorizzazioni e ruoli**.  Potrebbe essere necessario scorrere verso il basso per visualizzare l'opzione.

1. Dalla pagina Autorizzazioni e ruoli, sotto **Messaggio e-mail e ruoli di collaborazione** selezionare **Ruoli**.

1. Nella barra di ricerca immettere **Rischio Insider** quindi selezionare l'icona di ricerca (lente di ingrandimento).  Notare i cinque ruoli che vengono visualizzati.  Ciascuno ha diversi livelli di accesso.  Selezionare **Gestione dei rischi Insider**. 

1. Nella finestra che viene aperta accanto a dove c'è scritto Membri selezionare **Modifica**.

1. Per aggiungere membri a questo gruppo di ruoli, selezionare **Scegli membri**.

1. Selezionare **+ Aggiungi** dalla parte superiore della pagina.

1. Dall'elenco dei nomi, selezionare **Amministratore MOD**, **Megan Bowen** quindi selezionare **Aggiungi** nella parte inferiore della pagina, quindi selezionare **Fatto** nella parte inferiore della pagina.

1. Verificare che i membri aggiunti siano corretti, quindi selezionare **Salva**.

1. Dalla parte inferiore della finestra Gestione dei rischi Insider selezionare **Chiudi**.

1. Mantenere questa scheda del browser aperta, poiché servirà per un'attività successiva.


#### Attività 2 (IGNORARE se è stata eseguita l'attività del lab di impostazione per abilitare il log di controllo): Gestione dei rischi Insider usa i log di controllo Microsoft 365 per informazioni dettagliate e attività dell'utente identificate in criteri e informazioni dettagliate delle analisi. In questa attività, verrà abilitata la funzione di ricerca del log di controllo. Nota:  dopo l'attivazione della ricerca nel log di controllo, la restituzione di risultati quando si esegue la ricerca nel log di controllo potrebbe richiedere diverse ore.  Sebbene possa impiegare diverse ore prima di poter eseguire la ricerca nel log di controllo, non avrà un impatto sulla capacità di completare altre attività in questo lab.

1. Selezionare la scheda del browser con etichetta **Interfaccia di amministrazione di Microsoft 365 - Home page**.  Se in precedenza è stata chiusa questa scheda del browser, aprire Microsoft Edge e nella barra degli indirizzi immettere **admin.microsoft.com** e accedere con le credenziali di amministratore.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del Centro conformità Microsoft 365.  

1. Dal riquadro di spostamento sinistro del Centro conformità Microsoft 365 e poi selezionare **Mostra tutto**.

1. Dal riquadro di spostamento sinistro, sotto Soluzioni, selezionare **Controllo**.

1. Verificare che la scheda **Cerca** sia selezionata (sottolineata).

1. Una volta arrivati nella pagina Controllo, attendere 2-3 minuti.  Se il controllo non è abilitato, verrà visualizzata una barra blu in cima alla pagina per avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.

1. Tornare alla home page del Centro conformità Microsoft 365 selezionando **Home** dal riquadro di spostamento a sinistra.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

#### Attività 3. In questa attività verranno esaminate le impostazioni associate alla soluzione Gestione dei rischi Insider.  Le impostazioni di Gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto durante la creazione di un criterio. 

1. È necessario trovarsi nella home page del Centro conformità Microsoft 365. In caso contrario, aprire la scheda del browser **Home page - Conformità Microsoft 365**.

1. Dal riquadro di spostamento a sinistra sotto Soluzioni, selezionare **Gestione dei rischi Insider**.

1. Prima di iniziare a impostare un criterio, è necessario configurare alcune impostazioni.  Dalla pagina Gestione dei rischi Insider, selezionare l'**icona di ingranaggio delle impostazioni** sull'angolo in alto a destra della pagina per accedere alle impostazioni di Rischio Insider.  
    1. Scheda Privacy:  per gli utenti che eseguono attività che corrispondono ai criteri di rischio Insider, questa impostazione determinerà se mostrare i nomi effettivi o usare versioni anonime per nascondere le relative identità.  Selezionare **Non mostrare le versioni anonime dei nomi utente**, quindi selezionare **Salva**.  Selezionare la scheda **Indicatori di criteri**.
    
    1. Scheda Indicatori di criteri: Una volta che si verifica un criterio che attiva un evento, le attività che mappano agli indicatori selezionati sono usate per determinare il punteggio di rischio per l'utente. Gli indicatori di criteri selezionati qui sono inclusi nei modelli dei criteri dei rischi Insider.  Scorrere per visualizzare tutti gli indicatori disponibili e le informazioni associate. Sotto **Indicatori Office**, selezionare **Seleziona tutto**, quindi selezionare **Salva**.  Selezionare la scheda **Intervalli di criteri**.
    1. Scheda Intervalli di criteri:  Gli intervalli scelti qui si applicano quando un utente attiva una corrispondenza per un criterio di rischio Insider.   La finestra Attivazione determina per quanto tempo i criteri rileveranno attivamente l'attività per gli utenti e viene attivata quando un utente esegue la prima attività corrispondente a un criterio. Il rilevamento di attività passate determina quanto indietro nel tempo deve andare un criterio per rilevare l'attività di utente e viene attivato quando un utente esegue la prima attività corrispondente a un criterio.  Lasciare i valori predefiniti.  Selezionare la scheda **Rilevamenti intelligenti**.
    1. Scheda Rilevamenti intelligenti:  Esaminare le opzioni presenti.  Notare le impostazioni dei domini e la modalità con cui si correlano agli indicatori.
    1. Altri elementi elencati nelle impostazioni sono visualizzati in anteprima.  Esplorarli quando lo si desidera e tenere presente che, in quanto anteprima, sono soggette a modifiche.

1. Per tornare alla panoramica di Gestione dei rischi Insider, selezionare **Gestione dei rischi Insider** dall'angolo in alto a sinistra della pagina, sopra dove è visualizzato Impostazioni.

1. Mantenere la scheda del browser aperta perché verrà usata nell'attività successiva.

#### Attività 4.  In questa attività verrà spiegata la creazione di un criterio.

1. È necessario trovarsi nella pagina Gestione dei rischi Insider.  In caso contrario, aprire la scheda del browser con etichetta, **Gestione dei rischi Insider - Conformità Microsoft 365**.

1. Dalla pagina della panoramica Gestione dei rischi Insider, selezionare la scheda **Criteri**, quindi selezionare **+ Crea**.  Configurare ciascuna delle seguenti schede dei criteri.

    1. Modello criteri:  Dall'elenco di categorie, selezionare **Perdite di dati**, quindi selezionare **Perdite di dati generali**.  Tenere presente che per i modelli all'interno delle categorie possono esserci prerequisiti aggiuntivi.  Leggere i dettagli associati a questo modello, quindi selezionare **Avanti**.
    
    1. Nome e descrizione:  immettere un nome, **SC900-InsiderRiskPolicy**, quindi selezionare **Avanti**.
    1. Utenti e gruppi:  esaminare la casella delle informazioni.  Lasciare l'impostazione predefinita, **Includi tutti gli utenti e i gruppi**.  Selezionare **Avanti**.
    1. Contenuti a cui dare priorità: Leggere la descrizione. Selezionare **Desidero specificare siti SharePoint, etichette di riservatezza e/o tipi di informazioni sensibili come contenuto prioritario**, quindi selezionare **Avanti**.
        1. Sito SharePoint: per questo esempio di criterio, lasciare il campo vuoto, selezionare **Avanti**
        1. Tipi di informazioni sensibili: per questo esempio di criterio, lasciare il campo vuoto, quindi selezionare **Avanti**. 
        1. Etichette di riservatezza: selezionare **+ Aggiungi o modifica etichette di riservatezza**.  Selezionare le etichette elencate:  **Riservato - Finanza** e **Riservatezza elevata/Progetto – Falcon**, selezionare **Aggiungi**, quindi **Avanti**.
    1. Indicatori ed evento di attivazione: esaminare le informazioni dettagliate.  Il criterio viene attivato dall'utente che esegue un'attività di esfiltrazione come definita (selezionare le icone di informazioni per ciascun elenco puntato per informazioni più dettagliate) OPPURE una corrispondenza a un criterio Prevenzione della perdita dei dati (DLP) esistente.  Poiché non si dispone di criteri DLP configurati come parte di questo esercizio, selezionare **L'utente esegue un'attività di esfiltrazione**.  Scorrere verso il basso per visualizzare ciò che è automaticamente selezionato.  Notare che gli indicatori di criteri abilitati nell'attività precedente sono selezionati.   Tenere a mente che questi indicatori saranno attivati solo dopo l'attivazione del criterio e le attività che mappano a questi indicatori saranno usate per calcolare un punteggio di rischio per l'utente.  Inoltre, è abilitato il rilevamento di sequenza.  Se una sequenza di attività, come definita, viene rilevata, allora ne deriva un rischio maggiore.  Selezionare l'icona delle informazioni per informazioni dettagliate su cui sono richiesti gli indicatori.  Questa selezione richiede che determinati indicatori siano selezionati e che i dispositivi siano caricati.  Per questioni di semplicità e poiché non disponiamo di dispositivi caricati in questo tenant, deselezionare **Seleziona tutto**.  Selezionare **Avanti**.
    1. Soglie di indicatori:  qui è possibile specificare soglie predefinite o personalizzate associate agli indicatori.  Tenere a mente che gli indicatori sono attivati solo dopo che si verifica l'attivazione del criterio in modo tale che le soglie non influiscano quando il criterio è attivato. Selezionare **Specifica soglie personalizzate**. La selezione di questa opzione consentirà di visualizzare i valori predefiniti correnti. Lasciare i valori predefiniti e selezionare **Avanti**.  
    1. Fine:  esaminare le impostazioni, selezionare **Invia**, quindi selezionare **Fatto**.

1. Si è di nuovo nella scheda Criteri della pagina Gestione dei rischi Insider.  Il criterio appena creato sarà inserito nell'elenco.  

1. Nel criterio appena creato, il campo "Utenti nell'ambito" rappresenta gli utenti a cui vengono correntemente assegnati punteggi di rischio dal criterio.  L'assegnazione di punteggi di rischio agli utenti si verifica quando il criterio è attivato, ed è il motivo per cui il valore indica 0.  Un amministratore può configurare un criterio per iniziare ad assegnare punteggi di rischio a utenti specifici, in base all'attività rilevata dai criteri selezionati, E che bypassa il requisito per cui un evento di attivazione è rilevato per primo.  A questo scopo, selezionare il cerchio vuoto accanto al nome del criterio per selezionare il criterio, quindi selezionare **Inizia calcolo punteggio attività per utenti**, che è mostrato sopra alla tabella dei criteri.  Compilare ogni campo, quindi selezionare **Inizia calcolo punteggio attività**.  Prima che gli utenti siano visualizzati nella scheda "Utenti" potrebbero trascorrere 24 ore. Dopodiché, è possibile selezionare gli utenti dalla scheda per esaminare le attività rilevate.

#### Verifica
In questo lab, è stato spiegato il processo di impostazione di un criterio di rischio Insider, insieme ai prerequisiti di base per configurare e usare i criteri di gestione di rischi Insider.
