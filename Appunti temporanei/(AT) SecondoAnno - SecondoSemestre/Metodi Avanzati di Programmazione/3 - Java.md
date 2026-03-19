# Introduzione
Java è un linguaggio di programmazione orientato agli oggetti e indipendente dalla piattaforma di esecuzione, garantita dal fatto che il codice non dipende dalla macchina fisica o dal sistema operativo specifico, ma viene compilato in un formato intermedio chiamato **bytecode**, il quale può essere poi eseguito su qualunque Virtual Machine compatibile.
A differenza del paradigma procedurale, che descrive i sistemi come un insieme di processi tramite flow-chart e utilizza procedure e funzioni tipiche di linguaggi come C, Basic o Pascal , il mondo a oggetti descrive i sistemi come un insieme di "cose" modellate attraverso gerarchie e dipendenze tra classi. Questo moderno approccio utilizza costrutti basati su dichiarazioni di classi e metodi.
## Il paradigma Object-Oriented 
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

L'ereditarietà è un meccanismo estremamente potente che permette di rappresentare le gerarchie tra classi, consentendo a una determinata classe di ereditare in blocco gli attributi e i metodi di un'altra classe genitore. 

> [!example] Esempio di ereditarietà 
> Riprendendo l'esempio di prima, classi più specifiche come le BMX, le Mountain Bike e le City Bike ereditano tutte le caratteristiche di base di una Bicicletta generica, aggiungendo poi i propri attributi e metodi specializzati. 
> ![[Pasted image 20260319101107.png]]

Per gestire l'organizzazione di progetti complessi, Java permette di strutturare le classi all'interno di specifiche cartelle separate chiamate **package**, le quali supportano la creazione di ulteriori sottocartelle per definire gerarchie annidate. Il percorso completo e sequenziale dei package necessari per individuare univocamente una classe prende il nome formale di **namespace**

> [!example] Rappresentazione grafica di package e namespace sulle biciclette
> ![[Pasted image 20260319101433.png]]
# Codice
## Commenti
Per commentare dentro un codice Java, utilizziamo questi simboli:
```java
/* 
Questo è un commento multi riga, infatti posso anche andare a capo senza farmi problemi.
Ecco qui!
*/

//Questo è un commento per una singola riga
```
Il compilatore Java ignorerà qualunque cosa posto all'interno degli slash per le righe con la prima sintassi, nella seconda soltanto la riga corrente
## Definizione di classi, il main e println()
Per definire una classe in Java usiamo la sintassi **class <nomeclasse\>** 
```java
class HelloWorldApp{
	public static void main(String[] args){
		System.out.println("Ciao mondo!")
	}
}
```

Il main è l'entrypoint di ogni applicazione dove possiamo richiamare altre classi e metodi, in Java deve essere sempre presente all'interno di un applicazione. Come argomento ha sempre `String[] args`, che si riferisce agli argomenti che possiamo passare al main dalla riga di comando quando invochiamo un applicazione Java.

La riga `System.out.println("Ciao mondo!")`è composta da 3 elementi fondamentali:
- `System`, che è una delle librerie **core** di Java
- `out` è un suo attributo (in questo caso un oggetto PrintStream)
- `println` è un metodo della classe PrintStream che permette di scrivere su un dispositivo di output
## Le Variabili 
Le variabili in Java ricoprono il ruolo fondamentale di descrivere lo stato di un oggetto esse possiedono sempre:
- Un tipo;
- Un nome identificativo;
- Un valore coerente con il tipo specificato in fase di dichiarazione.

**Vanno sempre dichiarate**, utilizzando la seguente sintassi:
![[Pasted image 20260319103905.png]]


Nel linguaggio esistono diverse categorie di variabili: 
- Le variabili delle istanze (non statiche), in cui ogni singolo oggetto conserva il suo stato in modo indipendente; 
- Le variabili delle classi (statiche), che risultano condivise e identiche per tutte le istanze di una specifica classe; 
- Le variabili locali, che vengono utilizzate e risultano accessibili esclusivamente all'interno del metodo in cui sono dichiarate; 
- I parametri, che rappresentano i valori passati al momento della chiamata di un metodo 

Per quanto riguarda i nomi identificativi, il linguaggio impone che siano case-sensitive, che inizino rigorosamente con una lettera o con il simbolo \$ e che possano contenere numeri al loro interno, avendo preferibilmente delle nomenclature autoesplicative.
Le convenzioni comunemente accettate prevedono che 
- Le costanti e le variabili statiche debbano essere scritte interamente a lettere maiuscole, 
- Per i nomi composti da più parole si adotta lo stile in cui la prima lettera di ogni nuova parola successiva alla prima viene scritta in maiuscolo.

## Tipi di dato primitivi
Il linguaggio Java definisce a livello nativo una serie di tipi di dato primitivi per ottimizzare la memorizzazione dei valori. 

> [!info] Tabella dei valori primitivi
> ![[Pasted image 20260319104304.png]]
> Quasi tutti i tipi primitivi possiedono uno zero numerico, un carattere nullo o il valore false come impostazione di default, ad eccezione delle variabili locali che risultano prive di tale assegnazione automatica e necessitano pertanto di un'inizializzazione manuale.

Ogni tipo primitivo è inoltre affiancato dalla sua rispettiva classe "wrapper" (la sua rappresentazione ad oggetti come Integer, Long o Boolean). 
### Tipo String
Il tipo String non si tratta di un tipo primitivo ma di un oggetto vero e proprio il cui valore di default risulta essere null. Le stringhe sono istanze immutabili e il linguaggio provvede a creare automaticamente un nuovo oggetto String ogni volta che incontra una sequenza di caratteri racchiusa tra doppi apici.

## I letterali
Il termine letterale (literal) viene utilizzato per indicare i valori espliciti che assegniamo direttamente nel codice alle variabili di tipo primitivo o alle stringhe. 
> [!example] Esempii di literals
> ![[Pasted image 20260319104603.png]]

### Letterali interi
Per quanto riguarda i letterali interi, il compilatore li interpreta sempre come tipo `int` di default, a meno che non venga specificato esplicitamente l'uso del formato long tramite l'aggiunta di una lettera L finale; essi supportano inoltre la scrittura in formati alternativi, potendo essere espressi anche in base esadecimale o binaria.

```java
int n=10; 
long m=1000L;
int h=0xa1; 
int b=0b001101;
```
### Letterali in virgola mobile (o floating point)
I letterali in virgola mobile seguono una logica simile: sono considerati di tipo double per impostazione predefinita, a meno che non si utilizzi la lettera f per forzarne il tipo a float, e supportano l'impiego della notazione scientifica. 
```java
float f=3.14f; 
double d1=134.54 
double d2=1.3454e2 //Notazione scientifica
```
### Letterali caratteri e Stringhe (character e String)
i character possono contenere qualunque carattere Unicode a 16-bit racchiuso tra singoli apici, mentre le stringhe impiegano i doppi apici.

```java
Per char vale questo -> 'c'
Per String vale questo -> "testo di esempio"
```
All'interno dei testi è inoltre possibile avvalersi di speciali sequenze di escape per rappresentare agevolmente caratteri di controllo come il line feed, la tabulazione oppure per visualizzare simboli specifici come il doppio apice, il singolo apice e il backslash

```java
\n, \r, \f, \b: line feed, carriage return, form feed, backspace

\t: tab

\’’, \’, \\: doppio apice, singolo apice, backslash
```
## Array
L'array è un **oggetto** che contiene un numero finito di oggetti (o tipi primitivi) dello stesso tipo.
Ha una lunghezza fissa definita al momento della creazione, ogni suo elemento viene chiamato **elemento** ed è possibile accederne con l'indice
```java
Dichiarazione di un array: float[] v;
Inizializzazione: float[] v=new float[100];
Assegnazione: v[3]=1.3;
Dichiarazione e inizializzazione contemporanea: int[] a = {10, 34, 21}; 
Array multidimensionali: double[][] m; 
```

Quando si dichiara un array inizializzato, questo avrà dimensioni uguali a quanti elementi son stati inizializzati
### Copia di un array
La classe `System` mette a disposizione il metodo `arraycopy` per copiare degli array
```java
arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
```

È composto da:
- **src**: array sorgente
- **srcPos**: posizione di inizio in src
- **dest**: array di destinazione
- **destPos**: posizione di inizio in dest
- **length**: numero di elementi da copiare

> [!example] Esempio di copia di array
> ![[Pasted image 20260319112406.png]]
### Manipolazione di array
La classe Arrays mette a disposizione un serie di metodi statici per manipolare gli array, la documentazione è presente [qui](http://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html), ma riportiamo comunque alcuni metodi come:
- **copyOfRange**: è la copia di array
- **fill**: riempimento di array
- **equals**: confronto tra due array
- **search**: ricerca di un elemento 
- **sort**: ordinamento crescente
## Operatori
Gli operatori eseguono delle operazioni da 1 a 3 argomenti e restituiscono un valore. Gli operatori con stessa priorità son eseguiti da sinistra verso destra, **tranne per le operazioni di assegnamento**

> [!info] Tabella operatori 
> ![[Pasted image 20260319112938.png]]
### Operatori aritmetici