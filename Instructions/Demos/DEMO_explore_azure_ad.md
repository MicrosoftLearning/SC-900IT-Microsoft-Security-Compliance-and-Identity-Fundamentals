---
Demo:
    title: 'Impostazioni utente di Azure Active Directory'
    module: 'Modulo 2. Lezione 1. Descrizione delle funzionalità delle soluzioni Microsoft per la gestione delle identità e degli accessi: esplorare i servizi e i tipi di identità di Azure AD'
---

# Demo: Impostazioni utente di Azure Active Directory

### Scenario demo

In questa demo, si accederà ad Azure Active Directory e verranno illustrate le varie impostazioni per un utente esistente.

1. Accedere alla scheda **Home – Microsoft Azure** aperta nel browser.  Se la scheda era stata chiusa, aprire Microsoft Edge e nella barra degli indirizzi inserire portal.azure.com e accedere con le stesse credenziali di amministratore del tenant di Microsoft 365.

1. La pagina di destinazione del portale di Azure mostra i servizi Azure, selezionare **Azure Active Directory**. Se non è immediatamente visibile, allora dalla casella di ricerca accanto a Microsoft Azure, digitare Azure Active Directory.  Si potrebbe anche voler mostrare come accedere tramite l'icona del menu del portale (le tre linee orizzontali indicate anche come icona ad hamburger, nella barra blu nella parte superiore della pagina) a sinistra di Microsoft Azure.

1. Dal riquadro di spostamento sinistro, selezionare **Utenti**. Si ricorda che il tenant è già configurato con gli utenti.

1. Dall'elenco degli utenti, selezionare **Adele Vance**.

1. Notare che sul riquadro di spostamento sinistro è selezionato **Profilo**.  Mostrare/attestare le informazioni mostrate nella pagina del profilo.

1. Dal riquadro di spostamento sinistro, selezionare **Ruoli assegnati**.  A questo utente non è assegnato nessun ruolo di amministratore.  Dalla parte superiore della pagina selezionare **+ Aggiungi assegnazione** per mostrare i tipi di ruoli di amministratore disponibili.  Non aggiungerne nessuno, basta chiudere la pagina selezionando la **X** nella parte superiore destra della pagina.

1. Dal riquadro di spostamento sinistro, selezionare **Gruppi**.  Attestare che l'utente è un membro di diversi gruppi.  Qui è possibile attestare i tipi di gruppi.  Per aggiungere questo utente ad altri gruppi, basta selezionare **+ Aggiungi appartenenze**.  Non aggiungere nuovi gruppi, basta attestare quanto è facile aggiungere un utente ai gruppi esistenti. Chiudere la finestra dei gruppi selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal riquadro di spostamento sinistro selezionare **Licenze**. Si ricorda che a questo utente sono assegnate le licenze Microsoft 365 E5 e la licenza EMS.  Per aggiungere una licenza, selezionare **+ Assegnazioni** dalla parte superiore della finestra principale.  Mostrare le licenze per questo utente. NON modificare nulla.  Chiudere questa finestra selezionando la **X** nell'angolo in alto a destra della pagina.

1. Dal pannello di navigazione sinistro selezionare **Dispositivi**.  Non appare nulla, ma si può dire che se questo utente avesse dei dispositivi assegnati apparirebbero qui.

1. Dal riquadro di spostamento sinistro, selezionare **Assegnazioni di ruolo di Azure**.  Nota:
    1. questo è diverso dalla scheda dei ruoli assegnati mostrata prima, in quanto la scheda precedente serve per il controllo degli accessi in base al ruolo in Azure Active Directory (enfatizzare Active Directory).
    1. In questa scheda, è possibile visualizzare le assegnazioni di ruolo degli utenti per le risorse di Azure. Per esempio, se si dovesse creare un gruppo di risorse di Azure, e si assegnasse ad Adele un ruolo specifico, come proprietaria o collaboratrice del gruppo di risorse, si vedrebbe quel ruolo elencato qui. Questo fa parte del controllo degli accessi in base al ruolo di Azure (RBAC Azure). Questa assegnazione di ruolo è gestita come parte di quella specifica risorsa.

1. Dal pannello di navigazione sinistro, selezionare **Metodi di autenticazione**.  Ricordare la descrizione che dice: "In questa pagina è possibile configurare i numeri di telefono e gli indirizzi di posta elettronica usati dagli utenti per eseguire Multi-Factor Authentication e la reimpostazione della password self-service e reimpostare la password di un utente". Se un utente è configurato per la reimpostazione della password self-service o è richiesto l'uso della MFA, e in qualità di amministratore si popola questo campo, allora saranno già registrati e non dovranno passare attraverso la procedura di registrazione per la reimpostazione della password self-service o MFA.  È comune che l'utente si registri autonomamente piuttosto che rivolgersi all'amministratore per farlo.

1. Dal pannello di navigazione sinistro, selezionare **Accessi**.  Qui è riportata l'attività di accesso per questo utente.  Per questo utente potrebbe non essere riportate informazioni, dato che non ha ancora effettuato l'accesso.

1. Selezionare la **X** nell'angolo in alto a destra della pagina. In questo modo si torna all'elenco degli utenti.  Prima di chiudere l'elenco degli utenti, è possibile evidenziare che la MFA è mostrata nella parte superiore della pagina.  Selezionare **Autenticazione a più fattori**.  In questo modo si apre una nuova finestra del browser.  Qui è possibile selezionare in blocco la MFA per gli utenti.  Questo è un modo per abilitare la MFA per gli utenti.  In realtà mostreremo di più sulla MFA nel contesto dell'Accesso condizionale che consente un controllo più granulare della MFA.  Chiudere la scheda del browser per l'Autenticazione a più fattori.

1. Selezionare la **X** nell'angolo in alto a destra della pagina. In questo modo si torna alla pagina principale per il tenant di Contoso.

### Verifica

Questa demo ha mostrato le impostazioni di un utente esistente, compresi i gruppi a cui l'utente può essere assegnato, la disponibilità dei ruoli e l'assegnazione delle licenze utente.
