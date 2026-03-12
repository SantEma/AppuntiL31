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
Lo stato di un oggetto può anche contenere il riferimento ad un altro oggetto, si dice quindi che un **oggetto punta ad un altro**. Il puntamento è asimmetrico