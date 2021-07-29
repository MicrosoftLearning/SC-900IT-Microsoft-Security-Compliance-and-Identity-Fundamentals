---
lab:
    title: 'Esplorazione della governance dell’identità in Azure AD con Privileged Identity Management'
    module: 'Modulo 2. Lezione 4. Descrizione delle funzionalità di protezione e governance dell'identità di Azure AD: Descrizione di Azure Identity Protection.'
---


# Lab: Esplorazione della governance dell'identità in Azure AD con Privileged Identity Management

## Scenario del lab
In questo lab, si esploreranno alcune delle funzionalità di base di Privileged identity Management (PIM). PIM richiede Azure AD Premium P2.  In questo lab, in qualità di amministratore, si configurerà uno degli utenti, Diego Siciliani, con un ruolo di amministratore utenti di Azure AD attraverso Privileged ID Management (PIM).   Attraverso i privilegi di amministratore, Diego riuscirà a creare utenti e gruppi, gestire licenze e altro ancora.  Per la licenza di Azure AD Premium P2 è necessario configurare sia l'amministratore che l'utente, Diego.

**Tempo stimato**: 30-45 minuti

#### Attività 1. In questa attività, in qualità di amministratore, si reimposterà la password per l'utente Diego Siciliani. Questo passaggio è necessario in modo da poter effettuare l'accesso iniziale come utente nelle attività successive.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **portal.azure.com**.

2. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

3. Selezionare **Azure Active Directory**.  

4. Dal riquadro di spostamento a sinistra, selezionare **Utenti**.

5. Selezionare **Diego Siciliani** dall'elenco degli utenti.

6. Selezionare **Reimposta password** in cima alla pagina. Poiché non è stato effettuato l'accesso come Diego in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

7. All'apertura della finestra Reimposta password, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, poiché servirà in un'attività successiva per poter accedere come utente.

8. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della pagina.

9. Chiudere la finestra del profilo di Diego selezionando la **X** nell'angolo in alto a destra della pagina.

10. Chiudere la finestra Tutti gli utenti selezionando la **X** nell'angolo in alto a destra della pagina. Ora ci si dovrebbe trovare nella pagina di Contoso di Azure Active Directory.

11. Tenere aperta la pagina del browser poiché verrà usata nelle attività successive.


#### Attività 2. In questa attività, in qualità di amministratore si assegnerà a Diego un ruolo di Azure AD in Privileged Identity Management.

1. Passare alla scheda del browser aperta chiamata Contoso - Microsoft Azure.   Se la scheda del browser era stata chiusa in precedenza, aprire Microsoft Edge e, nella barra degli indirizzi, immettere portal.azure.com e accedere con le proprie credenziali di amministratore, quindi selezionare Azure Active Directory.  

2. Dal riquadro di spostamento sinistro, selezionare **Identity Governance**.

3. Dalla finestra principale, assicurarsi che **Attività iniziali** sia sottolineato, quindi selezionare **Gestione delle assegnazioni di ruolo** nella porzione centrale della schermata sulla destra.  In alternativa, dal riquadro di spostamento a sinistra, sotto Privileged Identity Management, selezionare **Ruoli di Azure AD**.

4. Ora ci si trova nella finestra di avvio rapido di Privileged Identity Management.  Selezionare **Gestisci accesso**.

5. Ora ci si trova nella pagina Ruoli di Contoso.  Nella barra della ricerca in cima alla pagina, immettere **utente**.  Selezionare **Amministratore utenti** dai risultati della ricerca. 

6. Dalla parte superiore della pagina, selezionare **+ Assegnazioni**.

7. Nella pagina Aggiungi assegnazioni, assicurarsi che **Appartenenza** sia sottolineato.  Qui verranno configurate le impostazioni di appartenenza per il ruolo di amministratore utenti in PIM.

8. Lasciare Tipo di ambito impostato sul valore predefinito, Directory.  

9. In Seleziona membri, scegliere **Nessun membro selezionato**. In questo modo si apre la finestra Seleziona un membro. 

10. Nella barra di ricerca immettere **Diego**.  Selezionare **Diego Siciliani** dai risultati della ricerca, quindi premere **Seleziona** in fondo alla pagina.  

11. In Seleziona membri, si vedrà 1 membro selezionato e il nome e l'indirizzo e-mail del membro selezionato, Diego Siciliani. In fondo alla pagina Aggiungi assegnazioni, selezionare **Avanti**.  

12. Ora ci si trova nella pagina Impostazione.  Lasciare Tipo di assegnazione impostato sul valore predefinito, Idoneo.

13. Se la casella Idoneità permanente è selezionata, selezionare **Idoneità permanente** per rimuovere il segno di spunta.

14. Nei campi Ora di inizio dell'assegnazione, tenere la data e l'ora predefinite, ossia data e ora correnti.

15. Nei campi Ora di fine dell'assegnazione, modificare la data in data odierna (notare che l'impostazione predefinita è un anno a partire dalla data odierna, quindi è necessario modificare l'anno). Per l'ora, impostarla su due ore dopo l'ora corrente.  Dopo aver impostato il campo dell'ora di fine dell'assegnazione, premere il tasto TAB della tastiera e selezionare **Assegna** in fondo alla pagina.  

16. In questo modo si torna alla finestra Assegnazioni.  Dopo alcuni secondi, Diego Siciliani dovrebbe essere visibile nella tabella Amministratore utenti, insieme ai dettagli dell'assegnazione.  Se dopo alcuni secondi non si vede ancora l'aggiornamento, selezionare **Aggiorna** nella parte superiore della pagina.

17. Dalla parte superiore della pagina, selezionare **Impostazioni**.

18. Nei dettagli dell'impostazione Ruolo per l'amministratore utenti, notare le varie opzioni.  Osservare che l'opzione "Richiedi giustificazione all'attivazione" è impostata su Sì e che anche "All'attivazione richiedi Azure MFA" è impostata su Sì.  Queste impostazioni saranno entrambe visibili nell'attività successiva, quando Diego attiverà il ruolo.  Notare inoltre che "Richiedi l'approvazione per l'attivazione" è impostata su No. Lasciare tutte le impostazioni sui valori predefiniti.  Chiudere la pagina selezionando la **X** nell'angolo in alto a destra della schermata.

19. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Quindi, chiudere tutte le finestre del browser.


#### Attività 3. Attività 3.  In questa attività, in qualità di Diego Siciliani, si effettuerà l'accesso al portale di Azure per accedere alla funzionalità Privileged Identity Management di Azure Active Directory in modo da attivare la propria assegnazione come amministratore utenti.  Una volta attivata, si apporteranno alcune modifiche alla configurazione di un utente esistente. Nota: per questa attività sarà necessario avere accesso immediato a un dispositivo mobile che può ricevere messaggi di testo.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi del browser, immettere **portal.azure.com**.

1. Accedere come Diego Siciliani.
    1. Nella finestra di accesso, immettere **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password temporanea annotata nell'attività precedente, quindi selezionare **Accedi**. Selezionare **Accedi**.
    1. Poiché la password immessa era una password temporanea, ora occorre aggiornarla. Immettere la password corrente.  Per i campi Nuova password e Conferma password, immettere **SC900-Lab**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

1. Dovrebbe essere stato effettuato l'accesso al portale di Azure.
1. Dalla pagina principale di benvenuto, in Servizi di Azure, selezionare **Azure Active Directory**.
1. Dal riquadro di spostamento sinistro, selezionare **Identity Governance**.
1. Dal riquadro di spostamento a sinistra, sotto Privileged Identity Management, selezionare **Ruoli di Azure AD**.
1. Dal riquadro di spostamento sinistro, selezionare **Ruoli personali**.  Vengono visualizzate le informazioni relative ai propri ruoli di Azure AD.  Si vedrà che all'utente Diego è stato assegnato il ruolo di amministratore utenti.  
1. Nell'ultima colonna della tabella, chiamata Azione, selezionare **Attiva**.
1. Verrà visualizzata un'icona di avviso che indica È necessaria una verifica aggiuntiva.  Selezionare **Fare clic per continuare**.  Ricordare che le impostazioni di PIM per il ruolo di amministratore utenti richiedono l'autenticazione a più fattori.  Inoltre, poiché le informazioni di contatto di Diego da usare con la MFA (metodi di autenticazione) non erano state configurate in precedenza, Diego dovrà registrare le proprie informazioni per poter utilizzare la MFA.  Sebbene Diego dovrà effettuare la MFA ogni volta che accede come amministratore utenti, nel corso del periodo di assegnazione, il processo di registrazione MFA deve essere eseguito una sola volta.
1. Si riceve una notifica la quale indica che sono necessarie altre informazioni; selezionare **Avanti**.
1. Immettere la propria password, **SC900-Lab**.
1. Nella parte inferiore della finestra di Microsoft Authenticator, selezionare **Si vuole configurare un metodo diverso**.
1. Viene visualizzata la richiesta Scegliere un metodo diverso.  Accanto alla dicitura App Authenticator, selezionare il tasto freccia GIÙ.   Selezionare **Telefono**, quindi **Conferma**.
1. Viene richiesta l'immissione del numero di telefono che si vuole usare. Assicurarsi della correttezza del paese per il prefisso internazionale del proprio numero di telefono.  Immettere il numero di telefono, assicurarsi che **Invia un SMS** sia selezionato, quindi premere **Avanti**.
1. Immettere il codice a 6 cifre ricevuto sul telefono e selezionare **Avanti**. 
1. Verrà visualizzata una notifica dell'avvenuta registrazione del telefono. Selezionare **Avanti**, quindi **Fatto**.
1. Compare la richiesta se rimanere connessi. Selezionare **Sì**.
1. Viene visualizzata la finestra Activate User Administrator (Attiva amministratore utenti).  È necessario immettere un motivo per l'attivazione.  Nella casella visualizzata, immettere un motivo a scelta (con un massimo di 500 caratteri), quindi selezionare **Attiva**.
1. Durante l'elaborazione dell'attivazione verrà visualizzato il relativo stato (3 stadi di avanzamento).
1. Una volta completata l'attivazione, si tornerà alla pagina Ruoli personali | di Azure AD, dove verrà visualizzata una notifica che indica l'avvenuta attivazione di un ruolo.  Selezionare **Fare clic qui** per visualizzare i propri ruoli attivi.  Se si nota che l'ora di fine è diversa dalla configurazione originale, selezionare il pulsante di aggiornamento in cima alla pagina (l'aggiornamento potrebbe richiedere alcuni minuti). 
1. Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della schermata.
1. Chiudere la finestra di avvio rapido di Privileged Identity Management | selezionando la **X** nell'angolo in alto a destra della schermata.
1. Chiudere la finestra di Identity Governance selezionando la **X** nell'angolo in alto a destra della schermata.
1. Ora si torna alla pagina di Contoso di Azure Active Directory.  In qualità di amministratore utenti di Azure AD, è possibile creare utenti e gruppi, gestire licenze e altro ancora.   Dal riquadro di spostamento sinistro, selezionare **Utenti**.
1. Dall'elenco degli utenti, selezionare **Bianca Pisani**.
1. Dal riquadro di spostamento sinistro, selezionare **Licenze**.
1. Notare che Bianca non ha licenze assegnate.  Dalla parte superiore della pagina, selezionare **+ Assegnazioni**. 
1. Dall'elenco Selezionare le licenze, scegliere **Office 365 E3** e **Windows 10 Enterprise E3**.
1. In fondo alla pagina, selezionare **Salva**.  Nell'angolo in alto a destra della pagina, verrà visualizzata una breve notifica la quale indica che le licenze sono state assegnate.
1. Chiudere la pagina delle assegnazioni delle licenze aggiornate selezionando la **X** nell'angolo in alto a destra della schermata.
1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi **Disconnetti**. Quindi, chiudere tutte le finestre del browser.
1. La durata del ruolo di amministratore utenti è limitata al tempo configurato.

#### Verifica
In questo lab, si è esplorato PIM.  In qualità di amministratore, si è configurato Diego con privilegi di amministratore utenti per un determinato periodo di tempo.  Quindi, in qualità di Diego, si è seguito il processo di attivazione dei privilegi di amministratore utenti e di configurazione delle impostazioni utente.  Ricordare che PIM richiede la licenza Azure AD Premium P2.
