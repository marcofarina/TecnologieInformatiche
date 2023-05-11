# Dadi, casualità e D&D
In Dungeons & Dragons e molti altri giochi di ruolo il lancio dei dadi è usato per determinare l'esito delle prove e degli attacchi.

In questo e in molti altri tipi di giochi, chi ha una buona comprensione delle probabilità e della frequenza con cui determinati risultati possono essere ottenuti mediante il lancio dei dadi, può trarre un vantaggio a lungo termine rispetto a chi non ha questa conoscenza.

## Probabilità e statistica
Il calcolo delle probabilità e la statistica sono due discipline che si occupano di capire quanto è possibile che succeda qualcosa. Ad esempio, se lanci una moneta sai che c'è una possibilità su due che esca testa e una su due che esca croce. Questa analisi è chiamata _calcolo delle probabilità_. 

La statistica viene usata invece per analizzare dati provenienti da esperimenti e rispondere ad eventuali domande che ci poniamo, come "quanti studenti nella mia scuola hanno più di 8 in informatica?". 

In generale possiamo affermare che il calcolo delle probabilità si concentra sulla possibilità di eventi teorici, mentre la statistica sulle osservazioni reali.

### Pseudocasualità
Quando abbiamo dato una definizione di algoritmo abbiamo affermato che essi sono _deterministici_, ovvero che essi sono completamente prevedibili: dato un certo input, non importa quante volte eseguirò l'algoritmo, otterrò sempre lo stesso output, senza alcuna variazione o casualità.

Com'è possibile allora che esistano nei linguaggi di programmazione delle funzioni che restituiscono valori casuali, come la funzione `Random()` in Flowgorithm?

La risposta è data dal concetto di **pseudocasualità**: le funzioni `Random()` producono sequenze di numeri che sembrano casuali, ma che in realtà sono generate da algoritmi deterministici. Tali algoritmi utilizzando un seme (o _seed_) come input iniziale e producono una sequenza di numeri che appaiono imprevedibili, ma che in realtà sono il risultato di una formula matematica deterministica.

Le sequenze pseudocasuali sono ampiamente utilizzate in applicazioni informatiche che richiedono una fonte di casualità, come la crittografia (che studieremo in quinta), la simulazione di eventi casuali e la creazione di giochi.

## Misuriamo la (pseudo)casualità di Flowgorithm
In questo esercizio misureremo empiricamente la "casualità" della generazione di numeri in Flowgorithm. Lo stesso esperimento può naturalmente essere ripetuto con qualsiasi linguaggio di programmazione.

Partiamo da un esempio molto semplice: se lanciamo un dado con sei facce numerate da 1 a 6 e vogliamo sapere qual è la _probabilità_ di ottenere un 6, sappiamo di avere un caso favorevole su un totale di sei casi totali, uno per ogni faccia del dado. Quindi possiamo affermare che

$$ P(6) = \frac{1}{6} $$

Questo significa che ogni sei lanci in media otterrò un 6.

Possiamo verificare con un esperimento se l'algoritmo di generazione di numeri casuali di Flowgorithm rispecchia questa probabilità. È qui che entra in gioco la statistica. Per effettuare una misurazione dobbiamo produrre dei dati.

#### Esercizio 1: simulazione del lancio di 1000000 di dadi da 6 facce
Scrivi un algoritmo che lancia per $1000000$ volte un dado da $6$ facce e conta quante volte è uscito un $6$.

La teoria ci dice che circa $\frac{1}{6}$ di questi lanci dovrà essere un $6$, quindi ci aspettiamo di avere come output un conteggio di circa $166666$.[^1]

[^1]: Può succedere che mandando in esecuzione questo algoritmo Flowgorithm sembri bloccato: è normale! Dovendo generare un milione di numeri impiegherà un po' di tempo, che dipende anche dalla potenza del tuo computer. Dopo aver avviato l'algoritmo dovrai attendere per un po' prima di vedere il risultato.