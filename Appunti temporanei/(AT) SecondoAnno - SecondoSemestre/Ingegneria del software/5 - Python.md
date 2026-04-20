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

> [!example] Esempio di stringa come sequenza
> ```python
> s = "Hello"
> print(s[2])   # 'l'
> print(s[3:])  # 'lo'
> ```

A differenza delle liste, le tuple si definiscono tramite parentesi tonde e sono rigorosamente immutabili, prestandosi particolarmente alla conservazione di dati disomogenei che non devono subire alterazioni nel tempo.

> [!example] Esempio di una tupla
> ```python
> t = ("a", 2, "c")
> t[1] = "b"  # TypeError! Le tuple sono immutabili
> ```
> Sarebbe raccomandabile mettere in una tupla i dati disomogenei e in una lista quelli omogenei

Tutte le sequenze condividono funzionalità comuni: 
- Gli operatori `in` e `not in` permettono di verificare l'esistenza di un elemento,
- L'operatore di addizione concatena più sequenze, la moltiplicazione per un numero intero le replica.
- Funzioni integrate come `len`, `min`, `max` e `sum` ne analizzano il contenuto.

> [!example] Esempio di funzioni di sequenze
> ```python
> l = [None] * 100  # lista di 100 elementi None
> 
> len(l)   # lunghezza
> min(l)   # valore minimo
> max(l)   # valore massimo
> sum(l)   # somma degli elementi
> ```

Una caratteristica potente delle sequenze è il "sequence unpacking", che permette di assegnare i singoli valori interni a variabili distinte in una sola riga di codice.

> [!example] Esempio di sequence unpackaging
> ```python
> l = (4, 6, 8, 10)
> a, b, _, c = l
> # a=4, b=6, _=8 (ignorato), c=10
> ```

Per generare rapidamente sequenze numeriche entra in gioco il tipo di dato `range`, utilissimo per creare contatori specificando un punto di inizio, un termine escluso e un passo, dove il parametro di partenza è considerato zero se omesso.

> [!example] Esempio di range
> ```python
> range(start, end, step)
> 
> # Esempio: numeri da 1 a 100 con passo 3
> l = list(range(1, 100, 3))
> ```
### Set e Dizionari
Python gestisce i dati non ordinati attraverso i set e i dizionari. Il set, delimitato da parentesi graffe, è una collezione non ordinata e non indicizzabile che garantisce l'assenza di duplicati, rivelandosi lo strumento ideale per gestire enormi moli di dati su cui effettuare rapide ricerche di appartenenza.

> [!example] Esempio di set
> ```python
> s = {4, 2, 4, 1}
> print(s)   # {1, 2, 4}  <- il duplicato è rimosso
> # s[1]     # TypeError! I set non sono indicizzabili
> ```

Il dizionario, anch'esso definito da parentesi graffe, struttura invece le informazioni come collezioni mutabili di coppie chiave-valore, un po' come un vocabolario tradizionale.

> [!example]
> ```python
> d = {'Uniba': 'Università nel Sud Italia', 'Gatto': 'Mammifero di tipo felino'}
> # Oppure, se le chiavi sono identificatori validi:
> d = dict(Uniba='...', Gatto='...')
> ```

Per accedere al valore di un dizionario è sufficiente richiamare la sua chiave, a patto che questa sia un identificatore valido, utilizzando le parentesi quadre oppure il metodo `.get()`.

```python
d = {'Uniba': 'Università nel Sud Italia', 7: 'Numero intero'}
print(d['Uniba'])       # accesso con parentesi quadre
print(d.get(7))         # accesso con .get()
d['Bari'] = 'Bellissima citta'  # aggiunta di una nuova coppia
```

Esattamente come accade per le liste, anche i dizionari sono oggetti mutabili, il che significa che una semplice assegnazione ne copia solo il riferimento in memoria, rendendo necessario l'uso del metodo `.copy()` per duplicare l'oggetto in modo sicuro.

```python
d = {'Uniba': 'Università nel Sud Italia', 7: 'Numero intero'}
c = d
c['Uniba'] = 5
print(d)  # anche d è cambiato!

# Per una vera copia:
c = d.copy()
## Testing

