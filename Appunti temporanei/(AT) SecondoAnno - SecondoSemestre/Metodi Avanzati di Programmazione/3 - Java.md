# Introduzione
Java è un linguaggio di programmazione orientato agli oggetti e indipendente dalla piattaforma di esecuzione, garantita dal fatto che il codice non dipende dalla macchina fisica o dal sistema operativo specifico, ma viene compilato in un formato intermedio chiamato **bytecode**, il quale può essere poi eseguito su qualunque Virtual Machine compatibile.
A differenza del paradigma procedurale, che descrive i sistemi come un insieme di processi tramite flow-chart e utilizza procedure e funzioni tipiche di linguaggi come C, Basic o Pascal , il mondo a oggetti descrive i sistemi come un insieme di "cose" modellate attraverso gerarchie e dipendenze tra classi. Questo moderno approccio utilizza costrutti basati su dichiarazioni di classi e metodi.

## Il paradigma Object-Oriented e i suoi vantaggi
Riprendendo la definizione del paradigma orientato agli oggetti, ogni singola entità del mondo reale è considerata un oggetto caratterizzato da uno stato e da un funzionamento specifico. 

> [!example] Esempio di paradigma OO nel mondo reale
> Ad esempio, lo stato di una bicicletta è definito da valori come la marcia corrente e la velocità di marcia, mentre il suo funzionamento comprende azioni concrete come il cambio della marcia o la frenata
> 

Nel contesto del software, gli oggetti reali vengono modellati memorizzando il loro stato all'interno di **fields** (ovvero variabili o attributi) ed esponendo il loro funzionamento all'esterno attraverso **methods** (funzioni o metodi), che hanno il compito cruciale di modificare lo stato dell'oggetto agendo in modo mirato sui suoi attributi. 

L'adozione di questo paradigma porta numerosi e importanti vantaggi: 
- Favorisce la modularità, permettendo di gestire il codice di ogni oggetto in modo separato e indipendente; 
- Garantisce l'information-hiding, nascondendo i dettagli implementativi e permettendo l'interazione solo tramite metodi prestabiliti; 
- Facilita il riutilizzo del codice, consentendo di estendere o sostituire facilmente oggetti scritti da altri sviluppatori.

## Classi, Ereditarietà e Package
Poiché nel mondo reale moltissimi oggetti condividono delle caratteristiche intrinseche, nella programmazione essi vengono raggruppati in **classi** che ne definiscono il funzionamento e le peculiarità comuni, rendendo quindi i singoli oggetti istanze fisiche e operative di tali classi.
> [!example] Esempio di classe
> ![[Pasted image 20260319101544.png]]

L'ereditarietà è un meccanismo estremamente potente che permette di rappresentare le gerarchie tassonomiche, consentendo a una determinata classe di ereditare in blocco gli attributi e i metodi di un'altra classe genitore. 

> [!example] Esempio di ereditarietà
> 
> Riprendendo l'esempio di prima, classi più specifiche come le BMX, le Mountain Bike e le City Bike ereditano tutte le caratteristiche di base di una Bicicletta generica, aggiungendo poi i propri attributi e metodi specializzati. 
> ![[Pasted image 20260319101107.png]]

Per gestire l'organizzazione di progetti complessi, Java permette di strutturare le classi all'interno di specifiche cartelle separate chiamate **package**, le quali supportano la creazione di ulteriori sottocartelle per definire gerarchie annidate. Il percorso completo e sequenziale dei package necessari per individuare univocamente una classe prende il nome formale di **namespace**

> [!example] Rappresentazione grafica di package e namespace sulle biciclette
> ![[Pasted image 20260319101433.png]]


## Le Variabili in JAVA e le relative convenzioni
Le variabili in Java ricoprono il ruolo fondamentale di descrivere lo stato di un oggetto; esse possiedono sempre un tipo, un nome identificativo e memorizzano un valore coerente con il tipo specificato in fase di dichiarazione[: 8, 9, 10]. È opportuno prestare attenzione alla terminologia, poiché in Java i termini "variabile" e "field" (o attributo) vengono spesso utilizzati in maniera interscambiabile, generando a volte una lieve confusione[: 11]. Nel linguaggio esistono diverse categorie di variabili: le variabili delle istanze (non statiche), in cui ogni singolo oggetto conserva il suo stato in modo indipendente; le variabili delle classi (statiche), che risultano condivise e identiche per tutte le istanze di una specifica classe; le variabili locali, che vengono utilizzate e risultano accessibili esclusivamente all'interno del metodo in cui sono dichiarate; e infine i parametri, che rappresentano i valori passati al momento della chiamata di un metodo[: 15, 16, 17, 18, 19]. Per quanto riguarda i nomi identificativi, il linguaggio impone che siano case-sensitive, che inizino rigorosamente con una lettera o con il simbolo \$ e che possano contenere numeri al loro interno, incoraggiando comunque l'adozione di nomenclature che siano sempre chiare e auto-esplicative[: 22, 23, 24, 25]. Le convenzioni comunemente accettate prevedono che le costanti e le variabili statiche debbano essere scritte interamente a lettere maiuscole, mentre per i nomi composti da più parole si adotta lo stile in cui la prima lettera di ogni nuova parola successiva alla prima viene scritta in maiuscolo[: 27, 28]. È inoltre una regola sintattica imesempioprescindibile che in Java tutte le variabili debbano essere esplicitamente dichiarate prima di poter essere utilizzate[: 31].

## Tipi di dato primitivi e il tipo String
Il linguaggio Java definisce a livello nativo una serie di tipi di dato primitivi per ottimizzare la memorizzazione dei valori. Per la gestione dei numeri interi troviamo il tipo byte a 8-bit con un range di valori $[-128, 127]$, il tipo short a 16-bit, il diffusissimo tipo int a 32-bit e il capiente tipo long a 64-bit[: 36]. Per le operazioni che richiedono numeri in virgola mobile, basati sullo standard IEEE 754, il linguaggio mette a disposizione il tipo float a 32-bit e il tipo double a 64-bit[: 36]. L'elenco si conclude con il tipo boolean per gestire i valori logici true e false, e il tipo char, che serve a rappresentare un singolo carattere Unicode a 16-bit[: 36]. Quasi tutti i tipi primitivi possiedono uno zero numerico, un carattere nullo o il valore false come impostazione di default, ad eccezione delle variabili locali che risultano prive di tale assegnazione automatica e necessitano pertanto di un'inizializzazione manuale[: 36, 38]. Ogni tipo primitivo è inoltre affiancato dalla sua rispettiva classe "wrapper" (la sua rappresentazione ad oggetti come Integer, Long o Boolean)[: 37]. Il tipo String costituisce un'eccezione notevole: non si tratta di un tipo primitivo ma di un oggetto vero e proprio il cui valore di default risulta essere null[: 46, 47]. Le stringhe sono istanze immutabili e il linguaggio provvede a creare automaticamente un nuovo oggetto String ogni volta che incontra una sequenza di caratteri racchiusa tra doppi apici[: 40, 41, 42, 43, 45].

## I letterali
Il termine letterale (literal) viene utilizzato per indicare i valori espliciti che assegniamo direttamente nel codice alle variabili di tipo primitivo o alle stringhe[: 49, 50]. Per quanto riguarda i letterali interi, il compilatore li interpreta sempre come tipo int di default, a meno che non venga specificato esplicitamente l'uso del formato long tramite l'aggiunta di una lettera L finale; essi supportano inoltre la scrittura in formati alternativi, potendo essere espressi anche in base esadecimale o binaria[: 57, 58, 59, 60]. I letterali in virgola mobile seguono una logica simile: sono considerati di tipo double per impostazione predefinita, a meno che non si utilizzi la lettera f per forzarne il tipo a float, e supportano l'impiego della notazione scientifica[: 62, 63, 64, 65]. Concludendo la panoramica sui letterali, i character possono contenere qualunque carattere Unicode a 16-bit racchiuso tra singoli apici, mentre le stringhe impiegano i doppi apici[: 69, 70, 71]. All'interno dei testi è inoltre possibile avvalersi di speciali sequenze di escape per rappresentare agevolmente caratteri di controllo come il line feed, la tabulazione oppure per visualizzare simboli specifici come il doppio apice, il singolo apice e il backslash[: 72, 74, 75, 76].