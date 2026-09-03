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

## 0.10.44-beta.1 – 2026 m. rugsėjo 1 d.

- Paketų kūrimas dabar sukuria atskirus paketus Windows x64 ir ARM64,
  macOS su Apple Silicon ir Intel bei Linux x64 ir ARM64. Paketų
  pavadinimai, atnaujinimo pasirinkimas ir leidimai skiria architektūrą;
  leidimas lieka užblokuotas, kol trūksta bent vieno iš šešių tikslinių
  paketų arba jo priklausomybių patvirtinimo. Linux ARM64 dėl Qt reikalauja
  bent glibc 2.39. Kol kas realia technine įranga pilnai patikrinti tik
  Windows x64 ir macOS su Apple Silicon; likę architektūriniai paketai
  aiškiai žymimi kaip išankstinės versijos, skirtos išbandymui, o ne
  produkciniam naudojimui.

- Dirbant su keliais failais atpažinimas dabar tęsiasi toliau, kol
  peržiūra laukia patikrinimo. Iš eilės rodomos iki trijų iš anksto
  paruoštų peržiūrų; tuo pačiu metu skaičiuojamas tik vienas dokumentas,
  o rezultato failas sukuriamas tik po jo patvirtinimo. Peržiūroje
  pasirinkta nuolatinė išimtis galioja ir jau paruoštiems sekantiems
  dokumentams.

- Redagavimo sertifikatus dabar bet kada galima tikrinti tiesiai Failo
  meniu prieš pažymėtą (juodinimo būdu) dokumentą. Maskuro skiria
  atitinkantį pasirašytą failą, atitinkantį, bet nepasirašytą įrodymą,
  negaliojantį parašą ir dokumentą, kuris nepriklauso sertifikatui.
  Kontrolinei patikrai nereikia nei licencijos, nei pradinės operacinės
  sistemos paskyros.
  Automatiniams patikros punktams tas pats palyginimas prieinamas per
  `--zertifikat-pruefen`; grąžinimo kodai skiria atitikimą, valdymo
  klaidą ir negaliojantį įrodymą.
  Kontrolinė patikra papildomai palygina įterptą Maskuro ID su
  sertifikatu; laisvai įrašytas svetimas ID dėl to išaiškėja net esant
  nepasirašytam įrodymui.
  Kai parašas galioja, tikrinimo rezultatas papildomai rodo administravimo
  aktyvuotą redaktorių su operacinės sistemos paskyra, technine paskyros ID
  ir platforma. Nepatvirtinti duomenys iš nepasirašytų arba negaliojančių
  įrodymų nerodomi.

- Nauja vokiška dokumentų laboratorija sukuria 160 visiškai sintetinių
  TXT, HTML, PDF ir DOCX dokumentų iš dešimties sričių ir keturių
  struktūros variantų. Manifestas dabar aiškiai skiria duomenis, kurie
  turi dingti, ir specialius tekstus bei dalykinius identifikatorius,
  kurie turi likti nepakitę; dokumento šeima, mutacija ir vieša
  struktūros kilmė yra atsekami.

- Vokiška dokumentų laboratorija išplėsta iki 280 failų, septynių
  struktūros formų, 1 540 privalomų reikšmių ir 1 036 išsaugojimo
  žymeklių. Naujai tikrinamos numeruotos formos, skliaustuose esantys
  PDF/kaukės laukai ir techniniai `=>` sąryšiai. Išplėstas pilnas
  rinkinys TXT, HTML, PDF ir DOCX formatuose pasiekia po 100 procentų
  be klaidingų aliarmų. Dabar struktūriškai atpažįstami skliaustuose
  esantys datos ir identifikavimo numerių laukai, rodyklių skirtukai ir
  aiškiai pažymėti junginiai.

- Antrasis laboratorijos plėtinys pakelia rinkinį iki 400 dokumentų,
  dešimties struktūros formų, 2 200 privalomų reikšmių ir 1 480
  išsaugojimo žymeklių. JSON tipo raktų reikšmės, YAML sąrašai ir
  didžiosiomis raidėmis rašomi formos laukai kartu su ankstesniu
  rinkiniu pasiekia 100 procentų be klaidingų aliarmų. Cituojamos
  gimimo datos ir identifikavimo numeriai bei aiškiai pažymėti
  vaidmenys, tokie kaip apdraustieji, pareiškėjai, mokesčių mokėtojai ir
  įgalioti asmenys, dabar atpažįstami ir šiose eksporto formose.

- Atskiras vokiškos dokumentų laboratorijos OCR režimas papildomai
  sukuria 200 grynai vaizdinių nuskaitymų iš visų 40 šeimų. Švarūs,
  mažo kontrasto, žemos raiškos, JPEG artefaktų turintys ir 90 laipsnių
  pasukti puslapiai matuojami tiksliais pikselių langeliais, nekeičiant
  palyginamo 1 600 failų teksto pagrindo. Manifestas atskiria įjungiamus
  datos, pinigų ir medicinos požymius nuo pagrindinio profilio ir žino
  patvirtintus OCR nuskaitymo variantus, jų neskaičiuodamas kaip
  papildomų privalomų reikšmių. Matavimas suskirstomas pagal mutaciją ir
  dokumento šeimą. Griežtos lauko ribos, be kita ko, neleidžia, kad
  `Az` vietovardyje `Graz` paverstų sekančią datą bylos numeriu ir ją
  paslėptų; dabartinė pagrindinė matrica veikia be klaidingų aliarmų ir
  be nutraukimų.

- Penkios papildomos vokiškos dokumentų šeimos – sąskaitos/važtaraščiai,
  bankas/kreditas, nuoma/namų valdymas, mokykla/aukštoji mokykla ir
  logistika/muitinė – išplečia laboratoriją iki 600 failų su 3 520
  privalomų reikšmių ir 2 360 išsaugojimo žymeklių. Griežtas PDF
  lentelių kelias naudoja aiškią antraštę `Feld Angabe`, kai teksto
  sluoksnis praranda langelių skirtukus; naujas `--familien` pasirinkimas
  pagreitina dalinius matavimus. 200 naujų failų pasiekia 1 320/1 320 be
  klaidingų aliarmų ir be nutraukimų.

- Draudimas/žala, darbas/darbo užmokestis, medicina/laboratorija,
  transporto priemonė/dirbtuvės ir technika/priežiūra išplečia vokišką
  dokumentų laboratoriją iki 800 failų su 4 960 privalomų reikšmių ir
  3 200 išsaugojimo žymeklių. Atpažįstami griežtai pažymėti polisų,
  pacientų, tikrintojų ir transporto priemonių identifikatoriai bei
  nauji vaidmenų, adresų ir organizacijų laukai. Nauja dalinė matrica ir
  pilna matrica pasiekia 100 procentų be klaidingų aliarmų ir be
  nutraukimų TXT, HTML, PDF ir DOCX formatuose.

- Statyba/konkursas, energetika/aplinka, asociacija/bendrija,
  komunikacija/kalendorius ir viešbutis/renginys pakelia vokišką
  dokumentų laboratoriją iki 1 200 failų su 7 920 privalomų reikšmių ir
  4 800 išsaugojimo žymeklių. Nauji vaidmenų, įmonių, adresų, registro,
  pirkimų, rezervacijų ir vartotojo paskyrų laukai atpažįstami ir
  visuose eksporto formatuose. Skaitiklių numeriai išlieka kaip dalykiniai
  identifikatoriai. Dalinė ir pilna matrica pasiekia 100 procentų be
  klaidingų aliarmų ir be nutraukimų.

- Gastronomija/pristatymo tarnyba, vaistinė/receptas, laidojimo
  paslaugos/kapinės, sportas/narystė ir nekilnojamasis turtas/tarpininkas
  išplečia vokišką dokumentų laboratoriją iki 1 400 failų su 9 360
  privalomų reikšmių ir 5 640 išsaugojimo žymeklių. Atpažįstami nauji
  asmenų vaidmenys, adresų laukai ir paieškos užsakymo numeriai.
  Pažymėti įmonių pavadinimai su teisine forma lieka visiškai apsaugoti
  net ir po automatinio eilutės perkėlimo; amžiaus grupės ir specialistų
  pavadinimai nebekeičiami klaidingai. Dalinė ir pilna matrica pasiekia
  100 procentų be klaidingų aliarmų ir be nutraukimų.

- Odontologija, vairavimo mokykla, gaisrinė/įvykis, energetikos bendrija
  ir kelionė su viskuo įskaičiuota išplečia vokišką dokumentų
  laboratoriją iki 1 600 failų su 10 840 privalomų reikšmių ir 6 440
  išsaugojimo žymeklių. Nauji vaidmenys, adresų laukai bei gydymo,
  mokymo, įvykio, energijos ir kelionės sutarties identifikatoriai
  atpažįstami struktūriškai. Nauja 200 failų dalinė matrica pasiekia
  1 480/1 480; pilna matrica pasiekia 10 840/10 840. Abi lieka be
  klaidingų aliarmų ir be nutraukimų.

- Pilnas dokumentų laboratorijos matavimas dėl griežtų oficialių
  dalykinių formų ir struktūros taisyklių sumažino nereikalingus
  pakeitimus nuo 68 iki 0, aiškiai matuojamus išsaugojimo pažeidimus
  nuo 23 iki 0 ir nutraukimus nuo 3 iki 0. Radimo rodiklis tuo pačiu metu
  pakilo nuo 91,1 iki 100,0 procento; TXT, HTML, PDF ir DOCX kiekvienas
  pasiekia po 100 procentų. Bendros lentelių antraštės, tokios kaip
  `Feld`, stabdomos tik patvirtintoje sekoje `Feld`/`Angabe`; tokia pat
  pavarde lieka apsaugota. Visiškai atpažįstami teismo bylų numeriai su
  galūnės raide, lygybės ženklo laukai, `Geburtsdatum des Kindes` ir
  keli pažymėti pavieniai vardai toje pačioje eilutėje. Word lentelės ir
  priešeilutės laukai naudoja savo lauko antraštę kaip laikiną atpažinimo
  kontekstą; pažymėti PDF adresai lieka visiškai apsaugoti net ir esant
  sakinio sąlygotam eilutės perkėlimui.

- Vokiški asmens požymių, profesijų ir medicinos laukai dabar veikia ir
  su Windows eilučių lūžiais. Vienos raidės lyties nurodymai, pvz.
  `Geschlecht`/`w`, saugomi priešeilutės formoje. Dalykiniai
  `Artikel-PZN` laukai, priešingai, nesukelia nei vaisto kodo, nei
  asmens radinio; tikri PZN, ICD ir ATC duomenys lieka atpažįstami.

- Vokiški formų ir numerių laukai tikslesni: „DW.“ dabar veikia ir prieš
  minkštą eilutės lūžį, aiškiai pažymėti vardai pašalinami net rašant
  mažosiomis raidėmis, o grynai skaitiniai bylos numeriai priskiriami
  teisingai savo identifikavimo numerio rūšiai. Priešingai, atsitiktinai
  Luhn algoritmą atitinkanti sąskaitos, dokumento ar prekės numeris
  nebelaikoma kredito kortele. Sintetiniai HTML ir PDF išvesties
  pavyzdžiai patvirtina pašalinimą ir išsaugojimą galutiniame dokumente.
  Identifikavimo numeriai ir vartotojo vardai dabar atpažįstami ir tada,
  kai jų žymėjimas yra tiesiogiai ankstesnėje lentelės ar formos
  eilutėje; dalykiniai dokumentų numeriai lieka matomi ir šioje formoje.

- Slaptažodžiai dabar atpažįstami ir esantys už pavienio lauko antraštės
  ankstesnėje eilutėje. Baigiamieji specialūs ženklai, tokie kaip `!` ar
  `#`, dabar visiškai priklauso saugomai reikšmei. Produktų ir prekių
  PIN kodai, priešingai, nebekaukuojami kaip kortelės PIN; aiškūs `PIN`
  ir `Karten-PIN` laukai lieka apsaugoti.

- Mažosiomis raidėmis rašytos formos reikšmės vienareikšmiuose vokiškuose
  adreso ir `PLZ/Ort` laukuose dabar pateikiamos kaip adresas arba
  pašto kodas su vietove, o ne tik kaip bendra vietovė. Taip pat
  mažosiomis raidėmis rašytos įmonės reikšmės, pvz., „beispiel service“,
  už įmonės lauko lieka visiškai apsaugotos, neapkarpant paskutinio
  žodžio kaip tariamos kitos lauko antraštės.

- Pagalba, DUK, privatumo tekstas ir svetainė dabar kartu paaiškina
  kilmės įrodymą: neutralus Maskuro ID dokumente, neprivaloma sąsaja su
  tikra operacinės sistemos paskyra tik vietiniame patikros protokole,
  vartotojo pasikeitimas Windows/macOS/Linux sistemose bei SHA-256 ir
  parašo įrodomoji galia.

- Vaizdu pagrįsti techniniai darbų sąrašai valomi atsargiau. Vienareikšmiai
  dalykiniai žodžiai, tokie kaip „Abbruchhämmern“, „Deckungsrücklass“,
  „Positionsnummern“, „Einbauplatine“ ar „Terminsituation“, taip pat
  OCR formos, perskirtos žodžio viduryje, nebelaikomos asmeniu ar
  vietove. Realaus savivaldybės biuro pasiūlymo atveju tai sumažino
  vienareikšmius pakeitimus nuo 140 iki 90, nesukuriant naujų atitikčių;
  tokie vardai kaip Schneider, Lang, Bauer ir Hahn lieka aiškiai
  apsaugoti.

- Ištaisyti tolesni klaidingi aliarmai iš realių pasiūlymų: „Digital
  signiert“ nebeturi tariamo asmens, BIC atpažįstamas ir be dvitaškio
  už savo žymėjimo, `15000 Alternativ` nebelaikoma pašto kodu su
  vietove, o ES citata „(VO (EG) 715/2007“ nebesukuria organizacijos.
  Dėl to fotovoltinės sistemos pasiūlyme pakeitimų skaičius sumažėjo nuo
  26 iki 16; tikri vardai, vietovės ir sąskaitų duomenys išliko.

- Darbuotojų sąrašuose pavaduotojo santrumpa „Stv.“ ir atskirai stovinti
  „FACILITY“ srities antraštė nebekeičiamos kaip asmens vardas. Realioje
  13 puslapių kontrolinėje patikroje pakeitimų skaičius sumažėjo nuo 878
  iki 875; vardai, vidiniai numeriai ir įmonės pavadinimas liko
  apsaugoti.

- Išvalyti PDF, OpenDocument ir Office failai gauna neutralų
  `MASKURO-…` identifikatorių savo dokumento savybėse. Patikros
  ataskaita ir pasirašytas patikros protokolas nurodo tą patį
  identifikatorių bei šaltinio ir rezultato SHA-256 reikšmes; redagavimo
  sertifikatas perima identifikatorių iš galutinio failo. Vartotojo
  vardas pridedamas tik tada, kai administravimas aiškiai įjungia esamą
  vartotojo lauką.

- Pagrindinis langas ir nustatymai suskirstyti ramiau: Išsaugoti, Kopijuoti,
  Detalės, Rodikliai ir atpažinimo profilio trynimas rodomi tik tada, kai
  atitinkamas veiksmas yra galimas. Techniniai OCR kalbų kodai ir ilgi
  pavyzdžiai prireikus rodomi paaiškinimo tekste, o ne nuolat darbo
  paviršiuje. Atpažinimo puslapis geriau prisitaiko prie siauresnių langų
  – be nukirstų paaiškinimų ar horizontalios slankties; įspėjimas apie
  aiškų tekstą pakeitimų sąraše lieka matomas.

- Atpažinimas dabar apima daugiau vokiškų ir tarptautinių kontaktų
  atvejų: telefono numeriai dabar tikrinami visuose pasirenkamuose
  šalies regionuose, vengriški ir kroatiški sutarties vaidmenys pilnai
  aprėpia ir su profesijomis sutampančias pavardes, o numeruoti atsarginių
  dalių/medžiagų sąrašai nebesukelia klaidingo asmens aliarmo dėl
  „Mutter / Flach“. Asmenų laukai su akivaizdžiai skaitmenis turinčia
  dalykine reikšme nebelaikomi vardu; mašininio skaitymo paso zona (MRZ)
  papildomai gali būti bendrai įjungta ir išjungta per grupę
  „Identifikatoriai“.

- Įmonės be teisinės formos dabar geriau skiriamos nuo asmenų už
  daugiareikšmių darbdavio laukų: tokie vardai kaip „Huber Handel“,
  „Müller Logistik“ ar „Kowalski Handel“ dabar pilnai atpažįstami kaip
  įmonė, o „Arbeitgeber: Bauer Anna“ toliau lieka asmens vardu.
  Automatinis šalies pasirinkimas prancūziškiems dokumentams toliau
  apima visą prancūzakalbę erdvę, įskaitant Liuksemburgą.

- Anksčiau atpažinti parašai ir asmens duomenis atitinkantis tekstas
  vaizde visada buvo uždengiami juodu stačiakampiu – net kai pakeitimo
  vaizdo nustatymuose buvo pasirinkta kita spalva ar raštas, pvz.,
  „Vaivorykštė“. Šios vaizdo sritys dabar taip pat perima pasirinktą
  užtemdymo pateikimą; dengiantis plotas ir toliau įrašomas tiesiai į
  vaizdo pikselius.

- Anglų kalbos atpažinimas buvo pertikrintas ir tikslingai patobulintas
  pagal vienuolika rankiniu būdu išverstų realių dokumentų: inventoriaus
  būsena, techniniai pasiūlymų ir internetinės parduotuvės laukai bei
  vaidmenys darbuotojų sąrašuose lieka matomi, „CV“ šablono sakinyje
  nebeskaitomas kaip teisinė forma, cituojami šriftų pavadinimai lieka
  nepakeisti, o vardai vertikaliose gyvenimo aprašymo antraštėse,
  daugiapuslapiuose darbuotojų sąrašuose, po „Account manager“ bei
  skaitmeniu prasidedantys įmonių pavadinimai atpažįstami pilnai.
  Austrijos įmonių registro numeriai dabar veikia ir po angliškos
  antraštės; trumpoji forma „Customer:“, EAR registracijos numeriai ir
  darbdavio numeriai perneša savo reikšmę. Matmenų grandinės, kabelių
  tipai, ES teisės nuorodos, pasiūlymo galiojimo datos, atlikimo vietos,
  teismingumo vietos, registro teismai, mokesčio santrumpa „NoVA“,
  techniniai numeriai padangų etiketėse bei standartų nuorodos, tokios
  kaip „OVE R6-2“ ir „AStV“, nebesukelia klaidingo aliarmo. Galiojanti
  pažymėta IBAN dabar švariai baigiasi prieš registracijos lauką arba
  sekančios eilutės antraštę; adresai su verslo zonos priedu pilnai
  atpažįstami ir PDF teksto srautuose su Windows eilučių lūžiais.
  Angliškos įmonių įžangos ir struktūrizuoti taupomųjų kasų pavadinimai
  visiškai atskiriami. Pirminio dokumento šalis išlieka pašto kodų ir
  su šalimi susijusių identifikatorių kalbinėse versijose.

- Gavėjų ir pranešimų antraštėse kalbos modelis kartais sujungdavo pirmus
  du kableliais atskirto sąrašo vardus į vieną radinį („Bcc: Huber,
  Mayer“). Dabar abu vardai atpažįstami, pakeičiami ir įtraukiami į
  ataskaitą atskirai – taip pat ir po „Sent:“, „Reply:“ bei „Fwd:“.

- Mašininio skaitymo paso ar tapatybės kortelės zona (MRZ) nebuvo
  grupinio valdymo skydelyje „Kas ieškoma“. Dabar ji priklauso grupei
  „Identifikatoriai“ ir kartu su ja gali būti įjungta bei išjungta.

- Kas pasirenka šabloną „Vaivorykštė“ pakeitimo tekstams, dabar gauna ir
  užtemdytas vietas tame pačiame pateikime – anksčiau jos likdavo
  netikėtai klasikiškai juodos. Užtemdymo plotai ir toliau gali būti
  nepriklausomai perjungti į kitą šabloną.

- Taisymo redaktoriaus puslapių skydelis po išsaugotos lango išdėstymo
  atkūrimo galėjo likti tuščias, kol jo plotis nebuvo pakeistas ranka.
  Miniatiūros dabar iš naujo išdėstomos po matomos lango sandaros ir
  iškart atsiduria skydelio viduryje.

- Spalvoti patikros ženklai aplink pakeitimo tekstus PDF failuose
  priklausomai nuo kategorijos ir šviesoforo spalvos buvo vos matomi.
  Šviesus apatinis kontūras dabar patikimai atskiria patikros rėmelį nuo
  spalvoto vietos žymeklio ir puslapio fono.

- Kas taisymo redaktoriuje užtemdo eilutę dokumente su siauru eilučių
  intervalu (būdinga pasiūlymams ir darbų sąrašams), gaudavo juostą,
  kuri kišosi į apatinės eilutės viršutinius elementus – po to ji buvo
  įskaitoma tik per pusę. Dabar juosta baigiasi ties tikrai nupieštu
  gretimos eilutės šriftu; pati užtemdyta eilutė kartu su apatiniais
  elementais lieka visiškai padengta.

- Pratybų dokumentas („Pagalba → Atverti pratybų dokumentą“, taip pat
  apžvalgoje) dabar demonstruoja kiekvieną atpažinimo rūšį: prie
  sugalvoto laiško pridėta nuotrauka su atpažįstamu veidu, ranka
  rašytas parašas, profesija ir skyrius, diagnozė ir vaistas – šalia
  jau buvusio įmonės pavadinimo, sumos ir datos. Ką numatytieji
  nustatymai sąmoningai palieka, paaiškina pats lapas, kartu su
  jungikliu, kuris tai pašalina; veidas nuotraukoje iš gamyklos
  supikseliuojamas.

- Piniginės sumos įprasta vokiška rašyba su simboliu po skaičiaus
  („1.240,00 €“) niekada nebuvo aptinkamos jungikliu „Pašalinti ir
  piniginius sumas“ – „1.240,00 EUR“ ir „€ 1.240,00“ buvo aptinkamos
  visada. Dabar atpažįstamos visos trys rašybos.

- Parašų paieška dabar veikia ir pavieniuose vaizdo failuose: kas valo
  nuskaitymą kaip JPG ar PNG, gauna jame užtemdytus ranka rašytus
  parašus – tą patį atpažinimą, tą pačią žinutę ataskaitoje kaip su PDF.
  Office failuose įterpti vaizdai toliau nėra tikrinami, nes atpažinimas
  ten, kaip nustatyta matavimais, veikia nepatikimai; todėl žymimasis
  langelis dabar vadinasi „PDF ir vaizdo failai: užtemdyti ranka rašytus
  parašus“.

- Užtemdymo juosta, esant siauram eilučių intervalui, galėjo matomai
  kištis į apatinės eilutės viršutinius elementus ir padaryti ją pusiau
  neįskaitomą – juostos aukštis buvo skaičiuojamas iš šrifto metrikos,
  o ne iš to, kas iš tikrųjų yra popieriuje. Dabar juosta baigiasi ties
  tikrai nupieštu gretimos eilutės rašalu tiek taisymo redaktoriuje, tiek
  automatiniame valyme. Pati eilutė kartu su apatiniais elementais lieka
  visada visiškai padengta; jei eilutės tikrai persidengia, juosta
  mieliau lieka ant gretimos eilutės, nei kad kažką atidengia.

- Darbuotojų sąraše su vaidmeniu po vardu moteriškas vadovaujantis
  pavadinimas („Anna Berger“ su „Montageleiterin“ po juo) buvo įtrauktas
  į vardo pakeitimą – vyriška forma šalia liko teisingai. Moteriškos
  „…leiterin“ formos (Montage-, Team-, Projekt-, Bau-, Abteilungs-,
  Betriebs-, Gruppen-, Amtsleiterin) dabar traktuojamos kaip pareigų
  pavadinimas, kaip ir jų vyriški atitikmenys; Filial-, Personal- ir
  Vertriebsleitung naujai įtraukti abiem formomis.

- Įjungiamas profesijos atpažinimas nerasdavo moteriškų vadovaujančių
  vaidmenų, tokių kaip „Projektleiterin“, „Teamleiterin“ ar
  „Abteilungsleiterin“, nors jų vyriškas formas rasdavo. Dabar abi
  formos vertinamos vienodai.

- Peržiūros lange „Mac“ sistemoje kelis kartus paminėtas skaičius
  glaudėsi tiesiai prie termino („Anna Musterfrau2“ vietoj „Anna
  Musterfrau 2“). Tarpas grąžintas.

- Palyginimo lupa turi naują mygtuką šalia mastelio reguliatoriaus: vienu
  paspaudimu ji patalpina rezultatą per visą plotį – po pusę aukščio, o
  originalą tuo pačiu masteliu kaip dokumentą (lupos mastelis tuo metu
  peršoka į 100 %). Antras paspaudimas vėl priglaudžia ją mažą kairėje
  skiltyje ir atkuria ankstesnį lupos mastelį. Šalia esantis apskritimo
  mygtukas dabar tik atstato mastelį – jo paaiškinimo tekstas iki šiol
  klaidingai teigė, kad jis taip pat vėl prišvartuoja langą.

- Taisymo redaktoriaus įrankių juostoje pasirinktam įrankiui vėl matyti,
  kad jis pasirinktas: aktyvaus įrankio mygtukas turi užpildytą plotą su
  mėlynu rėmeliu – taip pat kaip ir kiekvienas kitas įjungtas juostos
  perjungimo mygtukas (pvz., palyginimo lupa ar mokymosi režimas).
  Žymėjimas buvo prarastas dėl rugpjūčio 29 d. naujo mygtukų dizaino.

- Darbų sąrašo pozicijų numeriai („2.3.3.3, 2.3.3.4, 2.3.3.5“ vienas po
  kito) buvo laikomi IP adresais ir pašalinami iš rezultato; trijų
  lygmenų numeriai su metams panašiu paskutiniu nariu („2.3.19, 2.3.20“)
  buvo priskirti kalendorinėms datoms. Didėjanti numerių seka eilutės
  pradžioje dabar laikoma tuo, kas ji iš tikrųjų yra – pozicijų sąrašu;
  tikri adresai (tinklo lentelės su techniniu žodžių kontekstu, skaičiai
  virš 99) ir tikros datos toliau atpažįstami.

- Pavardės, tokios kaip „Müller“, „Fischer“, „Bauer“, „Koch“, „Wagner“,
  „Schneider“, „Weber“, „Jäger“, „Schmied“, „Becker“, „Schuster“,
  „Schäfer“ ar „Meister“, sąrašuose formos „Pavardė, Vardas“ (pvz.,
  „Dalyviai: Müller, Peter; Nowak, Anna“) likdavo neuždengtos, nes jos
  tuo pačiu metu yra ir įprastos profesijų pavadinimai. Dabar jos
  patikimai atpažįstamos.

- Juodinant PDF, juosta siaurose lentelės ląstelėse galėjo nusinešti
  visą ląstelę: iš radinio „D-LINK“ darbų sąraše buvo pašalintas visas
  šalia esantis produkto aprašymas, nors peržiūroje buvo minimas tik pats
  radinys. Juosta toliau dengia visas adreso bloko eilutes ir lauko
  žymėjimus, tačiau prarija ne daugiau nereikšmingo turinio, nei
  reikalauja saugotino turinio – aprašymas šalia radinio dabar lieka.

- Po „Atkurti rodinį“ taisymo redaktoriuje puslapių skydelis likdavo
  tuščias – puslapių miniatiūros vėl matėsi tik uždarius ir iš naujo
  atidarius langą. Dabar jos matomos iškart po atkūrimo, kaip ir anksčiau
  – per vidurį.

- Taisymo redaktorius turi ketvirtą įrankį: **Pašalinti** be pakaitalo
  išima tekstą po rėmeliu – be juostos (užtemdymo) ir be vietos žymeklio
  (pakeitimo); tarpas lieka matomai tuščias. Jis veikia tiksliai pagal
  žodį; jei po juo yra vaizdas, jo fonas išvalomas iki balto, o „Atkurti
  originalą“ atšaukia ir pašalinimą be pakaitalo. Turi savo įrankių
  juostos simbolį ir taikiklio ženklelį (kryžius), savo spartųjį klavišą
  visomis 18 kalbų (vokiškai F kaip entFernen).

- PDF paieškos juostoje „Aplankas …“ dabar stovi dešinėje šalia paieškos
  parinkčių. Nuo tada, kai šalia užtemdymo atsirado ir radinių keitimas,
  penki mygtukai įprastame lango plotyje nebetilpo greta – pirmasis buvo
  suspaustas, o jo tekstas nukirstas.

- „Atstatyti visus nustatymus“ dabar atstato ir žymimąjį langelį
  „Pakeisti raudoną/žalią kitomis spalvomis“ ir pažymi jį kaip
  „pakeista“, kaip ir bet kurį kitą, kai jis skiriasi nuo numatytosios
  pristatymo būsenos.

- Pakeitimo tekstai PDF failuose dabar atrodo tolygiau: kur pilnas
  vietos žymeklis turėtų būti gerokai mažesnis nei jo eilutė (pvz.,
  „[BEG16]“ suspaustas į trumpą žodį, tokį kaip „Das“), vietoj to rodoma
  eilutės dydžio trumpoji forma („[B16]“) – gerai įskaitoma, o ne
  smulki, o atkūrimo numeris perneša abi rašybas. Vietos žymeklis tampa
  itin mažas tik tada, kai net trumpiausia forma nerandama vietos – tai
  vis tiek geriau nei juosta be jokios informacijos.

- Daugiaspalvis pakeitimo tekstas (perėjimas ar vaivorykštė) PDF faile
  likdavo nepakitęs tik iki kito veiksmo: kiekvienas tolesnis pakeitimas
  ar užtemdymas tame pačiame puslapyje galėjo sustumti jau įrašytus
  vietos žymeklius į neįskaitomą, suspaustą raidžių krūvą – kas
  redaktoriuje keitė žodis po žodžio, vietoj „[BEG17]“ matydavo tik vieną
  ant kito atspausdintus ženklus. Kartą įrašyti vietos žymekliai dabar
  lieka tokie, kokie buvo įrašyti.

- Nuolatinių išimčių jungiklis peržiūroje dabar vadinasi „Niekada
  nešalinti“ – kaip ir sąrašas, į kurį jis įrašo; anksčiau ten buvo
  „niekada daugiau“. Šalia esanti radinio eilutė dabar tvarkingesnė:
  informacijos ženklelis „ⓘ“ yra didesnis ir lengviau pataikomas, o
  žymimasis langelis, keitimo žyma ir mygtukas turi bendrą aukštį.
  Sakinys apie radinį dabar tikrai naudoja skirtą plotį – ankstesnis
  pločio nustatymas buvo tyliai ignoruojamas, ir ištrauka lūžo kaip siaura
  juostelė.

- Redaktoriuje pelės žymeklis dabar rodo, koks įrankis veikia: taikiklis
  taikymui, šalia jo mažas ženklas – juosta užtemdymui, mainų rodyklės
  keitimui, atšaukimo lankas atkūrimui, pikselių tinklelis
  supikseliavimui. Ankstesni rankos simboliai pašalinti; ranka visur kitur
  reiškia „griebti ir stumti“. Dabar ji turi tinkamą užduotį: virš
  raudonai pažymėto žodžio ar juostos žymeklis tampa rodančia ranka –
  ten pakanka vieno paspaudimo.

- „Maksimalus atpažinimas (DI)“ nebesiūlo atsisiunčiamo, vietinio kalbos
  modelio – ši pakopa dabar skaičiuoja išimtinai per savo DI, sukonfigūruotą
  skiltyje „Prijungti savo DI“. Kas jau turėjo prijungtą savo serverį,
  nepastebės skirtumo.

- Peržiūros vedlys dabar paaiškina ir informacijos ženklelį „ⓘ“, kuris
  rodo sakinį apie radinį. Ir pats šis sakinys geriau įskaitomas: vienu
  laipsniu didesnis šriftas, didesnis eilučių intervalas, fiksuotas
  plotis vietoj siauro, glaudžiai sugrūsto perkėlimo.
- Taip pat „Patikrinti failą“, „Atpažinimo taisyklės ir savi terminai“,
  „Valyti tekstą“ ir „Valyti vaizdą“ dabar turi savo apžvalgą – per naują
  mygtuką „Apžvalga per langą“, nes šie keturi langai neturi savo meniu
  juostos.
- Vardai po devyniomis ukrainietiškomis sutarties vaidmenų antraštėmis
  likdavo nepilnai atpažinti su homografine pavarde, kai antraštė stovėjo
  eilutėje viena: „Покупець“/„Продавець“ (pirkėjas/pardavėjas),
  „Поручитель“/„Боржник“ (laiduotojas/pagrindinis skolininkas),
  „Свідок“ (liudytojas), „Орендодавець“/„Орендар“
  (nuomotojas/nuomininkas) ir „Спадкодавець“/„Спадкоємець“
  (palikėjas/paveldėtojas). Vardai dabar pilnai atpažįstami.

- Excel knygos pavadintos srities komentaras (vardų tvarkytuvė, laukas
  „Komentaras“) perkeldavo jame įrašytą vardą nepakeistą. Dabar jis
  valomas taip pat, kaip likęs knygos turinys.

- Vardai po septyniomis vengriškomis sutarties vaidmenų antraštėmis
  likdavo visiškai neaptikti su homografine pavarde:
  „Bérbeadó“/„Bérlő“ (nuomotojas/nuomininkas),
  „Vevő“/„Eladó“ (pirkėjas/pardavėjas),
  „Kezes“/„Főadós“ (laiduotojas/pagrindinis skolininkas) ir „Tanú“
  (liudytojas). Vardai dabar pilnai atpažįstami.

- Vardai po čekiška pirkėjo antrašte „Kupující“ likdavo visiškai neaptikti
  su homografine pavarde. Vardas dabar pilnai atpažįstamas.

- Vardai po rusiška globėjo antrašte „Опекун“ likdavo visiškai neaptikti
  su homografine pavarde. Vardas dabar pilnai atpažįstamas.

- Vardai po šešiomis kitomis kroatiškomis antraštėmis likdavo neaptikti:
  „Jamac“ (laiduotojas), „Glavni dužnik“/„Dužnik“ (pagrindinis
  skolininkas/skolininkas), „Ostavitelj“ (palikėjas), „Nasljednik“
  (paveldėtojas) ir „Vjerovnik“ (kreditorius). Vardai dabar pilnai
  atpažįstami.

- Išsaugotas HTML puslapis su įterptu papuslapiu `<embed>` elemento
  `src` atributu (vietoj `data` prie `<object>`) perkeldavo jame esančius
  asmens duomenis nepakeistus. Dabar jie valomi taip pat, kaip ir su
  `<object>`.

- Vardai po penkiomis danų sutarties vaidmenų antraštėmis likdavo
  nepilnai atpažinti su homografine pavarde, kai antraštė stovėjo su
  dvitaškiu prieš vardą: „Arvelader“/„Arving“
  (palikėjas/paveldėtojas), „Befuldmægtiget“/„Fuldmagtsgiver“
  (įgaliotinis/įgaliotojas) ir „Værge“ (globėjas). Vardai dabar pilnai
  atpažįstami; atitinkamos norvegiškos antraštės papildomai įtrauktos
  saugumo tikslais.

- Vietos žymekliai Word ir PowerPoint failuose dabar turi tą pačią spalvą
  kaip pasirinktame pateikime (vienspalvis, perėjimas, vaivorykštė ar
  pagal kategoriją) – anksčiau ten jie likdavo įprastos teksto spalvos,
  net jei PDF rezultatai jau seniai buvo spalvoti.

- „Kopijuoti kaip tekstą“ ir „Kopijuoti kaip Markdown“ įdeda rezultato
  aiškų tekstą tiesiai į iškarpinę – įklijavimui į pokalbį, laišką ar
  kitą programą, neatidarant failo.

- Vardai po penkiomis kitomis slovėniškomis antraštėmis likdavo
  neaptikti: „Toženec“ (atsakovas), „Tožnik“ (ieškovas), „Zastavitelj“
  (įkaito davėjas), „Zastavni upnik“ (įkaito kreditorius) ir
  „Darovalec“ (dovanotojas). Vardai dabar pilnai atpažįstami.

- Word sekamojo lentelės langelio pakeitimo (įterpto, ištrinto ar
  sujungto langelio) autoriaus vardas likdavo faile, net jei tas pats
  vardas kaip komentaro autorius jau seniai buvo pašalintas. Dabar jis
  taip pat pašalinamas.

- Vardai po devyniomis kitomis slovėniškomis antraštėmis likdavo
  neaptikti: „Najemodajalec“/„Najemnik“ (nuomotojas/nuomininkas),
  „Zapustnik“/„Dedič“ (palikėjas/paveldėtojas),
  „Upnik“/„Dolžnik“ (kreditorius/skolininkas), „Glavni dolžnik“
  (pagrindinis skolininkas) ir „Skrbnik“ (globėjas/prižiūrėtojas).
  Vardai dabar pilnai atpažįstami.

- Vardai po penkiomis slovėniškomis antraštėmis likdavo neaptikti:
  „Izvedenec“ (ekspertas), „Kupec“ (pirkėjas), „Prodajalec“
  (pardavėjas), „Naročnik“ (užsakovas) ir „Izvajalec“ (vykdytojas).
  Vardai dabar pilnai atpažįstami.

- Vardai po penkiomis kitomis lietuviškomis antraštėmis likdavo
  neaptikti: „Užsakovas“, „Vykdytojas“, „Vežėjas“, „Siuntėjas“ ir
  „Arbitras“. Vardai dabar pilnai atpažįstami.

- Vardai po šešiomis kitomis lietuviškomis antraštėmis likdavo neaptikti:
  „Įgaliotinis“, „Įgaliotojas“, „Naudos gavėjas“ (draudimo
  atveju), „Trečiasis asmuo“ (nebylinėjimosi proceso šalis civiliniame
  procese), „Ankstesnis nuomininkas“ ir „Naujasis nuomininkas“. Vardai
  dabar pilnai atpažįstami.

- ODT dokumentų žymė (`text:bookmark`) laisvai pavadinama, dažnai pagal
  vietą, į kurią rodo (pvz., „Herr_Mueller_Unterschrift“) – neįžvelgiama
  skaitytojui, bet pažodžiui esanti faile. Vardas dabar taip pat
  išvalomas.

- Vardai po aštuoniomis kitomis lietuviškomis antraštėmis likdavo
  neaptikti: „Pareiškėjas“, „Suinteresuotas asmuo“ (atsakovas
  nebylinėjimosi procese), „Ekspertas“, „Bankroto administratorius“,
  „Valdybos narys“, „Direktorius“, „Palikėjas“ ir „Įpėdinis“. Vardai
  dabar pilnai atpažįstami.
- Vardai po septyniomis kitomis lietuviškomis antraštėmis likdavo
  neaptikti: „Liudytojas“, „Vertėjas“, „Notaras“, „Dovanotojas“,
  „Apdovanotasis“, „Pirkėjas“ ir „Pardavėjas“. Vardai dabar pilnai
  atpažįstami.

- Vardai po šešiomis kitomis lietuviškomis antraštėmis likdavo neaptikti:
  „Globėjas“, „Palikimo administratorius“, „Laiduotojas“, „Pagrindinis
  skolininkas“, „Nuomotojas“ ir „Nuomininkas“. Vardai dabar pilnai
  atpažįstami.

- Vardas po lietuviška antrašte „Ieškovas“/„Atsakovas“ (kaip proceso
  šalis) likdavo neaptiktas, nepriklausomai nuo to, ar pavardė tuo
  pačiu metu yra įprastas žodis (pvz., „Vilkas“) ar ne. Vardas dabar
  pilnai atpažįstamas.

- ODT dokumentų asmenų rodyklės įrašas (žymė terminų rodyklei) vardą
  įrašydavo antrą kartą savo pačios rikiavimo rakte – nematomai
  pagrindiniame tekste, bet pažodžiui vėliau sukuriamoje rodyklėje.
  Raktas dabar taip pat išvalomas.

- PowerPoint pristatymo skaidrės pavadinimas ir skyriaus pavadinimas
  (matomi pasirinkimo srityje arba skaidrių rūšiavime) likdavo
  neišvalyti, nes abu yra elemento, kuris nėra skaidrės tekstas,
  atributas. Dabar abu atpažįstami.

- Lietuviškas dvigubas vardas su brūkšneliu, pvz. „Petraitis-Kazlauskas“,
  prarasdavo antrąją savo pusę, kai tik prieš jį buvo bet koks tekstas
  (tik teksto pradžioje jis likdavo pilnas): pavardė dabar visada
  pilnai atpažįstama.

- Vardas po kroatiška antrašte „Cesionar“ (cesijonarijus reikalavimo
  perleidime) sukeldavo klaidingą aliarmą, nes pats lauko žymėjimas
  buvo klaidingai skaitomas kaip asmuo. Vardas po rusiška antrašte
  „Цессионарий“ (taip pat cesijonarijus), priešingai, likdavo visiškai
  neaptiktas. Abu atvejai dabar ištaisyti.

- Vardas po antrašte „Zedent“/„Zessionar“ (vokiečių k., reikalavimo
  perleidimas) likdavo visiškai neaptiktas, kai pavardė tuo pačiu metu
  buvo įprastas žodis (pvz., „Bauer“). Vardas dabar pilnai
  atpažįstamas.

- Vardas po lenkiška antrašte „Darczyńca“/„Obdarowany“ (dovanotojas/
  apdovanotasis dovanojimo sutartyje) likdavo neaptiktas, kai pavardė
  tuo pačiu metu buvo įprastas žodis (pvz., „Wilk“ = vilkas). Taip pat
  rumuniška antraštė „Donatar“ (apdovanotasis) su įprasta pavarde
  likdavo tarsi tariama vardo dalis. Abu atvejai dabar ištaisyti.

- Vardas po lenkiška antrašte „Wierzyciel“/„Dłużnik“ (išieškotojas/
  skolininkas vykdymo procese arba bendrasis kreditorius/skolininkas)
  likdavo neaptiktas, kai pavardė tuo pačiu metu buvo įprastas žodis
  (pvz., „Wilk“ = vilkas). Vardas dabar pilnai atpažįstamas.

- Vardas po lenkiška antrašte „Poręczyciel“/„Dłużnik główny“
  (laiduotojas/pagrindinis skolininkas laidavimo sutartyse) likdavo
  neaptiktas, kai pavardė tuo pačiu metu buvo įprastas žodis (pvz.,
  „Wilk“ = vilkas). Vardas dabar pilnai atpažįstamas.

- Vardas po lenkiška antrašte „Ubezpieczony“/„Ubezpieczający“
  (apdraustasis/draudėjas draudimo polisuose) likdavo dalinai ar
  visiškai neaptiktas, kai pavardė tuo pačiu metu buvo įprastas žodis
  (pvz., „Wilk“ = vilkas). Taip pat vardas po „Osiguranik“/
  „Osiguravatelj“ (kroatų k., tie patys vaidmenys) ten dingdavo kartu
  su vardu visiškai (pvz., „Golub“ = balandis). Abu vardai dabar pilnai
  atpažįstami.

- Vardas po lenkiška antrašte „Pełnomocnik“/„Mocodawca“ (įgaliotinis/
  įgaliotojas įgaliojimo dokumentuose) likdavo neaptiktas, kai pavardė
  tuo pačiu metu buvo įprastas žodis (pvz., „Wilk“ = vilkas). Taip pat
  vardas po „Opunomoćenik“/„Opunomoćitelj“ (kroatų k., tie patys
  vaidmenys) ten dingdavo net visiškai kartu su vardu. Abu vardai dabar
  pilnai atpažįstami.

- Vardas po lenkiška antrašte „Pozwany“ (atsakovas kaip proceso šalis)
  likdavo neaptiktas, kai pavardė tuo pačiu metu buvo įprastas žodis
  (pvz., „Wilk“ = vilkas). Vardas dabar pilnai atpažįstamas.

- Vardas po kroatiška antrašte „Najmoprimac“/„Najmodavac“ (nuomininkas/
  nuomotojas nuomos sutartyse) likdavo neaptiktas, kai pavardė tuo pačiu
  metu buvo įprastas žodis (pvz., „Kovač“ = kalvis). Vardas dabar
  pilnai atpažįstamas.

- Vardas po lenkiška antrašte „Pracodawca“/„Pracownik“ (darbdavys/
  darbuotojas kaip sutarties šalis darbo sutartyse) likdavo dalinai
  neaptiktas, kai pavardė tuo pačiu metu buvo įprastas žodis (pvz.,
  „Krawiec“ = siuvėjas). Vardas dabar pilnai atpažįstamas.

- Vengrijos šalių kataloge buvo tik asmens identifikatoriai ir PVM
  mokėtojo kodas: dabar atpažįstamas prekybos registro numeris
  (Cégjegyzékszám), jei prieš jį iš karto stovi lauko žodis
  „Cégjegyzékszám“ arba santrumpa „Cg.“ – pats numeris neturi kontrolinio
  skaitmens.

- Estijos šalių kataloge buvo tik Isikukood: dabar su kontroliniu
  skaitmeniu atpažįstamas Käibemaksukohustuslase number (PVM mokėtojo
  numeris kiekvienoje estiškoje sąskaitoje).

- Latvijos šalių kataloge buvo tik Personas kods: dabar su kontroliniu
  skaitmeniu atpažįstamas PVN reģistrācijas numurs juridiniams asmenims
  (įmonės identifikatorius kiekvienoje latviškoje sąskaitoje).

- Elektroninis laiškas su šifruotu turiniu (S/MIME arba PGP/MIME
  apvalkalas, `multipart/encrypted`) buvo pateikiamas be jokio
  įspėjimo kaip tariamai visiškai patikrintas, nors jo tikrasis turinys
  liko šifruotas ir dėl to nepatikrintas. Tokie laiškai dabar, kaip ir
  netikrintas priedas, apie tai įspėja.

- Maltos šalių kataloge trūko: dabar atpažįstamas maltietiškas PVM
  mokėtojo kodas (VAT number).

- Liuksemburgo šalių kataloge trūko: dabar atpažįstamas liuksemburgiškas
  PVM mokėtojo kodas (n° TVA).

- Sakinio pradžioje esantis bulgariškas „Изчакайте“ („Palaukite!“) buvo
  klaidingai pateikiamas kaip vietovė – ta pati modelio riba kaip ir
  anksčiau su vengriškomis, lenkiškomis, čekiškomis ir kitomis
  raginimo formomis be atskiro kalbos modelio. Šis klaidingas aliarmas
  dabar nebepasitaiko.

- Vardas po antrašte „Zleceniodawca“, „Zleceniobiorca“ (lenkų k.),
  „Prestator“ (rumunų k.), „Naručitelj“ ar „Izvođač“ (kroatų k.)
  likdavo dalinai ar visiškai neaptiktas, kai pavardė tuo pačiu metu
  buvo įprastas žodis (pvz., „Wilk“, „Vuk“ = vilkas, „Vulpe“ = lapė,
  „Sokol“ = sakalas). Vardas dabar pilnai atpažįstamas.

- Vardas po antrašte „Nadawca“ (lenkų k.), „Afsender“ (danų k.) ar
  „Pošiljatelj“ (slovėnų k.) likdavo dalinai ar visiškai neaptiktas,
  kai pavardė tuo pačiu metu buvo įprastas žodis (pvz., „Sowa“ = pelėda,
  „Bager“ = kepėjas, „Volk“ = vilkas). Vardas dabar pilnai atpažįstamas.

- Vardas po antrašte „Gavėjas“ (lietuvių k.) ar „Prejemnik“ (slovėnų k.)
  likdavo dalinai ar visiškai neaptiktas, kai pavardė tuo pačiu metu
  buvo įprastas žodis (pvz., „Vilkas“). Kaip jau ir su „Primatelj“
  (kroatų k.) bei „Modtager“ (danų k.), vardas dabar pilnai
  atpažįstamas.

- Aplinkraščio antraštė, tokia kaip „To All Staff“ ar „To All
  Employees“, buvo klaidingai atpažįstama ir pašalinama kaip asmens
  vardas. Dabar tai nebepasitaiko.

- Vardas po antrašte „Primatelj“ (kroatų k.) ar „Modtager“ (danų k.)
  likdavo dalinai neaptiktas, kai pavardė tuo pačiu metu buvo įprastas
  žodis (pvz., „Golub“ = balandis, „Bager“ = kepėjas). Kaip jau ir su
  „Odbiorca“ (lenkų k.) bei „Destinatar“ (rumunų k.), vardas dabar
  pilnai atpažįstamas.

- Pilnas vardas danų, norvegų ar graikų dokumento parašo eilutėje
  likdavo dalinai neaptiktas, kai antraštė „Underskrift“ ar „Υπογραφή“
  stovėjo viena virš vardo – graikų kalbos atveju pavardė net buvo
  atpažįstama kaip vietovė, o ne kaip vardas. Kaip jau ir su
  „Подпись“ (rusų k.), vardas dabar pilnai atpažįstamas.

- Tekstas šoniniu formatu padarytoje telefono nuotraukoje (įprastas
  vertikalus kadras, kuris rodomas stačias tik dėl vaizdo pasukimo
  žymos) galėjo likti nepastebėtas teksto atpažinimo, nes iki šiol jis
  skaitė žalius, gulinčius pikselius. Tokios nuotraukos dabar prieš
  skaitymą teisingai pasukamos – kaip jau anksčiau buvo daroma veidų
  atpažinimui.

- Pilnas vardas rusų, ukrainiečių ar lietuvių dokumento parašo eilutėje
  likdavo dalinai neaptiktas, kai antraštė „Подпись“, „Підпис“ ar
  „Parašas“ stovėjo viena virš vardo – vardas ar tėvavardis dingdavo.
  Kaip jau ir su „Potpis“ (kroatų k.), vardas dabar pilnai atpažįstamas.

- Veidas šoniniu formatu padarytoje telefono nuotraukoje (įprastas
  vertikalus kadras, kuris rodomas stačias tik dėl vaizdo pasukimo
  žymos) galėjo likti nepastebėtas veidų atpažinimo, nes iki šiol ji
  tikrino žalius, gulinčius pikselius. Tokios nuotraukos dabar prieš
  paiešką teisingai pasukamos.

- Pilnas vardas kroatiško dokumento parašo eilutėje likdavo dalinai
  neaptiktas, kai antraštė „Potpis“ stovėjo viena virš vardo arba su
  dvitaškiu prieš jį – vardas dingdavo, nesvarbu, ar tai atskira eilutė,
  ar forma „Potpis: Vardas Antrasvardis Pavardė“. Kaip jau ir su
  „Unterschrift“ bei „Signature“, vardas dabar pilnai atpažįstamas.

- Santuokos pavardė po asmens statuso santrumpomis „verh.“ (ištekėjusi/
  vedęs) ir „verw.“ (našlė/našlys) iki šiol likdavo visiškai neaptikta,
  nesvarbu, ar skliaustuose, po kablelio, ar be tarpo prilipdyta
  („Anna Meier (verh. Weber)“, „Klaus Bauer (verw.Fischer)“) – kaip jau
  ir su „geb.“, dabar ji patikimai atpažįstama.

- Vardas po prokūros parašu „ppa.“ (pvz., verslo el. laiško ar verslo
  laiško parašo eilutėje) su su profesija sutampančia pavarde, tokia
  kaip „Bauer“ ar „Koch“, iki šiol likdavo dalinai ar visiškai
  neaptiktas – kaip jau ir su „gez.“, dabar jis patikimai atpažįstamas.

- Lenkiško asmens tapatybės kortelės (dowód osobisty) numeris buvo
  atpažįstamas tik be tarpo tarp serijos ir numerio („ABS123456“). Bet
  būtent taip dokumentas šios reikšmės nespausdina – oficialiai ten yra
  tarpas („ABS 123456“), ir tokia rašyba numeris iki šiol likdavo
  neaptiktas.

- Animuotas PNG (APNG, pvz., trumpas ekrano įrašas, išsaugotas kaip PNG
  vietoj GIF) iki šiol buvo tikrinamas ir valomas tik pagal pirmą
  vaizdą, apie tai neinformuojant – kaip anksčiau su animuotu WebP,
  Maskuro dabar informuoja, kad kiekvienas kitas vaizdas rezultate lieka
  netikrintas.

- Animuotas WebP vaizdas (pvz., iš ekrano nuotraukos įrankio ar
  pokalbių programos su keliais vaizdais viename faile) iki šiol buvo
  tikrinamas ir valomas tik pagal pirmą vaizdą, apie tai neinformuojant
  – kaip anksčiau su daugiapuslapiu TIFF, Maskuro dabar informuoja, kad
  kiekvienas kitas vaizdas rezultate lieka netikrintas.

- Slovėniškas dvigubas vardas su brūkšneliu („Ana-Marija Novak“)
  prarasdavo priekinę pusę, kai prieš jį tekste buvo sakinys – ta pati
  klaida, kaip anksčiau su lenkų kalba. „Ana-“ likdavo neuždengta
  aiškiame tekste, nors likusi vardo dalis jau buvo pakeista.

- Lenkiškas dvigubas vardas su brūkšneliu („Anna-Maria Kowalska“)
  prarasdavo priekinę pusę, kai prieš jį buvo sakinys ar prielinksnis,
  toks kaip „z“/„od“ – likusi vardo dalis buvo pakeista, „Anna-“ likdavo
  neuždengta aiškiame tekste.

- Kazachiškos mandagumo formos „Хабарласыңыз“/„Байланысыңыз“
  (susisiekite su mumis) bei serbiškos veiksmažodžių formos „Помоћи“,
  „Чекамо“ ir „Пишите“ be atskiro kalbos atpažinimo modelio telefono
  sakiniuose buvo klaidingai atpažįstamos kaip asmens vardas ar vietovė.

- Azerbaidžanietiškas mandagumo žodis „Xahiş“ (prašymas) be atskiro
  kalbos atpažinimo modelio telefono sakiniuose buvo klaidingai
  atpažįstamas kaip asmens vardas.

- Indoneziški ir malajiški mandagumo/raginimo žodžiai be atskiro kalbos
  atpažinimo modelio, tokie kaip „Silakan“, „Mohon“ (indonezų k.),
  „Sila“ ir „Tolong“ (malajų k.), telefono sakiniuose buvo klaidingai
  atpažįstami kaip asmens vardas ar vietovė.

- Uzbekiška raginimo forma „Kutamiz“ (mes laukiame) be atskiro kalbos
  atpažinimo modelio telefono sakiniuose buvo klaidingai atpažįstama
  kaip vietovė.

- Turkiškos raginimo formos be atskiro kalbos atpažinimo modelio, tokios
  kaip „Arayınız“ (paskambinkite) ir „Bekliyoruz“ (mes laukiame),
  telefono sakiniuose buvo klaidingai atpažįstamos kaip asmens vardas.

- Raginimo formos kitomis kalbomis be atskiro kalbos atpažinimo modelio
  (čekų, slovakų, graikų), tokios kaip „Zavolejte“ (paskambink),
  „Prosíme“ (mes prašome) ir „Περιμένουμε“ (mes laukiame), telefono
  sakiniuose buvo klaidingai atpažįstamos kaip asmens vardas ar vietovė.

- Vengriškos ir lenkiškos raginimo formos, tokios kaip „Hívjon“
  (paskambink), „Kérjük“ (mes prašome), „Várjuk“ (mes laukiame),
  „Zadzwoń“ (paskambink) ir „Czekamy“ (mes laukiame), telefono
  sakiniuose buvo klaidingai atpažįstamos kaip asmens vardas ar vietovė.

- Numeruotame vardų sąraše be lentelės formos (pvz., „1. Robert Brown“,
  po juo „2. Mary Johnson“) su tam tikromis angliškomis pavardėmis
  (tarp jų „Brown“, „White“, „Green“, „Black“, „Young“) vardas likdavo
  visiškai nepastebėtas – kalbos modelis prijungdavo sekančios eilutės
  numerį prie vardo, todėl radinys niekada tiksliai nesutapdavo.

- Lenkiškame kalbos modelyje prieš pavardę einanti vardo raidė
  (pvz., „J. Kowalski“, „A. Nowak“) likdavo neatpažinta ir neišvalyta
  tekste – buvo pakeičiama tik pavardė. Kitos tikrintos kalbos (tarp jų
  vokiečių, anglų, rumunų, kroatų, vengrų, rusų) tą pačią raidę jau
  anksčiau perimdavo kartu.

- Asmens vardas po mažosiomis raidėmis rašomu titulu, tokiu kaip „dr.“,
  „ing.“ ar „dipl. ing.“, vengrų, rumunų ir kroatų kalbomis visai
  nebūdavo atpažįstamas – dingdavo ne tik titulas, bet ir visas vardas
  (pvz., „dr. Kovács Béla“, „ing. Andrei Popescu“, „dipl. ing. Marko
  Horvat“).
- Slovėniškuose posėdžių protokoluose grynas vaidmens pavadinimas prieš
  dvitaškį (pvz., „Tajnik:“, „Podpredsednik:“, „Poročevalec:“,
  „Predsedujoči:“) buvo klaidingai atpažįstamas kaip asmens vardas,
  kai tik kitoje protokolo vietoje jau buvo tikras kalbėtojo vardas.
- Rusiškuose posėdžių protokoluose grynas vaidmens pavadinimas prieš
  dvitaškį (pvz., „Секретарь:“, „Докладчик:“, „Докладчица:“) buvo
  klaidingai atpažįstamas kaip asmens vardas, kai tik kitoje protokolo
  vietoje jau buvo tikras kalbėtojo vardas.
- Rumuniškuose posėdžių protokoluose grynas vaidmens pavadinimas su
  žymimuoju artikeliu prieš dvitaškį (pvz., „Secretarul:“,
  „Președintele:“, „Vicepreședintele:“, „Moderatorul:“,
  „Consilierul:“) buvo klaidingai atpažįstamas kaip asmens vardas –
  „Președintele“ jau savaime, kiti papildomai, kai tik kitoje protokolo
  vietoje jau buvo tikras kalbėtojo vardas.
- Kroatiškuose posėdžių protokoluose grynas vaidmens pavadinimas prieš
  dvitaškį (pvz., „Izvjestiteljica:“, „Zapisničar:“/„Zapisnicar:“,
  „Predsjedavajući:“) buvo klaidingai atpažįstamas kaip asmens vardas.
- Lenkiškas pašto dėžutės adresas „Skrytka pocztowa“ po siuntėjo ar
  gavėjo antrašte (pvz., „Odbiorca: Skrytka pocztowa 45“) buvo
  klaidingai atpažįstamas kaip asmens vardas.
- Kroatiškas pašto dėžutės adresas „Poštanski pretinac“ po adreso
  antrašte „Adresa:“ (pvz., „Adresa: Poštanski pretinac 45“, taip pat
  su pridėtu numerio žymėjimu „br.“) buvo klaidingai atpažįstamas kaip
  asmens vardas.
- Vietovė be papildomos antraštės norvegiškame tekste (pvz., „Anna
  Hansen bor i Oslo“) nebuvo atpažįstama – savas kalbos modelis ten
  vietoves dažniausiai žymi savu, iki šiol nepriskirtu žymikliu, o ne
  įprastu „LOC“.
- Data ISO tvarka metai-mėnuo-diena su brūkšneliu ar tašku (pvz.,
  „2024-12-31“) kai kuriomis kalbomis visai nebuvo atpažįstama kaip
  data – labiausiai pastebima lietuvių kalba, kur oficialiuose
  raštuose datos dažniausiai nurodomos šia tvarka.
- Vengriškas PVM mokėtojo kodas (közösségi adószám) oficialiai
  vienodai galiojančia, be skirtukų 11 skaitmenų forma (pvz.,
  „12345678123“ vietoj „12345678-1-23“) nebuvo atpažįstamas.
- Lenkiškas mokesčių mokėtojo numeris NIP su skirtukais grupuotas
  3-2-2-3 (pvz., „856-73-46-215“, kaip įprasta įmonių ir individualių
  verslininkų sąskaitose) nebuvo atpažįstamas – veikė tik grupavimas
  3-3-2-2 fiziniams asmenims.
- Įmonės pavadinimas po slovakiška lauko antrašte „Zamestnávateľ:“ ar
  „Názov zamestnávateľa:“ (darbdavys/įmonė) nebuvo atpažįstamas.
- Įmonės pavadinimas po rumuniška lauko antrašte „Angajator:“ ar
  „Denumire angajator:“ (darbdavys/įmonė) nebuvo atpažįstamas.
- Įmonės pavadinimas po vengriška lauko antrašte „Cég:“ ar
  „Munkáltató:“ (įmonė/darbdavys) nebuvo atpažįstamas.
- Įmonės pavadinimas po lenkiška lauko antrašte „Pracodawca:“ ar
  „Nazwa firmy:“ (darbdavys/įmonė) nebuvo atpažįstamas.
- Įmonės pavadinimas po slovėniška lauko antrašte „Podjetje:“ ar
  „Delodajalec:“ (įmonė/darbdavys) nebuvo atpažįstamas.
- Įmonės pavadinimas po kroatiška lauko antrašte „Tvrtka:“ ar
  „Poslodavac:“ (įmonė/darbdavys) nebuvo atpažįstamas.
- Išrašyta piniginė suma su mažosiomis raidėmis rašoma valiuta (pvz.,
  „500 euro“) nebuvo atpažįstama, veikė tik didžioji raidė („Euro“).
- Pavardė po „Schwager“/„Schwägerin“ (svainis/svainė; pvz., „Der
  Schwager Bauer erhält die Erbschaft.“) nebuvo atpažįstama.
- Turkiško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „34000 İstanbul İstiklal Caddesi No:
  45“) namo numeris likdavo neišvalytas.
- Slovakiško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „831 01 Bratislava Hlavná 15“) namo
  numeris likdavo neišvalytas.
- Gimimo šalis be papildomos antraštės kroatiškame formos lauke (pvz.,
  „Zemlja rođenja: Njemačka“) nebuvo atpažįstama.
- Gimimo šalis be papildomos antraštės lietuviškame formos lauke (pvz.,
  „Gimimo valstybė: Vokietija“) nebuvo atpažįstama.
- Gimimo ar gyvenamosios vietos šalis be papildomos antraštės lenkiškame
  formos lauke (pvz., „Kraj: Niemcy“) nebuvo atpažįstama.
- Pilietybė ar gyvenamoji vietovė be papildomos antraštės slovėniškame
  formos lauke (pvz., „Državljanstvo: Nemčija“) nebuvo atpažįstama.
- Gyvenamosios vietos šalis be papildomos antraštės norvegiškame formos
  lauke (pvz., „Bosted: Tyskland“) nebuvo atpažįstama.
- Naujas nustatymų puslapis „Pranešimai“ (anksčiau skyrius skiltyje
  „Programa“): trys užduočių juostos pranešimai (peržiūra paruošta,
  apdorojimas baigtas, atnaujinimas atsisiųstas) dabar turi savo vietą.
- Nauja: rezultatas papildomai gali būti išsaugotas kaip grynas teksto
  failas (.txt) arba su .md plėtiniu šalia – tolesniam apdorojimui DI
  ar kitoje programoje.
- Kroatiškame kontaktiniame duomenyje su antrašte „Osoba za kontakt“/
  „Kontakt osoba“ (pvz., „Osoba za kontakt: Golub Marko“) vardas
  likdavo visiškai neatpažintas, kai pavardė tuo pačiu metu buvo
  įprastas daiktavardis (Golub = „balandis“).

- Rumuniškame kontaktiniame duomenyje su antrašte „Persoana de
  contact“/„Persoană de contact“ (pvz., „Persoana de contact: Lup
  Ion“) vardas likdavo visiškai neatpažintas, kai pavardė tuo pačiu
  metu buvo įprastas daiktavardis (Lup = „vilkas“) ir vardas buvo labai
  trumpas bei bendrinis.

- Lenkiškame kontaktiniame duomenyje su antrašte „Osoba
  kontaktowa“/„Osoba do kontaktu“ (pvz., „Osoba kontaktowa: Wilk
  Adam“) pavardė likdavo neatpažinta, kai ji tuo pačiu metu buvo
  įprastas daiktavardis (Wilk = „vilkas“, Zielony = „žalias“).

- Rumuniško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „010061 București Strada Victoriei
  30“) namo numeris likdavo neišvalytas.
- Serbiško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „11000 Beograd Bulevar Kralja
  Aleksandra 73“) namo numeris likdavo neišvalytas.
- Graikiško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „104 32 Αθήνα Ερμού 15“) namo numeris
  likdavo neišvalytas.
- Slovėniško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „1000 Ljubljana Slovenska cesta 58“)
  pašto kodas likdavo neišvalytas.
- Lietuviško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „LT-01100 Vilnius Gedimino pr. 9“)
  pašto kodas likdavo visiškai neišvalytas.
- Vengriško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „1052 Budapest Kossuth Lajos utca 12“)
  pašto kodas likdavo neišvalytas.
- Pavardė po „Erben“ (paveldėtojai; pvz., „Die Erben Wagner erhielten
  die Mitteilung fristgerecht.“) beveik visada likdavo neatpažinta
  palikimo/paveldėjimo kontekste.
- Pavardė po „Geschwister“ (broliai ir seserys; pvz., „Die Geschwister
  Bauer wohnen in Linz.“) iki šiol beveik visada likdavo neatpažinta –
  skirtingai nei su „Familie“/„Ehepaar“, tai paveikdavo ne tik su
  profesijos žodžiu sutampančias pavardes (Koch, Bauer, Richter), bet
  bet kokias pavardes šioje vietoje.
- Pavardė po „Ehepaar“ ar „Eheleute“ (sutuoktinių pora; pvz., „Das
  Ehepaar Koch zieht um.“) likdavo neatpažinta, kai ji tuo pačiu metu
  buvo įprastas daiktavardis ar profesijos pavadinimas (Koch, Bauer,
  Richter).
- Įprastas užsakymo, pavedimo ar prekės numeris tipiniame mokesčių
  numerio ar socialinio draudimo numerio grupavimo rastre (pvz., „030
  4471 2298“) be jokio susijusio žymėjimo buvo klaidingai užtemdomas
  kaip toks numeris.
- Dokumento/bylos numeris formatu „metai/eilės numeris“ (pvz., „Rechnung
  Nr. 4/2024/778899“) buvo klaidingai užtemdomas telefono numerio
  atpažinimo kaip telefono numeris.
- Vardas po „Herr“/„Frau“ su daugiažodė akademine titulų grandine prieš
  jį („Herr Dr. med. Weber“, „Herr Prof. Dr. Krause“) iki šiol likdavo
  visiškai neapsaugotas – iki šiol buvo atpažįstamas tik vienas titulo
  žodis tarp kreipinio ir vardo.
- Teismo bylos numeris klasikiniu formatu su rūmų/senato santrumpa
  („4 Ca 1523/24“, „Az.: 7 O 234/25“) iki šiol likdavo visiškai
  neapsaugotas – šalia išrašytos antraštės nebuvo atpažįstama net ir
  įprasta trumpa forma „Az.“/„Gz.“.
- Kredito kortelės numeris, kuris eilutės lūžio buvo perskeltas savo
  keturženklio grupavimo viduryje – pvz., siauroje lentelės skiltyje –,
  iki šiol likdavo visiškai neapsaugotas.
- Mokesčių identifikavimo numeris, kuris eilutės lūžio buvo perskeltas
  savo grupavimo viduryje – pvz., siauroje lentelės skiltyje ar formos
  lauke –, iki šiol likdavo visiškai neapsaugotas.
- Socialinio draudimo numeris, kuris eilutės lūžio buvo perskeltas savo
  grupavimo viduryje – pvz., siauroje lentelės skiltyje –, iki šiol
  likdavo visiškai neapsaugotas, net dalinai nepakeistas.
- Namo numeris su intervalu, toks kaip „12a-14b“ ar „3-5“, buvo
  pakeičiamas tik per pusę – antroji dalis po brūkšnelio likdavo
  atvira rezultate.
- Transporto priemonės identifikavimo numeris (FIN/VIN), kurio 17
  ženklų viduryje buvo perskirti eilutės lūžio, tarpo ar brūkšnelio –
  pvz., siauroje lentelės skiltyje ar transporto priemonės liudijimo
  lauke –, iki šiol likdavo visiškai neapsaugotas.
- Laiško/pašto kreipinys, toks kaip „Liebe Anna!“ ar „Lieber Hans“ – be
  kablelio po vardu, dažniausia forma laisvuose laiškuose – vardą
  palikdavo visiškai neapsaugotą, net pilname dokumente su tekstu ir
  atsisveikinimo fraze po juo.
- Ta pati spraga paveikė ir laisvus pokalbių/pašto kreipinius „Hallo
  Anna!“, „Hi Anna!“, „Hey Anna!“ ir „Servus Anna!“ be kablelio – vardas
  taip pat likdavo visiškai neapsaugotas.
- Grynas parašo blokas, prasidedantis tiesiogiai „MfG“ ar „Herzlichst“
  – pvz., nukopijuotas iš iškarpinės, be prieš tai einančio sakinio –
  po juo palikdavo vardą visiškai neapsaugotą.
- Laukas su keliais asmenimis, pvz., „Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)“, sulydydavo abu vardus kartu su
  skliaustelio nuoroda į vieną, gerokai per ilgą radinį – antrasis
  vardas dalinai likdavo neapsaugotas rezultate.
- Gatvė be „-straße“/„-weg“ priesagos – kaip įprasta kaime, pvz., „Am
  Marktplatz 5“ ar „Im Grund 12“ – likdavo neatpažinta, kai po jos
  ėjo pašto kodo-vietovės eilutė, pvz., gyvenamosios vietos
  pažymėjime: „Neue Anschrift: Am Weidengarten 17, 54295 Trier“
  prarasdavo gatvę visiškai, buvo pašalinamas tik pašto kodas.
- Vardas po sudėtine lauko antrašte su pasviruoju brūkšniu (pvz.,
  „Name/Vorname: Bauer Klaus“) dalinai nebuvo atpažįstamas –
  daugiareikšmė pavardė, tokia kaip „Bauer“, be lauko įrodymo likdavo
  neaptikta. Ta pati spraga paveikė sudėtinius laukus, tokius kaip
  „PLZ/Ort: 04109 / Leipzig“. Tas pats galiojo sudėtiniams laukams su
  išrašytu jungtuku vietoj pasvirojo brūkšnio, pvz., „Vor- und
  Nachname: Bauer Klaus“ ar „Nachname bzw. Vorname: …“.
- Gimimo data forma „Datum der Geburt: …“ ir mirties data forma
  „Todesdatum: …“ arba „Datum des Todes: …“ nebuvo atpažįstamos – veikė
  tik „Geburtsdatum: …“ ir „Sterbedatum: …“.
- Santuokos data forma „Datum der Heirat: …“ arba „Datum der Hochzeit:
  …“ nebuvo atpažįstama – veikė tik „Hochzeitsdatum: …“,
  „Heiratsdatum: …“ ir „Datum der Eheschließung: …“, nors skyrybų,
  natūralizacijos ir partnerystės datos jau seniai turėjo tą pačią
  „Datum der X“ formą.
- Skyrybų data forma „Datum der Scheidung: …“ nebuvo atpažįstama –
  veikė tik „Scheidungsdatum: …“ ir sekamoji veiksmažodžio forma, nors
  natūralizacijos ir partnerystės data jau nuo pat pradžių turėjo tą
  pačią „Datum der X“ formą.
- Partnerystės data iki šiol visai nebuvo atpažįstama – nei su antrašte
  („Verpartnerungsdatum: …“, „Datum der Lebenspartnerschaft: …“), nei
  tekste („… wurden am … verpartnert“). Dabar ji, kaip gimimo,
  santuokos, skyrybų ir natūralizacijos data, pakeičiama kaip savarankiška
  duomenų rūšis.
- Natūralizacijos data iki šiol visai nebuvo atpažįstama – nei su
  antrašte („Einbürgerungsdatum: …“), nei tekste („… wurde am …
  eingebürgert“). Dabar ji, kaip gimimo, santuokos ir skyrybų data,
  pakeičiama kaip savarankiška duomenų rūšis.
- Skyrybų data iki šiol visai nebuvo atpažįstama – nei su antrašte
  („Scheidungsdatum: …“), nei tekste („Die Ehe wurde am … geschieden“).
  Dabar ji, kaip gimimo, mirties ir santuokos data, pakeičiama kaip
  savarankiška duomenų rūšis.
- Santuokos data po genealoginiu vestuvių ženklu „⚭“ be antraštės
  nebuvo atpažįstama, nors gimimo ir mirties data toje pačioje eilutėje
  su žvaigždute ir kryžiumi jau buvo atpažįstamos – dabar atpažįstama
  ir santuokos data.
- Mirties data po nekrologo kryžiumi be antraštės („*03.06.1940
  †21.11.2023“) nebuvo atpažįstama, nors gimimo data prieš ją su
  genealogine žvaigždute jau buvo atpažįstama – dabar atpažįstama ir
  mirties data.
- Pavardė prieš vardą tikslo/bilieto eilutės pabaigoje su prieš tai
  einančiu dalykiniu tekstu ir skiriamuoju brūkšneliu („Betreff:
  Reklamation - Bauer, Anna“) su profesija sutampančios pavardės atveju
  nebuvo atpažįstama – dabar ji atpažįstama.
- Pareiškėjo ir prašymo teikėjo numeriai po jų antrašte („Bewerbernummer:
  4471829“, „Antragstellernummer: 7654321“) visiškai nebuvo
  atpažįstami – dabar jie atpažįstami.
- Keitimas nebeuztemdomas, kai nėra vietos įskaitomam vietos žymekliui –
  per mažas vietos žymeklis dabar rašomas mažesniu šriftu vietoj to,
  kad taptų tuščia juosta, kol tik apskritai lieka vietos. Be to, naujai:
  ar radinys vaizde (laiško antraštė, nuskaitymo fonas) žymimas ar tik
  uztemdomas, dabar galima nustatyti nepriklausomai nuo likusios
  rezultato rūšies. Ir radinys vaizde, kuris visiškai pašalinamas, buvo
  žymimas taip, tarsi vaizdas liktų – vietos žymeklis stovėjo šviesus
  ant fono, kuris niekada nebuvo uztemdytas, ir taip nematomai
  dingdavo dabar baltame popieriuje.
- Radinys **išsaugotame** vaizde keičiant visada buvo uztemdomas
  juodai-baltai, nepriklausomai nuo pasirinkto pateikimo (kategorijų
  spalvos, vaivorykštė…) – matoma kaip lūžis tarp spalvingų etikečių
  tekste ir juodų juostų ant laiško antraštės. Vaizdo fonas dabar seka
  tą pačią spalvą kaip šalia esantis vietos žymeklis.
- Transporto priemonės identifikavimo numerio (FIN/VIN) atpažinimas
  besąlygiškai žymėjo kiekvieną 17 ženklų alfaskaitinį kodą be I/O/Q
  kaip važiuoklės numerį – taip pat užsakymo, serijos ir licencijos
  raktų numerius, kurie atsitiktinai turi tą pačią formą. Dabar jis
  skaičiuoja tik su kontekstiniu žodžiu netoliese („FIN“, „VIN“,
  „Fahrgestell“, „Chassis“ ir pan.).
- Bilietų/kalendorių sistemose vardo atpažinimas po „Assigned to“/
  „Closed by“ ir pan. nusinešdavo sekantį lauko žodį, jei jis toje
  pačioje eilutėje sekė iš karto be skirtuko („Assigned to Max
  Mustermann Priority High“ tapo „Max Mustermann Priority“). Git
  commit antraštėse vardo atpažinimas taip pat nusinešdavo **sekantį**
  žymens raktą, jei dvi eilutės buvo sujungtos vien tarpu vietoj
  eilutės lūžio („Author: julia bergmann Reviewed-by: …“ tapo „julia
  bergmann Reviewed-by“). Abi apsaugos papildytos.
- Vardas po „p.A.“, „zH“/„zHd“, „i.A.“/„i.V.“ ir „geb.“ nusinešdavo
  tiesiogiai sekantį skyriaus žodį į tą patį radinį, jei jis be
  skirtuko stovėjo toje pačioje eilutėje („p.A. Max Mustermann
  Buchhaltung“ tapo „Max Mustermann Buchhaltung“, „i.A.Max Mustermann
  Vertrieb“ tapo „Max Mustermann Vertrieb“). Ta pati apsauga, kaip su
  „Assigned to“/Git žymenimis, dabar papildyta ir čia.
- Pažymėta IBAN tiesiai virš BIC, BLZ ar SWIFT eilutės nusinešdavo jos
  antraštę į savo radinį, nes „BIC“ ir „BLZ“ patys atrodė kaip dar
  vienas numerių blokas – iš „IBAN: DE89 … 0130 00“ ir eilutės po ja
  susidarydavo vienas, per plačiai siekiantis radinys, ir sekančios
  eilutės antraštė kartu dingdavo valymo metu. Tai paveikdavo beveik
  kiekvieną banko sąskaitą su IBAN ir BIC viena po kita.
- Radinių skydelis dabar sako, **kur** yra vietos žymeklis, kurio jis
  puslapyje neranda. Du atvejai iki šiol pranešdavo tik „nerasta“, nors
  pakeitimas įvyko: jei vietos žymeklis yra nematomame šalutiniame
  tekste – pvz., nuorodos adrese, pastaboje ar formos lauke –, eilutė
  dabar tai nurodo kaip atskirą informaciją („šalutiniame tekste“), ir
  paspaudimas tai paaiškina. Ir jei vietos žymeklis dėl vietos stokos
  buvo sutrumpintas („[N382]“ vietoj „[NAM382]“), paspaudimas ant ilgos
  eilutės dabar peršoka prie trumposios formos vietos ir nurodo
  pervardijimą; sąsaja specialiai susieja abi eilutes tarpusavyje.
- Jei tas pats pakeitimo tekstas dokumente stovi kelis kartus, kiekvienas
  tolesnis paspaudimas ant skydelio eilutės peršoka ratu prie sekančios
  radimo vietos – net per puslapio ribas; būsenos eilutė skaičiuoja
  („Radimo vieta 2 iš 4“), o dabar pasiekta vieta apvedama sodresniu
  rėmeliu nei kitos. Ir jei vietos žymeklis stovi tik radinių sąraše,
  bet niekur dokumente (nes vieta buvo įtraukta į persidengiantį
  pakeitimą), būsenos eilutė dabar tai sako, vietoj to, kad paspaudimas
  liktų tyliai be pasekmių.
- Sutrumpintas vardas po „an“ ar „für“ dabar patikimai atpažįstamas
  kaip vardas – „Überweisung an M. Wagner“ ir „Rechnung für M. Wagner“
  iki šiol dažnai likdavo neišvalyti, nors tas pats vardas su kita
  antrašte prieš jį (pvz., „Zahlungsempfänger:“) jau buvo aptinkamas.
  Tai daugiausia paveikė sąskaitos išrašo ir apskaitos eilutes.
- „Angeklagter“/„Angeklagte“/„Beschuldigter“/„Beschuldigte“ dabar
  laikomi vardo lauku: jei baudžiamosios bylos dokumentuose vardas
  stovėjo tiesiai po viena iš šių antraščių, iki šiol jis maždaug pusei
  patikrintų vardų visai nebūdavo atpažįstamas – nei vardas, nei
  pavardė.
- Radinių skydelio paspausta vieta dabar apvedama mėlynai, o ne žymima
  geltonai – ant spalvotų šviesoforo paviršių paieškos radinio geltona
  spalva nebuvo įžvelgiama. Be to, paspaudimas dabar randa ir daugiažodžius
  pakeitimo tekstus (sugalvotus vardus, kaukuotus numerius): iki šiol
  jis būdavo bejėgis tokiose eilutėse, nes radimo vieta buvo ieškoma
  tik žodis po žodžio.
- Įtėviai, globėjai ir podukra/posūnio tėvai („Adoptivvater“,
  „Pflegemutter“, „Stiefvater“ ir kiti) dabar atpažįstami kaip vardo
  laukas, anksčiau vardas likdavo neišvalytas
- Skaičiais gausios lentelės ir sąrašai daugiau nebemetami klaidingai:
  jei buvo pakeistas trumpas skaičius (pvz., kaip telefono numeris
  perskaityta kliento numerio dalis), galutinė patikra tą pačią skaitmenų
  seką pranešdavo kaip likusią reikšmę net ir tada, kai ji kitur
  atsitiktinai buvo įsipynusi visai kitame numeryje – ir tada nebuvo
  gaunamas joks rezultatas. Skaičius dabar skaičiuojamas kaip likutis
  tik ten, kur jis stovi kaip savarankiškas skaičius.
- Civilinės būklės liudijimai: „Vater:“/„Mutter:“ dabar atpažįstami
  kaip vardo laukas, anksčiau tėvo/motinos vardas likdavo neišvalytas
- Kiti šeimos vaidmenys („Pate“, „Großvater/-mutter“, „Ehepartner“,
  „Lebenspartner“, „Onkel“, „Tante“) dabar atpažįstami kaip vardo
  laukas, anksčiau vardas likdavo neišvalytas
- Vokiškas banko kodas dabar atpažįstamas ir oficialiai sugrupuotas
  („370 400 44“, „370.400.44“, „370-400-44“, „370/400/44“), o ne tik
  kaip aštuoni sujungti skaitmenys.
- Vokiškas pensijų draudimo numeris dabar atpažįstamas ir su tašku,
  brūkšneliu ar pasviruoju brūkšniu tarp penkių blokų („65-170839-J-08-8“,
  „65.170839.J.08.8“), o ne tik su tarpais.
- Pagrindinis langas atsiveria greičiau: atpažinimo bibliotekos
  (Presidio kartu su kalbos modelio pagrindu) iki šiol jau buvo kraunamos
  lango kūrimo metu – Windows sistemoje tai maždaug keturios sekundės
  laukimo, kol dar nieko nesimatė. Dabar jos pilnai kraunamos fone;
  mygtukas „Valyti“ kaip anksčiau taps prieinamas tik tada, kai viskas
  paruošta.
- Office dokumentai su daug vaizdų ar vaizdo įrašų dabar rašomi
  greičiau: jau suglaudinta medija rezultato pakete saugoma tokia,
  kokia yra, o ne beprasmiškai antrą kartą suglaudinama – tai iki šiol
  nesutaupydavo nė bito ir dažniau padidindavo JPEG failus.
- Skaičiuoklės ir kiti dokumentai iš daugelio mažų teksto vienetų
  tikrinami greičiau: kalbos atpažinimas dabar apdoroja visus dokumento
  langelius ir pastraipas per vieną praėjimą vietoj po vieną – esant
  akivaizdžiai tiems patiems radiniams (400 langelių: nuo maždaug 4,7
  iki 2,5–3,5 sekundžių).
- Sąrašo tipo PDF puslapiai (rodyklės, pozicijų sąrašai) vietos žymeklių
  įterpimo metu žymiai greitesni: vietos paieška kiekvienai antraštei
  iki šiol vyko per visus puslapio žodžius – dabar tik per eilutės
  aplinką, esant akivaizdžiai tam pačiam rezultatui (puslapyje su 300
  antraščių maždaug šešiolika kartų greičiau).
- Vaizdais gausūs dokumentai sutaupo kelis nereikalingus darbo žingsnius
  kiekvienam vaizdui: veidų ir kodų skaičiavimas PDF puslapiuose
  nebeiškoduoja puslapio vaizdo du kartus, metaduomenų tikrinimas
  visai nebeiškoduoja švaraus vaizdo, supikseliuoti vaizdai rašomi su
  normalia, o ne lėčiausia PNG glaudinimo pakopa (tas pats dydis,
  trečdalis laiko), o be nustatyto vandenženklio nebelieka beprasmiško
  visos PDF failo perrašymo pabaigoje.
- Nuskaityti PDF failai su įjungta teksto atpažinimu dabar žymiai
  greičiau apdorojami: kiekvienas puslapis iki šiol buvo pilna raiška
  atvaizduojamas du kartus (vieną kartą skaitymui, vieną kartą
  rastravimui) – dabar atvaizdas pakartotinai naudojamas. Ir Windows/
  Linux sistemose teksto atpažinimas skaito didelio nuskaitymo juostas
  vienu ėjimu vietoj savarankiško programos paleidimo kiekvienai
  juostai.
- Dideli dokumentai valomi žymiai greičiau: jau rastų reikšmių
  palyginimas iki šiol augo su radimo vietų skaičiumi (64 KB teksto
  blokas didelio failo pabaigoje kainavo apie sekundę vien dėl to,
  dabar šešiasdešimtąją dalį), o įmonių teisinių formų paieška vyko su
  visomis ~280 katalogo formomis per kiekvieną teksto vietą (dabar
  maždaug dvidešimt kartų greičiau, esant akivaizdžiai tiems patiems
  radiniams).
- Vardas tiesiai po „Beste Grüße“/„Beste Wünsche“ be prieš tai einančio
  teksto ar skyrybos ženklo visai nebuvo atpažįstamas – grynas parašo
  blokas be teksto prieš jį leisdavo vardui dingti be pėdsako.
- Adreso laukas dokumento pradžioje su su profesija sutampančia pavarde
  („Bauer Anna“, „Koch Stefan“ kaip pirma eilutė virš gatvės ir
  vietovės) iki šiol likdavo dalinai neatpažintas arba buvo priskiriamas
  vietovei, o ne asmeniui – be prieš tai einančio sakinio kalbos modelis
  neturėjo sakinio struktūros, kuri kitaip leistų atpažinti „Bauer“ kaip
  vardą, o ne profesiją.
- Vardas po parašo žyma „gez.“ su profesija sutampančia pavarde prieš
  vardą („gez. Bauer Anna“ sprendimo ar nuosprendžio pabaigoje) iki
  šiol likdavo nepilnai atpažintas – buvo rastas tik vardas, pavardė
  dingdavo be pėdsako.
- Vardas tiesiai po kliento numeriu, sutarties numeriu ar panašiu
  identifikavimo numeriu be atskiros eilutės („Vertragsnummer 55219
  Bauer Anna“, „Kundennr. 4711 Bauer Anna“) iki šiol su profesija
  sutampančia pavarde likdavo dalinai ar visai neatpažintas.
- macOS meniu juostos simbolis dabar yra šablonas, kuris kaip ir
  gretimi simboliai prisitaiko prie šviesaus ir tamsaus režimo – su
  dviem iškirstomis juostomis jis kaip Maskuro lieka atpažįstamas.
  Kai veikia iškarpinės sekimas, tai rodo atskirtas taškas skydo
  viršūnėje.
- Paspaudimas radinių skydelyje dabar veikia ir anonimizuojant: puslapio
  keitimas, ritinimas iki vaizdo, geltonas pažymėjimas. Iki šiol
  paspaudimas ten likdavo bereikšmis, nes vietos žymekliai buvo
  laikomi neturinčiais numerio – nuo tada, kai kiekviena radimo vieta
  turi savo numerį, vieta yra vienareikšmė. Tik tikrai numerio
  neturinčio vietos žymeklio atveju būsenos eilutė toliau paaiškina,
  kodėl šuolio tikslo nustatyti negalima.
- Pirmasis išsaugojimas taisymo redaktoriuje (Ctrl+S arba diskelio
  mygtukas) dabar klausia vietos, kaip „Išsaugoti kaip …“ – iš anksto
  nustatyta originalo aplanke su rezultato pavadinimu. Iki šiol failas
  be žodžio atsidurdavo šalia originalo. Kas jau anksčiau pasirinko
  saugojimo vietą per būsenos eilutę, antrą kartą nebeklausiamas;
  kiekvienas tolesnis išsaugojimas kaip anksčiau perrašo tą patį failą.
- Kai saugumo patikra prieš išsaugojimą praneša įtartiną vietą, „Grįžti
  į patikrą“ dabar veda ten: pirmoji radimo vieta įritinama į vaizdą ir
  apvedama raudonai, būsenos eilutė ją nurodo. Iki šiol likdavai vienas
  su puslapio numeriu ir taškų koordinatėmis. Iš pagrindinio lango
  dėl to atsidaro redaktorius toje vietoje. Taip pat ir gavus įspėjimą
  apie skirtingą puslapių skaičių mygtukas dabar veda ten – į pirmą
  puslapį, kuris yra tik viename iš dviejų dokumentų.
- Kas peržiūrą perjungia į „Greta viena kitos dviejose skiltyse“, dabar
  savaime gauna langą, į kurį telpa abi juostos – iki šiol jos
  spraudėsi į seną plotį, kol nebūdavo pačiam patempiama. Praplečiama
  ne daugiau nei iki ekrano krašto ir niekada vėl nesusiaurinama; pačiam
  ištrauktas plotis lieka toks pat.
- Pavardė ir vardas atskirose lentelės skiltyse (pvz., „Nachname |
  Vorname“ registracijos patvirtinime ar CSV eksporte) likdavo atviri –
  kiekvienas langelis pats savaime atpažinimui atrodydavo kaip bet koks
  žodis be jokio ryšio su vardu. Dabar atpažįstami.
- Vardas ir pavardė ES vairuotojo pažymėjimo kortelės antroje pusėje
  likdavo atviri – jie ten stovi po oficialiais lauko kodais „1.“ ir
  „2.“, o ne po vokišku žodžiu, ir būtent tai leisdavo jiems likti
  neatpažintiems. Dabar atpažįstami, jei šalia stovi vairuotojo
  pažymėjimo numeris (lauko kodas „5.“).
- Transporto priemonės valdytojo vardas registracijos liudijime
  likdavo atviras – jis stovi po oficialiu lauko kodu „C.1.2“, o ne
  po vokišku žodžiu, tokiu kaip „Vorname“, ir būtent tai leisdavo jam
  likti neatpažintam. Pavardė ir vardas po lauko kodais C.1, C.1.1 ir
  C.1.2 dabar atpažįstami.
- Pirma paso ar asmens tapatybės kortelės mašininio skaitymo zonos
  (MRZ) eilutė likdavo atvira – ji neša vardą formatu
  „PAVARDĖ<<VARDAS“ ir nepasiekiama liko net ir naujam MRZ
  atpažintuvui kontrolinio skaitmens eilutei. Radinys dabar skaičiuojamas
  tik tada, kai šalia iš karto stovi kontrolinio skaitmens požiūriu
  galiojanti antroji MRZ eilutė – pati vardo eilutė savo paties
  kontrolinio skaitmens neturi.
- Antra paso ar asmens tapatybės kortelės mašininio skaitymo zonos
  (MRZ) eilutė likdavo visiškai neatpažinta – ji aiškiame tekste
  turi paso numerį, gimimo ir galiojimo pabaigos datą, tačiau
  neatitiko nė vieno esamo atpažintuvo. Savas atpažintuvas dabar
  patikrina keturis ICAO kontrolinius skaitmenis.
- Transporto priemonės numeris be jokio tarpo iki žymėjimo likdavo
  atviras – „KennzeichenM-AB1234“ ar „KFZ-KennzeichenM-AB1234“ visai
  nebuvo atpažįstami, nes pagrindinė numerio patikra prieš numerį
  reikalauja ne-žodinio ženklo. Paveikė transporto priemonės duomenis,
  kuriuose tarp lauko žodžio ir numerio nebuvo tarpo.
- Telefono numeris be jokio tarpo iki žymėjimo likdavo atviras –
  „Handynummer0171/2345678“ ar „Tel0171/2345678“ visai nebuvo
  atpažįstami, nes pagrindinė numerio patikra prieš numerį reikalauja
  tarpo ar skyrybos ženklo. Paveikė kontaktinius duomenis, kuriuose tarp
  lauko žodžio ir numerio nebuvo tarpo.
- Mergautinė pavardė po santrumpa „geb.“ visai nebuvo atpažįstama –
  „Julia Bergmann (geb. Weber)“ rasdavo tik „Julia Bergmann“, taškas
  santrumpoje „geb.“ leisdavo kalbos modeliui visiškai praleisti
  sekantį vardą. Paveikė asmens duomenis su mergautine pavarde
  skliaustuose arba po kablelio.
- Vardas prieš slapyvardį kabutėse likdavo atviras, kai kreipinys ir
  titulas stovėjo kartu prieš jį – „Herr Dr. Klaus "KP" Peters“ davė
  tik „Peters“, „Klaus“ likdavo įskaitomas. Paveikė parašus ir
  kontaktinius duomenis su titulu ir slapyvardžiu.
- Vardas po be taško trumpąja forma „zH“/„zHd“ (dėmesiui) visai nebuvo
  atpažįstamas – priešingai nei su „z.Hd.“ su tašku, trūkstama sakinio
  struktūra nusinešdavo vardą kartu. Paveikė adresus be taško santrumpoje.
- Vardas po „p.A.“ (per adresą) visai nebuvo atpažįstamas – taškas
  santrumpoje leisdavo kalbos modeliui visiškai praleisti vardo
  atpažinimą. Paveikė sąskaitas ir kandidatūras su bendru adresu.
- Vardas po be taško prilipdyta „i.A.“/„i.V.“ (pavedimu/atstovaujant)
  visai nebuvo atpažįstamas, pvz., „i.A.Robert Lang“ be tarpo – ta pati
  sakinio struktūros klaida, kaip ir su „p.A.“. Paveikė parašo eilutes
  ir el. laiškų parašus atstovavimo atvejais.
- Gryna dalyvių sąrašas su ženkleliais, be jokio kito duomens („- Max
  Mustermann“, taip pat su tašku eilutės gale), prarasdavo visus
  vardus dėl tos pačios apsaugos, kuri iš tikrųjų turėtų saugoti tik
  dalykinius sąrašus, tokius kaip „- Farbe: Blau“. Tokie sąrašai dabar
  atpažįstami.
- Failai, kurių nebebuvo galima valyti, dabar vėl gali būti valomi.
  Reikšmė, kuri jau buvo pakeista atpažinimo metu, galėjo būti rasta ir
  savo pačios jau pakeistoje žymoje, tokioje kaip „[SVNR1]“ – galutinis
  patikrinimas tada atmesdavo nepriekaištingai išvalytą failą. Be to,
  telefono nuoroda CSV lentelėje dabar taip pat pašalinama, o kas
  paiešką apriboja atskiromis rūšimis, dabar gauna ją visur dokumente
  vienodai – ir vaizdo alternatyviame tekste, Excel antraštėje,
  pasirinkimo sąraše ar HTML atribute.
- Vardas po el. pašto antrašte „To:“ (arba „To“ be dvitaškio) nebuvo
  atpažįstamas, nes svetimas kalbos modelis skaitydavo visą eilutę kaip
  vieną nepastebimą radinį ir visiškai praryja jame esantį vardą –
  skirtingai nei su „Cc:“, „Bcc:“ ar „From:“ prieš tą patį vardą.
  Vardas po „To“ dabar patikimai randamas.
- Vestuvių datos savose taisyklėse nebuvo galima traktuoti kaip datos
  (jungiklis „perkelti“ buvo atmestas su „yra tik datoms“), jos trūko
  radimo rūšių grupavime – dėl ko jos negalima buvo išjungti per žymas
  „Kas ieškoma“ – ir vietoj trumpo santrumpos, kaip mirties datos
  atveju, ji gaudavo pilną žodinę formą kaip vietos žymeklį. Ištaisyta
  visose šešiose santrumpų/žymėjimo lentelėse.
- Peržiūroje sąmoningai neatžymėta reikšmė vis tiek galėjo būti
  užtemdyta kitoje vietoje: jei, pvz., buvo atžymėtas el. pašto adresas,
  pats adresas likdavo stovintis, bet jo vietinė dalis be domeno buvo
  pakeičiama, kai tik ji sutapdavo su kito, papildomai pasirinkto
  asmens išvestu vartotojo vardu („anna.musterfrau@beispiel.de“ šalia
  „Anna Musterfrau“). Atžymėtas žodinis turinys dabar lieka draudžiamas
  visame dokumente, nepriklausomai nuo to, iš kurios radimo rūšies jis
  kilęs.
- Gimimo data likdavo neatpažinta, kai šeimos knygos ar civilinės
  būklės išraše ji buvo pateikta su bendra antrašte kartu su gimimo
  vieta („Geburtsdatum, Geburtsort: 19.11.1982, Steyr“) – antras lauko
  žodis tarp „Geburtsdatum“ ir datos iki šiol leisdavo atpažinimui
  visiškai nesuveikti.
- Jau atpažintas telefono numeris likdavo įskaitomas savo sutrumpinta
  patvirtinimo forma, jei kitoje to paties dokumento vietoje jis buvo
  minimas tik su paskutiniais keturiais skaitmenimis („erreichbar unter
  der Nummer ...5678“, „Rückruf unter ...5678“) – ta pati forma, kaip
  su IBAN ir kredito kortele.
- Jau atpažintas kredito kortelės numeris likdavo įskaitomas savo
  sutrumpinta patvirtinimo forma, jei kitoje to paties dokumento vietoje
  jis buvo minimas tik su paskutiniais keturiais skaitmenimis („Ihre
  Kreditkarte endet auf ...0366“) – ta pati mokėjimo patvirtinimuose
  įprasta forma, kaip su IBAN.
- Jau atpažinta IBAN likdavo įskaitoma savo sutrumpinta patvirtinimo
  forma, jei kitoje to paties dokumento vietoje ji buvo minima tik su
  paskutiniais keturiais skaitmenimis („Die IBAN endet auf ...3201“) –
  patvirtinimo el. laiškuose įprasta forma.
- Kalbėtojas pokalbio ar posėdžio protokole likdavo neatpažintas, kai
  prieš jo vardą stovėjo kreipinys („Herr Bauer: …“, „Frau Koch: …“) –
  ir dažnai paveikdavo taip pat ir sekančią kalbėtojo eilutę tame pačiame
  protokole, nes likdavo per mažai atpažintų eilučių, kad dokumentas
  apskritai būtų vertinamas kaip protokolas.
- Gimimo data likdavo neatpažinta, kai lauko žodis „geboren“ stovėjo
  UŽ datos, o ne prieš ją („Das Kind wurde am 14.01.2026 geboren“) –
  taip vaiko gimimo datą formuluoja, pvz., vaiko priežiūros atostogų ar
  motinystės apsaugos pažymėjimas. Iki šiol modeliai visada laikė, kad
  lauko žodis eina prieš datą.
- Formos antraštė su reakcijos ar varnelės ženklu tiesiai prieš ją
  („Ansprechpartner 😊:“, „Kontaktperson ✓:“) nebebuvo atpažįstama kaip
  antraštė, ir dėl to po ja ar už jos esantis vardas dalinai likdavo
  atpažintas (pvz., tik pavardė su „Mayer Roman“).
- Ta pati spraga paveikė ir ypač saugotinus duomenis pagal DSGVO
  9 str. (religija, sveikata, profsąjunga): reakcijos ženklas tiesiai
  prieš skirtuką ar eilutės lūžį („Konfession 😊: römisch-katholisch“)
  leisdavo antraštei visai nesuveikti, ir duomenys likdavo visiškai
  neatpažinti.
- Adresas su brūkšneliu sudarytu dvigubu vietovės pavadinimu (pvz.,
  „79761 Waldshut-Tiengen“, „78050 Villingen-Schwenningen“) visiškai
  prarasdavo pašto kodą, nors pati vietovė buvo atpažįstama ir
  užtemdoma – transporto priemonės dokumente ar rašte pašto kodas taip
  likdavo įskaitomas.
- Lentelės skiltis be tarpo tarp skilčių (tikras PDF teksto ištraukos
  atvejis) po vardo skiltimi galėjo klaidingai užtemdyti kaip asmenį
  net du atsitiktinai greta stovinčius didžiąja raide rašomus žodžius,
  pvz., dvi vietoves toje pačioje duomenų eilutėje; dabar tai vyksta
  tik tada, kai toje pačioje vietoje jokia kita radimo forma jau
  neatpažįsta kažko kito.
- Ta pati vardų skiltis toje pačioje eilutės formoje klaidingai
  užtemdydavo kaip asmenį ir du kalbos modeliui nežinomus dalykinius
  žodžius (pvz., „Frontend Backend“, „Turbo Modul“), nes ten jokia
  kita radimo forma neįjungdavo apsaugos; dabar ji papildomai
  reikalauja, kad bent vienas iš dviejų žodžių pats kalbos modelio
  būtų skaitomas kaip tikrinis vardas.
- Vokiškas pensijų draudimo numeris jo oficialiu pilnu grupavimu
  (pvz., „65 170839 J 08 8“ – toks, koks jis nurodytas socialinio
  draudimo pažymėjime ir atlyginimo lapelyje) nebuvo atpažįstamas ir
  likdavo originalo tekste; buvo atpažįstama tik kompaktiška rašyba ir
  tik iki raidės sugrupuota forma.
- Mokesčių identifikavimo numeris jo oficialia rašyba (grupavimas
  2-3-3-3, pvz., „48 836 075 988“ – toks, koks jis nurodytas
  kiekviename tikrame mokesčio pranešime ir kiekviename Federalinio
  mokesčių centrinio biuro pranešime) visai nebuvo atpažįstamas ir
  likdavo originalo tekste; buvo apimtas tik rečiau naudojamas
  grupavimas 3-3-3-2.
- Šiaurės Reino-Vestfalijos mokesčių numeris (pvz., „221/5147/0815“, su
  keturženkle vietoj trijų ženklų antra grupe) mokesčių pranešimuose
  visai nebuvo atpažįstamas ir likdavo originalo tekste – kiekviena
  kita federalinė žemė jau buvo apimta.
- Darbo sutartyse vardas po antrašte „Arbeitgeber:“ visiškai
  nepastebimai praleidžiamas, kai tik pavardė tuo pačiu metu yra
  paprastas žodis (pvz., „Bauer Anna“) – „Arbeitgeber“ sąraše stovi ir
  kaip vardo, ir kaip įmonės antraštė, ir įmonės priskyrimas
  perrašydavo vardo priskyrimą.
- Nuomos sutarties antraštėje su antraštėmis „Vermieter:“/„Mieter:“
  pavardė, kuri tuo pačiu metu yra paprastas žodis (pvz., „Bauer“),
  buvo praleidžiama – atpažįstamas likdavo tik vardas. Numeruotos
  nuomos šalys („Mieter 1:“, „Mieter 2:“) papildomai buvo paveiktos,
  net su vardais be šio daugiareikšmiškumo.
- Teismo protokole su antraštėmis „Zeuge:“/„Kläger:“/„Beklagter:“
  (taip pat su numeravimu, „Zeuge 1:“, „Zeuge 2:“) pavardė, kuri tuo
  pačiu metu yra paprastas žodis (pvz., „Bauer“), taip pat buvo
  praleidžiama – atpažįstamas likdavo tik vardas.
- Paveldėjimo pažymėjime, įgaliojime, priminimo procese ir pirkimo
  sutartyje pavardė, kuri tuo pačiu metu yra paprastas žodis (pvz.,
  „Bauer“), buvo praleidžiama po antraštėmis „Erblasser:“, „Erbe:“,
  „Vollmachtgeber:“, „Bevollmächtigte:r“, „Antragsgegner:“,
  „Schuldner:“, „Gläubiger:“, „Käufer:“, „Verkäufer:“,
  „Vermächtnisnehmer:“ ar „Testamentsvollstrecker:“ – kartais
  atpažįstamas likdavo tik vardas, kartais dingdavo visas vardas.
- Kelių šalių sąraše prieš rubrumo skirtuką „./.“ (pvz., „Sand, Werner
  und Huber, Anna ./. Wechsler, Martina“) pirmoji šalis likdavo
  nekaukuota – atpažįstama buvo tik šalis, tiesiogiai besiribojanti su
  „./.“.
- Rubrumo skirtuke „./.“ (pvz., „Sand./.Wechsler“) vardas po ženklo
  visiškai nepastebimai praleidžiamas, kai ten nebūdavo tarpo – veikė
  tik su tarpu prieš ir po.
- Pavardė „Wahr“ visiškai nepastebimai praleidžiama, kai stovėdavo
  viena (pvz., „Frau Wahr bearbeitet Ihren Vorgang.“) – šis žodis
  atsitiktinai taip pat yra įprastų vokiškų žodžių sąraše, kuris kitaip
  filtruoja vardų radinius iš sakinių, tokių kaip „Das ist wahr.“
- Pavardės, tokios kaip „Los“, „Weit“, „Rund“ ar „Hoch“, visiškai
  nepastebimai praleidžiamos, kai jos stovėdavo vienos (pvz., „Herr
  Hoch übernahm die Leitung.“) – visi keturi žodžiai atsitiktinai taip
  pat yra įprastų vokiškų žodžių sąraše, kuris kitaip filtruoja vardų
  radinius iš sakinių, tokių kaip „Rund einhundert Gäste kamen zur
  Feier.“
- Pavardės, tokios kaip „Ganz“ ar „Recht“, visiškai nepastebimai
  praleidžiamos, kai jos stovėdavo vienos (pvz., „Herr Ganz unterschrieb
  den Vertrag.“) – abu žodžiai atsitiktinai taip pat yra įprastų
  vokiškų žodžių sąraše, kuris kitaip filtruoja vardų radinius iš
  sakinių, tokių kaip „Ganz genau, das stimmt.“
- Formos laukas su žvaigždute ar viršutine išnašos skaitmeniu po
  antrašte (pvz., „Konfession*: römisch-katholisch“ arba
  „Religionszugehörigkeit¹: evangelisch“) nebuvo atpažįstamas ir
  likdavo aiškiame tekste – veikė tik forma be šio ženklo.
- Tas pats laukas toliau likdavo aiškiame tekste, kai po antrašte
  stovėjo net du išnašos ženklai (pvz., „Konfession**: römisch-
  katholisch“ arba „Gewerkschaft¹²: ver.di“).
- Versijos numeris, toks kaip „Softwareversion 4.2.1.19“ ar „Firmware
  Build 2.0.4.11“, daugiau nebeuztemdomas klaidingai kaip IP adresas.
  Tas pats dabar galioja dokumento ir bylos numeriams, tokiems kaip
  „Rechnungsnummer 10.20.30.40“ ar „Bestellnummer 7.8.9.10“.
- Dvi IBAN tiesiai viena po kitos (pvz., savo ir užsienio verslo
  partnerio sąskaitos antraštėje) abi nebebuvo atpažįstamos vienodai –
  antroji likdavo nepastebėta.
- Pažymėta IBAN kartais nusinešdavo sekantį žodį sakinyje
  („Bankverbindung AT61 … wird belastet“ buvo uztemdoma iki žodžio
  „wird“ imtinai), kai tik sekantis žodis buvo rašomas mažąja raide –
  aiškaus teksto liekana šalia likdavo nepaliesta.
- Lichtenšteino adresai dabar atpažįstami („FL-9490 Vaduz“), taip pat
  kaip iki šiol vokiški, austriški ir šveicariški.
- Paso ir kelionės dokumento numeris dabar atpažįstamas ir pašalinamas
  po jo antrašte (pvz., „Reisepassnummer: C01X00T471“).
- Leidimo gyventi ir gyvenamosios vietos deklaravimo pažymėjimo numeris
  dabar atpažįstamas ir pašalinamas po jo antrašte.
- Identifikavimo numeris po jo antrašte dabar atpažįstamas ir tada,
  kai vietoj dvitaškio skiria brūkšnys (pvz., „Kundennummer – K903944“).
- Kaip „IBAN“ ar „Kontonummer“ pažymėta banko sąskaita dabar
  atpažįstama ir tada, kai vietoj dvitaškio skiria brūkšnys.
- Vardas po antrašte, tokia kaip „Kontaktperson (Vertrieb)“ ar
  „Sachbearbeiter/in“, dabar atpažįstamas ir su skliaustelio priedu ar
  lyčiai neutraliu pasvirojo brūkšnio priesagos variantu.
- Ta pati žvaigždutės lyčiai neutrali forma („Sachbearbeiter*in“) dabar
  taip pat atpažįstama.
- Vardas po antrašte dabar atpažįstamas ir tada, kai vietoj dvitaškio
  skiria lygybės ženklas (pvz., „Ansprechpartner = Mayer Roman“ ar
  „Kontaktperson=Mayer Roman“), kaip įprasta konfigūracijos failuose ar
  CSV antraštėse. Jei kelios tokios antraštės-reikšmės poros eilutėje
  atskirtos kabliataškiu, atpažįstama tik pirmoji reikšmė, o ne visa
  likusi eilutė.
- GPS koordinačių pora po žodžio „Koordinaten“ dabar patikimai
  atpažįstama (pvz., „Koordinaten: 48.2082, 16.3738“) – žodis vidiniame
  kataloge turėjo netinkamą linksnio formą.
- Identifikavimo numeris po jo antrašte (kliento numeris, sutarties
  numeris, bylos numeris, asmens tapatybės kortelės numeris ir apie
  šimtas kitų lauko žodžių) daugiau nebebuvo atpažįstamas, kai tik
  antraštė nebuvo tiksliai tokiomis pačiomis didžiosiomis/mažosiomis
  raidėmis, kokia įrašyta kataloge – „kundennummer:“ el. laiške ar
  „KUNDENNUMMER:“ formos antraštėje likdavo nepaliesti.
### Nauja

- **Realistiškos pakeitimo reikšmės dabar yra sąmoningai naudojamas
  pavyzdys, o ne numatytoji nuostata.** Išimčių lentelė skirtuke
  „Vietos žymekliai“ prasideda tuščia. Naujas mygtukas ten pageidaujant
  įrašo tikėtinas neteisingas reikšmes vardui, vietovei, adresui,
  organizacijai, el. paštui, telefonui, vidiniam numeriui ir IBAN. Jis
  aiškiai palieka pinigines sumas prie numeruoto vietos žymeklio;
  strategija „sugalvoti“ atskiroms rūšims lieka pasirenkama ir toliau
  rankiniu būdu.
- **DI pakopa gali naudoti vaizdo plokštę.** Windows sistemoje tam
  galima papildomai atsisiųsti beveik 17 MB dydžio papildomą paketą;
  po to DI pakopa tinkamoje vaizdo plokštėje skaičiuoja žymiai greičiau
  nei procesoriuje. Kas jos neturi ar nieko neatsisiunčia, dirba toliau
  nepakitusiai – tik lėčiau. macOS sistemoje pagreitinimas jau įdiegtas
  savaime.
- **Du nauji pranešimai per užduočių juostos simbolį**: kai peržiūra
  prieš pakeitimą paruošta apžiūrai ir kai apdorojimas baigtas. Abu
  numatytai įjungti ir gali būti atskirai išjungti skiltyje *Nustatymai
  → Programa → Pranešimai*.

### Pakeista

- **Asmens tapatybės kortelės ir vairuotojo pažymėjimo numeris dabar
  atpažįstami**, kai prieš juos stovi antraštė
  („Personalausweisnummer: …“, „Führerscheinnummer: …“) – iki šiol abu
  buvo praleidžiami kiekvieno atpažinimo metu.
- **Maskuro dabar seka Windows kontrasto dizainus.** Kas skiltyje
  *Nustatymai → Prieinamumas → Kontrasto dizainai* vieną turi įjungtą,
  iki šiol jį gaudavo visur, tik ne čia: Maskuro po to nustatydavo savo
  spalvas. Dabar lieka prie sistemos dizaino – langas, sąrašai, numetimo
  zona, protokolas ir būsenos spalvos. Spalvotas patikros šviesoforas
  peržiūroje ir taisymo lange ten sąmoningai išnyksta – ką jis sako, jau
  seniai stovi šalia kaip ženklas ir kaip žodis.
- **Patikros poreikis dabar nurodomas ne tik spalva.** Raudona, oranžinė
  ir žalia yra beveik vienodo šviesumo – kas turi raudonos-žalios spalvų
  silpnumą, peržiūroje ir radinių skydelyje matydavo sąrašą be jokio
  skirtumo, o tai maždaug kas dvyliktas vyras. Kiekviena eilutė dabar
  papildomai turi forma besiskiriantį ženklą: ▲ tikrinti pirmiausia,
  ● tikrinti, ○ gerai pagrįsta, ◆ be vertinimo. Trumpas paaiškinimas
  tai nurodo žodžiais, ir ekrano skaitytuvas jį perskaito.
- **Alt vėl atveria meniu kaip įprasta.** Meniu juosta neturėjo
  klaviatūros spartųjų klavišų: kas nesinaudoja pele, turėjo klaidžioti
  per kiekvieną meniu rodyklėmis. Dabar kiekvienas įrašas turi
  pabrauktą raidę – Alt+D „Datei“ (Failas), iš ten B „Beenden“
  (Baigti) –, ir tai visomis sąsajos kalbomis.
- **Valdymo elementai vėl sako ekrano skaitytuvui, kam jie skirti.**
  Taisymo lange, taisyklių lange, protokole, žodžių sąrašuose, pagalboje,
  paieškoje ir dar penkiuose languose sąrašai, paieškos laukai, iškrentantys
  sąrašai ir slankikliai iki šiol buvo skelbiami tik kaip „medis“ arba
  „kombinuotas laukas“ – be to, koks. Dabar apie keturiasdešimt vietų
  turi pavadinimą. (Pagrindinis langas buvo tvarkoje nuo rugpjūčio; po
  to atsiradę langai niekada nebuvo pritaikyti šiam žingsniui.)
- **Kas naudojasi klaviatūra, visur mato, kur yra.** Ties patikros
  poreikio slankikliais, žymimuoju langeliu ir peržiūros mygtuku
  „niekada daugiau“, ties rūšių antraštėmis joje, ties taisymo lango
  puslapių skydeliu ir nustatymų šoniniu meniu trūko rėmelio, kurį
  sistema kitaip deda aplink pasiektą valdymo elementą.
- **Didesnis sistemos šriftas nieko daugiau nebekerpa.** Kas skiltyje
  *Prieinamumas → Teksto dydis* nustato virš 175 %, iki šiol prarasdavo
  antraščių galą aplankų sekimo ir sparčiųjų klavišų laukuose. Pagalbos
  skyrių sąrašas ilgus skyrių pavadinimus nukirsdavo jau ir prie
  įprasto šrifto; dabar jis juos perkelia į naują eilutę ir pilną
  pavadinimą nurodo trumpame paaiškinime.

- **Atpažinimas tapo žymiai greitesnis.** Pažymėtų identifikavimo
  numerių atpažintuvas („Kundennummer: K903944“) iki šiol kiekvienam
  teksto ruožui iš eilės tikrindavo per 1200 pavienių šablonų – tai
  buvo didžiausia atskira atpažinimo laiko dalis kiekvienoje pastraipoje
  ir kiekviename lentelės langelyje. Dabar tai vienas šablonas su tuo
  pačiu rezultatu: matavimo korpuse nesikeičia nė vienas radinys,
  pagrindinė pakopa kiekvienam teksto ruožui tampa maždaug tris–keturis
  kartus greitesnė.
- **Langas atsiranda paleidus iškart.** Iki šiol pagrindinis langas
  pilnai įkraudavo kalbos įrankius dar prieš jam apskritai
  pasirodant – maždaug keturios sekundės aklo laiko kiekvieną kartą
  paleidžiant. Modeliai dabar kraunami kaip ir numatyta fone, kol langas
  jau stovi; mygtukas „Valyti“ kaip ir anksčiau tampa prieinamas tik
  tada, kai viskas paruošta. Taip pat gryni informaciniai komandinės
  eilutės kvietimai (pvz., `--version`) dabar atsako iškart, o ne po
  kelių sekundžių.
- **Vaizdai automatinio kalbos atpažinimo metu dabar skaitomi tik
  vieną kartą.** Iki šiol teksto atpažinimas su numatytuoju nustatymu
  „Kalba: automatinė“ du kartus vykdavo per tą patį vaizdą – vieną
  kartą kalbos spėjimui, vieną kartą tikram tikrinimui. Vaizdo failai,
  iškarpinės vaizdai ir teksto langas dėl to baigia darbą apie du
  kartus greičiau; išjungus teksto atpažinimą, iki šiol nepastebimai
  vis tiek vykstantis skaitymas visai nebevyksta.
- **Išsaugoti tinklalapiai ir el. laiškai dabar valomi greičiau.**
  Reikšmės HTML atributuose, komentaruose ir įterptuose duomenų
  blokuose iki šiol buvo atpažįstamos po vieną – savivaldybės puslapis
  su šimtais antraščių atpažinimui uždavė šimtus atskirų klausimų.
  Dabar jos surenkamos ir kiekviena skirtinga reikšmė atpažįstama tik
  vieną kartą; matavimo korpuse nesikeičia nė vienas radinys, .html ir
  .eml apdorojami maždaug trečdaliu greičiau.
- **Lentelių ir pristatymų šalutinės saugyklos taip pat atpažįstamos
  surinktai.** Alternatyvūs tekstai, formulių eilutės, diagramų
  antraštės, komentarai, suvestinių lentelių talpykla ir dokumento
  savybės iki šiol kiekvienai reikšmei uždavė atskirą atpažinimo
  klausimą – knyga su tūkstančiais suvestinės eilučių atitinkamai
  tūkstančiais. Dabar vyksta vienas surinktas praėjimas per skirtingas
  reikšmes, o pabaigos papildomas pilnas praėjimas vyksta tik tada, kai
  nuo pagrindinio teksto tikrai atsirado naujų reikšmių. Matavimo
  korpuse nesikeičia nė vienas radinys.
- **Formų gausūs PDF failai valomi greičiau.** Laukai, pastabos,
  žymos ir nuorodos masiškai kartoja tas pačias reikšmes („Off“
  kiekviename žymimajame langelyje, tas pats autorius kiekvienoje
  pastaboje) – iki šiol kiekviena uždavė savo atpažinimo klausimą.
  Kiekviename praėjime reikšmė dabar atpažįstama tik vieną kartą;
  pakeitimas ir nuoseklumo papildomas praėjimas kaip anksčiau vyksta
  kiekvienai vietai.
- **Dideli lentelių failai (.csv/.tsv) valomi žymiai greičiau.**
  Keturi lentelių papildomi praėjimai iki šiol patys ženklas po ženklo
  ardydavo tą patį failą į langelius (esant 40 MB tai apie 30 s
  papildomo darbo); dabar suskaidymas vyksta vieną kartą. Antraštės
  atpažinimas (gimimo datos ir personalo numerio skiltys) vietoj
  klausimo kiekvienam langeliui uždavo surinktą – esant vienodiems
  radiniams maždaug dvidešimt kartų greičiau. O didelių personalo
  sąrašų vardų skilčių suvestinė nebėra kvadratinė pagal eilučių
  skaičių.
- **Rodiklių skydelis nebekausto lango.** Rodiklių atskleidimas su
  daugeliu didelių failų pirmiausia surinkdavo jų tekstą ir dėl to
  langas kelias sekundes stovėdavo. Skaičiavimas dabar vyksta fone;
  skydelis atsidaro iškart ir skaičius papildo vėliau.
- **Paieškos ataskaita nebekausto lango.** Perieškojus daug tūkstančių
  failų, bendras aplankas buvo iš naujo perskaičiuojamas kiekvienam
  paveiktam failui; dideliuose praėjimuose langas dėl to stovėdavo
  dvienženklį skaičių sekundžių. Ataskaita dabar pasirodo iškart.
- **PDF failai su teksto atpažinimu tikrinami greičiau.** Kiekvienas
  puslapis pertikrinant nereikalingai buvo du kartus konvertuojamas į
  PNG formatą; dabar perduodamas jau esamas vaizdas. Rezultatas
  nepakitęs, tik patikra vyksta sparčiau.
- **Nuostabos pastabos dideliuose vaizduose nebetrūkčioja.** Traukiant
  už rankenėlių pastabą su perėjimu, perėjimas iki šiol buvo
  perskaičiuojamas taškas po taško – dideliame ekrano nuotraukos
  vaizde tai buvo matomas stringimas. Rezultatas toks pat, tik be
  pauzės.

### Ištaisyta

- **Kryžius failui pašalinti iš sąrašo vėl yra paprastas X.** Naujas
  redaktoriaus įrankis „Pašalinti“ netyčia naudojo tą pačią simbolio
  žymą ir dėl to rodė savo raudoną kryžių kartu su punktyrine teksto
  linija ir kiekvienoje failo eilutėje. Abu veiksmai dabar turi
  atskirus simbolių pavadinimus ir išlaiko kiekvienam tinkantį
  pateikimą.
- **Kelių dalių duomenys PDF failuose dabar atpažįstami ir per matomą
  eilutės lūžį.** Maskuro dabar geometriškai sukurtą puslapio tekstą
  papildomai skaito kaip poslinkiu sutampantį teksto rodinį. Tai
  galioja visiems pagrindinės ir aukštosios pakopos atpažintuvams bei
  saviems paieškos šablonams, ne tik pirmiausia matomam atvejui
  „Diabetes mellitus Typ 2“. Tuščios eilutės ir atpažintos lentelės ar
  skyriaus ribos lieka griežtos ribos; radimo vietos toliau tiksliai
  atitinka uztemdomus žodžius.
- **Pavyzdys prie „Pseudonimizuoti“ prieštaravo pats sau.** Sakinys
  žadėjo „tas pats asmuo, tas pats numeris“ ir tada rodė du skirtingus
  numerius – lygiai tokį vaizdą, koks yra teisingas su
  „Anonimizuoti“. Abu pavyzdžiai dabar sutampa su savo sakiniu.
- **Ką tik įterptas vietos žymeklis „Atkurti originalą“ metu galėjo
  likti kaip persidengęs raidžių košė vietoj to, kad išnyktų.**
  Vienspalvis įterptas vietos žymeklis iki šiol rašė savo atskirą
  išvesties komandą kiekvienam ženklui, iš kurių tik pirmasis turėjo
  savo teksto matricą – tolesnio to paties vietos redagavimo metu (pvz.,
  „atkurti“ iškart po to) likę ženklo komandos ratu gaudavo pirmojo
  ženklo indeksus, ir vietos žymeklis suirdavo į dvi persidengiančias
  pozicijas. Vienspalvis vietos žymeklis dabar gauna vieną vientisą
  išvesties komandą visam savo tekstui.

- **Jei tas pats uztemdytas ar pašalintas žodis stovėjo dviejose
  eilutėse taisymo lange ir abi buvo pažymėtos atšaukimui, antroji
  eilutė klaidingai skaičiuota kaip „nevienareikšmė“ – nors reikšmė jau
  seniai buvo atkurta.** Abi eilutės dabar laikomos atliktomis.

- **Vardas po „Reply-To:“ dabar randamas.** El. laiško antraštėje,
  tokioje kaip „Reply-To: Huber“, vardas iki šiol visai nebuvo
  atpažįstamas – kalbos modelis skaitė „Reply-To:“ kaip savo atskirą,
  klaidingą asmenį ir praleisdavo tikrąjį vardą po jo.

- **El. laiško antraštės žodžiai „Reply“ ir „Fwd“ daugiau patys
  neuztemdomi kaip vardas.** Temos eilutėje, tokioje kaip „Fwd:
  Angebot von Huber“, iki šiol be vardo dar buvo atpažįstamas ir
  uztemdomas ir pats antraštės žodis kaip asmuo.

- **„Arbeitgeber: Siemens AG“ dabar atpažįstama kaip įmonė, o ne kaip
  asmuo.** Jei įmonės reikšmė po antraštė „Arbeitgeber“ turėjo teisinę
  formą, tokią kaip GmbH, AG ar KG, ji, nepaisant įjungto organizacijų
  atpažinimo, likdavo asmens radiniu – iki šiol kaip įmonė buvo
  atpažįstamas tik siauresnis atvejis be teisinės formos („Wollmuth
  und Partner“).
- **Kartą atpažintas adresas nebelieka kitoje vietoje.** Jei gatvės
  adresas buvo atpažintas ir pakeistas vienoje vietoje, tas pats adresas
  kitoje vietoje galėjo likti nepakeistas – pvz., sunkiai įskaitomoje
  nuskaityto dokumento poraštėje, kur automatinis teksto atpažinimas
  jį perskaitydavo iškraipytai. Adresai dabar, kaip ir vardai bei
  įmonės jau seniai, nuosekliai pašalinami visame dokumente.

- **El. laiškai su keliais gavėjais valymo metu buvo tyliai
  sugadinami.** `.msg` tipo laiškas su dviem ar daugiau gavėjų
  saugojant prarasdavo savo vidinės struktūros dalis, todėl išvalytas
  rezultatas būdavo nepilnas. Priežastis buvo vienodai pavadintų
  vidinių komponentų, kurie pasikartoja kiekvienam gavėjui, sumaišymas.
  Tokie laiškai dabar visiškai atkuriami iš naujo.

- **Du iš pridedamų testinių dokumentų nebuvo atveriami Word ir
  PowerPoint programose.** Kas parsisiuntė matavimo korpusą, gaudavo
  ties `format_dokument.docx` pranešimą „Klaida atveriant failą Word
  programoje“ ir ties `format_praesentation.pptx“ „Failas
  sugadintas“. Abu failai buvo klaidingi dar prieš tai, kai Maskuro juos
  palietė – išvalyta versija tiesiog perimdavo klaidą. LibreOffice abu
  atverdavo be trukdžių, todėl to niekas nepastebėjo.

- **Sava DI internete dabar pasiekiama šifruotai.** Kas savai DI
  įrašo išorinį adresą be „https://“ (kaip dažnai nurodyta IT skyriaus
  lapelyje), iki šiol jį pasiekdavo per nešifruotą ryšį – neuztemdytas
  tekstas keliaudavo aiškiu tekstu. Tokie adresai dabar pasiekiami per
  „https://“; serveris savame tinkle lieka pasiekiamas nepakitęs. Jei
  serveris nukreipia į kitą kompiuterį, prieigos raktas kartu nebekeliauja.

- **Ir sugadintas vaizdas dabar praranda savo paslėptus
  metaduomenis.** Jei įterptas vaizdas nebebuvo galima pilnai atverti
  (pvz., nukirsta nuotrauka), jis iki šiol išlaikydavo savo EXIF ir GPS
  duomenis – fotografavimo vieta ir fotografo vardas likdavo
  nematomi rezultate. Tokie vaizdai dabar taip pat atlaisvinami nuo šių
  duomenų net tada, kai jų iš viso nebeįmanoma rodyti.

- **Įterptas failas, kurio nepavyko išvalyti, dabar pranešamas, o ne
  tyliai perkeliamas toliau.** Jei pristatyme ar knygoje buvo įterptas
  objektas, kuris buvo per giliai įdėtas arba jo nepavyko atverti, jis
  iki šiol likdavo nepakitęs rezultate be jokio nurodymo – failas buvo
  laikomas išvalytu. Tokie atvejai dabar minimi įspėjime „NEBUVO
  patikrinti“, lygiai taip pat kaip įterptas senas formatas.

- **Tamsūs sąrašai vėl nuosekliai tamsūs ir įskaitomi.** macOS sistemoje
  failų sąrašai keitėsi tarp beveik juodų ir šviesiai pilkų eilučių;
  taisant dėl to ta pati žalia, oranžinė ar raudona patikros reikšmė
  atrodydavo skirtingai priklausomai nuo eilutės. Langas, sąrašai,
  šriftas, vietos žymekliai ir pasirinkimas dabar sekami vienos bendros
  šviesios/tamsios paletės. Spalvomis pažymėtas radinių sąrašas be to
  daugiau nebeuždeda zebro juostų po savo spalvomis.

- **Profesijos nurodymai su „als“ buvo klaidingai uztemdomi kaip
  vardas.** Sakinys, toks kaip „Als Koch ist er seit vier Jahren bei
  uns tätig.“, prarasdavo profesiją, ne tik vardą – „als“ pradeda
  vaidmens nurodymą lygiai taip pat kaip „der“ ar „die“. Tikros
  pavardės toje pačioje vietoje (pvz., su kreipiniu prieš tai) lieka
  nepaliestos.

- **Lentelės antraštė galėjo įtraukti pozicijos numerį į piniginę
  sumą** (tik esant įjungtai parinkčiai „Pašalinti ir pinigines
  sumas“). Jei eilutė baigdavosi valiuta („… Einzelpreis EUR“) ir
  sekanti prasidėdavo skaičiumi, iš to klaidingai susidarydavo suma
  per eilutės lūžį. Skirtukas tarp valiutos ir skaičiaus dabar lieka
  toje pačioje eilutėje.

- **Trumpa santrumpa didžiosiomis raidėmis galėjo praryti visą sakinio
  dalį arba prisijungti prie teisingai atpažinto vardo.** Jei eilutėje
  stovėjo dviejų raidžių didžiąja raide rašytas žodis, toks kaip „DI“,
  „AG“ ar „KG“ – kasdienės santrumpos, ne vardai –, visa eilutė bandomai
  buvo tikrinama mažosiomis raidėmis, ir santrumpa kartais įtraukdavo
  gretimus žodžius (net veiksmažodžius) į vieną tariamą vardą. Tik nuo
  trijų raidžių didžiosiomis raidėmis rašomas žodis dabar sukelia šį
  antrą patikrinimą. Su šiek tiek ilgesniais santrumpomis, tokiomis kaip
  „CEO“ ar „USB“, likdavo antra klaida: jau teisingai rastas vardas
  („Schneider“) gaudavo priešais stovinčią santrumpą kaip priešdėlį,
  įtrauktą į rezultatą („CEO Schneider“). Santrumpa dabar lieka nuošalyje.

- **Gimimo data be tarpo po jos likdavo stovinti.** Jei po „geb.“
  nebūdavo tarpo prieš datą – kaip įprasta glaudžiai surašytose formose
  („geb.14.03.1988“) –, Maskuro lauko neatpažindavo ir palikdavo datą
  nepaliestą. Dabar atpažįstamos ir dažnos trumposios formos, tokios
  kaip „Geburtsdat.“ ar „Geb.-Dat.“

- **IBAN su pasviraisiais brūkšniais kaip skirtukais likdavo
  stovinti.** Kaip ir telefono numerių atveju („0664/1234567“), kai
  kurios šablonai IBAN taip pat rašo blokais su pasviruoju brūkšniu
  („AT48/3200/0000/1234/5864“) vietoj tarpo ar brūkšnelio. Ši rašyba
  dabar taip pat atpažįstama.

- **Austrijos socialinio draudimo numeris su brūkšneliu, tašku ar
  pasviruoju brūkšniu likdavo stovintis arba buvo neteisingai
  pažymėtas.** Tarp dviejų skaitmenų blokų iki šiol buvo numatytas tik
  tarpas; rašybos, tokios kaip „1237-010180“, „1237.010180“ ar
  „1237/010180“, nebuvo atpažįstamos (arba pasviro brūkšnio atveju buvo
  atpažįstamos neteisinga rūšimi). Kontrolinis skaitmuo toliau patvirtina
  kiekvieną radinį, nepriklausomai nuo skirtuko.

- **Vardas po „c/o“ adrese visai nebuvo pašalinamas.** „c/o Max
  Mustermann, Hauptstraße 5, 1010 Wien“ uztemdydavo gatvę ir vietovę,
  bet vardą po jomis palikdavo visiškai stovintį. Vardas dabar
  atpažįstamas; „c/o“ pats lieka matomas kaip adreso nuoroda.

- **Su taškais sugrupuotas kredito kortelės numeris likdavo stovintis.**
  Rašybos, tokios kaip „4111.1111.1111.1111“, nebuvo atpažįstamos; su
  tarpu ar brūkšneliu atskirti numeriai to nepaveikė. Kontrolinė suma
  toliau patvirtina kiekvieną radinį.

- **Su brūkšneliais sugrupuotas mokesčių identifikavimo numeris likdavo
  stovintis, taip pat ir austriškas PVM kodas su brūkšneliu ar
  tašku.** Tarpas, pasvirasis brūkšnys ir taškas mokesčio ID atveju
  jau buvo numatyti, trūko brūkšnelio; PVM kodo atveju
  („ATU12345678“) trūko brūkšnelio ir taško po priešdėlio. Mokesčio
  ID kontrolinis skaitmuo toliau patvirtina kiekvieną radinį.

- **Lauko reikšmė kabutėse likdavo stovinti, pvz., JSON tipo eilutėje,
  tokioje kaip „vorname“: „Max“.** Atpažinimas per lauko antraštę
  („Vorname: …“) iki šiol reikalavo, kad nei antraštė, nei pati reikšmė
  nebūtų kabutėse. Tokios eilutės dabar taip pat atpažįstamos – lygiai
  taip pat kaip lauko antraštės su pridėtu YAML sąrašo ženklu
  („- Vorname: Max“) arba tabuliavimo ženklu vietoj tarpo prieš
  dvitaškį.

- **El. laiško antraštės žodis „Sent“ pats buvo uztemdomas kaip
  vardas.** Antraštėje, tokioje kaip „Sent: Huber“, iki šiol buvo
  paveikiami ir „Sent“, ir pats tikras vardas; giminingi antraštės
  žodžiai, tokie kaip „Subject“ ar „Betreff“, jau seniai to
  nepaveikdavo. „Sent“ dabar taip pat lieka stovintis.

- Vardas po antraštėmis „Errors-To:“ ar „Resent-From:“ likdavo
  neatpažintas, kai tokia eilutė stovėjo nukopijuota aiškiame tekste
  (pvz., persiųstas laiškas ar incidento ataskaita) – skirtingai nei su
  „Reply-To:“ ar „Return-Path:“, vardas čia visiškai dingdavo, o ne tik
  netiksliai apribojamas. Dabar jis randamas.
- Tas pats failas dviejų valymo metu kartais duodavo skirtingą
  rezultatą: jei du atpažinimai lygiai sutapo toje pačioje vietoje su
  tuo pačiu ilgiu ir tuo pačiu patikimumu (pvz., „Sozialversicherungs-
  nummer 1237/010180“ kaip AT_SVNR arba kaip bendras identifikavimo
  numeris), atsitiktinai priklausydavo, kuris laimi – reikšmė abiem
  atvejais buvo pašalinama, keitėsi tik vietos žymeklio žymėjimas.
  Lygiosios dabar visada sprendžiamos vienodai.
- Pareigų pavadinimas tiesiai prieš daiktavardį (pvz., „Behandelnder
  Arzt: Dr. …“ ar „Zuständiger Sachbearbeiter ist …“) kartais buvo
  klaidingai kartu uztemdomas, tarsi jis pats būtų vardas. Tikros
  pavardės šalia to nepaveikia.
- Tikra pavardė, kuri atsitiktinai atrodo kaip būdvardis (pvz.,
  „Schöne“, „Lange“, „Junge“) ir stovi tiesiai prieš kitą daiktavardį
  (pvz., „Kontaktperson: Schöne Assistentin“), nuo paskutinio taisymo
  likdavo tekste neuztemdyta – duomenų nutekėjimas. Dabar tik siaurai
  apribotas sąrašas tikrų pareigų pavadinimų (pvz., „Behandelnder“,
  „Zuständiger“) šioje formoje traktuojamas kaip ne vardas.
- Pavieniui stovinti pavardė daugiaeilio vardo radinio pabaigoje, kuri
  atsitiktinai atrodo kaip būdvardis (pvz., „Schwarz“, „Kurz“, „Alt“,
  „Frisch“, „Gut“, „Reich“), likdavo neatpažinta prieš tiesiogiai
  einantį dvitaškį – valymas ją supainiodavo su lauko antrašte, tokia
  kaip „Telefon:“. Uždaras žinomų daugiareikšmių pavardžių sąrašas dabar
  ją saugo.
- Pavieniui stovinti pavardė, kuri atsitiktinai yra įprastas vokiškas
  žodis („Gross“/„Grosse“, „Gut“, „Kurz“, „Lang“/„Lange“), iki šiol
  **visiškai** dingdavo – net paprastuose sakiniuose, tokiuose kaip
  „Herr Gross unterschrieb den Vertrag.“ Priežastis buvo spaCy pačios
  stabdomųjų žodžių sąraše, kuris šiuos žodžius apima; uždaras žinomų
  pavardžių sąrašas dabar apsaugo jas nuo atmetimo.
- Darbo, paskolos, laidavimo, patikėjimo ir bankroto sutartyse bei
  globos/rūpybos ir ekspertizės užsakymuose pavardė, kuri tuo pačiu
  metu yra paprastas žodis (pvz., „Bauer“), buvo praleidžiama po
  antraštėmis „Auftraggeber:“, „Auftragnehmer:“, „Arbeitnehmer:“,
  „Versicherter:“, „Darlehensgeber:“, „Darlehensnehmer:“, „Bürge:“,
  „Sicherungsgeber:“, „Treuhänder:“, „Treugeber:“,
  „Insolvenzverwalter:“, „Gutachter:“, „Sachverständiger:“,
  „Vormund:“ ar „Pfleger:“ – kartais atpažįstamas likdavo tik vardas,
  kartais dingdavo visas vardas.
- Įmonės rekvizituose pavardė, kuri tuo pačiu metu yra paprastas žodis
  (pvz., „Bauer“), buvo praleidžiama po antraštėmis
  „Geschäftsführer:“, „Geschäftsführerin:“, „Vertretungsberechtigt:“,
  „Inhaber:“ ar „Inhaberin:“ – su „Geschäftsführer:“/„Inhaber:“
  dingdavo visas vardas, su „Vertretungsberechtigt:“ atpažįstamas
  likdavo tik vardas.
- Kontaktinis blokas, kurio antraštė stovėjo eilutėje viena su lyčiai
  neutraliu dvitaškio variantu („Ansprechpartner:in“, vardas po ja),
  buvo **visiškai** praleidžiamas – dvitaškis buvo skaitomas kaip
  lauko skirtukas, „in“ kaip (atmesta) lauko reikšmė, ir tikrasis
  vardas sekančioje eilutėje dėl to niekada nebebuvo pasiekiamas.
  Žvaigždutės forma („Ansprechpartner*in“) to nepaveikė.
- Jei vardas ir antraštė su ta pačia dvitaškio lyčių forma stovėjo
  **vienoje** eilutėje („Ansprechpartner:in Anna Berger“), vietos
  žymeklis nusinešdavo žodį „in“ į pakeitimą vietoj to, kad pašalintų
  tik vardą – pats vardas ir toliau buvo pilnai aprėpiamas.
- Vardas lentelės skiltyje po asmens skilties antrašte (pvz., „Name
  Vorname Geburtsdatum“ virš „Bauer Anna 03.05.1985“, kaip atlyginimo
  lapelyje) buvo visiškai praleidžiamas, kai tik tarp skilčių stovėjo
  vien tik vienas tarpas ir jokia eilutė neprasidėjo skirstymo
  numeriu – lygiai ta forma, kuria tikra PDF teksto ištrauka tokias
  eilutes pateikia.
- Pokalbio ar posėdžio protokole su kalbėtojo vardu prieš dvitaškį
  (pvz., „Bauer 🙂: Ich stimme dem Vorschlag zu.“) vardas visiškai
  nebuvo atpažįstamas, kai tik tarp vardo ir dvitaškio stovėjo reakcijos
  ženklas ir pavardė tuo pačiu metu buvo įprastas žodis („Bauer“,
  „Koch“, „Schneider“ ir pan.) – dėl to visas protokolas galėjo likti be
  nė vieno atpažinto kalbėtojo.
- Ta pati kalbėtojo eilučių spraga egzistavo ir su kitais tarpiniais
  ženklais prieš dvitaškį: statuso priedu skliaustuose („Bauer
  (Vorsitz): …“, „Bauer (abwesend): …“), laiku kvadratiniuose
  skliaustuose („Bauer [14:32]: …“) ir išnašos ženklu tiesiai prie
  vardo („Bauer*: …“). Ir čia kalbėtojas visiškai nebuvo atpažįstamas,
  kai tik pavardė tuo pačiu metu buvo įprastas žodis.
- Jei jau atpažintas asmuo pridėtame protokolo ar žurnalo fragmente
  toje pačioje žinutėje (pvz., pagalbos bilieto) papildomai stovėjo
  kaip vartotojo vardas formos „vardas.pavardė“ – rašomas mažosiomis
  raidėmis, be tarpo, sujungtas tašku –, šis aiškus vardas likdavo
  įskaitomas, nors tas pats vardas laiške jau buvo uztemdytas.
- Ta pati vartotojo vardo spraga egzistavo ir su pabraukimu vietoj
  taško („vardas_pavardė“) – lygiai taip pat paplitęs formatas
  protokolo ir žurnalo fragmentuose.
- Ir atvirkštine tvarka vartotojo vardas likdavo įskaitomas
  („pavardė.vardas“ arba „pavardė_vardas“) – kai kurios sistemos
  žurnalo vartotojo varde pavardę deda prieš vardą, o ne po jo.
- Mirties data likdavo neatpažinta, kai šalia nebūdavo kito duomens
  („Herr Bauer ist am 12.03.1985 verstorben“) – tam iki šiol nebuvo
  jokio savo atpažinimo, o bendras datos atpažinimas šiuo standartiniu
  slenksčiu neveikia.
- Mirties data taip pat likdavo neatpažinta, kai sakinyje buvo naudojama
  veiksmažodžio, o ne dalyvio forma („Frau Meier verstarb am
  12.03.1985“, „Er starb am 12.03.1985“) – iki šiol veikė tik „ist …
  verstorben“/„ist … gestorben“.
- Santuokos data likdavo neatpažinta, nesvarbu, kokia forma ji buvo
  užrašyta („Eheschließung am 12.03.2010“, „Hochzeitsdatum:
  12.03.2010“, „Herr und Frau Bauer heirateten am 12.03.2010“) – tam
  iki šiol nebuvo jokio savo atpažinimo, o bendras datos atpažinimas
  šiuo standartiniu slenksčiu neveikia.

- **Taisymo redaktoriuje antras rėmelis virš ką tik įterpto vietos
  žymeklio galėjo palikti raudoną ženklo likutį**, pvz., „[G“ vietoj
  „[BEG1]“ – be jokio įspėjimo, nes likutis nebepriklausė
  konfidencialiam duomeniui (tas jau buvo pašalintas pirmuoju
  veiksmu), o tik pačiam vietos žymekliui. Priežastis buvo spalvinimas:
  naujai įterptas vietos žymeklis buvo įrašomas ženklas po ženklo į
  failą, net esant vienspalvei nuostatai – vėlesnis rėmelis toje
  pačioje vietoje dėl to nebegaudavo vientiso teksto, prie kurio galėtų
  susieti savo vietą. Dabar vienspalvis vietos žymeklis stovi sraute
  kaip vienas gabalas, taip kaip automatinis valymas visada darė; tik
  tikras perėjimas ar vaivorykštinis tekstas ir toliau reikalauja
  pavienių ženklų. Įdiegta kontrolinė patikra dabar tokį likutį papildomai
  atpažįsta ir tada, kai tikslus vietos žymeklio ženklų junginys
  nebeatsiranda.
- Numeruotas vardų sąrašas su laipsniškai skaidytu skirstymo numeriu
  („1.1 Max Mustermann“, „1.2 Huber Franz“ …) prarasdavo visus vardus
  dėl tos pačios apsaugos, kuri iš tikrųjų turėtų saugoti tik tikras
  skirsnių struktūras ir pozicijų sąrašus – be skilties antraštės virš
  sąrašo nebuvo jokio liudytojo, prie kurio vardas galėtų prisišvartuoti
  ir išsigelbėti.
- Vardas angliškoje sistemos žurnalo prisijungimo eilutėje („Accepted
  password for Max Mustermann from 10.0.0.5 port 51000 ssh2“) nebuvo
  atpažįstamas – vokiškas kalbos modelis jį rasdavo tik tada, kai prieš
  jį stovėjo „invalid user“, kitaip jis likdavo stovintis. Tokie
  žurnalo fragmentai dažnai pridedami prie incidento ataskaitos
  nepakitę. Vardai po „for“ prieš IP adresą dabar patikimai
  atpažįstami.
- Mokėtojo vardas sąskaitos išrašo ar apskaitos žurnalo SEPA pavedimo
  nuorodoje (pvz., „MREF+Mustermann Klaus+SVWZ+ Miete August“) likdavo
  atviras – jokio tarpo, jokios sakinio struktūros, tik su „+“
  atskirti didžiųjų raidžių laukai, ir tenai įprasta tvarka „Pavardė
  Vardas“ atpažinimas jo taip pat neaptikdavo nė atsitiktinai. Dabar
  atpažįstamas.
- Gatvė kartu su namo numeriu pirmoje adreso lentelės eilutėje (pvz.,
  „Pavardė | Vardas | Gatvė | Pašto kodas | Vietovė“) likdavo atvira –
  kalbos modelis ten spėdavo klaidingą, bet ilgesnę vietovę per kelias
  skiltis, ir ji išstumdavo teisingą, trumpesnį adreso radinį. Dabar
  atpažįstama.
- Ta pati spraga pasireiškė ir su tabuliavimo ženklu vietoj „|“ ar „;“
  kaip skilties skirtuku – ten adresas net visai dingdavo, o ne tik
  prarasdavo dalį. Dabar atpažįstama.
- Gatvė su namo numeriu likdavo atvira, kai tiesiogiai po jos be
  tarpo sekdavo pašto kodas su kableliu (pvz., „Bahnhofstrasse
  12,80331 München“, kaip kableliu atskirtoje lentelės skiltyje) –
  kablelis atrodė kaip kiekio dešimtainės dalies ženklas, ir dėl to
  gatvė šablonui apskritai nepatekdavo kaip adresas. Dabar atpažįstama.
- Gatvė su namo numeriu likdavo atvira, kai tiesiogiai po jos be
  kablelio sekdavo vietovės priešdėlis „St.“ (Sankt) (pvz.,
  „Hauptstraße 5 St. Pölten“, laiško antraštė be prieš tai einančio
  pašto kodo) – „St.“ atrodė kaip vienetų kiekio matas, ir dėl to gatvė
  šablonui apskritai nepatekdavo kaip adresas. Dabar atpažįstama.
- Durų/laiptų priedas po namo numerio (pvz., „Lerchenfelder Gürtel
  43/12“) likdavo atviras matomas, kai tiesiogiai po jo stovėjo
  pavienė raidė, atsitiktinai sutampanti su matavimo vienetu (pvz.,
  „h“ valandai) – adresas tada buvo išvalomas tik iki namo numerio be
  jo priedo, vietoj to, kad būtų aprėptas visas arba visai
  neaprėptas.
- Betreff eilutė su profesija sutampančia pavarde prieš vardą
  („Betreff: Bauer Anna“, „Betreff: Bauer, Anna“) iki šiol visiškai
  nebuvo atpažįstama – net dokumento viduryje su prieš tai einančiu
  pilnu sakiniu. Dabar atpažįstama.
- Vokiškas mokesčių numeris su tarpu, tašku ar brūkšneliu tarp blokų
  (pvz., „Steuernummer: 30 815 08153“ arba „30.815.08153“) iki šiol
  nebuvo atpažįstamas – buvo randama tik rašyba su pasviruoju brūkšniu.
  Dabar atpažįstama.
- Vardas po medicinine lauko antrašte („Patient:“, „Hausarzt:“,
  „Behandelnder Arzt:“, „Überweisender Arzt:“ ir jų moteriškos formos)
  iki šiol nebuvo atpažįstamas, kai pavardė tuo pačiu metu buvo
  paprastas vokiškas žodis (pvz., „Patient: Bauer Thomas“). Dabar
  atpažįstama.
- Vardas po lauko antraštė „Zahnarzt“ savo eilutėje (pvz., „Zahnarzt“,
  po ja „Huber Franz“) iki šiol nebuvo atpažįstamas – nei vardas, nei
  pavardė. „Zahnärztin“ ir paprasta „Arzt“ forma to nepaveikė. Dabar
  atpažįstama.
- Pavardė po „Herr“/„Frau“, po kurios sekdavo biurokratinė frazė, tokia
  kaip „zur Kenntnisnahme“, „zur Unterschrift“ ar „zur Weiterleitung“,
  iki šiol buvo apimama per plačiai ir nusinešdavo frazę į vardo
  radinį – iš „Frau Petra Klein zur Vertretung in allen
  Angelegenheiten“ buvo pakeičiama „Petra Klein zur Vertretung“, o
  likusi sakinio dalis likdavo gramatiškai suluošinta. Tikri kilmingumo
  prielinksniai, tokie kaip „von der Leyen“ ar „zu Guttenberg“, to
  nepaveikia.
- Ta pati biurokratinės frazės perredagavimo klaida slypėjo ir po vardu
  el. laiško „To:“ antraštėje, registracijos kode (C.1/C.1.1/C.1.2),
  vairuotojo pažymėjimo kode, skliaustuose esančiame formos lauke
  („[Vorname]: …“) ir be taško atsisveikinimo frazėje – visur ten
  „zur“/„von“ ir pan. nusinešdavo tolesnę frazę, tokią kaip „zur
  Unterschrift“ ar „zur Vertretung“, į radinį, kartais net pats
  dalelytės žodis likdavo kaip vardo liekana rezultate. Ir čia tikri
  kilmingumo prielinksniai lieka visiškai nepaliesti.
- Studento pažymėjimo numeris po jo antraštę iki šiol visai nebuvo
  atpažįstamas – „Matrikelnummer 7654321“ visiškai nepatekdavo į
  atpažinimą, nei kaip identifikavimo numeris, nei per kalbos modelį,
  nes pats skaičius neturi atpažįstamos formos.
- Tas pats galiojo dalyvio numeriui – „Teilnehmernummer 4471829“
  visiškai nepatekdavo į atpažinimą, nei kaip identifikavimo numeris,
  nei per kalbos modelį.
- Gyvenimo aprašyme vardas po skyriaus antraštę „Persönliche Daten“
  dažnai visiškai ar dalinai nepatekdavo į atpažinimą, kai stovėjo
  tiesiai po ja be kreipinio forma „Pavardė Vardas“.
- Tas pats galiojo skyriaus antraštei „Kontaktdaten“ – ten vardas net
  visiškai nepatekdavo į atpažinimą, ne tik dalinai.
- Gyvenamosios vietos pažymėjime ar prašymo sąraše su sujungta skiltimi
  „Name, Vorname“ (gyventojų registro rašyba, reikšmė pvz., „Mustermann,
  Max“ viename langelyje) vardas visiškai nepatekdavo į atpažinimą, kai
  sekdavo kita skiltis, tokia kaip gimimo data.
- Gimimo data forma, įprasta asmens tapatybės kortelėje ir gyvenamosios
  vietos pažymėjime „Geburtsdatum/-ort: 22.07.1978 / Rostock“, nebuvo
  atpažįstama – veikė tik kableliu atskirta forma „Geburtsdatum,
  Geburtsort: …“.
- „Bürgerservice“ ir „Bürgerbüro“ kartais buvo klaidingai uztemdomi
  kaip vietovė, ypač po brūkšnio kaip sąrašo skirtuko (pvz., „Wenden
  Sie sich an das Bürgerservice – Bürgerbüro …“).
- Pažymėtas telefono numeris, kurį eilutės lūžis perskyrė per vidurį
  (pvz., iš siauros laiško antraštės skilties ar PDF teksto ištraukos
  ties skilties pločiu: „Telefon: 0176 12\n34567“), dalinai buvo
  uztemdomas tik iš pusės – likusi dalis po eilutės lūžio likdavo
  įskaitoma.
- Pažymėtas identifikavimo numeris (kliento, nario, sutarties numeris ir
  panašūs), kurį eilutės lūžis perskyrė per vidurį (pvz., „Kundennummer:
  K903\n944“ iš siauros skilties), buvo uztemdomas tik iš pusės –
  likusi dalis po eilutės lūžio likdavo įskaitoma.
- Vardas su akademiniu titulu prieš pareigų pavadinimą po kablelio
  (pvz., „Dipl.-Ing. Sabine Roth, Projektleiterin“) likdavo visiškai
  neapsaugotas – eilutė atrodė kaip lentelės skilties antraštė ir buvo
  klaidingai atmetama kaip dalykinis turinys.
- Titulas „Dr.-Ing.“ (dažnas vokiškas inžinieriaus laipsnis) prieš
  vardą nebuvo įtraukiamas į kaukuotą asmens reikšmę ir likdavo
  įskaitomas – ta pati brūkšnelio klaida, kaip su „Dipl.-Ing.“.
- Titulai „Dipl.-Kfm.“, „Dipl.-Kffr.“ ir „Dipl.-Psych.“ (diplomuotas
  komersantas/komersantė/psichologas) prieš vardą nebuvo įtraukiami į
  kaukuotą asmens reikšmę ir likdavo įskaitomi – ta pati brūkšnelio
  klaida, kaip su „Dipl.-Ing.“ ir „Dr.-Ing.“.
- MAC adresas Cisco rašyba su taškais vietoj dvitaškių (pvz.,
  „aabb.ccdd.eeff“, kaip jį pateikia komutatorių protokolai ir
  pagalbos bilietai) visai nebuvo atpažįstamas ir likdavo įskaitomas.
- Pavardė po „Familie“ (pvz., „Die Familie Gruber unterschreibt den
  Vertrag“) priklausomai nuo sakinio sandaros likdavo neatpažinta ir
  dėl to įskaitoma – net su kilmingumo prielinksniu prieš ją („Familie
  von der Leyen“).

- Kroatiško adreso be skiriamojo skyrybos ženklo tarp pašto kodo+vietovės
  ir gatvės+namo numerio (pvz., „10000 Zagreb Ulica Ivana Lučića 5“)
  namo numeris likdavo neišvalytas.

- Lietuviško kontaktinio duomens su antrašte „Kontaktinis asmuo“ (pvz.,
  „Kontaktinis asmuo: Vilkas Jonas“) pavardė likdavo neatpažinta, kai
  ji tuo pačiu metu buvo įprastas daiktavardis (Vilkas = „vilkas“,
  Vanagas = „vanagas“).

- Gimimo ar gyvenamosios vietos šalis be papildomos antraštės
  daniškame formos lauke (pvz., „Fødeland: Tyskland“ arba „Bopæl:
  Tyskland“) nebuvo atpažįstama.

- Gimimo ar gyvenamosios vietos šalis be papildomos antraštės
  rumuniškame formos lauke (pvz., „Țara: Germania“ arba „Țara de
  reședință: Franța“) nebuvo atpažįstama.

- Įmonės pavadinimas po lietuviška lauko antraste „Darbdavys:“ arba
  „Įmonės pavadinimas:“ (darbdavys/įmonė) nebuvo atpažįstamas.

- Įmonės pavadinimas po rusiška lauko antrašte
  „Работодатель:“ arba „Наименование организации:“
  (darbdavys/įmonė) nebuvo atpažįstamas.

- Išrašyta data su mėnesio pavadinimu rumunų kalba (pvz.,
  „31 decembrie 2024“) nebuvo atpažįstama.

- Vengriška mergautinė pavardė po santrumpa „szül.“ (pvz., „Nagy
  Éva (szül. Kovács)“) nebuvo atpažįstama ir likdavo atvira įskaitoma.

- Išsaugotas HTML profilio puslapis (arba el. laiškas su pridėtu
  tinklalapiu) galėjo palikti neišvalytą civilinį vardą, kai jis stovėjo
  tik Open Graph profilio laukuose `profile:first_name`/
  `profile:last_name`/`profile:username` – jie neša vardą suskaidytą,
  o ne aprašomąjį kaip `og:title`, ir dabar taip pat išvalomi.

- Neįteikimo pranešimas (Bounce/NDR) dažnai nešė iš pradžių neįteikto
  laiško antraštes (siuntėją, gavėją, temą) atskiroje, trečioje priedo
  dalyje – ji išvalytoje versijoje likdavo visiškai nepaliesta. Ši
  dalis dabar valoma taip pat, kaip likusi pristatymo ataskaita.

- Individualiai įvardytas apsaugotos Word srities redaktorius
  (Redagavimo apribojimas → Išimtys, `w:permStart`) likdavo aiškiame
  tekste, net jei tas pats vardas pagrindiniame tekste jau seniai buvo
  išvalytas. Dabar jis taip pat pašalinamas.

## 0.10.42-alpha.20260827 – 2026 m. rugpjūčio 27 d.

### Nauja

- **Vardu pavadinti aptikimo profiliai leidžia vienu paspaudimu pasiekti
  skirtingus darbo atvejus.** Ties *Nustatymai → Aptikimas → Kas
  pašalinama* dabar galima išsaugoti esamą kategorijų ir rūšių pasirinkimą
  ir iškart vėl pritaikyti per pasirinkimo lauką. Fiksuotas profilis
  *Numatytasis* atitinka ankstesnę pristatymo būseną ir jo negalima
  ištrinti. Profilis keičia tik tai, kas pašalinama; kalba, rezultato
  rūšis, aptikimo lygis bei nuosavi terminai ir paieškos šablonai lieka
  nepaliesti.

- **Rezultato rūšis dabar renkamasi tiesiogiai prieš valymą.**
  Bendras pasirinkimo laukas pagrindiniame lange nustato visai partijai,
  ar Maskuro įterpia įskaitomus rezetavimo laukelius (Platzhalter), ar
  juodina, ar pašalina be pakaitalo. Du atskiri laukai PDF ir Office
  nustatymų lange panaikinti; taip svarbus sprendimas matomas ir mišriose
  partijose nebegali nepastebimai išsiskirti. Vedlys prieš pirmąjį valymą
  paaiškina naująjį pasirinkimą.

- **Temos ir vandenženkliai dabar aiškiai pažymi paruoštus PDF failus, jei
  norima.** Dvylika bendrų išvaizdų suderina pakaitalo tekstus ir juodinimo
  plotus tarpusavyje; naujos yra Pride, taip pat pavasaris, vasara, ruduo ir
  žiema. *Slaptas bylas* (Geheimakte) iškart prideda įstrižą užrašą
  `TOP SECRET`. Nepriklausomai nuo to galima pasirinkti laisvą žymėjimo
  tekstą arba savo paveikslėlį, piktogramą ar SVG su spalva ir
  nepermatomumu. Importuota grafika įterpiama be jos metaduomenų ir lieka
  prieinama, jei šaltinio failas perkeliamas. Taisant iš naujo Maskuro
  pakeičia savo ankstesnį vandenženklį, o ne deda jį vieną ant kito kelis
  kartus. Teksto vandenženkliai piešiami kaip paskutinis PDF sluoksnis su
  šviesiu kontūru, kad liktų matomi ir ant tamsių paveikslėlių, ir ant
  tankaus teksto. Taisymo redaktorius Maskuro vandenženklį visiškai
  ignoruoja ir nebesiūlo jo teksto kaip juodinimo kandidato.

- **Savo pačių išvesties temas galima išsaugoti ir dalytis.** Esamas
  pakaitalo teksto, juodinimo ir vandenženklio derinys gauna pavadinimą,
  lieka nustatymuose ir gali būti eksportuotas ar importuotas kaip
  aiškiateksčio neturintis JSON. Nespalvota spaudos peržiūra įspėja apie
  silpną kontrastą; nebūtinas sėkmės konfeti lieka tik sąsajoje.

- **Paskutinis eksporto bandymas ir aiškinamasis patikros papildymas
  užbaigia išvaizdos ciklą.** Prieš galutinį išsaugojimą Maskuro dar kartą
  palygina kiekvieną tiksliai žinomą PDF vietą tekstiniame sluoksnyje ir
  atvaizduotuose pikseliuose; įspėjimai nurodo tik puslapį ir koordinates.
  Redaktoriuje *Kodėl tai uždengta?* rodo kategoriją, aptikimo būdą ir
  saugumo paraštę, bet niekada pašalintą aiškiatekstį – ir niekada
  galutiniame dokumente.

- **Juodinimo juostos dabar gali būti gražios.** Ties *Nustatymai →
  Išvaizda* yra spalvų šablonai, laisvi spalvų rinkikliai, gradientai,
  vaivorykštė, dryžiai, taškeliai, gėlės, žvaigždutės, širdelės, letenėlės,
  debesys, žaibai, kavos pupelės, antys, saulės, lapai, snaigės, popieriaus,
  markerio, lipniosios juostos ir atkuriami atsitiktiniai raštai su iškart
  matoma peržiūra. Pakaitalo tekstai gauna, pasirinktinai, spalvą,
  gradientą, vaivorykštę, piliulę arba etiketę. Kategorijų spalvos skiria
  vardus, adresus, kontaktus ir medicininius duomenis. PDF perima visą
  apdailą; Word, PowerPoint, OpenDocument ir HTML naudoja pasirinktą
  dengiamąją pagrindinę spalvą. Apsauga dėl to nesikeičia: Maskuro pirmiausia
  pašalina konfidencialų turinį ir tik tada tuščioje vietoje piešia spalvą
  ar raštą.

- **Maskuro vėl pasiekiamas Linux sistemai – kaip AppImage, DEB, RPM ir
  perkeliamasis archyvas.** DEB ir RPM įrašo programos aprašą, failų
  priskyrimus, terminalo komandą ir piktogramą į sistemą; AppImage veikia
  be diegimo. Atnaujinimai, jei jau įdiegta DEB ar RPM versija, lieka tame
  pačiame paketo formate, kitu atveju pirmenybė teikiama AppImage.

- **Vizualinė patikra nebeteikia įprasto PDF teksto kaip naujų radinių
  antrą kartą.** Baigiamasis OCR žvilgsnis ir saugus matomų puslapių
  perkūrimas lieka visiškai veikiantys; tačiau pagal numatytuosius
  nustatymus nauju radinio šaltiniu laikomos tik sritys, kurių puslapio
  tekstas ir atskiro paveikslėlio patikra dar neperskaitė. Taip produktų
  eilutės netampa naujais vardais ar įmonėmis vien dėl kitokio antrojo OCR
  skaitymo. Kas ir toliau nori dviejų nepriklausomų sprendimų dėl viso
  matomo teksto, nustatymuose įjungia *Visą matomą PDF puslapį dar kartą
  tikrinti dėl duomenų*.

- **PDF failus dabar galima peržiūrėti ištisai, lapas po lapo arba kaip
  dvipuslapį.** Trys kompaktiškos peržiūros piktogramos yra apačioje,
  tiesiai šalia „Plotis“ ir „Puslapis“. Ištisinė peržiūra slenka prie
  kito puslapio ties lapo kraštu; vieno puslapio peržiūra laiko pelės
  ratuką ant esamo lapo; dvipuslapio peržiūra rodo atverstą knygą, padaro
  paspaustą lapą redaguojamą ir stumia pirmyn/atgal per visą atvertą lapų
  porą. Puslapių miniatiūros ir palyginimo lupa taip pat atsidaro
  aiškiai siauresniame kairiajame stulpelyje ir palieka daugiau vietos
  darbo puslapiui.

- **Dabar matote, ką padarė DI (dirbtinio intelekto) pakopa.** Po
  kiekvieno paleidimo prie „Detalės“ atsiranda eilutė kiekvienam failui –
  „DI pakopa: patikrinti 12 ribinių atvejų, 3 atmesti“ – ir jei ji
  nieko nekeitė, tai irgi parašoma. Iki šiol brangiausia pakopa visiškai
  tylėjo: iš išorės nebuvo galima žinoti, ar jos apskritai klausta.

  Kam reikia tikslesnės informacijos, ties „Nustatymai → DI“ įjungia
  *Kiekvieną DI užklausą įrašyti į žurnalą*. Tuomet žurnalo failas
  kiekvienai užklausai fiksuoja dydį, trukmę ir rastų atvejų skaičių, taip
  pat laukimo laiką dėl priešingos pusės kiekio ribos. Šalia esantis
  mygtukas „Rodyti žurnalo failą“ atveria aplanką – jis yra programos
  duomenų kataloge, kuris „Windows“ sistemoje yra paslėptas ir kurio
  savaime niekas nesuras. Faile yra tik dydžiai, niekada tekstas iš jūsų
  dokumentų.

- **Maskuro atpažįsta, kai jūsų DI paslauga riboja užklausų skaičių.**
  Talpinamos paslaugos dažnai leidžia tik kelias užklausas per minutę –
  keturios nėra retenybė. Perteklinės neatmetamos, bet turi laukti, ir
  dviejų sekundžių atsakymas virsta keturiasdešimčia. Iki šiol tai atrodė
  taip, lyg modelis būtų lėtas. Dabar Maskuro nuskaito ribą iš paslaugos
  atsakymo, nebesiunčia daugiau vienalaikių užklausų, nei priimama, nurodo
  ribą ties „Tikrinti ryšį“ ir įtraukia ją į trukmės įvertį.

- **Peržiūra naudoja jūsų Word, Excel ir PowerPoint – ir dėl to yra maždaug
  šešis kartus greitesnė.** Iki šiol reikėjo LibreOffice, kurio nėra
  daugumoje biuro kompiuterių; kas jo neturėjo, matė mygtuką, kuris
  reikalavo svetimos programos diegimo. Dabar: jei įdiegtas Microsoft
  Office, jis naudojamas savaime – be konfigūravimo, be atsisiuntimo, be
  jokio jūsų varnelės. LibreOffice lieka antrasis kelias, o su OpenDocument
  failais – net pirmasis; jei vienas nepavyksta, bandomas kitas.

  Skirtumas labiausiai jaučiamas dirbant: po kiekvieno pakeitimo puslapis
  perrenkamas iš naujo, ir per Office tai kainuoja maždaug pusę sekundės
  vietoj trijų. Pirmoji dokumento peržiūra vis dar trunka kelias sekundes,
  po to seka jūsų veiksmus be laukimo.

  Jūsų paties atidarytas Word nepaliečiamas: Maskuro paleidžia savo,
  nematomą sesiją, atidaro failą tik skaitymui, išjungia makrokomandas ir
  viską vėl uždaro, kai tik taisymo langas užsidaro. Slaptažodžiu apsaugoti
  failai atmetami, o ne palikti kaboti nematomame dialoge.

- **Pirminė sąranka dabar taip pat klausia apie veidus, kodus ir parašus –
  ir viską trūkstamą pakrauna vienu ypu.** Šalia išplėstinio aptikimo
  pirmajame puslapyje yra trys paveikslėlių jungikliai: neatpažįstamai
  padaryti veidų sritis, neatpažįstamai padaryti brūkšninius ir QR kodus,
  juodinti ranka rašytus parašus PDF puslapiuose. PDF riba pažymėta prie
  varnelės matomai; Office failai automatiškai nėra tikrinami dėl parašų.
  Po varnelėmis parašyta, kiek megabaitų kainuoja paspaudimas „Toliau“.
  Krovimas tada vyksta **viename** lange su **viena** bendra pažangos
  juosta, o ne keliuose languose iš eilės; nutraukimas baigia visą
  procesą ir nepalieka nieko pusiau baigto. Kas nieko iš to nenori, nuima
  varneles – tuomet niekas nekraunama.

- **Peržiūrą galima retinti pagal tikrinimo poreikį ir suskleisti pagal
  rūšį.** Virš sąrašo yra slankiklis *Slėpti gerai pagrįstus*: kuo toliau
  jis paslinktas dešinėn, tuo daugiau slepiama nuo žalios link raudonos;
  visiškai dešinėje lieka tik tai, ką programa numanė visiškai viena.
  Paspaudus rūšies antraštę ji suskleidžiama. Abu tai yra skaitymo
  pagalba, o ne pasirinkimas – kas paslėpta ar suskleista, lieka pažymėta
  ir pakeičiama; kiek tuo metu tokių reikšmių yra, parašyta po slankikliu.
  Trumpuose sąrašuose slankiklis nerodomas. Perjungimas į du stulpelius
  dabar taip pat išlaiko jungiklius *daugiau niekada*.

- **Paveikslėlių sąrašas gali savaime atsidaryti prieš kiekvieną
  paleidimą.** Kas nori spręsti dėl kiekvieno paveikslėlio atskirai, ties
  „Paveikslėliai“ įjungia naują varnelę *Prieš kiekvieną paleidimą
  nustatyti atskirai*. Sąrašas su peržiūra tada atsiranda valant savaime,
  užuot kiekvieną kartą patiems spaudus „Nustatyti atskirai …“; jei jį
  nutraukiate, valymas irgi nevyksta. Jei nė viename pasirinktame faile
  nėra paveikslėlio, nieko neatsiranda. Numatytoji varnelės būsena –
  išjungta.
- **Maskuro randa PDF puslapiuose ranka rašytus parašus ir pašalina juos
  iš pikselių.** Iki šiol parašas likdavo po išvalytu dokumentu – teksto
  atpažinimas skaito spausdintinį šriftą, o ko jis neskaito, tas
  nepakeičiama. Paieška yra atskiras jungiklis ir reikalauja aptikimo
  modelio, kuris pakraunamas vieną kartą.

  Ji, remiantis matavimais, randa maždaug 84 iš 100 parašų ir juos
  padengia apie keturiais penktadaliais. Tai pagalba, o ne pažadas: po
  kiekvieno paleidimo ataskaitoje parašyta, kiek jų rasta – ir tada, kai
  jų nebuvo nė vieno, nes tai gali reikšti, kad parašo nebuvo, arba kad
  jis buvo praleistas. 72 realiuose verslo puslapiuose be parašo nė
  vieno neišgalvojo.

  **Nupieštas** parašas randamas, bet nepašalinamas: jis sudarytas iš
  linijų, ne pikselių, o juosta virš jo būtų tik dengimas, po kuriuo
  linijos liktų. Tokios vietos suskaičiuojamos ir įvardijamos, kad
  jas būtų galima pačiam pajuodinti taisymo lange.

  Word, Excel, PowerPoint ir OpenDocument failai automatiškai
  netikrinami dėl parašų. Sąsaja, pirminė sąranka, modelio atsisiuntimas,
  komandinė eilutė ir žinynas dabar šią ribą nurodo aiškiai.

- **Vedlys dabar veda ir per peržiūrą – langą, kuriame priimate
  sprendimus.** Su pratybų dokumentu jis atsidaro savaime, net jei
  peržiūrą kitaip esate išjungę (jūsų nustatymas lieka nepakeistas).
  Paaiškinama, ką reiškia spalvos, kodėl kiekvienoje eilutėje tik vienas
  klausimas – ar čia išvis yra asmuo? – ir kam skirtas „daugiau niekada“.
  Prie spalvų dėmesys nukreipiamas į gerai pagrįstą eilutę, dažniausiai
  IBAN – žalią pavyzdį, kurį mini sakinys; po to į silpniausiai pagrįstą,
  ir čia leidžiama pačiam spustelėti tiesiog paaiškinimo metu: varnelė
  nuimama, reikšmė lieka dokumente. Prie ilgo sąrašo vedlio langas
  atsidaro didesnis, kad paaiškinimas neuždengtų eilučių. Jei langas
  atsidaro antrą kartą, vedlys taip pat pasako, kodėl – baigtas puslapis
  dar kartą perskaitomas kaip paveikslėlis, ir tada atsiranda fragmentų,
  panašių į vardą.

- **Redaktorius pirmą kartą atsidaro didelis.** Originalas, rezultatas,
  įrankių juosta ir radinių sąrašas stovi vienas šalia kito ir ankstesniame
  numatytajame dydyje turėjo per mažai vietos. Kas langą sutraukia
  mažesnį, kitą kartą gauna jį tokio pat dydžio – niekam nieko
  neprimetama.

- **Dvigubas spustelėjimas ant pakaitalo lauko jį grąžina atgal** – Word,
  Excel, PowerPoint, OpenDocument, tekste, el. laiške ir HTML. O kas
  nuveda pelę per kelis pakaitalo laukus ir pasirenka „Grąžinti
  pasirinkimą“, grąžina visus juose esančius iš karto. Nebereikia taikliai
  pataikyti į laužtinį skliaustelį. Pakaitalo laukai, kurie anonimizuojant
  žymi kelias skirtingas reikšmes, nuo to neapsaugomi – jie
  suskaičiuojami ir įvardijami, o ne spėjami.

- **Žinyne yra skyrius „Peržiūra prieš pakeitimą“.** Langas iš anksto
  įjungtas ir yra vienintelis, kuriame priimate sprendimą – iki šiol
  žinyne apie tai buvo tik šalutiniame sakinyje. Dabar parašyta, ką
  reiškia varnelė (ji galioja **kiekvienai** radimo vietai, ne tik
  išvardytai), kodėl kiekvienoje eilutėje reikia atsakyti tik į vieną
  klausimą, ką ilgam laikui reiškia „daugiau niekada“ ir kodėl langas
  PDF atveju gali atsidaryti antrą kartą. Visose aštuoniolikoje kalbų, o
  nustatymų sąraše jungiklis dabar taip pat nurodytas.

### Pakeista

- **Skydelis „Pakeistos reikšmės“ turi slankiklį virš spalvų, o mokymosi
  režimo ten daugiau nebėra.** Kai reikšmių daugiau nei aštuonios, virš
  sąrašo yra tas pats slankiklis kaip peržiūros lange: *Slėpti gerai
  pagrįstus* išretina rodinį iki to, ką tikrai verta patikrinti. Dokumente
  tai nieko nekeičia, ir kiek eilučių iš kiek rodoma, parašyta žemiau –
  paieškos laukas ir slankiklis skaičiuojami kartu. Varnelė *Mokymosi
  režimas* iš skydelio išnyko; ji ir toliau yra meniu *Įrankiai* ir
  įrankių juostoje.

- **Skydelis „Pakeistos reikšmės“ dabar rodo tas pačias spalvas kaip
  dokumentas.** Kiekviena jo eilutė padengta taip pat, kaip vieta
  dokumente ir kaip reikšmė peržiūroje: raudona reiškia „numanyta
  vienintele programos nuomone, čia verta pirmiausia dar kartą pažiūrėti“,
  žalia – „atpažinta pagal pavadintą šabloną“. Kiekvienoje rūšyje
  neaiškiausia stovi viršuje – taigi sąrašą peržiūrite iš viršaus žemyn ir
  svarbiausią dalyką matote pirmiausia. Iki šiol viskas ten buvo vienodai
  šviesu ir surikiuota abėcėlės tvarka.

- **Mokymosi režimas iš gamyklos yra išjungtas.** Po pataisymo taisymo
  lange programa iki šiol savaime klausdavo, ar iš to turi tapti sava
  taisyklė. Šis klausimas iškyla darbo viduryje; kas jo neužsakė, jį
  suvokia kaip pertrūkį. Kas nori tų taisyklių, įjungia mygtuką *Mokymosi
  režimas* įrankių juostoje – tada pasirinkimas galioja nuolat, abiem
  kryptimis.

### Sutvarkyta

- **Eksportuoti taisyklių failai dabar aiškiai pažymimi kaip saugotini.**
  Juose gali būti aiškiatekstiniai savi terminai ir išimtys; be to, faile
  gali būti maišos druska (hash druska), kuria patvirtinamos numanomos
  reikšmės. Todėl sėkmingas eksportavimas dabar rodo įspėjimą ir ragina
  saugoti failą bei perduoti jį tik sąmoningai teisėtiems gavėjams.

- **Paskutinė saugumo patikra nebesulaiko išvalytų biuro failų dėl jų
  pačių pakaitalo laukų.** Rūšies santrumpa, pvz., „SVNR“, stovi ir
  `[SVNR1]`; iki šiol tai buvo laikoma tariamu aiškiateksčio likučiu ir
  paruoštas failas buvo atmetamas. Kartu telefono numeriai ir IBAN dabar
  ištaisomi ir ten, kur Office tą pačią reikšmę be matomų tarpų laiko
  nuorodoje ar įterptame faile.

- **Word, Excel, PowerPoint ir OpenDocument nebepalieka vėlai aptiktos
  lauko kopijos.** Kai reikšmė pirmą kartą atpažįstama papildomoje saugykloje
  ar įterptame biuro faile, siauras pakartotinis perėjimas sutvarko ir
  anksčiau perskaitytas matomas bei paslėptas kopijas. Jau sukurti
  nuorodų pakaitalo laukai tuo metu antrą kartą nepakeičiami.

- **Grąžinant atgal vieną Word išskleidžiamąjį sąrašą, kaimyninis
  pasirinkimas daugiau nebegrįžta nepaklaustas.** Visas originalus
  pastraipos tekstas perimamas tik tada, kai ir jo atributuose nebelieka
  atvirų pakaitalo laukų.

- **Prastai įskaitomi skenavimai praranda mažiau tarpusavyje susijusių
  duomenų.** Alternatyvus OCR skaitymas su kreipiniu ir dviejų dalių vardu
  išlieka; gatvės fragmentas, namo numeris ir pašto kodas su miestu drauge
  saugo visą adreso eilutę, net jei ji suskyla į gretimus OCR blokus.
  Sąskaitų ir prekių laukai bei renginių eilutės šalia dėl to neįtraukiami.
  Po žodžio „gimęs“ (geboren) į kelis OCR žodžius ir skyrybos ženklus
  suskilusi galiojanti data taip pat visiškai padaroma neatpažįstama.

- **Sėkmės konfeti dabar matomas automatiškai atsidarant redaktoriui.**
  Blizgučiai purškiami tiesiai iš mygtuko *Išvalyti*, o ne
  lyja nuo viršutinio lango krašto. Redaktorius laukia tik pirmojo,
  850 milisekundžių trukmės purškimo ir tada atsidaro automatiškai; be
  įjungto konfeti vėlinimo, kaip ir anksčiau, nėra.

- **Puslapių skaitiklis ir mastelio juosta pervedus pelę per peržiūros
  piktogramas daugiau nešokinėja pirmyn atgal.** Qt iš naujo paskirstydavo
  laisvą būsenos juostos vietą vos ten pasirodydavo simbolio užuomina.
  Dabar abi valdymo grupės, pelei užvedus, išlaiko natūralų plotį ir
  fiksuotą vietą.

- **Prijungto DI serverio greičio matavimas visada nepavykdavo** – kiekviename
  serveryje, nuo tada, kai atsirado sava DI. Ji klausdavo su siaura
  atsakymo riba ir po to bandydavo skaityti dėl to nutrauktą atsakymą; tai
  turėjo nepavykti, ir buvo išsaugoma „neišmatuota“. Pasekmes buvo matyti
  visur: trukmės įvertis skaičiavo jūsų serverį pagal pridedamo modelio
  greitį biuro kompiuteryje, o nustatymuose nuolat stovėjo, kad greitis
  dar neišmatuotas. Dabar matuojama pagal serverio sukurtą kiekį, o ne
  pagal jo atsakymo turinį.

- **„Maksimalus aptikimas (DI) – lėta“ buvo rodoma ir tada, kai tai
  netiko.** Antraštė ir užuomina aprašė pridedamą modelį biuro kompiuteryje –
  „kalbos modelis šiame kompiuteryje“, „didelių dokumentų atveju iki
  valandos“. Kas prijungė savo DI serverį, skaitė dvi klaidingas
  detales: skaičiuojama ne jo kompiuteryje, ir atsakoma per sekundes, o ne
  valandas. Dabar abi detalės gaunamos iš matavimo. Jei jo nėra, programa
  nebeteigia nieko, o sako, kad matavimo dar nebuvo.

- **Grąžinimas dabar veikia ir pažymėtai sričiai.** Kas pelės pavesdavo per
  kelis pakaitalo laukus ir norėdavo paspausti *Grąžinti pasirinkimą*,
  rasdavo mygtuką pilkos spalvos: jis įsijungdavo tik tada, kai žymėjimas
  buvo **tiksliai** vienas pakaitalo laukas – nuvestas per pastraipą jis
  toks niekada nebūna. Kelias iki to jau egzistavo, tik niekas iki jo
  neprieidavo. Dabar užtenka pažymėti sritį; visi joje esantys pakaitalo
  laukai grįžta vienu ypu.

- **Grąžinimas užstrigdavo, kai buvo atverta palyginimo lupa.** Lupa
  įsimena vietą po pelės žymekliu, kad galėtų sekti originale. Iš naujo
  įkeliant po grąžinimo ji grąžindavo šią vietą tokia forma, su kuria
  teksto rodinys nieko negalėjo padaryti – o kadangi tokia klaida
  sąsajos viduryje baigia programos darbą, iš grąžinimo tapdavo lūžis.
  Lupa pagal numatytuosius nustatymus atvira, tad tai paveikdavo įprastą
  kelią.

- **Po grąžinimo rodinys daugiau nešoka į dokumento pradžią.** Ilgesniame
  rašte po kiekvieno veiksmo dingdavo vieta, kurioje ką tik dirbote. Dabar
  lieka viršuje ta pastraipa, kuri prieš tai buvo viršuje.

- **Be LibreOffice peržiūra dabar sako, iš kur tai kyla, o ne tik trūksta.**
  Abu mygtukai *Peržiūra* ir *Juodinti kaip PDF* buvo užrakinti ir
  paaiškinime nurodydavo tik tai, kad LibreOffice nerastas; kelio ten
  programoje niekur nebuvo. Paspaudus dabar atsidaro nuoroda su keliu iki
  nemokamos, atvirojo kodo LibreOffice. Žinyne ir DUK ši vieta buvo
  klaidinga – jie skelbė papildomą įskiepį atsisiuntimui, kurio programa
  nesiūlo.

- **Prieš pateikiant paruoštas failas dar kartą pilnai peiliuojamas
  (perieškomas) – dabar ir Word, Excel, PowerPoint, LibreOffice, el.
  laiške, HTML ir tekste.** Iki šiol šį paskutinį žvilgsnį turėjo tik PDF.
  Visos ankstesnės patikros žiūri į vietą, kurią prieš tai kažkas
  įvardijo; saugyklos, apie kurią niekas nepagalvojo, dėl to niekas ir
  netikrina. Pabaigoje Maskuro dabar tiesiog paieško visko, kas buvo
  pakeista – kiekvienoje pakuotės dalyje. Jei kas nors lieka, rezultatas
  **nesukuriamas**, ir pranešime nurodoma reikšmė. Failas, laikomas
  išvalytu, yra blogiau nei jokio failo.

- **Pavadinimai, esantys `<script>` ir `<style>` viduje, dabar
  pranešami.** Abu lieka nepaliesti – ten yra programos tekstas, o
  pakeitimas viduryje identifikatoriaus paverstų tinklalapį sugadintu
  tinklalapiu. Bet iki šiol apie tai nebuvo pranešama, ir tai buvo
  klaida: stiliaus taisyklė `content: "Anna Musterfrau"` gavėjui
  **matoma** ekrane, o rezultate ji likdavo, o programa skelbdavo puslapį
  išvalytu.

- **Nustatymuose vėl galima pakrauti ir pašalinti papildomus modelius.**
  Mygtukas šalia „Išplėstinis aptikimas“ ir „Maksimalus aptikimas (DI)“
  paspaudus baigdavo klaidos pranešimo lange, užuot atsiuntęs modelį.
  Antrasis kelias – aptikimo varnelė, kuri savaime paklausia modelio –
  tuo niekada nebuvo paveiktas.

- **Vardai, esantys lapo ir srities pavadinimuose lentelėje, dabar
  pranešami.** Lapo pavadinimas rodomas apačioje esančiame skirtuke, o
  pavadintos srities pavadinimas – pavadinimų lauke ir kiekvienoje
  formulėje, kuri jį naudoja. Abu ir toliau nekeičiami – formulės
  nurodo per juos, o knyga su nuorodų klaidomis niekam nepadeda – bet
  dabar tai parašoma. Iki šiol pranešimas buvo tik apie Excel knygos
  lapo pavadinimą: pavadinta sritis „Bezuege_Brunnthaler“ išeidavo tyliai,
  o LibreOffice lentelėje programa tylėdavo visai. Lapas „Notizen
  Ortner“ tokiu būdu buvo laikomas išvalytu, ir pirmasis gavėjo žvilgsnis
  krisdavo ant vardo.

  Pranešama tik apie tai, kas iš tikrųjų veda prie asmens: žodis, kuris
  toje pačioje knygoje ir taip buvo pakeistas, arba radinys, kuris
  parenkamas iš kelių žodžių. Vienišas žodis kaip „Zustaendig“ ar
  „Bezug_Umsatz“ įspėjimo daugiau nesukelia – anksčiau būtų sukėlęs, o
  įspėjimą, kuris pasirodo kas antroje knygoje, po trečio karto niekas
  nebeskaito.

- **„Grąžinti originalą“ dabar tikrai grąžina viską.** Kai kuriuose
  dokumentuose po to trūkdavo pavienių ženklų – iš „Seestraße 14“
  pasidarydavo „Seestraße 4“, iš „An:“ – „An“, iš „nordlicht-planung“ –
  „nordlicht planung“ – ir kai kurios eilutės iš viso negrįždavo. Būtent
  tose vietose po to nieko nebuvo galima pažymėti pele ir nieko
  pajuodinti: tekstas popieriuje buvo, bet programa jo nebepažino.
  Paveikti buvo siauri ženklai – vienetas, dvitaškis, brūkšnys – dokumentuose,
  kurie kiekvieną ženklą sudeda atskirai; pratybų dokumentas yra vienas iš
  jų.

- **O tie patys dokumentai valant daugiau nebeverčiami paveikslėliu.**
  Kadangi toks ženklas likdavo, papildoma patikra praneša apie likutį ir
  puslapis atsargumo dėlei buvo perpiešiamas rastro pavidalu. Tekstas ant
  jo po to buvo tik nuotrauka: nebeieškomas, nebepažymimas, didesnės
  apimties faile. Pratybų dokumentas dabar abiejuose puslapiuose lieka
  tikru tekstu.

- **Spalvotos žymės nebelieka virš grąžinto teksto.** Kas atšaukdavo
  pakeitimą, toliau matydavo spalvotą stačiakampį virš atkurto žodžio –
  jis teigė „čia kažkas buvo pašalinta“, nors ten vėl stovėjo originalas.

- **Juosta daugiau neišduoda, koks ilgas žodis buvo po ja.** Juodinant
  trumpose eilutėse juosta dabar dengia **visą** eilutę – adreso bloką,
  antraštinius duomenis, siaurą lentelės langelį. Jei visa eilutė
  netelpa (įprasta trijų stulpelių lentelės eilutė), lieka prie lauko;
  tekstinėje eilutėje lieka tiksliai pagal žodį, kitaip vardas sakinio
  viduryje pajuodintų visą sakinį. O viena po kitos stovinčios juostos
  tampa **vienodo ilgio**: adreso bloke kiekvienoje eilutėje yra
  reikšmė, ir trys skirtingo ilgio juostos toliau išduodavo, kokio ilgio
  eilutės buvo. Jos plečiasi tik tiek, kiek popieriuje yra laisvos vietos –
  prieš gretimą stulpelį juosta baigiasi.

- **„Visa eilutė“ dabar tikrai pajuodina visą eilutę.** Iki šiol juosta
  baigdavosi ties kitu didesniu tarpu – taigi lauko pabaigoje. Tekste tai
  nebuvo pastebima, ten laukas yra eilutė; antraštiniuose duomenyse ir
  lentelėse – taip: iš „Name: Anna Musterfrau   Abteilung: Vertrieb“
  gaudavosi juosta, kuri baigdavosi tiksliai ties paskutine vardo raide –
  taip jo ilgis vėl likdavo matomas ant lapo. Juosta dabar eina nuo
  pirmojo iki paskutinio eilutės žodžio ir apima gretimus stulpelius. Kas
  nori pataikyti tik į reikšmę, renkasi „Žodžiai“; automatika ir toliau
  juodina pagal lauką.

- **Prieš pateikiant, paruoštas failas dar kartą pilnai peiliuojamas.**
  Visos ankstesnės patikros žiūri į vietą, kurią prieš tai kažkas
  įvardijo – puslapio tekstą, radinio stačiakampį, paveikslėlio plotą. Bet
  PDF turi daugiau saugyklų, nei gali aprėpti sąrašas: anotacijas,
  formos reikšmes, žymes, dokumento informaciją, prisegtus failus,
  JavaScript. Pabaigoje Maskuro dabar tiesiog perieško parašytą failą dėl
  visko, ką pakeitė – visur, išskyrus puslapio tekste, kur tas pats
  tekstas gali stovėti ir teisėtai. Jei kas nors lieka, rezultatas
  **nesukuriamas**, ir pranešime nurodoma reikšmė. Dokumentas, laikomas
  išvalytu, yra blogiau nei jokio dokumento.

- **Kas nebuvo patikrinta, daugiau nelaikoma patikrinta.** Trimis
  keliais nepavykusi papildoma patikra iki šiol atrodė kaip švarus
  rezultatas. Puslapis, kurio teksto sluoksnio nepavyko perskaityti,
  buvo laikomas ypač švariu – juk ten nieko nerasta; dabar jis
  perpiešiamas rastro pavidalu. Jei puslapio su likusia radimo vieta
  nepavykdavo alternatyviai perpiešti, jis buvo tyliai pateikiamas; dabar
  valymas geriau nutraukiamas. O taisymo lango kontrolinis patikrinimas
  po savo klaidos praneša „nieko neliko“ – lange to negalima atskirti nuo
  to, kad viskas buvo pašalinta; dabar rodomas įspėjimas su mygtuku
  „Perpiešti puslapį“.

- **„Atkurti į numatytuosius nustatymus“ daugumos nustatymų iš tikrųjų
  neatkurdavo.** Devynios iš dvidešimt dviejų varnelių po veiksmo likdavo
  nepakeistos – tarp jų peržiūra, „Išvalytus failus po to atverti“,
  taisymo langas, tiesioginis atidėjimas ir abi atnaujinimo varnelės.
  Išsaugotas failas buvo tuščias, bet langas laikė senas reikšmes ir jas
  vėl įrašydavo kitą kartą paspaudus. Dabar grįžta kiekviena varnelė, o
  kartu su ja išnyksta žyma „pakeista“.
- **„Kiekvienam valymui automatiškai išsaugoti patikros ataskaitą“ rodė
  įjungta, bet buvo išjungta.** Po atkūrimo varnelė likdavo pažymėta,
  nors reikšmė buvo ištrinta – ataskaita nebebuvo kuriama, ir niekas apie
  tai nesignalizavo. Tas pats galiojo patikros žurnalui ir savai
  ekrano įrašymo funkcijai; jų klavišų kombinacija atkuriant dabar taip
  pat iškart teisingai įjungiama ar išjungiama.

- **Vienos eilutės juostos dabar atrodo vienodai.** Iki šiol kiekviena
  radimo vieta atsinešdavo savo juostą, o jos aukštis priklausydavo nuo
  rasto žodžio šrifto. Eilutėje su antrašte ir reikšme skirtingo dydžio
  šriftu dėl to šalia stovėdavo storas ir plonas brūkšnys su pasislinkusiais
  kraštais, o kur dvi radimo vietas skirdavo tik tarpas, virš jo likdavo
  šviesus plyšys. Tos pačios eilutės juostos dabar turi tas pačias
  viršutinę ir apatinę kraštines, o kas skiriama tik tarpu, tampa viena
  juosta. Kas turi likti tarp dviejų radimo vietų – kablelis po vardo,
  antraštė, suma – toliau jas skiria. Galioja tiek surinktiems
  puslapiams, tiek skenavimams.

- **Skirtukai po „Apie šią programą“ vėl prasideda nuo viršaus.**
  Duomenų apsauga, licencijos sąlygos ir licencijos nuorodos atsidarydavo
  teksto viduryje – norintys perskaityti pirmiausia turėdavo pervilkti
  iki pat viršaus, kad matytų pirmąją eilutę.

- **Pieštukas nebeatveria antro redaktoriaus lango, o iškelia į priekį
  esamą.** Iki šiol kiekvieną kartą paspaudus atsirasdavo naujas. Langas
  neturi savo įrašo užduočių juostoje – kas jį sumažindavo, prie jo
  nebegalėdavo prieiti ir spausdavo dar kartą; atkuriant pagrindinį langą
  visi susikaupę langai iškildavo iš karto. Dabar tolesni dokumentai
  patenka į atviro lango skirtukų juostą, ir dokumentas, kuris ten jau
  yra, antro skirtuko negauna.

- **„Išplėstinis aptikimas“ nebežymimas kaip „pakeista“, kol trūksta jo
  modelio.** Pristatoma įjungta, bet be pakraunamo modelio ji tokia
  negali būti – nustatymuose eilutė dėl to bet kuriame ką tik nustatytame
  kompiuteryje rodėsi kaip pakeista, nors niekas jos nelietė. Kodėl
  varnelė išjungta, dabar sako vien jos pati antraštė: „Modelis dar
  nepakrautas“.

- **Pristatymo juostelė Office ir teksto failuose aiškindavo PDF
  drobę.** Ten buvo parašyta „paspaudus žodį jis pajuodinamas“ – bet
  Word faile paspaudimas nieko nepajuodina, ten pažymima, o po to
  paspaudžiamas mygtukas. Dabar ji sako, kas galioja atitinkamame
  rodinyje.
- **Įrankių juosta teksto rodinyje buvo užversta antraštėmis.**
  „Pakeisti pasirinkimą“, „Pajuodinti pasirinkimą“, „Grąžinti
  pasirinkimą“, „Peržiūra“ ir „Juodinti kaip PDF“ dabar rodomos kaip
  piktogramos – kaip jų giminaitės PDF faile. Jų pavadinimai lieka
  paaiškinime ir meniu.
- **Ctrl+pelės ratukas palyginimo lupoje nejudino jos mastelio
  slankiklio.** Šriftas didėdavo, o slankiklis ir šalia esantis
  procentinis skaičius toliau rodydavo senąją būseną.
- **Aktualizacijos diegimo programa nepersikeldavo į priekį** – reikėdavo
  ją pirmiausia paspausti užduočių juostoje (tik Windows).
- **Metų skaičius eilutės pradžioje buvo laikomas Austrijos pašto
  kodu.** Gyvenimo aprašyme iš „2020 Verkaufsstrategien“ atsirasdavo
  pakaitalo laukas – visa eilutė dingdavo. Keturženklis skaičius tarp
  1900 ir 2099 dabar reikalauja antro adreso signalo: gatvės virš jo,
  lauko žodžio prieš jį, šalies kodo ar žinomo vietovės pavadinimo.
  Adreso blokai tai turi; metų stulpeliai – ne.
- **Mėnesio ir metų pora buvo laikoma telefono numeriu.** Iš „Seit
  08.2010 123-Verkauft GmbH“ atsirasdavo „telefono numeris“ – mėnuo,
  metai ir pirmieji po jų einantys įmonės pavadinimo skaitmenys.
- **Ataskaitoje buvo parašyta „patikrinta teksto atpažinimu“ ir
  nutylima, ko ji neperskaito.** Jei paveikslėliai išsaugomi, dabar šalia
  parašyta, kad ranka rašytas tekstas juose nerandamas – parašas ar ranka
  įrašytas vardas lieka nepaliestas. Iki šiol šis sakinys buvo tik prie
  nuskenuotų puslapių; įprastas PDF su įterptu parašu apie tai negaudavo
  nė žodžio.

- **Žymiklis ant užtamsinto vaizdo fono stovėjo kairiajame savo juostos
  krašte.** Kai reikšmė randama vaizde – pavyzdžiui, įrašytas vardas
  šalia nuskenuoto parašo –, vaizdo sritis turi būti užtamsinta per visą
  plotį. Trumpesnis žymiklis šalia palikdavo plikai juodą plotą, kuris
  atrodė kaip du veiksmai. Dabar jis stovi juostos viduryje.

## 0.10.41-alpha.20260826 – 2026 m. rugpjūčio 26 d.

### Nauja

- **Pasibaigus bandomajam laikotarpiui langas kartą per paleidimą primena
  apie licenciją.** Jis pasirodo penkios minutės po paleidimo – ne iš karto,
  kad niekam netrukdytų prieš pirmą veiksmą – ir palaukia, kol vyksta
  valymas. Iš ten veda kelias į pirkimą ir kelias jau nupirktam raktui
  įvesti; „Vėliau" jį uždaro, kai tik baigiasi penkios sekundės mygtuke.
  Nieko neužrakinama: nemokama pakopa veikia toliau kaip ir anksčiau.

- **Laukimo laikas prieš paleidimą nemokamoje pakopoje dabar trunka
  dešimt, o ne trisdešimt sekundžių.** Jis turi priminti apie licenciją, o
  ne stabdyti darbą.

- **Visi trys nurodymai apie licenciją dabar atrodo vienodai.** Laukimo
  laikas, priminimas paskutinėmis bandymo dienomis ir nuoroda po bandomojo
  laikotarpio turi tą pačią juostą, tą pačią sandarą ir tuos pačius
  mygtukus; likęs laikas dabar rodomas mygtuke, o ne dideliu skaičiumi
  šalia.

- **Radimo sąrašas peržiūroje vėl stovi vienas po kito.** Nuo devynių
  reikšmių jis būdavo dviejų stulpelių; peržiūrint akis tada šokinėja tarp
  dviejų takelių, o čia sprendžiama eilutė po eilutės. Kas mėgsta du
  takelius, juos vėl įjungia apačioje kairėje lango kampe – pasirinkimas
  įsimenamas, o perjungiant jau atžymėtos reikšmės lieka atžymėtos.

- **Dirbtinio intelekto pakopa dabar atvira kiekvienam, kas prijungia
  savo DI serverį.** „Nustatymai → DI" turi viską tam: prijungimą, ką DI
  gali daryti, ką jam pavedama daryti – ir virš to jungiklį pakopai kartu
  su kryžmine patikra, kai tik įrašytas serveris. Kalbos modelis, kuris
  skaičiuoja pačioje darbo vietoje, lieka sulaikytas: dešimčiai puslapių
  jam reikia kelių minučių, taigi jis netinka kasdieniam darbui.

- **Galima prijungti savą DI.** Vietoj pridedamo kalbos modelio gali
  atsakyti didesnis modelis kitame kompiuteryje – vidiniame serveryje arba
  darbo stotyje su galinga grafikos plokšte. Reikalaujama paslaugos su
  OpenAI suderinama sąsaja (Ollama, LM Studio, llama.cpp-server, vLLM,
  LocalAI); ji nustatoma po „Nustatymai → Sava DI" kartu su ryšio
  patikra, kuri iš tikrųjų užklausia modelį, matuoja greitį ir nustato
  galimą atsakymo formą. Keli teksto fragmentai tuo pačiu apdorojami
  vienu metu, o ne vienas po kito.

- **Ką DI gali daryti ir ką jam pavedama daryti, dabar nustatoma.** Trys
  jungikliai sprendžia dėl ribinių atvejų tikrinimo, savarankiškos
  paieškos ir paieškos rišliame tekste; nurodymas modeliui rodomas
  pažodžiui, gali būti papildytas vidiniais terminais ir vienu mygtuku
  grąžintas į numatytąją reikšmę.

- **Jei tekstas dėl to palieka savo tinklą, prieš kiekvieną paleidimą
  įspėjama.** Maskuro pagal adresą atpažįsta, ar DI serveris yra viduje, ir
  žinomą tiekėją įvardija vardu. Įspėjimą galima išjungti, bet tik prieš
  tai aiškiai patvirtinus, kad esate įgalioti šiam perdavimui, ir tik
  būtent šiam adresui. Pačiam procesui tai nieko nekeičia: perdavimas ir
  toliau lieka žurnale bei kiekvieno failo patikros ataskaitoje.
  Komandinėje eilutėje neklausiama, o sustabdoma – ten reikia
  `--ki-auswaerts-erlauben`.

- **Peržiūra prieš keitimą pagal numatytuosius naujų nustatymų dabar
  aktyvi ir galioja sąmoningai išvalytam mainų srities turiniui bei
  tekstui ir vaizdams, kurie įklijuojami į programą.** Dokumentų
  paketuose ir toliau pasirodo lygiai viena peržiūra kiekvienam dokumentui
  su visais puslapiais; tylus greitas trumpų kopijų valymas sąmoningai
  neatidaro lango.

- **Radiniai peržiūroje įjungiami ir išjungiami spustelėjus visą spalvotą
  eilutę.** Varnelė dabar didelė ir kontrastinga; papildomai būsenos
  laukelis rodo „Keisti" arba perbrauktą „Keisti", kad pasirinktos ir
  atžymėtos reikšmės iš karto skirtųsi net ant tamsių pasitikėjimo spalvų.

- **Ir PDF failai su matomu saugumo kryžminiu žvilgsniu peržiūrą atidaro
  tik kartą per dokumentą.** Atžymėti terminai lieka atžymėti vėlesniam
  puslapio liudytojui; jo patikra vyksta toliau, nepertraukiant to paties
  paleidimo antru dialogu.

- **Pakaitos žodžiai taisymo redaktoriuje atrodo vienodai ir rastruotuose
  puslapiuose.** Jei raudonas žymiklis yra pikseliuose, o ne PDF teksto
  sluoksnyje, jis dabar vis tiek gauna tą patį pagal pasitikėjimą nuspalvintą
  foną kaip ir įprastas PDF teksto žymiklis.

- **Jau peržiūra prieš keitimą rodo rastų terminų patikros poreikį.**
  Kiekviena eilutė turi tą pačią raudona–oranžinė–žalia spalvą kaip vėliau
  pakaitalas redaktoriuje. Kategorijos viduje mažas patikimumas ir raudoni
  galimai klaidingi kandidatai stovi viršuje, stiprūs žali įrodymai –
  apačioje; lygiavertės vertės lieka abėcėline tvarka. Jei ta pati reikšmė
  gaunama iš kelių radimo vietų, atsargumo dėlei skaičiuojamas
  abejotiniausias jų įvertinimas. Neįvertinti ypatingi atvejai stovi
  neutraliai geltoni tarp raudonos ir oranžinės.

- **Rezultatą dabar galima kopijuoti kaip failą tiesiogiai iš taisymo
  redaktoriaus.** „Kopijuoti rezultatą" perkelia dabartinę išvalytą
  versiją į mainų sritį, neuždarant redaktoriaus ir nereikia iš naujo
  ieškoti failo pagrindiniame sąraše. Prie dar neišsaugoto rankinio
  taisymo prieš tai automatiškai vyksta visas saugus išsaugojimo kelias;
  „Kopijuoti vaizdą" lieka kaip atskira funkcija grynam pikselių turiniui.

- **Pakeisti žodžiai redaktoriuje iš karto rodo, ką reikėtų patikrinti
  pirmiausia.** Grynas kalbos modelio spėjimas yra raudonas, net jei spaCy
  tam bendrai praneša 85 procentus. Kiti nepagrįsti modelio sprendimai
  lieka daugiausia oranžiniai; stiprūs įvardyti įrodymai gali tapti
  žali. Rankinis darbas ir senos priskirtys be įvertinamo balo lieka
  neutraliai geltoni. Ir automatinės užtamsinimo juostos redaktoriaus
  peržiūroje turi šias spalvas – dabar ir tada, kai juosta yra rastruoto
  PDF puslapio dalis. Tam priskirtis turi tikti, o ankstesnis žodžio
  langelis turi būti įrodomai vientisai juodas; įprastas paryškintas
  šriftas nespalvinamas. Išsaugotame PDF faile visos juostos lieka
  nepakitusios, vientisai juodos.

- **Kas peržiūroje atžymima, gali būti įsimenama ilgam.** Kur nuimate
  varnelę, sakote: čia atpažinimas suklydo. Iki šiol tai galiojo tik
  vienam dokumentui. Dabar prie eilutės atsiranda jungiklis „niekada
  daugiau"; paspaudus reikšmė ilgam patenka į sąrašą „Niekada nešalinti"
  ir toliau kiekviename dokumente laikoma nekenksminga. Po sąrašu
  parašyta, kas taps ilgalaikiu, prieš jums paspaudžiant „Keisti". Priešinga
  kryptis sąmoningai neįtraukta: kas kartą buvo rasta, tą atpažinimas
  ras vėl.

- **Mygtukas grąžina visus nustatymus į pristatymo būseną.** Jis stovi
  apačioje kairėje nustatymų lange ir prieš tai klausia. Jūsų failai,
  jūsų licencija, jūsų savos atpažinimo taisyklės ir automatinis
  paleidimas nepaliečiami; kas nurodyta jūsų administravimo, galioja
  toliau. Kiekvienas nustatymas, kuris skiriasi nuo pristatymo būsenos,
  papildomai turi žymą „pakeista" – taip iš karto matoma, kas buvo
  perstatyta.

### Pakeista

- **Rezultatas nebeįrašomas savaime – tik išsaugant.** Paleidimas iš lango
  savo išvalytą versiją pirmiausia rašo į laikiną vietą; failas
  „…_bereinigt" šalia originalo atsiranda tik paspaudus „Išsaugoti". Iki
  tol rezultatą galima peržiūrėti, taisyti ir kopijuoti. Kiekviena baigta
  eilutė tam turi išsaugojimo mygtuką, po sąrašu stovi „Išsaugoti visus", o
  redaktoriuje galioja Ctrl+S. Kas išvalo sąrašą ar užbaigia programą,
  klausiamas; ko niekas neišsaugo, tas ir niekur nelieka. „Rodyti aplanke"
  prieš išsaugant užrakinta – laikina vieta nėra tikslas, į kurį kas nors
  siunčiamas. Priskirčių failas išsaugant keliauja kartu.

  Nustatymuose po „Programa" „Rezultatus iš karto dėti šalia originalo"
  grąžina ankstesnį elgesį. Komandinė eilutė, aplankų stebėjimas ir mainų
  srities sargas ir toliau iš karto įrašo – ten niekas neišsaugo rankiniu
  būdu.

- **Taisymo redaktoriaus įrankių juosta sutvarkyta.** Mokymosi veiksena
  dabar stovi dešiniajame gale prie palyginimo didinamojo stiklo ir
  „Pakeistos reikšmės" – trys jungikliai, įjungiantys ir išjungiantys
  veikseną, dabar stovi kartu. „Taikyti visiems puslapiams" perkeltas prie
  trijų užtamsinimo formų, nes tik ten jis ką nors veikia. „Kopijuoti
  rezultatą", „Failas – Atstatyti" ir „Taikyti visiems puslapiams" apsieina
  be užrašo; jų pavadinimas ir toliau stovi paaiškinime ir meniu. Tarp
  „Keisti" ir „Grąžinti originalą" yra skiriamoji linija: šie du yra
  priešingos kryptys ir šalia atrodė kaip to paties įrankio dvi
  atmainos.

- **„Kopijuoti rezultatą" ženklas dabar rodo dokumentą.** Du lapai su
  užlenktu kampu ir teksto eilutėmis vietoj dviejų vienodų lapų su mažu
  kampo rodykle. „Kopijuoti vaizdą" už tai turi vaizdo ženklą, kad abu
  be užrašo būtų atskiriami. Mygtukas „Kopijuoti" rezultatų sąraše rodo
  tą patį dokumento ženklą – jis įrašo tą patį failą.

- **Nustatymai surūšiuoti ir turi antraštes.** „Atpažinimas" dabar turi
  keturis skyrius: *Kas pašalinama*, *Kaip pakeičiama*, *Kaip kruopščiai
  ieškoma* ir *Prieš ir po paleidimo*. Veidų atpažinimas bei brūkšninis/QR
  kodų atpažinimas stovi prie vaizdų, kur jų ieškoma; „Programa" padalyta į
  *Rezultatų failai*, *Paleidžiant*, *Atnaujinimas*, *Rodinys* ir
  *Atsiliepimas mums*, o rezultato failo priedas stovi prie rezultatų
  failų, o ne tarp kalbos ir išvaizdos.

- **Išplėstinis atpažinimas gamykliškai įjungtas**, net prieš jo kalbos
  modelio įkėlimą. Anksčiau numatytoji reikšmė priklausė nuo modelio
  buvimo, ir ką tik sutvarkytas kompiuteris nuolat veikė silpnesnėje
  pakopoje. Diegimo langas modelį siūlo įkelti pirmajame puslapyje ir
  nurodo šalia kainą. Jei jo trūksta, varnelė tai ir toliau sako, o ne
  apsimeta pakopa, kuri neveikia.

- **Du terminų sąrašai dabar vadinasi taip, ką jie daro:** „Visada
  pašalinti" vietoj „Savi terminai" ir „Niekada nešalinti" vietoj
  „Išimtys".

- **Peržiūros langas aiškesnis.** Nuo devynių reikšmių jos stovi dviejuose
  stulpeliuose, eilutės žemesnės, o radimo vietų skaičius stovi tiesiai už
  termino, o ne dešiniajame krašte.

- **Taisymo redaktoriuje „Keisti" stovi prieš „Užtamsinti"** – įrankių
  juostoje, meniu „Įrankiai" ir dešiniojo pelės klavišo meniu puslapyje.
  Keitimas yra įprastas atvejis: žymiklį galima spustelėti ir grąžinti,
  juostą – ne.

- **Mažiau dvigubų mygtukų redaktoriuje.** „Išsaugoti kaip …" ir
  „Kopijuoti vaizdą" liko tik meniu „Failas", su įprastais klavišų
  deriniais. Juostoje lieka po vieną: „Išsaugoti" ir „Kopijuoti
  rezultatą" – kur išsaugoma, vis tiek rodo būsenos eilutė, ir ten tai
  galima pakeisti vienu spustelėjimu.

- **Mainų srities sargas pirmo paleidimo metu daugiau nebesiūlomas.** Jis
  įsikiša į kiekvieną sistemos kopijavimo veiksmą; kas programą mato
  pirmą kartą, to negali įvertinti. Nustatymuose jis ir toliau yra, ten su
  šalia esančia jam priklausančia sąlyga.

- **Šviesi išvaizda mažiau akina.** Lango fonas anksčiau buvo imamas iš
  atitinkamo sistemos stiliaus ir taip buvo vienintelis didelis plotas,
  kurio niekas nebuvo apsisprendęs – „Windows" sistemoje beveik baltas.
  Dabar jis yra pertraukta balta spalva, vienoda kiekvienoje sistemoje.

- **Apžvalginis vedimasis ir vadovas paaiškina spalvas.** Ką reiškia
  raudona, oranžinė, žalia ir geltona spalva už pakeisto žodžio, dabar
  aprašyta kaip atskiras taškas apžvalginiame vedimesi ir kaip pastraipa
  vadove – visose kalbų versijose.

### Ištaisyta

- **Vadovas ir DUK rodė žymiklius, kurių jau nebėra.** Nuo perėjimo prie
  trumposios formos Maskuro rašo `[NAM1]"; pagalboje ir toliau stovėjo
  `[NAME1]", ir sakinys „Numatytoji reikšmė yra `[NAME1]`" buvo tiesiog
  neteisingas. Septyniolikoje išverstų versijų papildomai stovėjo
  **vokiška** žymė vietoj savos – ispanų kalbos skaitytojas matė
  `[NAME1]", kur jo programa rašo `[NOMB1]". Taip pat rezultato failo
  priedas: ten visos versijos žadėjo `_bereinigt", nors programa sukuria
  `_limpiado", `_nettoyé" ar `_除去済み". Paveikta buvo ir be numerio forma
  (anoniminant viskas vadinasi `[NAM]", ne `[NAME]") bei iš reikšmės
  išvestas identifikatorius maišant.

- **Peržiūros langas pertraukia tik kartą per dokumentą – ir antrą kartą
  tik jei tikrai atsiranda kažkas naujo.** PDF failas skaitomas iš dviejų
  pusių: kartą iš turinio srauto ir galiausiai iš atvaizduoto, matomo
  puslapio. Anksčiau kiekviena iš jų klausdavo atskirai. Dabar galioja:
  kas nuspręsta pirmame lange, galioja toliau, ir reikšmės, kurios ten jau
  stovėjo, negrįžta. Jei baigtų puslapių vizualinė patikra vis tiek randa
  kažką, kas anksčiau niekur nestovėjo, tai jums vėl pateikiama – vien
  tik, be jau nuspręstų reikšmių.

- **Peržiūros langas dabar sako, pagal ką reikia spręsti.** Vietoj
  „Nuimti varnelę = reikšmė lieka" – kas parodo, ką varnelė *daro*, bet
  ne kada ją nuimti – ten parašyta: nuimkite varnelę visur, kur nėra
  asmens duomenų reikšmės; ten atpažinimas suklydo. Be to, kiekvienas
  langas nurodo patikros paleidimą, iš kurio kilo jo reikšmės.

- **Žymikliai visame dokumente atrodo vienodai.** Puslapiuose, kurie OCR
  keliu iš naujo sukuriami kaip vaizdo puslapiai, matomi žymikliai
  anksčiau būdavo rašomi rašomosios mašinėlės šriftu – „[PLZ4]" tada
  stovėjo platus ir su serifais šalia siauro to paties puslapio „[NAM1]".
  Dabar jie turi tą patį beserifinį šriftą kaip ir visur kitur ir taip
  pat nebedaromi platesni, nei buvo suplanuota talpinant. Nematomas
  paieškos sluoksnis išlaiko savo šriftą – jam reikia patikimų matmenų,
  ne išvaizdos.

- **Redaktoriaus įrankių juostoje nebėra dvigubų skiriamųjų linijų.** Kur
  visa įrankių grupė atidarytos failo rūšies neturi – PDF faile, pavyzdžiui,
  puslapio peržiūra ir atvaizdavimas –, iki šiol likdavo abi linijos
  aplink spragą.

- **Grąžinant retkarčiais nebelieka vien baltos vietos.** Jau tiksliai
  atkurtas originalo tekstas daugiau nebeuždengiamas baltai plačiu,
  suvestu jo pašalinto žymiklio langeliu. Esant mišriam teksto ir vaizdo
  grąžinimui, tekstas be to įterpiamas nematomai tik tada, jei puslapio
  vaizdas jau matomai turi būtent šią originalo būseną. Tai galioja
  rėmeliui, radimo skydeliui ir PDF prieduose.

- **„Grąžinti originalą" nebesiūlo be reikalo rastruoti puslapio.**
  Griežta likutinio teksto patikra ir toliau veikia užtamsinant ir
  keičiant. Grąžinant ji praleidžiama: ten originalo turinys sąmoningai
  grąžinamas, ir nepakitę kaimyniniai žodžiai išplėstame grąžinimo
  rėmelyje nebuvo valymo klaida, o klaidingas pavojaus signalas.

- **Apžvalginis vedimasis per redaktorių dabar „Keisti" ir „Grąžinti
  originalą" paaiškina kaip atskirus žingsnius.** Abu įrankiai
  paryškinami tiesiogiai juostoje ir aprašo, kad nutemptas rėmelis
  įterpia žymiklį arba grąžina pradinį šios vietos turinį iš šaltinio
  failo.

- **Ir šalims būdingi žymikliai dabar lieka ne ilgesni kaip keturi
  simboliai.** Šios rūšys anksčiau trūko centriniame santrumpų kataloge
  ir dėl to galėjo pasirodyti išrašytos, pvz., `[UMSATZSTEUER_ID1]".
  Nauji paleidimai dabar rašo `[UID1]"; visos automatiškai atpažįstamos
  vokiškos ir angliškos rūšys tuo pačiu lieka vienareikšmės. Net pačios
  apskaičiuotos kitų sąsajos kalbų santrumpos vienodo pavadinimo atveju
  daugiau neauga virš keturių simbolių. Savi taisyklių pavadinimai
  vadinami taip, kaip buvo įvesti, ir toliau nepakitę.

- **Keitimas dabar prieš užtamsindamas naudoja visą faktiškai laisvą
  eilutės vietą.** Ankstesnė griežta triguba pradinio žodžio pločio riba
  net beveik tuščiuose formos laukuose sukurdavo juostas. Ir matomo OCR
  kryžminio žvilgsnio radiniai su užimtu PDF tekstu dabar gauna
  įskaitomą žymiklį; juodi lieka gryni vaizdo, anotacijų ir vektoriniai
  turiniai, pasirinkta užtamsinimo veiksena bei tikri ankšti plotai, į
  kuriuos netelpa net vienareikšmė trumpa forma.

- **Jau matomas žymiklis saugumo rastravimo metu daugiau neperrašomas
  antrą kartą raudonai.** Rastravimas dabar esamą pakaitalą perima iš
  puslapio vaizdo ir sukuria tik nematomą paieškos kopiją. Jei saugumo
  juosta turi uždengti būtent šią vietą, atnaujinamas visas tikras
  žymiklio langelis, o ne tik jo trumpesnis pradinis inkaras.

- **„Grąžinti originalą" pažymi tik saugius taikinius nutemptame
  rėmelyje.** Visi jame pakeisti terminai nušvinta atskirai ir tiksliai;
  nepakitęs rišlusis tekstas lieka nepaliestas. Tikros vektorinės
  užtamsinimo juostos taip pat pažymimos atskirai, jei po jų juoda PDF
  sritimi yra originalo tekstas. Rastruotuose puslapiuose peržiūra
  sąmoningai atsisako tariamos juostos srities: ankstesnė pikselių
  paieška ten sujungdavo raides, pabraukimus ir lentelių linijas į
  dideles raudonas sritis netinkamose vietose. Pats atkūrimas dėl to
  nepaveiktas.

- **Atkuriant rastruotuose puslapiuose tekstas vėl sugrįžta.** Anksčiau
  ten likdavo tuščia vieta su spalvotais stačiakampiais virš jos.
  Grąžintas tekstas stovėjo dokumente, tačiau buvo uždengtas baltu
  žymiklio fonu, piešiamu vėliau puslapio kūrimo eigoje.

- **Patikros spalvos nebestovi kelis kartus viena ant kitos.** Ta pati
  vieta būdavo nuspalvinama kiekvienam priskirties įrašui – puslapyje
  penkios tikros radimo vietos, kiekviena penkis kartus perpiešta, kol
  iš blankios žymės tapdavo sodrus blokas. Ir jos nebepasirodo ant žodžių,
  kurie iš viso nebuvo pakeisti: jei originali reikšmė puslapyje vis dar
  stovi, ten žymės nebėra.

## 0.10.40-beta.1 – 2026 m. rugpjūčio 24 d.

### Ištaisyta

- **Užtamsinimo juostos redaktoriuje dabar turi saugumo paraštę.** Žodžio,
  eilutės ir laisvi rėmeliai dengia ir kabančius glifus bei glotninamus
  krašto pikselius; papildoma atvaizdavimo patikra užtikrina, kad neliktų
  nei matomų likučių, nei nuskaitomo originalo teksto.

- **Pakaitos tekstai lieka įskaitomi ir vienodai trumpi.** Nauji vardai,
  adresai ir laisvi terminai pavyzdžiui rodomi kaip `[NAM1]`, `[ADR2]" ir
  `[BEG3]". Fiksuota apatinė riba yra 4,5 taško; trūkstant vietos pirmiausia
  trumpinama, o naudojamas laisvas plotas išplečiamas. Senos priskirtys su
  ilgais žymikliais lieka įskaitomos ir grąžinamos.

- **Kelių žodžių pakeitimai iš radimo skydelio apsaugoti nuo dvigubų
  žymių ir originalo likučių.** Regresija veikia su ir be sunumeruotų
  žymiklių; kiekvienai radimo vietai išlieka lygiai viena bendra
  priskirtis.

- **Grąžintas mainų srities turinys „macOS" sistemoje iš karto pakartotinai
  neišvalomas.** Net jei sisteminis parašas po įrašymo pasikeičia tik
  vėluodamas, Maskuro patikimai atpažįsta savo paties turinį.

### Nauja

- **Redaktorius gali failą visiškai grąžinti į ką tik išvalytą pradinę
  versiją.** „Failas – Atstatyti" po patvirtinimo atmeta visus dabartinio
  skirtuko taisymus, įskaitant pakeitimų sąrašą ir skaitiklius. Komanda be
  pakeitimų yra užrakinta ir savo ruožtu gali būti atšaukta komanda
  „Anuliuoti".

- **Pastumtos datos dabar patikimai išlaiko savo chronologiją keliuose
  failuose.** Bendras poslinkis nuo strategijos įjungimo iš karto įtvirtinamas
  taisyklėse ilgam; be to, poslinkis nebegali būti lygus nuliui dienų ir taip
  nepastebimai palikti tikrą datą.

- **PDF rankinis darbas dabar apima visą profesionalų užtamsinimo eigą.**
  Pavieniai terminai, sąrašai ir reguliarieji šablonai gali būti ieškomi ir
  saugiai užtamsinami atidarytame PDF faile arba visuose aplanko PDF
  failuose; visi puslapiai ir puslapių sritys tiesiogiai pasirenkamos.
  Spalva, neutrali balta sritis, uždengimo tekstas, šriftas, lygiavimas ir
  kartojimas turi peržiūrą, pakartotinai naudojami kodai gali būti tvarkomi
  bei importuojami ir eksportuojami. PDF valymas pašalina pasirinktinai
  visą paslėptą turinį per pilną atkūrimą arba pasirinktas duomenų
  kategorijas. Saugiausias pasirinkimas aiškiai rekomenduojamas, negaliojantys
  paieškos šablonai paaiškinami, o aplankų paleidimai rašo tik rezultatų
  kopijas.

- **Savanoriška naudojimo statistika dabar rodo diegimus ir versijų
  keitimus.** Tam Maskuro sukuria atsitiktinį, vietoje saugomą diegimo
  identifikatorių. Jame nėra jokių įrenginio, naudotojo ar licencijos
  duomenų; serveris saugo tik jo SHA-256 reikšmę. Statistiką nustatymuose
  ir toliau galima visiškai išjungti.

- **Apžvalginis vedimasis dabar yra vedama pratybų per abu langus.** Jis
  pats sugalvotą pratybų dokumentą įtraukia į sąrašą, paaiškina kelią iki
  valymo ir po paleidimo automatiškai tęsiasi redaktoriuje. Kas nutraukia
  vedimąsi, nutraukia ir šį tęsinį.

- **Atpažįstamos įmonės iš penkiolikos papildomų teisinių erdvių.** Kas
  valo dokumentus iš Baltijos šalių, Belgijos, Skandinavijos, Čekijos,
  Lenkijos, Pietryčių Europos, Singapūro, Brazilijos ar Meksikos, daugiau
  nebeprarandavo įmonių pavadinimų dėl to, kad jų teisinė forma buvo
  nežinoma – naujai pridėta, be kita ko, OÜ, MTÜ, SIA, VZW, ASBL, P/S,
  Sh.p.k., EIRELI, z.s., o.p.s., S.K.A., Pte. Ltd. bei S.A. de C.V. ir
  S. de R.L.

### Pakeista

- **Redaktoriaus įrankių juostos dabar tiksliau naudoja vietą.**
  Vienareikšmiai standartiniai simboliai ir iš karto atpažįstamos įrankių
  formos stovi juostoje be pasikartojančio teksto; dviprasmiški veiksmai
  išlaiko pavadinimą. Meniu „Rodinys" galima išjungti „Rodyti įrankių
  užrašus", kad abi juostos susitrauktų vien iki simbolių. Paaiškinimai ir
  meniu tuo pačiu lieka pilnai užrašyti, pasirinkimas įsimenamas.

- **Mokymosi veiksena dabar nuolat matoma įrankių juostoje.** Ją ten
  galima iš karto įjungti ir išjungti, net kai pakeistų reikšmių skyrius
  uždarytas. Įrankių juosta, meniu „Įrankiai" ir ankstesnė varnelė
  skyriuje visada rodo tą pačią būseną.

- **„Atstatyti" prie palyginimo didinamojo stiklo dabar grąžina tik jo
  mastelį.** Mygtukas atstato numatytąjį 125 procentų dydį, neprišvartuodamas
  didinamojo stiklo, jo neperkeldamas ir nekeisdamas jo lango dydžio. Už
  visą išdėstymą ir toliau atsako „Atstatyti rodinį".

- **Klaidas ir pageidavimus dabar galima pranešti ir per pagalbos
  mygtuką.** „Pranešti apie klaidą …" ir „Pareikšti pageidavimą …" ten
  dabar stovi taip pat, kaip ir klasikiniame pagalbos meniu; abu keliai
  atveria jau esamą saugų klaidos pranešimą arba viešą pageidavimų
  sąrašą.

- **Užduočių juostos meniu trumpesnis ir aiškiau sutvarkytas.** Dvi
  komandos su globaliu klavišų deriniu – mainų srities valymas ir ekrano
  nuotrauka – dabar stovi tiesiogiai viena po kita su bendru dešiniuoju
  derinių stulpeliu. „Atkurti paskutinį originalo turinį" ten
  panaikinama; suprantamesnis atkūrimo mygtukas lieka pasiekiamas
  pagrindiniame lange.

- **Teisiniai puslapiai pasiekiami tiesiogiai po „Pagalba → Teisinė
  informacija".** Papildomas meniu veda į licencijos sąlygas, privatumo
  pareiškimą, teisinę informaciją apie leidėją ir bendrąsias sąlygas
  svetainėje maskuro.com. Nuorodos dėl atsisakymo teisės lieka svetainėje
  perkant.

- **Rankiniu būdu užtamsinti PDF failai išsaugant visiškai atkuriami iš
  naujo.** Matomi lieka puslapiai ir jų iš naujo perskaitytas paieškos
  sluoksnis; metaduomenys, failo priedai, žymelės, komentarai, formos
  reikšmės, paslėpti sluoksniai, paieškos indeksai, scenarijai, apkirpti
  turiniai ir po kitais objektais paslėptas turinys į išvesties failą
  neperkeliami. Šriftas ir vektorinė grafika po to sudaryti iš pikselių –
  tai yra įrodomos ribos su svetimu PDF objektų medžiu kaina.

- **Ctrl+Shift+B dabar visose sistemose pagal numatytuosius nustatymus
  daro ekrano nuotrauką su Maskuro.** „Print Screen" klavišas ir jo
  deriniai lieka galimi kaip atskiras priskyrimas. Užduočių juostos
  piktogramos meniu globalūs klavišų deriniai dabar stovi dešinėje šalia
  atitinkamų komandų. Savi išsaugoti priskyrimai išlieka.

- **Redaktorius startuoja su puslapiais ir palyginimo didinamuoju stiklu
  kairėje.** Puslapių skyrius stovi viršuje, atidarytas originalo
  didinamasis stiklas tiesiai po juo; pakeistos reikšmės lieka dešinėje.
  Sąmoningai išsaugotas savas išdėstymas ir toliau turi pirmenybę.

- **Pratybų dokumentas nebestovi nuolat pagrindiniame lange.** Jis yra
  vedamos pratybos dalis ir papildomai pasiekiamas po „Pagalba".

- **Pirmasis paleidimas dabar tiesiogiai veda į praktinę pratybą.**
  Iliustruota trumpa instrukcija nebesiūloma kaip antras, turiniu
  besidubliuojantis įėjimo kelias; ji ir toliau visada pasiekiama po
  „Pagalba → Trumpa instrukcija".

- **Neaktyvi užduočių juostos piktograma lieka pilnos spalvos.** Ji dabar
  rodo tą patį ryškų Maskuro skydą kaip ir aktyvi mainų srities veiksena;
  tik esant aktyviam stebėjimui prisideda žalias švytintis taškas.

- **Pratybų dokumentas lieka Maskuro programoje.** Įėjimo mygtukas sukuria
  sugalvotą PDF ir tiesiogiai įtraukia jį į failų sąrašą, tačiau daugiau
  nebepaleidžia papildomos PDF peržiūros programos.

- **Paieška taisymo lange rašant lieka sklandi.** Vieta radinių skaitikliui
  rezervuojama jau atidarant; jos pirmasis tekstas nebekeičia drobės ir
  nebesukelia naujo PDF rastravimo paleidimo.

- **Gamintojų pavadinimai gaminio nurodymuose lieka matomi.** Įrašas kaip
  „Fabrikat: TRILUX oder gleichwertig" aprašo reikiamą prekę ir
  nebeužtamsinamas kaip įmonė vien dėl šio užrašo. Tiekėjo, įmonės ir
  gamintojo laukai dėl to nepaveikti.

- **Korpuso matavimai per plačiai užtamsintus radinius skaičiuoja kaip
  klaidingus pavojus.** Kai Maskuro pašalina laukiamą vardą, bet kartu
  nusineša sakinio dalį, klaidingų pavojų skaičius dabar padidėja.
  Ataskaita papildomai atskirai nurodo tokius peržengimus; todėl ankstesni
  klaidingų pavojų skaičiai tiesiogiai nepalyginami.

### Ištaisyta

- **Techniniai ir valdiški terminai iš vokiškų originalių dokumentų
  rečiau užtamsinami kaip vardai ar vietovės.** Transporto priemonių
  įranga, pozicijų ir sumų eilutės, pirkimų ir duomenų apsaugos terminai,
  įstatymų nuorodos bei viešos medžiagos failų pavadinimai stabdomi tik
  pagal jų pagrįstą dalykinį kontekstą. Teksto atpažinimo metu prarastas
  balsis „Marz 2026" lieka apsaugotas kaip mėnuo; „Marz" be datos ryšio
  ir toliau gali būti tikras vardas ar vieta.

- **„Grąžinti originalą" iš karto užima visą reikiamą plotį.** Jei
  rėmelis paliečia tik vieną priskirtos reikšmės žodį, Maskuro pagal
  priskirtį ir originalo eilutę savarankiškai išplečia jį iki viso
  duomens – pavyzdžiui, nuo „Planungs" iki „Nordlicht Planungs GmbH".
  Vėliau pasiekiamas rėmelis taip pat rodo faktiškai grąžintą bendrą
  plotį.

- **„Grąžinti originalą" dabar juodas juostas rodo kaip vienareikšmį
  taikinį.** Vedant pele virš arba tempiant, visa atpažinta juosta
  nušvinta raudonai su šviesiu kontrastiniu kontūru, o ne tik sunkiai
  priskiriamas teksto langelis šalia. Tai galioja ir rastruotiems
  puslapiams, kuriuose juosta sudaryta tik iš pikselių.

- **Redaktoriaus apžvalginis vedimasis nebepraleidžia stotelių, kai
  skyriai buvo uždaryti.** Vedimuisi Maskuro laikinai pats atidaro ir
  sutvarko puslapių skyrių, palyginimo didinamąjį stiklą ir pakeistas
  reikšmes. Po „Baigta" ar nutraukimo grįžta asmeninis išdėstymas. Jei
  įrankis tam tikrai dokumento rūšiai iš principo nepasiekiamas, jo
  paaiškinimas išlieka kaip teksto sustojimas, o ne nepastebimai
  išnyksta.

- **„Keisti" lieka matomas ir per PDF saugumo atsarginį kelią.** Jei
  Maskuro turėjo iš naujo sukurti puslapį kaip vaizdą dėl likusio
  simbolio ar sugadinto teksto srauto, teisingi pakeitimai likdavo tik
  nematomi paieškos sluoksnyje, o puslapyje gulėjo juodos juostos. Faktiškai
  nustatytos pakaitos reikšmės dabar išlieka matomos raudonos ir
  ieškomos per visus rastravimo ir OCR atkūrimus.

- **Nuorodos virš išvalytos versijos lieka įskaitomos tamsioje
  išvaizdoje.** Versijos antraštė, valdymo eilutė ir įžanga dabar savo
  šrifto spalvą perima tiesiogiai iš faktiškai rodomo Qt lango.

- **Užtamsinimo rėmeliai rastruotuose PDF puslapiuose vėl stovi virš
  teksto.** Nematomi žodžių langeliai, priklausomai nuo originalo
  šrifto, būdavo siauresni nei matomos raidės. Dėl to juostoje
  atsirasdavo spragų arba paskutinė raidė likdavo įskaitoma. Langeliai
  dabar išlaiko matomo žodžio plotį, aukštį ir kryptį.

- **„Kas naujo" vėl prasideda visiškai nuo viršaus.** Pakeitimų sąrašo
  dialogas po baigto lango sudarymo teksto žymeklį ir slinkties juostą
  aiškiai nustato į pradžią, o ne pradeda vidury naujienų, priklausomai
  nuo Qt būsenos.

- **Uždarymas skenavimo žodžių atpažinimo metu lieka tylus.** Ką tik
  baigiamas OCR fono paleidimas daugiau nebesiunčia į jau uždarytą
  taisymo langą.

- **Santykiniai laiko nurodymai daugiau nebelaikomi vardais.** Fiksuotus
  posakius kaip „šiandien", „vakar", „rytoj" ir „kitą savaitę" Maskuro
  dabar atpažįsta iš atitinkamos dokumento kalbos oficialių kalendoriaus
  duomenų.

- **Užbaigimas pirmojo modelio įkėlimo metu tvarkingai susitvarko.** Kas
  uždaro Maskuro ar taisymo langą tuoj pat po atidarymo, procesui
  baigiantis nebepalieka dar veikiančio siūlo natyviame kalbos
  atpažinime. Tai apsaugo nuo pavienio avarijos pranešimo užbaigiant;
  jau vykstantis įkėlimas tvarkingai užbaigiamas.

- **Vėluojantys paleidimo dialogai daugiau nepasirodo po užbaigimo.** Kas
  uždaro pagrindinį langą netrukus po paleidimo, po to daugiau negauna
  nematomai ar pavėluotai parodyto klausimo apie geriausią atpažinimą,
  naujienas ar įvadą.

- **HTML ir e. laiškai išlaiko savo eilučių pabaigas.** „Windows" sistemoje
  HTML serializavimas po valymo ir grąžinimo maišydavo LF ir CRLF.
  Turinys ir formatavimas buvo teisingi, tačiau failas nebebuvo baitas į
  baitą tapatus. HTML failai ir MIME žinutės dabar vėl perima savo
  šaltinio užrašymo būdą.

- **Įmonių pavadinimai su santykio žodžiu lieka pilni.** Po įvardžio
  Maskuro nukirsdavo tokius vardus kaip „Gesellschaft für Systemtechnik
  mbH" ar „Bank für Arbeit und Wirtschaft AG" ties žodžiu „für". Dabar
  atpažįstamas visas įmonės pavadinimas; tikri sakinio įvadai kaip „Wir
  sind bei Alpha GmbH versichert" lieka matomi.

- **Kinų įmonių pavadinimai lieka pilni prieš jų teisinę formą.** Kaip
  veiksmažodis interpretuojama prekės ženklo dalis, nepaisant
  vienareikšmio priedo „有限公司", galėjo atmesti visą pavadinimą. Raštuose
  be didžiųjų ir mažųjų raidžių skirtumo oficialus teisinės formos
  inkaras dabar turi pirmenybę prieš šią nepatikimą žodžio dalies ribą.

- **PDF puslapiai be reikalo tapdavo vaizdais.** Daugiapuslapiuose PDF
  failuose, kurių puslapiai dalijasi šriftų sąrašu – kaip įprasta
  kuriama įprastų generatorių –, po pirmojo puslapio visi tolesni
  prarasdavo nuorodą į savo šriftus. Pasekmė buvo dviguba: balsiai su
  ženklais rezultate nebebuvo beieškomi (nebuvo galima rasti
  „Auftragsbestätigung"), o pakartotinė patikra po to laikė praleistomis
  raides, kurių puslapyje niekada nebuvo – ji rastravo sveikus teksto
  puslapius į vaizdus, taip juos padarydama nebeieškomus, nebekopijuojamus
  ir gerokai didesnius. Patikros rinkinyje tai paveikė keturis iš
  septyniolikos puslapių.
- **Vien kablelis daugiau nebesukelia rastravimo.** Jei radimo sritis
  baigiasi ties žodžiu, skyrybos ženklas šalia dar priklauso jai. Tačiau
  kablelis ar taškas nėra praleista informacija, o rastravimas kainuoja
  visą puslapį. Raidės ir skaitmenys ir toliau lieka pagrindas tikslinti
  paiešką.

## 0.10.38-alpha.20260824 – 2026 m. rugpjūčio 24 d.

### Nauja

- **Įmonių pavadinimai be teisinės formos dabar atpažįstami, kai juos
  nurodo užrašas.** „Lieferant: Kranzbichler Handels GmbH" visada buvo
  pašalinama – teisinė forma išduoda įmonę. „Lieferant: Dehner Märkte"
  likdavo, o pasiūlymuose, konkursuose ir užsakymuose tiekėjas dažniausiai
  būna nurodytas būtent taip. Tas pats galioja „Firma:", „Hersteller:",
  „Fabrikat:", „Arbeitgeber:" ir jų atitikmenims aštuoniose kitose
  kalbose, ir tada, kai užrašas stovi vienas savo eilutėje, o pavadinimas
  po juo.

  Kas po užrašu *nėra* įmonė, lieka nepaliesta: „Lieferant: siehe Anlage"
  neužtamsinama – kitaip ten stovėtų „Lieferant: [ORGA1]", o tai teigtų
  pavadinimą, kurio niekada nebuvo. Užrašai, po kuriais taip pat dažnai
  stovi žmogus („Kunde:", „Auftraggeber:"), sąmoningai neįtraukti.

- **Įterptą vaizdą dabar galima ir redaguoti.** Lange „Išvalyti paveikslėlį"
  šalia „Kopijuoti rezultatą" yra mygtukas *Redaguoti redaktoriuje*:
  vaizdas išvalomas, o po to atidaromas papildomam užtamsinimui,
  užrašams ir paryškinimui – tuo pačiu keliu, kuriuo eina ekrano
  nuotrauka.

- **Numeriai po jų užrašo dabar randami ir tada, kai jie įvardija verslo
  partnerį.** Anksčiau krisdavo kliento, sutarties ir personalo numeriai;
  dabar taip pat debitoriaus, kreditoriaus ir tiekėjo numeris, austriška
  darbdavio numeris, ANKÖ registracija ir gamintojo WEEE, EAR bei EPR
  numeris – vokiškai ir angliškai. Be to, Maskuro dabar supranta
  nustatytų pasiūlymų antraščių rašyseną su tarpu prieš dvitaškį
  („Kunden-Nr : K903944"). Prekės, užsakymo, darbo, pasiūlymo ir
  sąskaitos numeriai ir toliau lieka nepaliesti: jie įvardija procesą ar
  prekę, ne žmogų. Kas juos vis tiek nori pašalinti, įrašo juos kaip
  atskirą paieškos šabloną.

- **Dabar matote, kiek laiko užtruko failas.** Baigtoje eilutėje šalia
  atpažintos kalbos rodoma trukmė („baigta · vokiečių · 2,4 s"),
  santraukoje – viso paleidimo, rodiklių skydelyje – suma, o patikros
  ataskaitoje ji stovi kaip atskiras laukas. Esant keliems failams,
  eilutė sako, kuriam iš jų prireikė laiko.

- **Sistemos OCR nepalaikomi raštai gali būti perskaityti atsarginiu
  būdu, jei yra tinkama kalbos byla.** Anksčiau galiojo: jei sisteminis
  teksto atpažinimas nevaldo rašto (pvz., „Mac" sistemoje devanagari),
  rezultate stovėdavo „Vaizdas(-ai) NEBUVO patikrinti", o vaizdo duomenys
  likdavo. Dabar, jei tinkama kalbos byla yra, į pagalbą ateina
  pridedamas teksto atpažinimas. Kadangi taip perskaitytas vaizdas yra
  mažiau patikimas nei įprastai patikrintas, tai rašoma rezultate:
  „perskaityta atsarginiu būdu – prašome peržiūrėti". Vertinant pagal
  istorinę tarpinę hindi bandymo būseną: **rasta dešimt duomenų daugiau
  ir keturiais klaidingais pavojais mažiau** (64 % → 73 %). Dabartinė
  galutinė reikšmė nurodyta aukščiau ir su šia nemaišytina.

- **Teksto atpažinimas dabar klausia teisingos kalbos.** Visoms
  dokumentų kalboms, išskyrus vokiečių ir anglų, iki šiol buvo naudojamas
  angliškas atpažinimo modelis, net jei buvo paruošta tinkama kalbos
  byla. „Windows" sistemoje tai lietė kiekvieną kalbą – graikų, japonų
  ar hindi ten buvo skaitomos angliško modelio.

- **Diegimo asistentas per pačią pirmą paleidimą.** (Kas Maskuro jau
  naudojo, jo negauna – „pirmas paleidimas" reiškia pirmą paleidimą, ne
  pirmą paleidimą po šio atnaujinimo.) Trys klausimai vietoj šešių
  paveikslėlių: jūsų dokumentų kalba, ar tekstas vaizduose taip pat
  skaitomas, ir kaip norite Maskuro pasiekti kasdien. Pabaigoje ir toliau
  yra trys keliai – pratybų dokumentas, apžvalginis vedimasis ar
  iliustruota trumpa instrukcija. Viską galima praleisti, o „Pagalba →
  Pereiti diegimą iš naujo" jį grąžina.

- **F1 atveria vadovą reikiamame skyriuje.** Pagrindiniame lange,
  nustatymuose (priklausomai nuo puslapio), peržiūros lange ir kalbų
  valdyme; taisymo lange – per Shift+F1, nes F1 ten nuo seno rodo
  klavišų derinius. Anksčiau pagalba visada prasidėdavo nuo viršaus, prie
  25 skyrių.

- **Naujas pirmas vadovo skyrius: „Pradėkite per tris minutes".** Keturi
  žingsniai, daugiau dokumentui nereikia – visose 18 kalbų versijų.

- **Apžvalginis vedimasis per langą.** „Pagalba → Apžvalginis vedimasis
  per langą" po vieną paryškina valdymo elementą ir šalia parašo
  sakinį – pagrindiniame lange aštuonios stotelės, taisymo lange
  septynios. Kitaip nei iliustruota trumpa instrukcija, jis paaiškina
  langą, prieš kurį šiuo metu sėdite. Bet kada nutraukiamas su Esc.

- **Pratybų dokumentas saugiam bandymui.** Po įkėlimo sritimi dabar yra
  „Atidaryti pratybų dokumentą" (taip pat pagalbos meniu). Jis sukuria
  sugalvotą lapą – vardas, adresas, telefono numeris, IBAN, socialinio
  draudimo numeris – ir lape kartu parašyta, ką su juo galite daryti ir
  ką po to pamatysite. Nė vienas žodis nepriklauso tikram žmogui; taigi
  pirmasis dokumentas, kurį siunčiate per Maskuro, neprivalo būti
  tikras.

- **„Tik peržiūrėti …" dabar stovi šalia „Valyti".** Jis rodo, kur yra
  asmens duomenys – failas, rūšis ir kiekis –, nieko nekeisdamas ir
  nerašydamas. Kas įkėlė dokumentą, gali jį peržiūrėti prieš valydamas.
  Anksčiau šis kelias buvo tik meniu „Failas" po „Peržiūrėti aplanką …" ir
  ėjo per visą aplanką, o ne per įkeltus failus.

- **Kai nieko nerasta, dabar parašyta, kodėl taip gali būti.** Pavyzdžiui:
  faile yra vaizdų, bet „Tikrinti ir tekstą vaizduose" išjungta. Arba:
  nustatyta kalba netinka dokumento kalbai. O jei nieko panašaus nėra,
  Maskuro tai taip pat pasako.

- **Taisymo langas pirmą kartą jus pasitinka trimis sakiniais:**
  spustelėjimas užtamsina žodį, tempimas – sritį, dešinėje stovi
  pakeistos reikšmės. „Supratau" nuorodą pašalina ilgam; „Pagalba →
  Rodyti įvadą iš naujo" ją grąžina.

- **Žodžius dabar galima spustelėti ir nuskenuotuose puslapiuose.**
  Anksčiau žodžius buvo galima spustelėti tik ten, kur PDF failas turi
  teksto sluoksnį – skenavime tai neveikė, ir tame pačiame dokumente tai
  galėjo keistis nuo puslapio iki puslapio. Tokie puslapiai dabar vieną
  kartą perskaitomi teksto atpažinimo; po to žodžius spustelite kaip
  visur kitur. Būsenos eilutė sako, kas šiuo metu vyksta.

- **Puslapių skyrius vėl yra vientisas plotas.** Jis baigdavosi savo
  stulpelio viduryje: nukirsta antraštės juosta, šalia kitos spalvos
  juosta, o dabartinis puslapis buvo atpažįstamas tik iš spalvoto
  langelio už jo numerio. Dabar jis užpildo visą savo stulpelį, gali
  būti tempiamas platesnis, o dabartinis puslapis paryškintas kaip visa
  plytelė – su nesuklastota puslapio peržiūra viduje.

- **Pakeistos vietos nušvinta blankiai geltonai.** Puslapio vaizde taip
  iš karto matoma, kur kas nors buvo pakeista – ta pati spalva, kurią
  naudoja palyginimo didinamasis stiklas virš originalo. Raudonas
  rėmelis vedant pele lieka nepakitęs.

- **„Atstatyti rodinį" taisymo lange** (meniu „Rodinys"). Kas perkėlė,
  atskyrė ar uždarė puslapių skyrių ar radimo sąrašą, tuo viską grąžina
  ten, kur buvo per pirmą paleidimą.

### Pakeista

- **Žymikliai trumpesni.** Iš `[SOZIALVERSICHERUNGSNR_1]` tampa `[SVNR1]`,
  iš `[ORGANISATION_1]` – `[ORGA1]`, iš `[EMAIL_1]` – `[MAIL1]`. Priežastis
  ne grožis: žymiklis, ilgesnis už reikšmę, kurią jis keičia, išstumia
  eilutę ir siaurame lentelės stulpelyje nebetelpa iš viso – ten anksčiau
  likdavo juoda juosta, kuri niekam nebesako, kad vietoje kažkas stovėjo.
  Kur yra įprasta santrumpa, ji ir naudojama (`[BLZ1]`, `[KFZ1]`,
  `[IBAN1]`). Ankstesnių paleidimų rezultatai lieka naudojami: senoji
  rašysena ir toliau atpažįstama, o vakarykščiai priskirčių failai veikia
  nepakitę.

- **Programos ženklas dabar visur atrodo vienodai.** „Mac" meniu juostoje
  anksčiau rodydavosi vienspalvis skydas, kurį pati sistema nudažydavo
  juodai ar baltai, „Windows" užduočių juostoje – žalias arba pilkas.
  Dabar kiekviena juosta turi tą patį mėlyną Maskuro skydą. Kaip matyti,
  ar mainų sritis stebima, lieka taip pat aišku: kai stebėjimas veikia,
  prie skydo yra žalias taškas; kai jis ilsisi, tas pats skydas stovi
  blankus. Net mažiausiuose dydžiuose skyde dabar rodomos abi
  užtamsinimo juostos – anksčiau užduočių juosta ten rodė tik vieną.

- **Veidai atpažįstami modeliu, kurio mokymo vaizdai sukurti su
  sutikimu.** Dabar pristatomas „MediaPipe BlazeFace" (Apache-2.0);
  ankstesnis detektorius lieka įmontuotas ir perjungiamas, tačiau nebe
  pridedamas, nes jo mokymo kilmė nėra galutinai išaiškinta. Atpažinimui
  niekas nesikeičia: 324 portretuose ir 143 vaizduose be veido nauja
  versija randa lygiai tiek pat, esant lygiai tiek pat klaidingų pavojų,
  ir jai reikia trečdalio laiko.

- **OCR yra saugumo inkaras stipriausiam PDF pažadui.** Įprastas PDF
  paleidimas jį naudoja ir sukuria pilną minimalią struktūrą. Kas
  aiškiai išjungia OCR, gauna suderinamesnį objektų kelią; sąsaja,
  baigiamasis pranešimas ir vadovas dabar aiškiai sako, kad šis kelias
  nesuteikia tos pačios architektūros prieš nežinomus paslėptus PDF
  kanalus.

- **Pardavimo vartai dabar užrakina ir iki šiol pridedamą „YuNet"
  modelį.** Tikslaus svorio MIT licencija lieka dokumentuota, tačiau
  viešai matomai mokymo duomenų grandinei per „WIDER FACE" jos
  nepakanka konservatyviam produkto leidimui. Prieš parduodant reikia
  rašytinio išaiškinimo arba pakeitimo modeliu su patikima komercine
  duomenų ir svorių grandine.

- **Įmonių ir organizacijų pavadinimai dabar pašalinami savaime.**
  Anksčiau jie likdavo, kol nebūdavo aiškiai jų paprašyta. Verslo laiškui
  tai buvo neteisinga numatytoji reikšmė: kas persiunčia pasiūlymą,
  nenori jame skaityti užsakovo. „Kranzbichler Handels GmbH", „Institut
  für Bauphysik" ir panašūs dalykai dėl to traktuojami kaip vardas. Kas
  jo nori kitaip, išjungia jį lange; komandinėje eilutėje jungiklis dabar
  vadinasi `--ohne-organisationen`. Senasis `--mit-organisationen`
  ir toliau priimamas, tačiau daugiau nieko nedaro, kad esami scenarijai
  ir nuorodos neliktų sugadinti. Datos ir pinigų duomenys ir toliau
  nepaliesti.

- **Užtamsinimas dabar turi tris formas vietoj dviejų varnelių.**
  „Žodžiai", „Visa eilutė" ir „Laisvas rėmelis" stovi kaip vienas
  pasirinkimas šalia vienas kito – visada galioja lygiai vienas. Anksčiau
  „Teksto eilutės" ir „Visa eilutė" buvo du nepriklausomi jungikliai, kurie
  abu galėjo būti paspausti, o laisvas rėmelis apskritai nebuvo mygtukas,
  o pirmojo išjungta būsena. Trys dabar matomai stovi prie savo įrankio ir
  yra pilki, kol pasirinktas kitas įrankis.

### Patobulinta

- **Pirmasis dokumentas baigiamas maždaug sekunde greičiau.** Prieš
  pradedant valymą Maskuro nustato dokumento kalbą – ir tam anksčiau
  imdavo visų 48 kalbų žodžių sąrašus keliu, kuris įkeldavo gerokai
  daugiau nei tik žodžius. Tai sudarė maždaug pusę laukimo laiko iki
  pirmojo rezultato. Pats atpažinimas nepakitęs: jis mato tuos pačius
  žodžius kaip anksčiau, tik greičiau. Kiekvienam tolesniam dokumentui
  tai vis tiek neturėjo įtakos.

- **Dokumentai su labai ilgomis pastraipomis tikrinami greičiau.**
  Pastraipą be eilutės lūžio Maskuro anksčiau iš naujo perskaitydavo
  visą kiekvienai rastai vietai; dabar pakanka vieno karto. Kuo ilgesnė
  pastraipa, tuo didesnis skirtumas – išmatuota maždaug septintadaliu
  mažiau skaičiavimo laiko. Rezultatas nepakitęs.

### Ištaisyta

- **Su įmone dažnai dingdavo pusė sakinio.** Jei rišliame tekste stovėjo
  įmonės pavadinimas – „Information über die Gottwald GmbH & Co KG",
  „… (AGB) der Musterbetriebe GmbH" –, būdavo užtamsinamas ne tik
  pavadinimas, bet ir viskas prieš jį iki sakinio pradžios. Dėl to tekstas
  tapdavo neįskaitomas ir atrodydavo, tarsi būtų užtamsinta atsitiktinai.
  Įmonių pavadinimai, kurie patys turi „für" ar „und" („Bank für Arbeit
  und Wirtschaft AG"), dėl to lieka nepakitę ir pilni.

- **Įmonių pavadinimai likdavo firminiuose blankuose, nors tekste buvo
  pašalinti.** Pasiūlyme įmonės buveinė firminio blanko vaizde tebestovėjo
  įskaitoma – ta pati vieta, kurią Maskuro rišliame tekste užtamsino;
  ieškomame rezultato tekste ji netgi tebestovėjo nematomai. Kas kartą
  buvo pašalinta, dabar pašalinama ir ten, kur tai yra tik vaizdas. Tai
  veikia ir su logotipais bei žodiniais ženklais, nupieštais kaip grafika.

- **„macOS" kiekvieną kartą paleidžiant klausdavo dėl ekrano įrašymo**,
  net kai leidimas jau seniai buvo suteiktas. Nuoroda paleidimo metu
  išbandydavo įrašymą, ir būtent tai iškviesdavo sisteminį dialogą.
  Dabar paleidžiant klausia tik pats Maskuro, ir tik kartą; sistema
  klausia tik tada, kai tikrai darote ekrano nuotrauką.

- **Techniniai dalykiniai terminai buvo laikomi vietovėmis ir
  įmonėmis.** „Einspeisepunkt", „Flachdach", „Verteileranlage",
  „Meldersockel" ir dešimtys panašių žodžių dingdavo iš pasiūlymų ir
  darbų sąrašų. Maskuro juos dabar atpažįsta iš šaknies: kas baigiasi
  „-anlage", „-punkt" ar „-kanal", yra daiktas. Vietovardžiai kaip
  Berlynas, Melkas ar Vyzelburgas tokios šaknies neturi ir lieka
  nepaliesti – taip pat kaip adresai „Der Graben" ar „Alter Markt".

- **Japonų, korėjiečių, kinų, tajų ir gudžaratų kalbų dokumentai galėjo
  sukelti programos avariją.** Jei dokumente viena iš šių penkių kalbų
  turėjo interneto adresą be „https://" priešais, valymas nutrūkdavo su
  vidine klaida – esant atidarytam langui, tuomet prarasdavo ir kitą
  darbą. Visos keturiasdešimt aštuonios pasirenkamos dokumentų kalbos
  dabar veikia iki galo; jei kalbai trūksta dažnumo žodyno, duomuo
  abejonės atveju lieka, o ne dingsta.

- **Lauko užrašai saugojo tik vokiškai ir angliškai.** „Reference"
  likdavo, itališkas „Riferimento" ir portugališkas „Referência" buvo
  pašalinami kaip vietovė – tas pats lauko pavadinimas, ta pati eilutė,
  kitoks rezultatas. Kas dirba ne angliškai, buvo blogesnėje padėtyje.
  Maskuro dabar žino tuos pačius lauko pavadinimus visose vienuolikoje
  prižiūrimų kalbų.

- **„Grąžinti originalą" nuskenuotuose puslapiuose grąžindavo per
  daug.** Rėmelis virš vienos užtamsintos adreso bloko eilutės vėl
  atverdavo **visą bloką** – ir puslapis likdavo suplėšytas: juostų
  likučiai tebestovėjo, iš kurių kyšojo pavieniai žodžių galai.
  Priežastis buvo ta, kad viena po kita einančios juostos rastruotame
  puslapyje susiliečia ir todėl laikomos viena vientisa sritimi. Dabar
  grąžinama lygiai ta eilutė, į kurią rodo rėmelis; kaimyninės eilutės
  lieka užtamsintos, o pataikytos eilutės juosta visiškai dingsta.

- **Kiekio nurodymai pozicijų sąrašuose buvo laikomi adresais.** Eilutėje
  kaip „1.4 Kabelgraben 100,00 m" „Kabelgraben 100" buvo pakeista kaip
  gatvė su namo numeriu. Tokios eilutės dabar lieka; tikri adresai – taip
  pat „Hauptplatz 1, 3250 Wieselburg" – ir toliau atpažįstami nepakitę.

- **Prieš įmonės pavadinimą dingdavo pusė sakinio.** Iš „Vertrag zwischen
  der Firma Gottwald GmbH & Co KG und dem Auftraggeber." tapdavo
  „[ORGANISATION_1] und dem Auftraggeber." – sakinio pradžia dingdavo, o
  su ja ir nuoroda, apie ką kalbama. Dabar krenta tik pats įmonės
  pavadinimas. Kur bendrinis žodis priklauso pavadinimui („Deutsche Bank
  AG", „Universität Wien"), viskas lieka kaip anksčiau.

- **Protokole likdavo kalbėtojai, kurių vardas kartu yra profesija.**
  „Bauer:", „Koch:", „Weber:" prieš žodinį pasisakymą būdavo praleidžiami,
  „Gruber:" šalia – ne; Maskuro anksčiau reikėjo bent vieno atpažinto
  vardo dokumente, kad iš viso skaitytų eilutes kaip pasisakymus. Jei
  dokumentas turi antraštę kaip „Ergebnisprotokoll" arba „Niederschrift",
  dabar to pakanka. Pastabų eilutės („Achtung: …", „Hinweis: …") lieka
  nepaliestos.

- **Lauko užrašas dingdavo kartu su savo reikšme.** Iš „Projekt: Sanierung
  und Erweiterung Gemeindezentrum" gaudavosi vienas žymiklis – žodis
  „Projekt:" taip pat dingdavo, o su juo ir nuoroda, kas toje vietoje
  buvo. Užrašai dabar lieka. Kur užrašas priklauso duomeniui ir neša jo
  reikšmę („Durchwahl 214"), niekas nesikeičia.

- **Maksimalus atpažinimas nepašalindavo dalykinių terminų.**
  „Flachdach", „Einspeisepunkt", „Elektrotechnik" ir panašūs specialieji
  žodžiai buvo keičiami kaip vietovė ar įmonė net esant įjungtai DI
  pakopai – DI niekada negaudavo įvertinti būtent šių radinių. Dabar ji
  juos taip pat tikrina: konkursų ir sutarčių tekstų korpuse dėl to
  dingsta visos 27 klaidos, neprarandant nė vieno tikro duomens. Vardai,
  įmonės ir vietovės atpažįstami nepakitę.

- **Bendriniai žodžiai įstaigų rūšims buvo laikomi organizacijomis.**
  Sutarties tekste dingdavo „Hochschulen und Universitäten", „Staatliche
  und private Schulen", „Akademische Lehrkrankenhäuser",
  „Bildungseinrichtung" ir „Zulieferfirmen" – žodžiai, kurie neįvardija
  konkrečios įstaigos, o įstaigos rūšį. Jie dabar lieka. Jei prieš juos
  stovi tikrinis vardas („EU-Kommission"), ir toliau keičiama, o įmonių
  pavadinimų ši taisyklė apskritai neliečia.

- **Vardai sąrašuose krisdavo tik tada, kai buvo įprasti.** Dalyvių ar
  buvimo sąraše po stulpelio antrašte „Name" būdavo pašalinami „Anna
  Huber" ir „Thomas Müller", bet ne „Wójcik Aleksandra" ar „Kücükgöl
  Sinan" – ta pati eilutė, ta pati sandara. Kas turi retesnį vardą, buvo
  blogiau apsaugotas. Dabar sprendžia stulpelio antraštė: kas stovi po
  „Name", yra vardas. Pozicijų sąrašas su dalykine stulpelio antrašte
  lieka nepaliestas.

- **Telefono numeris po „Durchwahl" buvo perkirstas per vidurį.** Iš
  „Durchwahl 0732 771190" gaudavosi „[DURCHWAHL_1] 771190" – antra
  numerio pusė likdavo įskaitoma. Dabar krenta visas numeris, o užrašas
  lieka. Tikras vidinis numeris („Durchwahl 214") ir toliau keičiamas
  kartu su užrašu.

- **Kai kurių PDF failų iš viso nebebuvo galima išvalyti.** Jei spalvų
  profilio ar vaizdo metaduomenų nepavykdavo įrodomai pašalinti,
  paleidimas nutrūkdavo be rezultato – tai lietė įprastus verslo
  dokumentus kaip bendrųjų sąlygų puslapius, techninių sąlygų sąrašus ir
  konkursus. Tokie failai dabar valomi, o įspėjimas įvardija vietas,
  kurios liko atviros: jose gali būti įrenginio, gamintojo ar įrašymo
  identifikatorius. Originalas kaip visada lieka nepakitęs.

- **Sutarties vaidmenys buvo laikomi asmenimis.** „Bieter", „Verbraucher",
  „Mieter", „Käufer", „Auftraggebers" ir apie keturiasdešimt kitų
  vaidmenų žodžių buvo keičiami, kai stovėjo be artikelio – sutarčių
  antraštėse, lentelių stulpeliuose ir parašo eilutėse. Sutarties tekstas
  be nė vieno asmens duomens dėl to vietomis tapdavo neįskaitomas. Šie
  žodžiai dabar lieka. Jei šalia stovi asmens nuoroda – kreipinys,
  vardas, lauko žodis kaip „Ansprechpartner" –, ir toliau keičiama:
  „Herr Bieter" ir „Frau Käufer" yra vardai. Dažnos pavardės, kurios
  kartu yra profesijos (Bauer, Richter, Koch), šios taisyklės apskritai
  neliečia.

- **Sutrumpinta gatvė buvo praleista, kai namo numeris tiesiogiai lipo
  prie taško.** „Schlesischestr.31" nebuvo laikoma adresu – ir kadangi
  šalia esantis pašto kodas atramą gauna iš adreso radinio, jis taip pat
  likdavo. Rezultate adresą iš gatvės ir pašto kodo vėl buvo galima
  sudėti, ir tai vykdavo tik kai kuriuose to paties dokumento puslapiuose.
  Dabar abu krenta kartu. Dalykiniai pavadinimai su pridėtu skaičiumi
  („Kabelrinne200") lieka nepaliesti.

- **Adresas per dvi eilutes buvo sutraukiamas į vieną žymiklį.** Jei
  adreso bloke pašto kodas stovėjo virš gatvės, Maskuro abi eilutes
  sujungdavo į vieną radimo vietą: rezultate dingdavo eilutės lūžis, o
  pašto kodas likdavo įskaitomas prieš jį. Dabar kiekviena eilutė
  randama ir keičiama atskirai, ir šrifto vaizdas išlieka. Ta pati
  priežastis kartais įtraukdavo į adresą ir pavardę iš eilutės virš jo.

- **Maksimalus PDF kelias daugiau nebeperima originalo objektų.** Esant
  įjungtam teksto atpažinimui, Maskuro kiekvieną puslapį visiškai iš
  naujo sukuria iš matomo „PDFium" vaizdo. Į naują minimalų failą
  patenka tik šis vaizdo puslapis ir naujai sukurtas, OCR tekstu
  apribotas paieškos sluoksnis – ne svetimas objektų medis su
  komentarais, priedais, veiksmais, sluoksniais, metaduomenimis, spalvų
  profiliais ar privačiais raktais. Tai galioja ir turiniui anotacijų
  išvaizdose, raštuose, „Type-3" šriftuose, formos objektuose ir
  minkštosiose kaukėse. Šaltinio failas lieka nepaliestas.

- **Veidai ir kodai įdėtoje PDF grafikoje buvo praleisti.** Abu
  detektoriai dabar papildomai mato pilną atvaizduotą puslapio vaizdą.
  Dėl to portretai ir QR/brūkšniniai kodai anotacijose, raštuose,
  „Type-3" glifuose ir permatomumo kaukėse pasiekia detektorius;
  atpažintos sritys – jei įjungta – padaromos neatpažįstamos prieš
  minimalią struktūrą. Pats atpažinimas ir toliau gali klysti.

- **Trūkstamas OCR variklis PDF failuose baigdavosi vidine klaida.**
  Maksimalus paleidimas dabar valdomai nutrūksta ir be tikslinio failo,
  vietoj neišbaigto ar nepatikrinto failo pateikimo.

- **Keli tikri kontaktų ir verslo duomenys prasmukdavo, kol buvo
  keičiamas dalykinis tekstas.** Vardo laukai per eilučių lūžius, banko
  ir įmonių pavadinimai, teisinės formos, paženklinti identifikaciniai
  numeriai, gimimo datos bei telefono, URL ir IBAN ribos tikrinamos
  griežčiau. Kartu šalys dalykiniame tekste, vaidmenų ir bendriniai
  žodžiai, prekės/normos kodai, skaičių eilutės ir įprastos santrumpos
  dažniau lieka nepaliesti.

- **Mišrios ir pasuktos OCR eilutės buvo skaitomos neteisingai.**
  Nepatikimi vertikalūs žodžiai dabar vietoje ištiesinami ir perskaitomi
  iš naujo; techninės lotyniškos reikšmės nelotyniškame tekste gauna
  nepriklausomą angliškos kalbos liudytoją. Laisvai stovintis nepatikimas
  vienas skaitmuo taisomas tik tada, kai sutampa du glaudūs skaitmenų
  ruožai. Lenkiškos teisinės formos OCR forma „sp. z 0.0." uždarame
  kontekste skaitoma kaip „sp. z o.o.".

- **Vaizdo matavimas galėjo praleisti iš dalies matomas likusias
  reikšmes.** Jis dabar tikrina persidengiančius vietinius fragmentus,
  atskiria baltą žymiklio šriftą ant juodos juostos nuo originalo
  glifų ir perkelia neapdorotų vaizdų langelius net į pasuktus, iš
  naujo atvaizduotus minimalius PDF failus. Fiksuotas sintetinis
  pagrindinis korpusas dėl to pasiekia 1 392/1 392 pašalintų siektinų
  reikšmių esant 0 klaidingų pavojų ir 0 apdorojimo klaidų. Tai korpuso
  įrodymas, ne bendras 100 % pažadas.

- **Nekomerciniai kalbos modeliai nebesiūlomi.** Šeši itališki ir
  graikiški spaCy variantai pagal CC BY-NC-SA 3.0 pašalinti iš katalogo,
  atsisiuntimo ir įkėlimo kelio; net esami modelio aplankai
  ignoruojami. Abi kalbos vietoj to naudoja MIT licencijuotą daugiakalbį
  modelį.

- **Vardas po „Ansprechpartner" buvo pašalinamas tik iš dalies.** Jei
  užrašas stovi vienas eilutėje, o po juo „Nachname Vorname", vardas
  likdavo, kai jis kartu yra ir įprastas žodis – iš „Mayer Roman" tapdavo
  „[NAME_1] Roman". Tokios eilutės dabar imamos visos. Skyrius toje
  pačioje vietoje („Technischer Innendienst") ir toliau lieka nepaliestas.
  Beje, taip pat ištaisyta: „Ansprechpartner" apskritai nebuvo laikomas
  vardo lauku, nors „Kontaktperson" tokiu yra nuo seno.

- **Įmonės pavadinimas be teisinės formos likdavo, kai tarp jo ir
  konteksto stovėjo pramonės žodis.** „Kranzbichler Handels GmbH" buvo
  pašalinama, plikas „Kranzbichler" trimis pastraipomis vėliau – ne, o
  „Kranzbichler GmbH" – taip. Dabar veikia abu atvejai. Įprasti žodžiai
  neįtraukiami: „Deutsche Bank AG" nepaverčia „deutsche" tekste įmone.

- **Ta pati reikšmė tame pačiame dokumente kartą vadinosi vardu, kartą
  vietove.** „Anna Musterfrau … Musterfrau" davė „[NAME_1]" ir „[ORT_1]" –
  antroje vietoje trūksta vardo, ir be jo tai tapo vietove. Abu atvejai
  buvo pašalinti, tačiau tai skaitėsi kaip du skirtingi dalykai. Reikšmė
  dabar išlaiko savo pirmo pasirodymo pavadinimą.

- **Datos nebebuvo pašalinamos.** Data, sudaryta vien iš skaitmenų
  („01.03.2026"), nuo paskutinės versijos krisdavo per patikrą, skirtą
  vardams, ir likdavo dokumente – ir maskavimo veiksenoje „perkelti", be
  eilutės patikros ataskaitoje. Tai paveikė tik tuos, kas aiškiai buvo
  įjungę datos atpažinimą.

- **Šalys ir žemynai daugiau nebeuztamsinami.** „Die Lieferung geht in
  die Vereinigten Staaten", „Marktschwäche in Asien", „die Norm gilt in
  Rumänien" – tokie duomenys nieko nepasako apie asmenį ir dabar lieka.
  Jei šalies pavadinimas priklauso adresui arba stovi po užrašu kaip
  „Wohnsitz" ar „Geburtsort", jis ir toliau pašalinamas. **Miestai
  nepaveikti** – „Ich bin gerade in Bilbao" lieka duomuo apie asmenį ir
  toliau užtamsinamas.

- **Sutrumpinti žodžiai tapdavo tinklalapio adresais.** Jei tekste stovi
  „bzw. deutsche" arba „incl. der", kai kurie PDF failai pateikia tašką
  be tarpo – iš to gaudavosi „bzw.de" ar „incl.de", galiojantis adresas
  su šalies galūne, ir jis būdavo pašalintas. Tokios žodžių poros dabar
  lieka. Tikri adresai nepaveikti, taip pat ir be „www." prieš juos.

- **Skaičių stulpeliai iš balansų buvo užtamsinti kaip telefono
  numeriai.** Verslo ataskaitose ir kainoraščiuose praėję ir einami metai
  stovi vienas šalia kito – „64.518 65.133". Tai buvo laikoma vienu
  telefono numeriu ir pašalinama, taip pat skaičių intervalai kaip
  „12200-23200" ir data su po jos einančiu skaičiumi. Tokie skaičiai
  dabar lieka. Priešingai, tikras telefono numeris atpažįstamas
  patikimiau: užrašai „Telefon", „Fax", „Mobil", „Durchwahl" ir jų
  atitikmenys kitose sąsajos kalbose dabar taip pat skaičiuojami –
  anksčiau programa ten atpažindavo tik angliškus žodžius.

- **Vardai sunumeruotoje lentelėje likdavo.** Dalyvių ar personalo
  lentelė įprasta forma – stulpelio antraštė, po ja „1.1 Auersperg
  Bernhard Montage 03.03.2026" – iš viso nebūdavo valoma: tokios eilutės
  atrodė kaip pasiūlymo pozicijų sąrašas, kuriame dalykiniai terminai
  turi likti. Jei stulpelio antraštė turi asmens užrašą („Name",
  „Nachname", „Surname" …), eilutės po ja dabar laikomos vardais.
  Pozicijų sąrašai lieka nepaliesti kaip anksčiau – net kai firminiame
  blanke stovi „Sachbearbeiter:".

- **Iš vieno vardo kartais gaudavosi du žymikliai šalia.** Jei pavardė
  dokumente stovėjo ir atskirai, tolesnis apdorojimas tokioje vietoje
  kaip „Anna Musterfrau GmbH" pirma pakeisdavo pavardę, po to vardą –
  rezultate tai atrodė kaip du skirtingi asmenys. Dabar laimi ilgiausias
  žinomas vardas.

- **Sugalvotos reikšmės nestovėjo jokioje priskirtyje.** Kas pasirinko
  „Sugalvoti reikšmes", gaudavo rezultatą, kuriame „Anna Musterfrau" tapo
  „Greta Mayrhofer" – priskirtyje apie tai nieko nestovėjo, kai tik tame
  pačiame dokumente pasitaikė nors vienas anoniminis pakeitimas. Dėl to
  jokios sugalvotos reikšmės nebuvo galima grąžinti, o priskirčių failas
  nutylėjo pakeitimą. Pavojingiausia buvo trečia dalis: kas skaito
  rezultatą, mato tikėtiną vardą ir neturi jokio ženklo, kad jis
  sugalvotas. Dabar kiekvienas pakeitimas stovi priskirtyje.

- **Priskirtis užtamsintą dalyką vadino „pakeista".** El. laiškas
  dalijasi priskirtimi su savo priedais, o priedą galima užtamsinti, kol
  laiško tekste stovi žymiklis. Priskirtyje visoms trims vietoms tuomet
  stovėjo tas pats – „pakeista" –, o grąžinimas priede ieškojo
  žymiklio, kurio ten nėra: juosta likdavo. Dabar kiekvienai radimo
  vietai parašyta, kas ten iš tikrųjų įvyko, ir abu priedai grįžta.

- **Reikšmių, esančių tik vaizde, nebuvo galima grąžinti.** Radimo
  skydelyje jos stovėdavo dukart – kartą kaip žymiklis, kurio dokumente
  niekur nebuvo („Žymiklis dokumente nerastas"), kartą kaip užtamsinta
  vieta. Pirmoji eilutė buvo gryna apskaita ir dingo.

- **Užtamsintas reikšmes buvo galima grąžinti tik kartą.** Jei ta pati
  reikšmė stovi keliose vietose, vienas spustelėjimas grąžina visas –
  tačiau likusios eilutės likdavo radimo skydelyje, ir kitas spustelėjimas
  ant jų pranešdavo „Nevienareikšmiška". Jos dabar dingsta kartu.

- **Grąžinimai trūko patikros žurnale, kai mokymosi veiksena buvo
  išjungta.** Kas taisymo lange atkūrė grąžintą reikšmę, po to
  neberasdavo šio veiksmo patikros žurnale, kai tik mokymosi klausimai
  buvo išjungti – įrodymas priklausė nuo jungiklio, kuris skirtas tik
  taisyklių pasiūlymams. Esant įjungtam patikros žurnalui, dabar
  nepriklausomai nuo to klausiama priežasties ir įrašoma eilutė.

- **Įtempti failai likdavo neišvalyti – ir apie tai net nebūdavo
  pranešama.** Kas tempia failą į dokumentą, o ne siunčia jį kaip priedą,
  tam „Word" ar „PowerPoint" jį visiškai patalpina dokumente. Jis po to
  nepakitęs stovėdavo rezultate, kartu su pradiniu failo pavadinimu ir
  saugojimo keliu – o šie praktikoje dažnai patys turi vardą. Tokie
  failai dabar valomi kaip ir likęs dokumentas.

- **Ir kur to padaryti negalima, Maskuro tai pasako.** Jei įterptame
  objekte yra senas formatas („Word 97", „Excel 97"), kuriam nėra
  valymo, dabar rodomas DĖMESIO pranešimas su failo pavadinimu. Anksčiau
  jis buvo tyliai perduodamas nepakitęs.

- **Suplėšyti žodžiai ir santrumpos buvo laikomos vardais.** Kai žodis
  PDF faile eilutės gale perskirtas, kai kurių failų skaitymas duoda
  fragmentą – „Jahresent… gelts", „Gewerbli…". Tokie fragmentai,
  sulipę žodžiai („TürverschlussmitV") ir plikos santrumpos („JY", „FFB")
  buvo užtamsinamos kaip vardai. Jos dabar lieka. Vardas su tuo pačiu
  perskyrimo pažeidimu ir toliau užtamsinamas, kol yra kreipinys – o
  vardai, kurie savaime turi didžiąją raidę žodžio viduryje (McKenzie,
  MacDonald, LeBlanc), dėl to apskritai nepaveikti.

- **Matmenų nurodymai ir mėnesiai buvo laikomi adresu.** Techniniuose
  dokumentuose buvo užtamsinami „2000 Lux", „1200 Mbit", „1500 Watt",
  „5308 Platz" ir „2022 Mrz" – keturi skaitmenys ir didžiąja raide
  rašomas žodis atrodė kaip pašto kodas su vietove. Pašto kodas dabar
  skaičiuojamas tik tada, kai kartu yra adreso ženklas: šalies žyma,
  lauko užrašas, eilutės pradžia, gatvė eilutėje virš arba vietovė,
  kurią ten mato ir kalbos atpažinimas. Penkiuose darbų sąrašuose dėl to
  dingsta 14 klaidingų užtamsinimų, neprarandant nė vieno tikro adreso.

- **Tikslesnis atpažinimas keitė per daug.** Papildomai įjungiama
  pakopa „tikslesnis atpažinimas" vokiškuose verslo dokumentuose
  dalykinius terminus laikė vardais ir vietovėmis – „Photovoltaikanlage",
  „Einspeisepunkt", „Flachdach", „Personaleingang" – ir užtamsindavo
  įmonių pavadinimus iš einamų pozicijų sąrašų. Priežastis buvo
  apsauga: jos radiniai buvo neįtraukti į patikras, atpažįstančias
  pozicijos ar sąrašo eilutę. Ši apsauga dabar galioja tik daugiadalyviams
  vardams, kuriems pakopa ir skirta – „Anna Huber" sąrašo eilutėje taigi
  ir toliau atpažįstama, o pavienis dalykinis žodis pozicijos eilutėje
  iškrenta. Techniniame konkurse tai perpus sumažina pakopos klaidingus
  užtamsinimus, neprarandant nė vieno vardo.

- **Diagramos atsinešdavo pilnus šaltinio duomenis – nepatikrintus.**
  Kas „Word" ar „PowerPoint" faile įterpia schemą, tam programa į
  dokumentą kaip atskirą failą patalpina lentelę, iš kurios ji
  apskaičiuota. Matomi iš jos tik keli skaičiai schemoje; lentelėje
  stovi visas sąrašas, įskaitant eilutes, kurių schemoje visai nėra. Ši
  lentelė iki šiol būdavo perduodama nepakitusi. Ji dabar taip pat
  valoma, tais pačiais žymikliais kaip likęs dokumentas.

- **Tas pats galioja įterptiems objektams „OpenDocument" failuose**
  (ODT, ODS, ODP): įterpta schema ar įterpta lentelė likdavo nepaliesta.

- **„Word" dokumentai: išnašos ir baigiamosios išnašos nebuvo
  valomos.** Jų tekstas rezultate likdavo pilnas – taip pat vardai,
  adresai ir sąskaitų numeriai. Paveiktas buvo kiekvienas „Word"
  dokumentas su išnaša ar baigiamąja išnaša. Taip pat nepaliestas
  likdavo automatinio teksto blokas, kuris nematomai keliauja su
  dokumentu.

- **„Word": duomenys pasirinkimo sąrašuose, komentaruose ir vaizdų
  aprašymuose.** Pasirinkimo lauko įrašai (matomi tik atskleidus),
  komentaro autorius, brėžinio aprašymas ir adresas po nuorodos komanda
  toliau stovėjo rezultate.

- **„Excel": suvestinė lentelė antrą kartą įtraukė pradinius
  duomenis.** Knyga su suvestine lentele joje saugo pilną apdorotų
  eilučių kopiją – nematomą, bet faile. Ši kopija anksčiau likdavo
  nepakitusi, net jei pačiame lape viskas buvo pakeista. Paveiktas buvo
  kiekvienas analizė, perduodama su suvestine lentele.

- **„Excel": pokalbio komentarai ir jų autoriai.** Naujesnio tipo
  komentaro tekstas ir komentuotojų sąrašas – rodomas vardas ir
  prisijungimo žyma, įmonėse dažniausiai el. pašto adresas – toliau
  stovėjo rezultate. Tas pats sąrašas ir „Word" dokumentuose.

- **Savų dokumento savybių „Word" ir „Excel" failuose.** Laukai kaip
  „Mandant" ar „Aktenzeichen", kuriuos kanceliarija priduoda savo
  šablonams, iki šiol nebuvo valomi. Jie nematomi jokiame rodinyje ir
  vis tiek keliauja su kiekviena kopija.

- **Lentelės (ODS): langelio pasirinkimo sąrašas.** Kaip ir „Excel" nuo
  ankstesnės versijos, dabar valoma ir „OpenDocument" lentelėse tai, kas
  pasirodo atskleidus langelį. Nuorodos į kitus langelius lieka
  nepaliestos, kad sąrašas toliau veiktų.

Visas šias vietas kaip įprasta galima grąžinti per priskirtį.

- **„Outlook" žinutės: sugadintas failas visiškai nutraukdavo valymą.**
  Tam tikri sugadinti `.msg` failai sukeldavo nutraukimą vietoj
  pranešimo; dabar jie perskaitomi tiek, kiek yra įskaitomi.

- **Priskirčių failas dabar įskaitomas tik jums.** Jame paprastu tekstu
  yra originalūs duomenys, ir iki šiol jis gulėjo šalia rezultato su
  įprastomis teisėmis – bendroje saugykloje jį galėjo atverti bet kas.
  Pačiame išvalytame rezultate niekas nesikeičia – jis juk turi būti
  perduodamas toliau.

- **Atsisiųsti kalbos modeliai prieš išpakavimą dabar tikrinami
  tiksliau.** Suklastotas paketas – pavyzdžiui, iš įmonės bendrinamos
  vietos, kuria naudojasi keletas darbo vietų – išpakuojant galėjo
  patalpinti failus už numatyto aplanko ribų. Įprastas atsisiuntimas
  nepakitęs.

- **Padaryti ekrano nuotrauką – ir ji iš karto išvaloma.** Su
  `Ctrl+Shift+B`, per „Failas → Padaryti ekrano nuotrauką …" arba tempiant
  užduočių juostos piktogramą, ištempiate rėmelį per ekraną. Kas jame
  yra, po to eina tuo pačiu keliu kaip bet kuris kitas failas: teksto
  atpažinimas perskaito ekrano tekstą, vardai, adresai, telefono numeriai
  ir el. pašto adresai užtamsinami, o po to vaizdas atveriamas
  redaktoriuje, kur rėmeliu galite papildomai užtamsinti tai, kas buvo
  praleista. Išvalytas vaizdas atsiduria darbalaukyje (arba jūsų
  nustatytame išvesties aplanke); **žalia** nuotrauka niekur
  nepatalpinama ir uždarant ištrinama. Teksto atpažinimas šiam paleidimui
  įjungiamas, net jei kitaip jis išjungtas – be jo vaizde nieko nebūtų
  galima rasti. „Mac" sistemoje pirmą kartą sistema klausia leidimo
  „ekrano įrašymas".

- **Ant vaizdų dabar galima piešti: stačiakampį, elipsę, rodyklę, tekstą
  ir sunumeruotus žingsnių žymeklius.** Šešiomis spalvomis ir trimis
  linijos storiais, pasirenkamais klavišais nuo 1 iki 5. Tai skirta
  ekrano nuotraukoms ir instrukcijoms: parodyti, kas svarbu, neatidarant
  dėl to antros programos. Anuliavimas ir tempimas už rankenėlių galioja
  kaip bet kuriai juostai – pastabą taigi galima perkelti ir ištempti
  jau po to, kai ji nustatyta.
  **Piešimas sąmoningai nėra užtamsinimas.** Nupieštas stačiakampis yra
  rėmelis, ne juosta: kas po juo stovi, lieka įskaitoma ir iškeliauja su
  failu. Duomenims pašalinti ir toliau skirti „Užtamsinti" ir
  „Pikselizuoti"; piešimo įrankiai dėl to stovi atskiroje įrankių
  juostos eilutėje, o nuorodos eilutė tai sako, kol vienas iš jų
  pasirinktas.

- **Redaguotas vaizdas vienu spustelėjimu patenka į mainų sritį.**
  „Kopijuoti vaizdą" redaktoriuje (arba `Ctrl+C`) jį patalpina tokį, koks
  yra – pakanka įklijuoti, kad jis atsidurtų žinutėje ar laiške. Taip
  kelias nuo klavišo paspaudimo iki pokalbio yra keturi žingsniai ir
  nereikia jokio aplanko.

- **Prie to teksto žymeklis, šešėlis ir gradientai.** „Paryškinti"
  nudažo sritį, jos neuždengdamas – turinys po ja lieka įskaitomas, ir
  būtent tuo jis skiriasi nuo juostos. „Šešėlis" atskiria pastabą nuo
  neramaus fono, „Gradientas" leidžia spalvai išblukti tempimo kryptimi;
  abu galioja visiems šešiems piešimo įrankiams.

- **Ištaisyta, prieš kam nors užkliūnant:** naujoji įrankių eilutė būtų
  atrodžiusi beveik tuščia kiekvienam, kas Maskuro jau naudojo –
  įsimintas lango išdėstymas buvo iš laiko prieš tai ir nebūtų jai
  palikęs vietos. Pasenęs išdėstymas dabar atmetamas; redaktoriaus langas
  tada vienkartinai stovi savo pagrindiniu išdėstymu.

- **Savo ekrano nuotrauką galima išjungti.** Kas įpratęs prie
  „Greenshot", „ShareX" ar iškirpimo įrankio, po „Nustatymai → Programa"
  išjungia „Daryti ekrano nuotrauką su Maskuro". Maskuro tada iš viso
  neregistruoja klavišų derinio – jis lieka jūsų įrankiui –, ir
  pakeitimas galioja iš karto, be paleidimo iš naujo. Taip padarytą
  vaizdą ir toliau galima valyti: Ctrl+V jį iš mainų srities atneša į
  langą.

## 0.10.37-alpha.20260821 – 2026 m. rugpjūčio 21 d.

### Nauja

- **Anonimizuojant kiekviena rasta vieta dabar turi savo numerį.**
  Iki šiol visi asmenys vadinosi `[NAME]`, visos vietovės `[ORT]` – todėl
  nebuvo galima pasakyti, kuri vieta priklauso kuriai reikšmei, ir nebuvo ką
  atkurti. Dabar numeriai skaičiuojami toliau kiekvienam pasikartojimui:
  tas pats vardas trijose vietose žymimas kaip `[NAME_1]`, `[NAME_3]` ir
  `[NAME_7]`. Dokumente vis tiek nesimato, kurios vietos susijusios – tačiau
  su priskyrimo failu galima atkurti kiekvieną atskirai. Todėl priskyrimo
  failą vėl galima pasirinkti ir anonimizuojant; laikykite jį atskirai nuo
  rezultato.
- **Mėnesiai, savaitės dienos, valiutos, matavimo vienetai ir įmonių
  teisinės formos visose 48 dokumentų kalbose nebelaikomi vardais ar
  vietovėmis.** Kalendoriaus ir vienetų pavadinimai gaunami iš Unicode
  CLDR (sugeneruoti, ne parašyti ranka), teisinės formos – iš šalių
  bendrovių teisės – taip pat daugiažodės („sp. z o.o.", „Pty Ltd") ir
  einančios priekyje („株式会社"). Kai mėnesio pavadinimas kartu yra ir
  vardas (Juli, August, May), sprendžia forma: šalia dienos ar metų – data,
  kitaip – vardas. Be to, kreipiniai ir titulai, ištisos pasisveikinimo
  formulės, dokumentų rūšys ir gatvių pagrindiniai žodžiai 28 kalboms su
  savu kalbos modeliu, teisės aktų santrumpos (DSGVO, UStG, ABGB,
  § 6 Abs 1 Z 27 UStG), taip pat kalbų pavadinimai kaip lauko reikšmė
  („Sprache: Deutsch"). Sąrašai pateikiami „Pagalba → Žodžių sąrašai …".
- **Indija: atpažįstamas adresas ir PIN kodas** – „15 गांधी मार्ग",
  „नई दिल्ली 110001", taip pat „15 Gandhi Marg, New Delhi 110001". Indijos
  šalies paketas iki šiol pažino tik identifikacinius numerius; hindi
  kalbos dokumentuose adresai todėl likdavo.
- **Kiekvienas išvalytas biuro failas prieš pateikimą dar kartą atidaromas
  kaip paketas.** Teksto ištrauka nepastebi, jei Word, Excel ar LibreOffice
  failo atsisakytų atidaryti (dvigubas įrašas, nutrūkęs XML, trūkstama
  dalis). Ir skaičiuojama pagal originalą tai, ko valymas niekada negali
  keisti: PDF puslapiai, lentelės lakštai, eilutės ir langeliai, pristatymo
  skaidrės. Jei patikra suveikia, rezultate ir patikros ataskaitoje
  atsiranda DĖMESIO įspėjimas – originalas lieka nepakeistas.
- **Automatika taip pat švarina visą lauką.** Švarinimo režimu trumpose
  eilutėse – adreso bloke, lentelės langelyje, antraštiniuose
  duomenyse – juosta dengia visą eilutę, o ne tik rastą reikšmę: žodžio
  ilgio juosta atskleistų, koks ilgas buvo žodis. Šalia esantys užrašai ir
  sumos lieka matomi, o ištisinio teksto eilutės (ilgesnės nei pusė teksto
  pločio) toliau švarinamos žodžio tikslumu, kad vardas sakinio viduryje
  nepaverstų juodu viso sakinio.
- **Atkurta reikšmė vėl atrodo kaip originale.** „Atkurti originalą" ir
  „Atšaukti pakeitimą" PDF redaktoriuje dabar tiksliai grąžina sritį iš
  šaltinio failo – tas pats šriftas, tas pats dydis, ta pati spalva ir
  padėtis, skenuotame dokumente – tie patys pikseliai. Iki šiol tekstas
  buvo iš naujo įdėtas pakaitiniu šriftu ir atrodė pastebimai atkurtas.
  Ankstesnio švarinimo juosta tuo metu visiškai išnyksta, o ne užtapoma
  baltai – lentelės spalvotas langelio fonas išlieka. Tai galioja ir
  pasuktuose puslapiuose, tekstui iš įterptų formos objektų ir
  **užpildytiems formos laukams**: tam skirtoje sugeneruotoje darbinėje
  kopijoje ištrauka grąžinama iš naujai atvaizduoto originalo puslapio –
  net ten, kur jokia teksto sluoksnio dalis nežino lauko reikšmės. Taip pat
  **pakeisti paveikslėliai** PDF faile grąžinami šitaip – suprastintais
  pikseliais, suliejimu ar visiškai pašalinti, visas arba tik pažymėta
  ištrauka. Tik ten, kur šaltinio failo šalia rezultato nebėra, lieka
  senasis kelias.
- **Sušvarintas ir be pakaitalo pašalintas reikšmes galima atkurti taip pat
  Word, Excel, PowerPoint ir OpenDocument failuose.** Iki šiol atšaukimui
  tenai reikėjo pakaitalo tekste – juosta ar tarpas neturėjo atgalinio
  kelio. Dabar radinių skydelis siūlo eilutes „sušvarinta" ir „pašalinta",
  kai tik nepaliestas šaltinio failas guli šalia rezultato: Maskuro
  palygina rezultatą su originalu ir įrašo reikšmę atgal juostos ar tarpo
  vietoje – kartu su formatavimu, suskaidytas ruožas vėl tampa vientisas.
  Tai galioja taip pat tekstui, HTML, el. laiškui ir el. laiško Office
  priedams; jei laiško tekste yra pakaitalas, o priede – juosta, abu
  atkuriami vienu žingsniu.
- **Taip pat PDF priedus el. laiške ar Outlook pranešime galima
  atkurti** – pakaitalus (sunumeruotus ir anoniminius), juostas ir be
  pakaitalo pašalintus. Be lango vieta gaunama iš originalaus priedo;
  atgal reikšmė grįžta tiksliai pagal glifus, originalo skaitymo tvarka.
- **Užmaskuotas reikšmes galima atkurti** – tiek PDF, tiek teksto rodinyje.
  Kaukė („**** **** **** **** 3201") niekada nėra vienareikšmė, du
  numeriai gali turėti tą pačią; todėl atkūrimas niekada nevyksta
  pažodžiui, o klausia originalo, kokia reikšmė buvo šioje vietoje. Iki
  šiol šios eilutės radinių skydelyje visai nebuvo veikiamos.
- **Įterptus paveikslėlius Word, Excel, PowerPoint ir OpenDocument
  failuose galima atkurti.** Paveikslėlyje sušvarinta reikšmė grąžinama
  per savo skydelio eilutę – Maskuro nuskaito originalų paveikslėlį ir
  paima būtent šią vietą; suliejęs, pašalintas arba veidais ir kodais
  apdorotas paveikslėlis atkuriamas kaip visuma per naują punktą „Atkurti
  įterptus paveikslėlius" meniu Redaguoti – taip pat per el. laiško ar
  Outlook pranešimo Office priedus. Paveikslėlis, kuris pats yra priedas
  ir buvo sušvarintas per teksto atpažinimą, taip pat atkuriamas per savo
  skydelio eilutę.
- **Sugalvotas reikšmes galima atkurti teksto rodinyje.** Iki šiol
  skydelis tenai rodė „Nevienareikšmė". Dabar atkūrimas ieško reikšmės
  originale ir toje pačioje rezultato vietoje reikalauja būtent
  sugalvoto pakaitalo – sugalvotas vardas niekada nekeičiamas pažodžiui
  visur, jis galėtų kur nors būti tikras.
- **Atkūrimas Word, Excel, PowerPoint ir OpenDocument failuose išlaiko
  originalo formatavimą.** Jei reikšmė buvo keliuose ruožuose – „Anna"
  paprastu šriftu, „Musterfrau" paryškintu ir raudonu –, iki šiol ji
  grįždavo visa į pirmąjį ruožą ir prarasdavo paryškinimą bei spalvą.
  Dabar simboliai vėl pasiskirsto kaip originale; Word pastraipa po to yra
  baitas po baito tokia pati kaip pirminė. Tas pats galioja HTML puslapiams,
  el. laiško HTML daliai ir Outlook pranešimo (.msg) HTML kūnui – prie
  el. laiško papildomai išsaugomas doctype, kurį valymas iki šiol tyliai
  pašalindavo.
- **Tekstiniai failai išlaiko savo koduotę.** Valymas ir atkūrimas dabar
  įrašo `.txt`, `.md` ir `.csv` ta koduote, kuria jie buvo pateikti – UTF-8
  su BOM ir be jo, UTF-16, Windows-1252. Iki šiol Windows-1252 failas
  visada tapdavo UTF-8, o UTF-16 failas grįždavo sugadintas, net jei jame
  nebuvo ko keisti.
- **Atkurti paveikslėliai išlaiko savo spalvų režimą.** Pilkų atspalvių
  skenas grįžta kaip pilki atspalviai, o ne tris kartus didesnis RGB
  failas, paletė lieka paletė, juoda-balta lieka juoda-balta – visas
  paveikslėlis su tomis pačiomis reikšmėmis kaip originale. Galioja
  paveikslėlių failams ir paveikslėliams PDF dokumentuose. CMYK ir 16 bitų
  lieka RGB, nes PNG rezultatas negali perteikti nei vieno, nei kito.
- **Rėmelis paveikslėlyje atkuria visą redagavimą, kurio jis liečia.**
  Suprastinti veidai turi kraštą aplink aptiktą dėžę; kas rėmelį traukė
  tik per veidą, gaudavo suprastintą žiedą. Dabar rėmelis auga iki visos
  susijusios permainos nuo originalo – užtenka rėmelio virš akių srities.
  Atskiros greta esančios juostos lieka; visiškai pašalintai ar visiškai
  suliejamai nuotraukai toliau galioja nutrauktas rėmelis. Galioja
  paveikslėlių failams ir paveikslėliams PDF dokumentuose.
- **Švarinimo juosta per visą eilutę.** Redaktoriaus eilutės režime juosta
  dabar tęsiasi nuo pirmo iki paskutinio eilutės žodžio, o ne tik per
  rastą žodį – žodžio ilgio juosta atskleistų, koks ilgas buvo žodis, o
  iš šešių simbolių prieš pašto kodą galima nuspėti vietovės pavadinimą.
  Šalia reikšmės esantys užrašai, sumos ir lentelės stulpeliai lieka
  matomi – juosta dengia lauką, ne visą sąskaitos eilutę. Naujas
  jungiklis „Visa eilutė" šalia „Teksto eilutės" leidžia vėl grįžti prie
  žodžio tikslumo, jei kaimyniniai žodžiai turi likti; pasirinkimas
  įsimenamas.

### Ištaisyta

- **Paveikslėliai HTML puslapiuose ir el. laiškuose likdavo nepatikrinti –
  vardas logotipe po valymo liko įskaitomas.** Į puslapį įterptas
  paveikslėlis (``data:`` adresas) apskritai nebuvo liečiamas, tik jo
  alternatyvus tekstas; laiško HTML šakos logotipas (įterptas
  paveikslėlis be failo vardo) neprasmuko per priedų filtrą; o vardiniam
  paveikslėlio priedui paveikslėlio taisyklė „suliejimas"/„pašalinimas"
  neveikė. Dabar visi trys eina tuo pačiu keliu kaip paveikslėlio failas:
  teksto atpažinimas išsaugotame paveikslėlyje, veidai, kodai, metaduomenys
  ir paveikslėlio taisyklė. Ataskaitoje nurodomi paveikslėliai – taip pat
  įspėjimas, jei jie lieka nepatikrinti be teksto atpažinimo, – o „Atkurti
  įterptus paveikslėlius" ir atkūrimas iš radinių skydelio šiuos
  paveikslėlius taip pat atpažįsta.
- **Biuro failo su paveikslėliu apskritai nepavykdavo išvalyti, jei teksto
  atpažinimas nemokėjo kalbos.** Mac sistemoje skaito sisteminis teksto
  atpažinimas; hindi, graikų, kroatų ar lietuvių kalbai jis to negali ir
  neseniai pradėjo tai ir pranešti – tačiau Word, Excel, PowerPoint ir
  OpenDocument failuose dėl to nutrūkdavo **visas** valymas ir failas
  nesusikurdavo. Tuo tarpu tekstą buvo galima puikiai išvalyti; tik
  paveikslėlis buvo neįskaitomas. Dabar failas įrašomas taip pat kaip PDF
  ir pavieniai paveikslėliai, o rezultate parašoma, kad paveikslėliai
  NEBUVO patikrinti – su priežastimi ir nuoroda į „Tvarkyti kalbas".

- **Excel knygose vardai likdavo pasirinkimo sąrašuose.** Išskleidžiamojo
  lauko (duomenų tikrinimo) sąrašas dabar valomas kaip ir bet koks kitas
  langelio turinys; nuorodos į langelių sritis lieka nepaliestos, kad
  knyga liktų sveika.
- **Kur pakaitalas netilpo, stovėjo juoda juosta – dabar stovi trumpesnis
  užrašas.** `[GEBU_1]` vietoj `[GEBURTSDATUM_1]`, ir tik kai net
  trumpiausia forma nebetelpa, švarinama juosta. Juosta niekam nebepasako,
  kad ten kažkas buvo; trumpas pakaitalas – pasako. Taisymo redaktorius tai
  jau mokėjo, savaiminis valymas – iki šiol ne. Priskyrimo failas abu
  užrašus sieja su ta pačia reikšme, kad ir sutrumpintą būtų galima
  atkurti.
- **Pirmasis paspaudimas ant „Pakeisti" trumpam sustabdydavo Taisymo
  langą.** Atpažinimas, kuris pakaitalui suteikia jo rūšį (`[NAME_3]`
  vietoj `[BEGRIFF_3]`), buvo įkeliamas būtent šią akimirką – maždaug
  dvi–tris sekundes. Dabar jis paruošiamas fone atidarant langą; matuota
  iš 2289 milisekundžių tapo 193.
- **Du vienalaikiai valymai galėjo dukart įkelti tą patį kalbos modelį** –
  pavyzdžiui, aplanko stebėjimas ir pagrindinis langas. Kadangi kiekvienas
  modelis užima kelis šimtus megabaitų, atminties poreikis trumpam
  siekdavo dvigubą kiekį. Dabar antrasis paleidimas laukia pirmojo
  modelio.
- **Vietovė datos eilutėje dabar pašalinama ir tada, kai kalbos modelis jos
  vienas neatpažįsta:** kas patikimai rastas kaip pašto kodas su vietove
  („3335 Amstetten"), tas vietovės pavadinimą traukia paskui save visame
  dokumente – kaip pavardė iš pilno vardo. O santrumpa su skaitmeniu prieš
  vardą („T3 Hofbauer Christian") lieka įskaitoma, o ne dingsta kartu su
  pakaitalu.
- **Uždaryti trys nutekėjimai iš tikro užsakymo antrosios peržiūros:**
  sachbearbeiteris „T3 Hofbauer Christian" dėl santrumpos „T3" laikytas
  stulpelio antrašte ir liko įskaitomas; vietovė, kurią kalbos modelis
  perskaitė per eilutės lūžį iki pat stulpelio antraštės, prarijo „Pos." ir
  paliko kliento vardą; o vardas su kreipiniu („Herr Robert Köttel")
  patraukė paskui save tik pavardę, ne vardą – o už tai kiekvieną „Herr".
  Dabar santrumpos yra tik raidės, dviejų žodžių vardai nėra antraštė,
  radiniai nukertami prieš stulpelio antraštę, o kreipinys nepriskiriamas
  vardui.
- **Vietovė datos eilutėje („Melk, 05.08.2026") tiesiai po adreso bloko
  liko įskaitoma.** Kalbos modelis ją sulipdė su pašto kodo eilutės
  vietove į vieną radinį, o šis kaip visuma nesutapo su pašto kodo
  šablonu. Dabar likusi dalis lieka atskiru radiniu. Rasta per naują
  rezultato antrąją peržiūrą (`werkzeuge/zweitlesung.py`).
- **Mac: skenas kalba, kurios sisteminis teksto atpažinimas nemoka (pvz.,
  hindi, graikų, kroatų, lietuvių), buvo laikomas patikrintu.** Buvo
  skaitoma anglišku atsarginiu variantu, svetimas raštas liko paveikslėlyje,
  o ataskaita sakė „nieko nerasta". Dabar rašoma „Paveikslėlis(-iai) NEBUVO
  patikrinti" su priežastimi, o kalbų valdymas tokioms kalboms nebežada
  teksto atpažinimo vien todėl, kad guli Tesseract kalbos failas.
- **PDF faile skyrybos ženklas po pakeistos reikšmės lieka vietoje.** Iš
  „Aufnahme am 01.03.2026, Entlassung am 04.03.2026." iki šiol gaudavosi
  „Aufnahme am [DATUM_1] Entlassung am [DATUM_2]" – kablelis ir taškas
  pabaigoje dingdavo, tiek su pakaitalais, tiek su perkeltomis datomis.
  Dabar pašalinama tik atpažinta reikšmė, ne visas žodis iki kito tarpo;
  kablelis, kabliataškis, taškas ar skliaustelis po jos lieka savo vietoje,
  o pakaitalas jų neperbraukia.
- **Rusų ir ukrainiečių kalbos nepastebimai veikdavo su silpnesniu
  daugiakalbiu modeliu**, jei trūko pagalbinio žodžių formų analizės
  paketo (`pymorphy3`) – savi modeliai tada nepasikraudavo, ir „Львів" tapo
  asmeniu. Vardų atpažinimui žodžių formų analizė nebūtina; modelis dabar
  kraunamas be jos, ir vietovės vėl yra vietovės.
- **Licencijos nuorodos 16 kalbų buvo pasenusios.** Ten dar buvo rašoma,
  kad MPL šaltinio kodas teikiamas „pagal pareikalavimą", QPDF laikytas
  MPL-2.0, lentelėje trūko septynių komponentų (wordfreq, Qt, ONNX
  Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), spaCy pastraipa buvo
  angliška, o pabaigoje kabojo angliškas pakaitinis skyrius. Dabar visos
  18 versijų atitinka vokiškos versijos lygį: šaltinio archyvai nuolat
  saugomi adresu maskuro.com/quellcode/oss/, QPDF – Apache-2.0, Qt LGPL
  kelias, modelių kilmė. Taip pat angliškoje lentelėje yra trūkstamos
  eilutės.

- **Sutarties žodžiai kilmininku („des Angebotsinhaltes", „des Anbotes",
  „des Terminplanes") nebelaikomi vietove.** Pavienis žodis po kilmininko
  ar naudininko artikelio su linksniuote yra bendrinis žodis – vietovardžiai
  nelinksniuojami („nach Graz"). Jei vietovė dokumente kitur nurodyta be
  artikelio („Burgenland"), toliau atpažįstamas ir „des Burgenlandes".
- **Perkeltos, užmaskuotos ir sugalvotos reikšmės priversdavo rastruoti PDF
  puslapį.** Pašalinimo patikra radinio stačiakampyje leisdavo tik
  pakaitalą laužtiniuose skliaustuose; perkelta data („01.07.2026") ar
  užmaskuota reikšmė („****1234") buvo laikoma nepastebėtu likučiu, ir
  puslapis dėl atsargumo būdavo paverčiamas paveikslėliu – parinkus
  „Pakeisti" – ne. Dabar tokie puslapiai lieka tekstiniai, o atkūrimas iš
  skydelio ar rėmelio vėl grąžina originalą.
- **Daugiažodžių pakaitalų nepavykdavo atkurti PDF faile per radinių
  skydelį.** Sugalvotas vardas („Greta Mayrhofer") ar užmaskuota IBAN
  („**** **** **** **** 3201") sudaryta iš kelių žodžių; radimo paieška
  lygino žodį po žodžio ir pranešdavo „Pakaitalas dokumente nerastas".
  Dabar iš eilės einantys tos pačios eilutės žodžiai sujungiami.
- **Po be pakaitalo pašalintos reikšmės atkūrimo jos eilutė skydelyje
  likdavo.** Reikšmės, kurias strategija „švarinti" pakaitalo režimu
  pašalina be pakaitalo, neturi pakaitalo, pagal kurį skydelis galėtų
  užfiksuoti dingimą. Dabar eilutė ištrinama, kai tik reikšmė vėl atsiranda
  dokumente.

- **Santrumpiniai dūriniai kaip „E-Helfer" ar „U-Bahn" nebelaikomi
  vardu.**
- **Skiemenavimo likučiai („Leis-") ir pernelyg ilgi dūriniai
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator")
  nebelaikomi vardu ar vietove.** Skenuotame konkurso tekste taip
  sušvarinta 28 žodžiais mažiau.
- **Skenuotų pasiūlymų pozicijų sąrašai nebelaikomi vardų sąrašu.**
  Papildomas sąrašų atpažinimo praėjimas (trumpos eilutės) iš „Kälterohr"
  ir „Außengeräte" darydavo asmenis; dabar jis sustabdomas, kai eilutės
  pradžioje yra pozicijų numeriai kaip „1.1.5". Datų eilutės pašto
  susirašinėjimuose tokiais pozicijų numeriais nelaikomos.
- **Skenuotų pasiūlymų stulpelių antraštės ir pozicijų numeriai („Pos.",
  „Pos. 1.1.3", santrumpos „E/L/S") buvo laikomos vardu ar vietove.**
  Santrumpa, vienintelė savo eilutėje, užrašas su numeriu ir pavieniai
  raidiniai simboliai eilutėje tokie nėra.
- **Puslapis „kvėpuodavo" Taisymo lange atidarius palyginimo lupą** – ties
  „Puslapio plotis" ir „Talpinti" mastelis priklauso nuo lango, o šis
  keičiasi su kiekviena atsirandančia ar dingstančia slinkties juosta;
  kiekvienas kitas veiksmas puslapį šiek tiek pastumdavo. Drobė dabar tai
  pati ištaiso, kol nusistovi. O mastelio mygtukai, slankikliai ir
  spartieji klavišai išlaiko vaizdo centrą net tada, kai priartinant
  atsiranda slinkties juosta.
- **Skersai išsaugoti skenai dabar skaitomi stačiai, o smulkus šriftas
  dideliuose skenuose nebedingsta.** 24 puslapių skenuotas pasiūlymas
  kiekvienoje poraštėje išlaikė šešias banko IBAN, įmonės registro numerį
  ir PVM numerį įskaitomus: skenas PDF faile buvo pasuktas 90°, o teksto
  atpažinimas priklausomai nuo paveikslėlio dydžio praleisdavo ištisas
  eilutes labai dideliuose paveikslėliuose. Dabar atsižvelgiama į matomą
  pasukimą, o dideli paveikslėliai skaitomi persidengiančiomis juostomis –
  poraštės juodos.
- **Gatvės pagal asmenis su brūkšneliu prieš pagrindinį žodį („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8", „Dr.-Karl-Renner-Straße 12")
  atpažįstamos kaip adresas.** Skenuoto pasiūlymo laiško antraštėje
  toks adresas liko įskaitomas, nes šablonas reikalavo tarpo prieš
  „Straße".
- **IBAN numeriai iš teksto atpažinimo su O vietoj 0 ar l vietoj 1 dabar
  atpažįstami.** Smulkiame skenuoto teksto šrifte teksto atpažinimas mielai
  perskaito skaitmenis kaip raides; numeris tada turėjo IBAN formą, bet
  kontrolinė suma nesutapo, ir jis likdavo. Dabar, jei kontrolinė suma
  nesutampa, bandoma skaitmenų versija – jei ji sutampa, tai yra IBAN.
  Neteisingi kontroliniai skaitmenys lieka neteisingi.
- **Sakinio dalys kaip „folgenden Codes auf der" buvo laikomos vietove.**
  Vardas ar vietovė, prasidedantys mažąja raide, tokiais nėra – išskyrus
  bajorystės daleles („van Gogh", „de Vries").
- **Redaktoriuje šalia švarinimo juostos likdavo paskutinė raidė**
  („…6", „…t", „…g"), o juosta turėjo nutraukto rėmelio, o ne eilutės
  aukštį. Priežastis: kai redaktorius negalėjo išmatuoti puslapio, jis
  kiekvieną rėmelį laikė „žodis nepataikytas" ir taikė jį tiksliai – be
  taisyklės, kad pusė žodžio niekada nelieka. Tas pats nutikdavo su
  pavieniais teksto komandomis, kurių redaktorius negalėjo lokalizuoti.
  Dabar šalia visada skaičiuojama žodžio dėžė: ką rėmelis iš esmės
  dengia, tas krenta visas.
- **Žodžio paskutinė raidė kyšodavo už švarinimo juostos.** Juosta buvo
  matuojama pagal poslinkio plotį iš šrifto metrikos; jei šriftas piešia
  platesnę glifą, jos likutis stovėdavo šalia juostos. Simbolio dėžė dabar
  apima ir nupieštą glifą.
- **Pranešimas apie puslapio pavertimą paveikslėliu žadėjo per daug.**
  „Vaizdas lieka toks pat" po rastravimo netiesa: šriftas ir grafika tada
  tampa pikseliais, failas padidėja. Pranešimas tai dabar sako – ir nurodo
  taip pat antrąją priežastį, dėl kurios rastruojama (perdarymas būtų
  pažeidęs puslapį).
- **Tekstas po pašalintos reikšmės pasislinkdavo iki vieno taško
  kairėn.** Eilutės perdarymo metu pradžia buvo matuojama pagal glifo
  kraštą, tęsinys – pagal plunksnos pradžios tašką – pirmosios raidės
  poslinkio plotis likdavo kaip klaida („C" 0,5 tšk., „I" 1,0 tšk.).
  Dabar perdarymas visur skaičiuoja nuo plunksnos pradžios taško;
  tolesnis tekstas stovi dešimtųjų taško tikslumu savo vietoje.
- **Austrijos PVM numeris su tarpais („ATU 187 35901") ir įmonės registro
  numeris be „FN" po jo užrašo („Firmenbuchnummer: 30799v") dabar
  atpažįstami.** Abu buvo įrašyti ranka skenuotoje konkurso formoje ir
  liko įskaitomi, nors teksto atpažinimas juos perskaitė teisingai.
- **Skersai gulinčius PDF puslapius po švarinimo be reikalo versdavo
  paveikslėliu.** Vientisumo patikra lygino originalą ir rezultatą
  pasuktame vaizde, bet savo švarinimo zonas skaičiavo nepasuktas – puslapyje
  su pasukimo žyma dėl to sava švara atsidurdavo šalia savo zonos ir buvo
  laikoma žala. Tokie puslapiai dabar išlaiko savo teksto sluoksnį ir
  vektorinę grafiką.
- **Taip pat tiesūs puslapiai kartais be reikalo versti paveikslėliu**,
  kai tekstas po pakaitalo pasislinkdavo per vieną tašką – leidžiama, bet
  paveikslėlių palyginimas buvo jautresnis nei jo paties tolerancija. Dabar
  jis lygina pusiau taškų tikslumu ir taip tiksliai pataiko į savo
  toleranciją: iki dviejų taškų poslinkio niekas nesuveikia, virš to –
  suveikia visada.
- **Duomenys įterptuose formos objektuose likdavo.** Kai kurios šablonų
  formos laiško antraštę ar pabaigą pateikia kaip atskirą formą, kurią
  puslapis tik įtraukia. Radinys joje buvo suplanuotas ir suskaičiuotas
  kaip pašalintas, bet niekada neįrašytas – tekstas liko stovėti, ir tai
  užfiksuodavo tik viso puslapio rastravimas. Dabar pati forma
  perrašoma; forma, esanti keliuose puslapiuose, perrašoma vieną kartą.
- **PDF puslapiai versti paveikslėliu, nors nieko įskaitomo nebuvo
  likę.** Septynių puslapių pasiūlymą tai ištiko šešiuose puslapiuose;
  jis išaugo nuo 73 kB iki 3,3 MB ir prarado savo šriftą, virsdamas
  atvaizdu. Priežastis – tarpai, kurie dokumente stovi keli iš eilės, o
  skaitytuvas juos pastebi tik vieną kartą: tekstas po pašalintos
  reikšmės pasislinkdavo jos pločiu į dešinę, patikra rasdavo kaimyninį
  žodį radinio stačiakampyje ir imdavosi rastravimo. Išsaugoti eilutės
  likučiai dabar vėl stovi tiksliai savo vietoje; tas pats pasiūlymas
  išvalomas be nė vieno rastruoto puslapio (76 kB).
- **Raktų vardai ir sąskaitų faktūrų antraštės buvo laikomi asmenimis.**
  Prieigos faile buvo pakeičiamas aplinkos kintamojo vardas
  („AWS_ACCESS_KEY_ID"), ne tik jo reikšmė; angliškoje sąskaitoje
  antraštė „Bill to" krito kaip vardas. Identifikatorius didžiosiomis
  raidėmis su pabraukimais niekada nėra vardas, o žodis eilutėje, kuri
  kaip visuma yra lauko užrašas, taip pat ne – po juo esantis gavėjas
  toliau randamas.
- **Paieška Taisymo lange stringa dideliuose PDF puslapiuose.** Kiekviena
  paieškos lauke įvesta raidė iš naujo rastruodavo puslapį, nors keitėsi
  tik paryškinimas. Atvaizduotas puslapio vaizdas dabar lieka nekintantis,
  kol puslapis, mastelis ir rodinys tie patys – taip pat originalas
  palyginimo lupoje; vartymas, mastelio keitimas ir naujas failo stovis
  toliau piešiami iš naujo.
- **Pozicijų numeriai pasiūlymuose buvo laikomi IP adresu ar telefono
  numeriu.** Prekės eilutė kaip „1.3.3.4 … 5-Port Gigabit Switch"
  vertė struktūros numerį tinklo adresu, nes „Port" buvo laikomas
  techniniu kontekstu – dabar jis skaičiuojamas tik kaip savarankiška
  reikšmė („Port 80"), ne kaip žodžio dalis. O „1.3.3.6 216879" (pozicijos
  ir prekės numeris) nebelaikomas telefono numeriu ir nešvarinamas. Tikri
  IP adresai ir telefono numeriai tokiuose sąrašuose lieka atpažįstami.
- **Prekių eilutės pasiūlymuose buvo laikomos pašto kodu su vietove.**
  „35252 DIETZEL SALR" (prekės numeris su gamintoju) ir „1000 AWG" (kiekis
  su laidininko skerspjūviu) sunumeruotose pozicijų eilutėse buvo
  sušvarinami kaip adresas, nes didžiosiomis raidėmis parašytas žodis po
  skaičiaus buvo laikomas vietovardžiu didžiosiomis raidėmis. Pozicijų
  sąrašuose tai nebegalioja; „1080 WIEN" adreso bloke ir mažosiomis
  raidėmis parašytos vietovės visur toliau atpažįstamos.
- **Papildomas vardų atpažinimas sušvarindavo pasiūlymuose vaidmenų
  eilutes ir stulpelių antraštes.** „Partiestundensatz Monteur +
  E-Helfer" 49 kartus buvo laikomas asmeniu, stulpelio antraštė „Pos.
  Bezeichnung Menge EH" 19 kartų – vietove; 19 puslapių užsakymas dėl to
  tapo neįskaitomas. Tokie radiniai pozicijų eilutėse dabar krenta, jei
  jie patys turi simbolių, kurių vardas neturi (pliusas, pasvirasis
  brūkšnys, skaitmuo, santrumpa) – net jei eilutė baigiasi suma
  („Alternativ Markt … - PV/LS AC-Versorgung 1 290,00"). Vardai
  sąrašuose ir katalogo lentelėse – kam ši pakopa ir skirta – lieka
  neliesti.
- **„Der Kunde" versdavo kiekvieną „Kunde" bendrose sutarties sąlygose
  vardu.** Kai papildomas vardų atpažinimas į radinį įtraukdavo
  artikelį, jis buvo laikomas dviejų dalių vardu ir apsaugodavo visas 35
  kitas to paties žodžio vietas. Dabar artikelis nuo jo atimamas, ir
  „der Kunde" krenta taip pat, kaip iki šiol jau krisdavo „des Kunden".
- **Užrašai buvo laikomi reikšme.** „E-Mail" septynis kartus buvo
  sušvarintas kaip el. pašto adresas, „Telefonnummer" ir „Faxnummer" – kaip
  telefono numeris. Adresas be @ ir telefono numeris be skaitmenų
  nebelaikomi tokiais.
- **Vienos raidės stulpelių santrumpos („L: 154,50", „S: 0,00") buvo
  laikomos vardu** – 25 kartus PV pasiūlyme. Pavienė raidė nėra nei vardas,
  nei vietovė.
- **PDF puslapiai buvo verčiami paveikslėliu daug per dažnai.** Dvi
  priežastys, abi rastos tikruose pasiūlymuose: jei PDF failas kiekvieną
  glifą pateikia kaip atskirą komandą ir po ja slypi tarpo glifa be teksto
  simbolio, priskyrimas nuo tos vietos pasislinkdavo per vienetą – nuo
  pašalintos reikšmės likdavo paskutinė raidė
  („ŠkodaTopCar**d**"), ir patikra teisingai rastruodavo puslapį. O žodis,
  perkeltas per eilutės pabaigą su brūkšneliu („Datenschutz-"), dėl
  skaitymo bibliotekos perkėlimo žymos buvo laikomas pasislinkusiu. Abu
  atvejai ištaisyti: automobilio pasiūlymas nuo 4 rastruotų puslapių
  perėjo prie 0, 19 puslapių užsakymas – nuo 7 prie 0 – šriftas lieka
  šriftu, failas lieka mažas.
- **Ištaisytos dar dvi rastravimo priežastys:** jei dokumentas pats atsineša
  šriftą pavadinimu „F1", pakaitalai virš paveikslėlių buvo nustatomi šiuo
  šriftu ir buvo neįskaitomi – dabar sava užrašų šriftas gauna laisvą
  pavadinimą. O jei skaitymo bibliotekai ilgoje teksto komandoje trūksta
  tarpo, vieta dabar įrodoma taip pat daugiabaitiams šriftams (tas pats
  kodas, tas pats simbolis), o ne spėjama pabaigoje – anksčiau tai
  palikdavo vieną pašalintos reikšmės raidę stovinčią, o likęs tekstas
  matomai pasislinkdavo į šoną. Dar du paskutiniai atvejai: komanda iš
  keliolikos tarpo glifų priskyrimą leisdavo nuklysti (po jos likdavo
  vardas), o didelė antraštė su poslinkio pločiu neranda savo pirmo
  simbolio (likdavo įmonės pavadinimas). **Iš devynių tikrų pasiūlymų
  dabar nerastruojamas nė vienas puslapis** – anksčiau būdavo 30 iš 90.
- **Rastruojant paveikslėliai dingdavo po juodu bloku.** Kai puslapį reikia
  paversti paveikslėliu, jis atvaizduojamas iš originalo – o tai nežino
  jokio paveikslėlių valymo. Iki šiol dėl to *kiekviena* puslapio
  paveikslėlio sritis atsidurdavo po juosta, net nepaliesta. Viename
  pasiūlyme adresas ir du sertifikatų logotipai buvo tame pačiame laiško
  antraštės paveikslėlyje; juosta pasiimdavo ir logotipus. Dabar
  įterpiamas jau išvalytas paveikslėlis: adresas jame sušvarintas, visa
  kita lieka matoma. Pašalintas paveikslėlis palieka baltą popierių, o ne
  juodą dėžę.

- **Išvalyti skenai tapdavo kelis kartus didesni už originalą.** Kiekvienas
  paveikslėlis, kuriame kas nors buvo sušvarinta, grįždavo į failą kaip
  nesuspaustas žalias vaizdas – 24 puslapių skeną tai išpūsdavo nuo 11,8
  iki 52,9 MB. Paveikslėliai dabar išlaiko tokią formą, kokia buvo pateikti:
  nuotrauka lieka nuotrauka, fakso skenas lieka juodas-baltas, spalvos
  neturintis paveikslėlis nesaugomas kaip spalvotas. Tas pats failas dabar
  yra 15,6 MB, be matomo skirtumo.

- **Skenuoti PDF failai iš biuro įrenginių grįždavo kaip juostuotas
  raštas.** Tokie skenai deda tekstą kaip aiškų juodai baltą sluoksnį virš
  stambaus spalvoto paveikslėlio – taip savo failus kuria Canon, Xerox ir
  Kofax. Švarinant paveikslėlyje šis sluoksnis buvo neteisingai
  parašomas atgal; rezultatas būdavo neįskaitomas. Šešių puslapių
  pasiūlyme tai ištiko devynis iš šešiolikos paveikslėlių. Dabar jis
  tvarkomas teisingai, savo spalvomis, o sušvarintos vietos jame iš tikrųjų
  dingsta.

- **„Pašalinti visus paveikslėlius" atimdavo iš skenuoto puslapio jo
  tekstą.** Tokio skeno teksto sluoksnis techniškai yra paveikslėlis – jis
  buvo pašalinamas ar suliejamas kartu, o liko tuščias lapas. Dabar jis
  lieka; logotipai, antspaudai ir parašai toliau šalinami.

- **Patikra dėl pažeistų PDF puslapių dėl smulkaus poslinkio nebe
  rastruoja.** Valant iš naujo pritvirtintas teksto gabalas gali
  pasislinkti iki dviejų taškų; paveikslėlių palyginimas tai vis tiek
  laikydavo žala ir puslapį perkurdavo kaip atvaizdą – tuo metu prarasdavo
  vektorinę grafiką, pavyzdžiui, lentelių linijas, o virš radinių gulėdavo
  juosta vietoj pakaitalo. Dabar palyginimas leidžia tą patį nedidelį
  poslinkį kaip žodžių patikra; tikra žala toliau pastebima.

- **Daugelio reikšmių atkūrimas vienas po kito Windows sistemoje daugiau
  nebežlugdavo dėl „Prieiga uždrausta".** Kas Office faile greitai vieną
  po kito atšaukdavo daug skydelio eilučių, galėjo susidurti su trumpalaikiu
  antivirusinės programos failo užraktu; keitimas dabar tokių užraktų
  trumpai palaukia.

- **Windows komandų perdavimo kelias baigdavo tikrintuvo darbą, vietoj
  jį patikrinti.** Klausančio egzemplioriaus gyvumo patikra Windows
  sistemoje netyčia siųsdavo tikrą Vald+C savo pačios konsolės grupei;
  dabar ji klausia sistemos be signalo.

- **Daugiažodžiai lauko užrašai neveikdavo, bet veikdavo jų
  fragmentai.** „Date of birth", „Bank account", „Cuenta bancaria" ir
  „Numero de cliente" buvo užrašų sąraše, tačiau ten buvo suskaidyti į
  pavienius žodžius ir todėl niekada nesuveikdavo; likdavo tokie
  fragmentai kaip „de" ir „of", kurie nuo tada buvo laikomi užrašu – o
  „de" juk yra vardo dalis („Anna de Vries"). Abu dalykai ištaisyti: šios
  frazės dabar veikia kaip visuma, fragmentų nebeliko.

- **Vokiškos pasisveikinimo formulės su „ß" nepaisant įrašo buvo
  traktuojamos kaip asmenvardis.** Po „Herzliche Grüße" ar „Mit
  freundlichen Grüßen" rezultate stovėjo pakaitalas, nors abi frazės nuo
  seno yra išimčių sąraše. Priežastis buvo rašyba, kuri lyginant niekada
  nesutapdavo; paveikta buvo aštuoni įrašai penkiuose sąrašuose. Dabar jie
  visi veikia.

- **„John Staff" likdavo nepakeistas.** Pavardė, kuri kartu yra angliška
  stulpelio antraštė, buvo pašalinta kartu su užrašo filtru. Antraštė
  toliau lieka nepaliesta, o po ja esantis vardas vėl pakeičiamas.

- **Reikšmės iš su užrašais pažymėtų formos laukų lieka apsaugotos KI
  pakopoje.** KI pakopos vietinis arbitras iki šiol gaudavo vertinti taip
  pat radinius, kurių reikšmę jau įrodo lauko užrašas (virš reikšmės –
  „Geburtsdatum:") – ir galėjo juos atmesti. Tokios struktūriškai įrodytos
  reikšmės jam daugiau nepateikiamos. Priskyrimo failas dabar prie
  kiekvieno pakeitimo papildomai nurodo atpažinimo kelią („beleg").

- **PDF puslapis, kurio išsaugotas tekstas valant nukentėjo, dabar
  atpažįstamas ir iš naujo sukuriamas kaip originalo atvaizdas.** Kai
  kuriuose kūrėjo šriftuose išsaugotos teksto vietos po valymo galėjo
  atrodyti kaip juodi blokai arba žodžiai susilieti, nors visos šalintinos
  reikšmės buvo teisingai pašalintos. Maskuro dabar lygina rezultatą su
  originalu žodis po žodžio ir pikselis po pikselio; pažeistas puslapis
  pakeičiamas švariu jo atvaizdu – su švarinimo juostomis virš radinių,
  sušvarintomis paveikslėlių sritimis ir ieškomu tekstu. Puslapis lieka
  įskaitomas, pašalinimas – patikimas.

### Pakeista

- **Verstose sąsajose kiekvienas terminas dabar vadinamas vienodai
  visur.** Tam pačiam vokiškam žodžiui priklausomai nuo lango stovėjo du
  ar trys skirtingi vertimai vienas šalia kito: patikros protokolas
  norvegiškai vadinosi tai „Revisjonslogg", tai „Kontrollogg", nemokama
  pakopa – tai „Gratisnivå", tai „Gratisversjon" – ir panašiai daugiau nei
  keliolikoje kitų kalbų. Kas ieškojo nustatymo, rasdavo jį kitame lange
  kitu vardu. Suvienodinta pagal žodį, kurį sąsaja ir taip vartoja
  dažniausiai.

  Tuo pačiu paaiškėjo vietų, kur vienas žodis reiškė du **skirtingus**
  dalykus: prancūzų, graikų ir korėjiečių kalbose „schwärzen" (švarinti) ir
  „maskieren" (maskuoti) žymėti tas pats žodis – būtent ten, kur programa
  paaiškina skirtumą („Švarinimas pašalina be pakaitalo, maskavimas
  išlaiko formą"). Dabar abu atskirti. Švedų kalbai šis sprendimas dar
  laukia: ten švarinimas vadinasi „maskera" – tas pats žodis kaip
  maskavimas.

- **Klausimas apie naudojimo pobūdį pirmo paleidimo metu panaikintas.**
  Netrukus po paleidimo pasirodydavo langas („Asmeniniam naudojimui ar
  įmonėje?"), o nustatymuose dėl to buvo eilutė. Abiejų nebeliko –
  visiškai. Nuoroda, prie kurios nieko nepririšta, klaidingai nurodo, kam
  reikia neteisingos licencijos rūšies, o kas sąžiningas, tam jos nereikia;
  tai kainavo kiekvienam po paspaudimą tuo metu, kai apie licencijų rūšis
  niekas negalvoja. Kuri licencija teisinga, nurodyta ten, kur tai
  sprendžiama: kainų puslapyje, kasoje ir pagalboje. Įmonės, kurios
  Maskuro diegia centralizuotai, naudojimo pobūdį toliau nurodo per
  numatytųjų nustatymų failą.

- **Licencijos rūšies nuorodose įvardijamas atvejis, apie kurį kalbama.**
  Asmeninė licencija galioja išskirtinai asmeniniam naudojimui; bet koks
  profesinis ar komercinis darbas reikalauja įmonės licencijos – taip pat
  savarankiškai dirbančiam be darbuotojų. Tai buvo įrašyta licencijos
  sąlygose, bet nei programoje, nei pagalboje: ten buvo minima tik įmonės
  domenas, o jis būtent šio atvejo neapima: savarankiškai dirbančio
  kompiuteris nepriklauso jokiam domenui. Nuoroda įkeliant asmeninę
  licenciją dabar tai sako, taip pat licencijos skyrius instrukcijoje ir
  dažni klausimai, kuriems dėl to sukurtas atskiras įrašas. Toliau
  neblokuojama nieko.

- **Dar nepristatyti keliai dabar sugrupuoti kartu.** Nustatymuose atsirado
  puslapis „Kūrėjams"; ten yra maksimalus atpažinimas (KI) kartu su savo
  patikros procedūra, žodžių sąrašų katalogas ir aplanko stebėjimas. Visi
  trys sukurti, bet dar neišbandyti realioje aplinkoje – todėl matomi tik
  su kūrėjo licencija, ir tai visur vienu metu: puslapis, meniu punktai ir
  veikimas eigoje priklauso nuo to paties sprendimo. Be šios licencijos
  anksčiau įjungta KI pakopa lieka be poveikio; jos nustatymas neištrinamas
  ir vėl galioja, kai tik kelias bus pristatytas.

### Patobulinta

- **„Kas ieškoma" rodo dar tris sąrašus iš vardų atpažinimo.** Kreipiniai,
  po kurių sekantis žodis skaitomas kaip vardas; titulai ir pareigos,
  po kurių sekantis žodis dar **nėra** vardas („Herr Bürgermeister
  Huber"); ir aštuoniasdešimt daugiakalbių užrašų, pagal kuriuos
  atpažįstami bylos, proceso ir atvejo numeriai. Visi trys veikė nuo pat
  pradžių, tačiau apžvalgoje nebuvo matomi.

- **„Kas ieškoma" rodo du iki šiol trūkusius žodžių sąrašus.** Kreipiniai
  ir titulai, kurie prieš tai einantį žodį paverčia vardu („Herr", „Frau",
  „Dr."), ir standartizacijos organizacijų santrumpos, pagal kurias
  Maskuro atskiria standarto nuorodą, tokią kaip „ÖNORM B 2110", nuo
  asmens. Abu daro poveikį nuo seno, tačiau apžvalgoje jų nebuvo.

- **Pozicijų sąrašai, turinio rodyklės, įrangos sąrašai ir standartų
  nuorodos lieka įskaitomi.** Atpažinimas dabar mato eilutės formą:
  spėjamas vardas struktūros eilutėje („1.3.1 Energieerdkabel 1kV"),
  turinio rodyklės eilutėje su vedimo taškais, sąraše
  („- kabelloses Laden mit Magnetring"), virš kiekio/kainos eilutės,
  stulpelio antraštėje ar po „mittels" yra dalykinis terminas ir
  nebekeičiamas. Tikri vardai lieka apsaugoti – per kreipinį, lauko
  užrašą ir įrodymą kitoje dokumento vietoje; matavimo korpuse jokia
  reikšmė neprarado savo apsaugos. Verslo korpuse klaidingų signalų
  sumažėjo nuo 25 iki 6.

- **Antraštės, formos užrašai ir pasisveikinimo formulės rečiau laikomos
  vardais – vokiškai ir angliškai.** Žodžių sąrašai, kuriais Maskuro
  atskiria dalykinius žodžius nuo asmenvardžių, gerokai išaugo: sąskaitų,
  formų ir valdiškos korespondencijos užrašai („Aktenzeichen",
  „Verwendungszweck", „Kostenstelle", „Sort code", „Subtotal"), CV ir
  ataskaitų skyrių antraštės („WERDEGANG", „QUALIFIKATIONEN", „SUMMARY",
  „REFERENCES"), vokiškos ir angliškos dokumentų rūšys
  („Auftragsbestätigung", „Niederschrift", „Timesheet", „Agreement"), taip
  pat instrukcijų liepiamosios formos („Sende…", „Select…"). Angliška
  pusė iki šiol buvo pastebimai skurdi.

- **Su užrašais pažymėti laukai dabar išduoda, kas juose parašyta, ir
  tada, kai užrašas yra sudėtinis.** „Lieferanschrift", „Rechnungsadresse",
  „Sachbearbeiterin", „Kontoinhaber", „Contact person" ir „Billing address"
  dabar reikšmę šalia ar po jais priskiria tai pačiai rūšiai kaip paprastą
  „Anschrift" ar „Name" – užpildytoje formoje su langeliais tai skirtumas
  tarp rasta ir praleista.

- **Taisymo lange pelės ratukas veda toliau prie puslapio krašto.** Kas
  puslapio pabaigoje sukasi toliau, atsiduria kito puslapio viršuje; kas
  sukasi atgal pradžioje, – ankstesnio puslapio apačioje – dokumentą
  galima taip perbėgti nuo pradžios iki galo, nepaliečiant puslapio
  mygtukų. Klaviatūra (Puslapis↑/Puslapis↓) tai jau galėjo; trumpa
  pauzė tarp dviejų puslapio pakeitimų neleidžia jutiklinio kilimėlio
  inercijai pernešti per pusę dokumento.

- **Puslapio miniatiūros Taisymo lange stovi centre skydelyje.** Iki šiol
  jos limpėjo prie kairiojo krašto, o plečiant plotį augdavo tik tuščias
  dešinysis kraštas.

- **Taisymo lango įrankių juosta rodo savo grupes.** Skiriamosios linijos
  dabar turi erdvės ir spalvos, „Ieškoti" ir „Perkelti į visus puslapius"
  stovi kaip atskiros grupės šalia įrankių, o „Perkelti" rodomas tik tose
  dokumentų rūšyse, kuriose jis gali kažką pakeisti. Kiekvienas juostos ir
  meniu punktas dabar turi paveikslėlį: „Teksto eilutės" ir palyginimo lupa
  gavo savo ženkliukus (lupa iki šiol dalijosi savuoju su „Prieš/Po"), taip
  pat mastelis, Visas puslapis, Puslapio plotis, Sukti, Vartymas ir
  spartieji klavišai. „Atverti su sistemos programa" dabar taip pat yra
  juostoje šalia Spausdinimo – kelias nuo baigto rezultato iki įprastos
  programos yra vienas paspaudimas, ne meniu ėjimas.

- **Iškarpinės valymo srityje vėl rašoma, kad reikia patikrinti.**
  Nustatymuose šalia jungiklio nuolat stovi nuoroda: Maskuro gali
  nepastebėti asmens duomenų arba klaidingai apdoroti duomenis, prieš
  perduodant įklijuotą tekstą reikia peržiūrėti. Įjungiant tai papildomai
  praneša pranešimas, ir tai pažymima išvesties srityje – net ir tada,
  kai jokia piktograma pranešimų srityje neveikia. Prie kiekvieno atskiro
  kopijavimo veiksmo nuoroda sąmoningai nerodoma: nuoroda, kuri pasirodytų
  penkiasdešimt kartų per dieną, po trečio karto nebebūtų skaitoma.

## 0.10.36-beta.1 – 2026 m. rugpjūčio 20 d.

### Patobulinta

- **Techniniai verslo dokumentai nebesutamsinami per daug.** Keturi
  atpažinimo stabdžiai, gauti iš vienuolikos realių pasiūlymų ir užsakymų:
  struktūros numeriai („1.3.1.1") nebelaikomi IP adresais, normų nuorodos
  („ÖNORM EN 62446") ir kodai nebelaikomi pašto kodu ar telefono numeriu,
  o vaidmenų žodžiai po artikelių („der Kunde", „des Auftraggebers")
  nebelaikomi vardais – realaus pasiūlymo bendrosiose sąlygose visi 46
  vaidmenų žodžiai vėl skaitomi, o ne užtamsinti. Adresai su šalies kodu
  („A 3390 Melk", „D-94032 Passau") dabar visiškai pašalinami, vietoj to,
  kad pašto kodas liktų kaip našlaitis.

- **Žodžių sąrašai dabar visiškai peržiūrimi.** Meniu „Pagalba → Žodžių
  sąrašai …" galima naršyti vietoje naudojamus atpažinimo ir kryžminio
  tikrinimo sąrašus kartu su kalba, paskirtimi, šaltiniu ir turiniu. Prie
  jų priklauso ir wordfreq, medicinos, asmeniniai bei centralizuotai
  valdomi sąrašai, taip pat sugalvotų pakaitalų atsargos. Vadove katalogas
  aprašytas atskirame skyriuje.

- **Baigtos failų eilutės rodo naudotą atpažinimo kalbą.** Už žodžio
  „baigta" dabar rodoma, pvz., „vokiečių" arba „anglų", kad netinkamas
  automatinis kalbos pasirinkimas iš karto kristų į akis. Jei teko
  įsikišti kitai įdiegtai kalbai, rodyklė rodo abi kalbas.

- **Naujas palyginimo didinamasis stiklas skaitant iš karto rodo tinkamą
  vietą originale.** Jo padidinta originalo ištrauka seka pelės žymeklį
  virš toliau redaguojamo rezultato; teksto atveju ji seka pastraipą.
  Didinamąjį stiklą galima naudoti lango krašte arba ištraukti kaip
  atskirą, išdidinamą langą. Jo mastelis tiesiogiai nustatomas nuo 50 iki
  300 procentų ir įsimenamas taip pat, kaip ir įjungimas. „Atstatyti"
  padidintą ar nepatogiai prišvartuotą didinamąjį stiklą taip pat grąžina
  atgal kairėn į valdomą dydį. Pakeistos originalo reikšmės didinamajame
  stikle paryškintos geltonai, kad paveikti žodžiai skaitant iš karto
  kristų į akis. Vieną kartą įjungtas, jis vėl atsiveria tinkamuose
  tolesniuose dokumentuose – net ir po programos paleidimo iš naujo.
  Ankstesnis prieš/po perjungiklis lieka meniu „Rodinys". Vadove jis
  aprašytas atskirame skyriuje.

- **Atviro kodo ir modelių įrodymai dabar atitinka tikslią laidą.**
  Paketo kūrimas sukuria mašininiu būdu nuskaitomą komponentų sąrašą
  kartu su pridėtų licencijos tekstų maišomis. MPL šaltiniai, modelio
  kilmė, fiksuotos redakcijos, pakeitimai ir SHA-256 įrodomi atskirai;
  atsisiunčiami modeliai gauna savo kilmės įrodymą tiesiai modelio
  aplanke. Kintantys Tesseract ir spaCy šaltinių sąrašai buvo fiksuotai
  prisegti. Pardavimo artefaktai lieka užrakinti, kol visi šaltiniai ir
  modelių priedai nepaskelbti ir nepatikrinti.

- **Vietinis wordfreq duomenų rinkinys visiškai pagrįstas licencijomis.**
  Paketo kūrimas patikrina versiją 3.1.1, 39 nepakeistus mažus sąrašus,
  įskaitant CJK ir kinų rašmenų lentelę, pagal kiekį, dydį ir
  manifesto kontrolinę sumą. Apache-2.0 kodo nuoroda, visas CC-BY-SA-4.0
  licencijos tekstas, atributavimas, duomenų šaltiniai ir praleisti
  dideli, Jieba bei nepalaikomi sąrašai dokumentuoti pakete.

- **Dažni sakinio žodžiai rečiau klaidingai užtamsinami.** Vietinis
  dažnumo žodynas tarnauja kaip papildoma kryžminė patikra, kai vardų
  atpažinimas veiksmažodį, įvardį, artikelį ar prielinksnį laiko asmeniu.
  Žodynas niekada nesprendžia vienas: daiktavardžiai, kelių dalių vardai
  bei vardai laukuose, sąrašuose ir po kreipinių lieka apsaugoti. Kinų,
  japonų ir korėjiečių kalbos naudoja tik tikslias jau turimų kalbos
  modelių ženklų ribas; neturimoms kalboms tariamai panaši žodyno kalba
  nenaudojama. Tam jokio dokumento teksto į internetą neperduodama.

- **Techniniai gaminio ir įrangos terminai rečiau laikomi vardais ar
  vietovardžiais.** Vietinė kryžminė patikra dabar sujungia dažnumą,
  kalbos dalį, techninę žodžių darybą ir dalykines sritis. Todėl,
  pavyzdžiui, „Travel-Assistent", „Family-Bonus", „WLTP-Wert",
  „Easy-Start" ir sudėtiniai numerių, laikiklių ar stabdžių terminai
  lieka dokumente. Angliški komponentai ieškomi vietoje ir vokiškame
  dalykiniame tekste; tikri tikriniai vardai, kreipiniai bei asmenų ir
  vietovių laukai išlaiko pirmenybę. Be to, „2 metų gamintojo garantija"
  nebelaikoma amžiumi.

- **Qt/PySide licencijų teisės dabar visiškai atsekamos.** Programos
  paketas papildomai turi visą GPL-3.0 tekstą, tikslias Qt versijas,
  pasiūlymą gauti šaltinio kodą ir vokišką/anglišką instrukciją, kaip
  pakeisti dinamines bibliotekas, įskaitant vietinį macOS pakartotinį
  pasirašymą. Pardavimo statyba blokuojama, kol tikslūs pristatytos
  versijos šaltinio archyvai nepasiekiami savo šaltinio kodo puslapyje.

- **Licencija ir atnaujinimo būsena dabar kiekvienai pakopai vienareikšmiai
  sako, kas galioja.** Licencijos lange ir atnaujinimo nustatymuose
  nurodoma, ar atnaujinimai įtraukti, iki kokios dienos jie galioja ir ar
  veikianti versija lieka nuolat naudojama. Privačios licencijos po
  nurodytos dienos nebeįdiegia vėliau išleistos versijos; net naujai
  atsisiųstas diegimo failas pagal savo fiksuotą išleidimo datą atpažįsta,
  ar įvestas raktas jį apima. Paskutinė padengta privati versija lieka
  nuolat naudojama. Jei tačiau baigiasi įmonės prenumerata, baigiasi
  naudojimas ir atnaujinimai; bandomasis laikotarpis ir nemokama pakopa
  aplinkkeliu neatsidaro.

- **Privačios nuolatinės licencijos dabar suranda tinkamą programos
  būseną ir po pakartotinio diegimo.** Pasirašytas versijų katalogas
  registruoja visas stabilias versijas ir jų paketus. Jei paskutinis
  pirkimo apimamas diegimo failas nebepasiekiamas, vietoj jo automatiškai
  gali būti naudojama tiksliai kita, aukštesnė turima stabili versija –
  niekada beta ar nightly. Esant per naujam diegimui, klientas gali
  įdiegti leistiną versiją arba pereiti į pirkimo puslapį naujam
  atnaujinimo laikotarpiui; žingsnis atgal neįvyksta tyliai. Tai galioja
  ir valdomiems MSI diegimams.

- **Automatinis veidų užtamsinimas dabar vienareikšmiai aprašytas.**
  Programos pagalba ir privatumo tekstas šią funkciją vadina „Veido
  sričių atpažinimas ir padarymas neatpažįstamu" ir atriboja ją nuo
  identifikavimo, pakartotinio atpažinimo, veidų palyginimo, biometrinių
  šablonų bei asmenų ar veidų duomenų bazių. Jie taip pat aiškiai nurodo,
  kad visiškai vietinis atpažinimas gali sritis praleisti ar klaidingai
  pažymėti, todėl rezultatas turi būti vizualiai patikrintas. Ir pavieniui
  išvalyto vaizdo failo rezultatų ataskaitoje dabar nurodomos atpažintos ir
  pikselizuotos veido sritys; trūkstamas teksto atpažinimas dėl to
  nebeaprašomas klaidingai kaip visiškai nepakeistas failas.

## 0.10.36-alpha.20260820 – 2026 m. rugpjūčio 20 d.

### Ištaisyta

- **Anoniminti duomenys dabar visiškai grąžinami nepriklausomai nuo eiliškumo.**
  Ankstesnis grąžinimas ieškojo reikšmės pagal matomus teksto inkarus.
  Tankiose lentelėse, tiesiogiai gretimuose žymikliuose ir nematomose
  „Office"/pašto vietose šių inkarų trūko; kartais terminas tapdavo
  grąžinamas tik po to, kai kitas atviras tekstas atsitiktinai sukurdavo
  naują inkarą. Dabar rezultatas ir originalas lyginami pagal kiekvieną
  tikrą formato laikiklį su visu priskyrimu, ir įrašomos tik pasirinktos
  reikšmės užimtos vietos.

- **Vardai, pašto adresai, numeriai ir savi tikrinimo terminai išlieka
  vienareikšmiškai valdomi net esant persidengiančiam atpažinimui.** Jei
  tam pačiam atviram tekstui priskirtos dvi rūšys, sprendžia radimo vietoje
  iš tikrųjų esantis žymiklis kartu su pažymėta šoninės juostos eilute.
  Neužimta reikšmės ir žymiklio pora ir toliau lieka saugiai užrakinta.

- **Pašto ypatingi atvejai daugiau nebepalieka paslėptų žymiklių.** Tai
  galioja MIME koduotoms temoms, teksto priedams ir per HTML žymėjimą
  atskirtiems vardams EML ir MSG failuose. UTF-8 HTML be savo koduotės
  nurodymo „Outlook" failuose taip pat nebekoduojamas į „mojibake" po
  kiekvieno redagavimo veiksmo; ankstesni, jau taip užrašyti rezultatai
  išlieka grąžinami.

### Patobulinta

- **Nauja išleidimo matrica atskirai ir tyčia atgaline tvarka tikrina
  kiekvieną anoniminę šoninės juostos eilutę.** Ji patikrina visus 14
  teksto, „Office", žiniatinklio ir pašto formatų bei PDF, po to dar
  formules, atributus, ryšius, komentarus, pašto antraštes, priedus ir
  vidines pagalbines saugyklas. Pilnas macOS paleidimas dabar apima
  149/149 žalius patikros scenarijus.

## 0.10.35-alpha.20260820 – 2026 m. rugpjūčio 20 d.

### Patobulinta

- **Kalbų matavimai dabar tikrai lygina panašų su panašiu.** Reguliariame
  matavimo korpuse yra tie patys 14 dokumentų atvejų su tomis pačiomis
  septyniomis teksto ir keturiomis vaizdo užduotimis vokiečių ir anglų
  kalbomis. Pilnas paleidimas tiksliai pakartoja šią matricą visoms
  dvylikai turimų korpuso kalbų. Formos, lentelės, pokalbiai ir kiti dar
  ne iki galo išversti struktūros pavyzdžiai išlieka, tačiau nurodomi
  atskirai ir nebemaišomi su kalbų kvotomis.

- **Pilnas paleidimas kiekvienai kalbai parašo atskirą matavimo ataskaitą.**
  Be kalbos jungiklio sąmoningai tikrinamos vokiečių ir anglų kalbos;
  `--alle-sprachen` reikalauja pilno dvylikos kalbų korpuso ir nutraukiamas
  prieš pirmąjį dokumentą, jei trūksta kalbos ar atvejo. Vienodo pavadinimo
  rezultatai yra atskiruose kalbų aplankuose. Bendroje ataskaitoje šalia
  svertinio radimo rodiklio nurodomas ir nesvertinis kalbų rodiklių
  vidurkis.

- **Atviras kalbų palyginimas dabar rodo ir savo tikrąją ribą.** Reguliariame
  paleidime su teksto atpažinimu vokiečių ir anglų kalbos pašalina 218/218
  žinomų duomenų be klaidingo pavojaus. Pilnas testas su teksto atpažinimu
  ir aukšta pakopa pašalina 1 255/1 308 duomenų su 17 klaidingų pavojų;
  vienuolika kalbų pasiekia 100 procentų, hindi – 51 procentą. Ankstesni
  pilni rodikliai buvo pagrįsti nevienodais dokumentų ir siektinų reikšmių
  kiekiais ir su naująja matrica nepalyginami.

## 0.10.34-alpha.20260819 – 2026 m. rugpjūčio 19 d.

### Ištaisyta

- **Kelis kartus pasikartojantys vardai po vieno pavienio grąžinimo
  išlieka pasiekiami šoninėje juostoje.** Anksčiau visa vardo eilutė
  dingdavo jau po pirmos grąžintos `[VARDAS]` vietos. Kitos to paties
  vardo vietos dėl to likdavo kaip žymikliai ir kartais net būdavo
  užblokuojamos, kol būdavo grąžinti kiti vardai. Dabar eilutė dingsta
  tik po paskutinės vietos; jau grąžintas atviras tekstas vis tiek
  automatiškai pakartotinai neanonimintas. Tai galioja taip pat
  dalinai pavykusiam masiniam grąžinimui ir rėmelio įrankiui PDF
  failuose.

- **„Atšaukti pakeitimą" veikia ir iš „Office" puslapio peržiūros.**
  Matomas puslapis ten yra tik trumpalaikė PDF peržiūra; dabar teisingai
  keičiamas po ja esantis „Word", lentelės ar pristatymo dokumentas, o
  peržiūra po to atnaujinama.

- **Grąžinimas dabar visiškai atgauna ir paslėptus reikšmės atitikmenis.**
  „Word", „OpenDocument", „Excel" ir „PowerPoint" failuose tos pačios
  reikšmės gali papildomai būti formulėse, komentaruose, diagramose,
  laukų reikšmėse, alternatyviuose tekstuose ir nuorodų tiksluose; HTML,
  EML ir MSG jas papildomai laiko atributuose, JSON, žinučių antraštėse
  ir prieduose. Anksčiau, priklausomai nuo formato, dalis ten likdavo kaip
  žymiklis. Dabar kiekviena radimo srityje siūloma reikšmė gali būti
  grąžinta nepriklausomai ir bet kokia tvarka. Sąmoningai pašalinti
  metaduomenys, pakeitimų istorija ir perdavimo antraštės saugumo
  sumetimais lieka pašalinti.

- **Grąžinant iš paveikslėlių daugiau nebelieka juodos krašto linijos.**
  Rėmelio dešinysis ir apatinis kraštas kopijuojant iš originalo buvo
  apskaičiuojami vienu tašku per siaurai. Koordinatės dabar sutampa su
  užtamsinimu.

### Patobulinta

- **Išleidimo patikra dabar per pilną ratą praleidžia kiekvieną iš 22
  palaikomų failo plėtinių.** Turiniu turtingi failai išvalomi, visos
  siūlomos reikšmės atkuriamos ir po to giliai patikrinamos. Prie to
  prisideda tikras šoninės juostos valdymas, pikselio tikslumo vaizdų
  palyginimai ir matomas „LibreOffice" atvaizdavimas visiems septyniems
  raštinės formatams. Maži regresijos testai lieka ten, kur jie apima
  atskirą klaidos ar saugumo atvejį; įrodytai dubliuotas HTML patikrinimas
  ir pašalintos nespalvotos veiksenos testas panaikinti.

- **Šios versijos pilnas matavimo korpusas paruoštas pakartotiniam
  matavimui.** Paketą sudaro 294 sintetiniai dokumentai dvylikoje formatų
  ir dvylikoje kalbų, 2 564 žinomi duomenys, keturi mašininiu būdu
  nuskaitomi siektinų reikšmių sąrašai ir instrukcija. Kokybės puslapio
  atsisiuntimas naudoja nuo turinio priklausantį failo pavadinimą, kad
  naršyklės netyčia iš podėlio nepateiktų senesnės versijos.

## 0.10.33-alpha.20260819 – 2026 m. rugpjūčio 19 d.

### Nauja

- **Ir vaizdo failuose atskiras vietas dabar galima grąžinti iš originalo.**
  Rėmelio įrankis „Grąžinti originalą" nukopijuoja tuos pačius pikselius
  toje pačioje vietoje atgal iš nepaliesto originalaus failo. Kelias lieka
  užrakintas, jei originalo trūksta arba jis turi kitokius vaizdo matmenis;
  taip neįmanoma įterpti turinio iš pastumtos vietos.

### Patobulinta

- **Rankiniai užtamsinimo juostos pagal numatytuosius nustatymus prisitraukia
  prie teksto eilučių.** Traukimas per kelias eilutes sukuria vienodo aukščio
  juostą kiekvienai eilutei ir tarp jų palieka laisvą tarpą. Parašams,
  grafikai ir kitiems ypatingiems atvejams „Laisvas rėmelis" grąžina prie
  paties pasirinkto aukščio.

- **Redaktorius kitą veiksmą paaiškina tiesiai virš dokumento.** Nuoroda
  keičiasi priklausomai nuo dokumento tipo ir įrankio ir sako, ar laukiama
  spustelėjimo ant žodžio, teksto pažymėjimo ar rėmelio. Papildomai įrankis,
  žymeklis ir gyva peržiūra jau prieš atleidžiant rodo, kas įvyks.

### Pašalinta

- **Klaidoms linkusi nespalvota išvestis pašalinta.** Kai kuriuose PDF
  failuose nematomi teksto laukai likdavo pasislinkę nuo raste rodomo
  puslapio; tariamas failo dydžio sumažėjimas nebuvo vertas šios saugumo
  ir vaizdavimo rizikos. Įprastas PDF valymas ir tikslinis probleminių
  puslapių rastravimas išlieka.

## 0.10.32-alpha.20260819 – 2026 m. rugpjūčio 19 d.

### Nauja

- **Aplankų stebėjimas dabar tikrai veikia fone.** Gaunami, siunčiami
  failai ir taisyklės yra atskirame puslapyje po „Nustatymai". Pradedama
  ir sustabdoma per „Maskuro" piktogramą užduočių arba meniu juostoje;
  įrašas pasirodo tik su tam skirta atrakinta licencija. Nustatymų langą
  po to galima uždaryti, o pagrindinį langą sumažinti į piktogramą, ir
  stebėjimas nesustos.

- **Taisymo redaktorius dabar turi nuolatinį mokymosi veiksenos
  jungiklį.** Jis yra radimo srityje ir meniu „Įrankiai". Kai jis
  išjungtas, nei grąžinant, nei po rankinių taisymų neberodomi klausimai
  apie savų taisyklių kūrimą. Maskuro pasirinkimą įsimena visiems
  būsimai atveriamiems dokumentams; pats grąžinimas veikia nepakitęs.

### Ištaisyta

- **Didysis papildomas modelis vėl įsikelia.** Vieša saugykla su 403
  atmesdavo bendrą standartinę Python žymę. Modelio atsisiuntimai dabar
  naudoja tą patį nurodytą Maskuro tinklo kelią kaip ir kitos savos
  paslaugos; beveik 596 MB dydžio failas ir jo kontrolinė suma lieka
  nepakitę.

- **Padidintas palyginimo didinamasis stiklas prišvartavus nebelieka
  siauros juostos viršutiniame krašte.** Prieš prišvartavimą jo laisvo
  lango būsena normalizuojama. Įsimenama padidinta būsena kitą kartą
  atidarius taip pat grąžinama į keičiamą dydį.

- **Masinis grąžinimas lentelėse ir kituose teksto formatuose dabar
  tikrai grąžina visas pasirinktas reikšmes.** Anoniminant tokius
  žymiklius kaip `[EMAIL]`, Maskuro anksčiau reikšmes rašydavo iš eilės.
  Kai tik pirmoji būdavo pakeista, visų likusių radimo vietų numeriai
  pasislinkdavo, o jau apskaičiuotas planas vis tiek rodė senus
  numerius. Dėl to grįždavo tik dalis pasirinkimo. Dabar visos to paties
  žymiklio pasirinktos reikšmės įrašomos kartu su stabiliais radimo
  vietos numeriais. Jei vieta tampa vienareikšmė tik dėl kito grąžinto
  reikšmės, Maskuro ją tuo pačiu žingsniu patikrina iš naujo – pasirinkimo
  tvarka dėl to nebesvarbi.

- **„Atšaukti pakeitimą" PDF failuose nebepraleidžia pasirinktų
  reikšmių.** Jei žymiklis stovėjo labai arti kito žodžio arba originale
  prie reikšmės tiesiogiai kabojo kablelis, padėties patikra galėjo
  klaidingai priskirti kaimyninį žodį ar skyrybos ženklą reikšmei.
  Bendro grąžinimo metu tada likdavo pavieniai žymikliai ir radimo
  eilutės. Patikra dabar orientuojasi į tikrą žodžio pradžią ir
  atsižvelgia į skirtingą puslapio pasukimą tarp originalo ir rezultato.

- **Grąžintas PDF tekstas dabar išlaiko savo pradinį dydį.** Anksčiau
  matu tarnavo jau mažesniu šriftu surašytas žymiklis; be to, ir
  originaliam tekstui galiojo žymikliams skirta 11 taškų viršutinė riba.
  Dabar originalo langelis ir originalo šrifto dydis perimami iš
  šaltinio failo – tiek naudojant rėmelio įrankį, tiek grąžinant iš
  radimo skydelio.

### Patobulinta

- **Patikros nuoroda dabar aiškiau nurodo likutinę riziką.** Ji aiškiai
  sako, kad Maskuro gali praleisti duomenis ar neteisingai apdoroti
  duomenis, ir prieš kiekvieną paskelbimą ar perdavimą ragina atlikti
  visišką patikrą ir prireikus rankiniu būdu pataisyti. Tai galioja ir
  tekstui iš mainų srities ir yra visiškai perkelta į visus 17 vertimų.

- **Patikros žurnalas dabar pradeda ir savo eilutėse be naudotojo
  vardo.** Pats žurnalas lieka išjungtas, kol įmonė sąmoningai jį
  aktyvuoja. Po to, be papildomo įmonės nurodymo, nei eilutėje, nei
  centrinio mėnesio failo pavadinime nėra naudotojo vardo; ten saugiam
  atskyrimui naudojamas neatspėjamas, tik iš atsitiktinės vietinės
  profilio paslapties išvestas slapyvardis. Licencijos dialogas
  aktyvavimo daugiau nebesiūlo, iš anksto numato „Be žurnalo" ir iš
  anksto nurodo į darbo tarybą, personalo atstovybę bei duomenų apsaugą.

- **Keitimas dabar nurodo, ką jis keičia.** Pažymėtas vardas tampa
  `[NAME_3]`, vietovė – `[ORT_1]`, telefono numeris – `[TELEFON_2]" –
  o ne kaip anksčiau viskas tapdavo `[BEGRIFF_n]`. Rūšis atpažįstama
  spustelėjus; jei ji nevienareikšmė – paprastas žodis arba vardas *ir*
  vietovė viename pasirinkime – lieka bendras terminas. Žymiklis, kuris
  teigia rūšį, kuri neteisinga, būtų blogesnis nei toks, kuris jokios
  nenurodo.

- **Įrankiai taisymo lange dabar turi klavišą.** **S** užtamsina, **E**
  keičia, **Z** grąžina originalą, **V** pikselizuoja. Teksto vaizde jie
  veikia iš karto pažymėjimui, puslapio vaizde jie pasirenka įrankį.
  **Raidės seka kalbą**, kuria valdote programą – angliškai B/R/O/P,
  itališkai O/S/R/P –, nes atminimo pagalba padeda tik savoje kalboje.
  Raidė nurodyta ant mygtuko. Kas tuo metu rašo paieškos juostoje, toliau
  rašo raides – ten jos neveikia.

- **Programa kartą per dieną praneša, kokios būsenos ji veikia – be
  jokio identifikatoriaus.** Taip skaičiuojame, kiek įdiegimų
  naudojama ir kaip tai pasiskirsto tarp bandomojo laikotarpio,
  nemokamos pakopos ir licencijos. Siunčiama būsena, operacinė sistema,
  versija, kanalas, šalis, kalba, aplinka ir atpažinimo pakopa –
  **nieko apie jūsų dokumentus ir nieko, iš ko būtų galima atpažinti
  jūsų kompiuterį**. Du jūsų pranešimai mums atrodo kaip dviejų skirtingų
  žmonių pranešimai; pavieniui keliui iš to nusekti negalima. Kas
  tiksliai siunčiama ir kaip tai išjungti, nurodyta privatumo tekste,
  5 punkte.

- **Skersai paduoti puslapiai dabar savaime stovi teisingai.** Lapą,
  kuris buvo nuskaitytas kreivai to nepažymėjus, taisymas atpažįsta pagal
  teksto tėkmę ir vaizdą ištiesina. Kur to padaryti negalima – esant
  grynam skenavimui be skaitomo teksto –, du nauji įrašai meniu „Rodinys"
  pasuka rankiniu būdu (Ctrl+Shift+L ir Ctrl+Shift+R). Sukamas tik
  rodinys: pačiame faile nieko nekeičiama, o užtamsinimas ir toliau
  paliečia lygiai tą vietą, ant kurios spustelėjama.

- **Vietinė laida dabar visiškai ir matomai turi savo licencijas.**
  Statyba nustato faktiškai supakuotus Python paketus, patalpina jų
  licencijų tekstus kartu su versijų apžvalga aplanke `lizenzen` ir
  nutraukiama, jei kas nors trūksta. Ir Qt, Tesseract bei veido modelis
  turi savo reikiamus tekstus; pačios Maskuro sąlygos pridedamos kaip
  licencinė sutartis.

- **Dabar matoma, kuriame žymiklyje stovi rašymo žymeklis.** Kas
  spustelėja į žymiklį, mato jį visą nušvintantį – kartu su skliaustais
  ir numeriu. Mygtukas „Grąžinti pasirinkimą" jau anksčiau reagavo į
  vieną spustelėjimą; tik nesimatė, kurią žymę jis pataikė. Švytėjimas
  lieka net tada, kai pelė pajuda link mygtuko.

- **Pelės žymeklis dabar sako, koks įrankis pasirinktas.** Keturi
  įrankiai dalijasi ta pačia sritimi ir tuo pačiu gestu; iki šiol visi
  atrodė vienodai. Kryžius reiškia užtamsinti, uždaryta ranka – keisti,
  atvira ranka – grąžinti.

- **Paruoštas „Office" dokumentas dabar pats save atmeta.** „Word",
  „Excel" ar „OpenDocument" failas gali turėti instrukcijų, kurios
  atidarant nutraukia svetimą failą jūsų kompiuteryje į savo tekstą arba
  perpildo atmintį. Abu atvejai buvo atmetami ir anksčiau – bet tai
  darė įmontuota XML biblioteka, o ne Maskuro. Dabar tai sprendžia pati
  programa, nepriklausomai nuo to, kokia šios bibliotekos versija yra
  pakete. Įprastiems dokumentams niekas nesikeičia.

### Ištaisyta

- **Radimo skydelis dabar pašalina užtamsintus žymiklius.** Jei, pvz.,
  `[NAME_1]` buvo užtamsintas taisymo lange, jo reikšmės eilutė anksčiau
  likdavo dešinėje, nors dokumente tokios vietos jau nebuvo. Eilutė
  dabar dingsta kartu su paskutine radimo vieta; jei tas pats žymiklis
  vis dar yra kitoje vietoje, ji išlieka.

- **Grąžinant pasuktame puslapyje kaimyninis žodis dabar išlieka.**
  Užtamsinimo juosta sąmoningai šiek tiek išsikiša už teksto ribų; jau
  šis siauras kraštas anksčiau galėjo pagriebti gretimą žodį, pvz., „im".
  Dabar skaičiuojasi tik aiškus persidengimas, o ne tik prisilietimas
  prie krašto.

- **Antras pakeitimas toje pačioje eilutėje nusinešdavo tolesnį
  sakinį.** Kas „Sachbearbeitung Quaxi Blubbo übernimmt" pakeitė du
  kartus iš eilės, gaudavo „Sachbearbeitung [ORT_1] [ORT_2]" – žodis už
  jo buvo dingęs be pakaitalo, be jokio pranešimo. Priežastis buvo
  gretimas žymiklis: eilutės likutis po pirmo pakeitimo prasideda
  tarpu, o teksto vietos paieška pagriebdavo kaimyno uždaromąjį
  skliaustą. Po to viskas buvo pasislinkę vienu simboliu. Paveikta buvo
  kiekviena eilutė, kurioje buvo keičiama ar užtamsinama du kartus – ir
  grąžinant šalia.

- **Keitimas nebeužtamsina, kai žymiklis per ilgas.** Jei šalia žodžio
  nebuvo vietos `[BEGRIFF_2]`, sritis anksčiau būdavo užtapyta juoda – ir
  tuomet nebesimatė net to, kad ten kažkas buvo, juo labiau nebuvo ką
  grąžinti. Dabar rašomas trumpesnis užrašas: `[BEGR_2]`, `[BE_2]`,
  prireikus `[B_2]`. Eilės numeris išlieka kiekvienoje pakopoje – pagal
  jį grąžinimas vietą vėl suranda. Tik ten, kur netelpa net trumpiausias,
  lieka juosta.

- **Keitimas palikdavo tekstą, jei toje pačioje eilutėje jau buvo
  užtamsinta.** Kas taisymo lange grąžino vardą iš originalo, iš jo
  pakeitė vardą (ten nebuvo vietos – atsirado juosta) ir po to pakeitė
  pavardę, gaudavo įterptą žymiklį, tačiau vardas **nebuvo pašalintas**.
  Tai buvo pastebėta tik iš antrinės peržiūros perspėjimo. Priežastis
  buvo pati eilutė: po pirmo užtamsinimo jos likutis prasideda tarpu, ir
  teksto vietos paieška ten neturėjo atramos. Tai paveikė kiekvieną antrą
  užtamsinimą toje pačioje eilutėje.

- **Įjungtas išplėstinis atpažinimas be jo modelio dabar pastebimas.**
  Varnelė galėjo būti pažymėta, nors modelio trūko – nustatymai galioja
  kiekvienam diegimui, o modelis yra šalia programos. Valymas tuomet
  vykdavo be šios pakopos, be jokio žodžio apie tai. Dabar varnelė
  sako, kad modelio trūksta, o rezultatas turi perspėjimą. Kartą
  padarytas pasirinkimas išlieka išsaugotas: kai tik modelis įkeltas,
  jis vėl veikia.

- **Anoniminant dabar grąžinamas teisingas terminas.** Kas kelis
  terminus pakeitė ranka ir po to vieną iš jų grąžino, visada gaudavo
  **pirmąjį** – iš „Schmidt" tapdavo „Müller". Priskyrimas kiekvienam
  žymikliui įsimindavo tik vieną pakeitimą, o anoniminant visi turi tą
  patį žymiklį; antras ir kiekvienas tolesnis terminas dėl to
  prarandamas. Dabar kiekviena reikšmė gauna savo eilutę – taip pat ir
  pakeitimų sąraše, kuris anksčiau buvo per trumpas.

- **Lentelėse dabar taip pat galima grąžinti.** CSV ar personalo sąraše
  žymikliai stovi tiesiogiai vienas šalia kito, atskirti tik
  kabliataškiu. Iki šiol programa negalėjo nustatyti, kuri reikšmė
  kurioje vietoje stovėjo, ir atsisakydavo – su `[NAME]` pavykdavo, su
  `[GEBURTSDATUM]" ir `[TELEFON]" ne. Dabar ji išskaido eilutę pagal
  visus žymiklius. Jei vieta lieka tikrai dviprasmiška, ji ir toliau
  atsisako: neteisingai grąžinta reikšmė būtų blogiau nei nesuteikta
  informacija.

- **Ir atsisakymas dabar matomas.** Jis stovėjo pilkšva spalva
  apatiniame lango krašte, o sakinys buvo toks ilgas, kad būdavo
  nukirstas – atrodydavo, tarsi nieko nevyktų. Sakiniai sutrumpinti, o
  eilutė kelias sekundes nušvinta perspėjimo spalva.

- **Grąžinimas dabar išlieka ir po kito veiksmo.** Kas anoniminant
  grąžino kelias vietas ir po to pakeitė kažką kito, rasdavo visas
  grąžintas vietas vėl pakeistas ir turėdavo pradėti iš naujo.
  Priežastis buvo priskyrimas: jis išlaikė reikšmę, o savaiminis
  suderinimas dėl vienodų žymiklių ją kitą kartą rašant vėl
  grąžindavo. Dabar galioja: kas grąžinta, lieka grąžinta – kitos to
  paties reikšmės vietos dėl to nekeičiamos.

- **Teksto, „Word", „Excel" ir e. pašto failuose dabar tikrai pakanka
  spustelėti į žymiklį.** Pranešimas apie tai buvo jau ankstesnėje
  versijoje, tačiau mygtukas „Grąžinti pasirinkimą" liko užrakintas,
  kol kas nors nebuvo tiksliai pažymėta – taigi nebuvo net galimybės
  pasiekti kelio, kuris pats nustatytų pasirinkimą.

### Ištaisyta

- **Patikros žurnalas daugiau neatskleidžia failo pavadinimo.** Jis
  sąmoningai failus registruoja kaip maišos reikšmę, o ne atviru tekstu,
  nes failo pavadinimas atskleidžia klientą ir ginčo dalyką. Tačiau šią
  maišos reikšmę buvo galima patvirtinti spėjant – kelias nėra
  atsitiktinis skaičius. Dabar į skaičiavimą įtraukiama atsitiktinė
  šio diegimo reikšmė: skaičiavimas ir atskyrimas žurnale ir toliau
  veikia, o perskaičiavimas iš išorės – ne.

## 0.10.31-alpha.20260819 – 2026 m. rugpjūčio 19 d.

### Patobulinta

- **Ir teksto bei lentelių failuose žymiklis rodant nušvinta raudonai.**
  Anksčiau raudona peržiūra buvo tik PDF puslapyje. Dabar abu vaizdai rodo
  tą patį: kas raudona, tą paliestų kitas veiksmas – ir pakanka spustelėti,
  kad grąžintum.

- **Pakanka spustelėti žodį – rėmelį sukuria pats redaktorius.** Taisymo
  lange anksčiau reikėjo virš kiekvienos vietos nutraukti rėmelį. Dabar
  pakanka spustelėjimo: rėmelis apsigaubia aplink žodį ir lieka pasiekiamas,
  taigi jį galima toliau tempti ar perkelti. Vedant pele virš žodžio jis jau
  nušvinta raudonai, kad iš anksto matytum, ką paliestų spustelėjimas. Kur
  žodžio nėra, kaip ir anksčiau tempiamas rėmelis.

- **Su rėmeliu nebereikia taikytis tiksliai.** Kas tempia rėmelį virš
  žymiklio ar užtamsinimo, visada turi omenyje visą vietą – niekada tik jos
  pusę. Todėl rėmelis savaime išsiplečia iki viso, ką jis paliečia: iki
  viso žymiklio, visos juostos ar, nuskenuotame lape, iki viso užtamsinto
  ploto. Mažesnis už nutemptą rėmelį jis niekada netampa.

- **Dabar užtamsinama žodžiu.** Rėmelis virš pusės žodžio anksčiau
  užtamsindavo tik pusę – o pusiau užtamsintas vardas vis tiek yra vardas.
  Paliesti žodžiai dabar krenta visiškai; kaimynas lieka nepaliestas.

- **Tekste ir lentelėse pakanka spustelėti į žymiklį.** „Grąžinti pasirinkimą"
  anksčiau reikalavo tiksliai pažymėti žymiklį kartu su laužtiniais
  skliaustais. Dabar pakanka įdėti žymeklį; pasirinkimas matomai peršoka
  ant viso žymiklio.

- **Prisidėjo Belgija kaip šalis.** Pasirenkama nustatymuose; tada
  atpažįstami belgiški telefono numeriai, nacionalinio registro numeris
  (su kontroliniu skaitmeniu), PVM / įmonės numeris (su kontroliniu
  skaitmeniu), adresai abiem oficialiomis kalbomis ir pašto kodas su
  vietove. Anksčiau belgiški telefono numeriai likdavo, nes šalies iš
  viso nebuvo sąraše.

- **Atnaujinimo kanalas dabar sako, kaip anksti gaunate naujienas, o ne
  kaip toli.** Kas buvo nustatytas ties „Bandomoji versija", naujos
  peržiūros ar naujos stabilios versijos iš viso negaudavo pasiūlytos ir
  turėjo ranka pakeisti kanalą, kad apie tai sužinotų. Dabar siūloma ir
  viskas, kas patikimiau: bandomoji versija priima bandomąsias versijas,
  peržiūras ir stabilias versijas, peržiūra priima peržiūras ir stabilias.
  Atvirkščiai niekada – peržiūros kanale bandomoji versija nesiūloma,
  net jei ji naujesnė.

- **Nustatymų lange eilutės ir toliau stovi toliau viena nuo kitos.**
  Keturi puslapiai naudojo savo tarpus vietoj tinklelio, galiojančio
  likusioje programoje; ypač puslapyje „Atpažinimas" žymimieji langeliai
  dėl to stovėjo pastebimai per arti.

### Ištaisyta

- **Užpildytos PDF formos rankinio taisymo metu nebeatrodo tuščios.**
  Maskuro tam paverčia tik laikinąją, trumpalaikę darbo kopiją į statiškus
  puslapius: įrašytos reikšmės tampa matomos ir tikrai gali būti
  užtamsintos; nuskaitomi formos laukai neišlieka paslėpti faile. Originalas
  lieka interaktyvus ir nepakeistas. Tai dabar galioja ir dinaminėms XFA
  formoms: XFA palaikantis PDFium pirmiausia sukuria reikšmes ir puslapių
  lūžius, po to naujas PDF sukuriamas tik iš statiškų vaizdo puslapių. Jei
  XFA kūrimas nepavyksta, failas saugiai atmetamas, o ne atrodo tariamai
  tuščias.

- **„Atšaukti" veikia dabar ir tikslesnio atpažinimo metu.** Anksčiau
  mygtukas užsiblokuodavo paspaudus, tačiau paleidimas skaičiuodavo toliau
  iki paskutinio bloko – ilgame faile tai reiškia minutes be išeities, o
  mygtukas tuo metu atrodė, tarsi būtų suveikęs. Dabar paleidimas
  baigiasi ties kitu bloku.

- **CSV failuose vardai dabar randami ir tada, kai prieš juos nėra
  tarpo.** Įraše `P-1000;Brunnthaler, Elisabeth` darbuotojo numeris per
  kabliataškį prilimpa prie vardo, ir atpažinimui tai buvo vienas žodis
  be vardo jame – personalo sąrašuose dėl to priklausomai nuo eilutės
  likdavo visas vardas. Telefono numeriai, formulės ir failo stulpelių
  skaičius dėl to nepasikeičia.

- **Vardas, kurio vardas ir pavardė abu turi brūkšnelį, dabar
  atpažįstamas.** „Marie-Luise Habsburg-Ott" likdavo sakinio viduryje,
  kai „Dragan Mitrović" tame pačiame sakinyje būdavo randamas – būtent
  dviejų susietų pusių derinį kalbos modelis praleisdavo. Susieti
  daiktavardžiai kaip „Šiaurės–Pietų jungtis" ar „programinės įrangos
  kūrėjas" dėl to nepaveikiami.

## 0.10.30-beta.1 – 2026 m. rugpjūčio 18 d.

### Patobulinta

- **Teksto rodinio šrifto dydį dabar galima matomai keisti.** Slankiklis
  apačioje dešinėje, kuris iki šiol didino ir mažino tik puslapio rodinį,
  Taisymo lange tekstinių ir raštinės dokumentų failuose keičia šrifto dydį
  (50–300 %) – taip pat kaip „Didinti"/„Mažinti" meniu Rodinys. Ctrl+pelės
  ratukas tai galėjo visada, bet tai žinojo tik tas, kas išbandė; dabar
  slankiklis, rodmuo ir ratukas veikia kartu.

- **Tamsiame apipavidalinime dabar ant tamsaus darbo lauko guli baltas
  lapas.** Iki šiol buvo atvirkščiai: aplink lapą liko šviesus laukas, o
  pats tekstas buvo šviesus tamsiame fone. Dabar lapas abiejuose
  apipavidalinimuose lieka popieriaus baltumo su juodu tekstu – kaip PDF
  puslapis, kuris tamsiajame režime irgi netampa tamsus – o laukas aplink
  jį yra tamsus.

### Pataisyta

- **Po pašalinimo sakinio viduryje likusi sakinio dalis nebedingsta.**
  Kas Taisymo lange tris kartus grįžo prie tos pačios vietos – pakeitė,
  pašalino, tada „Atkurti originalą" –, tam ištrindavo sakinio pradžią:
  iš „Rückfragen richten Sie bitte an das Rechnungswesen." liko „bitte an
  das Rechnungswesen.", be jokio įspėjimo. Paveikta buvo kiekviena vieta,
  kur eilutės viduryje jau kartą kas nors buvo pašalinta.

- **Paleidimo klaida nebenutraukia programos uždarymo.** Kai pagrindinio
  lango kūrimas nutrūkdavo, tada sugriūdavo ir uždarymas per užduočių
  juostos ženkliuką – ir ši antra klaida klaidos pranešime nuslėpdavo
  tikrąją priežastį. Dabar programa tvarkingai užsidaro net iš iki galo
  nesukurto lango, o išsaugoti nustatymai lieka nepaliesti.

- **„Prieš/Po" nebešoka į dokumento pradžią.** Kas Taisymo lange buvo
  nusiritęs žemyn ir palyginimui persijungė į originalą, atsidurdavo vėl
  visai viršuje – ir turėdavo vietą surasti iš naujo rankiniu būdu.
  Rodinys dabar lieka toje pačioje eilutėje abiem kryptimis.

- **Šalinant liko paskutinė raidė lygiuotose pagal abu kraštus eilutėse.**
  Kai teksto komanda nupiešia daugiau glifų, nei skaitymo biblioteka
  praneša simbolių – lygiuojant pagal abu kraštus ji mielai „praryja"
  tarpą –, priskyrimas pasislinkdavo per vieną, ir iš „Dr. Michael Handler
  aus Willendorf" gaudavosi „[NAME] r aus f": dvi likusios raidės tiesiog
  bendrinto teksto viduryje (rastas tikrame tarybos posėdžio protokole).
  Priskyrimas dabar patikrinamas pagal paties komandos teksto turinį, kur
  tik jis įskaitomas – ten nebespėjama.

- **„Lerchenfelder Gürtel 43/12" buvo pašalintas tik iš pusės.** Adresų
  šablonai nepažino nei Gürtel, nei Kai, Lände, Zeile, Markt, nei Graben
  kaip gatvės pagrindinio žodžio, o namo numeris negalėjo turėti dalių su
  pasviruoju brūkšniu (43/12, namas/durys) – numeris likdavo šalia
  vietaženklio. Abu dalykai papildyti; Vienos ir Zalcburgo adresai dabar
  pašalinami visiškai.

- **Išsaugotos svetainės po bendrinimo lieka veikiančios.** Adresai, kuriuos
  tingusis krovimas (lazy-loading) saugo data-atributuose (`data-lazy-src`,
  `data-lazy-srcset`), buvo pakeisti kaip nuorodos – tikroje savivaldybės
  svetainėje šešiolika kartų – ir po to svetainės paveikslėliai nebeįsikeldavo.
  Interneto adresai ten dabar lieka, kaip ir `src` bei `href` atveju; vardai,
  el. pašto adresai ir telefono numeriai data-atributuose ir toliau
  pakeičiami.

- **Japoniški ir korėjietiški dokumentai buvo apdorojami kaip kiniški.**
  Kalbos atpažinimas visus tris raštus metė į vieną krūvą, japoniškame
  tekste (be tarpų) ir korėjietiškame (su prilipusiomis dalelytėmis)
  nerasdavo jungiamųjų žodžių – ir tada tiesiog imdavo pirmą sąrašo CJK
  kalbą. Taip japoniškas tarybos posėdžio protokolas ir korėjietiškas
  susirinkimo protokolas būdavo perskaitomi kinišku modeliu. Dabar
  sprendžia pats rašto vaizdas: kana reiškia japonų, hangul reiškia
  korėjiečių.

- **Kitos klaidos, rastos lauko bandymuose dar dešimtyje kalbų:** pareigybės
  kaip „Primar", „Gradonačelnik", „Ordfører", „Başkanı" ar „Δήμαρχος"
  nebelaikomos asmenvardžiais; turkiškos lauko antraštės („Adı", „Soyadı")
  ir graikiški pokalbio žodžiai („Ωραία", „Βεβαίως") nebešalinami; nutarimų
  ir straipsnių numeriai su data („323/25-6-2008", „27 30.09.2024") nebėra
  telefono numeriai; o sakinio nuolaužos su tašku („10.An", „T.U.EE", „…pa")
  nebekeičiamos kaip interneto adresai.

### Nauja

- **Patikros ataskaitos pageidaujant automatiškai.** Varnelė nustatymuose
  (puslapis „Programa") po kiekvieno bendrinimo savaime sukuria patikros
  ataskaitos PDF – su laiko žyma pavadinime, atskirame aplanke, niekada
  šalia rezultato. Vėliau lapo sukurti nebegalima; kam jo reikia bylai,
  tas jį dabar turi visada. Numatytasis nustatymas – išjungta.

- **Patikros žurnalą dabar galima įjungti programoje.** Įkeliant įmonės
  licenciją, Maskuro vieną kartą paklausia, ar žurnalas turi būti
  vedamas – įrodymas turi vertę tik jei veikia nuo pat pradžių. Tam skirtas
  jungiklis nustatymuose (puslapis „Programa", matomas su įmonės licencija
  arba bandomuoju laikotarpiu); administravimo nustatymų failas ir toliau
  galioja ir gali reikšmę priverstinai nustatyti, kaip iki šiol. Sava
  žurnalo eilutė „įjungta" fiksuoja, nuo kada vedama – taip patvirtinama ir
  pasirašoma įrašymo pradžia. Numatytai žurnalas lieka išjungtas.

- **Rodiklių skydelis rodo, ką atliko DI pakopa.** Nauja eilutė nurodo,
  kiek neaiškių atitikmenų modelis įvertino, paliko ir atmetė bei kiek dar
  papildomai rado – iki šiol jo darbas buvo nematomas, jei nespausdavai
  kiekvienos reikšmės Taisymo redaktoriuje. Tik skaičiai, niekada reikšmės
  ar pagrindimai; be DI darbo eilutė nerodoma.

- **Atkūrimas dabar veikia ir el. laiškuose bei HTML puslapiuose.** `.eml`,
  `.msg` ir išsaugotose svetainėse vietaženklio iki šiol atšaukti
  nebuvo galima – programa tai sąžiningai pranešdavo, bet būtent el.
  laiškas yra formatas su daugiausia asmeninių duomenų. Dabar atkūrimas
  ten veikia lygiai taip pat: iš atitikmenų skydelio, su pažymėta atranka
  ir net su anoniminiais vietaženkliais. Kartu perkeliamas ir nematomas
  el. laiško HTML šakas (tai, ką iš tikrųjų rodo Outlook), kad rodinys ir
  žinutė sutaptų.

- **Atitikmenų skydelis atkuria ir anonimintas reikšmes – po vieną.**
  „Atšaukti pakeitimą" anonimintuose failuose iki šiol buvo užrakintas,
  nes „[NAME]" reiškia visus vardus vienu metu. Dabar atkūrimas
  originale patikrina, kuri vieta priklauso kuriai reikšmei – PDF pagal
  radinio koordinates, teksto rodinyje lyginant su originalu – ir atkuria
  būtent pasirinktos reikšmės vietas. Kitų reikšmių eilutės lieka
  nepaliestos.

- **Anoniminius vietaženklius dabar galima atkurti ir po vieną.**
  Anonimindama programa visiems tos pačios rūšies duomenims suteikia tą
  patį pavadinimą – „[NAME]" reiškia kiekvieną asmenį, ir iki šiol dėl to
  buvo sakoma: po vieną atkurti negalima. Dabar patikrinama originale, kuris
  vis tiek yra šalia rezultato: teksto rodinyje pažymėkite vietaženklį ir
  pasirinkite „Atkurti pažymėjimą" – atkuriama būtent ta vieta su būtent
  jos reikšme. Jei reikšmės iš originalo vienareikšmiškai nustatyti
  nepavyksta, programa tai pasako, o ne spėlioja. Atitikčių failas dėl to
  ir toliau nesukuriamas.

- **Taisymo langas po bendrinimo dabar atsidaro pats.** Nė vienas įrankis
  neranda visko – todėl rezultato tikrinamasis žvilgsnis yra įprastas
  žingsnis, o ne papildomas paspaudimas. Kas to nenori, tai išjungia
  nustatymuose skiltyje „Atpažinimas" („Po bendrinimo rodyti rezultatą
  Taisymo lange").

### Patobulinta

- **Šalies pasirinkimas dabar numatytai „automatinis".** Iki šiol pagal
  nutylėjimą galiojo sąsajos kalbos regionas – vokiškame kompiuteryje
  nyderlandiški ar prancūziški dokumentai buvo bendrinami tik DACH
  atpažinikliais, o adresas kaip „Universiteitslaan 1" likdavo (rastas
  tikruose, viešuose tarybos posėdžių protokoluose). Dabar šalies
  pasirinkimas priklauso nuo dokumento kalbos; kas nustatymuose pasirinko
  fiksuotą reikšmę, ją ir išlaiko.

- **Mažiau klaidingai pašalinta.** Eilė klaidų, išmatuotų pagal patikros
  korpusą ir tikrus susirinkimų protokolus šešiomis kalbomis, išnyksta:
  įmonių pavadinimai su teisine forma („Musterfirma GmbH") nebelaikomi
  asmeniu ar vieta, o organizacija; pasisveikinimo frazės ir plikos
  kreipinio formos („Saygılarımızla", „Buenas tardes", vienišas „Frau")
  nebėra vardai; pareigybės („Bürgermeister", „Sindaco", „Alcalde") lieka
  nepaliestos; įstatymų ir nutarimų numeriai („39/2015") bei sumos su
  tūkstantiniu skirtuku („330.000") nebėra telefono numeriai; sakinio
  pradžios kaip „Envíame" ar „Estarei" nebelaikomos vardu; atitikmuo per
  tuščią eilutę nebeskaičiuojamas kaip vardas. Sąskaitos numeris sąskaitoje
  išlieka kaip dokumento žymuo – kliento numeris ir bylos numeris ir toliau
  pašalinami.

- **Prieš įkeliant DI modelį dabar parašyta, kam jis skirtas.** Įkėlimo
  dialogas įvardija modelio užduotis – vertinti neaiškius atitikmenis,
  rasti papildomus vardus, siūlyti taisykles ir profilius – ir atvirai
  sako, kad tai nėra pokalbių asistentas. DUK tą patį klausimą atsako
  išsamiai („Ką gali ir ko negali DI pakopa?"), visose kalbų versijose.

### Pataisyta

- **Patikros ataskaitų PDF iš komandinės eilutės dabar galima ieškoti
  tekste.** Windows sistemoje beantraštis PDF kelias startuodavo be
  jokio šrifto – kiekvienas simbolis buvo piešiamas kaip pakaitos
  langelis, o lape nebūdavo nuskaitomo teksto: kas jame norėdavo ieškoti
  ar ką nors nukopijuoti, nieko nerasdavo. Dabar tokiu atveju ataskaita
  pasikrauna sistemos šriftus; tekstas įterptas ir nuskaitomas. Ataskaitos,
  sukurtos iš lango, niekada nebuvo paveiktos.

- **„Atkurti originalą" per kelias skenuoto dokumento eilutes palikdavo
  juodus ruožus tarp eilučių.** Į paveikslėlį paverstame puslapyje rėmelis
  sutvarkydavo tik pačias eilučių juostas; ankstesnio pašalinimo likučiai
  likdavo tarpuose tarp jų. Dabar nubrėžtas rėmelis visiškai padalijamas
  tarp eilučių.

- **Antras rėmelis virš vietaženklio palikdavo raudoną likutį.** Vietaženklis
  beveik visada platesnis nei žodis, kurį jis atstoja; kas po to pašalindavo
  toje pačioje vietoje, paliesdavo tik jo pradžią – likdavo nuolauža kaip
  „RIFF_1]" sakinio viduryje, o atkūrimas vėliau originalų tekstą įrašydavo
  jos, o ne žodžio vietoje. Nukirstas vietaženklis dabar visada pašalinamas
  visas.

- **Pasuktame puslapyje pašalinimas virš vietaženklio ištrindavo su tuo
  nesusijusį sakinį.** Vėliau nupieštas vietaženklis šalinant būdavo
  supainiojamas su prieš jį esančiu tekstu: jis pats likdavo, atsirasdavo
  įspėjimas „vis dar yra dokumente" – o kitoje puslapio vietoje be pėdsako
  dingdavo sakinys, su rėmeliu nesusijęs. Vietaženklis dabar iš naujo
  surandamas pagal savo tekstą; grandinė „pakeisti, pašalinti, atkurti" nuo
  šiol veikia ir įstrižai pasuktuose puslapiuose.

- **Vadove dešimčia kalbų vis dar buvo patariama diegti `python3-tk`.**
  Klaidų šalinimo skyriuje buvo rašoma, kad Linux sistemoje gali trūkti
  tkinter – patarimas iš laikų prieš Qt sąsają, kuris nieko nebepadeda.
  Dabar visose versijose parašyta tas pats, kas vokiškoje: trūksta
  sistemos bibliotekų, kurių reikia Qt vaizdavimui.

- **Vadovo licencijos skyrius visuose šešiolikoje vertimų buvo pasenęs.**
  Dešimtyje kalbų buvo rašoma, kad Windows Server reikalinga įmonės
  licencija su serverio prieiga, o bandomasis laikotarpis ir nemokamas
  lygis ten neveikia – nuo tada, kai vietą skaičiuoja žmogus, o ne
  mašina, abu teiginiai neteisingi. Be to, visur trūko informacijos apie
  tai, kada užimta vieta vėl atlaisvinama, kad licencija reguliariai
  patvirtinama ir kas tuo metu perduodama, o aktyvinimas be interneto buvo
  aprašytas tik sutrumpintai, be trijų žingsnių ir be pastabos, kad
  kompiuteris po to metus veikia be ryšio.

- **Septyni pastraipos apie Taisymą trūko dešimtyje kalbų.** Kas skaitė
  pagalbą danų, suomių, prancūzų, italų, nyderlandų, norvegų, lenkų,
  portugalų, švedų ar ispanų kalba, nerado nei raštinės failų puslapio
  rodinio, nei „Šalinti rankiniu būdu", nei viso skyriaus apie tai, kaip
  programa mokosi iš pataisymo – kartu su lentele apie tris platumas.
  Skyriuje „Kas atpažįstama" toms pačioms dešimčiai versijų trūko kelio
  per dokumento antraštę.

- **Su įkelta licencija programa nebepasileisdavo.** Vietoj lango
  pasirodydavo „Programos paleisti nepavyko" – ir tai su bet kuria
  licencija, kad ir kokia. Priežastis buvo licencijos rodinio eilutė,
  kuri įspėja likus nedaug laiko iki bandomojo laikotarpio pabaigos; ji
  kreipėsi į kažką, kas ten nebuvo prieinama. Be licencijos – bandomuoju
  laikotarpiu ir nemokamu lygiu – klaida nepasireikšdavo, todėl ji
  pastebėta tik dabar.

- **Formose lauko pavadinimai lieka.** „Geburtsdatum" ir „Anschrift"
  dingdavo kartu su savo reikšme: vietaženklis stovėdavo mažas ir
  raudonas *lauko pavadinimo* vietoje, o pats laukas apačioje likdavo
  tuščias. Lauko pavadinimas nepriklauso duomenims – jis dabar lieka, o
  vietaženklis stovi ten, kur buvo reikšmė.

- **Kitakalbiai dokumentų antraštiniai pavadinimai nebelaikomi vardais.**
  Virš itališkos formos buvo parašyta „FATTURA", virš ispaniškos –
  „PERMISO PARENTAL" – abi buvo pašalintos. Dokumento žodžių sąrašas
  pažino tik vokiškus atitikmenis.

- **Iš sąskaitos nebedingsta jokia pozicija.** „Materialaufschlag
  1  84,00" buvo palaikoma adresu ir pakeista vietos vietaženkliu –
  dokumente po to trūkdavo vienos eilutės. Eilutė, kuri baigiasi suma,
  yra pozicija, o ne adresas; tikri adresai („Hauptstraße 1  120,00")
  lieka nepaliesti.

### Pakeista

- **„Stebėti aplanką …" ir komandinė eilutė kol kas pašalinti.** Abu
  keliai sukurti ir veikia, tačiau nė vienas iš jų nebuvo išbandytas
  praktikoje: aplanko stebėjimas niekada nebuvo tikrintas Windows
  sistemoje, o komandinė eilutė scenarijui atiduoda du tuzinus jungiklių,
  kurie pas jokį naudotoją niekada neveikė. Kas be priežiūros keičia
  dokumentus, neturėtų to daryti nepatikrinta – todėl jie pašalinti, kol
  patikra neatlikta. Meniu punktas dingsta, o `--wache` nebeliko
  `maskuro --help`.

- **Lieka aišku, kas tik skaito ir ko šiaip reikia.** Paieška
  (`--suchlauf`) ir patikrinimas (`--nachpruefen`) komandinėje eilutėje
  ir toliau veikia – jie nekeičia jokio failo. Taip pat lieka nepakitęs
  paleidimas iš Explorer, kontekstinio meniu, iškarpinės ir lango.

- **„Gauti iš skaitytuvo" dabar turi savo skyrių vadove.** Iki šiol jis
  buvo skyriaus „Stebėti aplanką" pabaigoje. Mac sistemoje ten buvo
  patariama leisti stebėti aplanką; dabar patariama nuskaitytus puslapius
  tiesiog vilkti į langą.

### Pataisyta

- **„Atkurti originalą" per kelias eilutes ardydavo struktūrą.** Rėmelis
  virš vietaženklio, nepakeistas pareigybės pavadinimas ir antras
  pakeitimas visą sritį iš naujo įdėdavo kaip **vieną** eilutę – iš trijų
  eilučių gaudavosi viena, o kas nebetilpo, virsdavo juosta. Dabar
  kiekviena eilutė atkuriama atskirai.

- **O nepakeistas tekstas lieka nepaliestas.** Kas apibrėžia sritį virš
  pakeitimo *ir* įprasto teksto, atgauna tik pakeitimą; likusi dalis
  nepaliečiama. Kartu dingsta ir paskutinis seno vietaženklio likutis –
  anksčiau jo uždaromasis skliaustelis likdavo sakinio viduryje.

- **Keičiant nebelieka seno teksto likučių.** Paryškintoje antraštėje
  atsirasdavo „1. R[BEGRIFF_2]ige [BEGRIFF_1] … che" – vietaženklis stovėjo
  savo vietoje, bet šalia liko originalo skiemenys. Dabar sutvarkoma
  visa sritis, kurią apvedate, o ne vien žodžių langeliai joje.

- **Anoniminis vietaženklis nebeatkuriamas.** Anonimindama programa
  kiekvienam vardui suteikia tą patį `[NAME]`. Atkūrimas imdavo pirmą
  pasitaikiusį įrašą ir įrašydavo jį į kiekvieną radimo vietą – iš
  „Georg Aigner" gaudavosi „Anna Musterfrau", taigi dokumente atsirasdavo
  neteisingas vardas. Dabar rodoma, kad nebeįmanoma nustatyti, kuri
  reikšmė buvo turima omenyje; dokumentas lieka nepaliestas.

### Nauja

- **„Atkurti originalą" dabar veikia ir rastrizuotame puslapyje.** Kai
  puslapis buvo paverstas paveikslėliu, iki šiol pasirodydavo atsisakymas:
  atkurtas tekstas atsidurtų po puslapio paveikslėliu. Dabar toje vietoje
  paveikslėlyje sutvarkoma vieta ir ant jos užrašomas tekstas – kaip
  vietaženklis skenuotame dokumente. Turinys tuo metu imamas iš pirminio
  failo, o jis nėra rastrizuotas.

- **„Atkurti pažymėjimą" dabar yra atskiras mygtukas.** Tai veikė ir anksčiau,
  bet tik jei atsitiktinai pažymėdavai vietaženklį ir paspausdavai
  „Pakeisti pažymėjimą" – funkcijos, kurią randi tik atsitiktinai,
  naudotojui tarsi nėra.

### Pakeista

- **Grynajame tekste, CSV ir Outlook laiškuose nebėra „Pažymėjimą
  pašalinti".** Šie formatai negali turėti juostos; mygtukas ten
  nustatydavo vietaženklį ir tai net pasakydavo – bet mygtukas, kuris
  daro ką kita, nei sako jo pavadinimas, čia nedera.

- **Įrankis dabar praneša, jei toje vietoje nėra ką veikti.** Vietaženklio
  dar kartą pakeisti negalima, virš pašalinimo vietaženklis nebededamas,
  o ten, kur jau yra originalas, nėra ko atkurti. Iki šiol šie veiksmai
  atrodydavo, kad kažką daro, nors iš tikrųjų nieko nedarė.

## 0.10.29-alpha.20260817 – 2026 m. rugpjūčio 17 d.

### Ištaisyta

- **Taisymo lange dabar veikia kiekvienas nutemptas rėmelis.** Kas toje
  pačioje vietoje dirbo du kartus – pirma keitė, po to užtamsino, po to
  grąžino originalą –, to antras ir trečias veiksmas nutildavo be jokio
  pranešimo: dar pasiekiamas ankstesnio veiksmo rėmelis jį pagaudavo.
  Tas pats vykdavo keičiant įrankį, kai net tyliai toliau veikdavo senas
  įrankis.
- **Per siaurai nutemptas rėmelis sako, kad jis per siauras.** Anksčiau
  peržiūroje žodis nušvisdavo raudonai, o atleidus be jokio žodžio
  nieko neįvykdavo.

- **„Outlook" žinutes pagaliau galima taisyti.** `.msg` failas taisymo
  lange rodydavo „Šis formatas čia negali būti rodomas" – tai buvo
  vienintelis palaikomas formatas be jokio būdo taisyti rankiniu būdu.
  Dabar siuntėjas, gavėjas, tema ir žinutės tekstas rodomi pavadinti
  vaizde ir gali būti pažymėti bei pakeisti kaip bet kuriame kitame
  teksto formate.

- **„Keisti pasirinkimą" e. laiške lieka prie pasirinkimo.** Kas pažymėjo
  vardą rišliame tekste, kartu prarasdavo siuntėją ir gavėją iš antraščių,
  o pranešime buvo minimas kitas žymiklis nei tas, kuris stovėjo tekste.
  Dabar pažymėta reikšmė keičiama visur – ir siuntėjo lauke, jei ji ten
  stovi – o kas kita neliečiama.

- **Rėmelis per kelias eilutes daugiau nebesugadina teksto.** Anksčiau
  vienoje vietoje atsirasdavo vienas vienintelis žymiklis: nuo nukirsto
  žodžio likdavo prilipęs likutis, o iš antros eilutės tekstas dingdavo
  be pakaitalo – nei žymiklio, nei juostos, tik tuščia vieta. Dabar
  kiekviena eilutė gauna savo žymiklį su reikšme, kuri joje iš tikrųjų
  stovėjo.

- **„Grąžinti originalą" dabar veikia ir po užtamsinimo.** Langas
  pranešdavo apie sėkmę, o tekstas niekada negrįždavo: juoda juosta
  skaičiuodavo kaip kliūtis, todėl grąžintam tekstui nebelikdavo vietos.
  Juosta dabar tokiu atveju pasitraukia, ir grąžintas tekstas stovi
  juodas kaip įprastas tekstas – ne raudonas kaip žymiklis.

- **„Grąžinti originalą" nepaliestoje vietoje daugiau nieko nedaro.** Kas
  ištempė rėmelį virš teksto, prie kurio niekas nebuvo keista, gaudavo
  tekstą pašalintą ir vėl įterptą mažesnį bei pastumtą – buvo pranešama
  apie sėkmę. Dabar ten parašyta, kad grąžinti nėra ko.

### Nauja

- **Ir „Word", „Excel", „PowerPoint", „OpenDocument" bei tekste galima
  užtamsinti.** Anksčiau ten buvo tik „Keisti pasirinkimą"; juosta buvo
  skirta tik PDF rodiniui, be jokios tam priežasties. Kur juostos
  pavaizduoti negalima – grynam tekste ir „Outlook" žinutėje –, reikšmė
  kaip ir anksčiau pakeičiama žymikliu, ir tai taip pat parašyta
  pranešime.

- **Pažymėjus žymiklį jis grąžinamas.** Teksto vaizde („Word", „Excel",
  „PowerPoint", „OpenDocument", tekstas) dabar pakanka pažymėti žymiklį
  ir paspausti „Keisti pasirinkimą": pradinė reikšmė grįžta. Anksčiau
  langas tam nukreipdavo į radimo skydelį.

- **Kalbėtojai posėdžio protokole atpažįstami net tada, kai jų vardas
  kartu yra ir įprastas žodis.** „Gruber: Die Abnahme erfolgt kommende
  Woche." buvo pakeista, „Bauer: Ich stimme zu." liko – pavardė
  atpažinimui atrodo kaip daiktavardis. Tos pačios formos pastabų
  eilutės lieka nepaliestos: iš „Achtung: Die Anlage ist abzuschalten."
  vardo negaunama.

- **„Naudojate naujausią versiją" buvo sakoma ir tada, kai iš viso
  nebuvo galima patikrinti.** Jei atnaujinimo serveris atmeta užklausą –
  nes iš to paties interneto adreso atėjo per daug užklausų arba nes jis
  pats tuo metu sutrikęs –, programa likdavo stovėti su savo sena
  versija ir tvirtindavo, kad tai naujausia. Būtent taip nutiko rugpjūčio
  17 d. „Mac" kompiuteryje: 0.10.25 liko, nors 0.10.28 jau valandų
  valandas buvo paruošta.

  Dabar langas sako, kas vyksta, nurodo kito patikrinimo laiką – ir
  aiškiai nurodo, kad **nėra aišku**, ar sava versija yra naujausia.

  Dažniausiai priežastis būna ne pačiame kompiuteryje: prie daugelio
  prieigų daug klientų dalijasi tuo pačiu interneto adresu, o serveris
  juos suskaičiuoja kartu. Todėl Maskuro tokiu atveju versijų sąrašo
  ieško **antru keliu** ir naujas versijas dažniausiai vis tiek suranda.
  Jei atsisakymas išlieka, serveris ramybėje paliekamas iki nurodyto
  laiko – net jei mygtukas paspaudžiamas dar kartą; papildomas spaudymas
  tik pratęsia blokavimą.

- **Kiekio nurodymai daugiau nebelaikomi vietovardžiais.** Paslaugų
  sutartyje „Vier-Tage-Woche" dingdavo už vietovės žymiklio – tiesiog
  sutarties dalyko viduryje. Tokie žodžių junginiai iš skaičiaus ir
  brūkšnelio („Drei-Punkte-Plan", „24-Stunden-Dienst") dabar išlieka.
  Adresams tai netaikoma: „Zwei-Brüder-Weg" ir toliau keičiamas.

## 0.10.28-alpha.20260817 – 2026 m. rugpjūčio 17 d.

### Pakeista

- **Licencijos vietos dabar tikrai skaičiuojamos.** Anksčiau nė viena
  darbo vieta niekada nesiregistruodavo licencijos tarnyboje – dešimties
  vietų licencija veikė bet kokiame kompiuterių skaičiuje, ir niekas apie
  tai nesužinodavo. Nauja: kompiuteris, kuris paleidžia programą, užima
  vietą; vieta savaime atsilaisvina po **septynių dienų be paleidimo**,
  todėl sugedęs įrenginys ar išėjęs darbuotojas nieko ilgam neužblokuoja.

  Nedidelis viršijimas tik **rodomas, o ne blokuojamas**: iki dešimt
  procentų virš nupirkto skaičiaus visi toliau dirba – naujas nešiojamasis
  kompiuteris šalia dar prisijungusio seno neturėtų tapti atveju pagalbos
  linijai. Kas prisijungia daugiau, grąžinamas į nemokamą pakopą ir apie
  tai informuojamas; kompiuteriai, kurie buvo pirmi, nieko nepastebi.

- **Nupirkta licencija reguliariai patvirtinama.** Jei tai nepavyksta
  **30 dienų**, tol galioja nemokama pakopa, kol vėl pavyksta. Niekas
  neišjungiama, o likus savaitei iki to nuoroda atsiranda lange. Kai
  tik kompiuteris vėl prisijungia prie interneto, viskas susitvarko
  savaime. Bandomasis laikotarpis ir nemokama pakopa ir toliau apskritai
  nieko nepraneša – kas niekada neperka, niekada ir neskambina.

- **„Atrakinti be interneto" pagaliau veikia.** Atrakinimas anksčiau
  buvo tikrinamas ir išsaugomas, tačiau po to niekas jo nebeskaitydavo –
  jis nieko nekeitė teisėse. Dabar tai yra išeitis kompiuteriams be
  tinklo prieigos: ji galioja **vienerius metus**, po to naujos gaunamos
  su nauju užklausos kodu. Kartą per metus reikia įrenginio su internetu –
  pats kompiuteris lieka nuolat neprijungtas.

- **Atrakinimą dabar galima atlikti ir iš kliento paskyros** – po „Mano
  licencijos" svetainėje. Ten taip pat nurodyta, kokie kompiuteriai
  priskirti jūsų licencijai ir kada jų vietos vėl atsilaisvins; to
  anksčiau niekur nesimatė. Puslapis be prisijungimo lieka visiems, kas
  neturi parduotuvės prieigos – tačiau jis papildomai reikalauja
  užsakymo el. pašto adreso, kad vien licencijos rakto nepakaktų.

- **Ir lange dabar parašyta, kur dėti užklausos kodą.** Popierinis kelias
  sakė „įvesti įrenginyje su interneto ryšiu" ir nenurodė adreso;
  atrakinimo puslapis jau seniai egzistavo, tačiau į jį niekur nebuvo
  nuorodos. Dabar dialoge, vadove ir DUK rodoma
  **maskuro.com/lizenz-freischalten** – ir svetainėje po licencijos raktu.

- **Mygtukas „Atrakinti be interneto …" lieka matomas**, net jei licencija
  šiuo metu negalioja. Anksčiau jis dingdavo kartu su ja – taigi būtent
  tada, kai jo reikia.

- **„Visos vietos užimtos" dabar sako tiesą.** Nuoroda baigdavosi žodžiais
  „Programa veikia toliau nepakitusi"; tai nebeteisinga, jei nebuvo
  paskirta jokia vieta. Dabar ten parašyta, kad kol kas galioja nemokama
  pakopa.

### Nauja

- **Įjungiant mainų srities valymą dabar parašyta, kad reikia
  peržiūrėti.** Pranešimas nuo šiol vartoja tą patį sakinį, kuris stovi ir
  failo rezultate: Maskuro ne visais atvejais atpažįsta visus asmens
  duomenis.

  Čia jis sveria daugiau nei kitur. Faile rezultatą pamatai, prieš jį
  perduodamas toliau. Mainų srityje – ne: nukopijuoji, įklijuoji, ir
  išvalytas tekstas jau stovi laiško lange. Todėl pranešimas aiškiai
  ragina peržiūrėti **įklijuotą** tekstą.

  Jis pasirodo įjungiant, o ne kiekvieno kopijavimo metu: kas rodytųsi
  penkiasdešimt kartų per dieną, po trečio karto niekas nebeskaito.

- **„Kopijuoti visus" po sąrašu – o „Pašalinti visus" pasitraukia.** Naujas
  mygtukas visus baigtus rezultatus vienu kartu perkelia į mainų sritį,
  kad būtų galima prisegti prie laiško ar įklijuoti kitoje programoje.
  Anksčiau tai buvo galima tik per meniu ir ten tik **pažymėtoms**
  eilutėms – kas turėjo omenyje visas, pirma turėjo paspausti Ctrl+A.

  Kartu iš naujo sutvarkyta mygtukų eilutė: kairėje tai, kas kažką prideda,
  dešinėje po tarpo – tai, kas kažką pašalina. „Pašalinti visus" anksčiau
  stovėjo tiesiai šalia „Pridėti …", ir klaidingas paspaudimas kainuodavo
  visą sąrašą. Ta pati taisyklė nuo rugpjūčio 13 d. jau galioja kiekvienoje
  baigtoje eilutėje.

- **Darbo vietos be interneto dabar gauna savo kalbos modelius iš
  vidaus.** Valymas ten visada veikė be ryšio – modelio atsisiuntimas ne,
  o modelis sveria kelis šimtus megabaitų.

  Administravimas failus vieną kartą surenka prijungtame kompiuteryje ir
  patalpina bendroje vietoje, diegimo pakete ar atmintinėje. Vieta
  įrašoma centralizuotai (laukas `modellquelle` faile `vorgaben.json`
  arba aplinkos kintamasis `MASKURO_MODELLQUELLE`). Nuo tada kiekvienas
  atsisiuntimas pirmiausia kreipiasi ten – kalbos modeliai, japonų žodynas
  ir aukšta pakopa – ir kreipiasi į tinklą tik jei failo trūksta.

  Kontrolinės sumos tuo pačiu galioja nepakitusios. Vidinė failų
  bendrinama vieta dažnai lengviau aprašoma nei laida tinkle; ji neturi
  tapti patogesniu keliu pakišti pakeistą modelį.

  Kaip toks fondas sukuriamas ir kaip licencija bei atrakinimas veikia
  be interneto, aprašyta `OFFLINE.md`.

- **„Grąžinti originalą" – rėmelis grąžina tai, kas buvo pašalinta per
  daug.** Taisymo lange yra naujas įrankis: nutempk rėmelį virš vietos,
  ir tekstas vėl stovi taip, kaip buvo originale.

  Tai užpildo spragą, kurią paliko radimo skydelis. Ten pakeitimą buvo
  galima atšaukti tik tada, jei jo žymiklis buvo vienareikšmis – taigi
  ne anoniminant, kur „[NAME]" stovi prie kiekvienos tokios rūšies
  reikšmės, ir apskritai ne užtamsintose vietose, kur žymiklio
  neišlieka. Būtent ten kaupiasi klaidos: „Benutzer", „Inventarnummer",
  „Unterschrift" mielai laikomi vardais.

  Rėmeliui žymiklio nereikia: **vieta** gaunama iš stačiakampio,
  **turinys** – iš originalo failo, to paties, kurį rodo prieš/po
  perjungiklis. Ar anoniminta, ar pseudoniminta – dabar nesvarbu.

  Grąžintas tekstas stovi juodas, ne raudonas: jis vėl yra atviras
  tekstas, o ne žymiklis. Iš radimo sąrašo įrašas dingsta tik tada, kai
  jo žymiklio **niekur** dokumente nebelieka – jei ta pati reikšmė buvo
  pakeista keliose vietose, ji lieka likusioms.

  Puslapyje, kuris buvo paverstas vaizdu, įrankis atsisako ir paaiškina
  kodėl: grąžintas tekstas atsidurtų po puslapio vaizdu ir nebūtų matomas.

### Ištaisyta

- **Suskleidus „Detalės" ir „Rodikliai" ekrane likdavo vaizdo liekanų.**
  Suskleidus dalis turinio pasislinkdavo po apatiniu lango kraštu ir ten
  likdavo virš fono, kol kas nors kitas užpiešdavo viršų.

  Abi sritys turi mažiausią aukštį, kad atidarytos būtų patogaus dydžio.
  Tačiau suskleidimo judesys mažino tik didžiausią aukštį – o žemiau
  savo mažiausio aukščio sritis nesusitraukia. Turinys taigi likdavo
  200 taškų aukščio, kol langas jau susitraukdavo iki 24; skirtumas
  stovėjo po kraštu. Dabar mažiausias aukštis judesio metu pasitraukia
  ir po to grįžta.

- **Langas kartotinai atidarant ir suskleidžiant vis mažėjo.** Atidarant
  jis auga daugiausiai iki 92 % ekrano aukščio; jei vietos mažai, jis
  auga mažiau, nei reikia. Suskleidžiant vis tiek buvo atimamas visas
  dydis. Dabar grąžinama lygiai tiek, kiek kainavo atidarymas.

- **Užtamsintos informacijos likutis galėjo likti matomas.** Gyvenimo
  aprašyme iš „*30.12.1991" rezultate liko įskaitomi simboliai
  „*30.1" – taigi gimimo datos diena ir mėnesio pradžia. Programa tą
  likutį net pastebėjo ir dėl to pavertė puslapį vaizdu; kaip tik tai
  padarė blogiau, nes tada likutis nebebuvo ieškomas tekste, bet ir
  toliau buvo įskaitomas – ir nebebuvo taisomas.

  Priežastis slypėjo tarp dviejų patikrų. Griežtesnioji tikrina, ar
  pašalintos informacijos plote dar stovi kažkas, kas ten neturėtų
  būti; ji savo radinį praneša kaip simbolių aibę, nes keičiant
  poslinkis pasislenka skaitymo tvarka. Atsarginis kelias, kuris tokias
  vietas užtapo prieš paverčiant vaizdu, šią simbolių aibę ieškojo kaip
  tekstą puslapyje – ir jos niekada nerasdavo. Todėl niekas nebūdavo
  užtapyta. Vieta buvo žinoma visą laiką ir dabar perduodama toliau,
  o ne ieškoma iš naujo.

  Paveiktas buvo kiekvienas puslapis, kurio likutį rado tik ši patikra –
  nepriklausomai nuo failo tipo ir kalbos.

- **Skersai paduotame skenavime teksto atpažinimas nieko
  nerasdavo.** Kas lapą deda į įtrauktuvą šonu, gauna failą, kuriame
  raidės stovi pasuktos 90 laipsnių. Iki šiol Maskuro tokiame faile
  **nei vienos** informacijos neperskaitydavo – ir failas po to
  atrodydavo nepastebimai: nieko nerasta, taigi nieko nepranešta, o
  adresas ir toliau stovėjo skaitomas vaizde. Dabar teksto atpažinimas
  puslapį pats ištiesina; patikros vaizde vėl krenta visi duomenys.

  Dvi ribos atvirai įvardytos: lapo, stovinčio **aukštyn kojomis**
  (180 laipsnių), jis vis dar neperskaito, o esant labai prastam
  skenavimui ištiesinimas nepadeda – ten per mažai įskaitoma, kad iš
  viso būtų galima nustatyti padėtį. Kiekvienam vaizdui dėl to reikia
  maždaug penktadaliu daugiau laiko.

### Pakeista

- **„Diegti automatiškai" dabar vadinasi taip, kaip veikia.** Varnelė
  nustatymuose žadėjo daugiau, nei įvykdydavo: ji savaime atsisiunčia
  naują versiją ir paleidžia diegimą – tačiau tai vyksta **matomai** ir
  reikalauja patvirtinimo, „Windows" atveju dar ir su naudotojo
  paskyrų valdymo klausimu. Kas skaitė „automatiškai", tikėjosi
  kompiuterio, kuris per naktį pats atsinaujina, o rytą stovėjo prieš
  diegimo vediklį. Varnelė dabar vadinasi „Atsisiųsti atnaujinimus
  savaime ir paleisti diegimą", su paaiškinimu apačioje, ką tai reiškia.
  Elgesys nepasikeičia – kad Maskuro nepakeičiamas nepastebimai, yra
  sąmoningas sprendimas ir tokiu lieka.

## 0.10.27-alpha.20260817 – 2026 m. rugpjūčio 17 d.

### Nauja

- **Nauja: `--ersetzen` prijungimui prie kanceliarijos programinės įrangos.**
  Rezultatas atsiranda vietoj šaltinio failo, o ne šalia jo. Taip
  kanceliarijos programinės įrangos išsiregistravimas ir įregistravimas
  („Atverti ir redaguoti“ e. byloje) veikia be jokios sąsajos: programinė
  įranga atiduoda failą ir atgauna jį tą pačią vietą užimantį, jau
  išvalytą.

  **Šis jungiklis pažeidžia patį pirmąjį pagrindinį principą**, todėl jis
  yra tik komandinėje eilutėje – ne lange – ir tik tada, kai jį leidžia
  jūsų administravimas (įrašas `ersetzen` numatytųjų reikšmių faile). Be
  leidimo iškvietimas nutrūksta ir pasako kodėl; tyliai sukurti antrą
  failą būtų dar blogesnė klaida, nes tada nepakeistas failas būtų vėl
  įregistruotas.

  Iš pradžių parašomas gretimas failas; tik kai jis baigtas, jis užima
  šaltinio vietą. Nutraukimas ar klaida palieka šaltinį **nepakeistą iki
  paskutinio bito** ir nepalieka jokios nuolaužos. Patikros žurnale
  pakeitimas žymimas kaip atskiras laukas – tikrintojas turi žinoti, kad
  neišvalytos versijos čia nebėra.

- **Žinynas dabar paaiškina „Windows" įspėjimą pirmojo paleidimo metu.**
  Naujas pirmasis skyrius „Windows" įspėja pirmojo paleidimo metu – ką
  daryti“, su dviem paveikslėliais ir trimis žingsniais: „Daugiau
  informacijos“ yra maža nuoroda, ne mygtukas – būtent čia daugiausia žmonių
  ir užstringa –, tada „Vis tiek vykdyti“.

  Tai, kad ten parašyta „Nežinomas leidėjas“, yra visa įspėjimo esmė:
  paketai šiuo metu tiekiami be sertifikato. Manome, kad tai teisingiau
  paaiškinti, o ne nutylėti.

- **Grįžtamasis kelias dabar pastebi, kai tekstas ir susiejimas
  nedera.** Kas įklijuodavo atsakymą į kitą užduotį, iki šiol gaudavo
  svetimus vardus teisingame tekste – jokios klaidos, jokio pranešimo, tik
  neteisybė. Maskuro dabar prisimena, kokius pakaitalus išvis sukūrė
  paskutinis paleidimas, ir praneša apie kiekvieną, kuris tam nepriklauso.
  Jei nė vienas kilęs iš paskutinio paleidimo, nieko neįterpiama, o langas
  pasako kodėl – vietoj to, kad iki šiol buvo spėjama apie pasibaigusį
  terminą.

  **Riba lieka, ir ji taip pat nurodyta žinyne:** pakaitalai
  sunumeruojami kiekvieno paleidimo metu, taigi pirmasis vardas kiekviename
  dokumente vadinasi `[NAME_1]`. Jei svetimame tekste yra tik tokie
  pakaitalai, sumaišymo pastebėti negalima.

- **PDF dabar galima išvesti nespalvotą (juoda–balta).** Varnelė prie
  veikimo režimo kiekvieną puslapį paverčia juodai baltu paveikslėliu – su
  nematomu teksto sluoksniu apačioje, taigi jis lieka skaitomas ir
  ieškomas. Siuntimui per „beA“ ir panašius kanalus su griežtais dydžio
  apribojimais: pagal mūsų matavimo korpusą vidutiniškai **68 % mažiau**
  (komandinė eilutė: `--monochrom`).

  **Kiek tai duoda, priklauso nuo dokumento** – ir tai parašyta prie pat
  varnelės. Nuskaitytas ir vaizdais gausus dokumentas smarkiai susitraukia,
  o lieknas teksto dokumentas be įterptų šriftų gali net padidėti.
  Išbandykite tai su vienu failu, prieš įjungdami visai partijai.

  Kaina: kiekvienas puslapis perskaičiuojamas iš naujo – prie tūkstančio
  puslapių tai užtrunka minutes. Ir iliustracijos praranda viską tarp
  juodos ir baltos; tekstui tai nesvarbu, nuotraukai – ne.

- **Radinių sąrašas taisymo lange dabar skaičiuoja.** Virš sąrašo rašoma
  „5 radiniai“, o filtravus – „1 iš 5 radinių“. Tai skirtumas tarp „aš
  atfiltravau“ ir „jų yra penki, ir aš visus mačiau“ – veiksmas, kuriuo
  patikrinama, ar vardas tikrai buvo pakeistas visur.

- **Patikros žurnale dabar galima ieškoti ir filtruoti.** Vaizdas po
  „Failas → Patikros žurnalas“ iki šiol turėjo tik lentelę ir nieko
  daugiau – per mėnesį su trimis tūkstančiais paleidimų buvo matyti, kad
  daug kas įvyko, bet ne kas.

  Nauji yra **paieškos laukas**, **trys filtrai** (procedūra, rezultatas,
  rūšis) ir **puslapiavimas**, prie jų trys stulpeliai, kurių anksčiau
  nebuvo: **Procedūra** (užtušuota ar pakeista), **pasitikėjimas** ir
  **trukmė**. Virš sąrašo rašoma, kiek dabar matoma ir kiek filtras
  paslepia.

  „Įrašyti kaip CSV …“ dabar išveda **tai, kas matoma** – kas atfiltravo,
  gauna atfiltruotą, o pranešime nurodomas skaičius.

  Brūkšnys prie pasitikėjimo ar trukmės reiškia, kad tai eilutei nieko
  neišmatuota – pavyzdžiui, todėl, kad ji senesnė už šią funkciją. Šios
  reikšmės **nebus** perskaičiuotos atgaline data. Filtro pagal naudotoją
  vis dar nėra; pavienę eilutę paieška vis tiek suranda.

### Pašalinta

- **Skaidrumo pastaba lange „Apie šią programą“ vėl dingo.** Ji buvo
  nuo 0.10.22-beta.1 ir sakė, kad programa sukurta pasitelkus dirbtinį
  intelektą. Niekur to nereikalaujama, o kaip tik duomenų apsaugos
  programoje kai kas ją skaitė kaip teiginį apie veikimo būdą – tarsi
  dokumentai keliautų į kokią nors tinklo paslaugą. Valymas ir toliau
  vyksta išimtinai savame kompiuteryje; tai parašyta ten, kur jai vieta –
  skirtuke „Duomenų apsauga“.

### Ištaisyta

- **Programa iškeisdavo savo paties piktogramą į blogesnę.** Kas
  savarankiškai įtraukdavo kontekstinį meniu iš programos, po to
  užduočių juostoje matydavo kitokį ženklą nei po diegimo – panašų, bet
  su kairiniuotomis, ne centruotomis juostelėmis ir pastebimai grubesnį.
  Už to slypėjo skubus sprendimas: jei programa neranda piktogramos
  šablono, ji nusipiešia pati. Tai buvo skirta atvejui, kai piktogramų
  **visai** nėra; iš tikrųjų taip pat pieštasi ir tada, kai atsiųstosios
  jau seniai buvo – ir jas perrašydavo. Iš diegimo programos įdiegtoje
  versijoje šablono nėra, taigi ten paveikė kiekvieną. Esamos
  piktogramos dabar lieka nepaliestos.

  **Jau paveiktos diegtys pačios teisingos piktogramos neatgauna** – tam
  reikia iš naujo įdiegti.

- **„Objektkennung: OB-4711-22“ buvo laikoma prisijungimo vardu.**
  Vartotojo vardų atpažinimo įrankis tikrino savo antraštes be žodžio
  ribos priešais – taigi griebdavo **kiekvieną** žodį, kuris baigiasi
  viena iš jų: Objektkennung, Fahrzeugkennung, Gerätekennung. Reikšmė po
  jo būdavo pašalinta, nors su prisijungimo vardu ji neturi nieko
  bendra.

  Sudėtiniai žodžiai, kurie tikrai turimi omenyje – „Benutzerkennung“,
  „Anmeldekennung“ –, sąraše nurodyti atskirai ir toliau randami.


- **Anglų, graikų, japonų ir korėjiečių kalbomis šešiolika pakaitalų
  rezultate liko vokiškai.** Kas sąsają buvo nustatęs viena iš šių keturių
  kalbų, naujesnėms duomenų rūšims dokumente gaudavo įrašytas vokiškas
  antraštes – iš slaptažodžio gaudavosi `[ZUGANGSDATEN_1]`, o ne
  `[CREDENTIALS_1]`, iš diagnozės kodo `[DIAGNOSESCHLUESSEL_1]`, o ne
  `[DIAGNOSIS_CODE_1]`. Paveikta buvo: sveikata, diagnozė, medikacija,
  diagnozės ir vaisto kodas, religija, profsąjunga, politinė nuomonė,
  baudžiamoji teisė, prisijungimo duomenys, vartotojo vardas, kortelės
  duomenys, koordinatės, profesija, suma ir požymis.

  Likusiose 44 kalbose šios klaidos niekada nebuvo: jos savo antraštes
  ima iš kalbos failų, kuriuose šios rūšys nuo pat pradžių buvo. Būtent
  šios keturios kalbos dėl kitos priežasties turi savo lenteles – jų
  rašmenys neišgyvena PDF ženklų rinkinio, todėl ten rašomos lotyniškos
  antraštės –, ir šiose lentelėse naujų rūšių tiesiog trūko.

  Tai pastebėta verčiant katalogo puslapį: interneto svetainė
  angliškai skaitantiems žadėjo antraštes, kurių programa nerašė.
  Vienas patikros akmuo dabar visas keturias lenteles patikrina prieš
  visų galimų antraščių sąrašą.

- **Taisyklių langas nebeatsidaro per mažas savo turiniui.** Skirtuke
  „Savi paieškos šablonai“ vedlio paaiškinimo eilutė („Ieškoma: …“) pusiau
  slėpėsi už lauko „Bandomasis tekstas“ – kaip tik už sakinio, pagal kurį
  be reguliariųjų reiškinių žinių patikrinama, ar sava taisyklė ieško
  tinkamo dalyko. Langas turėjo fiksuotą minimalų dydį iš laikų su mažiau
  skirtukų, todėl jį buvo galima susitraukinti mažiau nei tilptų turinys.
  Dabar jis derinasi prie savo turinio ir susitraukia tik tiek, kad
  viskas liktų skaitoma.

- **Vardai lentelių formulėse nebelieka.** Langelis turi daugiau nei
  vieną vietą tekstui, o iki šiol buvo išvalyta tik viena. Jei vardas
  buvo formulėje – `="Frau "&"Sieglinde Ortner"` – arba buvo paskutinis
  suskaičiuotas formulės rezultatas, jis likdavo knygoje nepakeistas,
  nors ta pati asmuo šalia esančiame langelyje jau buvo pakeistas. Kas
  spustelėdavo langelį, matydavo jį redagavimo juostoje.

  Abu atvejai dabar pakeičiami. Liečiama tik tai, kas tarp kabučių:
  langelių nuorodos, funkcijų pavadinimai ir lapų pavadinimai lieka
  nepaliesti, `=SUMME(K2:K6)` toliau skaičiuoja. Kadangi tas pats vardas
  visur gauna tą patį pakaitalą, `=SUMMEWENN(A:A;"Huber";B:B)` toliau
  suranda savo eilutes.

- **Diagramose vardai daugiau nerodomi.** Diagrama saugo savo pačios
  ašių antraščių kopiją – ji vis dar piešia net tada, kai šaltinio
  langeliai seniai tušti. Po stulpeliais toliau matėsi penki asmenų
  vardai, nors lentelė virš jų buvo švari. Galioja lentelėms **ir**
  pristatymams.

- **Pavadinti diapazonai su fiksuotu tekstu išvalomi.** Pavadintas
  diapazonas vietoj langelio nuorodos gali turėti fiksuotą tekstą; jei
  ten buvo vardas, jis likdavo. Paties diapazono **pavadinimas**
  ir toliau lieka – į jį nurodo formulės, o pervadinimas sukeltų nuorodos
  klaidą. Kaip ir su lapo pavadinimu, apie jį pranešama, o ne pakeičiama.

- **Vieną kartą atpažinta gimimo data dingsta visame dokumente.**
  Data pati savaime nieko nereiškia – tik lauko žodis paverčia ją gimimo
  data, ir kaip tik dėl to sąskaitos data lieka ramybėje. Bet jei ta pati
  reikšmė tame pačiame dokumente pasitaikydavo antrą kartą be to žodžio –
  paveikslėlio antraštėje, užpildytame formos lauke –, ji ten likdavo,
  nors kelios eilutės aukščiau „gimęs …“ buvo neabejotinai atpažinta.
  Perkeliama tik tai, kas **šiame** dokumente jau atpažinta kaip gimimo
  data; spėliojama ir toliau niekas.

- **Struktūrizuoti duomenys interneto puslapiuose atskleidžia gimimo
  datą.** JSON-LD bloke paieškos sistemoms data yra po raktu
  `birthDate“ – raktas pasako, kas tai, taip pat kaip kitur stulpelio
  antraštė. Dabar jis taip pat perskaitomas; „Birthday“ ir „Birthdate“
  formose taip pat laikomi lauko žymėjimu.

- **Gimimo data ir personalo numeris dabar randami ir lentelėse.**
  Langelyje yra tik nuoga reikšmė – `14.03.1988`. Ką ji reiškia, sako
  vien stulpelio antraštė, o ji yra daug eilučių aukščiau. „Excel“
  programoje ji jau buvo skaitoma; „LibreOffice“ lentelėse ir CSV
  failuose – ne, ir todėl gimimo data ten likdavo.

  Abi dabar taip pat skaito antraštę – **bet tik jei ji pati yra lauko
  žymėjimas**. Po „Geburtsdatum“ data pašalinama, po „Rechnungsdatum“ ar
  „Lieferdatum“ – ne. Tai sąmoningai atsargus aiškinimas: antraštė kaip
  „Name“ virš bet kokios pastabos jau kartą būtų uždėjusi pakaitalą ant
  sakinio, kuriame apskritai nėra jokio asmens.

### Ištaisyta

- **Išvalytas CSV lieka lentele.** Atpažinimas CSV eilutę skaito kaip
  sakinį, todėl kartais savo radinius nutiesdavo ir per kabliataškį.
  Pakaitalas prarydavo skirtuką, eilutė po to turėdavo vienu stulpeliu
  mažiau, o failo nebebuvo galima atverti kaip lentelės. Radiniai dabar
  baigiasi ties langelio riba, o maskavimo kabutės lieka. Paveikti
  langeliai po to dar kartą perskaitomi atskirai – kitaip likdavo
  neišvalytas kaimyninis langelis, kurį uždengdavo per ilgas radinys.

- **Pastabos pristatymuose.** Pastaba skaidrėje – dažnai kaip tik ten,
  kur parašyta „Prašau prieš posėdį paskambinti p. …“ – likdavo
  nepaliesta, kartu su parašiusiojo vardu. „Excel“ programoje abu jau
  seniai buvo išvalomi; „PowerPoint“ komentaro tekstą ir autorių saugo
  kitaip, ir tai buvo praleista. Paveikia abu formatus: senesnį ir tą,
  kurį „PowerPoint“ rašo nuo 2019 metų – ten taip pat tarnybinį el.
  pašto adresą, susietą su autoriumi. Inicialai, kuriuos „PowerPoint“
  rodo prie debesėlio, taip pat pašalinami.

- **„LibreOffice“ failai: formulė, vartotojo laukas, pastabos
  autorius.** Kas „Excel“ programoje jau buvo išvalyta, ODS lentelėje
  likdavo – ten formulė yra ne atskiras elementas, o langelio savybė, ir
  vardas joje išgyvendavo. Kitą kartą atvėrus „LibreOffice“ jį vėl
  perskaičiuodavo.

  Prie to dar trys vietos: OpenDocument formate **vartotojo lauko**
  reikšmė kartą yra deklaracijos viršuje ir tekste tik iškviečiama –
  iki šiol buvo pakeičiamas tik iškvietimas, todėl atvėrus vėl
  grįždavo senoji reikšmė. **Pastabos autorius** ir sekamo pakeitimo
  autorius likdavo. Ir **lentelėje** pakeitimų sekimas apskritai nebuvo
  išvalomas – kitaip nei teksto dokumente –, taigi ištrinti langelių
  turiniai kartu su redaktoriaus vardu išlikdavo. Langelių nuorodos ir
  sumos formulės tuo metu lieka nepaliestos.

- **Įrašyti interneto puslapiai atskleidžia savo atributus.** Puslapyje
  matyti toli gražu ne viskas, ką jis turi. Užpildytas formos laukas
  įvestį saugo `value` atribute, „JavaScript“ sąsaja savo duomenų rinkinį
  deda į `data-…`, o blokas paieškos sistemoms (JSON-LD) jį pilnai ir
  taisyklingai pakartoja: vardą, gimimo datą, adresą, telefoną. Matomas
  tekstas buvo išvalytas, o visa tai liko.

  Dabar išvalomos ir šios vietos, taip pat `aria-…` (tai, kas
  perskaitoma ekrano skaitytuvui), `placeholder`, `summary` ir siūlomas
  nuorodos failo pavadinimas. JSON-LD blokas tuo metu skaitomas kaip
  duomenys ir lieka teisingas – jo raktai ir žodynas lieka, dingsta tik
  reikšmės. Įprastas „JavaScript“ ir toliau nekeičiamas.

- **Paveikslėliai netenka savo papildomų duomenų ir be EXIF.**
  Nuotrauka šalia savęs neša fotografo vardą, nufotografavimo laiką ir
  vietos GPS koordinates – buto skelbime tai atskleidžia adresą, net jei
  tekste jo nėra. Tai buvo pašalinama, kol paveikslėlis turėjo EXIF. Jei
  duomenys buvo saugomi **tik** kaip XMP (taip saugo „Lightroom“ ir
  „Photoshop“) arba kaip teksto blokas PNG faile (`Author`, `Comment`),
  paveikslėlis likdavo visiškai nepaliestas. Dabar abu atvejai
  atpažįstami ir pašalinami – taip pat paveikslėliuose, kurie yra
  dokumento viduje ir jame lieka. Orientacija ir toliau išlieka, o
  paveikslėlis be papildomų duomenų nesaugomas iš naujo be reikalo.

- **Nuorodų taikiniai lentelėse, pristatymuose ir „Word“ dokumentuose.**
  Kur veda nuoroda, parašyta ne tekste, o atskiroje failo saugykloje.
  El. pašto adresas už „Rašyti laišką“ dėl to išgyvendavo valymą
  nepaliestas, nors ta pati adresas tekste buvo pakeista. `mailto:` ir
  `tel:` dabar taip pat išvalomi, kaip ir įrašytuose interneto
  puslapiuose.

### Nauja

- **Gydytojo laiškai daugiau negrįžta sugadinti.** Iki šiol vardų
  atpažinimas vaistines medžiagas laikydavo asmenų vardais: iš
  „Metoprololsuccinat“ išeidavo `[NAME]`, iš „Ramipril“ – `[ORT]“.
  Gydymo planas po to būdavo netinkamas naudoti – o diagnozės likdavo
  nepaliestos, taigi lygiai priešingai, nei turėtų būti. Išmatuota, kad
  tai paveikė **63 % veikliųjų medžiagų** ir **53 % klinikinių terminų**,
  ir ne tik vokiečių kalboje: per septynias kalbas – 74 %, italų kalboje –
  visos patikrintosios.

  Maskuro dabar žino medicininį žodyną ir jo neliečia. Lieka 6 % vietoj
  43 % (vokiškai) ir 1 % vietoj 74 % (per visas kalbas). Kur priešais
  stovi kreipinys – „Sehr geehrte Frau …“ –, vardas lieka vardu, net jei
  jis atsitiktinai skamba kaip vaistas.

- **Ligas ir vaistus galima pašalinti – jei norite.** Naujas varnelės
  laukelis nustatymuose: „Taip pat pašalinti ligas ir vaistus“
  (komandinė eilutė: `--mit-diagnosen`). Personalo byloms, atleidimams
  ir ekspertizėms, kur diagnozė niekam neturi rūpėti.

  **Numatytoji reikšmė – išjungta**, ir tai sąmoningai: gydytojo
  laiškas *susideda* iš diagnozių ir veikliųjų medžiagų. Kas ką nors
  anonimizuoja – tyrimams, mokymams, DI įrankiui –, dažniausiai nori
  būtent šį turinį išlaikyti ir atsikratyti tik to, apie ką eina
  kalba. Ten diagnozė yra turinys, ne asmens žymuo.

  Atpažinimas suranda įprastus pavadinimus ir nepakeičia peržiūros:
  ligų sąrašas niekada nebus išsamus, nes gydytojas rašo „C2-Abusus“,
  kur klasifikacijoje nurodyta „sutrikimai dėl alkoholio“.

- **Randami diagnozių ir vaistų kodai.** TLK-10 (`I48.2`), ATC
  (`A10BA02`) ir centrinis vaisto numeris yra sveikatos duomenys taip
  pat, kaip ir bet kuri išrašyta diagnozė – išleidimo laiškuose ir
  atsiskaitymo dokumentuose net dažnesnė forma. Jie pagal nutylėjimą
  įjungti, kaip ir kitos ypatingos kategorijos pagal BDAR 9 str.

  Diagnozės kodas atpažįstamas tik su įrodymu: su „ICD“ priešais arba
  skliausteliuose už diagnozės eilutės. Be šios sąlygos programa
  funkcinį klavišą **F10** laikytų priklausomybės diagnoze –
  klasifikacijoje F10 kaip tik tai ir reiškia.

- **Baigtą failą dabar galima nukopijuoti.** Prie kiekvienos baigtos
  eilutės šalia „Peržiūrėti“, „Taisyti“ ir „Rodyti aplanke“ yra
  ketvirtas mygtukas: **Kopijuoti**. Jis įdeda išvalytą failą į
  iškarpinę – iš ten Ctrl+V (Mac: ⌘V) nukelia jį į laišką, pokalbių
  langą ar DI įrankį, aplenkiant aplanko kelią.

  Kopijuojamas **failas**, ne jo tekstas: puslapio maketas, paveikslėliai
  ir užtušavimo juostos taip išlieka. Sąrašo kontekstiniame meniu iš
  karto į iškarpinę patenka ir keli pažymėti rezultatai, o meniu
  „Failas“ tas pats kelias vadinasi **„Kopijuoti rezultatą“** visiems,
  kurie mieliau naudoja klaviatūrą.

- **Šalies pasirinkimas dabar gali sekti dokumentą.** Asmens tapatybės,
  socialinio draudimo ir mokesčių numeriai skiriasi nuo šalies iki
  šalies, o kurios šalys tikrinamos, iki šiol buvo nustatyta visai
  sesijai – kildinama iš sąsajos kalbos. Kas dirba vokiškai ir išvalo
  prancūzišką laišką, tame ieškojo vokiškų mokesčių identifikatorių, o
  ne prancūziško socialinio draudimo numerio.

  Taisyklių lange dabar tam skirta **„Automatiškai pagal dokumento
  kalbą“**. Fiksuotas pasirinkimas lieka šalia, ir tai sąmoningai: kalbos
  atpažinimas nėra neklystantis – jei jis atpažįsta neteisingai, taikoma
  neteisinga šalies parinktis. Kas dirba tik vienos šalies bylomis,
  saugiau elgiasi su fiksuotu sąrašu.

  Tai neturi įtakos **vokiškiems** šablonams (mokesčių ID, valstybinis
  numeris, vidinis numeris): jie priklauso nuo kalbos, ne nuo šalies
  pasirinkimo, ir toliau veikia net tada, kai trumpas vokiškas tekstas
  laikomas angliškas.

- **Slaptažodžiai, raktai ir prisijungimo vardai dabar randami.** Kas
  klaidos pranešimą, žurnalą ar konfigūracijos failo iškarpą įkelia į DI
  langą, beveik visada turi jame prieigos raktą – ir jis iki šiol likdavo
  nepakeistas.

  Atpažįstama abi formos: paplitusios rakto formos, kurios kalba pačios
  už save (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token,
  privataus rakto antraštė), ir pažymėta forma – „Passwort:“, „API-Key
  =“, „Token:“, „Benutzername:“. Pakeičiama tik reikšmė, niekada
  žymė: „Passwort: [ZUGANGSDATEN_1]“ lieka skaitoma, ir kas tikrina
  rezultatą, mato, kad ten buvo slaptažodis.

  Prisijungimo vardas ir slaptažodis yra dvi atskiros rūšys. Kas nori
  pašalinti tik slaptažodžius, vieną išjungia, o kitą palieka.

- **Brūkšniniai ir QR kodai paveikslėliuose padaromi neatpažįstami.**
  Ant nuskaityto sprendimo beveik visada priklijuotas kodas, o jame yra
  bylos numeris – tas pats numeris, kuris šalia esančiame tekste
  pašalinamas. Iki šiol mašininio skaitymo forma likdavo: juosta virš
  numerio nieko nepadeda, jei du centimetrai toliau įrenginys jį per
  sekundę perskaito.

  Atpažįstamas QR kodas, „Data Matrix“, „Aztec“, „Code 128“, EAN ir
  kitos paplitusios formos. Padaryti neatpažįstamu reiškia užpikselinti,
  ir smarkiau nei veidų atveju: kodo klaidų taisymas iš kelių išlikusių
  laukų atkuria stebėtinai daug, pusiau nuslėptas šydas nebūtų
  pašalinimas.

  Ši parinktis stovi šalia „Padaryti veidus neatpažįstamus“ ir taip pat
  **numatytai įjungta**. Net kai parinktis išjungta, ataskaita pasako,
  kiek paveikslėlių turi kodą – veidą matai vartydamas, kodą laikai
  tik dekoru.

- **Kortelės saugos numeris, PIN kodas ir galiojimo data dabar
  randami.** Kredito kortelės numerį programa jau rado; tik su trimis
  greta esančiomis reikšmėmis jis tampa naudingas, o kiekviename
  atsiskaitymo dokumente jie yra vienoje vietoje. Visos trys tik už savo
  žymės: „123“ pati savaime yra namo numeris, puslapio numeris ar
  kiekis.

- **Koordinatės tekste dabar randamos.** Iš paveikslėlių Maskuro
  nufotografavimo vietą jau iki šiol šalindavo; jei ta pati reikšmė
  būdavo tekste ekspertizėje ar įvykio ataskaitoje, ji likdavo. Atpažįsta
  dešimtainius laipsnius ir laipsnių–minučių–sekundžių žymėjimą. Prie
  dešimtainių laipsnių šalia turi būti žodis kaip „Standort“, „Fundort“
  ar „Koordinaten“ – kitaip kiekviena matavimų eilutė su dviem
  skaičiais po kablelio taptų vietos nuoroda.

- **Pinigų sumas dabar galima taip pat pašalinti.** Naujas varnelės
  laukelis „Taip pat pašalinti pinigų sumas“, pagal nutylėjimą
  **išjungta**, kaip ir datos aukščiau: sutartyje suma yra turinys, ir
  kas viską užtušuoja, nieko neapsaugo. Atlyginimo lapelyje, susitarimo
  pasiūlyme ar sąskaitos išraše ji, priešingai, yra kaip tik ta reikšmė,
  kuri apie asmenį pasako daugiau nei šalia esantis vardas – tai žino
  tik tas, kas turi dokumentą prieš akis.

  Suma atpažįstama **tik su valiutos nuoroda**: „4.250,00“ pati savaime
  yra kiekis, tik „4.250,00 EUR“ yra pinigai. Skaičiuojamas valiutos
  simbolis, santrumpa ir pilnas pavadinimas, prieš arba po, taip pat
  rašymo forma „990,– CHF“.

- **Atpažįstamos ypatingos kategorijos pagal BDAR 9 str.** Religinis
  įsitikinimas, priklausymas profsąjungai, politiniai įsitikinimai,
  sveikatos duomenys – ir šalia jų baudžiamosios teisės duomenys pagal
  10 str. Tai duomenys, kurių tvarkymą reglamentas iš esmės
  **draudžia**; todėl jie kaip vienintelė nauja grupė pagal nutylėjimą
  **įjungti**. Kas nori juos palikti, pats nusprendžia.

  Atpažįstama forma, kuria jie praktikoje pasitaiko: formos laukas
  personalo anketoje – „Religionsbekenntnis: röm.-kath.“,
  „Gewerkschaft: ÖGB“, „Grad der Behinderung: 50“, „Vorstrafen: keine“ –
  tiek su dvitaškiu šalia, tiek su žyme virš, kaip pateikia užpildytas
  lapas.

  **Rišlus tekstas priklauso DI lygiui.** „Jis jau metų metus
  aktyviai dalyvauja profsąjungoje“ yra ta pati informacija, ir joks
  paieškos šablonas jos patikimai neranda. DI lygis nuo šios versijos
  aiškiai ieško ir šių kategorijų; kam reikia rišlaus teksto, tas jį
  įjungia.

- **Asmens požymiai ir profesija – duomenys, kurie ir be vardo parodo,
  kas turima omenyje.** Lytis, šeimyninė padėtis, ūgis, akių ir plaukų
  spalva nuo šios versijos pašalinami; profesija, pareigos ir skyrius –
  pageidaujant, per savą varnelę („Taip pat pašalinti profesiją ir
  skyrių“) arba `--mit-berufen`.

  **Kodėl vienas įjungtas, o kitas – ne:** „Pirkimų skyriaus vadovė“
  įmonėje reiškia lygiai vieną asmenį, net jei vardas šalia užtušuotas –
  ekspertizėje ar atleidime tai turi būti pašalinta. Darbuotojų
  apžvalga, priešingai, *susideda* iš pareigų pavadinimų; jei jos būtų
  numatytai šalinamos, grįžtų tuščias lapas. Kuris atvejis galioja, žino
  tik tas, kas turi dokumentą prieš akis. Aukščiau minėti požymiai
  beveik visada pasitaiko tik formos laukuose, yra reti ir niekada
  nesudaro turinio – jie taigi nieko nekainuoja.

- **Patikrinti svetimą failą.** „Failas → Patikrinti failą …“
  perskaito jau užtušuotą dokumentą ir praneša, kas jame dar liko – ir
  **kurioje vietoje**: puslapis ir eilutė, rūšis ir ilgis. Skirta
  atvejui, kai kažkas tikrina kito darbą: bylą iš kanceliarijos,
  pažymą iš įstaigos, savo paties siunčiamą paštą prieš išsiuntimą.

  **Pati reikšmė ataskaitoje nerodoma.** Kas atverčia vietą, ją ir taip
  mato – todėl ataskaitą galima saugoti ir perduoti, nesant pačiai
  asmens duomenų rinkiniui.

  **Ir ataskaita visada pasako, ko ji negalėjo patikrinti.**
  Paveikslėliai neskaitomi; nuskaitytame dokumente be teksto sluoksnio
  „radinių nėra“ reiškia *nepatikrinta*, ne *švaru*. Komandinėje
  eilutėje tai skiria grąžinama reikšmė: `--nachpruefen` grąžina 0, jei
  patikrinta ir švaru, 4 – jei yra radinių, ir 5 – jei nepatikrinama. Taip
  siunčiamą paštą galima automatiškai sulaikyti, o ne tiesiog praleisti.

- **Patikros ataskaita: po vieną lapą kiekvienam valymui.** „Failas →
  Įrašyti patikros ataskaitą …“ – arba `--pruefbericht <aplankas>`
  komandinėje eilutėje – parašo vieno puslapio PDF (arba, pasirinktinai,
  CSV ar tekstą) su duomenimis apie paleidimą, rastas rūšis su skaičiais,
  dviem rodikliais ir patikros žyma. Bylos aplankui ir priežiūrai: patikros
  žurnalas yra patikimas įrodymas, bet niekas nepateikia JSON-Lines
  failo.

  **Nauji du skaičiai**, kurių iki šiol niekur nebuvo matyti: *vidutinis
  pasitikėjimas* – kiek atpažinimas buvo tikras dėl to, ką rado – ir
  *maskavimo koeficientas*, pakeistų simbolių dalis tekste. Abu pateikti
  su savo riba: pasitikėjimas **nieko** nesako apie praleistus dalykus, o
  šalia visada nurodyta, kiek radinių jis apskritai apima; koeficientas
  neskaičiuoja paveikslėlių ir dokumente su daug paveikslėlių pasirodo
  per didelis.

  **Radinių reikšmės lape nenurodomos** – ta pati riba kaip žurnale ir
  paieškoje. Apačioje dvi eilutės, kurios sako ne tą patį: kontrolinė
  suma parodo, kad lapas nepakeistas; žurnalo eilutė – tik veikiant
  žurnalui – nurodo į **pasirašytą** eilutę, kuri patvirtina paleidimą.
  Tik ji įrodo kilmę.

- **„Kiek tai buvo patikima?“ – rodikliai prie rezultato.** Mygtukas
  „Rodikliai“ po rezultatu atskleidžia tai, ko iki šiol niekur nebuvo
  matyti: radinius, žodžius ir simbolius, pasiskirstymą pagal rūšį kaip
  juostinę eilutę, prie to vidutinį pasitikėjimą ir maskavimo
  koeficientą. Tie patys skaičiai kaip patikros ataskaitoje, tik iškart
  ir be spausdinimo.

  **Su savo išlyga toje pačioje srityje:** šalia pasitikėjimo nurodyta,
  kiek radinių jis apima, o žemiau – sakinys, kad jis **nieko** nesako
  apie praleistus dalykus. Procentinis skaičius be šio sakinio skaitomas
  kaip radimo dažnis – o kas jį taip supranta, atsiduria blogesnėje
  padėtyje nei visai be skaičiaus.

  Skaičiuojama tik atskleidus: maskavimo koeficiento vardiklis kiekvienam
  failui kainuoja vieną skaitymą, ir jį neturi apmokėti tas, kas
  skaičių apskritai nežiūri.

- **Kurti savus paieškos šablonus, neparašius nė vieno.** Skirtukas
  „Savi paieškos šablonai“ dabar per tris žingsnius veda per reikalą: *Ko
  ieškote? → Kaip tokia informacija atrodo pas jus? → Pavadinkite ir
  įrašykite.* Įrašote pavyzdį – pavyzdžiui, `KD-004711` –, programa iš jo
  išveda taisyklę ir žodžiais parašo, ko ji ieško. Peržiūra su radinių
  skaitikliu tikrina po kiekvieno klavišo paspaudimo.

  **Reguliarusis reiškinys čia visai nepasitaiko.** Galimybė niekada
  nebuvo problema: savi paieškos šablonai egzistuoja jau seniai, tik
  reikėjo tokio reiškinio kaip `\bKD-\d{6}\b`, o jį kanceliarijoje ar
  personalo skyriuje niekas nerašo. Kas nori tokį parašyti *pats*,
  atsiverčia eksperto režimą.

  **Šablonų katalogas dabar iš naujo surūšiuotas:** trylika kortelių su
  pavadinimu, paaiškinimu ir pavyzdine reikšme, filtruojamos pagal
  kategorijos žymes – finansai, valdžios institucijos, kontaktai,
  personalas, medicina.

  Ir jei išvestasis šablonas apima per daug, programa pati apie tai
  praneša: pavyzdys iš vienų skaitmenų atitinka bet kuriuos metus ir
  bet kokią sumą, o kas negali perskaityti reiškinio, kitaip to
  nepastebėtų.

- **Septynios žymos vietoj penkiasdešimt šešių varnelių.** Naujas
  skirtukas „Kas ieškoma“ sujungia visas atpažįstamas rūšis į septynias
  grupes – asmuo, kontaktas ir vieta, identifikatoriai, finansai,
  technika, ypatingos kategorijos, įmonės ir savi. Viena žyma perjungia
  savo grupę, „Visos įjungtos“ ir „Visos išjungtos“ – visą sąrašą; žemiau
  kiekvieną rūšį vis dar galima pažymėti atskirai.

  **Pagal nutylėjimą viskas įjungta, ir taip lieka.** Kas čia
  išjungiama, apskritai nebeieškoma – tai griežčiausias įsikišimas,
  kurį leidžia taisyklių langas, ir jis veikia kiekvieną dokumentą. Todėl
  po sąrašu visada rašoma, kiek rūšių yra išjungta, o įrašoma tik tai,
  kas išjungta: nauja rūšis taip yra įjungta ir taisyklių faile iš
  užvakar, o ne tyliai iškrenta.

- **Perkelti rėmelį į visus puslapius.** Taisymo lange mygtukas
  **Perkelti į visus puslapius** paima paskutinį nubrėžtą rėmelį ir tą
  pačią vietą užtušuoja kiekviename kitame puslapyje – antraštei,
  poraštei ir bylos numerio laukui. Prie aštuoniasdešimties puslapių
  nuskaitytos bylos tai iš dvidešimties minučių padaro dvi.

  **„Ta pati vieta“ reiškia tą pačią *santykinę* vietą lape.** Iš
  automatinio tiektuvo paimtoje krūvoje reguliariai vienas puslapis būna
  gulsčias, kitas – A3, trečias – pasuktas; absoliučiai perkeltas
  stačiakampis atsidurtų šalia antraštės – ir žmogus matytų juostą ir
  laikytų reikalą tvarkoje.

  **Užtušuojama, ne pakeičiama**, net jei pradinis rėmelis buvo
  pakaitalas: po tuo pačiu stačiakampiu keturiasdešimtame puslapyje yra
  kas kita nei pirmame, o pakaitalas su ta pačia numeracija tvirtintų
  lygybę, kurios nėra.

- **Pastaba ant užtušavimo juostos.** Susipažinimo su byla teisėje
  šalia kiekvieno užtušavimo rašoma, kodėl užtušuota. Naujas laukas
  **Pastaba ant juostos** nustatymuose – arba `--balkenvermerk“ –
  parašo trumpą tekstą ant kiekvienos juostos: „§ 203 StGB“, „BDAR“,
  „konfidencialu“. Institucijos išduodamam dokumentui tai reiškia
  skirtumą: gavėjas mato priežastį, neturėdamas žurnalo, kurio jis vis
  tiek niekada negauna.

  **Numatytoji reikšmė – tuščia**, nes pastaba matoma perduotame
  dokumente ir pati yra informacija – ji gavėjui pasako, kokiu pagrindu
  kas nors sulaikoma. Ji veikia tik **užtušuojant**; kur stovi pakaitalas,
  juostos nėra. Ant per mažos skaitomam tekstui juostos ji nerodoma –
  neįskaitoma pastaba atrodytų kaip klaida.

- **Atrakinimas be interneto ryšio – dabar visas.** Licencijų lange
  „Atrakinti be interneto“ buvo jau seniai: viršuje – reikalavimo kodas
  pasiimti su savimi, apačioje – laukas grįžtančiam atrakinimui. Tik
  jo iki šiol **niekas negalėjo išduoti** – tam skirto įrankio trūko, o
  kodas eidavo į niekur. Tai ištaisyta.

  Institucijoms ir kanceliarijoms su izoliuotais kompiuteriais tai ne
  ypatingas atvejis, o įprastas – ir kaip tik tai grupei labiausiai
  svarbu pažadas „Jūsų dokumentai niekada nepalieka kompiuterio“. Kodas
  apie dokumentus nieko neatskleidžia: jame yra licencijos identifikatorius
  ir kompiuterio maiša, ir daugiau nieko.

- **Gauti iš skenerio.** „Failas → Gauti iš skenerio …“ tiesiogiai
  nuskaito krūvą ir sudeda puslapius į sąrašą – pašto skyriui tai
  skirtumas tarp dviejų darbo žingsnių ir vieno. Automatinis tiektuvas
  ištuštinamas iki paskutinio puslapio; įrenginį, raišką ir spalvą
  parenka jums jau žinomas skenerio sistemos dialogas.

  **Automatiškai nevaloma.** Iš pradžių matote, kas atsiuntė, ir tik po
  to paspaudžiate „Valyti“ kaip ir su bet kuriuo kitu failu – jei
  nuskaitymas iš karto praeitų, prarastumėte galimybę pastebėti kreivai
  paimtą krūvą.

  **Tai galioja tik „Windows“ sistemoje**, ir meniu punktas tai sako ir
  „Mac“ sistemoje: ten jūsų skenerio programinė įranga rašo į aplanką, o
  „Stebėti aplanką …“ išvalo viską, kas ten atsiranda.

### Kita

- **Sąrašas visų surandamų duomenų dabar pridedamas** ir sugeneruojamas
  iš pirminio kodo (`hilfe/GEFUNDENE-ANGABEN.md`): 177 rūšys 35 šalyse,
  23 iš jų su kontrolinio skaičiaus tikrinimu. Jame taip pat parašyta,
  kaip skaičiuota – mes `[NAME]` skaičiuojame vieną kartą, kai kiti vardą,
  antrąjį vardą ir pavardę skaičiuoja kaip tris įrašus.

- **Užtušavimas dabar galimas ir „Word“, „PowerPoint“, „OpenDocument“
  ir HTML formatuose.** Pasirinkimas tarp pakaitalo ir užtušavimo iki
  šiol galiojo tik PDF failams. Dabar gali ir kiti: radinys pašalinamas,
  o jo vietoje atsiranda juoda juosta – pačiame dokumente, ne kaip
  paveikslėlis virš. Kas perduoda failą, perduoda užtušuotą bylą, o ne
  tokią, kurioje užtušuotas tekstas dar slypi apačioje.

  **Sprendžiama atskirai**, dviejuose pasirinkimo laukuose: „PDF
  atveju“ ir „Word, PowerPoint, OpenDocument ir HTML atveju“. To ir
  norima skirtingai – užtušuotas PDF eina į instituciją, ta pati byla
  kaip „Word“ failas keliauja toliau po įmonę ir turi likti skaitoma.
  Komandinėje eilutėje atitinkamai `--pdf-modus“ ir `--office-modus“;
  ankstesnių versijų įrašytas „Užtušuoti“ ir toliau reiškia PDF.

  Lentelėse, grynajame tekste, CSV ir el. laiškuose juosta neįmanoma –
  ten nėra ploto, ant kurio ji galėtų gulėti. Ten toliau įterpiamas
  pakaitalas, ir rezultatas **tai dabar sako**, o ne tyliai daro.

- **Nauja: „Pašalinti“ – radinio vieta tiesiog lieka tuščia.** Trečias
  veikimo režimas šalia pakaitalo ir užtušavimo, ir vienintelis, kuris
  veikia **kiekviename** formate: kad kas nors būtų praleista, ploto
  nereikia. PDF faile nieko nepiešiama, „Word“ ir HTML formatuose vieta
  lieka tuščia, lentelėje – taip pat.

  Jis yra tyliausias iš trijų: kas skaito rezultatą, nemato, kad ten
  kada nors kas nors buvo – net ir reikšmės ilgis nebeišduoda savęs.
  Dokumentui, kurį kažkas turi patikrinti, dažniausiai geresnis pasirinkimas
  vis dėlto lieka pakaitalas.

  Paveikslėliuose nė vienas iš trijų pasirinkimų negalioja: vaizdo
  taškų negalima pakeisti pakaitalu ir negalima praleisti. Tai, ką
  ten randa teksto atpažinimas, kaip ir anksčiau visada užtapoma.

- **Taisymo langas nebedeklaruoja pakeitimų, kurių nėra.** Dešinėje
  prie kiekvienos reikšmės stovėjo pakaitalas – net užtušuotame faile,
  kuriame nė vieno nėra. Paspaudus tokią eilutę nieko nepažymėdavo, o
  „Atšaukti“ eidavo į niekur. Dabar ten rašoma „užtušuota“ arba
  „pašalinta“, o eilučių apskritai negalima atšaukti: teksto nebėra,
  atsiimti nėra ko. Tai galiojo užtušuotiems PDF failams, „Word“ ir
  „OpenDocument“ dokumentams bei visam kam, kas rasta paveikslėliuose.

- **Teksto rodinys dabar rodo juostas kaip juostas.** Užtušuotas
  „Word“ failas taisant atrodė **tuščias**: užtušuotose vietose buvo
  tarpai, tarsi programa tekstą būtų prarijusi. Priežastis buvo
  atvaizdavime, ne rezultate – pačiame dokumente juosta visą laiką
  gulėjo teisingai. Dabar ji rodoma ir vaizde, juoda kaip rezultate,
  „Word“, „PowerPoint“, „OpenDocument“ ir HTML formatuose.

- **„Outlook“ pranešimai (`.msg`) dabar išvalomi.** `.eml“ jau buvo
  seniai – bet vokiškose įmonėse el. paštas dažniausiai yra „Outlook“, o
  ten įrašytas pranešimas vadinasi `.msg`. Taip tankiausias asmens
  duomenų formatas apima ir savo paplitusiausią laikymo formą: temą,
  siuntėją, gavėjų eilutes, pranešimo tekstą, HTML versiją, gavėjų
  sąrašą ir priedus – pastaruosius per esamus kelius ir su tais pačiais
  pakaitalais kaip laiško tekste.

  **`.msg` tą patį tekstą neša kelis kartus**, ir tai yra spąstai:
  kaip paprastas tekstas, kaip HTML **ir** kaip RTF. Kas išvalo tik
  paprastą tekstą, nieko nepadaro – „Outlook“ mieliau rodo RTF. RTF
  versija todėl visai pašalinama, taip pat interneto antraštės su savo
  „Received“ grandine ir dvejetainiai paieškos raktai, kurie vardus ir
  adresus išgyvena bet kokį teksto valymą. Rezultatas ir toliau
  atsidaro „Outlook“ programoje ir rodo tekstą be teksto formatavimo;
  ataskaita tai aiškiai nurodo.

- **Aprašyti taisykles savais žodžiais, o ne rašyti reguliarųjį
  reiškinį.** Taisyklių langas moka daug ir dėl to reikalavo
  reguliariojo reiškinio šablono – vietos, ties kuria daugelis
  sustoja. Dabar užtenka sakinio: „Mūsų bylų numeriai formos 12 C
  345/26 turi likti.“ DI lygis iš to siūlo terminus ir paieškos
  šablonus.

  **Priimama tik tai, ką pažymite – ir pagal nutylėjimą nepažymėta
  nieko.** Prie kiekvieno pasiūlymo yra sakinys, ką jis reiškia, ir jo
  radinių skaičius pavyzdiniame tekste, kurį galite pridėti patys. Kas
  apsaugą **atima**, taip ir pažymėta: „šį terminą visada pašalinti“ ir
  „šio termino niekada nešalinti“ sąraše kitaip atrodytų vienodai.
  Pasiūlymai, kurie tiktų viskam, iš viso nerodomi.

- **Patikros žurnalas dabar sumuoja per visas darbo vietas.** Jei
  įstaiga savo žurnalus per `protokoll_pfad“ laiko bendroje vietoje,
  kiekviena darbo vieta ten rašo savo mėnesio failą – iki šiol duomenų
  apsaugos pareigūnas su trisdešimčia vietų turėjo peržiūrėti trisdešimt
  failų atskirai. Virš sąrašo dabar yra eilutė su mėnesio sumomis, ir
  **ji pavadinimu praneša apie nutrūkusias grandines**: vėlesnis
  pakeitimas pastebimas tik jei kas nors patikrina, o trisdešimtyje failų
  ranka niekas netikrina.

  **Jokio sąrašo pagal asmenį** – net ir šiame rodinyje. Reitingas
  „kas kiek išvalė“ tiktų elgesio ir darbo kontrolei, ir kaip tik tai
  turi reikšmės darbuotojų atstovavimo teisės požiūriu, o ne ketinimai.
  Skaičiuojami paleidimai, failai ir radiniai visai įstaigai.

- **„Pasiūlyti profilį iš dokumento“: paklausti taisyklių vieną kartą
  vietoj peržiūros per keturiasdešimt keturias rūšis.** Taisyklių lange
  yra naujas mygtukas: jis parodo DI lygiui dokumentą, nustato, apie ką
  jis – gydytojo laišką, prašymą įsidarbinti, sutartį, sąskaitą,
  sprendimą – ir siūlo strategijas, kurios jam tinka. Gydytojo laiške,
  pavyzdžiui, datos perstumiamos, o ne pakeičiamos, nes ligos istorijoje
  chronologija yra turinys.

  **Profiliai yra programoje, modelis tik renkasi** – užtušavimo
  taisyklės nepriklauso nuo to, ką kalbos modelis laiko gera idėja.
  Siūlomas kiekvienas punktas atskirai ir su pagrindimu; priimama nieko
  be klausimo, o kas nustatyta jūsų pačių, lieka nepaliesta. Be DI
  lygio lieka saugi numatytoji nuostata: pakaitalas viskam.

- **Nauja strategija „sugalvoti“: patikima klaidinga reikšmė vietoj
  pakaitalo.** „Frau Berger schrieb an Herrn Doppler in Fulda“ vietoj
  „[NAME_1] schrieb an [NAME_2] in [ORT_1]“ – mokymo medžiagoms,
  demonstraciniams pavyzdžiams, testiniams duomenų rinkiniams ir viskam,
  kas vėliau pateikiama DI. Kreipinys, sakinio sandara ir skaitomumas
  išlieka.

  Ta pati reikšmė gauna tą patį klaidingą pakaitalą visuose vieno
  proceso failuose ir kiekviename kompiuteryje su ta pačia taisyklių
  byla – **niekur nesaugant jokio susiejimo** (ta pati mechanika kaip
  „hashen“). El. pašto adresai yra rezervuotose pavyzdinėse srityse,
  telefono numeriai – tam skirtame diapazone, sugalvoti IBAN turi
  teisingai apskaičiuotą kontrolinį skaičių. Galima vardams, vietoms,
  adresams, įmonėms, el. paštui, telefonui ir IBAN; kitoms rūšims
  taisyklė atmetama, o ne lieka neveikianti.

  **Ataskaita aiškiai sako, kad buvo sugalvota.** Taip išvalytas
  dokumentas skaitosi kaip tikras ir tikras nėra – jis netinka kaip
  įrodymas ir neturi būti perduodamas kaip originalas.

- **Priešpriešinis patikrinimas: „Kas lieka atpažįstamas?“** Naujas
  varnelė žymėjimas po DI lygiu **baigtą rezultatą** dar kartą pateikia
  kalbos modeliui ir klausia, kas, nepaisant valymo, vis tiek
  atpažįstamas. Turimas omenyje atvejis, kurio joks atpažinimas
  pasaulyje nesuras, nes ten apskritai nėra jokio vardo: „vienintelė
  akušerė rajone“, „kolega, kuris kovo mėnesį po gaisro atsistatydino“.
  Joks šablonas nesuveikia, o vietoje visi vis tiek žino, apie ką kalbama.

  **Nieko nešalinama.** Vietos ataskaitoje nurodomos su pagrindimo
  sakiniu, o sprendžiama rankiniu būdu – programa, kuri pati iš
  dokumento paima sakinius, nes jai jie atrodo įtartini, valymą paverčia
  perrašymu, ir niekas nematytų, kas dingo. Ne daugiau kaip penkios
  vietos kiekviename faile; ko modelis negali pažodžiui pagrįsti,
  atkrenta. Komandinėje eilutėje: `--restrisiko“ kartu su `--ki“.

- **Kelias atgal iš DI: „Atsakymo grąžinimas“.** Iki šiol buvo pastatyta
  tik pusė ciklo – nukopijuoti tekstą, įklijuoti išvalytą, pateikti DI.
  Atsakymas grįždavo su `[NAME_1]`, ir kas jį galėjo panaudoti, ranka
  vėl įrašydavo tai, ką ranka pašalino. Dabar grįžtamasis kelias yra
  meniu „Programa“: nukopijuoti atsakymą, spustelėti įrašą, tikrieji
  vardai vėl atsiranda.

  Šiam susiejimui skirti duomenys laikomi **tik operatyviojoje
  atmintyje**, visada galioja tik paskutinei išvalytai vietai ir
  baigiasi po valandos; kas išjungia iškarpinės stebėjimą, jų atsikrato
  iškart. Susigrąžinti galima tik tai, kas buvo pakeista – užtušuota,
  maskuota ir sumaišyta (hashuota) yra negrąžinama, ir programa pasako,
  kiek vietų dėl to teko palikti. Valdomos diegtys grįžtamąjį kelią gali
  visai išjungti per numatytąją reikšmę `rueckweg`.

- **Stebėti aplanką: kas įdedama, netrukus atsiranda išvalyta
  išvestyje.** Pašto skyriui, pašto dėžutės komandai ar nuskaitymo
  aplankui – vieną kartą nustatai, po to niekas nebespaudo mygtukų.
  Rasti po „Failas → Stebėti aplanką …“, komandinėje eilutėje per
  `--wache <aplankas>`.

  Originalas lieka, kur buvo; pageidaujant jis nepakeistas persikelia
  į paaplankį „Baigta“, niekas niekada neperrašomas. Failas liečiamas
  tik tada, kai jis pilnai parašytas – dar per tinklą kopijuojamas
  failas kitaip būtų perskaitytas pusiau ir pažymėtas kaip išvalytas.
  Kas nepavyksta, lieka gulėti ir yra pasakoma, o ne be galo kartojama.
  Ir stebėjimas prisimena atliktus darbus be failo pavadinimo: tai, kas
  guli gaunamųjų aplanke, dažnai jau pačiu pavadinimu išduoda, apie ką
  kalbama.

  **Aplanko, esančio ne savo vartotojo profilyje – pavyzdžiui, tinklo
  diske – stebėjimui reikia automatizavimo licencijos.** Aplankas,
  kurį pasiekia keli žmonės, yra paslauga, ne darbo vieta; savo profilyje
  ir bandomojo laikotarpio metu apribojimas negalioja.

### Ištaisyta

- **Nustatymai buvo nukirsti dešinėje.** Langas atsiverdavo fiksuoto
  dydžio, ir jo užteko tik šriftui, su kuriuo buvo kuriama: „Mac“
  sistemoje „Tikrinti dabar“, „Keisti …“ ir šalia esantys nurodymai
  pusiau likdavo už ribų. Dabar jis atsiveria toks platus, kokio reikia
  jo puslapiams – kiekviena kalba ir bet kokiu šrifto dydžiu, ribojant
  tik ekranui.

- **„Tikrinti dabar“ dabar atsako matomai.** Rezultatas rodydavosi
  pagrindinio lango būsenos eilutėje – taigi už nustatymų lango, iš kurio
  buvo klausta. Kas tikrino, nieko nematydavo. Dabar atsakymas ateina
  kaip pranešimas virš nustatymų, o jei yra nauja versija, iškart veda
  prie diegimo. Paleidžiant programą lieka kaip iki šiol – būsenos
  eilutėje, joks langas nepaklaustas neatsiveria.

- **Nukopijuoti failai „Mac“ sistemoje nepasiekdavo iškarpinės.**
  Išvalytų failų padėjimas atgal pranešdavo apie sėkmę ir vis tiek
  nieko naudingo neįdėdavo – įklijavus nieko negaudavosi. Paveikta buvo
  viskas, kas rašo failus į iškarpinę.

- **O iš iškarpinės „Mac“ sistemoje buvo skaitomas tik pirmas
  failas.** Kas „Finder“ programoje nukopijuodavo tris failus ir
  pasirinkdavo „Dabar išvalyti iškarpinę“, du iš jų gaudavo neišvalytus –
  ir apie tai niekas net neprašydavo. Dabar ateina visi.

- **„Patikrinti failą“ dabar priima ir vilktus failus** – taip pat kaip
  pagrindinis langas. Nuvilktas failas pridedamas prie esamo pasirinkimo,
  ne jį pakeičia; tą patį nuvilkus du kartus niekas nesikeičia, o ko
  programa negali perskaityti, tai pasakoma, o ne nutylima.

- **Ir langas sako, kad jis laukia jūsų.** Jis atsiverdavo su tuščiu
  langeliu ir pilku mygtuku „Patikrinti“ – tai atrodo, tarsi nieko
  nėra, ne kaip trūkstama pasirinktis. Dabar rašoma „Failas dar
  nepasirinktas – nuvilkite čia arba apačioje pasirinkite per „Pasirinkti
  failus …“.“

- **Ilgas darbas dabar sako, kad jis vyksta.** „Papildomas modelis
  tikslesniam atpažinimui kraunamas – palaukite …“ likdavo rodomas
  tol, kol vyko skaičiavimas: prie failo su 47 500 žodžių tai reiškė
  aštuoniolika minučių, nors krovimasis baigėsi po devynių sekundžių.
  Kas tai mato, mano, kad programa užstrigo. Dabar po to rašoma
  „Tikslesnis atpažinimas vyksta – ilgesniems tekstams tai gali trukti
  kelias minutes“, o būsenos eilutė skaičiuoja: „Tikslesnis atpažinimas
  (7/312)“. Pranešama iš modelio ciklo – kas 250 žodžių, taigi maždaug
  kas šešias sekundes –, ne kiekvieną teksto bloką: vienas teksto
  blokas gali turėti dvylika tūkstančių žodžių ir trukti minutes.

- **Nutrauktas darbas dabar sako, kad jis nutrauktas.** Kas paspaudė
  „Nutraukti“, po to skaitydavo „0 iš 1 failo(ų) išvalyta.“ – teisingai
  suskaičiuota ir vis dėlto neteisinga informacija. Pranešimas, kuris
  failas buvo paveiktas, tuo pačiu momentu buvo perrašytas skaičiavimo
  pranešimo. Ir failų sąraše toliau rodė „vykdoma …“, nors nieko nebevyko;
  dabar ten rašoma „nutraukta“.

- **Sakinys apie duomenų apsaugą buvo nukirstas.** „… jokio debesies,
  jokio įkėlimo. Daugiau skirtuke „Duomenų apsauga“ – tokiu lango pločiu,
  kokiu programa pasileidžia, jis baigdavosi vidury žodžio. Dabar jis
  užima visą plotį.

- **Licencijų tarnyba galėjo ką nors pranešti, ir niekas
  neišklausė.** Kai baigiasi visos licencijos vietos, licencija
  pasibaigusi, raktas nežinomas arba licencijų valdymas pas tiekėją
  išjungtas, tarnyba būtent tam siunčia priežastį – nuo pat pradžių
  buvo numatyta, kad ją paaiškins **vieną kartą**. Ji niekada nebuvo
  rodoma. Dabar atsiranda pranešimas, kuris pirmiausia pasako, kad
  programa toliau veikia nepakitusi, o tada – apie ką eina kalba.
  Vieną kartą kiekvienai priežasčiai: kas jį uždarė, kasdienės patikros
  metu jo daugiau nemato – tačiau vėl mato, jei priežastis pasikeičia.

- **Parduotuvėje pirktoje daugiavietėje licencijoje rodyta „1
  vieta“.** Parduotuvė paskirsto iš anksto paruoštus raktus ir įsigytą
  vietų skaičių saugo pas save; bet rodomas buvo skaičius iš paties
  rakto, o jis kiekviename atsargos rakte lygus vienai vietai. Kas
  buvo įsigijęs aštuonias vietas, skaitė „1 vieta“ – ir nuo antro
  prisijungusio kompiuterio rodymas tapdavo raudonas kartu su „Kreipkitės
  į savo administraciją“. Dabar galioja skaičius, kurį paskutinį kartą
  pranešė tarnyba; be atsakymo lieka prie rakto, ir mažesnis už įsigytą
  apimtį jis niekada netampa. Tas pats galioja papildomiems pirkimams
  ir pratęsimams: jie keičia vietų skaičių pas tiekėją, o ne jūsų raktą.

- **Po pirkimo rodyta „Licencijuota „Maskuro Privatlizenz““.** Tai ne
  vardas, o žymuo, kurio pagrindu raktai paruošiami iš anksto – jūsų
  vardas ten negali stovėti, nes raktas pasirašomas dar prieš pirkimą.
  Vietoj to, kad jums būtų rodomas svetimas vardas kaip jūsų, dabar
  ten tiesiog rašoma „Privati licencija“ ir vietų skaičius. Licencijoje,
  išduotoje jūsų vardu, jūsų vardas rodomas nepakitęs.

- **Meniu „Pagalba“ buvo parašyta „Pagalba _DUK“.** Ir ženklas tapo
  pabraukimo brūkšneliu, nes „Qt“ jį suprato kaip klavišo žymę. Dabar
  ten rašoma „Pagalba & DUK“.

- **Nustatymų langas likdavo stovėti, kai programa dingdavo į
  piktogramą** – ir netgi tada, kai pagrindinis langas buvo uždarytas.
  Dabar jis dingsta kartu. (Galioja tik šiai versijai; savas langas yra
  naujas.)

- **Atmesta licencijos užklausa dabar pasako, kodėl.** Jei licencijų
  tarnyba atmesdavo užklausą nenurodydama priežasties, licencijos
  lange raudonai rašydavo „Nežinomas atsakymas.“ – sakinys, su kuriuo
  nei jūs, nei pagalba nieko negalite padaryti, ir kuris verčia
  klaidos ieškoti savo rakte. Dabar rašoma, kas iš tikrųjų įvyko: kad
  tarnyba atmetė be pagrindimo, ir į ką kreiptis. Jei licencijų valdymas
  pas tiekėją laikinai išjungtas, tai taip pat įvardijama – kartu su
  nuoroda, kad jūsų raktas dėl to nenukenčia.

- **„Mac“ sistemoje nustatytos kalbos staiga tapdavo laikomos
  trūkstamomis.** Paleidus programa pranešdavo „Nė vienas kalbos
  modelis neįdiegtas“ ir siūlydavo pradinę sąranką, nors kalbos jau
  seniai buvo įkeltos – kas žiūrėdavo į „Dokumentų kalbos“, ten jas
  ir rasdavo. Programa jų ieškojo skirtingoje vietoje priklausomai nuo
  paleidimo būdo: paleista iš aplanko „Programos“, ji jas rasdavo;
  paleista kaip paprastas aplankas, ji ieškojo šalia savęs, kur jokių
  nėra. Nuo dabar „Mac“ sistemoje visada galioja ta pati vieta vartotojo
  profilyje, nepriklausomai nuo to, kaip programa supakuota. Nieko iš
  naujo krauti nereikia.

- **„Kas naujo“ rodė pusę sąrašo.** Langas po atnaujinimo nutrūkdavo
  vidury sakinio, o likę punktai rodydavosi kaip tušti sąrašo
  ženkleliai. Kaltas buvo laužtiniuose skliaustuose esantis pakaitalas –
  pvz., `<datei>.docx` –, kurį rodinys laikė žymėjimu ir nuo kurio
  visa likusi dalis atmetama. Kaip tik saugumo naujienos buvo tuo
  paveiktos. Žinynas tokius pakaitalus rodo teisingai jau seniai; dabar
  tą patį daro ir šis langas.

- **Suspaudimas dviem pirštais dabar priartina taisymo lange.** Jutiklinio
  kilimėlio srityje tai *ta* priartinimo gestas – redaktoriuje jis
  iki šiol nieko nedarė, ir kas norėdavo geriau įsižiūrėti į vietą,
  turėdavo griebtis slankiklio arba Ctrl+pelės ratuko. Puslapis dabar
  iškart seka gestą ir paleidus atgal vėl braižomas aiškiai.

- **Priartinama vietoje, į kurią žiūrima.** Suspaudimas didina apie
  tašką tarp pirštų, Ctrl+pelės ratukas – apie tašką po žymekliu.
  Mygtukai, klavišų kombinacijos ir priartinimo slankiklis išlaiko
  vidurį – jiems nepriskirta jokia vieta, į kurią žiūrima. Anksčiau
  visiems liko fiksuota tik slinkties reikšmė: nuo pritaikyto puslapio
  tai laikė viršutinį kraštą, o viskas žemiau didinant iškeliaudavo iš
  vaizdo.

- **„Prieš/po“ puslapio peržiūroje buvo negyvas mygtukas.** Kol
  puslapio peržiūra buvo įjungta, jį buvo galima paspausti – ir kiekvieną
  kartą pranešdavo, kad originalo atverti negalima. Ten ir nėra ko
  lyginti: puslapio peržiūra yra išvalytos versijos atvaizdas, o
  originalo atitikmens nėra. Mygtukas dabar užrakintas ir, kai užvedus
  pelę, pasako priežastį kartu su išeitimi (teksto rodiniu). Jo
  aprašymas dar ir aiškiai žadėjo, kad palyginimas vyksta „nepriklausomai
  nuo to, ar aktyvus teksto ar puslapio rodinys“ – tai niekada nebuvo
  tiesa.

- **Puslapio peržiūra sukeldavo „LibreOffice“ avariją.** Kai vienu metu
  buvo sukuriamos dvi puslapio peržiūros – pavyzdžiui, „Užtušuoti kaip
  PDF“, kol peržiūra dar skaičiavo –, sistema pranešdavo apie
  „LibreOffice“ avariją, nors puslapiai galiausiai vis tiek atsirasdavo:
  abu darbai naudojo tą pačią „LibreOffice“ darbinę saugyklą, ko ji
  netoleruoja. Dabar ją gauna visada tik vienas darbas; kiti pereina
  prie savos. Jiems reikia kelių sekundžių ilgiau, bet klaidos
  pranešimo daugiau nebūna, ir nė vienas darbas be rezultato nelieka.
  Antras atvaizdavimo užsakymas šalia vykstančio dabar taip pat iš
  karto nepriimamas.

- **„Rodyti originalą“ galėjo užverti programą.** Jei originalo
  nepavykdavo atverti – nes jis perkeltas, pervadintas, apsaugotas
  slaptažodžiu arba atskirame diske –, taisymo langas be įspėjimo
  užsidarydavo, ir atviros darbinės kopijos prapuldavo. Dabar atsiranda
  nurodymas, jungiklis grįžta atgal, o išvalyta versija lieka. Kur
  originalas iš principo netinka – pavyzdžiui, PDF puslapio peržiūroje,
  kilusioje iš „Word“ failo, – jungiklis iš anksto užrakintas ir, užvedus
  pelę, pasako priežastį vietoj to, kad kiekvieną kartą rodytų tą patį
  nurodymą.

- **Klaidų pranešimai niekada nepasiekdavo.** Kas norėjo pranešti apie
  klaidą, gaudavo „Gavėjas atmetė pranešimą“ – ir niekas jo niekada
  nematė. Dvi priežastys, abi kelyje: programa serveriui neprisistatydavo
  ir todėl būdavo atmesta apsaugos nuo masinės prieigos, o adresas
  nurodė antrą pavadinimą, kuriam programa nesekdavo. Abu ištaisyti;
  pranešimas vėl išsiunčiamas. **Tas pats paveikė licencijos
  atrakinimą**: prisijungimas, atsijungimas ir užklausos taip pat
  nepasiekdavo tarnybos – tik ten nepastebimai, nes neatsakyta užklausa
  sąmoningai nieko nekeičia jūsų licencijoje. Ir jei atsisakymas vis
  dėlto lieka nepaaiškinamas, dabar prie jo pridedamas techninis
  numeris, o ne kad kiekviena priežastis atrodytų vienodai.

- **Paspaudimas „Rodyti originalą“ galėjo užverti programą.** Jei
  originalo nepavykdavo atverti – perkelto, pervadinto, atskirame
  tinklo diske, apsaugoto slaptažodžiu ar sugadinto –, taisymo langas
  dingdavo kartu su visomis atvirosiomis darbinėmis kopijomis. Dabar
  jungiklis lieka prie išvalytos versijos, o langelis pasako, kas
  nutiko; techninė priežastis nurodyta detalėse, jei norėtumėte apie
  ją pranešti. Tas pats galioja rezultatui, kurio negalima parodyti:
  langas atsiveria ir tai pasako, o ne dingsta.

- **Klausimas apie avariją pasirodydavo per dažnai – ir sunaikindavo
  pėdsaką, apie kurį klausė.** Jis pasirodydavo ir tada, kai nieko
  neįvyko: pastaba atsiranda, kai bet kur pasitaiko netikėtas sutrikimas,
  net jei programa jį pergyvena ir po to normaliai užsidaro; pastaba
  niekada nebūdavo išvaloma. O kas atsakydavo „Ne“, sunaikindavo
  vienintelius įvykio duomenis – pastaba dingdavo jau rodant
  klausimą. Abu dalykai ištaisyti: tvarkingas užsidarymas pastabą
  pašalina, klausiama tik po tikro nutraukimo, ir žymima tik po
  jūsų atsakymo. Duomenys vis tiek yra klaidų žurnale jūsų pačių
  kompiuteryje – kas nieko nenori siųsti, vis tiek nieko neprarandata.
  Siunčiama, kaip ir anksčiau, tik tai, ką prieš tai pilnai matėte ir
  patys leidote.

- **„Valyti“ galėjo tyliai likti užblokuotas.** Jei kalbos modeliai
  strigdavo besikraudami, mygtukas likdavo išjungtas – be jokio
  paaiškinimo. Paspaudimas nieko nedarydavo, o būsenos eilutėje
  nepakitusiai rašydavo „Kalbos modeliai kraunami …“, net ir po
  dešimt minučių. Priežastis: fono procesų sutrikimai patekdavo į
  vietą, kurios paleidus iš failų tvarkyklės niekas nemato; likdavo
  langas, kuris atrodė paruoštas dirbti, bet į paspaudimą nereaguodavo.
  Dabar tokie sutrikimai patenka į klaidų žurnalą, kalbos modelių
  krovimasis apie savo nesėkmę praneša visais atvejais vietoj to, kad
  tyliai atsisakytų, o jei vis tiek tylu, programa po trijų ketvirčių
  minutės pasako, kad kažkas negerai, su patarimu detalėse. Užrakintas
  mygtukas, užvedus pelę, pasako savo priežastį. Ilgas pirmasis
  krovimasis netraktuojamas kaip tyla: kol pranešama apie pažangą,
  lieka ramu.

- **„Mac“ sistemoje programa nebeberasdavo atnaujinimų – ir sakydavo,
  kad naudojama naujausia versija.** „Mac“ versija neturėjo šaknies
  sertifikatų sąrašo; ji jo ieškojo vietoje, kuri egzistuoja tik
  kompiuteryje, kuriame ji surenkama. Dėl to ji negalėjo su jokiu
  serveriu patikrinti, su kuo kalbasi, ir nutraukdavo kiekvieną ryšį:
  jokių atnaujinimų, jokio licencijos atrakinimo, jokio kalbos modelių
  parsisiuntimo, jokio klaidų pranešimo. Senesnės versijos iš to tyliai
  padarydavo pranešimą „Naudojate naujausią versiją“. Sertifikatai
  dabar yra pačioje programoje; jei ji ten jų neranda, ima sistemos
  sertifikatus, o „Mac“ sistemoje – jei reikia – ir raktinės sertifikatus;
  o jei jų iš viso nėra, ji tai ir pasako, vietoj to, kad tvirtintų
  naujausią versiją. Pati patikra dėl to niekada neišjungiama.

  Šį vieną atnaujinimą „Mac“ naudotojai vis dar turi įdiegti patys:
  versija, kuri nepasiekia serverio, negali ir pati atsinaujinti.

### Pakeista

- **Pagrindinis langas sutvarkytas.** Apačioje buvo šeši vienodo dydžio
  mygtukai vienas šalia kito – „Apie …“, „Instrukcija“ ir „Pagalba & DUK“
  po jais, nors tie patys trys keliai jau stovėjo pagalbos meniu
  virš jų. Jie dabar sujungti į vieną mygtuką „Pagalba“, kuris juos
  atskleidžia; nė vienas nedingsta. Apačioje lieka du keliai, nuo kurių
  iš tikrųjų pradedama: „Valyti“ ir „Užtušuoti ranka …“.

- **Tai, ką programa dabar daro, dabar rodoma fiksuotoje vietoje.**
  Pranešimas („Kalbos modeliai kraunami …“, „(3 / 7) brief.pdf“, „5 iš
  7 failo(ų) išvalyta.“) iki šiol kabojo kaip pilkas tekstas tarp dviejų
  mygtukų eilučių. Dabar jis turi savo sritį su spalvotu tašku priešais:
  pilku, kol niekas nevyksta, mėlynu darbo metu, žaliu po sklandaus
  paleidimo ir geltonu, kai atsirado nurodymų. Taškas nesako nieko, ko
  nesako tekstas šalia – jis tik sako tai greičiau.

- **Nustatymai tapo atskiru langu.** Iki šiol jie buvo pagrindiniame
  lange – dėžutė su keturiais skirtukais, kurią atverdavai per „Daugiau
  nustatymų“, ir kuri po to buvo per maža savo turiniui: joje visada
  stovėjo slinkties juosta, o pasirinkimas tarp anonimizavimo ir
  pseudonimizavimo buvo pusiau nematomas. Mygtukas dabar vadinasi
  „Nustatymai …“ ir atveria langą su šonine juosta; kiekvienas iš
  keturių puslapių telpa pilnai. Pagrindinis langas daugiau nebeatsiveria
  savaime, ir failų sąrašą galima matyti šalia. Pasikeitė tik tai, kur
  nustatymai yra – kokie jie yra ir ką jie daro, liko nepakitę.

- **„Išsamiau“ atsiskleidžia, o ne pašoka.** Langas iki šiol staiga
  augdavo, ir po to reikėdavo ieškoti, kas pasikeitė. Dabar jis persislenka
  ten.

- **Šriftų dydžiai ir tarpai visame lange dabar seka tuo pačiu
  matu.** Antraštės dviejose vietose buvo skirtingo dydžio, o
  lygiavertės eilutės stovėjo skirtingu atstumu viena nuo kitos.
  Matoma tai kaip ramybė, ne kaip pavienis pakeitimas.

- **Anonimizavimas dabar yra numatytoji reikšmė.** Iki šiol pagal
  nutylėjimą buvo pseudonimizavimas: vienodi asmenys gaudavo tą patį
  numerį (`[NAME_1]`, `[NAME_2]`), sąsajos likdavo skaitomos – bet
  teisiškai tai vis tiek liko **asmens duomenimis**. Kas nieko
  nenustato, dabar gauna procedūrą, kuri duomenis pašalina iš BDAR
  taikymo srities: visi vienos rūšies radiniai vadinasi vienodai
  (`[NAME]`). Numeravimas liko pasirinkimu, jis nepakitęs stovi tame
  pačiame lange; esami nustatymai lieka tokie, kokie yra. Komandinėje
  eilutėje `--pseudonymisieren“ (taip pat `--mit-nummerierung“) grąžina
  ankstesnę tvarką.

- **Anonimizuotų pakaitalų nebegalima atšaukti po vieną.** Kas
  anonimizuoja, kiekvienam asmeniui gauna tą patį pakaitalą – ir todėl
  nebėra atskiros vietos, kuri priklausytų konkrečiam vardui. Taisymo
  langas vis tiek siūlydavo „Atšaukti pakeitimą“: paspaudimas būtų
  įrašęs *vieną* iš reikšmių *visose* vietose. Eilutės dabar
  pritemdytos kaip užtušuotos informacijos, paspaudimas pasako
  priežastį, o ranka pridėtas radinys nebegauna numerio, kurio kitur
  dokumente niekur nėra.

  Dėl tos pačios priežasties po anonimizuoto paleidimo daugiau nėra
  „Atsakymo grąžinimo“ – anksčiau tai būtų įrašę svetimą vardą į
  kiekvieno asmens vietą. Kas šio ciklo reikia, renkasi
  „Pseudonimizuoti“; programa dabar tai ir sako, o ne nurodo į
  pasibaigusį susiejimą.

  Komandinėje eilutėje `--zuordnung“ anonimizuojant dabar nutrūksta,
  o ne parašo failą, kuris nėra grįžtamasis susiejimas – lange
  varnelė jau seniai buvo užrakinta. Arba pridėti `--pseudonymisieren“,
  arba praleisti `--zuordnung“; pranešimas tai pasako. Rezultatas
  tokiu atveju iš viso nesukuriamas, kad scenarijus neliktų su puse
  darbo.

- **Atnaujinimo kanalas dabar iš naujo nustatytas į „Stabilus“.** Be
  paties pasirinkimo kanalas iki šiol priklausė nuo to, iš kokios
  versijos kilusi veikianti versija – kas kartą išbandė bandomąją
  versiją, nuo tada nuolat gaudavo pasiūlymus bandomosioms versijoms.
  Kanalo keitimas yra sprendimas ir turi juo likti; todėl numatytoji
  reikšmė yra „Stabilus“. Nustatyti kanalai lieka nepaliesti.

### Patobulinta

- **„Beschwerdevorgang“ (skundo byla) nebelaikoma vietovardžiu.**
  Antraštėje „Aktennotiz – Beschwerdevorgang 12 C 345/26“ programa
  bylą užtušuodavo kartu: kalbos modelis ją laikė vieta, ir tai
  nepriklausomai nuo aplinkos. Įtraukiamas ne pavienis žodis, o
  sudėtinio žodžio **pamatinis žodis** – „vorgang“ ir „notiz“ taip
  apima ir verslo, apskaitos bei mokėjimo bylą ar telefono pastabą. Iš
  trisdešimties patikrintų administracinių terminų anksčiau trys
  sukeldavo klaidingą aliarmą, dabar – nė vienas; randama toliau viskas,
  kas stovi šalia („Beschwerdevorgang: Bernd Meisinger“ praranda vardą,
  bet ne antraštę).

- **Anonimizuojant dabar vėl vedama apskaita – papildomam žingsniui
  ir žurnalui.** Anonimizuojančiame veikimo režime programa iki šiol
  neįsimindavo rastų reikšmių. Dėl to tyliai lieka du dalykai:
  visame dokumente galiojantis nuoseklumo papildomas patikrinimas
  (pavardė, kuri vėliau pasitaiko viena, likdavo nepakeista) ir
  pakeitimų sąrašas patikros žurnale. Kol anonimizavimas buvo retesnis
  pasirinkimas, tai beveik nepasireikšdavo – kaip numatytoji reikšmė
  tai būtų tapę įprastu atveju. Dokumente niekas nesikeičia: pakaitalas
  lieka be numerio.

- **„Kein personenbezogenes Datum“ dabar vadinasi „keine
  personenbezogene Angabe“ (jokios asmens duomenų informacijos).**
  Atsiėmimo dialoge ir veidų įspėjime buvo juridinis terminas *Datum*
  („duomuo“, vienaskaita nuo „Daten“). Jis buvo skaitomas kaip
  kalendorinė data, tuo labiau, kad kitoje vietoje programa siūlo
  „Taip pat pašalinti datas“. Dabar visur rašoma „Angabe“ (informacija),
  taip pat, kaip keturiose priežastyse tame pačiame lange virš jo.

- **Kilmės eilutė liko tik lange „Apie“.** „Made with ♥ in Austria“
  buvo pagrindinio lango apačioje, tarp mygtukų, ir ten atrodė kaip
  dar vienas mygtukas. Ji ir toliau yra lange „Apie“ – ten, kur jos
  ir ieškoma.

- **Dėjimo sritis dabar turi matomą kraštą.** Jos punktyrinis rėmelis
  buvo toks blankus, kad vos matėsi nuo fono – tai buvo nesvarbu, kol
  ta sritis buvo tik plotas. Kai ji tapo mygtuku, kurį galima pasiekti
  Tab klavišu, būtent ta linija yra vienintelis dalykas, rodantis, kad
  tai valdymo elementas; todėl ji pakelta iki normos reikalaujamos
  reikšmės.

## 0.10.22-beta.1 – 2026 m. rugpjūčio 15 d.

### Nauja

- **Jei iškarpinės stebėjimas išjungtas, jis iš tikrųjų išjungtas.**
  Stebėtojas laiko paskutinį turinį atmintyje, kad originalą būtų galima
  padėti atgal – iki šiol taip buvo ir tada, kai stebėjimas buvo išjungtas.
  Dabar išjungiant istorija pamirštama. Tai kainuoja atkūrimo galimybę po
  išjungimo, ir taip ir turi būti: išjungta reiškia išjungta.
- **Klaidų žurnale nebelieka failų kelių.** Jis buvo tik jūsų kompiuteryje ir
  niekada nebuvo siunčiamas savaime – bet jame būdavo keliai grynu tekstu, o
  failo pavadinimas dažnai pasako daugiau nei turinys. Iš
  „…/Scheidung_Mueller_Vergleich.docx“ rašant dabar tampa `<datei>.docx`;
  plėtinys lieka, nes jis svarbus ieškant klaidos priežasties. Tas pats
  galioja pastabai po strigties.
- **Pakaitalų sąrašas dabar perspėja pats savyje.** Tai vienintelis failas,
  kuriame jūsų originalūs duomenys yra grynu tekstu, ir jis guli šalia
  rezultato – kas atiduoda aplanką, atiduoda ir jį. Dabar perspėjimas
  stovi kaip pirma eilutė **pačiame** faile, išvesties srityje nurodomas
  visas kelias, o ne tik failo pavadinimas, o komandinėje eilutėje failas
  apskritai pirmą kartą paminimas: iki šiol ten nebuvo net žinoma, kad jis
  atsirado.
- **Anonimizavimas ar pseudonimizavimas dabar yra pavadintas pasirinkimas.**
  Ten iki šiol stovėjo varnelė „Vienodus vardus vadinti vienodai – DI tada
  vis tiek atpažįsta, kas yra kas“. Ji apibūdino naudą ir nutylėjo pasekmę:
  sunumeruoti pakaitalai (`[NAME_1]`, `[NAME_2]`) yra
  **pseudonimizavimas**, o pseudonimizuoti duomenys lieka asmens duomenimis
  – kas manė taip anonimizavęs, klydo. Dabar abu būdai stovi greta, kiekvienas
  su savo kaina. Numatytasis lieka pseudonimizavimas, nes dokumentui, kuris
  po to dar bus skaitomas ar apdorojamas DI, reikia jo ryšių. Anonimizuojant
  pakaitalų sąrašas užrakintas: jis vėl padarytų rezultatą atsekamą.
  Vadovas ir DUK aiškina skirtumą visomis 18 kalbų; komandinėje eilutėje
  jungiklis dabar vadinasi `--anonymisieren`.
- **Eilutė virš dėjimo srities dabar sako tai, kas iš tikrųjų teisinga.**
  Ji žadėjo „100 % vietinis apdorojimas – be debesijos ir paskyros,
  atitinka BDAR“. Jūsų dokumentams tai tinka, programai – ne tokiu
  bendrumu: ji ieško atnaujinimų, pageidaujant praneša apie klaidas,
  papildomai parsisiunčia modelius ir registruoja įsigytas darbo vietas.
  Dabar ten stovi siauresnis ir pagrįstas teiginys: jūsų dokumentai
  nepalieka kompiuterio.
- **Prie rezultato dabar visada stovi, kad jį reikia patikrinti.** Iki šiol
  Maskuro po sklandaus veikimo pranešdavo „Pašalinta 12 duomenų“ žaliai ir
  daugiau nieko – tai skaitosi kaip garantija, jog viskas rasta. Nuorodos
  atsirasdavo tik tada, kai konkrečiai kas nors negalėjo būti patikrinta
  (paveikslėliai, nežinomi priedai). Dabar po kiekvienu rezultatu aiškiai
  parašyta, kad ne kiekvienu atveju atpažįstami visi asmens duomenys, kad
  patikra – naudotojo reikalas, o trūkstama turi būti papildyta ranka –
  lange, išvesties srityje ir komandinėje eilutėje. Jokio pranešimų lango
  užverti: sakinys stovi ten nuolat. Trumpasis vadovas dabar sako tą patį
  tais pačiais žodžiais.
- **Po atnaujinimo paleidus programą matyti, kas pasikeitė.** Iki šiol
  atnaujinimas vykdavo tyliai ir nuo paprasto paleidimo iš naujo nesiskyrė.
  Dabar vieną kartą pasirodo „Kas naujo“ – ir kas praleido vieną versiją,
  mato ir tarpines. Ne pirmą kartą paleidus programą: tada toliau supažindina
  trumpasis vadovas.
- **Kinų ir japonų kalbos dabar randa vardus.** Iki šiol jos nerasdavo
  **jokio** – ne mažai, o nė vieno. Abiem kalbos modeliams trūko žodžių
  segmentavimo, be kurio sakinys be tarpų laikomas vienu vienintelio žodžiu;
  programa tyliai perjungdavo į daugiakalbį atsarginį modelį. Abi kalbos
  dabar atpažįsta asmenis ir vietoves kaip ir kitos. Japonų žodynas kraunamas
  kartu su kalba ir nėra programoje – vien jis sudarytų apie 200 MB, kuriuos
  kitaip neštųsi kiekvienas.
- **Rumunija pasirenkama kaip šalis.** Iki šiol jos apskritai nebuvo. Taip
  atpažįstami rumuniški adresai („Strada Victoriei 30“), pašto kodai su
  vietove („010061 București“) ir asmens kodas (Cod Numeric Personal) – pastarasis
  tik su teisingu kontroliniu skaitmeniu, kad nebūtų pažymėtas kiekvienas
  trylikaženklis skaičius sąskaitoje. Iki tol rumunų dokumentuose pašto
  kodas likdavo įskaitomas šalia užtušuoto vietovės pavadinimo.
- **„Raštinizuoti puslapį“ redaktoriuje.** Kai teksto iš PDF pašalinti
  nepavyksta – tai pasitaiko su svetimų kūrėjų failais – puslapis dabar
  pageidaujant pakeičiamas jo vaizdu: tekstas taip negrįžtamai dingsta,
  puslapis lieka skaitomas ir surandamas paieška. Įspėjimas, pranešantis
  apie šį atvejį, iškart siūlo šį veiksmą kaip mygtuką; per „Įrankiai →
  Raštinizuoti puslapį“ tai pasiekiama ir savarankiškai. Anuliuoti grąžina
  puslapį atgal.
- **Sąsaja dabar yra ir kroatų, graikų, lietuvių, slovėnų, japonų bei korėjiečių
  kalbomis.** Taip iš viso yra aštuoniolika kalbų. Vadovas,
  DUK ir teisiniai tekstai visomis šešiomis pateikti pilnai. Bendrinami
  išvalytame dokumente ženklinimai tuomet seka sąsają – iš `[NAME_1]`
  tampa `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` arba `[氏名_1]`.
  **Graikų, japonų ir korėjiečių kalbomis ženklinimai stovi lotyniškai** –
  `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. Sąsaja lieka savo raštu; tik tai,
  kas įrašoma į dokumentą, yra lotyniška. Priežastis – PDF simbolių rinkinys:
  ten graikiški ir japoniški ženklinimai anksčiau pasirodydavo kaip
  `[??_1]`, ir taip nebebuvo galima atskirti vardo nuo vietovės.
- **Devynios šalys prisideda, o septynios esamos tampa pilnos.** Naujai
  atpažįstami tapatybės, mokesčių ir socialinio draudimo numeriai kartu su
  adresais **Kroatijai, Slovėnijai, Graikijai, Lietuvai, Šiaurės Makedonijai,
  Rusijai, Ukrainai, Kinijai ir Japonijai**. Esamose šalyse uždarytos
  spragos, kurios svėrė daugiau: **Nyderlandams** ir **Portugalijai** iki
  šiol apskritai nebuvo asmens numerio – nei nyderlandų BSN, nei portugalų
  NIF nebuvo atpažįstami, nors jie stovi praktiškai kiekviename šių šalių
  dokumente. Lenkija gauna mokesčių mokėtojo numerį NIP, Danija, Norvegija
  ir Suomija – savo adresus, Kanada – savo pašto kodą. Taip iš viso
  yra **35 šalys**.

### Pašalinta

- **Linux kol kas nebeturi paketo.** Programos kodas ten veikia, bet trys
  dalykai, kuriuos žada šis vadovas, Linux sistemoje neveikia: automatinis
  paleidimas, visuotiniai spartieji klavišai ir – priklausomai nuo darbo
  aplinkos – piktograma juostoje. Pateikti paketą, kuris gali mažiau nei
  aprašyta, būtų netinkamas kelias. Windows ir macOS tai neliečia.

### Patobulinta

- **Bylos numeriai dabar randami visomis kalbomis.** „Aktenzeichen
  12/2026-AB“ buvo pašalintas, „File reference 12/2026-AB“ arba „Sygnatura
  12/2026-AB“ likdavo nepaliesti: laukų žodžiai, pagal kuriuos Maskuro
  atpažįsta tokį numerį, buvo tik vokiečių kalba. Dabar programa žino
  atitikmenis dvylika kalbų – ir kaip anksčiau, pakeičiamas tik pats
  numeris, o priešais stovintis žymėjimas lieka, kad rezultate būtų
  matyti, kas ten buvo pašalinta.
- **Nenaudojama Maskuro dabar užima maždaug puse gigabaito mažiau.**
  Paleidžiant iki šiol būdavo pakraunamas ir tikslesnio atpažinimo papildomas
  modelis, kad pirmasis valymas nelauktų. Išmatavus tai kainavo 648 MB
  operatyviosios atminties ir sutaupydavo 1,9 sekundės – ir kainavo net
  tada, kai langas tiesiog atidaromas ir vėl uždaromas. Modelis dabar
  pakraunamas pirmą kartą, kai jo prireikia; būsenos eilutė tai praneša.
  Kalbos modelis toliau kraunamas paleidžiant – to iškart reikia iškarpinės
  stebėjimui.
- **Dėjimo sritį dabar galima valdyti ir be pelės.** „Vilkite failus čia“
  buvo sritis, reaguojanti į paspaudimus – klaviatūra iki jos nepasieksi, o
  ekrano skaitytuvas ją skaitydavo kaip rėmelį su tekstu, o ne kaip tai, kas
  ji iš tikrųjų yra. Dabar tai mygtukas: klavišas Tab prie jo šokinėja,
  tarpo ir Enter klavišai atidaro failų pasirinkimą, o kas prie jo atšoko,
  mato tai iš krašto. Per meniu „Failas → Pasirinkti failus“ tai buvo
  galima ir anksčiau, bet tai reikėjo žinoti.
- **Išvalyto failo pavadinimas dabar taip pat perskaitomas balsu.** Failų
  sąraše jis stovi kaip antra, mažesnė eilutė po originalu – bet ji ten
  buvo tik nupiešta, o ekrano skaitytuvas įvardydavo tik originalą. Kaip tik
  ši eilutė sukurta apsaugoti nuo klaidingos minties, kad valymas buvo
  bevaisis, nes aplanke guli nepaliestas originalas. Eilutė dabar
  perskaitoma taip: „rechnung.pdf, rezultatas: rechnung_bereinigt.pdf“.
- **Valdikliai be ženklinimo dabar sako, kam jie skirti.** Piktogramų
  mygtukai failų sąraše, žymėjimo mygtukai lango „Taisyti“ ir visi
  pasirinkimo bei įvesties laukai ekrano skaitytuvui buvo bevardžiai – jie
  būdavo pranešami kaip „mygtukas“ ar „jungtinis laukas“ be jokios nuorodos,
  apie ką jie. Eilutės mygtukai tuo pačiu įvardija ir failą: sąraše su
  dvidešimt įrašų kitaip girdėtum tą patį sakinį dvidešimt kartų.
- **Kas valdo klaviatūra, vėl mato, kur yra.** Mygtukas „Valyti“ ir
  piktogramų mygtukai failų sąraše nuspalvinti, ir dėl to nustojo rodytis
  rėmelis, kurį sistema kitaip dėtų aplink pažymėtą valdiklį – tabuliuojant
  žvilgsnis krisdavo į tuštumą. Abu dabar turi savo rėmelį, kai tik ateina
  jų eilė. Mygtukai dėl to nekeičia savo dydžio.
- **Septynios šrifto spalvos buvo per blankios, abiejuose išvaizdos
  rėžimuose.** Išmatuota pagal įprastą normą (WCAG 2.1), blankios
  nuorodų eilutės, šalutiniai tekstai dėjimo zonoje, vadovo punktai ir
  tamsiajame rėžime papildomai mėlyna bei raudona spalvos buvo žemiau
  4,5:1 ribos – įskaitoma esant geram apšvietimui ir geram regėjimui, kitaip
  ne. Visos pakeltos; atspalvių skalė lieka, tekstai toliau skaitosi kaip
  šalutiniai. Dar trys – spalvos, kuriomis pranešami įspėjimai ir sėkmė –
  ribą laikė vos vos ir buvo pakeltos kartu: kas jų neperskaito, neperskaito
  ir žinios, ar kas nors nepavyko. Matomai pasikeitė tik mygtukas „Valyti“
  tamsiajame rėžime: jis dabar turi tamsų, o ne baltą tekstą, kaip
  Windows 11 akcentiniai mygtukai.
- **Kiekviena failų sąrašo eilutė dabar turi savo kryželį.** Iki šiol reikėjo
  pirmiausia pažymėti eilutę, o tada paspausti „Šalinti“ – du žingsniai
  smulkmenai. Kryželis stovi eilutės dešinėje ir reikalauja vieno
  paspaudimo. Mygtukas „Šalinti“ po juo dėl to atsisakomas; kas nori
  vienu kartu pašalinti kelias eilutes, jas pažymi ir naudoja kontekstinio
  meniu punktą, kuris taip pat pasako, kiek jų yra. „Šalinti visus“ lieka.
  Iš sąrašo visada šalinama tik eilutė – niekada failas diske.
- **Prieš DI patikrą dabar rašoma, ar šis kompiuteris jai tinka.** Iki šiol
  lange stovėjo tik tai, koks modelis didelis. Kas jį įjungdavo silpname
  kompiuteryje, pastebėdavo, kad tai užtrunka labai ilgai, tik su pirmuoju
  dokumentu – po 5,4 GB atsisiuntimo. Dabar langas **iš anksto** nurodo
  operatyviąją atmintį ir laisvą vietą bei paaiškina, ką tai reiškia;
  **po to** išmatuojamas greitis ir įvardijama dydžio, apie kurį kalbama,
  trukmė: „Dešimties puslapių dokumentas šiame kompiuteryje trunka apie
  12 minučių.“ Jei per lėta, programa atkalbėja ir siūlo pakopą vėl
  išjungti – bet nieko neuždraudžia.
- **Greičio matavimas dabar veikia kiekviename kompiuteryje.** Iki šiol jis
  vykdavo tik tada, kai buvo papildomai įrengtas grafinis spartinimas – o
  jis egzistuoja tik Windows sistemoje. Visuose kituose kompiuteriuose
  programa dėl to trukmę vertindavo pagal svetimą kompiuterį, ir kaip tik
  ten, kur veikia lėtai, vertinimas neatitikdavo tikrovės.
- **Turkiški adresai dabar randami ir nuskaitytame dokumente.** Nuskaitytoje
  firminio blanko antraštėje „34710 İstanbul“ likdavo įskaitomas, nors ta
  pati informacija šalimais tekste dingdavo: teksto atpažinimas skaito
  turkišką İ be taško, o šablonas laukė didžiosios raidės. Tas pats galiojo
  „Bağdat Caddesi“.
- **Ispaniški adresai be atskiro gatvės pavadinimo dabar randami.**
  „Gran Vía 5“ likdavo, nes šablonas po gatvės tipo dar tikėjosi vardo
  žodžio – prie „Calle Mayor“ toks yra, prie „Gran Vía“ pats tipas jau yra
  vardas. Tas pats dabar galioja „La Rambla“ ir „Castellana“.
- **Lange „Apie šią programą“ dabar yra skaidrumo pastaba** apie tai, kad
  programa buvo kuriama pasitelkiant dirbtinį intelektą. Ji liečia programos
  kūrimą, ne jos veikimo būdą: valymas toliau vyksta tik nuosavame
  kompiuteryje.
- **„Tvarkyti kalbas“ dabar rodo naudingas kalbas pirmiausia.** Pusei iš
  48 kalbų nėra atskiro kalbos modelio; ten vardus silpnai atpažįsta
  daugiakalbis atsarginis modelis, kai kuriais raštais – visai neatpažįsta.
  Sąraše šalia visos atrodė lygiavertiškai. Numatytasis rodinys dabar rodo
  tik kalbas su savo modeliu – per „Rodoma“ likusias bet kada galima
  parodyti, su sakiniu apie tai, ką jos gali ir ko negali. Niekas
  nedingsta, o kas nusistatė ribotą kalbą, ją ir toliau turi.
- **Klausimas apie trūkstamą kalbą dabar nurodo išeitį.** Kai atpažįstama
  kalba, kuriai dar nieko neįrengta, programa iki šiol siūlydavo tik
  „Pakrauti“ arba „Tęsti be“. Bet atpažinimas gali klysti – trumpuose
  formose ir sąrašuose su mažai rišlaus teksto sprendžia keli žodžiai.
  Lange dabar parašyta, kad galima atšaukti ir teisingą kalbą pasirinkti
  ranka, vietoj „Atpažinti automatiškai“. Tai abejotinu atveju sutaupo
  kelių šimtų megabaitų atsisiuntimą kalbai, kuri visai nereikalinga.
- **Pakaitalų ženklinimai dabar kalba sąsajos kalba.** „[NAME_1]“,
  „[ADRESSE_2]“ ir kt. iki šiol visada būdavo vokiškai, nesvarbu, kokia
  kalba nustatyta ar kokia kalba parašytas dokumentas. Dabar jie seka
  sąsajos kalbą – angliškai reiškia „[NAME_1]“, „[ADDRESS_2]“. Ne
  dokumento kalbą: ji spėjama, kai nustatyta „atpažinti automatiškai“, ir
  kartais klaidinga; sąsajos kalba – niekada.
- **Mažiau papildomų klausimų taisant.** Kur bus išsaugotas rezultatas, dabar
  nuolat rodoma apačioje juostoje („→ vertrag_bereinigt.pdf“, patarime –
  aplankas) – paspaudus ant to pasirenkama kita vieta, iškart neišsaugant.
  Todėl klausimas pirmą kartą saugant nebeliekamas. Klausimas „jau apdorota
  – pradėti iš naujo?“ gali būti įsimintas sesijai, o du pranešimų langai,
  teikę tik vieną informaciją, dabar yra būsenos eilutėje. Liko klausimai,
  saugantys nuo negrįžtamos žalos: neišsaugotas darbas uždarant ir
  įspėjimas apie nepašalintą tekstą.
- **Rezultatas dabar sako, kur pats skenavimas buvo neįskaitomas.**
  Nuskaitytame dokumente įrenginio teksto atpažinimas ne viską perskaito
  teisingai – iš „Solarstraße 9“ tuomet tampa, pavyzdžiui,
  „Solaret^aß« B“. To, kas taip klaidingai perskaityta, jokia patikra
  nebeaptiks: kiekvienam paieškos šablonui tai atrodo kaip raidžių
  makalynė. Programa čia nieko negali pakeisti, bet tokias vietas dabar
  įvardija su puslapio numeriu – dažniausiai ten slypi antspaudai,
  firminės antraštės ar ranka rašyti priedai. Tai nuoroda, ne įspėjimas:
  surinktame dokumente jos nebus.
- **Failų sąrašas dabar rodo, kaip vadinasi rezultatas.** Po failo
  pavadinimu po vykdymo stovi išvalyto failo pavadinimas
  („→ vertrag_bereinigt.pdf“). Iki šiol jis buvo tik žurnale už
  „Detalės“, ir kas žiūrėdavo aplanke, rasdavo nepaliestą originalą.
  Šaltinio pavadinimas lieka – kitaip nebebūtų matyti, iš kurio failo
  rezultatas kilęs.
- **Mygtukai baigtoje eilutėje yra didesni ir aiškesni.** Peržiūrėti,
  Taisyti ir „Rodyti aplanke“ buvo plokščios piktogramos be ploto ir
  pasimesdavo sąraše – nors po vykdymo jie yra vienintelis dalykas, kurį
  dar spaudi.

### Pataisyta

- **Svetima sąsajos kalba tyliai apeidavo savas taisykles dėl užtušavimo,
  maskavimo ir maišos.** Kas buvo nustatęs, kad vardai turi būti tušuojami,
  o ne keičiami, vis tiek juos gaudavo pakeistus – vos tik programa buvo
  naudojama ne vokiečių ar anglų kalba. Nustatymas stovėjo, tik neveikė, o
  rezultate skirtumo nebuvo matyti. Paveiktos buvo devynios iš dvylikos
  sąsajos kalbų.
- **Nustatymas „Ženklinimų kalba“ neveikė už vokiečių ir anglų ribų.**
  „Vokiečių“ ir „Anglų“ buvo galima pasirinkti, bet dokumente vis tiek
  likdavo sąsajos kalba. Dabar veikia visos trys galimybės; numatytasis
  „kaip sąsaja“ toliau duoda tą patį, kas buvo iki šiol.
- **Trumpuose teksto iškarpose vardai likdavo – pavyzdžiui, nukopijuotoje
  laiško citatoje.** Kas valydavo iškarpą per iškarpinę, dažnai gaudavo
  užtušuotą tik el. pašto adresą, o vardą po juo – ne. Lemiama buvo grynas
  eilučių skaičius: nuo šešių eilučių programa iškarpą atpažindavo kaip
  sąrašą ir rasdavo vardus, žemiau šešių – ne, o nukopijuota laiško citata
  turi penkias. Bet kokia papildoma eilutė, tarkim antraštė, apversdavo
  rezultatą. Dabar užtenka keturių eilučių, ir matavime dingsta visi
  patikrinti vardai, o ne trečdalis. Ilgesniems dokumentams ir rišliam
  tekstui tai poveikio neturi.
- **DI patikros grafinis spartinimas iki šiol vėl išsijungdavo, vos tik jis
  būdavo įrengtas.** Po įrengimo programa išmatuoja, ar grafika šiame
  kompiuteryje iš tikrųjų greitesnė nei procesorius – bet šis matavimas
  visada nepavykdavo, apie tai nepranešant, o rezultatas „abu vienodai
  greiti“ nulemdavo procesoriaus naudai. Kas buvo pasikrovęs 65 MB, po to
  gaudavo mažiau nei anksčiau. Matavimas dabar veikia; jei jis nepavyksta,
  daugiau nieko nekeičia.
- **Laiko įvertis kiekviename kompiuteryje skaičiavo pagal svetimą greitį.**
  Jis remiasi tuo pačiu matavimu; kol jis neveikė, galiojo kūrimo
  kompiuterio vertė. „Apie dvi minutes“ lėtame kompiuteryje galėjo reikšti
  pusę valandos.
- **DI pakopa dirba su naujesniu, gerokai geresniu kalbos modeliu**
  (Qwen3.5-9B vietoj Qwen3-4B) ir nebeapsiribota vokiečių bei anglų
  kalbomis, o veikia dvylika kalbų. Matuojant pagal patikros korpusą: tiek
  pat rastų duomenų kaip ir be šios pakopos, bet mažiau nei perpus mažiau
  nereikalingų užtušavimų (75 → 31). Modelis didesnis (5,4 vietoj
  2,4 GB) ir reikalauja apie dvigubai daugiau skaičiavimo laiko; įjungiant
  jis pakraunamas vieną kartą, senasis tuo pačiu pašalinamas.
- **Adresai prancūzų, italų, ispanų, portugalų, lenkų, turkų ir švedų
  kalbomis dabar visiškai pašalinami.** Iki šiol ten dingdavo tik
  gatvės ir vietovės pavadinimas – namo numeris ir pašto kodas likdavo
  įskaitomi („[ORT_1] 28, 28013 [ORT_2]“). Šioms kalboms nebuvo savų
  adresų šablonų; jie dabar papildyti.
- **Graikų ir korėjiečių kalbos iš viso nerasdavo vardų.** Graikų atveju
  priežastis buvo atsarginis modelis – su nuosavu modeliu, kurį dabar
  galima pasikrauti, vardai ir vietovės atpažįstami tvarkingai. Korėjiečių
  atveju priežastis buvo pačioje programoje: ji darė prielaidą, kad vardas
  prasideda didžiąja raide, o Hangul didžiųjų raidžių neturi. Ypač buvo
  paveiktos trumpos vienetos – lentelių langeliai, formų laukai, sąrašo
  įrašai.
- **Kalbos modelis, kurio nepavykdavo pakrauti, nutraukdavo valymą.**
  Vietoj klaidos pranešimo dabar įsijungia daugiakalbis modelis, o
  rezultatas nurodo, kad dirbta su silpnesniu atpažinimu. Šiuo metu
  paveikta kinų ir japonų kalbos, kurių modeliams reikia žodžių skaidymo,
  kuris programai dar nepridėtas.
- **Kalba su nuosavu modeliu buvo laikoma įrengta, vos tik buvo pakrauta
  bet kuri kita.** Kas, pavyzdžiui, įrengdavo turkų kalbą, kartu gaudavo
  daugiakalbį atsarginį modelį – o kinų, japonų, korėjiečių ar graikų
  kalbos po to sąraše rodydavosi su varnele ir „0 MB“, nors jų nuosavo
  modelio nebūdavo. Dėl to jos niekada nebūdavo pakraunamos ir nuolat
  dirbdavo su silpnesniu pakaitalu. Dabar sąrašas rodo tikrąją padėtį kartu
  su pakrovimo dydžiu.
- **Nepavykusi atpažinimo pakopa tylėdavo.** Kai buvo įjungta „Išplėstinis
  atpažinimas“ arba „Maksimalus atpažinimas (DI)“, o modelio paleisti
  nepavykdavo, programa dirbdavo toliau be šios pakopos – nė žodžio apie
  tai. Rezultatas atrodydavo kaip bet kuris kitas, o jungiklis toliau
  stovėdavo ties „įjungta“: taigi pagrindinės pakopos rezultatą laikydavai
  geriausiu, ką galima gauti. Rezultatas dabar tai sako ir nurodo abu
  dalykus – kas nebuvo patikrinta ir kaip modelį pakrauti iš naujo. Šis
  atvejis nėra retas: kai kuriuose kompiuteriuose DI pakopa nepavyksta
  pakrauti, kai trūksta grafinio spartinimo.
- **Klaida kraunant papildomą modelį nutraukdavo visą valymą.** „Išplėstinio
  atpažinimo“ atveju apsaugotas buvo tik modelio vertinimas, ne jo
  įkėlimas – o būtent ten kas nors nutinka blogai, kai failas sugadintas
  ar netinka kompiuteriui. Vietoj klaidos pranešimo dabar gaunamas
  pagrindinės pakopos rezultatas su nuoroda.
- **Kalbos nebepavykdavo pašalinti – taigi ir iš naujo pakrauti.** Kas
  lange „Tvarkyti kalbas“ nuimdavo varnelę ir patvirtindavo pakeitimą,
  perskaitydavo „Vokiečių pašalinta“, bet varnelę matydavo iškart vėl
  atsiradusią. Priežastis buvo perėmimas iš programos aplanko: diegiant
  visiems naudotojams kalbos modeliai guli tik skaitymui skirtame programos
  aplanke, o programa iš ten pasiima trūkstamus, užuot iš naujo pakrovusi
  šimtus megabaitų. Šis perėmimas vykdavo su kiekvienu kreipimusi – ir tą
  pačią akimirką atkopijuodavo ką tik ištrintą kalbą atgal. Dabar tai
  vyksta vienkartinai; papildomai pakrautos kalbos tuo tarpu išlieka. Be to,
  programa po pašalinimo patikrina: kas nepavyko pašalinti, dabar pranešama
  kaip nesėkmė, o ne kaip „pašalinta“.
- **Diegiant visiems naudotojams nepavykdavo padėti papildomai
  pakrautų dalykų.** Kas diegia programą visiems naudotojams, turi ją
  aplanke „Programos“, o ten be administratoriaus teisių nieko rašyti
  negalima. Kalbos modeliams tam jau seniai buvo numatyta alternatyvi
  vieta, kitiems dalykams – ne:
  - **Puslapio peržiūros komponentas** po 290 MB atsisiuntimo būdavo
    išpakuojamas į programos aplanką ir ten nepavykdavo – nenurodant
    priežasties. Dabar jis guli kartu su kalbos modeliais, kur pagal
    sumanymą ir turėjo visada gulėti.
  - **Grafinis spartinimas** negali pasitraukti į šalį: jis keičia
    bibliotekas pačioje programoje. Vietoj to, kad pirma pakrautų, o tada
    tyliai nepavyktų, programa dabar iš anksto sako, kad čia tai neįmanoma
    ir ką tai reiškia – maksimalus atpažinimas veikia toliau, tik per
    procesorių.
  - Kartu pridedama **teksto atpažinimo kalba** nepavykdavo pašalinti: ji
    būdavo iškart atkuriama iš programos aplanko. Ta pati priežastis kaip
    su kalbos modeliais, tas pats sprendimas.
  - Šalinant kalbą galėjo būti ištrinti **svetimos „Tesseract“ diegties**
    kalbos duomenys. Dabar liečiamas tik nuosavas aplankas.
  - Alternatyvi vieta iki šiol galiojo tik „Windows“ sistemoje. „Linux“
    archyvui, keliaujančiam į `/opt`, ta pati bėda neturėjo tos pačios
    išeities.
- **Taisant dingdavo visa eilutė, nors buvo aprėmintas tik vienas žodis.**
  Kas jau išvalytame faile užtušuodavo pakaitalą, prarasdavo eilutę, kurioje
  jis stovėjo: iš „Sehr geehrte Frau Doktor [NAME_1]“ nieko nelikdavo – o
  pranešimas skelbdavo „iš dokumento pašalintas vienas žodis“. Paveiktas
  buvo kiekvienas failas, kuris jau vieną kartą buvo praėjęs per programą –
  taigi kaip tik tas atvejis, dėl kurio taisymo funkcija ir egzistuoja.
  Likęs tekstas dabar lieka, nepakitusioje vietoje.
- **„EMPLOYEES“ virš vardų sąrašo buvo pats užtušuojamas.** Tas pats
  atvejis kaip „MITARBEITER“ 0.10.19 versijoje, tik angliškai – ten jis
  liko. Rašant didžiosiomis raidėmis kalbos modeliui trūksta skiriamojo
  požymio, o antraštė stovi virš vien tikrų vardų. Vardai po ja toliau
  randami. Neįtraukta „staff“: tai užimta pavardė, ir įrašas kartu paimtų
  kiekvieną „John Staff“ – tas pats svarstymas kaip anksčiau su
  „Arbeiter“.
- **Teisinė forma buvo pakeista antrą kartą.** Nuskaitytoje firminio
  blanko antraštėje kalbos modelis „GmbH“, adresą ir pašto kodą perskaitė
  kaip **vieną** vietovę. Adresas ir pašto kodas paskui iškirpo sau savo
  dalis, o liko teisinė forma kaip savarankiškas atitikmuo: rezultate
  stovėjo „[ORT_1] [ORT_2]“, kur turėjo būti „[ORT_1] GmbH“. Įmonės
  pavadinimas toliau keičiamas – lieka tik nuoga priesaga, ir rezultatas
  skaitosi kaip firminis blankas, o ne kaip pratimas su tuščiomis vietomis.
- **Apkarpytas atitikmuo nebūdavo patikrintas iš naujo.** Priežastis ta pati
  kaip aukščiau esančio atvejo, ir ji siekia toliau: filtrai prieš
  spėtus atitikmenis veikdavo su tuo, ką **praneša** atpažinimo įrankiai –
  ne su tuo, kas lieka po persidengimų sprendimo. Kai stipresnis atpažinimo
  įrankis apkerpa ilgą atitikmenį, nuolauža yra kitoks tekstas nei
  vertintas, ir niekas jo dar kartą neapžiūrėdavo. Dabar apžiūri.
- **„Naudojama naujausia versija“ – nors patikrinti apskritai nebuvo
  galima.** Kas kaip atnaujinimo kanalą buvo nustatęs „Peržiūra (beta)“
  ar „Stabili – rekomenduojama“, gaudavo tokią žinią, nors šiuose kanaluose
  iki šiol dar nieko nebuvo pasirodę. Dabar programa taip ir sako – ir
  siūlo nustatymuose pasirinkti kitą kanalą.
- **Uždarius langą kol vyko kėlimas, gijos veikimas nutrūkdavo.** Kas
  paleisdavo Maskuro ir iškart vėl uždarydavo langą, kol dar buvo
  kraunami kalbos modeliai, žurnale gaudavo klaidos pranešimą: kėlimo
  procesas kreipdavosi į langą, kurio jau nebebuvo. Matomų pasekmių nebūdavo,
  bet žurnale stovėdavo strigtis ten, kur kažkas tiesiog buvo greitesnis
  už programą.
- **Rezultatas dabar apžiūrimas, ne tik perskaitomas.** Iki šiol puslapis
  buvo laikomas švariu, jei vertė nebestovėjo tekste. Nuskaitytame dokumente
  tai ne įrodymas – ten matomas tekstas yra vaizdas. Todėl pabaigoje dabar
  apžiūrima, ar plotas rezultate iš tikrųjų užtušuotas; jei ten dar
  matyti šviesus popierius, apie tai aiškiai praneša ataskaita, vietoj
  to, kad pranešti „pakeista“.
- **Pakeista informacija likdavo vaizde.** Jei vertė buvo ant vaizdo –
  nuskaityta firminio blanko antraštė, antspaudas, ištisas nuskaitytas
  puslapis –, ji būdavo pašalinta iš dokumento teksto, bet ir toliau
  **matoma**: tai, ką skaito žmogus, ten yra taškai. Ataskaita vis tiek
  praneša „pakeista“. Dabar plotas vaizde užtušuojamas, kad ir kokia
  strategija būtų nustatyta, o pakaitalas stovi šviesiai ant šio fono –
  negražu, bet sąžininga, o priskyrimas išlieka. Jei vaizdo formato
  redaguoti nepavyksta, rezultatas dabar tai aiškiai sako, vietoj to, kad
  atrodytų tvarkingai.
- **Nuskaitytame dokumente pakaitalas visai nerodomas.** Nuskaityto puslapio
  teksto sluoksnis piešiamas nematomas, ir į jį įterptas pakaitalas tai
  paveldi: nustatytas, bet nematomas. Radimo vietoje po to nieko nelikdavo.
- **Teksto atpažinimas, kuris apskritai negalėjo veikti, būdavo laikomas
  išlaikytu.** Trūkstant kalbos failo ar teksto atpažinimo varikliui
  nutrūkus, ataskaita pranešdavo „Vaizdas(-ai) … buvo patikrinti teksto
  atpažinimu (0 radimo(-ų))“ – taigi patikra, kuri niekada nevyko.
  Nuskaitytame dokumente tai vienintelė galima patikra: sutartis su
  įskaitomu adresu puslapio vaizde tokiu būdu būdavo laikoma tvarkinga.
  Dabar ataskaita sako, kad nieko nepatikrinta, ir kodėl.
- **Kalbos failo buvo ieškoma ne tame aplanke.** Jei nuosavame kalbos
  aplanke gulėjo kitos kalbos nei dokumento, teksto atpažinimo variklis
  gaudavo būtent šį aplanką ir nepavykdavo – nors tinkama kalba gulėjo
  šalia. Dabar ieškoma **kalbos**, ne aplanko.
- **Įspėjimas apie nepašalintą tekstą siūlė tai, ko nėra.** Jis nurodė
  „Tušuoti kaip PDF“ – bet tai sukuria *Office* failų PDF vaizdą ir PDF
  atveju apskritai neprieinama. Kas norėjo pasekti įspėjimu, ieškojo
  veltui. Dabar ten stovi mygtukas, kuris tai atlieka.
- **Redaktoriuje juostos ir pakaitalai atsidurdavo šalia pažymėtos
  vietos.** Paveiktas buvo kiekvienas PDF, kuriame eilutė baigiasi
  brūkšneliu, o žodis tęsiasi kitoje eilutėje – nuskaitytuose dokumentuose
  tai ypač krisdavo į akis, nes sutarčių tekstai rinkti ištisai su
  perkėlimais. Abi eilučių pusės buvo laikomos *vienu* žodžiu, kuris driekiasi
  skersai puslapio, ir kiekvienas rėmelis šalia perimdavo šį plotį.
  Pats atpažinimas dėl to nesikeičia: matavimo korpusas duoda tą patį
  rezultatą kaip anksčiau.
- **Redaktorius įspėdavo, kad tekstas „vis dar dokumente“, nors jis buvo
  pašalintas.** Jei tas pats žodis puslapyje pasitaikydavo kelis kartus –
  sutartyse taisyklė, o ne išimtis –, savikontrolė po kiekvieno pakeitimo
  praneša nesėkmę. Dabar ji skaičiuoja pasikartojimus, o ne tiesiog
  žiūri, ar žodis dar kur nors stovi. Tikros nesėkmės atveju ji įspėja
  kaip anksčiau.
- **Rezultato failas kiekviena kalba vadinosi „_bereinigt“.** Buvo turėta
  omenyje, kad pavadinimo priedas seka sąsajos kalbą – angliškai taip ir
  buvo („_cleaned“), likusiose šešiolikoje kalbų – ne. Kas naudojo
  programą suomių kalba, gaudavo „asiakirja_bereinigt.pdf“. Dabar failas
  vadinasi „asiakirja_puhdistettu.pdf“, japoniškai „書類_除去済み.pdf“
  ir taip toliau – kiekvienu atveju su žodžiu, kurį ta pati sąsaja
  naudoja savo pabaigos pranešime. Kas nustatęs savo priedą, jį ir
  toliau turi.
- **„Tvarkyti kalbas“ visada rašydavosi vokiškai.** 48 dokumento kalbų
  sąraše stovėdavo vokiški pavadinimai, nesvarbu, kokia sąsaja nustatyta:
  suomis naudotojas skaitydavo „Chinesisch“. Dabar ten stovi pavadinimas
  jo kalba, o už jo – savas vardas – „Kiina (中文)“. Savas vardas –
  sąmoningas sprendimas: kas kalbą atpažįsta iš jos paties vardo, ją
  suras ir tada, kai suomiškas žodis jam nieko nesako.

## 0.10.19 – 2026 m. rugpjūčio 12 d.

### Patobulinta

- **Įrašas kontekstiniame meniu dabar kalba jūsų kalba.** Anksčiau ten
  kiekvienoje sistemoje stovėjo vokiškas užrašas – net angliškame
  „Windows". Dabar jis seka nustatytą sąsajos kalbą, ir kas kalbą pakeičia,
  gauna įrašą iš karto pervadintą, be pakartotinio diegimo. (Windows;
  „macOS" ir „Linux" meniu pavadinimas kartu yra ir failo pavadinimas –
  tai vėliau.)
- **Redaktorius įsimena, kuriame rodinyje paskutinį kartą dirbote.** Kas
  naudoja puslapio peržiūrą, kitą dokumentą ją gauna savaime – nereikia
  kiekvieną kartą įjungti iš naujo. Kas ja niekada nesinaudojo, nieko
  nepastebi: ji atkuriama tik tada, kai tam reikalingas komponentas jau
  įkeltas, niekada dėl to niekas papildomai neįkeliama.

### Ištaisyta

- **„MITARBEITER" virš vardų sąrašo pats buvo užtamsintas.** Darbuotojų
  katalogoose ir organizacinėse schemose antraštė dingdavo kaip tariamas
  vardas – ji ten stovi virš vien tikrų vardų, o didžiosiomis raidėmis
  kalbos modeliui trūksta skiriamojo požymio. Vardai po ja ir toliau
  randami.
- **Kiekio nurodymai buvo laikomi adresais.** Sąskaitose, važtaraščiuose
  ir sandėlio sąrašuose dingdavo tokie duomenys kaip „3390 Protokoll",
  „1030 Betrag" ar „3390 Lager" kaip tariamas pašto kodas su vietove –
  keturženklis skaičius atrodo kaip Austrijos pašto kodas. Jei už skaičiaus
  stovi žodis, kurį programa atpažįsta kaip daiktavardį, skyrių, veiklą ar
  lauko pavadinimą, jis dabar išlieka. Tikri vietovardžiai nepaliesti,
  taip pat tokie, kurie kartu yra ir toks žodis („4692 Ort"). Neišspręstas
  tebelieka atvejis, kai už skaičiaus stovi visiškai įprastas žodis
  („3390 Regal") – tam reikia pašto kodų katalogo.
- **Pagalba minėjo meniu punktą, kurio nėra.** Instrukcija, paveikslėlis
  ir pranešimas diegimo pabaigoje kalbėjo apie „Išvalyti dokumentą DI
  reikmėms"; tačiau įrašas kontekstiniame meniu vadinasi „Šalinti asmens
  duomenis". Kas sekė pagalba, ieškojo veltui. Visos trys vietos
  dabar meniu punktą vadina taip, kaip jis iš tikrųjų vadinasi.
- **„Paleisti kartu su sistema" nebuvo galima išjungti.** Kas diegdamas
  pažymėjo „Paleisti kartu su „Windows"", nustatymuose vis tiek matė
  tuščią varnelę – ir dar blogiau: įjungimas bei išjungimas programoje
  neveikė, programa ir toliau startuodavo kartu su „Windows". Priežastis
  buvo dvi vietos, kur „Windows" ieško paleidimo programų; programa žinojo
  tik vieną iš jų. Dabar skaičiuojamos abi, jungiklis rodo tikrąją būseną
  ir veikia abiem kryptimis. Taip pat atsižvelgta: kas išjungia įrašą
  užduočių tvarkytuve, tai dabar mato programoje – o kas jį ten vėl
  įjungia, tuo panaikina išjungimą.
- **Antraštės virš vardų sąrašų buvo užtamsintos.** „TEILNEHMERLISTE
  WERKSTATTGESPRÄCH" arba „MITARBEITERÜBERSICHT INNENDIENST" virš asmenų
  sąrašo dingdavo kaip tariamas vardas. Didžiosiomis raidėmis kalbos
  modeliui trūksta geriausio atpažinimo požymio, o vokiečių kalboje kiekvienas
  daiktavardis rašomas didžiąja raide – „Teilnehmerliste Werkstattgespräch"
  tuomet atrodo kaip „Anna Huber". Junginiai su `-liste`, `-dienst`,
  `-gespräch`, `-sitzung" ir `-besprechung" dabar išlieka. Patys šakniniai
  žodžiai ir toliau laikomi vardu: *Liste* ir *Dienst* yra egzistuojančios
  pavardės, *Teilnehmerliste* – ne.
- **Vertikaliai užrašyti duomenys gaudavo neįskaitomą žymiklį.** Bylos
  numeris puslapio krašte, vykdytojo kodas prie įrišimo krašto, vertikalios
  lentelių antraštės: tokie duomenys būdavo surandami ir pašalinami, tačiau
  žymiklis atsirasdavo skersai per tekstą, suspaustas iki vieno–dviejų taškų
  ir kartais peržengdavo popieriaus kraštą. Dabar jis seka tekstą – vertikaliai,
  skaitomo dydžio ir ta pačia kryptimi, kuria buvo duomenys. Tas pats galiojo
  puslapiams, kurie vėliau buvo pasukti (horizontaliai surašytas tekstas su
  įrašytu puslapio pasukimu, kokį pateikia kai kurios išvedimo programos);
  ir ten žymiklis dabar stovi taip, kaip puslapis matomas žiūrint. „Sehr
  geehrte Frau Doktor Anneliese Berger" duodavo vardu tik „Anneliese" –
  „Berger" likdavo dokumente. Tas pats atsitikdavo kiekvienam vardui su
  antruoju vardu („Frau Anna Maria Berger"). Priežastis buvo taisyklė vardui
  už kreipinio: ji turėjo dvi žodžio vietas, o titulas ar antrasis vardas
  suvartodavo pirmąją. Su „Dr." tai niekada nekrisdavo į akis – taškas
  sulaužo taisyklę, ir kalbos modelis pagaudavo visą vardą. Dabar titulai
  peršokami neužimant vietos, ir vardas gali būti iš trijų dalių. Vaidmuo
  **už** vardo ir toliau neįtraukiamas: „Frau Anna Huber Geschäftsführerin"
  pakeičia vardą, o ne vaidmenį.
