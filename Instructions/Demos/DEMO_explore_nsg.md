---
Demo:
    title: 'Gruppi di sicurezza di rete (NSG) di Azure'
    module: 'Modulo 3. Lezione 1. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione delle funzionalità di sicurezza di base in Azure'
---

# Demo: Gruppi di sicurezza di rete (NSG) di Azure

### Scenario demo
Questa demo illustrerà le funzionalità di un gruppo di sicurezza di rete (NSG) in Azure.  Per farlo, verrà innanzitutto creata una macchina virtuale (VM) senza alcun NSG come parte della configurazione pre-demo. Verrà anche creato un NSG senza alcuna interfaccia o subnet associata.  Come parte della demo, verranno anche mostrare le regole in ingresso e in uscita predefinite per il NSG. Si esaminerà quindi il processo di assegnazione dell'interfaccia della VM al NSG.  Al termine della configurazione, si testerà la connessione alla VM usando le regole del NSG predefinite e anche le regole create.
  

#### Configurazione pre-demo parte 1
 Si raccomanda agli istruttori di farlo **PRIMA** della lezione poiché la creazione di una VM può richiedere diversi minuti. In questa configurazione verrà creata una macchina virtuale di Windows 10.

1. Aprire la scheda **Home – Microsoft Azure** nel browser.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **Macchine virtuali** quindi selezionare **Macchine virtuali** dai risultati della ricerca.  

1. Dalla parte superiore sinistra della pagina selezionare **+Aggiungi**, quindi selezionare **+Macchina virtuale**.

1. Dalla scheda generale, compilare le seguenti informazioni (per eventuali voci non elencate, lasciare le impostazioni predefinite):
    1. **Sottoscrizione**: verificare che l'impostazione predefinita sia Azure Pass – Sponsorizzazione.
    1. **Gruppo di risorse**: selezionare **Crea nuovo** quindi nel campo Nome inserire **LabsSC900-RG**, poi selezionare **OK**.
    1. **Nome delle macchine virtuali**:  immettere **SC900-WinVM**.
    1. **Area**:  lasciare l'impostazione predefinita.
    1. **Opzioni di disponibilità**: assicurarsi di selezionare **La ridondanza dell'infrastruttura non è richiesta**.  NOTA: è molto importante che le opzioni di disponibilità siano impostate su La ridondanza dell'infrastruttura non è richiesta, altrimenti la demo non funzionerà come previsto.  Avere un'opzione di disponibilità richiede un NSG e viene intenzionalmente creata la VM senza un NSG.
    1. **Immagine**:  dal menu a discesa, selezionare **Windows 10 Pro, Versione 20H2 – Gen 1**.
    1. **Dimensione**:  selezionare **vedi tutte le dimensioni** dal menu a discesa e selezionare **B2s**, quindi premere **Seleziona** sulla parte inferiore della pagina.
    1. **Nome utente**:  immettere **AzureUser**.
    1. **Password**:  immettere **SC900AzureLabs**.
    1. **Porte in ingresso pubbliche**:  si può lasciare l'impostazione predefinita (non importa cosa si seleziona qui perché le impostazioni di rete sovrascriveranno ciò che si fa qui).
    1. **Licenze**:  selezionare **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights** (Confermo di avere una licenza idonea di Windows 10 con diritti di hosting multi-tenant), in modo che nella casella compaia un segno di spunta.
    1. Selezionare **Avanti: Dischi**.

1. Ora ci si trova nella scheda Dischi per la configurazione della macchina virtuale  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Rete >**.

1. Ora ci si trova nella scheda Rete per la configurazione della macchina virtuale.  Inserire le seguenti informazioni (per eventuali voci non elencate, lasciare le impostazioni predefinite):
    1. Gruppo di sicurezza di rete della scheda di interfaccia di rete:  selezionare **Nessuno**.  Nota: selezionando Nessuno si assicura che la scheda di interfaccia di rete non abbia un NSG.  In un passaggio successivo della demo si creerà un NSG e si assegnerà una scheda di interfaccia di rete della VM al NSG creato.
    1. Poiché altre impostazioni della VM verranno mantenuto al valore predefinito, andare avanti e selezionare Avanti: **Verifica + Crea >**.

1. Rivedere la configurazione della macchina virtuale.  Alcuni punti da notare: Questa VM ha un indirizzo IP pubblico e nessun gruppo di sicurezza di rete della scheda di interfaccia di rete.  Dal punto di vista della sicurezza, in questo modo la macchina virtuale è esposta.  Questo problema verrà affrontato in un'attività successiva. Selezionare **Crea**.  Il completamento della distribuzione della macchina virtuale può richiedere diversi minuti.

1. Notare il nome dell'interfaccia di rete, **sc900-winvmXXX** (XXX sarà specifico dell'interfaccia di rete della macchina virtuale).

1. Una volta completata la distribuzione della VM, selezionare **Vai alla risorsa**.  Ora ci si trova nella pagina SC900-WinVM.  Notare l'indirizzo IP pubblico.

1. Dal riquadro di spostamento sinistro, selezionare **Rete** e notare l'interfaccia di rete **sc900-winvmXXX** (XXX sarà specifico dell'interfaccia di rete della propria macchina virtuale).  Non devono esserci regole in ingresso o in uscita associate all'interfaccia.  

1. Dalla parte superiore della pagina, selezionare **Connetti** poiché è importante verificare di potersi connettere alla VM.
    1. Dalla parte superiore della pagina, assicurarsi che sia selezionato **RDP** (sottolineato).
    1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
    1. **Aprire** il file scaricato e nella finestra che compare selezionare **Connetti**.
    1. Si apre una finestra di richiesta di inserimento delle credenziali. Se la finestra predefinita chiede di inserire un PIN, selezionare **Altre opzioni**, quindi selezionare **Usa un altro account**.   Verrà chiesto di inserire le credenziali.  Per il nome utente immettere **AzureUser**.  Per la password immettere **SC900AzureLabs**.
    1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified.  Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?)  Selezionare **Sì**.
    1. Ora si è connessi alla macchina virtuale di Windows appena creata. Completare la configurazione di Windows. Sebbene sia stata eseguita la connessione alla VM tramite RDP e una porta RDP comunemente usata, questa VM ha tutte le porte aperte e non c'è nulla che filtri il traffico.  Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP.  Una finestra pop-up indicherà "La sessione remota verrà disconnessa". Selezionare **OK**.

1. Ora si torna alla pagina SC900-WinVM del portale di Azure.  Lasciare aperta questa scheda del browser per l'attività successiva.

#### Configurazione pre-demo parte 2
Creare un gruppo di sicurezza di rete ma NON assegnare l'interfaccia di rete della VM a quel NSG.  

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppo di sicurezza di rete** quindi selezionare **Gruppi di sicurezza di rete** dai risultati della ricerca.  Non selezionare Gruppi di sicurezza di rete in versione classica.

1. Dalla parte superiore della pagina Gruppi di sicurezza di rete, selezionare **+ Crea**.

1. Nella scheda Generale della pagina Crea gruppo di sicurezza di rete specificare le impostazioni seguenti:
    1. Sottoscrizione:  Azure Pass – Sponsorizzazione
    1. Gruppo di risorse:  **LabsSC900-RG**
    1. Nome:  **NSG-SC900**
    1. Area:  lasciare l'impostazione predefinita **(Stati Uniti) Stati Uniti orientali**
    1. Selezionare **Verifica + Crea**, quindi **Crea**.

1. Al termine della distribuzione, selezionare **Vai alla risorsa** e assicurarsi che tutte le impostazioni siano corrette.  Dovrebbero esserci 3 regole in ingresso predefinite, 3 regole in uscita predefinite e nessuna subnet e nessuna interfaccia associate al NSG.  Tornare alla pagina **Home** del portale di Azure.  

#### Demo
Esaminare le impostazioni per un NSG.  In questo caso si esaminerà un NSG (quello creato nella configurazione precedente) che non è ancora stato assegnato a un'interfaccia della VM. Verrà quindi illustrato il processo di associazione di un'interfaccia al NSG e il processo di creazione di regole in ingresso e in uscita.

1. Aprire la scheda del browser, **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **gruppo di sicurezza di rete** quindi selezionare **Gruppi di sicurezza di rete** dai risultati della ricerca.  Non selezionare Gruppi di sicurezza di rete in versione classica.

1. Dalla pagina del NSG, selezionare il NSG creato nella configurazione, **NSG-SC900**.

1. La scheda **Panoramica** nel riquadro di spostamento sinistro è evidenziata.  Notare le regole in ingresso e in uscita predefinite nel NSG. Sebbene sia stato creato il NSG e ci siano regole predefinite per filtrare il traffico, nessuna interfaccia è stata associata al NSG. Si può vedere nella parte in alto a destra della pagina dove dice "Associato a: 0 subnet, 0 interfacce di rete".  Affinché un NSG funzioni correttamente, deve essere assegnato a qualcosa.  In questo caso verrà assegnato all'interfaccia di rete per la VM creata precedentemente.

1. Dal riquadro di spostamento a sinistra nella pagina NSG-SC900, selezionare **Interfacce di rete** sotto Impostazioni.

1. Selezionare **+ Associa**, sopra la casella di ricerca, poi dal menu a discesa selezionare **sc900-winvmXXX** (XXX sarà specifico per l'interfaccia di rete della VM) poi selezionare **Ok**. Mentre l'interfaccia viene associata si vedrà una casella di notifica nell'angolo in alto a destra dello schermo. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.

1. Tornare alla scheda **Panoramica**.  Notare che nella parte in alto a destra della pagina comparirà "Associato a: 0 subnet, 1 interfacce di rete"; l'interfaccia è ora assegnata al NSG. Inoltre, illustrare agli studenti le regole predefinite. In ingresso, saranno consentiti solo il traffico da altre reti virtuali Azure e Azure Load Balancer. Tutto il restante traffico in ingresso alla VM verrà negato. Richiamare inoltre le regole in uscita predefinite.  È consentito solo il traffico in uscita verso altre reti virtuali e il traffico Internet in uscita.  Come parte della demo, si raccomanda di mostrare che il traffico in uscita viene negato.
    1. Nella barra di ricerca nella parte superiore della pagina, inserire e selezionare **Macchine virtuali**.
    1. Dalla pagina Macchine virtuali, selezionare **SC900-WinVM**.
    1. Dalla parte superiore della pagina SC900-WinVM, selezionare **Connetti**, quindi selezionare **RDP**.
    1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
    1. **Aprire** il file scaricato e selezionare **Connetti**.
    1. Dopo alcuni secondi di tentativo di connessione, comparirà il messaggio di errore, il quale indica che il desktop remoto non può connettersi al computer remoto. Selezionare **OK**.

1. Ora che è stato illustrato l'impatto delle regole in ingresso predefinite di NSG, si vuole creare una nuova regola per permettere il traffico RDP in ingresso.  Ricordare che non è possibile eliminare le regole predefinite esistenti, si possono solo creare altre regole con una priorità superiore.
    1. Dal riquadro di spostamento sinistro, in Impostazioni selezionare **Rete**.  Si è ora nella pagina di rete della VM e sebbene da qui sia possibile creare una regola in ingresso e una regola in uscita, tornare alla pagina NSG, che è l'argomento della demo.  **Selezionare NSG-SC900**, è il collegamento al centro della finestra.

1. Si è ora nella pagina panoramica del NSG  Notare le informazioni sul NSG. Dal riquadro di spostamento sinistro della pagina del NSG, sotto le impostazioni, selezionare **Regole di sicurezza in ingresso**, quindi selezionare **+ Aggiungi** dalla parte superiore della pagina. Nella pagina Aggiungi regola di sicurezza in ingresso, illustrare le varie impostazioni. Si raccomanda di creare effettivamente la regola per consentire il traffico RDP in ingresso, con le seguenti impostazioni:
    1. Origine: **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **Qualsiasi**
    1. Servizio: **RDP**
    1. Azione: **Consenti**
    1. Priorità: **300**; Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime. Pertanto la priorità per questa nuova regola deve essere più alta della priorità della regola esistente che nega tutto il traffico in ingresso.
    1. Nome: **AllowRDP**
    1. Selezionare **Aggiungi**
    1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in ingresso.

1. Ora esaminare le **Regole di sicurezza in uscita**.  Selezionare **+ Aggiungi** dalla parte superiore della pagina e illustrare le varie impostazioni.  Si raccomanda di creare la regola. Le impostazioni seguenti creano una regola per negare il traffico Internet in uscita:
    1. Origine: **Qualsiasi**
    1. Intervalli di porte di origine: **\***
    1. Destinazione: **Tag del servizio**
    1. Tag del servizio di destinazione: **Internet**
    1. Servizio: **Personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione: **\*** (assicurarsi di inserire un asterisco nel campo degli intervalli di porte di destinazione).
    1. Protocollo: **Qualsiasi**
    1. Azione: **Nega**
    1. Priorità: **4000** (il punto da sottolineare è che la priorità deve essere superiore a quella della regola esistente che permette il traffico Internet in uscita)
    1. Nome: **DenyInternet**
    1. Selezionare **Aggiungi**
    1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.

1. Tornare ora alla VM e testare le regole.  Nella parte superiore della pagina, selezionare **SC900-VM**, sopra alle regole di sicurezza in uscita.

1. Testare la regola in ingresso verificando che è possibile connettersi alla VM tramite RDP.
    1. Selezionare **Connetti** nel riquadro di spostamento a sinistra.
    1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
    1. **Aprire** il file scaricato e selezionare **Connetti**.
    1. Verrà chiesto di inserire le credenziali. Per il nome utente immettere **AzureUser**. Per la password immettere **SC900AzureLabs**.  Se la finestra di richiesta di inserimento delle credenziali richiede un PIN, selezionare **Altre opzioni**, quindi selezionare **Usa un altro account**.
    1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified. Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?) Selezionare **Sì**.
    1. Si è ora connessi alla VM. Sottolineare allo studente che in questo caso era possibile connettersi alla VM perché la regola del traffico in ingresso creata consentiva il traffico in ingresso alla VM tramite RDP.

1. Ora testare la regola del NSG in uscita
    1. Aprire il browser Edge nella VM.
    1. Digitare **https://www.bing.com**. La pagina non dovrebbe essere visualizzata. Nota: se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare efficace. Attendere alcuni minuti e riprovare.

1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP. Una finestra pop-up indicherà "La sessione remota verrà disconnessa". Selezionare **Ok**.

1. Tornare alla Home page del portale Azure selezionando **Microsoft Azure** sulla barra blu sulla parte superiore della pagina.

#### Eliminazione
**IMPORTANTE**: In questa attività si eliminerà il gruppo di risorse e tutte le risorse in esso contenute.   Questo è importante per evitare altri addebiti.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dall'angolo superiore sinistro della pagina, selezionare **Tutti i servizi**.

1. Nella casella Filtra servizi accanto alla dicitura Tutti i servizi, immettere **Gruppi di risorse**, quindi dai risultati selezionare **Gruppi di risorse**.

1. Selezionare **LabsSC900-RG**.

1. Dalla parte centrale superiore della pagina LabsSC900-RG, selezionare **Elimina gruppo di risorse**.

1. Nella finestra che si apre, inserire il nome del gruppo di risorse, **LabsSC900-RG**, per confermare l'eliminazione del gruppo di risorse e di tutte le sue risorse, quindi selezionare **Elimina** dal fondo della pagina.

1. L'eliminazione di tutte le risorse e del gruppo di risorse può richiedere alcuni minuti.

#### Verifica

Questa demo ha illustrato le informazioni e le impostazioni associate a un NSG, incluso il processo di associazione di un'interfaccia al NSG, ha illustrato e regole in ingresso e in uscita predefinite e infine i passaggi per creare una nuova regola.
