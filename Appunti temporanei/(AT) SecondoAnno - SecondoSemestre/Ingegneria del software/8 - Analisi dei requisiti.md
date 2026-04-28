# Modello di dominio
Il modello di dominio è utile per avere una base solida della **business logic** e per rappresentarlo si utilizza un **diagramma delle classi con prospettiva concettuale**, esso rappresenta in modo visivo i concetti caratteristici del dominio che stiamo studiando.
Inoltre questo modello è **indipendente dal software** ed è chiamato anche **modello concettuale** (già visto e usato nei concetti di Basi di Dati).
## Classe come concetto
Una classe rappresenta un concetto ben definito che permette l'astrazione di istanze simili.
![[Pasted image 20260424095750.png]]
Le proprietà della classe sono gli **attributi** e le **associazioni**.
### Attributi e Associazioni
Un **attributo** è una proprietà rilevante di un concetto (o classe) che contiene un valore per ogni oggetto.
![[Pasted image 20260424095913.png]]

Un'**associazione** è una relazione rivelante tra due concetti (o classi) ed è etichettata, come ad esempio `classe1 verbo classe2` quindi *Persona **lavora per** Dipartimento*.
Le associazioni sono generalmente bidirezionali, anche se generalmente vengono lette da sinistra a destra o dall'altro al basso.
Inoltre le associazioni possono essere anche **ricorsive**, come una classe di nome *"cartella"* che *contiene* altre classi cartella.
#### Legami delle associazioni
Un'associazione può rappresentare in modo più preciso anche un **gruppo di legami** tra gli oggetti delle classi associate:
![[Pasted image 20260424100339.png]]
![[Pasted image 20260424100354.png]]
### Classi associative e attributi di legame
Le classi nate dalle associazioni sono utilizzate per modellare proprietà intrinseche nella relazione delle due classi coinvolte. Un attributo di una classe associativa contiene un **valore per ogni legame** e per definizione di Basi di Dati si ricorda che nascono molto spesso dalle relazioni di tipo **molti-a-molti**.
![[Pasted image 20260424101220.png]]
## Ruoli
Un'alternativa grafica per non inserire l'etichetta nell'associazione è quella di definire dei **ruoli**. I ruoli rappresentano il nome della proprietà e sono posti alla fine della linea di congiunzione.
I ruoli hanno gran efficacia nelle associazioni tra oggetti della stessa classe, come l'esempio precedente:![[Pasted image 20260424101505.png]]
L'aggregazione del contenuto e del contenitore viene rappresentato anch'esso graficamente tramite il **daimo**, il quale può essere **vuoto** o **pieno**:
![[Pasted image 20260424101826.png]]
La **composizione** è una forma definita **forte** dell'aggregazione, poiché stiamo definendo che:
- la parte componente non può esistere senza il contenitore
- la parte componente può appartenere solo ad un unico oggetto contenitore
La composizione è una forma definita **debole** invece quando l'oggetto può esistere anche senza un altra classe.

In lettura queste due parti si leggono con ***è parte di*** o al contrario ***è composto da***.
## Generalizzazione
L'associazione tra classi viene definita sotto il concetto di ***è un tipo di*** o al contrario come ***può essere un***. 
Questo concetto è utilizzato per definire le **tassonomie** di classi, così possiamo dividere le classi in **superclasse** e le loro rispettive **sottoclassi**.
![[Pasted image 20260424102403.png]]
Ad esempio *Docente* è una classe specializzata di *Persona* che è una classe generale.
Per definizione, ogni oggetto di una sottoclasse è anche un oggetto della sua superclasse.

>[!WARNING] Attenzione
>Non tutti gli attributi sono generali per tutte le sottoclassi di una superclasse.

Per rappresentare graficamente una bozza degli studi di dominio si usa una **lavagna condivisa in scrittura** così da condividere questi dettagli. Questa lavagna virtuale è integrata sulle piattaforme di meeting (come quella su teams). Altrimenti Claude IA può aiutare a dare una base di partenza.
# I requisiti
Un requisito è una caratteristica o condizione che un sistema è tenuto a rispettare.
La formulazione dei requisiti chiarisce il modo in cui i bisogni dei clienti o degli utenti dovranno essere soddisfatti dai progettisti.
L'insieme dei requisiti è noto come **spazio delle soluzioni ammissibili**.

I requisiti si dividono i due tipi:
- **Requisiti funzionali** o **features**
- **Requisiti non funzionali**:
	- affidabilità
	- efficienza
	- usabilità
	- manutenibilità
	- portabilità

I requisiti devono essere espressi in maniera corretta, dettagliata e chiara nel modo più possibile ed in più ogni metodo implementato per la soddisfazione di questi requisiti devono essere testabili.

Lo scambio dei requisiti fino al prodotto finito avviene nel seguente schema:
![[Pasted image 20260424111227.png]]
Sebbene lo schema sia tipico di altri contesti ingegneristici, l’applicazione nel campo del software è spesso problematica.
## Problemi nella raccolta dei requisiti
**Idealmente** si dovrebbero seguire questi passaggi semplici:
- il committente comunica i requisiti alla partenza del progetto 
- il compito degli analisti è soltanto quello di acquisirli e di comprenderli

**Concettualmente e realmente** però non avviene mai questo, poiché il cliente non conosce bene i termini da utilizzare per far comprendere appieno all'analista cosa raccogliere come dati, ma può essere astratto, confuso e non preciso o diverso da come se lo aspettava il cliente a prodotto aggiornato nello sviluppo.
Quindi si eseguiranno più step nella scoperta dei dati e specialmente durante l'evoluzione del progetto, poiché nasceranno più requisiti:
- i requisiti possono nascere, o cambiare, anche dopo il raggiungimento dell'accordo (o la stipula del contratto), mentre sono in corso le attività di realizzazione
- fattori che possono determinare un cambiamento di requisiti: 
	- innovazioni legislative 
	- cambiamenti negli scenari di mercato o nelle strategie aziendali, 
	- nuove opportunità e bisogni 
	- scoperta di errori
## Ingegneria dei requisiti
Esistono varie tecniche per:
- Scoprire i requisiti
- Specificare i requisiti
- Validare i requisiti
- Gestire dei cambiamenti
Queste tecniche sono notate come l'**ingegneria dei requisiti**.
### Scoprire i requisiti
Si creano delle **interviste** fisicamente tra analista e cliente o tramite **workshop** dove molti membri del team parlano con molti clienti coinvolti.
La figura che identifica gli interlocutori è chiamato **stakeholder**.
Si generano **prototipi UI** da far vedere al cliente per poter continuare a procedere lo sviluppo software e avviene anche il recupero e l'analisi della documentazione da sistemi esterni.
### SRS
La specifica dei requisiti o **SRS** avviene tramite la sottoscrizione di **documenti**, la cui struttura può dettata dagli standard come *IEEE Std 830-1998* ecc...
Il documento è suddiviso in varie parti:
1. **Introduzione**
2. **Descrizione**
3. **Requisiti specifici**
	1. Requisiti funzionali
	2. Requisiti non funzionali
4. Appendici
5. Indice
## Stile di descrizione dei requisiti
I requisiti si descrivono tramite le:
- **Proposizioni**, sia funzionali che non
- **Casi d'uso**, usati solo per quelli funzionali
- **User stories**, usati solo per requisiti funzionali nello sviluppo agile
### Casi d'uso e user stories
Essi rappresentano una funzionalità che il sistema deve offrire ai suoi **attori**.
I casi d'uso differiscono dalle user stories dal **metodo in cui sono descritti**:
- User story sono descritte con brevi annotazioni da post-it
- Casi d'uso sono descritti tramite la narrazione delle interazioni tipiche tra attori e sistema

Gli **attori** è il ruolo degli utilizzatori del prodotto, che possono essere utenti del prodotto finale o utilizzatori di mezzo, o possono anche essere qualcuno che svolge interazioni con il sistema.
L'attore è definito **esterno al sistema** e possono essere:
- persone fisiche
- sistemi che lavorano esternamente al progetto (come il sistema di contabilità)
- dispositivi hardware esterni
### Diagramma di contesto
Il diagramma di contesto ci permette di definire in modo grafico i confini del sistema e chiarisce anche le entità che devono interagire con quest'ultimo.
![[Pasted image 20260424113447.png]]
![[Pasted image 20260424113507.png]]
## Descrizione caso d'uso
La descrizione del caso d'uso si divide in **Formato breve** [Da finire da pag 16 a 26]