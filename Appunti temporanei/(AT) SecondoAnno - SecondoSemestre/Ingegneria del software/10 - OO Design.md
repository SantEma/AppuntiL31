Nel desing della programmazione OO adottiamo una **prospettiva software**, dove gli elementi di un modello corrispondono agli elementi di un sistema software orientato agli oggetti ed è **indipendente dai vari linguaggi di programmazione**.

Per descrivere le relazioni tra oggetti e classi presenti in un sistema costruito con metodologia OO si usa il **diagramma delle classi con prospettiva software**.
## Classe
```Python
public class Dialler{
}
```
Si rappresenta tramite il seguente disegno madre
![[Pasted image 20260505102637.png]]

## Attributi
Gli attributi generalmente sono **privati** e rappresentano le **proprietà strutturali** degli oggetti di una classe.
![[Pasted image 20260505102331.png]]
In un linguaggio OO, gli attributi corrispondono al nome di una **variabile di istanza** della classe.
```Python
public class Dialler{
	private Vector digits;
	int nDigits;
	public void digit(int n);
	protected boolean recordDigit(int n);
}
```
## Operazioni
Sono mostrate in UML nel segmento inferiore e disegnate nel seguente modo:
![[Pasted image 20260505102943.png]]
Rappresentano le **azioni** che si possono eseguire sugli oggetti di una classe. A differenza degli UML precedenti, nel diagramma delle classi è utile e doveroso mostrare i nomi delle operazioni, dato che sono i lavori principali di una classe.

Nei linguaggi OO queste azioni corrispondono ai **metodi** della classe.

La visibilità delle operazioni è per default **pubblica**, se non lo sono conviene specificarlo con $-$ nell'UML o possono addirittura essere **protette**, dimostrabili tramite *#*, ma è un caso abbastanza particolare da gestire.

Nell'UML generalmente non si mostrano le **operazioni basilari**, come il `GetAtt` o il `SetAtt`, o anche il **costruttore stesso**, dato che è facilmente intuibile la loro presenza nel codice. Rendendo così vantaggiosa la lettura dell'UML e avendo uno schema più compatto.

![[Pasted image 20260505103429.png]]
La responsabilità della classe serve per poter capire, tramite brevi commenti, cosa andranno a fare le funzioni che si eseguono all'interno della classe.
## Associazioni
Le associazioni tra più classi vengono rappresentate nel diagramma delle classi tramite un collegamento tra un attributo di una classe e lo stesso attributo di appartenenza in un altra classe.

Le associazioni hanno un verso di navigazione. Il verso della freccia ci fa capire quale classe conosce il tipo presente nell'altra classe.

L'associazione è una rappresentazione alternativa della **proprietà strutturale**, il tipo base presente in una classe viene quindi cambiato in un altra classe con le sue informazioni.
![[Pasted image 20260505104243.png]]
### Molteplicità
>[!WARNING] Nota
>Alcuni professori preferisceono la notazione con le frecce nelle associazioni di molteplicità e non i vari pallini

La molteplicità specifica quante istanze di una classe possono essere associate con una singola istanza di un’altra classe. Il simbolo di molteplicità adiacente alla classe 2 indica quante istanze della classe 2 possono avere legami con una singola istanza della classe 1.
![[Pasted image 20260505104442.png]]
## Ruoli
Non è possibile definire dell'etichette alle associazioni ma si possono definire dei **ruoli**.
Il ruolo indica in modo esplicito il nome della proprietà di una classe rappresentata come associazione.
![[Pasted image 20260505104653.png]]
Dove `productSpec` è il seguente codice:
![[Pasted image 20260505104733.png]]
## Dipendenza
La dipendenza in UML delle classi viene rappresentata tramite **freccia tratteggiata** per distinguerla dall'associazione.
Si ha una dipendenza tra classi quando una classe **è a conoscenza di un'altra classe**, dove il cambiamento della classe $A$ può modificare la classe $B$, che dipende da essa (questo principio vale anche per le associazioni e le generalizzazioni).
![[Pasted image 20260505105147.png]]
## Aggregazione e composizione
L’aggregazione non ha un significato distinto da una generica associazione e quindi non c’è bisogno di usarla.
A livello teorico però, la composizione è un’associazione in cui:
- L’oggetto contenitore è l’unico responsabile della creazione degli oggetti contenuti
- La cancellazione dell’oggetto contenitore ha come effetto la cancellazione degli oggetti contenuti
- La copia dell’oggetto contenitore ha come effetto la copia degli oggetti contenuti
![[Pasted image 20260505105116.png]]
## Vincoli
Rappresentano la possibilità di inserire qualche dettaglo agli elementi di un diagramma delle classi.
Si possono esprimere in modo informale tra **parentesi graffe** e **Object Constraint Language (OCL)** è un linguaggio formale per specificare i vincoli.
![[Pasted image 20260505105259.png]]
## Generalizzazione
Molto più importante dei concetti precedenti è proprio la rappresentazione grafica delle **generalizzazioni**.
Questo concetto ci permette di individuare la **condivisione delle caratteristiche delle classi**, ove le caratteristiche sono operazioni o attributi.

Gli oggetti delle **sottoclassi** ereditano le stesse caratteristiche delle **superclasse** (classe generale).

Una sottoclasse può definire delle **estensioni**, ovvero caratteristiche aggiuntive e possono eseguire un **overriding**, ossia una modifica dell'implementazioni delle operazioni ereditata. 

>[!NOTE] Uso comune dell'overriding
>Molto spesso l'overriding anche se permesso non è la soluzione migliore e ben vista per risolvere i problemi di modifica delle operazioni per le classi figlie

![[Pasted image 20260505105648.png]]
## Classi astratte e concrete
Una classe astratta è una classe che non può essere direttamente istanziata e contiene delle operazioni **astratte**, prive di implementazione che vengono implementate dalle classi figlie in base all'uso che ne devono fare.
Una sottoclasse di una classe astratta viene definita **classe concreta** ed è l'unico metodo in cui si possono implementare le operazioni della classe astratta e istanziarne gli oggetti.
![[Pasted image 20260505105926.png]]
Le classi astratte hanno portato all'uso delle **interface**.
### Interface
Un'interfaccia è un costrutto puro basato sulla classe astratta in grado di estendere una o più interfacce.
Una classe **realizza** un'interfaccia se è sostituibile a essa, poiché ne implementa una o più operazioni astratte.
Una classe **richiede** una sua interfaccia se necessita delle sue operazioni per funzionare, si crea una dipendenza da essa e una gerarchia d'ordine.

In UML esistono diversi modi per rappresentare un Interface e chi la richiede:![[Pasted image 20260505110315.png]]
In passato si rappresentava in maniera più semplice tramite la **rappresentazione lollipop**:
![[Pasted image 20260505110423.png]]
o tramite quella **conica**:
![[Pasted image 20260505110431.png]]
Nessuno dei due metodi però permette di identificare chi ha richiesto l'interfaccia.
# Costruzione di diagrammi delle classi con prospettiva software funzionanti
Queste sono le regole generali da seguire per avere un ottimo diagramma delle classi funzionante e dimostrabile:
- **Non cercare di modellare tutto il sistema con un singolo diagramma**
- Ogni diagramma deve avere un suo criterio:
  - Diagramma che mostra le classi che collaborano nella realizzazione di una user story
  - Diagramma dei package
  - Diagramma che mostra la gerarchia di classi
- Non è importante distinguere correttamente tra associazioni e dipendenza ma è **fondamentale** indicare **precisamente la direzione dei riferimenti ad altre classi**. Poiché crea confusione e dà il senso di non conoscere quale classe richiede informazioni da un altra classe.
- Principio di **parsimonia**, non mostrare tutto ciò che è presente nel codice ma solamente quelle significative per il diagramma in questione.

# Modellare il comportamento
Per modellare il comportamento di un progetto software si fa ricorso alla **documentazione** del comportamento di un gruppo di oggetti che realizzano un singolo scenario di utilizzo del sistema. Tale comportamento è visualizzabile tramite il **diagramma di sequenza**.
## Diagramma di sequenza
Il diagramma mostra l'interazione tra oggetti con enfasi sulla sequenza dei messaggi.
Nel diagramma di sequenza si hanno vari elementi, primi tra tutti sono i **partecipanti**.
### Personaggi
I **partecipanti** del diagramma, i quali sono **oggetti** rappresentati come un rettangolo in cima a una linea tratteggiata.
La linea tratteggiata rappresenta **lo scorrere del tempo** detta **Linee di vita**.
![[Pasted image 20260506170406.png]]
### Messaggi
Nel diagramma di sequenza esistono anche i **messaggi**, ovvero la comunicazione tra oggetti realizzata tramite la chiamata dei metodi.
I messaggi possono essere anche **speciali**, come il `create`, il `return` o la `destroy` di un oggetto.
![[Pasted image 20260506173850.png]]
### Barre di attivazione 
Le barre di attivazione sono sottili **rettangoli** posti sulla linea di vita di un oggetto e servono ad indicare quando il partecipante è attivo nell'interazione.
La presenza di questo elemento nel diagramma rende ridondante l'uso delle linee di **restituzione del controllo**.
![[Pasted image 20260506174435.png]]
![[Pasted image 20260506174539.png]]
![[Pasted image 20260506174802.png]]
## UML 2
In **UML 2** esistono dei simboli che non era possibile utilizzare prima, detti **frame di interazione**. Il frame di interazione è una cornice intorno ad una parte del diagramma di sequenza, tra gli elementi principali vi si ha:
- **opt** che sostituisce gli `if`
- **alt** che serve per `l'else`
- **loop** che serve per i cicli iterativi
![[Pasted image 20260506175111.png]]

**Esempio Alt**:
![[Pasted image 20260506175438.png]]
**Esempio loop**:
![[Pasted image 20260506175454.png]]
**Esempio opt**:
![[Pasted image 20260506175505.png]]
# Attività dell'OO design
L'attività di OO design serve per valutare altre vie percorribili nella realizzazione del sistema, analizzando i requisiti, i moduli, ecc...
Serve specialmente per tenere traccia di cosa si è fatto e rispondere alla domanda: *"cosa si è fatto qui?"*, infatti la **documentazione** è fondamentale in questa fase per portare traccia degli avanzamenti e le modifiche.

Avviene il riuso del **design pattern**, delle librerie e del **framework OO** e su quest'ultimi si applica il principio di OO design per evitare il **debito tecnico**.
## Principi di OO desing
I principi dell'OO desing sono:
- Information hiding
- Alta coesione
- Basso accoppiamento
- Presentazione separata
- Do Not Repeat Yourself **(DRY)**
- **SOLID method**


Ogni elemento di conoscenza deve avere una sola, non ambigua, autorevole rappresentazione all'interno di un sistema

Qualsiasi parte significativa di un metodo dovrebbe essere implementato in unica zona apposita del codice sorgente, evitando **cloni** dati dal **copy-paste** e creando astrazioni in caso ci dovessimo imbattere in ripetizioni del concetto.

### SOLID
![[Pasted image 20260512115803.png]]

