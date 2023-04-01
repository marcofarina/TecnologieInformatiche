# Calcolo della radice quadrata

## L'algoritmo babilonese

La radice quadrata di un numero è il valore che, elevato al quadrato, restituisce il numero stesso. Ad esempio, $\sqrt{16} = 4$, dato che $4^2=16$.

Il calcolo della radice quadrata è un'operazione matematica fondamentale, ma il metodo per ottenerla non è sempre stato così semplice come usare la calcolatrice oggigiorno. Uno dei primi metodi conosciuti risale all'antica Babilonia, dove si usava un algoritmo basato sulla _successione di approssimazioni_ che convergeva alla radice quadrata del numero cercato.

L'algoritmo è molto semplice e consiste di alcuni passaggi che vengono ripetuti più volte. Supponiamo di voler calcolare il valore della radice quadrata di $n$:

1. si inizia con un valore _approssimato_ della radice quadrata, ad esempio il valore stesso del numero diviso due. Si ottiene così una prima approssimazione della radice quadrata; $$x_0=\frac{n}{2}$$
2. successivamente si divide il numero di partenza per l'approssimazione ottenuta al passo precedente; $$y_0=\frac{n}{x_0}$$
3. a questo punto si fa la media tra il risultato ($y_0$) e l'approssimazione stessa ($x_0$); $$x_1=\frac{x_0+y_0}{2}$$
4. questo procedimento viene ripetuto un certo numero di volte, fino ad arrivare alla desiderata approssimazione del valore della radice quadrata. La seconda iterazione sarà quindi, ad esempio: $$y_1=\frac{n}{x_1}$$ $$x_2=\frac{x_1+y_1}{2}$$ e via dicendo.

Formalmente, il passo _i_-esimo dell'algoritmo si può scrivere come:

$$x_{i+1} = \frac{1}{2} \left(x_i + \frac{n}{x_i}\right)$$

dove $x_i$ è l'approssimazione ottenuta al passo $i$, e $n$ è il numero di partenza.

### Curiosità

<img align="right" width="200px" alt="Tavoletta babilonese" src="/media/tavoletta-babilonese.jpeg">

Questo metodo per il calcolo della radice quadrata ha una lunga storia. È stato scoperto dalla civiltà babilonese attorno al $-2000$ e fu utilizzato anche da altre culture antiche, come quella egizia e quella indiana. L'algoritmo veniva usato per calcolare radici quadrate di numeri molto grandi, come ad esempio per calcolare la lunghezza di un lato di un quadrato avente un'area pari a quella di un terreno coltivato.

Nella figura qui accanto si può osservare una tavoletta babilonese che riproduce un esercizio matematico per trovare la diagonale di un quadrato ricorrendo proprio al calcolo della radice quadrata.

In Europa, il metodo è stato introdotto da Leonardo Pisano, noto come Fibonacci, nel quattordicesimo capitolo del suo libro "_Liber Abbaci_" del 1202, ispirandosi alle dalle opere di matematici arabi come al-Khwarizmi e Abu Kamil.[^1]

## L'algoritmo babilonese per calcolare la radice quadrata

Per svolgere l'esercizio su Flowgorithm, è necessario utilizzare un ciclo `for` che approssimerà sempre meglio il valore della radice quadrata.

Sarà quindi necessario svolgere i seguenti passi:

* Chiedere all'utente di inserire il numero di cui vuoi calcolare la radice quadrata
* Impostare il numero di iterazioni desiderate (da stabilire in base a quanto volete rendere precisa l'approssimazione del calcolo della radice quadrata)
* Inizializzare la variabile che rappresenta l'approssimazione con il valore del numero diviso 2
* Ripetere il numero di volte desiderato il calcolo della media esplicitato precedentemente.
* Visualizzare in output il valore reale della radice quadrata (tramite la funzione `sqrt()` di Flowgorithm) e confrontarlo con il valore dell'approssimazione dato dal metodo babilonese.

[^1]: https://www.matematicamente.it/magazine/19aprile2013/183-Mazzucato-Radice.pdf