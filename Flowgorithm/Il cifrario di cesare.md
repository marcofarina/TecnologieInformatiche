# Crittografia

## Steganografia
>_«Istieo, volendo comunicare ad Aristagora l'ordine di insorgere, non aveva sistema sufficientemente sicuro per avvisarlo, dato che le strade erano tutte sotto controllo; allora, rasato il capo al più fidato dei suoi servi, vi tatuò dei segni, attese che ricrescessero i capelli e appena furono ricresciuti lo mandò a Mileto con il solo incarico, una volta giuntovi, di invitare Aristagora a radergli i capelli e a dargli una occhiata sulla testa. Il tatuaggio ordinava, come ho già detto, la ribellione.»_
> 
> Erodoto, Storie – Libro V

Fin dalle origini della comunicazione, gli esseri umani hanno sempre avuto la necessità di proteggere le proprie informazioni. I primi resoconti storici di tecniche dedicate all'occultamento dei messaggi arrivano dalle _Storie_ di Erodoto, uno dei primi esempi di storiografia in Occidente, scritto tra il –440 e il –429. In particolare, il Libro V si concentra sulla storia delle guerre persiane e descrive gli eventi che portarono alla seconda invasione della Grecia da parte dei Persiani, guidati dal re Serse, nel –480. Il libro contiene la descrizione di alcune delle più antiche tecniche di occultazione dei messaggi, conosciuta oggi come _steganografia_ (dal greco στεγανός –_coperto_– e γραφία –_scrittura_–).

Nel libro viene raccontato un episodio riguardante Istieo, tiranno di Mileto, che voleva comunicare in modo segreto con Aristagora, per incitarlo alla ribellione contro Dario. Per eludere il controllo dei soldati, Istieo scrisse il messaggio sulla nuca rasata di un suo servitore, aspettò che i capelli ricrescessero, ed infine inviò il messaggero al destinatario. Il servitore aveva ricevuto l'ordine di radesi la testa e di mostrarla ad Aristagora, il quale potè leggere nuovamente il messaggio.

Su questa tecnica possiamo fare un'importante considerazione: il metodo usato da Istieo è valido fintanto che non viene scoperto dai suoi avversari. Se la tecnica dovesse essere scoperta, le parti che vogliono comunicare segretamente dovranno inventare un nuovo metodo, il che può risultare scomodo. La sicurezza della comunicazione, in questo caso, si basa sulla segretezza del metodo. 

Per risolvere quest'ultimo problema è necessario aggiungere un nuovo ingrediente alla tecnica di occultamento del messaggio: un'informazione da mantenere segreta senza la quale è impossibile ricostruire il messaggio. Usando questo stratagemma ciò che rende sicura la comunicazione si sposta dalla segretezza del metodo, alla segretezza di un pezzo dell'informazione. Nasce così la **crittografia**, ovvero l'arte di proteggere l'informazione da occhi indiscreti _trasformando_ il messaggio (invece di _nasconderlo_) in modo che solo il destinatario previsto possa leggerlo.

## Il cifrario di Cesare

> _Extant et ad Ciceronem, item ad familiares domesticis de rebus, in quibus, si qua occultius perferenda erant, per notas scripsit, id est sic structo litterarum ordine, ut nullum verbum effici posset: quae si qui investigare et persequi velit, quartam elementorum litteram, id est D pro A et perinde reliquas commutet._
> 
> Svetonio, _De vita Caesarum_, Libro I, capitolo 56

La prima idea per migliorare la protezione dei messaggi che vanno trasmessi segretamente è quella di sostituire i segni che compongono la scrittura con altri, seguendo una certa regola. Questa tecnica viene chiamata di **sostituzione**.

Uno dei primi esempi di trasformazione del messaggio per sostituzione è quella descritta da Svetonio nella sua biografia di Giulio Cesare. Egli racconta che nella sua corrispondenza, Cesare era solito a sostituire ogni lettera delle parole del messaggio con la lettera che occupa tre posizioni più avanti nell'alfabeto, quindi A con D, B con E, C con F e via dicento. In questo metodo l'alfabeto va immaginato come "circolare", quindi lo scorrimento dopo la lettera Z ricomincia dalla A.

```
A B C D E F G H I J K L M N O P Q R S T U V X Y Z (testo in chiaro)
D E F G H I J K L M N O P Q R S T U V X Y Z A B C (testo cifrato)
```
Per esempio, se volessimo trasformare il messaggio "_et tu Brute?_", dovremmo sostituire ogni lettera ed ottenere il messaggio segreto "_hw wx Euxwh?_".

Anche se Cesare usava uno scorrimento di tre posizioni, non siamo obbligati a seguire questa regola: nel momento in cui decidiamo di scegliere casualmente il numero di scorrimenti e di non divulgarlo, stiamo creando quell'informazione segreta che ci porta da una scrittura in _codice_ ad una scrittura _cifrata_. La crittografia infatti, a differenza dei codici, prevede l'utilizzo di una **chiave segreta** come elemento fondamentale per la trasformazione del messaggio.

Immaginiamo quindi di scegliere un numero intero $K$[^1], che indica di quante posizioni scorrere nell'alfabeto. Immaginando di rappresentare le lettere dell'alfabeto dalla A alla Z con i numeri da 0 a 25, il processo di cifratura sarà semplicemente la somma tra la lettera e la chiave $K$: indicando con $C$ la lettera cifrata e con $M$ la lettera del messaggio, avremo la regola di cifratura:

$$ C = M + K\, \pmod{26} $$

In questa equazione $(\mod 26)$ indica l'operazione aritmetica di modulo, che introdurremo più avanti. Per il momento la possiamo semplicemente vedere in questi termini: se la somma $M + K$ è maggiore o uguale a 26, allora si sottrae 26 al risultato.[^2]

Il procedimento che trasforma il messaggio cifrato in quello originario viene detto **decifratura**. Nel cifrairio di Cesare sarà sufficiente calcolare

$$ M = C - K\, \pmod{26} $$

### L'algoritmo del Cifrario di Cesare
Possiamo ora stabilire un algoritmo di cifratura:

```
leggi il testo in chiaro M
leggi la chiave K
per ogni lettera del messaggio M
    calcola il testo cifrato C sommando il messaggio M alla chiave K
scrivi il testo cifrato C 
```
Per la realizzazione di questo algoritmo in Flowgorithm è indispensabile imparare ad usare alcune [funzioni predefinite nel linguaggio](http://www.flowgorithm.org/documentation/intrinsic-functions.html):
* `Len(s)`: restituisce la lunghezza intera di una stringa;
* `Char(s, i)`: restituisce il carattere alla posizione `i` della stringa `s`;
* `ToChar(n)`: converte un numero intero n rappresentante il codice ASCII nel carattere corrispondente;
* `ToCode(c)`: converte un carattere `c` nel codice ASCII corrispondente.

Realizzare su Flowgorithm sia l'algoritmo cifrante che quello decifrante.

[^1] Nei testi riguardanti la crittografia solitamente la chiave crittografica si rappresenta con la lettera K, iniziale di _key_, _chiave_.

[^2] Per chi ha studiato qualcosa di algebra, stiamo lavorando nel gruppo $Z_{26}$.