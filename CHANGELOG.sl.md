Kaj se spreminja iz različice v različico – opisano z vidika uporabe programa,
ne njegove notranjosti. Kdor želi vedeti, *iz česa* je zgrajen, najde to v
[LIZENZEN.md](LIZENZEN.md); tu piše, kaj se spreminja za delo z njim.

Številčenje sledi običajnemu štetju: **prva** številka se spremeni,
ko nekaj ne deluje več tako, kot je delovalo prej, **druga** ob novih
zmožnostih, **tretja** ob odpravljenih napakah.

## 0.10.52-alpha.20260903 – 3. september 2026

- Obdelava več kot štirih datotek se po več odgovorih v oknih predogleda ne
  ustavi več. Naslednji dokumenti se še naprej pripravljajo v ozadju; po
  odgovoru se pripadajoča datoteka zdaj zanesljivo dokonča, s čimer se sprosti
  naslednje mesto v čakalni vrsti.
- Ujemanje kratkih oznak podjetij v PDF-jih je zdaj omejeno na prepoznano
  besedilo v slikah. Zato v običajnem besedilu strani dolg večvrstični zadetek
  modela ne povzroči več dodatnega zakritja enake posamezne besede na drugem
  mestu.

## 0.10.51-alpha.20260903 – 3. september 2026

- Seznam sprememb se zdaj prikaže v izbranem jeziku – na
  maskuro.com/neuigkeiten in v programu pod »Spremembe« ter v »Kaj je novega«
  po posodobitvi. Doslej je bilo v vseh osemnajstih jezikovnih različicah pod
  prevedenim naslovom besedilo v nemščini. Kjer prevod še manjka, ustrezna
  različica ostane v nemščini, namesto da izgine; seznam različic je povsod
  enak.

## 0.10.50-alpha.20260903 – 3. september 2026

- Ponavljajoči se znaki podjetij v PDF-jih se zdaj čistijo skladno, tudi
  kadar optično prepoznavanje besedila napis na eni strani prebere drugače
  ali okrogli znak povsem izpusti. Izrecna odizbira v predogledu pri tem
  ostaja zavezujoča in je noben poznejši nadaljnji zagon ne more razveljaviti.
- Cene brez valute v skeniranih tabelah se zdaj v celoti zakrijejo tudi,
  kadar glava tabele in vrednosti ležijo v različnih prekrivajočih se
  slikah PDF. Količine, ure, teže in odstotki ostanejo; daleč narazen
  ležeče številke se ne povežejo več pomotoma v en znesek.
- Iskanje podpisov zdaj zajame tudi zasedene šibke modre napise in ozke
  rdeče podpisne kratice. Pikčaste diagrame, merilne krivulje, žige,
  logotipe in široke rdeče urejevalne oznake ta ozki nadaljnji zagon še
  naprej izvzema.
- Zakritja v zasukanih, zrcaljenih, strižno popačenih ali obrezanih slikah
  PDF zdaj zadenejo pravi slikovni mnogokotnik. Tehnične vloge v postavkah
  storitev, stvarne besede za vozila in pnevmatike ter tehnična
  „kompenzacija" so hkrati ožje razmejene proti napačnim najdbam; izrecno
  označene kontaktne vloge in telefonske številke ostajajo zaščitene.
- Vidno preverjanje pred shranjevanjem PDF-ja okna ne zamrzne več: pri
  velikih dokumentih s številnimi najdbami je doslej stalo več sekund brez
  odziva; zdaj se pokaže opozorilo, da poteka preverjanje, okno pa se še
  naprej izrisuje.
- Obnavljanje vrednosti iz slike v urejevalniku Popravi zdaj vsako izvirno
  sliko prebere z optičnim prepoznavanjem le enkrat; doslej je to teklo
  znova ob vsakem nadaljnjem preklicu za iste slike.
- Nalaganje visoke stopnje in modela podpisov zdaj potrebuje komaj še
  pomnilnika: 596 MB velik paket je bil doslej v celoti držan v pomnilniku,
  preverjen in tam razpakiran – prek gigabajta vrha med tekočim programom,
  na računalnikih z 8 GB trenutek, ko je vse začelo zatikati. Zdaj teče na
  disk po blokih in se tam preveri ter razpakira.
- Iskanje v urejevalniku Popravi ne zamrzne več velikih PDF-jev: prva črka
  v iskalnem polju je doslej naenkrat prebrala vse strani – pri 200 straneh
  je okno stalo dve sekundi, in po vsakem zakritju še enkrat. Strani se zdaj
  berejo po koščkih; do takrat v števcu piše „Se bere …", rezultat pa je
  enak.
- Rastrirane strani PDF – po optičnem prepoznavanju besedila ali kadar
  besedila ni bilo mogoče čisto odstraniti – se zdaj shranijo znatno manjše
  in brez izgube slike: namesto vedno kot JPEG se vsaka stran kodira tudi
  brez izgub, v datoteko pa pride manjša različica. Očiščen sken se tako
  skrči z 248 na 48 KB, vadbeni dokument z optičnim prepoznavanjem besedila
  z 913 na 702 KB; besedilo ostaja ostro.
- Naknadno naloženi modeli (visoka stopnja, podpisi, obrazi, drugo optično
  prepoznavanje) se po desetih minutah brez čiščenja znova sprostijo iz
  pomnilnika. Doslej so ostali naloženi do konca programa – kdor je enkrat
  uporabil iskanje podpisov in visoko stopnjo, je trajno zasedel prek dveh
  gigabajtov. Naslednji zagon jih znova naloži v eni do dveh sekundah;
  vrstica stanja to sporoči.
- PowerPoint: generična imena postavitev in matric prosojnic („Prazna",
  „Naslovna prosojnica") se ne zamenjajo več kot navedba. „Prazna" je tudi
  kraj in se je v vsaki nemški in angleški predstavitvi napačno zakrivalo;
  zdaj se čistijo le ročno dodeljena imena samih prosojnic.
- V PDF-jih glajenje vrstic ne potegne več glave naslednje vrstice v
  najdbo: številka naslednje postavke seznama za datumom je veljala za
  telefonsko številko, glava polja, kot je „Šifra" ali „Številka naročila",
  za piko za znesek pa je veljala za poštno številko s krajem, vrstica
  kraja pod naslovom pa je podvojila kraj. Pravilna, krajša najdba je bila s
  tem izpodrinjena. Na 132 korpusnih PDF-jih od 24 dodatnih najdb glajenja
  ostaneta pravi dve; v praksnem korpusu se lažni alarmi zmanjšajo z 29 na
  21 pri enaki stopnji najdb.
- „Preišči in zakrij mapo PDF" v urejevalniku Popravi ne blokira več okna:
  zagon teče v ozadju, napredek in gumb za preklic se odzivata, meniji ali
  zavihki pa se ne dajo več upravljati sredi napol dokončane datoteke.
- Skenirane strani z najdbami se pri zakrivanju zdaj na novo zapišejo le
  enkrat namesto dvakrat: doslej je program okvirčke najdb in okvirčke
  utemeljitev polnil v dveh prehodih, drugi pa je ravno na novo shranjeno
  skensko sliko stisnil še enkrat. To prihrani čas pri velikih skenih in
  izgubo kakovosti slike.
- Listanje, približevanje in sličice v urejevalniku Popravi se odzivajo
  hitreje: vsaka izrisana stran je doslej šla kot PNG skozi stiskanje in
  takoj nazaj, samo da bi bila prikazana – pri zaslonih z visoko ločljivostjo
  približno desetinko sekunde na stran. Slika zdaj pride neposredno,
  slikovna točka za slikovno točko enaka.
- Vidno preverjanje pred shranjevanjem PDF-ja („preizkus izhoda") je
  približno trikrat hitrejše, ob enakem rezultatu.
- Glavno okno se pojavi še približno četrtinko sekunde prej: preverjanje,
  ali je optično prepoznavanje besedila na tem računalniku pripravljeno, je
  doslej teklo ob izgradnji okna – na Macu vključno s preizkusno zahtevo
  sistemskemu prepoznavanju –, stran z nastavitvami dodatnih komponent pa je
  ob tem poizvedela stanje vseh 48 jezikov. Oboje se zdaj zgodi v ozadju
  oziroma šele, ko je jezikovni seznam resnično odprt; do takrat piše
  „Preverjanje optičnega prepoznavanja besedila …".
- Po iskanju podpisov program porabi približno 300 MB manj pomnilnika:
  prepoznavalni model je bil dotlej podvojen v pomnilniku – enkrat za
  preverjanje pristnosti, enkrat za računanje. Preverja se še naprej, le
  brez druge kopije.
- Optično prepoznavanje besedila v PDF-jih je opazno hitrejše: za vsako
  glavo polja na strani („Datum rojstva:", „Davčna številka:") je bila
  doslej za vsako vrsto navedbe poslana lastna poizvedba skozi
  prepoznavanje – na vsaki strani znova, tudi če je ista glava stala že
  deset strani prej. Odgovor si zdaj zapomni; dvostranski popis storitev je
  tako postavil 324 vprašanj, zdaj le še različna. Najdbe so enake.
- Velike preglednice se spet čistijo v sekundah namesto minutah: v
  anonimizirajočem načinu – privzetem – je bilo usklajevanje že znanih
  vrednosti z vsako nadaljnjo celico počasnejše, ker se je vmesni
  predpomnilnik ob vsaki najdbi zavrgel in zgradil na novo. 5.000 celic je
  za to potrebovalo približno 18 sekund, zdaj pol sekunde; rezultat je
  znak za znakom enak.
- Glavno okno se pojavi še znatno hitreje: seznam držav v nastavitvah je
  ob izgradnji okna v ospredje potegnil celotno prepoznavalno knjižnico –
  približno 0,7 sekunde na Macu, na Windows ustrezno več –, čeprav so za to
  potrebna le imena držav. Seznam zdaj izhaja iz lahkega kataloga; knjižnica
  se nalaga po načrtu v ozadju, medtem ko okno že stoji. To velja tudi po
  vsaki menjavi jezika ali videza, ki program znova zažene.
- Laboratorij dokumentov zdaj obrezane glave polj, krajevne sence vrednosti
  in močne skenske obreze v celoti izvaja skozi vsebnike PDF, DOCX in ODT.
  Matrika obsega 680 datotek iz 40 družin dokumentov in 17 osi vsebnikov.
  Maskuro v novih ter v popolnih osnovnih in značilnostnih profilih
  odstrani vse ciljne navedbe, brez izmerjenega lažnega alarma, poškodovane
  ohranitvene vrednosti ali prekinitve.

- Večkrat uporabljeni skeni se zdaj preverijo in očistijo prek vsake vidne
  postavitve: laboratorij dokumentov isti slikovni predmet deli med
  različnimi stranmi, velikostmi in zasuki v PDF-ju ter isti slikovni del
  večkrat referencira v DOCX in ODT. Tehnična imena okvirov ODT, kot je
  „Formularscan klein quer", ne veljajo več za osebo; prosta imena in kraji
  s podobnim začetkom ostajajo zaščiteni. Splošno uganjevanje obrazcev
  zaključnega poteka strani PDF na že samostojno prebrani slikovni površini
  ne more več ustvariti večje napačne najdbe naslova. 120 novih vsebnikov v
  osnovnem in značilnostnem profilu doseže vseh 813 oziroma 840 ciljnih
  navedb brez lažnega alarma, kršitve ohranitve ali prekinitve; popolni
  prevzem značilnosti na 800 datotekah potrdi 5.600/5.600.

- Nemški laboratorij OCR zdaj obsega 560 skenov iz 40 družin dokumentov.
  Nove različice obrežejo robove glave polja in strani ali položijo senco
  neposredno čez vrednost. Maskuro pri tem ščiti tudi imena, naslove,
  datume rojstva, medicinske šifre in označene identifikacijske številke z
  delno poškodovano oznako. Hkrati se ostanki polj obrazcev, uradni naslovi
  ter stvarni pravni in informacijski izrazi ne zamenjajo več kot osebe ali
  kraji. Popolna osnovni in značilnostni profil dosežeta 3.794/3.794
  oziroma 3.920/3.920 ciljnih navedb brez izmerjenega lažnega alarma ali
  prekinitve.

- Samodejna izbira slik v PDF-ju velikih fotografij izdelkov, energijskih
  nalepk in vrst portretov ne odstrani več le zato, ker se začnejo na
  zgornjem robu strani. Prave ploščate slike glave/noge in briefne glave, ki
  se začnejo ob robu lista, še naprej padejo. V imenikih zaposlenih se
  imena zdaj prepoznajo tudi iz strukturno ponovljenih vnosov, kadar je
  viden naslov dokumenta na voljo le kot slika. Prepoznavanje ni več
  prikrojeno le dvema konkretnima vlognima besedama in kratici „DW": ena do
  štiri prelomljene vloge ter „Durchwahl", „Nebenstelle", „Ext." in
  „Extension" se zdaj sklepajo iz skupne oblike. Vloge in naslovi odsekov
  ostanejo, tudi kadar jezikovni model po razrešitvi prekrivanja pusti le
  vlogni pridevnik. Vodoravne mreže vlog ne veljajo več pomotoma za stolpce
  imen. Če OCR strani zlepi več kartic v izjemno široko besedo z notranjimi
  velikimi črkami, ozek krajevni protipogled loči prave besedne okvirčke;
  zaradi tega ne ostane niti posamezno ime niti široka napačna proga.
  Ponovljeni večvrstični logotipi podjetij se zakrijejo na podlagi že
  potrjene enake slikovne predloge tudi na straneh brez uporabnega besedila
  OCR in ob odstopanju lege do dveh slikovnih točk; krajše lokalne druge
  branja OCR pri tem ne smejo več dopolniti večjega glavnega območja kot
  izmišljeno ime. Številke strani pred glavo dopisnega papirja podjetja ne
  sodijo več k imenu organizacije, številčno začeta prava imena znamk
  ostajajo zaščitena. Več izmerjenih izdelčnih, strokovnih in obrazčnih
  besed se ne predlaga več kot osebe.

- Iskanje podpisov v PDF-jih zdaj teče šele po čiščenju slik OCR, obišče
  tudi strani brez običajne besedilne najdbe in pravilno preračuna okvirčke
  najdb zasukanih strani nazaj v prostor dokumenta. Goste fotografije
  izdelkov se ne zakrijejo več kot podpis. Nad enolično označenimi polji
  podpisa ozka rezervna možnost s črto zapre tanke vrzeli modela; prazne
  črte s prednatisnjenim datumom je ne sprožijo.
  Čisti skeni izključno z najdbami OCR/podpisov v tej fazi ne prekinejo več
  zaradi zakrivalnika slik, naloženega šele v besedilni veji.

- Veliko hkrati odprtih dokumentov ostaja v urejevalniku Popravi
  razločljivih: zavihki se ne skrčijo več na golo tripičje, gumb seznama
  desno pa pokaže vsa polna imena datotek drugo pod drugim. Zavihke je
  mogoče prerazvrstiti z vlečenjem in jih z njihovim križcem odstraniti iz
  istega seznama kot v glavnem oknu; nešranjeno delo se pri tem še naprej
  najprej razjasni. Desni klik poleg tega ponudi „Zapri", „Zapri druge
  zavihke" in „Zapri zavihke na desni".

- Kratkotrajna blokada Windows zaradi protivirusnega programa ali
  iskalnega indeksa mape z dokončano naloženim jezikovnim modelom oziroma
  slovarjem ne spodleti več ob sklepni zamenjavi z „Dostop zavrnjen".
  Maskuro to zadnjo menjavo mape zdaj za kratek čas poskusi znova.

- Nemški laboratorij dokumentov zdaj preverja vsebnike tudi z menjajočim se
  zasukom strani PDF, neodvisno zasukanimi slikami PDF ter merjeno
  spremenjenimi in obrezanimi slikami tabel v DOCX in ODT. Vrednosti polj v
  vidno zasukanih slikah se spet v celoti prepoznajo, tehnične oznake
  stolpcev se ne zamenjajo več kot kraji, imena s skupnim priimkom pa se ne
  razdelijo več z usklajevalnim naknadnim pregledom na podvojene delne
  najdbe. Na 320 datotek podvojena matrika ob vklopljenem prepoznavanju
  datumov, denarja in medicine doseže 2.240/2.240 ciljnih navedb brez
  izmerjenega lažnega alarma ali prekinitve.

- Večstranski slikovni PDF-ji, mešani besedilno-slikovni PDF-ji ter v DOCX
  ali ODT vdelani skeni se zdaj preverjajo v lastnem laboratoriju s 160
  datotekami prek vseh 40 nemških družin dokumentov. Tehnična imena
  okvirov ODT in označene kode naprav se ne zamenjajo več kot kraji; prava
  imena, kraji in naslovi v istih strukturah ostajajo zaščiteni. Ob
  vklopljenem prepoznavanju medicine ali denarja se poleg tega neposredno
  sledeč odmerek oziroma plačilni interval v celoti odstranita. Zagoni
  vsebnikov, osnovnega besedila, značilnosti besedila in značilnosti OCR
  skupaj dosežejo svoja polna stanja brez izmerjenega lažnega alarma ali
  prekinitve.

- Varnostno preverjanje pred shranjevanjem zdaj sumljiva mesta PDF-ja kaže
  kot posamično izbirljiv seznam. „Preveri v urejevalniku" odpre natanko
  izbrano stran in označi območje; prekrivajoče se delne najdbe na istem
  mestu se prikažejo le še enkrat. Nova besedila vmesnika so v celoti na
  voljo v vseh 17 prevedenih jezikih vmesnika.

- Datoteke Markdown pri zamenjavi ohranijo svojo skladnjo sklicev,
  poudarkov in opomb. Maskuro za to prebere znakovno enako dolgo različico
  brez oznak Markdown; podčrtaji v e-poštnih naslovih, računske zvezdice in
  navadni sklici brez osebne navedbe ostanejo nespremenjeni.

- Več rokopisnih vnosov na isti strani PDF se zdaj išče v do treh
  prehodih. Že najdene poteze se skrijejo le na delovni sliki, da ne
  izpodrivajo več šibkejših podpisov; na zasukanih straneh zakrivne
  površine spet pristanejo na vidnem mestu najdbe. Slikovne zapolnitve
  prejšnjih varnostnih faz ostanejo ohranjene pri poznejšem zapisu nazaj.

- „Ponastavi vse nastavitve" zdaj zajema tudi „Besedilo na slikah". Če
  komponenta OCR ni na voljo, stikalo tehnično ostane izklopljeno, ne da bi
  bilo pomotoma označeno kot odstopajoče od dostavljenega stanja.

- Veliki slikovni fragmenti na zgornjem robu strani ne veljajo več za glavo
  le zaradi svoje lege. Zaradi tega ostanejo ohranjeni zlasti na sliki
  temelječi opisi izdelkov in vsebine tabel. Na novo prepoznane, po vrsti
  natančne najdbe e-pošte in obrazcev se poleg tega tudi na že preverjeni
  slikovni površini ne izločijo več iz sklepnega vidnega preverjanja.

- Tehnične vrstice postavk in artiklov v ponudbah za klimo in elektriko so
  ožje razmejene od oseb, krajev in organizacij. To zadeva med drugim vrste
  kablov, napajanje AC, številke postavk ter velike kode izdelkov; prava
  imena in naslovi ostajajo zaščiteni.

- Preverjanje resničnih očiščenih PDF-jev sestavin cene, kot je `1 699,59`,
  ne zamenjuje več s telefonskimi številkami in iz popolnega datuma, kot je
  `08.05.2025`, ne izreže več domnevne navedbe kartice. Imena za nagovorom
  se končajo na prelomu vrstice namesto v naslednji ulici; imena krajev v
  imenih datotek prilog so omejena na dejanski kraj. Barve vozil, tehnične
  statusne vrednosti, oznake dejavnosti in pravne oblike izdelkov prav tako
  ostanejo. Poškodovana branja ograd, kot je `|PLLZ`, se ob drugem prehodu
  OCR ne obravnavajo več znova kot osebna navedba.

- Postrani shranjene slike PDF pri sklepnem vidnem preverjanju dobijo
  dodaten pogled v svoji nespremenjeni slikovni legi. Ta sme naknadno
  zakriti izključno vrednosti, ki jih je Maskuro na isti strani že zanesljivo
  prepoznal. Tako se na primer majhen zasukan naslovni žig v celoti prekrije,
  ne da bi si izmislili nove besede iz slikovnih naslovov ali tehničnih
  risb kot osebne navedbe.

- V besedilih OpenDocument se zdaj skupaj z avtorjem izpraznejo tudi
  avtorjeve začetnice opombe (komentarja). LibreOffice jih poleg polnega
  imena shrani kot lastno kratko obliko in prav to prikaže ob robu strani;
  doslej je tam ostal „SO", medtem ko je bila „Sieglinde Ortner" zraven že
  zdavnaj ograda. Izprazni se le, če je bil avtor resnično zamenjan – opomba
  oddelka obdrži svojo oznako.

- V italijanskih poslovnih dopisih standardne fraze na začetku stavka ne
  veljajo več za ime ali kraj: „Restiamo a disposizione", „Rimaniamo",
  „Attendiamo", „Alleghiamo", „Comunichiamo" in „Auguriamo buon lavoro" so
  doslej ostajale kot domnevna oseba ali navedba kraja. Prava imena na istem
  mestu („Rossi Mario") se še naprej prepoznajo.

- Dvostolpčni skeni zdaj ščitijo označene identifikacije in navedbe krajev
  tudi, kadar optično prepoznavanje besedila najprej vrne vse glave polj in
  nato vse vrednosti. Pripis sledi vidni slikovni vrstici in deluje tudi na
  za 90 stopinj zasukanih straneh. Tesno ločeni deli identifikacije potnega
  lista ali pogodbe se zakrijejo skupaj; označeni datumi rojstva ter šifre
  ICD in PZN so prav tako pokriti, sledeče stvarne besede ostanejo.
  Kratka imena in uporabniška imena so zaščitena pri natančnih poljih; v več
  besed OCR razdeljeni e-poštni naslovi le pri tesni soseščini in popolni
  slovnici e-pošte. Poljsko vezana popravka zamenljivih znakov ter krajevno
  ponovno branje še praznega osebnega polja zaključita poškodovane in
  zasukane skene, ne da bi razširila stvarna polja ali že zasedene
  vrednosti. Varnostni robovi sledijo velikosti besede, značilnostni profil
  pa zajame neposredno sosednje enote odmerka in plačilne intervale. Rahlo
  postrani vložene obrazce se geometrijsko povratno projicira iz več
  smerno skladnih vrstic OCR; zaokroževalni šum ali nasprotujoče si priče
  ne zadoščajo. Kratke črkovne predpone ostanejo pred identifikacijo z
  vezajem, popoln označen naslovni fund pa zamenja le svoj sorodni delni
  fund ulice. Napačno prebrana glava vlognega polja pade izključno v
  stolpcu obrazca, zasedenem z vsaj tremi znanimi glavami; imena v klepetu
  ostajajo zaščitena. Tesen robni obrez in lokalna preosvetlitev z
  diagonalnim svetlobnim odsevom dopolnjujeta slikovno matriko. Najdbe
  oseb, krajev in podjetij, ki segajo čez več vrstic obrazca, so v
  večkrat zasedenem stolpcu polja omejene na ustrezno vrednost. Tehnična
  vrednost postavke pade le z glavo postavke in ustrezno obliko oznake;
  prava imena ostajajo zaščitena. Tudi na svetlobnem odsevu prekinjene
  vrednosti e-pošte se odstranijo za izrecno glavo polja e-pošte s tesnim,
  na sosede omejenim slikovnim robom. Dva para polje-vrednost iste vidne
  vrstice se zdaj vrednotita neodvisno; vrednosti na globlji osnovni črti
  se povežejo šele po treh ujemajočih se geometrijskih pričah. Zaradi tega
  identifikacijske številke, datumi rojstva in naslovi ostanejo v celoti
  zaščiteni tudi v gostih postavitvah obrazcev. Ulica, poštna številka in
  kraj se združijo izključno znotraj istega polja naslova in z ustrezno
  poštno slovnico. Tesno omejena stvarna polja za delovna/pomožna sredstva
  in zobni status ne ustvarjajo več lažnih alarmov krajev ali imenikov;
  prava imena in podobno poimenovana polja ostajajo zaščitena. Nemški
  laboratorij dokumentov zdaj obsega 440 skenov in doseže 2.981/2.981 v
  osnovnem profilu ter 3.080/3.080 v značilnostnem profilu. Vseh enajst
  slikovnih mutacij in vseh 40 družin dokumentov je pri 100 odstotkih,
  še vedno brez izmerjenega lažnega alarma, kršitve ohranitve ali
  prekinitve.

- Besedilne plasti PDF z izgubljenimi ločili celic zdaj omejujejo najdbe
  organizacij, naslovov in krajev glede na ponovljeno strukturo polje-
  vrednost. Glave polj pred vrednostmi podjetij in tehnične puščice, kot sta
  `=>` ali `->`, ne sodijo več k najdbi. Dodaten pogled za mehke prelome
  vrstic ne sme več razširiti najdb pravne oblike in kraja čez več vrstic
  tabele; že popoln naslov se konča pred naslednjo glavo polja skupaj z
  vrednostjo. Sklepni zagon prek vseh 1.600 dokumentov TXT, HTML, PDF in
  DOCX odstrani 10.840/10.840 ciljnih navedb pri nič lažnih alarmih, nič
  kršitvah ohranitve in nič prekinitvah.
