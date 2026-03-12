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
- **Object-based**: supportano la nozione di oggetto (come il linguaggio Modula-2)
- **Class-based**: supportano la nozione di oggetto e classe (come il linguaggio Ada-83)
- **Object-oriented**: supportano la nozione di oggetto, classe, ereditarietà (Smalltalk, C++, Java, …)

> [!info] Domanda di esame: Quali sono le caratteristiche di un linguaggio ad oggetti?
> Quelli che supportano nozioni di oggetto, classe e ereditarietà

