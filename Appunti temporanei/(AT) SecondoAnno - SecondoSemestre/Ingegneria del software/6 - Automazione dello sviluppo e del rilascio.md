Nel manifesto agile, uno dei vari principi è proprio quello del:

> [!info] Massima priorità
> La nostra massima priorità è soddisfare il cliente **rilasciando software**, fin da subito e **in maniera continiua**
## Integrazione continua (CI)
Per integrazione continua si intendono diversi passaggi, tra cui:
- Ogni componente del team integra il proprio lavoro sul repository **almeno una volta al giorno**
- Ogni integrazione è accompagnata da un **build automatico** che include analisi statica del codice e test automatizzati
- Un build rotto (ossia che fallisce) deve essere **riparato immediatamente** da chi lo ha innescato
## Rilascio continuo (CD)
Con il rilascio continuo è possibile **rilasciare software funzionante in qualsiasi momento**. Il team da priorità ad assicurarsi che il software sia rilasciabile piuttosto che lavorare su nuove funzionalità

Ma quali sono le condizioni per il rilascio continuo?
- Una stretta collaborazione tra gli sviluppatori e i sistemisti
  Da qui nasce la figura del DevOps, un ibrido tra i due citati
- La presenza di una deployment pipeline, ossia di un automazione di tutti i passaggi sul processo del rilascio

Principalmente useremo Docker e Github Actions come 