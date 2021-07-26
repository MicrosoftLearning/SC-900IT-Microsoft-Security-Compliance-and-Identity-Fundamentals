---
lab:
    title: 'Esplorazione delle etichette di riservatezza in Microsoft 365'
    module: 'Modulo 4. Lezione 2. Descrizione delle funzionalità delle soluzioni di conformità Microsoft: descrizione delle funzionalità di protezione e governance delle informazioni in Microsoft 365'
---


# Lab: Esplorazione delle etichette di riservatezza in Microsoft 365

## Scenario del lab
In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichette di riservatezza esistenti che sono state create e il criterio corrispondente per pubblicare l'etichetta.   Quindi verrà illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.


**Tempo stimato**: 20-25 minuti

#### Attività 1. In questa attività si comprenderanno le funzioni delle etichette di riservatezza esaminando le impostazioni di un'etichetta di riservatezza esistente che è stata creata e il criterio corrispondente per pubblicare l'etichetta.

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

1. In Interfacce di amministrazione selezionare **Conformità**.  Si apre una nuova pagina del browser alla pagina di benvenuto del Centro conformità Microsoft 365.  

1. Dal riquadro di spostamento sinistro del Centro conformità Microsoft 365 e poi selezionare **Mostra tutto**.

1. Dal riquadro di spostamento sinistro, sotto Soluzioni, selezionare **Information Protection**.

1. Nel riquadro delle informazioni giallo viene indicato che l'organizzazione non ha abilitato la possibilità di elaborare il contenuto dei file online di Office che hanno etichette di riservatezza crittografate applicate e sono archiviati in OneDrive e SharePoint.  Selezionare Abilita ora.  Al termine, potrebbe esserci un ritardo nella propagazione delle impostazioni nel sistema.

1. Verificare che la scheda **Etichette** sulla parte superiore della pagina sia selezionata (sottolineata).

1. Al centro della pagina sono presenti tre etichette già create.  Selezionare **Riservato - Finanza**.  Si apre una finestra contenente informazioni su questa etichetta.  Questa etichetta è impostata per supportare sia la crittografia che il contrassegno dei contenuti.  Selezionare Modifica etichetta nella parte superiore della pagina per visualizzare alcune delle impostazioni di configurazione di base.

1. La configurazione inizia fornendo un nome e una descrizione per l'etichetta.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.

1. Osservare l'ambito di questa etichetta.  L'ambito è impostato su File ed e-mail a cui è possibile configurare le impostazioni di crittografia e contrassegno dei contenuti per proteggere le e-mail etichettate e i file di ufficio.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.

1. Per l'ambito selezionato, File ed e-mail, è possibile configurare la crittografia e/o il contrassegno dei contenuti.  Osservare come è impostata la protezione per file e messaggi e-mail sia per la crittografia sia per la marcatura dei contenuti dei file.  Esaminare la definizione di ciascuna.  Non modificare nulla.  Selezionare **Avanti** nella parte inferiore della pagina.

1. La finestra Crittografia mostra la configurazione per le impostazioni di crittografia.  Non modificare nulla.  Esaminare la casella delle informazioni sotto Configura impostazioni di crittografia ed esaminare le impostazioni configurate. Notare che la modalità con cui l'utente accede ai contenuti è impostata per non scadere mai.  È anche possibile assegnare autorizzazioni a specifici utenti e gruppi in modo che solo loro possano interagire con il contenuto a cui è applicata questa etichetta.  Sotto utenti e gruppi, il tenant è definito in modo che tutti gli utenti nel tenant possano vedere il contenuto a cui è applicata questa etichetta.  Nell'elenco è presente il team finanziario che ha autorizzazioni di Co-autore.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.

1. Nella pagina dei contrassegni dei contenuti, prendere nota del riquadro informativo nella parte superiore della pagina.  I contrassegni dei contenuti saranno applicati ai documenti, ma solo le intestazioni e i piè di pagina saranno applicati ai messaggi di posta elettronica. In altre parole, le filigrane non vengono applicate alle e-mail.  Il contrassegno dei contenuti associato a questa etichetta è una filigrana.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.

1. Ora ci si trova nell'etichettatura automatica per la finestra di file e messaggi e-mail.  Leggere la descrizione dell'etichettatura automatica sulla parte alta della pagina e la casella delle informazioni sotto.  Si noti anche che questa etichetta è impostata per l'etichettatura automatica per condizioni specifiche. Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.

1. La prossima finestra definisce le impostazioni di protezione per i team, i gruppi e i siti a cui è applicata questa etichetta. Questa funzionalità non è abilitata, selezionare **Avanti** nella parte inferiore della pagina. 

1. La prossima finestra è una funzionalità di anteprima per applicare automaticamente questa etichetta alle colonne del database Azure (come SQL, Synapse e altro) che contengono i tipi di informazioni sensibili scelti.  Questa funzionalità non è abilitata. Selezionare **Annulla** in fondo alla pagina per uscire dalla configurazione guidata dell'etichetta e tornare alla pagina Information Protection. 

1. Dalla parte superiore della pagina Information Protection, selezionare **Criteri delle etichette**.  È attraverso i criteri delle etichette che le etichette di riservatezza possono essere pubblicate.  

1. Selezionare **Criterio Riservato-Finanza**.  Si apre una finestra contenente informazioni sul criterio.  Questo criterio serve a pubblicare le etichette Criterio Riservato-Finanza e protegge i dati che contengono dati finanziari per Contoso.  Si ricorda inoltre che questo criterio viene pubblicato per tutti.  

1. Selezionare il criterio **Modifica** dalla parte superiore della finestra.

1. Leggere la descrizione sotto "Scegli le etichette di riservatezza da pubblicare".  Osservare l'etichetta inclusa nell'elenco.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.

1. Leggere la descrizione sotto "Pubblica per utenti e gruppi".  Notare che questa etichetta è disponibile per tutti gli utenti.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.

1. Rivedere le impostazioni dei criteri.  Non modificare alcuna impostazione.  Selezionare **Avanti** nella parte inferiore della pagina.

1. L'ultima opzione di configurazione è quella di dare un nome al criterio.  Non modificare alcuna impostazione.  Selezionare **Annulla** in fondo alla pagina per uscire dalla configurazione dei criteri e tornare alla pagina Information Protection.

1. Dalla pagina Information Protection, selezionare Aggiunta automatica dell'etichetta.  Notare che non è stato configurato nessun criterio di aggiunta automatica dell'etichetta.  Non modificare alcuna impostazione.  Si noterà che non presente alcun criterio, dato che la configurazione dell'etichetta è impostata sull'aggiunta automatica dell'etichetta per i file e le e-mail; tornare ai passaggi di definizione delle impostazioni di configurazione dell'etichetta e riesaminare la descrizione e le caselle informative associate all'aggiunta automatica dell'etichetta per i file e le e-mail.  Suggerimento:  nella scheda dell'etichettatura automatica per il lab sulla riservatezza, viene mostrato un messaggio simile al seguente:  "Per applicare automaticamente questa etichetta ai file già salvati (in SharePoint e OneDrive) o alle e-mail già elaborate da Exchange, è necessario creare un criterio di aggiunta automatica dell'etichetta".

1. Dal riquadro di spostamento sinistro, selezionare Home per tornare al Centro conformità Microsoft 365.

1. Tenere aperta la pagina poiché verrà usata nell'attività successiva.


#### Attività 2.  In questa attività, verrà affrontato il processo per applicare un'etichetta dal punto di vista dell'utente (in questo caso l'utente è l'amministratore) e visualizzare la marcatura dei contenuti generata dall'etichetta.

1. Dalla home page del Centro conformità Microsoft 365, selezionare l'**icona di avvio delle app**, accanto a Contoso Electronics. Fare **clic con il tasto destro sull'icona di Word** e selezionare **Apri in una nuova scheda**.  

1. Selezionare **+ Nuovo documento vuoto**, quindi immettere il testo nella pagina.  Sulla barra blu nella parte superiore della pagina, selezionare la freccia verso il basso, accanto a DocumentoXX - Salvato, e nella casella Nome file immettere **Etichetta di test**.

1. Dalla barra dei menu in alto selezionare **Riservatezza**. Dall'elenco a discesa, selezionare **Riservato - Finanza**. 

1. Dalla barra dei menu in alto, selezionare **Visualizzazione**, poi selezionare **Visualizzazione di lettura**.

1. Osservare in che modo il documento include la filigrana.  

1. Chiudere le schede di Microsoft Word aperte sul browser per uscire da Word.

#### Attività 3 (facoltativa): Oltre al contrassegno dei contenuti, l'impostazione della protezione dell'etichetta è stata impostata per la crittografia. Secondo i permessi che sono stati configurati con questa etichetta, i membri del gruppo finanziario possono ave autorizzazioni di co-autore per i documenti con questa etichetta applicata e gli utenti del tenant Contoso possono visualizzare (o qualsiasi documento/e-mail con l'etichetta applicata).  In questa attività si invierà il documento a un indirizzo e-mail a cui si può accedere (ovvero, un indirizzo e-mail personale) e che NON è parte del dominio WWLxZZZZ.OnMicrosoft.com e vedere cosa succede quando si tenta di aprire l'allegato.  

1. Dalla home page del Centro conformità Microsoft 365, selezionare l'**icona di avvio delle app**, accanto a Contoso Electronics. Fare **clic con il tasto destro sull'icona di Outlook** e selezionare **Apri in una nuova scheda**.

1. Selezionare **Nuovo messaggio** dall'angolo in alto a sinistra dello schermo.  Inserire un indirizzo e-mail a cui si ha accesso e che non fa parte del dominio WWLxZZZZ.OnMicrosoft.com e immettere **Test** nell'oggetto.

1. Selezionare **Allega**.

1. Selezionare **Cerca nei percorsi sul cloud**.

1. Dall'elenco che appare, selezionare il documento creato e al quale è stata applicata l'etichetta **Etichetta di test**. Selezionare **Avanti** e selezionare **Allega come copia**.  Premere **Invia**.

1. Controllare l'e-mail a cui è stato inviato il documento.  L'e-mail potrebbe essere finita nella cartella della posta indesiderata.  Quando si tenta di aprire il file Word allegato comparirà una notifica che informa l'utente che non ha il permesso di aprire il documento.

1. Chiudere le schede del browser aperte.


#### Verifica
In questo lab verranno esplorate le funzionalità delle etichette di riservatezza.  Verranno esaminate le impostazioni per le etichetta di riservatezza esistenti che sono già state create e il criterio corrispondente per pubblicare l'etichetta.   Quindi verrà illustrato come applicare un'etichetta e l'impatto della stessa dal punto di vista dell'utente.