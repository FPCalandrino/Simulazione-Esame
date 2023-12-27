# Tombola

Si vuole implementare in Python un programma che simuli una partita a Tombola fra due giocatori.

Le schedine che i due giocatori intendono giocare sono presenti nei due file `schedina1.txt` e `schedina2.txt`.

Le schedine sono strutturate in modo tale che siano delle tabelle di dimensione **3 x 9 caselle**,
dove in **ogni riga** ci devono essere esattamente **5 numeri** (le **caselle vuote** sono contrassegnate da una **X**).

Nelle righe sottostanti viene riportato un esempio della struttura che deve avere una schedina.

#### Esempio file `schedina1.txt`
```
X 11 21 X 45 X 60 X 83
X 14 X 36 X 50 X 76 88
6 X 25 X 47 52 X 71 X
```

#### Esempio file `schedina2.txt`
```
X 16 X 33 48 53 X X 82
8 10 X X 42 X 67 X 87
2 X 28 32 X X X 74 90 
```

Come si può notare, la schedina è strutturata in modo tale che ogni colonna contenga numeri tali per cui la decina coincida con l'indice della effettiva colonna
(nella colonna **1** ci sono i numeri da **10 a 19**, nella colonna **2** ci sono i numeri da **20 a 29**, e così via; l'unica eccezzione è l'**ultima colonna** che contiene anche il **90**!).

Ad ogni turno viene estratto, in maniera casuale, un numero da **1 a 90** (uno stesso numero non può uscire più volte!); il programma deve verificare se tale numero sia presente nelle schedine da gioco, e se è affermativo sostituire
tale valore con un **O**.

Infine, il programma deve segnalare quando un giocatore fa: 

* **AMBO** (due O in una stessa riga);
* **TERNO** (tre O in una stessa riga);
* **QUATERNA** (quattro O in una stessa riga);
* **CINQUINA** (cinque O in una stessa riga);
* **TOMBOLA** (tutte le caselle non vuote sostiuite da O)

Quando un giocatore fa TOMBOLA, finirà la partita.

Si assuma che:
* Ogni combinazione può essere fatta una e una sola volta da un solo giocatore (se G1 fa AMBO, G2 non lo può più fare, a meno che non lo abbiano fatto in contemporanea);
* Il formato del file sia corretto.

#### Esempio di output
```
Schedine giocate:

X 11 21 X 45 X 60 X 83                X 16 X 33 48 53 X X 82
X 14 X 36 X 50 X 76 88                8 10 X X 42 X 67 X 87
6 X 25 X 47 52 X 71 X                 2 X 28 32 X X X 74 90 

> Numero uscito: 53

X 11 21 X 45 X 60 X 83                X 16 X 33 48 O X X 82
X 14 X 36 X 50 X 76 88                8 10 X X 42 X 67 X 87
6 X 25 X 47 52 X 71 X                 2 X 28 32 X X X 74 90

> Numero uscito: 82

X 11 21 X 45 X 60 X 83                X 16 X 33 48 O X X O
X 14 X 36 X 50 X 76 88                8 10 X X 42 X 67 X 87
6 X 25 X 47 52 X 71 X                 2 X 28 32 X X X 74 90

Il giocatore 2 ha fatto AMBO!

...

> Numero uscito: 71

X O O X O X O X O                X O X 33 O O X X O
X O X O X O X O O                8 10 X X O X O X O
O X O X O O X O X                O X O 32 X X X 74 O

Il giocatore 1 ha fatto TOMBOLA!
```

