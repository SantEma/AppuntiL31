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


Per generare numeri casuali nell'intervallo $[0;1)$ tramite `Math.random()`, il cui risultato può essere scalato moltiplicandolo per un intero. Nel caso si voglia generare una serie più articolata di numeri casuali è consigliato l'utilizzo della classe dedicata `java.util.Random`
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

L’uguaglianza degli oggetti in questa sottoclasse è definita dai metodi equals e hashCode della classe `Object`

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

