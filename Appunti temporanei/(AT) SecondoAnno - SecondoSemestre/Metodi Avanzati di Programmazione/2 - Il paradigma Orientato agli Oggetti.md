## Introduzione
Un difetto fondamentale della programmazione imperativa è che **le variabili globali sono potenzialmente accessibili da ogni parte del programma**. I grandi programmi che permettono l’accesso alle variabili globali tendono ad essere ingestibili, la ragione è che nessun modulo che accede ad una variabile globale può essere sviluppato e compreso indipendentemente da altri moduli che pure accedono alla medesima variabile

Il rimedio fu ovviamente **l'information hiding**, ossia quello di incapsulare in un modulo ogni variabile globale insieme a un gruppo di operazioni autorizzate ad accedervi, gli altri moduli non possono accedervi direttamente ma indirettamente chiamando queste operazioni. Il loro nome era proprio quello di **oggetti**

In alcuni linguaggi operativi era già possibile definire degli **oggetti**, ma:
- Il concetto dell'oggetto non fa parte della base del linguaggio, il programmatore deve controllare come venga utilizzati
- Quando sono introdotti, non sono trattati come **cittadini di prima classe**, ossia non avevano tutte le funzionalità previste dal paradigma
## Paradigma Object Oriented
Confrontando il paradigma orientato a oggetti rispetto a quello imperativo si può dire che esso costituisce:
- Una **evoluzione**, in quanto permette agli oggetti di essere cittadini di prima classe
- Una **rivoluzione**, in quanto gli oggetti assumono un ruolo fondamentale nella progettazione e nella programmazione. Ora l'information hiding e l' incapsulamento sono principi cardine nel paradigma orientato a oggetti
### Classificazione di Wegner
I linguaggi di programmazione si classificano in:
- **Object-based**: supportano la nozione di oggetto (come il linguaggio Modula-2), qui non sono ancora trattati come cittadini di prima classe
- **Class-based**: supportano la nozione di oggetto e classe (come il linguaggio Ada-83)
- **Object-oriented**: supportano la nozione di oggetto, classe, ereditarietà (Smalltalk, C++, Java, …)
> [!info] Domanda di esame: Quali sono le caratteristiche di un linguaggio ad oggetti?
> Quelli che supportano nozioni di oggetto, classe e ereditarietà
## Gli oggetti
Gli oggetti quindi sono questo particolare costrutto che permettono di incapsulare **uno stato e un comportamento**:
- Lo **stato** è identificato dal contenuto di una certa area di memoria (quindi dalle variabili)
- Il **comportamento** è definito da una collezione di procedure e funzioni (chiamate **metodi**) che possono operare sulla rappresentazione dell’area di memoria associata all'oggetto.

Un oggetto implementato bene quindi permette la modifica delle variabili soltanto tramite delle sue funzioni dedicate
> [!example] Esempio di oggetto
> ![[Pasted image 20260312113300.png]]
> Le variabili e i metodi definiti nell’oggetto ‘palla’ stabiliscono lo stato e il comportamento che sono rilevanti all’uso della palla nel gioco elettronico
### Identificatore di oggetto
Un oggetto ha la sua **identità**, cioè è riconoscibile indipendentemente dal suo stato corrente. Per questo ogni oggetto ha un identificatore di oggetto (object identifier, OID) che lo identifica univocamente. In alcuni contesti gli OID sono anche detti **riferimenti (references)** (in alcuni linguaggi prende questo nome poichè coincide con l'indirizzo di memoria con l'oggetto utilizzato)

Un identificatore di oggetto è **immutabile**, cioè non può essere modificato da una qualche opzione di programmazione. Cambiare l’OID di un oggetto equivale alla cancellazione dell’oggetto e alla creazione di un altro oggetto con lo stesso stato.

Il concetto di uguaglianza non è uguale a quello di identificatore, infatti si può avere lo stesso stato di due oggetti con due OID differenti.

Normalmente gli OID sono assegnati in modo automatico agli oggetti, sicché non hanno un significato nel mondo reale. In molti ambienti di programmazione object-oriented, l’OID corrisponde all'indirizzo dell’area di memoria che conserva lo stato dell’oggetto. Quasi mai il programmatore utilizza esplicitamente i riferimenti, generalmente questi vengono legati a delle variabili e si fa riferimento agli oggetti mediante gli identificatori di variabile, ma variabili distinte potrebbero far riferimento al medesimo oggetto, in questo caso si hanno degli **alias**.

La presenza di alias non significa che un oggetto non è identificato univocamente, ma semplicemente che **diversi identificatori di variabile sono stati legati al medesimo riferimento di oggetto**. 
Lo stato di un oggetto può anche contenere il riferimento ad un altro oggetto, si dice quindi che un **oggetto punta ad un altro**. Il puntamento è asimmetrico, ossia questo puntamento va in unica direzione.
## UML
L'UML è un linguaggio visuale utilizzato per 
- Definire
- Progettare 
- Realizzare 
- Documentare

È un linguaggio di **rappresentazioni dei sistemi universale** (sistemi eterogenei per architettura, tecnologie, tipologia applicativa). L'UML è di supporto sia alla progettazione di un nuovo sistema che alla documentazione di un software esistente.

Essendo molto versatile può essere anche utilizzato in molte fasi del ciclo di vita del software (come nelle relazioni clienti-fornitori o ingegnere-ingegnere) senza scendere nei dettagli di un linguaggio di programmazione.

La notazione, sintassi e semantica sono standard secondo le specifiche UML. 
L'UML permette di usare una notazione universale per illustrare alcuni concetti del paradigma orientato a oggetti, senza fare così riferimento a un particolare linguaggio di programmazione.
Ogni simbolo in UML ha una **semantica ben definita** che ne permette **l’univoca interpretazione** fra diversi interlocutori e strumenti software
### Modellazione Object-Oriented
Nella modellazione object-oriented le componenti elementari sono **l’oggetto e la classe**:
- Un oggetto è qualcosa tratta generalmente dal vocabolario dello spazio del problema o dello spazio della soluzione. Ogni oggetto ha un identità, stato e comportamento.
- Una classe è una descrizione di un insieme di oggetti omogenei

Visualizzare, specificare, costruire, e documentare sistemi object-oriented è esattamente lo scopo dello UML
### Oggetti (Istanze in UML)
In UML un oggetto (o istanza) è graficamente rappresentato in questo modo:
![[Pasted image 20260312121838.png]]
Quindi è possibile indicare:
- Solo il nome (identificatore) dell'istanza
- Nome dell'istanza e dell'astrazione (la classe) a cui appartiene
- Solo il nome dell’astrazione, qualora non si conosca a priori il nome dell’istanza
- Un’istanza orfana, se non si conosce a priori la sua astrazione

Lo stato di un oggetto può essere rappresentato in modo astratto, oppure indicando esplicitamente i valori assunti dagli attributi dell’oggetto
![[Pasted image 20260312122252.png]]
## Classi
**Una classe è la descrizione di una famiglia di oggetti che condividono la stessa struttura** (gli attributi) **e il medesimo comportamento** (operazioni).
Nella programmazione OO ogni oggetto è un’istanza di una classe, cioè un oggetto non può essere ottenuto se non si definisce la sua classe di appartenenza. Analogamente nella modellazione OO le istanze **esistono in quanto ci sono le loro astrazioni**.
I dettagli della realizzazione di una classe sono normalmente nascosti.
Ogni classe ha una doppia componente
1. **Una componente statica**, ossia i dati, costituita da campi o attributi dotati di nome, che contengono un valore. I campi caratterizzano lo stato degli oggetti durante l’esecuzione del programma.
	Questi si distinguono in base al loro ambito d'azione (**scope**):
	- **Attributi d’istanza**: sono associati ad una istanza e hanno un tempo di vita pari a quello dell’istanza alla quale sono associati.
	- **Attributi di classe**: sono associati alle classi e condivisi da tutte le istanze della classe. Il loro tempo di vita è lo stesso della classe.
	Gli attributi di istanza contribuiscono a caratterizzare lo stato di ogni singolo oggetto, mentre gli attributi di classe contribuiscono a definire il fattore comune allo stato di tutti gli oggetti di una classe.  
 2. **Una componente dinamica**, ossia i metodi (o operazioni), che rappresentano il comportamento comune degli oggetti appartenenti alla classe, cioè i servizi che possono essere richiesti a un oggetto di una classe. I metodi manipolano gli attributi.
     I metodi possono essere classificati in:
     - **Metodi costruttori**: sono invocati per creare (istanziare) gli oggetti e inizializzarli
     - **Metodi di accesso**: restituiscono astrazioni significative dello stato di un oggetto
     - **Metodi di trasformazione**: modificano lo stato di un oggetto
     - **Metodi distruttori**: sono invocati quando si rimuovono gli oggetti dalla memoria
      I metodi di accesso e trasformazione possono essere distinti in:
      1. **Metodi di istanza**: operano su almeno un attributo di istanza, pertanto possono essere invocati solo specificando l’istanza
      2. **Metodi di classe**: operano esclusivamente su attributi di classe, pertanto possono essere invocati specificando la classe. Si possono invocare metodi di classe anche quando non è stato istanziato alcun oggetto per quella classe