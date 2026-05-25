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

### Statement
Uno **statement** rappresenta una **singola istruzione esecutiva** e la sua sintassi richiede tassativamente che termini sempre con il carattere punto e virgola (;).
All'interno del linguaggio si possono individuare quattro tipologie principali di statement:
1. Le istruzioni di assegnazione di valori;
2. Gli operatori matematici particolari come $++$ o $--$;
3. Le istruzioni che effettuano una chiamata ad un metodo;
4. Le istruzioni dedicate alla creazione di un nuovo oggetto in memoria;
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
L'istruzione return viene adoperata per terminare in modo definitivo l'esecuzione di un metodo corrente.k
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
Le classi astratte si distinguono per la presenza di metodi astratti, ovvero funzioni di cui viene fornita solamente la firma senza alcuna implementazione, sebbene la classe possa contenere dei metodi implementati

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
Esistono differenze importanti tra classi astratte e interfacce:
1. Nelle classi astratte è possibile dichiarare attributi che non siano obbligatoriamente `static` e `final`, e si possono definire metodi completi della loro implementazione. All'interno delle interfacce tutti gli attributi devono essere rigorosamente `static` e `final`, e tutti i metodi assumono di default una visibilità `public`
2. In Java è consentito estendere una sola classe alla volta (anche se astratta), ma si possono implementare contemporaneamente numerose interfacce
3. Le classi astratte sono utili quando si desidera condividere del codice (sotto forma di metodi) tra un insieme di classi che sono tra di loro strettamente correlate, quando ci si aspetta che le classi figlie abbiano molti metodi o attributi in comune, o quando si necessita di attributi non statici e non finali per permettere ai metodi di modificare liberamente lo stato degli oggetti. Le interfacce sono la scelta preferibile se le classi che le devono implementare non sono strettamente correlate, quando si vuole semplicemente specificare il comportamento di una particolare struttura dati senza entrare nei dettagli implementativi, o quando si ha il bisogno specifico di ricorrere e simulare un'ereditarietà multipli.
#### Classi astratte e Interfacce combinate
In Java, una classe astratta può implementare una o più interfacce. Il grande vantaggio in questo caso è che la classe astratta non è obbligata a implementare subito tutti i metodi richiesti, si può decidere di scriverne solo alcuni e lasciarne altri non implementati",  le sottoclassi concrete (cioè le classi "normali" che andranno a estenderla) avranno poi l'obbligo di fornire il codice per tutti i metodi rimasti vuoti.
### Numeri
Java mette a disposizione delle classi che rappresentano i tipi primitivi numerici che sono `Byte, Short, Long, Integer, Float, Double`. Ognuno di questi eredita dalla classe madre `Numbers`.

Il compilatore converte automaticamente tra tipi primitivi e classi usando una tecnica chiamata **boxing/unboxing**:
- Il **boxing** (noto anche come **wrapper**) è la trasformazione che consiste nel posizionare un tipo primitivo all'interno di un oggetto in modo che il valore possa essere utilizzato come riferimento.
- **Unboxing** è la trasformazione inversa dell'estrazione del valore primitivo dal suo oggetto nel wrapper

Questa classe mette a disposizione come sottoclassi:
- BigInteger/BigDecimal: sottoclassi adibite a interi e decimali con alta precisione
- AtomicInteger/AtomicDecimal: sottoclassi adibite a interi e decimali per applicazioni concorrenti, una volta che un operazione viene effettuata su un tipo di questo genere non è interrompibile (da questo la sua atomicità)

Di solito si usa questa classe per alcuni motivi, tra cui:
- Un argomento deve essere un oggetto e non un tipo primitivo
- Quando bisogna definire delle costanti statiche nelle classi (come MAX_VALUE o MIN_VALUE)
- Per delle conversioni tra tipo, come
	- Da String (stringa contenente dei numeri) a tipo primitivo
	- Da un tipo numerico ad un altro

La classe number implementa diversi metodi tra cui:
> [!info] Metodi per la conversione in un tipo primitivo
> ![[Pasted image 20260402141848.png]]

> [!NOTE] Metodi per il confronto di un numero con un argomento
> ![[Pasted image 20260402142039.png]]

> [!info] boolean equals(Object obj)
> Questo metodo serve per confrontare due oggetti booleani per determinare se siano di stesso valore. Restituisce "true" se sono uguali, altrimenti "false"

> [!info] Metodi per la conversione
> ![[Pasted image 20260402142348.png]]
> 
#### Stampa dei numeri
In Java, poiché ogni numero può essere convertito in una stringa, è possibile stamparli direttamente sullo standard output utilizzando i metodi `System.out.print` e `System.out.println`. `System.out` è un'istanza della classe `PrintStream`, il che permette di utilizzare indifferentemente anche i metodi equivalenti `printf` e `format`
> [!example] Esempio di format
> ```java
System.out.format("The value of the float variable is %f, while the value of the integer variable is %d, and the string is %s", floatVar, intVar, stringVar)
>``` 
>Il metodo `format` accetta una stringa di formattazione seguita da una serie di argomenti, specificando in modo preciso come questi ultimi debbano essere visualizzati
>
>

> [!info] Flag converter e flag
> Al metodo format possono essere passate queste flag:
> ![[Pasted image 20260403173345.png]]
### Math
La classe `Math` mette a disposizione strumenti avanzati per eseguire svariate operazioni matematiche. Al suo interno si trovano:
- Costanti fondamentali come `Math.E` e `Math.PI`
- Metodi per operazioni di base, tra cui:
	- Calcolo del valore assoluto tramite `abs`
	- Arrotondamento tramite `round`
	- Determinazione del valore minimo o massimo tra due numeri con `min` e `max
	-  `double ceil(double d)` per ottenere l'intero più piccolo che sia maggiore o uguale al parametro
	- `double floor(double d)` per calcolare l'intero più grande che sia minore o uguale
	- `double rint(double d)`  per trovare l'intero più vicino a `d`

Sono presenti metodi per calcoli esponenziali e logaritmici come:
- `double exp(double d)` per calcolare $e^{d}$
- `double log(double d)` per il logaritmo naturale $ln(d)$
- `double pow(double base, double exponent)` per eseguire l'elevamento a potenza di una base per un esponente
- `double sqrt(double d)` per calcolare la radice quadrata

Per le funzioni trigonometriche di base e inverse troviamo altri metodi come:
- `sin`, `cos`, `tan`, `asin`, `acos`, `atan`
- `double atan2(double y, double x)`  che permette di convertire coordinate rettangolari in coordinate polari, restituendo l'angolo theta calcolato 
- `double toDegrees(double d),` e `toRadians(double d)` converte l’argomento in gradi o radianti
Come argomento per ogni metodo viene passato un double che rappresenta l’angolo espresso in radianti


Per generare numeri casuali nell'intervallo 0 - 1 si usa `Math.random()`, il cui risultato può essere scalato moltiplicandolo per un intero. Nel caso si voglia generare una serie più articolata di numeri casuali è consigliato l'utilizzo della classe dedicata `java.util.Random`
### Stringhe
La classe `String` rappresenta sequenze testuali ed è caratterizzata dalla sua immutabilità, ossia il valore dell'istanza non può in alcun modo essere alterato una volta portato a compimento il suo processo di creazione.
Ogni letterale scritto tra virgolette nel codice Java è a tutti gli effetti una vera e propria istanza predefinita della classe `String`

Una stringa può essere pensata e gestita logicamente come un array di caratteri; infatti, per accedere agli elementi si usa il metodo `charAt()`, che restituisce il carattere posizionato all'indice specificato
> [!example] Esempio di charAt()
> ```java
> char[] helloArray = { 'h', 'e', 'l', 'l', 'o', '.' }; 
> String helloString = new String(helloArray); 
> System.out.println(helloString);
> ``` 
> Il metodo charAt(int i) di String restituisce il carattere alla i-esima posizione
#### Metodi della classe `String`
La classe presenta diversi metodi:
- `length()` restituisce la lunghezza della stringa in caratteri
- `contains(CharSequence s)` verifica la presenza di una particolare sequenza testuale con risultato booleano
- `indexOf(String s)`  restituisce l’indice dal quale inizia la sottostringa `s`, -1 se non esiste la sottostringa
- `indexOf(String s, int i)` restituisce l’indice dal quale inizia la sottostringa `s` a partire dall'i-esimo carattere, -1 se non esiste la sottostringa
- `replace(CharSequence s1, CharSequence s2)` consente di scambiare sequenze di caratteri esatti (`s1` è quella da cercare, `s2` quella con cui sostituirla)
- `matches(String regex)` restituisce true se la stringa corrisponde all’espressione regolare `regex`
- `startsWith` ed `endsWith` verificano in modo rapido le sequenze collocate agli estremi di una stringa, vengono usati in congiunzione ad altri metodi
- `equals(Object o)` è l'operatore di uguaglianza fatto per le stringhe, si deve assolutamente evitare l'uso dell'operatore di uguaglianza classico tra oggetti (`==`)
- `int compareTo(String str), int compareToIgnoreCase(String str)` permettono un confronto funzionale all'ordinamento, il secondo si usa quando non è necessario il case-sensitive
- `substring(int b, int e), substring(int b)` permette di estrarre e generare una porzione della stringa a partire da un indice iniziale fino alla fine, o limitandosi a un indice finale escluso
- `trim` rimuove gli spazi bianchi inutili presenti all'inizio e alla fine
- `toLowerCase(), toUpperCase()` convertono globalmente il formato delle lettere rispettivamente in minuscolo e maiuscolo
> [!example] Esempio di stringa palindroma
> 
> ```java 
> public class StringDemo {
>     public static void main(String[] args) {
>         String palindrome = "Dot saw I was Tod";
>         int len = palindrome.length();
>         char[] tempCharArray = new char[len];
>         char[] charArray = new char[len];
>         // La stringa originale viene messa in un array di char
>         for (int i = 0; i < len; i++) {
>             tempCharArray[i] = palindrome.charAt(i);
>         }
>         // L'array di char viene girato
>         for (int j = 0; j < len; j++) {
>             charArray[j] = tempCharArray[len - 1 - j];
>         }
>         //Viene messa in un nuovo oggetto e stampata
>         String reversePalindrome = new String(charArray);
>         System.out.println(reversePalindrome);
>     }
> }
> ```

##### Conversione da numeri a stringhe
La conversione da un formato stringa verso effettivi valori numerici è operabile utilizzando i metodi di parsing specifici implementati per ogni tipo primitivo:
```java
int i = Integer.parseInt(“42”); 
float f = Float.parseFloat(“3.14”); 
double d = Double.parseDouble(“4.32144”);
Float fo = Float.valueOf(“3.14”);
```

Se l'esigenza è quella di trasformare un numero nativo in una stringa, si farà ricorso ai metodi di conversione:
```java
int i=3; double d=3.4; 
String s3 = Integer.toString(i); 
String s4 = Double.toString(d);

int i=3; 
String s1 = String.valueOf(i);
```
#### Classe Stringbuilder
Ogni qual volta sia necessario costruire o manipolare stringhe di cui si vuole modificare costantemente il contenuto, è mandatorio ricorrere alla classe `StringBuilder`
La classe lavora con una lunghezza variabile che consente l'aggiunta o la modifica continua di nuovi caratteri
##### Metodi e costruttori Stringbuilder
> [!info] Metodi di Stringbuiler
>` length()` restituisce la lunghezza della stringa presente nell'oggetto StringBuilder  
> `capacity()` restituisce la capacità attuale di questo oggetto StringBuilder (>=length())

> [!info] Costruttori di Stringbuilder
> ![[Pasted image 20260407190808.png]]
> - `StringBuilder append(...)` aggiunge alla fine dello StringBuilder l’argomento (viene convertito in String anche i tipi primitivi)
> - `StringBuilder delete(int start, int end), StringBuilder deleteCharAt(int index)` cancella una porzione o un carattere della stringa
> - `StringBuilder insert(int offset, …)`: inserisce l’argomento a partire dalla posizione `offset`
> - `StringBuilder replace(int start, int end, String s), void setCharAt(int index, char c)` sostituisce una porzione o un singolo carattere della stringa
> - `StringBuilder reverse()` inverte l’ordine dei caratteri della stringa
> - `String toString()`: restituisce una stringa che contiene la sequenza dei caratteri in StringBuilder

> [!example] Esempio con Stringbuilder, stringa palindroma
> ```java
> public class StringBuilderDemo { 
> 	public static void main(String[] args) { 
> 	String palindrome = "Dot saw I was Tod"; 
> 	StringBuilder sb = new StringBuilder(palindrome); 
> 	sb.reverse(); // reverse it System.out.println(sb); 
> 	}
> }
> ```

#### Espressioni regolari
Un'**espressione regolare** rappresenta a livello logico una parola capace di denotare un linguaggio regolare, utile per verificare se una data stringa sia o meno conforme alle regole di quel linguaggio.
> [!info] Diverse espressioni regolari nel linguaggio Java
> ![[Stringhe e numeri_0.png]]
> ![[Stringhe e numeri_1.png]]![[6 - JAVA - Stringhe e numeri_2.png]]![[6 - JAVA - Stringhe e numeri_3.png]]![[6 - JAVA - Stringhe e numeri_4.png]]![[6 - JAVA - Stringhe e numeri_5.png]]![[6 - JAVA - Stringhe e numeri_6.png]]

Dalla classe `String`, due metodi sono utilizzabili con le varie espressioni regolari:
- `split(String regex)` restituisce un array di String dividendo dove c’è il match con regex
- `replaceAll(String regex, String r)` sostituisce tutte le sequenze che corrispondono all’espressione regolare regex con `r`
##### Classe Pattern
Per utilizzi che richiedono procedure di validazione più strutturate o intensive, si ricorre esplicitamente alla classe `Pattern`, la quale costituisce una rappresentazione compilata in memoria di un'espressione regolare specificata tramite stringa

Partendo da un pattern già compilato, è possibile generare un oggetto derivato di tipo `Matcher`, il cui compito primario è quello di eseguire attivamente il matching, cercando in tutti i modi di far combaciare la sequenza di caratteri passata in input con le direttive fornite dall'espressione regolare pre-compilata

> [!example] Esempio di invocazione
> ```java 
> Pattern p = Pattern.compile("a*b"); 
> Matcher m = p.matcher("aaaaab"); 
> boolean b = m.matches();
> ``` 

##### Classe Matcher
La classe `Matcher` esegue le operazioni di matching su una sequenza di caratteri in funzione dell’espressione regolare compilata

Un matcher viene creato da un pattern invocando il metodo matcher del pattern. Una volta creato, un matcher può essere utilizzato per eseguire tre diversi tipi di operazioni di match:
- `match` viene usato per tentare l'abbinamento esatto dell'intera sequenza in input
- `lookingAt` cerca un abbinamento parziale avendo però l'obbligo di partire rigorosamente dall'inizio
- `find` serve a scorrere e analizzare progressivamente l'input alla ricerca della prima sottosequenza utile che corrisponda positivamente
Ognuno di questi metodi restituisce un valore booleano che indica l'esito positivo o negativo.

Un matcher trova corrispondenze in un sottoinsieme del suo input chiamato regione. Per impostazione predefinita, la regione contiene tutto l'input del matcher. Una regione può essere modificata tramite il metodo `region` e costantemente monitorata interrogando i valori forniti da `regionStart` e `regionEnd`

Lo stato esplicito di un matcher include gli indici di inizio e fine dell'ultimo `match (start ed end)`, includendo anche gli indici di inizio e fine della sotto-sequenza dell’ultimo match, nonché un conteggio totale `(groupCount)` di tali sotto-sequenze.
Per comodità, vengono forniti anche metodi per restituire queste sottosequenze in forma di stringa `(group)`
> [!example] Esempi per la classe matcher
> ```java
> //Esempio N.1
> Matcher matcher1 = pattern.matcher("dlkflsASDaslsdSD"); //deve corrispondere l'intera stringa
> System.out.println(matcher1.matches());
> Matcher matcher2 = pattern.matcher("dlkflsASDaslsdSD 8798767"); //la corrispondenza deve partire dall'inizio ma non è necessario che corrisponda l'intera stringa
> System.out.println(matcher2.lookingAt());
> Matcher matcher3 = pattern.matcher("dlkflsASDaslsdSD");
> //cicla su tutti i matching
> while (matcher3.find()) {
>     System.out.println(matcher3.group() + ": " +
>     matcher3.start() + "-" + matcher3.end());
> }
> //Esempio N.2
> //Una sequenza di numeri seguita da 1 o massimo 3 lettere min.
> String regexp = "([0-9]+)([a-z]{1,3})";
> Pattern pattern2 = Pattern.compile(regexp);
> String str = "9843989jf 39203920jie 32122i";
> Matcher matcher4 = pattern2.matcher(str);
> while (matcher4.find()) {
>     //restituisce il numero di gruppi (individuati dalle parentesi nella regexp)
>     int gc = matcher4.groupCount();
>     //il gruppo 0 corrisponde all'intero matching
>     for (int i = 0; i <= gc; i++) {
>        System.out.println(matcher4.group(i) + ": " +
>         matcher4.start(i) + "-" + matcher4.end(i));
>     }
>     System.out.println();
> }
> ```
> 
### Collection
Una **collection** è un oggetto volto a racchiudere più oggetti al suo interno per poterli memorizzare, recuperare ed elaborare.

In parole povere, rappresenta un gruppo di cose che vanno tenute insieme, come:
- Un mazzo di carte;
- L'elenco della rubrica telefonica;
- Insieme di email ricevute;
etc...

Java mette a disposizione un **framework** (insieme di strumenti e librerie predefiniti che forniscono una struttura di base per lo sviluppo e la distribuzione di applicazioni in un particolare ambiente) per la gestione delle Collection, composto da:
- Interfacce
- Implementazioni
- Algoritmi (ricerca, ordinamento etc.) in grado di funzionare in modo polimorfo
#### Interfacce di collection

> [!info] Gerarchia delle interfacce di Collection
> ![[Pasted image 20260409105151.png]]
>`Map` è una collection particolare che non eredita da `Collection`

Ognuna di queste interfacce ha un diverso utilizzo:
- `Collection` è la radice della gerarchia e per questo la più generica, rappresenta semplicemente un contenitore di oggetti (elementi) senza alcun particolare vincolo
- `Set` rappresenta un contenitore di tipo insieme, non può contenere duplicati
	- `SortedSet` è un `Set` in cui gli elementi sono ordinati in ordine crescente
- `List`  è una lista di elementi, ogni elemento avrà una posizione nella lista, ammette duplicati
- `Queue` è una coda in cui gli elementi hanno un preciso ordine di inserimento e recupero (si usa la tecninca FIFO, ma ci sono code particolari dette con priorità il cui ordine è dettato da una funzione di ordinamento)
- `Deque` è simile ad una coda ma permette l’accesso ad entrambe l’estremità della coda
- `Map` permette di collegare dei valori a delle chiavi (queste non possono essere duplicate all'interno della stessa `Map`)
	- `SortedMap` è una `Map` in cui le chiavi sono ordinate in ordine crescente 
##### Metodi delle Collection generali
Tutte le interfacce che ereditano da Collection ereditano i suoi metodi primitivi per gestire un gruppo di oggetti:
- `int size()` restituisce il numero di oggetti 
- `boolean isEmpty()` restituisce true se la Collection è vuota  
- `boolean contains(Object element)`restituisce true se la collection contiene elementi
- `boolean add(E element)` aggiunge un elemento alla Collection 
- `boolean remove(Object element)` rimuove un elemento alla Collection 
- `Iterator iterator()` restituisce un oggetto Iterator che permette di iterare su tutti gli elementi della Collection

Alcuni metodi agiscono sull'intera Collection:
- `boolean containsAll(Collection c)` restituisce true se la collection contiene tutti gli elementi in `c`
- `boolean addAll(Collection c)` aggiunge tutti gli elementi in `c` alla collection 
- `boolean removeAll(Collection c)` rimuove tutti gli elementi di c dalla collection 
- `boolean retainAll(Collection c)` mantiene nella collection solo gli elementi presenti in `c`
- `void clear()` elimina tutti gli elementi dalla collection\

L’interfaccia Collection ha due metodi `toArray` che permettono di fare da ponte tra le collection e gli array:
- `Object[] a = c.toArray()` trasforma la collection `c` in un array di oggetti, `a` avrà la stessa dimensione di `c`
- `String[] a = c.toArray(new String[0])`: se conosciamo il tipo di elementi in `c` possiamo creare un array che contiene gli stessi elementi di `c` e dello stesso tipo
##### Iterazione e interfaccia Iterator
Esistono due modi per iterare una Collection:
1. Il metodo for-each
2. Il metodo iterator, che utilizza l'interfaccia Iterator con i suoi diversi metodi tra cui
	- `hasNext()` restituisce true se ci sono altri elementi da visionare
	- `next()`: restituisce il prossimo elemento
	- `remove()`: rimuove l’elemento corrente
> [!example] Classe Iterator
> ```java
> public interface Iterator { 
> 	boolean hasNext(); 
> 	E next(); 
> 	void remove(); 
> }
> ```

> [!example] Filtrare elementi da una collection
> ```java
> Iterator it=collection.iterator() 
> while (it.hasNext()) { 
> 	if (!cond(it.next())) it.remove(); //cond è un metodo fittizzio che decide se un elemento rispetta o meno una particolare condizione 
> }
> ```
> 
Nel caso quindi sia necessario rimuovere degli elementi è preferibile utilizzare un Iterator e non il metodo for-each
#### Set
Come detto precedentement, la sottoclasse `Set` rappresenta un contenitore di tipo insieme che non può contenere duplicati. Implementa tutti i metodi dell'interfaccia `Collection` e presenta tre implementazioni:
- **HashSet**: un set implementato da una tabella hash non mantiene l’ordine di inserimento degli elementi; è l’implementazione più efficiente 
- **TreeSet**: un set implementato con una struttura ad albero che mantiene l’ordine di inserimento, è meno efficiente
- **LinkedHashSet**: un set implementato con una tabella hash e puntatore che mantiene l’ordine di inserimento degli elementi

L’uguaglianza degli oggetti in questa sottoclasse è definita dai metodi `equals` e `hashCode` (restituisce un intero) della classe `Object`

Siccome `Set` non può contenere duplicati, torna particolarmente utile nella creazione di una `Collection` senza duplicati partendo da una esistente
> [!example] Esempio di Collection senza duplicati
> ```java
> Set s=new LinkedHashSet(c);
> ```
> `s` non conterrà duplicati

> [!example] Esempio di utilizzo di Set
> ```java
> 
> public class Esempio1 {
>     public static void main(String[] args) {
>         // Crea un nuovo Set (insieme) di stringhe utilizzando LinkedHashSet.
>         Set<String> set = new LinkedHashSet<>();
>         
>         
>         // Aggiunge elementi al set.
>         set.add("a");
>         set.add("a"); // I duplicati vengono ignorati in un Set. Questa operazione non ha effetto.
>         set.add("b");
>         set.add("c");
>         
>         // Output: "3: [a, b, c]". 
>         // La dimensione è 3 perché il secondo "a" non è stato inserito.
>         System.out.println(set.size() + ": " + set);
>         
>         // Rimuove l'elemento "a" dal set.
>         set.remove("a");
>         
>         // Output: "2: [b, c]".
>         // Il set ora contiene solo 2 elementi.
>         System.out.println(set.size() + ": " + set);
>         
>         // Crea un secondo Set chiamato set1 e ci aggiunge "b" e "c".
>         Set<String> set1 = new LinkedHashSet<>();
>         set1.add("b");
>         set1.add("c");
>         
>         // removeAll elimina dal primo 'set' tutti gli elementi presenti nel 'set1'.
>         // Dato che 'set' conteneva [b, c] e 'set1' contiene [b, c], il primo set si svuota.
>         set.removeAll(set1);
>         
>         // Output: "0: []".
>         // La dimensione è 0 e l'insieme è vuoto.
>         System.out.println(set.size() + ": " + set);
>     }
> }
> ```
> Quando si crea un Set, è possibile assegnare una variabile Set senza specificare quale si usi, per rendere il codice più generico possibile e non legarlo all'implementazione.
> Questo vale anche per tutte le implementazioni successive di `Collection`
##### Operazione sugli insiemi
Il set permette operazioni su insiemi, tra cui unione, intersezione e differenza
> [!info] Unione
> ```java
> Set<Type> union = new HashSet<Type>(s1);
> union.addAll(s2);
> ``` 
> Il metodo `addAll(Collection c)` aggiunge tutti gli elementi della collezione specificata (in questo caso `s2`) all'insieme su cui viene chiamato, se non sono già presenti

> [!info] Intersezione 
>```java
Set<Type> intersection = new HashSet<Type>(s1);
intersection.retainAll(s2);
>```
> Il metodo `retainAll(Collection c)` mantiene nell'insieme corrente _solo_ gli elementi che sono contenuti anche nella collezione specificata (`s2`). Rimuove tutto il resto.

> [!info] Differenza
> ```java
> Set<Type> difference = new HashSet<Type>(s1);
> difference.removeAll(s2);
> ```
> Il metodo `removeAll(Collection c)` rimuove dall'insieme corrente tutti gli elementi che sono contenuti anche nella collezione specificata (`s2`).
#### Lista
Una lista è una sequenza di elementi ordinata, in questo caso sono ammessi duplicati (purchè si trovino in posizioni diverse) e sono presenti dei metodi oltre quelli previsti da Collection per sfruttare il suo ordinamento

Una lista non ha una dimensione predefinita, cresce dinamicamente
##### Implementazioni delle liste
Ci sono due implementazioni:
- `ArrayList`: lista basata sugli array, la più performante
- `LinkedList`: implementazioni con doppi puntatori
##### Metodi lista
Alcuni metodi sfruttano l'accesso alla posizione:
- `get(int i)`: restituisce l’oggetto alla posizione `i` (le posizioni partono da 0)
- `set(int i, E element)`: inserisce l’elemento alla posizione `i`
- `remove(int i)`: elimina l’oggetto in posizione `i`
- `add(int i, E element)`: aggiunge l’elemento in posizione `i`
- `addAll(int i, Collection c)`: aggiunge tutti gli elementi in c a partire dalla posizione `i`

Per ricercare degli elementi all'interno di una lista si usano questi metodi:
- `indexOf(Object o)`:restituisce la posizione in cui si trova l’oggetto `o`, altrimenti -1. Usa il metodo `equals` sotto.
- `lastIndexOf(Object o)`: restituisce l’ultima posizione in cui si trova l’oggetto o, altrimenti -1

`o` potrebbe trovarsi in più posizioni nella lista, se questo è duplicato viene restituita l’ultima posizione
##### Iterazione nella lista
Per iterare gli elementi della lista esistono diversi metodi:
- `iterator()`: restituisce un iteratore su questa lista, gli elementi verranno elencati in sequenza
- Ci sono due metodi che restituiscono un ListIterator che permette di scorrere la lista sia in avanti che indietro:
	- `listIterator()`: restituisce un ListIterator che parte dall’inizio della lista
	- `listIterator(int i)`: restituisce in ListIterator che parte dalla posizione `i`
##### ListIterator
Il ListIterator è un iteratore che ammette un cursore tra un elemento e l’altro della lista (se non specificato si mette all'inizio ovviamente) e permette di andare all'elemento precedente `previous()` e all'elemento successivo `next()`

> [!example] ListIterator in forma grafica
> ![[Pasted image 20260413085315.png]]

ListIterator ha altri metodi implementati:
- `hasNext()`: booleano che controlla se è presente un elemento avanti
- `hasPrevious()`: booleano che controlla se è presente un elemento indietro
- `remove()`: rimuove l’elemento ottenuto dall’ultima chiamata di `next()` o `previous()` 
- `add(E e)`: aggiunge un elemento tra `previous()` e  `next()` 
- `set(E e)`: sostituisce con `e` l’elemento ottenuto dall’ultima chiamata di `next()` o `previous()`

> [!example] Esempio di operazioni base su una lista
> ```java
> public class List1 {
>     public static void main(String[] args) {
>         // Inizializza una nuova ArrayList di tipo String
>         List<String> list = new ArrayList<>();
>         
>         // Aggiunge elementi in coda alla lista
>         list.add("a");
>         list.add("b");
>         list.add("c");
>         list.add("a");
>         System.out.println(list); // Stampa: [a, b, c, a]
>         
>         // Sostituisce l'elemento all'indice 0 ("a") con "z"
>         list.set(0, "z");
>         System.out.println(list); // Stampa: [z, b, c, a]
>         
>         // Inserisce "d" esattamente all'indice 3, spostando in avanti gli elementi successivi
>         list.add(3, "d");
>         System.out.println(list); // Stampa: [z, b, c, d, a]
>         
>         // Recupera e stampa l'elemento all'indice 1 ("b")
>         System.out.println(list.get(1));
>         
>         // Rimuove l'elemento all'indice 2 (che attualmente è "c")
>         list.remove(2);
>         System.out.println(list); // Stampa: [z, b, d, a]
>         
>         // Cerca e stampa l'indice della prima occorrenza di "a"
>         System.out.println(list.indexOf("a")); // Stampa: 3
>         
>         // Aggiunge un'altra "a" in fondo e cerca l'indice della sua ultima occorrenza
>         list.add("a");
>         System.out.println(list.lastIndexOf("a")); // Stampa: 4
>     }
> }
> ```

> [!example] Esempio di ListIterator
> ```java
> public class List2 {
>     public static void main(String[] args) {
>         // Crea e popola la lista
>         List<String> list = new ArrayList<>();
>         list.add("a");
>         list.add("b");
>         list.add("c");
>         list.add("a");
>         list.add("z");
>         list.add("h");
>         
>         // Crea un ListIterator associato alla lista
>         ListIterator<String> lit = list.listIterator();
>         
>         // hasNext() verifica se c'è un elemento successivo nella lista
>         while (lit.hasNext()) {
>             // Stampa l'indice precedente (-1 alla prima iterazione) e l'indice successivo
>             System.out.print(lit.previousIndex() + "\t" + lit.nextIndex() + " -> ");
>             
>             // next() recupera l'elemento corrente e sposta il cursore in avanti
>             System.out.println(lit.next());
>         }
>     }
> }
> ```

> [!example] Esempio di scorrimento all'indietro
>  ```java
> public class List3 {
>     public static void main(String[] args) {
>         // Crea e popola la lista
>         List<String> list = new ArrayList<>();
>         list.add("a");
>         list.add("b");
>         list.add("c");
>         list.add("a");
>         list.add("z");
>         list.add("h");
>         
>         // Inizializza l'iteratore partendo dal PENULTIMO elemento (size - 1)
>         ListIterator<String> lit = list.listIterator(list.size() - 1);
>         
>         // hasPrevious() verifica se ci sono elementi precedenti rispetto al cursore
>         while (lit.hasPrevious()) {
>             // previous() recupera l'elemento e sposta il cursore all'indietro
>             System.out.println(lit.previous());
>         }
>     }
> }
>  ```
##### Sotto lista
Il metodo `subList(int start, int end)` permette di ottenere una sottolista a partire dalla posizione start fino alla posizione end (non inclusa).

`subList()` restituisce una nuova lista con gli elementi richiesti, non viene fatta nessuna modifica sulla lista di partenza
##### Algoritmi sulle liste
La classe `Collections` (da non confondere con quella classica `Collection`) mette a disposizione dei metodi statici per effettuare degli algoritmi sulle classi che implementano Collection:
- sort: ordina gli elementi nella lista
- shuffle: permuta in modo casuale gli elementi nella lista
- reverse: inverte l’ordine degli elementi
- rotate: ruota gli elementi di una lista
- swap: scambia due elementi nella lista
- replaceAll: sostituisce un elemento con una altro valore
- fill: sostituisce tutti gli elementi con un altro valore
- copy: copia tra due liste
- binarySearch: ricerca un elemento nella lista utilizzando la ricerca binaria
- indexOfSubList, lastIndexOfSubList: cercano una sottolista all'interno di una lista

> [!example] Esempio di shuffling
> ```java
> public class List4 {
>     public static void main(String[] args) {
>         // Inizializzazione della lista con un nome più chiaro
>         List<String> list = new ArrayList<>();
>         
>         // Aggiunta degli elementi
>         list.add("pippo"); 
>         list.add("topolino");
>         list.add("paperino");
>         
>         // Stampa iniziale: [pippo, topolino, paperino]
>         System.out.println(list); 
>         
>         // Ordina la lista in ordine alfabetico
>         Collections.sort(list);
>         System.out.println(list); // [paperino, pippo, topolino]
>         
>         // Mescola gli elementi in modo casuale
>         Collections.shuffle(list);
>         System.out.println(list); 
>         
>         // Ruota gli elementi. Con -1, il primo elemento diventa l'ultimo
>         Collections.rotate(list, -1);
>         System.out.println(list); 
>     }
> }
> ```

##### SortedSet
> [!info] Visione veloce di SortedSet
> ![[Pasted image 20260414175335.png]]

> [!example] Ricerca frequenza parole con SortedSet
> 
> ```java
> import java.util.HashMap;
> import java.util.Map;
> 
> public class Freq {
>     public static void main(String[] args) {
>         // Inizializza una nuova HashMap. 
>         // La Chiave (String) sarà la parola, il Valore (Integer) sarà il suo conteggio.
>         Map<String, Integer> m = new HashMap<>();
> 
>         // Inizializza la tabella delle frequenze leggendo dalla riga di comando (args)
>         for (String a : args) {
>             // Cerca la parola 'a' nella mappa. 
>             // Se la parola non è ancora stata inserita, m.get() restituirà null.
>             Integer freq = m.get(a);
>             
>             // L'operatore ternario (condizione ? caso_vero : caso_falso) decide cosa inserire:
>             // - Se freq è null (parola nuova), inserisce la parola con valore 1.
>             // - Se freq NON è null (parola già vista), reinserisce la parola 
>             //   sovrascrivendo il vecchio valore con freq + 1.
>             m.put(a, (freq == null) ? 1 : freq + 1);
>         }
> 
>         // m.size() restituisce il numero di chiavi (ovvero le parole uniche)
>         System.out.println(m.size() + " distinct words:");
>         
>         // Stampa il contenuto dell'intera mappa nel formato {chiave1=valore1, chiave2=valore2...}
>         System.out.println(m);
>     }
> }
> ```
#### Queue
L'interfaccia `Queue`, come già detto precedentemente, crea una coda per poter mantenere degli elementi e processarli in un preciso ordine (di solito FIFO).
Essendo un interfaccia, non è possibile istanziare un oggetto di tipo Queue, ma estende una Collection già presente.
Generalmente questa interfaccia implementa dei metodi che creano delle eccezioni o fanno il return di un valore specifico (null o false)
##### Metodi in Queue
- `add(E e)`: aggiunge un elemento alla coda, restituisce true se l’elemento è inserito altrimenti genera un’eccezione
- `element()`: restituisce l’elemento in testa alla coda senza rimuoverlo, se la coda è vuota genera un’eccezione
- `offer(E e)`: aggiunge un elemento alla coda, in caso contrario offre valore null
- `peek()` restituisce l’elemento in testa alla coda senza rimuoverlo, oppure null se la coda è vuota
- `poll()`: restituisce e rimuove l’elemento in testa alla coda, null se la coda è vuota
- `remove()`:restituisce e rimuove l’elemento in testa alla coda, se la coda è vuota genera un’eccezione

I metodi di inserimento, cancellazione e recupero sono duplicati e si differenziano sul loro comportamento (eccezione/restituzione valore) nel caso in cui la coda è vuota o ha raggiunto la capacità massima

> [!example] Esempio operazioni base 
> ```java
> public class Queue1 {
>     public static void main(String[] args) {
>         // Crea una nuova coda FIFO (First-In-First-Out) basata su LinkedList
>         Queue<String> q = new LinkedList<>();
>         
>         // offer() aggiunge un elemento in fondo alla coda.
>         q.offer("g");
>         q.offer("h");
>         q.offer("a");
>         
>         // peek() recupera il primo elemento della coda.
>         // Poiché "g" è stato inserito per primo, sarà il primo della fila.
>         System.out.println(q.peek()); // Stampa: g
>     }
> }
> ```
#### Implementazioni di Queue
L'implementazioni di default di una coda è quella di `LinkedList`, che implementa sempre la coda FIFO. Nel caso ci sia bisogno di una lista con priorità, si usa `PriorityQueue`, l'elemento sempre in cima è quello più piccolo.
> [!example] Esempio coda con priorità
> ```java
> public class Queue2 {
>     public static void main(String[] args) {
>         // Inizializza una PriorityQueue. Gli elementi verranno ordinati 
>         // automaticamente in base alla loro "priorità" (ordine alfabetico).
>         Queue<String> q = new PriorityQueue<>();
>         
>         // Aggiunge elementi alla coda
>         q.offer("g");
>         q.offer("h");
>         q.offer("a");
>         
>         // peek() guarda il primo elemento in coda,.
>         // Poiché "a" viene prima di "g" e "h" nell'alfabeto, è lui
>         // l'elemento con la priorità più alta.
>         System.out.println(q.peek()); // Stampa: a
>     }
> }
> ```
#### Deque (Deck)
Deque è una Collection che è simile alla coda, ma con l'eccezione di poter inserire elementi all'inizio e alla fine di essa.
##### Metodi di Deque
Rispetto alla coda, Deque implementa le sue controparti:
- `addFirst(E e), addLast(E e)`: funziona come la controparte di Queue, una aggiunge in cima alla coda e il secondo alla fine delle coda (fa risultare un eccezione nel caso non sia possibile)
- `offerFirst(E e), offerLast(E e) ` funziona come la controparte di Queue, una aggiunge in cima alla coda e il secondo alla fine delle coda (valore null nel caso non sia possibile)
- `removeFirst(), removeLast()` funziona come la controparte di Queue, una rimuove in cima alla coda e il secondo alla fine delle coda (fa risultare un eccezione nel caso non sia possibile)
- `pollFirst(), pollLast()` funziona come la controparte di Queue, una rimuove in cima alla coda e il secondo alla fine delle coda (valore null nel caso non sia possibile)
- `getFirst(), getLast()` funziona come la controparte di Queue, una prende il valore in cime alla coda e il secondo alla fine della coda (fa risultare un eccezione nel caso non sia possibile)
- `peekFirst(), peekLast()` funziona come la controparte di Queue, una prende il valore in cime alla coda e il secondo alla fine della coda (valore null nel caso non sia possibile)
> [!example] Esempio di Deque
> ```java
> public class Deque1 {
>     public static void main(String[] args) {
>         // Inizializza una Deque utilizzando l'implementazione LinkedList.
>         Deque<String> q = new LinkedList<>();
>         
>         // offerLast() aggiunge elementi in coda (alla fine della lista)
>         q.offerLast("g"); // Stato attuale: [g]
>         q.offerLast("h"); // Stato attuale: [g, h]
>         
>         // offerFirst() aggiunge un elemento in testa (all'inizio della lista),
>         // spingendo indietro gli elementi già presenti.
>         q.offerFirst("z"); // Stato attuale: [z, g, h]
>         
>         // Aggiunge un altro elemento in coda
>         q.offerLast("a"); // Stato attuale: [z, g, h, a]
>         
>         // peekLast() legge l'ultimo elemento (senza rimuoverlo)
>         System.out.println("Coda: " + q.peekLast());   // Stampa: a
>         
>         // peekFirst() legge il primo elemento (senza rimuoverlo)
>         System.out.println("Testa: " + q.peekFirst()); // Stampa: z
>     }
> }
> ```
#### Map
L'interfaccia MAP permette di creare delle associazioni chiave-valore. Ogni chiave è univoca e ad ognuna di essa è associato un solo valore.
Esistono tre implementazioni dell'interfaccia Map (simili a Set):
- HashMap
- TreeMap
- LinkedHashMap
##### Metodi di Map
L'interfaccia Map implementa alcuni metodi utili
- `get(Object key)`: restituisce l’oggetto associato alla chiave `key`
- `put(K key, V value)`: inserisce una coppia chiave-volere nella `Map`
- `remove(Object key)`: rimuove la coppia chiave-valore associata a` key`
- `containsKey(Object key)`, : booleano che restituisce true se la Map contiene la chiave `key`
- `containsValue(Object value)`: booleano che restituisce true se la Map contiene il valore `value`
- `putAll(Map<K, V> map)`: inserisce tutti gli elementi di `map`
> [!example] Calcolare le frequenze con una HashMap
> ```java
> public class Freq {
>     public static void main(String[] args) {
>         // Inizializza una nuova HashMap. 
>         // La Chiave (String) sarà la parola, il Valore (Integer) sarà il suo conteggio.
>         Map<String, Integer> m = new HashMap<>();
> 
>         // Inizializza la tabella delle frequenze leggendo dalla riga di comando (args)
>         for (String a : args) {
>             // Cerca la parola 'a' nella mappa. 
>             // Se la parola non è ancora stata inserita, m.get() restituirà null.
>             Integer freq = m.get(a);
>             
>             // L'operatore ternario (condizione ? caso_vero : caso_falso) decide cosa inserire:
>             // - Se freq è null (parola nuova), inserisce la parola con valore 1.
>             // - Se freq NON è null (parola già vista), reinserisce la parola 
>             //   sovrascrivendo il vecchio valore con freq + 1.
>             m.put(a, (freq == null) ? 1 : freq + 1);
>         }
> 
>         // m.size() restituisce il numero di chiavi (ovvero le parole uniche)
>         System.out.println(m.size() + " distinct words:");
>         
>         // Stampa il contenuto dell'intera mappa nel formato {chiave1=valore1, chiave2=valore2...}
>         System.out.println(m);
>     }
> }
> ```
##### SortedMap
> [!info] Visione veloce di SortedMap
> ![[Pasted image 20260414175459.png]]
#### Equals e hashCode
Ogni classe eredita da Object due importanti metodi:
- `equals()`, che ricordiamo essere il metodo per confrontare due operatori, restituisce un valore booleano true quando due oggetti sono uguali
  Il metodo `equals`  è utilizzato da Set per evitare duplicati, ma anche da tutti i metodi di Collection che cercano un oggetto
- `hashCode()`, che restituisce il codice intero hash per l‘oggetto. È utilizzato dalle tabelle hash come quelle fornite da HashMap

Se due oggetti sono uguali in base al metodo `equals (Object)`, la chiamata del metodo `hashCode` su ciascuno dei due oggetti deve produrre gli stessi risultati interi, poichè Object genera l’hash code utilizzando l’indirizzo di memoria dell’oggetto
#### Generics
Le Collection sono originariamente strutture generiche nate per memorizzare oggetti di tipo generico `Object`, tuttavia è possibile tipizzare queste collezioni utilizzando i generics attraverso la sintassi `<T>`, la quale permette a tutti i metodi della struttura di lavorare specificamente su oggetti di tipo `T` anziché sul tipo generico `Object
Per comprendere l'utilità dei generics, è fondamentale analizzare come cambia la gestione dei tipi di dato nel codice:
> [!example] Senza vs Con Generics
> ![[Pasted image 20260414180540.png]]
### Eccezioni
Le eccezioni sono eventi che si verificano durante l'esecuzione del programma e identifica un anomalia che impedisce il normale flusso del programma.

In Java esiste un meccanismo (gestore delle eccezioni) che cattura e gestisce le eccezioni, che di solito possono essere generate durante l'esecuzione di un metodo. Il gestore delle eccezioni gestisce soltanto un determinato tipo di eccezione.
Ogni eccezione ha un oggetto con tutte le informazioni su cosa è accaduto.
#### Tipologie di eccezioni
Esistono 3 grandi tipologie di eccezioni:
- **Exception (con sottoclassi)**: sono eccezioni che possono essere gestite e catturate (anche se il programmatore dovrebbe anticipare e gestire questo tipo di eccezioni)
- **Error (e sottoclassi)**: sono eccezioni che non possono essere gestite e dipendono da qualcosa esterno dal programma
- **RuntimeException (e sottoclassi)**: eccezioni interne al programma che non possono essere anticipate o catturate (essenzialmente sono dei bug)

Tutte le eccezioni sono sottoclassi di Exception, ed è possibile creare una propria classe exception, estendendo quella originale o una delle sue sottoclassi 
#### Try-catch and finally
Per catturare un eccezione bisogna utilizzare il blocco try-catch
> [!info] Blocco try-catch
> ```java
> try {
>     //istruzioni
> } catch (Exception ex) {
>     //gestione dell’eccezione
> } finally {
>     //istruzioni che devono essere indipendentemente eseguite dal successo o non successo della try-catch
> }
> ```
> Il blocco `finally` è opzionale, può essere utilizzato per effettuare delle operazioni di ‘’pulizia’’

Per gestire più eccezioni nella stessa linea di codice si usa la seguente sintassi:
> [!example] Catch di più eccezioni
> ```java
> try { 
> //Istruzioni
> } catch (IOException|SQLException ex) { 
> 	System.err.println("Caught Exception: " + ex.getMessage()); 
> }
> ```

System.err.println() stampa l'errore ma non ferma l'esecuzione del programma. 
#### Lancio di un eccezione
I metodi possono dichiarare il tipo di eccezione che si potrebbe verificare al suo interno. Questo in sostanza obbliga tutti i metodi chiamanti a gestire l'eccezione nel blocco try-catch
> [!example] Esempio di lancio di un eccezione
> ```java
> public File openFile(String filename) throws IOException{
> 	try { 
> 		//istruzioni 
> 	} catch (IOException ex) { 
> 		throw ex; 
> 	}
> }
> ``` 

Il throw generalmente si usa per imporre regole rigide (come dei parametri importanti non validi, file non trovati, connessioni perse) in modo da interrompere il flusso di esecuzione.
Una guida interessante con esempi ancora più chiari la trovate [qui](https://rollbar.com/guides/java/how-to-throw-exceptions-in-java/)
### I/O Stream
Un flusso I/O rappresenta una sorgente di input o una destinazione di output e sono di vario tipo come
file su disco, array di memoria...

Gli **stream** supportano molti tipi diversi di dati, dai byte semplici agli oggetti. Alcuni flussi si occupano di **trasmettere dati**, mentre altri **li manipolano**. Indipendentemente da come funzionano, tutti i flussi presentano **una sequenza di dati.**
#### Byte stream
I byte stream sono utilizzati per leggere e scrivere byte (8 bit) su un dispositivo di I/O.
Ereditano dalle classi `InputStream`  e `OutputStream`.

Ci sono diverse classi che ereditano direttamente dai byte stream per scrivere e leggere sui file:
- `FileInputStream`
- `FileOutputStream`
> [!example] Esempio di scrittura e output di un file
> Ad esempio:
> ```Java
> public class CopyBytes{
> 	public static void main(String[] args) throws IOException{
> 		FileInputStream in = null;
> 		FileOutputStream out = null;
> 		try{
> 			in = new FileInputStream("sorgente.txt");
> 			out = new FileOutputStream("destinazione.txt");
> 			int c;
> 			while((c = in.read())!= -1)
> 			 out.write(c);
> 		}
> 		finally{
> 			if(in != null)
> 			 in.close();
> 			if(out != null)
> 			 out.close();
> 		}
> 	}
> }
> ```
> Si **chiudono sempre** gli stream. È di vitale importanza eseguire questo, poiché possiamo de-allocare risorse e evitiamo di perdere le informazioni scritte sullo stream.
> 

Lo stream sui byte andrebbe evitato poiché **non è una operazione adeguata al compito**, essa infatti è un operazione di basso livello ed esistono degli stream idonei per scrivere e leggere caratteri per caratteri.
#### Character stream
Il character stream si usa in caso dovessimo eseguire operazioni IO di caratteri. Questo tipo di flusso gestisce automaticamente la codifica corretta per i caratteri, seguendo lo stile 
UTF o ISO.

Le classi per questo tipo di stream sono:
- `FileReader`
- `FileWriter`
> [!example] Esempio di character stream
> Ad esempio:
> ```Java
> FileReader inputStream = null;
> FileWriter outputStream = null;
> 
> try{
> 	inputStream = new FileReader("sorgente.txt");
> 	outputStream = new FileWriter("destinazione.txt");
> 	
> 	int c;
> 	while ((c = inputStream.read())!=-1){
> 		outputStream.write(c);
> 	}
> } finally{
> 	if(inputStream != null){
> 		inputStream.close();
> 	}
> 	if(outputStream != null){
> 		outputStream.close();
> 	}
> }
> ```
#### Line-oriented
Per facilitare il lavoro in un file pieno di caratteri (e generalmente i file presentano più testi che caratteri), si può raggruppare per testi.
Per poterlo implementare in questa maniera dobbiamo accedere a sequenze di caratteri, ovvero **prelevare le stringhe**.

Le classi I/O che permettono il prelievo di una stringa e l'inserimento di una stringa su un file sono:
- BufferedReader
- PrintWriter
> [!example] Esempio di stream line oriented
> ```Java
> BufferedReader inputStream = null;
> PrintWriter outputStream = null;
> 
> try{
> 	inputStream = new BufferedReader(new FileReader("sorgente.txt"));
> 	outputStream = new PrintWriter(new FileWriter("destinazione.txt"));
> 	
> 	String l;
> 	while ((l = inputStream.readLine())!=null){
> 		outputStream.println(l);
> 	}
> } finally{
> 	if(inputStream != null){
> 		inputStream.close();
> 	}
> 	if(outputStream != null){
> 		outputStream.close();
> 	}
> }
> ```

#### Buffered I/O
Il Buffered I/O è il più famoso ed utilizzato, specialmente per lo sviluppo in Java.
E' molto conveniente poiché le operazioni vengono eseguite **direttamente sul dispositivo di I/O**; questo è possibile poiché le classi di Java (generalmente) sono **unbeffered**.
>[!NOTE] Buffered e Unbeffered
> - **Unbeffered Stream**: Ogni singola richiesta di lettura o scrittura viene gestita e inviata **direttamente e immediatamente al dispositivo di I/O** (come il disco rigido)
> - **Buffered Stream**: Utilizza un'area di memoria temporanea e velocissima nella RAM (chiamata buffer)

l confronto tra questi due metodi serve a dimostrare il principio dell'**ottimizzazione delle prestazioni**, generalmente il collo di bottiglia è la scrittura su supporto fisico o le velocità di trasmissioni di rete

**Le classi buffered** utilizzano un buffer predisposto all'I/O che velocizza le operazioni di lettura e scrittura.

**Le funzioni** che seguono questa classe sono:
- **BufferedInputStream** e **BufferedOutputStream**: creano le versioni buffered di un byte stream
- **BufferedReader** e **BufferedWriter**: creano le versioni buffered di un character stream

A livello di codice si creano nel seguente modo: 
> [!example] Esempio di creazione BufferedReader e BufferedWriter
> ```java 
> inputStream = new BufferedReader(new FileReader(“pippo.txt")); 
> outputStream = new BufferedWriter(new FileWriter(“pluto.txt"));
> ``` 
#### La classe File
La classe `File` può rappresentare due concetti diversi sotto lo stesso nome:
- **nome** di un particolare file
- **nome** di una directory
Nell'ultimo caso possiamo conoscere gli insieme dei file che lo compongono tramite il metodo `list()`, che restituisce un array di stringe con gli elementi di tale insieme.
È possibile anche selezionare solo un tipo di oggetti nella cartella ricorrendo ad un **filtro**, detto **directory filter**.

L'interfaccia `FilenameFilter` è la seguente: 
```java
public interface FilenameFilter{ boolean accept (File dir, String name);}
```
Le classi che implementano questa funzione devono fornire sia un metodo `accept()` obbligatoriamente sia un metodo `list()` della classe madre `File`, così da eseguire una **call back** per determinare quali nomi di file devono essere inclusi nella lista.
##### Metodo accept()
Gli argomenti del metodo `accept()` sono due:
- Un oggetto **File** che rappresenta la directory in cui si trova il file
- Un oggetto **String** che rappresenta il nome del file

Esiste un'altra interfaccia simile chiamata `FileFilter` in cui il metodo `accept` prende in input direttamente l'oggetto File.

La classe File è usata anche per:
- creare nuove cartelle o percorsi tramite `\mkdir()` o `\mkdirs()`
- accedere alle caratteristiche dei file
- eliminare un file
- verificare l'oggetto File
#### I/O con l'utente
Ogni output visto fino a questo momento non è formattato adeguatamente. Per adeguarci a questa necessità abbiamo bisogno di poter formattare l'output in modo da renderlo comprensibile, così  da poter ottenere le singole informazioni necessarie dall'input di un utente

> [!example] Esempio di input formattato tramite `Scanner`
> ```Java
> Scanner s = null;
> double sum = 0;
> try{
> 	s = new Scanner(new BufferedReader(new FileReader("input.txt")));
> 	while (s.hasNext()){
> 		if( s.hasNextDouble()){ //ricerchiamo il dato semplice Double
> 			sum+=s.nextDouble();
> 		} else s.next();
> 	}
> } finally{
> 	s.close();
> }
> System.out.println(sum);
> ```
> La classe `Scanner` permette quindi di processare l'input suddividendolo i token e traducendolo rispetto ad un tipo predefinito. I token vengono suddivisi utilizzando i white space.
> 
> `new FileReader("input.txt")` prende i caratteri direttamente dal file sul disco,  `new BufferedReader(...)` li accumula in un buffer situato in RAM.
> 
### I/O da linea di comando
##### I/O da linea di comando
La classe System mette a disposizione tre stream collegati al terminale:
- `System.in`: InputStream che legge l'input
- `System.out`: PrintStream che stampa l'output
- `System.err`: PrintStream che stampa messaggi di errore
> [!example] Esempio di I/O con l'utente da linea di comando
> ```Java
> public static void main(String args[]){
> 	Scanner scanner=new Scanner(new InputStreamReader(System.in));
> 	String s= "";
> 	while (scanner.hasNext()){
> 		s= scanner.next();
> 		if(!s.equalsIgnoreCase("exit")){
> 			System.out.println("Hai scritto: "+s);
> 		} else{
> 			System.out.println("Goodbye!");
> 			break;
> 		}
> 	}
> 	scanner.close();
> }
> ```
#### Data Streams
I flussi di dati supportano l'I/O binario dei valori di dati primitivi, tra cui le stringhe pure.
I flussi di dati implementano l'interfaccia **DataInput** o **DataOutput**, tra cui le più utilizzate di queste due interfacce sono proprio **DataInputStream** e **DataOutputStream**.
L'esempio **DataStreams** mostra i flussi di dati scrivendo un **set di record di dati** e quindi rileggendoli. Ogni record è costituito da tre valori relativi ad un articolo: 
- Prezzo (double), 
- quantità (int), 
- descrizione (String).
> [!example] Esempio di Datastream
> ```JAVA
> static final String dataFile="invoicedata";
> 
> static final double[] prices={19.99,9.99,15,99,4,99};
> static final int[] units={12,8,13,29,50};
> static final String[] descs={
> 	"Java T-shirt",
> 	"Java Mug",
> 	"Duke Juggling Dolls",
> 	"Java Pin",
> };
> ```

DataStreams rileva una condizione di fine file catturando una **EOFException**, anziché testare un valore restituito non valido, come i modelli visti precedentemente. Generalmente si usa **IOException (end of stream)**.

Ogni scrittura in DataStreams corrisponde esattamente alla lettura corrispondente passo passo. Il programmatore deve assicurarsi che i tipi di output ed input siano abbinati correttamente. I dati in input sono binari, senza nulla che indichi il tipo dei singoli valori o da dove inizia il flusso.
#### Serializzazione degli oggetti
Se si volesse salvare dei dati su un file che non siano di tipo primitivo, come gli oggetti, DataStream da solo non basta. Dovremmo memorizzare tutte le parti di un oggetto in maniera separata, con una rappresentazione ben precisa così da ricostruire l'informazione correttamente al momento del bisogno. Questo processo prende il nome di **persistenza**.

>[!NOTE] Definizione di persistenza
>La **persistenza** di un oggetto è la capacità dell'oggetto di vivere separatamente dal programma che lo ha generato

Java contiene un meccanismo interno per creare oggetti persistenti, detto **serializzazione**.
La serializzazione trasforma in una sequenza di byte il concetto che vogliamo rappresentare, dopo di che questa rappresentazione di byte può essere ricostruita nel suo aspetto originale.
Dopo che l'oggetto viene serializzato può essere salvato su un file o inviato ad un altro PC.

La sua realizzazione prevede l'uso di un interfaccia con due classi:
- `ObjectOutputStream`, il quale contiene il metodo `writeObject` che serve per serializzare un oggetto.
- `ObjectInputStream`, il quale contiene il metodo `readObject` che serve per deserializzare un oggetto.

Ogni oggetto che si vuole serializzare deve implementare l’interfaccia `Serializable`, la quale non contiene metodi e serve soltanto al compilatore per comprendere che un oggetto di quella determinata classe può essere serializzato.

`ObjectInputStream` e `ObjectOutputStream` sono **stream di manipolazione** e devono essere utilizzati congiuntamente a un `OutputStream` e un `InputStream`.
> [!example] Esempio di serializzazione
> ```Java
> FileOutputStream outFile = new FileOutputStream("info.dat");
> ObjectOutputStream outStream = new ObjectOutputStream (outFile);
> outStream.writeObject(myCar); // dove myCar è un oggetto di una classe Car definita dal programmatore
> ```
>
Per poter leggere l’oggetto serializzato e ricaricarlo in memoria centrale si procederà come segue:
>```Java
>FileInputStream inFile = new FileInputStream("info.dat");
>ObjectInputStream inStream = new ObjectInputStream(inFile);
>Car myCar = (Car) inStream.readObject();
>```
>La serializzazione di un oggetto si occupa di serializzare tutti gli eventuali riferimenti ad esso collegati. Se la classe Car contenesse dei riferimenti (variabili di classe o di istanza) a oggetti di classe Engine, questa verrebbe serializzata automaticamente e diverrebbe parte della serializzazione di Car. La classe Engine dovrà, pertanto, implementare anch’essa l’interfaccia serializable al suo interno.

>[!ERROR] Errore comune
>Gli attributi di classe, cioè definiti come static, **non vengono serializzati**. Per poterli salvare occorre provvedere in modo personalizzato.

> [!example] Esempio di serializzazione personalizzata
> 
> ```java
> class Nave implements Serializable {
> 
>     private static int nroNavi = 1;
>     private int nroNave;
>     private String nomeNave;
> 
>     // Costruttore: assegna il numero progressivo e il nome alla nave
>     Nave(String nomeNave) {
>         nroNave = nroNavi++;// Assegna il numero corrente e incrementa il contatore
>         this.nomeNave = nmeNave;// Assegna il nome passato come parametro
>     }
> 
>     // Restituisce una rappresentazione testuale della nave
>     public String toString() {
>         return nomeNave + ": " + nroNave;
>     }
> 
>     // Metodo per SALVARE (serializzare) l'oggetto su file binario "info.dat"
>     public void salva() throws FileNotFoundException, IOException {
>         ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("info.dat"));
>         out.writeObject(this);// Serializza l'oggetto Nave corrente
>         out.writeObject(nroNavi);       
>         out.close();
>     }
> 
>     // Metodo statico per CARICARE (deserializzare) un oggetto Nave dal file "info.dat"
>     public static Nave carica() throws FileNotFoundException, IOException {
>         ObjectInputStream in = new ObjectInputStream(new FileInputStream("info.dat"));
>         Nave n = (Nave) in.readObject();// Legge e ricostruisce l'oggetto Nave
>         Nave.nroNavi = in.readObject();
>         in.close();
>         return n;// Restituisce la nave deserializzata
>     }
> }
> ```

Molte classi della **libreria standard Java implementano l’interfaccia Serializable** in modo da essere serializzate quando necessario, come ad esempio la classe String.
#### Transient
A volte, quando si serializza un oggetto, si può desiderare di **escludere delle informazioni**, come una password.
Questo accade quando le informazioni vengono trasmesse via rete, poiché il pericolo è che, pur dichiarandola con visibilità privata, la password possa essere letta e usata da soggetti non autorizzati quando viene serializzata.
Per questo tipo di richiesta e problematica ci viene in aiuto la parola chiave **transient** associato al nome di una variabile, esso indica al compilatore di nascondere quella variabile  così da non rappresentarla come parte dello stream di byte della versione serializzata dell'oggetto.

> [!example] Esempio di variabile transient
> ```Java
> private transient String password;
> private String CF;
> ```
> In questo caso, durante la serializzazione dell'oggetto che include queste due variabili, la variabile CF, anche se privata, sarà serializzata, mentre la password sarà ignorata nella rappresentazione grazie alla keyword transient.
### Generics
Le Generics in Java vengono introdotte per poter superare il limite imposto dalle interfacce nella generalizzazione (ossia il **polimorfismo per inclusione**)
> [!example] Limitazione delle interfacce in Java
> È possibile implementare un metodo $m$ che prende in input un oggetto della classe base $A$ come argomento. Tale metodo potrà essere utilizzato su tutte le sottoclassi della classe $A$ (ammesso che $A$ non sia dichiarata `final`). 
> La limitazione della applicabilità del metodo $m$ ad un albero di ereditarietà con radice $A$ può essere superato con l’utilizzo di un’interfaccia, ma alcune volte anche questo diventa un limite, dovendo ricorrere all'astrazione generica

Le Generics quindi permettono un astrazione maggiore rispetto alle interfacce, creando **classi contenitori** in grado di contenere oggetti omogenei di qualsiasi classe
> [!example] Esempio di Generics (W3Schools)
> ```java
> class Box<T> {  
>   T value; // T is a placeholder for any data type  
>   
>   void set(T value) {  
>     this.value = value;  
>   }  
>   
>   T get() {  
>     return value;  
>   }  
> }  
>   
> public class Main {  
>   public static void main(String[] args) {  
>     // Create a Box to hold a String  
>     Box<String> stringBox = new Box<>();  
>     stringBox.set("Hello");  
>     System.out.println("Value: " + stringBox.get());  
>   
>     // Create a Box to hold an Integer  
>     Box<Integer> intBox = new Box<>();  
>     intBox.set(50);  
>     System.out.println("Value: " + intBox.get());  
>   }  
> }
> ```

Uno degli scopi primari delle Java Generics risiede nella capacità di fornire un meccanismo di casting automatico e sicuro al momento dell'istanziazione di un tipo parametrizzato, delegando al compilatore il compito di verificare la consistenza dei tipi rigorosamente a tempo di compilazione (compile-time)
#### Tuple di Generics
In alcuni casi è possibile che sia necessario definire una funzione che restituisca non un singolo valore ma una coppia di valori o una tripla, allora si può definire con le Generics delle tuple
> [!example] Esempio di tuple in Generics
> ```java
> public class TwoTuple<A,B> {
>     public final A first;
>     public final B second;
>     public TwoTuple(A a, B b) { first = a; second = b; }
>     public String toString() {
>         return "(" + first + ", " + second + ")";
>     }
> } 
> 
> TwoTuple tt = new TwoTuple("hi", 47); 
> System.out.println(tt.toString());
> ```
> 
#### Containers per Generics
 Le Generics sono basilari per l'implementazione di tipi astratti di dati classici, come lo **stack**. È possibile strutturare uno stack dinamico senza vincolarlo al tipo di dato memorizzato, impiegando, ad esempio, una classe interna privata (inner class) destinata alla rappresentazione del singolo nodo della struttura

> [!example] Esempio di containers
> ![[Pasted image 20260426143346.png]]
> Node<U\> è una classe interna a LinkedStack<T\>. Questo significa che può essere utilizzata all’interno di LinkedStack<T\>. Potrebbe anche essere visibile all’esterno, ma in questo caso è definita privata, quindi non è visibile all’esterno.
> La classe Node<U\> è di servizio alla definizione di LinkedStack<T\>, per questa ragione non è resa accessibile se non a quest’ultima.

In generale non è possibile creare un oggetto di una classe interna a meno che non si disponga di un oggetto della classe esterna, tuttavia nel caso di classe interna dichiarata static (detta anche nested) non è necessario disporre di tale oggetto.

Tornando all’esempio di contenitore generico, a questo punto è possibile creare uno Stack che contiene solo Stringhe:
> [!example] Esempio Stack solo stringhe
> ```java    
> LinkedStack<String> names = new LinkedStack<String>();
> 
> void printNames(LinkedStack<String> names) {
>     String nextName = names.pop(); // no casting needed!
>     names.push("John"); // ok
>     names.push(new Integer(3)); // compile-time error! This stack contains only String
> }
> ```
> Tramite la parametrizzazione, un tentativo di immissione di un dato incoerente nella struttura genera tempestivamente un errore a tempo di compilazione, garantendo la sicurezza (type safety) senza oneri aggiuntivi di casting in fase di estrazione.
#### Interfacce per Generics
Le Java Generics possono essere anche utilizzate per parametrizzare la dichiarazione di interfacce
> [!example] Esempio di dichiarazione di interfacce
> 
> ```java
> public interface Generator <T> { T next(); }
> ```   
> L'interfaccia Generator garantisce che il metodo` next()` restituisca un valore del tipo specificato dal parametro `T`. Un’altra interfaccia parametrizzata è Iterable che forza l'implementazione del metodo: 
> ```java
> Iterator<T> iterator()
> ``` 
> Le classi che implementano tale interfaccia permettono ad un oggetto di essere usato nello statement "foreach".
#### Metodi generici
Oltre all'astrazione strutturale, il linguaggio permette la definizione di metodi generici, parametrizzando unicamente le dichiarazioni delle specifiche funzioni all'interno di una classe.
**Un metodo può essere definito generico indipendentemente dalla fatto che la classe sia generica oppure no.** Per di più, se un metodo definito in una classe parametrizzata è statico, tale metodo non accederà al parametro di tipo della classe.

Per definire un metodo come generico è sufficiente parametrizzare la sua dichiarazione
> [!example] Esempio di metodo generico
> ![[Pasted image 20260426164504.png]]
> Nell'esempio, la funzione `f()` è stata “sovraccaricata” (overloaded) ben sei volte. `f()` accetterà anche valori di tipo primitivo mediante il meccanismo dell'autoboxing.
> Java introduce anche una semplificazione che permette di inferire (definire) il tipo in maniera automatica
> ```java
> List <String> ls = new ArrayList();
> ```

I metodi generici possono essere anche utilizzati in combinazione con metodi a numero variabile di argomenti
#### Problema dell'erasure
Le Java Generics lasciano comunque alcune questioni poco chiare. 
Per esempio, mentre è possibile ricorrere al letterale di classe per la classe ArrayList:
```java
ArrayList.class
``` 
non è possibile ricorrere al letterale di classe per la classe ArrayList ottenuta parametrizzando il tipo del contenuto:
```java
ArrayList<Integer>.class
``` 
Il compilatore Java adotta la **tecnica dell'erasure**: tutte le direttive e i controlli sui tipi vengono eseguiti ed esauriti a compile-time, per poi essere cancellati durante la generazione del bytecode. Conseguentemente, a tempo di esecuzione, le istanze di collezioni diverse dal punto di vista semantico risultano essere indistinguibili e appartenenti al medesimo tipo base grazie alla tecnica dell'astrazione generica.
#### Wildcards
All'interno delle Generics possono essere messi dei tipi parametrici jolly chiamati **wildcard**, che servono ad indebolire i vincoli di tipo
> [!example] Wildcards
> ```java
> public class WildcardClassReferences {
>     public static void main(String[] args) {
>     Class<?> intClass = int.class; //? significa di qualunque tipo
>     intClass = double.class;
>     }
> }
> ```

In alcuni casi un riferimento potrebbe essere troppo generico, quindi al fine di creare riferimenti specifici è possibile combinare una wildcard con una estensione di una classe
> [!example] Esempio di estensione
> ``` java
> public class BoundedClassReferences {
>     public static void main(String[] args) {
>     Class<? extends Number> bounded = int.class;
>     bounded = double.class;
>     bounded = Number.class;
>     }
> }
> ```
### Identificazione di tipo a run-time
Java permette di scoprire informazioni sugli oggetti e sulle classi a run-time, basandosi su due approcci:
- RTTI (Run-time Type Identification, RTTI): si presuppone che le informazioni di tutti i tipi sono accessibili sia in fase di compilazione che di esecuzione
- Meccanismo di riflessione: permette di scoprire informazioni sulle classi esclusivamente al run-time
#### RTTI tradizionale
La rappresentazione delle informazioni su un tipo viene realizzato tramite un tipo speciale di oggetto chiamato **Class** (talvolta chiamato meta classe).
Contiene diverse informazioni, tra cui metodi, attributi, modalità di accesso... e durante la compilazione ogni classe che costituisce un programma ha un oggetto Class 

Gli oggetti di Class relativi alle varie classi che compongono un programma non sono caricati tutti in memoria prima di iniziare l’esecuzione, infatti quando in run-time si istanzia una classe, la Java Virtual Machine (JVM), su cui sta girando il programma, prima verifica se l’oggetto Class corrispondente è caricato e in caso negativo la JVM lo carica cercando il file .class con quel nome
> [!example] Esempio di RTTI tradizionale
> ```java
> class Candy {
>     static { // questa è una clausola statica
>         System.out.println("Loading Candy");
>     }
> }
> class Cookie {
>     static { // questa è una clausola statica
>         System.out.println("Loading Cookie");
>     }
> }
> 
> public class SweetShop {
> public static void main(String[] args) {
>     System.out.println("inside main");
>     new Candy();
>     System.out.println("After creating Candy");
>     try {
>         Class.forName("Gum");
>     } catch(ClassNotFoundException e) {
>         e.printStackTrace(System.err);
>     }
>     System.out.println("After Class.forName(\"Gum\")");
>     new Cookie();
>     System.out.println("After creating Cookie");
>     }
> }
> ```
> In questo esempio, ognuna delle classi Candy e Cookie ha una clausola statica che viene eseguita quando la classe è caricata la prima volta

Il metodo `forName()` è un metodo statico di Class che serve per ottenere un riferimento a un oggetto Class, esso prende un oggetto di tipo String contenente il nome testuale della classe di cui si vuole il riferimento e restituisce un riferimento a Class. Si può notare come ogni oggetto Class è stato caricato solo quando era necessario.

Alternativamente, per ottenere un riferimento a un oggetto Class **si può anche ricorrere al letterale di classe (class literal)**, dato dal nome della classe seguito da .class (esempio: Gum.class).
I vantaggi di questa notazione sono:
- Semplicità
- Efficienza 
- Controllo di esistenza della classe durante la compilazione

Il letterale di classe funziona anche con gli array, tipi primitivi (boolea.class) e interfacce
Per i "wrapper" dei tipi primitivi c'è anche un campo standard chiamato **TYPE**, che produce un riferimento all'oggetto Class per il tipo primitivo associato tale che si hanno le seguenti equivalenze
> [!info] Equivalenze di tipo TYPE
> ![[Pasted image 20260429121813.png]]
##### Forme di RTTI
Le forme di RTTI viste finora sono:
- Il classico cast che usa RTTI per assicurarsi che il cast è corretto e solleva una eccezione ClassCastException se è stato ottenuto un cast non corretto
- L’oggetto Class rappresentante il tipo dell’oggetto. L’oggetto Class può essere interrogato per ottenere utili informazioni al run-time

In Java, che esegue il controllo di tipo, questo tipo di cast è spesso chiamato “type safe downcast”

Un’altra forma di RTTI in Java è ottenuta attraverso l’uso della parola chiave `instanceof`, che indica se un oggetto è istanza di un particolare tipo e restituisce un boolean.
L’uso dell’operatore `instanceof` potrebbe risultare spesso molto noioso perché lo si deve specificare per il confronto di ogni tipo di oggetto distinto, quindi la classe `Class` mette a disposizione il metodo `isInstance()` che fornisce un modo per invocare dinamicamente l’operatore `instanceof`

Quando si dispone di un oggetto, si può estrarre il riferimento all’oggetto Class relativo alla sua classe richiamando un metodo che è implementato in Object: `getClass`
#### Meccanismo di riflessione
Talvolta le informazioni sulla classe dell’oggetto non sono accessibili a tempo di compilazione, in tal caso risulta molto utile poter usufruire di un meccanismo che ricava le informazioni relative alla classe al run-time

La classe `Class` supporta il concetto di riflessione e c’è una libreria aggiuntiva `java.lang.reflect` che contiene delle classi utili allo scopo: Field, Method, Constructor (ognuno dei quali implementa una interfaccia Member).

Questo tipo di oggetti sono creati dalla JVM al run-time per rappresentare il corrispondente membro della classe sconosciuta. 

Quando si usa il meccanismo di riflessione, la JVM tratta l'oggetto come appartenente ad una classe particolare, per questo deve essere sempre accessibile (localmente e in rete)
### JDBC
Java ha la possibilità di sviluppare applicazioni client/server indipendenti dalla piattaforma, garantita anche per applicazioni che lavorano su basi di dati.

Java implementa lo standard JDBC (Java DataBase Connectvity) che è **platform-independent**, e fornisce un driver per poter gestire dinamicamente tutti gli oggetti driver di cui hanno bisogno le interrogazioni a database.

JDBC incorpora in se stesso tutte le normali operazioni di interfacciamento con un database: connessione, creazione di tabelle, interrogazione e visualizzazione dei risultati

Attraverso il driver JDBC si possono effettuare tutte le operazioni disponibili su un DMBS.
#### Connessione ad un database
Per poter aprire una connessione ad un database è necessario ottenere un oggetto di tipo `Connection`, che fornisce tutti i metodi per preparare le query SQL.
Per ottenere una connessione è necessario caricare il driver che implementa le API JDBC, chiamando il metodo `getConnection()` della classe `DriverManager` 

Il metodo `DriverManager.getConnection stabilisce` una connessione ad un database. Questo metodo richiede una database URL, che dipende dal DBMS, per esempio:

> [!example] Esempio di connessione database H2
> ```
> jdbc:h2:/home/user/test/db
> ``` 
> dove /home/user/test/db è il file su file system che conterrà il DB

Altri parametri come ad esempio username e password possono essere specificati attraverso un oggetto `Properties` passato al metodo `getConnection()` insieme alla URL

> [!example] Esempi di connessione al database
> ```java
> //connessione senza parametri 
> Connection conn = DriverManager.getConnection("jdbc:h2:/home/user/test/db"); //connessione con username e password 
> Connection conn = DriverManager.getConnection("jdbc:h2:/home/user/test/db","us er","1234"); //connessione con oggetto Properties 
> Properties dbprops = new Properties(); 
> dbprops.setProperty("user", "user"); 
> dbprops.setProperty("password", "1234"); 
> Connection conn = DriverManager.getConnection("jdbc:h2:/home/user/test/db", dbprops);
> ```
#### SQLException
Quando la JDBC genere un errore durante le interrogazioni di un database solleva un eccezione di tipo **SQLException**, che contiene diverse informazioni:
- Una descrizione testuale, data dal metodo `getMessage()`
- `getSQLState()`, restituisce un codice alfanumerico codificato secondo lo standard ISO/ANSI e Open Group (X/Open)
- `getErrorCode()` restituisce un valore intero che indica un codice di errore specifico del driver che implementa JDBC
#### Statement
Le query SQL si eseguono attraverso oggetti di tipo `Statement`, ottenuti tramite l'oggetto `Connection`.

È possibile ottenere anche degli statement preimpostati in cui è possibile sostituire a dei segnaposto inseriti nella query SQL dei valori. Queste query preimpostate sono utili per inserire in maniera corretta all'interno della query dei lettarali applicando le opportune conversioni di tipo
##### Statement di modifica
Per eseguire le varie operazioni di modifica di un DB (come creazione di tabelle, aggiunta di tuple, modifica di tuple) si usa il metodo `executeUpdate()` definito dall'oggetto `Statement`. Gli statement vanno sempre chiusi tramite `close()`per liberare risorse
> [!example] Esempio di statement di modifica 
> ```java
> public static final String CREATE_TABLE = "CREATE TABLE IF NOT EXISTS store (artId INT PRIMARY KEY, desc VARCHAR(1024), price DOUBLE, unit INTEGER)";
> ... 
> Connection conn = DriverManager.getConnection("jdbc:h2:/home/user/db/store", dbprops); Statement stm = conn.createStatement(); 
> stm.executeUpdate(CREATE_TABLE); 
> stm.close(); //chiudere lo statement!!!
> 
> stm = conn.createStatement(); 
> stm.executeUpdate("INSERT INTO store VALUES(1,'pentola',4.5,20)"); 
> stm.close();
> ```

> [!example] Esempio di prepared Statement
> ```java
> PreparedStatement pstm = conn.prepareStatement("INSERT INTO store VALUES (?, ?, ?, ?)"); // ? è un segnaposto 
> pstm.setInt(1, 2); //l’indice parte da 1 
> pstm.setString(2, "piatto"); // i metodi set si occupano di inserire i letterali nella query SQL 
> pstm.setDouble(3, 1.5); pstm.setInt(4, 40); 
> pstm.executeUpdate(); 
> pstm.close();
> ```
##### Statement di interrogazione
Le query di selezione dei dati si effettuano con il metodo `executeQuery("Query")` che è istanziato sempre da `Statement`.

`executeQuery()` restituisce un oggetto di tipo `ResultSet` che permette di navigare nelle tuple restituite (simile ad un iteratore)

> [!example] Esempio di statement di interrogazione
> ```java
> Statement stm = conn.createStatement(); 
> ResultSet rs = stm.executeQuery("SELECT artId, desc FROM store WHERE unit>5"); 
> while (rs.next()) { 
> 	System.out.println(rs.getInt(1) + ": " + rs.getString(2)); 
> } 
> rs.close(); 
> stm.close();
> ```
> 
> ```java
> PreparedStatement pstm = conn.prepareStatement("SELECT artId, desc FROM store WHERE unit > ?"); 
> pstm.setInt(1, 20); 
> rs = pstm.executeQuery(); 
> while (rs.next()) { 
> 	System.out.println(rs.getInt(1) + ": " + rs.getString(2)); 
> } 
> rs.close(); 
> stm.close();
> ```
> È possibile utilizzare anche i PreparedStatement per le SELECT
### Programmazione concorrente
Un calcolatore moderno è progettato per eseguire molteplici compiti simultaneamente, come la riproduzione musicale, la navigazione sul web o la stesura di un documento in parallelo.

Java mette a disposizione dei programmatori una vasta gamma di classi dedicate alla programmazione concorrente, le quali sono principalmente racchiuse nel pacchetto standard `java.util.concurrent`
#### Processi e thread
Anche in presenza di un calcolatore dotato di una singola CPU, il sistema è in grado di simulare l'esecuzione simultanea di più processi attraverso una tecnica denominata **time slicing**, ossia il suddividere il tempo di calcolo complessivo della CPU in finestre temporali, distribuendolo tra i vari processi attivi.

I **processi** rappresentano tipicamente una singola applicazione in esecuzione all'interno del sistema operativo e possono essere composti da **threads**, ossia delle unità di esecuzione meno complesse dei processi.
#### Runnable e Thread
In Java, le funzionalità inerenti alla gestione e al ciclo di vita di un singolo flusso di esecuzione sono implementate e fornite dalla classe `Thread`. 
La creazione di un thread operativo può avvenire seguendo due approcci:
- **Approccio per classe da zero**
- **Approccio per estensione di classe**
> [!example] Esempio di approccio per classe da zero
> Si va a creare una classe che implementa l’interfaccia `Runnable`: questa interfaccia prevede un singolo metudo run() dove va inserito il codice che deve eseguire il thread
> ```java
> public class HelloRunnable implements Runnable { 
> 	public void run() { 
> 		System.out.println("Hello from a thread!"); 
> 		} 
> 		
> 	public static void main(String args[]) { 
> 		(new Thread(new HelloRunnable())).start(); 
> 	} 
> }
> ```
>

> [!example] Esempio di approccio per estensione di classe
> ```java
> public class HelloThread extends Thread { 
> 	public void run() { 
> 		System.out.println("Hello from a thread!"); 
> 	} 
> 	
> 	public static void main(String args[]) { 
> 		(new HelloThread()).start(); 
> 	} 
> }
> ```

In entrambi i casi è necessario invocare il metodo `start()` di `Thread` per farlo partire.
L’interfaccia `Runnable` è più generica in quanto svincolata dalla classe `Thread`, il suo utilizzo permette di evitare l'ereditarietà delle varie altre classi da `Thread`, così da poter ereditare da altre se necessario
#### Controllo di esecuzione
##### Sospensione di esecuzione
Per regolare il ritmo di esecuzione è possibile sospendere il thread corrente invocando il metodo `Thread.sleep()`.
L'intervallo di tempo può essere espresso in millisecondi o millisecondi+nanosecondi, anche se il calcolo del tempo è dipendente dal sistema operativo e non può essere esatto.

> [!example] Esempio di sleep
> ```java
> public class SleepMessages {
>     public static void main(String args[]) throws InterruptedException { // sleep può generare un’eccezione se il thread viene interrotto da un altro thread durante lo sleep
>         String importantInfo[] = {
>             "Info 1",
>         "Info 2",
>         "Info 3",
>         "Info 4"
>         };
>         for (int i = 0; i < importantInfo.length; i++) {
>             //sospendi per 4 secondi (4000 millisecondi)
>             Thread.sleep(4000);
>             //Stampa il messaggio
>         System.out.println(importantInfo[i]);
>         }
>     }
> }
> ```
##### Interruzione di un thread
L'interruzione di un thread in esecuzione può essere forzata invocando il metodo `interrupt()`.
Ogni thread, per essere ben implementato, deve avere le seguenti caratteristiche:
- Ogni thread deve implementare il suo metodo `interrupt()`
- Ogni `interrupt()` deve coincidere con la sua terminazione
- Ogni thread catturi l'eccezione `InterruptedException` e interrompa la sua esecuzione

> [!example] Esempi di interrupt
> Riprendendo l’esempio precedente, catturiamo l’eccezione durante lo sleep
> ```java
> for (int i = 0; i < importantInfo.length; i++) {
>     // Pause for 4 seconds
>     try {
>         Thread.sleep(4000);
>     } catch (InterruptedException e) {
> 	    // We've been interrupted: no more messages.
> 	    return; // Se interrotto esco dal metodo run
>     }
>     // Print a message 
>     System.out.println(importantInfo[i]);
> }
> ```
> Se non ci sono metodi che generano InterruptedException allora controlliamo periodicamente se qualche altro thread abbia invocato l’interruzione
> ```java
> for (int i = 0; i < inputs.length; i++) { //do something 
> 	if (Thread.interrupted()) { //Restituisce true nel caso di interruzione 
> 	// We've been interrupted return; 
> 	}
> ```
##### Unione di esecuzione dei thread
La classe `Thread` include anche il metodo `join()`, utile per la temporizzazione dei stessi thread
La chiamata del metodo `join()` mette in pausa il thread corrente fino a quando il thread sul quale si è chiamato non termina. Come il metodo precedente, `join()` permette di specificare un tempo massimo di atteso e può essere interrotto da un `InterruptedException`

> [!info] Visualizzazione grafica del join e del ciclo di vita di un thread
> ![[Pasted image 20260506103832.png]]
> ![[Pasted image 20260506103843.png]]
#### Sincronizzazione dei thread
I thread per poter comunicare e accedere alle stesse risorse hanno bisogno di essere **sincronizzati**.
Quando due thread non sono sincronizzati incorrono due problematiche:
- **Thread interference**
- **Memory consistency error**
La sincronizzazione permette di risolverle ma introduce problemi di **thread contention** quando vogliono utilizzare le stesse

Un metodo sincronizzato può essere chiamato da un solo thread alla volta (e gli altri restano in attesa), garantendo che il metodo protetto può essere invocato ed eseguito soltanto da un thread per volta, forzando tutti gli eventuali altri thread richiedenti a rimanere in uno stato di attesa

> [!example] Esempio di metodi sincronizzati
> ```java
> public class SynchronizedCounter { 
> 	private int c = 0; 
> 	public synchronized void increment() { 
> 		c++; 
> 	} 
> 	public synchronized void decrement() {
> 		c--; 
> 	} 
> 	public synchronized int value() { 
> 		return c; 
> 	} 
> }
> ```
##### Thread interference
Una **thread interference** avviene quando due operazioni su due thread differenti agiscono sullo stesso dato.
Essendo operazioni non atomiche è difficile ottenere un risultato prevedibile

> [!example] Esempio di thread interference
> ```java
> class Counter {
>     private int c = 0;
>     public void increment() {
>         c++;
>     }
>     public void decrement() {
>         c--;
>     }
>     public int value() {
>         return c;
>     }
> }
> ```
> 
> L’operazione `c++ (c--)` non è atomica, poiché
> 1. Recupera il valore di `c`
> 2. Incrementa (o decrementa) il valore assegnato
> 3. Assegna a `c` il nuovo valore
> 
> Supponiamo che ci siano due thread, `A` e `B`, il primo richiami la funzione `increment` e il secondo `decrement`:
> ![[Pasted image 20260506114536.png]]
> 
##### Memory incosistency
Si verifica quando due thread hanno una visione inconsistente di uno stesso dato.
Si considera un tipico scenario in cui una variabile inizializzata al valore $0$ sia accessibile simultaneamente a due entità, definite come Thread `A` e Thread `B`. Qualora il Thread `A` procede all'incremento della variabile e, nel medesimo istante temporale, il Thread `B` proceda alla stampa a schermo della stessa, sussiste la concreta possibilità che il Thread `B` restituisca il valore originario di $0$ poiché l'operazione di aggiornamento del Thread `A`, benché avviata, non si è ancora conclusa.
#### Sincronizzazioni delle istruzioni
È possibile anche sincronizzare soltanto una porzione di istruzioni, utile quando si richiede che soltanto quella porzione venga "velocizzata"

> [!example] Esempio di sincronizzazione di funzione
> ```java
> public void addName(String name) { 
> 	synchronized(this) { //in questo caso sincronizziamo solo la modifica di lastName e di nameCount. L’istruzione add non richiede sincronizzazione. Stiamo inserendo un lock sull'oggetto
> 		lastName = name;
> 		nameCount++; 
> 	} 
> 	nameList.add(name); 
> }
> ``` 
#### Problemi della programmazione concorrente
Ci sono diversi problemi presenti nella programmazione concorrente:
 - **Deadlock**: due o più thread sono bloccati in modo indefinito perché ognuno attende la fine dell’altro
 - **Starvation**: un thread non riesce ad accedere ad alcune risorse perché sono utilizzate avidamente da altri thread
 - **Livelock**: un thread `A` in genere agisce in risposta di un altro thread `B`, se `B` agisce in risposta di un altro thread C allora i thread proseguiranno in maniera discontinua
### Programmazione in rete
La programmazione in rete, nota anche come programmazione distribuita, è sempre risultata complessa e particolarmente soggetta ad errori data dalla necessità da parte del programmatore di conoscere tutto il

Nel linguaggio Java, la programmazione in rete subisce una notevole semplificazione, venendo astratta in modo efficace attraverso l'uso di un set dedicato di classi.
Queste classi gestiscono dei file di lettura e scrittura che non si trovano nella macchina locale ma in una remota, con totale autonomia di come processare un informazione inviata o richiesta.

Il modello di programmazione adottato si fonda sull'incapsulamento (**wrapping**) di una connessione di rete, definita socket, all'interno di un flusso (**stream**) di oggetti. Grazie a questa astrazione è possibile impiegare le medesime invocazioni di metodo utilizzate per gli stream dei file.

Grazie alla natura multipiattaforma di Java, tutte le specificità e i dettagli di basso livello della rete vengono gestiti direttamente dalla Java Virtual Machine (JVM) e dall'installazione locale dell'ambiente Java
#### Identificazione di una macchina
Per instaurare una comunicazione efficace con un altro nodo della rete, risulta indispensabile identificare in maniera univoca il destinatario.
L'identificazione del nodo avviene mediante l'indirizzo IP (Internet Protocol).
Esistono fondamentalmente due approcci per risolvere e identificare un indirizzo IP: 
- L'utilizzo del DNS (Domain Name System), ricorrendo a stringhe alfanumeriche come ad esempio $www.di.uniba.it$
- L'impiego della dot notation, che prevede l'uso di sequenze numeriche come $183.201.181.10$.

In Java, la rappresentazione dell'indirizzo IP, in entrambe le notazioni appena descritte, è affidata a una classe specifica denominata `InetAddress`, la quale è inclusa nel package `java.net`. 
Questa classe mette a disposizione del programmatore il metodo statico `InetAddress.getByName()`, il cui scopo è restituire un'istanza di `InetAddress` partendo dal nome dell'host o dal suo indirizzo IP.

> [!example] Esempio di socket
> ![[Pasted image 20260506152705.png]]
#### Uso del port
Su una macchina singola può ospitare più servizi contemporaneamente, per questo l'indirizzo IP da solo non è sufficiente. 

Quando si imposta un client o un server è necessario scegliere la “porta” (port) sul quale sia il server che il client decidono di connettersi.

Il port non è una locazione fisica su una macchina ma è una astrazione software, tipicamente ogni servizio è associato ad un singolo numero di port su una macchina server. Il programma clienti quindi non deve conoscere soltanto l'indirizzo IP, ma anche la porta giusta.
#### Socket
All'interno dell'ecosistema Java, la connessione verso una macchina remota viene stabilita attraverso l'utilizzo dei **socket**. Il socket è un astrazione software usata per rappresentare i terminali di connessioni di due macchine

Le librerie di Java mettono a disposizione due classi principali basate sugli stream per la gestione dei socket: 
- La classe `ServerSocket`, impiegata dal server per rimanere in ascolto delle richieste di connessione in ingresso
- La classe `Socket`, utilizzata dal client per inizializzare attivamente la connessione

Creando un socket in Java, si ottengono un `InputStream` e un `OutputStream` (o, con appropriate conversioni, un Reader e un Writer) al fine di abilitare la connessione in modo simile a un I/O su stream di oggetti.

Una volta che un client richiede una connessione socket, il `ServerSocket` restituisce (mediante il metodo `accept()`) un `Socket` corrispondente attraverso il quale la comunicazione può avvenire dal lato server, creando una connessione **Socket-To-Socket**

Durante la fase di inizializzazione, la creazione di un `ServerSocket` richiede esclusivamente l'indicazione di un numero di porta, omettendo l'indirizzo IP poiché esso coincide implicitamente con quello della macchina su cui il server è in esecuzione.
Al contrario, la creazione di un `Socket` lato client impone la specificazione di entrambi i parametri, in quanto server e client risiedono generalmente su elaboratori distinti. 

Il socket generato dalla chiamata `ServerSocket.accept()` incapsulerà automaticamente sia le informazioni del client sia quelle del server. 
Raggiunto questo punto, si possono invocare i metodi `getInputStream()` e `getOutputStream()` sui rispettivi socket per ricavare gli stream di dati, i quali supportano nativamente l'impiego delle classi di buffering e di formattazione del testo.
#### Servire più client
Per consentire al server di servire più client in maniera simultanea, è indispensabile ricorrere al multithreading. 
Il design pattern di base per affrontare tale casistica prevede l'istanziamento di un singolo `ServerSocket` sul server, seguito dalla chiamata bloccante al metodo `accept()`, che pone il processo in attesa attiva di una connessione. 
Nel momento in cui una connessione viene stabilita e il metodo `accept()` conclude la sua esecuzione restituendo il socket di comunicazione, quest'ultimo viene immediatamente passato a un nuovo thread appositamente istanziato per servire le richieste di quello specifico client. Nel frattempo, il thread principale del server non si arresta, ma si riavvia in un ciclo perpetuo richiamando nuovamente il metodo `accept()`, mettendosi così in attesa della successiva richiesta di connessione.
#### Esempi di codice
Poichè gli esempi di codice sono molto prolissi, rimando direttamente al materiale fornito dal professore sulla sua [pagina Github](https://github.com/pippokill/mapB_2526/tree/main/lab/src/main/java/di/uniba/map/b/lab/rete)
### Java RESTful
Il REST (**Representational State Transfer**) è un tipo di architettura software per i sistemi distribuiti, basato sulla trasmissione di dati tramite protocollo HTTP senza ulteriori livelli.

I sistemi REST non prevedono il concetto di sessione (anche chiamati **stateless**), ma prevedono una struttura URI (Uniform Resource Identifier) ben definita, che identifica univocamente una risorsa o un insieme di risorse.
#### Principi di una REST
Nella REST, lo stato dell'applicazione e le funzionalità sono divisi in **risorse web**, ognuna di esse unica e indirizzabile usando la sintassi delle URI.
Comunemente viene definita un’interfaccia uniforme per la condivisione delle risorse che permette il trasferimento di stato tra client e risorse, attraverso:
- Un insieme vincolato di operazioni ben definite
- Un insieme vincolato di contenuti
- Un protocollo che è:
	- **Client-server**: I ruoli del client e del server sono ben separati, diventa più facile poter scalare con il tempo e server e client possono essere sostituiti e sviluppati indipendentemente fintanto che l'interfaccia non viene modificata.
	- **Privo di stato (stateless):** La comunicazione client-server è vincolata in modo che nessun contesto client venga memorizzato sul server tra le richieste. Ciascuna richiesta dai vari client contiene tutte le informazioni necessarie per richiedere il servizio e lo stato della sessione è contenuto nel client
	- **Memorizzabile in cache**: I client possono mettere in cache le risposte. Queste devono in ogni modo definirsi implicitamente o esplicitamente cacheable o no, in modo da prevenire che i client possano riutilizzare stati vecchi e dati errati.
	- **A livelli**: il sistema è realizzato “a strati” (layer). Ciò rende possibile, per esempio, pubblicare le API in un server, memorizzare i dati in un secondo server e gestire l'autenticazione delle richieste in un terzo server.
#### Risorse
Una risorsa è una fonte di informazioni alla quale si può accedere attraverso un identificativo univoco (URI). 
Per utilizzare tali risorse sia il client e il server comunicano attraverso un **protocollo comune** (HTTP) e che sia il serve che il client abbiano un **meccanismo di rappresentazione** (come JSON o XML).
RESTful contrariamente ad altri protocolli non definisce standard per la rappresentazione o per le modalità di comunicazione.
##### Rappresentazione dei dati
Un formato molto utilizzato per lo scambio dei dati è **JavaScript Object Notation (JSON).** Un JSON è racchiuso tra parentesi graffe è può contenere diversi tipi di dati.

> [!example] Esempio di rappresentazione JSON
> ![[Pasted image 20260508195551.png]]
##### Definizione dei metodi
Progettare una API REST prevede la definizione dei **metodi/servizi**. 
Ogni metodo ha un suo **path**, ossia un identificativo univoco che coincide con la URL da utilizzare per richiedere il metodo tramite protocollo HTTP. Ad ogni metodo deve essere associato anche il relativo verbo HTTP da utilizzare.

Le URL possono avere dei parametri che possono essere utilizzati per scambiare informazioni con il server, ad esempio l’id della risorsa da recuperare.

> [!example] Esempio di risorsa da recuperare tramite URL
> Supponiamo di avere un metodo per il recupero di un libro da un store:
> ```HTTP
> http://store.api.org/book?id=12 
> http://store.api.org/book/12
> ```
> Riprendendo l’esempio precedente il client potrebbe utilizzare uno dei due servizi semplicemente effettuando una richiesta HTTP/GET per ottenere un libro tramite il suo id (es. 12):
> ```JSON
>  {
> 	 "id": 12, 
> 	 "title": "Alice in Wonderland", 
> 	 "price": 12.50 
>  }
> ```
#### Java e JSON
Per poter integrare JSON con il linguaggio Java utilizzeremo una libreria di nome **GSON**
> [!example] Esempio di integrazione con il libro
> ![[Pasted image 20260509113235.png]]
> Possiamo vedere come la classe GSON implementi i metodi `toJSON()` per convertire i parametri passati in un file JSON a partire da un oggetto e come possa fare la conversione inversa con `fromJSON()`
#### JAX-RS
Jakarta RESTful Web Services, (JAX-RS) è una API di Java che fornisce supporto nella creazione di servizi Web secondo il modello architetturale REST. 
JAX-RS utilizza le **annotazioni**, per semplificare lo sviluppo e la distribuzione di client e endpoint di servizi Web.

> [!example] Esempio di annotazione
> ![[Pasted image 20260509113735.png]]
##### Annotazioni
Esistono varie annotazioni all'interno di JAX-RS
- **@Path**: specifica il path all’interno della URL dove sarà disponibile il servizio la cui logica è realizzata all’interno di un metodo. Il path può essere sia a livello di classe sia a livello di metodo
- **@Produces/@Consumes**: specifica il data type1 che viene prodotto e/o consumato
- **@GET, @POST, @DELETE...**: specificano il verbo HTTP con il quale sarà richiamato il relativo servizio
- **@QueryParam**: identifica un parametro che verrà passato tramite parametro della URL
- **@PathParam**: identifica un parametro che verrà passato tramite path della URL

> [!example] Esempio di annotazioni per metodo
> ![[Pasted image 20260509123345.png]]![[Pasted image 20260509123400.png]]

> [!example] Esempio libri
> ![[Pasted image 20260509123426.png]]![[Pasted image 20260509123447.png]]
> ![[Pasted image 20260509123522.png]]

#### Server HTTP
Dopo aver creato le classi che forniscono i servizi con le relative annotazioni è necessario avere a disposizione un server HTTP che si occupi di gestire le richieste dai vari client.

Per semplicità utilizzeremo [grizzly](https://eclipse-ee4j.github.io/jersey.github.io/) , che è un server HTTP già incluso in Jersey, un framework REST per Java che permette di realizzare sia client sia server REST.
> [!example] Esempio di server HTTP con grizzly
> ![[Pasted image 20260509125217.png]]
> ![[Pasted image 20260509125231.png]]
> ![[Pasted image 20260509125240.png]]
> ![[Pasted image 20260509125250.png]]

#### Client REST
Dopo aver realizzato i nostri servizi REST e reso disponibile il server HTTP siamo pronti ad accettare le richieste ricevute attraverso il protocollo HTTP

Un client non deve far altro che preparare la richiesta HTTP in base alle specifiche del servizio e inoltrarla utilizzando il protocollo HTTP e il corrispettivo verbo previsto dal servizio. Java mette a disposizione nel suo framework delle classi per gestire le richieste HTTP

> [!example] Esempio di client con Jersey
> Utilizzando il framework Jersey è semplice inviare delle richieste attraverso l’utilizzo delle classi Client e WebTarget.
> ![[Pasted image 20260509124924.png]]
> Il client permette di effettuare le connessioni HTTP in modo semplice. 
> Il WebTarget memorizza la URL dove sono disponibili i servizi e attraverso i metodi path, queryParam, request permette di costruire la richiesta HTTP.
> 
> L’oggetto di tipo Response contiene il risultato della risposta HTTP.

> [!example] Esempio di richiesta PUT con invio di un JSON
> ![[Pasted image 20260509125103.png]]
### SWING
SWING è il framework di Java che permette la realizzazione di interfacce grafiche (chiamate anche GUI).
Si utilizza con i packages di riferimento `javax.swing, javax.swing.event`.

Questo pacchetto permette di creare:
- Finestre, Form, Dialog 
- Menu, Pulsanti, Check-box, Combo-box 
- Alberi, Tabelle 
- Layout, Look&Feel

> [!info] La mia prima applicazione (Netbeans+Swing)
> NetBeans mette a disposizione degli strumenti che facilitano la creazione delle GUI, che introducono:
> - Drag and drop dei componenti
> - Auto-generazione del codice 
> - Strumenti per la gestione del layout dei componenti
> Per trovare degli esempi conviene visionare il file [[3.1 - (Slide Esempi) Prima Applicazione in Java SWING.pdf]]
#### Contenitori
Java Swing mette a disposizione tre tipi di contenitori:
- JFrame
- JDialog
- JApplet

Ogni componente deve far parte di una gerarchia di componenti connessi ad un contenitore radice (chiamato anche **top level**), ognuno di questi componenti poi può appartenere ad un solo contenitore.
Ogni contenitore top-level è associato ad una vista (ovvero gli oggetti effettivamente visibili su schermo).
> [!info] Gerarchia dei componenti 
> ![[Pasted image 20260525105232.png]]
> Ogni programma SWING deve avere almeno un contenitore top-level (questo contenitore è la radice della gerarchia delle componenti)
> Per ogni contenitore top level è possibile aggiungere un menu.

Per aggiungere componenti ad un contenitore è necessario usare il metodo `add()`
> [!example] Esempio di metodo `add()`
> ```java
> frame.getContentPane().add(yellowLabel, BorderLayout.CENTER)
> ```
> 
> `getContentPane()` restituisce un oggetto Jcomponent

> [!info] Il root Pane
> Ogni finestra è suddivisa in diversi pannelli
> ![[Pasted image 20260525110222.png]]
#### JComponent
JComponent è una classe che mette a disposizione un set di metodi per modificare aspetto e comportamento dei componenti.
Questa eredita da container che a sua volta eredita da Component.

JComponent in particolare implementa:
- Modifica dell'aspetto del componente (colore, bordo, tipo cursore)
- Monitoraggio dello stato (gestione di un PopupMenu, cambio nome, non visibile/visibile, abilita/disabilita, modifica del ToolTip)
- Gestione degli eventi
- Disegno degli oggetti
- Gestione della gerarchia degli oggetti (aggiungi, rimuovi)
- Modifica della disposizione degli oggetti (Layout)
- Dimensione e posizione del componente
##### Buttons, CheckBoxes, RadioButtons
I pulsanti in Swing derivano tutti dalla classe astratta `AbstractButton`. Tra le implementazioni principali troviamo:
- **JButton**: un classico pulsante 
- **JCheckBox**: una check box 
- **JRadioButton**: un singolo pulsante di un gruppo di pulsanti di opzione 
- **JMenuItem**: una voce di un menu 
- **JCheckBoxMenuItem**: una voce di un menu che è una check box 
- **JRadioButtonMenuItem**: una voce di un menu che è un pulsante di opzione 
- **JToggleButton**: permette di creare un bottone a due stati utilizzando due check box o due radio button
##### Color Chooser
La selezione di un colore è implementata attraverso la classe `JColorChooser`, la quale offre diverse modalità di interazione per l'utente finale
Le informazioni relative al colore selezionato vengono memorizzate all'interno di un modello denominato `ColorSelectionModel()`; ogni istanza di `JColorChooser()` possiede una propria copia isolata di questo modello.
Per intercettare e gestire attivamente la selezione di un nuovo colore da parte dell'utente, è necessario implementare la specifica interfaccia `ChangeListener()`

> [!example] Esempio di color chooser
> ![[Pasted image 20260525132655.png]]
> ![[Pasted image 20260525132720.png]]
##### ComboBox
Il componente Combo Box consente all'utente la selezione di un valore all'interno di una serie di opzioni predefinite ed è gestito dalla classe `JComboBox`.
Questa componente può essere configurata come non editabile, vincolando la scelta alle sole voci presenti nell'elenco, oppure editabile, permettendo l'inserimento manuale di un valore da parte di un utente

> [!example] Esempio di ComboBox editabile
> ![[Pasted image 20260525150108.png]]

La visualizzazione degli elementi avviene tramite un renderizzatore di default che mostra stringhe o icone, oppure richiama il metodo `toString()` nel caso di altri tipi di oggetti più complessi