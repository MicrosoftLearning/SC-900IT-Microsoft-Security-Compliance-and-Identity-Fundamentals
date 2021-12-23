---
lab:
    title: 'Esplorazione dei Criteri di Azure'
    module: 'Modulo 4. Lezione 5. Descrizione delle funzionalità delle soluzioni di conformità Microsoft: descrizione dei criteri di Azure'
---


# Lab: Esplorazione dei Criteri di Azure

## Scenario del lab
Criteri di Azure consente di applicare gli standard dell'organizzazione e di valutare la conformità su larga scala. Criteri di Azure valuta le risorse in Azure confrontando le proprietà di quelle risorse con le business rules. In questo lab, lo studente inizierà esplorando la pagina di destinazione Criteri di Azure. Dopo aver esplorato la pagina Criteri di Azure, lo studente creerà un criterio ed esaminerà gli effetti del criterio creato.


**Tempo stimato**: 20-25 minuti

#### Attività 1. Esplorare brevemente la pagina Criteri di Azure.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Ora ci si trova nel portale di Azure.  Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **criteri**, quindi selezionare **Criteri** dai risultati della ricerca. Viene aperta la home page Criteri che fornisce una vista del dashboard.  L'ambito nel quale vengono visualizzate le informazioni è determinato dall'Azure Pass che si sta utilizzando, come parte di questo lab.   Notare le informazioni disponibili nel dashboard.

1. È presente la voce ASC Default (ASC sta per Centro sicurezza di Azure, ora denominato Microsoft Defender for Cloud) con ambito Azure Pass – Sponsorizzazione.   Selezionare **ASC Default**.

1. In alto sulla pagina, sotto Essentials, si possono vedere nome, descrizione e altre informazioni essenziali.  Leggere la descrizione (far scorrere il mouse sopra la descrizione). NOTA: il campo della descrizione fa riferimento al Centro sicurezza di Azure, rinominato Microsoft Defender for Cloud.

1. Notare che le informazioni fornite dal dashboard vengono aggiornate per riflettere l'elemento selezionato, la definizione dell'iniziativa ASC Default.  Si ricordi che la definizione di un'iniziativa è una raccolta di definizioni di criteri che mirano a raggiungere un singolo obiettivo generale. Le informazioni possono essere visualizzate per gruppi, criteri, risorse non conformi o eventi.

1. Uscire dalla pagina ASC e tornare alla home page dei criteri selezionando la **X** nell'angolo in alto a destra della finestra.

1. Dal riquadro di spostamento sinistro, selezionare **Attività iniziali**.  Vengono visualizzare le varie opzioni disponibili, inclusa l'opzione per sfogliare i criteri integrati e assegnare i criteri su larga scala, e si possono creare definizioni di criteri personalizzate per il proprio ambiente, consigliare assegnazioni di criteri e molto altro ancora.

1. Dal riquadro di spostamento sinistro, selezionare **Conformità**.  Come per la pagina della panoramica, in questa pagina è possibile visualizzare lo stato dei criteri e/o delle iniziative elencati.  Nella pagina Conformità dei criteri, si può anche assegnare un criterio o un'iniziativa (nella prossima attività assegneremo un criterio).

1. Dal riquadro di spostamento sinistro, selezionare **Correzione**.  Questa pagina fornisce un elenco di criteri che hanno risorse non conformi.  Selezionando un criterio nella pagina Correzione, è possibile attivare la creazione di un'attività per correggere il criterio.  

1. Dal riquadro di spostamento a sinistra, sotto Creazione, selezionare **Assegnazioni**.  In questa pagina, si possono vedere le attuali assegnazioni di criteri e/o iniziative ed è possibile creare assegnazioni di criteri o iniziative.  Ritorneremo in questa pagina nella prossima attività.  

1. Dal riquadro di spostamento sinistro, selezionare **Definizioni**.  In questa pagina, selezionare **Controlla i computer con impostazioni di sicurezza delle password non sicure**.  Questa è la definizione di un'iniziativa che include molti criteri.  Per vedere come si presenta la definizione di un criterio, selezionare **Controlla i computer Windows in cui la validità massima della password non è impostata su 70 giorni**.  Quando si apre la pagina, viene visualizzata la definizione effettiva del criterio in una struttura JSON (Java Script Object Notation).   Come si può vedere nel testo in rosso, la definizione del criterio contiene elementi che definiscono il nome visualizzato, la descrizione. i parametri, le regole del criterio e altro ancora. NON MODIFICARE NULLA.  

1. Uscire dalla pagina Definizione criteri, selezionando la **X** che si trova nell'angolo in alto a destra della pagina.

1. Uscire dalla pagina Definizione dell'iniziativa, selezionando la **X** che si trova nell'angolo in alto a destra della pagina.

1. Mantenere aperta questa scheda del browser (Criteri – Microsoft Azure) per la prossima attività.

#### Attività 2.  In questa attività verrà creata un'assegnazione di criteri base per richiedere un tag sui gruppi di risorse.

1. Nel browser, aprire la scheda Criteri – Microsoft Azure.

1. Dal riquadro di spostamento sinistro, sotto Creazione, selezionare **Assegnazioni**.

1. Dalla parte superiore della pagina selezionare **Assegna criterio**.

1. Si apre la procedura guidata di assegnazione dei criteri per guidare l'amministratore nel processo di assegnazione di un criterio.  Accanto al campo Definizione del criterio, selezionare le **ellissi**.  Viene fornito un elenco delle definizioni dei criteri disponibili.  

1. Nella barra di ricerca immettere **Tag**.

1. Dai risultati della ricerca, selezionare **Richiedi un tag su gruppo di risorse** (potrebbe essere necessario scorrere verso il basso), quindi premere **Seleziona**.  Nota: l'effetto di questo criterio è negare la creazione di qualunque gruppo di risorse che non soddisfa il requisito.  

1. Si noti il nome di assegnazione predefinito.  Mantenere il nome così com'è e dal fondo della pagina selezionare **Avanti**.

1. Nel campo Nome tag, immettere **Ambiente**, quindi selezionare **Avanti**.  

1. Nel messaggio di non conformità immettere **È richiesto un tag ambiente**, quindi selezionare **Avanti**. Nota: questo messaggio apparirà come motivo di non conformità per i gruppi di risorse che sono stati creati prima dell'assegnazione del criterio e non hanno un tag Ambiente.  La creazione di gruppi di risorse successiva alla creazione verrà negata in assenza di un tag ambiente.

1. Rivedere l'assegnazione dei criteri, quindi selezionare Crea.  Se non si vede immediatamente il criterio, selezionare **Aggiorna**. Nota: l'applicazione del criterio potrebbe richiedere fino a 30 minuti.

1. Uscire dalla pagina di assegnazione dei criteri selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Ora ci si trova nella home page dei servizi di Azure.  Tenere questa pagina aperta, servirà per l'attività successiva.

#### Attività 3.  In questa attività si vedrà l'effetto dell'assegnazione dei criteri di Azure, tramite la creazione in Azure di un gruppo di risorse privo di un tag, quindi il gruppo di risorse verrà aggiornato per includere un tag.  Nota: L'applicazione del criterio creato durante la precedente attività potrebbe richiedere fino a 30 minuti, ma in genere l'applicazione avviene più rapidamente.

1. Nel browser, aprire la scheda Home – Microsoft Azure.

1. In alto sulla pagina, sotto la dicitura Servizi di Azure, selezionare **Gruppi di risorse**.

1. Dall'angolo superiore sinistro della pagina, selezionare **+ Crea**.

1. Dalla scheda Generale di Crea un gruppo di risorse, lasciare il campo Sottoscrizione così come è, Azure Pass - Sponsorizzazione.

1. Nel campo Gruppo di risorse immettere **SC900-Labs**.

1. Lasciare l'impostazione Area geografica sul valore predefinito, quindi selezionare **Avanti: Tag**.

1. Lasciare vuoto il campo Nome e Valore del tag.  NON POPOLARE, quindi selezionare **Verifica + Crea**.

1. Si vedrà un'indicazione di convalida riuscita (il nome e il valore del tag non sono campi obbligatori nella procedura guidata), quindi selezionare **Crea**.

1. Comparirà un messaggio di errore nella parte superiore dello schermo, "Non è stato possibile creare il gruppo di risorse. Visualizza i dettagli dell'errore".  Selezionare **Visualizza dettagli errore**. La condizione che fa parte dei criteri di Azure non è stata soddisfatta, quindi la creazione del gruppo di risorse è stata bloccata per non conformità. Nota: se non viene visualizzato il messaggio di errore e il gruppo di risorse viene creato, significa che l'applicazione del criterio non è ancora avvenuta.  Accedere alla pagina dei criteri per il criterio creato nell'attività precedente e una volta che il criterio ha effetto si vedrà che la risorsa non è conforme.  La pagina dei dettagli includerà il messaggio di non conformità.

1. Il riepilogo dell'errore mostra il seguente tipo di errore, “La risorsa ‘SC900-Labs' non è consentita dai criteri.  Chiudere questa finestra selezionando la **X** nell'angolo in alto a sinistra dello schermo.

1. Dalla finestra Crea un gruppo di risorse selezionare **<Precedente**.

1. Si ritorna alla pagina Tag per la creazione di un gruppo di risorse.  Nel campo Nome immettere Ambiente e nel campo Valore immettere **SC900-Labs**, quindi selezionare **Avanti: Verifica + Crea >**.

1. Verificare il tag e selezionare **Crea**.

1. Si vedrà elencato il gruppo di risorse.  Poiché il tag è stato fornito nel gruppo di risorse, la condizione inclusa come parte del criterio di Azure è stata soddisfatta.  Il gruppo di risorse è conforme al criterio.

1. Prima di uscire, rimuovere il criterio di Azure.
    1. Nell'angolo in alto a sinistra sulla pagina, selezionare Home per ritornare alla home page di Azure.
    
    1. Sotto la dicitura Servizi di Azure, selezionare Criteri di Azure.
    1. Nel mezzo della pagina, verranno visualizzate le assegnazioni di criteri/iniziative di Azure.  Selezionare i puntini di sospensione per l'assegnazione del criterio Richiedi un tag sui gruppi di risorse, quindi selezionare Elimina assegnazione.
    1. Verrà richiesto di confermare che si desidera eliminare l'assegnazione.  Selezionare Sì.


#### Verifica

In questo lab, lo studente ha esplorato la pagina di destinazione Criteri di Azure. Dopo aver esplorato la pagina Criteri di Azure, lo studente ha eseguito la procedura per creare un criterio e ha potuto vedere gli effetti del criterio creato.