## I processi (di sviluppo del) software
> [!info] Definizione di processo software
> Un **processo software** descrive quali sono le attività che concorrono a sviluppare un prodotto software e come le attività sono collegate tra loro

Si assume che, se il processo stesso sia di una certa qualità, allora anche il software sia qualitativamente valido.

Le attività tipiche nello sviluppo ed evoluzione del software si dividono in **attività tecniche** e **attività organizzative**.

Le **attività tecniche** sono:
- Analisi dei requisiti
- Progettazione
- Realizzazione
- Collaudo
- Messa in esercizio
- Conduzione operativa
- Manutenzione

Le **attività organizzative** sono:
- Gestione del progetto
- Gestione della configurazione
- Assicurazione della qualità

Per eseguire il processo di creazione dello sviluppo di un software, si eseguono degli stili specifici.
## Stili di processo
### A cascata (waterfall)
Questo stile di processo suddivide il progetto in base alle attività tecniche (con delle che fasi coincidono con le attività), e si passa ad una fase successiva solo se si completa l’attività e si supera il punto di controllo.
Il waterfall è stato uno dei primi stili ad essere utilizzato per l'ingegneria del software, poiché si basa sulle ingegnerie classiche, e fino agli anni '90 è stato lo stile più utilizzato.
![[Pasted image 20260306095227.png]]
Questo stile ha diversi problemi:
- Rischio elevato: difficile stabilire che tutto procede veramente bene quando il progetto diventa grande, poichè il software finale si vedrebbe soltanto nella fase di testing
- Diventa difficile da applicare se i requisiti sono poco noti o volatili
- Time to market ritardato, ovvero anche se un progetto funziona ed è perfetto, bisogna essere comunque rapidi nella realizzazione, poiché è possibile che l'idea progettata non sia solamente stata pensata da una singola persona nel mondo ma bisogna sempre tener conto della concorrenza.
### Iterativo
Anche conosciuto come incrementale, a spirale, evolutivo, si suddivide il progetto in base a sottoinsiemi di funzionalità (iterazioni):
- L’inizio delle iterazioni è preceduto da una fase esplorativa. Il **project manager** decide che operazioni eseguire nell'iterazione 1 e cosa nell'iterazione 2.
- Ogni iterazione produce codice (**build**) testato e integrato nel sistema complessivo
- Le iterazioni messe in produzione sono dette **release** con la tecnica di **time boxing**, ossia rilasciate a intervalli di tempo regolari. Questo ci aiuta ad avere un ritmo costante, senza dover aspettare tempo indeterminato per rilasciare l'intero prodotto.
![[Pasted image 20260306100621.png]]
Quindi ripetiamo tutte le attività tecniche fino ad una certo punto in cui non andiamo ad eseguire nuovamente di nuovo tutte le attività tecniche di un altro tipo, così per ogni iterazione.
Questo processo riduce complessivamente il rischio di trovarsi un software che non rispetti le specifiche, poichè si da una versione con il minimo utilizzabile e poi di espanderlo con il tempo
### Altri metodi
Tra lo stile a waterfall e lo stile a spirale, esistono delle strade di mezzo:
- **Sviluppo ad hoc**: Basato sul build and fix, ed è il peggior metodo di utilizzo per lo sviluppo di un progetto software a livello ingegneristico, poiché è privo di documentazione e l'approccio utilizzato non è ripetibile e si può trasferire ad altri dipendenti solamente con un apprendistato sulla conoscenza del codice stesso. Utilizzato a livello amichevole e non permette crescita.
- **Sviluppo pianificato**: Lo sviluppo pianificato va bene nel caso i requisiti sono stati definiti a monte e non sono modificabili nel tempo. Imposto dal progettista o dai datori. Lo stile di processo utilizzato è quello a cascata. 
- **Sviluppo agile**: Questo sviluppo è ottimo in caso il progetto ha grandi margini di crescita ed è soggetto a grandi cambiamenti nel corso d'opera. La documentazione è basata sull'interlocuzione tra persone dirette, senza l'utilizzo di una documentazione scritta. Un esempio dello sviluppo agile è **Scrum**.

**Nessuno di questi stili è migliore dell'altro**, dipende tutto dal progetto che bisogna costruire e dal team presente all'interno.
## I 12 principi del Manifesto Agile
1. La priorità di coloro che lavorano tramite contratto di commissione deve soddisfare il clienti in qualsiasi richiesta, rilasciando software di valore da subito e in modo continuo. Bisogna aspettarsi che i clienti chiederanno altro fuori contratto stipulato, bisogna avere fiducia reciproca tra operatore e cliente.
2. Anche in stadi avanzati dello sviluppo del progetto, in caso di necessità, bisogna essere pronti ad apportare modifiche.
3. Consegnare il software sempre funzionante, con cadenza variabile tra un paio di settimane e un paio di mesi massimo (ed è già tanto, si preferiscono le due settimane).
4. Committenti e sviluppatori devono lavorare assieme per tutta la durata del progetto.
5. Fondiamo i progetti sulla base di individui (tra uomini e macchinari) ben motivati, il personale deve essere competente, coinvolto ed idoneo.
6. La conversazione faccia a faccia è il metodo migliore per comunicare con il team, anche se non è sempre possibile.
7. Il software funzionante è l'unico metodo di verifica per vedere se stanno avvenendo degli avanzamenti.
8. Gli sponsor, gli sviluppatori e gli utenti dovrebbero essere in grado di mantenere indefinitamente un ritmo costante.
9. La continua attenzione all'eccellenza tecnica e alla buona progettazione esaltano l'agilità.
10. La semplicità è essenziale
11. Le architetture, i requisiti e la progettazione migliori emergono da team che si auto-organizzano.
12. A intervalli regolari il team riflette su come diventare più efficace, dopodiché regola e adatta il proprio comportamento di conseguenza.

 Dei metodi agili possiamo dividere le risorse usate in **piccoli medi progetti** e **grandi progetti**.
 I **piccoli medi progetti** possono essere:
 - Scrum
 - XP
 - Kanban
 I **grandi progetti**, sono i progetti con più di 6 team o con 50 persone totali coinvolte, e le risorse possono essere:
 - Scrum of Scrum
 - SAFe
 - LeSS
 - DAD
 - Sa@S