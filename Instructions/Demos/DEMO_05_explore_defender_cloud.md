---
Demo:
    title: 'Microsoft Defender for Cloud'
    module: 'Modulo 3. Lezione 2. Descrizione delle funzionalità delle soluzioni di sicurezza Microsoft: descrizione delle funzionalità di gestione della sicurezza di Azure'
---

# Demo: Microsoft Defender for Cloud

### Scenario demo

Questa demo illustra Microsoft Defender for Cloud e mostra come è possibile usare Azure Secure Score per migliorare il comportamento di sicurezza di un'organizzazione.

1. Aprire la scheda del browser **Home-Microsoft Azure**.  Se la scheda era stata chiusa in precedenza, aprire una pagina del browser e nella barra degli indirizzi inserire portal.azure.com e accedere di nuovo.

1. Nella casella di ricerca, nella barra blu nella parte superiore della pagina accanto a Microsoft Azure, immettere **Microsoft Defender for Cloud** e quindi selezionare **Microsoft Defender for Cloud** nei risultati della ricerca.

1. Se questa è la prima volta che si accede a Microsoft Defender for Cloud con la propria sottoscrizione, è possibile che venga visualizzata la pagina Panoramica e potrebbe essere richiesto di eseguire l'aggiornamento.  Scorrere in fondo alla pagina e selezionare **ignora**.

1. Osservare le informazioni disponibili nella pagina Panoramica di Microsoft Defender for Cloud.  Nota: potrebbe essere visualizzata una casella di informazioni blu in alto nella pagina la quale indica che la visualizzazione delle informazioni potrebbe essere limitata.  Non selezionarlo (l'elaborazione può richiedere fino a 15 minuti e non fa alcuna differenza per questa demo).

1. Le informazioni nella parte superiore della pagina includono il numero di sottoscrizioni Azure, il numero di risorse valutate, il numero di raccomandazioni attive ed eventuali avvisi di sicurezza.  Il corpo principale della pagina contiene schede che rappresentano Punteggio di sicurezza, Conformità alle normative, Informazioni dettagliate, Azure Defender e altro.  

1. Nella parte superiore della pagina selezionare **Assessed resources** (Risorse valutate).  (Si noti che questo equivale alla selezione di Inventario nel riquadro di spostamento sinistro della home page di Microsoft Defender for Cloud).
    1. In questo modo si verrà reindirizzati alla pagina **Inventario** che mostra la sottoscrizione di Azure Pass.  Selezionare **Azure Pass – Sponsorizzazione**.
    1. La pagina Integrità risorse offre un elenco di raccomandazioni.  Dall'elenco disponibile, selezionare **There should be more than one owner assigned to your subscription** (È consigliabile assegnare più di un proprietario all'abbonamento).
    1. Selezionare la freccia a discesa accanto a Procedura di correzione. Osservare in che modo sono forniti i passaggi di correzione insieme all'opzione per intraprendere un'azione.  
    1. Selezionare **Microsoft Defender for Cloud** nell'angolo in alto a sinistra della schermata per tornare alla pagina Panoramica di Microsoft Defender for Cloud.

1. Dalla parte superiore della pagina selezionare **Raccomandazioni attive**.  (Si noti che questo equivale alla selezione di Raccomandazioni nel riquadro di spostamento sinistro della home page di Microsoft Defender for Cloud).
    1. La pagina delle raccomandazioni mostra il dashboard del punteggio di sicurezza.
    1. Sotto alla Dashboard del punteggio di sicurezza è presente un elenco di controlli. Ciascun controllo di sicurezza rappresenta un rischio di sicurezza che deve essere mitigato e include anche informazioni sul punteggio massimo associato al rispettivo controllo, il punteggio attuale, il potenziale aumento del punteggio e lo stato di integrità della risorsa.  
    1. Selezionare uno dei controlli, ad esempio **Abilita MFA**.  Selezionare una delle voci secondarie **È consigliabile abilitare MFA negli account con autorizzazioni di tipo proprietario per la sottoscrizione**.  Nella pagina che si apre saranno presenti una descrizione, la procedura di correzione e le risorse interessate. Uscire da questa pagina selezionando la **X** nell'angolo in alto a destra dello schermo.
    1. Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Si tornerà alla pagina Panoramica di Microsoft Defender for Cloud.  Nella pagina principale selezionare **Punteggio di sicurezza** (questo equivale a selezionare Punteggio di sicurezza nel riquadro di spostamento sinistro).
    1. In questo modo si accede alla Dashboard del punteggio di sicurezza.  Inoltre vengono elencati tutti i gruppi di gestione e le sottoscrizioni disponibili.  Selezionare la Sottoscrizione di Azure - Azure Pass - Sponsorizzazione.
    1. Si accede così alla pagina delle raccomandazioni mostrata prima.
    1. Uscire dalla pagina delle raccomandazioni selezionando la **X** nell'angolo in alto a destra dello schermo.
    1. Uscire dalla pagina Secure Score selezionando la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Si tornerà alla pagina Panoramica di Microsoft Defender for Cloud.  Dalla pagina principale selezionare **Conformità alle normative**. (Si noti che questo equivale alla selezione di Raccomandazioni nel riquadro di spostamento sinistro della home page di Microsoft Defender for Cloud).
    1. La pagina della conformità alle normative offre un elenco di controlli di conformità.  Sotto ciascun controllo è riportata una serie di valutazioni che sono basate su Azure Security Benchmark che offre raccomandazioni su come proteggere le soluzioni cloud su Azure.
    1. Selezionare **IM. Identity Management** (Gestione identità) e quindi selezionare **IM-6 Use strong authentication controls** (Usa controlli di autenticazione avanzati).  L'elenco mostra le azioni di responsabilità che il cliente può intraprendere per migliorare il profilo di conformità.
    1. Selezionare la **X** nell'angolo in alto a destra dello schermo per chiudere la pagina e tornare alla pagina della conformità alle normative.
    1. Selezionare la **X** nell'angolo in alto a destra dello schermo per tornare alla pagina della panoramica.

1. Tornare alla home page del portale Azure selezionando **Home** nell'angolo in alto a sinistra della pagina.  Tenere questa scheda del browser a disposizione, perché servirà di nuovo in una demo successiva.

## Verifica

In questa demo è stato presentato Microsoft Defender for Cloud e illustrato come è possibile usare Azure Secure Score per migliorare il comportamento di sicurezza di un'organizzazione.
