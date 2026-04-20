
## Codice
### Variabile
Una variabile in Python rappresenta una specifica locazione di memoria riservata per conservare dati di vario tipo, come interi, decimali, stringhe o oggetti complessi.
Ad essa viene associato un identificatore, ovvero un nome che segue regole precise: 
- Deve iniziare con una lettera o con un underscore, 
- Può contenere caratteri alfanumerici 
- Non deve coincidere con nessuna parola riservata del linguaggio. 
Per convenzione, i nomi delle variabili iniziano sempre con una lettera minuscola. Rispetto ad altri linguaggi, in Python non è necessario dover specificare il tipo.
### Operatori Matematici, Logici e Tipi di Dato
Python permette di visualizzare i dati a schermo tramite la funzione integrata `print()` e di eseguire calcoli su valori interi (int) e decimali (float) utilizzando i classici operatori matematici per addizione, sottrazione, moltiplicazione, divisione, modulo e potenza, supportando anche notazioni compatte come `+=` per l'incremento.

Oltre ai numeri, assumono un'importanza cruciale le variabili booleane, che possono assumere esclusivamente i valori `True` o `False`. Su di esse è possibile applicare le regole delle tavole di verità attraverso gli operatori logici `and`, `or` e `not`. I valori booleani sono spesso il risultato diretto del confronto tra variabili, effettuabile mediante operatori relazionali come l'uguaglianza (`==`), la disuguaglianza (`!=`), il minore (`<`), il maggiore (`>`) e le loro relative varianti inclusive (`<=`, `>=`).

### Strutture di Controllo e Cicli Iterativi
Per implementare la logica decisionale all'interno di un algoritmo, Python utilizza i blocchi condizionali definiti dalle parole chiave `if`, `elif` ed `else`, i quali eseguono porzioni di codice diverse in base alla veridicità di uno o più predicati. 

> [!example] Esempio di indentazione e codice sulle strutture di controllo
> ```python
> if <cond1>:
>     <istruzioni per cond1 == True>
> elif <cond2>:
>     <istruzioni per cond1 == False e cond2 == True>
> else:
>     <istruzioni per cond1 == False e cond2 == False>
> ```

L'intero linguaggio si basa sull'indentazione (solitamente 4 spazi) per raggruppare visivamente e strutturalmente le istruzioni: un'indentazione errata non è solo un problema stilistico, ma genera comportamenti anomali o errori di esecuzione.

Quando si presenta la necessità di ripetere un'azione fintanto che una specifica condizione iniziale risulta vera, si ricorre al ciclo iterativo `while`, che valuta la condizione ad ogni passaggio e interrompe l'esecuzione nel momento in cui essa diventa falsa.

> [!NOTE] Esempio di while
> ```python
> while <condizione>:
>     <istruzioni fino a quando condizione == True>
> else:
>     <istruzioni quando condizione == False>
> ```


## Testing

