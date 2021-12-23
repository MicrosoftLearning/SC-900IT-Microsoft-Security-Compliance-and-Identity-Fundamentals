---
Demo:
    title: 'Criteri di Azure'
    module: 'Modulo 4. Lezione 5. Descrizione delle funzionalità delle soluzioni di conformità Microsoft: descrizione dei criteri di Azure'
---


# Demo: Criteri di Azure

### Scenario demo
Questa demo illustra il processo di configurazione di un criterio di Azure e l'impatto di tale criterio.

#### Demo Parte 1: Creare un criterio per richiedere un tag su un gruppo di risorse (mostra la procedura per creare un criterio da un modello)

1. Aprire Microsoft Edge. Nella barra degli indirizzi immettere **portal.microsoft.com**.  L'accesso dovrebbe già essere stato effettuato, altrimenti è possibile accedere con le credenziali di amministratore.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, inserire **criteri**, quindi selezionare **Criteri** dai risultati della ricerca.

1. Compare una panoramica della pagina Criteri. Notare le informazioni disponibili nel dashboard.

1. Dal riquadro di spostamento sinistro, sotto Creazione, selezionare **Assegnazioni**.  Si noterà che è già presente un'assegnazione di criteri, selezionare **Impostazione predefinita del Centro sicurezza di Azure**.  Controllare il campo della descrizione. NOTA: il campo della descrizione fa riferimento al Centro sicurezza di Azure, rinominato Microsoft Defender for Cloud.  Tornare alla pagina Assegnazioni di criteri selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Dalla parte superiore della pagina selezionare **Assegna criterio**.

1. Si apre la procedura guidata di assegnazione dei criteri per guidare l'amministratore nel processo di assegnazione di un criterio.  Accanto al campo Definizione del criterio, selezionare le **ellissi**.  Viene fornito un elenco delle definizioni dei criteri disponibili.  

1. Nella barra di ricerca immettere **Tag**.

1. Dai risultati della ricerca, selezionare **Richiedi un tag su gruppo di risorse** (potrebbe essere necessario scorrere verso il basso), quindi premere **Seleziona**.  Nota: l'effetto di questo criterio è negare la creazione di qualunque gruppo di risorse che non soddisfa il requisito.  

1. Si noti il nome di assegnazione predefinito.  Mantenere il nome così com'è e dal fondo della pagina selezionare **Avanti**.

1. Nel campo Nome tag, inserire **Ambiente** (i gruppi di risorse richiederanno un tag Ambiente) quindi selezionare **Avanti**.  

1. Dalla scheda Correzioni, leggere la descrizione ma non cambiare le impostazioni. Selezionare **Avanti**.

1. Nel messaggio di non conformità immettere **È richiesto un tag ambiente**, quindi selezionare **Avanti**. Nota: questo messaggio apparirà come motivo di non conformità per i gruppi di risorse che sono stati creati prima dell'assegnazione del criterio e non hanno un tag Ambiente.  La creazione di gruppi di risorse successiva alla creazione verrà negata in assenza di un tag ambiente.

1. Rivedere l'assegnazione dei criteri, quindi selezionare Crea.  Se non si vede immediatamente il criterio, selezionare **Aggiorna**. Nota: l'applicazione del criterio potrebbe richiedere fino a 30 minuti.

1. Uscire dalla pagina di assegnazione dei criteri selezionando la **X** nell'angolo in alto a destra dello schermo.

1. Ora ci si trova nella home page dei servizi di Azure.  Tenere questa pagina aperta, servirà per l'attività successiva.

#### Demo Parte 2:  Mostrare l'impatto del criterio creando un gruppo di risorse senza un tag, poi sistemarlo in modo da avere un tag.

1. Dalla parte superiore della pagina, sotto Servizi di Azure, selezionare **Gruppi di risorse**. Se l'opzione non è elencata, inserire Gruppi di risorse nella barra di ricerca e selezionarla da lì.

1. Dall'angolo superiore sinistro della pagina, selezionare **+ Crea**.

1. Dalla scheda Generale di Crea un gruppo di risorse, lasciare il campo Sottoscrizione così come è, Azure Pass - Sponsorizzazione.

1. Nel campo Gruppo di risorse immettere **SC900-Labs**.

1. Lasciare l'impostazione Area geografica sul valore predefinito, quindi selezionare **Avanti: Tag**.

1. Lasciare vuoto il campo Nome e Valore del tag.  NON POPOLARE, quindi selezionare **Verifica + Crea**.

1. Si vedrà un'indicazione di convalida riuscita (il nome e il valore del tag non sono campi obbligatori nella procedura guidata), quindi selezionare **Crea**.

1. Comparirà un messaggio di errore nella parte superiore dello schermo, "Non è stato possibile creare il gruppo di risorse. Visualizza i dettagli dell'errore".  Selezionare **Visualizza dettagli errore**. La condizione che fa parte dei criteri di Azure non è stata soddisfatta, quindi la creazione del gruppo di risorse è stata bloccata per non conformità. Nota: se non viene visualizzato il messaggio di errore e il gruppo di risorse viene creato, significa che l'applicazione del criterio non è ancora avvenuta.  Accedere alla pagina dei criteri per il criterio creato nell'attività precedente e una volta che il criterio ha effetto si vedrà che la risorsa non è conforme.  La pagina dei dettagli includerà il messaggio di non conformità.

1. Il riepilogo dell'errore mostra il seguente tipo di errore, "La risorsa ‘SC900-Labs’ non è consentita dai criteri."  Chiudere questa finestra selezionando la **X** nell'angolo in alto a sinistra dello schermo.

1. Dalla finestra Crea un gruppo di risorse selezionare **<Precedente**.

1. Si ritorna alla pagina Tag per la creazione di un gruppo di risorse.  Nel campo Nome immettere Ambiente e nel campo Valore immettere **SC900-Labs**, quindi selezionare **Avanti: Verifica + Crea >**.

1. Verificare il tag e selezionare **Crea**.

1. Si vedrà elencato il gruppo di risorse.  Poiché il tag è stato fornito nel gruppo di risorse, la condizione inclusa come parte del criterio di Azure è stata soddisfatta.  Il gruppo di risorse è conforme al criterio.

#### Verifica

Questa demo ha illustrato il processo di configurazione di un criterio di Azure e l'impatto di tale criterio.
