**Il controllo di versione** (control version) è una parte della gestione della configurazione del software, che tiene traccia e controlla le modifiche del software che stiamo scrivendo.

Il controllo di versione è utile in diverse situazioni, in particolare:
- Quando più sviluppatori lavorano contemporaneamente allo stesso file (e progetto)
- La manutenzione di vecchie release di software 
## Comandi universali
Ci sono due comandi universali che si usano nei software di versione di controllo:
- `diff`: confronta due file riga per riga e genera un resoconto di tutte le differenze
- `patch`: prende un file originale e un file `.patch` e li unisce per ricreare il file aggiornato.

Questi due comandi sono alla base di tutti i software di controllo di versione
## Architetture di controllo
### Controllo locale
Nel controllo locale, lo sviluppatore ha un database locale (ossia un **repository**) che tiene traccia di tutte le modifiche, non lasciando che siano gestite come file rinominati ma record di un database ad-hoc.
> [!info] Schema controllo locale
> ![[Pasted image 20260320100440.png]]

L'unico problema di questo schema è che non esiste nessun supporto alla collaborazione, quindi supporta il **multi-version** (più versioni) ma non il **multi-user** (più utenti )
### Controllo centralizzato di versione
Nel controllo centralizzato di versione, il repository viene condiviso su un server che contiene tutti i file versionati

> [!info] Schema controllo centralizzato di versione
> ![[Pasted image 20260320100501.png]]

Gli sviluppatori effettuano due operazioni:
- Scaricano una copia locale (**checkout**) dal server al computer locale
- Registrano i file modificati sul repository condiviso nel server (**commit**)

Nel caso ci sia un conflitto in un file (modifiche apportate da due o più persone), chi arriva per ultimo lo risolve (operazione chiamata **merge**).
Nei sistemi centralizzati, creare un ramo parallelo di sviluppo (chiamato **branch**) spesso significava che il server doveva letteralmente copiare e duplicare l'intera cartella del progetto, riunirlo con quello principale (**merge**) generava spesso conflitti difficili da aggiustare.
### Controllo distribuito di versione
A differenza del modello centralizzato, in questo caso esistono più repository, ognuno dei quali possiede la storia completa di tutte le versioni del software

> [!info] Schema controllo distribuito di versione
> ![[Pasted image 20260320123512.png]]

Gli sviluppatori adottano quindi questo workflow (principalmente questo si riferisce a git, ma è applicabile anche ad altri):
1.  Iniziano copiando un intero repository tramite un'operazione di `clone`, oppure ne creano uno nuovo, lavorando poi offline sui file della loro copia locale
2. Successivamente, registrano le modifiche sul proprio repository locale tramite il comando `commit`
3. Infine condividono il lavoro inviandolo su un repository remoto tramite il comando di  `push` o chiedendo al proprietario di tirare giù le loro modifiche tramite una **pull request**