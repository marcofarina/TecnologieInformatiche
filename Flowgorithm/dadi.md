# Dadi, casualità e D&D
In Dungeons & Dragons e molti altri giochi di ruolo il lancio dei dadi è usato per determinare l'esito delle prove e degli attacchi.

In questa e in molte altre categorie di giochi, chi ha una solida comprensione delle probabilità e della frequenza con cui determinati risultati possono essere ottenuti attraverso il lancio dei dadi, può trarre un vantaggio a lungo termine rispetto a colore che non hanno questa conoscenza.

## Probabilità e statistica
Il calcolo delle probabilità e la statistica sono due discipline che si occupano di valutare la probabilità di eventi e comprendere quanto è probabile che accadano. Ad esempio, nel lancio di una moneta, si sa che c'è una probabilità del 50% di ottenere testa e una del 50% di ottenere croce. Questo tipo di analisi è noto come "_calcolo delle **probabilità**_".

D'altra parte, la **statistica** viene impiegata per analizzare dati derivanti da esperimenti e rispondere a domande specifiche, come ad esempio "_quanti studenti nella mia scuola hanno una valutazione superiore a 8 in informatica?_".

In generale, si può affermare che il calcolo delle probabilità si concentra sulla valutazione di eventi teorici, mentre la statistica si occupa di analizzare osservazioni basate sulla realtà.

### Pseudocasualità
Nella nostra definizione degli algoritmi abbiamo sottolineato che essi sono _deterministici_, il che significa che sono completamente prevedibili: dato un determinato input, l'algoritmo produrrà sempre lo stesso output, senza alcuna variazione o casualità, indipendentemente da quante volte venga eseguito.

Ma come è possibile, quindi, che nei linguaggi di programmazione esistano funzioni che restituiscono valori casuali, come ad esempio la funzione `Random()` in Flowgorithm?

In realtà, queste funzioni non violano la natura deterministica degli algoritmi. Quello che fanno è simulare l'aspetto di casualità attraverso un meccanismo chiamato _generazione pseudo-casuale_. Questo significa che, sebbene i valori prodotti possano sembrare casuali, in realtà sono determinati da un processo matematico ben definito.

La funzione `Random()` utilizza un algoritmo che genera una sequenza di numeri basati su un _seed_ (seme), cioè un valore iniziale. Se si utilizza lo stesso seme, la sequenza di numeri generata sarà sempre la stessa. Tuttavia, cambiando il seme, si otterrà una sequenza diversa. In molti casi, il seme viene impostato utilizzando un _timestamp_ (il tempo attuale del sistema) come punto di partenza. Poiché il tempo di sistema cambia costantemente, l'uso di questa informazione come seme può fornire una sequenza apparentemente casuale di numeri.

Quindi, anche se sembra che le funzioni di generazione casuale introducano casualità negli algoritmi, in realtà sono ancora algoritmi deterministici che operano su sequenze di numeri pseudo-casuali.

Le sequenze pseudocasuali sono ampiamente utilizzate in applicazioni informatiche che richiedono una fonte di casualità, come la crittografia (che studieremo in quinta), la simulazione di eventi casuali e la creazione di giochi.

## Misuriamo la casualità di Flowgorithm
In questo esercizio condurremo un'analisi empirica[^1] sulla "casualità" della generazione di numeri in Flowgorithm. Tuttavia, lo stesso esperimento può essere facilmente ripetuto utilizzando qualsiasi altro linguaggio di programmazione.

Iniziamo con un esempio molto semplice: supponiamo di lanciare un dado a sei facce numerate da 1 a 6 e vogliamo determinare la _probabilità_ di ottenere un 6. Sappiamo che abbiamo un caso favorevole su un totale di sei possibili risultati, corrispondenti alle facce del dado. Pertanto, possiamo affermare che:

$$ P(6) = \frac{1}{6} $$

Ciò significa che in media, su sei lanci, ci si aspetta di ottenere un 6.

Per verificare se l'algoritmo di generazione di numeri casuali in Flowgorithm rispecchia questa probabilità, dobbiamo condurre un esperimento che coinvolga la raccolta di dati. È qui che entra in gioco la statistica.

#### Esercizio 1: simulazione del lancio di 1000000 di dadi da 6 facce
Scrivi un algoritmo che lancia per $1000000$ volte un dado da $6$ facce e conta quante volte è uscito un $6$.

La teoria ci dice che circa $\frac{1}{6}$ di questi lanci dovrà essere un $6$, quindi ci aspettiamo di avere come output un conteggio di circa $166666$.[^2]

### I dadi di Dungeons & Dragons
In Dungeons & Dragons (D&D) e in molti altri giochi di ruolo, vengono utilizzati diversi tipi di dadi per determinare gli esiti delle azioni e delle situazioni all'interno del gioco. Uno dei concetti fondamentali riguarda la notazione "$x$d$y$", dove $x$ rappresenta il numero di lanci e $y$ indica il tipo di dado utilizzato. Ad esempio, `1d20` indica il lancio di un dado a venti facce, mentre `2d6` rappresenta il lancio di due dadi a sei facce.

Ogni tipo di dado ha un range di valori possibili. Ad esempio, un dado a quattro facce (d4) può generare valori da 1 a 4, mentre un a venti facce (d20) può produrre valori da 1 a 20. La scelta del tipo di dado dipende dall'azione o dalla situazione in cui viene utilizzato.

La notazione "xdy" viene spesso utilizzata per determinare i risultati di azioni come attacchi, tiri salvezza, controlli delle abilità o determinare l'efficacia di un incantesimo. I valori ottenuti lanciando i dadi vengono poi sommati o utilizzati in base alle regole specifiche del gioco per determinare l'esito dell'azione.

#### Esercizio 2: lanciare `1d12` e `2d6`
I giocatori esperti sanno che lanciare `1d12` e `2d6` non è la stessa cosa! Realizza un algoritmo con Flowgorithm che richiama due funzioni:
- la prima funzione lancia 1000 volte 1d12 e conta quante volte è uscito ognuno dei numeri da 1 a 12.[^3]
- la seconda funzione lancia 1000 volte 2d6 e conta quante volte è uscito ognuno dei numeri da 1 a 12.

Al termine dell'esercizio esegui l'algoritmo (anche più di una volta se vuoi) e produci una relazione che riporti i dati che hai risponda alle seguenti domande:
1. Qual è il valore minimo che si può ottenere lanciando 1d12? E lanciando 2d6?
2. Qual è il valore massimo che si può ottenere lanciando 1d12? E lanciando 2d6?
3. Qual è la somma più probabile ottenibile lanciando 1d12? E lanciando 2d6?
4. Quali sono le differenze nell'andamento delle probabilità tra i due lanci?

La relazione dovrà contenere anche un istogramma dei valori ottenuti sia con il lancio dei d12, sia con il lancio dei d6. Puoi creare l'istogramma con un qualsiasi foglio di calcolo, come Microsoft Excel, Google Fogli o Numbers.

[^1]: Un'analisi o un esperimento empirico si basa sulla raccolta di dati concreti, osservazioni e misurazioni reali, piuttosto che su ragionamenti puramente teorici o astratti. L'obiettivo è acquisire conoscenza o supporto per una teoria o una conclusione basandosi su prove concrete.

[^2]: Può succedere che mandando in esecuzione questo algoritmo Flowgorithm sembri bloccato: è normale! Dovendo generare un milione di numeri impiegherà del tempo, che dipende anche dalla potenza del tuo computer. Dopo aver avviato l'algoritmo dovrai attendere per un po' prima di visualizzare il risultato.

[^3]: Sì, dovrai dichiarare 12 variabili! Questo tedioso problema verrà risolto all'inizio del prossimo anno quando impareremo ad usare strutture dati più complesse.