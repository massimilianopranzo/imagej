
# Image J Seminar
Immagine:
- Rappresentqzione didimensionale secondo coordinate spaziali indipendenti di un'entità fisica relativa d un oggetto o a una scena
- Funcione di due o tre varibiali reali L(x,y) o L(x,y,z) dove L rappresenta l'entità fisica (es. intensità luminosa) di ciascun punto di un piano o di un volume di intersse identificato con coordinate x,y o x,y,z

Immagine digitale (definizione funzionale):
- Matrice di pizel quadrati or rettangolari organizzati in righe e colonne (matrice tridimensionale e voxel nel caso di immagini tridimensionali)

Image processing:
- Lo studio di qualsiasi algoritmo che ha come input un'immagine digitale e restituisce a sua volta un'immagine digitale o informazioni estratte dall'immagine originale
- Include le seguenti operazioni:
	- visualizzazione e stampa
	- editing e manipolazione di immagini (image editing)
	- correzione di immagini (image restoration)
	- miglioramento di immagini (image enhancement)
	- identificazione di caratteristiche di interesse (feature detection)
	- compressione di immagini (image compression)


Image formation: object in -> image out  	<br>
Image processing: image in -> image out		<br>
Image analysis: image in -> features out	<br>

Computer graphics: numeri in -> image out
Computer vision: image in -> interpretation out
Visualization: image in -> representation out

Un'immageine viene rappresentata come una matrice di pixel, dove ogni pixel è un numero che rappresenta un colore.

Perchè elaborare e analizzare immagini?
- Realizzare immagini accattivanti, efficaci, informative (image processing)
	- Pubblicazioni, presentazioni, siti web, social 
- Estrarre informazioni qualitative e quantitative da immagini (image analysis)
	- Misurazioni dimensionali, conteggi, livelli di attività
- Rendere possibili test e attività sperimentali (automation)
	- Sequenziamento genomico, identificazione di nuove galassie, automazione industriale, controllo di qualità di linea
- Adottare un approccio oggettivo e riproducibile (science)
	- Essenziale per un processo scientifico

Percezione umana e limiti:
Il nostro sistema visivo non vede tutto lo spettro elettromagnetico, ma solo una piccola parte (400-700 nm).


- Occorre quindi convertire segnali ottenuti tramite radiazioni elettromagnetiche non visibili all'occhio umano in rappresentazioni nello spettro del visibile.
- Perché è possibile analizzare immagini ottenute da segnali differenti dalle radiazioni elettromagnetiche

Perchè il sistema di visione e percezione umano non permette sempre valutazioni affidabili.
La retina include due fotorecettori:
- Coni: localizzati nella fovea, altamente sensibili al colore, non lavorano a bassi livelli di illuminazione 
- Bastoncelli: localizzati altrove, contribuisco alla percezione del contest, sono incapaci di distinguere il colore, lavorano anche a bassi livelli di illuminazioneIl sistema di visione e percezione umano non permette sempre valutazioni affidabili.

II segnale relativo all'intensità luminosa raccolta dai singoli fotorecettori deve venire elaborato (localmente e dal cervello) per bilanciare gli effetti dovuti ai tessuti sovrastanti che assorbono frazioni non trascurabili di luce.

Il sistema di visione e percezione umano:
- è limitato alle lunghezze d'onda comprese fra 380 e 700 nm, con una maggiore sensibilità intorno ai 550 nm;
- riesce a discriminare poco più di un centinaio di gradazioni di grigio (intensità luminosa);
- interpreta in maniera non lineare la relazione fra intensità della luce riflessa e l'intensità luminosa percepita di un oggetto;
- tende a sopravvalutare o sottovalutare le informazioni al confine fra oggetti di differente intensità (effetto Mach band);
- è influenzata dalla luminosità dello sfondo (effetto di contrasto simultaneo);
- La percezione del colore di un'oggetto è influenzata dal colore del contesto;
- Applica in maniera non controllabile algoritmi interpretativi e ricostruttivi dell'immagine.

L'intensità percepita non è una semplice funzione dell'intensità luminosa reale <br>

![](machband.png)
![](processinglevels.png)

Esempio di acquisizione immagine
![](imagecapturing.png)

L'acquisizione permette di memorizzare l'immagine su supporto informatico (image digitization);
- II più piccolo elemento costituente l'immagine digitale è il «pixel» (picture-e/ement);
- I pixel contengono un unico valore, come in una cella di un foglio di calcolo;
I pixel vengono affiancati orizzontalmente e verticalmente come una sorta di mosaico. <br>

Viene stabilito:
- L'ordine in cui raccogliere e immagazzinare le infognazioni relative a ciascun pixel.
- Come archiviare l'informazione relativa a ciascun pixel.
![](matriximage.png)

Per aquisire un'immagine digitale sono necessarie due operazioni in sequenza:
- campionamento (sampling)
- quantizzazione (quantization)

Entrambi i passaggi eseguono una riduzione delle informazioni originali (analogiche e quindi appartenenti ad un continuum) in informazioni digitali, quindi necessariamente campionate e discretizzate. <br>
II processo comporta una perdita irreversibile di parte dell'informazione. <br>
L'operazione di campionamento è estremamente delicata e può portare a gravi errori di interpretazione (aliasing), in funzione della frequenza di campionamento (teorema del campionamento: $f_s \geq 2 B$). <br>
La catena di acqusizione digitale delle immagini
![](digitalcaptureimage.png)

II CAMPIONAMENTO (Sampling) di una Immagine (2D) consiste nel suddividere l'immagine in tanti quadretti (pixel) come se si sovrapponesse una griglia.
- Intervallo di campionamento (distanza tra i punti)
- Tassellamento (disposizione geometrica dei pixel)
- II numero di pixel in cui si suddivide l'immagine definisce la risoluzione

Minore è il numero totale di pixel, minore è la risoluzione spaziale dell'immagine <br>
Un'immagine può essere ricampionata a minore risoluzione spaziale con perdita di informazione. <br>
L'immagine viene poi QUANTIZZATA, cioè si attribuisce un valore di intensità luminosa (ed eventualmente di colore) a ciascun pixel.
![](matrixcreation.png)

La quantizzazione converte l'immagine da una rappresentazione analogica continua ad una discreta attraverso i livelli di decisione o profondità $dk = 2^m$ (dk toni di grigio, m: numero di bit necessari a descrivere il tono di )grigio
- Se m = 8 consegue che dk= 256 (0-255)
- Se m = 12 ne consegue che dk= 212 = 4096 (0-4095)
- se m = 16 ne consegue che 216= 65536 (0-65535)
ADC: Analog to Digital Converter, definisce i livelli di decisione nel processo di quantizzazione del segnale analogico

La qualità complessiva di un'immagine digitale dipende perciò:
- dal processo di campionamento (spaziale)
	- numero di pixel
- dal processo di quantizzazione (profondità colore di toni di grigio)
	- bit di quantizzazione

Rappresentazione di un'immagine digitale:
- matrice di dimensione M x N di numeri interi

II rapporto di forma (aspect ratio)
- rappresenta il rapporto tra il numero di pixel in orizzontale e quello in verticale
(Nx/Ny).
- Un formato 4/3 vuol dire che il lato più corto è tre quarti del lato più lungo.
Formati più diffusi:
![](formati.png)

Dimensione dei file
- Dimensione di un file di immagine non compresso (es. bitmap) qualità fotografica a colori:
	- 1 colore 8-bit (256 toni di grigio)
	- 3 colori 24-bit (16 milioni di colori)
- Dimensione in bit:
[2000 x 3000]pixel x 8-bit a colore x 3 colori = 144.000.000 bit, pari a circa 17Mb.

Cio che vediamo sullo schermo, spesso non è tutta l'informazione contenuta nell'imagine!
I monitor dei computer gestiscono (generalmente) 256 livelli di grigio (8 bit)
- L'immagine RGB visualizzata presenta $256^3= 16777216$ colori (24-bit, true-color)
- Tale valore è, al più, quello che l'occhio umano può distinguere.
- Spesso le immagini scientifiche vengono acquisite usando 16-bit = 65536 livelli di grigio.
- Considerando i limiti dell'occhio umano, I monitor spesso mostrano meno dello 0,4% dell'informazione contenuta in una buona imagine digitale.

## Compressione delle immagini
File senza compressione: RAW, BMP
Gli algoritmi per la compressione delle immagini sono divisi in 2 famiglie:
- Compressione senza perdita (lossless): TIFF, PNG
- Compressione con perdita: JPEG, GIF
La compressione lossy può generare notevoli artefatti nei bordi netti.

Le immagini vengono in genere salvate in formato TIFF (.tif), compressione no lossy.
Non salvare in formato JPEG (.jpg) per usi metrologici!!!
- I valori nei pixel vengono notevolmente alterati.
- Utile solo per una visione qualitativa e per essere spedite via mail o per il web (formato molto leggero).
- E' possibile utilizzarle per analisi quantitative solamente quando l'informazione da estrarre è semplice o i dati disponibili sono sovrabbondanti (i.e. giorno o notte, persone o edifici, interni o esterni, risoluzione spaziale molto superiore rispetto alle dimensioni delle features di interesse...).
![](imagedimension.png)

Elaborazione di immagini: <br>
Correzione dei difetti (Image restoration)
- mira a rimuovere o ridurre il degrado o la distorsione che un'immagine potrebbe aver subito durante l'acquisizione, la trasmissione o l'archiviazione.
- Tende a lavorare su porzioni di immagine con metodi generalmente lineari. E' un processo oggettivo. 

Miglioramento dell'immagine (Image enhancement)
- mira a migliorare la qualità visiva di un'immagine aumentandone il contrasto, la luminosita o la nitidezza.
- In genere agisce sull'intera immagine impiegando spesso metodi non lineari. E' un processo soggettivo.

## Convoluzione
La convoluzione è un'operazione matematica semplice in cui 2 matrici (l'immagine ed il kernel) producono come risultato una terza matrice.
- Consiste nei seguenti processi:
- Si sovrappone un kernel (o maschera) all'immagine
- Si moltiplicano i termini coincidenti
- Si sommano i risultati e si divide per il peso per $\sum_{i=1} k_{ij}$
- Si sposta il kernel al pixel successivo (su tutta la matrice immagine)
![](convolution.png)

Tipi di kernel: <br>
![](filters.png)

## Correzione dei difetti (Image restoration)
Rappresenta la prima fase di processamento delle immagini al fine di ridurre i difetti dovuti
- Catena di acquisizione mal configurata
- Illuminazione non uniforme
- Alterazioni dovute alla prospettiva
- Altre fonti di segnale non ritenute utili
Tali correzioni sono comunque meno efficaci rispetto all'ottimizzazione dell'acquisizione dell'immagine nella finestra dinamica di interesse (decisa a priori adattando opportunamente la catena di acquisizione).

Elaborazione delle immagini per incrementare il rapporto segnale/rumore <br>
Dopo aver definito precisamente cosa si ritiene sia segnale e cosa rumore (ad es. polvere o graffi, presenti nell'immagine ma non correlati alla microstruttura). <br>
Generalmente disponibile nei sistemi di elaborazione d'immagine commerciali:
- convoluzioni,
- filtri matematici e morfologici
- Filtri logici o booleani
- analisi nel dominio delle frequenze (FTT e RTFTT)
Questa fase è delicata e richiede notevole esperienza da parte dell'operatore.

Spesso è necessario lavorare sul rapporto segnale/rumore, a causa di:
- Instabilità della sorgente luminosa,
- Bassa statistica di raccolta del segnale (es. basso dwell time),
- Amplificazioni eccessive del segnale durante l'elaborazione elettronica.

Un difetto comune nei microscopi elettronici è la presenza di disturbi puntuali dovuti all'instabilità della catena di acquisizione (l'immagine è costruita mediante una scansione di x,y segnali raccolti per un certo dwell-time, possono comparire pixel con
luminosità eccessivamente alta o bassa). <br>
Stesso difetto può manifestarsi su pellicole vecchie o nell'acquisizione di immagini con
sensori CCD con alcuni componenti difettati. <br>

Per risolvere il problema nel caso del SEM, in fase di acquisizione dell'immagine si può intervenire con acquisizioni ripetute della stessa area in cui segnali vengono integrati o mediati. <br>
Nelle fotocamere si può aumentare il tempo di esposizione. <br>
In entrambe i casi tuttavia si rischia di introdurre un nuovo difetto causato dal drift dell'immagine. <br>
Se l'immagine è già disponibile la procedura più semplice e comune è effettuare una media del valore dei grigi rispetto ai pixel vicini: neighborhood averaging:
- Consiste nel mediare la luminosità di una regione limitata di pixel confinanti, sommando le singole intensità e dividendo il totale per il numero di pixel (filtri Mean).
- Di contro, se non correttamente impiegato, la risoluzione laterale può essere compromessa a discapito dei particolari più piccoli (blurring o sfocatura).
- Si tratta di filtri lineari nel dominio dello spazio che non causano perdita di informazioni.

La regione di pixel in genere è quadrata il cui lato può avere dimensione variabile secondo la relazione 2m+1 (ossia solo numeri dispari): 3x3, 5x5, 7x7. <br>
La dimensione del kernel e i pesi vanno scelti in base alla dimensione degli elementi di interesse nell'immagine.
![](meanex.png>)

![](kernelex.png)

L'utilizzo del kernel coinvolge anche operazioni non lineari le cui procedure sono note come «neighborhood ranking» che può comportare una perdita parziale dei dati originali.
- Consiste nell'ordinare con un certo criterio l'intensità dei pixel adiacenti.
- II più noto è il filtro «Median» dove l'intensità del pixel centrale sarà dato dal valore mediano di quelli adiacenti.
- Rispetto ai filtri lineari (Mean) il kernel «Median» possiede geometrie diverse.

II filtro Median è particolarmente adatto a ridurre rumori detti di 'Shot noise' che coinvolgono il singolo pixel (corrotto o mancante). <br>
Si induce comunque una leggera distorsione o degrado dell'immagine. <br>
![](shotnoise.png)

Nella distribuzione statistica dell'intensità luminosa di un gruppo di pixel adiacenti a quello da modificare è possibile utilizzare oltre alla media e alla mediana, la moda (filtri Mode). <br>
In questo caso la dimensione del kernel deve essere maggiore di 3x3 altrimenti la moda sarebbe scarsamente rappresentativa.

Un altro elemento di disturbo può essere l'illuminazione non uniforme che genera gradienti di luminosità nell'immagine, generati anche in trasmissione nel caso di campioni a spessore non omogeneo. <br>
Si può in genere minimizzare agendo sul setup dello strumento impiegando una illuminazione anulare (ottico), corretto allineamento del fascio (EM), ecc. <br>
In fase di post-processing si utilizza la tecnica del «Background subtraction». <br>
Ove possibile è utile acquisire una immagine dello sfondo e poi sottrarla all'originale eseguendo operazioni tra pixel spazialmente corrispondenti. 

Un'altra famiglia di filtri sono i filtri per l'aumento della nitidezza
Si tratta di filtri che incrementano il contrasto dei bordi distanziando il valore dei toni intermedi (es. toni di grigio) (filtri «Sharpening»)

## Image enhancement
Ha l'obiettivo di evidenziare una parte dell'immagine oppure solo alcune classi tra quelle utilizzate durante la quantizzazione. <br>
Nel dominio dello spazio, si applicano regole che coinvolgono il singolo pixel e/o quelli confinanti. <br>
L'applicazione più comune è la massimizzazione del contrasto (non comporta una perdita delle informazioni). <br>

I toni di grigio di una immagine vengono rappresentati con un istogramma che riporta il numero. <br>
di pixel rilevati per ciascun valore di tono di grigio. <br>
Esempio di istogrammi di una immagine troppo scura, troppo chiara e ben bilanciata.
![](<Screenshot 2023-07-03 105427.png>)

La procedura per la massimizzazione del contrasto consiste nell'assegnare il tono nero al pixel più scuro rilevato e il tono bianco a quello più luminoso. <br>
Gli altri toni di grigio intermedi vengono linearmente interpolati. <br>
Importante è non avere problemi di 'Shot noise' che renderebbero vana la procedura (in tal caso è consigliabile prima applicare un filtro Median)

In generale la manipolazione dei toni di grigio di ciascun pixel avviene tramite una funzione di trasferimento che dipende dal tono stesso ma non dal valore dei pixel confinanti (come nella convoluzione). <br>
Tale funzione può essere lineare e non lineare al fine di enfatizzare un range di toni e appiattirne altri. <br>
Utilizzando funzioni di trasferimento con pendenza negativa l'immagine può essere invertita, come il negativo di una pellicola. <br>
![Alt text](<Screenshot 2023-07-03 140337.png>)

Funzioni i trasferimento logaritmica e radice: comprimono la luminosità per i toni più chiari e la accentuano per i toni scuri. <br>
Funzioni i trasferimento esponenziale e quadratica: comprimono la luminosità per i toni più scusi e la accentuano per i toni chiari.
![Alt text](<Screenshot 2023-07-03 140521.png>)

## Equalizzazione dell'istogramma <br>
Esistono tecnche avanzate di "Histogram mode/ing" che permettono di modificare in modo sofisticato il range dinamico e il contrasto dell'immagine in modo che l'istogramma dell'immagine elaborata abbia specifiche caratteristiche. Gli operatori di Histogram mode/ing possono impiegare funzioni di trasferimento non-lineari e anche non monotone. <br>
L'equalizzazione dell'istogramma impiega una funzione di trasferimento monotona non lineare che ridefinisce i valori di intensità dell'immagine in modo che l'immagine elaborata contenga una distribuzione uniforme di intensità (istogramma piatto). <br>

Trasformata di Fourier (FFT) <br>
Qualsiasi funzione periodica f(t) può essere scomposta nella somma di diverse
funzioni seno - coseno a frequenza crescente (serie di Fourier).
- 1-D FT: analisi di segnali (1-D)
- 2-D FT: analisi di immagini (2-D)

![Alt text](<Screenshot 2023-07-03 141047.png>)

Eliminazione di una frequenz indesiderata <br>
![Alt text](<Screenshot 2023-07-03 141047-1.png>)

Esempio di trasformate di Fourier per alcune immagini con elevata periodicità. <br>
![Alt text](<Screenshot 2023-07-03 141556.png>)

Quando le immagini presentino informazioni periodiche da esaltare o eliminare, è utile lavorare nel dominio delle frequenze. <br>
Sono necessari i seguenti passaggi:
- Trasformazione nel dominio della frequenzao
- Filtraggio nel nuovo dominio
- Trasformazione inversa per tornare nel dominio dello spazio

![Alt text](<Screenshot 2023-07-03 141855.png>)

Le basse frequenze corrispondono a graduali variazioni della luminosità dei pixel (superfici continue). <br>
Le alte frequenze corrispondono repentine variazioni dell'intensità dei pixel (spigoli, rumore, ecc.).
![Alt text](<Screenshot 2023-07-03 142009.png>)

Applicazione della FFT per la rimozione del rumore: eliminazione del corrispondente spot luminoso nell'immagine della trasformata
![Alt text](<Screenshot 2023-07-03 142213.png>)
![Alt text](<Screenshot 2023-07-03 142447.png>)
![Alt text](<Screenshot 2023-07-03 142553.png>)

## Segmentazione
Procedura ampiamente utilizzata per isolare nell'immagine solo le porzioni che contengono l'informazione desiderata (generalmente linee, curve, aree) <br>
II processo consiste nel classificare i pixel che hanno caratteristiche comuni (colore, intensità, texture). <br>
Le regioni individuate avranno quindi almeno una di tali caratteristiche differenti. <br>
![Alt text](<Screenshot 2023-07-03 143017.png>)

Esistono diverse metodologie di segmentazione che si basano sulla elaborazione dell'istogramma dei toni di grigio secondo la logica di un 'descrittore':
- Classificazione dei pixel sulla base dei valori di intensità luminosa e applicazione di una soglia globale (**Thresholding e Binarizzazione**)
- Riconoscimento dei contorni (**edge detection**): si identificano le linee dove la luminosità cambia repentinamente.
- Raggruppamento (**clustering**): identifica aree di pixel aventi stesse caratteristiche in modo matematico (distanza euclidea e di colore, ecc.).
- Accrescimento delle aree (**Region growing**): parte da piccole aree di pixel di una regione dell'immagine e le accresce fino a coprire l'intera regione.

### Thresholding e Binarizzazione
- Consiste nel selezionare dall'immagine solo i pixel che hanno una luminosità inclasa in un range di toni di grigio prescelto.
- I pixel selezionati verranno convertiti con una luminosità a profondità binaria: ossia bianchi o neri.
- La scelta del range viene effettuata manualmente osservando l'immagine e agendo con software dedicati sull'istogramma dell'immagine.

La binarizzazione raramente produce subito risultati soddisfacenti a causa dell'illuminazione non uniforme o altre sorgenti di rumore.
![Alt text](<Screenshot 2023-07-03 143931.png>)

II miglioramento delle immagini binarizzate viene effettuato processandole con 2 famiglie di filtri:
- Filtri booleani (comparazione e combinazione di più immagini)
- Filtri morfologici (modifica individuale dei pixel)
Combinare più immagini è utile nella manipolazione delle immagini SEM e delle mappe EDS dove ogni immagine contiene parte dell'informazione.

I filtri booleani sono operazioni logiche che combinano due immagini binarie (A e B) per produrre una terza immagine binaria (C). <br>
![Alt text](<Screenshot 2023-07-03 144156.png>)

Filtri Morfologici
I filtri morfologici sono quelli più utilizzati tra cui si evidenziano:
- Erosion -> Opening
- Dilation -> Closing

Sono operatori che coinvolgono i pixel confinanti ma, essendo l'immagine binarizzata, le operazioni sono semplici (i pesi sono solo 1 o 0). <br>
Si ottiene l'aggiunta o l'eliminazione di pixel bianchi in base alla densità di quelli circondanti il pixel in oggetto, secondo determinate regole. <br>

**Erosion** <br>
La procedura rimuove i pixel bianchi isolati rispetto al numero di quelli bianchi che lo circondano, per eliminare i dettagli indesiderati a seguito della binarizzazione. <br>
**Dilation** <br>
Procedura inversa all'Erosion. Pixel bianchi vengono aggiunti attorno alle aree ad alta densità di pixel bianchi. <br>

Applicazione dei filtri Erosion e Dilation
- Isolamento delle sole fasi grigie tramite impiego in sequenza dei 2 filtri morfologici su una lega.

![Alt text](<Screenshot 2023-07-03 144801.png>)

Filtro Opening: sequenza i operazioni ripetute di Erosion e Dilation al fine di separare i particolari di interesse:

![Alt text](<Screenshot 2023-07-03 144940.png>)

Filtro Closing: sequenza di operazioni ripetute di Erosion e Dilation al fine di unire i particolari di interesse. <br>
es. fibre in cross-section con criccature.

![Alt text](<Screenshot 2023-07-03 145154.png>)

## Premesse all'analisi quantitativa delle immagini
Significatività e affidabilità delle analisi. <br>

Per ottenere immagini che contengano informazioni misurabili è essenziale che il campione sia rappresentativo dell'universo osservato e che la catena di acquisizione sia in grado di raccogliere il massimo numero di informazioni necessarie (e il minimo numero di informazioni non necessarie o sbagliate). <br>

I software per l'analisi di immagine possono generare nuove informazioni, ma il livello di affidabilità delle informazioni create è direttamente dipendente dalla conoscenza del fenomeno reale che si sta investigando, e dalla qualità e quantità delle informazioni «reali» contenute nell'immagine elaborata. <br>

Questi sono elementi imprescindibili per tentare successivamente la costruzione di conoscenza per interpolazione, estrapolazione con la formulazione di modelli descrittivi e/o predittivi.

## Misura delle grandezze 
La prima ase consiste ne a ca i razione imensionae e immagine. <br>

E' necessario cioè riferire l'immagine ad un sistema di riferimento opportuno: dimensioni, geolocalizzazione, piano di proiezione, sistema di proiezione. <br>

Trascurando le trasformazioni più complesse (normalizzazione, ortonormalizzazione , planarizzazione , passaggio a coordinate polari...) il primo elemento fondamentale è quello di stabilire la scala dimensionale, e cioè i versori degli assi e il loro valore scalare rispetto ad una grandezza di riferimento.

Molti software di acquisizione eseguono automaticamente tale operazione, laddove la catena di misura è fissa e il software è in dotazione con la catena di acquisizione.

Altre volte è necessario calibrare la catena di misura.

E' comunque buona norma verificare sempre la corretta calibrazione, soprattutto laddove sia richiesto un elevato livello di precisione e accuratezza.

Anche nei casi più semplici (rappresentazione cartesiana) è opportuno eseguire la calibrazione comunque per entrambi gli assi.

In alcune circostanze e laddove si è consapevoli di errori sistematici (i.e. aberrazioni sferiche delle lenti, oppure sistemi di acquisizione con fattori di ingrandimento non costanti su tutto il campo di osservazione) è indispensabile trovare la funzione di trasferimento per calibrare l'immagine, altrimenti segmenti di uguali dimensioni in zone diverse dell'immagine possono fornire dati falsati.

Un errore classico è quello di considerare il piano immagine come una proiezione piana parallela al piano oggetto.

Questo può portare a gravi errori nel caso di sezioni inclinate rispetto all'asse ottico di acquisizione dell'immagine, fortunatamente sistematico e quindi facilmente rettificabile.

Procedura piu elementare di calibrazione per un ottico:
1. Viene acquisita l'immagine di uno standard (oggetto graduato)
2. Si estrapola la dimensione del singolo pixel (gm/ pix , spesso rettangolare!)
3. Tale dimensione (in x e in y) viene utilizzata per calibrare le immagini che verranno prodotte da quella determinata catena di misura (i.e. con lo stesso sistema ottico).

Sull'immagine calibrata si possono effettuare tutte le misure di interesse 

L'immagine calibrata si riconosce perché porta sovraimpressa la dima o barra dimensionale.

Attenzione va posta nell'inserire una dima bidimensionale su un'immagine prospettica o con grande tridimensionalità.

Le misure prese sulle immagini saranno una parte di tutti i valori misurabili in quel campo di osservazione, che è una parte della superficie osservabile del campione, che a sua volta è una porzione del materiale che stiamo studiando. <br>

Non dobbiamo mai dimenticare che a questi valori va sempre data una significatività statistica.

E' prassi classificare i dati ottenuti e generare dei grafici di dispersione che meglio descrivano il comportamento statistico delle grandezze osservate, passando ove il caso a test statistici di significatività (t di student , chi quadro, ecc). <br>

Quanto più numerosi sono i dati e le classi, tanto più il grafico approssima una curva continua, la cosiddetta " curva di frequenza".

![Alt text](<Screenshot 2023-07-03 150430.png>)

![Alt text](<Screenshot 2023-07-03 150525.png>)

![Alt text](image.png)


# ImageJ
![Alt text](image-1.png)
![Alt text](image-2.png)
![Alt text](image-4.png)

Image > Type seleziona i bit per pixel dell'immagine (8, 16, 32 bit) <br>

Analyze: per estrarre l'informazione di interesse dall'immagine. <br>

![Alt text](image-5.png)
Analyze > Histogram: genera un istogramma dell'immagine. Applicando Log reisco ad amplificare i valori più bassi. <br>
Se l'istogramma va a 0 per un buon range di valori, significa che l'immagine non sfrutta tutto il range di valori disponibili. <br>
Enhance contrast: settando 0% e normalizzando l'immagine si schiarisce leggermente e l'istogramma si distribuisce meglio su tutti i livelli. I valori intermedi sono interpolati. <br>
![Alt text](image-6.png)

![Alt text](image-7.png)

![Alt text](image-8.png)
L'asse x dell'istogramma mostra il numero di bit del convertitore analogico digitale

![Alt text](image-9.png)
Mettendo 0%, in questo caso la normalizzazione non è servita
Mettendo 5% e normalizzando l'immagine si schiarisce leggermente e l'istogramma si distribuisce meglio su tutti i livelli. I valori intermedi sono interpolati. <br>
Abbiamo acquisito informazione perché abbiamo scoperto una parte dell'immagine che non era visibile prima ma abbiamo perso in definizione. <br>

![Alt text](image-10.png)
L'equalizzazione crea una funzione di trasferimento monotona non lineare ottimizzata per questa specifica immagine in cui si cerca di avere una distribuzione uniforme dei livelli di grigio. <br>
Questo permette di creare contrasto dove non c'è e non esagerare dove c'è già. <br> 
Ad esempio riusciamo a distinguere il grigio anche all'interno della galassia. <br>

---
Image > Adjust > Brightness/Contrast: permette di regolare il contrasto e la luminosità dell'immagine. <br>
![Alt text](image-11.png)
La retta indica le attuali impostazioni della funzione di trasferimento che di base è un'identità. <br>
La Brightness tende ad aggiungere un offset comune tutti i livelli di grigio (+Brightness -> +Offset, -Brightness -> -Offset). <br>
Il Contrast tende ad aumentare la pendenza della funzione di trasferimento (+Contrast -> +Pendenza, -Contrast -> -Pendenza). <br>

---
Aumentando il minimo e riducendo il massimo si aumenta il contrasto senza cambiare la pendenza della retta -> senza perdere informazione. <br>
![Alt text](image-12.png)

## RGB images
1/3 mostra il numero del canale (Rosso). <br>
512x512 shows the image size. <br>
8-bit shows the color depth of each color channel. <br>
768k shows the image size in bytes. <br>
The bottom bar shows the three color channels. <br>
White = R + G + B. <br>
![Alt text](image-13.png)
Image > Type > 8-bit: converts the image in grayscale. <br>
![Alt text](image-14.png)

The image has a red fluorescence which is captured with a RGB camera, then the green and blue channels are empty. <br> 
The red channel can be easily converted into a grayscale image by selecting Image > Type > 8-bit. <br>
![Alt text](image-15.png)
We can directly obtain the grayscale image by selecting Image > Color > Grayscale even if the image is RGB. <br> 
The resulting image is much more dark than the previous one since the coordinates of each pixel are averaged by 1/3 red + 1/3 green + 1/3 blue. In this case green and blue are black so the resulting image is much more dark. <br>
We can adjust the brightness and contrast of the image by selecting Image > Adjust > Brightness/Contrast. <br>
Its histogram is concentrated in the low values of the grayscale. <br>
![Alt text](image-16.png)
![Alt text](image-17.png)
The left histogram doesn't cover the whole range of the grayscale since we have only stretched the histogram by adjusting the brightness and contrast. It has a lot of zeros since the values are interpolated only where there are values, if there are zeros they remain zeros. <br>
The right histogram covers the whole range of the grayscale and has much more less zeros since the values are interpolated everywhere. <br>
Converting an RGB into a 8-bit grayscale image generates a loss of information.
![Alt text](image-18.png)

## Look up table
Image > Color > Show LUT
The look up table only converts the image visualization, not the pixel values. <br>
The graph shows the correlation between the bit 
![Alt text](image-19.png)
![Alt text](image-20.png)

The histogram has great peaks at low values of the grayscale while the image is not so dark. <br>
This is due to the fact that the image is saved as an inverted LUT. The histogram was correct but the image was inverted. <br>
![Alt text](image-21.png)
![Alt text](image-22.png)

EditLUT allows to modify how a color should be displayed
![Alt text](image-23.png)
![Alt text](image-24.png)
![Alt text](image-25.png)

To make some measurements, the image has to be calibrated. <br>
![Alt text](image-26.png)

## Segmentazione
Mettiamo a 1 o a 0 i pixel in base al valore di soglia. <br>
Image > Adjust > Threshold: permette di selezionare il valore di soglia. <br>
![Alt text](image-27.png)

## Conteggio particelle
![Alt text](image-28.png)
![Alt text](image-29.png)
![Alt text](image-30.png)

By making the ratio between area of different gray levels we can get the percentage of the colors in an area. <br>
![Alt text](image-31.png)

## Erosion and dilation
![Alt text](image-32.png)
![Alt text](image-33.png)
![Alt text](image-34.png)

## Segmentazione immagini a colori
![Alt text](image-35.png)
![Alt text](image-36.png)
![Alt text](image-37.png)

## Correzione shot noise
![Alt text](image-38.png)
Process > Smooth non è molto efficace. <br>
Process > Filters > Mean con raggio 2 non è molto efficace. <br>
Process > Filters > Mean con raggio 5 è efficace ma c'è molto blurring tra le zone bianche e nere. <br>
Process > Filters > Median con raggio è efficace e non c'è blurring tra le zone bianche e nere. Questo filtro non è lineare .<br>

## Filtraggio in frequenza
Il grafico mostra uno sfondo non uniforme, tende lentamente al bianco da sinistra verso destra. <br>
![Alt text](image-39.png)
Usando un filtro passa basso si ottiene un'immagine più uniforme. <br>
Mettendo 200 pixels in "filter large structures down to" filtriamo tutte le strutture più piccole di 200 pixels. <br>
![Alt text](image-40.png)

## FFT 
![Alt text](image-41.png)
![Alt text](image-42.png)
![Alt text](image-43.png)
![Alt text](image-44.png)
![Alt text](image-45.png)

![Alt text](image-46.png)
![Alt text](image-47.png)
![Alt text](image-48.png)
![Alt text](image-49.png)

## Edge detection
![Alt text](image-50.png)
![Alt text](image-51.png)
Il watershed applicato a immagini binarizzate funziona solo per maschere convesse
![Alt text](image-52.png)
![Alt text](image-53.png)
![Alt text](image-54.png)