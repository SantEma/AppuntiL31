## Dal cosa al come
La scienza del software studia il passaggio dal "cosa" (quello che il programmatore pensa, quindi il problema) al "come" (come viene eseguito dalla macchina)

L'estremo "cosa" raccoglie gli obbiettivi, i desideri e i bisogni dell'utente, la sua conoscenza del dominio del problema, tutti espressi in linguaggio naturale
L'estremo "come" è l'hardware che può raggiungere quegli obbiettivi e soddisfare i bisogni e i desideri in modo estremamente procedurale e rigorosamente sequenziale

La scienza della programmazione ha esplorato molti punti dello spettro "what-how", creando nella diversi **paradigmi di programmazione**.
## Paradigma
> [!info] Paradigma
> Complesso di regole metodologiche, modelli esplicativi, criteri di soluzione di problemi che caratterizza una comunità di scienziati in una fase determinata dell’evoluzione storica della loro disciplina

> [!info] Paradigma di programmazione
> Collezioni di modelli concettuali che insieme plasmano il processo di analisi, progettazione e sviluppo di un programma

Questi modelli concettuali “strutturano” il pensiero in quanto determinano la forma di programmi validi, influenzano il modo in cui pensiamo e formuliamo le soluzioni, arrivando a condizionare perfino la possibilità di trovare una soluzione.

Un paradigma cambia fondamentalmente il modo in cui guardiamo ai problemi incontrati nel passato, ci deve dare un nuovo schema per pensare ai problemi futuri e cambia le nostre priorità, le nostre idee su quanto merita attenzione e su cosa sia importante, cambiando effettivamente punto di vista

Un nuovo paradigma è spesso **introdotto per risolvere un particolare problema**, ma si rivela poi adatto per altri. Per un problema degli anni 60, ci si è accorti che nessun paradigma esistente non era effettivamente utilizzabile ed è stato inventato il **paradigma ad oggetti (object oriented)**

Nel senso della macchina di Turing, tutti **i linguaggi di programmazione più comuni sono universali**, tuttavia ogni linguaggio di programmazione si basa, o meglio supporta, un particolare paradigma, fornendo:
- Le primitive di quel paradigma
- I metodi di composizione di quel paradigma
- Un linguaggio utente appropriato che rende chiari i programmi scritti secondo quel paradigma
- Un'esecuzione efficiente dei programmi scritti nel linguaggio scelto al punto precedente

Per esempio il C è un linguaggio basato sul **paradigma imperativo**
### Rapporto Paradigma-Linguaggi
I linguaggi di programmazione sono dotati di opportuni **costrutti linguistici** che riflettono i modelli concettuali di un paradigma, al fine di facilitare l’espressione di una soluzione definita attraverso i modelli concettuali del paradigma. I linguaggi di programmazione possono supportare **più di un paradigma**.
#### Categorie di paradigmi
1. Paradigmi che supportano tecniche di programmazione di basso livello (assembly)
2. Paradigmi che supportano metodi di progettazione di algoritmi (e.g., divide-et-impera, programmazione dinamica)
3. Paradigmi che supportano gli approcci di alto livello alla programmazione (e.g., paradigma funzionale e quello basato su regole)
#### Approccio dei paradigmi al problem solving
I paradigmi che supportano la programmazione ad alto livello possono essere raggruppati in base al loro approccio alla soluzione dei problemi.
- **Approccio operazionale:** descrive per passi **COME** costruire una soluzione.
- **Approccio dimostrazionale**: è una variante del precedente che illustra la soluzione in modo operativo per esempi specifici e lascia al sistema il compito di generalizzare queste soluzione di esempi ad altri casi.
- **Approccio definizionale**: esso stabilisce delle proprietà della soluzione in modo da vincolarla senza per questo descrivere come viene calcolata.
##### Approccio operazionale
Questo approccio è il pilastro della programmazione imperativa e qui il programmatore agisce come un coordinatore che impartisce ordini sequenziali. **Il focus è sul mutamento di stato del sistema (le istruzioni modificano dei valori sulla memoria) attraverso istruzioni precise**.
Il concetto chiave di questo approccio è il programmatore controlla quel **flusso di controllo** (cicli for, istruzioni if, assegnazione di variabili).
##### Approccio dimostrazionale
È una variante dell’operazionale, ma più “guidata dagli esempi”, come esempi concreti di input/output. Il sistema generalizza automaticamente la soluzione, quindi tipico di contesti in cui si “insegna” al sistema cosa fare (come il Machine Learning).
Il concetto chiave è che **non scrivi l’algoritmo, mostri cosa deve fare**
##### Approccio definizionale
Si descrive **COSA** deve essere vero, non come ottenerlo, specificando proprietà, vincoli o relazioni. Il sistema trova autonomamente una soluzione che le soddisfi. Il concetto chiave è **che si descriva il risultato ma non il suo procedimento**
![[Pasted image 20260304121723.png]]
#### La scienza della programmazione
Chi studia questa scienza si deve occupare di diversi campi:
- **I metodi di analisi dei problemi**, che consentono di passare da formulazioni spesso imprecise ed ambigue di un problema, a specifiche espresse in un qualche linguaggio formale
- **Le tecniche di trasformazione dei programmi**, o tecniche di programmazione, che trasformano la specifica di un problema in un programma che lo risolve.
- **I metodi di verifica della correttezza**, che affrontano il problema di verificare la terminazione dei programmi e la rispondenza alle specifiche date
- **La teoria della complessità computazionale**, che studia l’efficienza delle soluzioni trovate
- **La teoria dei linguaggi formali e traduttori**, che studia gli strumenti utilizzabili per comunicare un algoritmo ad un elaboratore.
#### Approccio multi-paradimatico
Nessun singolo paradigma è appropriato per tutti i problemi, le applicazioni complesse necessitano l’adozione di più paradigmi di programmazione.
Ogni singolo paradigma di programmazione è caratterizzato da:
- Un diverso **potere di elisione**, cioè capacità di esprimere qualcosa in modo conciso (compattare per esempio il codice usando un paradigma rispetto ad un altro)
- Una diversa **invarianza rispetto ai cambiamenti** apportati nella strategia di soluzione di un problema (stesso paradigma per modifiche successive)

Occorre sempre bilanciare i costi dovuti all'uniformità di paradigma con i costi determinati dall'uso di diversi paradigmi per un medesimo problema. I costi che si riscontrano sono:
- Costi iniziali di apprendimento (il programmatore deve essere formato)
- Costi di debugging
- Costi di variazione dovuti all'evoluzione del programma
- Costi di esecuzione dell’applicazione (un paradigma sbagliato potrebbe portare ad un esecuzione più lenta per un codice più pesante)
#### Classificazioni di applicazioni software rispetto alla natura degli elementi
- **Applicazioni orientate alla realizzazione di funzioni**: la complessità prevalente riguarda le funzioni da realizzare (come i programmi utilizzati dagli utenti nella quotidianità).
- **Applicazioni orientate alla gestione dei dati**: l'aspetto prevalente è rappresentato dai dati che vengono memorizzati, ricercati e modificati, e che costituiscono il patrimonio informativo di una organizzazione.
- **Applicazioni orientate al controllo**: la complessità prevalente del sistema riguarda il controllo delle attività che si sincronizzano e cooperano durante l’evoluzione del sistema.
#### Classificazioni di applicazioni software rispetto al flusso di esecuzione delle attività
- **Applicazioni sequenziali**: sono caratterizzate da un unico flusso di controllo che governa l’evoluzione dell’applicazione. Queste sono le applicazioni più tradizionali, e vengono spesso adottate come riferimento per i metodi e le tecniche di base per la progettazione.
- **Applicazioni concorrenti**: sono caratterizzate dal fatto che le varie attività che compongono il sistema non hanno una natura inerentemente sequenziale, ma necessitano di meccanismi di sincronizzazione e comunicazione.
- **Applicazioni dipendenti dal tempo**: sono influenzate da vincoli temporali riguardanti sia la velocità di esecuzione delle attività sia la necessità di sincronizzare le attività stesse.
## Paradigmi operazionali
Nei paradigmi operazionali è difficile stabilire se l’insieme dei valori calcolati operativamente è proprio l’insieme dei valori soluzione. Le tecniche di verifica e di debugging cercano di superare questo problema di programmazione e spesso ci si accontenta di stabilire che i due insiemi siano “sufficientemente vicini”, ovvero indistinguibili per la sottoclasse attesa di problemi effettivi
### Side-effecting
I paradigmi operazionali si distinguono in:
- **Side-effecting**: procedono modificando ripetutamente la loro rappresentazione dei dati (le variabili sono legate a locazioni di memoria), come il C
- **Non-side-effecting**: procedono creando continuamente nuovi dati. Questi paradigmi includono quelli che tradizionalmente sono detti **funzionali** (si da ad una funzione dei valori e lei produce un risultato, non modificando valori esistenti ma calcolandone altri creando copie eventuali). Una volta allocato in memoria, un dato non può più essere modificato. Una "funzione pura" prende in input dei valori e ne restituisce di nuovi, senza mai intaccare gli originali né alterare lo stato esterno.

I paradigmi operazionali “side-effecting” si distinguono in:
- Imperativi
- Orientati agli oggetti
### Sequenziale vs Concorrente
Per ognuno dei paradigmi visti precedentemente possiamo distinguere due versioni:
- **Sequenziale**: il flusso di controllo è unico
- **Concorrente o parallelo**: più flussi di controllo sono ammessi.
## Astrazione nella progettazione
> [!info] Definizione di astrazione
> L'astrazione, in ambito scientifico, significa cambiare la rappresentazione di un problema, "trascinando via" un concetto, una idea, un principio da una realtà concreta.

L’obiettivo del cambio di rappresentazione è quello di concentrarsi su aspetti rilevanti dimenticando gli elementi secondari.
Non si tratta di omettere parti della rappresentazione di un problema, ma di riformulare lo stesso concentrando l’attenzione su idee generali piuttosto che su manifestazioni specifiche di quelle idee, tenendo conto della prospettiva di un osservatore.
![[Pasted image 20260304130450.png]]
L’astrazione si focalizza sulle caratteristiche essenziali di un oggetto, rispetto alla prospettiva di colui che osserva.
### Astrazione: processo o entità
Il termine astrazione sotto-intende
- **Un processo**: l’estrazione delle informazioni essenziali e rilevanti per un particolare scopo, ignorando il resto dell’informazione
- **Una entità**: una descrizione semplificata di un sistema che enfatizza alcuni dei dettagli o proprietà trascurandone altri

Entrambe le viste sono valide e di fatto necessarie.

Si suppone che si voglia controllare il traffico aereo, avremo due tipologie di dettagli:
- Dettagli **essenziali**: posizione del velivolo, velocità, etc.
- Dettagli **irrilevanti**: colore, nomi dei passeggeri, etc.

Nel quotidiano il principio di astrazione è costantemente applicato ogni qualvolta utilizziamo uno strumento senza per questo sapere come è realizzato.

