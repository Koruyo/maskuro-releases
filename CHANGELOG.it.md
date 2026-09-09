# Modifiche

Ciò che cambia da versione a versione – descritto dal punto di vista
dell'applicazione, non dei suoi meccanismi interni. Chi vuole sapere *di
cosa* è fatta trova la risposta in [LIZENZEN.md](LIZENZEN.md); qui sta
scritto cosa cambia per il lavoro con essa.

La numerazione segue la convenzione consueta: il **primo** numero cambia
quando qualcosa non funziona più come prima, il **secondo** per nuove
funzionalità, il **terzo** per correzioni di errori.

---

## 0.10.52-alpha.20260903 – 3 settembre 2026

- Un lotto di più di quattro file non rimane più bloccato dopo più risposte
  nelle finestre di anteprima. Gli altri documenti continuano a essere
  preparati in background; dopo una risposta, il file corrispondente viene
  ora completato in modo affidabile e si libera il posto successivo nel lotto.
- Il confronto dei loghi aziendali brevi nei PDF è ora limitato al testo
  riconosciuto nelle immagini. Nel normale testo della pagina, una lunga
  corrispondenza del modello estesa su più righe non fa quindi più oscurare
  anche una singola parola identica in un altro punto.

## 0.10.51-alpha.20260903 – 3 settembre 2026

- L'elenco delle modifiche viene ora visualizzato nella lingua dell'utente –
  su maskuro.com/neuigkeiten e nel programma alla voce «Modifiche», nonché in
  «Novità» dopo un aggiornamento. Finora, in tutte e diciotto le versioni
  linguistiche appariva testo in tedesco sotto un'intestazione tradotta. Se
  una traduzione manca ancora, la versione interessata rimane in tedesco
  invece di scomparire; l'elenco delle versioni è uguale ovunque.

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
