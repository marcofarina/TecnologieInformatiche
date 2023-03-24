# La successione di Fibonacci

## Cenni storici e teorici
Le [successioni](https://it.wikipedia.org/wiki/Successione_(matematica)) sono sequenze di numeri che seguono un certo schema. La successione di Fibonacci è una delle più famose e si basa su una semplice regola: ogni termine della successione è la somma dei due precedenti, partendo da 0 e 1. Quindi la successione inizia con 0, 1 e poi continua con 1, 2, 3, 5, 8, 13, 21, 34 e così via.

Per esempio, per calcolare il quinto termine della successione di Fibonacci, si devono sommare i due termini precedenti: 1 + 1 = 2. Quindi il quinto termine è 2.

Il sesto termine è la somma dei quarto e del quinto termine: 3 + 2 = 5.

Il settimo termine è la somma del quinto e del sesto termine: 2 + 5 = 7.

E così via, continuando a sommare i due termini precedenti per ottenere il termine successivo nella successione di Fibonacci.

Per calcolare la [successione di Fibonacci](https://it.wikipedia.org/wiki/Successione_di_Fibonacci), è possibile utilizzare la seguente formula matematica: $f_n = f_{n-1} + f_{n-2}$
dove $f_n$ rappresenta l'ennesimo termine della successione.

## Indicazioni generali
Per svolgere l'esercizio su Flowgorithm, è necessario utilizzare un ciclo FOR che eseguirà il calcolo per un determinato numero di volte, ovvero il numero di termini della successione di Fibonacci che si vuole ottenere.

* Chiedere all'utente di inserire il numero di termini della successione di Fibonacci che si vuole ottenere.
* Inizializzare due variabili, una per il primo termine $f_0$ e una per il secondo termine $f_1$, entrambe a 0.
* Utilizzare il ciclo `for` per calcolare i successivi termini della successione fino al termine desiderato.
* All'interno del ciclo `for`, assegnare alla variabile temporanea il valore della somma tra $f_0$ e $f_1$.
* Stampare il valore della variabile temporanea.
* Assegnare alla variabile $f_0$ il valore di $f_1$ e alla variabile $f_1$ il valore della variabile temporanea.
* Il ciclo `for` termina quando si sono calcolati tutti i termini.