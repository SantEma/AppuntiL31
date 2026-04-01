**Il controllo di versione** (control version) è una parte della gestione della configurazione del software, che tiene traccia e controlla le modifiche del software che stiamo scrivendo.

Il controllo di versione è utile in diverse situazioni, in particolare:
- Quando più sviluppatori lavorano contemporaneamente allo stesso file (e progetto)
- La manutenzione di vecchie release di software 
## Comandi universali
Ci sono due comandi universali che sono alla base di ogni software di gestione di controllo:
- `diff`: confronta due file riga per riga e genera un resoconto di tutte le differenze
- `patch`: prende un file originale e un file `.patch` e li unisce per ricreare il file aggiornato.

Qualunque sistema quindi che vedremo eredita la logica da questi 2 singoli comandi
## Architetture di controllo
### Controllo locale
Nel controllo locale, lo sviluppatore ha un database locale (ossia un **repository**) che tiene traccia di tutte le modifiche, non lasciando che siano gestite come file rinominati ma record di un database ad-hoc.
> [!info] Schema controllo locale
> ![[Pasted image 20260320100440.png]]

L'unico problema di questa architettura è che non esiste nessun supporto alla collaborazione, quindi supporta il **multi-version** (più versioni) ma non il **multi-user** (più utenti )
### Controllo centralizzato di versione
Nel controllo centralizzato di versione, l'architettura si basa su un unico repository condiviso su un server centrale contenente tutti i file versionati
> [!info] Schema controllo centralizzato di versione
> ![[Pasted image 20260320100501.png]]

Gli sviluppatori effettuano due operazioni:
- Scaricano una copia locale (**checkout**) dal server al computer locale
- Registrano i file modificati sul repository condiviso nel server (**commit**)

Nel caso ci sia un conflitto in un file (modifiche apportate da due o più persone), chi arriva per ultimo lo risolve (operazione chiamata **merge**).

Questa architettura presenta problematiche nella gestione, in particolare creare un ramo parallelo di sviluppo (chiamato **branch**) spesso significava che il server doveva letteralmente copiare e duplicare l'intera cartella del progetto, per riunirlo con quello principale (**merge**) spesso generava conflitti difficili da aggiustare.
### Controllo distribuito di versione
A differenza del modello centralizzato, in questo caso esistono più repository, ognuno dei quali possiede la storia completa di tutte le versioni del software
> [!info] Schema controllo distribuito di versione
> ![[Pasted image 20260320123512.png]]

Gli sviluppatori adottano quindi questo workflow (principalmente questo si riferisce a Git, ma è applicabile anche ad altri):
1.  Iniziano copiando un intero repository tramite un'operazione di `clone`, oppure ne creano uno nuovo, lavorando poi offline sui file della loro copia locale
2. Successivamente, registrano le modifiche sul proprio repository locale 
3. Infine condividono il lavoro inviandolo su un repository remoto tramite il comando di   o chiedendo al proprietario di tirare giù le loro modifiche 

L'unico vero svantaggio di questo sistema è la curva di apprendimento inizialmente ripida, dovuta ai molteplici flussi di lavoro possibili
## Git
### Modifiche nel computer locale
Ogni file, in base al comando, passa in determinate zone come descritte da questo schema:

> [!info] Schema fasi di modifiche nel computer locale
> ![[Pasted image 20260320125038.png]]
> ![[Pasted image 20260326190717.png]]
### Vari comandi di Git

| **Categoria**                  | **Comando**                                           | **Descrizione**                                                                    |
| ------------------------------ | ----------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **CONFIGURARE GLI STRUMENTI**  | `$ git config --global user.name "[name]"`            | Imposta il nome da associare alle transazioni di commit                            |
|                                | `$ git config --global user.email "[email address]"`  | Imposta l'email da associare alle transazioni di commit                            |
|                                | `$ git config --global color.ui auto`                 | Attiva la colorazione automatica dell'output della riga di comando                 |
| **CREARE REPOSITORY**          | `$ git init [project-name]`                           | Crea un nuovo repository locale con il nome specificato                            |
|                                | `$ git clone [url]`                                   | Scarica un progetto e la sua cronologia completa delle versioni                    |
| **APPORTARE MODIFICHE**        | `$ git status`                                        | Elenca tutti i file nuovi o modificati da sottoporre a commit                      |
|                                | `$ git diff`                                          | Mostra le differenze tra file non ancora sottoposti a staging                      |
|                                | `$ git add [file]`                                    | Crea un'istantanea del file in preparazione per la creazione della versione        |
|                                | `$ git diff --staged`                                 | Mostra le differenze tra staging e l'ultima versione del file                      |
|                                | `$ git reset [file]`                                  | Rimuove il file dallo staging, ma ne conserva i contenuti                          |
|                                | `$ git commit -m "[descriptive message]"`             | Registra in modo permanente le istantanee dei file nella cronologia delle versioni |
| **RAGGRUPPARE MODIFICHE**      | `$ git branch`                                        | Elenca tutti i rami locali nel repository corrente                                 |
|                                | `$ git branch [branch-name]`                          | Crea un nuovo ramo                                                                 |
|                                | `$ git checkout [branch-name]`                        | Passa al ramo specificato e aggiorna la directory di lavoro                        |
|                                | `$ git merge [branch]`                                | Unisce la cronologia del ramo specificato nel ramo corrente                        |
|                                | `$ git branch -d [branch-name]`                       | Elimina il ramo specificato                                                        |
| **RIFATTORE NOMI DEI FILE**    | `$ git rm [file]`                                     | Elimina il file dalla directory di lavoro e ne prepara l'eliminazione              |
|                                | `$ git rm --cached [file]`                            | Rimuove il file dal controllo di versione ma conserva il file locale               |
|                                | `$ git mv [file-original] [file-renamed]`             | Cambia il nome del file e lo prepara per il commit                                 |
| **SOPPRIMERE IL TRACCIAMENTO** | `* .log` `build/` `temp-*`                            | File denominato `.gitignore` per sopprimere il controllo di versione accidentale   |
|                                | `$ git ls-files --other --ignored --exclude-standard` | Elenca tutti i file ignorati in questo progetto                                    |
| **SALVARE FRAMMENTI**          | `$ git stash`                                         | Memorizza temporaneamente tutti i file tracciati modificati                        |
|                                | `$ git stash pop`                                     | Ripristina i file più recenti salvati nello stash                                  |
|                                | `$ git stash list`                                    | Elenca tutti i set di modifiche memorizzati nello stash                            |
|                                | `$ git stash drop`                                    | Elimina il set di modifiche più recenti nello stash                                |
| **REVISIONE DELLA CRONOLOGIA** | `$ git log`                                           | Elenca la cronologia delle versioni per il ramo attuale                            |
|                                | `$ git log --follow [file]`                           | Elenca la cronologia delle versioni di un file, compresi i cambi di nome           |
|                                | `$ git diff [first-branch] ... [second-branch]`       | Mostra le differenze di contenuto tra due rami                                     |
|                                | `$ git show [commit]`                                 | Mostra i metadati e le modifiche al contenuto del commit specificato               |
| **REDO COMMIT**                | `$ git reset [commit]`                                | Annulla tutti i commit dopo `[commit]`, mantenendo le modifiche locali             |
|                                | `$ git reset --hard [commit]`                         | Elimina tutta la cronologia e torna indietro al commit specificato                 |
| **SINCRONIZZARE LE MODIFICHE** | `$ git fetch [bookmark]`                              | Scarica tutta la cronologia dal segnalibro del repository                          |
|                                | `$ git merge [bookmark]/[branch]`                     | Unisce il ramo del segnalibro nel ramo locale corrente                             |
|                                | `$ git push [alias] [branch]`                         | Carica tutti i commit del ramo locale su GitHub                                    |
|                                | `$ git pull`                                          | Scarica la cronologia dei segnalibri e incorpora le modifiche                      |
### Commenti
I commenti in Git sono molto significativi, poiché aiutano a far capire al team (e a se stessi a distanza di tempo) ciò che si è fatto in una commit.
Ci sono alcune regole generali di **etiquette** da seguire, ad esempio:
- Il titolo deve essere separato dalla descrizione con una linea vuota o se il commento è vuoto o piccolo basta inserire solo il titolo.
- Il titolo non deve essere prolisso (massimo 50 caratteri), la descrizione dettagliata è il posto giusto per spiegare meglio i dettagli di un titolo molto lungo
- Il titolo inizia con una lettera maiuscola
- Il titolo è privo di punteggiatura
- Stile imperativo ed in lingua inglese
- La descrizione ha 72 caratteri massimi, oltre quelli è consigliato creare un'altra linea di descrizione
- Bisogna spiegare nella descrizione il **cosa si è fatto** non il **come**.
### Branching
Il **branch** ci permette di estrarre dal ramo **madre** una parte in cui ci si può lavorare separatamente, decidendo al termine della linea di sviluppo se inglobarlo nel ramo madre, lasciarlo separato o eliminarlo e creare un ulteriore branch da quest'ultimo.
Questa procedura è il modo migliore per lavorare contemporaneamente a più versioni di un **repository**.

Per default il ramo madre si chiama **master** (chiamato anche **main**) e i branch che vengono riuniti al master verranno rimossi, se quest'ultimi non sono rimossi vuol dire che quel branch serve per tenere traccia comunque di un punto del software che sia esterno o che abbia comunque utilità anche in **maniera esterna al progetto**.

L'operazione di **unione** del branch lavorato e finito al ramo master in corso (da cui è stato anche separato il branch stesso), si chiama **merge**.

Generalmente il branch viene usato in **locale**, altrimenti si ricadrebbe nello stesso bisogno che si è avuto per creare la separazione tra branch e master.

> [!example] Rappresentazione grafica del branching
> ![[Pasted image 20260326190743.png]]
#### Comandi per il branching
- `git branch`: mostrare i branch esistenti e visualizzare quello corrente
- `git branch branch-name`: crea un nuovo branch a partire da quello corrente
- `git checkout branch-name`: cambia il branch corrente e aggiorna la working directory
- `git merge branch-name`: fonde il branch specifico con quello madre
- `git merge -d branch-name`: cancella il branch selezionato
