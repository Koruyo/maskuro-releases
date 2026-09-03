# Modifiche

Ciò che cambia da versione a versione – descritto dal punto di vista
dell'applicazione, non dei suoi meccanismi interni. Chi vuole sapere *di
cosa* è fatta trova la risposta in [LIZENZEN.md](LIZENZEN.md); qui sta
scritto cosa cambia per il lavoro con essa.

La numerazione segue la convenzione consueta: il **primo** numero cambia
quando qualcosa non funziona più come prima, il **secondo** per nuove
funzionalità, il **terzo** per correzioni di errori.

---

## 0.10.50-alpha.20260903 – 3 settembre 2026

- I loghi aziendali ricorrenti nei PDF vengono bonificati in modo coerente,
  anche quando il riconoscimento testo legge la scritta in modo diverso su
  una pagina o tralascia del tutto il simbolo rotondo. Una deselezione
  esplicita nell'anteprima resta vincolante e non può essere annullata da
  nessun passaggio successivo.
- I prezzi senza valuta in tabelle scansionate vengono ora completamente
  oscurati anche quando intestazione di tabella e valori si trovano in
  immagini PDF diverse e sovrapposte. Quantità, ore, pesi e percentuali
  restano; numeri molto distanti tra loro non vengono più uniti per errore
  in un importo.
- La ricerca di firme rileva ora anche scritte blu deboli ma documentate e
  sigle di firma rosse strette. Diagrammi punteggiati, curve di misura,
  timbri, loghi e ampi contrassegni di elaborazione rossi restano esclusi
  da questo passaggio mirato.
- Gli oscuramenti in immagini PDF ruotate, specchiate, deformate o
  ritagliate colpiscono ora il poligono immagine effettivo. Allo stesso
  tempo, ruoli tecnici in voci di prestazione, dati tecnici di veicoli e
  pneumatici nonché „compensazione" tecnica vengono delimitati in modo più
  stretto contro falsi rilevamenti; ruoli di contatto esplicitamente
  etichettati e numeri di telefono restano protetti.
- Il controllo visivo prima del salvataggio di un PDF non blocca più la
  finestra: nei documenti grandi con molti punti di rilevamento restava
  finora per diversi secondi senza risposta; ora un'indicazione mostra che
  è in corso il controllo, e la finestra continua a disegnarsi.
- Il recupero di un valore da un'immagine nell'editor di correzione legge
  ogni immagine originale una sola volta tramite riconoscimento testo;
  finora girava di nuovo a ogni ulteriore recupero per le stesse immagini.
- Il caricamento del livello Alto e del modello firme richiede ora quasi
  nessuna memoria di lavoro in più: il pacchetto da 596 MB veniva finora
  tenuto completamente in memoria, verificato e lì decompresso – oltre un
  gigabyte di picco nel programma in esecuzione, sui computer con 8 GB il
  momento in cui tutto iniziava a bloccarsi. Ora fluisce a blocchi sul
  disco e lì viene verificato e decompresso.
- La ricerca nell'editor di correzione non blocca più i PDF grandi: la
  prima lettera nel campo di ricerca leggeva finora tutte le pagine in una
  volta – con 200 pagine la finestra restava ferma due secondi, e dopo
  ogni oscuramento di nuovo. Le pagine vengono ora lette a piccoli
  blocchi; fino ad allora nel contatore compare „In lettura …", il
  risultato è lo stesso.
- Le pagine PDF rasterizzate – dopo un riconoscimento testo o quando un
  testo non poteva essere rimosso in modo pulito – vengono salvate
  notevolmente più piccole e senza perdita di immagine: invece di essere
  sempre in JPEG, ogni pagina viene codificata anche senza perdita, e la
  versione più piccola finisce nel file. Una scansione bonificata si
  riduce così da 248 a 48 KB, il documento di esercizio con riconoscimento
  testo da 913 a 702 KB; il testo resta nitido.
- I modelli caricati successivamente (livello Alto, firme, volti, secondo
  riconoscimento testo) vengono rilasciati dalla memoria di lavoro dopo
  dieci minuti senza bonifica. Finora restavano caricati fino alla fine
  del programma – chi aveva usato una volta una ricerca di firme e il
  livello Alto tratteneva stabilmente oltre due gigabyte. L'esecuzione
  successiva li ricarica in uno o due secondi; la riga di stato lo
  segnala.
- PowerPoint: i nomi generici dei layout di diapositiva e dei modelli di
  diapositiva („Vuoto", „Diapositiva del titolo") non vengono più
  sostituiti come dato. „Vuoto" è anche un luogo ed era erroneamente
  oscurato in ogni presentazione tedesca e inglese; vengono bonificati
  ora solo i nomi assegnati manualmente delle diapositive stesse.
- Nei PDF, la levigatura di riga non trascina più l'inizio della riga
  successiva in un rilevamento: il numero del punto elenco successivo
  dietro una data valeva come numero di telefono, un'intestazione di
  campo come „Codice identificativo" o „Numero d'ordine" dietro un numero
  come codice postale con località, e la riga della località sotto
  l'indirizzo duplicava la località. Il rilevamento corretto e più corto
  veniva così soppiantato. Su 132 PDF del corpus restano, dei 24
  rilevamenti aggiuntivi di levigatura, i due veri; nel corpus pratico i
  falsi allarmi scendono da 29 a 21 con la stessa quota di rilevamento.
- „Cerca e oscura cartella PDF" nell'editor di correzione non blocca più
  la finestra: l'esecuzione lavora in background, avanzamento e pulsante
  Annulla rispondono, e menu o schede non possono più essere usati in
  mezzo a un file completato solo a metà.
- Le pagine scansionate con punti di rilevamento vengono ora riscritte
  solo una volta durante l'oscuramento invece di due: finora il programma
  riempiva i riquadri dei punti di rilevamento e quelli delle motivazioni
  in due passaggi, e il secondo comprimeva un'ulteriore volta l'immagine
  della scansione appena salvata. Questo risparmia tempo su scansioni
  grandi e una perdita di qualità nell'immagine.
- Scorrimento, zoom e le miniature nell'editor di correzione rispondono
  più velocemente: ogni pagina renderizzata passava finora attraverso una
  compressione PNG e subito di nuovo indietro, solo per essere mostrata –
  su schermi ad alta risoluzione circa un decimo di secondo per pagina.
  L'immagine ora arriva direttamente, pixel per pixel identica.
- Il controllo visivo prima del salvataggio di un PDF („prova di output")
  è circa tre volte più veloce, a parità di risultato.
- La finestra principale appare ancora circa un quarto di secondo prima:
  il controllo se il riconoscimento testo è pronto su questo computer
  girava durante la costruzione della finestra – sul Mac con tanto di
  richiesta di prova al riconoscimento di sistema – e la pagina delle
  impostazioni dei componenti aggiuntivi interrogava per questo lo stato
  di tutte le 48 lingue. Entrambe le cose ora avvengono in background,
  rispettivamente solo quando l'elenco lingue viene davvero aperto; fino
  ad allora compare „Verifica del riconoscimento testo in corso …".
- Dopo una ricerca di firme, il programma occupa circa 300 MB in meno di
  memoria di lavoro: il modello di riconoscimento restava finora doppio in
  memoria – una volta per verificarne l'autenticità, una volta per
  calcolare. Continua a essere verificato, solo senza la seconda copia.
- Il riconoscimento testo nei PDF è diventato sensibilmente più veloce:
  per ogni intestazione di campo di una pagina („Data di nascita:",
  „Codice fiscale:") veniva finora inviata al riconoscimento una prova
  propria per ogni tipo di dato – su ogni pagina di nuovo, anche se la
  stessa intestazione era già comparsa dieci pagine prima. La risposta
  viene ora memorizzata; un capitolato di due pagine poneva così 324
  domande, ora solo quelle diverse. I rilevamenti sono gli stessi.
- Le tabelle grandi vengono di nuovo bonificate in secondi invece che in
  minuti: nel funzionamento anonimizzante – l'impostazione predefinita –
  il confronto dei valori già noti con ogni ulteriore cella diventava più
  lento, perché una cache veniva scartata e ricostruita a ogni
  rilevamento. 5.000 celle richiedevano per questo circa 18 secondi, ora
  mezzo secondo; il risultato è identico carattere per carattere.
- La finestra principale appare ancora una volta sensibilmente più
  veloce: l'elenco paesi delle impostazioni tirava in primo piano, durante
  la costruzione della finestra, l'intera libreria di riconoscimento –
  circa 0,7 secondi sul Mac, su Windows corrispondentemente di più –
  sebbene per questo servano solo i nomi dei paesi. L'elenco proviene ora
  da un catalogo leggero; la libreria si carica come previsto in
  background, mentre la finestra è già pronta. Questo vale anche dopo ogni
  cambio di lingua o aspetto che riavvia il programma.
- Il laboratorio documenti passa ora completamente attraverso i
  contenitori PDF, DOCX e ODT intestazioni di campo tagliate, ombre di
  valore locali e forti ritagli di scansione. La matrice comprende 680
  file di 40 famiglie di documenti e 17 assi contenitore. Maskuro rimuove,
  nei nuovi profili base e caratteristica nonché in quelli completi, tutti
  i dati attesi, senza falso allarme misurato, valore di conservazione
  danneggiato o interruzione.

- Le scansioni usate più volte vengono ora verificate e bonificate su ogni
  posizionamento visibile: il laboratorio documenti condivide lo stesso
  oggetto immagine su pagine, dimensioni e orientamenti diversi nel PDF e
  fa riferimento più volte alla stessa parte di immagine in DOCX e ODT. I
  nomi tecnici di cornice ODT come „Scansione modulo piccola orizzontale"
  non valgono più come persona; nomi e luoghi liberi con inizio simile
  restano protetti. Un'ipotesi generica di modulo dell'esecuzione finale
  sulla pagina PDF non può più generare, su un'area immagine già letta
  indipendentemente, un grande falso rilevamento di indirizzo. I 120 nuovi
  contenitori raggiungono nel profilo base e caratteristica tutti gli 813
  rispettivamente 840 dati attesi senza falso allarme, violazione di
  conservazione o interruzione; la verifica caratteristica completa su
  800 file conferma 5.600/5.600.

- Il laboratorio OCR tedesco comprende ora 560 scansioni di 40 famiglie di
  documenti. Nuove varianti tagliano i margini di intestazione di campo e
  di pagina o pongono un'ombra direttamente su un valore. Maskuro protegge
  in questo caso anche nomi, indirizzi, date di nascita, codici medici e
  numeri identificativi etichettati con etichettatura parzialmente
  danneggiata. Allo stesso tempo, resti di campi modulo, intestazioni
  ufficiali nonché termini giuridici e informativi generici non vengono
  più sostituiti come persone o luoghi. I profili base e caratteristica
  completi raggiungono 3.794/3.794 rispettivamente 3.920/3.920 dati
  attesi senza falso allarme misurato o interruzione.

- La selezione automatica delle immagini PDF non rimuove più foto prodotto
  di grandi dimensioni, etichette energetiche e serie di ritratti solo
  perché iniziano nel margine superiore della pagina. Vere immagini piatte
  di intestazione/piè di pagina e intestazioni che partono dal bordo del
  foglio continuano a cadere. Negli elenchi del personale, i nomi vengono
  ora riconosciuti anche da voci ripetute strutturalmente quando il titolo
  visibile del documento è disponibile solo come immagine. Il
  riconoscimento non è più ritagliato su due parole di ruolo concrete e
  la sigla „DW": da uno a quattro ruoli con a capo nonché „Interno",
  „Numero interno", „Est." e „Extension" vengono dedotti dalla forma
  comune. Ruoli e intestazioni di sezione restano, anche se il modello
  linguistico dopo la risoluzione delle sovrapposizioni lascia solo un
  aggettivo di ruolo. Griglie di ruolo orizzontali non valgono più per
  errore come colonne di nomi. Se l'OCR di pagina incolla più schede in
  un'unica parola in maiuscolo interno estremamente larga, un confronto
  visivo locale stretto separa i veri riquadri di parola; così non resta
  né un nome isolato né un'ampia barra errata. I loghi aziendali su più
  righe ripetuti vengono oscurati sulla base di un modello pixel identico
  già confermato, anche su pagine senza testo OCR utilizzabile e con fino
  a due pixel di scostamento di posizione; letture secondarie OCR locali
  più brevi non possono contemporaneamente aggiungere un'area di
  intestazione più grande come nome inventato. I numeri di pagina davanti
  a un'intestazione aziendale non appartengono più al nome
  dell'organizzazione, i veri nomi di marca che iniziano con un numero
  restano protetti. Diverse parole misurate di prodotto, settore e modulo
  non vengono più proposte come persone.

- La ricerca di firme nei PDF gira ora solo dopo la bonifica immagine OCR,
  visita anche pagine senza un normale rilevamento testuale e ricalcola
  correttamente i riquadri di rilevamento delle pagine ruotate nello
  spazio del documento. Foto prodotto dense non vengono più oscurate come
  firma. Sopra campi firma esplicitamente etichettati, un ripiego a
  tratto stretto chiude piccole lacune del modello; righe vuote con data
  prestampata non lo attivano. Le scansioni pure con soli rilevamenti
  OCR/firma non si interrompono più in questa fase a causa di un
  oscuratore immagine caricato solo nel ramo testo.

- Molti documenti aperti contemporaneamente restano distinguibili
  nell'editor di correzione: le schede non si riducono più a un semplice
  segno di omissione, e un pulsante elenco a destra mostra tutti i nomi
  file completi uno sotto l'altro. Le schede si possono riordinare
  trascinandole e rimuovere con la loro croce dallo stesso elenco come
  nella finestra principale; il lavoro non salvato viene comunque
  chiarito prima. Un clic destro offre inoltre „Chiudi", „Chiudi altre
  schede" e „Chiudi schede a destra".

- Un blocco Windows momentaneo da parte di antivirus o indice di ricerca
  non fa più fallire con „Accesso negato" la cartella del modello
  linguistico o del dizionario completamente caricata al momento
  dell'inserimento finale. Maskuro ora riprova questo ultimo cambio di
  cartella per un breve periodo.

- Il laboratorio documenti tedesco verifica ora i contenitori anche con
  rotazione di pagina PDF variabile, immagini PDF ruotate
  indipendentemente nonché immagini di tabella ridimensionate e ritagliate
  in DOCX e ODT. I valori di campo in immagini visibilmente ruotate
  vengono di nuovo riconosciuti completamente, identificatori di colonna
  tecnici non vengono più sostituiti come luoghi e nomi con cognome comune
  non vengono più scomposti dal controllo di coerenza in doppi
  rilevamenti parziali. La matrice raddoppiata a 320 file raggiunge, con
  riconoscimento di data, denaro e medico attivato, 2.240/2.240 dati
  attesi senza falso allarme misurato o interruzione.

- I PDF immagine a più pagine, i PDF misti testo/immagine e le scansioni
  incorporate in DOCX o ODT vengono ora verificati in un laboratorio
  proprio di 160 file su tutte le 40 famiglie di documenti tedesche. I
  nomi tecnici di cornice ODT e i codici dispositivo etichettati non
  vengono più sostituiti come luoghi; nomi, luoghi e indirizzi reali nelle
  stesse strutture restano protetti. Con riconoscimento medico o
  finanziario attivato vengono inoltre rimossi completamente un dosaggio
  direttamente successivo o un intervallo di pagamento. Le esecuzioni
  contenitore, base testo, caratteristica testo e caratteristica OCR
  raggiungono insieme i rispettivi stati completi senza falso allarme
  misurato o interruzione.

- Il controllo di sicurezza prima del salvataggio mostra ora i punti PDF
  rilevanti come elenco selezionabile singolarmente. „Verifica
  nell'editor" apre esattamente la pagina scelta e marca l'area;
  rilevamenti parziali sovrapposti nello stesso punto compaiono ora una
  sola volta. I nuovi testi di interfaccia sono presenti completamente in
  tutte le 17 lingue di interfaccia tradotte.

- I file Markdown mantengono la loro sintassi di collegamento,
  evidenziazione e nota a piè di pagina durante la sostituzione. Maskuro
  legge per questo una versione di lunghezza identica in caratteri senza
  marcatori Markdown; trattini bassi in indirizzi email, asterischi di
  calcolo e normali collegamenti senza dato personale restano invariati.

- Più voci scritte a mano sulla stessa pagina PDF vengono ora cercate in
  fino a tre passaggi. I tratti già trovati vengono nascosti solo
  nell'immagine di lavoro, in modo che non soppiantino più firme più
  deboli; su pagine ruotate le aree di oscuramento finiscono di nuovo nel
  punto di rilevamento visibile. I riempimenti immagine di fasi di
  sicurezza precedenti vengono mantenuti nella successiva riscrittura.

- „Ripristina tutte le impostazioni" comprende ora anche „Testo nelle
  immagini". Se il componente OCR non è disponibile, l'interruttore resta
  tecnicamente spento, senza essere erroneamente marcato come divergente
  dallo stato di consegna.

- I grandi frammenti immagine nel margine superiore della pagina non
  valgono più come intestazione solo per la loro posizione. Restano così
  in particolare descrizioni di articoli basate su immagini e contenuti
  di tabella. I nuovi rilevamenti email e modulo precisi per tipo non
  vengono inoltre più filtrati dal controllo visivo finale nemmeno su
  un'area immagine già verificata.

- Le righe tecniche di posizione e articolo nelle offerte di climatizzazione
  ed elettrotecnica vengono distinte in modo più stretto da persone,
  luoghi e organizzazioni. Ciò riguarda tra l'altro tipi di cavo,
  alimentazione AC, numeri di posizione nonché codici prodotto in
  maiuscolo; nomi e indirizzi reali restano protetti.

- Il controllo di veri PDF bonificati non confonde più componenti di
  prezzo come `1 699,59` con numeri di telefono e non ritaglia più da una
  data completa come `08.05.2025` un presunto dato di carta. I nomi dietro
  una formula di cortesia terminano al ritorno a capo invece che nella via
  successiva; i nomi di luogo nei nomi file degli allegati vengono limitati
  al luogo effettivo. Anche colori di veicoli, valori di stato tecnici,
  denominazioni di attività e forme giuridiche di prodotto restano
  invariati. Letture di segnaposto danneggiate come `|PLLZ` non vengono
  più trattate come dato personale in un secondo passaggio OCR.

- Le immagini PDF salvate lateralmente ricevono, nel controllo visivo
  finale, uno sguardo aggiuntivo nella loro posizione immagine invariata.
  Questo può oscurare successivamente solo valori che Maskuro ha già
  riconosciuto con sicurezza sulla stessa pagina. Così viene ad esempio
  coperto completamente un piccolo timbro di indirizzo ruotato, senza
  inventare nuove parole da intestazioni di immagine o disegni tecnici
  come dati personali.

- Nei testi OpenDocument, le iniziali dell'autore di una nota (commento)
  vengono ora svuotate insieme all'autore. LibreOffice le deposita accanto
  al nome completo come forma abbreviata propria e le mostra esattamente
  nel margine della pagina; finora vi restava „SO", mentre „Sieglinde
  Ortner" accanto era già da tempo un segnaposto. Viene svuotato solo se
  l'autore è stato effettivamente sostituito – la nota di un reparto
  mantiene la propria identificazione.

- Nelle lettere commerciali italiane, le formule standard all'inizio della
  frase non valgono più come nome o luogo: „Restiamo a disposizione",
  „Rimaniamo", „Attendiamo", „Alleghiamo", „Comunichiamo" e „Auguriamo
  buon lavoro" restavano finora appese come presunta persona o dato di
  luogo. I nomi reali nello stesso punto („Rossi Mario") continuano a
  essere riconosciuti.

- Le scansioni a due colonne proteggono ora identificativi etichettati e
  dati di luogo anche quando il riconoscimento testo fornisce prima tutte
  le intestazioni di campo e poi tutti i valori. L'assegnazione segue la
  riga di pixel visibile e funziona anche con pagine ruotate di 90 gradi.
  Parti separate strettamente di un identificativo di passaporto o
  contratto vengono oscurate insieme; date di nascita etichettate, codici
  ICD e PZN sono anch'essi coperti, le parole tecniche successive restano.
  Nomi brevi e nomi utente vengono protetti in campi esatti; indirizzi
  email scomposti in più parole OCR solo con vicinanza stretta e
  grammatica email completa. Una correzione vincolata al campo di
  caratteri facilmente confondibili nonché la rilettura locale di un campo
  persona ancora vuoto racchiudono scansioni danneggiate e ruotate, senza
  estendere campi tecnici o valori già occupati. I margini di sicurezza
  seguono la dimensione della parola, e il profilo caratteristica include
  unità di dosaggio e intervalli di pagamento direttamente adiacenti.
  Moduli inseriti leggermente storti vengono riproiettati geometricamente
  da più righe OCR nella stessa direzione; rumore di arrotondamento o
  testimoni contraddittori non bastano. Brevi prefissi di lettere restano
  prima di un identificativo con trattino, e un rilevamento di indirizzo
  etichettato completo sostituisce solo il suo rilevamento parziale di via
  dello stesso tipo. Un'intestazione di campo di ruolo letta male cade
  esclusivamente in una colonna modulo occupata da almeno tre intestazioni
  note; i nomi di chat restano protetti. Un ritaglio di margine ristretto e
  una sovraesposizione locale con riflesso di luce diagonale completano la
  matrice immagine. I rilevamenti di persona, luogo e azienda che
  attraversano più righe di modulo vengono limitati, in una colonna campo
  occupata più volte, al rispettivo valore. Un valore di posizione tecnico
  cade solo con intestazione di posizione e forma identificativa
  corrispondente; i nomi reali restano protetti. Anche valori email
  interrotti dal riflesso di luce vengono rimossi dietro un'intestazione
  di campo email esplicita con margine immagine stretto e limitato ai
  vicini. Due coppie campo-valore della stessa riga visibile vengono ora
  valutate indipendentemente; valori su una linea di base più profonda
  vengono collegati solo dopo tre testimoni geometrici concordanti. Così
  numeri identificativi, date di nascita e indirizzi restano completamente
  protetti anche in layout modulo densi. Via, CAP e località vengono
  unificati esclusivamente all'interno dello stesso campo indirizzo e con
  grammatica postale corrispondente. Campi tecnici delimitati strettamente
  per ausili di lavoro e stato dentale non generano più falsi allarmi di
  luogo o elenco; nomi reali e campi denominati in modo simile restano
  protetti. Il laboratorio documenti tedesco comprende ora 440 scansioni e
  raggiunge 2.981/2.981 nel profilo base nonché 3.080/3.080 nel profilo
  caratteristica. Tutte le undici mutazioni immagine e tutte le 40
  famiglie di documenti sono al 100 per cento,
  continuando senza falso allarme misurato, violazione di conservazione o
  interruzione.

- Gli strati di testo PDF con separatori di cella persi delimitano ora i
  rilevamenti di organizzazione, indirizzo e luogo sulla base della
  struttura campo-valore ripetuta. Le intestazioni di campo davanti a
  valori aziendali e frecce tecniche come `=>` o `->` non fanno più parte
  del rilevamento. La visualizzazione aggiuntiva per gli a capo morbidi non
  può più estendere rilevamenti di forma giuridica e luogo su più righe di
  tabella; un indirizzo già completo termina prima della successiva
  intestazione di campo con valore. L'esecuzione finale su tutti i 1.600
  documenti TXT, HTML, PDF e DOCX rimuove 10.840/10.840 dati attesi con
  zero falsi allarmi, zero violazioni di conservazione e zero
  interruzioni.

## 0.10.44-beta.1 – 1° settembre 2026

- La generazione del pacchetto produce ora output separati per Windows x64 e ARM64, macOS su Apple Silicon e Intel, nonché Linux x64 e ARM64. Nomi dei pacchetti,
  selezione degli aggiornamenti e release distinguono l'architettura; una
  pubblicazione resta bloccata finché uno dei sei target o la relativa
  attestazione delle dipendenze manca. Linux ARM64 richiede, a causa di Qt, almeno glibc
  2.39. Collaudati completamente su hardware reale sono per ora solo
  Windows x64 e macOS su Apple Silicon; i pacchetti per le altre architetture vanno
  chiaramente indicati come versioni preliminari per prove, non per l'uso in produzione.

- Con più file, il riconoscimento ora continua a elaborare mentre
  un'anteprima attende la revisione. Fino a tre anteprime preparate vengono
  mostrate in sequenza; nel frattempo continua a elaborare un solo documento,
  e un file risultato nasce solo dopo il suo rilascio. Un'eccezione permanente scelta nell'anteprima vale anche per i documenti seguenti già preparati.

- I certificati di redazione ora si possono verificare in qualsiasi momento direttamente dal menu File a fronte
  del documento oscurato. Maskuro distingue in tal caso un file firmato corrispondente, una prova corrispondente ma non firmata, una
  firma non valida e un documento non corrispondente al certificato. Non è richiesta una licenza
  né l'account originale del sistema operativo per la controprova.
  Per i sistemi di verifica automatica lo stesso confronto è disponibile tramite
  `--zertifikat-pruefen`; i codici di ritorno distinguono corrispondenza,
  errore d'uso e prova non valida.
  La controprova confronta inoltre l'ID Maskuro incorporato con il
  certificato; un ID estraneo inserito liberamente emerge quindi anche con una
  prova non firmata.
  In caso di firma valida, l'esito della verifica mostra inoltre l'operatore attivato dall'amministrazione con account del sistema operativo, ID
  account tecnico e piattaforma. Le indicazioni non confermate provenienti da prove non firmate o
  non valide non vengono restituite.

- Un nuovo laboratorio documenti tedesco genera 160 documenti TXT, HTML, PDF e DOCX interamente sintetici da dieci ambiti e quattro
  varianti strutturali. Il manifesto distingue ora esplicitamente tra
  dati che devono sparire e testi tecnici ovvero
  identificativi tecnici che devono essere conservati; famiglia del documento, mutazione e
  fonte strutturale pubblica sono documentati in modo tracciabile.

- Il laboratorio documenti tedesco è stato esteso a 280 file, sette forme strutturali,
  1.540 valori attesi e 1.036 ancore di conservazione. Vengono verificati di nuovo
  moduli numerati, campi PDF/maschera tra parentesi e assegnazioni tecniche
  `=>`. Lo stato completo esteso raggiunge in TXT, HTML, PDF e
  DOCX rispettivamente il 100 percento con zero falsi allarmi. Campi data e numero identificativo tra parentesi, separatori a freccia e collettivi
  esplicitamente etichettati
  vengono ora riconosciuti strutturalmente.

- Un secondo ampliamento del laboratorio porta il patrimonio a 400 documenti, dieci
  forme strutturali, 2.200 valori attesi e 1.480 ancore di conservazione. Valori chiave in stile JSON,
  liste YAML e campi modulo in maiuscolo raggiungono insieme
  al patrimonio precedente il 100 percento con zero falsi allarmi. Date di nascita
  e identificativi citati, così come ruoli esplicitamente etichettati come persone assicurate, candidate, soggette a dichiarazione e autorizzate alla rappresentanza,
  vengono ora riconosciuti anche in queste forme di esportazione.

- Una modalità OCR separata del laboratorio documenti tedesco genera inoltre
  200 scansioni di sole immagini da tutte le 40 famiglie. Pagine pulite, a basso contrasto,
  a bassa risoluzione, con artefatti JPEG e ruotate di 90 gradi
  vengono rimisurate con riquadri di pixel esatti, senza alterare la
  base testuale comparabile di 1.600 file. Il manifesto separa
  caratteristiche attivabili di data, denaro e medicina dal profilo di base e conosce
  letture OCR documentate senza contarle come punti attesi aggiuntivi. La
  misurazione viene scomposta per mutazione e famiglia di documento. Confini di
  campo stretti impediscono tra l'altro che `Az` nel nome di luogo `Graz` faccia oscurare una
  data seguente come numero di protocollo; l'attuale matrice di base gira
  con zero falsi allarmi e zero interruzioni.

- Cinque ulteriori famiglie di documenti tedeschi per fattura/bolla di consegna,
  banca/credito, affitto/amministrazione immobiliare, scuola/università e
  logistica/dogana ampliano il laboratorio a 600 file con 3.520
  valori attesi e 2.360 ancore di conservazione. Un percorso tabellare PDF stretto usa
  l'intestazione esplicita `Campo Valore` quando il livello testo perde i separatori di cella; una nuova
  selezione `--familien` accelera le misurazioni parziali. I 200 nuovi file
  raggiungono 1.320/1.320 con zero falsi allarmi e zero interruzioni.

- Assicurazione/sinistro, lavoro/stipendio, medicina/laboratorio, veicolo/officina e
  tecnica/manutenzione ampliano il laboratorio documenti tedesco a 800 file con
  4.960 valori attesi e 3.200 ancore di conservazione. Identificativi di polizza, paziente,
  perito e veicolo etichettati in modo stretto, così come nuovi campi di ruolo, indirizzo
  e organizzazione vengono riconosciuti. La nuova matrice parziale e la
  matrice completa raggiungono il 100 percento con zero falsi allarmi e zero
  interruzioni in TXT, HTML, PDF e DOCX.

- Edilizia/appalto, energia/ambiente, associazione/società,
  comunicazione/calendario e hotel/evento portano il laboratorio documenti
  tedesco a 1.200 file con 7.920 valori attesi e 4.800
  ancore di conservazione. Nuovi campi di ruolo, azienda, indirizzo, registro, aggiudicazione,
  prenotazione e account utente vengono riconosciuti anche in tutte le
  forme di esportazione. I numeri di contatore restano conservati come identificativi tecnici. Matrice
  parziale e completa raggiungono il 100 percento con zero falsi allarmi e zero interruzioni.

- Ristorazione/servizio di consegna, farmacia/ricetta, pompe funebri/cimitero,
  sport/iscrizione e immobiliare/agenzia ampliano il
  laboratorio documenti tedesco a 1.400 file con 9.360
  valori attesi e 5.640 ancore di conservazione. Nuovi ruoli di persona, campi di indirizzo e
  numeri di richiesta di ricerca vengono riconosciuti. Ragioni sociali etichettate con forma giuridica
  restano completamente protette anche dopo un'interruzione di riga automatica;
  classi d'età e specialisti tecnici non vengono più sostituiti erroneamente. Matrice
  parziale e completa raggiungono il 100 percento con zero falsi allarmi e zero interruzioni.

- Cura odontoiatrica, scuola guida, vigili del fuoco/intervento, comunità energetica e
  viaggio tutto compreso ampliano il laboratorio documenti tedesco a 1.600 file con
  10.840 valori attesi e 6.440 ancore di conservazione. Nuovi ruoli, campi di indirizzo
  nonché identificativi di trattamento, formazione, intervento, energia e
  contratto di viaggio vengono riconosciuti strutturalmente. La nuova matrice parziale di 200 file
  raggiunge 1.480/1.480; la matrice completa raggiunge
  10.840/10.840. Entrambe restano a zero falsi allarmi e zero interruzioni.

- La misurazione completa del laboratorio documenti ha ridotto, grazie a forme ufficiali strette e
  regole strutturali, le sostituzioni non necessarie da 68 a 0, le
  violazioni di conservazione misurate esplicitamente da 23 a 0 e le interruzioni da 3 a 0.
  Il tasso di rilevamento è salito nel contempo da 91,1 a 100,0 percento; TXT, HTML, PDF e
  DOCX raggiungono ciascuno il 100 percento. Intestazioni di tabella generiche
  come `Campo` vengono frenate solo nella sequenza documentata `Campo`/`Valore`;
  un cognome omofono resta protetto. Numeri di protocollo giudiziari con
  lettera finale, campi con segno di uguale,
  `Data di nascita del figlio` e più nomi singoli etichettati nella stessa
  riga vengono riconosciuti completamente. Tabelle Word e campi di riga precedente usano
  la loro intestazione di campo come contesto di riconoscimento temporaneo; indirizzi PDF etichettati
  restano completamente protetti anche con un'interruzione di riga dovuta all'impaginazione.

- I campi tedeschi di caratteristiche personali, professione e medicina funzionano ora
  anche con interruzioni di riga stile Windows. Indicazioni di genere di una sola lettera come
  `Sesso`/`f` vengono protette nella forma a riga precedente. I campi oggettivi
  `Articolo-PZN` non attivano invece né un riconoscimento di codice farmaco né un
  riconoscimento di persona; le indicazioni PZN, ICD e ATC reali restano riconosciute.

- I campi modulo e numero tedeschi sono più precisi: „DW." funziona ora
  anche prima di un'interruzione di riga morbida, i nomi esplicitamente etichettati vengono
  rimossi anche se scritti in minuscolo e i numeri di protocollo puramente numerici vengono assegnati al
  loro corretto tipo di identificativo. Al contrario, un numero di fattura, documento o articolo casualmente
  valido secondo Luhn non vale più come carta di credito. Campioni sintetici di output HTML e
  PDF confermano rimozione e conservazione nel documento finito.
  Identificativi e nomi utente vengono inoltre riconosciuti quando la loro
  etichetta si trova nella riga di tabella o modulo immediatamente precedente; i numeri di documento oggettivi
  restano visibili anche in questa forma.

- Le password vengono ora riconosciute anche dopo un'intestazione di campo isolata nella
  riga precedente. Caratteri speciali finali come `!` o `#`
  appartengono in tal caso interamente al valore protetto. I PIN di prodotto e articolo
  non vengono invece più mascherati come PIN di carta; i campi espliciti
  `PIN` e `PIN carta` restano protetti.

- I valori modulo scritti in minuscolo vengono ora, in presenza di campi tedeschi inequivocabili di
  indirizzo e `CAP/Città`, restituiti come indirizzo ovvero
  CAP con città invece che solo come luogo generico. Allo stesso modo restano
  protetti valori aziendali scritti in minuscolo come „beispiel service" dopo un campo azienda, senza troncare la parola finale come presunta
  intestazione di campo successiva.

- Guida, FAQ, testo sulla privacy e sito web spiegano ora insieme la prova di origine: ID Maskuro neutro nel documento, associazione opzionale all'account reale del sistema
  operativo solo nel registro di verifica locale, cambio utente su
  Windows/macOS/Linux e valore probatorio di SHA-256 e firma.

- Gli elenchi di prestazioni tecnici basati su immagini vengono ripuliti in modo più prudente. Parole tecniche inequivocabili come „Abbruchhämmern", „Deckungsrücklass",
  „Positionsnummern", „Einbauplatine" o „Terminsituation", nonché forme OCR
  spezzate a metà parola non contano più come persona o luogo. Un'offerta reale di un comune è così scesa
  da 140 a 90 sostituzioni univoche, senza generare nuovi
  falsi positivi; nomi come Schneider, Lang, Bauer e Hahn
  restano espressamente protetti.

- Sono stati risolti ulteriori falsi allarmi da offerte reali: „Digital signiert"
  non contiene più una presunta persona, un BIC viene riconosciuto anche senza due punti
  dopo la sua etichetta, `15000 Alternativ` non conta più come CAP con città, e la citazione UE „(VO (EG) 715/2007" non genera più un'organizzazione. Un'offerta fotovoltaica è così scesa da 26 a 16
  occorrenze di sostituzione; nomi, luoghi e dati di conto reali sono rimasti conservati.

- Negli organigrammi del personale, l'abbreviazione per sostituto „Stv." e
  un'intestazione di area „FACILITY" separata da sola non vengono più sostituite come
  nome di persona. La controprova reale di 13 pagine è scesa da 878 a 875
  sostituzioni; nomi, numeri interni e la ragione sociale sono rimasti protetti.

- I file PDF, OpenDocument e Office ripuliti ricevono un identificativo neutro
  „MASKURO-…" nelle loro proprietà documento. Il rapporto di verifica e il
  registro di verifica firmato riportano lo stesso identificativo nonché i valori SHA-256 di
  origine e risultato; il certificato di redazione riprende l'identificativo dal
  file finito. Un nome utente viene aggiunto solo se l'amministrazione attiva
  espressamente il campo utente esistente.

- Finestra principale e impostazioni sono organizzate in modo più ordinato: Salva, Copia,
  Dettagli, Indicatori e l'eliminazione di un profilo di riconoscimento compaiono solo
  quando l'azione relativa è possibile. Le sigle tecniche di lingua OCR e
  esempi lunghi si trovano ora, se necessario, nel testo di aiuto invece che permanentemente nell'area
  di lavoro. La pagina di riconoscimento si adatta meglio a finestre più strette,
  senza spiegazioni troncate o barre di scorrimento orizzontali; l'avviso su
  testo in chiaro nell'elenco delle sostituzioni resta comunque visibile.

- Il riconoscimento copre ulteriori casi di contatto tedeschi e internazionali: i numeri di telefono vengono ora verificati per tutte le regioni-paese selezionabili, i ruoli contrattuali ungheresi e croati rilevano ora anche cognomi omonimi di professioni in modo completo, e gli elenchi numerati di ricambi/materiali non generano più un falso allarme di persona a causa di „Mutter / Flach". I campi persona con valore oggettivo chiaramente contenente cifre non vengono più assunti come nome; la zona leggibile automaticamente del passaporto (MRZ) si può inoltre attivare e disattivare insieme tramite il gruppo „Identificativi".

- Le aziende senza forma giuridica vengono distinte meglio dalle persone dietro campi datore di lavoro ambigui: nomi come „Huber Handel", „Müller Logistik" o
  „Kowalski Handel" vengono rilevati interamente come azienda, mentre
  „Arbeitgeber: Bauer Anna" resta un nome di persona. La selezione automatica
  del paese considera per i documenti francesi ancora l'intero
  spazio linguistico francese, Lussemburgo incluso.

- Firme e testo personale riconosciuti all'interno di un'immagine venivano finora sempre coperti con un rettangolo nero – anche quando per le oscurazioni era impostato un colore diverso o un motivo come „Arcobaleno". Queste aree dell'immagine ora adottano anch'esse la rappresentazione di oscuramento scelta; la superficie coprente continua a essere scritta direttamente nei pixel dell'immagine.

- Il riconoscimento inglese è stato ricalibrato e migliorato in modo mirato su undici documenti reali tradotti manualmente: stato dell'inventario, campi tecnici di offerta e webshop nonché ruoli negli elenchi dei dipendenti restano visibili, „CV" non viene più letto come forma giuridica nel set di modelli, i tipi di carattere citati restano conservati, e i nomi in intestazioni di CV verticali, elenchi di dipendenti multipagina, dopo „Account manager" nonché ragioni sociali che iniziano con una cifra vengono riconosciuti completamente. I numeri di registro delle imprese austriaci funzionano ora anche dopo un'etichetta inglese; la forma abbreviata „Customer:", i numeri di registrazione EAR e i numeri di datore di lavoro portano il loro valore. Catene di quote, tipi di cavo, riferimenti giuridici UE, date di validità delle offerte, luoghi di adempimento, fori competenti, tribunali di registro, l'abbreviazione fiscale „NoVA", numeri tecnici nelle etichette dei pneumatici nonché riferimenti a norme come „OVE R6-2" e „AStV" non generano più falsi allarmi. Un IBAN valido etichettato termina correttamente prima del campo di registrazione o del titolo della riga successiva; indirizzi con l'aggiunta di zona commerciale vengono riconosciuti completamente anche da flussi di testo PDF con interruzioni di riga stile Windows. Le introduzioni aziendali inglesi e i nomi di casse di risparmio strutturati vengono delimitati completamente. Il paese del documento di origine resta conservato per le versioni linguistiche dei codici postali e degli identificativi specifici del paese.

- Nelle righe di intestazione di destinatario e messaggio, il modello linguistico poteva unire i primi due nomi di un elenco separato da virgole in un unico risultato („Bcc: Huber, Mayer"). Entrambi i nomi vengono ora riconosciuti, sostituiti e riportati nel rapporto singolarmente – anche dopo „Sent:", „Reply:" e „Fwd:".

- L'area leggibile automaticamente di un passaporto o documento d'identità (MRZ) mancava nel controllo di gruppo „Cosa viene cercato". Ora appartiene a „Identificativi" e si può attivare e disattivare insieme a questo gruppo.

- Chi sceglie „Arcobaleno" come modello per i testi sostitutivi, ottiene ora anche i punti oscurati nello stesso aspetto grafico; finora restavano sorprendentemente in nero classico. Le aree di oscuramento si possono in seguito continuare a impostare in modo indipendente su un altro modello.

- Il pannello delle pagine dell'editor di rifinitura poteva restare vuoto dopo il ripristino di una disposizione di finestra salvata, finché la sua larghezza non veniva modificata manualmente. Le miniature vengono ora riordinate dopo la costruzione visibile della finestra e sono subito centrate nel pannello.

- I contrassegni di verifica colorati attorno ai testi sostitutivi nei PDF restavano poco visibili a seconda del colore di categoria e semaforo. Un contorno chiaro ora separa in modo affidabile il riquadro di verifica dal segnaposto colorato e dallo sfondo della pagina.

- Chi oscura nell'editor di rifinitura una riga il cui documento è impostato con interlinea stretta (tipico di offerte e capitolati) otteneva una barra che sconfinava nei tratti ascendenti della riga sottostante – che diventava così solo mezza leggibile. La barra termina ora al carattere realmente disegnato della riga vicina; la riga oscurata stessa resta comunque completamente coperta, discendenti comprese.

- Il documento di esercitazione („Guida → Apri documento di esercitazione", anche nella visita guidata) mostra ora ogni tipo di riconoscimento: alla lettera inventata si aggiungono una fotografia con volto riconoscibile, una firma scritta a mano, professione e reparto, diagnosi e farmaco – oltre a ragione sociale, importo e data che c'erano già. Ciò che l'impostazione predefinita lascia intenzionalmente al suo posto è spiegato dal foglio stesso, insieme all'interruttore che lo rimuove; il volto nella fotografia viene di serie pixelato.

- Gli importi in denaro nella comune notazione tedesca con il simbolo dopo il numero („1.240,00 €") non venivano mai trovati dall'interruttore „Rimuovi anche importi in denaro" – „1.240,00 EUR" e „€ 1.240,00" invece sempre. Ora tutte e tre le notazioni vengono riconosciute.

- La ricerca delle firme funziona ora anche su file immagine isolati: chi ripulisce una scansione come JPG o PNG ottiene le firme scritte a mano oscurate al suo interno – lo stesso riconoscimento, lo stesso messaggio nel rapporto come per PDF. Le immagini incorporate nei file Office continuano a non essere esaminate, perché il riconoscimento lì risulta, per misurazione, inaffidabile; la casella si chiama quindi ora „PDF e file immagine: oscura firme scritte a mano".

- Una barra di oscuramento poteva, con interlinea stretta, sconfinare visibilmente nei tratti ascendenti della riga sottostante rendendola mezza illeggibile – l'altezza della barra derivava dalle metriche del carattere, non da ciò che è realmente stampato sulla carta. La barra termina ora all'inchiostro effettivamente disegnato della riga vicina, sia nell'editor di rifinitura sia nella ripulitura automatica. La riga propria, discendenti comprese, resta sempre completamente coperta; se le righe si sovrappongono davvero, la barra preferisce restare sulla riga vicina piuttosto che lasciare scoperto qualcosa.

- In un elenco dipendenti con ruolo sotto il nome, una qualifica dirigenziale femminile („Anna Berger" con „Montageleiterin" sotto) veniva inclusa nella sostituzione del nome – la forma maschile accanto restava correttamente al suo posto. Le forme femminili „…leiterin" (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-, Gruppen-, Amtsleiterin) vengono ora trattate come le loro controparti maschili, quali denominazioni di funzione; Filial-, Personal- e Vertriebsleitung sono nuove in entrambe le forme.

- Il riconoscimento delle professioni attivabile non trovava ruoli dirigenziali femminili come „Projektleiterin", „Teamleiterin" o „Abteilungsleiterin", ma trovava già le loro forme maschili. Ora entrambe le forme contano allo stesso modo.

- Nella finestra di anteprima su Mac, l'indicazione multipla era attaccata direttamente al termine („Anna Musterfrau2" invece di „Anna Musterfrau 2"). Lo spazio è di nuovo presente.

- La lente di confronto ha un nuovo pulsante accanto al regolatore di zoom: con una pressione la posiziona a piena larghezza sopra il risultato – ciascuno a metà altezza, e l'originale nella stessa scala del documento (lo zoom della lente salta in tal caso al 100%). Una seconda pressione la riancora piccola nella colonna sinistra e ripristina lo zoom precedente della lente. Il cerchietto accanto ora reimposta solo lo zoom – il suo testo di suggerimento finora affermava erroneamente che riancorasse anche la finestra.

- Nella barra degli strumenti dell'editor di rifinitura, lo strumento scelto è di nuovo riconoscibile come tale: il pulsante dello strumento attivo porta una superficie piena con bordo blu – così come ogni altro pulsante di attivazione acceso della barra (ad esempio lente di confronto o modalità apprendimento). L'evidenziazione era andata persa con il nuovo design dei pulsanti del 29 agosto.

- I numeri di posizione di un capitolato („2.3.3.3, 2.3.3.4, 2.3.3.5" uno sotto l'altro) venivano scambiati per indirizzi IP e rimossi dal risultato; numeri a tre livelli con l'ultimo elemento simile a un anno („2.3.19, 2.3.20") cadevano come date del calendario. Una sequenza numerica crescente all'inizio riga viene ora riconosciuta per ciò che è – un elenco di posizioni; indirizzi reali (tabelle di rete con contesto tecnico, numeri sopra 99) e date reali continuano a essere riconosciuti.

- Cognomi come „Müller", „Fischer", „Bauer", „Koch", „Wagner", „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster", „Schäfer" o „Meister" restavano in chiaro negli elenchi della forma „Cognome, Nome" (ad es. „Teilnehmer: Müller, Peter; Nowak, Anna"), perché sono anche denominazioni professionali comuni. Ora vengono riconosciuti in modo affidabile.

- Nell'oscuramento di un PDF, la barra poteva, in celle di tabella strette, portare via l'intera cella: dal risultato „D-LINK" in un capitolato è stata rimossa l'intera descrizione del prodotto accanto, sebbene l'anteprima avesse menzionato solo il risultato. La barra continua a coprire intere righe di blocco indirizzo e intestazioni di campo, ma non copre più cose estranee di quante ne copra di meritevoli di protezione – la descrizione accanto al risultato ora resta al suo posto.

- Dopo „Ripristina visualizzazione" nell'editor di rifinitura, il pannello delle pagine restava vuoto – le miniature delle pagine erano visibili di nuovo solo dopo la chiusura e riapertura della finestra. Ora compaiono anche subito dopo il ripristino, centrate come prima.

- L'editor di rifinitura ha un quarto strumento: **Rimuovi** toglie il testo sotto il riquadro senza sostituzione – senza barra (oscuramento) e senza segnaposto (sostituzione); il vuoto resta visibile come tale. Funziona parola per parola; se sotto c'è un'immagine, il suo sfondo viene liberato in bianco, e „Ripristina originale" annulla anche una rimozione senza sostituzione. Icona propria nella barra, distintivo a mirino (croce), tasto di scelta rapida proprio in tutte le 18 lingue (tedesco F come entFernen).

- Nella barra di ricerca del PDF, „Cartella …" si trova ora a destra accanto alle opzioni di ricerca. Da quando esiste, oltre all'oscuramento, anche la sostituzione dei risultati, cinque pulsanti non stavano più affiancati con larghezza normale della finestra – il primo veniva compresso e il suo testo troncato.

- „Ripristina tutte le impostazioni" ora reimposta anche la casella „Sostituisci rosso/verde con altri colori" e la contrassegna, come ogni altra, con „modificata" quando si discosta dalla configurazione di fabbrica.

- I testi sostitutivi nei PDF ora appaiono più uniformi: dove il segnaposto completo dovrebbe risultare notevolmente più piccolo della sua riga (ad es. „[BEG16]" schiacciato in una parola breve come „Das"), compare invece una forma abbreviata in dimensione riga („[B16]") – ben leggibile invece che minuscola, e il numero per il ripristino porta entrambe le grafie. Un segnaposto diventa minuscolo solo se anche la forma più breve non trova posto – ciò resta comunque meglio di una barra senza alcuna informazione.

- Un testo sostitutivo colorato in modo multicolore (sfumatura o arcobaleno) in un PDF restava integro solo fino al successivo intervento: ogni ulteriore sostituzione o oscuramento sulla stessa pagina poteva comprimere segnaposto già impostati in una pila di caratteri illeggibile e schiacciata – chi sostituiva parola per parola nell'editor vedeva, invece di „[BEG17]", solo caratteri stampati uno sull'altro. I segnaposto una volta impostati ora restano come sono stati impostati.

- L'interruttore per le eccezioni permanenti nell'anteprima si chiama ora „Non rimuovere mai" – come l'elenco in cui inserisce; finora c'era scritto „mai più". La riga del risultato accanto è più ordinata: il simbolo informazioni „ⓘ" è più grande e più facile da colpire, e casella, contrassegno di sostituzione e pulsante hanno un'altezza comune. La frase attorno a un risultato ora sfrutta davvero la larghezza annunciata – l'indicazione di larghezza precedente veniva finora silenziosamente ignorata dalla visualizzazione, e il riquadro si avvolgeva come una striscia stretta.

- Nell'editor, il puntatore del mouse ora indica quale strumento è attivo: un mirino per puntare, accanto un piccolo segno – barra per oscurare, frecce di scambio per sostituire, arco annulla per ripristinare, trama a pixel per pixelare. I simboli a mano precedenti sono stati eliminati; una mano altrove significa sempre „afferra e sposta". Ora ha un compito adatto: su una parola o barra evidenziata in rosso, il puntatore diventa una mano che indica – lì basta un clic.

- „Riconoscimento massimo (IA)" non offre più un modello linguistico locale scaricabile – il livello ora calcola esclusivamente tramite una IA propria configurata sotto „Collega la tua IA". Chi aveva già collegato un proprio server non nota alcuna differenza.

- Il tour guidato dell'anteprima spiega ora anche il simbolo informazioni „ⓘ", che mostra la frase attorno a un risultato. E questa frase stessa è più leggibile: un livello di carattere più grande, più interlinea, larghezza fissa invece di un avvolgimento stretto e serrato.
- Anche „Verifica file", „Regole di riconoscimento e termini personalizzati", „Ripulisci testo" e „Ripulisci immagine" hanno ora un proprio tour – tramite un nuovo pulsante „Tour della finestra", poiché queste quattro finestre non hanno una propria barra dei menu.
- I nomi sotto nove etichette di ruolo contrattuale ucraine restavano riconosciuti in modo incompleto in caso di cognome omografo, quando l'etichetta stava da sola nella sua riga: „Покупець"/„Продавець" (Acquirente/Venditore), „Поручитель"/„Боржник" (Fideiussore/Debitore principale), „Свідок" (Testimone), „Орендодавець"/„Орендар" (Locatore/Locatario) e „Спадкодавець"/„Спадкоємець" (De cuius/Erede). I nomi vengono ora riconosciuti completamente.

- Il commento di un'area denominata in una cartella Excel (Gestione nomi, campo „Commento") portava invariato un nome in esso registrato. Ora viene ripulito esattamente come il resto del contenuto della cartella.

- I nomi sotto sette etichette di ruolo contrattuale ungheresi restavano completamente non rilevati in caso di cognome omografo: „Bérbeadó"/„Bérlő" (Locatore/Locatario), „Vevő"/„Eladó" (Acquirente/Venditore), „Kezes"/„Főadós" (Fideiussore/Debitore principale) e „Tanú" (Testimone). I nomi vengono ora riconosciuti completamente.

- I nomi sotto l'etichetta ceca „Kupující" (Acquirente) restavano completamente non rilevati in caso di cognome omografo. Il nome viene ora riconosciuto completamente.

- I nomi sotto l'etichetta russa „Опекун" (Tutore) restavano completamente non rilevati in caso di cognome omografo. Il nome viene ora riconosciuto completamente.

- I nomi sotto sei ulteriori etichette croate restavano non rilevati: „Jamac" (Fideiussore), „Glavni dužnik"/„Dužnik" (Debitore principale/Debitore), „Ostavitelj" (De cuius), „Nasljednik" (Erede) e „Vjerovnik" (Creditore). I nomi vengono ora riconosciuti completamente.

- Una pagina HTML salvata con una sottopagina incorporata nell'attributo `src` di un `<embed>` (invece di `data` in `<object>`) portava invariati dati personali al suo interno. Ora vengono ripuliti esattamente come con `<object>`.

- I nomi sotto cinque etichette di ruolo contrattuale danesi restavano riconosciuti in modo incompleto in caso di cognome omografo, quando l'etichetta stava con due punti prima del nome: „Arvelader"/„Arving" (De cuius/Erede), „Befuldmægtiget"/„Fuldmagtsgiver" (Procuratore/Mandante) e „Værge" (Tutore). I nomi vengono ora riconosciuti completamente; le corrispondenti etichette norvegesi sono state aggiunte a titolo cautelativo.

- I segnaposto nei file Word e PowerPoint portano ora lo stesso colore dell'aspetto grafico scelto (tinta unita, sfumatura, arcobaleno o per categoria) – finora restavano lì con il colore di testo normale, anche quando i risultati PDF erano già colorati da tempo.

- „Copia come testo" e „Copia come Markdown" mettono il testo in chiaro del risultato direttamente negli appunti – per incollarlo in chat, e-mail o un altro programma, senza dover prima aprire il file.

- I nomi sotto cinque ulteriori etichette slovene restavano non rilevati: „Toženec" (Convenuto), „Tožnik" (Attore), „Zastavitelj" (Datore di pegno), „Zastavni upnik" (Creditore pignoratizio) e „Darovalec" (Donante). I nomi vengono ora riconosciuti completamente.

- Il nome dell'autore di una modifica tracciata su cella di tabella (cella inserita, eliminata o unita in Word) restava presente nel file, anche quando lo stesso nome come autore di commento era già stato rimosso da tempo. Ora viene rimosso anch'esso.

- I nomi sotto nove ulteriori etichette slovene restavano non rilevati: „Najemodajalec"/„Najemnik" (Locatore/Locatario), „Zapustnik"/„Dedič" (De cuius/Erede), „Upnik"/„Dolžnik" (Creditore/Debitore), „Glavni dolžnik" (Debitore principale) e „Skrbnik" (Tutore/Curatore). I nomi vengono ora riconosciuti completamente.

- I nomi sotto cinque etichette slovene restavano non rilevati: „Izvedenec" (Perito), „Kupec" (Acquirente), „Prodajalec" (Venditore), „Naročnik" (Committente) e „Izvajalec" (Appaltatore). I nomi vengono ora riconosciuti completamente.

- I nomi sotto cinque ulteriori etichette lituane restavano non rilevati: „Užsakovas" (Committente), „Vykdytojas" (Appaltatore), „Vežėjas" (Vettore), „Siuntėjas" (Mittente) e „Arbitras" (Arbitro). I nomi vengono ora riconosciuti completamente.

- I nomi sotto sei ulteriori etichette lituane restavano non rilevati: „Įgaliotinis" (Procuratore), „Įgaliotojas" (Mandante), „Naudos gavėjas" (Beneficiario, assicurazione), „Trečiasis asmuo" (Interveniente/Terza parte nel processo civile), „Ankstesnis nuomininkas" (Precedente locatario) e „Naujasis nuomininkas" (Nuovo locatario). I nomi vengono ora riconosciuti completamente.

- Un segnalibro nei documenti ODT (`text:bookmark`) porta il proprio nome assegnato liberamente, spesso denominato secondo il punto a cui rimanda (ad es. „Herr_Mueller_Unterschrift") – invisibile per il lettore, ma presente testualmente nel file. Il nome viene ora ripulito anch'esso.

- I nomi sotto otto ulteriori etichette lituane restavano non rilevati: „Pareiškėjas" (Richiedente), „Suinteresuotas asmuo" (Controparte nel procedimento non contenzioso), „Ekspertas" (Perito/Consulente tecnico), „Bankroto administratorius" (Curatore fallimentare), „Valdybos narys" (Membro del consiglio di sorveglianza), „Direktorius" (Amministratore delegato), „Palikėjas" (De cuius) e „Įpėdinis" (Erede). I nomi vengono ora riconosciuti completamente.

- I nomi sotto sette ulteriori etichette lituane restavano non rilevati: „Liudytojas" (Testimone), „Vertėjas" (Interprete/Traduttore), „Notaras" (Notaio), „Dovanotojas" (Donante), „Apdovanotasis" (Donatario), „Pirkėjas" (Acquirente) e „Pardavėjas" (Venditore). I nomi vengono ora riconosciuti completamente.

- I nomi sotto sei ulteriori etichette lituane restavano non rilevati: „Globėjas" (Tutore/Curatore), „Palikimo administratorius" (Amministratore dell'eredità), „Laiduotojas" (Fideiussore), „Pagrindinis skolininkas" (Debitore principale), „Nuomotojas" (Locatore) e „Nuomininkas" (Locatario). I nomi vengono ora riconosciuti completamente.

- Un nome sotto l'etichetta lituana „Ieškovas"/„Atsakovas" (Attore/Convenuto come parte processuale) restava non rilevato, indipendentemente dal fatto che il cognome fosse anche una parola comune (ad es. „Vilkas" = Lupo) o meno. Il nome viene ora riconosciuto completamente.

- Una voce di indice dei nomi nei documenti ODT (segnalibro per l'indice analitico) portava il nome una seconda volta nella propria chiave di ordinamento – invisibile nel testo continuo, ma presente testualmente nell'indice generato successivamente. La chiave viene ora ripulita anch'essa.

- Il nome della diapositiva e il nome della sezione di una presentazione PowerPoint (visibili nell'area di selezione o nell'ordinamento diapositive) restavano non ripuliti, perché entrambi sono attributi legati a un elemento che non è testo della diapositiva. Entrambi vengono ora riconosciuti.

- Un nome composto lituano con trattino come „Petraitis-Kazlauskas" perdeva la sua seconda metà non appena lo precedeva del testo continuo (restava completo solo all'inizio del testo): il cognome viene ora riconosciuto completamente anche in tal caso.

- Un nome sotto l'etichetta „Cesionar" (croato, cessionario nella cessione del credito) generava un falso allarme, perché l'etichetta di campo stessa veniva letta erroneamente come persona. Un nome sotto l'etichetta russa „Цессионарий" (parimenti cessionario) restava invece completamente non rilevato. Entrambi i casi sono ora risolti.

- Un nome sotto l'etichetta „Zedent"/„Zessionar" (tedesco, cessione del credito) restava completamente non rilevato quando il cognome era anche una parola comune (ad es. „Bauer"). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Darczyńca"/„Obdarowany" (polacco, donante/donatario nel contratto di donazione) restava non rilevato quando il cognome era anche una parola comune (ad es. „Wilk" = Lupo). Allo stesso modo, l'etichetta rumena „Donatar" (donatario) restava impigliata in un cognome comune persino come presunto componente del nome. Entrambi i casi sono ora risolti.

- Un nome sotto l'etichetta „Wierzyciel"/„Dłużnik" (polacco, creditore procedente/debitore esecutato ovvero creditore/debitore generico) restava non rilevato quando il cognome era anche una parola comune (ad es. „Wilk" = Lupo). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Poręczyciel"/„Dłużnik główny" (polacco, fideiussore/debitore principale nei contratti di fideiussione) restava non rilevato quando il cognome era anche una parola comune (ad es. „Wilk" = Lupo). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Ubezpieczony"/„Ubezpieczający" (polacco, assicurato/contraente nelle polizze assicurative) restava parzialmente o completamente non rilevato quando il cognome era anche una parola comune (ad es. „Wilk" = Lupo). Allo stesso modo un nome sotto „Osiguranik"/„Osiguravatelj" (croato, stessi ruoli), lì spariva insieme al nome interamente (ad es. „Golub" = Colomba). Entrambi i nomi vengono ora riconosciuti completamente.

- Un nome sotto l'etichetta „Pełnomocnik"/„Mocodawca" (polacco, procuratore/mandante negli atti di procura) restava non rilevato quando il cognome era anche una parola comune (ad es. „Wilk" = Lupo). Allo stesso modo un nome sotto „Opunomoćenik"/„Opunomoćitelj" (croato, stessi ruoli), lì spariva persino interamente insieme al nome. Entrambi i nomi vengono ora riconosciuti completamente.

- Un nome sotto l'etichetta „Pozwany" (polacco, convenuto come parte processuale) restava non rilevato quando il cognome era anche una parola comune (ad es. „Wilk" = Lupo). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Najmoprimac"/„Najmodavac" (croato, locatario/locatore nei contratti di locazione) restava non rilevato quando il cognome era anche una parola comune (ad es. „Kovač" = Fabbro). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Pracodawca"/„Pracownik" (polacco, datore di lavoro/lavoratore come parte contrattuale nei contratti di lavoro) restava parzialmente non rilevato quando il cognome era anche una parola comune (ad es. „Krawiec" = Sarto). Il nome viene ora riconosciuto completamente.

- L'Ungheria aveva nel catalogo dei paesi solo gli identificativi personali e la partita IVA: il numero di registro delle imprese (Cégjegyzékszám) viene ora riconosciuto, se preceduto immediatamente dalla parola campo „Cégjegyzékszám" o dall'abbreviazione „Cg." – il numero stesso non porta cifra di controllo.

- L'Estonia aveva nel catalogo dei paesi solo l'Isikukood: il Käibemaksukohustuslase number (partita IVA presente su ogni fattura estone) viene ora riconosciuto con cifra di controllo.

- La Lettonia aveva nel catalogo dei paesi solo il Personas kods: il PVN reģistrācijas numurs delle persone giuridiche (identificativo aziendale su ogni fattura lettone) viene ora riconosciuto con cifra di controllo.

- Un'e-mail con contenuto cifrato (busta S/MIME o PGP/MIME, `multipart/encrypted`) veniva restituita senza alcun avviso come apparentemente completamente verificata, sebbene il suo contenuto effettivo fosse cifrato e quindi non verificato. Tali e-mail ora segnalano questo come un allegato non verificato.

- Malta mancava nel catalogo dei paesi: la partita IVA maltese (VAT number) viene ora riconosciuta.

- Il Lussemburgo mancava nel catalogo dei paesi: la partita IVA lussemburghese (n° TVA) viene ora riconosciuta.

- Un „Изчакайте" bulgaro posto a inizio frase ("Aspetti!") veniva segnalato come indicazione di luogo – lo stesso limite del modello già visto in precedenza con forme di invito ungheresi, polacche, ceche e altre senza modello linguistico proprio. Il falso allarme ora non compare più.

- Un nome sotto l'etichetta „Zleceniodawca", „Zleceniobiorca" (polacco), „Prestator" (rumeno), „Naručitelj" o „Izvođač" (croato) restava parzialmente o completamente non rilevato quando il cognome era anche una parola comune (ad es. „Wilk", „Vuk" = Lupo, „Vulpe" = Volpe, „Sokol" = Falco). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Nadawca" (polacco), „Afsender" (danese) o „Pošiljatelj" (sloveno) restava parzialmente o completamente non rilevato quando il cognome era anche una parola comune (ad es. „Sowa" = Civetta, „Bager" = Fornaio, „Volk" = Lupo). Il nome viene ora riconosciuto completamente.

- Un nome sotto l'etichetta „Gavėjas" (lituano) o „Prejemnik" (sloveno) restava parzialmente o completamente non rilevato quando il cognome era anche una parola comune (ad es. „Vilkas" = Lupo). Come già con „Primatelj" (croato) e „Modtager" (danese), il nome viene ora riconosciuto completamente.

- Un'intestazione di circolare come „To All Staff" o „To All Employees" veniva erroneamente riconosciuta e rimossa come nome di persona. Questo ora non si verifica più.

- Un nome sotto l'etichetta „Primatelj" (croato) o „Modtager" (danese) restava parzialmente non rilevato quando il cognome era anche una parola comune (ad es. „Golub" = Colomba, „Bager" = Fornaio). Come già con „Odbiorca" (polacco) e „Destinatar" (rumeno), il nome viene ora riconosciuto completamente.

- Un nome completo nella riga di firma di un documento danese, norvegese o greco restava parzialmente non rilevato quando l'etichetta „Underskrift" o „Υπογραφή" stava da sola sopra il nome – nel caso greco il cognome veniva persino riconosciuto come indicazione di luogo invece che come nome. Come già con „Подпись" (russo), il nome viene ora riconosciuto completamente.

- Il testo su una foto da telefono orientata lateralmente (la comune ripresa verticale, mostrata dritta solo tramite un contrassegno di rotazione dell'immagine) poteva sfuggire al riconoscimento del testo, perché finora leggeva i pixel grezzi e orizzontali. Tali foto vengono ora ruotate correttamente prima della lettura – come già in precedenza per il riconoscimento facciale.

- Un nome completo nella riga di firma di un documento russo, ucraino o lituano restava parzialmente non rilevato quando l'etichetta „Подпись", „Підпис" o „Parašas" stava da sola sopra il nome – nome o patronimico venivano persi. Come già con „Potpis" (croato), il nome viene ora riconosciuto completamente.

- Un volto su una foto da telefono orientata lateralmente (la comune ripresa verticale, mostrata dritta solo tramite un contrassegno di rotazione dell'immagine) poteva sfuggire al riconoscimento facciale, perché finora esaminava i pixel grezzi e orizzontali. Tali foto vengono ora ruotate correttamente prima della ricerca.

- Un nome completo nella riga di firma di un documento croato restava parzialmente non rilevato quando l'etichetta „Potpis" stava da sola sopra il nome o con due punti davanti – il nome veniva perso, sia come riga propria sia in „Potpis: Nome Secondo nome Cognome". Come già con „Unterschrift" e „Signature", il nome viene ora riconosciuto completamente.

- Un cognome da matrimonio dopo le abbreviazioni di stato civile „verh." (coniugata/coniugato) e „verw." (vedova/vedovo) restava finora completamente non rilevato, sia tra parentesi, dopo virgola sia attaccato senza spazio („Anna Meier (verh. Weber)", „Klaus Bauer (verw.Fischer)") – come già con „geb.", viene ora riconosciuto in modo affidabile.

- Un nome dopo la firma per procura „ppa." (ad es. nella riga di firma di un'e-mail o lettera commerciale) restava finora parzialmente o completamente non rilevato in caso di cognome omonimo di professione come „Bauer" o „Koch" – come già con „gez.", viene ora riconosciuto in modo affidabile.

- Il numero della carta d'identità polacca (dowód osobisty) veniva riconosciuto solo senza spazio tra serie e numero („ABS123456"). Proprio così, però, il documento non stampa l'indicazione – ufficialmente vi è uno spazio tra i due („ABS 123456"), e in questa grafia il numero finora restava non rilevato.

- Un PNG animato (APNG, ad es. una breve registrazione schermo salvata come PNG invece che GIF) veniva finora verificato e ripulito solo con la sua prima immagine, senza che ciò venisse segnalato – come già in precedenza per il WebP animato, Maskuro ora segnala che ogni ulteriore immagine resta non verificata nel risultato.

- Un'immagine WebP animata (ad es. da uno strumento di cattura schermo o un'applicazione di chat con più immagini in un file) veniva finora verificata e ripulita solo con la sua prima immagine, senza che ciò venisse segnalato – come già in precedenza per un TIFF multipagina, Maskuro ora segnala che ogni ulteriore immagine resta non verificata nel risultato.

- Un doppio nome sloveno con trattino („Ana-Marija Novak") perdeva la sua metà anteriore non appena lo precedeva un testo continuo nel documento – lo stesso errore già visto in precedenza per il polacco. „Ana-" restava in chiaro non riconosciuto, mentre il resto del nome veniva già sostituito.

- Un doppio nome polacco con trattino („Anna-Maria Kowalska") perdeva la sua metà anteriore non appena lo precedeva un testo continuo o una preposizione come „z"/„od" – il resto del nome veniva sostituito, „Anna-" restava in chiaro non riconosciuto.
- Le formule di cortesia kazake „Хабарласыңыз"/„Байланысыңыз" (ci contatti) nonché le forme verbali serbe „Помоћи", „Чекамо" e „Пишите" senza modello linguistico proprio venivano erroneamente riconosciute come nome di persona o luogo in frasi telefoniche.

- La parola di cortesia azera „Xahiş" (Prego/Richiesta) senza modello linguistico proprio veniva erroneamente riconosciuta come nome di persona in frasi telefoniche.

- Parole indonesiane e malesi di cortesia/invito senza modello linguistico proprio come „Silakan", „Mohon" (indonesiano), „Sila" e „Tolong" (malese) venivano erroneamente riconosciute come nome di persona o luogo in frasi telefoniche.

- La forma di invito uzbeka „Kutamiz" (aspettiamo) senza modello linguistico proprio veniva erroneamente riconosciuta come luogo in frasi telefoniche.

- Le forme di invito turche senza modello linguistico proprio come „Arayınız" (chiami) e „Bekliyoruz" (aspettiamo) venivano erroneamente riconosciute come nome di persona in frasi telefoniche.

- Forme di invito in altre lingue senza modello linguistico proprio (ceco, slovacco, greco) come „Zavolejte" (chiama), „Prosíme" (vi preghiamo) e „Περιμένουμε" (aspettiamo) venivano erroneamente riconosciute come nome di persona o luogo in frasi telefoniche.

- Le forme di invito ungheresi e polacche come „Hívjon" (chiami), „Kérjük" (vi preghiamo), „Várjuk" (aspettiamo), „Zadzwoń" (chiama) e „Czekamy" (aspettiamo) venivano erroneamente riconosciute come nome di persona o luogo in frasi telefoniche.

- In un elenco nominativo numerato senza forma tabellare (ad es. „1. Robert Brown", sotto „2. Mary Johnson") un nome con determinati cognomi inglesi (tra cui „Brown", „White", „Green", „Black", „Young") veniva completamente ignorato – il modello linguistico aveva unito il numero della riga seguente al nome, per cui il risultato non corrispondeva mai più esattamente.

- Nel modello linguistico polacco, l'iniziale del nome anteposta a un cognome (ad es. „J. Kowalski", „A. Nowak") restava non riconosciuta e non ripulita nel testo – veniva sostituito solo il cognome. Altre lingue verificate (tra cui tedesco, inglese, rumeno, croato, ungherese, russo) includevano già in precedenza la stessa iniziale.

- Un nome di persona dopo un titolo scritto in minuscolo come „dr.", „ing."
  o „dipl. ing." non veniva affatto riconosciuto in ungherese, rumeno e croato – non solo il titolo, ma l'intero nome andava perso
  (ad es. „dr. Kovács Béla", „ing. Andrei Popescu", „dipl. ing. Marko
  Horvat").
- Nei verbali di riunione sloveni, una denominazione di ruolo pura prima dei due punti (ad es. „Tajnik:", „Podpredsednik:", „Poročevalec:", „Predsedujoči:") veniva erroneamente riconosciuta come nome di persona non appena altrove nel verbale c'era già un vero nome di oratore.
- Nei verbali di riunione russi, una denominazione di ruolo pura prima dei due punti (ad es. „Секретарь:", „Докладчик:", „Докладчица:") veniva erroneamente riconosciuta come nome di persona non appena altrove nel verbale c'era già un vero nome di oratore.
- Nei verbali di riunione rumeni, una denominazione di ruolo pura con articolo determinativo prima dei due punti (ad es. „Secretarul:", „Președintele:", „Vicepreședintele:", „Moderatorul:", „Consilierul:") veniva erroneamente riconosciuta come nome di persona – „Președintele" già da sola, le altre in aggiunta non appena altrove nel verbale c'era già un vero nome di oratore.
- Nei verbali di riunione croati, una denominazione di ruolo pura prima dei due punti (ad es. „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:", „Predsjedavajući:") veniva erroneamente riconosciuta come nome di persona.
- Un indirizzo di casella postale polacca „Skrytka pocztowa" dopo un'etichetta
  di mittente o destinatario (ad es. „Odbiorca: Skrytka
  pocztowa 45") veniva erroneamente riconosciuto come nome di persona.
- Un indirizzo di casella postale croata „Poštanski pretinac" dopo l'etichetta
  di indirizzo „Adresa:" (ad es. „Adresa: Poštanski pretinac
  45", anche con „br." aggiunto per il numero) veniva erroneamente
  riconosciuto come nome di persona.
- Un luogo senza ulteriore etichetta in un testo continuo norvegese (ad es. „Anna Hansen bor i Oslo") non veniva riconosciuto – il modello linguistico proprio denomina lì i luoghi per lo più con un'etichetta propria finora non associata invece del consueto „LOC".
- Una data nell'ordine ISO anno-mese-giorno con trattino o
  punto (ad es. „2024-12-31") non veniva affatto riconosciuta come
  data in alcune lingue – particolarmente evidente in lituano, dove gli scritti
  ufficiali indicano le date prevalentemente in questo ordine.
- Una partita IVA ungherese (közösségi adószám) nella forma a 11 cifre
  senza separatori, ugualmente valida ufficialmente (ad es.
  „12345678123" invece di „12345678-1-23") non veniva riconosciuta.
- Un codice fiscale polacco NIP con i separatori nel raggruppamento 3-2-2-3
  (ad es. „856-73-46-215", come è consueto sulle fatture di aziende e
  ditte individuali) non veniva riconosciuto – funzionava solo il raggruppamento
  3-3-2-2 per le persone fisiche.
- Una ragione sociale sotto l'etichetta di campo slovacca
  „Zamestnávateľ:" o „Názov zamestnávateľa:" (datore di lavoro/azienda) non veniva
  riconosciuta.
- Una ragione sociale sotto l'etichetta di campo rumena
  „Angajator:" o „Denumire angajator:" (datore di lavoro/azienda) non veniva
  riconosciuta.
- Una ragione sociale sotto l'etichetta di campo ungherese
  „Cég:" o „Munkáltató:" (azienda/datore di lavoro) non veniva
  riconosciuta.
- Una ragione sociale sotto l'etichetta di campo polacca
  „Pracodawca:" o „Nazwa firmy:" (datore di lavoro/azienda) non veniva
  riconosciuta.
- Una ragione sociale sotto l'etichetta di campo slovena
  „Podjetje:" o „Delodajalec:" (azienda/datore di lavoro) non veniva
  riconosciuta.
- Una ragione sociale sotto l'etichetta di campo croata
  „Tvrtka:" o „Poslodavac:" (azienda/datore di lavoro) non veniva
  riconosciuta.
- Un importo in denaro scritto per esteso con valuta in minuscolo (ad es.
  „500 euro") non veniva riconosciuto, funzionava solo con la maiuscola („Euro").
- Il cognome dopo „Schwager"/„Schwägerin" (cognato/a, ad es. „Der Schwager Bauer
  erhält die Erbschaft.") non veniva riconosciuto.
- In un indirizzo turco senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „34000 İstanbul İstiklal
  Caddesi No: 45") il numero civico restava non ripulito.
- In un indirizzo slovacco senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „831 01 Bratislava Hlavná
  15") il numero civico restava non ripulito.
- Un paese di nascita senza ulteriore etichetta in un campo modulo
  croato (ad es. „Zemlja rođenja: Njemačka") non veniva riconosciuto.
- Un paese di nascita senza ulteriore etichetta in un campo modulo
  lituano (ad es. „Gimimo valstybė: Vokietija") non veniva riconosciuto.
- Un paese di nascita o residenza senza ulteriore etichetta in un
  campo modulo polacco (ad es. „Kraj: Niemcy") non veniva riconosciuto.
- Una cittadinanza o luogo di residenza senza ulteriore etichetta in
  un campo modulo sloveno (ad es. „Državljanstvo: Nemčija") non
  veniva riconosciuto/a.
- Un paese di residenza senza ulteriore etichetta in un campo modulo
  norvegese (ad es. „Bosted: Tyskland") non veniva riconosciuto.
- Nuova pagina impostazioni „Notifiche" (prima una sezione in „Programma"): i tre messaggi della barra delle applicazioni (anteprima pronta, elaborazione completata, aggiornamento scaricato) hanno ora un posto proprio.
- Nuovo: il risultato può essere depositato accanto anche come file di solo testo (.txt) o con estensione .md – per l'ulteriore elaborazione in una IA o in un altro programma.
- In un'indicazione di contatto croata con l'etichetta „Osoba za kontakt"/„Kontakt osoba" (ad es. „Osoba za kontakt: Golub Marko") il nome restava del tutto non riconosciuto se il cognome era anche un sostantivo comune (Golub = „Colomba").

- In un'indicazione di contatto rumena con l'etichetta „Persoana de contact"/„Persoană de contact" (ad es. „Persoana de contact: Lup Ion") il nome restava del tutto non riconosciuto se il cognome era anche un sostantivo comune (Lup = „Lupo") e il nome molto corto e generico.

- In un'indicazione di contatto polacca con l'etichetta „Osoba
  kontaktowa"/„Osoba do kontaktu" (ad es. „Osoba kontaktowa: Wilk
  Adam") il cognome restava non riconosciuto se era anche un
  sostantivo comune (Wilk = „Lupo", Zielony = „verde").

- In un indirizzo rumeno senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „010061 București Strada
  Victoriei 30") il numero civico restava non ripulito.
- In un indirizzo serbo senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „11000 Beograd Bulevar
  Kralja Aleksandra 73") il numero civico restava non ripulito.
- In un indirizzo greco senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „104 32 Αθήνα Ερμού 15")
  il numero civico restava non ripulito.
- In un indirizzo sloveno senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „1000 Ljubljana Slovenska
  cesta 58") il CAP restava non ripulito.
- In un indirizzo lituano senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „LT-01100 Vilnius
  Gedimino pr. 9") il CAP restava completamente non ripulito.
- In un indirizzo ungherese senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „1052 Budapest Kossuth
  Lajos utca 12") il CAP restava non ripulito.
- Un cognome dopo „Erben" (eredi, ad es. „Die Erben Wagner erhielten die
  Mitteilung fristgerecht.") restava, nel contesto ereditario/successorio, quasi
  sempre non riconosciuto.
- Un cognome dopo „Geschwister" (fratelli, ad es. „Die Geschwister Bauer wohnen
  in Linz.") restava finora quasi sempre non riconosciuto – diversamente da
  „Familie"/„Ehepaar" ciò riguardava non solo cognomi omonimi di professioni (Koch,
  Bauer, Richter), ma qualsiasi cognome in questa posizione.
- Un cognome dopo „Ehepaar" o „Eheleute" (coniugi, ad es. „Das Ehepaar Koch
  zieht um.") restava non riconosciuto se era anche un
  sostantivo comune o una denominazione professionale (Koch, Bauer, Richter).
- Un comune numero d'ordine, incarico o articolo nel tipico
  schema di raggruppamento di un codice fiscale o numero di previdenza sociale
  (ad es. „030 4471 2298") veniva oscurato erroneamente come tale
  senza alcuna etichetta corrispondente.
- Un numero di documento/pratica nel formato „anno/numero progressivo" (ad es. in
  „Rechnung Nr. 4/2024/778899") veniva erroneamente oscurato dal riconoscimento dei
  numeri di telefono come numero di telefono.
- Un nome dopo „Herr"/„Frau" con una catena di titoli accademici multiparola
  davanti („Herr Dr. med. Weber", „Herr Prof. Dr. Krause") restava
  finora del tutto non protetto – finora veniva riconosciuta solo
  una singola parola di titolo tra formula di cortesia e nome.
- Un numero di protocollo giudiziario nel formato classico con sigla di
  camera/sezione („4 Ca 1523/24", „Az.: 7 O 234/25") restava finora del tutto
  non protetto – anche la consueta forma abbreviata „Az."/„Gz." non veniva riconosciuta
  accanto all'etichetta per esteso.
- Un numero di carta di credito, separato nel mezzo del suo raggruppamento a quattro
  cifre da un'interruzione di riga – ad esempio in una colonna di tabella stretta –,
  restava finora del tutto non protetto.
- Un codice fiscale, separato nel mezzo del suo raggruppamento
  da un'interruzione di riga – ad esempio in una colonna di tabella stretta
  o un campo modulo –, restava finora del tutto
  non protetto.
- Un numero di previdenza sociale, separato nel mezzo del suo raggruppamento da un'interruzione
  di riga – ad esempio in una colonna di tabella stretta –,
  restava finora del tutto non protetto, nemmeno parzialmente
  sostituito.
- Un numero civico con intervallo come „12a-14b" o „3-5" veniva sostituito solo per metà
  – la seconda parte dopo il trattino restava scoperta nel risultato.
- Un numero di telaio (FIN/VIN), separato nel mezzo dei suoi 17 caratteri da
  un'interruzione di riga, uno spazio o un trattino – ad esempio in
  una colonna di tabella stretta o un campo del libretto di circolazione –, restava
  finora del tutto non protetto.
- Una formula di apertura di lettera/e-mail come „Liebe Anna!" o „Lieber Hans" – senza
  virgola dopo il nome, la forma più frequente nelle e-mail informali – lasciava il
  nome del tutto non protetto, anche nel documento completo con
  testo continuo e formula di chiusura sotto.
- La stessa lacuna riguardava anche le formule di apertura informali di chat/e-mail „Hallo Anna!",
  „Hi Anna!", „Hey Anna!" e „Servus Anna!" senza virgola – il nome restava
  anch'esso del tutto non protetto.
- Un blocco firma puro che inizia direttamente con „MfG" o „Herzlichst"
  – ad esempio copiato dagli appunti, senza frase precedente – lasciava
  il nome sottostante del tutto non protetto.
- Un campo con più persone, ad esempio „Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)", fondeva entrambi i nomi insieme
  all'indicazione tra parentesi in un unico risultato troppo lungo – il secondo
  nome restava in parte non protetto nel risultato.
- Una via senza suffisso „-straße"/„-weg" – come è consueto in campagna,
  ad esempio „Am Marktplatz 5" o „Im Grund 12" – restava
  non riconosciuta se seguita da una riga CAP-città, ad esempio in un
  certificato di residenza: „Neue Anschrift: Am Weidengarten 17, 54295 Trier"
  perdeva completamente la via, veniva rimosso solo il CAP.
- Un nome dopo un'etichetta di campo composta con
  barra (ad es. „Name/Vorname: Bauer Klaus") non veniva in parte
  riconosciuto – un cognome ambiguo come „Bauer" restava non rilevato senza
  la prova del campo. La stessa lacuna riguardava campi combinati come
  „PLZ/Ort: 04109 / Leipzig". Lo stesso valeva per campi combinati con
  connettore per esteso invece della barra, ad esempio
  „Vor- und Nachname: Bauer Klaus" o „Nachname bzw. Vorname: …".
- Una data di nascita nella forma „Datum der Geburt: …" e una data di morte
  nella forma „Todesdatum: …" o „Datum des Todes: …" non venivano
  riconosciute – funzionavano solo „Geburtsdatum: …" e „Sterbedatum: …".
- Una data di matrimonio nella forma „Datum der Heirat: …" o „Datum der
  Hochzeit: …" non veniva riconosciuta – funzionavano solo „Hochzeitsdatum: …",
  „Heiratsdatum: …" e „Datum der Eheschließung: …", sebbene
  la data di divorzio, naturalizzazione e unione civile conoscessero già da tempo la stessa
  forma „Datum der X".
- Una data di divorzio nella forma „Datum der Scheidung: …" non veniva
  riconosciuta – funzionavano solo „Scheidungsdatum: …" e la forma verbale
  posposta, sebbene la data di naturalizzazione e unione civile conoscessero
  la stessa forma „Datum der X" fin dall'inizio.
- Una data di unione civile finora non veniva affatto riconosciuta – né con
  etichetta („Verpartnerungsdatum: …", „Datum der Lebenspartnerschaft:
  …") né nel testo continuo („… wurden am … verpartnert"). Ora viene sostituita, come
  data di nascita, matrimonio, divorzio e naturalizzazione, come proprio
  tipo di dato.
- Una data di naturalizzazione finora non veniva affatto riconosciuta – né con
  etichetta („Einbürgerungsdatum: …") né nel testo continuo („… wurde am …
  eingebürgert"). Ora viene sostituita, come data di nascita, matrimonio e
  divorzio, come proprio tipo di dato.
- Una data di divorzio finora non veniva affatto riconosciuta – né con
  etichetta („Scheidungsdatum: …") né nel testo continuo („Die Ehe wurde
  am … geschieden"). Ora viene sostituita, come data di nascita, morte e
  matrimonio, come proprio tipo di dato.
- Una data di matrimonio dopo il simbolo genealogico di matrimonio „⚭" senza etichetta
  non veniva riconosciuta, sebbene la data di nascita e di morte nella stessa riga
  tramite asterisco e croce venissero già riconosciute – ora viene riconosciuta anche la
  data di matrimonio.
- Una data di morte dopo la croce dei necrologi senza etichetta
  („*03.06.1940 †21.11.2023") non veniva riconosciuta, sebbene la data di nascita
  prima di essa tramite l'asterisco genealogico venisse già riconosciuta – ora viene riconosciuta anche la
  data di morte.
- Cognome prima del nome alla fine di una riga di oggetto/ticket con testo introduttivo
  e trattino separatore anteposti („Betreff: Reklamation - Bauer, Anna") non veniva riconosciuto
  in caso di cognome omonimo di professione – ora viene riconosciuto.
- I numeri di candidato e richiedente dopo la loro etichetta
  („Bewerbernummer: 4471829", „Antragstellernummer: 7654321") sfuggivano
  completamente al riconoscimento – ora vengono riconosciuti.
- La sostituzione non oscura più quando non c'è spazio per un
  segnaposto leggibile – un segnaposto troppo piccolo viene ora scritto più piccolo
  invece di diventare una barra vuota, finché resta comunque
  spazio. Nuovo inoltre: se un punto trovato su un'immagine (intestazione,
  sfondo di scansione) venga etichettato o solo oscurato, si può ora impostare
  indipendentemente dal resto del tipo di risultato. E un punto trovato
  su un'immagine che viene rimossa del tutto veniva etichettato come se l'immagine
  restasse – il segnaposto stava chiaro su uno sfondo mai
  oscurato, e spariva così invisibile sulla carta ora
  bianca.
- Un punto trovato su un'immagine **conservata** veniva, nella sostituzione, sempre
  oscurato in bianco e nero, indipendentemente dalla rappresentazione scelta
  (colori di categoria, arcobaleno …) – visibile come rottura tra
  etichette colorate nel testo continuo e barre nere sull'intestazione. Lo
  sfondo dell'immagine ora segue lo stesso colore del segnaposto accanto.
- Il riconoscimento del numero di identificazione del veicolo (FIN/VIN) contrassegnava
  incondizionatamente ogni codice alfanumerico di 17 cifre senza I/O/Q come
  numero di telaio – anche numeri d'ordine, di serie e chiave di licenza,
  che hanno casualmente la stessa forma. Ora conta solo con una
  parola di contesto nelle vicinanze („FIN", „VIN", „Fahrgestell", „Chassis" e sim.).
- Nei sistemi di ticket/calendario, il riconoscimento dei nomi dopo „Assigned to"/
  „Closed by" e sim. trascinava con sé la parola del campo successivo, se seguiva
  direttamente nella stessa riga senza separatore („Assigned to Max Mustermann Priority High"
  diventava „Max Mustermann Priority"). Nelle righe di intestazione dei commit Git, il
  riconoscimento dei nomi trascinava allo stesso modo la **successiva** chiave trailer, se due
  righe erano attaccate con un solo spazio invece di un'interruzione di riga
  („Author: julia bergmann Reviewed-by: …" diventava „julia bergmann
  Reviewed-by"). Entrambi i freni sono stati aggiunti.
- Il nome dopo „p.A.", „zH"/„zHd", „i.A."/„i.V." e „geb." trascinava una
  parola di reparto immediatamente successiva nello stesso risultato, se stava
  senza separatore nella stessa riga („p.A. Max Mustermann Buchhaltung"
  diventava „Max Mustermann Buchhaltung", „i.A.Max Mustermann Vertrieb" diventava
  „Max Mustermann Vertrieb"). Lo stesso freno di „Assigned to"/
  trailer Git è stato aggiunto anche qui.
- Un IBAN etichettato direttamente sopra la riga BIC, BLZ o SWIFT trascinava
  la relativa etichetta nel proprio risultato, perché „BIC" e „BLZ"
  apparivano essi stessi come un ulteriore blocco numerico – da „IBAN: DE89 …
  0130 00" e dalla riga sottostante nasceva un unico risultato
  troppo esteso, e l'etichetta della riga successiva spariva insieme
  durante la ripulitura. Ne era colpita quasi ogni coordinata bancaria con IBAN e BIC
  uno sotto l'altro.
- Il pannello dei risultati ora indica **dove** si trova un segnaposto che non riesce a
  trovare sulla pagina. Due casi finora segnalavano solo „non trovato",
  sebbene la sostituzione fosse avvenuta: se il segnaposto si trova in un testo secondario non
  visibile – ad esempio l'indirizzo di riferimento di un link, un'annotazione o
  un campo modulo –, la riga ora lo riporta come informazione propria
  („nel testo secondario"), e il clic lo spiega. E se il segnaposto è stato
  scritto abbreviato per mancanza di spazio („[N382]" invece di „[NAM382]"), il
  clic sulla riga lunga ora salta al punto della forma abbreviata e indica
  la rinomina; l'associazione collega appositamente le due righe tra
  loro.
- Se lo stesso valore sostitutivo compare più volte nel documento, ogni ulteriore
  clic sulla riga del pannello salta in ciclo al punto trovato successivo – anche oltre
  i confini di pagina; la riga di stato conta insieme („Punto 2 di 4"), e il
  punto appena raggiunto ha un riquadro più marcato degli altri. E se
  un segnaposto si trova solo nell'elenco dei risultati, ma da nessuna parte nel documento
  (perché il punto è confluito in una sostituzione sovrapposta), la
  riga di stato lo dice ora, invece che il clic resti muto senza effetto.
- Un nome abbreviato dopo „an" o „für" viene ora riconosciuto in modo affidabile come
  nome – „Überweisung an M. Wagner" e „Rechnung für M. Wagner"
  finora restavano spesso non ripuliti, mentre lo stesso nome con un'altra
  etichetta davanti (ad es. „Zahlungsempfänger:") veniva già trovato.
  Ne erano colpite soprattutto le righe di estratto conto e registrazione contabile.
- „Angeklagter"/„Angeklagte"/„Beschuldigter"/„Beschuldigte" (imputato/a) contano ora come
  campo nome: se un nome negli atti di procedimento penale stava direttamente dopo
  una di queste etichette, finora non veniva affatto riconosciuto per circa la metà
  dei nomi verificati – né nome né cognome.
- Il punto cliccato dal pannello dei risultati viene ora incorniciato in blu invece di
  evidenziato in giallo – sulle superfici colorate del semaforo di verifica il giallo dei
  risultati di ricerca non era riconoscibile. Inoltre il clic trova ora anche
  valori sostitutivi composti da più parole (nomi inventati, numeri mascherati): finora
  restava senza effetto su tali righe, perché il punto trovato veniva cercato solo parola
  per parola.
- Genitori adottivi, affidatari e acquisiti („Adoptivvater", „Pflegemutter",
  „Stiefvater" e altro) vengono ora riconosciuti come campo nome, prima il nome
  sfuggiva non ripulito
- Tabelle ed elenchi ricchi di numeri non vengono più erroneamente scartati:
  se un numero breve (ad es. una parte del numero cliente letta come
  numero di telefono) veniva sostituito, la verifica finale segnalava la stessa
  sequenza di cifre come dato residuo anche quando si trovava altrove solo per
  caso in un numero del tutto diverso – e allora non forniva
  alcun risultato. Un numero ora conta come residuo solo dove
  compare come numero a sé stante.
- Atti di stato civile: „Vater:"/„Mutter:" viene ora riconosciuto come campo nome, prima il nome del genitore sfuggiva non ripulito
- Ulteriori ruoli familiari („Pate", „Großvater/-mutter", „Ehepartner",
  „Lebenspartner", „Onkel", „Tante") vengono ora riconosciuti come campo nome,
  prima il nome sfuggiva non ripulito
- Il codice bancario tedesco (Bankleitzahl) viene ora riconosciuto anche nel raggruppamento ufficiale
  ("370 400 44", "370.400.44", "370-400-44", "370/400/44"), non più solo
  come otto cifre consecutive.
- Il numero di previdenza pensionistica tedesco viene ora riconosciuto anche con punto,
  trattino o barra tra i cinque blocchi
  ("65-170839-J-08-8", "65.170839.J.08.8"), non più solo con spazio.
- La finestra principale compare più velocemente: le librerie di riconoscimento
  (Presidio con la base dei modelli linguistici) venivano finora già caricate
  durante la costruzione della finestra – su Windows circa quattro secondi, prima ancora che
  qualcosa fosse visibile. Ora si caricano completamente in background; il
  pulsante „Ripulisci" diventa disponibile, come prima, solo quando tutto è pronto.
- I documenti Office con molte immagini o video vengono scritti più velocemente:
  i media già compressi vengono salvati nel pacchetto risultato invece di
  essere compressi inutilmente una seconda volta – finora ciò non risparmiava alcun byte
  e rendeva i JPEG semmai più grandi.
- Fogli di calcolo e altri documenti composti da molte piccole
  unità di testo vengono verificati più velocemente: il riconoscimento linguistico ora elabora
  tutte le celle e i paragrafi di un documento in un unico passaggio invece
  che singolarmente – con risultati dimostrabilmente identici (400 celle: da circa
  4,7 a 2,5–3,5 secondi).
- Le pagine PDF simili a elenchi (indici, liste di posizioni) sono più veloci al
  inserimento dei segnaposto: la ricerca dello spazio per
  etichetta finora scorreva su tutte le parole della pagina – ora solo
  sull'intorno di riga, con risultato dimostrabilmente identico (su una
  pagina con 300 etichette circa sedici volte più veloce).
- I documenti ricchi di immagini risparmiano diversi passaggi di lavoro superflui per immagine:
  il conteggio di volti e codici sulle pagine PDF non decodifica più
  l'immagine di pagina due volte, la verifica dei metadati non decifra più
  affatto un'immagine pulita, le immagini pixelate vengono scritte con la
  compressione PNG normale invece della più lenta (stessa
  dimensione, un terzo del tempo), e senza filigrana impostata
  viene evitata l'inutile riscrittura dell'intero PDF alla fine.
- I PDF scansionati con riconoscimento testo attivato terminano decisamente più
  velocemente: ogni pagina veniva finora renderizzata due volte a piena risoluzione
  (una per leggere, una per rasterizzare) – l'immagine viene ora
  riutilizzata. E su Windows/Linux il riconoscimento testo legge le
  strisce di una grande scansione in un unico passaggio invece che con un proprio
  avvio di programma per ogni striscia.
- I documenti grandi vengono ripuliti decisamente più velocemente: il confronto dei
  valori già trovati cresceva finora con il numero dei risultati (un
  blocco di testo di 64 KB costava, alla fine di un file grande, circa un
  secondo solo per questo, ora un sessantesimo), e la ricerca delle forme giuridiche
  aziendali scorreva con tutte le ~280 forme del catalogo su ogni punto del testo
  (ora circa venti volte più veloce, con risultati dimostrabilmente identici).
- Un nome direttamente dopo „Beste Grüße"/„Beste Wünsche" senza testo
  o punteggiatura precedenti non veniva affatto riconosciuto – un puro
  blocco firma senza testo continuo davanti faceva sparire il nome
  senza lasciare traccia.
- Un campo indirizzo all'inizio del documento con un cognome omonimo di
  professione („Bauer Anna", „Koch Stefan" come prima riga sopra via e
  città) restava finora in parte non riconosciuto o veniva classificato come indicazione
  di luogo invece che come persona – senza frase precedente mancava al modello linguistico
  la struttura sintattica che altrimenti fa riconoscere „Bauer" come nome e non come professione.
- Un nome dopo la marca di firma „gez." con un cognome omonimo
  di professione prima del nome („gez. Bauer Anna" alla
  fine di un provvedimento o di una sentenza) restava finora riconosciuto in modo incompleto –
  veniva trovato solo il nome, il cognome spariva senza lasciare traccia.
- Un nome direttamente dopo un numero cliente, numero di contratto o
  identificativo simile senza riga propria („Vertragsnummer 55219 Bauer
  Anna", „Kundennr. 4711 Bauer Anna") restava finora, in caso di cognome omonimo
  di professione, riconosciuto in modo incompleto o per nulla.
- L'icona nella barra dei menu di macOS è ora un template che si adatta,
  come le icone vicine, a modalità chiara e scura – con le due
  barre ritagliate resta comunque riconoscibile come Maskuro. Se il
  sorvegliante degli appunti è in esecuzione, ciò è indicato da un punto separato sulla
  punta dello scudo.
- Un clic nel pannello dei risultati porta ora anche in modalità di anonimizzazione
  al punto trovato: cambia pagina, scorre fino all'immagine, evidenzia in giallo. Finora
  il clic restava lì senza effetto, perché considerava ancora i segnaposto
  privi di numero – da quando ogni punto trovato porta il proprio numero, il
  punto è univoco. Solo per il segnaposto effettivamente privo di numero,
  la riga di stato continua a spiegare perché non è possibile determinare una destinazione.
- Il primo salvataggio nell'editor di rifinitura (Ctrl+S o il
  pulsante a forma di dischetto) chiede ora il percorso, come „Salva con nome …" –
  precompilato con la cartella dell'originale e il nome del risultato. Finora
  il file finiva senza avviso accanto all'originale. Chi ha già scelto in precedenza
  il percorso di destinazione tramite la riga di stato non viene richiesto di nuovo;
  ogni ulteriore salvataggio continua a scrivere, come prima, lo stesso file.
- Se la verifica di sicurezza prima del salvataggio segnala un punto sospetto,
  „Torna alla verifica" ora porta lì: il primo punto trovato scorre nella vista
  ed è incorniciato in rosso, la riga di stato lo indica. Finora si restava soli
  con numero di pagina e coordinate del punto. Dalla finestra principale, per questo
  si apre l'editor nel punto in questione. Anche in caso di segnalazione di un numero di
  pagina diverso, il pulsante ora porta lì – alla prima pagina che
  esiste solo in uno dei due documenti.
- Chi commuta l'anteprima su „Affiancate in due colonne" ottiene ora
  automaticamente una finestra in cui entrambe le corsie stanno – finora
  si comprimevano nella vecchia larghezza finché non si trascinava da soli. Viene
  allargata al massimo fino al bordo dello schermo e mai ristretta indietro; una
  larghezza trascinata manualmente resta come impostata.
- Cognome e nome in colonne di tabella separate (ad es. „Cognome | Nome"
  in una conferma di iscrizione o un'esportazione CSV) restavano scoperti – ogni
  cella singolarmente appariva al riconoscimento come una parola qualsiasi senza
  contesto di nome. Vengono ora riconosciuti.
- Cognome e nome sul retro di una patente di guida in formato card UE restavano
  scoperti – lì si trovano dietro i codici di campo ufficiali „1." e „2."
  invece che dietro una parola tedesca, e proprio questo li lasciava non riconosciuti.
  Vengono ora riconosciuti quando accanto si trova il numero della patente (codice campo „5.").
- Il nome del titolare del veicolo sul certificato di immatricolazione restava
  scoperto – si trova dietro il codice di campo ufficiale „C.1.2" invece che dietro
  una parola tedesca come „Vorname", e proprio questo lo lasciava non riconosciuto.
  Cognome e nome sotto i codici di campo C.1, C.1.1 e C.1.2 vengono
  ora riconosciuti.
- La prima riga dell'area leggibile automaticamente (MRZ) su passaporto o
  carta d'identità restava scoperta – porta il nome nel formato
  „COGNOME<<NOME" e sfuggiva completamente anche con il nuovo riconoscitore MRZ
  per la riga della cifra di controllo. Un risultato ora conta solo se
  proprio accanto si trova una seconda riga MRZ valida secondo la cifra di controllo – la
  riga del nome stessa non ha una propria cifra di controllo.
- La seconda riga dell'area leggibile automaticamente (MRZ) su passaporto o
  carta d'identità restava completamente non riconosciuta – contiene numero di passaporto,
  data di nascita e di scadenza in chiaro, ma non corrispondeva a nessun
  riconoscitore esistente. Un riconoscitore proprio ora verifica le quattro
  cifre di controllo ICAO.
- Una targa senza alcuno spazio rispetto all'etichetta restava scoperta –
  „KennzeichenM-AB1234" o „KFZ-KennzeichenM-AB1234" non venivano affatto
  riconosciute, perché la verifica della targa sottostante richiede prima della targa
  un carattere non alfanumerico. Riguardava indicazioni di veicolo in cui non c'era
  spazio tra la parola di campo e la targa.
- Un numero di telefono senza alcuno spazio rispetto all'etichetta restava scoperto –
  „Handynummer0171/2345678" o „Tel0171/2345678" non venivano affatto
  riconosciuti, perché la verifica sottostante del numero di telefono richiede prima del numero uno
  spazio o un segno di punteggiatura. Riguardava indicazioni di contatto in cui
  non c'era spazio tra la parola di campo e il numero.
- Un cognome da nubile dopo l'abbreviazione „geb." non veniva affatto riconosciuto –
  „Julia Bergmann (geb. Weber)" trovava solo „Julia Bergmann", il punto in
  „geb." faceva sì che il modello linguistico ignorasse completamente il nome successivo.
  Riguardava dati personali con cognome da nubile tra parentesi o dopo virgola.
- Il nome prima di un soprannome tra virgolette restava scoperto quando
  formula di cortesia e titolo stavano insieme davanti – „Herr Dr. Klaus "KP" Peters"
  dava solo „Peters", „Klaus" restava leggibile. Riguardava firme
  e dati di contatto con titolo e soprannome.
- Un nome dopo la forma abbreviata senza punto „zH"/„zHd" (all'attenzione di) non veniva
  affatto riconosciuto – diversamente da „z.Hd." con punto, la mancante
  struttura sintattica trascinava via il nome. Riguardava indirizzi senza punto nell'
  abbreviazione.
- Un nome dopo „p.A." (presso l'indirizzo di) non veniva affatto riconosciuto – il punto
  nell'abbreviazione faceva sì che il modello linguistico saltasse completamente il riconoscimento del nome.
  Riguardava fatture e candidature con indirizzo collettivo.
- Un nome dopo „i.A."/„i.V." (per incarico/in rappresentanza) attaccato senza punto non veniva affatto riconosciuto, ad es. „i.A.Robert Lang" senza
  spazio – lo stesso errore di struttura sintattica di „p.A.". Riguardava
  righe di firma e firme e-mail di casi di rappresentanza.
- Un semplice elenco di presenze con trattino puntato senza alcun'altra
  indicazione („- Max Mustermann", anche con punto a fine riga) perdeva tutti i
  nomi allo stesso freno che in realtà dovrebbe proteggere solo elenchi oggettivi come
  „- Farbe: Blau". Tali elenchi vengono ora riconosciuti.
- I file che non si lasciavano più ripulire si lasciano di nuovo
  ripulire. Un valore già sostituito dal riconoscimento poteva essere ritrovato in
  una propria marca già sostituita come „[SVNR1]"
  – la verifica finale scartava allora un file impeccabilmente ripulito. Inoltre
  un riferimento telefonico in una tabella CSV viene ora rimosso anch'esso, e chi
  limita la ricerca a singoli tipi la ottiene ora uniforme in tutto il
  documento – anche nel testo alternativo di un'immagine, un'
  intestazione Excel, un elenco a discesa o un attributo HTML.
- Un nome dopo l'intestazione e-mail „To:" (o „To" senza due punti)
  non veniva riconosciuto, perché un modello linguistico estraneo leggeva l'intera riga come
  un unico risultato non appariscente, inghiottendo completamente il nome al suo interno
  – diversamente da „Cc:", „Bcc:" o „From:" davanti allo stesso
  nome. Un nome dopo „To" viene ora trovato in modo affidabile.
- La data di matrimonio non si poteva trattare come data nelle regole personalizzate
  („sposta" veniva rifiutato con „esiste solo per le indicazioni di data"),
  mancava nell'assegnazione di gruppo dei tipi di risultato – per cui non si poteva
  disattivare tramite le marche „Cosa viene cercato" – e otteneva, invece di
  una sigla breve come per la data di morte, il testo completo come segnaposto.
  Corretto per tutte e sei le tabelle di sigla/etichetta.
- Un valore deliberatamente deselezionato nell'anteprima poteva comunque essere oscurato
  in un altro punto: se ad esempio si deselezionava un indirizzo e-mail,
  l'indirizzo stesso restava sì al suo posto, ma la sua parte locale senza dominio veniva
  sostituita non appena coincideva con il nome utente derivato di una persona
  selezionata altrove („anna.musterfrau@beispiel.de" accanto a „Anna
  Musterfrau"). Un testo deselezionato resta ora tabù in tutto il documento,
  indipendentemente dal tipo di risultato da cui proviene.
- Una data di nascita restava non riconosciuta quando un libro di famiglia o
  un estratto di stato civile la riportava sotto un'intestazione comune con il
  luogo di nascita („Geburtsdatum, Geburtsort: 19.11.1982, Steyr") – la
  seconda parola di campo tra „Geburtsdatum" e la data faceva sì che il
  riconoscimento fallisse completamente fino ad allora.
- Un numero di telefono già riconosciuto restava leggibile nella sua forma
  di conferma abbreviata, se altrove nello stesso documento veniva menzionato solo con le
  ultime quattro cifre („erreichbar unter der Nummer
  ...5678", „Rückruf unter ...5678") – la stessa forma di IBAN e
  carta di credito.
- Un numero di carta di credito già riconosciuto restava leggibile nella sua forma
  di conferma abbreviata, se altrove nello stesso documento
  veniva menzionato solo con le ultime quattro cifre („Ihre Kreditkarte
  endet auf ...0366") – la stessa forma consueta nelle conferme di pagamento
  dell'IBAN.
- Un IBAN già riconosciuto restava leggibile nella sua forma di conferma
  abbreviata, se altrove nello stesso documento veniva menzionato solo con le
  ultime quattro cifre („Die IBAN endet auf ...3201") – una
  forma consueta nelle e-mail di conferma.
- Un oratore in una chat o in un verbale di riunione restava non riconosciuto se
  davanti al suo nome c'era una formula di cortesia („Herr Bauer: …", „Frau Koch: …") –
  e ciò colpiva spesso anche la riga dell'oratore successivo nello stesso verbale,
  perché restavano troppo poche righe riconosciute per classificare il documento
  come verbale.
- Una data di nascita restava non riconosciuta quando la parola di campo „geboren"
  stava DOPO la data invece che prima („Das Kind wurde am 14.01.2026 geboren") – così
  formula ad esempio un certificato di congedo parentale o di tutela della maternità
  la data di nascita del figlio. I modelli finora presupponevano sempre la parola di campo
  prima della data.
- Un'etichetta di modulo con un'emoji di reazione o un segno di spunta subito prima
  („Ansprechpartner 😊:", „Kontaktperson ✓:") non veniva più riconosciuta come
  etichetta, e il nome sotto o dopo restava di conseguenza in parte
  riconosciuto solo parzialmente (ad es. solo il cognome in „Mayer
  Roman").
- La stessa lacuna riguardava anche i dati particolarmente meritevoli di protezione ai sensi dell'art. 9
  GDPR (religione, salute, sindacato): un'emoji di reazione subito
  prima del separatore o dell'interruzione di riga („Konfession 😊: römisch-katholisch")
  faceva fallire completamente l'etichetta, e il dato restava
  del tutto non riconosciuto.
- Un indirizzo con nome composto da trattino nella città (ad es. „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") perdeva completamente il
  CAP, sebbene la città stessa venisse riconosciuta e oscurata – su un
  libretto di circolazione o una lettera restava così il
  CAP leggibile.
- Una colonna di tabella senza spaziatura tra colonne (vero estratto testo PDF) poteva,
  sotto una colonna di nomi, oscurare erroneamente anche due maiuscole
  casualmente adiacenti come persona, ad esempio due nomi di luogo in
  una riga di dati; ora ciò avviene solo se nessun altro
  risultato nello stesso punto riconosce già qualcos'altro.
- La stessa colonna di nomi oscurava, nella stessa forma di riga, anche due
  parole sconosciute al modello linguistico (ad es. „Frontend Backend", „Turbo
  Modul") erroneamente come persona, perché lì nessun altro risultato
  attivava il freno; ora richiede in aggiunta che almeno una delle
  due parole venga letta dal modello linguistico stesso come nome proprio.
- Il numero di previdenza pensionistica tedesco nel suo raggruppamento ufficiale
  completo (ad es. „65 170839 J 08 8" – così come si trova su
  tesserino di previdenza sociale e busta paga) non veniva riconosciuto e
  restava nell'originale; venivano riconosciute solo la grafia compatta
  e la forma raggruppata solo fino alla lettera.
- Il codice fiscale tedesco nella sua grafia ufficiale
  (raggruppamento 2-3-3-3, ad es. „48 836 075 988" – così come si trova su ogni
  vero avviso fiscale e ogni comunicazione dell'Ufficio federale centrale
  delle imposte) non veniva affatto riconosciuto e restava nell'originale; era coperto solo il
  raggruppamento più raro 3-3-3-2.
- Il codice fiscale del Nordreno-Vestfalia (ad es. „221/5147/0815", con
  secondo gruppo di quattro cifre invece di tre) non veniva affatto
  riconosciuto negli avvisi fiscali e restava nell'originale –
  ogni altro Land era già coperto.
- Nei contratti di lavoro, un nome dopo l'etichetta
  „Arbeitgeber:" veniva completamente ignorato non appena il cognome era anche una
  parola comune (ad es. „Bauer Anna") – „Arbeitgeber" figura nell'elenco
  sia come etichetta di nome sia come etichetta aziendale, e l'assegnazione
  aziendale sovrascriveva quella del nome.
- In un'intestazione di contratto di locazione con le etichette „Vermieter:"/„Mieter:"
  un cognome che è anche una parola comune (ad es.
  „Bauer") veniva ignorato – restava riconosciuto solo il nome. Le
  parti locatarie numerate („Mieter 1:", „Mieter 2:") erano inoltre colpite, anche
  con nomi privi di questa ambiguità.
- In un verbale giudiziario con le etichette „Zeuge:"/„Kläger:"/
  „Beklagter:" (anche numerato, „Zeuge 1:", „Zeuge 2:") un
  cognome che è anche una parola comune (ad es. „Bauer") veniva parimenti
  ignorato – restava riconosciuto solo il nome.
- Nel certificato di eredità, procura, procedimento ingiuntivo e contratto di
  compravendita, un cognome che è anche una parola comune (ad es. „Bauer") veniva ignorato
  dopo etichette come „Erblasser:", „Erbe:", „Vollmachtgeber:",
  „Bevollmächtigte:r", „Antragsgegner:", „Schuldner:", „Gläubiger:",
  „Käufer:", „Verkäufer:", „Vermächtnisnehmer:" o
  „Testamentsvollstrecker:" – in parte restava riconosciuto solo il nome, in
  parte l'intero nome andava perso.
- In un elenco multiparte prima del separatore di intestazione „./." (ad es.
  „Sand, Werner und Huber, Anna ./. Wechsler, Martina") la prima
  parte restava non mascherata – veniva riconosciuta solo la parte immediatamente
  adiacente a „./.".
- Nel separatore di intestazione „./." (ad es. „Sand./.Wechsler") il nome
  dopo il segno veniva completamente ignorato se lì non c'era spazio
  – il riconoscimento funzionava solo con spazio prima e dopo.
- Il cognome „Wahr" veniva completamente ignorato quando stava da solo
  (ad es. „Frau Wahr bearbeitet Ihren Vorgang.") – la parola si trova per caso
  anche nell'elenco delle comuni parole tedesche, che altrimenti filtra i risultati
  di nome da frasi come „Das ist wahr.".
- Cognomi come „Los", „Weit", „Rund" o „Hoch" venivano completamente
  ignorati quando stavano da soli (ad es. „Herr Hoch übernahm die
  Leitung.") – tutte e quattro le parole si trovano per caso anche nell'elenco
  delle comuni parole tedesche, che altrimenti filtra i risultati di nome da frasi come
  „Rund einhundert Gäste kamen zur Feier.".
- Cognomi come „Ganz" o „Recht" venivano completamente ignorati quando
  stavano da soli (ad es. „Herr Ganz unterschrieb den Vertrag.") – entrambe le
  parole si trovano per caso anche nell'elenco delle comuni parole tedesche,
  che altrimenti filtra i risultati di nome da frasi come „Ganz genau, das stimmt.".
- Un campo modulo con un asterisco o una cifra di nota a piè di pagina in apice
  subito dopo l'etichetta (ad es. „Konfession*:
  römisch-katholisch" o „Religionszugehörigkeit¹: evangelisch") non veniva
  riconosciuto e restava in chiaro – funzionava solo la forma senza questo
  segno.
- Lo stesso campo restava ancora in chiaro se addirittura due
  segni di nota a piè di pagina stavano dopo l'etichetta (ad es. „Konfession**:
  römisch-katholisch" o „Gewerkschaft¹²: ver.di").
- Un numero di versione come „Softwareversion 4.2.1.19" o „Firmware Build
  2.0.4.11" non viene più oscurato erroneamente come indirizzo IP. Lo stesso
  vale ora per numeri di documento e pratica come „Rechnungsnummer
  10.20.30.40" o „Bestellnummer 7.8.9.10".
- Due IBAN direttamente uno sotto l'altro (ad es. il proprio e quello di un
  partner commerciale estero nell'intestazione della fattura) non venivano più
  riconosciuti entrambi – il secondo restava inosservato.
- Un IBAN etichettato a volte trascinava con sé la parola successiva nella frase
  ("Bankverbindung AT61 … wird belastet" veniva oscurato fino a comprendere
  "wird"), non appena la parola successiva era scritta in minuscolo – il resto in chiaro
  accanto restava intatto.
- Gli indirizzi del Liechtenstein vengono ora riconosciuti („FL-9490 Vaduz"), come
  già in precedenza quelli tedeschi, austriaci e svizzeri.
- Numero di passaporto e numero del documento vengono ora riconosciuti dopo la loro
  etichetta e rimossi (ad es. „Reisepassnummer: C01X00T471").
- Il numero del titolo di soggiorno e del certificato di residenza vengono ora riconosciuti
  dopo la loro etichetta e rimossi.
- Un identificativo dopo la sua etichetta viene ora riconosciuto anche quando
  un trattino lungo separa invece dei due punti (ad es. „Kundennummer –
  K903944").
- Una coordinata bancaria etichettata come „IBAN" o „Kontonummer" viene ora
  riconosciuta anche quando un trattino lungo separa invece dei due punti.
- Un nome dopo un'etichetta come „Kontaktperson (Vertrieb)" o
  „Sachbearbeiter/in" viene ora riconosciuto anche con aggiunta tra parentesi o
  desinenza con barra neutra rispetto al genere.
- Anche la stessa forma di genere con asterisco („Sachbearbeiter*in") viene ora
  riconosciuta.
- Un nome dopo un'etichetta viene ora riconosciuto anche quando un
  segno di uguale separa invece dei due punti (ad es.
  „Ansprechpartner = Mayer Roman" o „Kontaktperson=Mayer Roman"), come è
  consueto nei file di configurazione o nelle intestazioni CSV. Se più coppie
  etichetta-valore di questo tipo si trovano separate da punto e virgola in una riga, viene
  riconosciuto solo il primo valore invece dell'intera riga rimanente.
- Una coppia di coordinate GPS dopo la parola „Koordinaten" viene ora riconosciuta
  in modo affidabile (ad es. „Koordinaten: 48.2082, 16.3738") – la parola aveva la
  forma di flessione sbagliata nel catalogo interno.
- Un identificativo dopo la sua etichetta (numero cliente, numero di contratto,
  numero di protocollo, numero della carta d'identità e circa cento altre parole di campo)
  non veniva più riconosciuto non appena l'etichetta non era esattamente nella
  combinazione di maiuscole/minuscole memorizzata – „kundennummer:" in un'
  e-mail o „KUNDENNUMMER:" in un'intestazione di modulo restavano intatti.

### Neu

- **I valori sostitutivi realistici sono ora un esempio scelto consapevolmente
  invece di un'impostazione predefinita.** La tabella delle eccezioni nella scheda „Segnaposto" inizia
  vuota. Un nuovo pulsante inserisce lì, a richiesta, valori falsi plausibili per nome,
  luogo, indirizzo, organizzazione, e-mail, telefono, interno e IBAN. Esso
  lascia espressamente gli importi in denaro al segnaposto numerato; la strategia
  „inventare" resta comunque selezionabile manualmente per i singoli tipi.
- **Il livello IA può usare la scheda grafica.** Su Windows si può a tale scopo
  scaricare un pacchetto aggiuntivo di poco meno di 17 MB; da quel momento il livello IA calcola
  su una scheda grafica adatta molto più velocemente che sul processore.
  Chi non ne ha una o non scarica nulla continua a lavorare invariato – solo
  più lentamente. Su macOS l'accelerazione è comunque già integrata.
- **Due nuove notifiche tramite l'icona nella barra delle applicazioni**: quando l'
  anteprima è pronta per la revisione prima della sostituzione e quando un'
  elaborazione è terminata. Entrambe sono attive per impostazione predefinita e si possono, sotto
  *Impostazioni → Programma → Notifiche* disattivare singolarmente.

### Modificato

- **Numero della carta d'identità e della patente vengono ora riconosciuti**, se
  la loro etichetta li precede („Personalausweisnummer: …",
  „Führerscheinnummer: …") – finora entrambi sfuggivano a ogni riconoscimento.
- **Maskuro ora segue i temi ad alto contrasto di Windows.** Chi ne ha attivato uno sotto
  *Impostazioni → Accessibilità → Temi ad alto contrasto*
  lo otteneva finora ovunque tranne che qui: Maskuro imponeva poi i propri
  colori. Ora resta al tema del sistema – finestra,
  liste, zona di rilascio, registro e colori di stato. Il semaforo colorato di verifica in
  anteprima e nella finestra di rifinitura viene lì deliberatamente omesso; ciò che indica
  compare comunque da tempo accanto come segno e come parola.
- **Il bisogno di verifica non è più indicato solo dal colore.** Rosso, arancione e
  verde sono quasi ugualmente chiari – chi soffre di daltonismo rosso-verde vedeva,
  in anteprima e nel pannello dei risultati, un elenco senza differenze, e ciò riguarda circa
  un uomo su dodici. Ogni riga porta ora inoltre un segno che
  si distingue nella forma: ▲ verificare per primo, ● verificare, ○ ben documentato,
  ◆ senza valutazione. La descrizione breve lo indica anche a parole, e un
  lettore di schermo lo legge ad alta voce.
- **Alt apre di nuovo i menu come al solito.** La barra dei menu non aveva scorciatoie
  da tastiera: chi non usa il mouse doveva percorrere ogni menu con le frecce.
  Ora ogni voce porta una lettera sottolineata –
  Alt+D per „Datei", da lì B per „Beenden" –, e questo in tutte le
  lingue dell'interfaccia.
- **Gli elementi di comando dicono di nuovo a un lettore di schermo a cosa servono.**
  Nella finestra di rifinitura, nella finestra delle regole, nel registro, negli elenchi di parole,
  nella guida, nella scansione di ricerca e in altre cinque finestre, elenchi,
  campi di ricerca, elenchi a discesa e regolatori venivano finora annunciati solo come „albero" o
  „campo combinato" – senza dire di cosa. Circa quaranta punti portano
  ora un nome. (La finestra principale era in ordine da agosto; le
  finestre aggiunte in seguito non avevano mai seguito questo passo.)
- **Chi usa la tastiera vede ovunque dove si trova.** Ai
  regolatori del bisogno di verifica, alla casella di controllo e al pulsante „mai più" dell'
  anteprima, alle intestazioni di tipo al suo interno, al pannello delle pagine della
  finestra di rifinitura e alla barra laterale delle impostazioni mancava il
  riquadro che il sistema pone altrimenti attorno all'elemento di comando raggiunto.
- **Una dimensione carattere di sistema maggiore non taglia più nulla.** Chi imposta oltre
  il 175% sotto *Accessibilità → Dimensione testo* perdeva finora la fine
  delle etichette nella sorveglianza cartelle e nei campi delle scorciatoie
  da tastiera. L'elenco dei capitoli della guida troncava i nomi lunghi dei capitoli già con
  carattere normale; ora li va a capo e indica il nome
  completo nella descrizione breve.

- **Il riconoscimento è diventato decisamente più veloce.** Il riconoscitore per
  identificativi etichettati („Kundennummer: K903944") verificava finora per
  ogni sezione di testo oltre 1200 pattern singoli in sequenza – era la voce
  singola più pesante nel tempo di riconoscimento, a ogni paragrafo e ogni cella di tabella.
  Ora è un unico pattern con lo stesso risultato: nel corpus di misurazione
  non cambia nemmeno un risultato, il livello base per sezione di testo diventa
  circa tre-quattro volte più veloce.
- **La finestra compare subito all'avvio.** Finora la finestra principale caricava
  gli strumenti linguistici completi prima ancora di mostrarsi – circa
  quattro secondi di tempo cieco a ogni avvio. I modelli si caricano ora, come
  previsto, in background, mentre la finestra è già visibile; il
  pulsante Ripulisci diventa disponibile, come prima, solo quando tutto è pronto. Anche
  le semplici chiamate informative da riga di comando (ad es. `--version`) rispondono
  ora subito invece che dopo diversi secondi.
- **Le immagini vengono lette una sola volta con il riconoscimento linguistico
  automatico.** Finora, con l'impostazione predefinita
  „Lingua: automatica", il riconoscimento del testo passava due volte sulla stessa immagine – una per
  l'ipotesi della lingua, una per la verifica vera e propria. File immagine,
  immagini negli appunti e la finestra di testo terminano così circa due volte più
  velocemente; con il riconoscimento testo disattivato, la lettura che finora comunque
  girava inosservata viene completamente eliminata.
- **Pagine web salvate ed e-mail vengono ripulite più velocemente.** I
  valori negli attributi HTML, nei commenti e nei blocchi di dati incorporati
  venivano finora riconosciuti singolarmente – una pagina comunale con centinaia
  di etichette poneva centinaia di domande singole al riconoscimento. Ora
  vengono raccolti e riconosciuti una sola volta per ciascun valore diverso;
  nel corpus di misurazione non cambia alcun risultato, .html e .eml sono circa un
  terzo più veloci.
- **Anche i dati secondari di tabelle e presentazioni vengono riconosciuti in
  blocco.** Testi alternativi, stringhe di formula, etichette di grafici,
  commenti, cache pivot e proprietà del documento ponevano una
  propria domanda di riconoscimento per ciascun valore – una cartella con migliaia di righe pivot
  altrettante migliaia. Ora gira un'unica scansione raccolta sui
  valori diversi, e la passata finale di rincalzo gira solo
  quando dal testo continuo sono effettivamente arrivati nuovi valori.
  Nel corpus di misurazione non cambia alcun risultato.
- **I PDF ricchi di moduli vengono ripuliti più velocemente.** Campi, note,
  segnalibri e riferimenti ripetono gli stessi valori in massa
  („Off" su ogni casella di spunta, lo stesso autore su ogni annotazione) –
  ognuno finora poneva la propria domanda di riconoscimento. Per ogni esecuzione un
  valore viene ora riconosciuto una sola volta; sostituzione e passata di
  coerenza continuano invariate per ogni punto.
- **I file di tabella grandi (.csv/.tsv) vengono ripuliti decisamente più
  velocemente.** Le quattro passate di tabella scomponevano finora ciascuna
  lo stesso file da sé carattere per carattere in celle (con 40 MB circa 30 s
  di lavoro aggiuntivo); ora la scomposizione gira una sola volta. Il riconoscimento delle
  intestazioni di colonna (colonne di data di nascita e numero di matricola) pone, invece di una domanda per
  cella, una domanda raggruppata – con risultati identici circa venti volte
  più veloce. E l'aggregazione delle colonne di nome di grandi elenchi del personale
  non è più quadratica nel numero di righe.
- **Il pannello degli indicatori non blocca più la finestra.** L'apertura
  degli indicatori leggeva prima l'intero testo di molti file grandi e
  bloccava così la finestra per diversi secondi. Il calcolo gira ora in
  background; il pannello si apre subito e riporta i numeri in seguito.
- **Il rapporto della scansione di ricerca non blocca più la finestra.** Dopo la
  scansione di molte migliaia di file, la cartella comune veniva ricalcolata per ogni
  file interessato; nelle grandi scansioni la finestra restava bloccata per
  decine di secondi. Il rapporto ora compare subito.
- **I PDF con riconoscimento testo vengono verificati più velocemente.** Ogni pagina
  veniva convertita inutilmente due volte in formato PNG durante il controllo incrociato;
  ora viene passata l'immagine già disponibile. Il risultato resta invariato, solo la verifica
  procede più speditamente.
- **Le annotazioni con sfumatura su immagini grandi non si inceppano più.** Nel
  trascinare le maniglie di un'annotazione con sfumatura, la sfumatura veniva
  finora ricalcolata punto per punto – su uno screenshot grande un
  visibile incepparsi. Il risultato è lo stesso, solo senza la pausa.

### Risolto

- **La croce per rimuovere un file dall'elenco è di nuovo una
  semplice X.** Il nuovo strumento dell'editor „Rimuovi" aveva usato per errore
  lo stesso identificativo di icona e mostrava così la sua croce rossa con
  linea di testo tratteggiata anche in ogni riga di file. Entrambe le azioni
  hanno ora nomi di icona separati e mantengono ciascuna la propria
  rappresentazione corretta.
- **I dati composti da più parti vengono riconosciuti nei PDF anche oltre
  un'interruzione di riga visibile.** Maskuro legge il testo di pagina generato
  geometricamente anche come vista di testo continuo con lo stesso offset. Ciò vale per tutti
  i riconoscitori del livello base e alto, nonché per i pattern personalizzati, non solo per il
  primo caso visibile „Diabetes mellitus Typ 2". Righe vuote e confini
  riconosciuti di tabella o sezione restano confini rigidi; i punti trovati
  continuano a combaciare esattamente con le parole da oscurare.
- **L'esempio in „Pseudonimizza" si contraddiceva da sé.** La frase
  prometteva „stessa persona, stesso numero" e mostrava poi due
  numeri diversi – esattamente l'immagine corretta per „Anonimizza".
  Entrambi gli esempi ora corrispondono alla loro propria frase.
- **Un segnaposto appena inserito poteva, con „Ripristina originale",
  restare come un ammasso di lettere sovrapposte invece di sparire.**
  Un segnaposto inserito in tinta unita scriveva finora un proprio
  comando di output per ogni carattere, di cui solo il primo portava una propria
  matrice di testo – alla successiva modifica dello stesso punto (ad es.
  „ripristina" subito dopo) gli altri comandi di carattere ricevevano a rotazione
  gli indici di carattere del primo, e il segnaposto si scomponeva in
  due posizioni sovrapposte. Un segnaposto in tinta unita riceve
  ora un unico comando di output per l'intero testo.

- **Se lo stesso valore oscurato o rimosso stava su due righe nella
  finestra di rifinitura ed entrambe venivano contrassegnate per l'annullamento,
  la seconda riga contava erroneamente come „non univoca" – sebbene il valore
  fosse già stato ripristinato da tempo.** Entrambe le righe contano ora come completate.

- **Il nome dopo „Reply-To:" viene ora trovato.** In un'intestazione e-mail
  come „Reply-To: Huber" il nome restava finora del tutto non riconosciuto – il
  modello linguistico leggeva „Reply-To:" come una persona propria ed errata e ignorava
  il vero nome successivo.

- **Le parole di intestazione e-mail „Reply" e „Fwd" non vengono più oscurate esse
  stesse come nome.** In una riga di oggetto come „Fwd: Angebot von Huber"
  finora, oltre al nome, veniva riconosciuta e oscurata come persona anche la parola di intestazione
  stessa.

- **„Arbeitgeber: Siemens AG" viene ora riconosciuto come azienda, non più come
  persona.** Se il valore aziendale dopo l'etichetta „Arbeitgeber" portava una
  forma giuridica come GmbH, AG o KG, restava, nonostante il riconoscimento
  delle organizzazioni attivato, un risultato di persona – finora era riconosciuto come azienda
  solo il caso più ristretto senza forma giuridica („Wollmuth und Partner").

- **Un indirizzo riconosciuto una volta non resta più in un altro punto.**
  Se un indirizzo stradale veniva riconosciuto e sostituito in un punto,
  lo stesso indirizzo poteva restare in un secondo punto – ad esempio in
  un piè di pagina difficile da leggere di un documento scansionato, dove il
  riconoscimento automatico del testo lo leggeva in modo mutilato. Gli indirizzi vengono ora,
  come già da tempo nomi e aziende, rimossi in modo coerente in tutto il documento.

- **Le e-mail con più destinatari venivano silenziosamente danneggiate durante la ripulitura.**
  Un messaggio `.msg` con due o più destinatari perdeva, al salvataggio,
  parti della sua struttura interna, per cui il risultato ripulito era incompleto.
  La causa era una confusione tra componenti interni con lo stesso nome,
  che ricorrono per ogni destinatario. Tali messaggi vengono ora ricostruiti
  completamente.

- **Due dei documenti di prova forniti non si lasciavano aprire in Word e
  PowerPoint.** Chi scaricava il corpus di misurazione otteneva, con
  `format_dokument.docx`, „Errore nell'apertura del file in Word" e con
  `format_praesentation.pptx`, „Il file è danneggiato". Entrambi i file
  erano già difettosi prima che Maskuro li toccasse – la versione ripulita
  si limitava a trasmettere l'errore. LibreOffice apriva entrambi
  senza problemi, per questo nessuno se n'era accorto.

- **Una IA propria su internet viene ora contattata in modo cifrato.** Chi
  inserisce, per la propria IA, un indirizzo esterno senza „https://" (come spesso
  riportato sul foglio dell'IT) la raggiungeva finora tramite una
  connessione non cifrata – il testo non oscurato usciva in chiaro.
  Tali indirizzi vengono ora contattati tramite „https://"; un server nella
  propria rete resta raggiungibile invariato. Se il server segue un reindirizzamento
  verso un altro computer, la chiave di accesso non viene più trasmessa con esso.

- **Anche un'immagine danneggiata perde ora i suoi metadati nascosti.**
  Se un'immagine incorporata non si lasciava più aprire completamente (ad esempio una foto
  troncata), finora manteneva i suoi dati EXIF e GPS –
  luogo di scatto e nome del fotografo restavano invisibili nel risultato. Tali
  immagini vengono ora liberate da questi dati anche quando non
  si lasciano più visualizzare affatto.

- **Un file incorporato che non si lasciava ripulire viene ora
  segnalato invece di essere consegnato in silenzio.** Se in una presentazione o
  cartella c'era un oggetto incorporato troppo profondamente annidato o che
  non si lasciava aprire, finora restava invariato nel risultato, senza avviso –
  il file passava per ripulito. Tali casi compaiono ora nell'avviso
  „non hanno potuto essere verificati", esattamente come un formato incorporato obsoleto.

- **Gli elenchi scuri sono di nuovo uniformemente scuri e leggibili.** Su macOS
  gli elenchi di file alternavano righe quasi nere e grigio chiaro; nella
  rifinitura, lo stesso valore di verifica verde, arancione o rosso appariva quindi
  diverso a seconda della riga. Finestra, elenchi, carattere, segnaposto e selezione derivano
  ora da un'unica tavolozza chiara/scura comune. L'elenco dei risultati con
  codice colore inoltre non pone più strisce a zebra sotto i suoi colori.

- **Le indicazioni professionali con „als" venivano erroneamente oscurate come nome.** Una frase
  come „Als Koch ist er seit vier Jahren bei uns tätig." perdeva la professione,
  non solo un nome – „als" introduce un'indicazione di ruolo esattamente come „der"
  o „die". I veri cognomi nello stesso punto (ad es. con una formula di cortesia
  davanti) restano inalterati.

- **Un'intestazione di tabella poteva trascinare un numero di posizione in un importo
  in denaro** (solo con l'opzione „Rimuovi anche importi in denaro" attivata). Se una riga
  terminava con una valuta („… Einzelpreis EUR") e la successiva
  iniziava con un numero, ne risultava erroneamente un importo attraverso
  l'interruzione di riga. Il separatore tra valuta e numero resta
  ora sulla stessa riga.

- **Un'abbreviazione breve in maiuscolo poteva inghiottire un'intera parte di frase,
  o attaccarsi davanti a un nome correttamente riconosciuto.** Se
  in una riga c'era una parola maiuscola di due lettere come „DI", „AG" o „KG" –
  abbreviazioni quotidiane, non nomi –, l'intera riga veniva cercata in prova
  in minuscolo, e l'abbreviazione trascinava talvolta
  parole vicine (anche verbi) in un unico presunto nome.
  Solo a partire da tre lettere una parola maiuscola attiva ora questa
  seconda verifica. Con sigle un po' più lunghe come „CEO" o „USB"
  restava un secondo errore: il nome già correttamente trovato („Schneider")
  veniva trascinato nel risultato con la sigla anteposta come prefisso
  („CEO Schneider"). La sigla ora resta esclusa.

- **Una data di nascita senza spazio dopo restava intatta.** Se dopo
  „geb." non c'era spazio prima della data – come è consueto nei moduli
  a impaginazione stretta („geb.14.03.1988") –, Maskuro non riconosceva il campo e lasciava
  la data intatta. Forme abbreviate diffuse come „Geburtsdat." o „Geb.-Dat."
  vengono ora riconosciute anch'esse.

- **Un IBAN con barre come separatore restava intatto.** Come per
  i numeri di telefono („0664/1234567"), alcuni modelli scrivono anche l'IBAN
  in blocchi con barra („AT48/3200/0000/1234/5864") invece che con
  spazio o trattino. Questa grafia viene ora riconosciuta anch'essa.

- **Un numero di previdenza sociale austriaco con trattino, punto
  o barra restava intatto o era etichettato in modo errato.** Tra
  i due blocchi numerici era finora previsto solo uno spazio;
  grafie come „1237-010180", „1237.010180" o „1237/010180"
  non venivano riconosciute (o, nel caso della barra, sotto il tipo errato).
  La cifra di controllo continua a confermare ogni risultato, indipendentemente dal
  separatore.

- **Un nome dopo „c/o" in un indirizzo non veniva affatto
  rimosso.** „c/o Max Mustermann, Hauptstraße 5, 1010 Wien" oscurava
  via e città, ma lasciava il nome dopo del tutto intatto. Il
  nome viene ora riconosciuto; „c/o" stesso resta visibile come indicazione
  di indirizzo.

- **Un numero di carta di credito raggruppato con punti restava intatto.**
  Grafie come „4111.1111.1111.1111" non venivano riconosciute; numeri separati
  con spazio o trattino non ne erano interessati. Il codice di controllo
  continua a confermare ogni risultato.

- **Un codice fiscale raggruppato con trattini restava
  intatto, così come una partita IVA austriaca con trattino o punto.**
  Spazio, barra e punto erano già previsti per il codice fiscale,
  mancava il trattino; per la partita IVA („ATU12345678") mancavano
  trattino e punto dopo il prefisso. La cifra di controllo del codice fiscale
  continua a confermare ogni risultato.

- **Un valore di campo tra virgolette restava intatto, ad esempio in una
  riga in stile JSON come „vorname": „Max".** Il riconoscimento tramite
  un'etichetta di campo („Vorname: …") presupponeva finora che né l'etichetta
  né il valore stesso fossero tra virgolette. Tali
  righe vengono ora riconosciute anch'esse – così come le etichette di campo con
  un punto elenco YAML anteposto („- Vorname: Max") o un
  tabulatore invece di uno spazio prima dei due punti.

- **La parola di intestazione e-mail „Sent" veniva oscurata essa stessa come un nome.**
  In un'intestazione come „Sent: Huber" finora veniva colpito sia „Sent" sia
  il vero nome; parole di intestazione affini come „Subject" o
  „Betreff" ne erano sempre rimaste immuni. „Sent" resta ora
  intatto anch'esso.

- Un nome dopo le intestazioni „Errors-To:" o „Resent-From:" restava
  non rilevato quando una tale riga era copiata in chiaro (ad esempio un
  messaggio inoltrato o un rapporto di incidente) – diversamente da
  „Reply-To:" o „Return-Path:", qui il nome andava completamente perso invece di
  essere solo delimitato in modo impreciso. Viene ora trovato.
- Uno stesso identico file dava talvolta, con due ripuliture, un
  risultato diverso: se due riconoscimenti colpivano esattamente lo stesso punto
  con la stessa lunghezza e la stessa certezza (ad es. „Sozialversicherungs-
  nummer 1237/010180" come AT_SVNR o come identificativo generico), dipendeva
  dal caso quale prevalesse – il valore veniva rimosso in entrambi i casi,
  cambiava solo l'etichetta del segnaposto. La parità viene ora
  sempre risolta allo stesso modo.
- Una denominazione di funzione direttamente prima di un sostantivo (ad es. „Behandelnder
  Arzt: Dr. …" o „Zuständiger Sachbearbeiter ist …") veniva a volte
  erroneamente oscurata insieme, come se fosse essa stessa un nome. I veri cognomi
  accanto ne restano immuni.
- Un vero cognome che per caso ha lo stesso aspetto di un aggettivo
  (ad es. „Schöne", „Lange", „Junge") e sta direttamente prima di un ulteriore
  sostantivo (ad es. „Kontaktperson: Schöne Assistentin") restava, dalla
  correzione precedente, non oscurato nel testo – una fuga di dati. Ora solo una
  lista ristretta di vere denominazioni di funzione (ad es. „Behandelnder",
  „Zuständiger") viene trattata in questa forma come non-nome.
- Un cognome isolato alla fine di un risultato di nome su più righe,
  che per caso ha lo stesso aspetto di un aggettivo (ad es. „Schwarz",
  „Kurz", „Alt", „Frisch", „Gut", „Reich"), restava non riconosciuto prima di due punti
  immediatamente successivi – la ripulitura lo confondeva
  con un'etichetta di campo come „Telefon:". Un elenco chiuso
  di cognomi ambigui noti lo protegge ora.
- Un cognome isolato che per caso è una comune parola tedesca
  („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange"), andava
  finora **completamente** perso – anche in frasi semplici come „Herr
  Gross unterschrieb den Vertrag." Il motivo stava nell'elenco di stop-word
  proprio di spaCy, che contiene queste parole; un elenco chiuso
  di cognomi noti li protegge ora dallo scarto.
- Nei contratti di lavoro, mutuo, fideiussione, fiduciari e di insolvenza,
  nonché in tutela/curatela e incarichi peritali, un
  cognome che è anche una parola comune (ad es. „Bauer"), veniva ignorato dopo
  etichette come „Auftraggeber:", „Auftragnehmer:", „Arbeitnehmer:",
  „Versicherter:", „Darlehensgeber:", „Darlehensnehmer:", „Bürge:",
  „Sicherungsgeber:", „Treuhänder:", „Treugeber:", „Insolvenzverwalter:",
  „Gutachter:", „Sachverständiger:", „Vormund:" o „Pfleger:" – in
  parte restava riconosciuto solo il nome, in parte l'intero nome andava perso.
- Nella nota legale, un cognome che è anche una parola comune
  (ad es. „Bauer") veniva ignorato dopo le etichette „Geschäftsführer:",
  „Geschäftsführerin:", „Vertretungsberechtigt:", „Inhaber:" o
  „Inhaberin:" – con „Geschäftsführer:"/„Inhaber:" l'intero
  nome andava perso, con „Vertretungsberechtigt:" restava riconosciuto solo il nome.
- Un blocco di contatto la cui etichetta stava da sola nella sua riga e portava la
  forma neutra rispetto al genere con due punti („Ansprechpartner:in", nome
  sotto), veniva **completamente** ignorato – i due punti venivano letti come
  separatore di campo, „in" come valore di campo (scartato), e il vero
  nome nella riga successiva non veniva più preso in considerazione. La forma con asterisco
  („Ansprechpartner*in") non ne era interessata.
- Se nome ed etichetta con la stessa forma di genere a due punti stavano in
  **una sola** riga („Ansprechpartner:in Anna Berger"), il segnaposto trascinava
  la parola „in" nella sostituzione, invece di rimuovere solo il
  nome – il nome stesso continuava comunque a essere rilevato completamente.
- Un nome in una colonna di tabella sotto un'intestazione di colonna persona (ad es.
  „Name Vorname Geburtsdatum" sopra „Bauer Anna 03.05.1985", come in un
  cedolino paga) veniva completamente ignorato non appena tra le
  colonne c'era un solo spazio e nessuna riga iniziava con un
  numero di sezione – esattamente la forma in cui un vero
  estratto di testo PDF fornisce tali righe.
- In una chat o in un verbale di riunione con nome dell'oratore prima dei
  due punti (ad es. „Bauer 🙂: Ich stimme dem Vorschlag zu.") il
  nome restava del tutto non riconosciuto non appena un'emoji di reazione stava tra nome
  e due punti e il cognome era anche una parola comune
  („Bauer", „Koch", „Schneider" e sim.) – un intero verbale
  poteva così restare senza un solo oratore riconosciuto.
- La stessa lacuna delle righe dell'oratore esisteva anche con altri segni intermedi
  prima dei due punti: un'aggiunta di stato tra parentesi („Bauer (Vorsitz):
  …", „Bauer (abwesend): …"), un orario tra parentesi quadre
  („Bauer [14:32]: …") e un segno di nota a piè di pagina subito dopo il nome
  („Bauer*: …"). Anche qui l'oratore restava del tutto non riconosciuto,
  non appena il cognome era anche una parola comune.
- Se una persona già riconosciuta compariva in un estratto di verbale o
  di log allegato allo stesso messaggio (ad es. un ticket di assistenza)
  anche come nome utente nella forma „vorname.nachname" – minuscolo,
  senza spazio, unito da un punto –, questo
  nome in chiaro restava leggibile, sebbene lo stesso nome nella lettera fosse
  già stato oscurato.
- La stessa lacuna del nome utente esisteva anche con un trattino basso invece di
  un punto („vorname_nachname") – un formato altrettanto diffuso in
  estratti di verbale e log.
- E anche in ordine inverso il nome utente restava leggibile
  („nachname.vorname" ovvero „nachname_vorname") – alcuni sistemi anticipano
  il cognome nel nome utente del log invece di posporlo.
- Una data di morte restava non riconosciuta se accanto non c'era alcun'altra
  indicazione („Herr Bauer ist am 12.03.1985 verstorben") – finora non c'era
  affatto un riconoscimento proprio, e la data generica non scatta con questa
  soglia standard.
- Una data di morte restava non riconosciuta anche quando la frase usava la forma verbale
  invece del participio („Frau Meier verstarb am 12.03.1985",
  „Er starb am 12.03.1985") – finora funzionava solo „ist … verstorben"/„ist … gestorben".
- Una data di matrimonio restava non riconosciuta, in qualunque forma si presentasse
  („Eheschließung am 12.03.2010", „Hochzeitsdatum: 12.03.2010", „Herr und
  Frau Bauer heirateten am 12.03.2010") – finora non c'era affatto
  un riconoscimento proprio, e la data generica non scatta con questa
  soglia standard.

- **Nell'editor di rifinitura, un secondo riquadro sopra un segnaposto appena
  inserito poteva lasciare un residuo rosso di caratteri**, ad esempio
  „[G" invece di „[BEG1]" – senza alcun avviso, perché il residuo non apparteneva più
  al dato riservato (già rimosso nel primo passaggio), ma solo
  al segnaposto stesso. Il motivo era la colorazione: un segnaposto appena
  inserito veniva scritto nel file carattere per carattere, anche con impostazione
  in tinta unita – un riquadro successivo sullo stesso punto non trovava
  quindi più un testo coerente a cui potesse
  ancorarsi. Ora un segnaposto in tinta unita sta nel flusso come un
  unico pezzo, come faceva già sempre la ripulitura automatica; solo
  una vera sfumatura o un testo arcobaleno continua a richiedere singoli
  caratteri. La controprova integrata riconosce inoltre ora un tale residuo
  anche quando la stringa esatta del segnaposto non
  compare più.
- Un elenco nominativo numerato con numerazione di sezione a più livelli
  („1.1 Max Mustermann", „1.2 Huber Franz" …) perdeva tutti i nomi allo
  stesso freno che in realtà dovrebbe proteggere solo vere sezioni e
  liste di posizioni – senza intestazione di colonna sopra l'elenco non c'era
  nessun testimone a cui un nome potesse aggrapparsi.
- Un nome in una riga di accesso in lingua inglese di un log di sistema
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2")
  non veniva riconosciuto – il modello linguistico tedesco lo trovava solo se prima c'era
  „invalid user", altrimenti restava intatto. Tali estratti di log
  vengono spesso allegati invariati a un rapporto di incidente. I nomi dopo „for"
  prima di un indirizzo IP vengono ora riconosciuti in modo affidabile.
- Il nome del debitore nel riferimento del mandato SEPA di un
  estratto conto o di un giornale di registrazione (ad es. „MREF+Mustermann Klaus+SVWZ+
  Miete August") restava scoperto – nessuno spazio, nessuna struttura sintattica, solo
  campi in maiuscolo separati da „+", e nel consueto ordine
  „Nachname Vorname" il riconoscimento non lo trovava nemmeno per
  caso. Viene ora riconosciuto.
- La via con numero civico nella prima riga di una tabella di indirizzi
  (ad es. „Nachname | Vorname | Straße | PLZ | Ort") restava scoperta – il
  modello linguistico indovinava lì un luogo sbagliato, ma più lungo, attraverso
  più colonne, che soppiantava il risultato di indirizzo corretto ma più
  corto. Viene ora riconosciuto.
- La stessa lacuna si presentava con un tabulatore invece di „|" o „;" come
  separatore di colonna – lì l'indirizzo spariva persino del tutto invece
  di andare solo in parte perso. Viene ora riconosciuto.
- Una via con numero civico restava scoperta se subito dopo, senza
  spazio, seguiva un CAP con virgola (ad es. „Bahnhofstrasse
  12,80331 München", come in una colonna di tabella separata da virgola) – la
  virgola sembrava un decimale di una quantità, e la via non veniva quindi
  nemmeno considerata dal pattern come indirizzo. Viene ora riconosciuta.
- Una via con numero civico restava scoperta se subito dopo, senza virgola,
  seguiva il prefisso di luogo „St." (Sankt) (ad es. „Hauptstraße 5 St.
  Pölten", un'intestazione senza CAP anteposto) – „St." sembrava
  l'unità di misura per il numero di pezzi, e la via non veniva quindi
  nemmeno considerata dal pattern come indirizzo. Viene ora riconosciuta.
- Un'aggiunta di porta/scala dopo un numero civico (ad es. „Lerchenfelder
  Gürtel 43/12") restava visibile scoperta se subito dopo c'era una singola
  lettera che coincideva per caso con un'unità di misura (ad es.
  „h" per ora) – l'indirizzo veniva allora ripulito solo fino al numero civico senza
  la sua aggiunta, invece di essere trattato completamente o per niente.
- Una riga di oggetto con un cognome omonimo di professione prima del
  nome („Betreff: Bauer Anna", „Betreff: Bauer, Anna") restava finora
  del tutto non riconosciuta – anche in mezzo al documento con una
  frase completa precedente. Viene ora riconosciuta.
- Un codice fiscale tedesco con spazio, punto o trattino
  tra i blocchi (ad es. „Steuernummer: 30 815 08153" o
  „30.815.08153") restava finora non riconosciuto – veniva trovata solo la grafia
  con barra. Viene ora riconosciuto.
- Un nome dopo un'etichetta di campo medica („Patient:",
  „Hausarzt:", „Behandelnder Arzt:", „Überweisender Arzt:" e le loro
  forme femminili) restava finora non riconosciuto se il cognome era anche
  una comune parola tedesca (ad es. „Patient: Bauer Thomas").
  Viene ora riconosciuto.
- Un nome dopo l'etichetta di campo „Zahnarzt" su riga propria (ad es.
  „Zahnarzt", sotto „Huber Franz") restava finora non riconosciuto – né nome
  né cognome. „Zahnärztin" e la forma semplice „Arzt" non ne
  erano interessate. Viene ora riconosciuto.
- Un cognome dopo „Herr"/„Frau", seguito da una formula burocratica come
  „zur Kenntnisnahme", „zur Unterschrift" o „zur Weiterleitung",
  veniva finora colto troppo ampiamente, trascinando la formula nel risultato di nome
  – da „Frau Petra Klein zur Vertretung in allen Angelegenheiten"
  veniva sostituito „Petra Klein zur Vertretung", e il resto della frase restava
  grammaticalmente mutilato. Veri predicati nobiliari come „von der Leyen"
  o „zu Guttenberg" ne restano immuni.
- La stessa sovra-redazione da formula burocratica si nascondeva anche dietro il nome
  in un'intestazione e-mail „To:", un codice di omologazione (C.1/C.1.1/C.1.2),
  un codice patente, un campo modulo tra parentesi
  („[Vorname]: …") e una formula di saluto senza punto – ovunque
  „zur"/„von" e sim. trascinavano nel risultato una formula successiva come „zur Unterschrift" o
  „zur Vertretung", in parte restava perfino la semplice
  particella stessa come residuo di nome nel risultato. Anche qui restano
  completamente conservati i veri predicati nobiliari.
- Il numero di matricola dopo la sua etichetta finora non veniva
  affatto riconosciuto – „Matrikelnummer 7654321" sfuggiva completamente al riconoscimento,
  né come identificativo né tramite il modello linguistico, perché il numero da solo
  non porta una forma riconoscibile.
- Lo stesso valeva per il numero di partecipante – „Teilnehmernummer 4471829" sfuggiva
  completamente, né come identificativo né tramite il modello linguistico.
- Nel curriculum, il nome sotto il titolo di sezione „Persönliche
  Daten" sfuggiva spesso del tutto o in parte al riconoscimento, se stava senza formula di cortesia
  nella forma „Nachname Vorname" direttamente sotto.
- Lo stesso valeva per il titolo di sezione „Kontaktdaten" – lì il
  nome sfuggiva persino del tutto, non solo in parte.
- In un certificato di residenza o un elenco di domande con colonna
  combinata „Name, Vorname" (grafia dell'anagrafe, valore ad es.
  „Mustermann, Max" in una cella), il nome sfuggiva completamente al
  riconoscimento se seguiva un'altra colonna come la data di nascita.
- Una data di nascita nella forma consueta su carta d'identità e certificato di
  residenza „Geburtsdatum/-ort: 22.07.1978 / Rostock" non veniva
  riconosciuta – funzionava solo la forma con virgola „Geburtsdatum, Geburtsort: …".
- „Bürgerservice" e „Bürgerbüro" venivano occasionalmente oscurati erroneamente come
  luogo, in particolare dopo un trattino lungo come separatore di elenco
  (ad es. „Wenden Sie sich an das Bürgerservice – Bürgerbüro …").
- Un numero di telefono etichettato, interrotto nel mezzo da un'interruzione di riga
  (ad esempio da una stretta colonna di intestazione o da un'estrazione di testo PDF
  alla larghezza della colonna: „Telefon: 0176 12\n34567"), veniva in parte
  oscurato solo a metà – il resto dopo l'interruzione di riga restava leggibile.
- Un identificativo etichettato (numero cliente, socio, contratto e
  simili), interrotto nel mezzo da un'interruzione di riga (ad esempio „Kundennummer:
  K903\n944" da una colonna stretta), veniva oscurato solo a metà –
  il resto dopo l'interruzione di riga restava leggibile.
- Un nome con titolo accademico prima di una denominazione professionale dopo virgola
  (ad esempio „Dipl.-Ing. Sabine Roth, Projektleiterin") restava del tutto
  non protetto – la riga sembrava un'intestazione di colonna tabellare
  e veniva erroneamente scartata come contenuto oggettivo.
- Il titolo „Dr.-Ing." (un frequente titolo di ingegnere tedesco) prima di un
  nome non veniva incluso nel valore persona mascherato e restava
  leggibile – la stessa insidia del trattino di „Dipl.-Ing.".
- I titoli „Dipl.-Kfm.", „Dipl.-Kffr." e „Dipl.-Psych." (laureato/a in
  economia/psicologia) prima di un nome non venivano inclusi nel
  valore persona mascherato e restavano leggibili – la stessa
  insidia del trattino di „Dipl.-Ing." e „Dr.-Ing.".
- Un indirizzo MAC nella grafia Cisco con punti invece di due punti
  (ad es. „aabb.ccdd.eeff", come emesso da log di switch e ticket di supporto)
  non veniva affatto riconosciuto e restava leggibile.
- Un cognome dopo „Familie" (ad es. „Die Familie Gruber unterschreibt
  den Vertrag") restava, a seconda della struttura della frase, non riconosciuto e quindi leggibile –
  anche con predicato nobiliare davanti („Familie von der Leyen").

- In un indirizzo croato senza segno di punteggiatura separatore tra
  CAP+città e via+numero civico (ad es. „10000 Zagreb Ulica Ivana
  Lučića 5") il numero civico restava non ripulito.

- In un'indicazione di contatto lituana con l'etichetta „Kontaktinis
  asmuo" (ad es. „Kontaktinis asmuo: Vilkas Jonas") il cognome
  restava non riconosciuto se era anche un sostantivo comune (Vilkas =
  „Lupo", Vanagas = „Astore").

- Un paese di nascita o residenza senza ulteriore etichetta in un
  campo modulo danese (ad es. „Fødeland: Tyskland" o „Bopæl:
  Tyskland") non veniva riconosciuto.

- Un paese di nascita o residenza senza ulteriore etichetta in un
  campo modulo rumeno (ad es. „Țara: Germania" o „Țara de
  reședință: Franța") non veniva riconosciuto.

- Una ragione sociale sotto l'etichetta di campo lituana „Darbdavys:"
  o „Įmonės pavadinimas:" (datore di lavoro/azienda) non veniva riconosciuta.

- Una ragione sociale sotto l'etichetta di campo russa
  „Работодатель:" o „Наименование организации:"
  (datore di lavoro/azienda) non veniva riconosciuta.

- Una data scritta per esteso con nome del mese in rumeno (ad es.
  „31 decembrie 2024") non veniva riconosciuta.

- Un cognome da nubile ungherese dopo l'abbreviazione „szül." (ad es. „Nagy
  Éva (szül. Kovács)") non veniva riconosciuto e restava leggibile scoperto.

- Una pagina di profilo HTML salvata (o un'e-mail con pagina web allegata)
  poteva lasciare il nome anagrafico non ripulito, se questo si trovava solo
  nei campi di profilo Open Graph `profile:first_name`/`profile:last_name`/
  `profile:username` – questi portano il nome scomposto invece che
  descrittivo come `og:title` e vengono ora ripuliti anch'essi.

- Una notifica di mancato recapito (bounce/NDR) portava spesso le intestazioni
  dell'e-mail originariamente non recapitabile (mittente, destinatario, oggetto) in una
  propria terza parte di allegato – questa restava del tutto intatta nella
  versione ripulita. Questa parte viene ora ripulita come il resto
  del rapporto di consegna.

- L'operatore denominato individualmente di un'area protetta in Word (Limita modifica → Eccezioni, `w:permStart`) restava in chiaro, anche se lo stesso nome nel testo continuo era già stato ripulito da tempo. Ora viene rimosso anch'esso.

## 0.10.42-alpha.20260827 – 27 agosto 2026

### Nuovo

- **I profili di riconoscimento con nome rendono raggiungibili con un solo
  gesto diversi casi d'uso.** Sotto *Impostazioni → Riconoscimento → Cosa
  viene rimosso* si può salvare la selezione attuale di categorie e tipi e
  riapplicarla subito tramite un campo di selezione. Il profilo fisso
  *Standard* corrisponde allo stato di consegna finora e non si può
  eliminare. Un profilo modifica esclusivamente cosa viene rimosso;
  lingua, tipo di output, profondità di riconoscimento nonché termini e
  modelli di ricerca propri restano invariati.

- **Il tipo di risultato viene ora scelto direttamente prima della
  bonifica.** Un campo di selezione comune nella finestra principale
  stabilisce per l'intero lotto se Maskuro inserisce segnaposto leggibili,
  oscura o rimuove senza sostituto. I due campi separati per PDF e Office
  nella finestra delle impostazioni sono stati eliminati; così la
  decisione importante è visibile e non può più divergere
  involontariamente in lotti misti. Il giro guidato spiega la nuova
  selezione prima della prima bonifica.

- **Temi e filigrane contrassegnano chiaramente i PDF completati su
  richiesta.** Dodici aspetti complessivi armonizzano testi sostitutivi e
  aree di oscuramento; nuovi tra questi sono Pride nonché primavera,
  estate, autunno e inverno. *Fascicolo segreto* porta direttamente una
  scritta diagonale `TOP SECRET`. Indipendentemente da ciò, si può
  scegliere un testo di marcatura libero oppure un'immagine, icona o SVG
  propri con colore e opacità. Le grafiche importate vengono incorporate
  senza i loro metadati e restano disponibili se il file sorgente viene
  spostato. Durante la correzione, Maskuro sostituisce la sua filigrana
  precedente, invece di sovrapporla più volte.
  Le filigrane di testo vengono disegnate come ultimo strato PDF con
  contorno chiaro, in modo da restare visibili anche su immagini scure e
  testo denso. L'editor di correzione ignora completamente la filigrana di
  Maskuro e non ne offre più il testo come candidato all'oscuramento.

- **I temi di output propri si possono salvare e condividere.** La
  miscela attuale di testo sostitutivo, oscuramento e filigrana riceve un
  nome, resta nelle impostazioni e può essere esportata o importata come
  JSON privo di testo in chiaro. L'anteprima di stampa in bianco e nero
  avverte di contrasti deboli; i coriandoli di successo opzionali restano
  puramente nell'interfaccia.

- **Una prova di esportazione finale e un motivo di controllo esplicativo
  chiudono il giro di rappresentazione.** Prima del salvataggio
  definitivo, Maskuro confronta ancora una volta ogni punto PDF noto con
  precisione nello strato di testo e nei pixel renderizzati; gli avvisi
  indicano esclusivamente pagina e coordinate. Nell'editor, *Perché è
  coperto?* mostra categoria, percorso di riconoscimento e margine di
  sicurezza, mai il testo in chiaro rimosso e mai nel documento finale.

- **Le barre di oscuramento ora possono essere belle.** Sotto
  *Impostazioni → Aspetto* sono disponibili preimpostazioni di colore,
  selettori di colore liberi, sfumature, arcobaleno, strisce, punti,
  fiori, stelle, cuori, zampe, nuvole, fulmini, chicchi di caffè,
  anatre, soli, foglie, fiocchi di neve, motivi carta, evidenziatore,
  nastro adesivo e motivi casuali riproducibili, con anteprima immediata.
  I testi sostitutivi ricevono a scelta un colore, una sfumatura, un
  arcobaleno, una pillola o un'etichetta. I colori di categoria
  distinguono nomi, indirizzi, contatti e dati medici. Il PDF adotta
  l'intera formattazione; Word, PowerPoint, OpenDocument e HTML usano il
  colore di base coprente scelto. La protezione non cambia in questo:
  Maskuro rimuove prima il contenuto riservato e disegna colore o motivo
  solo sul punto vuoto.

- **Maskuro torna disponibile per Linux – come AppImage, DEB, RPM e
  archivio portabile.** DEB e RPM registrano nel sistema voce programma,
  associazioni di file, comando terminale e icona; l'AppImage funziona
  senza installazione. Gli aggiornamenti restano, in presenza di
  un'installazione DEB o RPM esistente, nello stesso formato di pacchetto
  e altrimenti preferiscono l'AppImage.

- **Il controllo visivo non presenta più il testo PDF normale una seconda
  volta come nuovo rilevamento.** Lo sguardo OCR finale e la ricostruzione
  sicura delle pagine visibili restano completamente attivi; come nuova
  fonte di rilevamento, per impostazione predefinita, contano però solo le
  aree che il testo di pagina e il controllo immagine singola non hanno
  ancora letto. Così le righe prodotto non diventano nuovi nomi o aziende
  solo a causa di una seconda lettura OCR divergente. Chi desidera comunque
  due giudizi indipendenti sull'intero testo visibile attiva nelle
  impostazioni *Verifica di nuovo l'intera pagina PDF visibile per i
  dati*.

- **I PDF si possono visualizzare in modo continuo, foglio per foglio o
  come doppia pagina.** Tre icone di visualizzazione compatte si trovano
  in basso direttamente accanto a „Larghezza" e „Pagina". Continuo scorre
  al bordo del foglio verso la pagina successiva; Pagina singola mantiene
  la rotellina del mouse sul foglio attuale; Doppia pagina mostra un
  foglio doppio, rende modificabile il foglio cliccato e sposta
  avanti/indietro di un foglio doppio intero. Miniature di pagina e lente
  di confronto si aprono inoltre in una colonna base sinistra
  notevolmente più stretta e lasciano più spazio alla pagina di lavoro.

- **Ora vedete cosa ha fatto il livello IA.** Dopo ogni esecuzione, sotto
  „Dettagli" compare per ogni file una riga in merito – „Livello IA: 12
  casi limite verificati, 3 scartati" –, e se non ha trovato nulla da
  cambiare, c'è scritto anche quello. Finora il livello più costoso taceva
  completamente: se fosse stato interpellato non si poteva sapere
  dall'esterno.

  Chi ha bisogno di maggior dettaglio attiva sotto „Impostazioni → IA"
  *Registra ogni domanda IA nel registro*. Allora il file di registro
  registra per ogni domanda dimensione, durata e numero dei riscontri, più
  il tempo di attesa dovuto a un limite di volume della controparte. Il
  pulsante „Mostra file di registro" accanto apre la cartella – si trova
  nella cartella dati dell'applicazione, che sotto Windows è nascosta e
  che nessuno trova da solo. Nel file compaiono esclusivamente dimensioni,
  mai testo dai vostri documenti.

- **Maskuro riconosce quando il vostro servizio IA limita il numero di
  richieste.** I servizi ospitati spesso consentono solo poche richieste
  al minuto – quattro non è raro. Quelle in eccesso non vengono
  respinte, ma devono attendere, e da due secondi per risposta diventano
  quaranta. Finora sembrava che il modello fosse lento. Ora Maskuro legge
  il limite dalla risposta del servizio, non invia più domande
  contemporaneamente di quante ne vengano accettate, indica il limite
  sotto „Verifica connessione" e lo include nella stima della durata.

- **L'anteprima pagina usa il vostro Word, Excel e PowerPoint – ed è così
  circa sei volte più veloce.** Finora richiedeva LibreOffice, presente su
  pochissimi computer d'ufficio; chi non ne aveva uno vedeva un pulsante
  che chiedeva un'installazione esterna. Ora vale: se Microsoft Office è
  installato, viene usato da solo – senza configurazione, senza
  download, senza dover spuntare nulla. LibreOffice resta la seconda via
  e per i file OpenDocument perfino la prima; se una fallisce, si prova
  l'altra.

  La differenza si nota soprattutto lavorando: dopo ogni sostituzione la
  pagina viene ricomposta, e questo costa con Office circa mezzo secondo
  invece di tre. La prima visualizzazione di un documento richiede
  ancora qualche secondo, dopo di che segue i vostri gesti senza tempi di
  attesa.

  Il vostro Word aperto non viene toccato: Maskuro avvia una propria
  sessione invisibile, apre il file solo in lettura, disattiva le macro e
  chiude tutto di nuovo non appena la finestra di correzione si chiude. I
  file protetti da password vengono respinti, invece di restare bloccati
  in una finestra di dialogo invisibile.

- **La configurazione iniziale chiede ora anche di volti, codici e firme –
  e scarica tutto ciò che manca in un'unica volta.** Accanto al
  riconoscimento avanzato, sulla prima pagina compaiono i tre interruttori
  immagine: rendere irriconoscibili le aree del volto, rendere
  irriconoscibili codici a barre e QR, oscurare firme scritte a mano su
  pagine PDF. Il limite ai PDF è indicato visibilmente accanto alla
  spunta; i file Office non vengono cercati automaticamente per firme.
  Sotto le spunte c'è scritto quanti megabyte costa il clic su „Avanti".
  Il caricamento avviene poi in **un'unica** finestra con **un'unica**
  barra di avanzamento su tutto insieme, invece che in più finestre di
  dialogo in sequenza; un'interruzione termina l'intero processo e non
  lascia nulla a metà. Chi non vuole nulla di tutto ciò toglie le spunte
  – allora non viene scaricato nulla.

- **L'anteprima si può diradare in base al bisogno di controllo e
  chiudere per tipo.** Sopra l'elenco si trova un cursore *Nascondi ben
  documentati*: quanto più è spostato a destra, tanto più nasconde da
  verde verso rosso; tutto a destra resta solo ciò che il programma ha
  soltanto indovinato da solo. Un clic sull'intestazione di un tipo lo
  chiude. Entrambi sono un aiuto alla lettura, non una selezione – ciò
  che è nascosto o chiuso resta spuntato e viene sostituito; quanti
  valori siano al momento sta scritto sotto il cursore. Con elenchi
  brevi, il cursore non compare. Il passaggio a due colonne mantiene ora
  anche gli interruttori *mai più*.

- **L'elenco immagini può aprirsi da solo prima di ogni esecuzione.** Chi
  vuole decidere su ogni immagine singolarmente, imposta sotto
  „Immagini" la nuova spunta *Stabilisci singolarmente prima di ogni
  esecuzione*. L'elenco con anteprima compare allora da solo durante la
  bonifica, invece che dover cliccare voi stessi „Stabilisci
  singolarmente …" ogni volta; se lo annullate, non viene nemmeno
  bonificato. Se nessuno dei file scelti contiene un'immagine, non compare
  nulla. Predefinita, la spunta è disattivata.
- **Maskuro trova nelle pagine PDF firme scritte a mano e le rimuove dai
  pixel.** Finora la firma restava sotto un documento bonificato – il
  riconoscimento testo legge il carattere stampato, e ciò che non legge
  non viene sostituito. La ricerca è un interruttore proprio e richiede
  un modello di riconoscimento, che viene scaricato una tantum.

  Trova, come misurato, circa 84 firme su 100 e le copre per circa
  quattro quinti. È un aiuto e non una promessa: dopo ogni esecuzione, il
  rapporto indica quante ne sono state trovate – anche quando non ce n'era
  nessuna, perché ciò può significare che non ce n'è o che ne è stata
  trascurata una. Su 72 vere pagine aziendali senza firma non ne ha
  inventata nessuna.

  Una firma **disegnata** viene trovata, ma non rimossa: è composta da
  linee, non da pixel, e una barra sopra sarebbe solo una copertura sotto
  cui le linee resterebbero. Tali punti vengono contati e indicati, in
  modo da poterli oscurare da soli nella finestra di correzione.

  I file Word, Excel, PowerPoint e OpenDocument non vengono cercati
  automaticamente per firme. Interfaccia, configurazione iniziale,
  scaricamento modello, riga di comando e manuale indicano ora
  espressamente questo limite.

- **Il giro guidato passa ora anche attraverso l'anteprima – la finestra
  in cui decidete.** Con il documento di esercizio si apre da sola, anche
  se avete disattivato l'anteprima altrove (la vostra impostazione resta
  com'è). Viene spiegato cosa significano i colori, perché in ogni riga
  c'è solo una domanda – c'è qui davvero una persona? – e a cosa serve
  „mai più". Nei colori, il riflettore è puntato su una riga ben
  documentata, di solito l'IBAN – l'esempio verde che la frase nomina;
  dopo sulla meno documentata, e lì potete cliccare voi stessi in mezzo
  alla spiegazione: spunta tolta, il valore resta nel documento. Con un
  elenco lungo, la finestra per la guida si apre più grande, in modo che
  la spiegazione non copra le righe. Se la finestra si apre una seconda
  volta, il giro guidato dice anche perché – la pagina finita viene letta
  ancora una volta come immagine, e in questo nascono frammenti che
  sembrano un nome.

- **L'editor si apre grande la prima volta.** Originale, risultato, barra
  degli strumenti ed elenco dei rilevamenti stanno affiancati e nella
  dimensione base precedente avevano troppo poco spazio. Chi rimpicciolisce
  la finestra la ritrova nella stessa dimensione la volta successiva –
  nessuno viene sovrascritto.

- **Un doppio clic su un segnaposto lo recupera** – in Word, Excel,
  PowerPoint, OpenDocument, testo, e-mail e HTML. E chi traccia su più
  segnaposto e sceglie „Recupera selezione" recupera tutti quelli
  contenuti in una sola volta. Non serve quindi più colpire con
  precisione la parentesi quadra. I segnaposto che nell'anonimizzazione
  rappresentano più valori diversi ne restano esclusi – vengono contati e
  indicati, non indovinati.

- **Il manuale ha un capitolo „Anteprima prima della sostituzione".** La
  finestra è preimpostata su attiva ed è l'unica in cui decidete – nel
  manuale finora era presente solo come subordinata. Ora c'è scritto cosa
  significa una spunta (vale per **ogni** punto di rilevamento, non solo
  quello elencato), perché per ogni riga c'è solo una domanda a cui
  rispondere, cosa comporta „mai più" in modo permanente, e perché la
  finestra può aprirsi una seconda volta con un PDF. In tutte e diciotto
  le lingue, e nell'elenco delle impostazioni l'interruttore è ora
  anch'esso elencato.

### Modificato

- **Il pannello „Valori sostituiti" ha un cursore sui colori, e la
  modalità di apprendimento non è più lì.** Con più di otto valori, sopra
  l'elenco si trova lo stesso cursore della finestra di anteprima:
  *Nascondi ben documentati* dirada la visualizzazione a ciò che va
  davvero controllato. Sul documento questo non cambia nulla, e quante
  righe di quante siano visibili sta scritto sotto – campo di ricerca e
  cursore si sommano. La spunta *Modalità di apprendimento* è sparita dal
  pannello; resta comunque nel menu *Strumenti* e nella barra degli
  strumenti.

- **Il pannello „Valori sostituiti" mostra ora gli stessi colori del
  documento.** Ogni riga al suo interno è colorata come il punto nel
  documento e come il valore nell'anteprima: rosso significa „indovinato
  da solo, qui conviene guardare per primo", verde „riconosciuto da un
  modello con nome". All'interno di ogni tipo, il più incerto sta in
  alto – lavorate quindi l'elenco dall'alto verso il basso e vedete per
  primo ciò che è più importante. Finora tutto era colorato allo stesso
  modo e ordinato alfabeticamente.

- **La modalità di apprendimento è disattivata di fabbrica.** Dopo una
  correzione nella finestra di correzione, il programma finora chiedeva
  da solo se creare da essa una regola propria. Questa domanda arriva in
  mezzo al lavoro; chi non l'ha richiesta la percepisce come
  un'interruzione. Chi vuole le regole attiva il pulsante *Modalità di
  apprendimento* nella barra degli strumenti – la scelta vale poi in
  modo permanente, in entrambe le direzioni.

### Corretto

- **I file di regole esportati sono ora contrassegnati espressamente come
  degni di protezione.** Termini ed eccezioni propri possono trovarsi al
  loro interno in chiaro; inoltre il file può contenere il sale hash con
  cui si possono confermare valori presunti. L'esportazione riuscita
  mostra quindi un avviso e invita a proteggere il file e a passarlo solo
  consapevolmente a destinatari autorizzati.

- **L'ultimo controllo di sicurezza non trattiene più file d'ufficio
  bonificati a causa dei propri segnaposto.** Una sigla di tipo come
  „SVNR" compare anche in `[SVNR1]`; finora ciò valeva come presunto
  resto in chiaro e il file completato veniva scartato. Allo stesso
  tempo, numeri di telefono e IBAN vengono ora ripuliti anche dove Office
  deposita lo stesso dato senza spazi visibili in un riferimento o in un
  file incorporato.

- **Word, Excel, PowerPoint e OpenDocument non lasciano più una copia di
  campo scoperta solo in ritardo.** Se un valore viene riconosciuto per
  la prima volta in un deposito secondario o in un file d'ufficio
  incorporato, un passaggio successivo mirato ripulisce anche le copie
  visibili e nascoste lette in precedenza. I segnaposto di riferimento
  già generati non vengono in questo caso sostituiti una seconda volta.

- **Nel recupero singolo di un elenco di selezione Word, non torna più
  indietro senza chiedere una selezione vicina.** Il paragrafo originale
  completo viene ripreso solo quando anche i suoi attributi non
  contengono più segnaposto aperti.

- **Le scansioni poco leggibili perdono meno dati correlati.** Una lettura
  OCR alternativa con formula di cortesia e nome a due elementi viene
  mantenuta; frammento di via, numero civico e CAP-località proteggono
  insieme l'intera riga dell'indirizzo, anche quando si scompone in
  blocchi OCR adiacenti. Righe di fattura e articolo nonché righe di
  evento accanto non vengono in questo caso incluse. Anche una data
  valida scomposta dopo „nato" in più parole OCR e segni di punteggiatura
  viene resa completamente irriconoscibile.

- **I coriandoli di successo sono ora visibili all'apertura automatica
  dell'editor.** I frammenti sprizzano direttamente dal pulsante
  *Bonifica* invece di piovere dal bordo superiore della finestra.
  L'editor attende solo il primo spruzzo, breve di 850 millisecondi, e si
  apre poi automaticamente; senza coriandoli attivati continua a non
  esserci alcun ritardo.

- **Contatore pagine e barra dello zoom non saltano più avanti e indietro
  passando sopra le icone di visualizzazione.** Qt ridistribuiva lo
  spazio libero della riga di stato non appena vi compariva il suggerimento
  di un'icona. Entrambi i gruppi di comando mantengono ora al passaggio
  del mouse la loro larghezza naturale e una posizione fissa.

- **La misurazione della velocità di un server IA collegato falliva
  sempre** – su ogni server, da quando esiste l'IA propria. Interrogava
  con un limite di risposta stretto e in seguito tentava di leggere la
  risposta così troncata; ciò doveva fallire, e veniva salvato „non
  misurato". Le conseguenze si vedevano ovunque: la stima della durata
  calcolava il vostro server con la velocità del modello incluso su un
  computer d'ufficio, e nelle impostazioni c'era scritto in modo
  permanente che la velocità non era ancora stata misurata. Ora si misura
  in base alla quantità che il server ha generato, non in base al
  contenuto della sua risposta.

- **„Riconoscimento massimo (IA) – lento" compariva anche quando non era
  vero.** Etichetta e avviso descrivevano il modello incluso su un
  computer d'ufficio – „un modello linguistico su questo computer", „con
  documenti grandi fino a un'ora". Chi ha collegato un proprio server IA
  leggeva lì due cose sbagliate: non si calcola sul suo computer, e si
  risponde in secondi invece che in ore. Entrambe le cose provengono ora
  dalla misurazione. Se non ce n'è una, l'applicazione non afferma più
  nulla, ma dice che non è ancora stato misurato.

- **Il recupero agisce ora anche su una selezione tracciata.** Chi
  tracciava su più segnaposto e voleva premere *Recupera selezione*
  trovava il pulsante grigio: si attivava solo se la selezione era
  **esattamente** un segnaposto – tracciata su un paragrafo non lo è mai.
  Il percorso dietro esisteva già, solo che nessuno ci arrivava. Ora
  basta selezionare l'area; tutti i segnaposto al suo interno tornano
  indietro in un colpo solo.

- **Il recupero andava in crash se la lente di confronto era aperta.** La
  lente memorizza il punto sotto il puntatore del mouse, per seguirlo
  nell'originale. Al ricaricamento dopo un recupero restituiva questo
  punto in una forma con cui la visualizzazione testo non sapeva cosa
  fare – e poiché un tale errore in mezzo all'interfaccia chiude il
  programma, dal recupero era nato un crash. La lente è aperta nella
  posizione base, colpiva quindi il percorso normale.

- **Dopo il recupero, la visualizzazione non salta più all'inizio del
  documento.** In uno scritto più lungo, dopo ogni gesto spariva il punto
  in cui si stava lavorando. Ora il paragrafo che stava in alto resta in
  alto.

- **Senza LibreOffice, l'anteprima pagina dice da dove viene, invece di
  limitarsi a mancare.** I due pulsanti *Anteprima pagina* e *Oscura come
  PDF* erano bloccati e nel tooltip indicavano solo che non era stato
  trovato LibreOffice; non esisteva da nessuna parte nell'applicazione un
  percorso verso di esso. Un clic apre ora un avviso con il percorso
  verso LibreOffice, gratuito e open source. Manuale e FAQ erano sbagliati
  su questo punto – annunciavano un componente da scaricare che
  l'applicazione non offre.

- **Prima della consegna, il file completato viene cercato un'ultima
  volta per intero – ora anche per Word, Excel, PowerPoint, LibreOffice,
  e-mail, HTML e testo.** Finora solo il PDF aveva questo ultimo sguardo.
  Tutti i controlli precedenti verificano in un punto che qualcuno ha
  nominato in anticipo; un deposito a cui nessuno ha pensato non viene
  quindi controllato da nessuno. Alla fine, Maskuro cerca ora
  sistematicamente tutto ciò che è stato sostituito – in ogni parte del
  pacchetto. Se resta qualcosa, **non** nasce alcun risultato, e il
  messaggio indica il valore. Un file ritenuto bonificato è peggio di
  nessun file.

- **I nomi presenti in `<script>` e `<style>` vengono ora segnalati.**
  Entrambi restano comunque intatti – lì c'è codice di programma, e una
  sostituzione in mezzo a un identificatore trasforma una pagina web in
  una pagina web rotta. Finora però non veniva detto, ed era questo
  l'errore: una regola di stile `content: "Anna Musterfrau"` è
  **visibile** al destinatario sullo schermo, e nel risultato restava
  lì, mentre il programma segnalava la pagina come bonificata.

- **Nelle impostazioni si possono di nuovo caricare e rimuovere i modelli
  aggiuntivi.** Il pulsante accanto a „Riconoscimento avanzato" e
  „Riconoscimento massimo (IA)" finiva, alla pressione, nella finestra del
  rapporto di errore, invece di scaricare il modello. La seconda via – la
  spunta nel riconoscimento, che chiede da sola il modello – non ne era
  mai stata interessata.

- **I nomi presenti in nomi di foglio e area di una tabella vengono ora
  segnalati.** Il nome di un foglio compare sulla scheda in basso, il
  nome di un'area denominata nel campo nome e in ogni formula che la usa.
  Entrambi continuano a non essere sostituiti – le formule vi fanno
  riferimento, e una cartella con errori di riferimento non aiuta
  nessuno – ma ora c'è scritto. Finora il messaggio compariva solo per il
  nome del foglio di una cartella Excel: un'area denominata
  „Bezuege_Brunnthaler" usciva in silenzio, e con una tabella
  LibreOffice il programma taceva del tutto. Un foglio „Notizen Ortner"
  valeva quindi come bonificato, e il primo sguardo del destinatario
  cadeva sul nome.

  Viene segnalato solo ciò che porta davvero a una persona: una parola
  che nella stessa cartella è stata comunque sostituita, oppure un
  rilevamento che seleziona una tra più parole. Una parola isolata come
  „Zustaendig" o „Bezug_Umsatz" non genera più alcun avviso – prima lo
  avrebbe fatto, e un avviso che compare in una cartella su due dopo la
  terza volta non lo legge più nessuno.

- **„Recupera originale" ora recupera davvero tutto.** In alcuni
  documenti mancavano dopo singoli caratteri – da „Seestraße 14"
  diventava „Seestraße 4", da „An:" un „An", da „nordlicht-planung" un
  „nordlicht planung" –, e singole righe non tornavano affatto. Proprio
  lì dopo non si poteva più selezionare nulla con il mouse né oscurare
  nulla: il testo stava sì sulla carta, ma il programma non lo
  riconosceva più. Erano interessati caratteri stretti – l'uno, i due
  punti, il trattino – in documenti che compongono ogni carattere
  singolarmente; il documento di esercizio è uno di questi.

- **E gli stessi documenti non vengono più trasformati in immagine
  durante la bonifica.** Poiché un tale carattere restava, il controllo
  successivo segnalava un resto e la pagina veniva rasterizzata per
  precauzione. Il testo su di essa diventava allora solo un'immagine: non
  più ricercabile, non più selezionabile, più grande nel file. Il
  documento di esercizio resta ora testo vero su entrambe le pagine.

- **I contrassegni colorati non restano più sopra il testo recuperato.**
  Chi annullava una sostituzione vedeva ancora il rettangolo colorato
  sopra la parola ripristinata – affermava „qui è stato rimosso
  qualcosa", anche se lì stava di nuovo l'originale.

- **Una barra non rivela più quanto era lunga la parola sottostante.**
  Nell'oscuramento, la barra copre ora in righe corte l'**intera** riga –
  blocco indirizzo, dati di intestazione, cella di tabella stretta. Se
  l'intera riga non ci sta (la normale riga di tabella a tre colonne),
  resta il campo; in una riga di testo scorrevole resta a livello di
  parola, altrimenti un nome in mezzo alla frase avrebbe reso nera
  l'intera frase. E le barre poste una sotto l'altra diventano **della
  stessa lunghezza**: nel blocco indirizzo ogni riga porta un valore, e
  tre barre di lunghezza diversa rivelavano ancora quanto erano lunghe le
  righe. Crescono solo finché la carta è libera – davanti a una colonna
  vicina la barra si ferma.

- **„Riga intera" ora oscura davvero l'intera riga.** Finora la barra
  terminava allo spazio maggiore successivo – cioè alla fine del campo.
  Nel testo scorrevole non si notava, lì il campo è la riga; nei dati di
  intestazione e nelle tabelle sì: da „Nome: Anna Musterfrau  Reparto:
  Vendite" nasceva una barra che terminava esattamente all'ultima lettera
  del nome – e con essa la sua lunghezza restava di nuovo sul foglio. La
  barra corre ora dalla prima all'ultima parola della riga e include le
  colonne vicine. Chi vuole colpire solo il valore sceglie „Parole";
  l'automatismo oscura invariato per campo.

- **Prima della consegna, il file completato viene cercato un'ultima
  volta.** Tutti i controlli precedenti verificano in un punto che
  qualcuno ha nominato in anticipo – testo di pagina, rettangolo di
  rilevamento, area immagine. Un PDF ha però più depositi di quanti
  un'enumerazione possa contenere: annotazioni, valori di modulo,
  segnalibri, informazioni sul documento, allegati, JavaScript. Alla
  fine, Maskuro cerca quindi sistematicamente nel file scritto tutto ciò
  che ha sostituito – ovunque tranne nel testo di pagina, dove lo stesso
  testo letterale può stare anche in modo lecito. Se resta qualcosa,
  **non** nasce alcun risultato, e il messaggio indica il valore. Un
  documento ritenuto bonificato è peggio di nessuno.

- **Ciò che non si poteva verificare non conta più come verificato.** In
  tre modi, finora, un fallimento del controllo successivo appariva come
  un risultato pulito. Una pagina il cui strato di testo non si poteva
  leggere valeva come particolarmente pulita – lì non c'era nulla da
  trovare; viene ora rasterizzata. Se una pagina con un punto di
  rilevamento residuo non si poteva rasterizzare in alternativa, veniva
  consegnata in silenzio; ora la bonifica preferisce interrompersi. E la
  controprova nella finestra di correzione segnalava, dopo un proprio
  errore, „nulla rimasto" – nella finestra non distinguibile dal fatto che
  tutto fosse stato rimosso; ora compare l'avviso insieme al pulsante
  „Rasterizza pagina".

- **„Ripristina predefinito" non ripristinava affatto la maggior parte
  delle impostazioni.** Nove spunte su ventidue restavano invariate dopo
  il gesto – tra queste l'anteprima, „Apri i file bonificati dopo",
  la finestra di correzione, il deposito immediato ed entrambe le
  spunte di aggiornamento. Il file salvato era sì svuotato, ma la
  finestra manteneva i vecchi valori e li riscriveva al clic successivo.
  Ora ogni spunta torna, e la dicitura „modificato" sparisce con essa.
- **„Deposita automaticamente il rapporto di controllo per ogni
  bonifica" mostrava attivo, ma era disattivato.** Dopo il ripristino, la
  spunta restava impostata, mentre il valore era cancellato – non
  nasceva più alcun rapporto, senza che nulla lo indicasse. Lo stesso
  valeva per il registro di controllo e la registrazione schermo
  propria; la loro scorciatoia da tastiera viene ora anche correttamente
  attivata o disattivata al ripristino.

- **Le barre di una riga hanno ora lo stesso aspetto.** Finora ogni punto
  di rilevamento portava con sé la propria barra, e la sua altezza
  derivava dal carattere della parola colpita. In una riga con etichetta
  e valore di dimensioni diverse stavano quindi accanto un tratto spesso
  e uno sottile con bordi sfalsati, e dove due punti di rilevamento erano
  separati solo da uno spazio, sopra restava una fessura chiara. Le barre
  della stessa riga hanno ora lo stesso bordo superiore e inferiore, e
  ciò che è separato solo da uno spazio diventa un'unica barra. Ciò che
  deve restare tra due punti di rilevamento – la virgola dietro il nome,
  un'etichetta, un importo – continua a separarle. Vale sia per pagine
  composte sia per scansioni.

- **Le schede sotto „Informazioni su questo programma" ricominciano di
  nuovo dall'alto.** Privacy, condizioni di licenza e note di licenza si
  aprivano in mezzo al testo – chi le leggeva doveva prima scorrere fino
  in cima per vedere la prima riga.

- **La penna non apre più una seconda finestra editor, ma porta avanti
  quella esistente.** Finora nasceva una nuova a ogni clic. La finestra
  non ha una voce propria nella barra delle applicazioni – chi la
  riduceva a icona non riusciva più a raggiungerla e cliccava di nuovo;
  al ripristino della finestra principale, tutte le finestre accumulate
  venivano portate avanti in una volta. Ora ulteriori documenti finiscono
  nella barra delle schede della finestra aperta, e un documento già
  presente lì non riceve una seconda scheda.

- **„Riconoscimento avanzato" non porta più la dicitura „modificato",
  finché manca il suo modello.** Viene consegnato attivato, ma senza il
  modello scaricabile non può esserlo affatto – nelle impostazioni la
  riga risultava quindi su ogni computer appena configurato come
  modificata, anche se nessuno l'aveva toccata. Perché la spunta è
  disattivata lo dice ora da sola la sua etichetta: „Modello non ancora
  caricato".

- **Lo striscione introduttivo spiegava nei file Office e di testo la
  tela PDF.** Vi era scritto „cliccare su una parola la oscura" – in un
  file Word, però, un clic non oscura nulla, lì si seleziona e poi si
  preme un pulsante. Ora dice cosa vale nella rispettiva visualizzazione.
- **La barra degli strumenti nella visualizzazione testo era ingombra di
  etichette.** „Sostituisci selezione", „Oscura selezione", „Recupera
  selezione", „Anteprima pagina" e „Oscura come PDF" compaiono ora come
  icona – come le loro sorelle in un PDF. I loro nomi restano nella
  guida rapida e nel menu.
- **Ctrl+rotellina del mouse nella lente di confronto non muoveva con sé
  il suo cursore dello zoom.** Il carattere diventava più grande, cursore
  e percentuale accanto continuavano ad affermare il vecchio stato.
- **Il programma di installazione di un aggiornamento non veniva in
  primo piano** – bisognava prima cliccarlo nella barra delle
  applicazioni (solo Windows).
- **Un anno all'inizio riga valeva come codice postale austriaco.** In un
  curriculum, da „2020 Strategie di vendita" nasceva un segnaposto –
  l'intera riga spariva. Un numero di quattro cifre tra 1900 e 2099
  richiede ora un secondo segnale di indirizzo: la via sopra, una parola
  di campo prima, un codice paese o un nome di luogo noto. I blocchi
  indirizzo lo hanno; le colonne di anni no.
- **Una coppia mese-anno valeva come numero di telefono.** Da „Dal 08.2010
  123-Verkauft GmbH" nasceva un „numero di telefono" – mese, anno e le
  prime cifre del nome dell'azienda dietro.
- **Il rapporto diceva „verificato tramite riconoscimento testo" e
  taceva su cosa non legge.** Se le immagini vengono mantenute, ora c'è
  scritto che quanto scritto a mano lì dentro non viene trovato – una
  firma o un nome inserito a mano resta. Finora questa frase compariva
  solo per le pagine scansionate; un normale PDF con una firma
  incorporata non riceveva alcuna parola in merito.
- **Un segnaposto su sfondo immagine oscurato stava al margine sinistro
  della sua barra.** Se un valore viene trovato in un'immagine – ad
  esempio un nome digitato accanto a una firma scansionata –, l'area
  immagine deve essere oscurata a piena larghezza. Il segnaposto più
  corto lasciava accanto nero nudo, che sembrava il risultato di due
  operazioni. Ora sta centrato sulla barra.

## 0.10.41-alpha.20260826 – 26 agosto 2026

### Nuovo

- **Dopo il periodo di prova, una finestra ricorda la licenza una volta
  per avvio.** Compare cinque minuti dopo l'avvio – non subito, in modo
  da non ostacolare nessuno prima del primo gesto – e attende finché è in
  corso una bonifica. Da lì un percorso porta all'acquisto e uno
  all'inserimento di una chiave già acquistata; „Più tardi" la chiude non
  appena i cinque secondi nel pulsante sono trascorsi. Non viene bloccato
  nulla: il livello gratuito continua a funzionare come prima.

- **Il tempo di attesa prima di un'esecuzione nel livello gratuito dura
  ora dieci invece di trenta secondi.** Deve ricordare la licenza, non
  fermare il lavoro.

- **Tutti e tre gli avvisi sulla licenza hanno ora lo stesso aspetto.**
  Tempo di attesa, promemoria negli ultimi giorni di prova e avviso dopo
  il periodo di prova portano la stessa striscia, la stessa struttura e
  gli stessi pulsanti; il tempo residuo sta ora nel pulsante invece che
  come numero grande accanto.

- **L'elenco dei rilevamenti nell'anteprima sta di nuovo uno sotto
  l'altro.** Da nove valori era a due colonne; scorrendo, l'occhio salta
  tra due corsie, e qui si decide riga per riga. Chi preferisce le due
  corsie le riattiva in basso a sinistra nella finestra – la scelta resta
  memorizzata, e al cambio i valori già deselezionati restano
  deselezionati.

- **Il livello IA è ora aperto a chiunque colleghi un proprio server
  IA.** „Impostazioni → IA" raccoglie tutto: il collegamento, cosa l'IA
  può fare, cosa le viene affidato – e sopra l'interruttore per il
  livello con controprova, non appena è inserito un server. Un modello
  linguistico che calcola sulla propria postazione resta trattenuto:
  richiede diversi minuti per dieci pagine ed è quindi impraticabile per
  l'uso quotidiano.

- **Si può collegare un'IA propria.** Invece del modello linguistico
  incluso, può rispondere un modello più grande su un altro computer – su
  un server in azienda o una postazione con scheda grafica potente.
  Serve un servizio con interfaccia compatibile OpenAI (Ollama, LM
  Studio, llama.cpp-server, vLLM, LocalAI); si configura sotto
  „Impostazioni → IA propria" con un controllo connessione che interroga
  davvero il modello, misura la velocità e stabilisce la forma di
  risposta possibile. Più sezioni di testo vengono elaborate in questo
  caso contemporaneamente invece che in sequenza.

- **Cosa l'IA può fare e cosa le viene affidato è ora configurabile.** Tre
  interruttori decidono su verifica dei casi limite, ricerca autonoma e
  ricerca nel testo scorrevole; l'istruzione al modello è riportata
  letteralmente, si può integrare con termini aziendali e si può
  ripristinare al valore predefinito con un pulsante.

- **Se il testo lascia in questo caso la propria rete, viene avvisato
  prima di ogni esecuzione.** Maskuro riconosce dall'indirizzo se il
  server IA si trova in azienda, e nomina espressamente un fornitore
  noto. L'avviso si può disattivare, ma solo tramite la conferma esplicita
  di essere autorizzati a questa trasmissione, e solo per esattamente
  questo indirizzo. Sul procedimento questo non cambia nulla: la
  trasmissione resta comunque nel registro e nel rapporto di controllo di
  ogni file. Sulla riga di comando non viene chiesto, ma bloccato – lì
  serve `--ki-auswaerts-erlauben`.

- **L'anteprima prima della sostituzione è ora attiva per impostazione
  predefinita nelle nuove installazioni e vale ora anche per i contenuti
  degli appunti bonificati espressamente nonché per testo e immagini
  incollati nel programma.** Nei lotti di documenti compare comunque
  esattamente un'anteprima per documento con tutte le pagine; la bonifica
  immediata silenziosa di copie brevi non apre volutamente alcuna
  finestra.

- **I rilevamenti si possono attivare e disattivare nell'anteprima
  sull'intera riga colorata.** La spunta è ora grande e ad alto
  contrasto; inoltre un campo di stato mostra „Sostituisci" oppure,
  barrato, „Sostituisci", in modo che valori selezionati e deselezionati
  si distinguano subito anche su colori di affidabilità scuri.

- **Anche i PDF con controsguardo di sicurezza visibile aprono ora
  l'anteprima solo una volta per documento.** I termini deselezionati
  restano deselezionati per il successivo test di pagina; il suo
  controllo continua senza interrompere la stessa esecuzione con una
  seconda finestra di dialogo.

- **Le parole sostitutive hanno lo stesso aspetto nell'editor di
  correzione anche su pagine rasterizzate.** Se il segnaposto rosso si
  trova nei pixel invece che nello strato di testo PDF, riceve ora
  comunque la stessa area di sfondo colorata secondo l'affidabilità di un
  normale segnaposto di testo PDF.

- **Già l'anteprima prima della sostituzione mostra la necessità di
  controllo dei termini trovati.** Ogni riga porta lo stesso colore
  rosso-arancione-verde della successiva sostituzione nell'editor.
  All'interno di una categoria, la bassa affidabilità e i candidati rossi
  a falso allarme stanno in alto, i forti riscontri verdi in basso; le
  parità restano in ordine alfabetico. Se lo stesso valore proviene da
  più punti di rilevamento, per precauzione conta la loro valutazione più
  dubbia. I casi speciali non valutati stanno in giallo neutro tra rosso
  e arancione.

- **Il risultato si può ora copiare come file direttamente dall'editor di
  correzione.** „Copia risultato" mette la versione bonificata attuale
  negli appunti, senza chiudere l'editor e ricercare il file nell'elenco
  principale. Per una modifica manuale non ancora salvata, prima gira
  automaticamente l'intero percorso di salvataggio sicuro; „Copia
  immagine" resta come funzione separata per i soli pixel.

- **Le parole sostituite mostrano nell'editor a colpo d'occhio cosa
  andrebbe controllato per primo.** Una pura ipotesi del modello
  linguistico è rossa, anche se spaCy per questo segnala genericamente
  l'85 per cento. Ulteriori giudizi del modello non supportati restano al
  massimo arancioni; forti riscontri con nome possono diventare verdi. Il
  lavoro manuale e le assegnazioni più vecchie senza valutazione
  interpretabile restano gialli neutri. Anche le barre di oscuramento
  automatiche portano questi colori nell'anteprima dell'editor – ora
  anche quando la barra fa parte di una pagina PDF rasterizzata. Per
  questo l'assegnazione deve corrispondere e il precedente riquadro
  parola deve essere dimostrabilmente coprente nero; il grassetto normale
  non viene colorato. Nel PDF salvato, tutte le barre restano invariate,
  coprenti nere.

- **Ciò che viene deselezionato nell'anteprima si può memorizzare in modo
  permanente.** Dove togliete la spunta, dite: qui il riconoscimento si è
  sbagliato. Finora ciò valeva solo per questo unico documento. Ora
  compare sulla riga un interruttore „mai più"; premuto, il valore entra
  in modo permanente nell'elenco „Non rimuovere mai" e vale in futuro in
  ogni documento come non problematico. Sotto l'elenco sta scritto cosa
  diventa permanente, prima di premere „Sostituisci". La direzione
  opposta volutamente non esiste: ciò che è stato trovato una volta, il
  riconoscimento lo trova di nuovo.

- **Un pulsante ripristina tutte le impostazioni allo stato di
  consegna.** Si trova in basso a sinistra nella finestra delle
  impostazioni e chiede prima conferma. I vostri file, la vostra licenza,
  le vostre regole di riconoscimento proprie e l'avvio automatico restano
  intatti; ciò che la vostra amministrazione impone continua a valere.
  Ogni impostazione che diverge dallo stato di consegna porta inoltre la
  dicitura „modificato" – così si vede a colpo d'occhio cosa è stato
  modificato.

### Modificato

- **Un risultato non viene più depositato da solo – solo al
  salvataggio.** Un'esecuzione dalla finestra scrive la sua versione
  bonificata prima in un luogo provvisorio; il file „…_bereinigt" accanto
  all'originale nasce solo quando premete „Salva". Fino ad allora il
  risultato si può visualizzare, correggere e copiare. Ogni riga
  completata ha per questo un pulsante Salva, sotto l'elenco sta „Salva
  tutti", e nell'editor vale Ctrl+S. Chi svuota l'elenco o chiude il
  programma viene interrogato; ciò che nessuno deposita non resta da
  nessuna parte. „Mostra nella cartella" è bloccato prima del salvataggio
  – il luogo provvisorio non è una destinazione a cui indirizzare
  qualcuno. Il file di assegnazione viene salvato insieme.

  Nelle impostazioni sotto „Programma", „Deposita subito i risultati
  accanto all'originale" ripristina il comportamento precedente. Riga di
  comando, monitoraggio cartella e sorveglianza appunti depositano
  invariati subito – lì non c'è nessuno che possa salvare.

- **La barra degli strumenti dell'editor di correzione è stata
  riordinata.** La modalità di apprendimento sta ora all'estremità destra
  accanto a lente di confronto e „Valori sostituiti" – i tre interruttori
  che attivano e disattivano una modalità operativa stanno così insieme.
  „Applica a tutte le pagine" si è spostato accanto alle tre forme di
  oscuramento, perché agisce solo lì. „Copia risultato", „File –
  Ripristina" e „Applica a tutte le pagine" fanno a meno dell'etichetta;
  il loro nome resta nel tooltip e nel menu. Tra „Sostituisci" e
  „Recupera originale" c'è un separatore: i due sono direzioni opposte e
  affiancati sembravano due varianti dello stesso strumento.

- **L'icona di „Copia risultato" mostra ora un documento.** Due fogli con
  angolo piegato e righe di testo invece di due fogli identici con una
  piccola freccia d'angolo. „Copia immagine" porta in cambio il simbolo
  immagine, in modo che entrambi siano distinguibili senza etichetta. Il
  pulsante „Copia" nell'elenco risultati mostra lo stesso simbolo
  documento – deposita lo stesso file.

- **Le impostazioni sono ordinate e dotate di intestazioni.**
  „Riconoscimento" ha ora quattro sezioni: *Cosa viene rimosso*, *Come
  viene sostituito*, *Con quanta accuratezza si cerca* e *Prima e dopo
  l'esecuzione*. Riconoscimento volti e codici a barre/QR stanno con le
  immagini, dove si cercano; „Programma" è diviso in *File risultato*,
  *All'avvio*, *Aggiornamento*, *Visualizzazione* e *Segnalazioni a noi*,
  e il suffisso del nome del file risultato sta con i file risultato
  invece che tra lingua e aspetto.

- **Il riconoscimento avanzato è attivato di fabbrica**, anche prima che
  il suo modello linguistico sia caricato. Prima l'impostazione
  predefinita dipendeva dalla disponibilità del modello, e un computer
  appena configurato girava stabilmente sul livello più debole. La
  finestra di configurazione offre il modello sulla prima pagina per il
  caricamento e ne indica il costo accanto. Se manca, la spunta continua
  a dirlo, invece di simulare un livello che non funziona.

- **I due elenchi di termini si chiamano ora come ciò che fanno:**
  „Rimuovi sempre" invece di „Termini propri" e „Non rimuovere mai"
  invece di „Eccezioni".

- **La finestra di anteprima è più chiara.** Da nove valori sono a due
  colonne, le righe sono più basse, e il numero dei punti di rilevamento
  sta direttamente dietro il termine invece che al margine destro.

- **Nell'editor di correzione, Sostituisci precede Oscura** – nella barra
  degli strumenti, nel menu „Strumenti" e nel clic destro sulla pagina.
  Sostituisci è il caso normale: un segnaposto si può cliccare e
  recuperare, una barra no.

- **Meno pulsanti doppi nell'editor.** „Salva con nome …" e „Copia
  immagine" stanno ora solo nel menu File, con le loro consuete
  scorciatoie da tastiera. Nella barra ne resta uno ciascuno: Salva e
  „Copia risultato" – dove si salva sta comunque nella riga di stato e si
  può cambiare lì con un clic.

- **La sorveglianza appunti non viene più offerta al primo avvio.**
  Interviene in ogni operazione di copia del sistema; chi vede il
  programma per la prima volta non può valutarlo. Nelle impostazioni resta
  presente, con accanto la relativa clausola.

- **L'aspetto chiaro abbaglia meno.** Lo sfondo della finestra proveniva
  finora dallo stile di sistema rispettivo ed era così l'unica grande
  area che nessuno aveva deciso – sotto Windows quasi bianco. Ora è un
  bianco rotto, uguale su ogni sistema.

- **Il giro guidato e il manuale spiegano i colori.** Cosa significano
  rosso, arancione, verde e giallo dietro un valore sostituito sta ora
  come tappa propria nel giro guidato e come paragrafo nel manuale – in
  tutte le versioni linguistiche.

### Corretto

- **Manuale e FAQ mostravano segnaposto che non esistono più.** Dal
  passaggio alla forma corta, Maskuro scrive `[NAM1]`; nella guida
  restava scritto `[NAME1]`, e la frase „Predefinito è `[NAME1]`" era
  quindi semplicemente sbagliata. Nelle diciassette versioni tradotte
  c'era inoltre il marcatore **tedesco** invece di quello proprio – un
  lettore spagnolo vedeva `[NAME1]`, dove il suo programma scrive
  `[NOMB1]`. Lo stesso per l'estensione del file risultato: lì tutte le
  versioni promettevano `_bereinigt`, mentre il programma crea
  `_limpiado`, `_nettoyé` o `_除去済み`. Erano interessate anche la
  forma senza numero (nell'anonimizzazione tutto si chiama `[NAM]`, non
  `[NAME]`) e l'identificativo derivato dal valore nell'hashing.

- **La finestra di anteprima interrompe ora solo una volta per documento
  – e una seconda volta solo se davvero si aggiunge qualcosa di
  nuovo.** Un PDF viene letto da due parti: una volta dal flusso di
  contenuto e infine dalla pagina renderizzata visibile. Finora ognuna
  delle due chiedeva per conto proprio. Ora vale: ciò che avete deciso
  nella prima finestra continua a valere, e i valori già presenti lì non
  tornano. Se invece il controllo visivo delle pagine completate trova
  qualcosa che prima non stava da nessuna parte, vi viene presentato di
  nuovo – da solo, senza i valori già decisi.

- **La finestra di anteprima dice ora in base a cosa decidere.** Invece
  di „Togliere la spunta = il valore resta" – che dice cosa *fa* la
  spunta, ma non quando toglierla – ora c'è scritto: spunta via ovunque
  non ci sia un valore personale; lì il riconoscimento si è sbagliato.
  Inoltre ogni finestra indica il passaggio di controllo da cui
  provengono i suoi valori.

- **I segnaposto hanno lo stesso aspetto in tutto il documento.** Su
  pagine ricostruite come pagine immagine tramite il percorso OCR, i
  segnaposto visibili venivano finora composti in carattere macchina da
  scrivere – „[PLZ4]" appariva largo e con grazie accanto a un „[NAM1]"
  stretto della stessa pagina. Ora portano lo stesso carattere senza
  grazie di ovunque altro e non vengono più composti più larghi di quanto
  previsto in fase di adattamento. Lo strato di ricerca invisibile
  mantiene il proprio carattere – ha bisogno di misure affidabili, non
  di un aspetto.

- **Nella barra degli strumenti dell'editor non ci sono più doppi
  separatori.** Dove un intero gruppo di strumenti viene meno per il tipo
  di file aperto – in un PDF ad esempio anteprima pagina e rendering –
  finora restavano entrambi i trattini attorno al vuoto.

- **Nel recupero non resta più occasionalmente solo un punto bianco.**
  Un testo originale già ripristinato esattamente non viene più coperto
  di bianco dal riquadro largo e unificato del suo segnaposto rimosso.
  Nei recuperi misti di testo e immagine, il testo viene inoltre inserito
  in modo invisibile solo se l'immagine di pagina porta già visibilmente
  esattamente questo stato originale. Vale per cornice, pannello dei
  rilevamenti e allegati PDF.

- **„Recupera originale" non offre più inutilmente di rasterizzare la
  pagina.** Il controllo severo del testo residuo resta attivo per
  oscurare e sostituire. Nel recupero viene omesso: lì il contenuto
  originale torna volutamente ad aggiungersi, e parole vicine invariate
  nella cornice di recupero estesa non erano un errore di bonifica, ma un
  falso allarme.

- **Il giro guidato nell'editor spiega ora „Sostituisci" e „Recupera
  originale" come passaggi propri.** Entrambi gli strumenti vengono
  evidenziati direttamente nella barra e descrivono che una cornice
  tracciata inserisce un segnaposto oppure recupera il contenuto
  originale di quel punto dal file sorgente.

- **Anche i segnaposto specifici per paese restano ora entro al massimo
  quattro lettere.** Questi tipi mancavano finora nel catalogo di sigle
  centrale e potevano quindi apparire ancora per esteso, ad esempio
  `[UMSATZSTEUER_ID1]`. Le nuove esecuzioni scrivono per questo `[UID1]`;
  tutti i tipi tedeschi e inglesi riconosciuti automaticamente restano in
  questo caso univoci. Anche le sigle calcolate da sole di altre lingue
  di interfaccia non crescono più oltre quattro caratteri in caso di
  omonimia. Le etichette di regole proprie restano invariate, denominate
  come sono state inserite.

- **Sostituisci usa ora tutto lo spazio di riga effettivamente libero,
  prima di oscurare.** Il precedente limite rigido al triplo della
  larghezza originale della parola generava barre anche in campi modulo
  in gran parte vuoti. Anche i rilevamenti del controsguardo OCR visibile
  ricevono ora, con testo PDF occupato, un segnaposto leggibile; restano
  neri i contenuti puramente immagine, di annotazione e vettoriali, la
  modalità di oscuramento scelta nonché i veri spazi stretti in cui non
  entra nemmeno una forma abbreviata univoca.

- **Un segnaposto già visibile non viene più riscritto una seconda volta
  in rosso durante la rasterizzazione di sicurezza.** La rasterizzazione
  riprende ora la sostituzione esistente dall'immagine di pagina e crea
  solo una copia di ricerca invisibile. Se una barra di sicurezza deve
  coprire esattamente questo punto, viene rinnovato l'intero riquadro
  segnaposto effettivo invece del suo ancoraggio originale più corto.

- **„Recupera originale" marca ora solo obiettivi sicuri nella cornice
  tracciata.** Tutti i termini sostituiti al suo interno si illuminano
  singolarmente e con precisione; il testo scorrevole invariato resta
  intatto. Anche le vere barre di oscuramento vettoriali vengono marcate
  singolarmente, se sotto la loro area PDF nera si trova testo
  originale. Su pagine rasterizzate, l'anteprima rinuncia volutamente a
  una presunta area a barra: la precedente ricerca a pixel univa lì
  lettere, sottolineature e linee di tabella in grandi aree rosse in
  punti sbagliati. Il ripristino stesso non ne è toccato.

- **Nel ripristino su pagine rasterizzate il testo torna di nuovo.**
  Recentemente restava lì un punto vuoto con rettangoli colorati sopra.
  Il testo recuperato stava nel documento, ma veniva coperto dallo sfondo
  bianco di un segnaposto disegnato più indietro nella costruzione della
  pagina.

- **I colori di controllo non si sovrappongono più più volte.** Lo stesso
  punto veniva colorato per ogni voce dell'assegnazione – su una pagina
  cinque veri punti di rilevamento, ognuno colorato cinque volte, finché
  dal marcatore pallido non nasceva un blocco saturo. E non compaiono più
  su parole che non sono state affatto sostituite: se il valore originale
  sta ancora sulla pagina, lì non c'è più nemmeno il marcatore.

## 0.10.40-beta.1 – 24 agosto 2026

### Corretto

- **Le barre di oscuramento nell'editor hanno ora un margine di
  sicurezza.** Cornici a livello di parola, riga e libere coprono anche
  glifi sporgenti e pixel di bordo levigati; un controllo di rendering
  garantisce inoltre che non restino né resti visibili né testo
  originale leggibile.

- **I testi sostitutivi restano leggibili e uniformemente brevi.** Nuovi
  nomi, indirizzi e termini liberi compaiono ad esempio come `[NAM1]`,
  `[ADR2]` e `[BEG3]`. Il limite minimo fisso è di 4,5 punti; in caso di
  spazio insufficiente si abbrevia prima e si amplia lo spazio di
  scrittura utilizzabile. Le vecchie assegnazioni con segnaposto lunghi
  restano leggibili e recuperabili.

- **Le sostituzioni multiparola dal pannello dei rilevamenti sono protette
  contro marcatori doppi e resti dell'originale.** Il test di regressione
  passa con e senza segnaposto numerati; per ogni punto di rilevamento
  resta esattamente un'unica assegnazione comune.

- **I contenuti degli appunti recuperati non vengono bonificati di nuovo
  immediatamente su macOS.** Anche quando la firma di sistema cambia solo
  con ritardo dopo la scrittura, Maskuro riconosce in modo affidabile il
  proprio contenuto.

### Nuovo

- **L'editor può ripristinare un file completamente alla versione iniziale
  appena bonificata.** „File – Ripristina" scarta, dopo una conferma,
  tutte le correzioni della scheda attuale, compresi elenco sostituzioni e
  contatori. Il comando è bloccato senza modifiche e a sua volta si può
  annullare con „Annulla".

- **Le date spostate mantengono ora la loro cronologia in modo affidabile
  su più file.** Lo scostamento comune viene ancorato in modo permanente
  nelle regole già all'attivazione della strategia; inoltre lo
  scostamento non può più essere di zero giorni, lasciando così
  inosservata la data reale.

- **Il lavoro manuale sui PDF copre ora l'intero flusso professionale di
  oscuramento.** Termini singoli, elenchi e modelli regolari si possono
  cercare e oscurare in modo sicuro nel PDF aperto o su tutti i PDF di
  una cartella; intere pagine e intervalli di pagina sono selezionabili
  direttamente. Colore, area bianca neutra, testo di sovrapposizione,
  carattere, allineamento e ripetizione hanno un'anteprima, i codici
  riutilizzabili si possono gestire nonché importare ed esportare. La
  bonifica PDF rimuove a scelta tutti i contenuti nascosti tramite
  ricostruzione completa oppure classi di dati selezionate. La scelta più
  sicura è chiaramente consigliata, i modelli di ricerca non validi
  vengono spiegati e le esecuzioni su cartella scrivono esclusivamente
  copie del risultato.

- **La statistica d'uso volontaria mostra ora installazioni e cambi di
  versione.** Maskuro genera per questo un identificativo di
  installazione casuale, salvato localmente. Non contiene dati su
  dispositivo, utente o licenza; il server salva solo il suo valore
  SHA-256. La statistica resta completamente disattivabile nelle
  impostazioni.

- **Il giro guidato è ora un esercizio guidato attraverso entrambe le
  finestre.** Inserisce da solo il documento di esercizio inventato
  nell'elenco, spiega il percorso fino alla bonifica e prosegue
  automaticamente nell'editor dopo l'esecuzione. Chi interrompe il giro
  guidato termina anche questo proseguimento.

- **Vengono riconosciute aziende di altri quindici ordinamenti
  giuridici.** Chi bonifica documenti da Baltico, Belgio, Scandinavia,
  Repubblica Ceca, Polonia, Europa sud-orientale, Singapore, Brasile o
  Messico non perde più nomi di azienda perché la loro forma giuridica
  era sconosciuta – nuovi tra questi sono tra l'altro OÜ, MTÜ, SIA, VZW,
  ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s., S.K.A., Pte. Ltd. nonché S.A.
  de C.V. e S. de R.L.

### Modificato

- **Le barre degli strumenti dell'editor usano ora lo spazio in modo più
  mirato.** Icone standard univoche e forme di strumento riconoscibili
  direttamente stanno nella barra senza testo ripetitivo; le azioni
  ambigue mantengono il loro nome. Sotto „Visualizza" si può disattivare
  „Mostra etichette strumenti" per ridurre entrambe le barre
  completamente a icone. Tooltip e menu restano completamente etichettati,
  la scelta viene memorizzata.

- **La modalità di apprendimento è ora visibile in modo permanente nella
  barra degli strumenti.** Si può attivare e disattivare lì direttamente,
  anche quando il pannello dei valori sostituiti è chiuso. Barra degli
  strumenti, menu Strumenti e la precedente spunta nel pannello mostrano
  sempre lo stesso stato.

- **„Ripristina" sulla lente di confronto ripristina ora solo il suo
  zoom.** Il pulsante ripristina il valore predefinito del 125 per cento,
  senza agganciare la lente, spostarla o modificarne la dimensione della
  finestra. Per l'intera configurazione resta responsabile „Ripristina
  visualizzazione".

- **Errori e richieste si possono ora segnalare anche tramite il pulsante
  Guida.** „Segnala un errore …" e „Esprimi un desiderio …" stanno lì ora
  come nel menu Guida classico; entrambe le vie aprono la già esistente
  segnalazione di errore sicura rispettivamente l'elenco desideri
  pubblico.

- **Il menu della barra delle applicazioni è più corto e ordinato in modo
  più chiaro.** I due comandi con scorciatoia globale – bonifica appunti
  e schermata – stanno ora direttamente uno sotto l'altro con una colonna
  di scorciatoie comune a destra. „Ripristina l'ultimo contenuto
  originale" viene a mancare lì; il pulsante di ripristino più
  comprensibile resta disponibile nella finestra principale.

- **Le pagine legali sono raggiungibili direttamente sotto „Guida →
  Aspetti legali".** Il sottomenu porta a condizioni di licenza,
  informativa sulla privacy, note legali e condizioni generali su
  maskuro.com. Le indicazioni sul recesso restano all'acquisto sul sito
  web.

- **I PDF oscurati a mano vengono ricostruiti completamente al
  salvataggio.** Restano visibili le pagine e il loro strato di ricerca
  riletto; metadati, allegati, segnalibri, commenti, valori di modulo,
  livelli nascosti, indici di ricerca, script, contenuti ritagliati e
  contenuti nascosti in altri oggetti non vengono ripresi nel file di
  output. Testo e grafica vettoriale sono composti dopo di ciò da pixel –
  è il prezzo del confine dimostrabile verso l'albero oggetti PDF
  estraneo.

- **Ctrl+Maiusc+B ora cattura per impostazione predefinita una schermata
  con Maskuro su tutti i sistemi.** Il tasto Stampa e le combinazioni con
  esso restano possibili come assegnazione propria. Nel menu dell'icona
  della barra delle applicazioni, le scorciatoie globali stanno ora a
  destra accanto ai rispettivi comandi. Le assegnazioni salvate proprie
  restano invariate.

- **L'editor si avvia con pagine e lente di confronto a sinistra.** Il
  pannello pagine sta in alto, la lente sull'originale aperta subito
  sotto; i valori sostituiti restano a destra. Una disposizione propria
  salvata deliberatamente ha comunque la precedenza.

- **Il documento di esercizio non sta più permanentemente nella finestra
  principale.** Fa parte dell'esercizio guidato e resta inoltre
  raggiungibile sotto „Guida".

- **Il primo avvio porta direttamente all'esercizio pratico.** La guida
  rapida illustrata non viene più offerta come secondo percorso
  d'ingresso, contenutisticamente duplicato; resta raggiungibile in ogni
  momento sotto „Guida → Guida rapida".

- **L'icona inattiva nella barra delle applicazioni resta a colori
  pieni.** Mostra ora lo stesso scudo Maskuro deciso della modalità
  appunti attiva; solo con la sorveglianza attiva si aggiunge il punto
  luminoso verde.

- **Il documento di esercizio resta in Maskuro.** Il pulsante di ingresso
  genera il PDF inventato e lo inserisce direttamente nell'elenco file,
  ma non avvia più alcun visualizzatore PDF aggiuntivo.

- **La ricerca nella finestra di correzione resta fluida durante la
  digitazione.** Lo spazio per il contatore dei rilevamenti viene
  riservato già all'apertura; il suo primo testo non modifica più la tela
  e non genera una nuova esecuzione di rasterizzazione PDF.

- **I nomi di produttore in indicazioni di modello restano visibili.** Una
  voce come „Modello: TRILUX o equivalente" descrive la merce richiesta
  e non viene più oscurata come azienda solo a causa di questa dicitura.
  I campi fornitore, azienda e produttore non ne sono toccati.

- **Le misurazioni del corpus contano i rilevamenti oscurati troppo
  ampiamente come falsi allarmi.** Se Maskuro rimuove il nome atteso ma
  in tal caso porta via anche parte della frase, ora sale il numero di
  falsi allarmi. Il rapporto indica inoltre separatamente le
  eccedenze; i precedenti numeri di falsi allarmi non sono quindi
  direttamente confrontabili.

### Corretto

- **I termini tecnici e amministrativi da documenti originali tedeschi
  vengono oscurati più raramente come nomi o luoghi.** Dotazioni di
  veicoli, righe di posizione e totale, termini di appalto e privacy,
  riferimenti di legge nonché nomi file di materiali pubblici vengono
  frenati solo nel loro contesto tematico documentato. Una dieresi persa
  nel riconoscimento testo in „Marz 2026" resta protetta come mese;
  „Marz" senza riferimento a una data può continuare a essere un vero
  nome o luogo.

- **„Recupera originale" prende subito l'intera larghezza necessaria.**
  Se la cornice colpisce solo una parola di un valore assegnato, Maskuro
  la amplia autonomamente sulla base dell'assegnazione e della riga
  originale all'intero dato – ad esempio da „Planungs" a „Nordlicht
  Planungs GmbH". La cornice successivamente afferrabile mostra allo
  stesso modo l'intera larghezza effettivamente recuperata.

- **„Recupera originale" mostra ora le barre nere come obiettivo
  univoco.** Al passaggio o al trascinamento, l'intera barra riconosciuta
  si illumina di rosso con contorno di contrasto chiaro, invece di un
  riquadro di testo accanto difficilmente attribuibile. Vale anche per le
  pagine rasterizzate, in cui la barra è composta solo da pixel.

- **Il giro guidato dell'editor non salta più tappe quando i pannelli
  erano chiusi.** Per la guida, Maskuro apre e ordina temporaneamente da
  solo pannello pagine, lente di confronto e valori sostituiti. Dopo
  „Fine" o un'interruzione torna la disposizione personale. Se uno
  strumento non è fondamentalmente disponibile per un tipo di documento,
  la sua spiegazione resta come punto di sosta testuale, invece di
  sparire inosservata.

- **„Sostituisci" resta visibile anche nel ripiego di sicurezza PDF.** Se
  Maskuro doveva ricostruire una pagina come immagine a causa di un
  carattere residuo o di un flusso di testo danneggiato, le sostituzioni
  corrette restavano visibili solo nello strato di ricerca invisibile e
  sulla pagina c'erano barre nere. I valori sostitutivi effettivamente
  impostati vengono ora mantenuti visibili in rosso e ricercabili
  attraverso tutte le ricostruzioni raster e OCR.

- **Gli avvisi sopra la versione bonificata restano leggibili nell'aspetto
  scuro.** Intestazione versione, riga di comando e introduzione ora
  ereditano il loro colore del carattere direttamente dalla finestra Qt
  effettivamente rappresentata.

- **Le cornici di oscuramento sono di nuovo sopra il testo nelle pagine
  PDF rasterizzate.** I riquadri di parola invisibili erano, a seconda
  del carattere originale, più stretti delle lettere visibili. Ne
  risultavano lacune nella barra o l'ultima lettera restava leggibile. I
  riquadri mantengono ora larghezza, altezza e direzione di scrittura
  della parola visibile.

- **„Novità" ricomincia di nuovo dall'alto.** La finestra di dialogo del
  changelog posiziona ora esplicitamente cursore di testo e barra di
  scorrimento all'inizio dopo la costruzione completa della finestra,
  invece di partire, a seconda dello stato di Qt, in mezzo alle novità.

- **La chiusura durante il riconoscimento parole della scansione resta
  silenziosa.** Un'esecuzione OCR in background appena completata non
  invia più a una finestra di correzione già chiusa.

- **Le indicazioni di tempo relative non vengono più scambiate per
  nomi.** Espressioni fisse come „oggi", „ieri", „domani" e „la prossima
  settimana" ora Maskuro le conosce dai dati calendariali ufficiali della
  rispettiva lingua del documento.

- **La chiusura durante il primo caricamento del modello ripulisce in
  modo pulito.** Chi chiude Maskuro o la finestra di correzione subito
  dopo l'apertura non lascia più un thread ancora al lavoro nel
  riconoscimento linguistico nativo durante la chiusura del processo.
  Ciò impedisce il rapporto di crash sporadico alla chiusura; un
  caricamento già in corso viene completato in modo ordinato.

- **Le finestre di dialogo di avvio ritardate non compaiono più dopo la
  chiusura.** Chi chiude la finestra principale poco dopo l'avvio non
  vede più mostrarsi in seguito, in modo invisibile o ritardato, la
  domanda sul miglior riconoscimento, le novità o l'introduzione.

- **HTML ed e-mail mantengono i loro fine riga.** Su Windows, la
  serializzazione HTML mescolava dopo bonifica e recupero LF e CRLF.
  Contenuto e formattazione erano corretti, ma il file non più identico
  byte per byte. I file HTML e i messaggi MIME riprendono ora di nuovo
  la scrittura della loro fonte.

- **I nomi di azienda con una preposizione restano completi.** Dietro un
  pronome, Maskuro tagliava nomi come „Gesellschaft für Systemtechnik
  mbH" o „Bank für Arbeit und Wirtschaft AG" alla parola „für". L'intero
  nome dell'azienda viene ora riconosciuto; veri incipit di frase come
  „Siamo assicurati presso Alpha GmbH" restano visibili.

- **I nomi di azienda cinesi restano completi prima della loro forma
  giuridica.** Un componente del marchio interpretabile come verbo
  poteva, nonostante l'aggiunta univoca „有限公司", scartare l'intero
  nome. Nelle scritture senza maiuscole e minuscole, l'ancora ufficiale
  di forma giuridica ha ora la precedenza su questo confine incerto di
  categoria grammaticale.

- **Le pagine PDF diventavano immagini senza necessità.** Nei PDF a più
  pagine le cui pagine condividono un elenco caratteri – come lo creano
  i generatori comuni –, dopo la prima pagina tutte le successive
  perdevano il riferimento ai loro caratteri. La conseguenza era
  doppia: le dieresi non erano più ricercabili nel risultato
  („Auftragsbestätigung" non si trovava), e il controllo successivo
  riteneva quindi trascurate lettere che sulla pagina non erano mai
  esistite – rasterizzava pagine di testo integre in immagini, così non
  più ricercabili, non più copiabili e notevolmente più grandi. Nel
  campione di controllo ciò colpiva quattro pagine su diciassette.
- **Una virgola da sola non genera più una rasterizzazione.** Se un'area
  di rilevamento termina alla parola, il segno di punteggiatura accanto
  rientra ancora appena al suo interno. Una virgola o un punto non è
  però un dato trascurato, e la rasterizzazione costa l'intera pagina.
  Lettere e cifre restano invariate un motivo per correggere.

## 0.10.38-alpha.20260824 – 24 agosto 2026

### Nuovo

- **I nomi di azienda senza forma giuridica vengono ora riconosciuti se la
  loro etichetta li nomina.** „Fornitore: Kranzbichler Handels GmbH"
  veniva sempre già rimosso – la forma giuridica rivela l'azienda.
  „Fornitore: Dehner Märkte" restava, e in offerte, bandi di gara e
  ordini il fornitore sta per lo più esattamente così. Lo stesso vale
  per „Azienda:", „Produttore:", „Modello:", „Datore di lavoro:" e i
  loro equivalenti in altre otto lingue, e anche quando l'etichetta sta
  da sola sulla sua riga e il nome sotto.

  Ciò che dietro l'etichetta *non* è un'azienda resta intatto:
  „Fornitore: vedi allegato" non viene oscurato – altrimenti ci sarebbe
  scritto „Fornitore: [ORGA1]", e ciò affermerebbe un nome che non è mai
  esistito. Etichette dietro cui altrettanto spesso c'è una persona
  („Cliente:", „Committente:") non sono volutamente incluse.

- **Un'immagine inserita si può ora anche modificare.** Nella finestra
  „Bonifica immagine", accanto a „Copia risultato" c'è un pulsante *Modifica
  nell'editor*: l'immagine viene bonificata e poi aperta per oscurare,
  annotare ed evidenziare successivamente – lo stesso percorso di una
  schermata.

- **I numeri dietro la loro etichetta vengono trovati anche quando
  nominano un partner commerciale.** Finora cadevano numeri cliente,
  contratto e personale; ora anche numero debitore, creditore e
  fornitore, il numero datore di lavoro austriaco, la registrazione ANKÖ
  e il numero WEEE, EAR ed EPR di un produttore – sia in tedesco sia in
  inglese. Inoltre Maskuro comprende ora la scrittura di intestazioni di
  offerta composte con spazio prima dei due punti („Kunden-Nr : K903944").
  Numeri articolo, ordine, commessa, offerta e fattura restano comunque
  intatti: nominano il processo o la merce, non la persona. Chi vuole
  comunque rimuoverli li registra come modello di ricerca proprio.

- **Ora vedete quanto tempo ha richiesto un file.** Sulla riga completata
  sta la durata accanto alla lingua riconosciuta („completato · Tedesco ·
  2,4 s"), nel riepilogo quella dell'intera esecuzione, nella sezione
  cifre la somma – e nel rapporto di controllo sta come campo proprio.
  Con più file, la riga rivela quale di essi ha richiesto il tempo.

- **Le scritture non supportate dall'OCR di sistema si possono leggere in
  alternativa con un file linguistico presente.** Finora valeva: se il
  riconoscimento testo nativo non padroneggia una scrittura (sul Mac ad
  esempio il devanagari), nel risultato compariva „Le immagini NON sono
  state verificate", e i dati nell'immagine restavano. Ora interviene il
  riconoscimento testo incluso, se è disponibile il file linguistico
  adatto. Poiché un'immagine letta così è meno sicura di una verificata
  normalmente, ciò è indicato nel risultato: „letto con il metodo
  alternativo – si prega di controllare". Misurato su uno stato
  intermedio storico della prova hindi: **dieci dati trovati in più e
  quattro falsi allarmi in meno** (64% → 73%). Il valore finale attuale
  sta più sopra e non va quindi confuso con questo.

- **Il riconoscimento testo chiede la lingua giusta.** Per tutte le
  lingue di documento tranne tedesco e inglese veniva finora usato il
  modello di riconoscimento inglese, anche quando era disponibile il
  file linguistico adatto. Su Windows ciò riguardava ogni lingua – greco,
  giapponese o hindi venivano letti lì con il modello inglese.

- **Un assistente di configurazione al primissimo avvio.** (Chi ha già
  usato Maskuro non lo riceve – „primo avvio" significa primo avvio, non
  primo avvio dopo questo aggiornamento.) Tre domande invece di sei
  immagini: la lingua dei vostri documenti, se il testo nelle immagini
  viene letto insieme, e come volete raggiungere Maskuro nella vita
  quotidiana. Alla fine restano i tre percorsi – documento di esercizio,
  giro guidato o la guida rapida illustrata. Tutto si può saltare, e
  „Guida → Rifai la configurazione" lo richiama.

- **F1 apre il manuale al capitolo giusto.** Nella finestra principale,
  nelle impostazioni (lì a seconda della pagina), nella finestra di
  scansione e nella gestione lingue; nella finestra di correzione tramite
  Maiusc+F1, perché F1 lì mostra da sempre le scorciatoie da tastiera.
  Finora la guida iniziava sempre in cima, con 25 capitoli.

- **Nuovo primo capitolo del manuale: „Iniziare in tre minuti".** Quattro
  passi, non serve altro per un documento – in tutte le 18 versioni
  linguistiche.

- **Un giro guidato attraverso la finestra.** „Guida → Giro guidato della
  finestra" mette in risalto un elemento di comando dopo l'altro e
  scrive una frase accanto – nella finestra principale otto tappe, nella
  finestra di correzione sette. A differenza della guida rapida
  illustrata, spiega la finestra davanti a cui siete seduti in quel
  momento. Interrompibile in ogni momento con Esc.

- **Un documento di esercizio per provare senza rischi.** Sotto l'area di
  deposito c'è ora „Apri documento di esercizio" (anche nel menu Guida).
  Crea un foglio inventato – nome, indirizzo, numero di telefono, IBAN,
  numero di previdenza sociale – e sul foglio sta scritto contemporaneamente
  cosa potete farne e cosa vedrete dopo. Nessuna parola appartiene a una
  persona reale; il primo documento che inviate a Maskuro non deve quindi
  essere uno vero.

- **„Verifica soltanto …" sta ora accanto a „Bonifica".** Mostra dove si
  trovano dati personali – file, tipo e numero – senza modificare o
  scrivere nulla. Chi ha depositato un documento può così controllare
  prima di bonificare. Finora questo percorso stava solo nel menu File
  sotto „Scansiona cartella …" e passava per un'intera cartella invece
  che per i file depositati.

- **Se non è stato trovato nulla, ora c'è scritto a cosa può essere
  dovuto.** Ad esempio: nel file ci sono immagini, ma „Verifica anche il
  testo nelle immagini" è disattivato. Oppure: la lingua impostata non
  corrisponde a quella del documento. E se non si applica nulla di
  tutto ciò, Maskuro lo dice anche.

- **La finestra di correzione vi accoglie la prima volta con tre
  frasi:** cliccare oscura una parola, trascinare un'area, a destra
  stanno i valori sostituiti. „Capito" toglie l'avviso in modo
  permanente; „Guida → Mostra di nuovo l'introduzione" lo richiama.

- **Cliccare le parole ora funziona anche su pagine scansionate.**
  Finora si potevano cliccare le parole solo dove il PDF porta con sé
  uno strato di testo – con una scansione non funzionava, e nello stesso
  documento poteva cambiare da pagina a pagina. Tali pagine vengono ora
  lette una tantum dal riconoscimento testo; dopo si cliccano le parole
  come ovunque altro. La riga di stato indica cosa sta succedendo.

- **Il pannello pagine è di nuovo un'area piena.** Finiva a metà della
  sua colonna: barra del titolo tagliata, accanto una striscia di colore
  diverso, e la pagina attuale era riconoscibile solo da un riquadro
  colorato dietro il suo numero. Ora riempie la sua colonna, si può
  allargare, e la pagina attuale è evidenziata come piastrella intera –
  con anteprima di pagina non alterata al suo interno.

- **I punti sostituiti si illuminano di giallo pallido.** Nell'anteprima
  pagina si vede così a colpo d'occhio dove è stato sostituito qualcosa –
  lo stesso colore che la lente di confronto usa sopra l'originale. La
  cornice rossa al passaggio del mouse resta invariata.

- **„Ripristina visualizzazione" nella finestra di correzione** (menu
  „Visualizza"). Chi ha spostato, staccato o chiuso il pannello pagine o
  l'elenco dei rilevamenti riporta così tutto dove stava al primo avvio.

### Modificato

- **I segnaposto sono più corti.** Da `[SOZIALVERSICHERUNGSNR_1]" nasce
  `[SVNR1]`, da `[ORGANISATION_1]` un `[ORGA1]`, da `[EMAIL_1]` un
  `[MAIL1]`. Il motivo non è estetico: un segnaposto più lungo del
  valore che sostituisce allarga la riga e in una colonna di tabella
  stretta non trova più posto affatto – lì finora restava una barra nera,
  che non dice più a nessuno che in quel punto c'era qualcosa. Dove
  esiste un'abbreviazione comune, sta quella (`[BLZ1]`, `[KFZ1]`,
  `[IBAN1]`). I risultati di esecuzioni precedenti restano utilizzabili:
  la vecchia scrittura continua a essere riconosciuta, e i file di
  assegnazione di ieri funzionano invariati.

- **L'icona del programma è ora uguale ovunque.** Nella barra dei menu
  del Mac compariva finora uno scudo monocromatico che il sistema stesso
  colorava di nero o bianco, nella barra delle applicazioni Windows uno
  verde o grigio. Ora ogni barra porta lo stesso scudo Maskuro blu. Come
  si vede se gli appunti sono sorvegliati resta ugualmente chiaro: se la
  sorveglianza è attiva, un punto verde siede sullo scudo; se è inattiva,
  lo stesso scudo appare pallido. Anche nelle dimensioni più piccole
  stanno ora entrambe le barre di oscuramento nello scudo – finora la
  barra delle applicazioni ne mostrava lì solo una.

- **I volti vengono riconosciuti con un modello le cui immagini di
  addestramento sono nate con consenso.** Viene ora distribuito
  MediaPipe BlazeFace (Apache-2.0); il rilevatore precedente resta
  incorporato e selezionabile, ma non viene più distribuito, perché la
  sua provenienza di addestramento non è chiarita in modo definitivo. Per
  il riconoscimento non cambia nulla: su 324 ritratti e 143 immagini
  senza volto, la nuova versione trova la stessa quantità con lo stesso
  numero ridotto di errori e richiede un terzo del tempo.

- **L'OCR è l'ancora di sicurezza per la garanzia PDF più forte.**
  L'esecuzione PDF normale la usa e genera la ricostruzione minima
  completa. Chi disattiva espressamente l'OCR ottiene il percorso oggetto
  più compatibile; interfaccia, messaggio finale e manuale dicono ora
  espressamente che questo percorso non offre la stessa architettura
  contro canali PDF nascosti sconosciuti.

- **Il blocco vendita ora blocca anche il modello YuNet finora
  allegato.** La licenza MIT del peso esatto resta documentata, ma non
  basta come rilascio prodotto conservativo per la catena di dati di
  addestramento pubblicamente visibile tramite WIDER FACE. Prima della
  vendita è necessario un chiarimento scritto o la sostituzione con un
  modello con catena di dati e pesi commerciale solida.

- **I nomi di azienda e organizzazione vengono ora rimossi di
  default.** Finora restavano, finché non li si richiedeva
  espressamente. Era l'impostazione sbagliata per una lettera
  commerciale: chi inoltra un'offerta non vuole leggervi il committente.
  „Kranzbichler Handels GmbH", „Institut für Bauphysik" e simili vengono
  quindi trattati come un nome. Chi ha bisogno diversamente lo
  disattiva nella finestra; sulla riga di comando l'interruttore si
  chiama ora `--ohne-organisationen`. Il vecchio `--mit-organisationen`
  continua a essere accettato e non fa più nulla, in modo che script e
  collegamenti esistenti non si rompano. Date e importi restano
  invariati esclusi.

- **Oscurare ha ora tre forme invece di due spunte.** „Parole", „Riga
  intera" e „Cornice libera" stanno come un'unica scelta affiancate –
  vale sempre esattamente una. Finora „Righe di testo" e „Riga intera"
  erano due interruttori indipendenti, entrambi premibili
  contemporaneamente, e la cornice libera non era affatto un pulsante,
  ma lo stato disattivato del primo. I tre stanno visibilmente presso il
  loro strumento e sono grigi finché è scelto un altro strumento.

### Migliorato

- **Il primo documento è pronto circa un secondo più velocemente.**
  Prima che inizi la bonifica, Maskuro determina la lingua del documento
  – e finora scaricava per questo gli elenchi di parole di tutte le 48
  lingue tramite un percorso che caricava molto più delle parole. Era
  circa metà del tempo di attesa fino al primo risultato. Il
  riconoscimento stesso è invariato: vede le stesse parole di prima,
  solo più velocemente. Ogni documento successivo non ne era comunque
  toccato.

- **I documenti con paragrafi molto lunghi vengono verificati più
  velocemente.** Con un paragrafo senza a capo, Maskuro lo rileggeva per
  intero per ogni punto trovato; ora basta una volta. Più lungo è il
  paragrafo, maggiore la differenza – misurato circa un settimo in meno
  di tempo di calcolo. Sul risultato non cambia nulla.

### Corretto

- **Con un'azienda spariva spesso mezza frase.** Se un nome di azienda
  stava nel testo scorrevole – „Informazioni sulla Gottwald GmbH & Co
  KG", „… (condizioni generali) della Musterbetriebe GmbH" – non veniva
  oscurato solo il nome, ma tutto ciò che stava prima fino all'inizio
  della frase. Il testo diventava così illeggibile, e sembrava che fosse
  stato oscurato a caso. I nomi di azienda che portano essi stessi un
  „für" o „und" („Bank für Arbeit und Wirtschaft AG") restano in questo
  caso invariati completi.

- **I nomi di azienda restavano nelle intestazioni, anche se erano
  rimossi nel testo.** In un'offerta, la sede dell'azienda stava ancora
  leggibile nell'immagine dell'intestazione – lo stesso luogo che
  Maskuro aveva oscurato nel testo scorrevole; nel testo ricercabile del
  risultato stava addirittura ancora presente in modo invisibile. Ciò che
  è stato rimosso una volta viene ora rimosso anche dove è presente solo
  come immagine. Funziona anche con loghi e marchi denominativi
  disegnati come grafica.

- **macOS chiedeva a ogni avvio la registrazione schermo**, anche se
  l'autorizzazione era stata concessa da tempo. L'avviso all'avvio
  provava una registrazione, e proprio questo fa comparire la finestra
  di dialogo di sistema. Ora all'avvio chiede solo Maskuro stesso, e
  solo una volta; il sistema chiede solo quando catturate davvero una
  schermata.

- **I termini tecnici venivano scambiati per luoghi e aziende.**
  „Einspeisepunkt", „Flachdach", „Verteileranlage", „Meldersockel" e
  decine di parole simili sparivano da offerte e capitolati. Maskuro li
  riconosce ora dalla loro radice: ciò che termina in „-anlage",
  „-punkt" o „-kanal" è una cosa. I nomi di luogo come Berlin, Melk o
  Wieselburg non hanno una tale radice e restano intatti – così come
  indirizzi come „Der Graben" o „Alter Markt".

- **I documenti giapponesi, coreani, cinesi, thailandesi e gujarati
  potevano far bloccare il programma.** Se un documento in una di
  queste cinque lingue conteneva un indirizzo internet senza „https://"
  davanti, la bonifica si interrompeva con un errore interno – a finestra
  aperta andava perso anche il resto del lavoro. Tutte le quarantotto
  lingue di documento selezionabili funzionano ora correttamente; se
  manca per una lingua il dizionario di frequenza, il dato resta in caso
  di dubbio invece di sparire.

- **Le etichette di campo proteggevano solo in tedesco e inglese.**
  „Reference" restava, l'italiano „Riferimento" e il portoghese
  „Referência" venivano rimossi come dato di luogo – stesso nome di
  campo, stessa riga, risultato diverso. Chi non lavora in inglese era
  quindi svantaggiato. Maskuro conosce ora in tutte le undici lingue
  curate gli stessi nomi di campo.

- **„Recupera originale" recuperava troppo su pagine scansionate.** Una
  cornice sopra una riga oscurata di un blocco indirizzo riapriva
  **l'intero blocco** – e la pagina restava lacerata: resti di barra
  stavano ancora, da cui sporgevano singole fini di parola. Il motivo era
  che le barre poste una sotto l'altra su una pagina rasterizzata si
  toccano e valevano quindi come un'unica area. Viene ora recuperata
  esattamente la riga a cui punta la cornice; le righe vicine restano
  oscurate, e la barra della riga colpita sparisce completamente.

- **Le indicazioni di quantità in liste di posizione venivano scambiate
  per indirizzi.** In una riga come „1.4  Kabelgraben  100,00  m",
  „Kabelgraben 100" veniva sostituito come via con numero civico. Tali
  righe ora restano; gli indirizzi reali – anche „Hauptplatz 1, 3250
  Wieselburg" – vengono riconosciuti invariati.

- **Davanti a un nome di azienda spariva mezza frase.** Da „Contratto
  tra la ditta Gottwald GmbH & Co KG e il committente." diventava
  „[ORGANISATION_1] e il committente." – l'inizio della frase era sparito,
  e con esso l'indicazione di cosa si trattasse. Ora cade solo il nome
  dell'azienda stesso. Dove il termine generico fa parte del nome
  („Deutsche Bank AG", „Universität Wien"), tutto resta come prima.

- **In un verbale restavano relatori il cui nome è al contempo una
  professione.** „Bauer:", „Koch:", „Weber:" davanti a un intervento
  venivano trascurati, „Gruber:" accanto no – Maskuro aveva finora
  bisogno di almeno un nome riconosciuto nel documento per leggere
  affatto le righe come interventi. Se il documento porta un titolo
  come „Verbale dei risultati" o „Resoconto", ora basta questo. Righe di
  promemoria („Attenzione: …", „Nota: …") restano intatte.

- **Un'etichetta di campo spariva insieme al suo valore.** Da „Progetto:
  Risanamento ed ampliamento centro comunale" nasceva un unico
  segnaposto – era sparita anche la parola „Progetto:", e con essa
  l'indicazione di cosa stesse in quel punto. Le etichette ora restano.
  Dove un'etichetta fa parte del dato e ne porta il significato
  („Interno 214"), non cambia nulla.

- **Il riconoscimento massimo non ripuliva i termini tecnici.**
  „Flachdach", „Einspeisepunkt", „Elektrotechnik" e termini tecnici
  simili venivano sostituiti come luogo o azienda anche con il livello
  IA attivato – l'IA non riceveva mai proprio questi rilevamenti da
  valutare. Ora li verifica anche: su un corpus di testi di bandi di
  gara e contratti, così spariscono tutti i 27 errori, senza che resti
  un solo dato reale. Nomi, aziende e luoghi vengono riconosciuti
  invariati.

- **I termini generici per tipi di istituzione venivano scambiati per
  organizzazioni.** In un testo contrattuale sparivano „Scuole superiori
  e università", „Scuole statali e private", „Ospedali universitari
  accademici", „Istituto scolastico" e „Aziende fornitrici" – parole che
  non nominano un ente specifico, ma un tipo di ente. Ora restano. Se
  davanti c'è un nome proprio („Commissione UE"), continua a essere
  sostituito, e i nomi di azienda non sono affatto interessati dalla
  regola.

- **I nomi negli elenchi cadevano solo se erano comuni.** In un elenco
  partecipanti o presenze sotto un'intestazione di colonna „Nome"
  venivano rimossi „Anna Huber" e „Thomas Müller", ma non „Wójcik
  Aleksandra" o „Kücükgöl Sinan" – stessa riga, stessa struttura. Chi
  porta un nome più raro era quindi meno protetto. Ora decide
  l'intestazione di colonna: ciò che sta sotto „Nome" è un nome. Una
  lista di posizioni con intestazione di colonna generica resta intatta.

- **Un numero di telefono dietro „Interno" veniva tagliato a metà.** Da
  „Interno 0732 771190" nasceva „[DURCHWAHL_1] 771190" – la seconda
  metà del numero restava leggibile. Ora cade il numero completo per
  intero, e l'etichetta resta. Un vero interno („Interno 214") viene
  sostituito invariato insieme all'etichetta.

- **Alcuni PDF non si potevano più bonificare del tutto.** Se un profilo
  colore o i metadati in un'immagine non potevano essere rimossi in
  modo dimostrabile, l'esecuzione si interrompeva senza risultato –
  erano interessati normali documenti aziendali come pagine di
  condizioni generali, capitolati e bandi di gara. Tali file vengono ora
  bonificati, e un avviso indica i punti rimasti aperti: possono portare
  un identificativo di dispositivo, produttore o acquisizione.
  L'originale resta come sempre invariato.

- **I ruoli contrattuali venivano scambiati per persone.** „Offerente",
  „Consumatore", „Locatario", „Acquirente", „Committente" e circa
  quaranta altri termini di ruolo venivano sostituiti dove stavano
  senza articolo – in intestazioni di contratto, colonne di tabella e
  righe di firma. Un testo contrattuale senza un singolo dato personale
  diventava così a tratti illeggibile. Queste parole ora restano. Se
  accanto c'è un'indicazione di persona – una formula di cortesia, un
  nome proprio, una parola di campo come „Referente" –, continua a
  essere sostituito: „Signor Offerente" e „Signora Acquirente" sono
  nomi. I cognomi comuni che sono anche professioni (Bauer, Richter,
  Koch) non sono affatto interessati dalla regola.

- **Una via scritta in forma abbreviata veniva trascurata se il numero
  civico aderiva direttamente al punto.** „Schlesischestr.31" non
  valeva come indirizzo – e poiché il codice postale accanto trae il
  suo appiglio dal rilevamento dell'indirizzo, restava anch'esso. Nel
  risultato l'indirizzo si poteva ricomporre da via e codice postale, e
  ciò solo su alcune pagine dello stesso documento. Ora entrambi
  cadono insieme. Le denominazioni tecniche con numero appeso
  („Kabelrinne200") restano intatte.

- **Un indirizzo su due righe veniva unito in un unico segnaposto.** Se
  in un blocco indirizzo il codice postale stava sopra la via, Maskuro
  univa entrambe le righe in un unico punto di rilevamento: nel
  risultato spariva l'a capo, e il codice postale restava leggibile
  davanti. Ora ogni riga viene trovata e sostituita separatamente, e
  l'aspetto grafico resta intatto. La stessa causa a volte trascinava
  anche il cognome dalla riga sopra nell'indirizzo.

- **Il percorso PDF massimo non riprende più oggetti originali.** Con il
  riconoscimento testo attivato, Maskuro ricostruisce ogni pagina
  completamente dall'immagine PDFium visibile. Nel nuovo file minimo
  entrano solo questa pagina immagine e uno strato di ricerca appena
  generato, limitato al testo OCR – non l'albero oggetti estraneo con
  commenti, allegati, azioni, livelli, metadati, profili colore o
  chiavi private. Vale anche per contenuti in aspetti di annotazione,
  motivi, caratteri Type-3, oggetti forma e maschere morbide. Il file
  sorgente resta intatto.

- **Volti e codici in grafiche PDF annidate venivano trascurati.**
  Entrambi i rilevatori ora vedono inoltre l'intera immagine di pagina
  renderizzata. Così raggiungono i rilevatori anche ritratti e codici
  QR/a barre in annotazioni, motivi, glifi Type-3 e maschere di
  trasparenza; le aree riconosciute vengono – se attivato – rese
  irriconoscibili prima della ricostruzione minima. Il rilevamento
  stesso resta fallibile.

- **Un motore OCR mancante terminava, per i PDF, con un errore
  interno.** L'esecuzione massima ora si interrompe in modo controllato
  e senza file di destinazione, invece di produrre un file incompleto o
  non verificato.

- **Diversi valori reali di contatto e commerciali cadevano, mentre
  veniva sostituito testo tecnico.** Campi nome su più righe, nomi
  bancari e aziendali, forme giuridiche, numeri identificativi
  etichettati, date di nascita nonché i confini di telefono, URL e IBAN
  sono verificati in modo più stretto. Allo stesso tempo restano più
  spesso intatti paesi nel testo tecnico, parole di ruolo e generiche,
  codici articolo/norma, colonne numeriche e abbreviazioni comuni.

- **Le righe OCR miste e ruotate venivano lette in modo errato.** Le
  parole verticali incerte vengono ora rilette localmente raddrizzate;
  i valori latini tecnici in testo non latino ricevono un testimone
  inglese indipendente. Una singola cifra isolata incerta viene
  corretta solo se due sequenze di cifre vicine concordano. Le forme
  giuridiche polacche nella forma OCR „sp. z 0.0." vengono lette nel
  contesto chiuso come „sp. z o.o.".

- **La misurazione immagine poteva trascurare resti parzialmente
  visibili.** Ora verifica ritagli locali sovrapposti, distingue il
  carattere segnaposto bianco su una barra nera dai glifi originali e
  trasferisce i riquadri immagine grezza anche su PDF minimi ruotati,
  renderizzati di nuovo. Il corpus principale sintetico fisso raggiunge
  così 1.392/1.392 dati attesi rimossi con 0 falsi allarmi e 0 errori di
  elaborazione. È un riscontro di corpus, non una promessa generale del
  100%.

- **I modelli linguistici non commerciali non vengono più offerti.** Le
  sei varianti spaCy italiane e greche sotto CC BY-NC-SA 3.0 sono
  rimosse da catalogo, download e percorso di caricamento; anche le
  cartelle modello già presenti vengono ignorate. Entrambe le lingue
  usano invece il modello multilingue con licenza MIT.

- **Il nome sotto „Referente" veniva rimosso solo a metà.** Se
  l'etichetta sta da sola su una riga e sotto „Cognome Nome", il nome
  proprio restava non appena era anche una parola comune – da „Mayer
  Roman" diventava „[NAME_1] Roman". Tali righe vengono ora prese
  interamente. Un reparto nello stesso punto („Assistenza tecnica
  interna") continua a restare intatto. Corretto per inciso:
  „Referente" non contava affatto come campo nome, sebbene „Persona di
  contatto" lo faccia da sempre.

- **Il nome dell'azienda senza forma giuridica restava se una parola di
  settore stava in mezzo.** „Kranzbichler Handels GmbH" veniva rimosso,
  il nudo „Kranzbichler" tre paragrafi dopo no – con „Kranzbichler
  GmbH" invece sì. Ora funzionano entrambi. Le parole comuni ne sono
  escluse: „Deutsche Bank AG" non rende „deutsche" nel testo
  un'azienda.

- **Lo stesso valore si chiamava nello stesso documento una volta nome
  e una volta luogo.** „Anna Musterfrau … Musterfrau" dava „[NAME_1]" e
  „[ORT_1]" – al secondo punto manca il nome proprio, e senza di esso
  diventava un luogo. Entrambi erano rimossi, ma si leggeva come due
  cose diverse. Un valore mantiene ora la denominazione della sua prima
  occorrenza.

- **Le date non venivano più rimosse.** Una data composta solo da
  cifre („01.03.2026") cadeva, dall'ultima versione, attraverso un
  controllo pensato per i nomi, e restava nel documento – anche nella
  modalità operativa „spostare", e senza riga nel rapporto di
  controllo. Era interessato solo chi aveva attivato espressamente le
  date.

- **Paesi e continenti non vengono più oscurati.** „La consegna va negli
  Stati Uniti", „Debolezza di mercato in Asia", „la norma vale in
  Romania" – tali indicazioni non dicono nulla su una persona e ora
  restano. Se il nome del paese fa invece parte di un indirizzo o sta
  dietro un'etichetta come „Residenza" o „Luogo di nascita", continua a
  essere rimosso. **Le città non ne sono interessate** – „Sono appena a
  Bilbao" resta un dato su una persona e continua a essere oscurato.

- **Le parole abbreviate diventavano indirizzi web.** Se nel testo sta
  „ossia tedesca" o „incl. del", alcuni PDF forniscono il punto senza
  spazio – ne nasceva „ossia.de" rispettivamente „incl.de", un
  indirizzo valido con suffisso paese, e veniva rimosso. Tali coppie di
  parole ora restano. Gli indirizzi reali non ne sono interessati,
  nemmeno senza „www." davanti.

- **Le colonne numeriche dei bilanci venivano oscurate come numeri di
  telefono.** Nei bilanci e nelle tabelle prezzi, l'anno precedente e
  quello in corso stanno affiancati – „64.518  65.133". Ciò valeva come
  un numero di telefono e veniva rimosso, così come intervalli numerici
  come „12200-23200" e una data seguita da un numero. Tali numeri ora
  restano. Al contrario, un vero numero di telefono viene riconosciuto
  in modo più sicuro: le etichette „Telefono", „Fax", „Cellulare",
  „Interno" e i loro equivalenti nelle altre lingue di interfaccia ora
  contano anch'esse – finora il programma vi riconosceva solo le parole
  inglesi.

- **I nomi in una tabella numerata restavano.** Un elenco partecipanti o
  una tabella personale nella forma consueta – intestazione di colonna,
  sotto „1.1 Auersperg Bernhard Montaggio 03.03.2026" – non veniva
  affatto bonificato: tali righe sembravano la lista posizioni di
  un'offerta, in cui i termini tecnici devono restare. Se l'intestazione
  di colonna porta un'etichetta persona („Nome", „Cognome", „Surname"
  …), le righe sottostanti valgono ora come nomi. Le liste di posizioni
  restano invariate risparmiate – anche quando nell'intestazione sta
  „Responsabile:".

- **Da un nome nascevano a volte due segnaposto affiancati.** Se un
  cognome stava anche da solo nel documento, l'elaborazione successiva
  sostituiva in un punto come „Anna Musterfrau GmbH" prima il cognome e
  poi il nome proprio – nel risultato sembrava come due persone
  diverse. Ora vince il nome noto più lungo.

- **I valori inventati non stavano in nessuna assegnazione.** Chi aveva
  scelto „Inventa valori" otteneva un risultato in cui „Anna Musterfrau"
  era diventata „Greta Mayrhofer" – nell'assegnazione non ne stava
  scritto nulla, non appena nello stesso documento compariva anche una
  sola sostituzione anonima. Così non si poteva recuperare nessun
  valore inventato, e il file di assegnazione taceva sulla
  sostituzione. La cosa più delicata era la terza: chi legge il
  risultato vede un nome credibile e non ha alcun indizio che sia
  inventato. Ora ogni sostituzione sta nell'assegnazione.

- **L'assegnazione chiamava „sostituito" ciò che era oscurato.** Un'e-mail
  condivide un'assegnazione con i suoi allegati, e l'allegato può essere
  oscurato, mentre il testo della mail porta un segnaposto.
  Nell'assegnazione stava allora per tutti e tre i punti la stessa cosa
  – „sostituito" –, e il recupero cercava nell'allegato un segnaposto
  che lì non esiste: la barra restava. Ora sta indicato per ogni punto
  di rilevamento cosa è realmente successo, ed entrambi gli allegati
  tornano.

- **I valori presenti solo in un'immagine non si potevano recuperare.**
  Nel pannello dei rilevamenti stavano doppi – una volta come
  segnaposto, che nel documento non esisteva da nessuna parte („Il
  segnaposto non è stato trovato nel documento"), una volta come punto
  oscurato. La prima riga era pura contabilità interna ed è sparita.

- **I valori oscurati si potevano recuperare solo una volta.** Se lo
  stesso valore sta in più punti, un clic li recupera tutti – ma le
  altre righe restavano nel pannello dei rilevamenti, e il clic
  successivo su di esse segnalava „Non univoco". Ora spariscono
  insieme.

- **I recuperi mancavano nel registro di controllo, se la modalità di
  apprendimento era disattivata.** Chi ripristinava un valore recuperato
  nella finestra di correzione non ritrovava il procedimento nel
  registro di controllo, non appena le domande di apprendimento erano
  disattivate – la prova dipendeva da un interruttore che riguarda solo
  i suggerimenti di regola. Con il registro di controllo attivato, ora
  viene chiesto il motivo indipendentemente da questo e la riga viene
  scritta.

- **I file trascinati dentro restavano non bonificati – e non venivano
  nemmeno segnalati.** Chi trascina un file in un documento, invece di
  inviarlo come allegato, fa sì che Word o PowerPoint lo depositi
  completamente nel documento. Dopo restava invariato nel risultato,
  con il suo nome file e percorso di deposito originali – e questi in
  pratica portano spesso essi stessi un nome. Tali file vengono ora
  bonificati come il resto del documento.

- **E dove ciò non funziona, Maskuro lo dice.** Se in un oggetto
  incorporato c'è un formato vecchio (Word 97, Excel 97) per cui non
  esiste bonifica, compare ora un messaggio di ATTENZIONE con il nome
  del file. Finora veniva inoltrato invariato in silenzio.

- **Le parole spezzate e le sigle venivano scambiate per nomi.** Se una
  parola in un PDF è divisa a fine riga, alla lettura di alcuni file
  ne esce un frammento – „Jahresent… gelts", „Gewerbli…". Tali
  frammenti, parole incollate insieme („TürverschlussmitV") e sigle
  nude („JY", „FFB") venivano oscurati come se fossero nomi. Ora
  restano. Un nome con lo stesso danno di divisione continua a essere
  oscurato, finché c'è una formula di cortesia – e i nomi che portano
  di per sé una maiuscola all'interno della parola (McKenzie,
  MacDonald, LeBlanc) non sono comunque interessati.

- **Le indicazioni di misura e i mesi valevano come indirizzo.** In
  documenti tecnici venivano oscurati „2000 Lux", „1200 Mbit", „1500
  Watt", „5308 Platz" e „2022 Mrz" – quattro cifre e una parola
  maiuscola sembravano un codice postale con località. Un codice
  postale conta ora solo se c'è anche un segnale di indirizzo: un
  codice paese, un'etichetta di campo, l'inizio riga, una via nella
  riga sopra o un luogo che anche il riconoscimento linguistico vede
  lì. In cinque capitolati spariscono così 14 oscuramenti errati, senza
  che resti un vero indirizzo.

- **Il riconoscimento più accurato sostituiva troppo.** Il livello
  attivabile „riconoscimento più accurato" scambiava, in documenti
  aziendali tedeschi, termini tecnici per nomi e luoghi –
  „Photovoltaikanlage", „Einspeisepunkt", „Flachdach",
  „Personaleingang" – e oscurava denominazioni aziendali in liste di
  posizione correnti. Il motivo era un riguardo: i suoi rilevamenti
  erano esclusi dai controlli che riconoscono una riga di posizione o
  elenco. Questo riguardo vale ora solo per nomi composti da più parti,
  per i quali esiste il livello – „Anna Huber" in una riga di elenco
  resta quindi riconosciuta, una singola parola tecnica in una riga di
  posizione cade. In un bando tecnico questo dimezza gli oscuramenti
  errati del livello, senza che vada perso un nome.

- **I diagrammi portavano con sé i loro dati sorgente completi – non
  verificati.** Chi inserisce un grafico in Word o PowerPoint fa sì che
  il programma depositi nel documento, come file proprio, la tabella da
  cui è stato calcolato. Visibili sono solo i pochi numeri nel grafico;
  nella tabella sta l'intero elenco, comprese le righe che nel grafico
  non compaiono affatto. Questa tabella veniva finora inoltrata
  invariata. Viene ora bonificata insieme, con gli stessi segnaposto
  del resto del documento.

- **Lo stesso per oggetti incorporati in file OpenDocument** (ODT, ODS,
  ODP): un grafico o una tabella inseriti restavano intatti.

- **Documenti Word: le note a piè di pagina e le note di chiusura non
  venivano bonificate.** Il loro testo restava completamente nel
  risultato – anche nomi, indirizzi e numeri di conto. Era interessato
  ogni documento Word con una nota a piè di pagina o di chiusura. Allo
  stesso modo restava intatto un blocco di testo automatico che viaggia
  in modo invisibile con il documento.

- **Word: dati in elenchi di selezione, commenti e descrizioni
  immagine.** Le voci di un campo di selezione (visibili solo
  aprendolo), l'autore di un commento, la descrizione di un disegno e
  l'indirizzo dietro un comando di riferimento restavano nel risultato.

- **Excel: la tabella pivot registrava i dati di partenza una seconda
  volta.** Una cartella con una tabella pivot conserva al suo interno
  una copia completa delle righe elaborate – invisibile, ma nel file.
  Questa copia restava finora invariata, anche se nel foglio stesso
  tutto era sostituito. Era interessata ogni elaborazione inoltrata con
  una tabella pivot.

- **Excel: commenti di conversazione e i loro autori.** Il testo di un
  commento del tipo più recente e l'elenco dei commentatori – nome
  visualizzato e identificativo di accesso, in azienda per lo più
  l'indirizzo email – restavano nel risultato. Lo stesso elenco anche
  nei documenti Word.

- **Proprietà del documento autodefinite in Word ed Excel.** Campi come
  „Cliente" o „Numero di pratica", che uno studio aggiunge ai propri
  modelli, non venivano finora bonificati. Non sono visibili in nessuna
  visualizzazione e viaggiano comunque con ogni copia.

- **Fogli di calcolo (ODS): l'elenco di selezione di una cella.** Come
  in Excel dalla versione precedente, ora viene bonificato anche nei
  fogli di calcolo OpenDocument ciò che compare aprendo una cella. I
  riferimenti ad altre celle restano intatti, in modo che l'elenco
  continui a funzionare.

Tutti questi punti si possono recuperare come al solito tramite
l'assegnazione.

- **Messaggi Outlook: un file danneggiato interrompeva bruscamente la
  bonifica.** Alcuni file `.msg` rotti portavano a un'interruzione
  invece che a un messaggio; ora vengono letti nella misura in cui sono
  leggibili.

- **Il file di assegnazione è ora leggibile solo da voi.** Contiene i
  dati originali in chiaro e stava finora accanto al risultato con i
  diritti consueti – su un deposito condiviso chiunque poteva aprirlo.
  Sul risultato bonificato stesso non cambia nulla; deve pur essere
  inoltrato.

- **I modelli linguistici scaricati vengono verificati più accuratamente
  prima dell'estrazione.** Un pacchetto manipolato – ad esempio da una
  condivisione aziendale da cui vengono serviti più posti di lavoro –
  poteva, all'estrazione, depositare file al di fuori della cartella
  prevista. Sul normale scaricamento non cambia nulla.

- **Cattura schermata – e viene bonificata subito.** Con
  `Ctrl+Maiusc+B`, tramite „File → Cattura schermata …" o tramite
  l'icona nella barra delle applicazioni, tracciate una cornice sullo
  schermo. Ciò che vi si trova segue poi lo stesso percorso di ogni
  altro file: il riconoscimento testo legge il testo dello schermo,
  nomi, indirizzi, numeri di telefono e indirizzi email vengono
  oscurati, e dopo l'immagine è aperta nell'editor, dove potete
  oscurare a mano ciò che è stato trascurato. L'immagine bonificata
  finisce sulla scrivania (o nella cartella di output impostata); la
  cattura **grezza** non viene depositata da nessuna parte e viene
  eliminata alla chiusura. Il riconoscimento testo viene attivato per
  questa esecuzione, anche se altrimenti è disattivato – su
  un'immagine, senza di esso non si troverebbe nulla. Sul Mac il sistema
  chiede la prima volta l'autorizzazione „Registrazione schermo".

- **Sulle immagini si può ora disegnare: rettangolo, ellisse, freccia,
  testo e marcatori di passaggio numerati.** In sei colori e tre
  spessori di tratto, selezionabili con i tasti da 1 a 5. Pensato per
  schermate e istruzioni: mostrare ciò che conta, senza dover aprire un
  secondo programma. Annulla e il ridimensionamento dalle maniglie
  valgono come per ogni barra – un'annotazione si può quindi spostare e
  ridimensionare dopo essere stata posizionata.
  **Disegnare non è espressamente oscurare.** Un rettangolo disegnato è
  una cornice, non una barra: ciò che sta sotto resta leggibile e va
  fuori con il file. Per rimuovere dati ci sono ancora „Oscura" e
  „Pixela"; gli strumenti di disegno stanno perciò in una riga propria
  della barra degli strumenti, e la riga di avviso lo dice, finché uno
  di essi è selezionato.

- **L'immagine modificata va con un clic negli appunti.** „Copia
  immagine" nell'editor (o `Ctrl+C`) la deposita così com'è – basta
  incollarla per portarla in un messaggio o in un'e-mail. Così il
  percorso dalla pressione del tasto alla chat è di quattro passaggi e
  non richiede alcuna cartella.

- **Inoltre un evidenziatore, ombre e sfumature.** „Evidenzia" colora
  un'area senza coprirla – il contenuto sottostante resta leggibile, e
  proprio per questo si distingue dalla barra. „Ombra" stacca
  un'annotazione da uno sfondo agitato, „Sfumatura" fa sfumare il
  colore in direzione del tratto; entrambi valgono per tutti e sei gli
  strumenti di disegno.

- **Corretto prima che colpisse qualcuno:** la nuova riga di strumenti
  sarebbe apparsa quasi vuota per chiunque avesse già usato Maskuro –
  la disposizione della finestra memorizzata risaliva a prima e non le
  avrebbe lasciato spazio. Una disposizione obsoleta viene ora
  scartata; la finestra dell'editor appare allora una tantum nella sua
  disposizione di base.

- **La propria schermata si può disattivare.** Chi è abituato a
  Greenshot, ShareX o allo strumento di cattura disattiva sotto
  „Impostazioni → Programma" „Cattura schermata con Maskuro". Maskuro
  allora non registra affatto la scorciatoia da tastiera – resta al
  vostro strumento –, e il cambiamento vale subito, senza riavvio.
  Un'immagine catturata così si può comunque bonificare: Ctrl+V la
  porta dagli appunti nella finestra.

---

## 0.10.37-alpha.20260821 – 21 agosto 2026

### Nuovo

- **Nell'anonimizzazione ogni punto di rilevamento porta ora il proprio
  numero.** Finora tutte le persone si chiamavano `[NAME]`, tutti i luoghi
  `[ORT]" – così non si poteva più dire quale punto appartenesse a quale
  valore, e non c'era nulla da recuperare. Ora i numeri continuano a
  contare per ogni occorrenza: lo stesso nome sta in tre punti come
  `[NAME_1]`, `[NAME_3]` e `[NAME_7]`. Nel documento continua a non essere
  riconoscibile quali punti siano collegati – ma con il file di
  assegnazione si può recuperare ognuno singolarmente. Il file di
  assegnazione è quindi di nuovo selezionabile anche nell'anonimizzazione;
  conservatelo separato dal risultato.
- **Mesi, giorni della settimana, valute, unità e forme giuridiche
  aziendali in tutte le 48 lingue di documento non valgono più come nomi o
  luoghi.** I nomi di calendario e unità provengono da Unicode CLDR
  (generati, non scritti), le forme giuridiche dal diritto societario dei
  paesi – anche a più parole („sp. z o.o.", „Pty Ltd") e anteposte
  („株式会社"). Dove un nome di mese è al contempo un nome proprio (Juli,
  August, May), decide la forma: con giorno o anno accanto una data,
  altrimenti un nome. Inoltre formule di cortesia e titoli, intere formule
  di saluto, tipi di documento e parole base di via per 28 lingue con
  modello linguistico proprio, sigle di legge (GDPR, UStG, ABGB, § 6 Abs 1
  Z 27 UStG) nonché nomi di lingua come valore di campo („Lingua:
  Tedesco"). Gli elenchi stanno sotto „Guida → Elenchi di parole …".
- **India: indirizzo e codice PIN vengono riconosciuti** – „15 गांधी
  मार्ग", „नई दिल्ली 110001" così come „15 Gandhi Marg, New Delhi 110001".
  Il pacchetto paese India conosceva finora solo numeri identificativi;
  negli hindi documenti restavano quindi gli indirizzi.
- **Ogni file d'ufficio bonificato viene riaperto come pacchetto prima
  della consegna.** Un estratto di testo non nota quando Word, Excel o
  LibreOffice rifiuterebbero il file (voce doppia, XML strappato, una
  parte mancante). E viene contato contro l'originale ciò che una
  bonifica non deve mai cambiare: pagine di un PDF, fogli, righe e celle
  di una tabella, diapositive di una presentazione. Se la prova
  scatta, nel risultato e nel rapporto di controllo compare un avviso di
  ATTENZIONE – l'originale resta invariato.
- **Anche l'automatismo oscura l'intero campo.** In modalità oscuramento,
  la barra in righe corte – blocco indirizzo, cella di tabella, dati di
  intestazione – copre l'intera riga invece del solo valore trovato: una
  barra della lunghezza della parola rivela quanto era lunga la parola.
  Etichetta e importi accanto restano; le righe di testo scorrevole (più
  lunghe di metà della larghezza del testo) continuano a essere oscurate a
  livello di parola, in modo che un nome in mezzo alla frase non renda
  nera l'intera frase.
- **Ciò che viene recuperato ha di nuovo l'aspetto dell'originale.**
  „Recupera originale" e „Annulla sostituzione" nell'editor PDF scrivono
  ora l'area esattamente dal file sorgente – lo stesso carattere, la
  stessa dimensione, lo stesso colore e posizione, su una scansione gli
  stessi pixel. Fino ad allora il testo veniva ricomposto in un carattere
  sostitutivo e appariva riconoscibilmente ricostruito. La barra di un
  oscuramento precedente sparisce completamente, invece di essere coperta
  di bianco – uno sfondo di cella colorato in una tabella resta
  invariato. Vale anche su pagine ruotate, per testo da oggetti modulo
  incorporati e per **campi modulo compilati**: sulla copia di lavoro
  rasterizzata per questo, il ritaglio dalla pagina originale
  ri-renderizzata torna indietro – anche dove nessuno strato di testo
  conosce il valore del campo. Anche le **immagini sostituite** nel PDF
  tornano così indietro – pixelate, sfocate o rimosse del tutto, per
  intero o solo il ritaglio tracciato. Solo dove il file sorgente non si
  trova più accanto al risultato resta il percorso precedente.
- **I valori oscurati e rimossi senza sostituto si possono recuperare
  anche in Word, Excel, PowerPoint e OpenDocument.** Finora il recupero
  lì richiedeva un segnaposto nel testo – una barra o una lacuna non
  aveva via di ritorno. Ora il pannello dei rilevamenti offre le righe
  „oscurato" e „rimosso", non appena il file sorgente intatto sta accanto
  al risultato: Maskuro confronta il risultato con l'originale e reinserisce
  il valore al posto della barra o della lacuna – con tanto di
  formattazione, un run diviso torna intero. Vale anche per testo, HTML,
  e-mail e gli allegati Office di un'e-mail; se il testo della mail porta
  un segnaposto e l'allegato una barra, entrambi vengono recuperati in un
  colpo solo.
- **Anche gli allegati PDF di un'e-mail o di un messaggio Outlook si
  possono recuperare** – segnaposto (numerati e anonimi), barre e
  rimozioni senza sostituto. Senza strato grafico il punto proviene
  dall'allegato originale; il valore torna preciso glifo per glifo,
  nell'ordine di lettura dell'originale.
- **I valori mascherati si possono recuperare** – nel PDF e nella
  visualizzazione testo. Una maschera („**** **** **** **** 3201") non è
  mai univoca, due numeri portano la stessa; per questo il recupero non
  prende mai la via letterale, ma chiede all'originale quale valore stava
  in quel punto. Finora queste righe non erano affatto utilizzabili nel
  pannello dei rilevamenti.
- **Le immagini incorporate in Word, Excel, PowerPoint e OpenDocument si
  possono recuperare.** Un valore oscurato nell'immagine torna tramite la
  sua riga di pannello – Maskuro legge l'immagine originale e recupera
  esattamente quel punto; un'immagine sfocata, rimossa o elaborata con
  volti e codici viene recuperata per intero dal nuovo voce „Recupera
  immagini incorporate" nel menu Modifica dal file sorgente – anche
  attraverso gli allegati Office di un'e-mail o di un messaggio Outlook.
  Un'immagine che è essa stessa un allegato ed è stata oscurata tramite
  riconoscimento testo torna allo stesso modo tramite la sua riga di
  pannello.
- **I valori inventati si possono recuperare nella visualizzazione
  testo.** Finora il pannello lì segnalava „Non univoco". Ora il recupero
  cerca il valore nell'originale ed esige, nello stesso punto del
  risultato, esattamente il sostituto inventato – un nome inventato non
  viene mai sostituito letteralmente ovunque, potrebbe stare da qualche
  parte come reale.
- **Il recupero in Word, Excel, PowerPoint e OpenDocument mantiene la
  formattazione dell'originale.** Se un valore stava su più run – „Anna"
  normale, „Musterfrau" grassetto e rosso –, finora tornava interamente
  nel primo run e perdeva grassetto e colore. Ora i caratteri si
  distribuiscono di nuovo come nell'originale; un paragrafo Word è dopo
  identico byte per byte all'originale. Lo stesso vale per pagine HTML,
  la parte HTML di un'e-mail e il corpo HTML di un messaggio Outlook
  (.msg) – nell'e-mail resta inoltre conservato il doctype, che la
  bonifica finora rimuoveva in silenzio.
- **I file di testo mantengono la loro codifica.** Bonifica e recupero
  scrivono ora `.txt`, `.md` e `.csv` nella codifica in cui sono stati
  forniti – UTF-8 con e senza BOM, UTF-16, Windows-1252. Finora un file
  Windows-1252 diventava sempre UTF-8, e un file UTF-16 tornava
  danneggiato, anche se non c'era nulla da sostituire al suo interno.
- **Le immagini recuperate mantengono la loro modalità colore.** Una
  scansione in scala di grigi torna come scala di grigi invece che come
  file RGB tre volte più grande, una palette come palette, bianco e nero
  come bianco e nero – per l'intera immagine con gli stessi valori
  dell'originale. Vale per file immagine e per immagini nei PDF. CMYK e 16
  bit restano RGB, perché il risultato PNG non può portare entrambi.
- **Una cornice nell'immagine recupera l'intera elaborazione che
  tocca.** I volti pixelati portano un bordo intorno al riquadro
  riconosciuto; chi tracciava la cornice solo sopra il volto manteneva un
  anello pixelato. Ora la cornice cresce sulla modifica collegata rispetto
  all'originale – basta una cornice sopra la zona degli occhi. Le barre
  separate accanto restano; per una foto rimossa o sfocata interamente
  continua a valere la cornice tracciata. Vale per file immagine e
  immagini nei PDF.
- **Barre di oscuramento sull'intera riga.** In modalità riga dell'editor,
  la barra ora corre dalla prima all'ultima parola della riga, non più
  solo sopra la parola colpita – una barra della lunghezza della parola
  rivela quanto era lunga la parola, e da sei caratteri davanti a un
  codice postale si può indovinare un nome di luogo. Etichette, importi e
  colonne di tabella accanto al valore restano – la barra copre il campo,
  non la riga della fattura. Il nuovo interruttore „Riga intera" accanto a
  „Righe di testo" torna a impostare la modalità a livello di parola, se le
  parole vicine devono restare; la scelta viene memorizzata.

### Corretto

- **Le immagini in pagine HTML ed e-mail restavano non verificate – il
  nome nel logo restava leggibile dopo la bonifica.** Un'immagine
  incorporata nella pagina (indirizzo ``data:``) non veniva toccata
  affatto, solo il suo testo alternativo; il logo nel ramo HTML di una
  mail (immagine inline senza nome file) cadeva attraverso il filtro
  allegati; e per l'allegato immagine con nome la regola immagine
  „sfoca"/"rimuovi" restava senza effetto. Ora tutti e tre percorrono lo
  stesso percorso di un file immagine: riconoscimento testo nell'immagine
  mantenuta, volti, codici, metadati e la regola immagine. Il rapporto
  nomina le immagini – anche l'avviso se restano non verificate senza
  riconoscimento testo –, e „Recupera immagini incorporate" così come il
  recupero dal pannello dei rilevamenti conoscono anch'esse queste
  immagini.
- **Un file d'ufficio con immagine non si poteva affatto bonificare, se il
  riconoscimento testo non padroneggiava la lingua.** Sul Mac legge il
  riconoscimento testo nativo del sistema; per hindi, greco, croato o
  lituano non ci riesce e lo dice ormai anche – con Word, Excel,
  PowerPoint e OpenDocument, però, per questo si interrompeva l'**intera**
  bonifica, e non nasceva alcun file. Eppure il testo si poteva bonificare
  perfettamente; solo l'immagine non era leggibile. Ora il file viene
  scritto come per PDF e immagini singole, e nel risultato sta scritto che
  le immagini NON sono state verificate – con il motivo e il rimando a
  „Gestisci lingue".

- **Nelle cartelle Excel restavano nomi in elenchi di selezione.** L'elenco
  di un campo a discesa (convalida dati) viene ora bonificato come
  qualsiasi altro contenuto di cella; i riferimenti a intervalli di celle
  restano intatti, in modo che la cartella resti integra.
- **Dove il segnaposto non entrava, c'era una barra nera – ora c'è una
  scrittura più corta.** `[GEBU_1]` invece di `[GEBURTSDATUM_1]`, e solo
  quando nemmeno la forma più corta entra si oscura. Una barra non dice
  più a nessuno che lì c'era qualcosa; un segnaposto corto lo dice.
  L'editor di correzione lo sapeva già fare, la bonifica automatica
  finora no. Il file di assegnazione riconduce entrambe le scritture allo
  stesso valore, in modo che anche l'abbreviato si possa recuperare.
- **Il primo clic su „Sostituisci" faceva restare bloccata brevemente la
  finestra di correzione.** Il riconoscimento che assegna al segnaposto
  il suo tipo (`[NAME_3]` invece di `[BEGRIFF_3]`) veniva caricato solo in
  quel momento – circa due o tre secondi. Ora viene preparato in
  background all'apertura della finestra; misurati, da 2289 millisecondi
  sono diventati 193.
- **Due bonifiche contemporanee potevano caricare due volte lo stesso
  modello linguistico** – ad esempio il monitoraggio cartella e la
  finestra principale. Poiché ogni modello occupa alcune centinaia di
  megabyte, il fabbisogno di memoria era brevemente il doppio. Ora la
  seconda esecuzione attende il modello della prima.
- **Il luogo nella riga della data viene ora rimosso anche quando il
  modello linguistico non lo riconosce da solo:** ciò che è trovato con
  sicurezza come codice postale con località („3335 Amstetten") trascina
  il suo nome di luogo in tutto il documento – come un cognome da un nome
  completo. E una sigla con cifra davanti a un nome („T3 Hofbauer
  Christian") resta leggibile, invece di sparire insieme nel segnaposto.
- **Chiuse tre falle dalla rilettura secondaria di un ordine reale:** il
  responsabile „T3 Hofbauer Christian" veniva considerato, a causa della
  sigla „T3", un'intestazione di colonna e restava leggibile; un luogo
  che il modello linguistico leggeva attraverso l'a capo nell'intestazione
  di colonna inghiottiva „Pos." e lasciava il nome proprio del cliente; e
  un nome con formula di cortesia („Herr Robert Köttel") trascinava solo
  il cognome, non il nome proprio – e per questo ogni „Herr". Le sigle
  sono ora pure lettere, i nomi a due parole non sono intestazioni, i
  rilevamenti vengono tagliati davanti a un'intestazione di colonna, e la
  formula di cortesia non conta come parte del nome.
- **Il luogo nella riga della data („Melk, 05.08.2026") direttamente sotto
  il blocco indirizzo restava leggibile.** Il modello linguistico lo
  incollava con il luogo della riga del codice postale in un unico
  rilevamento, e questo cadeva per intero contro il modello del codice
  postale. Ora il resto sporgente resta un rilevamento proprio. Trovato
  dalla nuova rilettura secondaria del risultato (`werkzeuge/zweitlesung.py`).
- **Mac: una scansione in una lingua che il riconoscimento testo nativo
  del sistema non padroneggia (ad esempio hindi, greco, croato,
  lituano) valeva come verificata.** Veniva letta con il ripiego inglese,
  la scrittura estranea restava nell'immagine, e il rapporto diceva
  „nulla trovato". Ora dice „Le immagini NON sono state verificate" con
  il motivo, e la gestione lingue non promette più riconoscimento testo
  per tali lingue solo perché è presente un file linguistico Tesseract.
- **Nel PDF il segno di punteggiatura dietro un valore sostituito
  resta.** Da „Ricovero il 01.03.2026, dimissione il 04.03.2026." finora
  nasceva „Ricovero il [DATUM_1] dimissione il [DATUM_2]" – virgola e
  punto finale mancavano, sia con segnaposto sia con date spostate. Ora
  viene rimosso solo il valore riconosciuto, non l'intera parola fino al
  successivo spazio; virgola, punto e virgola, punto o parentesi dietro
  restano al loro posto, e il segnaposto non li scavalca.
- **Russo e ucraino giravano inosservati con il modello multilingue più
  debole**, quando mancava un pacchetto ausiliario per l'analisi delle
  forme di parola (`pymorphy3`) – i modelli propri allora non si potevano
  caricare, e „Львів" diventava una persona. Per il riconoscimento dei
  nomi, l'analisi delle forme di parola non è necessaria; il modello
  viene ora caricato senza di essa, e i luoghi sono di nuovo luoghi.
- **Le note di licenza in 16 lingue erano su vecchio stato.** Vi stava
  ancora scritto che il codice sorgente MPL sarebbe fornito „su
  richiesta", QPDF valeva come MPL-2.0, sette componenti mancavano nella
  tabella (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp,
  YuNet), il paragrafo spaCy era in inglese, e alla fine pendeva una
  sezione sostitutiva inglese. Ora tutte le 18 versioni sono allo stato
  della tedesca: archivi sorgente permanenti sotto maskuro.com/quellcode/oss/,
  QPDF Apache-2.0, percorso Qt-LGPL, provenienza dei modelli. Anche la
  tabella inglese ha le righe mancanti.

- **Le parole contrattuali al genitivo („des Angebotsinhaltes", „des
  Anbotes", „des Terminplanes") non valgono più come luogo.** Una singola
  parola dietro un articolo genitivo o dativo con desinenza flessiva è un
  termine generico – i nomi di luogo non si flettono („nach Graz"). Se il
  luogo sta altrove nel documento senza articolo („Burgenland"), resta
  riconosciuto anche „des Burgenlandes".
- **Valori spostati, mascherati e inventati rasterizzavano la pagina
  PDF.** Il controllo successivo dopo la rimozione consentiva nel
  rettangolo di rilevamento solo un segnaposto tra parentesi quadre; una
  data spostata („01.07.2026") o un valore mascherato („****1234")
  valevano come resto trascurato, e la pagina veniva convertita per
  precauzione in immagine – non con „Sostituisci". Ora tali pagine
  restano testo, e il recupero da pannello o cornice fornisce di nuovo
  l'originale.
- **I valori sostitutivi multiparola non si potevano annullare nel PDF
  tramite il pannello dei rilevamenti.** Un nome inventato („Greta
  Mayrhofer") o un IBAN mascherato („**** **** **** **** 3201") è
  composto da più parole; la ricerca del punto di rilevamento confrontava
  parola per parola e segnalava „Il segnaposto non è stato trovato nel
  documento". Ora le parole consecutive della stessa riga vengono lette
  insieme.
- **Dopo il recupero di un valore rimosso senza sostituto, la sua riga di
  pannello restava.** I valori che la strategia „oscura" in modalità
  segnaposto rimuove senza sostituto non hanno un segnaposto su cui il
  pannello potesse misurare una scomparsa. Ora la riga viene cancellata
  non appena il valore torna nel documento.

- **I composti abbreviativi come „E-Helfer" o „U-Bahn" non valgono più
  come nome.**
- **I resti di sillabazione („Leis-") e i composti eccessivamente lunghi
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") non
  valgono più come nome o luogo.** In un testo di bando scansionato sono
  così 28 parole in meno oscurate.
- **Le liste di posizioni di offerte scansionate non valgono più come
  elenco di nomi.** Il passaggio aggiuntivo per elenchi (righe corte)
  trasformava „Kälterohr" e „Außengeräte" in persone; ora si sospende non
  appena numeri di posizione come „1.1.5" stanno all'inizio riga. Le
  righe di data nelle conversazioni email non contano in questo caso come
  numeri di posizione.
- **Intestazioni di colonna e numeri di posizione di offerte scansionate
  („Pos.", „Pos. 1.1.3", le sigle „E/L/S") valevano come nome o luogo.**
  Un'abbreviazione da sola sulla sua riga, un'etichetta con numero e
  lettere singole riga per riga non lo sono.
- **La pagina „respirava" nella finestra di correzione dopo l'apertura
  della lente di confronto** – con „Larghezza pagina" ed „Adatta" la
  scala dipende dalla finestra visibile, e questa cambia con ogni barra
  di scorrimento che compare o scompare; ogni azione successiva spostava
  la pagina di un pezzo. La tela ora la corregge automaticamente finché
  si stabilizza. E pulsanti zoom, cursore e scorciatoie mantengono il
  centro dell'immagine anche quando, ingrandendo, compare una barra di
  scorrimento.
- **Le scansioni salvate di traverso vengono ora lette in verticale, e il
  carattere piccolo in scansioni grandi non va più perso.** Un'offerta
  scansionata di 24 pagine manteneva leggibili in ogni piè di pagina sei
  IBAN bancari, numero di registro delle imprese e partita IVA: la
  scansione stava nel PDF ruotata di 90°, e il riconoscimento testo, con
  immagini molto grandi, ometteva intere righe a seconda delle dimensioni
  dell'immagine. Ora viene considerata la rotazione visibile e le immagini
  grandi vengono lette in fasce sovrapposte – i piè di pagina sono neri.
- **Le vie con nome di persona con trattino prima della parola base
  („Josef Admanseder-Straße 7", „Abt-Karl-Straße 8",
  „Dr.-Karl-Renner-Straße 12") vengono riconosciute come indirizzo.**
  Nell'intestazione di un'offerta scansionata un tale indirizzo restava
  leggibile, perché il modello richiedeva uno spazio prima di „Straße".
- **Gli IBAN dal riconoscimento testo che portano una O invece di 0 o una
  l invece di 1 vengono ora riconosciuti.** Nel carattere piccolo di una
  scansione, il riconoscimento testo legge volentieri le cifre come
  lettere; il numero aveva quindi la forma di un IBAN, ma il checksum non
  tornava, e restava. Se il checksum fallisce, viene ora provata la
  lettura con cifre – se allora torna, è l'IBAN. Cifre di controllo
  sbagliate restano sbagliate.
- **Frammenti di frase come „folgenden Codes auf der" valevano come
  luogo.** Un nome o luogo che inizia con una parola minuscola non lo è –
  eccetto per le particelle nobiliari („van Gogh", „de Vries").
- **Nell'editor restava accanto alla barra di oscuramento l'ultima
  lettera** („…6", „…t", „…g"), e la barra aveva l'altezza della cornice
  tracciata invece che della riga. Causa: se l'editor non poteva misurare
  la pagina, considerava ogni cornice come „nessuna parola colpita" e la
  applicava esattamente – senza la regola secondo cui una mezza parola non
  resta mai. Lo stesso accadeva con singoli comandi di testo che l'editor
  non poteva localizzare. Ora conta sempre accanto il riquadro parola: ciò
  che la cornice sovrappone in modo significativo cade per intero.
- **L'ultima lettera di una parola sporgeva oltre la barra di
  oscuramento.** La barra era dimensionata secondo la larghezza di
  avanzamento dalle metriche del carattere; se il carattere disegna un
  glifo più largo, il suo resto stava accanto alla barra. Il riquadro di
  un carattere ora accoglie anche il glifo disegnato.
- **Il messaggio sulla conversione di una pagina in immagine prometteva
  troppo.** „La rappresentazione resta uguale" non è vero dopo la
  rasterizzazione: carattere e grafica sono allora pixel, il file
  diventa più grande. Il messaggio ora lo dice – e indica anche il
  secondo motivo per cui si rasterizza (la ricostruzione avrebbe
  danneggiato la pagina).
- **Il testo dietro un valore rimosso si spostava fino a un punto verso
  sinistra.** Nella ricomposizione di una riga, l'inizio veniva misurato
  al bordo del glifo, il proseguimento all'origine della penna – la
  larghezza di avanzamento del primo carattere restava come errore
  („C" 0,5 pt, „I" 1,0 pt). Ora la ricomposizione calcola in modo
  uniforme con l'origine della penna; la frase successiva sta al decimo
  di punto al suo posto.
- **La partita IVA austriaca con spazi („ATU 187 35901") e un numero di
  registro delle imprese senza „FN" sotto la sua etichetta
  („Firmenbuchnummer: 30799v") vengono riconosciuti.** Entrambi stavano
  scritti a mano su un modulo di bando scansionato e restavano leggibili,
  sebbene il riconoscimento testo li avesse letti correttamente.
- **Le pagine PDF orizzontali venivano convertite in immagine senza motivo
  dopo l'oscuramento.** Il controllo di integrità confrontava originale e
  risultato nella visualizzazione ruotata, ma calcolava le sue zone di
  oscuramento non ruotate – su una pagina con annotazione di rotazione, il
  proprio oscuramento stava quindi accanto alla sua zona e valeva come
  danno. Tali pagine ora mantengono il loro strato di testo e la grafica
  vettoriale.
- **Anche le pagine dritte venivano occasionalmente convertite in
  immagine senza necessità**, quando il testo dietro un segnaposto si
  spostava di un punto – consentito, ma il confronto immagine era più
  fine della sua stessa tolleranza. Ora confronta in mezzi punti e
  centra così esattamente la sua tolleranza: fino a due punti di
  scostamento non scatta nulla, oltre scatta tutto.
- **I dati in oggetti modulo incorporati restavano.** Alcuni modelli
  depositano intestazione o chiusura della lettera come modulo proprio
  che la pagina si limita a includere. Un rilevamento al suo interno
  veniva sì pianificato e contato come rimosso, ma mai scritto – il testo
  restava lì, e solo la rasterizzazione dell'intera pagina lo
  intercettava. Ora il modulo stesso viene riscritto; un modulo presente
  su più pagine, una sola volta.
- **Le pagine PDF venivano rasterizzate in immagine, sebbene non fosse
  rimasto nulla di leggibile.** Un'offerta di sette pagine ne colpiva
  sei; cresceva da 73 kB a 3,3 MB e perdeva il suo carattere in
  un'immagine. La causa erano spazi che nel documento stanno più volte di
  seguito, ma vengono segnalati dal lettore solo una volta: il testo
  dietro un dato rimosso si spostava a destra della sua larghezza, il
  controllo successivo trovava la parola vicina nel rettangolo di
  rilevamento e ricorreva alla rasterizzazione. I resti di riga mantenuti
  stanno ora di nuovo esattamente al loro posto; la stessa offerta viene
  bonificata senza una sola pagina rasterizzata (76 kB).
- **Nomi di chiave e intestazioni di fattura valevano come persone.** In
  un file di accesso veniva sostituito il nome della variabile d'ambiente
  („AWS_ACCESS_KEY_ID"), non solo il suo valore; su una fattura inglese
  l'intestazione „Bill to" cadeva come nome proprio. Un identificatore in
  maiuscole con trattini bassi non è mai un nome, e una parola in una
  riga che nel suo insieme è un'etichetta di campo nemmeno – il
  destinatario sottostante continua a essere trovato.
- **La ricerca nella finestra di correzione si bloccava con pagine PDF
  grandi.** Ogni lettera nel campo di ricerca faceva rasterizzare di nuovo
  la pagina, sebbene cambiasse solo l'evidenziazione. L'immagine di
  pagina renderizzata ora resta ferma, finché pagina, zoom e
  visualizzazione sono gli stessi – anche l'originale nella lente di
  confronto; scorrimento, zoom e un nuovo stato del file continuano a
  disegnare da capo come prima.
- **I numeri di posizione nelle offerte valevano come indirizzo IP o
  numero di telefono.** Una riga articolo come „1.3.3.4 … 5-Port Gigabit
  Switch" faceva diventare il numero di struttura un indirizzo di rete,
  perché „Port" contava come contesto tecnico – ora conta solo come dato
  autonomo („Port 80"), non come parte di parola. E „1.3.3.6 216879"
  (numero posizione più articolo) non viene più oscurato come numero di
  telefono. I veri indirizzi IP e numeri di telefono in tali elenchi
  restano riconosciuti.
- **Le righe articolo nelle offerte valevano come codice postale con
  località.** „35252 DIETZEL SALR" (numero articolo con produttore) e
  „1000 AWG" (quantità con sezione conduttore) venivano oscurati in righe
  di posizione numerate come indirizzo, perché una parola in maiuscolo
  dietro un numero valeva come nome di luogo in maiuscolo. Nelle liste di
  posizione ciò non vale più; „1080 WIEN" nel blocco indirizzo e luoghi
  in minuscolo restano riconosciuti ovunque.
- **Il riconoscimento nomi aggiuntivo oscurava, nelle offerte, righe di
  ruolo e intestazioni di colonna.** „Partiestundensatz Monteur +
  E-Helfer" valeva 49 volte come persona, l'intestazione di colonna „Pos.
  Bezeichnung Menge EH" 19 volte come luogo – un ordine di 19 pagine
  diventava così illeggibile. Tali rilevamenti in righe di posizione ora
  cadono, se portano essi stessi caratteri che nessun nome ha (più,
  barra, cifra, sigla) – anche quando la riga termina con un importo
  („Alternativ Markt … - PV/LS AC-Versorgung 1 290,00"). I nomi in
  elenchi e liste – per cui esiste il livello – restano intatti.
- **„Der Kunde" rendeva, nelle condizioni commerciali, ogni „Kunde" un
  nome.** Se il riconoscimento nomi aggiuntivo includeva l'articolo nel
  rilevamento, questo valeva come nome a due parole e proteggeva tutti gli
  altri 35 punti della stessa parola. Ora l'articolo viene sottratto, e
  „der Kunde" cade come già finora „des Kunden".
- **Le etichette valevano come valore.** „E-Mail" veniva oscurato sette
  volte come indirizzo email, „Telefonnummer" e „Faxnummer" come numero
  di telefono. Un indirizzo senza @ e un numero di telefono senza cifre
  non contano più.
- **Sigle di colonna di una lettera („L: 154,50", „S: 0,00") valevano
  come nome** – 25 volte in un'offerta fotovoltaica. Una singola lettera
  non è né nome né luogo.
- **Le pagine PDF venivano convertite in immagine molto troppo
  spesso.** Due cause, entrambe trovate in offerte reali: se un PDF
  compone ogni glifo come comando proprio e vi sta sotto un glifo spazio
  senza carattere di testo, l'assegnazione si spostava di uno da quel
  punto – dal valore rimosso restava l'ultima lettera
  („ŠkodaTopCar**d**"), e il controllo successivo rasterizzava la pagina
  a ragione. E una parola divisa a fine riga („Datenschutz-") valeva,
  a causa del marcatore di divisione della libreria di lettura, come
  spostata. Entrambi corretti: un'offerta di veicolo è passata da 4
  pagine rasterizzate a 0, un ordine di 19 pagine da 7 a 0 – il carattere
  resta carattere, il file resta piccolo.
- **Corretti altri due motivi di rasterizzazione:** se un documento porta
  con sé un carattere chiamato „F1", i segnaposto sopra le immagini
  venivano impostati nel suo carattere ed erano illeggibili – ora il
  carattere di etichettatura proprio riceve un nome libero. E se manca
  alla libreria di lettura uno spazio in mezzo a un lungo comando di
  testo, il punto viene ora dimostrato anche per caratteri multibyte
  (stesso codice, stesso carattere) invece di essere indovinato alla
  fine – prima restava una lettera del valore rimosso e il testo residuo
  si spostava visibilmente di lato. Inoltre due ultimi casi: un comando
  composto da decine di glifi spazio faceva scappare l'assegnazione (il
  nome successivo restava), e un titolo grande con larghezza di
  avanzamento non trovava il suo primo carattere (il nome dell'azienda
  restava). **Di nove offerte reali, ora non viene più rasterizzata
  nemmeno una singola pagina** – prima erano 30 su 90.
- **Durante la rasterizzazione le immagini sparivano sotto un blocco
  nero.** Se una pagina deve essere convertita in immagine, viene
  renderizzata dall'originale – e questo non conosce alcuna bonifica
  immagine. Finora quindi *ogni* area immagine della pagina cadeva sotto
  una barra, anche quelle non toccate. Su un'offerta, indirizzo e due
  loghi di certificazione stavano nella stessa immagine di intestazione;
  la barra portava via anche i loghi. Ora viene inserita l'immagine già
  bonificata: l'indirizzo al suo interno è oscurato, tutto il resto resta
  visibile. Un'immagine rimossa lascia carta bianca invece di un riquadro
  nero.

- **Le scansioni bonificate diventavano molte volte più grandi
  dell'originale.** Ogni immagine in cui era stato oscurato qualcosa
  tornava nel file come immagine grezza non compressa – con una
  scansione di 24 pagine cresceva così da 11,8 a 52,9 MB. Le immagini
  mantengono ora il tipo in cui erano presenti: una foto resta una foto,
  una scansione fax resta bianco e nero, un'immagine senza colore non
  viene depositata come immagine a colori. Lo stesso file è ora di 15,6
  MB, senza differenza visibile.

- **I file PDF scansionati da apparecchi d'ufficio tornavano come motivo
  a strisce.** Tali scansioni pongono la scrittura come livello bianco e
  nero nitido sopra un'immagine a colori grossolana – Canon, Xerox e
  Kofax costruiscono così i loro file. Durante l'oscuramento
  nell'immagine, questo livello veniva riscritto in modo errato; il
  risultato era illeggibile. Su un'offerta di sei pagine ciò colpiva nove
  di sedici immagini. Ora viene trattata correttamente, nel suo colore
  proprio, e i punti oscurati sono davvero spariti.

- **„Rimuovi tutte le immagini" toglieva a una pagina scansionata il suo
  testo.** Il livello di scrittura di una tale scansione è tecnicamente
  un'immagine – veniva rimosso o sfocato insieme, e restava un foglio
  vuoto. Ora resta; loghi, timbri e firme continuano a cedere.

- **Il controllo delle pagine PDF danneggiate non rasterizza più a causa
  di uno scostamento minimo.** Un pezzo di testo ancorato di nuovo
  durante la bonifica può spostarsi fino a due punti; il confronto
  immagine lo contava comunque come danno e ricostruiva la pagina come
  immagine – così andavano perse grafiche vettoriali come linee di
  tabella, e sopra i punti di rilevamento stava una barra invece di un
  segnaposto. Il confronto ora consente lo stesso piccolo scostamento del
  controllo parola; i veri danni continuano a essere rilevati.

- **Il recupero di molti valori in successione non falliva più su
  Windows con „Accesso negato".** Chi in un file d'ufficio annullava
  molte righe di pannello brevemente in successione poteva fallire per un
  blocco file di breve durata dell'antivirus; la sostituzione ora attende
  brevemente tali blocchi.

- **Il percorso Windows della trasmissione di comandi terminava il
  verificatore invece di verificare.** Il controllo di vitalità
  dell'istanza in ascolto inviava, su Windows, per errore un vero
  Ctrl+C al proprio gruppo console; ora interroga il sistema senza
  segnale.

- **Le etichette di campo a più parole non funzionavano, mentre
  funzionavano i loro frammenti.** „Date of birth", „Bank account",
  „Cuenta bancaria" e „Numero de cliente" stavano nell'elenco delle
  etichette, ma venivano lì scomposte in singole parole e quindi non
  corrispondevano mai; restavano frammenti di parola come „de" e „of",
  che da allora valevano come etichetta – „de" è però un componente di
  nome („Anna de Vries"). Entrambi corretti: le espressioni ora agiscono
  come intere, i frammenti sono spariti.

- **Le formule di saluto tedesche con „ß" venivano trattate come nome
  di persona nonostante la voce.** Sotto „Herzliche Grüße" o „Mit
  freundlichen Grüßen" stava nel risultato un segnaposto, sebbene
  entrambe le espressioni stiano da sempre nell'elenco contrario. La
  causa era una scrittura che nel confronto non arrivava mai; erano
  interessate otto voci su cinque elenchi. Ora agiscono tutte.

- **„John Staff" restava non sostituito.** Un cognome che è al contempo
  un'intestazione di colonna inglese veniva scartato insieme dal filtro
  etichette. L'intestazione continua a restare intatta, il nome
  sottostante viene di nuovo sostituito.

- **I valori da campi modulo etichettati restano protetti nel livello
  IA.** L'arbitro locale del livello IA finora riceveva da valutare anche
  rilevamenti il cui significato era già comprovato dall'etichetta di
  campo („Data di nascita:" sopra il valore) – e poteva scartarli. Tali
  valori strutturalmente comprovati non gli vengono più sottoposti. Il
  file di assegnazione indica ora per ogni sostituzione anche il percorso
  di riconoscimento („comprovato").

- **Una pagina PDF il cui testo mantenuto ha subito danni durante la
  bonifica viene ora riconosciuta e ricostruita come immagine
  dell'originale.** Con alcuni caratteri dei generatori, i punti di
  testo mantenuti potevano apparire dopo la bonifica come blocchi neri o
  le parole si avvicinavano, sebbene tutti i dati da rimuovere fossero
  stati rimossi correttamente. Maskuro confronta ora il risultato parola
  per parola e pixel per pixel con l'originale; una pagina danneggiata
  viene sostituita dalla sua immagine pulita — con barre di oscuramento
  sopra i punti di rilevamento, aree immagine oscurate e testo
  ricercabile. La pagina resta leggibile, la rimozione affidabile.

### Modificato

- **Nelle interfacce tradotte, ogni termine tecnico si chiama ora
  ovunque allo stesso modo.** Per una stessa parola tedesca stavano, a
  seconda della finestra, due o tre traduzioni affiancate: il registro
  di controllo si chiamava in norvegese in parte „Revisjonslogg", in
  parte „Kontrollogg", il livello gratuito in parte „Gratisnivå", in
  parte „Gratisversjon" – e similmente in una dozzina di altre lingue.
  Chi cercava un'impostazione la trovava nella finestra successiva con un
  altro nome. È stato uniformato sulla parola che l'interfaccia usa
  comunque più spesso.

  In questo sono emersi punti in cui una parola stava per due cose
  **diverse**: francese, greco e coreano usavano per „oscurare" e
  „mascherare" la stessa espressione – proprio dove il programma spiega
  la differenza („Oscurare rimuove senza sostituto, mascherare mantiene
  la forma"). Ora entrambi sono distinti. Per lo svedese questa decisione
  è ancora aperta: lì l'oscuramento si chiama „maskera" – la stessa
  parola del mascheramento.

- **La domanda sul tipo di utilizzo al primo avvio è stata eliminata.**
  Poco dopo l'avvio compariva una finestra („Privato o in azienda?"), e
  nelle impostazioni c'era una riga in merito. Entrambe non esistono
  più – senza sostituto. Un dato a cui non è collegato nulla indica in
  modo errato chi vuole la licenza sbagliata, e chi è onesto non ne ha
  bisogno; costava a ognuno un clic in un momento in cui nessuno pensa ai
  tipi di licenza. Quale licenza sia quella giusta sta scritto dove viene
  decisa: sulla pagina prezzi, nella cassa e nella guida. Le aziende che
  distribuiscono Maskuro centralmente continuano a imporre il tipo di
  utilizzo tramite il file di direttive.

- **Gli avvisi sul tipo di licenza nominano il caso di cui si tratta.**
  La licenza privata vale esclusivamente per l'uso privato; ogni lavoro
  professionale o commerciale richiede la licenza aziendale – anche come
  ditta individuale senza dipendenti. Ciò stava scritto così nelle
  condizioni di licenza, ma né nel programma né nella guida: lì si
  parlava sempre solo del dominio aziendale, e questo non copre proprio
  questo caso: il computer di un lavoratore autonomo non appartiene a
  nessun dominio. L'avviso alla lettura di una licenza privata lo dice
  ora, così come il capitolo licenza del manuale e le domande frequenti,
  che per questo hanno ricevuto una voce propria. Continua a non essere
  bloccato nulla.

- **I percorsi non ancora distribuiti stanno ora insieme.** Le
  impostazioni hanno ricevuto una pagina „Sviluppatore"; lì stanno il
  riconoscimento massimo (IA) con la sua controprova, il catalogo elenchi
  di parole e il monitoraggio cartella. Tutti e tre sono costruiti, ma
  non testati sul campo – sono quindi visibili solo con una licenza
  sviluppatore, e ovunque contemporaneamente: la pagina, le voci di menu
  e l'effetto durante l'esecuzione dipendono dalla stessa decisione.
  Senza questa licenza, un livello IA attivato in precedenza resta senza
  effetto; la sua impostazione non viene cancellata e torna valida non
  appena il percorso viene distribuito.

### Migliorato

- **„Cosa viene cercato" mostra tre elenchi aggiuntivi dal riconoscimento
  nomi.** Le formule di cortesia dopo le quali la parola successiva viene
  letta come nome; i titoli e ruoli che dopo **non** sono ancora il nome
  („Herr Bürgermeister Huber"); e le ottanta etichette multilingue con
  cui vengono riconosciuti numeri di pratica, procedimento e fascicolo.
  Tutti e tre agivano già da sempre, ma non erano visibili nella
  panoramica.

- **„Cosa viene cercato" mostra due elenchi di parole finora mancanti.**
  Le formule di cortesia e i titoli che rendono nome una parola
  precedente („Herr", „Frau", „Dr."), e le sigle delle organizzazioni di
  normazione con cui Maskuro distingue un riferimento normativo come
  „ÖNORM B 2110" da una persona. Entrambi influenzano il riconoscimento
  da sempre, ma non erano nella panoramica.

- **Liste di posizioni, indici, elenchi di dotazioni e riferimenti
  normativi restano leggibili.** Il riconoscimento vede ora la forma
  della riga: un nome indovinato in una riga di struttura („1.3.1
  Energieerdkabel 1kV"), una riga di indice con punti di guida,
  un'elencazione („- kabelloses Laden mit Magnetring"), sopra una riga di
  quantità/prezzo, in un'intestazione di colonna o dietro „mittels" è un
  termine tecnico e non viene più sostituito. I nomi reali restano
  protetti – tramite formula di cortesia, etichetta di campo e la prova
  in un altro punto del documento; sul corpus di misurazione nessun
  singolo dato ha perso la sua protezione. Nel corpus aziendale i falsi
  allarmi scendono così da 25 a 6.

- **Intestazioni, etichette di modulo e formule di saluto vengono
  scambiate più raramente per nomi – in tedesco e inglese.** Gli elenchi
  di parole con cui Maskuro distingue i termini tecnici dai nomi di
  persona sono cresciuti notevolmente: etichette da fatture, moduli e
  posta amministrativa („Numero di pratica", „Causale", „Centro di
  costo", „Sort code", „Subtotal"), intestazioni di sezione di
  candidature e rapporti („CARRIERA", „QUALIFICHE", „SUMMARY",
  „REFERENCES"), tipi di documento tedeschi e inglesi
  („Auftragsbestätigung", „Niederschrift", „Timesheet", „Agreement")
  nonché forme di comando da istruzioni („Invia…", „Select…"). Il lato
  inglese finora era notevolmente scarso.

- **I campi etichettati rivelano ora cosa contengono anche quando
  l'etichetta è composta.** „Indirizzo di consegna", „Indirizzo di
  fatturazione", „Responsabile pratica", „Titolare conto", „Contact
  person" e „Billing address" assegnano ora il valore accanto o sotto
  allo stesso tipo del semplice „Indirizzo" o „Nome" – in un modulo
  compilato con caselle, questa è la differenza tra trovato e trascurato.

- **Nella finestra di correzione la rotellina del mouse continua a
  scorrere al bordo pagina.** Chi continua a scorrere alla fine di una
  pagina finisce in cima alla successiva; chi torna indietro all'inizio
  finisce in fondo alla precedente – un documento si può così scorrere da
  cima a fondo senza toccare i pulsanti pagina. La tastiera (Pag↑/Pag↓)
  lo sapeva già fare; una breve pausa tra due cambi di pagina impedisce
  che l'inerzia di un trackpad porti attraverso metà documento.

- **Le miniature di pagina nella finestra di correzione stanno centrate
  nel pannello.** Finora erano attaccate al bordo sinistro, e
  allargando cresceva solo il margine vuoto a destra.

- **La barra degli strumenti della finestra di correzione mostra i suoi
  gruppi.** I separatori hanno ora respiro e colore, „Cerca" e „Applica a
  tutte le pagine" stanno come gruppi propri accanto agli strumenti, e
  „Applica" compare solo più per i tipi di documento in cui può avere
  effetto. Ogni voce in barra e menu porta ora un'immagine: „Righe di
  testo" e la lente di confronto hanno ricevuto icone proprie (la lente
  condivideva finora la sua con „Prima/Dopo"), inoltre zoom, pagina
  intera, larghezza pagina, ruota, sfoglia e le scorciatoie da tastiera.
  „Apri con programma di sistema" sta ora anche nella barra accanto a
  Stampa – il percorso dal risultato completato al programma abituale è
  un clic, non un giro nel menu.

- **Nella bonifica appunti c'è di nuovo scritto che va controllato.**
  Nelle impostazioni l'avviso sta in modo permanente accanto
  all'interruttore: Maskuro può trascurare dati personali o trattare
  erroneamente informazioni, il testo incollato va controllato prima
  della trasmissione. All'attivazione lo indica inoltre il messaggio, e
  viene annotato nell'area di output – anche quando nell'area
  informazioni non gira alcuna icona. A ogni singola operazione di copia
  non compare volutamente: un avviso che comparisse cinquanta volte al
  giorno non verrebbe più letto dopo la terza volta.

## 0.10.36-beta.1 – 20 agosto 2026

### Migliorato

- **I documenti aziendali tecnici non vengono più annerite per errore.**
  Quattro freni di riconoscimento, ricavati da undici offerte e ordini
  reali: i numeri di struttura („1.3.1.1") non valgono più come indirizzi
  IP, i riferimenti a norme („ÖNORM EN 62446") e i codici identificativi
  non più come codice postale o numero di telefono, e le parole di ruolo
  dopo articoli („il cliente", „del committente") non più come nomi – nelle
  condizioni commerciali di un'offerta reale sono così di nuovo leggibili
  tutte le 46 parole di ruolo invece di essere annerite. Gli indirizzi con
  codice paese („A 3390 Melk", „D-94032 Passau") vengono ora rimossi
  completamente, invece di lasciare il codice postale orfano.

- **Gli elenchi di parole sono ora completamente consultabili.** Sotto
  „Guida → Elenchi di parole …" si possono cercare gli elenchi di
  riconoscimento e controincrocio usati localmente, con lingua, scopo,
  fonte e contenuto. Ne fanno parte anche gli elenchi Wordfreq, medici,
  personali e gestiti centralmente, così come le scorte per i valori
  sostitutivi inventati. Il manuale descrive il catalogo in una sezione a
  parte.

- **Le righe dei file completati mostrano ora la lingua di riconoscimento
  usata.** Dietro „completato" compare ora ad esempio „Tedesco" o
  „Inglese", in modo che una scelta automatica della lingua non adatta
  salti subito all'occhio. Se è dovuta intervenire un'altra lingua
  installata, una freccia mostra entrambe le lingue.

- **La nuova lente di confronto mostra durante la lettura subito il punto
  corrispondente nell'originale.** Il suo estratto ingrandito dell'originale
  segue il puntatore del mouse sopra il risultato, che resta modificabile;
  nel testo segue il paragrafo. La lente si può usare al bordo della
  finestra oppure staccare come finestra propria, massimizzabile. Il suo
  zoom è regolabile direttamente tra 50 e 300 per cento e viene memorizzato
  come l'attivazione. „Ripristina" riporta anche una lente massimizzata o
  agganciata in modo sfavorevole a una dimensione utilizzabile a sinistra. I
  valori originali sostituiti sono evidenziati in giallo nella lente, in
  modo che le parole interessate risaltino subito durante la lettura. Una
  volta attivata, si riapre nei documenti idonei futuri – anche dopo un
  riavvio del programma. Il precedente commutatore prima/dopo resta nel
  menu Visualizza. Il manuale la descrive in una sezione a parte.

- **Le attestazioni open source e sui modelli sono ora precise per ogni
  release.** La generazione del pacchetto produce un elenco componenti
  leggibile da macchina con gli hash dei testi di licenza allegati. Fonti
  MPL, provenienza dei modelli, revisioni fisse, modifiche e SHA-256
  vengono documentati separatamente; i modelli scaricati successivamente
  ricevono la loro attestazione di provenienza direttamente nella cartella
  del modello. Gli elenchi di riferimento mobili di Tesseract e spaCy sono
  stati fissati stabilmente. Gli artefatti di vendita restano bloccati
  finché tutte le fonti e gli allegati dei modelli non sono pubblicati e
  verificati.

- **La base dati wordfreq locale è ora completamente documentata dal punto
  di vista della licenza.** La generazione del pacchetto verifica la
  versione 3.1.1, 39 elenchi piccoli invariati incluso il CJK e la mappa
  dei caratteri cinesi rispetto a numero, dimensione e checksum del
  manifesto. Nota sul codice Apache-2.0, licenza CC-BY-SA-4.0 completa,
  attribuzione, fonti dei dati e gli elenchi grandi, Jieba e non supportati
  omessi sono documentati nel pacchetto.

- **Le parole frequenti di frase vengono ora annerite per errore più
  raramente.** Un dizionario di frequenza locale funge da controprova
  aggiuntiva quando il riconoscimento dei nomi scambia per una persona un
  verbo, un pronome, un articolo o una preposizione. Il dizionario non
  decide mai da solo: sostantivi, nomi composti da più parti e nomi in
  campi, elenchi e dopo formule di cortesia restano protetti. Cinese,
  giapponese e coreano usano esclusivamente i confini di token esatti dei
  loro modelli linguistici già presenti; per le lingue non presenti non
  viene impiegata nessuna lingua di dizionario presunta simile. Per questo
  nessun testo di documento viene trasmesso in internet.

- **I termini tecnici di prodotto e dotazione non vengono più scambiati così
  facilmente per nomi o luoghi.** Il controincrocio locale collega ora
  frequenza, categoria grammaticale, formazione tecnica delle parole e
  ambiti tematici. Restano così nel documento ad esempio „Travel-Assistent",
  „Family-Bonus", „WLTP-Wert", „Easy-Start" e termini composti su numeri,
  intestatari o freni. Le componenti inglesi vengono cercate localmente
  anche in testo tecnico tedesco; nomi propri reali, formule di cortesia e
  campi persona/luogo mantengono la priorità. Inoltre una „garanzia del
  produttore di 2 anni" non vale più come età.

- **I diritti di licenza Qt/PySide sono ora completamente tracciabili.** Il
  pacchetto del programma contiene inoltre il testo completo della GPL-3.0,
  le versioni esatte di Qt, un'offerta di codice sorgente e una guida in
  tedesco/inglese per lo scambio delle librerie dinamiche, inclusa la
  nuova firma locale su macOS. Una build di vendita viene bloccata finché
  gli archivi sorgente esatti della versione distribuita non sono
  disponibili sulla pagina codice sorgente propria.

- **Licenza e stato di aggiornamento indicano ora per ogni livello in modo
  univoco cosa vale.** Nella finestra della licenza e nelle impostazioni di
  aggiornamento è indicato se sono inclusi aggiornamenti, fino a quale
  giorno arrivano e se la versione in uso resta utilizzabile in modo
  permanente. Le licenze private non installano più, dopo la data limite,
  una versione uscita successivamente; anche un installer scaricato di
  recente riconosce, dalla sua data di pubblicazione incorporata, se la
  chiave inserita lo copre. L'ultima versione privata coperta resta
  utilizzabile in modo permanente. Se invece termina un abbonamento
  aziendale, terminano uso e aggiornamenti; periodo di prova e livello
  gratuito non si aprono come scorciatoia.

- **Le licenze private permanenti trovano ora anche dopo una
  reinstallazione lo stato di programma corretto.** Un catalogo di
  versioni firmato elenca tutte le versioni stabili e i loro pacchetti. Se
  l'ultimo installer coperto dall'acquisto non è più disponibile, si può
  usare automaticamente esattamente la successiva versione stabile
  disponibile più alta – mai una beta o una nightly. In caso di
  installazione troppo recente, il cliente può installare la versione
  consentita oppure passare alla pagina di acquisto per un nuovo periodo
  di aggiornamento; un passo indietro non avviene silenziosamente. Vale
  anche per installazioni MSI gestite.

- **L'oscuramento automatico dei volti è ora descritto in modo univoco.**
  La guida del programma e il testo sulla privacy chiamano la funzione
  „Riconoscere e rendere irriconoscibili le aree del volto" e la
  distinguono da identificazione, riconoscimento, confronto facciale,
  modelli biometrici e banche dati di persone o volti. Segnalano inoltre
  chiaramente che il riconoscimento, completamente locale, può trascurare
  aree o segnarle per errore e che il risultato va quindi controllato
  visivamente. Anche per un singolo file immagine bonificato, il rapporto
  del risultato indica ora le aree del volto riconosciute e pixelate; un
  riconoscimento testo mancante non viene più descritto erroneamente come
  file completamente invariato.

## 0.10.36-alpha.20260820 – 20 agosto 2026

### Corretto

- **I dati anonimizzati si possono ora recuperare completamente
  indipendentemente dall'ordine.** Il recupero precedente cercava il valore
  tramite ancore di testo visibili. In tabelle dense, segnaposto
  direttamente adiacenti e archivi Office/mail invisibili mancavano queste
  ancore; a volte un termine diventava recuperabile solo dopo che un altro
  testo in chiaro aveva creato per caso una nuova ancora. Ora risultato e
  originale vengono confrontati per ogni vero supporto di formato con
  l'assegnazione completa, e vengono scritti solo i punti occupati del
  valore scelto.

- **Nomi, indirizzi email, numeri e termini di controllo propri restano
  utilizzabili in modo univoco anche in caso di riconoscimento
  sovrapposto.** Se lo stesso valore in chiaro è assegnato a due tipi,
  decide il segnaposto effettivamente presente nel punto del rilevamento
  insieme alla riga della sidebar cliccata. Una coppia valore/segnaposto
  non occupata resta comunque bloccata in modo sicuro.

- **I casi speciali di posta non lasciano più segnaposto nascosti.** Vale
  per oggetti codificati MIME, allegati di testo e nomi separati da markup
  HTML in EML e MSG. L'HTML UTF-8 senza indicazione propria del set di
  caratteri non viene più ricodificato in mojibake nei file Outlook a ogni
  passo di modifica; i risultati più vecchi già scritti così restano
  recuperabili.

### Migliorato

- **Una nuova matrice di rilascio serve ogni riga anonima della sidebar
  singolarmente e volutamente all'indietro.** Verifica tutti i 14 formati
  di testo, Office, web e mail nonché PDF, poi anche formule, attributi,
  relazioni, commenti, intestazioni mail, allegati e depositi interni
  secondari. L'esecuzione completa su macOS comprende ora 149/149 script
  di verifica verdi.

## 0.10.35-alpha.20260820 – 20 agosto 2026

### Migliorato

- **Le misurazioni linguistiche ora confrontano davvero uguale con
  uguale.** Il corpus di misurazione regolare contiene gli stessi 14 casi
  di documento con gli stessi sette compiti di testo e quattro compiti di
  immagine in tedesco e inglese. Un'esecuzione completa ripete esattamente
  questa matrice per tutte le dodici lingue del corpus presenti. Moduli,
  tabelle, chat e altri campioni strutturali non ancora completamente
  tradotti restano presenti, ma vengono indicati separatamente e non più
  mescolati nelle quote linguistiche.

- **L'esecuzione completa scrive un rapporto di misurazione proprio per
  ogni lingua.** Senza selettore di lingua vengono verificati
  volutamente tedesco e inglese; `--alle-sprachen` richiede il corpus
  completo delle dodici lingue e si interrompe prima del primo documento
  se manca una lingua o un caso. I risultati con lo stesso nome si trovano
  in cartelle di lingua separate. Il rapporto complessivo indica, oltre
  alla quota di rilevamento ponderata, anche la media non ponderata delle
  quote linguistiche.

- **Il confronto linguistico aperto mostra ora anche il suo limite
  effettivo.** Nell'esecuzione regolare con riconoscimento testo, tedesco
  e inglese rimuovono 218/218 dati noti senza falsi allarmi. Il test
  completo con riconoscimento testo e livello Alto rimuove 1.255/1.308
  dati con 17 falsi allarmi; undici lingue raggiungono il 100 per cento,
  l'hindi il 51 per cento. Le quote complete precedenti si basavano su
  quantità di documenti e valori attesi disomogenee e non sono confrontabili
  con la nuova matrice.

## 0.10.34-alpha.20260819 – 19 agosto 2026

### Corretto

- **I nomi ricorrenti più volte restano raggiungibili nella sidebar dopo un
  singolo recupero.** Finora l'intera riga del nome spariva già dopo il
  primo punto `[NOME]` recuperato. Altri punti dello stesso nome restavano
  quindi come segnaposto e venivano a volte persino bloccati, finché non
  erano stati recuperati altri nomi. Ora la riga scompare solo dopo
  l'ultimo punto; il testo in chiaro già recuperato non viene comunque
  anonimizzato di nuovo automaticamente. Vale anche per un recupero
  collettivo riuscito solo parzialmente e per lo strumento a cornice nei
  PDF.

- **„Annulla sostituzione" funziona anche dall'anteprima pagina di Office.**
  La pagina visibile lì è solo un'anteprima PDF volatile; ora viene
  modificato correttamente il documento Word, foglio di calcolo o
  presentazione sottostante e successivamente l'anteprima viene aggiornata.

- **Il recupero ora riporta indietro completamente anche le controparti
  nascoste di un valore.** Nei file Word, OpenDocument, Excel e PowerPoint
  gli stessi dati possono trovarsi anche in formule, commenti, diagrammi,
  valori di campo, testi alternativi e destinazioni di collegamento; HTML,
  EML e MSG li portano inoltre in attributi, JSON, intestazioni di
  messaggio e allegati. Finora, a seconda del formato, una parte restava
  come segnaposto. Ora ogni dato offerto nell'area dei rilevamenti può
  essere recuperato indipendentemente e in qualsiasi ordine. I metadati,
  le cronologie delle modifiche e le intestazioni di trasporto rimossi
  volutamente restano rimossi per motivi di sicurezza.

- **Nel recupero dalle immagini non resta più una linea nera di bordo.** Il
  bordo destro e inferiore di una cornice erano tracciati con un pixel di
  troppo poco durante la copia dall'originale. Le coordinate ora
  corrispondono all'oscuramento.

### Migliorato

- **Il controllo di rilascio invia ora ognuna delle 22 estensioni di file
  supportate attraverso un giro completo.** I file con contenuto ricco
  vengono bonificati, tutti i valori offerti ripristinati e infine
  controllati a fondo. A ciò si aggiungono un vero utilizzo della sidebar,
  confronti immagine pixel per pixel e un rendering LibreOffice visibile di
  tutti e sette i formati d'ufficio. I piccoli test di regressione restano
  dove coprono un caso di errore o sicurezza proprio; un test HTML
  dimostrato doppio e il test della modalità bianco e nero rimossa sono
  stati eliminati.

- **Il corpus di misurazione completo di questa versione è disponibile per
  ricontrollare.** Il pacchetto contiene 294 documenti sintetici in dodici
  formati e dodici lingue, 2.564 dati noti, quattro elenchi attesi leggibili
  da macchina e una guida. Il download sulla pagina qualità usa un nome
  file dipendente dal contenuto, in modo che i browser non forniscano per
  errore una versione più vecchia dalla cache.

## 0.10.33-alpha.20260819 – 19 agosto 2026

### Nuovo

- **Anche nei file immagine si possono ora recuperare singoli punti
  dall'originale.** Lo strumento a cornice „Recupera originale" copia
  indietro i pixel nella stessa posizione dal file sorgente intatto. Il
  percorso resta bloccato se la sorgente manca o ha dimensioni immagine
  diverse; così non può essere inserito nessun contenuto da un punto
  spostato.

### Migliorato

- **Le barre di oscuramento manuali si agganciano ora per impostazione
  predefinita alle righe di testo.** Un trascinamento su più righe genera
  per ogni riga una barra di altezza uniforme e lascia libero lo spazio
  bianco tra di esse. Per firme, grafici e altri casi speciali, „Cornice
  libera" torna all'altezza scelta liberamente.

- **L'editor spiega il passo successivo direttamente sopra il
  documento.** L'indicazione cambia con tipo di documento e strumento e
  dice se ci si aspetta un clic su una parola, una selezione di testo o
  una cornice. Inoltre strumento, puntatore del mouse e anteprima dal vivo
  mostrano già prima del rilascio cosa succederà.

### Rimosso

- **L'output bianco e nero soggetto a errori è stato rimosso.** In alcuni
  PDF i campi di testo invisibili restavano spostati rispetto alla pagina
  rasterizzata; l'apparente riduzione delle dimensioni del file non valeva
  questo rischio di sicurezza e di visualizzazione. La bonifica PDF
  normale e la rasterizzazione mirata di pagine problematiche restano
  invariate.

## 0.10.32-alpha.20260819 – 19 agosto 2026

### Nuovo

- **Il monitoraggio cartella funziona ora davvero in background.**
  Ingresso, uscita e regole si trovano in una pagina propria sotto
  „Impostazioni". Viene avviato e fermato tramite l'icona Maskuro nella
  barra delle applicazioni o dei menu; la voce compare solo con la licenza
  sbloccata per questo. La finestra delle impostazioni può poi essere
  chiusa e la finestra principale ridotta a icona senza interrompere il
  monitoraggio.

- **L'editor di correzione ha ora un interruttore permanente per la
  modalità di apprendimento.** Si trova nell'area dei rilevamenti e nel
  menu „Strumenti". Se viene disattivato, non compaiono più domande sulla
  creazione di regole proprie né al recupero né dopo correzioni manuali.
  Maskuro memorizza la scelta per tutti i documenti aperti in futuro; il
  recupero stesso funziona invariato.

### Corretto

- **Il grande modello aggiuntivo si può caricare di nuovo.** Il deposito
  pubblico respingeva con 403 l'identificativo generico standard di
  Python. Gli scaricamenti dei modelli usano ora lo stesso percorso di
  rete Maskuro dedicato degli altri servizi propri; il file di quasi
  596 MB e il suo checksum restano invariati.

- **Una lente di confronto massimizzata non resta più appesa come una
  barra stretta al bordo superiore durante l'aggancio.** Prima
  dell'aggancio il suo stato di finestra libera viene normalizzato. Uno
  stato massimizzato salvato viene riportato anche alla successiva
  apertura a una dimensione modificabile.

- **Un recupero collettivo ora riporta indietro davvero tutti i valori
  selezionati in tabelle e altri formati di testo.** Per segnaposto
  anonimizzati come `[EMAIL]`, Maskuro finora scriveva i valori uno dopo
  l'altro. Non appena il primo era sostituito, i numeri di tutti i
  restanti punti di rilevamento avanzavano, ma il piano già calcolato
  puntava ancora ai numeri vecchi. Per questo tornava indietro solo una
  parte della selezione. Ora tutti i valori scelti dello stesso segnaposto
  vengono scritti insieme e con numeri di rilevamento stabili. Se un punto
  diventa univoco solo grazie a un altro valore recuperato, Maskuro lo
  ricontrolla nello stesso passaggio – l'ordine della selezione non conta
  più.

- **„Annulla sostituzione" non tralascia più valori selezionati nei PDF.**
  Se un segnaposto si trovava molto vicino dietro un'altra parola oppure
  nell'originale una virgola era attaccata direttamente al valore, il
  controllo di posizione poteva attribuire per errore la parola vicina o
  il segno di punteggiatura al valore. Nel recupero collettivo restavano
  quindi singoli segnaposto e righe di rilevamento. Il controllo ora si
  orienta sull'effettivo inizio della parola e considera anche una
  rotazione di pagina diversa tra originale e risultato.

- **Il testo PDF recuperato mantiene ora la sua dimensione originale.**
  Finora fungeva da riferimento il segnaposto già impostato più piccolo;
  inoltre valeva anche per il testo originale il limite massimo di
  11 punti pensato per i segnaposto. Ora il riquadro e la dimensione del
  carattere originali vengono ripresi dal file sorgente – sia con lo
  strumento a cornice sia nel recupero dal pannello dei rilevamenti.

### Migliorato

- **L'avviso di controllo indica ora più chiaramente il rischio
  residuo.** Dice espressamente che Maskuro può trascurare dati o
  trattare erroneamente informazioni, e invita prima di ogni pubblicazione
  o trasmissione a un controllo completo e, se necessario, a una
  correzione manuale. Vale anche per il testo dagli appunti ed è ripreso
  completamente in tutte le 17 traduzioni.

- **Il registro di controllo parte ora anche all'interno delle sue righe
  senza nome utente.** Il registro stesso resta disattivato finché
  un'azienda non lo attiva volutamente. Dopo, senza un'ulteriore
  disposizione aziendale, non compare alcun nome utente né in una riga né
  nel nome di un file mensile centrale; lì serve per una separazione
  sicura uno pseudonimo non indovinabile, derivato solo dal segreto di
  profilo locale casuale. La finestra di dialogo della licenza non
  raccomanda più l'attivazione, presuppone „Senza registro" e rimanda in
  anticipo a consiglio aziendale, rappresentanza del personale e
  protezione dei dati.

- **Sostituisci ora indica cosa sostituisce.** Un nome marcato diventa
  `[NAME_3]`, un luogo `[ORT_1]`, un numero di telefono `[TELEFON_2]` –
  invece che finora tutto `[BEGRIFF_n]`. Il tipo viene riconosciuto al
  clic; se non è univoco – una parola comune, oppure un nome *e* un luogo
  in una selezione – resta il termine generico. Un segnaposto che
  afferma un tipo sbagliato sarebbe peggiore di uno che non ne indica
  nessuno.

- **Gli strumenti nella finestra di correzione hanno ora un tasto.** **S**
  oscura, **E** sostituisce, **Z** recupera l'originale, **V** pixela.
  Nella visualizzazione testo agiscono subito sulla selezione, nell'anteprima
  pagina scelgono lo strumento. **Le lettere seguono la lingua** in cui si
  usa il programma – inglese B/R/O/P, italiano O/S/R/P –, perché un aiuto
  mnemonico aiuta solo nella lingua propria. Il tasto è indicato sul
  pulsante. Chi sta digitando nella barra di ricerca continua a scrivere
  lettere normalmente – lì non hanno effetto.

- **Il programma segnala una volta al giorno in che stato funziona – senza
  alcun identificativo.** Così contiamo quante installazioni sono in uso e
  come si distribuiscono tra periodo di prova, livello gratuito e licenza.
  Vengono inviati stato, sistema operativo, versione, canale, paese,
  lingua, ambiente e livello di riconoscimento – **niente sui vostri
  documenti e niente da cui il vostro computer potrebbe essere
  riconosciuto**. Due segnalazioni da parte vostra appaiono a noi come
  segnalazioni di due persone diverse; da esse non si può ricostruire un
  singolo percorso. Cosa viene inviato esattamente e come si può
  disattivare è scritto nel testo sulla privacy al punto 5.

- **Le pagine acquisite di traverso ora si raddrizzano da sole.** Un foglio
  scansionato storto senza annotarlo viene riconosciuto dalla correzione
  tramite il flusso del testo e la visualizzazione viene raddrizzata. Dove
  ciò non è possibile – con una scansione pura senza testo leggibile – due
  nuove voci nel menu „Visualizza" ruotano manualmente (Ctrl+Maiusc+L e
  Ctrl+Maiusc+R). Viene ruotata solo la visualizzazione: nel file non
  cambia nulla, e l'oscuramento colpisce comunque esattamente il punto su
  cui si clicca.

- **L'output locale ora porta con sé le proprie licenze in modo completo e
  visibile.** La build determina i pacchetti Python effettivamente
  inclusi, deposita i loro testi di licenza con panoramica delle versioni
  sotto `lizenzen` e si interrompe in caso di lacuna. Anche Qt, Tesseract e
  il modello per i volti hanno i loro testi necessari; le condizioni per
  Maskuro stesso sono allegate come contratto di licenza.

- **Ora si vede in quale segnaposto si trova il cursore.** Chi clicca in
  un segnaposto lo vede illuminarsi per intero – comprese parentesi e
  numero. Il pulsante „Recupera selezione" reagiva già prima a un semplice
  clic; solo non si vedeva quale marcatore colpisse. L'illuminazione resta
  anche quando il mouse si sposta verso il pulsante.

- **Il puntatore del mouse indica ora quale strumento è selezionato.**
  Quattro strumenti condividono la stessa area e lo stesso gesto; finora
  apparivano tutti uguali. Mirino significa oscurare, mano chiusa
  sostituire, mano aperta recuperare.

- **Un documento Office preparato ora si rifiuta da solo grazie al
  programma stesso.** Un file Word, Excel o OpenDocument può contenere
  istruzioni che, all'apertura, prelevano nel proprio testo un file
  esterno del computer o riempiono la memoria di lavoro. Entrambi i casi
  venivano respinti anche prima – ma dalla libreria XML integrata, non da
  Maskuro. Ora è il programma stesso a deciderlo, indipendentemente da
  quale versione di questa libreria si trova nel pacchetto. Per i
  documenti normali non cambia nulla.

### Corretto

- **Il pannello dei rilevamenti rimuove ora i segnaposto oscurati.** Se ad
  esempio `[NAME_1]` veniva oscurato nella finestra di correzione, la sua
  riga di valore restava finora a destra, anche se nel documento non c'era
  più un punto del genere. Ora la riga scompare con l'ultimo punto di
  rilevamento; se lo stesso segnaposto compare ancora in un altro punto,
  resta.

- **Nel recupero su una pagina ruotata la parola vicina ora resta al
  proprio posto.** La barra di oscuramento sporge volutamente un po' oltre
  il testo; già questo margine stretto poteva finora portare via una
  parola adiacente come „nel". Ora conta solo una sovrapposizione netta,
  non il semplice contatto sul bordo.

- **Una seconda sostituzione nella stessa riga portava via la frase
  successiva.** Chi sostituiva due volte di seguito „Elaborazione Quaxi
  Blubbo si occupa" otteneva „Elaborazione [ORT_1] [ORT_2]" – la parola
  dietro era sparita senza sostituto, senza alcun messaggio. La causa era
  il segnaposto accanto: il resto della riga dopo la prima sostituzione
  inizia con uno spazio, e la ricerca del suo punto di testo intercettava
  la parentesi di chiusura del vicino. Dopo, tutto era spostato di un
  carattere. Erano interessate tutte le righe in cui si sostituiva o
  oscurava due volte – anche nel recupero accanto.

- **Sostituisci non oscura più quando il segnaposto è troppo lungo.** Se
  accanto alla parola non c'era spazio per `[BEGRIFF_2]`, l'area veniva
  finora dipinta di nero – e così non si vedeva più nemmeno che lì c'era
  stato qualcosa, tanto meno era recuperabile. Ora viene scritta una forma
  più corta: `[BEGR_2]`, `[BE_2]`, in caso estremo `[B_2]`. Il numero
  progressivo resta a ogni livello – è con esso che il recupero ritrova il
  punto. Solo dove nemmeno la forma più corta ci sta, resta la barra.

- **Sostituisci lasciava il testo quando nella stessa riga era già stato
  oscurato.** Chi nella finestra di correzione recuperava un nome
  dall'originale, di questo sostituiva il nome proprio (lì non c'era
  spazio – è diventata una barra) e dopo sostituiva il cognome, otteneva
  il segnaposto inserito, ma il nome **non rimosso**. Il problema è
  emerso solo dall'avviso della revisione. La causa era la riga stessa:
  dopo il primo oscuramento il suo resto inizia con uno spazio, e su
  questo la ricerca del punto di testo non trovava appiglio. Ciò
  riguardava ogni secondo oscuramento nella stessa riga.

- **Un riconoscimento avanzato attivato senza il suo modello ora salta
  all'occhio.** Il segno di spunta poteva essere impostato mentre il
  modello mancava – le impostazioni valgono per ogni installazione, ma il
  modello si trova accanto al programma. La bonifica girava allora senza
  il livello, senza una parola in merito. Ora il segno di spunta dice che
  il modello manca, e il risultato porta un avviso. La scelta fatta una
  volta resta comunque memorizzata: non appena il modello è caricato,
  torna a essere efficace.

- **Nell'anonimizzazione viene ora recuperato il termine giusto.** Chi
  sostituiva manualmente più termini e poi ne recuperava uno, otteneva
  sempre il **primo** – da „Schmidt" diventava „Müller". L'assegnazione
  memorizzava per segnaposto una sola sostituzione, e nell'anonimizzazione
  tutti portano lo stesso segnaposto; il secondo e ogni ulteriore termine
  andava perso. Ora ogni valore riceve la propria riga – anche
  nell'elenco delle sostituzioni, che prima era troppo corto.

- **Nelle tabelle ora si può anche recuperare.** In un CSV o in un elenco
  del personale i segnaposto stanno direttamente uno accanto all'altro,
  separati solo da un punto e virgola. Finora il programma non poteva
  stabilire lì quale valore fosse stato in quale punto, e rifiutava – con
  `[NAME]` funzionava, con `[GEBURTSDATUM]` e `[TELEFON]` no. Ora scompone
  la riga in corrispondenza di tutti i segnaposto. Se un punto resta
  davvero ambiguo, continua a rifiutare: un valore riscritto in modo
  sbagliato sarebbe peggiore di un'informazione mancante.

- **E ora il rifiuto è visibile.** Stava in grigio smorzato sul bordo
  inferiore della finestra, e la frase era così lunga da venire troncata –
  sembrava che non succedesse nulla. Le frasi sono accorciate, e la riga
  si illumina per qualche secondo nel colore di avviso.

- **Un recupero ora resta valido anche dopo l'intervento successivo.** Chi
  nell'anonimizzazione recuperava più punti e dopo sostituiva qualcos'altro,
  ritrovava tutti i punti recuperati di nuovo sostituiti e doveva
  ricominciare da capo. La causa era l'assegnazione: manteneva il valore, e
  l'allineamento automatico per segnaposto uniformi lo recuperava alla
  scrittura successiva. Ora vale: ciò che recuperate resta recuperato –
  altri punti dello stesso valore non ne sono toccati.

- **Nei file di testo, Word, Excel ed e-mail ora basta davvero un clic nel
  segnaposto.** Il messaggio era già nella versione precedente, ma il
  pulsante „Recupera selezione" restava bloccato finché non era selezionato
  esattamente qualcosa – non si arrivava quindi nemmeno al percorso che
  avrebbe impostato la selezione stessa.

### Corretto

- **Il registro di controllo non svela più il nome del file.** Tiene i
  file volutamente come valore di hash invece che in chiaro, perché un nome
  di file rivela cliente e oggetto della controversia. Questo valore di
  hash si poteva però confermare per tentativi – un percorso non è un
  numero casuale. Ora nel calcolo entra un valore casuale di questa
  installazione: contare e distinguere nel registro continuano a
  funzionare, il ricalcolo dall'esterno non più.

## 0.10.31-alpha.20260819 – 19 agosto 2026

### Migliorato

- **Anche nei file di testo e tabelle il segnaposto si illumina di rosso al
  passaggio del mouse.** Finora l'anteprima rossa esisteva solo su una
  pagina PDF. Ora entrambe le visualizzazioni mostrano lo stesso: ciò che
  è rosso viene colpito dalla mossa successiva – e un clic dentro basta per
  recuperare.

- **Un clic su una parola basta – il rettangolo lo imposta l'editor
  stesso.** Nella finestra di correzione finora bisognava tracciare un
  rettangolo su ogni punto. Ora basta un clic: la cornice si posiziona
  intorno alla parola e resta afferrabile, quindi si può ancora allargare
  o spostare. Passando con il mouse, la parola si illumina già di rosso, in
  modo da vedere prima cosa colpirebbe il clic. Dove non c'è una parola, si
  traccia un rettangolo come prima.

- **Non serve più mirare con precisione con il rettangolo.** Chi traccia
  un rettangolo su un segnaposto o un oscuramento intende sempre l'intero
  punto – mai la metà. La cornice cresce quindi da sola fino a coprire
  tutto ciò che tocca: l'intero segnaposto, l'intera barra o, su un foglio
  scansionato, l'intera area oscurata. Non diventa mai più piccola del
  rettangolo tracciato.

- **Ora si oscura parola per parola.** Una cornice sopra metà di una
  parola finora oscurava anche solo metà – e un nome oscurato a metà è
  ancora un nome. Le parole toccate cadono ora per intero; il vicino resta
  intatto.

- **Nel testo e nelle tabelle basta un clic nel segnaposto.** „Recupera
  selezione" finora richiedeva di selezionare esattamente il segnaposto
  comprese le parentesi quadre. Ora basta posizionare il cursore dentro; la
  selezione salta visibilmente sull'intero segnaposto.

- **Il Belgio si è aggiunto come paese.** Selezionabile nelle
  impostazioni; vengono quindi riconosciuti numeri di telefono belgi, il
  numero di registro nazionale (con cifra di controllo), il numero
  BTW/impresa (con cifra di controllo), indirizzi in entrambe le lingue
  ufficiali e il codice postale con località. Finora i numeri di telefono
  belgi restavano perché il paese non era affatto nel catalogo.

- **Il canale di aggiornamento indica ora quanto presto si ricevono le
  novità – non quanto sono avanzate.** Chi era su „Versione di prova" non
  riceveva affatto un'offerta per una nuova anteprima o una nuova versione
  stabile e doveva cambiare canale manualmente per venirne a conoscenza.
  Ora viene offerto anche tutto ciò che è più affidabile: versione di
  prova prende versioni di prova, anteprime e versioni stabili, anteprima
  prende anteprime e stabili. Mai il contrario – su anteprima non viene
  offerta nessuna versione di prova, anche se è più recente.

- **Nella finestra delle impostazioni le righe stanno di nuovo più
  distanziate.** Le quattro pagine usavano spaziature proprie invece della
  griglia valida nel resto del programma; in particolare nella pagina
  „Riconoscimento" le caselle di controllo stavano quindi visibilmente
  troppo vicine.

### Corretto

- **I moduli PDF compilati non appaiono più vuoti nella modifica
  manuale.** Per questo Maskuro rende statiche esclusivamente pagine dalla
  copia di lavoro volatile: i valori inseriti diventano visibili e si
  possono davvero oscurare; i campi modulo leggibili non restano nascosti
  nel file. L'originale resta interattivo e invariato. Vale ora anche per
  i moduli XFA dinamici: un PDFium compatibile con XFA costruisce
  dapprima valori e interruzioni di pagina, poi nasce un nuovo PDF
  composto esclusivamente da pagine immagine statiche. Se la costruzione
  XFA fallisce, il file viene respinto in modo sicuro invece di essere
  aperto apparentemente vuoto.

- **„Annulla" agisce ora anche durante il riconoscimento più preciso.**
  Finora il pulsante si bloccava al clic, ma l'esecuzione continuava a
  calcolare fino all'ultimo blocco – per un file lungo sono minuti senza
  via d'uscita, e il pulsante nel frattempo sembrava aver funzionato. Ora
  l'esecuzione termina al blocco successivo.

- **Nei file CSV i nomi vengono ora trovati anche quando non c'è uno
  spazio prima di essi.** In `P-1000;Brunnthaler, Elisabeth` il numero di
  matricola aderisce al nome oltre il punto e virgola, e per il
  riconoscimento era un'unica parola senza nome al suo interno – negli
  elenchi del personale restava quindi, a seconda della riga, l'intero
  nome. Numeri di telefono, formule e il numero di colonne del file non
  ne sono toccati.

- **Un nome il cui nome e cognome portano entrambi un trattino viene ora
  riconosciuto.** „Marie-Luise Habsburg-Ott" restava in mezzo alla frase,
  mentre „Dragan Mitrović" nella stessa frase veniva trovato – proprio la
  combinazione di due metà accoppiate sfuggiva al modello linguistico.
  Parole composte accoppiate come „Nord-Süd-Verbindung" o
  „Software-Entwickler" non ne sono toccate.

## 0.10.30-beta.1 – 18 agosto 2026

### Migliorato

- **La dimensione del carattere della visualizzazione testo è ora
  impostabile in modo visibile.** Il cursore in basso a destra, che finora
  ingrandiva solo nell'anteprima pagina, imposta nella finestra di
  correzione per i file di testo e Office la dimensione del carattere
  (50–300 %) – così come „Ingrandisci"/„Riduci" nel menu Visualizza.
  Ctrl+rotellina del mouse funzionava già sempre, ma lo sapeva solo chi
  l'aveva provato; ora cursore, indicazione e rotellina agiscono insieme.

- **Nell'aspetto scuro c'è ora un foglio bianco su una superficie di
  lavoro scura.** Finora era il contrario: intorno al foglio restava una
  superficie chiara, e il testo stesso era chiaro su scuro. Ora il foglio
  resta bianco carta con scrittura nera in entrambi gli aspetti – come una
  pagina PDF, che nemmeno in modalità scura diventa scura – e la
  superficie intorno è scura.

### Corretto

- **Dopo un oscuramento in mezzo a una frase, il resto della frase non va
  più perso.** Chi nella finestra di correzione ripeteva tre volte lo
  stesso punto – sostituire, oscurare, poi „Recupera originale" –, si
  ritrovava cancellato l'inizio della frase: da „Per domande si prega di
  rivolgersi alla contabilità." diventava „si prega di rivolgersi alla
  contabilità.", senza avviso. Era interessato ogni punto in cui era già
  stato rimosso qualcosa in mezzo a una riga.

- **Un errore all'avvio non trascina più con sé la chiusura.** Se la
  costruzione della finestra principale si interrompeva, dopo si bloccava
  anche la chiusura tramite l'icona nella barra delle applicazioni – e
  questo secondo errore nascondeva nel rapporto di errore la causa reale.
  Ora il programma si chiude in modo pulito anche da una finestra
  costruita solo a metà, e le impostazioni salvate restano intatte.

- **„Prima/Dopo" non salta più all'inizio del documento.** Chi nella
  finestra di correzione aveva scorso verso il basso e passava
  all'originale per il confronto, finiva di nuovo tutto in cima – e doveva
  ritrovare il punto a mano. La visualizzazione ora resta sulla stessa
  riga, in entrambe le direzioni.

- **Nell'oscuramento, sulle righe giustificate restava l'ultima
  lettera.** Quando un comando di testo disegna più glifi di quanti la
  libreria di lettura segnali come caratteri – nel testo giustificato
  spesso ingoia uno spazio –, l'assegnazione slittava di uno, e da „Dr.
  Michael Handler aus Willendorf" diventava „[NAME] r aus f": due
  lettere rimaste in mezzo alla frase bonificata (trovato in un vero
  verbale di consiglio). L'assegnazione viene ora riverificata sul testo
  letterale del comando stesso, dove questo è leggibile – lì non si tira
  più a indovinare.

- **„Lerchenfelder Gürtel 43/12" veniva rimosso solo a metà.** I modelli
  degli indirizzi non conoscevano né Gürtel, Kai, Lände, Zeile, Markt né
  Graben come parola base di via, e il numero civico non poteva portare
  parti con barra (43/12, casa/porta) – il numero restava accanto al
  segnaposto. Entrambi sono stati aggiunti; gli indirizzi viennesi e
  salisburghesi ora cadono per intero.

- **Le pagine web salvate restano funzionanti dopo la bonifica.** Gli
  indirizzi che il lazy-loading deposita in attributi data
  (`data-lazy-src`, `data-lazy-srcset`) venivano sostituiti come
  riferimenti – su una vera pagina comunale sedici pezzi – e le immagini
  della pagina dopo non si caricavano più. Gli indirizzi web ora restano
  lì, come anche in `src` e `href`; nomi, indirizzi email e numeri di
  telefono negli attributi data continuano a essere sostituiti.

- **I documenti giapponesi e coreani venivano trattati come cinese.** Il
  riconoscimento della lingua metteva tutte e tre le scritture nello
  stesso calderone, non trovava parole funzionali nel testo giapponese
  (senza spazi) e coreano (con particelle attaccate) – e prendeva quindi
  semplicemente la prima lingua CJK del catalogo. Un verbale di consiglio
  giapponese e un verbale di seduta coreano venivano così letti con il
  modello cinese. Ora decide la grafia stessa: kana significa giapponese,
  hangul significa coreano.

- **Altri errori dal test sul campo in altre dieci lingue:** cariche come
  „Primar", „Gradonačelnik", „Ordfører", „Başkanı" o „Δήμαρχος" non
  valgono più come nomi di persona; le etichette di campo turche („Adı",
  „Soyadı") e le parole di conversazione greche („Ωραία", „Βεβαίως") non
  cadono più; numeri di delibera e paragrafo con data („323/25-6-2008",
  „27 30.09.2024") non sono più numeri di telefono; e frammenti di frase
  con punto („10.An", „T.U.EE", „…pa") non vengono più sostituiti come
  indirizzi web.

### Nuovo

- **Rapporti di controllo automatici a richiesta.** Una spunta nelle
  impostazioni (pagina „Programma") deposita da sé, dopo ogni bonifica, un
  PDF di rapporto di controllo – con timestamp nel nome, in una cartella
  propria, mai accanto al risultato. Un foglio non si può generare in un
  secondo momento; chi ne ha bisogno per la pratica lo ha così sempre.
  Predefinito, il deposito è disattivato.

- **Il registro di controllo si può ora attivare nel programma.** Alla
  lettura di una licenza aziendale, Maskuro chiede una volta se il
  registro deve essere tenuto – una prova vale solo se funziona fin
  dall'inizio. C'è per questo un interruttore nelle impostazioni (pagina
  „Programma", visibile con licenza aziendale o nel periodo di prova); il
  file di direttive della gestione resta valido e può imporre il valore
  come prima. Una riga di registro propria „attivato" registra da quando
  viene tenuto – così anche l'inizio della registrazione è documentato e
  firmato. Predefinito, il registro resta disattivato.

- **La sezione delle cifre mostra cosa ha fatto il livello IA.** Una nuova
  riga indica quanti rilevamenti incerti il modello ha valutato,
  mantenuto e scartato, e quanti ne ha trovati in più – finora il suo
  lavoro era invisibile se non si cliccava ogni valore nell'editor di
  correzione. Solo numeri, mai valori o motivazioni; senza lavoro IA la
  riga non compare.

- **Il recupero funziona ora anche nelle e-mail e nelle pagine HTML.** In
  `.eml`, `.msg` e pagine web salvate, finora non si poteva annullare un
  segnaposto – l'applicazione lo diceva onestamente, ma proprio l'e-mail
  è il formato con più dati personali. Ora il recupero funziona lì
  allo stesso modo: dal pannello dei rilevamenti, con selezione marcata e
  anche per segnaposto anonimizzati. Il ramo HTML invisibile di un'e-mail
  (ciò che Outlook mostra davvero) viene trascinato con esso, in modo che
  visualizzazione e messaggio dicano la stessa cosa.

- **Il pannello dei rilevamenti recupera anche valori anonimizzati – per
  valore.** „Annulla sostituzione" era finora bloccato per i file
  anonimizzati, perché „[NAME]" vale per tutti i nomi insieme. Ora il
  recupero consulta l'originale per stabilire quale punto appartiene a
  quale valore – nel PDF alle coordinate del punto di rilevamento, nella
  visualizzazione testo tramite confronto con l'originale – e recupera
  esattamente i punti del valore scelto. Le righe degli altri valori
  restano.

- **Anche i segnaposto anonimizzati si possono recuperare
  singolarmente.** Nell'anonimizzazione tutti i dati di un tipo si
  chiamano uguale – „[NAME]" vale per ogni persona, e finora perciò
  valeva: il recupero singolo non funziona. Ora si consulta l'originale,
  che comunque si trova accanto al risultato: nella visualizzazione testo
  si seleziona il segnaposto e si sceglie „Recupera selezione" – torna
  esattamente quel punto con esattamente il suo valore. Se il valore non
  si può leggere dall'originale in modo inequivocabile, l'applicazione lo
  dice, invece di indovinare. Un file di assegnazione continua a non
  essere creato.

- **La finestra di correzione si apre da sola dopo la bonifica.** Nessuno
  strumento trova tutto – perciò lo sguardo di controllo sul risultato fa
  parte del caso normale, non è un clic in più. Chi non lo desidera lo
  disattiva nelle impostazioni sotto „Riconoscimento" („Mostra il
  risultato dopo nella finestra di correzione").

### Migliorato

- **La scelta del paese è ora impostata su „automatica".** Finora valeva
  di fabbrica l'area linguistica dell'interfaccia – su un computer tedesco
  venivano quindi bonificati anche documenti olandesi o francesi solo con
  i riconoscitori DACH, e un indirizzo come „Universiteitslaan 1"
  restava (trovato in veri verbali di consiglio pubblici). Ora la scelta
  del paese segue la lingua del documento; chi ha fatto una scelta fissa
  nelle impostazioni la mantiene.

- **Meno annerimenti errati.** Una serie di errori, misurati sul corpus di
  controllo e su veri verbali di seduta in sei lingue, viene meno: nomi di
  aziende con forma giuridica („Musterfirma GmbH") non valgono più come
  persona o luogo, ma come organizzazione; formule di saluto e formule di
  cortesia nude („Saygılarımızla", „Buenas tardes", un „Frau" isolato) non
  sono più nomi; cariche („Bürgermeister", „Sindaco", „Alcalde") restano;
  numeri di legge e delibera („39/2015") e importi con punto delle
  migliaia („330.000") non sono più numeri di telefono; inizi di frase
  come „Envíame" o „Estarei" non cadono più come nome; un rilevamento
  attraverso una riga vuota non conta più come nome. Il numero di fattura
  di una fattura resta come dato del documento – numero cliente e numero
  di pratica continuano a cadere.

- **Prima di caricare il modello IA c'è ora scritto a cosa serve.** La
  finestra di dialogo di scaricamento nomina i compiti del modello –
  valutare rilevamenti al limite, trovare nomi aggiuntivi, proporre regole
  e profili – e dice apertamente che non è un assistente di chat. Le FAQ
  rispondono alla stessa domanda in dettaglio („Cosa può fare il livello
  IA – e cosa no?"), in tutte le versioni linguistiche.

### Corretto

- **I PDF di rapporto di controllo dalla riga di comando ora si possono
  cercare.** Sotto Windows il percorso PDF senza interfaccia partiva senza
  un solo carattere tipografico – ogni carattere veniva disegnato come
  riquadro sostitutivo, e il foglio non portava testo leggibile: chi
  voleva cercare o copiare qualcosa non trovava nulla. Ora il rapporto in
  quel caso carica i caratteri del sistema; il testo è incorporato e
  leggibile. I rapporti dalla finestra non erano mai stati interessati.

- **„Recupera originale" su più righe di una scansione lasciava strisce
  nere tra le righe.** Su una pagina convertita in immagine, la cornice
  ripuliva solo le fasce di riga stesse; i resti dell'oscuramento
  precedente restavano negli spazi intermedi. Ora la cornice tracciata si
  suddivide completamente sulle righe.

- **Una seconda cornice sopra un segnaposto lasciava un resto rosso.** Il
  segnaposto è quasi sempre più largo della parola che rappresenta; chi
  dopo oscurava sullo stesso punto colpiva solo il suo inizio – restava un
  frammento come „RIFF_1]" in mezzo alla frase, e il recupero inseriva poi
  il testo originale al suo posto invece che al posto della parola. Un
  segnaposto tagliato ora cade sempre per intero.

- **Su una pagina ruotata, l'oscuramento sopra un segnaposto cancellava
  una frase non coinvolta.** Il segnaposto disegnato successivamente
  veniva confuso, alla rimozione, con il testo precedente: esso stesso
  restava, compariva l'avviso „è ancora presente nel documento" – e in un
  altro punto della pagina spariva senza sostituto una frase che non
  aveva nulla a che fare con la cornice. Un segnaposto viene ora
  ritrovato tramite il suo testo letterale; la catena „sostituire,
  oscurare, recuperare" funziona così anche su pagine acquisite di
  traverso.

- **Il manuale consigliava ancora in dieci lingue `python3-tk`.** Nella
  risoluzione dei problemi c'era scritto che sotto Linux potesse mancare
  tkinter – un consiglio dei tempi prima dell'interfaccia Qt, che non
  aiuta più nessuno. Ora in tutte le versioni c'è lo stesso paragrafo del
  tedesco: mancano le librerie di sistema di cui Qt ha bisogno per la
  visualizzazione.

- **Il capitolo sulla licenza del manuale era su vecchio stato in tutte e
  sedici le traduzioni.** In dieci lingue si leggeva ancora che Windows
  Server necessitasse di una licenza aziendale con accesso server e che
  lì non esistesse periodo di prova né livello gratuito – da quando un
  posto conta una persona e non una macchina, entrambe le cose sono
  sbagliate. Mancavano inoltre ovunque le informazioni su quando un posto
  occupato si libera di nuovo, che la licenza si conferma regolarmente e
  cosa viene trasmesso in tal caso, e l'attivazione senza internet era
  solo in forma abbreviata, senza i tre passaggi e senza l'avviso che il
  computer dopo lavora un anno senza connessione.

- **Sette paragrafi sulla correzione mancavano in dieci lingue.** Chi
  leggeva la guida in danese, finlandese, francese, italiano, olandese,
  norvegese, polacco, portoghese, svedese o spagnolo non trovava né
  l'anteprima pagina per i file Office né „Oscura a mano" né l'intera
  sezione su come il programma impara da una correzione – compresa la
  tabella con i tre livelli di ampiezza. In „Cosa viene riconosciuto"
  mancava nelle stesse dieci versioni il percorso tramite l'etichetta nel
  documento.

- **Con una licenza letta, il programma non si avviava più.** Invece
  della finestra compariva „Impossibile avviare il programma" – e questo
  con qualsiasi licenza. La causa era la riga nella visualizzazione della
  licenza che avvisa poco prima della scadenza del periodo di prova;
  accedeva a qualcosa che lì non era disponibile. Senza licenza – nel
  periodo di prova e nel livello gratuito – l'errore non si presentava,
  per questo è emerso solo ora.

- **Nel modulo restano i nomi dei campi.** „Data di nascita" e
  „Indirizzo" sparivano insieme al loro valore: il segnaposto stava
  piccolo e rosso al posto del *nome del campo*, il campo sottostante
  restava vuoto. Il nome del campo non fa parte dei dati – ora resta, e
  il segnaposto sta dove stava il valore.

- **I titoli di documento in lingua straniera non vengono più scambiati
  per nomi.** Sopra un modulo italiano c'era scritto „FATTURA", sopra uno
  spagnolo „PERMISO PARENTAL" – entrambi venivano sostituiti. L'elenco
  delle parole di documento conosceva solo gli equivalenti tedeschi.

- **Da una fattura non sparisce più nessuna voce.** „Sovrapprezzo
  materiale  1  84,00" veniva scambiato per un indirizzo e sostituito con
  un segnaposto di luogo – al documento mancava dopo una riga. Una riga
  che termina con un importo è una voce e non un indirizzo; gli indirizzi
  reali („Hauptstraße 1  120,00") restano invariati.

### Modificato

- **„Monitora cartella …" e la riga di comando non ci sono più per
  ora.** Entrambi i percorsi sono costruiti e funzionano, ma nessuno dei
  due è stato testato sul campo: il monitoraggio cartella non ha mai
  visto un test su Windows, e la riga di comando dà a uno script due
  dozzine di interruttori che non sono mai girati presso nessun utente.
  Ciò che modifica documenti senza sorveglianza non deve farlo senza
  controllo – perciò sono stati ritirati finché il test non sia stato
  recuperato. La voce di menu manca, e `--wache` non è più in
  `maskuro --help`.

- **Resta aperto ciò che legge soltanto e ciò che comunque serve.** La
  scansione (`--suchlauf`) e il controllo (`--nachpruefen`) continuano a
  funzionare sulla riga di comando – non modificano alcun file. Così
  anche l'avvio tramite Esplora risorse, il menu contestuale, gli appunti
  e la finestra; qui non cambia nulla.

- **„Acquisisci da scanner" ha ora un capitolo proprio nel manuale.**
  Prima si trovava alla fine di „Monitora cartella". Sul Mac il consiglio
  lì era di far monitorare una cartella; ora è di trascinare le pagine
  acquisite nella finestra.

### Corretto

- **„Recupera originale" su più righe distruggeva la struttura.** Una
  cornice sopra un segnaposto, un titolo di lavoro invariato e una
  seconda sostituzione inseriva l'intera area di nuovo come **un'unica**
  riga – da tre righe ne nasceva una, e ciò che non ci stava più
  diventava una barra. Ora ogni riga viene recuperata a sé.

- **E il testo invariato resta intatto.** Chi traccia su una sostituzione
  *e* testo normale ottiene indietro solo la sostituzione; il resto non
  viene toccato. Anche l'ultimo resto del vecchio segnaposto sparisce in
  questo caso – prima la sua parentesi di chiusura restava in mezzo alla
  frase.

- **Nella sostituzione non restano più resti del vecchio testo.** In un
  titolo in grassetto compariva dopo „1. R[BEGRIFF_2]ige [BEGRIFF_1] …
  che" – il segnaposto c'era, ma accanto sillabe dell'originale. Ora viene
  ripulita l'area che si delimita, non solo le caselle delle parole al
  suo interno.

- **Un segnaposto anonimo non viene più recuperato.** Nell'anonimizzazione
  ogni nome porta lo stesso `[NAME]`. Il recupero prendeva la prima voce
  disponibile e la scriveva in ogni punto di rilevamento – da „Georg
  Aigner" diventava „Anna Musterfrau", quindi un nome sbagliato nel
  documento. Ora c'è scritto che non si può più dire quale dato fosse
  inteso; il documento resta intatto.

### Nuovo

- **„Recupera originale" agisce ora anche su una pagina rasterizzata.** Se
  una pagina era stata convertita in immagine, finora arrivava un
  rifiuto: il testo recuperato finirebbe sotto l'immagine della pagina.
  Ora il punto nell'immagine viene ripulito e il testo scritto sopra –
  come un segnaposto su una scansione. Il contenuto proviene in questo
  caso dal file originale, che non è rasterizzato.

- **„Recupera selezione" è ora un pulsante proprio.** Funzionava già
  prima, ma solo selezionando per caso un segnaposto e premendo „Sostituisci
  selezione" – una funzione che si trova solo per caso non esiste per
  l'utente.

### Modificato

- **In testo puro, CSV e messaggi Outlook non esiste più „Oscura
  selezione".** Questi formati non possono portare una barra; il pulsante
  lì impostava un segnaposto e lo diceva anche – ma un pulsante che fa
  qualcosa di diverso da ciò che dice il suo nome non ci sta.

- **Uno strumento dice ora quando in quel punto non ha nulla da fare.** Un
  segnaposto non si può sostituire una seconda volta, sopra un
  oscuramento non viene impostato nessun segnaposto, e dove sta già
  l'originale non c'è nulla da recuperare. Finora queste azioni facevano
  qualcosa che sembrava avere effetto, ma non ne aveva.

## 0.10.29-alpha.20260817 – 17 agosto 2026

### Corretto

- **Nella finestra di correzione ora agisce ogni cornice tracciata.** Chi
  lavorava due volte nello stesso punto – prima sostituire, poi
  oscurare, poi recuperare l'originale –, vedeva la seconda e la terza
  mossa svanire senza alcun messaggio: la cornice ancora afferrabile della
  mossa precedente la intercettava. Lo stesso al cambio di strumento, dove
  addirittura il vecchio strumento continuava ad agire silenziosamente.
- **Una cornice tracciata troppo stretta dice che è troppo stretta.**
  Finora l'anteprima illuminava di rosso una parola, e al rilascio non
  succedeva nulla senza messaggio.

- **I messaggi Outlook finalmente si possono correggere.** Un `.msg`
  mostrava nella finestra di correzione „Questo formato non si può
  visualizzare qui" – era l'unico formato supportato senza alcun modo di
  intervenire a mano. Ora mittente, destinatario, oggetto e testo del
  messaggio compaiono con nome nella visualizzazione e si possono
  selezionare e sostituire come in qualsiasi altro formato di testo.

- **„Sostituisci selezione" in un'e-mail resta sulla selezione.** Chi
  selezionava un nome nel testo scorrevole perdeva con esso anche
  mittente e destinatario dalle intestazioni, e il messaggio nominava un
  segnaposto diverso da quello presente nel testo. Ora il valore
  selezionato viene sostituito ovunque – anche nel mittente, se si trova
  lì – e nient'altro viene toccato.

- **Una cornice su più righe non distrugge più il testo.** Finora nasceva
  un unico segnaposto in un punto: dalla parola tagliata restava
  attaccato un resto, e dalla seconda riga il testo spariva senza
  sostituto – nessun segnaposto, nessuna barra, solo un vuoto. Ora ogni
  riga riceve il proprio segnaposto con il valore che vi si trovava
  davvero.

- **„Recupera originale" agisce ora anche dopo un oscuramento.** La
  finestra segnalava successo, e il testo non tornava mai: la barra nera
  contava come ostacolo, così per il testo recuperato non c'era più
  spazio. Ora la barra cede, e il testo recuperato compare nero come
  testo normale – non rosso come un segnaposto.

- **„Recupera originale" su un punto non toccato ora non fa più nulla.**
  Chi tracciava la cornice su testo su cui non era stato affatto
  modificato nulla, si ritrovava il testo rimosso e reinserito più
  piccolo e spostato – veniva segnalato successo. Ora c'è scritto che non
  c'è nulla da recuperare.

### Nuovo

- **Si può oscurare anche in Word, Excel, PowerPoint, OpenDocument e
  testo.** Finora lì esisteva solo „Sostituisci selezione"; una barra era
  riservata alla visualizzazione PDF, senza che ci fosse un motivo per
  questo. Dove una barra non è rappresentabile – in testo puro e in un
  messaggio Outlook – il valore viene sostituito come prima con un
  segnaposto, e questo è indicato anche nel messaggio.

- **Selezionare un segnaposto lo recupera.** Nella visualizzazione testo
  (Word, Excel, PowerPoint, OpenDocument, testo) ora basta selezionare il
  segnaposto e premere „Sostituisci selezione": torna il valore
  originale. Finora la finestra rimandava per questo al pannello dei
  rilevamenti.

- **I relatori in un verbale di riunione vengono riconosciuti anche
  quando il loro nome è al contempo una parola comune.** „Gruber: Il
  collaudo avviene la prossima settimana." veniva sostituito, „Bauer: Sono
  d'accordo." restava – il cognome sembra al riconoscimento un
  sostantivo. Righe di promemoria della stessa forma restano intatte: da
  „Attenzione: l'impianto va spento." non nasce nessun nome.

- **„Stai usando la versione più recente" veniva detto anche quando non
  si poteva affatto verificare.** Se il server di aggiornamento
  respingeva la richiesta – perché dallo stesso indirizzo internet
  arrivavano troppe richieste o perché era lui stesso momentaneamente
  guasto –, il programma restava fermo sulla sua vecchia versione
  affermando che fosse la più recente. Esattamente questo è successo il
  17 agosto su un Mac: 0.10.25 restava, mentre 0.10.28 era pronta da ore.

  Ora la finestra dice cosa succede, indica l'orario del prossimo
  controllo – e segnala espressamente che **non** è certo se la propria
  versione sia la più recente.

  Spesso non dipende dal proprio computer: con molte connessioni,
  numerosi clienti condividono lo stesso indirizzo internet, e il server
  li conta insieme. Per questo Maskuro in questo caso cerca l'elenco delle
  versioni tramite un **secondo percorso** e trova comunque quasi sempre
  nuove versioni. Se il rifiuto persiste, il server viene lasciato in pace
  fino all'orario indicato – anche se si preme di nuovo il pulsante;
  insistere prolunga solo il blocco.

- **Le indicazioni di quantità non vengono più scambiate per nomi di
  luogo.** In un contratto di servizio „Settimana di quattro giorni"
  spariva dietro un segnaposto di luogo – in mezzo all'oggetto del
  contratto. Tali combinazioni di parole con numero e trattino
  („Piano in tre punti", „Servizio 24 ore") ora restano. Gli indirizzi
  ne sono esclusi: una „Via dei Due Fratelli" continua a essere
  sostituita.

## 0.10.28-alpha.20260817 – 17 agosto 2026

### Modificato

- **I posti licenza vengono ora davvero contati.** Finora nessuna
  postazione di lavoro si registrava mai presso il servizio licenze – una
  licenza a dieci posti girava su un numero qualsiasi di computer, senza
  che nessuno lo sapesse. Nuovo: il computer che avvia il programma occupa
  un posto; un posto si libera da solo dopo **sette giorni senza
  avvio**, così che un dispositivo rotto o un dipendente uscito non blocca
  nulla in modo permanente.

  Un piccolo sforamento viene **solo segnalato e non bloccato**: fino al
  dieci per cento oltre il numero acquistato tutti continuano a lavorare
  – il nuovo laptop accanto al vecchio ancora registrato non deve
  diventare un caso per l'assistenza. Chi si aggiunge oltre questo limite
  ricade sul livello gratuito e ne viene informato; i computer che
  c'erano per primi non se ne accorgono.

- **Una licenza acquistata si conferma regolarmente.** Se ciò non riesce
  per **30 giorni**, vale per tutto quel tempo di nuovo il livello
  gratuito, finché non riesce di nuovo. Non viene disattivato nulla, e a
  partire da una settimana prima l'avviso compare nella finestra. Non
  appena il computer torna in internet, la cosa si risolve da sola. Il
  periodo di prova e il livello gratuito continuano a non segnalare
  affatto nulla – chi non compra mai, non telefona mai.

- **„Attiva senza internet" finalmente funziona.** L'attivazione veniva
  finora sì verificata e depositata, ma dopo non era più letta da
  nessuno – non cambiava nulla nei diritti. Ora è la via d'uscita per
  computer senza accesso alla rete: vale **un anno**, dopo di che si
  ottiene una nuova attivazione con un codice di richiesta appena
  generato. Un dispositivo con internet serve per questo una volta
  all'anno – il computer stesso resta permanentemente offline.

- **L'attivazione ora funziona anche dall'account cliente** – sotto „Le
  mie licenze" sul sito web. Lì c'è scritto inoltre quali computer sono
  collegati alla vostra licenza e quando i loro posti si liberano di
  nuovo; finora non si vedeva da nessuna parte. La pagina senza accesso
  resta per chi non ha accesso allo shop – richiede in più l'indirizzo
  email dell'ordine, in modo che la sola chiave di licenza non basti.

- **E nella finestra c'è ora scritto dove mettere il codice di
  richiesta.** Il percorso cartaceo diceva „inserire su un dispositivo con
  connessione internet" e non nominava nessun indirizzo; la pagina di
  attivazione esiste da tempo, ma non era collegata da nessuna parte. Ora
  nella finestra di dialogo, nel manuale e nelle FAQ c'è scritto
  **maskuro.com/lizenz-freischalten** – e sul sito web sotto la chiave di
  licenza.

- **Il pulsante „Attiva senza internet …" resta visibile**, anche quando
  la licenza al momento non è valida. Prima spariva insieme a essa – cioè
  proprio quando serve.

- **„Tutti i posti occupati" dice ora la verità.** L'avviso terminava con
  „Il programma continua a funzionare invariato"; ciò non è più vero se
  non è stato assegnato alcun posto. Ora c'è scritto che fino a nuovo
  avviso vale il livello gratuito.

### Nuovo

- **All'attivazione della bonifica degli appunti c'è ora scritto che va
  controllato.** Il messaggio da allora riporta la stessa frase presente
  anche nel risultato di un file: Maskuro non riconosce in ogni caso
  tutti i dati personali.

  Qui pesa più che altrove. Con un file si vede il risultato prima di
  trasmetterlo. Con gli appunti no – si copia, si incolla, e il testo
  bonificato è già nella finestra di posta. Il messaggio dice quindi
  espressamente di controllare il testo **incollato**.

  Compare all'attivazione, non a ogni operazione di copia: ciò che
  apparirebbe cinquanta volte al giorno, dopo la terza volta non lo legge
  più nessuno.

- **„Copia tutti" sotto l'elenco – e „Rimuovi tutti" si sposta.** Il
  nuovo pulsante mette tutti i risultati completati in una volta negli
  appunti, per allegarli a un'e-mail o incollarli in un altro programma.
  Finora funzionava solo tramite il menu e anche lì solo per le righe
  **selezionate** – chi intendeva tutte doveva prima premere Ctrl+A.

  In questo la riga dei pulsanti è riordinata: a sinistra sta ciò che
  aggiunge qualcosa, a destra, dopo uno spazio, ciò che toglie qualcosa.
  „Rimuovi tutti" si trovava finora direttamente accanto ad „Aggiungi …",
  e un errore costava l'intero elenco. La stessa regola vale già dal
  13 agosto per ogni riga completata.

- **Le postazioni senza internet ricevono ora i loro modelli linguistici
  dall'azienda.** Bonificare lì funzionava già sempre senza connessione –
  scaricare un modello linguistico no, e un modello pesa alcune centinaia
  di megabyte.

  L'amministrazione raccoglie i file una volta su un computer con
  connessione e li deposita su una condivisione, nel rollout o su una
  chiavetta. Il percorso viene inserito centralmente (campo
  `modellquelle` in `vorgaben.json` o la variabile d'ambiente
  `MASKURO_MODELLQUELLE`). Da quel momento ogni scaricamento successivo si
  serve prima lì – modelli linguistici, il dizionario giapponese e il
  livello Alto – e va in rete solo se manca un file.

  I checksum restano validi invariati. Una condivisione file in azienda è
  spesso più facile da descrivere di una release in rete; non deve
  diventare la via più comoda verso un modello manomesso.

  Come nasce un tale deposito e come funzionano licenza e attivazione
  senza internet è descritto in `OFFLINE.md`.

- **„Recupera originale" – una cornice recupera ciò che è stato rimosso
  in eccesso.** Nella finestra di correzione c'è un nuovo strumento:
  tracciare una cornice sul punto, e il testo torna a essere quello che
  era nell'originale.

  Questo chiude la lacuna che il pannello dei rilevamenti lasciava
  aperta. Lì una sostituzione si poteva annullare solo se il suo
  segnaposto era univoco – quindi non nell'anonimizzazione, dove
  „[NAME]" vale per ogni dato di quel tipo, e per nulla nei punti
  oscurati, dove non resta alcun segnaposto. Proprio lì si accumulano gli
  errori: „Utente", „Numero di inventario", „Firma" vengono spesso
  scambiati per nomi.

  La cornice non ha bisogno del segnaposto: il **punto** viene dal
  rettangolo, il **contenuto** dal file originale – lo stesso che mostra
  il commutatore prima/dopo. Anonimizzato o pseudonimizzato non conta più
  nulla.

  Il testo recuperato compare nero, non rosso: è di nuovo testo in chiaro
  e non un segnaposto. Una voce sparisce dall'elenco dei rilevamenti solo
  quando il suo segnaposto non compare **più da nessuna parte** nel
  documento – se lo stesso valore è stato sostituito in più punti, resta
  per i restanti.

  Su una pagina convertita in immagine, lo strumento rifiuta e spiega
  perché: il testo recuperato finirebbe sotto l'immagine della pagina e
  non sarebbe visibile.

### Corretto

- **Chiudendo „Dettagli" e „Cifre" restavano resti di immagine sullo
  schermo.** Chiusi, una parte del contenuto scivolava sotto il bordo
  inferiore della finestra e restava lì sopra lo sfondo, finché qualcos'
  altro non veniva disegnato sopra.

  Entrambe le aree hanno un'altezza minima, in modo da essere di
  dimensione utile quando aperte. Il movimento di chiusura però riduceva
  solo l'altezza massima – e sotto la sua altezza minima un'area non si
  restringe. Il contenuto restava quindi alto 200 punti, mentre la
  finestra si contraeva già a 24; la differenza stava sotto il bordo. Ora
  l'altezza minima cede per la durata del movimento e torna dopo.

- **La finestra diventava sempre più piccola aprendo e chiudendo
  ripetutamente.** All'apertura cresce al massimo fino al 92 % dell'altezza
  dello schermo; se lo spazio è scarso, cresce quindi meno del necessario.
  Alla chiusura sottraeva comunque l'importo pieno. Ora restituisce
  esattamente ciò che l'apertura è costata.

- **Un resto di un dato oscurato poteva restare visibile.** In un
  curriculum restavano leggibili nel risultato i caratteri „*30.1" da
  „*30.12.1991" – cioè giorno e inizio del mese della data di nascita. Il
  programma aveva persino notato il resto e per questo convertito la
  pagina in immagine; proprio questo peggiorava le cose, perché così il
  resto non era più ricercabile, ma restava comunque leggibile – e non
  più correggibile.

  La causa stava tra due controlli. Il più severo dei due verifica se
  nell'area di un dato rimosso resta ancora qualcosa che lì non dovrebbe
  esserci; segnala il suo riscontro come insieme di caratteri, perché
  l'ordine di lettura si sposta con la sostituzione. Il ripiego, che
  dipinge tali punti prima della conversione, cercava questo insieme di
  caratteri come testo sulla pagina – e non lo trovava mai. Non veniva
  quindi dipinto nulla. Il punto era noto per tutto il tempo e viene ora
  passato direttamente, invece di essere ricercato di nuovo.

  Era interessata ogni pagina il cui resto veniva trovato solo da questo
  controllo – indipendentemente dal tipo di file e dalla lingua.

- **Su una scansione acquisita di traverso, il riconoscimento testo non
  trovava nulla.** Chi inserisce un foglio lateralmente nell'alimentatore
  ottiene un file in cui la scrittura è ruotata di 90 gradi. Finora
  Maskuro non leggeva lì **nessun** dato – e il file dopo appariva
  innocuo: non essendo stato trovato nulla, non veniva segnalato nulla, e
  l'indirizzo restava leggibile nell'immagine. Ora il riconoscimento testo
  raddrizza da sé la pagina; nell'immagine di controllo cadono di nuovo
  tutti i dati.

  Due limiti dichiarati apertamente: un foglio **capovolto** (180 gradi)
  continua a non essere letto, e con una scansione molto scadente il
  raddrizzamento non aiuta – lì è leggibile troppo poco per determinare
  affatto l'orientamento. Ogni immagine per questo richiede circa un
  quinto di tempo in più.

### Modificato

- **„Installa automaticamente" ora significa ciò che fa.** La spunta
  nelle impostazioni prometteva più di quanto manteneva: scarica da sola
  la nuova versione e avvia l'installazione – che però procede **in modo
  visibile** e vuole essere confermata, sotto Windows con tanto di
  richiesta del controllo account utente. Chi leggeva „automaticamente"
  contava su un computer che si aggiorna da solo durante la notte, e la
  mattina si ritrovava davanti alla procedura guidata di installazione.
  La spunta si chiama ora „Scarica automaticamente gli aggiornamenti e
  avvia l'installazione", con una frase sotto che spiega cosa significa.
  Nel comportamento non cambia nulla – che Maskuro non si sostituisca
  inosservato è intenzionale e resta così.

## 0.10.27-alpha.20260817 – 17 agosto 2026

### Nuove funzioni

- **Nuovo: `--ersetzen` per il collegamento a un software di studio legale.**
  Il risultato prende il posto del file di origine, invece di essere creato
  accanto ad esso. Così il check-out e il check-in di un software di studio
  legale (“Aprire e modificare” nel fascicolo elettronico) funziona senza
  alcuna interfaccia: il software rilascia il file e lo riceve indietro
  bonificato nello stesso punto.

  **Questo interruttore scavalca il primo principio fondamentale**, e per
  questo esiste solo da riga di comando – non nella finestra – e solo se la
  Sua amministrazione lo autorizza (voce `ersetzen` nel file delle
  impostazioni predefinite). Senza autorizzazione la chiamata si interrompe
  e dice perché; creare silenziosamente un secondo file sarebbe l'errore
  peggiore, perché allora quello non modificato verrebbe reintegrato di
  nuovo.

  Viene scritto prima un file accanto; solo quando è pronto prende il posto
  dell'origine. Un'interruzione o un errore lasciano quindi l'origine
  **byte per byte invariata** e non lasciano alcun frammento. Nel registro
  di verifica la sostituzione compare come campo a sé – chi verifica deve
  sapere che la versione non bonificata non si trova più qui.

- **Il manuale spiega ora l'avviso di Windows al primo avvio.** Nuova prima
  sezione “Windows avvisa al primo avvio – cosa fare”, con due immagini e
  tre passaggi: “Ulteriori informazioni” è un piccolo collegamento, non un
  pulsante – è proprio lì che si bloccano la maggior parte delle persone –,
  poi “Esegui comunque”.

  Il fatto che vi compaia “Autore sconosciuto” è tutto il senso
  dell'avviso: i pacchetti sono attualmente distribuiti senza certificato.
  Riteniamo più corretto spiegarlo che tacerlo.

- **Il percorso di ritorno si accorge ora quando testo e assegnazione non
  si corrispondono.** Chi incollava la risposta in un'altra pratica riceveva
  finora nomi estranei nel testo giusto – nessun errore, nessun avviso, solo
  un errore silenzioso. Maskuro ora memorizza quali segnaposto ha generato
  davvero l'ultima esecuzione e segnala ognuno che non ne fa parte. Se
  nessuno di essi proviene dall'ultima esecuzione, non viene inserito nulla
  e la finestra dice perché – invece di presumere, come finora, una scadenza
  del termine.

  **Un limite resta, ed è scritto anche nel manuale:** i segnaposto sono
  numerati progressivamente per ogni esecuzione, quindi il primo nome si
  chiama in ogni documento `[NAME_1]`. Se il testo estraneo contiene solo
  segnaposto di questo tipo, lo scambio non è riconoscibile.

- **Il PDF può ora essere emesso in bianco e nero.** Un segno di spunta
  nella modalità operativa converte ogni pagina in un'immagine in bianco e
  nero – con uno strato di testo invisibile sottostante, quindi rimane
  leggibile e ricercabile. Per l'invio tramite beA e canali simili con
  limiti di dimensione rigidi: nel nostro corpus di misurazione, in media
  **il 68% più piccolo** (riga di comando: `--monochrom`).

  **Quanto rende dipende dal documento** – ed è scritto anche accanto al
  segno di spunta: materiale scansionato e ricco di immagini si riduce
  molto, un documento di testo snello senza font incorporati può persino
  diventare più grande. Provatelo su un file prima di attivarlo per un
  intero lotto.

  Il prezzo: ogni pagina viene ricalcolata – con mille pagine ciò richiede
  minuti. E le immagini perdono tutto ciò che sta tra il nero e il bianco;
  per il testo è indifferente, per una fotografia no.

- **L'elenco dei risultati nella finestra di correzione ora tiene il
  conto.** Sopra l'elenco compare “5 risultati”, e non appena si filtra,
  “1 di 5 risultati”. È la differenza tra “ho filtrato” e “sono cinque, e
  li ho visti tutti” – il gesto con cui si verifica se un nome è stato
  davvero sostituito ovunque.

- **Il registro di verifica ora si può cercare e filtrare.** La vista sotto
  “File → Registro di verifica” aveva finora solo una tabella e nient'altro
  – con un mese di tremila esecuzioni si vedeva che era successo molto, ma
  non cosa.

  Sono nuovi un **campo di ricerca**, **tre filtri** (procedimento,
  risultato, tipo) e lo **scorrimento a pagine**, oltre a tre colonne che
  prima non c'erano: **Procedimento** (oscurato o sostituito),
  **Affidabilità** e **Durata**. Sopra l'elenco è indicato quanto si sta
  vedendo in questo momento e quanto il filtro nasconde.

  “Salva come CSV …” ora esporta **esattamente ciò che è visualizzato** –
  chi ha filtrato ottiene il filtrato, e il messaggio ne indica il numero.

  Un trattino in corrispondenza di Affidabilità o Durata significa che per
  quella riga non è stato misurato nulla – ad esempio perché è precedente a
  questa funzione. Questi valori **non** vengono calcolati a posteriori. Un
  filtro per utente continua a non esistere; una singola riga la trova
  comunque la ricerca.

### Rimosso

- **L'avviso sulla trasparenza nella finestra “Informazioni su questa
  applicazione” è di nuovo scomparso.** Era presente dalla versione
  0.10.22-beta.1 e diceva che l'applicazione era stata sviluppata con il
  supporto dell'Intelligenza Artificiale. Non è richiesto da nessuna parte,
  e proprio in un'applicazione per la protezione dei dati alcuni lo
  leggevano come un'affermazione sul modo di lavorare – cioè come se i
  documenti andassero verso un servizio in rete. La bonifica avviene
  tuttora esclusivamente sul proprio computer; questo è scritto dove
  appartiene, nella scheda “Protezione dei dati”.

### Corretto

- **Il programma scambiava la propria icona con una peggiore.** Chi
  registrava il menu contestuale dal programma stesso, aveva dopo
  un'insegna diversa nella barra delle applicazioni rispetto a dopo
  l'installazione – simile, ma con barre allineate a sinistra invece che al
  centro e visibilmente più grossolana. Dietro c'era un ripiego: se il
  programma non trova il modello dell'icona, ne disegna una da sé. Era
  pensato per il caso in cui **non** ci fossero affatto icone; in realtà
  disegnava anche quando quelle fornite erano già presenti da tempo – e le
  sovrascriveva. In una versione installata dal setup non esiste un
  modello, quindi lì colpiva chiunque. Le icone esistenti ora restano
  intatte.

  **Le installazioni già interessate non recuperano l'icona corretta da
  sole** – per questo occorre reinstallare una volta.

- **“Objektkennung: OB-4711-22" veniva considerato un nome utente.** Il
  riconoscitore per i nomi utente controllava le proprie etichette senza un
  confine di parola davanti – quindi catturava **ogni** parola che termina
  con una di esse: Objektkennung, Fahrzeugkennung, Gerätekennung. Il valore
  che seguiva veniva rimosso, sebbene non avesse nulla a che fare con un
  nome utente.

  I composti realmente intesi – „Benutzerkennung“, „Anmeldekennung“ –
  compaiono singolarmente nell'elenco e continuano a essere trovati.


- **In inglese, greco, giapponese e coreano, sedici segnaposto comparivano
  in tedesco nel risultato.** Chi aveva impostato l'interfaccia su una di
  queste quattro lingue, per i tipi di dato più recenti si ritrovava le
  etichette tedesche scritte nel documento – da una password diventava
  `[ZUGANGSDATEN_1]` invece di `[CREDENTIALS_1]`, da un codice di diagnosi
  `[DIAGNOSESCHLUESSEL_1]` invece di `[DIAGNOSIS_CODE_1]`. Erano interessati
  salute, diagnosi, terapia farmacologica, codici di diagnosi e di farmaco,
  religione, sindacato, opinione politica, diritto penale, credenziali di
  accesso, nome utente, dati della carta, coordinate, professione, importo
  e caratteristica personale.

  Le restanti 44 lingue non hanno mai avuto l'errore: ricavano le proprie
  etichette dai file linguistici, in cui questi tipi erano presenti fin
  dall'inizio. Proprio queste quattro lingue gestiscono tabelle proprie per
  un altro motivo – la loro scrittura non sopravvive al set di caratteri
  del PDF, per cui lì compaiono etichette latine –, e in queste tabelle
  mancavano semplicemente i tipi nuovi.

  È emerso durante la traduzione della pagina del catalogo: il sito
  prometteva ai lettori inglesi etichette che il programma non scriveva.
  Un test ora confronta le quattro tabelle con l'elenco di tutte le
  etichette che possono comunque essere generate.

- **La finestra delle regole non si apre più troppo piccola per il suo
  contenuto.** Nella scheda “Modelli di ricerca personalizzati” la riga di
  spiegazione dell'assistente (“Ricerca in corso: …”) si trovava mezza
  nascosta dietro il campo “Testo di prova” – proprio la frase con cui,
  senza conoscere le espressioni regolari, si verifica se la propria regola
  cerca la cosa giusta. La finestra aveva una dimensione minima fissa
  risalente a un'epoca con meno schede, e quindi poteva essere ridotta
  sotto ciò che vi entrava. Ora si adatta al proprio contenuto e si apre
  solo tanto piccola quanto tutto resta leggibile.

- **I nomi nelle formule delle tabelle non rimangono più.** Una cella ha
  più di un posto per il testo, e finora ne veniva ripulito solo uno. Se un
  nome si trovava in una formula – `="Frau "&"Sieglinde Ortner"` – oppure
  era l'ultimo risultato calcolato di una formula, rimaneva invariato nella
  cartella di lavoro, anche se la stessa persona nella cella accanto era
  stata sostituita. Chi cliccava sulla cella lo leggeva nella barra di
  modifica.

  Entrambi i casi vengono ora sostituiti. Viene toccato solo ciò che si
  trova tra virgolette: riferimenti di cella, nomi di funzione e nomi di
  foglio restano intatti, `=SUMME(K2:K6)` continua a calcolare. Poiché lo
  stesso nome ottiene ovunque lo stesso segnaposto, anche
  `=SUMMEWENN(A:A;"Huber";B:B)` continua a trovare le proprie righe.

- **I grafici non mostrano più nomi.** Un grafico salva una propria copia
  delle etichette degli assi – continua a disegnare anche quando le celle
  di origine sono da tempo vuote. Sotto le barre restavano quindi ancora
  cinque nomi di persone, mentre la tabella sopra era pulita. Vale sia per
  i fogli di calcolo **sia** per le presentazioni.

- **Gli intervalli con nome contenenti testo fisso vengono ripuliti.** Un
  intervallo con nome può contenere, invece di un riferimento di cella, un
  testo fisso; se lì c'era un nome, rimaneva. Il **nome** dell'intervallo
  resta invece invariato – a esso si riferiscono le formule, e una
  ridenominazione produrrebbe un errore di riferimento. Come per il nome
  del foglio, viene segnalato, non sostituito.

- **Una data di nascita riconosciuta una volta scompare in tutto il
  documento.** Una data da sola non dice nulla – solo una parola chiave la
  trasforma in una data di nascita, ed è proprio per questo che una data di
  fattura resta tranquilla. Se lo stesso dato compariva però una seconda
  volta nello stesso documento senza questa parola – nel titolo di
  un'immagine, in un campo modulo compilato –, restava lì, anche se poche
  righe sopra “nato il …” era stato riconosciuto senza dubbio. Viene
  trasferito solo ciò che in **questo** documento è già stato riconosciuto
  come data di nascita; non viene comunque indovinato nulla.

- **I dati strutturati nelle pagine web rivelano la data di nascita.** Nel
  blocco JSON-LD per i motori di ricerca la data si trova sotto la chiave
  `birthDate` – la chiave dice cosa sia, come altrove fa l'intestazione di
  colonna. Ora viene letta anche questa; “Birthday” e “Birthdate” valgono
  quindi anche nei moduli come etichetta di campo.

- **Data di nascita e numero di matricola vengono trovati anche nelle
  tabelle.** In una cella si trova solo il valore nudo – `14.03.1988`. Cosa
  significhi lo dice solo l'intestazione di colonna, che si trova molte
  righe più in alto. In Excel veniva già letta; nelle tabelle LibreOffice e
  nei file CSV no, e lì la data di nascita restava quindi.

  Entrambi ora leggono anche l'intestazione – **ma solo se essa stessa è
  un'etichetta di campo**. Sotto “Geburtsdatum” la data cade, sotto
  “Rechnungsdatum” o “Lieferdatum” no. È deliberatamente l'interpretazione
  prudente: un'intestazione come “Name” sopra un'osservazione qualsiasi
  avrebbe già una volta messo un segnaposto su una frase in cui non compare
  affatto una persona.

### Corretto

- **Un CSV bonificato resta una tabella.** Il riconoscimento legge una riga
  CSV come una frase e per questo a volte estendeva i propri risultati
  anche oltre un punto e virgola. Il segnaposto inghiottiva il separatore,
  la riga aveva dopo una colonna in meno, e il file non si apriva più come
  tabella. I riscontri ora terminano al confine della cella, e le
  virgolette del mascheramento restano. Le celle interessate vengono poi
  lette ancora una volta separatamente – altrimenti la cella vicina
  resterebbe non bonificata, coperta dal riscontro troppo lungo.

- **Commenti nelle presentazioni.** L'annotazione a margine di una diapositiva
  – spesso proprio il punto in cui c'è scritto “Si prega di chiamare la
  Sig.ra … prima della riunione” – rimaneva intatta, con tanto di nome di
  chi l'aveva scritta. In Excel entrambe le cose erano già state ripulite
  da tempo; PowerPoint memorizza il testo del commento e l'autore in modo
  diverso, e ciò era stato trascurato. Riguarda entrambi i formati: quello
  più vecchio e quello che PowerPoint scrive dal 2019 – lì anche
  l'indirizzo e-mail aziendale legato all'autore. Le iniziali che
  PowerPoint mostra sul fumetto vengono rimosse insieme al resto.

- **File LibreOffice: formula, campo utente, autore della nota.** Ciò che
  in Excel era già stato ripulito, restava nella tabella ODS – lì la
  formula non è un elemento a sé, ma una proprietà della cella, e il nome
  al suo interno sopravviveva. Alla riapertura successiva LibreOffice lo
  ricalcolava.

  A questo si aggiungono altri tre punti: il valore di un **campo utente**
  in OpenDocument si trova una volta nella dichiarazione in alto e nel
  testo viene solo richiamato – finora veniva sostituito solo il richiamo,
  per cui alla riapertura tornava il vecchio valore. L'**autore di una
  nota** e di una modifica tracciata restava. E in una **tabella** il
  tracciamento delle modifiche non veniva affatto ripulito – a differenza
  del documento di testo –, per cui i contenuti di cella cancellati, con
  tanto di nome dell'autore, restavano conservati. I riferimenti di cella
  e le formule di somma restano intoccati.

- **Le pagine web salvate rivelano i propri attributi.** Una pagina non
  mostra affatto tutto ciò che contiene. Un campo modulo compilato porta
  l'inserimento nel `value`, un'interfaccia JavaScript deposita il proprio
  set di dati in `data-…`, e il blocco per i motori di ricerca (JSON-LD) lo
  ripete completamente e in forma ben formata: nome, data di nascita,
  indirizzo, telefono. Il testo visibile era bonificato, tutto questo
  restava.

  Ora vengono ripuliti anche questi punti, oltre ad `aria-…` (ciò che viene
  letto ad alta voce dallo screen reader), `placeholder`, `summary` e il
  nome di file suggerito di un collegamento. Il blocco JSON-LD viene letto
  come dati e resta valido – le sue chiavi e il suo vocabolario restano,
  spariscono solo i valori. Il normale JavaScript continua a non essere
  toccato.

- **Le immagini perdono i propri metadati anche senza EXIF.** Una foto
  porta accanto a sé il nome del fotografo, l'ora di scatto e le
  coordinate GPS del luogo di ripresa – in un annuncio di locazione questo
  rivela l'indirizzo, anche se nel testo non ce n'è alcuno. Questo veniva
  rimosso finché l'immagine aveva EXIF. Se le indicazioni erano però
  registrate **solo** come XMP (così salvano Lightroom e Photoshop) o come
  blocco di testo in un PNG (`Author`, `Comment`), l'immagine restava del
  tutto intatta. Entrambi i casi vengono ora riconosciuti e rimossi – anche
  nelle immagini che si trovano in un documento e vi restano incorporate.
  L'orientamento continua a essere preservato, e un'immagine senza metadati
  non viene salvata di nuovo inutilmente.

- **Destinazioni dei collegamenti in tabelle, presentazioni e documenti
  Word.** Dove porta un collegamento non è scritto nel testo, ma in un
  archivio separato del file. Un indirizzo e-mail dietro “Scrivi e-mail”
  sopravviveva quindi intatto alla bonifica, mentre lo stesso indirizzo nel
  testo era stato sostituito. `mailto:` e `tel:` vengono ora ripuliti anche
  lì, così come nelle pagine web salvate.

### Nuove funzioni

- **Le lettere ai pazienti non tornano più danneggiate.** Finora il
  riconoscimento dei nomi scambiava i principi attivi per nomi di persona:
  da “Metoprololsuccinat” diventava `[NAME]`, da “Ramipril” diventava
  `[ORT]`. Il piano terapeutico era dopo inutilizzabile – mentre le
  diagnosi restavano intatte, cioè esattamente al contrario. Misurato, ciò
  riguardava il **63% dei principi attivi** e il **53% dei termini tecnici
  clinici**, e non solo in tedesco: su sette lingue il 74%, in italiano
  tutti i casi esaminati.

  Maskuro ora conosce il vocabolario medico e lo lascia in pace. Restano
  il 6% invece del 43% (tedesco) e l'1% invece del 74% (sulle lingue).
  Dove precede un titolo di cortesia – “Gentile Signora …” – il nome resta
  un nome, anche se per caso si chiama come un principio attivo.

- **Malattie e farmaci si possono rimuovere – se lo si desidera.** Nuovo
  segno di spunta nelle impostazioni: “Rimuovi anche malattie e farmaci”
  (riga di comando: `--mit-diagnosen`). Per fascicoli del personale,
  licenziamenti e perizie, dove la diagnosi non riguarda nessun altro.

  **Disattivato per impostazione predefinita**, e di proposito: una lettera
  medica *consiste* di diagnosi e principi attivi. Chi ne anonimizza una –
  per la ricerca, per un corso di formazione, per uno strumento di IA –
  vuole per lo più conservare proprio questo contenuto e sbarazzarsi solo
  di chi ne è protagonista. La diagnosi lì è il contenuto utile, non
  l'identificativo.

  Il riconoscimento trova le denominazioni comuni e non sostituisce la
  verifica: un elenco di malattie non è mai completo, perché il medico
  scrive “C2-Abusus”, dove la classificazione riporta “Disturbi da alcol”.

- **I codici di diagnosi e di farmaco vengono trovati.** ICD-10 (`I48.2`),
  ATC (`A10BA02`) e il numero centrale farmaceutico sono dati sulla salute
  come qualsiasi diagnosi scritta per esteso – nelle lettere di dimissione
  e nei documenti di fatturazione persino la forma più frequente. Sono
  attivati per impostazione predefinita, come le altre categorie
  particolari secondo l'art. 9 GDPR.

  Un codice di diagnosi viene riconosciuto solo con una prova: con “ICD”
  davanti oppure tra parentesi dietro la riga della diagnosi. Senza questa
  condizione il programma prenderebbe il tasto funzione **F10** per una
  diagnosi di dipendenza – nella classificazione F10 è esattamente questo.

- **Il file finito ora si può copiare.** Su ogni riga completata, accanto a
  “Visualizza”, “Correggi” e “Mostra nella cartella”, compare un quarto
  pulsante: **Copia**. Mette il file bonificato negli appunti – da lì passa
  con Ctrl+V (Mac: ⌘V) in un'e-mail, una finestra di chat o uno strumento
  di IA, senza il passaggio dalla cartella.

  Viene copiato il **file**, non il suo testo: impaginazione, immagini e
  le barre di oscuramento restano quindi conservate. Dal menu contestuale
  dell'elenco anche più risultati selezionati insieme finiscono negli
  appunti in un colpo solo, e nel menu “File” lo stesso percorso è
  disponibile come **“Copia risultato”** per chi preferisce usare la
  tastiera.

- **La selezione dei paesi può ora seguire il documento.** I numeri di
  documento d'identità, previdenziali e fiscali variano da paese a paese,
  e finora quali paesi venissero controllati era fissato per l'intera
  sessione – derivato dalla lingua dell'interfaccia. Chi lavora in tedesco
  e bonifica una lettera francese, cercava quindi al suo interno codici
  fiscali tedeschi e non il numero di previdenza sociale francese.

  Nella finestra delle regole ora c'è per questo **“Automaticamente in base
  alla lingua del documento”**. La selezione fissa resta disponibile
  accanto, e di proposito: il riconoscimento della lingua non è infallibile
  – se sbaglia, si applica la selezione paese sbagliata. Chi tratta solo
  pratiche di un paese, va più sul sicuro con l'elenco fisso.

  Restano non toccati da ciò i modelli **tedeschi** (codice fiscale, targa,
  interno telefonico): dipendono dalla lingua, non dalla selezione paese, e
  continuano ad agire anche quando un breve testo tedesco viene classificato
  come inglese.

- **Password, chiavi e nomi utente vengono ora trovati.** Chi copia un
  messaggio di errore, un log o un estratto da un file di configurazione in
  una finestra di IA, ha quasi sempre una chiave di accesso al suo interno –
  e finora restava invariata.

  Vengono riconosciute entrambe le forme: le forme di chiave diffuse che
  parlano da sole (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web
  Token, l'intestazione di una chiave privata), e la forma etichettata –
  „Passwort:", „API-Key =", „Token:", „Benutzername:". Viene sostituito
  solo il valore, mai l'etichetta: „Passwort: [ZUGANGSDATEN_1]" resta
  leggibile, e chi verifica il risultato vede che lì c'era una password.

  Nome utente e password sono due tipi separati. Chi vuole rimuovere solo
  le password, disattiva l'uno e mantiene l'altro.

- **I codici a barre e QR nelle immagini vengono resi irriconoscibili.** Su
  un provvedimento scansionato è quasi sempre incollato un codice, e vi si
  trova il numero di protocollo – lo stesso numero che nel testo accanto
  viene rimosso. Finora restava la versione leggibile da macchina: la barra
  sopra il numero non serve a nulla, se due centimetri più in là un
  dispositivo lo legge in un secondo.

  Vengono riconosciuti QR-Code, Data Matrix, Aztec, Code 128, EAN e le altre
  forme diffuse. Reso irriconoscibile significa pixelato, e in modo più
  grossolano che per i volti: la correzione d'errore di un codice recupera
  sorprendentemente molto da pochi campi conservati, un velo tiepido non
  sarebbe una rimozione.

  L'opzione si trova accanto a “Rendi irriconoscibili i volti” ed è
  ugualmente **preimpostata**. Anche con l'opzione disattivata, il rapporto
  indica quante immagini portano un codice – un volto lo si vede sfogliando,
  un codice lo si scambia per un dettaglio.

- **Codice di sicurezza della carta, PIN e data di scadenza vengono
  trovati.** Il numero della carta di credito lo trovava già il programma;
  solo con i tre dati accanto è utilizzabile, e su ogni scontrino di
  addebito si trovano insieme. Tutti e tre solo dietro la propria
  etichetta – “123” da solo è un numero civico, un numero di pagina o una
  quantità.

- **Le coordinate nel testo vengono trovate.** Dalle immagini Maskuro ha
  già rimosso finora il luogo di ripresa; se lo stesso dato si trovava come
  testo nella perizia o nel rapporto di intervento, restava. Vengono
  riconosciuti i gradi decimali e la notazione gradi-minuti-secondi. Per i
  gradi decimali deve trovarsi nelle vicinanze una parola come “Standort”,
  “Fundort” o “Koordinaten” – altrimenti ogni serie di misure con due cifre
  decimali sarebbe un'indicazione di luogo.

- **Gli importi in denaro si possono ora rimuovere insieme.** Nuovo segno
  di spunta “Rimuovi anche gli importi in denaro”, preimpostato **su
  disattivato** come le date sopra: in un contratto l'importo è il
  contenuto, e chi oscura tutto non protegge nessuno. In una busta paga, in
  una proposta di conciliazione o in un estratto conto è invece proprio il
  dato che dice più sulla persona del nome accanto — questo lo sa solo chi
  ha il documento davanti a sé.

  Un importo viene riconosciuto **solo con indicazione di valuta**:
  “4.250,00” da solo è una quantità, solo “4.250,00 EUR” è denaro. Simbolo
  di valuta, sigla e nome scritto per esteso contano, sia prima che dopo,
  inclusa la grafia “990,– CHF”.

- **Le categorie particolari secondo l'art. 9 GDPR vengono riconosciute.**
  Confessione religiosa, appartenenza sindacale, convinzione politica, dati
  sulla salute – e accanto i dati penali secondo l'art. 10. Sono i dati il
  cui trattamento il regolamento **vieta** in linea di principio; sono
  quindi l'unico nuovo gruppo preimpostato **su attivo**. Chi vuole
  conservarli, lo decide da sé.

  Viene riconosciuta la forma in cui si trovano nella pratica: il campo del
  modulo sul foglio personale – „Religionsbekenntnis: röm.-kath.",
  „Gewerkschaft: ÖGB", „Grad der Behinderung: 50", „Vorstrafen: keine" –,
  sia con i due punti accanto sia con l'etichetta sopra, come fornisce un
  foglio compilato.

  **Il testo continuo appartiene allo stadio IA.** „Er engagiert sich seit
  Jahren in der Gewerkschaft" è lo stesso dato, e nessun modello di ricerca
  lo trova in modo affidabile. Lo stadio IA da questa versione cerca
  espressamente anche queste categorie; chi ha bisogno del testo continuo,
  lo attiva.

- **Caratteristiche personali e professione – i dati che mostrano chi si
  intende anche senza nome.** Sesso, stato civile, statura, colore degli
  occhi e dei capelli vengono rimossi da questa versione; professione,
  funzione e reparto su richiesta, tramite un segno di spunta a sé
  (“Rimuovi anche professione e reparto”) oppure `--mit-berufen`.

  **Perché l'uno è attivo e l'altro no:** “La responsabile del reparto
  Acquisti” indica in un'azienda esattamente una persona, anche se il nome
  accanto è oscurato – in una perizia o in un licenziamento va rimossa. Un
  elenco del personale *consiste* invece di qualifiche professionali; chi
  le rimuovesse per impostazione predefinita, restituirebbe un foglio
  vuoto. Quale caso ricorra lo sa solo chi ha il documento davanti a sé. Le
  caratteristiche sopra si trovano quasi solo in campi modulo, sono rare e
  non portano mai il contenuto – non costano quindi nulla.

- **Verificare un file estraneo.** “File → Verifica file …” rilegge un
  documento già oscurato e segnala cosa vi si trova ancora – e **in quale
  punto**: pagina e riga, tipo e lunghezza. Per il caso in cui qualcuno
  verifichi il lavoro di un altro: una pratica dello studio legale, una
  risposta dell'ente, la propria corrispondenza in uscita prima dell'invio.

  **Il valore stesso non compare nel rapporto.** Chi apre il punto lo vede
  comunque – e il rapporto può quindi essere salvato e condiviso, senza
  essere esso stesso una raccolta di dati personali.

  **E il rapporto dice in ogni caso ciò che non ha potuto vedere.** Le
  immagini non vengono lette; in caso di una scansione senza livello di
  testo, “nessun riscontro” significa *non verificato*, non *pulito*. Da
  riga di comando questo viene distinto dal valore di ritorno:
  `--nachpruefen` restituisce 0 per verificato e pulito, 4 per riscontri e
  5 per non verificabile. Con questo la corrispondenza in uscita può essere
  trattenuta automaticamente, invece di essere lasciata passare.

- **Rapporto di verifica: un foglio per ogni bonifica.** “File → Salva
  rapporto di verifica …” – oppure `--pruefbericht <cartella>` da riga di
  comando – scrive un PDF di una pagina (a scelta CSV o testo) con i dati
  dell'esecuzione, i tipi trovati con relativo numero, due indicatori e una
  nota di verifica. Per la pratica in archivio e per la vigilanza: il
  registro di verifica è la prova solida, ma nessuno presenta un file
  JSON-Lines.

  **Sono nuovi due numeri**, che finora non si vedevano da nessuna parte:
  la *affidabilità media* – quanto era sicuro il riconoscimento in ciò che
  ha trovato – e il *tasso di mascheramento*, la quota di caratteri
  sostituiti sul testo. Entrambi compaiono con il proprio limite: l'affidabilità
  non dice **nulla** su ciò che è sfuggito, e accanto ad essa compare sempre
  su quanti riscontri si basa; il tasso non conta le immagini e risulta
  troppo alto in un documento illustrato.

  **I valori dei riscontri non compaiono sul foglio** – lo stesso limite
  del registro e della ricerca. In basso ci sono due righe che non dicono
  la stessa cosa: la somma di controllo mostra che il foglio è invariato;
  la riga di registro – solo con registro attivo – rimanda alla riga
  **firmata** che documenta l'esecuzione. Solo essa ne dimostra la
  provenienza.

- **“Quanto era sicuro?" – gli indicatori sul risultato.** Un pulsante
  “Indicatori” sotto il risultato apre ciò che finora non si vedeva da
  nessuna parte: riscontri, parole e caratteri, la distribuzione per tipo
  come riga a barre, oltre all'affidabilità media e al tasso di
  mascheramento. Gli stessi numeri del rapporto di verifica, solo subito e
  senza stampa.

  **Con la propria riserva nella stessa area:** accanto all'affidabilità
  compare su quanti riscontri si basa, e sotto la frase che essa **non**
  dice nulla su ciò che è sfuggito. Una percentuale senza questa frase si
  legge come un tasso di successo – e chi la intende così è messo peggio
  che senza quel numero.

  Il calcolo avviene solo all'apertura: il denominatore del tasso di
  mascheramento costa una lettura per file, e non deve pagarla chi i
  numeri non li guarda affatto.

- **Costruire modelli di ricerca personalizzati senza scriverne uno.** La
  scheda “Modelli di ricerca personalizzati” ora guida in tre passaggi:
  *Cosa cercate? → Come si presenta da voi un dato del genere? → Assegnare
  un nome e salvare.* Digitate un esempio – ad esempio `KD-004711` –, il
  programma ne ricava la regola e scrive a parole cosa cerca. Un'anteprima
  con contatore di riscontri verifica a ogni tasto premuto.

  **Un'espressione regolare non compare in tutto questo.** La capacità non
  era mai stata il problema: i modelli di ricerca personalizzati esistono
  da tempo, solo che richiedevano un'espressione come `\bKD-\d{6}\b`, e in
  uno studio legale o in un ufficio personale non la scrive nessuno. Chi
  vuole scriverne una, apre la modalità esperto.

  **Il catalogo dei modelli è stato riordinato:** tredici schede con nome,
  spiegazione ed esempio di valore, filtrate tramite etichette di
  categoria – Finanze, Enti pubblici, Contatti, Personale, Medicina.

  E se il modello dedotto è troppo ampio, il programma lo dice da sé: un
  esempio composto solo da cifre colpisce ogni anno e ogni importo, e chi
  non sa leggere l'espressione non potrebbe altrimenti accorgersene.

- **Sette etichette invece di cinquantasei caselle.** Una nuova scheda
  “Cosa viene cercato” raggruppa tutti i tipi riconoscibili in sette
  gruppi – Persona, Contatto e luogo, Identificativi, Finanze, Tecnica,
  Categorie particolari, Aziende e Personalizzato. Un'etichetta attiva il
  proprio gruppo, “Tutto attivo” e “Tutto disattivo” l'intero elenco;
  sotto resta ogni tipo attivabile singolarmente.

  **Preimpostato è tutto attivo, e resta così.** Ciò che qui viene
  disattivato non viene affatto cercato – l'intervento più grossolano
  consentito dalla finestra delle regole, e agisce su ogni documento. Per
  questo sotto l'elenco compare in ogni momento quanti tipi sono
  disattivati, e viene salvato solo ciò che è disattivato: un tipo nuovo è
  quindi attivo anche in un file di regole di due giorni fa, invece di
  cadere silenziosamente.

- **Trasferire un riquadro su tutte le pagine.** Nella finestra di
  correzione il pulsante **Trasferisci su tutte le pagine** prende
  l'ultimo riquadro tracciato e oscura lo stesso punto su ogni altra
  pagina – per intestazione, piè di pagina e campo del numero di
  protocollo. Con una pratica scansionata di ottanta pagine, questo
  trasforma venti minuti in due.

  **“Lo stesso punto” significa la stessa posizione *relativa* sul
  foglio.** In un lotto proveniente dall'alimentatore capita regolarmente
  che una pagina sia orizzontale, un'altra sia A3, una terza ruotata; un
  rettangolo trasferito in modo assoluto finirebbe accanto all'intestazione
  – e si vedrebbe una barra e si crederebbe la cosa fatta.

  **Si oscura, non si sostituisce**, anche se il riquadro di partenza era
  un segnaposto: sotto lo stesso rettangolo, alla pagina quaranta c'è
  scritto qualcos'altro rispetto alla pagina uno, e un segnaposto con lo
  stesso numero affermerebbe un'uguaglianza che non esiste.

- **Una nota sulla barra di oscuramento.** Nel diritto di accesso al
  fascicolo, accanto a ogni oscuramento è scritto perché è stato oscurato.
  Il nuovo campo **Nota sulla barra** nelle impostazioni – oppure
  `--balkenvermerk` – scrive un breve testo su ogni barra: „§ 203 StGB",
  „DSGVO", „vertraulich". Per un documento rilasciato da un ente pubblico,
  questo fa la differenza: il destinatario vede il motivo, senza avere un
  registro che comunque non riceverà mai.

  **Preimpostato vuoto**, perché la nota è visibile nel documento rilasciato
  ed è essa stessa un'informazione – dice al destinatario sotto quale
  titolo qualcosa viene trattenuto. Agisce solo con l'**oscuramento**; dove
  c'è un segnaposto, non c'è alcuna barra. Su una barra troppo piccola per
  un testo leggibile viene omessa – una nota illeggibile sembra un errore.

- **Sblocco senza connessione internet – ora completo.** Nella finestra
  della licenza “Sblocca senza internet” esisteva già da tempo: sopra un
  codice di richiesta da portare con sé, sotto il campo per lo sblocco che
  torna indietro. Solo che finora **nessuno poteva rilasciarlo** – mancava
  lo strumento per farlo, e il codice finiva nel vuoto. Ciò è stato
  corretto.

  Per enti pubblici e studi legali con computer isolati, questo non è un
  caso speciale, ma il caso normale – ed è proprio il gruppo di utenti in
  cui la promessa “i Suoi documenti non lasciano mai il computer” pesa di
  più. Il codice non rivela nulla sui documenti: contiene l'identificativo
  della licenza e un valore hash del computer, nient'altro.

- **Acquisire dallo scanner.** “File → Acquisisci dallo scanner …” legge
  direttamente un lotto e mette le pagine nell'elenco – per un ufficio
  postale, la differenza tra due passaggi di lavoro e uno solo. Un
  alimentatore di fogli viene svuotato fino all'ultima pagina; dispositivo,
  risoluzione e colore vengono scelti nella finestra di dialogo di sistema
  dello scanner, che già conoscete.

  **Non si bonifica automaticamente.** Vedete prima cosa è arrivato e poi
  premete “Bonifica” come per qualsiasi altro file – una scansione che
  passasse subito toglierebbe la vista su un lotto inserito storto.

  **Questo esiste solo su Windows**, e la voce di menu lo dice anche su
  Mac: lì il software del vostro scanner scrive in una cartella, e
  “Monitora cartella …” bonifica tutto ciò che vi arriva.

### Varie

- **L'elenco di tutti i dati riconosciuti è ora incluso** e viene generato
  dal codice sorgente (`hilfe/GEFUNDENE-ANGABEN.md`): 177 tipi in 35 paesi,
  23 dei quali con calcolo della cifra di controllo. Indica anche come è
  stato conteggiato – noi contiamo `[NAME]` una volta, dove altri elencano
  nome, secondo nome e cognome come tre voci.

- **L'oscuramento è ora disponibile anche in Word, PowerPoint, OpenDocument
  e HTML.** La scelta tra segnaposto e oscuramento era finora possibile
  solo per i file PDF. Ora possono anche gli altri: il riscontro viene
  rimosso, e al suo posto compare una barra nera – nel documento stesso,
  non come immagine sopra. Chi inoltra il file, inoltra una pratica
  oscurata e non una in cui l'oscurato si trova ancora come testo
  sottostante.

  **La scelta viene decisa separatamente**, in due campi di selezione: “Per
  PDF” e “Per Word, PowerPoint, OpenDocument e HTML”. Lo si vuole diverso –
  il PDF oscurato va all'ente pubblico, la stessa cosa come file Word
  continua a circolare in azienda e deve restare leggibile. Da riga di
  comando rispettivamente `--pdf-modus` e `--office-modus`; un
  “oscuramento” salvato da versioni precedenti vale ancora per il PDF.

  In tabelle, testo semplice, CSV ed e-mail la barra non è possibile – lì
  manca la superficie su cui potrebbe posarsi. Continua a essere inserito
  un segnaposto, e il risultato **lo dice ora**, invece di farlo
  silenziosamente.

- **Nuovo: “Rimuovi” – il punto trovato resta semplicemente vuoto.** La
  terza modalità operativa accanto a segnaposto e oscuramento, e l'unica
  che funziona in **ogni** formato: omettere qualcosa non richiede alcuna
  superficie. Nel PDF non viene disegnato nulla, in Word e HTML il punto
  resta vuoto, in una tabella lo stesso.

  È la più silenziosa delle tre: chi legge il risultato non vede che lì
  c'era qualcosa – anche la lunghezza del valore non si rivela più. Per un
  documento che qualcuno deve verificare, il segnaposto resta di solito la
  scelta migliore.

  Nelle immagini nessuna delle tre scelte vale: i pixel non si possono
  sostituire con un segnaposto né omettere. Ciò che il riconoscimento del
  testo trova lì viene sempre coperto come finora.

- **La finestra di correzione non afferma più sostituzioni che non
  esistono.** A destra compariva per ogni valore un segnaposto – anche in
  un file oscurato, in cui non ne compare nessuno. Un clic su una riga del
  genere non segnava nulla, e “Annulla” andava a vuoto. Ora vi compare
  “oscurato” oppure “rimosso”, e le righe non si possono affatto più
  annullare: il testo è sparito, non c'è nulla da recuperare. Valeva per i
  file PDF oscurati, per Word e OpenDocument e per tutto ciò che veniva
  trovato nelle immagini.

- **La vista testo ora mostra le barre come barre.** Un file Word oscurato
  appariva **vuoto** durante la correzione: nei punti oscurati c'erano
  spazi vuoti, come se il programma avesse inghiottito il testo. Il motivo
  era la visualizzazione, non il risultato – nel documento stesso la barra
  era sempre stata corretta. Ora compare anche nella vista, nera come nel
  risultato, in Word, PowerPoint, OpenDocument e HTML.

- **I messaggi di Outlook (`.msg`) vengono ora bonificati.** `.eml`
  esisteva già da tempo – ma nelle aziende tedesche l'e-mail è Outlook, e lì
  un messaggio salvato si chiama `.msg`. Con questo il formato più denso di
  dati personali è coperto anche nella sua forma di archiviazione più
  diffusa: oggetto, mittente, righe dei destinatari, testo del messaggio,
  versione HTML, elenco dei destinatari e allegati – questi ultimi tramite
  i percorsi esistenti e con gli stessi segnaposto del testo dell'e-mail.

  **Un `.msg` porta lo stesso testo più volte**, ed è questa la trappola:
  come testo semplice, come HTML **e** come RTF. Chi bonifica solo il testo
  semplice non ha fatto nulla – Outlook mostra preferibilmente l'RTF. La
  versione RTF viene quindi rimossa completamente, così come le intestazioni
  internet con la loro catena Received e le chiavi di ricerca binarie, che
  contengono nomi e indirizzi che sopravvivono a qualsiasi bonifica del
  testo. Il risultato continua ad aprirsi in Outlook e mostra il testo
  senza formattazione tipografica; il rapporto lo dichiara espressamente.

- **Descrivere le regole con parole proprie, invece di scrivere Regex.** La
  finestra delle regole può molto e richiedeva per questo un'espressione
  regolare – il punto in cui la maggior parte si ferma. Ora basta una
  frase: “I nostri numeri di pratica nella forma 12 C 345/26 devono
  rimanere.” Lo stadio IA ne propone termini e modelli di ricerca.

  **Viene applicato solo ciò che si spunta – e per impostazione predefinita
  non è spuntato nulla.** Accanto a ogni proposta c'è una frase che ne
  spiega il significato, e il numero dei suoi riscontri in un testo di
  esempio che potete fornire voi stessi. Ciò che **toglie** protezione è
  contrassegnato come tale: “rimuovi sempre questo termine” e “non
  rimuovere mai questo termine” sembrerebbero altrimenti uguali in un
  elenco. Le proposte che si applicherebbero a tutto non vengono affatto
  mostrate.

- **Il registro di verifica ora somma su tutte le postazioni di lavoro.**
  Se un'azienda deposita i registri tramite `protokoll_pfad` su una
  condivisione, lì ogni postazione scrive il proprio file mensile – finora
  un responsabile della protezione dei dati con trenta postazioni doveva
  visionare trenta file singolarmente. Sopra l'elenco compare ora una riga
  con i totali del mese, e **segnala le catene interrotte con il nome**:
  una modifica successiva emerge solo se qualcuno controlla, e in trenta
  file nessuno controlla a mano.

  **Nessun riepilogo per persona** – nemmeno in questa vista. Una
  classifica “chi ha bonificato quanto” si presterebbe al controllo del
  comportamento e delle prestazioni, e nel diritto della cogestione conta
  questo, non l'intenzione. Vengono contate esecuzioni, file e riscontri a
  livello aziendale.

- **“Suggerisci profilo da un documento": interrogare le regole una volta
  sola invece di scorrere quarantaquattro tipi.** Nella finestra delle
  regole c'è un nuovo pulsante: mostra allo stadio IA un documento,
  determina di cosa si tratta – lettera medica, candidatura, contratto,
  fattura, avviso – e propone le strategie adatte. Per una lettera medica,
  ad esempio, le date vengono spostate invece che sostituite, perché in una
  cartella clinica la cronologia è il contenuto.

  **I profili risiedono nel programma, il modello sceglie solo tra essi** –
  le regole di oscuramento non dipendono da ciò che un modello linguistico
  ritiene una buona idea. Ogni punto viene proposto singolarmente e
  motivato; non viene applicato nulla senza conferma, e ciò che avete
  stabilito voi stessi resta intatto. Senza stadio IA resta l'impostazione
  sicura: segnaposto per tutto.

- **Nuova strategia “inventa": un valore falso plausibile invece di un
  segnaposto.** “La Sig.ra Berger scrisse al Sig. Doppler a Fulda” invece
  di “[NAME_1] scrisse a [NAME_2] a [ORT_1]” – per materiale di formazione,
  pratiche dimostrative, banche dati di prova e tutto ciò che verrà poi
  sottoposto a una IA. Formula di cortesia, costruzione della frase e
  leggibilità restano conservate.

  Lo stesso valore ottiene lo stesso valore falso, in tutti i file di una
  pratica e su ogni computer con lo stesso file di regole – **senza che da
  nessuna parte venga salvata un'associazione** (lo stesso meccanismo
  dell'hashing). Gli indirizzi e-mail si trovano su domini di esempio
  riservati, i numeri di telefono nell'intervallo tenuto libero per questo,
  gli IBAN inventati portano una cifra di controllo calcolata correttamente.
  Possibile per nomi, luoghi, indirizzi, aziende, e-mail, telefono e IBAN;
  per altri tipi la regola viene respinta, invece di restare inefficace.

  **Il rapporto dichiara espressamente che si è inventato.** Un documento
  bonificato in questo modo si legge come uno vero e non lo è – non vale
  come prova e non deve essere consegnato come originale.

- **La controprova: “Chi resta riconoscibile?"** Un nuovo segno di spunta
  sotto lo stadio IA sottopone di nuovo al modello linguistico il
  **risultato finito** e chiede chi, nonostante la bonifica, sia ancora
  riconoscibile. Si intende il caso che nessun riconoscimento al mondo
  trova, perché lì non compare affatto un nome: “l'unica ostetrica del
  circondario”, “il collega che si è licenziato a marzo dopo l'incendio”.
  Nessun modello coglie il caso, e sul posto lo sanno comunque tutti chi si
  intende.

  **In questo caso non viene rimosso nulla.** I punti compaiono con una
  frase di motivazione nel rapporto, e si decide a mano – un programma che
  di propria iniziativa prendesse frasi da un documento perché gli sembrano
  compromettenti, trasformerebbe una bonifica in una riscrittura, e
  nessuno vedrebbe cosa manca. Al massimo cinque punti per file; ciò che il
  modello non può documentare alla lettera, cade. Da riga di comando:
  `--restrisiko` insieme a `--ki`.

- **La via di ritorno dall'IA: “Ritraduci risposta”.** Finora era costruita
  solo metà del ciclo – copiare il testo, incollarlo bonificato, sottoporlo
  all'IA. La risposta tornava con `[NAME_1]`, e chi ne aveva bisogno
  reinseriva a mano ciò che aveva tolto a mano. Ora il percorso di ritorno
  si trova nel menu “Programma”: copiare la risposta, cliccare sulla voce,
  i nomi veri tornano al loro posto.

  L'associazione per questo risiede **solo nella memoria di lavoro**, vale
  sempre solo per l'ultimo punto bonificato e scade dopo un'ora; chi
  disattiva il monitoraggio degli appunti la perde immediatamente. Si può
  recuperare solo ciò che è stato sostituito – ciò che è oscurato,
  mascherato o hashato non è reversibile, e il programma dice quanti punti
  ha dovuto per questo lasciare invariati. Le installazioni gestite
  disattivano del tutto il percorso di ritorno tramite l'impostazione
  predefinita `rueckweg`.

- **Monitora cartella: ciò che vi viene inserito, poco dopo si trova
  bonificato nell'uscita.** Per un ufficio postale, un team di caselle
  postali o una cartella di scansione – si configura una volta, dopo
  nessuno clicca più. Si trova sotto “File → Monitora cartella …”, da riga
  di comando tramite `--wache <cartella>`.

  L'originale resta dove si trovava; su richiesta si sposta invariato
  nella sottocartella “Fatto”, senza che nulla venga mai sovrascritto. Un
  file viene toccato solo quando è stato scritto completamente – un file
  ancora in fase di copia sulla rete verrebbe altrimenti letto a metà e
  segnalato come bonificato. Ciò che va storto resta lì ed è segnalato,
  invece di essere ripetuto all'infinito. E il monitoraggio ricorda ciò che
  è già stato fatto senza usare i nomi dei file: ciò che si trova in una
  cartella di ingresso spesso rivela già dal nome di cosa si tratta.

  **Il monitoraggio di una cartella al di fuori del proprio profilo utente
  – ad esempio su un'unità di rete – richiede una licenza per
  l'automazione.** Una cartella raggiungibile da più persone è un servizio,
  non una postazione di lavoro; nel proprio profilo e durante il periodo di
  prova la restrizione non si applica.

### Corretto

- **Le impostazioni erano tagliate a destra.** La finestra si apriva con
  una dimensione fissa, sufficiente solo per la dimensione dei caratteri
  con cui era stata sviluppata: su Mac “Verifica ora”, “Cambia …” e le note
  accanto erano per metà fuori. Ora si apre tanto larga quanto le sue
  pagine richiedono – in ogni lingua e con ogni dimensione di carattere,
  limitata solo dallo schermo.

- **“Verifica ora” risponde ora in modo visibile.** Il risultato compariva
  nella riga di stato della finestra principale – cioè dietro la finestra
  delle impostazioni, da cui era stata posta la richiesta. Chi verificava
  non vedeva nulla. Ora la risposta compare come messaggio sopra le
  impostazioni, e se è disponibile una nuova versione, porta subito
  all'installazione. All'avvio del programma resta come finora nella riga
  di stato, nessuna finestra si apre senza essere stata richiesta.

- **I file copiati non arrivavano negli appunti su Mac.** Il deposito dei
  file bonificati segnalava successo e non depositava nulla di utilizzabile
  – incollare non produceva nulla. Riguardava tutto ciò che scrive file
  negli appunti.

- **E dagli appunti su Mac veniva letto solo il primo file.** Chi copiava
  tre file nel Finder e sceglieva “Bonifica ora gli appunti”, ne riceveva
  indietro due non bonificati – senza che nulla lo segnalasse. Ora arrivano
  tutti.

- **“Verifica file” ora accetta anche file trascinati** – come la finestra
  principale. Ciò che viene rilasciato si aggiunge, invece di scartare la
  selezione precedente; rilasciare due volte la stessa cosa non cambia
  nulla, e ciò che il programma non può leggere viene segnalato invece di
  essere inghiottito.

- **E la finestra dice che sta aspettando.** Si apriva con una casella
  vuota e un pulsante grigio “Verifica” – sembra che non ci sia nulla, non
  che manchi la selezione. Ora compare “Nessun file ancora selezionato –
  trascinatelo qui oppure sceglietelo sotto tramite ‘Seleziona file …‘.”

- **Un'esecuzione lunga ora dice che è in corso.** “Caricamento del modello
  aggiuntivo per il riconoscimento più preciso – un momento …” restava
  visibile per tutto il tempo del calcolo del riconoscimento: con un file
  di 47.500 parole quindi diciotto minuti, sebbene il caricamento fosse
  terminato dopo nove secondi. Chi vede questo, ritiene il programma
  bloccato. Ora segue “Riconoscimento più preciso in corso – con testi
  lunghi richiede alcuni minuti”, e la riga di stato conta insieme:
  “Riconoscimento più preciso (7/312)”. La segnalazione avviene dal ciclo
  del modello – ogni 250 parole, quindi circa ogni sei secondi –, non per
  blocco di testo: un blocco di testo porta dodicimila parole e richiede
  minuti.

- **Un'esecuzione interrotta ora dice che è stata interrotta.** Chi premeva
  “Annulla” leggeva dopo “0 di 1 file bonificato(i).” – contato
  correttamente e comunque l'informazione sbagliata. Il messaggio su quale
  file fosse interessato veniva sovrascritto nello stesso istante dal
  messaggio di conteggio. E nell'elenco dei file compariva ancora “in
  corso …”, sebbene nulla fosse più in esecuzione; ora vi compare
  “interrotto”.

- **La frase sulla protezione dei dati era tagliata.** “… nessun cloud,
  nessun caricamento. Maggiori informazioni nella protez” – con la
  larghezza della finestra con cui parte il programma, terminava nel mezzo
  di una parola. Ora occupa l'intera larghezza.

- **Il servizio di licenza poteva comunicare qualcosa, e nessuno
  ascoltava.** Quando tutti i posti licenza sono occupati, la licenza è
  scaduta, la chiave è sconosciuta o la gestione delle licenze presso il
  fornitore è disattivata, il servizio invia proprio per questo un motivo –
  era previsto fin dall'inizio che ve lo si spiegasse **una volta**. Non
  veniva mai mostrato. Ora compare un avviso che dice prima che il
  programma continua a funzionare invariato, e poi di cosa si tratta. Una
  volta per motivo: chi lo ha chiuso, non lo rivede nel controllo
  giornaliero – lo rivede però se il motivo cambia.

- **Una licenza multiposto acquistata nel negozio mostrava “1 posto".** Il
  negozio distribuisce chiavi predisposte e conserva presso di sé il numero
  di posti acquistati; veniva però mostrato il numero ricavato dalla chiave
  stessa, e questo per ogni chiave di scorta indica un posto. Chi aveva
  acquistato otto posti, leggeva “1 posto” – e dal secondo computer
  registrato in poi l'indicazione compariva in rosso con “Si prega di
  contattare la Vostra amministrazione”. Ora vale il numero comunicato per
  ultimo dal servizio; senza risposta resta quello della chiave, e non
  diventa mai inferiore al volume acquistato. Lo stesso vale per acquisti
  aggiuntivi e rinnovi: questi modificano presso il fornitore il numero di
  posti, non la vostra chiave.

- **Dopo l'acquisto compariva “Licenziato per Maskuro Privatlizenz".** Non
  è un nome, ma il segnaposto sotto cui vengono predisposte le chiavi – il
  vostro nome non può trovarsi lì, perché la chiave viene firmata già
  prima dell'acquisto. Invece di mostrarvi un nome estraneo come il
  vostro, ora compare semplicemente “Licenza privata” e il numero di
  posti. Con una licenza intestata a voi, il vostro nome compare invariato.

- **Nel menu Guida compariva “Guida _FAQ”.** La e commerciale era diventata
  un trattino basso, perché Qt lo interpretava come segno di una lettera
  da tastiera. Ora compare “Guida & FAQ”.

- **La finestra delle impostazioni restava aperta quando il programma
  spariva nell'icona** – e anche quando la finestra principale veniva
  chiusa. Ora si chiude insieme. (Riguarda solo questa versione; la
  finestra propria è nuova.)

- **Una richiesta di licenza respinta ora dice il motivo.** Se il servizio
  di licenza respingeva una richiesta senza inviare un motivo, nella
  finestra della licenza compariva in rosso “Risposta sconosciuta.” – una
  frase con cui né voi né l'assistenza potete fare nulla e che vi fa
  cercare l'errore nella vostra chiave. Ora compare cosa è successo
  davvero: che il servizio ha respinto senza motivarlo, e a chi
  rivolgersi. Se la gestione delle licenze presso il fornitore è
  temporaneamente disattivata, viene indicato anche questo – con
  l'avvertenza che la vostra chiave non ne è interessata.

- **Su Mac le lingue configurate risultavano improvvisamente mancanti.**
  All'avvio il programma segnalava “Nessun modello linguistico installato”
  e proponeva la configurazione iniziale, sebbene le lingue fossero già
  caricate da tempo – chi controllava sotto “Lingue dei documenti”, le
  trovava tutte presenti. Il programma le cercava, a seconda del percorso
  di avvio, in due posti diversi: se avviato dalla cartella Applicazioni,
  le trovava; se la stessa build veniva avviata come semplice cartella, le
  cercava accanto a sé, dove non ce ne sono. D'ora in poi su Mac vale
  sempre lo stesso posto nel profilo utente, indipendentemente da come è
  confezionato il programma. Non serve ricaricare nulla.

- **“Novità” mostrava metà elenco.** La finestra dopo un aggiornamento si
  interrompeva a metà frase, e i punti restanti comparivano come
  segnaposto vuoti. La colpa era di un segnaposto tra parentesi angolari –
  ad esempio `<datei>.docx` –, che la visualizzazione interpretava come
  formattazione e da cui in poi scartava tutto il resto. Erano interessate
  proprio le novità sulla sicurezza. La guida mostra tali segnaposto
  correttamente da sempre; ora lo fa anche questa finestra.

- **Pizzicare con due dita ora esegue lo zoom nella finestra di
  correzione.** Sul trackpad è *il* gesto di zoom – nell'editor finora non
  faceva nulla, e chi voleva osservare un punto più da vicino doveva
  ricorrere al cursore o a Ctrl+rotellina del mouse. La pagina segue il
  gesto immediatamente e viene ridisegnata nitidamente al rilascio.

- **Si esegue lo zoom sul punto che si sta guardando.** Pizzicare ingrandisce
  intorno al punto tra le dita, Ctrl+rotellina del mouse intorno al punto
  sotto il cursore. Pulsanti, scorciatoie da tastiera e il cursore dello
  zoom mantengono fermo il centro – a essi non appartiene alcun punto verso
  cui si indica. Prima, in tutti i casi, restava fermo solo il valore di
  scorrimento: partendo da una pagina adattata, questo manteneva il bordo
  superiore, e tutto ciò che stava sotto usciva dall'immagine ingrandendo.

- **“Prima/Dopo” nell'anteprima di pagina era un pulsante morto.** Finché
  l'anteprima di pagina era attiva, si poteva premere – e ogni volta
  segnalava che l'originale non era apribile. Non c'è nemmeno nulla da
  confrontare lì: l'anteprima di pagina è un'immagine della versione
  bonificata, non esiste una controparte dell'originale. Il pulsante è ora
  bloccato e indica al passaggio del mouse il motivo con una via d'uscita
  (la vista testo). La sua descrizione prometteva per giunta espressamente
  che il confronto funzionasse “indipendentemente dal fatto che sia attiva
  la vista testo o quella di pagina” – cosa che non era mai vera.

- **L'anteprima di pagina faceva bloccare LibreOffice.** Se venivano
  generate due anteprime di pagina contemporaneamente – ad esempio “Oscura
  come PDF” mentre l'anteprima stava ancora calcolando –, il sistema
  segnalava un arresto anomalo di LibreOffice, sebbene alla fine le pagine
  comparissero comunque: entrambe le esecuzioni accedevano allo stesso
  archivio di lavoro di LibreOffice, cosa che non tollera. Ora ne riceve
  sempre solo un'esecuzione; le altre ne usano una propria. Per questo
  serve qualche secondo in più, ma non compare più alcun messaggio di
  errore, e nessuna delle esecuzioni resta senza risultato. Un secondo
  incarico di rendering accanto a uno in corso, inoltre, non viene proprio
  accettato.

- **“Mostra originale” poteva chiudere il programma.** Se l'originale non
  poteva essere aperto – perché spostato, rinominato, protetto da password
  o su un'unità disconnessa –, la finestra di correzione si interrompeva
  senza preavviso, e le copie di lavoro aperte andavano perse. Ora compare
  un avviso, l'interruttore torna indietro, e la versione bonificata resta
  visibile. Dove l'originale in linea di principio non corrisponde – ad
  esempio con un'anteprima di pagina PDF nata da un file Word – l'interruttore
  è bloccato fin dall'inizio e indica al passaggio del mouse il motivo,
  invece di mostrare ogni volta lo stesso avviso alla pressione.

- **Le segnalazioni di errore non arrivavano mai.** Chi voleva segnalare un
  errore riceveva “La controparte ha respinto la segnalazione” – e nessuno
  l'aveva mai vista. Due cause, entrambe lungo il percorso: il programma
  non si identificava presso il server e veniva quindi respinto dalla
  protezione contro gli accessi di massa, e l'indirizzo rimandava a un
  secondo nome che il programma non seguiva. Entrambe sono corrette; una
  segnalazione ora esce di nuovo. **Lo stesso riguardava lo sblocco della
  licenza**: accesso, disconnessione e richieste non raggiungevano
  nemmeno il servizio – lì solo in modo non appariscente, perché una
  richiesta senza risposta deliberatamente non modifica la vostra licenza.
  E se un rifiuto resta comunque inspiegabile, ora compare il suo numero
  tecnico, invece che ogni causa appaia uguale.

- **Un clic su “Mostra originale” poteva chiudere il programma.** Se
  l'originale non poteva essere aperto – spostato, rinominato, su
  un'unità di rete disconnessa, protetto da password o danneggiato – la
  finestra di correzione spariva insieme a tutte le copie di lavoro
  aperte. Ora l'interruttore resta sulla versione bonificata, e un
  riquadro dice cosa è successo; il motivo tecnico si trova nei dettagli,
  nel caso vogliate segnalarlo. Lo stesso vale per un risultato che non si
  può visualizzare: la finestra si apre e lo dice, invece di sparire.

- **La domanda su un arresto anomalo arrivava troppo spesso – e cancellava
  la traccia di cui chiedeva.** Compariva anche quando nulla era andato in
  crash: la nota si crea non appena si verifica un disturbo inatteso da
  qualche parte, anche se il programma lo supera e viene poi chiuso in modo
  del tutto normale; non veniva mai rimossa. E chi rispondeva “No”,
  distruggeva gli unici dettagli dell'accaduto – la nota spariva già alla
  *visualizzazione* della domanda. Entrambe le cose sono corrette: una
  chiusura ordinata rimuove la nota, si chiede solo dopo un'interruzione
  reale, e viene spuntata solo dopo la vostra risposta. I dettagli si
  trovano comunque nel registro degli errori sul proprio computer – chi
  non vuole inviare nulla non perde comunque nulla. Viene inviato come
  sempre solo ciò che avete visto completamente in anticipo e approvato
  voi stessi.

- **“Bonifica” poteva restare bloccato in silenzio.** Se i modelli
  linguistici si bloccavano durante il caricamento, il pulsante restava
  disattivato – senza spiegazione. Un clic su di esso non faceva nulla, e
  la riga di stato diceva invariata “Caricamento dei modelli linguistici
  in corso …”, anche dopo dieci minuti. La causa: i disturbi nei processi
  in background finivano in un punto che nessuno vede all'avvio dal
  gestore file; restava una finestra che sembrava pronta al lavoro e non
  reagiva ad alcun clic. Ora tali disturbi finiscono nel registro degli
  errori, il caricamento dei modelli linguistici segnala il proprio
  fallimento in ogni caso invece di arrendersi silenziosamente, e se resta
  comunque silenzioso, l'applicazione dice dopo tre quarti di minuto che
  qualcosa non va, con un consiglio nei dettagli. Il pulsante bloccato
  indica al passaggio del mouse il proprio motivo. Un primo caricamento
  lungo non conta come silenzio: finché viene segnalato un progresso,
  resta tranquillo. Come arresto anomalo non conta nulla di tutto ciò:
  l'applicazione continua a funzionare, e al successivo avvio quindi non
  viene nemmeno chiesto.

- **Su Mac il programma non trovava più aggiornamenti – e diceva di essere
  già aggiornato all'ultima versione.** La versione Mac non includeva un
  archivio dei certificati radice; lo cercava in un punto che esiste solo
  sul computer su cui viene compilata. Con questo non poteva verificare con
  nessun server con chi stesse parlando, e interrompeva ogni connessione:
  nessun aggiornamento, nessuno sblocco della licenza, nessun caricamento
  di modelli linguistici, nessuna segnalazione di errore. Le versioni
  precedenti ne facevano silenziosamente l'informazione “State usando
  l'ultima versione”. I certificati ora si trovano nel programma stesso;
  se non ne trova lì, prende quelli del sistema e su Mac in caso di
  necessità quelli del portachiavi – e se non ce n'è affatto nessuno, lo
  dice, invece di affermare di essere l'ultima versione. La verifica stessa
  non viene mai disattivata.

  Questo unico aggiornamento gli utenti Mac devono ancora installarlo a
  mano: una versione che non raggiunge il server non può nemmeno
  rinnovarsi da sola.

### Modificato

- **La finestra principale è stata riordinata.** In basso c'erano sei
  pulsanti della stessa dimensione affiancati – “Informazioni …”, “Guida” e
  “Guida & FAQ” sotto, sebbene gli stessi tre percorsi si trovassero già
  nel menu Guida sopra. Ora sono riuniti in un pulsante “Guida” che li
  apre; nessuno viene perso. In basso restano i due percorsi con cui
  davvero si comincia: “Bonifica” e “Oscura a mano …”.

- **Ciò che il programma sta facendo ora ha un posto fisso.** Il messaggio
  (“Caricamento dei modelli linguistici in corso …”, “(3 / 7)
  lettera.pdf”, “5 di 7 file bonificato(i).”) era finora un testo grigio
  tra due file di pulsanti. Ha ottenuto un'area propria, con un punto
  colorato davanti: grigio finché nulla è in corso, blu durante il lavoro,
  verde dopo un'esecuzione senza problemi e giallo se sono emersi avvisi.
  Il punto non dice nulla che non compaia accanto – lo dice solo più
  velocemente.

- **Le impostazioni sono diventate una finestra propria.** Si trovavano
  finora nella finestra principale – un riquadro con quattro schede, che si
  apriva sotto “Altre impostazioni”, e che era poi troppo piccolo per il
  proprio contenuto: c'era sempre una barra di scorrimento al suo interno,
  e la scelta tra anonimizzazione e pseudonimizzazione era per metà fuori
  dall'immagine. Il pulsante ora si chiama “Impostazioni …” e apre una
  finestra con una barra laterale; ciascuna delle quattro pagine ci entra
  del tutto. La finestra principale non si apre più all'avvio, e si può
  vedere l'elenco dei file accanto. È cambiato solo dove si trovano le
  impostazioni – quali esistono e cosa fanno è invariato.

- **“Dettagli” si apre, invece di saltare.** La finestra cresceva finora in
  un'unica immagine, e bisognava cercare cosa fosse cambiato. Ora vi si
  sposta.

- **Dimensioni dei caratteri e spaziature seguono nell'intera finestra la
  stessa unità di misura.** I titoli erano in due punti di dimensioni
  diverse, e righe dello stesso rango erano distanziate in modo diverso.
  Visibile è questo come calma, non come singola modifica.

- **L'anonimizzazione è ora l'impostazione predefinita.** Finora era
  preimpostata la pseudonimizzazione: le stesse persone ricevevano lo
  stesso numero (`[NAME_1]`, `[NAME_2]`), i riferimenti restavano
  leggibili – legalmente restavano però **dati personali**. Chi non
  imposta nulla, ottiene ora la procedura che toglie i dati dall'ambito del
  GDPR: tutti i riscontri di un tipo si chiamano uguali (`[NAME]`). La
  numerazione è rimasta una scelta, si trova invariata nella stessa
  finestra; le impostazioni esistenti restano come sono. Da riga di
  comando `--pseudonymisieren` (anche `--mit-nummerierung`) ripristina.

- **I segnaposto anonimizzati non si possono più annullare singolarmente.**
  Chi anonimizza, ottiene per ogni persona lo stesso segnaposto – e con
  questo non esiste più un singolo punto che appartenga a un nome preciso.
  La finestra di correzione offriva comunque “Annulla sostituzione”: un
  clic avrebbe inserito *uno* dei valori in *tutti* i punti. Le righe sono
  ora attenuate come per i dati oscurati, il clic ne dice il motivo, e un
  riscontro corretto a mano non riceve più un numero che non compare da
  nessun'altra parte nel resto del documento.

  Per lo stesso motivo, dopo un'esecuzione anonimizzata non esiste più
  “Ritraduci risposta” – prima avrebbe inserito un nome estraneo al posto
  di ogni persona. Chi ha bisogno di questo ciclo, sceglie
  “Pseudonimizza”; l'applicazione ora lo dice anche così, invece di
  rimandare a un'associazione scaduta.

  Da riga di comando `--zuordnung` ora si interrompe con
  l'anonimizzazione, invece di scrivere un file che non è una
  ritraduzione – nella finestra il segno di spunta era già bloccato da
  tempo. O si aggiunge `--pseudonymisieren` oppure si omette `--zuordnung`;
  il messaggio lo dice. Il risultato in tal caso non viene proprio
  generato, affinché uno script non si ritrovi con un lavoro a metà.

- **Il canale di aggiornamento è ora impostato di nuovo su “Stabile”.**
  Senza una scelta propria, il canale si orientava finora in base alla
  build da cui proveniva la versione in esecuzione – chi aveva provato una
  volta una versione di test, riceveva da quel momento in poi
  permanentemente versioni di test proposte. Un cambio di canale è una
  decisione e deve restare tale; l'impostazione predefinita è quindi
  “Stabile”. I canali impostati restano intatti.

### Migliorato

- **“Beschwerdevorgang" non vale più come nome di luogo.** Nel titolo
  “Nota d'atto – Beschwerdevorgang 12 C 345/26" il programma oscurava
  anche la pratica: il modello linguistico lo riteneva un luogo,
  indipendentemente dal contesto. A essere registrato non è la singola
  parola, ma il **radicale** del composto – „vorgang" e „notiz" coprono
  quindi anche Geschäfts-, Buchungs- e Zahlungsvorgang oppure la
  Telefonnotiz. Su trenta termini amministrativi verificati, prima tre
  scatenavano un falso allarme, ora nessuno più; continua a essere trovato
  tutto ciò che sta accanto (“Beschwerdevorgang: Bernd Meisinger" perde il
  nome, non il titolo).

- **L'anonimizzazione tiene di nuovo il conto – per il riscontro successivo
  e per il registro.** Nella modalità operativa anonimizzante il programma
  non memorizzava i valori trovati. Due cose restavano per questo mute: il
  riscontro di coerenza a livello di documento (un cognome che compare più
  tardi da solo, restava) e l'elenco delle sostituzioni nel registro di
  verifica. Finché l'anonimizzazione era la scelta più rara, ciò si notava
  a malapena – come impostazione predefinita sarebbe diventato il caso
  normale. Nel documento non cambia nulla: il segnaposto resta senza
  numero.

- **“Nessun dato personale" ora si chiama “nessuna informazione
  personale".** Nella finestra di annullamento e nell'avviso sui volti c'era
  scritto il termine giuridico *Datum* – il singolare di “Daten”. Veniva
  letto come giorno del calendario, tanto più che l'applicazione altrove
  offre “Rimuovi anche le date”. Ora si chiama ovunque “informazione”,
  come nei quattro motivi sopra nella stessa finestra.

- **La riga di provenienza si trova ora solo nella finestra
  “Informazioni".** “Made with ♥ in Austria" si trovava in basso nella
  finestra principale in mezzo alla fila di pulsanti e lì si leggeva come
  un altro pulsante. Si trova ora nella finestra “Informazioni" – dove la
  si cerca.

- **La superficie di deposito ora ha un bordo visibile.** Il suo bordo
  tratteggiato era così pallido da risaltare a malapena dalla finestra –
  era indifferente, finché la superficie era solo una superficie. Da
  quando è un elemento di comando che si può raggiungere con il tasto Tab,
  questo tratto è l'unica cosa che la mostra come tale; è quindi stato
  portato al valore che la norma richiede per questo.

## 0.10.22-beta.1 – 15 agosto 2026

### Nuovo

- **Se il monitoraggio degli appunti è disattivato, ora è davvero
  spento.** Il monitor conserva in memoria gli ultimi contenuti, per poter
  ripristinare l'originale – finora anche quando avevate disattivato il
  monitoraggio. Ora la cronologia viene dimenticata alla disattivazione.
  Questo ha un costo: il ripristino dopo la disattivazione, ed è proprio
  questo l'intento: disattivato significa disattivato.
- **Il registro degli errori non contiene più percorsi di file.** Restava
  solo sul vostro computer e non veniva mai inviato da sé – ma riportava
  percorsi in chiaro, e un nome di file spesso rivela più del contenuto. Da
  „…/Scheidung_Mueller_Vergleich.docx" diventa ora, in fase di scrittura,
  `<datei>.docx`; l'estensione resta, perché conta per la ricerca errori.
  Lo stesso vale per la nota dopo un arresto anomalo.
- **L'elenco delle sostituzioni ora avverte al proprio interno.** È l'unico
  file in cui i vostri dati originali compaiono in chiaro, e si trova
  accanto al risultato – chi condivide una cartella lo condivide con essa.
  Ora l'avviso compare come prima riga **nel** file, l'area di output
  indica il percorso completo invece del solo nome file, e sulla riga di
  comando il file viene finalmente menzionato: finora non si sapeva
  nemmeno che fosse stato creato.
- **Anonimizzare o pseudonimizzare è ora una scelta esplicita.** Al suo
  posto c'era finora una casella „Denominare uniformemente gli stessi nomi
  – così l'IA riconosce ancora chi è chi". Questo descriveva il vantaggio e
  taceva la conseguenza: segnaposto numerati in modo consecutivo
  (`[NAME_1]`, `[NAME_2]`) sono **pseudonimizzazione**, e i dati
  pseudonimizzati restano dati personali – chi credeva di aver anonimizzato
  con ciò si sbagliava. Ora le due procedure stanno una accanto all'altra,
  ciascuna con il proprio costo. L'impostazione predefinita resta
  pseudonimizzare, perché un documento che verrà poi letto o elaborato da
  un'IA ha bisogno dei suoi riferimenti. Con l'anonimizzazione l'elenco
  delle sostituzioni è bloccato: renderebbe di nuovo il risultato
  ricostruibile. Manuale e FAQ spiegano la differenza in tutte le 18
  lingue; sulla riga di comando l'opzione ora si chiama anche
  `--anonymisieren`.
- **La riga sopra l'area di deposito dice ora ciò che è davvero vero.**
  Prometteva „elaborazione al 100% locale – senza cloud e senza account,
  conforme al GDPR". Per i vostri documenti questo è vero, per il
  programma non in questa generalità: cerca aggiornamenti, segnala errori
  su richiesta, scarica modelli e registra postazioni acquistate. Ora vi
  compare l'affermazione più ristretta e sostenibile: i vostri documenti
  non lasciano il computer.
- **Sul risultato ora è sempre indicato che va controllato.** Finora
  Maskuro segnalava, dopo un'esecuzione senza intoppi, „12 dato/i
  rimosso/i" in verde e nient'altro – questo si legge come una garanzia di
  aver trovato tutto. Gli avvisi comparivano solo quando qualcosa in
  concreto non poteva essere controllato (immagini, allegati sconosciuti).
  Ora sotto ogni risultato compare in modo ben visibile che non in ogni
  caso vengono riconosciuti tutti i dati personali, che il controllo spetta
  all'utente e che ciò che manca va integrato a mano – nella finestra,
  nell'area di output e sulla riga di comando. Nessuna finestra di avviso
  da chiudere: la frase resta lì in modo permanente. Anche la guida rapida
  lo dice ora con le stesse parole.
- **Dopo un aggiornamento, all'avvio compare cosa è cambiato.** Finora un
  aggiornamento avveniva in silenzio e non si distingueva da un semplice
  riavvio. Ora compare una volta „Novità" – e chi ha saltato una versione
  vede anche quelle intermedie. Non al primissimo avvio: lì continua a
  guidare la guida rapida.
- **Cinese e giapponese ora trovano nomi.** Finora non ne trovavano
  **nessuno** – non pochi, nessuno. A entrambi i modelli linguistici
  mancava la segmentazione delle parole, senza la quale una frase senza
  spazi vale come un'unica parola; il programma passava silenziosamente al
  modello sostitutivo multilingue. Entrambe le lingue ora riconoscono
  persone e luoghi come le altre. Il dizionario giapponese viene caricato
  insieme alla lingua e non è incluso nel programma – da solo pesa circa
  200 MB, che altrimenti tutti si porterebbero dietro.
- **La Romania è selezionabile come paese.** Finora mancava del tutto. Con
  ciò vengono riconosciuti indirizzi rumeni („Strada Victoriei 30"), codici
  postali con località („010061 București") e il Cod Numeric Personal –
  quest'ultimo solo con cifra di controllo corretta, per non evidenziare
  ogni numero di tredici cifre su una fattura. Finora nei documenti rumeni
  restava leggibile il codice postale accanto al nome di località oscurato.
- **„Rasterizza pagina" nell'editor.** Se il testo non si può rimuovere da
  un PDF – capita con file di produttori terzi –, ora la pagina può essere
  sostituita a richiesta con la sua immagine: il testo è così rimosso in
  modo irrevocabile, la pagina resta leggibile e ricercabile. L'avviso che
  segnala il caso offre subito il passo come pulsante; anche tramite
  „Strumenti → Rasterizza pagina" è accessibile di propria iniziativa.
  Annullare lo riporta indietro.
- **L'interfaccia è ora disponibile anche in croato, greco, lituano,
  sloveno, giapponese e coreano.** Sono così diciotto lingue. Manuale,
  FAQ e testi legali sono completi in tutte e sei. Le etichette nel
  documento ripulito seguono l'interfaccia – da `[NAME_1]` diventa
  `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` o `[氏名_1]`. **In greco, giapponese e
  coreano le etichette restano in caratteri latini** – `[ONOMA_1]`,
  `[SHIMEI_1]`, `[IREUM_1]`. L'interfaccia resta nella propria scrittura;
  solo ciò che viene scritto nel documento è in caratteri latini. Il
  motivo è la codifica dei caratteri PDF: lì le etichette greche e
  giapponesi arrivavano finora come `[??_1]`, e con ciò non si distingueva
  più un nome da un luogo.
- **Si aggiungono nove paesi, e sette esistenti diventano completi.**
  Vengono ora riconosciuti numeri di carta d'identità, codici fiscali e
  numeri di previdenza sociale insieme agli indirizzi per **Croazia,
  Slovenia, Grecia, Lituania, Macedonia del Nord, Russia, Ucraina, Cina e
  Giappone**. Nei paesi già presenti sono state colmate lacune di maggior
  peso: per **Paesi Bassi** e **Portogallo** finora non esisteva alcun
  numero di identificazione personale – il BSN olandese e il NIF
  portoghese non venivano riconosciuti, benché compaiano praticamente su
  ogni documento di questi paesi. La Polonia riceve il codice fiscale NIP,
  Danimarca, Norvegia e Finlandia i loro indirizzi, il Canada il proprio
  codice postale. Sono così **35 paesi**.

### Rimosso

- **Per Linux al momento non c'è più un pacchetto.** Il codice sorgente vi
  funziona, ma mancano tre cose che questa guida promette: avvio
  automatico, scorciatoie da tastiera globali e – a seconda dell'ambiente
  di lavoro – l'icona nella barra. Distribuire un pacchetto che fa meno di
  quanto descritto sarebbe la strada sbagliata. Windows e macOS non ne sono
  interessati.

### Migliorato

- **I numeri di protocollo vengono ora trovati in tutte le lingue.**
  „Aktenzeichen 12/2026-AB" veniva rimosso, „File reference 12/2026-AB" o
  „Sygnatura 12/2026-AB" restavano invariati: le parole chiave di campo con
  cui Maskuro riconosce un tale numero esistevano solo in tedesco. Ora
  conosce gli equivalenti in dodici lingue – e come finora viene sostituito
  solo il numero, l'etichetta prima resta invariata, così nel risultato si
  vede cosa è stato rimosso.
- **Maskuro occupa a riposo circa mezzo gigabyte in meno.** All'avvio
  veniva finora caricato anche il modello aggiuntivo del riconoscimento più
  preciso, perché la prima ripulitura non dovesse attenderlo. Misurato,
  questo costava 648 MB di memoria e faceva risparmiare 1,9 secondi – e lo
  costava anche quando aprivate la finestra solo per richiuderla subito.
  Il modello viene ora caricato la prima volta che serve; la riga di stato
  lo segnala. Il modello linguistico continua a essere caricato
  all'avvio – ne ha bisogno subito il monitoraggio degli appunti.
- **L'area di deposito ora si usa anche senza mouse.** „Trascinate qui i
  file" era un'area che reagiva ai clic – con la tastiera non ci si
  arrivava, e uno screen reader la leggeva come una cornice con testo
  dentro, non come ciò che è. Ora è un pulsante: il tasto Tab la
  raggiunge, spazio e invio aprono la selezione file, e chi vi è arrivato
  lo vede dal bordo. Tramite il menu „File → Seleziona file" ci si
  arrivava già prima, ma bisognava saperlo.
- **Il nome del file ripulito viene ora anche letto ad alta voce.**
  Nell'elenco file compare come seconda riga, più piccola, sotto
  l'originale – ma finora era solo disegnata, e uno screen reader
  annunciava solo l'originale. Proprio questa riga è costruita contro
  l'equivoco che un'esecuzione sia stata inutile perché nella cartella si
  trova l'originale intatto. La riga suona ora, letta ad alta voce,
  „rechnung.pdf, Risultato: rechnung_bereinigt.pdf".
- **Gli elementi di comando senza etichetta ora dicono a cosa servono.**
  I pulsanti a icona nell'elenco file, i pulsanti di disegno nella
  finestra di correzione e tutti i campi di selezione e inserimento erano
  senza nome per gli screen reader – venivano annunciati come „pulsante" e
  „casella combinata", senza dire di cosa. I pulsanti su una riga citano
  qui anche il file: in un elenco con venti voci si sentiva altrimenti
  venti volte la stessa frase.
- **Chi opera con la tastiera vede di nuovo dove si trova.** Il pulsante
  „Ripulisci" e i pulsanti a icona nell'elenco file sono colorati, e con
  ciò smetteva di comparire il bordo che il sistema disegna normalmente
  intorno all'elemento di comando raggiunto – scorrendo con Tab lo sguardo
  finiva nel vuoto. Entrambi hanno ora un proprio bordo non appena sono di
  turno. I pulsanti non cambiano dimensione.
- **Sette colori del testo erano troppo tenui, in entrambi gli aspetti
  grafici.** Misurati secondo la norma consueta (WCAG 2.1), le righe di
  avviso tenui, i testi secondari sull'area di deposito, i punti della
  guida e, nel tema scuro, in aggiunta il blu e il rosso, erano sotto la
  soglia di 4,5:1 – leggibili con buona luce e buona vista, altrimenti no.
  Tutti sono stati innalzati; la gradazione resta, i testi continuano a
  leggersi come testi secondari. Altri tre – i colori con cui vengono
  segnalati avvisi e successo – rispettavano la soglia solo di poco e sono
  stati adeguati insieme: chi non li legge non legge l'informazione se
  qualcosa è andato storto. Visibilmente è cambiato solo il pulsante
  „Ripulisci" nel tema scuro: ora porta testo scuro invece che bianco,
  come i pulsanti di accento di Windows 11.
- **Ogni riga dell'elenco file ha ora la propria croce.** Finora bisognava
  prima selezionare la riga e poi cliccare su „Rimuovi" – due passaggi per
  una cosa da poco. La croce si trova a destra nella riga e ne basta una.
  Il pulsante „Rimuovi" sottostante è quindi venuto meno; chi vuole
  eliminare più righe in una volta le seleziona e usa la voce nel menu
  contestuale, che dice anche quante sono. „Rimuovi tutti" resta. Dall'
  elenco viene sempre tolta solo la riga – mai un file dal disco.
- **Prima del controllo IA compare ora se questo computer è adatto.**
  Finora nella finestra compariva solo quanto è grande il modello. Chi lo
  attivava su un computer poco potente se ne accorgeva solo al primo
  documento, che richiede molto tempo – dopo 5,4 GB di download. Ora la
  finestra indica **prima** memoria disponibile e spazio libero e dice cosa
  significa; **dopo** viene misurata la velocità e indicata nella
  dimensione di cui si tratta: „Un documento di dieci pagine richiede su
  questo computer circa 12 minuti." Se è troppo lento, il programma
  sconsiglia e offre di disattivare di nuovo il livello – non vieta nulla.
- **La misurazione della velocità ora funziona su ogni computer.** Finora
  compariva solo se veniva anche configurata l'accelerazione grafica –
  disponibile solo su Windows. Su tutti gli altri computer il programma
  stimava quindi la durata in base a un computer estraneo, e proprio dove
  è lento la stima era sbagliata.
- **Gli indirizzi turchi vengono trovati anche nella scansione.** Su
  un'intestazione scansionata „34710 İstanbul" restava leggibile, mentre la
  stessa indicazione nel testo accanto spariva: il riconoscimento del
  testo legge la İ turca senza il suo punto, e il modello si aspettava una
  lettera maiuscola. Lo stesso valeva per „Bağdat Caddesi".
- **Gli indirizzi spagnoli senza un proprio nome di via vengono trovati.**
  „Gran Vía 5" restava invariato perché il modello si aspettava, dopo il
  tipo di via, ancora una parola-nome – con „Calle Mayor" ce n'è una, con
  „Gran Vía" il tipo stesso è già il nome. Lo stesso vale ora per „La
  Rambla" e „Castellana".
- **Nella finestra „Informazioni su questo programma" compare ora un avviso
  di trasparenza** sul fatto che l'applicazione è stata sviluppata con il
  supporto dell'intelligenza artificiale. Riguarda la creazione del
  programma, non il suo funzionamento: la ripulitura avviene ancora
  esclusivamente sul proprio computer.
- **„Gestisci lingue" mostra ora per prime le lingue utilizzabili.** Per
  metà delle 48 lingue non esiste un modello linguistico proprio; lì un
  modello sostitutivo multilingue riconosce i nomi solo debolmente, in
  alcune scritture per niente. Affiancate in un elenco apparivano tutte
  equivalenti. L'impostazione predefinita mostra quindi solo le lingue con
  modello proprio – tramite „Visualizzate" le altre si possono mostrare in
  qualsiasi momento, con una frase su cosa sanno fare e cosa no. Non va
  perso nulla, e chi ha configurato una lingua limitata la conserva.
- **La domanda su una lingua mancante indica ora la via d'uscita.** Se
  viene riconosciuta una lingua per cui non è ancora stato configurato
  nulla, il programma offriva finora solo „Carica" o „Continua senza". Il
  riconoscimento però può sbagliare – in formulari brevi ed elenchi con
  poco testo scorrevole decidono poche parole. Nella finestra c'è quindi
  ora scritto che si può annullare e scegliere la lingua corretta a mano,
  invece di usare „Rilevamento automatico". Questo risparmia, nel dubbio,
  un download di alcune centinaia di megabyte per una lingua che non serve
  affatto.
- **Le etichette dei segnaposto ora parlano la lingua dell'interfaccia.**
  „[NAME_1]", „[ADRESSE_2]" ecc. erano finora sempre in tedesco, a
  prescindere dalla lingua impostata o dalla lingua in cui è redatto il
  documento. Ora seguono la lingua dell'interfaccia – in inglese quindi
  „[NAME_1]", „[ADDRESS_2]". Non la lingua del documento: questa, con
  „rilevamento automatico", è indovinata e talvolta sbagliata; la lingua
  dell'interfaccia non lo è mai.
- **Meno richieste di conferma durante la correzione.** Dove viene salvato
  il risultato è ora indicato in modo permanente in basso nella barra
  („→ vertrag_bereinigt.pdf", nel tooltip la cartella) – un clic su di
  essa sceglie un'altra posizione, senza salvare subito. La domanda al
  primo salvataggio viene così a mancare. La domanda „già elaborato –
  ricominciare?" può essere ricordata per la sessione, e due finestre di
  avviso che davano solo un'informazione sono ora nella barra di stato.
  Restano le domande che evitano un danno non annullabile: il lavoro non
  salvato alla chiusura e l'avviso su testo non rimosso.
- **Il risultato indica ora dove la scansione stessa non era leggibile.**
  Su un documento scansionato il riconoscimento del testo del dispositivo
  non legge tutto correttamente – da „Solarstraße 9" diventa allora ad
  esempio „Solaret^aß« B". Ciò che è stato letto male in questo modo, nessun
  controllo può più trovarlo: appare a ogni modello di ricerca come
  un'accozzaglia di lettere. Il programma non può cambiare nulla in
  merito, ma ora indica tali punti con il numero di pagina – di solito vi
  si trovano timbri, intestazioni o aggiunte manoscritte. Un'indicazione,
  non un avviso: su un documento composto tipograficamente resta assente.
- **L'elenco file mostra ora come si chiama il risultato.** Sotto il nome
  del file compare, dopo l'esecuzione, il nome del file ripulito
  („→ vertrag_bereinigt.pdf"). Finora compariva solo nel protocollo dietro
  „Dettagli", e chi guardava nella cartella trovava l'originale intatto.
  Il nome della fonte resta invariato – altrimenti non si vedrebbe più da
  quale file proviene un risultato.
- **I pulsanti in una riga completata sono più grandi e più chiari.**
  Visualizza, Correggi e „Mostra nella cartella" erano icone piatte senza
  superficie e si perdevano nell'elenco – eppure dopo l'esecuzione sono
  l'unica cosa su cui si clicca ancora.

### Risolto

- **Su interfaccia in lingua straniera le regole personalizzate per
  oscurare, mascherare e sottoporre a hash venivano ignorate in
  silenzio.** Chi aveva stabilito che i nomi venissero oscurati invece che
  sostituiti li otteneva comunque sostituiti – non appena il programma non
  era gestito in tedesco o in inglese. L'impostazione c'era, semplicemente
  non aveva effetto, e nel risultato la differenza non si vedeva.
  Interessate erano nove delle dodici lingue dell'interfaccia.
- **L'impostazione „Lingua delle etichette" non aveva effetto al di fuori
  di tedesco e inglese.** „Tedesco" e „Inglese" si potevano scegliere, ma
  nel documento restava comunque la lingua dell'interfaccia. Ora tutte e
  tre le possibilità funzionano; l'impostazione predefinita „come
  l'interfaccia" fornisce, invariata, lo stesso risultato di prima.
- **In brevi estratti di testo restavano nomi – ad esempio in una
  citazione di email copiata.** Chi ripuliva un estratto tramite gli
  appunti otteneva spesso oscurato solo l'indirizzo email, ma non il nome
  sottostante. Determinante era il puro numero di righe: da sei righe in
  su il programma riconosceva l'estratto come elenco e trovava i nomi, al
  di sotto no – una citazione di email copiata ne ha cinque. Una
  qualsiasi riga aggiuntiva, ad esempio un oggetto, ribaltava il
  risultato. Ora bastano quattro righe, e nella misurazione spariscono
  tutti i nomi verificati invece che un terzo. Su documenti più lunghi e
  su testo scorrevole ciò non ha effetto.
- **L'accelerazione grafica del controllo IA veniva finora disattivata di
  nuovo non appena la si era configurata.** Dopo la configurazione il
  programma misura se la grafica su questo computer è davvero più veloce
  del processore – questa misurazione però falliva sempre, senza dirlo, e
  il risultato „entrambi ugualmente veloci" decideva a favore del
  processore. Chi aveva scaricato i 65 MB otteneva dopo meno di prima. La
  misurazione ora funziona; se fallisce, non cambia più nulla.
- **La stima del tempo calcolava su ogni computer con una velocità
  estranea.** Si basa sulla stessa misurazione; finché questa non
  funzionava, valeva il valore del computer di sviluppo. „Circa due
  minuti" poteva così significare, su un computer lento, mezz'ora.
- **Il livello IA lavora con un modello linguistico nuovo, decisamente
  migliore** (Qwen3.5-9B invece di Qwen3-4B) e non è più limitato a
  tedesco e inglese, ma lavora in dodici lingue. Misurato sul corpus di
  prova: stesso numero di dati trovati rispetto a senza il livello, ma
  meno della metà delle oscurazioni superflue (da 75 a 31). Il modello è
  più grande (5,4 invece di 2,4 GB) e richiede circa il doppio del tempo
  di calcolo; all'attivazione viene caricato una sola volta, quello
  vecchio viene contestualmente rimosso.
- **Gli indirizzi in francese, italiano, spagnolo, portoghese, polacco,
  turco e svedese vengono ora rimossi completamente.** Finora spariva
  solo il nome della via e della località – numero civico e codice
  postale restavano leggibili („[ORT_1] 28, 28013 [ORT_2]"). Per queste
  lingue non esistevano modelli propri di indirizzo; ora sono stati
  aggiunti.
- **Greco e coreano non trovavano alcun nome.** Per il greco la causa era
  il modello sostitutivo – con il modello proprio, ora caricabile, nomi e
  luoghi vengono riconosciuti in modo pulito. Per il coreano la causa era
  nel programma: presupponeva che un nome iniziasse con una lettera
  maiuscola, e l'hangŭl non conosce lettere maiuscole. Interessate erano
  soprattutto le unità brevi – celle di tabella, campi di formulario, voci
  di elenco.
- **Un modello linguistico che non si lasciava caricare interrompeva la
  ripulitura.** Invece di un messaggio d'errore, ora subentra il modello
  multilingue, e il risultato segnala che si è lavorato con il
  riconoscimento più debole. Riguarda al momento cinese e giapponese, i
  cui modelli richiedono una segmentazione delle parole che il programma
  non porta ancora con sé.
- **Una lingua con modello proprio risultava installata non appena era
  caricata un'altra qualsiasi.** Chi configurava ad esempio il turco
  otteneva con ciò il modello sostitutivo multilingue – e cinese,
  giapponese, coreano o greco comparivano di conseguenza con spunta
  impostata e „0 MB" nell'elenco, benché mancasse il loro modello
  proprio. Non si lasciavano quindi mai ricaricare e lavoravano in modo
  permanente con il sostituto più debole. Ora l'elenco mostra lo stato
  effettivo insieme alla dimensione di caricamento.
- **Un livello di riconoscimento fallito taceva.** Se era attivato
  „Riconoscimento avanzato" o „Riconoscimento massimo (IA)", ma il modello
  non si lasciava eseguire, il programma continuava a lavorare senza quel
  livello – senza una parola in merito. Il risultato appariva come
  qualsiasi altro, e l'interruttore restava su „attivo": si riteneva
  quindi il risultato del livello base il massimo ottenibile. Il risultato
  lo dice ora e nomina entrambe le cose – cosa non è stato controllato e
  come ricaricare il modello. Il caso non è raro: su alcuni computer il
  livello IA fallisce al caricamento, quando manca l'accelerazione
  grafica.
- **Un errore nel caricamento del modello aggiuntivo interrompeva l'intera
  ripulitura.** Con „Riconoscimento avanzato" era protetta solo la
  valutazione del modello, non la sua lettura – e proprio lì qualcosa va
  storto se il file è danneggiato o non è compatibile con il computer.
  Invece di un messaggio d'errore, ora c'è un risultato del livello base
  con relativa indicazione.
- **Una lingua non si lasciava più rimuovere – e quindi nemmeno ricaricare.**
  Chi in „Gestisci lingue" toglieva la spunta e applicava la modifica
  leggeva „Tedesco rimosso", ma vedeva la spunta subito di nuovo
  impostata. La causa era la ripresa dalla cartella del programma: in
  un'installazione per tutti gli utenti i modelli linguistici si trovano
  in sola lettura nella cartella del programma, e il programma vi
  attinge quelli mancanti, invece di ricaricare centinaia di megabyte.
  Questa ripresa avveniva a ogni accesso – e ricopiava nello stesso
  istante la lingua appena eliminata. Ora avviene una sola volta; le
  lingue ricaricate restano conservate. Inoltre il programma ora verifica
  dopo l'eliminazione: ciò che non si è lasciato rimuovere viene ora
  segnalato come fallimento invece che come „rimosso".
- **In un'installazione per tutti gli utenti i contenuti ricaricati non si
  lasciavano depositare.** Chi installa il programma per tutti gli
  utenti lo ha in „Programmi", e lì non si può scrivere nulla senza
  diritti di amministratore. Per i modelli linguistici era già previsto da
  tempo un luogo alternativo, per altro no:
  - Il **componente di anteprima pagina** veniva estratto, dopo 290 MB di
    download, nella cartella del programma, e lì falliva – senza indicare
    un motivo. Ora si trova insieme ai modelli linguistici, dove secondo
    l'intenzione avrebbe dovuto trovarsi sempre.
  - L'**accelerazione grafica** non può ripiegare altrove: scambia
    librerie nel programma stesso. Invece di caricare prima e fallire poi
    in silenzio, il programma ora dice in anticipo che qui non funziona e
    cosa significa – il riconoscimento massimo continua a funzionare, solo
    tramite il processore.
  - Una **lingua del riconoscimento del testo** inclusa non si lasciava
    rimuovere: veniva subito ripristinata dalla cartella del programma.
    Stessa causa dei modelli linguistici, stessa correzione.
  - Nel rimuovere una lingua potevano essere cancellati **dati linguistici
    di un'installazione Tesseract estranea**. Ora viene toccata solo la
    propria cartella.
  - Il luogo alternativo valeva finora solo su Windows. Un archivio Linux
    verso `/opt` aveva la stessa necessità senza la stessa via d'uscita.
- **Durante la correzione spariva un'intera riga, benché fosse riquadrata
  solo una parola.** Chi in un file già ripulito oscurava un segnaposto
  perdeva la riga in cui si trovava: da „Sehr geehrte Frau Doktor
  [NAME_1]" non restava nulla – e il messaggio diceva „rimossa una parola
  dal documento". Interessato era ogni file già passato una volta
  attraverso il programma, quindi proprio il caso per cui esiste la
  correzione. Il resto del testo ora resta invariato, nella posizione
  originale.
- **„EMPLOYEES" sopra un elenco di nomi veniva oscurato esso stesso.**
  Stesso caso di „MITARBEITER" nella 0.10.19, solo in inglese – lì era
  rimasto. In maiuscolo manca al modello linguistico il segno
  distintivo, e l'intestazione si trova sopra una serie di nomi veri. I
  nomi sottostanti continuano a essere trovati. Non è stato incluso
  „staff": è un cognome attestato, e la voce coinvolgerebbe ogni „John
  Staff" – stessa valutazione fatta a suo tempo per „Arbeiter".
- **La forma giuridica veniva sostituita una seconda volta.** Su
  un'intestazione scansionata il modello linguistico leggeva „GmbH",
  l'indirizzo e il codice postale come **un'unica** località. Indirizzo e
  codice postale ritagliavano poi le proprie parti, e restava come
  risultato a sé la forma giuridica: nel risultato compariva „[ORT_1]
  [ORT_2]", dove si intendeva „[ORT_1] GmbH". La ragione sociale continua
  a essere sostituita – solo la sigla nuda ora resta invariata, e il
  risultato si legge come un'intestazione invece che come un esercizio a
  riempire spazi vuoti.
- **Un risultato ritagliato non veniva ricontrollato.** La causa del caso
  precedente, e va oltre: i filtri contro i risultati indovinati
  lavoravano su ciò che i riconoscitori **segnalano** – non su ciò che
  resta dopo la risoluzione delle sovrapposizioni. Se un risultato lungo
  viene tagliato da un riconoscitore più forte, il frammento è un testo
  diverso da quello valutato, e nessuno lo riesaminava. Ora sì.
- **„State usando la versione più recente" – benché non fosse affatto
  possibile verificarlo.** Chi aveva impostato come canale di
  aggiornamento „Anteprima (Beta)" o „Stabile – consigliato" riceveva
  questa informazione, mentre su questi canali finora non era ancora
  uscito nulla. Ora il programma dice esattamente questo – e propone di
  scegliere nelle impostazioni un altro canale.
- **Chiudere la finestra durante il caricamento faceva bloccare un
  thread.** Chi avviava Maskuro e richiudeva subito la finestra mentre i
  modelli linguistici erano ancora in caricamento otteneva nel protocollo
  una segnalazione di errore: il processo di caricamento si rivolgeva a
  una finestra che non esisteva più. Conseguenze visibili non ce n'erano,
  ma nel protocollo compariva un arresto anomalo, dove qualcuno era
  semplicemente stato più veloce del programma.
- **Il risultato viene ora osservato, non solo riletto.** Finora una
  pagina valeva come pulita se il valore non compariva più nel testo. Su
  una scansione questo non è una prova – lì il testo visibile è
  un'immagine. Alla fine viene quindi ora verificato se l'area nel
  risultato è davvero oscurata; se lì compare ancora carta chiara, il
  rapporto lo dice espressamente, invece di segnalare „sostituito".
- **Un dato sostituito restava visibile nell'immagine.** Se il valore si
  trovava su un'immagine – un'intestazione scansionata, un timbro,
  un'intera pagina scansionata –, veniva sì rimosso dal testo del
  documento, ma restava comunque **visibile**: ciò che l'occhio umano
  legge sono lì pixel. Il rapporto segnalava comunque „sostituito". Ora
  l'area nell'immagine viene oscurata, indipendentemente dalla strategia
  impostata, e il segnaposto compare chiaro su questo sfondo – brutto, ma
  onesto, e la corrispondenza resta conservata. Se un formato immagine non
  si lascia modificare, il risultato ora lo dice espressamente, invece di
  apparire pulito.
- **Su una scansione mancava del tutto il segnaposto.** Lo strato di
  testo di una pagina scansionata viene disegnato invisibile, e un
  segnaposto inserito al suo interno ereditava questa proprietà:
  impostato, ma non visibile. Nel punto trovato non restava allora nulla.
- **Un riconoscimento del testo che non poteva affatto funzionare
  risultava superato.** Se mancava il file linguistico o il motore di
  riconoscimento si interrompeva, il rapporto segnalava „immagine/i …
  verificate tramite riconoscimento del testo (0 riscontro/i)" – quindi un
  controllo mai avvenuto. Su una scansione questo è l'unico controllo
  esistente: un contratto con indirizzo leggibile nell'immagine di pagina
  valeva così come completo. Ora il rapporto dice che non è stato
  controllato nulla, e perché.
- **Il file linguistico veniva cercato nella cartella sbagliata.** Se
  nella propria cartella linguistica si trovavano lingue diverse da
  quella del documento, al motore di riconoscimento veniva presentata
  proprio questa cartella e falliva – benché la lingua giusta si trovasse
  accanto. Ora viene cercata la **lingua**, non la cartella.
- **L'avviso su testo non rimosso consigliava qualcosa che non esiste.**
  Rimandava a „Oscura come PDF" – che però crea una vista PDF di file
  *Office* e non è affatto disponibile per un PDF. Chi voleva seguire
  l'avviso cercava invano. Ora lì compare il pulsante che risolve la
  questione.
- **Nell'editor barre e segnaposto finivano accanto al punto
  contrassegnato.** Interessato era ogni PDF in cui una riga finisce con
  un trattino e la parola prosegue nella riga successiva – nelle
  scansioni ciò salta particolarmente all'occhio, perché i testi
  contrattuali sono composti con sillabazione continua. Le due metà di
  riga valevano come *una* parola, che si estende trasversalmente su
  tutta l'impaginazione, e ogni riquadro nelle sue vicinanze ereditava
  questa estensione. Il riconoscimento in sé non cambia con questo: il
  corpus di misura fornisce lo stesso risultato di prima.
- **L'editor avvertiva che il testo era „ancora nel documento", benché
  fosse stato rimosso.** Se la stessa parola compariva più volte su una
  pagina – nei contratti la regola –, il controllo automatico dopo ogni
  intervento segnalava un fallimento. Ora conta le occorrenze, invece di
  limitarsi a verificare se la parola si trova ancora da qualche parte. In
  caso di fallimento reale avverte come prima.
- **Il file di risultato si chiamava „_bereinigt" in ogni lingua.** Si
  intendeva sempre che il suffisso del nome seguisse la lingua
  dell'interfaccia – in inglese lo faceva davvero („_cleaned"), nelle
  restanti sedici lingue no. Chi usava il programma in finlandese
  otteneva „asiakirja_bereinigt.pdf". Ora il file si chiama
  „asiakirja_puhdistettu.pdf", in giapponese „書類_除去済み.pdf" e così
  via – ciascuno con la parola che la stessa interfaccia usa nel proprio
  messaggio di completamento. Chi ha impostato un proprio suffisso lo
  conserva.
- **„Gestisci lingue" si etichettava sempre in tedesco.** Nell'elenco
  delle 48 lingue dei documenti comparivano i nomi tedeschi, a
  prescindere da quale interfaccia fosse impostata: un utente finlandese
  leggeva „Chinesisch" (Cinese). Ora lì compare il nome nella propria
  lingua e dietro il nome originale – „Kiina (中文)". Il nome originale è
  intenzionale: chi riconosce la lingua dal proprio nome la trova anche
  quando la parola finlandese non gli dice nulla.

## 0.10.19 – 12 agosto 2026

### Migliorato

- **La voce nel menu contestuale ora parla la vostra lingua.** Finora vi
  compariva su ogni sistema il testo tedesco – anche su un Windows in
  inglese. Ora segue la lingua dell'interfaccia impostata, e chi cambia
  lingua vede subito la voce rinominata, senza reinstallare. (Windows; su
  macOS e Linux il nome del menu è anche un nome di file – questo arriverà
  più avanti.)
- **L'editor ricorda in quale vista avete lavorato l'ultima volta.** Chi usa
  l'anteprima di pagina la ritrova da sé al documento successivo – senza
  doverla attivare ogni volta. Chi non l'ha mai usata non nota nulla: viene
  ripristinata solo se il componente necessario è già caricato, e non viene
  mai scaricato apposta.

### Risolto

- **„MITARBEITER" (COLLABORATORI) sopra un elenco di nomi veniva oscurato
  esso stesso.** In elenchi del personale e organigrammi l'intestazione
  scompariva come presunto nome – si trova sopra una serie di nomi veri, e
  in maiuscolo il modello linguistico perde il suo segno distintivo. I nomi
  sottostanti continuano a essere trovati.
- **Quantità venivano scambiate per indirizzi.** In fatture, bolle di
  consegna ed elenchi di magazzino sparivano indicazioni come „3390
  Protokoll", „1030 Betrag" o „3390 Lager" come presunto CAP con località –
  un numero a quattro cifre assomiglia a un codice postale austriaco. Se
  dopo il numero segue una parola che l'applicazione riconosce come termine
  tecnico, reparto, attività o etichetta di campo, ora resta invariata. Le
  indicazioni di località reali non sono toccate, anche quando sono
  contemporaneamente una tale parola („4692 Ort"). Non risolto resta il
  caso in cui dopo il numero segue una parola del tutto comune („3390
  Regal") – per quello servirebbe un elenco dei codici postali.
- **La guida citava una voce di menu che non esiste.** Manuale, immagine e
  il messaggio al termine dell'installazione parlavano di „Dokument für KI
  bereinigen" (Ripulire documento per l'IA); la voce nel menu contestuale
  si chiama invece „Personenbezogene Daten entfernen" (Rimuovere dati
  personali). Chi seguiva la guida cercava invano. Tutti e tre i punti ora
  citano la voce di menu con il suo vero nome.
- **„Avvia con il sistema" non si lasciava disattivare.** Chi durante
  l'installazione aveva spuntato „Avvia con Windows" vedeva comunque nelle
  impostazioni una spunta vuota – e peggio: attivare e disattivare
  nell'applicazione restava senza effetto, il programma continuava ad
  avviarsi con Windows. Il motivo erano due punti in cui Windows cerca i
  programmi di avvio; l'applicazione ne conosceva solo uno. Ora contano
  entrambi, l'interruttore mostra lo stato reale e agisce in entrambe le
  direzioni. Considerato anche: chi disattiva la voce in Gestione attività
  ora lo vede nell'applicazione – e chi la riattiva lì annulla con ciò la
  disattivazione.
- **Intestazioni sopra elenchi di nomi venivano oscurate.** „TEILNEHMERLISTE
  WERKSTATTGESPRÄCH" (ELENCO PARTECIPANTI RIUNIONE OFFICINA) o
  „MITARBEITERÜBERSICHT INNENDIENST" (PANORAMICA PERSONALE UFFICIO INTERNO)
  sopra un elenco di persone sparivano come presunto nome. In maiuscolo il
  modello linguistico perde il suo miglior segno di riconoscimento, e in
  tedesco ogni sostantivo si scrive con l'iniziale maiuscola – „Teilnehmer­
  liste Werkstattgespräch" appare allora come „Anna Huber". I composti in
  `-liste`, `-dienst`, `-gespräch`, `-sitzung` e `-besprechung` ora restano
  invariati. Le parole di base da sole continuano a valere come nome:
  *Liste* e *Dienst* sono cognomi attestati, *Teilnehmerliste* non lo è.
- **Le indicazioni scritte in verticale ricevevano un segnaposto
  illeggibile.** Numeri di protocollo a margine pagina, sigle
  dell'incaricato accanto al margine di cucitura, intestazioni di tabella
  in verticale: tali indicazioni venivano sì trovate e rimosse, ma il
  segnaposto usciva trasversale rispetto al testo, compresso a uno o due
  punti e talvolta oltre il bordo del foglio. Ora segue il testo –
  verticale, in dimensione leggibile e nello stesso orientamento in cui si
  trovava l'indicazione. Lo stesso valeva per pagine ruotate in un secondo
  momento (testo scritto orizzontalmente con rotazione di pagina impostata,
  come la producono alcuni programmi di output); anche lì il segnaposto ora
  appare come si vede la pagina. „Sehr geehrte Frau Doktor Anneliese Berger"
  (Gentile Dott.ssa Anneliese Berger) dava come risultato solo „Anneliese"
  come nome – „Berger" restava nel documento. Lo stesso accadeva per ogni
  nome con secondo nome („Frau Anna Maria Berger"). Il motivo era la regola
  per il nome dopo un titolo di cortesia: aveva due posizioni di parola, e
  un titolo o un secondo nome ne consumava la prima. Con „Dr." non si notava
  mai – il punto interrompe la regola, e il modello linguistico catturava
  il nome intero. Ora i titoli vengono saltati senza consumare una
  posizione, e il nome può essere composto da tre parti. Un ruolo **dopo**
  il nome continua a non essere incluso: „Frau Anna Huber Geschäftsführerin"
  (Sig.ra Anna Huber Amministratrice) sostituisce il nome, non il ruolo.
