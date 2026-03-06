## I processi (di sviluppo del) software
> [!info] Definizione di processo software
> Un **processo software** descrive quali sono le attività che concorrono a sviluppare un prodotto software e come le attività sono collegate tra loro

Si assume che, se il processo stesso sia di una certa qualità, allora anche il software sia qualitativamente valido

## Stili di processo
### A cascata (waterfall)
Questo stile di processo suddivide il progetto in base alle attività tecniche (con delle che fasi coincidono con le attività), e si passa ad una fase successiva solo se si completa l’attività e si supera il punto di controllo.
![[Pasted image 20260306095227.png]]
Questo stile ha diversi problemi:
- Rischio elevato: difficile stabilire che tutto procede veramente bene quando il progetto diventa grande, poichè il software finale si vedrebbe soltanto nella fase di testing
- Diventa difficile da applicare se i requisiti sono poco noti o volatili
- Time to market ritardato
### Iterativo
Anche conosciuto come incrementale, a spirale, evolutivo, si suddivide il progetto in base a sottoinsiemi di funzionalità (iterazioni):
- L’inizio delle iterazioni è preceduto da una fase esplorativa
- Ogni iterazione produce codice (**build**) testato e integrato nel sistema complessivo
- Le iterazioni messe in produzione sono dette **release** con la tecnica di **time boxing**, ossia rilasciate a intervalli di tempo regolari
![[Pasted image 20260306100621.png]]
Questo processo riduce complessivamente il rischio di trovarsi un software che non rispetti le specifiche, poichè si da una versione con il minimo utilizzabile e poi di espanderlo con il tempo
### Altri metodi
#### Sviluppo ad hoc (build and fix)
[da finire] Quello dei coglioni che facciamo noi
#### Sviluppo pianificato (plan-driven)
[da finire] va bene in certi ambiti dove i requisiti sono ben definiti
#### Sviluppo agile
[da finire]  Quello per chi lavora in ufficio di un PA praticamente

