## 0.10.52-alpha.20260903 – 3. rujna 2026.

- Skup s više od četiri datoteke više ne zapinje nakon odgovora u nekoliko
  prozora pretpregleda. Ostali dokumenti i dalje se pripremaju u pozadini;
  nakon odgovora pripadajuća se datoteka sada pouzdano dovršava i oslobađa se
  sljedeće mjesto u skupu.
- Usklađivanje kratkih znakova tvrtke u PDF-ovima sada je ograničeno na tekst
  prepoznat na slikama. Stoga u običnom tekstu stranice dugačak, višeredni
  nalaz modela više ne uzrokuje dodatno zacrnjenje jednake pojedinačne riječi
  na drugom mjestu.

## 0.10.51-alpha.20260903 – 3. rujna 2026.

- Popis promjena sada se prikazuje na jeziku korisnika – na
  maskuro.com/neuigkeiten te u programu pod „Promjene”, kao i u prozoru
  „Što je novo” nakon ažuriranja. Dosad je ondje u svih osamnaest jezičnih
  inačica ispod prevedenog naslova stajao njemački tekst. Kad prijevod još
  nedostaje, odgovarajuća inačica ostaje na njemačkom umjesto da nestane;
  popis inačica svugdje je isti.

## 0.10.50-alpha.20260903 – 3. rujna 2026.

- Ponavljajući znakovi tvrtke u PDF-ovima čiste se dosljedno, čak i kad
  prepoznavanje teksta natpis na jednoj stranici čita drugačije ili
  posve izostavi okrugli znak. Izričito isključivanje u pregledu pritom
  ostaje obvezujuće i ne može ga poništiti nikakvo kasnije dovlačenje.
- Cijene bez oznake valute u skeniranim tablicama sada se u potpunosti
  zacrnjuju i kad zaglavlje tablice i vrijednosti leže u različitim
  preklapajućim PDF slikama. Količine, sati, težine i postoci ostaju
  netaknuti; daleko razmaknuti brojevi više se slučajno ne spajaju u
  iznos.
- Pretraga potpisa sada obuhvaća i dokazane slabe plave rukopisne
  natpise i uske crvene kratice potpisa. Točkasti dijagrami, mjerne
  krivulje, pečati, logotipi i široke crvene oznake obrade ostaju
  izuzeti iz ovog uskog dovlačenja.
- Zacrnjenja u zaokrenutim, zrcaljenim, uzduž nakošenim ili obrezanim
  PDF slikama sada pogađaju stvarni poligon slike. Tehničke uloge u
  stavkama usluga, stvarne vrijednosti vozila i guma te tehnička
  „Kompenzacija“ pritom se uže razgraničavaju od pogrešnih nalaza;
  izričito označene kontaktne uloge i telefonski brojevi ostaju
  zaštićeni.
- Vizualna provjera prije spremanja PDF-a više ne zamrzava prozor: kod
  velikih dokumenata s mnogo nalaza dosad je stajao nekoliko sekundi
  bez povratne informacije; sada napomena pokazuje da se provjerava, a
  prozor se dalje iscrtava.
- Vraćanje vrijednosti iz slike u uređivaču za doradu sada svaku
  izvornu sliku čita prepoznavanjem teksta samo jednom; dosad se to
  ponavljalo pri svakom daljnjem vraćanju za iste slike.
- Naknadno učitavanje Visoke razine i modela potpisa sada treba jedva
  imalo radne memorije: paket od 596 MB dosad se u cijelosti držao,
  provjeravao i raspakiravao u memoriji – preko gigabajta vrha u radu
  programa, na računalima s 8 GB trenutak u kojem je sve počelo
  zapinjati. Sada teče blokovima na disk i ondje se provjerava i
  raspakirava.
- Pretraga u uređivaču za doradu više ne zamrzava velike PDF-ove: prvo
  slovo u polju pretrage dosad je odjednom učitavalo sve stranice – kod
  200 stranica prozor je stajao dvije sekunde, i nakon svakog
  zacrnjenja ponovno. Stranice se sada čitaju po komadima; dotad u
  brojaču stoji „Čita se …“, rezultat je isti.
- Rasterizirane PDF stranice – nakon prepoznavanja teksta ili kad se
  tekst nije mogao čisto ukloniti – sada se spremaju znatno manje i bez
  gubitka slike: umjesto uvijek kao JPEG, svaka se stranica dodatno
  kodira i bez gubitaka, a manja inačica ulazi u datoteku. Očišćeni sken
  time se smanjuje s 248 na 48 KB, dokument za vježbu s prepoznavanjem
  teksta sa 913 na 702 KB; tekst ostaje oštar.
- Naknadno učitani modeli (Visoka razina, potpisi, lica, drugo
  prepoznavanje teksta) sada se nakon deset minuta bez čišćenja
  ponovno oslobađaju iz radne memorije. Dosad su ostajali učitani do
  kraja programa – tko je jednom koristio pretragu potpisa i Visoku
  razinu, trajno je zauzimao preko dva gigabajta. Sljedeće izvođenje
  ih ponovno učitava za jednu do dvije sekunde; statusni redak to
  javlja.
- PowerPoint: rodni nazivi izgleda i predložaka slajdova („Prazno“,
  „Naslovni slajd“) više se ne zamjenjuju kao podatak. „Prazno“ je i
  naziv mjesta i pogrešno se zacrnjivalo u svakoj njemačkoj i engleskoj
  prezentaciji; sada se čiste samo ručno dodijeljeni nazivi samih
  slajdova.
- U PDF-ovima izglađivanje redaka više ne uvlači u nalaz zaglavlje
  sljedećeg retka: broj sljedeće stavke popisa iza datuma vrijedio je
  kao telefonski broj, zaglavlje polja poput „Kod“ ili „Broj naloga“
  iza broja kao poštanski broj s mjestom, a redak mjesta ispod adrese
  udvostručavao je mjesto. Ispravan, kraći nalaz time je bio istisnut.
  Kroz 132 korpusna PDF-a od 24 dodatna nalaza izglađivanja ostaju dva
  stvarna; u praktičnom korpusu lažne uzbune padaju s 29 na 21 uz istu
  stopu nalaza.
- „Pretraži i zacrni mapu PDF-ova“ u uređivaču za doradu više ne
  blokira prozor: izvođenje radi u pozadini, napredak i gumb za
  prekid reagiraju, a izbornici ili kartice se više ne mogu koristiti
  usred napola gotove datoteke.
- Skenirane stranice s nalazima pri zacrnjivanju se sada ponovno pišu
  samo jednom umjesto dvaput: dosad je program ispunjavao okvire nalaza
  i okvire obrazloženja u dva prolaza, a drugi je dodatno komprimirao
  upravo nanovo spremljenu skeniranu sliku. To štedi vrijeme kod
  velikih skenova i sprječava gubitak kvalitete slike.
- Listanje, zumiranje i minijature u uređivaču za doradu reagiraju
  brže: svaka iscrtana stranica dosad je prolazila kroz PNG kompresiju
  i odmah natrag, samo da bi se prikazala – kod zaslona visoke
  razlučivosti to je bilo oko desetinke sekunde po stranici. Slika
  sada stiže izravno, piksel po piksel ista.
- Vizualna provjera prije spremanja PDF-a („probni ispis“) sada je oko
  tri puta brža, uz isti rezultat.
- Glavni prozor sada se pojavljuje još otprilike četvrtinu sekunde
  ranije: provjera je li prepoznavanje teksta spremno na ovom računalu
  odvijala se pri izgradnji prozora – na Macu uključujući probni upit
  sistemskom prepoznavanju – a stranica postavki dodatnih komponenata
  ondje je ispitivala stanje svih 48 jezika. Oboje se sada odvija u
  pozadini odnosno tek kad se popis jezika stvarno otvori; dotad stoji
  „Provjerava se prepoznavanje teksta …“.
- Nakon pretrage potpisa program zauzima oko 300 MB manje radne
  memorije: model prepoznavanja dosad je ležao dvostruko u memoriji –
  jednom radi provjere izvornosti, jednom radi računanja. Provjerava se
  i dalje, samo bez druge kopije.
- Prepoznavanje teksta u PDF-ovima znatno je brže: za svako zaglavlje
  polja na stranici („Datum rođenja:“, „Porezni broj:“) dosad se za
  svaku vrstu podatka slala vlastita proba kroz prepoznavanje – na
  svakoj stranici iznova, čak i kad je isto zaglavlje već stajalo deset
  stranica prije. Odgovor se sada pamti; dvostranični troškovnik time
  je postavljao 324 upita, sada samo različite. Nalazi su isti.
- Velike tablice ponovno se čiste u sekundama umjesto minutama: u
  anonimizirajućem načinu rada – zadanom – usklađivanje već poznatih
  vrijednosti sa svakom sljedećom stanicom postajalo je sporije, jer se
  međuspremnik kod svakog nalaza odbacivao i iznova gradio. 5.000
  stanica trebalo je za to oko 18 sekundi, sada pola sekunde; rezultat
  je znak po znak isti.
- Glavni prozor pojavljuje se još znatno brže: popis zemalja u
  postavkama pri izgradnji prozora dovlačio je cijelu biblioteku
  prepoznavanja u prvi plan – oko 0,7 sekundi na Macu, na Windowsu
  razmjerno više – iako su za to potrebni samo nazivi zemalja. Popis
  sada dolazi iz lakog kataloga; biblioteka se učitava kako je i
  predviđeno u pozadini, dok prozor već stoji. To vrijedi i nakon
  svake promjene jezika ili izgleda, koja ponovno pokreće program.
- Dokumentni laboratorij sada zaglavlja polja odsječena na rubu,
  lokalne sjene vrijednosti i jaka obrezivanja skena vodi potpuno kroz
  PDF, DOCX i ODT spremnike. Matrica obuhvaća 680 datoteka iz 40
  obitelji dokumenata i 17 osi spremnika. Maskuro u novim kao i u
  potpunim osnovnim i obilježnim profilima uklanja sve ciljane
  podatke, bez izmjerene lažne uzbune, oštećene vrijednosti za
  očuvanje ili prekida.

- Višestruko korišteni skenovi sada se provjeravaju i čiste preko
  svakog vidljivog položaja: dokumentni laboratorij dijeli isti
  slikovni objekt preko različitih stranica, veličina i zaokreta u
  PDF-u te višestruko upućuje na isti dio slike u DOCX-u i ODT-u.
  Tehnički ODT nazivi okvira poput „Sken obrasca mali položeno“ više se
  ne smatraju osobom; slobodna imena i mjesta sličnog početka ostaju
  zaštićena. Opće nagađanje obrasca završnog PDF prolaska stranica na
  već samostalno pročitanoj slikovnoj površini više ne može stvoriti
  veliki pogrešan nalaz adrese. 120 novih spremnika u osnovnom i
  obilježnom profilu postiže svih 813 odnosno 840 ciljanih podataka
  bez lažne uzbune, povrede očuvanja ili prekida; potpuna obilježna
  provjera od 800 datoteka potvrđuje 5.600/5.600.

- Njemački OCR laboratorij sada obuhvaća 560 skenova iz 40 obitelji
  dokumenata. Nove varijante odsijecaju rubove zaglavlja polja i
  stranice ili postavljaju sjenu izravno preko vrijednosti. Maskuro
  pritom štiti i imena, adrese, datume rođenja, medicinske šifre i
  označene identifikacijske brojeve s djelomično oštećenom oznakom.
  Istodobno se ostaci polja obrazaca, službeni naslovi te stručni
  pravni i informativni pojmovi više ne zamjenjuju kao osobe ili
  mjesta. Potpuni osnovni i obilježni profili postižu 3.794/3.794
  odnosno 3.920/3.920 ciljanih podataka bez izmjerene lažne uzbune ili
  prekida.

- Automatski odabir PDF slika više ne uklanja velike proizvodne
  fotografije, energetske naljepnice i nizove portreta samo zato što
  počinju u gornjem rubu stranice. Stvarne plosnate slike zaglavlja i
  podnožja te zaglavlja pisma koja počinju na rubu lista i dalje
  otpadaju. U imenicima djelatnika imena se sada prepoznaju iz
  strukturno ponovljenih unosa i kad je vidljivi naslov dokumenta samo
  slika. Prepoznavanje više nije skrojeno na dvije konkretne riječi
  uloge i kraticu „DW“: jedna do četiri prelomljene uloge te
  „Durchwahl“, „Nebenstelle“, „Ext.“ i „Extension“ izvode se iz
  zajedničkog oblika. Uloge i naslovi odjeljaka ostaju netaknuti, čak i
  kad jezični model nakon razrješenja preklapanja ostavi samo pridjev
  uloge. Vodoravni rasteri uloga više se pogrešno ne smatraju stupcima
  imena. Zalijepi li OCR stranice više kartica u iznimno široku riječ s
  unutarnjim velikim slovima, uska lokalna protuprovjera razdvaja
  stvarne okvire riječi; time ne ostaje ni pojedinačno ime ni širok
  pogrešan zacrnjeni pojas. Ponovljeni višeredni logotipi tvrtki
  zacrnjuju se prema već potvrđenom identičnom slikovnom predlošku i na
  stranicama bez upotrebljivog OCR teksta te uz odstupanje položaja do
  dva piksela; kraća lokalna drugo čitanja OCR-a pritom više ne smiju
  veće područje zaglavlja dodati kao izmišljeno ime. Brojevi stranica
  ispred zaglavlja pisma tvrtke više ne pripadaju nazivu organizacije,
  stvarni nazivi marki koji počinju brojem ostaju zaštićeni. Više
  izmjerenih riječi proizvoda, struke i obrasca više se ne predlažu kao
  osobe.

- Pretraga potpisa u PDF-ovima sada radi tek nakon OCR čišćenja slika,
  posjećuje i stranice bez uobičajenog tekstualnog nalaza te ispravno
  vraća okvire nalaza zaokrenutih stranica u prostor dokumenta. Guste
  proizvodne fotografije više se ne zacrnjuju kao potpis. Iznad
  jednoznačno označenih polja potpisa uski rezervni put crte zatvara
  tanke praznine modela; prazne linije s otisnutim datumom ga ne
  pokreću. Čisti skenovi isključivo s OCR/potpis nalazima u ovoj fazi
  više se ne prekidaju zbog tek u tekstualnoj grani učitanog zacrnjivača
  slike.

- Mnogo istodobno otvorenih dokumenata ostaje razlučivo u uređivaču za
  doradu: kartice se više ne smanjuju do gole tri točke, a gumb popisa
  desno prikazuje sve pune nazive datoteka jedan ispod drugoga. Kartice
  se mogu premjestiti povlačenjem i ukloniti svojim križićem iz istog
  popisa kao u glavnom prozoru; nespremljen rad se pritom i dalje
  najprije razjašnjava. Desni klik uz to nudi „Zatvori“, „Zatvori druge
  kartice“ i „Zatvori kartice desno“.

- Kratkotrajno Windows zaključavanje antivirusnim programom ili
  indeksom pretrage više ne uzrokuje da gotovo učitana mapa jezičnog
  modela odnosno rječnika propadne s „Pristup odbijen“ pri završnom
  postavljanju. Maskuro sada tu posljednju promjenu mape kratko vrijeme
  pokušava ponovno.

- Njemački dokumentni laboratorij sada spremnike provjerava i s
  promjenjivim zaokretom PDF stranica, neovisno zaokrenutim PDF
  slikama te skaliranim i obrezanim tabličnim slikama u DOCX-u i
  ODT-u. Vrijednosti polja u vidljivo zaokrenutim slikama ponovno se
  potpuno prepoznaju, tehnički nazivi stupaca više se ne zamjenjuju kao
  mjesta, a imena sa zajedničkim prezimenom više se ne razbijaju
  provjerom dosljednosti na dvostruke djelomične nalaze. Matrica
  udvostručena na 320 datoteka uz uključeno prepoznavanje datuma,
  novca i medicine postiže 2.240/2.240 ciljanih podataka bez izmjerene
  lažne uzbune ili prekida.

- Višestranični PDF-ovi sa slikama, mješoviti tekst/slika PDF-ovi i
  skenovi ugrađeni u DOCX ili ODT sada se provjeravaju u vlastitom
  laboratoriju od 160 datoteka kroz svih 40 njemačkih obitelji
  dokumenata. Tehnički ODT nazivi okvira i označeni kodovi uređaja
  više se ne zamjenjuju kao mjesta; stvarna imena, mjesta i adrese u
  istim strukturama ostaju zaštićeni. Uz uključeno prepoznavanje
  medicine ili novca dodatno se u potpunosti uklanjaju izravno
  slijedeća doza odnosno interval plaćanja. Izvođenja spremnika,
  tekstualnog osnovnog, tekstualnog obilježnog i OCR obilježnog profila
  zajedno postižu svoje pune vrijednosti bez izmjerene lažne uzbune ili
  prekida.

- Sigurnosna provjera prije spremanja sada upadljiva PDF mjesta
  prikazuje kao pojedinačno odabirljiv popis. „Provjeri u uređivaču“
  otvara točno odabranu stranicu i označava područje; preklapajući
  djelomični nalazi na istom mjestu pojavljuju se samo jednom. Novi
  tekstovi sučelja u potpunosti su dostupni na svih 17 prevedenih
  jezika sučelja.

- Markdown datoteke pri zamjeni zadržavaju svoju sintaksu poveznica,
  isticanja i fusnota. Maskuro za to čita jednako dugu inačicu bez
  Markdown oznaka; donje crte u adresama e-pošte, zvjezdice množenja i
  obični poveznici bez osobnog podatka ostaju nepromijenjeni.

- Više rukom pisanih unosa na istoj PDF stranici sada se traži u do tri
  prolaza. Već pronađeni potezi se skrivaju samo u radnoj slici, kako
  više ne bi istiskivali slabije potpise; na zaokrenutim stranicama
  površine zacrnjenja ponovno završavaju na vidljivom mjestu nalaza.
  Slikovna ispunjenja ranijih sigurnosnih faza ostaju sačuvana pri
  naknadnom zapisivanju.

- „Vrati sve postavke na početno“ sada obuhvaća i „Tekst na slikama“.
  Nije li OCR komponenta dostupna, prekidač ostaje tehnički isključen,
  bez pogrešnog označavanja kao odstupanje od stanja isporuke.

- Veliki slikovni ulomci na gornjem rubu stranice više se ne smatraju
  zaglavljem samo zbog svog položaja. Time ostaju sačuvani osobito
  slikovno utemeljeni opisi artikala i sadržaj tablica. Novo prepoznati,
  vrsti točno odgovarajući nalazi e-pošte i obrazaca uz to se više ne
  filtriraju iz završne vizualne provjere ni na već provjerenoj
  slikovnoj površini.

- Tehnički retci pozicija i artikala u klimatizacijskim i električnim
  ponudama uže se razlikuju od osoba, mjesta i organizacija. To se
  odnosi među ostalim na vrste kabela, AC napajanje, brojeve pozicija
  te verzalne kodove proizvoda; stvarna imena i adrese ostaju
  zaštićeni.

- Provjera stvarnih očišćenih PDF-ova više ne zamjenjuje dijelove cijena
  poput `1 699,59` s telefonskim brojevima i iz potpunog datuma poput
  `08.05.2025` više ne izrezuje navodni podatak kartice. Imena iza
  oslovljavanja završavaju na prijelomu retka umjesto u sljedećoj
  ulici; nazivi mjesta u nazivima datoteka privitaka ograničavaju se
  na stvarno mjesto. Boje vozila, tehničke statusne vrijednosti,
  oznake djelatnosti i pravni oblici proizvoda također ostaju
  sačuvani. Oštećena čitanja rezerviranih mjesta poput `|PLLZ` kod
  drugog OCR prolaza više se ne tretiraju ponovno kao osobni podatak.

- Bočno spremljene PDF slike pri završnoj vizualnoj provjeri dobivaju
  dodatan pogled u svom nepromijenjenom položaju slike. On smije
  naknadno zacrniti isključivo vrijednosti koje je Maskuro na istoj
  stranici već sigurno prepoznao. Tako se primjerice mali zaokrenut
  pečat adrese potpuno prekriva, bez izmišljanja novih riječi iz
  natpisa slika ili tehničkih crteža kao osobnih podataka.

- U OpenDocument tekstovima inicijali autora bilješke (komentara) sada
  se prazne zajedno s autorom. LibreOffice ih uz puno ime odlaže kao
  vlastitu kraticu i prikazuje baš nju na rubu stranice; dosad je ondje
  i dalje stajalo „SO“, dok je „Sieglinde Ortner“ pored odavno bilo
  rezervirano mjesto. Prazni se samo kad je autor stvarno zamijenjen –
  bilješka odjela zadržava svoju oznaku.

- U talijanskim poslovnim pismima uobičajene fraze na početku rečenice
  više se ne smatraju imenom ili mjestom: „Restiamo a disposizione“,
  „Rimaniamo“, „Attendiamo“, „Alleghiamo“, „Comunichiamo“ i „Auguriamo
  buon lavoro“ dosad su ostajale zapele kao navodna osoba ili oznaka
  mjesta. Stvarna imena na istom mjestu („Rossi Mario“) i dalje se
  prepoznaju.

- Dvostupčani skenovi sada štite označene identifikatore i podatke o
  mjestu i kad prepoznavanje teksta najprije isporuči sva zaglavlja
  polja, a zatim sve vrijednosti. Pridruživanje prati vidljivi piksel
  redak i radi i kod stranica zaokrenutih za 90 stupnjeva. Usko
  razdvojeni dijelovi identifikatora putovnice ili ugovora zacrnjuju se
  zajedno; označeni datumi rođenja, ICD i PZN šifre također su
  pokriveni, sljedeće imenice ostaju netaknute. Kratka imena i
  korisnička imena zaštićena su na točnim poljima; e-mail adrese
  rastavljene na više OCR riječi samo uz usku susjednost i potpunu
  gramatiku e-pošte. Ispravak zamjenjivih znakova vezan uz polje te
  lokalno dočitavanje još praznog osobnog polja zatvaraju oštećene i
  zaokrenute skenove, bez proširivanja stručnih polja ili već zauzetih
  vrijednosti. Sigurnosni rubovi prate veličinu riječi, a obilježni
  profil zahvaća i neposredno susjedne jedinice doze i intervale
  plaćanja. Blago nakrivo uvučeni obrasci geometrijski se vraćaju iz
  više jednako usmjerenih OCR redaka; šum zaokruživanja ili proturječni
  svjedoci nisu dovoljni. Kratki prefiksi slova ostaju sačuvani ispred
  identifikatora s crticom, a potpun označen nalaz adrese zamjenjuje
  samo svoj istovrsni djelomični nalaz ulice. Pogrešno pročitano
  zaglavlje polja uloge otpada isključivo u stupcu obrasca zauzetom s
  najmanje tri poznata zaglavlja; nazivi u razgovorima ostaju
  zaštićeni. Uska obrezanost ruba i lokalna preeksponiranost s
  dijagonalnim odsjajem svjetla dopunjuju slikovnu matricu. Nalazi
  osoba, mjesta i tvrtki koji sežu preko više redaka obrasca u
  višestruko zauzetom stupcu polja ograničavaju se na odgovarajuću
  vrijednost. Tehnička vrijednost pozicije otpada samo uz zaglavlje
  pozicije i odgovarajući oblik oznake; stvarna imena ostaju
  zaštićena. I vrijednosti e-pošte prekinute odsjajem svjetla uklanjaju
  se iza izričitog zaglavlja polja e-pošte s uskim, susjedstvom
  ograničenim rubom slike. Dva para polje-vrijednost istog vidljivog
  retka sada se procjenjuju neovisno; vrijednosti na dubljoj osnovnoj
  liniji povezuju se tek nakon tri podudarna geometrijska svjedoka.
  Time identifikacijski brojevi, datumi rođenja i adrese ostaju posve
  zaštićeni i u gustim rasporedima obrazaca. Ulica, poštanski broj i
  mjesto spajaju se isključivo unutar istog polja adrese i uz
  odgovarajuću poštansku gramatiku. Usko ocrtana stručna polja za
  pomagala/alate i stanje zuba više ne stvaraju lažne uzbune mjesta ili
  imenika; stvarna imena i slično nazvana polja ostaju zaštićeni.
  Njemački dokumentni laboratorij sada obuhvaća 440 skenova i postiže
  2.981/2.981 u osnovnom profilu te 3.080/3.080 u obilježnom profilu.
  Svih jedanaest slikovnih mutacija i svih 40 obitelji dokumenata
  postižu 100 posto, i dalje bez izmjerene lažne uzbune, povrede
  očuvanja ili prekida.

- PDF tekstualni slojevi s izgubljenim razdjelnicima stanica sada
  ograničavaju nalaze organizacija, adresa i mjesta prema ponovljenoj
  strukturi polje-vrijednost. Zaglavlja polja ispred vrijednosti tvrtke
  i tehničke strelice poput `=>` ili `->` više ne pripadaju nalazu.
  Dodatni prikaz za meke prijelome redaka više ne smije proširiti
  nalaze pravnog oblika i mjesta preko više redaka tablice; već potpuna
  adresa završava prije sljedećeg zaglavlja polja zajedno s
  vrijednošću. Završno izvođenje preko svih 1.600 TXT, HTML, PDF i
  DOCX dokumenata uklanja 10.840/10.840 ciljanih podataka uz nula
  lažnih uzbuna, nula povreda očuvanja i nula prekida.
