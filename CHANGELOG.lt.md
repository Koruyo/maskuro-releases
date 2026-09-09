# Pakeitimai

Kas keičiasi nuo vienos versijos iki kitos – aprašyta iš programos naudojimo
požiūrio taško, o ne jos vidinės sandaros. Kas nori sužinoti, *iš ko* ji
sukurta, ras tai [LIZENZEN.md](LIZENZEN.md); čia aprašyta, kas keičiasi
darbui su ja.

Numeracija seka įprastą schemą: **pirmasis** skaičius keičiasi, kai kas nors
nebeveikia taip, kaip anksčiau, **antrasis** – atsiradus naujoms galimybėms,
**trečiasis** – ištaisius klaidas.

## 0.10.52-alpha.20260903 – 2026 m. rugsėjo 3 d.

- Paketas, kurį sudaro daugiau nei keturi failai, nebesustoja atsakius
  keliuose peržiūros languose. Kiti dokumentai ir toliau ruošiami fone; po atsakymo
  susijęs failas dabar patikimai užbaigiamas ir atlaisvinama kita vieta
  pakete.
- Trumpi įmonių ženklai PDF failuose dabar lyginami tik su atpažintu vaizdų
  tekstu. Todėl įprastame puslapio tekste modelio aptiktas ilgas kelių eilučių
  fragmentas nebelemia, kad kitoje vietoje būtų papildomai uždengtas toks pat
  pavienis žodis.

## 0.10.51-alpha.20260903 – 2026 m. rugsėjo 3 d.

- Pakeitimų sąrašas dabar rodomas pasirinkta kalba – svetainėje
  maskuro.com/neuigkeiten, programos skiltyje „Pakeitimai“ ir po atnaujinimo
  atveriamame lange „Kas nauja“. Iki šiol visose aštuoniolikoje kalbinių
  versijų po išversta antrašte buvo rodomas vokiškas tekstas. Jei vertimo dar
  nėra, atitinkamas versijos įrašas lieka vokiškas, užuot pradingęs; versijų
  sąrašas visur vienodas.

## 0.10.50-alpha.20260903 – 2026 m. rugsėjo 3 d.

- Pasikartojantys firmų ženklai PDF failuose dabar valomi nuosekliai, net
  jei teksto atpažinimas užrašą viename puslapyje perskaito kitaip arba
  visiškai praleidžia apvalų ženklą. Aiškus atžymėjimas peržiūroje išlieka
  privalomas ir jo negali panaikinti joks vėlesnis pakartotinis
  patikrinimas.
- Be valiutos nurodytos kainos nuskenuotose lentelėse dabar visiškai
  užtamsinamos ir tada, kai lentelės antraštė bei reikšmės yra skirtinguose
  persidengiančiuose PDF vaizduose. Kiekiai, valandos, svoriai ir procentai
  lieka; toli vienas nuo kito esantys skaičiai daugiau netyčia nesujungiami
  į vieną sumą.
- Parašų paieška dabar aptinka ir silpnus mėlynus rašysenos elementus bei
  siaurus raudonus parašo trumpinius. Taškuoti diagramos, matavimo kreivės,
  antspaudai, logotipai ir platūs raudoni taisymo žymėjimai lieka
  neįtraukti į šį siaurą pakartotinį patikrinimą.
- Užtamsinimai pasuktuose, atspindėtuose, iškreiptuose ar apkirptuose PDF
  vaizduose dabar paliečia tikrą vaizdo daugiakampį. Techniniai vaidmenys
  paslaugų pozicijose, transporto priemonių ir padangų dalykiniai duomenys
  bei techninė „kompensacija" kartu tiksliau atribojami nuo klaidingų
  radinių; aiškiai pažymėti kontaktiniai vaidmenys ir telefono numeriai
  lieka apsaugoti.
- Vizualinė patikra prieš išsaugant PDF nebeįšaldo lango: dideliuose
  dokumentuose su daug radimo vietų jis anksčiau stovėdavo kelias sekundes
  be atsako; dabar rodoma nuoroda, kad vyksta patikra, ir langas toliau
  piešiamas.
- Reikšmės grąžinimas iš vaizdo taisymo redaktoriuje kiekvieną originalo
  vaizdą per teksto atpažinimą dabar skaito tik kartą; anksčiau ji
  kiekvieną kartą grąžinant tuos pačius vaizdus vykdavo iš naujo.
- Aukštos pakopos ir parašų modelio įkėlimui dabar beveik nebereikia
  operatyviosios atminties: 596 MB paketas anksčiau būdavo pilnai laikomas
  atmintyje, tikrinamas ir ten išpakuojamas – daugiau nei gigabaitas
  piko veikiančioje programoje, kompiuteriuose su 8 GB tas momentas, kai
  viskas pradėdavo stringiruoti. Dabar jis blokais teka į diską ir ten
  tikrinamas bei išpakuojamas.
- Paieška taisymo redaktoriuje dideliuose PDF failuose nebeįšaldo:
  pirmoji raidė paieškos lauke anksčiau iš karto įkeldavo visus puslapius –
  esant 200 puslapių langas stovėdavo dvi sekundes, ir dar kartą po
  kiekvieno užtamsinimo. Puslapiai dabar skaitomi dalimis; iki tol
  skaitiklyje rodoma „Skaitoma …", rezultatas tas pats.
- Rastruoti PDF puslapiai – po teksto atpažinimo arba kai teksto nepavyko
  švariai pašalinti – dabar išsaugomi gerokai mažesni ir be vaizdo
  kokybės nuostolių: vietoj visada JPEG kiekvienas puslapis papildomai
  koduojamas be nuostolių, ir mažesnė versija patenka į failą. Išvalytas
  skenavimas taip sumažėja nuo 248 iki 48 KB, pratybų dokumentas su teksto
  atpažinimu – nuo 913 iki 702 KB; tekstas lieka aštriai ryškus.
- Atsisiųsti modeliai (aukšta pakopa, parašai, veidai, antrasis teksto
  atpažinimas) po dešimties minučių be valymo dabar vėl paleidžiami iš
  operatyviosios atminties. Anksčiau jie likdavo įkelti iki programos
  pabaigos – kas kartą naudojo parašų paiešką ir aukštą pakopą, nuolat
  laikė daugiau nei du gigabaitus. Kitas paleidimas juos vėl įkelia per
  vieną–dvi sekundes; būsenos eilutė apie tai praneša.
- „PowerPoint": bendriniai skaidrių maketų ir skaidrių šablonų pavadinimai
  („Tuščias", „Antraštinė skaidrė") daugiau nebekeičiami kaip duomuo.
  „Tuščias" taip pat yra vietovė ir buvo klaidingai užtamsinamas
  kiekviename vokiškame ir angliškame pristatyme; valomi tik rankiniu būdu
  suteikti pačių skaidrių pavadinimai.
- PDF failuose eilučių glodinimas daugiau nebetraukia kitos eilutės
  pradžios į radinį: kito sąrašo punkto numeris po datos buvo laikomas
  telefono numeriu, lauko antraštė kaip „Kenncode" ar „Auftragsnummer" po
  skaičiaus – pašto kodu su vietove, o vietovės eilutė po adresu
  padvigubindavo vietovę. Dėl to teisingas, trumpesnis radinys būdavo
  išstumiamas. 132 korpuso PDF failuose iš 24 papildomų glodinimo radinių
  lieka du tikri; praktikos korpuse klaidingi pavojai sumažėja nuo 29 iki
  21 esant tai pačiai radimo kvotai.
- „Ieškoti ir užtamsinti PDF aplanke" taisymo redaktoriuje nebeblokuoja
  lango: paleidimas veikia fone, eiga ir atšaukimo mygtukas reaguoja, ir
  meniu ar skirtukų nebegalima valdyti pusiau baigto failo viduryje.
- Nuskenuoti puslapiai su radimo vietomis užtamsinant dabar iš naujo
  parašomi tik kartą, o ne du: anksčiau programa radimo vietų ir
  pagrindimų langelius pildė dviem etapais, o antrasis dar kartą
  suspausdavo ką tik iš naujo išsaugotą skenavimo vaizdą. Tai taupo laiką
  dideliems skenavimams ir kokybės nuostolį vaizde.
- Vartymas, mastelio keitimas ir miniatiūros taisymo redaktoriuje reaguoja
  greičiau: kiekvienas atvaizduotas puslapis anksčiau eidavo per PNG
  suspaudimą ir vėl atgal, vien tam, kad būtų parodytas – ekranuose su
  aukšta raiška tai maždaug dešimtadalis sekundės kiekvienam puslapiui.
  Vaizdas dabar atkeliauja tiesiogiai, pikselis į pikselį tas pats.
- Vizualinė patikra prieš išsaugant PDF failą („išvesties bandinys") yra
  maždaug tris kartus greitesnė, esant tam pačiam rezultatui.
- Pagrindinis langas atsiranda dar maždaug ketvirtadaliu sekundės
  anksčiau: patikra, ar teksto atpažinimas šiame kompiuteryje paruoštas,
  vykdavo lango sudarymo metu – „Mac" sistemoje kartu su bandomąja
  užklausa sisteminiam atpažinimui – o papildomų komponentų nustatymų
  puslapis tam papildomai tikrindavo visų 48 kalbų būseną. Abu dabar
  vyksta fone arba tik tada, kai kalbų sąrašas iš tikrųjų atidaromas; iki
  tol rodoma „Tikrinamas teksto atpažinimas …".
- Po parašų paieškos programa naudoja apie 300 MB mažiau operatyviosios
  atminties: atpažinimo modelis iki tol atmintyje būdavo dukart – kartą
  tikrinant jo autentiškumą, kartą skaičiuojant. Jis ir toliau tikrinamas,
  tik be antros kopijos.
- Teksto atpažinimas PDF failuose pastebimai pagreitėjo: kiekvienai
  puslapio lauko antraštei („Geburtsdatum:", „Steuernummer:") anksčiau
  būdavo siunčiamas atskiras bandinys atpažinimui kiekvienai duomenų
  rūšiai – iš naujo kiekviename puslapyje, net jei ta pati antraštė jau
  buvo prieš dešimt puslapių. Atsakymas dabar įsimenamas; dviejų puslapių
  darbų sąraše taip užduota 324 klausimai, dabar tik skirtingi. Radiniai
  tie patys.
- Didelės lentelės vėl valomos per sekundes, o ne minutes: anoniminimo
  veiksenoje – numatytojoje – jau žinomų reikšmių palyginimas su kiekviena
  tolesne ląstele lėtėjo, nes tarpinė talpykla kiekvieną kartą radus
  atmesdavo ir sukurdavo iš naujo. 5 000 ląstelių tam reikėjo apie 18
  sekundžių, dabar pusę; rezultatas simbolis į simbolį tas pats.
- Pagrindinis langas atsiranda dar gerokai greičiau: nustatymų šalių
  sąrašas lango sudarymo metu į priekinį planą traukdavo visą atpažinimo
  biblioteką – apie 0,7 sekundės „Mac" sistemoje, „Windows" atitinkamai
  daugiau –, nors tam reikia tik šalių pavadinimų. Sąrašas dabar imamas iš
  lengvo katalogo; biblioteka įkeliama, kaip numatyta, fone, kol langas
  jau stovi. Tai galioja ir po kiekvieno kalbos ar išvaizdos pakeitimo,
  kuris programą paleidžia iš naujo.
- Dokumentų laboratorija dabar apkirptas lauko antraštes, vietinius
  reikšmių šešėlius ir stiprius skenavimo apkirpimus visiškai pravaro per
  PDF, DOCX ir ODT konteinerius. Matricą sudaro 680 failų iš 40 dokumentų
  šeimų ir 17 konteinerių ašių. Maskuro naujuose bei pilnuose bazinio ir
  požymių profiliuose pašalina visas siektinas reikšmes be išmatuoto
  klaidingo pavojaus, pažeisto išsaugojimo ar nutraukimo.

- Kelis kartus naudojami skenavimai dabar tikrinami ir valomi per kiekvieną
  matomą pateikimo vietą: dokumentų laboratorija dalijasi tuo pačiu vaizdo
  objektu keliuose puslapiuose, dydžiuose ir pasukimo padėtyse PDF faile
  ir kelis kartus nurodo tą pačią vaizdo dalį DOCX bei ODT failuose.
  Techniniai ODT rėmelių pavadinimai kaip „Formularscan klein quer"
  nebelaikomi asmeniu; laisvi vardai ir vietovės su panašia pradžia lieka
  apsaugoti. Bendras baigiamojo PDF puslapio paleidimo formos spėjimas
  daugiau nebegali sukurti didelio adreso klaidingo radinio ant jau
  nepriklausomai perskaitytos vaizdo srities. 120 naujų konteinerių
  baziniame ir požymių profilyje pasiekia visas atitinkamai 813 ir 840
  siektinas reikšmes be klaidingo pavojaus, išsaugojimo pažeidimo ar
  nutraukimo; pilnas 800 failų požymių priėmimas patvirtina 5 600/5 600.

- Vokiškoji OCR laboratorija dabar apima 560 skenavimų iš 40 dokumentų
  šeimų. Naujos atmainos apkerpa lauko antraštės ir puslapio kraštus arba
  uždeda šešėlį tiesiai ant reikšmės. Maskuro tuo pačiu apsaugo vardus,
  adresus, gimimo datas, medicinos raktus ir paženklintus identifikacinius
  numerius su iš dalies pažeistu užrašu. Kartu formos laukų likučiai,
  oficialios antraštės bei dalykiniai teisiniai ir informaciniai terminai
  daugiau nebekeičiami kaip asmenys ar vietovės. Pilni baziniai ir požymių
  profiliai pasiekia 3 794/3 794 ir 3 920/3 920 siektinų reikšmių be
  išmatuoto klaidingo pavojaus ar nutraukimo.

- Automatinis PDF vaizdų pasirinkimas nebepašalina didelių gaminio
  nuotraukų, energijos etikečių ir portretų eilių vien todėl, kad jos
  prasideda viršutiniame puslapio krašte. Tikri plokšti antraštės/poraštės
  vaizdai ir prie lapo krašto prasidedantys firminiai blankai ir toliau
  pašalinami. Darbuotojų kataloguose vardai dabar atpažįstami iš
  struktūriškai pasikartojančių įrašų ir tada, kai matomas dokumento
  pavadinimas yra tik vaizdas. Atpažinimas nebeapribotas dviem konkrečiais
  vaidmenų žodžiais ir santrumpa „DW": vienas–keturi perlaužti vaidmenys
  bei „Durchwahl", „Nebenstelle", „Ext." ir „Extension" nustatomi iš
  bendros formos. Vaidmenys ir skyrių antraštės lieka, net jei kalbos
  modelis po persidengimo išsprendimo palieka tik vieną vaidmens būdvardį.
  Horizontalūs vaidmenų tinkleliai nebelaikomi klaidingai vardų
  stulpeliais. Jei puslapio OCR sulipdo kelias korteles į itin platų
  vidinį didžiosiomis raidėmis rašomą žodį, siauras vietinis kryžminis
  žvilgsnis atskiria tikrus žodžių langelius; dėl to nelieka nei pavienio
  vardo, nei plataus klaidingo juostos. Pasikartojantys kelių eilučių
  įmonių logotipai užtamsinami pagal jau patvirtintą tapatų pikselių
  šabloną net puslapiuose be naudingo OCR teksto ir esant iki dviejų
  pikselių padėties nuokrypiui; trumpesni vietiniai antriniai OCR
  perskaitymai kartu nebegali papildyti didesnio antraštės ploto kaip
  sugalvoto vardo. Puslapių numeriai prieš firmos blanką daugiau
  nepriklauso organizacijos pavadinimui, skaičiumi prasidedantys tikri
  prekės ženklai lieka apsaugoti. Keli išmatuoti gaminio, dalykiniai ir
  formos žodžiai daugiau nebesiūlomi kaip asmenys.

- Parašų paieška PDF failuose dabar vyksta tik po OCR vaizdo valymo,
  aplanko ir puslapius be įprasto teksto radinio ir teisingai perskaičiuoja
  pasuktų puslapių radimo langelius atgal į dokumento erdvę. Tankios
  gaminio nuotraukos daugiau nebeuztamsinamos kaip parašas. Virš aiškiai
  paženklintų parašo laukų siauras brūkšnio atsarginis kelias uždaro
  plonas modelio spragas; tuščios linijos su iš anksto atspausdinta data
  jo nesukelia. Grynas skenavimas vien su OCR/parašų radiniais šioje
  fazėje daugiau nebenutrūksta dėl tik teksto šakoje įkeliamo vaizdo
  užtamsintuvo.

- Daug tuo pačiu metu atidarytų dokumentų taisymo redaktoriuje lieka
  atskiriami: skirtukai nebesusitraukia iki vieno paprasto daugtaškio, o
  sąrašo mygtukas dešinėje rodo visus pilnus failų pavadinimus vienas po
  kito. Skirtukus galima pertvarkyti tempiant ir pašalinti jų kryželiu iš
  to paties sąrašo kaip pagrindiniame lange; neišsaugotas darbas tuo metu
  ir toliau pirmiausia išsiaiškinamas. Dešiniojo pelės klavišo meniu taip
  pat siūlo „Uždaryti", „Uždaryti kitus skirtukus" ir „Uždaryti skirtukus
  dešinėje".

- Trumpalaikis „Windows" užrakinimas dėl antivirusinės ar paieškos
  indekso daugiau nesukelia baigiamojo įkėlimo klaidos „Prieiga
  uždrausta" jau paruoštam kalbos modelio ar žodyno aplankui. Maskuro
  dabar šį paskutinį aplanko keitimą trumpam bandomas dar kartą.

- Vokiškoji dokumentų laboratorija dabar tikrina konteinerius ir su
  kintančiu PDF puslapio pasukimu, nepriklausomai pasuktais PDF vaizdais
  bei mastelio ir apkirpimo pakeistais lentelių vaizdais DOCX ir ODT
  failuose. Lauko reikšmės matomai pasuktuose vaizduose vėl visiškai
  atpažįstamos, techniniai stulpelių žymikliai nebekeičiami kaip vietovės,
  o vardai su bendra pavarde nebeišskaidomi nuoseklumo patikros į dvigubus
  dalinius radinius. Iki 320 failų padvigubinta matrica su papildomai
  įjungtu datos, pinigų ir medicinos atpažinimu pasiekia 2 240/2 240
  siektinų reikšmių be išmatuoto klaidingo pavojaus ar nutraukimo.

- Daugiapuslapiai vaizdo PDF failai, mišrūs teksto/vaizdo PDF failai ir
  DOCX ar ODT įterpti skenavimai dabar tikrinami atskiroje 160 failų
  laboratorijoje per visas 40 vokiškų dokumentų šeimų. Techniniai ODT
  rėmelių pavadinimai ir paženklinti įrenginių kodai nebekeičiami kaip
  vietovės; tikri vardai, vietovės ir adresai tose pačiose struktūrose
  lieka apsaugoti. Įjungus medicinos ar pinigų atpažinimą, be to,
  visiškai pašalinama tiesiogiai po jos einanti dozė ar mokėjimo
  intervalas. Konteinerių, teksto bazinio, teksto požymių ir OCR požymių
  paleidimai kartu pasiekia savo atitinkamas pilnas reikšmes be
  išmatuoto klaidingo pavojaus ar nutraukimo.

- Saugumo patikra prieš išsaugant dabar rodo pastebimas PDF vietas kaip
  atskirai pažymimą sąrašą. „Tikrinti redaktoriuje" atidaro būtent
  pasirinktą puslapį ir pažymi sritį; persidengiantys daliniai radiniai
  toje pačioje vietoje rodomi tik kartą. Nauji valdymo tekstai pilnai
  yra visose 17 išverstų sąsajos kalbų.

- Markdown failai keičiant išlaiko savo nuorodų, paryškinimo ir išnašų
  sintaksę. Maskuro tam skaito simboliais lygiai tokio pat ilgio versiją
  be Markdown žymėjimo; pabraukimai el. pašto adresuose, skaičiavimo
  žvaigždutės ir įprastos nuorodos be asmens duomens lieka nepakitę.

- Keli ranka rašyti įrašai tame pačiame PDF puslapyje dabar ieškomi iki
  trijų etapų. Jau rasti brūkšniai paslepiami tik darbiniame vaizde, kad
  jie nebeišstumtų silpnesnių parašų; pasuktuose puslapiuose užtamsinimo
  sritys vėl atsiduria matomoje radimo vietoje. Ankstesnių saugumo etapų
  vaizdo užpildai išlieka vėlesnio įrašymo atgal metu.

- „Atstatyti visus nustatymus" dabar apima ir „Tekstas vaizduose". Jei
  OCR komponentas nepasiekiamas, jungiklis technine prasme lieka
  išjungtas, be klaidingo pažymėjimo, kad jis skiriasi nuo pristatymo
  būsenos.

- Dideli vaizdo fragmentai viršutiniame puslapio krašte daugiau
  nebelaikomi antrašte vien dėl savo padėties. Dėl to ypač išlieka vaizdu
  pagrįsti straipsnių aprašymai ir lentelių turinys. Naujai atpažinti,
  tikslaus tipo el. pašto ir formų radiniai taip pat nebeišfiltruojami iš
  baigiamosios vizualinės patikros net ant jau patikrintos vaizdo srities.

- Techninės pozicijų ir prekių eilutės klimato ir elektros pasiūlymuose
  dabar tiksliau atskiriamos nuo asmenų, vietovių ir organizacijų. Tai
  liečia, be kita ko, kabelių tipus, kintamosios srovės tiekimą, pozicijų
  numerius bei didžiosiomis raidėmis rašomus gaminio kodus; tikri vardai
  ir adresai lieka apsaugoti.

- Realių išvalytų PDF failų patikra daugiau nepainioja kainos dalių kaip
  `1 699,59` su telefono numeriais ir iš pilnos datos kaip `08.05.2025`
  nebeiškerpa tariamos kortelės reikšmės. Vardai po kreipinio baigiasi
  eilutės lūžyje, o ne sekančioje gatvėje; vietovardžiai priedų failų
  pavadinimuose apribojami iki tikros vietovės. Transporto priemonių
  spalvos, techninės būsenos reikšmės, veiklos pavadinimai ir gaminių
  teisinės formos taip pat išsaugomi. Pažeisti žymiklio perskaitymai kaip
  `|PLLZ` antro OCR etapo metu nebelaikomi iš naujo asmens duomeniu.

- Šoniniai išsaugoti PDF vaizdai baigiamosios vizualinės patikros metu
  gauna papildomą žvilgsnį jų nepakitusioje vaizdo padėtyje. Jis gali tik
  papildomai užtamsinti reikšmes, kurias Maskuro tame pačiame puslapyje
  jau tikrai atpažino. Taip, pavyzdžiui, visiškai uždengiamas mažas
  pasuktas adreso antspaudas, neišgalvojant naujų žodžių iš vaizdo
  antraščių ar techninių brėžinių kaip asmens duomenų.

- „OpenDocument" tekstuose pastabos (komentaro) autoriaus inicialai dabar
  ištuštinami kartu su autoriumi. „LibreOffice" juos šalia pilno vardo
  laiko kaip atskirą trumpąją formą ir būtent ją rodo puslapio krašte;
  iki šiol ten ir toliau stovėjo „SO", nors „Sieglinde Ortner" šalia jau
  seniai buvo žymiklis. Ištuštinama tik tada, kai autorius iš tikrųjų
  buvo pakeistas – skyriaus pastaba išlaiko savo žymėjimą.

- Itališkuose verslo laiškuose standartiniai posakiai sakinio pradžioje
  daugiau nebelaikomi vardu ar vietove: „Restiamo a disposizione",
  „Rimaniamo", „Attendiamo", „Alleghiamo", „Comunichiamo" ir „Auguriamo
  buon lavoro" iki šiol likdavo kaip tariamas asmuo ar vietovė. Tikri
  vardai toje pačioje vietoje („Rossi Mario") ir toliau atpažįstami.

- Dviejų stulpelių skenavimai dabar apsaugo paženklintus identifikatorius
  ir vietovardžius ir tada, kai teksto atpažinimas pirmiausia pateikia
  visas lauko antraštes, o po to visas reikšmes. Priskyrimas seka matomą
  pikselių eilutę ir veikia taip pat su 90 laipsnių pasuktais puslapiais.
  Glaudžiai atskirtos paso ar sutarties identifikatoriaus dalys
  užtamsinamos kartu; paženklintos gimimo datos, TLK ir vaisto registro
  raktai taip pat apsaugoti, sekantys dalykiniai žodžiai lieka. Trumpi
  vardai ir naudotojo vardai apsaugomi tiksliuose laukuose; į kelis OCR
  žodžius suskaidyti el. pašto adresai – tik esant glaudžiam kaimynystei
  ir pilnai el. pašto gramatikai. Lauko taisymas painiotinų ženklų bei
  vietinis dar tuščio asmens lauko perskaitymas apima pažeistus ir
  pasuktus skenavimus, neišplečiant dalykinių laukų ar jau užimtų
  reikšmių. Saugumo paraštės seka žodžio dydį, o požymių profilis
  papildomai apima tiesiogiai gretimas dozės vienetus ir mokėjimo
  intervalus. Šiek tiek kreivai paduotos formos geometriškai
  perprojektuojamos iš kelių ta pačia kryptimi einančių OCR eilučių;
  apvalinimo triukšmo ar prieštaringų liudytojų nepakanka. Trumpi raidžių
  priešdėliai lieka prieš brūkšnelio identifikatorių, o pilnas
  paženklintas adreso radinys pakeičia tik jo panašų gatvės dalinį
  radinį. Neteisingai perskaityta vaidmens lauko antraštė krenta tik
  formos stulpelyje, paremtame bent trimis žinomomis antraštėmis; pokalbių
  vardai lieka apsaugoti. Siauras krašto apkirpimas ir vietinis
  peršvietimas su įstrižu šviesos atspindžiu papildo vaizdų matricą.
  Per kelias formos eilutes besitęsiantys asmenų, vietovių ir įmonių
  radiniai daugkartiniame lauko stulpelyje apribojami iki atitinkamos
  reikšmės. Techninė pozicijos reikšmė krenta tik su pozicijos antrašte
  ir tinkama forma; tikri vardai lieka apsaugoti. Ir šviesos atspindžio
  nutraukti el. pašto reikšmės pašalinamos už aiškios el. pašto lauko
  antraštės su siauru, kaimynystės ribotu vaizdo kraštu. Dvi lauko-reikšmės
  poros toje pačioje matomoje eilutėje dabar vertinamos nepriklausomai;
  reikšmės žemesnėje pagrindo linijoje susiejamos tik po trijų sutampančių
  geometrinių liudytojų. Dėl to identifikaciniai numeriai, gimimo datos ir
  adresai lieka visiškai apsaugoti net tankiuose formų išdėstymuose.
  Gatvė, pašto kodas ir vietovė sujungiami tik tame pačiame adreso lauke
  ir su tinkama pašto gramatika. Siaurai apibrėžti dalykiniai laukai
  darbo/pagalbinėms priemonėms ir dantų būsenai daugiau nebesukuria
  vietovės ar katalogo klaidingų pavojų; tikri vardai ir panašiai
  pavadinti laukai lieka apsaugoti. Vokiškoji dokumentų laboratorija
  dabar apima 440 skenavimų ir pasiekia 2 981/2 981 baziniame profilyje
  bei 3 080/3 080 požymių profilyje. Visos vienuolika vaizdo mutacijų ir
  visos 40 dokumentų šeimų yra ties 100 procentų,
  ir toliau be išmatuoto klaidingo pavojaus, išsaugojimo pažeidimo ar
  nutraukimo.

- PDF teksto sluoksniai su prarastais ląstelių skirtukais dabar riboja
  organizacijų, adresų ir vietovių radinius pagal pasikartojančią
  lauko-reikšmės struktūrą. Lauko antraštės prieš įmonės reikšmes ir
  techninės rodyklės kaip `=>` ar `->` daugiau nepriklauso radiniui.
  Papildomas vaizdas minkštiems eilučių lūžiams nebegali tęsti teisinės
  formos ir vietovės radinių per kelias lentelės eilutes; jau pilnas
  adresas baigiasi prieš kitą lauko antraštę su reikšme. Baigiamasis
  paleidimas per visus 1 600 TXT, HTML, PDF ir DOCX dokumentų pašalina
  10 840/10 840 siektinų reikšmių esant nuliui klaidingų pavojų, nuliui
  išsaugojimo pažeidimų ir nuliui nutraukimų.
