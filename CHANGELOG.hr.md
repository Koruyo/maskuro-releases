

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

## 0.10.44-beta.1 – 1. rujna 2026.

- Paketna izgradnja sada stvara zasebne izlaze za Windows x64 i ARM64, macOS
  na Apple Siliconu i Intelu te Linux x64 i ARM64. Nazivi paketa, izbor
  ažuriranja i objave razlikuju arhitekturu; objava ostaje blokirana dok god
  nedostaje jedan od šest ciljeva ili njegov dokaz o ovisnostima. Linux ARM64
  zbog Qt-a zahtijeva najmanje glibc 2.39. Za sada su na pravom hardveru u
  potpunosti prihvaćeni samo Windows x64 i macOS na Apple Siliconu; ostali
  arhitekturni paketi jasno su označeni kao predinačice za isprobavanje, a ne
  za produktivnu uporabu.

- Kod više datoteka prepoznavanje sada nastavlja raditi dok pregled čeka na
  provjeru. Do tri pripremljena pregleda prikazuju se jedan za drugim;
  istovremeno se i dalje računa samo jedan dokument, a rezultatna datoteka
  nastaje tek nakon njegovog odobrenja. Trajna iznimka odabrana u pregledu
  vrijedi i za već pripremljene sljedeće dokumente.

- Redakcijski certifikati sada se u bilo kojem trenutku mogu izravno u
  izborniku Datoteka provjeriti nasuprot zacrnjenom dokumentu. Maskuro pritom
  razlikuje odgovarajuću potpisanu datoteku, odgovarajući ali nepotpisan
  dokaz, nevažeći potpis i dokument koji ne pripada certifikatu. Za protuprovjeru
  nije potreban ni licenca ni izvorni korisnički račun operacijskog sustava.
  Za automatska mjesta provjere na raspolaganju je ista usporedba putem
  `--zertifikat-pruefen`; povratni kodovi razlikuju podudaranje, korisničku
  pogrešku i nevažeći dokaz.
  Protuprovjera dodatno uspoređuje ugrađeni Maskuro ID s certifikatom; slobodno
  upisan strani ID time se otkriva i kod nepotpisanog dokaza.
  Kod važećeg potpisa nalaz provjere dodatno prikazuje obrađivača kojeg je
  aktivirala uprava, s korisničkim računom operacijskog sustava, tehničkim ID-om
  računa i platformom. Nepotvrđeni podaci iz nepotpisanih ili nevažećih dokaza
  se ne prikazuju.

- Novi njemački dokumentni laboratorij stvara 160 potpuno sintetičkih
  TXT, HTML, PDF i DOCX dokumenata iz deset područja i četiri strukturne
  varijante. Manifest sada izričito razlikuje podatke koji moraju nestati od
  stručnih tekstova odnosno stvarnih oznaka koje moraju ostati sačuvane;
  obitelj dokumenta, mutacija i javni strukturni izvor su sljedivo pohranjeni.

- Njemački dokumentni laboratorij proširen je na 280 datoteka, sedam
  strukturnih oblika, 1.540 ciljanih podataka i 1.036 sidra za očuvanje. Novo
  se provjeravaju numerirani obrasci, zagrađena PDF/maskirana polja i tehnička
  `=>` pridruživanja. Prošireno potpuno stanje postiže u TXT, HTML, PDF i
  DOCX-u po 100 posto uz nula lažnih uzbuna. Zagrađena datumska polja i polja
  s brojevima oznaka, strelice-razdjelnici i izričito označeni sklopovi sada
  se strukturno prepoznaju.

- Drugo proširenje laboratorija podiže broj na 400 dokumenata, deset
  strukturnih oblika, 2.200 ciljanih podataka i 1.480 sidra za očuvanje.
  Vrijednosti u obliku JSON ključ-vrijednost, YAML popisi i verzalna polja
  obrazaca zajedno s dosadašnjim stanjem postižu 100 posto uz nula lažnih
  uzbuna. Citirani datumi rođenja i brojevi oznaka te izričito označene uloge
  poput osiguranih, prijavljenih, obveznika prijave i ovlaštenih zastupnika
  sada se prepoznaju i u tim izvoznim oblicima.

- Zaseban OCR način rada njemačkog dokumentnog laboratorija dodatno stvara
  200 čistih slikovnih skenova iz svih 40 obitelji. Čiste, niskokontrastne,
  nisko razlučene, JPEG-artefaktima opterećene i za 90 stupnjeva zakrenute
  stranice mjere se naknadno točnim pikselnim okvirima, bez promjene
  usporedivog osnovnog stanja od 1.600 tekstualnih datoteka. Manifest odvaja
  uklopive značajke datuma, novca i medicine od osnovnog profila i poznaje
  potvrđena OCR čitanja, a da ih ne broji kao dodatna ciljana mjesta. Mjerenje
  se raščlanjuje po mutaciji i obitelji dokumenta. Uske granice polja
  sprječavaju, između ostalog, da `Az` u nazivu mjesta `Graz` zacrni sljedeći
  datum kao broj spisa; trenutačna osnovna matrica radi uz nula lažnih uzbuna
  i nula prekida.

- Pet daljnjih njemačkih obitelji dokumenata za račun/otpremnicu,
  banku/kredit, najam/upravu zgrade, školu/visoku školu i logistiku/carinu
  proširuju laboratorij na 600 datoteka s 3.520 ciljanih podataka i 2.360
  sidra za očuvanje. Uski put PDF tablica koristi izričito zaglavlje
  `Feld Angabe` kada tekstualni sloj izgubi razdjelnike ćelija; novi izbor
  `--familien` ubrzava djelomična mjerenja. 200 novih datoteka postiže
  1.320/1.320 uz nula lažnih uzbuna i nula prekida.

- Osiguranje/šteta, rad/plaća, medicina/laboratorij, vozilo/servis i
  tehnika/održavanje proširuju njemački dokumentni laboratorij na 800
  datoteka s 4.960 ciljanih podataka i 3.200 sidra za očuvanje. Uski
  označeni identifikatori polica, pacijenata, ispitivača i vozila te nova
  polja uloga, adresa i organizacija se prepoznaju. Nova djelomična matrica i
  potpuna matrica postižu 100 posto uz nula lažnih uzbuna i nula prekida u
  TXT, HTML, PDF i DOCX-u.

- Gradnja/natječaj, energija/okoliš, udruga/društvo, komunikacija/kalendar i
  hotel/priredba podižu njemački dokumentni laboratorij na 1.200 datoteka s
  7.920 ciljanih podataka i 4.800 sidra za očuvanje. Nova polja uloga,
  tvrtki, adresa, registra, dodjele, rezervacija i korisničkih računa
  prepoznaju se i u svim izvoznim oblicima. Brojevi brojila ostaju sačuvani
  kao stvarne oznake. Djelomična i potpuna matrica postižu 100 posto uz nula
  lažnih uzbuna i nula prekida.

- Ugostiteljstvo/dostava, ljekarna/recept, pogrebne usluge/groblje,
  sport/članstvo i nekretnine/posrednik proširuju njemački dokumentni
  laboratorij na 1.400 datoteka s 9.360 ciljanih podataka i 5.640 sidra za
  očuvanje. Prepoznaju se nove uloge osoba, polja adresa i brojevi upitnih
  naloga. Označeni nazivi tvrtki s pravnim oblikom ostaju potpuno zaštićeni i
  preko automatskog prijeloma retka; dobne skupine i stručna zanimanja se
  više ne zamjenjuju pogrešno. Djelomična i potpuna matrica postižu 100 posto
  uz nula lažnih uzbuna i nula prekida.

- Zubno liječenje, autoškola, vatrogasci/intervencija, energetska zajednica i
  paket-putovanje proširuju njemački dokumentni laboratorij na 1.600
  datoteka s 10.840 ciljanih podataka i 6.440 sidra za očuvanje. Nove uloge,
  polja adresa te oznake liječenja, obrazovanja, intervencije, energije i
  ugovora o putovanju strukturno se prepoznaju. Nova djelomična matrica od
  200 datoteka postiže 1.480/1.480; potpuna matrica postiže 10.840/10.840.
  Obje ostaju uz nula lažnih uzbuna i nula prekida.

- Potpuno mjerenje dokumentnog laboratorija smanjilo je zahvaljujući uskim
  službenim stvarnim oblicima i strukturnim pravilima nepotrebne zamjene sa
  68 na 0, izričito izmjerene povrede očuvanja s 23 na 0 i prekide s 3 na 0.
  Stopa pronalaska istovremeno je porasla s 91,1 na 100,0 posto; TXT, HTML,
  PDF i DOCX postižu po 100 posto. Opća zaglavlja tablica poput `Feld`
  ograničavaju se samo u potvrđenom slijedu `Feld`/`Angabe`; istoimeno
  prezime ostaje zaštićeno. Sudski brojevi spisa sa slovom na kraju, polja sa
  znakom jednakosti, `Geburtsdatum des Kindes` i više označenih pojedinačnih
  imena u istom retku potpuno se prepoznaju. Word tablice i polja u
  prethodnom retku koriste svoje zaglavlje polja kao privremeni kontekst
  prepoznavanja; označene PDF adrese ostaju potpuno zaštićene i kod
  prijeloma retka uvjetovanog rečenicom.

- Njemačka polja osobnih obilježja, zanimanja i medicine sada rade i s
  Windows prijelomima redaka. Jednoslovne oznake spola poput
  `Geschlecht`/`w` zaštićene su u obliku prethodnog retka. Stvarna polja
  `Artikel-PZN` s druge strane ne pokreću ni nalaz šifre lijeka ni nalaz
  osobe; stvarni podaci PZN, ICD i ATC ostaju prepoznati.

- Njemačka polja obrazaca i brojeva su precizniji: „DW.“ sada radi i prije
  mekog prijeloma retka, izričito označena imena se uklanjaju i kad su pisana
  malim slovima, a čisto brojčani brojevi spisa dodjeljuju se svojoj pravoj
  vrsti broja oznake. Obrnuto, slučajno Luhn-valjani broj računa, dokumenta
  ili artikla više se ne smatra kreditnom karticom. Sintetički HTML i PDF
  izlazni uzorci potvrđuju uklanjanje i očuvanje u gotovom dokumentu.
  Brojevi oznaka i korisnička imena prepoznaju se dodatno kad se njihova
  oznaka nalazi u neposredno prethodnom retku tablice ili obrasca; stvarni
  brojevi dokumenata ostaju vidljivi i u tom obliku.

- Lozinke se sada prepoznaju i iza samostalnog zaglavlja polja u prethodnom
  retku. Završni posebni znakovi poput `!` ili `#` pritom u potpunosti
  pripadaju zaštićenoj vrijednosti. Proizvodni i artikl-PIN-ovi obrnuto se
  više ne maskiraju kao PIN kartice; izričita polja `PIN` i `Karten-PIN`
  ostaju zaštićena.

- Vrijednosti obrazaca pisane malim slovima kod jednoznačnih njemačkih
  polja adrese i `PLZ/Ort` sada se izlaze kao adresa odnosno poštanski broj s
  mjestom umjesto samo kao opće mjesto. Isto tako vrijednosti tvrtki pisane
  malim slovima poput „beispiel service“ ostaju potpuno zaštićene iza polja
  tvrtke, bez odsijecanja završne riječi kao navodnog sljedećeg zaglavlja
  polja.

- Pomoć, ČPP, tekst o zaštiti podataka i web-stranica sada zajedno
  objašnjavaju dokaz podrijetla: neutralni Maskuro ID u dokumentu, izborno
  pridruživanje stvarnom korisničkom računu operacijskog sustava samo u
  lokalnom zapisniku provjere, promjena korisnika na Windowsu/macOS-u/Linuxu
  te informativna vrijednost SHA-256 i potpisa.

- Slikovno utemeljeni tehnički troškovnici sada se čiste suzdržanije.
  Jednoznačne stvarne riječi poput „Abbruchhämmern“, „Deckungsrücklass“,
  „Positionsnummern“, „Einbauplatine“ ili „Terminsituation“ te OCR oblici
  razdvojeni usred riječi više se ne smatraju osobom ili mjestom. Stvarna
  ponuda općinskog ureda time je smanjena sa 140 na 90 jednoznačnih zamjena,
  bez stvaranja novih nalaza; imena poput Schneider, Lang, Bauer i Hahn
  ostaju izričito zaštićena.

- Otklonjene su daljnje lažne uzbune iz stvarnih ponuda: „Digital signiert“
  više ne sadrži navodnu osobu, BIC se prepoznaje i bez dvotočke iza svoje
  oznake, `15000 Alternativ` se ne smatra poštanskim brojem s mjestom, a
  EU citat „(VO (EG) 715/2007“ ne stvara organizaciju. Ponuda za
  fotonaponski sustav time je smanjena sa 26 na 16 pojavljivanja zamjena;
  stvarna imena, mjesta i podaci o računu ostali su sačuvani.

- U pregledima djelatnika kratica za zamjenika „Stv.“ i samostalno odvojen
  naslov područja „FACILITY“ više se ne zamjenjuju kao osobno ime. Stvarna
  13-stranična protuprovjera smanjena je s 878 na 875 zamjena; imena,
  interni brojevi i naziv tvrtke ostali su zaštićeni.

- Očišćene PDF, OpenDocument i Office datoteke sada dobivaju neutralnu
  oznaku `MASKURO-…` u svojim svojstvima dokumenta. Izvještaj provjere i
  potpisani zapisnik provjere vode istu oznaku te SHA-256 vrijednosti izvora
  i rezultata; redakcijski certifikat preuzima oznaku iz gotove datoteke. Ime
  korisnika se dodaje i dalje samo ako uprava izričito uključi postojeće
  polje korisnika.

- Glavni prozor i postavke su mirnije raspoređeni: Spremi, Kopiraj, Detalji,
  ključni pokazatelji i brisanje profila prepoznavanja pojavljuju se tek kad
  je odgovarajuća radnja moguća. Tehničke OCR jezične kratice i dugi primjeri
  stoje po potrebi u tekstu napomene umjesto trajno na radnoj površini.
  Stranica prepoznavanja bolje se prilagođava užim prozorima, bez odsječenih
  objašnjenja ili vodoravnih traka za pomicanje; upozorenje o čistom tekstu u
  popisu zamjena pritom ostaje vidljivo.

- Prepoznavanje sada obuhvaća daljnje njemačke i međunarodne slučajeve
  kontakata: telefonski brojevi se sada provjeravaju za sve odabirljive
  jezične regije, mađarske i hrvatske ugovorne uloge potpuno obuhvaćaju i
  prezimena istovjetna zanimanju, a numerirani popisi rezervnih dijelova/
  materijala više ne izazivaju lažnu uzbunu za osobu zbog „Mutter / Flach“.
  Polja osoba s očito brojčanom stvarnom vrijednošću se ne preuzimaju kao
  ime; strojno čitljiva zona putovnice (MRZ) se dodatno može zajedno
  uključiti i isključiti preko skupine „Identifikatori“.

- Tvrtke bez pravnog oblika bolje se razlikuju od osoba iza dvoznačnih polja
  poslodavca: imena poput „Huber Handel“, „Müller Logistik“ ili
  „Kowalski Handel“ potpuno se prepoznaju kao tvrtka, dok „Arbeitgeber:
  Bauer Anna“ i dalje ostaje osobno ime. Automatski odabir zemlje kod
  francuskih dokumenata i dalje uzima u obzir cijelo francusko jezično
  područje uključujući Luksemburg.

- Prepoznati potpisi i osobni podaci unutar slike dosad su uvijek bili
  prekriveni crnim pravokutnikom – čak i kad je za zacrnjenja bila
  postavljena druga boja ili uzorak poput „Duga“. Ta područja slike sada
  također preuzimaju odabrani prikaz zacrnjenja; neprozirna površina i dalje
  se izravno upisuje u piksele slike.

- Englesko prepoznavanje ponovno je izmjereno i ciljano poboljšano na
  jedanaest ručno prevedenih stvarnih dokumenata: status inventara, tehnička
  polja ponuda i web-trgovine te uloge u imenicima djelatnika ostaju
  vidljivi, „CV“ se u obrascu predloška više ne čita kao pravni oblik,
  citirani fontovi ostaju sačuvani, a imena u okomitim zaglavljima životopisa,
  višestraničnim popisima djelatnika, iza „Account manager“ te nazivi
  tvrtki koji počinju brojem potpuno se prepoznaju. Austrijski brojevi
  sudskog registra sada rade i iza engleske oznake; kratki oblik
  „Customer:“, EAR registracijski brojevi i brojevi poslodavca nose svoju
  vrijednost. Nizovi mjera, vrste kabela, EU pravni navodi, datumi valjanosti
  ponude, mjesta izvršenja, mjesta nadležnosti, registarski sudovi, porezna
  kratica „NoVA“, tehnički brojevi na oznakama guma te normativne oznake
  poput „OVE R6-2“ i „AStV“ više ne izazivaju lažnu uzbunu. Valjani označeni
  IBAN uredno završava prije polja registracije ili naslova sljedećeg retka;
  adrese s dodatkom obrtne zone potpuno se prepoznaju i u PDF tekstualnim
  tokovima s Windows prijelomima redaka. Engleski uvodi tvrtki i strukturirani
  nazivi štedionica potpuno se razgraničavaju. Zemlja izvornog dokumenta
  ostaje sačuvana u jezičnim inačicama za poštanske brojeve i oznake
  specifične za zemlju.

- U retcima primatelja i zaglavlja poruka jezični model mogao je spojiti
  prva dva imena u popisu odvojenom zarezom u jedan jedini nalaz („Bcc:
  Huber, Mayer“). Oba imena sada se prepoznaju, zamjenjuju i navode u
  izvještaju zasebno – jednako i iza „Sent:“, „Reply:“ i „Fwd:“.

- Strojno čitljivo područje putovnice ili osobne iskaznice (MRZ) nedostajalo
  je u skupnom upravljanju „Što se traži“. Sada pripada skupini
  „Identifikatori“ i može se zajedno s tom skupinom uključiti i isključiti.

- Tko za zamjenski tekst odabere predložak „Duga“, sada dobiva i zacrnjena
  mjesta u istom izgledu; dosad su ona iznenađujuće ostajala klasično crna.
  Površine zacrnjenja se nakon toga i dalje mogu neovisno prebaciti na drugi
  predložak.

- Bočna ploča stranica u uređivaču za doradu mogla je nakon obnavljanja
  spremljenog rasporeda prozora ostati prazna, sve dok se njezina širina nije
  ručno promijenila. Minijature se sada ponovno raspoređuju nakon vidljive
  izgradnje prozora i odmah stoje centrirano u ploči.

- Obojeni okviri provjere oko zamjenskih tekstova u PDF-ovima ostajali su
  jedva vidljivi ovisno o boji kategorije i boji semafora. Svijetla donja
  kontura sada pouzdano odvaja okvir provjere od obojenog zamjenskog mjesta
  i od pozadine stranice.

- Tko u uređivaču za doradu zacrni redak čiji je dokument postavljen s uskim
  proredom (tipično za ponude i troškovnike), dobio je traku koja je zadirala
  u gornje produžetke retka ispod – on je nakon toga bio samo napola čitljiv.
  Traka sada završava na stvarno nacrtanom pismu susjednog retka; zacrnjeni
  redak sam ostaje pritom potpuno prekriven zajedno sa svojim donjim
  produžecima.

- Vježbeni dokument („Pomoć → Otvori vježbeni dokument“, i u vodiču kroz
  program) sada demonstrira svaku vrstu prepoznavanja: izmišljenom pismu
  dodaju se fotografija s prepoznatljivim licem, ručno napisan potpis,
  zanimanje i odjel, dijagnoza i lijek – uz naziv tvrtke, iznos i datum koji
  su već bili prisutni. Ono što zadana postavka namjerno ostavlja, objašnjava
  sam list, uključno s prekidačem koji to uklanja; lice na fotografiji je
  tvornički piksellizirano.

- Novčani iznosi u uobičajenom njemačkom zapisu sa simbolom iza broja
  („1.240,00 €“) prekidač „Ukloni i novčane iznose“ nikad nije pronalazio –
  „1.240,00 EUR“ i „€ 1.240,00“ oduvijek jesu. Sada se prepoznaju sva tri
  zapisa.

- Pretraga potpisa sada radi i na samostalnim slikovnim datotekama: tko
  očisti sken kao JPG ili PNG, dobiva u njemu zacrnjene rukom pisane
  potpise – isto prepoznavanje, ista poruka u izvještaju kao kod PDF-a. Slike
  ugrađene u Office datoteke i dalje se ne pretražuju, jer prepoznavanje
  tamo mjereno radi nepouzdano; kvačica se zato sada zove „PDF i slikovne
  datoteke: Zacrni ručno napisane potpise“.

- Traka zacrnjenja mogla je kod uskog proreda vidljivo zadirati u gornje
  produžetke retka ispod i učiniti ga napola nečitljivim – visina trake
  dolazila je iz metrike fonta, ne iz onoga što se stvarno nalazi na
  papiru. Traka sada završava na stvarno nacrtanoj tinti susjednog retka, u
  uređivaču za doradu jednako kao i u automatskom čišćenju. Vlastiti redak sa
  svojim produžecima pritom uvijek ostaje potpuno prekriven; ako se retci
  stvarno preklapaju, traka radije ostaje na susjednom retku nego da nešto
  otkrije.

- U imeniku djelatnika s ulogom ispod imena ženska titula rukovoditeljice
  („Anna Berger“ s „Montageleiterin“ ispod) bila je uvučena u zamjenu imena –
  muški oblik pored ostao je ispravno netaknut. Ženski oblici „…leiterin“
  (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-, Gruppen-,
  Amtsleiterin) sada se tretiraju kao naziv funkcije jednako kao njihovi
  muški parnjaci; Filial-, Personal- i Vertriebsleitung su novo uključeni u
  oba oblika.

- Uklopiva prepoznavanja zanimanja nije nalazila ženske rukovodeće uloge
  poput „Projektleiterin“, „Teamleiterin“ ili „Abteilungsleiterin“, a njihove
  muške oblike jest. Oba oblika sada se broje jednako.

- U prozoru pregleda na Macu višestruka oznaka lijepila se izravno uz pojam
  („Anna Musterfrau2“ umjesto „Anna Musterfrau 2“). Razmak je vraćen.

- Usporedna lupa ima novi gumb pored regulatora zumiranja: jednim pritiskom
  postavlja je u punoj širini preko rezultata – svaka polovica visine, a
  original u istom mjerilu kao dokument (zum lupe pritom skače na 100 %).
  Drugi pritisak ponovno je sidra malu u lijevi stupac i vraća prethodni zum
  lupe. Kružić pored sada samo poništava zum – njegov opisni tekst dosad je
  pogrešno tvrdio da i ponovno sidra prozor.

- U alatnoj traci uređivača za doradu odabranom alatu ponovno se vidi da je
  odabran: gumb aktivnog alata nosi ispunjenu površinu s plavim rubom –
  jednako kao svaki drugi uključeni prekidački gumb trake (npr. usporedna
  lupa ili način učenja). Oznaka je izgubljena zajedno s vlastitim oblikovanjem
  gumba od 29. kolovoza.

- Brojevi pozicija troškovnika („2.3.3.3, 2.3.3.4, 2.3.3.5“ jedan ispod
  drugoga) smatrani su IP adresama i uklanjani iz rezultata; trorazinski
  brojevi sa zadnjim članom nalik godini („2.3.19, 2.3.20“) padali su kao
  kalendarski datumi. Uzlazni niz brojeva na početku retka sada se tretira
  kao ono što jest – popis pozicija; stvarne adrese (mrežne tablice s
  tehničkim okruženjem riječi, brojevi iznad 99) i stvarni datumi i dalje se
  prepoznaju.

- Prezimena poput „Müller“, „Fischer“, „Bauer“, „Koch“, „Wagner“,
  „Schneider“, „Weber“, „Jäger“, „Schmied“, „Becker“, „Schuster“, „Schäfer“
  ili „Meister“ ostajala su u čistom tekstu u popisima oblika „Prezime, Ime“
  (npr. „Teilnehmer: Müller, Peter; Nowak, Anna“), jer su ujedno uobičajeni
  nazivi zanimanja. Sada se pouzdano prepoznaju.

- Prilikom zacrnjivanja PDF-a traka je u uskim ćelijama tablice mogla
  odnijeti cijelu ćeliju: iz nalaza „D-LINK“ u troškovniku uklonjen je cijeli
  opis proizvoda pored njega, iako je pregled naveo samo sam nalaz. Traka i
  dalje prekriva cijele retke bloka adrese i oznake polja, ali skriva
  najviše onoliko nepovezanog koliko skriva vrijedno zaštite – opis pored
  nalaza sada ostaje netaknut.

- Nakon „Vrati prikaz na početno“ u uređivaču za doradu bočna ploča stranica
  ostajala je prazna – minijature stranica ponovno su bile vidljive tek
  nakon zatvaranja i ponovnog otvaranja prozora. Sada stoje odmah i nakon
  vraćanja, centrirano kao i prije.

- Uređivač za doradu ima četvrti alat: **Ukloni** izvlači tekst ispod okvira
  bez zamjene – bez trake (zacrnjivanje) i bez zamjenskog teksta (zamjena);
  praznina ostaje vidljivo prazna. Radi točno po riječima, a ako je ispod
  slika, njezina se pozadina čisti u bijelo, a „Vrati original“ poništava i
  uklanjanje bez zamjene. Vlastita ikona na traci i oznaka nišana (križić),
  vlastita prečica u svih 18 jezika (njemački F kao u entFernen).

- U traci pretrage PDF-a „Mapa …“ sada stoji desno od opcija pretrage.
  Otkad uz zacrnjivanje postoji i zamjena nalaza, pet gumba više nije
  stajalo jedan pored drugoga pri uobičajenoj širini prozora – prvi je bio
  stisnut i njegov tekst odsječen.

- „Vrati sve postavke na početno“ sada vraća i kvačicu „Zamijeni
  crveno/zeleno drugim bojama“ i, jednako kao svaku drugu, označava je s
  „promijenjeno“ kad odstupa od tvorničke postavke.

- Zamjenski tekstovi u PDF-ovima sada djeluju ujednačenije: gdje bi puni
  zamjenski tekst morao biti znatno manji od svog retka (npr. „[BEG16]“
  stisnut u kratku riječ poput „Das“), umjesto toga stoji skraćeni oblik u
  veličini retka („[B16]“) – dobro čitljivo umjesto sitno, a broj za vraćanje
  nosi oba zapisa. Zamjenski tekst postaje sitan tek kad ni najkraći oblik
  ne nalazi mjesta – to i dalje ostaje bolje od trake bez ikakve obavijesti.

- Višebojno postavljen zamjenski tekst (prijelaz ili duga) u PDF-u ostajao je neoštećen samo do sljedećeg zahvata: svaka daljnja zamjena ili zacrnjenje na istoj stranici mogla je već postavljene zamjenske oznake stisnuti u nečitljivu, zbijenu hrpu slova – tko je u uređivaču zamjenjivao riječ po riječ, umjesto „[BEG17]“ vidio je samo znakove ispisane jedan preko drugoga. Jednom postavljene zamjenske oznake sada ostaju kakve su postavljene.

- Prekidač za trajne iznimke u pregledu sada se zove „Nikad ne uklanjaj“ – kao popis u koji upisuje; dosad je stajalo „nikad više“. Redak nalaza pored njega je pregledniji: informacijski simbol „ⓘ“ je veći i lakše se pogađa, a kućica, oznaka zamjene i gumb imaju zajedničku visinu. Rečenica oko nalaza sada stvarno koristi svoju najavljenu širinu – dosadašnja postavka širine tiho je odbacivala prikaz, pa se isječak lomio kao uzak trak.

- U uređivaču pokazivač miša sada govori koji alat djeluje: nišan za ciljanje, pored njega mali znak – traka za zacrnjivanje, zamjenske strelice za zamjenu, luk za poništavanje za vraćanje, pikselna mreža za pikseliziranje. Dosadašnji simboli ruke su otpali; ruka inače posvuda znači „uhvati i pomakni“. Sada ima odgovarajući zadatak: iznad crveno istaknute riječi ili trake pokazivač postaje ruka koja pokazuje – ondje je dovoljan jedan klik.

- „Maksimalno prepoznavanje (AI)“ više ne nudi jezični model za preuzimanje i lokalnu upotrebu – ta razina sada radi isključivo preko vlastite AI postavljene pod „Poveži vlastitu AI“. Tko je već imao povezan vlastiti poslužitelj, ne primjećuje razliku.

- Vođena tura pregleda sada objašnjava i informacijski simbol „ⓘ“, koji prikazuje rečenicu oko nalaza. I sama ta rečenica bolje je čitljiva: jedan stupanj veći font, više proreda, fiksna širina umjesto uskog, zbijenog prijeloma.
- I „Provjeri datoteku“, „Pravila prepoznavanja i vlastiti pojmovi“, „Očisti tekst“ i „Očisti sliku“ sada imaju vlastitu turu – preko novog gumba „Tura kroz prozor“, jer ta četiri prozora nemaju vlastitu traku izbornika.
- Imena ispod devet ukrajinskih oznaka ugovornih uloga ostajala su nepotpuno prepoznata kod homografnog prezimena, kada je oznaka sama stajala u svom retku: „Покупець“/„Продавець“ (Kupac/Prodavatelj), „Поручитель“/„Боржник“ (Jamac/Glavni dužnik), „Свідок“ (Svjedok), „Орендодавець“/„Орендар“ (Najmodavac/Najmoprimac) i „Спадкодавець“/„Спадкоємець“ (Ostavitelj/Nasljednik). Imena se sada u potpunosti prepoznaju.

- Komentar imenovanog raspona u Excel radnoj knjizi (Upravitelj imena, polje „Komentar“) nepromijenjeno je nosio upisano ime dalje. Sada se čisti jednako kao i ostali sadržaj radne knjige.

- Imena ispod sedam mađarskih oznaka ugovornih uloga ostajala su potpuno neotkrivena kod homografnog prezimena: „Bérbeadó“/„Bérlő“ (Najmodavac/Najmoprimac), „Vevő“/„Eladó“ (Kupac/Prodavatelj), „Kezes“/„Főadós“ (Jamac/Glavni dužnik) i „Tanú“ (Svjedok). Imena se sada u potpunosti prepoznaju.

- Imena ispod češke oznake kupca „Kupující“ ostajala su potpuno neotkrivena kod homografnog prezimena. Ime se sada potpuno prepoznaje.

- Imena ispod ruske oznake skrbnika „Опекун“ ostajala su potpuno neotkrivena kod homografnog prezimena. Ime se sada potpuno prepoznaje.

- Imena ispod šest daljnjih hrvatskih oznaka ostajala su neotkrivena: „Jamac“, „Glavni dužnik“/„Dužnik“, „Ostavitelj“, „Nasljednik“ i „Vjerovnik“. Imena se sada u potpunosti prepoznaju.

- Spremljena HTML stranica s ugrađenom podstranicom u atributu `src` elementa `<embed>` (umjesto `data` kod `<object>`) nepromijenjeno je nosila osobne podatke dalje. Sada se čiste jednako kao kod `<object>`.

- Imena ispod pet danskih oznaka ugovornih uloga ostajala su nepotpuno prepoznata kod homografnog prezimena, kada je oznaka s dvotočkom stajala prije imena: „Arvelader“/„Arving“ (Ostavitelj/Nasljednik), „Befuldmægtiget“/„Fuldmagtsgiver“ (Opunomoćenik/Opunomoćitelj) i „Værge“ (Skrbnik). Imena se sada u potpunosti prepoznaju; odgovarajuće norveške oznake su radi sigurnosti također dodane.

- Zamjenski tekstovi u Word i PowerPoint datotekama sada nose istu boju kao u odabranom izgledu (jednobojno, prijelaz, duga ili po kategoriji) – dosad su tamo ostajali u običnoj boji teksta, iako su PDF rezultati odavno bili u boji.

- „Kopiraj kao tekst“ i „Kopiraj kao Markdown“ stavljaju čisti tekst rezultata izravno u međuspremnik – za umetanje u chat, e-poštu ili drugi program, bez prethodnog otvaranja datoteke.

- Imena ispod pet daljnjih slovenskih oznaka ostajala su neotkrivena: „Toženec“ (Tuženik), „Tožnik“ (Tužitelj), „Zastavitelj“ (Zalogodavac), „Zastavni upnik“ (Založni vjerovnik) i „Darovalec“ (Darovatelj). Imena se sada u potpunosti prepoznaju.

- Ime autora praćene promjene ćelije tablice (umetnuta, izbrisana ili spojena ćelija u Wordu) ostajalo je u datoteci, čak i kad je isto ime kao autor komentara odavno bilo uklonjeno. Sada se uklanja i ono.

- Imena ispod devet daljnjih slovenskih oznaka ostajala su neotkrivena: „Najemodajalec“/„Najemnik“ (Najmodavac/Najmoprimac), „Zapustnik“/„Dedič“ (Ostavitelj/Nasljednik), „Upnik“/„Dolžnik“ (Vjerovnik/Dužnik), „Glavni dolžnik“ (Glavni dužnik) i „Skrbnik“ (Skrbnik). Imena se sada u potpunosti prepoznaju.

- Imena ispod pet slovenskih oznaka ostajala su neotkrivena: „Izvedenec“ (Vještak), „Kupec“ (Kupac), „Prodajalec“ (Prodavatelj), „Naročnik“ (Naručitelj) i „Izvajalec“ (Izvođač). Imena se sada u potpunosti prepoznaju.

- Imena ispod pet daljnjih litavskih oznaka ostajala su neotkrivena: „Užsakovas“ (Naručitelj), „Vykdytojas“ (Izvođač), „Vežėjas“ (Prijevoznik), „Siuntėjas“ (Pošiljatelj) i „Arbitras“ (Arbitar). Imena se sada u potpunosti prepoznaju.

- Imena ispod šest daljnjih litavskih oznaka ostajala su neotkrivena: „Įgaliotinis“ (Opunomoćenik), „Įgaliotojas“ (Opunomoćitelj), „Naudos gavėjas“ (Korisnik, osiguranje), „Trečiasis asmuo“ (Umješač/treća strana u parnici), „Ankstesnis nuomininkas“ (Prijašnji najmoprimac) i „Naujasis nuomininkas“ (Novi najmoprimac). Imena se sada u potpunosti prepoznaju.

- Oznaka u ODT dokumentima (`text:bookmark`) nosi svoje ime slobodno dodijeljeno, često nazvano prema mjestu na koje pokazuje (npr. „Herr_Mueller_Unterschrift“) – nevidljivo za čitatelja, ali doslovno u datoteci. Ime se sada čisti zajedno s ostatkom.

- Imena ispod osam daljnjih litavskih oznaka ostajala su neotkrivena: „Pareiškėjas“ (Podnositelj zahtjeva), „Suinteresuotas asmuo“ (Protivnik u izvanparničnom postupku), „Ekspertas“ (Vještak), „Bankroto administratorius“ (Stečajni upravitelj), „Valdybos narys“ (Član nadzornog odbora), „Direktorius“ (Direktor), „Palikėjas“ (Ostavitelj) i „Įpėdinis“ (Nasljednik). Imena se sada u potpunosti prepoznaju.

- Imena ispod sedam daljnjih litavskih oznaka ostajala su neotkrivena: „Liudytojas“ (Svjedok), „Vertėjas“ (Prevoditelj/tumač), „Notaras“ (Javni bilježnik), „Dovanotojas“ (Darovatelj), „Apdovanotasis“ (Obdareni), „Pirkėjas“ (Kupac) i „Pardavėjas“ (Prodavatelj). Imena se sada u potpunosti prepoznaju.

- Imena ispod šest daljnjih litavskih oznaka ostajala su neotkrivena: „Globėjas“ (Skrbnik), „Palikimo administratorius“ (Upravitelj ostavine), „Laiduotojas“ (Jamac), „Pagrindinis skolininkas“ (Glavni dužnik), „Nuomotojas“ (Najmodavac) i „Nuomininkas“ (Najmoprimac). Imena se sada u potpunosti prepoznaju.

- Ime ispod litavske oznake „Ieškovas“/„Atsakovas“ (Tužitelj/Tuženik kao stranka u postupku) ostajalo je neotkriveno, neovisno o tome je li prezime ujedno bila uobičajena riječ (npr. „Vilkas“ = vuk) ili ne. Ime se sada potpuno prepoznaje.

- Unos u imenik osoba u ODT dokumentima (oznaka za kazalo pojmova) nosio je ime drugi put u vlastitom ključu razvrstavanja – nevidljivo u tekstu, ali doslovno u kasnije stvorenom kazalu. Ključ se sada čisti zajedno s ostatkom.

- Naziv slajda i naziv odjeljka PowerPoint prezentacije (vidljivi u području odabira odnosno u sortiranju slajdova) ostajali su neočišćeni, jer oba visi kao atribut na elementu koji nije tekst slajda. Oba se sada prepoznaju.

- Litavsko dvostruko ime spojeno crticom poput „Petraitis-Kazlauskas“ gubilo je svoju drugu polovicu čim je ispred njega stajao bilo kakav tekst (samo na početku teksta ostajalo je potpuno): prezime se sada u potpunosti prepoznaje i u tom slučaju.

- Ime ispod oznake „Cesionar“ (hrvatski, ustupitelj tražbine kod cesije) izazivalo je lažnu uzbunu, jer se sama oznaka polja pogrešno čitala kao osoba. Ime ispod ruske oznake „Цессионарий“ (također cesionar) naprotiv je ostajalo potpuno neotkriveno. Oba slučaja su sada otklonjena.

- Ime ispod oznake „Zedent“/„Zessionar“ (njemački, ustup tražbine) ostajalo je bez zamjene neotkriveno, kad je prezime ujedno bila uobičajena riječ (npr. „Bauer“). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Darczyńca“/„Obdarowany“ (poljski, darovatelj/obdarenik u ugovoru o darovanju) ostajalo je neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“ = vuk). Jednako je i rumunjska oznaka „Donatar“ (obdarenik) kod običnog prezimena ostajala zaglavljena kao navodni dio imena. Oba slučaja su sada otklonjena.

- Ime ispod oznake „Wierzyciel“/„Dłużnik“ (poljski, ovršni vjerovnik/ovršni dužnik odnosno opći vjerovnik/dužnik) ostajalo je neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“ = vuk). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Poręczyciel“/„Dłużnik główny“ (poljski, jamac/glavni dužnik u ugovorima o jamstvu) ostajalo je neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“ = vuk). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Ubezpieczony“/„Ubezpieczający“ (poljski, osiguranik/ugovaratelj osiguranja u policama osiguranja) ostajalo je djelomično ili potpuno neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“ = vuk). Jednako ime ispod „Osiguranik“/„Osiguravatelj“ (hrvatski, iste uloge), ondje je nestajalo potpuno zajedno s imenom (npr. „Golub“). Oba imena se sada u potpunosti prepoznaju.

- Ime ispod oznake „Pełnomocnik“/„Mocodawca“ (poljski, opunomoćenik/opunomoćitelj u punomoćima) ostajalo je neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“ = vuk). Jednako ime ispod „Opunomoćenik“/„Opunomoćitelj“ (hrvatski, iste uloge), ondje je nestajalo čak potpuno zajedno s imenom. Oba imena se sada u potpunosti prepoznaju.

- Ime ispod oznake „Pozwany“ (poljski, tuženik kao stranka u postupku) ostajalo je neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“ = vuk). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Najmoprimac“/„Najmodavac“ (hrvatski, najmoprimac/najmodavac u ugovorima o najmu) ostajalo je neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Kovač“). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Pracodawca“/„Pracownik“ (poljski, poslodavac/radnik kao ugovorna strana u ugovorima o radu) ostajalo je djelomično neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Krawiec“ = krojač). Ime se sada potpuno prepoznaje.

- Mađarska je u katalogu zemalja imala samo osobne identifikatore i PDV ID: broj trgovačkog registra (Cégjegyzékszám) sada se prepoznaje, ako riječ polja „Cégjegyzékszám“ ili kratica „Cg.“ stoji neposredno ispred – sam broj ne nosi kontrolnu znamenku.

- Estonija je u katalogu zemalja imala samo Isikukood: Käibemaksukohustuslase number (PDV ID na svakom estonskom računu) sada se prepoznaje s kontrolnom znamenkom.

- Latvija je u katalogu zemalja imala samo osobni kod: PVN reģistrācijas numurs pravnih osoba (identifikator tvrtke na svakom latvijskom računu) sada se prepoznaje s kontrolnom znamenkom.

- E-pošta sa šifriranim sadržajem (S/MIME ili PGP/MIME omotnica, `multipart/encrypted`) do sada je izlazila kao naizgled potpuno provjerena, bez ikakvog upozorenja, iako je njezin stvarni sadržaj bio šifriran i time neprovjeren. Takve poruke sada na to upozoravaju kao neprovjereni privitak.

- Malta je nedostajala u katalogu zemalja: malteški PDV broj (VAT number) sada se prepoznaje.

- Luksemburg je nedostajao u katalogu zemalja: luksemburški PDV broj (n° TVA) sada se prepoznaje.

- Bugarski „Изчакайте“ (“Pričekajte!“) na početku rečenice prijavljivan je kao oznaka mjesta – ista granica modela kao ranije kod mađarskih, poljskih, čeških i drugih poticajnih oblika bez vlastitog jezičnog modela. Lažna uzbuna sada izostaje.

- Ime ispod oznake „Zleceniodawca“, „Zleceniobiorca“ (poljski), „Prestator“ (rumunjski), „Naručitelj“ ili „Izvođač“ (hrvatski) ostajalo je djelomično ili potpuno neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Wilk“, „Vuk“, „Vulpe“ = lisica, „Sokol“). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Nadawca“ (poljski), „Afsender“ (danski) ili „Pošiljatelj“ (slovenski) ostajalo je djelomično ili potpuno neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Sowa“ = sova, „Bager“ = pekar, „Volk“ = vuk). Ime se sada potpuno prepoznaje.

- Ime ispod oznake „Gavėjas“ (litavski) ili „Prejemnik“ (slovenski) ostajalo je djelomično ili potpuno neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Vilkas“ = vuk). Kao i ranije kod „Primatelj“ (hrvatski) i „Modtager“ (danski), ime se sada potpuno prepoznaje.

- Zaglavlje okružnice poput „To All Staff“ ili „To All Employees“ pogrešno se prepoznavalo kao osobno ime i uklanjalo. To se sada više ne događa.

- Ime ispod oznake „Primatelj“ (hrvatski) ili „Modtager“ (danski) ostajalo je djelomično neotkriveno kad je prezime ujedno bila uobičajena riječ (npr. „Golub“, „Bager“ = pekar). Kao i ranije kod „Odbiorca“ (poljski) i „Destinatar“ (rumunjski), ime se sada potpuno prepoznaje.

- Puno ime u retku potpisa danskog, norveškog ili grčkog dokumenta ostajalo je djelomično neotkriveno kad je oznaka „Underskrift“ ili „Υπογραφή“ sama stajala iznad imena – u grčkom slučaju prezime se čak prepoznavalo kao oznaka mjesta umjesto kao ime. Kao i ranije kod „Подпись“ (ruski), ime se sada potpuno prepoznaje.

- Tekst na bočno položenoj fotografiji s mobitela (uobičajena okomita snimka koja se uspravno prikazuje samo preko oznake rotacije slike) mogao je promaknuti prepoznavanju teksta, jer je ono dosad čitalo sirove, položene piksele. Takve fotografije sada se prije čitanja okreću u ispravan položaj – kao već ranije kod prepoznavanja lica.

- Puno ime u retku potpisa ruskog, ukrajinskog ili litavskog dokumenta ostajalo je djelomično neotkriveno kad je oznaka „Подпись“, „Підпис“ ili „Parašas“ sama stajala iznad imena – ime ili patronim su otpadali. Kao i ranije kod „Potpis“ (hrvatski), ime se sada potpuno prepoznaje.

- Lice na bočno položenoj fotografiji s mobitela (uobičajena okomita snimka koja se uspravno prikazuje samo preko oznake rotacije slike) moglo je promaknuti prepoznavanju lica, jer je ono dosad provjeravalo sirove, položene piksele. Takve fotografije sada se prije pretrage okreću u ispravan položaj.

- Puno ime u retku potpisa hrvatskog dokumenta ostajalo je djelomično neotkriveno kad je oznaka „Potpis“ sama stajala iznad imena ili s dvotočkom ispred – ime je otpadalo, bilo u vlastitom retku ili u „Potpis: Ime Drugoime Prezime“. Kao i ranije kod „Unterschrift“ i „Signature“, ime se sada potpuno prepoznaje.

- Prezime iz braka iza skraćenica bračnog stanja „verh.“ (udana/oženjen) i „verw.“ (udovica/udovac) dosad je ostajalo potpuno neotkriveno, bilo u zagradi, iza zareza ili nalijepljeno bez razmaka („Anna Meier (verh. Weber)“, „Klaus Bauer (verw.Fischer)“) – kao već kod „geb.“ sada se pouzdano prepoznaje.

- Ime iza potpisa prokure „ppa.“ (npr. u retku potpisa poslovne e-pošte ili poslovnog pisma) dosad je kod prezimena istovjetnog nazivu zanimanja poput „Bauer“ ili „Koch“ ostajalo djelomično ili potpuno neotkriveno – kao već kod „gez.“ sada se pouzdano prepoznaje.

- Broj poljske osobne iskaznice (dowód osobisty) prepoznavao se samo bez razmaka između serije i broja („ABS123456“). No dokument taj podatak baš tako ne ispisuje – službeno ondje stoji razmak („ABS 123456“), a u tom je zapisu broj dosad ostajao neotkriven.

- Animirani PNG (APNG, npr. kratka snimka zaslona pohranjena kao PNG umjesto GIF) dosad se provjeravao i čistio samo sa svojom prvom slikom, bez ikakve obavijesti o tome – kao ranije kod animiranog WebP-a, Maskuro sada javlja da svaka daljnja slika ostaje neprovjerena u rezultatu.

- Animirana WebP slika (npr. iz alata za snimanje zaslona ili aplikacije za razgovor s više slika u jednoj datoteci) dosad se provjeravala i čistila samo sa svojom prvom slikom, bez ikakve obavijesti o tome – kao ranije kod višestraničnog TIFF-a, Maskuro sada javlja da svaka daljnja slika ostaje neprovjerena u rezultatu.

- Slovensko dvostruko ime spojeno crticom („Ana-Marija Novak“) gubilo je svoju prednju polovicu čim je ispred njega u tekstu stajala rečenica - ista pogreška kao ranije kod poljskog. „Ana-“ je ostajalo nezaštićeno u čistom tekstu, dok se ostatak imena već zamjenjivao.

- Poljsko dvostruko ime spojeno crticom („Anna-Maria Kowalska“) gubilo je svoju prednju polovicu čim je ispred njega stajala rečenica ili prijedlog poput „z“/„od“ - ostatak imena se zamjenjivao, „Anna-“ je ostajalo nezaštićeno u čistom tekstu.

- Kazaški učtivi izrazi „Хабарласыңыз“/„Байланысыңыз“ (kontaktirajte nas) te srpski glagolski oblici „Помоћи“, „Чекамо“ i „Пишите“ bez vlastitog jezičnog modela za prepoznavanje pogrešno su se u rečenicama s telefonom prepoznavali kao osobno ime ili mjesto.

- Azerbajdžanska učtiva riječ „Xahiş“ (molba) bez vlastitog jezičnog modela za prepoznavanje pogrešno se u rečenicama s telefonom prepoznavala kao osobno ime.

- Indonezijske i malajske učtive/poticajne riječi bez vlastitog jezičnog modela za prepoznavanje poput „Silakan“, „Mohon“ (indonezijski), „Sila“ i „Tolong“ (malajski) pogrešno su se u rečenicama s telefonom prepoznavale kao osobno ime ili mjesto.

- Uzbečki poticajni oblik „Kutamiz“ (čekamo) bez vlastitog jezičnog modela za prepoznavanje pogrešno se u rečenicama s telefonom prepoznavao kao mjesto.

- Turski poticajni oblici bez vlastitog jezičnog modela za prepoznavanje poput „Arayınız“ (nazovite) i „Bekliyoruz“ (čekamo) pogrešno su se u rečenicama s telefonom prepoznavali kao osobno ime.

- Poticajni oblici u daljnjim jezicima bez vlastitog jezičnog modela za prepoznavanje (češki, slovački, grčki) poput „Zavolejte“ (nazovite), „Prosíme“ (molimo) i „Περιμένουμε“ (čekamo) pogrešno su se u rečenicama s telefonom prepoznavali kao osobno ime ili mjesto.

- Mađarski i poljski poticajni oblici poput „Hívjon“ (nazovite), „Kérjük“ (molimo), „Várjuk“ (čekamo), „Zadzwoń“ (nazovite) i „Czekamy“ (čekamo) pogrešno su se u rečenicama s telefonom prepoznavali kao osobno ime ili mjesto.

- U numeriranom popisu imena bez oblika tablice (npr. „1. Robert Brown“, ispod „2. Mary Johnson“) ime s određenim engleskim prezimenima (među ostalim „Brown“, „White“, „Green“, „Black“, „Young“) potpuno se previđalo – jezični je model broj sljedećeg retka pridružio imenu, zbog čega nalaz nikad nije točno odgovarao.

- Kod poljskog jezičnog modela inicijal imena ispred prezimena (npr. „J. Kowalski“, „A. Nowak“) ostajao je neprepoznat i neočišćen u tekstu – zamjenjivalo se samo prezime. Drugi provjereni jezici (među ostalim njemački, engleski, rumunjski, hrvatski, mađarski, ruski) taj su inicijal već ranije uzimali zajedno s imenom.

- Osobno ime iza malim slovima pisanog naslova poput „dr.“, „ing.“
  ili „dipl. ing.“ na mađarskom, rumunjskom i hrvatskom uopće se nije
  prepoznavalo – gubio se ne samo naslov, nego cijelo ime
  (npr. „dr. Kovács Béla“, „ing. Andrei Popescu“, „dipl. ing. Marko
  Horvat“).
- U slovenskim zapisnicima sjednica čista oznaka uloge prije dvotočke (npr. „Tajnik:“, „Podpredsednik:“, „Poročevalec:“, „Predsedujoči:“) pogrešno se prepoznavala kao osobno ime, čim je na drugom mjestu u zapisniku već stajalo stvarno ime govornika.
- U ruskim zapisnicima sjednica čista oznaka uloge prije dvotočke (npr. „Секретарь:“, „Докладчик:“, „Докладчица:“) pogrešno se prepoznavala kao osobno ime, čim je na drugom mjestu u zapisniku već stajalo stvarno ime govornika.
- U rumunjskim zapisnicima sjednica čista oznaka uloge s određenim članom prije dvotočke (npr. „Secretarul:“, „Președintele:“, „Vicepreședintele:“, „Moderatorul:“, „Consilierul:“) pogrešno se prepoznavala kao osobno ime – „Președintele“ već samo za sebe, ostale dodatno, čim je na drugom mjestu u zapisniku već stajalo stvarno ime govornika.
- U hrvatskim zapisnicima sjednica čista oznaka uloge prije dvotočke (npr. „Izvjestiteljica:“, „Zapisničar:“/„Zapisnicar:“, „Predsjedavajući:“) pogrešno se prepoznavala kao osobno ime.
- Poljska adresa poštanskog pretinca „Skrytka pocztowa“ iza oznake
  pošiljatelja ili primatelja (npr. „Odbiorca: Skrytka
  pocztowa 45“) pogrešno se prepoznavala kao osobno ime.
- Hrvatska adresa poštanskog pretinca „Poštanski pretinac“ iza oznake
  adrese „Adresa:“ (npr. „Adresa: Poštanski pretinac
  45“, i s dodanim „br.“ za broj) pogrešno se prepoznavala
  kao osobno ime.
- Mjesto bez daljnje oznake u norveškom tekstu (npr. „Anna Hansen bor i Oslo“) nije se prepoznavalo – vlastiti jezični model ondje mjesta uglavnom označava vlastitom, dosad nepridruženom oznakom umjesto uobičajene „LOC“.
- Datum u ISO redoslijedu godina-mjesec-dan s crticom ili
  točkom (npr. „2024-12-31“) u nekim se jezicima uopće nije
  prepoznavao kao datum – najuočljivije na litavskom, gdje službeni dopisi
  datume pretežno navode u tom redoslijedu.
- Mađarski PDV broj (közösségi adószám) u službeno
  jednako valjanom, 11-znamenkastom obliku bez razdjelnika (npr.
  „12345678123“ umjesto „12345678-1-23“) nije se prepoznavao.
- Poljski porezni broj NIP s razdjelnicima u grupiranju 3-2-2-3
  (npr. „856-73-46-215“, kako je uobičajeno na računima tvrtki i
  samostalnih poduzetnika) nije se prepoznavao – pogađalo je samo
  grupiranje 3-3-2-2 za fizičke osobe.
- Naziv tvrtke ispod slovačke oznake polja
  „Zamestnávateľ:“ ili „Názov zamestnávateľa:“ (poslodavac/tvrtka) nije se
  prepoznavao.
- Naziv tvrtke ispod rumunjske oznake polja
  „Angajator:“ ili „Denumire angajator:“ (poslodavac/tvrtka) nije se
  prepoznavao.
- Naziv tvrtke ispod mađarske oznake polja
  „Cég:“ ili „Munkáltató:“ (tvrtka/poslodavac) nije se
  prepoznavao.
- Naziv tvrtke ispod poljske oznake polja
  „Pracodawca:“ ili „Nazwa firmy:“ (poslodavac/tvrtka) nije se
  prepoznavao.
- Naziv tvrtke ispod slovenske oznake polja
  „Podjetje:“ ili „Delodajalec:“ (tvrtka/poslodavac) nije se
  prepoznavao.
- Naziv tvrtke ispod hrvatske oznake polja
  „Tvrtka:“ ili „Poslodavac:“ (tvrtka/poslodavac) nije se
  prepoznavao.
- Ispisani novčani iznos s valutom pisanom malim slovima (npr.
  „500 euro“) nije se prepoznavao, pogađalo je samo veliko slovo („Euro“).
- Prezime iza „Schwager“/„Schwägerin“ (npr. „Der Schwager Bauer
  erhält die Erbschaft.“) nije se prepoznavalo.
- Kod turske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „34000 İstanbul İstiklal
  Caddesi No: 45“) kućni broj ostajao je neočišćen.
- Kod slovačke adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „831 01 Bratislava Hlavná
  15“) kućni broj ostajao je neočišćen.
- Zemlja rođenja bez daljnje oznake u hrvatskom
  polju obrasca (npr. „Zemlja rođenja: Njemačka“) nije se prepoznavala.
- Zemlja rođenja bez daljnje oznake u litavskom
  polju obrasca (npr. „Gimimo valstybė: Vokietija“) nije se prepoznavala.
- Zemlja rođenja ili prebivališta bez daljnje oznake u
  poljskom polju obrasca (npr. „Kraj: Niemcy“) nije se prepoznavala.
- Mjesto državljanstva ili prebivališta bez daljnje oznake u
  slovenskom polju obrasca (npr. „Državljanstvo: Nemčija“) nije se
  prepoznavalo.
- Zemlja prebivališta bez daljnje oznake u norveškom
  polju obrasca (npr. „Bosted: Tyskland“) nije se prepoznavala.
- Nova stranica postavki „Obavijesti“ (prije odjeljak u „Program“): tri obavijesti trake zadataka (pregled spreman, obrada gotova, ažuriranje preuzeto) sada stoje na vlastitom mjestu.
- Novo: rezultat se dodatno može spremiti kao čista tekstualna datoteka (.txt) ili s nastavkom .md pored – za daljnju obradu u AI-ju ili drugom programu.
- Kod hrvatskog kontakt podatka s oznakom „Osoba za kontakt“/„Kontakt osoba“ (npr. „Osoba za kontakt: Golub Marko“) ime je ostajalo potpuno neprepoznato, kad je prezime ujedno bila uobičajena imenica (Golub).

- Kod rumunjskog kontakt podatka s oznakom „Persoana de contact“/„Persoană de contact“ (npr. „Persoana de contact: Lup Ion“) ime je ostajalo potpuno neprepoznato, kad je prezime ujedno bila uobičajena imenica (Lup = „vuk“), a ime vrlo kratko i generičko.

- Kod poljskog kontakt podatka s oznakom „Osoba
  kontaktowa“/„Osoba do kontaktu“ (npr. „Osoba kontaktowa: Wilk
  Adam“) prezime je ostajalo neprepoznato, kad je ujedno bila
  uobičajena imenica (Wilk = „vuk“, Zielony = „zelen“).

- Kod rumunjske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „010061 București Strada
  Victoriei 30“) kućni broj ostajao je neočišćen.
- Kod srpske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „11000 Beograd Bulevar
  Kralja Aleksandra 73“) kućni broj ostajao je neočišćen.
- Kod grčke adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „104 32 Αθήνα Ερμού 15“)
  kućni broj ostajao je neočišćen.
- Kod slovenske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „1000 Ljubljana Slovenska
  cesta 58“) poštanski broj ostajao je neočišćen.
- Kod litavske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „LT-01100 Vilnius
  Gedimino pr. 9“) poštanski broj ostajao je potpuno neočišćen.
- Kod mađarske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „1052 Budapest Kossuth
  Lajos utca 12“) poštanski broj ostajao je neočišćen.
- Prezime iza „Erben“ (npr. „Die Erben Wagner erhielten die
  Mitteilung fristgerecht.“) u kontekstu nasljedstva/ostavine ostajalo je
  gotovo uvijek neprepoznato.
- Prezime iza „Geschwister“ (npr. „Die Geschwister Bauer wohnen
  in Linz.“) dosad je ostajalo gotovo uvijek neprepoznato – za razliku od
  „Familie“/„Ehepaar“ ovo se nije odnosilo samo na imena istovjetna nazivu
  zanimanja (Koch, Bauer, Richter), nego na bilo koje prezime na tom mjestu.
- Prezime iza „Ehepaar“ ili „Eheleute“ (npr. „Das Ehepaar Koch
  zieht um.“) ostajalo je neprepoznato, kad je ujedno bila uobičajena
  imenica ili naziv zanimanja (Koch, Bauer, Richter).
- Obični broj narudžbe, naloga ili artikla u tipičnom
  rasteru grupiranja poreznog broja ili broja socijalnog osiguranja
  (npr. „030 4471 2298“) pogrešno se zacrnjivao kao takav, bez ikakve
  pripadajuće oznake.
- Broj dokumenta/predmeta u obliku „godina/tekući broj“ (npr. u
  „Rechnung Nr. 4/2024/778899“) prepoznavanje telefonskog broja pogrešno je
  zacrnjivalo kao telefonski broj.
- Ime iza „Herr“/„Frau“ s višerječnim akademskim
  nizom titula ispred („Herr Dr. med. Weber“, „Herr Prof. Dr. Krause“) dosad
  je ostajalo potpuno nezaštićeno – prepoznavala se dosad samo
  jedna riječ titule između oslovljavanja i imena.
- Sudski broj spisa u klasičnom obliku s kraticom vijeća/senata
  („4 Ca 1523/24“, „Az.: 7 O 234/25“) dosad je ostajao potpuno
  nezaštićen – čak se ni uobičajeni kratki oblik „Az.“/„Gz.“ nije prepoznavao
  uz ispisanu oznaku.
- Broj kreditne kartice koji je usred svog grupiranja po četiri prekinut
  prijelomom retka – npr. u uskom stupcu tablice – dosad je
  ostajao potpuno nezaštićen.
- Porezni identifikacijski broj koji je usred svog grupiranja
  prekinut prijelomom retka – npr. u uskom
  stupcu tablice ili polju obrasca – dosad je ostajao potpuno
  nezaštićen.
- Broj socijalnog osiguranja koji je usred svog grupiranja prekinut
  prijelomom retka – npr. u uskom stupcu tablice – dosad je
  ostajao potpuno nezaštićen, čak ni djelomično
  zamijenjen.
- Kućni broj s rasponom poput „12a-14b“ ili „3-5“ zamjenjivao se samo
  napola – drugi dio iza crtice ostajao je otvoren u rezultatu.
- Broj šasije (FIN/VIN) koji je usred svojih 17 znakova
  prekinut prijelomom retka, razmakom ili crticom – npr. u
  uskom stupcu tablice ili polju prometne dozvole – dosad je
  ostajao potpuno nezaštićen.
- Oslovljavanje u pismu/e-pošti poput „Liebe Anna!“ ili „Lieber Hans“ – bez
  zareza iza imena, najčešći oblik u neformalnim porukama – ostavljalo je
  ime potpuno nezaštićeno, i u potpunom dokumentu s
  tekstom i pozdravnom formulom ispod.
- Ista praznina pogađala je i neformalna oslovljavanja u chatu/e-pošti „Hallo Anna!“,
  „Hi Anna!“, „Hey Anna!“ i „Servus Anna!“ bez zareza – ime je
  jednako ostajalo potpuno nezaštićeno.
- Čist blok potpisa koji izravno počinje s „MfG“ ili „Herzlichst“
  – npr. kopiran iz međuspremnika, bez prethodne rečenice – ostavljao je
  ime ispod njega potpuno nezaštićeno.
- Polje s više osoba, npr. „Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)“, spajalo je oba imena zajedno sa
  zagradom u jedan jedini, predug nalaz – drugo
  ime pritom je djelomično ostajalo nezaštićeno u rezultatu.
- Ulica bez nastavka „-straße“/„-weg“ – kakva je uobičajena na selu,
  npr. „Am Marktplatz 5“ ili „Im Grund 12“ – ostajala je
  neprepoznata, kad je iza nje slijedio redak poštanski broj-mjesto, npr. u
  potvrdi o prijavi boravišta: „Neue Anschrift: Am Weidengarten 17, 54295 Trier“
  gubila je ulicu potpuno, uklanjao se samo poštanski broj.
- Ime iza složene oznake polja s
  kosom crtom (npr. „Name/Vorname: Bauer Klaus“) djelomično se nije
  prepoznavalo – dvoznačno prezime poput „Bauer“ ostajalo je bez
  oznake polja neotkriveno. Ista praznina pogađala je kombinirana polja poput
  „PLZ/Ort: 04109 / Leipzig“. Isto je vrijedilo za kombinirana polja s
  ispisanim veznikom umjesto kose crte, npr.
  „Vor- und Nachname: Bauer Klaus“ ili „Nachname bzw. Vorname: …“.
- Datum rođenja u obliku „Datum der Geburt: …“ i datum smrti
  u obliku „Todesdatum: …“ ili „Datum des Todes: …“ nisu se
  prepoznavali – pogađalo je samo „Geburtsdatum: …“ odnosno „Sterbedatum: …“.
- Datum vjenčanja u obliku „Datum der Heirat: …“ ili „Datum der
  Hochzeit: …“ nije se prepoznavao – pogađalo je samo „Hochzeitsdatum: …“,
  „Heiratsdatum: …“ i „Datum der Eheschließung: …“, iako su
  datum razvoda, naturalizacije i registriranog partnerstva odavno poznavali isti
  oblik „Datum der X“.
- Datum razvoda u obliku „Datum der Scheidung: …“ nije se
  prepoznavao – pogađao je samo „Scheidungsdatum: …“ i pripadni
  glagolski oblik, iako su datum naturalizacije i registriranog partnerstva odavno
  poznavali isti oblik „Datum der X“.
- Datum registriranog partnerstva se dosad uopće nije prepoznavao – ni s
  oznakom („Verpartnerungsdatum: …“, „Datum der Lebenspartnerschaft:
  …“) ni u tekstu („… wurden am … verpartnert“). Sada se prepoznaje kao
  posebna vrsta podatka, kao datum rođenja, vjenčanja, razvoda i naturalizacije.
- Datum naturalizacije se dosad uopće nije prepoznavao – ni s
  oznakom („Einbürgerungsdatum: …“) ni u tekstu („… wurde am …
  eingebürgert“). Sada se prepoznaje kao posebna vrsta podatka, kao datum
  rođenja, vjenčanja i razvoda.
- Datum razvoda se dosad uopće nije prepoznavao – ni s
  oznakom („Scheidungsdatum: …“) ni u tekstu („Die Ehe wurde
  am … geschieden“). Sada se prepoznaje kao posebna vrsta podatka, kao datum
  rođenja, smrti i vjenčanja.
- Datum vjenčanja iza genealoškog znaka braka „⚭“ bez oznake
  nije se prepoznavao, iako su datum rođenja i smrti u istom retku
  preko zvjezdice i križa već bili prepoznati – sada se prepoznaje i
  datum vjenčanja.
- Datum smrti iza križa iz osmrtnice bez oznake
  („*03.06.1940 †21.11.2023“) nije se prepoznavao, iako se datum rođenja
  ispred njega preko genealoške zvjezdice već prepoznavao – sada se prepoznaje i
  datum smrti.
- Prezime prije imena na kraju retka predmeta/tiketa s ispred navedenim
  stvarnim tekstom i crticom-razdjelnikom („Betreff: Reklamation - Bauer, Anna“) nije se
  prepoznavalo kod prezimena istovjetnog nazivu zanimanja – sada se prepoznaje.
- Brojevi prijave/molbe i podnositelja zahtjeva iza svoje oznake
  („Bewerbernummer: 4471829“, „Antragstellernummer: 7654321“) potpuno su
  promašivali prepoznavanje – sada se prepoznaju.
- Zamjena više ne zacrnjuje, kad nema mjesta za čitljivu
  zamjensku oznaku – premala zamjenska oznaka sada se piše manje
  umjesto da postane prazna traka, sve dok uopće ostaje
  mjesta. Novo osim toga: hoće li se nalaz na slici (zaglavlje pisma,
  pozadina skena) označiti ili samo zacrniti, sada se može postaviti
  neovisno o ostatku vrste rezultata. I nalaz
  na slici koja se u potpunosti uklanja bio je označen, kao da
  slika ostaje – zamjenska oznaka stajala je svijetlo na podlozi koja nikad
  nije bila zacrnjena, i tako je nevidljivo nestajala na sada bijelom
  papiru.
- Nalaz na **zadržanoj** slici pri zamjeni se uvijek
  zacrnjivao crno-bijelo, neovisno o odabranom prikazu
  (boje kategorija, duga …) – vidljivo kao prijelom između šarenih
  oznaka u tekstu i crnih traka na zaglavlju pisma. Podloga
  slike sada slijedi istu boju kao zamjenska oznaka pored nje.
- Prepoznavanje identifikacijskog broja vozila (FIN/VIN) bezuvjetno je
  označavalo svaki 17-znamenkasti alfanumerički kod bez I/O/Q kao
  broj šasije – uključujući brojeve narudžbe, serije i licencnog ključa,
  koji slučajno imaju isti oblik. Sada broji samo uz
  kontekstnu riječ u blizini („FIN“, „VIN“, „Fahrgestell“, „Chassis“ i slično).
- U sustavima za tikete/kalendar prepoznavanje imena iza „Assigned to“/
  „Closed by“ i sličnog povlačilo je sljedeću riječ polja sa sobom, kad je
  u istom retku bez razdjelnika izravno slijedila („Assigned to Max Mustermann Priority High“
  postajalo je „Max Mustermann Priority“). U zaglavljima Git commitova
  prepoznavanje imena jednako je povlačilo **sljedeći** ključ trailera, kad su dva
  retka bila spojena samo jednim razmakom umjesto prijeloma retka
  („Author: julia bergmann Reviewed-by: …“ postajalo je „julia bergmann
  Reviewed-by“). Obje kočnice su dodane.
- Ime iza „p.A.“, „zH“/„zHd“, „i.A.“/„i.V.“ i „geb.“ povlačilo je
  izravno sljedeću riječ odjela u isti nalaz, kad je bez
  razdjelnika stajala u istom retku („p.A. Max Mustermann Buchhaltung“
  postajalo je „Max Mustermann Buchhaltung“, „i.A.Max Mustermann Vertrieb“ u
  „Max Mustermann Vertrieb“). Ista kočnica kao kod „Assigned to“/
  Git trailera sada je dodana i ovdje.
- Označeni IBAN izravno iznad retka BIC, BLZ ili SWIFT povlačio je
  njegovu oznaku u vlastiti nalaz, jer su „BIC“ i „BLZ“
  sami izgledali kao još jedan blok brojeva – iz „IBAN: DE89 …
  0130 00“ i retka ispod nastajao je jedan jedini, predaleko sežući
  nalaz, a oznaka sljedećeg retka nestajala je pri
  čišćenju zajedno s njim. Pogođena je bila gotovo svaka bankovna veza s IBAN-om i BIC-om
  jedan ispod drugog.
- Ploča nalaza sada javlja **gdje** stoji zamjenska oznaka koju na
  stranici ne može pronaći. Dva slučaja dosad su javljala samo „nije pronađeno“,
  iako je zamjena obavljena: stoji li zamjenska oznaka u nevidljivom
  pratećem tekstu – npr. odredišnoj adresi poveznice, napomeni ili
  polju obrasca – redak to sada nosi kao vlastitu obavijest
  („u pratećem tekstu“), a klik to objašnjava. A kad je zamjenska oznaka
  zbog nedostatka mjesta skraćena („[N382]“ umjesto „[NAM382]“), klik
  na dugi redak sada skače na mjesto kratkog oblika i navodi
  preimenovanje; pridruživanje pritom izričito povezuje oba retka
  jedan s drugim.
- Ako ista zamjenska vrijednost stoji više puta u dokumentu, svaki daljnji
  klik na redak ploče skače u krug na sljedeće mjesto nalaza – i preko
  granica stranica; statusni redak broji uz to („mjesto 2 od 4“), a
  upravo ciljano mjesto uokvireno je izraženije od ostalih. A kad
  zamjenska oznaka stoji samo u popisu nalaza, ali nigdje u dokumentu
  (jer je to mjesto uklopljeno u preklapajuću zamjenu), statusni redak to sada
  javlja, umjesto da klik ostane nijemo bez posljedica.
- Skraćeno ime iza „an“ ili „für“ sada se pouzdano prepoznaje kao
  ime – „Überweisung an M. Wagner“ i „Rechnung für M. Wagner“
  dosad su često ostajali neočišćeni, dok se isto ime uz drugu
  oznaku ispred (npr. „Zahlungsempfänger:“) već pronalazilo.
  Pogođeni su bili prije svega retci izvoda i knjiženja s računa.
- „Angeklagter“/„Angeklagte“/„Beschuldigter“/„Beschuldigte“ sada vrijede kao
  polje imena: stajalo li je ime u dokumentima kaznenog postupka izravno iza
  jedne od tih oznaka, dosad se nije prepoznavalo za otprilike polovicu
  provjerenih imena – ni ime ni prezime.
- Mjesto na koje se kliknulo u ploči nalaza sada je uokvireno plavo umjesto
  žuto obilježeno – na obojenim površinama semafora provjere žuta boja
  nalaza pretrage nije se prepoznavala. Osim toga klik sada pronalazi i
  višerječne zamjenske vrijednosti (izmišljena imena, maskirani brojevi): dosad
  je kod takvih redaka bio bez učinka, jer se mjesto nalaza tražilo samo riječ
  po riječ.
- Posvojitelji, hranitelji i pomajke/pomaci („Adoptivvater“, „Pflegemutter“,
  „Stiefvater“ i drugo) sada se prepoznaju kao polje imena, ime je
  ranije prolazilo neočišćeno
- Tablice i popisi bogati brojevima više se pogrešno ne odbacuju:
  zamijeni li se kratak broj (npr. dio broja kupca pročitan
  kao telefonski broj), završna provjera prijavljivala je isti
  niz znamenki kao preostali podatak i kad se on drugdje samo
  slučajno nalazio u posve drugom broju – i tada nije davala nikakav
  rezultat. Broj se sada broji kao ostatak samo tamo gdje stoji
  kao samostalan broj.
- Matične isprave: „Vater:“/„Mutter:“ sada se prepoznaje kao polje imena, ime roditelja ranije je prolazilo neočišćeno
- Daljnje obiteljske uloge („Kum“, „Djed/baka“, „Bračni partner“,
  „Životni partner“, „Ujak/stric“, „Teta“) sada se prepoznaju kao polje imena,
  ime je ranije prolazilo neočišćeno
- Njemački poziv na broj banke (BLZ) sada se prepoznaje i u službenom grupiranju
  (“370 400 44“, “370.400.44“, “370-400-44“, “370/400/44“), ne više samo
  kao osam povezanih znamenki.
- Njemački broj mirovinskog osiguranja sada se prepoznaje i s točkom,
  crticom ili kosom crtom između pet blokova
  (“65-170839-J-08-8“, “65.170839.J.08.8“), ne više samo s razmakom.
- Glavni prozor se pojavljuje brže: knjižnice prepoznavanja
  (Presidio zajedno s podlogom jezičnog modela) dosad su se učitavale već
  pri izgradnji prozora – na Windowsu oko četiri sekunde, prije nego što je uopće
  bilo išta vidljivo. Sada se u potpunosti učitavaju u pozadini; gumb
  „Očisti“ i dalje postaje dostupan tek kad je sve spremno.
- Office dokumenti s puno slika ili videa sada se brže
  zapisuju: već komprimirani mediji se u paketu rezultata
  spremaju umjesto da se beskorisno drugi put komprimiraju – to dosad
  nije uštedjelo ni bajt i JPEG-ove je radije povećavalo.
- Proračunske tablice i drugi dokumenti od mnogo malih
  tekstualnih jedinica provjeravaju se brže: prepoznavanje jezika sada
  obrađuje sve ćelije i odlomke dokumenta u jednom prolazu umjesto
  pojedinačno – uz dokazano iste nalaze (400 ćelija: s otprilike
  4,7 na 2,5–3,5 sekunde).
- Stranice PDF-a u obliku popisa (kazala, popisi pozicija) su pri
  umetanju zamjenskih oznaka znatno brže: pretraga mjesta po
  oznaci dosad je prolazila kroz sve riječi stranice – sada samo
  kroz okolinu retka, uz dokazano isti rezultat (na
  stranici s 300 oznaka otprilike šesnaest puta brže).
- Dokumenti bogati slikama štede više nepotrebnih koraka po slici:
  brojanje lica i kodova na PDF stranicama više ne dekodira
  sliku stranice dvaput, provjera metapodataka više uopće ne dešifrira
  najprije čistu sliku, pikselizirane slike se pišu s normalnom
  umjesto najsporijom PNG kompresijom (ista
  veličina, trećina vremena), a bez postavljenog vodenog žiga
  otpada beskorisno ponovno pisanje cijelog PDF-a na kraju.
- Skenirani PDF-ovi s uključenim prepoznavanjem teksta prolaze znatno brže:
  svaka stranica se dosad renderirala dvaput u punoj rezoluciji
  (jednom za čitanje, jednom za rasterizaciju) – sada se slika
  ponovno koristi. A na Windowsu/Linuxu prepoznavanje teksta čita
  trake velikog skena u jednom prolazu umjesto s vlastitim
  pokretanjem programa po traci.
- Veliki dokumenti se čiste znatno brže: usklađivanje već
  pronađenih vrijednosti dosad je raslo s brojem mjesta nalaza (64-KB
  blok teksta na kraju velike datoteke koštao je oko jednu sekundu
  samo za to, sada šezdeseti dio toga), a pretraga pravnih oblika tvrtki
  prolazila je sa svih ~280 kataloških oblika kroz svako mjesto teksta (sada oko
  dvadeset puta brže, uz dokazano iste nalaze).
- Ime izravno iza „Beste Grüße“/„Beste Wünsche“ bez prethodnog
  teksta ili interpunkcije uopće se nije prepoznavalo – čisti
  blok potpisa bez teksta ispred ostavljao je ime da
  nestane bez traga.
- Polje adrese na početku dokumenta s prezimenom istovjetnim nazivu
  zanimanja („Bauer Anna“, „Koch Stefan“ kao prvi redak iznad ulice i
  mjesta) dosad je djelomično ostajalo neprepoznato ili se klasificiralo
  kao oznaka mjesta umjesto kao osoba – bez prethodne rečenice jezičnom
  modelu nedostajala je struktura rečenice koja inače omogućuje da se „Bauer“
  prepozna kao ime, a ne kao zanimanje.
- Ime iza oznake potpisa „gez.“ s prezimenom istovjetnim nazivu
  zanimanja ispred imena („gez. Bauer Anna“ na
  kraju rješenja ili presude) dosad je ostajalo nepotpuno prepoznato –
  pronalazilo se samo ime, prezime je nestajalo bez traga.
- Ime izravno iza broja kupca, broja ugovora ili slične
  identifikacijske oznake bez vlastitog retka („Vertragsnummer 55219 Bauer
  Anna“, „Kundennr. 4711 Bauer Anna“) dosad je kod prezimena istovjetnog
  nazivu zanimanja ostajalo nepotpuno ili uopće neprepoznato.
- Ikona u traci izbornika macOS-a sada je predložak koji se, kao i
  susjedne ikone, prilagođava svijetlom i tamnom načinu rada – s dvije
  izrezane trake pritom ostaje prepoznatljiva kao Maskuro. Kad radi čuvar
  međuspremnika, to prikazuje odvojena točka na vrhu štita.
- Klik u ploči nalaza sada vodi do mjesta nalaza i u anonimizirajućem
  načinu rada: promjena stranice, pomicanje do slike, žuto obilježavanje.
  Dosad je klik ondje ostajao bez učinka, jer je zamjenske oznake još
  smatrao neoznačenima brojem – otkad svako mjesto nalaza nosi svoj
  vlastiti broj, mjesto je jednoznačno. Samo kod stvarno neoznačene
  zamjenske oznake statusni redak i dalje objašnjava zašto se odredište
  skoka ne može odrediti.
- Prvo spremanje u uređivaču za doradu (Ctrl+S ili gumb
  diskete) sada pita za mjesto, kao „Spremi kao …“ –
  unaprijed popunjeno mapom originala i nazivom rezultata. Dosad je
  datoteka bez pitanja završavala pored originala. Tko je mjesto pohrane
  već ranije odabrao preko statusnog retka, više se ne pita ponovno;
  svako daljnje spremanje kao dosad zapisuje istu datoteku.
- Javi li sigurnosna provjera prije spremanja upadljivo mjesto,
  „Natrag na provjeru“ sada vodi do njega: prvo mjesto nalaza pomiče se u
  prikaz i uokviruje crveno, statusni redak ga imenuje. Dosad se ostajalo
  samo s brojem stranice i koordinatama točke. Iz glavnog prozora se za to
  otvara uređivač na tom mjestu. I kod napomene o odstupajućem broju
  stranica gumb sada vodi do nje – na prvu stranicu koja postoji samo u
  jednom od dva dokumenta.
- Tko pregled prebaci na „Jedno pored drugog u dva stupca“, sada dobiva
  sam od sebe prozor u koji stanu obje trake – dosad su se stiskale u
  staru širinu, dok ih netko sam ne bi razvukao. Proširuje se najviše
  do ruba zaslona i nikad se ponovno ne sužava; ručno razvučena širina
  ostaje.
- Prezime i ime u odvojenim stupcima tablice (npr. „Prezime | Ime“
  u potvrdi prijave ili CSV izvozu) ostajali su otvoreni – svaka
  ćelija sama za sebe izgledala je za prepoznavanje kao proizvoljna riječ bez
  konteksta imena. Sada se prepoznaju.
- Prezime i ime na poleđini EU vozačke dozvole u obliku kartice ostajali su
  otvoreni – ondje stoje iza službenih šifri polja „1.“ i „2.“
  umjesto iza njemačke riječi, i upravo je to ostavljalo ih
  neprepoznatima. Sada se prepoznaju, kad je broj vozačke dozvole
  (šifra polja „5.“) pored.
- Ime vlasnika vozila na prometnoj dozvoli ostajalo je
  otvoreno – ono stoji iza službene šifre polja „C.1.2“ umjesto iza
  njemačke riječi poput „Vorname“, i upravo je to ostavljalo ga
  neprepoznatim. Prezime i ime ispod šifri polja C.1, C.1.1 i C.1.2 sada se
  prepoznaju.
- Prvi redak strojno čitljivog područja (MRZ) na putovnici ili
  osobnoj iskaznici ostajao je otvoren – on nosi ime u obliku
  „PREZIME<<IME“ i propuštao je i s novim MRZ prepoznavačem za
  redak kontrolne znamenke potpuno neopaženo. Nalaz se sada broji samo kad
  izravno pored njega stoji drugi MRZ redak s valjanom kontrolnom znamenkom – sam
  redak imena nema vlastitu kontrolnu znamenku.
- Drugi redak strojno čitljivog područja (MRZ) na putovnici ili
  osobnoj iskaznici ostajao je potpuno neprepoznat – on sadrži broj putovnice,
  datum rođenja i istjeka u čistom tekstu, ali nije pogađao nijedan
  postojeći prepoznavač. Zaseban prepoznavač sada provjerava četiri
  ICAO kontrolne znamenke.
- Registarska oznaka vozila bez ikakvog razmaka od oznake ostajala je
  otvorena – „KennzeichenM-AB1234“ ili „KFZ-KennzeichenM-AB1234“ uopće se
  nisu prepoznavali, jer temeljna provjera oznake pretpostavlja
  nealfanumerički znak ispred oznake. Pogađalo je podatke o vozilu kod kojih nije bilo
  razmaka između riječi polja i oznake.
- Telefonski broj bez ikakvog razmaka od oznake ostajao je otvoren –
  „Handynummer0171/2345678“ ili „Tel0171/2345678“ uopće se
  nisu prepoznavali, jer temeljna provjera telefonskog broja pretpostavlja
  razmak ili interpunkcijski znak ispred broja. Pogađalo je kontakt podatke kod
  kojih nije bilo razmaka između riječi polja i broja.
- Djevojačko prezime iza kratice „geb.“ uopće se nije prepoznavalo –
  „Julia Bergmann (geb. Weber)“ pronalazilo je samo „Julia Bergmann“, točka u
  „geb.“ natjerala je jezični model da sljedeće ime potpuno preskoči.
  Pogađalo je osobne podatke s djevojačkim prezimenom u zagradi ili iza zareza.
- Ime prije nadimka u navodnicima ostajalo je otvoreno, kad su
  oslovljavanje i titula zajedno stajali ispred – „Herr Dr. Klaus “KP“ Peters“
  davalo je samo „Peters“, „Klaus“ je ostajalo čitljivo. Pogađalo je potpise
  i kontakt podatke s titulom i nadimkom.
- Ime iza kratkog oblika bez točke „zH“/„zHd“ (na ruke) uopće se
  nije prepoznavalo – za razliku od „z.Hd.“ s točkom, nedostatak
  strukture rečenice povlačio je ime sa sobom. Pogađalo je adrese bez točke u
  kratici.
- Ime iza „p.A.“ (na adresi) uopće se nije prepoznavalo – točka
  u kratici natjerala je jezični model da prepoznavanje imena potpuno
  preskoči. Pogađalo je račune i molbe sa zajedničkom adresom.
- Ime iza bez točke nalijepljenog „i.A.“/„i.V.“ (u ime/u zastupanju) uopće se
  nije prepoznavalo, npr. „i.A.Robert Lang“ bez
  razmaka – ista pogreška strukture rečenice kao kod „p.A.“. Pogađalo je
  retke potpisa i potpise e-pošte u slučajevima zastupanja.
- Čisti popis prisutnosti u obliku nabrajanja bez ikakvog daljnjeg
  podatka („- Max Mustermann“, i s točkom na kraju retka) gubio je sva
  imena istoj kočnici koja zapravo treba štititi samo stvarne
  nabrajanja poput „- Farbe: Blau“. Takvi popisi sada se prepoznaju.
- Datoteke koje se više nisu mogle očistiti, ponovno se mogu
  očistiti. Vrijednost koja je već zamijenjena prepoznavanjem mogla se
  u vlastitoj, već zamijenjenoj oznaci poput „[SVNR1]“ ponovno pronaći
  – završna provjera je tada odbacivala besprijekorno očišćenu datoteku. Osim
  toga telefonski upit u CSV tablici sada se uklanja zajedno s ostalim, a tko
  ograniči pretragu na pojedine vrste, sada je dobiva posvuda u
  dokumentu jednako – i u alternativnom tekstu slike,
  zaglavlju Excela, padajućem popisu ili HTML atributu.
- Ime iza zaglavlja e-pošte „To:“ (ili „To“ bez dvotočke)
  nije se prepoznavalo, jer je strani jezični model čitao cijeli redak kao
  jedan jedini neupadljiv nalaz i pritom potpuno progutao ime unutra
  – za razliku od „Cc:“, „Bcc:“ ili „From:“ ispred istog
  imena. Ime iza „To“ sada se pouzdano pronalazi.
- Datum vjenčanja nije se u vlastitim pravilima mogao tretirati kao datum
  („pomakni“ je odbijalo s „postoji samo za datumske podatke“),
  nedostajalo je u skupnom pridruživanju vrsta nalaza – čime se preko
  oznaka „Što se traži“ nije moglo isključiti – i dobivao je umjesto
  kratke kratice kao kod datuma smrti puni tekst kao zamjensku oznaku.
  Nadograđeno za svih šest tablica kratica/oznaka.
- Vrijednost namjerno isključena u pregledu mogla se ipak zacrniti na
  drugom mjestu: odabere li se npr. e-mail adresa da se isključi,
  sama adresa je doduše ostajala, ali njezin lokalni dio bez domene
  zamjenjivao se čim bi se poklopio s izvedenim korisničkim imenom neke
  dalje odabrane osobe („anna.musterfrau@beispiel.de“ pored „Anna
  Musterfrau“). Isključena formulacija sada ostaje tabu u cijelom dokumentu,
  neovisno o tome iz koje vrste nalaza potječe.
- Datum rođenja ostajao je neprepoznat, kad ga je obiteljska knjiga ili
  izvadak iz matice vodio pod zajedničkim zaglavljem s
  mjestom rođenja („Geburtsdatum, Geburtsort: 19.11.1982, Steyr“) – druga
  riječ polja između „Geburtsdatum“ i datuma dosad je u potpunosti onemogućavala
  prepoznavanje.
- Već prepoznat telefonski broj ostajao je čitljiv u svom skraćenom
  obliku potvrde, kad je na drugom mjestu u istom dokumentu naveden samo
  posljednjim četirima znamenkama („dostupno na broju
  ...5678“, „povratni poziv na ...5678“) – isti oblik kao kod IBAN-a i
  kreditne kartice.
- Već prepoznat broj kreditne kartice ostajao je čitljiv u svom skraćenom
  obliku potvrde, kad je na drugom mjestu u istom dokumentu naveden
  samo posljednjim četirima znamenkama („Vaša kreditna kartica
  završava na ...0366“) – isti oblik uobičajen u potvrdama plaćanja
  kao kod IBAN-a.
- Već prepoznat IBAN ostajao je čitljiv u svom skraćenom obliku
  potvrde, kad je na drugom mjestu u istom dokumentu naveden samo
  posljednjim četirima znamenkama („IBAN završava na ...3201“) –
  oblik uobičajen u potvrdnim e-porukama.
- Govornik u zapisniku chata ili sjednice ostajao je neprepoznat, kad je
  ispred njegovog imena stajalo oslovljavanje („Herr Bauer: …“, „Frau Koch: …“) –
  i time je često pogađao i sljedeći redak govornika u istom zapisniku,
  jer je preostajalo premalo prepoznatih redaka da bi se dokument uopće
  ocijenio kao zapisnik.
- Datum rođenja ostajao je neprepoznat, kad je riječ polja „geboren“ stajala
  IZA datuma umjesto ispred njega („Das Kind wurde am 14.01.2026 geboren“) – tako
  npr. potvrda o roditeljskom dopustu ili zaštiti majčinstva formulira
  datum rođenja djeteta. Dosadašnji obrasci uvijek su pretpostavljali riječ polja
  ispred datuma.
- Oznaka obrasca s reakcijskim znakom ili kvačicom izravno ispred
  („Ansprechpartner 😊:“, „Kontaktperson ✓:“) više se nije prepoznavala kao
  oznaka, čime je ime ispod ili iza nje djelomično
  ostajalo samo nepotpuno pronađeno (npr. samo prezime kod „Mayer
  Roman“).
- Ista praznina pogađala je i posebno osjetljive podatke prema čl. 9
  GDPR-a (vjera, zdravlje, sindikat): reakcijski znak izravno
  ispred razdjelnika ili prijeloma retka („Konfession 😊: römisch-katholisch“)
  natjerao je oznaku da u potpunosti promakne, a podatak je
  ostajao potpuno neprepoznat.
- Adresa s dvostrukim imenom mjesta spojenim crticom (npr. „79761
  Waldshut-Tiengen“, „78050 Villingen-Schwenningen“) gubila je
  poštanski broj potpuno, iako se samo mjesto prepoznavalo i zacrnjivalo
  – na dokumentu vozila ili dopisu tako je poštanski broj
  ostajao čitljiv.
- Stupac tablice bez razmaka stupaca (stvaran PDF tekstualni izvadak) mogao je
  ispod stupca imena i dva slučajno susjedna velika slova
  pogrešno zacrniti kao osobu, npr. dva naziva mjesta u
  retku podataka; sada je to slučaj samo kad nijedan drugi
  nalaz na istom mjestu već ne prepoznaje nešto drugo.
- Isti stupac imena u istom obliku retka zacrnjivao je i dvije
  jezičnom modelu nepoznate stvarne riječi (npr. „Frontend Backend“, „Turbo
  Modul“) pogrešno kao osobu, jer ondje nijedan drugi nalaz nije
  aktivirao kočnicu; sada dodatno zahtijeva da barem jedna od
  te dvije riječi sam jezični model čita kao vlastito ime.
- Njemački broj mirovinskog osiguranja u svom službenom punom
  grupiranju (npr. „65 170839 J 08 8“ – onako kako stoji na
  iskaznici socijalnog osiguranja i platnoj listi) nije se prepoznavao i
  ostajao je u originalu; prepoznavali su se samo kompaktan zapis
  i oblik grupiran samo do slova.
- Porezni identifikacijski broj u svom službenom zapisu
  (grupiranje 2-3-3-3, npr. „48 836 075 988“ – onako kako stoji na svakom
  pravom poreznom rješenju i svakoj obavijesti Saveznog središnjeg ureda za
  poreze) uopće se nije prepoznavao i ostajao je u originalu; bilo je
  pokriveno samo rjeđe grupiranje 3-3-3-2.
- Porezni broj savezne pokrajine Sjeverna Rajna-Vestfalija (npr. „221/5147/0815“, s
  četveroznamenkastom umjesto troznamenkastom drugom grupom) uopće se
  nije prepoznavao u poreznim rješenjima i ostajao je u originalu –
  svaka druga savezna pokrajina bila je već pokrivena.
- Kod ugovora o radu ime iza oznake
  „Arbeitgeber:“ potpuno se previđalo, čim je prezime ujedno bilo
  obična riječ (npr. „Bauer Anna“) – „Arbeitgeber“ stoji u popisu i
  kao oznaka imena i kao oznaka tvrtke, a pridruživanje tvrtki
  prepisivalo je pridruživanje imena.
- U zaglavlju ugovora o najmu s oznakama „Vermieter:“/„Mieter:“
  previđalo se prezime koje je ujedno obična riječ (npr.
  „Bauer“) – prepoznavalo se samo ime. Numerirane
  strane najma („Mieter 1:“, „Mieter 2:“) bile su dodatno pogođene, čak
  i kod imena bez te dvoznačnosti.
- U sudskom zapisniku s oznakama „Zeuge:“/„Kläger:“/
  „Beklagter:“ (i s brojenjem, „Zeuge 1:“, „Zeuge 2:“) jednako se
  previđalo prezime koje je ujedno obična riječ (npr. „Bauer“) –
  prepoznavalo se samo ime.
- Kod potvrde o nasljeđivanju, punomoći, opomene i kupoprodajnog ugovora
  previđalo se prezime koje je ujedno obična riječ (npr. „Bauer“) iza
  oznaka poput „Erblasser:“, „Erbe:“, „Vollmachtgeber:“,
  „Bevollmächtigte:r“, „Antragsgegner:“, „Schuldner:“, „Gläubiger:“,
  „Käufer:“, „Verkäufer:“, „Vermächtnisnehmer:“ ili
  „Testamentsvollstrecker:“ – dijelom se prepoznavalo samo ime,
  dijelom je cijelo ime otpadalo.
- Kod popisa više stranaka ispred razdjelnika naslova predmeta „./.“ (npr.
  „Sand, Werner und Huber, Anna ./. Wechsler, Martina“) prva stranka
  ostajala je nemaskirana – prepoznavala se samo stranka koja izravno
  graniči s „./.“
- U razdjelniku naslova predmeta „./.“ (npr. „Sand./.Wechsler“) ime
  iza znaka potpuno se previđalo, kad ondje nije bilo razmaka
  – prepoznavanje je pogađalo samo s razmakom ispred i iza.
- Prezime „Wahr“ se potpuno previđalo, kad je stajalo samo
  (npr. „Frau Wahr bearbeitet Ihren Vorgang.“) – ta riječ slučajno
  stoji i na popisu uobičajenih njemačkih riječi, koji inače filtrira
  nalaze imena iz rečenica poput „Das ist wahr.“.
- Prezimena poput „Los“, „Weit“, „Rund“ ili „Hoch“ potpuno su se
  previđala, kad su stajala sama (npr. „Herr Hoch übernahm die
  Leitung.“) – sve četiri riječi slučajno stoje i na popisu
  uobičajenih njemačkih riječi, koji inače filtrira nalaze imena iz rečenica poput
  „Rund einhundert Gäste kamen zur Feier.“.
- Prezimena poput „Ganz“ ili „Recht“ potpuno su se previđala, kad su
  stajala sama (npr. „Herr Ganz unterschrieb den Vertrag.“) – obje
  riječi slučajno stoje i na popisu uobičajenih njemačkih riječi,
  koji inače filtrira nalaze imena iz rečenica poput „Ganz genau, das stimmt.“.
- Polje obrasca sa zvjezdicom ili eksponentom
  brojem fusnote izravno iza oznake (npr. „Konfession*:
  römisch-katholisch“ ili „Religionszugehörigkeit¹: evangelisch“) nije se
  prepoznavalo i ostajalo je u čistom tekstu – pogađao je samo oblik bez tog
  znaka.
- Isto polje ostajalo je i dalje u čistom tekstu, kad su odmah dva
  znaka fusnote stajala iza oznake (npr. „Konfession**:
  römisch-katholisch“ ili „Gewerkschaft¹²: ver.di“).
- Broj verzije poput „Softwareversion 4.2.1.19“ ili „Firmware Build
  2.0.4.11“ više se pogrešno ne zacrnjuje kao IP adresa. Isto
  sada vrijedi za brojeve dokumenata i predmeta poput „Rechnungsnummer
  10.20.30.40“ ili „Bestellnummer 7.8.9.10“.
- Dva IBAN-a izravno jedan ispod drugoga (npr. vlastiti i onaj
  inozemnog poslovnog partnera u zaglavlju računa) više se nisu
  oba prepoznavala – drugi je ostajao neopažen.
- Označen IBAN je ponekad povlačio sljedeću riječ u rečenici sa sobom
  (“Bankverbindung AT61 … wird belastet“ zacrnjivalo se sve do “wird“),
  čim je sljedeća riječ bila pisana malim slovom – ostatak čistog teksta
  pored pritom je ostajao netaknut.
- Adrese u Lihtenštajnu sada se prepoznaju („FL-9490 Vaduz“), kao
  dosad njemačke, austrijske i švicarske.
- Broj putovnice sada se prepoznaje i uklanja iza svoje oznake
  (npr. „Reisepassnummer: C01X00T471“).
- Broj dozvole boravka i potvrde o prijavi boravišta sada se prepoznaje i
  uklanja iza svoje oznake.
- Identifikacijska oznaka iza svoje oznake sada se prepoznaje i kad
  umjesto dvotočke razdvaja crtica (npr. „Kundennummer –
  K903944“).
- Bankovna veza označena kao „IBAN“ ili „Kontonummer“ sada se
  prepoznaje i kad umjesto dvotočke razdvaja crtica.
- Ime iza oznake poput „Kontaktperson (Vertrieb)“ ili
  „Sachbearbeiter/in“ sada se prepoznaje i s dodatkom u zagradi ili
  rodno neutralnim nastavkom s kosom crtom.
- Isti rodno obilježeni oblik sa zvjezdicom („Sachbearbeiter*in“) sada se
  također prepoznaje.
- Ime iza oznake sada se prepoznaje i kad
  umjesto dvotočke razdvaja znak jednakosti (npr.
  „Ansprechpartner = Mayer Roman“ ili „Kontaktperson=Mayer Roman“), kako je
  uobičajeno u konfiguracijskim datotekama ili CSV zaglavljima. Stoji li više
  takvih parova oznaka-vrijednost odvojenih točkom-zarezom u jednom retku, sada se
  prepoznaje samo prva vrijednost umjesto cijelog ostatka retka.
- Par GPS koordinata iza riječi „Koordinaten“ sada se pouzdano
  prepoznaje (npr. „Koordinaten: 48.2082, 16.3738“) – riječ je u internom
  katalogu nosila pogrešan oblik sklonidbe.
- Identifikacijska oznaka iza svoje oznake (broj kupca, broj ugovora,
  broj spisa, broj osobne iskaznice i još stotinjak drugih riječi polja)
  više se nije prepoznavala, čim oznaka nije točno odgovarala
  pohranjenom pisanju velikih/malih slova – „kundennummer:“ u
  e-pošti ili „KUNDENNUMMER:“ u zaglavlju obrasca ostajali su netaknuti.

### Novo

- **Realistične zamjenske vrijednosti sada su namjerno postavljen primjer
  umjesto zadane postavke.** Tablica iznimaka na kartici „Zamjenske oznake“ počinje
  prazna. Novi gumb ondje na zahtjev upisuje uvjerljive lažne vrijednosti za ime,
  mjesto, adresu, organizaciju, e-poštu, telefon, interni broj i IBAN. On
  izričito ostavlja novčane iznose kod numerirane zamjenske oznake; strategija
  „izmisli“ i dalje se za pojedine vrste može ručno birati.
- **AI razina može koristiti grafičku karticu.** Na Windowsu se za to
  može naknadno učitati dodatni paket od nepunih 17 MB; nakon toga AI razina
  na prikladnoj grafičkoj kartici radi znatno brže nego na procesoru.
  Tko je nema ili ništa ne učita, nastavlja raditi nepromijenjeno – samo
  sporije. Na macOS-u je ubrzanje ionako već ugrađeno.
- **Dvije nove obavijesti preko ikone u traci zadataka**: kad je pregled
  spreman za provjeru prije zamjene i kad je obrada gotova. Obje su
  unaprijed uključene i mogu se pojedinačno isključiti pod
  *Postavke → Program → Obavijesti*.

### Promijenjeno

- **Broj osobne iskaznice i vozačke dozvole sada se prepoznaje**, kad
  njihova oznaka stoji ispred („Personalausweisnummer: …“,
  „Führerscheinnummer: …“) – dosad su oba promašivala svako prepoznavanje.
- **Maskuro sada slijedi kontrastne izglede Windowsa.** Tko je pod
  *Postavke → Pristupačnost → Kontrastni izgledi* uključio jedan
  izgled, dosad ga je dobivao posvuda osim ovdje: Maskuro je nakon toga
  postavljao svoje vlastite boje. Sada ostaje pri izgledu sustava – prozor,
  popisi, zona za odlaganje, zapisnik i statusne boje. Obojeni semafor provjere u
  pregledu i prozoru za doradu ondje se namjerno izostavlja; ono što on govori
  otad ionako stoji kao znak i kao riječ pored.
- **Potreba provjere više ne stoji samo u boji.** Crvena, narančasta i
  zelena gotovo su jednako svijetle – tko ima slabovidnost na crveno-zeleno, vidio je u
  pregledu i ploči nalaza popis bez razlika, a to je otprilike
  svaki dvanaesti muškarac. Svaki redak sada dodatno nosi znak koji se
  razlikuje po obliku: ▲ provjeri prvo, ● provjeri, ○ dobro potkrijepljeno,
  ◆ bez ocjene. Kratka napomena to imenuje riječima, a
  čitač zaslona to izgovara.
- **Alt ponovno otvara izbornike kao i prije.** Traka izbornika nije imala
  tipkovničke kratice: tko ne koristi miša, morao se strelicama probijati kroz svaki
  izbornik. Sada svaka stavka nosi podcrtano slovo –
  Alt+D za „Datei“, odande B za „Beenden“ –, i to u svim
  jezicima sučelja.
- **Kontrole ponovno govore čitaču zaslona za što služe.**
  U prozoru za doradu, prozoru pravila, zapisniku, popisima riječi,
  pomoći, tijeku pretrage i pet daljnjih prozora popisi,
  polja pretrage, padajući popisi i klizači dosad su se najavljivali samo kao „stablo“ ili
  „kombinirano polje“ – bez toga čega. Oko četrdeset mjesta sada nosi
  ime. (Glavni prozor je bio ispravan od kolovoza; prozori
  koji su dodani nakon toga nikad nisu prošli taj korak.)
- **Tko upravlja tipkovnicom, posvuda vidi gdje se nalazi.** Na
  regulatorima potrebe provjere, na kućici i gumbu „nikad više“ u
  pregledu, na naslovima vrsta unutra, na bočnoj ploči stranica prozora za
  doradu i na bočnoj traci postavki nedostajao je
  okvir koji sustav inače stavlja oko kontrole na koju se skoči.
- **Veći sistemski font više ništa ne odsijeca.** Tko pod
  *Pristupačnost → Veličina teksta* postavi preko 175 %, dosad je gubio kraj
  oznaka u nadzoru mapa i u poljima tipkovničkih
  kratica. Popis poglavlja pomoći odsijecao je duge nazive poglavlja već kod
  obične veličine fonta; sada ih prelama i navodi puni
  naziv u kratkoj napomeni.

- **Prepoznavanje je postalo znatno brže.** Prepoznavač za
  označene identifikacijske oznake („Kundennummer: K903944“) dosad je po
  odsječku teksta provjeravao preko 1200 pojedinačnih obrazaca redom – to je
  bila najveća pojedinačna stavka vremena prepoznavanja, kod svakog odlomka i svake ćelije tablice.
  Sada je to jedan jedini obrazac s istim rezultatom: na mjernom korpusu
  se ne mijenja nijedan nalaz, osnovna razina po odsječku teksta postaje
  otprilike tri do četiri puta brža.
- **Prozor se pojavljuje odmah pri pokretanju.** Dosad je glavni prozor
  učitavao potpune jezične alate prije nego što se uopće prikazao – oko
  četiri sekunde slijepog vremena kod svakog pokretanja. Modeli se sada
  učitavaju u pozadini, kako je predviđeno, dok prozor već stoji;
  gumb za čišćenje kao i dosad postaje dostupan tek kad je sve spremno. I
  čisti informativni pozivi naredbenog retka (npr. `--version`) sada
  odgovaraju odmah umjesto nakon nekoliko sekundi.
- **Slike se kod automatskog prepoznavanja jezika sada čitaju samo
  jednom.** Dosad je prepoznavanje teksta kod zadane postavke
  „Jezik: automatski“ prolazilo dvaput preko iste slike - jednom za
  pretpostavku jezika, jednom za stvarnu provjeru. Slikovne datoteke,
  slike iz međuspremnika i prozor teksta time su gotovi otprilike dvostruko
  brže; kod isključenog prepoznavanja teksta dosad neprimjetno svejedno pokrenuto
  čitanje potpuno otpada.
- **Spremljene web stranice i e-pošta čiste se brže.** Vrijednosti
  u HTML atributima, komentarima i ugrađenim blokovima podataka
  dosad su se prepoznavale pojedinačno – stranica općine sa stotinama
  oznaka postavljala je stotine pojedinačnih upita prepoznavanju. Sada
  se prikupljaju i po različitoj vrijednosti prepoznaju samo jednom;
  na mjernom korpusu se ne mijenja nijedan nalaz, .html i .eml su oko
  trećinu brži.
- **I sporedni spremnici tablica i prezentacija sada se prepoznaju u
  skupinama.** Alternativni tekstovi, formule kao nizovi znakova, oznake dijagrama,
  komentari, privremena pohrana pivot tablica i svojstva dokumenta postavljali su po
  vrijednosti vlastiti upit prepoznavanju – radna knjiga s tisućama pivot redaka
  odgovarajuće tisuće upita. Sada se odvija skupni prolaz kroz
  različite vrijednosti, a naknadni potpuni prolaz na kraju izvodi se
  samo kad su od teksta stvarno dodane nove vrijednosti.
  Na mjernom korpusu se ne mijenja nijedan nalaz.
- **PDF-ovi bogati obrascima čiste se brže.** Polja, napomene,
  oznake i poveznice ponavljaju iste vrijednosti masovno
  („Off“ na svakom polju za kvačicu, isti autor na svakoj napomeni) –
  svaka je dosad postavljala vlastiti upit prepoznavanju. Po prolazu se
  vrijednost sada prepoznaje samo jednom; zamjena i naknadna provjera
  dosljednosti i dalje se izvode po mjestu nepromijenjeno.
- **Velike tablične datoteke (.csv/.tsv) čiste se znatno brže.**
  Četiri naknadna prolaza tablica dosad su istu datoteku svaki
  zasebno rastavljali znak po znak u ćelije (kod 40 MB oko 30 s
  dodatnog rada); sada se rastavljanje izvodi jednom. Prepoznavanje zaglavlja stupca
  (stupci datuma rođenja i osobnih brojeva) postavlja umjesto pitanja po
  ćeliji jedno skupno – kod istovjetnih nalaza otprilike dvadeset puta
  brže. A sažimanje stupaca imena velikih popisa osoblja
  više nije kvadratno u broju redaka.
- **Klapna s ključnim pokazateljima više ne zamrzava prozor.** Otvaranje
  klapne s pokazateljima kod mnogih velikih datoteka najprije je sabiralo njihov
  tekst i pritom prozor sekundama ostavljalo mirnim. Izračun se sada
  odvija u pozadini; klapna se otvara odmah i naknadno unosi brojeve.
- **Izvještaj tijeka pretrage više ne zamrzava prozor.** Nakon
  pretrage više tisuća datoteka zajednička mapa se za svaku
  pogođenu datoteku ponovno izračunavala; kod velikih prolaza prozor je time
  stajao dvoznamenkaste sekunde. Izvještaj se sada pojavljuje odmah.
- **PDF-ovi s prepoznavanjem teksta provjeravaju se brže.** Svaka stranica se kod
  usporedbe nepotrebno dvaput pretvarala u PNG format; sada se
  proslijeđuje već postojeća slika. Rezultat je nepromijenjen, samo je provjera
  brža.
- **Napomene s prijelazom na velikim slikama više ne trzaju.** Kod
  povlačenja rukohvata napomene s prijelazom prijelaz se dosad
  ponovno izračunavao točku po točku – na velikoj snimci zaslona
  vidljivo zastajkivanje. Rezultat je isti, samo bez zastoja.

### Otklonjeno

- **Križić za uklanjanje datoteke s popisa opet je jednostavan X.** Novi
  alat uređivača „Ukloni“ slučajno je koristio istu oznaku simbola i
  time svoj crveni križić zajedno s isprekidanom crtom teksta pokazivao
  i u svakom retku datoteke. Obje radnje sada imaju
  odvojene nazive simbola i zadržavaju svaki svoj odgovarajući
  prikaz.
- **Višedijelni podaci u PDF-ovima sada se prepoznaju i preko vidljivog
  prijeloma retka.** Maskuro sada geometrijski stvoren tekst stranice
  dodatno čita i kao pogledom s istim odmakom u tekstu. To vrijedi za sve
  prepoznavače osnovne i visoke razine te vlastite obrasce pretrage, ne samo za
  prvi vidljivi slučaj „Diabetes mellitus Typ 2“. Prazni retci i prepoznate
  granice tablica ili odjeljaka ostaju čvrste granice; mjesta nalaza i dalje
  točno odgovaraju riječima koje se zacrnjuju.
- **Primjer kod „Pseudonimizacija“ sam sebi je proturječio.** Rečenica
  je obećavala „ista osoba, isti broj“, a zatim je prikazivala dva
  različita broja – upravo sliku koja je ispravna kod „Anonimizacija“.
  Oba primjera sada odgovaraju vlastitoj rečenici.
- **Netom umetnuta zamjenska oznaka mogla je kod „Vrati original“
  ostati kao naslagana hrpa slova umjesto da nestane.** Jednobojno
  umetnuta zamjenska oznaka dosad je pisala vlastitu izlaznu naredbu po
  znaku, od kojih je samo prva nosila vlastitu tekstualnu matricu –
  pri sljedećoj obradi istog mjesta (npr. „vrati“ izravno nakon toga)
  ostale su naredbe znakova redom preuzimale indekse znakova prve, a
  zamjenska oznaka se raspadala na dva preklapajuća položaja. Jednobojna
  zamjenska oznaka sada dobiva jednu jedinu izlaznu naredbu za cijeli svoj tekst.

- **Stajala li je ista zacrnjena ili uklonjena vrijednost pod dva retka u
  prozoru za doradu i bila oba označena za vraćanje, drugi je redak pogrešno
  brojen kao „nejednoznačan“ – iako je vrijednost odavno vraćena.**
  Oba retka sada vrijede kao dovršena.

- **Ime iza „Reply-To:“ sada se pronalazi.** U zaglavlju e-pošte
  poput „Reply-To: Huber“ ime je dosad ostajalo potpuno neprepoznato – jezični
  model čitao je „Reply-To:“ kao vlastitu, pogrešnu osobu i previđao
  stvarno ime iza njega.

- **Riječi zaglavlja e-pošte „Reply“ i „Fwd“ više se same ne zacrnjuju kao
  ime.** U retku predmeta poput „Fwd: Angebot von Huber“
  dosad se uz ime dodatno prepoznavala i sama riječ zaglavlja kao osoba
  te zacrnjivala.

- **„Arbeitgeber: Siemens AG“ sada se prepoznaje kao tvrtka, ne više kao
  osoba.** Nosila li je vrijednost tvrtke iza oznake „Arbeitgeber“ pravni
  oblik poput GmbH, AG ili KG, ostajala je unatoč uključenom
  prepoznavanju organizacija nalaz osobe – samo uži slučaj bez
  pravnog oblika („Wollmuth und Partner“) dosad se prepoznavao kao tvrtka.

- **Jednom prepoznata adresa više ne ostaje na drugom mjestu.**
  Prepozna li se i zamijeni adresa ulice na jednom mjestu,
  ista je adresa mogla ostati na drugom mjestu – npr. u
  teško čitljivoj nožnoj bilješci skeniranog dokumenta, gdje ju je
  automatsko prepoznavanje teksta čitalo unakaženo. Adrese se sada, kao
  već dulje imena i tvrtke, dosljedno uklanjaju u cijelom dokumentu.

- **E-pošta s više primatelja tiho se oštećivala pri čišćenju.**
  Poruka `.msg` s dva ili više primatelja gubila je pri spremanju
  dijelove svoje unutarnje strukture, tako da je očišćeni rezultat bio
  nepotpun. Uzrok je bila zamjena istoimenih unutarnjih dijelova,
  koji se pojavljuju kod svakog primatelja. Takve poruke sada se
  potpuno ponovno grade.

- **Dvije od isporučenih testnih dokumenata nisu se dale otvoriti u Wordu i
  PowerPointu.** Tko je preuzeo mjerni korpus, dobivao je kod
  `format_dokument.docx` „Fehler beim Öffnen der Datei in Word“ i kod
  `format_praesentation.pptx` „Die Datei ist beschädigt“. Obje datoteke
  bile su neispravne već prije nego što ih je Maskuro dotaknuo – očišćena
  inačica pogrešku je samo prenijela dalje. LibreOffice je obje
  otvarao bez problema, zbog čega to nikome nije upalo u oči.

- **Vlastita AI na internetu sada se oslovljava šifrirano.** Tko
  kod vlastite AI unese vanjsku adresu bez „https://“ (kako često
  stoji na listiću IT-a), dosad ju je dosezao preko
  nešifrirane veze – nezacrnjeni tekst išao je van u čistom tekstu.
  Takve adrese se sada oslovljavaju preko „https://“; poslužitelj u
  vlastitoj mreži ostaje dostupan nepromijenjeno. Slijedi li poslužitelj preusmjeravanje
  na drugo računalo, pristupni ključ se više ne prenosi dalje s njim.

- **I oštećena slika sada gubi svoje skrivene metapodatke.**
  Nije li se ugrađena slika više dala potpuno otvoriti (npr.
  odsječena fotografija), dosad je zadržavala svoje EXIF i GPS podatke –
  mjesto snimanja i ime fotografa ostajali su nevidljivi u rezultatu. Takve
  slike se sada oslobađaju tih podataka i kad se
  uopće više ne mogu prikazati.

- **Ugrađena datoteka koja se nije dala očistiti sada se
  prijavljuje umjesto da tiho prođe dalje.** Nalazio li se u prezentaciji ili
  radnoj knjizi ugrađeni objekt koji je bio predubok umetnut ili se
  nije dao otvoriti, dosad je ostajao nepromijenjen u rezultatu, bez napomene –
  datoteka se smatrala očišćenom. Takvi slučajevi sada stoje u upozorenju
  „NISU mogli biti provjereni“, jednako kao ugrađen stari format.

- **Tamni popisi ponovno su dosljedno tamni i čitljivi.** Na macOS-u su
  popisi datoteka izmjenjivali gotovo crne i svijetlosive retke; u
  doradi je time ista zelena, narančasta ili crvena vrijednost provjere ovisno o
  retku izgledala drugačije. Prozor, popisi, font, zamjenske oznake i odabir dolaze
  sada iz zajedničke svijetle/tamne palete. Bojom kodirani
  popis nalaza osim toga više ne postavlja zebraste pruge ispod svojih boja.

- **Podaci o zanimanju s „als“ pogrešno su se zacrnjivali kao ime.** Rečenica
  poput „Als Koch ist er seit vier Jahren bei uns tätig.“ gubila je zanimanje,
  ne samo ime – „als“ uvodi podatak o ulozi jednako kao „der“
  ili „die“. Stvarna prezimena na istom mjestu (npr. s oslovljavanjem
  ispred) ostaju netaknuta.

- **Zaglavlje tablice moglo je uvući broj pozicije u novčani iznos**
  (samo kod uključene opcije „Ukloni i novčane iznose“). Završavao li
  redak valutom („… Einzelpreis EUR“) i počinjao li sljedeći brojem,
  od toga je pogrešno nastajao iznos preko prijeloma retka. Razdjelnik
  između valute i broja sada ostaje u istom retku.

- **Kratka kratica velikim slovima mogla je progutati cijeli dio rečenice
  ili se zalijepiti ispred ispravno prepoznatog imena.** Stajala li je
  u retku dvoslovna riječ velikim slovima poput „DI“, „AG“ ili „KG“ –
  svakodnevne kratice, ne imena –, cijeli redak se pokusno pretraživao
  pisan malim slovima, a kratica je pritom povremeno povlačila
  susjedne riječi (i glagole) u jedan navodni jedini nalaz imena.
  Tek od tri slova naviše velika riječ sada pokreće tu
  drugu provjeru. Kod nešto duljih kratica poput „CEO“ ili „USB“
  ostajala je druga pogreška: već ispravno pronađeno ime („Schneider“)
  dobivalo je ispred stavljenu kraticu kao predmetak uvučen u rezultat
  („CEO Schneider“). Kratica sada ostaje izvan toga.

- **Datum rođenja bez razmaka iza njega ostajao je nezacrnjen.** Stajala li
  je iza „geb.“ bez razmaka ispred datuma – kako je uobičajeno u usko
  postavljenim obrascima („geb.14.03.1988“) –, Maskuro nije prepoznavao
  polje i ostavljao je datum netaknut. Rašireni kratki oblici poput
  „Geburtsdat.“ ili „Geb.-Dat.“ sada se također prepoznaju.

- **IBAN s kosim crtama kao razdjelnicima ostajao je nezacrnjen.** Kao kod
  telefonskih brojeva („0664/1234567“) neki predlošci pišu i IBAN
  u blokovima s kosom crtom („AT48/3200/0000/1234/5864“) umjesto s
  razmakom ili crticom. Taj se zapis sada također
  prepoznaje.

- **Austrijski broj socijalnog osiguranja s crticom, točkom
  ili kosom crtom ostajao je nezacrnjen ili je bio pogrešno označen.** Između
  dva bloka brojeva dosad je bio predviđen samo razmak;
  zapisi poput „1237-010180“, „1237.010180“ ili „1237/010180“
  nisu se prepoznavali (ili su se kod slučaja s kosom crtom prepoznavali pod pogrešnom vrstom).
  Kontrolna znamenka i dalje potvrđuje svaki nalaz, neovisno od
  razdjelnika.

- **Ime iza „c/o“ u adresi uopće se nije
  uklanjalo.** „c/o Max Mustermann, Hauptstraße 5, 1010 Wien“ zacrnjivao je
  ulicu i mjesto, ali je ime iza toga ostavljao potpuno netaknuto. Ime
  se sada prepoznaje; „c/o“ samo ostaje vidljivo kao naznaka
  adrese.

- **Broj kreditne kartice grupiran točkama ostajao je nezacrnjen.**
  Zapisi poput „4111.1111.1111.1111“ nisu se prepoznavali; brojevi
  razdvojeni razmakom ili crticom time nisu bili
  pogođeni. Kontrolna suma i dalje potvrđuje svaki nalaz.

- **Porezni identifikacijski broj grupiran crticama ostajao je
  nezacrnjen, jednako i austrijski PDV ID s crticom ili točkom.**
  Razmak, kosa crta i točka kod poreznog ID-a bili su već
  predviđeni, crtica je nedostajala; kod PDV ID-a („ATU12345678“) nedostajali su
  crtica i točka iza prefiksa. Kontrolna znamenka poreznog ID-a
  i dalje potvrđuje svaki nalaz.

- **Vrijednost polja u navodnicima ostajala je nezacrnjena, npr. u
  retku nalik JSON-u poput „vorname“: „Max“.** Prepoznavanje preko
  oznake polja („Vorname: …“) dosad je pretpostavljalo da ni
  oznaka ni vrijednost sama ne stoje u navodnicima. Takvi
  retci sada se također prepoznaju – jednako i oznake polja s
  YAML znakom popisa ispred („- Vorname: Max“) ili
  tabulatorom umjesto razmaka ispred dvotočke.

- **Riječ zaglavlja e-pošte „Sent“ sama se zacrnjivala kao ime.**
  U zaglavlju poput „Sent: Huber“ dosad je pogađalo i „Sent“ i
  stvarno ime; srodne riječi zaglavlja poput „Subject“ ili
  „Betreff“ oduvijek su ostajale netaknute. „Sent“ sada isto tako
  ostaje netaknut.

- Ime iza zaglavlja „Errors-To:“ ili „Resent-From:“ ostajalo je
  neotkriveno, kad je takav redak stajao kopiran u čistom tekstu (npr.
  proslijeđena poruka ili izvještaj o incidentu) – za razliku od
  „Reply-To:“ ili „Return-Path:“ ime je ovdje potpuno otpadalo umjesto da
  bude samo netočno omeđeno. Sada se pronalazi.
- Ista datoteka pri dva čišćenja davala je ponekad
  drugačiji rezultat: pogodila li su dva prepoznavanja točno isto mjesto
  s jednakom duljinom i jednakom sigurnošću (npr. „Sozialversicherungs-
  nummer 1237/010180“ kao AT_SVNR ili kao opća identifikacijska oznaka), o slučaju je
  ovisilo koje pobjeđuje – vrijednost se u oba slučaja
  uklanjala, mijenjala se samo oznaka zamjenske oznake. Neriješeni ishod sada se
  uvijek rješava jednako.
- Naziv funkcije izravno ispred imenice (npr. „Behandelnder
  Arzt: Dr. …“ ili „Zuständiger Sachbearbeiter ist …“) ponekad se
  pogrešno zacrnjivao kao da je sam ime. Stvarna prezimena
  pored toga ostaju netaknuta.
- Stvarno prezime koje slučajno izgleda kao pridjev
  (npr. „Schöne“, „Lange“, „Junge“) i stoji izravno ispred još jedne
  imenice (npr. „Kontaktperson: Schöne Assistentin“), otkad je posljednji put otklonjeno
  ostajalo je nezacrnjeno u tekstu – curenje podataka. Sada se u ovom obliku
  kao ne-ime tretira samo usko ograničen popis stvarnih naziva funkcija
  (npr. „Behandelnder“, „Zuständiger“).
- Samostalno prezime na kraju višerednog nalaza imena, koje
  slučajno izgleda kao pridjev (npr. „Schwarz“,
  „Kurz“, „Alt“, „Frisch“, „Gut“, „Reich“), ostajalo je neprepoznato ispred
  izravno sljedeće dvotočke – čišćenje ga je zamijenilo
  s oznakom polja poput „Telefon:“. Zatvoren popis
  poznatih dvoznačnih prezimena sada ga štiti.
- Samostalno prezime koje je slučajno obična njemačka
  riječ („Gross“/„Grosse“, „Gut“, „Kurz“, „Lang“/„Lange“), dosad se
  **potpuno** gubilo – i u jednostavnim rečenicama poput „Herr
  Gross unterschrieb den Vertrag.“ Razlog je bio u vlastitom spaCy
  popisu praznih riječi, koji te riječi sadrži; zatvoren popis
  poznatih prezimena sada ih čuva od odbacivanja.
- Kod ugovora o radu, zajmu, jamstvu, povjereništvu i insolvenciji
  te skrbništvu/starateljstvu i naloga za vještačenje previđalo se
  prezime koje je ujedno obična riječ (npr. „Bauer“) iza
  oznaka poput „Auftraggeber:“, „Auftragnehmer:“, „Arbeitnehmer:“,
  „Versicherter:“, „Darlehensgeber:“, „Darlehensnehmer:“, „Bürge:“,
  „Sicherungsgeber:“, „Treuhänder:“, „Treugeber:“, „Insolvenzverwalter:“,
  „Gutachter:“, „Sachverständiger:“, „Vormund:“ ili „Pfleger:“ –
  dijelom se prepoznavalo samo ime, dijelom je cijelo ime otpadalo.
- U impresumu se previđalo prezime koje je ujedno obična riječ
  (npr. „Bauer“) iza oznaka „Geschäftsführer:“,
  „Geschäftsführerin:“, „Vertretungsberechtigt:“, „Inhaber:“ ili
  „Inhaberin:“ – kod „Geschäftsführer:“/„Inhaber:“ cijelo je
  ime otpadalo, kod „Vertretungsberechtigt:“ prepoznavalo se samo ime.
- Kontakt blok čija je oznaka sama stajala u svom retku i nosila
  rodno neutralan oblik s dvotočkom („Ansprechpartner:in“, ime
  ispod), **potpuno** se previđao – dvotočka se čitala kao
  razdjelnik polja, „in“ kao (odbačena) vrijednost polja, a stvarno
  ime u sljedećem retku time nikad više nije dolazilo na red. Oblik sa zvjezdicom
  („Ansprechpartner*in“) time nije bio pogođen.
- Stajali li su ime i oznaka s istim rodnim oblikom s dvotočkom u
  **jednom** retku („Ansprechpartner:in Anna Berger“), zamjenska oznaka je
  povlačila riječ „in“ u zamjenu sa sobom, umjesto da uklanja samo ime –
  samo ime se i dalje potpuno obuhvaćalo.
- Ime u stupcu tablice ispod zaglavlja stupca za osobu (npr.
  „Name Vorname Geburtsdatum“ iznad „Bauer Anna 03.05.1985“, kao u
  obračunu plaće) potpuno se previđalo, čim je između
  stupaca stajao samo jedan razmak i nijedan redak nije počinjao
  brojem gliedbe – upravo oblikom u kojem stvaran
  PDF tekstualni izvadak takve retke isporučuje.
- U zapisniku chata ili sjednice s imenom govornika ispred
  dvotočke (npr. „Bauer 🙂: Ich stimme dem Vorschlag zu.“) ime je
  potpuno ostajalo neprepoznato, čim je reakcijski znak stajao između imena
  i dvotočke, a prezime je ujedno bila obična riječ
  („Bauer“, „Koch“, „Schneider“ i slično) – cijeli zapisnik
  time je mogao ostati bez ijednog prepoznatog govornika.
- Ista praznina retka govornika postojala je i s drugim znakovima između
  imena i dvotočke: dodatkom statusa u zagradi („Bauer (Vorsitz):
  …“, „Bauer (abwesend): …“), vremenom u uglatim zagradama
  („Bauer [14:32]: …“) i znakom fusnote izravno uz ime
  („Bauer*: …“). I ovdje je govornik ostajao potpuno neprepoznat,
  čim je prezime ujedno bila obična riječ.
- Stajala li je već prepoznata osoba u priloženom isječku zapisnika ili
  loga iste poruke (npr. tiket podrške) dodatno
  kao korisničko ime u obliku „ime.prezime“ – pisano malim slovima,
  bez razmaka, povezano točkom –, to je čisto ime
  ostajalo čitljivo, iako je isto ime u dopisu već bilo
  zacrnjeno.
- Ista praznina korisničkih imena postojala je i s podvlakom umjesto
  točke („ime_prezime“) – jednako raširen format u
  isječcima zapisnika i loga.
- I u obrnutom redoslijedu korisničko ime ostajalo je čitljivo
  („prezime.ime“ odnosno „prezime_ime“) – neki sustavi stavljaju
  prezime ispred u korisničkom imenu loga umjesto na kraj.
- Datum smrti ostajao je neprepoznat, kad pored njega nije stajao nikakav drugi
  podatak („Herr Bauer ist am 12.03.1985 verstorben“) – za to dosad
  uopće nije postojalo vlastito prepoznavanje, a generički datum ne pogađa kod
  tog standardnog praga.
- Datum smrti ostajao je neprepoznat i kad je rečenica koristila glagolski oblik
  umjesto participa („Frau Meier verstarb am 12.03.1985“,
  „Er starb am 12.03.1985“) – dosad je pogađalo samo „ist … verstorben“/„ist … gestorben“.
- Datum vjenčanja ostajao je neprepoznat, u kojem god obliku stajao
  („Eheschließung am 12.03.2010“, „Hochzeitsdatum: 12.03.2010“, „Herr und
  Frau Bauer heirateten am 12.03.2010“) – za to dosad uopće nije postojalo
  vlastito prepoznavanje, a generički datum ne pogađa kod tog
  standardnog praga.

- **U uređivaču za doradu drugi okvir preko upravo umetnute
  zamjenske oznake mogao je ostaviti crveni ostatak znaka**, npr.
  „[G“ umjesto „[BEG1]“ – bez ikakvog upozorenja, jer ostatak više nije
  pripadao povjerljivom podatku (taj je odavno uklonjen u prvom
  koraku), nego samo vlastitoj zamjenskoj oznaci. Razlog je bio u bojanju: novo
  umetnuta zamjenska oznaka pisala se u datoteku znak po znak,
  čak i kod jednobojne postavke – kasniji okvir preko istog mjesta
  time više nije nalazio povezan tekst na koji bi se
  mogao smjestiti. Sada jednobojna zamjenska oznaka stoji kao jedan
  komad u toku, kako je automatsko čišćenje oduvijek radilo; samo
  stvaran prijelaz ili duga-tekst i dalje trebaju pojedinačne
  znakove. Ugrađena protuprovjera sada takav ostatak prepoznaje dodatno
  i kad se točan niz znakova zamjenske oznake više ne pojavljuje.
- Numerirani popis imena sa stupnjevanim brojem gliedbe
  („1.1 Max Mustermann“, „1.2 Huber Franz“ …) gubio je sva imena
  istoj kočnici koja zapravo treba štititi samo stvarne
  strukture i popise pozicija – bez zaglavlja stupca iznad popisa nije
  bilo svjedoka na kojem bi se ime moglo spasiti.
- Ime u engleskom retku prijave sistemskog zapisnika
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2“)
  nije se prepoznavalo – njemački jezični model pronalazio ga je samo ako je
  ispred stajalo „invalid user“, inače je ostajalo. Takvi isječci zapisnika
  često se nepromijenjeni prilažu izvještaju o incidentu. Imena iza „for“
  ispred IP adrese sada se pouzdano prepoznaju.
- Ime obveznika plaćanja u SEPA referenci naloga izvoda
  računa ili dnevnika knjiženja (npr. „MREF+Mustermann Klaus+SVWZ+
  Miete August“) ostajalo je otvoreno – nema razmaka, nema strukture
  rečenice, samo poljima velikih slova razdvojenim znakom „+“, a u
  ondje uobičajenom redoslijedu „Nachname Vorname“ prepoznavanje ga ni
  slučajno nije pronalazilo. Sada se prepoznaje.
- Ulica zajedno s kućnim brojem u prvom retku tablice adresa
  (npr. „Nachname | Vorname | Straße | PLZ | Ort“) ostajala je otvorena –
  jezični model pogađao je ondje pogrešno, ali dulje mjesto preko
  više stupaca, koje je istisnulo ispravan, kraći
  nalaz adrese. Sada se prepoznaje.
- Isto curenje pojavljivalo se s tabulatorom umjesto „|“ ili „;“ kao
  razdjelnikom stupaca – ondje je adresa čak potpuno nestajala umjesto
  da se samo djelomično gubi. Sada se prepoznaje.
- Ulica s kućnim brojem ostajala je otvorena, kad je izravno nakon nje bez
  razmaka slijedio poštanski broj sa zarezom (npr. „Bahnhofstrasse
  12,80331 München“, kao u tablici stupca razdvojenoj zarezom) –
  zarez je izgledao kao decimalno mjesto neke količine, i ulica se
  obrascu zbog toga uopće nije smatrala adresom. Sada se prepoznaje.
- Ulica s kućnim brojem ostajala je otvorena, kad je izravno nakon nje bez
  zareza slijedio predmetak mjesta „St.“ (Sankt) (npr. „Hauptstraße 5 St.
  Pölten“, zaglavlje pisma bez ispred navedenog poštanskog broja) – „St.“ je izgledao
  kao jedinica komada, i ulica se obrascu zbog toga uopće nije
  smatrala adresom. Sada se prepoznaje.
- Dodatak vrata/stubišta iza kućnog broja (npr. „Lerchenfelder
  Gürtel 43/12“) ostajao je vidljivo otvoren, kad je izravno nakon njega stajalo
  jedno slovo koje se slučajno poklapa s mjernom jedinicom (npr.
  „h“ za sat) – adresa se tada čistila samo do kućnog broja bez
  svog dodatka, umjesto da pogodi potpuno ili nikako.
- Redak predmeta s prezimenom istovjetnim nazivu zanimanja ispred
  imena („Betreff: Bauer Anna“, „Betreff: Bauer, Anna“) dosad je
  ostajao potpuno neprepoznat – i usred dokumenta s prethodnom
  cijelom rečenicom. Sada se prepoznaje.
- Njemački porezni broj s razmakom, točkom ili crticom
  između blokova (npr. „Steuernummer: 30 815 08153“ ili
  „30.815.08153“) dosad se nije prepoznavao – pronalazio se samo zapis sa
  kosom crtom. Sada se prepoznaje.
- Ime iza medicinske oznake polja („Patient:“,
  „Hausarzt:“, „Behandelnder Arzt:“, „Überweisender Arzt:“ i njihovi
  ženski oblici) dosad se nije prepoznavalo, kad je prezime ujedno bilo
  obična njemačka riječ (npr. „Patient: Bauer Thomas“).
  Sada se prepoznaje.
- Ime iza oznake polja „Zahnarzt“ u vlastitom retku (npr.
  „Zahnarzt“, ispod „Huber Franz“) dosad se nije prepoznavalo – ni ime,
  ni prezime. „Zahnärztin“ i jednostavan oblik „Arzt“ time nisu
  bili pogođeni. Sada se prepoznaje.
- Prezime iza „Herr“/„Frau“, iza kojeg je slijedila službena
  fraza poput „zur Kenntnisnahme“, „zur Unterschrift“ ili „zur Weiterleitung“,
  dosad je bilo obuhvaćeno preširoko i povlačilo je frazu u nalaz imena
  sa sobom – iz „Frau Petra Klein zur Vertretung in allen Angelegenheiten“
  zamjenjivalo se „Petra Klein zur Vertretung“, a ostatak rečenice ostajao je
  gramatički unakažen. Stvarni plemićki predikati poput „von der Leyen“
  ili „zu Guttenberg“ time nisu bili pogođeni.
- Ista preredakcija zbog službene fraze skrivala se i iza imena
  u zaglavlju e-pošte „To:“, šifri registracije (C.1/C.1.1/C.1.2),
  šifri vozačke dozvole, poljem obrasca u zagradi
  („[Vorname]: …“) i pozdravnom formulom bez točke – svugdje je
  „zur“/„von“ i slično povlačilo sljedeću frazu poput „zur Unterschrift“ ili
  „zur Vertretung“ u nalaz sa sobom, dijelom je čak i sama
  čestica ostajala kao ostatak imena u rezultatu. I ovdje
  stvarni plemićki predikati ostaju potpuno sačuvani.
- Matični broj iza svoje oznake dosad se uopće nije
  prepoznavao – „Matrikelnummer 7654321“ potpuno je promašivao prepoznavanje,
  ni kao identifikacijska oznaka ni preko jezičnog modela, jer sam broj
  nema prepoznatljiv oblik.
- Isto je vrijedilo za broj sudionika – „Teilnehmernummer 4471829“ potpuno
  je promašivao, ni kao identifikacijska oznaka ni preko jezičnog modela.
- U životopisu ime ispod naslova odjeljka „Persönliche
  Daten“ često je potpuno ili djelomično promašivalo prepoznavanje, kad je
  bez oslovljavanja u obliku „Nachname Vorname“ stajalo izravno ispod.
- Isto je vrijedilo za naslov odjeljka „Kontaktdaten“ – ondje je
  ime čak potpuno promašivalo, ne samo djelomično.
- U potvrdi o prijavi boravišta ili popisu zahtjeva sa spojenim
  stupcem „Name, Vorname“ (zapis matičnog ureda, vrijednost npr.
  „Mustermann, Max“ u jednoj ćeliji) ime je potpuno promašivalo
  prepoznavanje, kad je slijedio još jedan stupac poput datuma rođenja.
- Datum rođenja u obliku uobičajenom na osobnoj iskaznici i potvrdi o
  prijavi boravišta „Geburtsdatum/-ort: 22.07.1978 / Rostock“ nije se
  prepoznavao – pogađao je samo oblik sa zarezom „Geburtsdatum, Geburtsort: …“.
- „Bürgerservice“ i „Bürgerbüro“ povremeno su se pogrešno zacrnjivali kao mjesto,
  osobito iza crtice kao razdjelnika nabrajanja
  (npr. „Wenden Sie sich an das Bürgerservice – Bürgerbüro …“).
- Označen telefonski broj koji je prijelom retka prekinuo usred
  (npr. iz uskog stupca zaglavlja pisma ili PDF izdvajanja teksta
  po širini stupca: „Telefon: 0176 12\n34567“), dijelom se zacrnjivao samo
  napola – ostatak iza prijeloma retka ostajao je čitljiv.
- Označena identifikacijska oznaka (broj kupca, člana, ugovora i
  slično) koju je prijelom retka prekinuo usred (npr. „Kundennummer:
  K903\n944“ iz uskog stupca), zacrnjivala se samo napola –
  ostatak iza prijeloma retka ostajao je čitljiv.
- Ime s akademskom titulom ispred naziva zanimanja iza zareza
  (npr. „Dipl.-Ing. Sabine Roth, Projektleiterin“) ostajalo je potpuno
  nezaštićeno – redak je izgledao kao tablično zaglavlje stupca
  i pogrešno se odbacivao kao stvaran sadržaj.
- Titula „Dr.-Ing.“ (čest njemački inženjerski stupanj) ispred
  imena nije bila uključena u maskiranu vrijednost osobe i ostajala je
  čitljiva – ista zamka s crticom kao kod „Dipl.-Ing.“.
- Titule „Dipl.-Kfm.“, „Dipl.-Kffr.“ i „Dipl.-Psych.“ (diplomirani
  ekonomist/ekonomistica/psiholog) ispred imena nisu bile uključene u
  maskiranu vrijednost osobe i ostajale su čitljive – ista
  zamka s crticom kao kod „Dipl.-Ing.“ i „Dr.-Ing.“.
- MAC adresa u Cisco zapisu s točkama umjesto dvotočaka
  (npr. „aabb.ccdd.eeff“, kako ga ispisuju zapisnici preklopnika i tiketi podrške)
  uopće se nije prepoznavala i ostajala je čitljiva.
- Prezime iza „Familie“ (npr. „Die Familie Gruber unterschreibt
  den Vertrag“) ostajalo je, ovisno o strukturi rečenice, neprepoznato i time čitljivo –
  i s plemićkim predikatom ispred („Familie von der Leyen“).

- Kod hrvatske adrese bez razdvojnog interpunkcijskog znaka između
  poštanskog broja+mjesta i ulice+kućnog broja (npr. „10000 Zagreb Ulica Ivana
  Lučića 5“) kućni broj ostajao je neočišćen.

- Kod litavskog kontakt podatka s oznakom „Kontaktinis
  asmuo“ (npr. „Kontaktinis asmuo: Vilkas Jonas“) prezime je
  ostajalo neprepoznato, kad je ujedno bila uobičajena imenica (Vilkas =
  „vuk“, Vanagas = „jastreb“).

- Zemlja rođenja ili prebivališta bez daljnje oznake u
  danskom polju obrasca (npr. „Fødeland: Tyskland“ ili „Bopæl:
  Tyskland“) nije se prepoznavala.

- Zemlja rođenja ili prebivališta bez daljnje oznake u
  rumunjskom polju obrasca (npr. „Țara: Germania“ ili „Țara de
  reședință: Franța“) nije se prepoznavala.

- Naziv tvrtke ispod litavske oznake polja „Darbdavys:“
  ili „Įmonės pavadinimas:“ (poslodavac/tvrtka) nije se prepoznavao.

- Naziv tvrtke ispod ruske oznake polja
  „Работодатель:“ ili „Наименование организации:“
  (poslodavac/tvrtka) nije se prepoznavao.

- Ispisani datum s nazivom mjeseca na rumunjskom (npr.
  „31 decembrie 2024“) nije se prepoznavao.

- Mađarsko djevojačko prezime iza kratice „szül.“ (npr. „Nagy
  Éva (szül. Kovács)“) nije se prepoznavalo i ostajalo je otvoreno čitljivo.

- Spremljena HTML profilna stranica (ili e-pošta s priloženom
  web stranicom) mogla je ostaviti građansko ime neočišćeno, kad je stajalo samo
  u Open Graph profilnim poljima `profile:first_name`/`profile:last_name`/
  `profile:username` – ona nose ime rastavljeno umjesto opisno
  kao `og:title`, i sada se također čiste.

- Poruka o neisporučivosti (bounce/NDR) često je nosila zaglavlja
  izvorno neisporučive poruke (pošiljatelj, primatelj, predmet) u
  vlastitom, trećem dijelu privitka – taj je u očišćenoj inačici
  ostajao potpuno netaknut. Taj dio se sada čisti kao i
  ostatak izvještaja o isporuci.

- Pojedinačno imenovani obrađivač zaštićenog područja u Wordu (Ograniči uređivanje → Iznimke, `w:permStart`) ostajao je u čistom tekstu, čak i kad je isto ime u tekstu odavno očišćeno. Sada se uklanja i ono.

## 0.10.42-alpha.20260827 – 27. kolovoza 2026.

### Novo

- **Imenovani profili prepoznavanja omogućuju dohvat različitih radnih
  slučajeva jednim potezom.** Pod *Postavke → Prepoznavanje → Što se
  uklanja* trenutačan odabir kategorija i vrsta može se spremiti i
  odmah ponovno primijeniti preko izbornog polja. Fiksni profil
  *Standardno* odgovara dosadašnjem stanju isporuke i ne može se
  izbrisati. Profil mijenja isključivo ono što se uklanja; jezik, vrsta
  ispisa, dubina prepoznavanja te vlastiti pojmovi i uzorci pretrage
  ostaju netaknuti.

- **Vrsta rezultata sada se bira izravno prije čišćenja.** Zajedničko
  izborno polje u glavnom prozoru za cijelu skupinu određuje postavlja
  li Maskuro čitljiva rezervirana mjesta, zacrnjuje ili bez zamjene
  uklanja. Dva odvojena polja za PDF i Office u prozoru postavki su
  otpala; time je ta važna odluka vidljiva i kod miješanih skupina se
  više ne može nehotice razići. Vođeni obilazak novi odabir objašnjava
  prije prvog čišćenja.

- **Teme i vodeni žigovi na zahtjev jasno označavaju gotove PDF-ove.**
  Dvanaest cjelovitih izgleda usklađuju zamjenske tekstove i površine
  zacrnjenja; novo su tu Pride te proljeće, ljeto, jesen i zima. *Tajni
  spis* odmah donosi dijagonalni `TOP SECRET`. Neovisno o tome moguće
  je odabrati slobodan tekst oznake ili vlastitu sliku, ikonu odnosno
  SVG s bojom i neprozirnošću. Uvezene grafike ugrađuju se bez svojih
  metapodataka i ostaju dostupne kad se izvorna datoteka premjesti. Pri
  doradi Maskuro zamjenjuje svoj dosadašnji vodeni žig, umjesto da ga
  slaže višestruko jedan preko drugoga. Tekstualni vodeni žigovi crtaju
  se kao posljednji PDF sloj sa svijetlim obrisom, kako bi ostali
  vidljivi i na tamnim slikama i gustom tekstu. Uređivač za doradu
  potpuno ignorira Maskurov vodeni žig i njegov tekst više ne nudi kao
  kandidata za zacrnjenje.

- **Vlastite teme ispisa mogu se spremiti i podijeliti.** Trenutačna
  mješavina zamjenskog teksta, zacrnjenja i vodenog žiga dobiva naziv,
  ostaje u postavkama i može se izvesti ili uvesti kao JSON bez
  osobnih podataka. Crno-bijeli pregled ispisa upozorava na slab
  kontrast; neobavezni konfeti uspjeha ostaje isključivo u sučelju.

- **Posljednja izvozna proba i objašnjavajuća provjerna naklada
  zaokružuju krug oblikovanja.** Prije konačnog spremanja Maskuro svako
  vrijednosno poznato PDF mjesto još jednom uspoređuje u tekstualnom
  sloju i iscrtanim slikovnim točkama; upozorenja navode isključivo
  stranicu i koordinate. U uređivaču *Zašto je ovo prekriveno?*
  pokazuje kategoriju, put prepoznavanja i sigurnosni rub, nikad
  uklonjeni čitljivi tekst i nikad u konačnom dokumentu.

- **Trake zacrnjenja sada smiju biti lijepe.** Pod *Postavke → Izgled*
  stoje zadane boje, slobodni birači boje, prijelazi, duga, pruge,
  točke, cvijeće, zvijezde, srca, šape, oblaci, munje, zrna kave, patke,
  sunca, listovi, pahulje, papirni, flomasterski, ljepljivo-trakasti i
  ponovljivi slučajni uzorci zajedno s izravnim pregledom. Zamjenski
  tekstovi po izboru dobivaju boju, prijelaz, dugu, tabletu ili
  naljepnicu. Boje kategorija razlikuju imena, adrese, kontakte i
  medicinske podatke. PDF preuzima cjelovito oblikovanje; Word,
  PowerPoint, OpenDocument i HTML koriste odabranu neprozirnu osnovnu
  boju. Zaštita se pritom ne mijenja: Maskuro najprije uklanja povjerljiv
  sadržaj i tek potom crta boju ili uzorak na prazno mjesto.

- **Maskuro je ponovno dostupan za Linux – kao AppImage, DEB, RPM i
  prijenosna arhiva.** DEB i RPM u sustav upisuju stavku programa,
  pridruživanja datotečnih vrsta, naredbu terminala i ikonu; AppImage
  radi bez instalacije. Ažuriranja kod postojeće DEB ili RPM
  instalacije ostaju u istom formatu paketa, a inače daju prednost
  AppImageu.

- **Vizualna provjera obični PDF tekst više ne predlaže po drugi put kao
  novi nalaz.** Završni OCR pogled i sigurna ponovna izgradnja
  vidljivih stranica ostaju potpuno aktivni; kao izvor novih nalaza
  zadano sada vrijede samo područja koja tekst stranice i provjera
  pojedinačne slike još nisu pročitali. Time retci proizvoda više ne
  postaju novo ime ili tvrtka samo zbog drugačijeg drugog OCR čitanja.
  Tko i dalje želi dvije neovisne ocjene cijelog vidljivog teksta,
  uključuje u postavkama *Ponovno provjeri cijelu vidljivu PDF stranicu
  na podatke*.

- **PDF-ovi se sada mogu pregledavati tekuće, po listu ili kao dvostruka
  stranica.** Tri kompaktne ikone prikaza stoje dolje odmah uz „Širina“
  i „Stranica“. Tekuće kotačić miša na rubu lista prebacuje na
  sljedeću stranicu; pojedinačna stranica drži kotačić miša na
  trenutačnom listu; dvostruka stranica prikazuje arak, čini kliknuti
  list uredivim i pomiče naprijed/natrag za cijeli arak. Minijature
  stranica i povećalo za usporedbu uz to se otvaraju u znatno užem
  lijevom osnovnom stupcu i ostavljaju više prostora radnoj stranici.

- **Sada vidite što je AI razina učinila.** Nakon svakog izvođenja pod
  „Detalji“ po datoteci stoji redak o tome – „AI razina: provjereno 12
  graničnih slučajeva, odbačeno 3“ – a i kad nije našla ništa za
  promijeniti, to također piše. Dosad je najskuplja razina potpuno
  šutjela: izvana se nije moglo prepoznati je li uopće upitana.

  Tko treba točnije, uključuje pod „Postavke → AI“ *Zapisuj svako AI
  pitanje u zapisnik*. Tada datoteka zapisnika po pitanju bilježi
  veličinu, trajanje i broj nalaza, uz to i vrijeme čekanja zbog
  granice količine protustrane. Gumb „Prikaži datoteku zapisnika“ pored
  otvara mapu – ona se nalazi u direktoriju podataka aplikacije, koji
  je na Windowsu skriven i koji nitko sam od sebe ne pronalazi. U
  datoteci stoje isključivo veličine, nikad tekst iz vaših dokumenata.

- **Maskuro prepoznaje kad vaša AI usluga ograničava broj upita.**
  Hostirane usluge često dopuštaju samo nekoliko upita po minuti –
  četiri nije rijetkost. Suvišni se ne odbijaju, nego moraju čekati, pa
  od dvije sekunde po odgovoru nastaje četrdeset. To je dosad izgledalo
  kao da je model spor. Sada Maskuro čita granicu iz odgovora usluge,
  više ne šalje odjednom više pitanja nego što se prima, navodi granicu
  pod „Provjeri vezu“ i uračunava je u procjenu trajanja.

- **Pregled stranice sada koristi vaš Word, Excel i PowerPoint – i time
  je oko šest puta brži.** Dosad je trebao LibreOffice, koji stoji na
  najmanje uredskih računala; tko ga nije imao, vidio je gumb koji je
  tražio instalaciju treće strane. Sada vrijedi: je li Microsoft Office
  instaliran, koristi se sam od sebe – bez postavljanja, bez
  preuzimanja, bez ikakve kvačice. LibreOffice ostaje drugi put i kod
  OpenDocument datoteka čak prvi; ne uspije li jedan, pokušava se
  drugi.

  Razlika se najviše primjećuje pri radu: nakon svake zamjene stranica
  se ponovno slaže, a to preko Officea košta oko pola sekunde umjesto
  tri. Prvi prikaz dokumenta i dalje traje nekoliko sekundi, nakon toga
  prati vaše zahvate bez čekanja.

  Vaš vlastiti otvoren Word pritom se ne dira: Maskuro pokreće vlastitu,
  nevidljivu sjednicu, datoteku otvara samo za čitanje, isključuje
  makronaredbe i sve zatvara čim se prozor uređivača zatvori. Datoteke
  zaštićene lozinkom se odbijaju, umjesto da ostanu visjeti u
  nevidljivom dijalogu.

- **Prvo postavljanje sada pita i za lica, kodove i potpise – i sve što
  nedostaje učitava u jednom potezu.** Uz proširenu razinu
  prepoznavanja na prvoj stranici stoje tri slikovna prekidača:
  učiniti područja lica neprepoznatljivim, učiniti crtične i QR kodove
  neprepoznatljivim, zacrniti rukom pisane potpise na PDF stranicama.
  PDF granica vidljivo stoji uz kvačicu; Office datoteke se automatski
  ne pretražuju na potpise. Ispod kvačica stoji koliko megabajta klik
  na „Dalje“ košta. Nakon toga se učitava u **jednom** prozoru s
  **jednom** trakom napretka za sve zajedno, umjesto u više dijaloga
  jedan za drugim; prekid završava cijeli postupak i ne ostavlja ništa
  napola gotovo. Tko ništa od toga ne želi, ukloni kvačice – tada se
  ništa ni ne učitava.

- **Pregled se sada može prorijediti po potrebi provjere i sažeti po
  vrsti.** Iznad popisa stoji klizač *Sakrij dobro dokazane*: što je
  dalje udesno, to više sakriva od zelenog prema crvenom; sasvim
  udesno ostaje samo ono što je program sam nagađao. Klik na naslov
  vrste sažima je. Oboje je pomoć pri čitanju, ne odabir – što je
  sakriveno ili sažeto ostaje označeno i zamjenjuje se; koliko je to
  trenutačno vrijednosti, stoji ispod klizača. Kod kratkih popisa
  klizač se ne pojavljuje. Prebacivanje na dva stupca sada uz to drži i
  prekidače *nikad više*.

- **Popis slika se sada prije svakog izvođenja može sam otvoriti.** Tko
  želi odlučivati o svakoj slici pojedinačno, postavlja pod „Slike“ novu
  kvačicu *Odredi pojedinačno prije svakog izvođenja*. Popis s pregledom
  tada se pojavljuje pri čišćenju sam od sebe, umjesto da svaki put
  sami kliknete „Odredi pojedinačno …“; prekinete li ga, ne čisti se ni
  ništa drugo. Ne sadrži li nijedna odabrana datoteka sliku, ništa se
  ne pojavljuje. Zadano je kvačica isključena.
- **Maskuro na PDF stranicama pronalazi rukom pisane potpise i uklanja
  ih iz slikovnih točaka.** Dosad je potpis ostajao stajati ispod
  očišćenog dokumenta – prepoznavanje teksta čita tiskana slova, a ono
  što ne čita, ne zamjenjuje. Pretraga je vlastiti prekidač i treba
  model prepoznavanja koji se jednokratno naknadno učitava.

  Izmjereno pronalazi oko 84 od 100 potpisa i pokriva ih otprilike
  četiri petine. To je pomoć, ne jamstvo: nakon svakog izvođenja
  izvještaj navodi koliko je pronađeno – i onda kad ih nije bilo,
  jer to može značiti da ih nema ili da je jedan previđen. Na 72
  stvarne poslovne stranice bez potpisa nijedan nije izmišljen.

  **Nacrtan** potpis se pronalazi, ali se ne uklanja: sastoji se od
  linija, ne od slikovnih točaka, a traka preko njega bila bi samo
  prekrivanje ispod kojeg linije ostaju. Takva se mjesta broje i
  navode, kako bi se mogla sama zacrniti u prozoru uređivača.

  Word, Excel, PowerPoint i OpenDocument datoteke se automatski ne
  pretražuju na potpise. Sučelje, prvo postavljanje, preuzimanje
  modela, naredbeni redak i priručnik sada izričito navode tu granicu.

- **Obilazak sada vodi i kroz pregled – prozor u kojem odlučujete.** Kod
  dokumenta za vježbu otvara se sam od sebe, čak i ako ste pregled
  inače isključili (vaša postavka ostaje kakva jest). Objašnjava se što
  boje znače, zašto u svakom retku stoji samo jedno pitanje – postoji
  li ovdje uopće osoba? – i čemu služi „nikad više“. Kod boja
  reflektor je na dobro dokazanom retku, obično IBAN-u – zelenom
  primjeru koji rečenica navodi; zatim na najslabije dokazanom, i ondje
  smijete usred objašnjenja sami kliknuti: kvačica maknuta, vrijednost
  ostaje u dokumentu. Kod dugog popisa prozor se za vodstvo otvara
  veći, kako objašnjenje ne bi ležalo na retcima. Otvori li se prozor
  drugi put, obilazak kaže i zašto – gotova stranica ponovno se čita
  kao slika, pri čemu nastaju ulomci koji izgledaju kao ime.

- **Uređivač se prvi put otvara veći.** Izvornik, rezultat, alatna
  traka i popis nalaza stoje jedan uz drugoga i u dosadašnjoj osnovnoj
  veličini imali su premalo mjesta. Tko prozor smanji, dobiva njegovu
  veličinu sljedeći put natrag – nikome se ništa ne nameće.

- **Dvoklik na rezervirano mjesto ga vraća** – u Wordu, Excelu,
  PowerPointu, OpenDocumentu, tekstu, e-pošti i HTML-u. A tko povuče
  preko više rezerviranih mjesta i odabere „Vrati odabir“, vraća sve
  unutar njih odjednom. Uglatu zagradu više ne treba precizno pogoditi.
  Rezervirana mjesta koja kod anonimiziranja stoje za više različitih
  vrijednosti iz toga su izuzeta – broje se i navode, ne nagađaju.

- **Priručnik ima poglavlje „Pregled prije zamjene“.** Prozor je unaprijed
  postavljen kao uključen i jedini je u kojem odlučujete – u
  priručniku je dosad stajao samo u pokrajnjoj rečenici. Sada ondje
  stoji što kvačica znači (vrijedi za **svako** mjesto nalaza, ne samo
  navedeno), zašto je po retku potrebno odgovoriti na samo jedno
  pitanje, što „nikad više“ trajno postiže i zašto se prozor kod PDF-a
  može otvoriti drugi put. Na svih osamnaest jezika, a prekidač je sada
  naveden i u popisu postavki.

### Promijenjeno

- **Pretinac „Zamijenjene vrijednosti“ ima klizač preko boja, a način
  učenja ondje više ne stoji.** Kod više od osam vrijednosti iznad
  popisa stoji isti klizač kao u prozoru pregleda: *Sakrij dobro
  dokazane* prorjeđuje prikaz na ono što uistinu treba pregledati. Na
  dokumentu se time ništa ne mijenja, a koliko je redaka od koliko
  vidljivo, stoji ispod – polje pretrage i klizač zbrajaju se zajedno.
  Kvačica *Način učenja* nestala je iz pretinca; i dalje stoji u
  izborniku *Alati* i u alatnoj traci.

- **Pretinac „Zamijenjene vrijednosti“ sada prikazuje iste boje kao
  dokument.** Svaki redak u njemu obojen je jednako kao mjesto u
  dokumentu i kao vrijednost u pregledu: crveno znači „samo nagađano,
  ovdje se prvo isplati drugi pogled“, zeleno „prepoznato imenovanim
  uzorkom“. Unutar svake vrste najnesigurnije stoji gore – popis dakle
  obrađujete odozgo prema dolje i najvažnije ste vidjeli prvo. Dosad je
  sve stajalo jednako svijetlo i abecedno posloženo.

- **Način učenja je tvornički isključen.** Nakon ispravke u prozoru
  uređivača program je dosad sam od sebe pitao treba li od toga
  nastati vlastito pravilo. To pitanje dolazi usred rada; tko ga nije
  naručio, doživljava ga kao prekid. Tko želi pravila, uključuje gumb
  *Način učenja* u alatnoj traci – izbor tada trajno vrijedi, u oba
  smjera.

### Riješeno

- **Izvezene datoteke pravila sada su izričito označene kao vrijedne
  zaštite.** Vlastiti pojmovi i iznimke mogu u njima stajati u
  čitljivom obliku; uz to datoteka može sadržavati sol za hashiranje
  kojom se pretpostavljene vrijednosti mogu potvrditi. Uspješan izvoz
  zato prikazuje upozorenje i poziva na zaštitu datoteke te njezino
  prosljeđivanje samo svjesno ovlaštenim primateljima.

- **Posljednja sigurnosna provjera više ne zadržava očišćene uredske
  datoteke zbog njihovih vlastitih rezerviranih mjesta.** Kratica vrste
  poput „SVNR“ stoji i u `[SVNR1]`; dosad se to smatralo navodnim
  ostatkom čitljivog teksta i gotova je datoteka bila odbačena.
  Istodobno se telefonski brojevi i IBAN-ovi sada dovlače i ondje gdje
  Office isti podatak bez vidljivih razmaka odlaže u poveznici ili
  ugrađenoj datoteci.

- **Word, Excel, PowerPoint i OpenDocument više ne ostavljaju kasno
  otkrivenu kopiju polja.** Prepozna li se vrijednost prvi put u
  nusspremištu ili ugrađenoj uredskoj datoteci, uski naknadni prolaz
  čisti i prije pročitane vidljive i skrivene kopije. Već stvorena
  rezervirana mjesta poveznica pritom se ne zamjenjuju ponovno.

- **Kod pojedinačnog vraćanja Word padajućeg popisa više se ne vraća
  susjedni odabir bez pitanja.** Potpun izvorni odlomak preuzima se tek
  kad ni njegovi atributi više ne sadrže otvorena rezervirana mjesta.

- **Slabo čitljivi skenovi gube manje povezanih podataka.** Alternativno
  OCR čitanje s oslovljavanjem i dvodijelnim imenom ostaje sačuvano;
  ulomak ulice, kućni broj i poštanski broj s mjestom zajedno štite
  cijeli redak adrese, čak i kad se raspadne na susjedne OCR blokove.
  Retci računa i artikala te retci događaja pored time nisu zahvaćeni.
  Valjan datum raspadnut iza „rođen“ na više OCR riječi i
  interpunkcijskih znakova također se potpuno čini neprepoznatljivim.

- **Konfeti uspjeha sada je vidljiv pri automatskom otvaranju
  uređivača.** Komadići sada prskaju izravno iz gumba *Očisti* umjesto
  da padaju s gornjeg ruba prozora. Uređivač čeka samo prvi, 850
  milisekundi kratki mlaz i zatim se automatski otvara; bez uključenog
  konfetija i dalje nema odgode.

- **Brojač stranica i traka zuma više ne skaču pri prelasku preko ikona
  prikaza.** Qt je preraspoređivao slobodan prostor statusnog retka čim
  bi se ondje pojavila napomena nekog simbola. Obje upravljačke skupine
  sada pri lebdenju zadržavaju svoju prirodnu širinu i fiksan položaj.

- **Mjerenje brzine povezanog AI poslužitelja uvijek je propadalo** –
  na svakom poslužitelju, otkad postoji vlastita AI. Pitalo je uz usku
  granicu odgovora i potom pokušavalo čitati time odsječen odgovor; to
  je moralo propasti, a spremalo se „nije izmjereno“. Posljedice su
  bile vidljive posvuda: procjena trajanja vaš je poslužitelj računala
  tempom priloženog modela na uredskom računalu, a u postavkama je
  trajno stajalo da brzina još nije izmjerena. Sada se mjeri prema
  količini koju je poslužitelj stvorio, ne prema sadržaju njegovog
  odgovora.

- **„Maksimalna razina prepoznavanja (AI) – sporo“ stajalo je i kad
  nije bilo točno.** Oznaka i napomena opisivale su priloženi model na
  uredskom računalu – „jezični model na ovom računalu“, „kod velikih
  dokumenata do sat vremena“. Tko je povezao vlastiti AI poslužitelj,
  ondje je čitao dvije netočnosti: ne računa se na njegovom računalu, a
  odgovara se u sekundama umjesto satima. Oboje sada dolazi iz
  mjerenja. Ne postoji li mjerenje, aplikacija više ništa ne tvrdi, nego
  kaže da još nije izmjereno.

- **Vraćanje sada djeluje i na povučen odabir.** Tko je povukao preko
  više rezerviranih mjesta i htio pritisnuti *Vrati odabir*, nalazio je
  gumb siv: uključivao se samo kad je oznaka bila **točno** jedno
  rezervirano mjesto – povučena preko odlomka to nikad nije. Put iza
  toga je postojao, samo do njega nitko nije dolazio. Sada je dovoljno
  označiti područje; sva rezervirana mjesta u njemu vraćaju se
  odjednom.

- **Vraćanje se rušilo kad je povećalo za usporedbu bilo otvoreno.**
  Povećalo pamti mjesto ispod pokazivača miša, kako bi u izvorniku
  pratilo. Pri ponovnom učitavanju nakon vraćanja vraćalo je to mjesto
  u obliku s kojim prikaz teksta nije znao što bi – a jer takva pogreška
  usred sučelja zatvara program, od vraćanja je nastalo rušenje.
  Povećalo je u osnovnom stanju otvoreno, dakle pogodilo je uobičajen
  put.

- **Nakon vraćanja prikaz više ne skače na početak dokumenta.** U duljem
  dopisu nakon svakog zahvata nestajalo je mjesto na kojem se upravo
  radilo. Sada gore ostaje odlomak koji je i prije bio gore.

- **Bez LibreOfficea pregled stranice sada kaže odakle dolazi, umjesto
  da samo nedostaje.** Oba gumba *Pregled stranice* i *Zacrni kao PDF*
  bila su zaključana i u napomeni pri pokazivanju navodila samo da
  LibreOffice nije pronađen; puta do njega nigdje u aplikaciji nije
  bilo. Klik sada otvara napomenu s putem do besplatnog, otvorenog
  LibreOfficea. Priručnik i ČPP na tom mjestu bili su pogrešni –
  najavljivali su gradivni element za naknadno učitavanje koji
  aplikacija ne nudi.

- **Prije isporuke gotova datoteka posljednji put se u potpunosti
  pretražuje – sada i kod Worda, Excela, PowerPointa, LibreOfficea,
  e-pošte, HTML-a i teksta.** Dosad je taj posljednji pogled imao samo
  PDF. Sve provjere prije toga gledaju na mjesto koje je netko prije
  imenovao; spremište na koje nitko nije pomislio zato nitko ne
  provjerava. Na kraju Maskuro sada tupo pretražuje sve što je
  zamijenjeno – u svakom dijelu paketa. Ostane li nešto stajati, **ne**
  nastaje rezultat, a poruka navodi vrijednost. Datoteka koja se
  smatra očišćenom gora je od nikakve.

- **Imena u `<script>` i `<style>` sada se prijavljuju.** Oba ostaju i
  dalje netaknuta – ondje stoji programski kod, a zamjena usred
  identifikatora čini od web stranice pokvarenu web stranicu. No dosad
  to nije bilo rečeno, i to je bila pogreška: pravilo stila `content:
  “Anna Musterfrau“` primatelju stoji **vidljivo** na zaslonu, a u
  rezultatu je ostajalo ondje dok je program javljao da je stranica
  očišćena.

- **U postavkama se dodatni modeli ponovno mogu učitati i ukloniti.**
  Gumb uz „Proširena razina prepoznavanja“ i „Maksimalna razina
  prepoznavanja (AI)“ pri pritisku je završavao u prozoru izvještaja o
  pogrešci umjesto da dohvati model. Drugi put – kvačica u
  prepoznavanju, koja sama pita za model – time nikad nije bio
  zahvaćen.

- **Imena skrivena u nazivima listova i raspona tablice sada se
  prijavljuju.** Naziv lista stoji na kartici dolje, naziv imenovanog
  raspona u polju naziva i u svakoj formuli koja ga koristi. Oba se i
  dalje ne zamjenjuju – formule na njih upućuju, a radna knjiga s
  pogreškama u referencama nikom ne pomaže – ali to sada ondje piše.
  Dosad je poruka dolazila samo za naziv lista Excel radne knjige:
  imenovan raspon „Bezuege_Brunnthaler“ tiho je izlazio van, a kod
  LibreOffice tablice program je posve šutio. List „Bilješke Ortner“
  time je vrijedio kao očišćen, a prvi pogled primatelja padao je na
  ime.

  Prijavljuje se pritom samo ono što uistinu vodi na osobu: riječ koja
  je u istoj radnoj knjizi ionako zamijenjena, ili nalaz koji od više
  riječi odabire jednu. Samostojeća riječ poput „Zustaendig“ ili
  „Bezug_Umsatz“ više ne pokreće upozorenje – prije bi to učinila, a
  upozorenje koje dolazi kod svake druge radne knjige nakon trećeg
  puta više nitko ne čita.

- **„Vrati izvornik“ sada uistinu vraća sve.** U nekim dokumentima
  nakon toga nedostajali su pojedinačni znakovi – iz „Seestraße 14“
  nastajalo je „Seestraße 4“, iz „An:“ „An“, iz „nordlicht-planung“
  „nordlicht planung“ – a pojedini retci uopće se nisu vraćali. Baš na
  tim mjestima nakon toga se mišem ništa više nije moglo označiti ni
  zacrniti: tekst je doduše stajao na papiru, ali ga program više nije
  poznavao. Zahvaćeni su bili uski znakovi – jedinica, dvotočka, crtica
  – u dokumentima koji svaki znak postavljaju pojedinačno; dokument za
  vježbu jedan je od njih.

- **A isti dokumenti se pri čišćenju više ne pretvaraju u sliku.** Jer
  je takav znak ostajao, naknadna provjera javljala je ostatak i
  stranica se opreza radi rasterizirala. Tekst na njoj potom je bio
  samo slika: više nije bio pretraživ, nije se mogao označiti, i bio je
  veći u datoteci. Dokument za vježbu sada na obje strane ostaje pravi
  tekst.

- **Obojene oznake više ne ostaju iznad vraćenog teksta.** Tko je
  poništio zamjenu, i dalje je vidio obojen pravokutnik iznad
  obnovljene riječi – tvrdio je „ovdje je nešto uklonjeno“, iako je
  ondje ponovno stajao izvornik.

- **Traka više ne odaje koliko je duga bila riječ ispod nje.** Kod
  zacrnjivanja traka u kratkim recima sada pokriva **cijeli** redak –
  blok adrese, podatke zaglavlja, uzak stupac tablice. Ne stane li
  cijeli redak (uobičajen redak tablice s tri stupca), ostaje kod
  polja; u retku tekućeg teksta ostaje po riječima, jer bi ime usred
  rečenice inače pocrnilo cijelu rečenicu. A trake koje stoje jedna
  ispod druge postaju **jednako duge**: u bloku adrese na svakom retku
  stoji vrijednost, a tri različito duge trake i dalje su odavale
  koliko su dugi bili retci. Rastu pritom samo dok ima slobodnog
  papira – pred susjednim stupcem traka prestaje.

- **„Cijeli redak“ sada uistinu zacrnjuje cijeli redak.** Dosad je
  traka završavala na sljedećem većem razmaku – dakle na kraju polja.
  U tekućem tekstu to nije bilo uočljivo, ondje je polje redak; u
  podacima zaglavlja i tablicama jest: iz „Ime: Anna Musterfrau
  Odjel: Prodaja“ nastajala je traka koja je završavala točno na
  posljednjem slovu imena – čime je njegova duljina ponovno stajala na
  listu. Traka sada ide od prve do posljednje riječi retka i uzima sa
  sobom susjedne stupce. Tko želi pogoditi samo vrijednost, bira
  „Riječi“; automatika i dalje zacrnjuje po poljima.

- **Prije isporuke gotova datoteka posljednji put se pretražuje.** Sve
  dosadašnje provjere gledaju na mjesto koje je netko prije imenovao –
  tekst stranice, pravokutnik nalaza, slikovna površina. No PDF ima
  više spremišta nego što nabrajanje može obuhvatiti: napomene,
  vrijednosti obrazaca, oznake, podatke o dokumentu, privitke,
  JavaScript. Na kraju Maskuro zato tupo pretražuje zapisanu datoteku
  na sve što je zamijenio – posvuda osim u tekstu stranice, gdje isti
  tekst smije stajati i dopušteno. Ostane li ondje nešto, **ne**
  nastaje rezultat, a poruka navodi vrijednost. Dokument koji se
  smatra očišćenim gori je od nikakvog.

- **Ono što se nije moglo provjeriti više ne vrijedi kao provjereno.**
  Na tri načina neuspjeh naknadne provjere dosad je izgledao kao čist
  rezultat. Stranica čiji se tekstualni sloj nije mogao pročitati
  vrijedila je kao osobito čista – ondje se ionako nije imalo što
  pronaći; sada se rasterizira. Nije li se stranica s preostalim nalazom
  mogla zamjenski rasterizirati, tiho je bila isporučena; sada se
  čišćenje radije prekida. A protuprovjera u prozoru uređivača nakon
  vlastite pogreške javljala je „ništa preostalo“ – u prozoru se to nije
  moglo razlikovati od toga da je sve uklonjeno; sada se pojavljuje
  upozorenje zajedno s gumbom „Rasteriziraj stranicu“.

- **„Vrati na zadano“ nije vraćalo većinu postavki.** Devet od
  dvadeset dvije kvačice nakon zahvata stajalo je nepromijenjeno –
  među njima pregled, „Nakon toga otvori očišćene datoteke“, prozor
  uređivača, trenutačno odlaganje i obje kvačice ažuriranja.
  Spremljena datoteka bila je doduše ispražnjena, ali prozor je
  zadržavao stare vrijednosti i pri sljedećem kliku ih ponovno
  upisivao. Sada se vraća svaka kvačica, a napomena „promijenjeno“
  nestaje zajedno s njom.
- **„Automatski odloži izvješće o provjeri za svako čišćenje“
  prikazivalo se, ali je bilo isključeno.** Nakon vraćanja na zadano
  kvačica je ostajala postavljena dok je vrijednost bila obrisana –
  izvještaj više nije nastajao, bez ikakve naznake. Isto je vrijedilo
  za zapisnik provjere i vlastitu snimku zaslona; njihova tipkovna
  prečica pri vraćanju sada se odmah ispravno prijavljuje ili odjavljuje.

- **Trake jednog retka sada izgledaju jednako.** Dosad je svako mjesto
  nalaza donosilo svoju traku, a njezina visina dolazila je iz pisma
  pogođene riječi. U retku s oznakom i vrijednošću različitih veličina
  time su jedna debela i jedna tanka crta s pomaknutim rubovima stajale
  jedna uz drugu, a gdje su dva nalaza dijelila samo razmak, iznad je
  ostajao svijetli razmak. Trake istog retka sada imaju isti gornji i
  donji rub, a ono što razdvaja samo razmak postaje jedna traka. Ono
  što bi trebalo ostati stajati između dva nalaza – zarez iza imena,
  oznaka, iznos – i dalje ih razdvaja. Vrijedi za slagane stranice kao
  i za skenove.

- **Kartice pod „O ovom programu“ ponovno počinju od vrha.** Zaštita
  podataka, licencni uvjeti i licencne napomene otvarale su se usred
  teksta – tko ih je čitao, morao je najprije skrolati sasvim gore da
  vidi prvi redak.

- **Olovka više ne otvara drugi prozor uređivača, nego vraća postojeći
  naprijed.** Dosad je pri svakom kliku nastajao novi. Prozor nema
  vlastitu stavku u traci zadataka – tko ga minimizira, više do njega
  nije dolazio i kliknuo je ponovno; pri vraćanju glavnog prozora tada
  su svi nakupljeni prozori dolazili naprijed odjednom. Sada daljnji
  dokumenti završavaju u traci kartica otvorenog prozora, a dokument
  koji ondje već stoji ne dobiva drugu karticu.

- **„Proširena razina prepoznavanja“ više ne nosi napomenu
  „promijenjeno“ dok njezin model nedostaje.** Isporučuje se uključena,
  ali bez naknadno učitivog modela to ni ne može biti – u postavkama je
  taj redak zato na svakom svježe postavljenom računalu stajao kao
  promijenjen, iako ga nitko nije dirao. Zašto je kvačica isključena,
  sada govori sama njezina oznaka: „Model još nije učitan“.

- **Uvodna traka u Office i tekstualnim datotekama objašnjavala je PDF
  platno.** Ondje je stajalo „klik na riječ je zacrnjuje“ – no u Word
  datoteci klik ništa ne zacrnjuje, ondje se označava pa pritisne gumb.
  Sada kaže ono što vrijedi u odgovarajućem prikazu.
- **Alatna traka bila je u prikazu teksta zatrpana oznakama.** „Zamijeni
  odabir“, „Zacrni odabir“, „Vrati odabir“, „Pregled stranice“ i
  „Zacrni kao PDF“ sada stoje kao simbol – kao njihova braća u PDF-u.
  Njihovi nazivi ostaju u kratkoj pomoći i izborniku.
- **Ctrl+kotačić miša u povećalu za usporedbu nije pomicao njegov
  klizač zuma.** Pismo je postajalo veće, klizač i postotak pored i
  dalje su tvrdili staro stanje.
- **Instalacijski program ažuriranja nije dolazio u prvi plan** –
  trebalo ga je prvo kliknuti u traci zadataka (samo Windows).
- **Godina na početku retka smatrala se austrijskim poštanskim
  brojem.** U životopisu je iz „2020 Strategije prodaje“ nastajalo
  rezervirano mjesto – cijeli redak nestajao je. Četveroznamenkast broj
  između 1900 i 2099 sada treba drugi znak adrese: ulicu iznad, riječ
  polja ispred, oznaku zemlje ili poznat naziv mjesta. Blokovi adrese
  to imaju; stupci godina ne.
- **Par mjesec-godina smatrao se telefonskim brojem.** Iz „Od 08.2010
  123-Verkauft GmbH“ nastajao je „telefonski broj“ – mjesec, godina i
  prve znamenke naziva tvrtke iza toga.
- **Izvještaj je govorio „provjereno prepoznavanjem teksta“ i
  prešutio što se time ne čita.** Ostanu li slike sačuvane, sada uz to
  stoji da se rukom pisano u njima ne pronalazi – potpis ili rukom
  upisano ime ostaje netaknuto. Dosad je ta rečenica stajala samo kod
  skeniranih stranica; obični PDF s ugrađenim potpisom nije o tome
  dobivao ni riječi.
- **Rezervirano mjesto na zacrnjenoj slikovnoj podlozi stajalo je na
  lijevom rubu svoje trake.** Pronađe li se vrijednost na slici –
  primjerice otipkano ime uz skenirani potpis – slikovno se područje
  mora zacrniti u punoj širini. Kraće rezervirano mjesto ostavljalo je
  pored golo crno, što je izgledalo kao dva zahvata. Sada stoji
  sredinom trake.

## 0.10.41-alpha.20260826 – 26. kolovoza 2026.

### Novo

- **Nakon probnog razdoblja prozor jednom po pokretanju podsjeća na
  licencu.** Pojavljuje se pet minuta nakon pokretanja – ne odmah, kako
  nikome ne bi stajao na putu prije prvog zahvata – i čeka dok traje
  čišćenje. Odande vodi put do kupnje i put do unosa već kupljenog
  ključa; „Kasnije“ ga zatvara čim istekne pet sekundi na gumbu. Ništa
  se ne zaključava: besplatna razina i dalje radi kao dosad.

- **Vrijeme čekanja prije izvođenja u besplatnoj razini sada traje deset
  umjesto trideset sekundi.** Treba podsjetiti na licencu, ne zaustaviti
  rad.

- **Sve tri napomene o licenci sada izgledaju jednako.** Vrijeme čekanja,
  podsjetnik u posljednjim probnim danima i napomena nakon probnog
  razdoblja nose istu traku, isti raspored i iste gumbe; preostalo
  vrijeme stoji na gumbu umjesto kao velik broj pored.

- **Popis nalaza u pregledu ponovno stoji jedan ispod drugoga.** Od devet
  vrijednosti bio je dvostupčan; pri prolasku oko tada skače između dva
  toka, a ovdje se odlučuje redak po redak. Tko voli dva toka, uključuje
  ih ponovno dolje lijevo u prozoru – izbor se pamti, a pri prebacivanju
  već odabrane isključene vrijednosti ostaju isključene.

- **AI razina otvorena je svakome tko poveže vlastiti AI poslužitelj.**
  „Postavke → AI“ nosi sve za to: povezivanje, što AI smije raditi, što
  dobiva na obradu – a iznad toga prekidač za razinu zajedno s
  protuprovjerom, čim je poslužitelj unesen. Jezični model koji računa
  na vlastitom radnom mjestu ostaje zadržan: za deset stranica treba
  nekoliko minuta i time nije za svakodnevnu upotrebu.

- **Vlastita AI se može povezati.** Umjesto priloženog jezičnog modela
  može odgovarati veći model na drugom računalu – na poslužitelju u kući
  ili radnoj stanici sa snažnom grafičkom karticom. Traži se usluga sa
  sučeljem kompatibilnim s OpenAI (Ollama, LM Studio, llama.cpp-server,
  vLLM, LocalAI); postavlja se pod „Postavke → Vlastita AI“ zajedno s
  provjerom veze koja model stvarno upita, mjeri brzinu i utvrđuje mogući
  oblik odgovora. Više tekstualnih odlomaka pritom se obrađuje istodobno
  umjesto jedan za drugim.

- **Što AI smije raditi i što dobiva na obradu sada je podesivo.** Tri
  prekidača odlučuju o provjeri graničnih slučajeva, samostalnom
  pretraživanju i pretraživanju u tekućem tekstu; uputa modelu stoji
  doslovno, može se dopuniti vlastitim pojmovima i gumbom vratiti na
  zadano.

- **Napušta li tekst pritom vlastitu mrežu, upozorava se prije svakog
  izvođenja.** Maskuro prema adresi prepoznaje nalazi li se AI
  poslužitelj u kući, i navodi poznatog davatelja imenom. Upozorenje se
  može isključiti, ali samo uz izričitu potvrdu da ste ovlašteni za taj
  prijenos, i samo za točno tu adresu. Na sam postupak to ne utječe:
  prijenos i dalje stoji u zapisniku i u izvještaju provjere svake
  datoteke. Na naredbenom retku se ne pita, nego se zaustavlja – ondje
  je potrebno `--ki-auswaerts-erlauben`.

- **Pregled prije zamjene kod novih postavki zadano je uključen i sada
  vrijedi i za izričito očišćene sadržaje međuspremnika te tekst i
  slike umetnute u program.** Kod skupina dokumenata i dalje se pojavljuje
  točno jedan pregled po dokumentu sa svim stranicama; tiho trenutačno
  čišćenje kratkih kopija namjerno ne otvara prozor.

- **Nalazi se u pregledu mogu uključiti i isključiti preko cijelog
  obojenog retka.** Kvačica je sada velika i kontrastna; uz to polje
  stanja pokazuje „Zamijeni“ odnosno precrtano „Zamijeni“, tako da se
  odabrane i isključene vrijednosti odmah razlikuju i na tamnim bojama
  pouzdanosti.

- **I PDF-ovi s vidljivom sigurnosnom protuprovjerom sada otvaraju
  pregled samo jednom po dokumentu.** Isključeni pojmovi ostaju
  isključeni za kasniju provjeru stranice; njezina provjera nastavlja
  raditi bez prekidanja istog izvođenja drugim dijalogom.

- **Zamjenske riječi u uređivaču za doradu izgledaju jednako i na
  rasteriziranim stranicama.** Nalazi li se crveno rezervirano mjesto u
  slikovnim točkama umjesto u PDF tekstualnom sloju, sada ipak dobiva
  istu, prema pouzdanosti obojenu pozadinu kao i obično PDF tekstualno
  rezervirano mjesto.

- **Već pregled prije zamjene pokazuje potrebu provjere pronađenih
  pojmova.** Svaki redak nosi istu crveno-narančasto-zelenu boju kao
  kasnije zamjena u uređivaču. Unutar kategorije niska pouzdanost i
  crveni kandidati za lažnu uzbunu stoje gore, jaki zeleni dokazi dolje;
  izjednačenja ostaju abecedna. Dolazi li ista vrijednost iz više
  nalaza, opreza radi broji se njihova najupitnija ocjena. Neocijenjeni
  posebni slučajevi stoje neutralno žuto između crvene i narančaste.

- **Rezultat se sada može izravno iz uređivača za doradu kopirati kao
  datoteka.** „Kopiraj rezultat“ stavlja trenutačnu očišćenu inačicu u
  međuspremnik, bez zatvaranja uređivača i ponovnog traženja datoteke u
  glavnom popisu. Kod još nespremljene ručne obrade prije toga
  automatski prolazi potpuni sigurni put spremanja; „Kopiraj sliku“
  ostaje kao odvojena funkcija za čiste slikovne točke.

- **Zamijenjene riječi u uređivaču na prvi pogled pokazuju što bi
  trebalo prvo provjeriti.** Čisto nagađanje jezičnog modela crveno je,
  čak i kad spaCy za to paušalno javlja 85 posto. Daljnje neoslonjene
  ocjene modela ostaju najviše narančaste; jaki imenovani dokazi mogu
  postati zeleni. Ručna obrada i starija pridruživanja bez procjenjive
  ocjene ostaju neutralno žuta. I automatske trake zacrnjenja nose te
  boje u pregledu uređivača – sada i kad je traka dio rasterizirane PDF
  stranice. Za to pridruživanje mora odgovarati, a raniji okvir riječi
  mora dokazivo biti neprozirno crn; obična podebljana slova se ne
  boje. U spremljenom PDF-u sve trake ostaju nepromijenjeno neprozirno
  crne.

- **Ono što se u pregledu isključi, može se trajno zapamtiti.** Gdje
  maknete kvačicu, kažete: ovdje se prepoznavanje prevarilo. Dosad je to
  vrijedilo samo za taj jedan dokument. Sada se uz redak pojavljuje
  prekidač „nikad više“; pritisnut, vrijednost trajno ulazi u popis
  „Nikad ne uklanjaj“ i ubuduće u svakom dokumentu vrijedi kao
  bezopasna. Ispod popisa stoji što postaje trajno, prije nego što
  pritisnete „Zamijeni“. Suprotan smjer namjerno ne postoji: što je
  jednom pronađeno, prepoznavanje pronalazi ponovno.

- **Gumb vraća sve postavke na stanje isporuke.** Stoji dolje lijevo u
  prozoru postavki i unaprijed pita. Vaše datoteke, vaša licenca, vaša
  vlastita pravila prepoznavanja i automatsko pokretanje ostaju
  netaknuti; ono što propisuje vaša uprava i dalje vrijedi. Svaka
  postavka koja odstupa od stanja isporuke uz to nosi napomenu
  „promijenjeno“ – tako se na prvi pogled vidi što je izmijenjeno.

### Promijenjeno

- **Rezultat se više ne odlaže sam od sebe – tek pri spremanju.**
  Izvođenje iz prozora svoju očišćenu inačicu najprije zapisuje na
  privremeno mjesto; datoteka „…_ocisceno“ uz izvornik nastaje tek kad
  pritisnete „Spremi“. Do tada se rezultat može pogledati, doraditi i
  kopirati. Svaki gotov redak za to ima gumb za spremanje, ispod popisa
  stoji „Spremi sve“, a u uređivaču vrijedi Ctrl+S. Tko isprazni popis ili
  zatvori program, biva upitan; ono što nitko ne odloži, nigdje ni ne
  ostaje. „Prikaži u mapi“ prije spremanja je zaključano – privremeno
  mjesto nije odredište kamo se nekoga šalje. Datoteka pridruživanja ide
  zajedno pri spremanju.

  U postavkama pod „Program“ „Odmah odloži rezultate uz izvornik“ vraća
  dosadašnje ponašanje. Naredbeni redak, nadzor mape i čuvar
  međuspremnika nepromijenjeno odlažu odmah – ondje nema nikoga tko bi
  mogao spremiti.

- **Alatna traka uređivača za doradu je pospremljena.** Način učenja
  sada stoji na desnom kraju uz povećalo za usporedbu i „Zamijenjene
  vrijednosti“ – tri prekidača koji uključuju i isključuju način rada
  sada stoje zajedno. „Prenesi na sve stranice“ pomaknuto je do triju
  oblika zacrnjenja, jer samo ondje nešto radi. „Kopiraj rezultat“,
  „Datoteka – Vrati na početno“ i „Prenesi na sve stranice“ nemaju
  oznaku; njihov naziv i dalje stoji u napomeni pri pokazivanju i u
  izborniku. Između „Zamijeni“ i „Vrati izvornik“ stoji crta razdvajanja:
  oba su suprotni smjerovi i jedan uz drugoga izgledali su kao dvije
  varijante istog alata.

- **Simbol za „Kopiraj rezultat“ sada prikazuje dokument.** Dva lista sa
  savijenim kutom i redcima teksta umjesto dva jednaka lista s malom
  strelicom u kutu. „Kopiraj sliku“ zauzvrat nosi znak slike, kako bi se
  oba bez oznake razlikovala. Gumb „Kopiraj“ u popisu rezultata pokazuje
  isti simbol dokumenta – odlaže istu datoteku.

- **Postavke su razvrstane i naslovljene.** „Prepoznavanje“ sada ima
  četiri odjeljka: *Što se uklanja*, *Kako se zamjenjuje*, *Koliko
  temeljito se traži* i *Prije i poslije izvođenja*. Prepoznavanje lica
  i crtični/QR kodovi stoje kod slika, gdje ih se traži; „Program“ je
  podijeljen na *Datoteke rezultata*, *Pri pokretanju*, *Ažuriranje*,
  *Prikaz* i *Povratna informacija nama*, a dodatak nazivu datoteke
  rezultata stoji kod datoteka rezultata umjesto između jezika i
  izgleda.

- **Proširena razina prepoznavanja tvornički je uključena**, i prije
  nego što se njezin jezični model učita. Prije je zadana vrijednost
  ovisila o stanju modela, pa je svježe postavljeno računalo trajno
  radilo na slabijoj razini. Prozor postavljanja na prvoj stranici nudi
  model na učitavanje i navodi cijenu uz njega. Nedostaje li, kvačica to
  i dalje kaže, umjesto da prikazuje razinu koja ne radi.

- **Dva popisa pojmova sada se zovu ono što rade:** „Uvijek ukloni“
  umjesto „Vlastiti pojmovi“ i „Nikad ne ukloni“ umjesto „Iznimke“.

- **Prozor pregleda je pregledniji.** Od devet vrijednosti stoje u dva
  stupca, retci su niži, a broj nalaza stoji izravno iza pojma umjesto
  na desnom rubu.

- **U uređivaču za doradu Zamijeni stoji ispred Zacrni** – u alatnoj
  traci, izborniku „Alati“ i desnom kliku na stranici. Zamjena je
  uobičajen slučaj: rezervirano mjesto se može kliknuti i vratiti, traka
  ne.

- **Manje dvostrukih gumba u uređivaču.** „Spremi kao …“ i „Kopiraj
  sliku“ stoje samo u izborniku Datoteka, s uobičajenim tipkovnim
  prečicama. U traci ostaje po jedan: Spremi i „Kopiraj rezultat“ –
  kamo se sprema svejedno stoji u statusnom retku i ondje se može
  promijeniti jednim klikom.

- **Čuvar međuspremnika se pri prvom pokretanju više ne nudi.** On se
  umeće u svaki postupak kopiranja u sustavu; tko program vidi prvi
  put, to ne može procijeniti. U postavkama i dalje stoji, ondje s
  odgovarajućom klauzulom uz njega.

- **Svijetli izgled manje zasljepljuje.** Pozadina prozora dosad je
  dolazila iz odgovarajućeg sistemskog stila i time bila jedina velika
  površina koju nitko nije odlučio – na Windowsu gotovo bijela. Sada je
  to prelomljena bijela, jednaka na svakom sustavu.

- **Obilazak i priručnik objašnjavaju boje.** Što crvena, narančasta,
  zelena i žuta iza zamijenjene riječi znače, sada stoji kao vlastita
  postaja u obilasku i kao odlomak u priručniku – na svim jezičnim
  inačicama.

### Riješeno

- **Priručnik i ČPP prikazivali su rezervirana mjesta koja više ne
  postoje.** Otkako je prešao na kraći oblik, Maskuro piše `[NAM1]`; u
  pomoći je i dalje stajalo `[NAME1]`, pa je rečenica „Zadano je
  `[NAME1]`“ bila jednostavno pogrešna. U sedamnaest prevedenih inačica
  uz to je stajala **njemačka** oznaka umjesto vlastite – španjolski
  čitatelj vidio je `[NAME1]`, gdje njegov program piše `[NOMB1]`.
  Jednako i nastavak datoteke rezultata: ondje su sve inačice obećavale
  `_bereinigt`, dok program stvara `_limpiado`, `_nettoyé` ili
  `_除去済み`. Zahvaćen je bio i oblik bez broja (kod anonimiziranja sve
  se zove `[NAM]`, ne `[NAME]`) i oznaka izvedena iz vrijednosti kod
  hashiranja.

- **Prozor pregleda sada prekida samo jednom po dokumentu – a drugi put
  samo kad se stvarno pojavi nešto novo.** PDF se čita s dva puta:
  jednom iz tijeka sadržaja i naposljetku s iscrtane, vidljive stranice.
  Dosad su oba pitala svako za sebe. Sada vrijedi: ono što ste odlučili
  u prvom prozoru vrijedi i dalje, a vrijednosti koje su ondje već
  stajale ne vraćaju se ponovno. Pronađe li vizualna provjera gotovih
  stranica nešto što nigdje prije nije stajalo, dobivate to ponovno
  predloženo – samo to, bez već odlučenih vrijednosti.

- **Prozor pregleda sada kaže prema čemu se odlučuje.** Umjesto „Ukloni
  kvačicu = vrijednost ostaje“ – što kvačica *radi*, ali ne kada je
  treba maknuti – ondje sada stoji: kvačicu maknite svugdje gdje ne
  stoji osobni podatak; ondje se prepoznavanje prevarilo. Uz to svaki
  prozor navodi izvođenje provjere iz kojeg njegove vrijednosti potječu.

- **Rezervirana mjesta izgledaju jednako u cijelom dokumentu.** Na
  stranicama koje se OCR putem iznova izgrađuju kao slikovne stranice,
  vidljiva rezervirana mjesta dosad su bila postavljena pisaćim strojem
  – „[PLZ4]“ tada je stajao široko i sa serifima uz uski „[NAM1]“ iste
  stranice. Sada nose isto bezserifno pismo kao i posvuda drugdje i
  više se ne postavljaju šire nego što je planirano pri uklapanju.
  Nevidljivi sloj pretrage zadržava svoje vlastito pismo – njemu trebaju
  pouzdane mjere, ne izgled.

- **U alatnoj traci uređivača više nema dvostrukih crta razdvajanja.**
  Gdje cijela skupina alata otpada za otvorenu vrstu datoteke – u PDF-u
  primjerice pregled stranice i iscrtavanje – dosad su ostajale obje
  crte oko praznine.

- **Kod vraćanja povremeno više ne ostaje samo bijelo mjesto.** Već
  točno obnovljen izvorni tekst više se ne premazuje bijelo širokim,
  sažetim okvirom svog uklonjenog rezerviranog mjesta. Kod miješanog
  vraćanja teksta i slike tekst se uz to umeće nevidljivo samo kad
  slika stranice već vidljivo nosi baš to izvorno stanje. To vrijedi za
  okvire, ploču nalaza i PDF privitke.

- **„Vrati izvornik“ više nepotrebno ne nudi rasteriziranje stranice.**
  Stroga provjera preostalog teksta ostaje aktivna kod zacrnjivanja i
  zamjene. Kod vraćanja se izostavlja: ondje se izvorni sadržaj namjerno
  vraća, a nepromijenjene susjedne riječi u proširenom okviru vraćanja
  nisu bile pogreška čišćenja, nego lažna uzbuna.

- **Obilazak kroz uređivač sada „Zamijeni“ i „Vrati izvornik“ objašnjava
  kao vlastite korake.** Oba alata izravno se ističu u traci i opisuju
  da povučen okvir umeće rezervirano mjesto odnosno vraća izvorni
  sadržaj tog mjesta iz izvorne datoteke.

- **I rezervirana mjesta specifična za zemlju sada ostaju na najviše
  četiri slova.** Te vrste dosad su nedostajale u središnjem katalogu
  kratica i mogle su se stoga pojaviti ispisane u cijelosti, primjerice
  `[UMSATZSTEUER_ID1]`. Nova izvođenja za to pišu `[UID1]`; sve
  automatski prepoznate njemačke i engleske vrste pritom ostaju
  jednoznačne. Samostalno izračunate kratice drugih jezika sučelja kod
  istoimenosti više ne rastu preko četiri znaka. Vlastite oznake pravila
  ostaju nepromijenjeno nazvane onako kako su unesene.

- **Zamjena sada koristi cijeli stvarno slobodan prostor retka, prije
  nego što zacrni.** Dosadašnja kruta granica trostruke izvorne širine
  riječi stvarala je trake i u pretežno praznim poljima obrazaca. I
  nalazi vidljive OCR protuprovjere kod zauzetog PDF teksta sada dobivaju
  čitljivo rezervirano mjesto; crn ostaje čist slikovni, napomenski i
  vektorski sadržaj, odabrani način zacrnjenja te stvarna uska mjesta u
  koja ne stane ni jednoznačan kratki oblik.

- **Već vidljivo rezervirano mjesto pri sigurnosnom rasteriziranju više
  se ne ispisuje crveno po drugi put.** Rasteriziranje sada preuzima
  postojeću zamjenu iz slike stranice i postavlja samo nevidljivu kopiju
  za pretragu. Mora li sigurnosna traka premazati baš to mjesto,
  obnavlja se cijeli stvarni okvir rezerviranog mjesta umjesto samo
  njegovog kraćeg izvornog sidra.

- **„Vrati izvornik“ sada u povučenom okviru označava samo sigurne
  mete.** Svi zamijenjeni pojmovi u njemu pojedinačno i točno
  zasvijetle; nepromijenjen tekući tekst ostaje netaknut. Stvarne
  vektorske trake zacrnjenja također se pojedinačno označavaju, ako se
  ispod njihove crne PDF površine nalazi izvorni tekst. Kod
  rasteriziranih stranica pregled namjerno izostavlja navodnu površinu
  trake: ranija pretraga slikovnih točaka ondje je spajala slova,
  podcrte i linije tablica u velike crvene površine na pogrešnim
  mjestima. Sama obnova time nije zahvaćena.

- **Kod obnavljanja na rasteriziranim stranicama tekst se ponovno
  vraća.** Naposljetku je ondje ostajalo prazno mjesto s obojenim
  pravokutnicima iznad. Vraćeni tekst stajao je u dokumentu, ali ga je
  prekrivala bijela podloga rezerviranog mjesta koje se crta dalje u
  izgradnji stranice.

- **Boje provjere više se ne slažu višestruko jedna preko druge.** Isto
  mjesto bojalo se po unosu pridruživanja – na stranici pet stvarnih
  nalaza, svaki premazan pet puta, dok od blijede oznake ne bi nastao
  zasićen blok. I više se ne pojavljuju na riječima koje uopće nisu
  zamijenjene: stoji li izvorna vrijednost i dalje na stranici, ondje
  više nema ni oznake.

## 0.10.40-beta.1 – 24. kolovoza 2026.

### Riješeno

- **Trake zacrnjenja u uređivaču sada imaju sigurnosni rub.** Okviri
  riječi, retka i slobodni okviri pokrivaju i preklapajuće glifove i
  zaglađene rubne piksele; provjera iscrtavanja dodatno osigurava da ne
  ostaju ni vidljivi ostaci ni čitljiv izvorni tekst.

- **Zamjenski tekstovi ostaju čitljivi i jednako kratki.** Nova imena,
  adrese i slobodni pojmovi pojavljuju se primjerice kao `[NAM1]`,
  `[ADR2]` i `[BEG3]`. Fiksna donja granica iznosi 4,5 točke; kod
  manjka mjesta najprije se skraćuje i proširuje upotrebljivi prostor
  retka. Stara pridruživanja s dugim rezerviranim mjestima ostaju
  čitljiva i vratljiva.

- **Višerječne zamjene iz ploče nalaza osigurane su protiv dvostrukih
  oznaka i ostataka izvornika.** Regresija prolazi s brojčanim
  rezerviranim mjestima i bez njih; po nalazu ostaje točno jedno
  zajedničko pridruživanje.

- **Vraćeni sadržaji međuspremnika na macOS-u se odmah ponovno ne
  čiste.** I kad se sistemski potpis nakon zapisivanja mijenja tek s
  odgodom, Maskuro pouzdano prepoznaje vlastiti sadržaj.

### Novo

- **Uređivač sada može datoteku potpuno vratiti na svježe očišćenu
  polaznu inačicu.** „Datoteka – Vrati na početno“ nakon potvrde odbacuje
  sve dorade trenutačne kartice, uključujući popis zamjena i brojače.
  Naredba je zaključana bez izmjena i sama se može poništiti s
  „Poništi“.

- **Pomaknuti datumi sada pouzdano zadržavaju svoju kronologiju kroz
  više datoteka.** Zajednički pomak sada se trajno ugrađuje u pravila
  već pri uključivanju strategije; uz to pomak više ne može iznositi
  nula dana i time neopaženo ostaviti stvaran datum netaknut.

- **Ručna dorada PDF-a sada pokriva potpuni profesionalni tijek
  zacrnjivanja.** Pojedini pojmovi, popisi i regularni uzorci mogu se
  tražiti i sigurno zacrniti u otvorenom PDF-u ili u svim PDF-ovima
  mape; cijele stranice i raspone stranica izravno su odabirljivi.
  Boja, neutralno bijela površina, tekst preko zacrnjenja, pismo,
  poravnanje i ponavljanje imaju pregled, a kodovi za ponovnu upotrebu
  mogu se upravljati te uvoziti i izvoziti. Čišćenje PDF-a po izboru
  uklanja sav skriveni sadržaj potpunom ponovnom izgradnjom ili samo
  odabrane klase podataka. Najsigurniji izbor jasno je preporučen,
  nevažeći uzorci pretrage se objašnjavaju, a izvođenja po mapi pišu
  isključivo kopije rezultata.

- **Dobrovoljna statistika korištenja sada pokazuje instalacije i
  promjene inačica.** Maskuro za to stvara slučajnu, lokalno pohranjenu
  oznaku instalacije. Ne sadrži podatke o uređaju, korisniku ili
  licenci; poslužitelj pohranjuje samo njezinu SHA-256 vrijednost.
  Statistika ostaje potpuno isključiva u postavkama.

- **Obilazak je sada vođena vježba kroz oba prozora.** Sam stavlja
  izmišljeni dokument za vježbu u popis, objašnjava put do čišćenja i
  nakon izvođenja automatski se nastavlja u uređivaču. Tko prekine
  obilazak, prekida i taj nastavak.

- **Prepoznaju se tvrtke iz petnaest daljnjih pravnih područja.** Tko
  čisti dokumente iz Baltika, Belgije, Skandinavije, Češke, Poljske,
  jugoistočne Europe, Singapura, Brazila ili Meksika, više ne gubi
  nazive tvrtki jer je njihov pravni oblik bio nepoznat – novo su među
  ostalim OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s.,
  S.K.A., Pte. Ltd. te S.A. de C.V. i S. de R.L.

### Promijenjeno

- **Alatne trake uređivača sada ciljanije koriste svoj prostor.**
  Jednoznačni standardni simboli i izravno prepoznatljivi oblici alata
  stoje u traci bez ponavljajućeg teksta; dvoznačne radnje zadržavaju
  svoj naziv. Pod „Prikaz“ se „Prikaži oznake alata“ može isključiti,
  kako bi se obje trake potpuno svele na simbole. Napomene pri
  pokazivanju i izbornici pritom ostaju potpuno označeni, a izbor se
  pamti.

- **Način učenja sada je trajno vidljiv u alatnoj traci.** Ondje se
  izravno uključuje i isključuje, čak i kad je pretinac zamijenjenih
  vrijednosti zatvoren. Alatna traka, izbornik alata i dosadašnja
  kvačica u pretincu uvijek pokazuju isto stanje.

- **„Vrati na početno“ na povećalu za usporedbu sada vraća samo njegov
  zum.** Gumb vraća zadanih 125 posto, bez usidravanja povećala,
  pomicanja ili promjene veličine njegovog prozora. Za cjelokupan
  izgled i dalje je nadležno „Vrati prikaz na početno“.

- **Pogreške i želje sada se mogu prijaviti i preko gumba pomoći.**
  „Prijavi pogrešku …“ i „Iznesi želju …“ ondje sada stoje jednako kao
  i u klasičnom izborniku pomoći; oba puta otvaraju već postojeću
  sigurnu prijavu pogreške odnosno javni popis želja.

- **Izbornik u traci zadataka kraći je i jasnije uređen.** Dvije naredbe
  s globalnom tipkovnom prečicom – čišćenje međuspremnika i snimka
  zaslona – sada stoje izravno jedna ispod druge sa zajedničkim desnim
  stupcem prečica. „Vrati posljednji izvorni sadržaj“ ondje otpada;
  razumljiviji gumb za vraćanje ostaje dostupan u glavnom prozoru.

- **Pravne stranice dostupne su izravno pod „Pomoć → Pravno“.**
  Podizbornik vodi do licencnih uvjeta, izjave o zaštiti podataka,
  impresuma i općih uvjeta poslovanja na maskuro.com. Napomene o
  odustanku ostaju kod kupnje na web-stranici.

- **Ručno zacrnjeni PDF-ovi pri spremanju se u potpunosti iznova
  izgrađuju.** Vidljive ostaju stranice i njihov nanovo pročitani sloj
  za pretragu; metapodaci, privitci, oznake, komentari, vrijednosti
  obrazaca, skriveni slojevi, indeksi pretrage, skripte, izrezan
  sadržaj i sadržaj skriven unutar drugih objekata ne prenose se u
  izlaznu datoteku. Pismo i vektorska grafika nakon toga sastoje se od
  slikovnih točaka – to je cijena dokazive granice prema tuđem PDF
  stablu objekata.

- **Ctrl+Shift+B sada na svim sustavima zadano snima snimku zaslona
  Maskurom.** Tipka Print Screen i njezine kombinacije ostaju moguće
  kao vlastita dodjela. U izborniku ikone trake zadataka globalne
  tipkovne prečice sada stoje desno uz pripadajuće naredbe. Vlastite
  spremljene dodjele ostaju sačuvane.

- **Uređivač se pokreće sa stranicama i povećalom za usporedbu
  lijevo.** Pretinac stranica stoji gore, otvoreno povećalo izvornika
  odmah ispod njega; zamijenjene vrijednosti ostaju desno. Namjerno
  spremljen vlastiti raspored i dalje ima prednost.

- **Dokument za vježbu više trajno ne stoji u glavnom prozoru.** Dio je
  vođene vježbe i dodatno ostaje dostupan pod „Pomoć“.

- **Prvo pokretanje sada izravno vodi u praktičnu vježbu.** Ilustrirana
  kratka uputa više se ne nudi kao drugi, sadržajno dvostruk put
  ulaska; ostaje dostupna u svakom trenutku pod „Pomoć → Kratka uputa“.

- **Mirujuća ikona u traci zadataka ostaje u punoj boji.** Sada
  prikazuje isti izraženi Maskuro štit kao i aktivan način rada
  međuspremnika; samo kod aktivnog nadzora dodaje se zelena svijetleća
  točka.

- **Dokument za vježbu ostaje u Maskuru.** Ulazni gumb stvara izmišljeni
  PDF i izravno ga umeće u popis datoteka, ali više ne pokreće dodatni
  PDF preglednik.

- **Pretraga u prozoru uređivača ostaje tečna pri tipkanju.** Prostor za
  brojač nalaza rezervira se već pri otvaranju; njegov prvi tekst više
  ne mijenja platno i ne pokreće novo rasteriziranje PDF-a.

- **Nazivi proizvođača u oznakama izvedbe ostaju vidljivi.** Unos poput
  „Izvedba: TRILUX ili istovrijedno“ opisuje potrebnu robu i više se ne
  zacrnjuje kao tvrtka samo zbog te oznake. Polja dobavljača, tvrtke i
  proizvođača time nisu zahvaćena.

- **Korpusna mjerenja predugo zacrnjene nalaze broje kao lažne
  uzbune.** Ako Maskuro ukloni očekivano ime, ali pritom zahvati i dio
  rečenice, broj lažnih uzbuna sada raste. Izvještaj takve prekoračaje
  dodatno navodi odvojeno; ranije brojke lažnih uzbuna zato nisu
  izravno usporedive.

### Riješeno

- **Tehnički i službeni pojmovi iz njemačkih izvornih dokumenata rjeđe
  se zacrnjuju kao imena ili mjesta.** Oprema vozila, retci pozicija i
  zbroja, pojmovi nabave i zaštite podataka, upute na zakone te nazivi
  datoteka javnih materijala kočeni su samo uz svoj dokazani stručni
  kontekst. Preglas izgubljen pri prepoznavanju teksta u „Marz 2026“
  ostaje zaštićen kao mjesec; „Marz“ bez veze s datumom i dalje može
  biti stvarno ime ili mjesto.

- **„Vrati izvornik“ odmah uzima punu potrebnu širinu.** Pogodi li okvir
  samo jednu riječ pridružene vrijednosti, Maskuro ga na temelju
  pridruživanja i izvornog retka samostalno proširuje na cijeli
  podatak – primjerice s „Planungs“ na „Nordlicht Planungs GmbH“.
  Naknadno dohvatljiv okvir također prikazuje stvarno vraćenu ukupnu
  širinu.

- **„Vrati izvornik“ sada crne trake prikazuje kao jednoznačnu metu.**
  Pri prelasku ili povlačenju cijela prepoznata traka zasvijetli crveno
  s jasnim kontrastnim rubom, umjesto tek teško prepoznatljivog okvira
  teksta pored. To vrijedi i za rasterizirane stranice na kojima se
  traka sastoji samo od slikovnih točaka.

- **Obilazak uređivača više ne preskače postaje kad su pretinci bili
  zatvoreni.** Za vodstvo Maskuro privremeno sam otvara i raspoređuje
  pretinac stranica, povećalo za usporedbu i zamijenjene vrijednosti.
  Nakon „Gotovo“ ili prekida vraća se osobni raspored. Nije li neki
  alat kod vrste dokumenta uopće dostupan, njegovo objašnjenje ostaje
  kao tekstualna postaja, umjesto da neopaženo nestane.

- **„Zamijeni“ ostaje vidljivo i kod sigurnosnog rezervnog puta PDF-a.**
  Morao li Maskuro stranicu zbog preostalog znaka ili oštećenog toka
  teksta iznova izgraditi kao sliku, ispravne su zamjene ostajale samo
  nevidljive u sloju za pretragu, dok su na stranici ostajale crne
  trake. Stvarno postavljene zamjenske vrijednosti sada ostaju vidljivo
  crvene i pretražive kroz sve ponovne izgradnje rasteriziranjem i
  prepoznavanjem teksta.

- **Napomene iznad očišćene inačice ostaju čitljive u tamnom izgledu.**
  Naslov inačice, redak upravljanja i uvod sada boju pisma preuzimaju
  izravno iz stvarno prikazanog Qt prozora.

- **Trake zacrnjenja na rasteriziranim PDF stranicama ponovno sjede
  iznad teksta.** Nevidljivi okviri riječi bili su, ovisno o izvornom
  pismu, uži od vidljivih slova. Time su nastajale praznine u traci ili
  je posljednje slovo ostajalo čitljivo. Okviri sada zadržavaju
  širinu, visinu i smjer pisanja vidljive riječi.

- **„Što je novo“ ponovno počinje sasvim od vrha.** Dijalog changeloga
  nakon dovršene izgradnje prozora izričito postavlja tekstualni
  pokazivač i traku pomicanja na početak, umjesto da ovisno o stanju
  Qt-a počne usred novosti.

- **Zatvaranje tijekom prepoznavanja riječi na skenu ostaje tiho.**
  Pozadinsko izvođenje prepoznavanja teksta koje se upravo dovršava
  više ne šalje u već zatvoren prozor uređivača.

- **Relativne vremenske oznake više se ne smatraju imenima.** Ustaljene
  fraze poput „danas“, „jučer“, „sutra“ i „sljedeći tjedan“ Maskuro
  sada poznaje iz službenih kalendarskih podataka odgovarajućeg jezika
  dokumenta.

- **Izlaz tijekom prvog učitavanja modela sada čisto pospremi za
  sobom.** Tko zatvori Maskuro ili prozor uređivača neposredno nakon
  otvaranja, više ne ostavlja nit koja još radi u izvornom prepoznavanju
  govora pri rušenju procesa. To sprječava povremeni izvještaj o
  rušenju pri izlazu; već pokrenuto učitavanje uredno se dovršava.

- **Odgođeni dijalozi pri pokretanju više se ne pojavljuju nakon
  izlaza.** Tko zatvori glavni prozor ubrzo nakon pokretanja, više
  naknadno ne dobiva nevidljivo ili zakašnjelo prikazano pitanje o
  najboljem prepoznavanju, novostima ili uvodu.

- **HTML i e-pošta zadržavaju svoje završetke redaka.** Na Windowsu je
  HTML serijalizacija nakon čišćenja i vraćanja miješala LF i CRLF.
  Sadržaj i oblikovanje bili su ispravni, no datoteka više nije bila
  bajtno jednaka. HTML datoteke i MIME poruke sada ponovno preuzimaju
  zapis svog izvornika.

- **Nazivi tvrtki s prijedlogom ostaju potpuni.** Iza prijedloga Maskuro
  je nazive poput „Gesellschaft für Systemtechnik mbH“ ili „Bank für
  Arbeit und Wirtschaft AG“ odsijecao na riječi „für“. Cijeli naziv
  tvrtke sada se prepoznaje; stvarni uvodi rečenice poput „Osigurani smo
  kod Alpha GmbH“ ostaju vidljivi.

- **Kineski nazivi tvrtki ostaju potpuni ispred svog pravnog oblika.**
  Sastavni dio marke koji se mogao protumačiti kao glagol mogao je,
  unatoč jednoznačnom dodatku „有限公司“, odbaciti cijeli naziv. U
  pismima bez velikih i malih slova službeni sidro pravnog oblika sada
  ima prednost pred tom nesigurnom granicom vrste riječi.

- **PDF stranice bez potrebe postajale su slike.** Kod višestraničnih
  PDF-ova čije stranice dijele popis pisama – tako ih grade uobičajeni
  izrađivači – sve sljedeće stranice nakon prve gubile su vezu sa
  svojim pismima. Posljedica je bila dvostruka: preglasi u rezultatu
  više nisu bili pretraživi („Auftragsbestätigung“ nije se moglo
  pronaći), a naknadna provjera potom je smatrala previđenima slova
  koja nikad nisu ni stajala na stranici – zdrave tekstualne stranice
  rasterizirala je u slike, čime one više nisu bile pretražive,
  kopirljive i znatno su bile veće. U ispitnom skupu to je pogađalo
  četiri od sedamnaest stranica.
- **Sam zarez više ne pokreće rasteriziranje.** Završava li područje
  nalaza na riječi, interpunkcijski znak pored njega još se tijesno
  ubraja u nju. No zarez ili točka nisu previđen podatak, a
  rasteriziranje košta cijelu stranicu. Slova i znamenke i dalje ostaju
  razlog za doradu.

## 0.10.38-alpha.20260824 – 24. kolovoza 2026.

### Novo

- **Nazivi tvrtki bez pravnog oblika sada se prepoznaju kad ih navodi
  njihova oznaka.** „Dobavljač: Kranzbichler Handels GmbH“ oduvijek se
  uklanjao – pravni oblik odaje tvrtku. „Dobavljač: Dehner Märkte“
  ostajao je netaknut, a u ponudama, natječajima i narudžbama
  dobavljač najčešće stoji baš tako. Isto vrijedi za „Tvrtka:“,
  „Proizvođač:“, „Izvedba:“, „Poslodavac:“ i njihove istovrijednice u
  osam daljnjih jezika, i kad oznaka sama stoji na svom retku, a naziv
  ispod nje.

  Ono što iza oznake *nije* tvrtka, ostaje netaknuto: „Dobavljač: vidi
  privitak“ se ne zacrnjuje – inače bi ondje stajalo „Dobavljač:
  [ORGA1]“, a to bi tvrdilo ime koje nikad nije postojalo. Oznake iza
  kojih jednako često stoji čovjek („Kupac:“, „Naručitelj:“) namjerno
  nisu uključene.

- **Umetnuta slika sada se može i obrađivati.** U prozoru „Očisti
  sliku“ uz „Kopiraj rezultat“ stoji gumb *Obradi u uređivaču*: slika
  se čisti i zatim otvara za dodatno prekrivanje, označavanje i
  isticanje – isti put kojim ide snimka zaslona.

- **Brojevi iza svoje oznake sada se pronalaze i kad imenuju poslovnog
  partnera.** Dosad su otpadali brojevi kupca, ugovora i osoblja; sada
  i broj dužnika, vjerovnika i dobavljača, austrijski broj poslodavca,
  ANKÖ registracija te WEEE, EAR i EPR broj proizvođača – na njemačkom
  kao i na engleskom. Uz to Maskuro sada razumije zapis postavljenih
  zaglavlja ponude s razmakom ispred dvotočke („Kupac-br : K903944“).
  Brojevi artikla, narudžbe, naloga, ponude i računa ostaju i dalje
  netaknuti: oni imenuju postupak ili robu, ne osobu. Tko ih ipak želi
  ukloniti, pohranjuje ih kao vlastiti uzorak pretrage.

- **Sada vidite koliko je vremena trebala datoteka.** Uz gotov redak
  stoji trajanje pored prepoznatog jezika („gotovo · njemački · 2,4
  s“), u sažetku trajanje cijelog izvođenja, u klapi s kazaljkama zbroj
  – a u izvještaju provjere stoji kao vlastito polje. Kod više datoteka
  redak odaje koja je od njih oduzela vrijeme.

- **Pisma koja sistemski OCR ne podržava mogu se zamjenski čitati uz
  postojeću jezičnu datoteku.** Dosad je vrijedilo: ne vlada li
  sistemsko prepoznavanje teksta pismom (na Macu npr. devanagari), u
  rezultatu je stajalo „slika(e) NISU provjerene“, a podaci na slici
  ostajali su netaknuti. Sada uskače priloženo prepoznavanje teksta,
  ako je odgovarajuća jezična datoteka dostupna. Jer je tako pročitana
  slika manje pouzdana od redovno provjerene, to stoji u rezultatu:
  „pročitano zamjenskim postupkom – molimo pregledajte“. Izmjereno na
  povijesnom međustanju hindskog testa: **deset podataka više pronađeno
  i četiri lažne uzbune manje** (64 % → 73 %). Trenutačna konačna
  vrijednost stoji dalje gore i time se s ovime ne smije zamijeniti.

- **Prepoznavanje teksta pita za pravi jezik.** Za sve jezike dokumenta
  osim njemačkog i engleskog dosad se koristio engleski model
  prepoznavanja, čak i kad je odgovarajuća jezična datoteka bila
  dostupna. Na Windowsu to se odnosilo na svaki jezik – grčki, japanski
  ili hindski ondje su se čitali engleskim modelom.

- **Čarobnjak za postavljanje pri baš prvom pokretanju.** (Tko je
  Maskuro već koristio, ne dobiva ga – „prvo pokretanje“ znači prvo
  pokretanje, ne prvo pokretanje nakon ovog ažuriranja.) Tri pitanja
  umjesto šest slika: jezik vaših dokumenata, čita li se i tekst na
  slikama i kako želite dosezati Maskuro u svakodnevnom radu. Na kraju
  i dalje stoje tri puta – dokument za vježbu, obilazak ili ilustrirana
  kratka uputa. Sve se može preskočiti, a „Pomoć → Ponovno prođi
  postavljanje“ ga vraća.

- **F1 otvara priručnik na odgovarajućem poglavlju.** U glavnom prozoru,
  u postavkama (ondje ovisno o stranici), u prozoru pregleda i u
  upravljanju jezicima; u prozoru uređivača preko Shift+F1, jer F1
  ondje oduvijek pokazuje tipkovne prečice. Dosad je pomoć uvijek
  počinjala od vrha, kod 25 poglavlja.

- **Novo prvo poglavlje priručnika: „Krenite za tri minute“.** Četiri
  koraka, više za dokument nije potrebno – na svih 18 jezičnih inačica.

- **Obilazak kroz prozor.** „Pomoć → Obilazak kroz prozor“ postavlja
  reflektor na jedan upravljački element za drugim i uz njega piše
  rečenicu – u glavnom prozoru osam postaja, u prozoru uređivača
  sedam. Za razliku od ilustrirane kratke upute, on objašnjava prozor
  pred kojim upravo sjedite. Prekid u svakom trenutku s Esc.

- **Dokument za vježbu za bezopasno isprobavanje.** Ispod površine za
  odlaganje sada stoji „Otvori dokument za vježbu“ (i u izborniku
  Pomoć). Stvara izmišljeni list – ime, adresa, telefonski broj, IBAN,
  broj socijalnog osiguranja – a na listu ujedno stoji što s njim
  možete učiniti i što ćete nakon toga vidjeti. Nijedna riječ ne
  pripada stvarnoj osobi; prvi dokument koji pošaljete kroz Maskuro
  time ne mora biti pravi.

- **„Samo pogledati …“ sada stoji uz „Očisti“.** Pokazuje gdje leže
  osobni podaci – datoteka, vrsta i broj – bez ikakve promjene ili
  pisanja. Tko je odložio dokument, time ga najprije pregleda prije
  čišćenja. Dosad je taj put bio samo u izborniku Datoteka pod
  „Pregledaj mapu …“ i vodio kroz cijelu mapu umjesto kroz odložene
  datoteke.

- **Nije li ništa pronađeno, sada stoji zašto bi to moglo biti.**
  Primjerice: u datoteci su slike, ali „Provjeri i tekst na slikama“ je
  isključeno. Ili: postavljeni jezik ne odgovara jeziku u dokumentu. A
  ne nalazi li se ništa slično, Maskuro to i kaže.

- **Prozor uređivača vas prvi put dočekuje s tri rečenice:** klik
  zacrnjuje riječ, povlačenje područje, desno stoje zamijenjene
  vrijednosti. „Razumijem“ trajno uklanja napomenu; „Pomoć → Ponovno
  prikaži uvod“ je vraća.

- **Klik na riječi sada radi i na skeniranim stranicama.** Dosad su se
  riječi mogle klikati samo ondje gdje PDF donosi tekstualni sloj – na
  skenu nije išlo, a unutar istog dokumenta moglo se mijenjati od
  stranice do stranice. Takve se stranice sada jednokratno čitaju
  prepoznavanjem teksta; nakon toga se riječi klikaju kao svugdje
  drugdje. Statusni redak kaže što se upravo događa.

- **Pretinac stranica ponovno je površina.** Prestajao je usred svog
  stupca: naslovna traka odsječena, pored trake u drugoj boji, a
  trenutačna stranica prepoznavala se samo po obojenom kvadratiću iza
  svog broja. Sada ispunjava svoj stupac, može se povući šire, a
  trenutačna stranica istaknuta je kao cijela pločica – s netaknutim
  pregledom stranice u sebi.

- **Zamijenjena mjesta svijetle blijedožuto.** U pregledu stranice tako
  je na prvi pogled vidljivo gdje je nešto zamijenjeno – ista boja koju
  povećalo za usporedbu koristi iznad izvornika. Crveni okvir pri
  pokazivanju mišem ostaje nepromijenjen.

- **„Vrati prikaz na početno“ u prozoru uređivača** (izbornik
  „Prikaz“). Tko je pretinac stranica ili popis nalaza pomaknuo,
  odvojio ili zatvorio, time sve vraća onamo gdje je stajalo pri prvom
  pokretanju.

### Promijenjeno

- **Rezervirana mjesta su kraća.** Iz `[SOZIALVERSICHERUNGSNR_1]`
  nastaje `[SVNR1]`, iz `[ORGANISATION_1]` `[ORGA1]`, iz `[EMAIL_1]`
  `[MAIL1]`. Razlog nije ljepota: rezervirano mjesto dulje od
  vrijednosti koju zamjenjuje razvlači redak i u uskom stupcu tablice
  za njega uopće nema mjesta – ondje je dosad ostajala crna traka, a
  ona nikome više ne kaže da je ondje nešto stajalo. Gdje postoji
  uobičajena kratica, ona stoji (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`).
  Rezultati ranijih izvođenja ostaju upotrebljivi: stari zapis i dalje
  se prepoznaje, a jučerašnje datoteke pridruživanja rade nepromijenjeno.

- **Ikona programa sada posvuda stoji jednako.** U izborniku Maca dosad
  se pojavljivao jednobojni štit koji je sustav sam bojao crno ili
  bijelo, na Windows traci zadataka zelen odnosno siv. Sada svaka
  traka nosi isti plavi Maskuro štit. Po čemu se vidi nadzire li se
  međuspremnik, ostaje jednako jasno: radi li nadzor, na štitu sjedi
  zelena točka; miruje li, isti štit stoji blijed. I u najmanjim
  veličinama sada u štitu stoje obje trake zacrnjenja – dosad je traka
  zadataka ondje pokazivala samo jednu.

- **Lica se prepoznaju modelom čije su slike za treniranje nastale uz
  pristanak.** Isporučuje se sada MediaPipe BlazeFace (Apache-2.0);
  dosadašnji detektor ostaje ugrađen i dostupan za prebacivanje, ali
  se više ne isporučuje, jer njegovo podrijetlo treniranja nije
  konačno razjašnjeno. Za prepoznavanje se ništa ne mijenja: na 324
  portreta i 143 slike bez lica nova inačica pronalazi jednako mnogo
  uz jednako malo pogrešnih zahvata i treba trećinu vremena.

- **OCR je sigurnosno sidro za najjaču PDF razinu.** Redoviti PDF put ga
  koristi i stvara potpunu minimalnu izgradnju. Tko OCR izričito
  isključi, dobiva kompatibilniji objektni put; sučelje, poruka o
  dovršetku i priručnik sada izričito kažu da taj put ne pruža istu
  arhitekturu protiv nepoznatih skrivenih PDF kanala.

- **Prodajni prekidač sada blokira i dosad priloženi YuNet model.** MIT
  licenca točne težine ostaje dokumentirana, ali za javno vidljiv lanac
  podataka za treniranje preko WIDER FACE ne dostaje kao konzervativna
  potvrda za proizvod. Prije prodaje potrebno je pisano razjašnjenje
  ili zamjena modelom s pouzdanim komercijalnim lancem podataka i
  težina.

- **Nazivi tvrtki i organizacija sada se automatski uklanjaju.** Dosad
  su ostajali netaknuti dok ih se nije izričito zatražilo. To je za
  poslovno pismo bila pogrešna zadana vrijednost: tko prosljeđuje
  ponudu, ne želi u njoj čitati naručitelja. „Kranzbichler Handels
  GmbH“, „Institut für Bauphysik“ i slično zato se tretiraju kao ime.
  Tko to treba drugačije, isključuje u prozoru; na naredbenom retku
  prekidač se sada zove `--ohne-organisationen`. Stari
  `--mit-organisationen` i dalje se prihvaća i više ništa ne radi, kako
  postojeće skripte i prečaci ne bi puknuli. Datumi i novčani iznosi
  ostaju nepromijenjeno izuzeti.

- **Zacrnjivanje sada ima tri oblika umjesto dvije kvačice.** „Riječi“,
  „Cijeli redak“ i „Slobodni okvir“ stoje kao jedan izbor jedan uz
  drugoga – uvijek vrijedi točno jedan. Dosad su „Retci teksta“ i
  „Cijeli redak“ bila dva neovisna prekidača koji su oba mogla biti
  pritisnuta, a slobodni okvir uopće nije bio gumb, nego isključeno
  stanje prvog. Sada tri stoje vidljivo uz svoj alat i sivi su dok je
  odabran neki drugi alat.

### Poboljšano

- **Prvi dokument gotov je oko sekundu brže.** Prije početka čišćenja
  Maskuro utvrđuje jezik dokumenta – i za to je dosad dohvaćao popise
  riječi svih 48 jezika putem koji je učitavao mnogo više od samih
  riječi. To je bilo otprilike pola vremena čekanja do prvog rezultata.
  Samo prepoznavanje ostaje nepromijenjeno: vidi iste riječi kao i
  prije, samo brže. Svaki sljedeći dokument time ionako nije bio
  zahvaćen.

- **Dokumenti s vrlo dugim odlomcima provjeravaju se brže.** Kod
  odlomka bez prijeloma retka Maskuro ga je za svako pronađeno mjesto
  ponovno čitao u cijelosti; sada je dovoljno jednom. Što je odlomak
  dulji, to je razlika veća – izmjereno oko sedmine manje vremena
  računanja. Na rezultatu se ništa ne mijenja.

### Riješeno

- **S tvrtkom je često nestajala i polovica rečenice.** Stajao li naziv
  tvrtke u tekućem tekstu – „Obavijest o Gottwald GmbH & Co KG“, „…
  (opći uvjeti) tvrtke Musterbetriebe GmbH“ – nije se zacrnjivalo samo
  ime, nego sve ispred njega do početka rečenice. Tekst je time postajao
  nečitljiv, i izgledalo je kao da je zacrnjeno nasumično. Nazivi
  tvrtki koji sami nose „für“ ili „und“ („Bank für Arbeit und
  Wirtschaft AG“) pritom ostaju nepromijenjeno potpuni.

- **Nazivi tvrtki ostajali su u zaglavljima pisma, iako su u tekstu
  uklonjeni.** U jednoj ponudi sjedište tvrtke u slici zaglavlja pisma
  ostajalo je čitljivo – isto mjesto koje je Maskuro zacrnio u tekućem
  tekstu; u pretraživom tekstu rezultata čak je nevidljivo i dalje
  ostajalo unutra. Ono što je jednom uklonjeno sada se uklanja i ondje
  gdje postoji samo kao slika. To djeluje i kod logotipa i znakova
  riječi nacrtanih kao grafika.

- **macOS je pri svakom pokretanju pitao za snimanje zaslona**, čak i
  kad je dopuštenje odavno bilo dano. Napomena pri pokretanju
  isprobavala je snimanje, a baš to dovodi sistemski dijalog na
  zaslon. Sada pri pokretanju pita samo sam Maskuro, i to samo jednom;
  sustav pita tek kad stvarno napravite snimku zaslona.

- **Tehnički stručni pojmovi smatrani su mjestima i tvrtkama.**
  „Einspeisepunkt“, „Flachdach“, „Verteileranlage“, „Meldersockel“ i
  desetci sličnih riječi nestajali su iz ponuda i troškovnika. Maskuro
  ih sada prepoznaje po osnovnoj riječi: ono što završava na „-anlage“,
  „-punkt“ ili „-kanal“ je stvar. Nazivi mjesta poput Berlina, Melka ili
  Wieselburga nemaju takvu osnovnu riječ i ostaju netaknuti – jednako i
  adrese poput „Der Graben“ ili „Alter Markt“.

- **Japanski, korejski, kineski, tajlandski i gudžaratski dokumenti mogli
  su srušiti program.** Sadržavao li dokument na jednom od tih pet
  jezika internetsku adresu bez „https://“ ispred, čišćenje se
  prekidalo internom pogreškom – kod otvorenog prozora time se gubio i
  ostali rad. Svih četrdeset osam odabirljivih jezika dokumenta sada
  prolaze; nedostaje li za jezik rječnik učestalosti, podatak u dvojbi
  ostaje netaknut umjesto da nestane.

- **Oznake polja štitile su samo na njemačkom i engleskom.**
  „Reference“ ostajao je netaknut, talijanski „Riferimento“ i
  portugalski „Referência“ uklanjani su kao podatak o mjestu – isti
  naziv polja, isti redak, drugačiji rezultat. Tko nije radio na
  engleskom, bio je time u lošijem položaju. Maskuro sada u svih
  jedanaest održavanih jezika poznaje iste nazive polja.

- **„Vrati izvornik“ na skeniranim stranicama vraćao je previše.**
  Okvir preko zacrnjenog retka bloka adrese ponovno je otkrivao **cijeli
  blok** – a stranica je ostajala rastrgana: ostaci traka i dalje su
  stajali, iz kojih su virili krajevi pojedinih riječi. Razlog je bio
  da se trake jedna ispod druge na rasteriziranoj stranici dodiruju i
  zato vrijede kao jedna jedina površina. Sada se vraća točno redak na
  koji okvir pokazuje; susjedni retci ostaju zacrnjeni, a traka
  pogođenog retka potpuno nestaje.

- **Količine u popisima pozicija smatrane su adresama.** U retku poput
  „1.4 Kabelgraben 100,00 m“ „Kabelgraben 100“ bio je zamijenjen kao
  ulica s kućnim brojem. Takvi retci sada ostaju netaknuti; stvarne
  adrese – i „Hauptplatz 1, 3250 Wieselburg“ – prepoznaju se
  nepromijenjeno.

- **Ispred naziva tvrtke nestajala je polovica rečenice.** Iz „Ugovor
  između tvrtke Gottwald GmbH & Co KG i naručitelja.“ nastajalo je
  „[ORGANISATION_1] i naručitelja.“ – početak rečenice bio je nestao, a
  s njim i naznaka o čemu je riječ. Sada otpada samo sam naziv tvrtke.
  Gdje opća riječ pripada nazivu („Deutsche Bank AG“, „Universität
  Wien“), sve ostaje kao dosad.

- **U zapisniku su ostajali stajati govornici čije je ime ujedno
  zanimanje.** „Bauer:“, „Koch:“, „Weber:“ ispred izlaganja bili su
  previđeni, „Gruber:“ pored ne – Maskuro je dosad trebao barem jedno
  prepoznato ime u dokumentu da bi retke uopće čitao kao izlaganja.
  Nosi li dokument naslov poput „Zapisnik rezultata“ ili „Zapisnik
  sjednice“, sada je to dovoljno. Napomenski retci („Pozor: …“,
  „Napomena: …“) ostaju netaknuti.

- **Oznaka polja nestajala je zajedno sa svojom vrijednošću.** Iz
  „Projekt: Sanacija i proširenje mjesnog centra“ nastajalo je jedno
  jedino rezervirano mjesto – i riječ „Projekt:“ je nestajala, a s njom
  i naznaka što je ondje stajalo. Oznake sada ostaju netaknute. Gdje
  oznaka pripada podatku i nosi njegovo značenje („Interni broj 214“),
  ništa se ne mijenja.

- **Maksimalno prepoznavanje nije čistilo stručne pojmove.**
  „Flachdach“, „Einspeisepunkt“, „Elektrotechnik“ i slične stručne
  riječi zamjenjivane su kao mjesto ili tvrtka i uz uključenu AI
  razinu – AI baš te nalaze nikad nije dobivao na ocjenu. Sada ih
  provjerava zajedno: na korpusu natječajnih i ugovornih tekstova time
  nestaje svih 27 pogrešnih zahvata, bez da ijedan pravi podatak
  ostane. Imena, tvrtke i mjesta i dalje se prepoznaju nepromijenjeno.

- **Opće riječi za vrste ustanova smatrane su organizacijama.** U
  ugovornom tekstu nestajali su „Visoke škole i sveučilišta“, „Državne i
  privatne škole“, „Akademske nastavne bolnice“, „Obrazovna ustanova“ i
  „Podizvođačke tvrtke“ – riječi koje ne imenuju određeno mjesto, nego
  vrstu mjesta. Sada ostaju netaknute. Stoji li ispred njih vlastito
  ime („EU-komisija“), i dalje se zamjenjuju, a nazivi tvrtki tim
  pravilom uopće nisu obuhvaćeni.

- **Imena u popisima otpadala su samo ako su bila česta.** U popisu
  sudionika ili prisutnosti ispod zaglavlja stupca „Ime“ uklanjani su
  „Anna Huber“ i „Thomas Müller“, ali „Wójcik Aleksandra“ ili
  „Kücükgöl Sinan“ ne – isti redak, isti oblik. Tko nosi rjeđe ime,
  bio je time slabije zaštićen. Sada odlučuje zaglavlje stupca: što
  stoji ispod „Ime“, ime je. Popis pozicija sa stručnim zaglavljem
  stupca ostaje netaknut.

- **Telefonski broj iza „Interni broj“ bio je prerezan po sredini.** Iz
  „Interni broj 0732 771190“ nastajalo je „[DURCHWAHL_1] 771190“ –
  druga polovica broja ostajala je čitljiva. Sada cijeli broj otpada u
  cijelosti, a oznaka ostaje netaknuta. Stvarni interni broj („Interni
  broj 214“) i dalje se zamjenjuje zajedno sa svojom oznakom.

- **Neki PDF-ovi uopće se više nisu mogli čistiti.** Ne da li se profil
  boje ili metapodaci u slici dokazivo ukloniti, izvođenje se
  prekidalo bez rezultata – zahvaćeni su bili obični poslovni
  dokumenti poput stranica općih uvjeta, tehničkih zadataka i
  natječaja. Takve se datoteke sada čiste, a upozorenje navodi mjesta
  koja su ostala otvorena: mogu nositi oznaku uređaja, autora ili
  snimanja. Izvornik kao i uvijek ostaje nepromijenjen.

- **Ugovorne uloge smatrane su osobama.** „Ponuditelj“, „Potrošač“,
  „Najmoprimac“, „Kupac“, „Naručitelja“ i oko četrdeset daljnjih riječi
  uloga zamjenjivane su gdje su stajale bez člana – u naslovima
  ugovora, stupcima tablica i recima potpisa. Ugovorni tekst bez
  ijednog osobnog podatka time je mjestimično postajao nečitljiv. Te
  riječi sada ostaju netaknute. Stoji li pored njih naznaka osobe –
  oslovljavanje, ime, riječ polja poput „Osoba za kontakt“ – i dalje se
  zamjenjuju: „Gospodin Ponuditelj“ i „Gospođa Kupac“ su imena. Česta
  prezimena koja su ujedno i zanimanja (Bauer, Richter, Koch) tim
  pravilom uopće nisu obuhvaćena.

- **Skraćeno pisana ulica bila je previđena kad je kućni broj bio
  izravno uz točku.** „Schlesischestr.31“ nije vrijedilo kao adresa – a
  jer poštanski broj pored svoj oslonac dobiva iz nalaza adrese,
  ostajao je i on. U rezultatu se adresa mogla ponovno sastaviti iz
  ulice i poštanskog broja, i to samo na nekim stranicama istog
  dokumenta. Sada oboje otpada zajedno. Stručni nazivi s pridodanim
  brojem („Kabelrinne200“) ostaju netaknuti.

- **Adresa preko dva retka bila je sažeta u jedno jedino rezervirano
  mjesto.** Stajao li u bloku adrese poštanski broj iznad ulice, Maskuro
  je oba retka spajao u jedno mjesto nalaza: u rezultatu je nestajao
  prijelom retka, a poštanski broj ostajao je čitljiv ispred njega.
  Sada se svaki redak pronalazi i zamjenjuje zasebno, a slika teksta
  ostaje sačuvana. Isti uzrok povremeno je u adresu uvlačio i prezime
  iz retka iznad.

- **Maksimalni PDF put više ne preuzima izvorne objekte.** Uz uključeno
  prepoznavanje teksta Maskuro svaku stranicu potpuno iznova gradi iz
  vidljive PDFium slike. U novu minimalnu datoteku ulazi samo ta
  slikovna stranica i novostvoren, na OCR tekst ograničen sloj za
  pretragu – ne tuđe stablo objekata s komentarima, privitcima,
  akcijama, slojevima, metapodacima, profilima boje ili privatnim
  ključevima. To vrijedi i za sadržaj u napomenskim prikazima,
  uzorcima, Type-3 pismima, objektima obrasca i mekim maskama. Izvorna
  datoteka ostaje netaknuta.

- **Lica i kodovi u ugniježđenoj PDF grafici bili su previđeni.** Oba
  detektora sada dodatno vide potpunu iscrtanu sliku stranice. Time i
  portreti te QR/crtični kodovi u napomenama, uzorcima, Type-3
  glifovima i maskama prozirnosti dolaze do detektora; prepoznata
  područja – ako je uključeno – čine se neprepoznatljivima prije
  minimalne izgradnje. Sama detekcija ostaje pogreška.

- **Nedostajući OCR stroj kod PDF-ova završavao je internom
  pogreškom.** Maksimalno izvođenje sada se prekida kontrolirano i bez
  ciljne datoteke, umjesto da isporuči nepotpunu ili neprovjerenu
  datoteku.

- **Više stvarnih kontaktnih i poslovnih vrijednosti prolazilo je
  neprepoznato, dok se stručni tekst zamjenjivao.** Polja imena preko
  prijeloma redaka, nazivi banaka i tvrtki, pravni oblici, označeni
  identifikacijski brojevi, datumi rođenja te granice telefona, URL-a
  i IBAN-a strože su provjereni. Istodobno zemlje u stručnom tekstu,
  riječi uloga i opće riječi, kodovi artikla/norme, nizovi brojeva i
  uobičajene kratice češće ostaju netaknuti.

- **Miješani i zaokrenuti OCR retci pogrešno su se čitali.** Nesigurne
  okomite riječi sada se lokalno uspravljaju i ponovno čitaju; tehničke
  latinične vrijednosti u nelatiničnom tekstu dobivaju neovisnog
  engleskog svjedoka. Samostojeća nesigurna pojedinačna znamenka
  ispravlja se samo ako se dva uska niza znamenki podudaraju. Poljski
  pravni oblici u OCR obliku „sp. z 0.0.“ u zatvorenom kontekstu čitaju
  se kao „sp. z o.o.“.

- **Mjerenje slika moglo je previdjeti djelomično vidljive ostatke
  vrijednosti.** Sada provjerava preklapajuće lokalne izreske,
  razlikuje bijelo pismo rezerviranog mjesta na crnoj traci od
  izvornih glifova i prenosi okvire sirove slike i na zaokrenute,
  nanovo iscrtane minimalne PDF-ove. Fiksni sintetički glavni korpus
  time postiže 1.392/1.392 uklonjenih ciljanih podataka uz 0 lažnih
  uzbuna i 0 pogrešaka obrade. To je dokaz na korpusu, ne opće
  obećanje 100 posto.

- **Nekomercijalni jezični modeli više se ne nude.** Šest talijanskih i
  grčkih spaCy varijanti pod CC BY-NC-SA 3.0 uklonjeno je iz kataloga,
  preuzimanja i puta učitavanja; ignoriraju se i već postojeće mape
  modela. Oba jezika umjesto toga koriste MIT licencirani višejezični
  model.

- **Ime ispod „Osoba za kontakt“ bilo je uklonjeno samo napola.** Stoji
  li oznaka sama na retku, a ispod nje „Prezime Ime“, ime je ostajalo
  netaknuto čim je ujedno bilo obična riječ – iz „Mayer Roman“ nastajalo
  je „[NAME_1] Roman“. Takvi retci sada se uzimaju u cijelosti. Odjel
  na istom mjestu („Technischer Innendienst“) i dalje ostaje netaknut.
  Usput riješeno: „Osoba za kontakt“ uopće se nije brojila kao polje
  imena, iako „Kontaktperson“ to oduvijek jest.

- **Naziv tvrtke bez pravnog oblika ostajao je netaknut kad je između
  stajala riječ struke.** „Kranzbichler Handels GmbH“ bio je uklonjen,
  goli „Kranzbichler“ tri odlomka kasnije ne – kod „Kranzbichler GmbH“
  naprotiv da. Sada djeluje oboje. Uobičajene riječi su iz toga
  izuzete: „Deutsche Bank AG“ ne čini „deutsche“ u tekstu tvrtkom.

- **Ista vrijednost u istom dokumentu zvala se jednom ime, jednom
  mjesto.** „Anna Musterfrau … Musterfrau“ davalo je „[NAME_1]“ i
  „[ORT_1]“ – na drugom mjestu nedostaje ime, a bez njega je od toga
  nastalo mjesto. Uklonjeno je oboje, ali se čitalo kao dvije različite
  stvari. Vrijednost sada zadržava oznaku svog prvog pojavljivanja.

- **Datumi se više nisu uklanjali.** Datum posve od znamenki
  („01.03.2026“) od posljednje je inačice propadao kroz provjeru
  namijenjenu imenima i ostajao u dokumentu – i u načinu rada
  „pomakni“, i bez retka u izvještaju provjere. Zahvaćen je bio samo
  tko je izričito uključio datume.

- **Zemlje i kontinenti se više ne zacrnjuju.** „Isporuka ide u
  Sjedinjene Države“, „Slabost tržišta u Aziji“, „norma vrijedi u
  Rumunjskoj“ – takvi podaci ne govore ništa o osobi i sada ostaju
  netaknuti. Pripada li naziv zemlje naprotiv adresi ili stoji iza
  oznake poput „Prebivalište“ ili „Mjesto rođenja“, i dalje se
  uklanja. **Gradovi nisu zahvaćeni** – „Upravo sam u Bilbau“ ostaje
  podatak o osobi i i dalje se zacrnjuje.

- **Skraćene riječi postajale su web adrese.** Stoji li u tekstu „npr.
  njemačka“ ili „uklj. tog“, neki PDF isporučuje točku bez razmaka –
  time je nastajalo „npr.hr“ odnosno „uklj.hr“, valjana adresa sa
  zemaljskim nastavkom, i bila je uklonjena. Takvi parovi riječi sada
  ostaju netaknuti. Stvarne adrese nisu zahvaćene, ni bez „www.“
  ispred.

- **Stupci brojeva iz bilanci zacrnjivani su kao telefonski brojevi.** U
  poslovnim izvještajima i cjenicima prošla i tekuća godina stoje jedna
  uz drugu – „64.518 65.133“. To je vrijedilo kao jedan telefonski
  broj i bilo uklanjano, jednako i rasponi brojeva poput „12200-23200“
  i datum s brojem koji slijedi. Takvi brojevi sada ostaju netaknuti.
  Obrnuto, stvaran telefonski broj sada se pouzdanije prepoznaje:
  oznake „Telefon“, „Faks“, „Mobitel“, „Interni broj“ i njihove
  istovrijednice na drugim jezicima sučelja sada se broje – dosad je
  program ondje prepoznavao samo engleske riječi.

- **Imena u numeriranoj tablici ostajala su netaknuta.** Popis sudionika
  ili tablica osoblja u uobičajenom obliku – zaglavlje stupca, ispod
  njega „1.1 Auersperg Bernhard Montaža 03.03.2026“ – uopće se nije
  čistio: takvi retci izgledali su kao popis pozicija ponude, u kojem
  stručni pojmovi trebaju ostati. Nosi li zaglavlje stupca oznaku osobe
  („Ime“, „Prezime“, „Surname“ …), retci ispod sada vrijede kao imena.
  Popisi pozicija i dalje su nepromijenjeno pošteđeni – i kad u
  zaglavlju pisma stoji „Obrađivač:“.

- **Iz jednog imena povremeno su nastajala dva rezervirana mjesta jedno
  uz drugo.** Stajalo li prezime i samo u dokumentu, naknadna je obrada
  na mjestu poput „Anna Musterfrau GmbH“ najprije zamjenjivala
  prezime, a zatim ime – u rezultatu je to izgledalo kao dvije
  različite osobe. Sada pobjeđuje najdulje poznato ime.

- **Izmišljene vrijednosti nisu stajale ni u kakvom pridruživanju.** Tko
  je odabrao „Izmisli vrijednosti“, dobivao je rezultat u kojem je
  „Anna Musterfrau“ postala „Greta Mayrhofer“ – u pridruživanju o tome
  nije stajalo ništa, čim se u istom dokumentu pojavila i samo jedna
  anonimna zamjena. Time se nijedna izmišljena vrijednost nije mogla
  vratiti, a datoteka pridruživanja prešućivala je zamjenu. Najosjetljivije
  je bilo treće: tko čita rezultat, vidi uvjerljivo ime i nema nikakav
  znak da je izmišljeno. Sada svaka zamjena stoji u pridruživanju.

- **Pridruživanje je zacrnjeno zvalo „zamijenjeno“.** E-pošta dijeli
  pridruživanje sa svojim privitcima, a privitak smije biti zacrnjen
  dok tekst poruke nosi rezervirano mjesto. U pridruživanju je za sva
  tri mjesta stajalo isto – „zamijenjeno“ – a vraćanje je u privitku
  tražilo rezervirano mjesto kojeg ondje nema: traka je ostajala.
  Sada po mjestu nalaza stoji što se ondje stvarno dogodilo, a oba
  privitka se vraćaju.

- **Vrijednosti koje su stajale samo na slici nisu se mogle vratiti.**
  U ploči nalaza stajale su dvostruko – jednom kao rezervirano mjesto
  koje nigdje u dokumentu nije postojalo („Rezervirano mjesto nije
  pronađeno u dokumentu“), jednom kao zacrnjeno mjesto. Prvi redak
  bio je čisto knjigovodstvo i nestao je.

- **Zacrnjene vrijednosti mogle su se vratiti samo jednom.** Stoji li
  ista vrijednost na više mjesta, klik ih vraća sve – preostali retci
  ipak su ostajali u ploči nalaza, a sljedeći klik na njih javljao je
  „Nije jednoznačno“. Sada nestaju zajedno.

- **Vraćanja su nedostajala u zapisniku provjere kad je način učenja bio
  isključen.** Tko je u prozoru uređivača obnovio vraćenu vrijednost,
  postupak nije nalazio u zapisniku provjere čim su pitanja učenja
  bila isključena – dokaz je ovisio o prekidaču koji vrijedi samo za
  prijedloge pravila. Uz uključen zapisnik provjere sada se neovisno
  o tome pita za razlog i piše redak.

- **Uvučene datoteke ostajale su neočišćene – i nisu se ni javljale.**
  Tko datoteku povuče u dokument umjesto da je pošalje kao privitak,
  Word ili PowerPoint je u cijelosti odlaže unutar dokumenta. Ona je
  potom nepromijenjena ostajala u rezultatu, zajedno sa svojim izvornim
  nazivom i putanjom – a oni u praksi često sami nose ime. Takve se
  datoteke sada čiste kao i ostatak dokumenta.

- **A gdje to ne ide, Maskuro to kaže.** Ima li ugrađeni objekt stari
  format (Word 97, Excel 97) za koji ne postoji čišćenje, sada se
  pojavljuje poruka POZOR s nazivom datoteke. Dosad se tiho
  prosljeđivala nepromijenjena.

- **Rastrgane riječi i kratice smatrane su imenima.** Rastavi li se
  riječ u PDF-u na kraju retka, pri čitanju nekih datoteka izlazi
  ulomak – „Jahresent… gelts“, „Gewerbli…“. Takvi ulomci, zalijepljene
  riječi („TürverschlussmitV“) i gole kratice („JY“, „FFB“) bili su
  zacrnjivani kao da su imena. Sada ostaju netaknuti. Ime s istom
  štetom od rastavljanja i dalje se zacrnjuje, dok uz njega stoji
  oslovljavanje – a imena koja izvorno nose veliko slovo usred riječi
  (McKenzie, MacDonald, LeBlanc) time ionako nisu zahvaćena.

- **Mjerne jedinice i mjeseci smatrani su adresom.** U tehničkoj
  dokumentaciji zacrnjivani su „2000 Lux“, „1200 Mbit“, „1500 Watt“,
  „5308 Platz“ i „2022 Mrz“ – četiri znamenke i riječ velikim slovom
  izgledali su kao poštanski broj s mjestom. Poštanski broj sada
  vrijedi samo uz dodatan znak adrese: oznaku zemlje, oznaku polja,
  početak retka, ulicu u retku iznad ili mjesto koje ondje vidi i
  prepoznavanje jezika. U pet troškovnika time nestaje 14 pogrešnih
  zacrnjenja, bez da ijedna stvarna adresa ostane.

- **Preciznije prepoznavanje zamjenjivalo je previše.** Uključiva razina
  „preciznije prepoznavanje“ u njemačkim poslovnim dokumentima
  smatrala je stručne pojmove imenima i mjestima – „Photovoltaikanlage“,
  „Einspeisepunkt“, „Flachdach“, „Personaleingang“ – i zacrnjivala
  nazive tvrtki iz tekućih popisa pozicija. Razlog je bila zaštita:
  njezini nalazi bili su izuzeti iz provjera koje prepoznaju redak
  pozicije ili popisa. Ta zaštita sada vrijedi samo za višedijelna
  imena, za koja razina i postoji – „Anna Huber“ u retku popisa dakle
  ostaje prepoznata, pojedinačna stručna riječ u retku pozicije
  otpada. U tehničkom natječaju to prepolovljuje pogrešna zacrnjenja
  razine, bez da se izgubi ijedno ime.

- **Dijagrami su donosili svoje potpune izvorne podatke – neprovjerene.**
  Tko u Word ili PowerPoint umetne grafikon, program tablicu iz koje
  je izračunat odlaže kao vlastitu datoteku u dokument. Vidljivo je
  time samo nekoliko brojeva u grafikonu; u tablici stoji cijeli popis,
  uključujući retke koji se u grafikonu uopće ne pojavljuju. Ta se
  tablica dosad prosljeđivala nepromijenjena. Sada se čisti zajedno,
  istim rezerviranim mjestima kao ostatak dokumenta.

- **Isto za ugrađene objekte u OpenDocument datotekama** (ODT, ODS,
  ODP): umetnuti grafikon ili umetnuta tablica ostajali su netaknuti.

- **Word dokumenti: fusnote i bilješke uz tekst nisu se čistile.**
  Njihov tekst ostajao je u potpunosti u rezultatu – i imena, adrese i
  brojevi računa. Zahvaćen je bio svaki Word dokument s fusnotom ili
  bilješkom uz tekst. Jednako je netaknut ostajao i element automatskog
  teksta koji nevidljivo putuje s dokumentom.

- **Word: podaci u padajućim popisima, komentarima i opisima slika.**
  Unosi padajućeg polja (vidljivi tek pri otvaranju), autor komentara,
  opis crteža i adresa iza naredbe poveznice ostajali su i dalje u
  rezultatu.

- **Excel: zaokretna tablica nosila je izvorne podatke po drugi put.**
  Radna knjiga sa zaokretnom tablicom u sebi čuva potpunu kopiju
  obrađenih redaka – nevidljivo, ali u datoteci. Ta je kopija dosad
  ostajala nepromijenjena, čak i kad je u samom listu sve bilo
  zamijenjeno. Zahvaćena je bila svaka obrada proslijeđena sa
  zaokretnom tablicom.

- **Excel: komentari razgovora i njihovi autori.** Tekst komentara
  novijeg oblika i popis komentatora – prikazano ime i prijavna oznaka,
  u tvrtkama najčešće adresa e-pošte – ostajali su i dalje u rezultatu.
  Isti popis u Word dokumentima jednako.

- **Vlastito definirana svojstva dokumenta u Wordu i Excelu.** Polja
  poput „Klijent“ ili „Broj predmeta“, koja odvjetnički ured pridaje
  svojim predlošcima, dosad se nisu čistila. Nisu vidljiva ni u jednom
  prikazu, a ipak putuju sa svakom kopijom.

- **Tablice (ODS): padajući popis stanice.** Kao u Excelu od prethodne
  inačice, sada se čisti i u OpenDocument tablicama ono što se
  pojavljuje pri otvaranju stanice. Upute na druge stanice pritom
  ostaju netaknute, kako bi popis i dalje radio.

Sva se ta mjesta kao i dosad mogu vratiti preko pridruživanja.

- **Outlook poruke: oštećena datoteka je čišćenje prekidala.** Određene
  pokvarene `.msg` datoteke uzrokovale su prekid umjesto poruke; sada
  se čitaju u onoj mjeri u kojoj su čitljive.

- **Datoteka pridruživanja sada je čitljiva samo vama.** Sadrži izvorne
  podatke u čitljivom obliku i dosad je s uobičajenim pravima ležala uz
  rezultat – na zajedničkom spremištu mogao ju je otvoriti bilo tko. Na
  samom očišćenom rezultatu se ništa ne mijenja; on se ionako treba
  proslijediti.

- **Naknadno učitani jezični modeli sada se preciznije provjeravaju
  prije raspakiravanja.** Manipuliran paket – primjerice s tvrtkine
  zajedničke mape s koje se opslužuje više radnih mjesta – pri
  raspakiravanju je mogao odložiti datoteke izvan predviđene mape. Na
  redovitom naknadnom učitavanju se ništa ne mijenja.

- **Snimi snimku zaslona – i odmah se čisti.** Preko `Ctrl+Shift+B`, iz
  „Datoteka → Snimi snimku zaslona …“ ili preko ikone u traci zadataka
  povlačite okvir preko zaslona. Ono što je unutra potom prolazi isti
  put kao svaka druga datoteka: prepoznavanje teksta čita tekst na
  zaslonu, imena, adrese, telefonski brojevi i adrese e-pošte se
  zacrnjuju, a zatim se slika otvara u uređivaču, gdje okvirom možete
  dodatno zacrniti što je previđeno. Očišćena slika završava na
  radnoj površini (ili u vašoj postavljenoj izlaznoj mapi); **sirova**
  snimka se nigdje ne odlaže i briše se pri izlazu. Prepoznavanje
  teksta uključuje se za to izvođenje, čak i kad je inače isključeno –
  na slici bi bez njega ionako ništa nije bilo pronaći. Na Macu sustav
  prvi put pita za dopuštenje „Snimanje zaslona“.

- **Po slikama se sada može i crtati: pravokutnik, elipsa, strelica,
  tekst i numerirane oznake koraka.** U šest boja i tri debljine crte,
  odabirljivo tipkama 1 do 5. Zamišljeno za snimke zaslona i upute:
  pokazati što je bitno, bez otvaranja drugog programa. Poništi i
  naknadno prilagođavanje ručkama vrijede kao za svaku traku – oznaka
  se dakle može pomicati i razvlačiti nakon što je postavljena.
  **Crtanje izričito nije zacrnjivanje.** Nacrtan pravokutnik je okvir,
  ne traka: ono što je ispod njega ostaje čitljivo i izlazi s
  datotekom. Za uklanjanje podataka i dalje postoje „Zacrni“ i
  „Pikseliziraj“; alati za crtanje zato stoje u vlastitom retku alatne
  trake, a napomenski redak to kaže dok je jedan od njih odabran.

- **Obrađena slika jednim klikom odlazi u međuspremnik.** „Kopiraj
  sliku“ u uređivaču (ili `Ctrl+C`) odlaže je onako kako stoji –
  lijepljenje je dovoljno da bi ušla u poruku ili e-poštu. Put od
  pritiska tipke do razgovora time je dug četiri koraka i ne treba
  mapu.

- **Uz to flomaster, sjena i prijelazi.** „Istakni“ boja površinu bez
  da je prekriva – sadržaj ispod ostaje čitljiv, i baš po tome se
  razlikuje od trake. „Sjena“ ističe oznaku od nemirne podloge,
  „Prijelaz“ boji da izblijedi u smjeru povlačenja; oboje vrijedi za
  svih šest alata crtanja.

- **Riješeno prije nego što je ikoga pogodilo:** novi redak alata gotovo
  bi kod svakoga tko je Maskuro već koristio bio prazan – zapamćen
  raspored prozora potjecao je iz vremena prije toga i ne bi mu ostavio
  mjesta. Zastarjeli raspored sada se odbacuje; prozor uređivača tada
  jednokratno stoji u svom osnovnom rasporedu.

- **Vlastita snimka zaslona se može isključiti.** Tko je navikao na
  Greenshot, ShareX ili alat za izrezivanje, isključuje pod „Postavke →
  Program“ „Snimi snimku zaslona Maskurom“. Maskuro tada uopće ne
  prijavljuje tipkovnu prečicu – ostaje vašem alatu – a promjena
  vrijedi odmah, bez ponovnog pokretanja. Tako snimljenu sliku i dalje
  je moguće čistiti: Ctrl+V je dovodi iz međuspremnika u prozor.

## 0.10.37-alpha.20260821 – 21. kolovoza 2026.

### Novo

- **Kod anonimiziranja svako mjesto nalaza sada nosi vlastiti broj.**
  Dosad su se sve osobe zvale `[NAME]`, sva mjesta `[ORT]` – time se
  više nije moglo reći koje mjesto pripada kojoj vrijednosti, i nije
  bilo što vraćati. Sada brojevi rastu po pojavljivanju: isto ime na tri
  mjesta stoji kao `[NAME_1]`, `[NAME_3]` i `[NAME_7]`. U dokumentu se
  time i dalje ne prepoznaje koja mjesta pripadaju zajedno – no
  datotekom pridruživanja svako se pojedinačno može vratiti. Datoteka
  pridruživanja zato je ponovno izborljiva i kod anonimiziranja;
  čuvajte je odvojeno od rezultata.
- **Mjeseci, dani u tjednu, valute, jedinice i pravni oblici tvrtki na
  svih 48 jezika dokumenta više se ne smatraju imenima ili mjestima.**
  Nazivi kalendara i jedinica dolaze iz Unicode CLDR-a (generirano, ne
  ručno pisano), pravni oblici iz trgovačkog prava zemalja – i
  višerječni („sp. z o.o.“, „Pty Ltd“) i prepostavljeni („株式会社“).
  Gdje je naziv mjeseca ujedno i osobno ime (Juli, August, May),
  odlučuje oblik: uz dan ili godinu pored to je datum, inače ime. Uz
  to oslovljavanja i titule, cijele pozdravne formule, vrste dokumenata
  i osnovne riječi ulica za 28 jezika s vlastitim jezičnim modelom,
  kratice zakona (GDPR, UStG, ABGB, § 6 st. 1 t. 27 UStG) te nazivi
  jezika kao vrijednost polja („Jezik: Njemački“). Popisi stoje pod
  „Pomoć → Popisi riječi …“.
- **Indija: adresa i PIN kod se prepoznaju** – „15 गांधी मार्ग“, „नई
  दिल्ली 110001“ jednako kao „15 Gandhi Marg, New Delhi 110001“.
  Paket zemlje Indija dosad je poznavao samo identifikacijske brojeve;
  u hindskim dokumentima adrese su zato ostajale netaknute.
- **Svaka očišćena Office datoteka prije predaje ponovno se otvara kao
  paket.** Tekstualni izvadak ne primjećuje kad bi Word, Excel ili
  LibreOffice odbili datoteku (dvostruk unos, rastrgan XML, dio koji
  nedostaje). A broji se prema izvorniku ono što čišćenje nikad ne
  smije promijeniti: stranice PDF-a, listovi, retci i stanice tablice,
  slajdovi prezentacije. Aktivira li se proba, u rezultatu i izvještaju
  provjere stoji upozorenje POZOR – izvornik ostaje nepromijenjen.
- **I automatika sada zacrnjuje cijelo polje.** U načinu zacrnjivanja
  traka u kratkim recima – blok adrese, stanica tablice, podaci
  zaglavlja – pokriva cijeli redak umjesto samo pronađenu vrijednost:
  traka duljine riječi odaje koliko je duga riječ bila. Oznaka i
  iznosi pored ostaju netaknuti, a retci tekućeg teksta (duži od
  polovice širine teksta) i dalje se zacrnjuju po riječima, kako ime
  usred rečenice ne bi pocrnilo cijelu rečenicu.
- **Vraćeno ponovno izgleda kao u izvorniku.** „Vrati izvornik“ i
  „Poništi zamjenu“ u PDF uređivaču sada područje zapisuju točno iz
  izvorne datoteke – isto pismo, ista veličina, ista boja i položaj, na
  skenu iste slikovne točke. Dosad se tekst nanovo umetao u zamjenskom
  pismu i vidljivo je izgledao nadograđeno. Traka ranijeg zacrnjenja
  pritom potpuno nestaje, umjesto da se premaže bijelo – obojena
  podloga stanice u tablici ostaje sačuvana. To vrijedi i na
  zaokrenutim stranicama, za tekst iz ugrađenih objekata obrasca i za
  **ispunjena polja obrazaca**: na za to rasteriziranoj radnoj kopiji
  izrezak dolazi iz nanovo iscrtane izvorne stranice – i ondje gdje
  nijedan tekstualni sloj ne poznaje vrijednost polja. I **zamijenjene
  slike** u PDF-u tako se vraćaju – pikselizirane, zamućene ili
  potpuno uklonjene, u cijelosti ili samo povučeni izrezak. Samo gdje
  izvorna datoteka više ne leži uz rezultat, ostaje pri dosadašnjem
  putu.
- **Zacrnjene i bez zamjene uklonjene vrijednosti mogu se vratiti i u
  Wordu, Excelu, PowerPointu i OpenDocumentu.** Dosad je vraćanje ondje
  trebalo rezervirano mjesto u tekstu – traka ili praznina nisu imale
  put natrag. Sada ploča nalaza nudi retke „zacrnjeno“ i „uklonjeno“
  čim izvorna netaknuta datoteka leži uz rezultat: Maskuro uspoređuje
  rezultat s izvornikom i vraća vrijednost na mjesto trake ili
  praznine – zajedno s oblikovanjem, rastavljen niz ponovno postaje
  cjelina. Vrijedi jednako za tekst, HTML, e-poštu i Office privitke
  e-pošte; nosi li tekst poruke rezervirano mjesto, a privitak traku,
  oba se vraćaju u jednom potezu.
- **I PDF privitci e-pošte ili Outlook poruke mogu se vratiti** –
  rezervirana mjesta (brojčana i anonimna), trake i bez zamjene
  uklonjeno. Bez platna mjesto dolazi iz izvornog privitka; vraća se
  vrijednost glif po glif, u redoslijedu čitanja izvornika.
- **Maskirane vrijednosti se mogu vratiti** – u PDF-u i u prikazu
  teksta. Maska („**** **** **** **** 3201“) nikad nije jednoznačna,
  dva broja nose istu; zato vraćanje nikad ne ide doslovnim putem, nego
  pita izvornik koja je vrijednost stajala na tom mjestu. Dosad se ti
  retci u ploči nalaza uopće nisu mogli koristiti.
- **Ugrađene slike u Wordu, Excelu, PowerPointu i OpenDocumentu mogu se
  vratiti.** Vrijednost zacrnjena u slici vraća se preko svog retka u
  ploči – Maskuro čita izvornu sliku i dohvaća baš to mjesto; zamućenu,
  uklonjenu ili obrađenu lica i kodova sliku novi unos „Vrati ugrađene
  slike“ u izborniku Uređivanje dohvaća u cijelosti iz izvorne
  datoteke – i kroz Office privitke e-pošte ili Outlook poruke. Slika
  koja sama visi kao privitak i bila je zacrnjena prepoznavanjem
  teksta, jednako se vraća preko svog retka u ploči.
- **Izmišljene vrijednosti mogu se vratiti u prikazu teksta.** Dosad je
  ploča ondje javljala „Nije jednoznačno“. Sada vraćanje traži
  vrijednost u izvorniku i na istom mjestu u rezultatu zahtijeva točno
  izmišljenu zamjenu – izmišljeno ime se nikad ne zamjenjuje doslovno
  posvuda, moglo bi negdje stvarno stajati.
- **Vraćanje u Wordu, Excelu, PowerPointu i OpenDocumentu zadržava
  oblikovanje izvornika.** Je li vrijednost stajala preko više
  segmenata – „Anna“ obično, „Musterfrau“ podebljano i crveno –, dosad
  se u cijelosti vraćala u prvi segment i gubila podebljano i boju.
  Sada se znakovi ponovno raspodjeljuju kao u izvorniku; Word odlomak
  nakon toga je bajt po bajt izvoran. Isto vrijedi za HTML stranice,
  HTML dio e-pošte i HTML tijelo Outlook poruke (.msg) – kod e-pošte uz
  to ostaje sačuvan doctype koji je čišćenje dosad tiho uklanjalo.
- **Tekstualne datoteke zadržavaju svoje kodiranje.** Čišćenje i
  vraćanje sada `.txt`, `.md` i `.csv` zapisuju u kodiranju u kojem su
  isporučene – UTF-8 s BOM-om i bez njega, UTF-16, Windows-1252. Dosad
  je Windows-1252 datoteka uvijek postajala UTF-8, a UTF-16 datoteka
  vraćala se oštećena, čak i kad u njoj nije bilo ništa za zamijeniti.
- **Vraćene slike zadržavaju svoj način boje.** Sken u sivim tonovima
  vraća se kao sivi tonovi umjesto tri puta veće RGB datoteke, paleta
  kao paleta, crno-bijelo kao crno-bijelo – kod cijele slike s istim
  vrijednostima kao u izvorniku. Vrijedi za slikovne datoteke i slike u
  PDF-ovima. CMYK i 16-bitno ostaju RGB, jer PNG rezultat oboje ne može
  nositi.
- **Okvir na slici vraća cijelu obradu koju dotiče.** Pikselizirana
  lica nose rub oko prepoznatog okvira; tko je povukao okvir samo
  preko lica, zadržao je pikselizirani prsten. Sada okvir raste na
  cjelovitu promjenu prema izvorniku – dovoljan je okvir preko područja
  očiju. Odvojene trake pored ostaju stajati; kod potpuno uklonjene ili
  potpuno zamućene fotografije i dalje vrijedi povučeni okvir. Vrijedi
  za slikovne datoteke i slike u PDF-ovima.
- **Trake zacrnjenja preko cijelog retka.** U retkovnom načinu
  uređivača traka sada ide od prve do posljednje riječi retka, ne više
  samo preko pogođene riječi – traka duljine riječi odaje koliko je
  riječ bila duga, a iz šest znakova ispred poštanskog broja može se
  pogoditi naziv mjesta. Oznake, iznosi i stupci tablice pored
  vrijednosti ostaju netaknuti – traka pokriva polje, ne redak računa.
  Novi prekidač „Cijeli redak“ uz „Retci teksta“ ponovno prebacuje na
  točno po riječima, kad susjedne riječi trebaju ostati; izbor se
  pamti.

### Riješeno

- **Slike na HTML stranicama i u e-pošti ostajale su neprovjerene – ime
  u logotipu nakon čišćenja ostajalo je čitljivo.** Slika ugrađena u
  stranicu (`data:` adresa) uopće se nije dirala, samo njezin
  alternativni tekst; logotip u HTML grani poruke (umetnuta slika bez
  naziva datoteke) prolazio je kroz filtar privitaka; a kod imenovanog
  slikovnog privitka pravilo slike „zamuti“/“ukloni“ ostajalo je bez
  učinka. Sada sva tri idu istim putem kao slikovna datoteka:
  prepoznavanje teksta u sačuvanoj slici, lica, kodovi, metapodaci i
  pravilo slike. Izvještaj navodi slike – i upozorenje ako ostaju
  neprovjerene bez prepoznavanja teksta – a „Vrati ugrađene slike“ te
  vraćanje iz ploče nalaza također poznaju te slike.
- **Office datoteka sa slikom nije se mogla ni čistiti ako
  prepoznavanje teksta ne vlada jezikom.** Na Macu čita sistemsko
  prepoznavanje teksta; za hindski, grčki, hrvatski ili litavski to ne
  može i to od nedavno i kaže – kod Worda, Excela, PowerPointa i
  OpenDocumenta zbog toga se prekidalo **cijelo** čišćenje, i nije
  nastajala nijedna datoteka. Pritom se tekst mogao besprijekorno
  čistiti; samo slika nije bila čitljiva. Sada se datoteka piše kao kod
  PDF-a i pojedinačnih slika, a u rezultatu stoji da slike NISU
  provjerene – s razlogom i uputom na „Upravljanje jezicima“.
- **U Excel radnim knjigama imena su ostajala u padajućim popisima.**
  Popis padajućeg polja (provjera valjanosti podataka) sada se čisti
  kao i svaki drugi sadržaj stanice; upute na raspone stanica ostaju
  netaknute, kako bi radna knjiga ostala ispravna.
- **Gdje rezervirano mjesto nije stalo, stajala je crna traka – sada
  ondje stoji kraći zapis.** `[GEBU_1]` umjesto `[GEBURTSDATUM_1]`, i
  tek kad ni najkraći oblik ne stane, zacrnjuje se. Traka nikome više
  ne kaže da je ondje nešto stajalo; kratko rezervirano mjesto to
  kaže. Uređivač za doradu to je već mogao, automatsko čišćenje dosad
  nije. Datoteka pridruživanja vodi oba zapisa na istu vrijednost, kako
  bi se i skraćeno moglo vratiti.
- **Prvi klik na „Zamijeni“ kratko je zadržavao prozor uređivača.**
  Prepoznavanje koje rezerviranom mjestu daje njegovu vrstu (`[NAME_3]`
  umjesto `[BEGRIFF_3]`) učitavalo se tek u tom trenutku – oko dvije do
  tri sekunde. Sada se priprema u pozadini pri otvaranju prozora;
  izmjereno, od 2289 milisekunda nastalo je 193.
- **Dva istodobna čišćenja mogla su isti jezični model učitati
  dvostruko** – primjerice nadzor mape i glavni prozor. Jer svaki model
  zauzima nekoliko stotina megabajta, potreba za memorijom kratkotrajno
  je time bila dvostruka. Sada drugo izvođenje čeka model prvog.
- **Mjesto u retku datuma sada se uklanja i kad ga jezični model sam ne
  prepoznaje:** ono što je sigurno pronađeno kao poštanski broj s
  mjestom („3335 Amstetten“) povlači svoj naziv mjesta kroz cijeli
  dokument – kao prezime iz punog imena. A kratica sa znamenkom ispred
  imena („T3 Hofbauer Christian“) ostaje čitljiva, umjesto da nestane s
  rezerviranim mjestom.
- **Zatvorena tri propusta iz drugog čitanja stvarnog naloga:**
  obrađivač „T3 Hofbauer Christian“ zbog kratice „T3“ smatran je
  zaglavljem stupca i ostajao čitljiv; mjesto koje je jezični model
  preko prijeloma retka pročitao u zaglavlje stupca gutalo je „Pos.“ i
  ostavljalo klijentovo ime; a ime zajedno s oslovljavanjem
  („Herr Robert Köttel“) povlačilo je samo prezime, ne i ime – a zato
  svako „Herr“. Kratice su sada čisto slova, dvoriječna imena više nisu
  zaglavlje, nalazi se odsijecaju ispred zaglavlja stupca, a
  oslovljavanje se ne broji kao dio imena.
- **Mjesto u retku datuma („Melk, 05.08.2026“) izravno ispod bloka
  adrese ostajalo je čitljivo.** Jezični model lijepio ga je s mjestom
  retka poštanskog broja u jedan nalaz, a taj je u cijelosti otpadao
  protiv uzorka poštanskog broja. Sada isturen ostatak ostaje vlastiti
  nalaz. Pronađeno novim drugim čitanjem rezultata
  (`werkzeuge/zweitlesung.py`).
- **Mac: sken na jeziku koji sistemsko prepoznavanje teksta ne vlada
  (npr. hindski, grčki, hrvatski, litavski) vrijedio je kao
  provjeren.** Čitalo se engleskim rezervnim putem, strano pismo
  ostajalo je na slici, a izvještaj je govorio „ništa pronađeno“. Sada
  stoji „slika(e) NISU provjerene“ s razlogom, a upravljanje jezicima
  za takve jezike više ne obećava prepoznavanje teksta samo zato što
  postoji Tesseract jezična datoteka.
- **U PDF-u interpunkcijski znak iza zamijenjene vrijednosti sada
  ostaje sačuvan.** Iz „Prijem 01.03.2026, otpust 04.03.2026.“ dosad je
  nastajalo „Prijem [DATUM_1] otpust [DATUM_2]“ – zarez i završna
  točka nedostajali su, kod rezerviranih mjesta jednako kao kod
  pomaknutih datuma. Sada se uklanja samo prepoznata vrijednost, ne
  cijela riječ do sljedećeg razmaka; zarez, točka-zarez, točka ili
  zagrada iza ostaju na svom mjestu, a rezervirano mjesto ne prelazi
  preko njih.
- **Ruski i ukrajinski su neopaženo radili sa slabijim višejezičnim
  modelom**, nedostajao li pomoćni paket za analizu oblika riječi
  (`pymorphy3`) – vlastiti modeli tada se nisu mogli učitati, a
  „Львів“ je postajao osoba. Za prepoznavanje imena analiza oblika
  riječi nije potrebna; model se sada učitava bez nje, a mjesta su
  ponovno mjesta.
- **Licencne napomene na 16 jezika bile su na starom stanju.** Ondje je
  još stajalo da se MPL izvorni kod pruža „na zahtjev“, QPDF je
  vrijedio kao MPL-2.0, sedam gradivnih elemenata nedostajalo je u
  tablici (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp,
  YuNet), spaCy odlomak bio je engleski, a na kraju je visio engleski
  zamjenski odjeljak. Sada svih 18 inačica stoji na stanju njemačke:
  izvorni arhivi trajno pod maskuro.com/quellcode/oss/, QPDF Apache-2.0,
  Qt-LGPL put, podrijetlo modela. I engleska tablica ima retke koji su
  nedostajali.

- **Ugovorne riječi u genitivu („des Angebotsinhaltes“, „des Anbotes“,
  „des Terminplanes“) više se ne smatraju mjestom.** Pojedinačna riječ
  iza genitivnog ili dativnog člana s nastavkom sklonidbe je opća
  imenica – nazivi mjesta ne sklanjaju se („nach Graz“). Stoji li
  mjesto negdje drugdje u dokumentu bez člana („Burgenland“), ostaje
  prepoznato i „des Burgenlandes“.
- **Pomaknute, maskirane i izmišljene vrijednosti rasterizirale su PDF
  stranicu.** Naknadna provjera nakon uklanjanja dopuštala je u
  pravokutniku nalaza samo rezervirano mjesto u uglatim zagradama;
  pomaknut datum („01.07.2026“) ili maskirana vrijednost („****1234“)
  vrijedili su kao previđen ostatak, i stranica se opreza radi
  pretvarala u sliku – kod „Zamijeni“ ne. Sada takve stranice ostaju
  tekst, a vraćanje iz ploče ili okvira ponovno daje izvornik.
- **Zamjenske vrijednosti od više riječi nisu se u PDF-u mogle vratiti
  preko ploče nalaza.** Izmišljeno ime („Greta Mayrhofer“) ili
  maskiran IBAN („**** **** **** **** 3201“) sastoji se od više
  riječi; pretraga mjesta nalaza uspoređivala je riječ po riječ i
  javljala „Rezervirano mjesto nije pronađeno u dokumentu“. Sada se
  uzastopne riječi istog retka čitaju zajedno.
- **Nakon vraćanja bez zamjene uklonjene vrijednosti njezin redak u
  ploči ostajao je stajati.** Vrijednosti koje strategija „zacrni“ u
  načinu rezerviranog mjesta uklanja bez zamjene nemaju rezervirano
  mjesto na kojem bi ploča mogla izmjeriti nestanak. Sada se redak
  briše čim je vrijednost ponovno u dokumentu.

- **Kratice sastavljenice poput „E-Helfer“ ili „U-Bahn“ više se ne
  smatraju imenom.**
- **Ostaci rastavljanja slogova („Leis-“) i predugačke složenice
  („Bauarbeitenkoordinationsgesetzes“, „Baustellenkoordinator“) više se
  ne smatraju imenom ili mjestom.** U skeniranom tekstu natječaja time
  je 28 riječi manje zacrnjeno.
- **Popisi pozicija skeniranih ponuda više se ne smatraju popisom
  imena.** Dodatni prolaz za popise (kratki retci) od „Kälterohr“ i
  „Außengeräte“ pravio je osobe; sada izostavlja čim brojevi pozicija
  poput „1.1.5“ stoje na početku retka. Retci datuma u nizovima poruka
  pritom se ne broje kao brojevi pozicija.
- **Zaglavlja stupaca i brojevi pozicija skeniranih ponuda („Pos.“,
  „Pos. 1.1.3“, kratice „E/L/S“) smatrali su se imenom ili mjestom.**
  Kratica sama na svom retku, oznaka zajedno s brojem i pojedinačna
  slova redak po redak to nisu.
- **Stranica je „disala“ u prozoru uređivača nakon otvaranja povećala
  za usporedbu** – kod „Širina stranice“ i „Uklopi“ mjerilo ovisi o
  vidljivom prozoru, a to se mijenja sa svakom trakom pomicanja koja
  dolazi ili odlazi; svaka sljedeća radnja pomicala je stranicu za
  komadić. Platno to sada samo dovlači dok se ne smiri. A gumbi zuma,
  klizač i tipkovne prečice zadržavaju sredinu slike i kad se pri
  uvećavanju pojavi traka pomicanja.
- **Poprečno spremljeni skenovi sada se čitaju uspravno, a sitan tisak
  na velikim skenovima više se ne gubi.** 24-stranična skenirana
  ponuda u svakom podnožju zadržavala je šest bankovnih IBAN-a, broj
  trgovačkog registra i UID čitljivim: sken je u PDF-u ležao zaokrenut
  za 90°, a prepoznavanje teksta kod vrlo velikih slika ovisno o
  dimenzijama izostavljalo je cijele retke. Sada se uzima u obzir
  vidljivi zaokret, a velike se slike čitaju u preklapajućim vrpcama –
  podnožja su crna.
- **Ulice po osobama s crticom ispred osnovne riječi („Josef
  Admanseder-Straße 7“, „Abt-Karl-Straße 8“, „Dr.-Karl-Renner-Straße
  12“) prepoznaju se kao adresa.** U zaglavlju pisma skenirane ponude
  takva je adresa ostajala čitljiva jer je uzorak zahtijevao razmak
  ispred „Straße“.
- **IBAN-ovi iz prepoznavanja teksta koji nose O umjesto 0 ili l
  umjesto 1 sada se prepoznaju.** U sitnom tisku skena prepoznavanje
  teksta rado čita znamenke kao slova; broj je tada imao oblik IBAN-a,
  ali kontrolna suma nije odgovarala, i broj je ostajao. Ne uspije li
  kontrolna suma, sada se proba čitanje sa znamenkama – odgovara li
  tada, to je IBAN. Pogrešne kontrolne znamenke ostaju pogrešne.
- **Ulomci rečenice poput „folgenden Codes auf der“ smatrani su
  mjestom.** Ime ili mjesto koje počinje malim slovom to nije – osim
  kod plemićkih čestica („van Gogh“, „de Vries“).
- **U uređivaču je uz traku zacrnjenja ostajalo posljednje slovo**
  („…6“, „…t“, „…g“), a traka je imala visinu povučenog okvira umjesto
  retka. Uzrok: nije li uređivač mogao izmjeriti stranicu, svaki je
  okvir smatrao „nijedna riječ nije pogođena“ i primjenjivao ga
  točno – bez pravila da polovica riječi nikad ne ostaje. Isto se
  događalo kod pojedinačnih tekstualnih naredbi koje uređivač nije
  mogao smjestiti. Sada uvijek uz to broji okvir riječi: ono što okvir
  bitno preklapa, u cijelosti otpada.
- **Posljednje slovo riječi izlazilo je izvan trake zacrnjenja.** Traka
  je mjerena prema širini pomaka iz metrike pisma; crta li pismo glif
  širi, ostatak je stajao pored trake. Okvir znaka sada obuhvaća i
  nacrtani glif.
- **Poruka o pretvaranju stranice u sliku obećavala je previše.**
  „Prikaz ostaje isti“ nakon rasteriziranja ne vrijedi: pismo i grafika
  tada su slikovne točke, datoteka postaje veća. Poruka to sada kaže –
  i navodi i drugi razlog rasteriziranja (izgradnja bi oštetila
  stranicu).
- **Tekst iza uklonjene vrijednosti pomicao se do jedne točke
  ulijevo.** Pri preslagivanju retka početak se mjerio prema rubu
  glifa, nastavak prema ishodištu pera – pomak prve slova ostajao je
  kao pogreška („C“ 0,5 pt, „I“ 1,0 pt). Sada preslagivanje dosljedno
  računa s ishodištem pera; nastavak stoji na desetinku točke na svom
  mjestu.
- **Austrijski UID s razmacima („ATU 187 35901“) i broj trgovačkog
  registra bez „FN“ ispod svoje oznake („Firmenbuchnummer: 30799v“)
  prepoznaju se.** Oboje je rukom pisano stajalo na skeniranom obrascu
  natječaja i ostajalo čitljivo, iako je prepoznavanje teksta to
  ispravno pročitalo.
- **Poprečno položene PDF stranice bez razloga su pretvarane u
  sliku.** Provjera cjelovitosti uspoređivala je izvornik i rezultat u
  zaokrenutom prikazu, ali svoje zone zacrnjenja računala je
  nezaokrenuto – na stranici s napomenom zaokreta vlastito je
  zacrnjenje zato ležalo pored svoje zone i vrijedilo kao šteta. Takve
  stranice sada zadržavaju svoj tekstualni sloj i vektorsku grafiku.
- **I ravne stranice povremeno su nepotrebno pretvarane u sliku**, kad
  se tekst iza rezerviranog mjesta pomaknuo za jednu točku – dopušteno,
  ali usporedba slika bila je finija od vlastite tolerancije. Sada
  uspoređuje u polutočkama i time točno pogađa svoju toleranciju: do
  dva boda pomaka ništa ne pokreće, iznad toga sve.
- **Podaci u ugrađenim objektima obrasca ostajali su netaknuti.** Neki
  predlošci polažu zaglavlje ili završetak pisma kao vlastiti obrazac
  koji stranica samo uključuje. Nalaz u njemu bio je planiran i brojan
  kao uklonjen, ali se nikad nije zapisivao – tekst je ostajao stajati,
  a hvatalo ga je samo rasteriziranje cijele stranice. Sada se sam
  obrazac prepisuje; obrazac koji leži na više stranica, samo jednom.
- **PDF stranice su se rasterizirale u sliku, iako ništa nije ostajalo
  čitljivo.** Sedmostraničnu ponudu to je pogodilo na šest stranica;
  narasla je sa 73 kB na 3,3 MB i izgubila svoje pismo u slikovni
  prikaz. Uzrok su bili razmaci koji u dokumentu stoje višestruko
  jedan za drugim, a čitač ih javlja samo jednom: tekst iza uklonjenog
  podatka pomicao se udesno za njegovu širinu, naknadna je provjera
  pronalazila susjednu riječ u pravokutniku nalaza i posezala za
  rasteriziranjem. Sačuvani ostaci retka sada ponovno stoje točno na
  svom mjestu; ista se ponuda čisti bez ijedne rasterizirane stranice
  (76 kB).
- **Nazivi ključeva i zaglavlja računa smatrani su osobama.** U
  pristupnoj datoteci naziv varijable okruženja („AWS_ACCESS_KEY_ID“)
  bio je zamijenjen, ne samo njezina vrijednost; na engleskom računu
  naslov „Bill to“ otpadao je kao ime. Identifikator velikim slovima s
  podcrtama nikad nije ime, kao ni riječ u retku koji je u cjelini
  oznaka polja – primatelj ispod i dalje se pronalazi.
- **Pretraga u prozoru uređivača zapinjala je kod velikih PDF
  stranica.** Svako slovo u polju pretrage nanovo je rasteriziralo
  stranicu, iako se mijenjalo samo isticanje. Iscrtana slika stranice
  sada ostaje ista dok su stranica, zum i prikaz isti – jednako i
  izvornik u povećalu za usporedbu; listanje, zumiranje i novo stanje
  datoteke i dalje se crtaju iznova.
- **Brojevi pozicija u ponudama smatrani su IP adresom ili telefonskim
  brojem.** Redak artikla poput „1.3.3.4 … 5-Port Gigabit Switch“ činio
  je broj strukture mrežnom adresom, jer se „Port“ brojao kao tehničko
  okruženje – sada se broji samo kao samostalan podatak („Port 80“),
  ne kao dio riječi. A „1.3.3.6 216879“ (broj pozicije plus broj
  artikla) više se ne zacrnjuje kao telefonski broj. Stvarne IP adrese
  i telefonski brojevi u takvim popisima ostaju prepoznati.
- **Retci artikala u ponudama smatrani su poštanskim brojem s
  mjestom.** „35252 DIETZEL SALR“ (broj artikla s proizvođačem) i
  „1000 AWG“ (količina s presjekom vodiča) u numeriranim recima
  pozicija bili su zacrnjeni kao adresa, jer je riječ velikim slovima
  iza broja vrijedila kao naziv mjesta u verzalu. U popisima pozicija
  to više ne vrijedi; „1080 WIEN“ u bloku adrese i mjesta malim slovima
  posvuda ostaju prepoznati.
- **Dodatno prepoznavanje imena zacrnjivalo je u ponudama retke uloga i
  zaglavlja stupaca.** „Partiestundensatz Monteur + E-Helfer“ 49 puta
  je vrijedio kao osoba, zaglavlje stupca „Pos. Bezeichnung Menge EH“
  19 puta kao mjesto – time je 19-stranični nalog postao nečitljiv.
  Takvi nalazi u recima pozicija sada otpadaju ako sami nose znakove
  koje nijedno ime nema (plus, kosa crta, znamenka, kratica) – i kad
  redak završava iznosom („Alternativ Markt … - PV/LS AC-Versorgung 1
  290,00“). Imena u imenicima i popisima – čemu ta razina služi –
  ostaju netaknuta.
- **„Der Kunde“ u općim uvjetima činio je svaku riječ „Kunde“ imenom.**
  Uzme li dodatno prepoznavanje imena član u nalaz, on je vrijedio kao
  dvodijelno ime i štitio svih 35 daljnjih mjesta iste riječi. Sada se
  član odbija, a „der Kunde“ otpada kao i dosad već „des Kunden“.
- **Oznake su se smatrale vrijednošću.** „E-Mail“ bilo je sedam puta
  zacrnjeno kao adresa e-pošte, „Telefonnummer“ i „Faxnummer“ kao
  telefonski broj. Adresa bez @ i telefonski broj bez znamenki više se
  ne broje.
- **Kratice stupaca od jednog slova („L: 154,50“, „S: 0,00“) smatrane
  su imenom** – 25 puta u fotonaponskoj ponudi. Pojedinačno slovo nije
  ni ime ni mjesto.
- **PDF stranice pretvarane su u sliku daleko prečesto.** Dva uzroka,
  oba pronađena u stvarnim ponudama: postavlja li PDF svaki glif kao
  vlastitu naredbu i pod njim leži razmak-glif bez tekstualnog znaka,
  pridruživanje se od te točke pomicalo za jedan – od uklonjene
  vrijednosti ostajalo je posljednje slovo („ŠkodaTopCar**d**“), a
  naknadna je provjera stranicu opravdano rasterizirala. A na kraju
  retka rastavljena riječ („Datenschutz-“) zbog oznake crtice za
  rastavljanje knjižnice za čitanje vrijedila je kao pomaknuta. Oboje
  riješeno: ponuda vozila pala je s 4 rasterizirane stranice na 0,
  19-stranični nalog sa 7 na 0 – pismo ostaje pismo, datoteka ostaje
  mala.
- **Otklonjena još dva razloga rasteriziranja:** donese li dokument sam
  pismo naziva „F1“, rezervirana mjesta iznad slika postavljala su se
  u tom pismu i bila nečitljiva – sada vlastito pismo oznaka dobiva
  slobodan naziv. A nedostaje li knjižnici za čitanje razmak usred
  duge tekstualne naredbe, mjesto se sada dokazuje i kod višebajtnih
  pisama (isti kod, isti znak) umjesto da se pogodi na kraju – prije je
  time ostajalo jedno slovo uklonjene vrijednosti, a preostali se tekst
  vidljivo pomicao u stranu. Uz to dva posljednja slučaja: naredba od
  desetaka razmaknih glifova puštala je pridruživanje da odbjegne
  (ime iza njega ostajalo je stajati), a velik naslov s pomakom nije
  pronalazio svoj prvi znak (naziv tvrtke ostajao je stajati). **Od
  devet stvarnih ponuda sada se više nijedna stranica ne
  rasterizira** – prije ih je bilo 30 od 90.
- **Pri rasteriziranju slike su nestajale ispod crnog bloka.** Mora li
  se stranica pretvoriti u sliku, iscrtava se iz izvornika – a to ne
  poznaje čišćenje slike. Dosad je zato *svaka* slikovna površina
  stranice padala pod traku, i netaknuta. Na jednoj ponudi adresa i
  dva certifikatska logotipa nalazili su se u istoj slici zaglavlja
  pisma; traka je odnijela i logotipe. Sada se umeće već očišćena
  slika: adresa u njoj je zacrnjena, sve ostalo ostaje vidljivo.
  Uklonjena slika ostavlja bijeli papir umjesto crnog kvadrata.

- **Očišćeni skenovi postajali su višestruko veći od izvornika.** Svaka
  slika u kojoj je nešto zacrnjeno vraćala se u datoteku kao
  nekomprimirana sirova slika – kod 24-stranične skenirane datoteke to
  ju je time povećavalo s 11,8 na 52,9 MB. Slike sada zadržavaju vrstu
  u kojoj su bile: fotografija ostaje fotografija, fax sken ostaje
  crno-bijeli, bezbojna slika ne odlaže se kao slika u boji. Ista
  datoteka sada je 15,6 MB, bez vidljive razlike.

- **Skenirani PDF-ovi iz uredskih uređaja vraćali su se kao uzorak
  pruga.** Takvi skenovi polažu pismo kao oštar crno-bijeli sloj preko
  grube slike u boji – Canon, Xerox i Kofax tako grade svoje datoteke.
  Kod zacrnjivanja u slici taj se sloj pogrešno zapisivao natrag;
  rezultat je bio nečitljiv. Kod šesterostranične ponude to je pogodilo
  devet od šesnaest slika. Sada se obrađuje ispravno, u vlastitoj boji,
  a zacrnjena mjesta u njoj su uistinu nestala.

- **„Ukloni sve slike“ oduzimalo je skeniranoj stranici njezin tekst.**
  Sloj pisma takvog skena tehnički je slika – uklanjao se odnosno
  zamućivao zajedno s ostalim, a ostajao je prazan list. Sada ostaje
  netaknut; logotipi, pečati i potpisi i dalje odlaze.

- **Provjera oštećenih PDF stranica više se ne rasterizira zbog
  sitnog pomaka.** Tekstualni ulomak novo usidren pri čišćenju smije se
  pomaknuti do dva boda; usporedba slika to je unatoč tome brojala kao
  štetu i stranicu iznova gradila kao slikovni prikaz – time su
  nestajale vektorske grafike poput linija tablice, a preko nalaza je
  ležala traka umjesto rezerviranog mjesta. Usporedba sada dopušta isti
  mali pomak kao provjera riječi; stvarna oštećenja i dalje se uočavaju.

- **Vraćanje mnogo vrijednosti zaredom na Windowsu više ne propada zbog
  „Pristup odbijen“.** Tko je u Office datoteci vraćao mnogo redaka
  ploče brzo jedan za drugim, mogao je propasti zbog kratkotrajnog
  zaključavanja datoteke antivirusnim programom; zamjena sada takva
  zaključavanja kratko pričeka.

- **Windows put predaje naredbi zatvarao je provjernik umjesto da
  provjerava.** Provjera je li slušajuća instanca živa na Windowsu je
  slučajno slala pravi Ctrl+C vlastitoj konzolnoj skupini; sada pita
  sustav bez signala.

- **Višerječne oznake polja nisu djelovale, a djelovali su njihovi
  ulomci.** „Date of birth“, „Bank account“, „Cuenta bancaria“ i
  „Numero de cliente“ stajale su u popisu oznaka, ali su se ondje
  rastavljale na pojedinačne riječi i zato nikad nisu pogađale;
  ostajali su ulomci riječi poput „de“ i „of“, koji su otad vrijedili
  kao oznaka – „de“ je ipak dio imena („Anna de Vries“). Oboje je
  riješeno: fraze sada djeluju kao cjelina, ulomci su nestali.

- **Njemačke pozdravne formule sa „ß“ unatoč unosu tretirane su kao
  osobno ime.** Ispod „Herzliche Grüße“ ili „Mit freundlichen Grüßen“ u
  rezultatu je stajalo rezervirano mjesto, iako obje fraze oduvijek
  stoje u protupopisu. Uzrok je bio zapis koji se pri usporedbi nikad
  nije podudarao; zahvaćeno je bilo osam unosa u pet popisa. Sada svi
  djeluju.

- **„John Staff“ ostajao je nezamijenjen.** Prezime koje je ujedno
  engleski naslov stupca filtar oznaka odbacivao je zajedno s
  naslovom. Naslov ostaje i dalje netaknut, ime ispod ponovno se
  zamjenjuje.

- **Vrijednosti iz označenih polja obrazaca ostaju zaštićene u AI
  razini.** Lokalni sudac AI razine dosad je na ocjenu dobivao i
  nalaze čije značenje već dokazuje oznaka polja („Datum rođenja:“
  iznad vrijednosti) – i smio ih je odbaciti. Takve strukturno
  dokazane vrijednosti sada mu se više ne predlažu. Datoteka
  pridruživanja sada uz svaku zamjenu dodatno navodi put prepoznavanja
  („dokaz“).

- **PDF stranica čiji je sačuvani tekst pri čišćenju oštećen sada se
  prepoznaje i iznova gradi kao slikovni prikaz izvornika.** Kod nekih
  pisama izrađivača sačuvana tekstualna mjesta nakon čišćenja mogla su
  se pojaviti kao crni blokovi ili se riječi mogle stisnuti, iako su
  svi podaci za uklanjanje bili ispravno uklonjeni. Maskuro sada
  rezultat uspoređuje riječ po riječ i piksel po piksel s izvornikom;
  oštećena stranica zamjenjuje se svojim čistim slikovnim prikazom –
  s trakama zacrnjenja preko mjesta nalaza, zacrnjenim slikovnim
  područjima i pretraživim tekstom. Stranica ostaje čitljiva, uklanjanje
  pouzdano.

### Promijenjeno

- **U prevedenim sučeljima svaki stručni pojam sada se zove posvuda
  jednako.** Za jednu te istu njemačku riječ ovisno o prozoru stajala
  su dva ili tri prijevoda jedan uz drugi: zapisnik provjere na
  norveškom se dijelom zvao „Revisjonslogg“, dijelom „Kontrollogg“,
  besplatna razina dijelom „Gratisnivå“, dijelom „Gratisversjon“ – i
  slično na tucet daljnjih jezika. Tko je tražio postavku, pronalazio
  ju je u sljedećem prozoru pod drugim nazivom. Ujednačeno je na riječ
  koju sučelje ionako najčešće koristi.

  Pritom su se otkrila mjesta gdje je jedna riječ stajala za dvije
  **različite** stvari: francuski, grčki i korejski koristili su za
  „zacrniti“ i „maskirati“ isti izraz – baš tamo gdje program objašnjava
  razliku („Zacrnjivanje uklanja bez zamjene, maskiranje zadržava
  oblik“). Oboje je sada razdvojeno. Za švedski ta odluka još stoji
  otvorena: ondje se zacrnjivanje zove „maskera“ – ista riječ kao
  maskiranje.

- **Pitanje o vrsti korištenja pri prvom pokretanju je otpalo.** Ubrzo
  nakon pokretanja pojavljivao se prozor („Privatno ili u tvrtki?“), a
  u postavkama je stajao redak o tome. Oboje sada ne postoji – bez
  zamjene. Podatak o kojem ništa ne ovisi pogrešno navodi tko želi
  pogrešnu licencu, a tko je pošten, ne treba ga; svakoga je koštao
  jedan klik u trenutku kad nitko ne razmišlja o vrstama licence. Koja
  je licenca ispravna, stoji ondje gdje se o tome odlučuje: na
  stranici cijena, na blagajni i u pomoći. Tvrtke koje Maskuro
  raspoređuju centralno vrstu korištenja i dalje unaprijed određuju
  preko datoteke zadanih vrijednosti.

- **Napomene o vrsti licence sada navode o kojem je slučaju riječ.**
  Osobna licenca vrijedi isključivo za privatno korištenje; svaki
  poslovni ili gospodarski rad treba poslovnu licencu – i kao
  samostalni poduzetnik bez zaposlenika. To je stajalo u licencnim
  uvjetima, ali ni u programu ni u pomoći: ondje se uvijek govorilo
  samo o domeni tvrtke, a to baš taj slučaj ne obuhvaća: računalo
  samostalnog poduzetnika ne pripada nikakvoj domeni. Napomena pri
  učitavanju osobne licence to sada kaže, jednako i licencno poglavlje
  priručnika i česta pitanja, koja su za to dobila vlastiti unos.
  Ništa se time i dalje ne zaključava.

- **Putovi koji još nisu isporučeni sada stoje zajedno.** Postavke su
  dobile stranicu „Razvojni programer“; ondje stoje maksimalna razina
  prepoznavanja (AI) zajedno sa svojom protuprovjerom, katalog popisa
  riječi i nadzor mape. Sva tri su izgrađena, ali nisu provjerena u
  praksi – zato su vidljiva samo uz razvojnu licencu, i to posvuda
  istodobno: stranica, stavke izbornika i učinak pri izvođenju ovise o
  istoj odluci. Bez te licence ranije uključena AI razina ostaje bez
  učinka; njezina postavka se ne briše i ponovno vrijedi čim se put
  isporuči.

### Poboljšano

- **„Što se traži“ pokazuje tri daljnja popisa iz prepoznavanja
  imena.** Oslovljavanja iza kojih se sljedeća riječ čita kao ime;
  titule i uloge koje nakon toga **nisu** ime („Herr Bürgermeister
  Huber“); i osamdeset višejezičnih oznaka po kojima se prepoznaju
  brojevi predmeta, postupaka i slučajeva. Sva tri oduvijek djeluju, ali
  u pregledu se nisu vidjela.

- **„Što se traži“ pokazuje dva dosad nedostajuća popisa riječi.**
  Oslovljavanja i titule koje riječ ispred sebe čine imenom („Herr“,
  „Frau“, „Dr.“), i kratice normirnih organizacija po kojima Maskuro
  razlikuje uputu na normu poput „ÖNORM B 2110“ od osobe. Oboje
  oduvijek utječe na prepoznavanje, ali u pregledu nije stajalo.

- **Popisi pozicija, sadržaji, popisi opreme i upute na norme ostaju
  čitljivi.** Prepoznavanje sada vidi oblik retka: pogađano ime u retku
  strukture („1.3.1 Energieerdkabel 1kV“), retku sadržaja s vodećim
  točkama, popisu s crticom („- kabelloses Laden mit Magnetring“),
  iznad retka količine/cijene, u zaglavlju stupca ili iza „mittels“ je
  stručni pojam i više se ne zamjenjuje. Stvarna imena ostaju
  zaštićena – oslovljavanjem, oznakom polja i dokazom na drugom mjestu
  dokumenta; na mjernom korpusu nijedan podatak nije izgubio zaštitu.
  U poslovnom korpusu lažne uzbune time padaju s 25 na 6.

- **Naslovi, oznake obrazaca i pozdravne formule rjeđe se smatraju
  imenima – na njemačkom i engleskom.** Popisi riječi kojima Maskuro
  razlikuje stručne riječi od osobnih imena znatno su narasli: oznake
  iz računa, obrazaca i pošte tijela vlasti („Aktenzeichen“,
  „Verwendungszweck“, „Kostenstelle“, „Sort code“, „Subtotal“), naslovi
  odjeljaka prijava i izvještaja („WERDEGANG“, „QUALIFIKATIONEN“,
  „SUMMARY“, „REFERENCES“), njemačke i engleske vrste dokumenata
  („Auftragsbestätigung“, „Niederschrift“, „Timesheet“, „Agreement“) te
  zapovjedni oblici iz uputa („Sende…“, „Select…“). Engleska strana pri
  tome je dosad bila upadljivo slabo popunjena.

- **Označena polja sada odaju što u njima stoji i kad je oznaka
  složena.** „Lieferanschrift“, „Rechnungsadresse“, „Sachbearbeiterin“,
  „Kontoinhaber“, „Contact person“ i „Billing address“ sada vrijednost
  pored ili ispod sebe pridružuju istoj vrsti kao jednostavno
  „Anschrift“ ili „Name“ – u ispunjenom obrascu s poljima to je razlika
  između pronađenog i previđenog.

- **U prozoru uređivača kotačić miša na rubu stranice nastavlja
  listati.** Tko se na kraju stranice nastavi pomicati, dolazi na vrh
  sljedeće; tko se na početku pomiče natrag, dolazi na dno prethodne –
  dokument se time može proći od početka do kraja bez dodirivanja
  gumba stranica. Tipkovnica (Page Up/Page Down) to je već mogla;
  kratka stanka između dvije promjene stranice sprječava da inercija
  touchpada ponese pola dokumenta.

- **Minijature stranica u prozoru uređivača sjede sredinom pretinca.**
  Dosad su bile prilijepljene za lijevi rub, a pri širenju je rastao
  samo prazan rub desno.

- **Alatna traka prozora uređivača pokazuje svoje skupine.** Crte
  razdvajanja sada imaju prostor i boju, „Pretraži“ i „Prenesi na sve
  stranice“ stoje kao vlastite skupine uz alate, a „Prenesi“ se
  pojavljuje samo kod vrsta dokumenta u kojima nešto može učiniti.
  Svaka stavka u traci i izbornicima sada nosi sliku: „Retci teksta“ i
  povećalo za usporedbu dobili su vlastite simbole (povećalo je dosad
  dijelilo svoj s „Prije/poslije“), uz to zum, cijela stranica, širina
  stranice, okretanje, listanje i tipkovne prečice. „Otvori sistemskim
  programom“ sada stoji i u traci uz Ispis – put od gotovog rezultata
  do uobičajenog programa jedan je klik, ne prolazak kroz izbornik.

- **Kod čišćenja međuspremnika ponovno stoji da treba pregledati.** U
  postavkama napomena trajno stoji uz prekidač: Maskuro može previdjeti
  osobne podatke ili pogrešno postupiti s podacima, umetnuti tekst
  treba pregledati prije prosljeđivanja. Pri uključivanju uz to je
  navodi poruka, a bilježi se u području ispisa – i onda kad nijedna
  ikona ne radi u području obavijesti. Kod svakog pojedinog postupka
  kopiranja namjerno se ne pojavljuje: napomena koja bi dolazila pedeset
  puta dnevno nakon trećeg puta više se ne čita.

## 0.10.36-beta.1 – 20. kolovoza 2026.

### Poboljšano

- **Tehnički poslovni dokumenti više se ne rascjepkavaju zacrnjenjem.**
  Četiri kočnice prepoznavanja, dobivene iz jedanaest stvarnih ponuda i
  naloga: brojevi struktuiranja („1.3.1.1“) više ne vrijede kao IP
  adrese, upute na norme („ÖNORM EN 62446“) i identifikacijski kodovi
  više ne kao poštanski broj ili telefonski broj, a riječi uloga iza
  članova („der Kunde“, „des Auftraggebers“) više ne kao imena – u
  općim uvjetima stvarne ponude time je svih 46 riječi uloga ponovno
  čitljivo umjesto zacrnjeno. Adrese s oznakom države („A 3390 Melk“,
  „D-94032 Passau“) sada se u potpunosti uklanjaju, umjesto da poštanski
  broj ostane kao siroče.

- **Popisi riječi sada su potpuno pregledni.** Pod „Pomoć → Popisi
  riječi …“ moguće je pretraživati lokalno korištene popise za
  prepoznavanje i protuprovjeru, uz jezik, svrhu, izvor i sadržaj. Tu
  spadaju i Wordfreq, medicinski, osobni i središnje upravljani popisi te
  zalihe za izmišljene zamjenske vrijednosti. Priručnik opisuje katalog
  u vlastitom odjeljku.

- **Gotovi retci datoteka pokazuju korišteni jezik prepoznavanja.** Iza
  „gotovo“ sada stoji npr. „njemački“ ili „engleski“, kako bi neprikladan
  automatski odabir jezika odmah bio uočljiv. Ako je morao priskočiti
  drugi instalirani jezik, strelica prikazuje oba jezika.

- **Nova povećalo za usporedbu odmah pokazuje odgovarajuće mjesto u
  izvorniku dok čitate.** Njegov uvećani isječak izvornika prati
  pokazivač miša iznad rezultata koji se i dalje može uređivati; kod
  teksta prati odlomak. Povećalo se može koristiti uz rub prozora ili
  izvući kao vlastiti, maksimizirajući prozor. Njegov je zum izravno
  podesiv između 50 i 300 posto i pamti se jednako kao i uključivanje.
  „Vrati na početno“ vraća i maksimizirano ili nezgodno usidreno
  povećalo natrag lijevo u upotrebljivu veličinu. Zamijenjene izvorne
  vrijednosti u povećalu su istaknute žutom bojom, kako bi zahvaćene
  riječi odmah bile uočljive pri čitanju. Jednom aktivirano, ponovno se
  otvara kod budućih prikladnih dokumenata – i nakon ponovnog pokretanja
  programa. Dosadašnji prekidač prije/poslije ostaje sačuvan u izborniku
  prikaza. Priručnik ga opisuje u vlastitom odjeljku.

- **Dokazi otvorenog koda i modela sada su precizni po izdanju.** Izgradnja
  paketa stvara strojno čitljiv popis komponenata s kontrolnim
  vrijednostima priloženih licencnih tekstova. MPL izvori, podrijetlo
  modela, fiksne revizije, izmjene i SHA-256 dokazuju se odvojeno;
  naknadno preuzeti modeli dobivaju svoj dokaz podrijetla izravno u mapi
  modela. Pokretni Tesseract i spaCy popisi izvora su fiksno pripeti.
  Prodajni artefakti ostaju zaključani dok svi izvori i prilozi modela
  ne budu objavljeni i provjereni.

- **Lokalni wordfreq skup podataka je potpuno licencno dokumentiran.**
  Izgradnja paketa provjerava inačicu 3.1.1, 39 nepromijenjenih malih
  popisa uključujući CJK i kinesku znakovnu kartu prema broju, veličini i
  kontrolnoj vrijednosti manifesta. Apache-2.0 napomena o kodu, potpuna
  CC-BY-SA-4.0 licenca, atribucija, izvori podataka i izostavljeni
  veliki, Jieba i nepodržani popisi dokumentirani su u paketu.

- **Česte riječi rečenice rjeđe se pogrešno zacrnjuju.** Lokalni rječnik
  učestalosti služi kao dodatna protuprovjera kad prepoznavanje imena
  smatra glagol, zamjenicu, član ili prijedlog osobom. Rječnik nikada ne
  odlučuje sam: imenice, višedijelna imena te imena u poljima, popisima i
  iza oslovljavanja ostaju zaštićeni. Kineski, japanski i korejski
  koriste isključivo točne granice tokena svojih već postojećih jezičnih
  modela; za jezike koji ne postoje ne koristi se navodno srodan jezik
  rječnika. Za to se nikakav tekst dokumenta ne prenosi na internet.

- **Tehnički pojmovi proizvoda i opreme rjeđe se smatraju imenima ili
  mjestima.** Lokalna protuprovjera sada povezuje učestalost, vrstu
  riječi, tehničko tvorbu riječi i stručna područja. Time u dokumentu
  ostaju primjerice „Travel-Assistent“, „Family-Bonus“, „WLTP-Wert“,
  „Easy-Start“ i složeni pojmovi brojeva, nositelja ili kočnica. Engleski
  se dijelovi provjeravaju lokalno i u njemačkom stručnom tekstu; stvarna
  vlastita imena, oslovljavanja te polja osoba i mjesta zadržavaju
  prednost. Uz to „2-godišnje tvorničko jamstvo“ više se ne smatra
  životnom dobi.

- **Licencna prava za Qt/PySide sada su potpuno sljediva.** Paket
  programa dodatno sadrži potpuni tekst GPL-3.0, točne inačice Qt-a,
  ponudu izvornog koda i njemačko/englesku uputu za zamjenu dinamičkih
  biblioteka uključujući lokalno ponovno potpisivanje na macOS-u.
  Prodajna izgradnja je blokirana dok točni izvorni arhivi isporučene
  inačice nisu dostupni na vlastitoj stranici izvornog koda.

- **Licenca i stanje ažuriranja sada za svaku razinu jasno kažu što
  vrijedi.** U prozoru licence i u postavkama ažuriranja stoji jesu li
  ažuriranja uključena, do kojeg dana vrijede i ostaje li tekuća inačica
  trajno upotrebljiva. Osobne licence nakon graničnog datuma više ne
  instaliraju kasnije objavljenu inačicu; i novo preuzeti instalacijski
  program prepoznaje prema svom fiksno ugrađenom datumu izdanja obuhvaća
  li ga uneseni ključ. Posljednja pokrivena osobna inačica ostaje trajno
  upotrebljiva. Završi li, naprotiv, poslovna pretplata, prestaju
  korištenje i ažuriranja; probno razdoblje i besplatna razina ne
  otvaraju se kao zaobilazni put.

- **Osobne trajne licence sada nalaze ispravno stanje programa i nakon
  ponovne instalacije.** Potpisani katalog inačica vodi sve stabilne
  inačice i njihove pakete. Ako posljednji instalacijski program obuhvaćen
  kupnjom više nije dostupan, automatski se smije umjesto njega koristiti
  točno sljedeća viša dostupna stabilna inačica – nikada beta ili
  nightly. Kod prenove instalacije korisnik može instalirati dopušteno
  stanje ili prijeći na stranicu kupnje za novo razdoblje ažuriranja;
  korak unatrag se ne događa tiho. To vrijedi i za upravljane MSI
  instalacije.

- **Automatsko zacrnjivanje lica sada je jednoznačno opisano.** Pomoć
  programa i tekst o zaštiti podataka nazivaju funkciju „Prepoznaj i
  učini neprepoznatljivim područja lica“ i razgraničavaju je od
  identifikacije, prepoznavanja, usporedbe lica, biometrijskih predložaka
  i baza podataka osoba ili lica. Uz to jasno napominju da potpuno
  lokalno prepoznavanje može previdjeti ili pogrešno označiti područja te
  da rezultat zbog toga treba vizualno provjeriti. I kod pojedinačno
  očišćene slikovne datoteke izvještaj o rezultatu sada navodi
  prepoznata i pikselizirana područja lica; nedostajuće prepoznavanje
  teksta pritom se više ne opisuje pogrešno kao potpuno nepromijenjena
  datoteka.

## 0.10.36-alpha.20260820 – 20. kolovoza 2026.

### Riješeno

- **Anonimizirani podaci sada se u potpunosti mogu vratiti neovisno o
  redoslijedu.** Ranije vraćanje tražilo je vrijednost preko vidljivih
  tekstualnih sidra. U gustim tablicama, izravno susjednim rezerviranim
  mjestima i nevidljivim Office/mail spremištima ti su sidra nedostajala;
  ponekad je pojam zbog toga postajao vratljiv tek nakon što je neki
  drugi čitljivi tekst slučajno stvorio novo sidro. Sada se rezultat i
  izvornik uspoređuju po stvarnom formatnom nositelju s punim
  pridruživanjem, a zapisuju se samo dokazana mjesta odabrane
  vrijednosti.

- **Imena, adrese e-pošte, brojevi i vlastiti pojmovi provjere ostaju
  jednoznačno upravljivi i kod preklapajućeg prepoznavanja.** Ako je ista
  čitljiva vrijednost pridružena dvjema vrstama, odlučuje rezervirano
  mjesto koje stvarno stoji na mjestu nalaza zajedno s odabranim retkom
  bočne trake. Nedokazan par vrijednost/rezervirano mjesto i dalje
  ostaje sigurno zaključan.

- **Posebni slučajevi e-pošte više ne ostavljaju skrivena rezervirana
  mjesta.** To vrijedi za MIME-kodirane predmete, tekstualne privitke i
  imena razdvojena HTML oznakama u EML i MSG datotekama. UTF-8 HTML bez
  vlastite oznake znakovnog skupa u Outlook datotekama također se više
  ne pretvara u nečitljive znakove pri svakom koraku obrade; starije,
  već tako zapisane rezultate i dalje je moguće vratiti.

### Poboljšano

- **Nova matrica pokrivenosti obrađuje svaki anonimni redak bočne trake
  pojedinačno i namjerno unatrag.** Provjerava svih 14 tekstualnih,
  Office, web i mail formata te PDF, a zatim i formule, atribute, veze,
  komentare, zaglavlja pošte, privitke i unutarnja pomoćna spremišta.
  Potpuno pokretanje na macOS-u sada obuhvaća 149/149 zelenih
  provjernih skripti.

## 0.10.35-alpha.20260820 – 20. kolovoza 2026.

### Poboljšano

- **Jezična mjerenja sada uistinu uspoređuju jednako s jednakim.** Redoviti
  mjerni korpus sadrži istih 14 slučajeva dokumenata s istih sedam
  tekstualnih i četiri slikovna zadatka na njemačkom i engleskom. Puni
  ciklus ponavlja točno tu matricu za svih dvanaest postojećih jezika
  korpusa. Obrasci, tablice, razgovori i drugi još potpuno neprevedeni
  strukturni uzorci ostaju sačuvani, ali se prikazuju odvojeno i više se
  ne miješaju u jezične kvote.

- **Puni ciklus piše za svaki jezik vlastito mjerno izvješće.** Bez
  jezične oznake namjerno se provjeravaju njemački i engleski;
  `--alle-sprachen` traži potpuni korpus od dvanaest jezika i prekida
  se prije prve datoteke ako neki jezik ili slučaj nedostaje. Rezultati
  istog naziva nalaze se u odvojenim jezičnim mapama. Ukupno izvješće uz
  ponderiranu stopu nalaza navodi i neponderiranu srednju vrijednost
  jezičnih kvota.

- **Otvorena jezična usporedba sada pokazuje i svoju stvarnu granicu.** U
  redovitom pokretanju s prepoznavanjem teksta njemački i engleski
  uklanjaju 218/218 poznatih podataka bez lažne uzbune. Puni test s
  prepoznavanjem teksta i Visokom razinom uklanja 1.255/1.308 podataka
  uz 17 lažnih uzbuna; jedanaest jezika postiže 100 posto, hindski 51
  posto. Ranije pune kvote temeljile su se na nejednakim skupovima
  dokumenata i ciljanih vrijednosti te nisu usporedive s novom matricom.

## 0.10.34-alpha.20260819 – 19. kolovoza 2026.

### Riješeno

- **Imena koja se pojavljuju više puta ostaju dostupna u bočnoj traci i
  nakon pojedinačnog vraćanja.** Dosad je cijeli redak imena nestajao već
  nakon prvog vraćenog mjesta `[IME]`. Daljnja mjesta istog imena time su
  ostajala kao rezervirana mjesta, a povremeno su čak bila blokirana dok
  se nisu vratila druga imena. Sada redak nestaje tek nakon posljednjeg
  mjesta; već vraćeni čitljivi tekst ipak se ponovno automatski ne
  anonimizira. To vrijedi i za djelomično uspjelo skupno vraćanje i za
  alat okvira u PDF-ovima.

- **„Poništi zamjenu“ radi i iz Office pregleda stranice.** Vidljiva
  stranica ondje je samo prolazni PDF pregled; sada se ispravno mijenja
  Word, tablični ili prezentacijski dokument ispod, a pregled se
  naknadno obnavlja.

- **Vraćanje sada u potpunosti dohvaća i skrivene parnjake neke
  vrijednosti.** U Word, OpenDocument, Excel i PowerPoint datotekama isti
  se podaci dodatno mogu nalaziti u formulama, komentarima, dijagramima,
  vrijednostima polja, alternativnim tekstovima i ciljevima poveznica;
  HTML, EML i MSG nose ih još i u atributima, JSON-u, zaglavljima poruka
  i privitcima. Dosad je ondje, ovisno o formatu, dio ostajao kao
  rezervirano mjesto. Sada se svaki podatak ponuđen u području nalaza
  može vratiti neovisno i bilo kojim redoslijedom. Namjerno uklonjeni
  metapodaci, povijesti izmjena i prijenosna zaglavlja iz sigurnosnih
  razloga ostaju i dalje uklonjeni.

- **Kod vraćanja iz slika više ne ostaje crna rubna linija.** Desni i
  donji rub okvira pri kopiranju iz izvornika bili su izračunati po
  jednu slikovnu točku preusko. Koordinate sada odgovaraju zacrnjenju.

### Poboljšano

- **Provjera pokrivenosti sada svaki od 22 podržana nastavka datoteke
  provodi kroz potpuni krug.** Sadržajno bogate datoteke se čiste, sve
  ponuđene vrijednosti vraćaju se, a zatim se temeljito provjeravaju.
  Uz to dolaze stvarno upravljanje bočnom trakom, pikselno točne
  usporedbe slika i vidljivo LibreOffice iscrtavanje svih sedam uredskih
  formata. Manji regresijski testovi ostaju ondje gdje pokrivaju vlastiti
  slučaj pogreške ili sigurnosti; dokazano dvostruka HTML provjera i
  test uklonjenog crno-bijelog načina rada su otpali.

- **Potpuni mjerni korpus ove inačice dostupan je za ponovno mjerenje.**
  Paket sadrži 294 sintetička dokumenta u dvanaest formata i dvanaest
  jezika, 2.564 poznata podatka, četiri strojno čitljiva popisa ciljanih
  vrijednosti i uputu. Preuzimanje na stranici kvalitete koristi naziv
  datoteke ovisan o sadržaju, kako preglednik ne bi slučajno poslužio
  stariju inačicu iz predmemorije.

## 0.10.33-alpha.20260819 – 19. kolovoza 2026.

### Novo

- **I u slikovnim datotekama pojedina mjesta sada je moguće vratiti iz
  izvornika.** Alat okvira „Vrati izvornik“ kopira slikovne točke na istom
  mjestu natrag iz netaknute izvorne datoteke. Put ostaje zaključan ako
  izvornik nedostaje ili ima druge dimenzije slike; time se sprječava
  umetanje sadržaja s pomaknutog mjesta.

### Poboljšano

- **Ručne trake zacrnjenja sada se standardno uklapaju u retke teksta.**
  Povlačenje preko više redaka stvara po retku jednako visoku traku i
  ostavlja bijeli prostor između njih slobodnim. Za potpise, grafike i
  druge posebne slučajeve „Slobodni okvir“ vraća se na samostalno
  odabranu visinu.

- **Uređivač sada objašnjava sljedeći korak izravno iznad dokumenta.**
  Napomena se mijenja ovisno o vrsti dokumenta i alatu te kaže očekuje li
  se klik na riječ, odabir teksta ili okvir. Uz to alat, pokazivač miša i
  prikaz uživo već prije otpuštanja pokazuju što će se dogoditi.

### Uklonjeno

- **Uklonjena je izlazna crno-bijela varijanta sklona pogreškama.** Kod
  nekih PDF-ova nevidljiva tekstualna polja ostajala su pomaknuta u
  odnosu na rasteriziranu stranicu; prividno smanjenje datoteke nije
  vrijedilo tog sigurnosnog i prikaznog rizika. Uobičajeno čišćenje PDF-a
  i ciljano rasteriziranje problematičnih stranica ostaju sačuvani.

## 0.10.32-alpha.20260819 – 19. kolovoza 2026.

### Novo

- **Nadzor mape sada uistinu radi u pozadini.** Ulazna mapa, izlazna mapa
  i pravila stoje na vlastitoj stranici pod „Postavke“. Pokreće se i
  zaustavlja preko Maskuro ikone u traci zadataka ili izborniku; stavka
  se pojavljuje samo uz licencu koja je za to otključana. Prozor postavki
  se nakon toga može zatvoriti, a glavni prozor spustiti u ikonu, bez
  prekidanja nadzora.

- **Uređivač za doradu sada ima trajni prekidač načina učenja.** Stoji u
  području nalaza i u izborniku „Alati“. Kad je isključen, ni pri
  vraćanju ni nakon ručnih ispravaka ne pojavljuju se pitanja o
  stvaranju vlastitih pravila. Maskuro pamti odabir za sve buduće
  otvorene dokumente; samo vraćanje pritom radi nepromijenjeno.

### Riješeno

- **Veliki dodatni model ponovno se može učitati.** Javno spremište
  odbijalo je Pythonovu opću zadanu oznaku s 403. Dohvaćanje modela
  sada koristi isti imenovani Maskuro mrežni put kao i ostale vlastite
  usluge; datoteka od gotovo 596 MB i njezina kontrolna vrijednost
  ostaju nepromijenjeni.

- **Maksimizirano povećalo za usporedbu više ne ostaje kao uska traka na
  gornjem rubu pri usidravanju.** Prije usidravanja njegovo se slobodno
  stanje prozora normalizira. Spremljeno maksimizirano stanje pri
  sljedećem otvaranju također se vraća na promjenjivu veličinu.

- **Skupno vraćanje u tablicama i drugim tekstualnim formatima sada
  uistinu vraća sve odabrane vrijednosti.** Kod anonimiziranih
  rezerviranih mjesta poput `[EMAIL]` Maskuro je dosad zapisivao
  vrijednosti jednu za drugom. Čim je prva bila zamijenjena, brojevi
  svih preostalih nalaza pomicali su se naprijed, ali već izračunati
  plan i dalje je pokazivao na stare brojeve. Time se vraćao samo dio
  odabira. Sada se sve odabrane vrijednosti istog rezerviranog mjesta
  zapisuju zajedno i sa stabilnim brojevima nalaza. Postane li neko
  mjesto jednoznačno tek zahvaljujući drugoj vraćenoj vrijednosti,
  Maskuro ga u istom koraku ponovno provjerava – redoslijed odabira
  time više nije važan.

- **„Poništi zamjenu“ u PDF-ovima više ne izostavlja odabrane
  vrijednosti.** Ako je rezervirano mjesto stajalo vrlo blizu iza druge
  riječi ili je u izvorniku zarez bio izravno uz vrijednost, provjera
  položaja mogla je susjednu riječ odnosno interpunkcijski znak
  pogrešno pripisati vrijednosti. Kod zajedničkog vraćanja tada su
  ostajala pojedina rezervirana mjesta i retci nalaza. Provjera se sada
  ravna prema stvarnom početku riječi i uzima u obzir i različit zaokret
  stranice između izvornika i rezultata.

- **Vraćeni PDF tekst sada zadržava svoju izvornu veličinu.** Dosad je
  kao mjerilo služilo već umanjeno rezervirano mjesto; dodatno je i za
  izvorni tekst vrijedila gornja granica od 11 točaka predviđena za
  rezervirana mjesta. Sada se izvorni okvir i izvorna veličina fonta
  preuzimaju iz izvorne datoteke – jednako kod alata okvira kao i kod
  vraćanja iz ploče nalaza.

### Poboljšano

- **Napomena o provjeri sada jasnije imenuje preostali rizik.** Izričito
  kaže da Maskuro može previdjeti podatke ili pogrešno postupiti s
  podacima, te prije svake objave ili prosljeđivanja traži potpunu
  provjeru i po potrebi ručnu ispravku. To vrijedi i za tekst iz
  međuspremnika i potpuno je preneseno u svih 17 prijevoda.

- **Zapisnik provjere sada počinje i unutar svojih redaka bez
  korisničkog imena.** Sam zapisnik ostaje isključen dok ga tvrtka
  namjerno ne aktivira. Nakon toga, bez dodatne tvrtkine postavke, ni u
  retku ni u nazivu središnje mjesečne datoteke ne stoji korisničko
  ime; ondje za sigurno razdvajanje služi neprogonjiv pseudonim izveden
  isključivo iz slučajne lokalne tajne profila. Licencni dijalog više
  ne preporučuje aktivaciju, pretpostavlja „Bez zapisnika“ i unaprijed
  upozorava na radničko vijeće, predstavništvo zaposlenika i zaštitu
  podataka.

- **Zamjena sada imenuje što zamjenjuje.** Označeno ime postaje
  `[NAME_3]`, mjesto `[ORT_1]`, telefonski broj `[TELEFON_2]` – umjesto
  dosadašnjeg zajedničkog `[BEGRIFF_n]`. Vrsta se prepoznaje pri kliku;
  nije li jednoznačna – obična riječ, ili ime *i* mjesto u jednom
  odabiru – ostaje kod općeg pojma. Rezervirano mjesto koje tvrdi vrstu
  koja nije točna bilo bi gore od onog koje ne navodi nikakvu.

- **Alati u prozoru uređivača sada imaju svoju tipku.** **Z** zacrnjuje,
  **M** zamjenjuje, **V** vraća izvornik, **P** pikselizira. U prikazu
  teksta odmah djeluju na oznaku, u pregledu stranice biraju alat.
  **Slova prate jezik** kojim upravljate programom, jer pomoć u
  pamćenju vrijedi samo na vlastitom jeziku. Tipka stoji na gumbu. Tko
  upravo tipka u traci pretrage, i dalje piše slova – ondje ne
  djeluju.

- **Program jednom dnevno javlja u kojem stanju radi – bez ikakve
  oznake.** Time brojimo koliko se instalacija koristi i kako se to
  raspoređuje na probno razdoblje, besplatnu razinu i licencu. Šalju se
  stanje, operacijski sustav, inačica, kanal, zemlja, jezik, okruženje i
  razina prepoznavanja – **ništa o vašim dokumentima i ništa po čemu bi
  se vaše računalo moglo prepoznati**. Dvije poruke od vas za nas
  izgledaju kao poruke dviju različitih osoba; jedan jedini put se iz
  toga ne može pratiti. Što se točno šalje i kako se to isključuje,
  stoji u tekstu o zaštiti podataka pod točkom 5.

- **Poprečno uvučene stranice sada same stoje ispravno okrenute.** List
  koji je skeniran nakrivo, bez ikakve zabilješke o tome, dorada
  prepoznaje po toku teksta i uspravlja prikaz. Gdje to ne ide – kod
  čistog skena bez čitljivog teksta – dva nova unosa u izborniku
  „Prikaz“ okreću ručno (Ctrl+Shift+L i Ctrl+Shift+R). Okreće se samo
  prikaz: na datoteci se ništa ne mijenja, a zacrnjivanje i dalje pogađa
  točno mjesto na koje se klikne.

- **Lokalno izdanje sada svoje licence vodi potpuno i vidljivo.** Bau
  utvrđuje stvarno pripojene Python pakete, njihove licencne tekstove
  zajedno s pregledom inačica odlaže pod `lizenzen` i prekida se kod
  praznine. I Qt, Tesseract i model lica imaju svoje potrebne tekstove;
  uvjeti za sam Maskuro prilažu se kao licencni ugovor.

- **Sada se vidi u kojem rezerviranom mjestu stoji kursor.** Tko klikne
  u rezervirano mjesto, vidi ga potpuno osvijetljeno – zajedno sa
  zagradama i brojem. Gumb „Vrati odabir“ radio je i prije na sam klik;
  samo se nije vidjelo koju je oznaku pogodio. Osvjetljenje ostaje i
  kad se miš pomakne prema gumbu.

- **Pokazivač miša sada kaže koji je alat odabran.** Četiri alata dijele
  istu površinu i istu gestu; dosad su svi izgledali jednako. Nišan
  znači zacrni, zatvorena šaka zamijeni, otvorena šaka vrati izvornik.

- **Pripremljen Office dokument sada odbija sam program.** Word, Excel
  ili OpenDocument datoteka može donijeti upute koje pri otvaranju u
  svoj tekst dovlače tuđu datoteku vašeg računala ili preplave radnu
  memoriju. Oboje se odbijalo i dosad – ali od ugrađene XML biblioteke,
  ne od Maskura. Sada to odlučuje sam program, neovisno o tome koja se
  inačica te biblioteke nalazi u paketu. Za uobičajene dokumente ništa
  se ne mijenja.

### Riješeno

- **Ploča nalaza sada uklanja zacrnjena rezervirana mjesta.** Ako je npr.
  `[NAME_1]` u prozoru uređivača zacrnjen, njegov je redak vrijednosti
  dosad ostajao desno, iako u dokumentu takvog mjesta više nije bilo.
  Redak sada pada s posljednjim nalazom; pojavi li se isto rezervirano
  mjesto još na nekom drugom mjestu, redak ostaje sačuvan.

- **Kod vraćanja na zaokrenutoj stranici susjedna riječ sada ostaje
  netaknuta.** Traka zacrnjenja namjerno malo prelazi preko teksta; već
  je taj uski rub dosad mogao zahvatiti susjednu riječ poput „u“. Sada
  broji samo izrazito preklapanje, ne dodir na rubu.

- **Druga zamjena u istom retku odnosila je i sljedeći dio rečenice.**
  Tko je „Obradu preuzima Quaxi Blubbo“ zamijenio dvaput zaredom,
  dobivao je „Obradu preuzima [ORT_1] [ORT_2]“ – riječ iza toga
  nestajala je bez zamjene i bez ikakve poruke. Uzrok je bilo susjedno
  rezervirano mjesto: ostatak retka nakon prve zamjene počinje razmakom,
  a traženje njegovog mjesta u tekstu zahvatilo je zatvarajuću zagradu
  susjeda. Nakon toga sve je bilo pomaknuto za jedan znak. Pogođen je
  bio svaki redak u kojem se dvaput zamjenjivalo ili zacrnjivalo – i kod
  vraćanja pored.

- **Zamjena više ne zacrnjuje kad je rezervirano mjesto predugo.** Nije
  li uz riječ bilo mjesta za `[BEGRIFF_2]`, područje se dosad prekrivalo
  crnom bojom – čime se više nije vidjelo ni da je ondje nešto stajalo,
  a kamoli da se to može vratiti. Sada se piše kraći zapis: `[BEGR_2]`,
  `[BE_2]`, u krajnjem slučaju `[B_2]`. Tekući broj ostaje na svakoj
  razini – po njemu vraćanje ponovno pronalazi mjesto. Samo gdje ni
  najkraći zapis ne stane, ostaje traka.

- **Zamjena je ostavljala tekst netaknut ako je u istom retku već bilo
  zacrnjeno.** Tko je u prozoru uređivača vratio ime iz izvornika, od
  toga zamijenio ime (za njega nije bilo mjesta – nastala je traka) i
  zatim zamijenio prezime, dobivao je umetnuto rezervirano mjesto, ali
  ime **nije bilo uklonjeno**. Uočeno je to samo po upozorenju naknadne
  provjere. Uzrok je bio sam redak: nakon prvog zacrnjenja njegov
  ostatak počinje razmakom, na koji traženje mjesta u tekstu nije imalo
  oslonca. To je pogađalo svako drugo zacrnjenje u istom retku.

- **Uključena proširena razina prepoznavanja bez svog modela sada je
  uočljiva.** Kvačica je mogla biti postavljena dok je model nedostajao
  – postavke vrijede za svaku instalaciju, ali model leži uz program.
  Čišćenje je tada radilo bez te razine, bez ijedne riječi o tome. Sada
  kvačica kaže da model nedostaje, a rezultat nosi upozorenje. Vaš
  jednom donesen odabir pritom ostaje spremljen: čim se model učita,
  ponovno djeluje.

- **Kod anonimiziranja sada se vraća pravi pojam.** Tko je ručno
  zamijenio više pojmova, a zatim jedan od njih vratio, dobivao je
  uvijek **prvi** – iz „Schmidt“ nastajao je „Müller“. Pridruživanje je
  po rezerviranom mjestu pamtilo samo jednu zamjenu, a kod
  anonimiziranja svi nose isto rezervirano mjesto; drugi i svaki
  sljedeći pojam pritom su otpadali. Sada svaka vrijednost dobiva svoj
  vlastiti redak – i u popisu zamjena, koji je prije bio prekratak.

- **U tablicama se sada može i vraćati.** U CSV-u ili popisu osoblja
  rezervirana mjesta stoje izravno jedna do drugih, odvojena samo
  točkom-zarezom. Dosad ondje program nije mogao dokazati koja je
  vrijednost stajala na kojem mjestu i odbijao je – kod `[NAME]` je
  išlo, kod `[GEBURTSDATUM]` i `[TELEFON]` nije. Sada rastavlja redak na
  svim rezerviranim mjestima. Ostane li mjesto uistinu dvoznačno, i
  dalje odbija: pogrešno vraćena vrijednost bila bi gora od izostale
  obavijesti.

- **A odbijanje se sada i vidi.** Stajalo je u prigušenoj sivoj boji na
  donjem rubu prozora, a rečenica je bila toliko duga da je bila
  odsječena – izgledalo je kao da se ništa ne događa. Rečenice su
  skraćene, a redak nekoliko sekundi svijetli u boji upozorenja.

- **Vraćanje sada vrijedi i nakon sljedećeg zahvata.** Tko je kod
  anonimiziranja vratio više mjesta, a zatim zamijenio nešto drugo,
  zatekao je sva vraćena mjesta ponovno zamijenjena i morao je
  početi ispočetka. Uzrok je bilo pridruživanje: ono je pamtilo
  vrijednost, a samostalno usklađivanje za jedinstvena rezervirana
  mjesta vraćalo ju je pri sljedećem zapisu. Sada vrijedi: ono što
  vratite, ostaje vraćeno – druga mjesta iste vrijednosti time nisu
  dirnuta.

- **U tekstualnim, Word, Excel i mail datotekama sada je uistinu
  dovoljan klik u rezervirano mjesto.** Odgovarajuća poruka stajala je
  već u prethodnoj inačici, ali gumb „Vrati odabir“ ostajao je zaključan
  dok nešto nije bilo precizno označeno – dakle uopće se nije dolazilo
  do puta koji bi sam postavio odabir.

### Riješeno

- **Zapisnik provjere više ne odaje naziv datoteke.** Datoteke namjerno
  vodi kao kontrolnu vrijednost, a ne u čitljivom obliku, jer naziv
  datoteke odaje klijenta i predmet spora. Ta se kontrolna vrijednost
  ipak mogla potvrditi pogađanjem – putanja nije slučajan broj. Sada u
  izračun ulazi slučajna vrijednost ove instalacije: brojanje i
  razlikovanje u zapisniku i dalje rade, provjera izvana više ne.

## 0.10.31-alpha.20260819 – 19. kolovoza 2026.

### Poboljšano

- **I u tekstualnim i tabličnim datotekama rezervirano mjesto zasvijetli
  crveno pri pokazivanju.** Dosad je crveni pregled postojao samo na PDF
  stranici. Sada oba prikaza pokazuju isto: što je crveno, pogađa
  sljedeći potez – a za vraćanje je dovoljan jedan klik unutra.

- **Dovoljan je klik na riječ – pravokutnik postavlja uređivač sam.** U
  prozoru uređivača dosad je preko svakog mjesta trebalo povući
  pravokutnik. Sada je dovoljan klik: okvir se postavlja oko riječi i
  ostaje dohvatljiv, dakle može se dalje razvlačiti ili pomicati. Pri
  pokazivanju mišem riječ već zasvijetli crveno, tako da se unaprijed
  vidi što bi klik pogodio. Gdje riječi nema, povlači se okvir kao
  dosad.

- **Pravokutnikom više nije potrebno precizno ciljati.** Tko povuče
  pravokutnik preko rezerviranog mjesta ili zacrnjenja, uvijek misli na
  cijelo mjesto – nikad na njegovu polovicu. Okvir zato samostalno raste
  na cjelinu koju dotiče: na cijelo rezervirano mjesto, cijelu traku ili,
  na skeniranom listu, na cijelu zacrnjenu površinu. Nikad ne postaje
  manji od povučenog okvira.

- **Zacrnjuje se sada po riječima.** Okvir preko polovice riječi dosad je
  zacrnio samo tu polovicu – a napola zacrnjeno ime i dalje je ime.
  Dotaknute riječi sada padaju u cijelosti; susjedna ostaje netaknuta.

- **U tekstu i tablicama dovoljan je klik u rezervirano mjesto.**
  „Vrati odabir“ dosad je zahtijevao precizno označavanje rezerviranog
  mjesta zajedno s uglatim zagradama. Sada je dovoljno postaviti
  pokazivač unutra; odabir vidljivo skoči na cijelo rezervirano mjesto.

- **Belgija je dodana kao zemlja.** Odabirljiva u postavkama; prepoznaju
  se belgijski telefonski brojevi, matični broj (Rijksregisternummer, s
  kontrolnom znamenkom), PDV/tvrtkin broj (s kontrolnom znamenkom),
  adrese na oba službena jezika te poštanski broj s mjestom. Dosad su
  belgijski telefonski brojevi ostajali netaknuti, jer zemlja uopće nije
  bila u katalogu.

- **Kanal ažuriranja sada kaže koliko rano dobivate novo – ne koliko
  daleko.** Tko je bio na „Testnoj inačici“, uopće mu nisu bili ponuđeni
  novi pregled ili nova stabilna inačica, i morao je ručno mijenjati
  kanal da bi za to uopće saznao. Sada se nudi i sve što je pouzdanije:
  Testna inačica prima testne inačice, preglede i stabilne inačice,
  Pregled prima preglede i stabilne. Obrnuto nikad – na Pregledu se ne
  nudi testna inačica, čak i ako je novija.

- **U prozoru postavki retci sada stoje dalje jedan od drugoga.** Četiri
  stranice koristile su vlastite razmake umjesto rastera koji vrijedi u
  ostatku programa; osobito na stranici „Prepoznavanje“ kućice za
  potvrdu bile su zbog toga primjetno pregusto raspoređene.

### Riješeno

- **Ispunjeni PDF obrasci više se ne prikazuju prazni pri ručnoj
  doradi.** Maskuro za to isključivo prolaznu radnu kopiju pretvara u
  statične stranice: unesene vrijednosti postaju vidljive i stvarno se
  mogu zacrniti; čitljiva polja obrasca ne ostaju skrivena u datoteci.
  Izvornik ostaje interaktivan i nepromijenjen. To sada vrijedi i za
  dinamičke XFA obrasce: XFA-sposoban PDFium najprije izgrađuje
  vrijednosti i prijelome stranica, zatim nastaje novi PDF isključivo
  od statičnih slikovnih stranica. Ako izgradnja XFA ne uspije, datoteka
  se sigurno odbija umjesto da se prividno otvori prazna.

- **„Prekini“ sada djeluje i tijekom preciznijeg prepoznavanja.** Dosad
  se gumb zaključavao pri kliku, ali izvođenje je nastavljalo računati
  do posljednjeg bloka – kod duge datoteke to su minute bez izlaza, a
  gumb je pritom izgledao kao da je djelovao. Sada se izvođenje
  zaustavlja kod sljedećeg bloka.

- **U CSV datotekama imena se sada pronalaze i kad ispred njih nema
  razmaka.** U „P-1000;Brunnthaler, Elisabeth“ broj osoblja lijepi se
  preko točke-zareza uz ime, a za prepoznavanje to je bila jedna jedina
  riječ bez imena u sebi – u popisima osoblja tako je, ovisno o retku,
  ostajalo cijelo ime. Telefonski brojevi, formule i broj stupaca
  datoteke time nisu zahvaćeni.

- **Ime čije ime i prezime oboje nose crticu sada se prepoznaje.**
  „Marie-Luise Habsburg-Ott“ ostajalo je netaknuto usred rečenice, dok je
  „Dragan Mitrović“ u istoj rečenici bilo pronađeno – baš kombinaciju
  dviju spojenih polovica jezični je model previdio. Spojene imenice
  poput „Nord-Süd-Verbindung“ ili „Software-Entwickler“ time nisu
  zahvaćene.

## 0.10.30-beta.1 – 18. kolovoza 2026.

### Poboljšano

- **Veličina pisma u prikazu teksta sada se vidljivo podešava.** Klizač
  dolje desno, koji je dosad zumirao samo u pregledu stranice, u
  prozoru uređivača kod tekstualnih i Office datoteka podešava veličinu
  pisma (50–300 %) – jednako i „Povećaj“/„Smanji“ u izborniku Prikaz.
  Ctrl+kotačić miša oduvijek je to mogao, ali to je znao samo tko je
  probao; sada rade klizač, prikaz i kotačić zajedno.

- **U tamnom izgledu sada leži bijeli list na tamnoj radnoj površini.**
  Dosad je bilo obrnuto: oko lista je ostajala svijetla površina, a
  sam tekst stajao je svijetlo na tamnom. Sada list u oba izgleda
  ostaje papirno bijel s crnim pismom – kao PDF stranica, koja se u
  tamnom načinu rada također ne zatamnjuje – a površina oko njega je
  tamna.

### Riješeno

- **Nakon zacrnjenja usred rečenice ostatak rečenice više se ne
  gubi.** Tko je u prozoru uređivača triput otišao na isto mjesto –
  zamijenio, zacrnio, zatim „Vrati izvornik“ – dobivao je izbrisan
  početak rečenice: iz „Za povratne upite obratite se računovodstvu.“
  nastajalo je „obratite se računovodstvu.“, bez upozorenja. Zahvaćeno
  je bilo svako mjesto na kojem je već jednom nešto uklonjeno usred
  retka.

- **Pogreška pri pokretanju više ne povlači za sobom izlaz.** Kad bi
  izgradnja glavnog prozora prekinula, potom se rušio i izlaz preko
  ikone trake zadataka – a ta druga pogreška u izvještaju o pogrešci
  skrivala je pravi uzrok. Sada se program uredno zatvara i iz napola
  izgrađenog prozora, a spremljene postavke pritom ostaju netaknute.

- **„Prije/poslije“ više ne skače na početak dokumenta.** Tko je u
  prozoru uređivača skrolao dolje i prebacio se na izvornik radi
  usporedbe, vraćao se sasvim na vrh – i morao ručno ponovno pronaći
  mjesto. Prikaz sada ostaje na istom retku, u oba smjera.

- **Kod zacrnjivanja na redcima obostranog poravnanja ostajalo je
  posljednje slovo.** Kad tekstualna naredba crta više glifova nego
  što knjižnica za čitanje javlja znakova – kod obostranog poravnanja
  rado proguta razmak – pridruživanje se pomicalo za jedan, pa je iz
  „Dr. Michael Handler aus Willendorf“ nastajalo „[NAME] r aus f“: dva
  ostala slova usred očišćene rečenice (pronađeno u stvarnom zapisniku
  vijeća). Pridruživanje se sada provjerava prema stvarnom sadržaju
  naredbe, gdje je on čitljiv – ondje se više ne nagađa.

- **„Lerchenfelder Gürtel 43/12“ bilo je uklonjeno samo napola.** Uzorci
  adresa nisu poznavali Gürtel, Kai, Lände, Zeile, Markt ni Graben kao
  osnovnu riječ ulice, a kućni broj nije smio nositi dijelove s kosom
  crtom (43/12, kuća/vrata) – broj je ostajao uz rezervirano mjesto.
  Oboje je dopunjeno; bečke i salzburške adrese sada u potpunosti
  otpadaju.

- **Spremljene web stranice ostaju upotrebljive nakon čišćenja.**
  Adrese koje lijeno učitavanje odlaže u data-atributima
  (`data-lazy-src`, `data-lazy-srcset`) bile su zamijenjene kao
  poveznice – na stvarnoj općinskoj stranici šesnaest komada – i slike
  stranice potom se nisu učitavale. Web adrese ondje sada ostaju kao i
  u `src` i `href`; imena, adrese e-pošte i telefonski brojevi u
  data-atributima i dalje se zamjenjuju.

- **Japanski i korejski dokumenti obrađivali su se kao kineski.**
  Prepoznavanje jezika sva je tri pisma bacalo u isti koš, u japanskom
  tekstu (bez razmaka) i korejskom (sa zalijepljenim česticama) nije
  nalazilo funkcijske riječi – i tada je jednostavno uzimalo prvi CJK
  jezik kataloga. Japanski zapisnik vijeća i korejski zapisnik sjednice
  tako su čitani kineskim modelom. Sada odlučuje samo pismo: kana znači
  japanski, hangul znači korejski.

- **Daljnji pogrešni zahvati iz terenskog testa u deset daljnjih
  jezika:** funkcije poput „Primar“, „Gradonačelnik“, „Ordfører“,
  „Başkanı“ ili „Δήμαρχος“ više se ne smatraju osobnim imenima; turske
  oznake polja („Adı“, „Soyadı“) i grčke razgovorne riječi („Ωραία“,
  „Βεβαίως“) više ne otpadaju; brojevi odluka i članaka s datumom
  („323/25-6-2008“, „27 30.09.2024“) više nisu telefonski brojevi; a
  ulomci rečenice s točkom („10.An“, „T.U.EE“, „…pa“) više se ne
  zamjenjuju kao web adrese.

### Novo

- **Izvještaji o provjeri automatski na zahtjev.** Kvačica u postavkama
  (stranica „Program“) nakon svakog čišćenja sama odlaže PDF izvještaj
  o provjeri – s vremenskom oznakom u nazivu, u vlastitoj mapi, nikad
  uz rezultat. Naknadno se list ne može stvoriti; tko ga treba za spis,
  time ga uvijek ima. Zadano je odlaganje isključeno.

- **Zapisnik provjere sada se može uključiti u programu.** Pri učitavanju
  poslovne licence Maskuro jednom pita treba li se voditi zapisnik –
  dokaz vrijedi samo ako radi od početka. Uz to postoji prekidač u
  postavkama (stranica „Program“, vidljiv uz poslovnu licencu ili u
  probnom razdoblju); datoteka zadanih vrijednosti uprave i dalje
  vrijedi i može vrijednost nametnuti kao dosad. Vlastiti redak
  zapisnika „uključeno“ bilježi otkad se vodi – time je dokazan i
  potpisan i sam početak zapisivanja. Zadano zapisnik ostaje isključen.

- **Klapa s kazaljkama pokazuje što je AI razina učinila.** Novi redak
  navodi koliko je nesigurnih nalaza model ocijenio, zadržao i odbacio
  te koliko ih je dodatno pronašao – dosad je njegov rad bio nevidljiv
  ako se nije kliknulo na svaku vrijednost u uređivaču za doradu. Samo
  brojevi, nikad vrijednosti ili obrazloženja; bez rada AI-ja redak se
  ne prikazuje.

- **Vraćanje sada radi i u e-poštama i HTML stranicama.** U `.eml`,
  `.msg` i spremljenim web stranicama rezervirano se mjesto dosad nije
  moglo vratiti – aplikacija je to pošteno govorila, ali baš je
  e-pošta format s najviše osobnih podataka. Sada vraćanje ondje radi
  jednako: iz ploče nalaza, s označenim odabirom i kod anonimiziranih
  rezerviranih mjesta. Nevidljiva HTML grana e-pošte (ono što Outlook
  stvarno prikazuje) pritom se vuče zajedno, kako bi prikaz i poruka
  govorili isto.

- **Ploča nalaza sada vraća i anonimizirane vrijednosti – po
  vrijednosti.** „Poništi zamjenu“ bilo je kod anonimiziranih datoteka
  dosad zaključano, jer „[NAME]“ istodobno stoji za sva imena. Sada
  vraćanje u izvorniku provjerava koje mjesto pripada kojoj vrijednosti
  – u PDF-u prema koordinatama nalaza, u prikazu teksta usporedbom s
  izvornikom – i vraća točno mjesta odabrane vrijednosti. Retci
  preostalih vrijednosti ostaju stajati.

- **I anonimizirana rezervirana mjesta mogu se vratiti pojedinačno.**
  Kod anonimiziranja svi podaci iste vrste zovu se jednako – „[NAME]“
  stoji za svaku osobu, i dosad je zato vrijedilo: pojedinačno vraćanje
  ne ide. Sada se provjerava izvornik, koji uostalom leži uz rezultat:
  u prikazu teksta označite rezervirano mjesto i odaberite „Vrati
  odabir“ – vraća se točno to mjesto s točno njegovom vrijednošću. Ne
  da li se vrijednost iz izvornika nedvojbeno pročitati, aplikacija to
  kaže, umjesto da nagađa. Datoteka pridruživanja pritom i dalje ne
  nastaje.

- **Prozor uređivača se nakon čišćenja sam otvara.** Nijedan alat ne
  pronalazi sve – zato provjeravajući pogled na rezultat pripada
  uobičajenom slučaju, ne dodatnom kliku. Tko to ne želi, isključuje to
  u postavkama pod „Prepoznavanje“ („Prikaži rezultat nakon toga u
  prozoru uređivača“).

### Poboljšano

- **Odabir zemlje sada je zadano „automatski“.** Dosad je tvornički
  vrijedio jezični prostor sučelja – na njemačkom računalu su se tako i
  nizozemski ili francuski dokumenti čistili samo DACH prepoznavačima,
  a adresa poput „Universiteitslaan 1“ ostajala je netaknuta
  (pronađeno u stvarnim, javnim zapisnicima vijeća). Sada se odabir
  zemlje ravna prema jeziku dokumenta; tko je u postavkama napravio
  fiksan odabir, zadržava ga.

- **Manje pogrešno zacrnjenog.** Niz pogrešnih zahvata, izmjereno
  prema ispitnom korpusu i stvarnim zapisnicima sjednica na šest
  jezika, otpada: nazivi tvrtki s pravnim oblikom („Musterfirma GmbH“)
  više se ne smatraju osobom ili mjestom, nego organizacijom; pozdravne
  formule i gole oslovljavanja („Saygılarımızla“, „Buenas tardes“,
  samostojeće „Gospođo“) više nisu imena; funkcije („Gradonačelnik“,
  „Sindaco“, „Alcalde“) ostaju netaknute; brojevi zakona i odluka
  („39/2015“) i iznosi s točkom tisućica („330.000“) više nisu
  telefonski brojevi; počeci rečenica poput „Envíame“ ili „Estarei“
  više ne otpadaju kao ime; nalaz preko praznog retka više se ne broji
  kao ime. Broj računa ostaje sačuvan kao podatak dokumenta – broj
  kupca i broj predmeta i dalje otpadaju.

- **Prije učitavanja AI modela sada stoji čemu služi.** Dijalog
  naknadnog učitavanja navodi zadatke modela – ocjenjivanje graničnih
  nalaza, pronalaženje dodatnih imena, predlaganje pravila i profila –
  i otvoreno kaže da to nije chat asistent. ČPP na isto pitanje
  opširno odgovara („Što AI razina može – a što ne?“), u svim jezičnim
  inačicama.

### Riješeno

- **PDF izvještaji o provjeri iz naredbenog retka sada se mogu
  pretraživati.** Na Windowsu se bezglavi PDF put pokretao bez ijednog
  pisma – svaki znak crtao se kao zamjenski kvadratić, a list nije
  nosio čitljiv tekst: tko je u njemu htio tražiti ili nešto kopirati,
  nije pronalazio ništa. Sada izvještaj u tom slučaju naknadno učitava
  pisma sustava; tekst je ugrađen i čitljiv. Izvještaji iz prozora
  nikad nisu bili zahvaćeni.

- **„Vrati izvornik“ preko više redaka skena ostavljao je crne pruge
  između redaka.** Na stranici pretvorenoj u sliku okvir je čistio
  samo same trake redaka; ostaci ranijeg zacrnjenja ostajali su u
  prazninama između njih. Sada se povučeni okvir potpuno dijeli na
  retke.

- **Drugi okvir preko rezerviranog mjesta ostavljao je crveni
  ostatak.** Rezervirano mjesto gotovo je uvijek šire od riječi koju
  zastupa; tko je nakon toga zacrnio isto mjesto, pogodio je samo
  njegov početak – ostajao je ulomak poput „RIFF_1]“ usred rečenice, a
  vraćanje je potom postavljalo izvorni tekst na to mjesto umjesto na
  mjesto riječi. Zahvaćeno rezervirano mjesto sada uvijek otpada u
  cijelosti.

- **Na zaokrenutoj stranici zacrnjivanje preko rezerviranog mjesta
  brisalo je nepovezanu rečenicu.** Naknadno nacrtano rezervirano mjesto
  pri uklanjanju miješalo se s tekstom ispred njega: ono samo je
  ostajalo, dolazilo je upozorenje „i dalje stoji u dokumentu“ – a na
  drugom mjestu stranice bez zamjene je nestajala rečenica koja s
  okvirom nije imala nikakve veze. Rezervirano mjesto sada se ponovno
  pronalazi prema svom sadržaju; lanac „zamijeni, zacrni, vrati“ time
  radi i na poprečno uvučenim stranicama.

- **Priručnik je u deset jezika još savjetovao `python3-tk`.** U
  otklanjanju pogrešaka stajalo je da na Linuxu možda nedostaje
  tkinter – savjet iz vremena prije Qt sučelja, koji više nikome ne
  pomaže. Sada u svim inačicama stoji isti odlomak kao na njemačkom:
  nedostaju sistemske biblioteke koje Qt treba za prikaz.

- **Licencno poglavlje priručnika u svih šesnaest prijevoda bilo je na
  starom stanju.** U deset jezika i dalje se čitalo da Windows Server
  treba poslovnu licencu s pristupom poslužitelju i da ondje nema
  probnog razdoblja ni besplatne razine – otkad mjesto broji čovjeka, a
  ne stroj, oboje je pogrešno. Uz to je posvuda nedostajala obavijest o
  tome kada se zauzeto mjesto ponovno oslobađa, da se licenca redovito
  potvrđuje i što se pritom prenosi, a aktivacija bez interneta stajala
  je samo kao kratak sažetak bez tri koraka i bez napomene da računalo
  nakon toga godinu dana radi bez veze.

- **Sedam odlomaka o doradi nedostajalo je u deset jezika.** Tko je
  pomoć čitao na danskom, finskom, francuskom, talijanskom,
  nizozemskom, norveškom, poljskom, portugalskom, švedskom ili
  španjolskom, nije pronašao ni pregled stranice za Office datoteke, ni
  „Ručno zacrni“, ni cijeli odjeljak o tome kako program uči iz
  ispravke – zajedno s tablicom triju širina. U „Što se prepoznaje“ tih
  je deset inačica nedostajao put preko oznake u dokumentu.

- **S učitanom licencom program se više nije pokretao.** Umjesto
  prozora dolazilo je „Program se nije mogao pokrenuti“ – i to kod
  svake licence, bilo koje. Uzrok je bio redak u prikazu licence koji
  upozorava neposredno prije isteka probnog roka; on je pristupao
  nečemu što ondje nije bilo dostupno. Bez licence – u probnom
  razdoblju i u besplatnoj razini – pogreška se nije pojavljivala, zato
  je uočena tek sada.

- **Nazivi polja u obrascu ostaju sačuvani.** „Datum rođenja“ i
  „Adresa“ nestajali su zajedno sa svojom vrijednošću: rezervirano
  mjesto stajalo je malo i crveno na mjestu *naziva polja*, a polje
  ispod ostajalo je prazno. Naziv polja ne spada u podatke – sada
  ostaje, a rezervirano mjesto stoji ondje gdje je stajala vrijednost.

- **Naslovi dokumenata na stranom jeziku više se ne smatraju
  imenima.** Iznad talijanskog obrasca stajalo je „FATTURA“, iznad
  španjolskog „PERMISO PARENTAL“ – oba su bila zamijenjena. Popis
  riječi za dokumente poznavao je samo njemačke istovrijednice.

- **Iz računa više ne nestaje nijedna stavka.** „Doplata za materijal
  1 84,00“ smatrano je adresom i zamijenjeno rezerviranim mjestom
  mjesta – dokazu je zatim nedostajao redak. Redak koji završava
  iznosom je stavka, a ne adresa; stvarne adrese („Glavna ulica 1
  120,00“) ostaju netaknute.

### Promijenjeno

- **„Nadziri mapu …“ i naredbeni redak zasad su uklonjeni.** Oba puta
  su izgrađena i rade, ali nijedan od njih nije provjeren u praksi:
  nadzor mape nikad nije prošao Windows provjeru, a naredbeni redak
  daje skripti dva tuceta prekidača koji kod nijednog korisnika nikad
  nisu pokrenuti. Ono što bez nadzora mijenja dokumente ne smije to
  raditi neprovjereno – zato su povučeni dok se provjera ne nadoknadi.
  Stavka izbornika nedostaje, a `--wache` više ne stoji u `maskuro
  --help`.

- **Ostaje otvoreno što samo čita i što je ionako potrebno.**
  Pretraživanje (`--suchlauf`) i naknadna provjera (`--nachpruefen`) na
  naredbenom retku i dalje rade – ne mijenjaju nijednu datoteku. Jednako
  i pokretanje preko Explorera, kontekstnog izbornika, međuspremnika i
  prozora; na tome se ništa ne mijenja.

- **„Preuzmi sa skenera“ sada ima vlastito poglavlje u priručniku.**
  Dosad je stajalo na kraju poglavlja „Nadziri mapu“. Na Macu je
  savjet ondje glasio da se nadgleda mapa; sada glasi da se učitane
  stranice povuku u prozor.

### Riješeno

- **„Vrati izvornik“ preko više redaka uništavao je strukturu.** Okvir
  preko rezerviranog mjesta, nepromijenjenog naziva radnog mjesta i
  druge zamjene cijelo je područje iznova umetao kao **jedan** redak –
  od tri retka nastajao je jedan, a što više nije stalo, postajalo je
  traka. Sada se svaki redak vraća zasebno.

- **A nepromijenjen tekst pritom ostaje netaknut.** Tko povuče preko
  zamjene *i* običnog teksta, dobiva natrag samo zamjenu; ostatak
  se ne dira. I posljednji ostatak starog rezerviranog mjesta pritom
  nestaje – prije je njegova zatvarajuća zagrada ostajala usred
  rečenice.

- **Pri zamjeni više ne ostaju ostaci starog teksta.** U podebljanom
  naslovu nakon toga je stajalo „1. R[BEGRIFF_2]ige [BEGRIFF_1] … che“
  – rezervirano mjesto bilo je ondje, ali uz njega slogovi izvornika.
  Sada se čisti područje koje ste ocrtali, ne samo okviri riječi u
  njemu.

- **Anonimno rezervirano mjesto se više ne vraća pogrešno.** Kod
  anonimiziranja svako ime nosi isti `[NAME]`. Vraćanje je uzimalo prvi
  najbolji unos i upisivalo ga na svako mjesto nalaza – iz „Georg
  Aigner“ nastajao je „Anna Musterfrau“, dakle pogrešno ime u
  dokumentu. Sada ondje stoji da se više ne može reći koji je podatak
  bio mišljen; dokument ostaje netaknut.

### Novo

- **„Vrati izvornik“ sada djeluje i na rasteriziranoj stranici.**
  Pretvorena li je stranica u sliku, dosad je dolazilo odbijanje:
  vraćeni tekst došao bi ispod slike stranice. Sada se mjesto na slici
  čisti i tekst se piše na njega – kao rezervirano mjesto na skenu.
  Sadržaj pritom dolazi iz izvorne datoteke, a ona nije rasterizirana.

- **„Vrati odabir“ sada stoji kao vlastiti gumb.** To je već i prije
  radilo, ali samo ako se slučajno označilo rezervirano mjesto i
  pritisnulo „Zamijeni odabir“ – funkcija koja se pronalazi samo
  slučajno za korisnika ne postoji.

### Promijenjeno

- **U čistom tekstu, CSV-u i Outlook porukama više nema „Zacrni
  odabir“.** Ti formati ne mogu nositi traku; gumb je ondje postavljao
  rezervirano mjesto i to i govorio – ali gumb koji radi nešto drugo
  od onoga što se zove ondje ne pripada.

- **Alat sada kaže kad na tom mjestu ne može ništa učiniti.**
  Rezervirano mjesto se ne može ponovno zamijeniti, iznad zacrnjenja se
  ne postavlja rezervirano mjesto, a gdje već stoji izvornik, nema što
  vratiti. Dosad su ti potezi radili nešto što je izgledalo kao
  učinak, ali ga nije bilo.

## 0.10.29-alpha.20260817 – 17. kolovoza 2026.

### Riješeno

- **U prozoru uređivača sada djeluje svaki okvir koji povučete.** Tko je
  na istom mjestu radio dvaput – najprije zamijenio, zatim zacrnio, pa
  vratio izvornik –, njegov drugi i treći potez nestajali su bez glasa:
  još uvijek dohvatljiv okvir prethodnog poteza presreo ga je. Isto se
  događalo kod promjene alata, gdje je čak i stari alat tiho nastavljao
  djelovati.
- **Preusko povučen okvir kaže da je preuzak.** Dosad je pregled riječi
  zasvijetlio crveno, a nakon otpuštanja bez ikakve poruke nije se
  dogodilo ništa.

- **Outlook poruke se napokon mogu dorađivati.** `.msg` je u prozoru
  uređivača prikazivao „Ovaj se format ovdje ne može prikazati“ – bio je
  jedini podržani format bez ikakvog puta za ručnu doradu. Sada u
  prikazu stoje imenovani pošiljatelj, primatelj, predmet i tekst poruke
  te se mogu označavati i zamjenjivati kao u svakom drugom tekstualnom
  formatu.

- **„Zamijeni odabir“ u e-pošti ostaje uz odabir.** Tko je označio ime u
  tekstu poruke, gubio je uz to i pošiljatelja i primatelja iz
  zaglavlja, a poruka je navodila drugo rezervirano mjesto od onog koje
  je stajalo u tekstu. Sada se označena vrijednost zamjenjuje posvuda –
  i u pošiljatelju, ako ondje stoji – a ništa se drugo ne dira.

- **Okvir preko više redaka više ne uništava tekst.** Dosad je nastajalo
  jedno jedino rezervirano mjesto na jednom mjestu: od zahvaćene riječi
  ostajao je prilijepljen ostatak, a iz drugog retka tekst je nestajao
  bez ikakve zamjene – ni rezervirano mjesto, ni traka, samo praznina.
  Sada svaki redak dobiva vlastito rezervirano mjesto s vrijednošću koja
  je ondje stvarno stajala.

- **„Vrati izvornik“ sada djeluje i nakon zacrnjenja.** Prozor je javljao
  uspjeh, a tekst se nikad nije vratio: crna traka brojala se kao
  prepreka, pa za vraćeni tekst više nije bilo mjesta. Traka sada
  ustupa mjesto, a vraćeni tekst stoji crno kao običan tekst – ne
  crveno kao rezervirano mjesto.

- **„Vrati izvornik“ na netaknutom mjestu više ne radi ništa.** Tko je
  povukao okvir preko teksta na kojem ništa nije bilo promijenjeno,
  dobivao je tekst uklonjen te ponovno umetnut manji i pomaknut – uz
  poruku o uspjehu. Sada ondje stoji da nema što vratiti.

### Novo

- **I u Wordu, Excelu, PowerPointu, OpenDocumentu i tekstu moguće je
  zacrniti.** Dosad je ondje postojalo samo „Zamijeni odabir“; traka je
  bila rezervirana za PDF pregled, bez ikakvog razloga za to. Gdje traku
  nije moguće prikazati – u čistom tekstu i u Outlook poruci – vrijednost
  se kao i dosad zamjenjuje rezerviranim mjestom, i to tako piše i u
  poruci.

- **Označavanje rezerviranog mjesta ga vraća.** U prikazu teksta (Word,
  Excel, PowerPoint, OpenDocument, tekst) sada je dovoljno označiti
  rezervirano mjesto i pritisnuti „Zamijeni odabir“: izvorna vrijednost
  se vraća. Dosad je prozor za to upućivao na ploču nalaza.

- **Govornici u zapisniku sastanka prepoznaju se i kad je njihovo ime
  ujedno obična riječ.** „Gruber: Preuzimanje se obavlja sljedeći tjedan.“
  bilo je zamijenjeno, „Bauer: Slažem se.“ ostajalo je netaknuto –
  prezime za prepoznavanje izgleda kao imenica. Napomenski retci istog
  oblika ostaju netaknuti: iz „Pozor: Postrojenje treba isključiti.“ ne
  nastaje ime.

- **„Koristite najnoviju inačicu“ govorilo se i kad se uopće nije moglo
  provjeriti.** Ako poslužitelj ažuriranja odbije upit – jer je s iste
  internetske adrese stiglo previše upita ili jer je sam trenutačno u
  smetnji – program je ostajao na svojoj staroj inačici i tvrdio da je
  najnovija. Točno to dogodilo se 17. kolovoza na Macu: 0.10.25 je
  ostala, dok je 0.10.28 satima bila spremna.

  Sada prozor kaže što se događa, navodi vrijeme sljedeće provjere – i
  izričito upozorava da **nije** utvrđeno je li vlastita inačica
  najnovija.

  Uzrok najčešće nije u vlastitom računalu: kod mnogih priključaka
  brojni korisnici dijele istu internetsku adresu, a poslužitelj ih broji
  zajedno. Zato Maskuro u tom slučaju traži popis inačica **drugim
  putem** i uglavnom svejedno pronalazi nove inačice. Ako odbijanje
  ostane, poslužitelj se ostavlja na miru do navedenog vremena – čak i
  ako se gumb ponovno pritisne; ponovno pritiskanje samo produljuje
  blokadu.

- **Količine se više ne smatraju nazivima mjesta.** U ugovoru o radu
  „Vier-Tage-Woche“ (četverodnevni tjedan) nestajao je iza rezerviranog
  mjesta za mjesto – posred predmeta ugovora. Takve spojnice broja i
  crtice (“Drei-Punkte-Plan“, “24-Stunden-Dienst“) sada ostaju netaknute.
  Adrese su iz toga izuzete: “Zwei-Brüder-Weg“ i dalje se zamjenjuje.

## 0.10.28-alpha.20260817 – 17. kolovoza 2026.

### Promijenjeno

- **Licencna mjesta sada se stvarno broje.** Dosad se nijedno radno
  mjesto nikada nije prijavilo kod licencne službe – licenca za deset
  mjesta radila je na proizvoljno mnogo računala, a da to nitko nije
  znao. Novo: računalo koje pokreće program zauzima jedno mjesto; mjesto
  se nakon **sedam dana bez pokretanja** samostalno oslobađa, tako da
  pokvareni uređaj ili djelatnik koji je otišao ništa trajno ne
  blokira.

  Manji prekoračaj pritom se **samo prikazuje, a ne blokira**: do deset
  posto iznad kupljenog broja svi i dalje rade – novi prijenosnik uz još
  prijavljeni stari ne treba biti slučaj za korisničku podršku. Tko
  dođe iznad toga, pada natrag na besplatnu razinu i to mu se javlja;
  računala koja su bila tu prva ništa od toga ne primjećuju.

- **Kupljena licenca se redovito potvrđuje.** Ne uspije li to **30 dana**,
  toliko dugo ponovno vrijedi besplatna razina, dok potvrda ponovno ne
  uspije. Ništa se ne isključuje, a tjedan dana unaprijed napomena stoji
  u prozoru. Čim računalo ponovno dobije internet, to se riješi samo od
  sebe. Probno razdoblje i besplatna razina i dalje ne javljaju ništa –
  tko nikad ne kupi, nikad ne telefonira.

- **„Aktiviraj bez interneta“ napokon djeluje.** Aktivacija se dosad
  provjeravala i pohranjivala, ali je nakon toga nitko više nije
  čitao – na prava ništa nije mijenjala. Sada je izlaz za računala bez
  pristupa mreži: vrijedi **godinu dana**, nakon čega se svježim
  kodom zahtjeva dobiva nova. Uređaj s internetom za to je potreban
  jednom godišnje – samo računalo ostaje trajno izvan mreže.

- **Aktivacija sada ide i preko korisničkog računa** – pod „Moje
  licence“ na web-stranici. Ondje uz to stoji koja računala vise o vašoj
  licenci i kada im se mjesta ponovno oslobađaju; to se dosad nigdje
  nije vidjelo. Stranica bez prijave ostaje za sve koji nemaju pristup
  trgovini – ona za to dodatno traži adresu e-pošte iz narudžbe, kako
  sam licencni ključ ne bi bio dovoljan.

- **A u prozoru sada stoji kamo s kodom zahtjeva.** Papirni put govorio
  je „unesite na uređaju s internetskom vezom“ i nije navodio adresu;
  stranica za aktivaciju postoji odavno, ali s nje nigdje nije bilo
  poveznice. Sada u dijalogu, priručniku i ČPP-u stoji
  **maskuro.com/lizenz-freischalten** – i na web-stranici ispod
  licencnog ključa.

- **Gumb „Aktiviraj bez interneta …“ ostaje vidljiv**, i kad licenca
  trenutačno ne vrijedi. Prije je nestajao zajedno s njom – dakle baš
  onda kad je potreban.

- **„Sva mjesta zauzeta“ sada govori istinu.** Napomena je završavala s
  „Program nastavlja raditi nepromijenjeno“; to više ne vrijedi ako
  nijedno mjesto nije dodijeljeno. Sada ondje stoji da do daljnjega
  vrijedi besplatna razina.

### Novo

- **Pri uključivanju čišćenja međuspremnika sada stoji da je potrebno
  pregledati.** Poruka od tada navodi istu rečenicu koja stoji i uz
  rezultat datoteke: Maskuro ne prepoznaje u svakom slučaju sve osobne
  podatke.

  Ovdje ona teži više nego drugdje. Kod datoteke rezultat se vidi prije
  nego što se proslijedi. Kod međuspremnika ne – kopira se, lijepi, i
  očišćeni tekst već stoji u prozoru pošte. Poruka zato izričito kaže da
  treba pregledati **zalijepljeni** tekst.

  Pojavljuje se pri uključivanju, ne kod svakog kopiranja: ono što bi
  se pojavilo pedeset puta dnevno, nakon trećeg puta više nitko ne
  čita.

- **„Kopiraj sve“ ispod popisa – a „Ukloni sve“ se pomiče dalje.** Novi
  gumb odjednom stavlja sve gotove rezultate u međuspremnik, za
  privitak uz poruku ili lijepljenje u drugi program. Dosad je to išlo
  samo preko izbornika i tamo samo za **označene** retke – tko je
  mislio na sve, morao je najprije pritisnuti Ctrl+A.

  Pritom je redak gumba nanovo poredan: lijevo stoji ono što nešto
  dodaje, desno iza razmaka ono što nešto uklanja. „Ukloni sve“ dosad je
  stajalo neposredno uz „Dodaj …“, a pogrešan klik koštao je cijeli
  popis. Isto pravilo vrijedi od 13. kolovoza već za svaki gotovi
  redak.

- **Radna mjesta bez interneta sada svoje jezične modele dobivaju iz
  vlastite kuće.** Čišćenje je ondje oduvijek radilo bez veze – naknadno
  učitavanje jezičnog modela ne, a model teži nekoliko stotina
  megabajta.

  Uprava jednom na računalu s vezom slaže datoteke i postavlja ih na
  zajedničko mjesto, u rollout ili na USB. Mjesto se unosi središnje
  (polje `modellquelle` u `vorgaben.json` ili varijabla okruženja
  `MASKURO_MODELLQUELLE`). Od tada svako naknadno učitavanje – jezični
  modeli, japanski rječnik i Visoka razina – najprije posluži sebe
  odande, a na mrežu ide tek ako datoteka nedostaje.

  Kontrolne vrijednosti pritom vrijede nepromijenjene. Kućno dijeljenje
  datoteka često je lakše opisati nego mrežno izdanje; ne smije postati
  lakši put do podmetnutog modela.

  Kako takav sustav nastaje i kako rade licenca i aktivacija bez
  interneta, stoji u `OFFLINE.md`.

- **„Vrati izvornik“ – okvir vraća ono što je previše uklonjeno.** U
  prozoru uređivača postoji novi alat: povucite okvir preko mjesta, i
  tekst opet stoji ondje kako je stajao u izvorniku.

  Time se zatvara praznina koju je ostavljala ploča nalaza. Ondje se
  zamjena mogla poništiti samo ako je njezino rezervirano mjesto bilo
  jednoznačno – dakle ne kod anonimizacije, gdje „[IME]“ stoji uz svaki
  takav podatak, i uopće ne kod zacrnjenih mjesta, gdje ne ostaje
  rezervirano mjesto. Baš se ondje nakupljaju pogrešni zahvati:
  „Korisnik“, „Inventurni broj“, „Potpis“ rado se smatraju imenima.

  Okvir ne treba rezervirano mjesto: **mjesto** dolazi iz pravokutnika,
  **sadržaj** iz izvorne datoteke – iste one koju pokazuje prekidač
  prije/poslije. Anonimizirano ili pseudonimizirano time više nije
  važno.

  Vraćeni tekst stoji crno, ne crveno: opet je čitljiv tekst, a ne
  rezervirano mjesto. Iz popisa nalaza unos nestaje tek kad njegovo
  rezervirano mjesto **nigdje** više ne stoji u dokumentu – ako je ista
  vrijednost zamijenjena na više mjesta, ostaje za preostala.

  Na stranici pretvorenoj u sliku alat odbija i objašnjava zašto:
  vraćeni tekst došao bi ispod slike stranice i ne bi se vidio.

### Riješeno

- **Pri sklapanju „Detalja“ i „Kazaljki“ ostajali su ostaci slike na
  zaslonu.** Sklopljeno, dio sadržaja gurao se pod donji rub prozora i
  ondje ostajao iznad pozadine, dok se nešto drugo preko toga ne
  nacrta.

  Oba područja imaju najmanju visinu, kako bi otvorena bila upotrebljivo
  velika. Pokret pri sklapanju spuštao je samo najveću visinu – a ispod
  svoje najmanje visine područje se ne skuplja. Sadržaj je tako ostajao
  visok 200 točaka, dok se prozor već stisnuo na 24; razlika je stajala
  ispod ruba. Sada se najmanja visina za trajanje pokreta izmiče i
  potom se vraća.

- **Prozor je pri ponovljenom sklapanju i rasklapanju postajao sve
  manji.** Pri rasklapanju raste najviše do 92 % visine zaslona; ako je
  prostora malo, raste manje nego što je potrebno. Pri sklapanju je
  ipak oduzimao puni iznos natrag. Sada se vraća točno onoliko koliko je
  rasklapanje koštalo.

- **Ostatak zacrnjenog podatka mogao je ostati vidljiv.** U životopisu
  su od „*30.12.1991“ u rezultatu ostajali čitljivi znakovi „*30.1“ –
  dakle dan i početak mjeseca datuma rođenja. Program je čak primijetio
  ostatak i zato stranicu pretvorio u sliku; upravo je to pogoršalo
  stvar, jer time ostatak više nije bio pretraživ, ali je i dalje bio
  čitljiv – i više se nije mogao ispraviti.

  Uzrok je ležao između dviju provjera. Oštrija od njih dviju provjerava
  stoji li u površini uklonjenog podatka još nešto što ondje ne pripada;
  svoj nalaz javlja kao skup znakova, jer se redoslijed čitanja pri
  zamjeni pomiče. Rezervni put, koji takva mjesta premazuje prije
  pretvaranja, tražio je taj skup znakova kao tekst na stranici – i
  nikad ga nije pronašao. Ništa zato nije bilo premazano. Mjesto je bilo
  poznato cijelo vrijeme i sada se prosljeđuje, umjesto da se ponovno
  traži.

  Pogođena je bila svaka stranica čiji je ostatak pronašla isključivo ta
  provjera – neovisno o vrsti datoteke i jeziku.

- **Na poprečno uvučenom skenu prepoznavanje teksta nije ništa
  pronalazilo.** Tko list stavi bočno u uvlak, dobiva datoteku u kojoj
  pismo stoji zaokrenuto za 90 stupnjeva. Dosad Maskuro u njoj nije
  pročitao **nijedan jedini** podatak – i datoteka je nakon toga
  izgledala neupadljivo: ništa nije pronađeno, dakle ništa nije
  javljeno, a adresa je i dalje čitljivo stajala na slici. Sada
  prepoznavanje teksta samo uspravlja stranicu; na kontrolnoj slici
  ponovno padaju svi podaci.

  Otvoreno navedene dvije granice: list koji stoji **naopako** (180
  stupnjeva) i dalje se ne čita, a kod vrlo lošeg skena uspravljanje ne
  pomaže – ondje je premalo čitljivo da bi se položaj uopće odredio.
  Svakoj slici za to treba oko petinu dulje.

### Promijenjeno

- **„Automatski instaliraj“ sada znači ono što radi.** Kvačica u
  postavkama obećavala je više nego što je ispunjavala: sama preuzima
  novu inačicu i pokreće instalaciju – ona pak teče **vidljivo** i traži
  potvrdu, na Windowsu uključujući upit Kontrole korisničkog računa. Tko
  je pročitao „automatski“, računao je s računalom koje se preko noći
  samo ažurira, a ujutro je stajao pred čarobnjakom za instalaciju.
  Kvačica se sada zove „Samostalno preuzmi ažuriranja i pokreni
  instalaciju“, s rečenicom ispod koja objašnjava što to znači. U
  ponašanju se ništa ne mijenja – da se Maskuro ne mijenja neopaženo,
  namjerno je i tako ostaje.

## 0.10.27-alpha.20260817 – 17. kolovoza 2026.

### Novo

- **Novo: `--ersetzen` za povezivanje s odvjetničkim softverom.** Rezultat
  zauzima mjesto izvorne datoteke, umjesto da nastaje pored nje. Time
  odjava i prijava odvjetničkog softvera („Otvori i uredi“ u e-spisu)
  radi bez ikakvog sučelja: softver preda datoteku i dobiva je natrag
  očišćenu na istom mjestu.

  **Ovaj prekidač zaobilazi prvo temeljno načelo**, i zato postoji samo
  na naredbenom retku – ne u prozoru – i samo ako to vaša uprava
  dopusti (unos `ersetzen` u datoteci zadanih vrijednosti). Bez
  dopuštenja poziv se prekida i kaže zašto; tiho stvaranje druge
  datoteke bilo bi gora pogreška, jer bi se tada natrag prijavila
  nepromijenjena datoteka.

  Zapisuje se najprije susjedna datoteka; tek kad je gotova, zauzima
  mjesto izvornika. Prekid ili pogreška time ostavljaju izvornik
  **bajt po bajt nepromijenjen** i ne ostavljaju nikakav ulomak. U
  zapisniku provjere zamjena stoji kao vlastito polje – provjeritelj
  mora znati da neočišćena inačica ovdje više ne leži.

- **Priručnik sada objašnjava Windows upozorenje pri prvom pokretanju.**
  Novi prvi odjeljak „Windows upozorava pri prvom pokretanju – što
  učiniti“, s dvije slike i tri koraka: „Više informacija“ je mala
  poveznica, ne gumb – baš na tome se većina zaustavi –, zatim
  „Ipak pokreni“.

  Da ondje piše „Nepoznat izdavač“, cijela je poruka upozorenja: paketi
  se trenutačno isporučuju bez certifikata. Smatramo ispravnijim to
  objasniti, nego prešutjeti.

- **Put natrag sada primjećuje kad tekst i pridruživanje ne pripadaju
  zajedno.** Tko umetne odgovor u drugi predmet, dosad je dobivao tuđa
  imena u ispravnom tekstu – bez pogreške, bez poruke, samo pogrešno.
  Maskuro sada pamti koja je rezervirana mjesta uopće stvorilo
  posljednje izvođenje i prijavljuje svako koje ne pripada. Ne potječe
  li nijedno od njih iz posljednjeg izvođenja, ništa se ne umeće, a
  prozor kaže zašto – umjesto da kao dosad pretpostavi istekao rok.

  **Granica ostaje, i ona stoji i u priručniku:** rezervirana mjesta
  broje se po izvođenju, prvo ime u svakom dokumentu zato se zove
  `[NAME_1]`. Nosi li tuđi tekst samo takva rezervirana mjesta, zamjena
  se ne može prepoznati.

- **PDF se sada može ispisati crno-bijelo.** Kvačica kod načina rada
  pretvara svaku stranicu u crno-bijelu sliku – s nevidljivim
  tekstualnim slojem ispod, dakle i dalje čitljivu i pretraživu. Za
  slanje preko beA i sličnih puteva s čvrstim granicama veličine: preko
  našeg mjernog korpusa u prosjeku **68 % manje** (naredbeni redak:
  `--monochrom`).

  **Koliko to donosi, ovisi o dokumentu** – i to stoji uz kvačicu:
  skenirano i slikovno sadržajno se jako smanjuje, vitak tekstualni
  dokument bez ugrađenih pisama može čak postati veći. Isprobajte na
  jednoj datoteci prije nego što uključite za cijelu skupinu.

  Cijena: svaka stranica se iznova računa – kod tisuću stranica to traje
  minute. A slike gube sve između crne i bijele; za tekst je to
  svejedno, za fotografiju ne.

- **Popis nalaza u prozoru uređivača sada broji zajedno s vama.** Iznad
  popisa stoji „5 nalaza“, a čim filtrirate, „1 od 5 nalaza“. To je
  razlika između „filtrirao sam“ i „ima ih pet, i sve sam vidio“ –
  zahvat kojim se provjerava je li ime uistinu posvuda zamijenjeno.

- **Zapisnik provjere sada se može pretraživati i filtrirati.** Prikaz
  pod „Datoteka → Zapisnik provjere“ dosad je imao tablicu i ništa
  drugo – kod mjeseca s tri tisuće izvođenja vidjelo se da se mnogo
  dogodilo, ali ne što.

  Novi su **polje pretrage**, **tri filtra** (postupak, rezultat, vrsta)
  i **listanje**, uz to tri stupca koja prije nisu postojala:
  **Postupak** (zacrnjeno ili zamijenjeno), **Pouzdanost** i
  **Trajanje**. Iznad popisa stoji koliko se trenutačno vidi i koliko
  filtar sakriva.

  „Spremi kao CSV …“ sada ispisuje **ono što stoji ondje** – tko je
  filtrirao, dobiva filtrirano, a poruka navodi broj.

  Crta kod pouzdanosti ili trajanja znači da za taj redak ništa nije
  izmjereno – primjerice jer je stariji od ove funkcije. Te se
  vrijednosti **ne** naknadno izračunavaju. Filtar po korisniku i dalje
  ne postoji; pojedinačan redak pretraga ipak pronalazi.

### Uklonjeno

- **Napomena o transparentnosti u prozoru „O ovom programu“ opet je
  nestala.** Stajala je ondje od 0.10.22-beta.1 i govorila da je
  aplikacija razvijena uz potporu umjetne inteligencije. Nigdje se ne
  zahtijeva, a baš u aplikaciji za zaštitu podataka neki su je čitali
  kao izjavu o načinu rada – dakle kao da dokumenti idu prema usluzi u
  mreži. Čisti se i dalje isključivo na vlastitom računalu; to stoji
  ondje gdje pripada, u kartici „Zaštita podataka“.

### Riješeno

- **Program je vlastitu ikonu zamjenjivao lošijom.** Tko je kontekstni
  izbornik upisao iz programa, nakon toga je imao drugačiji štit u
  traci zadataka nego nakon instalacije – sličan, ali s trakama
  poravnatim lijevo umjesto sredinom i vidljivo grublji. Iza toga je
  stajao provizorij: ne pronađe li program predložak ikone, sam ga
  crta. Zamišljeno je to bilo za slučaj da **nijedna** ikona ne
  postoji; zapravo je crtao i kad su priložene odavno ležale – i
  prepisivao ih. U inačici instaliranoj iz Setupa nema predloška, pa
  je ondje pogodilo svakoga. Postojeće ikone sada ostaju netaknute.

  **Već zahvaćene instalacije ne dobivaju ispravnu ikonu same od
  sebe** – za to jednom instalirajte ponovno.

- **„Broj objekta: OB-4711-22“ vrijedio je kao korisničko ime.**
  Prepoznavač korisničkih imena provjeravao je svoje oznake bez granice
  riječi ispred – time je zahvatao **svaku** riječ koja završava na
  jednu od njih: broj objekta, broj vozila, broj uređaja. Vrijednost
  iza toga se uklanjala, iako s korisničkim imenom nema veze.

  Sastavljenice koje su stvarno mišljene – „korisnička oznaka“,
  „prijavna oznaka“ – stoje pojedinačno u popisu i i dalje se
  pronalaze.

- **Na engleskom, grčkom, japanskom i korejskom šesnaest rezerviranih
  mjesta u rezultatu stajalo je na njemačkom.** Tko je sučelje postavio
  na jedan od ta četiri jezika, za novije vrste podataka dobivao je
  njemačke oznake upisane u dokument – iz lozinke je nastajalo
  `[ZUGANGSDATEN_1]` umjesto `[CREDENTIALS_1]`, iz dijagnostičke šifre
  `[DIAGNOSESCHLUESSEL_1]` umjesto `[DIAGNOSIS_CODE_1]`. Zahvaćeni su
  bili zdravlje, dijagnoza, lijek, dijagnostička i ljekarnička šifra,
  vjera, sindikat, političko mišljenje, kazneno pravo, pristupni
  podaci, korisničko ime, podaci kartice, koordinate, zanimanje, iznos
  i obilježje.

  Preostalih 44 jezika taj propust nikad nisu imali: svoje oznake
  dohvaćaju iz jezičnih datoteka, u kojima su te vrste od početka
  stajale. Baš ta četiri jezika iz drugog razloga vode vlastite
  tablice – njihovo pismo ne preživi PDF znakovni skup, pa ondje stoje
  latinične oznake – i u tim tablicama nove vrste jednostavno
  nedostaju.

  Uočeno je pri prevođenju stranice kataloga: web stranica je
  engleskim čitateljima obećavala oznake koje program nije pisao.
  Provjerni kamen sada uspoređuje sve četiri tablice s popisom svih
  oznaka koje uopće mogu nastati.

- **Prozor pravila više se ne otvara premalen za svoj sadržaj.** U
  kartici „Vlastiti uzorci pretrage“ objašnjavajući redak čarobnjaka
  („Traži se: …“) ležao je napola iza polja „Probni tekst“ – baš rečenica
  po kojoj se bez poznavanja regularnih izraza provjerava traži li
  vlastito pravilo pravu stvar. Prozor je imao fiksnu najmanju veličinu
  iz vremena s manje kartica i mogao se povući ispod onoga što stane.
  Sada se ravna prema svom sadržaju i otvara samo onoliko malen koliko
  sve ostaje čitljivo.

- **Imena u formulama tablice više ne ostaju netaknuta.** Stanica ima
  više od jednog mjesta za tekst, a dosad se čistilo samo jedno. Stoji
  li ime u formuli – `="Gospođa "&"Sieglinde Ortner"` – ili je bilo
  posljednji izračunati rezultat formule, ostajalo je nepromijenjeno u
  radnoj knjizi, iako je ista osoba u susjednoj stanici bila
  zamijenjena. Tko klikne na stanicu, čitao ga je u traci uređivanja.

  Oboje se sada zamjenjuje. Dira se samo ono što stoji između
  navodnika: upute na stanice, nazivi funkcija i nazivi listova ostaju
  netaknuti, `=SUMA(K2:K6)` i dalje računa. Jer isto ime posvuda dobiva
  isto rezervirano mjesto, i `=SUMIF(A:A;"Huber";B:B)` i dalje
  pronalazi svoje retke.

- **Dijagrami više ne prikazuju imena.** Dijagram sprema vlastitu kopiju
  oznaka svojih osi – crta se i kad su izvorne stanice odavno prazne.
  Ispod stupaca zato je i dalje stajalo pet osobnih imena, dok je
  tablica iznad bila čista. Vrijedi za tablice **i** prezentacije.

- **Imenovani rasponi s fiksnim tekstom se čiste.** Imenovan raspon
  umjesto upute na stanicu može sadržavati fiksni tekst; stajalo li
  ondje ime, ostajalo je. **Naziv** raspona i dalje ostaje – na njega
  upućuju formule, a preimenovanje bi dalo pogrešku reference. Kao kod
  naziva lista, prijavljuje se, ne zamjenjuje.

- **Jednom prepoznat datum rođenja nestaje u cijelom dokumentu.** Datum
  sam po sebi ništa ne govori – tek ga riječ polja čini datumom
  rođenja, i baš zato datum računa ostaje netaknut. Stajao li isti
  podatak u istom dokumentu drugi put bez te riječi – u naslovu slike,
  u ispunjenom polju obrasca – ostajao je ondje, iako je nekoliko
  redaka iznad „rođen dana …“ bilo nedvojbeno prepoznato. Prenosi se
  samo ono što je u **ovom** dokumentu već prepoznato kao datum
  rođenja; i dalje se ništa ne pogađa.

- **Strukturirani podaci na web stranicama odaju svoj datum rođenja.**
  U JSON-LD bloku za tražilice datum stoji pod ključem `birthDate` –
  ključ kaže što je to, kao inače zaglavlje stupca. Sada se čita
  zajedno; „Birthday“ i „Birthdate“ time vrijede kao oznaka polja i u
  obrascima.

- **Datum rođenja i broj osoblja pronalaze se i u tablicama.** U stanici
  stoji samo gola vrijednost – `14.03.1988`. Što ona znači, kaže samo
  zaglavlje stupca, a ono stoji mnogo redaka iznad. U Excelu se to već
  čitalo; u LibreOffice tablicama i u CSV datotekama ne, i ondje je
  datum rođenja zato ostajao.

  Oba sada čitaju zaglavlje – **ali samo ako je ono samo oznaka
  polja**. Ispod „Datum rođenja“ datum otpada, ispod „Datum računa“ ili
  „Datum isporuke“ ne. To je namjerno oprezno tumačenje: zaglavlje
  poput „Ime“ iznad proizvoljne napomene već bi jednom postavilo
  rezervirano mjesto preko rečenice u kojoj uopće ne stoji osoba.

### Riješeno

- **Očišćen CSV ostaje tablica.** Prepoznavanje čita redak CSV-a kao
  rečenicu i zato je povremeno svoje nalaze polagalo i preko
  točke-zareza. Rezervirano mjesto gutalo je razdjelnik, redak je
  nakon toga imao stupac manje, a datoteka se više nije mogla otvoriti
  kao tablica. Mjesta nalaza sada završavaju na granici stanice, a
  navodnici maskiranja ostaju sačuvani. Zahvaćene stanice se nakon toga
  još jednom čitaju zasebno – inače bi susjedna stanica ostala
  neočišćena, koju je predugačak nalaz prekrivao.

- **Komentari u prezentacijama.** Bilješka na rubu slajda – često baš
  mjesto na kojem stoji „Molim nazvati gospođu … prije sjednice“ –
  ostajala je netaknuta, zajedno s imenom onoga tko ju je napisao. U
  Excelu se oboje odavno čistilo; PowerPoint tekst komentara i autora
  odlaže drugačije, i to je bilo previđeno. Odnosi se na oba oblika:
  stariji i onaj koji PowerPoint piše od 2019. – ondje i poslovnu
  adresu e-pošte koja visi uz autora. Inicijali koje PowerPoint
  prikazuje na oblačiću također se uklanjaju.

- **LibreOffice datoteke: formula, korisničko polje, autor bilješke.**
  Ono što se u Excelu već čistilo, u ODS tablici je ostajalo – ondje
  formula ne stoji kao vlastiti element, nego kao svojstvo stanice, i
  ime u njoj preživljavalo je. Pri sljedećem otvaranju LibreOffice ga
  je ponovno izračunavao.

  Uz to tri daljnja mjesta: vrijednost **korisničkog polja** u
  OpenDocumentu stoji jednom gore u deklaraciji, a u tekstu se samo
  dohvaća – dosad se zamjenjivao samo dohvat, pa se pri otvaranju
  vraćala stara vrijednost. **Autor bilješke** i praćene izmjene
  ostajali su netaknuti. A u **tablici** praćenje izmjena uopće se
  nije čistilo – za razliku od tekstualnog dokumenta – pa su obrisani
  sadržaji stanica zajedno s imenom obrađivača ostajali sačuvani.
  Upute na stanice i formule zbroja pritom ostaju netaknuti.

- **Spremljene web stranice odaju svoje atribute.** Stranica daleko od
  toga pokazuje sve što sadrži. Ispunjeno polje obrasca nosi unos u
  `value`, JavaScript sučelje odlaže svoj skup podataka u `data-…`, a
  blok za tražilice (JSON-LD) ga u potpunosti i pravilno ponavlja: ime,
  datum rođenja, adresa, telefon. Vidljivi tekst bio je očišćen, sve to
  je i dalje stajalo.

  Sada se čiste i ta mjesta, uz to `aria-…` (ono što čitač zaslona
  izgovara), `placeholder`, `summary` i predloženi naziv datoteke
  poveznice. JSON-LD blok se pritom čita kao podaci i ostaje valjan –
  njegovi ključevi i rječnik ostaju, samo vrijednosti odlaze. Obični
  JavaScript i dalje se ne dira.

- **Slike gube svoje dodatne podatke i bez EXIF-a.** Fotografija uz sebe
  nosi ime fotografa, vrijeme snimanja i GPS koordinate mjesta snimanja
  – kod oglasa za stan to odaje adresu, čak i kad je u tekstu nema. To
  se uklanjalo dok je slika imala EXIF. Bili li podaci pohranjeni
  **samo** kao XMP (tako spremaju Lightroom i Photoshop) ili kao
  tekstualni blok u PNG-u (`Author`, `Comment`), slika je ostajala
  posve netaknuta. Sada se oboje prepoznaje i uklanja – i kod slika
  koje se nalaze u dokumentu i u njemu ostaju. Orijentacija i dalje
  preživljava, a slika bez dodatnih podataka se nepotrebno ne sprema
  iznova.

- **Ciljevi poveznica u tablicama, prezentacijama i Word dokumentima.**
  Kamo poveznica vodi ne stoji u tekstu, nego u vlastitom spremištu
  datoteke. Adresa e-pošte iza „Napiši poruku“ zato je preživljavala
  čišćenje netaknuta, dok je ista adresa u tekstu bila zamijenjena.
  `mailto:` i `tel:` se sada ondje čiste jednako kao u spremljenim web
  stranicama.

### Novo

- **Liječnička pisma više se ne vraćaju oštećena.** Dosad je
  prepoznavanje imena smatralo ljekove osobnim imenima: iz
  „Metoprololsuccinat“ nastajao je `[NAME]`, iz „Ramipril“ `[ORT]`. Plan
  terapije bio je time neupotrebljiv – dok su dijagnoze ostajale
  netaknute, dakle upravo obrnuto. Izmjereno, to je pogađalo **63 %
  aktivnih tvari** i **53 % kliničkih stručnih pojmova**, i to ne samo
  na njemačkom: kroz sedam jezika 74 %, na talijanskom svi provjereni.

  Maskuro sada poznaje medicinski rječnik i ostavlja ga na miru. Ostaje
  6 % umjesto 43 % (njemački) i 1 % umjesto 74 % (kroz jezike). Stoji
  li ispred oslovljavanje – „Poštovana gospođo …“ – ime ostaje ime, čak
  i kad se slučajno zove kao lijek.

- **Bolesti i lijekovi se mogu ukloniti – ako to želite.** Nova kvačica
  u postavkama: „Ukloni i bolesti i lijekove“ (naredbeni redak:
  `--mit-diagnosen`). Za osobne dosjee, otkaze i vještačenja, gdje se
  dijagnoza nikoga ne tiče.

  **Zadano isključeno**, i to namjerno: liječničko pismo se *sastoji*
  od dijagnoza i aktivnih tvari. Tko ga anonimizira – za istraživanje,
  za obuku, za AI alat – najčešće želi zadržati baš taj sadržaj i
  samo se riješiti toga o kome je riječ. Dijagnoza je ondje sadržaj,
  ne oznaka.

  Prepoznavanje pronalazi uobičajene nazive i ne zamjenjuje pregled:
  popis bolesti nikad nije potpun, jer liječnik piše „C2-Abusus“, gdje
  klasifikacija vodi „Poremećaji uzrokovani alkoholom“.

- **Dijagnostičke i ljekarničke šifre se pronalaze.** MKB-10 (`I48.2`),
  ATK (`A10BA02`) i farmacevtska centralna oznaka su zdravstveni
  podaci kao i svaka ispisana dijagnoza – u otpusnim pismima i
  obračunskoj dokumentaciji čak češći oblik. Zadano su uključene, kao i
  ostale posebne kategorije po čl. 9 GDPR-a.

  Dijagnostička šifra se prepoznaje samo s dokazom: s „MKB“ ispred ili
  u zagradi iza retka dijagnoze. Bez tog uvjeta program bi funkcijsku
  tipku **F10** smatrao dijagnozom ovisnosti – u klasifikaciji je F10
  baš to.

- **Gotova datoteka se sada može kopirati.** Uz svaki gotov redak, uz
  „Pogledaj“, „Doradi“ i „Prikaži u mapi“ stoji četvrti gumb:
  **Kopiraj**. Stavlja očišćenu datoteku u međuspremnik – odande ide
  s Ctrl+V (Mac: ⌘V) u poštu, prozor razgovora ili AI alat, bez
  zaobilaska preko mape.

  Kopira se **datoteka**, ne njezin tekst: raspored stranice, slike i
  trake zacrnjenja time ostaju sačuvani. Preko kontekstnog izbornika
  popisa u međuspremnik odjednom ide i više odabranih rezultata, a u
  izborniku „Datoteka“ isti put stoji kao **„Kopiraj rezultat“** za sve
  koji radije koriste tipkovnicu.

- **Odabir zemlje sada može pratiti dokument.** Identifikacijski,
  socijalni i porezni brojevi razlikuju se od zemlje do zemlje, a koje
  se zemlje provjeravaju dosad je vrijedilo za cijelu sjednicu –
  izvedeno iz jezika sučelja. Tko radi na njemačkom i čisti francusko
  pismo, u njemu je tražio njemačke porezne brojeve, a ne francuski
  broj socijalnog osiguranja.

  U prozoru pravila sada za to stoji **„Automatski prema jeziku
  dokumenta“**. Fiksan odabir ostaje pored, i to namjerno: prepoznavanje
  jezika nije nepogrešivo – pogriješi li, primjenjuje se pogrešan
  odabir zemlje. Tko obrađuje samo spise jedne zemlje, sigurniji je s
  fiksnim popisom.

  Time nisu zahvaćeni **njemački** uzorci (porezna ID, registarska
  oznaka vozila, interni broj): oni ovise o jeziku, ne o odabiru
  zemlje, i djeluju i dalje čak i kad se kratak njemački tekst
  procijeni kao engleski.

- **Lozinke, ključevi i korisnička imena se sada pronalaze.** Tko
  kopira poruku o pogrešci, zapisnik ili isječak konfiguracijske
  datoteke u AI prozor, gotovo uvijek u njemu ima pristupni ključ – a
  taj je dosad ostajao nepromijenjen.

  Prepoznaje se oboje: uobičajeni oblici ključeva koji govore sami za
  sebe (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token,
  zaglavlje privatnog ključa), i označeni oblik – „Lozinka:“, „API-ključ
  =“, „Token:“, „Korisničko ime:“. Zamjenjuje se pritom samo
  vrijednost, nikad oznaka: „Lozinka: [ZUGANGSDATEN_1]“ ostaje
  čitljiva, a tko provjeri rezultat, vidi da je ondje stajala lozinka.

  Korisničko ime i lozinka su dvije odvojene vrste. Tko želi ukloniti
  samo lozinke, isključuje jednu i zadržava drugu.

- **Crtični i QR kodovi na slikama se čine neprepoznatljivima.** Na
  skeniranom rješenju gotovo uvijek je zalijepljen kod, a u njemu stoji
  broj predmeta – isti broj koji se uklanja u tekstu pored. Dosad je
  strojno čitljiva inačica ostajala: traka preko broja ništa ne
  koristi, ako ga dva centimetra dalje uređaj u sekundi očita.

  Prepoznaju se QR kod, Data Matrix, Aztec, Code 128, EAN i ostali
  uobičajeni oblici. Neprepoznatljivo znači pikselizirano, i to grublje
  nego kod lica: ispravak pogrešaka koda iz nekoliko sačuvanih polja
  iznenađujuće mnogo vraća, polovičan veo ne bi bio uklanjanje.

  Opcija stoji uz „Učini lica neprepoznatljivima“ i jednako je
  **zadano uključena**. I kod isključene opcije izvještaj kaže koliko
  slika nosi kod – lice se vidi pri listanju, kod se smatra ukrasom.

- **Kontrolni broj kartice, PIN i datum isteka se pronalaze.** Broj
  kreditne kartice program je već pronalazio; tek s tri podatka pored
  postaje upotrebljiv, a na svakom obračunskom dokazu stoje zajedno.
  Sva tri samo iza svoje oznake – „123“ samo je kućni broj, broj
  stranice ili količina.

- **Koordinate u tekstu se pronalaze.** Iz slika je Maskuro mjesto
  snimanja već uklanjao; stajao li isti podatak kao tekst u vještačenju
  ili izvještaju o intervenciji, ostajao je. Prepoznaju se decimalni
  stupnjevi i zapis stupanj-minuta-sekunda. Kod decimalnih stupnjeva
  riječ poput „Lokacija“, „Mjesto nalaza“ ili „Koordinate“ mora biti u
  blizini – inače bi svaki niz mjerenja s dvije decimale bio podatak o
  mjestu.

- **Novčani iznosi se sada mogu ukloniti zajedno.** Nova kvačica
  „Ukloni i novčane iznose“, zadano **isključena** kao i datumi
  iznad: u ugovoru je iznos sadržaj, i tko sve zacrni, nikoga ne
  štiti. U platnoj listi, prijedlogu nagodbe ili izvodu iz računa
  naprotiv je baš taj podatak koji o osobi govori više od imena pored
  – to zna samo tko ima dokument pred sobom.

  Iznos se prepoznaje **samo uz oznaku valute**: „4.250,00“ sam po sebi
  je količina, tek „4.250,00 EUR“ je novac. Znak valute, kratica i
  ispisan naziv broje se, ispred i iza, uključujući zapis „990,–
  CHF“.

- **Posebne kategorije po čl. 9 GDPR-a se prepoznaju.** Vjeroispovijed,
  sindikalno članstvo, političko uvjerenje, zdravstveni podaci – i uz
  to podaci o kaznenim djelima po čl. 10. To su podaci čiju obradu
  Uredba u načelu **zabranjuje**; zato su jedina nova skupina zadano
  **uključena**. Tko ih želi zadržati, sam odlučuje.

  Prepoznaje se oblik u kojem stoje u praksi: polje obrasca na osobnom
  listu – „Vjeroispovijed: rimokatolička“, „Sindikat: SSSH“, „Stupanj
  invaliditeta: 50“, „Kaznene osude: nema“ –, i to s dvotočkom pored
  jednako kao i s oznakom iznad, kako ih donosi ispunjen list.

  **Tekući tekst pripada AI razini.** „Godinama je aktivan u sindikatu“
  isti je podatak, a nijedan uzorak pretrage ga pouzdano ne pronalazi.
  AI razina od ove inačice izričito traži i te kategorije u tekućem
  tekstu; tko treba tekući tekst, uključuje je.

- **Osobna obilježja i zanimanje – podaci koji i bez imena pokazuju o
  kome je riječ.** Spol, bračno stanje, visina, boja očiju i kose od
  ove se inačice uklanjaju; zanimanje, funkcija i odjel na zahtjev,
  preko vlastite kvačice („Ukloni i zanimanje i odjel“) ili
  `--mit-berufen`.

  **Zašto je jedno uključeno, a drugo isključeno:** „Voditeljica odjela
  nabave“ u poduzeću imenuje točno jednu osobu, čak i kad je ime pored
  zacrnjeno – u vještačenju ili otkazu to treba ukloniti. Pregled
  djelatnika naprotiv *se sastoji* od naziva zanimanja; tko bi ih
  zadano uklanjao, vraćao bi prazan list. Koji je slučaj prisutan, zna
  samo tko ima dokument pred sobom. Obilježja iznad stoje gotovo
  isključivo u poljima obrazaca, rijetka su i nikad ne nose sadržaj –
  ne koštaju dakle ništa.

- **Provjeriti tuđu datoteku.** „Datoteka → Provjeri datoteku …“ ponovno
  čita već zacrnjen dokument i javlja što u njemu još stoji – i
  **na kojem mjestu**: stranica i redak, vrsta i duljina. Za slučaj
  kad netko provjerava tuđi rad: spis iz odvjetničkog ureda, odgovor
  tijela vlasti, vlastitu izlaznu poštu prije slanja.

  **Sama vrijednost ne stoji u izvještaju.** Tko otvori to mjesto, vidi
  je ionako – i izvještaj se stoga smije spremiti i proslijediti, a da
  sam ne bude zbirka osobnih podataka.

  **A izvještaj u svakom slučaju kaže što nije mogao vidjeti.** Slike se
  ne čitaju; kod skena bez tekstualnog sloja „nema nalaza“ znači *nije
  provjereno*, ne *čisto*. Na naredbenom retku to razdvaja povratna
  vrijednost: `--nachpruefen` daje 0 za provjereno i čisto, 4 za
  nalaze i 5 za neprovjerivo. Time se izlazna pošta može automatski
  zadržati, umjesto da se propusti.

- **Izvještaj provjere: list po čišćenju.** „Datoteka → Spremi izvještaj
  provjere …“ – ili `--pruefbericht <mapa>` na naredbenom retku –
  piše jednostranični PDF (po izboru CSV ili tekst) s podacima o
  izvođenju, pronađenim vrstama s brojem, dvije kazaljke i napomenom
  provjere. Za spis i za nadzorno tijelo: zapisnik provjere je
  pouzdaniji dokaz, ali nitko ne prilaže JSON-Lines datoteku.

  **Novo su dvije brojke** koje se dosad nigdje nisu vidjele: *prosječna
  pouzdanost* – koliko je prepoznavanje bilo sigurno u ono što je
  pronašlo – i *stopa maskiranja*, udio zamijenjenih znakova u tekstu.
  Obje stoje sa svojom granicom: pouzdanost **ništa** ne govori o
  previđenom, a uz nju uvijek stoji na koliko se nalaza uopće odnosi;
  stopa ne broji slike i kod ilustriranog dokumenta ispada previsoka.

  **Vrijednosti nalaza ne stoje na listu** – ista granica kao kod
  zapisnika i pretraživanja. Dolje stoje dva retka koja ne kažu isto:
  kontrolna suma pokazuje da je list nepromijenjen; redak zapisnika –
  samo uz pokrenut zapisnik – upućuje na **potpisani** redak koji
  dokazuje izvođenje. Tek on dokazuje podrijetlo.

- **„Koliko je to bilo sigurno?“ – kazaljke uz rezultat.** Gumb
  „Kazaljke“ ispod rezultata otvara ono što se dosad nigdje nije
  vidjelo: mjesta nalaza, riječi i znakovi, raspodjela po vrsti kao
  redak stupaca, uz to prosječna pouzdanost i stopa maskiranja. Iste
  brojke kao u izvještaju provjere, samo odmah i bez ispisa.

  **Sa svojom ogradom na istoj površini:** uz pouzdanost stoji na koliko
  se nalaza odnosi, a ispod rečenica da **ništa** ne kaže o previđenom.
  Postotak bez te rečenice čita se kao stopa pogodaka – a tko ga tako
  shvati, u lošijem je položaju nego bez broja.

  Računa se tek pri otvaranju: nazivnik stope maskiranja po datoteci
  košta jedno čitanje, i to ne treba platiti tko brojke uopće ne
  pogleda.

- **Vlastiti uzorci pretrage bez pisanja ijednog.** Kartica „Vlastiti
  uzorci pretrage“ sada u tri koraka vodi kroz stvar: *Što tražite? →
  Kako to kod vas izgleda? → Imenujte i spremite.* Utipkate primjer –
  primjerice `KD-004711` –, program iz njega izvodi pravilo i riječima
  piše što traži. Pregled s brojačem nalaza provjerava pri svakom
  pritisku tipke.

  **Regularni izraz se pritom uopće ne pojavljuje.** Moć nikad nije bila
  problem: vlastiti uzorci pretrage postoje odavno, samo su zahtijevali
  izraz poput `\bKD-\d{6}\b`, a takav u odvjetničkom uredu ili
  kadrovskoj službi nitko ne piše. Tko ga *želi* napisati, otvara
  stručni način.

  **Katalog predložaka je nanovo posložen:** trinaest kartica s
  nazivom, objašnjenjem i primjerom vrijednosti, filtrirano preko
  oznaka kategorija – financije, tijela vlasti, kontakt, kadrovi,
  medicina.

  A kad izvedeni uzorak zahvaća previše, program to sam kaže: primjer
  od samih znamenki pogađa svaku godinu i svaki iznos, a tko ne zna
  pročitati izraz, inače to ne bi mogao primijetiti.

- **Sedam oznaka umjesto pedeset šest kvačica.** Nova kartica „Što se
  traži“ objedinjuje sve prepoznatljive vrste u sedam skupina – osoba,
  kontakt i mjesto, identifikatori, financije, tehnika, posebne
  kategorije, tvrtke i vlastito. Oznaka uključuje svoju skupinu, „Sve
  uključi“ i „Sve isključi“ cijeli popis; ispod toga svaka vrsta ostaje
  pojedinačno odabirljiva.

  **Zadano je sve uključeno, i tako ostaje.** Ono što se ovdje isključi,
  uopće se ne traži – najgrublji zahvat koji prozor pravila dopušta, i
  djeluje na svaki dokument. Zato ispod popisa uvijek stoji koliko je
  vrsta isključeno, a sprema se samo isključeno: nova vrsta time je
  uključena i u datoteci pravila od prekjučer, umjesto da tiho ispadne.

- **Prenijeti okvir na sve stranice.** U prozoru uređivača gumb
  **Prenesi na sve stranice** uzima posljednje povučeni okvir i
  zacrnjuje isto mjesto na svakoj daljnjoj stranici – za zaglavlje,
  podnožje i polje broja predmeta. Kod skeniranog spisa od osamdeset
  stranica od toga dvadeset minuta postaje dvije.

  **„Isto mjesto“ znači isto *relativno* mjesto na listu.** U skupini
  iz uvlaka redovito jedna stranica leži poprijeko, druga je A3, treća
  zaokrenuta; apsolutno prenesen pravokutnik ondje bi sletio pored
  zaglavlja pisma – a vidjela bi se traka i smatralo bi se stvar
  gotovom.

  **Zacrnjuje se, ne zamjenjuje**, čak i kad je polazni okvir bio
  rezervirano mjesto: ispod istog pravokutnika na stranici četrdeset
  stoji nešto drugo nego na stranici jedan, a rezervirano mjesto s
  istim brojem tvrdilo bi jednakost koje nema.

- **Napomena na traci zacrnjenja.** U pravu na uvid u spis uz svako
  zacrnjenje stoji zašto je zacrnjeno. Novo polje **Napomena na traci**
  u postavkama – ili `--balkenvermerk` – piše kratak tekst na svaku
  traku: „čl. 203 KZ“, „GDPR“, „povjerljivo“. Za dokument koji izdaje
  tijelo vlasti to je razlika: primatelj vidi razlog bez zapisnika koji
  ionako nikad ne dobiva.

  **Zadano prazno**, jer je napomena vidljiva u izdanom dokumentu i
  sama je podatak – primatelju kaže po kojem se naslovu nešto
  zadržava. Djeluje samo kod **zacrnjivanja**; gdje stoji rezervirano
  mjesto, nema trake. Na traci premaloj za čitljiv tekst izostaje –
  nečitljiva napomena izgleda kao pogreška.

- **Aktivacija bez internetske veze – sada potpuna.** U prozoru
  licence „Aktiviraj bez interneta“ postojao je već duže: gore kod
  zahtjeva za ponijeti sa sobom, dolje polje za aktivaciju koja se
  vraća. Samo je nju dosad **nitko mogao izdati** – alat za to
  nedostajao je, a kod je odlazio u prazno. To je riješeno.

  Za tijela vlasti i odvjetničke urede s izoliranim računalima to nije
  poseban slučaj, nego uobičajen – i baš je to ciljna skupina kod koje
  obećanje „vaši dokumenti nikad ne napuštaju računalo“ najviše teži.
  Kod ništa ne otkriva o dokumentima: sadrži licencnu oznaku i
  kontrolnu vrijednost računala, ništa drugo.

- **Preuzeti sa skenera.** „Datoteka → Preuzmi sa skenera …“ izravno
  učitava skupinu i stavlja stranice u popis – za pisarnicu razlika
  između dva radna koraka i jednog. Uvlak lista se prazni do
  posljednje stranice; uređaj, razlučivost i boju bira sistemski
  dijalog skenera, koji već poznajete.

  **Ne čisti se automatski.** Prvo vidite što je ušlo, pa pritisnete
  „Očisti“ kao kod svake druge datoteke – sken koji odmah prolazi
  oduzeo bi vam pogled na nakrivo uvučenu skupinu.

  **To postoji samo na Windowsu**, a stavka izbornika to na Macu i
  kaže: ondje softver vašeg skenera piše u mapu, a „Nadziri mapu …“
  čisti sve što ondje sleti.

### Ostalo

- **Popis svih pronađenih podataka sada je priložen** i stvara se iz
  izvornog koda (`hilfe/GEFUNDENE-ANGABEN.md`): 177 vrsta u 35 zemalja,
  23 od toga s izračunom kontrolne znamenke. Navodi i kako se brojalo –
  mi brojimo `[NAME]` jednom, gdje drugi ime, drugo ime i prezime vode
  kao tri unosa.

- **Zacrnjivanje sada postoji i u Wordu, PowerPointu, OpenDocumentu i
  HTML-u.** Izbor između rezerviranog mjesta i zacrnjenja dosad je
  vrijedio samo za PDF datoteke. Sada mogu i ostali: nalaz se uklanja,
  a na njegovo mjesto dolazi crna traka – u samom dokumentu, ne kao
  slika preko njega. Tko datoteku proslijedi, prosljeđuje zacrnjen spis,
  ne onaj u kojem zacrnjeno i dalje leži kao tekst ispod.

  **Odlučuje se odvojeno**, u dva izborna polja: „Kod PDF-a“ i „Kod
  Worda, PowerPointa, OpenDocumenta i HTML-a“. Netko to želi
  drugačije – zacrnjen PDF ide tijelu vlasti, ista stvar kao Word
  datoteka putuje dalje kroz tvrtku i treba ostati čitljiva. Na
  naredbenom retku odgovarajuće `--pdf-modus` i `--office-modus`;
  spremljeno „Zacrni“ iz ranijih inačica i dalje vrijedi za PDF.

  U tablicama, čistom tekstu, CSV-u i e-pošti traka ne ide – ondje
  nedostaje površina na koju bi se položila. I dalje se postavlja
  rezervirano mjesto, a rezultat to **sada i kaže**, umjesto da to tiho
  radi.

- **Novo: „Ukloni“ – mjesto nalaza jednostavno ostaje prazno.** Treći
  način rada uz rezervirano mjesto i zacrnjivanje, i jedini koji radi
  sa **svakim** formatom: izostavljanje ne treba površinu. U PDF-u se
  pritom ništa ne crta, u Wordu i HTML-u mjesto ostaje prazno, u
  tablici jednako.

  Najtiši je od sva tri: tko čita rezultat, ne vidi da je ondje ikad
  nešto stajalo – ni duljina vrijednosti se više ne otkriva. Za spis
  koji netko treba provjeriti, rezervirano mjesto najčešće ostaje bolji
  izbor.

  Na slikama nijedan od tri izbora ne vrijedi: slikovne točke se ne
  mogu zamijeniti rezerviranim mjestom ni izostaviti. Ono što
  prepoznavanje teksta ondje pronađe, kao i dosad se uvijek premazuje.

- **Prozor uređivača više ne tvrdi zamjene koje ne postoje.** Desno je
  uz svaku vrijednost stajalo rezervirano mjesto – i kod zacrnjene
  datoteke u kojoj nijedno ne postoji. Klik na takav redak ništa nije
  označavao, a „Poništi“ je promašivao. Sada ondje stoji „zacrnjeno“
  odnosno „uklonjeno“, a takvi se retci uopće ne mogu poništiti: teksta
  nema, nema što vratiti. Vrijedilo je za zacrnjene PDF datoteke, za
  Word i OpenDocument i za sve pronađeno na slikama.

- **Prikaz teksta sada trake prikazuje kao trake.** Zacrnjena Word
  datoteka pri doradi izgledala je **prazno**: na zacrnjenim mjestima
  stajale su praznine, kao da je program progutao tekst. Razlog je bio
  prikaz, ne rezultat – u samom dokumentu traka je cijelo vrijeme
  ispravno ležala. Sada stoji ondje i u prikazu, crna kao u rezultatu,
  u Wordu, PowerPointu, OpenDocumentu i HTML-u.

- **Outlook poruke (`.msg`) sada se čiste.** `.eml` je postojao odavno –
  u njemačkim tvrtkama Outlook je ipak e-pošta, i ondje se spremljena
  poruka zove `.msg`. Time je najgušći PII format pokriven i u svom
  najraširenijem obliku spremanja: predmet, pošiljatelj, retci
  primatelja, tekst poruke, HTML inačica, popis primatelja i privitci –
  potonji preko postojećih puteva i istim rezerviranim mjestima kao
  tekst poruke.

  **`.msg` isti tekst nosi više puta**, i to je zamka: kao čist tekst,
  kao HTML **i** kao RTF. Tko čisti samo čist tekst, nije učinio
  ništa – Outlook prije svega prikazuje RTF. RTF inačica se zato
  potpuno uklanja, jednako i internetska zaglavlja s lancem Received i
  binarni ključevi pretrage, koji imena i adrese preživljavaju svako
  čišćenje teksta. Rezultat se i dalje otvara u Outlooku i prikazuje
  tekst bez oblikovanja pisma; izvještaj to izričito kaže.

- **Pravila opisati vlastitim riječima umjesto pisati regex.** Prozor
  pravila mnogo toga zna i za to je zahtijevao uzorak regularnog
  izraza – mjesto na kojem većina staje. Sada je dovoljna rečenica:
  „Naši brojevi predmeta oblika 12 C 345/26 trebaju ostati.“ AI razina
  iz toga predlaže pojmove i uzorke pretrage.

  **Preuzima se samo ono što označite – i zadano ništa nije
  označeno.** Uz svaki prijedlog stoji rečenica što znači, i broj
  njegovih nalaza u primjeru teksta koji možete priložiti. Ono što
  **oduzima** zaštitu posebno je označeno: „ovaj pojam uvijek ukloni“ i
  „ovaj pojam nikad ne ukloni“ inače bi u popisu izgledali jednako.
  Prijedlozi koji bi odgovarali svemu se uopće ne prikazuju.

- **Zapisnik provjere sada broji zbrojeno preko svih radnih mjesta.**
  Odlaže li tvrtka zapisnike preko `protokoll_pfad` na zajedničko
  mjesto, ondje svako radno mjesto piše svoju mjesečnu datoteku – dosad
  je službenik za zaštitu podataka s trideset mjesta morao pojedinačno
  pregledati trideset datoteka. Iznad popisa sada stoji redak sa
  zbrojevima mjeseca, i **on prijavljuje prekinute lance s imenom**:
  naknadna izmjena upada u oči samo ako je netko pregleda, a u
  trideset datoteka nitko ne provjerava ručno.

  **Nema popisa po osobi** – ni u ovom prikazu. Poredak „tko je koliko
  očistio“ bio bi prikladan za nadzor ponašanja i učinka, a na to je
  ključno pravno gledište, ne namjera. Broje se izvođenja, datoteke i
  nalazi kroz cijelu tvrtku.

- **„Predloži profil iz spisa“: jednom pitati pravila umjesto proći
  četrdeset četiri vrste.** U prozoru pravila postoji novi gumb:
  pokazuje AI razini spis, utvrđuje o čemu se radi – liječničko pismo,
  prijava, ugovor, račun, rješenje – i predlaže strategije koje mu
  odgovaraju. Kod liječničkog pisma primjerice se datumi pomiču
  umjesto zamjenjuju, jer je u zdravstvenom kartonu kronologija
  sadržaj.

  **Profili stoje u programu, model samo bira** – pravila zacrnjivanja
  ne ovise o tome što jezični model smatra dobrom idejom. Predlaže se
  svaka točka pojedinačno i s obrazloženjem; ništa se ne preuzima bez
  potvrde, a ono što ste sami odredili ostaje netaknuto. Bez AI razine
  ostaje pri sigurnoj zadanoj vrijednosti: rezervirano mjesto za sve.

- **Nova strategija „izmisli“: vjerodostojna pogrešna vrijednost umjesto
  rezerviranog mjesta.** „Gospođa Berger pisala je gospodinu Doppleru
  u Fuldi“ umjesto „[NAME_1] pisala je [NAME_2] u [ORT_1]“ – za
  obrazovne materijale, prezentacijske spise, testne skupove podataka
  i sve što se potom predlaže AI-ju. Oslovljavanje, struktura rečenice
  i čitljivost ostaju sačuvani.

  Ista vrijednost dobiva istu izmišljenu vrijednost, kroz sve datoteke
  jednog predmeta i na svakom računalu s istom datotekom pravila –
  **bez da se ikamo sprema pridruživanje** (ista mehanika kao kod
  hashiranja). Adrese e-pošte leže na rezerviranim primjerskim
  domenama, telefonski brojevi u za to rezerviranom rasponu, izmišljeni
  IBAN-ovi nose ispravno izračunatu kontrolnu znamenku. Moguće za
  imena, mjesta, adrese, tvrtke, e-poštu, telefon i IBAN; za druge
  vrste pravilo se odbija, umjesto da ostane bez učinka.

  **Izvještaj izričito kaže da je izmišljeno.** Tako očišćen dokument
  čita se kao stvaran, a nije – ne vrijedi kao dokaz i ne smije se
  prosljeđivati kao izvornik.

- **Protuprovjera: „Tko ostaje prepoznatljiv?“** Nova kvačica ispod AI
  razine **gotov rezultat** ponovno predlaže jezičnom modelu i pita
  tko je unatoč čišćenju prepoznatljiv. Mišljen je slučaj koji nijedno
  prepoznavanje na svijetu ne nalazi, jer ondje uopće ne stoji ime:
  „jedina primalja u okrugu“, „kolega koji je nakon požara u ožujku
  dao otkaz“. Nijedan uzorak ne pogađa, a na terenu svejedno svatko zna
  na koga se misli.

  **Pritom se ništa ne uklanja.** Mjesta stoje s rečenicom obrazloženja
  u izvještaju, a odlučuje se ručno – program koji sam uzima rečenice
  iz spisa jer mu se čine odajućima, od čišćenja pravi prepisivanje, i
  nitko ne bi vidio što nedostaje. Najviše pet mjesta po datoteci; ono
  što model ne može doslovno dokazati, otpada. Na naredbenom retku:
  `--restrisiko` zajedno s `--ki`.

- **Put natrag iz AI-ja: „Prevedi odgovor natrag“.** Dosad je izgrađena
  samo polovica petlje – kopirati tekst, umetnuti očišćeno, predložiti
  AI-ju. Odgovor se vraćao s `[NAME_1]`, a tko ga je trebao, ručno je
  vraćao ono što je ručno izvadio. Sada put natrag stoji u izborniku
  „Program“: kopirati odgovor, kliknuti unos, prava imena su ponovno
  ondje.

  Pridruživanje za to leži **samo u radnoj memoriji**, vrijedi uvijek
  samo za posljednje očišćeno mjesto i istječe nakon sat vremena; tko
  isključi čuvara međuspremnika, odmah ga gubi. Vratiti se pritom može
  samo ono što je zamijenjeno – zacrnjeno, maskirano i hashirano nije
  obrativo, a program kaže koliko je mjesta zbog toga moralo ostaviti.
  Upravljane instalacije put natrag u potpunosti isključuju preko
  zadane vrijednosti `rueckweg`.

- **Nadziri mapu: što se odloži, ubrzo potom leži očišćeno u izlazu.**
  Za pisarnicu, tim za poštanski pretinac ili mapu skeniranja – jednom
  postaviti, nakon toga nitko više ne klika. Nalazi se pod „Datoteka →
  Nadziri mapu …“, na naredbenom retku preko `--wache <mapa>`.

  Izvornik ostaje gdje je bio; na zahtjev nepromijenjen putuje u
  podmapu „Gotovo“, pri čemu se nikad ništa ne prepisuje. Datoteka se
  dira tek kad je gotovo zapisana – inače bi datoteka koja se još
  kopira preko mreže bila napola pročitana i prijavljena kao očišćena.
  Ono što pođe po zlu ostaje ležati i javlja se, umjesto da se
  beskonačno ponavlja. A nadzor pamti gotovo bez naziva datoteke: ono
  što leži u ulaznoj mapi često već u nazivu odaje o čemu je riječ.

  **Nadzor mape izvan vlastitog korisničkog profila – primjerice na
  mrežnom pogonu – zahtijeva licencu za automatizaciju.** Mapa do koje
  dopire više ljudi je usluga, ne radno mjesto; u vlastitom profilu i
  tijekom probnog razdoblja to ograničenje ne vrijedi.

### Riješeno

- **Postavke su bile odsječene desno.** Prozor se otvarao fiksne
  veličine, dovoljne samo za veličinu pisma s kojom se razvijalo: na
  Macu su „Provjeri sada“, „Promijeni …“ i napomene pored bili
  napola izvan. Sada se otvara onoliko širok koliko trebaju njegove
  stranice – na svakom jeziku i svakoj veličini pisma, ograničen samo
  zaslonom.

- **„Provjeri sada“ sada odgovara vidljivo.** Rezultat je stajao u
  statusnom retku glavnog prozora – dakle iza prozora postavki, iz
  kojeg je upit poslan. Tko je provjeravao, nije vidio ništa. Sada
  odgovor dolazi kao poruka iznad postavki, a postoji li nova inačica,
  odmah vodi na instalaciju. Pri pokretanju programa i dalje ostaje
  status u traci, bez upita se ne otvara nijedan prozor.

- **Kopirane datoteke na Macu nisu stizale u međuspremnik.** Odlaganje
  očišćenih datoteka javljalo je uspjeh, a ipak nije ostavljalo ništa
  upotrebljivo – lijepljenje nije davalo ništa. Zahvaćeno je bilo sve
  što zapisuje datoteke u međuspremnik.

- **A iz međuspremnika se na Macu čitala samo prva datoteka.** Tko je u
  Finderu kopirao tri datoteke i odabrao „Očisti međuspremnik sada“,
  dobivao je dvije od njih natrag neočišćene – bez da je itko to
  rekao. Sada stižu sve.

- **„Provjeri datoteku“ sada prihvaća i povučene datoteke** – kao
  glavni prozor. Odloženo se dodaje umjesto da odbaci dosadašnji
  odabir; dvostruko odlaganje istog ništa ne mijenja, a ono što program
  ne može pročitati, javlja se umjesto da se proguta.

- **A prozor kaže da čeka na vas.** Otvarao se s praznim okvirom i sivim
  gumbom „Provjeri“ – to izgleda kao da ničega nema, ne kao da
  nedostaje odabir. Sada ondje stoji „Još nijedna datoteka odabrana –
  povucite ovamo ili dolje odaberite preko „Odaberi datoteke …“.“

- **Dugo izvođenje sada kaže da traje.** „Učitava se dodatni model za
  precizno prepoznavanje – trenutak …“ ostajalo je stajati dok je
  prepoznavanje računalo: kod datoteke od 47 500 riječi dakle osamnaest
  minuta, iako je učitavanje bilo gotovo nakon devet sekundi. Tko to
  vidi, smatra program zaglavljenim. Sada slijedi „Precizno
  prepoznavanje u tijeku – kod dugih tekstova to traje nekoliko
  minuta“, a statusni redak broji: „Precizno prepoznavanje (7/312)“.
  Javlja se pritom iz petlje modela – svakih 250 riječi, dakle
  otprilike svakih šest sekundi – ne po tekstualnom bloku: tekstualni
  blok nosi dvanaest tisuća riječi i treba minute.

- **Prekinuto izvođenje sada kaže da je prekinuto.** Tko je pritisnuo
  „Prekini“, nakon toga je čitao „Očišćeno 0 od 1 datoteka.“ –
  ispravno izbrojano, a ipak pogrešna obavijest. Poruka koja je
  javljala koju je datoteku pogodilo bila je u istom trenu prepisana
  porukom brojanja. A u popisu datoteka i dalje je stajalo „u tijeku
  …“, iako ništa više nije radilo; sada ondje stoji „prekinuto“.

- **Rečenica o zaštiti podataka bila je odsječena.** „… bez oblaka, bez
  učitavanja. Više o zaštit“ – kod širine prozora s kojom se program
  pokreće, prekidala se usred riječi. Sada zauzima punu širinu.

- **Licencna usluga je mogla nešto priopćiti, i nitko nije slušao.**
  Kad su sva licencna mjesta zauzeta, licenca istekla, ključ nepoznat
  ili je licencna usluga kod pružatelja isključena, usluga za to šalje
  točan razlog – zamišljeno je od početka bilo da vam se on **jednom**
  objasni. Nikad se nije prikazao. Sada se pojavljuje napomena koja
  najprije kaže da program nastavlja raditi nepromijenjeno, a zatim o
  čemu je riječ. Jednom po razlogu: tko ga je odklikao, ne vidi ga
  ponovno pri dnevnoj provjeri – no vidi ga ako se razlog promijeni.

- **Licenca za više mjesta kupljena u trgovini pokazivala je „1
  mjesto“.** Trgovina raspodjeljuje pripremljene ključeve i kupljen
  broj mjesta drži kod sebe; prikazivao se pak broj iz samog ključa, a
  taj kod svakog pripremljenog ključa glasi na jedno mjesto. Tko je
  kupio osam mjesta, čitao je „1 mjesto“ – a od drugog prijavljenog
  računala prikaz je stajao crveno uz „Molimo obratite se svojoj
  upravi“. Sada vrijedi broj koji je usluga posljednji put javila; bez
  odgovora ostaje pri ključu, a manje od kupljenog opsega nikad ne
  postaje.
  Isto vrijedi za dokupe i produljenja: oni mijenjaju broj mjesta kod
  pružatelja, ne vaš ključ.

- **Nakon kupnje stajalo je „Licencirano za Maskuro osobnu licencu“.**
  To nije ime, nego rezervirano mjesto pod kojim se ključevi pripremaju
  – vaše ime ondje ne može stajati, jer je ključ potpisan već prije
  kupnje. Umjesto da vam pokaže tuđe ime kao vaše, sada ondje jednostavno
  stoji „Osobna licenca“ i broj mjesta. Kod licence koja je izdana na
  vas, vaše ime i dalje ondje stoji nepromijenjeno.

- **U izborniku Pomoć stajalo je „Pomoć _ČPP“.** Znak „i“ postao je
  podcrta, jer ga je Qt čitao kao oznaku za tipkovno slovo. Sada ondje
  stoji „Pomoć i ČPP“.

- **Prozor postavki ostajao je otvoren kad je program nestao u ikonu** –
  i to čak i kad je glavni prozor zatvoren. Sada se zatvara zajedno.
  (Odnosi se samo na ovu inačicu; vlastiti prozor je nov.)

- **Odbijen licencni upit sada kaže o čemu se radi.** Odbije li
  licencna usluga upit bez slanja razloga, u prozoru licence crveno je
  stajalo „Nepoznat odgovor.“ – rečenica s kojom ni vi ni podrška ne
  mogu ništa, i koja vas navodi da tražite pogrešku u svom ključu. Sada
  ondje stoji što se stvarno dogodilo: da je usluga odbila bez
  obrazloženja, i kome se obratiti. Je li licencno upravljanje kod
  pružatelja privremeno isključeno, to se također navodi – uz napomenu
  da vaš ključ time nije zahvaćen.

- **Na Macu su postavljeni jezici odjednom vrijedili kao nedostajući.**
  Pri pokretanju program je javljao „Nije instaliran nijedan jezični
  model“ i nudio prvo postavljanje, iako su jezici odavno bili
  učitani – tko je provjerio pod „Jezici dokumenata“, pronalazio ih je
  ondje sve. Program ih je, ovisno o putu pokretanja, tražio na dva
  različita mjesta: pokrenut iz mape Programi, pronalazio ih je;
  pokrenut isti bau kao obična mapa, tražio ih je pored sebe, gdje
  nijedan ne leži. Od sada na Macu bez iznimke vrijedi isto mjesto u
  korisničkom profilu, kako god je program upakiran. Ništa se ne mora
  ponovno učitati.

- **„Što je novo“ prikazivalo je pola popisa.** Prozor nakon ažuriranja
  prekidao se usred rečenice, a preostale su točke stajale kao prazni
  znakovi popisa. Kriv je bio rezervirano mjesto u kutnim zagradama –
  primjerice `<datoteka>.docx` – koje je prikaz smatrao oznakom i od
  kojeg je sve daljnje odbacivao. Baš su novosti o sigurnosti time bile
  zahvaćene. Pomoć takva rezervirana mjesta oduvijek prikazuje
  ispravno; sada to čini i ovaj prozor.

- **Štipanje s dva prsta sada zumira u prozoru uređivača.** Na touchpadu
  je to *ta* gesta zumiranja – u uređivaču dosad nije ništa radila, a
  tko je htio pobliže pogledati mjesto, morao je posegnuti za
  klizačem ili Ctrl+kotačić. Stranica sada odmah prati gestu i pri
  otpuštanju se ponovno crta oštro.

- **Zumira se na mjesto koje se gleda.** Štipanje uvećava oko točke
  između prstiju, Ctrl+kotačić oko točke ispod pokazivača. Gumbi,
  tipkovne prečice i klizač zuma zadržavaju sredinu – njima ne
  pripada mjesto na koje se pokazuje. Prije je kod svih ostajala samo
  vrijednost pomicanja: od uklopljene stranice to je držalo gornji rub,
  a sve ispod pri uvećavanju izlazilo je iz slike.

- **„Prije/poslije“ u pregledu stranice bio je mrtav gumb.** Dok je
  pregled stranice bio uključen, mogao se pritisnuti – i svaki put je
  javljao da se izvornik ne može otvoriti. Ondje se uostalom nema što
  uspoređivati: pregled stranice je slika očišćene inačice, izvorniku
  parnjaka nema. Gumb je sada zaključan i pri pokazivanju navodi
  razlog zajedno s izlazom (prikaz teksta). Njegov opis je uz to
  izričito obećavao da usporedba radi „neovisno o tome je li aktivan
  prikaz teksta ili pregled stranice“ – to nikad nije bilo točno.

- **Pregled stranice rušio je LibreOffice.** Stvorena li su istodobno
  dva pregleda stranice – primjerice „Zacrni kao PDF“ dok je pregled
  još računao – sustav se javljao rušenjem LibreOfficea, iako su se
  stranice na kraju ipak pojavile: oba izvođenja pristupala su istom
  radnom spremištu LibreOfficea, što on ne podnosi. Sada ga uvijek
  dobiva samo jedno izvođenje; ostali prelaze na vlastito. Za to im
  treba nekoliko sekundi dulje, ali poruke o pogrešci više nema, i
  nijedno izvođenje ne ostaje bez rezultata. Drugi nalog iscrtavanja
  uz aktivan se uz to uopće ne prihvaća.

- **„Prikaži izvornik“ mogao je zatvoriti program.** Nije li se
  izvornik dao otvoriti – jer je premješten, preimenovan, zaštićen
  lozinkom ili leži na odvojenom pogonu – prozor uređivača prekidao se
  bez upozorenja, i otvorene radne kopije bile su izgubljene. Sada
  dolazi napomena, prekidač skače natrag, a očišćena inačica ostaje
  stajati. Gdje izvornik u načelu ne pristaje pored – primjerice kod
  PDF pregleda stranice nastalog iz Word datoteke – prekidač je
  unaprijed zaključan i pri pokazivanju navodi razlog, umjesto da kod
  svakog pritiska prikazuje istu napomenu.

- **Izvještaji o pogreškama nikad nisu stizali.** Tko je htio prijaviti
  pogrešku, dobivao je „Protustrana je odbila izvještaj“ – a nitko ga
  nikad nije vidio. Dva uzroka, oba na putu: program se poslužitelju
  nije predstavljao i zato ga je odbijala zaštita od masovnih pristupa,
  a adresa je upućivala na drugi naziv kojeg program nije slijedio.
  Oboje je riješeno; izvještaj sada ponovno odlazi. **Isto je pogodilo
  aktivaciju licence**: prijava, odjava i upit isto nisu dopirali do
  usluge – ondje tek neupadljivo, jer neodgovoren upit namjerno ništa
  ne mijenja na vašoj licenci. A ostane li odbijanje ipak neobjašnjivo,
  sada uz njega stoji njegov tehnički broj, umjesto da svaki uzrok
  izgleda jednako.

- **Klik na „Prikaži izvornik“ mogao je zatvoriti program.** Nije li se
  izvornik dao otvoriti – premješten, preimenovan, na odvojenom
  mrežnom pogonu, zaštićen lozinkom ili oštećen – prozor uređivača
  nestajao je zajedno sa svim otvorenim radnim kopijama. Sada prekidač
  ostaje kod očišćene inačice, a okvir kaže o čemu je riječ; tehnički
  razlog stoji u detaljima, ako ga želite prijaviti. Isto vrijedi za
  rezultat koji se ne može prikazati: prozor se otvara i to kaže,
  umjesto da nestane.

- **Pitanje o rušenju pojavljivalo se prečesto – i brisalo trag o kojem
  je pitalo.** Pojavljivalo se i kad se ništa nije srušilo: bilješka
  nastaje čim se igdje pojavi neočekivana smetnja, čak i kad je program
  preživi i nakon toga sasvim uobičajeno zatvori; nikad se nije
  uklanjala. A tko je odgovorio „Ne“, uništio je jedine pojedinosti
  događaja – bilješka je nestajala već pri *prikazu* pitanja. Oboje je
  riješeno: uredan kraj uklanja bilješku, pita se samo kod stvarnog
  prekida, a odjavljuje se tek nakon vašeg odgovora. Pojedinosti i
  dalje stoje u zapisniku pogrešaka na vlastitom računalu – tko ništa
  ne želi poslati, time svejedno ništa ne gubi. Šalje se i dalje samo
  ono što ste prije u cijelosti vidjeli i sami odobrili.

- **„Očisti“ je mogao ostati tiho zaključan.** Zaglave li se jezični
  modeli pri učitavanju, gumb je ostajao isključen – bez objašnjenja.
  Klik na njega nije radio ništa, a statusni redak i dalje je govorio
  „Jezični modeli se učitavaju …“, i nakon deset minuta. Uzrok: smetnje
  u pozadinskim procesima odlazile su na mjesto koje pri pokretanju iz
  upravitelja datoteka nitko ne vidi; ostajao je prozor koji je
  izgledao spreman za rad i nije reagirao ni na jedan klik. Sada takve
  smetnje završavaju u zapisniku pogrešaka, učitavanje jezičnih modela
  u svakom slučaju javlja svoj neuspjeh umjesto da tiho odustane, a
  ostane li ipak tiho, aplikacija nakon tri četvrt minute kaže da
  nešto nije u redu, sa savjetom u detaljima. Zaključan gumb pri
  pokazivanju navodi svoj razlog. Dugo prvo naknadno učitavanje pritom
  ne vrijedi kao tišina – dok se javlja napredak, sve ostaje mirno. Kao
  rušenje se sve to ne broji: aplikacija nastavlja raditi, i zato se
  pri sljedećem pokretanju o tome ni ne pita.

- **Na Macu program više nije pronalazio ažuriranja – i govorio je da je
  na najnovijem stanju.** Mac inačica nije nosila popis korijenskih
  certifikata; tražila ga je na mjestu koje postoji samo na računalu
  na kojem se gradi. Time ni na jednom poslužitelju nije mogla
  provjeriti s kim razgovara, i prekidala je svaku vezu: nema
  ažuriranja, nema aktivacije licence, nema naknadnog učitavanja
  jezičnih modela, nema izvještaja o pogrešci. Starije inačice su od
  toga tiho pravile obavijest „Koristite najnoviju inačicu“. Certifikati
  sada leže u samom programu; ne pronađe li ih ondje, uzima sustavske,
  a na Macu u krajnjem slučaju one iz privjeska ključeva – a nema li
  ih uopće, to i kaže, umjesto da tvrdi najnoviju inačicu. Sama
  provjera se pritom nikad ne isključuje.

  To jedno ažuriranje Mac korisnici još moraju ručno instalirati:
  inačica koja ne doseže poslužitelj ne može se ni sama obnoviti.

### Promijenjeno

- **Glavni prozor je pospremljen.** Dolje je stajalo šest jednako
  velikih gumba jedan uz drugoga – „O …“, „Uputa“ i „Pomoć i ČPP“
  ispod, iako su ista tri puta već stajala u izborniku Pomoć iznad.
  Sada su objedinjeni u gumb „Pomoć“ koji ih otvara; nijedan se ne
  gubi. Dolje ostaju dva puta kojima se stvarno počinje: „Očisti“ i
  „Ručno zacrni …“.

- **Što program upravo radi, sada stoji na fiksnom mjestu.** Poruka
  („Jezični modeli se učitavaju …“, „(3 / 7) pismo.pdf“, „Očišćeno 5
  od 7 datoteka.“) dosad je visjela kao sivi tekst između dva reda
  gumba. Dobila je vlastitu površinu, s obojenom točkom ispred: siva
  dok ništa ne radi, plava tijekom rada, zelena nakon glatkog
  izvođenja i žuta kad su se pojavile napomene. Točka ne govori ništa
  što ne stoji pored – samo to kaže brže.

- **Postavke su postale vlastiti prozor.** Dosad su ležale u glavnom
  prozoru – kutija s četiri kartice koja se otvarala pod „Više
  postavki“, a koja je za svoj sadržaj bila premalena: uvijek je u
  njoj stajala traka pomicanja, a izbor između anonimiziranja i
  pseudonimiziranja stajao je napola izvan slike. Gumb se sada zove
  „Postavke …“ i otvara prozor s bočnom trakom; svaka od četiri
  stranice u potpunosti stane. Glavni prozor pri otvaranju se više ne
  otvara odjednom, a popis datoteka se može vidjeti sa strane.
  Promijenilo se samo gdje postavke stoje – koje postoje i što rade
  ostaje nepromijenjeno.

- **„Detalji“ se otvara, umjesto da skoči.** Prozor je dosad rastao u
  jednoj slici, i nakon toga se moralo tražiti što se promijenilo.
  Sada se onamo pomiče.

- **Veličine pisma i razmaci prate isto mjerilo u cijelom prozoru.**
  Naslovi su na dva mjesta bili različite veličine, a jednako rangirani
  retci stajali su različito razmaknuti. Vidljivo je to kao mir, ne kao
  pojedinačna izmjena.

- **Anonimiziranje je sada zadano.** Dosad je pseudonimiziranje bilo
  zadano: iste osobe dobivale su isti broj (`[NAME_1]`, `[NAME_2]`),
  veze su ostajale čitljive – pravno su time ipak ostajali **osobni
  podaci**. Tko ništa ne postavi, sada dobiva postupak koji podatke
  izuzima iz GDPR-a: svi nalazi jedne vrste zovu se jednako (`[NAME]`).
  Numeriranje ostaje izbor, i dalje stoji u istom prozoru; postojeće
  postavke ostaju kakve jesu. Na naredbenom retku `--pseudonymisieren`
  (i `--mit-nummerierung`) vraća staro.

- **Anonimizirana rezervirana mjesta se više ne mogu pojedinačno
  poništiti.** Tko anonimizira, za svaku osobu dobiva isto rezervirano
  mjesto – time više ne postoji pojedinačno mjesto koje pripada
  određenom imenu. Prozor uređivača je unatoč tome nudio „Poništi
  zamjenu“: klik bi umetnuo *jednu* od vrijednosti na *sva* mjesta.
  Retci su sada prigušeni kao kod zacrnjenih podataka, klik navodi
  razlog, a ručno dovučen nalaz više ne dobiva broj koji nigdje drugdje
  u dokumentu ne stoji.

  Iz istog razloga nakon anonimiziranog izvođenja više nema „Prevedi
  odgovor natrag“ – prije bi to na mjesto svake osobe stavilo tuđe
  ime. Tko treba tu petlju, bira „Pseudonimiziraj“; aplikacija to sada
  i kaže, umjesto da upućuje na istekli rok pridruživanja.

  Na naredbenom retku `--zuordnung` kod anonimiziranja sada se prekida,
  umjesto da piše datoteku koja nije prijevod natrag – u prozoru je
  kvačica odavno bila zaključana. Ili uz to `--pseudonymisieren` ili
  izostaviti `--zuordnung`; poruka to kaže. Rezultat pritom uopće ne
  nastaje, kako skripta ne bi ostala s polovičnim radom.

- **Kanal ažuriranja sada je zadano „Stabilno“.** Bez vlastitog izbora
  kanal se dosad ravnao prema tome iz kojeg je gradiva potjecala tekuća
  inačica – tko je jednom isprobao testnu inačicu, otad je trajno
  dobivao ponuđene testne inačice. Promjena kanala je odluka i treba
  ostati odluka; zadano je zato „Stabilno“. Postavljeni kanali ostaju
  netaknuti.

### Poboljšano

- **„Postupak žalbe“ više se ne smatra nazivom mjesta.** U naslovu
  „Bilješka spisa – Postupak žalbe 12 C 345/26“ program je zacrnjivao i
  postupak: jezični model smatrao ga je mjestom, i to neovisno o
  okruženju. Uzeta nije pojedinačna riječ, nego **osnovna riječ**
  složenice – „postupak“ i „bilješka“ time pokrivaju i poslovni,
  knjigovodstveni i platni postupak ili telefonsku bilješku. Od trideset
  provjerenih upravnih pojmova tri su prije izazivala lažnu uzbunu,
  sada nijedan; i dalje se pronalazi sve što pored stoji („Postupak
  žalbe: Bernd Meisinger“ gubi ime, ne naslov).

- **Anonimiziranje ponovno vodi evidenciju – za dosljednost i
  zapisnik.** U anonimizirajućem načinu rada program nije pamtio
  pronađene vrijednosti. Time su dvije stvari šutjele: dokumentski
  konzistentni naknadni prolaz (prezime koje se kasnije pojavi samo
  ostajalo je stajati) i popis zamjena u zapisniku provjere. Dok je
  anonimiziranje bilo rjeđi izbor, to se jedva primjećivalo – kao
  zadano bi postalo pravilo. U dokumentu se ništa ne mijenja:
  rezervirano mjesto ostaje bez broja.

- **„Nijedan osobni datum“ sada se zove „nijedan osobni podatak“.** U
  dijalogu poništavanja i upozorenju o licima stajao je pravni izraz
  *datum* – jednina od „podaci“. Čitao se kao kalendarski dan, tim
  više što aplikacija na drugom mjestu nudi „Ukloni i datume“. Sada
  posvuda stoji „podatak“, kao u četiri razloga iznad u istom prozoru.

- **Redak podrijetla sada stoji samo u prozoru „O programu“.** „Made
  with ♥ in Austria“ sjedio je dolje u glavnom prozoru usred reda
  gumba i ondje se čitao kao još jedan gumb. I dalje stoji u prozoru
  „O programu“ – ondje gdje se traži.

- **Površina za odlaganje sada ima vidljiv rub.** Njezin isprekidan rub
  bio je toliko blijed da se jedva odvajao od prozora – to je bilo
  svejedno dok je površina bila samo površina. Otkad je gumb koji se
  može doći tipkom Tab, taj je crtak jedino što je pokazuje kao
  upravljački element; zato je podignut na vrijednost koju za to
  zahtijeva norma.

## 0.10.22-beta.1 – 15. kolovoza 2026.

### Novo

- **Isključi li se nadzor međuspremnika, uistinu je isključen.** Čuvar u
  radnoj memoriji drži posljednje sadržaje, kako bi se izvornik mogao
  vratiti – dosad i onda kad je nadzor bio isključen. Sada se povijest
  pri isključivanju zaboravlja. To košta obnavljanje nakon isključivanja,
  i baš tako je zamišljeno: isključeno znači isključeno.
- **Zapisnik pogrešaka više ne sadrži putanje datoteka.** Nalazio se samo
  na vašem računalu i nikad se sam nije slao – ali je putanje vodio u
  čitljivom obliku, a naziv datoteke često odaje više od sadržaja. Iz
  „…/Razvod_Mueller_Nagodba.docx“ sada pri zapisivanju nastaje
  `<datoteka>.docx`; nastavak ostaje, jer je važan pri traženju
  pogreške. Isto vrijedi za bilješku nakon rušenja.
- **Popis zamjena sada upozorava sam u sebi.** On je jedina datoteka u
  kojoj vaši izvorni podaci stoje u čitljivom obliku, a nalazi se uz
  rezultat – tko proslijedi mapu, prosljeđuje i njega. Sada upozorenje
  stoji kao prvi redak **u** datoteci, područje ispisa navodi punu
  putanju umjesto samo naziva datoteke, a na naredbenom retku se
  datoteka uopće prvi put spominje: ondje se dosad nije ni saznalo da je
  nastala.
- **Anonimiziranje ili pseudonimiziranje sada je imenovan izbor.** Na tom
  je mjestu dosad stajala kvačica „Ista imena imenuj isto – AI tada i
  dalje prepoznaje tko je tko“. Ona je opisivala korist, a prešutjela
  posljedicu: brojčano označena rezervirana mjesta (`[NAME_1]`,
  `[NAME_2]`) su **pseudonimizacija**, a pseudonimizirani podaci ostaju
  osobni podaci – tko je vjerovao da je time anonimizirao, griješio je.
  Sada oba postupka stoje jedan uz drugi, svaki sa svojom cijenom.
  Zadano ostaje pseudonimiziranje, jer dokument koji se nakon toga i
  dalje čita ili ga obrađuje AI treba svoje veze. Kod anonimiziranja
  popis zamjena je zaključan: ponovno bi omogućio vraćanje rezultata na
  izvornik. Priručnik i ČPP objašnjavaju razliku na svih 18 jezika; na
  naredbenom retku prekidač se sada zove i `--anonymisieren`.
- **Redak iznad površine za odlaganje sada kaže ono što stvarno vrijedi.**
  Obećavao je „100 % lokalna obrada – bez oblaka i računa, u skladu s
  GDPR-om“. Za vaše dokumente to vrijedi, za program ne u toj mjeri: on
  traži ažuriranja, na zahtjev javlja pogreške, naknadno učitava modele i
  prijavljuje kupljena radna mjesta. Sada ondje stoji uža i održiva
  tvrdnja: vaši dokumenti ne napuštaju računalo.
- **Uz rezultat sada uvijek stoji da ga treba provjeriti.** Dosad je
  Maskuro nakon glatkog izvođenja javljao „Uklonjeno podataka: 12“ u
  zelenoj boji i ništa drugo – to se čita kao jamstvo da je sve
  pronađeno. Napomene su se pojavljivale samo kad konkretno nešto nije
  moglo biti provjereno (slike, nepoznati privitci). Sada ispod svakog
  rezultata neprijeporno stoji da se ne prepoznaju u svakom slučaju svi
  osobni podaci, da je provjera na korisniku i da nedostajuće treba
  ručno dopuniti – u prozoru, u području ispisa i na naredbenom retku.
  Nema prozora s porukom koji se odklikne: rečenica stoji trajno. Kratka
  uputa to sada kaže istim riječima.
- **Nakon ažuriranja pri pokretanju stoji što se promijenilo.** Dosad je
  ažuriranje prolazilo nečujno i nije se razlikovalo od ponovnog
  pokretanja. Sada se jednokratno pojavljuje „Što je novo“ – a tko je
  preskočio inačicu, vidi i one između. Ne kod baš prvog pokretanja:
  ondje i dalje uvodi kratka uputa.
- **Kineski i japanski sada pronalaze imena.** Dosad nisu pronalazili
  **nijedno** – ne malo, nijedno. Oba jezična modela nisu imala
  segmentaciju riječi, bez koje rečenica bez razmaka vrijedi kao jedna
  jedina riječ; program je tiho prelazio na višejezični zamjenski
  model. Oba jezika sada prepoznaju osobe i mjesta kao i ostali.
  Japanski rječnik se pritom učitava zajedno s jezikom i ne nalazi se u
  programu – sam bi bio dobrih 200 MB, koje bi inače svatko nosio sa
  sobom.
- **Rumunjska je odabirljiva kao zemlja.** Dosad je posve nedostajala.
  Time se prepoznaju rumunjske adrese („Strada Victoriei 30“), poštanski
  brojevi s mjestom („010061 București“) i Cod Numeric Personal –
  potonji samo uz ispravnu kontrolnu znamenku, kako se ne bi označio
  svaki trinaesteroznamenkasti broj na računu. Do sada je u rumunjskim
  dokumentima poštanski broj ostajao čitljiv uz zacrnjeni naziv mjesta.
- **„Rasteriziraj stranicu“ u uređivaču.** Ne da li se tekst iz PDF-a
  ukloniti – to se događa kod datoteka tuđih izrađivača – stranica se
  sada na zahtjev zamjenjuje svojom slikom: tekst je time neopozivo
  nestao, stranica ostaje čitljiva i pretraživa. Upozorenje koje javlja
  taj slučaj odmah nudi ovaj korak kao gumb; preko „Alati → Rasteriziraj
  stranicu“ ide i samostalno. Vraćanje unatrag donosi stranicu natrag.
- **Sučelje je sada dostupno i na hrvatskom, grčkom, litavskom,
  slovenskom, japanskom i korejskom.** Time ih je osamnaest. Priručnik,
  ČPP i pravni tekstovi potpuno su dostupni na svih šest. Oznake u
  očišćenom dokumentu pritom prate sučelje – iz `[NAME_1]` nastaje
  `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` ili `[氏名_1]`. **Kod grčkog,
  japanskog i korejskog oznake stoje latinicom** – `[ONOMA_1]`,
  `[SHIMEI_1]`, `[IREUM_1]`. Sučelje ostaje u vlastitom pismu; latinicom
  je samo ono što se piše u dokument. Razlog je PDF znakovni skup: ondje
  su grčke i japanske oznake ranije stizale kao `[??_1]`, čime se ime
  više nije moglo razlikovati od mjesta.
- **Devet zemalja dolazi, a sedam postojećih postaje potpuno.** Novo se
  prepoznaju identifikacijski, porezni i socijalno-osigurateljni brojevi
  zajedno s adresama za **Hrvatsku, Sloveniju, Grčku, Litvu,
  Sjevernu Makedoniju, Rusiju, Ukrajinu, Kinu i Japan**. Kod postojećih
  zemalja zatvorene su praznine koje su više vrijedile: za
  **Nizozemsku** i **Portugal** dosad uopće nije bilo osobnog broja –
  nizozemski BSN i portugalski NIF nisu se prepoznavali, iako stoje na
  praktički svakom dokumentu tih zemalja. Poljska dobiva porezni broj
  NIP, Danska, Norveška i Finska svoje adrese, Kanada svoj poštanski
  broj. Time ih je **35 zemalja**.

### Uklonjeno

- **Za Linux zasad više nema paketa.** Izvorni kod ondje radi, ali tri
  stvari koje ova uputa obećava nedostaju na Linuxu: automatsko
  pokretanje, globalne tipkovne prečice i, ovisno o radnom okruženju,
  ikona u traci. Isporučiti paket koji može manje od opisanog bio bi
  pogrešan put. Windows i macOS nisu zahvaćeni.

### Poboljšano

- **Brojevi predmeta sada se pronalaze na svim jezicima.** „Aktenzeichen
  12/2026-AB“ bio je uklonjen, „File reference 12/2026-AB“ ili
  „Sygnatura 12/2026-AB“ ostajali su netaknuti: riječi polja po kojima
  Maskuro prepoznaje takav broj postojale su samo na njemačkom. Sada
  poznaje odgovarajuće izraze na dvanaest jezika – i kao dosad
  zamjenjuje se samo broj, oznaka ispred njega ostaje, kako bi u
  rezultatu bilo prepoznatljivo što je ondje uklonjeno.
- **Maskuro u mirovanju zauzima oko pola gigabajta manje.** Pri
  pokretanju se dosad učitavao i dodatni model preciznijeg prepoznavanja,
  kako prvo čišćenje ne bi na njega čekalo. Izmjereno, to je koštalo 648
  MB radne memorije i štedjelo 1,9 sekunda – a koštalo je i onda kad
  samo otvorite i opet zatvorite prozor. Model se sada učitava prvi put
  kad je potreban; statusni redak to javlja. Jezični model i dalje se
  učitava pri pokretanju – njega odmah treba nadzor međuspremnika.
- **Površina za odlaganje sada se koristi i bez miša.** „Povucite
  datoteke ovamo“ bila je površina koja je reagirala na klikove – s
  tipkovnicom se do nje nije dolazilo, a čitač zaslona ju je najavljivao
  kao okvir s tekstom u sebi, ne kao ono što jest. Sada je gumb: tipka
  Tab skače na nju, tipka za razmak i Enter otvaraju odabir datoteka, a
  tko je na njoj, vidi to po rubu. Preko izbornika „Datoteka → Odaberi
  datoteke“ išlo je već i prije, ali to je trebalo znati.
- **Naziv očišćene datoteke sada se i izgovara.** U popisu datoteka stoji
  kao drugi, manji redak ispod izvornika – ali bio je samo nacrtan, i
  čitač zaslona izgovarao je samo izvornik. Baš je taj redak izgrađen
  protiv zablude da je izvođenje bilo bez učinka, jer u mapi stoji
  netaknut izvornik. Redak se sada izgovara kao „racun.pdf, rezultat:
  racun_ocisceno.pdf“.
- **Upravljački elementi bez oznake sada kažu čemu služe.** Simbol-gumbi
  u popisu datoteka, gumbi znakova u prozoru uređivača te sva polja
  odabira i unosa bili su za čitač zaslona bezimeni – najavljivali su se
  kao „gumb“ i „kombinirano polje“, bez informacije o čemu. Gumbi u
  jednom retku pritom uz to navode i datoteku: u popisu s dvadeset
  unosa inače se dvadeset puta čula ista rečenica.
- **Tko upravlja tipkovnicom, ponovno vidi gdje se nalazi.** Gumb
  „Očisti“ i simbol-gumbi u popisu datoteka izrađeni su u boji, čime je
  prestao raditi obrub koji sustav inače crta oko upravljačkog elementa
  na koji se skoči – kod prolaska tipkom Tab pogled je upadao u
  prazno. Oba sada imaju vlastiti obrub čim su na redu. Gumbi pritom ne
  mijenjaju veličinu.
- **Sedam boja teksta bilo je preblijedo, u oba izgleda.** Izmjereno prema
  uobičajenoj normi (WCAG 2.1), blijedi retci s napomenama, sporedni
  tekstovi na zoni odlaganja, točke upute i u tamnom izgledu dodatno
  plava i crvena bile su ispod granice 4,5:1 – čitljivo pri dobrom
  svjetlu i dobrom oku, inače ne. Sve su podignute; stupnjevanje ostaje,
  tekstovi se i dalje čitaju kao sporedni. Tri daljnje boje – u kojima se
  javljaju upozorenje i uspjeh – granicu su držale tek za dlaku i
  povučene su s njima: tko ih ne čita, ne čita ni obavijest je li nešto
  pošlo po zlu. Vidljivo se pritom promijenio samo gumb „Očisti“ u
  tamnom izgledu: sada nosi tamno umjesto bijelo pismo, kao i akcentni
  gumbi Windowsa 11.
- **Svaki redak popisa datoteka sada ima vlastiti križić.** Dosad je
  trebalo najprije označiti redak, a zatim kliknuti „Ukloni“ – dva
  koraka za sitnicu. Križić stoji desno u retku i treba samo jedan klik.
  Gumb „Ukloni“ ispod time je otpao; tko odjednom želi maknuti više
  redaka, označi ih i uzme stavku u kontekstnom izborniku, koja kaže i
  koliko ih je. „Ukloni sve“ ostaje. Iz popisa se uvijek uklanja samo
  redak – nikad datoteka na disku.
- **Prije AI provjere sada stoji je li ovo računalo za nju prikladno.**
  Dosad je u prozoru stajalo samo koliko je model velik. Tko ga je
  uključio na slabijem računalu, tek je kod prvog dokumenta primijetio
  da traje jako dugo – nakon 5,4 GB preuzimanja. Sada prozor **unaprijed**
  navodi radnu memoriju i slobodan prostor te kaže što to znači;
  **naknadno** se mjeri brzina i navodi u veličini o kojoj je riječ:
  „Desetostranični dokument na ovom računalu traje oko 12 minuta.“ Ako je
  presporo, program odgovara i nudi da se razina ponovno isključi –
  ništa ne zabranjuje.
- **Mjerenje brzine sada radi na svakom računalu.** Dosad se pojavljivalo
  samo ako je dodatno bila postavljena grafička akceleracija – koja
  postoji samo na Windowsu. Na svim drugim računalima program je stoga
  trajanje procjenjivao prema tuđem računalu, i baš ondje gdje je
  sporije, procjena je bila pogrešna.
- **Turske adrese sada se pronalaze i na skenu.** Na skeniranom zaglavlju
  pisma „34710 İstanbul“ ostajao je čitljiv, dok je ista oznaka u tekstu
  pored nestajala: prepoznavanje teksta čita tursko İ bez njegove
  točke, a uzorak je očekivao veliko slovo. Isto je vrijedilo za
  „Bağdat Caddesi“.
- **Španjolske adrese bez vlastitog imena ulice sada se pronalaze.**
  „Gran Vía 5“ ostajao je netaknut jer je uzorak iza vrste ulice
  očekivao još jednu riječ imena – kod „Calle Mayor“ postoji jedna, kod
  „Gran Vía“ je sama vrsta već ime. Isto sada vrijedi za „La Rambla“ i
  „Castellana“.
- **U prozoru „O ovom programu“ sada stoji napomena o transparentnosti**
  o tome da je aplikacija razvijena uz potporu umjetne inteligencije.
  Ona se odnosi na nastanak programa, ne na njegov način rada: čisti se
  i dalje isključivo na vlastitom računalu.
- **„Upravljanje jezicima“ sada prvo prikazuje upotrebljive jezike.** Za
  polovicu od 48 jezika ne postoji vlastiti jezični model; ondje
  višejezični zamjenski model prepoznaje imena samo slabo, u nekim
  pismima uopće ne. Jedan uz drugi u popisu svi su izgledali jednako
  vrijedni. Zadano se stoga prikazuju samo jezici s vlastitim modelom –
  preko „Prikazano“ ostali se mogu bilo kad uključiti, uz rečenicu što
  mogu i što ne. Ništa ne otpada, a tko je postavio ograničen jezik,
  zadržava ga.
- **Pitanje o jeziku koji nedostaje sada navodi izlaz.** Prepozna li se
  jezik za koji još ništa nije postavljeno, program je dosad nudio samo
  „Učitaj“ ili „Nastavi bez toga“. No prepoznavanje može promašiti – kod
  kratkih obrazaca i popisa s malo tekućeg teksta odlučuje nekoliko
  riječi. U prozoru zato sada stoji da se može prekinuti i ručno odabrati
  ispravan jezik, umjesto korištenja „Automatski prepoznaj“. To u
  dvojbi štedi preuzimanje od nekoliko stotina megabajta za jezik koji
  uopće nije potreban.
- **Oznake rezerviranih mjesta sada govore jezikom sučelja.**
  „[NAME_1]“, „[ADRESSE_2]“ i slično dosad su uvijek stajale na
  njemačkom, bez obzira koji je jezik postavljen ili na kojem je jeziku
  napisan dokument. Sada prate jezik sučelja – kod engleskog dakle
  „[NAME_1]“, „[ADDRESS_2]“. Ne jezik dokumenta: on je kod „automatski
  prepoznaj“ pogađan i ponekad pogrešan; jezik sučelja nikad nije.
- **Manje potpitanja pri doradi.** Kamo se rezultat sprema sada trajno
  stoji dolje u traci (“→ ugovor_ocisceno.pdf“, u napomeni mapa) – klik
  na to bira drugo mjesto, bez odmah spremanja. Time otpada potpitanje
  kod prvog spremanja. Pitanje „već obrađeno – početi iznova?“ može se
  zapamtiti za sjednicu, a dva prozora s napomenom koji su davali samo
  obavijest sada stoje u statusnom retku. Ostala su pitanja koja
  sprječavaju neopozivu štetu: nespremljeni rad pri zatvaranju i
  upozorenje o neuklonjenom tekstu.
- **Rezultat sada kaže gdje sam sken nije bio čitljiv.** Na skeniranom
  dokumentu prepoznavanje teksta uređaja ne čita sve ispravno – iz
  „Solarstraße 9“ nastane npr. „Solaret^aß« B“. Ono što je tako
  pogrešno pročitano više nijedna provjera ne može pronaći: za svaki
  uzorak pretrage izgleda kao mješavina slova. Program tu ne može ništa
  promijeniti, ali takva mjesta sada navodi s brojem stranice – ondje se
  najčešće nalaze pečati, zaglavlja pisma ili rukom pisani dodaci.
  Napomena, ne upozorenje: kod složenog dokumenta izostaje.
- **Popis datoteka sada pokazuje kako se zove rezultat.** Ispod naziva
  datoteke nakon izvođenja stoji naziv očišćene datoteke
  (“→ ugovor_ocisceno.pdf“). Dosad je stajao samo u zapisniku iza
  „Detalja“, a tko je pogledao u mapu, pronalazio je netaknut izvornik.
  Naziv izvora ostaje – inače se ne bi vidjelo iz koje datoteke rezultat
  potječe.
- **Gumbi u gotovom retku veći su i jasniji.** Pogledaj, Doradi i
  „Prikaži u mapi“ bili su plosnati simboli bez površine i gubili se u
  popisu – a upravo su oni jedino što se nakon izvođenja još klika.

### Riješeno

- **Na sučelju na stranom jeziku vlastita pravila za zacrnjivanje,
  maskiranje i hashiranje tiho su se preskakala.** Tko je odredio da se
  imena zacrnjuju umjesto zamjenjuju, ipak ih je dobivao zamijenjena –
  čim program nije radio na njemačkom ili engleskom. Postavka je
  stajala, samo nije djelovala, a u rezultatu se razlika nije vidjela.
  Zahvaćeno je bilo devet od dvanaest jezika sučelja.
- **Postavka „Jezik oznaka“ izvan njemačkog i engleskog nije imala
  učinka.** „Njemački“ i „Engleski“ mogli su se odabrati, ali u
  dokumentu je i dalje stajao jezik sučelja. Sada djeluju sve tri
  mogućnosti; zadano „kao sučelje“ daje nepromijenjeno isto što i
  dosad.
- **U kratkim isječcima teksta imena su ostajala netaknuta – primjerice
  u kopiranom citatu poruke.** Tko je isječak čistio preko
  međuspremnika, u njemu je često bila zacrnjena samo adresa e-pošte, a
  ime ispod nje ne. Odlučujući je bio sam broj redaka: od šest redaka
  program je isječak prepoznavao kao popis i pronalazio imena, ispod
  toga ne – kopirani citat poruke ima pet. Bilo koji dodatni redak,
  primjerice predmet, prevagnuo bi rezultat. Sada je dovoljno četiri
  retka, a u mjerenju nestaju sva provjerena imena umjesto trećine. Na
  duže dokumente i na tekući tekst to nema utjecaja.
- **Grafička akceleracija AI provjere dosad se ponovno isključivala čim
  bi je se postavilo.** Nakon postavljanja program mjeri je li grafika
  na ovom računalu uistinu brža od procesora – to mjerenje uvijek je
  bez riječi propadalo, a rezultat „oboje jednako brzo“ odlučivao je u
  korist procesora. Tko je učitao tih 65 MB, dobivao je nakon toga
  manje nego prije. Mjerenje sada radi; ne uspije li, više ništa ne
  mijenja.
- **Procjena vremena na svakom je računalu računala s tuđom brzinom.**
  Oslanja se na isto mjerenje; dok ono nije radilo, vrijedila je
  vrijednost razvojnog računala. „Otprilike dvije minute“ moglo je na
  sporom računalu značiti pola sata.
- **AI razina radi s novim, znatno boljim jezičnim modelom** (Qwen3.5-9B
  umjesto Qwen3-4B) i više nije ograničena na njemački i engleski, nego
  radi na dvanaest jezika. Izmjereno preko ispitnog korpusa: jednako
  mnogo pronađenih podataka kao i bez te razine, ali manje od polovice
  suvišnih zacrnjenja (75 → 31). Model je veći (5,4 umjesto 2,4 GB) i
  treba otprilike dvostruko vrijeme računanja; pri uključivanju
  jednokratno se učitava, a stari se pritom uklanja.
- **Adrese na francuskom, talijanskom, španjolskom, portugalskom,
  poljskom, turskom i švedskom sada se u potpunosti uklanjaju.** Dosad
  je ondje nestajao samo naziv ulice i mjesta – kućni broj i poštanski
  broj ostajali su čitljivi (“[ORT_1] 28, 28013 [ORT_2]“). Za te jezike
  nisu postojali vlastiti uzorci adresa; sada su dopunjeni.
- **Grčki i korejski uopće nisu pronalazili imena.** Kod grčkog razlog je
  bio zamjenski model – s vlastitim modelom, koji se sada može učitati,
  imena i mjesta prepoznaju se čisto. Kod korejskog razlog je bio u
  programu: pretpostavljao je da ime počinje velikim slovom, a hangul ne
  poznaje velika slova. Zahvaćene su bile prije svega kratke jedinice –
  stanice tablica, polja obrazaca, stavke popisa.
- **Jezični model koji se nije dao učitati prekidao je čišćenje.**
  Umjesto poruke o pogrešci sada uskače višejezični model, a rezultat
  napominje da se radilo sa slabijim prepoznavanjem. Trenutačno se to
  odnosi na kineski i japanski, čiji modeli trebaju odvajanje riječi koje
  još nije priloženo programu.
- **Jezik s vlastitim modelom vrijedio je kao instaliran čim je bio
  učitan bilo koji drugi.** Tko je postavio npr. turski, time je dobio
  višejezični zamjenski model – a kineski, japanski, korejski ili grčki
  potom su u popisu stajali s postavljenom kvačicom i „0 MB“, iako je
  njihov vlastiti model nedostajao. Time se nikad nisu mogli naknadno
  učitati i trajno su radili sa slabijim zamjenskim modelom. Popis sada
  pokazuje stvarno stanje zajedno s veličinom učitavanja.
- **Ispala razina prepoznavanja šutjela je o tome.** Bila je uključena
  „Proširena razina prepoznavanja“ ili „Maksimalna razina prepoznavanja
  (AI)“, ali se model nije mogao izvršiti, program je nastavljao raditi
  bez te razine – bez ijedne riječi o tome. Rezultat je izgledao kao
  svaki drugi, a prekidač je ostao na „uključeno“: rezultat osnovne
  razine tako se smatrao najboljim mogućim. Rezultat sada to kaže i
  navodi oboje – što nije provjereno i kako se model može ponovno
  učitati. Slučaj nije rijedak: na nekim računalima AI razina propada pri
  učitavanju kad nedostaje grafička akceleracija.
- **Pogreška pri učitavanju dodatnog modela prekidala je cijelo
  čišćenje.** Kod „Proširene razine prepoznavanja“ bila je osigurana
  samo obrada modela, ne i njegovo učitavanje – a upravo ondje nešto
  pođe po zlu kad je datoteka oštećena ili ne odgovara računalu. Umjesto
  poruke o pogrešci sada nastaje rezultat osnovne razine zajedno s
  napomenom.
- **Jezik se više nije dao ukloniti – a time ni ponovno učitati.** Tko je
  u „Upravljanju jezicima“ maknuo kvačicu i preuzeo promjenu, čitao je
  „Njemački uklonjen“, ali kvačicu je odmah vidio ponovno postavljenu.
  Uzrok je bilo preuzimanje iz mape programa: kod instalacije za sve
  korisnike jezični modeli nalaze se zaštićeni od pisanja u mapi
  programa, a program otuda uzima ono što nedostaje umjesto da naknadno
  učitava stotine megabajta. To preuzimanje odvijalo se pri svakom
  pristupu – i u istom trenu vraćalo upravo obrisan jezik natrag. Sada se
  događa jednokratno; naknadno učitani jezični modeli pritom ostaju
  sačuvani. Uz to program nakon brisanja provjerava: ono što se nije
  dalo ukloniti sada se javlja kao neuspjeh umjesto kao „uklonjeno“.
- **Kod instalacije za sve korisnike naknadno učitano nije se moglo
  odložiti.** Tko instalira program za sve korisnike, ima ga u
  „Programi“, a onamo se bez administratorskih prava ništa ne smije
  zapisivati. Za jezične modele odavno je za to bilo predviđeno
  zamjensko mjesto, za ostalo ne:
  - **Komponenta pregleda stranice** raspakiravala se nakon 290 MB
    preuzimanja u mapu programa i ondje propadala – bez navođenja
    razloga. Sada se nalazi uz jezične modele, gdje je po zamisli i
    trebala biti oduvijek.
  - **Grafička akceleracija** ne može izbjeći: zamjenjuje biblioteke u
    samom programu. Umjesto da se najprije učita pa tiho propadne,
    program sada unaprijed kaže da ovdje to ne ide i što to znači –
    maksimalno prepoznavanje i dalje radi, samo preko procesora.
  - Priložen **jezik prepoznavanja teksta** nije se dao ukloniti: iz mape
    programa je odmah ponovno bio obnovljen. Isti uzrok kao kod jezičnih
    modela, isto rješenje.
  - Pri uklanjanju jezika mogli su se obrisati **jezični podaci tuđe
    Tesseract instalacije**. Sada se dira samo vlastita mapa.
  - Zamjensko mjesto dosad je vrijedilo samo na Windowsu. Linux arhiva
    prema `/opt` imala je istu nevolju bez istog izlaza.
- **Pri doradi nestajao je cijeli redak, iako je bila okvirena samo jedna
  riječ.** Tko je u već očišćenoj datoteci zacrnio rezervirano mjesto,
  gubio je redak u kojem je ono stajalo: iz „Poštovana gospođo doktorice
  [NAME_1]“ ništa nije ostajalo – a poruka je uz to govorila „uklonjena
  jedna riječ iz dokumenta“. Zahvaćena je bila svaka datoteka koja je
  već jednom prošla kroz program, dakle baš slučaj za koji dorada
  postoji. Ostali tekst sada ostaje netaknut, na nepromijenjenom mjestu.
- **„EMPLOYEES“ iznad popisa imena bilo je i samo zacrnjeno.** Isti
  slučaj kao „MITARBEITER“ u 0.10.19, samo na engleskom – ondje je
  ostao. U velikim slovima jezičnom modelu nedostaje razlikovno
  obilježje, a naslov stoji iznad samih pravih imena. Imena ispod i
  dalje se pronalaze. Nije uvršteno „staff“: to je postojeće prezime, a
  unos bi zahvatio svakog „John Staff“ – ista odvaga kao svojedobno kod
  „Arbeiter“.
- **Pravni oblik bio je zamijenjen po drugi put.** Na skeniranom
  zaglavlju pisma jezični je model čitao „GmbH“, adresu i poštanski broj
  kao **jedno** mjesto. Adresa i poštanski broj potom su iz toga izrezali
  svoje dijelove, a ostao je pravni oblik kao vlastiti nalaz: u
  rezultatu je stajalo „[ORT_1] [ORT_2]“, gdje se mislilo na „[ORT_1]
  GmbH“. Naziv tvrtke i dalje se zamjenjuje – samo goli dodatak sada
  ostaje, a rezultat se čita kao zaglavlje pisma umjesto kao vježba s
  prazninama za popuniti.
- **Skraćen nalaz nije se ponovno provjeravao.** Uzrok slučaja iznad, i
  seže dalje: filtri protiv nagađanih nalaza radili su na onome što
  prepoznavači **javljaju** – ne na onome što ostaje nakon razrješenja
  preklapanja. Skrati li se dug nalaz na jačem prepoznavaču, ulomak je
  drugačiji tekst od procijenjenog, i nitko ga više nije pregledao.
  Sada da.
- **„Koristite najnoviju inačicu“ – iako se uopće nije moglo
  provjeriti.** Tko je za kanal ažuriranja postavio „Pregled (beta)“ ili
  „Stabilno – preporučeno“, dobivao je tu obavijest, iako na tim
  kanalima dosad uopće ništa nije izašlo. Sada program to točno kaže – i
  predlaže odabir drugog kanala u postavkama.
- **Zatvaranje prozora tijekom učitavanja rušilo je nit.** Tko je pokrenuo
  Maskuro i odmah opet zatvorio prozor dok su se jezični modeli još
  učitavali, dobivao je u zapisniku izvještaj o pogrešci: postupak
  učitavanja javljao se prozoru kojeg više nije bilo. Vidljivih
  posljedica nije bilo, ali u zapisniku je stajalo rušenje ondje gdje je
  netko bio brži od programa.
- **Rezultat se sada gleda, ne samo čita.** Dosad je stranica vrijedila
  kao čista kad vrijednost više nije stajala u tekstu. Na skenu to nije
  dokaz – ondje je vidljivi tekst slika. Na kraju se stoga provjerava je
  li površina u rezultatu uistinu zacrnjena; stoji li ondje još svijetli
  papir, izvještaj to izričito kaže, umjesto da javi „zamijenjeno“.
- **Zamijenjeni podatak ostajao je vidljiv na slici.** Stajala li je
  vrijednost na slici – skenirano zaglavlje pisma, pečat, cijela
  skenirana stranica – bila je uklonjena iz teksta dokumenta, ali je i
  dalje bila **vidljiva**: ono što čovjek čita ondje su slikovne točke.
  Izvještaj je unatoč tome javljao „zamijenjeno“. Sada se površina na
  slici zacrnjuje, bez obzira koja je strategija postavljena, a
  rezervirano mjesto stoji svijetlo na toj podlozi – ružno, ali pošteno,
  a pridruživanje ostaje sačuvano. Ne da li se format slike obraditi,
  rezultat to sada izričito kaže, umjesto da izgleda čisto.
- **Na skenu je rezervirano mjesto posve nedostajalo.** Tekstualni sloj
  skenirane stranice crta se nevidljivo, a rezervirano mjesto umetnuto u
  njega naslijedilo je to: postavljeno, ali se ne vidi. Na mjestu nalaza
  nakon toga nije stajalo ništa.
- **Prepoznavanje teksta koje uopće nije moglo raditi vrijedilo je kao
  uspješno.** Nedostajala li je jezična datoteka ili se prekinuo stroj
  za prepoznavanje, izvještaj je javljao „slika(e) … provjerene su
  prepoznavanjem teksta (0 nalaza)“ – dakle provjeru koja se nikad nije
  dogodila. Kod skena to je jedina provjera uopće: ugovor s čitljivom
  adresom na slici stranice time je vrijedio kao gotov. Izvještaj sada
  kaže da ništa nije provjereno, i zašto.
- **Jezična datoteka tražila se u pogrešnoj mapi.** Ako su u vlastitom
  jezičnom direktoriju bili drugi jezici od jezika dokumenta, stroj za
  prepoznavanje dobivao je baš taj direktorij i propadao – iako je
  odgovarajući jezik ležao pored. Sada se traži **jezik**, ne mapa.
- **Upozorenje o neuklonjenom tekstu savjetovalo je nešto što ne
  postoji.** Upućivalo je na „Zacrni kao PDF“ – no to stvara PDF prikaz
  *Office* datoteka i kod PDF-a uopće nije dostupno. Tko je htio
  poslušati upozorenje, tražio je uzalud. Sada ondje stoji gumb koji
  obavlja stvar.
- **U uređivaču su traka i rezervirano mjesto završavali pored označenog
  mjesta.** Zahvaćen je bio svaki PDF u kojem redak završava crticom za
  rastavljanje, a riječ se nastavlja u sljedećem – kod skenova je to
  osobito upadljivo, jer su ugovorni tekstovi dosljedno slagani s
  rastavljanjem. Obje polovice retka vrijedile su kao *jedna* riječ koja
  seže poprijeko preko sloga, a svaki okvir u njezinoj blizini preuzimao
  je to protezanje. Samo prepoznavanje time se ne mijenja: mjerni korpus
  daje isti rezultat kao i prije.
- **Uređivač je upozoravao da tekst „i dalje stoji u dokumentu“, iako je
  bio uklonjen.** Pojavljivala li se ista riječ više puta na stranici –
  u ugovorima pravilo – samoprovjera je nakon svakog zahvata javljala
  neuspjeh. Sada broji pojavljivanja, umjesto da samo provjeri stoji li
  riječ još igdje. Kod stvarnog neuspjeha upozorava nepromijenjeno.
- **Datoteka rezultata na svakom jeziku zvala se „_bereinigt“.** Zamišljeno
  je uvijek bilo da dodatak nazivu prati jezik sučelja – na engleskom je
  to i radilo („_cleaned“), u preostalih šesnaest jezika ne. Tko je
  program koristio na finskom, dobivao je „asiakirja_bereinigt.pdf“.
  Sada se datoteka zove „asiakirja_puhdistettu.pdf“, na japanskom
  „書類_除去済み.pdf“ i tako dalje – svaki put s riječju koju isto
  sučelje koristi u svojoj poruci o dovršetku. Tko je postavio vlastiti
  dodatak, zadržava ga.
- **„Upravljanje jezicima“ oznake je uvijek davalo na njemačkom.** U
  popisu 48 jezika dokumenta stajali su njemački nazivi, bez obzira koje
  je sučelje postavljeno: finski korisnik čitao je „Chinesisch“. Sada
  ondje stoji naziv na njegovom jeziku, a iza njega vlastito ime jezika
  – „Kiina (中文)“. Vlastito ime je namjerno: tko jezik prepoznaje po
  vlastitom imenu, pronalazi ga i kad mu finska riječ ništa ne govori.

## 0.10.19 – 12. kolovoza 2026.

### Poboljšano

- **Stavka u kontekstnom izborniku sada govori vašim jezikom.** Dosad je
  ondje na svakom sustavu stajao njemački tekst – čak i na engleskom
  Windowsu. Sada slijedi postavljeni jezik sučelja, a tko promijeni
  jezik, dobiva odmah preimenovanu stavku, bez ponovne instalacije.
  (Windows; na macOS-u i Linuxu naziv izbornika ujedno je i naziv
  datoteke – to dolazi kasnije.)
- **Uređivač pamti u kojem ste prikazu zadnji put radili.** Tko koristi
  pregled stranice, dobiva ga sam od sebe kod sljedećeg dokumenta – bez
  uključivanja svaki put. Tko ga nikada nije koristio, ne primjećuje
  ništa: obnavlja se samo ako je za to potreban gradivni element već
  učitan, nikada se zbog toga ništa ne dodatno preuzima.

### Riješeno

- **„MITARBEITER“ (DJELATNICI) iznad popisa imena bilo je i samo
  zacrnjeno.** U imenicima djelatnika i organigramima naslov je nestajao
  kao navodno ime – stoji ondje iznad samih pravih imena, a u velikim
  slovima jezičnom modelu nedostaje razlikovno obilježje. Imena ispod i
  dalje se pronalaze.
- **Količine su se smatrale adresama.** U računima, otpremnicama i
  popisima skladišta nestajali su podaci poput „3390 Zapisnik“, „1030
  Iznos“ ili „3390 Skladište“ kao navodni poštanski broj s mjestom –
  četveroznamenkasta količina izgleda kao austrijski poštanski broj. Ako
  iza broja stoji riječ koju aplikacija poznaje kao stvarnu imenicu,
  odjel, djelatnost ili oznaku polja, sada ostaje netaknuta. Stvarni
  podaci o mjestu ostaju nedirnuti, pa i oni koji su ujedno takva riječ
  („4692 Mjesto“). Time nije riješen slučaj kad iza broja stoji sasvim
  obična riječ („3390 Polica“) – za to je potreban popis poštanskih
  brojeva.
- **Pomoć je spominjala stavku izbornika koja ne postoji.** Uputa, slika
  i poruka na kraju instalacije govorile su o „Očisti dokument za AI“; no
  stavka u kontekstnom izborniku zove se „Ukloni osobne podatke“. Tko je
  slijedio pomoć, tražio je uzalud. Sva tri mjesta sada navode stavku
  izbornika onako kako se stvarno zove.
- **„Pokreni sa sustavom“ nije se dalo isključiti.** Tko je pri
  instalaciji označio „Pokreni s Windowsom“, u postavkama je ipak vidio
  praznu kvačicu – i teže: uključivanje i isključivanje u aplikaciji
  ostajalo je bez učinka, program se i dalje pokretao s Windowsom.
  Razlog su bila dva mjesta na kojima Windows traži programe za
  pokretanje; aplikacija je poznavala samo jedno od njih. Sada se broje
  oba, prekidač pokazuje stvarno stanje i djeluje u oba smjera.
  Uzeto je u obzir i sljedeće: tko isključi stavku u Upravitelju
  zadataka, sada to vidi u aplikaciji – a tko je ondje ponovno uključi,
  time poništava isključivanje.
- **Naslovi iznad popisa imena bili su zacrnjeni.** „POPIS SUDIONIKA
  RADIONICE“ ili „PREGLED DJELATNIKA UNUTARNJE SLUŽBE“ iznad popisa osoba
  nestajali su kao navodno ime. U velikim slovima jezičnom modelu
  nedostaje njegovo najbolje razlikovno obilježje, a u njemačkom je
  svaka imenica pisana velikim slovom – „Popis sudionika radionice“ tada
  izgleda kao „Anna Huber“. Složenice na `-liste` (popis), `-dienst`
  (služba), `-gespräch` (razgovor), `-sitzung` (sjednica) i
  `-besprechung` (sastanak) sada ostaju netaknute. Same osnovne riječi i
  dalje vrijede kao ime: *Liste* i *Dienst* su postojeća prezimena,
  *Teilnehmerliste* nije.
- **Podaci ispisani okomito dobivali su nečitljivo rezervirano mjesto.**
  Brojevi predmeta na rubu stranice, kratice obrađivača uz uvez, okomiti
  zaglavlja tablica: takvi su podaci bili pronađeni i uklonjeni, ali
  rezervirano mjesto ispisivalo se poprijeko preko teksta, sažeto na
  jednu do dvije točke i ponekad izvan ruba papira. Sada slijedi tekst –
  okomito, u čitljivoj veličini i u istom smjeru u kojem je podatak
  stajao. Isto je vrijedilo za stranice koje su naknadno zaokrenute
  (vodoravno napisan tekst s upisanim zaokretom stranice, kakav
  isporučuju neki izlazni programi); i ondje rezervirano mjesto sada
  stoji onako kako se stranica gleda. „Poštovana gospođo doktorice
  Anneliese Berger“ davalo je kao ime samo „Anneliese“ – „Berger“ je
  ostajalo u dokumentu. Isto je vrijedilo za svako ime s drugim imenom
  („Gospođa Anna Maria Berger“). Razlog je bilo pravilo za ime iza
  oslovljavanja: imalo je dva mjesta za riječ, a titula ili drugo ime
  trošili su prvo. S „dr.“ to nikada nije bilo uočljivo – točka prekida
  pravilo, pa je jezični model zahvatio cijelo ime. Sada se titule
  preskaču bez trošenja mjesta, a ime smije imati tri dijela. Uloga
  **iza** imena i dalje ne prolazi: „Gospođa Anna Huber direktorica“
  zamjenjuje ime, ne ulogu.
