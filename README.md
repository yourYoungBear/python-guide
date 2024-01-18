
![course-cover](https://github.com/yourYoungBear/python-guide/blob/main/python-social-preview.png?raw=true)

## Introduzione

Python è uno dei linguaggi di programmazione più utilizzati al mondo, grazie alla sua semplicità e versalità viene sfruttato per moltissimi scopi diversi come lo sviluppo di applicazioni desktop, web e networking ma da del suo meglio proprio nel calcolo scientifico e nel **machine learning**.  
  
Python è un **linguaggio interpretato**, questo vuol dire che, a differenza di un lingaggio compilato, il codice non viene direttamente compilato in un file eseguibile (ad esempio i file .exe di Windows), ma viene interpretato da un altro software, chiamato proprio _interprete_, che poi lo esegue. Questo vuol dire che lo stesso codice Python può essere eseguito su qualsiasi sistema operativo sulla quale sia disponibile l'interprete, come Windows, Unix/Linux, Macintosh e sistemi mobili come Android e iOS.  
  
In realtà, prima di essere eseguito tramite l'interprete, un programma Python viene pre-compilato in un formato chiamato _bytecode_, il ché lo rende più performante di diversi linguaggi interpretati, anche se non al livello di linguaggi compilati a basso livello come C/C++ (Python è realizzato proprio in linguaggio C).
## Input e Output

Le funzioni fondamentali di un qualsiasi linguaggio di programmazione sono quelle che ci permettono di prendere delle informazioni in ingresso e mostrarle in uscita.  
Con Python possiamo stampare dei dati su schermo utilizzando la funzione _print_.

```
print("Ciao mondo") 
```

In questo caso il dato che abbiamo stampato è una stringa, cioè del testo, che viene racchiusa tra doppi apici.  
Per acquisire dei dati possiamo invece utilizzare la funzione input.

```
name = input("Come ti chiami ? ")
print("Felice di conoscerti",name)
```

In questo caso abbiamo immagazzianto l'input inserito da tastiera all'interno di una **variabile** che poi abbiamo stampato su schermo
## Le variabili

Una variabile serve per immagazzinare dati, possiamo assegnare un dato a una variabile usando l'operatore di assegnazione (=).

```
num = 5
print(num)

word = "ciao"
print(word)
```

Il nome della variabile viene definito da noi, è buona norma utilizzare un nome che rappresenta il contenuto della variabile, in modo da facilitare la lettura del codice.

```
cat = input("Inserisci un nome per il tuo nuovo gatto: ")
print(cat+" è il tuo nuovo padrone")
```

## Tipi di dati

Python è un linguaggio **non tipizzato** questo vuol dire che il tipo di dato che una variabile può contenere non va dichiarato espressamente. Per conoscere il tipo di dato che una variabile contiene possiamo usare la funzione type.

```
var = "ciao"
type(var)
```

I tipi di dati principali che Python ci mette a disposizine sono i seguenti:

- **Interi**: numeri interi (es: 5, 10, 123)
- **Float**: numeri in virgola mobile (es: 4.34, 5.31, 0.17)
- **Stringhe**: del testo (es: "ciao", "abc", "Yo, come butta fratello ?")
- **Booleani**: possono avere solo due valori vero/falso (True/False)

 - Intero
`var = 5`

- Float
`var = 4.15`

- String
`var = "ciao ciao"`

- Boolean
`var = True`

## Casting 

```
- Creiamo una variabile che contiene un'intero
var = 5
- Convertiamo la variabile da intero a stringa
var = str(var)
print(var)
print(type(var))
```

### Formattazione
---

Un'altra soluzione consiste nell'utilizzare l'operatore di formattazione (%)

```
cat_lives = 7
print("I gatti hanno %d vite" % cat_lives)
```

Il carattere dopo l'operatore di formattazione indica il tipo di variabile, i principali sono:

- **%d**: numero intero
- **%f**: numero in virgola mobile
- **%s**: stringa

Per la lista completa, dai uno sguardo [qui](https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Fdocs.python.org%2F3%2Flibrary%2Fstdtypes.html%23old-string-formatting).  
Possiamo anche utilizzare più operatori di formattazione all'interno di una stringa.

```
cat_lives = 7

cat = input("Come si chiama il tuo gatto ? ")

my_cat_lives = input("Quante vite ha perso ? ")

my_cat_lives = int(my_cat_lives)
my_cat_lives = cat_lives-my_cat_lives

print("Il tuo gatto %s ha ancora %d vite" % (cat, my_cat_lives))
```

**NOTA BENE** la funzione input ritorna una stringa, quindi abbiamo dovuto usare il casting per convertirla in un'intero.

---

Un'altra soluzione ancora, quella consigliata per Python 3, consiste nell'utilizzare il metodo lo _format_

```
cat_lives = 7

cat = input("Come si chiama il tuo gatto ? ")
my_cat_lives = int(input("Quante vite ha perso ? "))
my_cat_lives = cat_lives-my_cat_lives

print("Il tuo gatto {name} ha ancora {lives} vite".format(name=cat, lives=my_cat_lives))
```

Se usiamo una versione di Python superiore alla 3.6 abbiamo anche un'altro modo per formattare le stringhe, chiamato **f-strings**

```
cat_lives = 7

cat = input("Come si chiama il tuo gatto ? ")
my_cat_lives = int(input("Quante vite ha perso ? "))
my_cat_lives = cat_lives-my_cat_lives

# inseriamo una f prima della stringa per indicare la formattazione
print(f"Il tuo gatto {cat} ha ancora {my_cat_lives} vite")
```

## Operazioni aritmetiche

Con Python possiamo eseguire le varie **operazioni matematiche** utilizzando l'operatore corretto

```
# somma
print(5+3)

# sottrazione
print(4-1)

# prodotto
print(3*2)

# divisione
print(4/2)

# resto
print(5%2)

# unire due stringhe
print("5"+"2")
```

Come vedi dall'ultimo print, l'utilizzo dell'operatore somma (+) su due stringhe ha l'effetto di unirle.  
Il testo inserito dopo il carattere # è un **commento**, il suo scopo è quello di permetterci di inserire annotazioni nel codice, che poi verranno scartate dall'interprete e quindi non utilizzate in alcun modo dal programma.  
  
E' possibile anche stampare più dati, anche di tipo differente, semplicemente separandoli con una virgola, se si tratta solo di stringhe possiamo anche utilizzare l'operatore somma (+).

```
print("5 + 3 = "+"8")

print("5 + 3 =",8)

print("5 + 3 =",5+3)
```

## Le Eccezioni

Cosa succede se proviamo a sommare una parola e un numero ?

```
cat_lives = 7

print("I gatti hanno "+cat_lives+" vite")
```

quando eseguiremo:

---------------------------------------------------------------------------

```
TypeError                                 Traceback (most recent call last)

<ipython-input-4-d06ce6cd1899> in <module>()
      1 cat_lives = 7
----> 2 print("I gatti hanno "+cat_lives+" vite")

TypeError: can only concatenate str (not "int") to str
```

Come vedi il tentativo di sommare una parola e un numero ha causato un'errore, che in Python vengono chiamate **eccezioni**.  
Ogni volta che si verifica un'eccezione Python ci mostra:

- la riga esatta in cui si è verificato (La freccia verde)
- il tipo di eccezone (TypeError)
- una breve descrizione (_can only concatenate str (not "int") to str_)

Un altro esempio di eccezione è quella che avviene se proviamo a convertire una parola in numero.

```
# Creiamo una variabile che contiene un intero
var = "boh"

# Convertiamo la variabile da intero a float
var = float(var)

print(var)
print(type(var))
```

quando eseguiremo:

---------------------------------------------------------------------------

```
ValueError                                Traceback (most recent call last)

<ipython-input-5-80155e966d89> in <module>()
      3       4 # Convertiamo la variabile da intero a float
----> 5 var = float(var)
      6       7 print(var)

ValueError: could not convert string to float: 'boh'
```

**APPROFONDIMENTO** Possiamo gestire le eccezioni con dei try-except, non tratteremo l'argomento in questo tutorial, ma puoi trovare informazioni in merito [qui](https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Fdocs.python.it%2Fhtml%2Ftut%2Fnode10.html)

## Liste, Tuple e Set

Ogni linguaggio di programmazione ci da la possibilità di creare sequenze di dati, Python lo fa con tre tipi, le liste e le tuple e i set  
Possiamo creare una lista di dati semplicemente racchiudendoli tra parentesti quadre e separandoli con una virgola

```
weights = [85.2, 80.3, 76.5 ,72.7, 69.8, 68.0,]

print(weights)

print(type(weights))
```

In questo caso abbiamo creato una lista che contiene i primi 7 valori della successione di Fibonacci. 

Possiamo conoscere la lunghezza di una lista utilizzando la funzione len.

`len(weights)`

### Indexing
---

Per accedere ad un elemento della lista dobbiamo inserire il suo **indice** tra parentesi quadre, questa opeazione è chiamata _indexing_.  
**NOTA BENISSIMO** In Python e in quasi tutti i linguaggi di programmazione gli indici partono da 0.

```
# stampiamo il primo elemento della lista
print(weights[0])

#stampiamo il secondo elemento della lista
print(weights[1])
```

L'utilizzo del - davanti all'indice ci permette di accedere alla lista dall'ultimo elemento verso il primo, in questo caso l'indice parte da 1 e non da zero, quindi con -1 accederemo all'ultimo elemento della lista.

```
# stampiamo l'ultimo elemento della lista
print(weights[-1])

# stampiamo il terzultimo elemento della lista
print(weights[-3])

```

### Slicing
---
Possiamo estrarre solo una parte della lista inserendo gli indici di inizio (incluso) e fine (escluso) separati da (:)

```
# primi 3 elementi della lista
print(weights[:3])

# quarto e quinto elemento 
print(weights[3:5])

# ultimi due elementi
print(weights[-2:])

# fino ali ultimi 2 elementi
print(weights[:-2])
```

Possiamo anche utilizzare un terzo valore, che indicherà il verso della selezione, valore 1: da sinistra a destra (valore di default) valore -1 da destra a sinistra (per ribaltare la lista).

```
# dall'ultimo al primo

weights[::-1]
```

### Verifica
---

Possiamo verificare se un elemento è contenuto nella lista con lo statement _in_, questo ritorna True se l'elemento è contenuto nella lista, altrimenti ritorna False (_in_ è molto utile utilizzato per creare istruzioni condizionali, di cui parleremo più sotto).

```
print(72.7 in weights)
```

quando eseguiremo:

`True`

```
people = ["Giuseppe", "Francesco", "Antonio"]
print("Sigismundo" in l)
```

quando eseguiremo:

`False`

### Modifica

---

Possiamo modificare il valore di un elemento della lista semplicemente accedendo ad esso e eseguendo un'assegnazione.

```
weights = [85.2, 80.3, 76.5 ,72.7, 69.8, 68.0]

print("Vecchio peso di partenza: %.1f" % weights[0])

# sostituiamo il valore alla posizione 0 con un 84.2

weights[0]=84.2

#stampiamo il primo elemento della lista

print("Nuovo peso di partenza: %.1f" % weights[0])
```

Per modificare il contenuto di una lista possiamo sfruttare i seguenti metodi:

- **append(e)** aggiunge un elemento e in fondo alla lista
- **insert(i,e)** aggiunge l'elemento e all'indice i della lista
- **remove(e)** rimuove l'elemento e dalla lista
- **pop(i)** rimuove l'elemento all'indice i

```
# creiamo una lista contenente solo due elementi
animals = ["topo", "gatto"]

# aggiungiamo la parola "cane" alla lista
animals.append("cane")
print(animals)

# rimuoviamo la parola "gatto" dalla lista
animals.remove("gatto")
print(animals)

# aggiungiamo un sinonimo di gatto alla posizione 1
animals.insert(1,"essere superiore")
print(animals)

# rimuoviamo l'elemento alla posizione 1
animals.pop(1)

# aggiungiamo un sinonimo più realistico di gatto alla posizione 1
animals.insert(1,"dominatore della terra, dell'universo e di tutto il creato")
print(animals)
```

Passiamo alle tuple, possiamo creare una tupla inserendo gli elementi tra parentesi tonde e separandoli con una virgola

```
animals_t = ("topo", "gatto", "cane", "uomo")

print(animals_t)

print(type(animals_t))
```

Per l'accesso agli elementi vale la stessa regola delle liste, quindi indexing e slicing.

```
# Stampiamo il primo elemento della tupla

print(animals_t[0])

# Stampiamo l'ultimo elemento della tupla

print(animals_t[-1])
```

Che differenza c'è tra una lista e una tupla ? La differenza consiste nel fatto che, una volta creata, una tupla non può essere modificata.

`t[0] = 5`

quando eseguiremo:

```
---------------------------------------------------------------------------

TypeError                                 Traceback (most recent call last)

<ipython-input-35-6dd06f73cec4> in <module>()
----> 1 t[0] = 5

TypeError: 'tuple' object does not support item assignment
```

Come vedi il tentativo di modificare un'elemento della lista scatena un'eccezione di tipo TypeError, che ci informa proprio del fatto che gli elementi di una tupla non possono essere modificati. Se questa cosa non ci sta bene possiamo sempre convertira la tupla in lista (e viceversa).

```
animals = list(animals_t)
print(animals)
print(type(animals))
```

Le stringe in Python possono essere considerate come tuple di caratteri, questo vuol dire che possiamo usare le operazioni di indexing e slicing anche su di esse.

```
s = "Hello world"

print(s[:5])
print(s[::-1])

s[4]="s"
```

quando eseguiremo:

```
Hello
dlrow olleH

---------------------------------------------------------------------------

TypeError                                 Traceback (most recent call last)

<ipython-input-40-9888b16a9851> in <module>()
      4 print(s[::-1])
      5 ----> 6 s[4]="s"

TypeError: 'str' object does not support item assignment
```

Anche in questo caso il tentativo di modificare un elemento ha scatenato la stessa eccezione.

```
### Altre funzioni utili per liste e tuple

hello_list = ["Ciao","Hello","Hola","Salut","Hallo","Ciao"]

hello_tuple = ("Ciao","Hello","Hola","Salut","Hallo","Ciao")

  

# ottieni l'indice dell'elemento

print(hello_list.index('Salut'))

print(hello_tuple.index('Salut'))

  

# conta quante volte è presente un'elemento

print(hello_list.count('Ciao'))

print(hello_tuple.count('Ciao'))
```

Veniamo ai set, i set sono insiemi di elementi unici non ordinati, questo vuol dire che un set non può contenere due volte lo stesso elemento e che non tiene conto della disposizione degli elementi al suo interno.
Possiamo creare un set inserendo gli elementi tra parentesi graffe e separandoli con una virgola.

```
my_set = {1,2,2,3,4,5,5}

print(my_set)

print(type(my_set))
```

**NOTA BENE:** Gli elementi duplicati all'interno di un set, vengono rimossi quando andiamo ad eseguire il nostro codice. Ora vediamo alcune funzioni utili per lavorare con i set.

```
# creiamo un set di nomi di persona


names = {"Giuseppe","Federico","Antonio","Matteo"}

print(names)

# aggiungiamo un elemento al set


names.add("Lorenzo")

print(names)

# se il nome è già presente, non verrà aggiunto


names.add("Federico")

print(names)

# rimuoviamo un nome


names.remove("Antonio")

print(names)  

# se il nome non è presente otterremo un'eccezione KeyError

# in tal caso possiamo piuttosto usare discard


names.discard("Paolo")

print(names)

# estraiamo un elemento dal set


name = names.pop()

print(name)

print(names)

# svuoitamo il set


names.clear()

print(names)
```

Possiamo convertire una lista in un set e vice versa utilizzando il casting.

**NOTA BENE** convertendo una lista in un set, gli elementi al suo interno verranno mischiati e i duplicati verranno rimossi.

```
my_list = ["Giuseppe","Federico","Giuseppe","Antonio","Matteo","Matteo"]

print(my_list)

print(type(my_list))


my_set = set(my_list)

print(my_set)

print(type(my_set))


my_list = list(my_set)

print(my_list)

print(type(my_list))
```

Possiamo anche creare un set immutabile utilizzando **frozenset**, in questo caso una volta creato non potremo più aggiungere o rimuovere elementi dal set.

```
names = frozenset({"Giuseppe","Federico","Antonio","Matteo"})

print(names)
```

<a id='dict'></a>
## Dizionari

Un dizionario è un tipo Python che ci permette di salvare dei dati in un formato chiave valore, in maniera tale da poter utilizzare la chiave per accedere al valore. Possiamo creare un dizionario con Python racchiudendolo tra parentesi graffe e separando chiavi e valori con **:**

```
# Creiamo un dizionario con una lista della spesa

# specificando cosa comprare come chiave e la quantità come valore

items = {"latte":3,"riso": 2, "tofu":5}

type(items)
```

Possiamo accedere ad un elemento del dizionario inserendo la chiave tra parentesi quadre

`items["tofu"]`

Se la chiave è inesistente otterremo un'eccezione di tipo KeyError.
Possiamo aggiungere un'altro elemento al dizionario semplicemente inserendo la chiave tra parentesi quadre ed eseguendo un'assegnazione

```
items["cereali"]=1

print(items)
```

E' possibile inserire all'interno di un elemento del dizionario un'altro dizionario.

```
items["yogurt"] = {"fragola":2, "bianco":3}
print(items)
```











