
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

> [!example] Esempio di while
> ```python
> while <condizione>:
>     <istruzioni fino a quando condizione == True>
> else:
>     <istruzioni quando condizione == False>
> ```
### Liste e Manipolazione dei Dati
Le liste rappresentano una sequenza ordinata di oggetti di qualsiasi tipo, racchiusa tra parentesi quadre e separata da virgole, con la peculiarità di poter contenere al suo interno anche altre liste.

> [!example] Esempio di lista
> ```python
> l = [4.02, "bruno", x, True]
> ```
> L'accesso agli elementi avviene tramite un sistema di indicizzazione che parte da 0 per il conteggio da sinistra verso destra, o da -1 per esplorare la lista a ritroso partendo dall'ultimo elemento. 
> ```python
> print(l[0])   # 4.02  (primo elemento)
> print(l[-1])  # True  (ultimo elemento)
> ```

Python fornisce un ricco arsenale di metodi per manipolare le liste: 
- È possibile aggiungere elementi con `append()` o `extend()`, 
- È possibile inserire in posizioni specifiche elementi con `insert()`, rimuoverli con `remove()` o estrarli tramite `pop()`,
- Ordinare elementi in modo crescente o decrescente con `sort()` e `reverse()` e contarne le occorrenze con `count()`. 

> [!example] 
> ```python
> x = [5]
> l = [4.02, "claudio", x, True]
> l.append("giulio")   # aggiunge in fondo
> l.extend(x)          # estende con gli elementi di x
> l.insert(2, False)   # inserisce False all'indice 2
> l.remove("claudio")  # rimuove la prima occorrenza
> e = l.pop(3)         # estrae e rimuove l'elemento all'indice 3
> print("lista: {}, elemento: {}".format(l, e))
> # Output: lista: [4.02, False, [5], "giulio", 5], elemento: True
> 
> l = [7, 22.1, 22.1, 7, 7, 11.6]
> l.sort()              # ordinamento crescente
> l.reverse()           # ribalta la lista
> l.sort(reverse=True)  # equivalente a sort() + reverse()
> print(l.index(22.1))  # 1 - indice della prima occorrenza
> print(l.count(7))     # 3 - numero di occorrenze
> ```

Essendo oggetti mutabili, la modifica di una lista altera il contenuto del contenitore originale in memoria; per questo motivo, se si desidera creare una copia indipendente, è necessario utilizzare il metodo `.copy()` oppure ricorrere alla notazione`[start:end:step]`, che consente di estrarre porzioni specifiche di una lista definendo l'indice di partenza incluso, quello di fine escluso e il passo di avanzamento, offrendo persino la possibilità di invertire l'intera lista semplicemente impostando un passo negativo.

> [!example] Esempio di notazione start:end:step
> ```python
> l = [2, 3, 10, 50]
c = l[1:3]          # [3, 10]
print(l[:2])        # [2, 3]
print(l[1:])        # [3, 10, 50]
print(l[:])         # [2, 3, 10, 50]
print(l[::-1])      # [50, 10, 3, 2]  <- lista invertita!
> ```
### Tuple, Sequenze e Range
Le liste appartengono alla più ampia famiglia delle sequenze, un raggruppamento concettuale che include anche le stringhe di testo e le tuple. 
```python
s = "Hello"
print(s[2])   # 'l'
print(s[3:])  # 'lo'
```
A differenza delle liste, le tuple si definiscono tramite parentesi tonde e sono rigorosamente immutabili, prestandosi particolarmente alla conservazione di dati disomogenei che non devono subire alterazioni nel tempo.

> [!example] Esempio di una tupla
> ```python
> t=("a",2,"c")
> ```
> Sarebbe raccomandabile mettere in una tupla i dati disomogenei e in una lista quelli omogenei



## Testing

