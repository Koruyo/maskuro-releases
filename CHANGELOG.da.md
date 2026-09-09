# Ændringer

Hvad der ændrer sig fra version til version – beskrevet set fra
applikationens side, ikke dens indre. Hvem der vil vide, *hvoraf* den er
bygget, finder det i [LIZENZEN.md](LIZENZEN.md); her står, hvad der ændrer
sig for arbejdet med den.

Nummereringen følger den sædvanlige tælling: Det **første** tal ændrer sig,
når noget ikke længere fungerer som hidtil, det **andet** ved nye
funktioner, det **tredje** ved fejlrettelser.

---

## 0.10.52-alpha.20260903 – 3. september 2026

- En stak med mere end fire filer går ikke længere i stå efter svar i flere
  forhåndsvisningsvinduer. Yderligere dokumenter forberedes fortsat i
  baggrunden; efter et svar færdiggøres den tilhørende fil nu pålideligt,
  og den næste plads i stakken frigives.
- Matchningen af korte firmamærker i PDF'er er nu begrænset til genkendt
  tekst i billeder. I almindelig sidetekst medfører et langt modeltræf over
  flere linjer derfor ikke længere, at et identisk enkeltord et andet sted
  også maskeres.

## 0.10.51-alpha.20260903 – 3. september 2026

- Ændringslisten vises nu på brugerens eget sprog – på
  maskuro.com/neuigkeiten og i programmet under »Ændringer« samt i »Nyheder«
  efter en opdatering. Indtil nu stod der tysk tekst under en oversat
  overskrift i alle atten sprogversioner. Hvis en oversættelse endnu mangler,
  bliver den pågældende version stående på tysk i stedet for at forsvinde;
  listen over versioner er den samme overalt.

## 0.10.50-alpha.20260903 – 3. september 2026

- Tilbagevendende firmamærker i PDF'er bliver nu renset konsekvent, også
  når teksgenkendelsen læser skriften anderledes på en side eller helt
  udelader det runde signet. Et udtrykkeligt fravalg i forhåndsvisningen
  forbliver bindende og kan ikke ophæves af nogen senere gennemgang.
- Valutaløse priser i scannede tabeller sortsløres nu fuldstændigt, også
  når tabelhoved og værdier ligger i forskellige, overlappende PDF-billeder.
  Mængder, timer, vægt og procenter bliver stående; tal med stor
  indbyrdes afstand bliver ikke længere fejlagtigt slået sammen til et
  beløb.
- Underskriftssøgningen finder nu også belagte, svage blå skrifttræk og
  smalle røde signaturforkortelser. Punkterede diagrammer, målekurver,
  stempler, logoer og brede røde redigeringsmarkeringer er fortsat
  undtaget fra denne snævre gennemgang.
- Sortsløringer i drejede, spejlvendte, forskudte eller beskårne
  PDF-billeder rammer nu det virkelige billedpolygon. Tekniske roller i
  leverancepositioner, køretøjs- og dæksagsværdier samt teknisk
  „kompensation" afgrænses samtidig snævrere mod falske fund;
  udtrykkeligt betegnede kontaktroller og telefonnumre forbliver beskyttet.
- Synskontrollen før lagring af en PDF får ikke længere vinduet til at
  fryse: Ved store dokumenter med mange fund stod det hidtil flere sekunder
  uden tilbagemelding; nu vises en meddelelse om, at der kontrolleres,
  og vinduet tegner videre.
- Genfindingen af en værdi fra et billede i redigeringsværktøjet læser
  nu hvert originalbillede kun én gang via teksgenkendelse; hidtil kørte
  den ved hver yderligere tilbagetagning på ny for de samme billeder.
- Genindlæsningen af det udvidede niveau og underskriftsmodellen kræver
  næsten ingen arbejdshukommelse længere: 596 MB-pakken blev hidtil holdt
  helt i hukommelsen, kontrolleret og udpakket der – over et gigabyte i
  spidsbelastning i det kørende program, på maskiner med 8 GB det øjeblik,
  hvor alt begyndte at gå i stå. Nu strømmer den blokvis til disken og
  kontrolleres og udpakkes der.
- Søgningen i redigeringsværktøjet får ikke længere store PDF'er til at
  fryse: Det første bogstav i søgefeltet indlæste hidtil alle sider på én
  gang – ved 200 sider stod vinduet i to sekunder, og efter hver
  sortsløring endnu en gang. Siderne læses nu i portioner; indtil da står
  „Indlæses …" i tælleren, resultatet er det samme.
- Rastrerede PDF-sider – efter en tekstgenkendelse eller når en tekst
  ikke kunne fjernes helt rent – gemmes nu betydeligt mindre og uden
  billedtab: I stedet for altid at blive gemt som JPEG kodes hver side
  også tabsfrit, og den mindste udgave kommer med i filen. En renset
  scanning krymper således fra 248 til 48 KB, øvelsesdokumentet med
  tekstgenkendelse fra 913 til 702 KB; teksten forbliver knivskarp.
- Genindlæste modeller (udvidet niveau, underskrifter, ansigter, sekundær
  tekstgenkendelse) frigives nu fra arbejdshukommelsen igen efter ti
  minutter uden en rensning. Hidtil forblev de indlæst til programmet
  lukkede – den, der én gang havde brugt en underskriftssøgning og det
  udvidede niveau, holdt varigt over to gigabyte. Det næste kørsel
  indlæser dem igen på ét til to sekunder; statuslinjen melder det.
- PowerPoint: Slidelayouts og slidemastres generiske navne („Tom",
  „Titeldias") erstattes ikke længere som en angivelse. „Tom" er også et
  stednavn og blev fejlagtigt sortsløret i hver tysk og engelsk
  præsentation; nu renses kun de manuelt tildelte navne på selve
  diassene.
- I PDF'er trækker linjeudjævningen ikke længere overskriften fra næste
  linje ind i et fund: Nummeret på næste listepunkt efter en dato gjaldt
  som telefonnummer, en felthoved som „Kenncode" eller „Auftragsnummer"
  efter et tal som postnummer med by, og bynavnet under adressen
  fordoblede byen. Det korrekte, kortere fund blev derved fortrængt. Over
  132 korpus-PDF'er er de to ægte fund tilbage af 24 ekstra
  udjævningsfund; i praksiskorpuset falder falske alarmer fra 29 til 21
  ved samme fundfrekvens.
- „Gennemsøg og sortslør PDF-mappe" i redigeringsværktøjet blokerer ikke
  længere vinduet: Kørslen arbejder i baggrunden, fremdriften og
  afbrydelsesknappen reagerer, og menuer eller faneblade kan ikke længere
  betjenes midt i en halvfærdig fil.
- Scannede sider med fund genskrives nu kun én gang ved sortsløring i
  stedet for to: Hidtil fyldte programmet fundkasserne og
  begrundelseskasserne i to omgange, og den anden omgang komprimerede det
  netop nygemte scanbillede endnu en gang. Det sparer tid på store
  scanninger og en kvalitetsforringelse af billedet.
- Bladring, zoom og miniaturer i redigeringsværktøjet reagerer hurtigere:
  Hver gengivet side gik hidtil gennem en PNG-komprimering og tilbage
  igen, kun for at blive vist – på skærme med høj opløsning omkring et
  tiendedel sekund pr. side. Billedet kommer nu direkte frem, billedpunkt
  for billedpunkt det samme.
- Synskontrollen før lagring af en PDF („udgaveprøve") er cirka tre gange
  hurtigere, med samme resultat.
- Hovedvinduet står endnu en gang cirka et kvart sekund hurtigere:
  Kontrollen af, om teksgenkendelsen er klar på denne maskine, kørte
  under vinduesopbygningen – på Mac endda med en prøveforespørgsel til
  systemgenkendelsen – og indstillingssiden for tillægskomponenter
  hentede dertil status for alle 48 sprog. Begge dele sker nu i
  baggrunden henholdsvis først, når sproglisten faktisk åbnes; indtil da
  står „Teksgenkendelse kontrolleres …".
- Efter en underskriftssøgning bruger programmet cirka 300 MB mindre
  arbejdshukommelse: Genkendelsesmodellen lå hidtil dobbelt i hukommelsen
  – én gang til kontrol af dens ægthed, én gang til beregning. Den
  kontrolleres fortsat, blot uden den anden kopi.
- Teksgenkendelsen i PDF'er er blevet mærkbart hurtigere: For hvert
  felthoved på en side („Fødselsdato:", „Skatte-ID:") blev der hidtil
  sendt en separat prøve gennem genkendelsen pr. angivelsestype – på
  hver side igen, selv når samme hoved allerede stod ti sider tidligere.
  Svaret huskes nu; en to-siders leveringsspecifikation stillede således
  324 spørgsmål, nu kun de forskellige. Fundene er de samme.
- Store tabeller renses igen på sekunder i stedet for minutter: I den
  anonymiserende drift – standarden – blev sammenligningen af allerede
  kendte værdier langsommere med hver yderligere celle, fordi en
  mellemlager blev kasseret og genopbygget ved hvert fund. 5.000 celler
  krævede dertil cirka 18 sekunder, nu et halvt; resultatet er tegn for
  tegn det samme.
- Hovedvinduet fremkommer endnu en gang markant hurtigere: Landelisten i
  indstillingerne trak hele genkendelsesbiblioteket frem under
  vinduesopbygningen – cirka 0,7 sekund på Mac, tilsvarende mere på
  Windows –, selvom kun landenavnene er nødvendige dertil. Listen kommer
  nu fra et letvægtskatalog; biblioteket indlæses som tiltænkt i
  baggrunden, mens vinduet allerede står. Det gælder også efter hvert
  sprog- eller udseendeskift, som genstarter programmet.
- Dokumentlaboratoriet fører nu beskårne felthoveder, lokale værdiskygger
  og kraftige scanbeskæringer helt igennem PDF-, DOCX- og
  ODT-beholdere. Matricen omfatter 680 filer fra 40 dokumentfamilier og
  17 beholderakser. Maskuro fjerner i de nye samt de fuldstændige
  grund- og egenskabsprofiler alle forventede angivelser, uden målt falsk
  alarm, beskadiget bevaringsværdi eller afbrydelse.

- Flergangsbrugte scanninger kontrolleres og renses nu over hver synlig
  placering: Dokumentlaboratoriet deler det samme billedobjekt over
  forskellige sider, størrelser og drejningslejer i PDF og refererer til
  den samme billeddel flere gange i DOCX og ODT. Tekniske ODT-rammenavne
  som „Formularscan lille tværformat" gælder ikke længere som en person;
  frie navne og steder med lignende begyndelse forbliver beskyttet. Et
  generelt formulargæt fra det afsluttende PDF-sideforløb kan ikke
  længere skabe et stort adressefejlfund på en billedflade, der allerede
  er læst uafhængigt. De 120 nye beholdere når i grund- og
  egenskabsprofil alle henholdsvis 813 og 840 forventede angivelser uden
  falsk alarm, bevaringskrænkelse eller afbrydelse; den fuldstændige
  800-filers egenskabsafprøvning bekræfter 5.600/5.600.

- Det tyske OCR-laboratorium omfatter nu 560 scanninger fra 40
  dokumentfamilier. Nye varianter beskærer felthoved- og siderande eller
  lægger en skygge direkte over en værdi. Maskuro beskytter samtidig navne,
  adresser, fødselsdatoer, medicinske koder og betegnede id-numre med
  delvist beskadiget mærkning. Samtidig erstattes formularfeltrester,
  officielle overskrifter samt saglige juridiske og informationsbegreber
  ikke længere som personer eller steder. De fuldstændige grund- og
  egenskabsprofiler når 3.794/3.794 henholdsvis 3.920/3.920 forventede
  angivelser uden målt falsk alarm eller afbrydelse.

- Den automatiske PDF-billedudvælgelse fjerner ikke længere
  storformatede produktfotos, energimærker og portrætrækker udelukkende
  fordi de begynder ved øverste siderand. Ægte flade top-/bundbilleder og
  brevhoveder, der starter ved arkkanten, falder fortsat. I
  medarbejderfortegnelser genkendes navne nu også fra strukturelt
  gentagne poster, når den synlige dokumenttitel kun findes som billede.
  Genkendelsen er ikke længere skåret til to konkrete rolleord og
  forkortelsen „DW": et til fire ombrudte roller samt „Durchwahl",
  „Nebenstelle", „Ext." og „Extension" udledes nu af den fælles
  bygningsform. Roller og afsnitshoveder bliver stående, også når
  sprogmodellen efter overlapningsopløsningen kun efterlader et
  rolleadjektiv. Vandrette rollegitre gælder ikke længere fejlagtigt som
  navnesøjler. Sammenklæber sidegenkendelsen (OCR) flere kort til et
  ekstremt bredt indre versalord, adskiller et snævert lokalt modblik de
  virkelige ordkasser; derved bliver hverken et enkeltnavn eller en bred
  fejlbjælke tilbage. Gentagne flerlinjede firmalogoer sortsløres nu ud
  fra en allerede bekræftet identisk pixelskabelon, også på sider uden
  brugbar OCR-tekst og ved op til to pixels lejeafvigelse; kortere
  lokale genlæsninger af OCR må samtidig ikke længere supplere et større
  hovedområde som opfundet navn. Sidetal foran et firmabrevhoved hører
  ikke længere til organisationsnavnet, numerisk begyndende ægte
  varemærker forbliver beskyttet. Flere målte produkt-, fag- og
  formularord foreslås ikke længere som personer.

- Underskriftssøgningen kører ved PDF'er først efter OCR-billedrensningen,
  besøger også sider uden almindeligt tekstfund og regner fundkasser på
  drejede sider korrekt tilbage til dokumentrummet. Tætte produktfotos
  sortsløres ikke længere som underskrift. Over entydigt betegnede
  signaturfelter lukker et snævert stregfaldback tynde modelhuller; tomme
  linjer med fortrykt dato udløser det ikke. Rene scanninger med
  udelukkende OCR-/underskriftsfund afbrydes ikke længere i denne fase
  på grund af en billedsortslører, der først indlæses i tekstgrenen.

- Mange samtidig åbne dokumenter forbliver adskillelige i
  redigeringsværktøjet: Fanebladene skrumper ikke længere ned til blot
  et udeladelsestegn, og en listeknap til højre viser alle fulde
  filnavne under hinanden. Faneblade kan omordnes ved at trække og
  fjernes med deres kryds fra samme liste som i hovedvinduet;
  ugemte arbejde afklares fortsat først. Et højreklik tilbyder desuden
  „Luk", „Luk andre faneblade" og „Luk faneblade til højre".

- En kortvarig Windows-blokering fra virusscanner eller søgeindeks får
  ikke længere den færdigindlæste sprogmodel- henholdsvis ordbogsmappe
  til at fejle med „Adgang nægtet" ved den afsluttende indsættelse.
  Maskuro forsøger nu dette sidste mappeskift igen i kort tid.

- Det tyske dokumentlaboratorium kontrollerer nu beholdere også med
  skiftende PDF-sidedrejning, uafhængigt drejede PDF-billeder samt
  skalerede og beskårne tabelbilleder i DOCX og ODT. Feltværdier i
  synligt drejede billeder genkendes igen fuldstændigt, tekniske
  søjlebetegnelser erstattes ikke længere som steder, og navne med
  fælles efternavn opdeles ikke længere af konsistens-eftergangen i
  dobbelte deltræf. Den til 320 filer fordoblede matrice når med
  tilkoblet dato-, penge- og medicingenkendelse 2.240/2.240 forventede
  angivelser uden målt falsk alarm eller afbrydelse.

- Flersidede billed-PDF'er, blandede tekst-/billed-PDF'er og indlejrede
  scanninger i DOCX eller ODT kontrolleres nu i et eget 160-filers
  laboratorium over alle 40 tyske dokumentfamilier. Tekniske
  ODT-rammenavne og betegnede enhedskoder erstattes ikke længere som
  steder; ægte navne, steder og adresser i de samme strukturer forbliver
  beskyttet. Med tilkoblet medicin- eller pengegenkendelse fjernes
  desuden en umiddelbart følgende dosering henholdsvis et
  betalingsinterval fuldstændigt. Beholder-, tekstgrund-, tekstegenskabs-
  og OCR-egenskabsforløb når tilsammen deres respektive fuldstændige
  niveauer uden målt falsk alarm eller afbrydelse.

- Sikkerhedskontrollen før lagring viser nu iøjnefaldende PDF-steder som
  en enkeltvis vælgbar liste. „Kontrollér i editor" åbner netop den
  valgte side og markerer området; overlappende deltræf på samme sted
  vises kun én gang. De nye betjeningstekster er fuldstændigt til stede
  på alle 17 oversatte grænsefladesprog.

- Markdown-filer beholder deres henvisnings-, fremhævnings- og
  fodnotesyntaks ved erstatning. Maskuro læser dertil en tegnligeledes
  lang udgave uden Markdown-markeringer; understregninger i
  e-mailadresser, regnestjerner og almindelige henvisninger uden personlig
  angivelse forbliver uændrede.

- Flere håndskrevne indførsler på samme PDF-side søges nu i op til tre
  omgange. Allerede fundne træk skjules kun i arbejdsbilledet, så de
  ikke længere fortrænger svagere underskrifter; på drejede sider
  havner sortsløringsfladerne igen på det synlige fundsted.
  Billedfyldninger fra tidligere sikkerhedsfaser bevares ved den
  efterfølgende tilbageskrivning.

- „Nulstil alle indstillinger" omfatter nu også „Tekst i billeder". Er
  OCR-komponenten ikke tilgængelig, forbliver kontakten teknisk fra,
  uden fejlagtigt at blive markeret som afvigende fra leveringsstanden.

- Store billedfragmenter ved øverste siderand gælder ikke længere blot
  på grund af deres placering som sidehoved. Derved bevares især
  billedbaserede artikelbeskrivelser og tabelindhold. Nyt genkendte,
  typepræcise e-mail- og formularfund udelukkes desuden heller ikke
  længere fra den afsluttende synskontrol, selv på en allerede
  kontrolleret billedflade.

- Tekniske positions- og artikellinjer i klima- og eltilbud
  adskilles nu snævrere fra personer, steder og organisationer. Det
  gælder blandt andet kabeltyper, AC-forsyning, positionsnumre samt
  versale produktkoder; ægte navne og adresser forbliver beskyttet.

- Kontrollen af rigtige rensede PDF'er forveksler ikke længere
  prisbestanddele som `1 699,59` med telefonnumre og skærer ikke
  længere en formodet kortangivelse ud af en fuldstændig dato som
  `08.05.2025`. Navne efter en tiltaleform ender ved linjeskiftet i
  stedet for i den følgende gade; stednavne i bilagsfilnavne begrænses
  til det faktiske sted. Køretøjsfarver, tekniske statusværdier,
  branchebetegnelser og produktretsformer bevares ligeledes. Beskadigede
  pladsholderaflæsninger som `|PLLZ` behandles ikke igen som personlig
  angivelse ved en anden OCR-gennemgang.

- Sidevis gemte PDF-billeder får ved den afsluttende synskontrol et
  ekstra kig i deres uændrede billedlejring. Dette må udelukkende
  eftersortslør værdier, som Maskuro allerede sikkert har genkendt på
  samme side. Således dækkes for eksempel et lille drejet adressestempel
  fuldstændigt uden at opfinde nye ord fra billedoverskrifter eller
  tekniske tegninger som personlige angivelser.

- I OpenDocument-tekster tømmes en kommentarforfatters initialer nu
  sammen med forfatteren. LibreOffice lægger dem ved siden af det fulde
  navn som en egen kortform og viser netop denne i margenen; hidtil
  stod „SO" fortsat, mens „Sieglinde Ortner" ved siden af for længst var
  en pladsholder. Der tømmes kun, hvis forfatteren rent faktisk blev
  erstattet – en afdelings kommentar beholder sin betegnelse.

- I italienske forretningsbreve gælder standardvendinger ved
  sætningsbegyndelsen ikke længere som navn eller sted: „Restiamo a
  disposizione", „Rimaniamo", „Attendiamo", „Alleghiamo", „Comunichiamo"
  og „Auguriamo buon lavoro" blev hidtil hængende som formodet person-
  eller stedangivelse. Ægte navne samme sted („Rossi Mario") genkendes
  fortsat.

- Tospaltede scanninger beskytter nu betegnede id-numre og stedangivelser
  også når teksgenkendelsen først leverer alle felthoveder og derefter
  alle værdier. Tilordningen følger den synlige pixellinje og fungerer
  også ved sider drejet 90 grader. Tæt adskilte dele af et pas- eller
  kontraktnummer sortsløres samlet; betegnede fødselsdatoer, ICD- og
  PZN-koder er ligeledes dækket, efterfølgende sagsord bliver stående.
  Korte navne og brugernavne beskyttes ved eksakte felter; e-mailadresser
  opdelt i flere OCR-ord kun ved tæt naboskab og fuldstændig
  e-mail-grammatik. En feltbunden korrektion af forvekslingsegnede tegn
  samt den lokale genlæsning af et endnu tomt personfelt lukker
  beskadigede og drejede scanninger uden at udvide sagsfelter eller
  allerede belagte værdier. Sikkerhedsrande følger ordstørrelsen, og
  egenskabsprofilen medtager umiddelbart nabolagte doseringsenheder og
  betalingsintervaller. Let skævt indtrukne formularer projiceres
  geometrisk tilbage fra flere ensrettede OCR-linjer; afrundingsstøj
  eller modstridende vidner er ikke tilstrækkeligt. Korte bogstavpræfikser
  bliver stående foran en bindestregskode, og et fuldstændigt betegnet
  adressefund erstatter kun sit ensartede gadedeltræf. Et fejllæst
  rollefelthoved falder udelukkende i en formularsøjle belagt med
  mindst tre kendte hoveder; chatnavne forbliver beskyttet. En knap
  randbeskæring og en lokal overbelysning med diagonal lysrefleks
  supplerer billedmatricen. Person-, steds- og firmafund, der strækker
  sig over flere formularlinjer, begrænses i en flerfoldsbelagt
  feltsøjle til den respektive værdi. En teknisk positionsværdi falder
  kun med positionshoved og passende kodeform; ægte navne forbliver
  beskyttet. Også e-mailværdier afbrudt ved lysrefleksen fjernes bag
  et udtrykkeligt e-mail-felthoved med snæver, nabobegrænset billedrand.
  To felt-værdi-par i samme synlige linje vurderes nu uafhængigt af
  hinanden; værdier på en dybere grundlinje kobles kun efter tre
  overensstemmende geometriske vidner. Derved forbliver id-numre,
  fødselsdatoer og adresser fuldstændigt beskyttet også i tætte
  formularlayouts. Gade, postnummer og by forenes udelukkende inden for
  samme adressefelt og med passende postal grammatik. Snævert afgrænsede
  sagsfelter for arbejds-/hjælpemidler og tandstatus skaber ikke længere
  falske sted- eller registerfund; ægte navne og lignende benævnte felter
  forbliver beskyttet. Det tyske dokumentlaboratorium omfatter nu 440
  scanninger og når 2.981/2.981 i grundprofilen samt 3.080/3.080 i
  egenskabsprofilen. Alle elleve billedmutationer og alle 40
  dokumentfamilier ligger på 100 procent, fortsat uden målt falsk alarm,
  bevaringskrænkelse eller afbrydelse.

- PDF-tekstlag med mistede celleadskillere begrænser nu organisations-,
  adresse- og stedfund ud fra den gentagne felt-værdi-struktur.
  Felthoveder foran firmaværdier og tekniske pile som `=>` eller `->`
  hører ikke længere til fundet. Den ekstra visning for bløde
  linjeskift må ikke længere udvide retsforms- og stedfund over flere
  tabellinjer; en allerede fuldstændig adresse ender før næste
  felthoved med værdi. Det afsluttende forløb over alle 1.600 TXT-,
  HTML-, PDF- og DOCX-dokumenter fjerner 10.840/10.840 forventede
  angivelser ved nul falske alarmer, nul bevaringskrænkelser og nul
  afbrydelser.
