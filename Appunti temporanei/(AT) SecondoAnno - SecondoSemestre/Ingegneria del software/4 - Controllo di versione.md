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
Nel controllo locale, lo sviluppatore ha un database locale (ossia un **repository**) che tiene traccia di tutte le modifiche, non lasciando che siano gestite come file rinominati ma record di un database ad-hoc

> [!info] Schema controllo locale
> ![[Pasted image 20260320100440.png]]

L'unico problema di questo schema è che non esiste nessun supporto alla collaborazione, quindi supporta il **multi-version** (più versioni) ma non il **multi-user** (più utenti )
### Controllo centralizzato di versione
Nel controllo centralizzato di versione, il repository viene condiviso su un server che contiene tutti i file versionati, non l'intero repository.

> [!info] Schema controllo centralizzato di versione
> ![[Pasted image 20260320100501.png]]

Gli sviluppatori effettuano due operazioni:
- Scaricano una copia locale (**checkout**) dal server al computer locale
- Registrano i file modificati sul repository condiviso nel server (**commit**)

Nel caso ci sia un conflitto in un file (modifiche apportate ), chi arriva per ultimo lo risolve (**merge**).
Nei sistemi centralizzati, creare un ramo parallelo di sviluppo (chiamato **branch**) spesso significava che il server doveva letteralmente copiare e duplicare l'intera cartella del progetto, riunirlo con quello principale (**merge**) generava spesso conflitti difficili da aggiustare.
### Controllo distribuito di versione
Questa architettura permette di scaricare tutto il repository e di lavorarci sopra, avendo visibilità completa, rendendolo molto più comodo rispetto all'architettura precedente