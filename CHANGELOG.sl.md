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

## 0.10.44-beta.1 – 1. september 2026

- Izgradnja paketa ustvari ločene izdaje za Windows x64 in ARM64, macOS na
  Apple Silicon in Intelu ter Linux x64 in ARM64. Imena paketov, izbira
  posodobitev in sprostitve ločijo arhitekturo; objava ostane zaklenjena,
  dokler manjka eden od šestih ciljev ali njegovo dokazilo o odvisnostih.
  Linux ARM64 zaradi Qt zahteva vsaj glibc 2.39. Na resnični strojni opremi
  sta zaenkrat v celoti prevzeta le Windows x64 in macOS na Apple Silicon;
  preostali arhitekturni paketi so jasno označeni kot predizdaje za
  preizkušanje in ne za produktivno rabo.

- Pri več datotekah prepoznavanje zdaj dela naprej, medtem ko predogled
  čaka na pregled. Do trije pripravljeni predogledi se prikažejo zaporedoma;
  hkrati še vedno računa le en dokument, datoteka rezultata pa nastane šele
  po njegovi sprostitvi. Trajna izjema, izbrana v predogledu, velja tudi za
  že pripravljene naslednje dokumente.

- Redakcijska potrdila je zdaj mogoče kadar koli neposredno v meniju
  Datoteka preveriti proti zakritemu dokumentu. Maskuro pri tem loči
  ustrezno podpisano datoteko, ustrezno a nepodpisano dokazilo, neveljaven
  podpis in dokument, ki ne pripada potrdilu. Licenca ali izvirni sistemski
  račun za protipreizkušnjo nista potrebna.
  Za samodejna preverjevalna mesta je ista primerjava na voljo prek
  `--zertifikat-pruefen`; povratne kode ločijo ujemanje, napako uporabe in
  neveljavno dokazilo.
  Protipreizkušnja dodatno primerja vdelano oznako Maskuro s potrdilom;
  poljubno vpisana tuja oznaka zato pade v oči tudi pri nepodpisanem
  dokazilu.
  Pri veljavnem podpisu preverjevalni izsledek poleg tega pokaže
  obdelovalca, ki ga je aktivirala uprava, s sistemskim računom, tehnično
  oznako računa in platformo. Nepotrjene navedbe iz nepodpisanih ali
  neveljavnih dokazil se ne izpišejo.

- Nov nemški laboratorij dokumentov ustvari 160 povsem sintetičnih listin
  TXT, HTML, PDF in DOCX iz desetih področij in štirih strukturnih
  različic. Manifest zdaj izrecno loči med navedbami, ki morajo izginiti,
  in strokovnimi besedili oziroma stvarnimi identifikacijami, ki morajo
  ostati; družina dokumenta, mutacija in javni strukturni vir so sledljivo
  zabeleženi.

- Nemški laboratorij dokumentov je razširjen na 280 datotek, sedem
  strukturnih oblik, 1.540 ciljnih navedb in 1.036 sider ohranitve. Na
  novo se preverjajo oštevilčeni obrazci, oklepajna polja PDF/mask in
  tehnične dodelitve `=>`. Razširjeno polno stanje doseže v TXT, HTML, PDF
  in DOCX vsakič 100 odstotkov pri nič lažnih alarmih. Oklepajna polja
  datumov in identifikacijskih številk, puščični ločevalniki in izrecno
  označena združenja se zdaj strukturno prepoznajo.

- Druga razširitev laboratorija dvigne zbirko na 400 dokumentov, deset
  strukturnih oblik, 2.200 ciljnih navedb in 1.480 sider ohranitve.
  Vrednosti ključev v obliki JSON, seznami YAML in obrazčna polja z
  velikimi črkami skupaj z dosedanjo zbirko dosežejo 100 odstotkov pri nič
  lažnih alarmih. Citirani datumi rojstva in identifikacijske številke ter
  izrecno označene vloge, kot so zavarovane, prijavljajoče, k oddaji
  zavezane in zastopanju pooblaščene osebe, se zdaj prepoznajo tudi v teh
  izvoznih oblikah.

- Ločen način OCR nemškega laboratorija dokumentov dodatno ustvari 200
  golih slikovnih skenov iz vseh 40 družin. Čiste, nizkokontrastne, nizko
  ločljive, z artefakti JPEG obremenjene in za 90 stopinj zasukane strani
  se ponovno izmerijo z natančnimi slikovnimi okvirčki, ne da bi spremenile
  primerljivo osnovno stanje 1.600 besedilnih datotek. Manifest loči
  vklopljive značilnosti datuma, denarja in medicine od osnovnega profila
  ter pozna dokazana branja OCR, ne da bi jih štel kot dodatna ciljna
  mesta. Meritev je razčlenjena po mutaciji in družini dokumenta. Tesne
  meje polj med drugim preprečujejo, da bi „Az" v imenu kraja „Graz"
  naslednji datum zakril kot opravilno številko; trenutna osnovna matrika
  teče z nič lažnimi alarmi in nič prekinitvami.

- Pet nadaljnjih nemških družin dokumentov za račun/dobavnico,
  banko/kredit, najem/upravo stavbe, šolo/visoko šolo in
  logistiko/carino razširi laboratorij na 600 datotek s 3.520 ciljnimi
  navedbami in 2.360 sidri ohranitve. Ozka pot tabel PDF uporabi izrecno
  glavo `Polje Navedba`, kadar besedilna plast izgubi ločila celic; nova
  izbira `--familien` pospeši delne meritve. 200 novih datotek doseže
  1.320/1.320 pri nič lažnih alarmih in nič prekinitvah.

- Zavarovanje/škoda, delo/plača, medicina/laboratorij, vozilo/servis in
  tehnika/vzdrževanje razširijo nemški laboratorij dokumentov na 800
  datotek s 4.960 ciljnimi navedbami in 3.200 sidri ohranitve. Ozko
  označene police, identifikacije pacientov, preizkuševalcev in vozil ter
  nova polja vlog, naslovov in organizacij se prepoznajo. Nova delna
  matrika in polna matrika dosežeta 100 odstotkov pri nič lažnih alarmih
  in nič prekinitvah v TXT, HTML, PDF in DOCX.

- Gradnja/razpis, energija/okolje, društvo/združenje,
  komunikacija/koledar in hotel/prireditev dvignejo nemški laboratorij
  dokumentov na 1.200 datotek s 7.920 ciljnimi navedbami in 4.800 sidri
  ohranitve. Nova polja vlog, podjetij, naslovov, registra, oddaje naročil,
  rezervacij in uporabniških računov se prepoznajo tudi v vseh izvoznih
  oblikah. Številke števcev ostajajo ohranjene kot stvarne identifikacije.
  Delna in polna matrika dosežeta 100 odstotkov pri nič lažnih alarmih in
  nič prekinitvah.

- Gostinstvo/dostava, lekarna/recept, pogreb/pokopališče, šport/članstvo
  in nepremičnine/posredništvo razširijo nemški laboratorij dokumentov na
  1.400 datotek z 9.360 ciljnimi navedbami in 5.640 sidri ohranitve. Nove
  osebne vloge, polja naslovov in številke iskalnih naročil se prepoznajo.
  Označena imena podjetij s pravno obliko ostajajo v celoti zaščitena tudi
  čez samodejni prelom vrstice; starostni razredi in strokovne glave se ne
  zamenjajo več napačno. Delna in polna matrika dosežeta 100 odstotkov pri
  nič lažnih alarmih in nič prekinitvah.

- Zobozdravstvo, avtošola, gasilci/intervencija, energetska skupnost in
  paketno potovanje razširijo nemški laboratorij dokumentov na 1.600
  datotek z 10.840 ciljnimi navedbami in 6.440 sidri ohranitve. Nove
  vloge, polja naslovov ter identifikacije zdravljenja, izobraževanja,
  intervencije, energije in potovalne pogodbe se strukturno prepoznajo.
  Nova delna matrika 200 datotek doseže 1.480/1.480; polna matrika doseže
  10.840/10.840. Obe ostajata pri nič lažnih alarmih in nič prekinitvah.

- Polna meritev laboratorija dokumentov je z ozkimi uradnimi stvarnimi
  oblikami in strukturnimi pravili znižala nepotrebne zamenjave z 68 na 0,
  izrecno izmerjene kršitve ohranitve z 23 na 0 in prekinitve s 3 na 0.
  Stopnja najdb se je hkrati dvignila z 91,1 na 100,0 odstotka; TXT, HTML,
  PDF in DOCX dosežejo vsak po 100 odstotkov. Splošne glave tabel, kot je
  „Polje", se zavrejo le v dokazanem zaporedju „Polje"/„Navedba"; enako
  zveneč priimek ostaja zaščiten. Sodne opravilne številke s končno črko,
  polja z enačajem, „Datum rojstva otroka" in več označenih posamičnih
  imen v isti vrstici se v celoti prepoznajo. Tabele Word in vrstice pred
  poljem uporabljajo svojo glavo polja kot začasni kontekst prepoznavanja;
  označeni naslovi PDF ostajajo v celoti zaščiteni tudi pri stavčno
  pogojenem prelomu vrstice.

- Nemška polja osebnih lastnosti, poklica in medicine zdaj delujejo tudi z
  Windows-prelomi vrstic. Enočrkovne navedbe spola, kot je „Spol"/„ž", so
  zaščitene v obliki pred vrstico. Stvarna polja „Artikel-PZN" pa ne
  sprožijo niti najdbe zdravilne šifre niti osebe; prave navedbe PZN, ICD
  in ATC ostajajo prepoznane.

- Nemška polja obrazcev in številk so natančnejša: „DW." zdaj deluje tudi
  pred mehkim prelomom vrstice, izrecno označena imena se odstranijo tudi
  pri malih začetnicah, izključno številska opravilna številka pa je
  dodeljena svoji pravi vrsti identifikacije. Obratno naključno
  Luhn-veljavna številka računa, dokazila ali artikla ne velja več za
  kreditno kartico. Sintetični preizkusi izpisa HTML in PDF potrjujejo
  odstranitev in ohranitev v dokončanem dokumentu.
  Identifikacijske številke in uporabniška imena se poleg tega prepoznajo,
  če njihova oznaka stoji v neposredno predhodni vrstici tabele ali
  obrazca; stvarne številke dokazil ostajajo vidne tudi v tej obliki.

- Gesla se zdaj prepoznajo tudi za samostojno glavo polja v prejšnji
  vrstici. Zaključni posebni znaki, kot sta `!` ali `#`, pri tem v celoti
  sodijo k zaščiteni vrednosti. Izdelčni in artiklovi PIN-i se obratno ne
  maskirajo več kot PIN kartice; izrecna polja „PIN" in „PIN kartice"
  ostajajo zaščitena.

- Male začetnice v vrednostih obrazcev se pri enoličnih nemških poljih
  naslova in „poštna št./kraj" zdaj izpišejo kot naslov oziroma poštna
  številka s krajem namesto le kot splošni kraj. Prav tako ostanejo z
  malo začetnico zapisane vrednosti podjetja, kot je „primer servis", za
  poljem podjetja v celoti zaščitene, ne da bi zadnjo besedo odrezale kot
  domnevno naslednjo glavo polja.

- Pomoč, pogosta vprašanja, besedilo o varstvu podatkov in spletna stran
  zdaj skupaj razlagajo dokazilo o izvoru: nevtralna oznaka Maskuro v
  dokumentu, neobvezna povezava s pravim sistemskim računom le v
  krajevnem dnevniku preverjanja, menjava uporabnika prek
  Windows/macOS/Linuxa ter pomenska vrednost SHA-256 in podpisa.

- Slikovno temelječi tehnični popisi del se čistijo bolj zadržano.
  Enolične stvarne besede, kot so „Odbijalno kladivo", „Odbitek za
  jamstvo", „Številke postavk", „Vgradna plošča" ali „Terminska
  situacija", ter sredi besede deljene oblike OCR ne veljajo več za osebo
  ali kraj. Prava ponudba občinske uprave se je s tem znižala s 140 na 90
  enoličnih zamenjav, ne da bi nastale nove najdbe; imena, kot so
  Schneider, Lang, Bauer in Hahn, ostajajo izrecno zaščitena.

- Odpravljeni so nadaljnji lažni alarmi iz pravih ponudb: „Digitalno
  podpisano" ne vsebuje več domnevne osebe, BIC se prepozna tudi brez
  dvopičja za svojo oznako, `15000 Alternativa` ne velja več za poštno
  številko s krajem, citat EU „(VO (EG) 715/2007" pa ne ustvari
  organizacije. Ponudba fotovoltaike se je s tem znižala z 26 na 16
  pojavitev zamenjav; prava imena, kraji in podatki o računu so ostali
  ohranjeni.

- V pregledih zaposlenih se kratica namestnika „Namestnik/-ca" in
  samostojno odcepljen naslov področja „FACILITY" ne zamenjata več kot
  osebno ime. Prava 13-stranska protipreizkušnja se je znižala z 878 na
  875 zamenjav; imena, interne številke in ime podjetja so ostali
  zaščiteni.

- Očiščene datoteke PDF, OpenDocument in Office dobijo nevtralno oznako
  `MASKURO-…` v svojih lastnostih dokumenta. Poročilo o preverjanju in
  podpisan dnevnik preverjanja nosita isto oznako ter vrednosti SHA-256
  vira in rezultata; redakcijsko potrdilo prevzame oznako iz dokončane
  datoteke. Uporabniško ime se doda le, če uprava izrecno vklopi
  obstoječe polje uporabnika.

- Glavno okno in nastavitve so mirneje razporejeni: Shrani, Kopiraj,
  Podrobnosti, Kazalniki in brisanje profila prepoznavanja se prikažejo
  šele, ko je ustrezno dejanje mogoče. Tehnične kratice jezikov OCR in
  dolgi primeri stojijo po potrebi v besedilu namiga namesto trajno na
  delovni površini. Stran za prepoznavanje se bolje prilagaja ožjim
  oknom, brez odrezanih razlag ali vodoravnega drsnika; opozorilo pred
  golim besedilom v seznamu zamenjav ostaja pri tem vidno.

- Prepoznavanje zajema nadaljnje nemške in mednarodne primere stikov:
  telefonske številke se zdaj preverijo za vse izbirljive državne regije,
  madžarske in hrvaške pogodbene vloge zdaj v celoti zajamejo tudi
  priimke, enake poklicu, oštevilčeni seznami nadomestnih delov/materiala
  pa ne sprožijo več lažnega alarma osebe zaradi „Mother / Flat". Osebna
  polja z očitno številčno stvarno vrednostjo se ne prevzamejo več kot
  ime; strojno berljivo območje potnega lista (MRZ) je poleg tega mogoče
  skupaj vklopiti in izklopiti prek skupine „Identifikacije".

- Podjetja brez pravne oblike se za dvoumnimi polji delodajalca bolje
  ločijo od oseb: imena, kot so „Huber Trgovina", „Müller Logistika" ali
  „Kowalski Trgovina", se v celoti zajamejo kot podjetje, medtem ko
  „Delodajalec: Bauer Anna" ostaja osebno ime. Samodejna izbira države pri
  francoskih dokumentih še naprej upošteva celotno francosko govorno
  območje, vključno z Luksemburgom.

- Prepoznani podpisi in osebno besedilo znotraj slike so bili doslej vedno
  prekriti s črnim pravokotnikom – tudi če je bila za zakrivanje
  nastavljena druga barva ali vzorec, kot je „mavrica". Ta slikovna
  območja zdaj prav tako prevzamejo izbrano zakrivno oblikovanje;
  prekrivna površina se še naprej zapiše neposredno v slikovne točke.

- Angleško prepoznavanje je bilo ponovno izmerjeno na enajstih ročno
  prevedenih pravih dokumentih in ciljno izboljšano: stanje zaloge,
  tehnična polja ponudb in spletne trgovine ter vloge v imenikih
  zaposlenih ostajajo vidni, „CV" se v vzorčnem stavku ne bere več kot
  pravna oblika, citirane pisave ostanejo ohranjene, imena v navpičnih
  glavah življenjepisov, večstranskih seznamih zaposlenih, za „Account
  manager" ter s številko začeta imena podjetij pa se v celoti prepoznajo.
  Avstrijske matične številke podjetja zdaj delujejo tudi za angleško
  oznako; kratka oblika „Customer:", registracijske številke EAR in
  številke delodajalca nosijo svojo vrednost. Merilne verige, vrste
  kablov, sklici na pravo EU, datumi veljavnosti ponudbe, kraji
  izpolnitve, pristojna sodišča, registrska sodišča, davčna kratica
  „NoVA", tehnične številke na oznakah pnevmatik ter sklici na standarde,
  kot sta „OVE R6-2" in „AStV", ne ustvarijo več lažnega alarma. Veljaven
  označen IBAN se čisto konča pred poljem registracije ali naslovom
  naslednje vrstice; naslovi z dodatkom obrtne cone se v celoti prepoznajo
  tudi iz besedilnih tokov PDF z Windows-prelomi vrstic. Angleški uvodi
  podjetij in strukturirana imena hranilnic se v celoti razmejijo. Država
  izvornega dokumenta ostaja ohranjena pri jezikovnih različicah za poštne
  številke in državno posebne identifikacije.

- V glavah prejemnika in sporočila je jezikovni model prvi dve imeni
  seznama, ločenega z vejico, lahko združil v eno samo najdbo („Bcc:
  Huber, Mayer"). Obe imeni se zdaj prepoznata, zamenjata in vodita v
  poročilu posamično – enako za „Sent:", „Reply:" in „Fwd:".

- Strojno berljivo območje potnega lista ali osebne izkaznice (MRZ) je
  manjkalo v skupinskem upravljanju „Kaj se išče". Zdaj sodi k
  „Identifikacije" in ga je mogoče skupaj s to skupino vklopiti in
  izklopiti.

- Kdor za nadomestna besedila izbere predlogo „Mavrica", zdaj dobi tudi
  zakrita mesta v istem videzu; doslej so presenetljivo ostajala
  klasično črna. Zakrivne površine je nato še naprej mogoče neodvisno
  preklopiti na drugo predlogo.

- Predal strani urejevalnika Popravi je po obnovitvi shranjene
  razporeditve oken lahko ostal prazen, dokler njegove širine niste ročno
  spremenili. Sličice se zdaj razporedijo na novo po vidni izgradnji
  okna in takoj stojijo sredinsko v predalu.

- Barvne preverjevalne oznake okoli nadomestnih besedil v PDF-jih so bile
  glede na barvo kategorije in semaforja komaj vidne. Svetel spodnji obris
  zdaj zanesljivo loči preverjevalni okvir od barvne ograde in od ozadja
  strani.

- Kdor v urejevalniku Popravi zakrije vrstico dokumenta, postavljenega s
  tesnim razmikom vrstic (značilno za ponudbe in popise del), je dobil
  progo, ki je segala v zgornje poteze vrstice pod njo – ta je bila nato
  le še napol berljiva. Proga se zdaj konča pri resnično narisani pisavi
  sosednje vrstice; zakrita vrstica sama pri tem ostane skupaj s svojimi
  spodnjimi potezami v celoti pokrita.

- Vadbeni dokument („Pomoč → Odpri vadbeni dokument", tudi v rundgangu)
  zdaj predstavi vsako vrsto prepoznavanja: k izmišljenemu pismu se
  dodajo fotografija s prepoznavnim obrazom, napisan podpis, poklic in
  oddelek, diagnoza in zdravilo – poleg imena podjetja, zneska in
  datuma, ki so bili tam že prej. Kaj privzeta nastavitev namerno pusti,
  list razloži sam, skupaj s stikalom, ki to odstrani; obraz na fotografiji
  je tovarniško pikseliziran.

- Denarni zneski v običajnem nemškem zapisu s simbolom za številko
  („1.240,00 €") jih stikalo „Odstrani tudi denarne zneske" ni nikoli
  našel – „1.240,00 EUR" in „€ 1.240,00" pa vedno. Zdaj se prepoznajo vsi
  trije zapisi.

- Iskanje podpisov zdaj deluje tudi na samostojnih slikovnih datotekah:
  kdor očisti sken kot JPG ali PNG, dobi v njem zakrite ročno napisane
  podpise – isto prepoznavanje, isto sporočilo v poročilu kot pri PDF-ju.
  Slike, vdelane v pisarniške datoteke, se še naprej ne preiskujejo, ker
  tam prepoznavanje izmerjeno deluje nezanesljivo; kljukica se zato zdaj
  imenuje „PDF in slikovne datoteke: zakrij ročno napisane podpise".

- Zakrivna proga je pri tesnem razmiku vrstic lahko vidno segala v
  zgornje poteze vrstice pod njo in jo naredila napol neberljivo – višina
  proge je izhajala iz metrik pisave, ne iz tega, kar resnično stoji na
  papirju. Proga se zdaj konča pri dejansko narisanem črnilu sosednje
  vrstice, v urejevalniku Popravi kot pri samodejnem čiščenju. Lastna
  vrstica skupaj s spodnjimi potezami pri tem vedno ostane v celoti
  pokrita; če se vrstici resnično prekrivata, proga raje ostane na
  sosednji vrstici, kot da bi kaj sprostila.

- V imeniku zaposlenih z vlogo pod imenom je bilo žensko vodstveno
  poimenovanje („Anna Berger" z „Vodja montaže" pod njim) potegnjeno v
  zamenjavo imena – moška oblika zraven je pravilno ostala. Ženske oblike
  na „…vodja" (vodja montaže, ekipe, projekta, gradnje, oddelka,
  obrata, skupine, urada) se zdaj obravnavajo enako kot njihovi moški
  ustrezniki kot poimenovanje funkcije; vodja podružnice, kadrov in
  prodaje sta na novo zajeta v obeh oblikah.

- Vklopljivo prepoznavanje poklicev ni našlo ženskih vodstvenih vlog, kot
  so „vodja projekta", „vodja ekipe" ali „vodja oddelka" v ženski obliki,
  njihovih moških oblik pa že. Obe obliki zdaj štejeta enako.

- V oknu predogleda je na Macu večkratna navedba lepela neposredno na
  izraz („Anna Vzorčnaženska2ק namesto „Anna Vzorčnaženska 2ק). Presledek
  spet stoji.

- Primerjalna lupa ima nov gumb ob drsniku približevanja: z enim
  pritiskom jo postavi v polni širini čez rezultat – vsaka po polovico
  višine, izvirnik pa v istem merilu kot dokument (povečava lupe pri tem
  skoči na 100 %). Drugi pritisk jo znova zasidra majhno v levem stolpcu
  in obnovi prejšnjo povečavo lupe. Krožec zraven zdaj ponastavi le
  povečavo – njegovo besedilo namiga je doslej napačno trdilo, da tudi
  znova zasidra okno.

- V orodni vrstici urejevalnika Popravi je spet razvidno, katero orodje
  je izbrano: gumb aktivnega orodja nosi zapolnjeno površino z modrim
  robom – enako vsak drug vklopljen preklopni gumb vrstice (na primer
  primerjalna lupa ali način učenja). Oznaka je bila izgubljena z lastno
  zasnovo gumbov z dne 29. avgusta.

- Številke postavk popisa del („2.3.3.3, 2.3.3.4, 2.3.3.5" druga pod
  drugo) so veljale za naslove IP in bile odstranjene iz rezultata;
  tridelne številke z letnici podobnim zadnjim členom („2.3.19, 2.3.20")
  so padle kot koledarski datumi. Naraščajoče zaporedje številk na
  začetku vrstice zdaj velja za to, kar je – seznam postavk; pravi naslovi
  (omrežne tabele s tehničnim besednim okoljem, številke nad 99) in pravi
  datumi ostajajo prepoznani.

- Priimki, kot so „Müller", „Fischer", „Bauer", „Koch", „Wagner",
  „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster",
  „Schäfer" ali „Meister", so v seznamih oblike „priimek, ime" (npr.
  „Udeleženci: Müller, Peter; Nowak, Anna") ostajali v golem besedilu, ker
  so hkrati uveljavljena poimenovanja poklicev. Zdaj se zanesljivo
  prepoznajo.

- Pri zakrivanju PDF-ja je proga v ozkih celicah tabele lahko potegnila s
  seboj celo celico: iz najdbe „D-LINK" v popisu del je bil odstranjen
  celoten opis izdelka zraven, čeprav je predogled navedel le samo
  najdbo. Proga še naprej pokrije cele vrstice bloka naslova in oznake
  polj, a pogoltne kvečjemu toliko nezadetega, kolikor pokrije
  zaščitenega – opis ob najdbi zdaj ostane.

- Po „Ponastavi pogled" v urejevalniku Popravi je predal strani ostal
  prazen – sličice strani so bile spet vidne šele po zaprtju in ponovnem
  odprtju okna. Zdaj stojijo tudi neposredno po ponastavitvi, sredinsko
  kot prej.

- Urejevalnik Popravi ima četrto orodje: **Odstrani** vzame besedilo pod
  okvirjem brez nadomestila – brez proge (zakrivanje) in brez ograde
  (zamenjava); vrzel ostane vidno prazna. Deluje natančno na besedo; če
  pod njim leži slika, se njeno ozadje pobeli, „Obnovi izvirnik" pa
  razveljavi tudi odstranitev brez nadomestila. Lasten simbol v vrstici in
  oznaka križca, lastna pomnilna tipka v vseh 18 jezikih (slovensko O kot
  Odstrani).

- V iskalni vrstici PDF zdaj „Mapa …" stoji desno ob iskalnih možnostih.
  Odkar poleg zakrivanja obstaja tudi zamenjava najdb, se pet gumbov pri
  običajni širini okna ni več prilegalo drug ob drugem – prvi je bil
  stisnjen in njegovo besedilo odrezano.

- „Ponastavi vse nastavitve" zdaj ponastavi tudi kljukico „Zamenjaj
  rdečo/zeleno z drugima barvama" in jo, če odstopa od dostavljenega
  stanja, označi kot vsako drugo z „spremenjeno".

- Nadomestna besedila v PDF-jih zdaj delujejo enotneje: kjer bi bila
  polna ograda znatno manjša od svoje vrstice (na primer „[BEG16]"
  stisnjeno v kratko besedo, kot je „To"), zdaj stoji krajša oblika v
  velikosti vrstice („[B16]") – dobro berljivo namesto drobcene, številka
  za obnavljanje pa nosi oba zapisa. Ograda postane drobcena le, kadar
  niti najkrajša oblika ne najde prostora – to ostaja boljše od proge
  brez vsake informacije.

- Večbarven nadomestni besedilni zapis (preliv ali mavrica) v PDF-ju je
  ostal celovit le do naslednjega posega: vsaka nadaljnja zamenjava ali
  zakritje na isti strani je lahko že postavljene ograde stisnilo v
  neberljiv, stisnjen kup črk – kdor je v urejevalniku zamenjaval besedo
  za besedo, je namesto „[BEG17]" videl le drugo na drugo natisnjene
  znake. Enkrat postavljene ograde zdaj ostanejo take, kot so bile
  postavljene.

- Stikalo za trajne izjeme v predogledu se zdaj imenuje „Nikoli ne
  odstrani" – kot seznam, v katerega vpisuje; doslej je tam pisalo
  „nikoli več". Vrstica najdbe zraven je pospravljena: informacijski
  simbol „ⓘ" je večji in ga je lažje zadeti, potrditveno polje, oznaka
  zamenjave in gumb pa imajo skupno višino. Stavek okoli najdbe zdaj
  resnično izkoristi napovedano širino – dosedanja navedba širine je bila
  tiho zavržena, izsek pa se je prelomil ožje kot ozek trak.

- V urejevalniku kazalec miške zdaj pove, katero orodje deluje: križec za
  ciljanje, zraven majhen znak – proga za zakrivanje, menjalne puščice za
  zamenjavo, lok razveljavitve za obnavljanje, slikovna mreža za
  pikselizacijo. Dosedanji simboli roke so odpadli; roka drugod povsod
  pomeni „prijemi in premakni". Zdaj ima primerno nalogo: nad rdeče
  poudarjeno besedo ali progo postane kazalec kažoča roka – tam zadošča
  klik.

- „Največje prepoznavanje (UI)" ne ponuja več prenosljivega, krajevnega
  jezikovnega modela – stopnja zdaj računa izključno prek lastnega UI,
  nastavljenega pod „Poveži lastno UI". Kdor je že priklopil lasten
  strežnik, ne opazi razlike.

- Vodena tura predogleda zdaj razlaga tudi informacijski simbol „ⓘ", ki
  kaže stavek okoli najdbe. In ta stavek sam je bolje berljiv: eno stopnjo
  večja pisava, več razmika med vrsticami, trdna širina namesto ozkega,
  gosto stisnjenega preloma.
- Tudi „Preveri datoteko", „Pravila prepoznavanja in lastni izrazi",
  „Očisti besedilo" in „Očisti sliko" imajo zdaj lasten rundgang – prek
  novega gumba „Rundgang skozi okno", ker ta štiri okna nimajo lastne
  menijske vrstice.
- Imena pod devetimi ukrajinskimi oznakami pogodbenih vlog so pri
  homografnem priimku ostala nepopolno prepoznana, kadar je oznaka stala
  sama na svoji vrstici: „Покупець"/„Продавець" (kupec/prodajalec),
  „Поручитель"/„Боржник" (porok/glavni dolžnik), „Свідок" (priča),
  „Орендодавець"/„Орендар" (najemodajalec/najemnik) in
  „Спадкодавець"/„Спадкоємець" (zapustnik/dedič). Imena se zdaj v celoti
  prepoznajo.

- Komentar poimenovanega obsega v delovnem zvezku Excel (upravitelj imen,
  polje „Komentar") je nespremenjeno nosil vanj vpisano ime. Zdaj se
  čisti enako kot preostala vsebina zvezka.

- Imena pod sedmimi madžarskimi oznakami pogodbenih vlog so pri
  homografnem priimku ostala povsem neopažena: „Bérbeadó"/„Bérlő"
  (najemodajalec/najemnik), „Vevő"/„Eladó" (kupec/prodajalec),
  „Kezes"/„Főadós" (porok/glavni dolžnik) in „Tanú" (priča). Imena se zdaj
  v celoti prepoznajo.

- Imena pod češko oznako kupca „Kupující" so pri homografnem priimku
  ostala povsem neopažena. Ime se zdaj v celoti prepozna.

- Imena pod rusko oznako skrbnika „Опекун" so pri homografnem priimku
  ostala povsem neopažena. Ime se zdaj v celoti prepozna.

- Imena pod šestimi nadaljnjimi hrvaškimi oznakami so ostala neopažena:
  „Jamac" (porok), „Glavni dužnik"/„Dužnik" (glavni dolžnik/dolžnik),
  „Ostavitelj" (zapustnik), „Nasljednik" (dedič) in „Vjerovnik" (upnik).
  Imena se zdaj v celoti prepoznajo.

- Shranjena stran HTML z vdelano podstranjo v atributu `src` elementa
  `<embed>` (namesto `data` pri `<object>`) je nespremenjeno nosila
  osebne navedbe v njej. Zdaj se čisti enako kot pri `<object>`.

- Imena pod petimi danskimi oznakami pogodbenih vlog so pri homografnem
  priimku ostala nepopolno prepoznana, kadar je oznaka stala z dvopičjem
  pred imenom: „Arvelader"/„Arving" (zapustnik/dedič),
  „Befuldmægtiget"/„Fuldmagtsgiver" (pooblaščenec/pooblastitelj) in
  „Værge" (skrbnik). Imena se zdaj v celoti prepoznajo; ustrezne
  norveške oznake so za zavarovanje prav tako dopolnjene.

- Ograde v datotekah Word in PowerPoint zdaj nosijo isto barvo kot v
  izbranem videzu (enobarvno, preliv, mavrica ali po kategoriji) – doslej
  so tam ostajale v navadni barvi besedila, tudi kadar so bili rezultati
  PDF že zdavnaj barvni.

- „Kopiraj kot besedilo" in „Kopiraj kot Markdown" postavita golo
  besedilo rezultata neposredno v odložišče – za lepljenje v klepet,
  pošto ali drug program, ne da bi bilo treba datoteko najprej odpreti.

- Imena pod petimi nadaljnjimi slovenskimi oznakami so ostala neopažena:
  „Toženec", „Tožnik", „Zastavitelj", „Zastavni upnik" in „Darovalec".
  Imena se zdaj v celoti prepoznajo.

- Ime avtorja sledene spremembe celice tabele (vstavljena, izbrisana ali
  združena celica v Wordu) je ostalo v datoteki, tudi kadar je bilo isto
  ime kot avtor komentarja že zdavnaj odstranjeno. Zdaj se odstrani prav
  tako.

- Imena pod devetimi nadaljnjimi slovenskimi oznakami so ostala
  neopažena: „Najemodajalec"/„Najemnik", „Zapustnik"/„Dedič",
  „Upnik"/„Dolžnik", „Glavni dolžnik" in „Skrbnik". Imena se zdaj v
  celoti prepoznajo.

- Imena pod petimi slovenskimi oznakami so ostala neopažena: „Izvedenec",
  „Kupec", „Prodajalec", „Naročnik" in „Izvajalec". Imena se zdaj v
  celoti prepoznajo.

- Imena pod petimi nadaljnjimi litovskimi oznakami so ostala neopažena:
  „Užsakovas" (naročnik), „Vykdytojas" (izvajalec), „Vežėjas"
  (prevoznik), „Siuntėjas" (pošiljatelj) in „Arbitras" (razsodnik).
  Imena se zdaj v celoti prepoznajo.

- Imena pod šestimi nadaljnjimi litovskimi oznakami so ostala neopažena:
  „Įgaliotinis" (pooblaščenec), „Įgaliotojas" (pooblastitelj), „Naudos
  gavėjas" (upravičenec, zavarovanje), „Trečiasis asmuo" (tretja oseba v
  civilnem postopku), „Ankstesnis nuomininkas" (prejšnji najemnik) in
  „Naujasis nuomininkas" (novi najemnik). Imena se zdaj v celoti
  prepoznajo.

- Zaznamek v dokumentih ODT (`text:bookmark`) nosi svoje ime prosto
  dodeljeno, pogosto poimenovano po mestu, na katero kaže (npr.
  „Gospod_Mueller_Podpis") – nevidno za bralca, a dobesedno v datoteki.
  Ime se zdaj čisti zraven.

- Imena pod osmimi nadaljnjimi litovskimi oznakami so ostala neopažena:
  „Pareiškėjas" (prosilec), „Suinteresuotas asmuo" (nasprotna stranka v
  nepravdnem postopku), „Ekspertas" (izvedenec), „Bankroto
  administratorius" (stečajni upravitelj), „Valdybos narys" (član sveta),
  „Direktorius" (direktor), „Palikėjas" (zapustnik) in „Įpėdinis"
  (dedič). Imena se zdaj v celoti prepoznajo.

- Imena pod sedmimi nadaljnjimi litovskimi oznakami so ostala neopažena:
  „Liudytojas" (priča), „Vertėjas" (tolmač/prevajalec), „Notaras"
  (notar), „Dovanotojas" (darovalec), „Apdovanotasis" (obdarjenec),
  „Pirkėjas" (kupec) in „Pardavėjas" (prodajalec). Imena se zdaj v celoti
  prepoznajo.

- Imena pod šestimi nadaljnjimi litovskimi oznakami so ostala neopažena:
  „Globėjas" (skrbnik), „Palikimo administratorius" (upravitelj
  zapuščine), „Laiduotojas" (porok), „Pagrindinis skolininkas" (glavni
  dolžnik), „Nuomotojas" (najemodajalec) in „Nuomininkas" (najemnik).
  Imena se zdaj v celoti prepoznajo.

- Ime pod litovsko oznako „Ieškovas"/„Atsakovas" (tožnik/toženec kot
  pravdna stranka) je ostalo neopaženo, ne glede na to, ali je bil priimek
  hkrati navadna beseda (npr. „Vilkas" = volk) ali ne. Ime se zdaj v
  celoti prepozna.

- Vnos osebnega imenika v dokumentih ODT (zaznamek za stvarno kazalo) je
  ime nosil še drugič v svojem lastnem razvrstitvenem ključu – nevidno v
  tekočem besedilu, a dobesedno v pozneje ustvarjenem kazalu. Ključ se
  zdaj čisti zraven.

- Ime prosojnice in ime odseka predstavitve PowerPoint (vidna v območju
  izbire oziroma v razvrščanju prosojnic) sta ostala neočiščena, ker sta
  oba atribut na elementu, ki ni besedilo prosojnice. Oba se zdaj
  prepoznata.

- Litovsko dvojno ime z vezajem, kot je „Petraitis-Kazlauskas", je
  izgubilo svojo drugo polovico, takoj ko je pred njim stalo poljubno
  tekoče besedilo (le na začetku besedila je ostalo celo): priimek se
  zdaj tudi tedaj v celoti prepozna.

- Ime pod oznako „Cesionar" (hrvaško, cesionar pri odstopu terjatve) je
  ustvarilo lažni alarm, ker je bila sama oznaka polja napačno prebrana
  kot oseba. Ime pod rusko oznako „Цессионарий" (prav tako cesionar) je
  nasprotno ostalo povsem neopaženo. Oba primera sta zdaj odpravljena.

- Ime pod oznako „Zedent"/„Zessionar" (nemško, odstop terjatve) je
  ostalo brez nadomestila neopaženo, kadar je bil priimek hkrati navadna
  beseda (npr. „Bauer"). Ime se zdaj v celoti prepozna.

- Ime pod oznako „Darczyńca"/„Obdarowany" (poljsko, darovalec/obdarjenec
  v darilni pogodbi) je ostalo neopaženo, kadar je bil priimek hkrati
  navadna beseda (npr. „Wilk" = volk). Prav tako je romunska oznaka
  „Donatar" (obdarjenec) pri navadnem priimku obtičala celo kot domneven
  del imena. Oba primera sta zdaj odpravljena.

- Ime pod oznako „Wierzyciel"/„Dłużnik" (poljsko, izvršilni
  upnik/izvršilni dolžnik oziroma splošni upnik/dolžnik) je ostalo
  neopaženo, kadar je bil priimek hkrati navadna beseda (npr. „Wilk" =
  volk). Ime se zdaj v celoti prepozna.

- Ime pod oznako „Poręczyciel"/„Dłużnik główny" (poljsko, porok/glavni
  dolžnik v poroštvenih pogodbah) je ostalo neopaženo, kadar je bil
  priimek hkrati navadna beseda (npr. „Wilk" = volk). Ime se zdaj v
  celoti prepozna.

- Ime pod oznako „Ubezpieczony"/„Ubezpieczający" (poljsko, zavarovanec/
  zavarovalec v zavarovalnih policah) je ostalo delno ali povsem
  neopaženo, kadar je bil priimek hkrati navadna beseda (npr. „Wilk" =
  volk). Enako ime pod „Osiguranik"/„Osiguravatelj" (hrvaško, iste
  vloge), kjer je izginilo skupaj z osebnim imenom (npr. „Golub" =
  golob). Obe imeni se zdaj v celoti prepoznata.

- Ime pod oznako „Pełnomocnik"/„Mocodawca" (poljsko, pooblaščenec/
  pooblastitelj v pooblastilnih listinah) je ostalo neopaženo, kadar je
  bil priimek hkrati navadna beseda (npr. „Wilk" = volk). Enako ime pod
  „Opunomoćenik"/„Opunomoćitelj" (hrvaško, iste vloge), kjer je celo
  izginilo skupaj z osebnim imenom. Obe imeni se zdaj v celoti
  prepoznata.

- Ime pod oznako „Pozwany" (poljsko, toženec kot pravdna stranka) je
  ostalo neopaženo, kadar je bil priimek hkrati navadna beseda (npr.
  „Wilk" = volk). Ime se zdaj v celoti prepozna.

- Ime pod oznako „Najmoprimac"/„Najmodavac" (hrvaško, najemnik/
  najemodajalec v najemnih pogodbah) je ostalo neopaženo, kadar je bil
  priimek hkrati navadna beseda (npr. „Kovač" = kovač). Ime se zdaj v
  celoti prepozna.

- Ime pod oznako „Pracodawca"/„Pracownik" (poljsko, delodajalec/
  delavec kot pogodbena stranka v pogodbah o zaposlitvi) je ostalo delno
  neopaženo, kadar je bil priimek hkrati navadna beseda (npr. „Krawiec" =
  krojač). Ime se zdaj v celoti prepozna.

- Madžarska je v katalogu držav imela le osebne identifikacije in ID DDV:
  registrska številka podjetja (Cégjegyzékszám) se zdaj prepozna, če
  neposredno pred njo stoji beseda „Cégjegyzékszám" ali kratica „Cg." –
  sama številka ne nosi kontrolne številke.

- Estonija je v katalogu držav imela le Isikukood: Käibemaksukohustuslase
  number (ID DDV na vsakem estonskem računu) se zdaj prepozna s kontrolno
  številko.

- Latvija je v katalogu držav imela le osebno kodo: PVN reģistrācijas
  numurs pravnih oseb (identifikacija podjetja na vsakem latvijskem
  računu) se zdaj prepozna s kontrolno številko.

- E-pošta s šifrirano vsebino (ovojnica S/MIME ali PGP/MIME,
  `multipart/encrypted`) je bila brez vsakega opozorila izdana kot
  navidezno v celoti preverjena, čeprav je njena resnična vsebina
  ostala šifrirana in s tem nepreverjena. Take pošte zdaj opozorijo nase
  kot nepreverjena priloga.

- Malta je manjkala v katalogu držav: malteški ID DDV (VAT number) se
  zdaj prepozna.

- Luksemburg je manjkal v katalogu držav: luksemburški ID DDV (n° TVA)
  se zdaj prepozna.

- Na začetku stavka postavljeno bolgarsko „Изчакайте" ("Počakajte!") je
  bilo javljeno kot navedba kraja – ista meja modela kot prej pri
  madžarskih, poljskih, čeških in drugih velelnih oblikah brez lastnega
  jezikovnega modela. Ta lažni alarm zdaj odpade.

- Ime pod oznako „Zleceniodawca", „Zleceniobiorca" (poljsko), „Prestator"
  (romunsko), „Naručitelj" ali „Izvođač" (hrvaško) je ostalo delno ali
  povsem neopaženo, kadar je bil priimek hkrati navadna beseda (npr.
  „Wilk", „Vuk" = volk, „Vulpe" = lisica, „Sokol" = sokol). Ime se zdaj v
  celoti prepozna.

- Ime pod oznako „Nadawca" (poljsko), „Afsender" (dansko) ali
  „Pošiljatelj" (slovensko) je ostalo delno ali povsem neopaženo, kadar
  je bil priimek hkrati navadna beseda (npr. „Sowa" = sova, „Bager" =
  pek, „Volk" = volk). Ime se zdaj v celoti prepozna.

- Ime pod oznako „Gavėjas" (litovsko) ali „Prejemnik" (slovensko) je
  ostalo delno ali povsem neopaženo, kadar je bil priimek hkrati navadna
  beseda (npr. „Vilkas" = volk). Kot že pri „Primatelj" (hrvaško) in
  „Modtager" (dansko) se ime zdaj v celoti prepozna.

- Glava okrožnice, kot je „To All Staff" ali „To All Employees", je bila
  napačno prepoznana in odstranjena kot osebno ime. To se zdaj ne
  zgodi več.

- Ime pod oznako „Primatelj" (hrvaško) ali „Modtager" (dansko) je ostalo
  delno neopaženo, kadar je bil priimek hkrati navadna beseda (npr.
  „Golub" = golob, „Bager" = pek). Kot že pri „Odbiorca" (poljsko) in
  „Destinatar" (romunsko) se ime zdaj v celoti prepozna.

- Polno ime v podpisni vrstici danskega, norveškega ali grškega dokumenta
  je ostalo delno neopaženo, kadar je oznaka „Underskrift" ali
  „Υπογραφή" stala sama nad imenom – v grškem primeru je bil priimek celo
  prepoznan kot navedba kraja namesto kot ime. Kot že pri „Подпись"
  (rusko) se ime zdaj v celoti prepozna.

- Besedilo na postrani odloženi telefonski fotografiji (običajen pokončni
  posnetek, ki je pokonci prikazan le prek oznake zasuka slike) je lahko
  spregledalo optično prepoznavanje besedila, ker je doslej brala surove,
  leže obrnjene slikovne točke. Take fotografije se pred branjem zdaj
  zasukajo v pravilno smer – kot že prej pri prepoznavanju obrazov.

- Polno ime v podpisni vrstici ruskega, ukrajinskega ali litovskega
  dokumenta je ostalo delno neopaženo, kadar je oznaka „Подпись",
  „Підпис" ali „Parašas" stala sama nad imenom – osebno ime ali očetovo
  ime je odpadlo. Kot že pri „Potpis" (hrvaško) se ime zdaj v celoti
  prepozna.

- Obraz na postrani odloženi telefonski fotografiji (običajen pokončni
  posnetek, ki je pokonci prikazan le prek oznake zasuka slike) je lahko
  spregledalo prepoznavanje obrazov, ker je doslej preverjalo surove, leže
  obrnjene slikovne točke. Take fotografije se pred iskanjem zdaj
  zasukajo v pravilno smer.

- Polno ime v podpisni vrstici hrvaškega dokumenta je ostalo delno
  neopaženo, kadar je oznaka „Potpis" stala sama nad imenom ali z
  dvopičjem pred njim – osebno ime je odpadlo, ne glede na to, ali je
  stalo v lastni vrstici ali v „Potpis: ime drugo_ime priimek". Kot že
  pri „Unterschrift" in „Signature" se ime zdaj v celoti prepozna.

- Priimek po zakonu za okrajšavama osebnega stanu „por." (poročena/
  poročen) in „vd." (vdova/vdovec) je doslej ostal povsem neopažen, ne
  glede na to, ali je stal v oklepaju, za vejico ali prilepljen brez
  presledka („Anna Meier (por. Weber)", „Klaus Bauer (vd.Fischer)") – kot
  že pri „rojena/rojen" se zdaj zanesljivo prepozna.

- Ime za podpisom prokure „ppa." (na primer v podpisni vrstici poslovne
  e-pošte ali poslovnega dopisa) je pri priimku, enakemu poklicu, kot je
  „Bauer" ali „Koch", doslej ostalo delno ali povsem neopaženo – kot že
  pri „podpisal/-a" se zdaj zanesljivo prepozna.

- Številka poljske osebne izkaznice (dowód osobisty) se je prepoznala
  le brez presledka med serijo in številko („ABS123456"). Prav takega
  zapisa pa dokument ne natisne – uradno tam stoji presledek
  („ABS 123456"), in v tem zapisu je številka doslej ostala neopažena.

- Animiran PNG (APNG, na primer kratek posnetek zaslona, shranjen kot PNG
  namesto GIF) je bil doslej preverjen in očiščen le v svoji prvi sliki,
  ne da bi bilo to sporočeno – kot že prej pri animiranem WebP Maskuro
  zdaj sporoči, da vsaka nadaljnja slika ostane nepreverjena v rezultatu.

- Animirana slika WebP (na primer iz orodja za zajem zaslona ali klepetalne
  aplikacije z več slikami v eni datoteki) je bila doslej preverjena in
  očiščena le v svoji prvi sliki, ne da bi bilo to sporočeno – kot že prej
  pri večstranskem TIFF Maskuro zdaj sporoči, da vsaka nadaljnja slika
  ostane nepreverjena v rezultatu.

- Slovensko dvojno osebno ime z vezajem („Ana-Marija Novak") je izgubilo
  svojo prvo polovico, takoj ko je pred njim v besedilu stal tekoč stavek
  – ista napaka kot prej pri poljščini. „Ana-" je ostala nezaščitena v
  golem besedilu, medtem ko je bil preostanek imena že zamenjan.

- Poljsko dvojno osebno ime z vezajem („Anna-Maria Kowalska") je
  izgubilo svojo prvo polovico, takoj ko je pred njim v besedilu stal
  tekoč stavek ali predlog, kot je „z"/„od" – preostanek imena je bil
  zamenjan, „Anna-" pa je ostala nezaščitena v golem besedilu.

- Kazahstanske vljudnostne oblike „Хабарласыңыз"/„Байланысыңыз"
  (kontaktirajte nas) ter srbske glagolske oblike „Помоћи", „Чекамо" in
  „Пишите" brez lastnega jezikovnega modela so bile v telefonskih stavkih
  napačno prepoznane kot osebno ime ali kraj.

- Azerbajdžanska vljudnostna beseda „Xahiş" (prošnja/zahteva) brez
  lastnega jezikovnega modela je bila v telefonskih stavkih napačno
  prepoznana kot osebno ime.

- Indonezijske in malajske vljudnostne/velelne besede brez lastnega
  jezikovnega modela, kot so „Silakan", „Mohon" (indonezijsko), „Sila" in
  „Tolong" (malajsko), so bile v telefonskih stavkih napačno prepoznane
  kot osebno ime ali kraj.

- Uzbekistanska velelna oblika „Kutamiz" (čakamo) brez lastnega
  jezikovnega modela je bila v telefonskih stavkih napačno prepoznana kot
  kraj.

- Turške velelne oblike brez lastnega jezikovnega modela, kot sta
  „Arayınız" (pokličite) in „Bekliyoruz" (čakamo), so bile v telefonskih
  stavkih napačno prepoznane kot osebno ime.

- Velelne oblike v nadaljnjih jezikih brez lastnega jezikovnega modela
  (češčina, slovaščina, grščina), kot so „Zavolejte" (pokliči), „Prosíme"
  (prosimo) in „Περιμένουμε" (čakamo), so bile v telefonskih stavkih
  napačno prepoznane kot osebno ime ali kraj.

- Madžarske in poljske velelne oblike, kot so „Hívjon" (pokliči),
  „Kérjük" (prosimo), „Várjuk" (pričakujemo), „Zadzwoń" (pokliči) in
  „Czekamy" (čakamo), so bile v telefonskih stavkih napačno prepoznane
  kot osebno ime ali kraj.

- V oštevilčenem seznamu imen brez oblike tabele (npr. „1. Robert Brown",
  pod tem „2. Mary Johnson") je bilo ime z določenimi angleškimi priimki
  (med drugim „Brown", „White", „Green", „Black", „Young") povsem
  spregledano – jezikovni model je številko naslednje vrstice pripel k
  imenu, zaradi česar najdba ni nikoli več natančno ustrezala.

- Pri poljskem jezikovnem modelu je pred priimkom stoječa začetnica
  osebnega imena (npr. „J. Kowalski", „A. Nowak") ostala neprepoznana in
  neočiščena v besedilu – zamenjan je bil le priimek. Drugi preverjeni
  jeziki (med drugim nemščina, angleščina, romunščina, hrvaščina,
  madžarščina, ruščina) so isto začetnico zajeli že prej.

- Osebno ime za malo začetnico zapisanim nazivom, kot je „dr.", „ing."
  ali „dipl. ing.", v madžarščini, romunščini in hrvaščini sploh ni bilo
  prepoznano – izgubljen ni bil le naziv, temveč celo ime (npr. „dr.
  Kovács Béla", „ing. Andrei Popescu", „dipl. ing. Marko Horvat").
- V slovenskih sejnih zapisnikih je bilo golo poimenovanje vloge pred
  dvopičjem (npr. „Tajnik:", „Podpredsednik:", „Poročevalec:",
  „Predsedujoči:") napačno prepoznano kot osebno ime, takoj ko je drugje
  v zapisniku že stalo pravo ime govorca.
- V ruskih sejnih zapisnikih je bilo golo poimenovanje vloge pred
  dvopičjem (npr. „Секретарь:", „Докладчик:", „Докладчица:") napačno
  prepoznano kot osebno ime, takoj ko je drugje v zapisniku že stalo
  pravo ime govorca.
- V romunskih sejnih zapisnikih je bilo golo poimenovanje vloge z
  določnim členom pred dvopičjem (npr. „Secretarul:", „Președintele:",
  „Vicepreședintele:", „Moderatorul:", „Consilierul:") napačno
  prepoznano kot osebno ime – „Președintele" že samo zase, ostala
  dodatno, takoj ko je drugje v zapisniku že stalo pravo ime govorca.
- V hrvaških sejnih zapisnikih je bilo golo poimenovanje vloge pred
  dvopičjem (npr. „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:",
  „Predsjedavajući:") napačno prepoznano kot osebno ime.
- Poljski naslov poštnega predala „Skrytka pocztowa" za oznako
  pošiljatelja ali prejemnika (npr. „Odbiorca: Skrytka pocztowa 45") je
  bil napačno prepoznan kot osebno ime.
- Hrvaški naslov poštnega predala „Poštanski pretinac" za oznako naslova
  „Adresa:" (npr. „Adresa: Poštanski pretinac 45", tudi s pripeto „br."
  za številko) je bil napačno prepoznan kot osebno ime.
- Kraj brez dodatne oznake v norveškem tekočem besedilu (npr. „Anna
  Hansen bor i Oslo") ni bil prepoznan – lastni jezikovni model tam
  kraje večinoma poimenuje z lastno, doslej nedodeljeno oznako namesto
  običajnega „LOC".
- Datum v vrstnem redu ISO leto-mesec-dan z vezajem ali piko (npr.
  „2024-12-31") v nekaterih jezikih sploh ni bil prepoznan kot datum –
  najbolj opazno v litovščini, kjer uradna pisma datume večinoma navajajo
  v tem vrstnem redu.
- Madžarski ID DDV (közösségi adószám) v uradno enako veljavni,
  neločevani 11-mestni obliki (npr. „12345678123" namesto
  „12345678-1-23") ni bil prepoznan.
- Poljska davčna številka NIP z ločili v razporeditvi 3-2-2-3 (npr.
  „856-73-46-215", kot je običajna na računih podjetij in samostojnih
  podjetnikov) ni bila prepoznana – zadela je le razporeditev 3-3-2-2 za
  fizične osebe.
- Ime podjetja pod slovaško oznako polja „Zamestnávateľ:" ali „Názov
  zamestnávateľa:" (delodajalec/podjetje) ni bilo prepoznano.
- Ime podjetja pod romunsko oznako polja „Angajator:" ali „Denumire
  angajator:" (delodajalec/podjetje) ni bilo prepoznano.
- Ime podjetja pod madžarsko oznako polja „Cég:" ali „Munkáltató:"
  (podjetje/delodajalec) ni bilo prepoznano.
- Ime podjetja pod poljsko oznako polja „Pracodawca:" ali „Nazwa firmy:"
  (delodajalec/podjetje) ni bilo prepoznano.
- Ime podjetja pod slovensko oznako polja „Podjetje:" ali „Delodajalec:"
  (podjetje/delodajalec) ni bilo prepoznano.
- Ime podjetja pod hrvaško oznako polja „Tvrtka:" ali „Poslodavac:"
  (podjetje/delodajalec) ni bilo prepoznano.
- Izpisan denarni znesek z malo začetnico pri valuti (npr. „500 euro")
  ni bil prepoznan, zadela je le velika začetnica („Euro").
- Priimek za „svak"/„svakinja" (npr. „Svak Bauer prejme dediščino.") ni
  bil prepoznan.
- Pri turškem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „34000 İstanbul İstiklal Caddesi No: 45") je
  hišna številka ostala neočiščena.
- Pri slovaškem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „831 01 Bratislava Hlavná 15") je hišna
  številka ostala neočiščena.
- Država rojstva brez dodatne oznake v hrvaškem polju obrazca (npr.
  „Zemlja rođenja: Njemačka") ni bila prepoznana.
- Država rojstva brez dodatne oznake v litovskem polju obrazca (npr.
  „Gimimo valstybė: Vokietija") ni bila prepoznana.
- Država rojstva ali stalnega bivališča brez dodatne oznake v poljskem
  polju obrazca (npr. „Kraj: Niemcy") ni bila prepoznana.
- Državljanstvo ali kraj stalnega bivališča brez dodatne oznake v
  slovenskem polju obrazca (npr. „Državljanstvo: Nemčija") ni bilo
  prepoznano.
- Država stalnega bivališča brez dodatne oznake v norveškem polju
  obrazca (npr. „Bosted: Tyskland") ni bila prepoznana.
- Nova stran nastavitev „Obvestila" (prej odsek v „Program"): tri
  sporočila opravilne vrstice (predogled pripravljen, obdelava
  dokončana, posodobitev prenesena) zdaj stojijo na lastnem mestu.
- Novo: rezultat je mogoče poleg tega odložiti tudi kot golo besedilno
  datoteko (.txt) ali s pripono .md – za nadaljnjo obdelavo v UI ali
  drugem programu.
- Pri hrvaški kontaktni navedbi z oznako „Osoba za kontakt"/„Kontakt
  osoba" (npr. „Osoba za kontakt: Golub Marko") je ime ostalo povsem
  neprepoznano, kadar je bil priimek hkrati navaden samostalnik (Golub =
  „golob").

- Pri romunski kontaktni navedbi z oznako „Persoana de contact"/„Persoană
  de contact" (npr. „Persoana de contact: Lup Ion") je ime ostalo povsem
  neprepoznano, kadar je bil priimek hkrati navaden samostalnik (Lup =
  „volk") in je bilo osebno ime zelo kratko in splošno.

- Pri poljski kontaktni navedbi z oznako „Osoba kontaktowa"/„Osoba do
  kontaktu" (npr. „Osoba kontaktowa: Wilk Adam") je priimek ostal
  neprepoznan, kadar je bil hkrati navaden samostalnik (Wilk = „volk",
  Zielony = „zelen").

- Pri romunskem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „010061 București Strada Victoriei 30") je
  hišna številka ostala neočiščena.
- Pri srbskem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „11000 Beograd Bulevar Kralja Aleksandra
  73") je hišna številka ostala neočiščena.
- Pri grškem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „104 32 Αθήνα Ερμού 15") je hišna številka
  ostala neočiščena.
- Pri slovenskem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „1000 Ljubljana Slovenska cesta 58") je
  poštna številka ostala neočiščena.
- Pri litovskem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „LT-01100 Vilnius Gedimino pr. 9") je
  poštna številka ostala v celoti neočiščena.
- Pri madžarskem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „1052 Budapest Kossuth Lajos utca 12") je
  poštna številka ostala neočiščena.
- Priimek za „dediči" (npr. „Dediči Wagner so obvestilo prejeli
  pravočasno.") je v kontekstu dedovanja/zapuščine skoraj vedno ostal
  nepoznan.
- Priimek za „bratje in sestre" (npr. „Bratje in sestre Bauer stanujejo v
  Linzu.") je doslej skoraj vedno ostal neprepoznan – za razliko od
  „družina"/„zakonca" to ni zadelo le priimkov, enakih poklicu (Koch,
  Bauer, Richter), temveč poljubne priimke na tem mestu.
- Priimek za „zakonca" ali „zakonski par" (npr. „Zakonca Koch se
  selita.") ni bil prepoznan, kadar je bil hkrati navaden samostalnik ali
  poimenovanje poklica (Koch, Bauer, Richter).
- Navadna številka naročila, opravila ali artikla v tipični razporeditvi
  davčne ali socialnozavarovalne številke (npr. „030 4471 2298") je bila
  brez vsake pripadajoče oznake napačno zakrita kot taka.
- Številka dokazila/opravila v obliki „leto/tekoča številka" (npr. v
  „Račun št. 4/2024/778899") je bila s strani prepoznavanja telefonskih
  številk napačno zakrita kot telefonska številka.
- Ime za „Gospod"/„Gospa" z večbesedno akademsko nazivno verigo pred njim
  („Gospod dr. med. Weber", „Gospod prof. dr. Krause") je doslej ostalo
  povsem nezaščiteno – prepoznana je bila doslej le ena posamezna beseda
  naziva med nagovorom in imenom.
- Sodna opravilna številka v klasični obliki s kratico senata/oddelka
  („4 Ca 1523/24", „Št.: 7 O 234/25") je doslej ostala povsem
  nezaščitena – tudi običajna kratka oblika „Št."/„Op. št." poleg
  izpisane oznake ni bila prepoznana.
- Številka kreditne kartice, ki jo je sredi njene četverne razporeditve
  ločil prelom vrstice – na primer v ozkem stolpcu tabele –, je doslej
  ostala povsem nezaščitena.
- Davčna identifikacijska številka, ki jo je sredi njene razporeditve
  ločil prelom vrstice – na primer v ozkem stolpcu tabele ali polju
  obrazca –, je doslej ostala povsem nezaščitena.
- Številka socialnega zavarovanja, ki jo je sredi njene razporeditve
  ločil prelom vrstice – na primer v ozkem stolpcu tabele –, je doslej
  ostala povsem nezaščitena, niti delno zamenjana.
- Hišna številka z razponom, kot je „12a-14b" ali „3-5", je bila
  zamenjana le do polovice – drugi del za vezajem je v rezultatu ostal
  odprt.
- Identifikacijska številka vozila (FIN/VIN), ki jo je sredi njenih 17
  znakov ločil prelom vrstice, presledek ali vezaj – na primer v ozkem
  stolpcu tabele ali polju prometnega dovoljenja –, je doslej ostala
  povsem nezaščitena.
- Nagovor v pismu/pošti, kot je „Draga Anna!" ali „Dragi Hans" – brez
  vejice za imenom, najpogostejša oblika v sproščeni pošti – je pustil
  ime povsem nezaščiteno, tudi v polnem dokumentu s tekočim besedilom in
  pozdravno formulo pod njim.
- Ista vrzel je zadela tudi sproščene nagovore v klepetu/pošti „Zdravo
  Anna!", „Hi Anna!", „Hej Anna!" in „Servus Anna!" brez vejice – ime je
  prav tako ostalo povsem nezaščiteno.
- Gol podpisni blok, ki se začne neposredno z „Lep pozdrav" ali „Iskreno" –
  na primer kopiran iz odložišča, brez predhodnega stavka – je ime pod
  njim pustil povsem nezaščiteno.
- Polje z več osebami, na primer „Sorodniki: Kaczmarek, Piotr (sin),
  Kaczmarek, Anna (žena)", je obe imeni skupaj z navedbo v oklepaju
  zlilo v eno samo, veliko predolgo najdbo – drugo ime je pri tem ostalo
  delno nezaščiteno v rezultatu.
- Ulica brez pripone „-straße"/„-weg" – kot je na podeželju običajno,
  na primer „Am Marktplatz 5" ali „Im Grund 12" – ni bila prepoznana,
  kadar ji je sledila vrstica poštna številka-kraj, na primer v
  prijavnem potrdilu: „Nov naslov: Am Weidengarten 17, 54295 Trier" je
  izgubil ulico v celoti, odstranjena je bila le poštna številka.
- Ime za sestavljeno oznako polja s poševnico (na primer „Ime/Priimek:
  Bauer Klaus") ni bilo deloma prepoznano – dvoumen priimek, kot je
  „Bauer", je brez dokazila polja ostal neopažen. Ista vrzel je zadela
  kombinirana polja, kot je „Poštna št./Kraj: 04109 / Leipzig". Enako je
  veljalo za kombinirana polja z izpisanim veznikom namesto poševnice, na
  primer „Ime in priimek: Bauer Klaus" ali „Priimek oz. ime: …".
- Datum rojstva v obliki „Datum rojstva: …" in datum smrti v obliki
  „Datum smrti: …" ali „Dan smrti: …" nista bila prepoznana – zadela je
  le „Rojstni datum: …" oziroma „Datum smrti: …" v izvirni obliki.
- Datum poroke v obliki „Datum poroke: …" ali „Dan poroke: …" ni bil
  prepoznan – zadela je le „Poročni datum: …", „Datum sklenitve zakonske
  zveze: …", čeprav so datum ločitve, naturalizacije in sklenitve
  partnerske skupnosti isto obliko „datum X" poznali že zdavnaj.
- Datum ločitve v obliki „Datum ločitve: …" ni bil prepoznan – zadela je
  le „Datum razveze: …" in sledeča glagolska oblika, čeprav sta datum
  naturalizacije in sklenitve partnerske skupnosti isto obliko „datum X"
  poznala od začetka.
- Datum sklenitve partnerske skupnosti doslej sploh ni bil prepoznan – ne
  z oznako („Datum sklenitve partnerske skupnosti: …") ne v tekočem
  besedilu („… sta sklenila partnersko skupnost dne …"). Zdaj se zamenja
  kot lastna vrsta navedbe, tako kot datum rojstva, poroke, ločitve in
  naturalizacije.
- Datum naturalizacije doslej sploh ni bil prepoznan – ne z oznako
  („Datum naturalizacije: …") ne v tekočem besedilu („… je bil/a dne …
  naturaliziran/a"). Zdaj se zamenja kot lastna vrsta navedbe, tako kot
  datum rojstva, poroke in ločitve.
- Datum ločitve doslej sploh ni bil prepoznan – ne z oznako („Datum
  ločitve: …") ne v tekočem besedilu („Zakonska zveza je bila razvezana
  dne …"). Zdaj se zamenja kot lastna vrsta navedbe, tako kot datum
  rojstva, smrti in poroke.
- Datum poroke za genealoškim zakonskim znakom „⚭" brez oznake ni bil
  prepoznan, čeprav sta bila datum rojstva in smrti v isti vrstici prek
  zvezdice in križca že prepoznana – zdaj se prepozna tudi datum poroke.
- Datum smrti za osmrtniškim križem brez oznake („*03.06.1940
  †21.11.2023") ni bil prepoznan, čeprav je bil datum rojstva pred njim
  prek genealoške zvezdice že prepoznan – zdaj se prepozna tudi datum
  smrti.
- Priimek pred osebnim imenom na koncu vrstice zadeve/prijave s
  predhodnim stvarnim besedilom in ločilno črto („Zadeva: Reklamacija -
  Bauer, Anna") pri priimku, enakem poklicu, ni bil prepoznan – zdaj se
  prepozna.
- Številke prosilcev in vlagateljev za svojo oznako („Številka prosilca:
  4471829", „Številka vlagatelja: 7654321") so v celoti padle skozi
  prepoznavanje – zdaj se prepoznajo.
- Zamenjava ne zakrije več, kadar za berljivo ogrado ni prostora –
  premajhna ograda se zdaj zapiše krajše, namesto da bi postala prazna
  proga, dokler sploh ostane prostor. Novo poleg tega: ali je najdba na
  sliki (glava dopisa, ozadje skena) označena ali le zakrita, je zdaj
  mogoče nastaviti neodvisno od preostale vrste rezultata. In najdba na
  sliki, ki se v celoti odstrani, je bila označena, kot da slika ostane –
  ograda je stala svetlo na podlagi, ki ni bila nikoli zakrita, in je
  tako izginila nevidno na zdaj beli podlagi.
- Najdba na **ohranjeni** sliki je bila pri zamenjavi vedno zakrita
  črno-belo, ne glede na izbrano oblikovanje (barve kategorij, mavrica
  …) – vidno kot prelom med pisanimi oznakami v tekočem besedilu in
  črnimi progami na glavi dopisa. Slikovno ozadje zdaj sledi isti barvi
  kot ograda zraven.
- Prepoznavanje identifikacijske številke vozila (FIN/VIN) je vsako
  17-mestno alfanumerično kodo brez I/O/Q brezpogojno označilo kot
  identifikacijsko številko vozila – tudi številke naročil, serij in
  licenčnih ključev, ki imajo po naključju isto obliko. Zdaj šteje le z
  besedo sobesedila v bližini („FIN", „VIN", „šasija", „Chassis" ipd.).
- V sistemih vozovnic/koledarjev je prepoznavanje imen za „Assigned to"/
  „Closed by" ipd. potegnilo s seboj naslednjo besedo polja, kadar je v
  isti vrstici sledila brez ločila („Assigned to Max Mustermann Priority
  High" je postalo „Max Mustermann Priority"). V glavah Git-commitov je
  prepoznavanje imen enako potegnilo s seboj **naslednji** ključ
  dodatka, kadar sta bili dve vrstici povezani le z enim presledkom
  namesto s prelomom vrstice („Author: julia bergmann Reviewed-by: …" je
  postalo „julia bergmann Reviewed-by"). Obe zavori sta dopolnjeni.
- Ime za „p.A.", „zH"/„zHd", „i.A."/„i.V." in „rojen(a)" je potegnilo s
  seboj neposredno sledečo besedo oddelka, kadar je stala brez ločila v
  isti vrstici („p.A. Max Mustermann Računovodstvo" je postalo „Max
  Mustermann Računovodstvo", „i.A.Max Mustermann Prodaja" pa „Max
  Mustermann Prodaja"). Ista zavora kot pri „Assigned to"/dodatkih Git
  je zdaj dopolnjena tudi tukaj.
- Označen IBAN neposredno nad vrstico BIC, BLZ ali SWIFT je potegnil s
  seboj njeno oznako v svojo lastno najdbo, ker sta „BIC" in „BLZ"
  sama izgledala kot še en blok številk – iz „IBAN: DE89 … 0130 00" in
  vrstice pod njo je nastala ena sama, predaleč segajoča najdba, oznaka
  naslednje vrstice pa je pri čiščenju izginila zraven. Prizadeta je bila
  skoraj vsaka bančna povezava z IBAN in BIC drug pod drugim.
- Okno z najdbami zdaj pove, **kje** stoji ograda, ki je na strani ne
  najde. Dva primera sta doslej javljala le „ni najdeno", čeprav je
  zamenjava potekla: če ograda stoji v nevidnem stranskem besedilu –
  na primer v naslovnem cilju povezave, v opombi ali polju obrazca –,
  vrstica zdaj to nosi kot lastno informacijo („v stranskem besedilu"),
  klik pa to pojasni. In če je bila ograda zaradi pomanjkanja prostora
  zapisana skrajšano („[N382]" namesto „[NAM382]"), klik na dolgo vrstico
  zdaj skoči na mesto kratke oblike in navede preimenovanje; pripis
  zato izrecno poveže obe vrstici.
- Če ista nadomestna vrednost stoji večkrat v dokumentu, vsak nadaljnji
  klik na vrstico okna v krogu skoči na naslednje mesto najdbe – tudi
  čez meje strani; vrstica stanja šteje zraven („Najdba 2 od 4"), in
  ravno naslovljeno mesto je bolj poudarjeno obrobljeno kot preostala.
  In če ograda stoji le v seznamu najdb, a nikjer v dokumentu (ker je
  mesto stopilo v prekrivajočo se zamenjavo), to zdaj pove vrstica
  stanja, namesto da bi klik ostal brez tihe posledice.
- Skrajšano osebno ime za „na" ali „za" se zdaj zanesljivo prepozna kot
  ime – „Nakazilo na M. Wagner" in „Račun za M. Wagner" sta doslej
  pogosto ostala neočiščena, medtem ko je bilo isto ime z drugo oznako
  pred njim (na primer „Prejemnik plačila:") že najdeno. Prizadete so
  bile predvsem vrstice izpiska računa in knjiženja.
- „Obtoženec"/„Obtožena"/„Osumljenec"/„Osumljena" zdaj veljajo za polje
  imena: če je v kazenskopravnih listinah ime stalo neposredno za eno od
  teh oznak, doslej ni bilo prepoznano za približno polovico preverjenih
  imen – ne osebno ime, ne priimek.
- Mesto, kliknjeno v oknu z najdbami, je zdaj obrobljeno modro namesto
  označeno rumeno – na barvnih površinah semaforja preverjanja rumena
  barva iskalne najdbe ni bila razpoznavna. Poleg tega klik zdaj najde
  tudi večbesedne nadomestne vrednosti (izmišljena imena, maskirane
  številke): doslej je pri takih vrsticah ostal brez učinka, ker se je
  mesto najdbe iskalo le besedo za besedo.
- Posvojiteljski, rejniški in polstarši („posvojiteljski oče", „rejniška
  mati", „očim" in drugo) se zdaj prepoznajo kot polje imena, ime je prej
  padlo skozi neočiščeno.
- Številčno bogate tabele in seznami se ne zavržejo več napačno: če je
  bila kratka številka (na primer del kupčeve številke, prebran kot
  telefonska številka) zamenjana, je sklepno preverjanje isto zaporedje
  znakov javilo kot preostalo navedbo tudi, kadar je po naključju stalo
  drugje v povsem drugi številki – in ni izdalo nobenega rezultata.
  Številka zdaj šteje za ostanek le tam, kjer stoji kot lastna številka.
- Matične listine: „Oče:"/„Mati:" se zdaj prepozna kot polje imena, ime
  starša je prej padlo skozi neočiščeno.
- Nadaljnje družinske vloge („boter", „ded/babica", „zakonski partner",
  „življenjski partner", „stric", „teta") se zdaj prepoznajo kot polje
  imena, ime je prej padlo skozi neočiščeno.
- Nemška bančna koda (BLZ) se zdaj prepozna tudi v uradni razporeditvi
  ("370 400 44", "370.400.44", "370-400-44", "370/400/44"), ne le kot
  osem povezanih številk.
- Nemška številka pokojninskega zavarovanja se zdaj prepozna tudi s piko,
  vezajem ali poševnico med petimi bloki ("65-170839-J-08-8",
  "65.170839.J.08.8"), ne le s presledki.
- Glavno okno se prikaže hitreje: prepoznavalne knjižnice (Presidio
  skupaj s podlago jezikovnih modelov) so se doslej nalagale že ob
  izgradnji okna – pod Windows približno štiri sekunde, preden je bilo
  sploh kaj videti. Zdaj se v celoti naložijo v ozadju; gumb „Očisti" se
  kot doslej sprosti šele, ko je vse pripravljeno.
- Pisarniški dokumenti s številnimi slikami ali videoposnetki se
  zapišejo hitreje: že stisnjeni mediji se v paketu rezultata shranijo
  namesto nekoristno stisnjeni drugič – to doslej ni prihranilo niti
  bajta in je JPEG-e prej povečalo.
- Preglednice in drugi dokumenti iz mnogih majhnih besedilnih enot se
  preverijo hitreje: prepoznavanje jezika zdaj vse celice in odstavke
  dokumenta obdela v enem prehodu namesto posamično – ob dokazano istih
  najdbah (400 celic: od približno 4,7 na 2,5–3,5 sekunde).
- Seznamu podobne strani PDF (imeniki, seznami postavk) so pri vstavljanju
  ograd znatno hitrejše: iskanje prostora za vsako oznako je doslej teklo
  prek vseh besed strani – zdaj le prek okolice vrstice, ob dokazano
  enakem rezultatu (na strani z 300 oznakami približno šestnajstkrat
  hitreje).
- Slikovno bogati dokumenti prihranijo več nepotrebnih delovnih korakov na
  sliko: štetje obrazov in kod na straneh PDF slike strani ne dekodira
  več dvakrat, preverjanje metapodatkov čiste slike sploh ne dešifrira
  več, pikselizirane slike se zapišejo z običajnim namesto najpočasnejšim
  stiskanjem PNG (enaka velikost, tretjina časa), brez nastavljenega
  vodnega žiga pa odpade nekoristno ponovno zapisovanje celega PDF-ja na
  koncu.
- Skenirani PDF-ji z vklopljenim optičnim prepoznavanjem besedila so
  znatno hitrejši: vsaka stran se je doslej izrisala dvakrat v polni
  ločljivosti (enkrat za branje, enkrat za rastriranje) – odslikava se
  zdaj ponovno uporabi. In na Windows/Linuxu optično prepoznavanje bere
  pasove velikega skena v enem prehodu namesto z lastnim zagonom programa
  za vsak pas.
- Veliki dokumenti se čistijo znatno hitreje: usklajevanje že najdenih
  vrednosti je doslej raslo s številom najdb (64-KB besedilni blok je ob
  koncu velike datoteke stal približno sekundo samo za to, zdaj
  šestdesetinko), iskanje pravnih oblik podjetij pa je teklo z vsemi
  približno 280 katalogskimi oblikami čez vsako besedilno mesto (zdaj
  približno dvajsetkrat hitreje, ob dokazano istih najdbah).
- Ime neposredno za „Lep pozdrav"/„Lepe želje" brez predhodnega besedila
  ali ločila sploh ni bilo prepoznano – gol podpisni blok brez tekočega
  besedila pred njim je pustil ime izginiti brez sledu.
- Polje naslova na začetku dokumenta s priimkom, enakim poklicu („Bauer
  Anna", „Koch Stefan" kot prva vrstica nad ulico in krajem), je doslej
  ostalo delno neprepoznano ali bilo uvrščeno kot navedba kraja namesto
  osebe – brez predhodnega stavka je jezikovnemu modelu manjkala stavčna
  zgradba, ki sicer „Bauer" prepozna kot ime in ne kot poklic.
- Ime za podpisno oznako „podpisal/-a" s priimkom, enakim poklicu, pred
  osebnim imenom („podpisal/-a Bauer Anna" na koncu odločbe ali sodbe),
  je doslej ostalo nepopolno prepoznano – najdeno je bilo le osebno ime,
  priimek je izginil brez sledu.
- Ime neposredno za kupčevo številko, pogodbeno številko ali podobno
  identifikacijsko številko brez lastne vrstice („Pogodbena številka
  55219 Bauer Anna", „Kupčeva št. 4711 Bauer Anna") je bilo pri priimku,
  enakem poklicu, doslej nepopolno ali sploh ne prepoznano.
- Ikona v menijski vrstici macOS je zdaj predloga, ki se – kot sosednje
  ikone – prilagodi svetlemu in temnemu načinu, pri čemer z obema
  izsekanima progama ostane prepoznavna kot Maskuro. Če teče stražar
  odložišča, to kaže ločena pika na konici ščita.
- Klik v oknu z najdbami zdaj vodi do mesta najdbe tudi v anonimizirajočem
  načinu: menjava strani, zvitje v sliko, rumena oznaka. Doslej je klik
  tam ostal brez posledic, ker je ograde še imel za neoštevilčene – odkar
  vsaka najdba nosi svojo številko, je mesto enolično. Le pri resnično
  neoštevilčeni ogradi vrstica stanja še naprej pojasni, zakaj cilja
  skoka ni mogoče določiti.
- Prvo shranjevanje v urejevalniku Popravi (Ctrl+S ali gumb diskete) zdaj
  vpraša po mestu, kot „Shrani kot …" – vnaprej izpolnjeno z mapo
  izvirnika in imenom rezultata. Doslej je datoteka brez besede pristala
  ob izvirniku. Kdor je mesto odlaganja že prej izbral prek vrstice
  stanja, ni vprašan znova; vsako nadaljnje shranjevanje kot doslej
  nadaljuje isto datoteko.
- Če varnostno preverjanje pred shranjevanjem javi sumljivo mesto, „Nazaj
  na preverjanje" zdaj vodi tja: prva najdba se zvije v sliko in obrobi
  rdeče, vrstica stanja jo navede. Doslej ste ostali sami s številko
  strani in koordinatami točke. Iz glavnega okna se za to odpre
  urejevalnik na tem mestu. Tudi pri opozorilu o odstopajočem številu
  strani gumb zdaj vodi tja – na prvo stran, ki obstaja le v enem od
  obeh dokumentov.
- Kdor predogled preklopi na „Drug ob drugem v dveh stolpcih", zdaj sam
  od sebe dobi okno, v katero se prilegata obe stezi – doslej sta se
  stiskali v staro širino, dokler ni sam povlekel. Razširi se kvečjemu do
  roba zaslona in se nikoli ne skrči nazaj; sama povlečena širina ostane.
- Priimek in osebno ime v ločenih stolpcih tabele (npr. „Priimek |
  Osebno ime" v prijavni potrditvi ali izvozu CSV) sta ostala odprta –
  vsaka celica zase je za prepoznavanje izgledala kot poljubna beseda
  brez povezave z imenom. Zdaj se prepoznata.
- Priimek in osebno ime na hrbtni strani vozniškega dovoljenja EU sta
  ostala odprta – tam stojita za uradnima kodama polj „1." in „2."
  namesto za nemško besedo, in prav to ju je pustilo neprepoznana. Zdaj
  se prepoznata, če zraven stoji številka vozniškega dovoljenja (koda
  polja „5.").
- Osebno ime imetnika vozila na prometnem dovoljenju je ostalo odprto –
  stoji za uradno kodo polja „C.1.2" namesto za nemško besedo, kot je
  „Ime", in prav to ga je pustilo neprepoznano. Priimek in osebno ime pod
  kodami polj C.1, C.1.1 in C.1.2 se zdaj prepoznata.
- Prva vrstica strojno berljivega območja (MRZ) na potnem listu ali
  osebni izkaznici je ostala odprta – nosi ime v obliki
  „PRIIMEK<<OSEBNO_IME" in je zdrsnila skozi tudi z novim prepoznavalnikom
  MRZ za vrstico s kontrolno številko. Najdba zdaj šteje le, če
  neposredno zraven stoji druga vrstica MRZ z veljavno kontrolno
  številko – vrstica z imenom sama nima lastne kontrolne številke.
- Druga vrstica strojno berljivega območja (MRZ) na potnem listu ali
  osebni izkaznici je ostala povsem neprepoznana – vsebuje številko
  potnega lista, datum rojstva in datum poteka v golem besedilu, a ni
  zadela nobenega obstoječega prepoznavalnika. Lasten prepoznavalnik zdaj
  preveri vse štiri kontrolne številke ICAO.
- Registrska tablica brez vsakega presledka do oznake je ostala odprta –
  „RegistrskaTablicaM-AB1234" ali „VozRegistrskaTablicaM-AB1234" sploh
  nista bili prepoznani, ker temeljno preverjanje tablice pred tablico
  predpostavlja neabecedni znak. Zadelo je navedbe vozil, kjer med
  besedo polja in tablico ni presledka.
- Telefonska številka brez vsakega presledka do oznake je ostala odprta –
  „ŠtevilkaMobitela0171/2345678" ali „Tel0171/2345678" sploh nista bili
  prepoznani, ker temeljno preverjanje telefonskih številk pred številko
  predpostavlja presledek ali ločilo. Zadelo je kontaktne navedbe, kjer
  med besedo polja in številko ni presledka.
- Rojstno ime za kratico „roj." sploh ni bilo prepoznano – „Julia
  Bergmann (roj. Weber)" je našlo le „Julia Bergmann", pika v „roj." je
  jezikovnemu modelu povsem preskočila sledeče ime. Zadelo je osebne
  navedbe z rojstnim imenom v oklepaju ali za vejico.
- Osebno ime pred vzdevkom v narekovajih je ostalo odprto, kadar sta pred
  njim skupaj stala nagovor in naziv – „Gospod dr. Klaus "KP" Peters" je
  dalo le „Peters", „Klaus" je ostal berljiv. Zadelo je podpise in
  kontaktne navedbe z nazivom in vzdevkom.
- Ime za kratko obliko „zH"/„zHd" (v roke) brez pike sploh ni bilo
  prepoznano – za razliko od „z.Hd." s piko je manjkajoča stavčna
  struktura potegnila ime s seboj. Zadelo je naslove brez pike v kratici.
- Ime za „p.A." (po naslovu) sploh ni bilo prepoznano – pika v kratici je
  jezikovnemu modelu povsem preskočila prepoznavanje imen. Zadelo je
  račune in prijave s skupnim naslovom.
- Ime za brez presledka prilepljenim „i.A."/„i.V." (po naročilu/v
  zastopstvu) sploh ni bilo prepoznano, na primer „i.A.Robert Lang" brez
  presledka – ista napaka stavčne zgradbe kot pri „p.A.". Zadelo je
  podpisne vrstice in podpise e-pošte pri primerih zastopanja.
- Gola prisotnostna lista v obliki naštevanja brez vsake dodatne navedbe
  („- Max Mustermann", tudi s piko na koncu vrstice) je izgubila vsa
  imena na isto zavoro, ki naj bi ščitila le stvarna naštevanja, kot je
  „- Barva: Modra". Taki seznami se zdaj prepoznajo.
- Datoteke, ki jih ni bilo več mogoče očistiti, je spet mogoče očistiti.
  Vrednost, ki je bila že zamenjana s prepoznavanjem, se je lahko znova
  našla v svoji lastni že zamenjani oznaki, kot je „[SVNR1]" – sklepni
  preizkus je nato zavrgel brezhibno očiščeno datoteko. Poleg tega se
  telefonski sklic v tabeli CSV zdaj odstrani zraven, in kdor omeji
  iskanje na posamezne vrste, jih zdaj dobi enako povsod v dokumentu –
  tudi v nadomestnem besedilu slike, glavi Excela, spustnem seznamu ali
  atributu HTML.
- Ime za e-poštno glavo „To:" (ali „To" brez dvopičja) ni bilo prepoznano,
  ker je tuj jezikovni model celo vrstico bral kot eno samo neopazno
  najdbo in ime v njej povsem pogoltnil – za razliko od „Cc:", „Bcc:" ali
  „From:" pred istim imenom. Ime za „To" se zdaj zanesljivo najde.
- Datuma poroke v lastnih pravilih ni bilo mogoče obravnavati kot datum
  („premakni" je bilo zavrnjeno z „obstaja le za datumske navedbe"), v
  skupinski dodelitvi vrst najdb je manjkal – s čimer ga prek oznak „Kaj
  se išče" ni bilo mogoče izklopiti – in namesto kratke oznake, kot pri
  datumu smrti, je dobil poln besedni zapis kot ogrado. Popravljeno za
  vseh šest tabel kratic/oznak.
- Vrednost, ki je bila v predogledu zavestno odizbrana, je bila lahko
  kljub temu zakrita drugje: če je bil na primer odizbran e-poštni
  naslov, je sicer sam naslov ostal, njegov lokalni del brez domene pa je
  bil zamenjan, takoj ko se je ujel z izpeljanim uporabniškim imenom
  nadalje izbrane osebe („anna.musterfrau@primer.si" ob „Anna
  Vzorčnaženska"). Odizbrano besedilo zdaj ostane tabu po celem
  dokumentu, ne glede na to, iz katere vrste najdbe izhaja.
- Datum rojstva je ostal neprepoznan, kadar ga je izpisek iz matičnega
  registra ali osebnega stanja vodil pod skupno glavo z krajem rojstva
  („Datum rojstva, kraj rojstva: 19.11.1982, Steyr") – druga beseda polja
  med „datum rojstva" in datumom je prepoznavanje doslej v celoti
  onemogočila.
- Že prepoznana telefonska številka je ostala berljiva v svoji skrajšani
  potrditveni obliki, kadar je bila drugje v istem dokumentu navedena le
  še z zadnjimi štirimi številkami („dosegljivi na številki ...5678",
  „povratni klic na ...5678") – ista oblika kot pri IBAN in kreditni
  kartici.
- Že prepoznana številka kreditne kartice je ostala berljiva v svoji
  skrajšani potrditveni obliki, kadar je bila drugje v istem dokumentu
  navedena le še z zadnjimi štirimi številkami („vaša kreditna kartica se
  konča na ...0366") – ista v plačilnih potrditvah običajna oblika kot
  pri IBAN.
- Že prepoznan IBAN je ostal berljiv v svoji skrajšani potrditveni
  obliki, kadar je bil drugje v istem dokumentu naveden le še z zadnjimi
  štirimi številkami („IBAN se konča na ...3201") – v potrditvenih
  e-pismih običajna oblika.
- Govorec v klepetu ali sejnem zapisniku je ostal neprepoznan, kadar je
  pred njegovim imenom stal nagovor („Gospod Bauer: …", „Gospa Koch: …")
  – s tem je pogosto zadelo tudi naslednjo vrstico govorca v istem
  zapisniku, ker je ostalo premalo prepoznanih vrstic, da bi dokument
  sploh veljal za zapisnik.
- Datum rojstva je ostal neprepoznan, kadar je beseda polja „rojen(a)"
  stala ZA datumom namesto pred njim („Otrok se je rodil dne 14.01.2026")
  – tako na primer potrdilo o starševskem dopustu ali materinski
  varnosti formulira datum rojstva otroka. Dosedanji vzorci so besedo
  polja vedno predpostavljali pred datumom.
- Oznaka obrazca z znakom odziva ali kljukico neposredno pred njo
  („Kontaktna oseba 😊:", „Kontaktna oseba ✓:") ni bila več prepoznana
  kot oznaka, ime pod njo ali za njo pa je bilo zato deloma le nepopolno
  najdeno (npr. le priimek pri „Mayer Roman").
- Ista vrzel je zadela tudi posebej varovane navedbe po čl. 9 GDPR
  (veroizpoved, zdravje, sindikat): znak odziva neposredno pred ločilom
  ali prelomom vrstice („Veroizpoved 😊: rimskokatoliška") je oznako
  povsem onemogočil, navedba pa je ostala povsem neprepoznana.
- Naslov z dvojnim imenom kraja z vezajem (npr. „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") je izgubil poštno
  številko v celoti, čeprav je bil kraj sam prepoznan in zakrit – na
  prometnem dokumentu ali dopisu je tako poštna številka ostala
  berljiva.
- Stolpec tabele brez razmika med stolpci (pravi izvleček besedila PDF)
  je pod stolpcem imen lahko dve po naključju druga ob drugi stoječi
  veliki začetnici napačno zakril kot osebo, na primer dve imeni krajev v
  podatkovni vrstici; zdaj to velja le, kadar nobena druga najdba na
  istem mestu ne prepozna že nečesa drugega.
- Isti stolpec imen je v isti obliki vrstice tudi dve jezikovnemu modelu
  neznani stvarni besedi (npr. „Frontend Backend", „Turbo Modul") napačno
  zakril kot osebo, ker tam nobena druga najdba ni sprožila zavore; zdaj
  dodatno zahteva, da vsaj eno od obeh besed jezikovni model sam prebere
  kot lastno ime.
- Nemška številka pokojninskega zavarovanja v svoji uradni polni
  razporeditvi (npr. „65 170839 J 08 8" – tako, kot stoji na izkaznici
  socialnega zavarovanja in plačilni listi) ni bila prepoznana in je
  ostala v izvirniku; prepoznani sta bili le strnjena oblika in oblika,
  razporejena le do črke.
- Davčna identifikacijska številka v svojem uradnem zapisu (razporeditev
  2-3-3-3, npr. „48 836 075 988" – tako, kot stoji na vsaki pravi davčni
  odločbi in vsakem obvestilu zveznega davčnega urada) sploh ni bila
  prepoznana in je ostala v izvirniku; pokrita je bila le redkejša
  razporeditev 3-3-3-2.
- Davčna številka Severnega Porenja-Vestfalije (npr. „221/5147/0815", s
  štirimestno namesto trimestne druge skupine) v davčnih odločbah sploh
  ni bila prepoznana in je ostala v izvirniku – vsaka druga nemška
  zvezna dežela je bila že pokrita.
- Pri pogodbah o zaposlitvi je ime za oznako „Delodajalec:" povsem
  spregledano, takoj ko je priimek hkrati navadna beseda (npr. „Bauer
  Anna") – „Delodajalec" stoji na seznamu tako kot oznaka imena kot
  oznaka podjetja, in dodelitev podjetja je prepisala dodelitev imena.
- V glavi najemne pogodbe z oznakama „Najemodajalec:"/„Najemnik:" je bil
  priimek, ki je hkrati navadna beseda (npr. „Bauer"), spregledan – ostal
  je prepoznan le priimek. Oštevilčene najemniške stranke („Najemnik 1:",
  „Najemnik 2:") so bile dodatno prizadete, tudi pri imenih brez te
  dvoumnosti.
- V sodnem zapisniku z oznakami „Priča:"/„Tožnik:"/„Toženec:" (tudi s
  štetjem, „Priča 1:", „Priča 2:") je bil priimek, ki je hkrati navadna
  beseda (npr. „Bauer"), prav tako spregledan – ostal je prepoznan le
  priimek.
- Pri dednem listu, pooblastilu, opominskem postopku in kupoprodajni
  pogodbi je bil priimek, ki je hkrati navadna beseda (npr. „Bauer"), za
  oznakami, kot so „Zapustnik:", „Dedič:", „Pooblastitelj:",
  „Pooblaščenec:", „Nasprotna stranka:", „Dolžnik:", „Upnik:", „Kupec:",
  „Prodajalec:", „Volilojemnik:" ali „Izvršitelj oporoke:", spregledan –
  deloma je ostalo prepoznano le osebno ime, deloma je odpadlo celo ime.
- Pri seznamu več strank pred ločilom naslovne rubrike „./." (npr. „Sand,
  Werner in Huber, Anna ./. Wechsler, Martina") je prva stranka ostala
  nemaskirana – prepoznana je bila le stranka, neposredno meječa na
  „./.".
- V ločilu naslovne rubrike „./." (npr. „Sand./.Wechsler") je bilo ime za
  znakom povsem spregledano, kadar tam ni bilo presledka – prepoznavanje
  je zadelo le s presledkom pred in za znakom.
- Priimek „Wahr" je bil povsem spregledan, kadar je stal sam (npr. „Gospa
  Wahr obravnava vašo zadevo.") – beseda po naključju stoji tudi na
  seznamu navadnih nemških besed, ki sicer filtrira najdbe imen iz
  stavkov, kot je „To je res." („Das ist wahr.").
- Priimki, kot so „Los", „Weit", „Rund" ali „Hoch", so bili povsem
  spregledani, kadar so stali sami (npr. „Gospod Hoch je prevzel
  vodstvo.") – vse štiri besede po naključju stojijo tudi na seznamu
  navadnih nemških besed, ki sicer filtrira najdbe imen iz stavkov, kot
  je „Približno sto gostov je prišlo na praznovanje." („Rund
  einhundert Gäste …“).
- Priimka „Ganz" ali „Recht" sta bila povsem spregledana, kadar sta
  stala sama (npr. „Gospod Ganz je podpisal pogodbo.") – obe besedi po
  naključju stojita tudi na seznamu navadnih nemških besed, ki sicer
  filtrira najdbe imen iz stavkov, kot je „Prav zares, to drži." („Ganz
  genau, das stimmt.").
- Polje obrazca z zvezdico ali dvignjeno opombno številko za oznako
  (npr. „Veroizpoved*: rimskokatoliška" ali „Verska pripadnost¹:
  evangeličanska") ni bilo prepoznano in je ostalo v golem besedilu –
  zadela je le oblika brez tega znaka.
- Isto polje je ostalo v golem besedilu tudi, kadar sta za oznako stali
  kar dve opombni oznaki (npr. „Veroizpoved**: rimskokatoliška" ali
  „Sindikat¹²: ver.di").
- Različica programske opreme, kot je „Različica programske opreme
  4.2.1.19" ali „Firmware Build 2.0.4.11", se ne zakrije več napačno kot
  naslov IP. Enako zdaj velja za številke dokazil in opravil, kot sta
  „Številka računa 10.20.30.40" ali „Številka naročila 7.8.9.10".
- Dva IBAN-a neposredno drug pod drugim (npr. lasten in tuj poslovni
  partner v glavi računa) nista bila več oba prepoznana – drugi je
  ostal neopažen.
- Označen IBAN je včasih potegnil s seboj naslednjo besedo v stavku
  ("Bančna povezava AT61 … bo bremenjena" je bilo zakrito do vključno
  "bo"), takoj ko je bila naslednja beseda z malo začetnico – ostanek
  golega besedila zraven je pri tem ostal nedotaknjen.
- Naslovi iz Lihtenštajna se zdaj prepoznajo („FL-9490 Vaduz"), tako kot
  doslej že nemški, avstrijski in švicarski.
- Številka potnega lista se zdaj prepozna in odstrani za svojo oznako
  (npr. „Številka potnega lista: C01X00T471").
- Številka dovoljenja za prebivanje in prijavnega potrdila se zdaj
  prepozna in odstrani za svojo oznako.
- Identifikacijska številka za svojo oznako se zdaj prepozna tudi, kadar
  namesto dvopičja loči pomišljaj (npr. „Kupčeva številka – K903944").
- Bančna povezava, označena kot „IBAN" ali „Številka računa", se zdaj
  prepozna tudi, kadar namesto dvopičja loči pomišljaj.
- Ime za oznako, kot je „Kontaktna oseba (prodaja)" ali „Referent/-ka",
  se zdaj prepozna tudi z dodatkom v oklepaju ali spolno nevtralno
  končnico s poševnico.
- Ista oblika spola z zvezdico („Referent*ka") se zdaj prav tako
  prepozna.
- Ime za oznako se zdaj prepozna tudi, kadar namesto dvopičja loči
  enačaj (npr. „Kontaktna oseba = Mayer Roman" ali
  „Kontaktnaoseba=Mayer Roman"), kot je običajno v nastavitvenih
  datotekah ali glavah CSV. Če v vrstici stoji več takih parov
  oznaka-vrednost, ločenih s podpičjem, se prepozna le prva vrednost
  namesto cele preostale vrstice.
- Par koordinat GPS za besedo „koordinate" se zdaj zanesljivo prepozna
  (npr. „Koordinate: 48.2082, 16.3738") – beseda je v notranjem katalogu
  nosila napačno sklonsko obliko.
- Identifikacijska številka za svojo oznako (kupčeva številka, pogodbena
  številka, opravilna številka, številka osebne izkaznice in približno
  sto nadaljnjih besed polja) ni bila več prepoznana, takoj ko oznaka ni
  natančno ustrezala shranjeni veliki/mali začetnici – „kupčevaštevilka:"
  v e-pošti ali „KUPČEVA ŠTEVILKA:" v glavi obrazca sta ostali
  nedotaknjeni.

### Novo

- **Realistične nadomestne vrednosti so zdaj zavestno uporabljen primer,
  ne privzeta vrednost.** Tabela izjem v zavihku „Ograde" se začne prazna.
  Nov gumb tja na željo vnese verjetne napačne vrednosti za ime, kraj,
  naslov, organizacijo, e-pošto, telefon, interno številko in IBAN.
  Denarne zneske izrecno pusti pri oštevilčeni ogradi; strategija
  „izmisli si" ostaja za posamezne vrste še naprej ročno izbirljiva.
- **Stopnja UI lahko uporabi grafično kartico.** Pod Windows je za to
  mogoče naknadno naložiti dober 17 MB velik dodatni paket; nato stopnja
  UI na primerni grafični kartici računa znatno hitreje kot na
  procesorju. Kdor je nima ali ničesar ne naloži, dela naprej
  nespremenjeno – le počasneje. Na macOS je pospešitev tako ali tako
  že vgrajena.
- **Dve novi obvestili prek ikone opravilne vrstice**: kadar je predogled
  pred zamenjavo pripravljen za pregled in kadar je obdelava dokončana.
  Obe sta privzeto vklopljeni in ju je mogoče pod *Nastavitve → Program →
  Obvestila* posamično izklopiti.

### Spremenjeno

- **Številka osebne izkaznice in vozniškega dovoljenja se zdaj
  prepoznata**, kadar pred njima stoji njuna oznaka („Številka osebne
  izkaznice: …", „Številka vozniškega dovoljenja: …") – doslej sta obe
  padli skozi vsako prepoznavanje.
- **Maskuro zdaj sledi kontrastnim oblikam Windows.** Kdor je pod
  *Nastavitve → Dostopnost → Kontrastne teme* eno vklopil, jo je doslej
  dobil povsod razen tu: Maskuro je nato nastavil svoje lastne barve.
  Zdaj ostane pri oblikovanju sistema – okno, seznami, odlagalna cona,
  dnevnik in barve stanja. Barvni semafor preverjanja v predogledu in
  oknu Popravi tam zavestno odpade; kar pove, tako ali tako stoji zraven
  kot znak in kot beseda.
- **Potreba po preverjanju ni več le v barvi.** Rdeča, oranžna in zelena
  so skoraj enako svetle – kdor ima rdeče-zeleno slepoto, je v predogledu
  in predalu najdb videl seznam brez razlik, in to je približno vsak
  dvanajsti moški. Vsaka vrstica zdaj dodatno nosi znak, ki se razlikuje
  po obliki: ▲ preveri najprej, ● preveri, ○ dobro podprto, ◆ brez
  ocene. Kratki namig ga navede z besedami, bralnik zaslona pa ga
  prebere.
- **Alt spet odpira menije kot običajno.** Menijska vrstica ni imela
  tipkovnih bližnjic: kdor ni uporabljal miške, se je moral po vsakem
  meniju premikati s puščicami. Zdaj vsak vnos nosi podčrtano črko –
  Alt+D za „Datoteka", od tam Z za „Zapri" –, in sicer v vseh jezikih
  vmesnika.
- **Elementi upravljanja bralniku zaslona spet povedo, čemu služijo.** V
  oknu Popravi, oknu pravil, dnevniku, seznamih besed, pomoči, iskalnem
  teku in petih nadaljnjih oknih so bili seznami, iskalna polja, spustni
  seznami in drsniki doslej naznanjeni le kot „drevo" ali „spustno polje"
  – brez česa. Približno štirideset mest zdaj nosi ime. (Glavno okno je
  bilo v redu že od avgusta; okna, ki so prišla pozneje, tega koraka
  niso nikoli naredila.)
- **Kdor upravlja s tipkovnico, povsod vidi, kje se nahaja.** Pri drsnikih
  potrebe po preverjanju, pri potrditvenem polju in gumbu „nikoli več"
  predogleda, pri naslovih vrst v njem, pri predalu strani okna Popravi
  in pri stranski vrstici nastavitev je manjkal rob, ki ga sistem sicer
  nariše okoli elementa, na katerega je bilo skočeno.
- **Večja sistemska pisava ničesar več ne odreže.** Kdor pod
  *Dostopnost → Velikost besedila* nastavi nad 175 %, je doslej izgubil
  konec oznak v nadzoru mape in v poljih tipkovnih bližnjic. Seznam
  poglavij pomoči je dolga imena poglavij odrezal že pri običajni pisavi;
  zdaj jih prelomi in polno ime navede v kratkem namigu.

- **Prepoznavanje je znatno hitrejše.** Prepoznavalnik za označene
  identifikacijske številke („Kupčeva številka: K903944") je doslej za
  vsak besedilni odsek zaporedno preveril prek 1200 posamičnih vzorcev –
  to je bila največja posamezna postavka časa prepoznavanja, pri vsakem
  odstavku in vsaki celici tabele. Zdaj je to en sam vzorec z istim
  rezultatom: na merilnem korpusu se ne spremeni niti ena najdba,
  osnovna stopnja na besedilni odsek pa je približno tri- do štirikrat
  hitrejša.
- **Okno se ob zagonu prikaže takoj.** Doslej je glavno okno naložilo
  popolna jezikovna orodja, preden se je sploh pokazalo – približno
  štiri sekunde slepega časa ob vsakem zagonu. Modeli se zdaj po načrtu
  nalagajo v ozadju, medtem ko okno že stoji; gumb Očisti se kot doslej
  sprosti šele, ko je vse pripravljeno. Tudi goli informativni klici
  ukazne vrstice (na primer `--version`) zdaj odgovorijo takoj namesto
  po nekaj sekundah.
- **Slike se pri samodejnem prepoznavanju jezika berejo le še enkrat.**
  Doslej je optično prepoznavanje pri privzeti nastavitvi „Jezik:
  samodejno" isto sliko preletelo dvakrat – enkrat za ugibanje jezika,
  enkrat za resnično preverjanje. Slikovne datoteke, slike iz odložišča
  in besedilno okno so s tem približno dvakrat hitreje dokončani; pri
  izklopljenem optičnem prepoznavanju odpade doslej neopazno vseeno
  tekoče branje v celoti.
- **Shranjene spletne strani in e-pošta se čistijo hitreje.** Vrednosti v
  atributih HTML, komentarjih in vdelanih podatkovnih blokih so se
  doslej prepoznavale posamično – občinska stran s stotinami oznak je
  postavila stotine posamičnih vprašanj prepoznavanju. Zdaj se zberejo in
  za vsako različno vrednost prepoznajo le enkrat; na merilnem korpusu se
  ne spremeni nobena najdba, .html in .eml sta približno tretjino
  hitrejša.
- **Tudi stranska odlagališča preglednic in predstavitev se prepoznavajo
  zbrano.** Nadomestna besedila, formulski nizi, oznake diagramov,
  komentarji, vmesni pomnilnik vrtilnih tabel in lastnosti dokumenta so
  za vsako vrednost postavili lastno vprašanje prepoznavanju – zvezek s
  tisoči vrstic vrtilne tabele ustrezno tisoče. Zdaj teče zbran zagon
  prek različnih vrednosti, sklepni naknadni polni prehod pa teče le, če
  so od tekočega besedila dejansko pristopile nove vrednosti. Na
  merilnem korpusu se ne spremeni nobena najdba.
- **PDF-ji, bogati z obrazci, se čistijo hitreje.** Polja, opombe,
  zaznamki in povezave množično ponavljajo iste vrednosti („Off" pri
  vsakem potrditvenem polju, isti avtor pri vsaki opombi) – vsak je
  doslej postavil svoje lastno vprašanje prepoznavanju. Na zagon se
  vrednost zdaj prepozna le enkrat; zamenjava in naknadni pregled
  skladnosti tečeta nespremenjeno za vsako mesto.
- **Velike datoteke preglednic (.csv/.tsv) se čistijo znatno hitreje.**
  Štirje naknadni prehodi preglednic so isto datoteko doslej vsak zase
  razčlenili znak za znakom v celice (pri 40 MB približno 30 s dodatnega
  dela); zdaj razčlenitev teče enkrat. Prepoznavanje glave stolpca (stolpci
  datuma rojstva in kadrovske številke) namesto vprašanja na celico
  postavi zbrano vprašanje – ob enakih najdbah približno dvajsetkrat
  hitreje. In združevanje stolpca imen velikih kadrovskih seznamov ni več
  kvadratno v številu vrstic.
- **Predal kazalnikov ne zamrzne več okna.** Razpiranje kazalnikov je pri
  mnogih velikih datotekah najprej v celoti prebralo njihovo besedilo in
  pri tem okno za sekunde ustavilo. Izračun zdaj teče v ozadju; predal se
  odpre takoj in številke doda naknadno.
- **Poročilo iskalnega teka ne zamrzne več okna.** Po preiskavi mnogih
  tisoč datotek se je skupna mapa za vsako prizadeto datoteko znova
  izračunala; pri velikih zagonih je okno pri tem stalo dvomestno število
  sekund. Poročilo se zdaj prikaže takoj.
- **PDF-ji z optičnim prepoznavanjem besedila se preverijo hitreje.**
  Vsaka stran se je pri protibranju po nepotrebnem dvakrat pretvorila v
  format PNG; zdaj se prenese že obstoječa slika. Rezultat je
  nespremenjen, le preverjanje teče hitreje.
- **Anotacije s prelivom na velikih slikah ne trzajo več.** Pri
  poznejšem prilagajanju ročic anotacije s prelivom se je preliv doslej
  znova izračunal točko za točko – na velikem posnetku zaslona vidno
  zatikanje. Rezultat je isti, le brez premora.

### Odpravljeno

- **Križec za odstranitev datoteke s seznama je spet preprost X.** Novo
  orodje urejevalnika „Odstrani" je pomotoma uporabljalo isto oznako
  simbola in zato pokazalo svoj rdeči križ skupaj s črtkano besedilno
  črto tudi v vsaki vrstici datoteke. Obe dejanji imata zdaj ločeni imeni
  simbolov in obdržita vsako svoj ustrezni prikaz.
- **Večdelne navedbe se v PDF-jih zdaj prepoznajo tudi čez viden prelom
  vrstice.** Maskuro geometrijsko ustvarjeno besedilo strani dodatno
  bere kot zamikovno enak pogled tekočega besedila. To velja za vse
  prepoznavalnike osnovne in visoke stopnje ter lastne iskalne vzorce, ne
  le za prej vidni primer „Diabetes mellitus tipa 2". Prazne vrstice in
  prepoznane meje tabel ali odsekov ostajajo trdne meje; najdbe se še
  naprej natančno prilegajo besedam za zakritje.
- **Primer pri „Psevdonimiziranje" si je nasprotoval.** Stavek je
  obljubljal „ista oseba, ista številka" in nato pokazal dve različni
  številki – ravno sliko, ki je pravilna pri „Anonimiziranje". Oba
  primera se zdaj ujemata z lastnim stavkom.
- **Na novo vstavljena ograda je pri „Obnovi izvirnik" lahko ostala kot
  prekrit kup črk namesto da bi izginila.** Enobarvno vstavljena ograda
  je doslej za vsak znak pisala lasten izhodni ukaz, od katerih je le
  prvi nosil lastno besedilno matriko – pri naslednjem urejanju istega
  mesta (na primer „obnovi izvirnik" takoj za tem) so preostali ukazi
  znakov po vrsti dobili indekse znakov prvega, in ograda je razpadla na
  dve prekrivajoči se legi. Enobarvna ograda zdaj dobi en sam izhodni
  ukaz za celo svoje besedilo.

- **Če je ista zakrita ali odstranjena vrednost stala pod dvema
  vrsticama v oknu Popravi in sta bili obe označeni za preklic, je
  druga vrstica napačno štela kot „ni enolično" – čeprav je bila vrednost
  že zdavnaj obnovljena.** Obe vrstici zdaj veljata za opravljeni.

- **Ime za „Reply-To:" se zdaj najde.** V glavi e-pošte, kot je
  „Reply-To: Huber", ime doslej ni bilo prepoznano – jezikovni model je
  „Reply-To:" prebral kot lastno, napačno osebo in spregledal pravo ime
  za tem.

- **Besedi glave e-pošte „Reply" in „Fwd" se ne zakrijeta več sami kot
  ime.** V vrstici zadeve, kot je „Fwd: Ponudba od Huber", je bila
  doslej poleg imena zakrita tudi glavna beseda sama kot oseba.

- **„Delodajalec: Siemens AG" se zdaj prepozna kot podjetje, ne več kot
  oseba.** Če je vrednost podjetja za oznako „Delodajalec" nosila pravno
  obliko, kot je d.o.o., d.d. ali k.d., je kljub vklopljenemu
  prepoznavanju organizacij ostala najdba osebe – le ožji primer brez
  pravne oblike („Wollmuth in partnerji") je bil doslej prepoznan kot
  podjetje.

- **Enkrat prepoznan naslov ne ostane več na drugem mestu.** Če je bil
  naslov ulice prepoznan in zamenjan na enem mestu, je lahko isti naslov
  ostal na drugem mestu – na primer v težko berljivi nogi skeniranega
  dokumenta, kjer ga je samodejno optično prepoznavanje prebralo
  popačeno. Naslovi se zdaj, kot že dlje časa imena in podjetja, dosledno
  odstranjujejo po celem dokumentu.

- **E-pošta z več prejemniki je bila pri čiščenju tiho poškodovana.**
  Sporočilo `.msg` z dvema ali več prejemniki je pri shranjevanju
  izgubilo dele svoje notranje zgradbe, tako da je bil očiščen rezultat
  nepopoln. Vzrok je bila zamenjava enako poimenovanih notranjih
  sestavin, ki se pojavijo pri vsakem prejemniku. Taka sporočila se zdaj
  znova v celoti zgradijo.

- **Dveh priloženih preizkusnih dokumentov ni bilo mogoče odpreti v Wordu
  in PowerPointu.** Kdor je prenesel merilni korpus, je pri
  `format_dokument.docx` dobil „Napaka pri odpiranju datoteke v Wordu" in
  pri `format_praesentation.pptx` „Datoteka je poškodovana". Obe datoteki
  sta bili napačni že, preden se ju je Maskuro dotaknil – očiščena
  različica je napako le prenesla naprej. LibreOffice je obe odprl brez
  težav, zato ni nihče opazil.

- **Lastno UI v internetu se zdaj naslavlja šifrirano.** Kdor pri lastnem
  UI vnese zunanji naslov brez „https://" (kot pogosto piše na listku
  IT-službe), ga je doslej dosegel prek nešifrirane povezave – nezakrito
  besedilo je šlo ven v golem besedilu. Taki naslovi se zdaj naslavljajo
  prek „https://"; strežnik v lastnem omrežju ostaja nespremenjeno
  dosegljiv. Če strežnik sledi preusmeritvi na drug računalnik, dostopni
  ključ ne potuje več zraven.

- **Tudi poškodovana slika zdaj izgubi svoje skrite metapodatke.** Če
  vdelane slike ni bilo mogoče več v celoti odpreti (na primer obrezana
  fotografija), je doslej obdržala svoje podatke EXIF in GPS – kraj
  zajema in ime fotografa sta v rezultatu ostala nevidna. Take slike se
  zdaj teh podatkov znebijo tudi, kadar jih sploh ni več mogoče
  prikazati.

- **Vdelana datoteka, ki je ni bilo mogoče očistiti, se zdaj sporoči
  namesto tiho posredovana.** Če je v predstavitvi ali zvezku ležal
  vdelan predmet, ki je bil pregneteno vdelan ali se ni dal odpreti, je
  doslej ostal nespremenjen v rezultatu, brez opozorila – datoteka je
  veljala za očiščeno. Taki primeri zdaj stojijo v opozorilu „NI bilo
  mogoče preveriti", enako kot vdelan star format.

- **Temni seznami so spet dosledno temni in berljivi.** Na macOS so se
  seznami datotek menjavali med skoraj črnimi in svetlo sivimi
  vrsticami; v Popravi je zato ista zelena, oranžna ali rdeča
  preverjevalna vrednost izgledala glede na vrstico drugače. Okno,
  seznami, pisava, ograde in izbor zdaj izhajajo iz skupne svetle/temne
  palete. Barvno kodiran seznam najdb poleg tega ne polaga več
  zebrastih prog pod svoje barve.

- **Poklicne navedbe z „kot" so bile napačno zakrite kot ime.** Stavek,
  kot je „Kot kuhar je pri nas zaposlen že štiri leta.", je izgubil
  poklic, ne le ime – „kot" uvaja navedbo vloge enako kot „ta" ali „ti".
  Prave priimke na istem mestu (na primer z nagovorom pred njimi) to ne
  zadeva.

- **Naslov tabele je lahko potegnil številko postavke v denarni znesek**
  (le pri vklopljeni možnosti „Odstrani tudi denarne zneske"). Če se je
  vrstica končala z valuto („… Cena na enoto EUR") in se je naslednja
  začela s številko, je iz tega čez prelom vrstice napačno nastal
  znesek. Ločilo med valuto in številko zdaj ostane v isti vrstici.

- **Kratka kratica z velikimi črkami je lahko pogoltnila cel del stavka
  ali se pripela pred pravilno prepoznano ime.** Če je v vrstici stala
  dvočrkovna velika beseda, kot je „DI", „AG" ali „KG" – vsakdanje
  kratice, ne imena –, se je cela vrstica poskusno preiskala z malimi
  začetnicami, kratica pa je pri tem občasno potegnila sosednje besede
  (tudi glagole) v eno samo domnevno ime. Šele od treh črk naprej z
  veliko začetnico zapisana beseda zdaj sproži to drugo preverjanje. Pri
  nekoliko daljših kraticah, kot sta „CEO" ali „USB", je ostala druga
  napaka: že pravilno najdeno ime („Schneider") je kratico pred njim
  dobilo pripeto kot predpono v rezultat („CEO Schneider"). Kratica zdaj
  ostane zunaj.

- **Datum rojstva brez presledka za njim je ostal.** Če za „rojen(a)" ni
  bilo vrzeli pred datumom – kot je običajno v tesno postavljenih
  obrazcih („rojen(a)14.03.1988") –, Maskuro polja ni prepoznal in je
  datum pustil nedotaknjen. Razširjene kratke oblike, kot je „Datum
  rojstva" ali „Datum roj.", se zdaj prav tako prepoznajo.

- **IBAN s poševnicami kot ločilom je ostal.** Kot pri telefonskih
  številkah („0664/1234567") nekatere predloge tudi IBAN zapišejo v
  blokih s poševnico („AT48/3200/0000/1234/5864") namesto s presledkom
  ali vezajem. Ta zapis se zdaj prav tako prepozna.

- **Avstrijska številka socialnega zavarovanja z vezajem, piko ali
  poševnico je ostala ali bila napačno označena.** Med obema blokoma
  številk je bil doslej predviden le presledek; zapisi, kot so
  „1237-010180", „1237.010180" ali „1237/010180", niso bili prepoznani
  (ali so bili v primeru poševnice prepoznani pod napačno vrsto).
  Kontrolna številka še naprej potrdi vsako najdbo, ne glede na ločilo.

- **Ime za „c/o" v naslovu sploh ni bilo odstranjeno.** „c/o Max
  Mustermann, Hauptstraße 5, 1010 Dunaj" je zakrilo ulico in kraj, ime za
  tem pa je v celoti pustilo. Ime se zdaj prepozna; „c/o" samo ostane
  vidno kot napotek naslova.

- **S pikami razporejena številka kreditne kartice je ostala.** Zapisi,
  kot je „4111.1111.1111.1111", niso bili prepoznani; s presledki ali
  vezaji ločene številke to ni zadelo. Kontrolna vsota še naprej potrdi
  vsako najdbo.

- **Z vezaji razporejena davčna identifikacijska številka je ostala,
  enako avstrijski ID DDV z vezajem ali piko.** Presledek, poševnica in
  pika sta bila pri davčnem ID že predvidena, vezaj je manjkal; pri ID
  DDV („ATU12345678") sta za predpono manjkala vezaj in pika. Kontrolna
  številka davčnega ID še naprej potrdi vsako najdbo.

- **Vrednost polja v narekovajih je ostala, na primer v vrstici v obliki
  JSON, kot je „ime": „Max".** Prepoznavanje prek oznake polja („Ime:
  …") je doslej predpostavljalo, da niti oznaka niti vrednost sama ne
  stojita v narekovajih. Take vrstice se zdaj prav tako prepoznajo –
  enako oznake polj s predhodno piko seznama YAML („- Ime: Max") ali
  tabulatorjem namesto presledka pred dvopičjem.

- **Beseda glave e-pošte „Sent" je bila sama zakrita kot ime.** V glavi,
  kot je „Sent: Huber", je doslej zadelo tako „Sent" kot pravo ime;
  sorodne glavne besede, kot sta „Subject" ali „Zadeva", to ni nikoli
  zadelo. „Sent" zdaj prav tako ostane.

- Ime za glavama „Errors-To:" ali „Resent-From:" je ostalo neopaženo,
  kadar je taka vrstica stala kopirana v golem besedilu (na primer
  posredovano sporočilo ali poročilo o dogodku) – za razliko od
  „Reply-To:" ali „Return-Path:" je ime tu povsem odpadlo namesto le
  nenatančno razmejeno. Zdaj se najde.
- Ista datoteka je pri dveh čiščenjih včasih dala različen rezultat: če
  sta dve prepoznavanji zadeli natanko isto mesto z enako dolžino in
  enako gotovostjo (npr. „Številka socialnega zavarovanja 1237/010180"
  kot AT_SVNR ali kot splošna identifikacijska številka), je bilo od
  naključja odvisno, katera zmaga – vrednost je bila odstranjena v obeh
  primerih, spremenila se je le oznaka ograde. Izenačenje se zdaj vedno
  razreši enako.
- Funkcijsko poimenovanje neposredno pred samostalnikom (npr. „Lečeči
  zdravnik: dr. …" ali „Pristojni referent je …") je bilo včasih napačno
  zakrito zraven, kot da bi bilo samo ime. Prave priimke zraven to ne
  zadeva.
- Pravi priimek, ki po naključju izgleda kot pridevnik (npr. „Schöne",
  „Lange", „Junge") in stoji neposredno pred nadaljnjim samostalnikom
  (na primer „Kontaktna oseba: Schöne Assistentin"), je od zadnjega
  popravka ostal nezakrit v besedilu – uhajanje podatkov. Zdaj se v tej
  obliki kot ne-ime obravnava le ozko omejen seznam pravih funkcijskih
  poimenovanj (npr. „Lečeči", „Pristojni").
- Samostojen priimek na koncu večvrstične najdbe imena, ki po naključju
  izgleda kot pridevnik (npr. „Schwarz", „Kurz", „Alt", „Frisch", „Gut",
  „Reich"), je pred neposredno sledečim dvopičjem ostal neprepoznan –
  čiščenje ga je zamenjalo z oznako polja, kot je „Telefon:". Zaprt
  seznam znanih dvoumnih priimkov ga zdaj varuje.
- Samostojen priimek, ki je po naključju navadna nemška beseda
  („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange"), je doslej **v
  celoti** izginil – tudi v preprostih stavkih, kot je „Gospod Gross je
  podpisal pogodbo." Vzrok je bil v lastnem seznamu stop-besed spaCy, ki
  te besede vsebuje; zaprt seznam znanih priimkov jih zdaj varuje pred
  zavrženjem.
- Pri delovnih, posojilnih, poroštvenih, skrbniških in stečajnih
  pogodbah ter pri skrbništvu/oskrbi in izvedenskih naročilih je bil
  priimek, ki je hkrati navadna beseda (npr. „Bauer"), za oznakami, kot
  so „Naročnik:", „Izvajalec:", „Delavec:", „Zavarovanec:",
  „Posojilodajalec:", „Posojilojemalec:", „Porok:", „Dajalec
  zavarovanja:", „Skrbnik premoženja:", „Ustanovitelj sklada:",
  „Stečajni upravitelj:", „Izvedenec:", „Sodni izvedenec:", „Skrbnik:"
  ali „Oskrbnik:", spregledan – deloma je ostalo prepoznano le osebno
  ime, deloma je odpadlo celo ime.
- V impresumu je bil priimek, ki je hkrati navadna beseda (npr. „Bauer"),
  za oznakami „Poslovodja:", „Poslovodkinja:", „Zastopnik:", „Lastnik:"
  ali „Lastnica:", spregledan – pri „Poslovodja:"/„Lastnik:" je odpadlo
  celo ime, pri „Zastopnik:" je ostalo prepoznano le osebno ime.
- Kontaktni blok, katerega oznaka je stala sama na svoji vrstici in nosila
  spolno nevtralno obliko z dvopičjem („Kontaktna:oseba", ime pod njo), je
  bil **v celoti** spregledan – dvopičje je bilo prebrano kot ločilo
  polja, „oseba" kot (zavržena) vrednost polja, pravo ime v naslednji
  vrstici pa zato nikoli ni prišlo na vrsto. Oblika z zvezdico
  („Kontaktna*oseba") s tem ni bila prizadeta.
- Če sta ime in oznaka z isto spolno obliko z dvopičjem stala v **eni**
  vrstici („Kontaktna:oseba Anna Berger"), je ograda v zamenjavo
  potegnila besedo „oseba", namesto da bi odstranila le ime – ime samo je
  bilo še naprej v celoti zajeto.
- Ime v stolpcu tabele pod glavo stolpca za osebe (npr. „Priimek Ime
  Datum rojstva" nad „Bauer Anna 03.05.1985", kot v plačilni listi) je
  bilo povsem spregledano, takoj ko je med stolpci stal le en sam
  presledek in nobena vrstica ni začela s strukturno številko – prav v
  taki obliki pravi izvleček besedila PDF take vrstice dostavi.
- V klepetu ali sejnem zapisniku z imenom govorca pred dvopičjem (npr.
  „Bauer 🙂: Strinjam se s predlogom.") je ime ostalo povsem neprepoznano,
  takoj ko je med imenom in dvopičjem stal znak odziva in je bil priimek
  hkrati navadna beseda („Bauer", „Koch", „Schneider" ipd.) – cel
  zapisnik je tako lahko ostal brez enega samega prepoznanega govorca.
- Ista vrzel vrstic govorca je obstajala tudi z drugimi vmesnimi znaki
  pred dvopičjem: dodatkom statusa v oklepaju („Bauer (predsedstvo): …",
  „Bauer (odsoten): …"), uro v oglatih oklepajih („Bauer [14:32]: …") in
  opombnim znakom neposredno ob imenu („Bauer*: …"). Tudi tu je govorec
  ostal povsem neprepoznan, takoj ko je bil priimek hkrati navadna
  beseda.
- Če je že prepoznana oseba v priloženem izsečku zapisnika ali dnevnika
  istega sporočila (na primer podporna vozovnica) dodatno stala kot
  uporabniško ime v obliki „ime.priimek" – z malo začetnico, brez
  presledka, povezano s piko –, je to golo ime ostalo berljivo, čeprav
  je bilo isto ime v dopisu že zakrito.
- Ista vrzel uporabniškega imena je obstajala tudi s podčrtajem namesto
  piko („ime_priimek") – enako razširjena oblika v izsečkih zapisnikov
  in dnevnikov.
- Tudi v obratnem vrstnem redu je uporabniško ime ostalo berljivo
  („priimek.ime" oziroma „priimek_ime") – nekateri sistemi priimek v
  uporabniškem imenu dnevnika postavijo pred ime namesto za njim.
- Datum smrti je ostal neprepoznan, kadar zraven ni stala nobena druga
  navedba („Gospod Bauer je umrl 12.03.1985") – za to doslej sploh ni
  bilo lastnega prepoznavanja, generični datum pa pri tem standardnem
  pragu ne zadene.
- Datum smrti je ostal neprepoznan tudi, kadar je stavek namesto
  deležnika uporabil glagolsko obliko („Gospa Meier je umrla
  12.03.1985.", „Umrl je 12.03.1985.") – zadela je doslej le oblika „je …
  umrl(a)".
- Datum poroke je ostal neprepoznan, ne glede na obliko, v kateri je
  stal („Sklenitev zakonske zveze 12.03.2010", „Datum poroke:
  12.03.2010", „Gospod in gospa Bauer sta se poročila 12.03.2010") – za
  to doslej sploh ni bilo lastnega prepoznavanja, generični datum pa pri
  tem standardnem pragu ne zadene.

- **V urejevalniku Popravi je drugi okvir čez ravno vstavljeno ogrado
  lahko pustil rdeč ostanek znakov**, na primer „[G" namesto „[BEG1]" –
  brez vsakega opozorila, saj ostanek ni več sodil k zaupni navedbi (ta
  je bila odstranjena že v prvem koraku), temveč le še k lastni ogradi.
  Vzrok je bilo barvanje: na novo vstavljena ograda se je zapisala v
  datoteko po znakih, tudi pri enobarvni privzeti vrednosti – poznejši
  okvir čez isto mesto zato ni več našel povezanega besedila, na
  katerem bi se lahko umestil. Enobarvna ograda zdaj stoji kot en kos v
  toku, kot je to samodejno čiščenje počelo od nekdaj; le pravi preliv
  ali mavrično besedilo še naprej potrebujeta posamezne znake. Vgrajena
  protipreizkušnja zdaj tak ostanek prepozna tudi, kadar natančnega
  zaporedja znakov ograde ni več.
- Oštevilčen seznam imen s stopnjevano strukturno številko („1.1 Max
  Mustermann", „1.2 Huber Franz" …) je izgubil vsa imena na isto
  zavoro, ki naj bi ščitila le prave strukture in sezname postavk – brez
  glave stolpca nad seznamom ni bilo priče, na kateri bi se ime lahko
  rešilo.
- Ime v angleški prijavni vrstici sistemskega dnevnika („Accepted
  password for Max Mustermann from 10.0.0.5 port 51000 ssh2") ni bilo
  prepoznano – nemški jezikovni model ga je našel le, če je pred njim
  stalo „invalid user", sicer je ostalo. Taki izsečki dnevnika se pogosto
  nespremenjeno priložijo poročilu o dogodku. Imena za „for" pred
  naslovom IP se zdaj zanesljivo prepoznajo.
- Ime plačnika v sklicu SEPA mandatne reference izpiska računa ali
  dnevnika knjiženja (npr. „MREF+Mustermann Klaus+SVWZ+Najemnina
  avgust") je ostalo odprto – brez presledka, brez stavčne strukture,
  le s „+" ločena polja z velikimi črkami, in v tam običajnem vrstnem
  redu „priimek ime" ga prepoznavanje ni našlo niti po naključju. Zdaj se
  prepozna.
- Ulica skupaj s hišno številko v prvi vrstici tabele naslovov (npr.
  „Priimek | Ime | Ulica | Poštna št. | Kraj") je ostala odprta –
  jezikovni model je tam ugibal napačen, a daljši kraj čez več stolpcev,
  ta pa je izpodrinil pravilno, krajšo najdbo naslova. Zdaj se prepozna.
- Ista vrzel se je pojavila s tabulatorjem namesto „|" ali „;" kot
  ločilom stolpcev – tam je naslov celo izginil namesto le izgubil delček.
  Zdaj se prepozna.
- Ulica s hišno številko je ostala odprta, kadar ji je neposredno brez
  presledka sledila poštna številka z vejico (npr. „Bahnhofstrasse
  12,80331 München", kot v z vejico ločenem stolpcu tabele) – vejica je
  izgledala kot decimalno mesto količine, in ulica zato vzorcu sploh ni
  veljala za naslov. Zdaj se prepozna.
- Ulica s hišno številko je ostala odprta, kadar ji je neposredno brez
  vejice sledila predpona kraja „Sv." (Sveti) (npr. „Hauptstraße 5 Sv.
  Pölten", glava dopisa brez predhodne poštne številke) – „Sv." je
  izgledal kot kosovna enota, in ulica zato vzorcu sploh ni veljala za
  naslov. Zdaj se prepozna.
- Dodatek vrat/stopnišča za hišno številko (npr. „Lerchenfelder Gürtel
  43/12") je ostal vidno odprt, kadar mu je neposredno sledila
  posamezna črka, ki se po naključju ujema z mersko enoto (npr. „h" za
  uro) – naslov se je nato očistil le do hišne številke brez dodatka,
  namesto da bi zadel v celoti ali sploh ne.
- Vrstica zadeve s priimkom, enakim poklicu, pred osebnim imenom
  („Zadeva: Bauer Anna", „Zadeva: Bauer, Anna") je doslej ostala povsem
  neprepoznana – tudi sredi dokumenta s predhodnim polnim stavkom. Zdaj
  se prepozna.
- Nemška davčna številka s presledkom, piko ali vezajem med bloki (npr.
  „Davčna številka: 30 815 08153" ali „30.815.08153") doslej ni bila
  prepoznana – najden je bil le zapis s poševnico. Zdaj se prepozna.
- Ime za medicinsko oznako polja („Pacient:", „Osebni zdravnik:",
  „Lečeči zdravnik:", „Napotni zdravnik:" in njihove ženske oblike) je
  doslej ostalo neprepoznano, kadar je bil priimek hkrati navadna nemška
  beseda (npr. „Pacient: Bauer Thomas"). Zdaj se prepozna.
- Ime za oznako polja „Zobozdravnik" na lastni vrstici (npr.
  „Zobozdravnik", pod tem „Huber Franz") je doslej ostalo neprepoznano –
  niti osebno ime niti priimek. „Zobozdravnica" in preprosta oblika
  „zdravnik" s tem nista bili prizadeti. Zdaj se prepozna.
- Priimek za „Gospod"/„Gospa", ki mu je sledila uradniška fraza, kot je
  „v vednost", „v podpis" ali „v posredovanje", je bil doslej zajet
  preširoko in je frazo potegnil s seboj v najdbo imena – iz „Gospa Petra
  Klein za zastopanje v vseh zadevah" je bilo zamenjano „Petra Klein za
  zastopanje", preostanek stavka pa je ostal slovnično pohabljen. Prave
  plemiške predikate, kot sta „von der Leyen" ali „zu Guttenberg", to ne
  zadeva.
- Ista uradniška frazna preredakcija je tičala tudi za imenom v glavi
  e-pošte „To:", kodi dovoljenja (C.1/C.1.1/C.1.2), kodi vozniškega
  dovoljenja, oklepajnem polju obrazca („[Ime]: …") in nepikčasti
  pozdravni formuli – povsod tam je „za"/„od" & Co. potegnilo sledečo
  frazo, kot je „v podpis" ali „za zastopanje", v najdbo, deloma je
  ostal celo gol delec kot ostanek imena v rezultatu. Tudi tu prave
  plemiške predikate to ne zadeva.
- Matična številka za svojo oznako doslej sploh ni bila prepoznana –
  „Matična številka 7654321" je v celoti padla skozi prepoznavanje, niti
  kot identifikacijska številka niti prek jezikovnega modela, ker
  številka sama nosi neprepoznavno obliko.
- Enako je veljalo za udeleženčevo številko – „Udeleženčeva številka
  4471829" je v celoti padla skozi, niti kot identifikacijska številka
  niti prek jezikovnega modela.
- V življenjepisu je ime pod naslovom odseka „Osebni podatki" pogosto v
  celoti ali delno padlo skozi prepoznavanje, kadar je brez nagovora v
  obliki „priimek ime" stalo neposredno pod njim.
- Enako je veljalo za naslov odseka „Kontaktni podatki" – tam je ime celo
  v celoti padlo skozi, ne le delno.
- V prijavnem potrdilu ali seznamu vlog z združenim stolpcem „Priimek,
  ime" (zapis prijave prebivališča, vrednost npr. „Mustermann, Max" v
  celici) je ime v celoti padlo skozi prepoznavanje, kadar je sledil
  nadaljnji stolpec, kot je datum rojstva.
- Datum rojstva v na osebni izkaznici in prijavnem potrdilu običajni
  obliki „Datum/kraj rojstva: 22.07.1978 / Rostock" ni bil prepoznan –
  zadela je le oblika z vejico „Datum rojstva, kraj rojstva: …".
- „Storitve za občane" in „Pisarna za občane" sta bila občasno napačno
  zakrita kot kraj, zlasti za pomišljajem kot ločilom naštevanja (na
  primer „Obrnite se na storitve za občane – pisarno za občane …").
- Označena telefonska številka, ki jo je sredi vrstice ločil prelom
  vrstice (na primer iz ozkega stolpca glave dopisa ali izvleka besedila
  PDF ob širini stolpca: „Telefon: 0176 12\n34567"), je bila deloma
  zakrita le do polovice – ostanek za prelomom vrstice je ostal berljiv.
- Označena identifikacijska številka (kupčeva, članska, pogodbena
  številka in podobne), ki jo je sredi vrstice ločil prelom vrstice (na
  primer „Kupčeva številka: K903\n944" iz ozkega stolpca), je bila
  zakrita le do polovice – ostanek za prelomom vrstice je ostal berljiv.
- Ime z akademskim nazivom pred poklicnim poimenovanjem za vejico (na
  primer „Dipl.-Ing. Sabine Roth, vodja projekta") je ostalo povsem
  nezaščiteno – vrstica je izgledala kot glava stolpca tabele in je bila
  napačno zavržena kot stvarna vsebina.
- Naziv „Dr.-Ing." (pogost nemški inženirski naziv) pred imenom ni bil
  zajet v maskirano osebno vrednost in je ostal berljiv – ista past z
  vezajem kot pri „Dipl.-Ing.".
- Nazivi „Dipl.-Kfm.", „Dipl.-Kffr." in „Dipl.-Psych." (diplomirani
  ekonomist/-ka, diplomirani psiholog) pred imenom niso bili zajeti v
  maskirano osebno vrednost in so ostali berljivi – ista past z vezajem
  kot pri „Dipl.-Ing." in „Dr.-Ing.".
- Naslov MAC v zapisu Cisco s pikami namesto dvopičij (npr.
  „aabb.ccdd.eeff", kot ga izpisujejo dnevniki stikal in podporne
  vozovnice) sploh ni bil prepoznan in je ostal berljiv.
- Priimek za „Družina" (npr. „Družina Gruber podpiše pogodbo") je glede
  na stavčno zgradbo ostal neprepoznan in s tem berljiv – tudi s
  plemiškim predikatom pred njim („Družina von der Leyen").

- Pri hrvaškem naslovu brez ločila med poštno številko+krajem in
  ulico+hišno številko (npr. „10000 Zagreb Ulica Ivana Lučića 5") je
  hišna številka ostala neočiščena.

- Pri litovski kontaktni navedbi z oznako „Kontaktinis asmuo" (npr.
  „Kontaktinis asmuo: Vilkas Jonas") priimek ni bil prepoznan, kadar je
  bil hkrati navaden samostalnik (Vilkas = „volk", Vanagas = „kragulj").

- Država rojstva ali stalnega bivališča brez dodatne oznake v danskem
  polju obrazca (npr. „Fødeland: Tyskland" ali „Bopæl: Tyskland") ni bila
  prepoznana.

- Država rojstva ali stalnega bivališča brez dodatne oznake v romunskem
  polju obrazca (npr. „Țara: Germania" ali „Țara de reședință: Franța")
  ni bila prepoznana.

- Ime podjetja pod litovsko oznako polja „Darbdavys:" ali „Įmonės
  pavadinimas:" (delodajalec/podjetje) ni bilo prepoznano.

- Ime podjetja pod rusko oznako polja „Работодатель:" ali „Наименование
  организации:" (delodajalec/podjetje) ni bilo prepoznano.

- Izpisan datum z imenom meseca v romunščini (npr. „31 decembrie 2024")
  ni bil prepoznan.

- Madžarsko rojstno ime za kratico „szül." (npr. „Nagy Éva (szül.
  Kovács)") ni bilo prepoznano in je ostalo odprto berljivo.

- Shranjena profilna stran HTML (ali e-pošta s priloženo spletno stranjo)
  je lahko pustila civilno ime neočiščeno, kadar je stalo le v poljih
  profila Open Graph `profile:first_name`/`profile:last_name`/
  `profile:username` – ta ime nosijo razčlenjeno namesto opisno, kot
  `og:title`, in se zdaj čistijo prav tako.

- Sporočilo o nedostavljivosti (bounce/NDR) je pogosto nosilo glave
  prvotno nedostavljive pošte (pošiljatelj, prejemnik, zadeva) v lastnem,
  tretjem delu priloge – ta je v očiščeni različici ostal povsem
  nedotaknjen. Ta del se zdaj čisti enako kot preostalo poročilo o
  dostavi.

- Posamično imenovan urejevalec zaščitenega območja v Wordu (Omeji urejanje → Izjeme, `w:permStart`) je ostal v golem besedilu, tudi kadar je bilo isto ime v tekočem besedilu že zdavnaj očiščeno. Zdaj se odstrani prav tako.

## 0.10.42-alpha.20260827 – 27. avgust 2026

### Novo

- **Poimenovani profili prepoznavanja z enim prijemom omogočijo dostop do
  različnih delovnih primerov.** Pod *Nastavitve → Prepoznavanje → Kaj se
  odstrani* je mogoče trenutni izbor kategorij in vrst shraniti in ga prek
  izbirnega polja takoj znova uporabiti. Trdni profil *Standard* ustreza
  dosedanjemu dostavljenemu stanju in ga ni mogoče izbrisati. Profil
  spremeni izključno to, kar se odstrani; jezik, vrsta izhoda, globina
  prepoznavanja ter lastni izrazi in iskalni vzorci ostanejo nedotaknjeni.

- **Vrsta rezultata se zdaj izbere neposredno pred čiščenjem.** Skupno
  izbirno polje v glavnem oknu za celoten sveženj določi, ali Maskuro
  vstavi berljive ograde, zakrije ali odstrani brez nadomestila. Dve
  ločeni polji za PDF in pisarniške datoteke v oknu nastavitev sta
  odpadli; s tem je pomembna odločitev vidna in se pri mešanih svežnjih ne
  more več nehote razhajati. Vodeni rundgang razloži novo izbiro pred
  prvim čiščenjem.

- **Teme in vodni žigi na željo jasno označijo dokončane PDF-je.** Dvanajst
  celostnih videzov medsebojno uskladi nadomestna besedila in zakrivne
  površine; na novo sta med njimi Pride ter pomlad, poletje, jesen in
  zima. *Tajni spis* neposredno prinese diagonalni `TOP SECRET`. Neodvisno
  od tega je mogoče izbrati prosto besedilo oznake ali lastno sliko, ikono
  oziroma SVG z barvo in prekrivnostjo. Uvožene grafike se vdelajo brez
  svojih metapodatkov in ostanejo na voljo, tudi če se izvorna datoteka
  premakne. Pri dodelovanju Maskuro zamenja svoj dosedanji vodni žig,
  namesto da bi ga večkrat postavil enega čez drugega.
  Besedilni vodni žigi se izrišejo kot zadnja plast PDF-ja s svetlim
  obrisom, da ostanejo vidni tudi na temnih slikah in gostem besedilu.
  Urejevalnik Popravi vodni žig Maskura v celoti prezre in njegovega
  besedila ne ponuja več kot kandidata za zakritje.

- **Lastne izhodne teme je mogoče shraniti in deliti.** Trenutna mešanica
  nadomestnega besedila, zakritja in vodnega žiga dobi ime, ostane v
  nastavitvah in jo je mogoče izvoziti ali uvoziti kot JSON brez golega
  besedila. Črno-beli tiskovni predogled opozori na šibke kontraste;
  neobvezni uspešni konfeti ostaja izključno v vmesniku.

- **Zadnji preizkus izvoza in pojasnjevalna preverjevalna prevleka
  zaključita krog prikaza.** Pred dokončnim shranjevanjem Maskuro vsako
  natančno znano mesto PDF-ja še enkrat primerja v besedilni plasti in
  izrisanih slikovnih točkah; opozorila navajajo izključno stran in
  koordinate. V urejevalniku *Zakaj je to prekrito?* pokaže kategorijo,
  pot prepoznavanja in varnostni rob, nikoli odstranjenega golega besedila
  in nikoli v končnem dokumentu.

- **Zakrivne proge so zdaj lahko lepe.** Pod *Nastavitve → Videz* so na
  voljo barvne privzete vrednosti, prosti izbirniki barv, prelivi,
  mavrica, črte, pike, cvetlice, zvezde, srca, tačke, oblaki, strele,
  kavna zrna, race, sonca, listi, snežinke, papirnati, označevalni,
  lepilno-trakasti in ponovljivi naključni vzorci skupaj z neposrednim
  predogledom. Nadomestna besedila po izbiri dobijo barvo, preliv,
  mavrico, tabletko ali oznako. Barve kategorij razlikujejo imena,
  naslove, stike in medicinske navedbe. PDF prevzame celotno oblikovanje;
  Word, PowerPoint, OpenDocument in HTML uporabljajo izbrano prekrivno
  osnovno barvo. Zaščita se pri tem ne spremeni: Maskuro najprej odstrani
  zaupno vsebino in barvo ali vzorec nariše šele na prazno mesto.

- **Maskuro je spet na voljo za Linux – kot AppImage, DEB, RPM in
  prenosljiv arhiv.** DEB in RPM v sistem vpišeta vnos programa,
  dodelitve datotek, ukaz terminala in ikono; AppImage teče brez
  namestitve. Posodobitve pri obstoječi namestitvi DEB ali RPM ostajajo v
  istem paketnem formatu, sicer pa dajejo prednost AppImage.

- **Vidno preverjanje navadnega besedila PDF ne predlaga več drugič kot
  nove najdbe.** Sklepni pogled OCR in varna obnova vidnih strani ostajata
  v celoti dejavna; kot nov vir najdb v privzetem stanju veljajo le
  območja, ki jih preverjanje besedila strani in posamezne slike še nista
  prebrali. S tem se vrstice izdelkov ne spremenijo v nova imena ali
  podjetja le zaradi drugačnega drugega branja OCR. Kdor še vedno želi
  dve neodvisni presoji celotnega vidnega besedila, v nastavitvah vklopi
  *Celotno vidno stran PDF še enkrat preveriti glede navedb*.

- **PDF-je si je mogoče ogledati zvezno, po listih ali kot dvostran.** Tri
  kompaktne ikone pogleda stojijo spodaj neposredno ob „Širina" in
  „Stran". Zvezno se ob robu lista zvija na naslednjo stran; posamezna
  stran drži kolešček miške na trenutnem listu; dvostran pokaže polo,
  naredi kliknjen list urejljiv in premika naprej/nazaj za celo polo.
  Sličice strani in primerjalna lupa se poleg tega odpreta v znatno ožjem
  levem osnovnem stolpcu in delovni strani pustita več prostora.

- **Zdaj vidite, kaj je storila stopnja UI.** Po vsakem zagonu pod
  „Podrobnosti" za vsako datoteko stoji vrstica o tem – „Stopnja UI: 12
  mejnih primerov preverjenih, 3 zavrnjeni" –, in če ni našla ničesar za
  spremeniti, stoji tudi to. Doslej je najdražja stopnja povsem molčala:
  ali je bila sploh vprašana, od zunaj ni bilo mogoče videti.

  Kdor potrebuje več podrobnosti, pod „Nastavitve → UI" vklopi *Vsako
  vprašanje UI zabeležiti v dnevnik*. Nato dnevniška datoteka za vsako
  vprašanje beleži velikost, trajanje in število ugotovitev, poleg tega pa
  čakalni čas zaradi omejitve količine na strani gostitelja. Gumb „Pokaži
  dnevniško datoteko" zraven odpre mapo – ta leži v mapi podatkov programa,
  ki je pod Windows skrita in je sam od sebe ne najde nihče. V datoteki
  stojijo izključno velikosti, nikoli besedilo iz vaših dokumentov.

- **Maskuro prepozna, kadar vaša storitev UI omeji število zahtev.**
  Gostovane storitve pogosto dovolijo le malo zahtev na minuto – štiri ni
  redkost. Presežne se ne zavrnejo, temveč morajo počakati, in iz dveh
  sekund na odgovor postane štirideset. To je doslej izgledalo, kot da je
  model počasen. Zdaj Maskuro mejo prebere iz odgovora storitve, ne pošlje
  več vprašanj hkrati, kot jih storitev sprejme, mejo navede pod
  „Preveri povezavo" in jo vračuna v oceno trajanja.

- **Pogled strani uporablja vaš Word, Excel in PowerPoint – in je pri tem
  približno šestkrat hitrejši.** Doslej je potreboval LibreOffice, ki ga
  ima le malo pisarniških računalnikov; kdor ga ni imel, je videl gumb, ki
  je zahteval tujo namestitev. Zdaj velja: če je nameščen Microsoft
  Office, se uporabi sam od sebe – brez nastavljanja, brez prenosa, ne da
  bi kaj obkljukali. LibreOffice ostaja druga pot in pri datotekah
  OpenDocument celo prva; če eden odpove, se poskusi drugi.

  Razlika se najbolj pozna pri delu: po vsaki zamenjavi se stran znova
  postavi, kar prek Officea stane približno pol sekunde namesto tri.
  Prvi pogled na dokument še vedno traja nekaj sekund, nato pa sledi
  vašim korakom brez čakanja.

  Vaš lasten odprt Word pri tem ni prizadet: Maskuro zažene lastno,
  nevidno sejo, datoteko odpre le za branje, izklopi makre in vse znova
  konča, takoj ko se okno Popravi zapre. Datoteke, zaščitene z geslom, se
  zavrnejo, namesto da bi obviselo v nevidnem pogovornem oknu.

- **Prva nastavitev zdaj vpraša tudi po obrazih, kodah in podpisih – in
  vse manjkajoče naloži v enem koraku.** Poleg razširjenega prepoznavanja
  na prvi strani stojijo tri stikala za slike: naredi območja obraza
  neprepoznavna, naredi črtne in QR kode neprepoznavne, zakrij ročno
  napisane podpise na straneh PDF. Meja PDF stoji vidno ob kljukici;
  pisarniške datoteke se samodejno ne preiskujejo po podpisih. Pod
  kljukicami piše, koliko megabajtov stane klik na „Naprej". Naloži se
  nato v **enem** oknu z **eno** vrstico napredka za vse skupaj, namesto v
  več zaporednih pogovornih oknih; prekinitev konča celoten postopek in ne
  pusti ničesar polovičnega. Kdor tega noče, odstrani kljukice – potem se
  tudi nič ne naloži.

- **Predogled je mogoče stanjšati po potrebi preverjanja in strniti po
  vrsti.** Nad seznamom stoji drsnik *Skrij dobro podprte*: bolj ko je
  postavljen v desno, bolj skrije od zelene proti rdeči; skrajno desno
  ostane le tisto, kar je program ugotovil povsem sam. Klik na naslov
  vrste jo strne. Oboje je bralni pripomoček, ne izbor – kar je skrito ali
  strnjeno, ostaja odkljukano in se zamenja; koliko vrednosti je trenutno
  prikazanih od koliko, piše pod drsnikom. Pri kratkih seznamih se drsnik
  ne prikaže. Preklop na dva stolpca zdaj ohranja tudi stikala *nikoli
  več*.

- **Seznam slik se lahko pred vsakim zagonom odpre sam.** Kdor želi o
  vsaki sliki odločati posebej, pod „Slike" nastavi novo kljukico
  *Pred vsakim zagonom določiti posamično*. Seznam s predogledom se nato
  pri čiščenju odpre sam, namesto da bi vsakič sami kliknili „Določi
  posamično …"; če ga prekinete, se tudi ne očisti. Če nobena od izbranih
  datotek ne vsebuje slike, se ne pojavi nič. Privzeto je kljukica
  izklopljena.
- **Maskuro na straneh PDF najde ročno napisane podpise in jih odstrani iz
  slikovnih točk.** Doslej je podpis pod očiščenim dokumentom ostal –
  optično prepoznavanje bere tiskano pisavo, in kar ne prebere, se ne
  zamenja. Iskanje je lastno stikalo in potrebuje prepoznavalni model, ki
  se naloži enkrat naknadno.

  Izmerjeno najde približno 84 od 100 podpisov in jih pokrije približno
  štiri petine. To je pomoč in ne zagotovilo: po vsakem zagonu poročilo
  navede, koliko jih je bilo najdenih – tudi kadar ni bilo nobenega, ker
  to lahko pomeni, da ga ni ali da je bil spregledan. Na 72 pravih
  poslovnih straneh brez podpisa si ga ni izmislil.

  **Narisan** podpis se najde, a ne odstrani: sestoji iz črt, ne iz
  slikovnih točk, in proga čeznjo bi bila le prekritje, pod katerim bi
  črte ostale. Taka mesta se preštejejo in navedejo, da jih je mogoče v
  oknu Popravi zakriti ročno.

  Datoteke Word, Excel, PowerPoint in OpenDocument se samodejno ne
  preiskujejo po podpisih. Vmesnik, prva nastavitev, prenos modela,
  ukazna vrstica in priročnik zdaj to mejo izrecno navajajo.

- **Rundgang zdaj vodi tudi skozi predogled – okno, v katerem
  odločate.** Pri vadbenem dokumentu se odpre sam, tudi če ste predogled
  sicer izklopili (vaša nastavitev ostane, kot je). Pojasnjeno je, kaj
  pomenijo barve, zakaj v vsaki vrstici stoji le eno vprašanje – ali tu
  sploh gre za osebo? – in čemu služi „nikoli več". Pri barvah je
  poudarek na dobro podprti vrstici, večinoma IBAN – zelenem primeru, ki
  ga navaja stavek; nato na najšibkeje podprti, kjer lahko sredi razlage
  kliknete sami: kljukica stran, vrednost ostane v dokumentu. Pri dolgem
  seznamu se okno za vodenje odpre večje, da razlaga ne leži na vrsticah.
  Če se okno odpre drugič, rundgang pove tudi zakaj – dokončana stran se
  še enkrat prebere kot slika, pri čemer nastanejo drobci, ki izgledajo
  kot ime.

- **Urejevalnik se prvič odpre velik.** Izvirnik, rezultat, orodna vrstica
  in seznam najdb stojijo drug ob drugem in so imeli v dosedanji osnovni
  velikosti premalo prostora. Kdor okno pomanjša, dobi svojo velikost
  naslednjič nazaj – nikomur se ne vsiljuje.

- **Dvoklik na ogrado jo obnovi** – v Wordu, Excelu, PowerPointu,
  OpenDocumentu, besedilu, e-pošti in HTML-ju. In kdor povleče čez več
  ograd in izbere „Povrni izbor", obnovi vse, ki so v njem, naenkrat.
  Oglatega oklepaja torej ni več treba natančno zadeti. Ograde, ki pri
  anonimiziranju stojijo za več različnih vrednosti, so pri tem izvzete –
  preštejejo se in navedejo, ne uganjujejo.

- **Priročnik ima poglavje „Predogled pred zamenjavo".** Okno je privzeto
  vklopljeno in je edino, v katerem odločate – v priročniku je bilo
  doslej omenjeno le mimogrede. Zdaj tam piše, kaj pomeni kljukica (velja
  za **vsako** najdbo, ne le navedeno), zakaj je v vsaki vrstici treba
  odgovoriti le na eno vprašanje, kaj trajno povzroči „nikoli več" in
  zakaj se okno pri PDF-ju lahko odpre drugič. V vseh osemnajstih jezikih,
  in na seznamu nastavitev je stikalo zdaj prav tako navedeno.

### Spremenjeno

- **Predal „Zamenjane vrednosti" ima drsnik nad barvami, način učenja pa
  tam ne stoji več.** Pri več kot osmih vrednostih nad seznamom stoji isti
  drsnik kot v oknu predogleda: *Skrij dobro podprte* stanjša prikaz na
  tisto, kar je resnično treba preveriti. Na dokumentu se pri tem ne
  spremeni nič, koliko vrstic od koliko je prikazanih, pa piše spodaj –
  iskalno polje in drsnik štejeta skupaj. Kljukica *Način učenja* je
  izginila iz predala; ostaja v meniju *Orodja* in v orodni vrstici.

- **Predal „Zamenjane vrednosti" zdaj kaže iste barve kot dokument.** Vsaka
  vrstica v njem je podložena enako kot mesto v dokumentu in kot vrednost
  v predogledu: rdeča pomeni „samo uganjeno, tu se najprej splača drugi
  pogled", zelena „prepoznano po poimenovanem vzorcu". Znotraj vsake vrste
  stoji najbolj negotovo zgoraj – seznam torej obdelate od zgoraj navzdol
  in ste najprej videli najpomembnejše. Doslej je vse stalo enako svetlo
  in razvrščeno po abecedi.

- **Način učenja je tovarniško izklopljen.** Po popravku v oknu Popravi je
  program doslej sam vprašal, ali naj iz tega nastane lastno pravilo. To
  vprašanje pride sredi dela; kdor ga ni naročil, ga doživlja kot
  prekinitev. Kdor pravila želi, v orodni vrstici vklopi gumb *Način
  učenja* – izbira nato trajno velja, v obe smeri.

### Odpravljeno

- **Izvožene datoteke pravil so zdaj izrecno označene kot vredne
  zaščite.** Lastni izrazi in izjeme so lahko v njej v golem besedilu;
  poleg tega lahko datoteka vsebuje sol za razprševanje, s katero je
  mogoče potrditi domnevne vrednosti. Uspešen izvoz zato pokaže
  opozorilo in poziva k zaščiti datoteke ter njenemu zavestnemu
  posredovanju le pooblaščenim prejemnikom.

- **Zadnje varnostno preverjanje ne zadrži več očiščenih pisarniških
  datotek zaradi njihovih lastnih ograd.** Kratica vrste, kot je „SVNR",
  stoji tudi v `[SVNR1]`; doslej je to veljalo za domneven ostanek golega
  besedila in dokončana datoteka je bila zavržena. Hkrati se telefonske
  številke in IBAN-i zdaj dodatno preverijo tudi tam, kjer pisarniški
  program isto navedbo brez vidnih presledkov shrani v sklicu ali vdelani
  datoteki.

- **Word, Excel, PowerPoint in OpenDocument ne puščajo več pozno odkrite
  kopije polja.** Če se vrednost prvič prepozna v stranski ali vdelani
  pisarniški datoteki, ozek naknadni tek pospravi tudi prej prebrane
  vidne in skrite kopije. Že ustvarjene ograde sklicev se pri tem ne
  zamenjajo znova.

- **Pri posamičnem obnavljanju spustnega seznama Word ne pride več
  nevprašano zraven sosednja izbira.** Popoln izvirni odstavek se prevzame
  šele, ko tudi njegovi atributi ne vsebujejo več odprtih ograd.

- **Slabo berljivi skeni izgubijo manj povezanih navedb.** Alternativno
  branje OCR z nagovorom in dvodelnim imenom ostane ohranjeno; delec
  ulice, hišna številka in poštna številka s krajem skupaj ščitijo celo
  vrstico naslova, tudi če razpade v sosednje bloke OCR. Polja računa in
  artikla ter vrstice prireditev zraven se pri tem ne zajamejo. Za
  „rojen(a)" v več besed OCR in ločila razpadli veljaven datum se prav
  tako v celoti naredi neprepoznaven.

- **Uspešni konfeti je zdaj viden ob samodejnem odpiranju urejevalnika.**
  Koščki brizgajo neposredno iz gumba *Očisti* namesto da bi deževali z
  zgornjega roba okna. Urejevalnik počaka le na prvi, 850 milisekund
  kratek brizg in se nato samodejno odpre; brez vklopljenega konfetija
  zamude še naprej ni.

- **Števec strani in vrstica približevanja ne poskakujeta več pri
  prehodu čez ikone pogleda.** Qt je prerazdelil prosti prostor vrstice
  stanja, takoj ko se je tam pojavil namig simbola. Obe skupini upravljanja
  zdaj ob prehodu obdržita svojo naravno širino in trdni položaj.

- **Meritev hitrosti priklopljenega strežnika UI je vedno spodletela** – na
  vsakem strežniku, odkar obstaja lastno UI. Vprašala je z ozko mejo
  odgovora in nato poskušala prebrati s tem odrezan odgovor; to je moralo
  spodleteti, shranjeno pa je bilo „ni izmerjeno". Posledice so bile vidne
  povsod: ocena trajanja je vaš strežnik računala s hitrostjo priloženega
  modela na pisarniškem računalniku, v nastavitvah pa je trajno pisalo, da
  hitrost še ni izmerjena. Zdaj se meri po količini, ki jo je strežnik
  ustvaril, ne po vsebini njegovega odgovora.

- **„Največje prepoznavanje (UI) – počasno" je pisalo tudi, kadar ni
  držalo.** Oznaka in namig sta opisovala priloženi model na pisarniškem
  računalniku – „jezikovni model na tem računalniku", „pri velikih
  dokumentih do ene ure". Kdor je priklopil lasten strežnik UI, je tam
  bral dvoje napačnega: računa se ne na njegovem računalniku, odgovor pa
  pride v sekundah namesto urah. Oboje zdaj izhaja iz meritve. Če je ni,
  aplikacija ne trdi več ničesar, temveč pove, da meritev še ni bila
  opravljena.

- **Obnavljanje zdaj deluje tudi na povlečen izbor.** Kdor je povlekel čez
  več ograd in hotel pritisniti *Povrni izbor*, je gumb našel sivega:
  vklopil se je le, če je bila oznaka **natanko** ena ograda – čez odstavek
  povlečena to ni nikoli. Pot za tem je že obstajala, le nihče ni prišel
  do nje. Zdaj zadošča, da označite območje; vse ograde v njem se vrnejo v
  enem koraku.

- **Obnavljanje se je sesulo, če je bila odprta primerjalna lupa.** Lupa si
  zapomni mesto pod kazalcem miške, da lahko sledi izvirniku. Ob ponovnem
  nalaganju po preklicu je to mesto vrnila v obliki, s katero besedilni
  pogled ni znal ničesar začeti – in ker taka napaka sredi vmesnika konča
  program, je iz preklica nastal sesutje. Lupa je v osnovnem stanju
  odprta, torej je to zadelo običajno pot.

- **Po obnavljanju pogled ne skoči več na začetek dokumenta.** V daljšem
  dopisu je bilo po vsakem koraku izgubljeno mesto, na katerem ste ravno
  delali. Zdaj ostane zgoraj tisti odstavek, ki je bil zgoraj že prej.

- **Brez LibreOffice pogled strani pove, od kod prihaja, namesto da bi le
  manjkal.** Gumba *Pogled strani* in *Počrni kot PDF* sta bila zaklenjena
  in v namigu navedla le, da LibreOffice ni bil najden; poti do njega
  nikjer v aplikaciji ni bilo. Klik zdaj odpre opozorilo s potjo do
  brezplačnega, odprtokodnega LibreOffice. Priročnik in pogosta vprašanja
  so na tem mestu navajali napačno – napovedovali so gradnik za naknadno
  nalaganje, ki ga aplikacija ne ponuja.

- **Pred izročitvijo se dokončana datoteka zadnjič v celoti preišče –
  zdaj tudi pri Wordu, Excelu, PowerPointu, LibreOfficeu, e-pošti, HTML-ju
  in besedilu.** Doslej je imel ta zadnji pogled le PDF. Vse dosedanje
  preverbe pregledajo mesto, ki ga je prej nekdo poimenoval; odlagališče,
  na katerega ni nihče pomislil, zato ne preveri nihče. Na koncu se zdaj
  topo preišče vse, kar je bilo zamenjano – v vsakem delu paketa. Če kaj
  ostane, ne nastane **noben** rezultat, sporočilo pa navede vrednost.
  Datoteka, ki velja za očiščeno, je hujša kot nobena.

- **Imena v `<script>` in `<style>` se zdaj sporočijo.** Oba ostajata še
  naprej nedotaknjena – tam stoji programska koda, in zamenjava sredi
  oznake iz spletne strani naredi pokvarjeno spletno stran. Doslej pa to
  ni bilo povedano, in to je bila napaka: slogovno pravilo `content:
  "Anna Vzorčnaženska"` je prejemniku **vidno** na zaslonu, in v rezultatu je
  še naprej stalo tam, medtem ko je program stran javil kot očiščeno.

- **V nastavitvah je dodatne modele spet mogoče naložiti in odstraniti.**
  Gumb ob „Razširjeno prepoznavanje" in „Največje prepoznavanje (UI)" se je
  ob pritisku končal v oknu poročila o napaki, namesto da bi prinesel
  model. Druga pot – kljukica pri prepoznavanju, ki sama od sebe vpraša po
  modelu – s tem nikoli ni bila prizadeta.

- **Imena, skrita v imenih listov in obsegov preglednice, se zdaj
  sporočijo.** Ime lista stoji na zavihku spodaj, ime poimenovanega obsega
  v polju imena in v vsaki formuli, ki ga uporablja. Nobeno od obeh se še
  vedno ne zamenja – formule se sklicujejo prek njiju, in delovni zvezek s
  napakami sklicev ne pomaga nikomur –, a zdaj to tam piše. Doslej je
  sporočilo prišlo le za ime lista datoteke Excel: poimenovan obseg
  „Bezuege_Brunnthaler" je šel ven tiho, pri preglednici LibreOffice pa je
  program molčal povsem. List „Notizen Ortner" je zato veljal za očiščen,
  in prvi pogled prejemnika je padel na ime.

  Sporoči se pri tem le tisto, kar resnično vodi do osebe: beseda, ki je v
  isti mapi tako ali tako bila zamenjana, ali najdba, ki iz več besed
  izbere eno. Samostojna beseda, kot je „Zustaendig" ali „Bezug_Umsatz", ne
  sproži več opozorila – prej bi ga, in opozorilo, ki pride pri vsakem
  drugem delovnem zvezku, po tretjič ne prebere nihče več.

- **„Obnovi izvirnik" zdaj resnično obnovi vse.** V nekaterih dokumentih so
  potem manjkali posamezni znaki – iz „Seestraße 14" je nastalo „Seestraße
  4", iz „An:" „An", iz „nordlicht-planung" „nordlicht planung" –, in
  posamezne vrstice se sploh niso vrnile. Prav tam nato ni bilo mogoče
  ničesar več izbrati z miško ali zakriti: besedilo je sicer stalo na
  papirju, a program ga ni več poznal. Prizadeti so bili ozki znaki –
  enica, dvopičje, vezaj – v dokumentih, ki vsak znak postavijo posebej;
  vadbeni dokument je eden od njih.

- **In isti dokumenti se pri čiščenju ne spremenijo več v sliko.** Ker je
  tak znak ostal, je naknadno preverjanje javilo ostanek in stran je bila
  previdnostno rastrirana. Besedilo na njej je bilo nato le še odslikava:
  ni več iskano, ni več označljivo, večje v datoteki. Vadbeni dokument
  zdaj ostaja na obeh straneh pravo besedilo.

- **Barvne oznake ne ostanejo več nad obnovljenim besedilom.** Kdor je
  zamenjavo preklical, je barvni pravokotnik še naprej videl nad
  obnovljeno besedo – trdil je „tu je bilo nekaj odstranjeno", čeprav je
  tam spet stal izvirnik.

- **Proga ne izda več, kako dolga je bila beseda pod njo.** Pri zakrivanju
  proga v kratkih vrsticah zdaj pokrije **celo** vrstico – blok naslova,
  glavne podatke, ozko celico tabele. Če cela vrstica ne pride vmes
  (navadna vrstica tabele s tremi stolpci), ostane pri polju; v vrstici
  tekočega besedila ostane natančno na besedi, sicer bi ime sredi stavka
  počrnilo cel stavek. In proge, ki stojijo druga pod drugo, postanejo
  **enako dolge**: v bloku naslova stoji v vsaki vrstici vrednost, in tri
  različno dolge proge so še naprej izdajale, kako dolge so bile vrstice.
  Zrastejo pri tem le toliko, kolikor je papir prost – pred sosednjim
  stolpcem proga preneha.

- **„Cela vrstica" zdaj resnično zakrije celo vrstico.** Doslej se je proga
  končala pri naslednji večji vrzeli – torej na koncu polja. V tekočem
  besedilu to ni padlo v oči, tam je polje vrstica; v glavnih podatkih in
  tabelah pa je: iz „Ime: Anna Vzorčnaženska   Oddelek: Prodaja" je
  nastala proga, ki se je končala natanko pri zadnji črki imena – s tem je
  njegova dolžina spet stala na listu. Proga zdaj teče od prve do zadnje
  besede vrstice in zajame sosednje stolpce. Kdor želi zadeti le vrednost,
  izbere „Besede"; samodejni način še naprej zakriva po poljih.

- **Pred izročitvijo se dokončana datoteka zadnjič preišče.** Vse dosedanje
  preverbe pregledajo mesto, ki ga je prej nekdo poimenoval – besedilo
  strani, pravokotnik najdbe, slikovno površino. PDF pa ima več
  odlagališč, kot jih zajame naštevanje: opombe, vrednosti obrazcev,
  zaznamki, informacije o dokumentu, priloge datotek, JavaScript. Na koncu
  Maskuro zato topo preišče zapisano datoteko po vsem, kar je zamenjal –
  povsod razen v besedilu strani, kjer isto besedilo sme dovoljeno stati.
  Če tam kaj ostane, ne nastane **noben** rezultat, sporočilo pa navede
  vrednost. Dokument, ki velja za očiščenega, je hujši kot nobenega.

- **Kar ni bilo mogoče preveriti, ne velja več za preverjeno.** Na treh
  poteh je doslej neuspeh naknadnega preverjanja izgledal kot čist
  rezultat. Stran, katere besedilne plasti ni bilo mogoče prebrati, je
  veljala za posebej čisto – tam ni bilo česa najti; zdaj se rastrira.
  Če strani z ostalo najdbo ni bilo mogoče nadomestno rastrirati, je bila
  tiho izročena; zdaj se čiščenje raje prekine. In protipreizkušnja v oknu
  Popravi je po lastni napaki javila „nič ostalo" – v oknu tega ni bilo
  mogoče ločiti od tega, da je bilo vse odstranjeno; zdaj se prikaže
  opozorilo skupaj z gumbom „Rastriraj stran".

- **„Ponastavi na privzeto" večine nastavitev sploh ni ponastavilo.**
  Devet od dvaindvajsetih kljukic je po tem koraku ostalo nespremenjenih –
  med njimi predogled, „Nato odpri očiščene datoteke", okno Popravi,
  takojšnje odlaganje in obe kljukici posodobitve. Shranjena datoteka je
  bila sicer izpraznjena, a okno je držalo stare vrednosti in jih ob
  naslednjem kliku znova vpisalo. Zdaj se vrne vsaka kljukica, in oznaka
  „spremenjeno" izgine z njo.
- **„Poročilo o preverjanju samodejno odložiti po vsakem čiščenju" je
  kazalo vklopljeno, a je bilo izklopljeno.** Po ponastavitvi je kljukica
  ostala nastavljena, medtem ko je bila vrednost izbrisana – poročilo ni
  več nastalo, ne da bi kaj na to opozorilo. Enako je veljalo za dnevnik
  preverjanja in lasten posnetek zaslona; njuna tipkovna bližnjica se ob
  ponastavitvi zdaj takoj tudi pravilno vklopi ali izklopi.

- **Proge v isti vrstici zdaj izgledajo enako.** Doslej je vsaka najdba
  prinesla svojo progo, njena višina pa je izhajala iz pisave zadete
  besede. V vrstici z oznako in vrednostjo v različnih velikostih sta
  zato drug ob drugem stali debela in tanka črta z zamaknjenimi robovi, in
  kjer je dve najdbi ločil le presledek, je nad njima ostala svetla
  vrzel. Proge iste vrstice imajo zdaj isti zgornji in spodnji rob, in kar
  ločuje le presledek, postane ena proga. Kar naj ostane med dvema
  najdbama – vejica za imenom, oznaka, znesek – ju še naprej loči. Velja
  za postavljene strani kot za skene.

- **Zavihki pod „O tem programu" se spet začnejo zgoraj.** Varstvo
  podatkov, licenčni pogoji in licenčna obvestila so se odprla sredi
  besedila – kdor jih je bral, je moral najprej odrolati povsem na vrh, da
  je videl prvo vrstico.

- **Pisalo ne odpre več drugega okna urejevalnika, temveč obstoječega
  potegne naprej.** Doslej je ob vsakem kliku nastalo novo. Okno nima
  lastnega vnosa v opravilni vrstici – kdor ga je pomanjšal, ni več
  prišel do njega in je kliknil še enkrat; pri obnovitvi glavnega okna so
  potem vsa nabrana okna prišla naprej hkrati. Zdaj nadaljnji dokumenti
  pristanejo v zavihkovni vrstici odprtega okna, dokument, ki tam že
  stoji, pa ne dobi drugega zavihka.

- **„Razširjeno prepoznavanje" ne nosi več oznake „spremenjeno", dokler
  njegov model manjka.** Dostavljeno je vklopljeno, brez naknadno
  naložljivega modela pa to sploh ne more biti – v nastavitvah je zato
  vrstica na vsakem sveže nastavljenem računalniku veljala za spremenjeno,
  čeprav se je ni dotaknil nihče. Zakaj je kljukica izklopljena, zdaj pove
  že sama oznaka: „Model še ni naložen".

- **Uvodni trak je v pisarniških in besedilnih datotekah razlagal platno
  PDF.** Tam je pisalo „klik na besedo jo zakrije" – v datoteki Word klik
  pa ne zakrije ničesar, tam se označi in nato pritisne gumb. Zdaj pove,
  kaj velja v posameznem pogledu.
- **Orodna vrstica je bila v besedilnem pogledu natrpana z oznakami.**
  „Zamenjaj izbor", „Zatemni izbor", „Povrni izbor", „Predogled strani" in
  „Počrni kot PDF" zdaj stojijo kot simbol – kot njihovi sorodniki v
  PDF-ju. Njihova imena ostajajo v kratki pomoči in meniju.
- **Ctrl+kolešček miške v primerjalni lupi ni premikal njenega drsnika
  povečave.** Pisava je postala večja, drsnik in odstotek zraven pa sta
  še naprej trdila staro stanje.
- **Namestitveni program posodobitve ni prišel v ospredje** – najprej ga
  je bilo treba klikniti v opravilni vrstici (le Windows).
- **Letnica na začetku vrstice je veljala za avstrijsko poštno
  številko.** V življenjepisu je iz „2020 Prodajne strategije" nastala
  ograda – cela vrstica je izginila. Štirimestna številka med 1900 in
  2099 zdaj potrebuje drug znak naslova: ulico nad njo, besedo polja
  pred njo, državno oznako ali znano ime kraja. Bloki naslova to imajo;
  stolpci letnic ne.
- **Par mesec-leto je veljal za telefonsko številko.** Iz „Od 08.2010
  123-Prodano d.o.o." je nastala „telefonska številka" – mesec, leto in
  prve številke imena podjetja za tem.
- **Poročilo je govorilo „preverjeno z optičnim prepoznavanjem besedila"
  in zamolčalo, česa ne prebere.** Če slike ostanejo, zdaj piše, da
  ročno napisanega v njih ne najde – podpis ali ročno vpisano ime ostane.
  Doslej je ta stavek stal le pri skeniranih straneh; navaden PDF z
  vdelanim podpisom ni dobil niti besede o tem.
- **Ograda na zakritem slikovnem ozadju je stala na levem robu svoje
  proge.** Kadar se vrednost najde na sliki – na primer natipkano ime ob
  skeniranem podpisu –, je treba slikovno območje zakriti v polni širini.
  Krajša ograda je poleg puščala golo črnino, kar je izgledalo kot dva
  postopka. Zdaj stoji na sredini proge.

## 0.10.41-alpha.20260826 – 26. avgust 2026

### Novo

- **Po preizkusnem obdobju okno enkrat na zagon spomni na licenco.** Prikaže
  se pet minut po zagonu – ne takoj, da nikomur ne stoji na poti pred prvim
  korakom – in počaka, dokler traja čiščenje. Od tam vodi pot do nakupa in
  ena do vnosa že kupljenega ključa; „Pozneje" ga zapre, takoj ko petih
  sekund v gumbu poteče. Nič se ne zaklene: brezplačna stopnja dela naprej
  kot doslej.

- **Čakalni čas pred zagonom v brezplačni stopnji zdaj traja deset namesto
  trideset sekund.** Namenjen je opominjanju na licenco, ne ustavljanju
  dela.

- **Vsa tri opozorila o licenci zdaj izgledajo enako.** Čakalni čas, opomin
  v zadnjih preizkusnih dneh in opozorilo po preizkusnem obdobju nosijo isti
  trak, isto zgradbo in iste gumbe; preostali čas zdaj stoji v gumbu namesto
  kot velika številka zraven.

- **Seznam najdb v predogledu spet stoji drug pod drugim.** Od devetih
  vrednosti naprej je bil dvostolpčen; pri pregledovanju oko med tem skače
  med dvema stezama, odloča pa se tu vrstico za vrstico. Kdor ima raje dva
  stolpca, ju spodaj levo v oknu spet vklopi – izbira ostane shranjena, pri
  preklopu pa že odizbrane vrednosti ostanejo odizbrane.

- **Stopnja UI je zdaj odprta vsakomur, ki priklopi lasten strežnik UI.**
  „Nastavitve → UI" nosi vse za to: povezavo, kaj sme UI storiti, kaj dobi za
  početi – in nad tem stikalo za stopnjo skupaj s protipreizkušnjo, takoj ko
  je vnesen strežnik. Jezikovni model, ki računa na lastnem delovnem mestu,
  ostaja zadržan: za deset strani potrebuje več minut in zato ni za vsakdanjo
  rabo.

- **Lastno UI je mogoče priklopiti.** Namesto priloženega jezikovnega
  modela lahko odgovarja večji model na drugem računalniku – na strežniku v
  hiši ali delovni postaji z močno grafično kartico. Zahtevana je storitev z
  vmesnikom, združljivim z OpenAI (Ollama, LM Studio, llama.cpp-server, vLLM,
  LocalAI); nastavi se pod „Nastavitve → Lastno UI" skupaj s preverjanjem
  povezave, ki model resnično povpraša, izmeri hitrost in ugotovi možno
  obliko odgovora. Več besedilnih odsekov pri tem teče hkrati namesto
  zaporedno.

- **Kaj sme UI storiti in kaj dobi za početi, je zdaj nastavljivo.** Tri
  stikala odločajo o preverjanju mejnih primerov, samostojnem iskanju in
  iskanju v tekočem besedilu; navodilo modelu stoji tam dobesedno, dopolniti
  ga je mogoče z lastnimi izrazi hiše in ga z enim gumbom ponastaviti na
  privzeto.

- **Če besedilo pri tem zapusti lastno omrežje, se pred vsakim zagonom
  opozori.** Maskuro po naslovu prepozna, ali strežnik UI stoji v hiši, in
  znanega ponudnika imenuje po imenu. Opozorilo je mogoče izklopiti, a le z
  izrecno potrditvijo, da ste za ta prenos pooblaščeni, in le za natanko ta
  naslov. Na samem postopku se s tem ne spremeni nič: prenos še naprej stoji
  v dnevniku in v poročilu o preverjanju vsake datoteke. V ukazni vrstici se
  ne vpraša, temveč ustavi – tam je potreben `--ki-auswaerts-erlauben`.

- **Predogled pred zamenjavo je pri novih nastavitvah privzeto vklopljen in
  zdaj velja tudi za izrecno očiščeno vsebino odložišča ter besedilo in
  slike, prilepljene v program.** Pri svežnjih dokumentov se še naprej
  prikaže natanko en predogled na dokument z vsemi stranmi; tiho takojšnje
  čiščenje kratkih kopij namerno ne odpre okna.

- **Najdbe je v predogledu mogoče vklopiti in izklopiti prek cele barvne
  vrstice.** Kljukica je zdaj velika in kontrastna; poleg tega polje stanja
  kaže „Zamenjaj" oziroma prečrtano „Zamenjaj", tako da se izbrane in
  odizbrane vrednosti takoj razločijo tudi na temnih barvah zaupanja.

- **Tudi PDF-ji z vidnim varnostnim protipogledom zdaj odprejo predogled le
  enkrat na dokument.** Odizbrani izrazi ostanejo odizbrani za poznejšo
  pričo strani; njeno preverjanje teče naprej, ne da bi isti zagon prekinilo
  z drugim pogovornim oknom.

- **Nadomestne besede v urejevalniku Popravi izgledajo enako tudi na
  rastriranih straneh.** Če rdeča ograda leži v slikovnih točkah namesto v
  besedilni plasti PDF-ja, zdaj kljub temu dobi isto po zaupanju obarvano
  ozadje kot navadna besedilna ograda PDF.

- **Že predogled pred zamenjavo kaže potrebo po preverjanju najdenih
  izrazov.** Vsaka vrstica nosi isto rdeče-oranžno-zeleno barvo kot kasneje
  nadomestek v urejevalniku. Znotraj kategorije stojijo nizka zanesljivost in
  rdeči kandidati za lažni alarm zgoraj, močni zeleni dokazi spodaj;
  izenačenja ostajajo abecedna. Če ista vrednost izhaja iz več najdb, se za
  vsak primer šteje njihova najbolj vprašljiva ocena. Neocenjeni posebni
  primeri stojijo nevtralno rumeno med rdečo in oranžno.

- **Rezultat je zdaj mogoče neposredno kopirati kot datoteko iz urejevalnika
  Popravi.** „Kopiraj rezultat" trenutno očiščeno različico postavi v
  odložišče, ne da bi zaprl urejevalnik in datoteko znova iskal na glavnem
  seznamu. Pri še neshranjeni ročni obdelavi pred tem samodejno teče
  celotna varna pot shranjevanja; „Kopiraj sliko" ostaja ločena funkcija za
  golo slikovne točke.

- **Zamenjane besede v urejevalniku na prvi pogled kažejo, kaj je treba
  najprej preveriti.** Golo ugibanje jezikovnega modela je rdeče, tudi če
  spaCy zanj pavšalno javi 85 odstotkov. Nadaljnje neopprte sodbe modela
  ostajajo kvečjemu oranžne; močni poimenovani dokazi lahko postanejo
  zeleni. Ročno delo in starejši pripisi brez ocenljive presoje ostajajo
  nevtralno rumeni. Tudi samodejne zakrivne proge nosijo te barve v
  predogledu urejevalnika – zdaj tudi, kadar je proga del rastrirane strani
  PDF. Za to se mora pripis ujemati in prejšnji besedni okvir mora biti
  dokazano prekrivno črn; navaden krepki tisk se ne obarva. V shranjenem
  PDF-ju vse proge ostajajo nespremenjeno prekrivno črne.

- **Kar je v predogledu odizbrano, si je mogoče trajno zapomniti.** Kjer
  odstranite kljukico, poveste: tu se je prepoznavanje zmotilo. Doslej je
  to veljalo le za ta en dokument. Zdaj se ob vrstici pojavi stikalo „nikoli
  več"; pritisnjeno vrednost trajno doda na seznam „Nikoli ne odstrani" in
  odslej velja v vsakem dokumentu za neproblematično. Pod seznamom piše, kaj
  postane trajno, preden pritisnete „Zamenjaj". Obratne smeri namerno ni:
  kar je bilo enkrat najdeno, prepoznavanje najde znova.

- **Gumb vse nastavitve ponastavi na dostavljeno stanje.** Stoji spodaj levo
  v oknu nastavitev in vnaprej vpraša. Vaše datoteke, vaša licenca, vaša
  lastna pravila prepoznavanja in samodejni zagon ostanejo nedotaknjeni; kar
  določa vaša uprava, velja naprej. Vsaka nastavitev, ki odstopa od
  dostavljenega stanja, poleg tega nosi oznako „spremenjeno" – tako je na
  prvi pogled videti, kaj ste prestavili.

### Spremenjeno

- **Rezultat se ne odloži več sam od sebe – šele ob shranjevanju.** Zagon iz
  okna svojo očiščeno različico najprej zapiše na začasno mesto; datoteka
  „…_bereinigt" ob izvirniku nastane šele, ko pritisnete „Shrani". Do takrat
  si je rezultat mogoče ogledati, ga dodelati in kopirati. Vsaka dokončana
  vrstica ima za to gumb za shranjevanje, pod seznamom stoji „Shrani vse", v
  urejevalniku pa velja Ctrl+S. Kdor izprazni seznam ali zapre program, je
  vprašan; kar nihče ne odloži, tudi nikjer ne obleži. „Pokaži v mapi" je
  pred shranjevanjem zaklenjeno – začasno mesto ni cilj, kamor bi koga
  poslali. Datoteka pripisa gre ob shranjevanju zraven.

  V nastavitvah pod „Program" „Rezultate takoj odložiti ob izvirniku" vrne
  dosedanje vedenje. Ukazna vrstica, nadzor mape in stražar odložišča
  nespremenjeno odlagajo takoj – tam ni nikogar, ki bi lahko shranil.

- **Orodna vrstica urejevalnika Popravi je pospravljena.** Način učenja
  zdaj stoji na desnem koncu ob primerjalni lupi in „Zamenjanih vrednostih"
  – trije stikali, ki vklapljajo in izklapljajo način dela, tako stojita
  skupaj. „Uporabi na vseh straneh" se je premaknilo k trem oblikam
  zakrivanja, ker tam edino kaj naredi. „Kopiraj rezultat", „Datoteka –
  Ponastavi" in „Uporabi na vseh straneh" so brez oznake; njihovo ime
  ostaja v namigu in meniju. Med „Zamenjaj" in „Obnovi izvirnik" stoji
  ločilna črta: oba sta obratni smeri in sta drug ob drugem izgledala kot
  dve različici istega orodja.

- **Simbol za „Kopiraj rezultat" zdaj kaže dokument.** Dva lista z zavihanim
  kotom in vrsticami besedila namesto dveh enakih listov z majhno kotno
  puščico. „Kopiraj sliko" v zameno nosi slikovni znak, tako da ju je brez
  oznake mogoče razločiti. Gumb „Kopiraj" na seznamu rezultatov kaže isti
  simbol dokumenta – odlaga isto datoteko.

- **Nastavitve so razvrščene in opremljene z naslovi.** „Prepoznavanje" ima
  zdaj štiri odseke: *Kaj se odstrani*, *Kako se zamenja*, *Kako temeljito
  se išče* in *Pred in po zagonu*. Prepoznavanje obrazov ter črtne/QR-kode
  stojijo pri slikah, kjer jih iščete; „Program" je razdeljen na *Datoteke
  rezultatov*, *Ob zagonu*, *Posodobitev*, *Prikaz* in *Povratna informacija
  nam*, pripona imena datoteke rezultata pa stoji pri datotekah rezultatov
  namesto med jezikom in videzom.

- **Napredno prepoznavanje je tovarniško vklopljeno**, tudi preden je
  njegov jezikovni model naložen. Prej je bila privzeta vrednost odvisna od
  zaloge modelov, sveže nastavljen računalnik pa je trajno deloval na šibkejši
  stopnji. Okno za nastavitev na prvi strani ponudi nalaganje modela in
  zraven navede ceno. Če manjka, to kljukica še naprej pove, namesto da bi
  prikazovala stopnjo, ki ne deluje.

- **Dva seznama izrazov se zdaj imenujeta, kar počneta:** „Vedno odstrani"
  namesto „Lastni izrazi" in „Nikoli ne odstrani" namesto „Izjeme".

- **Okno predogleda je preglednejše.** Od devetih vrednosti naprej stojijo v
  dveh stolpcih, vrstice so nižje, število najdb pa stoji neposredno za
  izrazom namesto ob desnem robu.

- **V urejevalniku Popravi „Zamenjaj" stoji pred „Počrni"** – v orodni
  vrstici, v meniju „Orodja" in v kontekstnem meniju na strani. Zamenjava je
  običajen primer: ogrado je mogoče klikniti in obnoviti, progo ne.

- **Manj podvojenih gumbov v urejevalniku.** „Shrani kot …" in „Kopiraj
  sliko" stojita zdaj le še v meniju Datoteka, z ustaljenima bližnjicama. V
  vrstici ostane po eden: Shrani in „Kopiraj rezultat" – kam se shrani, tako
  ali tako piše v vrstici stanja in se tam z enim klikom spremeni.

- **Stražar odložišča se ob prvem zagonu ne ponuja več.** Poseže v vsak
  kopirni postopek sistema; kdor program vidi prvič, tega ne more oceniti.
  V nastavitvah ostaja naprej, tam z ustrezno klavzulo zraven.

- **Svetli videz manj bleščí.** Ozadje okna je doslej prihajalo iz sistemske
  sloga in je bilo tako edina velika površina, o kateri ni odločil nihče –
  pod Windows skoraj bela. Zdaj je zlomljeno bela, na vsakem sistemu enaka.

- **Rundgang in priročnik razlagata barve.** Kaj pomenijo rdeča, oranžna,
  zelena in rumena za zamenjano besedo, zdaj stoji kot lastna postaja v
  rundgangu in kot odstavek v priročniku – v vseh jezikovnih različicah.

### Odpravljeno

- **Priročnik in pogosta vprašanja so kazali ograde, ki jih ni več.** Od
  prehoda na kratko obliko Maskuro piše `[NAM1]`; v pomoči je še naprej
  stalo `[NAME1]`, in stavek „Privzeto je `[NAME1]`" je bil zato preprosto
  napačen. V sedemnajstih prevedenih različicah je poleg tega stala
  **nemška** oznaka namesto lastne – španski bralec je videl `[NAME1]`,
  kjer njegov program piše `[NOMB1]`. Enako pripona datoteke rezultata:
  vse različice so obljubljale `_bereinigt`, medtem ko program ustvari
  `_limpiado`, `_nettoyé` ali `_除去済み`. Prizadeta je bila tudi
  neoštevilčena oblika (pri anonimizaciji se vse imenuje `[NAM]`, ne
  `[NAME]`) in iz vrednosti izpeljana oznaka pri razprševanju.

- **Okno predogleda zdaj prekine le enkrat na dokument – in drugič le, če
  se resnično pojavi nekaj novega.** PDF se bere z dveh strani: enkrat iz
  vsebinskega toka in nazadnje z izrisane, vidne strani. Doslej je vsaka od
  obeh vprašala zase. Zdaj velja: kar ste odločili v prvem oknu, velja
  naprej, in vrednosti, ki so tam že stale, se ne vrnejo. Če pa vidna
  preveritev dokončanih strani najde nekaj, česar prej ni bilo nikjer, vam
  je to znova predloženo – samo to, brez že odločenih vrednosti.

- **Okno predogleda zdaj pove, po čem naj se odloča.** Namesto „odstranite
  kljukico = vrednost ostane" – kar kljukica *počne*, ne pa, kdaj jo je
  treba odstraniti – zdaj stoji: kljukico stran povsod, kjer ne stoji
  osebni podatek; tam se je prepoznavanje zmotilo. Poleg tega vsako okno
  navede preverjalni zagon, iz katerega izhajajo njegove vrednosti.

- **Ograde v celotnem dokumentu izgledajo enako.** Na straneh, ki se pri
  poti OCR na novo zgradijo kot slikovne strani, so bile vidne ograde doslej
  postavljene v pisalni pisavi – „[PLZ4]" je stal širok in s serifi ob
  ozkem „[NAM1]" iste strani. Zdaj nosijo isto brezserifno pisavo kot
  povsod drugod in tudi niso postavljene širše, kot je bilo predvideno pri
  prilagajanju. Nevidna iskalna plast obdrži svojo lastno pisavo – potrebuje
  zanesljive mere, ne videza.

- **V orodni vrstici urejevalnika ni več podvojenih ločilnih črt.** Kjer
  cela skupina orodij odpade za odprto vrsto datoteke – v PDF-ju na primer
  pogled strani in izris –, sta doslej ob vrzeli ostali obe črti.

- **Pri obnavljanju včasih ne ostane več le belo mesto.** Že natančno
  obnovljeno izvirno besedilo se ne prekrije več belo s širokim, skupnim
  okvirjem svoje odstranjene ograde. Pri mešanih besedilnih in slikovnih
  obnovitvah se besedilo poleg tega vstavi nevidno le, kadar slika strani
  natanko to izvirno stanje že vidno nosi. To velja za okvire, okno z
  najdbami in priloge PDF.

- **„Obnovi izvirnik" ne ponuja več po nepotrebnem rastriranja strani.**
  Strogo preverjanje ostanka besedila ostaja dejavno pri zakrivanju in
  zamenjavi. Pri obnavljanju je izpuščeno: tam se izvirna vsebina namerno
  vrača, nespremenjene sosednje besede v razširjenem okviru obnavljanja pa
  niso bile napaka čiščenja, temveč lažni alarm.

- **Rundgang skozi urejevalnik zdaj „Zamenjaj" in „Obnovi izvirnik"
  razlaga kot lastna koraka.** Obe orodji sta neposredno poudarjeni v
  vrstici in opisujeta, da povlečen okvir vstavi ogrado oziroma iz izvorne
  datoteke obnovi prvotno vsebino tega mesta.

- **Tudi državno posebne ograde zdaj ostajajo pri kvečjemu štirih črkah.**
  Te vrste so doslej manjkale v osrednjem katalogu kratic in so se zato
  lahko pojavile izpisane, na primer `[UMSATZSTEUER_ID1]`. Novi zagoni zato
  pišejo `[UID1]`; vse samodejno prepoznane nemške in angleške vrste ostajajo
  pri tem enolične. Tudi sami izračunane kratice drugih jezikov vmesnika ob
  enakem imenu ne zrastejo več čez štiri znake. Lastne oznake pravil
  ostajajo poimenovane nespremenjeno, kot so bile vnesene.

- **Zamenjava zdaj pred zakrivanjem izkoristi ves dejansko prosti prostor
  vrstice.** Dosedanja toga meja pri trikratni prvotni širini besede je
  proge ustvarjala tudi v pretežno praznih poljih obrazcev. Tudi najdbe
  vidnega protipogleda OCR zdaj pri zasedenem besedilu PDF dobijo berljivo
  ogrado; črne ostajajo golo slikovna, opombna in vektorska vsebina, izbrani
  način zakrivanja ter prave tesnine, kamor ne sodi niti enolična kratka
  oblika.

- **Že vidna ograda se pri varnostnem rastriranju ne prepiše več drugič
  rdeče.** Rastriranje zdaj obstoječi nadomestek prevzame iz slike strani in
  vstavi le nevidno iskalno kopijo. Če mora varnostna proga natanko to mesto
  prekriti, se obnovi celoten dejanski okvir ograde namesto le njegovega
  krajšega prvotnega sidra.

- **„Obnovi izvirnik" zdaj označi le varne cilje v povlečenem okviru.** Vsi
  zamenjani izrazi v njem zasvetijo posamično in natančno; nespremenjeno
  tekoče besedilo ostaja nedotaknjeno. Prave vektorske zakrivne proge se
  prav tako označijo posamično, če pod njihovo črno površino PDF-ja leži
  izvirno besedilo. Na rastriranih straneh se predogled zavestno odpove
  navidezni površini proge: prejšnje iskanje po slikovnih točkah je tam
  povezovalo črke, podčrtaje in tabelarne črte v velike rdeče površine na
  napačnih mestih. Sama obnovitev pri tem ostaja nedotaknjena.

- **Pri obnavljanju na rastriranih straneh se besedilo spet vrne.** Doslej
  je tam ostalo prazno mesto z barvnimi pravokotniki nad njim. Obnovljeno
  besedilo je stalo v dokumentu, vendar je bilo prekrito z belo podlago
  ograde, ki se riše nadaljnjič v zgradbi strani.

- **Barve preverjanja se ne prekrivajo več večkrat.** Isto mesto je bilo
  obarvano za vsak vnos pripisa – na eni strani pet pravih najdb, vsaka
  petkrat prebarvana, dokler iz blede oznake ni nastal zbit blok. In se ne
  pojavljajo več na besedah, ki sploh niso bile zamenjane: če izvirna
  vrednost še stoji na strani, tam tudi ni več oznake.

## 0.10.40-beta.1 – 24. avgust 2026

### Odpravljeno

- **Zakrivne proge v urejevalniku imajo zdaj varnostni rob.** Besedni,
  vrstični in prosti okviri pokrijejo tudi previsne pisave in zglajene robne
  slikovne točke; preverjanje izrisa dodatno zagotovi, da ne ostanejo niti
  vidni ostanki niti berljivo izvirno besedilo.

- **Nadomestna besedila ostajajo berljiva in enotno kratka.** Nova imena,
  naslovi in prosti izrazi se prikažejo na primer kot `[NAM1]`, `[ADR2]` in
  `[BEG3]`. Trdna spodnja meja je 4,5 pike; ob pomanjkanju prostora se
  najprej skrajša, nato razširi uporabni tekoči prostor. Stari pripisi z
  dolgimi ogradami ostajajo berljivi in obnovljivi.

- **Večbesedne zamenjave iz okna z najdbami so zavarovane pred podvojenimi
  oznakami in izvirnimi ostanki.** Regresija zdrži z oštevilčenimi ogradami
  in brez njih; za vsako najdbo ostane natanko en skupen pripis.

- **Obnovljena vsebina odložišča se na macOS ne očisti takoj znova.** Tudi
  če se sistemski podpis po zapisu spremeni z zamikom, Maskuro zanesljivo
  prepozna lastno vsebino.

### Novo

- **Urejevalnik lahko datoteko v celoti ponastavi na sveže očiščeno
  izhodiščno različico.** „Datoteka – Ponastavi" po potrditvi zavrže vse
  popravke trenutnega zavihka, vključno s seznamom zamenjav in števci. Ukaz
  je brez sprememb zaklenjen in ga je mogoče z „Razveljavi" znova preklicati.

- **Premaknjene datumske navedbe zdaj zanesljivo ohranijo svojo kronologijo
  v več datotekah.** Skupni zamik se trajno zasidra v pravila že ob vklopu
  strategije; poleg tega zamik ne more več znašati nič dni in tako neopazno
  pustiti pravega datuma.

- **Ročno delo s PDF zdaj pokriva celoten profesionalen potek zakrivanja.**
  Posamezne izraze, sezname in regularne vzorce je mogoče iskati in varno
  zakriti v odprtem PDF-ju ali v vseh PDF-jih neke mape; cele strani in
  obsege strani je mogoče izbrati neposredno. Barva, nevtralno bela
  površina, prekrivno besedilo, pisava, poravnava in ponavljanje imajo
  predogled, ponovno uporabne kode pa je mogoče upravljati ter uvoziti in
  izvoziti. Čiščenje PDF-ja po izbiri odstrani vso skrito vsebino s
  popolno obnovo ali izbrane razrede podatkov. Najvarnejša izbira je jasno
  priporočena, neveljavni iskalni vzorci so pojasnjeni, zagoni po mapah pa
  pišejo izključno kopije rezultatov.

- **Prostovoljna statistika uporabe zdaj kaže namestitve in menjave
  različic.** Maskuro za to ustvari naključno, krajevno shranjeno
  identifikacijsko oznako namestitve. Ne vsebuje nobenih podatkov o
  napravi, uporabniku ali licenci; strežnik shrani le njeno vrednost
  SHA-256. Statistiko je mogoče v nastavitvah v celoti izklopiti.

- **Rundgang je zdaj vodena vaja skozi obe okni.** Sam vstavi izmišljeni
  vadbeni dokument na seznam, pojasni pot do čiščenja in se po zagonu
  samodejno nadaljuje v urejevalniku. Kdor rundgang prekine, konča tudi to
  nadaljevanje.

- **Prepoznana so podjetja iz petnajstih nadaljnjih pravnih območij.** Kdor
  čisti listine iz Baltika, Belgije, Skandinavije, Češke, Poljske,
  jugovzhodne Evrope, Singapurja, Brazilije ali Mehike, ne izgubi več imen
  podjetij zato, ker njihova pravna oblika ni bila znana – na novo so med
  drugim OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s.,
  S.K.A., Pte. Ltd. ter S.A. de C.V. in S. de R.L.

### Spremenjeno

- **Orodne vrstice urejevalnika zdaj bolj ciljno izkoriščajo svoj prostor.**
  Enolični standardni simboli in neposredno prepoznavne oblike orodij so v
  vrstici brez ponavljajočega se besedila; dvoumna dejanja obdržijo svoje
  ime. Pod „Pogled" je mogoče izklopiti „Prikaži oznake orodij", da se
  obe vrstici v celoti skrčita na simbole. Namigi in meniji ostajajo pri
  tem v celoti opisani, izbira pa se zapomni.

- **Način učenja je zdaj trajno viden v orodni vrstici.** Tam ga je mogoče
  neposredno vklopiti in izklopiti, tudi kadar je predal zamenjanih vrednosti
  zaprt. Orodna vrstica, meni Orodja in dosedanja kljukica v predalu vedno
  kažejo isto stanje.

- **„Ponastavi" pri primerjalni lupi zdaj ponastavi le njeno povečavo.**
  Gumb obnovi privzetih 125 odstotkov, ne da bi lupo zasidral, premaknil ali
  spremenil velikost njenega okna. Za celotno postavitev je še naprej
  pristojen „Ponastavi pogled".

- **Napake in želje je zdaj mogoče prijaviti tudi prek gumba za pomoč.**
  „Prijavi napako …" in „Izrazi željo …" tam zdaj stojita enako kot v
  klasičnem meniju Pomoč; obe poti odpreta že obstoječe varno prijavo
  napake oziroma javni seznam želja.

- **Meni ikone v opravilni vrstici je krajši in jasneje urejen.** Oba ukaza
  z globalno bližnjico – čiščenje odložišča in posnetek zaslona – zdaj
  stojita neposredno drug pod drugim s skupnim desnim stolpcem bližnjic.
  „Obnovi zadnjo izvirno vsebino" tam odpade; razumljivejši gumb za
  obnovitev ostaja na voljo v glavnem oknu.

- **Pravne strani so neposredno dosegljive pod „Pomoč → Pravne
  informacije".** Podmeni vodi do licenčnih pogojev, izjave o varstvu
  podatkov, impresuma in splošnih pogojev na maskuro.com. Napotki za
  odstop od pogodbe ostajajo pri nakupu na spletni strani.

- **Ročno zakrite datoteke PDF se ob shranjevanju v celoti znova
  zgradijo.** Vidne ostanejo strani in njihova na novo prebrana iskalna
  plast; metapodatki, priloge datoteke, zaznamki, komentarji, vrednosti
  obrazcev, skrite plasti, iskalni indeksi, skripte, obrezana vsebina in v
  drugih objektih skrita vsebina se ne prenesejo v izhodno datoteko. Pisava
  in vektorska grafika nato sestojita iz slikovnih točk – to je cena
  dokazljive meje do tujega objektnega drevesa PDF.

- **Ctrl+Shift+B zdaj na vseh sistemih privzeto zajame posnetek zaslona z
  Maskurom.** Tipka Print Screen in kombinacije z njo ostajajo mogoče kot
  lastna dodelitev. V meniju ikone opravilne vrstice zdaj globalne
  tipkovne bližnjice stojijo desno ob pripadajočih ukazih. Lastne shranjene
  dodelitve ostanejo ohranjene.

- **Urejevalnik se zažene s stranmi in primerjalno lupo levo.** Predal
  strani stoji zgoraj, odprta lupa izvirnika neposredno pod njim; zamenjane
  vrednosti ostajajo desno. Zavestno shranjena lastna razporeditev ima še
  naprej prednost.

- **Vadbeni dokument ni več trajno v glavnem oknu.** Del je vodene vaje in
  ostaja dodatno dosegljiv pod „Pomoč".

- **Prvi zagon vodi neposredno v praktično vajo.** Slikovna kratka navodila
  se ne ponujajo več kot drugi, vsebinsko podvojen vstopni pot; ostajajo
  vsak čas dosegljiva pod „Pomoč → Kratka navodila".

- **Mirujoča ikona v opravilni vrstici ostaja v polni barvi.** Zdaj kaže
  isti izrazit ščit Maskuro kot aktivni način odložišča; le pri aktivnem
  nadzoru se doda zelena svetleča pika.

- **Vadbeni dokument ostane v Maskuru.** Vstopni gumb ustvari izmišljeni PDF
  in ga vstavi neposredno v seznam datotek, ne zažene pa več dodatnega
  pregledovalnika PDF.

- **Iskanje v oknu Popravi ostaja med tipkanjem tekoče.** Prostor za
  števec najdb je rezerviran že ob odpiranju; njegovo prvo besedilo ne
  spremeni več platna in ne sproži novega rastriranja PDF-ja.

- **Imena proizvajalcev v navedbah izdelka ostajajo vidna.** Vnos, kot je
  „Izdelek: TRILUX ali enakovreden", opisuje potrebno blago in se ne
  zakrije več le zaradi te oznake kot podjetje. Polja dobavitelja, podjetja
  in proizvajalca ostajajo pri tem nedotaknjena.

- **Meritve korpusa zdaj preveč zakrite najdbe štejejo za lažne alarme.**
  Kadar Maskuro odstrani pričakovano ime, pri tem pa zajame še del stavka,
  se zdaj poveča število lažnih alarmov. Poročilo take prekoračitve
  izkazuje tudi ločeno; prejšnja števila lažnih alarmov zato niso
  neposredno primerljiva.

### Odpravljeno

- **Tehnični in uradni izrazi iz nemških izvirnih listin se redkeje
  zakrijejo kot imena ali kraji.** Oprema vozil, vrstice postavk in vsot,
  izrazi za oddajo naročil in varstvo podatkov, sklici na zakone ter imena
  datotek javnih gradiv se zavrejo le v svojem izkazanem stvarnem
  sobesedilu. Pri optičnem prepoznavanju izgubljen preglas v „Marz 2026"
  ostaja zaščiten kot mesec; „Marz" brez datumske povezave je lahko še
  naprej pravo ime ali kraj.

- **„Obnovi izvirnik" takoj zajame celotno potrebno širino.** Če okvir
  zadene le eno besedo dodeljene vrednosti, jo Maskuro na podlagi pripisa
  in izvirne vrstice samostojno razširi na celotno navedbo – na primer od
  „Planungs" na „Nordlicht Planungs GmbH". Nato oprijemljivi okvir prav
  tako kaže dejansko obnovljeno skupno širino.

- **„Obnovi izvirnik" zdaj kaže črne proge kot enolični cilj.** Ob prehodu
  ali vlečenju čez njih cela prepoznana proga zasveti rdeče s svetlim
  kontrastnim obrisom, namesto le komaj pripisljivega besedilnega okvira
  zraven. To velja tudi za rastrirane strani, na katerih proga sestoji le
  še iz slikovnih točk.

- **Rundgang urejevalnika zdaj ne izpusti več postaj, kadar so bili predali
  zaprti.** Za vodenje Maskuro začasno sam odpre in uredi predal strani,
  primerjalno lupo in zamenjane vrednosti. Po „Končano" ali prekinitvi se
  vrne osebna razporeditev. Če orodje pri neki vrsti dokumenta načeloma ni
  na voljo, njegova razlaga ostane kot besedilna postaja, namesto da bi
  neopazno izginila.

- **„Zamenjaj" ostane viden tudi pri varnostni rezervni rešitvi za PDF.**
  Če je moral Maskuro stran zaradi preostalega znaka ali poškodovanega
  poteka besedila na novo zgraditi kot sliko, so pravilne zamenjave ostale
  vidne le še v iskalni plasti, na strani pa so bile črne proge. Dejansko
  nastavljene nadomestne vrednosti zdaj ostajajo vidno rdeče in iskane skozi
  vse ponovne izgradnje z rastriranjem in optičnim prepoznavanjem.

- **Opozorila nad očiščeno različico ostajajo berljiva v temnem
  videzu.** Naslov različice, upravljalna vrstica in uvod zdaj barvo
  pisave prevzamejo neposredno iz dejansko prikazanega okna Qt.

- **Zakrivni okviri na rastriranih straneh PDF spet ležijo nad besedilom.**
  Nevidni besedni okviri so bili glede na izvirno pisavo ožji od vidnih
  črk. Zaradi tega so nastajale vrzeli v progi ali je zadnja črka ostala
  berljiva. Okviri zdaj ohranjajo širino, višino in smer poteka vidne
  besede.

- **„Kaj je novega" se spet začne povsem na vrhu.** Pogovorno okno
  changeloga po dokončani izgradnji okna izrecno postavi besedilni kazalec
  in drsnik na začetek, namesto da bi se glede na stanje Qt začelo sredi
  novosti.

- **Zapiranje med prepoznavanjem besed na skenu ostaja tiho.** Ravno
  dokončan ozadnji tek OCR ne pošilja več v že zaprto okno Popravi.

- **Relativne časovne navedbe se ne štejejo več za imena.** Ustaljene
  besedne zveze, kot so „danes", „včeraj", „jutri" in „naslednji teden",
  Maskuro zdaj pozna iz uradnih koledarskih podatkov ustreznega jezika
  dokumenta.

- **Zaprtje med prvim nalaganjem modela pospravi zares čisto.** Kdor Maskuro
  ali okno Popravi zapre takoj po odprtju, ne pusti niti ene niti v
  domorodnem prepoznavanju jezika še delujoče niti za sabo pri razgradnji
  procesa. To preprečuje občasno poročilo o sesutju ob zapiranju; že
  tekoče nalaganje se urejeno dokonča.

- **Zakasnela začetna pogovorna okna se po zaprtju ne prikažejo več.** Kdor
  glavno okno zapre kmalu po zagonu, mu nato ni več prikazano niti nevidno
  niti zakasnelo vprašanje o najboljšem prepoznavanju, novostih ali uvodu.

- **HTML in e-pošta ohranjata svoje konce vrstic.** Na Windows je
  serializacija HTML po čiščenju in preklicu mešala LF in CRLF. Vsebina in
  oblikovanje sta bila pravilna, datoteka pa ni bila več enaka po bajtih.
  Datoteke HTML in sporočila MIME zdaj znova prevzamejo zapis svojega vira.

- **Imena podjetij z veznim izrazom ostanejo popolna.** Za predlogom je
  Maskuro imena, kot sta „Gesellschaft für Systemtechnik mbH" ali „Bank für
  Arbeit und Wirtschaft AG", odrezal pri besedi „für". Celotno ime podjetja
  se zdaj prepozna; pravi stavčni uvodi, kot je „Zavarovani smo pri Alpha
  GmbH", ostajajo vidni.

- **Kitajska imena podjetij ostanejo popolna pred svojo pravno obliko.**
  Sestavina znamke, ki jo je mogoče razumeti kot glagol, je kljub
  enoličnemu dodatku „有限公司" lahko zavrgla celotno ime. V pisavah brez
  velikih in malih črk ima uradno sidro pravne oblike zdaj prednost pred to
  negotovo mejo besedne vrste.

- **Strani PDF so se po nepotrebnem spreminjale v slike.** Pri večstranskih
  PDF-jih, katerih strani si delijo seznam pisav – kar tako oblikujejo
  pogosti ustvarjalci –, so po prvi strani vse nadaljnje izgubile sklic na
  svoje pisave. Posledica je bila dvojna: preglasi v rezultatu niso bili
  več iskani („Auftragsbestätigung" ni bilo mogoče najti), naknadno
  preverjanje pa je zato štelo za spregledane črke, ki na strani nikoli
  niso stale – nepoškodovane besedilne strani je rastriralo v slike, s tem
  ne več iskane, ne kopirane in znatno večje. V preizkusnem naboru je to
  prizadelo štiri od sedemnajstih strani.
- **Sama vejica ne sproži več rastriranja.** Če se območje najdbe konča na
  besedi, ločilo zraven še ravno sodi zraven. Vejica ali pika pa ni
  spregledana navedba, rastriranje pa stane celo stran. Črke in številke
  ostajajo nespremenjeno razlog za doostritev.

## 0.10.38-alpha.20260824 – 24. avgust 2026

### Novo

- **Imena podjetij brez pravne oblike se zdaj prepoznajo, kadar jih navede
  njihova oznaka.** „Dobavitelj: Kranzbichler Handels GmbH" je bilo
  odstranjeno od nekdaj – pravna oblika razkrije podjetje. „Dobavitelj:
  Dehner Märkte" je ostalo, in v ponudbah, razpisih in naročilih tako
  večinoma stoji dobavitelj. Enako velja za „Podjetje:", „Proizvajalec:",
  „Izdelek:", „Delodajalec:" in njihove ustreznice v osmih dodatnih
  jezikih, tudi kadar oznaka stoji sama na svoji vrstici, ime pa pod njo.

  Kar za oznako *ni* podjetje, ostane nedotaknjeno: „Dobavitelj: glej
  prilogo" se ne zakrije – sicer bi stalo „Dobavitelj: [ORGA1]", kar bi
  trdilo ime, ki nikoli ni obstajalo. Oznake, za katerimi enako pogosto
  stoji človek („Kupec:", „Naročnik:"), so namerno izvzete.

- **Vstavljeno sliko je zdaj mogoče tudi urejati.** V oknu „Očisti sliko"
  ob „Kopiraj rezultat" stoji gumb *Uredi v urejevalniku*: slika se očisti
  in nato odpre za naknadno zakrivanje, oznake in poudarke – ista pot kot
  jo gre posnetek zaslona.

- **Številke za svojo oznako se zdaj najdejo tudi, kadar poimenujejo
  poslovnega partnerja.** Doslej so padle številke strank, pogodb in
  zaposlenih; zdaj tudi številka dolžnika, upnika in dobavitelja, avstrijska
  številka delodajalca, registracija ANKÖ ter številka WEEE, EAR in EPR
  proizvajalca – v nemščini kot v angleščini. Poleg tega Maskuro zdaj
  razume zapis postavljenih glav ponudb s presledkom pred dvopičjem
  („Št. stranke : K903944"). Številke artiklov, naročil, nalogov, ponudb in
  računov ostajajo nedotaknjene: poimenujejo postopek ali blago, ne osebe.
  Kdor jih vseeno želi odstraniti, jih shrani kot lasten iskalni vzorec.

- **Zdaj vidite, koliko časa je datoteka potrebovala.** V dokončani vrstici
  stoji trajanje ob prepoznanem jeziku („dokončano · nemščina · 2,4 s"), v
  povzetku trajanje celega zagona, v predalu kazalnikov vsota – in v
  poročilu o preverjanju stoji kot lastno polje. Pri več datotekah vrstica
  razkrije, katera od njih je stala čas.

- **Pisave, ki jih sistemski OCR ne podpira, je mogoče z obstoječo jezikovno
  datoteko prebrati nadomestno.** Doslej je veljalo: če sistemsko optično
  prepoznavanje pisave ne obvlada (na Macu na primer devanagari), je v
  rezultatu stalo „Slike NISO bile preverjene", navedbe na sliki pa so
  ostale. Zdaj vskoči priložena optična prepoznava, če je ustrezna
  jezikovna datoteka na voljo. Ker je tako prebrana slika negotovejša od
  redno preverjene, to v rezultatu piše: „prebrano z nadomestnim
  postopkom – prosimo, oglejte si". Izmerjeno na zgodovinskem vmesnem
  stanju preizkusa za hindijščino: **deset navedb več najdenih in štirje
  lažni alarmi manj** (64 % → 73 %). Trenutna sklepna vrednost stoji višje
  in je s tem ni zamenjati.

- **Optično prepoznavanje besedila zdaj vpraša po pravem jeziku.** Za vse
  jezike dokumentov razen nemščine in angleščine se je doslej uporabljal
  angleški prepoznavalni model, tudi kadar je bila ustrezna jezikovna
  datoteka na voljo. Pod Windows je to zadelo vsak jezik – grščina,
  japonščina ali hindijščina so bile tam brane z angleškim modelom.

- **Čarovnik za nastavitev ob čisto prvem zagonu.** (Kdor je Maskuro že
  uporabljal, ga ne dobi – „prvi zagon" pomeni prvi zagon, ne prvi zagon po
  tej posodobitvi.) Tri vprašanja namesto šestih slik: jezik vaših
  dokumentov, ali se bere tudi besedilo na slikah in kako želite Maskuro
  doseči v vsakdanu. Na koncu ostajajo trije poti – vadbeni dokument,
  rundgang ali slikovna kratka navodila. Vse je mogoče preskočiti, „Pomoč →
  Ponovi nastavitev" pa čarovnika prikliče nazaj.

- **F1 odpre priročnik pri ustreznem poglavju.** V glavnem oknu, v
  nastavitvah (tam odvisno od strani), v oknu za pregled in v upravljanju
  jezikov; v oknu Popravi prek Shift+F1, ker F1 tam od nekdaj kaže
  tipkovne bližnjice. Doslej se je pomoč vedno začela zgoraj, pri 25
  poglavjih.

- **Novo prvo poglavje priročnika: „V treh minutah do prvega rezultata".**
  Štirje koraki, več za dokument ni treba – v vseh 18 jezikovnih
  različicah.

- **Rundgang skozi okno.** „Pomoč → Rundgang skozi okno" postavi žarometni
  snop na en element upravljanja za drugim in zraven zapiše stavek – v
  glavnem oknu osem postaj, v oknu Popravi sedem. Za razliko od slikovnih
  kratkih navodil razloži okno, pred katerim ravno sedite. Kadar koli
  prekinete z Esc.

- **Vadbeni dokument za nenevarno preizkušanje.** Pod odlagalno površino
  zdaj stoji „Odpri vadbeni dokument" (tudi v meniju Pomoč). Ustvari
  izmišljen list – ime, naslov, telefonska številka, IBAN, številka
  socialnega zavarovanja – na listu pa hkrati piše, kaj lahko z njim
  storite in kaj boste videli nato. Nobena beseda od tega ne pripada
  resnični osebi; prvi dokument, ki ga pošljete skozi Maskuro, torej ni
  treba, da je pravi.

- **„Samo poglej …" zdaj stoji ob „Očisti".** Pokaže, kje ležijo osebni
  podatki – datoteka, vrsta in število –, ne da bi karkoli spremenil ali
  zapisal. Kdor je odložil dokument, s tem najprej pogleda, preden očisti.
  Doslej je bila ta pot le v meniju Datoteka pod „Preglej mapo …" in je
  šla prek cele mape namesto prek odloženih datotek.

- **Če ni bilo nič najdeno, zdaj piše, kaj je lahko razlog.** Na primer: v
  datoteki so slike, a „Preveri tudi besedilo na slikah" je izklopljeno.
  Ali: nastavljen jezik se ne ujema z jezikom v dokumentu. In če nič od
  tega ne drži, Maskuro pove tudi to.

- **Okno Popravi vas ob prvem obisku pozdravi s tremi stavki:** klik zakrije
  besedo, vlečenje območje, desno stojijo zamenjane vrednosti. „Razumem"
  napotek trajno umakne; „Pomoč → Ponovno pokaži uvod" ga prikliče nazaj.

- **Klik na besedo zdaj tudi na skeniranih straneh.** Doslej je bilo besede
  mogoče klikniti le tam, kjer PDF prinaša besedilno plast – pri skenu ni
  šlo, in v istem dokumentu se je to lahko spreminjalo od strani do
  strani. Take strani se zdaj enkratno preberejo z optičnim
  prepoznavanjem; nato kliknete besede kot povsod drugod. Vrstica stanja
  pove, kaj se ravno dogaja.

- **Predal strani je spet površina.** Nehal se je sredi svojega stolpca:
  odrezan naslovni trak, ob njem pas druge barve, trenutna stran pa je
  bila prepoznavna le po barvnem okvirčku za svojo številko. Zdaj zapolni
  svoj stolpec, ga je mogoče razširiti, trenutna stran pa je poudarjena
  kot cela ploščica – z nepopačenim predogledom strani v njej.

- **Zamenjana mesta zasvetijo bledo rumeno.** V pogledu strani je s tem na
  prvi pogled videti, kje je bilo kaj zamenjano – ista barva, ki jo
  primerjalna lupa uporablja nad izvirnikom. Rdeč okvir ob kazanju z miško
  ostaja nespremenjen.

- **„Ponastavi pogled" v oknu Popravi** (meni „Pogled"). Kdor je premaknil,
  izvlekel ali zaprl predal strani ali seznam najdb, s tem vse postavi
  nazaj tja, kjer je stalo ob prvem zagonu.

### Spremenjeno

- **Ograde so krajše.** Iz `[SOZIALVERSICHERUNGSNR_1]` nastane `[SVNR1]`,
  iz `[ORGANISATION_1]` `[ORGA1]`, iz `[EMAIL_1]` `[MAIL1]`. Razlog ni
  lepota: ograda, daljša od vrednosti, ki jo zamenjuje, razmakne vrstico in
  v ozkem stolpcu tabele ne najde več prostora – tam je doslej ostala
  črna proga, ki nikomur več ne pove, da je tam nekaj stalo. Kjer obstaja
  uveljavljena kratica, stoji ta (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`). Rezultati
  prejšnjih zagonov ostajajo uporabni: stari zapis se še naprej prepozna,
  datoteke pripisa iz preteklosti pa delujejo nespremenjeno.

- **Ikona programa zdaj povsod izgleda enako.** V menijski vrstici Maca se
  je doslej pojavil enobarven ščit, ki ga je sistem sam obarval črno ali
  belo, v opravilni vrstici Windows zelen oziroma sivi. Zdaj vsaka vrstica
  nosi isti modri ščit Maskuro. Po čemer je razvidno, ali se odložišče
  nadzoruje, ostaja enako jasno: če nadzor teče, sedi na ščitu zelena
  pika; če miruje, isti ščit stoji bled. Tudi v najmanjših velikostih zdaj
  v ščitu stojita obe zakrivni progi – doslej je opravilna vrstica tam
  kazala le eno.

- **Obrazi se prepoznajo z modelom, katerega učne slike so nastale s
  privolitvijo.** Zdaj se dostavi MediaPipe BlazeFace (Apache-2.0); dosedanji
  detektor ostaja vgrajen in preklopljiv, a se ne dostavlja več, ker njegov
  izvor učenja ni dokončno pojasnjen. Za prepoznavanje se ne spremeni
  nič: na 324 portretih in 143 slikah brez obraza nova različica najde
  enako veliko ob enako malo napačnih prijemih in potrebuje tretjino časa.

- **OCR je varnostno sidro za najmočnejšo zavezo PDF.** Običajni zagon PDF
  ga uporablja in ustvari popolno minimalno zgradbo. Kdor OCR izrecno
  izklopi, dobi bolj združljivo pot prek predmetov; vmesnik, sklepno
  sporočilo in priročnik zdaj izrecno povedo, da ta pot ne ponuja iste
  arhitekture proti neznanim skritim kanalom PDF.

- **Prodajna zapora zdaj zaklene tudi doslej priloženi model YuNet.**
  Licenca MIT za natančno utež ostaja dokumentirana, a za javno vidno
  učno verigo prek WIDER FACE ne zadošča kot konservativna prodajna
  sprostitev. Pred prodajo je potrebna pisna razjasnitev ali zamenjava z
  modelom z zanesljivo komercialno podatkovno in utežno verigo.

- **Imena podjetij in organizacij se zdaj odstranijo same od sebe.** Doslej
  so ostajala, dokler jih niste izrecno zahtevali. To je bila za poslovni
  dopis napačna privzeta vrednost: kdor posreduje ponudbo, v njej ne želi
  brati naročnika. „Kranzbichler Handels GmbH", „Institut für Bauphysik"
  in podobno se zato obravnava kot ime. Kdor to potrebuje drugače, izklopi
  v oknu; na ukazni vrstici se stikalo zdaj imenuje
  `--ohne-organisationen`. Stari `--mit-organisationen` se še naprej
  sprejme in ne naredi več ničesar, da obstoječe skripte in bližnjice ne
  zlomijo. Datumske in denarne navedbe ostajajo nespremenjeno izvzete.

- **Zakrivanje ima zdaj tri oblike namesto dveh kljukic.** „Besede", „Cela
  vrstica" in „Prosti okvir" stojijo kot ena izbira drug ob drugem – velja
  vedno natanko ena. Doslej sta bila „Besedilne vrstice" in „Cela vrstica"
  dve neodvisni stikali, ki sta lahko bili obe pritisnjeni, prosti okvir
  pa sploh ni bil gumb, temveč izklopljeno stanje prvega. Vsi trije stojijo
  vidno ob svojem orodju in so sivi, dokler je izbrano drugo orodje.

### Izboljšano

- **Prvi dokument je dokončan približno sekundo hitreje.** Preden se
  čiščenje začne, Maskuro ugotovi jezik dokumenta – in si je za to doslej
  prek poti, ki je naložila mnogo več kot le besede, priskrbel sezname
  besed vseh 48 jezikov. To je bilo približno polovica čakalnega časa do
  prvega rezultata. Prepoznavanje samo je nespremenjeno: vidi iste besede
  kot prej, le hitreje. Vsak nadaljnji dokument s tem tako ali tako ni bil
  prizadet.

- **Dokumenti z zelo dolgimi odstavki se preverijo hitreje.** Pri odstavku
  brez preloma vrstice je Maskuro doslej za vsako najdeno mesto znova
  prebral celega; zdaj zadošča enkrat. Daljši ko je odstavek, večja je
  razlika – izmerjeno približno sedmino manj računskega časa. Na rezultatu
  se ne spremeni nič.

### Odpravljeno

- **S podjetjem je pogosto izginila tudi polovica stavka.** Če je ime
  podjetja stalo v tekočem besedilu – „Informacija o Gottwald GmbH & Co
  KG", „… (splošni pogoji) Musterbetriebe GmbH" –, ni bilo zakrito le
  ime, temveč vse pred njim do začetka stavka. Besedilo je s tem postalo
  neberljivo in je izgledalo, kot da je bilo zakrivano naključno. Imena
  podjetij, ki sama nosijo „für" ali „und" („Bank für Arbeit und
  Wirtschaft AG"), ostajajo nespremenjeno popolna.

- **Imena podjetij so ostajala v glavah dopisov, čeprav so bila v
  besedilu odstranjena.** V ponudbi je sedež podjetja v sliki glave
  dopisa ostal berljiv – isti kraj, ki ga je Maskuro zakril v tekočem
  besedilu; v iskanem besedilu rezultata je celo ostal naprej, le
  nevidno. Kar je bilo enkrat odstranjeno, se zdaj odstrani tudi tam, kjer
  je na voljo le kot slika. To učinkuje tudi pri logotipih in besednih
  znamkah, narisanih kot grafika.

- **macOS je ob vsakem zagonu vprašal po zajemu zaslona**, tudi kadar je
  bila privolitev že zdavnaj podeljena. Namig ob zagonu je preizkusil
  zajem, prav to pa na zaslon prikliče sistemsko pogovorno okno. Zdaj ob
  zagonu vpraša le še Maskuro sam, in to enkrat; sistem vpraša šele, ko
  resnično zajamete posnetek zaslona.

- **Tehnični stvarni izrazi so veljali za kraje in podjetja.**
  „Vpajalna točka", „Ravna streha", „Razdelilna naprava", „Podnožje
  javljalnika" in ducati podobnih besed so izginjali iz ponudb in popisov
  del. Maskuro jih zdaj prepozna po osnovni besedi: kar se konča na
  „-naprava", „-točka" ali „-kanal", je stvar. Imena krajev, kot so
  Berlin, Melk ali Wieselburg, take osnovne besede nimajo in ostajajo
  nedotaknjena – enako naslovi, kot sta „Der Graben" ali „Alter Markt".

- **Japonski, korejski, kitajski, tajski in gudžaratski dokumenti so lahko
  povzročili sesutje programa.** Če je dokument v enem od teh petih
  jezikov vseboval spletni naslov brez „https://" spredaj, se je čiščenje
  prekinilo z notranjo napako – pri odprtem oknu se je pri tem izgubilo
  tudi preostalo delo. Vseh oseminštirideset izbirljivih jezikov dokumenta
  zdaj tečejo do konca; če za jezik manjka frekvenčni slovar, navedba v
  dvomu ostane namesto da bi izginila.

- **Oznake polj so ščitile le v nemščini in angleščini.** „Reference" je
  ostal, italijanski „Riferimento" in portugalski „Referência" pa sta bila
  odstranjena kot navedba kraja – isto ime polja, ista vrstica, drug
  rezultat. Kdor ni delal v angleščini, je bil s tem slabše zaščiten.
  Maskuro zdaj pozna v vseh enajstih vzdrževanih jezikih ista imena polj.

- **„Obnovi izvirnik" je na skeniranih straneh obnovil preveč.** Okvir čez
  zakrito vrstico bloka naslova je znova razkril **cel blok** – in stran
  je ostala raztrgana: ostanki prog so stali naprej, iz njih pa so
  štrleli posamezni konci besed. Vzrok je bil, da progi, ki stojita ena
  pod drugo na rastrirani strani, mejita druga na drugo in sta zato
  veljali za eno samo površino. Zdaj se obnovi natanko vrstica, na katero
  kaže okvir; sosednje vrstice ostanejo zakrite, proga zadete vrstice pa
  povsem izgine.

- **Količinske navedbe v seznamih postavk so veljale za naslove.** V
  vrstici, kot je „1.4  Kabelski jarek  100,00  m", je bilo „Kabelski
  jarek 100" zamenjano kot ulica s hišno številko. Take vrstice zdaj
  ostanejo; pravi naslovi – tudi „Hauptplatz 1, 3250 Wieselburg" – se
  prepoznajo nespremenjeno.

- **Pred imenom podjetja je izginila polovica stavka.** Iz „Pogodba med
  podjetjem Gottwald GmbH & Co KG in naročnikom." je nastalo
  „[ORGANISATION_1] in naročnikom." – začetek stavka je izginil, s tem pa
  napotek, za kaj gre. Zdaj pade le ime podjetja samo. Kjer vrstna beseda
  spada k imenu („Deutsche Bank AG", „Universität Wien"), ostane vse kot
  doslej.

- **V zapisniku so ostali govorci, katerih ime je hkrati poklic.**
  „Bauer:", „Koch:", „Weber:" pred besedno prijavo so bili spregledani,
  „Gruber:" zraven ne – Maskuro je doslej potreboval vsaj eno prepoznano
  ime v listini, da je vrstice sploh prebral kot besedne prijave. Če
  dokument nosi naslov, kot je „Zapisnik sklepov" ali „Zapisnik", zdaj to
  zadošča. Opozorilne vrstice („Pozor: …", „Napotek: …") ostajajo
  nedotaknjene.

- **Oznaka polja je izginila skupaj s svojo vrednostjo.** Iz „Projekt:
  Sanacija in razširitev občinskega centra" je nastala ena sama ograda –
  izginila je tudi beseda „Projekt:", s tem pa napotek, kaj je na tem
  mestu stalo. Oznake zdaj ostanejo. Kjer oznaka pripada navedbi in nosi
  njen pomen („interna št. 214"), se ne spremeni nič.

- **Največje prepoznavanje ni pospravilo stvarnih izrazov.** „Ravna
  streha", „vpajalna točka", „elektrotehnika" in podobne strokovne besede
  so bile zamenjane kot kraj ali podjetje tudi z vklopljeno stopnjo UI –
  UI teh najdb sploh ni dobila v presojo. Zdaj jih preveri tudi ona: na
  korpusu iz razpisnih in pogodbenih besedil s tem izginejo vseh 27
  napačnih prijemov, ne da bi ostala nepokrita niti ena resnična navedba.
  Imena, podjetja in kraji se prepoznajo nespremenjeno.

- **Vrstne besede za vrste ustanov so veljale za organizacije.** V
  pogodbenem besedilu so izginili „visoke šole in univerze", „državne in
  zasebne šole", „akademske učne bolnišnice", „izobraževalna ustanova" in
  „dobavitelji" – besede, ki ne poimenujejo določenega mesta, temveč
  vrsto mesta. Zdaj ostanejo. Če pred njimi stoji lastno ime („Komisija
  EU"), se še naprej zamenja, imena podjetij pa to pravilo sploh ne
  zajame.

- **Imena na seznamih so padla le, če so bila pogosta.** Na seznamu
  udeležencev ali prisotnosti pod glavo stolpca „Ime" so bila odstranjena
  „Anna Huber" in „Thomas Müller", „Wójcik Aleksandra" ali „Kücükgöl
  Sinan" pa ne – ista vrstica, ista zgradba. Kdor nosi redkejše ime, je
  bil s tem slabše zaščiten. Zdaj odloča glava stolpca: kar stoji pod
  „Ime", je ime. Seznam postavk s stvarno glavo stolpca ostane
  nedotaknjen.

- **Telefonska številka za „interna" je bila prerezana na sredini.** Iz
  „Interna 0732 771190" je nastalo „[INTERNA_1] 771190" – druga polovica
  številke je ostala berljiva. Zdaj pade cela številka, oznaka pa ostane.
  Prava interna številka („interna 214") se nespremenjeno zamenja skupaj
  z oznako.

- **Nekaterih PDF-jev sploh ni bilo več mogoče očistiti.** Če barvnega
  profila ali metapodatkov na sliki ni bilo mogoče dokazano odstraniti, se
  je zagon prekinil brez rezultata – prizadete so bile navadne poslovne
  listine, kot so strani splošnih pogojev, specifikacije in razpisi. Take
  datoteke se zdaj očistijo, opozorilo pa navede mesta, ki so ostala
  odprta: lahko nosijo oznako naprave, ustvarjalca ali zajema. Izvirnik
  ostane kot vedno nespremenjen.

- **Pogodbene vloge so veljale za osebe.** „Ponudnik", „potrošnik",
  „najemnik", „kupec", „naročnika" in okrog štirideset drugih vlognih
  besed so bile zamenjane, kjer so stale brez člena – v naslovih pogodb,
  stolpcih tabel in podpisnih vrsticah. Pogodbeno besedilo brez enega
  samega osebnega podatka je s tem ponekod postalo neberljivo. Te besede
  zdaj ostanejo. Če zraven stoji osebni napotek – nagovor, osebno ime,
  beseda polja, kot je „Kontaktna oseba" –, se še naprej zamenja: „Gospod
  Ponudnik" in „Gospa Kupec" sta imeni. Pogosti priimki, ki so hkrati
  poklici (Bauer, Richter, Koch), s tem pravilom sploh niso zajeti.

- **Skrajšano zapisana ulica je bila spregledana, kadar je hišna številka
  neposredno lepela na piko.** „Schlesischestr.31" ni veljalo za naslov –
  in ker poštna številka zraven svojo oporo dobi iz najdbe naslova, je
  tudi ta ostala. V rezultatu je bilo naslov iz ulice in poštne številke
  spet mogoče sestaviti, in sicer le na nekaterih straneh istega
  dokumenta. Oboje zdaj pade skupaj. Stvarna poimenovanja s pripeto
  številko („Kabelski žleb200") ostajajo nedotaknjena.

- **Naslov čez dve vrstici je bil združen v eno samo ogrado.** Če je v
  bloku naslova poštna številka stala nad ulico, je Maskuro obe vrstici
  povezal v eno najdbo: v rezultatu je izginil prelom vrstice, poštna
  številka pa je pred njim ostala berljiva. Zdaj se vsaka vrstica najde in
  zamenja zase, pisna podoba pa ostane ohranjena. Isti vzrok je občasno v
  naslov potegnil tudi priimek iz vrstice nad njim.

- **Najmočnejša pot PDF ne prevzame več izvirnih predmetov.** Z
  vklopljenim optičnim prepoznavanjem Maskuro vsako stran v celoti na
  novo zgradi iz vidne slike PDFium. V novo minimalno datoteko pridejo le
  ta slikovna stran in na novo ustvarjena, na besedilo OCR omejena iskalna
  plast – ne tuje drevo predmetov s komentarji, prilogami, dejanji,
  plastmi, metapodatki, barvnimi profili ali zasebnimi ključi. To velja
  tudi za vsebino v pojavitvah opomb, vzorcih, pisavah tipa 3, predmetih
  obrazcev in mehkih maskah. Izvorna datoteka ostane nedotaknjena.

- **Obrazi in kode v vgnezdenih grafikah PDF so bili spregledani.** Oba
  detektorja zdaj dodatno vidita popolno izrisano sliko strani. S tem
  detektorje dosežejo tudi portreti in kode QR/črtne kode v opombah,
  vzorcih, glifih pisave tipa 3 in maskah prosojnosti; prepoznana območja
  se – če je vklopljeno – naredijo neprepoznavna pred minimalno gradnjo.
  Zaznava sama ostaja fallibilna.

- **Manjkajoč stroj OCR se je pri PDF-jih končal z notranjo napako.**
  Najmočnejši zagon se zdaj prekine nadzorovano in brez ciljne datoteke,
  namesto da bi izdal nepopolno ali nepreverjeno datoteko.

- **Več pravih stikov in poslovnih vrednosti je padlo skozi, medtem ko je
  bilo zamenjano stvarno besedilo.** Polja imen čez prelome vrstic, imena
  bank in podjetij, pravne oblike, označene identifikacijske številke,
  datumi rojstva ter meje telefonskih, spletnih in IBAN navedb so ožje
  preverjeni. Hkrati pogosteje ostanejo nedotaknjene države v stvarnem
  besedilu, vlogne in vrstne besede, kode artiklov/standardov, stolpci
  števil in navadne kratice.

- **Mešane in zasukane vrstice OCR so bile napačno prebrane.** Negotove
  navpične besede se zdaj krajevno postavijo pokonci in znova preberejo;
  tehnične latinične vrednosti v nelatiničnem besedilu dobijo neodvisno
  angleško pričo. Samostojna negotova posamezna številka se popravi le,
  če se ujemata dva tesna zaporedja številk. Poljske pravne oblike v
  obliki OCR „sp. z 0.0." se v zaprtem sobesedilu preberejo kot „sp. z
  o.o.".

- **Meritev slike je lahko spregledala delno vidne preostale vrednosti.**
  Zdaj preveri prekrivajoče se krajevne izseke, loči belo pisavo ograde na
  črni progi od izvirnih pisav in prenese okvirčke surove slike tudi na
  zasukane, na novo izrisane minimalne PDF-je. Trdni sintetični osnovni
  korpus s tem doseže 1.392/1.392 odstranjenih ciljnih navedb pri 0 lažnih
  alarmih in 0 napakah obdelave. To je korpusno dokazilo, ne splošno
  100-odstotno zagotovilo.

- **Nekomercialni jezikovni modeli se ne ponujajo več.** Šest italijanskih
  in grških različic spaCy pod CC BY-NC-SA 3.0 je odstranjenih iz
  kataloga, prenosa in poti nalaganja; tudi že obstoječe mape modelov se
  prezrejo. Oba jezika namesto tega uporabljata večjezični model z licenco
  MIT.

- **Ime pod „Kontaktna oseba" je bilo odstranjeno le napol.** Če oznaka
  stoji sama na vrstici, pod njo pa „Priimek Ime", je osebno ime ostalo,
  takoj ko je bilo hkrati navadna beseda – iz „Mayer Roman" je nastalo
  „[IME_1] Roman". Take vrstice se zdaj vzamejo v celoti. Oddelek na istem
  mestu („Tehnična notranja služba") ostaja nedotaknjen. Mimogrede
  odpravljeno: „Kontaktna oseba" sploh ni štela za polje imena, čeprav
  „Kontaktna oseba" (drug izraz) to od nekdaj počne.

- **Ime podjetja brez pravne oblike je ostalo, kadar je vmes stala beseda
  panoge.** „Kranzbichler Handels GmbH" je bilo odstranjeno, golo
  „Kranzbichler" tri odstavke pozneje ne – pri „Kranzbichler GmbH" pa je
  šlo. Zdaj deluje oboje. Navadne besede so izvzete: „Deutsche Bank AG" ne
  naredi „nemška" v besedilu za podjetje.

- **Ista vrednost se je v istem dokumentu enkrat imenovala ime, drugič
  kraj.** „Anna Vzorčnaženska … Vzorčnaženska" je dalo „[IME_1]" in
  „[KRAJ_1]" – na drugem mestu manjka osebno ime, in brez njega je nastal
  kraj. Odstranjeno je bilo oboje, a bralo se je kot dve različni stvari.
  Vrednost zdaj obdrži oznako svoje prve pojavitve.

- **Datumske navedbe niso bile več odstranjene.** Datum, sestavljen samo
  iz številk („01.03.2026"), je od zadnje različice padel skozi
  preverjanje, namenjeno imenom, in je ostal v dokumentu – tudi v načinu
  „premakni" in brez vrstice v poročilu o preverjanju. Prizadet je bil le,
  kdor je izrecno vklopil datumske navedbe.

- **Države in celine se ne zakrivajo več.** „Dobava gre v Združene države",
  „Šibkost trga v Aziji", „standard velja v Romuniji" – take navedbe ne
  povedo ničesar o osebi in zdaj ostanejo. Če ime države pripada naslovu
  ali stoji za oznako, kot je „Stalno bivališče" ali „Kraj rojstva", se še
  naprej odstrani. **Mesta niso prizadeta** – „Trenutno sem v Bilbau"
  ostaja navedba o osebi in se še naprej zakriva.

- **Skrajšane besede so postale spletni naslovi.** Če v besedilu stoji
  „oz. nemška" ali „vklj. z", nekateri PDF-ji piko postavijo brez
  presledka – iz tega je nastalo „oz.de" oziroma „vklj.de", veljaven
  naslov s končnico države, in bil odstranjen. Take besedne pare zdaj
  ostanejo. Prave naslove to ne zadeva, tudi brez „www." spredaj ne.

- **Stolpci števil iz bilanc so bili zakriti kot telefonske številke.** V
  poslovnih poročilih in cenikih stojita prejšnje in tekoče leto drug ob
  drugem – „64.518  65.133". To je veljalo za eno telefonsko številko in
  bilo odstranjeno, enako obsegi števil, kot je „12200-23200", in datum s
  sledečo številko. Take številke zdaj ostanejo. Obratno se prava
  telefonska številka zanesljiveje prepozna: oznake „telefon", „faks",
  „mobilni", „interna" in njihove ustreznice v drugih jezikih vmesnika
  zdaj štejejo zraven – doslej je program tam prepoznal le angleške
  besede.

- **Imena v oštevilčeni tabeli so ostajala.** Seznam udeležencev ali
  kadrovska tabela v običajni obliki – glava stolpca, pod njo „1.1
  Auersperg Bernhard Montaža 03.03.2026" – sploh ni bila očiščena: take
  vrstice so izgledale kot seznam postavk ponudbe, v katerem naj stvarni
  izrazi ostanejo. Če glava stolpca nosi osebno oznako („Ime", „Priimek",
  „Surname" …), zdaj vrstice pod njo veljajo za imena. Seznami postavk
  ostajajo nespremenjeno prizanešeni – tudi kadar v glavi dopisa stoji
  „Referent:".

- **Iz enega imena sta včasih nastali dve ogradi druga ob drugi.** Če je
  priimek stal tudi sam v dokumentu, je naknadna obdelava na mestu, kot je
  „Anna Vzorčnaženska GmbH", najprej zamenjala priimek in nato ime – v
  rezultatu je to izgledalo kot dve različni osebi. Zdaj zmaga najdaljše
  znano ime.

- **Izmišljene vrednosti niso stale v nobenem pripisu.** Kdor je izbral
  „Izmisli vrednosti", je dobil rezultat, v katerem je „Anna
  Vzorčnaženska" postala „Greta Mayrhofer" – v pripisu o tem ni stalo
  nič, takoj ko se je v istem dokumentu pojavila le ena anonimna
  zamenjava. S tem izmišljene vrednosti ni bilo mogoče obnoviti, datoteka
  pripisa pa je zamenjavo zamolčala. Najbolj tvegano je bilo tretje: kdor
  bere rezultat, vidi verjetno ime in nima nobenega znamenja, da je
  izmišljeno. Zdaj vsaka zamenjava stoji v pripisu.

- **Pripis je zakrito imenoval „zamenjano".** E-pošta si pripis deli s
  svojimi prilogami, priloga pa se lahko zakrije, medtem ko besedilo pošte
  nosi ogrado. V pripisu je nato za vsa tri mesta stalo isto – „zamenjano"
  –, obnavljanje pa je v prilogi iskalo ogrado, ki je tam ni bilo: proga je
  ostala. Zdaj za vsako najdbo piše, kaj se je tam resnično zgodilo, in
  obe prilogi se obnovita.

- **Vrednosti, ki so stale le na sliki, ni bilo mogoče obnoviti.** V oknu z
  najdbami so stale dvakrat – enkrat kot ograda, ki je v dokumentu ni bilo
  nikjer („Ograda v dokumentu ni bila najdena"), enkrat kot zakrito mesto.
  Prva vrstica je bila golo knjigovodstvo in je odpravljena.

- **Zakrite vrednosti je bilo mogoče obnoviti le enkrat.** Če ista vrednost
  stoji na več mestih, klik obnovi vse – preostale vrstice pa so ostale v
  oknu z najdbami, naslednji klik nanje pa je javil „Ni enolično". Zdaj
  izginejo skupaj.

- **Preklici so manjkali v dnevniku preverjanja, kadar je bil način učenja
  izklopljen.** Kdor je obnovljeno vrednost v oknu Popravi povrnil, ni
  našel dejanja v dnevniku preverjanja, takoj ko so bila vprašanja učenja
  izklopljena – dokazilo je bilo vezano na stikalo, ki zadeva le predloge
  pravil. Pri vklopljenem dnevniku preverjanja se zdaj neodvisno od tega
  vpraša po razlogu in zapiše vrstica.

- **Povlečene datoteke so ostale neočiščene – in niso bile niti
  sporočene.** Kdor datoteko povleče v dokument, namesto da bi jo poslal
  kot prilogo, jo Word ali PowerPoint v celoti shrani v dokument. Ostala je
  nespremenjena v rezultatu, skupaj s prvotnim imenom datoteke in potjo –
  ti v praksi pogosto sami nosijo ime. Take datoteke se zdaj čistijo kot
  preostali dokument.

- **In kjer to ne gre, Maskuro to pove.** Če je v vdelanem predmetu star
  format (Word 97, Excel 97), za katerega čiščenja ni, se zdaj pojavi
  sporočilo POZOR z imenom datoteke. Doslej je bila tiho posredovana
  nespremenjena.

- **Raztrgane besede in kratice so veljale za imena.** Če je beseda v
  PDF-ju deljena na koncu vrstice, pri branju nekaterih datotek nastane
  delec – „letno poroč… ilo", „Obrtnišk…". Taki delci, zlepljene besede
  („VratnaKljučavnicazV") in gole kratice („JY", „FFB") so bili zakriti,
  kot da so imena. Zdaj ostanejo. Ime z isto poškodbo deljenja ostaja
  zakrito, dokler zraven stoji nagovor – imena, ki od doma nosijo veliko
  črko sredi besede (McKenzie, MacDonald, LeBlanc), pa to sploh ne zadeva.

- **Merske navedbe in meseci so veljali za naslov.** V tehnični
  dokumentaciji so bili zakriti „2000 luksov", „1200 Mbit", „1500 vatov",
  „5308 mesto" in „2022 mar" – štiri številke in beseda z veliko začetnico
  so izgledale kot poštna številka s krajem. Poštna številka zdaj šteje le,
  kadar je zraven tudi znak naslova: državna oznaka, oznaka polja, začetek
  vrstice, ulica v vrstici nad njo ali kraj, ki ga na tem mestu vidi tudi
  prepoznavanje jezika. V petih popisih del s tem izginejo 14 napačnih
  zakritij, ne da bi ostal noben pravi naslov.

- **Natančnejše prepoznavanje je zamenjalo preveč.** Vklopljiva stopnja
  „natančnejše prepoznavanje" je v nemških poslovnih listinah stvarne
  izraze imela za imena in kraje – „fotovoltaična naprava", „vpajalna
  točka", „ravna streha", „vhod za osebje" – in zakrila poimenovanja
  podjetij iz tekočih seznamov postavk. Vzrok je bila prizanesljivost:
  njihove najdbe so bile izvzete iz preverjanj, ki prepoznajo vrstico
  postavke ali imenika. Ta prizanesljivost zdaj velja le še za večdelna
  imena, za katera stopnja obstaja – „Anna Huber" v vrstici imenika torej
  ostane prepoznana, posamezna stvarna beseda v vrstici postavke pa pade.
  V tehničnem razpisu to prepolovi napačna zakritja stopnje, ne da bi se
  izgubilo ime.

- **Diagrami so s seboj prinesli svoje popolne izvorne podatke –
  nepreverjene.** Kdor v Word ali PowerPoint vstavi grafikon, program
  tabelo, iz katere je bil izračunan, kot lastno datoteko shrani v
  dokument. Vidnih je le nekaj številk v grafikonu; v tabeli stoji cel
  seznam, skupaj z vrsticami, ki se v grafikonu sploh ne pojavijo. Ta
  tabela je bila doslej posredovana nespremenjena. Zdaj se očisti tudi
  ona, z istimi ogradami kot preostali dokument.

- **Enako za vdelane predmete v datotekah OpenDocument** (ODT, ODS, ODP):
  vstavljen grafikon ali vstavljena tabela sta ostala nedotaknjena.

- **Dokumenti Word: sprotne in končne opombe niso bile očiščene.** Njihovo
  besedilo je v celoti ostalo v rezultatu – tudi imena, naslovi in
  številke računov. Prizadet je bil vsak dokument Word s sprotno ali
  končno opombo. Enako je ostal nedotaknjen samodejni besedilni gradnik,
  ki nevidno potuje z dokumentom.

- **Word: navedbe v spustnih seznamih, komentarjih in opisih slik.** Vnosi
  izbirnega polja (vidni šele ob razprtju), avtor komentarja, opis risbe in
  naslov za ukazom sklica so ostali v rezultatu.

- **Excel: vrtilna tabela je izvorne podatke vpisala še drugič.** Zvezek z
  vrtilno tabelo v njej hrani popolno kopijo ovrednotenih vrstic –
  nevidno, a v datoteki. Ta kopija je doslej ostala nespremenjena, tudi
  kadar je bilo v listu samem vse zamenjano. Prizadeta je bila vsaka
  analiza, posredovana z vrtilno tabelo.

- **Excel: pogovorni komentarji in njihovi avtorji.** Besedilo komentarja
  novejše oblike in seznam komentatorjev – prikazano ime in prijavna
  oznaka, v podjetjih večinoma e-poštni naslov – sta ostala v rezultatu.
  Enak seznam v dokumentih Word prav tako.

- **Samostojno določene lastnosti dokumenta v Wordu in Excelu.** Polja,
  kot sta „Stranka" ali „Opravilna številka", ki jih pisarna doda svojim
  predlogam, doslej niso bila očiščena. V nobenem pogledu niso vidna in
  kljub temu potujejo z vsako kopijo.

- **Preglednice (ODS): spustni seznam celice.** Kot v Excelu od prejšnje
  različice se zdaj čisti tudi v preglednicah OpenDocument, kar se
  prikaže ob razprtju celice. Sklici na druge celice ostajajo pri tem
  nedotaknjeni, da seznam ostane delujoč.

Vsa ta mesta je mogoče kot običajno obnoviti prek pripisa.

- **Sporočila Outlook: poškodovana datoteka je čiščenje trdo prekinila.**
  Nekatere pokvarjene datoteke `.msg` so povzročile prekinitev namesto
  sporočila; zdaj se preberejo, kolikor so berljive.

- **Datoteka pripisa je zdaj berljiva le za vas.** Vsebuje izvirne podatke
  v golem besedilu in je doslej ležala z običajnimi pravicami ob
  rezultatu – na skupni mapi jo je s tem lahko odprl vsak. Na samem
  očiščenem rezultatu se ne spremeni nič; ta naj bi bil vendarle
  posredovan naprej.

- **Naknadno naloženi jezikovni modeli se pred razpakiranjem natančneje
  preverijo.** Prirejen paket – na primer iz podjetniške sprostitve, iz
  katere se streže več delovnih mest – je lahko pri razpakiranju odložil
  datoteke zunaj predvidene mape. Pri običajnem nalaganju se ne spremeni
  nič.

- **Zajemite posnetek zaslona – in takoj je očiščen.** S `Ctrl+Shift+B`,
  prek „Datoteka → Zajemi posnetek zaslona …" ali prek ikone v opravilni
  vrstici povlecite okvir čez zaslon. Kar leži v njem, gre nato po isti
  poti kot vsaka druga datoteka: optično prepoznavanje prebere besedilo
  na zaslonu, imena, naslovi, telefonske številke in e-poštni naslovi se
  zakrijejo, nato pa je slika odprta v urejevalniku, kjer lahko z okvirjem
  naknadno zakrijete, kar je bilo spregledano. Očiščena slika pristane na
  namizju (ali v vaši nastavljeni izhodni mapi); **surov** posnetek se
  nikjer ne shrani in se ob koncu izbriše. Optično prepoznavanje se za ta
  zagon vklopi, tudi če je sicer izklopljeno – na sliki brez njega ne bi
  bilo mogoče najti ničesar. Na Macu sistem ob prvem zajemu vpraša po
  privolitvi „Snemanje zaslona".

- **Na slike je zdaj mogoče risati: pravokotnik, elipso, puščico, besedilo
  in oštevilčene korake.** V šestih barvah in treh debelinah črte, izbirljivo
  s tipkami 1 do 5. Namenjeno je posnetkom zaslona in navodilom: pokazati,
  kaj je pomembno, ne da bi za to odprli drug program. Razveljavitev in
  poznejše prilagajanje z ročicami veljata enako kot za vsako progo –
  anotacijo je torej mogoče premakniti in raztegniti, potem ko je
  postavljena.
  **Risanje izrecno ni zakrivanje.** Narisan pravokotnik je okvir, ne
  proga: kar je pod njim, ostane berljivo in gre naprej z datoteko. Za
  odstranjevanje navedb sta še naprej tu „Zakrij" in „Pikseliziraj";
  risalna orodja zato stojijo v lastni vrstici orodne vrstice, namigovalna
  vrstica pa to pove, dokler je izbrano eno od njih.

- **Obdelana slika gre z enim klikom v odložišče.** „Kopiraj sliko" v
  urejevalniku (ali `Ctrl+C`) jo odloži tako, kot stoji – za vstavitev v
  sporočilo ali pošto zadošča prilepiti. Pot od pritiska tipke do klepeta
  je s tem dolga štiri korake in ne potrebuje mape.

- **Poleg tega označevalnik, senca in prelivi.** „Označi" pobarva
  površino, ne da bi jo prekril – vsebina pod njo ostane berljiva, in prav
  po tem se razlikuje od proge. „Senca" anotacijo dvigne z nemirnega
  ozadja, „Preliv" pusti barvo pojemati v smeri vlečenja; oboje velja za
  vseh šest risalnih orodij.

- **Odpravljeno, preden je koga prizadelo:** nova vrstica orodij bi se pri
  vsakomur, ki je Maskuro že uporabljal, prikazala skoraj prazna –
  zapomnjena razporeditev oken je izhajala iz časa pred tem in ji ne bi
  pustila prostora. Zastarela razporeditev se zdaj zavrže; okno
  urejevalnika nato enkratno stoji v svoji osnovni razporeditvi.

- **Lasten posnetek zaslona je mogoče izklopiti.** Kdor je navajen
  Greenshota, ShareX ali orodja za izrezovanje, pod „Nastavitve → Program"
  izklopi „Zajem zaslonskih slik z Maskurom". Maskuro nato tipkovne
  bližnjice sploh ne prijavi – ostane vašemu orodju –, in preklop velja
  takoj, brez ponovnega zagona. Tako zajeto sliko je še vedno mogoče
  očistiti: Ctrl+V jo prinese iz odložišča v okno.

## 0.10.37-alpha.20260821 – 21. avgust 2026

### Novo

- **Pri anonimiziranju zdaj vsaka najdba nosi svojo številko.** Doslej so se
  vse osebe imenovale `[NAME]`, vsi kraji `[ORT]` – s tem ni bilo več
  mogoče povedati, katero mesto pripada kateri vrednosti, in ni bilo
  ničesar za obnoviti. Zdaj se številke za vsako pojavitev štejejo naprej:
  isto ime na treh mestih stoji kot `[IME_1]`, `[IME_3]` in `[IME_7]`. V
  dokumentu s tem še naprej ni razvidno, katera mesta spadajo skupaj – z
  datoteko pripisa pa je mogoče obnoviti vsako posebej. Datoteka pripisa je
  zato spet izbirljiva tudi pri anonimiziranju; hranite jo ločeno od
  rezultata.
- **Meseci, dnevi v tednu, valute, enote in pravne oblike podjetij v vseh
  48 jezikih dokumentov ne veljajo več za imena ali kraje.** Imena
  koledarja in enot izhajajo iz Unicode CLDR (ustvarjena, ne napisana),
  pravne oblike iz gospodarskega prava držav – tudi večbesedne
  („sp. z o.o.", „Pty Ltd") in postavljene spredaj („株式会社"). Kjer je ime
  meseca hkrati osebno ime (Julij, Avgust, May), odloča oblika: z dnevom ali
  letom zraven datum, sicer ime. Poleg tega nagovori in nazivi, cele
  pozdravne formule, vrste listin in osnovne besede za ulice za 28 jezikov
  z lastnim jezikovnim modelom, kratice zakonov (GDPR, DDV-Z, ABGB, § 6
  odst. 1 t. 27 UStG) ter imena jezikov kot vrednost polja („Jezik:
  nemščina"). Seznami stojijo pod „Pomoč → Seznami besed …".
- **Indija: naslov in koda PIN se prepoznata** – „15 गांधी मार्ग",
  „नई दिल्ली 110001" enako kot „15 Gandhi Marg, New Delhi 110001". Državni
  paket za Indijo je doslej poznal le identifikacijske številke; v
  dokumentih v hindijščini so zato naslovi ostajali.
- **Vsaka očiščena pisarniška datoteka se pred izročitvijo še enkrat odpre
  kot paket.** Besedilni izvleček ne opazi, kadar bi Word, Excel ali
  LibreOffice datoteko zavrnili (podvojen vnos, pretrgan XML, manjkajoč
  del). In proti izvirniku se šteje to, česar čiščenje ne sme nikoli
  spremeniti: strani PDF-ja, listi, vrstice in celice preglednice, prosojnice
  predstavitve. Če preizkus sproži, v rezultatu in poročilu o preverjanju
  stoji opozorilo POZOR – izvirnik ostane nespremenjen.
- **Tudi samodejni način zdaj zakrije celo polje.** V načinu zakrivanja
  proga v kratkih vrsticah – bloku naslova, celici tabele, glavnih podatkih
  – pokrije celo vrstico namesto le najdene vrednosti: proga v dolžini
  besede izda, kako dolga je bila beseda. Oznaka in zneski zraven ostanejo,
  vrstice tekočega besedila (daljše od polovice širine besedila) pa se še
  naprej zakrivajo natančno na besedo, da ime sredi stavka ne počrni
  celega stavka.
- **Obnovljeno spet izgleda kot v izvirniku.** „Obnovi izvirnik" in
  „Prekliči zamenjavo" v urejevalniku PDF zdaj območje zapišeta nazaj
  natanko iz izvorne datoteke – ista pisava, ista velikost, ista barva in
  lega, na skenu iste slikovne točke. Doslej je bilo besedilo znova
  vstavljeno v nadomestni pisavi in je izgledalo prepoznavno obnovljeno.
  Proga prejšnjega zakritja pri tem povsem izgine, namesto da bi bila
  prebarvana belo – barvno ozadje celice v tabeli ostane ohranjeno. To
  velja tudi na zasukanih straneh, za besedilo iz vdelanih predmetov
  obrazcev in za **izpolnjena polja obrazcev**: na za to rastrirani delovni
  kopiji se izsek vrne iz na novo izrisane izvirne strani – tudi tam, kjer
  nobena besedilna plast ne pozna vrednosti polja. Tudi **zamenjane slike**
  v PDF-ju se tako vrnejo – pikselizirane, zamegljene ali povsem
  odstranjene, v celoti ali le povlečen izsek. Le kjer izvorne datoteke ni
  več ob rezultatu, ostane pri dosedanji poti.
- **Zakrite in brez nadomestila odstranjene vrednosti je mogoče obnoviti
  tudi v Wordu, Excelu, PowerPointu in OpenDocumentu.** Doslej je preklic
  tam potreboval ogrado v besedilu – proga ali vrzel nista imeli poti
  nazaj. Zdaj okno z najdbami ponudi vrstici „zakrito" in „odstranjeno",
  takoj ko nedotaknjena izvorna datoteka leži ob rezultatu: Maskuro
  primerja rezultat z izvirnikom in vrednost znova vstavi na mesto proge
  ali vrzeli – skupaj z oblikovanjem, razcepljen tek postane spet celota.
  Velja enako za besedilo, HTML, e-pošto in pisarniške priloge e-pošte; če
  besedilo pošte nosi ogrado, priloga pa progo, se oboje obnovi v enem
  koraku.
- **Tudi priloge PDF v e-pošti ali sporočilu Outlook je mogoče obnoviti** –
  ograde (oštevilčene in anonimne), proge in brez nadomestila odstranjeno.
  Brez platna mesto izhaja iz izvirne priloge; vrednost se vrne natančno
  po pisavah, v vrstnem redu branja izvirnika.
- **Maskirane vrednosti je mogoče obnoviti** – v PDF-ju in v besedilnem
  pogledu. Maska („**** **** **** **** 3201") nikoli ni enolična, dve
  številki nosita isto; zato preklic nikoli ne gre po dobesedni poti,
  temveč izvirnik vpraša, katera vrednost je stala na tem mestu. Doslej te
  vrstice v oknu z najdbami sploh niso bile upravljive.
- **Vdelane slike v Wordu, Excelu, PowerPointu in OpenDocumentu je mogoče
  obnoviti.** Vrednost, zakrita na sliki, se vrne prek svoje vrstice v
  oknu – Maskuro prebere izvirno sliko in obnovi natanko to mesto; zamegljeno,
  odstranjeno ali z obrazi in kodami obdelano sliko obnovi novi vnos
  „Obnovi vdelane slike" v meniju Uredi kot celoto iz izvorne datoteke –
  tudi skozi pisarniške priloge e-pošte ali sporočila Outlook. Slika, ki
  visi kot priloga sama in je bila zakrita z optičnim prepoznavanjem
  besedila, se prav tako vrne prek svoje vrstice v oknu.
- **Izmišljene vrednosti je mogoče obnoviti v besedilnem pogledu.** Doslej
  je okno tam javilo „Ni enolično". Zdaj preklic poišče vrednost v
  izvirniku in na istem mestu v rezultatu zahteva natanko izmišljen
  nadomestek – izmišljeno ime se nikoli ne zamenja dobesedno povsod, saj
  bi lahko nekje resnično stalo.
- **Preklic v Wordu, Excelu, PowerPointu in OpenDocumentu ohrani
  oblikovanje izvirnika.** Če je vrednost stala prek več tekov – „Anna"
  navadno, „Vzorčnaženska" krepko in rdeče –, se je doslej v celoti vrnila
  v prvi tek in izgubila krepko pisavo in barvo. Zdaj se znaki spet
  porazdelijo kot v izvirniku; odstavek Word je nato bajt za bajtom
  prvoten. Enako velja za strani HTML, del HTML e-pošte in telo HTML
  sporočila Outlook (.msg) – pri e-pošti ostane poleg tega ohranjen tudi
  doctype, ki ga je čiščenje doslej tiho odstranjevalo.
- **Besedilne datoteke ohranijo svoje kodiranje.** Čiščenje in obnavljanje
  zdaj `.txt`, `.md" in `.csv` zapišeta v kodiranju, v katerem so bile
  dobavljene – UTF-8 z BOM in brez, UTF-16, Windows-1252. Doslej je
  datoteka Windows-1252 vedno postala UTF-8, datoteka UTF-16 pa se je
  vrnila poškodovana, tudi če v njej ni bilo nič za zamenjati.
- **Obnovljene slike ohranijo svoj barvni način.** Sivinski sken se vrne
  kot sivine namesto kot trikrat večja datoteka RGB, paleta kot paleta,
  črno-belo kot črno-belo – pri celi sliki z istimi vrednostmi kot v
  izvirniku. Velja za slikovne datoteke in za slike v PDF-jih. CMYK in
  16-bitno ostaneta RGB, ker rezultat PNG ne more nositi nobenega od
  obeh.
- **Okvir na sliki obnovi celotno obdelavo, ki se je dotakne.** Pikselizirani
  obrazi nosijo rob okoli prepoznanega okvira; kdor je okvir povlekel le
  čez obraz, je obdržal pikeliziran obroč. Zdaj okvir zraste na povezano
  spremembo glede na izvirnik – zadošča okvir čez predel oči. Ločene proge
  zraven ostanejo; pri v celoti odstranjeni ali povsem zamegljeni
  fotografiji še naprej velja povlečen okvir. Velja za slikovne datoteke
  in slike v PDF-jih.
- **Zakrivne proge čez celo vrstico.** V vrstičnem načinu urejevalnika
  proga zdaj teče od prve do zadnje besede vrstice, ne več le čez zadeto
  besedo – proga v dolžini besede izda, kako dolga je bila beseda, in iz
  šestih znakov pred poštno številko je mogoče uganiti ime kraja. Oznake,
  zneski in stolpci tabele ob vrednosti ostanejo – proga pokrije polje, ne
  vrstice računa. Novo stikalo „Cela vrstica" ob „Besedilne vrstice" spet
  preklopi na natančno besedo, kadar naj sosednje besede ostanejo; izbira
  se zapomni.

### Odpravljeno

- **Slike na straneh HTML in v e-pošti so ostajale nepreverjene – ime v
  logotipu je bilo po čiščenju še naprej berljivo.** Slika, vdelana v
  stran (naslov ``data:``), se sploh ni obravnavala, le njeno nadomestno
  besedilo; logotip v veji HTML pošte (vrstična slika brez imena datoteke)
  je padel skozi filter prilog; pri poimenovani slikovni prilogi pa
  pravilo o sliki „zamegli"/„odstrani" ni imelo učinka. Zdaj vse tri gredo
  po isti poti kot slikovna datoteka: optično prepoznavanje besedila v
  ohranjeni sliki, obrazi, kode, metapodatki in pravilo o sliki. Poročilo
  navede slike – tudi opozorilo, kadar ostanejo nepreverjene brez
  optičnega prepoznavanja –, „Obnovi vdelane slike" in preklic iz okna z
  najdbami pa te slike prav tako poznata.
- **Pisarniške datoteke s sliko sploh ni bilo mogoče očistiti, če optično
  prepoznavanje besedila jezika ni obvladalo.** Na Macu bere sistemsko
  optično prepoznavanje; za hindijščino, grščino, hrvaščino ali litovščino
  tega ne zmore in to tudi pove od nedavnega – pri Wordu, Excelu,
  PowerPointu in OpenDocumentu pa se je zaradi tega prekinilo **celotno**
  čiščenje in datoteka ni nastala. Besedilo bi se pri tem dalo brezhibno
  očistiti; le slika ni bila berljiva. Zdaj se datoteka zapiše kot pri PDF-ju
  in posameznih slikah, v rezultatu pa piše, da slike NISO bile preverjene
  – z razlogom in napotilom na „Upravljanje jezikov".

- **V delovnih zvezkih Excel so ostajala imena v spustnih seznamih.**
  Seznam spustnega polja (preverjanje podatkov) se zdaj čisti kot vsaka
  druga vsebina celice; sklici na obsege celic ostajajo nedotaknjeni, da
  zvezek ostane nepoškodovan.
- **Kjer ograda ni šla vmes, je stala črna proga – zdaj tam stoji krajši
  zapis.** `[ROJ_1]` namesto `[ROJSTNI_DATUM_1]`, in šele ko ne gre vmes
  niti najkrajša oblika, se zakrije. Proga nikomur ne pove, da je tam nekaj
  stalo; kratka ograda to pove. Urejevalnik Popravi je to znal že, samodejno
  čiščenje doslej ne. Datoteka pripisa obe obliki zapisa vodi na isto
  vrednost, da je tudi skrajšano mogoče obnoviti.
- **Prvi klik na „Zamenjaj" je okno Popravi za trenutek zamrznil.**
  Prepoznavanje, ki ogradi da njeno vrsto (`[IME_3]` namesto
  `[IZRAZ_3]`), se je naložilo šele v tem trenutku – približno dve do tri
  sekunde. Zdaj se pripravi v ozadju ob odpiranju okna; izmerjeno je iz
  2289 milisekund nastalo 193.
- **Dve sočasni čiščenji sta lahko isti jezikovni model naložili
  dvakrat** – na primer nadzor mape in glavno okno. Ker vsak model zaseda
  več sto megabajtov, je poraba pomnilnika za kratek čas znašala dvojno.
  Zdaj drugi zagon počaka na model prvega.
- **Kraj v vrstici z datumom se zdaj odstrani tudi, kadar ga jezikovni
  model sam ne prepozna:** kar je zanesljivo najdeno kot poštna številka s
  krajem („3335 Amstetten"), potegne svoje ime kraja s seboj po celem
  dokumentu – kot priimek iz polnega imena. In kratica s številko pred
  imenom („T3 Hofbauer Christian") ostane berljiva, namesto da bi izginila
  skupaj v ogradi.
- **Zaprte tri luknje iz drugega branja pravega naročila:** referent „T3
  Hofbauer Christian" je zaradi kratice „T3" veljal za glavo stolpca in
  ostal berljiv; kraj, ki ga je jezikovni model prek preloma vrstice
  prebral v glavo stolpca, je pogoltnil „Pos." in pustil kupčevo osebno
  ime; ime skupaj z nagovorom („Gospod Robert Köttel") pa je s seboj
  potegnilo le priimek, ne imena – in zato vsak „Gospod". Kratice so zdaj
  gole črke, dvobesedna imena niso glava, najdbe se pred glavo stolpca
  odrežejo, nagovor pa ne šteje k imenu.
- **Kraj v vrstici z datumom („Melk, 05.08.2026") neposredno pod blokom
  naslova je ostal berljiv.** Jezikovni model ga je zlepil s krajem vrstice
  poštne številke v eno najdbo, in ta je v celoti padla proti vzorcu poštne
  številke. Zdaj štrleči preostanek ostane lastna najdba. Najdeno z novim
  drugim branjem rezultata (`werkzeuge/zweitlesung.py`).
- **Mac: sken v jeziku, ki ga sistemsko optično prepoznavanje ne obvlada
  (na primer hindijščina, grščina, hrvaščina, litovščina), je veljal za
  preverjen.** Bralo se je z angleško rezervno rešitvijo, tuja pisava je
  ostala na sliki, poročilo pa je javilo „nič najdeno". Zdaj piše „Slike
  NISO bile preverjene" z razlogom, upravljanje jezikov pa za take jezike
  ne obljublja več optičnega prepoznavanja besedila le zato, ker je zraven
  jezikovna datoteka Tesseract.
- **V PDF-ju ločilo za zamenjano vrednostjo ostane.** Iz „Sprejem
  01.03.2026, odpust 04.03.2026." je doslej nastalo „Sprejem [DATUM_1]
  odpust [DATUM_2]" – vejica in končna pika sta manjkali, pri ogradah
  enako kot pri premaknjenih datumih. Zdaj se odstrani le prepoznana
  vrednost, ne cela beseda do naslednjega presledka; vejica, podpičje,
  pika ali oklepaj za njo ostanejo na svojem mestu, ograda pa čeznje ne
  seže.
- **Ruščina in ukrajinščina sta neopazno tekli s šibkejšim večjezičnim
  modelom**, kadar je manjkal pomožni paket za analizo besednih oblik
  (`pymorphy3`) – lastnih modelov v tem primeru ni bilo mogoče naložiti, in
  „Львів" je postal oseba. Za prepoznavanje imen analiza besednih oblik ni
  potrebna; model se zdaj naloži brez nje, kraji pa so spet kraji.
- **Licenčna obvestila v 16 jezikih so bila na starem stanju.** Tam je še
  pisalo, da se izvorna koda MPL zagotavlja „na zahtevo", QPDF je veljal
  za MPL-2.0, sedem gradnikov je manjkalo v tabeli (wordfreq, Qt, ONNX
  Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), odstavek o spaCy je
  bil v angleščini, na koncu pa je visel angleški nadomestni odsek. Zdaj je
  vseh 18 fassung na stanju nemške: izvorni arhivi trajno pod
  maskuro.com/quellcode/oss/, QPDF Apache-2.0, pot Qt-LGPL, izvor modelov.
  Tudi angleška tabela ima manjkajoče vrstice.

- **Pogodbene besede v rodilniku („des Angebotsinhaltes", „des Anbotes",
  „des Terminplanes") ne veljajo več za kraj.** Posamezna beseda za
  rodilniškim ali dajalniškim členom s sklonsko končnico je vrstna beseda –
  imena krajev se ne sklanjajo („nach Graz"). Če kraj drugje v dokumentu
  stoji brez člena („Burgenland"), ostane prepoznan tudi „des
  Burgenlandes".
- **Premaknjene, maskirane in izmišljene vrednosti so stran rastrirale.**
  Naknadno preverjanje po odstranitvi je v pravokotniku najdbe dovoljevalo
  le ogrado v oglatih oklepajih; premaknjen datum („01.07.2026") ali
  maskirana vrednost („****1234") sta veljala za spregledan ostanek, in
  stran je bila zaradi varnosti pretvorjena v sliko – pri „Zamenjaj" ne.
  Zdaj take strani ostanejo besedilo, obnavljanje iz okna ali okvira pa
  spet vrne izvirnik.
- **Večbesedne nadomestne vrednosti ni bilo mogoče v PDF-ju obnoviti prek
  okna z najdbami.** Izmišljeno ime („Greta Mayrhofer") ali maskiran IBAN
  („**** **** **** **** 3201") sestoji iz več besed; iskanje najdbe je
  primerjalo besedo za besedo in javilo „Ograda v dokumentu ni bila
  najdena". Zdaj se zaporedne besede iste vrstice preberejo skupaj.
- **Po obnovitvi brez nadomestila odstranjene vrednosti je njena vrstica v
  oknu ostala.** Vrednosti, ki jih strategija „zakrij" v načinu ograd
  odstrani brez nadomestila, nimajo ograde, na kateri bi okno lahko merilo
  izginotje. Zdaj se vrstica prečrta, takoj ko vrednost spet stoji v
  dokumentu.

- **Kratične sestavljenke, kot sta „E-pomočnik" ali „podzemna",** ne
  veljajo več za ime.
- **Ostanki deljenja („Sto-") in predolge sestavljenke
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") ne veljajo
  več za ime ali kraj.** V skeniranem besedilu razpisa je bilo tako 28
  besed manj zakritih.
- **Seznami postavk skeniranih ponudb ne veljajo več za imenik.** Dodatni
  prehod za imenike (kratke vrstice) je iz „Kälterohr" in „Außengeräte"
  naredil osebe; zdaj izpusti, takoj ko na začetku vrstice stojijo številke
  postavk, kot je „1.1.5". Vrstice z datumom v poštnih nizih pri tem ne
  štejejo za številke postavk.
- **Glave stolpcev in številke postavk skeniranih ponudb („Pol.", „Pol.
  1.1.3", kratice „E/L/S") so veljale za ime ali kraj.** Kratica sama na
  svoji vrstici, oznaka skupaj s številko in posamezne črke po vrsticah
  niso.
- **Stran je „dihala" v oknu Popravi po odpiranju primerjalne lupe** – pri
  „Širina strani" in „Prilagodi" je merilo odvisno od pogleda, ta pa se
  spremeni z vsakim drsnikom, ki se pojavi ali izgine; vsako naslednje
  dejanje je stran premaknilo za košček. Platno to zdaj samo poravna,
  dokler ne obstoji. Gumbi približevanja, drsnik in tipkovne bližnjice
  zdaj obdržijo sredino slike tudi, kadar se pri povečevanju pojavi
  drsnik.
- **Postrani shranjeni skeni se zdaj berejo pokonci, drobni tisk v velikih
  skenih pa se ne izgubi več.** 24-stranska skenirana ponudba je v vsaki
  nogi ohranila šest bančnih IBAN-ov, matično številko podjetja in ID DDV
  berljive: sken je v PDF-ju ležal zasukan za 90°, optično prepoznavanje
  pa je pri zelo velikih slikah glede na mere slike izpuščalo cele
  vrstice. Zdaj se upošteva vidni zasuk, velike slike pa se berejo v
  prekrivajočih se pasovih – noge so črne.
- **Ulice po osebah z vezajem pred osnovno besedo („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8", „Dr.-Karl-Renner-Straße 12")
  se prepoznajo kot naslov.** V glavi dopisa skenirane ponudbe je tak
  naslov ostal berljiv, ker je vzorec zahteval presledek pred „Straße".
- **IBAN-i iz optičnega prepoznavanja, ki nosijo O namesto 0 ali l namesto
  1, se zdaj prepoznajo.** V drobnem tisku skena optično prepoznavanje
  rado bere številke kot črke; številka je nato imela obliko IBAN, a
  kontrolna vsota ni šla skozi, in je ostala. Če kontrolna vsota spodleti,
  se zdaj poskusi branje s številkami – če se ta izide, je to IBAN.
  Napačne kontrolne številke ostajajo napačne.
- **Delci stavkov, kot so „naslednji kodi na" so veljali za kraj.** Ime
  ali kraj, ki se začne z malo črko, ni ime ali kraj – razen pri plemiških
  delcih („van Gogh", „de Vries").
- **V urejevalniku je ob zakrivni progi ostala zadnja črka**
  („…6", „…t", „…g"), proga pa je imela višino povlečenega okvira namesto
  vrstice. Vzrok: če urejevalnik ni mogel izmeriti strani, je vsak okvir
  štel za „nobena beseda zadeta" in ga uporabil natančno – brez pravila,
  da polovica besede nikoli ne ostane. Enako se je zgodilo pri posameznih
  besedilnih ukazih, ki jih urejevalnik ni znal umestiti. Zdaj poleg vedno
  šteje besedni okvirček: kar okvir bistveno prekriva, pade v celoti.
- **Zadnja črka besede je štrlela čez zakrivno progo.** Proga je bila
  odmerjena po širini pomika iz metrik pisave; če je pisava narisala širšo
  pisavo znaka, je njen ostanek stal ob progi. Okvirček znaka zdaj zajame
  tudi narisano obliko.
- **Sporočilo o pretvorbi strani v sliko je obljubljalo preveč.**
  „Prikaz ostane enak" po rastriranju ne drži: pisava in grafika sta nato
  slikovni točki, datoteka pa postane večja. Sporočilo to zdaj pove – in
  navede tudi drugi razlog za rastriranje (predelava bi stran poškodovala).
- **Besedilo za odstranjeno vrednostjo se je premaknilo do ene pike v
  levo.** Pri predelavi vrstice je bil začetek merjen ob robu pisave,
  nadaljevanje pa ob izhodišču peresa – predbreza prve črke je ostala kot
  napaka („C" 0,5 pt, „I" 1,0 pt). Predelava zdaj dosledno računa z
  izhodiščem peresa; nadaljevanje stoji na desetinko pike na svojem mestu.
- **Avstrijski ID DDV z razmiki („ATU 187 35901") in matična številka
  podjetja brez „FN" pod svojo oznako („Firmenbuchnummer: 30799v") se
  prepoznata.** Oboje je stalo ročno napisano na skeniranem razpisnem
  obrazcu in je ostalo berljivo, čeprav je optično prepoznavanje to
  pravilno prebralo.
- **Postrani ležeče strani PDF so bile po zakrivanju brez razloga
  pretvorjene v sliko.** Preverjanje nepoškodovanosti je izvirnik in
  rezultat primerjalo v zasukanem prikazu, svoja območja zakritja pa je
  računalo nezasukano – na strani z zapisom o zasuku je zato lastno
  zakritje ležalo ob svojem območju in veljalo za škodo. Take strani zdaj
  obdržijo svojo besedilno plast in vektorsko grafiko.
- **Tudi ravne strani so se občasno brez potrebe spremenile v sliko**,
  kadar se je besedilo za ogrado premaknilo za eno piko – dovoljeno, a
  primerjava slike je bila natančnejša od svoje lastne tolerance. Zdaj
  primerja v pol pike in s tem natanko zadene svojo toleranco: do dveh pik
  odmika ne sproži nič, nad tem vse.
- **Navedbe v vdelanih predmetih obrazcev so ostajale.** Nekatere predloge
  glavo ali zaključek dopisa shranijo kot lasten obrazec, ki ga stran le
  vključi. Najdba v njem je bila sicer načrtovana in šteta kot odstranjena,
  a nikoli zapisana – besedilo je ostalo tam, in ga je zajelo le
  rastriranje cele strani. Zdaj se sam obrazec prepiše; obrazec, ki leži
  na več straneh, enkrat samkrat.
- **Strani PDF so bile rastrirane v sliko, čeprav ni ostalo nič
  berljivega.** Sedemstransko ponudbo je to doletelo na šestih straneh;
  narasla je s 73 kB na 3,3 MB in izgubila pisavo v odslikavo. Vzrok so
  bili presledki, ki v dokumentu stojijo večkrat zapored, bralnik pa jih
  javi le enega: besedilo za odstranjeno navedbo se je premaknilo za njeno
  širino v desno, naknadno preverjanje pa je v pravokotniku najdbe našlo
  sosednjo besedo in poseglo po rastriranju. Ohranjeni ostanki vrstic zdaj
  spet stojijo natanko na svojem mestu; ista ponudba se očisti brez ene
  same rastrirane strani (76 kB).
- **Imena ključev in glave računov so veljala za osebe.** V dostopni
  datoteki je bilo zamenjano ime okoljske spremenljivke
  („AWS_ACCESS_KEY_ID"), ne le njena vrednost; na angleškem računu je
  naslov „Bill to" padel kot osebno ime. Oznaka v velikih črkah s
  podčrtaji nikoli ni ime, in beseda v vrstici, ki je kot celota oznaka
  polja, tudi ne – prejemnik pod njo se še naprej najde.
- **Iskanje v oknu Popravi je zastajalo pri velikih straneh PDF.** Vsaka
  črka v iskalnem polju je stran znova rastrirala, čeprav se je spremenilo
  le poudarjanje. Izrisana slika strani zdaj ostane, dokler so stran,
  približanje in pogled isti – enako izvirnik v primerjalni lupi;
  listanje, približevanje in nov stan datoteke se kot doslej znova
  izrišejo.
- **Številke postavk v ponudbah so veljale za naslov IP ali telefonsko
  številko.** Vrstica artikla, kot je „1.3.3.4 … 5-vratno stikalo
  Gigabit", je strukturno številko spremenila v omrežni naslov, ker je
  „Port" štel za tehnično okolje – zdaj šteje le kot samostojna navedba
  („vrata 80"), ne kot del besede. In „1.3.3.6 216879" (številka postavke
  plus artikla) se ne zakrije več kot telefonska številka. Prave naslove
  IP in telefonske številke v takih seznamih se še naprej prepozna.
- **Vrstice artiklov v ponudbah so veljale za poštno številko s krajem.**
  „35252 DIETZEL SALR" (številka artikla skupaj s proizvajalcem) in „1000
  AWG" (količina skupaj s presekom vodnika) sta bila v oštevilčenih
  vrsticah postavk zakrita kot naslov, ker je beseda z velikimi črkami za
  številko veljala za ime kraja v velikih črkah. V seznamih postavk to ne
  velja več; „1080 DUNAJ" v bloku naslova in kraji z malimi črkami
  ostajajo prepoznani povsod.
- **Dodatno prepoznavanje imen je v ponudbah zakrivalo vlogne vrstice in
  glave stolpcev.** „Urna postavka za monterja + E-pomočnika" je 49-krat
  veljala za osebo, glava stolpca „Pol. Oznaka Količina EM" 19-krat za
  kraj – 19-stranski nalog je s tem postal neberljiv. Take najdbe v
  vrsticah postavk zdaj padejo, če same nosijo znake, ki jih nobeno ime ne
  nosi (plus, poševnica, številka, kratica) – tudi kadar se vrstica konča
  z zneskom („Alternativa Trg … - PV/LS AC-napajanje 1 290,00"). Imena v
  imenikih in seznamih – za kar je stopnja namenjena – ostajajo
  nedotaknjena.
- **„Kupec" je v splošnih pogojih vsakega „kupca" naredil ime.** Če je
  dodatno prepoznavanje imen v najdbo zajelo člen, je ta veljal za dvodelno
  ime in ščitil vseh 35 drugih mest iste besede. Zdaj se člen odšteje, in
  „kupec" pade tako kot že prej „kupca".
- **Oznake so veljale za vrednost.** „E-pošta" je bila sedemkrat zakrita
  kot e-poštni naslov, „telefonska številka" in „številka faksa" kot
  telefonska številka. Naslov brez @ in telefonska številka brez številk
  ne štejeta več.
- **Kratice stolpcev iz ene črke („L: 154,50", „S: 0,00") so veljale za
  ime** – 25-krat v ponudbi za sončno elektrarno. Posamezna črka ni ne
  ime ne kraj.
- **Strani PDF so se prevečkrat spreminjale v sliko.** Dva vzroka, oba
  najdena na resničnih ponudbah: če PDF vsako pisavo postavi kot lasten
  ukaz in je pod njo znak presledka brez besedilnega znaka, se je pripis od
  tam naprej premaknil za enega – od odstranjene vrednosti je ostala
  zadnja črka („ŠkodaTopCar**d**"), naknadno preverjanje pa je stran
  upravičeno rastriralo. In beseda, deljena na koncu vrstice
  („Varstvo-podatkov-"), je zaradi oznake vezaja knjižnice za branje
  veljala za premaknjeno. Oboje odpravljeno: vozniška ponudba je šla iz 4
  rastriranih strani na 0, 19-stranski nalog iz 7 na 0 – pisava ostane
  pisava, datoteka ostane majhna.
- **Odpravljena še dva vzroka za rastriranje:** če dokument sam prinese
  pisavo z imenom „F1", so bile ograde nad slikami postavljene v tej
  pisavi in neberljive – zdaj lastna pisava oznak dobi prosto ime. In kjer
  knjižnici za branje manjka presledek sredi dolgega besedilnega ukaza, se
  mesto zdaj dokaže tudi pri večbajtnih pisavah (ista koda, isti znak),
  namesto da bi bilo uganjeno na koncu – prej je zaradi tega ostala črka
  odstranjene vrednosti, preostalo besedilo pa se je vidno premaknilo. K
  temu še dva zadnja primera: ukaz iz več deset presledkovnih pisav je
  pripis speljal stran (ime za tem je ostalo), in velik naslov s predbrezo
  ni našel svojega prvega znaka (ime podjetja je ostalo). **Od devetih
  resničnih ponudb se zdaj ne rastrira niti ena sama stran** – prej jih je
  bilo 30 od 90.
- **Pri rastriranju so slike izginile pod črnim blokom.** Če je treba
  stran pretvoriti v sliko, se izriše iz izvirnika – in ta ne pozna
  čiščenja slik. Doslej je zato pod progo padla *vsaka* slikovna površina
  strani, tudi nedotaknjena. Na ponudbi sta naslov in dva logotipa
  certifikatov tičala v isti sliki glave dopisa; proga je logotipa
  potegnila s seboj. Zdaj se vstavi že očiščena slika: naslov v njej je
  zakrit, vse drugo ostane vidno. Odstranjena slika pusti bel papir
  namesto črnega okvirja.

- **Očiščeni skeni so postali večkratno večji od izvirnika.** Vsaka slika,
  na kateri je bilo kaj zakrito, se je v datoteko vrnila kot
  nestisnjena surova slika – pri 24-stranskem skenu je s tem narasla z
  11,8 na 52,9 MB. Slike zdaj ohranijo vrsto, v kateri so bile: fotografija
  ostane fotografija, faks-sken ostane črno-bel, brezbarvna slika se ne
  odloži kot barvna. Ista datoteka je zdaj velika 15,6 MB, brez vidne
  razlike.

- **Skenirane datoteke PDF iz pisarniških naprav so se vrnile kot vzorec
  prog.** Taki skeni pisavo postavijo kot ostro črno-belo plast čez grobo
  barvno sliko – Canon, Xerox in Kofax svoje datoteke tako gradijo. Pri
  zakrivanju na sliki je bila ta plast napačno zapisana nazaj; rezultat je
  bil neberljiv. Pri šeststranski ponudbi je to zadelo devet od šestnajstih
  slik. Zdaj se pravilno obravnava, v svoji lastni barvi, in zakrita mesta
  v njej resnično izginejo.

- **„Odstrani vse slike" je skenirani strani vzelo besedilo.** Plast
  pisave takega skena je tehnično slika – bila je odstranjena oziroma
  zamegljena skupaj z vsem, ostal je prazen list. Zdaj ostane; logotipi,
  žigi in podpisi se še naprej umaknejo.

- **Preverjanje poškodovanih strani PDF se ne rastrira več zaradi
  drobnega odmika.** Besedilni delec, na novo zasidran pri čiščenju, sme
  zdrsniti do dveh pik; primerjava slike je to kljub temu štela za škodo
  in stran na novo zgradila kot odslikavo – pri tem so se izgubile
  vektorske grafike, kot so tabelarne črte, in čez najdbe je ležala proga
  namesto ograde. Primerjava zdaj dovoli isti majhen odmik kot preverjanje
  besed; prave poškodbe še naprej padejo v oči.

- **Obnavljanje mnogih vrednosti zapored ni več spodletelo na Windows
  zaradi „Dostop zavrnjen".** Kdor je v pisarniški datoteki v hitrem
  zaporedju obnovil veliko vrstic okna, je lahko naletel na kratkotrajno
  zaklenjeno datoteko protivirusnega programa; izmenjava zdaj take zapore
  kratko počaka.

- **Windows pot predaje ukazov je namesto preverjanja končala
  preizkuševalca.** Živo preverjanje poslušajoče instance je na Windows
  pomotoma poslalo pravi Ctrl+C lastni konzolni skupini; zdaj sistem
  vpraša brez signala.

- **Večbesedne oznake polj niso delovale, delovali pa so njihovi delci.**
  „Date of birth", „Bank account", „Cuenta bancaria" in „Numero de
  cliente" so stale na seznamu oznak, a so bile tam razčlenjene na
  posamezne besede in zato nikoli niso zadele; ostali so delci, kot sta
  „de" in „of", ki so odtlej veljali za oznako – „de" pa je sestavni del
  imena („Anna de Vries"). Oboje je odpravljeno: fraze zdaj delujejo kot
  celota, delci so odpravljeni.

- **Nemške pozdravne formule z „ß" so bile kljub vnosu obravnavane kot
  osebno ime.** Pod „Lep pozdrav" ali „S spoštovanjem" je v rezultatu
  stala ograda, čeprav sta obe frazi od nekdaj na protiseznamu. Vzrok je
  bil zapis, ki pri primerjavi nikoli ni prišel skozi; prizadetih je bilo
  osem vnosov v petih seznamih. Zdaj delujejo vsi.

- **„John Staff" je ostal nezamenjan.** Priimek, ki je hkrati angleški
  naslov stolpca, je filter oznak zavrgel skupaj z njim. Naslov ostaja
  nedotaknjen, ime pod njim se spet zamenja.

- **Vrednosti iz označenih polj obrazca ostajajo zaščitene v stopnji
  UI.** Krajevni razsodnik stopnje UI je doslej v presojo dobival tudi
  najdbe, katerih pomen že dokazuje oznaka polja („Datum rojstva:" nad
  vrednostjo) – in jih smel zavrniti. Take strukturno dokazane vrednosti se
  mu zdaj ne predložijo več. Datoteka pripisa pri vsaki zamenjavi zdaj
  dodatno navede pot prepoznavanja („dokaz").

- **Stran PDF, katere ohranjeno besedilo je pri čiščenju utrpelo škodo, se
  zdaj prepozna in na novo zgradi kot odslikava izvirnika.** Pri nekaterih
  pisavah ustvarjalcev so lahko ohranjena besedilna mesta po čiščenju
  izgledala kot črni bloki ali so se besede stikale, čeprav so bile vse
  navedbe za odstranitev pravilno odstranjene. Maskuro zdaj rezultat
  primerja z izvirnikom besedo za besedo in slikovno točko za slikovno
  točko; poškodovana stran se nadomesti s svojo čisto odslikavo – z
  zakrivnimi progami nad najdbami, zakritimi slikovnimi območji in iskanim
  besedilom. Stran ostane berljiva, odstranitev zanesljiva.

### Spremenjeno

- **V prevedenih vmesnikih se zdaj vsak strokovni izraz povsod imenuje
  enako.** Za isto nemško besedo sta glede na okno stali dve ali tri
  vzporedne prevode: dnevnik preverjanja se je v norveščini imenoval deloma
  „Revisjonslogg", deloma „Kontrollogg", brezplačna stopnja deloma
  „Gratisnivå", deloma „Gratisversjon" – podobno v ducatu drugih jezikov.
  Kdor je iskal nastavitev, jo je v naslednjem oknu našel pod drugim
  imenom. Poenoteno je bilo na besedo, ki jo vmesnik tako ali tako
  uporablja najpogosteje.

  Pri tem so na dan prišla mesta, kjer je ena beseda stala za dve
  **različni** stvari: francoščina, grščina in korejščina sta za
  „zakriti" in „maskirati" uporabljali isti izraz – ravno tam, kjer program
  razlaga razliko („Zakrivanje odstrani brez nadomestila, maskiranje
  ohrani obliko"). Oboje je zdaj ločeno. Za švedščino ta odločitev še
  stoji: tam se zakrivanje imenuje „maskera" – ista beseda kot maskiranje.

- **Vprašanje o vrsti uporabe ob prvem zagonu je odpadlo.** Kmalu po
  zagonu se je pojavilo okno („Zasebno ali v podjetju?"), v nastavitvah pa
  je bila o tem vrstica. Oboje ni več, brez nadomestila. Navedba, na kateri
  nič ne visi, napačno prikaže, kdo želi napačno licenco, in kdor je
  pošten, je ne potrebuje; vsakogar je stala en klik v trenutku, ko nihče
  ne misli na vrste licenc. Katera licenca je prava, piše tam, kjer se o
  tem odloča: na strani s cenami, v blagajni in v pomoči. Podjetja, ki
  Maskuro razpošiljajo centralno, vrsto uporabe še naprej določajo prek
  datoteke nastavitev.

- **Napotki k vrsti licence navedejo primer, za katerega gre.** Zasebna
  licenca velja izključno za zasebno rabo; vsako poklicno ali gospodarsko
  delo potrebuje podjetniško licenco – tudi kot samostojni podjetnik brez
  zaposlenih. To je tako stalo v licenčnih pogojih, a ne v programu ne v
  pomoči: tam je bilo vedno govora le o domeni podjetja, ta pa prav tega
  primera ne zajame: računalnik samostojnega podjetnika ne pripada nobeni
  domeni. Napotek ob vnosu zasebne licence to zdaj pove, enako licenčno
  poglavje priročnika in pogosta vprašanja, ki so za to dobila lasten
  vnos. Zaklene se še naprej nič.

- **Poti, ki še niso dostavljene, zdaj ležijo skupaj.** Nastavitve so
  dobile stran „Razvijalec"; tam stojijo največje prepoznavanje (UI) skupaj
  s svojo protipreizkušnjo, katalog seznamov besed in nadzor mape. Vsi trije
  so zgrajeni, a niso preizkušeni v praksi – zato so vidni le z licenco za
  razvijalce, in sicer povsod hkrati: stran, menijski vnosi in učinek pri
  zagonu so vezani na isto odločitev. Brez te licence prej vklopljena
  stopnja UI ostane brez učinka; njena nastavitev se ne izbriše in znova
  velja, takoj ko je pot dostavljena.

### Izboljšano

- **„Kaj se išče" zdaj kaže tri nadaljnje sezname iz prepoznavanja imen.**
  Nagovori, po katerih se naslednja beseda bere kot ime; nazivi in vloge,
  po katerih **še ni** ime („Gospod župan Huber"); in osemdeset večjezičnih
  oznak, po katerih se prepoznajo opravilne, zadevne in spisne številke.
  Vsi trije so delovali od nekdaj, v pregledu pa niso bili vidni.

- **„Kaj se išče" kaže dva doslej manjkajoča seznama besed.** Nagovori in
  nazivi, ki besedo pred sabo naredijo za ime („gospod", „gospa", „dr."),
  ter kratice normirnih organizacij, po katerih Maskuro loči sklic na
  standard, kot je „ÖNORM B 2110", od osebe. Oba od nekdaj vplivata na
  prepoznavanje, v pregledu pa nista stala.

- **Seznami postavk, kazala, naštevanja opreme in sklici na standarde
  ostajajo berljivi.** Prepoznavanje zdaj vidi obliko vrstice: uganjeno
  ime v strukturni vrstici („1.3.1 Energijski zemeljski kabel 1kV"),
  vrstici kazala z vodilnimi pikami, naštevanju („- brezžično polnjenje z
  magnetnim obročem"), nad vrstico količine/cene, v glavi stolpca ali za
  „s pomočjo" je stvarni pojem in se ne zamenja več. Prava imena ostajajo
  zaščitena – z nagovorom, oznako polja in dokazom drugje v dokumentu; na
  merilnem korpusu nobena navedba ni izgubila zaščite. V poslovnem korpusu
  se lažni alarmi s tem znižajo z 25 na 6.

- **Naslovi, oznake obrazcev in pozdravne formule redkeje veljajo za
  imena – v nemščini in angleščini.** Seznami besed, s katerimi Maskuro
  loči stvarne besede od osebnih imen, so znatno zrastli: oznake iz
  računov, obrazcev in uradne pošte („opravilna številka", „namen
  plačila", „stroškovno mesto", „Sort code", „Subtotal"), naslovi
  odsekov prijav in poročil („DELOVNE IZKUŠNJE", „KVALIFIKACIJE",
  „SUMMARY", „REFERENCES"), nemške in angleške vrste listin
  („potrditev naročila", „zapisnik", „Timesheet", „Agreement") ter
  velelne oblike iz navodil („Pošlji…", „Izberi…"). Angleška stran je bila
  pri tem doslej opazno slabo zasedena.

- **Označena polja zdaj povedo, kaj v njih stoji, tudi kadar je oznaka
  sestavljena.** „Naslov dostave", „Naslov računa", „Referentka",
  „Imetnik računa", „Contact person" in „Billing address" vrednost zraven
  ali pod njo zdaj razvrstijo v isto vrsto kot preprosto „naslov" ali
  „ime" – v izpolnjenem obrazcu s kvadratki je to razlika med najdenim in
  spregledanim.

- **V oknu Popravi kolešček miške ob robu strani listа naprej.** Kdor se
  ob koncu strani zvija naprej, pristane zgoraj na naslednji; kdor se ob
  začetku vrne nazaj, spodaj na prejšnji – dokument je tako mogoče
  prevrteti od začetka do konca, ne da bi se dotaknili gumbov strani.
  Tipkovnica (Page Up/Page Down) je to že znala; kratek predah med dvema
  menjavama strani preprečuje, da bi zalet sledilne ploščice ponesel skozi
  pol dokumenta.

- **Sličice strani v oknu Popravi so postavljene sredinsko v predalu.**
  Doslej so lepele na levem robu, in pri raztezanju je rasel le prazen rob
  desno.

- **Orodna vrstica okna Popravi kaže svoje skupine.** Ločilne črte imajo
  zdaj zrak in barvo, „Išči" in „Uporabi na vseh straneh" stojita kot
  lastni skupini ob orodjih, „Uporabi" pa se prikaže le pri vrstah
  dokumentov, kjer lahko kaj doseže. Vsak vnos v vrstici in menijih zdaj
  nosi sliko: „Besedilne vrstice" in primerjalna lupa sta dobili lastna
  simbola (lupa si je svojega doslej delila s „Prej/potem"), poleg tega
  približanje, cela stran, širina strani, sukanje, listanje in tipkovne
  bližnjice. „Odpri s sistemskim programom" zdaj stoji tudi v vrstici ob
  tiskanju – pot od dokončanega rezultata v ustaljen program je en klik,
  ne pot skozi meni.

- **Pri čiščenju odložišča spet piše, da je treba pregledati.** V
  nastavitvah opozorilo zdaj trajno stoji ob stikalu: Maskuro lahko
  spregleda osebne podatke ali navedbe napačno obravnava, prilepljeno
  besedilo je treba pred posredovanjem pregledati. Ob vklopu ga dodatno
  navede sporočilo, zabeleži pa se tudi v izhodnem območju – tudi kadar v
  obvestilnem območju ne teče nobena ikona. Pri vsakem posameznem kopiranju
  se zavestno ne prikaže: opozorilo, ki bi prišlo petdesetkrat na dan, po
  tretjič ne bi bilo več prebrano.

## 0.10.36-beta.1 – 20. avgust 2026

### Izboljšano

- **Tehnični poslovni dokumenti se ne razčistijo več na kose.** Štiri
  zavore prepoznavanja, pridobljene iz enajstih resničnih ponudb in
  naročil: strukturne številke („1.3.1.1") ne veljajo več za naslove IP,
  sklici na standarde („ÖNORM EN 62446") in oznake kod ne več za poštno
  številko ali telefonsko številko, vlogne besede za členom („kupec",
  „naročnika") pa ne več za imena – v splošnih pogojih resnične ponudbe je
  s tem vseh 46 vlognih besed spet berljivih namesto zakritih. Naslovi z
  državno oznako („A 3390 Melk", „D-94032 Passau") se zdaj v celoti
  odstranijo, namesto da bi poštna številka ostala osamljena.

- **Sezname besed je zdaj mogoče v celoti pregledati.** Pod „Pomoč →
  Seznami besed …" je mogoče brskati po krajevno uporabljenih seznamih za
  prepoznavanje in protipreverjanje skupaj z jezikom, namenom, virom in
  vsebino. Sem sodijo tudi seznami Wordfreq, medicinski, osebni in
  centralno vodeni seznami ter zaloge izmišljenih nadomestnih vrednosti.
  Priročnik opisuje katalog v lastnem poglavju.

- **Vrstice dokončanih datotek kažejo uporabljeni jezik prepoznavanja.** Za
  „dokončano" zdaj stoji na primer „nemščina" ali „angleščina", da
  neustrezna samodejna izbira jezika takoj pade v oči. Če je moral
  vskočiti drug nameščen jezik, puščica pokaže oba jezika.

- **Nova primerjalna lupa pri branju takoj pokaže ustrezno mesto v
  izvirniku.** Njen povečan izsek izvirnika sledi kazalcu miške nad še
  vedno urejljivim rezultatom; pri besedilu sledi odstavku. Lupo je mogoče
  uporabljati ob robu okna ali jo izvleči kot lastno, pomanjšljivo/
  povečljivo okno. Njeno povečavo je mogoče nastaviti neposredno med 50 in
  300 odstotki, zapomni pa si tudi vklop. „Ponastavi" tudi povečano ali
  neugodno zasidrano lupo znova postavi levo v uporabno velikost.
  Zamenjane izvirne vrednosti so v lupi rumeno poudarjene, da prizadete
  besede med branjem takoj padejo v oči. Ko je enkrat vklopljena, se pri
  prihodnjih primernih dokumentih znova odpre – tudi po ponovnem zagonu
  programa. Dosedanje stikalo prej/potem ostaja v meniju pogleda. Priročnik
  jo opisuje v lastnem poglavju.

- **Dokazila o odprtokodnih virih in modelih so zdaj natančna za vsako
  izdajo.** Izgradnja paketa ustvari strojno berljiv seznam sestavnih delov
  skupaj z zgoščenimi vrednostmi priloženih licenčnih besedil. Viri MPL,
  izvor modelov, fiksne revizije, spremembe in SHA-256 so dokazani ločeno;
  naknadno naloženi modeli dobijo svoje dokazilo o izvoru neposredno v mapi
  modela. Spremenljivi seznami virov za Tesseract in spaCy so bili trdno
  pripeti. Prodajne izgradnje ostajajo zaklenjene, dokler niso vsi viri in
  priloge modelov objavljeni in preverjeni.

- **Krajevna podatkovna zbirka wordfreq je zdaj v celoti licenčno
  dokazana.** Izgradnja paketa preveri različico 3.1.1, 39 nespremenjenih
  majhnih seznamov, vključno s CJK, in kitajsko znakovno karto glede na
  število, velikost in kontrolno vsoto manifesta. Opomba o kodi Apache-2.0,
  polna licenca CC-BY-SA-4.0, pripis, viri podatkov ter izpuščeni veliki,
  Jieba in nepodprti seznami so dokumentirani v paketu.

- **Pogoste stavčne besede se redkeje pomotoma zakrijejo.** Krajevni
  frekvenčni slovar služi kot dodatna protipreizkušnja, kadar prepoznavanje
  imen glagol, zaimek, člen ali predlog šteje za osebo. Slovar nikoli ne
  odloča sam: samostalniki, večdelna imena ter imena v poljih, seznamih in
  za nagovori ostajajo zaščiteni. Kitajščina, japonščina in korejščina
  uporabljajo izključno natančne meje žetonov svojih že obstoječih
  jezikovnih modelov; za jezike, ki jih ni, se ne uporabi navidezno podoben
  jezik slovarja. Za to se besedilo dokumenta ne prenaša v internet.

- **Tehnični izrazi za izdelke in opremo se zdaj redkeje štejejo za imena
  ali kraje.** Krajevna protipreizkušnja zdaj povezuje pogostost, besedno
  vrsto, tehnično besedotvorje in stvarna področja. Zaradi tega v
  dokumentu ostanejo na primer „Travel-Assistent", „Family-Bonus",
  „WLTP-Wert", „Easy-Start" ter sestavljeni izrazi za številke, imetnike
  ali zavore. Angleške sestavine se preverjajo krajevno tudi v nemškem
  stvarnem besedilu; pravi lastni imeni, nagovori ter polja oseb in krajev
  ohranjajo prednost. Poleg tega „2-letna garancija proizvajalca" ne velja
  več za starost.

- **Licenčne pravice Qt/PySide so zdaj v celoti sledljive.** Programski
  paket vsebuje dodatno celotno besedilo GPL-3.0, natančne različice Qt,
  ponudbo izvorne kode ter nemško/angleško navodilo za zamenjavo
  dinamičnih knjižnic, vključno s krajevnim ponovnim podpisovanjem na
  macOS. Prodajna izgradnja je blokirana, dokler natančni izvorni arhivi
  dostavljene različice niso na voljo na lastni strani z izvorno kodo.

- **Licenca in stanje posodobitev zdaj za vsako stopnjo nedvoumno povesta,
  kaj velja.** V oknu licence in pri nastavitvah posodobitev piše, ali so
  posodobitve vključene, do katerega dne segajo in ali ostaja tekoča
  različica trajno uporabna. Zasebne licence po določenem datumu ne
  namestijo več pozneje izdane različice; tudi na novo prenesen namestitveni
  program po svojem trdno vgrajenem datumu izida prepozna, ali ga vneseni
  ključ zajema. Zadnja zajeta zasebna različica ostaja trajno uporabna. Če
  se konča podjetniška naročnina, pa se konča tudi uporaba in posodobitve;
  preizkusno obdobje in brezplačna stopnja se ne odpreta kot obvoz.

- **Zasebne trajne licence zdaj po ponovni namestitvi najdejo pravo stanje
  programa.** Podpisan katalog različic vodi vse stabilne različice in
  njihove pakete. Če zadnji namestitveni program, ki ga zajema nakup, ni
  več na voljo, se sme namesto tega samodejno uporabiti natanko naslednja
  višja razpoložljiva stabilna različica – nikoli beta ali nightly. Pri
  preveč novi namestitvi lahko stranka namesti dovoljeno stanje ali preide
  na stran za nakup novega obdobja posodobitev; korak nazaj se ne zgodi
  tiho. To velja tudi za upravljane namestitve MSI.

- **Samodejno zakrivanje obrazov je zdaj nedvoumno opisano.** Pomoč programa
  in besedilo o varstvu podatkov funkcijo imenujeta „Prepoznaj in zakrij
  območja obraza" ter jo razmejita od identifikacije, ponovnega
  prepoznavanja, primerjave obrazov, biometričnih predlog ter zbirk oseb ali
  obrazov. Poleg tega jasno opozarjata, da lahko popolnoma krajevno
  prepoznavanje spregleda ali pomotoma označi območja, zato je treba
  rezultat vizualno preveriti. Tudi pri posamično očiščeni slikovni
  datoteki poročilo o rezultatu zdaj navede prepoznana in pikselizirana
  območja obraza; manjkajoče optično prepoznavanje besedila se pri tem ne
  opiše več napačno kot povsem nespremenjena datoteka.

## 0.10.36-alpha.20260820 – 20. avgust 2026

### Odpravljeno

- **Anonimizirane navedbe je zdaj mogoče v celoti obnoviti ne glede na
  vrstni red.** Prejšnji preklic je vrednost iskal prek vidnih besedilnih
  sider. V gostih tabelah, neposredno sosednjih ogradah in nevidnih
  odlagališčih pisarniških/poštnih datotek so ta sidra manjkala; včasih je
  bil pojem zato mogoče obnoviti šele, ko je drugo golo besedilo po naključju
  ustvarilo novo sidro. Zdaj se rezultat in izvirnik primerjata za vsak
  pravi nosilec formata s popolno pripadnostjo, zapišejo pa se le zasedena
  mesta izbrane vrednosti.

- **Imena, poštni naslovi, številke in lastni preizkusni izrazi ostajajo
  jasno upravljivi tudi pri prekrivajočem se prepoznavanju.** Če je isti
  golo besedilo dodeljen dvema vrstama, o tem odloči ograda, ki dejansko
  stoji na mestu najdbe, skupaj s kliknjeno vrstico stranske vrstice.
  Nezasedeni par vrednost/ograda ostaja varno zaklenjen.

- **Posebni primeri pri pošti ne puščajo več skritih ograd.** To velja za
  zadeve, kodirane po MIME, besedilne priloge in imena, ločena s HTML
  označevanjem, v EML in MSG. UTF-8-HTML brez lastne navedbe nabora znakov
  se v datotekah Outlook poleg tega ne prekodira več v mojibake pri vsakem
  koraku urejanja; starejši, že tako zapisani rezultati ostajajo obnovljivi.

### Izboljšano

- **Nova preizkusna matrika sproščanja obravnava vsako anonimno vrstico
  stranske vrstice posamično in namenoma v obratnem vrstnem redu.** Preveri
  vseh 14 besedilnih, pisarniških, spletnih in poštnih formatov ter PDF,
  nato pa še formule, atribute, razmerja, komentarje, glave pošte, priloge
  in notranja stranska odlagališča. Poln zagon na macOS zdaj obsega
  149/149 zelenih preizkusnih skript.

## 0.10.35-alpha.20260820 – 20. avgust 2026

### Izboljšano

- **Jezikovne meritve zdaj resnično primerjajo enako z enakim.** Redni
  merilni korpus vsebuje istih 14 dokumentnih primerov z istimi sedmimi
  besedilnimi in štirimi slikovnimi nalogami v nemščini in angleščini.
  Poln zagon ponovi točno to matriko za vseh dvanajst obstoječih jezikov
  korpusa. Obrazci, tabele, klepeti in drugi še ne popolnoma prevedeni
  strukturni vzorci ostajajo ohranjeni, vendar so izkazani ločeno in se ne
  mešajo več v jezikovne kvote.

- **Poln zagon zapiše za vsak jezik svoje poročilo o meritvi.** Brez
  jezikovnega stikala se namenoma preverjata nemščina in angleščina;
  `--alle-sprachen` zahteva popoln korpus dvanajstih jezikov in se ustavi
  pred prvim dokumentom, če jezik ali primer manjka. Enako poimenovani
  rezultati ležijo v ločenih jezikovnih mapah. Skupno poročilo poleg tehtane
  stopnje najdb navaja tudi netehtano povprečje jezikovnih stopenj.

- **Odprta jezikovna primerjava zdaj kaže tudi svojo dejansko mejo.** V
  rednem zagonu z optičnim prepoznavanjem besedila nemščina in angleščina
  odstranita 218/218 znanih navedb brez lažnega alarma. Polni test z
  optičnim prepoznavanjem besedila in visoko stopnjo odstrani 1.255/1.308
  navedb pri 17 lažnih alarmih; enajst jezikov doseže 100 odstotkov, hindijščina
  51 odstotkov. Prejšnje polne stopnje so temeljile na neenakih količinah
  dokumentov in ciljnih vrednosti ter niso primerljive z novo matriko.

## 0.10.34-alpha.20260819 – 19. avgust 2026

### Odpravljeno

- **Večkrat pojavljajoča se imena ostanejo po enem samem preklicu dosegljiva
  v stranski vrstici.** Doslej je cela vrstica z imenom izginila že po prvem
  obnovljenem mestu `[IME]`. Nadaljnja mesta istega imena so zato ostala kot
  ograda, občasno so bila celo blokirana, dokler niso bila obnovljena druga
  imena. Zdaj vrstica izgine šele po zadnjem mestu; že obnovljeno besedilo se
  kljub temu ne anonimizira samodejno znova. Enako velja za delno uspešen
  skupinski preklic in za orodje za okvir v PDF-jih.

- **„Prekliči zamenjavo" deluje tudi iz pogleda strani pisarniških
  programov.** Vidna stran je tam le begajoč predogled PDF; zdaj se
  pravilno spremeni dokument Word, preglednice ali predstavitve pod njim,
  nato pa se predogled osveži.

- **Preklic zdaj v celoti obnovi tudi skrite ustreznike neke vrednosti.** V
  datotekah Word, OpenDocument, Excel in PowerPoint so lahko iste navedbe
  dodatno v formulah, komentarjih, diagramih, vrednostih polj, nadomestnih
  besedilih in ciljih sklicev; HTML, EML in MSG jih vsebujejo tudi v
  atributih, JSON-ju, glavah sporočil in prilogah. Doslej je glede na format
  del ostal kot ograda. Zdaj je vsako ponujeno navedbo v območju najdb
  mogoče preklicati neodvisno in v poljubnem vrstnem redu. Namerno
  odstranjeni metapodatki, zgodovina sprememb in transportne glave iz
  varnostnih razlogov ostajajo odstranjeni.

- **Pri obnavljanju iz slik ne ostane več črna robna črta.** Desni in
  spodnji rob okvira sta bila pri kopiranju iz izvirnika izmerjena za eno
  slikovno točko preozko. Koordinate se zdaj ujemajo z zakritjem.

### Izboljšano

- **Preizkus sproščanja zdaj pošlje vsako od 22 podprtih pripon datotek
  skozi celoten krožni obhod.** Vsebinsko bogate datoteke se očistijo, vse
  ponujene vrednosti se obnovijo in nato temeljito preverijo. K temu se
  pridružijo resnično upravljanje stranske vrstice, primerjave slik na
  natančnost slikovne točke in viden izris vseh sedmih pisarniških formatov
  v LibreOfficeu. Majhni regresijski testi ostajajo tam, kjer pokrivajo
  lasten napačen ali varnostni primer; dokazano podvojeno preverjanje HTML
  in preizkus odstranjenega črno-belega načina sta odpadla.

- **Popoln merilni korpus te različice je na voljo za ponovno merjenje.**
  Paket vsebuje 294 sintetičnih dokumentov v dvanajstih formatih in
  dvanajstih jezikih, 2.564 znanih navedb, štiri strojno berljive ciljne
  sezname in navodilo. Prenos na strani kakovosti uporablja od vsebine
  odvisno ime datoteke, da brskalniki po pomoti ne dostavijo starejše
  različice iz predpomnilnika.

## 0.10.33-alpha.20260819 – 19. avgust 2026

### Novo

- **Tudi v slikovnih datotekah je zdaj mogoče posamezna mesta obnoviti iz
  izvirnika.** Orodje za okvir „Obnovi izvirnik" kopira slikovne točke na
  istem položaju nazaj iz nedotaknjene izvorne datoteke. Pot ostane
  zaklenjena, če izvirnik manjka ali ima druge mere slike; s tem ni mogoče
  vstaviti vsebine s premaknjenega mesta.

### Izboljšano

- **Ročni zakrivni trakovi se privzeto zaskočijo na vrstice besedila.** Vlek
  čez več vrstic ustvari za vsako vrstico enako visok trak in vmesni prazen
  prostor pusti prost. Za podpise, grafike in druge posebne primere „Prosti
  okvir" preklopi nazaj na poljubno izbrano višino.

- **Urejevalnik razloži naslednji korak neposredno nad dokumentom.**
  Namig se spreminja z vrsto dokumenta in orodjem ter pove, ali se
  pričakuje klik na besedo, izbor besedila ali okvir. Poleg tega orodje,
  kazalec miške in predogled v živo že pred spustom pokažejo, kaj se bo
  zgodilo.

### Odstranjeno

- **Črno-belo izhodno možnost, ki je bila dovzetna za napake, je bila
  odstranjena.** Pri nekaterih PDF-jih so nevidna besedilna polja ostala
  premaknjena glede na rastrirano stran; navidezno zmanjšanje datoteke ni
  bilo vredno tega varnostnega in prikaznega tveganja. Običajno čiščenje
  PDF-jev in ciljno rastriranje problematičnih strani ostajata ohranjena.

## 0.10.32-alpha.20260819 – 19. avgust 2026

### Novo

- **Nadzor mape zdaj resnično teče v ozadju.** Vhod, izhod in pravila so na
  lastni strani pod „Nastavitve". Zažene in ustavi se prek ikone Maskuro v
  opravilni ali menijski vrstici; vnos se prikaže le z ustrezno odklenjeno
  licenco. Okno nastavitev je nato mogoče zapreti in glavno okno spraviti v
  ikono, ne da bi se nadzor ustavil.

- **Urejevalnik Popravi ima zdaj trajno stikalo za način učenja.** Stoji v
  območju najdb in v meniju „Orodja". Ko je izklopljeno, se ne pri
  obnavljanju ne po ročnih popravkih ne pojavljajo vprašanja o oblikovanju
  lastnih pravil. Maskuro si izbiro zapomni za vse odslej odprte dokumente;
  sam preklic pa deluje nespremenjeno.

### Odpravljeno

- **Veliki dodatni model se spet naloži.** Javni pomnilnik je splošno
  privzeto oznako Pythona zavrnil s 403. Prenosi modelov zdaj uporabljajo
  isto izkazano omrežno pot Maskuro kot preostale lastne storitve; skoraj
  596 MB velika datoteka in njena kontrolna vsota ostajata nespremenjeni.

- **Povečana primerjalna lupa ob zasidranju ne obvisi več kot ozek trak
  ob zgornjem robu.** Pred zasidranjem se njeno prosto stanje okna
  normalizira. Shranjeno povečano stanje se pri naslednjem odpiranju prav
  tako vrne v spremenljivo velikost.

- **Skupinski preklic v preglednicah in drugih besedilnih formatih zdaj
  resnično obnovi vse izbrane vrednosti.** Pri anonimiziranih ogradah, kot
  je `[EMAIL]`, je Maskuro doslej vrednosti pisal zaporedoma. Takoj ko je
  bila prva zamenjana, so se številke vseh preostalih najdb pomaknile
  naprej, že izračunan načrt pa je še kazal na stare številke. Zato se je
  vrnil le del izbora. Zdaj se vse izbrane vrednosti istega ograditelja
  zapišejo skupaj in s stabilnimi številkami najdb. Če mesto postane
  enolično šele z drugo obnovljeno vrednostjo, ga Maskuro v istem koraku
  znova preveri – vrstni red izbire zato ni več pomemben.

- **„Prekliči zamenjavo" v PDF-jih zdaj ne izpusti več izbranih vrednosti.**
  Če je ograda stala zelo tesno za drugo besedo ali je v izvirniku vejica
  visela neposredno ob vrednosti, je preverjanje lege sosednjo besedo
  oziroma ločilo lahko pomotoma pripisalo vrednosti. Pri skupnem
  obnavljanju so tako ostale posamezne ograde in vrstice najdb. Preverjanje
  se zdaj ravna po dejanskem začetku besede in upošteva tudi drugačen zasuk
  strani med izvirnikom in rezultatom.

- **Obnovljeno besedilo PDF zdaj obdrži svojo prvotno velikost.** Doslej je
  za merilo služila že pomanjšano ograda; poleg tega je tudi za izvirno
  besedilo veljala zgornja meja 11 pik, namenjena ogradam. Zdaj se izvirni
  okvir in izvirna velikost pisave prevzameta iz izvorne datoteke – tako pri
  orodju za okvir kot pri obnavljanju iz okna z najdbami.

### Izboljšano

- **Opozorilo pred preverjanjem zdaj jasneje pove preostalo tveganje.**
  Izrecno pravi, da lahko Maskuro podatke spregleda ali navedbe napačno
  obravnava, in pred vsako objavo ali posredovanjem poziva k popolnemu
  pregledu in po potrebi ročnemu popravku. To velja tudi za besedilo iz
  odložišča in je v celoti izvedeno v vseh 17 prevodih.

- **Dnevnik preverjanja zdaj tudi znotraj svojih vrstic začne brez
  uporabniškega imena.** Sam dnevnik ostaja izklopljen, dokler ga podjetje
  zavestno ne vklopi. Nato brez dodatne podjetniške nastavitve niti v
  vrstici niti v imenu centralne mesečne datoteke ne stoji uporabniško ime;
  tam za varno ločevanje služi neuganljiv psevdonim, izpeljan izključno iz
  naključne krajevne skrivnosti profila. Licenčno pogovorno okno vklopa ne
  priporoča več, predpostavlja „Brez dnevnika" in vnaprej opozarja na
  svet delavcev, kadrovsko zastopstvo in varstvo podatkov.

- **Zamenjava zdaj poimenuje, kaj zamenjuje.** Označeno ime postane
  `[IME_3]`, kraj `[KRAJ_1]`, telefonska številka `[TELEFON_2]` –
  namesto da bi bilo doslej vse `[IZRAZ_n]`. Vrsta se prepozna ob kliku; če
  ni enolična – navadna beseda ali ime *in* kraj hkrati v izboru –, ostane
  splošni izraz. Ograda, ki trdi napačno vrsto, bi bila slabša od take, ki
  je ne navede.

- **Orodja v oknu Popravi imajo zdaj tipko.** **S** zakrije, **E** zamenja,
  **Z** obnovi izvirnik, **V** pikselizira. V besedilnem pogledu takoj
  delujejo na oznako, v pogledu strani izberejo orodje. **Črke sledijo
  jeziku**, v katerem upravljate program – angleško B/R/O/P, italijansko
  O/S/R/P –, kajti pomagalo za pomnjenje pomaga le v lastnem jeziku. Tipka
  stoji na gumbu.
  Kdor ravno tipka v iskalno vrstico, še naprej piše črke – tam ne
  učinkujejo.

- **Program enkrat na dan javi, v kakšnem stanju teče – brez kakršne koli
  oznake.** S tem štejemo, koliko namestitev je v uporabi in kako se to
  porazdeli med preizkusno obdobje, brezplačno stopnjo in licenco. Ven
  gredo stanje, operacijski sistem, različica, kanal, država, jezik,
  okolje in stopnja prepoznavanja – **nič o vaših dokumentih in nič, po
  čemer bi bilo mogoče prepoznati vaš računalnik**. Dve sporočili od vas za
  nas izgledata kot sporočili dveh različnih ljudi; posamezne poti iz tega
  ni mogoče slediti. Kaj natančno se pošilja in kako se to izklopi, piše v
  besedilu o varstvu podatkov pod točko 5.

- **Postrani vložene strani zdaj same stojijo pravilno.** List, ki je bil
  skeniran postrani, ne da bi bilo to zabeleženo, Popravi prepozna po
  poteku besedila in poravna pogled. Kjer to ne gre – pri čistem skenu
  brez berljivega besedila –, dva nova vnosa v meniju „Pogled" zasukata
  ročno (Ctrl+Shift+L in Ctrl+Shift+R). Zasuka se le prikaz: na datoteki se
  pri tem ne spremeni nič, zakrivanje pa še naprej zadene natanko mesto, na
  katero kliknete.

- **Krajevna izgradnja zdaj v celoti in vidno vodi svoje licence.** Gradnja
  ugotovi dejansko vključene pakete Python, njihova licenčna besedila
  skupaj s pregledom različic položi pod `lizenzen` in se prekine ob
  vrzeli. Tudi Qt, Tesseract in model obraza imajo svoja potrebna besedila;
  pogoji za Maskuro sam so priloženi kot licenčna pogodba.

- **Zdaj je vidno, v kateri ogradi stoji pisalna oznaka.** Kdor klikne v
  ogrado, jo vidi celo zasvetiti – vključno z oklepaji in številko. Gumb
  „Povrni izbor" se je vklopil že prej ob golem kliku; le videti ni bilo,
  katero oznako je zadel. Sijaj ostane tudi, ko se miška premakne k gumbu.

- **Kazalec miške zdaj pove, katero orodje je izbrano.** Štiri orodja si
  delijo isto površino in isto gesto; doslej so vsa izgledala enako.
  Križec pomeni zakrij, zaprta pest zamenjaj, odprta dlan obnovi.

- **Pripravljen pisarniški dokument zdaj zavrne program sam.** Datoteka
  Word, Excel ali OpenDocument lahko prinese navodila, ki ob odpiranju
  potegnejo tujo datoteko z vašega računalnika v svoje besedilo ali
  napolnijo pomnilnik do konca. Oboje je bilo zavrnjeno tudi doslej – toda
  z vgrajeno knjižnico XML, ne z Maskurom. Zdaj o tem odloča program sam,
  ne glede na to, katera različica te knjižnice je v paketu. Pri
  običajnih dokumentih se ne spremeni nič.

### Odpravljeno

- **Okno z najdbami zdaj odstrani zakrite ograde.** Če je bil na primer
  `[IME_1]` v oknu Popravi zakrit, je njegova vrstica z vrednostjo doslej
  ostala na desni, čeprav takega mesta v dokumentu ni bilo več. Vrstica
  zdaj izgine skupaj z zadnjo najdbo; če se ista ograda pojavi še na
  drugem mestu, ostane ohranjena.

- **Pri obnavljanju na zasukani strani zdaj sosednja beseda ostane.**
  Zakrivna proga namerno sega nekoliko čez besedilo; že ta ozek rob je
  doslej lahko zajel sosednjo besedo, na primer „v". Zdaj šteje le
  izrazito prekrivanje, ne stik ob robu.

- **Druga zamenjava v isti vrstici je odnesla naslednji stavek.** Kdor je
  „Referent Kvaksi Blubo prevzame" zamenjal dvakrat zapored, je dobil
  „Referent [KRAJ_1] [KRAJ_2]" – beseda za tem je izginila brez
  nadomestila, brez vsakega opozorila. Vzrok je bila ograda zraven: preostanek
  vrstice se po prvi zamenjavi začne s presledkom, iskanje njegovega
  besedilnega mesta pa je zajelo zaklepajni oklepaj soseda. Nato je bilo
  vse premaknjeno za en znak. Prizadeta je bila vsaka vrstica, v kateri je
  bilo zamenjano ali zakrito dvakrat – tudi pri obnavljanju zraven.

- **Zamenjava ne zakrije več, kadar je ograda predolga.** Če ob besedi ni
  bilo prostora za `[IZRAZ_2]`, je bilo območje doslej prebarvano črno – s
  tem ni bilo več videti niti, da je tam nekoč nekaj stalo, kaj šele
  obnovljivo. Zdaj se zapiše krajši zapis: `[IZR_2]`, `[IZ_2]`, v skrajnem
  primeru `[I_2]`. Tekoča številka ostane na vsaki stopnji – po njej
  obnavljanje mesto spet najde. Le kjer še najkrajša ne pride vmes, ostane
  pri progi.

- **Zamenjava je pustila besedilo stati, če je bilo v isti vrstici že
  zakrito.** Kdor je v oknu Popravi obnovil ime iz izvirnika, mu nato
  zamenjal ime (tam ni bilo prostora – nastala je proga) in nato zamenjal
  priimek, je dobil vstavljeno ogrado, ime pa **ni bilo odstranjeno**. To
  je bilo opaziti šele pri opozorilu druge presoje. Vzrok je bila vrstica
  sama: po prvem zakritju se njen preostanek začne s presledkom, iskanje
  besedilnega mesta pa v tem ni našlo opore. To je prizadelo vsako drugo
  zakritje v isti vrstici.

- **Vklopljeno napredno prepoznavanje brez svojega modela zdaj pade v
  oči.** Kljukica je lahko bila nastavljena, medtem ko je model manjkal –
  nastavitve veljajo za vsako namestitev, model pa leži ob programu.
  Čiščenje je nato teklo brez te stopnje, brez besede o tem. Zdaj kljukica
  pove, da model manjka, rezultat pa nosi opozorilo. Enkrat sprejeta
  izbira pri tem ostane shranjena: takoj ko je model naložen, spet
  učinkuje.

- **Pri anonimiziranju se zdaj obnovi pravi izraz.** Kdor je ročno zamenjal
  več izrazov in nato enega od njih obnovil, je vedno dobil **prvega** – iz
  „Schmidt" je nastal „Müller". Pripis si je za vsako ogrado zapomnil le
  eno zamenjavo, pri anonimiziranju pa vse nosijo isto ogrado; drugi in
  vsak nadaljnji izraz je pri tem odpadel. Zdaj vsaka vrednost dobi svojo
  vrstico – tudi v seznamu zamenjav, ki je bil doslej prekratek.

- **V preglednicah je zdaj mogoče tudi obnavljati.** V CSV-ju ali
  kadrovskem seznamu ograde stojijo neposredno druga ob drugi, ločene le s
  podpičjem. Doslej program tam ni mogel ugotoviti, katera vrednost je
  stala na katerem mestu, in je zavrnil – pri `[IME]` je šlo, pri
  `[ROJSTNI_DATUM]` in `[TELEFON]` ne. Zdaj vrstico razčleni pri vseh
  ogradah. Če mesto ostane resnično dvoumno, še naprej zavrne: napačno
  nazaj zapisana vrednost bi bila hujša kot izostala informacija.

- **In zavrnitev je zdaj vidna.** Stala je v pridušeno sivi barvi ob
  spodnjem robu okna, stavek pa je bil tako dolg, da je bil odrezan –
  izgledalo je, kot da se ne zgodi nič. Stavki so skrajšani, vrstica pa
  nekaj sekund zasveti v opozorilni barvi.

- **Preklic zdaj drži tudi po naslednjem posegu.** Kdor je pri
  anonimiziranju obnovil več mest in nato zamenjal nekaj drugega, je vsa
  obnovljena mesta našel spet zamenjana in moral začeti znova. Vzrok je
  bil pripis: obdržal je vrednost, samodejno usklajevanje za enotne ograde
  pa jo je ob naslednjem zapisu obnovilo nazaj. Zdaj velja: kar obnovite,
  ostane obnovljeno – drugih mest iste vrednosti se to ne dotakne.

- **V besedilnih, Word, Excel in poštnih datotekah zdaj resnično zadošča
  klik v ogrado.** Sporočilo o tem je stalo že v prejšnji različici, gumb
  „Povrni izbor" pa je ostal zaklenjen, dokler ni bilo nič natančno
  označeno – do poti, ki bi izbor nastavila sama, torej sploh niste prišli.

### Odpravljeno

- **Dnevnik preverjanja ne razkrije več imena datoteke.** Datoteke zavestno
  vodi kot razpršeno vrednost namesto v golem besedilu, ker ime datoteke
  razkrije naročnika in predmet spora. To razpršeno vrednost pa je bilo
  mogoče potrditi z ugibanjem – pot ni naključno število. Zdaj v izračun
  vstopa naključna vrednost te namestitve: štetje in razločevanje v
  dnevniku še naprej delujeta, preračun od zunaj pa ne več.

## 0.10.31-alpha.20260819 – 19. avgust 2026

### Izboljšano

- **Tudi v besedilnih in preglednih datotekah ograda ob kazanju zasveti
  rdeče.** Doslej je bil rdeč predogled na voljo le na strani PDF. Zdaj obe
  vrsti pogleda kažeta isto: kar je rdeče, zadene naslednji korak – in za
  obnovitev zadošča klik nanj.

- **Zadošča klik na besedo – pravokotnik nastavi urejevalnik sam.** V oknu
  Popravi je bilo doslej treba čez vsako mesto povleči pravokotnik. Zdaj
  zadošča klik: okvir se postavi okoli besede in ostane oprijemljiv, torej
  ga je še mogoče raztegniti ali premakniti. Ob kazanju z miško beseda že
  zasveti rdeče, tako da vidite vnaprej, kaj bi klik zadel. Kjer ni besede,
  se pravokotnik povleče kot doslej.

- **S pravokotnikom ni več treba natančno meriti.** Kdor povleče
  pravokotnik čez ogrado ali zakritje, vedno misli celotno mesto – nikoli
  le polovico. Okvir zato samodejno zraste na celoto, ki se je dotakne: na
  celo ogrado, celo progo ali, na skenirani strani, na celotno zakrito
  površino. Manjši od povlečenega okvira ne postane nikoli.

- **Zakriva se zdaj po besedah.** Okvir čez polovico besede je doslej
  zakril tudi le polovico – napol zakrito ime pa je še vedno ime. Zdaj
  dotaknjene besede padejo v celoti; sosednja ostane nedotaknjena.

- **V besedilu in preglednicah zadošča klik v ogrado.** „Povrni izbor" je
  doslej zahteval, da natančno označite ogrado skupaj z oglatimi oklepaji.
  Zdaj zadošča, da kazalec postavite vanjo; izbor vidno skoči na celotno
  ogrado.

- **Belgija je dodana kot država.** Izbirljiva v nastavitvah; prepoznajo se
  belgijske telefonske številke, matična številka (Rijksregisternummer, s
  kontrolno številko), številka DDV/podjetja (s kontrolno številko),
  naslovi v obeh uradnih jezikih ter poštna številka s krajem. Doslej so
  belgijske telefonske številke ostajale, ker država sploh ni bila na
  seznamu.

- **Kanal posodobitev zdaj pove, kako zgodaj dobite novosti – ne, kako
  daleč.** Kdor je bil nastavljen na „Testna različica", ni dobil ponujene
  nove predizdaje ali nove stabilne različice in je moral kanal ročno
  zamenjati, da je sploh izvedel zanjo. Zdaj se ponudi tudi vse, kar je
  zanesljivejše: testna različica sprejme testne različice, predizdaje in
  stabilne različice, predizdaja sprejme predizdaje in stabilne. Obratno
  nikoli – pri predizdaji se ne ponudi testna različica, tudi če je novejša.

- **V oknu z nastavitvami so vrstice zdaj bolj razmaknjene.** Štiri strani
  so uporabljale lastne razmike namesto mreže, ki velja v preostalem
  programu; zlasti na strani „Prepoznavanje" so bila potrditvena polja
  zato občutno pretesno postavljena.

### Odpravljeno

- **Izpolnjeni obrazci PDF se pri ročnem urejanju ne prikažejo več
  prazni.** Maskuro za to izključno pretvori nestanovitno delovno kopijo v
  statične strani: vnesene vrednosti postanejo vidne in jih je resnično
  mogoče zakriti; berljiva polja obrazcev ne ostanejo skrita v datoteki.
  Izvirnik ostaja interaktiven in nespremenjen. To zdaj velja tudi za
  dinamične obrazce XFA: PDFium, sposoben XFA, najprej zgradi vrednosti in
  prelome strani, nato pa nastane nov PDF izključno iz statičnih slikovnih
  strani. Če izgradnja XFA spodleti, se datoteka varno zavrne, namesto da
  bi se navidezno prazna odprla.

- **„Prekliči" zdaj deluje tudi med natančnejšim prepoznavanjem.** Doslej
  se je gumb ob kliku zaklenil, izračun pa je tekel naprej do zadnjega
  bloka – pri dolgi datoteki gre za minute brez izhoda, gumb pa je pri tem
  izgledal, kot da je deloval. Zdaj se izračun konča ob naslednjem bloku.

- **V datotekah CSV se imena zdaj najdejo tudi, kadar pred njimi ni
  presledka.** V `P-1000;Brunnthaler, Elisabeth` se kadrovska številka čez
  podpičje prilepi na ime, za prepoznavanje pa je bila to ena sama beseda
  brez imena v njej – v kadrovskih seznamih je zato glede na vrstico ostalo
  celo ime. Telefonske številke, formule in število stolpcev datoteke
  ostajajo nedotaknjeni.

- **Ime, katerega ime in priimek oba nosita vezaj, se zdaj prepozna.**
  „Marie-Luise Habsburg-Ott" je ostalo sredi stavka, medtem ko je bilo
  „Dragan Mitrović" v istem stavku najdeno – ravno kombinacijo dveh
  povezanih polovic je jezikovni model spregledal. Povezane stvarne besede,
  kot sta „Nord-Süd-Verbindung" ali „Software-Entwickler", ostajajo
  nedotaknjene.

## 0.10.30-beta.1 – 18. avgust 2026

### Izboljšano

- **Velikost pisave v besedilnem pogledu je zdaj vidno nastavljiva.**
  Drsnik spodaj desno, ki je doslej približeval le v pogledu strani, v
  oknu Popravi pri besedilnih in pisarniških datotekah nastavi velikost
  pisave (50–300 %) – enako „Povečaj"/„Pomanjšaj" v meniju Pogled.
  Ctrl+kolešček miške je to znal že od nekdaj, a to je vedel le, kdor je
  poskusil; zdaj delujejo drsnik, prikaz in kolešček skupaj.

- **V temnem videzu zdaj na temni delovni površini leži bel list.** Doslej
  je bilo obratno: okoli lista je ostala svetla površina, besedilo samo pa
  je stalo svetlo na temnem. Zdaj list v obeh videzih ostane papirno bel s
  črno pisavo – kot stran PDF, ki v temnem načinu tudi ne postane temna –
  površina okoli njega pa je temna.

### Odpravljeno

- **Po zakritju sredi stavka se preostanek stavka ne izgubi več.** Kdor je
  v oknu Popravi trikrat posegel na isto mesto – zamenjal, zakril, nato
  „Obnovi izvirnik" –, je dobil izbrisan začetek stavka: iz „Za povratna
  vprašanja se obrnite na računovodstvo." je nastalo „na
  računovodstvo.", brez opozorila. Prizadeto je bilo vsako mesto, na
  katerem je bilo že enkrat nekaj odstranjenega sredi vrstice.

- **Napaka pri zagonu ne potegne s seboj več zapiranja.** Ko se je izgradnja
  glavnega okna prekinila, se je nato sesulo tudi zapiranje prek ikone v
  opravilni vrstici – in ta druga napaka je v poročilu o napaki zakrila
  pravi vzrok. Program se zdaj urejeno zapre tudi iz napol zgrajenega okna,
  shranjene nastavitve pa ostanejo nedotaknjene.

- **„Prej/potem" ne skoči več na začetek dokumenta.** Kdor je v oknu
  Popravi skrolal navzdol in za primerjavo preklopil na izvirnik, je
  pristal spet povsem na vrhu – in moral mesto poiskati ročno. Pogled zdaj
  ostane na isti vrstici, v obe smeri.

- **Pri zakrivanju je na vrsticah z obojestransko poravnavo ostala zadnja
  črka.** Kadar besedilni ukaz nariše več pisav, kot jih knjižnica za
  branje javi kot znake – ta v obojestranski poravnavi rada pogoltne
  presledek –, se je pripis premaknil za eno mesto, in iz „Dr. Michael
  Handler aus Willendorf" je nastalo „[NAME] r aus f": dve ostali črki
  sredi očiščenega stavka (najdeno na resničnem zapisniku sveta). Pripis se
  zdaj preveri ob dobesednem besedilu ukaza samega, kjer je to berljivo –
  tam se ne ugiba več.

- **„Lerchenfelder Gürtel 43/12" je bilo odstranjeno le napol.** Vzorci
  naslovov niso poznali besed Gürtel, Kai, Lände, Zeile, Markt niti Graben
  kot osnovne besede za ulico, hišna številka pa ni smela nositi delov s
  poševnico (43/12, hiša/vrata) – številka je ostala ob ogradi. Oboje je
  dopolnjeno; dunajski in salzburški naslovi zdaj padejo v celoti.

- **Shranjene spletne strani po čiščenju ostanejo delujoče.** Naslovi, ki
  jih leno nalaganje shrani v atributih data (`data-lazy-src`,
  `data-lazy-srcset`), so bili zamenjani kot sklici – na pravi občinski
  strani šestnajst kosov – in slike strani se po tem niso več naložile.
  Spletni naslovi tam zdaj ostanejo, kot tudi v `src` in `href`; imena,
  e-poštni naslovi in telefonske številke v atributih data se še naprej
  zamenjajo.

- **Japonski in korejski dokumenti so tekli kot kitajščina.** Prepoznavanje
  jezika je vse tri pisave metalo v isti koš, v japonskem besedilu (brez
  presledkov) in korejskem (s prilepljenimi delci) ni našlo funkcijskih
  besed – in je preprosto vzelo prvi jezik CJK s seznama. Japonski
  zapisnik sveta in korejski zapisnik seje sta bila tako brana s kitajskim
  modelom. Zdaj o tem odloča pisava sama: kana pomeni japonščino, hangul
  pomeni korejščino.

- **Nadaljnji napačni prijemi s terenskega preizkusa v desetih nadaljnjih
  jezikih:** uradi, kot so „Primar", „Gradonačelnik", „Ordfører",
  „Başkanı" ali „Δήμαρχος", ne veljajo več za osebna imena; turške oznake
  polj („Adı", „Soyadı") in grške pogovorne besede („Ωραία", „Βεβαίως") ne
  padejo več; sklepne in paragrafske številke z datumom („323/25-6-2008",
  „27 30.09.2024") niso več telefonske številke; in ostanki stavkov s piko
  („10.An", „T.U.EE", „…pa") se ne zamenjajo več kot spletni naslovi.

### Novo

- **Poročila o preverjanju na željo samodejno.** Kljukica v nastavitvah
  (stran „Program") po vsakem čiščenju sama odloži PDF s poročilom o
  preverjanju – s časovnim žigom v imenu, v lastni mapi, nikoli ob
  rezultatu. Naknadno lista ni mogoče ustvariti; kdor jo potrebuje za
  spis, jo ima s tem vedno. Privzeto je odlaganje izklopljeno.

- **Dnevnik preverjanja je zdaj mogoče vklopiti v programu.** Ob vnosu
  podjetniške licence Maskuro enkrat vpraša, ali naj se dnevnik vodi –
  dokazilo tehta le, če teče od začetka. Poleg tega je v nastavitvah
  stikalo (stran „Program", vidno s podjetniško licenco ali v preizkusnem
  obdobju); vgrajena datoteka nastavitev uprave velja naprej in lahko
  vrednost kot doslej vsili. Lastna vrstica dnevnika „vklopljeno" beleži,
  odkdaj se vodi – s tem je dokazan in podpisan tudi začetek beleženja.
  Privzeto dnevnik ostaja izklopljen.

- **Predal kazalnikov kaže, kaj je storila stopnja UI.** Nova vrstica navede,
  koliko negotovih najdb je model presodil, obdržal in zavrgel ter koliko
  jih je dodatno našel – doslej je bilo njegovo delo nevidno, če niste
  kliknili vsake vrednosti v urejevalniku Popravi. Le številke, nikoli
  vrednosti ali obrazložitve; brez dela UI se vrstica ne prikaže.

- **Obnavljanje zdaj deluje tudi v e-pošti in spletnih straneh.** V `.eml`,
  `.msg` in shranjenih spletnih straneh doslej ograde ni bilo mogoče
  preklicati – aplikacija je to pošteno povedala, prav e-pošta pa je format
  z največ osebnimi podatki. Zdaj preklic tam deluje enako: iz okna z
  najdbami, z označenim izborom in tudi pri anonimiziranih ogradah. Nevidna
  veja HTML e-pošte (tisto, kar Outlook resnično prikaže) se pri tem
  potegne zraven, da pogled in sporočilo govorita isto.

- **Okno z najdbami obnovi tudi anonimizirane vrednosti – za vsako
  posebej.** „Prekliči zamenjavo" je bilo pri anonimiziranih datotekah
  doslej zaklenjeno, ker „[IME]" stoji za vsa imena hkrati. Zdaj preklic v
  izvirniku poišče, kateremu mestu pripada katera vrednost – v PDF-ju po
  koordinatah najdbe, v besedilnem pogledu s primerjavo z izvirnikom – in
  obnovi natanko mesta izbrane vrednosti. Vrstice preostalih vrednosti
  ostanejo.

- **Tudi anonimizirane ograde je mogoče obnoviti posamično.** Pri
  anonimiziranju se vse navedbe neke vrste imenujejo enako – „[IME]" stoji
  za vsako osebo, in doslej je to pomenilo: posamičen preklic ne gre. Zdaj
  se poišče v izvirniku, ki tako ali tako leži ob rezultatu: v besedilnem
  pogledu označite ogrado in izberite „Povrni izbor" – vrne se natanko to
  mesto z natanko njegovo vrednostjo. Če vrednosti iz izvirnika ni mogoče
  nedvoumno razbrati, to aplikacija pove, namesto da bi ugibala. Datoteka
  pripisa pri tem še naprej ne nastane.

- **Okno Popravi se po čiščenju odpre samo.** Nobeno orodje ne najde vsega
  – zato preverjajoč pogled na rezultat sodi v običajni potek, ne v dodaten
  klik. Kdor tega noče, ga izklopi v nastavitvah pod „Prepoznavanje"
  („Po zaključku prikaži rezultat v oknu Popravi").

### Izboljšano

- **Izbira države zdaj privzeto stoji na „samodejno".** Doslej je
  tovarniško veljalo jezikovno območje vmesnika – na nemškem računalniku so
  se tako tudi nizozemski ali francoski dokumenti čistili le z
  nemško-avstrijsko-švicarskimi prepoznavalniki, naslov, kot je
  „Universiteitslaan 1", pa je ostal (najdeno na pravih, javnih zapisnikih
  sveta). Zdaj se izbira države ravna po jeziku dokumenta; kdor je v
  nastavitvah določil trdno izbiro, jo obdrži.

- **Manj napačno zakritega.** Vrsta napačnih prijemov, izmerjenih na
  preizkusnem korpusu in na pravih zapisnikih sej v šestih jezikih,
  odpade: imena podjetij s pravno obliko („Vzorčno podjetje d.o.o.") ne
  veljajo več za osebo ali kraj, temveč za organizacijo; pozdravne
  formule in gole nagovore („Saygılarımızla", „Buenas tardes", samostojna
  „gospa") niso več imena; uradi („župan", „Sindaco", „Alcalde") ostanejo;
  zakonske in sklepne številke („39/2015") in zneski s piko za tisočice
  („330.000") niso več telefonske številke; začetki stavkov, kot sta
  „Envíame" ali „Estarei", ne padejo več kot ime; najdba čez prazno
  vrstico se ne šteje več za ime. Številka računa na računu ostane kot
  navedba dokumenta – številka stranke in opravilna številka pa še naprej
  padeta.

- **Pred nalaganjem modela UI zdaj piše, čemu služi.** Pogovorno okno za
  naknadno nalaganje navede naloge modela – presojanje mejnih najdb,
  iskanje dodatnih imen, predlaganje pravil in profilov – in odkrito pove,
  da ni klepetalni pomočnik. Pogosta vprašanja odgovarjajo na isto vprašanje
  podrobno („Kaj zmore stopnja UI – in česa ne?"), v vseh jezikovnih
  različicah.

### Odpravljeno

- **PDF-ji s poročilom o preverjanju iz ukazne vrstice so zdaj
  preiskovalni.** Pod Windows se je brezglava pot PDF zagnala brez ene
  same pisave – vsak znak je bil narisan kot nadomestni okvirček, list pa
  ni nosil berljivega besedila: kdor je hotel v njem iskati ali kaj
  izkopirati, ni našel ničesar. Zdaj poročilo v tem primeru naloži pisave
  sistema; besedilo je vdelano in berljivo. Poročila iz okna niso bila
  nikoli prizadeta.

- **„Obnovi izvirnik" čez več vrstic skena je puščal črne proge med
  vrsticami.** Na strani, pretvorjeni v sliko, je okvir pospravil le sama
  vrstična pasova; ostanki prejšnjega zakritja so ostali v vmesnih vrzelih.
  Zdaj se povlečeni okvir v celoti razdeli na vrstice.

- **Drugi okvir čez ogrado je puščal rdeč ostanek.** Ograda je skoraj vedno
  širša od besede, ki jo zastopa; kdor je nato zakril isto mesto, je zadel
  le njen začetek – ostal je delček, kot je „RIFF_1]" sredi stavka, in
  obnavljanje je nato vstavilo izvirno besedilo na njegovo mesto namesto na
  mesto besede. Obrezana ograda zdaj vedno pade v celoti.

- **Na zasukani strani je zakrivanje čez ogrado izbrisalo nepovezan
  stavek.** Naknadno narisana ograda je bila pri odstranjevanju zamenjana z
  besedilom pred njo: sama je ostala, prikazalo se je opozorilo „še vedno
  stoji v dokumentu" – na drugem mestu strani pa je brez nadomestila
  izginil stavek, ki z okvirjem ni imel nič skupnega. Ograda se zdaj znova
  najde po svojem besedilu; veriga „zamenjaj, zakrij, obnovi" tako deluje
  tudi na postrani vloženih straneh.

- **Priročnik je v desetih jezikih še svetoval `python3-tk`.** V odpravljanju
  težav je stalo, da pod Linuxom morda manjka tkinter – nasvet iz časa pred
  vmesnikom Qt, ki nikomur več ne pomaga. Zdaj v vseh različicah stoji isti
  odstavek kot v nemščini: manjkajo sistemske knjižnice, ki jih Qt potrebuje
  za prikaz.

- **Licenčno poglavje priročnika je v vseh šestnajstih prevodih stalo na
  starem stanju.** V desetih jezikih je še pisalo, da Windows Server
  potrebuje podjetniško licenco s strežniškim dostopom in da tam ni
  preizkusnega obdobja ne brezplačne stopnje – odkar mesto šteje človeka in
  ne stroj, je oboje napačno. Poleg tega je povsod manjkalo, kdaj se
  zasedeno mesto spet sprosti, da se licenca redno potrjuje in kaj se pri
  tem prenaša, odklep brez interneta pa je stal le v kratki obliki, brez
  treh korakov in brez opozorila, da računalnik nato leto dni deluje brez
  povezave.

- **Sedem odstavkov o dodelovanju je manjkalo v desetih jezikih.** Kdor je
  pomoč bral v danščini, finščini, francoščini, italijanščini,
  nizozemščini, norveščini, poljščini, portugalščini, švedščini ali
  španščini, ni našel niti pogleda strani za pisarniške datoteke niti
  „Ročno zakrij" niti celotnega odstavka o tem, kako se program uči iz
  popravka – skupaj s tabelo s tremi širinami. V „Kaj se prepozna" je istim
  desetim različicam manjkala pot prek oznake v dokumentu.

- **Z vnešeno licenco se program ni več zagnal.** Namesto okna se je
  pojavilo „Programa ni bilo mogoče zagnati" – in sicer pri vsaki licenci,
  ne glede na katero. Vzrok je bila vrstica v prikazu licence, ki opozori
  malo pred iztekom preverjalnega roka; dostopala je do nečesa, kar tam ni
  bilo na voljo. Brez licence – v preizkusnem obdobju in v brezplačni
  stopnji – se napaka ni pojavila, zato je bila opažena šele zdaj.

- **V obrazcu ostanejo imena polj.** „Datum rojstva" in „Naslov" sta
  izginila skupaj s svojo vrednostjo: ograda je stala majhna in rdeča na
  mestu *imena polja*, polje pod njim pa je ostalo prazno. Ime polja ne
  sodi med podatke – zdaj ostane, ograda pa stoji tam, kjer je stala
  vrednost.

- **Naslovi tujejezičnih dokumentov se ne štejejo več za imena.** Nad
  italijanskim obrazcem je stalo „FATTURA", nad španskim „PERMISO
  PARENTAL" – oba sta bila zamenjana. Seznam besed za listine je poznal
  le nemške ustreznice.

- **Iz računa ne izgine več nobena postavka.** „Doplačilo materiala
  1  84,00" je veljalo za naslov in bilo zamenjano z ogrado kraja – dokazilu
  je nato manjkala vrstica. Vrstica, ki se konča z zneskom, je postavka in
  ne naslov; pravi naslovi („Glavna cesta 1  120,00") ostanejo nedotaknjeni.

### Spremenjeno

- **„Nadziraj mapo …" in ukazna vrstica zaenkrat nista več tu.** Obe poti
  sta zgrajeni in delujeta, a nobena od njiju ni preizkušena v praksi:
  nadzor mape ni nikoli videl preizkusa na Windows, ukazna vrstica pa da
  skripti v roke dva ducata stikal, ki pri nobenem uporabniku še nikoli
  niso tekla. Kar nenadzorovano spreminja dokumente, naj tega ne počne
  nepreverjeno – zato sta umaknjena, dokler preizkus ni opravljen. Menijski
  vnos manjka, `--wache` pa ni več v `maskuro --help`.

- **Ostaja, kar samo bere in kar je tako ali tako potrebno.** Iskalni tek
  (`--suchlauf`) in preverjanje (`--nachpruefen`) delujeta v ukazni vrstici
  naprej – ne spreminjata nobene datoteke. Enako zagon prek Raziskovalca,
  kontekstnega menija, odložišča in okna; pri tem se ne spremeni nič.

- **„Vzemi s skenerja" ima zdaj svoje poglavje v priročniku.** Doslej je
  stalo na koncu „Nadziraj mapo". Na Macu je tam svetoval nadzor mape;
  zdaj svetuje, naj se prebrane strani povlečejo v okno.

### Odpravljeno

- **„Obnovi izvirnik" čez več vrstic je uničil razčlenitev.** Okvir čez
  ogrado, nespremenjen naziv delovnega mesta in drugo zamenjavo je celotno
  območje na novo vstavil kot **eno** vrstico – iz treh vrstic je nastala
  ena, kar ni več sodilo zraven, pa je postalo proga. Zdaj se vsaka
  vrstica obnovi zase.

- **In nespremenjeno besedilo pri tem ostane nedotaknjeno.** Kdor povleče
  čez zamenjavo *in* navadno besedilo, dobi nazaj le zamenjavo; preostalo
  se ne dotakne. Pri tem izgine tudi zadnji ostanek stare ograde – prej je
  njen zaklepajni oklepaj ostal sredi stavka.

- **Pri zamenjavi ne ostanejo več ostanki starega besedila.** V krepkem
  naslovu je nato stalo „1. R[IZRAZ_2]ige [IZRAZ_1] … che" – ograda je
  stala tam, poleg pa zlogi izvirnika. Zdaj se pospravi območje, ki ga
  obrišete, ne le okvirčki besed v njem.

- **Anonimna ograda se ne obnovi več napačno.** Pri anonimiziranju vsako
  ime nosi isti `[IME]`. Obnavljanje je vzelo prvi najboljši vnos in ga
  zapisalo na vsako najdbo – iz „Georg Aigner" je nastala „Anna
  Vzorčnaženska", torej napačno ime v dokumentu. Zdaj tam piše, da ni več
  mogoče povedati, katera navedba je bila mišljena; dokument ostane
  nedotaknjen.

### Novo

- **„Obnovi izvirnik" zdaj deluje tudi na rastrirani strani.** Če je bila
  stran pretvorjena v sliko, je doslej sledila zavrnitev: obnovljeno
  besedilo bi prišlo pod sliko strani. Zdaj se mesto na sliki pospravi in
  besedilo se zapiše nanjo – kot ograda na skenu. Vsebina pri tem izhaja iz
  izvorne datoteke, ta pa ni rastrirana.

- **„Povrni izbor" zdaj stoji kot samostojen gumb.** Šlo je že prej, a le,
  če ste po naključju označili ogrado in pritisnili „Zamenjaj izbor" –
  funkcije, ki jo najdete le po naključju, za uporabnika ni.

### Spremenjeno

- **V golem besedilu, CSV in sporočilih Outlook ni več „Zatemni izbor".**
  Ti formati ne morejo nositi proge; gumb je tam vstavil ogrado in to tudi
  povedal – toda gumb, ki počne nekaj drugega, kot se imenuje, tja ne
  sodi.

- **Orodje zdaj pove, kadar na tem mestu nima kaj opraviti.** Ograde ni
  mogoče znova zamenjati, nad zakritjem se ne vstavi ograda, in kjer že
  stoji izvirnik, ni ničesar za obnoviti. Doslej so ti koraki počeli nekaj,
  kar je izgledalo kot učinek, a ga ni bilo.

## 0.10.29-alpha.20260817 – 17. avgust 2026

### Odpravljeno

- **V oknu Popravi zdaj deluje vsak povlečeni okvir.** Kdor je dvakrat
  delal na istem mestu – najprej zamenjal, nato zakril, nato obnovil
  izvirnik –, je njegov drugi in tretji korak brez sledu propadel: še
  oprijemljiv okvir prejšnjega koraka ga je prestregel. Enako pri menjavi
  orodja, kjer je celo tiho še naprej delovalo staro orodje.
- **Preozko povlečen okvir pove, da je preozek.** Doslej je predogled
  besedo obarval rdeče, ob spustu pa se ni brez sledu zgodilo nič.

- **Sporočila Outlook je končno mogoče popraviti.** Datoteka `.msg" je v
  oknu Popravi kazala „Tega formata tukaj ni mogoče prikazati" – bila je
  edini podprt format brez kakršne koli poti do ročnega dodelovanja. Zdaj
  so pošiljatelj, prejemnik, zadeva in besedilo sporočila poimenovano
  prikazani in jih je mogoče označiti in zamenjati kot v vsakem drugem
  besedilnem formatu.

- **„Zamenjaj izbor" v e-pošti ostane pri izboru.** Kdor je označil ime v
  tekočem besedilu, je s tem izgubil tudi pošiljatelja in prejemnika iz
  glav, sporočilo pa je navedlo drugo ogrado, kot je stala v besedilu.
  Zdaj se označena vrednost zamenja povsod – tudi pri pošiljatelju, če
  stoji tam – drugje pa se nič ne dotakne.

- **Okvir čez več vrstic ne uniči več besedila.** Doslej je na enem mestu
  nastala ena sama ograda: od obrezane besede je ostal lepljiv preostanek,
  iz druge vrstice pa je besedilo izginilo brez nadomestila – brez ograde,
  brez proge, le vrzel. Zdaj vsaka vrstica dobi svojo ogrado z vrednostjo,
  ki je tam resnično stala.

- **„Obnovi izvirnik" zdaj deluje tudi po zakritju.** Okno je javilo
  uspeh, besedilo pa se ni nikoli vrnilo: črna proga je štela za oviro,
  zato za obnovljeno besedilo ni bilo več prostora. Proga zdaj umakne
  pot, obnovljeno besedilo pa stoji črno kot navadno besedilo – ne rdeče
  kot ograda.

- **„Obnovi izvirnik" na nedotaknjenem mestu zdaj ne naredi ničesar.**
  Kdor je povlekel okvir čez besedilo, na katerem sploh ni bilo nič
  spremenjeno, je dobil besedilo odstranjeno in znova vstavljeno manjše in
  premaknjeno – javljen pa je bil uspeh. Zdaj tam piše, da ni ničesar za
  obnoviti.

### Novo

- **Zakriva se lahko zdaj tudi v Wordu, Excelu, PowerPointu, OpenDocumentu
  in besedilu.** Doslej je bilo tam na voljo le „Zamenjaj izbor"; proga je
  bila pridržana pogledu PDF, ne da bi za to obstajal razlog. Kjer proge
  ni mogoče prikazati – v čistem besedilu in v sporočilu Outlook – se
  vrednost kot doslej zamenja z ogrado, in tako piše tudi v sporočilu.

- **Označitev ograde jo obnovi.** V besedilnem pogledu (Word, Excel,
  PowerPoint, OpenDocument, besedilo) zdaj zadošča, da ogrado označite in
  pritisnete „Zamenjaj izbor": prvotna vrednost se vrne. Doslej je okno za
  to napotilo na okno z najdbami.

- **Govorci v zapisniku sestanka se prepoznajo tudi, kadar je njihovo ime
  hkrati navadna beseda.** „Gruber: Prevzem sledi naslednji teden." je bilo
  zamenjano, „Bauer: Strinjam se." pa je ostalo – priimek je za
  prepoznavanje videti kot samostalnik. Opozorilne vrstice iste oblike
  ostajajo nedotaknjene: iz „Pozor: Napravo je treba izklopiti." ne nastane
  ime.

- **„Uporabljate najnovejšo različico" je bilo javljeno tudi takrat, kadar
  sploh ni bilo mogoče preveriti.** Če strežnik za posodobitve zahtevo
  zavrne – ker je z istega internetnega naslova prišlo preveč zahtev ali
  ker je sam trenutno moten –, je program obstal na svoji stari različici
  in trdil, da je najnovejša. Prav to se je zgodilo 17. avgusta na Macu:
  0.10.25 je obstala, medtem ko je 0.10.28 že ure čakala pripravljena.

  Zdaj okno pove, kaj se dogaja, navede uro naslednjega preverjanja – in
  izrecno opozori, da **ni** gotovo, ali je lastna različica najnovejša.

  Večinoma vzrok ni v lastnem računalniku: pri mnogih priključkih si
  isti internetni naslov deli veliko strank, strežnik pa jih šteje
  skupaj. Zato Maskuro v tem primeru seznam različic poišče po **drugi
  poti** in nove različice večinoma vseeno najde. Če ostane pri zavrnitvi,
  se strežnika do navedene ure pusti pri miru – tudi če gumb pritisnete še
  enkrat; ponavljanje zaporo le podaljša.

- **Količinske navedbe se ne štejejo več za imena krajev.** V pogodbi o
  delu je „štiridnevni delovni teden" izginil za ogrado kraja – sredi
  predmeta pogodbe. Take besedne zveze iz števila in vezaja
  („tritočkovni načrt", „24-urna dežurna služba") zdaj ostanejo. Naslovi so
  izvzeti: „Zwei-Brüder-Weg" se še naprej zamenja.

## 0.10.28-alpha.20260817 – 17. avgust 2026

### Spremenjeno

- **Licenčna mesta se zdaj resnično štejejo.** Doslej se noben delovni prostor
  ni nikoli prijavil pri licenčni storitvi – licenca za deset mest je tekla
  na poljubno mnogo računalnikih, ne da bi kdo za to izvedel. Novo: računalnik,
  ki zažene program, zasede mesto; mesto se po **sedmih dneh brez zagona**
  samodejno sprosti, tako da pokvarjena naprava ali odšli sodelavec ničesar
  trajno ne blokira.

  Manjši prekoračitev se pri tem **le prikaže in ne zaklene**: do deset
  odstotkov nad kupljenim številom vsi delajo naprej – nov prenosnik poleg
  še prijavljenega starega naj ne bo primer za klicni center. Kdor pride
  poleg tega, pade nazaj na brezplačno stopnjo in je o tem obveščen; računalniki,
  ki so bili tam prej, tega ne opazijo.

- **Kupljena licenca se redno potrjuje.** Če to **30 dni** ne uspe, tako
  dolgo znova velja brezplačna stopnja, dokler ne uspe znova. Nič se ne
  izklopi, teden dni prej pa v oknu stoji opozorilo. Takoj ko računalnik
  spet pride na internet, se to uredi samo. Preizkusno obdobje in
  brezplačna stopnja še naprej sploh ničesar ne javljata – kdor nikoli ne
  kupi, nikoli ne telefonira.

- **„Odkleni brez interneta" zdaj deluje.** Odklep je bil doslej sicer
  preverjen in shranjen, potem pa ga ni nihče več prebral – na pravicah ni
  spremenil ničesar. Zdaj je izhod za računalnike brez dostopa do omrežja:
  velja **eno leto**, nato si s svežo zahtevno kodo pridobite novega.
  Napravo z internetom za to potrebujete enkrat na leto – računalnik sam
  ostane trajno brez povezave.

- **Odklep zdaj poteka tudi iz uporabniškega računa** – pod „Moje licence"
  na spletni strani. Tam poleg tega piše, kateri računalniki so vezani na
  vašo licenco in kdaj se njihova mesta znova sprostijo; tega doslej ni bilo
  nikjer videti. Stran brez prijave ostaja za vse, ki nimajo dostopa do
  trgovine – zahteva pa dodatno e-poštni naslov iz naročila, da sam licenčni
  ključ ne zadošča.

- **In v oknu zdaj piše, kam z zahtevno kodo.** Papirna pot je govorila
  „vnesite na napravi z internetno povezavo" in ni navedla naslova; stran
  za odklep že dolgo obstaja, vendar ni bila od nikoder povezana. Zdaj v
  pogovornem oknu, priročniku in pogostih vprašanjih stoji
  **maskuro.com/lizenz-freischalten** – in na spletni strani pod licenčnim
  ključem.

- **Gumb „Odkleni brez interneta …" ostane viden**, tudi kadar licenca
  trenutno ne velja. Prej je izginil skupaj z njo – torej ravno takrat, ko
  ga potrebujete.

- **„Vsa mesta zasedena" zdaj pove resnico.** Opozorilo se je končalo z
  „Program deluje nespremenjeno naprej"; to ne drži več, če ni bilo
  dodeljeno nobeno mesto. Zdaj tam piše, da do preklica velja brezplačna
  stopnja.

### Novo

- **Ob vklopu čiščenja odložišča zdaj stoji, da je treba pregledati.**
  Sporočilo od takrat navaja isti stavek, ki stoji tudi ob rezultatu
  datoteke: Maskuro ne prepozna v vsakem primeru vseh osebnih podatkov.

  Tu tehta bolj kot drugod. Pri datoteki vidite rezultat, preden ga
  posredujete naprej. Pri odložišču ne – kopirate, prilepite, in očiščeno
  besedilo je že v oknu za pošto. Sporočilo zato izrecno poziva k pregledu
  **prilepljenega** besedila.

  Prikaže se ob vklopu, ne ob vsakem kopiranju: kar bi se pojavilo
  petdesetkrat na dan, po tretjič ne prebere nihče več.

- **„Kopiraj vse" pod seznamom – in „Odstrani vse" se umakne.** Novi gumb
  vse dokončane rezultate naenkrat postavi v odložišče, za prilogo k pošti
  ali lepljenje v drug program. Doslej je to šlo le prek menija in tudi tam
  le za **izbrane** vrstice – kdor je mislil vse, je moral najprej pritisniti
  Ctrl+A.

  Ob tem je vrstica z gumbi na novo urejena: levo stoji, kar nekaj doda,
  desno za presledkom, kar nekaj odvzame. „Odstrani vse" je doslej stalo
  neposredno ob „Dodaj …", in napačen klik je stal cel seznam. Isto pravilo
  velja že od 13. avgusta ob vsaki dokončani vrstici.

- **Delovna mesta brez interneta zdaj dobijo svoje jezikovne modele od
  doma.** Čiščenje je tam vedno delovalo brez povezave – nalaganje
  jezikovnega modela pa ne, model pa tehta več sto megabajtov.

  Uprava datoteke enkrat sestavi na računalniku s povezavo in jih položi na
  skupno mapo, v uvajanje ali na ključek. Mesto se vnese centralno (polje
  `modellquelle` v `vorgaben.json` ali okoljska spremenljivka
  `MASKURO_MODELLQUELLE`). Od takrat naprej se vsako nalaganje najprej
  postreže tam – jezikovni modeli, japonski slovar in visoka stopnja – in
  gre v omrežje le, če datoteka manjka.

  Kontrolne vsote pri tem veljajo nespremenjeno. Skupna mapa v hiši je
  pogosto lažje opisljiva kot izdaja v omrežju; ne sme postati udobnejša
  pot do podtaknjenega modela.

  Kako tak zbir nastane in kako licenca in odklep delujeta brez interneta,
  piše v `OFFLINE.md`.

- **„Obnovi izvirnik" – okvir vrne, kar je bilo odstranjenega preveč.** V
  oknu Popravi je novo orodje: povlecite okvir čez mesto, in besedilo je
  spet tam, kot je stalo v izvirniku.

  To zapolni vrzel, ki jo je pustilo okno z najdbami. Tam je bilo zamenjavo
  mogoče preklicati le, če je bila njena ograda enolična – torej ne pri
  anonimizaciji, kjer „[IME]" stoji ob vsaki tovrstni navedbi, in sploh ne
  pri zakritih mestih, kjer ne ostane nobena ograda. Prav tam se zbirajo
  napačni prijemi: „uporabnik", „inventarna številka", „podpis" se rada
  štejejo za imena.

  Okvir ograde ne potrebuje: **mesto** izhaja iz pravokotnika, **vsebina**
  iz izvorne datoteke – iste, ki jo kaže stikalo prej/potem. Ali je bilo
  anonimizirano ali psevdonimizirano, zato ni več pomembno.

  Obnovljeno besedilo stoji črno, ne rdeče: spet je golo besedilo in ne
  ograda. Vnos s seznama najdb izgine šele, ko njegova ograda **nikjer** več
  ne stoji v dokumentu – če je bila ista vrednost zamenjana na več mestih,
  ostane za preostala.

  Na strani, ki je bila pretvorjena v sliko, orodje odkloni in pojasni
  zakaj: obnovljeno besedilo bi prišlo pod sliko strani in ne bi bilo
  vidno.

### Odpravljeno

- **Pri zapiranju „Podrobnosti" in „Kazalniki" so na zaslonu ostajali
  ostanki slike.** Zaprto se je del vsebine potisnil pod spodnji rob okna
  in tam ostal nad ozadjem, dokler ni bilo nekaj drugega narisanega čeznjo.

  Oba dela imata najmanjšo višino, da sta odprta uporabno velika. Gib pri
  zapiranju pa je znižal le največjo višino – pod svojo najmanjšo višino
  pa se del ne skrči. Vsebina je torej ostala visoka 200 pik, medtem ko se
  je okno že skrčilo na 24; razlika je stala pod robom. Zdaj se najmanjša
  višina za čas giba umakne in nato vrne.

- **Okno je bilo ob ponovnem odpiranju in zapiranju vedno manjše.** Pri
  odpiranju zraste kvečjemu do 92 % višine zaslona; če je prostora malo,
  zraste torej manj, kot je potrebno. Pri zapiranju je kljub temu odštelo
  celoten znesek nazaj. Zdaj vrne točno toliko, kolikor je odpiranje
  stalo.

- **Ostanek zakrite navedbe je lahko ostal viden.** V življenjepisu so od
  „*30.12.1991" v rezultatu ostali berljivi znaki „*30.1" – torej dan in
  začetek meseca datuma rojstva. Program je ostanek celo opazil in stran
  zato pretvoril v sliko; prav to je zadevo poslabšalo, saj s tem ostanka
  sicer ni bilo več mogoče iskati, ostal pa je berljiv – in ni ga bilo več
  mogoče odpraviti.

  Vzrok je ležal med dvema preverjanjema. Ostrejše od obeh preveri, ali v
  površini odstranjene navedbe še stoji nekaj, kar tja ne sodi; svoj izsledek
  javi kot množico znakov, ker se vrstni red branja pri zamenjavi premakne.
  Rezervna možnost, ki taka mesta pred pretvorbo prebarva, je to množico
  znakov iskala kot besedilo na strani – in je nikoli ni našla. Prebarvano
  torej ni bilo nič. Mesto je bilo ves čas znano in se zdaj posreduje
  naprej, namesto da bi se iskalo znova.

  Prizadeta je bila vsaka stran, katere ostanek je našlo izključno to
  preverjanje – ne glede na vrsto datoteke in jezik.

- **Na počez vloženem skenu optično prepoznavanje besedila ni našlo
  ničesar.** Kdor list položi v podajalnik postrani, dobi datoteko, v kateri
  je pisava zasukana za 90 stopinj. Doslej Maskuro v njej ni prebral
  **niti ene** navedbe – in datoteka je bila po tem videti neopazna:
  najdeno ni bilo nič, torej ni bilo javljeno nič, naslov pa je ostal
  berljiv na sliki. Zdaj optično prepoznavanje besedila stran samo
  poravna; na kontrolni sliki spet padejo vse navedbe.

  Odkrito povedani sta dve meji: list, ki stoji **na glavi** (180 stopinj),
  se še naprej ne prebere, pri zelo slabem skenu pa poravnava ne pomaga –
  tam je premalo berljivega, da bi sploh določili lego. Vsaka slika zato
  potrebuje približno petino več časa.

### Spremenjeno

- **„Samodejno namesti" zdaj pomeni, kar dejansko naredi.** Kljukica v
  nastavitvah je obljubljala več, kot je izpolnila: novo različico naloži
  sama in zažene namestitev – ta pa poteka **vidno** in zahteva potrditev,
  pod Windows vključno s povratnim vprašanjem nadzora uporabniškega računa.
  Kdor je prebral „samodejno", je pričakoval računalnik, ki se čez noč
  posodobi sam, in zjutraj je stal pred čarovnikom za namestitev. Kljukica
  se zdaj imenuje „Samodejno naloži posodobitve in zaženi namestitev", s
  stavkom pod njo, kaj to pomeni. Pri vedenju se ne spremeni nič – da se
  Maskuro ne zamenja neopazno, je namerno in ostaja tako.

## 0.10.27-alpha.20260817 – 17. avgust 2026

### Novo

- **Novo: `--ersetzen` za povezavo s pisarniško programsko opremo.** Rezultat
  stopi na mesto izvorne datoteke, namesto da bi nastal zraven. S tem
  odjava in prijava dokumenta v pisarniško programsko opremo („Odpri in
  uredi" v e-spisu) delujeta brez vsakega vmesnika: programska oprema
  datoteko izroči in jo dobi na istem mestu očiščeno nazaj.

  **To stikalo izniči prvo temeljno pravilo**, zato obstaja le na ukazni
  vrstici – ne v oknu – in le, če ga vaša uprava sprosti (vnos `ersetzen` v
  datoteki nastavitev). Brez sprostitve se klic prekine in pove zakaj; tiho
  ustvariti drugo datoteko bi bila hujša napaka, saj bi se tako nazaj
  prijavila nespremenjena.

  Zapiše se najprej sosednja datoteka; šele ko je dokončana, stopi na
  mesto vira. Prekinitev ali napaka tako izvirnik pusti **bajt za bajtom
  nespremenjen** in ne pusti nobenega delca za sabo. V dnevniku
  preverjanja zamenjava stoji kot lastno polje – preverjevalec mora vedeti,
  da neočiščena različica tu ne leži več.

- **Priročnik zdaj razlaga opozorilo Windows ob prvem zagonu.** Nov prvi
  odsek „Windows opozori ob prvem zagonu – kaj storiti", z dvema slikama
  in tremi koraki: „Več informacij" je majhna povezava, ne gumb – prav na
  tem obtiči večina –, nato „Vseeno zaženi".

  Da tam piše „Neznan izdajatelj", je celotna izjava opozorila: paketi so
  trenutno dostavljeni brez potrdila. Menimo, da je pravilneje to
  pojasniti, kot pa prikriti.

- **Povratna pot zdaj opazi, kadar besedilo in pripis ne sodita skupaj.**
  Kdor odgovor prilepi v drugo opravilo, je doslej dobil tuja imena v
  pravem besedilu – brez napake, brez sporočila, le napačno. Maskuro si
  zdaj zapomni, katere ograde je sploh ustvaril zadnji zagon, in prijavi
  vsako, ki ne sodi zraven. Če nobena od njih ne izhaja iz zadnjega
  zagona, se ne vstavi nič, okno pa pove zakaj – namesto da bi kot doslej
  domnevalo potekel rok.

  **Meja ostaja, in stoji tudi v priročniku:** ograde so oštevilčene po
  zagonu, prvo ime se torej v vsakem dokumentu imenuje `[IME_1]`. Če tuje
  besedilo nosi le take ograde, zamenjave ni mogoče prepoznati.

- **PDF je zdaj mogoče izdati črno-belo.** Kljukica pri načinu delovanja
  vsako stran spremeni v črno-belo sliko – z nevidno besedilno plastjo pod
  njo, torej še naprej berljivo in iskano. Za pošiljanje prek beA in
  podobnih poti s trdimi omejitvami velikosti: prek našega merilnega
  korpusa v povprečju **68 % manjše** (ukazna vrstica: `--monochrom`).

  **Koliko to prinese, je odvisno od dokumenta** – in to stoji tudi ob
  kljukici: skenirano in slikovno vsebino močno skrči, vitek besedilni
  dokument brez vdelanih pisav pa lahko celo naraste. Preizkusite na eni
  datoteki, preden vklopite za cel sveženj.

  Cena: vsaka stran se na novo izračuna – pri tisoč straneh to traja
  minute. In slike izgubijo vse med črno in belo; za besedilo je to
  vseeno, za fotografijo ne.

- **Seznam najdb v oknu Popravi zdaj šteje zraven.** Nad seznamom stoji „5
  najdb", in takoj ko filtrirate, „1 od 5 najdb". To je razlika med „sem
  filtriral" in „je pet, in videl sem vse" – prijem, s katerim se preveri,
  ali je bilo ime resnično zamenjano povsod.

- **Dnevnik preverjanja je zdaj mogoče preiskati in filtrirati.** Pogled
  pod „Datoteka → Dnevnik preverjanja" je doslej imel tabelo in sicer
  nič – pri mesecu s tri tisoč zagoni je bilo videti, da se je zgodilo
  mnogo, ne pa kaj.

  Novo so **iskalno polje**, **trije filtri** (postopek, rezultat, vrsta)
  in **listanje**, poleg tega trije stolpci, ki jih prej ni bilo:
  **postopek** (zakrito ali zamenjano), **zaupanje** in **trajanje**. Nad
  seznamom stoji, koliko je ravno vidnega in koliko filter skrije.

  „Shrani kot CSV …" zdaj izda **to, kar je prikazano** – kdor je
  filtriral, dobi filtrirano, sporočilo pa navede število.

  Črtica pri zaupanju ali trajanju pomeni, da za to vrstico ni bilo
  ničesar izmerjenega – na primer, ker je starejša od te funkcije. Te
  vrednosti se **ne** izračunajo naknadno. Filtra po uporabniku še naprej
  ni; posamezno vrstico iskanje kljub temu najde.

### Odstranjeno

- **Opozorilo o preglednosti v oknu „O tem programu" je spet odstranjeno.**
  Stalo je tam od 0.10.22-beta.1 in povedalo, da je bila aplikacija
  razvita s podporo umetne inteligence. Zahtevano ni nikjer, in prav v
  aplikaciji za varstvo podatkov ga je marsikdo bral kot izjavo o
  delovanju – torej kot da dokumenti gredo k spletni storitvi. Čisti se še
  naprej izključno na lastnem računalniku; to stoji tam, kamor sodi, v
  zavihku „Varstvo podatkov".

### Odpravljeno

- **Program je svojo lastno ikono zamenjal za slabšo.** Kdor je vpisal
  kontekstni meni iz programa, je nato imel v opravilni vrstici drug ščit
  kot po namestitvi – podoben, a z levo poravnanimi namesto sredinskimi
  progami in vidno grobejši. Za tem se je skrivala zasilna rešitev: če
  program ne najde predloge ikone, si jo nariše sam. Zamišljeno je bilo
  za primer, ko ikon **sploh ni**; dejansko je risal tudi, kadar so
  priložene že zdavnaj ležale – in jih prepisal. V različici, nameščeni
  prek namestitvenega programa, predloge ni, torej je to zadelo vsakogar
  tam. Obstoječe ikone zdaj ostajajo nedotaknjene.

  **Že prizadete namestitve pravilne ikone ne dobijo nazaj same od sebe** –
  za to enkrat znova namestite.

- **„Objektna oznaka: OB-4711-22" je veljala za prijavno ime.**
  Prepoznavalnik uporabniških imen je svoje oznake preverjal brez besedne
  meje pred njimi – torej je zajel **vsako** besedo, ki se konča na eno od
  njih: objektna oznaka, oznaka vozila, oznaka naprave. Vrednost za njo je
  bila odstranjena, čeprav s prijavnim imenom nima nič skupnega.

  Sestavljenke, ki so resnično mišljene – „uporabniška oznaka", „prijavna
  oznaka" –, stojijo posamično na seznamu in se še naprej najdejo.

- **V angleščini, grščini, japonščini in korejščini je v rezultatu stalo
  šestnajst ograd v nemščini.** Kdor je vmesnik nastavil na enega od teh
  štirih jezikov, je za novejše vrste podatkov v dokument dobil zapisane
  nemške oznake – iz gesla je nastalo `[ZUGANGSDATEN_1]` namesto
  `[CREDENTIALS_1]`, iz diagnostične šifre `[DIAGNOSESCHLUESSEL_1]`
  namesto `[DIAGNOSIS_CODE_1]`. Prizadeti so bili zdravje, diagnoza,
  zdravljenje, diagnostična in zdravilna šifra, veroizpoved, sindikat,
  politično mnenje, kazensko pravo, dostopni podatki, uporabniško ime,
  podatki kartice, koordinate, poklic, znesek in lastnost.

  Preostalih 44 jezikov te napake nikoli ni imelo: svoje oznake dobijo iz
  jezikovnih datotek, v katerih so te vrste od začetka stale. Prav ti
  štirje jeziki iz drugega razloga vodijo lastne tabele – njihova pisava
  ne preživi nabora znakov PDF, zato tam stojijo latinične oznake –, in v
  teh tabelah so nove vrste preprosto manjkale.

  Opaženo je bilo pri prevajanju kataloške strani: spletna stran je
  angleškim bralcem obljubljala oznake, ki jih program ni pisal. Preizkusni
  kamen zdaj vse štiri tabele preveri proti seznamu vseh oznak, ki sploh
  lahko nastanejo.

- **Okno pravil se ne odpira več premajhno za svojo vsebino.** V zavihku
  „Lastni iskalni vzorci" je vrstica z razlago čarovnika („Iščemo: …") ležala
  napol za poljem „Preizkusno besedilo" – ravno stavek, s katerim brez
  znanja regularnih izrazov preverite, ali lastno pravilo išče pravo
  stvar. Okno je imelo trdno najmanjšo mero iz časa z manj zavihki in se je
  zato dalo povleči pod tisto, kar gre vanj. Zdaj se ravna po svoji
  vsebini in se odpre le tako majhno, kot ostane vse berljivo.

- **Imena v formulah preglednic ne ostajajo več.** Celica ima več kot eno
  mesto za besedilo, doslej pa je bilo pospravljeno le eno. Če je ime
  stalo v formuli – `="gospa "&"Sieglinde Ortner"` – ali je bilo nazadnje
  izračunan rezultat formule, je ostalo nespremenjeno v zvezku, čeprav je
  bila ista oseba v sosednji celici zamenjana. Kdor je celico kliknil, ga
  je prebral v vrstici za urejanje.

  Zdaj se zamenja oboje. Dotaknjeno je le tisto, kar stoji med
  narekovaji: sklici na celice, imena funkcij in imena listov ostajajo
  nedotaknjeni, `=SUMME(K2:K6)` še naprej računa. Ker ima isto ime povsod
  isto ogrado, tudi `=SUMMEWENN(A:A;"Huber";B:B)` še naprej najde svoje
  vrstice.

- **Diagrami ne prikazujejo več imen.** Diagram shrani lastno kopijo oznak
  svojih osi – riše tudi, kadar so izvorne celice že zdavnaj prazne. Pod
  stolpci je zato ostalo pet osebnih imen, medtem ko je bila preglednica
  nad njimi čista. Velja za preglednice **in** predstavitve.

- **Poimenovani obsegi s trdnim besedilom se pospravijo.** Poimenovan
  obseg lahko namesto sklica na celico vsebuje trdno besedilo; če je tam
  stalo ime, je ostalo. **Ime** obsega ostaja nedotaknjeno – nanj se
  sklicujejo formule, in preimenovanje bi povzročilo napako sklica. Kot
  pri imenu lista se sporoči, ne zamenja.

- **Enkrat prepoznan datum rojstva izgine po celem dokumentu.** Datum sam
  po sebi ne pove ničesar – šele beseda polja ga naredi datum rojstva, in
  prav zato datum računa ostane pri miru. Če je ista navedba v istem
  dokumentu stala drugič brez te besede – v naslovu slike, v izpolnjenem
  polju obrazca –, je tam ostala, čeprav je bilo nekaj vrstic višje
  „rojen(a) dne …" nedvomno prepoznano. Prenese se le tisto, kar je bilo v
  **tem** dokumentu že prepoznano kot datum rojstva; ugiba se še naprej
  nič.

- **Strukturirani podatki na spletnih straneh razkrijejo svoj datum
  rojstva.** V bloku JSON-LD za iskalnike stoji datum pod ključem
  `birthDate` – ključ pove, kaj je, tako kot sicer naslov stolpca. Zdaj se
  bere zraven; „Birthday" in „Birthdate" s tem veljata tudi v obrazcih za
  oznako polja.

- **Datum rojstva in kadrovska številka se najdeta tudi v preglednicah.** V
  celici stoji le gola vrednost – `14.03.1988`. Kaj pomeni, pove edino
  naslov stolpca, ta pa stoji mnogo vrstic višje. V Excelu se je to že
  bralo; v preglednicah LibreOffice in v datotekah CSV ne, in tam je zato
  datum rojstva ostal.

  Oba zdaj naslov berejo zraven – **a le, če je sam oznaka polja**. Pod
  „Datum rojstva" datum pade, pod „Datum računa" ali „Datum dobave" ne. To
  je zavestno previdna razlaga: naslov, kot je „Ime", nad poljubno pripombo
  bi tudi že enkrat postavil ogrado nad stavek, v katerem se sploh ne
  pojavlja nobena oseba.

### Odpravljeno

- **Očiščen CSV ostane preglednica.** Prepoznavanje CSV-vrstico bere kot
  stavek in je zato svoje najdbe že enkrat postavilo čez podpičje. Ograda
  je pogoltnila ločilo, vrstica je nato imela en stolpec manj, datoteke pa
  ni bilo več mogoče odpreti kot preglednico. Najdbe se zdaj končajo na
  meji celice, narekovaji maskiranja pa ostanejo. Prizadete celice se
  nato še enkrat preberejo posebej – sicer bi sosednja celica ostala
  neočiščena, ki jo je predolga najdba pokrila.

- **Komentarji v predstavitvah.** Robna opomba na prosojnici – pogosto
  ravno mesto, kjer stoji „Prosim pokličite gospo … pred sejo" – je
  ostala nedotaknjena, skupaj z imenom tistega, ki jo je napisal. V
  Excelu je bilo oboje že zdavnaj pospravljeno; PowerPoint besedilo
  komentarja in avtorja shrani drugače, in to je bilo spregledano. Zadeva
  obe obliki: starejšo in tisto, ki jo PowerPoint piše od 2019 – tam tudi
  službeni e-poštni naslov, vezan na avtorja. Začetnice, ki jih PowerPoint
  prikaže na oblačku, se odstranijo skupaj.

- **Datoteke LibreOffice: formula, uporabniško polje, avtor opombe.** Kar je
  bilo v Excelu že pospravljeno, je v preglednici ODS ostalo – tam formula
  ne stoji kot lasten element, temveč kot lastnost celice, in ime v njej je
  preživelo. Ob naslednjem odpiranju ga je LibreOffice znova izračunal.

  K temu tri nadaljnja mesta: vrednost **uporabniškega polja** v
  OpenDocument stoji enkrat zgoraj v deklaraciji in se v besedilu le
  prikliče – doslej je bil zamenjan le priklic, tako da se je ob odpiranju
  vrnila stara vrednost. **Avtor opombe** in sledene spremembe je ostal.
  In v **preglednici** sledenje spremembam sploh ni bilo pospravljeno – za
  razliko od besedilnega dokumenta –, tako da so izbrisane vsebine celic
  skupaj z imenom obdelovalca ostale. Sklici na celice in vsotne formule
  pri tem ostajajo nedotaknjeni.

- **Shranjene spletne strani razkrijejo svoje atribute.** Stran zdaleč ne
  pokaže vsega, kar vsebuje. Izpolnjeno polje obrazca nosi vnos v `value`,
  vmesnik JavaScript svoj nabor podatkov odloži v `data-…`, blok za
  iskalnike (JSON-LD) pa ga ponovi v celoti in urejeno: ime, datum
  rojstva, naslov, telefon. Vidno besedilo je bilo očiščeno, vse to je
  ostalo.

  Zdaj se pospravijo tudi ta mesta, poleg tega `aria-…` (kar prebere
  bralnik zaslona), `placeholder`, `summary` in predlagano ime datoteke
  povezave. Blok JSON-LD se pri tem bere kot podatki in ostane veljaven –
  njegovi ključi in besednjak ostanejo, izginejo le vrednosti. Navaden
  JavaScript ostaja nedotaknjen.

- **Slike izgubijo svoje stranske podatke tudi brez EXIF.** Fotografija
  poleg sebe nosi ime fotografa, čas zajema in koordinate GPS kraja zajema
  – pri oglasu za stanovanje to razkrije naslov, tudi če ga v besedilu ni.
  To je bilo odstranjeno, dokler je imela slika EXIF. Če pa so bile
  navedbe **le** kot XMP (tako shranjujeta Lightroom in Photoshop) ali kot
  besedilni blok v PNG (`Author`, `Comment`), je slika ostala povsem
  nedotaknjena. Oboje se zdaj prepozna in odstrani – tudi pri slikah, ki
  tičijo v dokumentu in v njem ostanejo. Usmerjenost ostaja ohranjena,
  slika brez stranskih podatkov pa se ne shrani na novo po nepotrebnem.

- **Cilji povezav v preglednicah, predstavitvah in dokumentih Word.** Kam
  vodi povezava, ne stoji v besedilu, temveč v lastnem odlagališču
  datoteke. E-poštni naslov za „Napiši pošto" je zato čiščenje preživel
  nedotaknjen, medtem ko je bil isti naslov v besedilu zamenjan.
  `mailto:` in `tel:` se tam zdaj pospravita enako kot v shranjenih
  spletnih straneh.

### Novo

- **Zdravniška pisma se ne vračajo več poškodovana.** Doslej je
  prepoznavanje imen zdravilne učinkovine imelo za osebna imena: iz
  „Metoprololsuccinat" je nastalo `[NAME]`, iz „Ramipril" `[ORT]`. Načrt
  zdravljenja je bil s tem neuporaben – medtem ko so diagnoze ostale
  nedotaknjene, torej ravno obratno. Izmerjeno je to zadelo **63 %
  učinkovin** in **53 % kliničnih strokovnih izrazov**, in ne le v
  nemščini: prek sedmih jezikov 74 %, v italijanščini vse preverjene.

  Maskuro zdaj pozna medicinski besednjak in ga pusti pri miru. Ostane 6 %
  namesto 43 % (nemško) in 1 % namesto 74 % (prek jezikov). Kjer pred tem
  stoji nagovor – „Spoštovana gospa …" – ime ostane ime, tudi če se
  slučajno imenuje kot zdravilna učinkovina.

- **Bolezni in zdravila je mogoče odstraniti – če želite.** Nova kljukica v
  nastavitvah: „Odstrani tudi bolezni in zdravila" (ukazna vrstica:
  `--mit-diagnosen`). Za kadrovske spise, odpovedi in izvedenska mnenja,
  kjer diagnoza nikogar ne zanima.

  **Privzeto izklopljeno**, in to namerno: zdravniško pismo *sestoji* iz
  diagnoz in učinkovin. Kdor ga anonimizira – za raziskave, za
  usposabljanje, za orodje UI –, večinoma želi ohraniti prav to vsebino in
  se znebiti le tega, za koga gre. Diagnoza je tam vsebina, ne izkaznica.

  Prepoznavanje najde uveljavljena poimenovanja in ne nadomesti pregleda:
  seznam bolezni nikoli ni popoln, ker zdravnik piše „C2-abuzus", kjer
  klasifikacija vodi „Motnje zaradi alkohola".

- **Diagnostične in zdravilne šifre se najdejo.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) in centralna farmacevtska številka so zdravstveni podatki
  kot vsaka izpisana diagnoza – v odpustnih pismih in obračunskih listinah
  celo pogostejša oblika. Privzeto so vklopljene, kot preostale posebne
  kategorije po čl. 9 GDPR.

  Diagnostična šifra se prepozna le z dokazom: z „ICD" spredaj ali v
  oklepaju za vrstico diagnoze. Brez tega pogoja bi program funkcijsko
  tipko **F10** imel za diagnozo zasvojenosti – v klasifikaciji je F10
  natanko to.

- **Dokončano datoteko je zdaj mogoče kopirati.** Ob vsaki dokončani
  vrstici poleg „Ogled", „Popravi" in „Pokaži v mapi" stoji četrti gumb:
  **Kopiraj**. Postavi očiščeno datoteko v odložišče – od tam gre s
  Ctrl+V (Mac: ⌘V) v pošto, okno klepeta ali orodje UI, brez ovinka prek
  mape.

  Kopira se **datoteka**, ne njeno besedilo: postavitev strani, slike in
  zakrivne proge s tem ostanejo ohranjeni. Prek kontekstnega menija
  seznama gre v odložišče tudi več izbranih rezultatov naenkrat, v meniju
  „Datoteka" pa stoji ista pot kot „**Kopiraj rezultat**" za vse, ki raje
  uporabljajo tipkovnico.

- **Izbira države zdaj lahko sledi dokumentu.** Identifikacijske, socialne
  in davčne številke se od države do države razlikujejo, katere države se
  preverjajo, pa je doslej veljalo za celo sejo – izpeljano iz jezika
  vmesnika. Kdor dela v nemščini in čisti francosko pismo, je torej v njem
  iskal nemške davčne ID-je in ne francoske številke socialnega
  zavarovanja.

  V oknu s pravili zato zdaj stoji **„Samodejno po jeziku dokumenta"**.
  Trdna izbira ostaja zraven, in to namerno: prepoznavanje jezika ni
  nezmotljivo – če se zmoti, deluje napačna izbira države. Kdor obdeluje
  le spise ene države, je z nespremenljivim seznamom varnejši.

  Nedotaknjeni ostajajo **nemški** vzorci (davčni ID, registrska, interna
  številka): ti so vezani na jezik, ne na izbiro države, in delujejo tudi
  naprej, kadar je kratko nemško besedilo uvrščeno kot angleško.

- **Gesla, ključi in prijavna imena se zdaj najdejo.** Kdor sporočilo o
  napaki, dnevnik ali izsek iz nastavitvene datoteke kopira v okno UI, ima
  v njem skoraj vedno dostopni ključ – ta je doslej stal nespremenjen.

  Prepozna se oboje: razširjene oblike ključev, ki govorijo same zase
  (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, glava
  zasebnega ključa), in označena oblika – „Geslo:", „API-ključ =",
  „Žeton:", „Uporabniško ime:". Zamenja se pri tem le vrednost, nikoli
  oznaka: „Geslo: [ZUGANGSDATEN_1]" ostane berljivo, in kdor preveri
  rezultat, vidi, da je tam stalo geslo.

  Prijavno ime in geslo sta dve ločeni vrsti. Kdor želi odstraniti le
  gesla, izklopi eno in obdrži drugo.

- **Črtne in QR-kode na slikah se naredijo neprepoznavne.** Na skeniranem
  odločbi skoraj vedno lepi koda, v njej pa stoji opravilna številka –
  ista številka, ki se v besedilu zraven odstrani. Doslej je strojno
  berljiva različica ostala: proga nad številko ne koristi ničesar, če jo
  dve centimetri stran naprava v sekundi prebere.

  Prepoznajo se QR-koda, Data Matrix, Aztec, Code 128, EAN in preostale
  uveljavljene oblike. Neprepoznavno pomeni pikselizirano, in sicer
  grobše kot pri obrazih: popravljanje napak kode iz nekaj ohranjenih
  polj presenetljivo veliko obnovi, polovičen tančica ne bi bila
  odstranitev.

  Možnost stoji ob „Naredi obraze neprepoznavne" in je enako
  **privzeto vklopljena**. Tudi z izklopljeno možnostjo poročilo pove,
  koliko slik nosi kodo – obraz se opazi ob listanju, koda velja za
  postranski dodatek.

- **Kontrolna številka kartice, PIN in datum poteka se najdejo.** Številko
  kreditne kartice je program že našel; šele s tremi navedbami zraven je
  uporabna, in na vsakem obračunskem potrdilu stojijo skupaj. Vse tri le
  za svojo oznako – golo „123" je hišna številka, stran ali kos.

- **Koordinate v besedilu se najdejo.** Iz slik je Maskuro kraj zajema že
  odstranjeval; če je ista navedba stala kot besedilo v izvedenskem
  mnenju ali poročilu o intervenciji, je ostala. Prepoznata se
  decimalna stopinja in zapis stopinje-minute-sekunde. Pri decimalni
  stopinji mora biti v bližini beseda, kot je „lokacija", „najdišče" ali
  „koordinate" – sicer bi bila vsaka merilna vrsta z dvema decimalkama
  navedba kraja.

- **Denarne zneske je zdaj mogoče odstraniti zraven.** Nova kljukica
  „Odstrani tudi denarne zneske", privzeto **izklopljena** kot datumske
  navedbe nad njo: v pogodbi je znesek vsebina, in kdor zakrije vse, ne
  ščiti nikogar. V plačilni listi, predlogu poravnave ali izpisku računa
  pa je ravno navedba, ki o osebi pove več kot ime zraven – to ve le, kdor
  ima listino pred seboj.

  Znesek se prepozna **le z navedbo valute**: „4.250,00" samo je kos,
  šele „4.250,00 EUR" je denar. Simbol valute, kratica in izpisano ime
  štejejo, pred in za njim, skupaj z zapisom „990,– CHF".

- **Posebne kategorije po čl. 9 GDPR se prepoznajo.** Veroizpoved,
  sindikalna pripadnost, politično prepričanje, zdravstvene navedbe – in
  zraven kazenskopravne navedbe po čl. 10. To so podatki, katerih obdelavo
  uredba načeloma **prepoveduje**; zato so kot edina nova skupina privzeto
  **vklopljene**. Kdor jih želi obdržati, se odloči sam.

  Prepozna se oblika, v kakršni v praksi stojijo: polje obrazca na
  kadrovski listi – „Veroizpoved: rimskokatoliška", „Sindikat: ZSSS",
  „Stopnja invalidnosti: 50", „Kazenske obsodbe: brez" –, tako z
  dvopičjem zraven kot z oznako nad vrednostjo, kot jo poda izpolnjen list.

  **Tekoče besedilo pripada stopnji UI.** „Že leta se udejstvuje v
  sindikatu" je ista navedba, in noben iskalni vzorec je ne najde
  zanesljivo. Stopnja UI od te različice izrecno išče tudi te kategorije;
  kdor potrebuje tekoče besedilo, jo vklopi.

- **Osebne lastnosti in poklic – navedbe, ki tudi brez imena pokažejo, kdo
  je mišljen.** Spol, zakonski stan, telesna višina, barva oči in las se
  od te različice odstranjujejo; poklic, funkcija in oddelek na željo,
  prek lastne kljukice („Odstrani tudi poklic in oddelek") ali
  `--mit-berufen`.

  **Zakaj je eno vklopljeno, drugo pa ne:** „Vodja oddelka nabave" v
  podjetju poimenuje natanko eno osebo, tudi če je ime zraven zakrito – v
  izvedenskem mnenju ali odpovedi to sodi zraven. Pregled zaposlenih
  nasprotno *sestoji* iz poklicnih naslovov; kdor bi jih privzeto
  odstranil, bi vrnil prazen list. Kateri primer gre, ve le, kdor ima
  listino pred seboj. Lastnosti nad tem stojijo skoraj le v poljih
  obrazcev, so redke in nikoli ne nosijo vsebine – zato ne stanejo nič.

- **Preveriti tujo datoteko.** „Datoteka → Preveri datoteko …" prebere že
  zakrit dokument in javi, kaj v njem še stoji – in **na katerem mestu**:
  stran in vrstica, vrsta in dolžina. Za primer, ko nekdo preverja delo
  drugega: spis iz pisarne, uradno pojasnilo, lastno odhodno pošto pred
  odpošiljanjem.

  **Vrednost sama ne stoji v poročilu.** Kdor odpre mesto, jo tako ali
  tako vidi – in poročilo sme zato biti shranjeno in posredovano naprej,
  ne da bi bilo samo zbirka osebnih podatkov.

  **In poročilo v vsakem primeru pove, česa ni moglo videti.** Slike se ne
  berejo; pri skenu brez besedilne plasti „nobene najdbe" pomeni *ni
  preverjeno*, ne *čisto*. V ukazni vrstici to loči povratna vrednost:
  `--nachpruefen` vrne 0 za preverjeno in čisto, 4 za najdbe in 5 za
  nepreverljivo. S tem je mogoče odhodno pošto samodejno zadržati, namesto
  da bi jo spustili skozi.

- **Poročilo o preverjanju: en list na čiščenje.** „Datoteka → Shrani
  poročilo o preverjanju …" – ali `--pruefbericht <mapa>` na ukazni
  vrstici – zapiše enostranski PDF (po izbiri CSV ali besedilo) z
  navedbami o zagonu, najdenimi vrstami skupaj s številom, dvema
  kazalnikoma in preverjevalno opombo. Za spisovno mapo in za nadzor:
  dnevnik preverjanja je zanesljivo dokazilo, a nihče ne predloži
  datoteke JSON Lines.

  **Novi sta dve številki**, ki jih doslej nikjer ni bilo videti:
  *povprečno zaupanje* – kako gotovo je bilo prepoznavanje pri tem, kar je
  našlo – in *stopnja maskiranja*, delež zamenjanih znakov v besedilu.
  Obe stojita s svojo mejo: zaupanje **nič** ne pove o spregledanem, in
  zraven vedno stoji, prek koliko najdb sploh gre; stopnja slik ne šteje
  zraven in je pri slikovnem dokumentu previsoka.

  **Najdene vrednosti ne stojijo na listu** – ista meja kot pri dnevniku
  in iskalnem teku. Spodaj stojita dve vrstici, ki ne povesta istega:
  kontrolna vsota pokaže, da je list nespremenjen; vrstica dnevnika – le
  pri tekočem dnevniku – napotuje na **podpisano** vrstico, ki dokazuje
  zagon. Šele ona dokaže izvor.

- **„Kako zanesljivo je bilo to?" – kazalniki ob rezultatu.** Gumb
  „Kazalniki" pod rezultatom razpre, česar doslej ni bilo videti nikjer:
  najdbe, besede in znake, porazdelitev po vrsti kot vrstico stolpcev,
  poleg tega povprečno zaupanje in stopnjo maskiranja. Iste številke kot v
  poročilu o preverjanju, le takoj in brez izpisa.

  **S svojim pridržkom na isti površini:** ob zaupanju stoji, prek koliko
  najdb gre, pod tem pa stavek, da **nič** ne pove o spregledanem.
  Odstotek brez tega stavka se bere kot stopnja najdb – in kdor ga tako
  razume, je na slabšem kot brez številke.

  Izračuna se šele ob razprtju: imenovalec stopnje maskiranja stane en
  branje na datoteko, in tega naj ne plača, kdor si številk sploh ne
  ogleda.

- **Lastne iskalne vzorce zgradite, ne da bi katerega napisali.** Zavihek
  „Lastni iskalni vzorci" zdaj v treh korakih vodi skozi zadevo: *Kaj
  iščete? → Kako pri vas izgleda taka navedba? → Poimenujte in shranite.*
  Vnesete primer – na primer `KD-004711` –, program iz njega izpelje
  pravilo in v besedah zapiše, po čem išče. Predogled s števcem najdb
  preverja ob vsakem pritisku tipke.

  **Regularni izraz se pri tem sploh ne pojavi.** Znanje nikoli ni bilo
  težava: lastni iskalni vzorci obstajajo že dolgo, le zahtevali so izraz,
  kot je `\bKD-\d{6}\b`, tega pa v pisarni ali kadrovskem oddelku ne piše
  nihče. Kdor ga *hoče* napisati, razpre strokovni način.

  **Katalog predlog je na novo razvrščen:** trinajst kartic z imenom,
  razlago in vzorčno vrednostjo, filtrirano prek oznak kategorij – finance,
  uradi, stik, kadri, medicina.

  In če izpeljan vzorec zajame preveč, program to pove sam od sebe: primer
  iz samih številk zadene vsako letnico in vsak znesek, in kdor izraza ne
  zna brati, tega sicer ne bi opazil.

- **Sedem oznak namesto šestinpetdeset kljukic.** Nov zavihek „Kaj se
  išče" združi vse prepoznavne vrste v sedem skupin – osebe, stik in kraj,
  identifikacije, finance, tehnika, posebne kategorije, podjetja in
  lastno. Oznaka preklopi svojo skupino, „Vse vklopljeno" in „Vse
  izklopljeno" cel seznam; pod tem ostane vsaka vrsta posamično
  odkljukljiva.

  **Privzeto je vse vklopljeno, in tako ostane.** Kar je tu izklopljeno,
  se sploh ne išče – najgrobejši poseg, ki ga okno pravil dovoljuje, in
  učinkuje na vsak dokument. Zato pod seznamom vedno piše, koliko vrst je
  izklopljenih, shrani pa se le izklopljeno: nova vrsta je s tem tudi v
  datoteki pravil izpred dveh dni vklopljena, namesto da bi tiho odpadla.

- **Okvir prenesti na vse strani.** V oknu Popravi gumb **Uporabi na vseh
  straneh** vzame nazadnje povlečen okvir in zakrije isto mesto na vsaki
  nadaljnji strani – za glavo dopisa, nogo in polje opravilne številke.
  Pri skeniranem spisu z osemdesetimi stranmi to iz dvajsetih minut naredi
  dve.

  **„Isto mesto" pomeni isto *relativno* mesto na listu.** V svežnju iz
  podajalnika redno leži ena stran postrani, druga je A3, tretja
  zasukana; absolutno prenesen pravokotnik bi tam pristal ob glavi
  dopisa – in videli bi progo ter mislili, da je zadeva urejena.

  **Zakrije se, ne zamenja**, tudi če je izhodiščni okvir bila ograda: pod
  istim pravokotnikom na strani štirideset stoji nekaj drugega kot na
  strani ena, in ograda z isto številko bi trdila enakost, ki je ni.

- **Opomba na zakrivni progi.** Pri pravici vpogleda v spis ob vsakem
  zakritju stoji, zakaj je bilo zakrito. Novo polje **Opomba na progi** v
  nastavitvah – ali `--balkenvermerk` – na vsako progo zapiše kratko
  besedilo: „§ 203 KZ", „GDPR", „zaupno". Za dokument, ki ga izda urad, je
  to razlika: prejemnik vidi razlog, ne da bi imel dnevnik, ki ga tako ali
  tako nikoli ne dobi.

  **Privzeto prazno**, ker je opomba v izdanem dokumentu vidna in sama
  navedba – prejemniku pove, pod katerim naslovom je nekaj zadržano.
  Učinkuje le pri **zakrivanju**; kjer stoji ograda, ni proge. Na progi,
  premajhni za berljivo besedilo, odpade – neberljiva opomba izgleda kot
  napaka.

- **Odklep brez internetne povezave – zdaj popoln.** V oknu licence je „Odkleni
  brez interneta" obstajalo že dlje: zgoraj zahtevna koda za s seboj,
  spodaj polje za odklep, ki pride nazaj. Le izdati je doslej **ni mogel
  nihče** – orodje za to je manjkalo, koda pa je šla v prazno. To je
  odpravljeno.

  Za urade in pisarne z izoliranimi računalniki to ni poseben primer,
  temveč navaden primer – in prav to je ciljna skupina, pri kateri
  obljuba „vaši dokumenti nikoli ne zapustijo računalnika" tehta
  najtežje. Koda ne razkrije ničesar o dokumentih: vsebuje oznako licence
  in razpršeno vrednost računalnika, sicer nič.

- **Prevzemi iz bralnika.** „Datoteka → Prevzemi iz bralnika …" neposredno
  prebere sveženj in strani postavi na seznam – za pošto je to razlika
  med dvema delovnima korakoma in enim. Podajalnik listov se izprazni do
  zadnje strani; napravo, ločljivost in barvo izbere sistemsko pogovorno
  okno bralnika, ki ga tako ali tako poznate.

  **Ne čisti se samodejno.** Najprej vidite, kaj je prišlo noter, in nato
  pritisnete „Očisti" kot pri vsaki drugi datoteki – sken, ki bi takoj
  tekel skozi, bi vam vzel pogled na postrani vložen sveženj.

  **To je le pod Windows**, in menijska postavka to pove tudi na Macu:
  tam programska oprema vašega bralnika piše v mapo, „Nadziraj mapo …" pa
  očisti vse, kar tam pristane.

### Drugo

- **Seznam vseh najdenih navedb je zdaj priložen** in nastane iz izvorne
  kode (`hilfe/GEFUNDENE-ANGABEN.md`): 177 vrst v 35 državah, 23 od njih z
  računom kontrolne številke. Navede tudi, kako je bilo šteto – `[IME]`
  štejemo enkrat, kjer drugi osebno, drugo in priimek vodijo kot tri
  vnose.

- **Zakrivanje je zdaj tudi v Wordu, PowerPointu, OpenDocumentu in
  HTML-ju.** Izbira med ogrado in zakritjem je doslej veljala le za
  datoteke PDF. Zdaj zmorejo tudi drugi: najdba se odstrani, na njeno
  mesto pa pride črna proga – v samem dokumentu, ne kot slika čeznjo.
  Kdor datoteko posreduje naprej, poda zakrit spis in ne takega, v
  katerem zakrito še leži kot besedilo pod njim.

  **Odloča se ločeno**, v dveh izbirnih poljih: „Pri PDF" in „Pri Wordu,
  PowerPointu, OpenDocumentu in HTML-ju". Radi se odločite drugače –
  zakriti PDF gre na urad, ista stvar kot datoteka Word potuje naprej po
  hiši in naj ostane berljiva. Na ukazni vrstici ustrezno `--pdf-modus` in
  `--office-modus`; shranjeno „zakrivanje" iz prejšnjih različic velja še
  naprej za PDF.

  V preglednicah, golem besedilu, CSV-ju in e-pošti proga ne gre – tam
  manjka površina, na katero bi legla. Še naprej se vstavi ograda, rezultat
  pa to **zdaj pove**, namesto da bi to tiho počel.

- **Novo: „Odstrani" – najdba preprosto ostane prazna.** Tretji način
  delovanja poleg ograde in zakritja, in edini, ki zmore **vsak** format:
  izpustitev ne potrebuje površine. V PDF-ju se pri tem ne izriše nič, v
  Wordu in HTML-ju mesto ostane prazno, v preglednici enako.

  Najtiši je od treh: kdor bere rezultat, ne vidi, da je tam kdaj kaj
  stalo – tudi dolžina vrednosti se ne razkrije. Za listino, ki naj jo
  nekdo preveri, ostaja ograda večinoma boljša izbira.

  Na slikah ne velja nobena od treh izbir: slikovnih točk ni mogoče
  zamenjati z ogrado in ne izpustiti. Kar tam najde optično prepoznavanje,
  se kot doslej vedno prebarva.

- **Okno Popravi ne trdi več zamenjav, ki jih ni.** Desno je ob vsaki
  vrednosti stala ograda – tudi pri zakriti datoteki, v kateri je ni bilo
  niti ene. Klik na tako vrstico ni ničesar označil, „Prekliči" pa je šel
  v prazno. Zdaj tam stoji „zakrito" oziroma „odstranjeno", vrstic pa
  sploh ni več mogoče preklicati: besedila ni več, ni ničesar za
  obnoviti. To je veljalo za zakrite datoteke PDF, za Word in OpenDocument
  ter za vse, kar je bilo najdeno na slikah.

- **Besedilni pogled zdaj proge kaže kot proge.** Zakrita datoteka Word je
  pri dodelovanju izgledala **prazna**: na zakritih mestih so stale
  vrzeli, kot da je program besedilo pogoltnil. Vzrok je bil prikaz, ne
  rezultat – v samem dokumentu je proga ves čas ležala pravilno. Zdaj
  stoji tudi v pogledu tam, črna kot v rezultatu, v Wordu, PowerPointu,
  OpenDocumentu in HTML-ju.

- **Sporočila Outlook (`.msg`) se zdaj čistijo.** `.eml` je obstajal
  zdavnaj – v nemških podjetjih pa je Outlook e-pošta, in tam se shranjeno
  sporočilo imenuje `.msg`. S tem je najgostejši format PII pokrit tudi v
  svoji najbolj razširjeni obliki odlaganja: zadeva, pošiljatelj, vrstice
  prejemnika, besedilo sporočila, oblika HTML, seznam prejemnikov in
  priloge – slednje prek obstoječih poti in z istimi ogradami kot besedilo
  pošte.

  **`.msg` nosi isto besedilo večkrat**, in to je past: kot golo besedilo,
  kot HTML **in** kot RTF. Kdor očisti le golo besedilo, ni storil nič –
  Outlook prednostno prikaže RTF. Oblika RTF se zato v celoti odstrani,
  enako internetne glave z verigo Received in binarni iskalni ključi, ki
  imena in naslove preživijo vsako čiščenje besedila. Rezultat se še
  naprej odpre v Outlooku in prikaže besedilo brez oblikovanja pisave;
  poročilo to izrecno pove.

- **Pravila opisati z lastnimi besedami, namesto pisati regex.** Okno
  pravil zmore veliko in je za to zahtevalo vzorec regularnega izraza –
  mesto, kjer se za večino neha. Zdaj zadošča stavek: „Naše opravilne
  številke oblike 12 C 345/26 naj ostanejo." Stopnja UI iz tega predlaga
  izraze in iskalne vzorce.

  **Prevzame se le, kar odkljukate – privzeto ni odkljukano nič.** Ob
  vsakem predlogu stoji stavek, kaj pomeni, in število njegovih najdb v
  vzorčnem besedilu, ki ga lahko priložite. Kar zaščito **odvzame**, je
  kot tako označeno: „ta izraz vedno odstrani" in „ta izraz nikoli ne
  odstrani" bi na seznamu sicer izgledala enako. Predlogi, ki bi ustrezali
  vsemu, se sploh ne prikažejo.

- **Dnevnik preverjanja zdaj šteje skupaj prek vseh delovnih mest.** Če
  podjetje dnevnike prek `protokoll_pfad` odlaga na skupno mapo, tam
  vsako delovno mesto piše svojo mesečno datoteko – doslej je pooblaščenec
  za varstvo podatkov s tridesetimi mesti moral pregledati trideset
  datotek posamično. Nad seznamom zdaj stoji vrstica z vsotami meseca, in
  **javi pretrgane verige z imenom**: naknadna sprememba pade v oči le,
  če jo kdo pregleda, v tridesetih datotekah pa nihče ne pregleduje
  ročno.

  **Brez pregleda po osebah** – tudi v tem pogledu ne. Razvrstitev „kdo je
  koliko očistil" bi bila primerna za nadzor vedenja in učinkovitosti, in
  na tem je odvisno soodločanje, ne na namenu. Štejejo se zagoni,
  datoteke in najdbe prek podjetja.

- **„Predlagaj profil iz listine": pravila enkrat vprašati namesto
  preleteti štiriinštirideset vrst.** V oknu pravil je nov gumb: stopnji UI
  pokaže listino, ugotovi, za kaj gre – zdravniško pismo, prijava,
  pogodba, račun, odločba – in predlaga strategije, ki k temu sodijo. Pri
  zdravniškem pismu se na primer datumske navedbe premaknejo namesto
  zamenjajo, ker je v zdravstvenem kartonu kronologija vsebina.

  **Profili so v programu, model le izbira** – pravila zakrivanja niso
  odvisna od tega, kar jezikovni model šteje za dobro zamisel. Predlaga se
  vsaka točka posamično in z obrazložitvijo; prevzame se nič brez
  povratnega vprašanja, in kar ste sami določili, ostane nedotaknjeno.
  Brez stopnje UI ostane pri varni privzeti vrednosti: ograda za vse.

- **Nova strategija „izmisli si": verjetna napačna vrednost namesto
  ograde.** „Gospa Berger je pisala gospodu Dopplerju v Fuldi" namesto
  „[IME_1] je pisal/a [IME_2] v [KRAJ_1]" – za gradiva za usposabljanje,
  predstavitvene spise, testne podatkovne zbirke in vse, kar se nato
  predloži UI. Nagovor, stavčna zgradba in berljivost ostanejo ohranjeni.

  Ista vrednost dobi isto napačno vrednost, prek vseh datotek nekega
  opravila in na vsakem računalniku z isto datoteko pravil – **ne da bi
  bil kjer koli shranjen pripis** (ista mehanika kot pri razprševanju).
  E-poštni naslovi ležijo na rezerviranih vzorčnih domenah, telefonske
  številke v za to prostem obsegu, izmišljeni IBAN-i nosijo pravilno
  izračunano kontrolno številko. Mogoče za imena, kraje, naslove,
  podjetja, e-pošto, telefon in IBAN; za druge vrste se pravilo zavrne,
  namesto da bi ostalo brez učinka.

  **Poročilo izrecno pove, da je bilo izmišljeno.** Tako očiščen dokument
  se bere kot pravi in to ni – ne velja kot dokazilo in se ne sme
  posredovati kot izvirnik.

- **Protipreizkušnja: „Kdo ostane prepoznaven?"** Nova kljukica pod
  stopnjo UI **dokončan rezultat** še enkrat predloži jezikovnemu modelu
  in vpraša, kdo je kljub čiščenju prepoznaven. Mišljen je primer, ki ga
  nobeno prepoznavanje na svetu ne najde, ker tam sploh ne stoji ime:
  „edina babica v okraju", „sodelavec, ki je marca po požaru odpovedal".
  Noben vzorec ne zadene, in na kraju samem vseeno vsak ve, kdo je
  mišljen.

  **Pri tem se ne odstrani nič.** Mesta stojijo s stavkom obrazložitve v
  poročilu, odloča pa se ročno – program, ki sam od sebe jemlje stavke iz
  listine, ker se mu zdijo izdajalski, iz čiščenja naredi prepis, in
  nihče ne bi videl, kaj manjka. Kvečjemu pet mest na datoteko; česar
  model ne more dobesedno dokazati, odpade. V ukazni vrstici:
  `--restrisiko` skupaj z `--ki`.

- **Pot nazaj iz UI: „Prevedi odgovor nazaj".** Doslej je bila zgrajena le
  polovica zanke – kopirati besedilo, prilepiti očiščeno, predložiti UI.
  Odgovor je prišel nazaj z `[IME_1]`, in kdor ga je potreboval, je ročno
  vstavil nazaj, kar je ročno vzel ven. Zdaj pot nazaj stoji v meniju
  „Program": kopirati odgovor, klikniti vnos, prava imena so spet tam.

  Pripis za to leži **le v pomnilniku**, velja vedno le za nazadnje
  očiščeno mesto in poteče po eni uri; kdor izklopi stražarja odložišča,
  ga takoj izgubi. Obnoviti je mogoče le tisto, kar je bilo zamenjano –
  zakrito, maskirano in razpršeno ni obratljivo, program pa pove, koliko
  mest je zato moral pustiti stati. Upravljane namestitve pot nazaj prek
  nastavitve `rueckweg` povsem izklopijo.

- **Nadziraj mapo: kar je vloženo, kmalu leži očiščeno v izhodu.** Za
  pošto, ekipo za predal ali mapo skenov – enkrat nastavite, nato nihče
  več ne klika. Najdete pod „Datoteka → Nadziraj mapo …", v ukazni
  vrstici prek `--wache <mapa>`.

  Izvirnik ostane, kjer je bil; na željo nespremenjen preide v podmapo
  „Opravljeno", pri čemer se nikoli nič ne prepiše. Datoteka se dotakne
  šele, ko je dokončano zapisana – sicer bi bila datoteka, še kopirana
  prek omrežja, prebrana napol in javljena kot očiščena. Kar spodleti,
  ostane in se pove, namesto da bi se neskončno ponavljalo. In stražar si
  opravljeno zapomni brez imena datoteke: kar leži v vhodni mapi, pogosto
  že v imenu razkrije, za kaj gre.

  **Nadzor mape zunaj lastnega uporabniškega profila – na primer na
  omrežnem pogonu – predpostavlja licenco za avtomatizacijo.** Mapa, do
  katere ima dostop več ljudi, je storitev in ne delovno mesto; v
  lastnem profilu in med preizkusnim obdobjem omejitev ne velja.

### Odpravljeno

- **Nastavitve so bile desno odrezane.** Okno se je odprlo v trdni
  velikosti, ki je zadoščala le za velikost pisave, s katero je bilo
  razvito: na Macu so „Preveri zdaj", „Spremeni …" in namigi zraven stali
  napol zunaj. Zdaj se odpre tako široko, kot ga potrebujejo njegove
  strani – v vsakem jeziku in pri vsaki velikosti pisave, omejeno le z
  zaslonom.

- **„Preveri zdaj" zdaj vidno odgovori.** Rezultat je stal v vrstici stanja
  glavnega okna – torej za oknom nastavitev, iz katerega je bilo
  vprašano. Kdor je preveril, ni videl ničesar. Zdaj pride odgovor kot
  sporočilo nad nastavitvami, in če je na voljo nova različica, vodi
  naravnost k namestitvi. Ob zagonu programa ostane kot doslej pri
  vrstici stanja, nevprašano se ne odpre nobeno okno.

- **Kopirane datoteke na Macu niso prišle v odložišče.** Vračanje
  očiščenih datotek je javilo uspeh, a ni odložilo ničesar uporabnega –
  lepljenje ni dalo ničesar. Prizadeto je bilo vse, kar piše datoteke v
  odložišče.

- **In iz odložišča se je na Macu prebrala le prva datoteka.** Kdor je v
  Finderju kopiral tri datoteke in izbral „Zdaj očisti odložišče", je dve
  od njih dobil nazaj neočiščeni – ne da bi kar koli to povedalo. Zdaj
  pridejo vse.

- **„Preveri datoteko" zdaj sprejme tudi povlečene datoteke** – kot glavno
  okno. Odloženo se doda, namesto da bi zavrglo dosedanjo izbiro; isto
  odloženo dvakrat ne spremeni ničesar, kar program ne zna prebrati, pa
  se pove namesto pogoltne.

- **In okno pove, da čaka na vas.** Odprlo se je s praznim okvirjem in
  sivim gumbom „Preveri" – to izgleda, kot da ni ničesar, ne kot da manjka
  izbira. Zdaj tam piše „Datoteka še ni izbrana – povlecite jo sem ali
  spodaj izberite prek 'Izberi datoteke …'."

- **Dolg zagon zdaj pove, da teče.** „Dodatni model za natančnejše
  prepoznavanje se nalaga – trenutek …" je obstal, dokler je
  prepoznavanje računalo: pri datoteki s 47.500 besedami torej osemnajst
  minut, čeprav je bilo nalaganje po devetih sekundah končano. Kdor to
  vidi, ima program za obviseli. Zdaj sledi „Natančnejše prepoznavanje
  teče – pri dolgih besedilih traja nekaj minut", vrstica stanja pa šteje
  zraven: „Natančnejše prepoznavanje (7/312)". Sporoča se pri tem iz
  zanke modela – vsakih 250 besed, torej približno vsakih šest sekund –,
  ne za vsak besedilni blok: en besedilni blok nosi dvanajst tisoč besed
  in potrebuje minute.

- **Prekinjen zagon zdaj pove, da je bil prekinjen.** Kdor je pritisnil
  „Prekliči", je nato prebral „0 od 1 datoteke očiščene." – pravilno
  prešteto in vendar napačna informacija. Sporočilo, katero datoteko je
  zadelo, je v istem trenutku prepisalo sporočilo o štetju. In v seznamu
  datotek je še naprej stalo „teče …", čeprav ni teklo nič več; zdaj tam
  stoji „prekinjeno".

- **Stavek o varstvu podatkov je bil odrezan.** „… brez oblaka, brez
  nalaganja. Več v izjavi o va" – pri širini okna, s katero se program
  zažene, se je končal sredi besede. Zdaj zavzame polno širino.

- **Licenčna storitev je lahko nekaj sporočila, in nihče ni poslušal.**
  Kadar so vsa licenčna mesta zasedena, je licenca potekla, ključ neznan
  ali licenčna uprava pri ponudniku izklopljena, storitev za to pošlje
  razlog – predvideno je bilo od začetka, da vam je **enkrat** pojasnjen.
  Prikazan ni bil nikoli. Zdaj se pojavi opozorilo, ki najprej pove, da
  program deluje nespremenjeno naprej, in nato, za kaj gre. Enkrat na
  razlog: kdor ga je zaprl, ga pri dnevnem preverjanju ne vidi znova – ga
  pa vidi, če se razlog spremeni.

- **V trgovini kupljena licenca za več mest je kazala „1 mesto".**
  Trgovina razdeljuje pripravljene ključe in kupljeno število mest hrani
  pri sebi; prikazano pa je bilo število iz samega ključa, to pa pri
  vsakem zalogovnem ključu glasi na eno mesto. Kdor je kupil osem mest, je
  bral „1 mesto" – in od drugega prijavljenega računalnika naprej je
  prikaz stal v rdečem skupaj z „Obrnite se na svojo upravo". Zdaj velja
  število, ki ga je storitev nazadnje javila; brez odgovora ostane pri
  ključu, manjše od kupljenega obsega pa nikoli ne postane. Enako velja za
  dokupe in podaljšanja: ti pri ponudniku spremenijo število mest, ne
  vašega ključa.

- **Po nakupu je stalo „Licencirano za Maskuro zasebna licenca".** To ni
  ime, temveč ograda, pod katero se ključi pripravijo – vaše ime tam ne
  more stati, ker je ključ podpisan že pred nakupom. Namesto da bi vam
  pokazal tuje ime kot vaše, zdaj tam preprosto stoji „Zasebna licenca" in
  število mest. Pri licenci, izdani na vas, ostane vaše ime nespremenjeno
  tam.

- **V meniju Pomoč je stalo „Pomoč _FAQ".** In-znak se je spremenil v
  podčrtaj, ker ga je Qt bral kot oznako za tipko na tipkovnici. Zdaj tam
  stoji „Pomoč in FAQ".

- **Okno nastavitev je ostalo, ko je program izginil v ikono** – in tudi
  takrat, ko je bilo glavno okno zaprto. Zdaj gre zraven. (Zadeva le to
  različico; lastno okno je novo.)

- **Zavrnjena zahteva za licenco zdaj pove, za kaj gre.** Če je licenčna
  storitev zahtevo zavrnila, ne da bi poslala razlog, je v oknu licence v
  rdečem pisalo „Neznan odgovor." – stavek, s katerim niti vi niti podpora
  ne moreta ničesar začeti in ki vas napelje iskati napako pri lastnem
  ključu. Zdaj tam piše, kaj se je resnično zgodilo: da je storitev
  zavrnila, ne da bi to utemeljila, in na koga se obrniti. Če je licenčna
  uprava pri ponudniku začasno izklopljena, se tudi to navede – skupaj z
  napotkom, da vaš ključ s tem ni prizadet.

- **Na Macu so nastavljeni jeziki nenadoma veljali za manjkajoče.** Ob
  zagonu je program javil „Nobenega jezikovnega modela ni nameščenega" in
  ponudil prvo nastavitev, čeprav so bili jeziki že zdavnaj naloženi –
  kdor je pogledal pod „Jeziki dokumentov", jih je tam našel v celoti.
  Program jih je glede na pot zagona iskal na dveh različnih mestih: če je
  bil zagnan iz mape Programi, jih je našel; če je bila ista izgradnja
  zagnana kot navadna mapa, jih je iskal zraven sebe, kjer nobenih ni. Od
  zdaj na Macu brez izjeme velja isto mesto v uporabniškem profilu, ne
  glede na to, kako je program pakiran. Ničesar ni treba znova naložiti.

- **„Kaj je novega" je kazalo polovico seznama.** Okno po posodobitvi se je
  prekinilo sredi stavka, preostale točke pa so stale kot prazna
  oznaka naštevanja. Krivec je bila ograda v koničastih oklepajih – na
  primer `<datei>.docx` –, ki jo je prikaz imel za oznako in od katere je
  vse nadaljnje zavrgel. Prav novosti glede varnosti so bile s tem
  prizadete. Pomoč take ograde od nekdaj kaže pravilno; zdaj to počne
  tudi to okno.

- **Ščipanje z dvema prstoma zdaj približuje v oknu Popravi.** Na
  sledilni ploščici je to *ta* gesta za približevanje – v urejevalniku
  doslej ni naredila ničesar, in kdor je hotel mesto ogledati natančneje,
  je moral seči po drsniku ali Ctrl+kolešček. Stran gesti sledi
  neposredno in se ob spustu znova izriše ostro.

- **Približuje se na mesto, ki ga gledate.** Ščipanje poveča okrog točke
  med prsti, Ctrl+kolešček okrog točke pod kazalcem. Gumbi, tipkovne
  bližnjice in drsnik približevanja obdržijo sredino – k njim ne sodi
  mesto, na katero kažete. Prej je pri vseh ostala le vrednost drsenja: od
  prilagojene strani je to obdržalo zgornji rob, vse pod njim pa je pri
  približevanju odromalo iz slike.

- **„Prej/potem" je bil v pogledu strani mrtev gumb.** Dokler je bil
  pogled strani vklopljen, se je dal pritisniti – in vsakič javil, da
  izvirnika ni mogoče odpreti. Za primerjavo tam tudi ni ničesar: pogled
  strani je odslikava očiščene različice, nasprotja izvirniku ni. Gumb je
  zdaj zaklenjen in ob prehodu navede razlog skupaj z izhodom (besedilni
  pogled). Njegov opis je poleg tega izrecno obljubljal, da primerjava
  poteka „neodvisno od tega, ali je aktiven besedilni ali stranski
  pogled" – to nikoli ni držalo.

- **Pogled strani je povzročil sesutje LibreOffice.** Če sta bila
  ustvarjena dva pogleda strani hkrati – na primer „Počrni kot PDF", medtem
  ko je predogled še računal –, se je sistem javil s sesutjem LibreOffice,
  čeprav so strani na koncu vendarle nastale: oba zagona sta dostopala do
  istega delovnega odlagališča LibreOffice, kar ta ne prenese. Zdaj ga
  vedno dobi le en zagon; preostali se umaknejo na lastnega. To stane
  nekaj sekund dlje, zato pa ni več sporočila o napaki, in noben zagon ne
  ostane brez rezultata. Drugo naročilo izrisa ob tekočem se poleg tega
  sploh ne sprejme.

- **„Pokaži izvirnik" je lahko končal program.** Če izvirnika ni bilo
  mogoče odpreti – ker je premaknjen, preimenovan, zaščiten z geslom ali
  leži na ločenem pogonu –, se je okno Popravi brez opozorila prekinilo,
  odprte delovne kopije pa so bile izgubljene. Zdaj se pojavi namig,
  stikalo skoči nazaj, očiščena različica pa ostane. Kjer izvirnik načelno
  ne sodi zraven – na primer pri pogledu strani PDF, nastalem iz datoteke
  Word –, je stikalo vnaprej zaklenjeno in ob prehodu navede razlog,
  namesto da bi ob vsakem pritisku prikazalo isti namig.

- **Poročila o napakah niso nikoli prispela.** Kdor je hotel prijaviti
  napako, je dobil „Gegenstelle je poročilo zavrnila" – in nihče ga ni
  nikoli videl. Dva vzroka, oba na poti: program se pri strežniku ni
  izkazal in je bil zato zavrnjen z zaščito pred množičnim dostopom, naslov
  pa je kazal na drugo ime, ki mu program ni sledil. Oboje je odpravljeno;
  poročilo znova gre ven. **Isto je zadelo licenčni odklep**: prijava,
  odjava in poizvedbe prav tako niso dosegle storitve – tam neopazno, ker
  neodgovorjena zahteva zavestno ničesar ne spremeni na vaši licenci. In
  če zavrnitev vseeno kdaj ostane nepojasnjena, zdaj zraven stoji njena
  tehnična številka, namesto da bi vsak vzrok izgledal enako.

- **Klik na „Pokaži izvirnik" je lahko končal program.** Če izvirnika ni
  bilo mogoče odpreti – premaknjen, preimenovan, na ločenem omrežnem
  pogonu, zaščiten z geslom ali poškodovan –, je izginilo okno Popravi
  skupaj z vsemi odprtimi delovnimi kopijami. Zdaj stikalo ostane pri
  očiščeni različici, okvir pa pove, kaj se dogaja; tehnični razlog stoji v
  podrobnostih, če ga želite prijaviti. Enako velja za rezultat, ki ga ni
  mogoče prikazati: okno se odpre in to pove, namesto da bi izginilo.

- **Vprašanje po sesutju je prihajalo prepogosto – in izbrisalo sled, po
  kateri je spraševalo.** Pojavilo se je tudi, kadar se ni sesulo nič:
  zapisek nastane, takoj ko se kjer koli pojavi nepričakovana motnja,
  tudi če jo program preživi in se nato povsem običajno zapre; nikoli ni
  bil pospravljen. In kdor je odgovoril „Ne", je uničil edine podrobnosti
  dogodka – zapisek je izginil že ob *prikazu* vprašanja. Oboje je
  odpravljeno: urejen konec zapisek pospravi, vpraša se le še po pravi
  prekinitvi, odkljuka pa se šele po vašem odgovoru. Podrobnosti tako ali
  tako stojijo v dnevniku napak na lastnem računalniku – kdor noče ničesar
  poslati, s tem vseeno ne izgubi ničesar. Pošlje se še naprej le tisto,
  kar ste prej v celoti videli in sami sprostili.

- **„Očisti" je lahko tiho ostal zaklenjen.** Če se jezikovni modeli
  obtičijo pri nalaganju, je gumb ostal izklopljen – brez razlage. Klik
  nanj ni storil nič, vrstica stanja pa je nespremenjeno govorila
  „Nalagajo se jezikovni modeli …", tudi po desetih minutah. Vzrok:
  motnje v ozadnjih tekih so šle na mesto, ki ga ob zagonu iz upravitelja
  datotek ne vidi nihče; ostalo je okno, ki je izgledalo delovno
  pripravljeno in se ni odzivalo na noben klik. Take motnje zdaj pristanejo
  v dnevniku napak, nalaganje jezikovnih modelov v vsakem primeru javi
  svoj neuspeh namesto tiho obupati, in če vseeno ostane tiho, aplikacija
  po treh četrtinah minute pove, da nekaj ni v redu, z nasvetom v
  podrobnostih. Zaklenjen gumb ob prehodu navede svoj razlog. Dolgo prvo
  nalaganje pri tem ne šteje za tišino – dokler se javlja napredek, ostane
  mirno. Kot sesutje to sploh ne šteje: aplikacija teče naprej, zato se ob
  naslednjem zagonu tudi ne vpraša po tem.

- **Na Macu program ni več našel posodobitev – in trdil, da je na
  najnovejšem stanju.** Različica za Mac ni prinesla imenika korenskih
  potrdil; iskala ga je na mestu, ki obstaja le na računalniku, kjer je
  zgrajena. S tem ni mogla pri nobenem strežniku preveriti, s kom govori,
  in je prekinila vsako povezavo: brez posodobitev, brez licenčnega
  odklepa, brez naknadnega nalaganja jezikovnih modelov, brez poročila o
  napaki. Starejše različice so iz tega tiho naredile informacijo
  „Uporabljate najnovejšo različico". Potrdila zdaj ležijo v samem
  programu; če jih tam ne najde, vzame sistemska in na Macu v skrajnem
  primeru tista iz zbirke ključev – in če jih sploh ni, to pove, namesto
  da bi trdil najnovejšo različico. Preverjanje samo se pri tem nikoli ne
  izklopi.

  To eno posodobitev morajo uporabniki Maca še vedno namestiti ročno:
  različica, ki ne doseže strežnika, se tudi ne more sama posodobiti.

### Spremenjeno

- **Glavno okno je pospravljeno.** Spodaj je stalo šest enako velikih
  gumbov drug ob drugem – „O …", „Navodila" in „Pomoč in FAQ" pod tem,
  čeprav so iste tri poti že stale v meniju Pomoč zgoraj. Zdaj so združeni
  v en gumb „Pomoč", ki jih razpre; nobena ne izgine. Spodaj ostaneta dve
  poti, s katerima se resnično začne: „Očisti" in „Počrni ročno …".

- **Kaj program ravno počne, zdaj stoji na trdnem mestu.** Sporočilo
  („Nalagajo se jezikovni modeli …", „(3 / 7) pismo.pdf", „5 od 7
  datotek(e) očiščenih.") je doslej viselo kot siv tekst med dvema
  vrsticama gumbov. Dobilo je lastno površino, s pobarvano piko spredaj:
  sivo, dokler nič ne teče, modro med delom, zeleno po gladkem zagonu in
  rumeno, kadar so nastala opozorila. Pika ne pove ničesar, česar ne bi
  stalo zraven – pove le hitreje.

- **Nastavitve so postale lastno okno.** Doslej so ležale v glavnem oknu –
  okvir s štirimi zavihki, ki se je razprl pod „Več nastavitev" in je bil
  nato premajhen za svojo vsebino: v njem je vedno stal drsnik, izbira med
  anonimiziranjem in psevdonimiziranjem pa je stala napol zunaj slike.
  Gumb se zdaj imenuje „Nastavitve …" in odpre okno s stransko vrstico;
  vsaka od štirih strani vanj v celoti sodi. Glavno okno se ob odpiranju
  ne razpre več, zraven pa je mogoče videti seznam datotek. Spremenilo se
  je le, kje nastavitve stojijo – katere so in kaj počnejo, je
  nespremenjeno.

- **„Podrobnosti" se razpre, namesto da bi skočilo.** Okno je doslej
  zraslo v enem trenutku, in nato je bilo treba iskati, kaj se je
  spremenilo. Zdaj se tja premakne.

- **Velikosti pisave in razmiki po celem oknu sledijo istemu merilu.**
  Naslovi so bili na dveh mestih različno veliki, enakovredne vrstice pa
  so stale različno narazen. Vidno je to kot mirnost, ne kot posamezna
  sprememba.

- **Anonimiziranje je zdaj privzeto.** Doslej je bilo privzeto
  psevdonimiziranje: iste osebe so dobile isto številko (`[IME_1]`,
  `[IME_2]`), povezave so ostale berljive – pravno pa so s tem ostale
  **osebni podatki**. Kdor ne nastavi ničesar, zdaj dobi postopek, ki
  podatke izvzame iz GDPR: vse najdbe neke vrste se imenujejo enako
  (`[IME]`). Oštevilčenje ostaja izbira, stoji nespremenjeno v istem
  oknu; obstoječe nastavitve ostanejo, kakršne so. Na ukazni vrstici
  `--pseudonymisieren` (tudi `--mit-nummerierung`) ponastavi nazaj.

- **Anonimiziranih ograd ni več mogoče posamično preklicati.** Kdor
  anonimizira, za vsako osebo dobi isto ogrado – in s tem ni več
  posameznega mesta, ki bi pripadalo določenemu imenu. Okno Popravi je
  kljub temu ponudilo „Prekliči zamenjavo": klik bi *eno* od vrednosti
  vstavil na *vsa* mesta. Vrstice so zdaj zamolčane kot pri zakritih
  navedbah, klik navede razlog, ročno dodana najdba pa ne dobi več
  številke, ki v preostalem dokumentu nikjer ne stoji.

  Iz istega razloga po anonimiziranem zagonu ni več „Prevedi odgovor
  nazaj" – prej bi na mesto vsake osebe postavil tuje ime. Kdor to zanko
  potrebuje, izbere „Psevdonimiziraj"; aplikacija to zdaj tudi tako pove,
  namesto da bi napotila na potekel pripis.

  Na ukazni vrstici se `--zuordnung` pri anonimiziranju zdaj prekine,
  namesto da bi zapisala datoteko, ki ni prevod nazaj – v oknu je bila
  kljukica že zdavnaj zaklenjena. Bodisi zraven `--pseudonymisieren` ali
  izpustite `--zuordnung`; sporočilo to pove. Rezultat pri tem sploh ne
  nastane, da skripta ne ostane s polovičnim delom.

- **Kanal posodobitev je na novo nastavljen na „Stabilno".** Brez lastne
  izbire se je kanal doslej ravnal po tem, iz katere izgradnje je izhajala
  tekoča različica – kdor je enkrat preizkusil testno različico, je odtlej
  trajno dobival ponujene testne različice. Menjava kanala je odločitev in
  naj tudi ostane taka; privzeto je zato „Stabilno". Nastavljeni kanali
  ostajajo nedotaknjeni.

### Izboljšano

- **„Postopek pritožbe" ne velja več za ime kraja.** V naslovu „Uradni
  zaznamek – Postopek pritožbe 12 C 345/26" je program zakril tudi
  postopek: jezikovni model ga je imel za kraj, in sicer neodvisno od
  okolice. Zajeta ni posamezna beseda, temveč **osnovna beseda**
  sestavljenke – „postopek" in „zaznamek" s tem pokrijeta tudi poslovni,
  knjigovodski in plačilni postopek ali telefonski zaznamek. Od trideset
  preverjenih upravnih izrazov so prej trije sprožili lažni alarm, zdaj
  noben več; še naprej se najde vse, kar stoji zraven („Postopek
  pritožbe: Bernd Meisinger" izgubi ime, ne naslova).

- **Anonimiziranje spet vodi evidenco – za naknadni pregled in
  dnevnik.** V anonimizirajočem načinu delovanja si program najdenih
  vrednosti ni zapomnil. Zaradi tega sta obmolknili dve stvari:
  dokumentno-širok naknadni pregled skladnosti (priimek, ki se pozneje
  pojavi sam, je ostal) in seznam zamenjav v dnevniku preverjanja. Dokler
  je bilo anonimiziranje redkejša izbira, to skoraj ni padlo v oči – kot
  privzeto bi postalo pravilo. V dokumentu se ne spremeni nič: ograda
  ostane brez številke.

- **„Ni osebnega datuma" se zdaj imenuje „ni osebne navedbe".** V
  pogovornem oknu preklica in v opozorilu o obrazih je stal pravni
  *datum* – ednina od „podatki". Bran je bil kot koledarski dan, še
  posebej ker aplikacija drugje ponuja „Odstrani tudi datumske navedbe".
  Zdaj se povsod imenuje „navedba", tako kot pri štirih razlogih nad njim
  v istem oknu.

- **Vrstica o izvoru stoji le še v oknu „O programu".** „Made with ♥ in
  Austria" je spodaj v glavnem oknu sedela sredi vrste gumbov in se tam
  brala kot še ena tipka. Ostaja v oknu „O programu" – tam, kjer jo
  iščete.

- **Odlagalna površina ima zdaj viden rob.** Njen črtkani rob je bil tako
  bled, da se je komaj ločil od okna – to je bilo vseeno, dokler je bila
  površina le površina. Odkar je gumb, ki ga je mogoče doseči s
  tabulatorko, je ta črta edino, kar jo kaže kot element upravljanja; zato
  je dvignjena na vrednost, ki jo za to zahteva norma.

## 0.10.22-beta.1 – 15. avgust 2026

### Novo

- **Kadar je nadzor odložišča izklopljen, je resnično izklopljen.** Stražar
  drži zadnjo vsebino v pomnilniku, da je mogoče izvirnik vrniti nazaj –
  doslej tudi takrat, ko ste nadzor izklopili. Zdaj se zgodovina ob izklopu
  pozabi. To stane obnovitev po izklopu, in prav tako je mišljeno: izklopljeno
  pomeni izklopljeno.
- **Dnevnik napak ne vsebuje več poti do datotek.** Ležal je le na vašem
  računalniku in se nikoli ni samodejno pošiljal – vseboval pa je poti v
  golem besedilu, ime datoteke pa pogosto razkrije več kot vsebina. Iz
  „…/Locitev_Mueller_Primerjava.docx" zdaj ob zapisu nastane `<datoteka>.docx`;
  pripona ostane, ker šteje pri iskanju napake. Enako velja za zapisek po
  sesutju.
- **Seznam zamenjav zdaj opozarja sam v sebi.** To je edina datoteka, v
  kateri so vaši izvirni podatki v golem besedilu, in leži ob rezultatu –
  kdor posreduje mapo, posreduje tudi njo. Opozorilo zdaj stoji kot prva
  vrstica **v** datoteki, izhodno območje navede polno pot namesto le imena
  datoteke, na ukazni vrstici pa se datoteka sploh šele omeni: dotlej se
  tam sploh ni izvedelo, da je nastala.
- **Anonimiziranje ali psevdonimiziranje je zdaj poimenovana izbira.** Na tem
  mestu je doslej stala kljukica „Ista imena poimenuj enako – UI potem še
  vedno prepozna, kdo je kdo". Ta je opisovala korist in prikrila posledico:
  oštevilčene ograde (`[IME_1]`, `[IME_2]`) so **psevdonimizacija**, in
  psevdonimizirani podatki ostajajo osebni podatki – kdor je mislil, da je s
  tem anonimiziral, se je motil. Zdaj stojita oba postopka drug ob drugem,
  vsak s svojo ceno. Privzeto ostaja psevdonimiziranje, ker dokument, ki se
  nato še bere ali obdeluje z UI, potrebuje svoje povezave. Pri anonimiziranju
  je seznam zamenjav zaklenjen: naredil bi rezultat spet sledljiv nazaj.
  Priročnik in pogosta vprašanja razložijo razliko v vseh 18 jezikih; na
  ukazni vrstici se stikalo zdaj imenuje tudi `--anonymisieren`.
- **Vrstica nad odlagalno površino zdaj pove, kaj resnično drži.** Obljubljala
  je „100-odstotno krajevno obdelavo – brez oblaka in računa, prijazno GDPR".
  Za vaše dokumente to drži, za program pa ne v tej pavšalnosti: išče
  posodobitve, na željo javi napake, naknadno naloži modele in prijavi
  kupljena delovna mesta. Zdaj tam stoji ožja in vzdržna trditev: vaši
  dokumenti ne zapustijo računalnika.
- **Pri rezultatu zdaj vedno piše, da ga je treba preveriti.** Doslej je
  Maskuro po gladkem zagonu javil „Odstranjenih navedb: 12" v zeleni barvi in
  sicer nič drugega – to se bere kot zagotovilo, da je bilo najdeno vse.
  Opozorila so se pojavila le, kadar konkretno nečesa ni bilo mogoče preveriti
  (slike, neznane priloge). Zdaj pod vsakim rezultatom nespregledljivo piše,
  da niso v vsakem primeru prepoznani vsi osebni podatki, da je preverjanje
  na uporabniku in da je manjkajoče treba dopolniti ročno – v oknu, v
  izhodnem območju in na ukazni vrstici. Ni pojavnega okna za odkljukati:
  stavek stoji tam trajno. Kratka navodila zdaj to povedo z istimi besedami.
- **Po posodobitvi ob zagonu piše, kaj se je spremenilo.** Doslej je
  posodobitev potekla tiho in je ni bilo mogoče ločiti od ponovnega zagona.
  Zdaj se enkratno prikaže „Kaj je novega" – in kdor je preskočil kakšno
  različico, vidi tudi vmesne. Ne pri čisto prvem zagonu: tam še naprej uvaja
  kratka navodila.
- **Kitajščina in japonščina zdaj najdeta imena.** Doslej nista našli
  **nobenega** – ne malo, nobenega. Obema jezikovnima modeloma je manjkala
  segmentacija besed, brez katere stavek brez presledkov velja za eno samo
  besedo; program je tiho preklopil na večjezični nadomestni model. Oba
  jezika zdaj prepoznata osebe in kraje kot ostali. Japonski slovar se pri
  tem naloži skupaj z jezikom in ne leži v programu – sam bi obsegal dobrih
  200 MB, ki bi jih sicer nosil vsak.
- **Romunija je izbirljiva kot država.** Doslej je popolnoma manjkala. S tem
  se prepoznajo romunski naslovi („Strada Victoriei 30"), poštne številke s
  krajem („010061 București") in Cod Numeric Personal – slednji le z
  ustrezno kontrolno številko, da se ne označi vsaka trinajstmestna številka
  na računu. Do zdaj je v romunskih dokumentih poštna številka ostajala
  berljiva ob zakritem imenu kraja.
- **„Rastriraj stran" v urejevalniku.** Če besedila iz PDF-ja ni mogoče
  odstraniti – to se zgodi pri datotekah tujih ustvarjalcev –, se stran
  zdaj na željo nadomesti s svojo odslikavo: besedilo je s tem nepovratno
  odstranjeno, stran pa ostane berljiva in iskana. Opozorilo, ki javi ta
  primer, korak ponudi kar kot gumb; prek „Orodja → Rastriraj stran" gre
  tudi sam od sebe. Razveljavi stran vrne nazaj.
- **Vmesnik je zdaj na voljo tudi v hrvaščini, grščini, litovščini,
  slovenščini, japonščini in korejščini.** S tem jih je osemnajst.
  Priročnik, pogosta vprašanja in pravna besedila so v vseh šestih v celoti
  na voljo. Oznake v očiščenem dokumentu pri tem sledijo vmesniku – iz
  `[NAME_1]` nastane `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` ali `[氏名_1]`.
  **Pri grščini, japonščini in korejščini oznake stojijo latinično** –
  `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. Vmesnik ostaja v svoji lastni
  pisavi; le tisto, kar se zapiše v dokument, je latinično. Razlog je nabor
  znakov PDF: tam so grške in japonske oznake prej prispele kot `[??_1]`, s
  čimer imena ni bilo več mogoče ločiti od kraja.
- **Devet držav se pridruži, sedem obstoječih pa postane popolnih.** Na
  novo se prepoznajo osebne, davčne in socialnozavarovalne številke skupaj
  z naslovi za **Hrvaško, Slovenijo, Grčijo, Litvo, Severno Makedonijo,
  Rusijo, Ukrajino, Kitajsko in Japonsko**. Pri obstoječih državah so
  zaprte vrzeli, ki so tehtale huje: za **Nizozemsko** in **Portugalsko**
  doslej sploh ni bilo osebne številke – nizozemski BSN in portugalski NIF
  se nista prepoznavala, čeprav stojita na praktično vsaki listini teh
  držav. Poljska dobi davčno številko NIP, Danska, Norveška in Finska
  svoje naslove, Kanada svojo poštno številko. S tem jih je **35 držav**.

### Odstranjeno

- **Za Linux zaenkrat ni več paketa.** Izvorna koda tam teče, a manjkajo
  tri stvari, ki jih ta priročnik obljublja pod Linuxom: samodejni zagon,
  globalne tipkovne bližnjice in – odvisno od delovnega okolja – ikona v
  vrstici. Dostaviti paket, ki zmore manj, kot je opisano, bi bila napačna
  pot. Windows in macOS nista prizadeta.

### Izboljšano

- **Opravilne številke se zdaj najdejo v vseh jezikih.** „Aktenzeichen
  12/2026-AB" je bilo odstranjeno, „File reference 12/2026-AB" ali
  „Sygnatura 12/2026-AB" pa je ostalo: besede polj, po katerih Maskuro tako
  številko prepozna, so obstajale le v nemščini. Zdaj pozna ustreznice v
  dvanajstih jezikih – in kot doslej se zamenja le številka, oznaka pred
  njo ostane, da je v rezultatu razvidno, kaj je bilo tam odstranjeno.
- **Maskuro v mirovanju porabi približno pol gigabajta manj.** Ob zagonu se
  je doslej naložil tudi dodatni model natančnejšega prepoznavanja, da prvo
  čiščenje nanj ne bi čakalo. Izmerjeno je to stalo 648 MB pomnilnika in
  prihranilo 1,9 sekunde – in stalo je tudi takrat, ko ste okno le odprli
  in spet zaprli. Model se zdaj naloži prvič, ko je potreben; vrstica
  stanja to sporoči. Jezikovni model se še naprej naloži ob zagonu – to
  nadzor odložišča potrebuje takoj.
- **Odlagalno površino je zdaj mogoče upravljati tudi brez miške.**
  „Povlecite datoteke sem" je bila površina, ki se je odzivala na klike – s
  tipkovnico do nje ni bilo mogoče priti, bralnik zaslona pa jo je prebral
  kot okvir z besedilom v njem, ne kot to, kar je. Zdaj je gumb: tabulatorka
  skoči nanjo, preslednica in vnašalka odpreta izbiro datotek, kdor je
  nanjo skočil, pa to vidi po robu. Prek menija „Datoteka → Izberi
  datoteke" je šlo že prej, a to je bilo treba vedeti.
- **Ime očiščene datoteke se zdaj tudi prebere na glas.** V seznamu datotek
  stoji kot druga, manjša vrstica pod izvirnikom – a bila je le narisana, in
  bralnik zaslona je imenoval le izvirnik. Prav ta vrstica je zgrajena
  proti zmoti, da je bil zagon brez učinka, ker v mapi leži nedotaknjen
  izvirnik. Vrstica se zdaj prebere kot „racun.pdf, rezultat:
  racun_ociscen.pdf".
- **Elementi za upravljanje brez oznake zdaj povedo, čemu služijo.**
  Simbolni gumbi v seznamu datotek, gumbi z znaki v oknu Popravi ter vsa
  izbirna in vnosna polja so bila za bralnike zaslona brezimna – naznanjena
  so bila kot „gumb" in „spustno polje", brez česa. Gumbi v vrstici pri tem
  navedejo tudi datoteko: na seznamu z dvajsetimi vnosi bi sicer dvajsetkrat
  slišali isti stavek.
- **Kdor upravlja s tipkovnico, spet vidi, kje se nahaja.** Gumb „Očisti" in
  simbolni gumbi v seznamu datotek so barvno zasnovani, s tem pa je nehal
  veljati rob, ki ga sistem sicer nariše okoli elementa, na katerega je bilo
  skočeno – pri tabulaciji je pogled skočil v prazno. Oba zdaj dobita
  lasten rob, takoj ko sta na vrsti. Gumba pri tem ne spremenita velikosti.
- **Sedem barv pisave je bilo prebledih, v obeh videzih.** Izmerjeno po
  običajni normi (WCAG 2.1) so blede opozorilne vrstice, stranska besedila
  na odlagalni coni, točke navodil in v temni sliki dodatno modra in rdeča
  ležale pod mejo 4,5:1 – berljivo pri dobri svetlobi in dobrem vidu,
  sicer ne. Vse so dvignjene; stopnjevanje ostaja, besedila se še naprej
  berejo kot stranska. Tri nadaljnje – barve, v katerih se javljajo
  opozorila in uspeh – so mejo komaj držale in so bile dvignjene skupaj:
  kdor jih ne prebere, ne prebere obvestila, ali je kaj šlo narobe. Vidno se
  je pri tem spremenil le gumb „Očisti" v temni sliki: zdaj nosi temno
  namesto belo pisavo, kot poudarjeni gumbi Windows 11 tudi.
- **Vsaka vrstica seznama datotek ima zdaj svoj križec.** Doslej je bilo
  treba vrstico najprej izbrati in nato klikniti „Odstrani" – dva koraka za
  malenkost. Križec stoji desno v vrstici in potrebuje enega. Gumb
  „Odstrani" pod njim je s tem odpadel; kdor se hoče znebiti več vrstic
  naenkrat, jih izbere in vzame vnos v kontekstnem meniju, ki tudi pove,
  koliko jih je. „Odstrani vse" ostaja. Iz seznama se vedno vzame le
  vrstica – nikoli datoteka na disku.
- **Pred preverjanjem UI zdaj piše, ali je ta računalnik za to primeren.**
  Doslej je v oknu stalo le, kako velik je model. Kdor ga je vklopil na
  šibkem računalniku, je šele pri prvem dokumentu opazil, da traja zelo
  dolgo – po 5,4 GB prenosa. Zdaj okno **vnaprej** navede pomnilnik in
  prost prostor ter pove, kaj to pomeni; **potem** se izmeri hitrost in
  navede v velikosti, za katero gre: „Desetstranski dokument na tem
  računalniku traja približno 12 minut." Če je prepočasi, program odsvetuje
  in ponudi, da se stopnja spet izklopi – nič pa ne prepoveduje.
- **Meritev hitrosti zdaj teče na vsakem računalniku.** Doslej se je
  pojavila le, če je bila dodatno nastavljena grafična pospešitev – ki
  obstaja le pod Windows. Na vseh drugih računalnikih je program zato
  trajanje ocenil po tujem računalniku, in prav tam, kjer je počasen, je
  ocena zgrešila.
- **Turški naslovi se zdaj najdejo tudi na skenu.** Na skeniranem glavi
  dopisa je „34710 İstanbul" ostal berljiv, medtem ko je ista navedba v
  besedilu zraven izginila: optično prepoznavanje bere turški İ brez
  njegove pike, vzorec pa je pričakoval veliko črko. Enako je veljalo za
  „Bağdat Caddesi".
- **Španski naslovi brez lastnega imena ulice se najdejo.** „Gran Vía 5" je
  ostal, ker je vzorec za vrsto ulice pričakoval še besedo imena – pri
  „Calle Mayor" jo ima, pri „Gran Vía" pa je vrsta sama že ime. Enako zdaj
  velja za „La Rambla" in „Castellana".
- **V oknu „O tem programu" zdaj stoji opozorilo o preglednosti** glede
  tega, da je bila aplikacija razvita s podporo umetne inteligence. Zadeva
  nastanek programa, ne njegovega delovanja: čisti se še naprej izključno
  na lastnem računalniku.
- **„Upravljanje jezikov" zdaj prikaže uporabne jezike najprej.** Za
  polovico od 48 jezikov ni lastnega jezikovnega modela; tam večjezični
  nadomestni model imena prepozna le šibko, v nekaterih pisavah sploh ne.
  Drug ob drugem so na seznamu izgledali enakovredno. Privzeto se zato
  prikažejo le jeziki z lastnim modelom – prek „Prikazano" je preostale
  mogoče kadar koli prikazati, s stavkom o tem, kaj zmorejo in kaj ne.
  Nič ne odpade, in kdor je nastavil omejen jezik, ga obdrži.
- **Vprašanje o manjkajočem jeziku zdaj navede izhod.** Če se prepozna
  jezik, za katerega še ni nič nastavljeno, je program doslej ponudil le
  „Naloži" ali „Nadaljuj brez". Prepoznavanje pa se lahko zmoti – pri
  kratkih obrazcih in seznamih z malo tekočega besedila odloča le nekaj
  besed. V oknu zato zdaj piše, da je mogoče prekiniti in pravi jezik
  izbrati ročno, namesto uporabe „Samodejno prepoznaj". To v dvomu
  prihrani prenos več sto megabajtov za jezik, ki sploh ni potreben.
- **Oznake ograd zdaj govorijo jezik vmesnika.** „[NAME_1]", „[ADRESSE_2]"
  in podobne so doslej vedno stale v nemščini, ne glede na to, kateri jezik
  je bil nastavljen ali v katerem jeziku je dokument napisan. Zdaj sledijo
  jeziku vmesnika – pri angleščini torej „[NAME_1]", „[ADDRESS_2]". Ne
  jeziku dokumenta: ta je pri „samodejno prepoznaj" uganjen in včasih
  napačen; jezik vmesnika nikoli ni.
- **Manj vprašanj pri dodelovanju.** Kam se rezultat shrani, zdaj trajno
  piše spodaj v vrstici („→ pogodba_ociscena.pdf", v namigu mapa) – klik
  nanj izbere drugo mesto, ne da bi takoj shranil. S tem odpade povratno
  vprašanje ob prvem shranjevanju. Vprašanje „že obdelano – začeti znova?"
  si je mogoče zapomniti za sejo, dve opozorilni okni, ki sta dajali le eno
  informacijo, pa zdaj stojita v vrstici stanja. Ostala so vprašanja, ki
  preprečujejo nepovratno škodo: neshranjeno delo pri zapiranju in
  opozorilo o neodstranjenem besedilu.
- **Rezultat zdaj pove, kje sam sken ni bil berljiv.** Na skeniranem
  dokumentu optično prepoznavanje naprave ne prebere vsega pravilno – iz
  „Solarstraße 9" nastane na primer „Solaret^aß« B". Kar je bilo tako
  napačno prebrano, ne najde več nobeno preverjanje: za vsak iskalni vzorec
  izgleda kot solata iz črk. Program tega ne more spremeniti, a taka mesta
  zdaj poimenuje s številko strani – večinoma tam tičijo žigi, glave dopisov
  ali ročno dodani pripisi. Opozorilo, ne svarilo: pri postavljenem
  dokumentu ga ni.
- **Seznam datotek zdaj kaže, kako se imenuje rezultat.** Pod imenom
  datoteke po zagonu stoji ime očiščene datoteke („→
  pogodba_ociscena.pdf"). Doslej je stalo le v dnevniku za „Podrobnosti", in
  kdor je pogledal v mapo, je našel nedotaknjen izvirnik. Ime vira ostane –
  sicer ne bi bilo več videti, iz katere datoteke rezultat izhaja.
- **Gumbi v dokončani vrstici so večji in jasnejši.** Ogled, dodelovanje in
  „Pokaži v mapi" so bili ploščati simboli brez površine in so na seznamu
  izginjali – čeprav so po zagonu edino, kar se še klika.

### Odpravljeno

- **Na tujejezičnem vmesniku so bila lastna pravila zakrivanja, maskiranja
  in razprševanja tiho prezrta.** Kdor je določil, da se imena zakrijejo
  namesto zamenjajo, je vseeno dobil zamenjana – takoj ko program ni deloval
  v nemščini ali angleščini. Nastavitev je stala tam, le delovala ni, in v
  rezultatu razlike ni bilo videti. Prizadetih je bilo devet od dvanajstih
  jezikov vmesnika.
- **Nastavitev „Jezik oznak" izven nemščine in angleščine ni imela
  učinka.** „Nemščina" in „angleščina" sta bili izbirljivi, v dokumentu pa
  je še naprej stal jezik vmesnika. Zdaj delujejo vse tri možnosti; privzeta
  nastavitev „kot vmesnik" nespremenjeno da isto kot doslej.
- **V kratkih odlomkih besedila so imena ostajala – na primer v kopiranem
  citatu iz pošte.** Kdor je odlomek očistil prek odložišča, je tam pogosto
  dobil zakrit le e-poštni naslov, ime pod njim pa ne. Odločalo je golo
  število vrstic: od šestih vrstic naprej je program odlomek prepoznal kot
  razpredelnico in našel imena, pod tem ne – kopiran citat pošte jih ima
  pet. Poljubna dodatna vrstica, na primer zadeva, je izid prevesila. Zdaj
  zadoščajo štiri vrstice, in pri meritvi izginejo vsa preverjena imena
  namesto tretjine. Na daljše dokumente in na tekoče besedilo to ne
  vpliva.
- **Grafična pospešitev preverjanja UI se je doslej znova izklopila, takoj
  ko ste jo nastavili.** Po nastavitvi program izmeri, ali je grafika na tem
  računalniku resnično hitrejša od procesorja – ta meritev pa je vedno
  spodletela, ne da bi to povedala, in izid „oba enako hitra" je odločil za
  procesor. Kdor je naložil 65 MB, je po tem dobil manj kot prej. Meritev
  zdaj teče; če spodleti, ne spremeni več ničesar.
- **Ocena časa je na vsakem računalniku računala s tujo hitrostjo.**
  Opira se na isto meritev; dokler ta ni tekla, je veljala vrednost
  razvojnega računalnika. „Približno dve minuti" je tako na počasnem
  računalniku lahko pomenilo pol ure.
- **Stopnja UI dela z novim, znatno boljšim jezikovnim modelom**
  (Qwen3.5-9B namesto Qwen3-4B) in ni več omejena na nemščino in angleščino,
  temveč dela v dvanajstih jezikih. Izmerjeno prek preizkusnega korpusa:
  enako veliko najdenih navedb kot brez stopnje, a manj kot polovica
  odvečnih zakritij (75 → 31). Model je večji (5,4 namesto 2,4 GB) in
  potrebuje približno dvakratni računski čas; ob vklopu se enkratno naloži,
  stari se pri tem odstrani.
- **Naslovi v francoščini, italijanščini, španščini, portugalščini,
  poljščini, turščini in švedščini se zdaj v celoti odstranijo.** Doslej je
  tam izginilo le ime ulice in kraja – hišna številka in poštna številka sta
  ostali berljivi („[KRAJ_1] 28, 28013 [KRAJ_2]"). Za te jezike ni bilo
  lastnih naslovnih vzorcev; zdaj so dopolnjeni.
- **Grščina in korejščina nista našli nobenega imena.** Pri grščini je bil
  vzrok nadomestni model – z lastnim modelom, ki se zdaj da naložiti, se
  imena in kraji čisto prepoznajo. Pri korejščini je bil vzrok v programu:
  predpostavljal je, da se ime začne z veliko črko, hangul pa velikih črk ne
  pozna. Prizadete so bile predvsem kratke enote – celice tabel, polja
  obrazcev, vnosi na seznamih.
- **Jezikovni model, ki se ni dal naložiti, je prekinil čiščenje.** Namesto
  sporočila o napaki zdaj vskoči večjezični model, rezultat pa opozori, da
  je bilo delano s šibkejšim prepoznavanjem. Trenutno zadeva kitajščino in
  japonščino, katerih modela potrebujeta ločevanje besed, ki programu še ni
  priloženo.
- **Jezik z lastnim modelom je veljal za nameščen, takoj ko je bil naložen
  kateri koli drug.** Kdor je na primer nastavil turščino, je s tem dobil
  večjezični nadomestni model – kitajščina, japonščina, korejščina ali
  grščina so nato na seznamu stale z nastavljeno kljukico in „0 MB", čeprav
  je njihov lastni model manjkal. S tem jih ni bilo nikoli mogoče naknadno
  naložiti in so trajno delovale z okrnjenim nadomestkom. Zdaj seznam kaže
  dejansko stanje skupaj z velikostjo nalaganja.
- **Odpovedana stopnja prepoznavanja je molčala.** Če je bilo vklopljeno
  „Razširjeno prepoznavanje" ali „Največje prepoznavanje (UI)", modela pa ni
  bilo mogoče izvesti, je program deloval naprej brez te stopnje – brez
  besede o tem. Rezultat je izgledal kot vsak drug, stikalo pa je še naprej
  stalo na „vklopljeno": rezultat osnovne stopnje ste tako imeli za
  najboljše, kar je bilo mogoče dobiti. Rezultat zdaj to pove in navede
  oboje – kaj ni bilo preverjeno in kako se model znova naloži. Primer ni
  redek: na nekaterih računalnikih stopnja UI ob nalaganju odpove, kadar
  manjka grafična pospešitev.
- **Napaka pri nalaganju dodatnega modela je prekinila celotno čiščenje.**
  Pri „Razširjenem prepoznavanju" je bilo zavarovano le vrednotenje modela,
  ne njegovo branje – in prav tam gre kaj narobe, če je datoteka poškodovana
  ali ne ustreza računalniku. Namesto sporočila o napaki je zdaj rezultat
  osnovne stopnje skupaj z opozorilom.
- **Jezika ni bilo več mogoče odstraniti – in s tem tudi ne znova
  naložiti.** Kdor je v „Upravljanju jezikov" odstranil kljukico in
  potrdil spremembo, je prebral „Nemščina odstranjena", a je kljukico takoj
  spet videl nastavljeno. Vzrok je bil prevzem iz programske mape: pri
  namestitvi za vse uporabnike ležijo jezikovni modeli zaščiteni pred
  pisanjem v programski mapi, in program manjkajoče od tam prevzame, namesto
  da bi na novo naložil sto megabajtov. Ta prevzem je tekel ob vsakem
  dostopu – in ravno izbrisani jezik je v istem dihu kopiral nazaj. Zdaj se
  zgodi enkratno; naknadno naloženi jezikovni modeli pri tem ostanejo
  ohranjeni. Poleg tega program po brisanju preveri: kar se ni dalo
  odstraniti, se zdaj javi kot neuspeh namesto kot „odstranjeno".
- **Pri namestitvi za vse uporabnike se naknadno naloženega ni dalo
  odložiti.** Kdor program namesti za vse uporabnike, ga ima v „Programih",
  kamor brez skrbniških pravic ni mogoče ničesar pisati. Za jezikovne
  modele je bilo za to že zdavnaj predvideno nadomestno mesto, za drugo ne:
  - **Komponenta pogleda strani** se je po 290 MB prenosa razpakirala v
    programsko mapo in tam spodletela – ne da bi navedla razlog. Zdaj leži
    pri jezikovnih modelih, kjer bi po namenu morala biti ves čas.
  - **Grafična pospešitev** se ne more umakniti: menja knjižnice v samem
    programu. Namesto da bi se najprej naložila in nato brez besede
    spodletela, program zdaj vnaprej pove, da tu ne gre in kaj to pomeni –
    največje prepoznavanje deluje naprej, le prek procesorja.
  - Priloženega **jezika optičnega prepoznavanja besedila** ni bilo mogoče
    odstraniti: iz programske mape se je takoj obnovil. Isti vzrok kot pri
    jezikovnih modelih, ista odprava.
  - Pri odstranjevanju jezika so se lahko izbrisali **jezikovni podatki tuje
    namestitve Tesseract**. Zdaj se dotakne le lastne mape.
  - Nadomestno mesto je doslej veljalo le pod Windows. Linux arhiv v `/opt`
    je imel isto stisko brez istega izhoda.
- **Pri dodelovanju je izginila cela vrstica, čeprav je bila obkrožena le
  ena beseda.** Kdor je v že očiščeni datoteki zakril ogrado, je izgubil
  vrstico, v kateri je stala: iz „Spoštovana gospa doktorica [IME_1]" ni
  ostalo nič – sporočilo pa je pri tem navedlo „iz dokumenta odstranjena
  ena beseda". Prizadeta je bila vsaka datoteka, ki je že enkrat šla skozi
  program, torej ravno primer, za katerega obstaja dodelovanje. Preostalo
  besedilo zdaj ostane, na nespremenjenem mestu.
- **„EMPLOYEES" nad seznamom imen je bilo samo zakrito.** Isti primer kot
  „MITARBEITER" v 0.10.19, le v angleščini – tam je ostal. V velikih črkah
  jezikovnemu modelu manjka razločevalno znamenje, naslov pa stoji nad
  samimi pravimi imeni. Imena pod njim se še naprej najdejo. „staff" ni bil
  vključen: to je zaseden priimek, in vnos bi s seboj potegnil vsakega
  „Johna Staffa" – enak preudarek kot nekoč pri „Arbeiter".
- **Pravna oblika je bila zamenjana drugič.** Na skeniranem glavi dopisa je
  jezikovni model prebral „d.o.o.", naslov in poštno številko kot **en**
  kraj. Naslov in poštna številka sta si nato izrezala svoja kosa, ostala
  pa je pravna oblika kot lastna najdba: v rezultatu je stalo „[KRAJ_1]
  [KRAJ_2]", kjer je bilo mišljeno „[KRAJ_1] d.o.o.". Ime podjetja se še
  naprej zamenja – le goli dodatek zdaj ostane, in rezultat se bere kot
  glava dopisa namesto kot vaja z vrzelmi.
- **Prikrojena najdba se ni preverila znova.** Vzrok primera zgoraj, in sega
  dlje: filtri proti uganjenim najdbam so delovali na tem, kar prepoznavalniki
  **javijo** – ne na tem, kar ostane po razrešitvi prekrivanja. Če je dolga
  najdba obrezana pri močnejšem prepoznavalniku, je delec drugo besedilo od
  ocenjenega, in nihče si ga ni znova ogledal. Zdaj se.
- **„Uporabljate najnovejšo različico" – čeprav sploh ni bilo mogoče
  preveriti.** Kdor je kot kanal posodobitev nastavil „Predizdaja (beta)"
  ali „Stabilno – priporočeno", je dobil to sporočilo, čeprav na teh
  kanalih doslej sploh ni nič izšlo. Program zdaj pove prav to – in
  predlaga, naj se v nastavitvah izbere drug kanal.
- **Zapiranje okna med nalaganjem je povzročilo sesutje niti.** Kdor je
  zagnal Maskuro in okno takoj spet zaprl, medtem ko so se jezikovni modeli
  še nalagali, je v dnevniku dobil poročilo o napaki: nalaganje se je
  javilo oknu, ki ga ni bilo več. Vidnih posledic ni bilo, v dnevniku pa je
  stalo sesutje, kjer je bil nekdo le hitrejši od programa.
- **Rezultat se zdaj ogleda, ne le prebere.** Doslej je stran veljala za
  čisto, če vrednosti ni bilo več v besedilu. Na skenu to ni dokaz – tam je
  vidno besedilo slika. Zato se na koncu preveri, ali je površina v
  rezultatu resnično zakrita; če tam še stoji svetel papir, to poročilo
  izrecno pove, namesto da bi javilo „zamenjano".
- **Zamenjana navedba je ostala vidna na sliki.** Če je vrednost stala na
  sliki – skeniran glavi dopisa, žig, cela skenirana stran –, je bila sicer
  odstranjena iz besedila dokumenta, a je bila še naprej **vidna**: kar
  vidi človek, so tam slikovne točke. Poročilo je kljub temu javilo
  „zamenjano". Zdaj se površina na sliki zakrije, ne glede na nastavljeno
  strategijo, ograda pa stoji svetlo na tej podlagi – grdo, a pošteno, in
  pripis ostane ohranjen. Če slikovnega formata ni mogoče obdelati, to
  rezultat zdaj izrecno pove, namesto da bi izgledal čisto.
- **Na skenu je ograda povsem manjkala.** Besedilna plast skenirane strani
  se izriše nevidno, in ograda, ki je bila vstavljena vanjo, je to
  podedovala: nastavljena, a nevidna. Na mestu najdbe ni nato stalo nič.
- **Optično prepoznavanje besedila, ki sploh ni moglo teči, je veljalo za
  uspešno.** Če je manjkala jezikovna datoteka ali je prepoznavalni stroj
  odpovedal, je poročilo javilo „Slike so bile preverjene z optičnim
  prepoznavanjem besedila (0 najdb)" – torej preverjanje, ki se nikoli ni
  zgodilo. Pri skenu je to edino preverjanje sploh: pogodba z berljivim
  naslovom v sliki strani je s tem veljala za dokončano. Poročilo zdaj pove,
  da ni bilo preverjeno nič, in zakaj.
- **Jezikovna datoteka se je iskala v napačni mapi.** Če so v lastnem
  jezikovnem imeniku ležali drugi jeziki kot jezik dokumenta, je
  prepoznavalni stroj dobil prav ta imenik in spodletel – čeprav je ustrezen
  jezik ležal zraven. Zdaj se išče **jezik**, ne mapa.
- **Opozorilo o neodstranjenem besedilu je svetovalo nekaj, česar ni.**
  Napotilo je na „Počrni kot PDF" – to pa ustvari pogled PDF za datoteke
  *pisarniških* programov in pri PDF-ju sploh ni na voljo. Kdor je hotel
  slediti opozorilu, ga je iskal zaman. Zdaj tam stoji gumb, ki stvar
  opravi.
- **V urejevalniku sta proga in ograda pristali ob označenem mestu.**
  Prizadet je bil vsak PDF, v katerem se vrstica konča na vezaju in se
  beseda nadaljuje v naslednji – pri skenih to posebej pade v oči, ker so
  pogodbeni teksti dosledno deljeni. Obe polovici vrstice sta veljali za
  *eno* besedo, ki sega počez čez stavčno zrcalo, in vsak okvir v njeni
  bližini je prevzel to razsežnost. Prepoznavanje samo se s tem ne
  spremeni: merilni korpus daje enak rezultat kot prej.
- **Urejevalnik je opozarjal, da besedilo „še vedno stoji v dokumentu",
  čeprav je bilo odstranjeno.** Če se je ista beseda na strani pojavila
  večkrat – v pogodbah pravilo –, je samopreverjanje po vsakem posegu javilo
  neuspeh. Zdaj šteje pojavitve, namesto da bi le preverilo, ali beseda
  sploh še kje stoji. Pri resničnem neuspehu opozori nespremenjeno.
- **Datoteka rezultata se je v vsakem jeziku imenovala „_bereinigt".**
  Mišljeno je bilo vedno, da dodatek imena sledi jeziku vmesnika – v
  angleščini je to tudi počel („_cleaned"), v preostalih šestnajstih jezikih
  ne. Kdor je program uporabljal v finščini, je dobil
  „asiakirja_bereinigt.pdf". Zdaj se datoteka imenuje „asiakirja_puhdistettu.pdf",
  v japonščini „書類_除去済み.pdf" in tako naprej – vsakič z besedo, ki jo
  isti vmesnik uporablja v svojem sporočilu o dokončanju. Kdor je nastavil
  lasten dodatek, ga obdrži.
- **„Upravljanje jezikov" se je vedno označevalo nemško.** Na seznamu 48
  jezikov dokumentov so stala nemška imena, ne glede na nastavljen vmesnik:
  finski uporabnik je bral „Chinesisch". Zdaj tam stoji ime v njegovem
  jeziku, za njim pa lastno ime – „Kiina (中文)". Lastno ime je namerno:
  kdor jezik prepozna po lastnem imenu, ga najde tudi, kadar mu finska
  beseda nič ne pove.

## 0.10.19 – 12. avgust 2026

### Izboljšano

- **Vnos v kontekstnem meniju zdaj govori vaš jezik.** Doslej je bilo tam
  na vsakem sistemu nemško besedilo – tudi na angleškem Windowsu. Zdaj
  sledi nastavljenemu jeziku vmesnika, in kdor spremeni jezik, dobi vnos
  takoj preimenovan, brez ponovne namestitve. (Windows; pod macOS in
  Linuxom je ime menija hkrati ime datoteke – to pride pozneje.)
- **Urejevalnik si zapomni, v katerem pogledu ste nazadnje delali.** Kdor
  uporablja predogled strani, ga pri naslednjem dokumentu dobi samodejno –
  brez vsakokratnega vklopa. Kdor ga ni nikoli uporabil, ne opazi ničesar:
  obnovi se le, če je potrebni gradnik že naložen, nikoli se zaradi tega
  ničesar ne naloži naknadno.

### Odpravljeno

- **„MITARBEITER" nad seznamom imen je bilo samo zakrito.** V imenikih
  zaposlenih in organigramih je naslov izginil kot domnevno ime – stoji nad
  samimi pravimi imeni, in v velikih črkah jezikovnemu modelu manjka
  razločevalno znamenje. Imena pod njim se še naprej najdejo.
- **Količinske navedbe so veljale za naslove.** V računih, dobavnicah in
  skladiščnih seznamih so izginile navedbe, kot so „3390 zapisnik", „1030
  znesek" ali „3390 skladišče", kot domnevna poštna številka s krajem –
  štirimestno število je videti kot avstrijska poštna številka. Če za
  številko stoji beseda, ki jo aplikacija pozna kot stvarno besedo, oddelek,
  dejavnost ali oznako polja, zdaj ostane. Prave krajevne navedbe so
  nedotaknjene, tudi tiste, ki so hkrati taka beseda („4692 kraj"). S tem ni
  rešen primer, ko za številko stoji povsem navadna beseda („3390 polica") –
  za to je potreben imenik poštnih številk.
- **Pomoč je omenjala menijsko postavko, ki ne obstaja.** Navodila, slika
  in sporočilo ob koncu namestitve so govorili o „Dokument za UI očistiti";
  postavka v kontekstnem meniju pa se imenuje „Odstrani osebne podatke".
  Kdor je sledil pomoči, je iskal zaman. Vsa tri mesta zdaj imenujejo
  menijsko postavko tako, kot se resnično imenuje.
- **„Zagon s sistemom" se ni dalo izklopiti.** Kdor je ob namestitvi
  obkljukal „Zaženi z Windows", je v nastavitvah kljub temu videl prazno
  kljukico – in huje: vklop in izklop v aplikaciji je ostal brez učinka,
  program se je še naprej zaganjal z Windows. Vzrok sta bili dve mesti,
  kjer Windows išče zagonske programe; aplikacija je poznala le eno od
  njiju. Zdaj šteje oboje, stikalo kaže resnično stanje in učinkuje v obe
  smeri. Upoštevano je tudi: kdor izklopi vnos v Upravitelju opravil, to
  zdaj vidi v aplikaciji – in kdor ga tam znova vklopi, s tem prekliče
  izklop.
- **Naslovi nad seznami imen so bili zakriti.** „SEZNAM UDELEŽENCEV
  DELAVNICE" ali „PREGLED ZAPOSLENIH NOTRANJA SLUŽBA" nad seznamom oseb je
  izginilo kot domnevno ime. V velikih črkah jezikovnemu modelu manjka
  njegovo najboljše razpoznavno znamenje, v nemščini pa je vsak samostalnik
  zapisan z veliko začetnico – „Teilnehmerliste Werkstattgespräch" je videti
  kot „Anna Huber". Sestavljenke na `-liste`, `-dienst`, `-gespräch`,
  `-sitzung` in `-besprechung` zdaj ostanejo. Osnovne besede same še naprej
  veljajo za ime: *Liste* in *Dienst* sta zasedena priimka, *Teilnehmerliste*
  ni.
- **Navpično postavljene navedbe so dobile neberljiv ograjenec.** Opravilne
  številke ob robu strani, kratice obdelovalca ob hrbtnem robu, navpične
  glave tabel: take navedbe so bile sicer najdene in odstranjene, vendar je
  ograjenec izšel počez čez besedilo, stisnjen na eno do dve piki in
  ponekod čez rob papirja. Zdaj sledi besedilu – navpično, v berljivi
  velikosti in v isti smeri, v kateri je stala navedba. Enako je veljalo za
  strani, ki so bile naknadno zasukane (vodoravno zapisano besedilo z
  vpisanim zasukom strani, kot ga dajejo nekateri izhodni programi); tudi
  tam ograjenec zdaj stoji tako, kot se stran gleda. „Spoštovana gospa
  doktorica Anneliese Berger" je dalo le „Anneliese" kot ime – „Berger" je
  ostal v dokumentu. Enako je veljalo za vsako ime z drugim imenom
  („gospa Anna Maria Berger"). Vzrok je bilo pravilo za ime za nagovorom:
  imelo je dve besedni mesti, naziv ali drugo ime pa je porabil prvo. Pri
  „Dr." to ni nikoli padlo v oči – pika prekine pravilo, in jezikovni model
  je zajel celo ime. Zdaj se nazivi preskočijo, ne da bi stali mesto, in
  ime lahko obsega tri dele. Vloga **za** imenom še naprej ne gre zraven:
  „gospa Anna Huber poslovodkinja" nadomesti ime, ne vloge.
