---
lab:
    title: 'Esplorazione di Azure Active Directory'
    module: 'Modulo 2. Lezione 1. Descrizione delle funzionalità delle soluzioni Microsoft per la gestione delle identità e degli accessi: esplorare i servizi e i tipi di identità di Azure AD'
---

# Lab: Esplorazione di Azure Active Directory

## Scenario del lab

In questo lab si accederà ad Azure Active Directory.  Inoltre, si creerà un utente e si configureranno le varie impostazioni, compresa l'aggiunta di licenze.  



**Tempo stimato**: 10-15 minuti

#### Attività 1.  In qualità di abbonato di Microsoft 365, si usa già Azure AD.  Questa attività illustrerà i passaggi dettagliati per accedere ad Azure AD tramite il portale di amministrazione di Microsoft 365 e il portale di Azure.

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **admin.microsoft.com** per accedere all'interfaccia di amministrazione di Microsoft 365.

3. Accedere con le credenziali di amministratore. 
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

4. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Mostra tutto**.

5. In Interfacce di amministrazione selezionare **Azure Active Directory** (potrebbe essere necessario scorrere verso il basso).  Si apre una nuova pagina del browser con la pagina Dashboard dell'interfaccia di amministrazione di Azure Active Directory. Nelle finestre principali del dashboard saranno visibili vari riquadri, compresi il riquadro Identità dell'organizzazione (Contoso, il tenant e l'edizione di Azure AD), un riquadro per gli utenti e i gruppi e altro ancora.

6. Dal riquadro di spostamento a sinistra, in Preferiti, selezionare **Azure Active Directory**.  Nella finestra principale sarà visibile un altro riquadro di spostamento che elenca tutti i servizi disponibili in Azure AD. A destra verranno visualizzate informazioni sul tenant Contoso, collegamenti ai tipi di identità che è possibile creare e i servizi offerti.  

7. Aprire ora una nuova finestra del browser e, nella barra degli indirizzi, immettere **portal.azure.com**.  Poiché è stato già effettuato l'accesso come admin@WWLxZZZZZZ.onmicrosoft.com e queste stesse credenziali erano state utilizzate per riscattare l'Azure Pass, l'accesso al portale di Azure dovrebbe essere avvenuto come amministratore.  È possibile verificarlo controllando l'indirizzo e-mail nell'angolo in alto a destra della pagina e passando il mouse sopra l'icona dell'utente.

8. La pagina di destinazione del portale di Azure mostra i servizi di Azure, compresi Azure Active Directory, macchine virtuali, account di archiviazione, database e altro ancora.  Selezionare **Azure Active Directory**.  

9. Ora si visualizza Azure Active Directory per il tenant Contoso Microsoft 365.    Qualsiasi approccio si adotti per l'accesso ai servizi di Azure Active Directory (il portale di amministrazione Microsoft 365 o il portale Azure), la destinazione non cambia: Azure Active Directory di Contoso, in cui è possibile gestire tutti i servizi di Azure AD.

10. Lasciare aperta questa pagina del browser per la prossima attività.


#### Attività 2.  In questa attività, si apprenderà come creare un nuovo utente in Azure Active Directory e si esploreranno alcuni dei servizi che possono essere gestiti a livello di utente.

1. Passare alla scheda Contoso – Microsoft Azure aperta nel browser. Se la scheda era stata chiusa, aprire una pagina del browser e, nella barra degli indirizzi, inserire portal.azure.com e selezionare Azure Active Directory.  Occorre aver effettuato l'accesso come amministratore nel portale di Azure. In caso contrario, eseguire di nuovo l'accesso.

2. Dal riquadro di spostamento sinistro, selezionare **Utenti**.  Si ricorda che il tenant è già configurato con gli utenti.

3. Dalla parte superiore della pagina, selezionare **+ Nuovo utente**.

4. L'opzione **Crea utente** dovrebbe già essere selezionata. In caso contrario, selezionarla.

5. Compilare i campi **Identità** nel seguente modo:

    1. Nome utente: **sara**.

    2. Campo Nome: **Sara Perez**.

    3. Nome: **Sara**.

    4. Cognome: **Perez**.

6. Compilare i campi **Password** nel seguente modo:

    1. Selezionare **Consenti la creazione manuale della password**.

    1. Password iniziale: **Naja8996**. Quando Sara accede per la prima volta, le verrà richiesto di modificare la password.

7. Configurare **Gruppi e ruoli**.

    1. Accanto a Gruppi, selezionare **0 gruppi selezionati**.  In questo modo vengono visualizzati i gruppi disponibili.  Notare l'elenco dei gruppi disponibili.

    2. Selezionare **Operazioni** (potrebbe essere necessario scorrere verso il basso), quindi premere **Seleziona**. Notare come il testo accanto ai gruppi è stato aggiornato per rispecchiare la selezione di 1 gruppo.  

    3. Accanto a Ruoli, selezionare **Utente**. Viene visualizzato l'elenco dei ruoli della directory.  Scorrere verso il basso per visualizzare i vari ruoli predefiniti, i diversi ruoli, ma non modificare il ruolo dell'utente.  Chiudere questa finestra selezionando la **X** nell'angolo in alto a destra della pagina.

8. Configurare **Impostazioni**.

    1. Blocca l'accesso:  **No** (lasciare l'impostazione predefinita).

    1. Località di utilizzo: **Stati Uniti** (selezionare l'elenco a discesa, quindi scorrere verso il basso per trovare questa opzione).  La configurazione della località di utilizzo è obbligatoria per l'assegnazione delle licenze.

9. Nella parte inferiore della pagina, selezionare il pulsante **Crea**.

10. Verificare che l'utente compaia nell'elenco degli utenti (i nomi sono elencati in ordine alfabetico).

11. Dall'elenco degli utenti, selezionare l'utente appena creato, **Sara Perez**.  Si apre la pagina del profilo.

12. Il riquadro di spostamento a sinistra mostra le varie opzioni che è possibile configurare per l'utente.  Selezionare **Gruppi**.  Qui è possibile visualizzare ulteriori informazioni sul gruppo.  Verificare che il gruppo Operazioni sia presente nell'elenco (la visualizzazione dell'assegnazione del gruppo potrebbe richiedere alcuni minuti).  Nota:  verrà visualizzato anche il gruppo Contoso, anche se al momento della creazione dell'utente è stato assegnato un solo gruppo.  Questo è il risultato di un criterio preconfigurato nel tenant, che assegna automaticamente i nuovi utenti al gruppo Contoso.

13. Dal riquadro di spostamento sinistro selezionare **Licenze**.  Notare che per questo utente non sono state trovate assegnazioni di licenze.  

14. Per aggiungere una licenza, selezionare **+ Assegnazioni** nella parte superiore della finestra principale.

15. In Selezionare le licenze scegliere **Office 365 E3** e **Windows 10 Enterprise E3**, quindi premere il pulsante **Salva** in fondo alla pagina. Nell'angolo in alto a destra dovrebbe comparire una notifica indicante che le assegnazioni delle licenze sono avvenute correttamente.

16. Selezionare la **X** nell'angolo in alto a destra della schermata per chiudere la finestra Assegnazioni di licenze.

17. Selezionare l'icona **Aggiorna** in cima alla pagina per confermare le assegnazioni delle licenze.

18. Tornare alla pagina di Azure Active Directory Panoramica di Contoso selezionando **Contoso** nell'angolo in alto a sinistra della schermata (nella barra di navigazione), sopra il punto in cui è indicato Sara Perez | Licenze.

19. È stato creato e configurato correttamente un utente in Azure Active Directory.

20.	Disconnettersi da tutte le schede del browser selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata. Quindi, chiudere tutte le finestre del browser.

#### Attività 3.  In questa attività, si effettuerà l'accesso come Sara Perez per la prima volta.

1. Aprire Microsoft Edge.

2. Nella barra degli indirizzi immettere **login.microsoft.com**.

3. Accedere come **sara@WWLxZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab).

4. Immettere la password temporanea **Naja8996**.

5. Ora viene richiesto l'aggiornamento della password. Nel campo Password corrente immettere **Naja8996**.

6. Nel campo Nuova password immettere **SC900-Lab**.  Nel campo Confermare la password immettere SC900-Lab, quindi selezionare Accedi. Nota: è consigliabile utilizzare una password più sicura. Questa password è stata selezionata come espediente e solo per questo lab.

7. Ora dovrebbe essere stato effettuato l'accesso a Microsoft 365.

8. **Disconnettersi** da tutte le schede del browser selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata. Quindi, chiudere tutte le finestre del browser.



#### Verifica
In questo lab è stata avviata l'esplorazione iniziale di Azure AD. Poiché gli abbonati di Microsoft 365 accedono automaticamente utilizzando Azure AD, si è scoperto che è possibile accedere alle funzionalità e ai servizi di Azure AD tramite il portale di amministrazione Microsoft 365 o il portale di Azure.  Entrambi gli approcci portano alla stessa destinazione.  Inoltre, sono stati illustrati in modo dettagliato il processo di creazione di un nuovo utente e le diverse impostazioni configurabili, inclusi i gruppi a cui è possibile assegnare l'utente, la disponibilità dei ruoli e l'assegnazione di licenze utenti.


