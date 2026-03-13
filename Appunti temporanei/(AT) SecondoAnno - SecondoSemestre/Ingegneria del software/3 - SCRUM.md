Scrum è un framework agile per la gestione del ciclo di sviluppo del software, iterativo ed incrementale, concepito per gestire progetti e prodotti software o applicazioni di sviluppo
![[Pasted image 20260313095019.png]]
## Sprint
I progetti Scrum fanno progressi in una serie di iterazioni dette **Sprint**.
In ogni iterazione si svolgono le varie attività tecniche, quindi i requisiti sono analizzati, progettati, realizzati e testati durante lo sprint.
Gli Sprint non sono interrompibili e non modificabili, le modifiche dei requisiti sono accettate soltanto durante la fine di questo ciclo attuale e l'inizio del ciclo successivo.
Ogni Sprint ha una durante costante definita inizialmente (**timeboxing**), di solito questi durano dalle 2 alle 4 settimane
## Framework
Il framework di Scrum è definito in 3 parti principali:
- Ruoli(Product owner, ScrumMaster, Team)
- Eventi (Sprint planning, Sprint review, Sprint retrospective, Daily scrum meeting)
- Artifact(Product backlog, Sprint backlog, Burndown charts)
### Artifact
#### Product Backlog
Il product backlog è una lista di requisiti funzionali richieste sul progetto. A differenza di un processo a cascata, dove viene fatta tutto a monte, questo processo prevede il cambiamento dinamico di questi requisiti.

I requisiti vengono stabiliti dal Product Owner (analista di solito impiegato nel campo, esperto del dominio), che stabilisce delle priorità per ogni Sprint.
Per ogni elemento presente nel product backlog si danno delle stime, con diverse unità di misura (di solito giorni-persona)

Le funzionalità da realizzare vengono chiamate **User Story** (punto di vista di un utente rispetto alla funzionalità)

> [!example] Esempio di User Story
![[Pasted image 20260313100614.png]]

Altre task presenti sono le **Issues** (ossia le problematiche, molto spesso si riferiscono ai bug presenti sui software)

> [!example] Esempio di product backlog
> ![[Pasted image 20260313100902.png]]

L'unità di misura principale sono gli **story point**, il cui valore unitario è un valore non standardizzato, ma per convenzione equivale ad una User Story semplice (di solito quella che uno sviluppatore potrebbe fare in mezza giornata lavorativa).
#### Sprint goal
Lo sprint goal è una breve indicazione dell’obiettivo principale dello Sprint, fornendo una guida al team sul perché si sta sviluppando un nuovo incremento del prodotto.
#### Sprint backlog
Lo Sprint Backlog è l'insieme degli elementi del Product Backlog selezionati per lo Sprint più un piano per fornire l'Incremento del prodotto e realizzare lo Sprint Goal
Questi, diversamente dall'essere gestiti dal Product Owner, sono gestite da Team di sviluppo autogestiti, ovvero i componenti del team scelgono su quale elemento lavorare, qualsiasi componente può aggiungere, cancellare o modificare gli elementi.
La stima del lavoro rimanente è aggiornata nel daily meeting

> [!info] Scrum Board
> La Scrum board è una rappresentazione grafica di tutto questo processo. 
> ![[Pasted image 20260313102257.png]]
### Eventi
Gli eventi nello Scrum sono degli incontri, suddivisi in:
- Sprint planning
- Sprint review
- Sprint retrospective
- Daily scrum meeting
I primi 2 si svolgono durante ogni sprint
#### Sprint planning
Si divide in due parti:
1. La selezione dello Sprint, guidata dal Product Owner, dove avvengono:
	- Valutazione delle priorità nel Product Backlog
	- Scelta dello Sprint Goal
	- Selezione degli elementi da completare nello Sprint
2. Creazione dello Sprint Backlog (autogestita dal team), ossia tutto il processo di raffinamento di design preliminare e identificazione dei task

![[Pasted image 20260313111425.png]]
#### Daily scrum meeting
Il Daily Scrum meeting è un meeting giornaliero per poter fare un recap generale, è breve (15 minuti massimo), ha come basi queste tre domande:
- Cosa hai fatto ieri?
- Cosa farai oggi?
- Ci sono problemi?
#### Sprint review
È una riunione aperta dove tutto il team partecipa e sono ben visti degli esterni (come degli utenti), viene mostrata una demo con delle nuove funzionalità.
Il suo obbiettivo principale è la raccolta di feedback dalla parte del software.
#### Sprint retrospective
Questo punto è dedicato al feedback sul processo sempre alla fine di uno Sprint, partecipa tutto il team e si discute cosa fare nel prossimo sprint, in particolare:
1. Cosa introdurre
2. Cosa evitare
3. Cosa continuare

In alternativa si discute sullo sprint concluso, sopratutto su cosa ha fatto sentire:
- Contento
- Deluso
- Disperato

### Ruoli
#### Team di sviluppo
Un team di sviluppo è un gruppo di persone di dimensione dalle 3 alle 8 persone cross-functional (ossia un team formato da persone con tutte le competenze richieste dal progetto).
#### Product Owner
È responsabile del valore del prodotto, ossia ha la responsabilità esclusiva di gestione del Product Backlog:
- Definisce le caratteristiche funzionali e non funzionali (feature) del prodotto (in collaborazione con il team)
- Assegna le priorità alle feature in base al valore di mercato (per ogni iterazione)

Lui ha anche il potere di accettare o rifiutare i risultati del lavoro del Team di Sviluppo, che devono rispettare diversi criteri suddivisi in: 
- Generali: in base a una definizione di “Done” (lavoro completo) compresa da tutto il Team di Sviluppo
- Specifica: Criteri di accettazione (specifiche dei casi di test)
#### Scrum master
Lo scrum master è il responsabile del rispetto del metodo SCRUM, in modo da guidare tutti ad usare lo stesso metodo.
Può essere un esterno o un interno nell'azienda e si interfaccia con i vari management, isolando il team dalle varie distrazioni.

Quando è affiancato dal product owner e al team di sviluppo svolge diversi ruoli:
- Aiuta a creare gli elementi del Product Backlog
- Aiuta ad ordinare gli elementi del Product Backlog per massimizzare il valore


