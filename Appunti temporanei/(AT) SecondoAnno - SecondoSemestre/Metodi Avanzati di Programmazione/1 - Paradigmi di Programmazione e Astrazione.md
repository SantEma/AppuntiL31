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
## Rapporto Paradigma-Linguaggi
I linguaggi di programmazione sono dotati di opportuni **costrutti linguistici** che riflettono i modelli concettuali di un paradigma, al fine di facilitare l’espressione di una soluzione definita attraverso i modelli concettuali del paradigma. I linguaggi di programmazione possono supportare **più di un paradigma**.
### Categorie di paradigmi
1. Paradigmi che supportano tecniche di programmazione di basso livello (assembly)
2. Paradigmi che supportano metodi di progettazione di algoritmi (e.g., divide-et-impera, programmazione dinamica)
3. Paradigmi che supportano gli approcci di alto livello alla programmazione (e.g., paradigma funzionale e quello basato su regole)
### Approccio dei paradigmi al problem solving
I paradigmi che supportano la programmazione ad alto livello possono essere raggruppati in base al loro approccio alla soluzione dei problemi.
- **Approccio operazionale:** descrive per passi **COME** costruire una soluzione.
- **Approccio dimostrazionale**: è una variante del precedente che illustra la soluzione in modo operativo per esempi specifici e lascia al sistema il compito di generalizzare queste soluzione di esempi ad altri casi.
- **Approccio definizionale**: esso stabilisce delle proprietà della soluzione in modo da vincolarla senza per questo descrivere come viene calcolata.
#### Approccio operazionale
Questo approccio è il pilastro della programmazione imperativa e qui il programmatore agisce come un coordinatore che impartisce ordini sequenziali. **Il focus è sul mutamento di stato del sistema (le istruzioni modificano dei valori sulla memoria) attraverso istruzioni precise**.
Il concetto chiave di questo approccio è il programmatore controlla quel **flusso di controllo** (cicli for, istruzioni if, assegnazione di variabili).
#### Approccio dimostrazionale
È una variante dell’operazionale, ma più “guidata dagli esempi”, come esempi concreti di input/output. Il sistema generalizza automaticamente la soluzione, quindi tipico di contesti in cui si “insegna” al sistema cosa fare (come il Machine Learning).
Il concetto chiave è che **non scrivi l’algoritmo, mostri cosa deve fare**
#### Approccio definizionale
Si descrive **COSA** deve essere vero, non come ottenerlo, specificando proprietà, vincoli o relazioni. Il sistema trova autonomamente una soluzione che le soddisfi. Il concetto chiave è **che si descriva il risultato ma non il suo procedimento**
![[Pasted image 20260304121723.png]]