# Ændringer

Hvad der ændrer sig fra version til version – beskrevet set fra
applikationens side, ikke dens indre. Hvem der vil vide, *hvoraf* den er
bygget, finder det i [LIZENZEN.md](LIZENZEN.md); her står, hvad der ændrer
sig for arbejdet med den.

Nummereringen følger den sædvanlige tælling: Det **første** tal ændrer sig,
når noget ikke længere fungerer som hidtil, det **andet** ved nye
funktioner, det **tredje** ved fejlrettelser.

---

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

## 0.10.44-beta.1 – 1. september 2026

- Pakkebygningen genererer adskilte udgaver til Windows x64 og ARM64, macOS
  på Apple Silicon og Intel samt Linux x64 og ARM64. Pakkenavne,
  opdateringsvalg og frigivelser skelner arkitekturen; en udgivelse
  forbliver spærret, så længe et af de seks mål eller dets
  afhængighedsbevis mangler. Linux ARM64 kræver på grund af Qt mindst
  glibc 2.39. Fuldstændigt afprøvet på ægte hardware er foreløbig kun
  Windows x64 og macOS på Apple Silicon; de øvrige arkitekturpakker skal
  klart betegnes som forhåndsversioner til afprøvning i stedet for
  produktiv brug.

- Ved flere filer arbejder genkendelsen nu videre, mens en forhåndsvisning
  venter på gennemsyn. Op til tre forberedte forhåndsvisninger vises efter
  hinanden; samtidig regner fortsat kun ét dokument, og en resultatfil
  opstår først efter dens frigivelse. En i forhåndsvisningen valgt
  permanent undtagelse gælder også for allerede forberedte følgende
  dokumenter.

- Redaktionscertifikater kan nu til enhver tid kontrolleres direkte i
  filmenuen mod det slørede dokument. Maskuro skelner hermed mellem en
  passende signeret fil, et passende men usigneret bevis, en ugyldig
  underskrift og et dokument, der ikke hører til certifikatet. En licens
  eller den oprindelige styresystemkonto kræves ikke til kontrolprøven.
  Til automatiske kontrolsteder findes den samme sammenligning via
  `--zertifikat-pruefen`; returkoder skelner overensstemmelse,
  betjeningsfejl og ugyldigt bevis.
  Kontrolprøven sammenligner desuden den indlejrede Maskuro-ID med
  certifikatet; en frit indtastet fremmed ID falder derved også ved et
  usigneret bevis i øjnene.
  Ved gyldig underskrift viser kontrolfundet desuden den af
  administrationen aktiverede redaktør med styresystemkonto, teknisk
  konto-ID og platform. Ubekræftede angivelser fra usignerede eller
  ugyldige beviser udgives ikke.

- Et nyt tysk dokumentlaboratorium genererer 160 fuldstændigt syntetiske
  TXT-, HTML-, PDF- og DOCX-dokumenter fra ti områder og fire
  strukturvarianter. Manifestet skelner nu udtrykkeligt mellem
  angivelser, der skal forsvinde, og fagtekster henholdsvis
  sagskendinger, der skal bevares; dokumentfamilie, mutation og offentlig
  strukturkilde er sporbart dokumenteret.

- Det tyske dokumentlaboratorium blev udvidet til 280 filer, syv
  strukturformer, 1.540 målangivelser og 1.036 bevaringsankre. Nyt
  kontrolleres nummererede formularer, parentessatte PDF-/maskefelter og
  tekniske `=>`-tilknytninger. Det udvidede fulde stade opnår i TXT,
  HTML, PDF og DOCX hver især 100 procent ved nul falske alarmer.
  Parentessatte dato- og identifikationsnummerfelter, pileadskillere og
  udtrykkeligt betegnede forbund genkendes nu strukturelt.

- En anden laboratorieudvidelse hæver bestanden til 400 dokumenter, ti
  strukturformer, 2.200 målangivelser og 1.480 bevaringsankre.
  JSON-agtige nøgleværdier, YAML-lister og versale formularfelter opnår
  sammen med den hidtidige bestand 100 procent ved nul falske alarmer.
  Citerede fødselsdatoer og identifikationsnumre samt udtrykkeligt
  betegnede roller som forsikrede, ansøgende, afgiftspligtige og
  repræsentationsberettigede personer genkendes nu også i disse
  eksportformer.

- En adskilt OCR-tilstand af det tyske dokumentlaboratorium genererer
  desuden 200 rene billedscanninger fra alle 40 familier. Rene,
  kontrastfattige, lavtopløste, JPEG-artefaktbehæftede og 90 grader
  drejede sider efterprøves med nøjagtige pixelkasser, uden at ændre det
  sammenlignelige 1.600-filers tekstgrundstade. Manifestet adskiller
  tilkoblelige dato-, penge- og medicinske kendetegn fra grundprofilen og
  kender belagte OCR-læsemåder, uden at tælle dem som ekstra
  målsteder. Målingen opdeles efter mutation og dokumentfamilie. Snævre
  feltgrænser forhindrer blandt andet, at `Az` i stednavnet `Graz` slører
  en følgende dato som sagsnummer; den aktuelle grundmatrix kører med nul
  falske alarmer og nul afbrydelser.

- Fem yderligere tyske dokumentfamilier for faktura/følgeseddel,
  bank/kredit, husleje/ejendomsadministration, skole/universitet og
  logistik/told udvider laboratoriet til 600 filer med 3.520
  målangivelser og 2.360 bevaringsankre. En snæver PDF-tabelvej bruger
  den udtrykkelige overskrift `Felt Angivelse`, når tekstlaget mister
  celleadskillere; et nyt `--familien`-valg fremskynder delmålinger. De
  200 nye filer opnår 1.320/1.320 ved nul falske alarmer og nul
  afbrydelser.

- Forsikring/skade, arbejde/løn, medicin/laboratorium, køretøj/værksted og
  teknik/vedligeholdelse udvider det tyske dokumentlaboratorium til 800
  filer med 4.960 målangivelser og 3.200 bevaringsankre. Snævert
  betegnede police-, patient-, kontrol- og køretøjsidentifikationer samt
  nye rolle-, adresse- og organisationsfelter genkendes. Den nye
  delmatrix og den fuldstændige matrix opnår 100 procent ved nul falske
  alarmer og nul afbrydelser i TXT, HTML, PDF og DOCX.

- Byggeri/udbud, energi/miljø, forening/selskab,
  kommunikation/kalender og hotel/arrangement hæver det tyske
  dokumentlaboratorium til 1.200 filer med 7.920 målangivelser og 4.800
  bevaringsankre. Nye rolle-, firma-, adresse-, register-, tildelings-,
  bestillings- og brugerkontofelter genkendes også i alle
  eksportformer. Tællernumre forbliver bevaret som sagskendinger. Del- og
  fuldmatrix opnår 100 procent ved nul falske alarmer og nul afbrydelser.

- Gastronomi/leveringstjeneste, apotek/recept, bedemand/kirkegård,
  sport/medlemskab og ejendom/mægler udvider det tyske
  dokumentlaboratorium til 1.400 filer med 9.360 målangivelser og 5.640
  bevaringsankre. Nye personroller, adressefelter og søgeordrenumre
  genkendes. Betegnede firmanavne med selskabsform forbliver fuldt
  beskyttede også over et automatisk linjeskift; aldersgrupper og
  fagoverskrifter erstattes ikke længere fejlagtigt. Del- og fuldmatrix
  opnår 100 procent ved nul falske alarmer og nul afbrydelser.

- Tandbehandling, køreskole, brandvæsen/udrykning, energifællesskab og
  pakkerejse udvider det tyske dokumentlaboratorium til 1.600 filer med
  10.840 målangivelser og 6.440 bevaringsankre. Nye roller, adressefelter
  samt behandlings-, uddannelses-, udrykning-, energi- og
  rejsekontraktidentifikationer genkendes strukturelt. Den nye
  200-filers delmatrix opnår 1.480/1.480; den fuldstændige matrix opnår
  10.840/10.840. Begge forbliver ved nul falske alarmer og nul
  afbrydelser.

- Fuldmålingen af dokumentlaboratoriet sænkede gennem snævre officielle
  sagformer og strukturregler de unødvendige erstatninger fra 68 til 0,
  de udtrykkeligt målte bevaringskrænkelser fra 23 til 0 og afbrydelserne
  fra 3 til 0. Fundkvoten steg samtidig fra 91,1 til 100,0 procent; TXT,
  HTML, PDF og DOCX opnår hver især 100 procent. Almindelige
  tabeloverskrifter som `Felt` bremses kun i den belagte følge
  `Felt`/`Angivelse`; et enslydende efternavn forbliver beskyttet.
  Retslige sagsnumre med slutbogstav, lighedstegn-felter,
  `Barnets fødselsdato` og flere betegnede enkeltnavne i samme linje
  genkendes fuldstændigt. Word-tabeller og forlinjefelter bruger deres
  feltoverskrift som midlertidig genkendelseskontekst; betegnede
  PDF-adresser forbliver fuldt beskyttede også ved et satsbetinget
  linjeskift.

- Tyske personkendetegns-, erhvervs- og medicinske felter fungerer nu
  også med Windows-linjeskift. Enbogstavs-kønsangivelser som
  `Køn`/`k` beskyttes i forlinjeformen. Saglige `Artikel-PZN`-felter
  udløser derimod hverken et lægemiddelnøgle- eller et personfund; ægte
  PZN-, ICD- og ATC-angivelser forbliver genkendt.

- Tyske formular- og nummerfelter er mere præcise: „DW." fungerer nu også
  foran et blødt linjeskift, udtrykkeligt betegnede navne fjernes selv
  med lille bogstav, og rent numeriske sagsnumre tilknyttes deres rigtige
  identifikationsnummer-art. Omvendt gælder et tilfældigt Luhn-gyldigt
  faktura-, bilags- eller artikelnummer ikke længere som kreditkort.
  Syntetiske HTML- og PDF-udgangsprøver bekræfter fjernelse og bevaring i
  det færdige dokument.
  Identifikationsnumre og brugernavne genkendes desuden, når deres
  betegnelse står i den umiddelbart forudgående tabel- eller
  formularlinje; saglige bilagsnumre forbliver også i denne form
  synlige.

- Kodeord genkendes nu også bag en alenestående feltoverskrift i den
  forudgående linje. Afsluttende specialtegn som `!` eller `#` hører
  hermed fuldstændigt med til den beskyttede værdi. Produkt- og
  artikel-PIN'er maskeres omvendt ikke længere som kort-PIN;
  udtrykkelige `PIN`- og `Kort-PIN`-felter forbliver beskyttede.

- Med lille bogstav skrevne formularværdier udgives nu ved entydige tyske
  adresse- og `Postnummer/By`-felter som adresse henholdsvis postnummer
  med by i stedet for kun som generelt sted. Ligeledes forbliver med
  lille bogstav skrevne firmaværdier som „eksempel service" bag et
  firmafelt fuldt beskyttede, uden at afskære slutordet som en formodet
  næste feltoverskrift.

- Hjælp, FAQ, databeskyttelsestekst og hjemmeside forklarer nu
  herkomstbeviset samlet: neutral Maskuro-ID i dokumentet, valgfri
  tilknytning til den ægte styresystemkonto kun i den lokale
  kontrolprotokol, brugerskift via Windows/macOS/Linux samt
  udsagnskraften af SHA-256 og underskrift.

- Billedbaserede tekniske arbejdsbeskrivelser renses mere tilbageholdent.
  Entydige sagord som „nedbrydningshamre", „garantiforbehold",
  „positionsnumre", „indbygningsplatine" eller „terminsituation" samt
  midt i ordet delte OCR-former gælder ikke længere som person eller
  sted. Et virkeligt kommunekontor-tilbud faldt derved fra 140 til 90
  entydige erstatninger, uden at skabe nye fund; navne som Schneider,
  Lang, Bauer og Hahn forbliver udtrykkeligt beskyttede.

- Yderligere falske alarmer fra virkelige tilbud er rettet: „Digitalt
  signeret" indeholder ikke længere en formodet person, en BIC genkendes
  også uden kolon bag sin betegnelse, `15000 Alternativt` gælder ikke som
  postnummer med by, og EU-citatet „(VO (EF) 715/2007" skaber ingen
  organisation. Et solcelletilbud faldt derved fra 26 til 16
  erstatningsforekomster; ægte navne, steder og kontodata blev bevaret.

- I medarbejderoversigter erstattes forkortelsen for stedfortræder „Stv."
  og en alenestående „FACILITY"-områdeoverskrift ikke længere som
  personnavn. Den virkelige 13-siders kontrolprøve faldt fra 878 til 875
  erstatninger; navne, lokalnumre og firmabetegnelsen forblev beskyttede.

- Rensede PDF-, OpenDocument- og Office-filer får en neutral
  `MASKURO-…`-kending i deres dokumentegenskaber. Kontrolrapport og
  signeret kontrolprotokol fører samme kending samt SHA-256-værdier fra
  kilde og resultat; redaktionscertifikatet overtager kendingen fra den
  færdige fil. Et brugernavn kommer fortsat kun med, når administrationen
  udtrykkeligt tilkobler det eksisterende brugerfelt.

- Hovedvindue og indstillinger er roligere opdelt: Gem, kopiér, detaljer,
  nøgletal og sletning af en genkendelsesprofil fremkommer først, når den
  pågældende handling er mulig. Tekniske OCR-sprogforkortelser og lange
  eksempler står ved behov i henvisningsteksten i stedet for permanent i
  arbejdsfladen. Genkendelsessiden tilpasser sig bedre til smallere
  vinduer, uden afskårne forklaringer eller vandrette rullebjælker;
  advarslen om klartekst i erstatningslisten forbliver hermed synlig.

- Genkendelsen omfatter flere tyske og internationale kontakttilfælde:
  Telefonnumre kontrolleres nu for alle valgbare landeregioner, ungarske
  og kroatiske kontraktroller omfatter nu også erhvervssammenfaldende
  efternavne fuldstændigt, og nummererede reservedels-/materiallister
  udløser ikke længere en personfalsk alarm på grund af „Møtrik / Flad".
  Personfelter med tydeligt cifferholdig sagværdi overtages ikke som
  navn; den maskinlæsbare paszone (MRZ) kan desuden tændes og slukkes
  samlet via gruppen „Kendinger".

- Firmaer uden selskabsform skelnes bedre fra personer bag flertydige
  arbejdsgiverfelter: Navne som „Huber Handel", „Müller Logistik" eller
  „Kowalski Handel" opfattes fuldstændigt som firma, mens „Arbejdsgiver:
  Bauer Anna" fortsat forbliver et personnavn. Det automatiske landevalg
  tager ved franske dokumenter fortsat hele det franske sprogområde med
  i betragtning, inklusive Luxembourg.

- Genkendte underskrifter og personoplysende tekst inden i et billede
  blev hidtil altid dækket med et sort rektangel – også når der for
  sløringer var indstillet en anden farve eller et mønster som
  „regnbue". Disse billedområder overtager nu ligeledes den valgte
  sløringsfremtoning; den dækkende flade skrives fortsat direkte i
  billedpunkterne.

- Den engelske genkendelse blev efterprøvet på elleve manuelt oversatte
  virkelige dokumenter og målrettet forbedret: Lagerstatus, tekniske
  tilbuds- og webshopfelter samt roller i medarbejderfortegnelser
  forbliver synlige, „CV" læses ikke længere som selskabsform i
  skabelonsætningen, citerede skrifttyper bevares, og navne i lodrette
  CV-hoveder, flersidede medarbejderlister, bag „Account manager" samt
  cifferbegyndende firmanavne genkendes fuldstændigt. Østrigske
  firmabogsnumre fungerer nu også bag en engelsk betegnelse; kortformen
  „Customer:", EAR-registreringsnumre og arbejdsgivernumre bærer deres
  værdi. Målkæder, kabeltyper, EU-retshenvisninger, tilbuds-gyldighedsdatoer,
  opfyldelsessteder, værneting, registerretter, skatteforkortelsen „NoVA",
  tekniske numre i dæklabels samt normhenvisninger som „OVE R6-2" og
  „AStV" skaber ikke længere en falsk alarm. En gyldig betegnet IBAN
  slutter rent foran registreringsfeltet eller overskriften på den
  følgende linje; adresser med erhvervszone-tilføjelse genkendes
  fuldstændigt også fra PDF-tekststrømme med Windows-linjeskift. Engelske
  firmaindledninger og strukturerede sparekassenavne afgrænses
  fuldstændigt. Kildedokumentets land forbliver bevaret ved
  sprogfassionerne for postnumre og landespecifikke kendinger.

- I modtager- og meddelelseshoveder kunne sprogmodellen forbinde de
  første to navne i en kommaliste til ét eneste fund („Bcc: Huber,
  Mayer"). Begge navne genkendes nu enkeltvis, erstattes og føres i
  rapporten – ligeledes bag „Sent:", „Reply:" og „Fwd:".

- Det maskinlæsbare område på et pas eller ID-kort (MRZ) manglede i
  gruppestyringen „Hvad der søges efter". Det hører nu til „Kendinger"
  og kan tændes og slukkes samlet med denne gruppe.

- Den, der for erstatningstekster vælger skabelonen „regnbue", får nu
  også slørede steder i samme fremtoning; hidtil forblev de
  overraskende klassisk sorte. Sløringsfladerne kan derefter fortsat
  uafhængigt stilles om til en anden skabelon.

- Sidefaget i editoren til efterretning kunne forblive tomt efter
  genoprettelse af en gemt vindueopdeling, indtil dets bredde blev ændret
  manuelt. Miniaturerne nyordnes nu efter den synlige vinduesopbygning og
  står straks centreret i faget.

- De farvede kontrolmærker om erstatningstekster i PDF'er forblev alt
  efter kategori- og trafiklysfarve næppe synlige. En lys underkontur
  adskiller nu kontrolrammen pålideligt fra den farvede pladsholder og
  fra sidebaggrunden.

- Den, der i editoren til efterretning slører en linje, hvis dokument er
  sat med snæver linjeafstand (typisk for tilbud og
  arbejdsbeskrivelser), fik en bjælke, der stak ind i overlængderne på
  linjen nedenunder – den var derefter kun halvt læselig. Bjælken slutter
  nu ved nabolinjens virkeligt tegnede skrift; selve den slørede linje
  forbliver hermed fuldt dækket sammen med sine underlængder.

- Øvelsesdokumentet („Hjælp → Åbn øvelsesdokument", også i rundturen)
  fremviser nu hver genkendelsesart: Til det opdigtede brev kommer et
  fotografi med genkendeligt ansigt, en skreven underskrift, erhverv og
  afdeling, diagnose og medicin til – ved siden af firmanavn, beløb og
  dato, som allerede var der. Hvad standardindstillingen bevidst lader
  stå, forklarer arket selv, sammen med kontakten, der fjerner det;
  ansigtet på fotografiet pixeleres fra fabrikken.

- Pengebeløb i den sædvanlige tyske skrivemåde med symbolet efter tallet
  („1.240,00 €") blev aldrig fundet af kontakten „Fjern også
  pengebeløb" – „1.240,00 EUR" og „€ 1.240,00" derimod altid. Nu genkendes
  alle tre skrivemåder.

- Underskriftssøgningen arbejder nu også på alenestående billedfiler: Den,
  der renser en scanning som JPG eller PNG, får håndskrevne underskrifter
  deri sløret – samme genkendelse, samme meddelelse i rapporten som ved
  PDF. Billeder indlejret i Office-filer gennemsøges fortsat ikke, fordi
  genkendelsen der målt arbejder upålideligt; fluebenet hedder derfor nu
  „PDF og billedfiler: Slør håndskrevne underskrifter".

- En sløringsbjælke kunne ved snæver linjeafstand synligt stikke ind i
  overlængderne på linjen nedenunder og gøre den halvt ulæselig –
  bjælkehøjden kom fra skriftmetrikkerne, ikke fra det, der virkelig
  står på papiret. Bjælken slutter nu ved nabolinjens virkeligt tegnede
  blæk, i editoren til efterretning såvel som i den automatiske
  rensning. Den egne linje forbliver hermed altid helt dækket sammen med
  underlængder; overlapper linjerne virkelig, forbliver bjælken hellere
  på nabolinjen, end at frigive noget.

- I en medarbejderfortegnelse med rolle under navnet blev en kvindelig
  ledelsesbetegnelse („Anna Berger" med „Montageleder" [f] nedenunder)
  trukket med ind i navneerstatningen – den mandlige form ved siden af
  forblev korrekt stående. De kvindelige „…leder"-formene (montage-,
  team-, projekt-, bygge-, afdelings-, drifts-, gruppe-, kontorchef)
  behandles nu ligesom deres mandlige modstykker som
  funktionsbetegnelse; filial-, personale- og salgsledelse er i begge
  former nyt med.

- Den tilkoblelige erhvervsgenkendelse fandt ikke kvindelige
  ledelsesroller som „projektleder" [f], „teamleder" [f] eller
  „afdelingsleder" [f], deres mandlige former dog. Begge former tæller
  nu ligeligt.

- I forhåndsvisningsvinduet klæbede flerdobbeltangivelsen på Mac'en
  direkte til begrebet („Anna Musterfrau2ק i stedet for „Anna
  Musterfrau 2ק). Mellemrummet er der igen.

- Sammenligningsluppen har en ny knap ved siden af zoom-skyderen: Den
  lægger den med ét tryk i fuld bredde over resultatet – hver halv
  højde, og originalen i samme målestok som dokumentet (lupzoomen
  springer dertil til 100 %). Et andet tryk dokker den igen lille ind i
  venstre spalte og genopretter den forrige lupzoom. Cirklen ved siden af
  nulstiller nu kun zoomen – dens hjælpetekst påstod hidtil fejlagtigt,
  at den også dokkede vinduet igen.

- I værktøjslinjen i editoren til efterretning kan man igen se på det
  valgte værktøj, at det er valgt: Knappen for det aktive værktøj bærer
  en udfyldt flade med blå kant – ligeledes enhver anden tilkoblet
  omskifterknap i linjen (f.eks. sammenligningslup eller
  læringstilstand). Markeringen var gået tabt med den egne
  knapudformning fra 29. august.

- Positionsnumre i en arbejdsbeskrivelse („2.3.3.3, 2.3.3.4, 2.3.3.5"
  under hinanden) blev opfattet som IP-adresser og fjernet fra
  resultatet; trecifrede numre med årstalslignende sidste led
  („2.3.19, 2.3.20") faldt som kalenderdatoer. En stigende talfølge ved
  linjens begyndelse gælder nu som det, den er – en positionsliste; ægte
  adresser (netværkstabeller med teknisk ordomgivelse, tal over 99) og
  ægte datoangivelser forbliver fortsat genkendt.

- Efternavne som „Müller", „Fischer", „Bauer", „Koch", „Wagner",
  „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster",
  „Schäfer" eller „Meister" blev stående i klartekst i lister af formen
  „Efternavn, Fornavn" (f.eks. „Deltagere: Müller, Peter; Nowak, Anna"),
  fordi de samtidig er almindelige erhvervsbetegnelser. De genkendes nu
  pålideligt.

- Ved sløring af en PDF kunne bjælken i smalle tabelceller tage hele
  cellen med sig: Af fundet „D-LINK" i en arbejdsbeskrivelse blev hele
  produktbeskrivelsen ved siden af fjernet, selv om forhåndsvisningen
  kun havde nævnt fundet. Bjælken dækker fortsat hele
  adresseblok-linjer og feltbetegnelser, men opsluger højst så meget
  uvedkommende, som den dækker beskyttelsesværdigt – beskrivelsen ved
  siden af fundet bliver nu stående.

- Efter „Nulstil visning" i editoren til efterretning forblev sidefaget
  tomt – sidernes miniaturer var først synlige igen efter lukning og
  genåbning af vinduet. Nu står de der også direkte efter nulstillingen,
  centreret som før.

- Editoren til efterretning har et fjerde værktøj: **Fjern** tager
  teksten under rammen ud uden erstatning – uden bjælke (sløring) og uden
  pladsholder (erstatning); hullet forbliver synligt tomt. Det arbejder
  ordpræcist, ligger der et billede nedenunder, ryddes dets grund hvidt,
  og „Hent original tilbage" fortryder også en erstatningsløs fjernelse.
  Eget linje-symbol og trådkorsmærke (kryds), egen mærketast på alle 18
  sprog (dansk F som i Fjern).

- I PDF-søgelinjen står „Mappe …" nu til højre for søgemulighederne.
  Siden der ved siden af sløringen også findes erstatning af fund,
  passede fem knapper ikke længere ved siden af hinanden ved almindelig
  vinduesbredde – den første blev sammenpresset og dens tekst afskåret.

- „Nulstil alle indstillinger" nulstiller nu også fluebenet „Erstat
  rødt/grønt med andre farver" og noterer det som enhver anden med
  „ændret", hvis det afviger fra leveringen.

- Erstatningstekster i PDF'er virker nu mere ensartede: Hvor den fulde
  pladsholder skulle blive betydeligt mindre end sin linje (f.eks.
  „[BEG16]" presset ind i et kort ord som „Det"), står der i stedet en
  kortform i linjestørrelse („[B16]") – godt læselig i stedet for
  mikroskopisk, og nummeret til tilbagehentning bærer begge skrivemåder.
  Mikroskopisk lille bliver en pladsholder kun, hvis selv den korteste
  form ikke finder plads – det forbliver bedre end en bjælke uden nogen
  oplysning.

- En flerfarvet sat erstatningstekst (forløb eller regnbue) i en PDF
  forblev kun hel indtil det næste indgreb: Enhver yderligere erstatning
  eller sløring på samme side kunne skubbe allerede satte pladsholdere
  sammen til en ulæselig, sammenpresset bogstavstak – den, der i
  editoren erstattede ord for ord, så i stedet for „[BEG17]" kun tegn
  trykt oven i hinanden. Én gang satte pladsholdere bliver nu stående,
  som de blev sat.

- Kontakten for permanente undtagelser i forhåndsvisningen hedder nu
  „Fjern aldrig" – som listen, den indfører til; hidtil stod der
  „aldrig igen". Fundlinjen ved siden af er ryddeligere: Infosymbolet
  „ⓘ" er større og lettere at ramme, og felt, erstatningsmærke og knap
  har en fælles højde. Sætningen om et fund bruger nu virkelig sin
  annoncerede bredde – den hidtidige breddeangivelse havde stiltiende
  forkastet visningen, og udsnittet brød om som en smal stribe.

- I editoren siger musemarkøren nu, hvilket værktøj der virker: et
  trådkors til at sigte med, ved siden af et lille tegn – bjælke til
  sløring, byttepile til erstatning, fortryd-bue til genoprettelse,
  pixelraster til pixelering. De hidtidige håndsymboler bortfaldt; en
  hånd betyder ellers overalt „gribe og skubbe". Den har nu en passende
  opgave: Over et rødt fremhævet ord eller en bjælke bliver markøren til
  den pegende hånd – et klik er nok der.

- „Maksimal genkendelse (AI)" tilbyder ikke længere en downloadbar,
  lokal sprogmodel – niveauet regner nu udelukkende over en under „Tilslut
  egen AI" indrettet, egen AI. Den, der allerede havde tilsluttet en
  egen server, mærker ingen forskel.

- Den guidede rundtur i forhåndsvisningen forklarer nu også infosymbolet
  „ⓘ", der viser sætningen om et fund. Og selve denne sætning er mere
  læselig: et niveau større skrift, mere linjeafstand, fast bredde i
  stedet for en smal, tæt presset ombrydning.
- Også „Kontrollér fil", „Genkendelsesregler og egne begreber", „Rens
  tekst" og „Rens billede" har nu en egen rundtur – via en ny knap
  „Rundtur gennem vinduet", da disse fire vinduer ikke har en egen
  menulinje.
- Navne under ni ukrainske kontraktrolle-betegnelser forblev ufuldstændigt
  genkendt ved et homograft efternavn, når betegnelsen stod alene på sin
  linje: „Покупець"/„Продавець" (køber/sælger), „Поручитель"/„Боржник"
  (kautionist/hovedskyldner), „Свідок" (vidne), „Орендодавець"/„Орендар"
  (udlejer/lejer) og „Спадкодавець"/„Спадкоємець" (arvelader/arving).
  Navnene genkendes nu fuldstændigt.

- Kommentaren til et navngivet område i en Excel-arbejdsbog
  (navnestyring, feltet „Kommentar") bar et deri indtastet navn uændret
  videre. Den renses nu ligesom det øvrige indhold i arbejdsbogen.

- Navne under syv ungarske kontraktrolle-betegnelser forblev helt
  uopdaget ved et homograft efternavn: „Bérbeadó"/„Bérlő"
  (udlejer/lejer), „Vevő"/„Eladó" (køber/sælger), „Kezes"/„Főadós"
  (kautionist/hovedskyldner) og „Tanú" (vidne). Navnene genkendes nu
  fuldstændigt.

- Navne under den tjekkiske køberbetegnelse „Kupující" forblev helt
  uopdaget ved et homograft efternavn. Navnet genkendes nu fuldstændigt.

- Navne under den russiske værgebetegnelse „Опекун" forblev helt
  uopdaget ved et homograft efternavn. Navnet genkendes nu fuldstændigt.

- Navne under seks yderligere kroatiske betegnelser forblev uopdaget:
  „Jamac" (kautionist), „Glavni dužnik"/„Dužnik" (hovedskyldner/skyldner),
  „Ostavitelj" (arvelader), „Nasljednik" (arving) og „Vjerovnik"
  (kreditor). Navnene genkendes nu fuldstændigt.

- En gemt HTML-side med en indlejret underside i `src`-attributten på et
  `<embed>` (i stedet for `data` ved `<object>`) bar personoplysninger deri
  uændret videre. De renses nu ligesom ved `<object>`.

- Navne under fem danske kontraktrolle-betegnelser forblev ufuldstændigt
  genkendt ved et homograft efternavn, når betegnelsen stod med kolon
  foran navnet: „Arvelader"/„Arving", „Befuldmægtiget"/„Fuldmagtsgiver"
  og „Værge". Navnene genkendes nu fuldstændigt; de tilsvarende norske
  betegnelser er til sikkerhed også tilføjet.

- Pladsholdere i Word- og PowerPoint-filer bærer nu samme farve som i
  den valgte fremtoning (ensfarvet, forløb, regnbue eller pr. kategori) –
  hidtil forblev de der i almindelig tekstfarve, selv når PDF-resultater
  for længst var farvede.

- „Kopiér som tekst" og „Kopiér som Markdown" lægger resultatets
  klartekst direkte på udklipsholderen – til indsættelse i chat, mail
  eller et andet program, uden først at åbne filen.

- Navne under fem yderligere slovenske betegnelser forblev uopdaget:
  „Toženec" (sagsøgte), „Tožnik" (sagsøger), „Zastavitelj" (pantsætter),
  „Zastavni upnik" (pantekreditor) og „Darovalec" (gavegiver). Navnene
  genkendes nu fuldstændigt.

- Forfatternavnet på en sporet tabelcelle-ændring (indsat, slettet eller
  sammenlagt celle i Word) forblev stående i filen, også når det samme
  navn som kommentarforfatter for længst var fjernet. Det fjernes nu
  også.

- Navne under ni yderligere slovenske betegnelser forblev uopdaget:
  „Najemodajalec"/„Najemnik" (udlejer/lejer), „Zapustnik"/„Dedič"
  (arvelader/arving), „Upnik"/„Dolžnik" (kreditor/skyldner), „Glavni
  dolžnik" (hovedskyldner) og „Skrbnik" (værge/plejer). Navnene
  genkendes nu fuldstændigt.

- Navne under fem slovenske betegnelser forblev uopdaget: „Izvedenec"
  (sagkyndig), „Kupec" (køber), „Prodajalec" (sælger), „Naročnik"
  (ordregiver) og „Izvajalec" (kontrahent). Navnene genkendes nu
  fuldstændigt.

- Navne under fem yderligere litauiske betegnelser forblev uopdaget:
  „Užsakovas" (ordregiver), „Vykdytojas" (kontrahent), „Vežėjas"
  (transportør), „Siuntėjas" (afsender) og „Arbitras" (voldgiftsmand).
  Navnene genkendes nu fuldstændigt.

- Navne under seks yderligere litauiske betegnelser forblev uopdaget:
  „Įgaliotinis" (fuldmagtshaver), „Įgaliotojas" (fuldmagtsgiver),
  „Naudos gavėjas" (begunstiget, forsikring), „Trečiasis asmuo"
  (biintervenient/tredjepart i civilproces), „Ankstesnis nuomininkas"
  (tidligere lejer) og „Naujasis nuomininkas" (ny lejer). Navnene
  genkendes nu fuldstændigt.

- Et bogmærke i ODT-dokumenter (`text:bookmark`) bærer sit navn frit
  angivet, ofte navngivet efter det sted, det peger på (f.eks.
  „Herr_Mueller_Unterschrift") – usynligt for læseren, men ordret i
  filen. Navnet renses nu med.

- Navne under otte yderligere litauiske betegnelser forblev uopdaget:
  „Pareiškėjas" (ansøger), „Suinteresuotas asmuo" (modpart i
  udenretssag), „Ekspertas" (sagkyndig/vurderingsmand), „Bankroto
  administratorius" (kurator), „Valdybos narys" (bestyrelsesmedlem),
  „Direktorius" (direktør), „Palikėjas" (arvelader) og „Įpėdinis"
  (arving). Navnene genkendes nu fuldstændigt.

- Navne under syv yderligere litauiske betegnelser forblev uopdaget:
  „Liudytojas" (vidne), „Vertėjas" (tolk/oversætter), „Notaras"
  (notar), „Dovanotojas" (gavegiver), „Apdovanotasis" (begunstiget),
  „Pirkėjas" (køber) og „Pardavėjas" (sælger). Navnene genkendes nu
  fuldstændigt.

- Navne under seks yderligere litauiske betegnelser forblev uopdaget:
  „Globėjas" (værge/plejer), „Palikimo administratorius" (bobestyrer),
  „Laiduotojas" (kautionist), „Pagrindinis skolininkas" (hovedskyldner),
  „Nuomotojas" (udlejer) og „Nuomininkas" (lejer). Navnene genkendes nu
  fuldstændigt.

- Et navn under den litauiske betegnelse „Ieškovas"/„Atsakovas" (sagsøger/
  sagsøgte som procespart) forblev uopdaget, uafhængigt af om
  efternavnet samtidig var et almindeligt ord (f.eks. „Vilkas" = ulv)
  eller ej. Navnet genkendes nu fuldstændigt.

- En personregisterpost i ODT-dokumenter (bogmærke til
  stikordsregisteret) bar navnet en anden gang i sin egen sorteringsnøgle
  – usynligt i brødteksten, men ordret i det senere genererede register.
  Nøglen renses nu med.

- Diasnavnet og afsnitsnavnet i en PowerPoint-præsentation (synlige i
  udvalgsområdet henholdsvis i diassorteringen) forblev urensede, fordi
  begge hænger som attribut på et element, der ikke er diastekst. Begge
  genkendes nu.

- Et litauisk bindestregs-dobbeltnavn som „Petraitis-Kazlauskas" mistede
  sin anden halvdel, så snart nogen brødtekst stod foran (kun ved
  tekstens begyndelse forblev det fuldstændigt): Efternavnet genkendes
  nu også da helt.

- Et navn under betegnelsen „Cesionar" (kroatisk, cessionar ved
  fordringsoverdragelse) skabte en falsk alarm, fordi selve
  feltbetegnelsen fejlagtigt blev læst som en person. Et navn under den
  russiske betegnelse „Цессионарий" (ligeledes cessionar) forblev
  derimod helt uopdaget. Begge tilfælde er nu rettet.

- Et navn under betegnelsen „Zedent"/„Zessionar" (tysk,
  fordringsoverdragelse) forblev uden erstatning uopdaget, hvis
  efternavnet samtidig var et almindeligt ord (f.eks. „Bauer"). Navnet
  genkendes nu fuldstændigt.

- Et navn under betegnelsen „Darczyńca"/„Obdarowany" (polsk,
  gavegiver/begunstiget i gaveaftalen) forblev uopdaget, hvis efternavnet
  samtidig var et almindeligt ord (f.eks. „Wilk" = ulv). Ligeledes hang
  den rumænske betegnelse „Donatar" (begunstiget) ved et almindeligt
  efternavn selv fast som en formodet navnebestanddel. Begge tilfælde er
  nu rettet.

- Et navn under betegnelsen „Wierzyciel"/„Dłużnik" (polsk,
  fuldbyrdelseskreditor/fuldbyrdelsesskyldner henholdsvis almindelig
  kreditor/skyldner) forblev uopdaget, hvis efternavnet samtidig var et
  almindeligt ord (f.eks. „Wilk" = ulv). Navnet genkendes nu
  fuldstændigt.

- Et navn under betegnelsen „Poręczyciel"/„Dłużnik główny" (polsk,
  kautionist/hovedskyldner i kautionskontrakter) forblev uopdaget, hvis
  efternavnet samtidig var et almindeligt ord (f.eks. „Wilk" = ulv).
  Navnet genkendes nu fuldstændigt.

- Et navn under betegnelsen „Ubezpieczony"/„Ubezpieczający" (polsk,
  forsikrede/forsikringstager i forsikringspolicer) forblev delvist eller
  helt uopdaget, hvis efternavnet samtidig var et almindeligt ord (f.eks.
  „Wilk" = ulv). Ligeledes et navn under „Osiguranik"/„Osiguravatelj"
  (kroatisk, samme roller), dér forsvandt det fuldstændigt sammen med
  fornavnet (f.eks. „Golub" = due). Begge navne genkendes nu
  fuldstændigt.

- Et navn under betegnelsen „Pełnomocnik"/„Mocodawca" (polsk,
  fuldmægtig/fuldmagtsgiver i fuldmagtsdokumenter) forblev uopdaget, hvis
  efternavnet samtidig var et almindeligt ord (f.eks. „Wilk" = ulv).
  Ligeledes et navn under „Opunomoćenik"/„Opunomoćitelj" (kroatisk,
  samme roller), dér forsvandt det endda fuldstændigt sammen med
  fornavnet. Begge navne genkendes nu fuldstændigt.

- Et navn under betegnelsen „Pozwany" (polsk, sagsøgte som procespart)
  forblev uopdaget, hvis efternavnet samtidig var et almindeligt ord
  (f.eks. „Wilk" = ulv). Navnet genkendes nu fuldstændigt.

- Et navn under betegnelsen „Najmoprimac"/„Najmodavac" (kroatisk,
  lejer/udlejer i lejekontrakter) forblev uopdaget, hvis efternavnet
  samtidig var et almindeligt ord (f.eks. „Kovač" = smed). Navnet
  genkendes nu fuldstændigt.

- Et navn under betegnelsen „Pracodawca"/„Pracownik" (polsk,
  arbejdsgiver/arbejdstager som kontraktpart i ansættelseskontrakter)
  forblev delvist uopdaget, hvis efternavnet samtidig var et almindeligt
  ord (f.eks. „Krawiec" = skrædder). Navnet genkendes nu fuldstændigt.

- Ungarn havde i landekataloget kun personkendingerne og momsnummeret:
  Handelsregisternummeret (Cégjegyzékszám) genkendes nu, forudsat at
  feltordet „Cégjegyzékszám" eller forkortelsen „Cg." står umiddelbart
  foran – selve nummeret bærer intet kontrolciffer.

- Estland havde i landekataloget kun Isikukood: Käibemaksukohustuslase
  number (momsnummer på enhver estisk faktura) genkendes nu med
  kontrolciffer.

- Letland havde i landekataloget kun personkoden: PVN reģistrācijas
  numurs for juridiske personer (virksomhedskending på enhver lettisk
  faktura) genkendes nu med kontrolciffer.

- En e-mail med krypteret indhold (S/MIME- eller PGP/MIME-omslag,
  `multipart/encrypted`) blev uden nogen advarsel udgivet som
  tilsyneladende fuldstændigt kontrolleret, selv om dens egentlige
  indhold var krypteret og dermed ukontrolleret. Sådanne mails gør nu som
  et ukontrolleret bilag opmærksom på det.

- Malta manglede i landekataloget: Det maltesiske momsnummer (VAT
  number) genkendes nu.

- Luxembourg manglede i landekataloget: Det luxembourgske momsnummer
  (n° TVA) genkendes nu.

- Et sætningsindledende bulgarsk „Изчакайте" ("Vent!") blev meldt som
  stedangivelse – samme modelgrænse som tidligere ved ungarske, polske,
  tjekkiske og andre opfordringsformer uden egen sprogmodel. Den falske
  alarm udebliver nu.

- Et navn under betegnelsen „Zleceniodawca", „Zleceniobiorca" (polsk),
  „Prestator" (rumænsk), „Naručitelj" eller „Izvođač" (kroatisk) forblev
  delvist eller helt uopdaget, hvis efternavnet samtidig var et
  almindeligt ord (f.eks. „Wilk", „Vuk" = ulv, „Vulpe" = ræv, „Sokol" =
  falk). Navnet genkendes nu fuldstændigt.

- Et navn under betegnelsen „Nadawca" (polsk), „Afsender" (dansk) eller
  „Pošiljatelj" (slovensk) forblev delvist eller helt uopdaget, hvis
  efternavnet samtidig var et almindeligt ord (f.eks. „Sowa" = ugle,
  „Bager" = bager, „Volk" = ulv). Navnet genkendes nu fuldstændigt.

- Et navn under betegnelsen „Gavėjas" (litauisk) eller „Prejemnik"
  (slovensk) forblev delvist eller helt uopdaget, hvis efternavnet
  samtidig var et almindeligt ord (f.eks. „Vilkas" = ulv). Som allerede
  ved „Primatelj" (kroatisk) og „Modtager" (dansk) genkendes navnet nu
  fuldstændigt.

- En rundskrivelse-overskrift som „To All Staff" eller „To All Employees"
  blev fejlagtigt genkendt som personnavn og fjernet. Det forekommer nu
  ikke længere.

- Et navn under betegnelsen „Primatelj" (kroatisk) eller „Modtager"
  (dansk) forblev delvist uopdaget, hvis efternavnet samtidig var et
  almindeligt ord (f.eks. „Golub" = due, „Bager" = bager). Som allerede
  ved „Odbiorca" (polsk) og „Destinatar" (rumænsk) genkendes navnet nu
  fuldstændigt.

- Et fuldstændigt navn i underskriftslinjen på et dansk, norsk eller
  græsk dokument forblev delvist uopdaget, når betegnelsen „Underskrift"
  eller „Υπογραφή" stod alene over navnet – i det græske tilfælde blev
  efternavnet endda genkendt som stedangivelse i stedet for som navn.
  Som allerede ved „Подпись" (russisk) genkendes navnet nu fuldstændigt.

- Tekst på et sidelæns aflagt telefonfoto (den sædvanlige
  højkant-optagelse, der kun via et billeddrejningsmærke vises
  opretstående) kunne overses af tekstgenkendelsen, fordi den hidtil læste
  de rå, liggende billedpunkter. Sådanne fotos drejes nu rigtigt vendt
  før læsning – som allerede tidligere ved ansigtsgenkendelsen.

- Et fuldstændigt navn i underskriftslinjen på et russisk, ukrainsk eller
  litauisk dokument forblev delvist uopdaget, når betegnelsen „Подпись",
  „Підпис" eller „Parašas" stod alene over navnet – for- eller
  patronymnavn faldt væk. Som allerede ved „Potpis" (kroatisk)
  genkendes navnet nu fuldstændigt.

- Et ansigt på et sidelæns aflagt telefonfoto (den sædvanlige
  højkant-optagelse, der kun via et billeddrejningsmærke vises
  opretstående) kunne overses af ansigtsgenkendelsen, fordi den hidtil
  kontrollerede de rå, liggende billedpunkter. Sådanne fotos drejes nu
  rigtigt vendt før søgningen.

- Et fuldstændigt navn i underskriftslinjen på et kroatisk dokument
  forblev delvist uopdaget, når betegnelsen „Potpis" stod alene over
  navnet eller med kolon foran – fornavnet faldt væk, uanset om som egen
  linje eller i „Potpis: Fornavn Mellemnavn Efternavn". Som allerede ved
  „Unterschrift" og „Signature" genkendes navnet nu fuldstændigt.

- Et ægtenavn bag civilstandsforkortelserne „g." (gift) og „enke/enkemand
  efter" forblev hidtil helt uopdaget stående, uanset om i parentes, bag
  komma eller klæbet uden mellemrum („Anna Meier (g. Weber)", „Klaus
  Bauer (enkemand efter Fischer)") – som allerede ved „f." (født)
  genkendes det nu pålideligt.

- Et navn bag prokura-tegningen „ppa." (f.eks. i signaturlinjen i en
  forretnings-e-mail eller et forretningsbrev) forblev ved et
  erhvervsnavnesammenfaldende efternavn som „Bauer" eller „Koch"
  hidtil delvist eller helt uopdaget stående – som allerede ved „u." (på
  vegne af) genkendes det nu pålideligt.

- Nummeret på det polske identitetskort (dowód osobisty) blev kun
  genkendt uden mellemrum mellem serie og nummer („ABS123456"). Netop
  sådan trykker dokumentet dog ikke angivelsen – officielt står der et
  mellemrum imellem („ABS 123456"), og i denne skrivemåde forblev nummeret
  hidtil uopdaget.

- Et animeret PNG (APNG, f.eks. en som PNG i stedet for GIF gemt kort
  skærmoptagelse) blev hidtil kun kontrolleret og renset med sit første
  billede, uden at dette blev meldt – som tidligere ved det animerede
  WebP melder Maskuro nu, at hvert yderligere billede forbliver
  ukontrolleret i resultatet.

- Et animeret WebP-billede (f.eks. fra et skærmbilledeværktøj eller en
  chat-applikation med flere billeder i en fil) blev hidtil kun
  kontrolleret og renset med sit første billede, uden at dette blev
  meldt – som tidligere ved en flersidet TIFF melder Maskuro nu, at hvert
  yderligere billede forbliver ukontrolleret i resultatet.

- Et slovensk dobbelt-fornavn med bindestreg („Ana-Marija Novak") mistede
  sin forreste halvdel, så snart en brødtekstsætning gik forud i
  teksten - samme fejl som tidligere ved polsk. „Ana-" forblev ubelagt i
  klartekst stående, mens resten af navnet allerede var erstattet.

- Et polsk dobbelt-fornavn med bindestreg („Anna-Maria Kowalska") mistede
  sin forreste halvdel, så snart en brødtekstsætning eller en
  præposition som „z"/„od" gik forud - resten af navnet blev erstattet,
  „Anna-" forblev ubelagt i klartekst stående.

- Kasakhiske høflighedsformer „Хабарласыңыз"/„Байланысыңыз" (kontakt os)
  samt serbiske verbformer „Помоћи", „Чекамо" og „Пишите" uden egen
  sprogmodel blev i telefonsætninger fejlagtigt genkendt som personnavn
  eller sted.

- Aserbajdsjansk høflighedsord „Xahiş" (bede om/anmode) uden egen
  sprogmodel blev i telefonsætninger fejlagtigt genkendt som personnavn.

- Indonesiske og malajiske høflighed-/opfordringsord uden egen sprogmodel
  som „Silakan", „Mohon" (indonesisk), „Sila" og „Tolong" (malajisk) blev
  i telefonsætninger fejlagtigt genkendt som personnavn eller sted.

- Usbekisk opfordringsform „Kutamiz" (vi venter) uden egen sprogmodel
  blev i telefonsætninger fejlagtigt genkendt som sted.

- Tyrkiske opfordringsformer uden egen sprogmodel som „Arayınız" (ring)
  og „Bekliyoruz" (vi venter) blev i telefonsætninger fejlagtigt
  genkendt som personnavn.

- Opfordringsformer på flere sprog uden egen sprogmodel (tjekkisk,
  slovakisk, græsk) som „Zavolejte" (ring), „Prosíme" (vi beder) og
  „Περιμένουμε" (vi venter) blev i telefonsætninger fejlagtigt genkendt
  som personnavn eller sted.

- Ungarske og polske opfordringsformer som „Hívjon" (ring), „Kérjük" (vi
  beder), „Várjuk" (vi venter), „Zadzwoń" (ring) og „Czekamy" (vi venter)
  blev i telefonsætninger fejlagtigt genkendt som personnavn eller sted.

- I en nummereret navneliste uden tabelform (f.eks. „1. Robert Brown",
  nedenunder „2. Mary Johnson") blev et navn med visse engelske
  efternavne (bl.a. „Brown", „White", „Green", „Black", „Young") helt
  overset – sprogmodellen havde hæftet nummeret på den følgende linje til
  navnet, hvorved fundet aldrig længere passede nøjagtigt.

- Ved den polske sprogmodel forblev det foranstillede fornavns-initial
  foran et efternavn (f.eks. „J. Kowalski", „A. Nowak") ugenkendt og
  urenset i teksten – kun efternavnet blev erstattet. Andre kontrollerede
  sprog (bl.a. tysk, engelsk, rumænsk, kroatisk, ungarsk, russisk) tog
  allerede tidligere det samme initial med.

- Et personnavn bag en med lille bogstav skrevet titel som „dr.", „ing."
  eller „dipl. ing." blev på ungarsk, rumænsk og kroatisk slet ikke
  genkendt – ikke kun titlen, men hele navnet gik tabt (f.eks. „dr.
  Kovács Béla", „ing. Andrei Popescu", „dipl. ing. Marko Horvat").
- I slovenske mødereferater blev en ren rollebetegnelse foran kolonet
  (f.eks. „Tajnik:", „Podpredsednik:", „Poročevalec:", „Predsedujoči:")
  fejlagtigt genkendt som personnavn, så snart der andetsteds i referatet
  allerede stod et ægte talernavn.
- I russiske mødereferater blev en ren rollebetegnelse foran kolonet
  (f.eks. „Секретарь:", „Докладчик:", „Докладчица:") fejlagtigt genkendt
  som personnavn, så snart der andetsteds i referatet allerede stod et
  ægte talernavn.
- I rumænske mødereferater blev en ren rollebetegnelse med bestemt
  artikel foran kolonet (f.eks. „Secretarul:", „Președintele:",
  „Vicepreședintele:", „Moderatorul:", „Consilierul:") fejlagtigt
  genkendt som personnavn – „Președintele" allerede alene, de øvrige
  desuden, så snart der andetsteds i referatet allerede stod et ægte
  talernavn.
- I kroatiske mødereferater blev en ren rollebetegnelse foran kolonet
  (f.eks. „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:",
  „Predsjedavajući:") fejlagtigt genkendt som personnavn.
- En polsk postboksadresse „Skrytka pocztowa" bag en afsender- eller
  modtagerbetegnelse (f.eks. „Odbiorca: Skrytka pocztowa 45") blev
  fejlagtigt genkendt som personnavn.
- En kroatisk postboksadresse „Poštanski pretinac" bag adressebetegnelsen
  „Adresa:" (f.eks. „Adresa: Poštanski pretinac 45", også med vedhæftet
  „br." for nummeret) blev fejlagtigt genkendt som personnavn.
- Et sted uden yderligere betegnelse i norsk brødtekst (f.eks. „Anna
  Hansen bor i Oslo") blev ikke genkendt – den egne sprogmodel benævner
  der steder for det meste med en egen, hidtil ikke tilknyttet mærkat i
  stedet for det sædvanlige „LOC".
- En dato i ISO-rækkefølgen år-måned-dag med bindestreg eller punktum
  (f.eks. „2024-12-31") blev på visse sprog slet ikke genkendt som dato –
  mest påfaldende på litauisk, hvor officielle skrivelser overvejende
  angiver datoer i denne rækkefølge.
- Et ungarsk momsnummer (közösségi adószám) i den officielt ligeledes
  gyldige, adskillerløse 11-cifrede form (f.eks. „12345678123" i stedet
  for „12345678-1-23") blev ikke genkendt.
- Et polsk skattenummer NIP med adskillerne i grupperingen 3-2-2-3
  (f.eks. „856-73-46-215", som det er sædvanligt på fakturaer fra
  virksomheder og enkeltmandsvirksomheder) blev ikke genkendt – kun
  grupperingen 3-3-2-2 for fysiske personer ramte.
- Et firmanavn under den slovakiske feltbetegnelse „Zamestnávateľ:"
  eller „Názov zamestnávateľa:" (arbejdsgiver/firma) blev ikke genkendt.
- Et firmanavn under den rumænske feltbetegnelse „Angajator:" eller
  „Denumire angajator:" (arbejdsgiver/firma) blev ikke genkendt.
- Et firmanavn under den ungarske feltbetegnelse „Cég:" eller
  „Munkáltató:" (firma/arbejdsgiver) blev ikke genkendt.
- Et firmanavn under den polske feltbetegnelse „Pracodawca:" eller
  „Nazwa firmy:" (arbejdsgiver/firma) blev ikke genkendt.
- Et firmanavn under den slovenske feltbetegnelse „Podjetje:" eller
  „Delodajalec:" (firma/arbejdsgiver) blev ikke genkendt.
- Et firmanavn under den kroatiske feltbetegnelse „Tvrtka:" eller
  „Poslodavac:" (firma/arbejdsgiver) blev ikke genkendt.
- Et udskrevet pengebeløb med lille skrevet valuta (f.eks. „500 euro")
  blev ikke genkendt, kun den store forbogstav („Euro") ramte.
- Efternavnet bag „svoger"/„svigerinde" (f.eks. „Svogeren Bauer modtager
  arven.") blev ikke genkendt.
- Ved en tyrkisk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „34000 İstanbul İstiklal
  Caddesi No: 45") forblev husnummeret urenset stående.
- Ved en slovakisk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „831 01 Bratislava Hlavná 15")
  forblev husnummeret urenset stående.
- Et fødeland uden yderligere betegnelse i et kroatisk formularfelt
  (f.eks. „Zemlja rođenja: Njemačka") blev ikke genkendt.
- Et fødeland uden yderligere betegnelse i et litauisk formularfelt
  (f.eks. „Gimimo valstybė: Vokietija") blev ikke genkendt.
- Et føde- eller bopælsland uden yderligere betegnelse i et polsk
  formularfelt (f.eks. „Kraj: Niemcy") blev ikke genkendt.
- Et statsborgerskabs- eller bopælssted uden yderligere betegnelse i et
  slovensk formularfelt (f.eks. „Državljanstvo: Nemčija") blev ikke
  genkendt.
- Et bopælsland uden yderligere betegnelse i et norsk formularfelt
  (f.eks. „Bosted: Tyskland") blev ikke genkendt.
- Ny indstillingsside „Notifikationer" (tidligere et afsnit i
  „Program"): de tre proceslinje-meddelelser (forhåndsvisning klar,
  behandling færdig, opdatering downloadet) står nu på et eget sted.
- Nyt: Resultatet kan desuden gemmes som ren tekstfil (.txt) eller med
  endelsen .md ved siden af – til videre behandling i en AI eller et
  andet program.
- Ved en kroatisk kontaktangivelse med betegnelsen „Osoba za
  kontakt"/„Kontakt osoba" (f.eks. „Osoba za kontakt: Golub Marko")
  forblev navnet fuldstændigt ugenkendt, hvis efternavnet samtidig var et
  almindeligt navneord (Golub = „due").

- Ved en rumænsk kontaktangivelse med betegnelsen „Persoana de
  contact"/„Persoană de contact" (f.eks. „Persoana de contact: Lup Ion")
  forblev navnet fuldstændigt ugenkendt, hvis efternavnet samtidig var et
  almindeligt navneord (Lup = „ulv") og fornavnet meget kort og generisk.

- Ved en polsk kontaktangivelse med betegnelsen „Osoba
  kontaktowa"/„Osoba do kontaktu" (f.eks. „Osoba kontaktowa: Wilk Adam")
  forblev efternavnet ugenkendt, hvis det samtidig var et almindeligt
  navneord (Wilk = „ulv", Zielony = „grøn").

- Ved en rumænsk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „010061 București Strada
  Victoriei 30") forblev husnummeret urenset stående.
- Ved en serbisk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „11000 Beograd Bulevar Kralja
  Aleksandra 73") forblev husnummeret urenset stående.
- Ved en græsk adresse uden adskillende tegnsætning mellem postnummer+by
  og gade+husnummer (f.eks. „104 32 Αθήνα Ερμού 15") forblev husnummeret
  urenset stående.
- Ved en slovensk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „1000 Ljubljana Slovenska
  cesta 58") forblev postnummeret urenset stående.
- Ved en litauisk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „LT-01100 Vilnius Gedimino
  pr. 9") forblev postnummeret fuldstændigt urenset stående.
- Ved en ungarsk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „1052 Budapest Kossuth Lajos
  utca 12") forblev postnummeret urenset stående.
- Et efternavn bag „arvinger" (f.eks. „Arvingerne Wagner modtog
  meddelelsen rettidigt.") forblev i arve-/boopgørelseskontekst så godt
  som altid ugenkendt.
- Et efternavn bag „søskende" (f.eks. „Søskende Bauer bor i Linz.")
  forblev hidtil så godt som altid ugenkendt – i modsætning til ved
  „familie"/„ægtepar" ramte det ikke kun erhvervsordsammenfaldende navne
  (Koch, Bauer, Richter), men vilkårlige efternavne på dette sted.
- Et efternavn bag „ægtepar" eller "ægtefæller" (f.eks. „Ægteparret Koch
  flytter.") forblev ugenkendt, hvis det samtidig var et almindeligt
  navneord eller en erhvervsbetegnelse (Koch, Bauer, Richter).
- Et almindeligt bestillings-, ordre- eller artikelnummer i det typiske
  grupperingsraster for et skattenummer eller personnummer (f.eks. „030
  4471 2298") blev uden nogen tilhørende betegnelse fejlagtigt sløret som
  et sådant.
- Et bilags-/sagsnummer i formatet „år/løbenummer" (f.eks. i „Faktura nr.
  4/2024/778899") blev af telefonnummer-genkendelsen fejlagtigt sløret
  som telefonnummer.
- Et navn bag „Hr."/„Fru" med en flerords akademisk titelkæde foran
  („Hr. Dr. med. Weber", „Hr. Prof. Dr. Krause") forblev hidtil
  fuldstændigt ubeskyttet stående – genkendt blev hidtil kun ét enkelt
  titelord mellem tiltale og navn.
- Et retsligt sagsnummer i det klassiske format med afdelings-/senats-
  forkortelse („4 Ca 1523/24", „J.nr.: 7 O 234/25") forblev hidtil
  fuldstændigt ubeskyttet stående – heller ikke den sædvanlige kortform
  „J.nr."/„Sagsnr." blev genkendt ved siden af den udskrevne betegnelse.
- Et kreditkortnummer, der midt i sin firergruppering blev adskilt af et
  linjeskift – f.eks. i en smal tabelkolonne –, forblev hidtil
  fuldstændigt ubeskyttet stående.
- Et skattemæssigt identifikationsnummer, der midt i sin gruppering blev
  adskilt af et linjeskift – f.eks. i en smal tabelkolonne eller et
  formularfelt –, forblev hidtil fuldstændigt ubeskyttet stående.
- Et personnummer, der midt i sin gruppering blev adskilt af et
  linjeskift – f.eks. i en smal tabelkolonne –, forblev hidtil
  fuldstændigt ubeskyttet stående, end ikke delvist erstattet.
- Et husnummer med interval som „12a-14b" eller „3-5" blev kun halvt
  erstattet – anden del bag bindestregen forblev åben stående i
  resultatet.
- Et stelnummer (FIN/VIN), der midt i sine 17 tegn blev adskilt af et
  linjeskift, mellemrum eller bindestreg – f.eks. i en smal tabelkolonne
  eller et køretøjsdokument-felt –, forblev hidtil fuldstændigt
  ubeskyttet stående.
- En brev-/mailhilsen som „Kære Anna!" eller „Kære Hans" – uden komma
  efter navnet, den hyppigste form i afslappede mails – lod navnet
  forblive fuldstændigt ubeskyttet, også i det fulde dokument med
  brødtekst og hilsenformular nedenunder.
- Samme hul ramte også de afslappede chat-/mailhilsener „Hej Anna!", „Hi
  Anna!", „Hallo Anna!" og „Halløj Anna!" uden komma – navnet forblev
  ligeledes fuldstændigt ubeskyttet stående.
- En ren signaturblok, der begynder direkte med „Mvh" eller "Kærligst" –
  f.eks. kopieret fra udklipsholderen, uden foranstående sætning – lod
  navnet nedenunder forblive fuldstændigt ubeskyttet.
- Et felt med flere personer, f.eks. „Pårørende: Kaczmarek, Piotr (søn),
  Kaczmarek, Anna (hustru)", smeltede begge navne sammen med
  parentesangivelsen til ét eneste, alt for langt fund – det andet navn
  forblev til dels ubeskyttet i resultatet.
- En gade uden „-gade"/„-vej"-endelse – som det er sædvanligt på landet,
  f.eks. „Am Marktplatz 5" eller „Im Grund 12" – forblev ugenkendt, hvis
  en postnummer-by-linje fulgte efter, f.eks. i en folkeregisterattest:
  „Ny adresse: Am Weidengarten 17, 54295 Trier" mistede gaden
  fuldstændigt, kun postnummeret blev fjernet.
- Et navn bag en sammensat feltbetegnelse med skråstreg (f.eks.
  „Navn/Fornavn: Bauer Klaus") blev delvist ikke genkendt – et
  flertydigt efternavn som „Bauer" forblev uden feltbelæg uopdaget.
  Samme hul ramte kombifelter som „Postnr./By: 04109 / Leipzig". Det
  samme gjaldt kombifelter med udskrevet forbindelsesled i stedet for
  skråstreg, f.eks. „For- og efternavn: Bauer Klaus" eller „Efternavn
  hhv. fornavn: …".
- En fødselsdato i formen „Fødselsdato: …" og en dødsdato i formen
  „Dødsdato: …" eller „Dato for dødsfald: …" blev ikke genkendt – kun
  „Fødselsdato: …" henholdsvis „Dødsdato: …" ramte.
- En vielsesdato i formen „Dato for vielse: …" eller „Dato for
  bryllup: …" blev ikke genkendt – kun „Vielsesdato: …",
  „Bryllupsdato: …" og „Dato for indgåelse af ægteskab: …" ramte, selv om
  skilsmisse-, statsborgerskabs- og registreringsdato længe havde kendt
  den samme „Dato for X"-form.
- En skilsmissedato i formen „Dato for skilsmisse: …" blev ikke
  genkendt – kun „Skilsmissedato: …" og den efterstillede verbform
  ramte, selv om statsborgerskabs- og registreringsdato havde kendt den
  samme „Dato for X"-form fra begyndelsen.
- En registreringsdato (for registreret partnerskab) blev hidtil slet
  ikke genkendt – hverken med betegnelse („Registreringsdato: …", „Dato
  for registreret partnerskab: …") eller i brødtekst („… blev
  registreret som partnere den …"). Nu erstattes den ligesom fødsels-,
  vielses-, skilsmisse- og statsborgerskabsdato som en egen angivelsesart.
- En statsborgerskabsdato blev hidtil slet ikke genkendt – hverken med
  betegnelse („Statsborgerskabsdato: …") eller i brødtekst („… blev
  statsborger den …"). Nu erstattes den ligesom fødsels-, vielses- og
  skilsmissedato som en egen angivelsesart.
- En skilsmissedato blev hidtil slet ikke genkendt – hverken med
  betegnelse („Skilsmissedato: …") eller i brødtekst („Ægteskabet blev
  opløst den …"). Nu erstattes den ligesom fødsels-, døds- og
  vielsesdato som en egen angivelsesart.
- En vielsesdato bag slægtsforskningens ægteskabstegn „⚭" uden betegnelse
  blev ikke genkendt, selv om fødsels- og dødsdato i samme linje via
  stjerne og kors allerede blev genkendt – nu genkendes også vielsesdatoen.
- En dødsdato bag dødsannoncens kors uden betegnelse
  („*03.06.1940 †21.11.2023") blev ikke genkendt, selv om fødselsdatoen
  foran via slægtsforskningens stjerne allerede blev genkendt – nu
  genkendes også dødsdatoen.
- Efternavn foran fornavn ved slutningen af en emne-/sagslinje med
  foranstående sagtekst og skillestreg („Emne: Reklamation - Bauer,
  Anna") blev ved et erhvervsnavnesammenfaldende efternavn ikke
  genkendt – nu genkendes det.
- Ansøger- og anmodernumre bag deres betegnelse („Ansøgernummer:
  4471829", „Anmodernummer: 7654321") faldt helt igennem genkendelsen –
  nu genkendes de.
- Erstat slører ikke længere, når der ikke er plads til en læselig
  pladsholder – en for lille pladsholder skrives nu mindre i stedet for
  at blive til en tom bjælke, så længe der overhovedet er plads
  tilbage. Nyt desuden: Om et fundsted på et billede (brevhoved,
  scanningsbaggrund) betegnes eller kun sløres, kan nu indstilles
  uafhængigt af den øvrige resultatart. Og et fundsted på et billede, der
  fjernes helt, blev betegnet, som om billedet blev stående – pladsholderen
  stod lys på en grund, der aldrig blev sløret, og forsvandt dermed
  usynligt på det nu hvide papir.
- Et fundsted på et **beholdt** billede blev ved erstatning altid sløret
  sort-hvid, uafhængigt af den valgte fremtoning (kategorifarver,
  regnbue …) – synligt som et brud mellem farvede etiketter i brødteksten
  og sorte bjælker på brevhovedet. Billedgrunden følger nu samme farve
  som pladsholderen ved siden af.
- Genkendelsen af køretøjets identifikationsnummer (FIN/VIN) markerede
  hver 17-cifret alfanumerisk kode uden I/O/Q betingelsesløst som
  stelnummer – også ordre-, serie- og licensnøglenumre, der tilfældigvis
  har samme form. Nu tæller den kun med et kontekstord i nærheden
  („FIN", „VIN", „Stelnummer", „Chassis" og lign.).
- I ticket-/kalendersystemer rev navnegenkendelsen efter „Assigned to"/
  „Closed by" og lign. det næste feltord med, hvis det stod i samme
  linje uden adskiller direkte efter („Assigned to Max Mustermann
  Priority High" blev til „Max Mustermann Priority"). I
  Git-commit-hoveder rev navnegenkendelsen ligeledes den **næste**
  trailer-nøgle med, hvis to linjer kun med ét mellemrum i stedet for
  linjeskift hang sammen („Author: julia bergmann Reviewed-by: …" blev
  til „julia bergmann Reviewed-by"). Begge bremser tilføjet.
- Navnet bag „p.A.", „ATT"/„c/o", „på vegne af" og „f." rev et direkte
  følgende afdelingsord med ind i samme fund, hvis det stod uden
  adskiller i samme linje („p.A. Max Mustermann Bogholderi" blev til
  „Max Mustermann Bogholderi", „på vegne afMax Mustermann Salg" til „Max
  Mustermann Salg"). Samme bremse som ved „Assigned to"/Git-trailere nu
  også tilføjet her.
- En betegnet IBAN direkte over BIC-, registrerings- eller
  SWIFT-linjen rev dens betegnelse med ind i sit eget fund, fordi „BIC"
  og lignende selv lignede endnu en talblok – af „IBAN: DE89 … 0130 00"
  og linjen nedenunder blev der ét eneste, alt for vidtrækkende fund, og
  betegnelsen på den næste linje forsvandt med under rensningen. Berørt
  var næsten enhver bankforbindelse med IBAN og BIC under hinanden.
- Fundpanelet siger nu **hvor** en pladsholder står, som det ikke kan
  finde på siden. To tilfælde meldte hidtil kun „ikke fundet", selv om
  erstatningen fandt sted: Står pladsholderen i usynlig sidetekst –
  f.eks. et links henvisningsadresse, en anmærkning eller et
  formularfelt –, bærer linjen nu det som egen oplysning („i
  sidetekst"), og klikket forklarer det. Og blev pladsholderen skrevet
  forkortet på grund af pladsmangel („[N382]" i stedet for „[NAM382]"),
  springer klikket på den lange linje nu til kortformens sted og nævner
  omdøbningen; tilknytningen forbinder hermed udtrykkeligt begge linjer
  med hinanden.
- Står samme erstatningsværdi flere gange i dokumentet, springer hvert
  yderligere klik på panellinjen i en cirkel til det næste fundsted – også
  over sidegrænser; statuslinjen tæller med („Fundsted 2 af 4"), og det
  netop tilgåede sted er kraftigere indrammet end de øvrige. Og hvis en
  pladsholder kun står i fundlisten, men ingen steder i dokumentet (fordi
  stedet gik op i en overlappende erstatning), siger statuslinjen det nu
  i stedet for at klikket forbliver tavst virkningsløst.
- Et forkortet fornavn bag „til" eller "for" genkendes nu pålideligt som
  navn – „Overførsel til M. Wagner" og „Faktura for M. Wagner" forblev
  hidtil ofte urensede stående, mens det samme navn med en anden
  betegnelse foran (f.eks. „Betalingsmodtager:") allerede blev fundet.
  Berørt var især kontoudtogs- og bogføringslinjer.
- „Tiltalt"/„Sigtet" gælder nu som navnefelt: Stod et navn i
  straffesagsdokumenter direkte bag en af disse betegnelser, blev det
  hidtil for omkring halvdelen af de kontrollerede navne slet ikke
  genkendt – hverken for- eller efternavn.
- Det sted, der klikkes på i fundpanelet, indrammes nu blåt i stedet for
  markeret gult – på de farvede kontrolampel-flader var fundets gule
  farve ikke til at skelne. Desuden finder klikket nu også
  flerords-erstatningsværdier (opdigtede navne, maskerede numre): Hidtil
  forblev det virkningsløst ved sådanne linjer, fordi fundstedet kun blev
  søgt ord for ord.
- Adoptiv-, pleje- og stedforældre („adoptivfar", „plejemor", „stedfar"
  og flere) genkendes nu som navnefelt, navnet faldt tidligere urenset
  igennem
- Talrige tabeller og lister forkastes ikke længere fejlagtigt: Blev et
  kort tal (f.eks. en som telefonnummer fejllæst del af kundenummer)
  erstattet, meldte slutkontrollen samme cifferfølge som en resterende
  angivelse, også når den andetsteds kun tilfældigt sad i et helt andet
  nummer – og leverede da slet intet resultat. Et tal tæller nu kun som
  rest, hvor det står som selvstændigt tal.
- Civilstandsattester: „Far:"/„Mor:" genkendes nu som navnefelt,
  forældrenavnet faldt tidligere urenset igennem
- Yderligere familieroller („gudfar/-mor", „bedstefar/-mor", „ægtefælle",
  „samlever", „onkel", „tante") genkendes nu som navnefelt, navnet faldt
  tidligere urenset igennem
- Det tyske registreringsnummer (bankleitzahl) genkendes nu også
  officielt grupperet ("370 400 44", "370.400.44", "370-400-44",
  "370/400/44"), ikke længere kun som otte sammenhængende cifre.
- Det tyske pensionsforsikringsnummer genkendes nu også med punktum,
  bindestreg eller skråstreg mellem de fem blokke ("65-170839-J-08-8",
  "65.170839.J.08.8"), ikke længere kun med mellemrum.
- Hovedvinduet fremkommer hurtigere: Genkendelsesbibliotekerne (Presidio
  samt sprogmodel-underbygningen) blev hidtil allerede indlæst ved
  vinduesopbygningen – på Windows omkring fire sekunder, før overhovedet
  noget var at se. De indlæses nu fuldstændigt i baggrunden; knappen
  „Rens" bliver som hidtil først fri, når alt er klar.
- Office-dokumenter med mange billeder eller videoer skrives hurtigere:
  Allerede komprimerede medier gemmes i resultatpakken i stedet for
  nytteløst at blive komprimeret en anden gang – det sparede hidtil ikke
  en byte og gjorde JPEG'er snarere større.
- Regneark og andre dokumenter af mange små tekstenheder kontrolleres
  hurtigere: Sproggenkendelsen behandler nu alle celler og afsnit i et
  dokument i ét gennemløb i stedet for enkeltvis – ved bevisligt samme
  fund (400 celler: fra omkring 4,7 til 2,5–3,5 sekunder).
- Listeagtige PDF-sider (registre, positionslister) er betydeligt
  hurtigere ved indsættelse af pladsholderne: Pladssøgningen pr.
  betegnelse kørte hidtil over alle ord på siden – nu kun over
  linjeomgivelsen, ved bevisligt samme resultat (på en side med 300
  betegnelser omkring seksten gange hurtigere).
- Billedrige dokumenter sparer flere unødvendige arbejdstrin pr. billede:
  Optælling af ansigter og koder på PDF-sider afkoder ikke længere
  sidebilledet dobbelt, kontrollen for metadata dekrypterer slet ikke
  længere et rent billede, pixelerede billeder skrives med den normale
  i stedet for den langsomste PNG-kompression (samme størrelse, en
  tredjedel af tiden), og uden indstillet vandmærke bortfalder den
  nytteløse genskrivning af hele PDF'en til sidst.
- Indscannede PDF'er med tilkoblet tekstgenkendelse er betydeligt
  hurtigere igennem: Hver side blev hidtil rendret to gange i fuld
  opløsning (én gang til læsning, én gang til rastrering) – aftrykket
  genbruges nu. Og på Windows/Linux læser tekstgenkendelsen striberne af
  en stor scanning i ét gennemløb i stedet for med en egen programstart
  pr. stribe.
- Store dokumenter renses betydeligt hurtigere: Sammenligningen af
  allerede fundne værdier voksede hidtil med antallet af fundsteder (en
  64-KB-tekstblok kostede ved slutningen af en stor fil omkring et
  sekund kun til dette, nu en tresindstyvendedel), og søgningen efter
  firma-selskabsformer kørte med alle ~280 katalogformer over hvert
  tekststed (nu omkring tyve gange hurtigere, ved bevisligt samme fund).
- Et navn direkte efter „Bedste hilsner"/„De bedste ønsker" uden
  foranstående tekst eller tegnsætning blev slet ikke genkendt – en ren
  signaturblok uden brødtekst foran lod navnet forsvinde sporløst.
- Et adressefelt ved dokumentets begyndelse med et
  erhvervsnavnesammenfaldende efternavn („Bauer Anna", „Koch Stefan" som
  første linje over gade og by) forblev hidtil delvist ugenkendt eller
  blev klassificeret som stedangivelse i stedet for person – uden
  foranstående sætning manglede sprogmodellen den sætningsopbygning, der
  ellers lader „Bauer" genkendes som navn og ikke som erhverv.
- Et navn bag underskriftsmærket „u." med et
  erhvervsnavnesammenfaldende efternavn foran fornavnet („u. Bauer Anna"
  ved slutningen af en afgørelse eller dom) forblev hidtil ufuldstændigt
  genkendt – kun fornavnet blev fundet, efternavnet forsvandt sporløst.
- Et navn direkte bag et kundenummer, kontraktnummer eller lignende
  identifikationsnummer uden egen linje („Kontraktnummer 55219 Bauer
  Anna", „Kundenr. 4711 Bauer Anna") blev ved et
  erhvervsnavnesammenfaldende efternavn hidtil ufuldstændigt eller slet
  ikke genkendt.
- Symbolet i macOS-menulinjen er nu en skabelon, der ligesom
  nabosymbolerne tilpasser sig lys- og mørketilstand – med de to
  udstansede bjælker forbliver det hermed genkendeligt som Maskuro.
  Kører udklipsholder-vagten, viser det en fritstående prik ved
  skjoldets spids.
- Et klik i fundpanelet fører nu også i anonymiserende drift til
  fundstedet: skift side, rul ind i billedet, marker gult. Hidtil forblev
  klikket der virkningsløst, fordi det stadig anså pladsholderne for
  nummerløse – siden hvert fundsted bærer sit eget nummer, er stedet
  entydigt. Kun ved den faktisk nummerløse pladsholder forklarer
  statuslinjen fortsat, hvorfor intet springmål kan bestemmes.
- Den første lagring i editoren til efterretning (Ctrl+S eller
  diskette-knappen) spørger nu om stedet, som „Gem som …" –
  forudfyldt med originalens mappe og resultatnavnet. Hidtil havnede
  filen tavst ved siden af originalen. Den, der allerede har valgt
  aflæggelsesstedet forinden via statuslinjen, spørges ikke igen; hver
  yderligere lagring skriver som hidtil videre på samme fil.
- Melder sikkerhedskontrollen før lagring et påfaldende sted, fører
  „Tilbage til kontrol" nu derhen: Det første fundsted rulles ind i
  billedet og indrammes rødt, statuslinjen nævner det. Hidtil stod man
  alene med sidetal og punktkoordinater. Fra hovedvinduet åbnes til
  formålet editoren på stedet. Også ved henvisningen om et afvigende
  sidetal fører knappen nu derhen – til den første side, der kun findes
  i ét af de to dokumenter.
- Den, der stiller forhåndsvisningen om til „Ved siden af hinanden i to
  spalter", får nu af sig selv et vindue, hvori begge baner passer –
  hidtil klemte de sig ind i den gamle bredde, indtil man selv trak.
  Der udvides højst til skærmkanten og forsmalles aldrig tilbage; en
  selv trukket bredde forbliver stående.
- Efternavn og fornavn i adskilte tabelkolonner (f.eks. „Efternavn |
  Fornavn" i en tilmeldingsbekræftelse eller en CSV-eksport) forblev
  åbne – hver celle for sig lignede for genkendelsen et vilkårligt ord
  uden navnesammenhæng. Genkendes nu.
- Navn og fornavn på bagsiden af et EU-kortkørekort forblev åbne – de
  står der bag de officielle feltkoder „1." og „2." i stedet for bag et
  dansk ord, og netop det lod dem være ugenkendte. Genkendes nu, når
  kørekortnummeret (feltkode „5.") står ved siden af.
- Fornavnet på køretøjsejeren i registreringsattesten forblev åbent – det
  står bag den officielle feltkode „C.1.2" i stedet for bag et dansk ord
  som „Fornavn", og netop det lod det være ugenkendt. Efternavn og
  fornavn under feltkoderne C.1, C.1.1 og C.1.2 genkendes nu.
- Den første linje af den maskinlæsbare zone (MRZ) på pas eller ID-kort
  forblev åben – den bærer navnet i formatet „EFTERNAVN<<FORNAVN" og
  slap også med den nye MRZ-genkender for kontrolciffer-linjen helt
  igennem. Et fund tæller nu kun, hvis
  direkte ved siden af en kontrolciffer-gyldig anden MRZ-linje står –
  selve navnelinjen har ikke selv noget kontrolciffer.
- Den anden linje af den maskinlæsbare zone (MRZ) på pas eller ID-kort
  forblev fuldstændigt ugenkendt – den indeholder pasnummer, fødsels- og
  udløbsdato i klartekst, men ramte ikke en eneste eksisterende
  genkender. En egen genkender kontrollerer nu de fire ICAO-kontrolcifre.
- En nummerplade uden noget mellemrum til betegnelsen forblev åben –
  „NummerpladeM-AB1234" eller „RegnrM-AB1234" blev slet ikke genkendt,
  fordi den underliggende nummerpladekontrol kræver et ikke-ordtegn foran
  nummerpladen. Berørte køretøjsangivelser, hvor der ikke står noget
  mellemrum mellem feltord og nummerplade.
- Et telefonnummer uden noget mellemrum til betegnelsen forblev åben –
  „Mobilnummer0171/2345678" eller „Tlf0171/2345678" blev slet ikke
  genkendt, fordi den underliggende telefonnummerkontrol kræver et
  mellemrum eller tegnsætning foran nummeret. Berørte kontaktangivelser,
  hvor der ikke står noget mellemrum mellem feltord og nummer.
- Et fødenavn bag forkortelsen „f." blev slet ikke genkendt – „Julia
  Bergmann (f. Weber)" fandt kun „Julia Bergmann", punktummet i „f." lod
  sprogmodellen springe det følgende navn helt over. Berørte
  personangivelser med fødenavn i parentes eller bag komma.
- Fornavnet foran et kaldenavn i anførselstegn forblev åbent, når tiltale
  og titel stod sammen foran – „Hr. Dr. Klaus "KP" Peters" gav kun
  „Peters", „Klaus" forblev læseligt stående. Berørte underskrifter og
  kontaktangivelser med titel og kaldenavn.
- Et navn bag den punktumløse kortform „ATT"/„c/o" (att.) blev slet ikke
  genkendt – i modsætning til ved „att." med punktum rev den manglende
  sætningsstruktur navnet med væk. Berørte adresser uden punktum i
  forkortelsen.
- Et navn bag „p.A." (per adresse) blev slet ikke genkendt – punktummet i
  forkortelsen lod sprogmodellen helt springe navnegenkendelsen over.
  Berørte fakturaer og ansøgninger med samleadresse.
- Et navn bag punktumløst klæbet „på vegne af"/"i.st.f." (i stedet for)
  blev slet ikke genkendt, f.eks. „på vegne afRobert Lang" uden
  mellemrum – samme sætningsopbygningsfejl som ved „p.A.". Berørte
  underskriftslinjer og mailsignaturer i repræsentationstilfælde.
- En ren fremmødeliste med opremsningstegn uden nogen yderligere angivelse
  („- Max Mustermann", også med punktum ved linjens slutning) mistede
  alle navne til den samme bremse, der egentlig kun skal beskytte
  sagopremsninger som „- Farve: Blå". Sådanne lister genkendes nu.
- Filer, der ikke længere kunne renses, kan renses igen. En værdi, der
  allerede var erstattet af genkendelsen, kunne genfindes i sit eget,
  allerede erstattede mærke som „[SVNR1]" – slutkontrollen forkastede da
  en fejlfrit renset fil. Desuden renses en telefonhenvisning i en
  CSV-tabel nu med, og den, der begrænser søgningen til enkelte arter,
  får det nu ens overalt i dokumentet – også i alternativteksten til et
  billede, en Excel-overskrift, en valgliste eller et HTML-attribut.
- Et navn bag e-mail-overskriften „To:" (eller „To" uden kolon) blev ikke
  genkendt, fordi en fremmed sprogmodel læste hele linjen som ét eneste
  ubemærkelsesværdigt fund og slugte navnet deri fuldstændigt – i
  modsætning til ved „Cc:", „Bcc:" eller „From:" foran samme navn. Et
  navn bag „To" findes nu pålideligt.
- Vielsesdatoen kunne ikke behandles som dato i egne regler
  („forskyd" blev afvist med „findes kun for datoangivelser"), manglede i
  gruppetilknytningen af fundarterne – hvormed det ikke kunne slås fra
  via mærkerne „Hvad der søges efter" – og fik i stedet for en kort
  forkortelse som ved dødsdatoen den fulde ordlyd som pladsholder.
  Rettet for alle seks forkortelses-/betegnelsestabeller.
- En i forhåndsvisningen bevidst fravalgt værdi kunne alligevel sløres et
  andet sted: Fravalgte man f.eks. en mailadresse, forblev selve
  adressen ganske vist stående, men dens lokale del uden domæne blev
  erstattet, så snart den dækkede sig med det udledte brugernavn på en
  yderligere valgt person („anna.musterfrau@beispiel.de" ved siden af
  „Anna Musterfrau"). En fravalgt ordlyd forbliver nu tabu i hele
  dokumentet, uafhængigt af hvilken fundart den stammer fra.
- En fødselsdato forblev ugenkendt, hvis en familiebog eller
  civilstandsattest førte den under en fælles overskrift med
  fødestedet („Fødselsdato, fødested: 19.11.1982, Steyr") – det andet
  feltord mellem „Fødselsdato" og datoen lod genkendelsen indtil da falde
  helt igennem.
- Et allerede genkendt telefonnummer forblev læseligt i sin forkortede
  bekræftelsesform, hvis det andetsteds i samme dokument kun blev nævnt
  med de sidste fire cifre („kan nås på nummeret ...5678",
  „tilbagekald på ...5678") – samme byggeform som ved IBAN og
  kreditkort.
- Et allerede genkendt kreditkortnummer forblev læseligt i sin forkortede
  bekræftelsesform, hvis det andetsteds i samme dokument kun blev nævnt
  med de sidste fire cifre („Dit kreditkort slutter på ...0366") – samme
  byggeform, sædvanlig i betalingsbekræftelser, som ved IBAN.
- En allerede genkendt IBAN forblev læselig i sin forkortede
  bekræftelsesform, hvis den andetsteds i samme dokument kun blev nævnt
  med de sidste fire cifre („IBAN'en slutter på ...3201") – en byggeform
  sædvanlig i bekræftelses-e-mails.
- En taler i et chat- eller mødereferat forblev ugenkendt, hvis der stod
  en tiltale foran vedkommendes navn („Hr. Bauer: …", „Fru Koch: …") – og
  ramte dermed ofte også den næste talerlinje i samme referat med, fordi
  for få genkendte linjer forblev til overhovedet at vurdere dokumentet
  som et referat.
- En fødselsdato forblev ugenkendt, hvis feltordet „født" stod BAG datoen
  i stedet for foran („Barnet blev født den 14.01.2026") – sådan
  formulerer f.eks. en barselsattest barnets fødselsdato. Hidtidige
  mønstre forudsatte altid feltordet foran datoen.
- En formularbetegnelse med et reaktions- eller flueben-tegn direkte
  foran („Kontaktperson 😊:", „Kontaktperson ✓:") blev ikke længere
  genkendt som betegnelse, og navnet nedenunder eller derefter blev
  derved delvist kun ufuldstændigt fundet (f.eks. kun efternavnet ved
  „Mayer Roman").
- Samme hul ramte også særligt beskyttelsesværdige angivelser efter
  GDPR-artikel 9 (religion, sundhed, fagforening): Et reaktionstegn
  direkte foran adskilleren eller linjeskiftet („Trosretning 😊:
  romersk-katolsk") lod betegnelsen falde helt igennem, og angivelsen
  forblev fuldstændigt ugenkendt stående.
- En adresse med bindestregs-dobbeltnavn i byen (f.eks. „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") mistede postnummeret
  fuldstændigt, selv om selve byen blev genkendt og sløret – på et
  køretøjsdokument eller anskrivelse forblev postnummeret således
  læseligt stående.
- En tabelkolonne uden kolonneafstand (ægte PDF-tekstudtræk) kunne under
  en navnekolonne også sløre to tilfældigt ved siden af hinanden stående
  store bogstaver fejlagtigt som person, f.eks. to stednavne i en
  datalinje; det er nu kun tilfældet, hvis intet andet fund på samme
  sted allerede genkender noget andet.
- Samme navnekolonne slørede i samme linjeform også to sprogmodellen
  ukendte sagord (f.eks. „Frontend Backend", „Turbo Modul") fejlagtigt
  som person, fordi intet andet fund der udløste bremsen; nu kræver den
  desuden, at mindst ét af de to ord selv læses af sprogmodellen som et
  egennavn.
- Det tyske pensionsforsikringsnummer blev i sin officielle fulde
  gruppering (f.eks. „65 170839 J 08 8" – som det står på
  socialsikringskortet og lønsedlen) ikke genkendt og forblev stående i
  originalen; genkendt blev kun den kompakte skrivemåde og den kun til
  bogstavet grupperede form.
- Det skattemæssige identifikationsnummer blev i sin officielle
  skrivemåde (gruppering 2-3-3-3, f.eks. „48 836 075 988" – som det står
  på enhver ægte skatteafgørelse og enhver meddelelse fra det tyske
  forbundscentralkontor for skatter) slet ikke genkendt og forblev
  stående i originalen; kun den sjældnere gruppering 3-3-3-2 var dækket.
- Det nordrhein-westfalske skattenummer (f.eks. „221/5147/0815", med
  firecifret i stedet for trecifret anden gruppe) blev slet ikke
  genkendt i skatteafgørelser og forblev stående i originalen – enhver
  anden delstat var allerede dækket.
- Ved ansættelseskontrakter blev et navn bag betegnelsen
  „Arbejdsgiver:" fuldstændigt overset, så snart efternavnet samtidig var
  et almindeligt ord (f.eks. „Bauer Anna") – „Arbejdsgiver" står både som
  navne- og som firmabetegnelse i listen, og firmatilknytningen
  overskrev navnetilknytningen.
- I en lejekontrakts hoved med betegnelserne „Udlejer:"/„Lejer:" blev et
  efternavn, der samtidig var et almindeligt ord (f.eks. „Bauer"),
  overset – kun fornavnet forblev genkendt. Nummererede lejere
  („Lejer 1:", „Lejer 2:") var yderligere berørte, også ved navne uden
  denne flertydighed.
- I et retsprotokol med betegnelserne „Vidne:"/„Sagsøger:"/„Sagsøgte:"
  (også med tælling, „Vidne 1:", „Vidne 2:") blev et efternavn, der
  samtidig var et almindeligt ord (f.eks. „Bauer"), ligeledes overset –
  kun fornavnet forblev genkendt.
- Ved skifteattest, fuldmagt, betalingspåkravsprocedure og købsaftale
  blev et efternavn, der samtidig var et almindeligt ord (f.eks.
  „Bauer"), overset bag betegnelser som „Arvelader:", „Arving:",
  „Fuldmagtsgiver:", „Fuldmægtig:", „Modpart:", „Skyldner:",
  „Kreditor:", „Køber:", „Sælger:", „Legatar:" eller
  „Bobestyrer:" – dels forblev kun fornavnet genkendt, dels faldt hele
  navnet væk.
- Ved en flerpartsliste foran retssagsbetegnelsens skilletegn „./."
  (f.eks. „Sand, Werner og Huber, Anna ./. Wechsler, Martina") forblev
  den første part umaskeret – kun den part, der grænsede umiddelbart op
  til „./.", blev genkendt.
- I retssagsbetegnelsens skilletegn „./." (f.eks. „Sand./.Wechsler") blev
  navnet efter tegnet fuldstændigt overset, hvis der ikke stod noget
  mellemrum der – kun med mellemrum foran og bagved ramte genkendelsen.
- Efternavnet „Wahr" blev fuldstændigt overset, når det stod alene
  (f.eks. „Fru Wahr behandler din sag.") – ordet står tilfældigvis også i
  listen over almindelige tyske ord, som ellers filtrerer navnefund fra
  sætninger som „Das ist wahr." (det er sandt).
- Efternavne som „Los", „Weit", „Rund" eller „Hoch" blev fuldstændigt
  overset, når de stod alene (f.eks. „Hr. Hoch overtog ledelsen.") – alle
  fire ord står tilfældigvis også i listen over almindelige tyske ord,
  som ellers filtrerer navnefund fra sætninger som „Rund einhundert
  Gäste kamen zur Feier." (omkring hundrede gæster kom til festen).
- Efternavne som „Ganz" eller „Recht" blev fuldstændigt overset, når de
  stod alene (f.eks. „Hr. Ganz underskrev kontrakten.") – begge ord står
  tilfældigvis også i listen over almindelige tyske ord, som ellers
  filtrerer navnefund fra sætninger som „Ganz genau, das stimmt." (netop,
  det stemmer).
- Et formularfelt med en stjerne eller et hævet fodnotetal bag
  betegnelsen (f.eks. „Trosretning*: romersk-katolsk" eller
  „Religionstilhørighed¹: evangelisk") blev ikke genkendt og forblev
  stående i klartekst – kun formen uden dette tegn ramte.
- Samme felt forblev fortsat i klartekst stående, hvis der ligefrem stod
  to fodnotetegn bag betegnelsen (f.eks. „Trosretning**:
  romersk-katolsk" eller „Fagforening¹²: 3F").
- Et versionsnummer som „Softwareversion 4.2.1.19" eller „Firmware Build
  2.0.4.11" sløres ikke længere fejlagtigt som IP-adresse. Det samme
  gælder nu for bilags- og sagsnumre som „Fakturanummer 10.20.30.40"
  eller „Ordrenummer 7.8.9.10".
- To IBAN'er direkte under hinanden (f.eks. egen og en udenlandsk
  forretningspartners i fakturahovedet) blev ikke længere begge
  genkendt – den anden forblev ubemærket stående.
- En betegnet IBAN rev til tider det følgende ord i sætningen med
  ("Bankforbindelse AT61 … belastes" blev sløret helt ind i "belastes"),
  så snart det følgende ord var skrevet med lille bogstav –
  klartekstresten ved siden af forblev hermed urørt stående.
- Liechtensteinske adresser genkendes nu („FL-9490 Vaduz"), ligesom
  hidtil allerede tyske, østrigske og schweiziske.
- Pasnummer genkendes nu bag sin betegnelse og fjernes (f.eks.
  „Pasnummer: C01X00T471").
- Opholdstilladelses- og folkeregisterattestnummer genkendes nu bag sin
  betegnelse og fjernes.
- Et identifikationsnummer bag sin betegnelse genkendes nu også, når en
  tankestreg i stedet for et kolon adskiller (f.eks. „Kundenummer –
  K903944").
- En som „IBAN" eller „kontonummer" betegnet bankforbindelse genkendes
  nu også, når en tankestreg i stedet for et kolon adskiller.
- Et navn bag en betegnelse som „Kontaktperson (salg)" eller
  „Sagsbehandler/-behandlerske" genkendes nu også med parentestilføjelse
  eller kønsneutral skråstregsendelse.
- Samme stjerne-kønsform („Sagsbehandler*ske") genkendes nu ligeledes.
- Et navn bag en betegnelse genkendes nu også, når et lighedstegn i
  stedet for et kolon adskiller (f.eks. „Kontaktperson = Mayer Roman"
  eller „Kontaktperson=Mayer Roman"), som sædvanligt i
  konfigurationsfiler eller CSV-overskrifter. Står flere sådanne
  betegnelse-værdi-par adskilt af semikolon i en linje, genkendes nu kun
  den første værdi i stedet for hele den resterende linje.
- Et GPS-koordinatpar bag ordet „koordinater" genkendes nu pålideligt
  (f.eks. „Koordinater: 48.2082, 16.3738") – ordet bar den forkerte
  bøjningsform i det interne katalog.
- Et identifikationsnummer bag sin betegnelse (kundenummer,
  kontraktnummer, sagsnummer, identitetskortnummer og omkring hundrede
  andre feltord) blev ikke længere genkendt, så snart betegnelsen ikke
  stod nøjagtigt i den gemte store-/lille bogstav-skrivning –
  „kundenummer:" i en e-mail eller „KUNDENUMMER:" i en formularoverskrift
  forblev urørte stående.

### Nyt

- **Realistiske erstatningsværdier er nu et bevidst indsat eksempel i
  stedet for en standard.** Undtagelsestabellen i fanen „Pladsholder"
  begynder tom. En ny knap indfører der efter ønske plausible falske
  værdier for navn, sted, adresse, organisation, e-mail, telefon,
  lokalnummer og IBAN. Den lader udtrykkeligt pengebeløb blive ved den
  nummererede pladsholder; strategien „opdigt" forbliver fortsat manuelt
  valgbar for enkelte arter.
- **AI-niveauet kan bruge grafikkortet.** Under Windows kan der til dette
  formål efterindlæses en knap 17 MB stor ekstrapakke; derefter regner
  AI-niveauet betydeligt hurtigere på et egnet grafikkort end på
  processoren. Den, der ikke har et, eller intet efterindlæser, arbejder
  uændret videre – blot langsommere. På macOS er accelerationen
  alligevel allerede indbygget.
- **To nye notifikationer via proceslinje-symbolet**: når
  forhåndsvisningen er klar til gennemsyn før erstatning, og når en
  behandling er færdig. Begge er som standard tændt og kan slås fra
  enkeltvis under *Indstillinger → Program → Notifikationer*.

### Ændret

- **Identitetskort- og kørekortnummer genkendes nu**, når betegnelsen
  står foran („Identitetskortnummer: …", „Kørekortnummer: …") – hidtil
  faldt begge igennem enhver genkendelse.
- **Maskuro følger nu Windows' kontrastdesign.** Den, der under
  *Indstillinger → Tilgængelighed → Kontrastdesign* har tændt ét, fik det
  hidtil overalt undtagen her: Maskuro satte derefter sine egne farver.
  Nu forbliver det ved systemets design – vindue, lister, aflæggelseszone,
  protokol og statusfarver. Det farvede kontrolampel i forhåndsvisning
  og vinduet til efterretning bortfalder der bevidst; hvad det siger,
  står siden alligevel som tegn og som ord ved siden af.
- **Kontrolbehovet står ikke længere kun i farven.** Rødt, orange og
  grønt er næsten lige lyse – den, der har rød-grøn-svaghed, så i
  forhåndsvisning og fundfag en liste uden forskelle, og det er omkring
  hver tolvte mand. Hver linje bærer nu desuden et tegn, der adskiller
  sig i formen: ▲ kontrollér først, ● kontrollér, ○ godt belagt, ◆ uden
  vurdering. Kortvejledningen nævner det med ord, og en skærmlæser læser
  det op.
- **Alt åbner igen menuerne som vant.** Menulinjen havde ingen
  tastaturgenveje: Den, der ikke bruger musen, måtte pile sig gennem
  hver menu. Nu bærer hvert punkt et understreget bogstav – Alt+F for
  „Fil", derfra A for „Afslut" – og det på alle grænsefladens sprog.
- **Betjeningselementer fortæller igen en skærmlæser, hvad de er til.**
  I vinduet til efterretning, i regelvinduet, i protokollen, i
  ordlisterne, i hjælpen, i søgningen og i fem yderligere vinduer blev
  lister, søgefelter, rullelister og skydere hidtil kun annonceret som
  „træ" eller „kombinationsfelt" – uden hvad. Omkring fyrre steder bærer
  nu et navn. (Hovedvinduet var i orden siden august; de vinduer, der kom
  til bagefter, havde aldrig fulgt trinnet med.)
- **Den, der betjener med tastaturet, ser overalt, hvor han står.** Ved
  kontrolbehovs-skyderne, ved afkrydsningsfeltet og ved „aldrig
  igen"-knappen i forhåndsvisningen, ved artoverskrifterne deri, ved
  sidefaget i vinduet til efterretning og ved indstillingernes
  sidebjælke manglede rammen, som systemet ellers lægger om det
  tilsprungne betjeningselement.
- **Større systemskrift afskærer intet længere.** Den, der under
  *Tilgængelighed → Tekststørrelse* stiller over 175 %, mistede hidtil
  slutningen af betegnelserne i mappeovervågningen og i
  tastaturgenvejsfelterne. Hjælpens kapitelliste afskar lange
  kapitelnavne allerede ved almindelig skrift; den ombryder dem nu og
  nævner det fulde navn i kortvejledningen.

- **Genkendelsen er blevet betydeligt hurtigere.** Genkenderen for
  betegnede identifikationsnumre („Kundenummer: K903944") kontrollerede
  hidtil pr. tekstafsnit over 1200 enkeltmønstre efter hinanden – det var
  den største enkeltpost i genkendelsestiden, ved hvert afsnit og hver
  tabelcelle. Nu er det ét eneste mønster med samme resultat: På
  målekorpuset ændres ikke et eneste fund, grundniveauet pr. tekstafsnit
  bliver omkring tre til fire gange så hurtigt.
- **Vinduet fremkommer straks ved start.** Hidtil indlæste hovedvinduet
  de fuldstændige sprogværktøjer, før det overhovedet viste sig –
  omkring fire sekunders blindtid ved hver start. Modellerne indlæses nu
  som tilsigtet i baggrunden, mens vinduet allerede står; knappen
  „Rens" bliver som hidtil først fri, når alt er klar. Også rene
  oplysningskald fra kommandolinjen (f.eks. `--version`) svarer nu
  straks i stedet for efter flere sekunder.
- **Billeder læses ved automatisk sproggenkendelse kun én gang.** Hidtil
  kørte tekstgenkendelsen ved standardindstillingen „Sprog: automatisk"
  to gange over samme billede – én gang til sprogformodningen, én gang
  til den egentlige kontrol. Billedfiler, udklipsholder-billeder og
  tekstvinduet er dermed omkring dobbelt så hurtigt færdige; ved
  frakoblet tekstgenkendelse bortfalder den hidtil ubemærket alligevel
  kørende læsning helt.
- **Gemte hjemmesider og e-mails renses hurtigere.** Værdierne i
  HTML-attributter, kommentarer og indlejrede datablokke blev hidtil
  genkendt enkeltvis – en kommuneside med hundreder af betegnelser
  stillede hundreder af enkeltspørgsmål til genkendelsen. Nu samles de og
  genkendes kun én gang pr. forskellig værdi; på målekorpuset ændres
  intet fund, .html og .eml er omkring en tredjedel hurtigere.
- **Også biarkiverne fra regneark og præsentationer genkendes samlet.**
  Alternative tekster, formel-tegnstrenge, diagrambetegnelser,
  kommentarer, pivot-mellemlagre og dokumentegenskaber stillede pr.
  værdi et eget genkendelsesspørgsmål – en arbejdsbog med tusinder af
  pivot-linjer tilsvarende tusinder. Nu kører et samlet forløb over de
  forskellige værdier, og eftertrækkets fulde gennemløb til sidst kører
  kun, hvis der virkelig er kommet nye værdier til siden brødteksten. På
  målekorpuset ændres intet fund.
- **Formularrige PDF'er renses hurtigere.** Felter, noter, bogmærker og
  henvisninger gentager de samme værdier massevis („Off" ved hvert
  afkrydsningsfelt, samme forfatter ved hver anmærkning) – hver stillede
  hidtil sit eget genkendelsesspørgsmål. Pr. kørsel genkendes en værdi nu
  kun én gang; erstatning og konsistens-eftergang kører uændret pr.
  sted.
- **Store regnearksfiler (.csv/.tsv) renses betydeligt hurtigere.** De
  fire regneark-eftergange opdelte hidtil hver især selv samme fil
  tegnvis i celler (ved 40 MB omkring 30 s ekstraarbejde); nu kører
  opdelingen én gang. Kolonneoverskrifts-genkendelsen (fødselsdato- og
  personalenummerkolonner) stiller i stedet for ét spørgsmål pr. celle
  ét samlet – ved identiske fund omkring tyve gange hurtigere. Og
  navnekolonne-sammenfatningen af store personallister er ikke længere
  kvadratisk i linjeantallet.
- **Nøgletalsklappen fryser ikke længere vinduet.** Udfoldningen af
  nøgletallene læste ved mange store filer først deres tekst sammen og
  lod vinduet stå stille i sekunder. Beregningen kører nu i baggrunden;
  klappen åbner straks og efterindtaster tallene.
- **Søgnings-rapporten fryser ikke længere vinduet.** Efter gennemsøgning
  af mange tusinde filer blev den fælles mappe genberegnet for hver
  berørt fil; ved store kørsler stod vinduet hermed tocifrede sekunder
  stille. Rapporten fremkommer nu straks.
- **PDF'er med tekstgenkendelse kontrolleres hurtigere.** Hver side blev
  ved gennemlæsning unødvendigt konverteret to gange til PNG-format; nu
  føres det allerede foreliggende billede videre. Resultatet er uændret,
  kun kontrollen forløber hurtigere.
- **Forløbsanmærkninger på store billeder hakker ikke længere.** Ved
  efterjustering på håndtagene af en anmærkning med forløb blev forløbet
  hidtil genberegnet punkt for punkt – på et stort skærmbillede en synlig
  standsning. Resultatet er det samme, blot uden pausen.

### Rettet

- **Krydset til at fjerne en fil fra listen er igen et enkelt X.** Det
  nye editorværktøj „Fjern" havde ved en fejl brugt samme symbolkending
  og derved også vist sit røde kryds med stiplet tekstlinje i hver
  fillinje. Begge handlinger har nu adskilte symbolnavne og beholder
  hver deres passende visning.
- **Flerdelte angivelser genkendes i PDF'er nu også hen over et synligt
  linjeskift.** Maskuro læser nu desuden den geometrisk genererede
  sidetekst som en offsetlig brødtekstvisning. Det gælder for alle
  grund- og høj-niveau-genkendere samt egne søgemønstre, ikke kun for det
  først synlige tilfælde „Diabetes mellitus type 2". Tomme linjer og
  genkendte tabel- eller afsnitsgrænser forbliver hårde grænser;
  fundsteder passer fortsat nøjagtigt til de ord, der skal sløres.
- **Eksemplet ved „Pseudonymisering" modsagde sig selv.** Sætningen
  lovede „samme person, samme nummer" og viste derefter to forskellige
  numre – netop det billede, der er rigtigt ved „Anonymisering". Begge
  eksempler stemmer nu overens med deres egen sætning.
- **En friskt indsat pladsholder kunne ved „Hent original tilbage" blive
  stående som overlejret bogstavmudder i stedet for at forsvinde.** En
  ensfarvet indlagt pladsholder skrev hidtil en egen udgangskommando pr.
  tegn, hvoraf kun det første bar en egen tekstmatrix – ved den næste
  redigering af samme sted (f.eks. „hent tilbage" direkte derefter) fik
  de øvrige tegnkommandoer på skift det førstes tegnindeks tildelt, og
  pladsholderen faldt fra hinanden i to overlejrede positioner. En
  ensfarvet pladsholder får nu én eneste udgangskommando for hele sin
  tekst.

- **Stod samme slørede eller fjernede værdi under to linjer i vinduet til
  efterretning, og blev begge markeret til tilbagehentning, talte den
  anden linje fejlagtigt som „ikke entydig" – selv om værdien for
  længst var hentet tilbage.** Begge linjer gælder nu som klaret.

- **Navnet efter „Reply-To:" findes nu.** I en e-mail-overskrift som
  „Reply-To: Huber" forblev navnet hidtil helt ugenkendt – sprogmodellen
  læste „Reply-To:" som en egen, forkert person og overså det ægte navn
  derefter.

- **E-mail-overskriftsordene „Reply" og „Fwd" sløres ikke længere selv
  som navn.** I en emnelinje som „Fwd: Tilbud fra Huber" blev hidtil
  udover navnet også selve overskriftsordet genkendt og sløret som en
  person.

- **„Arbejdsgiver: Siemens AG" genkendes nu som firma, ikke længere som
  person.** Bar firmaværdien bag betegnelsen „Arbejdsgiver" en
  selskabsform som GmbH, AG eller KG, forblev den trods tilkoblet
  organisationsgenkendelse et personfund – kun det smallere tilfælde uden
  selskabsform („Wollmuth og partnere") blev hidtil genkendt som firma.

- **En allerede genkendt adresse bliver ikke længere stående et andet
  sted.** Blev en gadeadresse genkendt og erstattet ét sted, kunne samme
  adresse blive stående et andet sted – f.eks. i en svært læselig
  sidefod i et indscannet dokument, hvor den automatiske
  tekstgenkendelse læste den forvansket. Adresser fjernes nu, ligesom
  navne og firmaer længe har været, gennemgående i hele dokumentet.

- **E-mails med flere modtagere blev stiltiende beskadiget ved
  rensning.** En `.msg`-meddelelse med to eller flere modtagere mistede
  ved lagring dele af sin indre opbygning, så det rensede resultat var
  ufuldstændigt. Årsagen var en forveksling af ensbenævnte indre
  bestanddele, som forekommer ved hver modtager. Sådanne meddelelser
  genopbygges nu fuldstændigt.

- **To af de medfølgende testdokumenter kunne ikke åbnes i Word og
  PowerPoint.** Den, der downloadede målekorpuset, fik ved
  `format_dokument.docx` „Fejl ved åbning af filen i Word" og ved
  `format_praesentation.pptx` „Filen er beskadiget". Begge filer var
  allerede fejlbehæftede, før Maskuro rørte dem – den rensede version
  bar blot fejlen videre. LibreOffice åbnede begge uden indvendinger,
  hvorfor ingen havde bemærket det.

- **En egen AI på internettet tiltales nu krypteret.** Den, der ved egen
  AI indtaster en ekstern adresse uden „https://" (som den ofte står på
  IT'ens seddel), nåede den hidtil via en ukrypteret forbindelse – den
  usløret tekst gik ud i klartekst. Sådanne adresser tiltales nu via
  „https://"; en server i eget netværk forbliver uændret tilgængelig.
  Følger serveren en omdirigering til en anden computer, vandrer
  adgangsnøglen ikke længere med.

- **Også et beskadiget billede mister nu sine skjulte metadata.** Kunne
  et indlejret billede ikke længere åbnes fuldstændigt (f.eks. et
  afskåret foto), beholdt det hidtil sine EXIF- og GPS-data –
  optagested og fotografnavn forblev usynlige i resultatet. Sådanne
  billeder befries nu for disse data, også når de slet ikke længere kan
  vises.

- **En indlejret fil, der ikke kunne renses, meldes nu i stedet for at
  blive givet stiltiende videre.** Lå der i en præsentation eller
  arbejdsbog et indlejret objekt, der var for dybt indlejret eller ikke
  kunne åbnes, forblev det hidtil uændret i resultatet, uden henvisning –
  filen gjaldt som renset. Sådanne tilfælde står nu i advarslen „kunne
  IKKE kontrolleres", ligesom et indlejret gammelt format.

- **Mørke lister er igen gennemgående mørke og læselige.** På macOS
  skiftede fillister mellem næsten sorte og lysegrå linjer; i
  efterretning så samme grønne, orange eller røde kontrolværdi derved
  forskellig ud alt efter linje. Vindue, lister, skrift, pladsholder og
  markering kommer nu fra en fælles lys-/mørkepalette. Den farvekodede
  fundliste lægger desuden ikke længere zebrastriber under sine farver.

- **Erhvervsangivelser med „som" blev fejlagtigt sløret som navn.** En
  sætning som „Som kok har han været ansat hos os i fire år." mistede
  erhvervet, ikke kun et navn – „som" indleder en rolleangivelse ligesom
  „den" eller „det". Ægte efternavne på samme sted (f.eks. med en tiltale
  foran) forbliver uberørte.

- **En tabeloverskrift kunne trække et positionsnummer ind i et
  pengebeløb** (kun ved tilkoblet valgmulighed „Fjern også
  pengebeløb"). Endte en linje på en valuta („… enhedspris EUR") og
  begyndte den næste med et tal, blev der fejlagtigt et beløb hen over
  linjeskiftet. Adskilleren mellem valuta og tal forbliver nu på samme
  linje.

- **En kort forkortelse i store bogstaver kunne sluge en hel sætningsdel
  eller hænge sig foran et korrekt genkendt navn.** Stod der i en linje
  et tobogstavs-storord som „DI", „AG" eller „KG" – hverdagsforkortelser,
  ingen navne –, blev hele linjen gennemsøgt forsøgsvis med lille
  bogstav, og forkortelsen trak hermed til tider nabo-ord (også udsagnsord)
  ind i ét eneste formodet navn. Først fra tre bogstaver udløser et
  stort skrevet ord nu denne anden kontrol. Ved lidt længere
  forkortelser som „CEO" eller „USB" forblev en anden fejl: Det allerede
  korrekt fundne navn („Schneider") fik den foranstillede forkortelse
  trukket med ind i resultatet som forstavelse („CEO Schneider").
  Forkortelsen forbliver nu udenfor.

- **En fødselsdato uden mellemrum bagefter forblev stående.** Stod der
  bag „f." ikke noget mellemrum foran datoen – som sædvanligt i tæt satte
  formularer („f.14.03.1988") –, genkendte Maskuro ikke feltet og lod
  datoen forblive urørt. Udbredte kortformer som „Fødselsdat." eller
  „Fød.-dato." genkendes nu ligeledes.

- **En IBAN med skråstreger som adskiller forblev stående.** Som ved
  telefonnumre („0664/1234567") skriver visse skabeloner også IBAN'en i
  blokke med skråstreg („AT48/3200/0000/1234/5864") i stedet for med
  mellemrum eller bindestreg. Denne skrivemåde genkendes nu ligeledes.

- **Et østrigsk personnummer med bindestreg, punktum eller skråstreg
  forblev stående eller var forkert betegnet.** Mellem de to talblokke
  var hidtil kun forudset et mellemrum; skrivemåder som „1237-010180",
  „1237.010180" eller „1237/010180" blev ikke genkendt (eller i
  skråstreg-tilfældet under den forkerte art). Kontrolcifferet bekræfter
  fortsat hvert fund, uafhængigt af adskilleren.

- **Et navn bag „c/o" i en adresse blev slet ikke fjernet.** „c/o Max
  Mustermann, Hauptstraße 5, 1010 Wien" slørede gade og by, men lod
  navnet derefter forblive fuldstændigt stående. Navnet genkendes nu;
  „c/o" selv forbliver synligt som adressehenvisning.

- **Et med punktummer grupperet kreditkortnummer forblev stående.**
  Skrivemåder som „4111.1111.1111.1111" blev ikke genkendt; med
  mellemrum eller bindestreg adskilte numre var ikke berørt af dette.
  Kontrolsummen bekræfter fortsat hvert fund.

- **Et med bindestreger grupperet skattemæssigt identifikationsnummer
  forblev stående, en østrigsk UID med bindestreg eller punktum
  ligeledes.** Mellemrum, skråstreg og punktum var allerede forudset ved
  skatte-ID'et, bindestregen manglede; ved UID'et („ATU12345678") manglede
  bindestreg og punktum efter præfikset. Kontrolcifferet i skatte-ID'et
  bekræfter fortsat hvert fund.

- **En feltværdi i anførselstegn forblev stående, f.eks. i en JSON-agtig
  linje som „fornavn": „Max".** Genkendelsen via en feltbetegnelse
  („Fornavn: …") forudsatte hidtil, at hverken betegnelsen eller selve
  værdien står i anførselstegn. Sådanne linjer genkendes nu ligeledes –
  ligeledes feltbetegnelser med et foranstillet YAML-listepunkt
  („- Fornavn: Max") eller en tabulator i stedet for et mellemrum foran
  kolonet.

- **E-mail-overskriftsordet „Sent" blev selv sløret som et navn.** I en
  overskrift som „Sent: Huber" ramte det hidtil både „Sent" og selve
  navnet; beslægtede overskriftsord som „Subject" eller „Emne" var altid
  uberørte af dette. „Sent" forbliver nu ligeledes stående.

- Et navn bag overskrifterne „Errors-To:" eller „Resent-From:" forblev
  uopdaget, hvis en sådan linje stod kopieret i klartekst (f.eks. en
  videresendt meddelelse eller en hændelsesrapport) – i modsætning til
  ved „Reply-To:" eller „Return-Path:" faldt navnet her helt væk i stedet
  for kun at være unøjagtigt afgrænset. Det findes nu.
- En og samme fil gav ved to rensninger til tider et forskelligt
  resultat: Ramte to genkendelser netop samme sted med samme længde og
  samme sikkerhed (f.eks. „Socialsikringsnummer 1237/010180" som AT_SVNR
  eller som generelt identifikationsnummer), var det afhængigt af
  tilfældet, hvilken der vandt – værdien blev fjernet i begge tilfælde,
  kun pladsholderbetegnelsen skiftede. Uafgjortheden afgøres nu altid
  ens.
- En funktionsbetegnelse direkte foran et navneord (f.eks. „Behandlende
  læge: Dr. …" eller „Ansvarlig sagsbehandler er …") blev til tider
  fejlagtigt sløret med, som var den selv et navn. Ægte efternavne ved
  siden af forbliver uberørte af dette.
- Et ægte efternavn, der tilfældigvis ligner et tillægsord (f.eks.
  „Skønne", „Lange", „Unge") og står umiddelbart foran endnu et navneord
  (f.eks. „Kontaktperson: Skønne Assistent"), forblev siden sidste
  rettelse usløret stående i teksten – et datalæk. Kun en snævert
  afgrænset liste over ægte funktionsbetegnelser (f.eks. „Behandlende",
  „Ansvarlig") behandles nu i denne byggeform som ikke-navn.
- Et alenestående efternavn ved slutningen af et flerlinje-navnefund, der
  tilfældigvis ligner et tillægsord (f.eks. „Sort", „Kort", „Gammel",
  „Frisk", „God", „Rig"), forblev ugenkendt stående foran et umiddelbart
  følgende kolon – rensningen forvekslede det med en feltbetegnelse som
  „Telefon:". En lukket liste over kendte flertydige efternavne beskytter
  det nu.
- Et alenestående efternavn, der tilfældigvis er et almindeligt dansk ord
  („Stor"/„Store", „God", „Kort", „Lang"/„Lange"), gik hidtil
  **fuldstændigt** tabt – også i enkle sætninger som „Hr. Stor
  underskrev kontrakten." Årsagen lå i spaCy's egen stopordsliste, som
  indeholder disse ord; en lukket liste over kendte efternavne bevarer
  dem nu fra at blive kasseret.
- Ved ansættelses-, lån-, kautions-, forvaltnings- og
  insolvenskontrakter samt værgemål/plejeforhold og vurderingsopdrag blev
  et efternavn, der samtidig er et almindeligt ord (f.eks. „Bauer"),
  overset bag betegnelser som „Ordregiver:", „Kontrahent:",
  „Arbejdstager:", „Forsikret:", „Långiver:", „Låntager:", „Kautionist:",
  „Sikkerhedsstiller:", „Forvalter:", „Forvaltningsgiver:",
  „Bobestyrer:", „Vurderingsmand:", „Sagkyndig:", „Værge:" eller
  „Plejer:" – dels forblev kun fornavnet genkendt, dels faldt hele
  navnet væk.
- I kolofonen blev et efternavn, der samtidig er et almindeligt ord
  (f.eks. „Bauer"), overset bag betegnelserne „Direktør:",
  „Direktion:", „Tegningsberettiget:", „Indehaver:" eller
  „Indehaverske:" – ved „Direktør:"/„Indehaver:" faldt hele navnet
  væk, ved „Tegningsberettiget:" forblev kun fornavnet genkendt.
- En kontaktblok, hvis betegnelse stod alene på sin linje og bar den
  kønsneutrale kolon-form („Kontaktperson:/-inde", navn nedenunder),
  blev **fuldstændigt** overset – kolonet blev læst som feltadskiller,
  „inde" som en (kasseret) feltværdi, og det egentlige navn i næste linje
  kom derved aldrig til udførelse. Stjerneformen
  („Kontaktperson*inde") var ikke berørt af dette.
- Stod navn og betegnelse med samme kolon-kønsform i **én** linje
  („Kontaktperson:inde Anna Berger"), rev pladsholderen ordet „inde" med
  ind i erstatningen i stedet for kun at fjerne navnet – selve navnet
  blev fortsat fuldstændigt fanget.
- Et navn i en tabelkolonne under en person-kolonneoverskrift (f.eks.
  „Efternavn Fornavn Fødselsdato" over „Bauer Anna 03.05.1985", som i en
  lønseddel) blev fuldstændigt overset, så snart der kun stod ét eneste
  mellemrum mellem kolonnerne, og ingen linje begyndte med et
  struktureringsnummer – netop den form, hvori et ægte
  PDF-tekstudtræk leverer sådanne linjer.
- I et chat- eller mødereferat med talernavne foran kolonet (f.eks.
  „Bauer 🙂: Jeg er enig i forslaget.") forblev navnet fuldstændigt
  ugenkendt, så snart et reaktionstegn stod mellem navn og kolon, og
  efternavnet samtidig var et almindeligt ord („Bauer", „Koch",
  „Schneider" og lign.) – et helt referat kunne derved forblive uden en
  eneste genkendt taler.
- Samme talerlinje-hul fandtes også med andre mellemtegn foran kolonet:
  en statustilføjelse i parentes („Bauer (formand): …", „Bauer
  (fraværende): …"), et klokkeslæt i firkantede parenteser
  („Bauer [14:32]: …") og et fodnotetegn umiddelbart ved navnet
  („Bauer*: …"). Også her forblev taleren fuldstændigt ugenkendt, så
  snart efternavnet samtidig var et almindeligt ord.
- Stod en allerede genkendt person i et vedhæftet protokol- eller
  logudsnit til samme meddelelse (f.eks. en supportsag) desuden som
  brugernavn i formen „fornavn.efternavn" – med lille bogstav, uden
  mellemrum, forbundet med et punktum –, forblev dette klarnavn læseligt
  stående, selv om samme navn allerede var sløret i følgebrevet.
- Samme brugernavn-hul fandtes også med en understregning i stedet for
  et punktum („fornavn_efternavn") – et ligeledes udbredt format i
  protokol- og logudsnit.
- Og også i omvendt rækkefølge forblev brugernavnet læseligt
  („efternavn.fornavn" hhv. „efternavn_fornavn") – visse systemer sætter
  efternavnet foran i stedet for bagest i logbrugernavnet.
- En dødsdato forblev ugenkendt, hvis der ikke stod nogen anden angivelse
  ved siden af („Hr. Bauer afgik ved døden den 12.03.1985") – for det
  fandtes hidtil slet ingen egen genkendelse, og den generiske dato
  rammer ikke ved denne standardtærskel.
- En dødsdato forblev også ugenkendt, hvis sætningen brugte verbformen i
  stedet for participiet („Fru Meier døde den 12.03.1985", „Han afgik
  ved døden den 12.03.1985") – kun „er … afgået ved døden"/„er … død"
  ramte hidtil.
- En vielsesdato forblev ugenkendt, uanset i hvilken form den stod
  („Vielse den 12.03.2010", „Vielsesdato: 12.03.2010", „Hr. og fru Bauer
  blev gift den 12.03.2010") – for det fandtes hidtil slet ingen egen
  genkendelse, og den generiske dato rammer ikke ved denne
  standardtærskel.

- **I editoren til efterretning kunne en anden ramme over en netop
  indsat pladsholder lade en rød tegnrest blive stående**, f.eks. „[G" i
  stedet for „[BEG1]" – uden nogen advarsel, for resten hørte ikke
  længere til den fortrolige angivelse (den var allerede fjernet i det
  første træk), men kun til selve pladsholderen. Årsagen var
  farvegivningen: En nyt indsat pladsholder blev skrevet tegnvis i
  filen, også ved ensfarvet standard – en senere ramme over samme sted
  fandt derved ingen sammenhængende ordlyd, som den kunne have
  stedfæstet sig på. Nu står en ensfarvet pladsholder som ét stykke i
  strømmen, som den automatiske rensning altid har gjort; kun ægte
  forløb eller regnbuetekst kræver fortsat enkelte tegn. Den indbyggede
  kontrolprøve genkender nu desuden en sådan rest også, når
  pladsholderens nøjagtige tegnstreng ikke længere forekommer.
- En nummereret navneliste med trinvis struktureringsnummer
  („1.1 Max Mustermann", „1.2 Huber Franz" …) mistede alle navne til den
  samme bremse, der egentlig kun skal beskytte ægte struktureringer og
  positionslister – uden kolonneoverskrift over listen fandtes intet
  vidne, hvorpå et navn kunne have reddet sig.
- Et navn i en engelsksproget login-linje i en systemlog
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2")
  blev ikke genkendt – den tyske sprogmodel fandt det kun, hvis der stod
  „invalid user" foran, ellers forblev det stående. Sådanne loguddrag
  vedlægges ofte uændret en hændelsesrapport. Navne bag „for" foran en
  IP-adresse genkendes nu pålideligt.
- Navnet på den betalingspligtige i SEPA-mandatreferencen på et
  kontoudtog eller bogføringsjournal (f.eks. „MREF+Mustermann Klaus+SVWZ+
  Husleje august") forblev åbent – intet mellemrum, ingen
  sætningsstruktur, kun med „+" adskilte store bogstav-felter, og i den
  der sædvanlige rækkefølge „efternavn fornavn" fandt genkendelsen det
  heller ikke ved en tilfældighed. Genkendes nu.
- Gaden med husnummer i den første linje af en adressetabel (f.eks.
  „Efternavn | Fornavn | Gade | Postnr | By") forblev åben –
  sprogmodellen gættede der på et forkert, men længere sted hen over
  flere kolonner, og det fortrængte det korrekte, kortere adressefund.
  Genkendes nu.
- Samme læk optrådte med en tabulator i stedet for „|" eller „;" som
  kolonneadskiller – der forsvandt adressen endda helt i stedet for kun
  at gå tabt delvist. Genkendes nu.
- En gade med husnummer forblev åben, hvis der direkte bagefter uden
  mellemrum fulgte et postnummer med komma (f.eks. „Bahnhofstrasse
  12,80331 München", som i en kommaadskilt tabelkolonne) – kommaet
  lignede en decimal for en mængde, og gaden gjaldt derfor slet ikke som
  adresse for mønsteret. Genkendes nu.
- En gade med husnummer forblev åben, hvis der direkte bagefter uden
  komma fulgte stedsforstavelsen „St." (Sankt) (f.eks. „Hauptstraße 5 St.
  Pölten", et brevhoved uden foranstillet postnummer) – „St." lignede
  styktalsenheden, og gaden gjaldt derfor slet ikke som adresse for
  mønsteret. Genkendes nu.
- En dør-/trappetilføjelse efter et husnummer (f.eks. „Lerchenfelder
  Gürtel 43/12") forblev synligt åben, hvis der direkte bagefter stod et
  enkelt bogstav, der tilfældigvis stemmer overens med en måleenhed
  (f.eks. „h" for time) – adressen blev da kun renset til husnummeret
  uden sin tilføjelse, i stedet for at ramme fuldstændigt eller slet
  ikke.
- En emnelinje med et erhvervsnavnesammenfaldende efternavn foran
  fornavnet („Emne: Bauer Anna", „Emne: Bauer, Anna") forblev hidtil
  fuldstændigt ugenkendt – også midt i dokumentet med en foranstående
  fuldstændig sætning. Genkendes nu.
- Et tysk skattenummer med mellemrum, punktum eller bindestreg mellem
  blokkene (f.eks. „Steuernummer: 30 815 08153" eller „30.815.08153")
  forblev hidtil ugenkendt – kun skrivemåden med skråstreg blev fundet.
  Genkendes nu.
- Et navn bag en medicinsk feltbetegnelse („Patient:", „Praktiserende
  læge:", „Behandlende læge:", „Henvisende læge:" og deres kvindelige
  former) forblev hidtil ugenkendt, hvis efternavnet samtidig var et
  almindeligt tysk ord (f.eks. „Patient: Bauer Thomas"). Genkendes nu.
- Et navn bag feltbetegnelsen „Tandlæge" på egen linje (f.eks.
  „Tandlæge", nedenunder „Huber Franz") forblev hidtil ugenkendt –
  hverken for- eller efternavn. „Tandlægeske" og den enkle „Læge"-form
  var ikke berørt af dette. Genkendes nu.
- Et efternavn bag „Hr."/„Fru", efterfulgt af en kancellisprogsvending
  som „til efterretning", „til underskrift" eller „til videreformidling",
  blev hidtil fanget for bredt og rev vendingen med ind i navnefundet –
  af „Fru Petra Klein til repræsentation i alle anliggender" blev „Petra
  Klein til repræsentation" erstattet, og resten af sætningen forblev
  grammatisk lemlæstet stående. Ægte adelsprædikater som „von der Leyen"
  eller „zu Guttenberg" forbliver uberørte af dette.
- Samme kancellisprogs-overredigering stak også bag navnet i en
  e-mail-„To:"-overskrift, en registreringskode (C.1/C.1.1/C.1.2), en
  kørekortkode, et parentesat formularfelt („[Fornavn]: …") og en
  ikke-punkteret hilsenformular – overalt der rev „til"/„von" og lign. en
  følgende vending som „til underskrift" eller „til repræsentation" med
  ind i fundet, dels forblev endda selve partikelordet hængende som
  navnerest i resultatet. Også her forbliver ægte adelsprædikater
  fuldstændigt bevarede.
- Matrikelnummeret bag sin betegnelse blev hidtil slet ikke genkendt –
  „Matrikelnummer 7654321" faldt helt igennem genkendelsen, hverken som
  identifikationsnummer eller via sprogmodellen, fordi tallet alene ikke
  bærer en genkendelig form.
- Det samme gjaldt deltagernummeret – „Deltagernummer 4471829" faldt
  helt igennem, hverken som identifikationsnummer eller via
  sprogmodellen.
- I et CV faldt navnet under afsnitsoverskriften „Personlige oplysninger"
  ofte helt eller delvist igennem genkendelsen, hvis det stod uden
  tiltale i formen „efternavn fornavn" direkte nedenunder.
- Det samme gjaldt afsnitsoverskriften „Kontaktoplysninger" – der faldt
  navnet endda helt igennem, ikke kun delvist.
- I en folkeregisterattest eller ansøgningsliste med sammenfattet
  kolonne „Navn, fornavn" (folkeregisterets skrivemåde, værdi f.eks.
  „Mustermann, Max" i en celle) faldt navnet helt igennem genkendelsen,
  hvis endnu en kolonne som fødselsdatoen fulgte.
- En fødselsdato i den på identitetskort og folkeregisterattest
  sædvanlige form „Fødselsdato/-sted: 22.07.1978 / Rostock" blev ikke
  genkendt – kun kommaformen „Fødselsdato, fødested: …" ramte.
- „Borgerservice" og „Borgerkontor" blev til tider fejlagtigt sløret som
  sted, især efter en tankestreg som opremsningsadskiller (f.eks. „Henvend
  dig til borgerservice – borgerkontoret …").
- Et betegnet telefonnummer, som et linjeskift skar midt igennem (f.eks.
  fra en smal brevhoved-kolonne eller en PDF-tekstudtrækning ved
  kolonnebredden: „Telefon: 0176 12\n34567"), blev til dels kun halvt
  sløret – resten bag linjeskiftet forblev læselig stående.
- Et betegnet identifikationsnummer (kunde-, medlems-, kontraktnummer og
  lignende), som et linjeskift skar midt igennem (f.eks. „Kundenummer:
  K903\n944" fra en smal kolonne), blev kun halvt sløret – resten bag
  linjeskiftet forblev læselig stående.
- Et navn med akademisk titel foran en erhvervsbetegnelse efter komma
  (f.eks. „Dipl.-ing. Sabine Roth, projektleder") forblev fuldstændigt
  ubeskyttet stående – linjen lignede en tabellarisk kolonneoverskrift og
  blev fejlagtigt kasseret som sagindhold.
- Titlen „Dr.-Ing." (en hyppig tysk ingeniørgrad) foran et navn blev ikke
  medtaget i den maskerede personværdi og forblev læselig stående – samme
  bindestregs-faldgrube som ved „Dipl.-Ing.".
- Titlerne „Dipl.-Kfm.", „Dipl.-Kffr." og „Dipl.-Psych." (diplomeret
  merkonom/-økonoma/-psykolog) foran et navn blev ikke medtaget i den
  maskerede personværdi og forblev læselige stående – samme
  bindestregs-faldgrube som ved „Dipl.-Ing." og „Dr.-Ing.".
- En MAC-adresse i Cisco-skrivemåden med punktummer i stedet for kolon
  (f.eks. „aabb.ccdd.eeff", som switch-protokoller og supportsager
  udgiver) blev slet ikke genkendt og forblev læselig stående.
- Et efternavn bag „familien" (f.eks. „Familien Gruber underskriver
  kontrakten") forblev alt efter sætningsopbygning ugenkendt og dermed
  læseligt stående – også med adelsprædikat foran („Familien von der
  Leyen").

- Ved en kroatisk adresse uden adskillende tegnsætning mellem
  postnummer+by og gade+husnummer (f.eks. „10000 Zagreb Ulica Ivana
  Lučića 5") forblev husnummeret urenset stående.

- Ved en litauisk kontaktangivelse med betegnelsen „Kontaktinis asmuo"
  (f.eks. „Kontaktinis asmuo: Vilkas Jonas") forblev efternavnet
  ugenkendt, hvis det samtidig var et almindeligt navneord (Vilkas =
  „ulv", Vanagas = „høg").

- Et føde- eller bopælsland uden yderligere betegnelse i et dansk
  formularfelt (f.eks. „Fødeland: Tyskland" eller „Bopæl: Tyskland") blev
  ikke genkendt.

- Et føde- eller bopælsland uden yderligere betegnelse i et rumænsk
  formularfelt (f.eks. „Țara: Germania" eller „Țara de reședință:
  Franța") blev ikke genkendt.

- Et firmanavn under den litauiske feltbetegnelse „Darbdavys:" eller
  „Įmonės pavadinimas:" (arbejdsgiver/firma) blev ikke genkendt.

- Et firmanavn under den russiske feltbetegnelse „Работодатель:" eller
  „Наименование организации:" (arbejdsgiver/firma) blev ikke genkendt.

- En udskrevet dato med måneds­navn på rumænsk (f.eks. „31 decembrie
  2024") blev ikke genkendt.

- Et ungarsk fødenavn bag forkortelsen „szül." (f.eks. „Nagy Éva (szül.
  Kovács)") blev ikke genkendt og forblev åbent læseligt stående.

- En gemt HTML-profilside (eller en e-mail med vedhæftet hjemmeside)
  kunne lade det borgerlige navn forblive urenset, hvis det kun stod i
  Open-Graph-profilfelterne `profile:first_name`/`profile:last_name`/
  `profile:username` – disse bærer navnet opdelt i stedet for beskrivende
  som `og:title` og renses nu ligeledes.

- En leveringsfejlmeddelelse (bounce/NDR) bar ofte overskrifterne fra den
  oprindeligt ikke-leverbare mail (afsender, modtager, emne) i en egen,
  tredje bilagsdel – denne forblev i den rensede version fuldstændigt
  urørt stående. Delen renses nu ligesom den øvrige leveringsrapport.

- Den individuelt benævnte redaktør af et beskyttet område i Word
  (Begræns redigering → Undtagelser, `w:permStart`) forblev i klartekst
  stående, også når samme navn for længst var renset i brødteksten. Han
  fjernes nu ligeledes.

## 0.10.42-alpha.20260827 – 27. august 2026

### Nyt

- **Navngivne genkendelsesprofiler gør forskellige arbejdssituationer
  tilgængelige med ét greb.** Under *Indstillinger → Genkendelse → Hvad
  fjernes* kan det aktuelle kategori- og typevalg gemmes og med det samme
  anvendes igen via et valgfelt. Standardprofilen *Standard* svarer til
  den hidtidige leveringsstand og kan ikke slettes. En profil ændrer
  udelukkende, hvad der fjernes; sprog, udgavetype, genkendelsesdybde
  samt egne begreber og søgemønstre berøres ikke.

- **Resultattypen vælges nu direkte før rensningen.** Et fælles
  valgfelt i hovedvinduet fastlægger for hele batchen, om Maskuro
  indsætter læsbare pladsholdere, sortslør eller fjerner uden erstatning.
  De to separate felter for PDF og Office i indstillingsvinduet er
  bortfaldet; derved bliver den vigtige beslutning synlig og kan ikke
  længere utilsigtet komme til at afvige ved blandede batcher. Den
  guidede gennemgang forklarer det nye valg før den første rensning.

- **Temaer og vandmærker markerer tydeligt færdige PDF'er efter ønske.**
  Tolv samlede udseender afstemmer erstatningstekster og
  sortsløringsflader mod hinanden; nye er Pride samt forår, sommer,
  efterår og vinter. *Hemmelig akte* medbringer direkte et diagonalt
  `TOP SECRET`. Uafhængigt heraf kan der vælges en fri markeringstekst
  eller eget billede, ikon henholdsvis SVG med farve og dækkraft.
  Importerede grafikker indlejres uden deres metadata og forbliver
  tilgængelige, hvis kildefilen flyttes. Ved efterredigering erstatter
  Maskuro sit hidtidige vandmærke i stedet for at lægge det oven på
  flere gange. Tekstvandmærker tegnes som det sidste PDF-lag med lys
  kontur, så de forbliver synlige også på mørke billeder og tæt tekst.
  Efterredigeringseditoren ignorerer Maskuros vandmærke fuldstændigt og
  tilbyder ikke længere dets tekst som sortsløringskandidat.

- **Egne udgavetemaer kan gemmes og deles.** Den aktuelle blanding af
  erstatningstekst, sortsløring og vandmærke får et navn, forbliver i
  indstillingerne og kan eksporteres eller importeres som klartekstfri
  JSON. Sort-hvid-printforhåndsvisningen advarer mod svage kontraster;
  valgfri succes-konfetti forbliver rent i brugerfladen.

- **En sidste eksportprøve og en forklarende kontrolvisning afslutter
  visningsrunden.** Før den endelige lagring sammenligner Maskuro hver
  værdikendt PDF-position endnu en gang i tekstlag og gengivne
  billedpunkter; advarsler nævner udelukkende side og koordinater. I
  editoren viser *Hvorfor er det dækket?* kategori, genkendelsesvej og
  sikkerhedsrand, aldrig den fjernede klartekst og aldrig i slutdokumentet.

- **Sortsløringsbjælker må nu godt være pæne.** Under *Indstillinger →
  Udseende* findes farveforvalg, frie farvevælgere, forløb, regnbue,
  striber, prikker, blomster, stjerner, hjerter, poter, skyer, lyn,
  kaffebønner, ænder, sole, blade, snefnug, papir-, tekstmarkør-,
  tape- og reproducerbare tilfældighedsmønstre samt umiddelbar
  forhåndsvisning. Erstatningstekster får valgfrit en farve, et forløb,
  en regnbue, en pille eller en etiket. Kategorifarver adskiller navne,
  adresser, kontakter og medicinske angivelser. PDF overtager den
  fuldstændige gestaltning; Word, PowerPoint, OpenDocument og HTML
  bruger den valgte dækkende grundfarve. Beskyttelsen ændres ikke
  herved: Maskuro fjerner det fortrolige indhold først og tegner
  derefter farve eller mønster på det tomme sted.

- **Maskuro findes igen til Linux – som AppImage, DEB, RPM og portabelt
  arkiv.** DEB og RPM registrerer programpost, filtilknytninger,
  terminalkommando og ikon i systemet; AppImage kører uden installation.
  Opdateringer forbliver ved en eksisterende DEB- eller
  RPM-installation i samme pakkeformat og foretrækker ellers AppImage.

- **Synskontrollen forelægger ikke længere almindelig PDF-tekst en anden
  gang som nye fund.** Det afsluttende OCR-kig og den sikre genopbygning
  af de synlige sider forbliver fuldt aktive; som ny fundkilde gælder i
  standarden dog kun områder, som sidetekst- og enkeltbilledkontrol
  endnu ikke har læst. Derved bliver produktlinjer ikke til nye navne
  eller firmaer blot på grund af en afvigende anden OCR-læsning. Den,
  der fortsat ønsker to uafhængige vurderinger af hele den synlige
  tekst, slår *Kontrollér hele den synlige PDF-side for angivelser
  endnu en gang* til i indstillingerne.

- **PDF'er kan nu ses løbende, arkvis eller som dobbeltside.** Tre
  kompakte visningsikoner sidder forneden lige ved siden af „Bredde" og
  „Side". Løbende ruller ved arkkanten til næste side; Enkeltside
  holder musehjulet på det aktuelle ark; Dobbeltside viser et opslag,
  gør det klikkede ark redigerbart og flytter frem/tilbage et helt
  opslag. Sideminiaturer og sammenligningslup åbner desuden nu i en
  markant smallere venstre grundspalte og giver arbejdssiden mere
  plads.

- **Du kan nu se, hvad KI-niveauet har gjort.** Efter hver kørsel står
  der under „Detaljer" pr. fil en linje om det – „KI-niveau: 12
  grænsetilfælde kontrolleret, 3 forkastet" –, og hvis det ikke fandt
  noget at ændre, står det også der. Hidtil tav det dyreste niveau
  fuldstændigt: Om det overhovedet blev spurgt, kunne man ikke se
  udefra.

  Den, der har brug for det mere præcist, slår *Skriv hvert KI-spørgsmål
  ind i loggen* til under „Indstillinger → KI". Så fastholder logfilen
  pr. spørgsmål størrelse, varighed og antal fund, hertil ventetiden
  gennem en mængdegrænse hos modparten. Knappen „Vis logfil" ved siden
  af åbner mappen – den ligger i programdatamappen, som er skjult under
  Windows, og som ingen finder af sig selv. I filen står udelukkende
  størrelser, aldrig tekst fra dine dokumenter.

- **Maskuro genkender, når din KI-tjeneste begrænser antallet af
  forespørgsler.** Hostede tjenester tillader ofte kun få forespørgsler
  pr. minut – fire er ingen sjældenhed. De overskydende afvises ikke,
  men må vente, og af to sekunder pr. svar bliver der fyrre. Det så
  hidtil ud, som om modellen var langsom. Nu læser Maskuro grænsen ud
  af tjenestens svar, sender ikke flere spørgsmål samtidig, end der
  accepteres, nævner grænsen under „Test forbindelse" og indregner den
  i varighedsestimatet.

- **Sidevisningen bruger dit Word, Excel og PowerPoint – og er samtidig
  cirka seks gange hurtigere.** Hidtil krævede den LibreOffice, som
  findes på de færreste kontormaskiner; den, der ikke havde det, så en
  knap, der krævede en fremmedinstallation. Nu gælder: Er Microsoft
  Office installeret, bruges det automatisk – uden opsætning, uden
  download, uden at du skal krydse af noget. LibreOffice forbliver den
  anden vej og ved OpenDocument-filer endda den første; slår den ene
  fejl, forsøges den anden.

  Forskellen mærkes især under arbejdet: Efter hver erstatning sættes
  siden op på ny, og det koster via Office cirka et halvt sekund i
  stedet for tre. Den første visning af et dokument tager fortsat nogle
  sekunder, derefter følger den dine håndgreb uden ventetid.

  Dit eget åbne Word røres ikke: Maskuro starter en egen, usynlig
  session, åbner filen kun til læsning, slår makroer fra og afslutter
  alt igen, så snart redigeringsvinduet lukkes. Adgangskodebeskyttede
  filer afvises i stedet for at hænge i en usynlig dialog.

- **Førsteopsætningen spørger nu også om ansigter, koder og
  underskrifter – og indlæser alt manglende i én omgang.** Ved siden af
  den udvidede genkendelse står de tre billedkontakter på første side:
  Gør ansigtsområder ukendelige, gør stribe- og QR-koder ukendelige,
  sortslør håndskrevne underskrifter på PDF-sider. PDF-grænsen står
  synligt ved kontakten; Office-filer gennemsøges ikke automatisk for
  underskrifter. Under kontakterne står, hvor mange megabyte klikket på
  „Videre" koster. Der indlæses derefter i **ét** vindue med **én**
  fremdriftslinje for det hele samlet, i stedet for i flere dialoger
  efter hinanden; en afbrydelse afslutter hele forløbet og efterlader
  intet halvfærdigt. Den, der ikke vil have noget af det, fjerner
  kontakterne – så indlæses der heller intet.

- **Forhåndsvisningen kan tyndes ud efter kontrolbehov og foldes sammen
  efter type.** Over listen sidder en skyder *Skjul godt belagte*: Jo
  længere den står mod højre, desto mere blender den fra grøn i retning
  rød ud; helt til højre står kun det, programmet alene har gættet. Et
  klik på overskriften for en type folder den sammen. Begge dele er en
  læsehjælp, ikke et valg – hvad der skjules eller foldes sammen,
  forbliver afkrydset og bliver erstattet; hvor mange værdier det
  netop er, står under skyderen. Ved korte lister vises skyderen ikke.
  Skiftet til to spalter holder nu desuden også kontakterne *aldrig
  igen*.

- **Billedlisten kan åbne sig selv før hver kørsel.** Den, der vil
  beslutte om hvert billede enkeltvis, sætter under „Billeder" den nye
  kontakt *Fastlæg enkeltvis før hver kørsel*. Listen med
  forhåndsvisning vises da automatisk ved rensning, i stedet for at
  du skal klikke på „Fastlæg enkeltvis …" hver gang selv; afbryder du
  den, renses der heller ikke. Indeholder ingen af de valgte filer
  et billede, vises intet. Kontakten er som standard fra.
- **Maskuro finder håndskrevne underskrifter på PDF-sider og fjerner
  dem fra billedpunkterne.** Hidtil blev navnetrækket stående under et
  renset dokument – teksgenkendelsen læser trykskrift, og det, den
  ikke læser, erstattes ikke. Søgningen er en egen kontakt og kræver en
  genkendelsesmodel, som indlæses en enkelt gang.

  Den finder målt cirka 84 af 100 underskrifter og dækker dem til
  omkring fire femtedele. Det er en hjælp og ikke en garanti: Efter
  hver kørsel står der i rapporten, hvor mange der blev fundet – også
  når der ingen var, for det kan betyde, at der ingen er, eller at en
  blev overset. På 72 rigtige forretningssider uden underskrift har den
  ikke opfundet nogen.

  En **tegnet** underskrift bliver fundet, men ikke fjernet: Den består
  af linjer, ikke af billedpunkter, og en bjælke ovenpå ville kun være
  en tildækning, hvorunder linjerne stod tilbage. Sådanne steder tælles
  og nævnes, så man selv kan sortslør dem i redigeringsvinduet.

  Word-, Excel-, PowerPoint- og OpenDocument-filer gennemsøges ikke
  automatisk for underskrifter. Brugerflade, førsteopsætning,
  modeldownload, kommandolinje og håndbog nævner nu udtrykkeligt denne
  grænse.

- **Rundvisningen fører nu også gennem forhåndsvisningen – vinduet, hvor
  du beslutter.** Ved øvelsesdokumentet åbner den sig selv, også hvis du
  ellers har slukket forhåndsvisningen (din indstilling forbliver, som
  den er). Der forklares, hvad farverne betyder, hvorfor der kun står
  ét spørgsmål pr. linje – er der overhovedet en person? – og hvad
  „aldrig igen" er godt for. Ved farverne ligger fokus på en godt belagt
  linje, som regel IBAN'en – det grønne eksempel, som sætningen nævner;
  derefter på den svagest belagte, og der må du klikke midt i
  forklaringen: kontakt væk, værdien bliver stående i dokumentet. Ved en
  lang liste åbner vinduet for rundvisningen større, så forklaringen
  ikke ligger over linjerne. Åbner vinduet en anden gang, forklarer
  rundvisningen også hvorfor – den færdige side læses igen som et
  billede, og derved opstår brudstykker, der ligner et navn.

- **Editoren åbner stort første gang.** Original, resultat, værktøjslinje
  og fundliste står ved siden af hinanden og havde i den hidtidige
  standardstørrelse for lidt plads. Den, der trækker vinduet mindre,
  får sin størrelse igen næste gang – ingen bliver overstyret.

- **Et dobbeltklik på en pladsholder henter den tilbage** – i Word,
  Excel, PowerPoint, OpenDocument, tekst, e-mail og HTML. Og den, der
  trækker over flere pladsholdere og vælger „Hent valg tilbage", henter
  alle deri liggende tilbage på én gang. Man behøver altså ikke længere
  ramme den firkantede parentes præcist. Pladsholdere, der ved
  anonymisering står for flere forskellige værdier, er undtaget herfra
  – de tælles og nævnes, gættes ikke.

- **Håndbogen har et kapitel „Forhåndsvisning før erstatning".** Vinduet
  er forudindstillet til, og det er det eneste, hvor du beslutter – i
  håndbogen stod det hidtil kun i en bisætning. Nu står der, hvad en
  kontakt betyder (den gælder for **hvert** fund, ikke kun det
  opførte), hvorfor der pr. linje kun skal besvares ét spørgsmål, hvad
  „aldrig igen" varigt bevirker, og hvorfor vinduet kan åbne en anden
  gang ved en PDF. På alle atten sprog, og i indstillingernes liste er
  kontakten nu også opført.

### Ændret

- **Fanen „Erstattede værdier" har en skyder over farverne, og
  læringstilstanden står ikke længere der.** Ved mere end otte værdier
  sidder over listen den samme skyder som i forhåndsvisningsvinduet:
  *Skjul godt belagte* tynder visningen ud til det, der virkelig skal
  gennemgås. På dokumentet ændrer det intet, og hvor mange linjer af
  hvor mange der ses, står under – søgefelt og skyder tælles sammen.
  Kontakten *Læringstilstand* er forsvundet fra fanen; den står fortsat
  i menuen *Værktøjer* og i værktøjslinjen.

- **Fanen „Erstattede værdier" viser nu de samme farver som dokumentet.**
  Hver linje deri er farvelagt som stedet i dokumentet og som værdien i
  forhåndsvisningen: Rød betyder „gættet alene, her lønner det andet
  blik sig først", grøn „genkendt af et navngivet mønster". Inden for
  hver type står det mest usikre øverst – du arbejder altså listen
  igennem oppefra og ned og har set det vigtigste først. Hidtil stod
  alt lige lyst og alfabetisk sorteret.

- **Læringstilstanden er fra ab fabrik.** Efter en rettelse i
  redigeringsvinduet spurgte programmet hidtil selv, om der skulle blive
  en egen regel ud af det. Dette spørgsmål kommer midt i arbejdet; den,
  der ikke har bestilt det, oplever det som en afbrydelse. Den, der vil
  have reglerne, slår knappen *Læringstilstand* til i værktøjslinjen –
  valget gælder derefter varigt, i begge retninger.

### Rettet

- **Eksporterede regelfiler mærkes nu udtrykkeligt som beskyttelseskrævende.**
  Egne begreber og undtagelser kan stå deri i klartekst; desuden kan
  filen indeholde det hash-salt, som formodede værdier bekræftes med.
  Den vellykkede eksport viser derfor en advarsel og opfordrer til at
  beskytte filen og kun videregive den bevidst til berettigede modtagere.

- **Den sidste sikkerhedskontrol tilbageholder ikke længere rensede
  kontorfiler på grund af deres egne pladsholdere.** En typeforkortelse
  som „SVNR" står også i `[SVNR1]`; hidtil gjaldt det som en formodet
  klartekstrest, og den færdige fil blev kasseret. Samtidig efterspores
  nu også telefonnumre og IBAN'er, hvor Office lægger samme angivelse
  uden synlige mellemrum i en reference eller en indlejret fil.

- **Word, Excel, PowerPoint og OpenDocument efterlader ikke længere en
  sent opdaget feltkopi.** Genkendes en værdi først i en biopbevaring
  eller indlejret kontorfil, rydder en snæver eftergang også de
  tidligere læste synlige og skjulte kopier op. Allerede oprettede
  referencepladsholdere erstattes ikke endnu en gang derved.

- **Ved enkeltvis tilbagehentning af en Word-rullegardinliste kommer der
  ikke længere et nabovalg ubedt med tilbage.** Det fuldstændige
  originalafsnit overtages først, når også dets attributter ikke
  længere indeholder åbne pladsholdere.

- **Dårligt læsbare scanninger mister færre sammenhørende angivelser.**
  En alternativ OCR-læsning med tiltaleform og topartsnavn bevares;
  gadefragment, husnummer og postnummer-by beskytter i fællesskab hele
  adresselinjen, også når den falder i naboliggende OCR-blokke. Fakturæ-
  og artikelfelter samt begivenhedslinjer ved siden af tages ikke med
  derved. En gyldig dato, der efter „født" er faldet i flere OCR-ord og
  tegnsætning, gøres ligeledes fuldstændigt ukendelig.

- **Succes-konfettien er nu synlig ved automatisk åbning af editoren.**
  Konfettien sprøjter direkte fra *Rensnings*-knappen i stedet for
  at regne ned fra øverste vinduesrand. Editoren venter kun på det
  første, 850 millisekunder korte spray og åbner derefter automatisk;
  uden aktiveret konfetti er der fortsat ingen forsinkelse.

- **Sidetæller og zoomlinje springer ikke længere frem og tilbage ved
  overkørsel af visningsikonerne.** Qt omfordelte statuslinjens frie
  plads, så snart et symbols tip dukkede op der. Begge betjeningsgrupper
  beholder nu deres naturlige bredde og faste position ved hover.

- **Hastighedsmålingen af en tilkoblet KI-server fejlede altid** – på
  hver server, siden den egne KI kom. Den spurgte med en snæver
  svargrænse og forsøgte derefter at læse det derved afskårne svar; det
  måtte mislykkes, og der blev gemt „ikke målt". Følgerne var overalt
  synlige: Varighedsestimatet regnede din server med tempoet fra den
  medfølgende model på en kontormaskine, og i indstillingerne stod der
  varigt, at hastigheden endnu ikke var målt. Der måles nu på mængden,
  serveren har genereret, og ikke på indholdet af dens svar.

- **„Maksimal genkendelse (KI) – langsom" stod der også, når det ikke
  passede.** Betegnelse og bemærkning beskrev den medfølgende model på
  en kontormaskine – „en sprogmodel på denne maskine", „ved store
  dokumenter op til en time". Den, der har tilkoblet en egen KI-server,
  læste to forkerte ting der: Der regnes ikke på hans maskine, og der
  svares på sekunder i stedet for timer. Begge dele kommer nu fra
  målingen. Foreligger der ingen, påstår programmet intet mere, men
  siger, at der endnu ikke er målt.

- **Tilbagehentning virker nu også på et trukket udvalg.** Den, der
  trak over flere pladsholdere og ville trykke *Hent udvalg tilbage*,
  fandt knappen grå: Den blev kun aktiv, hvis markeringen var **netop**
  én pladsholder – trukket over et afsnit er den det aldrig. Vejen
  dertil fandtes allerede, blot kom ingen frem. Nu er det nok at
  markere området; alle pladsholdere deri kommer tilbage i ét greb.

- **Tilbagehentning gik ned, når sammenligningsluppen var åben.** Luppen
  husker stedet under musemarkøren for at følge med i originalen. Ved
  genindlæsning efter en tilbagetagning gav den dette sted tilbage i en
  form, som tekstvisningen ikke kunne bruge til noget – og fordi en
  sådan fejl midt i brugerfladen afslutter programmet, var
  tilbagetagningen blevet et nedbrud. Luppen står i grundstillingen
  åben, det ramte altså den almindelige vej.

- **Efter tilbagehentning springer visningen ikke længere til
  dokumentbegyndelsen.** I et længere brev var stedet, man netop
  arbejdede på, væk efter hvert håndgreb. Nu bliver afsnittet, der stod
  øverst før, stående øverst.

- **Uden LibreOffice fortæller sidevisningen, hvor det kommer fra, i
  stedet for blot at mangle.** De to knapper *Sidevisning* og *Sortslør
  som PDF* var spærrede og nævnte kun i tooltippen, at der ikke blev
  fundet noget LibreOffice; en vej dertil fandtes ingen steder i
  programmet. Et klik åbner nu en henvisning med vejen til det gratis,
  åbne LibreOffice. Håndbog og FAQ stod forkert her – de bebudede en
  eftermonterbar komponent, som programmet ikke tilbyder.

- **Før udlevering gennemsøges den færdige fil en sidste gang helt –
  nu også ved Word, Excel, PowerPoint, LibreOffice, e-mail, HTML og
  tekst.** Hidtil havde kun PDF'en dette sidste kig. Alle kontroller
  forinden ser efter et sted, som nogen har navngivet forinden; en
  opbevaring, ingen har tænkt på, kontrolleres derfor heller ikke af
  nogen. Til sidst gennemsøges filen nu blot for alt, hvad der er
  blevet erstattet – i hver del af pakken. Står der noget tilbage,
  opstår der **intet** resultat, og meldingen nævner værdien. En fil,
  der anses for renset, er værre end slet ingen.

- **Navne, der står i `<script>` og `<style>`, meldes nu.** Begge
  forbliver fortsat urørte – der står programtekst, og en erstatning
  midt i et betegner gør en webside til en ødelagt webside. Det blev
  bare ikke sagt hidtil, og det var fejlen: En stilregel
  `content: "Anna Musterfrau"` står **synligt** for modtageren på skærmen,
  og i resultatet blev den stående, mens programmet meldte siden som
  renset.

- **I indstillingerne kan tillægsmodellerne igen indlæses og fjernes.**
  Knappen ved siden af „Udvidet genkendelse" og „Maksimal genkendelse
  (KI)" endte ved tryk i fejlmeldingsvinduet i stedet for at hente
  modellen. Den anden vej – kontakten i genkendelsen, der selv spørger
  om modellen – var aldrig berørt heraf.

- **Navne, der ligger i ark- og områdenavne i en tabel, meldes nu.**
  Navnet på et ark står på fanen forneden, navnet på et navngivet
  område i navnefeltet og i hver formel, der bruger det. Ingen af dem
  erstattes fortsat – formler henviser via dem, og en mappe med
  referencefejl hjælper ingen –, men det står nu der. Hidtil kom
  meldingen kun for arknavnet i en Excel-mappe: Et navngivet område
  „Bezuege_Brunnthaler" gik stille med ud, og ved en LibreOffice-tabel
  tav programmet helt. Et ark „Notizen Ortner" gjaldt derved som
  renset, og modtagerens første blik faldt på navnet.

  Der meldes kun, hvad der reelt fører til en person: et ord, der
  alligevel blev erstattet i samme mappe, eller et fund, der vælger ud
  af flere ord. Et enkeltstående ord som „Zustaendig" eller
  „Bezug_Umsatz" udløser ikke længere nogen advarsel – før ville det
  have gjort det, og en advarsel, der kommer ved hver anden mappe,
  læser ingen efter den tredje mere.

- **„Hent original tilbage" henter nu virkelig alt tilbage.** I nogle
  dokumenter manglede der bagefter enkelte tegn – af „Seestraße 14" blev
  „Seestraße 4", af „An:" et „An", af „nordlicht-planung" et
  „nordlicht planung" –, og enkelte linjer kom slet ikke tilbage. Netop
  der kunne der derefter ikke længere markeres noget med musen, og
  intet kunne sortsløres: Teksten stod ganske vist på papiret, men
  programmet kendte den ikke længere. Berørt var smalle tegn – ettallet,
  kolonet, bindestregen – i dokumenter, der sætter hvert tegn enkeltvis;
  øvelsesdokumentet er et af dem.

- **Og samme dokumenter forvandles ikke længere til et billede ved
  rensning.** Fordi et sådant tegn blev stående, meldte
  efterkontrollen en rest, og siden blev forsigtighedsvis rastreret.
  Teksten derpå var derefter kun et aftryk: ikke længere søgbar, ikke
  længere markerbar, større i filen. Øvelsesdokumentet forbliver nu
  ægte tekst på begge sider.

- **Farvede markeringer bliver ikke længere stående over tilbagehentet
  tekst.** Den, der fortrød en erstatning, så det farvede rektangel
  fortsat over det genoprettede ord – det påstod „her blev noget
  fjernet", selvom originalen igen stod der.

- **En bjælke afslører ikke længere, hvor langt ordet nedenunder var.**
  Ved sortsløring dækker bjælken i korte linjer nu **hele** linjen –
  adresseblok, tophoveddata, smal tabelcelle. Passer hele linjen ikke
  (den almindelige tabellinje med tre spalter), forbliver det ved
  feltet; i en flydetekstlinje forbliver det ordpræcist, ellers gjorde
  et navn midt i sætningen hele sætningen sort. Og bjælker, der står
  under hinanden, gøres **lige lange**: I adresseblokken står der en
  værdi på hver linje, og tre forskelligt lange bjælker afslørede
  fortsat, hvor lange linjerne var. De vokser dog kun så langt, som
  papiret er frit – foran en nabospalte holder bjælken op.

- **„Hele linjen" sortslør nu virkelig hele linjen.** Hidtil endte
  bjælken ved næste større mellemrum – altså ved feltets ende. I
  flydetekst gjorde det ingen forskel, dér er feltet linjen; i
  tophoveddata og tabeller gjorde det: Af „Name: Anna Musterfrau
  Abteilung: Vertrieb" blev en bjælke, der endte præcis ved navnets
  sidste bogstav – og dermed stod dets længde stadig på arket. Bjælken
  løber nu fra linjens første til sidste ord og tager nabospalterne med.
  Den, der kun vil ramme værdien, vælger „Ord"; automatikken sortslør
  fortsat feltvis.

- **Før udlevering gennemsøges den færdige fil en sidste gang.** Alle
  hidtidige kontroller ser efter et sted, som nogen har navngivet
  forinden – sidetekst, fundrektangel, billedflade. En PDF har dog
  flere opbevaringer, end en opremsning kan rumme: Bemærkninger,
  formularværdier, bogmærker, dokumentinformationer, filbilag,
  JavaScript. Til sidst gennemsøger Maskuro derfor den skrevne fil blot
  for alt, hvad den har erstattet – overalt undtagen i sidetekst, hvor
  samme ordlyd også lovligt kan stå. Står der noget tilbage, opstår der
  **intet** resultat, og meldingen nævner værdien. Et dokument, der
  anses for renset, er værre end slet intet.

- **Hvad der ikke kunne kontrolleres, gælder ikke længere som
  kontrolleret.** Ad tre veje så et mislykket efterkontrol hidtil ud
  som et rent resultat. En side, hvis tekstlag ikke kunne læses, gjaldt
  som særligt ren – der var jo intet at finde; den rastreres nu. Kunne
  en side med tilbageværende fund ikke rastreres som erstatning, blev
  den udleveret uden videre; nu afbryder rensningen hellere. Og
  modprøven i redigeringsvinduet meldte efter en egen fejl „intet
  tilbage" – i vinduet ikke til at skelne fra, at alt blev fjernet; nu
  vises advarslen med knappen „Rastrér side".

- **„Nulstil til standard" nulstillede slet ikke de fleste
  indstillinger.** Ni ud af toogtyve kontakter stod uændrede efter
  håndgrebet – deriblandt forhåndsvisningen, „Åbn rensede filer
  bagefter", redigeringsvinduet, den øjeblikkelige aflæggelse og begge
  opdateringskontakter. Den gemte fil var ganske vist tømt, men vinduet
  holdt de gamle værdier fast og skrev dem ind igen ved næste klik. Nu
  kommer hver kontakt tilbage, og bemærkningen „ændret" forsvinder med
  den.
- **„Læg automatisk kontrolrapport pr. rensning" viste sig sat, men
  var fra.** Efter nulstillingen forblev kontakten sat, mens værdien var
  slettet – der opstod ingen rapport mere, uden at noget viste det.
  Det samme gjaldt kontrolloggen og den egne skærmoptagelse; deres
  tastaturgenveje ved nulstilling til- eller framedles nu også korrekt
  med det samme.

- **Bjælkerne på en linje ser nu ens ud.** Hidtil medbragte hvert fund
  sin egen bjælke, og dens højde kom fra det ramte ords skrift. På en
  linje med mærkning og værdi i forskellige størrelser stod derfor en
  tyk og en tynd streg med forskudte kanter ved siden af hinanden, og
  hvor kun et mellemrum adskilte to fund, blev der en lys spalte
  ovenover. Bjælker på samme linje har nu samme over- og underkant, og
  hvad kun et mellemrum adskiller, bliver til én bjælke. Hvad der skal
  blive stående mellem to fund – kommaet efter navnet, en mærkning, et
  beløb – holder dem fortsat adskilt. Gælder for satte sider som for
  scanninger.

- **Fanebladene under „Om dette program" starter igen øverst.**
  Databeskyttelse, licensbetingelser og licensbemærkninger åbnede sig
  midt i teksten – den, der læste dem, måtte først rulle helt op for
  at se den første linje.

- **Pennen åbner ikke længere et andet redigeringsvindue, men henter det
  eksisterende frem.** Hidtil opstod der et nyt ved hvert klik. Vinduet
  har ingen egen post i proceslinjen – den, der minimerede det, kom
  ikke til det igen og klikkede en gang til; ved genoprettelse af
  hovedvinduet kom alle ophobede vinduer så frem på én gang. Nu havner
  yderligere dokumenter i det åbne vindues fanebladslinje, og et
  dokument, der allerede står der, får ikke en anden fane.

- **„Udvidet genkendelse" bærer ikke længere bemærkningen „ændret", så
  længe dens model mangler.** Den leveres slået til, men uden den
  eftermonterbare model kan den slet ikke være det – i indstillingerne
  stod linjen derfor på hver nyopsat maskine som ændret, selvom ingen
  havde rørt den. Hvorfor kontakten er fra, siger nu udelukkende dens
  betegnelse: „Model endnu ikke indlæst".

- **Introduktionsstrimlen forklarede i kontor- og tekstfiler
  PDF-lærredet.** Der stod „klik på et ord for at sortslør det" – i en
  Word-fil sortslør et klik dog intet, dér markeres og trykkes derefter
  på en knap. Den siger nu, hvad der gælder i den pågældende visning.
- **Værktøjslinjen var tilstoppet med mærkninger i tekstvisningen.**
  „Erstat udvalg", „Sortslør udvalg", „Hent udvalg tilbage",
  „Sidevisning" og „Sortslør som PDF" står nu som symbol – som deres
  søskende i en PDF. Deres navne forbliver i kort hjælp og menu.
- **Ctrl+musehjul i sammenligningsluppen flyttede ikke dens
  zoomregulator med.** Skriften blev større, regulator og procenttal
  ved siden af påstod fortsat den gamle stand.
- **Opdateringens installationsprogram kom ikke frem** – man måtte
  først klikke på det i proceslinjen (kun Windows).
- **Et årstal ved linjebegyndelsen gjaldt som østrigsk postnummer.** I
  et cv blev „2020 Salgsstrategier" til en pladsholder – hele linjen
  forsvandt. Et firecifret tal mellem 1900 og 2099 kræver nu et andet
  adressesignal: gaden ovenover, et feltord foran, en landekode eller
  et kendt stednavn. Adresseblokke har det; årstalskolonner ikke.
- **Et måned-år-par gjaldt som telefonnummer.** Af „Siden 08.2010
  123-Verkauft GmbH" blev en „telefonnummer" – måned, år og de første
  cifre af firmanavnet derefter.
- **Rapporten sagde „kontrolleret via teksgenkendelse" og fortav, hvad
  den ikke læser.** Bevares billeder, står der nu ved siden af, at
  håndskrevet indhold deri ikke findes – en underskrift eller et
  håndskrevet indført navn bliver stående. Hidtil stod denne sætning
  kun ved scannede sider; en almindelig PDF med en indlejret underskrift
  fik intet ord om det.
- **En pladsholder på sortsløret billedgrund stod i venstre kant af sin
  bjælke.** Findes en værdi i et billede – fx et tastet navn ved siden
  af en indscannet underskrift –, skal billedområdet sortslør i fuld
  bredde. Den kortere pladsholder lod nøgen sort blive stående ved
  siden af, hvilket lignede to processer. Den sidder nu centreret på
  bjælken.

## 0.10.41-alpha.20260826 – 26. august 2026

### Nyt

- **Efter prøveperioden minder et vindue én gang pr. start om licensen.**
  Det kommer fem minutter efter start – ikke straks, så det ikke står i
  vejen for nogen før det første håndgreb – og venter, så længe en
  rensning kører. Derfra fører en vej til køb og en til indtastning
  af en allerede købt nøgle; „Senere" lukker det, så snart de fem
  sekunder i knappen er gået. Der spærres intet: Det gratis niveau
  fungerer videre som hidtil.

- **Ventetiden før en kørsel i det gratis niveau varer nu ti i stedet
  for tredive sekunder.** Den skal minde om licensen, ikke stoppe
  arbejdet.

- **Alle tre licensbemærkninger ser nu ens ud.** Ventetid, påmindelse i
  de sidste prøvedage og bemærkning efter prøveperioden bærer samme
  bånd, samme opbygning og samme knapper; resttiden står i knappen i
  stedet for som stort tal ved siden af.

- **Fundlisten i forhåndsvisningen står igen under hinanden.** Den var
  fra ni værdier tospaltet; ved gennemgang springer øjet derved mellem
  to baner, og der besluttes her linje for linje. Den, der kan lide de
  to baner, slår dem til igen nederst til venstre i vinduet – valget
  gemmes, og allerede fravalgte værdier forbliver fravalgte ved skiftet.

- **KI-niveauet står nu åbent for alle, der tilkobler en egen
  KI-server.** „Indstillinger → KI" bærer det hele: tilkoblingen, hvad
  KI'en må gøre, hvad den får til opgave – og over det kontakten for
  niveauet samt modprøven, så snart en server er indtastet. En
  sprogmodel, der beregner på den egne arbejdsplads, holdes fortsat
  tilbage: Den kræver flere minutter til ti sider og er dermed ikke
  noget for hverdagen.

- **En egen KI kan tilkobles.** I stedet for den medfølgende sprogmodel
  kan en større model svare på en anden maskine – på en server i huset
  eller en arbejdsstation med kraftigt grafikkort. Der kræves en
  tjeneste med OpenAI-kompatibel grænseflade (Ollama, LM Studio,
  llama.cpp-server, vLLM, LocalAI); den opsættes under „Indstillinger →
  Egen KI" med en forbindelseskontrol, der rent faktisk spørger
  modellen, måler tempoet og fastslår den mulige svarform. Flere
  tekstafsnit kører samtidig i stedet for efter hinanden.

- **Hvad KI'en må gøre, og hvad den får til opgave, kan nu indstilles.**
  Tre kontakter afgør grænsetilfældekontrol, selvstændig søgning og
  søgning i flydetekst; instruktionen til modellen står ordret der, kan
  suppleres med husets egne begreber og nulstilles til standard med en
  knap.

- **Forlader teksten dermed det eget netværk, advares der før hver
  kørsel.** Maskuro genkender på adressen, om KI-serveren står i huset,
  og nævner en kendt udbyder ved navn. Advarslen kan slås fra, men kun
  mod udtrykkelig bekræftelse af at være bemyndiget til denne
  overførsel, og kun for netop denne adresse. Selve forløbet ændres
  ikke af det: Overførslen står fortsat i loggen og i kontrolrapporten
  for hver fil. På kommandolinjen spørges der ikke, men standses –
  dér kræves `--ki-auswaerts-erlauben`.

- **Forhåndsvisningen før erstatning er som standard aktiv ved nye
  indstillinger og gælder nu også for udtrykkeligt rensede
  udklipsholder-indhold samt tekst og billeder, der indsættes i
  programmet.** Ved dokumentbatches vises fortsat netop én
  forhåndsvisning pr. dokument med alle sider; den stille øjeblikkelige
  rensning af korte kopier åbner bevidst ikke noget vindue.

- **Fund kan slås til og fra i forhåndsvisningen over hele den farvede
  linje.** Kontakten er nu stor og kontrastrig; desuden viser et
  statusfelt „Erstat" henholdsvis gennemstreget „Erstat", så valgte og
  fravalgte værdier straks kan skelnes fra hinanden, også på mørke
  sikkerhedsfarver.

- **Også PDF'er med synligt sikkerheds-modblik åbner forhåndsvisningen
  nu kun én gang pr. dokument.** Fravalgte begreber forbliver fravalgt
  for det senere sidevidne; dets kontrol kører videre uden at afbryde
  samme kørsel med en anden dialog.

- **Erstatningsord ser i redigeringsværktøjet ens ud, også på
  rastrerede sider.** Ligger den røde pladsholder i billedpunkterne i
  stedet for i PDF-tekstlaget, får den nu alligevel samme
  konfidensfarvede baggrundsflade som en almindelig
  PDF-tekstpladsholder.

- **Allerede forhåndsvisningen før erstatning viser kontrolbehovet for
  de fundne begreber.** Hver linje bærer samme rød–orange–grøn-farve
  som senere erstatningen i editoren. Inden for en kategori står lav
  sikkerhed og røde falsk-alarm-kandidater øverst, stærke grønne beviser
  nederst; uafgjorte forbliver alfabetiske. Kommer samme værdi fra flere
  fund, tæller forsigtighedsvis deres mest tvivlsomme vurdering.
  Uvurderede særtilfælde står neutralt gule mellem rød og orange.

- **Resultatet kan nu kopieres direkte fra redigeringsværktøjet som en
  fil.** „Kopiér resultat" lægger den aktuelle rensede udgave i
  udklipsholderen uden at lukke editoren og genfinde filen i
  hovedlisten. Ved en endnu ikke gemt håndredigering kører forinden
  automatisk den fulde sikre gemmevej; „Kopiér billede" forbliver en
  separat funktion for rene billedpunkter.

- **Erstattede ord viser i editoren med ét blik, hvad der først skal
  kontrolleres.** Ren sprogmodel-gætteri er rødt, også når spaCy melder
  en generel sikkerhed på 85 procent. Yderligere ustøttede
  modeldomme forbliver højst orange; stærke navngivne beviser kan blive
  grønne. Håndarbejde og ældre tildelinger uden vurderbar bedømmelse
  forbliver neutralt gule. Også automatiske sortsløringsbjælker bærer
  disse farver i editorens forhåndsvisning – nu også, når bjælken er
  del af en rastreret PDF-side. Dertil skal tildelingen passe og den
  tidligere ordkasse dokumenterligt være dækkende sort; almindelig
  fed skrift farvelægges ikke. I den gemte PDF forbliver alle bjælker
  uændret dækkende sorte.

- **Hvad der fravælges i forhåndsvisningen, kan huskes varigt.** Hvor du
  fjerner kontakten, siger du: Her har genkendelsen taget fejl. Hidtil
  gjaldt det kun for dette ene dokument. Nu vises der en kontakt „aldrig
  igen" ved linjen; trykket kommer værdien varigt ind i listen „Fjern
  aldrig" og gælder fremover som uproblematisk i ethvert dokument.
  Under listen står, hvad der bliver varigt, før du trykker „Erstat".
  Den omvendte retning findes bevidst ikke: Hvad der én gang blev
  fundet, finder genkendelsen igen.

- **En knap nulstiller alle indstillinger til leveringsstanden.** Den
  står nederst til venstre i indstillingsvinduet og spørger først
  bagefter. Dine filer, din licens, dine egne genkendelsesregler og
  autostarten berøres ikke; hvad din administration foreskriver, gælder
  fortsat. Enhver indstilling, der afviger fra leveringsstanden, bærer
  desuden bemærkningen „ændret" – så ses det med ét blik, hvad man har
  stillet om på.

### Ændret

- **Et resultat aflægges ikke længere af sig selv – først ved lagring.**
  En kørsel fra vinduet skriver først sin rensede udgave til et
  midlertidigt sted; filen „…_bereinigt" ved siden af originalen opstår
  først, når du trykker „Gem". Indtil da kan resultatet ses, efterredigeres
  og kopieres. Hver færdig linje har dertil en gem-knap, under listen
  står „Gem alle", og i editoren gælder Ctrl+S. Den, der tømmer listen
  eller afslutter programmet, bliver spurgt; hvad ingen aflægger, bliver
  heller ikke liggende noget sted. „Vis i mappe" er spærret før
  lagring – det midlertidige sted er ikke et mål, man sender nogen hen
  til. Tildelingsfilen følger med ved lagring.

  I indstillingerne under „Program" henter „Aflæg resultater
  øjeblikkeligt ved siden af originalen" den hidtidige adfærd tilbage.
  Kommandolinje, mappevagt og udklipsholdervagt aflægger uændret
  øjeblikkeligt – dér sidder ingen, der kunne gemme.

- **Redigeringsværktøjets værktøjslinje er ryddet op.** Læringstilstanden
  står nu yderst til højre ved sammenligningslup og „Erstattede værdier"
  – de tre kontakter, der slår en driftsform til og fra, står dermed
  samlet. „Overfør til alle sider" er flyttet til de tre
  sortsløringsformer, fordi det kun gør noget dér. „Kopiér resultat",
  „Fil – Nulstil" og „Overfør til alle sider" klarer sig uden mærkning;
  deres navn står fortsat i tooltip og menu. Mellem „Erstat" og „Hent
  original tilbage" står en skillestreg: De to er hinandens modsætning
  og så ved siden af hinanden ud som to varianter af samme værktøj.

- **Symbolet for „Kopiér resultat" viser nu et dokument.** To ark med
  bukket hjørne og tekstlinjer i stedet for to ens ark med en lille
  hjørnepil. „Kopiér billede" bærer til gengæld billedtegnet, så begge
  kan skelnes fra hinanden uden mærkning. Knappen „Kopiér" i
  resultatlisten viser det samme dokumentsymbol – den lægger den samme
  fil.

- **Indstillingerne er sorteret og forsynet med overskrifter.**
  „Genkendelse" har nu fire afsnit: *Hvad fjernes*, *Hvordan erstattes*,
  *Hvor grundigt søges* og *Før og efter kørslen*. Ansigtsgenkendelse
  og stribe-/QR-koder står ved billederne, hvor man leder efter dem;
  „Program" er delt i *Resultatfiler*, *Ved start*, *Opdatering*,
  *Visning* og *Tilbagemelding til os*, og resultatfilens navnetilføjelse
  står ved resultatfilerne i stedet for mellem sprog og udseende.

- **Den udvidede genkendelse er slået til ab fabrik**, også før dens
  sprogmodel er indlæst. Tidligere hang standarden sammen med
  modelbeholdningen, og en nyopsat maskine kørte varigt på det svagere
  niveau. Opsætningsvinduet tilbyder modellen til indlæsning på første
  side og nævner prisen ved siden af. Mangler den, siger kontakten det
  fortsat, i stedet for at foregive et niveau, der ikke kører.

- **De to begrebslister hedder nu det, de gør:** „Fjern altid" i stedet
  for „Egne begreber" og „Fjern aldrig" i stedet for „Undtagelser".

- **Forhåndsvisningsvinduet er mere overskueligt.** Fra ni værdier står
  de i to spalter, linjerne er fladere, og antallet af fund står
  direkte efter begrebet i stedet for i højre kant.

- **I redigeringsværktøjet står Erstat før Sortslør** – i
  værktøjslinjen, i menuen „Værktøjer" og ved højreklik på siden.
  Erstat er hovedreglen: En pladsholder kan klikkes og hentes tilbage,
  en bjælke ikke.

- **Færre dobbelte knapper i editoren.** „Gem som …" og „Kopiér billede"
  står nu kun i menuen Fil, med deres sædvanlige tastaturgenveje. I
  linjen bliver hver af dem tilbage: Gem og „Kopiér resultat" – hvor der
  gemmes til, står under alle omstændigheder i statuslinjen og kan
  ændres der med et klik.

- **Udklipsholdervagten tilbydes ikke længere ved første start.** Den
  griber ind i hver kopieringshandling i systemet; den, der ser
  programmet for første gang, kan ikke vurdere det. I indstillingerne
  står den fortsat, dér med det tilhørende forbehold ved siden af.

- **Det lyse udseende blænder mindre.** Vinduesgrunden kom hidtil fra
  det pågældende systemudseende og var dermed den eneste store flade,
  ingen havde besluttet – under Windows næsten hvid. Nu er den et
  brudt hvid, ens på hvert system.

- **Rundvisningen og håndbogen forklarer farverne.** Hvad rød, orange,
  grøn og gul betyder bag et erstattet ord, står nu som en egen station
  i rundvisningen og som et afsnit i håndbogen – på alle sprogudgaver.

### Rettet

- **Håndbog og FAQ viste pladsholdere, der ikke findes mere.** Siden
  overgangen til den korte form skriver Maskuro `[NAM1]`; i hjælpen
  stod fortsat `[NAME1]`, og sætningen „Standardindstillet er `[NAME1]`"
  var dermed simpelthen forkert. I de sytten oversatte udgaver stod
  desuden den **tyske** kode i stedet for den egne – en spansk læser så
  `[NAME1]`, hvor hans program skriver `[NOMB1]`. Ligeledes
  resultatfilens endelse: Der lovede alle udgaver `_bereinigt`, mens
  programmet opretter `_limpiado`, `_nettoyé` eller `_除去済み`. Berørt var
  også den nummerløse form (ved anonymisering hedder alt `[NAM]`, ikke
  `[NAME]`) og den fra værdien afledte kode ved hashing.

- **Forhåndsvisningsvinduet afbryder nu kun én gang pr. dokument – og en
  anden gang kun, hvis der virkelig kommer noget nyt til.** En PDF
  læses fra to sider: én gang fra indholdsstrømmen og til sidst fra den
  gengivne, synlige side. Hidtil spurgte hver af de to for sig. Nu
  gælder: Hvad du besluttede i det første vindue, gælder videre, og
  værdier, der allerede stod der, kommer ikke igen. Finder synskontrollen
  af de færdige sider derimod noget, som ikke stod nogen steder
  tidligere, får du det forelagt igen – alene, uden de allerede
  afgjorte værdier.

- **Forhåndsvisningsvinduet siger nu, hvad man skal beslutte ud fra.**
  I stedet for „Fjern kontakt = værdien bliver stående" – hvad kontakten
  *gør*, men ikke, hvornår man skal fjerne den – står der nu: Kontakt
  væk overalt, hvor der ikke står en personrelateret værdi; dér har
  genkendelsen taget fejl. Desuden nævner hvert vindue det kontrolløb,
  dets værdier stammer fra.

- **Pladsholdere ser ens ud i hele dokumentet.** På sider, der genopbygges
  som billedsider i OCR-vejen, blev synlige pladsholdere hidtil sat i
  skrivemaskineskrift – „[PLZ4]" stod da bredt og med seriffer ved
  siden af et smalt „[NAM1]" på samme side. De bærer nu samme
  seriffri skrift som alle andre steder og sættes heller ikke bredere,
  end der var planlagt ved tilpasningen. Det usynlige søgelag beholder
  sin egen skrift – det kræver pålidelige mål, ikke udseende.

- **I editorens værktøjslinje står der ikke længere doble skillestreger.**
  Hvor en hel værktøjsgruppe bortfalder for den åbnede filtype – i en
  PDF fx sidevisning og gengivelse – blev begge streger omkring
  hullet hidtil stående.

- **Ved tilbagehentning bliver der ikke længere lejlighedsvis kun et
  hvidt sted tilbage.** En allerede eksakt genoprettet originaltekst
  overmales ikke længere hvid af den brede, sammenfattede kasse fra
  dens fjernede pladsholder. Ved blandede tekst- og billedtilbagehentninger
  indsættes tekst desuden kun usynligt, hvis sidebilledet allerede
  synligt bærer netop denne originaltilstand. Det gælder for rammer,
  fundpanel og PDF-bilag.

- **„Hent original tilbage" tilbyder ikke længere unødigt at rastrere
  siden.** Den strenge resttekstkontrol forbliver aktiv ved sortsløring
  og erstatning. Ved tilbagehentning udelades den: Dér tilføjes
  originalindhold bevidst igen, og uændrede naboord i den udvidede
  tilbagehentningsramme var ikke en rensningsfejl, men en falsk
  alarm.

- **Rundvisningen gennem editoren forklarer nu „Erstat" og „Hent original
  tilbage" som egne trin.** Begge værktøjer fremhæves direkte i linjen
  og beskriver, at en trukket ramme indsætter en pladsholder henholdsvis
  henter det oprindelige indhold på dette sted tilbage fra kildefilen.

- **Også landespecifikke pladsholdere forbliver nu på højst fire
  bogstaver.** Disse typer manglede hidtil i det centrale kodekatalog og
  kunne derfor fortsat fremstå udskrevet i fuld længde, fx
  `[UMSATZSTEUER_ID1]`. Nye kørsler skriver nu `[UID1]`; alle automatisk
  genkendte tyske og engelske typer forbliver entydige. Selvberegnede
  koder for andre grænsefladesprog vokser heller ikke længere ud over
  fire tegn ved navnesammenfald. Egne regelmærkninger forbliver uændret
  benævnt, som de blev indtastet.

- **„Hent original tilbage" udnytter nu hele det faktisk frie
  linjerum, før det sortslør.** Den hidtidige stive grænse ved det
  tredobbelte af den oprindelige ordbredde skabte bjælker selv i
  overvejende tomme formularfelter. Også fund fra det synlige
  OCR-modblik får nu en læsbar pladsholder ved belagt PDF-tekst; sort
  forbliver rent billed-, kommentar- og vektorindhold, den valgte
  sortsløringsform samt reelle trange steder, hvor end ikke en entydig
  kortform passer.

- **En allerede synlig pladsholder overskrives ikke længere en anden
  gang rødt ved sikkerhedsrastrering.** Rastreringen overtager nu det
  eksisterende erstatningsord fra sidebilledet og lægger kun et usynligt
  søgelag ovenover. Skal en sikkerhedsbjælke netop dette sted overmales,
  fornys hele den faktiske pladsholderkasse i stedet for kun dens
  kortere, oprindelige anker.

- **„Hent original tilbage" markerer nu kun sikre mål i den trukne
  ramme.** Alle erstattede begreber deri lyser enkeltvis og præcist op;
  uændret flydetekst forbliver urørt. Ægte vektorielle
  sortsløringsbjælker markeres ligeledes enkeltvis, hvis der ligger
  originaltekst under deres sorte PDF-flade. Ved rastrerede sider
  undlader forhåndsvisningen bevidst en formodet bjælkeflade: Den
  tidligere billedpunktssøgning forbandt der bogstaver, understregninger
  og tabellinjer til store røde flader på forkerte steder. Selve
  genoprettelsen berøres ikke heraf.

- **Ved genoprettelse på rastrerede sider kommer teksten tilbage.**
  Senest blev der stående et tomt sted med farvede rektangler ovenover.
  Den tilbagehentede tekst stod i dokumentet, men blev overmalet af den
  hvide grund fra en pladsholder, som tegnes længere bagude i
  sideopbygningen.

- **Kontrolfarverne ligger ikke længere flere gange oven på hinanden.**
  Samme sted blev farvelagt pr. post i tildelingen – på en side fem
  ægte fund, hver farvelagt fem gange, indtil den blege markering blev
  en mættet blok. Og de fremkommer ikke længere på ord, der slet ikke
  blev erstattet: Står originalværdien fortsat på siden, findes der
  heller ikke længere nogen markering.

## 0.10.40-beta.1 – 24. august 2026

### Rettet

- **Sortsløringsbjælker i editoren har nu en sikkerhedsrand.** Ord-,
  linje- og frie rammer dækker også overhængende glyffer og udjævnede
  randpixels; en gengivelseskontrol sikrer desuden, at hverken synlige
  rester eller læsbar originaltekst bliver stående.

- **Erstatningstekster forbliver læsbare og ensartet korte.** Nye navne,
  adresser og frie begreber fremstår for eksempel som `[NAM1]`, `[ADR2]`
  og `[BEG3]`. Den faste nedre grænse er 4,5 punkt; ved pladsmangel
  forkortes der først, og det brugbare løberum udvides. Gamle
  tildelinger med lange pladsholdere forbliver læsbare og kan hentes
  tilbage.

- **Flerordede erstatninger fra fundpanelet er sikret mod dobbelte
  markeringer og originalrester.** Regressionen består med og uden
  nummererede pladsholdere; pr. fund forbliver netop én fælles
  tildeling.

- **Tilbagehentede udklipsholderindhold renses ikke øjeblikkeligt igen
  på macOS.** Også når systemsignaturen først skifter forsinket efter
  skrivningen, genkender Maskuro pålideligt sit eget indhold.

### Nyt

- **Editoren kan nulstille en fil fuldstændigt til den friskt rensede
  udgangsudgave.** „Fil – Nulstil" forkaster efter en bekræftelse alle
  efterredigeringer af den aktuelle fane, herunder erstatningsliste og
  tællere. Kommandoen er spærret uden ændringer og kan selv fortrydes
  med „Fortryd".

- **Forskudte datoangivelser bevarer nu deres kronologi pålideligt over
  flere filer.** Den fælles forskydning forankres allerede varigt i
  reglerne, når strategien slås til; desuden kan forskydningen ikke
  længere være nul dage og dermed umærkeligt lade den ægte dato blive
  stående.

- **PDF-håndarbejdet dækker nu det fuldstændige professionelle
  sortsløringsforløb.** Enkeltbegreber, lister og regulære mønstre kan
  søges og sikkert sortsløres i den åbne PDF eller over alle PDF'er i en
  mappe; hele sider og sideområder kan vælges direkte. Farve, neutral
  hvid flade, overlejringstekst, skrift, retning og gentagelse har en
  forhåndsvisning, genbrugelige koder kan administreres samt im- og
  eksporteres. PDF-rensningen fjerner efter ønske alle skjulte
  indhold ved fuldstændig genopbygning eller udvalgte datakategorier.
  Det sikreste valg er tydeligt anbefalet, ugyldige søgemønstre forklares,
  og mappeforløb skriver udelukkende resultatkopier.

- **Den frivillige brugsstatistik viser nu installationer og
  versionsskift.** Maskuro genererer dertil en tilfældig, lokalt gemt
  installationskode. Den indeholder ingen enheds-, bruger- eller
  licensangivelser; serveren gemmer kun dens SHA-256-værdi. Statistikken
  forbliver fuldstændigt afbrydelig i indstillingerne.

- **Rundvisningen er nu en guidet øvelse gennem begge vinduer.** Den
  lægger selv det opfundne øvelsesdokument i listen, forklarer vejen
  frem til rensning og fortsætter automatisk i editoren efter
  kørslen. Den, der afbryder rundvisningen, afslutter også denne
  fortsættelse.

- **Firmaer fra femten yderligere retssystemer genkendes.** Den, der
  renser dokumenter fra Baltikum, Belgien, Skandinavien, Tjekkiet,
  Polen, Sydøsteuropa, Singapore, Brasilien eller Mexico, mister ikke
  længere firmanavne, fordi deres retsform var ukendt – nye deriblandt
  er OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s.,
  S.K.A., Pte. Ltd. samt S.A. de C.V. og S. de R.L.

### Ændret

- **Editorens værktøjslinjer bruger nu deres plads mere målrettet.**
  Entydige standardsymboler og direkte genkendelige værktøjsformer står
  uden gentagen tekst i linjen; flertydige handlinger beholder deres
  navn. Under „Vis" kan „Vis værktøjsmærkninger" slås fra for at
  reducere begge linjer helt til symboler. Tooltips og menuer forbliver
  fuldstændigt mærkede, valget huskes.

- **Læringstilstanden er nu varigt synlig i værktøjslinjen.** Den kan
  slås til og fra der direkte, også når fanen med de erstattede værdier
  er lukket. Værktøjslinje, menuen Værktøjer og den hidtidige kontakt i
  fanen viser altid samme tilstand.

- **„Nulstil" ved sammenligningsluppen nulstiller nu kun dens zoom.**
  Knappen genopretter standardværdien på 125 procent uden at fjerne
  luppens dokning, flytte den eller ændre dens vinduesstørrelse. For
  hele opsætningen er „Nulstil visning" fortsat ansvarlig.

- **Fejl og ønsker kan nu også indberettes via hjælpeknappen.** „Meld
  fejl …" og „Kom med ønske …" står der nu ligesom i det klassiske
  hjælpemenu; begge veje åbner den allerede eksisterende sikre
  fejlmelding henholdsvis den offentlige ønskeliste.

- **Proceslinjemenuen er kortere og mere klart ordnet.** De to
  kommandoer med globalt tastaturgenvej – udklipsholder-rensning og
  skærmbillede – står nu umiddelbart under hinanden med en fælles højre
  genvejsspalte. „Gendan seneste originalindhold" bortfalder der; den
  mere forståelige gendan-knap forbliver tilgængelig i hovedvinduet.

- **Juridiske sider er direkte tilgængelige under „Hjælp → Juridisk".**
  Undermenuen fører til licensbetingelser, databeskyttelseserklæring,
  impressum og AGB på maskuro.com. Henvisninger til fortrydelsesretten
  forbliver ved købet på webstedet.

- **Manuelt sortslørede PDF'er genopbygges fuldstændigt ved lagring.**
  Synlige forbliver siderne og deres nyligt læste søgelag; metadata,
  filbilag, bogmærker, kommentarer, formularværdier, skjulte lag,
  søgeindekser, scripts, beskåret indhold og indhold skjult under
  andre objekter overtages ikke i udgavefilen. Skrift og vektorgrafik
  består derefter af billedpunkter – det er prisen for den beviselige
  grænse til det fremmede PDF-objekttræ.

- **Ctrl+Shift+B tager nu på alle systemer som standard et skærmbillede
  med Maskuro.** Print Screen-tasten og kombinationer dermed forbliver
  mulige som egen tildeling. I proceslinjeikonets menu står de globale
  tastaturgenveje nu til højre for de tilhørende kommandoer. Egne gemte
  tildelinger bevares.

- **Editoren starter med sider og sammenligningslup til venstre.**
  Sidefanen står øverst, den åbne original-lup lige under; de
  erstattede værdier forbliver til højre. En bevidst gemt egen ordning
  har fortsat forrang.

- **Øvelsesdokumentet står ikke længere varigt i hovedvinduet.** Det er
  en del af den guidede øvelse og forbliver desuden tilgængeligt under
  „Hjælp".

- **Førstestarten fører direkte til den praktiske øvelse.** Den
  illustrerede korte vejledning tilbydes ikke længere som en anden,
  indholdsmæssigt dobbelt indgangsvej; den forbliver til enhver tid
  tilgængelig under „Hjælp → Kortvejledning".

- **Det hvilende proceslinjesymbol forbliver i fuld farve.** Det viser
  nu det samme kraftige Maskuro-skjold som den aktive
  udklipsholdertilstand; kun ved aktiv overvågning kommer den grønne
  lysende prik til.

- **Øvelsesdokumentet forbliver i Maskuro.** Indgangsknappen genererer
  den opfundne PDF og indsætter den direkte i fillisten, men starter
  ikke længere en ekstra PDF-fremviser.

- **Søgningen i redigeringsvinduet forbliver flydende under indtastning.**
  Pladsen til fundtælleren reserveres allerede ved åbning; dens første
  tekst ændrer ikke længere lærredet og udløser ikke noget nyt
  PDF-rastreringsforløb.

- **Producentnavne i fabrikatangivelser forbliver synlige.** En post som
  „Fabrikat: TRILUX eller tilsvarende" beskriver den nødvendige vare og
  sortslør ikke længere blot på grund af denne mærkning som firma.
  Leverandør-, firma- og producentfelter berøres ikke heraf.

- **Korpusmålinger tæller for vidt sortslørede fund som falske alarmer.**
  Når Maskuro fjerner det forventede navn, men samtidig tager en del af
  sætningen med, stiger nu antallet af falske alarmer. Rapporten
  udviser desuden overgreb separat; tidligere falsk-alarm-tal er derfor
  ikke direkte sammenlignelige.

### Rettet

- **Tekniske og officielle begreber fra tyske originaldokumenter
  sortslør sjældnere som navne eller steder.** Køretøjsudstyr,
  positions- og sumlinjer, udbuds- og databeskyttelsesbegreber,
  lovhenvisninger samt filnavne på offentligt materiale bremses kun
  ved deres belagte sagskontekst. En umlaut, der er gået tabt ved
  teksgenkendelse i „Marz 2026", forbliver beskyttet som måned; „Marz"
  uden datorelation kan fortsat være et ægte navn eller sted.

- **„Hent original tilbage" tager straks den fuldt nødvendige bredde.**
  Rammer rammen kun ét ord af en tildelt værdi, udvider Maskuro den
  selvstændigt ud fra tildelingen og originallinjen til hele angivelsen
  – for eksempel fra „Planungs" til „Nordlicht Planungs GmbH". Den
  efterfølgende gribbare ramme viser ligeledes den faktisk
  tilbagehentede samlede bredde.

- **„Hent original tilbage" viser sorte bjælker nu som et entydigt mål.**
  Ved overkørsel eller trækning lyser hele den genkendte bjælke rødt op
  med lys kontrastkontur, i stedet for kun en næppe tilordnelig
  tekstkasse ved siden af. Det gælder også for rastrerede sider, hvor
  bjælken kun består af billedpunkter.

- **Editorens rundvisning udelader ikke længere stationer, hvis faner
  var lukkede.** Til gennemgangen åbner og ordner Maskuro selv
  midlertidigt sidefane, sammenligningslup og erstattede værdier. Efter
  „Færdig" eller en afbrydelse vender den personlige ordning tilbage.
  Er et værktøj grundlæggende ikke tilgængeligt ved en dokumenttype,
  forbliver dets forklaring som et teksttrin, i stedet for umærkeligt
  at forsvinde.

- **„Erstat" forbliver synligt også ved PDF-sikkerhedsfaldbacken.**
  Måtte Maskuro genopbygge en side som billede på grund af et
  tilbageblevet tegn eller beskadiget tekstløb, stod de rigtige
  erstatninger kun usynligt i søgelaget, og på siden lå sorte bjælker.
  De faktisk indsatte erstatningsværdier bevares nu synligt røde og
  søgbare over alle raster- og OCR-genopbygninger.

- **Bemærkningerne over den rensede udgave forbliver læsbare i det
  mørke udseende.** Versionsoverskrift, betjeningslinje og indledning
  overtager nu deres skriftfarve direkte fra det faktisk viste
  Qt-vindue.

- **Sortsløringsrammer sidder igen over teksten på rastrerede
  PDF-sider.** De usynlige ordkasser var afhængigt af originalskriften
  smallere end de synlige bogstaver. Derved opstod huller i bjælken,
  eller det sidste bogstav forblev læsbart. Kasserne beholder nu
  bredde, højde og retning af det synlige ord.

- **„Hvad er nyt" begynder igen helt øverst.** Changelog-dialogen sætter
  nu efter den færdige vinduesopbygning tekstmarkør og rullelinje
  udtrykkeligt til begyndelsen, i stedet for at starte midt i
  nyhederne afhængigt af Qt-standen.

- **Lukning under scanningens ordgenkendelse forbliver stille.** Et
  netop færdiggørende OCR-baggrundsforløb sender ikke længere til et
  allerede lukket redigeringsvindue.

- **Relative tidsangivelser opfattes ikke længere som navne.** Faste
  vendinger som „i dag", „i går", „i morgen" og „næste uge" kender
  Maskuro nu ud fra de officielle kalenderdata for det pågældende
  dokumentsprog.

- **Afslutning under den første modelindlæsning rydder rent op.** Den,
  der lukker Maskuro eller redigeringsvinduet umiddelbart efter
  åbningen, efterlader ingen tråd, der stadig arbejder i den native
  sprog­genkendelse, ved procesnedbrydningen. Det forhindrer den
  sporadiske nedbrudsrapport ved afslutning; en allerede kørende
  indlæsning færdiggøres velordnet.

- **Forsinkede startdialoger vises ikke længere efter afslutning.** Den,
  der lukker hovedvinduet kort efter start, får ikke bagefter alligevel
  usynligt eller forsinket vist spørgsmålet om den bedste genkendelse,
  nyheder eller introduktion.

- **HTML og e-mail beholder deres linjeafslutninger.** På Windows
  blandede HTML-serialiseringen efter rensning og tilbagetagning LF
  og CRLF. Indhold og formatering var korrekte, men filen ikke længere
  bytelig. HTML-filer og MIME-beskeder overtager nu igen deres kildes
  skrivemåde.

- **Firmanavne med et forholdsord forbliver fuldstændige.** Efter et
  forholdsord skar Maskuro navne som „Gesellschaft für Systemtechnik
  mbH" eller „Bank für Arbeit und Wirtschaft AG" af ved ordet „für".
  Hele firmanavnet genkendes nu; ægte sætningsindledninger som „Wir sind
  bei Alpha GmbH versichert" forbliver synlige.

- **Kinesiske firmanavne forbliver fuldstændige foran deres retsform.**
  En som verbum tolkbar mærkebestanddel kunne trods det entydige tillæg
  „有限公司" forkaste hele navnet. I skrifter uden store og små
  bogstaver har det officielle retsformanker nu forrang for denne
  usikre ordklassegrænse.

- **PDF-sider blev unødigt til billeder.** Ved flersidede PDF'er, hvis
  sider deler en skriftliste – hvilket almindelige generatorer opretter
  sådan –, mistede alle sider efter den første henvisningen til deres
  skrifter. Følgen var dobbelt: Umlaut var ikke længere søgbare i
  resultatet („Auftragsbestätigung" kunne ikke findes), og
  efterkontrollen anså derefter bogstaver for overset, som aldrig
  havde stået på siden – den rastrerede intakte tekstsider til billeder,
  derved ikke længere søgbare, ikke kopierbare og betydeligt større. I
  prøvebeholdningen ramte det fire ud af sytten sider.
- **Et komma alene udløser ikke længere rastrering.** Slutter et
  fundområde ved ordet, hører tegnsætningen ved siden af netop med
  ind. Et komma eller et punktum er dog ikke en overset angivelse, og
  rastreringen koster hele siden. Bogstaver og cifre forbliver fortsat
  en grund til at skærpe.

## 0.10.38-alpha.20260824 – 24. august 2026

### Nyt

- **Firmanavne uden selskabsform genkendes nu, når deres betegnelse nævner
  dem.** „Leverandør: Kranzbichler Handels GmbH" er altid blevet fjernet –
  selskabsformen afslører firmaet. „Leverandør: Dehner Märkte" blev
  stående, og i tilbud, udbud og bestillinger står leverandøren for det
  meste netop sådan. Det samme gælder „Firma:", „Producent:",
  „Fabrikat:", „Arbejdsgiver:" og deres tilsvarende i otte andre sprog,
  og også når betegnelsen står alene på sin linje og navnet nedenunder.

  Hvad der bag betegnelsen *ikke* er et firma, forbliver urørt:
  „Leverandør: se bilag" sløres ikke – ellers ville der stå „Leverandør:
  [ORGA1]", og det ville påstå et navn, der aldrig fandtes. Betegnelser,
  bag hvilke der lige så ofte står et menneske („Kunde:", „Ordregiver:"),
  er bevidst ikke med.

- **Et indsat billede kan nu også redigeres.** I vinduet „Rens billede"
  står ved siden af „Kopiér resultat" en knap *Rediger i editor*: Billedet
  renses og åbnes derefter til efterretning, betegnelse og fremhævning –
  samme vej, som et skærmbillede går.

- **Numre efter deres betegnelse findes nu også, når de benævner en
  forretningspartner.** Hidtil faldt kunde-, kontrakt- og
  personalenumre; nu også debitor-, kreditor- og leverandørnummer, det
  østrigske arbejdsgivernummer, ANKÖ-registreringen og WEEE-, EAR- og
  EPR-nummeret på en producent – på tysk som på engelsk. Desuden forstår
  Maskuro nu skrivemåden i satte tilbudshoveder med mellemrum foran
  kolonet („Kunde-Nr : K903944"). Artikel-, ordre-, sags-, tilbuds- og
  fakturanumre forbliver fortsat urørte: De benævner sagen eller varen,
  ikke mennesket. Den, der alligevel vil fjerne dem, gemmer dem som eget
  søgemønster.

- **Du ser nu, hvor lang tid en fil har taget.** Ved den færdige linje
  står varigheden ved siden af det genkendte sprog („færdig · tysk ·
  2,4 s"), i sammenfatningen hele kørslens, i nøgletalsklappen summen –
  og i kontrolrapporten står den som eget felt. Ved flere filer afslører
  linjen, hvilken af dem der kostede tiden.

- **Skrifter, som system-OCR ikke understøtter, kan læses reservevis med
  en eksisterende sprogfil.** Hidtil gjaldt: Beherskede den systemegne
  tekstgenkendelse ikke en skrift (på Mac'en f.eks. devanagari), stod der
  i resultatet „billede(r) blev IKKE kontrolleret", og angivelserne i
  billedet blev stående. Nu springer den medfølgende tekstgenkendelse ind,
  hvis den passende sprogfil foreligger. Fordi et sådant læst billede er
  mere usikkert end et regulært kontrolleret, står det i resultatet: „læst
  med reservemetoden – bedes gennemset". Målt på et historisk mellemstade
  af hindi-prøven: **ti angivelser flere fundet og fire falske alarmer
  færre** (64 % → 73 %). Den aktuelle slutværdi står længere oppe og må
  ikke forveksles hermed.

- **Tekstgenkendelsen spørger om det rigtige sprog.** For alle
  dokumentsprog undtagen tysk og engelsk blev hidtil den engelske
  genkendelsesmodel brugt, også når den passende sprogfil forelå. Under
  Windows berørte det ethvert sprog – græsk, japansk eller hindi blev der
  læst med den engelske model.

- **En opsætningsguide ved allerførste start.** (Den, der allerede har
  brugt Maskuro, får den ikke – „førstestart" betyder første start, ikke
  første start efter denne opdatering.) Tre spørgsmål i stedet for seks
  billeder: sproget for dine dokumenter, om tekst i billeder læses med,
  og hvordan du vil nå Maskuro i hverdagen. Til sidst står de tre veje
  fortsat – øvelsesdokument, rundtur eller den illustrerede
  kortvejledning. Alt kan springes over, og „Hjælp → Gennemgå opsætning
  igen" henter den tilbage.

- **F1 slår håndbogen op ved det tilsvarende kapitel.** I hovedvinduet, i
  indstillingerne (der alt efter side), i gennemsynsvinduet og i
  sprogadministrationen; i vinduet til efterretning via Skift+F1, fordi F1
  der altid har vist tastaturgenvejene. Hidtil begyndte hjælpen altid
  øverst, ved 25 kapitler.

- **Nyt første håndbogskapitel: „Kom i gang på tre minutter".** Fire
  trin, mere kræves ikke til et dokument – på alle 18 sprogfassioner.

- **En rundtur gennem vinduet.** „Hjælp → Rundtur gennem vinduet" lægger
  et spotlight på ét betjeningselement efter det andet og skriver en
  sætning ved siden af – i hovedvinduet otte stationer, i vinduet til
  efterretning syv. I modsætning til den illustrerede kortvejledning
  forklarer den det vindue, du netop sidder foran. Afbryd til enhver tid
  med Esc.

- **Et øvelsesdokument til ufarlig afprøvning.** Under aflæggelsesfladen
  står nu „Åbn øvelsesdokument" (også i hjælpemenuen). Det opretter et
  opdigtet ark – navn, adresse, telefonnummer, IBAN, personnummer – og på
  arket står samtidig, hvad du kan gøre med det, og hvad du vil se
  derefter. Ikke et ord af det tilhører et rigtigt menneske; det første
  dokument, du sender gennem Maskuro, behøver altså ikke være et ægte.

- **„Bare se efter …" står nu ved siden af „Rens".** Det viser, hvor
  personoplysninger ligger – fil, art og antal –, uden at ændre eller
  skrive noget som helst. Den, der har lagt et dokument ind, ser dermed
  først efter, før han renser. Hidtil lå denne vej kun i filmenuen under
  „Gennemse mappe …" og gik over en hel mappe i stedet for over de
  aflagte filer.

- **Blev der intet fundet, står der nu med, hvad det kan skyldes.** F.eks.:
  I filen står billeder, men „Kontrollér også tekst i billeder" er slået
  fra. Eller: Det indstillede sprog passer ikke til dokumentets. Og hvis
  intet af det foreligger, siger Maskuro også det.

- **Vinduet til efterretning byder dig velkommen første gang med tre
  sætninger:** klik slører et ord, træk et område, til højre står de
  erstattede værdier. „Forstået" fjerner henvisningen permanent; „Hjælp →
  Vis introduktion igen" henter den tilbage.

- **Klik på ord fungerer nu også på indscannede sider.** Hidtil kunne ord
  kun klikkes der, hvor PDF'en bringer et tekstlag med sig – ved en
  scanning gik det ikke, og i samme dokument kunne det skifte fra side til
  side. Sådanne sider læses nu engangsvist af tekstgenkendelsen; derefter
  klikker man på ord som alle andre steder. Statuslinjen siger, hvad der
  netop sker.

- **Sidefaget er igen en flade.** Det holdt op midt i sin spalte:
  titelbjælke afskåret, ved siden af en stribe i en anden farve, og den
  aktuelle side var kun genkendelig på en farvet kasse bag sit nummer. Nu
  fylder det sin spalte ud, kan trækkes bredere, og den aktuelle side er
  fremhævet som en hel flise – med uforfalsket sideforhåndsvisning i sig.

- **Erstattede steder lyser blegt gult.** I sidevisningen kan man dermed
  se på et øjeblik, hvor der er erstattet noget – samme farve, som
  sammenligningsluppen bruger over originalen. Den røde ramme ved peget
  med musen forbliver uændret.

- **„Nulstil visning" i vinduet til efterretning** (menuen „Visning"). Den,
  der har flyttet, løsrevet eller lukket sidefag eller fundliste, stiller
  hermed alt tilbage til, hvor det stod ved første start.

### Ændret

- **Pladsholderne er kortere.** Af `[SOCIALSIKRINGSNR_1]` bliver
  `[SVNR1]`, af `[ORGANISATION_1]` et `[ORGA1]`, af `[EMAIL_1]` et
  `[MAIL1]`. Grunden er ikke skønhed: En pladsholder, der er længere end
  den værdi, den erstatter, presser linjen fra hinanden og finder slet
  ingen plads i en trang tabelkolonne – der forblev hidtil en sort
  bjælke, og den fortæller ingen længere, at der stod noget på stedet.
  Hvor der findes en almindelig forkortelse, står den der (`[REG1]`,
  `[BILNR1]`, `[IBAN1]`). Resultater fra tidligere kørsler forbliver
  brugbare: Den gamle skrivemåde genkendes fortsat, og tilknytningsfiler
  fra i går fungerer uændret.

- **Programikonet står nu ens overalt.** I Mac'ens menulinje fremkom
  hidtil et ensfarvet skjold, som systemet selv farvede sort eller hvidt,
  i Windows-proceslinjen et grønt henholdsvis gråt. Nu bærer hver bjælke
  samme blå Maskuro-skjold. Hvad man kan se, om udklipsholderen
  overvåges, forbliver lige tydeligt: Kører overvågningen, sidder en grøn
  prik på skjoldet; hviler den, står det samme skjold blegt der. Også i de
  mindste størrelser står nu begge sløringsbjælker i skjoldet – hidtil
  viste proceslinjen der kun én.

- **Ansigter genkendes med en model, hvis træningsbilleder er opstået med
  samtykke.** Der leveres nu MediaPipe BlazeFace (Apache-2.0); den
  hidtidige detektor forbliver indbygget og kan skiftes til, men medfølger
  ikke længere, fordi dens træningsherkomst ikke er endeligt afklaret. For
  genkendelsen ændres intet: På 324 portrætter og 143 billeder uden
  ansigt finder den nye version lige så meget ved lige så få fejlgreb og
  bruger en tredjedel af tiden.

- **OCR er sikkerhedsankeret for den stærkeste PDF-garanti.** Den normale
  PDF-kørsel bruger den og genererer den fuldstændige minimalopbygning.
  Den, der udtrykkeligt slår OCR fra, får den mere kompatible objektvej;
  grænseflade, afslutningsmeddelelse og håndbog siger nu udtrykkeligt, at
  denne vej ikke tilbyder samme arkitektur mod ukendte skjulte
  PDF-kanaler.

- **Salgsgaten spærrer nu også den hidtil vedlagte YuNet-model.**
  MIT-licensen for den nøjagtige vægt forbliver dokumenteret, men er ikke
  nok som konservativ produktfrigivelse for den offentligt synlige
  træningsdatakæde over WIDER FACE. Før salg kræves en skriftlig
  afklaring eller udskiftning mod en model med en bæredygtig kommerciel
  data- og vægtkæde.

- **Firma- og organisationsnavne fjernes nu af sig selv.** Hidtil blev de
  stående, så længe man ikke udtrykkeligt anmodede om det. Det var den
  forkerte standard for et forretningsbrev: Den, der giver et tilbud
  videre, vil ikke læse ordregiveren deri. „Kranzbichler Handels GmbH",
  „Institut for Bygningsfysik" og lignende behandles derfor som et navn.
  Den, der har brug for det anderledes, slår det fra i vinduet; på
  kommandolinjen hedder omskifteren nu `--ohne-organisationen`. Den gamle
  `--mit-organisationen` accepteres fortsat og gør ikke længere noget, så
  eksisterende scripts og genveje ikke går i stykker. Datoer og
  pengeangivelser forbliver uændret undtaget.

- **Sløring har nu tre former i stedet for to fluebenene.** „Ord", „Hele
  linjen" og „Fri ramme" står som ét valg ved siden af hinanden – altid
  gælder netop ét. Hidtil var „Tekstlinjer" og „Hele linjen" to
  uafhængige omskiftere, der begge kunne være trykket, og den fri ramme
  var slet ikke en knap, men den frakoblede tilstand af den første. De tre
  står synligt ved deres værktøj og er grå, så længe et andet værktøj er
  valgt.

### Forbedret

- **Det første dokument er omkring et sekund hurtigere færdigt.** Før
  rensningen begynder, fastslår Maskuro dokumentets sprog – og hentede
  dertil hidtil ordlisterne for alle 48 sprog via en vej, der indlæste
  langt mere end ordene. Det var omkring halvdelen af ventetiden til det
  første resultat. Selve genkendelsen er uændret: Den ser de samme ord som
  før, blot hurtigere. Hvert efterfølgende dokument var alligevel ikke
  berørt af dette.

- **Dokumenter med meget lange afsnit kontrolleres hurtigere.** Ved et
  afsnit uden linjeskift læste Maskuro det helt igennem på ny for hvert
  fundet sted; nu er én gang nok. Jo længere afsnittet, desto større
  forskellen – målt omkring en syvendedel mindre regnetid. Ved resultatet
  ændres intet.

### Rettet

- **Med et firma forsvandt ofte den halve sætning med.** Stod et
  firmanavn i brødteksten – „Information om Gottwald GmbH & Co KG", „…
  (AGB) fra Musterbetriebe GmbH" –, blev ikke kun navnet sløret, men alt
  foran det til sætningens begyndelse. Teksten blev derved ulæselig, og
  det så ud, som om der var sløret vilkårligt. Firmanavne, der selv bærer
  et „for" eller „og" („Bank for Arbejde og Erhverv A/S"), forbliver hermed
  uændret fuldstændige.

- **Firmanavne forblev stående i brevhoveder, selv om de blev fjernet i
  teksten.** I et tilbud stod firmasædet i brevhovedbilledet fortsat
  læseligt – samme sted, som Maskuro havde sløret i brødteksten; i den
  søgbare tekst af resultatet stod det endda usynligt videre inde. Hvad
  der én gang er fjernet, fjernes nu også der, hvor det kun foreligger som
  billede. Det virker også ved logoer og ordmærker, der er tegnet som
  grafik.

- **macOS spurgte ved hver start om skærmoptagelse**, også når
  tilladelsen var givet for længst. Henvisningen ved start afprøvede en
  optagelse, og netop det henter systemdialogen frem på skærmen. Nu
  spørger kun Maskuro selv ved start, og kun én gang; systemet spørger
  først, når du virkelig tager et skærmbillede.

- **Tekniske sagbegreber blev opfattet som steder og firmaer.**
  „Indfødningspunkt", „fladt tag", „fordelingsanlæg", „meldersokkel" og
  snesevis af lignende ord forsvandt fra tilbud og
  arbejdsbeskrivelser. Maskuro genkender dem nu på deres grundord: Hvad
  der ender på „-anlæg", „-punkt" eller „-kanal", er en sag. Stednavne som
  Berlin, Melk eller Wieselburg har ikke et sådant grundord og forbliver
  uberørte – ligeledes adresser som „Der Graben" eller „Alter Markt".

- **Japanske, koreanske, kinesiske, thailandske og gujarati-dokumenter
  kunne bringe programmet til nedbrud.** Indeholdt et dokument på et af
  disse fem sprog en internetadresse uden „https://" foran, afbrød
  rensningen med en intern fejl – ved åbent vindue gik samtidig det
  øvrige arbejde tabt. Alle otteogfyrre valgbare dokumentsprog kører nu
  igennem; mangler en frekvensordbog for et sprog, forbliver angivelsen i
  tvivlstilfælde stående i stedet for at forsvinde.

- **Feltbetegnelser beskyttede kun på tysk og engelsk.** „Reference" blev
  stående, det italienske „Riferimento" og det portugisiske „Referência"
  blev fjernet som stedangivelse – samme feltnavn, samme linje, andet
  resultat. Den, der ikke arbejder på engelsk, var dermed dårligere
  stillet. Maskuro kender nu de samme feltnavne på alle elleve
  vedligeholdte sprog.

- **„Hent original tilbage" hentede for meget tilbage på indscannede
  sider.** En ramme over en sløret linje i en adresseblok afdækkede
  **hele blokken** igen – og siden forblev revet i stykker: Bjælkerester
  stod tilbage, hvorfra enkelte ordender stak frem. Årsagen var, at
  bjælker liggende over hinanden på en rastreret side støder sammen og
  derfor gjaldt som én flade. Der hentes nu netop den linje tilbage, som
  rammen peger på; nabolinjerne forbliver slørede, og bjælken for den
  ramte linje forsvinder helt.

- **Mængdeangivelser i positionslister blev opfattet som adresser.** I en
  linje som „1.4  Kabelgrav  100,00  m" blev „Kabelgrav 100" erstattet som
  gade med husnummer. Sådanne linjer bliver nu stående; ægte adresser –
  også „Hauptplatz 1, 3250 Wieselburg" – genkendes uændret.

- **Foran et firmanavn forsvandt den halve sætning.** Af „Kontrakt mellem
  firmaet Gottwald GmbH & Co KG og ordregiveren." blev „[ORGANISATION_1]
  og ordregiveren." – sætningens begyndelse var væk, og dermed
  henvisningen til, hvad det drejer sig om. Nu falder kun selve
  firmanavnet. Hvor gattungsordet hører til navnet („Deutsche Bank AG",
  „Universität Wien"), forbliver alt som hidtil.

- **I et referat blev talere stående, hvis navn samtidig er et erhverv.**
  „Bauer:", „Koch:", „Weber:" foran en ordveksling blev overset,
  „Gruber:" ved siden af ikke – Maskuro krævede hidtil mindst ét
  genkendt navn i dokumentet for overhovedet at læse linjerne som
  ordvekslinger. Bærer dokumentet en overskrift som „Resultatprotokol"
  eller "Referat", er det nu nok. Mærkelinjer („Bemærk: …", „Henvisning:
  …") forbliver urørte.

- **En feltbetegnelse forsvandt sammen med sin værdi.** Af „Projekt:
  Renovering og udvidelse af kommunecenter" blev én eneste pladsholder –
  også ordet „Projekt:" var væk, og dermed henvisningen til, hvad der
  havde stået på dette sted. Betegnelser bliver nu stående. Hvor en
  betegnelse hører til angivelsen og bærer dens betydning
  („Lokalnummer 214"), ændres intet.

- **Den maksimale genkendelse ryddede ikke op i sagbegreber.** „Fladt
  tag", „indfødningspunkt", „elektroteknik" og lignende fagord blev også
  med tilkoblet AI-niveau erstattet som sted eller firma – AI'en fik
  netop disse fund aldrig forelagt til bedømmelse. Den kontrollerer dem
  nu med: På et korpus af udbuds- og kontrakttekster forsvinder derved
  alle 27 fejlgreb, uden at en eneste ægte angivelse bliver stående. Navne,
  firmaer og steder genkendes uændret.

- **Gattungsord for institutionstyper blev opfattet som organisationer.**
  I en kontrakttekst forsvandt „Højskoler og universiteter", „Statslige
  og private skoler", „Akademiske undervisningshospitaler",
  „Uddannelsesinstitution" og „Underleverandørfirmaer" – ord, der ikke
  benævner et bestemt sted, men en art af sted. De bliver nu stående.
  Står et egennavn foran („EU-Kommissionen"), erstattes fortsat, og
  firmanavne er slet ikke omfattet af reglen.

- **Navne i lister faldt kun, hvis de var almindelige.** I en deltager-
  eller fremmødeliste under en kolonneoverskrift „Navn" blev „Anna Huber"
  og „Thomas Müller" fjernet, „Wójcik Aleksandra" eller „Kücükgöl Sinan"
  ikke – samme linje, samme opbygning. Den, der bærer et sjældnere navn,
  var dermed dårligere beskyttet. Nu afgør kolonneoverskriften: Hvad der
  står under „Navn", er et navn. En positionsliste med et sagligt
  kolonneoverskrift forbliver urørt.

- **Et telefonnummer efter „Lokalnummer" blev skåret midt over.** Af
  „Lokalnummer 0732 771190" blev „[LOKALNUMMER_1] 771190" – anden
  halvdel af nummeret forblev læselig. Nu falder det fuldstændige nummer
  helt, og betegnelsen bliver stående. Et ægte lokalnummer
  („Lokalnummer 214") erstattes uændret sammen med betegnelsen.

- **Nogle PDF'er kunne slet ikke længere renses.** Kunne en farveprofil
  eller metadataene i et billede ikke bevisligt fjernes, afbrød kørslen
  uden resultat – berørt var almindelige forretningsdokumenter som
  standardvilkårssider, kravspecifikationer og udbud. Sådanne filer
  renses nu, og en advarsel nævner de steder, der forblev åbne: De kan
  bære en enheds-, producent- eller optagelsesidentifikation. Originalen
  forbliver som altid uændret.

- **Kontraktroller blev opfattet som personer.** „Byder", „Forbruger",
  „Lejer", „Køber", „Ordregivers" og omkring fyrre andre rolleord blev
  erstattet, hvor de stod uden artikel – i kontraktoverskrifter,
  tabelkolonner og underskriftslinjer. En kontrakttekst uden en eneste
  personoplysning blev derved delvist ulæselig. Disse ord bliver nu
  stående. Står der ved siden af en personhenvisning – en tiltale, et
  fornavn, et feltord som „Kontaktperson" –, erstattes fortsat: „Hr.
  Byder" og „Fru Køber" er navne. Hyppige efternavne, der samtidig er
  erhverv (Bauer, Richter, Koch), er slet ikke omfattet af reglen.

- **En forkortet skrevet gade blev overset, hvis husnummeret klæbede
  direkte til punktummet.** „Schlesischestr.31" gjaldt ikke som adresse –
  og fordi postnummeret ved siden af har sit belæg fra adressefundet,
  forblev også det stående. I resultatet var adressen af gade og
  postnummer igen sammensættelig, og kun på nogle sider af samme
  dokument. Begge dele falder nu sammen. Sagsbetegnelser med vedhæftet
  tal („Kabelrende200") forbliver urørte.

- **En adresse over to linjer blev trukket sammen til en enkelt
  pladsholder.** Stod postnummeret over gaden i en adresseblok,
  forbandt Maskuro begge linjer til ét fund: I resultatet forsvandt
  linjeskiftet, og postnummeret forblev læseligt foran. Nu findes og
  erstattes hver linje for sig, og skriftbilledet bevares. Samme årsag
  trak til tider også efternavnet fra linjen ovenover med ind i adressen.

- **Den maksimale PDF-vej overtager ikke længere originalobjekter.** Med
  tilkoblet tekstgenkendelse genopbygger Maskuro hver side fuldstændigt
  fra det synlige PDFium-billede. Ind i den nye minimalfil kommer kun
  denne billedside og et nygenereret, til OCR-teksten begrænset søgelag –
  ikke det fremmede objekttræ med kommentarer, bilag, handlinger, lag,
  metadata, farveprofiler eller private nøgler. Det gælder også indhold i
  annotation-fremtoninger, mønstre, type-3-skrifter, formularobjekter og
  softmasker. Kildefilen forbliver urørt.

- **Ansigter og koder i indlejrede PDF-grafikker blev overset.** Begge
  detektorer ser nu desuden det fuldstændige rendrede sidebillede. Derved
  når også portrætter og QR-/stregkoder i annotationer, mønstre,
  type-3-glyffer og transparensmasker detektorerne; genkendte områder
  gøres – hvis tilkoblet – ukendelige før minimalopbygningen. Selve
  detektionen forbliver fejlbar.

- **En manglende OCR-maskine endte ved PDF'er med en intern fejl.** Den
  maksimale kørsel afbryder nu kontrolleret og uden målfil, i stedet for
  at udlevere en ufuldstændig eller ukontrolleret fil.

- **Flere ægte kontakt- og forretningsværdier faldt igennem, mens
  sagtekst blev erstattet.** Navnefelter over linjeskift, bank- og
  firmanavne, selskabsformer, betegnede identifikationsnumre,
  fødselsdatoer samt telefon-, URL- og IBAN-grænser er kontrolleret
  strammere. Samtidig forbliver lande i sagtekst, rolle- og
  gattungsord, artikel-/normkoder, talkolonner og almindelige
  forkortelser hyppigere urørte.

- **Blandede og drejede OCR-linjer blev læst forkert.** Usikre lodrette
  ord genlæses nu lokalt opretstillede; tekniske latinske værdier i
  ikke-latinsk tekst får et uafhængigt engelsk-vidne. Et fritstående
  usikkert enkeltciffer rettes kun, hvis to nære ciffersekvenser stemmer
  overens. Polske selskabsformer af OCR-formen „sp. z 0.0." læses i
  lukket kontekst som „sp. z o.o.".

- **Billedmålingen kunne overse delvist synlige restværdier.** Den
  kontrollerer nu overlappende lokale udsnit, adskiller hvid
  pladsholderskrift på en sort bjælke fra originalglyffer og overfører
  råbilledkasser også til drejede, nyrendrede minimal-PDF'er. Det faste
  syntetiske hovedkorpus opnår dermed 1.392/1.392 fjernede målangivelser
  ved 0 falske alarmer og 0 behandlingsfejl. Det er et korpusbevis, ikke
  et generelt 100 %-løfte.

- **Ikke-kommercielle sprogmodeller tilbydes ikke længere.** De seks
  italienske og græske spaCy-varianter under CC BY-NC-SA 3.0 er fjernet
  fra katalog, download og indlæsningsvej; også allerede eksisterende
  modelmapper ignoreres. Begge sprog bruger i stedet den MIT-licenserede
  flersprogede model.

- **Navnet under „Kontaktperson" blev kun halvt fjernet.** Står
  betegnelsen alene på en linje og nedenunder „Efternavn Fornavn", blev
  fornavnet stående, så snart det samtidig var et almindeligt ord – af
  „Mayer Roman" blev „[NAVN_1] Roman". Sådanne linjer tages nu helt. En
  afdeling på samme sted („Teknisk Indendørs Service") forbliver fortsat
  urørt. Rettet i samme ombæring: „Kontaktperson" talte slet ikke som
  navnefelt, selv om „Kontaktperson" altid har gjort det.

- **Firmanavnet uden selskabsform forblev stående, hvis et brancheord stod
  imellem.** „Kranzbichler Handels GmbH" blev fjernet, det nøgne
  „Kranzbichler" tre afsnit senere ikke – ved „Kranzbichler GmbH" derimod
  gjorde det. Nu virker begge dele. Almindelige ord er undtaget fra det:
  „Deutsche Bank AG" gør ikke „tyske" i teksten til et firma.

- **Samme værdi hed i samme dokument ét sted navn og ét sted sted.** „Anna
  Musterfrau … Musterfrau" gav „[NAVN_1]" og „[STED_1]" – på det andet
  sted manglede fornavnet, og uden det blev det til et sted. Fjernet var
  begge, men det læstes som to forskellige ting. En værdi beholder nu
  betegnelsen fra sin første forekomst.

- **Datoangivelser blev ikke fjernet længere.** En dato helt af cifre
  („01.03.2026") faldt siden sidste version igennem en kontrol, der var
  tiltænkt navne, og forblev stående i dokumentet – også i tilstanden
  „forskyd", og uden linje i kontrolrapporten. Berørt var kun den, der
  udtrykkeligt havde tilkoblet datoangivelser.

- **Lande og kontinenter sløres ikke længere.** „Leveringen går til De
  Forenede Stater", „Markedssvaghed i Asien", „normen gælder i Rumænien"
  – sådanne angivelser siger intet om en person og bliver nu stående.
  Hører landenavnet derimod til en adresse eller står det efter en
  betegnelse som „Bopæl" eller „Fødested", fjernes det fortsat. **Byer er
  ikke berørt af dette** – „Jeg er netop i Bilbao" forbliver en angivelse
  om en person og sløres fortsat.

- **Forkortede ord blev til webadresser.** Står i teksten „hhv. tyske"
  eller "inkl. af", leverer visse PDF'er punktummet uden mellemrum –
  deraf blev „hhv.de" henholdsvis „inkl.de", en gyldig adresse med
  landeendelse, og den blev fjernet. Sådanne ordpar bliver nu stående.
  Ægte adresser er ikke berørt af dette, heller ikke uden „www." foran.

- **Talkolonner fra balancer blev sløret som telefonnumre.** I
  årsrapporter og pristabeller står sidste år og indeværende år ved siden
  af hinanden – „64.518  65.133". Det gjaldt som ét telefonnummer og blev
  fjernet, ligeledes talintervaller som „12200-23200" og en dato med et
  følgende tal. Sådanne tal bliver nu stående. Omvendt genkendes et ægte
  telefonnummer mere sikkert: Betegnelserne „Telefon", „Fax", „Mobil",
  „Lokalnummer" og deres tilsvarende på de andre grænsefladesprog tæller
  nu med – hidtil genkendte programmet der kun de engelske ord.

- **Navne i en nummereret tabel blev stående.** En deltagerliste eller
  personaletabel i den sædvanlige form – kolonneoverskrift, nedenunder
  „1.1 Auersperg Bernhard Montage 03.03.2026" – blev slet ikke renset:
  Sådanne linjer lignede en positionsliste fra et tilbud, hvor sagbegreber
  skal blive stående. Bærer kolonneoverskriften en personbetegnelse
  („Navn", „Efternavn", „Surname" …), gælder linjerne nedenunder nu som
  navne. Positionslister forbliver uændret skånede – også når der i
  brevhovedet står „Sagsbehandler:".

- **Af et navn blev der til tider to pladsholdere ved siden af
  hinanden.** Når et efternavn også stod alene i dokumentet, erstattede
  efterbehandlingen på et sted som „Anna Musterfrau GmbH" først
  efternavnet og derefter fornavnet – i resultatet så det ud som to
  forskellige personer. Nu vinder det længste kendte navn.

- **Opdigtede værdier stod i ingen tilknytning.** Den, der havde valgt
  „Opdigt værdier", fik et resultat, hvori „Anna Musterfrau" var blevet
  til „Greta Mayrhofer" – i tilknytningen stod intet om det, så snart der
  i samme dokument også blot forekom én anonym erstatning. Dermed kunne
  ingen opdigtet værdi hentes tilbage, og tilknytningsfilen fortav
  erstatningen. Det mest betænkelige var det tredje: Den, der læser
  resultatet, ser et troværdigt navn og har intet holdepunkt for, at det
  er opdigtet. Nu står hver erstatning i tilknytningen.

- **Tilknytningen kaldte sløret for „erstattet".** En e-mail deler en
  tilknytning med sine bilag, og bilaget må gerne sløres, mens
  mailteksten bærer en pladsholder. I tilknytningen stod da det samme for
  alle tre steder – „erstattet" –, og tilbagehentningen søgte i bilaget
  en pladsholder, der ikke findes der: Bjælken blev liggende. Nu står det
  pr. fundsted, hvad der virkelig skete der, og begge bilag kommer
  tilbage.

- **Værdier, der kun stod i et billede, kunne ikke hentes tilbage.** I
  fundpanelet stod de dobbelt – én gang som pladsholder, der ikke fandtes
  i dokumentet noget sted („Pladsholderen blev ikke fundet i
  dokumentet"), én gang som sløret sted. Den første linje var ren
  bogføring og er forsvundet.

- **Slørede værdier kunne kun hentes tilbage én gang.** Står samme værdi
  flere steder, henter et klik alle tilbage – de øvrige linjer blev dog
  stående i fundpanelet, og det næste klik derpå meldte „Ikke entydig".
  De forsvinder nu med.

- **Tilbagehentninger manglede i kontrolprotokollen, hvis læringstilstand
  var fra.** Den, der genoprettede en tilbagehentet værdi i vinduet til
  efterretning, fandt ikke forløbet i kontrolprotokollen igen, så snart
  læringsspørgsmålene var frakoblede – beviset hang på en kontakt, der
  kun angår regelforslagene. Ved tilkoblet kontrolprotokol spørges nu
  uafhængigt heraf om grunden, og linjen skrives.

- **Trukket ind filer forblev urensede – og blev ikke engang meldt.** Den,
  der trækker en fil ind i et dokument i stedet for at sende den som
  bilag, lægger den med Word eller PowerPoint fuldstændigt i dokumentet.
  Den stod derefter uændret i resultatet, med sit oprindelige filnavn og
  aflæggelsessti – og de bærer i praksis ofte selv et navn. Sådanne filer
  renses nu som resten af dokumentet.

- **Og hvor det ikke går, siger Maskuro det.** Sidder der i et indlejret
  objekt et gammelt format (Word 97, Excel 97), som der ikke findes
  rensning for, fremkommer nu en ADVARSEL-meddelelse med filens navn.
  Hidtil blev den stiltiende givet videre uændret.

- **Sønderrevne ord og forkortelser blev opfattet som navne.** Deles et
  ord i en PDF ved linjeskiftet, kommer der ved udlæsning af nogle filer
  et brudstykke ud – „Årsafslut… ning", „Erhvervsmæ…". Sådanne
  brudstykker, sammenklæbede ord („DørlåsMedV") og nøgne forkortelser
  („JY", „FFB") blev sløret, som var de navne. De bliver nu stående. Et
  navn med samme delingsskade forbliver fortsat sløret, så længe en
  tiltale er med – og navne, der af sig selv bærer et stort bogstav midt
  i ordet (McKenzie, MacDonald, LeBlanc), er slet ikke berørt af dette.

- **Måleangivelser og måneder gjaldt som adresse.** I tekniske dokumenter
  blev „2000 Lux", „1200 Mbit", „1500 Watt", „5308 Plads" og „2022 Mar"
  sløret – fire cifre og et stort skrevet ord lignede et postnummer med
  by. Et postnummer tæller nu kun, hvis der også er et adressesignal med:
  en landekode, en feltbetegnelse, linjens begyndelse, en gade i linjen
  ovenover eller et sted, som sproggenkendelsen også ser der. I fem
  arbejdsbeskrivelser forsvinder derved 14 falske sløringer, uden at en
  ægte adresse bliver stående.

- **Den mere præcise genkendelse erstattede for meget.** Det tilkoblelige
  niveau „mere præcis genkendelse" har i tyske forretningsdokumenter
  opfattet sagbegreber som navne og steder – „solcelleanlæg",
  „indfødningspunkt", „fladt tag", „personaleindgang" – og sløret
  firmabetegnelser fra løbende positionslister. Grunden var en skånsel:
  Dens fund var undtaget fra de kontroller, der genkender en positions-
  eller registerlinje. Denne skånsel gælder nu kun for flerleddede navne,
  som niveauet findes for – „Anna Huber" i en registerlinje forbliver
  altså genkendt, et enkelt sagord i en positionslinje falder væk. I et
  teknisk udbud halverer det niveauets falske sløringer, uden at et navn
  går tabt.

- **Diagrammer bragte deres fuldstændige kildedata med – ukontrolleret.**
  Den, der indsætter et diagram i Word eller PowerPoint, lægger
  programmet tabellen, det er beregnet ud fra, som en egen fil i
  dokumentet. Synlige er deraf kun de få tal i diagrammet; i tabellen
  står hele listen, med de linjer, der slet ikke forekommer i diagrammet.
  Denne tabel blev hidtil givet videre uændret. Den renses nu med, med
  samme pladsholdere som det øvrige dokument.

- **Det samme for indlejrede objekter i OpenDocument-filer** (ODT, ODS,
  ODP): Et indsat diagram eller en indsat tabel forblev urørt.

- **Word-dokumenter: fodnoter og slutnoter blev ikke renset.** Deres
  tekst forblev fuldstændigt i resultatet – også navne, adresser og
  kontonumre. Berørt var ethvert Word-dokument med en fod- eller
  slutnote. Ligeledes forblev en autotekst-byggeklods urørt, der usynligt
  rejser med dokumentet.

- **Word: angivelser i valglister, kommentarer og billedbeskrivelser.**
  Posterne i et valgfelt (synlige først ved udfoldning), forfatteren af
  en kommentar, beskrivelsen af en tegning og adressen bag en
  henvisningskommando stod fortsat i resultatet.

- **Excel: pivottabellen bar udgangsdataene en anden gang.** En
  arbejdsbog med en pivottabel opbevarer deri en fuldstændig kopi af de
  udnyttede linjer – usynlig, men i filen. Denne kopi forblev hidtil
  uændret stående, også når alt var erstattet i selve arket. Berørt var
  enhver udnyttelse, der blev givet videre med en pivottabel.

- **Excel: samtalekommentarer og deres forfattere.** Teksten af en
  kommentar af den nyere byggeform og fortegnelsen over kommentatorer –
  visningsnavn og login-kendetegn, i firmaer for det meste
  mailadressen – stod fortsat i resultatet. Samme fortegnelse i
  Word-dokumenter ligeledes.

- **Selvdefinerede dokumentegenskaber i Word og Excel.** Felter som
  „Klient" eller „Sagsnummer", som et advokatkontor giver sine skabeloner
  med, blev hidtil ikke renset. De er ikke synlige i nogen visning og
  følger alligevel med hver kopi.

- **Regneark (ODS): valglisten for en celle.** Som i Excel siden forrige
  version renses nu også i OpenDocument-regneark det, der fremkommer ved
  udfoldning af en celle. Henvisninger til andre celler forbliver urørte
  hermed, så listen fortsat fungerer.

Alle disse steder kan som sædvanligt hentes tilbage via tilknytningen.

- **Outlook-meddelelser: en beskadiget fil afbrød rensningen hårdt.**
  Visse ødelagte `.msg`-filer førte til en afbrydelse i stedet for en
  meddelelse; nu læses de, i det omfang de er læselige.

- **Tilknytningsfilen er nu kun læselig for dig.** Den indeholder
  originaldataene i klartekst og lå hidtil med de sædvanlige rettigheder
  ved siden af resultatet – på en fælles deling kunne enhver dermed åbne
  den. Ved det rensede resultat selv ændres intet; det skal jo gives
  videre.

- **Efterindlæste sprogmodeller kontrolleres mere nøjagtigt før
  udpakning.** En manipuleret pakke – f.eks. fra en firmadeling, hvorfra
  flere arbejdspladser betjenes – kunne ved udpakning lægge filer uden
  for den tilsigtede mappe. Ved den almindelige efterindlæsning ændres
  intet.

- **Tag et skærmbillede – og det renses med det samme.** Med
  `Ctrl+Skift+B`, via „Fil → Tag skærmbillede …" eller via symbolet i
  proceslinjen trækker du en ramme over skærmen. Hvad der ligger deri,
  går derefter samme vej som enhver anden fil: Tekstgenkendelsen læser
  skærmteksten, navne, adresser, telefonnumre og mailadresser sløres, og
  derefter står billedet åbent i editoren, hvor du med en ramme kan
  eftersløre, hvad der blev overset. Det rensede billede havner på
  skrivebordet (eller i din indstillede udgangsmappe); den **rå**
  optagelse lægges ingen steder og slettes ved afslutning.
  Tekstgenkendelsen tilkobles for denne kørsel, også når den ellers er
  fra – ved et billede ville der uden den intet være at finde. På Mac'en
  spørger systemet første gang om tilladelsen „skærmoptagelse".

- **Der kan nu tegnes på billeder: rektangel, ellipse, pil, tekst og
  nummererede trinmærker.** I seks farver og tre stregtykkelser, at vælge
  med tasterne 1 til 5. Tænkt til skærmbilleder og vejledninger: vise,
  hvad det kommer an på, uden at åbne et andet program for det. Fortryd
  og efterjustering ved håndtagene gælder som for enhver bjælke – en
  anmærkning kan altså flyttes og trækkes op, efter den er sat.
  **At tegne er udtrykkeligt ikke at sløre.** Et tegnet rektangel er en
  ramme, ikke en bjælke: Hvad der står under, forbliver læseligt og går
  med filen ud. Til fjernelse af angivelser er fortsat „Slør" og
  „Pixeler" til rådighed; tegneværktøjerne står derfor i en egen linje i
  værktøjslinjen, og hjælpelinjen siger det, så længe et af dem er valgt.

- **Det redigerede billede går med et klik på udklipsholderen.** „Kopiér
  billede" i editoren (eller `Ctrl+C`) lægger det, som det står –
  indsæt er nok til at bringe det ind i en besked eller mail. Dermed er
  vejen fra tastetryk til chat fire trin lang og kræver ingen mappe.

- **Dertil en tekstmarkør, skygger og forløb.** „Fremhæv" farver en
  flade, uden at dække den til – indholdet nedenunder forbliver læseligt,
  og netop deri adskiller den sig fra bjælken. „Skygge" hæver en
  anmærkning fra urolig baggrund, „forløb" lader farven løbe ud i
  trækretningen; begge dele gælder for alle seks tegneværktøjer.

- **Rettet, før det ramte nogen:** Den nye værktøjslinje ville hos alle,
  der allerede har brugt Maskuro, være fremkommet næsten tom – den
  huskede vindueopdeling stammede fra tiden før og ville ikke have givet
  den nogen plads. En forældet opdeling forkastes nu; editorvinduet står
  derefter engangsvist i sin grundopdeling.

- **Ens eget skærmbillede kan slås fra.** Den, der er vant til Greenshot,
  ShareX eller udklipningsværktøjet, slår under „Indstillinger → Program"
  „Tag skærmbillede med Maskuro" fra. Maskuro tilmelder da slet ikke
  tastaturgenvejen – den forbliver dit værktøjs – og omstillingen gælder
  straks, uden genstart. Rense lader et sådant optaget billede sig fortsat
  gøre: Ctrl+V henter det fra udklipsholderen ind i vinduet.

---

## 0.10.37-alpha.20260821 – 21. august 2026

### Nyt

- **Ved anonymisering bærer hvert fundsted nu sit eget nummer.** Hidtil
  hed alle personer `[NAVN]`, alle steder `[STED]` – derved kunne det ikke
  længere siges, hvilket sted der hørte til hvilken værdi, og der var
  intet at hente tilbage. Nu tæller numrene videre pr. forekomst: Samme
  navn står tre steder som `[NAVN_1]`, `[NAVN_3]` og `[NAVN_7]`. I
  dokumentet er det dermed fortsat ikke til at se, hvilke steder hører
  sammen – men med tilknytningsfilen kan hver enkelt hentes tilbage.
  Tilknytningsfilen kan derfor igen vælges ved anonymisering; opbevar den
  adskilt fra resultatet.
- **Måneder, ugedage, valutaer, enheder og virksomheders selskabsformer på
  alle 48 dokumentsprog gælder ikke længere som navne eller steder.**
  Kalender- og enhedsnavnene kommer fra Unicode CLDR (genereret, ikke
  skrevet), selskabsformerne fra landenes selskabsret – også flerords
  („sp. z o.o.", „Pty Ltd") og forankstillede („株式会社"). Hvor et
  månedsnavn samtidig er et fornavn (Juli, August, May), afgør
  byggeformen: med dag eller år ved siden af en dato, ellers et navn.
  Dertil tiltaler og titler, hele hilsenformler, dokumenttyper og
  gadenavnegrundord for 28 sprog med egen sprogmodel, lovforkortelser
  (GDPR, momsloven, § 6 stk. 1 nr. 27), samt sprognavne som feltværdi
  („Sprog: Tysk"). Listerne findes under „Hjælp → Ordlister …".
- **Indien: adresse og PIN-kode genkendes** – „15 गांधी मार्ग", „नई दिल्ली
  110001" ligesom „15 Gandhi Marg, New Delhi 110001". Landepakken Indien
  kendte hidtil kun ID-numre; i hindi-dokumenter blev adresser derfor
  stående.
- **Hver renset Office-fil åbnes endnu en gang som pakke før
  udlevering.** Et tekstudtræk mærker ikke, når Word, Excel eller
  LibreOffice ville afvise filen (dobbelt post, afrevet XML, en manglende
  del). Og der tælles op imod originalen, hvad en rensning aldrig må
  ændre: sider i en PDF, ark, linjer og celler i et regneark, dias i en
  præsentation. Slår prøven ud, står en ADVARSEL-henvisning i resultatet
  og i kontrolrapporten – originalen forbliver uændret.
- **Også automatikken slører hele feltet.** I sløringstilstand dækker
  bjælken i korte linjer – adresseblok, tabelcelle, kopfelter – hele
  linjen i stedet for kun den fundne værdi: En bjælke i ordlængde afslører,
  hvor langt ordet var. Betegnelse og beløb ved siden af bliver stående, og
  brødtekstlinjer (længere end halvdelen af tekstbredden) sløres fortsat
  ordpræcist, så et navn midt i sætningen ikke gør hele sætningen sort.
- **Tilbagehentet ligner igen originalen.** „Hent original tilbage" og
  „Fortryd erstatning" i PDF-editoren skriver nu området nøjagtigt tilbage
  fra kildefilen – samme skrift, samme størrelse, samme farve og
  placering, på en scanning samme billedpunkter. Indtil da blev teksten
  genindsat i en erstatningsskrift og så genkendeligt genopbygget ud.
  Bjælken fra en tidligere sløring forsvinder hermed helt i stedet for at
  blive overmalet hvid – en farvet cellebaggrund i en tabel bevares. Det
  gælder også på drejede sider, for tekst fra indlejrede
  formular-objekter og for **udfyldte formularfelter**: På den til formålet
  rastrerede arbejdskopi kommer udsnittet fra den nyrenderede originalside
  tilbage – også der, hvor intet tekstlag kender feltværdien. Også
  **erstattede billeder** i PDF'en kommer sådan tilbage – pixelerede,
  udviskede eller helt fjernede, helt eller kun det trukne udsnit. Kun
  hvor kildefilen ikke længere ligger ved siden af resultatet, forbliver
  det ved den hidtidige vej.
- **Slørede og erstatningsløst fjernede værdier kan også hentes tilbage i
  Word, Excel, PowerPoint og OpenDocument.** Hidtil krævede
  tilbagehentningen der en pladsholder i teksten – en bjælke eller et hul
  havde ingen vej tilbage. Nu tilbyder fundpanelet linjerne „sløret" og
  „fjernet", så snart den urørte kildefil ligger ved siden af resultatet:
  Maskuro sammenligner resultatet med originalen og indsætter værdien
  igen på bjælkens eller hullets sted – inklusive formatering, et opdelt
  forløb bliver igen helt. Gælder ligeledes for tekst, HTML, e-mail og en
  e-mails Office-bilag; bærer mailteksten en pladsholder og bilaget en
  bjælke, hentes begge tilbage i ét træk.
- **Også PDF-bilag i en e-mail eller Outlook-meddelelse kan hentes
  tilbage** – pladsholdere (nummererede og anonyme), bjælker og
  erstatningsløst fjernede. Uden lærred kommer stedet fra det oprindelige
  bilag; tilbage kommer værdien glyfpræcist, i originalens læserækkefølge.
- **Maskerede værdier kan hentes tilbage** – i PDF og i tekstvisningen. En
  maske („**** **** **** **** 3201") er aldrig entydig, to numre bærer
  den samme; derfor tager tilbagehentningen aldrig den ordrette vej, men
  spørger originalen, hvilken værdi der stod dette sted. Hidtil var disse
  linjer i fundpanelet slet ikke betjenbare.
- **Indlejrede billeder i Word, Excel, PowerPoint og OpenDocument kan
  hentes tilbage.** En værdi sløret i billedet kommer tilbage via sin
  panellinje – Maskuro læser originalbilledet og henter netop dette sted;
  et udvisket, fjernet eller med ansigter og koder bearbejdet billede
  henter den nye post „Hent indlejrede billeder tilbage" i menuen Rediger
  som helhed fra kildefilen – også gennem en e-mails eller
  Outlook-meddelelses Office-bilag. Et billede, der selv hænger som
  bilag og er sløret via tekstgenkendelse, kommer ligeledes tilbage via
  sin panellinje.
- **Opdigtede værdier kan hentes tilbage i tekstvisningen.** Hidtil meldte
  panelet der „Ikke entydig". Nu søger tilbagehentningen værdien i
  originalen og kræver på samme sted i resultatet netop den opdigtede
  erstatning – et opdigtet navn erstattes aldrig ordret overalt, det kunne
  et sted stå ægte.
- **Tilbagehentning i Word, Excel, PowerPoint og OpenDocument beholder
  originalens formatering.** Stod en værdi over flere forløb – „Anna"
  normal, „Musterfrau" fed og rød –, kom den hidtil helt tilbage i det
  første forløb og mistede fed og farve. Nu fordeler tegnene sig igen som
  i originalen; et Word-afsnit er derefter byte for byte det
  oprindelige. Det samme gælder HTML-sider, HTML-delen af en e-mail og
  HTML-brødteksten af en Outlook-meddelelse (.msg) – ved e-mailen bevares
  desuden doctypen, som rensningen hidtil stiltiende fjernede.
- **Tekstfiler beholder deres tegnsæt.** Rensning og tilbagehentning
  skriver nu `.txt`, `.md` og `.csv` i det tegnsæt, de blev leveret i –
  UTF-8 med og uden BOM, UTF-16, Windows-1252. Hidtil blev en
  Windows-1252-fil altid til UTF-8, og en UTF-16-fil kom beskadiget
  tilbage, også når intet i den skulle erstattes.
- **Tilbagehentede billeder beholder deres farvetilstand.** En
  gråtoneskanning kommer tilbage som gråtoner i stedet for en tre gange så
  stor RGB-fil, en palette som palette, sort-hvid som sort-hvid – for
  hele billedet med samme værdier som i originalen. Gælder for billedfiler
  og for billeder i PDF'er. CMYK og 16 bit forbliver RGB, fordi
  PNG-resultatet ikke kan bære nogen af delene.
- **En ramme i billedet henter hele den bearbejdning tilbage, den
  berører.** Pixelerede ansigter bærer en kant om den genkendte boks; den,
  der kun trak rammen over ansigtet, beholdt en pixeleret ring. Nu vokser
  rammen til den sammenhængende ændring i forhold til originalen – en
  ramme over øjenpartiet er nok. Adskilte bjælker ved siden af bliver
  stående; ved et helt fjernet eller helt udvisket foto gælder fortsat den
  trukne ramme. Gælder for billedfiler og billeder i PDF'er.
- **Sløringsbjælke over hele linjen.** I editorens linjetilstand løber
  bjælken nu fra det første til det sidste ord i linjen, ikke længere kun
  over det ramte ord – en bjælke i ordlængde afslører, hvor langt ordet
  var, og af seks tegn foran et postnummer kan et stednavn gættes.
  Betegnelser, beløb og tabelkolonner ved siden af værdien bliver
  stående – bjælken dækker feltet, ikke fakturaens linje. Den nye omskifter
  „Hele linjen" ved siden af „Tekstlinjer" stiller igen om til
  ordpræcist, hvis nabo-ordene skal blive stående; valget huskes.

### Rettet

- **Billeder i HTML-sider og e-mails forblev ukontrollerede – navnet i
  logoet stod fortsat læseligt efter rensningen.** Et billede indlejret i
  siden (``data:``-adresse) blev slet ikke rørt, kun dets alternative
  tekst; logoet i en mails HTML-gren (indlejret billede uden filnavn)
  faldt igennem bilagsfilteret; og ved det benævnte billedbilag var
  billedreglen „udvisk"/"fjern" uden virkning. Nu følger alle tre samme
  vej som en billedfil: tekstgenkendelse i det beholdte billede, ansigter,
  koder, metadata og billedreglen. Rapporten nævner billederne – også
  advarslen, hvis de forbliver ukontrollerede uden tekstgenkendelse – og
  „Hent indlejrede billeder tilbage" samt tilbagehentningen fra
  fundpanelet kender også disse billeder.
- **En Office-fil med billede kunne slet ikke renses, hvis
  tekstgenkendelsen ikke beherskede sproget.** På Mac'en læser den
  systemegne tekstgenkendelse; for hindi, græsk, kroatisk eller litauisk
  kan den ikke det og siger det også siden for nylig – ved Word, Excel,
  PowerPoint og OpenDocument afbrød dette imidlertid **hele** rensningen,
  og der opstod ingen fil. Teksten kunne dog fint renses; kun billedet var
  ikke læseligt. Nu skrives filen som ved PDF og enkelte billeder, og i
  resultatet står, at billederne IKKE blev kontrolleret – med grunden og
  henvisningen til „Administrer sprog".

- **I Excel-arbejdsbøger blev navne stående i valglister.** Listen til et
  rullefelt (datavalidering) renses nu som ethvert andet celleindhold;
  henvisninger til celleområder forbliver urørte, så arbejdsbogen forbliver
  hel.
- **Hvor pladsholderen ikke passede, stod en sort bjælke – nu står en
  kortere skrivemåde.** `[FØD_1]` i stedet for `[FØDSELSDATO_1]`, og først
  når heller ikke den korteste form passer, sløres der. En bjælke siger
  ingen længere, at der stod noget der; en kort pladsholder siger det. Det
  kunne editoren til efterretning allerede, den automatiske rensning
  hidtil ikke. Tilknytningsfilen fører begge skrivemåder til samme værdi,
  så også det forkortede kan hentes tilbage.
- **Det første klik på „Erstat" lod vinduet til efterretning stå kort
  stille.** Genkendelsen, der giver pladsholderen dens art (`[NAVN_3]` i
  stedet for `[BEGREB_3]`), blev først indlæst i dette øjeblik – omkring
  to til tre sekunder. Den forberedes nu i baggrunden ved åbning af
  vinduet; målt er 2289 millisekunder blevet til 193.
- **To samtidige rensninger kunne indlæse samme sprogmodel dobbelt** –
  f.eks. mappeovervågningen og hovedvinduet. Fordi hver model belægger
  flere hundrede megabyte, stod hukommelsesbehovet kortvarigt ved det
  dobbelte. Nu venter den anden kørsel på den førstes model.
- **Stedet i datolinjen fjernes nu også, når sprogmodellen alene ikke
  genkender det:** Hvad der sikkert er fundet som postnummer med by
  („3335 Amstetten"), trækker sit stednavn med sig gennem hele dokumentet
  – som et efternavn fra et fuldt navn. Og en forkortelse med ciffer foran
  et navn („T3 Hofbauer Christian") forbliver læselig i stedet for at
  forsvinde med i pladsholderen.
- **Tre lækager fra andengennemlæsningen af en ægte ordre lukket:**
  Sagsbehandleren „T3 Hofbauer Christian" gjaldt på grund af
  forkortelsen „T3" som kolonneoverskrift og forblev læselig; et sted, som
  sprogmodellen læste over linjeskiftet ind i kolonneoverskriften,
  slugte „Pos." og lod kundens fornavn blive stående; og et navn med
  tiltale („Hr. Robert Köttel") trak kun efternavnet med, ikke fornavnet –
  og til gengæld hvert „Hr.". Forkortelser er nu rene bogstaver,
  to-ords-navne ingen kolonneoverskrift, fund afskæres foran en
  kolonneoverskrift, og tiltalen tæller ikke med til navnet.
- **Stedet i datolinjen („Melk, 05.08.2026") direkte under adresseblokken
  forblev læseligt.** Sprogmodellen klæbede det sammen med stedet fra
  postnummerlinjen til ét fund, og det faldt som helhed mod
  postnummer-mønsteret. Nu forbliver den fremstikkende rest et eget fund.
  Fundet af den nye andengennemlæsning af resultatet
  (`werkzeuge/zweitlesung.py`).
- **Mac: En scanning på et sprog, som den systemegne tekstgenkendelse ikke
  beherskede (f.eks. hindi, græsk, kroatisk, litauisk), gjaldt som
  kontrolleret.** Der blev læst med det engelske reservevalg, det
  fremmede skrift forblev i billedet, og rapporten sagde „intet fundet".
  Nu hedder det „billede(r) blev IKKE kontrolleret" med grunden, og
  sprogadministrationen lover for sådanne sprog ikke længere
  tekstgenkendelse, blot fordi en Tesseract-sprogfil ligger der.
- **I PDF'en bliver skilletegnet efter en erstattet værdi stående.** Af
  „Indlagt den 01.03.2026, udskrevet den 04.03.2026." blev der hidtil
  „Indlagt den [DATO_1] udskrevet den [DATO_2]" – komma og slutpunktum
  manglede, ved pladsholdere ligesom ved forskudte data. Der fjernes nu
  kun den genkendte værdi, ikke hele ordet frem til næste mellemrum;
  komma, semikolon, punktum eller parentes bagved bliver på deres plads,
  og pladsholderen løber ikke hen over dem.
- **Russisk og ukrainsk kørte ubemærket med den svagere flersprogede
  model**, når en hjælpepakke til ordformsanalyse (`pymorphy3`) manglede –
  de egne modeller kunne så ikke indlæses, og „Львів" blev til en person.
  Til genkendelse af navne er ordformsanalysen ikke nødvendig; modellen
  indlæses nu uden den, og steder er igen steder.
- **Licenshenvisningerne på 16 sprog var på gammelt stade.** Der stod
  stadig, at MPL-kildekoden blev stillet til rådighed „på forespørgsel",
  QPDF gjaldt som MPL-2.0, syv byggeklodser manglede i tabellen (wordfreq,
  Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet),
  spaCy-afsnittet var engelsk, og til sidst hang et engelsk
  erstatningsafsnit. Nu står alle 18 versioner på samme stade som den
  tyske: kildearkiver permanent på maskuro.com/quellcode/oss/, QPDF
  Apache-2.0, Qt-LGPL-vejen, modelherkomst. Også den engelske tabel har de
  manglende linjer.

- **Kontraktord i genitiv („des Angebotsinhaltes", „des Anbotes", „des
  Terminplanes") gælder ikke længere som sted.** Et enkelt ord efter en
  genitiv- eller dativartikel med bøjningsendelse er et gattungsord –
  stednavne bøjes ikke („til Graz"). Står stedet andetsteds i dokumentet
  uden artikel („Burgenland"), forbliver også „des Burgenlandes" genkendt.
- **Forskudte, maskerede og opdigtede værdier rastrerede PDF-siden.**
  Efterkontrollen efter fjernelse tillod kun en pladsholder i firkantede
  parenteser i fundrektanglet; en forskudt dato („01.07.2026") eller en
  maskeret værdi („****1234") gjaldt som overset rest, og siden blev af
  sikkerhedsgrunde omdannet til et billede – ikke ved „Erstat". Nu
  forbliver sådanne sider tekst, og tilbagehentningen fra panel eller
  ramme leverer igen originalen.
- **Flerords-erstatningsværdier kunne ikke fortrydes via fundpanelet i
  PDF'en.** Et opdigtet navn („Greta Mayrhofer") eller en maskeret IBAN
  („**** **** **** **** 3201") består af flere ord; fundstedssøgningen
  sammenlignede ord for ord og meldte „Pladsholderen blev ikke fundet i
  dokumentet". Nu læses efterfølgende ord på samme linje sammen.
- **Efter tilbagehentning af en erstatningsløst fjernet værdi forblev dens
  panellinje stående.** Værdier, som strategien „slør" i
  pladsholdertilstand fjerner uden erstatning, har ingen pladsholder, som
  panelet kunne måle en forsvinden på. Nu slettes linjen, så snart værdien
  igen står i dokumentet.

- **Forkortelseskomposita som „E-hjælper" eller „S-tog" gælder ikke
  længere som navn.**
- **Orddelingsrester („frem-") og alt for lange komposita
  („byggearbejdskoordinationsloven", „byggepladskoordinator") gælder ikke
  længere som navn eller sted.** I en indscannet udbudstekst blev 28 ord
  mindre sløret dermed.
- **Positionslister fra indscannede tilbud gælder ikke længere som
  navneregister.** Ekstragennemgangen for registre (korte linjer) gjorde
  „kølerør" og „udendørsenheder" til personer; den fravælges nu, så snart
  positionsnumre som „1.1.5" står forrest i linjen. Datolinjer i
  mailforløb tæller hermed ikke som positionsnumre.
- **Kolonneoverskrifter og positionsnumre fra indscannede tilbud
  („Pos.", „Pos. 1.1.3", forkortelserne „E/L/S") gjaldt som navn eller
  sted.** En forkortelse alene på sin linje, en betegnelse med nummer og
  enkeltbogstaver linjevis er det ikke.
- **Siden „åndede" i vinduet til efterretning efter åbning af
  sammenligningsluppen** – ved „sidebredde" og „tilpas" hænger målestokken
  på synsfeltet, og det ændrer sig med hver rullebjælke, der kommer eller
  går; hver følgende handling rykkede siden et stykke. Lærredet retter nu
  det til af sig selv, indtil det står stille. Og zoomknapper, skydere og
  tastaturgenveje holder billedmidten også, når der dukker en rullebjælke
  op ved indzoomning.
- **Tværvendt gemte scanninger læses nu oprejst, og småtryk i store
  scanninger går ikke længere tabt.** Et 24-siders indscannet tilbud
  beholdt i hver sidefod seks bank-IBAN'er, CVR-nummer og momsnummer
  læselige: Scanningen lå i PDF'en drejet 90°, og tekstgenkendelsen udelod
  ved meget store billeder alt efter billedmål hele linjer. Nu tages den
  synlige drejning i betragtning, og store billeder læses i overlappende
  bånd – sidefødderne er sorte.
- **Gader efter personer med bindestreg foran grundordet („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8", „Dr.-Karl-Renner-Straße 12")
  genkendes som adresse.** I brevhovedet på et indscannet tilbud forblev
  en sådan adresse læselig, fordi mønsteret krævede et mellemrum foran
  „Straße".
- **IBAN'er fra tekstgenkendelsen, der bærer et O i stedet for 0 eller et l
  i stedet for 1, genkendes nu.** I småtrykket på en scanning læser
  tekstgenkendelsen gerne cifre som bogstaver; nummeret havde da formen
  af en IBAN, men kontrolsummen gik ikke op, og det forblev stående.
  Slår kontrolsummen fejl, prøves nu læsemåden med cifre – stemmer den
  så, er det IBAN'en. Forkerte kontrolcifre forbliver forkerte.
- **Sætningsstykker som „følgende koder på" gjaldt som sted.** Et navn
  eller sted, der begynder med et lille bogstav, er ikke et – bortset fra
  ved adelspartikler („van Gogh", „de Vries").
- **I editoren blev det sidste bogstav stående ved siden af
  sløringsbjælken** („…6", „…t", „…g"), og bjælken havde den trukne rammes
  højde i stedet for linjens. Årsag: Kunne editoren ikke opmåle siden,
  holdt den enhver ramme for „intet ord ramt" og anvendte den nøjagtigt –
  uden reglen om, at et halvt ord aldrig bliver stående. Det samme skete
  ved enkelte tekstkommandoer, som editoren ikke kunne stedfæste. Nu
  tæller altid ordkassen ved siden af: Hvad rammen væsentligt overlapper,
  falder helt.
- **Det sidste bogstav i et ord stak ud over sløringsbjælken.** Bjælken
  var beregnet efter fremføringsbredden fra skriftmetrikkerne; tegner
  skriften en glyf bredere, stod dens rest ved siden af bjælken. Kassen
  for et tegn tager nu også den tegnede glyf med.
- **Meddelelsen om omdannelse af en side til et billede lovede for
  meget.** „Fremstillingen forbliver den samme" passer ikke efter
  rastrering: Skrift og grafik er så billedpunkter, filen bliver større.
  Meddelelsen siger det nu – og nævner også den anden grund til, at der
  rastreres (ombygningen ville have beskadiget siden).
- **Teksten efter en fjernet værdi rykkede op til et punkt mod venstre.**
  Ved ombrydning af en linje blev begyndelsen målt ved glyfkanten,
  fortsættelsen ved pennens udgangspunkt – fremføringsbredden af det
  første bogstav blev stående som en fejl („C" 0,5 pt, „I" 1,0 pt). Nu
  regner ombrydningen gennemgående med pennens udgangspunkt; eftersætningen
  står på tiendedelspunktet nøjagtigt på sit sted.
- **Østrigsk momsnummer med mellemrum („ATU 187 35901") og et CVR-lignende
  virksomhedsnummer uden „FN" under sin betegnelse
  („Firmenbuchnummer: 30799v") genkendes.** Begge stod håndskrevet på et
  indscannet udbudsskema og forblev læselige, selv om tekstgenkendelsen
  havde læst det korrekt.
- **Tværliggende PDF-sider blev efter sløring uden grund omdannet til et
  billede.** Integritetskontrollen sammenlignede original og resultat i
  den drejede visning, men regnede deres sløringszoner udrejet – på en
  side med drejningsnotat lå den egne sløring derfor ved siden af sin
  zone og gjaldt som skade. Sådanne sider beholder nu deres tekstlag og
  vektorgrafik.
- **Også lige sider blev til tider unødvendigt omdannet til et billede**,
  når teksten efter en pladsholder rykkede en punkt frem – tilladt, men
  billedsammenligningen var finere end sin egen tolerance. Den
  sammenligner nu i halve punkter og rammer sin tolerance dermed
  nøjagtigt: op til to punkters forskydning slår intet ud, derover alt.
- **Angivelser i indlejrede formular-objekter blev stående.** Nogle
  skabeloner lægger brevhoved eller brevafslutning som en egen formular,
  der kun indlejrer siden. Et fund deri blev ganske vist planlagt og talt
  som fjernet, men aldrig skrevet – teksten stod fortsat der, og kun
  rastrering af hele siden fangede det. Nu skrives selve formularen om;
  en formular, der ligger på flere sider, én gang.
- **PDF-sider blev rastreret til et billede, selv om intet læseligt var
  blevet tilbage.** Et syv-siders tilbud ramte det på seks sider; det
  voksede fra 73 kB til 3,3 MB og mistede sin skrift til et aftryk.
  Årsagen var mellemrum, der står flere gange i træk i dokumentet, men af
  læseren kun meldes én gang: Teksten efter en fjernet angivelse rykkede
  sin bredde mod højre, efterkontrollen fandt nabo-ordet i fundrektanglet
  og greb til rastrering. Beholdte linjerester står nu igen nøjagtigt på
  deres sted; samme tilbud renses nu uden en eneste rastreret side (76 kB).
- **Nøglenavne og fakturahoveder gjaldt som personer.** I en adgangsfil
  blev navnet på miljøvariablen („AWS_ACCESS_KEY_ID") erstattet, ikke kun
  dens værdi; på en engelsk faktura faldt overskriften „Bill to" som
  fornavn. En betegner i versaler med understregninger er aldrig et navn,
  og et ord i en linje, der som helhed er en feltbetegnelse, heller ikke –
  modtageren nedenunder findes fortsat.
- **Søgningen i vinduet til efterretning gik i stå ved store PDF-sider.**
  Hvert bogstav i søgefeltet lod siden rastreres på ny, selv om kun
  fremhævningen ændrede sig. Det rendrede sidebillede bliver nu stående,
  så længe side, zoom og visning er de samme – også originalen i
  sammenligningsluppen; bladring, zoomning og en ny filstatus tegner som
  hidtil frisk.
- **Positionsnumre i tilbud gjaldt som IP-adresse eller telefonnummer.**
  En artikellinje som „1.3.3.4 … 5-Port Gigabit Switch" fik
  struktureringsnummeret til at blive en netadresse, fordi „Port" talte
  som teknisk omgivelse – nu tæller det kun som en selvstændig angivelse
  („Port 80"), ikke som orddel. Og „1.3.3.6 216879" (positions- plus
  artikelnummer) sløres ikke længere som telefonnummer. Ægte IP-adresser
  og telefonnumre i sådanne lister forbliver genkendt.
- **Artikellinjer i tilbud gjaldt som postnummer med by.** „35252 DIETZEL
  SALR" (artikelnummer med producent) og „1000 AWG" (mængde med
  ledertværsnit) blev i nummererede positionslinjer sløret som adresse,
  fordi et versalord efter et tal gjaldt som stednavn i versaler. I
  positionslister gælder det ikke længere; „1080 WIEN" i adresseblokken
  og steder i småbogstaver forbliver genkendt overalt.
- **Den ekstra navnegenkendelse slørede rollelinjer og kolonneoverskrifter
  i tilbud.** „Partitimeløn montør + E-hjælper" gjaldt 49 gange som
  person, kolonneoverskriften „Pos. Betegnelse Mængde EH" 19 gange som
  sted – en 19-siders ordre blev derved ulæselig. Sådanne fund i
  positionslinjer falder nu, hvis de selv bærer tegn, som intet navn har
  (plus, skråstreg, ciffer, forkortelse) – også når linjen ender med et
  beløb („Alternativt marked … - PV/LS AC-forsyning 1 290,00"). Navne i
  registre og lister – som niveauet er til for – forbliver urørte.
- **„Kunden" gjorde i forretningsbetingelser hvert „kunde" til et navn.**
  Tog den ekstra navnegenkendelse artiklen med i fundet, gjaldt det som et
  toleddet navn og beskyttede alle 35 øvrige steder for det samme ord. Nu
  trækkes artiklen fra, og „kunden" falder som allerede før „kundens".
- **Betegnelser gjaldt som værdi.** „E-mail" blev syv gange sløret som
  mailadresse, „telefonnummer" og „faxnummer" som telefonnummer. En
  adresse uden @ og et telefonnummer uden cifre tæller ikke længere.
- **Kolonneforkortelser med ét bogstav („L: 154,50", „S: 0,00") gjaldt som
  navn** – 25 gange i et solcelletilbud. Et enkelt bogstav er hverken navn
  eller sted.
- **PDF-sider blev alt for ofte omdannet til et billede.** To årsager,
  begge fundet i ægte tilbud: Sætter en PDF hver glyf som sin egen
  kommando og gemmer et mellemrums-glyf uden tekst-tegn nedenunder,
  forskød tilknytningen sig fra det punkt med ét – af den fjernede værdi
  blev det sidste bogstav stående („ŠkodaTopCar**d**"), og efterkontrollen
  rastrerede siden med rette. Og et ord delt ved linjeskift
  („Databeskyttelses-") gjaldt på grund af læsebibliotekets
  delingsstregsmarkering som forskudt. Begge rettet: Et køretøjstilbud gik
  fra 4 rastrerede sider til 0, en 19-siders ordre fra 7 til 0 – skriften
  forbliver skrift, filen forbliver lille.
- **To yderligere rastreringsgrunde rettet:** Bringer et dokument selv en
  skrift ved navn „F1" med, blev pladsholderne over billeder sat i dens
  skrift og var ulæselige – nu får den egne betegnelsesskrift et frit
  navn. Og mangler læsebiblioteket et mellemrum midt i en lang
  tekstkommando, bevises stedet nu også ved flerbyte-skrifter (samme
  kode, samme tegn) i stedet for at gætte til slutningen – før blev et
  bogstav af den fjernede værdi stående og resttegnen rykkede synligt til
  siden. Dertil to sidste tilfælde: en kommando af snesevis af
  mellemrums-glyffer lod tilknytningen løbe fra (navnet derefter blev
  stående), og en stor overskrift med fremføringsbredde fandt ikke sit
  første tegn (firmanavnet blev stående). **Af ni ægte tilbud rastreres
  nu ikke en eneste side længere** – før var det 30 af 90.
- **Ved rastrering forsvandt billeder under en sort blok.** Skal en side
  omdannes til et billede, rendres den fra originalen – og det kender
  ingen billedrensning. Hidtil faldt derfor *hver* billedflade på siden
  under en bjælke, også urørte. På et tilbud sad adresse og to
  certifikatlogoer i samme brevhovedbillede; bjælken tog logoerne med.
  Nu indsættes det allerede rensede billede: Adressen deri er sløret,
  alt andet forbliver synligt. Et fjernet billede efterlader hvidt papir i
  stedet for en sort kasse.

- **Rensede scanninger blev mange gange større end originalen.** Hvert
  billede, hvor noget blev sløret, kom som ukomprimeret råbillede tilbage
  i filen – ved en 24-siders scanning voksede den derved fra 11,8 til
  52,9 MB. Billeder beholder nu den art, de forelå i: et foto forbliver et
  foto, en faxscanning forbliver sort-hvid, et farveløst billede lagres
  ikke som farvebillede. Samme fil er nu 15,6 MB stor, uden synlig
  forskel.

- **Indscannede PDF-filer fra kontorapparater kom tilbage som
  stribemønster.** Sådanne scanninger lægger skriften som et skarpt
  sort-hvid-lag oven på et groft farvebillede – Canon, Xerox og Kofax
  bygger deres filer sådan. Ved sløring i billedet blev dette lag skrevet
  forkert tilbage; resultatet var ulæseligt. Ved et seks-siders tilbud
  ramte det ni af seksten billeder. Det behandles nu korrekt, i sin egen
  farve, og de slørede steder er deri virkelig væk.

- **„Fjern alle billeder" tog teksten fra en indscannet side.** Skriftlaget
  på en sådan scanning er teknisk et billede – det blev fjernet
  henholdsvis udvisket med, og tilbage blev et tomt ark. Det bliver nu
  stående; logoer, stempler og underskrifter viger fortsat.

- **Kontrollen for beskadigede PDF-sider rastrerer ikke længere på grund
  af en mikroskopisk forskydning.** Et ved rensning nyforankret
  tekststykke må forskyde sig op til to punkter; billedsammenligningen
  talte det alligevel som skade og genopbyggede siden som et aftryk – der
  gik vektorgrafik som tabellinjer tabt, og over fundsteder lå en bjælke i
  stedet for en pladsholder. Sammenligningen tillader nu samme lille
  forskydning som ordkontrollen; ægte skader falder fortsat i øjnene.

- **Tilbagehentning af mange værdier i træk fejlede ikke længere på
  Windows med „adgang nægtet".** Den, der i en Office-fil tilbagekaldte
  mange panellinjer kort efter hinanden, kunne fejle ved en kortvarig
  fillås fra virusscanneren; udskiftningen venter nu kort på sådanne
  låse.

- **Windows-vejen for kommandooverdragelse afsluttede kontrolløren i
  stedet for at kontrollere.** Livskontrollen af den lyttende instans
  sendte på Windows ved en fejl et ægte Ctrl+C til sin egen
  konsolgruppe; den spørger nu uden signal hos systemet.

- **Flerords-feltbetegnelser virkede ikke, til gengæld virkede deres
  brudstykker.** „Date of birth", „Bank account", „Cuenta bancaria" og
  „Numero de cliente" stod i betegnelseslisten, men blev der splittet i
  enkeltord og ramte derfor aldrig; tilbage blev ordstykker som „de" og
  „of", som siden gjaldt som betegnelse – „de" er dog en navnebestanddel
  („Anna de Vries"). Begge dele er rettet: Vendingerne virker nu som
  helhed, brudstykkerne er væk.

- **Tyske hilsenformler med „ß" blev behandlet som personnavn på trods af
  optagelse.** Under „Herzliche Grüße" eller „Mit freundlichen Grüßen"
  stod i resultatet en pladsholder, selv om begge vendinger altid har
  stået på modlisten. Årsagen var en skrivemåde, der aldrig kom med i
  sammenligningen; berørt var otte poster over fem lister. De virker nu
  alle.

- **„John Staff" forblev uerstattet.** Et efternavn, der samtidig er en
  engelsk kolonneoverskrift, blev kasseret sammen med af
  betegnelsesfilteret. Overskriften forbliver fortsat urørt, navnet
  nedenunder erstattes igen.

- **Værdier fra betegnede formularfelter forbliver beskyttede i
  AI-niveauet.** AI-niveauets lokale skiftedommer fik hidtil også fund
  forelagt til bedømmelse, hvis betydning feltbetegnelsen allerede havde
  belagt („Fødselsdato:" over værdien) – og måtte kassere dem. Sådanne
  strukturelt belagte værdier forelægges den ikke længere.
  Tilknytningsfilen nævner nu desuden genkendelsesvejen for hver
  erstatning („belæg").

- **En PDF-side, hvis bevarede tekst tog skade ved rensning, genkendes nu
  og genopbygges som aftryk af originalen.** Ved visse producentskrifter
  kunne bevarede tekststeder efter rensning fremstå som sorte blokke
  eller rykke ord sammen, selv om alle angivelser, der skulle fjernes,
  var fjernet korrekt. Maskuro sammenligner nu resultatet ord for ord og
  billedpunkt for billedpunkt med originalen; en beskadiget side erstattes
  af sit rene aftryk – med sløringsbjælker over fundsteder, slørede
  billedområder og søgbar tekst. Siden forbliver læselig, fjernelsen
  pålidelig.

### Ændret

- **I de oversatte grænseflader hedder hvert fagbegreb nu det samme
  overalt.** For et og samme tyske ord stod alt efter vindue to eller tre
  oversættelser ved siden af hinanden: Kontrolprotokollen hed på norsk
  dels „Revisjonslogg", dels „Kontrollogg", gratisniveauet dels
  „Gratisnivå", dels „Gratisversjon" – og tilsvarende på et dusin andre
  sprog. Den, der søgte en indstilling, fandt den i det næste vindue under
  et andet navn. Der er ensrettet til det ord, som grænsefladen alligevel
  bruger oftest.

  Dermed kom steder for dagens lys, hvor et ord stod for to
  **forskellige** ting: Fransk, græsk og koreansk brugte samme udtryk for
  „sløre" og „maskere" – altså netop dér, hvor programmet forklarer
  forskellen („Sløring fjerner uden erstatning, maskering bevarer
  formen"). Begge dele er nu holdt adskilt. For svensk står denne
  beslutning fortsat åben: Der hedder sløringen „maskera" – samme ord som
  maskeringen.

- **Spørgsmålet om brugstypen ved første start er bortfaldet.** Kort efter
  start kom et vindue („Privat eller i virksomheden?"), og i
  indstillingerne stod en linje om det. Begge dele findes ikke længere –
  uden erstatning. En angivelse, intet hænger på, angiver forkert, hvem
  der vil have den forkerte licens, og den, der er ærlig, har ikke brug
  for den; den kostede alle et klik på et tidspunkt, hvor ingen tænker på
  licenstyper. Hvilken licens der er den rigtige, står der, hvor det
  afgøres: på prissiden, i kassen og i hjælpen. Huse, der ruller Maskuro
  centralt ud, angiver fortsat brugstypen via vorgabefilen.

- **Henvisningerne om licenstypen nævner nu det tilfælde, det drejer sig
  om.** Privatlicensen gælder udelukkende privat brug; alt fagligt eller
  erhvervsmæssigt arbejde kræver firmalicensen – også som selvstændig
  uden ansatte. Det stod sådan i licensbetingelserne, men hverken i
  programmet eller i hjælpen: Der var altid kun tale om virksomhedens
  domæne, og det dækker netop ikke dette tilfælde: En selvstændigs
  computer hører ikke til noget domæne. Henvisningen ved indlæsning af en
  privatlicens siger det nu, ligeledes vejledningens licenskapitel og de
  hyppige spørgsmål, der har fået en egen post til dette formål. Der
  spærres fortsat intet.

- **De endnu ikke udleverede veje ligger nu samlet.** Indstillingerne har
  fået en side „Udviklere"; der står den maksimale genkendelse (AI) samt
  dens kontrolprøve, ordliste-kataloget og mappeovervågningen. Alle tre
  er bygget, men ikke afprøvet i praksis – de er derfor kun synlige med en
  udviklerlicens, og det overalt samtidig: Siden, menuposterne og
  virkningen i kørslen hænger på samme beslutning. Uden denne licens
  forbliver et tidligere tilkoblet AI-niveau uden virkning; dets
  indstilling slettes ikke og gælder igen, så snart vejen udleveres.

### Forbedret

- **„Hvad der søges efter" viser tre yderligere lister fra
  navnegenkendelsen.** Tiltalerne, hvorefter det følgende ord læses som
  navn; titlerne og rollerne, som derefter fortsat **ikke** er navnet
  („Hr. borgmester Huber"); og de firs flersprogede betegnelser, hvorpå
  sagsnumre, sags- og fald-numre genkendes. Alle tre har altid virket, men
  var ikke at se i oversigten.

- **„Hvad der søges efter" viser to hidtil manglende ordlister.**
  Tiltalerne og titlerne, som gør et foranstående ord til et navn („Hr.",
  „Fru", „Dr."), og forkortelserne for standardiseringsorganisationer,
  som Maskuro på skelner en normhenvisning som „ÖNORM B 2110" fra en
  person med. Begge har altid påvirket genkendelsen, men stod ikke i
  oversigten.

- **Positionslister, indholdsfortegnelser, udstyrsopregninger og
  normhenvisninger forbliver læselige.** Genkendelsen ser nu linjens
  byggeform: Et gættet navn i en struktureringslinje („1.3.1 Jordkabel
  1kV"), en registerlinje med ledepunkter, en opregning („- trådløs
  opladning med magnetring"), over en mængde-/prislinje, i en
  kolonneoverskrift eller efter „ved hjælp af" er et sagbegreb og
  erstattes ikke længere. Ægte navne forbliver beskyttede – via tiltale,
  feltbetegnelse og belægget andetsteds i dokumentet; i målekorpuset
  mistede ikke en eneste angivelse sin beskyttelse. I forretningskorpuset
  falder falske alarmer dermed fra 25 til 6.

- **Overskrifter, formularbetegnelser og hilsenformler holdes sjældnere for
  navne – på tysk og engelsk.** Ordlisterne, som Maskuro adskiller
  sagord fra personnavne med, er vokset betydeligt: Betegnelser fra
  fakturaer, formularer og myndighedspost („sagsnummer",
  „anvendelsesformål", „omkostningssted", „Sort code", „Subtotal"),
  afsnitsoverskrifter fra ansøgninger og rapporter („KARRIEREFORLØB",
  „KVALIFIKATIONER", „SUMMARY", „REFERENCES"), tyske og engelske
  dokumenttyper („ordrebekræftelse", „referat", „Timesheet",
  „Agreement") samt kommandoformer fra vejledninger („Send…",
  „Select…"). Den engelske side var hidtil påfaldende tyndt besat.

- **Betegnede felter afslører nu også, hvad der står i dem, når
  betegnelsen er sammensat.** „Leveringsadresse", „Fakturaadresse",
  „Sagsbehandler", „Kontohaver", „Contact person" og „Billing address"
  tilordner nu værdien ved siden af eller nedenunder samme art som det
  enkle „Adresse" eller „Navn" – i den udfyldte formular med felter er det
  forskellen mellem fundet og overset.

- **I vinduet til efterretning blader musehjulet videre ved sidekanten.**
  Den, der ruller videre ved slutningen af en side, lander øverst på den
  næste; den, der ruller tilbage ved begyndelsen, nederst på den
  foregående – et dokument kan dermed rulles igennem fra først til sidst
  uden at røre sideknapperne. Tastaturet (Side↑/Side↓) kunne det
  allerede; en kort åndepause mellem to sideskift forhindrer, at et
  trackpads eftersvingning bærer gennem det halve dokument.

- **Sideminiaturerne i vinduet til efterretning sidder centreret i
  fanget.** Hidtil klæbede de til venstre kant, og ved bredere trækning
  voksede kun den tomme rand til højre.

- **Værktøjslinjen i vinduet til efterretning viser sine grupper.**
  Skillestregerne har nu luft og farve, „Søg" og „Overfør til alle sider"
  står som egne grupper ved siden af værktøjerne, og „Overfør" fremkommer
  kun ved dokumenttyper, hvor det kan have virkning. Hver post i linje og
  menuer bærer nu et billede: „Tekstlinjer" og sammenligningsluppen har
  fået egne symboler (luppen delte hidtil sit med „Før/efter"), dertil
  zoom, hele siden, sidebredde, drej, blad og tastaturgenveje. „Åbn med
  systemprogram" står nu også i linjen ved siden af Udskriv – vejen fra
  det færdige resultat til det vante program er et klik, ingen menugang.

- **Ved udklipsholder-rensning står der igen med, at der skal ses efter.**
  I indstillingerne står henvisningen permanent ved siden af kontakten:
  Maskuro kan overse personoplysninger eller behandle angivelser forkert,
  den indsatte tekst skal gennemgås før videregivelse. Ved tilkobling
  nævner meddelelsen den desuden, og den noteres i udgangsområdet – også
  når intet symbol kører i infoområdet. Ved hver enkelt kopiering
  fremkommer den bevidst ikke: En henvisning, der ville komme halvtreds
  gange om dagen, ville ikke blive læst efter tredje gang.

## 0.10.36-beta.1 – 20. august 2026

### Forbedret

- **Tekniske forretningsdokumenter bliver ikke længere sønderslørede.**
  Fire genkendelsesbremser, uddraget fra elleve virkelige tilbud og ordrer:
  Struktureringsnumre („1.3.1.1") gælder ikke længere som IP-adresser,
  normhenvisninger („ÖNORM EN 62446") og identifikationskoder ikke længere
  som postnummer eller telefonnummer, og rolleord efter artikler („kunden",
  „ordregiveren") ikke længere som navne – i et virkeligt tilbuds
  forretningsbetingelser er dermed alle 46 rolleord igen læselige i stedet
  for slørede. Adresser med landekode („A 3390 Melk", „D-94032 Passau")
  fjernes nu fuldstændigt, i stedet for at lade postnummeret stå tilbage
  som en forældreløs rest.

- **Ordlister kan nu ses fuldstændigt.** Under „Hjælp → Ordlister …" kan de
  lokalt anvendte genkendelses- og kontrollister gennemsøges sammen med
  sprog, formål, kilde og indhold. Dertil hører også wordfreq-, medicinske,
  personlige og centralt administrerede lister samt beholdningerne til
  opdigtede erstatningsværdier. Håndbogen beskriver kataloget i et eget
  afsnit.

- **Færdige fillinjer viser det anvendte genkendelsessprog.** Bag „færdig"
  står nu f.eks. „Tysk" eller "Engelsk", så et upassende automatisk
  sprogvalg straks falder i øjnene. Måtte et andet installeret sprog
  springe til, viser en pil begge sprog.

- **Den nye sammenligningslup viser under gennemlæsning straks det
  tilsvarende sted i originalen.** Dens forstørrede originaludsnit følger
  musemarkøren over det fortsat redigerbare resultat; ved tekst følger den
  afsnittet. Luppen kan bruges ved vinduets kant eller trækkes ud som eget,
  maksimerbart vindue. Dens zoom kan indstilles direkte mellem 50 og 300
  procent og huskes ligesom aktiveringen. „Nulstil" bringer også en
  maksimeret eller uheldigt dokket lup tilbage til venstre i en betjenbar
  størrelse. Erstattede originalværdier er fremhævet gult i luppen, så de
  berørte ord straks falder i øjnene under læsningen. Én gang aktiveret,
  åbner den sig igen ved fremtidige egnede dokumenter – også efter en
  programgenstart. Den hidtidige før/efter-omskifter forbliver i
  visningsmenuen. Håndbogen beskriver den i et eget afsnit.

- **Open source- og modelbeviser er nu udgivelsespræcise.** Pakkebygningen
  genererer en maskinlæsbar komponentliste sammen med hashes af de
  vedlagte licenstekster. MPL-kilder, modelherkomst, faste revisioner,
  ændringer og SHA-256 dokumenteres separat; efterindlæste modeller får
  deres herkomstbevis direkte i modelmappen. Bevægelige Tesseract- og
  spaCy-referencelister er nu fast fastgjort. Salgsartefakter forbliver
  spærrede, indtil alle kilder og modelbilag er offentliggjort og
  kontrolleret.

- **Den lokale wordfreq-datamængde er fuldstændigt licensbelagt.**
  Pakkebygningen kontrollerer version 3.1.1, 39 uændrede små lister
  inklusive CJK og det kinesiske tegnkort mod antal, størrelse og
  manifest-kontrolsum. Apache-2.0-kodehenvisning, fuldstændig
  CC-BY-SA-4.0-licens, attribution, datakilder og de udeladte store,
  Jieba- og ikke understøttede lister er dokumenteret i pakken.

- **Hyppige sætningsord slørede sjældnere ved en fejltagelse.** En lokal
  frekvensordbog tjener som ekstra kontrolprøve, når navnegenkendelsen
  anser et udsagnsord, pronomen, en artikel eller en præposition for en
  person. Ordbogen afgør aldrig alene: Navneord, flerdelte navne samt navne
  i felter, lister og efter tiltaler forbliver beskyttede. Kinesisk,
  japansk og koreansk bruger udelukkende deres allerede eksisterende
  sprogmodellers nøjagtige tokengrænser; for ikke-eksisterende sprog
  indsættes ikke et formodet lignende ordbogssprog. Til dette overføres
  ingen dokumenttekst til internettet.

- **Tekniske produkt- og udstyrsbegreber opfattes ikke længere så let som
  navne eller steder.** Den lokale kontrolprøve forbinder nu hyppighed,
  ordklasse, teknisk orddannelse og sagsfelter. Derved bliver f.eks.
  „Travel-Assistent", „Family-Bonus", „WLTP-værdi", „Easy-Start" og
  sammensatte numre-, holder- eller bremsebegreber stående i dokumentet.
  Engelske bestanddele slås også op lokalt i tysk sagtekst; ægte egennavne,
  tiltaler samt person- og stedfelter beholder forrang. Desuden gælder en
  „2-årig producentgaranti" ikke længere som alder.

- **Qt-/PySide-licensrettighederne er nu fuldstændigt sporbare.**
  Programpakken indeholder desuden GPL-3.0-helteksten, nøjagtige
  Qt-versioner, et kildekodetilbud og en tysk/engelsk vejledning til
  udskiftning af de dynamiske biblioteker inklusive lokal
  macOS-gensignering. En salgsbygning blokeres, så længe de nøjagtige
  kildearkiver for den udleverede version ikke er tilgængelige på den egne
  kildekodeside.

- **Licens og opdateringsstatus siger nu entydigt for hvert niveau, hvad
  der gælder.** I licensvinduet og ved opdateringsindstillingerne står,
  om opdateringer er inkluderet, til hvilken dato de rækker, og om den
  kørende version forbliver brugbar permanent. Privatlicenser installerer
  efter skæringsdatoen ikke længere en senere udkommet version; også en
  nyligt downloadet installer genkender på sin fast indbyggede
  udgivelsesdato, om den indtastede nøgle omfatter den. Den sidste dækkede
  privatversion forbliver permanent brugbar. Slutter derimod et
  virksomhedsabonnement, slutter brug og opdateringer; prøveperiode og
  gratisniveau åbner sig ikke som en omvej.

- **Private permanente licenser finder nu også den rigtige programversion
  efter en geninstallation.** Et signeret versionskatalog fører alle
  stabile versioner og deres pakker. Er den sidste installer, der er
  omfattet af købet, ikke længere tilgængelig, må i stedet automatisk
  netop den næste højere tilgængelige stabile version bruges – aldrig en
  beta eller nightly. Ved en for ny installation kan kunden installere det
  tilladte niveau eller skifte til købssiden for en ny opdateringsperiode;
  et tilbageskridt sker ikke stiltiende. Det gælder også for
  administrerede MSI-installationer.

- **Den automatiske ansigtssløring er nu entydigt beskrevet.**
  Programhjælpen og databeskyttelsesteksten benævner funktionen
  „Genkend og gør ansigtsområder ukendelige" og afgrænser den fra
  identifikation, genkendelse, ansigtssammenligning, biometriske skabeloner
  og person- eller ansigtsdatabaser. De gør desuden klart opmærksom på, at
  den fuldstændigt lokale genkendelse kan overse eller fejlagtigt markere
  områder, og at resultatet derfor skal kontrolleres visuelt. Også ved en
  enkeltvist renset billedfil nævner resultatrapporten nu genkendte og
  pixelerede ansigtsområder; en manglende tekstgenkendelse beskrives
  herved ikke længere fejlagtigt som en fuldstændigt uændret fil.

## 0.10.36-alpha.20260820 – 20. august 2026

### Rettet

- **Anonymiserede angivelser kan nu hentes fuldstændigt tilbage uafhængigt
  af rækkefølgen.** Den tidligere tilbagehentning søgte værdien via synlige
  tekstankre. I tætte tabeller, direkte nabo-pladsholdere og usynlige
  Office-/mail-lagre manglede disse ankre; nogle gange kunne et udtryk
  derfor først hentes tilbage, efter en anden klartekst tilfældigt havde
  skabt et nyt anker. Nu sammenlignes resultat og original pr. ægte
  formatbærer med den fuldstændige tilknytning, og kun de belagte steder
  for den valgte værdi skrives.

- **Navne, mailadresser, numre og egne kontrolbegreber forbliver entydigt
  betjenbare også ved overlappende genkendelse.** Er den samme klartekst
  tilknyttet to typer, afgør den pladsholder, der faktisk står på
  fundstedet, sammen med den klikkede sidebar-linje. Et ikke-belagt
  værdi-/pladsholderpar forbliver fortsat sikkert spærret.

- **Mail-særtilfælde efterlader ikke længere skjulte pladsholdere.** Det
  gælder MIME-kodede emner, tekstbilag og navne adskilt via HTML-markup i
  EML og MSG. UTF-8-HTML uden egen tegnsætsangivelse bliver desuden ikke
  længere omkodet til mojibake ved hvert redigeringstrin i Outlook-filer;
  ældre resultater, der allerede er skrevet sådan, forbliver hentelige
  tilbage.

### Forbedret

- **En ny frigivelsesmatrix betjener hver anonym sidebar-linje enkeltvis og
  bevidst baglæns.** Den kontrollerer alle 14 tekst-, Office-, web- og
  mailformater samt PDF, derefter også formler, attributter, relationer,
  kommentarer, mailhoveder, bilag og interne biarkiver. Den fuldstændige
  macOS-kørsel omfatter nu 149/149 grønne kontrolskripte.

## 0.10.35-alpha.20260820 – 20. august 2026

### Forbedret

- **Sprogmålinger sammenligner nu virkelig ens med ens.** Det regelmæssige
  målekorpus indeholder de samme 14 dokumenttilfælde med de samme syv
  tekst- og fire billedopgaver på tysk og engelsk. En fuld kørsel gentager
  netop denne matrix for alle tolv eksisterende korpussprog. Formularer,
  tabeller, chats og andre endnu ikke fuldt oversatte strukturprøver
  bevares, men vises adskilt og blandes ikke længere ind i sprogkvoter.

- **Den fulde kørsel skriver en egen målerapport for hvert sprog.** Uden
  sprogomskifter kontrolleres bevidst tysk og engelsk; `--alle-sprachen`
  kræver det fulde tolv-sprogs-korpus og afbryder før det første dokument,
  hvis et sprog eller et tilfælde mangler. Ensnavnede resultater ligger i
  adskilte sprogmapper. Totalrapporten nævner ud over den vægtede fundkvote
  også det uvægtede gennemsnit af sprogkvoterne.

- **Den åbne sprogsammenligning viser nu også sin faktiske grænse.** I den
  regelmæssige kørsel med tekstgenkendelse fjerner tysk og engelsk 218/218
  kendte angivelser uden falsk alarm. Den fulde test med tekstgenkendelse
  og høj-niveau fjerner 1.255/1.308 angivelser med 17 falske alarmer; elleve
  sprog opnår 100 procent, hindi 51 procent. Tidligere fulde kvoter beroede
  på ulige dokument- og målmængder og kan ikke sammenlignes med den nye
  matrix.

## 0.10.34-alpha.20260819 – 19. august 2026

### Rettet

- **Flere gange forekommende navne forbliver tilgængelige i sidebaren efter
  en enkelt tilbagehentning.** Hidtil forsvandt hele navnelinjen allerede
  efter det første tilbagehentede `[NAVN]`-sted. Yderligere steder med
  samme navn blev derved stående som pladsholder og blev til tider endda
  blokeret, indtil andre navne var hentet tilbage. Nu forsvinder linjen
  først efter det sidste sted; allerede tilbagehentet klartekst
  anonymiseres alligevel ikke automatisk igen. Det gælder ligeledes en
  delvist lykkedes samlet tilbagehentning og rammeværktøjet i PDF'er.

- **„Fortryd erstatning" fungerer også fra Office-sidevisningen.** Den
  synlige side er der kun en flygtig PDF-forhåndsvisning; nu ændres
  korrekt Word-, regneark- eller præsentationsdokumentet nedenunder, og
  forhåndsvisningen fornyes derefter.

- **Tilbagehentningen henter nu også en værdis skjulte modstykker
  fuldstændigt tilbage.** I Word-, OpenDocument-, Excel- og
  PowerPoint-filer kan de samme angivelser desuden ligge i formler,
  kommentarer, diagrammer, feltværdier, alternative tekster og
  henvisningsmål; HTML, EML og MSG fører dem desuden i attributter, JSON,
  meddelelseshoveder og bilag. Hidtil forblev der alt efter format en del
  stående som pladsholder. Nu kan hver angivelse, der tilbydes i
  fundområdet, hentes tilbage uafhængigt og i vilkårlig rækkefølge. Bevidst
  fjernede metadata, ændringsforløb og transporthoveder forbliver fjernet
  af sikkerhedsgrunde.

- **Ved tilbagehentning fra billeder bliver der ikke længere stående en
  sort kantlinje.** Højre og nederste kant af en ramme blev ved kopiering
  fra originalen udlagt et billedpunkt for knapt. Koordinaterne stemmer nu
  overens med sløringen.

### Forbedret

- **Frigivelseskontrollen sender nu hver af de 22 understøttede
  filendelser gennem en fuldstændig rundtur.** Indholdsrige filer renses,
  alle tilbudte værdier genoprettes og kontrolleres derefter grundigt.
  Dertil kommer ægte sidebar-betjening, pixelnøjagtige billedsammenligninger
  og en synlig LibreOffice-gengivelse af alle syv kontorformater. De små
  regressionstests forbliver dér, hvor de dækker et eget fejl- eller
  sikkerhedstilfælde; en påvist dobbelt HTML-kontrol og testen af den
  fjernede sort-hvid-tilstand er udgået.

- **Denne fasnings fuldstændige målekorpus ligger klar til efterprøvning.**
  Pakken indeholder 294 syntetiske dokumenter i tolv formater og tolv
  sprog, 2.564 kendte angivelser, fire maskinlæsbare målelister og en
  vejledning. Downloadet på kvalitetssiden bruger et indholdsafhængigt
  filnavn, så browsere ikke ved en fejl leverer en ældre version fra
  cachen.

## 0.10.33-alpha.20260819 – 19. august 2026

### Nyt

- **Også i billedfiler kan enkelte steder nu hentes tilbage fra originalen.**
  Rammeværktøjet „Hent original tilbage" kopierer billedpunkterne på samme
  position tilbage fra den urørte kildefil. Vejen forbliver spærret, hvis
  kilden mangler eller har andre billedmål; dermed kan intet indhold
  indsættes fra et forskudt sted.

### Forbedret

- **Manuelle sløringsbjælker rykker som standard fast på tekstlinjer.** Et
  træk over flere linjer skaber en ensartet høj bjælke pr. linje og lader
  det hvide rum imellem stå frit. Til underskrifter, grafik og andre
  særtilfælde skifter „Fri ramme" tilbage til den selvvalgte højde.

- **Editoren forklarer det næste håndgreb direkte over dokumentet.**
  Anvisningen skifter med dokumenttype og værktøj og siger, om der forventes
  et ordklik, en tekstmarkering eller en ramme. Desuden viser værktøj,
  musemarkør og livevisning allerede før slippet, hvad der vil ske.

### Fjernet

- **Den fejlbehæftede sort-hvid-udskrift er fjernet.** I nogle PDF'er var
  usynlige tekstfelter forskudt i forhold til den rastrerede side; den
  tilsyneladende filformindskelse var ikke denne sikkerheds- og
  visningsrisiko værd. Almindelig PDF-rensning og målrettet rastrering af
  problematiske sider forbliver bevaret.

## 0.10.32-alpha.20260819 – 19. august 2026

### Nyt

- **Mappeovervågningen kører nu virkelig i baggrunden.** Indgang,
  udgang og regler står på deres egen side under „Indstillinger“.
  Den startes og stoppes via Maskuro-ikonet i proceslinjen eller
  menulinjen; punktet vises kun med den dertil frigivne
  licens. Indstillingsvinduet kan derefter lukkes, og hovedvinduet kan
  lægges i ikonet, uden at overvågningen afsluttes.

- **Efterretningseditoren har nu en fast læringstilstand-kontakt.**
  Den står i trefferområdet og i menuen „Værktøjer“. Slukkes den,
  vises hverken ved gendannelse eller efter manuelle rettelser spørgsmål
  om at oprette egne regler. Maskuro husker valget for alle fremover
  åbnede dokumenter; selve tilbageførslen fungerer uændret.

### Rettet

- **Den store tillægsmodel kan igen indlæses.** Det offentlige
  lager afviste Pythons generelle standardkendetegn med 403. Modelhentninger
  bruger nu samme udpegede Maskuro-netvej som de øvrige
  egne tjenester; den knap 596 MB store fil og dens kontrolsum forbliver
  uændrede.

- **En maksimeret sammenligningslup bliver ikke længere hængende som en
  smal bjælke øverst ved dokning.** Før dokningen normaliseres dens frie
  vinduestilstand. En gemt maksimeret tilstand føres ved
  næste åbning ligeledes tilbage til en ændelig størrelse.

- **En samlet tilbageførsel henter nu virkelig alle valgte værdier tilbage
  i tabeller og andre tekstformater.** Ved anonymiserede pladsholdere
  som `[EMAIL]` skrev Maskuro hidtil værdierne efter hinanden. Så snart den
  første var erstattet, rykkede numrene på alle resterende fund frem, men
  den allerede beregnede plan pegede stadig på de gamle numre. Derfor kom
  kun en del af valget tilbage. Nu skrives alle valgte værdier af samme
  pladsholder samlet og med stabile fundnumre.
  Bliver et sted først entydigt gennem en anden tilbagehentet værdi,
  kontrollerer Maskuro det på ny i samme omgang – rækkefølgen af valget spiller
  dermed ikke længere nogen rolle.

- **„Fortryd erstatning“ udelader ikke længere valgte værdier i PDF'er.**
  Stod en pladsholder meget tæt bag et andet ord, eller hang der
  i originalen et komma direkte ved værdien, kunne placeringskontrollen fejlagtigt
  henregne nabo-ordet henholdsvis skilletegnet til værdien. Ved fælles
  tilbagehentning blev enkelte pladsholdere og trefferlinjer da stående. Kontrollen
  retter sig nu efter det faktiske ordstart og tager også højde
  for en afvigende sidedrejning mellem original og resultat.

- **Tilbagehentet PDF-tekst bevarer nu sin oprindelige størrelse.** Hidtil
  tjente den allerede mindre satte pladsholder som målestok; desuden gjaldt
  også for originalteksten den øvre grænse på 11 punkt, der egentlig var tænkt
  til pladsholdere. Nu overtages original-boksen og original-skriftstørrelsen fra
  kildefilen – både ved rammeværktøjet og ved tilbagehentning fra
  trefferpanelet.

### Forbedret

- **Kontrolhenvisningen navngiver nu restrisikoen tydeligere.** Den siger
  udtrykkeligt, at Maskuro kan overse data eller behandle oplysninger forkert,
  og opfordrer til fuld kontrol og om nødvendigt manuel
  rettelse før enhver offentliggørelse eller videregivelse. Det
  gælder også teksten fra udklipsholderen og er fuldt ud gennemført i alle 17
  oversættelser.

- **Kontrolloggen starter nu også inde i sine linjer uden
  brugernavn.** Loggen selv forbliver slået fra, indtil en virksomhed bevidst
  aktiverer den. Derefter står der uden yderligere virksomhedsforskrift hverken
  i en linje eller i navnet på en central månedsfil et brugernavn;
  dér tjener et ikke-gætteligt pseudonym, afledt udelukkende af den
  tilfældige lokale profilhemmelighed, til sikker
  adskillelse. Licensdialogen anbefaler ikke længere aktivering, forudsætter
  „Uden log“ og gør på forhånd opmærksom på samarbejdsudvalg,
  personalerepræsentation og databeskyttelse.

- **Erstat navngiver nu, hvad det erstatter.** Et markeret navn bliver til
  `[NAME_3]`, et sted bliver til `[ORT_1]`, et telefonnummer til `[TELEFON_2]` –
  i stedet for som hidtil alt til `[BEGRIFF_n]`. Arten genkendes ved
  klik; er den ikke entydig – et almindeligt ord, eller et navn
  *og* et sted i ét valg –, forbliver det ved det generelle begreb.
  En pladsholder, der påstår en art, som ikke passer, ville være
  værre end en, der slet ingen nævner.

- **Værktøjerne i efterretningsvinduet har nu en tast.**
  **S** sværter, **E** erstatter, **Z** henter originalen tilbage, **V**
  pixelerer. I tekstvisningen virker de straks på markeringen, i
  sidevisningen vælger de værktøjet. **Bogstaverne følger sproget**,
  som du betjener programmet på – engelsk B/R/O/P,
  italiensk O/S/R/P –, for en huskeregel hjælper kun på ens eget
  sprog. Tasten står på knappen.
  Hvem der lige nu skriver i søgefeltet, skriver fortsat bogstaver videre – der
  griber de ikke ind.

- **Programmet melder én gang om dagen, i hvilken tilstand det kører – uden
  nogen identifikation.** Dermed tæller vi, hvor mange installationer der bruges,
  og hvordan det fordeler sig på prøveperiode, gratistrin og licens. Ud
  går tilstand, operativsystem, version, kanal, land, sprog, miljø og
  genkendelsestrin – **intet om dine dokumenter og intet, som din
  computer kunne genkendes på**. To meldinger fra dig ser for os ud
  som meldinger fra to forskellige mennesker; et enkelt forløb kan ikke
  spores derfra. Hvad der præcist sendes, og hvordan det kan slås
  fra, står i databeskyttelsesteksten under punkt 5.

- **Skævt indlæste sider står nu selv rigtigt vendt.** Et
  ark, der er skannet skævt uden at det er noteret, genkender
  efterretningen på tekstforløbet og retter visningen op. Hvor det ikke kan lade sig gøre –
  ved en ren skanning uden læsbar tekst –, drejer to nye punkter i
  menuen „Vis“ manuelt (Ctrl+Shift+L og Ctrl+Shift+R). Drejet
  bliver kun visningen: Ved filen ændres der intet, og
  sværtning rammer fortsat præcis det sted, man klikker på.

- **Den lokale udgave fører nu sine licenser fuldstændigt og synligt
  med.** Byggeriet fastslår de faktisk medfølgende Python-pakker, lægger
  deres licenstekster med versionoversigt under `lizenzen` og afbryder ved
  et hul. Også Qt, Tesseract og ansigtsmodellen har deres nødvendige
  tekster; betingelserne for Maskuro selv følger med som licensaftale.

- **Man kan nu se, i hvilken pladsholder markøren står.** Hvem der
  klikker i en pladsholder, ser den lyse helt op – inklusive parenteser og
  nummer. Knappen „Hent valg tilbage“ virkede allerede før
  ved et blot klik; man kunne bare ikke se, hvilket mærke den
  ramte. Lyset bliver stående, selv når musen flyttes hen til knappen.

- **Musemarkøren viser nu, hvilket værktøj der er valgt.** Fire værktøjer
  deler den samme flade og den samme bevægelse; indtil nu så alle ens
  ud. Trådkors betyder sværtning, lukket hånd erstatning, åben hånd
  tilbagehentning.

- **Et forberedt Office-dokument afviser nu selv programmet.**
  En Word-, Excel- eller OpenDocument-fil kan medbringe instruktioner, der
  ved åbning henter en fremmed fil på din computer ind i sin tekst eller
  fylder arbejdshukommelsen op. Begge dele blev også hidtil afvist –
  men af det indbyggede XML-bibliotek, ikke af Maskuro. Nu
  afgør programmet det selv, uanset hvilken version af
  dette bibliotek der ligger i pakken. For almindelige dokumenter ændrer
  intet sig.

### Rettet

- **Trefferpanelet fjerner nu sværtede pladsholdere.** Blev fx
  `[NAME_1]` sværtet i efterretningsvinduet, blev dens værdilinje hidtil
  stående til højre, selvom der ikke længere fandtes et sådant sted i dokumentet.
  Linjen falder nu bort sammen med det sidste fund; forekommer samme
  pladsholder stadig et andet sted, bevares den.

- **Ved tilbagehentning på en drejet side bliver nabo-ordet nu
  stående.** Sværtningsbjælken rager bevidst en smule ud over
  teksten; allerede denne smalle kant kunne hidtil tage et tilstødende ord som
  „im“ med. Nu tæller kun en tydelig overlapning, ikke berøring ved
  kanten.

- **En anden erstatning i samme linje tog eftersætningen med.** Hvem der
  erstattede „Sachbearbeitung Quaxi Blubbo übernimmt“ to gange i træk,
  fik „Sachbearbeitung [ORT_1] [ORT_2]“ – ordet bagefter
  var uden varsel simpelthen væk. Årsagen var pladsholderen
  ved siden af: Resten af linjen begynder efter den første erstatning med et
  mellemrum, og søgningen efter dens tekststed greb nabo-parentesens
  lukkeparentes. Derefter var alt forskudt med ét tegn.
  Berørt var hver linje, hvor der blev erstattet eller sværtet to gange –
  også ved tilbagehentning ved siden af.

- **Erstat sværter ikke længere, når pladsholderen er for lang.** Var der
  ikke plads ved siden af ordet til `[BEGRIFF_2]`, blev området hidtil
  malet sort – og dermed kunne man heller ikke længere se, at der
  engang stod noget, endsige hente det tilbage. Nu skrives en
  kortere skrivemåde: `[BEGR_2]`, `[BE_2]`, i yderste konsekvens `[B_2]`.
  Løbenummeret bevares på hvert trin – ved det finder
  tilbagehentningen stedet igen. Kun hvor selv den korteste ikke
  passer ind, forbliver det ved bjælken.

- **Erstat lod teksten stå, hvis der allerede var sværtet i samme
  linje.** Hvem der i efterretningsvinduet hentede et navn fra originalen
  tilbage, derfra erstattede fornavnet (der var ikke plads – det blev
  en bjælke) og derefter erstattede efternavnet, fik pladsholderen
  lagt ind, men navnet **ikke fjernet**. Det blev kun opdaget ved
  eftersynets advarsel. Årsagen var linjen selv: Efter den første
  sværtning begynder dens rest med et mellemrum, og deri fandt
  søgningen efter tekststedet intet holdepunkt. Det ramte hver anden sværtning
  i samme linje.

- **En aktiveret udvidet genkendelse uden dens model falder nu i
  øjnene.** Afkrydsningen kunne være sat, mens modellen manglede – indstillingerne
  gælder for hver installation, men modellen ligger ved siden af
  programmet. Rensningen kørte da uden trinnet, uden et ord
  om det. Nu siger afkrydsningen, at modellen mangler, og resultatet
  bærer en advarsel. Dit engang trufne valg forbliver gemt:
  Så snart modellen er indlæst, virker det igen.

- **Ved anonymisering hentes nu det rigtige begreb tilbage.** Hvem der
  erstattede flere begreber manuelt og derefter hentede et af dem
  tilbage, fik altid den **første** – af „Schmidt“ blev „Müller“. Tilknytningen
  huskede kun én erstatning pr. pladsholder, og ved anonymisering
  bærer alle den samme pladsholder; det andet og hvert yderligere begreb
  faldt dermed bort. Nu får hver værdi sin egen linje – også i
  listen over erstatninger, som før var for kort.

- **I tabeller kan man nu også hente tilbage.** I en CSV eller
  personaleliste står pladsholderne lige ved siden af hinanden, kun adskilt
  af et semikolon. Indtil nu kunne programmet dér ikke fastslå,
  hvilken værdi der havde stået hvor, og afviste – ved
  `[NAME]` gik det, ved `[GEBURTSDATUM]` og `[TELEFON]` ikke. Nu
  splitter det linjen ved alle pladsholdere. Forbliver et sted virkelig
  flertydigt, afviser det fortsat: En forkert genindsat værdi
  ville være værre end et udeblevet svar.

- **Og afvisningen kan nu ses.** Den stod i afdæmpet grå nederst i
  vinduet, og sætningen var så lang, at den blev afskåret – det
  så ud, som om der slet intet skete. Sætningerne er forkortet, og
  linjen lyser i nogle sekunder i advarselsfarven.

- **En tilbageførsel holder nu også efter det næste indgreb.** Hvem der
  ved anonymisering hentede flere steder tilbage og derefter erstattede
  noget andet, fandt alle tilbagehentede steder erstattet igen og måtte
  begynde forfra. Årsagen var tilknytningen: Den beholdt værdien, og
  den automatiske afstemning for ensartede pladsholdere hentede den ved
  næste skrivning tilbage. Nu gælder: Det du henter tilbage, forbliver
  tilbagehentet – andre steder med samme værdi rører det ikke ved.

- **I tekst-, Word-, Excel- og e-mailfiler er ét klik nu virkelig nok
  i pladsholderen.** Meldingen om det stod allerede i den forrige version,
  men knappen „Hent valg tilbage“ forblev spærret, så længe intet var nøjagtigt
  markeret – man kom altså slet ikke til den vej, der selv ville have sat
  markeringen.

### Rettet

- **Kontrolloggen afslører ikke længere filnavnet.** Den fører filer
  bevidst som hashværdi i stedet for i klartekst, fordi et filnavn afslører
  klient og tvistemål. Denne hashværdi lod sig dog bekræfte ved
  gætning – en sti er ikke et tilfældigt tal. Nu indgår en tilfældig
  værdi for netop denne installation i beregningen: Tælling og skelnen i
  loggen virker fortsat, efterregning udefra ikke længere.

## 0.10.31-alpha.20260819 – 19. august 2026

### Forbedret

- **Også i tekst- og regnearksfiler lyser pladsholderen rødt op ved
  peget.** Hidtil fandtes den røde forhåndsvisning kun på en PDF-side. Nu
  viser begge visninger det samme: Det, der er rødt, rammer det næste
  træk – og et klik ind i det er nok til at hente det tilbage.

- **Et klik på et ord er nok – rektanglet sætter editoren selv.** I
  vinduet til efterretning måtte man hidtil trække et rektangel over hvert
  sted. Nu er et klik nok: Rammen lægger sig om ordet og forbliver
  håndterbar, kan altså trækkes videre eller flyttes. Ved peget med musen
  lyser ordet allerede rødt op, så man ser på forhånd, hvad klikket ville
  ramme. Hvor der ikke står noget ord, trækker man som hidtil et
  rektangel.

- **Man skal ikke længere sigte præcist med rektanglet.** Den, der trækker
  et rektangel over en pladsholder eller en sløring, mener altid hele
  stedet – aldrig kun halvdelen. Rammen vokser derfor selv til det hele,
  den berører: til hele pladsholderen, hele bjælken eller, på et
  indscannet ark, til hele det slørede areal. Mindre end det trukne
  rektangel bliver den aldrig.

- **Der sløres nu ordvist.** En ramme over halvdelen af et ord slørede
  hidtil kun halvdelen – og et halvt sløret navn er stadig et navn. Berørte
  ord falder nu helt; naboen forbliver urørt.

- **I tekst og regneark er et klik i pladsholderen nok.** „Hent
  markering tilbage" krævede hidtil, at man markerede pladsholderen med de
  firkantede parenteser præcist. Nu er det nok at sætte markøren ind;
  markeringen springer synligt til hele pladsholderen.

- **Belgien er kommet til som land.** Kan vælges i indstillingerne;
  genkendt bliver derefter belgiske telefonnumre, Rijksregisternummer (med
  kontrolciffer), moms-/virksomhedsnummer (med kontrolciffer), adresser på
  begge officielle sprog og postnummer med by. Hidtil blev belgiske
  telefonnumre stående, fordi landet slet ikke stod i kataloget.

- **Opdateringskanalen siger nu, hvor tidligt du får nyt – ikke hvor
  langt.** Den, der stod på „Testversion", fik slet ikke tilbudt en ny
  forhåndsvisning eller en ny stabil version og måtte skifte kanal manuelt
  for overhovedet at få det at vide. Nu tilbydes også alt, der er mere
  pålideligt: Testversion tager testversioner, forhåndsvisninger og stabile
  versioner, forhåndsvisning tager forhåndsvisninger og stabile. Omvendt
  aldrig – på forhåndsvisning tilbydes ingen testversion, selv om den er
  nyere.

- **I indstillingsvinduet står linjerne længere fra hinanden.** De fire
  sider brugte egne afstande i stedet for det raster, der gælder i resten
  af programmet; især på siden „Genkendelse" stod afkrydsningsfelterne
  derfor mærkbart for tæt.

### Rettet

- **Udfyldte PDF-formularer fremstår ikke længere tomme ved
  håndredigering.** Maskuro gør til det formål udelukkende den flygtige
  arbejdskopi til statiske sider: Indtastede værdier bliver synlige og kan
  virkelig sløres; udlæselige formularfelter forbliver ikke skjult i
  filen. Originalen forbliver interaktiv og uændret. Det gælder nu også
  dynamiske XFA-formularer: En XFA-egnet PDFium opbygger først værdier og
  sideskift, derefter opstår en ny PDF udelukkende af statiske billedsider.
  Slår XFA-opbygningen fejl, afvises filen sikkert i stedet for at åbnes
  tilsyneladende tom.

- **„Annuller" virker nu også under den mere præcise genkendelse.** Hidtil
  spærrede knappen sig ved klik, men kørslen regnede videre til den sidste
  blok – ved en lang fil er det minutter uden udvej, og knappen så
  imidlertid ud, som om den havde virket. Nu slutter kørslen ved den næste
  blok.

- **I CSV-filer bliver navne nu også fundet, når der ikke står et
  mellemrum foran dem.** I `P-1000;Brunnthaler, Elisabeth` klæber
  personalenummeret hen over semikolonet til navnet, og for genkendelsen
  var det ét eneste ord uden noget navn i sig – i personallister blev
  derfor hele navnet stående alt efter linje. Telefonnumre, formler og
  filens kolonneantal forbliver uberørt af dette.

- **Et navn, hvis for- og efternavn begge bærer en bindestreg, bliver nu
  genkendt.** „Marie-Luise Habsburg-Ott" blev stående midt i sætningen,
  mens „Dragan Mitrović" i samme sætning blev fundet – netop kombinationen
  af to koblede halvdele overså sprogmodellen. Koblede sagord som
  „Nord-Syd-forbindelse" eller „Software-udvikler" forbliver uberørt af
  dette.

## 0.10.30-beta.1 – 18. august 2026

### Forbedret

- **Skriftstørrelsen i tekstvisningen kan nu synligt indstilles.**
  Skyderen nederst til højre, der hidtil kun zoomede i sidevisningen,
  indstiller i efterretningsvinduet ved tekst- og Office-filer
  skriftstørrelsen (50–300 %) – ligesom „Forstør“/„Formindsk“ i menuen
  Vis. Ctrl+musehjul kunne det altid, men det vidste kun den, der
  havde prøvet det; nu virker skyder, visning og hjul sammen.

- **I det mørke udseende ligger der nu et hvidt ark på et mørkt
  arbejdsområde.** Hidtil var det omvendt: Omkring arket blev en
  lys flade stående, og selve teksten stod lys på mørk. Nu
  forbliver arket i begge udseender papirhvidt med sort
  skrift – ligesom en PDF-side, der jo heller ikke bliver mørk i mørk
  tilstand – og fladen omkring er mørk.

### Rettet

- **Efter en sværtning midt i en sætning går resten af sætningen ikke
  længere tabt.** Hvem der i efterretningsvinduet gik tre gange på
  samme sted – erstatte, sværte, så „Hent original tilbage“ –, fik
  sætningsbegyndelsen slettet: Af „Rückfragen richten Sie bitte an das
  Rechnungswesen.“ blev „bitte an das Rechnungswesen.“, uden advarsel.
  Berørt var ethvert sted, hvor der allerede engang var fjernet noget midt
  i en linje.

- **En startfejl river ikke længere afslutningen med sig.** Når opbygningen af
  hovedvinduet afbrydes, styrtede derefter også afslutningen via
  proceslinjeikonet ned – og denne anden fejl skjulte i fejlrapporten
  den egentlige årsag. Nu afslutter programmet sig nu også fra et
  halvt opbygget vindue rent, og de gemte indstillinger
  forbliver urørte.

- **„Før/efter“ springer ikke længere til dokumentets begyndelse.** Hvem der
  i efterretningsvinduet havde rullet nedad og skiftede til originalen for
  sammenligning, landede igen helt øverst – og måtte finde stedet
  igen manuelt. Visningen forbliver nu på samme linje,
  i begge retninger.

- **Ved sværtning blev det sidste bogstav stående på lige margen-linjer.**
  Når en tekstkommando tegner flere glyffer, end læsebiblioteket
  melder tegn for – det sluger gerne et mellemrum i lige margen –,
  forskød tilknytningen sig med ét, og af „Dr. Michael Handler aus
  Willendorf“ blev „[NAME] r aus f“: to bogstaver blevet stående
  midt i den rensede sætning (fundet i en ægte rådsprotokol).
  Tilknytningen kontrolleres nu mod kommandoens egen ordlyd,
  hvor denne er læsbar – der gættes ikke længere dér.

- **„Lerchenfelder Gürtel 43/12“ blev kun halvt fjernet.** Adresse-
  mønstrene kendte hverken Gürtel, Kai, Lände, Zeile, Markt eller
  Graben som gadegrundord, og husnummeret måtte ikke have
  skråstregsdele (43/12, hus/dør) – nummeret blev stående ved siden af
  pladsholderen. Begge dele er tilføjet; wienske og salzburgske adresser
  falder nu helt.

- **Gemte websider forbliver funktionsdygtige efter rensningen.** De
  adresser, som lazy loading gemmer i data-attributter (`data-lazy-src`,
  `data-lazy-srcset`), blev erstattet som links – på en ægte
  kommuneside seksten stykker – og billederne på siden indlæste
  derefter ikke længere. Webadresser bliver nu stående dér, ligesom i
  `src` og `href`; navne, mailadresser og telefonnumre i data-attributter
  erstattes fortsat.

- **Japanske og koreanske dokumenter blev kørt som kinesisk.** Sprog-
  genkendelsen kastede alle tre skriftsystemer i samme kurv, fandt i
  japansk tekst (uden mellemrum) og koreansk (med tilhæftede
  partikler) ingen funktionsord – og valgte så bare det første
  CJK-sprog i kataloget. En japansk rådsprotokol og en
  koreansk mødeprotokol blev dermed læst med den kinesiske model.
  Nu afgør skriftbilledet selv: Kana betyder japansk,
  hangul betyder koreansk.

- **Yderligere fejlgreb fra felttesten på ti yderligere sprog:**
  Embeder som „Primar“, „Gradonačelnik“, „Ordfører“, „Başkanı“ eller
  „Δήμαρχος“ gælder ikke længere som personnavne; tyrkiske
  feltbetegnelser („Adı“, „Soyadı“) og græske samtaleord
  („Ωραία“, „Βεβαίως“) falder ikke længere; beslutnings- og paragrafnumre
  med dato („323/25-6-2008“, „27 30.09.2024“) er ikke længere telefonnumre;
  og sætningsrester med punktum („10.An“, „T.U.EE“, „…pa“) erstattes ikke
  længere som webadresser.

### Nyt

- **Kontrolrapporter automatisk efter ønske.** Et flueben i indstillingerne
  (siden „Program“) lægger efter hver rensning selv et
  kontrolrapport-PDF – med tidsstempel i navnet, i en egen mappe,
  aldrig ved siden af resultatet. Efterfølgende kan et blad ikke oprettes;
  hvem der har brug for det til sagsakten, har det dermed altid. Standard er
  aflæggelsen slået fra.

- **Kontrolloggen kan nu slås til i programmet.** Ved
  indlæsning af en virksomhedslicens spørger Maskuro én gang, om loggen
  skal føres – et bevis bærer kun, hvis det kører fra begyndelsen.
  Dertil findes en kontakt i indstillingerne (siden
  „Program“, synlig med virksomhedslicens eller i prøveperioden); administrationens
  forskriftsfil gælder fortsat og kan tvinge værdien som hidtil.
  En egen loglinje „slået til“ fastholder, siden hvornår der føres – dermed
  er også begyndelsen af optagelsen dokumenteret og underskrevet. Standard
  forbliver loggen slået fra.

- **Nøgletals-klappen viser, hvad KI-trinnet har gjort.** En ny
  linje angiver, hvor mange usikre fund modellen har vurderet, beholdt
  og forkastet, og hvor mange den yderligere har fundet – hidtil var
  dens arbejde usynligt, hvis man ikke klikkede på hver værdi i
  efterretningseditoren. Kun tal, aldrig værdier eller begrundelser; uden
  KI-arbejde vises linjen ikke.

- **Tilbagehentning virker nu også i e-mails og HTML-sider.** I `.eml`,
  `.msg` og gemte websider kunne en pladsholder hidtil ikke
  hentes tilbage – applikationen sagde det ærligt, men netop e-mailen er
  det format med flest personlige oplysninger. Nu bærer tilbageførslen
  dér på samme måde: fra trefferpanelet, med markeret valg og også ved
  anonymiserede pladsholdere. E-mailens usynlige HTML-gren (det,
  som Outlook virkelig viser) trækkes med, så visning og
  besked siger det samme.

- **Trefferpanelet henter også anonymiserede værdier tilbage – pr. værdi.**
  „Fortryd erstatning“ var hidtil spærret ved anonymiserede filer,
  fordi „[NAME]“ står for alle navne på én gang. Nu slår tilbageførslen
  op i originalen, hvilket sted der hører til hvilken værdi – i PDF'en ved
  koordinaterne for fundet, i tekstvisningen via sammenligning med
  originalen – og henter netop de steder for den valgte værdi tilbage. De
  øvrige værdiers linjer bliver stående.

- **Også anonymiserede pladsholdere kan hentes tilbage enkeltvis.** Ved
  anonymisering hedder alle oplysninger af én art det samme – „[NAME]“ står
  for hver person, og hidtil hed det derfor: at hente enkeltvis tilbage kan ikke lade sig gøre.
  Nu slås der op i originalen, som alligevel ligger ved siden af resultatet:
  I tekstvisningen markeres pladsholderen, og „Hent valg
  tilbage“ vælges – tilbage kommer netop dette sted med netop dets
  værdi. Kan værdien ikke aflæses entydigt fra originalen,
  siger applikationen det i stedet for at gætte. En tilknytningsfil opstår
  fortsat ikke ved dette.

- **Efterretningsvinduet åbner sig nu selv efter rensningen.**
  Intet værktøj finder alt – derfor hører det prøvende blik på resultatet
  til normaltilfældet, ikke til et ekstra klik. Hvem der ikke ønsker det,
  slår det fra i indstillingerne under „Genkendelse“ („Vis resultat
  bagefter i efterretningsvinduet“).

### Forbedret

- **Landevalget står nu på „automatisk“.** Hidtil gjaldt fra fabrikken
  brugerfladens sprogområde – på en tysk computer blev altså også
  nederlandske eller franske dokumenter kun renset med DACH-genkenderne,
  og en adresse som „Universiteitslaan 1“ blev stående
  (fundet i ægte, offentlige rådsprotokoller). Nu retter
  landevalget sig efter dokumentets sprog; hvem der i indstillingerne
  har truffet et fast valg, beholder det.

- **Færre falsk sværtede.** En række fejlgreb, målt på
  kontrolkorpusset og på ægte mødeprotokoller på seks sprog, falder
  bort: Firmanavne med selskabsform („Musterfirma GmbH“) gælder ikke
  længere som person eller sted, men som organisation; hilsenformler og
  nøgne tiltaler („Saygılarımızla“, „Buenas tardes“, et alenestående „Frau“)
  er ikke længere navne; embeder („Bürgermeister“, „Sindaco“, „Alcalde“)
  bliver stående; lov- og beslutningsnumre („39/2015“) og beløb
  med tusindepunktum („330.000“) er ikke længere telefonnumre; sætningsbegyndelser
  som „Envíame“ eller „Estarei“ falder ikke længere som navn; et fund
  hen over en tom linje tæller ikke længere som navn. Faktura-
  nummeret på en faktura bevares som belægangivelse –
  kundenummer og sagsnummer falder fortsat.

- **Før indlæsning af KI-modellen står nu, hvad den er god til.** Nedlaste-
  dialogen nævner modellens opgaver – vurdere grænsetilfælde,
  finde yderligere navne, foreslå regler og profiler –
  og siger åbent, at det ikke er en chat-assistent. FAQ'en besvarer
  samme spørgsmål udførligt („Hvad kan KI-trinnet – og hvad kan det ikke?“),
  i alle sprogudgaver.

### Rettet

- **Kontrolrapport-PDF'er fra kommandolinjen kan nu gennemsøges.**
  Under Windows startede den hovedløse PDF-vej uden en eneste skrifttype –
  hvert tegn blev tegnet som erstatningsboks, og bladet bar
  ingen læsbar tekst: Hvem der ville søge eller kopiere noget ud
  derfra, fandt intet. Nu indlæser rapporten i det tilfælde systemets
  skrifttyper; teksten er indlejret og læsbar. Rapporter fra
  vinduet var aldrig berørt.

- **„Hent original tilbage“ over flere linjer af en skanning lod sorte
  striber blive stående mellem linjerne.** På en side omdannet til et
  billede ryddede rammen kun selve linjebåndene; resterne af
  den tidligere sværtning blev stående i mellemrummene. Nu deler
  den trukne ramme sig fuldstændigt op på linjerne.

- **En anden ramme over en pladsholder lod en rød rest blive stående.**
  Pladsholderen er næsten altid bredere end det ord, den repræsenterer; hvem der
  derefter sværtede over samme sted, ramte kun dens begyndelse – tilbage
  blev et fragment som „RIFF_1]“ midt i sætningen, og tilbageførslen
  satte derefter originalteksten ind på dets sted i stedet for ordets.
  En afskåret pladsholder falder nu altid helt bort.

- **På en drejet side slettede sværtning over en pladsholder en
  uvedkommende sætning.** Den efterfølgende tegnede pladsholder blev
  ved fjernelsen forvekslet med teksten foran: Den selv blev stående, advarslen
  „står stadig i dokumentet“ kom – og et andet sted på
  siden forsvandt uden erstatning en sætning, der ikke havde noget med
  rammen at gøre. En pladsholder genfindes nu via sin ordlyd;
  kæden „erstatte, sværte, hente tilbage“ går dermed op også på tværdrejede
  sider.

- **Håndbogen anbefalede i ti sprog stadig `python3-tk`.** I
  fejlfindingen stod dér, at tkinter måske manglede under Linux – et
  råd fra tiden før Qt-brugerfladen, som ikke længere hjælper nogen.
  Nu står i alle udgaver samme afsnit som på tysk: Det er
  systembibliotekerne, Qt har brug for til visningen, der mangler.

- **Håndbogens licenskapitel stod i alle seksten oversættelser
  på et forældet stadie.** På ti sprog kunne man dér stadig læse, at Windows Server
  krævede en virksomhedslicens med serveradgang, og at der ikke fandtes prøveperiode
  og gratistrin dér – siden en plads tæller et menneske og ikke en
  maskine, er begge dele forkerte. Der manglede desuden overalt oplysningerne
  om, hvornår en belagt plads bliver ledig igen, at licensen
  regelmæssigt bekræfter sig selv og hvad der overføres derved, og
  frigivelsen uden internet stod kun som kortfattet version uden de tre trin og uden
  bemærkningen om, at computeren derefter arbejder et år uden
  forbindelse.

- **Syv afsnit om efterretningen manglede på ti sprog.** Hvem der
  læste hjælpen på dansk, finsk, fransk, italiensk, nederlandsk,
  norsk, polsk, portugisisk, svensk eller spansk, fandt hverken
  sidevisningen for Office-filer eller „Sværte manuelt“ eller
  hele afsnittet om, hvordan programmet lærer af en rettelse –
  inklusive tabellen med de tre trin. I „Hvad genkendes“ manglede
  de samme ti udgaver vejen via betegnelsen i dokumentet.

- **Med indlæst licens startede programmet ikke mere.** I stedet for
  vinduet kom „Programmet kunne ikke startes“ – og det ved
  enhver licens, uanset hvilken. Årsagen var linjen i licensvisningen,
  der advarer kort før prøveperiodens udløb; den tilgik noget, der
  ikke var til rådighed dér. Uden licens – i prøveperioden og i
  gratistrinnet – opstod fejlen ikke, derfor er den først nu
  blevet opdaget.

- **I formularen bliver feltnavnene stående.** „Geburtsdatum“ og
  „Anschrift“ forsvandt sammen med deres værdi: Pladsholderen stod lille og
  rødt på stedet for *feltnavnet*, feltet nedenunder forblev tomt. Felt-
  navnet hører ikke til dataene – det bliver nu stående, og pladsholderen
  står dér, hvor værdien stod.

- **Fremmedsprogede dokumenttitler opfattes ikke længere som navne.**
  Over en italiensk formular stod „FATTURA“, over en spansk
  „PERMISO PARENTAL“ – begge blev erstattet. Listen over
  dokumentord kendte kun de tyske modstykker.

- **Fra en faktura forsvinder ingen post længere.** „Materialaufschlag
  1  84,00“ blev opfattet som en adresse og erstattet med en steds-pladsholder
  – bilaget manglede derefter en linje. En linje, der ender med et
  beløb, er en post og ikke en adresse; ægte adresser
  („Hauptstraße 1  120,00“) forbliver urørte.

### Ændret

- **„Overvåg mappe …“ og kommandolinjen er indtil videre ikke
  mere til stede.** Begge veje er bygget og kører, men ingen af dem er
  afprøvet i praksis: Mappeovervågningen har aldrig set et
  Windows-gennemløb, og kommandolinjen giver et script to dusin
  kontakter i hånden, som aldrig har kørt hos nogen bruger. Det, der
  uovervåget ændrer dokumenter, skal ikke gøre det uprøvet –
  derfor er de trukket tilbage, indtil gennemløbet er efterhentet. Menupunktet
  mangler, og `--wache` står ikke længere i `maskuro --help`.

- **Åbent forbliver, hvad der kun læser, og hvad der alligevel er nødvendigt.** Søge-
  gennemløbet (`--suchlauf`) og efterkontrollen (`--nachpruefen`) fungerer
  fortsat på kommandolinjen – de ændrer ingen fil. Ligeledes starten
  via Stifinder, kontekstmenuen, udklipsholderen og vinduet;
  det ændrer sig ikke.

- **„Hent fra scanner“ har nu sit eget kapitel i håndbogen.** Det
  stod hidtil for enden af „Overvåg mappe“. På Mac'en lød rådet
  dér, at lade en mappe overvåge; nu lyder det, at trække de
  indlæste sider ind i vinduet.

### Rettet

- **„Hent original tilbage“ over flere linjer ødelagde opdelingen.**
  En ramme over en pladsholder, en uændret jobtitel og en
  anden erstatning lagde hele området ind som **én** linje –
  af tre linjer blev der én, og det, der ikke længere passede ind, blev til
  en bjælke. Nu hentes hver linje tilbage for sig.

- **Og uændret tekst forbliver urørt derved.** Hvem der trækker over en
  erstatning *og* almindelig tekst, får kun erstatningen
  tilbage; resten røres ikke ved. Også den sidste rest af den gamle
  pladsholder forsvinder derved – tidligere blev dens lukkeparentes
  stående midt i sætningen.

- **Ved erstatning bliver der ikke længere rester af den gamle tekst stående.** I
  en fed overskrift stod der derefter „1. R[BEGRIFF_2]ige [BEGRIFF_1] …
  che“ – pladsholderen sad dér, men stavelser af originalen ved siden af.
  Nu ryddes det område, du indrammer, ikke kun boksene om
  ordene deri.

- **En anonym pladsholder hentes ikke længere tilbage.** Ved
  anonymisering bærer hvert navn samme `[NAME]`. Tilbageførslen tog
  den førstebedste post og skrev den ind på hvert fund – af „Georg
  Aigner“ blev „Anna Musterfrau“, altså et forkert navn i dokumentet.
  Nu står der, at det ikke længere kan siges, hvilken oplysning der var
  ment; dokumentet forbliver urørt.

### Nyt

- **„Hent original tilbage“ virker nu også på en rasteret side.**
  Blev en side omdannet til et billede, kom hidtil en afvisning: Den
  tilbagehentede tekst ville komme under sidebilledet. Nu ryddes stedet
  i billedet, og teksten skrives på det – som en pladsholder på
  en skanning. Indholdet kommer derved fra originalfilen, og den er
  ikke rasteret.

- **„Hent valg tilbage“ står nu som sin egen knap.** Det gik allerede
  før, men kun hvis man tilfældigvis markerede en pladsholder og
  trykkede „Erstat valg“ – en funktion, man kun finder ved tilfælde,
  findes ikke for brugeren.

### Ændret

- **I ren tekst, CSV og Outlook-beskeder findes „Sværte valg“
  ikke længere.** Disse formater kan ikke bære en bjælke; knappen
  satte dér en pladsholder og sagde det også – men en knap, der
  gør noget andet end den hedder, hører ikke hjemme dér.

- **Et værktøj siger nu, når det intet kan udrette på dette
  sted.** En pladsholder kan ikke erstattes én gang til, over en
  sværtning sættes ingen pladsholder, og hvor originalen allerede
  står, er der intet at hente tilbage. Hidtil gjorde disse handlinger noget, der
  så ud som en virkning, men ingen var det.

## 0.10.29-alpha.20260817 – 17. august 2026

### Rettet

- **I vinduet til efterretning virker nu hver ramme, man trækker.** Den,
  der arbejdede to gange på samme sted – først erstattede, så slørede, så
  hentede originalen tilbage –, dennes andet og tredje træk forsvandt
  lydløst: Den stadig håndterbare ramme fra det forrige træk fangede det.
  Det samme gjaldt ved værktøjsskift, hvor endda det gamle værktøj
  lydløst blev ved med at virke.
- **En for smalt trukket ramme siger, at den er for smal.** Hidtil lyste
  forhåndsvisningen et ord rødt op, og ved slip skete der lydløst intet.

- **Outlook-meddelelser kan endelig efterrettes.** En `.msg` viste i
  vinduet til efterretning „Dette format kan ikke vises her" – den var det
  eneste understøttede format uden nogen vej til manuel efterbehandling.
  Nu står afsender, modtager, emne og meddelelsestekst benævnt i visningen
  og kan markeres og erstattes som i ethvert andet tekstformat.

- **„Erstat markering" bliver i en e-mail ved markeringen.** Den, der
  markerede et navn i brødteksten, mistede derved også afsender og
  modtager fra kopfelterne, og meddelelsen nævnte en anden pladsholder end
  den, der stod i teksten. Nu erstattes den markerede værdi overalt – også
  i afsenderen, hvis den står der – og ellers røres intet.

- **En ramme over flere linjer ødelægger ikke længere teksten.** Hidtil
  opstod én eneste pladsholder på ét sted: Af det afskårne ord blev en
  rest hængende, og fra den anden linje forsvandt teksten uden erstatning
  – ingen pladsholder, ingen bjælke, kun et hul. Nu får hver linje sin
  egen pladsholder med den værdi, der virkelig stod der.

- **„Hent original tilbage" virker nu også efter en sløring.** Vinduet
  meldte succes, og teksten kom aldrig tilbage: Den sorte bjælke talte som
  en forhindring, så der ikke længere var plads til den tilbagehentede
  tekst. Bjælken viger nu, og den tilbagehentede tekst står sort som
  almindelig tekst – ikke rød som en pladsholder.

- **„Hent original tilbage" på et urørt sted gør ikke længere noget.**
  Den, der trak rammen over tekst, hvor slet intet var ændret, fik teksten
  fjernet og genindsat mindre og forskudt – der blev meldt succes. Nu står
  der, at der ikke er noget at hente tilbage.

### Nyt

- **Der kan nu også sløres i Word, Excel, PowerPoint, OpenDocument og
  tekst.** Hidtil fandtes der kun „Erstat markering"; en bjælke var
  forbeholdt PDF-visningen, uden at der var nogen grund til det. Hvor en
  bjælke ikke kan vises – i ren tekst og i en Outlook-meddelelse – erstattes
  værdien som hidtil med en pladsholder, og det står også sådan i
  meddelelsen.

- **At markere en pladsholder henter den tilbage.** I tekstvisningen
  (Word, Excel, PowerPoint, OpenDocument, tekst) er det nu nok at markere
  pladsholderen og trykke „Erstat markering": Den oprindelige værdi kommer
  tilbage. Hidtil henviste vinduet i den forbindelse til fundpanelet.

- **Talere i et mødereferat genkendes nu også, når deres navn samtidig er
  et almindeligt ord.** „Gruber: Godkendelsen sker i næste uge." blev
  erstattet, „Bauer: Jeg er enig." blev stående – efternavnet ligner for
  genkendelsen et navneord. Mærkelinjer af samme byggeform forbliver
  urørte: Af „Bemærk: Anlægget skal slukkes." bliver der intet navn.

- **„Du bruger den nyeste version" blev også sagt, når det slet ikke kunne
  undersøges.** Afviser opdateringsserveren forespørgslen – fordi der kom
  for mange forespørgsler fra samme internetadresse, eller fordi den selv
  lige er forstyrret – så stod programmet stille på sin gamle version og
  påstod, det var den nyeste. Netop det skete den 17. august på en Mac:
  0.10.25 blev liggende, mens 0.10.28 havde ligget klar i timevis.

  Nu siger vinduet, hvad der er galt, nævner klokkeslættet for næste
  eftersyn – og gør udtrykkeligt opmærksom på, at det **ikke** står fast,
  om ens egen version er den nyeste.

  Som regel ligger det ikke hos ens egen computer: Ved mange forbindelser
  deler talrige kunder samme internetadresse, og serveren tæller dem
  sammen. Derfor søger Maskuro i dette tilfælde versionslisten via en
  **anden vej** og finder for det meste alligevel nye versioner. Bliver
  det ved afvisningen, lades serveren i fred indtil det nævnte
  klokkeslæt – også selvom man trykker knappen igen; at blive ved
  forlænger kun spærringen.

- **Mængdeangivelser opfattes ikke længere som stednavne.** I en
  tjenestekontrakt forsvandt „Fire-dages-uge" bag en stedspladsholder –
  midt i kontraktens genstand. Sådanne ordforbindelser af tal og
  bindestreg („Tre-punkts-plan", „24-timers-vagt") bliver nu stående.
  Adresser er undtaget fra dette: En „To-brødre-vej" erstattes fortsat.

## 0.10.28-alpha.20260817 – 17. august 2026

### Ændret

- **Licenspladser tælles nu virkelig.** Hidtil meldte ingen arbejdsplads sig
  nogensinde til licenstjenesten – en tipladslicens kørte på vilkårligt
  mange computere, uden at nogen fik det at vide. Nyt: Den computer, der
  starter programmet, tager en plads; en plads bliver efter **syv dage
  uden opstart** af sig selv fri igen, så en defekt enhed eller en
  fratrådt medarbejder ikke blokerer noget permanent.

  Et lille overskridelse vises hermed **kun og spærres ikke**: Op til ti
  procent over det købte antal fortsætter alle med at arbejde – den nye
  bærbare ved siden af den stadig tilmeldte gamle skal ikke være en sag for
  hotlinen. Den, der kommer til derudover, falder tilbage til gratisniveauet
  og får det at vide; de computere, der var der først, mærker intet til
  det.

- **En købt licens bekræfter sig regelmæssigt.** Lykkes det ikke i **30
  dage**, gælder gratisniveauet igen, indtil det lykkes igen. Der slås
  intet fra, og fra en uge før står henvisningen i vinduet. Så snart
  computeren igen får internetadgang, ordner det sig af sig selv.
  Prøveperiode og gratisniveau melder fortsat overhovedet intet – den, der
  aldrig køber, ringer aldrig.

- **„Aktiver uden internet" virker endelig.** Aktiveringen blev hidtil
  ganske vist kontrolleret og gemt, men derefter læst af ingen længere –
  den ændrede intet ved rettighederne. Nu er den udvejen for computere uden
  netadgang: Den varer **et år**, derefter henter man sig en ny med en
  frisk anmodningskode. En enhed med internet skal man bruge til det én
  gang om året – computeren selv forbliver permanent offline.

- **Aktiveringen går nu også fra kundekontoen** – under „Mine licenser" på
  hjemmesiden. Der står desuden, hvilke computere der hænger på din
  licens, og hvornår deres pladser bliver fri igen; det var hidtil ikke at
  se noget sted. Siden uden login forbliver for alle, der ikke har
  shop-adgang – den kræver til gengæld yderligere e-mailadressen fra
  bestillingen, så licensnøglen alene ikke er nok.

- **Og i vinduet står der nu, hvor anmodningskoden skal hen.** Papirvejen
  sagde „indtast på en enhed med internetforbindelse" og nævnte ingen
  adresse; aktiveringssiden har eksisteret længe, men den var ikke linket
  fra noget sted. Nu står **maskuro.com/lizenz-freischalten** i dialogen,
  i håndbogen og i FAQ'en – og på hjemmesiden under licensnøglen.

- **Knappen „Aktiver uden internet …" forbliver synlig**, også når licensen
  netop ikke gælder. Før forsvandt den sammen med den – altså netop når man
  har brug for den.

- **„Alle pladser optaget" siger nu sandheden.** Henvisningen endte med
  „Programmet fortsætter uændret med at arbejde"; det er ikke længere
  sandt, når der ikke er tildelt nogen plads. Der står nu, at gratisniveauet
  gælder indtil videre.

### Nyt

- **Ved tilkobling af udklipsholder-rensning står der nu med, at der skal
  ses efter.** Meddelelsen nævner siden den samme sætning, som også står
  ved resultatet af en fil: Maskuro genkender ikke i alle tilfælde alle
  personoplysninger.

  Her vejer den tungere end andre steder. Ved en fil ser man resultatet,
  før man giver det videre. Ved udklipsholderen ikke – man kopierer,
  indsætter, og den rensede tekst står allerede i mailvinduet. Meddelelsen
  siger derfor udtrykkeligt at gennemgå den **indsatte** tekst.

  Den kommer ved tilkoblingen, ikke ved hver kopiering: Det, der ville
  fremkomme halvtreds gange om dagen, læser ingen efter tredje gang
  længere.

- **„Kopiér alle" under listen – og „Fjern alle" rykker væk.** Den nye
  knap lægger samtlige færdige resultater på én gang på udklipsholderen,
  til vedhæftning på en mail eller indsættelse i et andet program. Hidtil
  kunne det kun ske via menuen og der kun for de **markerede** linjer – den,
  der mente alle, måtte først trykke Ctrl+A.

  Samtidig er knapperækken nyordnet: Til venstre står det, der tilføjer
  noget, til højre bag et mellemrum det, der fjerner noget. „Fjern alle"
  stod hidtil umiddelbart ved siden af „Tilføj …", og et fejlgreb kostede
  hele listen. Samme regel gælder allerede siden 13. august ved hver
  færdig linje.

- **Arbejdspladser uden internet får nu deres sprogmodeller fra huset.**
  Rensning fungerede der altid allerede uden forbindelse – efterindlæsning
  af en sprogmodel ikke, og en model vejer flere hundrede megabyte.

  Administrationen samler filerne én gang på en computer med forbindelse
  og lægger dem på en deling, i udrulningen eller på et USB-stik. Stedet
  angives centralt (feltet `modellquelle` i `vorgaben.json` eller
  miljøvariablen `MASKURO_MODELLQUELLE`). Fra da af betjener hver
  efterindlæsning sig først der – sprogmodeller, den japanske ordbog og
  høj-niveauet – og går kun ud på nettet, hvis en fil mangler.

  Kontrolsummerne gælder uændret. En fildeling i huset er ofte lettere at
  udgive sig for end en udgivelse på nettet; den skal ikke blive den mere
  bekvemme vej til en underskudt model.

  Hvordan en sådan beholdning opstår, og hvordan licens og aktivering
  fungerer uden internet, står i `OFFLINE.md`.

- **„Hent original tilbage" – en ramme henter tilbage, hvad der blev
  fjernet for meget.** I vinduet til efterretning findes et nyt værktøj:
  Træk rammen over stedet, og teksten står der igen, som den stod i
  originalen.

  Det lukker det hul, som fundpanelet lod stå åbent. Der kunne en
  erstatning kun fortrydes, hvis dens pladsholder var entydig – altså ikke
  ved anonymisering, hvor „[NAVN]" står ved enhver angivelse af denne art,
  og slet ikke ved slørede steder, hvor ingen pladsholder bliver tilbage.
  Netop dér ophober fejlgrebene sig: „Bruger", „Inventarnummer",
  „Underskrift" holdes gerne for navne.

  Rammen behøver ikke pladsholderen: **Stedet** kommer fra rektanglet,
  **indholdet** fra originalfilen – den samme, som før/efter-omskifteren
  viser. Anonymiseret eller pseudonymiseret spiller dermed ikke længere
  nogen rolle.

  Den tilbagehentede tekst står sort, ikke rød: Den er igen klartekst og
  ingen pladsholder. Fra fundlisten forsvinder en post først, når dens
  pladsholder **ingen steder** længere står i dokumentet – blev den samme
  værdi erstattet flere steder, forbliver den for de øvrige.

  På en side, der er omdannet til et billede, afviser værktøjet og
  forklarer hvorfor: Den tilbagehentede tekst ville komme til at ligge
  under sidebilledet og ville ikke være til at se.

### Rettet

- **Ved sammenklapning af „Detaljer" og „Nøgletal" blev billedrester
  stående på skærmen.** Sammenklappet skubbede en del af indholdet sig ind
  under vinduets nederste kant og blev liggende der oven på baggrunden,
  indtil noget andet blev tegnet ovenpå.

  Begge områder har en minimumshøjde, så de er brugbart store, når de er
  åbne. Bevægelsen ved sammenklapning satte imidlertid kun maksimumshøjden
  ned – og under sin minimumshøjde krymper et område ikke. Indholdet
  forblev altså 200 punkter højt, mens vinduet allerede trak sig sammen
  til 24; forskellen stod under kanten. Nu viger minimumshøjden i
  bevægelsens varighed og kommer tilbage bagefter.

- **Vinduet blev mindre og mindre ved gentagen op- og sammenklapning.**
  Ved udklapning vokser det højst til 92 % af skærmhøjden; er pladsen
  knap, vokser det altså mindre end nødvendigt. Ved sammenklapning trak det
  alligevel det fulde beløb fra igen. Nu gives netop det tilbage, som
  udklapningen kostede.

- **En rest af en sløret angivelse kunne stå synlig tilbage.** I et CV
  forblev af „*30.12.1991" tegnene „*30.1" læselige i resultatet – altså
  dag og begyndelsen af måneden for fødselsdatoen. Programmet havde endda
  bemærket resten og derfor omdannet siden til et billede; netop det gjorde
  det værre, for dermed var resten ganske vist ikke længere søgbar, men
  fortsat læselig – og ikke længere til at rette.

  Årsagen lå mellem to kontroller. Den skarpeste af de to ser efter, om
  der i fladen af en fjernet angivelse stadig står noget, der ikke hører
  hjemme der; den melder sit fund som en tegnmængde, fordi læserækkefølgen
  forskydes ved erstatning. Reservevejen, der overmaler sådanne steder
  før omdannelsen, søgte denne tegnmængde som tekst på siden – og fandt den
  aldrig. Der blev derfor intet overmalet. Stedet var kendt hele tiden og
  føres nu videre i stedet for at blive søgt på ny.

  Berørt var hver side, hvis rest udelukkende blev fundet af denne
  kontrol – uafhængigt af filtype og sprog.

- **På en tværvendt indscannet original fandt tekstgenkendelsen intet.**
  Den, der lægger et ark sidelæns i indtrækket, får en fil, hvori skriften
  står drejet 90 grader. Hidtil læste Maskuro **ikke en eneste** angivelse
  deri – og filen så derefter ubemærkelsesværdig ud: der blev intet fundet,
  altså blev intet meldt, og adressen stod fortsat læselig i billedet. Nu
  retter tekstgenkendelsen selv siden op; på kontrolbilledet falder igen
  alle angivelser.

  To grænser åbent nævnt: Et ark, der står **på hovedet** (180 grader),
  læser den fortsat ikke, og ved en meget dårlig scanning hjælper
  oprejsningen ikke – dér er for lidt læseligt til overhovedet at
  bestemme retningen. Hvert billede kræver til dette omkring en femtedel
  længere tid.

### Ændret

- **„Installer automatisk" hedder nu, hvad det gør.** Fluebenet i
  indstillingerne lovede mere, end det holdt: Det henter den nye version
  af sig selv og starter installationen – den forløber imidlertid
  **synligt** og vil bekræftes, under Windows sammen med en forespørgsel
  fra brugerkontokontrollen. Den, der læste „automatisk", regnede med en
  computer, der opdaterer sig selv i løbet af natten, og stod om morgenen
  foran installationsguiden. Fluebenet hedder nu „Hent opdateringer
  automatisk og start installationen", med en sætning nedenunder om, hvad
  det betyder. Ved adfærden ændres intet – at Maskuro ikke udskiftes
  ubemærket, er tilsigtet og forbliver sådan.

## 0.10.27-alpha.20260817 – 17. august 2026

### Nyt

- **Nyt: `--ersetzen` til integration med et advokatkontor-system.**
  Resultatet træder i stedet for kildefilen i stedet for at blive oprettet
  ved siden af. Dermed fungerer ud- og indtjekning fra et sagsstyringssystem
  („Åbn og rediger" i e-akten) uden nogen grænseflade: Systemet udleverer
  filen og får den rensede fil tilbage på samme sted.

  **Denne kontakt ophæver det første grundprincip**, og derfor findes den
  kun i kommandolinjen – ikke i vinduet – og kun hvis Deres administration
  frigiver den (posten `ersetzen` i standardfilen). Uden frigivelse
  afbrydes kaldet og siger hvorfor; at stiltiende oprette en anden fil ville
  være den værre fejl, for så ville den uændrede blive tjekket ind igen.

  Der skrives først en nabofil; først når den er færdig, træder den i
  stedet for kilden. Et afbrud eller en fejl efterlader dermed kilden
  **byte for byte uændret** og efterlader intet fragment. I kontrolloggen
  står erstatningen som et eget felt – en kontrollant skal vide, at den
  urensede udgave ikke længere ligger her.

- **Håndbogen forklarer nu Windows-advarslen ved første start.** Nyt første
  afsnit „Windows advarer ved første start – hvad skal man gøre", med to
  billeder og tre trin: „Flere oplysninger" er et lille link, ikke en knap –
  det er netop det, de fleste hænger fast i –, derefter „Kør alligevel".

  At der står „Ukendt udgiver" der, er hele budskabet i advarslen: Pakkerne
  leveres for øjeblikket uden certifikat. Vi mener, det er mere rigtigt at
  forklare det end at fortie det.

- **Tilbagevejen bemærker nu, når tekst og tildeling ikke hører sammen.**
  Den, der indsatte svaret i en anden sag, fik hidtil fremmede navne i den
  rigtige tekst – ingen fejl, ingen meddelelse, bare forkert. Maskuro
  husker nu, hvilke pladsholdere det seneste kørsel overhovedet oprettede,
  og melder hver eneste, som ikke hører til. Stammer ingen af dem fra det
  seneste kørsel, indsættes intet, og vinduet siger hvorfor – i stedet for
  som hidtil at antage en udløbet frist.

  **En grænse består fortsat, og den står også i håndbogen:** Pladsholdere
  nummereres pr. kørsel, det første navn hedder altså i hvert dokument
  `[NAME_1]`. Indeholder den fremmede tekst kun sådanne pladsholdere, kan
  forvekslingen ikke opdages.

- **PDF kan nu udskrives i sort-hvid.** Et flueben ved driftstilstanden
  omdanner hver side til et sort-hvidt billede – med et usynligt tekstlag
  under, altså fortsat læsbar og søgbar. Til afsendelse via beA og
  lignende veje med faste størrelsesgrænser: over vores målekorpus i
  gennemsnit **68 % mindre** (kommandolinje: `--monochrom`).

  **Hvor meget det giver, afhænger af dokumentet** – og det står også ved
  fluebenet: Scannet og billedholdigt materiale krymper stærkt, et slankt
  tekstdokument uden indlejrede skrifttyper kan endda blive større. Prøv
  det på en fil, før De slår det til for en bunke.

  Prisen: Hver side genberegnes – ved tusind sider tager det minutter. Og
  billeder mister alt mellem sort og hvidt; for tekst er det ligegyldigt,
  for et fotografi ikke.

- **Trefflisten i vinduet Efterbehandling tæller nu med.** Over listen står
  „5 træf", og så snart De filtrerer, „1 af 5 træf". Det er forskellen
  mellem „jeg har filtreret" og „der er fem, og jeg har set dem alle" –
  det håndgreb, man bruger til at kontrollere, om et navn virkelig er
  erstattet overalt.

- **Kontrolloggen kan nu gennemsøges og filtreres.** Visningen under „Fil →
  Kontrollog" havde hidtil kun en tabel og ellers intet – ved en måned med
  tre tusind kørsler kunne man se, at meget var sket, men ikke hvad.

  Nye er et **søgefelt**, **tre filtre** (metode, resultat, art) og
  **bladring**, dertil tre kolonner, der ikke fandtes før: **Metode**
  (sortlagt eller erstattet), **Konfidens** og **Varighed**. Over listen
  står, hvor meget der lige nu vises, og hvor meget filteret skjuler.

  „Gem som CSV …" udgiver nu **det, der står** – den, der har filtreret,
  får det filtrerede, og meddelelsen nævner antallet.

  En streg ved konfidens eller varighed betyder, at der ikke er målt noget
  for denne linje – f.eks. fordi den er ældre end denne funktion. Disse
  værdier beregnes **ikke** efterfølgende. Et filter over bruger findes
  fortsat ikke; en enkelt linje finder søgningen alligevel.

### Fjernet

- **Gennemsigtighedshenvisningen i vinduet „Om dette program" er væk
  igen.** Den stod der siden 0.10.22-beta.1 og sagde, at applikationen er
  udviklet med hjælp fra kunstig intelligens. Den er ikke krævet nogen
  steder, og netop i en applikation til databeskyttelse læste nogen den
  som en udsagn om arbejdsmåden – altså som om dokumenterne gik til en
  tjeneste på nettet. Der renses fortsat udelukkende på egen
  computer; det står, hvor det hører hjemme, i fanen „Databeskyttelse".

### Rettet

- **Programmet udskiftede sit eget ikon med et ringere.** Den, der
  registrerede kontekstmenuen fra programmet, havde bagefter et andet
  skilt i proceslinjen end efter installationen – lignende, men med
  venstrejusterede i stedet for centrerede bjælker og synligt grovere.
  Bag det stak en nødløsning: Finder programmet ikke ikonskabelonen,
  tegner det selv et. Det var tænkt til det tilfælde, at der **slet
  ingen** ikoner findes; faktisk tegnede det også, når de medfølgende
  længe havde ligget der – og overskrev dem. I en udgave installeret fra
  opsætningen findes ingen skabelon, så det ramte alle der. Eksisterende
  ikoner forbliver nu urørte.

  **Allerede berørte installationer henter ikke selv det rigtige ikon
  tilbage** – installer én gang på ny for det.

- **„Objektkennung: OB-4711-22" gjaldt som brugernavn.** Genkenderen til
  brugernavne kontrollerede sine betegnelser uden ordgrænse foran – altså
  greb den **hvert** ord, der ender på en af dem: Objektkennung,
  Fahrzeugkennung, Gerätekennung. Værdien bagved blev fjernet, selvom den
  intet har med et brugernavn at gøre.

  Sammensætninger, der virkelig er ment – „Benutzerkennung",
  „Anmeldekennung" –, står enkeltvis på listen og findes fortsat.

- **På engelsk, græsk, japansk og koreansk stod seksten pladsholdere på
  tysk i resultatet.** Den, der havde sat brugerfladen til et af disse
  fire sprog, fik for de nyere datatyper de tyske betegnelser skrevet ind
  i dokumentet – af en adgangskode blev der `[ZUGANGSDATEN_1]` i stedet
  for `[CREDENTIALS_1]`, af en diagnosenøgle `[DIAGNOSESCHLUESSEL_1]` i
  stedet for `[DIAGNOSIS_CODE_1]`. Berørt var helbred, diagnose,
  medicinering, diagnose- og lægemiddelnøgler, religion, fagforening,
  politisk mening, strafferet, adgangsdata, brugernavn, kortdata,
  koordinater, erhverv, beløb og kendetegn.

  De øvrige 44 sprog havde aldrig fejlen: De henter deres betegnelser fra
  sprogfilerne, hvor disse typer stod fra begyndelsen. Netop disse fire
  sprog fører af en anden grund deres egne tabeller – deres skrift
  overlever ikke PDF-tegnsættet, hvorfor der står latinske betegnelser –,
  og i disse tabeller manglede de nye typer ganske enkelt.

  Det blev opdaget under oversættelsen af katalogsiden: Hjemmesiden lovede
  engelske læsere betegnelser, som programmet ikke skrev. En kontrolsten
  holder nu de fire tabeller op mod listen over alle betegnelser, der
  overhovedet kan opstå.

- **Regel-vinduet åbner ikke længere for lille til sit indhold.** I fanen
  „Egne søgemønstre" lå assistentens forklaringslinje („Der søges efter:
  …") halvt bag feltet „Prøvetekst" – netop den sætning, man bruger til at
  kontrollere, uden kendskab til regulære udtryk, om ens egen regel søger
  det rigtige. Vinduet havde en fast minimumsstørrelse fra en tid med
  færre faner og kunne derfor trækkes mindre end det, der skal være
  plads til. Nu retter det sig efter sit indhold og bliver kun så lille,
  som alt forbliver læsbart.

- **Navne i regnearksformler bliver ikke længere stående.** En celle har
  mere end ét sted til tekst, og hidtil blev kun ét ryddet. Stod et navn i
  en formel – `="Frau "&"Sieglinde Ortner"` – eller var det det senest
  beregnede resultat af en formel, forblev det uændret i mappen, selvom
  den samme person i nabocellen var erstattet. Den, der klikkede på
  cellen, læste det i redigeringslinjen.

  Begge dele erstattes nu. Der røres kun ved det, der står mellem
  anførselstegn: Cellereferencer, funktionsnavne og arknavne forbliver
  urørte, `=SUMME(K2:K6)` beregner videre. Fordi det samme navn overalt
  får den samme pladsholder, finder også `=SUMMEWENN(A:A;"Huber";B:B)`
  fortsat sine rækker.

- **Diagrammer viser ikke længere navne.** Et diagram gemmer sin egen kopi
  af sine akse-betegnelser – det tegner også fortsat, når kildecellerne
  for længst er tomme. Under søjlerne stod derfor stadig fem personnavne,
  mens tabellen ovenover var ren. Gælder for regneark **og**
  præsentationer.

- **Navngivne områder med fast tekst ryddes.** Et navngivet område kan i
  stedet for en cellereference indeholde en fast tekst; stod der et navn
  dér, forblev det. **Navnet** på området forbliver fortsat stående – det
  refereres af formler, og en omdøbning ville give en referencefejl. Som
  ved arknavnet meldes det, erstattes ikke.

- **En fødselsdato, der én gang er genkendt, forsvinder i hele
  dokumentet.** En dato i sig selv siger intet – først et feltord gør den
  til en fødselsdato, og netop derfor forbliver en fakturadato i fred. Stod
  den samme oplysning i det samme dokument en anden gang uden dette ord –
  i billedtitlen, i et udfyldt formularfelt –, forblev den der, selvom et
  par linjer ovenover „født den …" var genkendt uden tvivl. Der
  overføres kun det, som allerede er genkendt som fødselsdato i **dette**
  dokument; der gættes fortsat intet.

- **Strukturerede data på hjemmesider afslører deres fødselsdato.** I
  JSON-LD-blokken til søgemaskiner står datoen under nøglen `birthDate` –
  nøglen fortæller, hvad det er, ligesom kolonneoverskriften ellers gør.
  Den læses nu med; „Birthday" og „Birthdate" gælder dermed også i
  formularer som feltbetegnelse.

- **Fødselsdato og personalenummer findes nu også i regneark.** I en celle
  står kun den nøgne værdi – `14.03.1988`. Hvad den betyder, siger alene
  kolonneoverskriften, og den står mange rækker længere oppe. I Excel blev
  den allerede læst med; i LibreOffice-regneark og i CSV-filer ikke, og
  der forblev fødselsdatoen derfor stående.

  Begge læser nu overskriften med – **men kun hvis den selv er en
  feltbetegnelse**. Under „Geburtsdatum" falder datoen, under
  „Rechnungsdatum" eller „Lieferdatum" ikke. Det er bevidst den forsigtige
  fortolkning: En overskrift som „Name" over en vilkårlig bemærkning ville
  også engang have lagt en pladsholder over en sætning, hvor der slet ikke
  optræder nogen person.

### Rettet

- **En renset CSV forbliver et regneark.** Genkendelsen læser en
  CSV-linje som en sætning og lagde derfor også sine fund hen over et
  semikolon. Pladsholderen slugte skilletegnet, linjen havde derefter én
  kolonne mindre, og filen kunne ikke længere åbnes som regneark. Fund
  ender nu ved cellegrænsen, og maskeringens anførselstegn forbliver
  stående. De berørte celler læses derefter endnu en gang for sig selv –
  ellers ville nabocellen forblive urenset, som det for lange fund
  havde skjult.

- **Kommentarer i præsentationer.** Sidebemærkningen ved et dias – ofte
  netop det sted, hvor der står „Ring venligst til fru … før mødet" –
  forblev urørt, sammen med navnet på den, der skrev den. I Excel var
  begge dele for længst ryddet; PowerPoint gemmer kommentartekst og
  forfatter på en anden måde, og det var overset. Gælder begge
  konstruktioner: den ældre og den, PowerPoint har skrevet siden 2019 –
  dér også tjeneste-mailadressen, der hænger ved forfatteren. Initialerne,
  som PowerPoint viser ved talebobler, fjernes med.

- **LibreOffice-filer: formel, brugerfelt, notatforfatter.** Hvad der
  allerede var ryddet i Excel, forblev stående i ODS-regnearket – der
  står formlen ikke som et eget element, men som en egenskab ved cellen,
  og navnet i den overlevede. Ved næste åbning beregnede LibreOffice den
  igen frem.

  Dertil tre yderligere steder: Værdien af et **brugerfelt** står i
  OpenDocument én gang oppe i deklarationen og hentes i teksten kun frem –
  erstattet blev hidtil kun opkaldet, så den gamle værdi kom tilbage ved
  åbning. **Forfatteren af et notat** og af en sporet ændring forblev
  stående. Og i et **regneark** blev sporingen af ændringer slet ikke
  ryddet ud – i modsætning til i tekstdokumentet –, så slettet celleindhold
  sammen med redaktørnavne blev bevaret. Cellereferencer og
  summeringsformler forbliver urørte.

- **Gemte hjemmesider afslører deres attributter.** En side viser langtfra
  alt, hvad den indeholder. Et udfyldt formularfelt bærer indtastningen i
  `value`, en JavaScript-brugerflade lægger sit datasæt i `data-…`, og
  blokken til søgemaskiner (JSON-LD) gentager den fuldstændigt og
  velformet: navn, fødselsdato, adresse, telefon. Den synlige tekst var
  renset, alt det andet stod der stadig.

  Nu ryddes også disse steder, dertil `aria-…` (det, der læses op for
  skærmlæseren), `placeholder`, `summary` og det foreslåede filnavn for et
  link. JSON-LD-blokken læses derved som data og forbliver gyldig – dens
  nøgler og dens vokabular forbliver stående, kun værdierne forsvinder.
  Almindeligt JavaScript rører man fortsat ikke ved.

- **Billeder mister deres tillægsdata også uden EXIF.** Et fotografi bærer
  fotografnavn, optagelsestidspunkt og GPS-koordinater for optagelsesstedet
  skrevet ved siden af – ved en boligannonce afslører det adressen, selv
  hvis der ikke står nogen i teksten. Det blev fjernet, så længe billedet
  havde EXIF. Var oplysningerne derimod **kun** gemt som XMP (sådan gemmer
  Lightroom og Photoshop) eller som tekstblok i en PNG (`Author`,
  `Comment`), forblev billedet helt urørt. Begge dele genkendes og fjernes
  nu – også ved billeder, der sidder i et dokument og bevares deri.
  Retningen overlever fortsat, og et billede uden tillægsdata gemmes ikke
  unødvendigt på ny.

- **Linkmål i regneark, præsentationer og Word-dokumenter.** Hvor et link
  fører hen, står ikke i teksten, men i filens eget lager. En mailadresse
  bag „Skriv mail" overlevede derfor rensningen uskadt, mens den samme
  adresse i teksten var erstattet. `mailto:` og `tel:` ryddes nu der lige
  så vel som i gemte hjemmesider.

### Nyt

- **Lægebreve kommer ikke længere beskadigede tilbage.** Hidtil holdt
  navnegenkendelsen lægemidler for personnavne: Af „Metoprololsuccinat"
  blev der `[NAME]`, af „Ramipril" blev der `[ORT]`. Medicinplanen var
  derefter ubrugelig – mens diagnoserne forblev urørte, altså præcis
  omvendt. Målt berørte det **63 % af aktivstofferne** og **53 % af de
  kliniske fagudtryk**, og ikke kun på tysk: over syv sprog 74 %, på
  italiensk alle undersøgte.

  Maskuro kender nu det medicinske ordforråd og lader det være i fred.
  Tilbage bliver 6 % i stedet for 43 % (tysk) og 1 % i stedet for 74 %
  (over sprogene). Hvor en tiltale står foran – „Kære fru …" – forbliver
  navnet et navn, selv hvis det tilfældigvis hedder som et lægemiddel.

- **Sygdomme og medicin kan fjernes – hvis De ønsker det.** Nyt flueben i
  indstillingerne: „Fjern også sygdomme og medicin" (kommandolinje:
  `--mit-diagnosen`). Til personalesager, opsigelser og udtalelser, hvor
  diagnosen ikke vedkommer nogen.

  **Forudindstillet fra**, og det med vilje: Et lægebrev *består* af
  diagnoser og aktivstoffer. Den, der anonymiserer et af dem – til
  forskning, til en uddannelse, til et AI-værktøj –, ønsker for det meste
  netop at beholde dette indhold og kun blive af med, hvem det drejer sig
  om. Diagnosen er dér nyttelasten, ikke identifikationen.

  Genkendelsen finder de gængse betegnelser og erstatter ikke
  gennemsynet: En sygdomsliste er aldrig fuldstændig, fordi lægen skriver
  „C2-Abusus", hvor klassifikationen fører „Forstyrrelser som følge af
  alkohol".

- **Diagnose- og lægemiddelkoder findes.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) og det centrale lægemiddelnummer er helbredsdata ligesom
  enhver udskrevet diagnose – i udskrivningsbreve og afregningsbilag
  endda den hyppigere form. De er forudindstillet til, ligesom de øvrige
  særlige kategorier efter GDPR art. 9.

  En diagnosekode genkendes kun med belæg: med „ICD" foran eller i
  parentes bag diagnoselinjen. Uden denne betingelse ville programmet
  holde funktionstasten **F10** for en misbrugsdiagnose – i
  klassifikationen er F10 netop det.

- **Den færdige fil kan nu kopieres.** Ved hver færdig linje står der ved
  siden af „Vis", „Efterbehandle" og „Vis i mappe" en fjerde knap:
  **Kopier**. Den lægger den rensede fil i udklipsholderen – derfra
  går den med Ctrl+V (Mac: ⌘V) ind i en mail, et chatvindue eller et
  AI-værktøj uden omvejen over mappen.

  Der kopieres **filen**, ikke dens tekst: Sideopsætning, billeder og
  sortlægningsbjælkerne bevares dermed. Via listens kontekstmenu går også
  flere valgte resultater på én gang i udklipsholderen, og i menuen „Fil"
  står den samme vej som **„Kopier resultat"** for dem, der hellere
  bruger tastaturet.

- **Landevalget kan nu følge dokumentet.** Identitets-, social- og
  skattenumre er forskellige fra land til land, og hvilke lande der
  kontrolleres, stod hidtil fast for hele sessionen – afledt af
  brugerfladens sprog. Den, der arbejder på tysk og renser et
  fransk brev, søgte altså i det efter tyske skatte-ID'er og ikke efter
  det franske socialsikringsnummer.

  I regelvinduet står der nu til det formål **„Selvvirkende efter
  dokumentets sprog"**. Det faste valg forbliver ved siden af, og det med
  vilje: Sproggenkendelsen er ikke ufejlbarlig – genkender den forkert,
  griber det forkerte landevalg ind. Den, der kun behandler sager fra ét
  land, kører sikrere med den faste liste.

  Urørt af dette forbliver de **tyske** mønstre (skatte-ID, nummerplade,
  gennemvalg): De hænger ved sproget, ikke ved landevalget, og griber
  fortsat ind, også når en kort tysk tekst klassificeres som engelsk.

- **Adgangskoder, nøgler og brugernavne findes nu.** Den, der kopierer en
  fejlmeddelelse, en log eller et uddrag fra en konfigurationsfil ind i et
  AI-vindue, har næsten altid en adgangsnøgle deri – og den stod hidtil
  uændret der.

  Begge dele genkendes: de udbredte nøgleformer, der taler for sig selv
  (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, hovedet af
  en privat nøgle), og den betegnede form – „Adgangskode:", „API-Key =",
  „Token:", „Brugernavn:". Der erstattes kun værdien, aldrig betegnelsen:
  „Adgangskode: [ZUGANGSDATEN_1]" forbliver læsbar, og den, der
  kontrollerer resultatet, ser, at der stod en adgangskode.

  Brugernavn og adgangskode er to adskilte typer. Den, der kun vil fjerne
  adgangskoder, slår den ene fra og beholder den anden.

- **Stregkoder og QR-koder i billeder gøres ukendelige.** På et scannet
  brev sidder der næsten altid en kode, og i den står sagsnummeret – det
  samme nummer, som fjernes i teksten ved siden af. Hidtil forblev den
  maskinlæsbare udgave stående: Bjælken over nummeret nytter ikke noget,
  hvis en enhed to centimeter derfra kan aflæse det på et sekund.

  Genkendes gør QR-kode, Data Matrix, Aztec, Code 128, EAN og de øvrige
  gængse former. Ukendelig betyder pixeleret, og det grovere end ved
  ansigter: Kodens fejlkorrektion henter overraskende meget tilbage fra
  få bevarede felter, et halvhjertet slør ville ikke være en fjernelse.

  Muligheden findes ved siden af „Gør ansigter ukendelige" og er ligeledes
  **forudindstillet til**. Også ved slået-fra mulighed fortæller
  rapporten, hvor mange billeder bærer en kode – et ansigt ser man ved
  gennembladring, en kode anses for pynt.

- **Kortverifikationsnummer, PIN og udløbsdato findes.** Kreditkortnummeret
  fandt programmet allerede; først med de tre oplysninger ved siden af er
  det brugbart, og på hver afregningskvittering står de sammen. Alle tre
  kun bag deres betegnelse – „123" alene er et husnummer, et sidetal eller
  et antal.

- **Koordinater i teksten findes.** Fra billeder har Maskuro allerede
  fjernet optagelsesstedet; stod den samme oplysning som tekst i
  erklæringen eller i indsatsrapporten, forblev den stående. Genkendes
  gør decimalgrader og grad-minut-sekund-skrivemåden. Ved decimalgrader
  skal et ord som „Standort", „Fundort" eller „Koordinaten" stå i
  nærheden – ellers ville hver måleserie med to decimaler være en
  stedangivelse.

- **Pengebeløb kan nu fjernes med.** Nyt flueben „Fjern også pengebeløb",
  forudindstillet **fra** ligesom datoangivelserne ovenover: I en
  kontrakt er beløbet indholdet, og den, der sortlægger alt, beskytter
  ingen. I en lønseddel, et forligsforslag eller et kontoudtog er det
  derimod netop den oplysning, der siger mere om personen end navnet ved
  siden af — det ved kun den, der har dokumentet foran sig.

  Et beløb genkendes **kun med valutaangivelse**: „4.250,00" alene er et
  antal, først „4.250,00 EUR" er penge. Valutasymbol, forkortelse og
  udskrevet navn tæller, både foran og bagved, inklusive skrivemåden
  „990,– CHF".

- **De særlige kategorier efter GDPR art. 9 genkendes.**
  Religionsbekendelse, fagforeningstilhørsforhold, politisk overbevisning,
  helbredsoplysninger – og ved siden af de strafferetlige oplysninger
  efter art. 10. Det er de data, hvis behandling forordningen i
  princippet **forbyder**; de er derfor som den eneste nye gruppe
  forudindstillet **til**. Den, der vil beholde dem, afgør det selv.

  Genkendes gør den form, de i praksis står i: formularfeltet på
  personalebladet – „Religion: rk.", „Fagforening: 3F", „Grad af
  invaliditet: 50", „Straffeattest: ingen" –, og det både med kolon ved
  siden af og med betegnelsen ovenover, som et udfyldt blad leverer det.

  **Løbende tekst hører til AI-niveauet.** „Han har i årevis engageret sig
  i fagforeningen" er den samme oplysning, og intet søgemønster finder den
  pålideligt. AI-niveauet søger fra denne udgave udtrykkeligt også efter
  disse kategorier; den, der har brug for løbende tekst, slår det til.

- **Personkendetegn og erhverv – de oplysninger, der også uden navn viser,
  hvem der menes.** Køn, civilstand, højde, øjen- og hårfarve fjernes fra
  denne udgave; erhverv, funktion og afdeling efter ønske, via et eget
  flueben („Fjern også erhverv og afdeling") eller `--mit-berufen`.

  **Hvorfor det ene er til og det andet fra:** „Lederen af indkøbsafdelingen"
  udpeger i en virksomhed netop én person, selv hvis navnet ved siden af er
  sortlagt – i en udtalelse eller en opsigelse skal det fjernes. Et
  medarbejderoverblik *består* derimod af stillingsbetegnelser; den, der
  fjernede dem som standard, ville aflevere et tomt blad. Hvilket tilfælde
  der foreligger, ved kun den, der har dokumentet foran sig. Kendetegnene
  ovenfor står næsten kun i formularfelter, er sjældne og bærer aldrig
  indholdet – de koster altså intet.

- **Kontrollere en fremmed fil.** „Fil → Kontroller fil …" genlæser et
  allerede sortlagt dokument og melder, hvad der stadig står deri – og
  **på hvilket sted**: side og linje, type og længde. Til det tilfælde,
  at nogen kontrollerer en andens arbejde: en sag fra advokatkontoret, et
  svar fra myndigheden, ens egen udgående post før afsendelse.

  **Værdien selv står ikke i rapporten.** Den, der slår stedet op, ser den
  alligevel – og rapporten må derfor gemmes og videregives uden selv at
  være en samling af personoplysninger.

  **Og rapporten fortæller i alle tilfælde, hvad den ikke kunne se.**
  Billeder læses ikke; ved en scanning uden tekstlag betyder „intet fund"
  *ikke kontrolleret*, ikke *rent*. I kommandolinjen adskiller
  returværdien det: `--nachpruefen` giver 0 for kontrolleret og rent, 4
  for fund og 5 for ikke kontrollerbart. Dermed kan udgående post
  automatisk tilbageholdes i stedet for at blive vinket igennem.

- **Kontrolrapport: ét ark pr. rensning.** „Fil → Gem kontrolrapport
  …" – eller `--pruefbericht <mappe>` i kommandolinjen – skriver en
  enkeltsidet PDF (valgfrit CSV eller tekst) med oplysninger om kørslen,
  de fundne typer med antal, to nøgletal og en kontrolpåtegning. Til
  sagsmappen og til tilsynet: Kontrolloggen er det bæredygtige bevis, men
  ingen fremlægger en JSON-Lines-fil.

  **Nye er to tal**, som man hidtil ikke kunne se nogen steder: den
  *gennemsnitlige konfidens* – hvor sikker genkendelsen var ved det, den
  fandt – og *maskeringsraten*, andelen af erstattede tegn i teksten.
  Begge står med deres begrænsning: Konfidensen siger **intet** om det
  oversete, og ved siden af den står altid, hvor mange fund den overhovedet
  omfatter; raten tæller ikke billeder med og bliver for høj ved et
  billedholdigt dokument.

  **Fundværdier står ikke på arket** – samme begrænsning som ved
  protokollen og søgekørslen. Nederst står to linjer, som ikke siger det
  samme: Tjeksummen viser, at arket er uændret; protokollinjen – kun ved
  løbende protokol – henviser til den **underskrevne** linje, der belægger
  kørslen. Først den beviser oprindelsen.

- **„Hvor sikker var det?" – nøgletallene ved resultatet.** En knap
  „Nøgletal" under resultatet folder ud, hvad der hidtil ikke kunne ses
  nogen steder: fund, ord og tegn, fordelingen pr. type som søjlelinje,
  dertil den gennemsnitlige konfidens og maskeringsraten. Samme tal som i
  kontrolrapporten, blot straks og uden udskrift.

  **Med sit forbehold i samme flade:** Ved siden af konfidensen står, hvor
  mange fund den omfatter, og derunder sætningen om, at den **intet**
  siger om det oversete. En procentsats uden denne sætning læses som en
  trefprocent – og den, der forstår den sådan, er dårligere stillet end
  uden tallet.

  Der beregnes først ved udfoldning: Nævneren i maskeringsraten koster pr.
  fil en læseproces, og det skal ikke betales af den, der slet ikke ser på
  tallene.

- **Byg egne søgemønstre uden at skrive et.** Fanen „Egne søgemønstre"
  fører nu i tre trin gennem sagen: *Hvad søger De? → Hvordan ser sådan en
  oplysning ud hos Dem? → Navngiv og gem.* De indtaster et eksempel –
  f.eks. `KD-004711` –, programmet udleder reglen deraf og skriver med ord,
  hvad den søger efter. En forhåndsvisning med trefftæller kontrollerer ved
  hvert tastetryk.

  **Et regulært udtryk optræder ikke i den forbindelse.** Kunnen var aldrig
  problemet: Egne søgemønstre har eksisteret længe, blot krævede de et
  udtryk som `\bKD-\d{6}\b`, og det skriver ingen i et advokatkontor eller
  en personaleafdeling. Den, der *vil* skrive et, folder eksperttilstanden
  ud.

  **Skabelonkataloget er nyordnet:** tretten kort med navn, forklaring og
  eksempelværdi, filtreret via kategorimærker – Finans, Myndigheder,
  Kontakt, Personale, Medicin.

  Og hvis det udledte mønster griber for bredt, siger programmet det af sig
  selv: Et eksempel bestående kun af cifre rammer hvert årstal og hvert
  beløb, og den, der ikke kan læse udtrykket, ville ellers ikke kunne
  bemærke det.

- **Syv mærker i stedet for seksoghalvtreds afkrydsninger.** En ny fane
  „Hvad der søges efter" samler alle genkendelige typer i syv grupper –
  Person, Kontakt og sted, Identifikationer, Finans, Teknik, Særlige
  kategorier, Virksomheder og Egne. Et mærke slår sin gruppe til, „Alle
  til" og „Alle fra" hele listen; derunder forbliver hver type
  individuelt afkrydsbar.

  **Forudindstillet er alt til, og det forbliver sådan.** Det, der slås fra
  her, søges slet ikke – det groveste indgreb, regelvinduet tillader, og
  det virker på hvert dokument. Derfor står der under listen til enhver
  tid, hvor mange typer er fra, og der gemmes kun det slåede fra: En ny
  type er dermed også til i en regelfil fra i forgårs, i stedet for
  stiltiende at falde ud.

- **Overfør en ramme til alle sider.** I vinduet Efterbehandling tager
  knappen **Overfør til alle sider** den senest trukne ramme og sortlægger
  det samme sted på hver yderligere side – til brevhoved, sidefod og
  sagsnummerfelt. Ved en scannet sag med firs sider gør det tyve minutter
  til to.

  **„Samme sted" betyder samme *relative* sted på arket.** I en bunke fra
  arkføderen ligger der jævnligt en side på tværs, en anden er A3, en
  tredje drejet; et absolut overført rektangel landede der ved siden af
  brevhovedet – og man ville se en bjælke og tro, sagen var klaret.

  **Der sortlægges, ikke erstattes**, også når udgangsrammen var en
  pladsholder: Under det samme rektangel står der på side fyrre noget
  andet end på side ét, og en pladsholder med samme nummer ville påstå en
  lighed, der ikke findes.

- **En påtegning på sortlægningsbjælken.** I retten til aktindsigt står der
  ved siden af hver sortlægning, hvorfor der er sortlagt. Det nye felt
  **Påtegning på bjælken** i indstillingerne – eller `--balkenvermerk` –
  skriver en kort tekst på hver bjælke: „§ 203 straffeloven", „GDPR",
  „fortroligt". For et dokument, en myndighed udleverer, er det forskellen:
  Modtageren ser grunden uden at have en protokol, som vedkommende
  alligevel aldrig får.

  **Forudindstillet tom**, for påtegningen er synlig i det udleverede
  dokument og er selv en oplysning – den fortæller modtageren, under
  hvilken titel noget tilbageholdes. Den virker kun ved **sortlægning**;
  hvor der står en pladsholder, står der ingen bjælke. På en bjælke, der er
  for lille til læsbar tekst, udelades den – en ulæselig påtegning ligner
  en fejl.

- **Aktivering uden internetforbindelse – nu fuldstændig.** I
  licensvinduet fandtes „Aktiver uden internet" allerede: øverst en
  anmodningskode at tage med, nederst feltet til aktiveringen, der kommer
  tilbage. Blot kunne den hidtil **ikke udstedes af nogen** – værktøjet
  dertil manglede, og koden løb ud i ingenting. Det er rettet.

  For myndigheder og advokatkontorer med afskærmede computere er det ikke
  et særtilfælde, men normaltilfældet – og det er netop den målgruppe,
  hvor løftet „Deres dokumenter forlader aldrig computeren" vejer tungest.
  Koden afslører intet om dokumenter: Den indeholder licenskoden og en
  hashværdi for computeren, ellers intet.

- **Hent fra scanner.** „Fil → Hent fra scanner …" indlæser en bunke direkte
  og lægger siderne i listen – for en postafdeling forskellen mellem to
  arbejdstrin og ét. En arkføder tømmes til sidste side; enhed, opløsning
  og farve vælges i scannerens systemdialog, som De alligevel kender.

  **Der renses ikke af sig selv.** De ser først, hvad der er kommet
  ind, og trykker derefter „Rens" som ved enhver anden fil – en
  scanning, der straks køres igennem, ville tage synet fra Dem på en skævt
  indført bunke.

  **Det findes kun under Windows**, og menupunktet siger det også på Mac:
  Der skriver scannerens software til en mappe, og „Overvåg mappe …"
  renser alt, hvad der havner der.

### Andet

- **Listen over alle fundne oplysninger følger nu med** og genereres fra
  kildekoden (`hilfe/GEFUNDENE-ANGABEN.md`): 177 typer i 35 lande, 23 af
  dem med tjekcifferberegning. Den fortæller også, hvordan der er talt –
  vi tæller `[NAME]` én gang, hvor andre fører for-, mellem- og efternavn
  som tre poster.

- **Sortlægning findes nu også i Word, PowerPoint, OpenDocument og HTML.**
  Valget mellem pladsholder og sortlægning fandtes hidtil kun for
  PDF-filer. Nu kan de andre det også: Fundet fjernes, og i stedet står
  der en sort bjælke – i selve dokumentet, ikke som et billede oven over.
  Den, der videregiver filen, videregiver en sortlagt akt og ikke én, hvor
  det sortlagte stadig ligger som tekst derunder.

  **Det afgøres separat**, i to valgfelter: „Ved PDF" og „Ved Word,
  PowerPoint, OpenDocument og HTML". Man vil have det forskelligt – den
  sortlagte PDF går til myndigheden, samme sag som Word-fil vandrer videre
  gennem huset og skal forblive læsbar. I kommandolinjen tilsvarende
  `--pdf-modus` og `--office-modus`; en gemt „Sortlægning" fra tidligere
  udgaver gælder fortsat PDF.

  I regneark, ren tekst, CSV og e-mail går bjælken ikke – der mangler
  fladen, den kunne lægges på. Der indsættes fortsat en pladsholder, og
  resultatet **siger det nu**, i stedet for at gøre det stiltiende.

- **Nyt: „Fjern" – fundstedet forbliver simpelthen tomt.** Den tredje
  driftstilstand ved siden af pladsholder og sortlægning, og den eneste,
  der kan **alle** formater: At udelade noget kræver ingen flade. I PDF
  tegnes intet, i Word og HTML forbliver stedet tomt, i et regneark
  ligeledes.

  Den er den mest stille af de tre: Den, der læser resultatet, ser ikke,
  at der nogensinde stod noget der – heller ikke værdiens længde afslører
  sig længere. For et dokument, nogen skal kontrollere, forbliver
  pladsholderen for det meste det bedre valg.

  I billeder gælder ingen af de tre valg: Billedpunkter kan hverken
  erstattes af en pladsholder eller udelades. Det, tekstgenkendelsen finder
  der, males over som hidtil altid.

- **Vinduet Efterbehandling påstår ikke længere erstatninger, der ikke
  findes.** Til højre stod der en pladsholder ved hver værdi – også ved en
  sortlagt fil, hvor der ikke findes en eneste. Et klik på sådan en linje
  markerede intet, og „Fortryd" løb ud i ingenting. Nu står der „sortlagt"
  hhv. „fjernet", og linjerne kan slet ikke fortrydes: Teksten er væk, der
  er intet at hente tilbage. Det gjaldt for sortlagte PDF-filer, for Word
  og OpenDocument og for alt, hvad der blev fundet i billeder.

- **Tekstvisningen viser nu bjælkerne som bjælker.** En sortlagt Word-fil
  så under efterbehandlingen **tom** ud: På de sortlagte steder stod der
  huller, som havde programmet slugt teksten. Grunden var visningen, ikke
  resultatet – i selve dokumentet lå bjælken hele tiden rigtigt. Nu står
  den også sådan i visningen, sort som i resultatet, i Word, PowerPoint,
  OpenDocument og HTML.

- **Outlook-beskeder (`.msg`) renses nu.** `.eml` fandtes længe – i
  danske virksomheder er Outlook derimod den e-mail, der bruges, og der
  hedder en gemt besked `.msg`. Dermed er det tætteste PII-format nu også
  dækket i sin mest udbredte gemme-form: emne, afsender,
  modtagerlinjer, beskedtekst, HTML-udgave, modtagerliste og vedhæftninger
  – de sidstnævnte via de eksisterende veje og med samme pladsholdere som
  mailteksten.

  **En `.msg` bærer den samme tekst flere gange**, og det er fælden: som
  ren tekst, som HTML **og** som RTF. Den, der kun renser ren tekst,
  har intet gjort – Outlook viser fortrinsvis RTF. RTF-udgaven fjernes
  derfor helt, ligeledes internet-hovedlinjerne med deres Received-kæde og
  de binære søgenøgler, der overlever enhver tekstrensning navne og
  adresser. Resultatet åbner fortsat i Outlook og viser teksten uden
  skriftformatering; rapporten siger det udtrykkeligt.

- **Beskriv regler med egne ord i stedet for at skrive regex.**
  Regel-vinduet kan meget og krævede dertil et regulært udtryksmønster –
  det sted, hvor det holder op for de fleste. Nu er en sætning nok:
  „Vores sagsnumre af formen 12 C 345/26 skal blive stående." AI-niveauet
  foreslår ud fra det begreber og søgemønstre.

  **Der overtages kun det, De afkrydser – og forudindstillet er intet
  afkrydset.** Ved hvert forslag står en sætning om, hvad det betyder, og
  antallet af dets fund i en eksempeltekst, De kan give med. Det, der
  **fratager** beskyttelse, er markeret som sådan: „fjern altid dette
  begreb" og „fjern aldrig dette begreb" ville se ens ud på en liste
  ellers. Forslag, der ville ramme alt, vises slet ikke.

- **Kontrolloggen tæller nu sammen over alle arbejdspladser.** Lægger et
  hus loggen via `protokoll_pfad` på en delt drev, skriver hver
  arbejdsplads sin egen månedsfil – hidtil måtte en databeskyttelsesrådgiver
  med tredive pladser se på tredive filer enkeltvis. Over listen står der
  nu en linje med månedens summer, og **den melder brudte kæder med
  navn**: En efterfølgende ændring falder kun i øjnene, hvis nogen ser
  efter, og i tredive filer ser ingen efter i hånden.

  **Ingen oversigt pr. person** – heller ikke i denne visning. Et rangeret
  overblik over „hvem har renset hvor meget" ville egne sig til
  adfærds- og præstationskontrol, og det er det, der tæller
  medbestemmelsesretligt, ikke hensigten. Der tælles kørsler, filer og fund
  over hele huset.

- **„Foreslå profil ud fra et dokument": spørg reglerne én gang i stedet
  for at gå igennem fireogfyrre typer.** I regel-vinduet findes en ny
  knap: Den viser AI-niveauet et dokument, bestemmer, hvad der er tale om
  – lægebrev, ansøgning, kontrakt, faktura, afgørelse – og foreslår de
  strategier, der passer dertil. Ved lægebrevet f.eks. forskydes
  datoangivelser i stedet for at blive erstattet, fordi kronologien i en
  patientjournal er indholdet.

  **Profilerne findes i programmet, modellen vælger blot** – sortlægnings-
  reglerne afhænger ikke af, hvad en sprogmodel synes er en god idé. Hvert
  punkt foreslås enkeltvis og med begrundelse; der overtages intet uden
  forespørgsel, og det, De selv har fastlagt, forbliver urørt. Uden
  AI-niveau bliver det ved den sikre standard: Pladsholder for alt.

- **Ny strategi „opdigt": en plausibel falsk værdi i stedet for en
  pladsholder.** „Fru Berger skrev til hr. Doppler i Fulda" i stedet for
  „[NAME_1] skrev til [NAME_2] i [ORT_1]" – til undervisningsmateriale,
  demonstrationssager, testdatasæt og alt, hvad der efterfølgende
  forelægges en AI. Tiltale, sætningsopbygning og læsbarhed bevares.

  Den samme værdi får den samme falske værdi, over alle filer i en sag og
  på hver computer med den samme regelfil – **uden at der nogen steder
  gemmes en tildeling** (samme mekanik som ved hashing). E-mailadresser
  ligger på reserverede eksempel-domæner, telefonnumre i det dertil
  afsatte område, opdigtede IBAN'er bærer et korrekt beregnet tjekciffer.
  Muligt for navne, steder, adresser, virksomheder, e-mail, telefon og
  IBAN; for andre typer afvises reglen i stedet for at forblive
  virkningsløs.

  **Rapporten siger udtrykkeligt, at der er opdigtet.** Et sådan
  renset dokument læses som et ægte og er ikke et – det duer ikke
  som bevis og må ikke videregives som original.

- **Modprøven: „Hvem forbliver genkendelig?"** Et nyt flueben under
  AI-niveauet forelægger sprogmodellen **det færdige resultat** endnu en
  gang og spørger, hvem der trods rensning kan genkendes. Der menes
  det tilfælde, som ingen genkendelse i verden finder, fordi der slet ikke
  står noget navn dér: „den eneste jordemoder i distriktet", „kollegaen,
  der sagde op i marts efter branden". Intet mønster griber ind, og lokalt
  ved alligevel enhver, hvem der menes.

  **Der fjernes intet dermed.** Stederne står med en begrundelsessætning i
  rapporten, og der besluttes i hånden – et program, der af sig selv tager
  sætninger ud af et dokument, fordi de forekommer det afslørende, gør en
  rensning til en omskrivning, og ingen ville se, hvad der mangler.
  Højst fem steder pr. fil; det, modellen ikke kan belægge ordret, falder
  bort. I kommandolinjen: `--restrisiko` sammen med `--ki`.

- **Vejen tilbage fra AI'en: „Oversæt svar tilbage".** Hidtil var kun den
  halve løkke bygget – kopiere tekst, indsætte renset, forelægge
  AI'en. Svaret kom tilbage med `[NAME_1]`, og den, der havde brug for
  det, indsatte i hånden igen det, vedkommende havde taget ud i hånden.
  Nu findes vejen tilbage i menuen „Program": Kopier svar, klik på posten,
  de rigtige navne står der igen.

  Tildelingen dertil ligger **kun i arbejdshukommelsen**, gælder altid kun
  det senest rensede sted og udløber efter en time; den, der slår
  udklipsholder-vagten fra, mister den straks. Der kan kun hentes tilbage,
  hvad der blev erstattet – sortlagt, maskeret og hashet er ikke
  reversibelt, og programmet siger, hvor mange steder det derfor måtte
  lade stå. Administrerede installationer slår vejen tilbage helt fra via
  standardværdien `rueckweg`.

- **Overvåg mappe: hvad der lægges ind, ligger kort efter renset i
  udgangen.** Til en postafdeling, et postboks-team eller en
  scanningsmappe – opsæt én gang, derefter klikker ingen mere. Findes
  under „Fil → Overvåg mappe …", i kommandolinjen via `--wache <mappe>`.

  Originalen bliver liggende, hvor den lå; efter ønske vandrer den
  uændret til undermappen „Udført", hvor der aldrig overskrives noget. En
  fil røres først, når den er færdigskrevet – en fil, der endnu kopieres
  over netværket, ville ellers blive halvt læst og meldt som renset.
  Det, der går galt, bliver liggende og bliver sagt, i stedet for at blive
  gentaget uendeligt. Og vagten husker udførte uden filnavne: Det, der
  ligger i en indgangsmappe, afslører ofte allerede i navnet, hvad det
  drejer sig om.

  **Overvågningen af en mappe uden for egen brugerprofil – f.eks. på et
  netværksdrev – forudsætter en automatiseringslicens.** En mappe, flere
  mennesker kan tilgå, er en tjeneste og ikke en arbejdsplads; i egen
  profil og i løbet af prøveperioden gælder begrænsningen ikke.

### Rettet

- **Indstillingerne var afskåret i højre side.** Vinduet åbnede med en
  fast størrelse, og den rakte kun til den skriftstørrelse, der blev
  udviklet med: På Mac stod „Kontroller nu", „Skift …" og henvisningerne
  ved siden af halvt uden for. Nu åbner det så bredt, som dets sider har
  brug for – på hvert sprog og ved hver skriftstørrelse, kun begrænset af
  skærmen.

- **„Kontroller nu" svarer nu synligt.** Resultatet stod i statuslinjen i
  hovedvinduet – altså bag indstillingsvinduet, hvorfra der blev spurgt.
  Den, der kontrollerede, så intet. Nu kommer svaret som en meddelelse
  over indstillingerne, og foreligger en ny udgave, fører det straks til
  installation. Ved programstart forbliver det som hidtil ved
  statuslinjen, uopfordret åbner intet vindue.

- **Kopierede filer nåede ikke frem til udklipsholderen på Mac.** Det at
  lægge rensede filer tilbage meldte succes og lagde alligevel intet
  brugbart ned – indsæt gav intet. Berørt var alt, der skriver filer til
  udklipsholderen.

- **Og fra udklipsholderen blev der på Mac kun læst den første fil.** Den,
  der kopierede tre filer i Finder og valgte „Rens udklipsholder nu",
  fik to af dem urensede tilbage – uden at noget sagde det. Nu kommer
  alle med.

- **„Kontroller fil" tager nu også trukne filer imod** – som hovedvinduet.
  Det aflagte kommer til, i stedet for at kassere det hidtidige valg; at
  lægge det samme to gange ændrer intet, og det, programmet ikke kan læse,
  bliver sagt i stedet for slugt.

- **Og vinduet siger, at det venter på Dem.** Det åbnede med en tom kasse
  og en grå knap „Kontroller" – det ligner, at der ikke er noget, ikke at
  valget mangler. Nu står der „Ingen fil valgt endnu – træk hertil eller
  vælg forneden via 'Vælg filer …'."

- **En lang kørsel siger nu, at den kører.** „Tillægsmodel til den mere
  nøjagtige genkendelse indlæses – et øjeblik …" blev stående, så længe
  genkendelsen regnede: ved en fil med 47.500 ord altså atten minutter,
  selvom indlæsningen var forbi efter ni sekunder. Den, der ser det, tror,
  programmet er hængt fast. Nu følger derefter „Mere nøjagtig genkendelse
  kører – det tager ved lange tekster nogle minutter", og statuslinjen
  tæller med: „Mere nøjagtig genkendelse (7/312)". Der meldes fra modellens
  løkke – for hver 250 ord, altså cirka hver sjette sekund –, ikke pr.
  tekstblok: En tekstblok bærer tolv tusind ord og tager minutter.

- **En afbrudt kørsel siger nu, at den er blevet afbrudt.** Den, der
  trykkede „Afbryd", læste derefter „0 af 1 fil(er) renset." –
  rigtigt talt og alligevel den forkerte oplysning. Meddelelsen om, hvilken
  fil det ramte, blev i samme øjeblik overskrevet af tælle-meddelelsen. Og
  i fillisten stod der fortsat „kører …", selvom intet længere kørte; der
  står nu „afbrudt".

- **Sætningen om databeskyttelse var afskåret.** „… ingen cloud, ingen
  upload. Mere i databe" – ved den vinduesbredde, programmet starter med,
  sluttede den midt i ordet. Den tager nu den fulde bredde.

- **Licenstjenesten kunne meddele noget, og ingen lyttede.** Når alle
  licenspladser er optaget, licensen er udløbet, nøglen er ukendt, eller
  licensadministrationen hos udbyderen er slået fra, sender tjenesten
  netop dertil en grund – planen var fra begyndelsen, at De skulle få den
  forklaret **én gang**. Den blev aldrig vist. Nu vises en henvisning, der
  først siger, at programmet fortsætter uændret, og derefter, hvad det
  drejer sig om. Én gang pr. grund: Den, der har lukket den, ser den ikke
  igen ved den daglige kontrol – dog igen, hvis grunden ændrer sig.

- **En flerpladslicens købt i shoppen viste „1 plads".** Shoppen fordeler
  forberedte nøgler og holder selv styr på den købte pladsantal; vist blev
  imidlertid antallet fra selve nøglen, og det lyder ved hver
  lagernøgle på én plads. Den, der havde købt otte pladser, læste „1
  plads" – og fra og med den anden tilmeldte computer stod visningen i
  rødt sammen med „Kontakt venligst Deres administration". Nu gælder det
  antal, tjenesten sidst har meldt; uden svar bliver det ved nøglen, og
  mindre end det købte omfang bliver det aldrig. Det samme gælder for
  eftertkøb og forlængelser: De ændrer pladsantallet hos udbyderen, ikke
  Deres nøgle.

- **Efter købet stod der „Licenseret til Maskuro Privatlicens".** Det er
  intet navn, men den pladsholder, hvorunder nøglerne forberedes – Deres
  navn kan ikke stå der, fordi nøglen underskrives allerede før købet. I
  stedet for at vise Dem et fremmed navn som Deres eget, står der nu
  ganske enkelt „Privatlicens" og pladsantallet. Ved en licens, der er
  udstedt til Dem, står Deres navn fortsat der.

- **I Hjælp-menuen stod „Hjælp _FAQ".** Og-tegnet var blevet til en
  understregning, fordi Qt læste det som markering af et tastaturbogstav.
  Nu står der „Hjælp & FAQ".

- **Indstillingsvinduet blev stående, når programmet forsvandt til
  ikonet** – og også når hovedvinduet blev lukket. Det følger nu med.
  (Gælder kun denne udgave; det egne vindue er nyt.)

- **En afvist licensanmodning siger nu, hvad grunden er.** Afviste
  licenstjenesten en anmodning uden at medsende en grund, stod der i
  licensvinduet i rødt „Ukendt svar." – en sætning, hverken De eller
  supporten kan bruge til noget, og som får Dem til at søge fejlen ved
  Deres nøgle. Nu står der, hvad der faktisk skete: at tjenesten har
  afvist uden at begrunde det, og hvem De kan henvende Dem til. Er
  licensadministrationen hos udbyderen midlertidigt slået fra, nævnes også
  det – sammen med henvisningen om, at Deres nøgle ikke er berørt af det.

- **På Mac gjaldt indstillede sprog pludselig som manglende.** Ved start
  meldte programmet „Der er ikke installeret nogen sprogmodel" og tilbød
  førsteopsætningen, selvom sprogene for længst var indlæst – den, der så
  under „Dokumenternes sprog", fandt dem der fuldtallige. Programmet
  søgte dem afhængigt af startvejen på to forskellige steder: Blev det
  startet fra programmemappen, fandt det dem; blev samme bygning startet
  som en simpel mappe, søgte det dem ved siden af sig selv, hvor der ikke
  ligger nogen. Fra nu af gælder på Mac uden undtagelse det samme sted i
  brugerprofilen, uanset hvordan programmet er pakket. Intet skal
  genindlæses.

- **„Hvad er nyt" viste den halve liste.** Vinduet efter en opdatering
  afbrød midt i sætningen, og de resterende punkter stod som tomme
  punktopstillingstegn. Skylden lå hos en pladsholder i kantede parenteser
  – f.eks. `<datei>.docx` –, som visningen holdt for formatering og fra
  hvilken alt yderligere blev kasseret. Netop nyhederne om sikkerhed var
  berørt af det. Hjælpen viser altid sådanne pladsholdere korrekt; nu gør
  dette vindue det også.

- **Knib med to fingre zoomer nu i vinduet Efterbehandling.** På
  trackpaden er det *den* zoombevægelse – i editoren gjorde den hidtil
  intet, og den, der ville se nærmere på et sted, måtte tage til skyderen
  eller Ctrl+musehjul. Siden følger bevægelsen umiddelbart og tegnes skarpt
  igen ved slip.

- **Der zoomes ind på det sted, man ser på.** Knib forstørrer om punktet
  mellem fingrene, Ctrl+musehjul om punktet under markøren. Knapper,
  tastaturgenveje og zoomskyderen holder midten fast – til dem hører ikke
  et sted, man peger på. Før forblev rullepositionen stående ved alle: Fra
  en tilpasset side holdt det overkanten, og alt derunder vandrede ud af
  billedet, når man zoomede ind.

- **„Før/Efter" var en død knap i sidevisningen.** Så længe sidevisningen
  var slået til, kunne den trykkes – og meldte hver gang, at originalen
  ikke kunne åbnes. Der er heller intet at sammenligne der: Sidevisningen
  er et billede af den rensede udgave, en modpart til originalen
  findes ikke. Knappen er nu spærret og nævner ved musen-over grunden samt
  udvejen (tekstvisningen). Dens beskrivelse lovede oven i købet
  udtrykkeligt, at sammenligningen foregik „uafhængigt af, om tekst- eller
  sidevisning er aktiv" – det stemte aldrig.

- **Sidevisningen fik LibreOffice til at gå ned.** Blev to sidevisninger
  genereret samtidig – f.eks. „Sortlæg som PDF" mens forhåndsvisningen
  endnu beregnede –, meldte systemet et LibreOffice-nedbrud, selvom
  siderne til sidst dukkede op alligevel: Begge kørsler tilgik det samme
  LibreOffice-arbejdslager, hvilket det ikke tåler. Nu får kun én kørsel
  det ad gangen; de øvrige skifter til deres eget. De tager et par
  sekunder længere om det, til gengæld kommer der ingen fejlmeddelelse
  mere, og ingen af kørslerne står uden resultat. En anden renderingsopgave
  ved siden af en igangværende accepteres slet ikke længere.

- **„Vis original" kunne afslutte programmet.** Kunne originalen ikke
  åbnes – fordi den var flyttet, omdøbt, forsynet med adgangskode eller lå
  på et adskilt drev –, afbrød vinduet Efterbehandling uden varsel, og
  åbne arbejdskopier gik tabt. Nu kommer en henvisning, kontakten springer
  tilbage, og den rensede udgave forbliver stående. Hvor originalen
  principielt ikke passer sammen – f.eks. ved en PDF-sidevisning, der er
  opstået af en Word-fil –, er kontakten fra begyndelsen spærret og nævner
  ved musen-over grunden, i stedet for at vise den samme henvisning ved
  hvert tryk.

- **Fejlrapporter nåede aldrig frem.** Den, der ville melde en fejl, fik
  „Modparten har afvist rapporten" – og ingen havde nogensinde set den. To
  årsager, begge på vejen: Programmet legitimerede sig ikke over for
  serveren og blev derfor afvist af beskyttelsen mod masseadgang, og
  adressen henviste til et andet navn, som programmet ikke fulgte. Begge
  dele er rettet; en rapport går ud igen. **Det samme ramte
  licensaktiveringen**: Tilmelding, afmelding og forespørgsel nåede
  ligeledes ikke tjenesten – der kun umærkeligt, fordi en ubesvaret
  forespørgsel bevidst ikke ændrer noget ved Deres licens. Og forbliver en
  afvisning alligevel uforklarlig, står nu dens tekniske nummer ved siden
  af, i stedet for at hver årsag ser ens ud.

- **Et klik på „Vis original" kunne afslutte programmet.** Kunne originalen
  ikke åbnes – flyttet, omdøbt, på et adskilt netværksdrev, forsynet med
  adgangskode eller beskadiget –, forsvandt vinduet Efterbehandling sammen
  med alle åbne arbejdskopier. Nu forbliver kontakten ved den rensede
  udgave, og en boks siger, hvad der er galt; den tekniske grund står i
  detaljerne, hvis De ønsker at melde den. Det samme gælder for et
  resultat, der ikke kan vises: Vinduet åbner og siger det, i stedet for at
  forsvinde.

- **Spørgsmålet om et nedbrud kom for ofte – og slettede sporet, det
  spurgte om.** Det dukkede også op, når intet var brudt ned: Notatet
  opstår, så snart en uventet forstyrrelse indtræffer et sted, også når
  programmet overlever den og bagefter afsluttes helt normalt; det blev
  aldrig ryddet væk. Og den, der svarede „Nej", tilintetgjorde de eneste
  detaljer om hændelsen – notatet forsvandt allerede ved *visningen* af
  spørgsmålet. Begge dele er rettet: En ordnet afslutning rydder notatet
  væk, der spørges kun ved et rigtigt afbrud, og der markeres først efter
  Deres svar. Detaljerne står under alle omstændigheder i fejlloggen på
  egen computer – den, der intet vil sende, mister alligevel intet dermed.
  Der sendes fortsat kun det, De forinden har set fuldstændigt og selv
  frigivet.

- **„Rens" kunne forblive tavst spærret.** Blev sprogmodellerne
  hængende ved indlæsning, forblev knappen slået fra – uden forklaring.
  Et klik på den gjorde intet, og statuslinjen sagde uændret
  „Sprogmodeller indlæses …", også efter ti minutter. Årsagen: Forstyrrelser
  i baggrundsprocesser gik til et sted, ingen ser ved start fra filhåndteringen;
  tilbage blev et vindue, der så arbejdsklart ud og ikke reagerede på noget
  klik. Nu havner sådanne forstyrrelser i fejlloggen, indlæsningen af
  sprogmodellerne melder sin fiasko i alle tilfælde i stedet for stille at
  give op, og forbliver det alligevel stille, siger programmet efter tre
  kvarter minut, at noget ikke stemmer, med et råd i detaljerne. Den
  spærrede knap nævner ved musen-over sin grund. En lang første indlæsning
  gælder ikke som stilhed: Så længe der meldes fremskridt, forbliver det
  roligt. Som nedbrud tæller det hele ikke: Programmet kører videre, og
  ved næste start spørges der derfor heller ikke om det.

- **På Mac fandt programmet ikke længere opdateringer – og sagde, det var
  på nyeste stand.** Mac-udgaven medbragte ikke noget register over
  rodcertifikater; den søgte det et sted, som kun findes på den computer,
  den bygges på. Dermed kunne den ikke kontrollere hos nogen server, hvem
  den taler med, og afbrød hver forbindelse: ingen opdateringer, ingen
  licensaktivering, ingen indlæsning af sprogmodeller, ingen fejlrapport.
  Ældre udgaver gjorde det stiltiende til beskeden „De bruger den nyeste
  udgave". Certifikaterne ligger nu i selve programmet; finder det ingen
  der, tager det systemets, og på Mac i nødstilfælde nøgleringens – og
  hvis der slet ingen findes, siger det det, i stedet for at påstå en
  nyeste udgave. Selve kontrollen slås aldrig fra dermed.

  Denne ene opdatering skal Mac-brugere stadig installere i hånden: En
  udgave, der ikke når serveren, kan heller ikke opdatere sig selv.

### Ændret

- **Hovedvinduet er blevet ryddet op.** Nederst stod seks lige store knapper
  ved siden af hinanden – „Om …", „Vejledning" og „Hjælp & FAQ" derunder,
  selvom de samme tre veje allerede stod i Hjælp-menuen ovenover. De er nu
  samlet til én knap „Hjælp", der folder dem ud; ingen går tabt. Tilbage
  forneden bliver de to veje, man virkelig starter med: „Rens" og
  „Sortlæg i hånden …".

- **Det, programmet lige nu gør, står nu på et fast sted.** Meddelelsen
  („Sprogmodeller indlæses …", „(3 / 7) brev.pdf", „5 af 7 fil(er)
  renset.") hang hidtil som grå tekst mellem to knapperækker. Den
  har fået sin egen flade, med en farvet prik foran: grå, så længe intet
  kører, blå under arbejdet, grøn efter en glat kørsel og gul, når der er
  faldet henvisninger. Prikken siger intet, der ikke står ved siden af –
  den siger det bare hurtigere.

- **Indstillingerne er blevet et eget vindue.** De lå hidtil i
  hovedvinduet – en kasse med fire faner, man foldede ud under „Flere
  indstillinger", og som derefter var for lille til sit indhold: Der stod
  altid en rullebjælke i den, og valget mellem anonymisering og
  pseudonymisering stod halvt i billedet. Knappen hedder nu
  „Indstillinger …" og åbner et vindue med en sidebjælke; hver af de fire
  sider passer helt ind. Hovedvinduet springer ikke længere op ved
  åbning, og man kan se fillisten ved siden af.
  Ændret er kun, hvor indstillingerne står – hvilke der findes, og hvad de
  gør, er uændret.

- **„Detaljer" folder ud, i stedet for at springe.** Vinduet voksede
  hidtil på ét billede, og man måtte lede efter, hvad der havde ændret
  sig. Nu bevæger det sig derhen.

- **Skriftstørrelser og afstande følger nu samme mål i hele vinduet.**
  Overskrifter var forskellige to steder, og linjer af samme rang stod
  forskelligt langt fra hinanden. Synligt er det som ro, ikke som en
  enkelt ændring.

- **Anonymisering er nu standarden.** Hidtil var pseudonymisering
  forudindstillet: Samme personer fik samme nummer (`[NAME_1]`,
  `[NAME_2]`), sammenhænge forblev læsbare – juridisk forblev det dermed
  dog **personoplysninger**. Den, der ikke indstiller noget, får nu den
  metode, der tager dataene ud af GDPR: Alle fund af en type hedder ens
  (`[NAME]`). Nummereringen er forblevet et valg, det står uændret i
  samme vindue; eksisterende indstillinger forbliver, som de er. I
  kommandolinjen stiller `--pseudonymisieren` (også `--mit-nummerierung`)
  tilbage.

- **Anonymiserede pladsholdere kan ikke længere fortrydes enkeltvis.** Den,
  der anonymiserer, får samme pladsholder for hver person – og dermed
  findes der ikke længere et enkelt sted, der hører til et bestemt navn.
  Vinduet Efterbehandling tilbød alligevel „Fortryd erstatning": Et klik
  ville have indsat *én* af værdierne på *alle* steder. Linjerne er nu
  dæmpede som ved sortlagte oplysninger, klikket fortæller grunden, og et
  fund efterhåndsrettet i hånden får ikke længere et nummer, der ikke
  findes noget andet sted i dokumentet.

  Af samme grund findes der ikke længere „Oversæt svar tilbage" efter en
  anonymiseret kørsel – tidligere ville det have sat et fremmed navn på
  hvert persons plads. Den, der har brug for denne løkke, vælger
  „Pseudonymiser"; programmet siger det nu også sådan, i stedet for at
  henvise til en udløbet tildeling.

  I kommandolinjen afbryder `--zuordnung` nu ved anonymisering, i stedet
  for at skrive en fil, der ikke er en tilbageoversættelse – i vinduet var
  fluebenet allerede spærret. Enten `--pseudonymisieren` med eller
  `--zuordnung` udelades; meddelelsen siger det. Resultatet opstår slet
  ikke i det tilfælde, så et script ikke står med halvt arbejde.

- **Opdateringskanalen står nu som standard på „Stabil".** Uden eget valg
  rettede kanalen sig hidtil efter, hvilken bygning den kørende udgave
  stammede fra – den, der en gang havde prøvet en testudgave, fik fra da
  af varigt testudgaver tilbudt. Et kanalskifte er en beslutning og skal
  også forblive én; standarden er derfor „Stabil". Indstillede kanaler
  forbliver urørte.

### Forbedret

- **„Beschwerdevorgang" gælder ikke længere som stednavn.** I
  overskriften „Aktennotiz – Beschwerdevorgang 12 C 345/26" sortlagde
  programmet forløbet med: Sprogmodellen holdt det for et sted, og det
  uafhængigt af omgivelserne. Optaget er ikke det enkelte ord, men
  **grundordet** i sammensætningen – „vorgang" og „notiz" dækker dermed
  også Geschäfts-, Buchungs- og Zahlungsvorgang eller Telefonnotiz. Af
  tredive undersøgte forvaltningsbegreber udløste tre tidligere en
  falsk alarm, nu ingen mere; der findes fortsat alt, hvad der står ved
  siden af („Beschwerdevorgang: Bernd Meisinger" mister navnet, ikke
  overskriften).

- **Anonymisering fører nu igen bog – til efterkontrollen og protokollen.**
  I den anonymiserende driftstilstand huskede programmet ikke de fundne
  værdier. To ting forblev derved tavse: den dokumentbrede
  konsistens-efterkontrol (et efternavn, der senere optræder alene, blev
  stående) og listen over erstatninger i kontrolloggen. Så længe
  anonymisering var det sjældnere valg, faldt det knap i øjnene – som
  standard ville det være blevet normaltilfældet. I dokumentet ændrer
  intet sig: Pladsholderen forbliver uden nummer.

- **„Ingen personhenførbar dato" hedder nu „ingen personhenførbar
  oplysning".** I fortryd-dialogen og i ansigts-advarslen stod det
  juridiske *dato* – ental for „data". Det blev læst som en kalenderdag,
  især da programmet et andet sted tilbyder „Fjern også datoangivelser".
  Det hedder nu overalt „oplysning", ligesom i de fire grunde ovenover i
  samme vindue.

- **Oprindelseslinjen står nu kun i vinduet „Om".** „Made with ♥ in
  Austria" sad nederst i hovedvinduet midt i knapperækken og læstes der
  som endnu en knap. Den står fortsat i vinduet „Om" – der, hvor man
  søger den.

- **Ablagefladen har nu en synlig kant.** Dens stiplede kant var så bleg,
  at den næppe skilte sig ud fra vinduet – det var ligegyldigt, så længe
  fladen kun var en flade. Siden den er en knap, man kan springe til med
  Tab-tasten, er denne streg det eneste, der viser den som betjeningselement;
  den er derfor hævet til den værdi, standarden kræver dertil.

## 0.10.22-beta.1 – 15. august 2026

### Nyt

- **Slås udklipsholder-overvågningen fra, er den virkelig fra.** Vagten
  holder de seneste indhold i arbejdshukommelsen, så originalen kan lægges
  tilbage – hidtil også, når du havde slået overvågningen fra. Nu glemmes
  forløbet ved frakobling. Det koster genoprettelsen efter frakobling, og
  netop sådan er det ment: Frakoblet betyder frakoblet.
- **Fejlprotokollen indeholder ikke længere filstier.** Den lå kun på din
  computer og blev aldrig sendt af sig selv – men den førte stier i
  klartekst, og et filnavn afslører ofte mere end indholdet. Af
  „…/Skilsmisse_Mueller_Forlig.docx" bliver der nu ved skrivning
  `<fil>.docx`; endelsen bliver, fordi den tæller ved fejlsøgning. Det
  samme gælder notatet efter et nedbrud.
- **Listen over erstatninger advarer nu i sig selv.** Den er den eneste
  fil, hvori dine originaldata står i klartekst, og den ligger ved siden
  af resultatet – den, der giver en mappe videre, giver den med. Nu står
  advarslen som første linje **i** filen, udgangsområdet nævner den
  fuldstændige sti i stedet for kun filnavnet, og på kommandolinjen
  nævnes filen overhovedet for første gang: Der fik man hidtil slet ikke
  at vide, at den var opstået.
- **Anonymisering eller pseudonymisering er nu et navngivet valg.** På det
  sted stod hidtil et flueben „Navngiv ens navne ens – AI'en genkender så
  stadig, hvem der er hvem". Det beskrev fordelen og fortav
  konsekvensen: Fortløbende nummererede pladsholdere (`[NAVN_1]`,
  `[NAVN_2]`) er **pseudonymisering**, og pseudonymiserede data forbliver
  personoplysninger – den, der troede, dermed at have anonymiseret, tog
  fejl. Nu står begge metoder ved siden af hinanden, hver med sin pris.
  Standarden forbliver pseudonymisering, fordi et dokument, der derefter
  stadig læses eller behandles af en AI, har brug for sine
  sammenhænge. Ved anonymisering er listen over erstatninger spærret: Den
  ville gøre resultatet sporbart igen. Håndbog og FAQ forklarer forskellen
  på alle 18 sprog; på kommandolinjen hedder omskifteren nu også
  `--anonymisieren`.
- **Linjen over aflæggelsesfladen siger nu, hvad der virkelig er sandt.**
  Den lovede „100 % lokal behandling – uden cloud og konto,
  GDPR-venlig". For dine dokumenter passer det, for programmet ikke i
  denne generalitet: Det søger efter opdateringer, melder efter ønske
  fejl, henter modeller efter og tilmelder købte arbejdspladser. Nu står
  der den snævrere og holdbare udtalelse: Dine dokumenter forlader ikke
  computeren.
- **Ved resultatet står nu altid, at det skal kontrolleres.** Hidtil meldte
  Maskuro efter en glat kørsel „12 angivelse(r) fjernet" i grønt og ellers
  intet – det læses som en garanti for at have fundet alt. Henvisninger
  fremkom kun, når noget konkret ikke kunne kontrolleres (billeder,
  ukendte bilag). Nu står der under hvert resultat umiskendeligt, at ikke
  i alle tilfælde alle personoplysninger genkendes, at kontrollen ligger
  hos brugeren, og at manglende skal suppleres manuelt – i vinduet, i
  udgangsområdet og på kommandolinjen. Intet meddelelsesvindue til at
  klikke væk: Sætningen står der permanent. Kortvejledningen siger det nu
  med samme ordlyd.
- **Efter en opdatering står der ved start, hvad der har ændret sig.**
  Hidtil forløb en opdatering stumt og var ikke til at skelne fra en
  genstart. Nu vises engangsvist „Hvad er nyt" – og den, der har sprunget
  en version over, ser de mellemliggende med. Ikke ved allerførste start:
  Der fører kortvejledningen fortsat ind.
- **Kinesisk og japansk finder nu navne.** Hidtil fandt de **ingen** – ikke
  få, ingen. Begge sprogmodeller manglede ordsegmenteringen, uden hvilken
  en sætning uden mellemrum gælder som ét eneste ord; programmet veg
  stiltiende ud til den flersprogede erstatningsmodel. Begge sprog
  genkender nu personer og steder som de øvrige. Den japanske ordbog
  indlæses hermed sammen med sproget og ligger ikke i programmet – den
  alene ville være godt 200 MB, som ellers alle skulle bære med sig.
- **Rumænien kan vælges som land.** Det manglede hidtil helt. Dermed
  genkendes rumænske adresser („Strada Victoriei 30"), postnumre med by
  („010061 București") og Cod Numeric Personal – sidstnævnte kun med
  stemmende kontrolciffer, så ikke ethvert trettencifret tal på en faktura
  markeres. Indtil da forblev postnummeret læseligt ved siden af det
  slørede stednavn i rumænske dokumenter.
- **„Rastrér side" i editoren.** Kan tekst ikke fjernes fra en PDF – det
  forekommer ved filer fra fremmede producenter –, erstattes siden nu
  efter ønske med sit aftryk: Teksten er dermed uigenkaldeligt væk, siden
  forbliver læselig og søgbar. Advarslen, der melder tilfældet, tilbyder
  trinnet straks som en knap; via „Værktøjer → Rastrér side" går det også
  af sig selv. Fortryd henter siden tilbage.
- **Grænsefladen findes nu også på kroatisk, græsk, litauisk, slovensk,
  japansk og koreansk.** Dermed er det atten sprog. Håndbog, FAQ og
  juridiske tekster er fuldstændigt med på alle seks. Betegnelserne i det
  rensede dokument følger hermed grænsefladen – af `[NAME_1]` bliver
  `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` eller `[氏名_1]`. **Ved græsk,
  japansk og koreansk står betegnelserne latinsk** – `[ONOMA_1]`,
  `[SHIMEI_1]`, `[IREUM_1]`. Grænsefladen forbliver i sit eget skrift; kun
  det, der skrives ind i dokumentet, er latinsk. Grunden er
  PDF-tegnsættet: Der ankom græske og japanske betegnelser tidligere som
  `[??_1]`, og dermed kunne navn ikke længere skelnes fra sted.
- **Ni lande kommer til, og syv eksisterende bliver fuldstændige.** Nyt
  genkendes ID-, skatte- og socialsikringsnumre samt adresser for
  **Kroatien, Slovenien, Grækenland, Litauen, Nordmakedonien, Rusland,
  Ukraine, Kina og Japan**. Ved de eksisterende lande er huller lukket,
  som vejede tungere: For **Holland** og **Portugal** fandtes hidtil slet
  intet personnummer – det hollandske BSN og det portugisiske NIF blev
  ikke genkendt, selv om de står på praktisk taget ethvert dokument fra
  disse lande. Polen får skattenummeret NIP, Danmark, Norge og Finland
  deres adresser, Canada sit postnummer. Dermed er det **35 lande**.

### Fjernet

- **For Linux findes der foreløbig ikke længere nogen pakke.** Kildekoden
  kører der, men tre ting, som denne vejledning lover, mangler under
  Linux: automatisk start, globale tastaturgenveje og – alt efter
  arbejdsmiljø – ikonet i bjælken. At levere en pakke, der kan mindre end
  beskrevet, ville være den forkerte vej. Windows og macOS er uberørte.

### Forbedret

- **Sagsnumre findes nu på alle sprog.** „Aktenzeichen 12/2026-AB" blev
  fjernet, „File reference 12/2026-AB" eller „Sygnatura 12/2026-AB" blev
  stående: Feltordene, som Maskuro genkender et sådant nummer på, fandtes
  kun på tysk. Nu kender det ækvivalenterne på tolv sprog – og som hidtil
  erstattes kun nummeret, betegnelsen foran bliver stående, så det i
  resultatet er genkendeligt, hvad der er fjernet der.
- **Maskuro belaster i tomgang omkring et halvt gigabyte mindre.** Ved
  start blev hidtil også ekstramodellen til den mere præcise genkendelse
  indlæst, så den første rensning ikke skulle vente på det. Efterprøvet
  kostede det 648 MB arbejdshukommelse og sparede 1,9 sekunder – og det
  kostede også dengang, hvor du blot åbner vinduet og lukker det igen.
  Modellen indlæses nu første gang, den skal bruges; statuslinjen melder
  det. Sprogmodellen indlæses fortsat ved start – det har
  udklipsholder-overvågningen brug for straks.
- **Aflæggelsesfladen kan nu også betjenes uden mus.** „Træk filer herhen"
  var en flade, der reagerede på klik – med tastaturet kom man ikke til,
  og en skærmlæser læste den op som en ramme med tekst i, ikke som det,
  den er. Den er nu en knap: Tabulatortasten springer til den, mellemrums-
  og enter-tasten åbner filvalget, og den, der er sprunget til, ser det på
  kanten. Via menuen „Fil → Vælg filer" gik det allerede tidligere, men
  det skulle man vide.
- **Navnet på den rensede fil bliver nu også læst op.** I fillisten står
  det som en anden, mindre linje under originalen – men det var der kun
  tegnet, og en skærmlæser nævnte kun originalen. Netop denne linje er
  bygget mod misforståelsen, at en kørsel var virkningsløs, fordi det
  urørte original ligger i mappen. Linjen lyder nu læst op „faktura.pdf,
  resultat: faktura_renset.pdf".
- **Betjeningselementer uden betegnelse siger nu, hvad de er til.**
  Symbolknapperne i fillisten, tegneknapperne i vinduet til efterretning
  og alle valg- og indtastningsfelter var navnløse for skærmlæsere – de
  blev annonceret som „knap" og „kombinationsfelt", uden hvad. Knapperne
  ved en linje nævner desuden filen med: I en liste med tyve poster hørte
  man ellers tyve gange den samme sætning.
- **Den, der betjener med tastaturet, ser igen, hvor han står.** Knappen
  „Rens" og symbolknapperne i fillisten er farvet, og dermed holdt den
  ramme op, som systemet ellers lægger om det tilsprungne
  betjeningselement – ved tabulering sprang blikket ud i det tomme. Begge
  har nu deres egen ramme, så snart de er i tur. Knapperne ændrer hermed
  ikke deres størrelse.
- **Syv skriftfarver var for blege, i begge fremtoninger.** Efterprøvet
  efter den sædvanlige norm (WCAG 2.1) lå de blege henvisningslinjer,
  sidenteksterne på aflæggelseszonen, vejledningens punkter og i det mørke
  udseende desuden det blå og det røde under grænsen på 4,5:1 – læselige
  ved godt lys og godt øje, ellers ikke. Alle er hævet; graderingen
  bevares, teksterne læses fortsat som sidenteksterne. Tre yderligere –
  farverne, hvori advarsler og succes meldes – holdt grænsen kun knapt og
  er hævet med: Den, der ikke læser dem, læser ikke oplysningen om, om
  noget gik galt. Synligt ændret har sig hermed kun knappen „Rens" i det
  mørke udseende: Den bærer nu mørk i stedet for hvid skrift, ligesom
  accentknapperne i Windows 11 også.
- **Hver linje i fillisten har nu sit eget kryds.** Hidtil måtte man først
  markere linjen og derefter klikke på „Fjern" – to trin for en
  bagatel. Krydset står til højre i linjen og kræver ét. Knappen „Fjern"
  nedenunder er dermed bortfaldet; den, der vil af med flere linjer på én
  gang, markerer dem og bruger posten i kontekstmenuen, der også siger,
  hvor mange det er. „Fjern alle" bliver. Fra listen fjernes altid kun
  linjen – aldrig en fil på disken.
- **Før AI-kontrollen står nu, om denne computer duer til det.** Hidtil
  stod der i vinduet kun, hvor stor modellen er. Den, der slog den til på
  en svag computer, mærkede først ved det første dokument, at det varer
  meget længe – efter 5,4 GB download. Nu nævner vinduet **på forhånd**
  arbejdshukommelse og fri plads og siger, hvad det betyder; **bagefter**
  måles hastigheden og angives i den størrelse, det drejer sig om: „Et
  ti-siders dokument tager på denne computer omkring 12 minutter." Er det
  for langsomt, fraråder programmet og tilbyder at slå niveauet fra igen –
  det forbyder intet.
- **Hastighedsmålingen kører nu på enhver computer.** Hidtil kom den kun,
  hvis grafikacceleration desuden var indrettet – den findes kun under
  Windows. På alle andre computere anslog programmet derfor varigheden ud
  fra en fremmed computer, og netop dér, hvor det er langsomt, ramte
  anslaget forbi.
- **Tyrkiske adresser findes nu også i scanning.** På et indscannet
  brevhoved forblev „34710 İstanbul" læseligt stående, mens den samme
  angivelse i teksten ved siden af forsvandt: Tekstgenkendelsen læser det
  tyrkiske İ uden sin prik, og mønsteret forventede et stort bogstav. Det
  samme gjaldt „Bağdat Caddesi".
- **Spanske adresser uden eget gadenavn findes.** „Gran Vía 5" blev
  stående, fordi mønsteret efter gadetypen forventede endnu et navneord –
  ved „Calle Mayor" findes ét, ved „Gran Vía" er typen selv allerede
  navnet. Det samme gælder nu for „La Rambla" og „Castellana".
- **I vinduet „Om dette program" står nu en gennemsigtighedshenvisning**
  om, at applikationen er udviklet med støtte fra kunstig intelligens. Den
  vedrører programmets tilblivelse, ikke dets arbejdsmåde: Der renses
  fortsat udelukkende på egen computer.
- **„Administrer sprog" viser nu de brugbare sprog først.** For halvdelen
  af de 48 dokumentsprog findes ingen egen sprogmodel; der genkender en
  flersproget erstatningsmodel navne kun svagt, i visse skriftsystemer
  slet ikke. Ved siden af hinanden i en liste så alle ligeværdige ud.
  Standarden viser derfor kun sprog med egen model – via „Vist" kan de
  øvrige til enhver tid vises, med en sætning om, hvad de kan og ikke kan.
  Intet falder væk, og den, der har indrettet et begrænset sprog, beholder
  det.
- **Spørgsmålet om et manglende sprog nævner nu udvejen.** Genkendes et
  sprog, som endnu ikke er indrettet, tilbød programmet hidtil kun
  „Indlæs" eller „Fortsæt uden". Genkendelsen kan dog ramme ved siden af –
  ved korte formularer og lister med lidt brødtekst afgør få ord. I
  vinduet står derfor nu, at man kan afbryde og vælge det rigtige sprog
  manuelt i stedet for at bruge „Genkend automatisk". Det sparer i
  tvivlstilfælde en download på flere hundrede megabyte til et sprog, der
  slet ikke er brug for.
- **Pladsholder-betegnelser taler nu grænsefladesproget.** „[NAME_1]",
  „[ADRESSE_2]" & co. stod hidtil altid på tysk, uanset hvilket sprog der
  var indstillet, eller på hvilket sprog dokumentet var forfattet. Nu
  følger de grænsefladesproget – på engelsk altså „[NAME_1]",
  „[ADDRESS_2]". Ikke dokumentsproget: Det er gættet ved „genkend
  automatisk" og til tider forkert; grænsefladesproget er det aldrig.
- **Færre forespørgsler ved efterretning.** Hvor resultatet gemmes, står
  nu permanent nederst i bjælken („→ kontrakt_renset.pdf", i
  værktøjstippet mappen) – et klik på det vælger et andet sted, uden at
  gemme med det samme. Tilbagespørgslen ved første lagring bortfalder
  dermed. Spørgsmålet „allerede behandlet – begynde forfra?" kan huskes
  for sessionen, og to henvisningsvinduer, der kun gav en oplysning, står
  nu i statuslinjen. Tilbage er de spørgsmål, der forhindrer en
  uigenkaldelig skade: det ugemte arbejde ved lukning og advarslen om
  ikke-fjernet tekst.
- **Resultatet siger nu, hvor selve scanningen ikke var læselig.** På et
  indscannet dokument læser enhedens tekstgenkendelse ikke alt korrekt –
  af „Solarstraße 9" bliver der så f.eks. „Solaret^aß« B". Hvad der
  således blev fejllæst, kan ingen kontrol længere finde: Det ligner for
  ethvert søgemønster bogstavsalat. Programmet kan intet ændre ved det,
  men benævner nu sådanne steder med sidetal – ofte sidder der stempler,
  brevhoveder eller håndskrevne tilføjelser. En henvisning, ingen
  advarsel: Ved et sat dokument udebliver den.
- **Fillisten viser nu, hvad resultatet hedder.** Under filnavnet står
  efter kørslen navnet på den rensede fil („→ kontrakt_renset.pdf").
  Hidtil stod det kun i protokollen bag „Detaljer", og den, der kiggede i
  mappen, fandt det urørte original. Kildens navn bliver stående – ellers
  ville det ikke længere være til at se, fra hvilken fil et resultat
  stammer.
- **Knapperne i en færdig linje er større og tydeligere.** Se, Efterret og
  „Vis i mappe" var flade symboler uden flade og gik under i listen –
  mens de efter kørslen er det eneste, man stadig klikker på.

### Rettet

- **På fremmedsproget grænseflade blev egne regler til sløring, maskering
  og hashning stiltiende tilsidesat.** Den, der havde fastlagt, at navne
  skulle sløres i stedet for erstattes, fik dem alligevel erstattet – så
  snart programmet ikke blev betjent på tysk eller engelsk. Indstillingen
  stod der, den virkede blot ikke, og i resultatet var forskellen ikke til
  at se. Berørt var ni af de tolv grænsefladesprog.
- **Indstillingen „Sprog for betegnelser" havde ingen virkning uden for
  tysk og engelsk.** „Tysk" og „Engelsk" kunne vælges, men i dokumentet
  stod fortsat grænsefladens sprog. Nu virker alle tre muligheder;
  standarden „som grænsefladen" leverer uændret det samme som hidtil.
- **I korte tekstuddrag blev navne stående – f.eks. i et kopieret
  mailcitat.** Den, der rensede et uddrag via udklipsholderen, fik der
  ofte kun mailadressen sløret, navnet nedenunder ikke. Afgørende var
  selve linjeantallet: Fra seks linjer genkendte programmet uddraget som
  en opstilling og fandt navnene, derunder ikke – et kopieret mailcitat
  har fem. En vilkårlig ekstra linje, f.eks. et emne, vippede resultatet.
  Nu er fire linjer nok, og i målingen forsvinder alle kontrollerede navne
  i stedet for en tredjedel. På længere dokumenter og på brødtekst har det
  ingen virkning.
- **Grafikaccelerationen af AI-kontrollen blev hidtil slået fra igen, så
  snart man havde indrettet den.** Efter indretningen måler programmet,
  om grafikken på denne computer virkelig er hurtigere end processoren –
  denne måling slog imidlertid altid fejl, uden at sige det, og
  resultatet „begge lige hurtige" afgjorde til fordel for processoren. Den,
  der havde indlæst de 65 MB, fik derefter mindre end før. Målingen kører
  nu; slår den fejl, ændrer den ikke længere noget.
- **Tidsanslaget regnede på enhver computer med fremmed hastighed.** Det
  bygger på samme måling; så længe den ikke kørte, gjaldt udviklingscomputerens
  værdi. „Omkring to minutter" kunne dermed på en langsom computer betyde
  en halv time.
- **AI-niveauet arbejder med en ny, betydeligt bedre sprogmodel**
  (Qwen3.5-9B i stedet for Qwen3-4B) og er ikke længere begrænset til
  tysk og engelsk, men arbejder på tolv sprog. Målt over kontrolkorpuset:
  lige så mange fundne angivelser som uden niveauet, men mindre end
  halvt så mange overflødige sløringer (75 → 31). Modellen er større (5,4
  i stedet for 2,4 GB) og kræver omkring dobbelt så meget regnetid; ved
  tilkobling indlæses den engangsvist, den gamle fjernes hermed.
- **Adresser på fransk, italiensk, spansk, portugisisk, polsk, tyrkisk og
  svensk fjernes nu fuldstændigt.** Hidtil forsvandt der kun gade- og
  stednavnet – husnummer og postnummer forblev læselige stående
  („[ORT_1] 28, 28013 [ORT_2]"). For disse sprog fandtes ingen egne
  adressemønstre; de er nu tilføjet.
- **Græsk og koreansk fandt slet ingen navne.** Ved græsk skyldtes det
  erstatningsmodellen – med den egen model, der nu kan indlæses,
  genkendes navne og steder rent. Ved koreansk skyldtes det programmet:
  Det forudsatte, at et navn begynder med et stort bogstav, og hangul
  kender ingen store bogstaver. Berørt var især korte enheder –
  tabelceller, formularfelter, listeposter.
- **En sprogmodel, der ikke kunne indlæses, afbrød rensningen.** I stedet
  for en fejlmeddelelse springer nu den flersprogede model til, og
  resultatet gør opmærksom på, at der er arbejdet med den svagere
  genkendelse. Vedrører for øjeblikket kinesisk og japansk, hvis modeller
  kræver en ordadskillelse, som programmet endnu ikke har med.
- **Et sprog med egen model gjaldt som installeret, så snart et hvilket som
  helst andet var indlæst.** Den, der f.eks. indrettede tyrkisk, fik
  dermed den flersprogede erstatningsmodel – og kinesisk, japansk,
  koreansk eller græsk stod herefter med sat flueben og „0 MB" i listen,
  selv om deres egen model manglede. De kunne derved aldrig efterindlæses
  og arbejdede permanent med den svagere erstatning. Nu viser listen den
  faktiske status samt indlæsningsstørrelse.
- **Et fejlslagent genkendelsesniveau tav.** Var „Udvidet genkendelse"
  eller „Maksimal genkendelse (AI)" slået til, men modellen kunne ikke
  udføres, arbejdede programmet videre uden niveauet – uden et ord om
  det. Resultatet så ud som ethvert andet, og kontakten stod fortsat på
  „til": Man holdt altså resultatet af grundniveauet for det bedste, der
  var at hente. Resultatet siger det nu og nævner begge dele – hvad der
  ikke blev kontrolleret, og hvordan modellen kan indlæses igen. Tilfældet
  er ikke sjældent: På visse computere slår AI-niveauet fejl ved
  indlæsning, hvis grafikacceleration mangler.
- **En fejl ved indlæsning af ekstramodellen afbrød hele rensningen.** Ved
  „Udvidet genkendelse" var kun modellens evaluering sikret, ikke dens
  indlæsning – og netop dér går det galt, hvis filen er beskadiget eller
  ikke passer til computeren. I stedet for en fejlmeddelelse findes der nu
  et resultat af grundniveauet samt henvisning.
- **Et sprog kunne ikke længere fjernes – og dermed heller ikke
  genindlæses.** Den, der i „Administrer sprog" fjernede fluebenet og
  overtog ændringen, læste „Tysk fjernet", men så straks fluebenet sat
  igen. Årsagen var overtagelsen fra programmappen: Ved en installation
  for alle brugere ligger sprogmodellerne skrivebeskyttede i programmappen,
  og programmet henter manglende derfra i stedet for at genindlæse
  hundreder af megabyte. Denne overtagelse kørte med ved hver adgang – og
  kopierede det netop slettede sprog tilbage i samme åndedrag. Den sker nu
  engangsvist; efterindlæste sprogmodeller bevares hermed. Desuden ser
  programmet efter, når det er slettet: Det, der ikke kunne fjernes,
  meldes nu som fejlslagen i stedet for „fjernet".
- **Ved en installation for alle brugere kunne efterindlæst ikke
  lægges.** Den, der installerer programmet for alle brugere, har det i
  „Programmer", og dertil må intet skrives uden administratorrettigheder.
  For sprogmodellerne var der allerede for længst indrettet et
  udvigested, for andet ikke:
  - **Sidevisningskomponenten** blev efter 290 MB download udpakket i
    programmappen og slog fejl der – uden at nævne en grund. Den ligger
    nu ved sprogmodellerne, hvor den ifølge hensigten altid burde ligge.
  - **Grafikacceleration** kan ikke vige ud: Den udskifter biblioteker i
    selve programmet. I stedet for først at indlæse og derefter lydløst
    slå fejl, siger programmet nu på forhånd, at det ikke går her, og
    hvad det betyder – den maksimale genkendelse arbejder videre, blot
    via processoren.
  - Et medleveret **sprog til tekstgenkendelse** kunne ikke fjernes: Det
    blev straks genoprettet fra programmappen. Samme årsag som ved
    sprogmodellerne, samme rettelse.
  - Ved fjernelse af et sprog kunne **sprogdata fra en fremmed
    Tesseract-installation** blive slettet. Berørt bliver nu kun den
    egne mappe.
  - Udvigestedet gjaldt hidtil kun under Windows. Et Linux-arkiv til
    `/opt` havde samme nød uden samme udvej.
- **Ved efterretning forsvandt en hel linje, selv om kun ét ord var
  rammet.** Den, der i en allerede renset fil slørede en pladsholder,
  mistede linjen, den stod i: Af „Kære fru doktor [NAVN_1]" blev der intet
  tilbage – og meldingen sagde dertil „ét ord fjernet fra dokumentet".
  Berørt var enhver fil, der allerede en gang havde kørt gennem programmet
  – altså netop det tilfælde, som efterretningen findes for. Den øvrige
  tekst bliver nu stående, på uændret sted.
- **„EMPLOYEES" over en navneliste blev selv sløret.** Samme tilfælde
  som „MITARBEITER" i 0.10.19, blot på engelsk – der var det forblevet.
  I versaler mangler sprogmodellen kendetegnet, og overskriften står
  over lutter rigtige navne. Navnene nedenunder bliver fortsat fundet.
  Ikke medtaget blev „staff": Det er et belagt efternavn, og posten ville
  tage hver „John Staff" med – samme afvejning som dengang ved
  „Arbejder".
- **Selskabsformen blev erstattet en anden gang.** På et indscannet
  brevhoved læste sprogmodellen „GmbH", adressen og postnummeret som
  **ét** sted. Adresse og postnummer skar sig derefter deres stykker ud,
  og tilbage blev selskabsformen som eget fund: I resultatet stod
  „[STED_1] [STED_2]", hvor „[STED_1] GmbH" var ment. Firmanavnet
  erstattes fortsat – kun den nøgne tilføjelse bliver nu stående, og
  resultatet læses som et brevhoved i stedet for som en
  udfyldningsøvelse.
- **Et tilrettet fund blev ikke kontrolleret på ny.** Årsagen til
  tilfældet ovenfor, og den rækker videre: Filtrene mod gættede fund
  arbejdede på det, som genkenderne **melder** – ikke på det, der bliver
  tilbage efter overlapningsopløsningen. Bliver et langt fund beskåret
  af en stærkere genkender, er brudstykket en anden tekst end den
  vurderede, og ingen så på det igen. Nu gør de.
- **„Du bruger den nyeste version" – selv om det slet ikke kunne
  undersøges.** Den, der havde indstillet opdateringskanalen til
  „Forhåndsvisning (beta)" eller „Stabil – anbefalet", fik denne
  oplysning, selv om der på disse kanaler hidtil slet intet var
  udkommet. Nu siger programmet netop det – og foreslår at vælge en
  anden kanal i indstillingerne.
- **At lukke vinduet under indlæsning fik en tråd til at gå ned.** Den,
  der startede Maskuro og straks lukkede vinduet igen, mens
  sprogmodellerne stadig blev indlæst, fik en fejlrapport i
  protokollen: Indlæsningen meldte sig ved et vindue, der ikke længere
  fandtes. Synlige følger havde det ingen, men i protokollen stod et
  nedbrud, hvor blot nogen var hurtigere end programmet.
- **Resultatet ses nu på, ikke kun læses efter.** Hidtil gjaldt en side
  som ren, når værdien ikke længere stod i teksten. På en scanning er
  det intet bevis – der er den synlige tekst et billede. Til sidst ses
  der derfor efter, om fladen i resultatet virkelig er sløret; står der
  stadig lyst papir, siger rapporten det udtrykkeligt i stedet for at
  melde „erstattet".
- **En erstattet angivelse blev stående i billedet.** Stod værdien på et
  billede – et indscannet brevhoved, et stempel, en hel indscannet
  side –, blev den ganske vist fjernet fra dokumentteksten, men var
  fortsat til at **se**: Hvad mennesket læser, er der billedpunkter.
  Rapporten meldte alligevel „erstattet". Nu sløres fladen i billedet,
  uanset hvilken strategi der er indstillet, og pladsholderen står lys
  på denne grund – grimt, men ærligt, og tilknytningen bevares. Kan et
  billedformat ikke redigeres, siger resultatet det nu udtrykkeligt i
  stedet for at se rent ud.
- **På en scanning manglede pladsholderen helt.** Tekstlaget på en
  indscannet side tegnes usynligt, og en pladsholder, der blev indsat i
  det, arvede dette: sat, men ikke synlig. På fundstedet stod der
  derefter intet.
- **En tekstgenkendelse, der slet ikke kunne køre, gjaldt som
  bestået.** Manglede sprogfilen, eller brød genkendelsesmaskinen
  sammen, meldte rapporten „billede(r) … blev kontrolleret via
  tekstgenkendelse (0 fundsted(er))" – altså en kontrol, der aldrig fandt
  sted. Ved en scanning er det den eneste kontrol overhovedet: En
  kontrakt med læselig adresse i sidebilledet gjaldt dermed som færdig.
  Nu siger rapporten, at intet blev kontrolleret, og hvorfor.
- **Sprogfilen blev søgt i den forkerte mappe.** Lå der i den egne
  sprogmappe andre sprog end dokumentets, fik genkendelsesmaskinen netop
  denne mappe forelagt og slog fejl – selv om det passende sprog lå ved
  siden af. Der søges nu efter **sproget**, ikke mappen.
- **Advarslen om ikke-fjernet tekst rådede til noget, der ikke findes.**
  Den henviste til „Slør som PDF" – det genererer imidlertid en
  PDF-visning af *Office*-filer og er slet ikke til rådighed ved en PDF.
  Den, der ville følge advarslen, søgte forgæves. Nu står der knappen,
  som klarer sagen.
- **I editoren havnede bjælker og pladsholdere ved siden af det markerede
  sted.** Berørt var hver PDF, hvori en linje slutter på en
  delingsstreg, og ordet fortsætter i den næste – ved scanninger falder
  det især i øjnene, fordi kontrakttekster er gennemgående delt. De to
  linjehalvdele gjaldt som *ét* ord, der rækker på tværs af satsspejlet,
  og enhver ramme i nærheden overtog denne udstrækning. Selve
  genkendelsen ændres ikke af dette: Målekorpuset leverer samme resultat
  som før.
- **Editoren advarede om, at teksten stod „stadig i dokumentet", selv om
  den var fjernet.** Forekom det samme ord flere gange på en side – i
  kontrakter reglen –, meldte selvkontrollen efter hvert indgreb en
  fejl. Den tæller nu forekomsterne i stedet for blot at se efter, om
  ordet stadig står et sted. Ved en ægte fejl advarer den uændret.
- **Resultatfilen hed på ethvert sprog „_bereinigt".** Meningen var altid,
  at navnetilføjelsen følger grænsefladesproget – på engelsk gjorde den
  det også ("_cleaned"), i de øvrige seksten sprog ikke. Den, der brugte
  programmet på finsk, fik „asiakirja_bereinigt.pdf". Nu hedder filen
  „asiakirja_puhdistettu.pdf", på japansk „書類_除去済み.pdf" og så videre –
  hver gang med det ord, som samme grænseflade bruger i sin
  færdigmelding. Den, der har indstillet en egen tilføjelse, beholder den.
- **„Administrer sprog" betegnede sig altid tysk.** I listen over de 48
  dokumentsprog stod de tyske navne, uanset hvilken grænseflade der var
  indstillet: En finsk bruger læste „Chinesisch". Nu står der navnet på
  dets eget sprog og derefter egennavnet – „Kiina (中文)". Egennavnet er
  tilsigtet: Den, der genkender sproget på dets eget navn, finder det også,
  når det finske ord ikke siger vedkommende noget.

## 0.10.19 – 12. august 2026

### Forbedret

- **Kontekstmenupunktet taler nu dit sprog.** Hidtil stod der på ethvert
  system den tyske ordlyd – også på et engelsk Windows. Nu følger den det
  indstillede grænsefladesprog, og den, der skifter sprog, får punktet
  omdøbt med det samme, uden at geninstallere. (Windows; på macOS og Linux
  er menunavnet samtidig et filnavn – det kommer senere.)
- **Editoren husker, i hvilken visning du sidst arbejdede.** Den, der bruger
  sidevisningen, får den af sig selv ved næste dokument – uden at skulle
  slå den til hver gang. Den, der aldrig har brugt den, mærker intet: Den
  genoprettes kun, hvis den nødvendige byggesten allerede er indlæst, der
  eftérindlæses aldrig noget for det.

### Rettet

- **„MEDARBEJDERE" over en navneliste blev selv sløret.** I
  medarbejderfortegnelser og organisationsdiagrammer forsvandt overskriften
  som et formodet navn – den står der over lutter rigtige navne, og i
  store bogstaver mangler sprogmodellen sit kendetegn. Navnene nedenunder
  bliver fortsat fundet.
- **Mængdeangivelser blev opfattet som adresser.** I fakturaer,
  følgesedler og lagerlister forsvandt angivelser som „3390 Protokol",
  „1030 Beløb" eller „3390 Lager" som et formodet postnummer med by –
  firecifret ligner ethvert antal et østrigsk postnummer. Står der bag
  tallet et ord, som applikationen kender som sagord, afdeling, aktivitet
  eller feltbetegnelse, bliver det nu stående. Rigtige stedangivelser er
  uberørte, også dem, der samtidig er et sådant ord („4692 By"). Ikke løst
  er dermed det tilfælde, at der bag tallet står et ganske almindeligt ord
  („3390 Reol") – det kræver en postnummerfortegnelse.
- **Hjælpen nævnte et menupunkt, der ikke findes.** Vejledningen, billedet
  og meddelelsen ved installationens afslutning talte om „Rens dokument
  for AI"; punktet i kontekstmenuen hedder derimod „Fjern personoplysninger".
  Den, der fulgte hjælpen, søgte forgæves. Alle tre steder nævner nu
  menupunktet, som det virkelig hedder.
- **„Start med systemet" kunne ikke slås fra.** Den, der under
  installationen havde afkrydset „Start med Windows", så alligevel et tomt
  flueben i indstillingerne – og værre: Til- og frakobling i applikationen
  var uden virkning, programmet startede fortsat med Windows. Årsagen var
  to steder, hvor Windows kigger efter startprogrammer; applikationen
  kendte kun det ene. Nu tæller begge, kontakten viser den sande tilstand
  og virker i begge retninger. Der er også taget højde for: Den, der slår
  punktet fra i jobliste, ser det nu i applikationen – og den, der slår det
  til der igen, ophæver dermed frakoblingen.
- **Overskrifter over navnelister blev slørede.** „DELTAGERLISTE
  VÆRKSTEDSSAMTALE" eller „MEDARBEJDEROVERSIGT INDENDØRS SERVICE" over en
  liste af personer forsvandt som et formodet navn. I store bogstaver
  mangler sprogmodellen sit bedste kendetegn, og på tysk skrives ethvert
  navneord med stort – „Teilnehmerliste Werkstattgespräch" ligner så
  „Anna Huber". Sammensætninger på `-liste`, `-dienst`, `-gespräch`,
  `-sitzung` og `-besprechung` bliver nu stående. Grundordene alene gælder
  fortsat som navn: *Liste* og *Dienst* er belagte efternavne,
  *Teilnehmerliste* er ikke et.
- **Lodret satte angivelser fik en ulæselig pladsholder.** Sagsnumre i
  sidemargenen, sagsbehandlerforkortelser ved indbindingskanten, lodrette
  tabelhoveder: Sådanne angivelser blev fundet og fjernet, men
  pladsholderen kom ud på tværs af teksten, sammenpresset til en til to
  punkter og til tider ud over papirkanten. Nu følger den teksten –
  lodret, i læsestørrelse og i samme retning, som angivelsen stod. Det
  samme gjaldt sider, der efterfølgende var drejet (vandret skrevet tekst
  med registreret sidedrejning, som visse udskrivningsprogrammer leverer);
  også der står pladsholderen nu, som man ser siden. „Kære fru doktor
  Anneliese Berger" gav kun „Anneliese" som navn – „Berger" blev stående i
  dokumentet. Det samme ramte ethvert navn med mellemnavn („Fru Anna Maria
  Berger"). Årsagen var reglen for navnet efter en tiltale: Den havde to
  ordpladser, og en titel eller et mellemnavn brugte den første. Med „Dr."
  gik det aldrig galt – punktummet bryder reglen, og sprogmodellen fangede
  hele navnet. Nu springes titler over uden at koste en plads, og navnet må
  bestå af tre dele. En rolle **efter** navnet går fortsat ikke med: „Fru
  Anna Huber direktør" erstatter navnet, ikke rollen.
