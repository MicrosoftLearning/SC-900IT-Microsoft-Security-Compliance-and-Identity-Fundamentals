---
lab:
    title: 'Esplorazione della gestione degli accessi in Azure AD con accesso condizionale'
    module: 'Modulo 2. Lezione 3. Descrizione delle funzionalità delle soluzioni Microsoft per la gestione delle identità e degli accessi: esplorazione delle funzionalità di gestione degli accessi di Azure AD'
---


# Lab: Esplorazione della gestione degli accessi in Azure AD con accesso condizionale

## Scenario del lab
In questo lab, si esplorerà l'autenticazione a più fattori (MFA) degli accessi condizionali dal punto di vista di un amministratore e di un utente.  In qualità di amministratore, si creerà un criterio che richiederà a un utente di eseguire l'autenticazione a più fattori durante l'accesso a un'applicazione di gestione di Microsoft Azure basata su cloud.  Dal punto di vista di un utente, si vedrà l'impatto dei criteri di accesso condizionale, compreso il processo per la registrazione all'autenticazione a più fattori.

**Tempo stimato**: 10-15 minuti

#### Attività 1. In questa attività, in qualità di amministratore, si reimposterà la password per l'utente Debra Berger.  Questo passaggio è necessario in modo da poter effettuare l'accesso iniziale come utente nelle attività successive.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi immettere **portal.azure.com**.

2. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**.

3. Selezionare **Azure Active Directory**.  

4. Dal riquadro di spostamento a sinistra, selezionare **Utenti**.

5. Selezionare **Debra Berger** dall'elenco degli utenti.

6. Selezionare **Reimposta password** in cima alla pagina. Poiché non è stato effettuato l'accesso come Debra Berger in precedenza, non si conosce la sua password e sarà quindi necessario reimpostarla.

7. All'apertura della finestra Reimposta password, selezionare **Reimposta password**.  IMPORTANTE: prendere nota della nuova password, poiché servirà in un'attività successiva per poter accedere come utente.

8. Chiudere la finestra di reimpostazione della password selezionando la **X** nell'angolo in alto a destra della pagina.

9. Chiudere la finestra Utenti selezionando la **X** nell'angolo in alto a destra della pagina.

10. Tenere aperta questa finestra.


#### Attività 2.  In questa attività, si seguirà il processo di creazione di criteri di accesso condizionale in Azure AD.

1. Aprire la scheda del browser chiamata Contoso - Microsoft Azure.   Se la scheda del browser era stata chiusa in precedenza, aprire Microsoft Edge e, nella barra degli indirizzi, immettere portal.azure.com e accedere con le proprie credenziali di amministratore, quindi selezionare Azure Active Directory.  

2. Dal riquadro di spostamento sinistro, selezionare **Sicurezza**.

3. Dal riquadro di spostamento sinistro, selezionare **Accesso condizionale**.

4. Compare la schermata Criteri di accesso condizionale. Qualsiasi criterio di accesso condizionale esistente è elencato qui. Selezionare **Nuovi criteri**.

5. Nel campo Nome, immettere **MFA Test Policy** (Criteri MFA di test).

6. In Utenti e gruppi, selezionare **0 utenti e gruppi selezionati**.

7. Ora sarà visibile l'opzione per includere o escludere utenti o gruppi.  Assicurarsi che sia selezionato (sottolineato) **Includi**.

8. Scegliere l'opzione per **Seleziona utenti e gruppi**, quindi **Utenti e gruppi**.  Si apre la finestra Seleziona utenti e gruppi.  

9. Nella barra di ricerca immettere **Debra**.  Selezionare **Debra Berger** da sotto la barra di ricerca, quindi premere il pulsante **Seleziona** in fondo alla pagina.  Notare che una prassi comune consiste nell'assegnare i criteri agli utenti di un gruppo.  Per comodità rispetto allo scopo di questo lab, i criteri saranno già stati assegnati a un utente specifico. 

10. In Applicazioni cloud o azioni, selezionare **Nessuna app cloud o azione selezionata**.

11. Ora sarà visibile l'opzione per includere o escludere app cloud o azioni di utenti.  Assicurarsi che **App cloud** sia evidenziato e che **Includi** sia selezionato (sottolineato), quindi scegliere **Selezionare le app**.  Si apre la finestra Select Cloud apps (Seleziona le app cloud).

12. Nella barra di ricerca immettere **Azure**.  Dai risultati della ricerca che compaiono sotto la casella di ricerca, selezionare **Gestione di Microsoft Azure**, quindi premere **Seleziona** in fondo alla pagina.  Notare l'avviso.  

13. In Condizioni, scegliere **0 condizioni selezionate**.  Notare le diverse opzioni che è possibile configurare.  Attraverso i criteri, è possibile controllare l'accesso degli utenti sulla base dei segnali delle condizioni quali rischio, piattaforma del dispositivo, posizione, applicazioni client o stato del dispositivo.  Ad esempio, è possibile includere una condizione per i criteri da applicare a tutte le posizioni tranne le posizioni selezionate o attendibili, quali la rete della propria sede centrale.  Per questi criteri, non impostare alcuna condizione.

14. Ora si imposteranno i controlli di accesso.  In Concedi, scegliere **0 controlli selezionati**.

15. Si apre la finestra Concedi.  Assicurarsi che l'opzione **Concedi accesso** sia selezionata, quindi scegliere **Richiedi l'autenticazione a più fattori**.  Nella sezione Per più controlli, lasciare l'impostazione predefinita **Richiedi tutti i controlli selezionati**.  Premere **Seleziona** in fondo alla pagina.

16. Nella parte inferiore della pagina, in Abilita criterio, selezionare **Attivato**, quindi premere il pulsante **Crea**.

17. Dopo alcuni secondi, dovrebbero venire visualizzati i criteri pilota MFA nell'elenco dei criteri di accesso condizionale (se necessario, selezionare **Aggiorna** in cima alla pagina).

18. Disconnettersi da Azure e chiudere le finestre del browser.

#### Attività 3. In questa attività, si vedrà l'impatto dei criteri di accesso condizionale dal punto di vista dell'utente Debra Berger. Si inizierà effettuando l'accesso a un'applicazione non inclusa nei criteri di accesso condizionale.  Quindi, si ripeterà il processo per un'applicazione inclusa nei criteri di accesso condizionale.  È opportuno ricordare che i criteri richiedono che l'utente effettui l'autenticazione a più fattori al momento dell'accesso a una applicazione di gestione di Microsoft Azure.  Per utilizzare la MFA, l'utente deve innanzitutto registrare il metodo di autenticazione che verrà utilizzato per la MFA, ad esempio un codice inviato a un dispositivo mobile o un'app di autenticazione.

1. Aprire Microsoft Edge.  Nella barra degli indirizzi del browser, immettere **https://login.microsoftonline.com/**.

1. Accedere come Debra Burger.
    1. Nella finestra di accesso, immettere **DebraB@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
    1. Immettere la password annotata nell'attività precedente. Selezionare **Accedi**.
    1. Poiché la password fornita quando, in qualità di amministratore, è stata reimpostata è temporanea, sarà necessario aggiornare la password (questo non fa parte della MFA).  Immettere la password corrente, quindi per i campi Nuova password e Conferma password immettere **SC900-Lab**. 
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**

1. Dovrebbe essere stato effettuato correttamente l'accesso al proprio account di Microsoft 365.  La MFA non era richiesta per questa applicazione poiché non fa parte dei criteri.

1. Ora si proverà a effettuare l'accesso a un'applicazione che soddisfa i criteri per la MFA.  Aprire Microsoft Edge e, nella barra degli indirizzi, immettere https://portal.azure.com.

1. Verrà visualizzata una finestra che indica Sono necessarie altre informazioni.  Selezionare **Avanti**.  Notare che in questo modo si avvierà il processo di registrazione MFA, poiché si tratta del primo accesso all'app cloud identificato nei criteri di accesso condizionale.  Questo processo di registrazione è richiesto una sola volta.   Un'alternativa all'esecuzione del processo di registrazione da parte dell'utente prevede che sia l'amministratore a configurare il metodo di autenticazione da utilizzare.

1. Nella finestra Proteggi l'account, è possibile selezionare il metodo da utilizzare per la MFA.  Microsoft Authenticator è un'opzione. Per comodità, in questo esercizio del lab si selezionerà un metodo diverso.  Selezionare **Si vuole configurare un metodo diverso**.  Dalla finestra popup Scegliere un metodo diverso, selezionare **la freccia a discesa**, quindi **Telefono** e infine **Conferma**.

1. Nella finestra che si apre, assicurarsi che sia selezionato il proprio paese, quindi immettere il numero di telefono cellulare da utilizzare, verificare che sia selezionato **Invia un SMS**, quindi premere **Avanti**.  Nella schermata comparirà "Verificato tramite SMS. Il telefono è stato registrato".  Selezionare **Avanti**, quindi **Fatto**.  In questo modo si completa il processo di registrazione da effettuare una sola volta.

1. Probabilmente verrà visualizzato un messaggio il quale indica che l'accesso è scaduto.  Immettere solamente la password **SC900-Lab** e selezionare **Accedi**.

1. Verrà visualizzata una finestra che richiede l'immissione del codice inviato al telefono.  Immettere il codice e selezionare **Avanti**.  Questo è ciò che l'utente Gerhard sperimenterà ogni volta che accederà all'applicazione cloud di gestione di Microsoft Azure, ad esempio il portale di Azure, conformemente ai criteri MFA.

1. Verrà visualizzata una finestra che richiede l'immissione del codice inviato al telefono.  Immettere il codice e selezionare il pulsante **Verifica**.  Quando compare la domanda se rimanere connessi, selezionare **No**.

1. Ora si dovrebbe poter accedere al portale di Azure.  Il portale di Azure è un'applicazione di gestione di Microsoft Azure e pertanto richiede l'autenticazione a più fattori, conformemente ai criteri di accesso condizionale creati.  

1. Disconnettersi selezionando l'icona dell'utente accanto all'indirizzo e-mail nell'angolo in alto a destra della schermata, quindi Disconnetti. Quindi, chiudere tutte le finestre del browser.

#### Verifica
In questo lab, si è seguito il processo di configurazione dei criteri di accesso condizionale, che richiede che gli utenti effettuino la MFA quando accedono all'applicazione cloud di gestione di Microsoft Azure.  Quindi, in qualità di utente, si è seguito il processo di registrazione per la MFA e si è visto l'impatto dei criteri di accesso condizionale che richiedono l'utilizzo della MFA quando si accede al portale di Azure.
