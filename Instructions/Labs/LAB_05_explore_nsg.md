---
lab:
    title: 'Esplorazione dei Gruppi di sicurezza di rete (NSG) di Azure'
    module: 'Modulo 3. Lezione 1. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione delle funzionalità di sicurezza di base in Azure'
---


# Lab: Esplorazione dei Gruppi di sicurezza di rete (NSG) di Azure.

## Scenario del lab
In questo lab, si esplorerà la funzione dei Gruppi di sicurezza di rete in Azure.  Questo avverrà attraverso la creazione della macchina virtuale (VM) senza alcun gruppo di sicurezza di rete.  Senza alcuna NSG a filtrare il traffico, tutte le porte della VM sono esposte a Internet pubblico.  Si seguirà quindi il processo di creazione di un NSG e di assegnazione dell'interfaccia della VM a quel NSG.  Al termine della configurazione, si testerà la connessione alla VM usando le regole del NSG predefinite e anche le regole create.
  

**Tempo stimato**: 15-20 minuti

#### Attività 1.  In questa attività verrà creata una macchina virtuale di Windows 10.    
1.	Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **portal.azure.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.

    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.
1. Nell'angolo in alto a sinistra della schermata, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi selezionare **Tutti i servizi**.  
1. Nella finestra principale, sotto In primo piano, selezionare Macchine virtuali.  Se non vi sono macchine virtuali elencate, immetterla nella barra di ricerca, quindi selezionarla dai risultati della ricerca. 
1. Nella parte superiore sinistra della pagina, selezionare **+Crea**, quindi **+Macchina virtuale**.
1. Dalla scheda generale, compilare le seguenti informazioni (per eventuali voci non elencate, lasciare le impostazioni predefinite):
    1. Sottoscrizione: verificare che l'impostazione predefinita sia Azure Pass – Sponsorizzazione.

    1. Gruppo di risorse:  Selezionare **Crea nuovo**, immettere **LabsSC900** nel campo Nome, quindi premere **OK**.
    1. Nome delle macchine virtuali:  immettere **SC900-WinVM**.
    1. Immagine:  dal menu a discesa, selezionare **Windows 10 Pro, Versione 20H2 – Gen 1**.
    1. Dimensione:  selezionare **vedi tutte le dimensioni** dal menu a discesa e selezionare **B2s**, quindi premere **Seleziona** sulla parte inferiore della pagina.
    1. Nome utente:  immettere **AzureUser**.
    1. Password:  immettere **SC900AzureLabs**.
    1. Porte in ingresso pubbliche:  selezionare **Nessuna**.
    1. Licenze:  selezionare **I confirm I have an eligible Windows 10 license with multi-tenant hosting rights** (Confermo di avere una licenza idonea di Windows 10 con diritti di hosting multi-tenant), in modo da visualizzare un segno di spunta nella casella.
    1. Selezionare **Avanti: Dischi**. 
1. Ora ci si trova nella scheda Dischi per la configurazione della macchina virtuale  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Rete >**.
1. Ora ci si trova nella scheda Rete per la configurazione della macchina virtuale.  Inserire le seguenti informazioni (per eventuali voci non elencate, lasciare le impostazioni predefinite):
    1. Gruppo di sicurezza di rete della scheda di interfaccia di rete:  selezionare **Nessuno**.

    1. Selezionare **Avanti:  Gestione >**.
1. Ora ci si trova nella scheda Gestione per la configurazione della macchina virtuale.  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Avanzate >**.
1. Ora ci si trova nella scheda Avanzate per la configurazione della macchina virtuale.  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Tag >**.
1. Ora ci si trova nella scheda Tag per la configurazione della macchina virtuale.  Lasciare tutte le impostazioni sul valore predefinito, quindi selezionare **Avanti: Verifica + crea >**.
1. Rivedere la configurazione della macchina virtuale.  Alcuni punti da notare: Questa VM ha un indirizzo IP pubblico e nessun gruppo di sicurezza di rete della scheda di interfaccia di rete.  Dal punto di vista della sicurezza, in questo modo la macchina virtuale è esposta.  Questo problema verrà affrontato in un'attività successiva. Selezionare Crea.  Il completamento della distribuzione della macchina virtuale può richiedere diversi minuti.
1. Notare il nome dell'interfaccia di rete, **sc900-winvmXXX** (XXX sarà specifico dell'interfaccia di rete della macchina virtuale).
1. Una volta completata la distribuzione della VM, selezionare **Vai alla risorsa**.
1. Ora ci si trova nella pagina SC900-WinVM.  Notare l'indirizzo IP pubblico. 
1. Dalla parte superiore della pagina selezionare **Connetti**, quindi selezionare **RDP** dall'elenco a discesa.
1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**. 
1. Aprire il file scaricato e selezionare **Connetti**. 
1. Verrà chiesto di inserire le credenziali.  Per il nome utente immettere **AzureUser**.  Per la password immettere **SC900AzureLabs**. 
1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified.  Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?)  Selezionare **Sì**.
1. Ora si è connessi alla macchina virtuale di Windows appena creata. Seguire le richieste per completate la configurazione della macchina virtuale. Sebbene sia stata eseguita la connessione alla VM tramite RDP e una porta RDP comunemente usata, questa VM ha tutte le porte aperte e non c'è nulla che filtri il traffico. 
1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP.  Una finestra pop-up indicherà "La sessione remota verrà disconnessa". Selezionare **OK**.
1. Ora si torna alla pagina SC900-WinVM del portale di Azure.  Lasciare aperta questa scheda del browser per l'attività successiva.

#### Attività 2.  Creare un gruppo di sicurezza di rete e assegnare l'interfaccia di rete della VM a quel gruppo di sicurezza di rete.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dall'angolo in alto a sinistra della pagina, accanto alla dicitura Microsoft Azure, selezionare l'icona Mostra menu Portale (le tre linee orizzontali, chiamata anche icona hamburger), quindi selezionare **Tutti i servizi**.
1. Nella casella Filtra servizi accanto alla dicitura Tutti i servizi, immettere **Gruppi di sicurezza di rete**, quindi selezionare **Gruppi di sicurezza di rete** dai risultati (non selezionare Gruppi di sicurezza di rete (versione classica)).
1. Dalla parte superiore della pagina Gruppi di sicurezza di rete, selezionare **+ Crea**.
1. Nella scheda Generale della pagina Crea gruppo di sicurezza di rete specificare le impostazioni seguenti:
    1. Sottoscrizione:  Azure Pass – Sponsorizzazione

    1. Gruppo di risorse:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Area:  lasciare l'impostazione predefinita **(Stati Uniti) Stati Uniti orientali**
    1. Selezionare **Verifica + Crea**, quindi **Crea**.
1. Una volta completata la distribuzione, selezionare **Vai alla risorsa**.
1. Notare le regole in ingresso e in uscita predefinite nel NSG.  Sebbene il gruppo di sicurezza di rete sia stato creato e siano presenti regole predefinite per filtrare il traffico, al gruppo non è stata associata alcuna interfaccia, quindi la VM è ancora vulnerabile, con le porte esposte a Internet pubblico.
1. Dal riquadro di spostamento a sinistra nella pagina NSG-SC900, selezionare **Interfacce di rete** sotto Impostazioni.
1. Selezionare l'opzione **+ Associa** sopra la casella di ricerca.
1. Dalla pagina Associa interfaccia di rete, selezionare **sc900-winvmXXX** (XXX sarà specifico dell'interfaccia di rete della propria VM).  Mentre l'interfaccia viene associata si vedrà una casella di notifica nell'angolo in alto a destra dello schermo.
1. Una volta effettuata l'associazione dell'interfaccia al NSG, questa verrà visualizzata nell'elenco.
1. Con l'interfaccia della VM associata al gruppo di sicurezza di rete e le regole NSG predefinite, qualsiasi tentativo di connessione alla VM non riuscirà.  
1. Dall'angolo superiore sinistro della pagina, selezionare **Tutti i servizi**, quindi **Macchine virtuali** sotto la dicitura In primo piano.
1. Dalla pagina Macchine virtuali, selezionare **SC900-WinVM**.
1. Dalla parte superiore della pagina **SC900-WinVM**, selezionare **Connetti**, quindi **RDP**.
1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
1. Aprire il file scaricato e selezionare **Connetti**.
1. Dopo alcuni secondi di tentativo di connessione, comparirà il messaggio di errore, il quale indica che il desktop remoto non può connettersi al computer remoto.  Selezionare **OK**.

#### Attività 3. In questa attività si creerà una regola NSG per consentire il traffico in ingresso usando RDP sulla porta 3389.  La regola verrà quindi testata mediante tentativo di connessione alla VM mediante RDP. 

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dal riquadro di spostamento sinistro, in Impostazioni selezionare **Rete**.
1. Con la scheda Regole porta in ingresso selezionata, saranno visibili le regole in ingresso predefinite.  Non è possibile rimuovere le regole predefinite, ma è possibile sostituirle creando regole con priorità più alte. Dal lato destro della pagina, selezionare **Aggiungi regola porta in ingresso**.
1. Nella pagina Aggiungi regola porta in ingresso, specificare le seguenti impostazioni:
    1. Origine:  **Qualsiasi**

    1. Intervalli di porte di origine: *
    1. Destinazione:  **Qualsiasi**
    1. Servizio:  **RDP**
    1. Azione:  **Consenti**
    1. Priorità:  **300**; Nota: le regole con i numeri più bassi hanno una priorità più alta e vengono elaborate per prime.
    1. Nome:  **AllowRDP**
1. Selezionare **Aggiungi**
1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in ingresso.
1. Verificare ora se sia possibile connettersi alla VM tramite RDP.  Selezionare **Connetti** nel riquadro di spostamento a sinistra.
1. Verificare che l'indirizzo IP sia impostato su Indirizzo IP pubblico, lasciare il numero di porta predefinito e selezionare **Scarica file DRP**.
1. Aprire il file scaricato e selezionare **Connetti**.
1. Verrà chiesto di inserire le credenziali.  Per il nome utente immettere **AzureUser**.  Per la password immettere **SC900AzureLabs**.
1. Si apre una finestra di connessione al Desktop remoto con l'avviso "The identity of the remote computer cannot be verified.  Do you wish to connect anyway?" (Non è possibile verificare l'identità del computer remoto. Connettersi comunque?)  Selezionare **Sì**.
1. Ora la connessione alla VM è stata stabilita. In questo caso, è stato possibile connettersi alla VM perché la regola del traffico in ingresso creata consente il traffico in ingresso alla VM tramite RDP.
1. Tenere aperta la VM, poiché verrà usata nell'attività successiva.

#### Attività 4.  Le regola in uscita predefinite per il gruppo di sicurezza di rete consentono il traffico Internet in uscita, quindi si confermerà la possibilità di connettersi a Internet.  Quindi si seguirà il processo di creazione di una regola in uscita personalizzata per bloccare il traffico Internet in uscita e si testerà quella regola.

1. Dalla VM, selezionare **Edge** per aprire il browser.  
1. Immettere **https://www.bing.com** nella barra degli indirizzi del browser e confermare di riuscire a connettersi al motore di ricerca.
1. Chiudere il browser nella propria VM, ma lasciare la VM aperta poiché verrà usata nei passaggi successivi.
1. Tornare al portale di Azure, aprire la scheda SC900-WinVM – Microsoft Azure nel browser.
1. Dal riquadro di spostamento sinistro, in Impostazioni selezionare **Rete**.
1. Selezionare la scheda **Regole porta in uscita**.  Verranno visualizzate le regole in uscita predefinite.  Notare la regola predefinita "AllowInternetOutBound". Questa regola consente tutto il traffico Internet in uscita. Non è possibile rimuovere la regola predefinita, ma è possibile sostituirla creando una regola con priorità più alta. Dal lato destro della pagina, selezionare **Aggiungi regola porta in uscita**.
1. Nella pagina Aggiungi regola porta in uscita, specificare le seguenti impostazioni:
    1. Origine:  **Qualsiasi**

    1. Intervalli di porte di origine:  *
    1. Destinazione:  **Tag del servizio**
    1. Tag del servizio di destinazione:  **Internet**
    1. Servizio:  **Personalizzato** (lasciare l'impostazione predefinita)
    1. Intervalli di porte di destinazione:  * (assicurarsi di mettere un asterisco nel campo Intervalli di porte di destinazione)
    1. Protocollo: **Qualsiasi**
    1. Azione: **Nega**
    1. Priorità:  **4000**
    1. Nome:  **DenyInternet**
1. Selezionare **Aggiungi**
1. Una volta eseguito il provisioning della regola, questa verrà visualizzata nell'elenco delle regole in uscita.  Sebbene compaia nell'elenco, occorreranno alcuni minuti perché diventi efficace (attendere alcuni minuti mentre si procede ai passaggi successivi).  
1. Tornare alla propria VM.
1. Aprire il browser Edge nella propria VM e immettere **https://www.bing.com**.  La pagina non dovrebbe essere visualizzata.  Nota: se si riesce a connettersi a Internet e si è verificata la corretta impostazione di tutti i parametri della regola in uscita, è possibile che ciò avvenga perché la regola impiega alcuni minuti per diventare efficace.  Chiudere il browser, attendere alcuni minuti e riprovare.
1. Chiudere la connessione al desktop remoto selezionando la **X** in alto al centro della pagina dove viene mostrato l'indirizzo IP.  Una finestra pop-up indicherà "La sessione remota verrà disconnessa". Selezionare **OK**.
1. In questa attività si è configurata una regola in uscita nel gruppo di sicurezza di rete per bloccare il traffico Internet in uscita.

#### Attività 5.  IMPORTANTE: In questa attività si eliminerà il gruppo di risorse e tutte le risorse in esso contenute.   Questo è importante per evitare altri addebiti.

1. Aprire la scheda SC900-WinVM – Microsoft Azure nel browser.

1. Dall'angolo superiore sinistro della pagina, selezionare **Tutti i servizi**.
1. Nella casella Filtra servizi accanto alla dicitura Tutti i servizi, immettere **Gruppi di risorse**, quindi dai risultati selezionare **Gruppi di risorse**.
1. Selezionare **LabsSC900**.
1. Dalla parte superiore centrale della pagina LabsSC900, selezionare **Elimina gruppo di risorse**.
1. Nella finestra che si apre, immettere il nome del gruppo di risorse, **LabsSC900**, per confermare l'eliminazione del gruppo di risorse e di tutte le relative risorse, quindi selezionare **Elimina** in fondo alla pagina.
1. L'eliminazione di tutte le risorse e del gruppo di risorse può richiedere alcuni minuti.

#### Verifica

In questo lab, si è seguito il processo di impostazione di una VM con e senza un gruppo di sicurezza di rete (NSG) e si è esaminato l'impatto delle regole NSG predefinite.  Inoltre, si è seguito il processo di creazione delle regole NSG.
