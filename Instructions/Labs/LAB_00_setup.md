---
lab:
    title: 'Configurazione'
---

# Lab: Configurazione

### Scenario del lab

In questo lab, si riscatterà l'Azure Pass utilizzando le stesse credenziali del tenant Microsoft 365.  Questo garantirà la continuità nel passaggio tra Microsoft 365 e Azure. Come parte della configurazione, verrà inoltre abilitata la funzionalità del log di controllo nel tenant Microsoft 365, poiché la sua applicazione potrebbe richiedere del tempo. Microsoft 365 utilizza log di controllo per informazioni dettagliate e attività degli utenti identificate nei criteri e nelle informazioni dettagliate di analisi.

**Tempo stimato**: 5-10 minuti

#### Parte 1 della configurazione - Riscatto dell'Azure Pass
In questa attività di configurazione, si riscatterà l'Azure Pass utilizzando le stesse credenziali del tenant Microsoft 365.  Questo garantirà una maggiore continuità nel passaggio tra Microsoft 365 e Azure.

1. Se sono presenti finestre del browser aperte, si consiglia di chiudere tutti i browser.

1. Fare clic con il tasto destro del mouse sull'icona di Microsoft Edge e selezionare **Nuova finestra InPrivate** per aprire una nuova sessione privata del browser. Altro 

1. Nella barra degli indirizzi immettere **www.microsoftazurepass.com**.  

1. Selezionare il pulsante **Accedi** per iniziare.

    1. Nella finestra di accesso, immettere l'indirizzo e-mail **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**. Se si visualizza la domanda se rimanere connessi, selezionare **Sì**.
    1. Se viene elencato l'indirizzo e-mail corretto, selezionare **Conferma account Microsoft**.
    1. Immettere il codice promo nella relativa casella e fare clic su **Claim Promo Code** (Codice promo di attestazione).  
    1. Nella pagina del proprio profilo, lasciare tutte le informazioni predefinite, selezionare **Accetto il contratto di sottoscrizione, i dettagli dell'offerta e l'informativa sulla privacy**, quindi **Iscrizione**.
    1. Se si apre una finestra di sondaggio, scegliere di chiuderla selezionando **X** o rispondere nel modo appropriato, quindi selezionare **Invia**.

1. Per l'attivazione dell'account potrebbero essere necessari alcuni minuti.  Una volta attivato, si viene reindirizzati alla home page del portale di Azure. Si apre una finestra di benvenuto di Microsoft Azure; selezionare **Forse in seguito**. È possibile che venga visualizzata una finestra popup "Optimize your cloud workloads with personalized recommendations" (Ottimizzare i carichi di lavoro del cloud con consigli personalizzati); selezionare **X** nell'angolo in alto a destra della finestra.

1. Lasciare aperta la scheda del browser per la home page del portale di Azure, poiché verrà utilizzata nella prossima demo. 

#### Parte 2 della configurazione - Abilitazione del log di controllo di Microsoft 365
In questa attività di configurazione, si abiliterà la funzionalità Log di controllo in Microsoft 365.  Sebbene la documentazione indichi che il log di controllo è attivato per impostazione predefinita, questa funzionalità non è abilitata per la maggior parte dei tenant dei lab e la sua attivazione potrebbe richiedere parecchie ore.  È vantaggioso abilitare questa funzionalità, poiché Microsoft 365 utilizza i log di controllo per informazioni dettagliate e attività degli utenti identificate nei criteri e nelle informazioni dettagliate di analisi.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del Centro conformità Microsoft 365.  

1. Dal riquadro di spostamento sinistro, sotto Soluzioni, selezionare **Controllo**.  Nota: la funzionalità di controllo è accessibile dalla home page di Microsoft 365 Defender (in precedenza chiamato Centro sicurezza Microsoft 365).

1. Verificare che la scheda **Cerca** sia selezionata (sottolineata).

1. Una volta arrivati nella pagina Controllo, attendere 2-3 minuti.  Se il controllo non è abilitato, verrà visualizzata una barra blu in cima alla pagina per avviare la registrazione delle attività di utenti e amministratori.  Selezionare **Avvia la registrazione delle attività di utenti e amministratori**.  Una volta abilitato il controllo, la barra blu scompare.  Se la barra blu non è presente, il controllo è già abilitato e non sono richieste ulteriori azioni.  È possibile verificare se il controllo sia attivato anche tramite PowerShell, ma questo non rientra nell'ambito di questo corso.

1. Tornare alla home page del Centro conformità Microsoft 365 selezionando **Home** dal riquadro di spostamento a sinistra.

#### Verifica

In questa di configurazione, è stato riscattato l'Azure Pass utilizzando le stesse credenziali del tenant Microsoft 365.  Inoltre, è stata abilitata la funzionalità Log di controllo in Microsoft 365.