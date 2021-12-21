---
lab:
    title: 'Esplorazione del portale di Microsoft 365 Defender'
    module: 'Modulo 3. Lezione 5. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione delle funzionalità di gestione della sicurezza di Microsoft 365'
---


# Lab: Esplorazione del portale di Microsoft 365 Defender

## Scenario del lab
In questo lab verrà esplorato il portale di Microsoft 365 Defender esaminando il contenuto visualizzato nella pagina di destinazione. Verranno inoltre esplorate le opzioni sul riquadro di spostamento che forniscono accesso rapido a funzionalità che fanno parte della soluzione Extended Detection and Response (XDR) di Microsoft: Microsoft Defender per endpoint e Microsoft Defender per Office 365 (e-mail e collaborazione).  Infine si esplorerà inoltre in che modo Microsoft Secure Score può aiutare un'organizzazione a migliorare il proprio profilo di sicurezza.


**Tempo stimato**: 10-15 minuti

#### Attività 1.  Esplorazione della pagina di destinazione di Microsoft 365 Defender

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **admin.microsoft.com**.

1. Accedere con le credenziali di amministratore.
    1. Nella finestra di accesso, immettere **admin@WWLxZZZZZZ.onmicrosoft.com** (dove ZZZZZZ è l'ID tenant univoco fornito dal provider di hosting del lab), quindi selezionare **Avanti**.
   
    1. Immettere la password di amministratore, che dovrebbe essere fornita dal proprio provider di hosting del lab. Selezionare **Accedi**.
    1. Quando compare la domanda se rimanere connessi, selezionare **Sì**. In questo modo si accede alla pagina dell'interfaccia di amministrazione di Microsoft 365.

1. Dal riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 selezionare **Sicurezza**.  Se l'opzione Sicurezza non è disponibile, selezionare **Mostra tutto** e quindi selezionare **Sicurezza**.  Si apre una nuova pagina del browser alla pagina di benvenuto del portale Microsoft 365 Defender.  

1. Se è la prima volta che si visita il portale Microsoft 365 Defender, potrebbe comparire una finestra pop-up per una breve presentazione.  È consigliabile completare la presentazione.  Selezionare **Take a quick tour** (Segui una breve presentazione).  Leggere la descrizione fornita in ciascuna finestra popup, quindi selezionare **Avanti**. Continuare con la presentazione fino alla fine, quindi selezionare **Fatto**.

1. Il riquadro di spostamento sinistro offre collegamenti e accesso alle informazioni che fanno parte della soluzione XDR (eXtended Detection and Response) Microsoft, che include incidenti e avvisi, ricerca, centro notifiche, analisi delle minacce, punteggio di sicurezza e molto altro.  Include inoltre l'accesso rapido a Microsoft Defender per endpoint (i collegamenti elencati sotto Endpoint) e Defender per Office 365 (i collegamenti elencati sotto E-mail e collaborazione).  Esplorare queste opzioni selezionando alcuni collegamenti.   Per tornare alla home page del portale Microsoft 365 Defender, selezionare **Home** sul riquadro di spostamento sinistro.  Nota: potrebbero non essere elencate molte informazioni in queste schede perché non ci sono dispositivi collegati e potrebbero non esserci minacce o avvisi attivi.

1. La pagina di benvenuto del portale Microsoft 365 Defender, mostra molte delle schede comuni di cui hanno bisogno i team di sicurezza. La composizione di schede e dati dipende dal ruolo dell'utente. Scorrere la pagina per visualizzare l'insieme di schede predefinito per il proprio ruolo di amministratore globale.

1. Le schede visualizzate possono essere personalizzate secondo le proprie preferenze.  Selezionare **+ Aggiungi schede**. Viene aperta una finestra la quale indica che tutte le schede sono già presenti nella home page.  Chiudere la finestra selezionando la **X** nell'angolo in alto a destra della finestra.

1. La selezione dei puntini di sospensione nell'angolo in alto a destra di qualsiasi scheda fornirà ulteriori azioni che è possibile eseguire.  

1. Le schede possono anche essere spostate. Passando il cursore del mouse sulla barra del titolo di qualsiasi scheda, quando il cursore diventa a forma di croce, selezionare la scheda e spostala nella posizione desiderata.

1. Selezionando il titolo di una scheda si accede a informazioni aggiuntive per quell'argomento. Questo passaggio sarà approfondito nell'attività successiva.  Tenere aperta la finestra del browser.

#### Attività 2. In questa attività si esplorerà come Microsoft Secure Score può aiutare un'organizzazione a migliorare il proprio profilo di sicurezza.

1. Dalla pagina di benvenuto del portale Microsoft 365 Defender, selezionare **Microsoft Secure Score**, dalla barra del titolo della scheda (il testo diventerà blu).  In alternativa, è possibile selezionare **Secure Score** dal riquadro di spostamento sinistro.

1. La pagina Microsoft Secure Score si apre sulla scheda Panoramica.  Microsoft Secure Score è una misura del profilo di sicurezza di un'organizzazione. Il punteggio di sicurezza dell'organizzazione è mostrato come percentuale, insieme al numero di punti raggiunti sul totale dei punti possibili e suddiviso per categoria. Selezionare **Includi** accanto a Il punteggio di sicurezza.  Viene visualizzata una piccola finestra che consente di includere il punteggio realizzabile, il punteggio pianificato e il punteggio della licenza corrente nel dettaglio del punteggio di sicurezza dell'organizzazione.  Selezionare di nuovo **Includi** per chiudere la finestra.

1. La pagina panoramica include anche le azioni di miglioramento più importanti, il punteggio di confronto, la cronologia e le risorse aggiuntive.

1. Selezionare **Azioni di miglioramento** dalla parte superiore della pagina.  Notare le informazioni disponibili nella tabella, per ciascun elemento, che includono l'impatto del punteggio e i punti realizzati.  

1. La selezione di un elemento dall'elenco fornisce informazioni dettagliate.  Selezionare **Richiedi la MFA per i ruoli amministrativi**.  Selezionare **Edit status & acton plan** (Modifica stato e piano di azione).  Nella finestra che viene aperta notare le opzioni di stato disponibili. Selezionare la **X** nell'angolo in alto a destra per chiudere questa finestra.

1. Nella parte inferiore della pagina selezionare **Gestisci in Microsoft Azure**.  Viene aperta una nuova scheda del browser che porta direttamente alla pagina Criteri di accesso condizionale.  Se è stato completato l'esercizio del lab Accesso condizionale, il criterio dovrebbe essere visualizzato nell'elenco. Tornare alla scheda Microsoft Secure Score del browser per tornare alla pagina delle azioni di miglioramento per richiedere la MFA per i ruoli amministrativi. Nell'angolo in alto a destra della finestra, selezionare la **X** per chiudere questa finestra e tornare alla pagina delle azioni di miglioramento.

1. Selezionare la scheda **Cronologia** dalla parte superiore della pagina.  Alcune attività possono mostrare punti negativi.  Come descritto nel campo dell'attività, il motivo può risiedere nel fatto che un elemento è stato rimosso in quanto non più pertinente.  Selezionare una voce dalla tabella della cronologia.  Viene aperta una pagina dettagliata per l'elemento selezionato.  Esplorare le opzioni disponibili.  Per uscire dalla pagina dei dettagli e tornare alla pagina Cronologia, selezionare la **X** nell'angolo in alto a destra della pagina.

1. Dalla parte superiore della pagina, selezionare **Metriche e tendenze**.  Consultare le informazioni disponibili.  Dall'angolo superiore destro della pagina, selezionare l'**icona del calendario**.  È possibile limitare la vista a un intervallo di date personalizzato.  Selezionando l'**icona del filtro** è possibile filtrare la vista per identità, dispositivi e/o app.  Chiudere la finestra e selezionare **Home** dal riquadro di spostamento sinistro per tornare alla home page di Microsoft 365 Defender.

1. Chiudere la pagina del browser.

#### Verifica
In questo lab è stato esplorato il portale di Microsoft 365 Defender esaminando il contenuto visualizzato nella pagina di destinazione, sono state esplorate le opzioni sul riquadro di spostamento che forniscono un rapido accesso alle funzionalità che fanno parte della soluzione Extended Detection and Response (XDR) di Microsoft, Microsoft Defender per endpoint e Microsoft Defender per Office 365 (e-mail e collaborazione).  Infine, è stato esplorato in che modo Microsoft Secure Score può aiutare un'organizzazione a migliorare il proprio profilo di sicurezza.
