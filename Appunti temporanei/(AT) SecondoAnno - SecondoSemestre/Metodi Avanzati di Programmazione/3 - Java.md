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

> [!example] Esempio di definizione classe
> ```java
> class HelloWorldApp{
> 	public static void main(String[] args){
> 		System.out.println("Ciao mondo!")
> 	}
> }
> ```

Il main è l'entrypoint di ogni applicazione dove possiamo richiamare altre classi e metodi, in Java deve essere sempre presente all'interno di un applicazione. Come argomento ha sempre `String[] args`, che si riferisce agli argomenti che possiamo passare al main dalla riga di comando quando invochiamo un applicazione Java.

La riga `System.out.println("Ciao mondo!")`è composta da 3 elementi fondamentali:
- `System`, che è una delle librerie **core** di Java
- `out` è un suo attributo (in questo caso un oggetto PrintStream)
- `println` è un metodo della classe PrintStream che permette di scrivere su un dispositivo di output
## Le variabili 
Le variabili in Java ricoprono il ruolo fondamentale di **descrivere lo stato di un oggetto**, ed esse possiedono sempre:
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
Il termine letterale (**literal**) viene utilizzato per indicare i **valori espliciti che assegniamo direttamente nel codice alle variabili di tipo primitivo o alle stringhe**. 
> [!example] Esempii di literals
> ![[Pasted image 20260319104603.png]]
### Letterali interi
Per quanto riguarda i letterali interi, il compilatore li interpreta sempre come tipo `int` di default, a meno che non venga specificato esplicitamente l'uso del formato long tramite l'aggiunta di una lettera L finale; essi supportano inoltre la scrittura in formati alternativi, potendo essere espressi anche in base esadecimale o binaria.

> [!example] Esempio di letterali interi
> ```java
> int n=10; 
> long m=1000L;
> int h=0xa1; 
> int b=0b001101;
> ```
### Letterali in virgola mobile (o floating point)
I letterali in virgola mobile seguono una logica simile: sono considerati di tipo double per impostazione predefinita, a meno che non si utilizzi la lettera f per forzarne il tipo a float, e supportano l'impiego della notazione scientifica. 

> [!example] Esempio di letterali float
> ```java
> float f=3.14f; 
> double d1=134.54 
> double d2=1.3454e2 //Notazione scientifica
> ```
### Letterali caratteri e Stringhe (character e String)
i character possono contenere qualunque carattere Unicode a 16-bit racchiuso tra singoli apici, mentre le stringhe impiegano i doppi apici.

> [!example] Esempio di letterali caratteri e stringhe
> ```java
> Per char vale questo -> 'c'
> Per String vale questo -> "testo di esempio"
> ```

All'interno dei testi è inoltre possibile avvalersi di speciali sequenze di escape per rappresentare agevolmente caratteri di controllo come il line feed, la tabulazione oppure per visualizzare simboli specifici come il doppio apice, il singolo apice e il backslash

> [!info] Lista di sequenze escape
> ```java
> \n, \r, \f, \b: line feed, carriage return, form feed, backspace
> \t: tab
> \’’, \’, \\: doppio apice, singolo apice, backslash
> ```
## Array
L'array è un **oggetto** che contiene un numero finito di oggetti (o tipi primitivi) dello stesso tipo.
Ha una lunghezza fissa definita al momento della creazione, ogni suo elemento viene chiamato **elemento** ed è possibile accederne con l'indice

> [!example] Esempio di vari tipi di array
> ```java
> Dichiarazione di un array: float[] v;
> Inizializzazione: float[] v=new float[100];
> Assegnazione: v[3]=1.3;
> Dichiarazione e inizializzazione contemporanea: int[] a = {10, 34, 21}; 
> Array multidimensionali: double[][] m; 
> ```

Quando si dichiara un array inizializzato, questo avrà dimensioni uguali a quanti elementi son stati inizializzati
### Copia di un array
La classe `System` mette a disposizione il metodo `arraycopy` per copiare degli array

> [!info] Metodo per la copia di un array
> ```java
> arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
> ```
> 
> È composto da:
> - **src**: array sorgente;
> - **srcPos**: posizione di inizio in src;
> - **dest**: array di destinazione;
> - **destPos**: posizione di inizio in dest;
> - **length**: numero di elementi da copiare;
> 

> [!example] Esempio di copia di array
> ![[Pasted image 20260319112406.png]]
### Manipolazione di array
La classe Arrays mette a disposizione un serie di metodi statici per manipolare gli array, la documentazione è presente [qui](http://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html), ma riportiamo comunque alcuni metodi come:
- **copyOfRange**: è la copia di array;
- **fill**: riempimento di array;
- **equals**: confronto tra due array;
- **search**: ricerca di un elemento;
- **sort**: ordinamento crescente;
## Operatori
Gli operatori eseguono delle operazioni da 1 a 3 argomenti e restituiscono un valore. Gli operatori con stessa priorità son eseguiti da sinistra verso destra, **tranne per le operazioni di assegnamento**
> [!info] Tabella operatori 
> ![[Pasted image 20260319112938.png]]

Alcune considerazioni da fare sono:
- **unary**: permette di negare un numero binario;
- **shift**: shifta i bit in un numero
- **relational**: mettono in relazione due 
- **equality**: i doppi uguale son particolari, con i tipi primitivi funzionano nella classica maniera, mentre nel confronto di oggetti funzionano solo se questi ultimi hanno lo stesso OID (Object ID)
### Operatori aritmetici
> [!info] Tabella degli operatori aritmetici
> ![[Pasted image 20260319113654.png]]

È possibile combinare assegnazione ed operatori aritmetici, per esempio:
```java
x += 1; è equivalente a x = x + 1; 
x *= 2; è equivalente a x = x * 2;
```
L'operatore `+` può essere utilizzato per concatenare le stringhe:
```java
String a=‘’Hello ‘’; String b=‘’ world!’’; String msg = a + b; (‘’Hello world!’’)
```
### Operatori unari
> [!info] Tabella deglio operatori unari
> ![[Pasted image 20260319113859.png]]
### Operatori uguaglianza e relazionali

| **Operatore** | Nome                |
| ------------- | ------------------- |
| ==            | uguale a            |
| !=            | diverso da          |
| >             | maggiore di         |
| >=            | maggiore o uguale a |
| <             | minore di           |
| <=            | minore o uguale a   |
Questi operatori restituiscono un boolean come risultato del confronto tra due espressioni
### Operatori condizionali

| **Operatore** | Nome       |
| ------------- | ---------- |
| &&            | AND-logico |
| \|\|          | OR-logico  |
In Java le espressioni sono valutate solo se necessario, per esempio se ci sono OR valuterà soltanto una e, se questa è vera, le altre verranno scartate a prescindere (in altri linguaggi questo non succede)
### Operatore 'istanceof'
instanceof è un particolare operatore per stabile se un oggetto è istanza di una particolare classe, come risultato restituisce un booleano.
> [!example] Esempio di istanceof
> ```java
> String s = ‘’sono una stringa’’; 
> boolean t = s instanceof String; 
> boolean f = s instanceof Double
> ```
### Bitwise e bitshift
Gli operatori **bitwise** e di **bit shift** permettono di **manipolare direttamente i singoli bit a livello macchina**.
L'operatore tilde (~) calcola il complemento della rappresentazione binaria andando a trasformare tutti gli zeri in uno e viceversa.

Per quanto riguarda lo scorrimento dei bit (shift) troviamo:
- L'operatore `<<` sposta i bit verso sinistra 
- L'operatore `>>` li sposta verso destra 
- L'operatore `>>>` si occupa di spostare i bit a destra ma senza conservare il segno originale

Java mette a disposizione specifici operatori binari sui bit, che sono l'AND logico, lo XOR e l'OR che troviamo all'inizio del capitolo .
### Espressioni
Un'espressione in Java è un costrutto fondamentale composto tipicamente da **variabili**, **operatori** e **chiamate a metodi**
La caratteristica essenziale di un'espressione è che, una volta valutata, restituisce sempre un singolo risultato.
Il tipo di questo risultato non è universale, ma dipende strettamente dai tipi delle variabili coinvolte, dagli operatori utilizzati e, naturalmente, dai valori restituiti dagli eventuali metodi chiamati.
Per gestire priorità complesse, le parentesi possono essere utilizzate liberamente per definire e forzare un preciso ordine di valutazione degli operatori.
### Statement
Uno **statement** rappresenta una **singola istruzione esecutiva** e la sua sintassi richiede tassativamente che termini sempre con il carattere punto e virgola (;).
All'interno del linguaggio si possono individuare quattro tipologie principali di statement:
1. Le istruzioni di assegnazione di valori;
2. Gli operatori matematici particolari come $++$ o $--$;
3. Le istruzioni che effettuano una chiamata ad un metodo;
4. Le istruzioni dedicate alla creazione di un nuovo oggetto in memoria;
### Blocchi
I blocchi sono gruppi di istruzioni racchiusi tra parentesi graffe
> [!example] Esempio di blocco di codice
> ```java
> if (condition) { 
> // Inizio primo blocco
> System.out.println("La condizione è vera."); 
> } 
> // Fine primo blocco
> else { 
> // Inizio secondo blocco
> System.out.println("La condizione è falsa."); 
> } 
> // Fine secondo blocco
> ``` 

## Controllo del flusso
### if-then e if-then-else
Le istruzioni if-then e if-then-else sono essenziali per eseguire dei blocchi di codice solo ed esclusivamente se si verifica una determinata condizione.
> [!example] Esempio di istruzione if-then-else
> ```java
> if (condition) { 
> //blocco if 
> } 
> else { 
> //blocco else 
> }
> ```

L'if-then avviene soltanto quando una condizione è vera, altrimenti nel caso sia falsa questa va nell'else
### if-else annidati
Quando la logica del programma lo richiede, è assolutamente possibile annidare più istruzioni if-else per creare percorsi decisionali multipli
```java
if (condizione1) {
 //blocco condizione 1
} 
else if (condizione2){ 
//blocco condizione 2 
}
else if (condizione3){ 
//blocco condizione 3
}
```
### Switch
Per gestire scenari con molteplici opzioni si utilizza l'istruzione **switch**, che definisce diversi percorsi di esecuzione in base allo specifico valore che assume una singola variabile
> [!example] Esempio di switch
> ```java
> switch (<variabile>) {
> case <valore1>: ...; break;// istruzione 1
> case <valore2>: ...; break; // istruzione 2
> default: ...; break; // istruzione default
> }
> ```

Tale variabile viene confrontata con vari blocchi "case", prevedendo anche un caso "default" finale nel caso nessuna condizione sia rispettata.
Lo switch può essere applicato soltanto a tipi di dati ben precisi, ovvero ai tipi primitivi byte, short, int, char, alla classe String e ai tipi enumerativi
### While
Il ciclo while permette di eseguire un blocco di istruzioni finché una specifica condizione posta in testa al ciclo si mantiene vera
> [!example] Esempio di condizione while
> ```java
> while (condizione) {
> //blocco istruzioni while
> }
> ``` 
### Do while
Il ciclo do-while è concettualmente simile al while, ma con una profonda differenza, ossia il controllo della condizione viene effettuato solamente alla fine del blocco di codice, facendolo sempre eseguire **almeno** una volta.
> [!example] Esempio do-while
> ```java 
> do {
//blocco istruzioni while
} while (condizione);
> ```
### for
L'istruzione **for** permette di iterare un blocco di istruzioni su uno specifico intervallo di valori
> [!example] Esempio for
> ```java
> for (initialization; termination; increment) {
> statement(s) //blocco istruzioni
> }
> ```

L'intestazione di questo ciclo racchiude tre parametri chiave separati da punto e virgola: la fase di inizializzazione, la condizione di terminazione e l'incremento (o decremento)
### for, Array, Collection (for each)
Il for è spesso utilizzato per iterare sugli oggetti di un Array o di una Collection, in questo caso esiste una forma compatta (**for-each**)

> [!example] Esempio for-each
> ```java
> public static void main(String[] args){ 
> 	int[] numbers ={1,2,3,4,5,6,7,8,9,10}; 
> 	for (int item : numbers) {
> 		System.out.println("Count is: " + item);
> 	} 
> }
> ``` 
A ogni passaggio del ciclo, la variabile temporanea item assume automaticamente il valore dell'elemento successivo, dal primo all'ultimo, fermandosi da sola quando l'array è terminato

Il for-each **non garantisce nessun ordinamento**, serve soltanto a visitare quello presente all'interno del contenitore
### break
Lo statement break interrompe istantaneamente e definitivamente un ciclo
> [!example] Esempio di statement break
> ```java
> for (i = 0; i < arrayOfInts.length; i++) { //si cerca 
> 	if (arrayOfInts[i] == searchfor) {
> 		foundIt = true;
> 		break;
> 	}
> }
> ```

Nel caso di cicli annidati, è importante sapere che il break va a interrompere solamente il ciclo più innestato rispetto alla posizione dell'istruzione stessa,
### continue
Lo statement continue  salta la corrente iterazione per passare a quella successiva
> [!example] Esempio di statement continue, cercando in una stringa solo le 'p'
> ```java
> for (int i = 0; i < max; i++) {
> // interested only in p's
>     if (searchMe.charAt(i) != 'p')
>         continue;
>     // process p's
>     numPs++;
> }
> ```

Spesso viene attivato da un costrutto condizionale, come in questo caso
### return
L'istruzione return viene adoperata per terminare in modo definitivo l'esecuzione di un metodo corrente.
A seconda del metodo, può essere usata in modo autonomo e senza restituire alcun valore, oppure restituendo un valore specifico tramite una variabile
## Classi
### Dichiarazione di una classe
La dichiarazione di una classe in Java serve a definire la struttura fondamentale che comprende lo stato della classe attraverso gli attributi, le modalità di creazione e inizializzazione tramite i costruttori, e le funzionalità offerte mediante i metodi

> [!info] Definizione di una classe in Java
> ```java
> class MyClass {
> // attributi
> // costruttori
> // metodi
> } 
> ```

A livello sintattico, la dichiarazione di una classe inizia specificando la sua visibilità, seguita dalla parola chiave class e dal nome della classe stessa
> [!info] Definizione di una classe completa
> ```java
> <visibilità> class <nome> extends <superclass>
> implements <interface1>, <interface2> … {
> //body
> } 
> ```

Durante questa fase è anche possibile indicare da quale superclasse essa erediti, utilizzando la parola chiave **extends**, e definire se implementa una o più interfacce tramite la parola chiave **implements** (le vedremo successivamente).
Il livello di visibilità, che può essere public, private o protected, determina come e da chi la classe può essere vista e utilizzata all'interno del progetto
### Variabili all'interno
All'interno di una classe possiamo trovare diverse tipologie di variabili:
- **I field, o attributi**, sono variabili che definiscono lo stato dell'oggetto e risultano visibili in tutta la classe
- Le **variabili locali**, sono confinate e visibili esclusivamente all'interno del metodo in cui vengono dichiarate e utilizzate
- I **parametri** sono variabili speciali che vengono passate a un metodo nel momento in cui questo viene richiamato
### Dichiarazione degli attributi
Quando si dichiara un attributo, è necessario specificarne la visibilità, il tipo di dato e il nome; se non viene assegnato esplicitamente un valore iniziale, la variabile assumerà il valore di default previsto per il suo tipo
> [!example] Esempio di variabili all'interno di una classe
> ```java
> public class Bicycle {
> 	private int gear = 1;
> 	private int speed;
> }
> ``` 
### Metodi
#### Dichiarazione
I metodi rappresentano le funzioni di una classe e la loro dichiarazione richiede l'indicazione della visibilità, del tipo di dato restituito, del nome e di eventuali parametri racchiusi tra parentesi
> [!example] Esempio di dichiarazione di metodi
> ```java
> public int sum(int a, int b) { //tipo, nome e parametri
>     return a+b;
> }
> ```
#### Nome
Per convenzione, i nomi dei metodi dovrebbero essere scritti in minuscolo e iniziare preferibilmente con un verbo, poiché indicano un'azione; se il nome è composto da più parole, si utilizza la notazione camelCase, inserendo la lettera maiuscola per identificare l'inizio di ogni parola successiva alla prima
#### Overloading di metodi
Java supporta l'overloading dei metodi, una funzionalità che permette a una classe di avere più metodi con lo stesso nome, a condizione fondamentale che abbiano una lista di parametri differente per numero o tipo. 
È importante notare che i metodi sovraccaricati con lo stesso nome devono comunque restituire lo stesso tipo di valore.
> [!example] Esempio di overloading
> ```java 
> public int sum(int a, int b) {
>     return a+b;
> }
> 
> public int sum(int a, int b, int c) {
>     return a+b+c;
> }
> ```
#### Parametri
Per quanto riguarda i parametri, ogni metodo può riceverne da zero a molti, e questi possono essere di qualsiasi tipo, spaziando dai tipi primitivi fino agli oggetti di altre classi come array o stringhe

I parametri all'interno della firma del metodo devono avere nomi differenti tra loro e non è consentito dichiarare variabili locali all'interno del metodo che abbiano lo stesso nome di un parametro. È invece possibile che un parametro abbia lo stesso nome di un attributo della classe, tuttavia in questo scenario l'attributo viene "nascosto" e reso non direttamente visibile al metodo, a meno che non si utilizzi in modo esplicito la parola chiave **this** per disambiguare il riferimento.
#### Costruttori
I costruttori sono metodi speciali progettati appositamente per inizializzare gli oggetti di una classe al momento della loro creazione.
> [!example] Esempio di un costruttore
> ```java
> // Metodo senza valori
>  public Bicycle(int startSpeed, int startGear) {
>     gear = startGear;
>     speed = startSpeed;
> }
> // Metodo con valori 
> public Bicycle() {
>     gear = 1;
>     speed = 0;
> }
> ```

Essi si distinguono per avere lo stesso identico nome della classe a cui appartengono e per il fatto di non restituire alcun valore, nemmeno void. 
Esattamente come accade per i metodi, una classe può dichiarare più di un costruttore sfruttando l'overloading, purché non esistano due costruttori con lo stesso numero e tipo di parametri. Anche ai costruttori possono essere applicati i modificatori di visibilità **private**, **public** o **protected**.
##### Istruzione 'this'
L'istruzione **this** è uno strumento fondamentale che permette di fare riferimento in modo esplicito agli attributi e ai costruttori della classe corrente in cui ci si trova, utile per risolvere ambiguità di nomi o per richiamare un costruttore dall'interno di un altro costruttore
> [!example] Esempio di istruzione 'this'
> ```java
> public class Bicycle {
>     private int gear;
>     private int speed;
>     public Bicycle(int startSpeed, int startGear) {
>         this.gear = startGear;
>         this.speed = startSpeed;
>     }
> 
>     public Bicycle() {
>         this(3, 0);
>     }
> } 
> ```
#### Oggetti
Gli oggetti veri e propri prendono vita in memoria utilizzando l'istruzione **new**, la quale si occupa di invocare il costruttore appropriato della classe a cui l'oggetto deve appartenere. Una volta che l'oggetto è stato instanziato, è possibile accedere ai suoi attributi e invocare i suoi metodi sfruttando la sintassi basata sul punto.

> [!example] Esempio di istanza e utilizzo di un oggetto
> ```java
> Bicycle myBike = new Bicycle(0, 3); //Istanza di un nuovo oggetto
> 
> myBike.gear; //richiamo dell'attributo
> myBike.getSpeed(); //Richiamo del metodo
> ```
#### Numero arbitrario di argomenti
Un'ulteriore caratteristica avanzata permette di definire in un metodo un numero arbitrario di argomenti dello stesso tipo. In questo caso, all'interno del metodo, il parametro viene trattato a tutti gli effetti come un array, rappresentato dai 3 puntini
 
> [!example] Esempio di numero arbitrario di argomenti
> ```java
> public void print(String... s) { // s è visto come un array
>     for (String item:s) {
>         System.out.println(item);
>     }
> }
> 
> print("Pippo", "Topolino", "Pluto")  // Posso invocare print passando tanti oggetti di tipo String
> ```
#### Metodi static
Il modificatore **static** viene impiegato per definire attributi e metodi a livello di classe anziché a livello di singola istanza. Questo significa che una variabile dichiarata come static è condivisa e mantiene lo stesso valore per tutte le istanze create da quella specifica classe. 
Di conseguenza, i metodi contrassegnati come static possono essere chiamati direttamente utilizzando il nome della classe, senza la necessità preventiva di creare un'istanza o un oggetto.

> [!example] Esempio con dichiarazione ed uso metodi static
> ```java
> public class Person {
>     static int numbOfPersons=0; // Qui il numero di persone aumenterà senza essere resettato alla prossima esecuzione
>     private String name;
>     private String surname;
>     public Person(String name, String surname) {
>         this.name=name;
> 	    this.surname=surname;
> 	    ++numbOfPersons;
>     }
> }
> 
> Person p1=new Person(‘’Pippo’’, ‘’Rossi’’);
> Person p2=new Person(‘’Topolino’’, ‘’Bianchi’’);
> System.out.println(Person.numbOfPersons); // Accedo al valore della variabile static della classe Person 
> ```
### Costanti
Per definire delle **costanti**, ovvero attributi il cui valore una volta assegnato non può più essere modificato, si utilizza il modificatore **final**. Un uso comune in Java per le costanti globali prevede la combinazione dei modificatori public, static e final, rendendo il valore accessibile ovunque senza dover instanziare la classe
```java
private final int A = 3; //Visibile solo nella classe
public final int X = 4 // Visibile ad altre classi
public static final double PI=3.14 // Visibile ad altre classi in modo static (senza dover creare un’istanza della classe)
```
### Classi innestate
Il linguaggio offre la possibilità di definire una classe direttamente all'interno del corpo di un'altra classe, creando le cosiddette **classi innestate**. 
Queste si dividono principalmente in due categorie: 
- **Classi innestate statiche**: Una classe innestata statica è indipendente e non ha accesso alle risorse e ai membri della classe esterna 
- **Classi interne**: al contrario, una classe interna gode di un accesso privilegiato a tutte le risorse della classe esterna che la contiene, comprese quelle dichiarate con visibilità private
  L'utilizzo delle classi innestate è consigliato principalmente in tre scenari: 
	- Quando la classe interna risulta utile esclusivamente alle logiche della classe esterna; 
	- Quando si desidera incapsulare una classe B dentro una classe A per permetterle di accedere alle risorse private di A mantenendole sicure; 
	- In generale per raggruppare logicamente il codice rendendolo più pulito e leggibile.

> [!example] Esempio di classi innestate
> ```java
> class OuterClass {
> ...
>     static class StaticNestedClass { // Non ha accesso alle risorse di OuterClass
>         ...
>     }
>     class InnerClass { // Ha accesso alle risorse di OuterClass anche se dichiarate private
>         ...
>     }
> } 
> ```
#### Tipi enumerativi
I tipi enumerativi permettono di definire dei tipi che possono assumere solo un set predefinito di costanti
> [!example] Esempio di tipo enumerativo
> ```java
> public enum Day {
> SUNDAY, MONDAY, TUESDAY, WEDNESDAY,
> THURSDAY, FRIDAY, SATURDAY
> } 
> ```

Quando si crea un tipo enum, Java crea automaticamente una classe di tipo enum che mette a disposizione dei metodi e permette di definire anche dei costruttori e nuovi metodi.
### Interfacce
Le interfacce in Java permettono di definire il funzionamento di una classe indicando esplicitamente quali metodi la classe deve possedere per potervi aderire.
Esse contengono unicamente la descrizione delle firme dei metodi senza fornirne alcuna implementazione, ma possono comunque includere delle costanti.

> [!info] Dichiarazione di interfacce
> ```java
> public interface <nome> extends <interface1>, <interface2>, <interface3> {
>     // dichiarazioni di costanti
>     // firme dei metodi
>     void methodA(int i, double x);
>     int methodB(String s);
> }
> ```

Grazie alle interfacce è possibile definire gruppi di classi che condividono le stesse funzionalità, lasciando però a ciascuna di esse la libertà di implementarle in maniera differente

L'implementazione pratica da parte di una classe avviene tramite la parola chiave `implements`, la quale obbliga la classe stessa a fornire il codice per tutti i metodi definiti all'interno dell'interfaccia.

Nelle interfacce va rispettato le stesse regole di nome delle classi
### Ereditarietà
In Java, le classi possono ereditare da altre classi, il che implica che la sottoclasse acquisisce automaticamente tutti gli attributi e i metodi che possiedono una visibilità `public` oppure `protected` all'interno della superclasse

> [!example] Esempio di ereditarietà in una calcolatrice
> Prendiamo una calcolatrice basica, come questa:
> ![[Pasted image 20260324192730.png]]
> ![[Pasted image 20260324192755.png]]
> Decidiamo di estenderla con una calcolatrice scientifica
> ![[Pasted image 20260324192858.png]]
> ![[Pasted image 20260324192905.png]]

Un aspetto fondamentale del linguaggio è che tutte le classi scritte in Java ereditano, in modo diretto o indiretto, dalla classe madre universale chiamata `Object`
### Overriding e poliformismo
Una classe ha la capacità di ridefinire un metodo che ha precedentemente ereditato dalla sua superclasse (o classe padre).
Quando questo accade, il metodo originale della superclasse viene nascosto e, al suo posto, viene invocato esclusivamente quello ridefinito all'interno della sottoclasse; questo specifico fenomeno strutturale prende il nome di **overriding**

Il polimorfismo è strettamente legato ai concetti di ereditarietà e overriding, in quanto rappresenta la **capacità di ogni sottoclasse di poter ridefinire specifici comportamenti della propria superclasse**.
Tutte le sottoclassi possono riscrivere determinati comportamenti per adattarli alle proprie esigenze, pur mantenendo altre caratteristiche operative in comune con la classe **padre**

> [!example] Esempio di overriding, poliformismo e ereditarietà
> ```java 
> public class ClassA {
>     public void printMe() {
>         System.out.println(‘’Io sono A’’);
>     }
>     public void sayHello() {
>         System.out.println(‘’Hello!’’);
>     }
> }
> 
> public class ClassB extends ClassA {
>     public void printMe() { //override del metodo in A, ereditato
>         System.out.println(‘’Io sono B’’); 
>     }
> }
> ```
> Se qui andassi a richiamare il metodo specificando un oggetto di di tipo B e metodo printMe, otterei come output "Io sono B", poichè ho fatto overriding del metodo precedente
#### Accesso alla superclasse da una sottoclasse
Per interagire esplicitamente con gli elementi della superclasse, Java mette a disposizione dello sviluppatore la parola chiave `super`, questa quando viene utilizzata permette:
- Di invocare direttamente i costruttori della classe padre, utilizzando `super()` senza parametri o `super(lista parametri)` con argomenti specifici, \
- Di richiamare i metodi originali della superclasse tramite la sintassi `super.methodSuper(...)

> [!example] Esempio di accesso alla superclasse da una sottoclasse
> ```java
> public class ClassA {
>     public void printMe() {
>         System.out.println(‘’Io sono A’’);
>     }
>     public void sayHello() {
>         System.out.println(‘’Hello!’’);
>     }
> }
> 
> public class ClassB extends ClassA {
>     public void printMe() {
>         super.printMe() //qui invochiamo il metodo di A direttamente
>         System.out.println(‘’Io sono B’’);
>     }
> }
> ```
### Classi astratte
Le classi astratte si distinguono per la presenza di metodi astratti, ovvero funzioni di cui viene fornita solamente la firma senza alcuna implementazione, sebbene la classe possa contenere parallelamente anche dei metodi regolarmente implementati

La caratteristica restrittiva principale di una classe astratta, dichiarata tramite la parola chiave `abstract`, è che non è fisicamente possibile istanziarne degli oggetti diretti, infatti esse sono concepite esclusivamente per essere ereditate; in tal caso, la sottoclasse ha l'obbligo di fornire un'implementazione concreta per tutti i metodi astratti che ha ereditato

> [!example] Esempio di dichiarazione classe astratta
> ```java
> public abstract class GraphicObject {
>     // declare fields
>     // declare nonabstract methods
> abstract void draw();
> }
> ```
#### Classi astratte vs interfacce

