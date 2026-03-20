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

Gli sviluppatori adottano quindi questo workflow (principalmente questo si riferisce a git, ma è applicabile anche ad altri):
1.  Iniziano copiando un intero repository tramite un'operazione di `clone`, oppure ne creano uno nuovo, lavorando poi offline sui file della loro copia locale
2. Successivamente, registrano le modifiche sul proprio repository locale 
3. Infine condividono il lavoro inviandolo su un repository remoto tramite il comando di   o chiedendo al proprietario di tirare giù le loro modifiche 

L'unico vero svantaggio di questo sistema è la curva di apprendimento inizialmente ripida, dovuta ai molteplici flussi di lavoro possibili
## Git
### Modifiche nel computer locale

> [!info] Schema fasi di modifiche nel computer locale
> ![[Pasted image 20260320125038.png]]

