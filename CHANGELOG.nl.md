Wat er van versie tot versie verandert – beschreven vanuit het oogpunt van de
toepassing, niet van haar binnenwerk. Wie wil weten *waaruit* ze is gebouwd,
vindt dat in [LIZENZEN.md](LIZENZEN.md); hier staat wat er voor het werk
ermee verandert.

De nummering volgt de gebruikelijke telwijze: het **eerste** getal verandert
wanneer iets niet meer werkt zoals voorheen, het **tweede** bij nieuwe
mogelijkheden, het **derde** bij foutcorrecties.

## 0.10.52-alpha.20260903 – 3 september 2026

- Een batch van meer dan vier bestanden loopt na antwoorden in meerdere
  voorbeeldvensters niet meer vast. De volgende documenten worden nog steeds
  op de achtergrond voorbereid; na een antwoord wordt het bijbehorende
  bestand nu steeds correct afgerond en komt de volgende plaats in de batch
  vrij.
- De vergelijking van korte bedrijfsaanduidingen in pdf's is nu beperkt tot
  herkende afbeeldingstekst. In gewone paginatekst zorgt een lange
  modeltreffer over meerdere regels er daardoor niet meer voor dat een
  gelijkluidend los woord elders extra wordt zwartgemaakt.

## 0.10.51-alpha.20260903 – 3 september 2026

- De lijst met wijzigingen verschijnt nu in de eigen taal – op
  maskuro.com/neuigkeiten en in het programma onder ‘Wijzigingen’, evenals in
  ‘Wat is er nieuw’ na een update. Tot nu toe stond daar in alle achttien
  taalversies Duitse tekst onder een vertaalde kop. Waar een vertaling nog
  ontbreekt, blijft de betreffende versie in het Duits staan in plaats van te
  verdwijnen; de versielijst is overal hetzelfde.

## 0.10.50-alpha.20260903 – 3 september 2026

- Terugkerende bedrijfslogo's in PDF's worden consistent opgeschoond, ook
  wanneer de tekstherkenning het schrift op een pagina anders leest of
  het ronde beeldmerk helemaal overslaat. Een uitdrukkelijke afwijzing in
  het voorbeeld blijft daarbij bindend en kan door geen latere nalezing
  worden opgeheven.
- Valutaloze prijzen in gescande tabellen worden ook dan volledig
  gezwart wanneer tabelkop en waarden in verschillende overlappende
  PDF-afbeeldingen zitten. Hoeveelheden, uren, gewichten en percentages
  blijven staan; ver uiteenliggende getallen worden niet meer per
  ongeluk tot één bedrag verbonden.
- De handtekeningzoektocht vangt nu ook overtuigende zwakke blauwe
  handschriften en smalle rode signatuurkortingen op. Gestippelde
  diagrammen, meetcurven, stempels, logo's en brede rode
  bewerkingsmarkeringen blijven van deze strikte nalezing uitgezonderd.
- Zwartingen in gedraaide, gespiegelde, geschuinde of bijgesneden
  PDF-afbeeldingen treffen nu het werkelijke beeldpolygoon. Technische
  rollen in werkzaamhedenposten, voertuig- en bandzakelijke waarden
  evenals technische „compensatie" worden tegelijk strakker afgebakend
  tegen valse treffers; uitdrukkelijk beschreven contactrollen en
  telefoonnummers blijven beschermd.
- De visuele controle vóór het opslaan van een PDF laat het venster niet
  meer bevriezen: bij grote documenten met veel vindplaatsen stond het
  tot nu toe meerdere seconden zonder terugkoppeling; nu toont een
  aanwijzing dat er wordt gecontroleerd, en het venster blijft tekenen.
- Het terughalen van een waarde uit een afbeelding in de
  nabewerkingseditor leest elke originele afbeelding nog maar één keer
  met tekstherkenning; tot nu toe liep die bij elke verdere terughaling
  voor dezelfde afbeeldingen opnieuw.
- Het naladen van het hoog-niveau en het handtekeningmodel heeft
  nauwelijks nog geheugen nodig: het 596-MB-pakket werd tot nu toe
  volledig in het geheugen gehouden, gecontroleerd en daar uitgepakt –
  ruim één gigabyte piek in het lopende programma, op computers met
  8 GB het moment waarop alles begon te haperen. Nu vloeit het
  blokgewijs naar de schijf en wordt daar gecontroleerd en uitgepakt.
- Het zoeken in de nabewerkingseditor laat grote PDF's niet meer
  bevriezen: de eerste letter in het zoekveld las tot nu toe alle
  pagina's in één keer in – bij 200 pagina's stond het venster twee
  seconden stil, en na elke zwarting nog eens. De pagina's worden nu
  stukje voor stukje gelezen; tot dan staat „Wordt gelezen …" in de
  teller, het resultaat is hetzelfde.
- Gerasterde PDF-pagina's – na een tekstherkenning of wanneer een tekst
  niet netjes te verwijderen was – worden aanzienlijk kleiner en zonder
  beeldverlies opgeslagen: in plaats van altijd als JPEG wordt elke
  pagina ook verliesvrij gecodeerd, en de kleinere versie komt in het
  bestand. Een opgeschoonde scan krimpt zo van 248 naar 48 KB, het
  oefendocument met tekstherkenning van 913 naar 702 KB; tekst blijft
  haarscherp.
- Nageladen modellen (hoog-niveau, handtekeningen, gezichten, tweede
  tekstherkenning) worden na tien minuten zonder opschoning weer uit
  het geheugen ontslagen. Tot nu toe bleven ze geladen tot het einde van
  het programma – wie eenmaal een handtekeningzoektocht en het
  hoog-niveau had gebruikt, hield blijvend meer dan twee gigabyte vast.
  De volgende run laadt ze binnen één tot twee seconden opnieuw; de
  statusregel meldt het.
- PowerPoint: de generieke namen van diaindelingen en diamasters
  („Leeg", „Titeldia") worden niet meer als gegeven vervangen. „Leeg"
  is ook een plaats en werd in elke Duitse en Engelse presentatie ten
  onrechte gezwart; opgeschoond worden alleen nog de met de hand gegeven
  namen van de dia's zelf.
- In PDF's trekt het regelgladstrijken niet meer de kop van de
  volgende regel in een vondst: het nummer van het volgende
  lijstpunt achter een datum gold als telefoonnummer, een veldkop zoals
  „Kenmerk" of „Ordernummer" achter een getal als postcode met plaats,
  en de plaatsregel onder het adres verdubbelde de plaats. De telkens
  juiste, kortere vondst werd daardoor verdrongen. Over 132 corpus-PDF's
  blijven van 24 extra gladstrijkvondsten de twee echte over; in het
  praktijkcorpus dalen de valse alarmen van 29 naar 21 bij gelijke
  vondstquote.
- „PDF-map doorzoeken en zwarten" in de nabewerkingseditor blokkeert het
  venster niet meer: de run werkt op de achtergrond, voortgang en
  annuleerknop reageren, en menu's of tabbladen kunnen niet meer midden
  in een half voltooid bestand worden bediend.
- Gescande pagina's met vindplaatsen worden bij het zwarten nog maar
  één keer opnieuw geschreven in plaats van twee keer: tot nu toe vulde
  het programma de kaders van de vindplaatsen en die van de
  motiveringen in twee doorlopen, en de tweede comprimeerde de net
  opnieuw opgeslagen scanafbeelding nog een keer. Dat bespaart tijd bij
  grote scans en een kwaliteitsverlies in de afbeelding.
- Bladeren, zoomen en de miniaturen in de nabewerkingseditor reageren
  sneller: elke gerenderde pagina ging tot nu toe als PNG door een
  compressie en meteen weer terug, alleen om te worden weergegeven –
  bij schermen met hoge resolutie zo'n tiende seconde per pagina. De
  afbeelding komt nu direct aan, beeldpunt voor beeldpunt hetzelfde.
- De visuele controle vóór het opslaan van een PDF („uitvoerproef") is
  ongeveer driemaal sneller, bij gelijk resultaat.
- Het hoofdvenster verschijnt nog eens ongeveer een kwart seconde
  eerder: de controle of de tekstherkenning op deze computer gereed is,
  liep bij het opbouwen van het venster – op de Mac inclusief een
  proefverzoek aan de systeemherkenning – en de instellingenpagina van
  de extra componenten vroeg daarbij de stand van alle 48 talen op.
  Beide gebeuren nu op de achtergrond respectievelijk pas wanneer de
  taallijst echt wordt geopend; tot dan staat er „Tekstherkenning wordt
  gecontroleerd …".
- Na een handtekeningzoektocht gebruikt het programma ongeveer 300 MB
  minder geheugen: het herkenningsmodel stond tot dan toe dubbel in het
  geheugen – eenmaal om zijn echtheid te controleren, eenmaal om te
  rekenen. Gecontroleerd wordt het nog steeds, alleen zonder de tweede
  kopie.
- De tekstherkenning in PDF's is merkbaar sneller geworden: voor elke
  veldkop van een pagina („Geboortedatum:", „Belastingnummer:") werd tot
  nu toe per soort gegeven een eigen proef door de herkenning gestuurd –
  op elke pagina opnieuw, ook als dezelfde kop al tien pagina's eerder
  stond. Het antwoord wordt nu onthouden; een tweepagina's tellend
  bestek stelde zo 324 vragen, nu nog de verschillende. De vondsten
  zijn dezelfde.
- Grote tabellen worden weer in seconden in plaats van minuten
  opgeschoond: bij de anonimiserende werkwijze – de standaard – werd de
  vergelijking van al bekende waarden met elke verdere cel trager,
  omdat een tussengeheugen bij elke treffer werd weggegooid en opnieuw
  opgebouwd. 5.000 cellen kostten daarvoor ongeveer 18 seconden, nu een
  halve; het resultaat is teken voor teken hetzelfde.
- Het hoofdvenster verschijnt nog eens duidelijk sneller: de landenlijst
  van de instellingen trok bij het opbouwen van het venster de hele
  herkenningsbibliotheek naar voren – ongeveer 0,7 seconden op de Mac,
  op Windows navenant meer –, hoewel daarvoor alleen de namen van de
  landen nodig zijn. De lijst komt nu uit een lichte catalogus; de
  bibliotheek laadt zoals bedoeld op de achtergrond, terwijl het
  venster al staat. Dat geldt ook na elke taal- of themawissel die het
  programma opnieuw start.
- Het documentlaboratorium voert aangesneden veldkoppen, plaatselijke
  waardeschaduwen en sterke scanbijsnedes nu volledig door PDF-, DOCX-
  en ODT-containers. De matrix omvat 680 bestanden uit 40
  documentfamilies en 17 containerassen. Maskuro verwijdert in de
  nieuwe evenals de volledige basis- en kenmerkprofielen alle
  doelgegevens, zonder gemeten vals alarm, beschadigde
  behoudswaarde of afbreking.

- Meermaals gebruikte scans worden nu via elke zichtbare plaatsing
  gecontroleerd en opgeschoond: het documentlaboratorium deelt hetzelfde
  beeldobject over verschillende pagina's, groottes en rotatiestanden
  in PDF en verwijst meermaals naar hetzelfde beelddeel in DOCX en ODT.
  Technische ODT-kadernamen zoals „Formulierscan klein liggend" gelden
  niet meer als persoon; vrije namen en plaatsen met vergelijkbaar
  begin blijven beschermd. Een algemeen formulierraadsel van de
  afsluitende PDF-paginaloop kan op een al onafhankelijk gelezen
  beeldvlak geen groot adres-vals-alarm meer veroorzaken. De 120 nieuwe
  containers bereiken in basis- en kenmerkprofiel alle respectievelijk
  813 en 840 doelgegevens zonder vals alarm, behoudsschending of
  afbreking; de volledige 800-bestanden-kenmerkkeuring bevestigt
  5.600/5.600.

- Het Duitse OCR-laboratorium omvat nu 560 scans uit 40
  documentfamilies. Nieuwe varianten snijden veldkop- en paginaranden
  aan of leggen een schaduw direct over een waarde. Maskuro beschermt
  daarbij ook namen, adressen, geboortedata, medische sleutels en
  beschreven kenmerken met deels beschadigde beschrijving. Tegelijk
  worden formulierveldresten, officiële koppen evenals zakelijke
  rechts- en informatiebegrippen niet meer als personen of plaatsen
  vervangen. De volledige basis- en kenmerkprofielen bereiken
  3.794/3.794 respectievelijk 3.920/3.920 doelgegevens zonder gemeten
  vals alarm of afbreking.

- De automatische PDF-beeldselectie verwijdert grootschalige
  productfoto's, energielabels en portretreeksen niet meer alleen
  omdat ze aan de bovenrand van de pagina beginnen. Echte platte
  kop-/voetafbeeldingen en briefkoppen die aan de bladrand beginnen,
  vallen verder wel. In personeelsregisters worden namen nu ook dan
  herkend uit structureel herhaalde vermeldingen wanneer de zichtbare
  documenttitel alleen als afbeelding aanwezig is. De herkenning is
  niet meer toegesneden op twee concrete rolwoorden en de afkorting
  „DW": één tot vier omgebroken rollen evenals „Doorkiesnummer",
  „Toestel", „Ext." en „Extension" worden uit de gemeenschappelijke
  bouwvorm afgeleid. Rollen en sectiekoppen blijven staan, ook wanneer
  het taalmodel na de overlappingsoplossing maar één rolbijvoeglijk
  naamwoord overlaat. Horizontale rolrasters gelden niet meer ten
  onrechte als naamkolommen. Plakt de pagina-OCR meerdere kaarten aan
  elkaar tot één extreem breed woord met interne hoofdletters, dan
  scheidt een strikte plaatselijke tegenblik de werkelijke woordkaders;
  daardoor blijft noch een enkele naam noch een brede foutbalk over.
  Herhaalde meerregelige bedrijfslogo's worden aan de hand van een al
  bevestigde identieke pixelsjabloon ook op pagina's zonder bruikbare
  OCR-tekst en bij tot twee pixels afwijking gezwart; kortere
  plaatselijke tweede OCR-lezingen mogen tegelijk geen groter kopgebied
  meer als verzonnen naam toevoegen. Paginanummers vóór een
  bedrijfsbriefkop horen niet meer bij de organisatienaam, numeriek
  beginnende echte merknamen blijven beschermd. Meerdere gemeten
  product-, vak- en formulierwoorden worden niet meer als personen
  voorgesteld.

- De handtekeningzoektocht loopt bij PDF's pas na de OCR-beeldopschoning,
  bezoekt ook pagina's zonder gewone teksttreffer en herrekent
  vondstkaders van gedraaide pagina's correct terug naar de
  documentruimte. Dichte productfoto's worden niet meer als
  handtekening gezwart. Boven eenduidig beschreven handtekeningvelden
  sluit een strikte streep-terugval dunne modelgaten; lege lijnen met
  voorgedrukte datum lokken hem niet uit. Pure scans met uitsluitend
  OCR-/handtekeningvondsten breken in deze fase niet meer af wegens een
  pas in de teksttak geladen beeldzwarter.

- Veel gelijktijdig geopende documenten blijven in de
  nabewerkingseditor onderscheidbaar: de tabbladen krimpen niet meer
  tot een kaal beletselteken, en een lijstknop rechts toont alle
  volledige bestandsnamen onder elkaar. Tabbladen laten zich door
  slepen herordenen en met hun kruis uit dezelfde lijst nemen als in
  het hoofdvenster; niet-opgeslagen werk wordt daarbij nog steeds eerst
  opgehelderd. Een rechtsklik biedt bovendien „Sluiten", „Andere
  tabbladen sluiten" en „Tabbladen rechts sluiten".

- Een kortstondige Windows-blokkade door virusscanner of zoekindex laat
  de kant-en-klaar geladen taalmodel- respectievelijk woordenboekmap
  niet meer bij het afsluitend plaatsen met „Toegang geweigerd"
  mislukken. Maskuro probeert deze laatste mapwissel nu kort opnieuw.

- Het Duitse documentlaboratorium controleert containers nu ook met
  wisselende PDF-paginarotatie, onafhankelijk gedraaide PDF-afbeeldingen
  evenals geschaalde en bijgesneden tabelafbeeldingen in DOCX en ODT.
  Veldwaarden in zichtbaar gedraaide afbeeldingen worden weer volledig
  herkend, technische kolombenamingen niet meer als plaatsen vervangen
  en namen met gemeenschappelijke achternaam niet meer door de
  consistentienacontrole in dubbele deeltreffers opgesplitst. De naar
  320 bestanden verdubbelde matrix bereikt met ingeschakelde datum-,
  geld- en medische herkenning 2.240/2.240 doelgegevens zonder gemeten
  vals alarm of afbreking.

- Meerdere-pagina's-tellende beeld-PDF's, gemengde tekst-/beeld-PDF's en
  in DOCX of ODT ingebedde scans worden nu in een eigen
  160-bestanden-laboratorium over alle 40 Duitse documentfamilies
  gecontroleerd. Technische ODT-kadernamen en beschreven apparaatcodes
  worden niet meer als plaatsen vervangen; echte namen, plaatsen en
  adressen in dezelfde structuren blijven beschermd. Met ingeschakelde
  medische of geldherkenning worden bovendien een direct volgende
  dosering respectievelijk een betalingsinterval volledig verwijderd.
  Container-, tekstbasis-, tekstkenmerk- en OCR-kenmerklopen bereiken
  samen hun respectievelijke volledige standen zonder gemeten vals
  alarm of afbreking.

- De veiligheidscontrole vóór het opslaan toont opvallende PDF-plekken
  nu als afzonderlijk aanwijsbare lijst. „In editor controleren" opent
  precies de gekozen pagina en markeert het gebied; overlappende
  deeltreffers op dezelfde plek verschijnen nog maar één keer. De
  nieuwe bedieningsteksten zijn in alle 17 vertaalde interfacetalen
  volledig aanwezig.

- Markdown-bestanden behouden bij het vervangen hun verwijzings-,
  markerings- en voetnootsyntaxis. Maskuro leest daarvoor een
  tekengelijk lange versie zonder Markdown-markeringen; onderstrepen in
  e-mailadressen, rekensterretjes en gewone verwijzingen zonder
  persoonlijk gegeven blijven ongewijzigd.

- Meerdere handgeschreven vermeldingen op dezelfde PDF-pagina worden nu
  in tot drie doorlopen gezocht. Al gevonden trekken worden alleen in
  het werkbeeld verborgen, zodat ze zwakkere handtekeningen niet meer
  verdringen; op gedraaide pagina's komen de zwartingsvlakken weer op
  de zichtbare vindplaats terecht. Beeldvullingen van eerdere
  veiligheidsfasen blijven bij het aansluitende terugschrijven behouden.

- „Alle instellingen terugzetten" omvat nu ook „Tekst in afbeeldingen".
  Is de OCR-component niet beschikbaar, dan blijft de schakelaar
  technisch uit, zonder ten onrechte als afwijkend van de
  uitleveringsstand te worden gemarkeerd.

- Grote beeldfragmenten aan de bovenrand van de pagina gelden niet meer
  alleen wegens hun plaats als koptekst. Daardoor blijven met name op
  afbeeldingen gebaseerde artikelbeschrijvingen en tabelinhoud
  behouden. Nieuw herkende, typenauwkeurige e-mail- en formuliervondsten
  worden bovendien ook op een al gecontroleerd beeldvlak niet meer uit
  de afsluitende visuele controle gefilterd.

- Technische positie- en artikelregels in klimaat- en elektro-offertes
  worden strikter van personen, plaatsen en organisaties onderscheiden.
  Dat betreft onder andere kabeltypes, AC-voeding, positienummers
  evenals productcodes in hoofdletters; echte namen en adressen blijven
  beschermd.

- De controle van echte opgeschoonde PDF's verwart prijsonderdelen zoals
  `1 699,59` niet meer met telefoonnummers en snijdt uit een volledige
  datum zoals `08.05.2025` geen vermeende kaartaanduiding meer.
  Namen achter een aanhef eindigen bij de regelafbreking in plaats van
  in de volgende straat; plaatsnamen in bijlagen-bestandsnamen worden
  beperkt tot de daadwerkelijke plaats. Voertuigkleuren, technische
  statuswaarden, branchebenamingen en product-rechtsvormen blijven
  eveneens behouden. Beschadigde plaatshouderlezingen zoals `|PLLZ`
  worden bij een tweede OCR-doorloop niet opnieuw als persoonlijk
  gegeven behandeld.

- Zijwaarts opgeslagen PDF-afbeeldingen krijgen bij de afsluitende
  visuele controle een extra blik in hun ongewijzigde beeldstand. Deze
  mag uitsluitend waarden nazwarten die Maskuro op dezelfde pagina al
  zeker heeft herkend. Zo wordt bijvoorbeeld een klein gedraaid
  adresstempel volledig afgedekt, zonder nieuwe woorden uit
  beeldkoppen of technische tekeningen als persoonsgegevens te
  verzinnen.

- In OpenDocument-teksten worden de auteursinitialen van een notitie
  (opmerking) nu samen met de auteur geleegd. LibreOffice legt ze naast
  de volledige naam als eigen korte vorm vast en toont precies deze aan
  de paginarand; tot nu toe bleef daar „SO" staan, terwijl „Sieglinde
  Ortner" ernaast al lang een plaatshouder was. Geleegd wordt alleen
  als de auteur daadwerkelijk werd vervangen – de notitie van een
  afdeling behoudt haar kenmerk.

- In Italiaanse zakelijke brieven gelden de standaardwendingen aan het
  begin van de zin niet meer als naam of plaats: „Restiamo a
  disposizione", „Rimaniamo", „Attendiamo", „Alleghiamo",
  „Comunichiamo" en „Auguriamo buon lavoro" bleven tot nu toe hangen
  als vermeende persoon of plaatsaanduiding. Echte namen op dezelfde
  plek („Rossi Mario") worden verder herkend.

- Tweekoloms-scans beschermen beschreven kenmerken en plaatsaanduidingen
  nu ook wanneer de tekstherkenning eerst alle veldkoppen en daarna
  alle waarden levert. De toewijzing volgt de zichtbare pixelregel en
  werkt ook bij 90 graden gedraaide pagina's. Nauw gescheiden delen van
  een pas- of contractkenmerk worden gezamenlijk gezwart; beschreven
  geboortedata, ICD- en PZN-sleutels zijn eveneens afgedekt, volgende
  zakelijke woorden blijven staan. Korte namen en gebruikersnamen
  worden op exacte velden beschermd; in meerdere OCR-woorden
  opgesplitste e-mailadressen alleen bij nauwe nabijheid en volledige
  e-mailgrammatica. Een veldgebonden correctie van verwarbare tekens
  evenals het plaatselijk nalezen van een nog leeg persoonsveld sluiten
  beschadigde en gedraaide scans, zonder zakelijke velden of al bezette
  waarden uit te breiden. Veiligheidsranden volgen de woordgrootte, en
  het kenmerkprofiel neemt direct aangrenzende doseringseenheden en
  betalingsintervallen mee. Licht scheef ingevoerde formulieren worden
  uit meerdere gelijkgerichte OCR-regels geometrisch teruggeprojecteerd;
  afrondingsruis of tegenstrijdige getuigen volstaan niet. Korte
  lettervoorvoegsels blijven behouden vóór een koppeltekenkenmerk, en
  een volledige beschreven adresvondst vervangt alleen zijn
  gelijksoortige straat-deelvondst. Een verkeerd gelezen rolveldkop
  vervalt uitsluitend in een door minstens drie bekende koppen bezette
  formulierkolom; chatnamen blijven beschermd. Een krappe randbijsnede
  en een plaatselijke overbelichting met diagonale lichtreflectie
  vullen de beeldmatrix aan. Over meerdere formulierregels reikende
  persoons-, plaats- en bedrijfsvondsten worden in een meermaals bezette
  veldkolom tot de betreffende waarde beperkt. Een technische
  positiewaarde vervalt alleen met positiekop en passende kenvorm;
  echte namen blijven beschermd. Ook aan de lichtreflectie afgebroken
  e-mailwaarden worden achter een uitdrukkelijke e-mailveldkop met
  strikte, aan buren gebonden beeldrand verwijderd. Twee
  veld-waardeparen van dezelfde zichtbare regel worden nu onafhankelijk
  geëvalueerd; waarden op een lagere grondlijn alleen na drie
  overeenstemmende geometrische getuigen gekoppeld. Daardoor blijven
  kenmerken, geboortedata en adressen ook in dichte formulierlay-outs
  volledig beschermd. Straat, postcode en plaats worden uitsluitend
  binnen hetzelfde adresveld en met passende postale grammatica
  samengevoegd. Strikt omlijnde zakelijke velden voor
  werk-/hulpmiddelen en tandstatus veroorzaken geen plaats- of
  registervalse-alarmen meer; echte namen en soortgelijk benoemde
  velden blijven beschermd. Het Duitse documentlaboratorium omvat nu
  440 scans en bereikt 2.981/2.981 in het basisprofiel en 3.080/3.080
  in het kenmerkprofiel. Alle elf beeldmutaties en alle 40
  documentfamilies liggen op 100 procent, verder zonder gemeten vals
  alarm, behoudsschending of afbreking.

- PDF-tekstlagen met verloren celscheidingen begrenzen organisatie-,
  adres- en plaatsvondsten nu aan de hand van de herhaalde
  veld-waardestructuur. Veldkoppen vóór bedrijfswaarden en technische
  pijlen zoals `=>` of `->` horen niet meer bij de treffer. De
  extra weergave voor zachte regelafbrekingen mag rechtsvorm- en
  plaatsvondsten niet meer over meerdere tabelregels uitbreiden; een al
  volledig adres eindigt vóór de volgende veldkop met waarde. De
  afsluitende run over alle 1.600 TXT-, HTML-, PDF- en DOCX-documenten
  verwijdert 10.840/10.840 doelgegevens bij nul valse alarmen, nul
  behoudsschendingen en nul afbrekingen.

## 0.10.44-beta.1 – 1 september 2026

- De pakketbouw genereert aparte uitgaven voor Windows x64 en ARM64, macOS
  op Apple Silicon en Intel evenals Linux x64 en ARM64. Pakketnamen,
  actualiseringskeuze en releases onderscheiden de architectuur; een
  publicatie blijft geblokkeerd zolang een van de zes doelen of zijn
  afhankelijkheidsbewijs ontbreekt. Linux ARM64 vereist wegens Qt minstens
  glibc 2.39. Volledig op echte hardware afgenomen zijn voorlopig alleen
  Windows x64 en macOS op Apple Silicon; de overige architectuurpakketten
  moeten duidelijk als voorlopige versies voor beproeving in plaats van
  productief gebruik worden aangeduid.

- Bij meerdere bestanden werkt de herkenning nu verder, terwijl een
  voorbeeld op doorzicht wacht. Tot drie voorbereide voorbeelden worden na
  elkaar getoond; gelijktijdig rekent verder maar één document, en een
  resultaatbestand ontstaat pas na de vrijgave ervan. Een in het voorbeeld
  gekozen permanente uitzondering geldt ook voor al voorbereide volgende
  documenten.

- Redactiecertificaten zijn nu op elk moment direct in het menu Bestand
  tegen het gezwarte document te controleren. Maskuro onderscheidt daarbij
  een passend gesigneerd bestand, een passend maar ongesigneerd bewijs,
  een ongeldige handtekening en een niet bij het certificaat horend
  document. Een licentie of het oorspronkelijke besturingssysteemaccount is
  voor de tegencontrole niet vereist.
  Voor geautomatiseerde controleposten staat dezelfde vergelijking via
  `--zertifikat-pruefen` klaar; retourcodes onderscheiden overeenstemming,
  bedieningsfout en ongeldig bewijs.
  De tegencontrole vergelijkt bovendien de ingebedde Maskuro-ID met het
  certificaat; een vrij ingevoerde vreemde ID valt daardoor ook bij een
  ongesigneerd bewijs op.
  Bij geldige handtekening toont de controlebevinding bovendien de door
  het beheer geactiveerde bewerker met besturingssysteemaccount,
  technische account-ID en platform. Onbevestigde gegevens uit
  ongesigneerde of ongeldige bewijzen worden niet uitgevoerd.

- Een nieuw Duits documentlaboratorium genereert 160 volledig synthetische
  TXT-, HTML-, PDF- en DOCX-documenten uit tien gebieden en vier
  structuurvarianten. Het manifest onderscheidt nu uitdrukkelijk tussen
  gegevens die moeten verdwijnen, en vaktermen respectievelijk
  zaakkenmerken die behouden moeten blijven; documentfamilie, mutatie en
  openbare structuurbron zijn navolgbaar vastgelegd.

- Het Duitse documentlaboratorium is uitgebreid tot 280 bestanden, zeven
  structuurvormen, 1.540 doelgegevens en 1.036 behoudsankers. Nieuw
  gecontroleerd worden genummerde formulieren, tussen haakjes staande
  PDF-/maskervelden en technische `=>`-toewijzingen. De uitgebreide
  volledige stand bereikt in TXT, HTML, PDF en DOCX telkens 100 procent
  bij nul valse alarmen. Tussen haakjes staande datum- en kenmerkvelden,
  pijlscheidingen en uitdrukkelijk beschreven verbanden worden nu
  structureel herkend.

- Een tweede laboratoriumuitbreiding tilt het bestand op naar 400
  documenten, tien structuurvormen, 2.200 doelgegevens en 1.480
  behoudsankers. JSON-achtige sleutelwaarden, YAML-lijsten en
  formuliervelden in hoofdletters bereiken samen met het bestaande bestand
  100 procent bij nul valse alarmen. Geciteerde geboortedata en
  kenmerken evenals uitdrukkelijk beschreven rollen zoals verzekerde,
  solliciterende, aangifteplichtige en vertegenwoordigingsbevoegde
  personen worden nu ook in deze exportvormen herkend.

- Een aparte OCR-modus van het Duitse documentlaboratorium genereert
  bovendien 200 pure beeldscans uit alle 40 families. Schone,
  contrastarme, laag opgeloste, met JPEG-artefacten behepte en 90 graden
  gedraaide pagina's worden met exacte pixelkaders nagemeten, zonder de
  vergelijkbare 1.600-bestanden-tekstbasisstand te veranderen. Het
  manifest scheidt inschakelbare datum-, geld- en medische kenmerken van
  het basisprofiel en kent bewezen OCR-lezingen, zonder ze als extra
  doelplekken te tellen. De meting wordt uitgesplitst naar mutatie en
  documentfamilie. Strikte veldgrenzen voorkomen onder andere dat „Az" in
  de plaatsnaam „Graz" een volgende datum als dossiernummer zwart; de
  huidige basismatrix loopt met nul valse alarmen en nul afbrekingen.

- Vijf verdere Duitse documentfamilies voor factuur/pakbon,
  bank/krediet, huur/vastgoedbeheer, school/hogeschool en
  logistiek/douane breiden het laboratorium uit naar 600 bestanden met
  3.520 doelgegevens en 2.360 behoudsankers. Een strikte PDF-tabelweg
  gebruikt de uitdrukkelijke kop `Veld Gegeven`, wanneer de tekstlaag
  celscheidingen verliest; een nieuwe `--familien`-selectie versnelt
  deelmetingen. De 200 nieuwe bestanden bereiken 1.320/1.320 bij nul
  valse alarmen en nul afbrekingen.

- Verzekering/schade, werk/loon, medisch/laboratorium, voertuig/garage
  en techniek/onderhoud breiden het Duitse documentlaboratorium uit
  naar 800 bestanden met 4.960 doelgegevens en 3.200 behoudsankers.
  Strikt beschreven polis-, patiënt-, keurmeester- en voertuigkenmerken
  evenals nieuwe rol-, adres- en organisatievelden worden herkend. De
  nieuwe deelmatrix en de volledige matrix bereiken 100 procent bij nul
  valse alarmen en nul afbrekingen in TXT, HTML, PDF en DOCX.

- Bouw/aanbesteding, energie/milieu, vereniging/genootschap,
  communicatie/agenda en hotel/evenement tillen het Duitse
  documentlaboratorium op naar 1.200 bestanden met 7.920 doelgegevens en
  4.800 behoudsankers. Nieuwe rol-, bedrijfs-, adres-, register-,
  aanbestedings-, boekings- en gebruikersaccountvelden worden ook in
  alle exportvormen herkend. Tellernummers blijven als zaakkenmerken
  behouden. Deel- en volledige matrix bereiken 100 procent bij nul
  valse alarmen en nul afbrekingen.

- Horeca/bezorgdienst, apotheek/recept, uitvaart/begraafplaats,
  sport/lidmaatschap en vastgoed/makelaar breiden het Duitse
  documentlaboratorium uit naar 1.400 bestanden met 9.360 doelgegevens
  en 5.640 behoudsankers. Nieuwe persoonsrollen, adresvelden en
  zoekopdrachtnummers worden herkend. Beschreven bedrijfsnamen met
  rechtsvorm blijven ook over een automatische regelafbreking heen
  volledig beschermd; leeftijdscategorieën en vakkoppen worden niet meer
  ten onrechte vervangen. Deel- en volledige matrix bereiken 100 procent
  bij nul valse alarmen en nul afbrekingen.

- Tandartsbehandeling, rijschool, brandweer/inzet, energiegemeenschap
  en pakketreis breiden het Duitse documentlaboratorium uit naar 1.600
  bestanden met 10.840 doelgegevens en 6.440 behoudsankers. Nieuwe
  rollen, adresvelden evenals behandelings-, opleidings-, inzet-,
  energie- en reiscontractkenmerken worden structureel herkend. De
  nieuwe 200-bestanden-deelmatrix bereikt 1.480/1.480; de volledige
  matrix bereikt 10.840/10.840. Beide blijven bij nul valse alarmen en
  nul afbrekingen.

- De volledige meting van het documentlaboratorium verlaagde door
  strikte officiële zaakvormen en structuurregels de onnodige
  vervangingen van 68 naar 0, de uitdrukkelijk gemeten
  behoudsschendingen van 23 naar 0 en de afbrekingen van 3 naar 0. Het
  vondstpercentage steeg tegelijk van 91,1 naar 100,0 procent; TXT,
  HTML, PDF en DOCX bereiken telkens 100 procent. Algemene tabelkoppen
  zoals `Veld` worden alleen in de bezette volgorde `Veld`/`Gegeven`
  afgeremd; een gelijkluidende achternaam blijft beschermd. Gerechtelijke
  dossiernummers met eindletter, gelijkheidsteken-velden,
  `Geboortedatum van het kind` en meerdere beschreven losse namen in
  dezelfde regel worden volledig herkend. Word-tabellen en
  voorregelvelden gebruiken hun veldkop als tijdelijke herkenningscontext;
  beschreven PDF-adressen blijven ook bij een zetgebonden
  regelafbreking volledig beschermd.

- Duitse persoonskenmerk-, beroeps- en medische velden werken nu ook
  met Windows-regelafbrekingen. Eénletterige geslachtsaanduidingen
  zoals `Geslacht`/`v` worden in de voorregelvorm beschermd. Zakelijke
  `Artikel-PZN`-velden lokken daarentegen noch een
  geneesmiddelencode- noch een persoonsvondst uit; echte PZN-, ICD- en
  ATC-gegevens blijven herkend.

- Duitse formulier- en nummervelden zijn nauwkeuriger: „DW." werkt nu
  ook vóór een zachte regelafbreking, uitdrukkelijk beschreven namen
  worden ook bij kleine letters verwijderd en zuiver numerieke
  dossiernummers worden toegewezen aan hun juiste soort kenmerk.
  Omgekeerd geldt een toevallig Luhn-geldig factuur-, bewijsstuk- of
  artikelnummer niet meer als creditcard. Synthetische HTML- en
  PDF-uitvoerproeven bevestigen verwijderen en behouden in het
  voltooide document.
  Kenmerken en gebruikersnamen worden bovendien herkend wanneer hun
  beschrijving in de direct voorafgaande tabel- of formulierregel
  staat; zakelijke bewijsstuknummers blijven ook in deze vorm zichtbaar.

- Wachtwoorden worden nu ook achter een alleenstaande veldkop in de
  voorafgaande regel herkend. Afsluitende bijzondere tekens zoals `!`
  of `#` horen daarbij volledig bij de beschermde waarde. Product- en
  artikel-pincodes worden omgekeerd niet meer als kaartpincode
  gemaskeerd; uitdrukkelijke `PIN`- en `Kaart-PIN`-velden blijven
  beschermd.

- Kleingeschreven formulierwaarden worden bij eenduidige Duitse
  adres- en `postcode/plaats`-velden nu als adres respectievelijk
  postcode met plaats uitgevoerd in plaats van alleen als algemene
  plaats. Evenzo blijven kleingeschreven bedrijfswaarden zoals
  „voorbeeld service" achter een bedrijfsveld volledig beschermd, zonder
  het laatste woord als vermeende volgende veldkop af te snijden.

- Hulp, FAQ, privacytekst en website leggen het herkomstbewijs nu
  gezamenlijk uit: neutrale Maskuro-ID in het document, optionele
  toewijzing aan het echte besturingssysteemaccount alleen in het
  lokale controlelogboek, gebruikerswissel via Windows/macOS/Linux
  evenals de zeggingskracht van SHA-256 en handtekening.

- Op afbeeldingen gebaseerde technische bestekken worden terughoudender
  opgeschoond. Eenduidige zaakwoorden zoals „sloophameren",
  „inhoudingsgarantie", „positienummers", „inbouwplatine" of
  „terminsituatie" evenals midden in het woord afgebroken OCR-vormen
  gelden niet meer als persoon of plaats. Een echte gemeentehuis-offerte
  daalde daardoor van 140 naar 90 eenduidige vervangingen, zonder nieuwe
  treffers te veroorzaken; namen zoals Schneider, Lang, Bauer en Hahn
  blijven uitdrukkelijk beschermd.

- Verdere valse alarmen uit echte offertes zijn opgelost: „Digitaal
  ondertekend" bevat geen vermeende persoon meer, een BIC wordt ook
  zonder dubbele punt achter haar beschrijving herkend, `15000
  Alternatief` geldt niet als postcode met plaats, en het EU-citaat
  „(VO (EG) 715/2007" veroorzaakt geen organisatie. Een
  zonne-energieofferte daalde daardoor van 26 naar 16
  vervangingsvoorkomens; echte namen, plaatsen en rekeninggegevens
  bleven behouden.

- In personeelsoverzichten worden de afkorting „Stv." (plaatsvervanger)
  en een alleenstaande afgesplitste „FACILITY"-sectiekop niet meer als
  persoonsnaam vervangen. De echte 13 pagina's tellende tegencontrole
  daalde van 878 naar 875 vervangingen; namen, doorkiesnummers en de
  bedrijfsbenaming bleven beschermd.

- Opgeschoonde PDF-, OpenDocument- en Office-bestanden krijgen een
  neutraal `MASKURO-…`-kenmerk in hun documenteigenschappen.
  Controlerapport en gesigneerd controlelogboek voeren hetzelfde
  kenmerk evenals SHA-256-waarden van bron en resultaat; het
  redactiecertificaat neemt het kenmerk over uit het voltooide bestand.
  Een gebruikersnaam komt verder alleen erbij als het beheer het
  bestaande gebruikersveld uitdrukkelijk inschakelt.

- Hoofdvenster en instellingen zijn rustiger geordend: opslaan,
  kopiëren, details, kengetallen en het verwijderen van een
  herkenningsprofiel verschijnen pas wanneer de betreffende handeling
  mogelijk is. Technische OCR-taalafkortingen en lange voorbeelden
  staan waar nodig in de aanwijstekst in plaats van blijvend op het
  werkvlak. De herkenningspagina past zich beter aan smallere vensters
  aan, zonder afgesneden uitleg of horizontale schuifbalk; de
  waarschuwing voor klare tekst in de vervangingslijst blijft daarbij
  zichtbaar.

- De herkenning sluit verdere Duitse en internationale contactgevallen af:
  telefoonnummers worden nu voor alle te kiezen landregio's gecontroleerd,
  Hongaarse en Kroatische contractrollen vatten ook beroepsgelijke
  achternamen volledig, en genummerde onderdelen-/materiaallijsten lokken
  niet meer wegens „Moeder / Plat" een persoonsvals alarm uit.
  Persoonsvelden met een overduidelijk cijferhoudende zakelijke waarde
  worden niet als naam overgenomen; de machineleesbare paszone (MRZ)
  is bovendien via de groep „Kenmerken" gezamenlijk in en uit te
  schakelen.

- Bedrijven zonder rechtsvorm worden achter meerduidige
  werkgeversvelden beter van personen onderscheiden: namen zoals
  „Huber Handel", „Müller Logistiek" of „Kowalski Handel" worden
  volledig als bedrijf herkend, terwijl „Werkgever: Bauer Anna" verder
  een persoonsnaam blijft. De automatische landkeuze houdt bij Franse
  documenten verder rekening met het hele Franse taalgebied inclusief
  Luxemburg.

- Herkende handtekeningen en persoonsgebonden tekst binnen een
  afbeelding werden tot nu toe altijd met een zwart rechthoek afgedekt
  – ook als voor zwartingen een andere kleur of een patroon zoals
  „Regenboog" was ingesteld. Deze beeldgebieden nemen nu ook de gekozen
  zwartingsweergave over; het dekkende vlak wordt verder direct in de
  beeldpunten geschreven.

- De Engelse herkenning is aan elf handmatig vertaalde echte documenten
  nagemeten en gericht verbeterd: voorraadstatus, technische offerte-
  en webshopvelden evenals rollen in personeelsregisters blijven
  zichtbaar, „CV" wordt in de sjabloonzin niet meer als rechtsvorm
  gelezen, geciteerde lettertypen blijven behouden, en namen in
  verticale cv-koppen, meerpagina's tellende personeelslijsten, achter
  „Account manager" evenals cijferbeginnende bedrijfsnamen worden
  volledig herkend. Oostenrijkse handelsregisternummers werken nu ook
  achter een Engelse beschrijving; de korte vorm „Customer:",
  EAR-registratienummers en werkgeversnummers dragen hun waarde.
  Maatketens, kabeltypes, EU-rechtsverwijzingen, offerte-geldigheidsdata,
  vervullingsplaatsen, bevoegde rechtbanken, registergerechten, de
  belastingafkorting „NoVA", technische nummers in bandenlabels
  evenals normverwijzingen zoals „OVE R6-2" en „AStV" veroorzaken geen
  vals alarm meer. Een geldige beschreven IBAN eindigt netjes vóór het
  registratieveld of de kop van de volgende regel; adressen met
  bedrijfszone-toevoeging worden ook uit PDF-tekststromen met
  Windows-regelafbrekingen volledig herkend. Engelse
  bedrijfsintroducties en gestructureerde spaarbanknamen worden volledig
  afgebakend. Het land van het brondocument blijft bij de taalversies
  voor postcodes en landspecifieke kenmerken behouden.

- In ontvanger- en berichtkopregels kon het taalmodel de eerste twee
  namen van een kommalijst tot één enkele vondst verbinden („Bcc: Huber,
  Mayer"). Beide namen worden nu afzonderlijk herkend, vervangen en in
  het rapport gevoerd – evenzo achter „Sent:", „Reply:" en „Fwd:".

- Het machineleesbare gebied van een paspoort of identiteitsbewijs (MRZ)
  ontbrak in de groepsbesturing „Wat wordt gezocht". Het hoort nu bij
  „Kenmerken" en is met deze groep gezamenlijk in en uit te schakelen.

- Wie voor vervangteksten het sjabloon „Regenboog" kiest, krijgt nu ook
  gezwarte plekken in dezelfde weergave; tot nu toe bleven ze
  verrassend klassiek zwart. De zwartingsvlakken zijn daarna verder
  onafhankelijk naar een ander sjabloon om te stellen.

- Het paginavak van de nabewerkingseditor kon na het herstellen van een
  opgeslagen vensterindeling leeg blijven, tot zijn breedte met de hand
  werd gewijzigd. De miniaturen worden nu na de zichtbare vensteropbouw
  opnieuw geordend en staan meteen gecentreerd in het vak.

- De gekleurde controlemarkeringen rond vervangteksten in PDF's bleven
  afhankelijk van categorie- en stoplichtkleur nauwelijks zichtbaar. Een
  lichte ondercontour scheidt het controlekader nu betrouwbaar van de
  gekleurde plaatshouder en van de paginaachtergrond.

- Wie in de nabewerkingseditor een regel zwart waarvan het document met
  krappe regelafstand is gezet (typisch voor offertes en bestekken),
  kreeg een balk die in de bovenlengtes van de regel eronder stak – die
  was daarna nog maar half leesbaar. De balk eindigt nu bij de echt
  getekende letters van de buurregel; de gezwarte regel zelf blijft
  daarbij inclusief haar onderlengtes volledig gedekt.

- Het oefendocument („Help → Oefendocument openen", ook in de
  rondleiding) toont nu elke herkenningssoort: bij de verzonnen brief
  komen een portretfoto met herkenbaar gezicht, een geschreven
  handtekening, beroep en afdeling, diagnose en medicijn erbij – naast
  bedrijfsnaam, bedrag en datum, die er al waren. Wat de standaard
  bewust laat staan, legt het blad zelf uit, samen met de schakelaar
  die het verwijdert; het gezicht op de foto wordt standaard
  gepixeleerd.

- Geldbedragen in de gebruikelijke Duitse schrijfwijze met het symbool
  achter het getal („1.240,00 €") werden door de schakelaar
  „Geldbedragen ook verwijderen" nooit gevonden – „1.240,00 EUR" en
  „€ 1.240,00" altijd al wel. Nu worden alle drie schrijfwijzen
  herkend.

- De handtekeningzoektocht werkt nu ook op losstaande beeldbestanden:
  wie een scan als JPG of PNG opschoont, krijgt handgeschreven
  handtekeningen erin gezwart – dezelfde herkenning, dezelfde melding
  in het rapport als bij PDF. In Office-bestanden ingebedde
  afbeeldingen worden verder niet doorzocht, omdat de herkenning daar
  gemeten onbetrouwbaar werkt; het vinkje heet daarom nu „PDF en
  beeldbestanden: handgeschreven handtekeningen zwarten".

- Een zwartbalk kon bij krappe regelafstand zichtbaar in de bovenlengtes
  van de regel eronder steken en die half onleesbaar maken – de
  balkhoogte kwam uit de lettertypemetriek, niet uit wat werkelijk op
  het papier staat. De balk eindigt nu bij de echt getekende inkt van
  de buurregel, in de nabewerkingseditor zoals in de automatische
  opschoning. De eigen regel inclusief onderlengtes blijft daarbij
  altijd helemaal gedekt; overlappen de regels echt, dan blijft de balk
  liever op de buurregel staan dan iets vrij te geven.

- In een personeelsregister met rol onder de naam werd een vrouwelijke
  leidinggevende benaming („Anna Berger" met „Montageleidster"
  eronder) meegetrokken in de naamvervanging – de mannelijke vorm
  ernaast bleef correct staan. De vrouwelijke „…leidster"-vormen
  (montage-, team-, project-, bouw-, afdelings-, bedrijfs-, groeps-,
  ambtsleidster) worden nu net als hun mannelijke tegenhangers als
  functiebenaming behandeld; filiaal-, personeels- en verkoopleiding
  zijn in beide vormen nieuw meegenomen.

- De inschakelbare beroepsherkenning vond vrouwelijke leidinggevende
  rollen zoals „Projectleidster", „Teamleidster" of
  „Afdelingsleidster" niet, hun mannelijke vormen echter wel. Beide
  vormen tellen nu gelijkelijk.

- In het voorbeeldvenster kleefde op de Mac de meervoudsaanduiding
  direct aan het begrip („Anna Modelvrouw2ק in plaats van „Anna
  Modelvrouw 2ק). De spatie staat er weer.

- Het vergelijkingsvergrootglas heeft een nieuwe knop naast de
  zoomregelaar: hij legt het met één druk in volle breedte over het
  resultaat – elk halve hoogte, en het origineel op dezelfde schaal
  als het document (de vergrootglaszoom springt daarvoor naar 100 %).
  Een tweede druk dokt het weer klein aan in de linkerkolom en herstelt
  de vorige vergrootglaszoom. De cirkel ernaast zet nu alleen de zoom
  terug – zijn aanwijstekst beweerde tot nu toe ten onrechte dat hij ook
  het venster weer aandokte.

- In de werkbalk van de nabewerkingseditor is aan het gekozen werktuig
  weer te zien dat het gekozen is: de knop van het actieve werktuig
  draagt een gevuld vlak met blauwe rand – evenzo elke andere
  ingeschakelde omschakelknop van de balk (bijvoorbeeld
  vergelijkingsvergrootglas of leermodus). De markering was met de
  eigen knopvormgeving van 29 augustus verloren gegaan.

- Positienummers van een bestek („2.3.3.3, 2.3.3.4, 2.3.3.5" onder
  elkaar) werden voor IP-adressen gehouden en uit het resultaat
  verwijderd; drietrapsnummers met een jaartalachtig laatste lid
  („2.3.19, 2.3.20") vielen als kalenderdata. Een oplopende
  nummerreeks aan het begin van de regel geldt nu als wat ze is – een
  positielijst; echte adressen (netwerktabellen met technische
  woordomgeving, getallen boven 99) en echte datumaanduidingen blijven
  verder herkend.

- Achternamen zoals „Müller", „Fischer", „Bauer", „Koch", „Wagner",
  „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster",
  „Schäfer" of „Meister" bleven in lijsten van de vorm „Achternaam,
  Voornaam" (bijv. „Deelnemers: Müller, Peter; Nowak, Anna") in klare
  tekst staan, omdat ze tegelijk gangbare beroepsbenamingen zijn. Ze
  worden nu betrouwbaar herkend.

- Bij het zwarten van een PDF kon de balk in smalle tabelcellen de hele
  cel meenemen: van de treffer „D-LINK" in een bestek werd de complete
  productbeschrijving ernaast verwijderd, hoewel het voorbeeld alleen de
  treffer had genoemd. De balk dekt verder hele adresblokregels en
  veldbeschrijvingen af, maar verzwelgt hoogstens zoveel onbetrokkens
  als hij beschermenswaardigs dekt – de beschrijving naast de treffer
  blijft nu staan.

- Na „Weergave terugzetten" in de nabewerkingseditor bleef het
  paginavak leeg – de miniaturen van de pagina's waren pas na het
  sluiten en opnieuw openen van het venster weer te zien. Nu staan ze
  ook direct na het terugzetten er, gecentreerd zoals voorheen.

- De nabewerkingseditor heeft een vierde werktuig: **Verwijderen** haalt
  de tekst onder het kader zonder vervanging weg – zonder balk
  (zwarten) en zonder plaatshouder (vervangen); het gat blijft zichtbaar
  leeg. Het werkt woordnauwkeurig, ligt eronder een afbeelding, dan
  wordt haar grond wit geruimd, en „Origineel terughalen" maakt ook een
  verwijdering zonder vervanging weer ongedaan. Eigen balksymbool en
  draadkruisembleem (kruis), eigen sneltoets in alle 18 talen (Duits F
  van entFernen, in het Nederlands V van Verwijderen).

- In de PDF-zoekbalk staat „Map …" nu rechts naast de zoekopties. Sinds
  er naast het zwarten ook het vervangen van treffers bestaat, pasten
  vijf knoppen bij gewone vensterbreedte niet meer naast elkaar – de
  eerste werd samengeperst en zijn tekst afgesneden.

- „Alle instellingen terugzetten" zet nu ook het vinkje „Rood/groen door
  andere kleuren vervangen" terug en vermeldt het net als elk ander met
  „gewijzigd" als het afwijkt van de uitlevering.

- Vervangteksten in PDF's werken nu gelijkmatiger: waar de volledige
  plaatshouder aanzienlijk kleiner zou moeten uitvallen dan zijn regel
  (bijvoorbeeld „[BEG16]" samengeperst in een kort woord zoals „Het"),
  staat in plaats daarvan een korte vorm in regelgrootte („[B16]") –
  goed leesbaar in plaats van piepklein, en het nummer voor het
  terughalen draagt beide schrijfwijzen. Piepklein wordt een
  plaatshouder alleen nog wanneer zelfs de kortste vorm geen plaats
  vindt – dat blijft beter dan een balk zonder enige informatie.

- Een meerkleurig gezette vervangtekst (verloop of regenboog) in een
  PDF bleef alleen tot de volgende ingreep heel: elke verdere
  vervanging of zwarting op dezelfde pagina kon al gezette
  plaatshouders tot een onleesbare, samengeperste letterstapel
  samendrukken – wie in de editor woord voor woord verving, zag in
  plaats van „[BEG17]" alleen nog over elkaar gedrukte tekens. Eenmaal
  gezette plaatshouders blijven nu staan zoals ze werden gezet.

- De schakelaar voor blijvende uitzonderingen in het voorbeeld heet nu
  „Nooit verwijderen" – zoals de lijst waarin hij invoert; tot nu toe
  stond daar „nooit meer". De trefregel ernaast is opgeruimder: het
  info-symbool „ⓘ" is groter en makkelijker te raken, en vakje,
  vervangmarkering en knop hebben een gemeenschappelijke hoogte. De zin
  rond een vondst gebruikt zijn aangekondigde breedte nu echt – de
  bestaande breedteopgave had de weergave stilzwijgend verworpen, en
  het fragment brak verder af als smalle strook.

- In de editor zegt de muisaanwijzer nu welk werktuig actief is: een
  draadkruis om te richten, ernaast een klein teken – balk voor
  zwarten, ruilpijlen voor vervangen, ongedaan-maken-boog voor
  herstellen, pixelraster voor pixeleren. De bestaande handsymbolen
  vervielen; een hand betekent overal elders „grijpen en schuiven". Ze
  heeft nu een passende taak: boven een rood uitgelicht woord of balk
  wordt de aanwijzer een wijzende hand – een klik volstaat daar.

- „Maximale herkenning (AI)" biedt geen downloadbaar, lokaal taalmodel
  meer aan – het niveau rekent nu uitsluitend via een onder „Eigen AI
  koppelen" ingerichte, eigen AI. Wie al een eigen server had
  gekoppeld, merkt geen verschil.

- De begeleide rondleiding van het voorbeeld legt nu ook het
  info-symbool „ⓘ" uit, dat de zin rond een vondst toont. En deze zin
  zelf is beter leesbaar: een niveau grotere letter, meer regelafstand,
  vaste breedte in plaats van een smalle, dicht opeengepakte
  afbreking.
- Ook „Bestand nakijken", „Herkenningsregels en eigen begrippen",
  „Tekst opschonen" en „Afbeelding opschonen" hebben nu een eigen
  rondleiding – via een nieuwe knop „Rondleiding door het venster",
  omdat deze vier vensters geen eigen menubalk hebben.
- Namen onder negen Oekraïense contractrol-beschrijvingen bleven bij een
  homografe achternaam onvolledig herkend, wanneer de beschrijving
  alleen op haar regel stond: „Покупець"/„Продавець" (koper/verkoper),
  „Поручитель"/„Боржник" (borg/hoofdschuldenaar), „Свідок" (getuige),
  „Орендодавець"/„Орендар" (verhuurder/huurder) en
  „Спадкодавець"/„Спадкоємець" (erflater/erfgenaam). De namen worden nu
  volledig herkend.

- De opmerking van een benoemd bereik in een Excel-werkmap
  (naambeheerder, veld „Opmerking") voerde een daarin ingevoerde naam
  ongewijzigd verder. Ze wordt nu net zo opgeschoond als de overige
  inhoud van de werkmap.

- Namen onder zeven Hongaarse contractrol-beschrijvingen bleven bij een
  homografe achternaam helemaal onontdekt: „Bérbeadó"/„Bérlő"
  (verhuurder/huurder), „Vevő"/„Eladó" (koper/verkoper),
  „Kezes"/„Főadós" (borg/hoofdschuldenaar) en „Tanú" (getuige). De
  namen worden nu volledig herkend.

- Namen onder de Tsjechische koper-beschrijving „Kupující" bleven bij
  een homografe achternaam helemaal onontdekt. De naam wordt nu
  volledig herkend.

- Namen onder de Russische voogd-beschrijving „Опекун" bleven bij een
  homografe achternaam helemaal onontdekt. De naam wordt nu volledig
  herkend.

- Namen onder zes verdere Kroatische beschrijvingen bleven onontdekt:
  „Jamac" (borg), „Glavni dužnik"/„Dužnik"
  (hoofdschuldenaar/schuldenaar), „Ostavitelj" (erflater), „Nasljednik"
  (erfgenaam) en „Vjerovnik" (schuldeiser). De namen worden nu volledig
  herkend.

- Een opgeslagen HTML-pagina met een ingebedde subpagina in het
  `src`-attribuut van een `<embed>` (in plaats van `data` bij
  `<object>`) voerde persoonsgegevens daarin ongewijzigd verder. Ze
  worden nu net zo opgeschoond als bij `<object>`.

- Namen onder vijf Deense contractrol-beschrijvingen bleven bij een
  homografe achternaam onvolledig herkend, wanneer de beschrijving met
  dubbele punt vóór de naam stond: „Arvelader"/„Arving"
  (erflater/erfgenaam), „Befuldmægtiget"/„Fuldmagtsgiver"
  (gevolmachtigde/volmachtgever) en „Værge" (voogd). De namen worden nu
  volledig herkend; de bijbehorende Noorse beschrijvingen zijn ter
  zekerheid eveneens aangevuld.

- Plaatshouders in Word- en PowerPoint-bestanden dragen nu dezelfde
  kleur als in de gekozen weergave (effen, verloop, regenboog of per
  categorie) – tot nu toe bleven ze daar in gewone tekstkleur, ook als
  PDF-resultaten allang gekleurd uitvielen.

- „Als tekst kopiëren" en „Als Markdown kopiëren" leggen de klare tekst
  van het resultaat direct op het klembord – om in chat, mail of een
  ander programma te plakken, zonder het bestand eerst te openen.

- Namen onder vijf verdere Sloveense beschrijvingen bleven onontdekt:
  „Toženec" (gedaagde), „Tožnik" (eiser), „Zastavitelj" (verpander),
  „Zastavni upnik" (pandhouder) en „Darovalec" (schenker). De namen
  worden nu volledig herkend.

- De auteursnaam van een bijgehouden tabelcelwijziging (ingevoegde,
  verwijderde of samengevoegde cel in Word) bleef in het bestand staan,
  ook als dezelfde naam als opmerkingauteur allang was verwijderd. Ze
  wordt nu eveneens verwijderd.

- Namen onder negen verdere Sloveense beschrijvingen bleven onontdekt:
  „Najemodajalec"/„Najemnik" (verhuurder/huurder),
  „Zapustnik"/„Dedič" (erflater/erfgenaam), „Upnik"/„Dolžnik"
  (schuldeiser/schuldenaar), „Glavni dolžnik" (hoofdschuldenaar) en
  „Skrbnik" (voogd/bewindvoerder). De namen worden nu volledig herkend.

- Namen onder vijf Sloveense beschrijvingen bleven onontdekt:
  „Izvedenec" (deskundige), „Kupec" (koper), „Prodajalec" (verkoper),
  „Naročnik" (opdrachtgever) en „Izvajalec" (opdrachtnemer). De namen
  worden nu volledig herkend.

- Namen onder vijf verdere Litouwse beschrijvingen bleven onontdekt:
  „Užsakovas" (opdrachtgever), „Vykdytojas" (opdrachtnemer), „Vežėjas"
  (vervoerder), „Siuntėjas" (afzender) en „Arbitras" (arbiter). De
  namen worden nu volledig herkend.

- Namen onder zes verdere Litouwse beschrijvingen bleven onontdekt:
  „Įgaliotinis" (gevolmachtigde), „Įgaliotojas" (volmachtgever),
  „Naudos gavėjas" (begunstigde, verzekering), „Trečiasis asmuo"
  (tussenkomende/derde partij in civiel proces), „Ankstesnis
  nuomininkas" (vorige huurder) en „Naujasis nuomininkas" (nieuwe
  huurder). De namen worden nu volledig herkend.

- Een bladwijzer in ODT-documenten (`text:bookmark`) draagt haar naam
  vrij gegeven, vaak genoemd naar de plek waarnaar ze verwijst (bijv.
  „Meneer_Mueller_Handtekening") – onzichtbaar voor de lezer, maar
  letterlijk in het bestand. De naam wordt nu mee opgeschoond.

- Namen onder acht verdere Litouwse beschrijvingen bleven onontdekt:
  „Pareiškėjas" (aanvrager), „Suinteresuotas asmuo" (verweerder in
  niet-contentieuze procedure), „Ekspertas" (deskundige), „Bankroto
  administratorius" (curator), „Valdybos narys" (lid raad van
  commissarissen), „Direktorius" (directeur), „Palikėjas" (erflater) en
  „Įpėdinis" (erfgenaam). De namen worden nu volledig herkend.

- Namen onder zeven verdere Litouwse beschrijvingen bleven onontdekt:
  „Liudytojas" (getuige), „Vertėjas" (tolk/vertaler), „Notaras"
  (notaris), „Dovanotojas" (schenker), „Apdovanotasis" (begiftigde),
  „Pirkėjas" (koper) en „Pardavėjas" (verkoper). De namen worden nu
  volledig herkend.

- Namen onder zes verdere Litouwse beschrijvingen bleven onontdekt:
  „Globėjas" (voogd/bewindvoerder), „Palikimo administratorius"
  (nalatenschapsbeheerder), „Laiduotojas" (borg), „Pagrindinis
  skolininkas" (hoofdschuldenaar), „Nuomotojas" (verhuurder) en
  „Nuomininkas" (huurder). De namen worden nu volledig herkend.

- Een naam onder de Litouwse beschrijving „Ieškovas"/„Atsakovas" (eiser/
  gedaagde als procespartij) bleef onontdekt, ongeacht of de
  achternaam tegelijk een gangbaar woord was (bijv. „Vilkas" = wolf) of
  niet. De naam wordt nu volledig herkend.

- Een persoonsregisteritem in ODT-documenten (bladwijzer voor het
  trefwoordenregister) voerde de naam een tweede keer in haar eigen
  sorteersleutel – onzichtbaar in de lopende tekst, maar letterlijk in
  het later gegenereerde register. De sleutel wordt nu mee opgeschoond.

- De dianaam en de sectienaam van een PowerPoint-presentatie (zichtbaar
  in het selectievenster resp. in de diasortering) bleven niet opgeschoond,
  omdat beide als attribuut aan een element hangen dat geen diatekst
  is. Beide worden nu herkend.

- Een Litouwse dubbele naam met koppelteken zoals „Petraitis-Kazlauskas"
  verloor haar tweede helft, zodra er ergens lopende tekst voor stond
  (alleen aan het begin van de tekst bleef ze volledig): de achternaam
  wordt nu ook dan helemaal herkend.

- Een naam onder de beschrijving „Cesionar" (Kroatisch, cessionaris bij
  vorderingsoverdracht) veroorzaakte een vals alarm, omdat de
  veldbeschrijving zelf ten onrechte als persoon werd gelezen. Een naam
  onder de Russische beschrijving „Цессионарий" (eveneens cessionaris)
  bleef daarentegen helemaal onontdekt. Beide gevallen zijn nu
  opgelost.

- Een naam onder de beschrijving „Zedent"/„Zessionar" (Duits,
  vorderingsoverdracht) bleef zonder vervanging onontdekt, wanneer de
  achternaam tegelijk een gangbaar woord was (bijv. „Bauer"). De naam
  wordt nu volledig herkend.

- Een naam onder de beschrijving „Darczyńca"/„Obdarowany" (Pools,
  schenker/begiftigde in schenkingsovereenkomst) bleef onontdekt,
  wanneer de achternaam tegelijk een gangbaar woord was (bijv. „Wilk" =
  wolf). Evenzo bleef de Roemeense beschrijving „Donatar" (begiftigde)
  bij een gewone achternaam zelf als vermeend naamonderdeel hangen.
  Beide gevallen zijn nu opgelost.

- Een naam onder de beschrijving „Wierzyciel"/„Dłużnik" (Pools,
  executieschuldeiser/executieschuldenaar resp. algemene
  schuldeiser/schuldenaar) bleef onontdekt, wanneer de achternaam
  tegelijk een gangbaar woord was (bijv. „Wilk" = wolf). De naam wordt
  nu volledig herkend.

- Een naam onder de beschrijving „Poręczyciel"/„Dłużnik główny" (Pools,
  borg/hoofdschuldenaar in borgtochtovereenkomsten) bleef onontdekt,
  wanneer de achternaam tegelijk een gangbaar woord was (bijv. „Wilk" =
  wolf). De naam wordt nu volledig herkend.

- Een naam onder de beschrijving „Ubezpieczony"/„Ubezpieczający" (Pools,
  verzekerde/verzekeringnemer in verzekeringspolissen) bleef gedeeltelijk
  of helemaal onontdekt, wanneer de achternaam tegelijk een gangbaar
  woord was (bijv. „Wilk" = wolf). Evenzo een naam onder
  „Osiguranik"/„Osiguravatelj" (Kroatisch, dezelfde rollen), daar
  verdween ze samen met de voornaam volledig (bijv. „Golub" = duif).
  Beide namen worden nu volledig herkend.

- Een naam onder de beschrijving „Pełnomocnik"/„Mocodawca" (Pools,
  gevolmachtigde/volmachtgever in volmachtaktes) bleef onontdekt,
  wanneer de achternaam tegelijk een gangbaar woord was (bijv. „Wilk" =
  wolf). Evenzo een naam onder
  „Opunomoćenik"/„Opunomoćitelj" (Kroatisch, dezelfde rollen), daar
  verdween ze zelfs volledig samen met de voornaam. Beide namen worden
  nu volledig herkend.

- Een naam onder de beschrijving „Pozwany" (Pools, gedaagde als
  procespartij) bleef onontdekt, wanneer de achternaam tegelijk een
  gangbaar woord was (bijv. „Wilk" = wolf). De naam wordt nu volledig
  herkend.

- Een naam onder de beschrijving „Najmoprimac"/„Najmodavac" (Kroatisch,
  huurder/verhuurder in huurovereenkomsten) bleef onontdekt, wanneer de
  achternaam tegelijk een gangbaar woord was (bijv. „Kovač" = smid). De
  naam wordt nu volledig herkend.

- Een naam onder de beschrijving „Pracodawca"/„Pracownik" (Pools,
  werkgever/werknemer als contractpartij in arbeidsovereenkomsten)
  bleef gedeeltelijk onontdekt, wanneer de achternaam tegelijk een
  gangbaar woord was (bijv. „Krawiec" = kleermaker). De naam wordt nu
  volledig herkend.

- Hongarije had in de landencatalogus alleen de persoonskenmerken en het
  btw-nummer: het handelsregisternummer (Cégjegyzékszám) wordt nu
  herkend, mits het veldwoord „Cégjegyzékszám" of de afkorting „Cg."
  direct ervoor staat – het nummer zelf draagt geen controlecijfer.

- Estland had in de landencatalogus alleen de Isikukood: de
  Käibemaksukohustuslase number (btw-nummer op elke Estse factuur)
  wordt nu met controlecijfer herkend.

- Letland had in de landencatalogus alleen de persoonscode: de PVN
  reģistrācijas numurs van rechtspersonen (bedrijfskenmerk op elke
  Letse factuur) wordt nu met controlecijfer herkend.

- Een e-mail met versleutelde inhoud (S/MIME- of PGP/MIME-envelop,
  `multipart/encrypted`) werd zonder enige waarschuwing als schijnbaar
  volledig gecontroleerd uitgevoerd, hoewel haar eigenlijke inhoud
  versleuteld en daarmee ongecontroleerd bleef. Zulke mails wijzen daar
  nu net als een ongecontroleerde bijlage op.

- Malta ontbrak in de landencatalogus: het Maltese btw-nummer (VAT
  number) wordt nu herkend.

- Luxemburg ontbrak in de landencatalogus: het Luxemburgse btw-nummer
  (n° TVA) wordt nu herkend.

- Een aan het begin van de zin geplaatst Bulgaars „Изчакайте" ("Wacht
  even!") werd als plaatsaanduiding gemeld – dezelfde modelgrens als
  eerder bij Hongaarse, Poolse, Tsjechische en andere
  gebiedende-wijsvormen zonder eigen taalmodel. Het valse alarm blijft
  nu uit.

- Een naam onder de beschrijving „Zleceniodawca", „Zleceniobiorca"
  (Pools), „Prestator" (Roemeens), „Naručitelj" of „Izvođač" (Kroatisch)
  bleef gedeeltelijk of helemaal onontdekt, wanneer de achternaam
  tegelijk een gangbaar woord was (bijv. „Wilk", „Vuk" = wolf, „Vulpe" =
  vos, „Sokol" = valk). De naam wordt nu volledig herkend.

- Een naam onder de beschrijving „Nadawca" (Pools), „Afsender" (Deens)
  of „Pošiljatelj" (Sloveens) bleef gedeeltelijk of helemaal onontdekt,
  wanneer de achternaam tegelijk een gangbaar woord was (bijv. „Sowa" =
  uil, „Bager" = bakker, „Volk" = wolf). De naam wordt nu volledig
  herkend.

- Een naam onder de beschrijving „Gavėjas" (Litouws) of „Prejemnik"
  (Sloveens) bleef gedeeltelijk of helemaal onontdekt, wanneer de
  achternaam tegelijk een gangbaar woord was (bijv. „Vilkas" = wolf).
  Zoals al bij „Primatelj" (Kroatisch) en „Modtager" (Deens) wordt de
  naam nu volledig herkend.

- Een rondzendbrief-kopregel zoals „To All Staff" of „To All Employees"
  werd ten onrechte als persoonsnaam herkend en verwijderd. Dat komt
  nu niet meer voor.

- Een naam onder de beschrijving „Primatelj" (Kroatisch) of „Modtager"
  (Deens) bleef gedeeltelijk onontdekt, wanneer de achternaam tegelijk
  een gangbaar woord was (bijv. „Golub" = duif, „Bager" = bakker).
  Zoals al bij „Odbiorca" (Pools) en „Destinatar" (Roemeens) wordt de
  naam nu volledig herkend.

- Een volledige naam in de handtekeningregel van een Deens, Noors of
  Grieks document bleef gedeeltelijk onontdekt, wanneer de beschrijving
  „Underskrift" of „Υπογραφή" alleen boven de naam stond – in het
  Griekse geval werd de achternaam zelfs als plaatsaanduiding in plaats
  van als naam herkend. Zoals al bij „Подпись" (Russisch) wordt de naam
  nu volledig herkend.

- Tekst op een zijwaarts opgeslagen telefoonfoto (de gebruikelijke
  staande opname, die alleen via een beeldrotatiemarkering rechtop
  wordt getoond) kon door de tekstherkenning over het hoofd worden
  gezien, omdat ze tot nu toe de ruwe, liggende beeldpunten las. Zulke
  foto's worden nu vóór het lezen goed rechtgedraaid – zoals eerder al
  bij de gezichtsherkenning.

- Een volledige naam in de handtekeningregel van een Russisch,
  Oekraïens of Litouws document bleef gedeeltelijk onontdekt, wanneer
  de beschrijving „Подпись", „Підпис" of „Parašas" alleen boven de naam
  stond – voor- of vadersnaam vielen weg. Zoals al bij „Potpis"
  (Kroatisch) wordt de naam nu volledig herkend.

- Een gezicht op een zijwaarts opgeslagen telefoonfoto (de
  gebruikelijke staande opname, die alleen via een
  beeldrotatiemarkering rechtop wordt getoond) kon door de
  gezichtsherkenning over het hoofd worden gezien, omdat ze tot nu toe
  de ruwe, liggende beeldpunten controleerde. Zulke foto's worden nu
  vóór de zoektocht goed rechtgedraaid.

- Een volledige naam in de handtekeningregel van een Kroatisch document
  bleef gedeeltelijk onontdekt, wanneer de beschrijving „Potpis"
  alleen boven de naam of met dubbele punt ervoor stond – de voornaam
  viel weg, ongeacht of als eigen regel of in „Potpis: Voornaam
  Tweede naam Achternaam". Zoals al bij „Unterschrift" en „Signature"
  wordt de naam nu volledig herkend.

- Een huwelijksnaam achter de burgerlijke-staat-afkortingen „verh."
  (gehuwde) en „verw." (weduwe/weduwnaar) bleef tot nu toe volledig
  onontdekt staan, ongeacht of tussen haakjes, achter komma of zonder
  spatie aangeplakt („Anna Meier (verh. Weber)", „Klaus Bauer
  (verw.Fischer)") – zoals al bij „geb." wordt ze nu betrouwbaar
  herkend.

- Een naam achter de procuratietekening „ppa." (bijv. in de
  handtekeningregel van een zakelijke e-mail of zakelijke brief) bleef
  bij een beroepsnaamgelijke achternaam zoals „Bauer" of „Koch" tot nu
  toe gedeeltelijk of helemaal onontdekt staan – zoals al bij „gez."
  wordt ze nu betrouwbaar herkend.

- Het nummer van de Poolse identiteitskaart (dowód osobisty) werd alleen
  zonder spatie tussen serie en nummer herkend („ABS123456"). Precies
  zo drukt het document de aanduiding echter niet af – officieel staat
  daar een spatie tussenin („ABS 123456"), en in deze schrijfwijze bleef
  het nummer tot nu toe onontdekt.

- Een geanimeerde PNG (APNG, bijv. een als PNG in plaats van GIF
  opgeslagen korte schermopname) werd tot nu toe alleen met haar eerste
  beeld gecontroleerd en opgeschoond, zonder dat dit werd gemeld – zoals
  eerder bij de geanimeerde WebP meldt Maskuro nu dat elk verder beeld
  ongecontroleerd in het resultaat blijft staan.

- Een geanimeerde WebP-afbeelding (bijv. uit een screenshotwerktuig of
  een chattoepassing met meerdere beelden in één bestand) werd tot nu
  toe alleen met haar eerste beeld gecontroleerd en opgeschoond, zonder
  dat dit werd gemeld – zoals eerder bij een meerpagina's tellende TIFF
  meldt Maskuro nu dat elk verder beeld ongecontroleerd in het
  resultaat blijft staan.

- Een Sloveense dubbele voornaam met koppelteken („Ana-Marija Novak")
  verloor haar voorste helft, zodra er in de tekst lopende tekst
  voorafging – dezelfde fout als eerder bij Pools. „Ana-" bleef
  onvervangen in klare tekst staan, terwijl de rest van de naam al
  werd vervangen.

- Een Poolse dubbele voornaam met koppelteken („Anna-Maria Kowalska")
  verloor haar voorste helft, zodra er in de tekst lopende tekst of een
  voorzetsel zoals „z"/„od" voorafging – de rest van de naam werd
  vervangen, „Anna-" bleef onvervangen in klare tekst staan.

- Kazachse beleefdheidsvormen „Хабарласыңыз"/„Байланысыңыз" (neem
  contact met ons op) evenals Servische werkwoordsvormen „Помоћи",
  „Чекамо" en „Пишите" zonder eigen taalherkenningsmodel werden in
  telefoonzinnen ten onrechte als persoonsnaam of plaats herkend.

- Azerbeidzjaans beleefdheidswoord „Xahiş" (verzoek) zonder eigen
  taalherkenningsmodel werd in telefoonzinnen ten onrechte als
  persoonsnaam herkend.

- Indonesische en Maleisische beleefdheids-/gebiedende-wijswoorden
  zonder eigen taalherkenningsmodel zoals „Silakan", „Mohon"
  (Indonesisch), „Sila" en „Tolong" (Maleisisch) werden in
  telefoonzinnen ten onrechte als persoonsnaam of plaats herkend.

- Oezbeekse gebiedende-wijsvorm „Kutamiz" (wij wachten) zonder eigen
  taalherkenningsmodel werd in telefoonzinnen ten onrechte als plaats
  herkend.

- Turkse gebiedende-wijsvormen zonder eigen taalherkenningsmodel zoals
  „Arayınız" (bel ons) en „Bekliyoruz" (wij wachten) werden in
  telefoonzinnen ten onrechte als persoonsnaam herkend.

- Gebiedende-wijsvormen in verdere talen zonder eigen
  taalherkenningsmodel (Tsjechisch, Slowaaks, Grieks) zoals „Zavolejte"
  (bel), „Prosíme" (wij vragen) en „Περιμένουμε" (wij wachten) werden
  in telefoonzinnen ten onrechte als persoonsnaam of plaats herkend.

- Hongaarse en Poolse gebiedende-wijsvormen zoals „Hívjon" (bel),
  „Kérjük" (wij vragen), „Várjuk" (wij verwachten), „Zadzwoń" (bel) en
  „Czekamy" (wij wachten) werden in telefoonzinnen ten onrechte als
  persoonsnaam of plaats herkend.

- In een genummerde namenlijst zonder tabelvorm (bijv. „1. Robert
  Brown", daaronder „2. Mary Johnson") werd een naam met bepaalde
  Engelse achternamen (o.a. „Brown", „White", „Green", „Black",
  „Young") volledig over het hoofd gezien – het taalmodel had het
  nummer van de volgende regel aan de naam gehecht, waardoor de
  treffer nooit meer precies paste.

- Bij het Poolse taalmodel bleef het voorafgaande voornaamsinitiaal vóór
  een achternaam (bijv. „J. Kowalski", „A. Nowak") onherkend en
  niet opgeschoond in de tekst staan – alleen de achternaam werd vervangen.
  Andere geteste talen (o.a. Duits, Engels, Roemeens, Kroatisch,
  Hongaars, Russisch) namen hetzelfde initiaal al eerder mee.

- Een persoonsnaam achter een kleingeschreven titel zoals „dr.", „ing."
  of „dipl. ing." werd in het Hongaars, Roemeens en Kroatisch helemaal
  niet herkend – niet alleen de titel, maar de hele naam ging verloren
  (bijv. „dr. Kovács Béla", „ing. Andrei Popescu", „dipl. ing. Marko
  Horvat").
- In Sloveense vergaderverslagen werd een pure rolbenaming vóór de
  dubbele punt (bijv. „Tajnik:", „Podpredsednik:", „Poročevalec:",
  „Predsedujoči:") ten onrechte als persoonsnaam herkend, zodra elders
  in het verslag al een echte sprekersnaam stond.
- In Russische vergaderverslagen werd een pure rolbenaming vóór de
  dubbele punt (bijv. „Секретарь:", „Докладчик:", „Докладчица:") ten
  onrechte als persoonsnaam herkend, zodra elders in het verslag al een
  echte sprekersnaam stond.
- In Roemeense vergaderverslagen werd een pure rolbenaming met bepaald
  lidwoord vóór de dubbele punt (bijv. „Secretarul:", „Președintele:",
  „Vicepreședintele:", „Moderatorul:", „Consilierul:") ten onrechte als
  persoonsnaam herkend – „Președintele" al op zichzelf, de overige
  bovendien zodra elders in het verslag al een echte sprekersnaam
  stond.
- In Kroatische vergaderverslagen werd een pure rolbenaming vóór de
  dubbele punt (bijv. „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:",
  „Predsjedavajući:") ten onrechte als persoonsnaam herkend.
- Een Pools postbusadres „Skrytka pocztowa" achter een afzender- of
  ontvangerbeschrijving (bijv. „Odbiorca: Skrytka pocztowa 45") werd
  ten onrechte als persoonsnaam herkend.
- Een Kroatisch postbusadres „Poštanski pretinac" achter de
  adresbeschrijving „Adresa:" (bijv. „Adresa: Poštanski pretinac 45",
  ook met aangehecht „br." voor het nummer) werd ten onrechte als
  persoonsnaam herkend.
- Een plaats zonder verdere beschrijving in Noorse lopende tekst (bijv.
  „Anna Hansen bor i Oslo") werd niet herkend – het eigen taalmodel
  benoemt plaatsen daar meestal met een eigen, tot nu toe niet
  toegewezen label in plaats van het gebruikelijke „LOC".
- Een datum in de ISO-volgorde jaar-maand-dag met koppelteken of punt
  (bijv. „2024-12-31") werd in sommige talen helemaal niet als datum
  herkend – het opvallendst in het Litouws, waar officiële brieven
  data overwegend in deze volgorde vermelden.
- Een Hongaars btw-nummer (közösségi adószám) in de officieel even
  geldige, scheidingstekenloze 11-cijferige vorm (bijv. „12345678123"
  in plaats van „12345678-1-23") werd niet herkend.
- Een Pools belastingnummer NIP met de scheidingstekens in de
  groepering 3-2-2-3 (bijv. „856-73-46-215", zoals gebruikelijk op
  facturen van bedrijven en eenmanszaken) werd niet herkend – alleen de
  groepering 3-3-2-2 voor natuurlijke personen trof raak.
- Een bedrijfsnaam onder de Slowaakse veldbeschrijving
  „Zamestnávateľ:" of „Názov zamestnávateľa:" (werkgever/bedrijf) werd
  niet herkend.
- Een bedrijfsnaam onder de Roemeense veldbeschrijving „Angajator:" of
  „Denumire angajator:" (werkgever/bedrijf) werd niet herkend.
- Een bedrijfsnaam onder de Hongaarse veldbeschrijving „Cég:" of
  „Munkáltató:" (bedrijf/werkgever) werd niet herkend.
- Een bedrijfsnaam onder de Poolse veldbeschrijving „Pracodawca:" of
  „Nazwa firmy:" (werkgever/bedrijf) werd niet herkend.
- Een bedrijfsnaam onder de Sloveense veldbeschrijving „Podjetje:" of
  „Delodajalec:" (bedrijf/werkgever) werd niet herkend.
- Een bedrijfsnaam onder de Kroatische veldbeschrijving „Tvrtka:" of
  „Poslodavac:" (bedrijf/werkgever) werd niet herkend.
- Een voluit geschreven geldbedrag met kleingeschreven valuta (bijv.
  „500 euro") werd niet herkend, alleen de hoofdletterschrijfwijze
  („Euro") trof raak.
- De achternaam achter „zwager"/„schoonzus" (bijv. „De zwager Bauer
  krijgt de erfenis.") werd niet herkend.
- Bij een Turks adres zonder scheidend leesteken tussen postcode+plaats
  en straat+huisnummer (bijv. „34000 İstanbul İstiklal Caddesi No: 45")
  bleef het huisnummer niet opgeschoond staan.
- Bij een Slowaaks adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „831 01 Bratislava
  Hlavná 15") bleef het huisnummer niet opgeschoond staan.
- Een geboorteland zonder verdere beschrijving in een Kroatisch
  formulierveld (bijv. „Zemlja rođenja: Njemačka") werd niet herkend.
- Een geboorteland zonder verdere beschrijving in een Litouws
  formulierveld (bijv. „Gimimo valstybė: Vokietija") werd niet herkend.
- Een geboorte- of woonland zonder verdere beschrijving in een Pools
  formulierveld (bijv. „Kraj: Niemcy") werd niet herkend.
- Een nationaliteits- of woonplaats zonder verdere beschrijving in een
  Sloveens formulierveld (bijv. „Državljanstvo: Nemčija") werd niet
  herkend.
- Een woonland zonder verdere beschrijving in een Noors formulierveld
  (bijv. „Bosted: Tyskland") werd niet herkend.
- Nieuwe instellingenpagina „Meldingen" (voorheen een sectie in
  „Programma"): de drie taakbalkmeldingen (voorbeeld klaar, verwerking
  voltooid, actualisering gedownload) staan nu op een eigen plek.
- Nieuw: het resultaat kan bovendien als platte tekstbestand (.txt) of
  met de extensie .md ernaast worden opgeslagen – voor verdere
  verwerking in een AI of een ander programma.
- Bij een Kroatische contactaanduiding met de beschrijving „Osoba za
  kontakt"/„Kontakt osoba" (bijv. „Osoba za kontakt: Golub Marko")
  bleef de naam volledig onherkend, wanneer de achternaam tegelijk een
  gangbaar zelfstandig naamwoord was (Golub = „duif").

- Bij een Roemeense contactaanduiding met de beschrijving „Persoana de
  contact"/„Persoană de contact" (bijv. „Persoana de contact: Lup
  Ion") bleef de naam volledig onherkend, wanneer de achternaam
  tegelijk een gangbaar zelfstandig naamwoord was (Lup = „wolf") en de
  voornaam zeer kort en generiek.

- Bij een Poolse contactaanduiding met de beschrijving „Osoba
  kontaktowa"/„Osoba do kontaktu" (bijv. „Osoba kontaktowa: Wilk
  Adam") bleef de achternaam onherkend, wanneer ze tegelijk een
  gangbaar zelfstandig naamwoord was (Wilk = „wolf", Zielony =
  „groen").

- Bij een Roemeens adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „010061 București Strada
  Victoriei 30") bleef het huisnummer niet opgeschoond staan.
- Bij een Servisch adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „11000 Beograd Bulevar
  Kralja Aleksandra 73") bleef het huisnummer niet opgeschoond staan.
- Bij een Grieks adres zonder scheidend leesteken tussen postcode+plaats
  en straat+huisnummer (bijv. „104 32 Αθήνα Ερμού 15") bleef het
  huisnummer niet opgeschoond staan.
- Bij een Sloveens adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „1000 Ljubljana
  Slovenska cesta 58") bleef de postcode niet opgeschoond staan.
- Bij een Litouws adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „LT-01100 Vilnius
  Gedimino pr. 9") bleef de postcode volledig niet opgeschoond staan.
- Bij een Hongaars adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „1052 Budapest Kossuth
  Lajos utca 12") bleef de postcode niet opgeschoond staan.
- Een achternaam achter „erfgenamen" (bijv. „De erfgenamen Wagner
  ontvingen de mededeling tijdig.") bleef in erfenis-/nalatenschapscontext
  zo goed als altijd onherkend.
- Een achternaam achter „broers en zussen" (bijv. „De broers en zussen
  Bauer wonen in Linz.") bleef tot nu toe zo goed als altijd onherkend
  – anders dan bij „familie"/„echtpaar" trof dat niet alleen
  beroepswoordgelijke namen (Koch, Bauer, Richter), maar willekeurige
  achternamen op deze plek.
- Een achternaam achter „echtpaar" (bijv. „Het echtpaar Koch verhuist.")
  bleef onherkend, wanneer ze tegelijk een gangbaar zelfstandig
  naamwoord of een beroepsbenaming was (Koch, Bauer, Richter).
- Een gewoon bestel-, order- of artikelnummer in het typische
  groeperingsraster van een belastingnummer of
  socialezekerheidsnummer (bijv. „030 4471 2298") werd zonder enige
  bijbehorende beschrijving ten onrechte als zodanig gezwart.
- Een bewijsstuk-/procesnummer in de vorm „jaar/volgnummer" (bijv. in
  „Factuur nr. 4/2024/778899") werd door de telefoonnummerherkenning
  ten onrechte als telefoonnummer gezwart.
- Een naam achter „De heer"/„Mevrouw" met een meerwoordige academische
  titelketen ervoor („De heer Dr. med. Weber", „De heer Prof. Dr.
  Krause") bleef tot nu toe volledig onbeschermd staan – herkend werd
  tot nu toe slechts één los titelwoord tussen aanhef en naam.
- Een gerechtelijk dossiernummer in het klassieke formaat met
  kamer-/senaatsafkorting („4 Ca 1523/24", „Az.: 7 O 234/25") bleef tot
  nu toe volledig onbeschermd staan – ook de gebruikelijke korte vorm
  „Az."/„Gz." werd naast de voluit geschreven beschrijving niet
  herkend.
- Een creditcardnummer die midden in haar viergroepering door een
  regelafbreking werd gescheiden – bijvoorbeeld in een smalle
  tabelkolom –, bleef tot nu toe volledig onbeschermd staan.
- Een fiscaal identificatienummer dat midden in zijn groepering door
  een regelafbreking werd gescheiden – bijvoorbeeld in een smalle
  tabelkolom of een formulierveld –, bleef tot nu toe volledig
  onbeschermd staan.
- Een socialezekerheidsnummer dat midden in zijn groepering door een
  regelafbreking werd gescheiden – bijvoorbeeld in een smalle
  tabelkolom –, bleef tot nu toe volledig onbeschermd staan, zelfs niet
  gedeeltelijk vervangen.
- Een huisnummer met bereik zoals „12a-14b" of „3-5" werd maar voor de
  helft vervangen – het tweede deel achter het koppelteken bleef open
  in het resultaat staan.
- Een chassisnummer (FIN/VIN) dat midden in zijn 17 tekens door een
  regelafbreking, spatie of koppelteken werd gescheiden – bijvoorbeeld
  in een smalle tabelkolom of een kentekenbewijsveld –, bleef tot nu
  toe volledig onbeschermd staan.
- Een brief-/mailaanhef zoals „Beste Anna!" of „Lieve Hans" – zonder
  komma na de naam, de meest voorkomende vorm in losse mails – liet de
  naam volledig onbeschermd staan, ook in het volledige document met
  lopende tekst en groetformule eronder.
- Hetzelfde gat trof ook de losse chat-/mailaanheffen „Hallo Anna!",
  „Hi Anna!", „Hey Anna!" en „Servus Anna!" zonder komma – de naam
  bleef eveneens volledig onbeschermd staan.
- Een puur handtekeningblok dat direct met „Mvg" of „Hartelijke groet"
  begint – bijvoorbeeld gekopieerd uit het klembord, zonder
  voorafgaande zin – liet de naam eronder volledig onbeschermd staan.
- Een veld met meerdere personen, bijvoorbeeld „Familieleden: Kaczmarek, Piotr (Zoon), Kaczmarek, Anna (Echtgenote)", versmolt beide namen samen met
  de aanduiding tussen haakjes tot één enkele, veel te lange treffer –
  de tweede naam bleef daarbij deels onbeschermd in het resultaat
  staan.
- Een straat zonder „-straat"/„-weg"-achtervoegsel – zoals op het
  platteland gebruikelijk, bijvoorbeeld „Am Marktplatz 5" of „Im
  Grund 12" – bleef onherkend, wanneer er een postcode-plaatsregel op
  volgde, bijvoorbeeld in een verhuisbewijs: „Nieuw adres: Am
  Weidengarten 17, 54295 Trier" verloor de straat volledig, alleen de
  postcode werd verwijderd.
- Een naam achter een samengestelde veldbeschrijving met schuine streep
  (bijvoorbeeld „Naam/Voornaam: Bauer Klaus") werd deels niet herkend –
  een meerduidige achternaam zoals „Bauer" bleef zonder het veldbewijs
  onontdekt. Hetzelfde gat trof combinatievelden zoals „Postcode/Plaats:
  04109 / Leipzig". Hetzelfde gold voor combinatievelden met voluit
  geschreven verbindingswoord in plaats van schuine streep, bijvoorbeeld
  „Voor- en achternaam: Bauer Klaus" of „Achternaam resp. voornaam: …".
- Een geboortedatum in de vorm „Datum van geboorte: …" en een
  overlijdensdatum in de vorm „Overlijdensdatum: …" of „Datum van
  overlijden: …" werden niet herkend – alleen „Geboortedatum: …" resp.
  „Overlijdensdatum: …" trof raak.
- Een huwelijksdatum in de vorm „Datum van het huwelijk: …" werd niet
  herkend – alleen „Huwelijksdatum: …" en „Datum van
  huwelijkssluiting: …" trof raak, hoewel echtscheidings-,
  naturalisatie- en geregistreerd-partnerschapsdatum dezelfde „Datum
  van X"-vorm allang kenden.
- Een echtscheidingsdatum in de vorm „Datum van de scheiding: …" werd
  niet herkend – alleen „Echtscheidingsdatum: …" en de nagestelde
  werkwoordsvorm trof raak, hoewel naturalisatie- en
  geregistreerd-partnerschapsdatum dezelfde „Datum van X"-vorm van meet
  af aan kenden.
- Een geregistreerd-partnerschapsdatum werd tot nu toe helemaal niet
  herkend – noch met beschrijving („Datum geregistreerd partnerschap:
  …", „Datum van het partnerschap: …") noch in lopende tekst („… zijn
  op … een geregistreerd partnerschap aangegaan"). Nu wordt het net als
  geboorte-, huwelijks-, echtscheidings- en naturalisatiedatum als
  eigen soort gegeven vervangen.
- Een naturalisatiedatum werd tot nu toe helemaal niet herkend – noch
  met beschrijving („Naturalisatiedatum: …") noch in lopende tekst („…
  werd op … genaturaliseerd"). Nu wordt het net als geboorte-,
  huwelijks- en echtscheidingsdatum als eigen soort gegeven vervangen.
- Een echtscheidingsdatum werd tot nu toe helemaal niet herkend – noch
  met beschrijving („Echtscheidingsdatum: …") noch in lopende tekst
  („Het huwelijk werd op … ontbonden"). Nu wordt het net als geboorte-,
  overlijdens- en huwelijksdatum als eigen soort gegeven vervangen.
- Een huwelijksdatum achter het genealogische huwelijksteken „⚭" zonder
  beschrijving werd niet herkend, hoewel geboorte- en overlijdensdatum
  in dezelfde regel via ster en kruis al werden herkend – nu wordt ook
  het huwelijksdatum herkend.
- Een overlijdensdatum achter het rouwadvertentiekruis zonder
  beschrijving („*03.06.1940 †21.11.2023") werd niet herkend, hoewel de
  geboortedatum ervoor via de genealogische ster al werd herkend – nu
  wordt ook het overlijdensdatum herkend.
- Achternaam vóór voornaam aan het einde van een onderwerp-/ticketregel
  met voorafgaande zakelijke tekst en verbindingsstreepje („Onderwerp:
  Klacht - Bauer, Anna") werd bij een beroepsnaamgelijke achternaam niet
  herkend – nu wordt hij herkend.
- Sollicitanten- en aanvraagnummers achter hun beschrijving
  („Sollicitantnummer: 4471829", „Aanvraagnummer: 7654321") vielen
  volledig door de herkenning – nu worden ze herkend.
- Vervangen zwart niet meer wanneer er geen plaats is voor een leesbare
  plaatshouder – een te kleine plaatshouder wordt nu kleiner
  geschreven in plaats van een lege balk te worden, zolang er
  überhaupt plaats overblijft. Nieuw bovendien: of een vindplaats op
  een afbeelding (briefkop, scanachtergrond) wordt beschreven of alleen
  gezwart, is nu onafhankelijk van het overige resultaattype in te
  stellen. En een vindplaats op een afbeelding die helemaal wordt
  verwijderd, werd beschreven alsof de afbeelding bleef staan – de
  plaatshouder stond licht op een grond die nooit werd gezwart, en
  verdween zo onzichtbaar op het nu witte papier.
- Een vindplaats op een **behouden** afbeelding werd bij het vervangen
  altijd zwart-wit gezwart, ongeacht de gekozen weergave
  (categoriekleuren, regenboog …) – zichtbaar als breuk tussen
  kleurrijke labels in de lopende tekst en zwarte balken op de
  briefkop. De beeldgrond volgt nu dezelfde kleur als de plaatshouder
  ernaast.
- De herkenning van het voertuigidentificatienummer (FIN/VIN)
  markeerde elke 17-cijferige alfanumerieke code zonder I/O/Q
  onvoorwaardelijk als chassisnummer – ook order-, serie- en
  licentiesleutelnummers, die toevallig dezelfde vorm hebben. Nu telt
  ze alleen nog mee met een contextwoord in de buurt („FIN", „VIN",
  „Chassisnummer" e.d.).
- In ticket-/agendasystemen trok de naamherkenning achter „Assigned
  to"/„Closed by" e.d. het volgende veldwoord mee, wanneer het in
  dezelfde regel zonder scheidingsteken direct volgde („Assigned to Max
  Mustermann Priority High" werd „Max Mustermann Priority"). In
  Git-commitkopregels trok de naamherkenning eveneens de **volgende**
  trailer-sleutel mee, wanneer twee regels met slechts een spatie in
  plaats van een regelafbreking aan elkaar hingen („Author: julia
  bergmann Reviewed-by: …" werd „julia bergmann Reviewed-by"). Beide
  remmen aangevuld.
- De naam achter „p.A.", „t.a.v.", „i.o." en „geb." trok een direct
  volgend afdelingswoord mee in dezelfde treffer, wanneer het zonder
  scheidingsteken in dezelfde regel stond („p.A. Max Mustermann
  Boekhouding" werd „Max Mustermann Boekhouding", „i.o.Max Mustermann
  Verkoop" werd „Max Mustermann Verkoop"). Dezelfde rem als bij
  „Assigned to"/Git-trailers nu ook hier aangevuld.
- Een beschreven IBAN direct boven de BIC-, bankcode- of SWIFT-regel
  trok haar beschrijving mee in haar eigen treffer, omdat „BIC" en
  bankcode-aanduidingen er zelf uitzagen als een verder nummerblok –
  van „IBAN: DE89 … 0130 00" en de regel eronder werd één enkele, te
  ver reikende treffer, en de beschrijving van de volgende regel
  verdween bij het opschonen mee. Getroffen was vrijwel elke
  bankrelatie met IBAN en BIC onder elkaar.
- Het trefpaneel zegt nu **waar** een plaatshouder staat die het niet
  op de pagina kan vinden. Twee gevallen meldden tot nu toe alleen
  „niet gevonden", hoewel de vervanging plaatsvond: staat de
  plaatshouder in niet-zichtbare bijtekst – bijvoorbeeld het
  verwijzingsadres van een link, een opmerking of een formulierveld –,
  dan draagt de regel dat nu als eigen mededeling („in bijtekst"), en
  de klik legt het uit. En werd de plaatshouder bij plaatsgebrek
  ingekort geschreven („[N382]" in plaats van „[NAM382]"), dan springt
  de klik op de lange regel nu naar de kortevormplek en noemt de
  hernoeming; de toewijzing verweeft daarvoor beide regels
  uitdrukkelijk met elkaar.
- Staat dezelfde vervangwaarde meermaals in het document, dan springt
  elke verdere klik op de paneelregel in een kring naar de volgende
  vindplaats – ook over paginagrenzen heen; de statusregel telt mee
  („Vindplaats 2 van 4"), en de zojuist aangestuurde plek is
  intensiever omkaderd dan de overige. En wanneer een plaatshouder
  alleen in de treflijst staat, maar nergens in het document (omdat de
  plek in een overlappende vervanging opging), zegt de statusregel dat
  nu, in plaats van dat de klik stil zonder gevolg blijft.
- Een afgekorte voornaam achter „aan" of „voor" wordt nu betrouwbaar
  als naam herkend – „Overschrijving aan M. Wagner" en „Factuur voor M.
  Wagner" bleven tot nu toe vaak niet opgeschoond staan, terwijl dezelfde
  naam met een andere beschrijving ervoor (bijvoorbeeld „Begunstigde:")
  al werd gevonden. Getroffen waren vooral rekeningafschrift- en
  boekingsregels.
- „Verdachte"/„Beklaagde" gelden nu als naamveld: stond een naam in
  strafproceduredocumenten direct achter een van deze beschrijvingen,
  dan werd hij tot nu toe voor ongeveer de helft van de geteste namen
  helemaal niet herkend – noch voor- noch achternaam.
- De door het trefpaneel aangeklikte plek wordt nu blauw omkaderd in
  plaats van geel gemarkeerd – op de gekleurde stoplichtvlakken was het
  geel van de zoektreffer niet te herkennen. Bovendien vindt de klik nu
  ook meerwoordige vervangwaarden (verzonnen namen, gemaskeerde
  nummers): tot nu toe bleef hij bij zulke regels zonder effect, omdat
  de vindplaats alleen woord voor woord werd gezocht.
- Adoptie-, pleeg- en stiefouders („adoptievader", „pleegmoeder",
  „stiefvader" en meer) worden nu als naamveld herkend, de naam viel
  voorheen niet opgeschoond door
- Cijferrijke tabellen en lijsten worden niet meer ten onrechte
  verworpen: werd een kort getal (bijvoorbeeld een als telefoonnummer
  verkeerd gelezen deel van een klantnummer) vervangen, dan meldde de
  slotcontrole dezelfde cijferreeks ook dan als resterend gegeven
  wanneer die elders alleen toevallig in een heel ander nummer zat – en
  leverde dan helemaal geen resultaat. Een getal telt nu alleen nog als
  restant waar het als los getal staat.
- Burgerlijke-standakten: „Vader:"/„Moeder:" wordt nu als naamveld
  herkend, de oudernaam viel voorheen niet opgeschoond door
- Verdere familierollen („peetouder", „grootvader/-moeder",
  „echtgenoot/echtgenote", „partner", „oom", „tante") worden nu als
  naamveld herkend, de naam viel voorheen niet opgeschoond door
- De Duitse bankcode wordt nu ook officieel gegroepeerd herkend ("370
  400 44", "370.400.44", "370-400-44", "370/400/44"), niet meer alleen
  als acht aaneengesloten cijfers.
- Het Duitse pensioenverzekeringsnummer wordt nu ook met punt,
  koppelteken of schuine streep tussen de vijf blokken herkend
  ("65-170839-J-08-8", "65.170839.J.08.8"), niet meer alleen met
  spatie.
- Het hoofdvenster verschijnt sneller: de herkenningsbibliotheken
  (Presidio samen met de taalmodel-onderbouw) werden tot nu toe al bij
de vensteropbouw geladen – op Windows ongeveer vier seconden voordat er
  überhaupt iets te zien was. Ze laden nu volledig op de achtergrond; de
  knop „Opschonen" wordt zoals voorheen pas vrij wanneer alles klaarstaat.
- Officedocumenten met veel afbeeldingen of video's worden sneller
  geschreven: al gecomprimeerde media worden in het resultaatpakket
  opgeslagen in plaats van nutteloos een tweede keer gecomprimeerd –
  dat bespaarde tot nu toe geen enkele byte en maakte JPEG's eerder
  groter.
- Spreadsheets en andere documenten uit veel kleine tekseenheden worden
  sneller gecontroleerd: de taalherkenning verwerkt alle cellen en
  alinea's van een document nu in één doorloop in plaats van
  afzonderlijk – bij aantoonbaar dezelfde vondsten (400 cellen: van
  ongeveer 4,7 naar 2,5–3,5 seconden).
- Lijstachtige PDF-pagina's (registers, positielijsten) zijn bij het
  invoegen van de plaatshouders aanzienlijk sneller: de plaatszoektocht
  per beschrijving liep tot nu toe over alle woorden van de pagina –
  nu alleen nog over de regelomgeving, bij aantoonbaar gelijk resultaat
  (op een pagina met 300 beschrijvingen ongeveer zestien keer sneller).
- Beeldrijke documenten besparen meerdere onnodige werkstappen per
  afbeelding: het tellen van gezichten en codes op PDF-pagina's
  decodeert de pagina-afbeelding niet meer dubbel, het controleren op
  metagegevens ontsleutelt een schone afbeelding helemaal niet meer,
  gepixeleerde afbeeldingen worden met de normale in plaats van de
  traagste PNG-compressie geschreven (gelijke grootte, een derde van de
  tijd), en zonder ingesteld watermerk vervalt het nutteloze opnieuw
  schrijven van de hele PDF aan het einde.
- Gescande PDF's met ingeschakelde tekstherkenning zijn aanzienlijk
  sneller klaar: elke pagina werd tot nu toe tweemaal in volledige
  resolutie gerenderd (eenmaal om te lezen, eenmaal om te rasteren) –
  de afbeelding wordt nu hergebruikt. En op Windows/Linux leest de
  tekstherkenning de banden van een grote scan in één doorloop in
  plaats van met een eigen programmastart per band.
- Grote documenten worden aanzienlijk sneller opgeschoond: de
  vergelijking van al gevonden waarden groeide tot nu toe met het
  aantal vindplaatsen (een 64-KB-tekstblok kostte aan het einde van een
  groot bestand ongeveer een seconde alleen daarvoor, nu een
  zestigste), en de zoektocht naar bedrijfsrechtsvormen liep met alle
  ~280 catalogusvormen over elke tekstplek (nu ongeveer twintig keer
  sneller, bij aantoonbaar dezelfde vondsten).
- Een naam direct na „Met vriendelijke groet"/„Beste wensen" zonder
  voorafgaande tekst of leesteken werd helemaal niet herkend – een puur
  handtekeningblok zonder lopende tekst ervoor liet de naam spoorloos
  verdwijnen.
- Een adresveld aan het begin van het document met een
  beroepsnaamgelijke achternaam („Bauer Anna", „Koch Stefan" als eerste
  regel boven straat en plaats) bleef tot nu toe deels onherkend of
  werd als plaatsaanduiding in plaats van als persoon ingedeeld –
  zonder voorafgaande zin ontbrak het taalmodel de zinsbouw die „Bauer"
  anders als naam en niet als beroep laat herkennen.
- Een naam achter de handtekeningmarkering „gez." met een
  beroepsnaamgelijke achternaam vóór de voornaam („gez. Bauer Anna" aan
  het einde van een beschikking of vonnis) bleef tot nu toe onvolledig
  herkend – alleen de voornaam werd gevonden, de achternaam verdween
  spoorloos.
- Een naam direct achter een klantnummer, contractnummer of
  soortgelijk kenmerk zonder eigen regel („Contractnummer 55219 Bauer
  Anna", „Klantnr. 4711 Bauer Anna") werd bij een beroepsnaamgelijke
  achternaam tot nu toe onvolledig of helemaal niet herkend.
- Het symbool in de macOS-menubalk is nu een sjabloon die zich net als
  de buursymbolen aan lichte en donkere modus aanpast – met de twee
  uitgestanste balken blijft het daarbij als Maskuro herkenbaar. Loopt
  de klembordwachter, dan toont dat een apart punt aan de schildpunt.
- Een klik in het trefpaneel leidt nu ook in de anonimiserende
  werkwijze naar de vindplaats: pagina wisselen, naar de afbeelding
  rollen, geel markeren. Tot nu toe bleef de klik daar zonder gevolg,
  omdat hij de plaatshouders nog voor nummerloos hield – sinds elke
  vindplaats haar eigen nummer draagt, is de plek eenduidig. Alleen bij
  de daadwerkelijk nummerloze plaatshouder legt de statusregel verder
  uit waarom geen sprongdoel bepaalbaar is.
- Het eerste opslaan in de nabewerkingseditor (Ctrl+S of de
  diskette-knop) vraagt nu naar de plek, zoals „Opslaan als …" –
  vooraf ingevuld met de map van het origineel en de resultaatnaam. Tot
  nu toe belandde het bestand zonder woord naast het origineel. Wie de
  opslaglocatie al eerder via de statusregel heeft gekozen, wordt niet
  nog eens gevraagd; elk verder opslaan schrijft zoals voorheen
  hetzelfde bestand verder.
- Meldt de veiligheidscontrole vóór het opslaan een opvallende plek,
  dan leidt „Terug naar controle" er nu naartoe: de eerste vindplaats
  rolt in beeld en wordt rood omkaderd, de statusregel noemt haar. Tot
  nu toe bleef men alleen met paginanummer en puntcoördinaten achter.
  Vanuit het hoofdvenster opent daarvoor de editor op die plek. Ook bij
  de aanwijzing over een afwijkend paginanummer leidt de knop nu
  ernaartoe – naar de eerste pagina die er alleen in een van beide
  documenten is.
- Wie het voorbeeld omschakelt naar „Naast elkaar in twee kolommen",
  krijgt nu vanzelf een venster waar beide banen in passen – tot nu toe
  perst men zich in de oude breedte, totdat men zelf trok. Verbreed
  wordt hoogstens tot de schermrand en nooit teruggesmald; een zelf
  getrokken breedte blijft staan.
- Achternaam en voornaam in aparte tabelkolommen (bijv. „Achternaam |
  Voornaam" in een aanmeldbevestiging of een CSV-export) bleven open –
  elke cel op zich zag er voor de herkenning uit als een willekeurig
  woord zonder naamverband. Worden nu herkend.
- Naam en voornaam op de achterkant van een EU-kaartrijbewijs bleven
  open – ze staan daar achter de officiële veldcodes „1." en „2." in
  plaats van achter een Duits woord, en juist dat liet ze onherkend.
  Worden nu herkend, als het rijbewijsnummer (veldcode „5.") ernaast
  staat.
- De voornaam van de voertuighouder op het kentekenbewijs bleef open –
  hij staat achter de officiële veldcode „C.1.2" in plaats van achter
  een Duits woord zoals „Voornaam", en juist dat liet hem onherkend.
  Achternaam en voornaam onder de veldcodes C.1, C.1.1 en C.1.2 worden
  nu herkend.
- De eerste regel van het machineleesbare gebied (MRZ) op paspoort of
  identiteitskaart bleef open – ze draagt de naam in de vorm
  „ACHTERNAAM<<VOORNAAM" en glipte ook met de nieuwe MRZ-herkenner voor
  de controlecijferregel volledig door. Een vondst telt nu alleen als
  er direct ernaast een controlecijfergeldige tweede MRZ-regel staat –
  de naamregel zelf heeft geen eigen controlecijfer.
- De tweede regel van het machineleesbare gebied (MRZ) op paspoort of
  identiteitskaart bleef volledig onherkend – ze bevat paspoortnummer,
  geboorte- en vervaldatum in klare tekst, maar trof geen enkele
  bestaande herkenner. Een eigen herkenner controleert nu de vier
  ICAO-controlecijfers na.
- Een kenteken zonder enige spatie tot de beschrijving bleef open –
  „KentekenM-AB1234" of „KFZ-KentekenM-AB1234" werden helemaal niet
  herkend, omdat de onderliggende kentekencontrole vóór het kenteken
  een niet-woordteken vereist. Betrof voertuiggegevens waarbij geen
  spatie tussen veldwoord en kenteken staat.
- Een telefoonnummer zonder enige spatie tot de beschrijving bleef open
  – „Mobielnummer0171/2345678" of „Tel0171/2345678" werden helemaal
  niet herkend, omdat de onderliggende telefoonnummercontrole vóór het
  nummer een spatie of leesteken vereist. Betrof contactgegevens
  waarbij geen spatie tussen veldwoord en nummer staat.
- Een geboortenaam achter de afkorting „geb." werd helemaal niet
  herkend – „Julia Bergmann (geb. Weber)" vond alleen „Julia Bergmann",
  de punt in „geb." liet het taalmodel de volgende naam helemaal
  overslaan. Betrof persoonsgegevens met geboortenaam tussen haakjes of
  achter komma.
- De voornaam vóór een bijnaam tussen aanhalingstekens bleef open,
  wanneer aanhef en titel er samen voor stonden – „De heer Dr. Klaus
  'KP' Peters" leverde alleen „Peters" op, „Klaus" bleef leesbaar
  staan. Betrof handtekeningen en contactgegevens met titel en bijnaam.
- Een naam achter de puntloze korte vorm „tav"/„tavv" (ter attentie
  van) werd helemaal niet herkend – anders dan bij „t.a.v." met punt
  trok de ontbrekende zinsstructuur de naam mee weg. Betrof adressen
  zonder punt in de afkorting.
- Een naam achter „p.A." (per adres) werd helemaal niet herkend – de
  punt in de afkorting liet het taalmodel de naamherkenning helemaal
  overslaan. Betrof facturen en sollicitaties met verzameladres.
- Een naam achter puntloos aangeplakt „i.o."/„i.v." (in opdracht/in
  vervanging) werd helemaal niet herkend, bijvoorbeeld „i.o.Robert
  Lang" zonder spatie – dezelfde zinsbouwfout als bij „p.A.". Betrof
  handtekeningregels en e-mailhandtekeningen van vervangingsgevallen.
- Een pure aanwezigheidslijst met opsommingsteken zonder verdere
  aanduiding („- Max Mustermann", ook met punt aan het regeleinde)
  verloor alle namen aan dezelfde rem die eigenlijk alleen zakelijke
  opsommingen zoals „- Kleur: Blauw" moet beschermen. Zulke lijsten
  worden nu herkend.
- Bestanden die zich niet meer lieten opschonen, laten zich weer
  opschonen. Een waarde die al door herkenning was vervangen, kon in
  een eigen, al vervangen markering zoals „[SVNR1]" opnieuw worden
  gevonden – de slotproef verwierp dan een onberispelijk opgeschoond
  bestand. Bovendien wordt een telefoonverwijzing in een CSV-tabel nu
  meeverwijderd, en wie de zoektocht tot losse soorten beperkt, krijgt
  ze nu overal in het document gelijk – ook in de alternatieve tekst
  van een afbeelding, een Excel-kopregel, een keuzelijst of een
  HTML-attribuut.
- Een naam achter de e-mailkopregel „To:" (of „To" zonder dubbele punt)
  werd niet herkend, omdat een vreemd taalmodel de hele regel als één
  onopvallende treffer las en de naam daarin helemaal inslikte – anders
  dan bij „Cc:", „Bcc:" of „From:" vóór dezelfde naam. Een naam achter
  „To" wordt nu betrouwbaar gevonden.
- Het huwelijksdatum liet zich in eigen regels niet als datum behandelen
  („verschuiven" werd afgewezen met „bestaat alleen voor
  datumaanduidingen"), ontbrak in de groepstoewijzing van de
  vondstsoorten – waardoor het zich niet via de markeringen „Wat wordt
  gezocht" liet uitschakelen – en kreeg in plaats van een korte
  afkorting zoals bij het overlijdensdatum de volledige tekst als
  plaatshouder. Nagetrokken voor alle zes afkortings-/beschrijvingstabellen.
- Een in het voorbeeld bewust afgevinkte waarde kon toch elders worden
  gezwart: koos men bijvoorbeeld een e-mailadres af, dan bleef het
  adres zelf wel staan, maar het lokale deel zonder domein werd
  vervangen zodra het overeenkwam met de afgeleide gebruikersnaam van
  een verder geselecteerde persoon („anna.modelvrouw@voorbeeld.nl"
  naast „Anna Modelvrouw"). Een afgevinkte bewoording blijft nu
  documentbreed taboe, ongeacht uit welke vondstsoort ze afkomstig is.
- Een geboortedatum bleef onherkend, wanneer een familieboek- of
  burgerlijke-standuittreksel haar onder een gemeenschappelijke kopregel
  met de geboorteplaats voerde („Geboortedatum, geboorteplaats:
  19.11.1982, Steyr") – het tweede veldwoord tussen „Geboortedatum" en
  de datum liet de herkenning tot dan toe helemaal doorvallen.
- Een al herkend telefoonnummer bleef in zijn verkorte
  bevestigingsvorm leesbaar, wanneer het elders in hetzelfde document
  nog alleen met de laatste vier cijfers werd genoemd („bereikbaar op
  het nummer ...5678", „terugbelen op ...5678") – dezelfde bouwvorm als
  bij IBAN en creditcard.
- Een al herkend creditcardnummer bleef in zijn verkorte
  bevestigingsvorm leesbaar, wanneer het elders in hetzelfde document
  nog alleen met de laatste vier cijfers werd genoemd („Uw creditcard
  eindigt op ...0366") – dezelfde in betalingsbevestigingen
  gebruikelijke bouwvorm als bij de IBAN.
- Een al herkende IBAN bleef in haar verkorte bevestigingsvorm
  leesbaar, wanneer ze elders in hetzelfde document nog alleen met de
  laatste vier cijfers werd genoemd („De IBAN eindigt op ...3201") –
  een in bevestigingsmails gebruikelijke bouwvorm.
- Een spreker in een chat- of vergaderverslag bleef onherkend, wanneer
  vóór zijn naam een aanhef stond („De heer Bauer: …", „Mevrouw Koch:
  …") – en trof daarmee vaak ook de volgende sprekersregel in hetzelfde
  verslag mee, omdat te weinig herkende regels overbleven om het
  document überhaupt als verslag te waarderen.
- Een geboortedatum bleef onherkend, wanneer het veldwoord „geboren"
  ACHTER de datum stond in plaats van ervoor („Het kind werd op
  14.01.2026 geboren") – zo formuleert bijvoorbeeld een
  ouderschapsverlof- of zwangerschapsverklaring de geboortedatum van
  het kind. Bestaande patronen veronderstelden het veldwoord altijd
  vóór de datum.
- Een formulierbeschrijving met reactie- of vinkjeteken direct ervoor
  („Contactpersoon 😊:", „Aanspreekpunt ✓:") werd niet meer als
  beschrijving herkend, en de naam eronder of erachter bleef daardoor
  deels maar onvolledig gevonden (bijv. alleen de achternaam bij
  „Mayer Roman").
- Hetzelfde gat trof ook bijzonder beschermenswaardige gegevens volgens
  art. 9 AVG (religie, gezondheid, vakbond): een reactieteken direct
  vóór het scheidingsteken of de regelafbreking („Geloofsovertuiging
  😊: rooms-katholiek") liet de beschrijving helemaal doorvallen, en het
  gegeven bleef volledig onherkend staan.
- Een adres met dubbele plaatsnaam met koppelteken (bijv. „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") verloor de postcode
  volledig, hoewel de plaats zelf werd herkend en gezwart – op een
  voertuigdocument of aanschrijven bleef zo de postcode leesbaar staan.
- Een tabelkolom zonder kolomafstand (echt PDF-tekstuittreksel) kon
  onder een naamkolom ook twee toevallig naast elkaar staande
  hoofdlettervormen ten onrechte als persoon zwarten, bijvoorbeeld twee
  plaatsnamen in een gegevensregel; dat is nu alleen nog het geval als
  geen andere vondst op dezelfde plek al iets anders herkent.
- Dezelfde naamkolom zwartte in dezelfde regelvorm ook twee voor het
  taalmodel onbekende zaakwoorden (bijv. „Frontend Backend", „Turbo
  Module") ten onrechte als persoon, omdat daar geen andere vondst de
  rem uitlokte; ze vereist nu bovendien dat minstens een van beide
  woorden door het taalmodel zelf als eigennaam wordt gelezen.
- Het Duitse pensioenverzekeringsnummer werd in zijn officiële volledige
  groepering (bijv. „65 170839 J 08 8" – zoals het op
  socialezekerheidsbewijs en loonstrook staat) niet herkend en bleef in
  het origineel staan; herkend werden alleen de compacte schrijfwijze
  en de alleen tot de letter gegroepeerde vorm.
- Het Duitse fiscale identificatienummer werd in zijn officiële
  schrijfwijze (groepering 2-3-3-3, bijv. „48 836 075 988" – zoals het
  op elke echte belastingaanslag en elke mededeling van het Bundeszentralamt
  für Steuern staat) helemaal niet herkend en bleef in het origineel
  staan; alleen de zeldzamere groepering 3-3-3-2 was gedekt.
- Het Noordrijn-Westfaalse belastingnummer (bijv. „221/5147/0815", met
  viercijferige in plaats van driecijferige tweede groep) werd in
  belastingaanslagen helemaal niet herkend en bleef in het origineel
  staan – elke andere Duitse deelstaat was al gedekt.
- Bij arbeidsovereenkomsten werd een naam achter de beschrijving
  „Werkgever:" volledig over het hoofd gezien, zodra de achternaam
  tegelijk een gewoon woord is (bijv. „Bauer Anna") – „Werkgever" staat
  zowel als naam- als als bedrijfsbeschrijving in de lijst, en de
  bedrijfstoewijzing overschreef de naamtoewijzing.
- In een huurcontractkop met de beschrijvingen „Verhuurder:"/„Huurder:"
  werd een achternaam die tegelijk een gewoon woord is (bijv. „Bauer"),
  over het hoofd gezien – alleen de voornaam bleef herkend. Genummerde
  huurpartijen („Huurder 1:", „Huurder 2:") waren bovendien getroffen,
  ook bij namen zonder deze dubbelzinnigheid.
- In een gerechtelijk proces-verbaal met de beschrijvingen
  „Getuige:"/„Eiser:"/„Gedaagde:" (ook met telling, „Getuige 1:",
  „Getuige 2:") werd een achternaam die tegelijk een gewoon woord is
  (bijv. „Bauer"), eveneens over het hoofd gezien – alleen de voornaam
  bleef herkend.
- Bij een verklaring van erfrecht, volmacht, aanmaningsprocedure en
  koopovereenkomst werd een achternaam die tegelijk een gewoon woord is
  (bijv. „Bauer"), achter beschrijvingen zoals „Erflater:", „Erfgenaam:",
  „Volmachtgever:", „Gevolmachtigde:", „Verweerder:", „Schuldenaar:",
  „Schuldeiser:", „Koper:", „Verkoper:", „Legataris:" of
  „Executeur:" over het hoofd gezien – deels bleef alleen de voornaam
  herkend, deels viel de hele naam weg.
- Bij een meerpartijenlijst vóór het rubrum-scheidingsteken „./." (bijv.
  „Sand, Werner en Huber, Anna ./. Wechsler, Martina") bleef de eerste
  partij ongemaskeerd – alleen de partij direct naast „./." werd
  herkend.
- In het rubrum-scheidingsteken „./." (bijv. „Sand./.Wechsler") werd de
  naam na het teken volledig over het hoofd gezien, wanneer daar geen
  spatie stond – alleen met spatie ervoor en erna greep de herkenning.
- De achternaam „Wahr" werd volledig over het hoofd gezien, wanneer ze
  alleen stond (bijv. „Mevrouw Wahr behandelt uw zaak.") – het woord
  staat toevallig ook in de lijst van gewone Duitse woorden, die anders
  naamvondsten uit zinnen zoals „Dat is waar." filtert.
- Achternamen zoals „Los", „Weit", „Rund" of „Hoch" werden volledig over
  het hoofd gezien, wanneer ze alleen stonden (bijv. „De heer Hoch nam
  de leiding op zich.") – alle vier de woorden staan toevallig ook in
  de lijst van gewone Duitse woorden, die anders naamvondsten uit
  zinnen zoals „Ongeveer honderd gasten kwamen naar het feest." filtert.
- Achternamen zoals „Ganz" of „Recht" werden volledig over het hoofd
  gezien, wanneer ze alleen stonden (bijv. „De heer Ganz ondertekende
  het contract.") – beide woorden staan toevallig ook in de lijst van
  gewone Duitse woorden, die anders naamvondsten uit zinnen zoals
  „Helemaal juist, dat klopt." filtert.
- Een formulierveld met een sterretje of een superscript
  voetnootcijfer achter de beschrijving (bijv. „Geloofsovertuiging*:
  rooms-katholiek" of „Kerkgenootschap¹: protestants") werd niet
  herkend en bleef in klare tekst staan – alleen de vorm zonder dit
  teken greep.
- Hetzelfde veld bleef verder in klare tekst staan, wanneer er zelfs
  twee voetnoottekens achter de beschrijving stonden (bijv.
  „Geloofsovertuiging**: rooms-katholiek" of „Vakbond¹²: FNV").
- Een versienummer zoals „Softwareversie 4.2.1.19" of „Firmware Build
  2.0.4.11" wordt niet meer ten onrechte als IP-adres gezwart. Hetzelfde
  geldt nu voor bewijsstuk- en procesnummers zoals „Factuurnummer
  10.20.30.40" of „Bestelnummer 7.8.9.10".
- Twee IBAN's direct onder elkaar (bijv. eigen en die van een
  buitenlandse zakenpartner in de factuurkop) werden niet meer beide
  herkend – de tweede bleef onopgemerkt staan.
- Een beschreven IBAN trok soms het volgende woord in de zin mee
  ("Bankgegevens AT61 … wordt afgeschreven" werd tot "wordt" toe
  gezwart), zodra het volgende woord kleingeschreven was – de
  klaretekstrest ernaast bleef daarbij onaangetast staan.
- Liechtensteinse adressen worden nu herkend („FL-9490 Vaduz"), zoals
  tot nu toe al Duitse, Oostenrijkse en Zwitserse.
- Paspoortnummer wordt nu achter zijn beschrijving herkend en
  verwijderd (bijv. „Paspoortnummer: C01X00T471").
- Verblijfsvergunning- en verhuisbewijsnummer worden nu achter hun
  beschrijving herkend en verwijderd.
- Een kenmerk achter zijn beschrijving wordt nu ook herkend, wanneer een
  gedachtestreepje in plaats van een dubbele punt scheidt (bijv.
  „Klantnummer – K903944").
- Een als „IBAN" of „Rekeningnummer" beschreven bankrelatie wordt nu ook
  herkend, wanneer een gedachtestreepje in plaats van een dubbele punt
  scheidt.
- Een naam achter een beschrijving zoals „Contactpersoon (Verkoop)" of
  „Behandelaar/-ster" wordt nu ook met toevoeging tussen haakjes of
  genderneutrale schuine-streepuitgang herkend.
- Dezelfde sterretjes-gendervorm („Behandelaar*ster") wordt nu eveneens
  herkend.
- Een naam achter een beschrijving wordt nu ook herkend, wanneer een
  gelijkheidsteken in plaats van een dubbele punt scheidt (bijv.
  „Contactpersoon = Mayer Roman" of „Aanspreekpunt=Mayer Roman"), zoals
  gebruikelijk in configuratiebestanden of CSV-kopregels. Staan meerdere
  van zulke beschrijving-waardeparen door puntkomma's gescheiden in één
  regel, dan wordt nu alleen nog de eerste waarde herkend in plaats van
  de hele overige regel.
- Een GPS-coördinatenpaar achter het woord „Coördinaten" wordt nu
  betrouwbaar herkend (bijv. „Coördinaten: 48.2082, 16.3738") – het
  woord droeg de verkeerde buigingsvorm in de interne catalogus.
- Een kenmerk achter zijn beschrijving (klantnummer, contractnummer,
  dossiernummer, identiteitskaartnummer en ongeveer honderd verdere
  veldwoorden) werd niet meer herkend, zodra de beschrijving niet exact
  in de vastgelegde hoofd-/kleine letters stond – „klantnummer:" in een
  e-mail of „KLANTNUMMER:" in een formulierkop bleven onaangetast staan.

### Nieuw

- **Realistische vervangwaarden zijn nu een bewust ingezet voorbeeld in
  plaats van een standaard.** De uitzonderingentabel in het tabblad
  „Plaatshouder" begint leeg. Een nieuwe knop voert daar op verzoek
  plausibele foutwaarden in voor naam, plaats, adres, organisatie,
  e-mail, telefoon, doorkiesnummer en IBAN. Hij laat geldbedragen
  uitdrukkelijk bij de genummerde plaatshouder; de strategie
  „verzinnen" blijft voor losse soorten verder met de hand te kiezen.
- **Het AI-niveau kan de grafische kaart gebruiken.** Onder Windows is
  daarvoor een krap 17 MB groot extra pakket na te laden; daarna
  rekent het AI-niveau op een geschikte grafische kaart aanzienlijk
  sneller dan op de processor. Wie er geen heeft of niets nalaadt,
  werkt ongewijzigd verder – alleen trager. Op macOS is de versnelling
  toch al ingebouwd.
- **Twee nieuwe meldingen via het taakbalksymbool**: wanneer het
  voorbeeld vóór het vervangen klaarstaat voor doorzicht en wanneer een
  verwerking voltooid is. Beide staan standaard aan en zijn onder
  *Instellingen → Programma → Meldingen* afzonderlijk uit te
  schakelen.

### Gewijzigd

- **Identiteitskaart- en rijbewijsnummer worden nu herkend**, wanneer
  hun beschrijving ervoor staat („Identiteitskaartnummer: …",
  „Rijbewijsnummer: …") – tot nu toe vielen beide door elke
  herkenning.
- **Maskuro volgt nu de contrastontwerpen van Windows.** Wie onder
  *Instellingen → Toegankelijkheid → Contrastontwerpen* er een heeft
  ingeschakeld, kreeg dat tot nu toe overal behalve hier: Maskuro
  stelde daarna zijn eigen kleuren in. Nu blijft het bij het ontwerp
  van het systeem – venster, lijsten, invoerzone, logboek en
  statuskleuren. Het gekleurde stoplicht in voorbeeld en
  nabewerkingsvenster vervalt daar bewust; wat het zegt, staat sindsdien
  toch al als teken en als woord ernaast.
- **De controlebehoefte staat niet meer alleen in de kleur.** Rood,
  oranje en groen zijn bijna even licht – wie roodgroenkleurenblind
  is, zag in voorbeeld en trefvak een lijst zonder verschillen, en dat
  is ongeveer elke twaalfde man. Elke regel draagt nu bovendien een
  teken dat in vorm verschilt: ▲ eerst controleren, ● controleren, ○
  goed onderbouwd, ◆ zonder beoordeling. De korte aanwijzing noemt het
  in woorden, en een schermlezer leest het voor.
- **Alt opent de menu's weer zoals gewend.** De menubalk had geen
  toetsenbordkortere weg: wie de muis niet gebruikte, moest zich door
  elk menu pijlen. Nu draagt elk item een onderstreepte letter – Alt+B
  voor „Bestand", vanaf daar A voor „Afsluiten" –, en wel in alle talen
  van de interface.
- **Bedieningselementen zeggen een schermlezer weer waarvoor ze
  dienen.** In het nabewerkingsvenster, het regelvenster, het logboek,
  de woordenlijsten, de hulp, de zoekloop en vijf verdere vensters
  werden lijsten, zoekvelden, uitklaplijsten en regelaars tot nu toe
  alleen als „boom" of „combinatieveld" aangekondigd – zonder waarvan.
  Ongeveer veertig plekken dragen nu een naam. (Het hoofdvenster was
  sinds augustus in orde; de vensters die daarna bijkwamen, hadden die
  stap nooit meegemaakt.)
- **Wie met het toetsenbord bedient, ziet overal waar hij staat.** Bij
  de controlebehoefteregelaars, bij het selectievakje en bij de
  „nooit meer"-knop van het voorbeeld, bij de soortkoppen erin, bij het
  paginavak van het nabewerkingsvenster en bij de zijbalk van de
  instellingen ontbrak het kader dat het systeem anders om het
  aangesprongen bedieningselement legt.
- **Grotere systeemletter snijdt niets meer af.** Wie onder
  *Toegankelijkheid → Tekstgrootte* boven 175 % instelt, verloor tot
  nu toe het einde van de beschrijvingen in de mapbewaking en in de
  toetsencombinatievelden. De hoofdstuklijst van de hulp sneed lange
  hoofdstuknamen al bij gewone letter af; ze breekt ze nu af en noemt
  de volledige naam in de korte aanwijzing.

- **De herkenning is aanzienlijk sneller geworden.** De herkenner voor
  beschreven kenmerken („Klantnummer: K903944") controleerde tot nu
  toe per tekstfragment meer dan 1200 losse patronen na elkaar – dat
  was de grootste afzonderlijke post van de herkenningstijd, bij elke
  alinea en elke tabelcel. Nu is het één enkel patroon met hetzelfde
  resultaat: aan het meetcorpus verandert geen enkele treffer, de
  basisstand per tekstfragment wordt ongeveer drie- tot viermaal zo
  snel.
- **Het venster verschijnt meteen bij de start.** Tot nu toe laadde het
  hoofdvenster de volledige taalwerktuigen, voordat het zich überhaupt
  toonde – ongeveer vier seconden blinde tijd bij elke start. De
  modellen laden nu zoals bedoeld op de achtergrond, terwijl het
  venster al staat; de opschonen-knop wordt zoals voorheen pas vrij
  wanneer alles klaar is. Ook pure informatie-aanroepen van de
  opdrachtregel (bijvoorbeeld `--version`) antwoorden nu meteen in
  plaats van na enkele seconden.
- **Afbeeldingen worden bij automatische taalherkenning nog maar één
  keer gelezen.** Tot nu toe liep de tekstherkenning bij de standaard
  „Taal: automatisch" tweemaal over dezelfde afbeelding – eenmaal voor
  het taalvermoeden, eenmaal voor de eigenlijke controle. Beeldbestanden,
  klembordafbeeldingen en het tekstvenster zijn daarmee ongeveer
  dubbel zo snel klaar; bij uitgeschakelde tekstherkenning vervalt de
  tot nu toe ongemerkt toch lopende lezing helemaal.
- **Opgeslagen webpagina's en e-mails worden sneller opgeschoond.** De
  waarden in HTML-attributen, opmerkingen en ingebedde gegevensblokken
  werden tot nu toe afzonderlijk herkend – een gemeentepagina met
  honderden beschrijvingen stelde honderden losse vragen aan de
  herkenning. Nu worden ze verzameld en per verschillende waarde maar
  één keer herkend; aan het meetcorpus verandert geen treffer, .html en
  .eml zijn ongeveer een derde sneller.
- **Ook de nevenopslagen van tabellen en presentaties worden gebundeld
  herkend.** Alternatieve teksten, formuletekenreeksen,
  grafiekbeschrijvingen, opmerkingen, pivot-tussenopslag en
  documenteigenschappen stelden per waarde een eigen herkenningsvraag –
  een werkmap met duizenden pivotregels navenant duizenden. Nu loopt
  een verzamelde run over de verschillende waarden, en de
  nacontrole-volledige doorloop aan het einde loopt alleen nog wanneer
  sinds de lopende tekst daadwerkelijk nieuwe waarden zijn bijgekomen.
  Aan het meetcorpus verandert geen treffer.
- **Formulierrijke PDF's worden sneller opgeschoond.** Velden, notities,
  bladwijzers en verwijzingen herhalen dezelfde waarden massaal
  („Off" bij elk aanvinkveld, dezelfde auteur bij elke opmerking) –
  elk stelde tot nu toe zijn eigen herkenningsvraag. Per run wordt een
  waarde nu nog maar één keer herkend; vervanging en
  consistentie-nacontrole lopen ongewijzigd per plek.
- **Grote tabelbestanden (.csv/.tsv) worden aanzienlijk sneller
  opgeschoond.** De vier tabelnacontroles ontleedden hetzelfde bestand
  tot nu toe elk zelf teken voor teken in cellen (bij 40 MB ongeveer
  30 s extra werk); nu loopt de ontleding één keer. De
  kolomkopherkenning (geboortedatum- en personeelsnummerkolommen)
  stelt in plaats van een vraag per cel een gebundelde – bij identieke
  treffers ongeveer twintig keer sneller. En de
  naamkolomsamenvatting van grote personeelslijsten is niet meer
  kwadratisch in het aantal regels.
- **Het kengetallenpaneel bevriest het venster niet meer.** Het
  openklappen van de kengetallen las bij veel grote bestanden hun
  tekst eerst samen en liet het venster daarbij seconden lang
  stilstaan. De berekening loopt nu op de achtergrond; het paneel opent
  meteen en vult de getallen na.
- **Het zoekloop-rapport bevriest het venster niet meer.** Na het
  doorzoeken van vele duizenden bestanden werd de gemeenschappelijke
  map voor elk getroffen bestand opnieuw berekend; bij grote runs stond
  het venster daarbij tientallen seconden stil. Het rapport verschijnt
  nu meteen.
- **PDF's met tekstherkenning worden sneller gecontroleerd.** Elke
  pagina werd bij het naast elkaar leggen onnodig tweemaal naar
  PNG-formaat omgezet; nu wordt de al aanwezige afbeelding doorgegeven.
  Het resultaat is ongewijzigd, alleen de controle
loopt vlotter.
- **Verloopaantekeningen op grote afbeeldingen haperen niet meer.** Bij
  het natrekken aan de handvatten van een aantekening met verloop werd
  het verloop tot nu toe punt voor punt opnieuw berekend – op een grote
  schermafbeelding een zichtbare hapering. Het resultaat is hetzelfde,
  alleen zonder de pauze.

### Opgelost

- **Het kruis om een bestand uit de lijst te verwijderen is weer een
  eenvoudige X.** Het nieuwe editorwerktuig „Verwijderen" gebruikte
  per ongeluk dezelfde symboolkenning en toonde daardoor zijn rode
  kruis samen met gestippelde tekstlijn ook in elke bestandsregel.
  Beide handelingen hebben nu gescheiden symboolnamen en behouden hun
  respectievelijk passende weergave.
- **Meerdelige gegevens worden in PDF's ook over een zichtbare
  regelafbreking heen herkend.** Maskuro leest de geometrisch
  gegenereerde paginatekst bovendien als offsetgelijke
  lopende-tekstweergave. Dat geldt voor alle basis- en hoog-niveau-
  herkenners evenals eigen zoekpatronen, niet alleen voor het eerst
  zichtbare geval „Diabetes mellitus type 2". Lege regels en herkende
  tabel- of sectiegrenzen blijven harde grenzen; vindplaatsen passen
  verder exact op de te zwarten woorden.
- **Het voorbeeld bij „Pseudonimiseren" sprak zichzelf tegen.** De zin
  beloofde „dezelfde persoon, hetzelfde nummer" en toonde vervolgens
  twee verschillende nummers – precies het beeld dat bij
  „Anonimiseren" correct is. Beide voorbeelden kloppen nu met hun eigen
  zin.
- **Een net ingevoegde plaatshouder kon bij „Origineel terughalen" als
  overlappende letterbrij blijven staan in plaats van te verdwijnen.**
  Een effen ingelegde plaatshouder schreef tot nu toe een eigen
  uitvoercommando per teken, waarvan alleen het eerste een eigen
  tekstmatrix droeg – bij de volgende bewerking van dezelfde plek
  (bijvoorbeeld „terughalen" er direct na) kregen de overige
  tekencommando's om beurten de tekenindexen van het eerste
  toegewezen, en de plaatshouder viel uiteen in twee elkaar
  overlappende posities. Een effen plaatshouder krijgt nu één enkel
  uitvoercommando voor zijn hele tekst.

- **Stond dezelfde gezwarte of verwijderde waarde onder twee regels in
  het nabewerkingsvenster en werden beide voor de terughaling
  gemarkeerd, dan telde de tweede regel ten onrechte als „niet
  eenduidig" – hoewel de waarde allang was teruggehaald.** Beide regels
  gelden nu als voltooid.

- **De naam na „Reply-To:" wordt nu gevonden.** In een e-mailkopregel
  zoals „Reply-To: Huber" bleef de naam tot nu toe helemaal onherkend –
  het taalmodel las „Reply-To:" als een eigen, foutieve persoon en zag
  de echte naam erna over het hoofd.

- **De e-mailkopwoorden „Reply" en „Fwd" worden niet meer zelf als naam
  gezwart.** In een onderwerpregel zoals „Fwd: Offerte van Huber" werd
  tot nu toe naast de naam ook het kopwoord zelf als persoon herkend en
  gezwart.

- **„Werkgever: Siemens AG" wordt nu als bedrijf herkend, niet meer als
  persoon.** Droeg de bedrijfswaarde achter de beschrijving „Werkgever"
  een rechtsvorm zoals GmbH, AG of KG, dan bleef ze ondanks
  ingeschakelde organisatieherkenning een persoonsvondst – alleen het
  smallere geval zonder rechtsvorm („Wollmuth en Partners") werd tot nu
  toe als bedrijf herkend.

- **Een eenmaal herkend adres blijft niet meer elders staan.** Werd een
  straatadres op de ene plek herkend en vervangen, dan kon hetzelfde
  adres op een tweede plek blijven staan – bijvoorbeeld in een moeilijk
  leesbare voettekst van een ingescand document, waar de automatische
  tekstherkenning het verminkt las. Adressen worden nu, zoals namen en
  bedrijven al langer, door het hele document consequent verwijderd.

- **E-mails met meerdere ontvangers werden bij het opschonen stil
  beschadigd.** Een `.msg`-bericht met twee of meer ontvangers verloor
  bij het opslaan delen van zijn interne opbouw, zodat het opgeschoonde
  resultaat onvolledig was. Oorzaak was een verwisseling van gelijk
  benoemde interne onderdelen, die bij elke ontvanger voorkomen. Zulke
  berichten worden nu weer volledig opgebouwd.

- **Twee van de meegeleverde testdocumenten lieten zich niet openen in
  Word en PowerPoint.** Wie het meetcorpus downloadde, kreeg bij
  `format_dokument.docx` „Fout bij het openen van het bestand in Word"
  en bij `format_praesentation.pptx` „Het bestand is beschadigd". Beide
  bestanden waren al gebrekkig voordat Maskuro ze aanraakte – de
  opgeschoonde versie voerde de fout alleen verder. LibreOffice opende
  beide probleemloos, waardoor het niemand was opgevallen.

- **Een eigen AI op het internet wordt nu versleuteld aangesproken.**
  Wie bij de eigen AI een extern adres zonder „https://" invoert (zoals
  het vaak op het briefje van IT staat), bereikte het tot nu toe via
  een onversleutelde verbinding – de ongezwarte tekst ging in klare
  tekst naar buiten. Zulke adressen worden nu via „https://"
  aangesproken; een server in het eigen netwerk blijft ongewijzigd
  bereikbaar. Volgt de server een omleiding naar een andere computer,
  dan gaat de toegangssleutel niet meer mee.

- **Ook een beschadigde afbeelding verliest nu haar verborgen
  metagegevens.** Liet een ingebedde afbeelding zich niet meer volledig
  openen (bijvoorbeeld een afgesneden foto), dan behield ze tot nu toe
  haar EXIF- en GPS-gegevens – opnamelocatie en fotografennaam bleven
  onzichtbaar in het resultaat. Zulke afbeeldingen worden nu ook dan
  van deze gegevens bevrijd, wanneer ze zich helemaal niet meer laten
  weergeven.

- **Een ingebed bestand dat zich niet liet opschonen, wordt nu gemeld
  in plaats van stilzwijgend meegegeven.** Zat in een presentatie of
  werkmap een ingebed object dat te diep genesteld was of zich niet
  liet openen, dan bleef het tot nu toe ongewijzigd in het resultaat,
  zonder aanwijzing – het bestand gold als opgeschoond. Zulke gevallen
  staan nu in de waarschuwing „konden NIET worden gecontroleerd",
  precies zoals een ingebed oud formaat.

- **Donkere lijsten zijn weer doorlopend donker en leesbaar.** Op macOS
  wisselden bestandslijsten tussen bijna zwarte en lichtgrijze regels;
  bij het nabewerken zag daardoor dezelfde groene, oranje of rode
  controlewaarde er per regel anders uit. Venster, lijsten, letter,
  plaatshouder en selectie komen nu uit een gemeenschappelijk
  licht-/donkerpalet. De kleurgecodeerde treflijst legt bovendien geen
  zebrastrepen meer onder haar kleuren.

- **Beroepsaanduidingen met „als" werden ten onrechte als naam gezwart.**
  Een zin zoals „Als kok is hij sinds vier jaar bij ons werkzaam."
  verloor het beroep, niet alleen een naam – „als" leidt een
  rolaanduiding net zo goed in als „de" of „het". Echte achternamen op
  dezelfde plek (bijv. met een aanhef ervoor) blijven onaangetast.

- **Een tabelkop kon een positienummer in een geldbedrag meetrekken**
  (alleen bij ingeschakelde optie „Geldbedragen ook verwijderen").
  Eindigde een regel op een valuta („… Eenheidsprijs EUR") en begon de
  volgende met een getal, dan werd daarvan ten onrechte een bedrag over
  de regelafbreking heen. Het scheidingsteken tussen valuta en getal
  blijft nu op dezelfde regel.

- **Een korte afkorting in hoofdletters kon een heel zinsdeel
  inslikken, of zich vóór een correct herkende naam hangen.** Stond in
  een regel een tweeletterig woord in hoofdletters zoals „DI", „AG" of
  „KG" – alledaagse afkortingen, geen namen –, dan werd de hele regel
  proefondervindelijk in kleine letters doorzocht, en de afkorting trok
  daarbij af en toe naburige woorden (ook werkwoorden) samen in één
  vermeende naam. Pas vanaf drie letters lokt een woord met
  hoofdletter deze tweede controle nu uit. Bij iets langere afkortingen
  zoals „CEO" of „USB" bleef een tweede fout: de al correct gevonden
  naam („Schneider") kreeg de voorafgaande afkorting als voorvoegsel
  mee in het resultaat („CEO Schneider"). De afkorting blijft nu buiten
  beschouwing.

- **Een geboortedatum zonder spatie erachter bleef staan.** Stond er
  achter „geb." geen ruimte vóór de datum – zoals gebruikelijk in
  krap gezette formulieren („geb.14.03.1988") –, dan herkende Maskuro
  het veld niet en liet de datum onaangetast. Gangbare korte vormen
  zoals „Geboortedat." of „Geb.-dat." worden nu eveneens herkend.

- **Een IBAN met schuine strepen als scheidingsteken bleef staan.**
  Zoals bij telefoonnummers („0664/1234567") schrijven sommige
  sjablonen ook de IBAN in blokken met schuine streep
  („AT48/3200/0000/1234/5864") in plaats van met spatie of
  koppelteken. Deze schrijfwijze wordt nu eveneens herkend.

- **Een Oostenrijks socialezekerheidsnummer met koppelteken, punt of
  schuine streep bleef staan of was verkeerd beschreven.** Tussen de
  twee cijferblokken was tot nu toe alleen een spatie voorzien;
  schrijfwijzen zoals „1237-010180", „1237.010180" of „1237/010180"
  werden niet (of in het geval met schuine streep onder de verkeerde
  soort) herkend.
Het controlecijfer bevestigt verder elke treffer, ongeacht het
  scheidingsteken.

- **Een naam achter „c/o" in een adres werd helemaal niet verwijderd.**
  „c/o Max Mustermann, Hauptstraße 5, 1010 Wien" zwartte straat en
  plaats, liet de naam erachter echter volledig staan. De naam wordt
  nu herkend; „c/o" zelf blijft als adresaanwijzing zichtbaar.

- **Een met punten gegroepeerd creditcardnummer bleef staan.**
  Schrijfwijzen zoals „4111.1111.1111.1111" werden niet herkend; met
  spatie of koppelteken gescheiden nummers waren daardoor niet
  getroffen. De controlesom bevestigt verder elke treffer.

- **Een met koppeltekens gegroepeerd fiscaal identificatienummer bleef
  staan, een Oostenrijks btw-nummer met koppelteken of punt evenzo.**
  Spatie, schuine streep en punt waren bij het fiscale nummer al
  voorzien, het koppelteken ontbrak; bij het btw-nummer
  („ATU12345678") ontbraken koppelteken en punt na het voorvoegsel.
  Het controlecijfer van het fiscale nummer bevestigt verder elke
  treffer.

- **Een veldwaarde tussen aanhalingstekens bleef staan, bijvoorbeeld in
  een JSON-achtige regel zoals „voornaam": „Max".** De herkenning via
  een veldbeschrijving („Voornaam: …") vereiste tot nu toe dat noch de
  beschrijving noch de waarde zelf tussen aanhalingstekens staat. Zulke
  regels worden nu ook herkend – evenzo veldbeschrijvingen met een
  voorafgaand YAML-lijstpunt („- Voornaam: Max") of een tab in plaats
  van een spatie vóór de dubbele punt.

- **Het e-mailkopwoord „Sent" werd zelf als naam gezwart.** In een
  kopregel zoals „Sent: Huber" trof het tot nu toe zowel „Sent" als de
  eigenlijke naam; verwante kopwoorden zoals „Subject" of
  „Onderwerp" bleven daarvan altijd al onaangetast. „Sent" blijft nu
  eveneens staan.

- Een naam achter de kopregels „Errors-To:" of „Resent-From:" bleef
  onontdekt, wanneer zo'n regel in klare tekst gekopieerd stond
  (bijvoorbeeld een doorgestuurd bericht of een incidentrapport) –
  anders dan bij „Reply-To:" of „Return-Path:" viel de naam hier
  helemaal weg in plaats van alleen onnauwkeurig afgebakend te zijn.
  Hij wordt nu gevonden.
- Een en hetzelfde bestand leverde bij twee opschoningen soms een
  ander resultaat op: troffen twee herkenningen precies dezelfde plek
  met gelijke lengte en gelijke zekerheid (bijv.
  „Socialezekerheidsnummer 1237/010180" als AT_SVNR of als algemeen
  kenmerk), dan hing het van het toeval af wie won – de waarde werd in
  beide gevallen verwijderd, alleen de plaatshouderbeschrijving
  wisselde. De gelijke stand wordt nu altijd gelijk opgelost.
- Een functiebenaming direct vóór een zelfstandig naamwoord (bijv.
  „Behandelend arts: Dr. …" of „Verantwoordelijke behandelaar is …")
  werd soms ten onrechte meegezwart, alsof ze zelf een naam was. Echte
  achternamen ernaast blijven daarvan onaangetast.
- Een echte achternaam die toevallig hetzelfde uitziet als een
  bijvoeglijk naamwoord (bijv. „Schöne", „Lange", „Junge") en direct
  vóór een verder zelfstandig naamwoord staat (bijv. „Contactpersoon:
  Schöne Assistente"), bleef sinds de laatste oplossing ongezwart in
  de tekst staan – een gegevenslek. Alleen nog een strikt begrensde
  lijst van echte functiebenamingen (bijv. „Behandelend",
  „Verantwoordelijke") wordt nu in deze bouwvorm als niet-naam
  behandeld.
- Een alleenstaande achternaam aan het einde van een meerregelige
  naamtreffer, die toevallig hetzelfde uitziet als een bijvoeglijk
  naamwoord (bijv. „Schwarz", „Kurz", „Alt", „Frisch", „Gut",
  „Reich"), bleef vóór een direct volgende dubbele punt onherkend
  staan – de opschoning verwarde haar met een veldbeschrijving zoals
  „Telefoon:". Een gesloten lijst van bekende meerduidige achternamen
  beschermt haar nu.
- Een alleenstaande achternaam die toevallig een gewoon Duits woord is
  („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange"), ging tot nu toe
  **volledig** verloren – ook in eenvoudige zinnen zoals „De heer Gross
  ondertekende het contract." De reden lag in de eigen spaCy-
  stopwoordenlijst, die deze woorden bevat; een gesloten lijst van
  bekende achternamen behoedt ze nu voor het verwerpen.
- Bij arbeids-, lenings-, borgtocht-, trust- en insolventieovereenkomsten
  evenals voogdij/bewind en deskundigenopdrachten werd een achternaam
  die tegelijk een gewoon woord is (bijv. „Bauer"), achter
  beschrijvingen zoals „Opdrachtgever:", „Opdrachtnemer:",
  „Werknemer:", „Verzekerde:", „Kredietgever:", „Kredietnemer:",
  „Borg:", „Zekerheidsgever:", „Trustee:", „Trustgever:",
  „Curator:", „Deskundige:", „Sachverständige:", „Voogd:" of
  „Bewindvoerder:" over het hoofd gezien – deels bleef alleen de
  voornaam herkend, deels viel de hele naam weg.
- In het colofon werd een achternaam die tegelijk een gewoon woord is
  (bijv. „Bauer"), achter de beschrijvingen „Directeur:",
  „Directrice:", „Vertegenwoordigingsbevoegd:", „Eigenaar:" of
  „Eigenares:" over het hoofd gezien – bij „Directeur:"/„Eigenaar:"
  viel de hele naam weg, bij „Vertegenwoordigingsbevoegd:" bleef
  alleen de voornaam herkend.
- Een contactblok waarvan de beschrijving alleen op haar regel stond en
  de geslachtsneutrale dubbelepuntvorm droeg („Contactpersoon:", naam
  eronder), werd **volledig** over het hoofd gezien – de dubbele punt
  werd als veldscheiding gelezen, en de eigenlijke naam in de volgende
  regel kwam daardoor nooit meer aan bod.
- Stond naam en beschrijving met dezelfde dubbelepunt-gendervorm in
  **één** regel („Contactpersoon: Anna Berger"), dan trok de
  plaatshouder het woord mee in de vervanging, in plaats van alleen de
  naam te verwijderen – de naam zelf werd verder volledig herkend.
- Een naam in een tabelkolom onder een personen-kolomkop (bijv.
  „Achternaam Voornaam Geboortedatum" boven „Bauer Anna 03.05.1985",
  zoals in een loonstrook) werd volledig over het hoofd gezien, zodra
  tussen de kolommen maar één enkele spatie stond en geen regel met een
  hiërarchienummer begon – precies de vorm waarin een echt
  PDF-tekstuittreksel zulke regels aflevert.
- In een chat- of vergaderverslag met sprekersnamen vóór de dubbele
  punt (bijv. „Bauer 🙂: Ik ga akkoord met het voorstel.") bleef de naam
  volledig onherkend, zodra een reactieteken tussen naam en dubbele
  punt stond en de achternaam tegelijk een gewoon woord is („Bauer",
  „Koch", „Schneider" e.d.) – een compleet verslag kon zo zonder één
  enkele herkende spreker blijven.
- Hetzelfde sprekersregelgat bestond ook met andere tussentekens vóór
  de dubbele punt: een statustoevoeging tussen haakjes („Bauer
  (voorzitter): …", „Bauer (afwezig): …"), een tijdstip tussen
  vierkante haken („Bauer [14:32]: …") en een voetnootteken direct aan
  de naam („Bauer*: …"). Ook hier bleef de spreker volledig onherkend,
  zodra de achternaam tegelijk een gewoon woord is.
- Stond een al herkende persoon in een aangehecht protocol- of
  logfragment van hetzelfde bericht (bijvoorbeeld een supportticket)
  bovendien als gebruikersnaam in de vorm „voornaam.achternaam" –
  kleine letters, zonder spatie, door een punt verbonden –, dan bleef
  deze klare naam leesbaar staan, hoewel dezelfde naam in het
  aanschrijven al was gezwart.
- Hetzelfde gebruikersnaamgat bestond ook met een liggend streepje in
  plaats van een punt („voornaam_achternaam") – een net zo gangbaar
  formaat in protocol- en logfragmenten.
- En ook in omgekeerde volgorde bleef de gebruikersnaam leesbaar
  („achternaam.voornaam" resp. „achternaam_voornaam") – sommige
  systemen plaatsen de achternaam vooraan in de log-gebruikersnaam in
  plaats van achteraan.
- Een overlijdensdatum bleef onherkend, wanneer er geen andere
  aanduiding naast stond („De heer Bauer is op 12.03.1985 overleden")
  – daarvoor bestond tot nu toe helemaal geen eigen herkenning, en de
  generieke datum grijpt bij deze standaarddrempel niet.
- Een overlijdensdatum bleef ook dan onherkend, wanneer de zin de
  werkwoordsvorm in plaats van het voltooid deelwoord gebruikte
  („Mevrouw Meier overleed op 12.03.1985", „Hij stierf op 12.03.1985")
  – alleen „is … overleden" greep tot nu toe.
- Een huwelijksdatum bleef onherkend, in welke vorm ook geschreven
  („Huwelijksvoltrekking op 12.03.2010", „Huwelijksdatum: 12.03.2010",
  „De heer en mevrouw Bauer trouwden op 12.03.2010") – daarvoor bestond
  tot nu toe helemaal geen eigen herkenning, en de generieke datum
  grijpt bij deze standaarddrempel niet.

- **In de nabewerkingseditor kon een tweede kader over een net pas
  ingevoegde plaatshouder een rood tekenrestant laten staan**,
  bijvoorbeeld „[G" in plaats van „[BEG1]" – zonder enige waarschuwing,
  want het restant hoorde niet meer bij het vertrouwelijke gegeven (dat
  was al in de eerste stap verwijderd), maar alleen nog bij de eigen
  plaatshouder. Reden was de kleurgeving: een nieuw ingevoegde
  plaatshouder werd teken voor teken in het bestand geschreven, ook bij
  effen standaard – een later kader over dezelfde plek vond daardoor
  geen samenhangende tekst meer waarop het zich had kunnen richten. Nu
  staat een effen plaatshouder als één stuk in de stroom, zoals de
  automatische opschoning altijd al deed; alleen een echt verloop- of
  regenboogtekst heeft nog steeds losse tekens nodig. De ingebouwde
  tegencontrole herkent zo'n restant bovendien nu ook wanneer de exacte
  tekenreeks van de plaatshouder niet
meer voorkomt.
- Een genummerde namenlijst met getrapt hiërarchienummer („1.1 Max
  Mustermann", „1.2 Huber Franz" …) verloor alle namen aan dezelfde rem
  die eigenlijk alleen echte hiërarchieën en positielijsten moet
  beschermen – zonder kolomkop boven de lijst was er geen getuige
  waaraan een naam zich had kunnen redden.
- Een naam in een Engelstalige aanmeldregel van een systeemlogboek
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000
  ssh2") werd niet herkend – het Duitse taalmodel vond hem alleen als
  ervoor „invalid user" stond, anders bleef hij staan. Zulke
  logboekfragmenten worden vaak ongewijzigd aan een incidentrapport
  toegevoegd. Namen achter „for" vóór een IP-adres worden nu
  betrouwbaar herkend.
- De naam van de betaalplichtige in de SEPA-machtigingsreferentie van
  een rekeningafschrift of boekingsjournaal (bijv. „MREF+Mustermann
  Klaus+SVWZ+ Huur augustus") bleef open – geen spatie, geen
  zinsstructuur, alleen met „+" gescheiden velden in hoofdletters, en
  in de daar gebruikelijke volgorde „Achternaam Voornaam" vond de
  herkenning hem ook niet toevallig. Wordt nu herkend.
- De straat samen met huisnummer in de eerste regel van een
  adrestabel (bijv. „Achternaam | Voornaam | Straat | Postcode |
  Plaats") bleef open – het taalmodel raadde daar een verkeerde, maar
  langere plaats dwars over meerdere kolommen heen, en die verdrong de
  juiste, kortere adrestreffer. Wordt nu herkend.
- Hetzelfde lek deed zich voor met een tab in plaats van „|" of „;" als
  kolomscheiding – daar verdween het adres zelfs helemaal in plaats van
  alleen te verliezen. Wordt nu herkend.
- Een straat met huisnummer bleef open, wanneer er direct erna zonder
  spatie een postcode met komma volgde (bijv. „Bahnhofstrasse
  12,80331 München", zoals in een door komma's gescheiden tabelkolom) –
  de komma zag eruit als een decimaal van een hoeveelheid, en de straat
  gold voor het patroon daarom helemaal niet als adres. Wordt nu
  herkend.
- Een straat met huisnummer bleef open, wanneer er direct erna zonder
  komma het plaatsvoorvoegsel „St." (Sint) volgde (bijv. „Hauptstraße 5
  St. Pölten", een briefkop zonder voorafgaande postcode) – „St." zag
  eruit als de stuk-eenheid, en de straat gold voor het patroon daarom
  helemaal niet als adres. Wordt nu herkend.
- Een deur-/verdiepingtoevoeging na een huisnummer (bijv. „Lerchenfelder
  Gürtel 43/12") bleef open zichtbaar, wanneer er direct erna een losse
  letter stond die toevallig overeenkwam met een maateenheid (bijv. „h"
  voor uur) – het adres werd dan alleen tot het huisnummer zonder zijn
  toevoeging opgeschoond, in plaats van volledig of helemaal niet te
  grijpen.
- Een onderwerpregel met een beroepsnaamgelijke achternaam vóór de
  voornaam („Onderwerp: Bauer Anna", „Onderwerp: Bauer, Anna") bleef
  tot nu toe volledig onherkend – ook midden in het document met
  voorafgaande volledige zin. Wordt nu herkend.
- Een Duits belastingnummer met spatie, punt of koppelteken tussen de
  blokken (bijv. „Belastingnummer: 30 815 08153" of „30.815.08153")
  bleef tot nu toe onherkend – alleen de schrijfwijze met schuine
  streep werd gevonden. Wordt nu herkend.
- Een naam achter een medische veldbeschrijving („Patiënt:",
  „Huisarts:", „Behandelend arts:", „Verwijzend arts:" en hun
  vrouwelijke vormen) bleef tot nu toe onherkend, wanneer de achternaam
  tegelijk een gewoon Duits woord is (bijv. „Patiënt: Bauer Thomas").
  Wordt nu herkend.
- Een naam achter de veldbeschrijving „Tandarts" op eigen regel (bijv.
  „Tandarts", daaronder „Huber Franz") bleef tot nu toe onherkend –
  noch voor- noch achternaam. „Tandartse" en de eenvoudige „Arts"-vorm
  waren daarvan niet getroffen. Wordt nu herkend.
- Een achternaam achter „De heer"/„Mevrouw", waarop een ambtelijke
  uitdrukking volgde zoals „ter kennisneming", „ter ondertekening" of
  „ter doorzending", werd tot nu toe te ruim opgevat en trok de
  uitdrukking mee in de naamtreffer – van „Mevrouw Petra Klein ter
  vertegenwoordiging in alle aangelegenheden" werd „Petra Klein ter
  vertegenwoordiging" vervangen, en de rest van de zin bleef
  grammaticaal verminkt staan. Echte adellijke titels zoals „von der
  Leyen" of „zu Guttenberg" blijven daarvan onaangetast.
- Dezelfde ambtelijke-uitdrukking-overredactie stak ook achter de naam
  in een e-mail-„To:"-kopregel, een goedkeuringscode (C.1/C.1.1/C.1.2),
  een rijbewijscode, een tussen haakjes staand formulierveld
  („[Voornaam]: …") en een puntloze groetformule – overal daar trok
  „ter"/„van" & co. een volgende uitdrukking zoals „ter ondertekening"
  of „ter vertegenwoordiging" mee in de treffer, deels bleef zelfs het
  kale partikelwoord zelf als naamrest in het resultaat hangen. Ook
  hier blijven echte adellijke titels volledig behouden.
- Het studentnummer achter zijn beschrijving werd tot nu toe helemaal
  niet herkend – „Studentnummer 7654321" viel volledig door de
  herkenning, noch als kenmerk noch via het taalmodel, omdat het getal
  alleen geen herkenbare vorm draagt.
- Hetzelfde gold voor het deelnemernummer – „Deelnemernummer 4471829"
  viel volledig door, noch als kenmerk noch via het taalmodel.
- In het cv viel de naam onder de sectiekop „Persoonlijke gegevens"
  vaak geheel of gedeeltelijk door de herkenning, wanneer hij zonder
  aanhef in de vorm „Achternaam Voornaam" direct eronder stond.
- Hetzelfde gold voor de sectiekop „Contactgegevens" – daar viel de
  naam zelfs volledig door, niet alleen gedeeltelijk.
- In een verhuisbewijs of aanvraaglijst met samengevoegde kolom „Naam,
  Voornaam" (basisregistratie-schrijfwijze, waarde bijv. „Mustermann,
  Max" in één cel) viel de naam volledig door de herkenning, wanneer
  een verdere kolom zoals de geboortedatum volgde.
- Een geboortedatum in de op identiteitskaart en verhuisbewijs
  gebruikelijke vorm „Geboortedatum/-plaats: 22.07.1978 / Rostock"
  werd niet herkend – alleen de kommavorm „Geboortedatum,
  geboorteplaats: …" greep.
- „Publieksbalie" en „Klantenservice" werden af en toe ten onrechte als
  plaats gezwart, vooral na een gedachtestreepje als opsommingsscheiding
  (bijvoorbeeld „Wendt u zich tot de publieksbalie – klantenservice …").
- Een beschreven telefoonnummer dat een regelafbreking middendoor
  scheidde (bijvoorbeeld uit een smalle briefkopkolom of een
  PDF-tekstextractie op de kolombreedte: „Telefoon: 0176 12\n34567"),
  werd deels maar voor de helft gezwart – het restant achter de
  regelafbreking bleef leesbaar staan.
- Een beschreven kenmerk (klant-, lid-, contractnummer en
  soortgelijke), dat een regelafbreking middendoor scheidde
  (bijvoorbeeld „Klantnummer: K903\n944" uit een smalle kolom), werd
  maar voor de helft gezwart – het restant achter de regelafbreking
  bleef leesbaar staan.
- Een naam met academische titel vóór een beroepsbenaming na komma
  (bijvoorbeeld „Ir. Sabine Roth, Projectleider") bleef volledig
  onbeschermd staan – de regel zag eruit als een tabelvormige kolomkop
  en werd ten onrechte als zakelijke inhoud verworpen.
- De titel „Dr.-Ing." (een gangbare Duitse ingenieursgraad) vóór een
  naam werd niet in de gemaskeerde persoonswaarde opgenomen en bleef
  leesbaar staan – dezelfde koppelteken-valkuil als bij „Dipl.-Ing.".
- De titels „Dipl.-Kfm.", „Dipl.-Kffr." en „Dipl.-Psych." (diploma
  bedrijfskunde/psycholoog) vóór een naam werden niet in de gemaskeerde
  persoonswaarde opgenomen en bleven leesbaar staan – dezelfde
  koppelteken-valkuil als bij „Dipl.-Ing." en „Dr.-Ing.".
- Een MAC-adres in de Cisco-schrijfwijze met punten in plaats van
  dubbele punten (bijv. „aabb.ccdd.eeff", zoals switch-logboeken en
  supporttickets die afgeven) werd helemaal niet herkend en bleef
  leesbaar staan.
- Een achternaam achter „familie" (bijv. „De familie Gruber
  ondertekent het contract") bleef afhankelijk van de zinsbouw
  onherkend en daarmee leesbaar staan – ook met adellijke titel ervoor
  („Familie von der Leyen").

- Bij een Kroatisch adres zonder scheidend leesteken tussen
  postcode+plaats en straat+huisnummer (bijv. „10000 Zagreb Ulica Ivana
  Lučića 5") bleef het huisnummer niet opgeschoond staan.

- Bij een Litouwse contactaanduiding met de beschrijving „Kontaktinis
  asmuo" (bijv. „Kontaktinis asmuo: Vilkas Jonas") bleef de achternaam
  onherkend, wanneer ze tegelijk een gangbaar zelfstandig naamwoord was
  (Vilkas = „wolf", Vanagas = „havik").

- Een geboorte- of woonland zonder verdere beschrijving in een Deens
  formulierveld (bijv. „Fødeland: Tyskland" of „Bopæl: Tyskland") werd
  niet herkend.

- Een geboorte- of woonland zonder verdere beschrijving in een
  Roemeens formulierveld (bijv. „Țara: Germania" of „Țara de
  reședință: Franța") werd niet herkend.

- Een bedrijfsnaam onder de Litouwse veldbeschrijving „Darbdavys:" of
  „Įmonės pavadinimas:" (werkgever/bedrijf) werd niet herkend.

- Een bedrijfsnaam onder de Russische veldbeschrijving
  „Работодатель:" of „Наименование организации:"
  (werkgever/bedrijf) werd niet herkend.

- Een voluit geschreven datum met maandnaam in het Roemeens (bijv.
  „31 decembrie 2024") werd niet herkend.

- Een Hongaarse geboortenaam achter de afkorting „szül." (bijv. „Nagy
  Éva (szül. Kovács)") werd niet herkend en bleef open leesbaar staan.

- Een opgeslagen HTML-profielpagina (of een e-mail met bijgevoegde
  webpagina) kon de burgerlijke naam niet opgeschoond laten, wanneer die
  alleen in de Open Graph-profielvelden
  `profile:first_name`/`profile:last_name`/`profile:username` stond –
  deze dragen de naam opgesplitst in plaats van beschrijvend zoals
  `og:title` en worden nu eveneens opgeschoond.

- Een onbestelbaarheidsmelding (bounce/NDR) droeg vaak de kopregels van
  de oorspronkelijk onbestelbare mail (afzender, ontvanger, onderwerp)
  in een eigen, derde bijlagedeel – dit bleef in de opgeschoonde versie
  volledig onaangetast staan. Het deel wordt nu net als het overige
  afleveringsrapport opgeschoond.

- De individueel benoemde bewerker van een beschermd gebied in Word
  (Bewerken beperken → Uitzonderingen, `w:permStart`) bleef in klare
  tekst staan, ook als dezelfde naam in de lopende tekst allang was
  opgeschoond. Hij wordt nu eveneens verwijderd.

## 0.10.42-alpha.20260827 – 27 augustus 2026

### Nieuw

- **Benoemde herkenningsprofielen maken verschillende werksituaties met één
  greep bereikbaar.** Onder *Instellingen → Herkenning → Wat wordt
  verwijderd* kan de huidige categorie- en soortselectie worden opgeslagen
  en via een keuzeveld meteen weer worden toegepast. Het vaste profiel
  *Standaard* komt overeen met de bestaande uitleveringsstand en kan niet
  worden verwijderd. Een profiel verandert uitsluitend wat wordt
  verwijderd; taal, uitvoertype, herkenningsdiepte evenals eigen begrippen
  en zoekpatronen blijven onaangetast.

- **Het type resultaat wordt nu direct vóór het opschonen gekozen.** Een
  gemeenschappelijk keuzeveld in het hoofdvenster legt voor de hele
  batch vast of Maskuro leesbare plaatshouders invoegt, zwart maakt of
  zonder vervanging verwijdert. De twee aparte velden voor PDF en Office
  in het instellingenvenster zijn vervallen; daardoor is de belangrijke
  beslissing zichtbaar en kan ze bij gemengde batches niet meer
  onbedoeld uiteenlopen. De begeleide rondleiding legt de nieuwe keuze
  uit vóór het eerste opschonen.

- **Thema's en watermerken markeren voltooide PDF's op verzoek duidelijk.**
  Twaalf totaallooks stemmen vervangteksten en zwartingsvlakken op
  elkaar af; nieuw daarbij zijn Pride evenals lente, zomer, herfst en
  winter. *Geheim dossier* brengt meteen een diagonale `TOP SECRET` mee.
  Onafhankelijk daarvan is een vrije markeringstekst of een eigen
  afbeelding, icoon respectievelijk SVG met kleur en dekking te kiezen.
  Geïmporteerde afbeeldingen worden zonder hun metagegevens ingebed en
  blijven beschikbaar wanneer het bronbestand wordt verplaatst. Bij het
  nabewerken vervangt Maskuro zijn bestaande watermerk, in plaats van
  het meermaals over elkaar te leggen. Tekstwatermerken worden als
  laatste PDF-laag met lichte contour getekend, zodat ze ook op donkere
  afbeeldingen en dichte tekst zichtbaar blijven. De nabewerkingseditor
  negeert Maskuro's watermerk volledig en biedt de tekst ervan niet meer
  als zwartingskandidaat aan.

- **Eigen uitvoerthema's zijn op te slaan en te delen.** De huidige mix
  van vervangtekst, zwarting en watermerk krijgt een naam, blijft in de
  instellingen en kan als klaretekstvrije JSON worden geëxporteerd of
  geïmporteerd. Het zwart-witafdrukvoorbeeld waarschuwt voor zwakke
  contrasten; optionele succesconfetti blijft puur in de interface.

- **Een laatste exportproef en een verklarende controlelaag sluiten de
  weergaveronde af.** Vóór het definitieve opslaan vergelijkt Maskuro
  elke waardegetrouw bekende PDF-plek nogmaals in tekstlaag en
  gerenderde beeldpunten; waarschuwingen noemen uitsluitend pagina en
  coördinaten. In de editor toont *Waarom is dit afgedekt?* categorie,
  herkenningsweg en veiligheidsrand, nooit de verwijderde klare tekst en
  nooit in het einddocument.

- **Zwartingsbalken mogen nu mooi zijn.** Onder *Instellingen →
  Weergave* staan kleurvoorinstellingen, vrije kleurkiezers,
  kleurverlopen, regenbogen, strepen, stippen, bloemen, sterren,
  hartjes, pootjes, wolken, bliksems, koffiebonen, eendjes, zonnen,
  bladeren, sneeuwvlokken, papier-, markeerstift-, plakband- en
  reproduceerbare toevalspatronen samen met direct voorbeeld klaar.
  Vervangteksten krijgen naar keuze een kleur, een verloop, een
  regenboog, een pil of een label. Categoriekleuren onderscheiden namen,
  adressen, contacten en medische gegevens. PDF neemt de volledige
  vormgeving over; Word, PowerPoint, OpenDocument en HTML gebruiken de
  gekozen dekkende basiskleur. De bescherming verandert daarbij niet:
  Maskuro verwijdert de vertrouwelijke inhoud eerst en tekent kleur of
  patroon pas op de lege plek.

- **Maskuro is er weer voor Linux – als AppImage, DEB, RPM en portable
  archief.** DEB en RPM registreren programma-item, bestandskoppelingen,
  terminalopdracht en symbool in het systeem; het AppImage draait zonder
  installatie. Actualiseringen blijven bij een bestaande DEB- of
  RPM-installatie in hetzelfde pakketformaat en geven anders de voorkeur
  aan het AppImage.

- **De visuele controle legt gewone PDF-tekst niet meer een tweede keer
  als nieuwe treffer voor.** De afsluitende OCR-blik en de veilige
  heropbouw van de zichtbare pagina's blijven volledig actief; als
  nieuwe vondstbron gelden in de standaard echter alleen gebieden die
  paginatekst en losse-beeldcontrole nog niet hebben gelezen. Daardoor
  worden productregels niet alleen wegens een afwijkende tweede
  OCR-lezing tot nieuwe namen of bedrijven. Wie verder twee onafhankelijke
  oordelen over de hele zichtbare tekst wil, schakelt in de instellingen
  *De hele zichtbare PDF-pagina nogmaals op gegevens controleren* in.

- **PDF's zijn doorlopend, per blad of als dubbele pagina te bekijken.**
  Drie compacte weergave-iconen zitten onderaan direct naast „Breedte"
  en „Pagina". Doorlopend rolt aan de bladrand naar de volgende pagina;
  enkele pagina houdt het muiswiel op het huidige blad; dubbele pagina
  toont een katern, maakt het aangeklikte blad bewerkbaar en beweegt
  vooruit/achteruit met een heel katern. Paginaminiaturen en
  vergelijkingsvergrootglas openen bovendien in een aanzienlijk smallere
  linker basiskolom en laten de werkpagina meer ruimte.

- **U ziet nu wat het AI-niveau heeft gedaan.** Na elke run staat onder
  „Details" per bestand een regel daarover – „AI-niveau: 12 grensgevallen
  gecontroleerd, 3 verworpen" –, en als het niets te wijzigen vond, staat
  ook dat er. Tot nu toe zweeg het duurste niveau volledig: of het
  überhaupt werd geraadpleegd, was van buitenaf niet te zien.

  Wie het preciezer nodig heeft, schakelt onder „Instellingen → AI" *Elke
  AI-vraag in het logboek bijhouden* in. Dan legt het logbestand per
  vraag grootte, duur en aantal bevindingen vast, plus de wachttijd door
  een hoeveelheidsgrens van de tegenpartij. De knop „Logbestand tonen"
  ernaast opent de map – die ligt in de toepassingsgegevensmap, die
  onder Windows verborgen is en die uit zichzelf niemand vindt. In het
  bestand staan uitsluitend groottes, nooit tekst uit uw documenten.

- **Maskuro herkent wanneer uw AI-dienst het aantal verzoeken beperkt.**
  Gehoste diensten laten vaak maar weinig verzoeken per minuut toe – vier
  is geen zeldzaamheid. De overtollige worden niet afgewezen, maar
  moeten wachten, en van twee seconden per antwoord worden er veertig.
  Dat zag er tot nu toe uit alsof het model traag was. Nu leest Maskuro
  de grens uit het antwoord van de dienst, stuurt niet meer vragen
  tegelijk dan er worden aangenomen, noemt de grens onder „Verbinding
  controleren" en rekent haar mee in de duurschatting.

- **De paginaweergave gebruikt uw Word, Excel en PowerPoint – en is
  daarbij ongeveer zes keer sneller.** Tot nu toe had ze LibreOffice
  nodig, dat op de minste kantoorcomputers staat; wie het niet had, zag
  een knop die om een vreemde installatie vroeg. Nu geldt: is Microsoft
  Office geïnstalleerd, dan wordt het vanzelf gebruikt – zonder
  inrichting, zonder download, zonder dat u iets aanvinkt. LibreOffice
  blijft de tweede weg en bij OpenDocument-bestanden zelfs de eerste;
  mislukt de ene, dan wordt de andere geprobeerd.

  Het verschil is vooral bij het werken te merken: na elke vervanging
  wordt de pagina opnieuw gezet, en dat kost via Office ongeveer een
  halve seconde in plaats van drie. De eerste weergave van een document
  duurt nog een paar seconden, daarna volgt ze uw handelingen zonder
  wachttijd.

  Uw eigen geopende Word wordt daarbij niet aangeraakt: Maskuro start
  een eigen, onzichtbare sessie, opent het bestand alleen lezend,
  schakelt macro's uit en beëindigt alles weer zodra het
  nabewerkingsvenster dichtgaat. Wachtwoordbeveiligde bestanden worden
  geweigerd, in plaats van in een onzichtbare dialoog te blijven hangen.

- **De eerste inrichting vraagt nu ook naar gezichten, codes en
  handtekeningen – en laadt alles wat ontbreekt in één keer.** Naast de
  uitgebreide herkenning staan op de eerste pagina de drie
  beeldschakelaars: gezichtsgebieden onherkenbaar maken, streep- en
  QR-codes onherkenbaar maken, handgeschreven handtekeningen op
  PDF-pagina's zwarten. De PDF-grens staat zichtbaar bij het vinkje;
  Office-bestanden worden niet automatisch op handtekeningen doorzocht.
  Onder de vinkjes staat hoeveel megabyte de klik op „Volgende" kost.
  Geladen wordt daarna in **één** venster met **één**
  voortgangsbalk over alles samen, in plaats van in meerdere dialogen
  na elkaar; een afbreking beëindigt het hele proces en laat niets half
  liggen. Wie niets daarvan wil, haalt de vinkjes weg – dan wordt ook
  niets geladen.

- **Het voorbeeld kan naar controlebehoefte worden uitgedund en naar
  soort worden ingeklapt.** Boven de lijst zit een schuifregelaar *Goed
  onderbouwde verbergen*: hoe verder hij naar rechts staat, hoe meer hij
  van groen richting rood verbergt; helemaal rechts staat alleen nog
  wat het programma zelf heeft geraden. Een klik op de kop van een soort
  klapt hem in. Beide zijn een leeshulp, geen selectie: wat verborgen of
  ingeklapt is, blijft aangevinkt en wordt vervangen; hoeveel waarden
  dat op dat moment zijn, staat onder de regelaar. Bij korte lijsten
  verschijnt de regelaar niet. Het omschakelen naar twee kolommen houdt
  nu bovendien ook de schakelaars *nooit meer* vast.

- **De beeldenlijst kan zich vóór elke run vanzelf openen.** Wie over
  elke afbeelding afzonderlijk wil beslissen, zet onder „Afbeeldingen"
  het nieuwe vinkje *Vóór elke run afzonderlijk vastleggen*. De lijst
  met voorbeeld verschijnt dan bij het opschonen vanzelf, in plaats
  van dat u „Afzonderlijk vastleggen …" elke keer zelf aanklikt; breekt
  u haar af, dan wordt er ook niet opgeschoond. Bevat geen van de gekozen
  bestanden een afbeelding, dan verschijnt niets. Standaard staat het
  vinkje uit.
- **Maskuro vindt op PDF-pagina's handgeschreven handtekeningen en
  verwijdert ze uit de beeldpunten.** Tot nu toe bleef de handtekening
  onder een opgeschoond document staan – de tekstherkenning leest
  drukletters, en wat ze niet leest, wordt niet vervangen. De zoektocht
  is een eigen schakelaar en heeft een herkenningsmodel nodig dat
  eenmalig wordt nageladen.

  Ze vindt gemeten ongeveer 84 van de 100 handtekeningen en dekt ze voor
  ongeveer vier vijfde af. Dat is een hulp en geen garantie: na elke run
  staat in het rapport hoeveel er zijn gevonden – ook als het er geen
  was, want dat kan betekenen dat er geen is of dat er een over het
  hoofd is gezien. Op 72 echte zakelijke pagina's zonder handtekening
  heeft ze er geen verzonnen.

  Een **getekende** handtekening wordt gevonden, maar niet verwijderd:
  ze bestaat uit lijnen, niet uit beeldpunten, en een balk erover zou
  alleen een afdekking zijn waaronder de lijnen bleven staan. Zulke
  plekken worden geteld en genoemd, zodat men ze in het
  nabewerkingsvenster zelf kan zwarten.

  Word-, Excel-, PowerPoint- en OpenDocument-bestanden worden niet
  automatisch op handtekeningen doorzocht. Interface, eerste inrichting,
  modeldownload, opdrachtregel en handboek noemen deze grens nu
  uitdrukkelijk.

- **De rondleiding voert nu ook door het voorbeeld – het venster waarin
  u beslist.** Bij het oefendocument gaat het vanzelf open, ook als u
  het voorbeeld verder heeft uitgeschakeld (uw instelling blijft zoals
  ze is). Uitgelegd wordt wat de kleuren betekenen, waarom in elke regel
  maar één vraag staat – is daar überhaupt een persoon? – en waarvoor
  „nooit meer" goed is. Bij de kleuren ligt de schijnwerper op een goed
  onderbouwde regel, meestal de IBAN – het groene voorbeeld dat de zin
  noemt; daarna op de zwakst onderbouwde, en daar mag u midden in de
  uitleg zelf klikken: vinkje weg, de waarde blijft in het document
  staan. Bij een lange lijst gaat het venster voor de begeleiding groter
  open, zodat de uitleg niet op de regels ligt. Gaat het venster een
  tweede keer open, dan zegt de rondleiding ook waarom – de voltooide
  pagina wordt nog een keer als afbeelding gelezen, en daarbij ontstaan
  fragmenten die op een naam lijken.

- **De editor gaat de eerste keer groot open.** Origineel, resultaat,
  werkbalk en treflijst staan naast elkaar en hadden in de bestaande
  basisgrootte te weinig ruimte. Wie het venster kleiner trekt, krijgt
  zijn grootte de volgende keer terug – niemand wordt overstemd.

- **Een dubbelklik op een plaatshouder haalt hem terug** – in Word,
  Excel, PowerPoint, OpenDocument, tekst, e-mail en HTML. En wie over
  meerdere plaatshouders sleept en „Selectie terughalen" kiest, haalt
  alle daarin liggende in één keer terug. Men hoeft het vierkante haakje
  dus niet meer precies te raken. Plaatshouders die bij het
  anonimiseren voor meerdere verschillende waarden staan, blijven
  daarvan uitgezonderd – ze worden geteld en genoemd, niet geraden.

- **Het handboek heeft een hoofdstuk „Voorbeeld vóór het vervangen".**
  Het venster staat standaard aan en is het enige waarin u beslist – in
  het handboek stond het tot nu toe alleen in de bijzin. Nu staat daar
  wat een vinkje betekent (het geldt voor **elke** vindplaats, niet
  alleen de opgevoerde), waarom per regel maar één vraag te
  beantwoorden is, wat „nooit meer" blijvend bewerkstelligt, en waarom
  het venster bij een PDF een tweede keer kan opengaan. In alle
  achttien talen, en in de lijst van de instellingen staat de schakelaar
  nu ook vermeld.

### Gewijzigd

- **Het vak „Vervangen waarden" heeft een regelaar over de kleuren, en
  de leermodus staat daar niet meer.** Bij meer dan acht waarden zit
  boven de lijst dezelfde regelaar als in het voorbeeldvenster: *Goed
  onderbouwde verbergen* dunt de weergave uit tot wat werkelijk moet
  worden nagekeken. Aan het document verandert dat niets, en hoeveel
  regels van hoeveel te zien zijn, staat eronder – zoekveld en regelaar
  tellen samen. Het vinkje *Leermodus* is uit het vak verdwenen; het
  staat verder in het menu *Werktuigen* en in de werkbalk.

- **Het vak „Vervangen waarden" toont nu dezelfde kleuren als het
  document.** Elke regel erin is zo ondergrond als de plek in het
  document en zoals de waarde in het voorbeeld: rood betekent „alleen
  geraden, hier loont de tweede blik het eerst", groen „door een
  benoemd patroon herkend". Binnen elke soort staat het onzekerste
  bovenaan – u werkt de lijst dus van boven naar beneden af en heeft
  het belangrijkste het eerst gezien. Tot nu toe stond daar alles even
  licht en op alfabet gesorteerd.

- **De leermodus staat standaard uit.** Na een correctie in het
  nabewerkingsvenster vroeg het programma tot nu toe uit zichzelf of
  daar een eigen regel van moest worden gemaakt. Deze vraag komt midden
  in het werk; wie haar niet had besteld, ervaart haar als onderbreking.
  Wie de regels wil hebben, schakelt de knop *Leermodus* in de werkbalk
  in – de keuze geldt dan blijvend, in beide richtingen.

### Opgelost

- **Geëxporteerde regelbestanden worden nu uitdrukkelijk als beschermenswaardig
  gemarkeerd.** Eigen begrippen en uitzonderingen kunnen erin in klare
  tekst staan; bovendien kan het bestand het hashzout bevatten waarmee
  vermoede waarden te bevestigen zijn. De geslaagde export toont daarom
  een waarschuwing en vraagt het bestand te beschermen en alleen bewust
  aan bevoegde ontvangers door te geven.

- **De laatste veiligheidscontrole houdt opgeschoonde kantoorbestanden niet
  meer tegen wegens hun eigen plaatshouders.** Een soortafkorting zoals
  „SVNR" staat ook in `[SVNR1]`; tot nu toe gold dat als vermeende
  restklaretekst en het voltooide bestand werd verworpen. Tegelijk
  worden telefoonnummers en IBAN's nu ook nagetrokken waar Office
  hetzelfde gegeven zonder zichtbare spaties in een verwijzing of een
  ingebed bestand opslaat.

- **Word, Excel, PowerPoint en OpenDocument laten geen pas laat ontdekte
  veldkopie meer staan.** Wordt een waarde voor het eerst in een
  nevenopslag of ingebed kantoorbestand herkend, dan ruimt een strikte
  nacontrole ook de eerder gelezen zichtbare en verborgen kopieën op.
  Al gemaakte verwijzingsplaatshouders worden daarbij niet nog eens
  vervangen.

- **Bij het afzonderlijk terughalen van een Word-keuzelijst komt geen
  naburige keuze meer ongevraagd mee terug.** De volledige originele
  alinea wordt pas overgenomen wanneer ook haar attributen geen open
  plaatshouders meer bevatten.

- **Slecht leesbare scans verliezen minder samenhangende gegevens.** Een
  alternatieve OCR-lezing met aanhef en tweeledige naam blijft behouden;
  straatfragment, huisnummer en postcode-plaats beschermen samen de hele
  adresregel, ook wanneer ze in naburige OCR-blokken uiteenvalt.
  Factuur- en artikelvelden evenals evenementregels ernaast worden
  daarbij niet meegenomen. Een achter „geboren" in meerdere OCR-woorden
  en leestekens uiteengevallen geldige datum wordt eveneens volledig
  onherkenbaar gemaakt.

- **De succesconfetti is bij het automatisch openen van de editor nu
  zichtbaar.** De snippers spuiten direct uit de *Opschonen*-knop in
  plaats van van de bovenrand van het venster te regenen. De editor
  wacht alleen op de eerste, 850 milliseconden korte spuitstoot en
  opent daarna automatisch; zonder geactiveerde confetti blijft er
  verder geen vertraging.

- **Paginateller en zoombalk springen bij het overgaan van de
  weergave-iconen niet meer heen en weer.** Qt herverdeelde de vrije
  ruimte van de statusregel zodra daar de aanwijzing van een symbool
  verscheen. Beide bedieningsgroepen behouden nu bij hover hun
  natuurlijke breedte en vaste positie.

- **De snelheidsmeting van een gekoppelde AI-server mislukte altijd** –
  op elke server, sinds de eigen AI bestaat. Ze vroeg met een strakke
  antwoordgrens en probeerde vervolgens het daardoor afgesneden antwoord
  te lezen; dat moest mislukken, en opgeslagen werd „niet gemeten". De
  gevolgen waren overal te zien: de duurschatting rekende uw server met
  het tempo van het bijgeleverde model op een kantoorcomputer, en in de
  instellingen stond blijvend dat de snelheid nog niet gemeten was.
  Gemeten wordt nu aan de hoeveelheid die de server heeft gegenereerd,
  en niet aan de inhoud van zijn antwoord.

- **„Maximale herkenning (AI) – traag" stond er ook wanneer het niet
  klopte.** Beschrijving en aanwijzing beschreven het bijgeleverde model
  op een kantoorcomputer – „een taalmodel op deze computer", „bij grote
  documenten tot een uur". Wie een eigen AI-server had gekoppeld, las
  daar twee onjuiste dingen: er wordt niet op zijn computer gerekend, en
  er wordt in seconden geantwoord in plaats van in uren. Beide komen nu
  uit de meting. Is er geen, dan beweert de toepassing niets meer, maar
  zegt ze dat nog niet is gemeten.

- **Terughalen werkt nu ook op een gesleepte selectie.** Wie over
  meerdere plaatshouders sleepte en *Selectie terughalen* wilde
  indrukken, vond de knop grijs: hij ging alleen aan als de markering
  **exact** één plaatshouder was – over een alinea gesleept is dat
  nooit. De weg daarachter bestond al, alleen kwam niemand erbij. Nu
  volstaat het het gebied te markeren; alle plaatshouders erin komen in
  één keer terug.

- **Terughalen crashte wanneer het vergelijkingsvergrootglas open
  stond.** Het vergrootglas onthoudt de plek onder de muisaanwijzer, om
  in het origineel mee te lopen. Bij het opnieuw laden na een
  terughaling gaf het deze plek terug in een vorm waarmee de
  tekstweergave niets kon beginnen – en omdat zo'n fout midden in de
  interface het programma beëindigt, was van de terughaling een crash
  geworden. Het vergrootglas staat in de basisstand open, het trof dus
  de gewone weg.

- **Na het terughalen springt de weergave niet meer naar het begin van
  het document.** In een langer schrijven was na elke handeling de plek
  weg waaraan men net werkte. Nu blijft de alinea boven staan die
  daarvoor boven stond.

- **Zonder LibreOffice zegt de paginaweergave waar het vandaan komt, in
  plaats van alleen te ontbreken.** De twee knoppen *Paginaweergave* en
  *Als PDF zwarten* waren geblokkeerd en noemden in de tooltip alleen
  dat geen LibreOffice was gevonden; een weg daarheen bestond nergens
  in de toepassing. Een klik opent nu een aanwijzing met de weg naar
  het gratis, open source LibreOffice. Handboek en FAQ stonden op dit
  punt fout – ze kondigden een na te laden bouwsteen aan die de
  toepassing niet aanbiedt.

- **Vóór het uitleveren wordt het voltooide bestand een laatste keer
  helemaal doorzocht – nu ook bij Word, Excel, PowerPoint, LibreOffice,
  e-mail, HTML en tekst.** Tot nu toe had alleen de PDF deze laatste
  blik. Alle controles daarvoor kijken op een plek die vooraf iemand
  heeft benoemd; een opslag waaraan niemand heeft gedacht, controleert
  daarom ook niemand. Ten slotte wordt nu bot naar alles gezocht wat
  werd vervangen – in elk deel van het pakket. Blijft er iets staan,
  dan ontstaat **geen** resultaat, en de melding noemt de waarde. Een
  bestand dat voor opgeschoond wordt gehouden, is erger dan helemaal geen.

- **Namen in `<script>` en `<style>` worden nu gemeld.** Beide blijven
  verder onaangetast – daar staat programmatekst, en een vervanging
  midden in een naam maakt van een webpagina een kapotte webpagina. Dat
  werd echter tot nu toe niet gezegd, en dat was de fout: een stijlregel
  `content: "Anna Modelvrouw"` staat de ontvanger **zichtbaar** op het
  scherm, en in het resultaat bleef ze staan, terwijl het programma de
  pagina als opgeschoond meldde.

- **In de instellingen laten de extra modellen zich weer laden en
  verwijderen.** De knop naast „Uitgebreide herkenning" en „Maximale
  herkenning (AI)" eindigde bij het indrukken in het
  foutrapport-venster, in plaats van het model op te halen. De tweede
  weg – het vinkje in de herkenning, dat vanzelf naar het model vraagt
  – was daar nooit door getroffen.

- **Namen die in blad- en bereiknamen van een tabel zitten, worden nu
  gemeld.** De naam van een blad staat op het tabblad onderaan, de naam
  van een benoemd bereik in het naamvak en in elke formule die hem
  gebruikt. Vervangen worden beide verder niet – formules verwijzen via
  hen, en een werkmap met verwijzingsfouten helpt niemand –, maar het
  staat er nu. Tot nu toe kwam de melding alleen voor de bladnaam van
  een Excel-werkmap: een benoemd bereik „Bezuege_Brunnthaler" ging
  stilzwijgend mee naar buiten, en bij een LibreOffice-tabel zweeg het
  programma helemaal. Een blad „Notities Ortner" gold daarmee als
  opgeschoond, en de eerste blik van de ontvanger viel op de naam.

  Gemeld wordt daarbij alleen wat echt naar een persoon leidt: een woord
  dat in dezelfde werkmap toch al werd vervangen, of een treffer die uit
  meerdere woorden er één kiest. Een alleenstaand woord zoals
  „Verantwoordelijk" of „Bezug_Omzet" veroorzaakt geen waarschuwing meer
  – voorheen had het dat gedaan, en een waarschuwing die bij elke tweede
  werkmap komt, leest na de derde keer niemand meer.

- **„Origineel terughalen" haalt nu echt alles terug.** In sommige
  documenten ontbraken daarna losse tekens – van „Zeestraat 14" werd
  „Zeestraat 4", van „Aan:" een „Aan", van „noordlicht-planning" een
  „noordlicht planning" –, en losse regels kwamen helemaal niet terug.
  Juist daar viel daarna niets meer met de muis te selecteren en niets
  meer te zwarten: de tekst stond wel op het papier, maar het programma
  kende hem niet meer. Getroffen waren smalle tekens – de één, de
  dubbele punt, het koppelteken – in documenten die elk teken
  afzonderlijk zetten; het oefendocument is daar één van.

- **En dezelfde documenten worden bij het opschonen niet meer naar een
  afbeelding omgezet.** Omdat zo'n teken bleef staan, meldde de
  nacontrole een restant en werd de pagina voor de zekerheid
  gerasterd. De tekst erop was daarna nog maar een afbeelding: niet
  meer doorzoekbaar, niet meer markeerbaar, groter in het bestand. Het
  oefendocument blijft nu op beide pagina's echte tekst.

- **Gekleurde markeringen blijven niet meer over teruggehaalde tekst
  staan.** Wie een vervanging ongedaan maakte, zag het gekleurde
  rechthoek toch boven het herstelde woord staan – het beweerde „hier
  werd iets verwijderd", hoewel daar weer het origineel stond.

- **Een balk verraadt niet meer hoe lang het woord eronder was.** Bij
  het zwarten dekt de balk in korte regels nu de **hele** regel –
  adresblok, kopgegevens, smalle tabelcel. Past de hele regel niet (de
  gewone tabelregel met drie kolommen), dan blijft het bij het veld; in
  een lopende-tekstregel blijft het woordnauwkeurig, anders maakte een
  naam midden in de zin de hele zin zwart. En balken die onder elkaar
  staan, worden **even lang**: in het adresblok staat op elke regel een
  waarde, en drie verschillend lange balken verraadden verder hoe lang
  de regels waren. Ze groeien daarbij alleen zo ver als het papier vrij
  is – vóór een naburige kolom houdt de balk op.

- **„Hele regel" zwart nu echt de hele regel.** Tot nu toe eindigde de
  balk bij de volgende grotere leemte – dus aan het einde van het veld.
  In lopende tekst viel dat niet op, daar is het veld de regel; in
  kopgegevens en tabellen wel: van „Naam: Anna Modelvrouw   Afdeling:
  Verkoop" werd een balk die precies bij de laatste letter van de naam
  eindigde – en daarmee stond diens lengte weer op het blad. De balk
  loopt nu van het eerste tot het laatste woord van de regel en neemt
  de naburige kolommen mee. Wie alleen de waarde wil raken, kiest
  „Woorden"; de automatiek zwart ongewijzigd veldsgewijs.

- **Vóór het uitleveren wordt het voltooide bestand een laatste keer
  doorzocht.** Alle bestaande controles kijken op een plek die vooraf
  iemand heeft benoemd – paginatekst, vondstrechthoek, beeldvlak. Een
  PDF heeft echter meer opslagen dan een opsomming kan bevatten:
  annotaties, formulierwaarden, bladwijzers, documentinformatie,
  bestandsbijlagen, JavaScript. Ten slotte doorzoekt Maskuro daarom het
  geschreven bestand bot naar alles wat het heeft vervangen – overal
  behalve in de paginatekst, waar dezelfde bewoording ook toegestaan
  mag staan. Blijft daar iets staan, dan ontstaat **geen** resultaat,
  en de melding noemt de waarde. Een document dat voor opgeschoond wordt
  gehouden, is erger dan helemaal geen.

- **Wat niet gecontroleerd kon worden, geldt niet meer als
  gecontroleerd.** Op drie manieren zag tot nu toe een mislukking van
  de nacontrole eruit als een schoon resultaat. Een pagina waarvan de
  tekstlaag niet leesbaar was, gold als bijzonder schoon – daar was
  immers niets te vinden; ze wordt nu gerasterd. Kon een pagina met
  resterende vindplaats niet vervangend worden gerasterd, dan werd ze
  stilzwijgend uitgeleverd; nu breekt de opschoning liever af. En de
  tegencontrole in het nabewerkingsvenster meldde na een eigen fout
  „niets over" – in het venster niet te onderscheiden van dat alles was
  verwijderd; nu verschijnt de waarschuwing samen met de knop „Pagina
  rasteren".

- **„Terugzetten naar standaard" zette de meeste instellingen helemaal
  niet terug.** Negen van tweeëntwintig vinkjes stonden na de handeling
  ongewijzigd – waaronder het voorbeeld, „Opgeschoonde bestanden daarna
  openen", het nabewerkingsvenster, het direct opslaan en beide
  actualiseringsvinkjes. Het opgeslagen bestand was wel leeggemaakt,
  maar het venster hield de oude waarden vast en schreef ze bij de
  volgende klik weer erin. Nu komt elk vinkje terug, en de aantekening
  „gewijzigd" verdwijnt ermee.
- **„Controlerapport per opschoning automatisch opslaan" gaf aan, maar
  stond uit.** Na het terugzetten bleef het vinkje gezet, terwijl de
  waarde gewist was – er ontstond geen rapport meer, zonder dat iets
  daarop wees. Hetzelfde gold voor het controlelogboek en de eigen
  schermopname; hun toetsencombinatie wordt bij het terugzetten nu ook
  meteen correct aan- of afgemeld.

- **De balken van een regel zien er nu hetzelfde uit.** Tot nu toe
  bracht elke vindplaats haar eigen balk mee, en zijn hoogte kwam uit
  het lettertype van het getroffen woord. In een regel met beschrijving
  en waarde in verschillende groottes stonden daardoor een dikke en een
  dunne streep met verspringende randen naast elkaar, en waar twee
  vindplaatsen slechts een spatie scheidde, bleef daarboven een lichte
  spleet. Balken van dezelfde regel hebben nu dezelfde boven- en
  onderkant, en wat maar een spatie scheidt, wordt één balk. Wat tussen
  twee vindplaatsen moet blijven staan – de komma achter de naam, een
  beschrijving, een bedrag – houdt ze verder uit elkaar. Geldt voor
  gezette pagina's zoals voor scans.

- **De tabbladen onder „Over dit programma" beginnen weer bovenaan.**
  Privacy, licentievoorwaarden en licentievermeldingen gingen midden in
  de tekst open – wie ze las, moest eerst helemaal naar boven scrollen
  om de eerste regel te zien.

- **De pen opent geen tweede editorvenster meer, maar haalt het
  bestaande naar voren.** Tot nu toe ontstond bij elke klik een nieuwe.
  Het venster heeft geen eigen item in de taakbalk – wie het
  minimaliseerde, kwam er niet meer bij en klikte nog eens; bij het
  herstellen van het hoofdvenster kwamen dan alle opgehoopte vensters
  ineens naar voren. Nu belanden verdere documenten in de tabbladbalk
  van het open venster, en een document dat daar al staat, krijgt geen
  tweede tabblad.

- **„Uitgebreide herkenning" draagt niet meer de aantekening
  „gewijzigd" zolang haar model ontbreekt.** Uitgeleverd wordt ze
  ingeschakeld, zonder het na te laden model kan ze het echter helemaal
  niet zijn – in de instellingen stond de regel daarom op elke vers
  ingerichte computer als gewijzigd, hoewel niemand hem had aangeraakt.
  Waarom het vinkje uit is, zegt nu alleen zijn opschrift: „Model nog
  niet geladen".

- **De introstrook legde in Office- en tekstbestanden het PDF-canvas
  uit.** Daar stond „een woord aanklikken zwart het" – in een
  Word-bestand zwart een klik echter niets, daar wordt gemarkeerd en
  dan een knop ingedrukt. Ze zegt nu wat in de betreffende weergave
  geldt.
- **De werkbalk was in de tekstweergave met opschriften dichtgezet.**
  „Selectie vervangen", „Selectie zwarten", „Selectie terughalen",
  „Paginaweergave" en „Als PDF zwarten" staan nu als symbool – zoals hun
  broers en zussen in een PDF. Hun namen blijven in de korte hulp en
  het menu.
- **Ctrl+muiswiel in het vergelijkingsvergrootglas bewoog zijn
  zoomregelaar niet mee.** Het lettertype werd groter, regelaar en
  percentage ernaast bleven de oude stand beweren.
- **Het installatieprogramma van een actualisering kwam niet naar
  voren** – men moest het eerst in de taakbalk aanklikken (alleen
  Windows).
- **Een jaartal aan het begin van een regel gold als Oostenrijkse
  postcode.** In een cv werd van „2020 Verkoopstrategieën" een
  plaatshouder – de hele regel verdween. Een viercijferig getal tussen
  1900 en 2099 heeft nu een tweede adressignaal nodig: de straat erboven,
  een veldwoord ervoor, een landcode of een bekende plaatsnaam.
  Adresblokken hebben dat; jaarkolommen niet.
- **Een maand-jaarpaar gold als telefoonnummer.** Van „Sinds 08.2010
  123-Verkoop BV" werd een „telefoonnummer" – maand, jaar en de eerste
  cijfers van de bedrijfsnaam erachter.
- **Het rapport zei „met tekstherkenning gecontroleerd" en verzweeg wat
  ze niet leest.** Blijven afbeeldingen behouden, dan staat er nu bij
  dat handgeschrevene daarin niet wordt gevonden – een handtekening of
  een handgeschreven ingevulde naam blijft staan. Tot nu toe stond deze
  zin alleen bij gescande pagina's; een gewone PDF met een ingebedde
  handtekening kreeg er geen woord over.
- **Een plaatshouder op gezwarte beeldgrond stond aan de linkerrand van
  zijn balk.** Wordt een waarde in een afbeelding gevonden – bijvoorbeeld
  een getypte naam naast een ingescande handtekening –, dan moet het
  beeldgebied over de volle breedte worden gezwart. De kortere
  plaatshouder liet ernaast kaal zwart staan, wat eruitzag als twee
  bewerkingen. Hij zit nu gecentreerd op de balk.

## 0.10.41-alpha.20260826 – 26 augustus 2026

### Nieuw

- **Na de testperiode herinnert een venster eenmaal per start aan de
  licentie.** Het komt vijf minuten na de start – niet meteen, zodat het
  niemand voor de eerste handeling in de weg staat – en wacht zolang een
  opschoning loopt. Van daaruit leidt een weg naar de aankoop en een
  naar het invoeren van een al gekochte sleutel; „Later" sluit het
  zodra de vijf seconden in de knop zijn verstreken. Er wordt niets
  geblokkeerd: het gratis niveau werkt verder zoals voorheen.

- **De wachttijd vóór een run in het gratis niveau duurt nu tien in
  plaats van dertig seconden.** Ze moet aan de licentie herinneren, niet
  het werk stilleggen.

- **Alle drie de aanwijzingen over de licentie zien er nu hetzelfde
  uit.** Wachttijd, herinnering in de laatste testdagen en aanwijzing na
  de testperiode dragen dezelfde strook, dezelfde opbouw en dezelfde
  knoppen; de resttijd staat daarbij in de knop in plaats van als groot
  getal ernaast.

- **De treflijst in het voorbeeld staat weer onder elkaar.** Ze was
  vanaf negen waarden tweekoloms; bij het doorlopen springt het oog
  daarbij tussen twee banen, en beslist wordt hier regel voor regel. Wie
  de twee banen mooi vindt, schakelt ze linksonder in het venster weer
  in – de keuze blijft opgeslagen, en bij het omschakelen blijven al
  afgevinkte waarden afgevinkt.

- **Het AI-niveau staat open voor iedereen die een eigen AI-server
  koppelt.** „Instellingen → AI" voert er alles voor: de koppeling, wat
  de AI mag doen, wat ze te doen krijgt – en daarboven de schakelaar
  voor het niveau samen met een tegencontrole, zodra een server is
  ingevoerd. Een taalmodel dat op de eigen werkplek meerekent, blijft
  tegengehouden: het heeft voor tien pagina's meerdere minuten nodig en
  is daarmee niets voor het dagelijks gebruik.

- **Een eigen AI is te koppelen.** In plaats van het meegeleverde
  taalmodel kan een groter model op een andere computer antwoorden – op
  een server in huis of een werkstation met een sterke grafische kaart.
  Vereist is een dienst met OpenAI-compatibele interface (Ollama, LM
  Studio, llama.cpp-server, vLLM, LocalAI); ingericht wordt hij onder
  „Instellingen → Eigen AI" samen met een verbindingscontrole die het
  model echt bevraagt, het tempo meet en de mogelijke antwoordvorm
  vaststelt. Meerdere tekstfragmenten lopen daarbij gelijktijdig in
  plaats van na elkaar.

- **Wat de AI mag doen en wat ze te doen krijgt, is nu instelbaar.** Drie
  schakelaars beslissen over grensgevallencontrole, zelfstandig zoeken
  en zoeken in lopende tekst; de instructie aan het model staat letterlijk
  erbij, is aan te vullen met huisbegrippen en met een knop terug te
  zetten naar de standaard.

- **Verlaat de tekst daarbij het eigen netwerk, dan wordt vóór elke run
  gewaarschuwd.** Maskuro herkent aan het adres of de AI-server in huis
  staat, en noemt een bekende aanbieder bij naam. De waarschuwing is uit
  te schakelen, maar alleen met de uitdrukkelijke bevestiging bevoegd te
  zijn tot deze overdracht, en alleen voor precies dat adres. Aan het
  proces verandert dat niets: de overdracht staat verder in het logboek
  en in het controlerapport van elk bestand. Op de opdrachtregel wordt
  niet gevraagd, maar gestopt – daar is `--ki-auswaerts-erlauben` nodig.

- **Het voorbeeld vóór het vervangen is bij nieuwe instellingen standaard
  actief en geldt nu ook voor uitdrukkelijk opgeschoonde
  klembordinhoud evenals tekst en afbeeldingen die in het programma
  worden geplakt.** Bij documentbatches verschijnt verder precies één
  voorbeeld per document met alle pagina's; de stille directe
  opschoning van korte kopieën opent bewust geen venster.

- **Treffers zijn in het voorbeeld over de hele gekleurde regel in en
  uit te schakelen.** Het vinkje is nu groot en contrastrijk; bovendien
  toont een statusveld „Vervangen" resp. doorgestreept „Vervangen",
  zodat geselecteerde en afgevinkte waarden ook op donkere
  betrouwbaarheidskleuren meteen uit elkaar te houden zijn.

- **Ook PDF's met zichtbare veiligheids-tegenblik openen het voorbeeld
  nog maar één keer per document.** Afgevinkte begrippen blijven voor de
  latere paginatoets afgevinkt; diens controle loopt verder, zonder
  dezelfde run met een tweede dialoog te onderbreken.

- **Vervangwoorden zien er in de nabewerkingseditor ook op gerasterde
  pagina's hetzelfde uit.** Ligt de rode plaatshouder in de beeldpunten
  in plaats van in de PDF-tekstlaag, dan krijgt hij nu toch hetzelfde
  naar betrouwbaarheid gekleurde achtergrondvlak als een gewone
  PDF-tekstplaatshouder.

- **Al het voorbeeld vóór het vervangen toont de controlebehoefte van de
  gevonden begrippen.** Elke regel draagt dezelfde rood-oranje-groene
  kleur als later de vervanging in de editor. Binnen een categorie staan
  lage zekerheid en rode vals-alarmkandidaten bovenaan, sterke groene
  bewijzen onderaan; gelijke standen blijven alfabetisch. Komt dezelfde
  waarde uit meerdere vindplaatsen, dan telt voor de zekerheid haar meest
  twijfelachtige beoordeling. Onbeoordeelde bijzondere gevallen staan
  neutraal geel tussen rood en oranje.

- **Het resultaat is nu direct vanuit de nabewerkingseditor als bestand
  te kopiëren.** „Resultaat kopiëren" legt de huidige opgeschoonde versie
  op het klembord, zonder de editor te sluiten en het bestand in de
  hoofdlijst weer op te zoeken. Bij een nog niet opgeslagen handmatige
  bewerking loopt daarvoor automatisch het volledige veilige
  opslagpad; „Afbeelding kopiëren" blijft als aparte functie voor pure
  beeldpunten behouden.

- **Vervangen woorden tonen in de editor in één oogopslag wat het eerst
  moet worden gecontroleerd.** Pure taalmodel-gissing is rood, ook als
  spaCy daarvoor algemeen 85 procent meldt. Verdere ongestaafde
  modeloordelen blijven hoogstens oranje; sterke benoemde bewijzen
  kunnen groen worden. Handwerk en oudere toewijzingen zonder
  evalueerbare beoordeling blijven neutraal geel. Ook automatische
  zwartbalken dragen deze kleuren in het editorvoorbeeld – nu ook
  wanneer de balk deel uitmaakt van een gerasterde PDF-pagina. Daarvoor
  moet de toewijzing kloppen en het eerdere woordkader aantoonbaar
  dekkend zwart zijn; gewone vetdruk wordt niet ingekleurd. In de
  opgeslagen PDF blijven alle balken ongewijzigd dekkend zwart.

- **Wat in het voorbeeld wordt afgevinkt, is blijvend te onthouden.** Waar
  u het vinkje weghaalt, zegt u: hier heeft de herkenning zich vergist.
  Tot nu toe gold dat alleen voor dit ene document. Nu verschijnt bij de
  regel een schakelaar „nooit meer"; ingedrukt komt de waarde blijvend
  in de lijst „Nooit verwijderen" en geldt voortaan in elk document als
  onbedenkelijk. Onder de lijst staat wat daarbij blijvend wordt,
  voordat u op „Vervangen" drukt. De omgekeerde richting bestaat bewust
  niet: wat eenmaal gevonden werd, vindt de herkenning opnieuw.

- **Een knop zet alle instellingen terug naar de uitleveringsstand.** Hij
  staat linksonder in het instellingenvenster en vraagt vooraf om
  bevestiging. Uw bestanden, uw licentie, uw eigen herkenningsregels en
  het automatisch opstarten blijven onaangetast; wat uw beheer
  voorschrijft, geldt verder. Elke instelling die afwijkt van de
  uitleveringsstand draagt bovendien de aantekening „gewijzigd" – zo
  ziet men in één oogopslag wat men heeft veranderd.

### Gewijzigd

- **Een resultaat wordt niet meer vanzelf opgeslagen – pas bij het
  opslaan.** Een run vanuit het venster schrijft zijn opgeschoonde versie
  eerst naar een tijdelijke plek; het bestand „…_opgeschoond" naast het
  origineel ontstaat pas wanneer u op „Opslaan" drukt. Tot dan is het
  resultaat te bekijken, na te bewerken en te kopiëren. Elke voltooide
  regel heeft daarvoor een opslaanknop, onder de lijst staat „Alles
  opslaan", en in de editor geldt Ctrl+S. Wie de lijst leegt of het
  programma afsluit, wordt gevraagd; wat niemand opslaat, blijft ook
  nergens liggen. „In map tonen" is vóór het opslaan geblokkeerd – de
  tijdelijke plek is geen bestemming waar men iemand naartoe stuurt. Het
  toewijzingsbestand gaat bij het opslaan mee.

  In de instellingen onder „Programma" haalt „Resultaten meteen naast
  het origineel opslaan" het oude gedrag terug. Opdrachtregel,
  mapbewaking en klembordwachter slaan ongewijzigd meteen op – daar zit
  niemand die zou kunnen opslaan.

- **De werkbalk van de nabewerkingseditor is opgeruimd.** De leermodus
  staat nu aan het rechteruiteinde bij vergelijkingsvergrootglas en
  „Vervangen waarden" – de drie schakelaars die een werkwijze in- en
  uitschakelen, staan daarmee bij elkaar. „Op alle pagina's toepassen"
  is naar de drie zwartingsvormen verschoven, omdat het alleen daar iets
  doet. „Resultaat kopiëren", „Bestand – Terugzetten" en „Op alle
  pagina's toepassen" komen zonder opschrift toe; hun naam staat verder
  in de tooltip en het menu. Tussen „Vervangen" en „Origineel
  terughalen" staat een scheidingsstreep: de twee zijn tegengesteld en
  zagen er naast elkaar uit als twee varianten van hetzelfde werktuig.

- **Het symbool voor „Resultaat kopiëren" toont nu een document.** Twee
  bladen met omgevouwen hoek en tekstregels in plaats van twee gelijke
  bladen met een klein hoekpijltje. „Afbeelding kopiëren" draagt in
  ruil daarvoor het beeldteken, zodat beide zonder opschrift uit elkaar
  te houden zijn. De knop „Kopiëren" in de resultatenlijst toont
  hetzelfde documentsymbool – hij legt hetzelfde bestand op.

- **De instellingen zijn geordend en van koppen voorzien.** „Herkenning"
  heeft nu vier secties: *Wat wordt verwijderd*, *Hoe wordt vervangen*,
  *Hoe grondig wordt gezocht* en *Vóór en na de run*. Gezichtsherkenning
  en streep-/QR-codes staan bij de afbeeldingen, waar men ze zoekt;
  „Programma" is verdeeld in *Resultaatbestanden*, *Bij het opstarten*,
  *Actualisering*, *Weergave* en *Terugkoppeling aan ons*, en de
  naamtoevoeging van het resultaatbestand staat bij de
  resultaatbestanden in plaats van tussen taal en weergave.

- **De uitgebreide herkenning staat standaard ingeschakeld**, ook vóórdat
  haar taalmodel is geladen. Voorheen hing de standaard af van de
  modelvoorraad, en een vers ingerichte computer draaide blijvend op het
  zwakkere niveau. Het inrichtingsvenster biedt het model op de eerste
  pagina aan om te laden en noemt de prijs ernaast. Ontbreekt het, dan
  zegt het vinkje dat verder, in plaats van een niveau voor te wenden
  dat niet draait.

- **De twee begrippenlijsten heten nu wat ze doen:** „Altijd verwijderen"
  in plaats van „Eigen begrippen" en „Nooit verwijderen" in plaats van
  „Uitzonderingen".

- **Het voorbeeldvenster is overzichtelijker.** Vanaf negen waarden staan
  ze in twee kolommen, de regels zijn platter, en het aantal
  vindplaatsen staat direct achter het begrip in plaats van aan de
  rechterrand.

- **In de nabewerkingseditor staat Vervangen vóór Zwarten** – in de
  werkbalk, in het menu „Werktuigen" en bij rechtsklikken op de pagina.
  Vervangen is de regel: een plaatshouder is aan te klikken en terug te
  halen, een balk niet.

- **Minder dubbele knoppen in de editor.** „Opslaan als …" en „Afbeelding
  kopiëren" staan alleen nog in het menu Bestand, met hun gebruikelijke
  toetsencombinaties. In de balk blijft er telkens één: Opslaan en
  „Resultaat kopiëren" – waarheen wordt opgeslagen, staat toch al in de
  statusregel en is daar met een klik te wijzigen.

- **De klembordwachter wordt bij de eerste start niet meer aangeboden.**
  Hij grijpt in elke kopieerhandeling van het systeem in; wie het
  programma voor het eerst ziet, kan dat niet inschatten. In de
  instellingen staat hij verder, daar met de bijbehorende clausule
  ernaast.

- **De lichte weergave verblindt minder.** De vensterachtergrond kwam tot
  nu toe van de betreffende systeemstijl en was daarmee het enige grote
  vlak dat niemand had bepaald – onder Windows bijna wit. Nu is het een
  gebroken wit, op elk systeem gelijk.

- **De rondleiding en het handboek leggen de kleuren uit.** Wat rood,
  oranje, groen en geel achter een vervangen woord betekenen, staat nu
  als eigen station in de rondleiding en als alinea in het handboek –
  in alle taalversies.

### Opgelost

- **Handboek en FAQ toonden plaatshouders die niet meer bestaan.** Sinds
  de overstap naar de korte vorm schrijft Maskuro `[NAM1]`; in de hulp
  stond nog `[NAME1]`, en de zin „Standaard is `[NAME1]`" klopte
  daarmee gewoonweg niet. In de zeventien vertaalde versies stond
  bovendien de **Duitse** markering in plaats van de eigen – een
  Spaanse lezer zag `[NAME1]`, waar zijn programma `[NOMB1]` schrijft.
  Evenzo de extensie van het resultaatbestand: daar beloofden alle
  versies `_bereinigt`, terwijl het programma `_limpiado`, `_nettoyé`
  of `_除去済み` aanmaakt. Getroffen waren ook de nummerloze vorm (bij
  het anonimiseren heet alles `[NAM]`, niet `[NAME]`) en de uit de
  waarde afgeleide markering bij het hashen.

- **Het voorbeeldvenster onderbreekt nog maar één keer per document – en
  een tweede keer alleen als er echt iets nieuws bijkomt.** Een PDF
  wordt van twee kanten gelezen: eenmaal uit de inhoudsstroom en
  tenslotte van de gerenderde, zichtbare pagina. Tot nu toe vroeg elk
  van de twee voor zich. Nu geldt: wat u in het eerste venster hebt
  beslist, geldt verder, en waarden die daar al stonden, komen niet
  terug. Vindt de visuele controle van de voltooide pagina's daarentegen
  iets dat voorheen nergens stond, dan krijgt u dat nog een keer
  voorgelegd – alleen, zonder de al beslissen waarden.

- **Het voorbeeldvenster zegt nu waarnaar men moet beslissen.** In plaats
  van „Vinkje verwijderen = de waarde blijft staan" – wat het vinkje
  *doet*, maar niet wanneer men het moet weghalen – staat er nu: vinkje
  weg overal waar geen persoonsgegeven staat; daar heeft de herkenning
  zich vergist. Bovendien noemt elk venster de controlelus waaruit zijn
  waarden komen.

- **Plaatshouders zien er in het hele document hetzelfde uit.** Op
  pagina's die in de OCR-weg als beeldpagina's opnieuw worden opgebouwd,
  werden zichtbare plaatshouders tot nu toe in schrijfmachineschrift
  gezet – „[PLZ4]" stond dan breed en met schreefjes naast een smal
  „[NAM1]" van dezelfde pagina. Ze dragen nu hetzelfde schreefloze
  lettertype als overal elders en worden ook niet meer breder gezet dan
  bij het inpassen gepland was. De onzichtbare zoeklaag behoudt haar
  eigen lettertype – ze heeft betrouwbare afmetingen nodig, geen
  uiterlijk.

- **In de werkbalk van de editor staan geen dubbele scheidingsstrepen
  meer.** Waar een hele werktuiggroep vervalt voor het geopende
  bestandstype – in een PDF bijvoorbeeld paginaweergave en renderen –,
  bleven tot nu toe beide strepen rond het gat staan.

- **Bij het terughalen blijft niet meer af en toe alleen een witte plek
  over.** Een al exact herstelde originele tekst wordt niet meer door
  het brede, samengevoegde kader van zijn verwijderde plaatshouder wit
  overschilderd. Bij gemengde tekst- en beeldterughalingen wordt tekst
  bovendien alleen onzichtbaar ingevoegd als het pagina-beeld precies
  deze originele stand al zichtbaar draagt. Dat geldt voor kaders,
  trefpaneel en PDF-bijlagen.

- **„Origineel terughalen" biedt niet meer onnodig aan de pagina te
  rasteren.** De strenge resttekstcontrole blijft bij zwarten en
  vervangen actief. Bij terughalen wordt ze overgeslagen: daar komt
  originele inhoud bewust weer bij, en onveranderde buurwoorden in het
  uitgebreide terughaalkader waren geen opschoningsfout, maar een
  vals alarm.

- **De rondleiding door de editor legt „Vervangen" en „Origineel
  terughalen" nu als eigen stappen uit.** Beide werktuigen worden direct
  in de balk uitgelicht en beschrijven dat een getrokken kader een
  plaatshouder invoegt respectievelijk de oorspronkelijke inhoud van
  die plek uit het bronbestand terughaalt.

- **Ook landspecifieke plaatshouders blijven nu op hoogstens vier
  letters.** Deze soorten ontbraken tot nu toe in de centrale
  afkortingencatalogus en konden daardoor nog voluit verschijnen,
  bijvoorbeeld `[UMSATZSTEUER_ID1]`. Nieuwe runs schrijven daarvoor
  `[UID1]`; alle automatisch herkende Duitse en Engelse soorten blijven
  daarbij eenduidig. Zelf berekende afkortingen van andere
  interfacetalen groeien bij naamgelijkheid niet meer boven vier tekens
  uit. Eigen regelbeschrijvingen blijven ongewijzigd zo benoemd als ze
  zijn ingevoerd.

- **Vervangen gebruikt nu de hele werkelijk vrije regelruimte, voordat
  het zwart maakt.** De bestaande starre grens bij het drievoudige van
  de oorspronkelijke woordbreedte creëerde zelfs in grotendeels lege
  formuliervelden balken. Ook treffers van de zichtbare OCR-tegenblik
  krijgen bij bezette PDF-tekst nu een leesbare plaatshouder; zwart
  blijven pure beeld-, annotatie- en vectorinhoud, de gekozen
  zwartingsmodus evenals echte krappe plekken waar zelfs een eenduidige
  korte vorm niet in past.

- **Een al zichtbare plaatshouder wordt bij het veiligheidsrasteren niet
  meer een tweede keer rood overschreven.** Het rasteren neemt de
  bestaande vervanging nu over uit het pagina-beeld en legt alleen een
  onzichtbare zoekkopie aan. Moet een veiligheidsbalk precies deze plek
  overschilderen, dan wordt het hele werkelijke plaatshouderkader
  vernieuwd in plaats van alleen zijn kortere oorspronkelijke anker.

- **„Origineel terughalen" markeert nog maar zekere doelen in het
  getrokken kader.** Alle vervangen begrippen erin lichten afzonderlijk
  en exact op; onveranderde lopende tekst blijft onaangetast. Echte
  vectoriële zwartbalken worden eveneens afzonderlijk gemarkeerd, als
  onder hun zwarte PDF-vlak originele tekst ligt. Bij gerasterde
  pagina's ziet het voorbeeld bewust af van een vermeend balkvlak: de
  eerdere beeldpuntzoektocht verbond daar letters, onderstrepingen en
  tabellijnen tot grote rode vlakken op verkeerde plekken. Het
  herstellen zelf blijft daarvan onaangetast.

- **Bij het herstellen op gerasterde pagina's komt de tekst weer
  terug.** Recent bleef daar een lege plek met gekleurde rechthoeken
  erboven staan. De teruggehaalde tekst stond in het document, maar
  werd door de witte grond van een plaatshouder overschilderd die
  verderop in de pagina-opbouw wordt getekend.

- **De controlekleuren liggen niet meer meermaals over elkaar.** Dezelfde
  plek werd per item van de toewijzing ingekleurd – op een pagina vijf
  echte vindplaatsen, elk vijf keer overschilderd, totdat van de bleke
  markering een verzadigd blok werd. En ze verschijnen niet meer op
  woorden die helemaal niet werden vervangen: staat de originele waarde
  nog op de pagina, dan is daar ook geen markering meer.

## 0.10.40-beta.1 – 24 augustus 2026

### Opgelost

- **Zwartbalken in de editor hebben nu een veiligheidsrand.** Woord-,
  regel- en vrije kaders dekken ook overhangende glyphen en gladgestreken
  randpixels af; een rendercontrole zorgt bovendien ervoor dat noch
  zichtbare resten noch uitleesbare originele tekst blijven staan.

- **Vervangteksten blijven leesbaar en uniform kort.** Nieuwe namen,
  adressen en vrije begrippen verschijnen bijvoorbeeld als `[NAM1]`,
  `[ADR2]` en `[BEG3]`. De vaste ondergrens bedraagt 4,5 punt; bij
  plaatsgebrek wordt eerst ingekort en de bruikbare loopruimte
  uitgebreid. Oude toewijzingen met lange plaatshouders blijven
  leesbaar en terug te halen.

- **Meerwoordige vervangingen vanuit het trefpaneel zijn beveiligd tegen
  dubbele markeringen en originele resten.** De regressie bestaat met
  en zonder genummerde plaatshouders; per vindplaats blijft precies één
  gemeenschappelijke toewijzing behouden.

- **Teruggehaalde klembordinhoud wordt op macOS niet meteen opnieuw
  opgeschoond.** Ook als de systeemhandtekening pas vertraagd wisselt na
  het schrijven, herkent Maskuro de eigen inhoud betrouwbaar.

### Nieuw

- **De editor kan een bestand volledig terugzetten naar de vers
  opgeschoonde uitgangsversie.** „Bestand – Terugzetten" verwerpt na een
  bevestiging alle nabewerkingen van het huidige tabblad, inclusief
  vervangingslijst en tellers. De opdracht is zonder wijzigingen
  geblokkeerd en laat zich op zijn beurt met „Ongedaan maken" weer
  terugnemen.

- **Verschoven datumaanduidingen behouden hun chronologie nu betrouwbaar
  over meerdere bestanden.** De gemeenschappelijke verschuiving wordt al
  bij het inschakelen van de strategie blijvend in de regels verankerd;
  bovendien kan de verschuiving niet meer nul dagen bedragen en
  daarmee ongemerkt de echte datum laten staan.

- **Het handmatige PDF-werk dekt nu het volledige professionele
  zwartingsproces af.** Losse begrippen, lijsten en reguliere patronen
  zijn in de geopende PDF of over alle PDF's van een map te zoeken en
  veilig te zwarten; hele pagina's en paginabereiken zijn direct te
  kiezen. Kleur, neutraal wit vlak, overlaytekst, lettertype,
  uitlijning en herhaling hebben een voorbeeld, herbruikbare codes zijn
  te beheren en te im- en exporteren. De PDF-opschoning verwijdert
  naar keuze alle verborgen inhoud door volledige heropbouw of
  geselecteerde gegevensklassen. De veiligste keuze wordt duidelijk
  aanbevolen, ongeldige zoekpatronen worden uitgelegd en maprun's
  schrijven uitsluitend resultaatkopieën.

- **De vrijwillige gebruiksstatistiek toont nu installaties en
  versiewisselingen.** Maskuro genereert daarvoor een willekeurige,
  lokaal opgeslagen installatiekenning. Ze bevat geen apparaat-,
  gebruikers- of licentiegegevens; de server slaat alleen haar
  SHA-256-waarde op. De statistiek blijft in de instellingen volledig
  uit te schakelen.

- **De rondleiding is nu een begeleide oefening door beide vensters.**
  Ze legt het verzonnen oefendocument zelf in de lijst, legt de weg tot
  het opschonen uit en zet zich na de run automatisch in de editor
  voort. Wie de rondleiding afbreekt, beëindigt ook dit vervolg.

- **Bedrijven uit vijftien verdere rechtsgebieden worden herkend.** Wie
  documenten uit de Baltische staten, België, Scandinavië, Tsjechië,
  Polen, Zuidoost-Europa, Singapore, Brazilië of Mexico opschoont,
  verliest bedrijfsnamen niet meer omdat hun rechtsvorm onbekend was –
  nieuw daarbij zijn onder andere OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k.,
  EIRELI, z.s., o.p.s., S.K.A., Pte. Ltd. evenals S.A. de C.V. en S. de
  R.L.

### Gewijzigd

- **De werkbalken van de editor gebruiken hun ruimte nu gerichter.**
  Eenduidige standaardsymbolen en direct herkenbare werktuigvormen
  staan zonder herhalende tekst in de balk; meerduidige handelingen
  behouden hun naam. Onder „Weergave" kan „Werktuigopschriften tonen"
  worden uitgeschakeld om beide balken volledig tot symbolen te
  reduceren. Tooltips en menu's blijven daarbij volledig beschreven, de
  keuze wordt onthouden.

- **De leermodus is nu blijvend zichtbaar in de werkbalk.** Hij is daar
  direct in en uit te schakelen, ook als het vak van de vervangen
  waarden gesloten is. Werkbalk, menu Werktuigen en het bestaande
  vinkje in het vak tonen steeds dezelfde status.

- **„Terugzetten" bij het vergelijkingsvergrootglas zet alleen nog zijn
  zoom terug.** De knop herstelt de standaard van 125 procent, zonder
  het vergrootglas aan te dokken, te verschuiven of zijn venstergrootte
  te wijzigen. Voor de hele opbouw blijft „Weergave terugzetten"
  verantwoordelijk.

- **Fouten en wensen zijn nu ook via de hulpknop te melden.** „Fout
  melden …" en „Wens uiten …" staan daar nu net als in het klassieke
  Help-menu; beide wegen openen de al bestaande veilige foutmelding
  respectievelijk de openbare wensenlijst.

- **Het taakbalkmenu is korter en duidelijker geordend.** De twee
  opdrachten met globale toetsencombinatie – klembordopschoning en
  schermafbeelding – staan nu direct onder elkaar met een
  gemeenschappelijke rechter afkortingskolom. „Laatste originele
  inhoud herstellen" vervalt daar; de begrijpelijkere
  herstellen-knop blijft in het hoofdvenster beschikbaar.

- **Juridische pagina's zijn direct bereikbaar onder „Help → Juridisch".**
  Het submenu leidt naar licentievoorwaarden, privacyverklaring,
  colofon en algemene voorwaarden op maskuro.com. Aanwijzingen over
  herroeping blijven bij de aankoop op de website.

- **Handmatig gezwarte PDF's worden bij het opslaan volledig opnieuw
  opgebouwd.** Zichtbaar blijven de pagina's en hun opnieuw gelezen
  zoeklaag; metagegevens, bestandsbijlagen, bladwijzers, opmerkingen,
  formulierwaarden, verborgen lagen, zoekindexen, scripts,
  bijgesneden inhoud en in andere objecten verborgen inhoud worden niet
  in het uitvoerbestand overgenomen. Lettertype en vectorafbeelding
  bestaan daarna uit beeldpunten – dat is de prijs van de bewijsbare
  grens tot de vreemde PDF-objectboom.

- **Ctrl+Shift+B maakt nu op alle systemen standaard een
  schermafbeelding met Maskuro.** De Print Screen-toets en combinaties
  daarmee blijven als eigen toewijzing mogelijk. In het menu van het
  taakbalksymbool staan de globale toetsencombinaties nu rechts naast de
  bijbehorende opdrachten. Eigen opgeslagen toewijzingen blijven
  behouden.

- **De editor start met pagina's en vergelijkingsvergrootglas links.**
  Het paginavak staat boven, het geopende origineel-vergrootglas direct
  eronder; de vervangen waarden blijven rechts. Een bewust opgeslagen
  eigen indeling heeft verder voorrang.

- **Het oefendocument staat niet meer blijvend in het hoofdvenster.**
  Het maakt deel uit van de begeleide oefening en blijft bovendien
  bereikbaar onder „Help".

- **De eerste start leidt direct naar de praktijkoefening.** De
  geïllustreerde snelstartgids wordt niet meer als tweede, inhoudelijk
  dubbele instapweg aangeboden; ze blijft altijd bereikbaar onder „Help
  → Snelstartgids".

- **Het rustende taakbalksymbool blijft in volle kleur.** Het toont nu
  hetzelfde krachtige Maskuro-schild als de actieve klembordmodus;
  alleen bij actieve bewaking komt het groene lichtpunt erbij.

- **Het oefendocument blijft in Maskuro.** De instapknop genereert de
  verzonnen PDF en voegt hem direct in de bestandslijst in, maar start
  geen extra PDF-viewer meer op.

- **Het zoeken in het nabewerkingsvenster blijft vloeiend tijdens het
  typen.** De ruimte voor de treffenteller wordt al bij het openen
  gereserveerd; zijn eerste tekst verandert het canvas niet meer en
  veroorzaakt geen nieuwe PDF-rasterrun.

- **Fabrikantnamen in fabricaataanduidingen blijven zichtbaar.** Een
  vermelding zoals „Fabricaat: TRILUX of gelijkwaardig" beschrijft het
  benodigde artikel en wordt niet meer alleen vanwege deze beschrijving
  als bedrijf gezwart. Leveranciers-, bedrijfs- en fabrikantvelden
  blijven daarvan onaangetast.

- **Corpusmetingen tellen te ver gezwarte treffers als valse alarmen.**
  Wanneer Maskuro de verwachte naam verwijdert, maar daarbij een deel
  van de zin meeneemt, stijgt nu het aantal valse alarmen. Het rapport
  wijst overschrijdingen bovendien apart aan; eerdere aantallen valse
  alarmen zijn daarom niet direct vergelijkbaar.

### Opgelost

- **Technische en officiële begrippen uit Duitse originele documenten
  worden minder vaak als namen of plaatsen gezwart.** Voertuiguitrusting,
  positie- en somregels, aanbestedings- en privacybegrippen,
  wetsverwijzingen evenals bestandsnamen van openbaar materiaal worden
  alleen met hun bezette zakelijke context afgeremd. Een bij de
  tekstherkenning verloren umlaut in „Marz 2026" blijft als maand
  beschermd; „Marz" zonder datumverband kan verder een echte naam of
  plaats zijn.

- **„Origineel terughalen" neemt meteen de volledige benodigde breedte.**
  Treft het kader maar één woord van een toegewezen waarde, dan breidt
  Maskuro het aan de hand van de toewijzing en de originele regel
  zelfstandig uit tot het hele gegeven – bijvoorbeeld van „Planungs" naar
  „Nordlicht Planungs GmbH". Het aansluitend grijpbare kader toont
  eveneens de daadwerkelijk teruggehaalde totale breedte.

- **„Origineel terughalen" toont zwarte balken nu als eenduidig doel.**
  Bij het overgaan of slepen licht de hele herkende balk rood op met
  een lichte contrastcontour, in plaats van alleen een nauwelijks toe te
  wijzen tekstkader ernaast. Dat geldt ook voor gerasterde pagina's,
  waarop de balk alleen nog uit beeldpunten bestaat.

- **De editor-rondleiding laat geen stations meer weg wanneer vakken
  gesloten waren.** Voor de begeleiding opent en ordent Maskuro
  paginavak, vergelijkingsvergrootglas en vervangen waarden tijdelijk
  zelf. Na „Klaar" of een afbreking keert de persoonlijke indeling
  terug. Is een werktuig bij een documentsoort principieel niet
  beschikbaar, dan blijft zijn uitleg als teksthalte behouden, in
  plaats van ongemerkt te verdwijnen.

- **„Vervangen" blijft ook bij de PDF-veiligheidsterugval zichtbaar.**
  Moest Maskuro een pagina wegens een resterend teken of een
  beschadigde tekstloop als afbeelding opnieuw opbouwen, dan stonden de
  juiste vervangingen alleen nog onzichtbaar in de zoeklaag en op de
  pagina lagen zwarte balken. De daadwerkelijk gezette vervangwaarden
  blijven nu over alle raster- en OCR-heropbouwen heen zichtbaar rood
  en doorzoekbaar behouden.

- **De aanwijzingen boven de opgeschoonde versie blijven in de donkere
  weergave leesbaar.** Versiekop, bedieningsregel en inleiding nemen
  hun lettertypekleur nu direct over van het daadwerkelijk weergegeven
  Qt-venster.

- **Zwartkaders staan op gerasterde PDF-pagina's weer boven de tekst.**
  De onzichtbare woordkaders waren afhankelijk van het originele
  lettertype smaller dan de zichtbare letters. Daardoor ontstonden
  gaten in de balk of bleef de laatste letter leesbaar. De kaders
  behouden nu breedte, hoogte en looprichting van het zichtbare woord.

- **„Wat is nieuw" begint weer helemaal bovenaan.** De changelog-dialoog
  zet na de voltooide vensteropbouw tekstcursor en schuifbalk
  uitdrukkelijk op het begin, in plaats van afhankelijk van de Qt-stand
  midden in de nieuwigheden te starten.

- **Sluiten tijdens de scan-woordherkenning blijft stil.** Een net
  voltooid rakende OCR-achtergrondrun stuurt niet meer naar een al
  gesloten nabewerkingsvenster.

- **Relatieve tijdsaanduidingen worden niet meer voor namen gehouden.**
  Vaste uitdrukkingen zoals „vandaag", „gisteren", „morgen" en
  „volgende week" kent Maskuro nu uit de officiële kalendergegevens van
  de betreffende documenttaal.

- **Afsluiten tijdens het eerste modelladen ruimt netjes op.** Wie
  Maskuro of het nabewerkingsvenster meteen na het openen sluit, laat
  geen thread achter die nog in de systeemeigen taalherkenning werkt
  bij het afbreken van het proces. Dat voorkomt het sporadische
  crashrapport bij het afsluiten; een al lopend laadproces wordt
  ordelijk afgerond.

- **Vertraagde startdialogen verschijnen niet meer na het afsluiten.**
  Wie het hoofdvenster kort na de start sluit, krijgt daarna niet
  alsnog onzichtbaar of vertraagd de vraag naar de beste herkenning,
  nieuwigheden of introductie getoond.

- **HTML en e-mail behouden hun regeleinden.** Op Windows mengde de
  HTML-serialisatie na opschoning en terughaling LF en CRLF. Inhoud en
  opmaak klopten, het bestand echter niet meer byte-voor-byte. HTML-
  bestanden en MIME-berichten nemen nu weer de schrijfwijze van hun
  bron over.

- **Bedrijfsnamen met een voorzetsel blijven volledig.** Achter een
  voorzetsel sneed Maskuro namen zoals „Gesellschaft für Systemtechnik
  mbH" of „Bank für Arbeit und Wirtschaft AG" af bij het woord „für".
  De hele bedrijfsnaam wordt nu herkend; echte zinsintroducties zoals
  „Wij zijn verzekerd bij Alpha GmbH" blijven zichtbaar.

- **Chinese bedrijfsnamen blijven vóór hun rechtsvorm volledig.** Een
  als werkwoord op te vatten merkonderdeel kon ondanks de eenduidige
  toevoeging „有限公司" de hele naam verwerpen. In schriften zonder
  hoofdletters heeft de officiële rechtsvormanker nu voorrang op deze
  onzekere woordsoortgrens.

- **PDF-pagina's werden zonder noodzaak afbeeldingen.** Bij meerpagina's
  tellende PDF's waarvan de pagina's een lettertypelijst delen – wat
  gangbare makers zo aanleggen –, verloren na de eerste pagina alle
  volgende de verwijzing naar hun lettertypen. Het gevolg was dubbel:
  umlauten waren in het resultaat niet meer doorzoekbaar
  („Auftragsbestätigung" was niet te vinden), en de nacontrole hield
  daarop letters voor gemist die nooit op de pagina stonden – ze
  rasterde intacte tekstpagina's naar afbeeldingen, daarmee niet meer
  doorzoekbaar, niet kopieerbaar en aanzienlijk groter. In het
  controlebestand trof dat vier van de zeventien pagina's.
- **Een komma alleen veroorzaakt geen rasterisatie meer.** Eindigt een
  vondstgebied bij het woord, dan hoort het leesteken ernaast net nog
  erbij. Een komma of een punt is echter geen over het hoofd gezien
  gegeven, en het rasteren kost de hele pagina. Letters en cijfers
  blijven ongewijzigd een reden om aan te scherpen.

## 0.10.38-alpha.20260824 – 24 augustus 2026

### Nieuw

- **Bedrijfsnamen zonder rechtsvorm worden nu herkend wanneer hun
  beschrijving ze noemt.** „Leverancier: Kranzbichler Handels GmbH" werd
  altijd al verwijderd – de rechtsvorm verraadt het bedrijf.
  „Leverancier: Dehner Märkte" bleef staan, en in offertes,
  aanbestedingen en bestellingen staat de leverancier meestal precies
  zo vermeld. Hetzelfde geldt voor „Bedrijf:", „Fabrikant:",
  „Fabricaat:", „Werkgever:" en hun equivalenten in acht andere talen,
  en ook wanneer de beschrijving alleen op haar regel staat en de naam
  eronder.

  Wat achter de beschrijving *geen* bedrijf is, blijft onaangetast:
  „Leverancier: zie bijlage" wordt niet gezwart – anders stond er
  „Leverancier: [ORGA1]", en dat beweerde een naam die er nooit was.
  Beschrijvingen waarachter net zo vaak een mens staat („Klant:",
  „Opdrachtgever:"), zijn bewust niet meegenomen.

- **Een ingevoegde afbeelding is nu ook te bewerken.** In het venster
  „Afbeelding opschonen" staat naast „Resultaat kopiëren" een knop *In
  editor bewerken*: de afbeelding wordt opgeschoond en daarna geopend om
  na te zwarten, te beschrijven en te markeren – dezelfde weg die een
  schermafbeelding gaat.

- **Nummers achter hun beschrijving worden ook gevonden wanneer ze een
  zakenpartner benoemen.** Tot nu toe vielen klant-, contract- en
  personeelsnummers; nu ook debiteuren-, crediteuren- en
  leveranciersnummer, het Oostenrijkse werkgeversnummer, de
  ANKÖ-registratie en het WEEE-, EAR- en EPR-nummer van een fabrikant –
  in het Duits zoals in het Engels. Bovendien begrijpt Maskuro nu de
  schrijfwijze van gezette offertekoppen met spatie vóór de dubbele punt
  („Klant-nr : K903944"). Artikel-, bestel-, order-, offerte- en
  factuurnummers blijven verder onaangetast: ze benoemen het proces of
  de waar, niet de mens. Wie ze toch wil verwijderen, legt ze vast als
  eigen zoekpatroon.

- **U ziet nu hoelang een bestand nodig had.** Bij de voltooide regel
  staat de duur naast de herkende taal („gereed · Duits · 2,4 s"), in
  de samenvatting die van de hele run, in het kengetallenpaneel de som
  – en in het controlerapport staat ze als eigen veld. Bij meerdere
  bestanden verraadt de regel welke ervan de tijd heeft gekost.

- **Schriften die de systeem-OCR niet ondersteunt, kunnen met aanwezig
  taalbestand vervangend worden gelezen.** Tot nu toe gold: beheerst de
  systeemeigen tekstherkenning een schrift niet (op de Mac
  bijvoorbeeld Devanagari), dan stond in het resultaat
  „Afbeelding(en) zijn NIET gecontroleerd", en de gegevens in de
  afbeelding bleven staan. Nu springt de meegeleverde tekstherkenning
  bij, als het passende taalbestand aanwezig is. Omdat een zo gelezen
  afbeelding onzekerder is dan een regulier gecontroleerde, staat dat
  in het resultaat: „met de vervangmethode gelezen – gelieve te
  bekijken". Gemeten aan een historische tussenstand van de
  Hindi-proef: **tien gegevens meer gevonden en vier valse alarmen
  minder** (64 % → 73 %). De huidige eindwaarde staat verderop en is
  daarmee niet te verwarren.

- **De tekstherkenning vraagt naar de juiste taal.** Voor alle
  documenttalen behalve Duits en Engels werd tot nu toe het Engelse
  herkenningsmodel gebruikt, ook als het passende taalbestand
  aanwezig was. Onder Windows betrof dat elke taal – Grieks, Japans of
  Hindi werden daar met het Engelse model gelezen.

- **Een inrichtingsassistent bij de allereerste start.** (Wie Maskuro al
  gebruikt heeft, krijgt hem niet – „eerste start" betekent eerste
  start, niet eerste start na deze actualisering.) Drie vragen in plaats
  van zes afbeeldingen: de taal van uw documenten, of tekst in
  afbeeldingen wordt meegelezen, en hoe u Maskuro dagelijks wilt
  bereiken. Aan het einde blijven de drie wegen staan – oefendocument,
  rondleiding of de geïllustreerde snelstartgids. Alles is over te
  slaan, en „Help → Inrichting opnieuw doorlopen" haalt hem terug.

- **F1 slaat het handboek op bij het passende hoofdstuk.** In het
  hoofdvenster, in de instellingen (daar per pagina), in het
  doorzichtvenster en in het taalbeheer; in het nabewerkingsvenster via
  Shift+F1, omdat F1 daar van oudsher de toetsencombinaties toont. Tot
  nu toe begon de hulp altijd bovenaan, bij 25 hoofdstukken.

- **Nieuw eerste handboekhoofdstuk: „In drie minuten aan de slag".** Vier
  stappen, meer is er niet nodig voor een document – in alle 18
  taalversies.

- **Een rondleiding door het venster.** „Help → Rondleiding door het
  venster" legt een schijnwerper op het ene bedieningselement na het
  andere en schrijft er een zin naast – in het hoofdvenster acht
  stations, in het nabewerkingsvenster zeven. Anders dan de
  geïllustreerde snelstartgids legt hij het venster uit waar u nu
  voor zit. Afbreken op elk moment met Esc.

- **Een oefendocument om zonder risico te proberen.** Onder het
  invoervlak staat nu „Oefendocument openen" (ook in het Help-menu). Het
  maakt een verzonnen blad aan – naam, adres, telefoonnummer, IBAN,
  sociaal-zekerheidsnummer – en op het blad staat tegelijk wat u ermee
  kunt doen en wat u daarna zult zien. Geen woord daarvan hoort bij een
  echt mens; het eerste document dat u door Maskuro stuurt, hoeft dus
  geen echt document te zijn.

- **„Alleen nakijken …" staat nu naast „Opschonen".** Het toont waar
  persoonsgegevens liggen – bestand, soort en aantal – zonder iets te
  wijzigen of te schrijven. Wie een document heeft neergelegd, kijkt
  daarmee eerst na voordat hij opschoont. Tot nu toe zat deze weg alleen
  in het menu Bestand onder „Map doorzien …" en ging hij over een hele
  map in plaats van over de neergelegde bestanden.

- **Als er niets werd gevonden, staat er nu bij wat de oorzaak kan
  zijn.** Bijvoorbeeld: in het bestand staan afbeeldingen, maar „Ook
  tekst in afbeeldingen controleren" staat uit. Of: de ingestelde taal
  past niet bij die in het document. En als niets van dat alles het
  geval is, zegt Maskuro ook dat.

- **Het nabewerkingsvenster begroet u de eerste keer met drie zinnen:**
  aanklikken zwart een woord, slepen een gebied, rechts staan de
  vervangen waarden. „Begrepen" haalt de aanwijzing blijvend weg;
  „Help → Introductie opnieuw tonen" haalt hem terug.

- **Woorden aanklikken nu ook op gescande pagina's.** Tot nu toe waren
  woorden alleen aan te klikken waar de PDF een tekstlaag meebracht –
  bij een scan ging het niet, en in hetzelfde document kon het van
  pagina tot pagina wisselen. Zulke pagina's worden nu eenmalig door de
  tekstherkenning gelezen; daarna klikt men woorden aan zoals overal
  elders. De statusregel zegt wat er op dat moment gebeurt.

- **Het paginavak is weer een vlak.** Het hield midden in zijn kolom op:
  titelbalk afgesneden, ernaast een strook in een andere kleur, en de
  huidige pagina was alleen aan een gekleurd kader achter haar nummer te
  herkennen. Nu vult het zijn kolom, is breder te trekken, en de huidige
  pagina wordt als hele tegel uitgelicht – met ongeveer een onvervalst
  paginavoorbeeld erin.

- **Vervangen plekken lichten bleekgeel op.** In de paginaweergave is
  daarmee in één oogopslag te zien waar iets werd vervangen – dezelfde
  kleur die het vergelijkingsvergrootglas boven het origineel gebruikt.
  Het rode kader bij het wijzen met de muis blijft ongewijzigd.

- **„Weergave terugzetten" in het nabewerkingsvenster** (menu
  „Weergave"). Wie paginavak of treflijst heeft verschoven, losgemaakt
  of gesloten, zet daarmee alles weer terug naar waar het bij de eerste
  start stond.

### Gewijzigd

- **De plaatshouders zijn korter.** Van `[SOZIALVERSICHERUNGSNR_1]` wordt
  `[SVNR1]`, van `[ORGANISATION_1]` een `[ORGA1]`, van `[EMAIL_1]` een
  `[MAIL1]`. De reden is geen schoonheid: een plaatshouder die langer is
  dan de waarde die hij vervangt, drukt de regel uiteen en vindt in een
  smalle tabelkolom helemaal geen plaats meer – daar bleef tot nu toe
  een zwarte balk staan, en die zegt niemand meer dat er op die plek
  iets stond. Waar een gebruikelijke afkorting bestaat, staat die er
  (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`). Resultaten uit eerdere runs blijven
  bruikbaar: de oude schrijfwijze wordt verder herkend, en
  toewijzingsbestanden van gisteren werken ongewijzigd.

- **Het programmasymbool staat nu overal hetzelfde.** In de menubalk van
  de Mac verscheen tot nu toe een eenkleurig schild dat het systeem zelf
  zwart of wit kleurde, in de Windows-taakbalk een groen resp. grijs.
  Nu draagt elke balk hetzelfde blauwe Maskuro-schild. Waaraan te zien
  is of het klembord bewaakt wordt, blijft even duidelijk: loopt de
  bewaking, dan zit een groen punt bij het schild; rust ze, dan staat
  hetzelfde schild bleek erbij. Ook op de kleinste groottes staan nu
  beide zwartingsbalken in het schild – tot nu toe toonde de taakbalk
  daar er maar één.

- **Gezichten worden herkend met een model waarvan de trainingsafbeeldingen
  met toestemming zijn ontstaan.** Uitgeleverd wordt nu MediaPipe
  BlazeFace (Apache-2.0); de bestaande detector blijft ingebouwd en
  omschakelbaar, maar wordt niet meer meegeleverd, omdat zijn
  trainingsherkomst niet afdoende is opgehelderd. Voor de herkenning
  verandert er niets: op 324 portretten en 143 afbeeldingen zonder
  gezicht vindt de nieuwe versie evenveel bij evenveel misgrepen en
  heeft daarvoor een derde van de tijd nodig.

- **OCR is het veiligheidsanker voor de sterkste PDF-garantie.** De
  normale PDF-run gebruikt haar en genereert de volledige
  minimaalopbouw. Wie OCR uitdrukkelijk uitschakelt, krijgt de
  compatibelere objectweg; interface, afsluitmelding en handboek zeggen
  nu uitdrukkelijk dat deze weg niet dezelfde architectuur biedt tegen
  onbekende verborgen PDF-kanalen.

- **De verkoopgrendel blokkeert nu ook het tot nu toe bijgevoegde
  YuNet-model.** De MIT-licentie van het exacte gewicht blijft
  gedocumenteerd, maar volstaat voor de openbaar zichtbare
  trainingsgegevensketen via WIDER FACE niet als conservatieve
  productvrijgave. Vóór verkoop is een schriftelijke opheldering of de
  vervanging door een model met een aantoonbare commerciële
  gegevens- en gewichtsketen vereist.

- **Bedrijfs- en organisatienamen worden nu vanzelf verwijderd.** Tot nu
  toe bleven ze staan, zolang men er niet uitdrukkelijk om vroeg. Dat
  was voor een zakelijke brief de verkeerde standaard: wie een offerte
  doorgeeft, wil de opdrachtgever er niet in lezen. „Kranzbichler
  Handels GmbH", „Institut für Bauphysik" en soortgelijke worden daarom
  behandeld als een naam. Wie het anders nodig heeft, schakelt het in
  het venster uit; op de opdrachtregel heet de schakelaar nu
  `--ohne-organisationen`. De oude `--mit-organisationen` wordt verder
  geaccepteerd en doet niets meer, zodat bestaande scripts en
  snelkoppelingen niet breken. Datum- en geldaanduidingen blijven
  ongewijzigd uitgezonderd.

- **Zwarten heeft nu drie vormen in plaats van twee vinkjes.** „Woorden",
  „Hele regel" en „Vrij kader" staan als één keuze naast elkaar – er
  geldt altijd precies één. Tot nu toe waren „Tekstregels" en „Hele
  regel" twee onafhankelijke schakelaars die allebei ingedrukt konden
  zijn, en het vrije kader was helemaal geen knop, maar de
  uitgeschakelde stand van de eerste. De drie staan zichtbaar bij hun
  werktuig en zijn grijs zolang een ander werktuig gekozen is.

### Verbeterd

- **Het eerste document is ongeveer een seconde sneller klaar.** Voordat
  de opschoning begint, stelt Maskuro de taal van het document vast –
  en haalde daarvoor tot nu toe de woordenlijsten van alle 48 talen op
  een manier die veel meer laadde dan de woorden. Dat was ongeveer de
  helft van de wachttijd tot het eerste resultaat. De herkenning zelf
  is ongewijzigd: ze ziet dezelfde woorden als voorheen, alleen sneller.
  Elk volgend document was daar sowieso niet door getroffen.

- **Documenten met zeer lange alinea's worden sneller gecontroleerd.**
  Bij een alinea zonder regelafbreking las Maskuro haar voor elke
  gevonden plek opnieuw helemaal door; nu volstaat één keer. Hoe langer
  de alinea, hoe groter het verschil – gemeten ongeveer een zevende
  minder rekentijd. Aan het resultaat verandert niets.

### Opgelost

- **Met een bedrijf verdween vaak de halve zin mee.** Stond een
  bedrijfsnaam in de lopende tekst – „Informatie over de Gottwald GmbH &
  Co KG", „… (AV) van de Modelbedrijven GmbH" –, dan werd niet alleen
  de naam gezwart, maar alles daarvoor tot het begin van de zin. De
  tekst werd daardoor onleesbaar, en het zag eruit alsof lukraak werd
  gezwart. Bedrijfsnamen die zelf een „voor" of „en" dragen („Bank für
  Arbeit und Wirtschaft AG"), blijven daarbij ongewijzigd volledig.

- **Bedrijfsnamen bleven in briefkoppen staan, hoewel ze in de tekst
  werden verwijderd.** In een offerte stond de bedrijfszetel in de
  briefkopafbeelding nog leesbaar – dezelfde plaats die Maskuro in de
  lopende tekst had gezwart; in de doorzoekbare tekst van het resultaat
  stond ze zelfs onzichtbaar verder in. Wat eenmaal werd verwijderd,
  wordt nu ook verwijderd waar het alleen als afbeelding voorkomt. Dat
  werkt ook bij logo's en woordmerken die als afbeelding getekend zijn.

- **macOS vroeg bij elke start naar de schermopname**, ook wanneer de
  toestemming allang was verleend. De aanwijzing bij de start
  probeerde een opname uit, en juist dat haalt de systeemdialoog op het
  scherm. Nu vraagt bij de start alleen Maskuro zelf, en maar één keer;
  het systeem vraagt pas als u echt een schermafbeelding maakt.

- **Technische zaakbegrippen werden voor plaatsen en bedrijven
  gehouden.** „Invoedpunt", „plat dak", „verdeelinstallatie",
  „meldersokkel" en tientallen vergelijkbare woorden verdwenen uit
  offertes en bestekken. Maskuro herkent ze nu aan hun grondwoord: wat
  eindigt op „-installatie", „-punt" of „-kanaal" is een zaak.
  Plaatsnamen zoals Berlijn, Melk of Wieselburg hebben zo'n grondwoord
  niet en blijven onaangetast – evenals adressen zoals „Der Graben" of
  „Alter Markt".

- **Japanse, Koreaanse, Chinese, Thaise en Gujarati-documenten konden het
  programma laten crashen.** Bevatte een document in een van deze vijf
  talen een internetadres zonder „https://" ervoor, dan brak de
  opschoning met een interne fout af – bij een geopend venster ging
  daarbij ook het overige werk verloren. Alle achtenveertig te kiezen
  documenttalen lopen nu door; ontbreekt voor een taal het
  frequentiewoordenboek, dan blijft het gegeven in twijfelgeval staan in
  plaats van te verdwijnen.

- **Veldbeschrijvingen beschermden alleen in het Duits en Engels.**
  „Reference" bleef staan, het Italiaanse „Riferimento" en het
  Portugese „Referência" werden als plaatsaanduiding verwijderd –
  dezelfde veldnaam, dezelfde regel, ander resultaat. Wie niet in het
  Engels werkte, was daarmee slechter af. Maskuro kent nu in alle elf
  bijgehouden talen dezelfde veldnamen.

- **„Origineel terughalen" haalde op gescande pagina's te veel terug.**
  Een kader over een gezwarte regel van een adresblok legde het
  **hele blok** weer open – en de pagina bleef verscheurd achter:
  balkresten stonden er nog, waaruit losse woordeindes staken. Reden
  was dat onder elkaar liggende balken op een gerasterde pagina elkaar
  raken en daarom als één enkel vlak golden. Teruggehaald wordt nu
  precies de regel waarnaar het kader wijst; de naburige regels blijven
  gezwart, en de balk van de getroffen regel verdwijnt helemaal.

- **Hoeveelheidsaanduidingen in positielijsten werden voor adressen
  gehouden.** In een regel zoals „1.4  Kabelgoot  100,00  m" werd
  „Kabelgoot 100" als straat met huisnummer vervangen. Zulke regels
  blijven nu staan; echte adressen – ook „Hauptplatz 1, 3250
  Wieselburg" – worden ongewijzigd herkend.

- **Vóór een bedrijfsnaam verdween de halve zin.** Van „Overeenkomst
  tussen de firma Gottwald GmbH & Co KG en de opdrachtgever." werd
  „[ORGANISATION_1] en de opdrachtgever." – het begin van de zin was
  weg, en daarmee de aanwijzing waar het over gaat. Nu vervalt alleen
  de bedrijfsnaam zelf. Waar het soortwoord bij de naam hoort
  („Deutsche Bank AG", „Universität Wien"), blijft alles zoals het was.

- **In een verslag bleven sprekers staan wier naam tegelijk een beroep
  is.** „Bauer:", „Koch:", „Weber:" vóór een woordmelding werden over
  het hoofd gezien, „Gruber:" ernaast niet – Maskuro had tot nu toe
  minstens één herkende naam in het document nodig om de regels
  überhaupt als woordmeldingen te lezen. Draagt het document een kop
  zoals „Verslag" of „Notulen", dan volstaat dat nu. Merkregels
  („Let op: …", „Aanwijzing: …") blijven onaangetast.

- **Een veldbeschrijving verdween samen met haar waarde.** Van
  „Project: Renovatie en uitbreiding gemeenschapscentrum" werd één
  enkele plaatshouder – ook het woord „Project:" was weg, en daarmee de
  aanwijzing wat op die plek had gestaan. Beschrijvingen blijven nu
  staan. Waar een beschrijving bij het gegeven hoort en haar betekenis
  draagt („Doorkiesnummer 214"), verandert niets.

- **De maximale herkenning ruimde zaakbegrippen niet op.** „Plat dak",
  „invoedpunt", „elektrotechniek" en soortgelijke vakwoorden werden ook
  met ingeschakeld AI-niveau als plaats of bedrijf vervangen – de AI
  kreeg precies deze vondsten nooit ter beoordeling voorgelegd. Ze
  controleert ze nu mee: op een corpus uit aanbestedings- en
  contractteksten verdwijnen daardoor alle 27 misgrepen, zonder dat
  ook maar één echt gegeven blijft staan. Namen, bedrijven en plaatsen
  worden ongewijzigd herkend.

- **Soortwoorden voor instellingstypen werden voor organisaties
  gehouden.** In een contracttekst verdwenen „Hogescholen en
  universiteiten", „Openbare en particuliere scholen", „Academische
  opleidingsziekenhuizen", „Onderwijsinstelling" en „Toeleveranciers" –
  woorden die geen bepaalde instelling benoemen, maar een soort
  instelling. Ze blijven nu staan. Staat er een eigennaam vóór
  („EU-Commissie"), dan wordt verder vervangen, en bedrijfsnamen vallen
  helemaal niet onder de regel.

- **Namen in lijsten vielen alleen wanneer ze courant waren.** In een
  deelnemers- of aanwezigheidslijst onder een kolomkop „Naam" werden
  „Anna Huber" en „Thomas Müller" verwijderd, „Wójcik Aleksandra" of
  „Kücükgöl Sinan" echter niet – dezelfde regel, dezelfde opbouw. Wie
  een zeldzamere naam draagt, was daarmee slechter beschermd. Nu
  beslist de kolomkop: wat onder „Naam" staat, is een naam. Een
  positielijst met zakelijke kolomkop blijft onaangetast.

- **Een telefoonnummer achter „Doorkiesnummer" werd in het midden
  doorgeknipt.** Van „Doorkiesnummer 0732 771190" werd
  „[DURCHWAHL_1] 771190" – de tweede helft van het nummer bleef
  leesbaar. Nu vervalt het hele nummer, en de beschrijving blijft
  staan. Een echt doorkiesnummer („Doorkiesnummer 214") wordt
  ongewijzigd samen met beschrijving vervangen.

- **Sommige PDF's lieten zich helemaal niet meer opschonen.** Kon een
  kleurprofiel of de metagegevens in een afbeelding niet aantoonbaar
  worden verwijderd, dan brak de run zonder resultaat af – getroffen
  waren gewone zakelijke documenten zoals AV-pagina's, bestekken en
  aanbestedingen. Zulke bestanden worden nu opgeschoond, en een
  waarschuwing noemt de plekken die open bleven: ze kunnen een
  apparaat-, maker- of opnamekenmerk dragen. Het origineel blijft zoals
  altijd ongewijzigd.

- **Contractrollen werden voor personen gehouden.** „Inschrijver",
  „Consument", „Huurder", „Koper", „Opdrachtgevers" en ongeveer
  veertig andere rolwoorden werden vervangen waar ze zonder lidwoord
  stonden – in contractkoppen, tabelkolommen en handtekeningregels. Een
  contracttekst zonder één enkel persoonsgegeven werd daardoor
  plaatselijk onleesbaar. Deze woorden blijven nu staan. Staat ernaast
  een persoonsaanwijzing – een aanhef, een voornaam, een veldwoord
  zoals „Contactpersoon" –, dan wordt verder vervangen: „De heer
  Inschrijver" en „Mevrouw Koper" zijn namen. Veelvoorkomende
  achternamen die tegelijk beroepen zijn (Bakker, Rechter, Kok), vallen
  helemaal niet onder de regel.

- **Een afgekort geschreven straat werd over het hoofd gezien wanneer
  het huisnummer direct aan de punt kleefde.** „Schlesischestr.31" gold
  niet als adres – en omdat de postcode ernaast haar houvast uit de
  adresvondst haalt, bleef ook zij staan. In het resultaat was het
  adres uit straat en postcode weer samen te stellen, en wel alleen op
  sommige pagina's van hetzelfde document. Beide vallen nu samen.
  Zaakbenamingen met aangehecht getal („Kabelgoot200") blijven
  onaangetast.

- **Een adres over twee regels werd tot één enkele plaatshouder
  samengetrokken.** Stond in een adresblok de postcode boven de straat,
  dan verbond Maskuro beide regels tot één vindplaats: in het resultaat
  verdween de regelafbreking, en de postcode bleef ervoor leesbaar
  staan. Nu wordt elke regel apart gevonden en vervangen, en het
  lettertypebeeld blijft behouden. Dezelfde oorzaak trok af en toe ook
  de achternaam uit de regel erboven het adres in.

- **De maximale PDF-weg neemt geen originele objecten meer over.** Met
  ingeschakelde tekstherkenning bouwt Maskuro elke pagina volledig
  opnieuw op uit de zichtbare PDFium-afbeelding. In het nieuwe
  minimaalbestand komen alleen deze beeldpagina en een nieuw gegenereerde,
  tot de OCR-tekst beperkte zoeklaag – niet de vreemde objectboom met
  opmerkingen, bijlagen, acties, lagen, metagegevens, kleurprofielen of
  private sleutels. Dat geldt ook voor inhoud in
  annotatieweergaven, patronen, Type-3-lettertypen, vormobjecten en
  softmasks. Het bronbestand blijft onaangetast.

- **Gezichten en codes in genestelde PDF-afbeeldingen werden over het
  hoofd gezien.** Beide detectoren zien nu bovendien de volledige
  gerenderde pagina-afbeelding. Daardoor bereiken ook portretten en
  QR-/streepjescodes in annotaties, patronen, Type-3-glyphen en
  transparantiemaskers de detectoren; herkende gebieden worden – indien
  ingeschakeld – vóór de minimaalopbouw onherkenbaar gemaakt. De
  detectie zelf blijft feilbaar.

- **Een ontbrekende OCR-machine eindigde bij PDF's met een interne
  fout.** De maximale run breekt nu gecontroleerd en zonder
  doelbestand af, in plaats van een onvolledig of ongecontroleerd
  bestand uit te geven.

- **Meerdere echte contact- en zakelijke waarden vielen door, terwijl
  zaaktekst werd vervangen.** Naamvelden over regelafbrekingen, bank-
  en bedrijfsnamen, rechtsvormen, beschreven kenmerken, geboortedata
  evenals telefoon-, URL- en IBAN-grenzen zijn strikter gecontroleerd.
  Tegelijk blijven landen in zaaktekst, rol- en soortwoorden,
  artikel-/normcodes, cijferreeksen en gewone afkortingen vaker
  onaangetast.

- **Gemengde en gedraaide OCR-regels werden verkeerd gelezen.** Onzekere
  verticale woorden worden nu plaatselijk rechtgezet nagelezen;
  technische Latijnse waarden in niet-Latijnse tekst krijgen een
  onafhankelijke Engelse getuige. Een vrijstaand onzeker enkel cijfer
  wordt alleen gecorrigeerd wanneer twee nauwe cijferreeksen
  overeenstemmen. Poolse rechtsvormen van de OCR-vorm „sp. z 0.0."
  worden in de gesloten context gelezen als „sp. z o.o.".

- **De beeldmeting kon deels zichtbare restwaarden over het hoofd
  zien.** Ze controleert nu overlappende plaatselijke uitsneden,
  onderscheidt witte plaatshoudertekst op een zwarte balk van originele
  glyphen en draagt ruwe beeldkaders ook over naar gedraaide, opnieuw
  gerenderde minimaal-PDF's. Het vaste synthetische hoofdcorpus bereikt
  daarmee 1.392/1.392 verwijderde doelgegevens bij 0 valse alarmen en
  0 verwerkingsfouten. Dat is een corpusbewijs, geen algemene
  100%-garantie.

- **Niet-commerciële taalmodellen worden niet meer aangeboden.** De zes
  Italiaanse en Griekse spaCy-varianten onder CC BY-NC-SA 3.0 zijn uit
  catalogus, download en laadweg verwijderd; ook al aanwezige
  modelmappen worden genegeerd. Beide talen gebruiken in plaats
  daarvan het MIT-gelicentieerde meertalige model.

- **De naam onder „Contactpersoon" werd maar half verwijderd.** Staat de
  beschrijving alleen op een regel en daaronder „Achternaam Voornaam",
  dan bleef de voornaam staan zodra hij tegelijk een gewoon woord is –
  van „Mayer Roman" werd „[NAME_1] Roman". Zulke regels worden nu
  helemaal genomen. Een afdeling op dezelfde plek („Technische
  binnendienst") blijft verder onaangetast. Bijkomend opgelost:
  „Contactpersoon" telde helemaal niet als naamveld, hoewel
  „Aanspreekpunt" dat van oudsher wel doet.

- **De bedrijfsnaam zonder rechtsvorm bleef staan wanneer een
  branchewoord ertussen stond.** „Kranzbichler Handels GmbH" werd
  verwijderd, het kale „Kranzbichler" drie alinea's later niet – bij
  „Kranzbichler GmbH" daarentegen wel. Nu grijpt beide. Gewone woorden
  zijn daarvan uitgezonderd: „Deutsche Bank AG" maakt geen „deutsche"
  in de tekst tot bedrijf.

- **Dezelfde waarde heette in hetzelfde document eens naam en eens
  plaats.** „Anna Modelvrouw … Modelvrouw" leverde „[NAME_1]" en
  „[ORT_1]" op – op de tweede plek ontbreekt de voornaam, en zonder
  hem werd er een plaats van. Verwijderd was beide, maar het las als
  twee verschillende dingen. Een waarde behoudt nu de benaming van haar
  eerste voorkomen.

- **Datumaanduidingen werden niet meer verwijderd.** Een datum geheel
  uit cijfers („01.03.2026") viel sinds de vorige versie door een
  controle die voor namen was bedoeld, en bleef in het document staan –
  ook in de werkwijze „verschuiven", en zonder regel in het
  controlerapport. Getroffen was alleen wie datumaanduidingen
  uitdrukkelijk had ingeschakeld.

- **Landen en continenten worden niet meer gezwart.** „De levering gaat
  naar de Verenigde Staten", „marktzwakte in Azië", „de norm geldt in
  Roemenië" – zulke aanduidingen zeggen niets over een persoon en
  blijven nu staan. Hoort de landnaam daarentegen bij een adres of
  staat hij achter een beschrijving zoals „Woonplaats" of
  „Geboorteplaats", dan wordt hij verder verwijderd. **Steden zijn niet
  getroffen** – „Ik ben net in Bilbao" blijft een aanduiding over een
  persoon en wordt verder gezwart.

- **Afgekorte woorden werden webadressen.** Staat in de tekst „resp.
  Duitse" of „incl. de", dan levert menige PDF de punt zonder spatie –
  daarvan werd „resp.de" respectievelijk „incl.de", een geldig adres
  met landextensie, en het werd verwijderd. Zulke woordparen blijven nu
  staan. Echte adressen zijn niet getroffen, ook niet zonder „www."
  ervoor.

- **Cijferkolommen uit balansen werden als telefoonnummers gezwart.** In
  jaarverslagen en prijstabellen staan vorig jaar en het lopende jaar
  naast elkaar – „64.518  65.133". Dat gold als één telefoonnummer en
  werd verwijderd, evenals cijferbereiken zoals „12200-23200" en een
  datum met een volgend getal. Zulke getallen blijven nu staan.
  Omgekeerd wordt een echt telefoonnummer zekerder herkend: de
  beschrijvingen „Telefoon", „Fax", „Mobiel", „Doorkiesnummer" en hun
  equivalenten in de andere interfacetalen tellen nu mee – tot nu toe
  herkende het programma daar alleen de Engelse woorden.

- **Namen in een genummerde tabel bleven staan.** Een deelnemerslijst of
  personeelstabel in de gebruikelijke vorm – kolomkop, daaronder „1.1
  Auersperg Bernhard Montage 03.03.2026" – werd helemaal niet
  opgeschoond: zulke regels zagen eruit als de positielijst van een
  offerte, waarin zaakbegrippen moeten blijven staan. Draagt de kolomkop
  een persoonsbeschrijving („Naam", „Achternaam", „Surname" …), dan
  gelden de regels eronder nu als namen. Positielijsten blijven
  ongewijzigd gespaard – ook wanneer in de briefkop „Behandelaar:"
  staat.

- **Uit een naam ontstonden soms twee plaatshouders naast elkaar.**
  Wanneer een achternaam ook los in het document stond, verving de
  nabewerking op een plek zoals „Anna Modelvrouw GmbH" eerst de
  achternaam en dan de voornaam – in het resultaat zag dat eruit als
  twee verschillende personen. Nu wint de langst bekende naam.

- **Verzonnen waarden stonden in geen enkele toewijzing.** Wie „Waarden
  verzinnen" had gekozen, kreeg een resultaat waarin „Anna Modelvrouw"
  „Greta Mayrhofer" was geworden – in de toewijzing stond daar niets
  van, zodra in hetzelfde document ook maar één anonieme vervanging
  voorkwam. Daarmee viel geen verzonnen waarde terug te halen, en het
  toewijzingsbestand verzweeg de vervanging. Het netelendste was het
  derde: wie het resultaat leest, ziet een geloofwaardige naam en heeft
  geen aanwijzing dat hij verzonnen is. Nu staat elke vervanging in de
  toewijzing.

- **De toewijzing noemde gezwarte inhoud „vervangen".** Een e-mail
  deelt een toewijzing met haar bijlagen, en de bijlage mag gezwart
  worden, terwijl de mailtekst een plaatshouder draagt. In de
  toewijzing stond dan voor alle drie plekken hetzelfde – „vervangen" –
  en het terughalen zocht in de bijlage een plaatshouder die daar niet
  bestaat: de balk bleef liggen. Nu staat per vindplaats wat daar
  werkelijk gebeurde, en beide bijlagen komen terug.

- **Waarden die alleen in een afbeelding stonden, waren niet terug te
  halen.** In het trefpaneel stonden ze dubbel – eenmaal als
  plaatshouder die in het document nergens bestond („De plaatshouder is
  niet in het document gevonden"), eenmaal als gezwarte plek. De eerste
  regel was pure boekhouding en is verdwenen.

- **Gezwarte waarden waren maar één keer terug te halen.** Staat
  dezelfde waarde op meerdere plekken, dan haalt één klik ze allemaal
  terug – de overige regels bleven echter in het trefpaneel staan, en
  de volgende klik erop meldde „Niet eenduidig". Ze verdwijnen nu mee.

- **Terughalingen ontbraken in het controlelogboek wanneer de leermodus
  uitstond.** Wie een teruggehaalde waarde in het nabewerkingsvenster
  herstelde, vond het proces niet terug in het controlelogboek zodra de
  leervragen waren uitgeschakeld – het bewijs hing aan een schakelaar
  die alleen de regelvoorstellen betreft. Bij ingeschakeld
  controlelogboek wordt nu onafhankelijk daarvan naar de reden gevraagd
  en de regel geschreven.

- **Ingesleepte bestanden bleven niet opgeschoond – en werden niet eens
  gemeld.** Wie een bestand in een document sleept in plaats van het als
  bijlage te versturen, legt Word of PowerPoint dat volledig in het
  document vast. Het stond daarna ongewijzigd in het resultaat, samen
  met zijn oorspronkelijke bestandsnaam en opslagpad – en die dragen in
  de praktijk vaak zelf een naam. Zulke bestanden worden nu net als het
  overige document opgeschoond.

- **En waar dat niet lukt, zegt Maskuro het.** Zit in een ingebed object
  een oud formaat (Word 97, Excel 97) waarvoor er geen opschoning
  bestaat, dan verschijnt nu een LET OP-melding met de naam van het
  bestand. Tot nu toe werd het stilzwijgend ongewijzigd doorgegeven.

- **Verscheurde woorden en afkortingen werden voor namen gehouden.** Als
  een woord in een PDF aan het regeleinde is afgebroken, komt bij het
  uitlezen van sommige bestanden een fragment naar boven –
  „Jaarrekeni… gelds", „Bedrijvi…". Zulke fragmenten,
  aaneengeplakte woorden („DeurslotmetV") en kale afkortingen („JY",
  „FFB") werden gezwart alsof ze namen waren. Ze blijven nu staan. Een
  naam met dezelfde afbreekschade blijft verder gezwart, zolang er een
  aanhef bij staat – en namen die van huis uit een hoofdletter midden
  in het woord dragen (McKenzie, MacDonald, LeBlanc), zijn daar sowieso
  niet door getroffen.

- **Maataanduidingen en maanden golden als adres.** In technische
  documenten werden „2000 Lux", „1200 Mbit", „1500 Watt", „5308 Plaats"
  en „2022 Mrz" gezwart – vier cijfers en een woord met hoofdletter
  zagen eruit als een postcode met plaats. Een postcode telt nu alleen
  nog mee als er ook een adressignaal bij is: een landcode, een
  veldbeschrijving, het begin van de regel, een straat in de regel
  erboven of een plaats die ook de taalherkenning daar ziet. In vijf
  bestekken verdwijnen daarmee 14 foutieve zwartingen, zonder dat een
  echt adres blijft staan.

- **De nauwkeurigere herkenning verving te veel.** Het inschakelbare
  niveau „nauwkeurigere herkenning" hield in Duitse zakelijke
  documenten zaakbegrippen voor namen en plaatsen –
  „fotovoltaïsche-installatie", „invoedpunt", „plat dak",
  „personeelsingang" – en zwartte bedrijfsbenamingen uit lopende
  positielijsten. Reden was een ontzien: hun treffers werden
  uitgezonderd van de controles die een positie- of registerregel
  herkennen. Dit ontzien geldt nu alleen nog voor meerdelige namen,
  waarvoor het niveau bestaat – „Anna Huber" in een registerregel
  blijft dus herkend, een los zaakwoord in een positieregel vervalt. In
  een technische aanbesteding halveert dat de foutieve zwartingen van
  het niveau, zonder dat een naam verloren gaat.

- **Diagrammen brachten hun volledige brongegevens mee – ongecontroleerd.**
  Wie in Word of PowerPoint een grafiek invoegt, legt het programma de
  tabel waaruit ze werd berekend als eigen bestand in het document.
  Zichtbaar daarvan zijn alleen de paar getallen in de grafiek; in de
  tabel staat de hele lijst, inclusief de regels die in de grafiek
  helemaal niet voorkomen. Deze tabel werd tot nu toe ongewijzigd
  doorgegeven. Ze wordt nu mee opgeschoond, met dezelfde plaatshouders als
  het overige document.

- **Hetzelfde voor ingebedde objecten in OpenDocument-bestanden** (ODT,
  ODS, ODP): een ingevoegde grafiek of een ingevoegde tabel bleef
  onaangetast.

- **Word-documenten: voetnoten en eindnoten werden niet opgeschoond.**
  Hun tekst bleef volledig in het resultaat staan – ook namen, adressen
  en rekeningnummers. Getroffen was elk Word-document met een voet- of
  eindnoot. Evenzo bleef een autotekstblok onaangetast dat onzichtbaar
  met het document meereist.

- **Word: gegevens in keuzelijsten, opmerkingen en beeldbeschrijvingen.**
  De items van een keuzeveld (zichtbaar pas bij het openklappen), de
  auteur van een opmerking, de beschrijving van een tekening en het
  adres achter een verwijzingsopdracht stonden verder in het resultaat.

- **Excel: de draaitabel voerde de brongegevens een tweede keer op.**
  Een werkmap met een draaitabel bewaart daarin een volledige kopie van
  de geanalyseerde regels – onzichtbaar, maar in het bestand. Deze
  kopie bleef tot nu toe ongewijzigd staan, ook als in het blad zelf
  alles was vervangen. Getroffen was elke analyse die met een
  draaitabel werd doorgegeven.

- **Excel: gespreksopmerkingen en hun auteurs.** De tekst van een
  opmerking van het nieuwere type en het register van de
  opmerkingmakers – weergavenaam en aanmeldkenmerk, in bedrijven meestal
  het e-mailadres – stonden verder in het resultaat. Hetzelfde register
  in Word-documenten eveneens.

- **Zelfgedefinieerde documenteigenschappen in Word en Excel.** Velden
  zoals „Cliënt" of „Dossiernummer", die een kantoor aan zijn sjablonen
  meegeeft, werden tot nu toe niet opgeschoond. Ze zijn in geen enkele
  weergave te zien en reizen toch met elke kopie mee.

- **Tabellen (ODS): de keuzelijst van een cel.** Zoals in Excel sinds de
  vorige versie wordt nu ook in OpenDocument-tabellen opgeschoond wat bij
  het openklappen van een cel verschijnt. Verwijzingen naar andere
  cellen blijven daarbij onaangetast, zodat de lijst blijft werken.

Al deze plekken zijn zoals gewoonlijk via de toewijzing weer terug te
halen.

- **Outlook-berichten: een beschadigd bestand beëindigde de opschoning
  hard.** Bepaalde kapotte `.msg`-bestanden leidden tot een afbreking in
  plaats van een melding; nu worden ze gelezen, voor zover ze leesbaar
  zijn.

- **Het toewijzingsbestand is nu alleen voor u leesbaar.** Het bevat de
  originele gegevens in klare tekst en lag tot nu toe met de
  gebruikelijke rechten naast het resultaat – op een gedeelde opslag
  kon daardoor iedereen het openen. Aan het opgeschoonde resultaat zelf
  verandert niets; het moet immers worden doorgegeven.

- **Nageladen taalmodellen worden vóór het uitpakken nauwkeuriger
  gecontroleerd.** Een gemanipuleerd pakket – bijvoorbeeld uit een
  bedrijfsshare, van waaruit meerdere werkplekken worden bediend – kon
  bij het uitpakken bestanden buiten de bedoelde map plaatsen. Aan het
  gewone naladen verandert niets.

- **Schermafbeelding maken – en het wordt meteen opgeschoond.** Met
  `Ctrl+Shift+B`, via „Bestand → Schermafbeelding maken …" of via het
  symbool in de taakbalk trekt u een kader over het scherm. Wat daarin
  ligt, gaat vervolgens dezelfde weg als elk ander bestand: de
  tekstherkenning leest de schermtekst, namen, adressen, telefoonnummers
  en e-mailadressen worden gezwart, en daarna staat de afbeelding open
  in de editor, waar u met een kader kunt nazwarten wat over het hoofd
  is gezien. De opgeschoonde afbeelding belandt op het bureaublad (of in
  uw ingestelde uitvoermap); de **ruwe** opname wordt nergens
  opgeslagen en bij het afsluiten gewist. De tekstherkenning wordt voor
  deze run ingeschakeld, ook als ze verder uit staat – aan een
  afbeelding zou zonder haar niets te vinden zijn. Op de Mac vraagt het
  systeem de eerste keer om de toestemming „Schermopname".

- **Op afbeeldingen kan nu getekend worden: rechthoek, ellips, pijl,
  tekst en genummerde stapmarkeringen.** In zes kleuren en drie
  lijndiktes, te kiezen met de toetsen 1 tot 5. Bedoeld voor
  schermafbeeldingen en handleidingen: tonen waar het om gaat, zonder
  daarvoor een tweede programma te openen. Ongedaan maken en het
  natrekken aan de handvatten gelden zoals voor elke balk – een
  aantekening is dus te verschuiven en op te trekken nadat ze is gezet.
  **Tekenen is uitdrukkelijk geen zwarten.** Een getekende rechthoek is
  een kader, geen balk: wat eronder staat, blijft leesbaar en gaat mee
  met het bestand naar buiten. Voor het verwijderen van gegevens zijn
  verder „Zwarten" en „Pixeleren" er; de tekenwerktuigen staan daarom
  in een eigen regel van de werkbalk, en de aanwijsregel zegt het
  zolang een ervan gekozen is.

- **De bewerkte afbeelding gaat met één klik naar het klembord.**
  „Afbeelding kopiëren" in de editor (of `Ctrl+C`) legt ze op zoals ze
  daar staat – plakken volstaat om ze in een bericht of mail te
  brengen. Daarmee is de weg van de toetsaanslag tot in de chat vier
  stappen lang en heeft geen map nodig.

- **Daarbij een markeerstift, schaduw en verlopen.** „Markeren" kleurt
  een vlak in zonder het te bedekken – de inhoud eronder blijft
  leesbaar, en juist daarin verschilt het van de balk. „Schaduw" heft
  een aantekening af van een onrustige ondergrond, „Verloop" laat de
  kleur in trekrichting uitdoven; beide gelden voor alle zes
  tekenwerktuigen.

- **Opgelost voordat het iemand trof:** de nieuwe werktuigregel zou bij
  iedereen die Maskuro al gebruikt heeft, bijna leeg zijn verschenen –
  de onthouden vensterindeling stamde van vóór die tijd en zou haar geen
  plaats hebben gegeven. Een verouderde indeling wordt nu verworpen;
  het editorvenster staat dan eenmalig in zijn basisindeling.

- **De eigen schermafbeelding is uit te schakelen.** Wie Greenshot,
  ShareX of het uitsnijdgereedschap gewend is, schakelt onder
  „Instellingen → Programma" „Schermafbeelding maken met Maskuro" uit.
  Maskuro meldt de toetsencombinatie dan helemaal niet aan – ze blijft
  van uw eigen werktuig –, en de omschakeling geldt meteen, zonder
  herstart. Opschonen lukt bij een zo gemaakte afbeelding verder:
  Ctrl+V haalt haar uit het klembord in het venster.

## 0.10.37-alpha.20260821 – 21 augustus 2026

### Nieuw

- **Bij het anonimiseren draagt nu elke vindplaats haar eigen nummer.**
  Tot nu toe heetten alle personen `[NAME]`, alle plaatsen `[ORT]" –
  daardoor was niet meer te zeggen welke plek bij welke waarde hoorde, en
  er viel niets terug te halen. Nu tellen de nummers per voorkomen door:
  dezelfde naam staat op drie plekken als `[NAME_1]`, `[NAME_3]` en
  `[NAME_7]`. In het document is daarmee verder niet te herkennen welke
  plekken samenhoren – met het toewijzingsbestand is echter elke
  afzonderlijke terug te halen. Het toewijzingsbestand is daarom ook bij
  het anonimiseren weer te kiezen; bewaar het gescheiden van het
  resultaat.
- **Maanden, weekdagen, valuta's, eenheden en bedrijfsrechtsvormen in
  alle 48 documenttalen gelden niet meer als namen of plaatsen.** De
  kalender- en eenheidsnamen komen uit Unicode CLDR (gegenereerd, niet
  geschreven), de rechtsvormen uit het vennootschapsrecht van de landen
  – ook meerwoordig („sp. z o.o.", „Pty Ltd") en voorafgaand
  („株式会社"). Waar een maandnaam tegelijk een voornaam is (Juli,
  Augustus, May), beslist de bouwvorm: met dag of jaar ernaast een
  datum, anders een naam. Daarbij aanheffen en titels, hele
  groetformules, documenttypes en straatgrondwoorden voor 28 talen met
  eigen taalmodel, wetsafkortingen (AVG, UStG, ABGB, § 6 Abs 1 Z 27
  UStG) evenals taalnamen als veldwaarde („Taal: Duits"). De lijsten
  staan onder „Help → Woordenlijsten …".
- **India: adres en pincode worden herkend** – „15 गांधी मार्ग", „नई
  दिल्ली 110001" evenals „15 Gandhi Marg, New Delhi 110001". Het
  landenpakket India kende tot nu toe alleen kenmerken; in
  Hindi-documenten bleven adressen daardoor staan.
- **Elk opgeschoond kantoorbestand wordt vóór de overdracht nog een keer
  als pakket geopend.** Een tekstuittreksel merkt niet wanneer Word,
  Excel of LibreOffice het bestand zouden weigeren (dubbel item,
  afgescheurd XML, een ontbrekend onderdeel). En geteld wordt tegen het
  origineel wat een opschoning nooit mag veranderen: pagina's van een
  PDF, bladen, regels en cellen van een tabel, dia's van een
  presentatie. Slaat de proef aan, dan staat een LET OP-waarschuwing in
  het resultaat en in het controlerapport – het origineel blijft
  ongewijzigd.
- **Ook de automatiek zwart het hele veld.** In de zwartingsmodus dekt
  de balk in korte regels – adresblok, tabelcel, kopgegevens – de hele
  regel in plaats van alleen de gevonden waarde: een balk in
  woordlengte verraadt hoe lang het woord was. Beschrijving en bedragen
  ernaast blijven staan, en regels lopende tekst (langer dan de halve
  tekstbreedte) worden verder woordnauwkeurig gezwart, zodat een naam
  midden in de zin niet de hele zin zwart maakt.
- **Teruggehaalde inhoud ziet er weer uit als in het origineel.**
  „Origineel terughalen" en „Vervanging ongedaan maken" in de
  PDF-editor schrijven het gebied nu exact uit het bronbestand terug –
  hetzelfde lettertype, dezelfde grootte, dezelfde kleur en positie, op
  een scan dezelfde beeldpunten. Tot dan werd de tekst in een
  vervanglettertype opnieuw ingelegd en zag hij herkenbaar nagebouwd
  uit. De balk van een eerdere zwarting verdwijnt daarbij helemaal, in
  plaats van wit te worden overschilderd – een gekleurde celgrond in
  een tabel blijft behouden. Dat geldt ook op gedraaide pagina's, voor
  tekst uit ingebonden formulierobjecten en voor **ingevulde
  formuliervelden**: op de daarvoor gerasterde werkkopie komt het
  fragment uit de opnieuw gerenderde originele pagina terug – ook waar
  geen tekstlaag de veldwaarde kent. Ook **vervangen afbeeldingen** in
  de PDF komen zo terug – gepixeleerd, vervaagd of geheel verwijderd,
  geheel of alleen het gesleepte uitsnede. Alleen waar het bronbestand
  niet meer naast het resultaat ligt, blijft het bij de bestaande weg.
- **Gezwarte en zonder vervanging verwijderde waarden zijn ook in Word,
  Excel, PowerPoint en OpenDocument terug te halen.** Tot nu toe had de
  terughaling daar een plaatshouder in de tekst nodig – een balk of een
  leemte had geen terugweg. Nu biedt het trefpaneel de regels „gezwart"
  en „verwijderd" aan, zodra het onaangetaste bronbestand naast het
  resultaat ligt: Maskuro vergelijkt het resultaat met het origineel en
  zet de waarde weer in op de plek van de balk of de leemte – inclusief
  opmaak, een verdeelde run wordt weer heel. Geldt evenzo voor tekst,
  HTML, e-mail en de Office-bijlagen van een e-mail; draagt de
  mailtekst een plaatshouder en de bijlage een balk, dan worden beide
  in één keer teruggehaald.
- **Ook PDF-bijlagen van een e-mail of Outlook-bericht zijn terug te
  halen** – plaatshouders (genummerd en anoniem), balken en zonder
  vervanging verwijderde inhoud. Zonder canvas komt de plek uit de
  originele bijlage; terug komt de waarde glyphnauwkeurig, in de
  leesvolgorde van het origineel.
- **Gemaskeerde waarden zijn terug te halen** – in de PDF en in de
  tekstweergave. Een masker („**** **** **** **** 3201") is nooit
  eenduidig, twee nummers dragen hetzelfde; daarom neemt de terughaling
  nooit de letterlijke weg, maar vraagt het origineel welke waarde op
  die plek stond. Tot nu toe waren deze regels in het trefpaneel
  helemaal niet bedienbaar.
- **Ingebedde afbeeldingen in Word, Excel, PowerPoint en OpenDocument
  zijn terug te halen.** Een in de afbeelding gezwarte waarde komt via
  haar paneelregel terug – Maskuro leest de originele afbeelding en
  haalt precies die plek terug; een vervaagde, verwijderde of met
  gezichten en codes bewerkte afbeelding haalt het nieuwe item
  „Ingebedde afbeeldingen terughalen" in het menu Bewerken als geheel
  uit het bronbestand – ook door de Office-bijlagen van een e-mail of
  Outlook-bericht heen. Een afbeelding die zelf als bijlage hangt en
  via tekstherkenning werd gezwart, komt eveneens via haar paneelregel
  terug.
- **Verzonnen waarden zijn in de tekstweergave terug te halen.** Tot nu
  toe meldde het paneel daar „Niet eenduidig". Nu zoekt de terughaling
  de waarde in het origineel en vereist op dezelfde plek in het
  resultaat precies de verzonnen vervanging – een verzonnen naam wordt
  nooit letterlijk overal vervangen, hij zou ergens echt kunnen staan.
- **Terughaling in Word, Excel, PowerPoint en OpenDocument behoudt de
  opmaak van het origineel.** Stond een waarde over meerdere runs –
  „Anna" normaal, „Modelvrouw" vet en rood –, dan kwam ze tot nu toe
  helemaal in de eerste run terug en verloor ze vet en kleur. Nu
  verdelen de tekens zich weer zoals in het origineel; een Word-alinea
  is daarna byte voor byte de oorspronkelijke. Hetzelfde geldt voor
  HTML-pagina's, het HTML-deel van een e-mail en de HTML-body van een
  Outlook-bericht (.msg) – bij de e-mail blijft bovendien de doctype
  behouden, die de opschoning tot nu toe stilzwijgend verwijderde.
- **Tekstbestanden behouden hun codering.** Opschoning en terughalen
  schrijven `.txt`, `.md` en `.csv` nu in de codering waarin ze werden
  aangeleverd – UTF-8 met en zonder BOM, UTF-16, Windows-1252. Tot nu
  toe werd een Windows-1252-bestand steeds naar UTF-8, en een
  UTF-16-bestand kwam beschadigd terug, ook als er niets te vervangen
  viel.
- **Teruggehaalde afbeeldingen behouden hun kleurmodus.** Een
  grijswaardenscan komt als grijswaarden terug in plaats van als
  driemaal zo groot RGB-bestand, een palet als palet, zwart-wit als
  zwart-wit – bij de hele afbeelding met dezelfde waarden als in het
  origineel. Geldt voor beeldbestanden en voor afbeeldingen in PDF's.
  CMYK en 16 bit blijven RGB, omdat het PNG-resultaat beide niet kan
  dragen.
- **Een kader in de afbeelding haalt de hele bewerking terug die het
  raakt.** Gepixeleerde gezichten dragen een rand rond de herkende box;
  wie het kader alleen over het gezicht trok, hield een gepixelde ring
  over. Nu groeit het kader naar de samenhangende wijziging ten opzichte
  van het origineel – een kader over de oogpartij volstaat. Losstaande
  balken ernaast blijven staan; bij een geheel verwijderde of geheel
  vervaagde foto geldt verder het getrokken kader. Geldt voor
  beeldbestanden en afbeeldingen in PDF's.
- **Zwartbalken over de hele regel.** In de regelmodus van de editor
  loopt de balk nu van het eerste tot het laatste woord van de regel,
  niet meer alleen over het getroffen woord – een balk in woordlengte
  verraadt hoe lang het woord was, en uit zes tekens vóór een postcode
  is een plaatsnaam te raden. Beschrijvingen, bedragen en
  tabelkolommen naast de waarde blijven staan – de balk dekt het veld,
  niet de regel van de rekening. De nieuwe schakelaar „Hele regel"
  naast „Tekstregels" stelt weer om naar woordnauwkeurig, wanneer de
  buurwoorden moeten blijven staan; de keuze wordt onthouden.

### Opgelost

- **Afbeeldingen in HTML-pagina's en e-mails bleven ongecontroleerd – de
  naam in het logo stond na de opschoning nog leesbaar erbij.** Een in
  de pagina ingebedde afbeelding (``data:``-adres) werd helemaal niet
  aangeraakt, alleen zijn alternatieve tekst; het logo aan de
  HTML-tak van een mail (inline-afbeelding zonder bestandsnaam) viel
  door de bijlagenfilter; en bij de benoemde beeldbijlage bleef de
  beeldregel „vervagen"/„verwijderen" zonder effect. Nu lopen alle drie
  dezelfde weg als een beeldbestand: tekstherkenning in de behouden
  afbeelding, gezichten, codes, metagegevens en de beeldregel. Het
  rapport noemt de afbeeldingen – ook de waarschuwing wanneer ze zonder
  tekstherkenning ongecontroleerd blijven –, en „Ingebedde afbeeldingen
  terughalen" evenals de terughaling vanuit het trefpaneel kennen deze
  afbeeldingen eveneens.
- **Een kantoorbestand met afbeelding liet zich helemaal niet opschonen
  als de tekstherkenning de taal niet beheerste.** Op de Mac leest de
  systeemeigen tekstherkenning; voor Hindi, Grieks, Kroatisch of Litouws
  kan ze dat niet en zegt dat sinds kort ook – bij Word, Excel,
  PowerPoint en OpenDocument brak daarop echter de **hele** opschoning
  af, en er ontstond geen bestand. Terwijl de tekst probleemloos te
  opschonen was; alleen de afbeelding was niet leesbaar. Nu wordt het
  bestand geschreven zoals bij PDF en losse afbeeldingen, en in het
  resultaat staat dat de afbeeldingen NIET werden gecontroleerd – met
  de reden en de verwijzing naar „Talen beheren".

- **In Excel-werkmappen bleven namen in keuzelijsten staan.** De lijst
  van een dropdown-veld (gegevensvalidatie) wordt nu opgeschoond zoals
  elke andere celinhoud; verwijzingen naar celbereiken blijven
  onaangetast, zodat de werkmap heel blijft.
- **Waar de plaatshouder niet paste, stond een zwarte balk – nu staat
  daar een kortere schrijfwijze.** `[GEBU_1]` in plaats van
  `[GEBURTSDATUM_1]`, en pas wanneer ook de kortste vorm niet meer
  past, wordt gezwart. Een balk zegt niemand meer dat daar iets stond;
  een korte plaatshouder wel. De nabewerkingseditor kon dat al, de
  zelfstandige opschoning tot nu toe niet. Het toewijzingsbestand
  voert beide schrijfwijzen op dezelfde waarde, zodat ook het ingekorte
  terug te halen is.
- **De eerste klik op „Vervangen" liet het nabewerkingsvenster kort
  hangen.** De herkenning die de plaatshouder zijn soort geeft
  (`[NAME_3]` in plaats van `[BEGRIFF_3]`), werd pas op dat moment
  geladen – ongeveer twee tot drie seconden. Ze wordt nu bij het
  openen van het venster op de achtergrond voorbereid; gemeten zijn uit
  2289 milliseconden 193 geworden.
- **Twee gelijktijdige opschoningen konden hetzelfde taalmodel dubbel
  laden** – bijvoorbeeld de mapbewaking en het hoofdvenster. Omdat elk
  model meerdere honderden megabytes inneemt, stond de geheugenbehoefte
  daarbij kortstondig op het dubbele. Nu wacht de tweede run op het
  model van de eerste.
- **De plaats in de datumregel wordt nu ook verwijderd wanneer het
  taalmodel haar alleen niet herkent:** wat als postcode met plaats
  zeker gevonden is („3335 Amstetten"), trekt haar plaatsnaam door het
  hele document na – zoals een achternaam uit een volledige naam. En
  een afkorting met cijfer vóór een naam („T3 Hofbauer Christian")
  blijft leesbaar, in plaats van met de plaatshouder te verdwijnen.
- **Drie lekken uit de tweede lezing van een echte order gesloten:** de
  behandelaar „T3 Hofbauer Christian" gold wegens de afkorting „T3" als
  kolomkop en bleef leesbaar; een plaats die het taalmodel via de
  regelafbreking in de kolomkop las, slikte „Pos." in en liet de
  voornaam van de klant staan; en een naam samen met aanhef („De heer
  Robert Köttel") trok alleen de achternaam mee, niet de voornaam – en
  dat gold voor elk „De heer". Afkortingen zijn nu pure letters,
  tweewoordnamen geen koptekst, treffers worden vóór een kolomkop
  afgesneden, en de aanhef telt niet mee met de naam.
- **De plaats in de datumregel („Melk, 05.08.2026") direct onder het
  adresblok bleef leesbaar.** Het taalmodel plakte haar met de plaats
  van de postcoderegel tot één treffer, en die viel als geheel tegen
  het postcodepatroon. Nu blijft het uitstekende restant een eigen
  treffer. Gevonden via de nieuwe tweede lezing van het resultaat
  (`werkzeuge/zweitlesung.py`).
- **Mac: een scan in een taal die de systeemeigen tekstherkenning niet
  beheerst (bijvoorbeeld Hindi, Grieks, Kroatisch, Litouws), gold als
  gecontroleerd.** Gelezen werd met de Engelse terugval, het vreemde
  schrift bleef in de afbeelding, en het rapport zei „niets gevonden".
  Nu heet het „Afbeelding(en) zijn NIET gecontroleerd" met de reden, en
  het taalbeheer belooft voor zulke talen geen tekstherkenning meer,
  alleen omdat er een Tesseract-taalbestand aanwezig is.
- **In de PDF blijft het leesteken achter een vervangen waarde staan.**
  Van „Opname op 01.03.2026, ontslag op 04.03.2026." werd tot nu toe
  „Opname op [DATUM_1] ontslag op [DATUM_2]" – komma en slotpunt
  ontbraken, bij plaatshouders zo goed als bij verschoven data.
  Verwijderd wordt nu alleen de herkende waarde, niet het hele woord
  tot de volgende spatie; komma, puntkomma, punt of haakje erachter
  blijven op hun plek, en de plaatshouder loopt er niet overheen.
- **Russisch en Oekraïens draaiden ongemerkt op het zwakkere meertalige
  model** wanneer een hulppakket voor de woordvormanalyse
  (`pymorphy3`) ontbrak – de eigen modellen lieten zich dan niet
  laden, en „Львів" werd een persoon. Voor de herkenning van namen is
  de woordvormanalyse niet nodig; het model wordt nu zonder haar
  geladen, en plaatsen zijn weer plaatsen.
- **De licentievermeldingen in 16 talen stonden op oude stand.** Daar
  stond nog dat de MPL-broncode „op aanvraag" werd verstrekt, QPDF
  gold als MPL-2.0, zeven bouwstenen ontbraken in de tabel (wordfreq,
  Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), de
  spaCy-alinea was Engels, en aan het einde hing een Engelse
  vervangsectie. Nu staan alle 18 versies op de stand van de Duitse:
  bronarchieven blijvend onder maskuro.com/quellcode/oss/, QPDF
  Apache-2.0, Qt-LGPL-weg, modelherkomst. Ook de Engelse tabel heeft de
  ontbrekende regels.

- **Contractwoorden in de genitief („des Angebotsinhaltes", „des
  Anbotes", „des Terminplanes") gelden niet meer als plaats.** Eén
  enkel woord achter een genitief- of datiefartikel met
  verbuigingsuitgang is een soortwoord – plaatsnamen buigen niet
  („naar Graz"). Staat de plaats elders in het document zonder artikel
  („Burgenland"), dan blijft ook „des Burgenlandes" herkend.
- **Verschoven, gemaskeerde en verzonnen waarden rasterden de
  PDF-pagina.** De nacontrole na het verwijderen stond in het
  vondstrechthoek alleen een plaatshouder tussen vierkante haken toe;
  een verschoven datum („01.07.2026") of een gemaskeerde waarde
  („****1234") gold als over het hoofd gezien restant, en de pagina
  werd voor de zekerheid naar een afbeelding omgezet – bij „Vervangen"
  niet. Nu blijven zulke pagina's tekst, en het terughalen uit paneel
  of kader levert weer het origineel.
- **Meerwoordige vervangwaarden waren in de PDF niet via het trefpaneel
  ongedaan te maken.** Een verzonnen naam („Greta Mayrhofer") of een
  gemaskeerde IBAN („**** **** **** **** 3201") bestaat uit meerdere
  woorden; de vindplaatszoektocht vergeleek woord voor woord en
  meldde „De plaatshouder is niet in het document gevonden". Nu worden
  opeenvolgende woorden van dezelfde regel samengelezen.
- **Na het terughalen van een zonder vervanging verwijderde waarde bleef
  haar paneelregel staan.** Waarden die de strategie „zwarten" in
  plaatshoudermodus zonder vervanging verwijdert, hebben geen
  plaatshouder waaraan het paneel een verdwijning kon meten. Nu wordt
  de regel doorgehaald zodra de waarde weer in het document staat.

- **Afkortingscomposita zoals „E-Helfer" of „U-Bahn" gelden niet meer
  als naam.**
- **Afbreekresten („Leis-") en extreem lange composita
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") gelden
  niet meer als naam of plaats.** In een gescande aanbestedingstekst
  werden zo 28 woorden minder gezwart.
- **Positielijsten van gescande offertes gelden niet meer als
  namenregister.** De extra doorloop voor registers (korte regels)
  maakte van „Koelbuis" en „Buitenapparaten" personen; ze slaat nu
  over zodra positienummers zoals „1.1.5" aan het begin van de regel
  staan. Datumregels in mailwisselingen tellen daarbij niet als
  positienummers.
- **Kolomkoppen en positienummers van gescande offertes („Pos.",
  „Pos. 1.1.3", de afkortingen „E/L/S") golden als naam of plaats.**
  Een afkorting alleen op haar regel, een beschrijving samen met
  nummer en losse letters per regel zijn dat niet.
- **De pagina „ademde" in het nabewerkingsvenster na het openen van het
  vergelijkingsvergrootglas** – bij „Paginabreedte" en „Inpassen" hangt
  de schaal aan het beeldvenster, en dat verandert bij elke schuifbalk
  die komt of gaat; elke volgende actie schoof de pagina een stukje op.
  Het canvas trekt dat nu vanzelf recht, tot het stilstaat. En
  zoomknoppen, regelaar en toetsencombinaties houden het beeldmidden
  ook vast wanneer bij het inzoomen een schuifbalk verschijnt.
- **Liggend opgeslagen scans worden nu rechtop gelezen, en kleine letters
  in grote scans gaan niet meer verloren.** Een 24 pagina's tellende
  gescande offerte behield in elke voettekst zes bank-IBAN's,
  handelsregisternummer en btw-nummer leesbaar: de scan lag in de PDF
  90° gedraaid, en de tekstherkenning liet bij zeer grote afbeeldingen
  afhankelijk van de beeldmaat hele regels weg. Nu wordt de zichtbare
  rotatie meegenomen en grote afbeeldingen worden in overlappende
  banden gelezen – de voetteksten zijn zwart.
- **Straten naar personen met koppelteken vóór het grondwoord („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8",
  „Dr.-Karl-Renner-Straße 12") worden als adres herkend.** In de
  briefkop van een gescande offerte bleef zo'n adres leesbaar, omdat
  het patroon een spatie vóór „Straße" vereiste.
- **IBAN's uit de tekstherkenning die een O in plaats van 0 of een l in
  plaats van 1 dragen, worden nu herkend.** In de kleine letters van
  een scan leest de tekstherkenning cijfers graag als letters; het
  nummer had dan de vorm van een IBAN, maar de controlesom klopte niet,
  en het bleef staan. Klopt de controlesom niet, dan wordt nu de
  lezing met cijfers geprobeerd – klopt die dan wel, dan is het de
  IBAN. Foute controlecijfers blijven fout.
- **Zinsfragmenten zoals „volgende codes op de" golden als plaats.** Een
  naam of plaats die met een kleingeschreven woord begint, is er geen –
  behalve bij adelspartikels („van Gogh", „de Vries").
- **In de editor bleef naast de zwartbalk de laatste letter staan**
  („…6", „…t", „…g"), en de balk had de hoogte van het getrokken kader
  in plaats van de regel. Oorzaak: kon de editor de pagina niet meten,
  dan hield hij elk kader voor „geen woord geraakt" en paste het exact
  toe – zonder de regel dat een half woord nooit blijft staan.
  Hetzelfde gebeurde bij losse tekstopdrachten die de editor niet kon
  plaatsen. Nu telt daarnaast altijd het woordkader: wat het kader
  wezenlijk overlapt, vervalt helemaal.
- **De laatste letter van een woord stak boven de zwartbalk uit.** De
  balk werd naar de voortgangsbreedte uit de lettertypemetriek
  gemeten; tekent het lettertype een glyph breder, dan stond het
  restant ervan naast de balk. Het kader van een teken neemt nu ook de
  getekende glyph op.
- **De melding over het omzetten van een pagina naar een afbeelding
  beloofde te veel.** „De weergave blijft gelijk" klopt na het
  rasteren niet: lettertype en grafiek zijn dan beeldpunten, het
  bestand wordt groter. De melding zegt dat nu – en noemt ook de
  tweede reden waarom wordt gerasterd (de omzetting zou de pagina
  hebben beschadigd).
- **De tekst achter een verwijderde waarde schoof tot een punt naar
  links.** Bij het omzetten van een regel werd het begin gemeten aan de
  glyphrand, het vervolg aan het pengronsprong – de voorbreedte van de
  eerste letter bleef als fout staan („C" 0,5 pt, „I" 1,0 pt). Nu
  rekent de omzetting doorlopend met het pengronsprong; het vervolg
  staat op de tiende punt nauwkeurig op zijn plek.
- **Oostenrijkse btw-nummers met spaties („ATU 187 35901") en een
  handelsregisternummer zonder „FN" onder zijn beschrijving
  („Handelsregisternummer: 30799v") worden herkend.** Beide stonden
  handgeschreven op een gescand aanbestedingsformulier en bleven
  leesbaar, hoewel de tekstherkenning het correct had gelezen.
- **Liggende PDF-pagina's werden na het zwarten zonder reden naar een
  afbeelding omgezet.** De ongeschondenheidscontrole vergeleek
  origineel en resultaat in de gedraaide weergave, maar rekende hun
  zwartingszones ongedraaid – op een pagina met rotatievermelding lag
  de eigen zwarting daardoor naast haar zone en gold als schade. Zulke
  pagina's behouden nu hun tekstlaag en vectorafbeelding.
- **Ook rechte pagina's werden af en toe zonder noodzaak naar een
  afbeelding omgezet**, wanneer de tekst achter een plaatshouder met
  een punt opschoof – toegestaan, maar de beeldvergelijking was fijner
  dan haar eigen tolerantie. Ze vergelijkt nu in halve punten en raakt
  haar tolerantie daarmee precies: tot twee punten verschuiving slaat
  niets aan, daarboven alles.
- **Gegevens in ingebedde formulierobjecten bleven staan.** Sommige
  sjablonen leggen briefkop of briefslot als eigen formulier vast dat
  de pagina alleen inbindt. Een treffer daarin werd wel gepland en als
  verwijderd geteld, maar nooit geschreven – de tekst stond verder
  daar, en alleen het rasteren van de hele pagina ving hem op. Nu wordt
  het formulier zelf herschreven; een formulier dat op meerdere
  pagina's ligt, één keer.
- **PDF-pagina's werden naar een afbeelding gerasterd, hoewel niets
  leesbaar was gebleven.** Een zeven pagina's tellende offerte trof
  het op zes pagina's; ze groeide van 73 kB naar 3,3 MB en verloor
  haar lettertype aan een afbeelding. Oorzaak waren spaties die in het
  document meermaals achter elkaar staan, maar door de lezer maar één
  keer worden gemeld: de tekst achter een verwijderd gegeven schoof
  met diens breedte naar rechts, de nacontrole vond het buurwoord in
  het vondstrechthoek en greep naar rasteren. Behouden regelresten
  staan nu weer exact op hun plek; dezelfde offerte wordt zonder één
  enkele gerasterde pagina opgeschoond (76 kB).
- **Sleutelnamen en factuurkoppen golden als personen.** In een
  toegangsbestand werd de naam van de omgevingsvariabele
  („AWS_ACCESS_KEY_ID") vervangen, niet alleen haar waarde; op een
  Engelse factuur viel de kop „Bill to" als voornaam. Een aanduiding in
  hoofdletters met liggende streepjes is nooit een naam, en een woord
  in een regel die als geheel een veldbeschrijving is, ook niet – de
  ontvanger eronder wordt verder gevonden.
- **Het zoeken in het nabewerkingsvenster haperde bij grote
  PDF-pagina's.** Elke letter in het zoekveld liet de pagina opnieuw
  rasteren, hoewel alleen de markering veranderde. De gerenderde
  pagina-afbeelding blijft nu staan, zolang pagina, zoom en weergave
  gelijk zijn – ook het origineel in het vergelijkingsvergrootglas;
  bladeren, zoomen en een nieuwe bestandsstand tekenen zoals voorheen
  vers.
- **Positienummers in offertes golden als IP-adres of telefoonnummer.**
  Een artikelregel zoals „1.3.3.4 … 5-poorts gigabit switch" liet het
  hiërarchienummer een netwerkadres worden, omdat „Port" als technische
  omgeving telde – nu telt het alleen nog als zelfstandig gegeven
  („Port 80"), niet als woorddeel. En „1.3.3.6 216879" (positie- plus
  artikelnummer) wordt niet meer als telefoonnummer gezwart. Echte
  IP-adressen en telefoonnummers in zulke lijsten blijven herkend.
- **Artikelregels in offertes golden als postcode met plaats.** „35252
  DIETZEL SALR" (artikelnummer samen met fabrikant) en „1000 AWG"
  (hoeveelheid samen met geleiderdoorsnede) werden in genummerde
  positieregels als adres gezwart, omdat een woord in hoofdletters
  achter een getal als plaatsnaam in hoofdletters gold. In positielijsten
  geldt dat niet meer; „1080 WIEN" in het adresblok en plaatsen in
  kleine letters blijven overal herkend.
- **De aanvullende naamherkenning zwartte in offertes rolregels en
  kolomkoppen.** „Partij-uurtarief monteur + E-Helfer" gold 49 keer
  als persoon, de kolomkop „Pos. Omschrijving Hoeveelheid EH" 19 keer
  als plaats – een 19 pagina's tellende opdracht werd daardoor
  onleesbaar. Zulke treffers in positieregels vervallen nu als ze zelf
  tekens dragen die geen naam heeft (plus, schuine streep, cijfer,
  afkorting) – ook wanneer de regel eindigt met een bedrag
  („Alternatief markt … - PV/LS AC-voeding 1 290,00"). Namen in
  registers en lijsten – waar het niveau voor bestaat – blijven
  onaangetast.
- **„De klant" maakte in algemene voorwaarden elk „klant" tot naam.**
  Nam de aanvullende naamherkenning het lidwoord in de treffer op, dan
  gold dat als tweedelige naam en beschermde het alle 35 andere plekken
  van hetzelfde woord. Nu wordt het lidwoord afgetrokken, en „de
  klant" vervalt zoals al eerder „van de klant".
- **Beschrijvingen golden als waarde.** „E-mail" werd zeven keer als
  e-mailadres, „Telefoonnummer" en „Faxnummer" als telefoonnummer
  gezwart. Een adres zonder @ en een telefoonnummer zonder cijfers
  tellen niet meer mee.
- **Kolomafkortingen van één letter („L: 154,50", „S: 0,00") golden
  als naam** – 25 keer in een zonne-energie-offerte. Eén enkele letter
  is noch naam noch plaats.
- **PDF-pagina's werden veel te vaak naar een afbeelding omgezet.**
  Twee oorzaken, beide gevonden aan echte offertes: zet een PDF elke
  glyph als eigen opdracht en zit daaronder een spatie-glyph zonder
  tekstteken, dan verschoof de toewijzing vanaf daar met één – van de
  verwijderde waarde bleef de laatste letter staan
  („ŠkodaTopCar**d**"), en de nacontrole rasterde de pagina terecht. En
  een aan het regeleinde afgebroken woord („Privacy-") gold wegens de
  afbreekstreepmarkering van de leesbibliotheek als verschoven. Beide
  opgelost: een voertuigoffertes ging van 4 gerasterde pagina's naar 0,
  een 19 pagina's tellende opdracht van 7 naar 0 – het lettertype
  blijft lettertype, het bestand blijft klein.
- **Twee verdere rasterredenen opgelost:** brengt een document zelf een
  lettertype genaamd „F1" mee, dan werden de plaatshouders boven
  afbeeldingen in dat lettertype gezet en waren onleesbaar – nu krijgt
  het eigen beschrijvingslettertype een vrije naam. En ontbreekt de
  leesbibliotheek een spatie midden in een lange tekstopdracht, dan
  wordt de plek nu ook bij meerbyte-lettertypen bewezen (gelijke code,
  gelijk teken) in plaats van geraden aan het einde – voorheen bleef
  daarbij een letter van de verwijderde waarde staan en de resttekst
  schoof zichtbaar op. Daarbij twee laatste gevallen: een opdracht uit
  tientallen spatie-glyphen liet de toewijzing weglopen (de naam
  erachter bleef staan), en een grote kop met voorbreedte vond haar
  eerste teken niet (de bedrijfsnaam bleef staan). **Van negen echte
  offertes wordt nu geen enkele pagina meer gerasterd** – voorheen
  waren dat 30 van de 90.
- **Bij het rasteren verdwenen afbeeldingen onder een zwart blok.** Moet
  een pagina naar een afbeelding worden omgezet, dan wordt ze uit het
  origineel gerenderd – en dat kent geen beeldopschoning. Tot nu toe
  viel daardoor *elk* beeldvlak van de pagina onder een balk, ook
  onaangetaste. Op een offerte staken adres en twee certificaatlogo's
  in dezelfde briefkopafbeelding; de balk nam de logo's mee. Nu wordt
  de al opgeschoonde afbeelding ingevoegd: het adres erin is gezwart,
  al het overige blijft zichtbaar. Een verwijderde afbeelding laat wit
  papier na in plaats van een zwart vlak.

- **Opgeschoonde scans werden een veelvoud groter dan het origineel.**
  Elke afbeelding waarin iets werd gezwart, ging als ongecomprimeerde
  ruwe afbeelding terug in het bestand – bij een 24 pagina's tellende
  scan groeide het daardoor van 11,8 naar 52,9 MB. Afbeeldingen
  behouden nu de soort waarin ze voorlagen: een foto blijft een foto,
  een faxscan blijft zwart-wit, een kleurloze afbeelding wordt niet als
  kleurafbeelding opgeslagen. Hetzelfde bestand is nu 15,6 MB groot,
  zonder zichtbaar verschil.

- **Gescande PDF-bestanden van kantoorapparatuur kwamen als
  streeppatroon terug.** Zulke scans leggen het lettertype als scherpe
  zwart-witlaag over een grove kleurafbeelding – Canon, Xerox en Kofax
  bouwen hun bestanden zo. Bij het zwarten in de afbeelding werd deze
  laag verkeerd teruggeschreven; het resultaat was onleesbaar. Bij een
  zes pagina's tellende offerte trof dat negen van de zestien
  afbeeldingen. Ze wordt nu correct behandeld, in haar eigen kleur, en
  de gezwarte plekken zijn erin echt weg.

- **„Alle afbeeldingen verwijderen" nam een gescande pagina haar tekst
  af.** De letterlaag van zo'n scan is technisch een afbeelding – ze
  werd meeverwijderd respectievelijk vervaagd, en over bleef een leeg
  blad. Ze blijft nu staan; logo's, stempels en handtekeningen wijken
  verder.

- **De controle op beschadigde PDF-pagina's rastert niet meer wegens een
  minieme verschuiving.** Een bij het opschonen opnieuw verankerd
  tekststuk mag tot twee punten verschuiven; de beeldvergelijking telde
  dat toch als schade en bouwde de pagina als afbeelding opnieuw op –
  daarbij gingen vectorafbeeldingen zoals tabellijnen verloren, en over
  vindplaatsen lag een balk in plaats van een plaatshouder. De
  vergelijking staat nu dezelfde kleine verschuiving toe als de
  woordcontrole; echte schade valt verder op.

- **Het terughalen van veel waarden achter elkaar mislukte op Windows
  niet meer door „Toegang geweigerd".** Wie in een kantoorbestand veel
  paneelregels kort na elkaar terugnam, kon stuiten op een kortstondige
  bestandsvergrendeling van de virusscanner; de vervanging wacht zulke
  vergrendelingen nu even af.

- **De Windows-weg van de opdrachtoverdracht beëindigde de controleur in
  plaats van te controleren.** De levendcontrole van de luisterende
  instantie stuurde op Windows per ongeluk een echte Ctrl+C naar de
  eigen consolegroep; ze vraagt nu zonder signaal bij het systeem na.

- **Meerwoordige veldbeschrijvingen werkten niet, maar hun fragmenten
  wel.** „Date of birth", „Bank account", „Cuenta bancaria" en „Numero
  de cliente" stonden in de beschrijvingslijst, werden daar echter in
  losse woorden opgesplitst en troffen daarom nooit; over bleven
  woorddelen zoals „de" en „of", die sindsdien als beschrijving
  golden – „de" is echter een naamonderdeel („Anna de Vries"). Beide
  zijn opgelost: de uitdrukkingen werken nu als geheel, de fragmenten
  zijn weg.

- **Duitse groetformules met „ß" werden ondanks vermelding als
  persoonsnaam behandeld.** Onder „Herzliche Grüße" of „Mit
  freundlichen Grüßen" stond in het resultaat een plaatshouder, hoewel
  beide uitdrukkingen van oudsher in de tegenlijst staan. Oorzaak was
  een schrijfwijze die bij de vergelijking nooit aankwam; getroffen
  waren acht items over vijf lijsten. Ze werken nu allemaal.

- **„John Staff" bleef onvervangen.** Een achternaam die tegelijk een
  Engelse kolomkop is, werd door het beschrijvingsfilter meeverworpen.
  De kop blijft verder onaangetast, de naam eronder wordt weer
  vervangen.

- **Waarden uit beschreven formuliervelden blijven in het AI-niveau
  beschermd.** De lokale scheidsrechter van het AI-niveau kreeg tot nu
  toe ook treffers ter beoordeling voorgelegd wier betekenis al de
  veldbeschrijving bewees („Geboortedatum:" boven de waarde) – en mocht
  ze verwerpen. Zulke structureel bewezen waarden worden hem niet meer
  voorgelegd. Het toewijzingsbestand noemt bij elke vervanging nu
  bovendien de herkenningsweg („bewijs").

- **Een PDF-pagina waarvan de behouden tekst bij het opschonen schade
  opliep, wordt nu herkend en als afbeelding van het origineel opnieuw
  opgebouwd.** Bij sommige makerslettertypen konden behouden tekstplekken
  na de opschoning als zwarte blokken verschijnen of woorden aan
  elkaar schuiven, hoewel alle te verwijderen gegevens correct waren
  verwijderd. Maskuro vergelijkt het resultaat nu woord voor woord en
  beeldpunt voor beeldpunt met het origineel; een beschadigde pagina
  wordt door haar schone afbeelding vervangen — met zwartbalken over de
  vindplaatsen, gezwarte beeldgebieden en doorzoekbare tekst. De pagina
  blijft leesbaar, de verwijdering betrouwbaar.

### Gewijzigd

- **In de vertaalde interfaces heet elk vakbegrip nu overal hetzelfde.**
  Voor een en hetzelfde Duitse woord stonden afhankelijk van het
  venster twee of drie vertalingen naast elkaar: het controlelogboek
  heette in het Noors deels „Revisjonslogg", deels „Kontrollogg", het
  gratis niveau deels „Gratisnivå", deels „Gratisversjon" – en
  vergelijkbaar in een dozijn andere talen. Wie een instelling zocht,
  vond haar in het volgende venster onder een andere naam.
  Geüniformeerd werd naar het woord dat de interface toch al het
  vaakst voert.

  Daarbij kwamen plekken aan het licht waar één woord voor twee
  **verschillende** dingen stond: Frans, Grieks en Koreaans gebruikten
  voor „zwarten" en „maskeren" dezelfde uitdrukking – dus juist waar
  het programma het verschil uitlegt („Zwarten verwijdert zonder
  vervanging, maskeren behoudt de vorm"). Beide zijn nu uit elkaar
  gehouden. Voor Zweeds staat deze beslissing nog uit: daar heet het
  zwarten „maskera" – hetzelfde woord als het maskeren.

- **De vraag naar het gebruikstype bij de eerste start is vervallen.**
  Kort na de start kwam een venster („Privé of zakelijk?"), en in de
  instellingen stond daarbij een regel. Beide bestaan niet meer –
  zonder vervanging. Een aanduiding waar niets aan hangt, geeft
  verkeerd aan wie de verkeerde licentie wil, en wie eerlijk is, heeft
  haar niet nodig; ze kostte iedereen een klik op een moment waarop
  niemand aan licentietypen denkt. Welke licentie de juiste is, staat
  waar ze wordt beslist: op de prijspagina, in de kassa en in de hulp.
  Huizen die Maskuro centraal uitrollen, geven het gebruikstype verder
  op via het voorschriftenbestand.

- **De aanwijzingen over het licentietype noemen het geval waar het om
  gaat.** De privélicentie geldt uitsluitend voor privégebruik; elk
  beroepsmatig of zakelijk werk heeft de bedrijfslicentie nodig – ook
  als zelfstandige zonder personeel. Dat stond zo in de
  licentievoorwaarden, maar noch in het programma noch in de hulp:
  daar was altijd alleen sprake van het bedrijfsdomein, en dat vangt
  juist dit geval niet: de computer van een zelfstandige behoort tot
  geen enkel domein. De aanwijzing bij het inlezen van een
  privélicentie zegt het nu, evenals het licentiehoofdstuk van de
  handleiding en de veelgestelde vragen, die daarvoor een eigen item
  hebben gekregen. Geblokkeerd wordt verder niets.

- **De nog niet uitgeleverde wegen liggen nu bij elkaar.** De
  instellingen hebben een pagina „Ontwikkelaar" gekregen; daar staan de
  maximale herkenning (AI) samen met haar tegencontrole, de
  woordenlijstencatalogus en de mapbewaking. Alle drie zijn gebouwd,
  maar in de praktijk niet beproefd – ze zijn daarom alleen met een
  ontwikkelaarslicentie zichtbaar, en wel overal tegelijk: de pagina,
  de menu-items en het effect in de run hangen aan dezelfde beslissing.
  Zonder deze licentie blijft een eerder ingeschakeld AI-niveau zonder
  effect; haar instelling wordt niet gewist en geldt weer zodra de weg
  wordt uitgeleverd.

### Verbeterd

- **„Wat wordt gezocht" toont drie verdere lijsten uit de
  naamherkenning.** De aanheffen waarna het volgende woord als naam
  wordt gelezen; de titels en rollen die daarna nog **niet** de naam
  zijn („De heer burgemeester Huber"); en de tachtig meertalige
  beschrijvingen waaraan dossiernummers, zaak- en gevalsnummers worden
  herkend. Alle drie werkten altijd al, waren in het overzicht echter
  niet te zien.

- **„Wat wordt gezocht" toont twee tot nu toe ontbrekende
  woordenlijsten.** De aanheffen en titels die een ervoor staand woord
  tot naam maken („De heer", „Mevrouw", „Dr."), en de afkortingen van
  de normeringsorganisaties waaraan Maskuro een normverwijzing zoals
  „ÖNORM B 2110" onderscheidt van een persoon. Beide beïnvloeden de
  herkenning van oudsher, stonden echter niet in het overzicht.

- **Positielijsten, inhoudsopgaven, uitrustingsopsommingen en
  normverwijzingen blijven leesbaar.** De herkenning ziet nu de
  bouwvorm van de regel: een geraden naam in een hiërarchieregel
  („1.3.1 Energie-ondergrondse kabel 1kV"), een registerregel met
  aanloopstippen, een opsomming („- draadloos laden met magneetring"),
  boven een hoeveelheids-/prijsregel, in een kolomkop of achter
  „middels" is een zaakbegrip en wordt niet meer vervangen. Echte namen
  blijven beschermd – door aanhef, veldbeschrijving en het bewijs
  elders in het document; aan het meetcorpus verloor geen enkel gegeven
  haar bescherming. In het zakelijke corpus dalen de valse alarmen
  daarmee van 25 naar 6.

- **Koppen, formulierbeschrijvingen en groetformules worden minder vaak
  voor namen gehouden – in het Duits en Engels.** De woordenlijsten
  waarmee Maskuro zaakwoorden van persoonsnamen onderscheidt, zijn
  aanzienlijk gegroeid: beschrijvingen uit facturen, formulieren en
  overheidspost („Dossiernummer", „Betalingskenmerk", „Kostenplaats",
  „Sort code", „Subtotal"), sectiekoppen van sollicitaties en
  verslagen („LOOPBAAN", „KWALIFICATIES", „SUMMARY", „REFERENCES"),
  Duitse en Engelse documenttypes („Orderbevestiging", „Notulen",
  „Timesheet", „Agreement") evenals gebiedende wijs uit handleidingen
  („Verstuur…", „Select…"). De Engelse kant was daarbij tot nu toe
  opvallend dun bezet.

- **Beschreven velden verraden nu ook dan wat erin staat wanneer de
  beschrijving samengesteld is.** „Afleveradres", „Factuuradres",
  „Behandelaar", „Rekeninghouder", „Contact person" en „Billing
  address" wijzen de waarde ernaast of eronder nu dezelfde soort toe
  als het eenvoudige „Adres" of „Naam" – in het ingevulde formulier met
  vakjes is dat het verschil tussen gevonden en over het hoofd gezien.

- **In het nabewerkingsvenster bladert het muiswiel aan de paginarand
  verder.** Wie aan het einde van een pagina blijft rollen, komt boven
  op de volgende terecht; wie aan het begin terugrolt, onderaan de
  vorige – een document is daarmee van voor naar achter door te rollen
  zonder de paginaknoppen aan te raken. Het toetsenbord (Page↑/Page↓)
  kon dat al; een korte adempauze tussen twee paginawissels voorkomt
  dat de nasleep van een trackpad dwars door het halve document draagt.

- **De paginaminiaturen in het nabewerkingsvenster zitten gecentreerd in
  het vak.** Tot nu toe kleefden ze aan de linkerrand, en bij het
  breder trekken groeide alleen de lege rand rechts.

- **De symboolbalk van het nabewerkingsvenster toont haar groepen.** De
  scheidingsstrepen hebben nu ruimte en kleur, „Zoeken" en „Op alle
  pagina's toepassen" staan als eigen groepen naast de werktuigen, en
  „Toepassen" verschijnt alleen nog bij documenttypes waarin het iets
  kan bewerkstelligen. Elk item in balk en menu's draagt nu een
  afbeelding: „Tekstregels" en het vergelijkingsvergrootglas hebben
  eigen symbolen gekregen (het vergrootglas deelde tot nu toe het
  zijne met „Voor/na"), plus zoom, hele pagina, paginabreedte, draaien,
  bladeren en de toetsencombinaties. „Met systeemprogramma openen"
  staat nu ook in de balk naast afdrukken – de weg van het voltooide
  resultaat naar het vertrouwde programma is één klik, geen menugang.

- **Bij de klembordopschoning staat weer bij dat het nagekeken moet
  worden.** In de instellingen staat de aanwijzing blijvend naast de
  schakelaar: Maskuro kan persoonsgegevens over het hoofd zien of
  gegevens verkeerd behandelen, de geplakte tekst is vóór de
  doorgifte na te kijken. Bij het inschakelen noemt de melding het
  bovendien, en het wordt in het uitvoergebied vermeld – ook wanneer
  geen symbool in het infogebied draait. Bij elke afzonderlijke
  kopieerhandeling verschijnt het bewust niet: een aanwijzing die
  vijftig keer per dag zou komen, wordt na de derde keer niet meer
  gelezen.

## 0.10.36-beta.1 – 20 augustus 2026

### Verbeterd

- **Technische zakelijke documenten worden niet meer stukgezwart.** Vier
  herkenningsremmen, gewonnen uit elf echte offertes en opdrachten:
  Gliederingsnummers („1.3.1.1") gelden niet meer als IP-adressen,
  normverwijzingen („ÖNORM EN 62446") en kenmerkcodes niet meer als
  postcode of telefoonnummer, en rolwoorden achter lidwoorden („de
  klant", „van de opdrachtgever") niet meer als namen – in de algemene
  voorwaarden van een echte offerte zijn daarmee alle 46 rolwoorden weer
  leesbaar in plaats van gezwart. Adressen met landcode („A 3390 Melk",
  „D-94032 Passau") worden nu volledig verwijderd, in plaats van de
  postcode als wees te laten staan.

- **Woordenlijsten zijn nu volledig inzichtelijk.** Onder „Help →
  Woordenlijsten …" zijn de plaatselijk gebruikte herkennings- en
  tegencontrolelijsten samen met taal, doel, bron en inhoud te
  doorzoeken. Daartoe behoren ook Wordfreq-, medische, persoonlijke en
  centraal beheerde lijsten evenals de voorraden voor verzonnen
  vervangwaarden. Het handboek beschrijft de catalogus in een eigen
  hoofdstuk.

- **Voltooide bestandsregels tonen de gebruikte herkenningstaal.** Achter
  „gereed" staat nu bijvoorbeeld „Duits" of „Engels", zodat een
  ongeschikte automatische taalkeuze meteen opvalt. Moest een andere
  geïnstalleerde taal inspringen, dan toont een pijl beide talen.

- **Het nieuwe vergelijkingsvergrootglas toont bij het doorlezen meteen de
  bijbehorende plek in het origineel.** Het vergrote origineeluitsnede
  volgt de muisaanwijzer boven het nog steeds bewerkbare resultaat; bij
  tekst volgt het de alinea. Het vergrootglas kan aan de vensterrand
  worden gebruikt of als eigen, maximaliseerbaar venster worden
  losgetrokken. De zoom is direct tussen 50 en 300 procent instelbaar en
  wordt net als het inschakelen onthouden. „Terugzetten" brengt ook een
  gemaximaliseerd of ongunstig aangedokt vergrootglas weer links naar een
  bedienbare grootte. Vervangen originele waarden zijn in het
  vergrootglas geel gemarkeerd, zodat de betrokken woorden bij het lezen
  meteen opvallen. Eenmaal geactiveerd, opent het zich bij toekomstige
  geschikte documenten weer – ook na een herstart van het programma. De
  bestaande voor/na-schakelaar blijft in het weergavemenu behouden. Het
  handboek beschrijft het in een eigen hoofdstuk.

- **Open source- en modelbewijzen zijn nu releasenauwkeurig.** De
  pakketbouw genereert een machineleesbare componentenlijst inclusief
  hashes van de bijgevoegde licentieteksten. MPL-bronnen, modelherkomst,
  vaste revisies, wijzigingen en SHA-256 worden apart bewezen; nageladen
  modellen krijgen hun herkomstbewijs direct in de modelmap. Beweeglijke
  Tesseract- en spaCy-bronlijsten zijn vast vastgepind. Verkoopartefacten
  blijven geblokkeerd totdat alle bronnen en modelbijlagen gepubliceerd en
  gecontroleerd zijn.

- **Het plaatselijke wordfreq-databestand is volledig licentie-onderbouwd.**
  De pakketbouw controleert versie 3.1.1, 39 ongewijzigde kleine lijsten
  inclusief CJK en de Chinese tekenkaart tegen aantal, grootte en
  manifest-controlesom. Apache-2.0-codevermelding, volledige
  CC-BY-SA-4.0-licentie, attributie, databronnen en de weggelaten grote,
  Jieba- en niet-ondersteunde lijsten zijn in het pakket gedocumenteerd.

- **Veelvoorkomende zinswoorden worden minder vaak per ongeluk gezwart.**
  Een plaatselijk frequentiewoordenboek dient als extra tegencontrole
  wanneer de naamherkenning een werkwoord, voornaamwoord, lidwoord of
  voorzetsel voor een persoon houdt. Het woordenboek beslist nooit
  alleen: zelfstandige naamwoorden, meerdelige namen en namen in velden,
  lijsten en na aanheffen blijven beschermd. Chinees, Japans en Koreaans
  gebruiken uitsluitend exacte tokengrenzen van hun reeds aanwezige
  taalmodellen; voor niet-aanwezige talen wordt geen vermeend gelijkende
  woordenboektaal ingezet. Daarvoor wordt geen documenttekst naar het
  internet verzonden.

- **Technische product- en uitrustingsbegrippen worden niet meer zo
  gemakkelijk voor namen of plaatsen gehouden.** De plaatselijke
  tegencontrole verbindt nu frequentie, woordsoort, technische
  woordvorming en vakgebieden. Daardoor blijven bijvoorbeeld
  „Travel-Assistent", „Family-Bonus", „WLTP-waarde", „Easy-Start" en
  samengestelde nummer-, houder- of rembegrippen in het document. Engelse
  onderdelen worden ook in Duitse vaktekst plaatselijk opgezocht; echte
  eigennamen, aanheffen en persoons- en plaatsvelden behouden voorrang.
  Bovendien geldt een „2-jarige fabrieksgarantie" niet meer als
  leeftijd.

- **De Qt-/PySide-licentierechten zijn nu volledig navolgbaar.** Het
  programmapakket bevat aanvullend de volledige GPL-3.0-tekst, exacte
  Qt-versies, een broncodeaanbod en een Duits/Engelse handleiding voor het
  vervangen van de dynamische bibliotheken inclusief lokale
  macOS-hersignering. Een verkoopbouw wordt geblokkeerd zolang de exacte
  bronarchieven van de uitgeleverde versie niet op de eigen
  broncodepagina beschikbaar zijn.

- **Licentie en actualiseringsstand zeggen nu voor elk niveau eenduidig
  wat geldt.** In het licentievenster en bij de actualiseringsinstellingen
  staat of actualiseringen inbegrepen zijn, tot welke dag ze reiken en of
  de lopende versie blijvend bruikbaar blijft. Privélicenties installeren
  na de peildatum geen later verschenen versie meer; ook een nieuw
  gedownload installatieprogramma herkent aan zijn vast ingebouwde
  verschijningsdatum of de ingevoerde sleutel het omvat. De laatste
  gedekte privéversie blijft blijvend bruikbaar. Eindigt daarentegen een
  bedrijfsabonnement, dan eindigen gebruik en actualiseringen; testperiode
  en gratis niveau openen zich niet als omweg.

- **Persoonlijke permanente licenties vinden nu ook na een herinstallatie
  de juiste programmastand.** Een gesigneerde versiecatalogus voert alle
  stabiele versies en hun pakketten. Is het laatste door de aankoop
  omvatte installatieprogramma niet meer verkrijgbaar, dan mag in plaats
  daarvan automatisch precies de eerstvolgende hogere beschikbare
  stabiele versie worden gebruikt – nooit een bèta of nightly. Bij een te
  nieuwe installatie kan de klant de toegestane stand installeren of naar
  de koopagina wisselen voor een nieuwe actualiseringsperiode; een stap
  terug gebeurt niet stilzwijgend. Dat geldt ook voor beheerde
  MSI-installaties.

- **De automatische gezichtszwarting is nu eenduidig beschreven.**
  Programmahulp en privacytekst noemen de functie „gezichtsgebieden
  herkennen en onherkenbaar maken" en grenzen deze af van identificatie,
  herkenning, gezichtsvergelijking, biometrische sjablonen en
  personen- of gezichtsdatabanken. Ze wijzen bovendien duidelijk erop dat
  de volledig lokale herkenning gebieden kan missen of ten onrechte kan
  markeren en het resultaat daarom visueel moet worden gecontroleerd.
  Ook bij een afzonderlijk opgeschoond beeldbestand noemt het resultaatverslag
  nu herkende en gepixeleerde gezichtsgebieden; een ontbrekende
  tekstherkenning wordt daarbij niet meer ten onrechte als volledig
  ongewijzigd bestand beschreven.

## 0.10.36-alpha.20260820 – 20 augustus 2026

### Opgelost

- **Geanonimiseerde gegevens kunnen nu onafhankelijk van de volgorde
  volledig worden teruggehaald.** De eerdere terughaling zocht de waarde
  via zichtbare tekstankers. In dichte tabellen, direct naast elkaar
  staande plaatshouders en onzichtbare Office-/mailopslag ontbraken deze
  ankers; soms werd een begrip daardoor pas terughaalbaar nadat een
  andere klare tekst toevallig een nieuw anker had geschapen. Nu worden
  resultaat en origineel per echte formaatdrager met de volledige
  toewijzing vergeleken en worden alleen de bezette plekken van de
  gekozen waarde geschreven.

- **Namen, mailadressen, nummers en eigen controlebegrippen blijven ook bij
  overlappende herkenning eenduidig bedienbaar.** Is dezelfde klare
  waarde aan twee soorten toegewezen, dan beslist de daadwerkelijk op de
  vindplaats staande plaatshouder samen met de aangeklikte
  zijbalkregel. Een niet-bezet waarde/plaatshouderpaar blijft verder
  veilig geblokkeerd.

- **Mail-bijzondere gevallen laten geen verborgen plaatshouders meer
  achter.** Dat geldt voor MIME-gecodeerde onderwerpen, tekstbijlagen en
  via HTML-opmaak gescheiden namen in EML en MSG. UTF-8-HTML zonder
  eigen tekensetopgave wordt in Outlook-bestanden bovendien niet meer bij
  elke bewerkingsstap naar mojibake omgecodeerd; oudere, al zo
  geschreven resultaten blijven terughaalbaar.

### Verbeterd

- **Een nieuwe vrijgavematrix bedient elke anonieme zijbalkregel
  afzonderlijk en bewust achterwaarts.** Ze controleert alle 14 tekst-,
  Office-, web- en mailformaten evenals PDF, aansluitend ook formules,
  attributen, relaties, opmerkingen, mailkoppen, bijlagen en interne
  nevenopslag. De volledige macOS-run omvat nu 149/149 groene
  controlescripts.

## 0.10.35-alpha.20260820 – 20 augustus 2026

### Verbeterd

- **Taalmetingen vergelijken nu echt gelijk met gelijk.** Het
  regelmatige meetcorpus bevat dezelfde 14 documentgevallen met dezelfde
  zeven tekst- en vier beeldtaken in het Duits en Engels. Een volledige
  run herhaalt exact deze matrix voor alle twaalf aanwezige
  corpustalen. Formulieren, tabellen, chats en andere nog niet volledig
  vertaalde structuurproeven blijven behouden, maar worden apart
  weergegeven en niet meer in taalquota gemengd.

- **De volledige run schrijft voor elke taal een eigen meetrapport.**
  Zonder taalschakelaar worden bewust Duits en Engels gecontroleerd;
  `--alle-sprachen` vraagt het volledige twaalftalencorpus aan en breekt
  af vóór het eerste document als een taal of geval ontbreekt.
  Gelijknamige resultaten staan in aparte taalmappen. Het totaalrapport
  noemt naast het gewogen vondstpercentage ook het ongewogen gemiddelde
  van de taalpercentages.

- **De open taalvergelijking toont nu ook zijn werkelijke grens.** In de
  regelmatige run met tekstherkenning verwijderen Duits en Engels
  218/218 bekende gegevens zonder vals alarm. De volledige test met
  tekstherkenning en hoog-niveau verwijdert 1.255/1.308 gegevens bij 17
  valse alarmen; elf talen bereiken 100 procent, Hindi 51 procent.
  Eerdere volledige percentages berustten op ongelijke document- en
  doelhoeveelheden en zijn met de nieuwe matrix niet vergelijkbaar.

## 0.10.34-alpha.20260819 – 19 augustus 2026

### Opgelost

- **Meermaals voorkomende namen blijven na een enkele terughaling in de
  zijbalk bereikbaar.** Tot nu toe verdween de hele naamregel al na de
  eerste teruggehaalde `[NAME]`-plek. Andere plekken van dezelfde naam
  bleven daardoor als plaatshouder staan en werden soms zelfs geblokkeerd,
  totdat andere namen waren teruggehaald. Nu verdwijnt de regel pas na
  de laatste plek; al teruggehaalde klare tekst wordt toch niet opnieuw
  automatisch geanonimiseerd. Dat geldt ook voor een gedeeltelijk
  geslaagde verzamelde terughaling en voor het kaderwerktuig in PDF's.

- **„Vervanging ongedaan maken" werkt ook vanuit de Office-paginaweergave.**
  De zichtbare pagina is daar slechts een vluchtig PDF-voorbeeld;
  gewijzigd wordt nu correct het Word-, tabel- of presentatiedocument
  eronder en aansluitend het voorbeeld vernieuwd.

- **De terughaling haalt nu ook de verborgen tegenhangers van een waarde
  volledig terug.** In Word-, OpenDocument-, Excel- en
  PowerPoint-bestanden kunnen dezelfde gegevens bovendien in formules,
  opmerkingen, diagrammen, veldwaarden, alternatieve teksten en
  verwijzingsdoelen staan; HTML, EML en MSG voeren ze bovendien in
  attributen, JSON, berichtkoppen en bijlagen. Tot nu toe bleef daar
  afhankelijk van het formaat een deel als plaatshouder staan. Nu kan
  elke in het trefgebied aangeboden gegeven onafhankelijk en in
  willekeurige volgorde worden teruggehaald. Bewust verwijderde
  metagegevens, wijzigingsgeschiedenissen en transportkoppen blijven om
  veiligheidsredenen verwijderd.

- **Bij het terughalen uit afbeeldingen blijft geen zwarte randlijn meer
  staan.** Rechter- en onderrand van een kader werden bij het kopiëren
  uit het origineel elk één beeldpunt te krap uitgelegd. De coördinaten
  komen nu overeen met de zwarting.

### Verbeterd

- **De vrijgavecontrole stuurt nu elk van de 22 ondersteunde
  bestandsextensies door een volledige rondreis.** Inhoudsrijke bestanden
  worden opgeschoond, alle aangeboden waarden hersteld en aansluitend diep
  gecontroleerd. Daarbij komen echte zijbalkbediening, pixelnauwkeurige
  beeldvergelijkingen en een zichtbare LibreOffice-rendering van alle
  zeven kantoorformaten. De kleine regressietests blijven bestaan waar ze
  een eigen fout- of veiligheidsgeval afdekken; een aantoonbaar dubbele
  HTML-controle en de test van de verwijderde zwart-witmodus zijn
  vervallen.

- **Het volledige meetcorpus van deze versie ligt klaar om na te meten.**
  Het pakket bevat 294 synthetische documenten in twaalf formaten en
  twaalf talen, 2.564 bekende gegevens, vier machineleesbare
  doellijsten en een handleiding. De download op de kwaliteitspagina
  gebruikt een inhoudsafhankelijke bestandsnaam, zodat browsers niet per
  ongeluk een oudere versie uit de cache leveren.

## 0.10.33-alpha.20260819 – 19 augustus 2026

### Nieuw

- **Ook in beeldbestanden kunnen afzonderlijke plekken nu uit het
  origineel worden teruggehaald.** Het kaderwerktuig „Origineel
  terughalen" kopieert de beeldpunten op dezelfde positie terug uit het
  onaangetaste bronbestand. De weg blijft geblokkeerd als de bron
  ontbreekt of andere beeldafmetingen heeft; daardoor kan geen inhoud
  uit een verschoven plek worden ingevoegd.

### Verbeterd

- **Handmatige zwartbalken klikken standaard vast op tekstregels.** Een
  sleep over meerdere regels genereert per regel een gelijkmatig hoge
  balk en laat de witruimte ertussen vrij. Voor handtekeningen,
  grafieken en andere bijzondere gevallen schakelt „Vrij kader" terug
  naar de zelf gekozen hoogte.

- **De editor legt de volgende handeling direct boven het document uit.**
  De aanwijzing wisselt met documenttype en werktuig en zegt of een
  woordklik, tekstselectie of kader wordt verwacht. Bovendien tonen
  werktuig, muisaanwijzer en live-voorbeeld al vóór het loslaten wat er
  gaat gebeuren.

### Verwijderd

- **De foutgevoelige zwart-wituitvoer is verwijderd.** Bij sommige PDF's
  bleven onzichtbare tekstvelden ten opzichte van de gerasterde pagina
  verschoven staan; de schijnbare bestandsverkleining was dit
  veiligheids- en weergaverisico niet waard. Normale PDF-opschoning en
  het gerichte rasteren van problematische pagina's blijven behouden.

## 0.10.32-alpha.20260819 – 19 augustus 2026

### Nieuw

- **De mapbewaking draait nu echt op de achtergrond.** Ingang, uitgang en
  regels staan op een eigen pagina onder „Instellingen". Gestart en
  gestopt wordt ze via het Maskuro-symbool in de taak- of menubalk; het
  item verschijnt alleen met de daarvoor vrijgeschakelde licentie. Het
  instellingenvenster kan daarna worden gesloten en het hoofdvenster in
  het symbool worden gelegd, zonder de bewaking te beëindigen.

- **De nabewerkingseditor heeft nu een blijvende leermodus-schakelaar.**
  Deze staat in het trefgebied en in het menu „Werktuigen". Wordt hij
  uitgeschakeld, dan verschijnen noch bij het terughalen noch na
  handmatige correcties vragen over het aanmaken van eigen regels.
  Maskuro onthoudt de keuze voor alle toekomstig geopende documenten; de
  terughaling zelf functioneert ongewijzigd.

### Opgelost

- **Het grote extra model kan weer worden geladen.** De publieke opslag
  wees Pythons algemene standaardkenmerk met 403 af. Modelophalingen
  gebruiken nu dezelfde aangewezen Maskuro-netweg als de overige eigen
  diensten; het bijna 596 MB grote bestand en zijn controlesom blijven
  ongewijzigd.

- **Een gemaximaliseerd vergelijkingsvergrootglas blijft bij het
  aandokken niet meer als smalle balk aan de bovenrand hangen.** Vóór
  het aandokken wordt zijn vrije vensterstatus genormaliseerd. Een
  opgeslagen gemaximaliseerde status wordt bij het volgende openen
  eveneens naar een veranderbare grootte teruggebracht.

- **Een verzamelde terughaling haalt in tabellen en andere
  tekstformaten nu echt alle geselecteerde waarden terug.** Bij
  geanonimiseerde plaatshouders zoals `[EMAIL]` schreef Maskuro de
  waarden tot nu toe na elkaar. Zodra de eerste was vervangen, schoven
  de nummers van alle resterende vindplaatsen op, maar het al berekende
  plan wees nog naar de oude nummers. Daardoor kwam maar een deel van
  de selectie terug. Nu worden alle gekozen waarden van dezelfde
  plaatshouder gezamenlijk en met stabiele vindplaatsnummers geschreven.
  Wordt een plek pas door een andere teruggehaalde waarde eenduidig, dan
  controleert Maskuro haar in dezelfde stap opnieuw – de volgorde van de
  selectie speelt daarmee geen rol meer.

- **„Vervanging ongedaan maken" laat in PDF's geen geselecteerde
  waarden meer weg.** Stond een plaatshouder heel dicht achter een
  ander woord, of hing er in het origineel een komma direct aan de
  waarde, dan kon de positiecontrole het naburige woord respectievelijk
  leesteken ten onrechte aan de waarde toerekenen. Bij het gezamenlijk
  terughalen bleven dan afzonderlijke plaatshouders en trefregels
  staan. De controle richt zich nu op het daadwerkelijke woordbegin en
  houdt ook rekening met een afwijkende paginarotatie tussen origineel
  en resultaat.

- **Teruggehaalde PDF-tekst behoudt nu zijn oorspronkelijke grootte.**
  Tot nu toe diende de al kleiner gezette plaatshouder als maatstaf;
  bovendien gold ook voor de originele tekst de voor plaatshouders
  bedoelde bovengrens van 11 punt. Nu worden origineel kader en
  originele lettergrootte uit het bronbestand overgenomen – bij het
  kaderwerktuig net zo goed als bij het terughalen uit het trefpaneel.

### Verbeterd

- **De controleaanwijzing benoemt het restrisico nu duidelijker.** Hij
  zegt uitdrukkelijk dat Maskuro gegevens kan missen of verkeerd kan
  behandelen, en vraagt vóór elke publicatie of doorgifte om volledige
  controle en zo nodig handmatige correctie. Dat geldt ook voor tekst
  uit het klembord en is in alle 17 vertalingen volledig doorgevoerd.

- **Het controlelogboek start nu ook binnen zijn regels zonder
  gebruikersnaam.** Het logboek zelf blijft uitgeschakeld totdat een
  bedrijf het bewust activeert. Daarna staat zonder extra
  bedrijfsvoorschrift noch in een regel noch in de naam van een
  centraal maandbestand een gebruikersnaam; daar dient een niet te
  raden, alleen uit het toevallige plaatselijke profielgeheim afgeleide
  pseudoniem voor veilige scheiding. De licentiedialoog beveelt de
  activering niet meer aan, veronderstelt „Zonder logboek" en wijst
  vooraf op ondernemingsraad, personeelsvertegenwoordiging en
  gegevensbescherming.

- **Vervangen benoemt nu wat het vervangt.** Een gemarkeerde naam wordt
  `[NAAM_3]`, een plaats `[PLAATS_1]`, een telefoonnummer
  `[TELEFOON_2]` – in plaats van tot nu toe alles `[BEGRIP_n]`. De soort
  wordt bij de klik herkend; is die niet eenduidig – een gewoon woord,
  of een naam *en* een plaats in een selectie –, dan blijft het bij het
  algemene begrip. Een plaatshouder die een soort beweert die niet
  klopt, zou slechter zijn dan een die er geen noemt.

- **De werktuigen in het nabewerkingsvenster hebben nu een toets.**
  **Z** zwart maakt, **V** vervangt, **T** haalt het origineel terug,
  **P** pixeleert. In de tekstweergave werken ze meteen op de markering,
  op de paginaweergave kiezen ze het werktuig. **De letters volgen de
  taal** waarin u het programma bedient, want een geheugensteun helpt
  alleen in de eigen taal. De toets staat bij de knop. Wie net in de
  zoekbalk typt, schrijft gewoon door – daar grijpen ze niet.

- **Het programma meldt eenmaal per dag in welke staat het draait –
  zonder enig kenmerk.** Daarmee tellen we hoeveel installaties worden
  gebruikt en hoe zich dat verdeelt over testperiode, gratis niveau en
  licentie. Uitgaand gaan staat, besturingssysteem, versie, kanaal,
  land, taal, omgeving en herkenningsniveau – **niets over uw documenten
  en niets waaraan uw computer te herkennen zou zijn**. Twee meldingen
  van u zien er voor ons uit als meldingen van twee verschillende
  mensen; een enkel spoor is daaruit niet te volgen. Wat precies wordt
  verzonden en hoe het kan worden uitgeschakeld, staat in de
  privacytekst onder punt 5.

- **Scheef ingescande pagina's staan nu vanzelf goed rechtop.** Een
  blad dat scheef werd gescand zonder dit te vermelden, herkent de
  nabewerking aan het tekstverloop en richt de weergave op. Waar dat
  niet lukt – bij een pure scan zonder leesbare tekst –, draaien twee
  nieuwe items in het menu „Weergave" met de hand (Ctrl+Shift+L en
  Ctrl+Shift+R). Alleen de weergave wordt gedraaid: aan het bestand
  verandert daarbij niets, en zwarten treft nog steeds precies de plek
  waarop wordt geklikt.

- **De lokale uitvoer voert zijn licenties nu volledig en zichtbaar
  mee.** De bouw bepaalt de daadwerkelijk gebundelde Python-pakketten,
  legt hun licentieteksten samen met versieoverzicht onder `lizenzen`
  vast en breekt bij een gat af. Ook Qt, Tesseract en het gezichtsmodel
  hebben hun benodigde teksten; de voorwaarden voor Maskuro zelf zijn
  als licentieovereenkomst bijgevoegd.

- **Men ziet nu in welke plaatshouder de cursor staat.** Wie in een
  plaatshouder klikt, ziet hem helemaal oplichten – inclusief haakjes
  en nummer. De knop „Selectie terughalen" werkte al eerder bij een
  loutere klik; alleen was niet te zien welk merk hij trof. Het
  oplichten blijft ook staan wanneer de muis naar de knop gaat.

- **De muisaanwijzer zegt nu welk werktuig is gekozen.** Vier
  werktuigen delen dezelfde ruimte en hetzelfde gebaar; tot nu toe zag
  elk er hetzelfde uit. Draadkruis betekent zwarten, gesloten hand
  vervangen, open hand terughalen.

- **Een geprepareerd Office-document wordt nu door het programma zelf
  afgewezen.** Een Word-, Excel- of OpenDocument-bestand kan
  instructies meebrengen die bij het openen een vreemd bestand van uw
  computer in zijn tekst halen of het geheugen laten vollopen. Beide
  werden ook tot nu toe afgewezen – maar door de ingebouwde
  XML-bibliotheek, niet door Maskuro. Nu beslist het programma het zelf,
  ongeacht welke versie van deze bibliotheek in het pakket zit. Voor
  gewone documenten verandert er niets.

### Opgelost

- **Het trefpaneel verwijdert nu gezwarte plaatshouders.** Werd
  bijvoorbeeld `[NAAM_1]` in het nabewerkingsvenster gezwart, dan bleef
  zijn waarderegel tot nu toe rechts staan, hoewel er in het document
  geen zo'n plek meer was. De regel vervalt nu bij de laatste
  vindplaats; komt dezelfde plaatshouder nog op een andere plek voor,
  dan blijft ze behouden.

- **Bij het terughalen op een gedraaide pagina blijft het naburige
  woord nu staan.** De zwartbalk steekt bewust een beetje over de
  tekst uit; al deze smalle rand kon tot nu toe een aangrenzend woord
  zoals „in" meenemen. Nu telt alleen nog een duidelijke overlapping,
  niet het raken van de rand.

- **Een tweede vervanging in dezelfde regel nam de bijzin mee.** Wie
  „Behandeling Quaxi Blubbo neemt over" tweemaal achter elkaar
  verving, kreeg „Behandeling [PLAATS_1] [PLAATS_2]" – het woord
  daarachter was zonder vervanging weg, zonder enige melding. Oorzaak
  was de plaatshouder ernaast: de rest van de regel begint na de eerste
  vervanging met een spatie, en de zoektocht naar zijn tekstplek greep
  de sluithaak van de buur mee. Daarna was alles één teken verschoven.
  Getroffen was elke regel waarin tweemaal werd vervangen of gezwart –
  ook bij het terughalen ernaast.

- **Vervangen zwart nu niet meer wanneer de plaatshouder te lang is.**
  Was naast het woord geen plaats voor `[BEGRIP_2]`, dan werd het gebied
  tot nu toe zwart overschilderd – en daarmee was ook niet meer te zien
  dat daar ooit iets stond, laat staan om terug te halen. Nu wordt een
  kortere schrijfwijze geschreven: `[BEGR_2]`, `[BE_2]`, in nood
  `[B_2]`. Het volgnummer blijft op elk niveau – daaraan vindt het
  terughalen de plek terug. Alleen waar zelfs de kortste niet past,
  blijft het bij de balk.

- **Vervangen liet de tekst staan wanneer in dezelfde regel al was
  gezwart.** Wie in het nabewerkingsvenster een naam uit het origineel
  terughaalde, daarvan de voornaam verving (daar was geen plaats – het
  werd een balk) en daarna de achternaam verving, kreeg de plaatshouder
  ingevoegd, maar de naam **niet verwijderd**. Dit viel alleen op door
  de waarschuwing van de nacontrole. Oorzaak was de regel zelf: na de
  eerste zwarting begint de rest ervan met een spatie, en daaraan vond
  de zoektocht naar de tekstplek geen houvast. Dat betrof elke tweede
  zwarting in dezelfde regel.

- **Een ingeschakelde uitgebreide herkenning zonder haar model valt nu
  op.** Het vinkje kon zijn aangevinkt terwijl het model ontbrak – de
  instellingen gelden voor elke installatie, maar het model ligt naast
  het programma. De opschonen liep dan zonder dit niveau, zonder enig
  woord erover. Nu zegt het vinkje dat het model ontbreekt, en het
  resultaat draagt een waarschuwing. Uw eenmaal gemaakte keuze blijft
  daarbij opgeslagen: zodra het model geladen is, werkt ze weer.

- **Bij het anonimiseren wordt nu het juiste begrip teruggehaald.**
  Wie meerdere begrippen met de hand verving en daarna een ervan
  terughaalde, kreeg altijd de **eerste** – van „Schmidt" werd
  „Müller". De toewijzing onthield per plaatshouder maar één
  vervanging, en bij het anonimiseren dragen alle dezelfde
  plaatshouder; het tweede en elk volgende begrip viel daarbij weg. Nu
  krijgt elke waarde haar eigen regel – ook in de lijst van
  vervangingen, die voorheen te kort was.

- **In tabellen kan nu ook worden teruggehaald.** In een CSV of
  personeelslijst staan de plaatshouders direct naast elkaar, alleen
  gescheiden door een puntkomma. Tot nu toe kon het programma daar niet
  bepalen welke waarde op welke plek had gestaan, en weigerde het – bij
  `[NAAM]` lukte het, bij `[GEBOORTEDATUM]` en `[TELEFOON]` niet. Nu
  ontleedt het de regel bij alle plaatshouders. Blijft een plek echt
  meerduidig, dan weigert het nog steeds: een verkeerd teruggeschreven
  waarde zou erger zijn dan een uitblijvende terughaling.

- **En de weigering is nu te zien.** Ze stond in gedekt grijs aan de
  onderkant van het venster, en de zin was zo lang dat hij werd
  afgekapt – het zag eruit alsof er helemaal niets gebeurde. De zinnen
  zijn ingekort, en de regel licht een paar seconden op in de
  waarschuwingskleur.

- **Een terughaling houdt nu ook stand na de volgende ingreep.** Wie bij
  het anonimiseren meerdere plekken terughaalde en daarna iets anders
  verving, vond alle teruggehaalde plekken weer vervangen en moest
  opnieuw beginnen. Oorzaak was de toewijzing: ze behield de waarde, en
  de zelfstandige afstemming voor eenduidige plaatshouders haalde haar
  bij het volgende schrijven terug. Nu geldt: wat u terughaalt, blijft
  teruggehaald – andere plekken van dezelfde waarde raakt dat niet aan.

- **In tekst-, Word-, Excel- en e-mailbestanden volstaat nu echt één
  klik in de plaatshouder.** De melding hierover stond al in de vorige
  versie, maar de knop „Selectie terughalen" bleef geblokkeerd zolang
  niets precies was gemarkeerd – men kwam dus helemaal niet toe aan de
  weg die de selectie zelf had ingesteld.

### Opgelost

- **Het controlelogboek verraadt de bestandsnaam niet meer.** Het voert
  bestanden bewust als hashwaarde in plaats van in klare tekst, omdat
  een bestandsnaam cliënt en geschilonderwerp verraadt. Deze hashwaarde
  liet zich echter door raden bevestigen – een pad is geen willekeurig
  getal. Nu gaat een toevalswaarde van deze installatie in de berekening
  mee: tellen en onderscheiden in het logboek blijven werken, natellen
  van buitenaf niet meer.

## 0.10.31-alpha.20260819 – 19 augustus 2026

### Verbeterd

- **Ook in tekst- en tabelbestanden licht de plaatshouder bij het wijzen
  rood op.** Tot nu toe was er de rode voorvertoning alleen op een
  PDF-pagina. Nu tonen beide weergaven hetzelfde: wat rood is, treft de
  volgende zet – en één klik erin volstaat om terug te halen.

- **Eén klik op een woord volstaat – het rechthoek zet de editor zelf.**
  In het nabewerkingsvenster moest tot nu toe over elke plek een
  rechthoek worden getrokken. Nu volstaat een klik: het kader legt zich
  om het woord en blijft grijpbaar, kan dus verder worden opgetrokken
  of verschoven. Bij het wijzen met de muis licht het woord al rood op,
  zodat men vooraf ziet wat de klik zou treffen. Waar geen woord staat,
  trekt men zoals voorheen een kader.

- **Men hoeft met het rechthoek niet meer precies te mikken.** Wie een
  rechthoek over een plaatshouder of een zwarting trekt, bedoelt altijd
  de hele plek – nooit de helft ervan. Het kader groeit daarom
  vanzelf naar het geheel dat het raakt: naar de hele plaatshouder, de
  hele balk of, op een ingescand blad, naar het hele gezwarte vlak.
  Kleiner dan het getrokken kader wordt het nooit.

- **Er wordt nu woordgewijs gezwart.** Een kader over de helft van een
  woord zwartte tot nu toe ook maar de helft – en een half gezwarte
  naam is nog altijd een naam. Geraakte woorden vallen nu helemaal weg;
  de buur blijft onaangetast.

- **In tekst en tabellen volstaat een klik in de plaatshouder.**
  „Selectie terughalen" vereiste tot nu toe dat men de plaatshouder
  inclusief vierkante haken precies markeerde. Nu volstaat het de
  cursor erin te zetten; de selectie springt zichtbaar naar de hele
  plaatshouder.

- **België is als land toegevoegd.** In de instellingen te kiezen;
  herkend worden dan Belgische telefoonnummers, het
  rijksregisternummer (met controlecijfer), het BTW-/ondernemingsnummer
  (met controlecijfer), adressen in beide officiële talen en de
  postcode met plaats. Tot nu toe bleven Belgische telefoonnummers
  staan, omdat het land helemaal niet in de catalogus stond.

- **Het actualiseringskanaal zegt nu hoe vroeg u iets nieuws krijgt –
  niet hoe ver.** Wie op „Testversie" stond, kreeg een nieuwe preview of
  een nieuwe stabiele versie helemaal niet aangeboden en moest het
  kanaal met de hand wisselen om er überhaupt van te horen. Nu wordt
  ook alles aangeboden wat betrouwbaarder is: testversie neemt
  testversies, previews en stabiele versies, preview neemt previews en
  stabiele. Omgekeerd nooit – op preview wordt geen testversie
  aangeboden, ook al is die nieuwer.

- **In het instellingenvenster staan de regels verder uit elkaar.** De
  vier pagina's gebruikten eigen afstanden in plaats van het raster dat
  in de rest van het programma geldt; vooral op de pagina „Herkenning"
  stonden de selectievakjes daardoor merkbaar te dicht op elkaar.

### Opgelost

- **Ingevulde PDF-formulieren verschijnen bij de handmatige bewerking
  niet meer leeg.** Maskuro maakt daarvoor uitsluitend de vluchtige
  werkkopie tot statische pagina's: ingevoerde waarden worden
  zichtbaar en kunnen echt worden gezwart; uitleesbare formuliervelden
  blijven niet verborgen in het bestand achter. Het origineel blijft
  interactief en ongewijzigd. Dat geldt nu ook voor dynamische
  XFA-formulieren: een XFA-geschikte PDFium bouwt eerst waarden en
  pagina-einden op, aansluitend ontstaat een nieuw PDF uitsluitend uit
  statische beeldpagina's. Mislukt de XFA-opbouw, dan wordt het bestand
  veilig geweigerd in plaats van schijnbaar leeg geopend.

- **„Annuleren" werkt nu ook tijdens de nauwkeurigere herkenning.** Tot
  nu toe blokkeerde de knop zich bij de klik, maar de run rekende door
  tot het laatste blok – bij een lang bestand zijn dat minuten zonder
  uitweg, en de knop zag er daarbij uit alsof hij had gewerkt. Nu
  eindigt de run bij het volgende blok.

- **In CSV-bestanden worden namen nu ook gevonden als er geen spatie
  vóór staat.** In `P-1000;Brunnthaler, Elisabeth` kleeft het
  personeelsnummer via de puntkomma aan de naam, en voor de herkenning
  was dat één woord zonder naam erin – in personeelslijsten bleef
  daardoor per regel de hele naam staan. Telefoonnummers, formules en
  het aantal kolommen van het bestand blijven daarvan onaangetast.

- **Een naam waarvan voor- en achternaam beide een koppelteken dragen,
  wordt nu herkend.** „Marie-Luise Habsburg-Ott" bleef midden in de zin
  staan, terwijl „Dragan Mitrović" in dezelfde zin werd gevonden – juist
  de combinatie van twee gekoppelde helften ontging het taalmodel.
  Gekoppelde zelfstandige naamwoorden zoals „Noord-Zuid-verbinding" of
  „Software-ontwikkelaar" blijven daarvan onaangetast.

## 0.10.30-beta.1 – 18 augustus 2026

### Verbeterd

- **De lettergrootte van de tekstweergave is nu zichtbaar instelbaar.**
  De schuifregelaar rechtsonder, die tot nu toe alleen in de
  paginaweergave zoomde, stelt in het nabewerkingsvenster bij tekst- en
  Office-bestanden de lettergrootte in (50–300 %) – net als
  „Vergroten"/„Verkleinen" in het menu Weergave. Ctrl+muiswiel kon dat
  altijd al, maar dat wist alleen wie het had uitgeprobeerd; nu werken
  regelaar, weergave en wiel samen.

- **In de donkere weergave ligt nu een wit blad op een donker
  werkvlak.** Tot nu toe was het omgekeerd: rond het blad bleef een
  licht vlak staan, en de tekst zelf stond licht op donker. Nu blijft
  het blad in beide weergaven papierwit met zwarte letters – zoals een
  PDF-pagina, die in de donkere modus ook niet donker wordt – en het
  vlak eromheen is donker.

### Opgelost

- **Na een zwarting midden in de zin gaat de rest van de zin niet meer
  verloren.** Wie in het nabewerkingsvenster driemaal naar dezelfde
  plek ging – vervangen, zwarten, dan „Origineel terughalen" –, kreeg
  het begin van de zin gewist: van „Vragen kunt u richten aan de
  boekhouding." werd „aan de boekhouding.", zonder waarschuwing.
  Getroffen was elke plek waar al eens iets midden uit een regel was
  verwijderd.

- **Een startfout sleept het afsluiten niet meer mee.** Als de opbouw
  van het hoofdvenster afbrak, crashte daarna ook het afsluiten via het
  taakbalksymbool – en deze tweede fout verborg in het foutrapport de
  eigenlijke oorzaak. Nu sluit het programma zich ook vanuit een half
  opgebouwd venster netjes af, en de opgeslagen instellingen blijven
  daarbij onaangetast.

- **„Voor/na" springt niet meer naar het begin van het document.** Wie
  in het nabewerkingsvenster naar beneden had gescrold en voor de
  vergelijking naar het origineel omschakelde, kwam weer helemaal
  bovenaan terecht – en moest de plek met de hand terugvinden. De
  weergave blijft nu op dezelfde regel staan, in beide richtingen.

- **Bij het zwarten bleef op regels met uitvulling de laatste letter
  staan.** Wanneer een tekstopdracht meer glyphen tekent dan de
  leesbibliotheek tekens meldt – ze slikt bij uitvulling graag een
  spatie in –, verschoof de toewijzing met één, en van „Dr. Michael
  Handler uit Willendorf" werd „[NAAM] r uit f": twee blijven staande
  letters midden in de opgeschoonde zin (gevonden in een echt
  raadsverslag). De toewijzing wordt nu aan de letterlijke tekst van de
  opdracht zelf gecontroleerd, waar die leesbaar is – daar wordt niet
  meer geraden.

- **„Lerchenfelder Gürtel 43/12" werd maar half verwijderd.** De
  adrespatronen kenden geen Gürtel, Kai, Lände, Zeile, Markt of Graben
  als straatgrondwoord, en het huisnummer mocht geen schuine-streepdelen
  dragen (43/12, huis/deur) – het nummer bleef naast de plaatshouder
  staan. Beide aangevuld; Weense en Salzburgse adressen vervallen nu
  helemaal.

- **Opgeslagen webpagina's blijven na de opschonen bruikbaar.** De
  adressen die lazy-loading in data-attributen opslaat
  (`data-lazy-src`, `data-lazy-srcset`), werden als verwijzingen
  vervangen – op een echte gemeentepagina zestien stuks – en de
  afbeeldingen van de pagina laadden daarna niet meer. Webadressen
  blijven daar nu staan, net als in `src` en `href`; namen,
  mailadressen en telefoonnummers in data-attributen worden verder
  vervangen.

- **Japanse en Koreaanse documenten liepen als Chinees.** De
  taalherkenning gooide alle drie schriften op één hoop, vond in
  Japanse tekst (zonder spaties) en Koreaanse (met aangeplakte
  partikels) geen functiewoorden – en nam dan gewoon de eerste
  CJK-taal van de catalogus. Een Japans raadsverslag en een Koreaans
  vergaderverslag werden zo met het Chinese model gelezen. Nu beslist
  het schriftbeeld zelf: kana betekent Japans, hangul betekent
  Koreaans.

- **Verdere misgrepen uit de veldtest in tien andere talen:** ambten
  zoals „Primar", „Gradonačelnik", „Ordfører", „Başkanı" of „Δήμαρχος"
  gelden niet meer als persoonsnamen; Turkse veldbeschriftingen („Adı",
  „Soyadı") en Griekse gesprekswoorden („Ωραία", „Βεβαίως") vallen niet
  meer weg; besluit- en paragraafnummers met datum („323/25-6-2008",
  „27 30.09.2024") zijn geen telefoonnummers meer; en zinsflarden met
  punt („10.An", „T.U.EE", „…pa") worden niet meer als webadres
  vervangen.

### Nieuw

- **Controlerapporten op verzoek automatisch.** Een vinkje in de
  instellingen (pagina „Programma") legt na elke opschoning vanzelf
  een controlerapport-PDF aan – met tijdstempel in de naam, in een
  eigen map, nooit naast het resultaat. Achteraf is een blad niet te
  maken; wie het voor het dossier nodig heeft, heeft het daarmee
  altijd. Standaard staat de opslag uit.

- **Het controlelogboek is nu in het programma in te schakelen.** Bij
  het inlezen van een bedrijfslicentie vraagt Maskuro eenmaal of het
  logboek moet worden bijgehouden – een bewijs telt alleen als het
  vanaf het begin loopt. Daarvoor is een schakelaar in de instellingen
  (pagina „Programma", zichtbaar met bedrijfslicentie of in de
  testperiode); het voorschriftenbestand van het beheer geldt verder
  en kan de waarde zoals voorheen afdwingen. Een eigen logboekregel
  „ingeschakeld" legt vast sinds wanneer wordt bijgehouden – daarmee is
  ook het begin van de registratie bewezen en ondertekend. Standaard
  blijft het logboek uit.

- **Het kengetallenpaneel toont wat het AI-niveau heeft gedaan.** Een
  nieuwe regel noemt hoeveel onzekere treffers het model heeft
  beoordeeld, behouden en verworpen en hoeveel het bovendien heeft
  gevonden – tot nu toe was zijn werk onzichtbaar als men niet elke
  waarde in de nabewerkingseditor aanklikte. Alleen aantallen, nooit
  waarden of motiveringen; zonder AI-werk verschijnt de regel niet.

- **Terughalen werkt nu ook in e-mails en HTML-pagina's.** In `.eml`,
  `.msg` en opgeslagen webpagina's was een plaatshouder tot nu toe niet
  terug te nemen – de toepassing zei dat eerlijk, maar juist e-mail is
  het formaat met de meeste persoonlijke gegevens. Nu werkt de
  terughaling daar net zo: vanuit het trefpaneel, met gemarkeerde
  selectie en ook bij geanonimiseerde plaatshouders. De onzichtbare
  HTML-tak van een e-mail (dat wat Outlook echt toont) wordt daarbij
  meegetrokken, zodat weergave en bericht hetzelfde zeggen.

- **Het trefpaneel neemt ook geanonimiseerde waarden terug – per
  waarde.** „Vervanging ongedaan maken" was bij geanonimiseerde
  bestanden tot nu toe geblokkeerd, omdat „[NAAM]" voor alle namen
  tegelijk staat. Nu zoekt de terughaling in het origineel op welke
  plek bij welke waarde hoort – in de PDF aan de coördinaten van de
  vindplaats, in de tekstweergave via de vergelijking met het
  origineel – en haalt precies de plekken van de gekozen waarde terug.
  De regels van de overige waarden blijven staan.

- **Ook geanonimiseerde plaatshouders zijn afzonderlijk terug te
  halen.** Bij het anonimiseren heten alle gegevens van een soort
  gelijk – „[NAAM]" staat voor elke persoon, en tot nu toe betekende
  dat: afzonderlijk terugnemen kan niet. Nu wordt opgezocht in het
  origineel, dat toch al naast het resultaat ligt: in de tekstweergave
  de plaatshouder markeren en „Selectie terughalen" kiezen – terug komt
  precies deze plek met precies haar waarde. Is de waarde uit het
  origineel niet ondubbelzinnig af te lezen, dan zegt de toepassing dat
  in plaats van te raden. Een toewijzingsbestand ontstaat daarbij nog
  steeds niet.

- **Het nabewerkingsvenster opent zich na de opschoning vanzelf.**
  Geen werktuig vindt alles – daarom hoort de controlerende blik op
  het resultaat bij het normale geval, niet bij een extra klik. Wie dat
  niet wil, schakelt het in de instellingen onder „Herkenning" uit
  („Resultaat daarna in het nabewerkingsvenster tonen").

### Verbeterd

- **De landkeuze staat nu standaard op „automatisch".** Tot nu toe
  gold standaard het taalgebied van het besturingssysteem – op een
  Duitse computer werden dus ook Nederlandse of Franse documenten
  alleen met de DACH-herkenners opgeschoond, en een adres als
  „Universiteitslaan 1" bleef staan (gevonden in echte, openbare
  raadsverslagen). Nu richt de landkeuze zich naar de taal van het
  document; wie in de instellingen een vaste keuze heeft gemaakt,
  behoudt die.

- **Minder ten onrechte gezwart.** Een reeks misgrepen, gemeten aan het
  controlecorpus en aan echte vergaderverslagen in zes talen, vervalt:
  bedrijfsnamen met rechtsvorm („Voorbeeldbedrijf BV") gelden niet meer
  als persoon of plaats, maar als organisatie; groetformules en kale
  aanheffen („Saygılarımızla", „Buenas tardes", een alleenstaand
  „Mevrouw") zijn geen namen meer; ambten („burgemeester", „Sindaco",
  „Alcalde") blijven staan; wets- en besluitnummers („39/2015") en
  bedragen met duizendtalpunt („330.000") zijn geen telefoonnummers
  meer; zinsbegin zoals „Envíame" of „Estarei" valt niet meer weg als
  naam; een treffer over een lege regel heen telt niet meer als naam.
  Het factuurnummer van een factuur blijft als bewijsstuknummer
  behouden – klantnummer en dossiernummer vallen verder weg.

- **Vóór het laden van het AI-model staat nu waarvoor het goed is.** De
  nalaaddialoog noemt de taken van het model – grensgevallen
  beoordelen, extra namen vinden, regels en profielen voorstellen – en
  zegt eerlijk dat het geen chatassistent is. De FAQ beantwoordt
  dezelfde vraag uitgebreid („Wat kan het AI-niveau – en wat niet?"),
  in alle taalversies.

### Opgelost

- **Controlerapport-PDF's vanaf de opdrachtregel zijn nu
  doorzoekbaar.** Onder Windows startte de headless PDF-weg zonder één
  lettertype – elk teken werd als vervangkader getekend, en het blad
  droeg geen uitleesbare tekst: wie erin wilde zoeken of iets wilde
  overkopiëren, vond niets. Nu laadt het rapport in dat geval de
  lettertypen van het systeem na; de tekst is ingebed en uitleesbaar.
  Rapporten vanuit het venster waren nooit getroffen.

- **„Origineel terughalen" over meerdere regels van een scan liet
  zwarte strepen tussen de regels staan.** Op een naar afbeelding
  omgezette pagina ruimde het kader alleen de regelbanden zelf op; de
  resten van de eerdere zwarting bleven in de tussenruimtes staan. Nu
  verdeelt het getrokken kader zich volledig over de regels.

- **Een tweede kader over een plaatshouder liet een rode rest staan.**
  De plaatshouder is bijna altijd breder dan het woord dat hij
  vervangt; wie daarna over dezelfde plek zwartte, trof alleen zijn
  begin – over bleef een fragment zoals „AAR_1]" midden in de zin, en
  het terughalen zette de oorspronkelijke tekst vervolgens op diens
  plek in plaats van op die van het woord. Een aangesneden plaatshouder
  vervalt nu altijd helemaal.

- **Op een gedraaide pagina wiste het zwarten over een plaatshouder een
  onbetrokken zin.** De achteraf getekende plaatshouder werd bij het
  verwijderen verward met de tekst ervoor: hij bleef zelf staan, de
  waarschuwing „staat nog steeds in het document" kwam – en op een
  andere plek van de pagina verdween zonder vervanging een zin die met
  het kader niets te maken had. Een plaatshouder wordt nu via zijn
  letterlijke tekst teruggevonden; de keten „vervangen, zwarten,
  terughalen" klopt daarmee ook op scheef ingescande pagina's.

- **Het handboek raadde in tien talen nog `python3-tk` aan.** In de
  foutoplossing stond daar dat onder Linux mogelijk tkinter ontbrak –
  een raad uit de tijd vóór de Qt-interface, die niemand meer verder
  helpt. Nu staat in alle versies dezelfde alinea als in het Duits: het
  ontbreken van de systeembibliotheken die Qt voor de weergave nodig
  heeft.

- **Het licentiehoofdstuk van het handboek stond in alle zestien
  vertalingen op oude stand.** In tien talen las men daar nog dat
  Windows Server een bedrijfslicentie met servertoegang nodig had en er
  daar geen gratis niveau was – sinds een plaats een mens telt en geen
  machine, is beide onjuist. Verder ontbraken overal de inlichtingen
  over wanneer een bezette plaats weer vrijkomt, dat de licentie zich
  regelmatig bevestigt en wat daarbij wordt overgedragen, en de
  activering zonder internet stond alleen als korte versie zonder de
  drie stappen en zonder de aanwijzing dat de computer daarna een jaar
  zonder verbinding werkt.

- **Zeven alinea's over het nabewerken ontbraken in tien talen.** Wie
  de hulp in het Deens, Fins, Frans, Italiaans, Nederlands, Noors,
  Pools, Portugees, Zweeds of Spaans las, vond noch de paginaweergave
  voor Office-bestanden, noch „Handmatig zwarten", noch het hele
  hoofdstuk over hoe het programma van een correctie leert – inclusief
  de tabel met de drie reikwijdtes. In „Wat wordt herkend" ontbrak in
  dezelfde tien versies de weg via de beschrijving in het document.

- **Met ingelezen licentie startte het programma niet meer.** In plaats
  van het venster kwam „Het programma kon niet worden gestart" – en wel
  bij elke licentie, ongeacht welke. Oorzaak was de regel in de
  licentieweergave die kort vóór het verstrijken van de proeftermijn
  waarschuwt; ze greep naar iets dat daar niet beschikbaar was. Zonder
  licentie – in de testperiode en het gratis niveau – trad de fout niet
  op, daarom is ze pas nu opgevallen.

- **In het formulier blijven de veldnamen staan.** „Geboortedatum" en
  „Adres" verdwenen met hun waarde: de plaatshouder stond klein en rood
  op de plek van de *veldnaam*, het veld eronder bleef leeg. De
  veldnaam hoort niet bij de gegevens – die blijft nu staan, en de
  plaatshouder staat op de plek waar de waarde stond.

- **Anderstalige documenttitels worden niet meer voor namen gehouden.**
  Boven een Italiaans formulier stond „FATTURA", boven een Spaans
  „PERMISO PARENTAL" – beide werden vervangen. De lijst met
  documentwoorden kende alleen de Duitse equivalenten.

- **Uit een factuur verdwijnt geen regel meer.** „Materiaaltoeslag 1
  84,00" werd voor een adres gehouden en door een plaatshouder
  vervangen – het bewijsstuk miste daarna een regel. Een regel die
  eindigt met een bedrag is een post en geen adres; echte adressen
  („Hoofdstraat 1  120,00") blijven onaangetast.

### Gewijzigd

- **„Map bewaken …" en de opdrachtregel zijn voorlopig niet meer
  aanwezig.** Beide wegen zijn gebouwd en werken, maar geen van beide
  is in de praktijk beproefd: de mapbewaking heeft nooit een
  Windows-doorloop gezien, en de opdrachtregel geeft een script twee
  dozijn schakelaars in handen die bij geen enkele gebruiker ooit
  hebben gedraaid. Wat onbeheerd documenten wijzigt, moet dat niet
  ongecontroleerd doen – daarom zijn ze teruggetrokken totdat de
  doorloop is ingehaald. Het menu-item ontbreekt, en `--wache` staat
  niet meer in `maskuro --help`.

- **Open blijft wat alleen leest en wat sowieso nodig is.** De
  zoekloop (`--suchlauf`) en de nacontrole (`--nachpruefen`) werken op
  de opdrachtregel verder – ze wijzigen geen bestand. Evenzo de start
  via de verkenner, het contextmenu, het klembord en het venster;
  daaraan verandert niets.

- **„Van scanner ophalen" heeft nu een eigen hoofdstuk in het
  handboek.** Het stond tot nu toe aan het einde van „Map bewaken". Op
  de Mac luidde het advies daar, een map te laten bewaken; nu luidt
  het, de ingescande pagina's naar het venster te slepen.

### Opgelost

- **„Origineel terughalen" over meerdere regels vernielde de
  structuur.** Een kader over een plaatshouder, een ongewijzigde
  functietitel en een tweede vervanging plaatste het hele gebied
  opnieuw als **één** regel – van drie regels werd er één, en wat niet
  meer paste, werd een balk. Nu wordt elke regel afzonderlijk
  teruggehaald.

- **En onveranderde tekst blijft daarbij onaangetast.** Wie over een
  vervanging *en* gewone tekst sleept, krijgt alleen de vervanging
  terug; de rest wordt niet aangeraakt. Ook de laatste rest van de oude
  plaatshouder verdwijnt daarbij – voorheen bleef diens sluithaak
  midden in de zin staan.

- **Bij het vervangen blijven geen resten van de oude tekst meer
  staan.** In een vette kop stond daarna „1. R[BEGRIP_2]ige [BEGRIP_1]
  … che" – de plaatshouder zat erin, maar lettergrepen van het
  origineel ernaast. Geruimd wordt nu het gebied dat u omkadert, niet
  alleen de kaders van de woorden erin.

- **Een anonieme plaatshouder wordt niet meer teruggehaald.** Bij het
  anonimiseren draagt elke naam dezelfde `[NAAM]`. Het terughalen nam
  de eerste de beste vermelding en schreef die op elke vindplaats – van
  „Georg Aigner" werd „Anna Modelvrouw", dus een verkeerde naam in het
  document. Nu staat er dat niet meer te zeggen is welke gegeven werd
  bedoeld; het document blijft onaangetast.

### Nieuw

- **„Origineel terughalen" werkt nu ook op een gerasterde pagina.**
  Werd een pagina naar een afbeelding omgezet, kwam tot nu toe een
  weigering: de teruggehaalde tekst zou onder het pagina-beeld komen.
  Nu wordt de plek in het beeld geruimd en de tekst erop geschreven –
  zoals een plaatshouder op een scan. De inhoud komt daarbij uit het
  originele bestand, en dat is niet gerasterd.

- **„Selectie terughalen" staat nu als eigen knop.** Het ging al
  eerder, maar alleen als men toevallig een plaatshouder markeerde en
  op „Selectie vervangen" drukte – een functie die men alleen bij
  toeval vindt, bestaat voor de gebruiker niet.

### Gewijzigd

- **In platte tekst, CSV en Outlook-berichten bestaat geen „Selectie
  zwarten" meer.** Deze formaten kunnen geen balk dragen; de knop zette
  daar een plaatshouder en zei dat ook – maar een knop die iets anders
  doet dan hij heet, hoort daar niet.

- **Een werktuig zegt nu wanneer het op deze plek niets kan doen.** Een
  plaatshouder kan niet nog eens worden vervangen, boven een zwarting
  wordt geen plaatshouder gezet, en waar al het origineel staat, valt
  er niets terug te halen. Tot nu toe deden deze acties iets wat naar
  effect leek, maar dat niet was.

## 0.10.29-alpha.20260817 – 17 augustus 2026

### Opgelost

- **In het nabewerkingsvenster werkt nu elk kader dat men trekt.** Wie
  tweemaal op dezelfde plek werkte – eerst vervangen, dan zwarten, dan
  het origineel terughalen –, wiens tweede en derde zet zonder woord
  wegviel: het nog grijpbare kader van de vorige zet ving hem op.
  Hetzelfde bij het wisselen van werktuig, waarbij zelfs stilzwijgend
  het oude werktuig doorwerkte.
- **Een te smal getrokken kader zegt dat het te smal is.** Tot nu toe
  lichtte de voorvertoning een woord rood op, en bij het loslaten
  gebeurde er zonder woord niets.

- **Outlook-berichten zijn eindelijk na te bewerken.** Een `.msg` toonde
  in het nabewerkingsvenster „Dit formaat kan hier niet worden
  weergegeven" – het was het enige ondersteunde formaat zonder enige weg
  om met de hand na te werken. Nu staan afzender, ontvanger, onderwerp
  en berichttekst benoemd in de weergave en zijn te markeren en te
  vervangen zoals in elk ander tekstformaat.

- **„Selectie vervangen" blijft in een e-mail bij de selectie.** Wie een
  naam in de lopende tekst markeerde, verloor daarbij ook afzender en
  ontvanger uit de kopregels, en de melding noemde een andere
  plaatshouder dan die in de tekst stond. Nu wordt de gemarkeerde
  waarde overal vervangen – ook in de afzender, als hij daar staat – en
  verder niets aangeraakt.

- **Een kader over meerdere regels vernielt de tekst niet meer.** Tot nu
  toe ontstond één enkele plaatshouder op één plek: van het
  aangesneden woord bleef een rest eraan kleven, en uit de tweede regel
  verdween de tekst zonder vervanging – geen plaatshouder, geen balk,
  alleen een gat. Nu krijgt elke regel zijn eigen plaatshouder met de
  waarde die daar echt stond.

- **„Origineel terughalen" werkt nu ook na een zwarting.** Het venster
  meldde succes, en de tekst kwam nooit terug: de zwarte balk telde als
  obstakel, zodat er voor de teruggehaalde tekst geen plaats meer was.
  De balk wijkt daarbij nu, en de teruggehaalde tekst staat er zwart
  bij zoals gewone tekst – niet rood zoals een plaatshouder.

- **„Origineel terughalen" op een onaangeraakte plek doet nu niets
  meer.** Wie het kader over tekst trok waaraan helemaal niets was
  gewijzigd, kreeg de tekst verwijderd en kleiner en verschoven weer
  ingevoegd – gemeld werd succes. Nu staat er dat er niets terug te
  halen valt.

### Nieuw

- **Ook in Word, Excel, PowerPoint, OpenDocument en tekst kan worden
  gezwart.** Tot nu toe bestond daar alleen „Selectie vervangen"; een
  balk was voorbehouden aan de PDF-weergave, zonder dat daar een reden
  voor was. Waar een balk niet weer te geven is – in platte tekst en in
  een Outlook-bericht –, wordt de waarde zoals voorheen door een
  plaatshouder vervangen, en dat staat ook zo in de melding.

- **Een plaatshouder markeren haalt hem terug.** In de tekstweergave
  (Word, Excel, PowerPoint, OpenDocument, tekst) volstaat het nu de
  plaatshouder te markeren en op „Selectie vervangen" te drukken: de
  oorspronkelijke waarde komt terug. Tot nu toe verwees het venster
  daarvoor naar het trefpaneel.

- **Sprekers in een vergaderverslag worden ook herkend als hun naam
  tegelijk een gewoon woord is.** „Gruber: De oplevering vindt volgende
  week plaats." werd vervangen, „Bauer: Ik ga akkoord." bleef staan –
  de achternaam ziet er voor de herkenning uit als een zelfstandig
  naamwoord. Merkregels van dezelfde bouwvorm blijven onaangetast: van
  „Let op: De installatie moet worden uitgeschakeld." wordt geen naam.

- **„U gebruikt de nieuwste versie" werd ook gezegd wanneer helemaal
  niet kon worden nagekeken.** Wijst de actualiseringsserver het
  verzoek af – omdat er van hetzelfde internetadres te veel verzoeken
  kwamen of omdat hij zelf net gestoord is –, dan bleef het programma
  stilstaan op zijn oude versie en beweerde het de nieuwste te zijn.
  Precies dat is op 17 augustus op een Mac gebeurd: 0.10.25 bleef
  liggen, terwijl 0.10.28 al uren klaarstond.

  Nu zegt het venster wat er aan de hand is, noemt het tijdstip van de
  volgende controle – en wijst uitdrukkelijk erop dat **niet** vaststaat
  of de eigen versie de nieuwste is.

  Meestal ligt het niet aan de eigen computer: bij veel aansluitingen
  delen talrijke klanten hetzelfde internetadres, en de server telt ze
  samen. Daarom zoekt Maskuro de versielijst in dat geval via een
  **tweede weg** en vindt meestal toch nieuwe versies. Blijft het bij
  de afwijzing, dan wordt de server tot het genoemde tijdstip met rust
  gelaten – ook als men de knop nog eens indrukt; nogmaals proberen
  verlengt alleen de blokkade.

- **Hoeveelheidsaanduidingen worden niet meer voor plaatsnamen
  gehouden.** In een dienstovereenkomst verdween „Vierdaagse werkweek"
  achter een plaatshouder voor een plaats – midden in het
  contractonderwerp. Zulke woordverbindingen van getal en koppelteken
  („Driepuntenplan", „24-uursdienst") blijven nu staan. Adressen zijn
  daarvan uitgezonderd: een „Tweegebroederspad" wordt verder wel
  vervangen.

## 0.10.28-alpha.20260817 – 17 augustus 2026

### Gewijzigd

- **Licentieplaatsen worden nu echt geteld.** Tot nu toe meldde geen
  enkele werkplek zich ooit bij de licentiedienst aan – een
  tienplaatsenlicentie liep op willekeurig veel computers, zonder dat
  iemand daarvan wist. Nieuw: de computer die het programma start,
  neemt een plaats in; een plaats komt na **zeven dagen zonder start**
  vanzelf weer vrij, zodat een kapot toestel of een vertrokken
  medewerker niets blijvend blokkeert.

  Een kleine overschrijding wordt daarbij **alleen weergegeven en niet
  geblokkeerd**: tot tien procent boven het gekochte aantal werkt
  iedereen door – de nieuwe laptop naast de nog aangemelde oude hoeft
  geen geval voor de hotline te zijn. Wie daarboven bijkomt, valt terug
  op het gratis niveau en krijgt dat te horen; de computers die er het
  eerst waren, merken daar niets van.

- **Een gekochte licentie bevestigt zich regelmatig.** Lukt dat **30
  dagen** lang niet, dan geldt zolang weer het gratis niveau, tot het
  weer lukt. Er wordt niets uitgeschakeld, en vanaf een week ervoor
  staat de aanwijzing in het venster. Zodra de computer weer internet
  heeft, lost dit vanzelf op. Testperiode en gratis niveau melden
  verder helemaal niets – wie nooit koopt, belt nooit.

- **„Zonder internet activeren" werkt eindelijk.** De activering werd
  tot nu toe wel gecontroleerd en opgeslagen, maar daarna door niemand
  meer gelezen – ze veranderde niets aan de rechten. Nu is ze de
  uitweg voor computers zonder netwerktoegang: ze geldt **een jaar**,
  daarna haalt men met een nieuwe aanvraagcode een nieuwe. Een
  apparaat met internet heeft men daarvoor eenmaal per jaar nodig – de
  computer zelf blijft blijvend offline.

- **De activering gaat nu ook via het klantaccount** – onder „Mijn
  licenties" op de website. Daar staat bovendien welke computers aan
  uw licentie hangen en wanneer hun plaatsen weer vrijkomen; dat was
  tot nu toe nergens te zien. De pagina zonder aanmelding blijft voor
  iedereen die geen shoptoegang heeft – ze vraagt daarvoor extra het
  e-mailadres uit de bestelling, zodat de licentiesleutel alleen niet
  volstaat.

- **En in het venster staat nu waar de aanvraagcode heen moet.** De
  papieren weg zei „op een apparaat met internetverbinding invoeren" en
  noemde geen adres; de activeringspagina bestaat al lang, maar er werd
  van nergens naar verwezen. Nu staat **maskuro.com/lizenz-freischalten**
  in de dialoog, in het handboek en in de FAQ – en op de website onder
  de licentiesleutel.

- **De knop „Zonder internet activeren …" blijft zichtbaar**, ook als de
  licentie op dat moment niet geldig is. Voorheen verdween hij samen
  ermee – dus juist wanneer men hem nodig heeft.

- **„Alle plaatsen bezet" zegt nu de waarheid.** De aanwijzing eindigde
  met „Het programma werkt ongewijzigd verder"; dat klopt niet meer als
  geen plaats is toegewezen. Daar staat nu dat tot nader order het
  gratis niveau geldt.

### Nieuw

- **Bij het inschakelen van de klembordopschoning staat er nu bij dat
  het nagekeken moet worden.** De melding noemt sindsdien dezelfde zin
  die ook bij het resultaat van een bestand staat: Maskuro herkent niet
  in elk geval alle persoonsgegevens.

  Hier weegt dat zwaarder dan elders. Bij een bestand ziet men het
  resultaat voordat men het doorgeeft. Bij het klembord niet – men
  kopieert, plakt, en de opgeschoonde tekst staat al in het mailvenster.
  De melding zegt daarom uitdrukkelijk om de **geplakte** tekst na te
  kijken.

  Ze verschijnt bij het inschakelen, niet bij elke kopieerhandeling: wat
  vijftig keer per dag zou verschijnen, leest na de derde keer niemand
  meer.

- **„Alles kopiëren" onder de lijst – en „Alles verwijderen" schuift
  weg.** De nieuwe knop legt alle voltooide resultaten in één keer op
  het klembord, om aan een mail te hangen of in een ander programma te
  plakken. Tot nu toe ging dat alleen via het menu en ook daar alleen
  voor de **geselecteerde** regels – wie alle bedoelde, moest eerst
  Ctrl+A indrukken.

  Daarbij is de knoppenrij opnieuw geordend: links staat wat iets
  toevoegt, rechts achter een tussenruimte wat iets wegneemt. „Alles
  verwijderen" stond tot nu toe direct naast „Toevoegen …", en een
  misgreep kostte de hele lijst. Diezelfde regel geldt sinds 13 augustus
  al bij elke voltooide regel.

- **Werkplekken zonder internet krijgen hun taalmodellen nu van
  binnenuit.** Opschonen ging daar altijd al zonder verbinding – het
  naladen van een taalmodel niet, en een model weegt enkele honderden
  megabytes.

  Het beheer stelt de bestanden eenmaal op een computer met verbinding
  samen en legt ze op een share, in de uitrol of op een stick. De
  locatie wordt centraal ingevoerd (veld `modellquelle` in
  `vorgaben.json` of de omgevingsvariabele `MASKURO_MODELLQUELLE`).
  Vanaf dan bedient elk naladen zich eerst daar – taalmodellen, het
  Japanse woordenboek en het hoog-niveau – en gaat pas het internet op
  als een bestand ontbreekt.

  De controlesommen gelden daarbij ongewijzigd. Een bestandsshare in
  huis is vaak makkelijker te beschrijven dan een release op het
  internet; ze mag niet de gemakkelijkere weg naar een ondergeschoven
  model worden.

  Hoe zo'n voorraad ontstaat en hoe licentie en activering zonder
  internet verlopen, staat in `OFFLINE.md`.

- **„Origineel terughalen" – een kader haalt terug wat te veel is
  verwijderd.** In het nabewerkingsvenster is er een nieuw werktuig:
  kader over de plek trekken, en de tekst staat er weer zoals in het
  origineel.

  Dat sluit het gat dat het trefpaneel openliet. Daar was een
  vervanging alleen terug te nemen als haar plaatshouder eenduidig was
  – dus niet bij het anonimiseren, waar „[NAAM]" voor elk gegeven van
  dat soort staat, en helemaal niet bij gezwarte plekken, waar geen
  plaatshouder overblijft. Juist daar hopen zich de misgrepen op:
  „Gebruiker", „Inventarisnummer", „Handtekening" worden graag voor
  namen gehouden.

  Het kader heeft de plaatshouder niet nodig: de **plek** komt uit het
  rechthoek, de **inhoud** uit het originele bestand – hetzelfde dat de
  voor/na-schakelaar toont. Geanonimiseerd of gepseudonimiseerd speelt
  daarmee geen rol meer.

  De teruggehaalde tekst staat er zwart bij, niet rood: hij is weer
  klare tekst en geen plaatshouder. Uit de treflijst verdwijnt een
  vermelding pas wanneer haar plaatshouder **nergens** meer in het
  document staat – werd dezelfde waarde op meerdere plekken vervangen,
  dan blijft ze voor de overige staan.

  Op een pagina die naar een afbeelding is omgezet, weigert het
  werktuig en legt uit waarom: de teruggehaalde tekst zou onder het
  pagina-beeld komen te liggen en zou niet te zien zijn.

### Opgelost

- **Bij het inklappen van „Details" en „Kengetallen" bleven
  beeldresten op het scherm staan.** Ingeklapt schoof een deel van de
  inhoud onder de onderrand van het venster en bleef daar boven de
  achtergrond hangen, totdat iets anders eroverheen werd getekend.

  Beide gebieden hebben een minimumhoogte, zodat ze open bruikbaar
  groot zijn. De beweging bij het inklappen verlaagde echter alleen de
  maximumhoogte – en onder zijn minimumhoogte krimpt een gebied niet.
  De inhoud bleef dus 200 punten hoog, terwijl het venster zich al tot
  24 samentrok; het verschil stond onder de rand. Nu wijkt de
  minimumhoogte voor de duur van de beweging en komt daarna terug.

- **Het venster werd bij herhaald open- en dichtklappen steeds
  kleiner.** Bij het openklappen groeit het hoogstens tot 92 % van de
  schermhoogte; is de ruimte krap, dan groeit het dus minder dan nodig.
  Bij het dichtklappen trok het toch het volledige bedrag weer af. Nu
  wordt precies teruggegeven wat het openklappen heeft gekost.

- **Een rest van een gezwarte gegeven kon zichtbaar blijven staan.** In
  een cv bleven van „*30.12.1991" de tekens „*30.1" leesbaar in het
  resultaat – dus dag en begin van de maand van de geboortedatum. Het
  programma had de rest zelfs opgemerkt en de pagina daarom naar een
  afbeelding omgezet; juist dat maakte het erger, want daarmee was de
  rest weliswaar niet meer doorzoekbaar, maar nog wel te lezen – en
  niet meer te verhelpen.

  De oorzaak lag tussen twee controles. De strengere van de twee kijkt
  na of in het vlak van een verwijderd gegeven nog iets staat dat daar
  niet hoort; ze meldt haar bevinding als tekenverzameling, omdat de
  leesvolgorde bij het vervangen verschuift. De terugvaloptie, die
  zulke plekken vóór het omzetten overschildert, zocht deze
  tekenverzameling als tekst op de pagina – en vond haar nooit.
  Overschilderd werd daarom niets. De plek was de hele tijd bekend en
  wordt nu doorgegeven, in plaats van opnieuw te worden gezocht.

  Getroffen was elke pagina waarvan de rest alleen door deze controle
  werd gevonden – ongeacht bestandstype en taal.

- **Op een scheef ingevoerde scan vond de tekstherkenning niets.** Wie
  een blad zijwaarts in de invoer legt, krijgt een bestand waarin de
  tekst 90 graden gedraaid staat. Tot nu toe las Maskuro daarin **geen
  enkel** gegeven – en het bestand zag er daarna onopvallend uit: er
  werd niets gevonden, dus er werd niets gemeld, en het adres stond nog
  steeds leesbaar in de afbeelding. Nu richt de tekstherkenning de
  pagina zelf op; op het controlebeeld vallen weer alle gegevens.

  Twee grenzen openlijk benoemd: een **op de kop** staand blad (180
  graden) leest zij nog steeds niet, en bij een heel slechte scan helpt
  het rechtzetten niet – daar is te weinig leesbaar om de stand
  überhaupt te bepalen. Elke afbeelding kost daarvoor ongeveer een
  vijfde langer.

### Gewijzigd

- **„Automatisch installeren" heet nu wat het doet.** Het vinkje in de
  instellingen beloofde meer dan het waarmaakte: het download de
  nieuwe versie vanzelf en start de installatie – die verloopt echter
  **zichtbaar** en wil bevestigd worden, onder Windows inclusief de
  vraag van de gebruikersaccountbeveiliging. Wie „automatisch" las,
  rekende op een computer die zich 's nachts zelf actualiseert, en
  stond 's ochtends voor de installatiewizard. Het vinkje heet nu
  „Actualiseringen automatisch downloaden en de installatie starten",
  met een zin eronder wat dat betekent. Aan het gedrag verandert niets
  – dat Maskuro zich niet ongemerkt vervangt, is opzet en blijft zo.

## 0.10.27-alpha.20260817 – 17 augustus 2026

### Nieuw

- **Nieuw: `--ersetzen` voor de koppeling aan kantoorsoftware.** Het
  resultaat komt in de plaats van het bronbestand, in plaats van
  ernaast te ontstaan. Daarmee werkt het uit- en incheken van
  kantoorsoftware („Openen en bewerken" in het e-dossier) zonder enige
  interface: de software geeft het bestand uit en krijgt het op
  dezelfde plek opgeschoond terug.

  **Deze schakelaar zet het eerste grondbeginsel opzij**, en daarom
  bestaat hij alleen op de opdrachtregel – niet in het venster – en
  alleen als uw beheer hem vrijgeeft (item `ersetzen` in het
  voorschriftenbestand). Zonder vrijgave breekt de aanroep af en zegt
  waarom; stilzwijgend een tweede bestand aanleggen zou de ergere fout
  zijn, want dan zou de ongewijzigde versie weer worden ingecheckt.

  Geschreven wordt eerst een naastliggend bestand; pas als het klaar
  is, komt het in de plaats van de bron. Een afbreking of fout laat de
  bron daarmee **byte voor byte ongewijzigd** en laat geen fragment
  achter. In het controlelogboek staat de vervanging als eigen veld –
  een controleur moet weten dat de niet opgeschoonde versie hier niet meer
  ligt.

- **Het handboek legt nu de Windows-waarschuwing bij de eerste start
  uit.** Nieuwe eerste sectie „Windows waarschuwt bij de eerste start –
  wat te doen", met twee afbeeldingen en drie stappen: „Meer informatie"
  is een kleine link, geen knop – juist daar blijven de meesten
  hangen –, dan „Toch uitvoeren".

  Dat daar „Onbekende uitgever" staat, is de hele boodschap van de
  waarschuwing: de pakketten worden momenteel zonder certificaat
  uitgeleverd. Wij vinden het juister dat uit te leggen dan het te
  verzwijgen.

- **De terugweg merkt nu wanneer tekst en toewijzing niet bij elkaar
  horen.** Wie het antwoord in een ander proces plakt, kreeg tot nu toe
  vreemde namen in de juiste tekst – geen fout, geen melding, alleen
  fout. Maskuro onthoudt nu welke plaatshouders de laatste run
  überhaupt heeft gegenereerd, en meldt elke die er niet bij hoort.
  Komt er geen enkele uit de laatste run, dan wordt niets ingevoegd en
  zegt het venster waarom – in plaats van zoals voorheen een verlopen
  termijn te vermoeden.

  **Een grens blijft, en ze staat ook in het handboek:** plaatshouders
  worden per run doorgenummerd, de eerste naam heet dus in elk document
  `[NAME_1]`. Draagt de vreemde tekst alleen zulke plaatshouders, dan
  is de verwisseling niet te herkennen.

- **PDF is nu in zwart-wit uit te voeren.** Een vinkje bij de werkwijze
  zet elke pagina om in een zwart-witafbeelding – met onzichtbare
  tekstlaag eronder, dus verder leesbaar en doorzoekbaar. Voor het
  versturen via beA en soortgelijke wegen met strikte
  groottegrenzen: over ons meetcorpus gemiddeld **68 % kleiner**
  (opdrachtregel: `--monochrom`).

  **Hoeveel het oplevert, hangt af van het document** – en dat staat
  ook bij het vinkje: gescand en beeldrijk materiaal krimpt sterk, een
  slank tekstdocument zonder ingebedde lettertypen kan zelfs groter
  worden. Probeer het op een bestand voordat u het voor een batch
  inschakelt.

  De prijs: elke pagina wordt opnieuw berekend – bij duizend pagina's
  duurt dat minuten. En afbeeldingen verliezen alles tussen zwart en
  wit; voor tekst maakt dat niet uit, voor een foto wel.

- **De treflijst in het nabewerkingsvenster telt nu mee.** Boven de
  lijst staat „5 treffers", en zodra u filtert, „1 van 5 treffers". Dat
  is het verschil tussen „ik heb gefilterd" en „het zijn er vijf, en ik
  heb ze allemaal gezien" – de handeling waarmee men controleert of een
  naam echt overal is vervangen.

- **Het controlelogboek is nu doorzoekbaar en filterbaar.** De weergave
  onder „Bestand → Controlelogboek" had tot nu toe een tabel en verder
  niets – bij een maand met drieduizend runs zag men dat er veel was
  gebeurd, maar niet wat.

  Nieuw zijn een **zoekveld**, **drie filters** (methode, resultaat,
  soort) en het **bladeren**, plus drie kolommen die er voorheen niet
  waren: **methode** (gezwart of vervangen), **betrouwbaarheid** en
  **duur**. Boven de lijst staat hoeveel er op dat moment te zien is en
  hoeveel het filter verbergt.

  „Opslaan als CSV …" geeft nu **uit wat er staat** – wie heeft
  gefilterd, krijgt het gefilterde, en de melding noemt het aantal.

  Een streep bij betrouwbaarheid of duur betekent dat voor die regel
  niets is gemeten – bijvoorbeeld omdat ze ouder is dan deze functie.
  Deze waarden worden **niet** achteraf berekend. Een filter op
  gebruiker bestaat verder niet; een afzonderlijke regel vindt het
  zoekveld toch.

### Verwijderd

- **De transparantieaanwijzing in het venster „Over dit programma" is
  weer weg.** Ze stond daar sinds 0.10.22-beta.1 en zei dat de
  toepassing met ondersteuning van kunstmatige intelligentie werd
  ontwikkeld. Vereist is ze nergens, en juist in een toepassing voor
  gegevensbescherming las menigeen haar als een uitspraak over de
  werkwijze – dus alsof de documenten naar een dienst op het internet
  gingen. Opgeschoond wordt verder uitsluitend op de eigen computer; dat
  staat waar het hoort, in het tabblad „Privacy".

### Opgelost

- **Het programma verving zijn eigen symbool door een slechter.** Wie
  het contextmenu vanuit het programma zelf registreerde, had daarna
  een ander schild in de taakbalk dan na de installatie – vergelijkbaar,
  maar met links uitgelijnde in plaats van gecentreerde balken en
  zichtbaar grover. Daarachter zat een noodgreep: vindt het programma
  de symboolsjabloon niet, dan tekent het er zelf een. Bedoeld was dat
  voor het geval er **geen** symbolen zijn; in werkelijkheid tekende
  het ook wanneer de meegeleverde er allang lagen – en overschreef ze.
  In een via setup geïnstalleerde versie bestaat geen sjabloon, dus
  trof het daar iedereen. Aanwezige symbolen blijven nu onaangetast.

  **Al getroffen installaties halen het juiste symbool niet vanzelf
  terug** – daarvoor eenmalig opnieuw installeren.

- **„Objectkenmerk: OB-4711-22" gold als aanmeldnaam.** De herkenner
  voor gebruikersnamen controleerde zijn beschrijvingen zonder
  woordgrens ervoor – dus greep **elk** woord dat op een ervan eindigt:
  objectkenmerk, voertuigkenmerk, apparaatkenmerk. De waarde erachter
  werd verwijderd, hoewel ze met een aanmeldnaam niets te maken heeft.

  Samenstellingen die echt bedoeld zijn – „Gebruikerskenmerk",
  „Aanmeldkenmerk" –, staan afzonderlijk in de lijst en worden verder
  gevonden.

- **In het Engels, Grieks, Japans en Koreaans stonden zestien
  plaatshouders in het Duits in het resultaat.** Wie de interface op
  een van deze vier talen had ingesteld, kreeg voor de nieuwere
  gegevenssoorten de Duitse beschrijvingen in het document geschreven –
  van een wachtwoord werd `[ZUGANGSDATEN_1]` in plaats van
  `[CREDENTIALS_1]`, van een diagnosecode `[DIAGNOSESCHLUESSEL_1]` in
  plaats van `[DIAGNOSIS_CODE_1]`. Getroffen waren gezondheid,
  diagnose, medicatie, diagnose- en geneesmiddelencode, religie,
  vakbond, politieke overtuiging, strafrecht, toegangsgegevens,
  gebruikersnaam, kaartgegevens, coördinaten, beroep, bedrag en
  kenmerk.

  De overige 44 talen kenden de fout nooit: ze halen hun
  beschrijvingen uit de taalbestanden, waarin deze soorten van meet af
  aan stonden. Juist deze vier talen voeren om een andere reden eigen
  tabellen – hun schrift overleeft de PDF-tekenset niet, waardoor daar
  Latijnse beschrijvingen staan –, en in deze tabellen ontbraken de
  nieuwe soorten simpelweg.

  Opgevallen is het bij het vertalen van de catalogusPagina: de website
  beloofde Engelse lezers beschrijvingen die het programma niet
  schreef. Een controlesteen houdt de vier tabellen nu tegen de lijst
  van alle beschrijvingen die überhaupt kunnen ontstaan.

- **Het regelvenster opent zich niet meer te klein voor zijn inhoud.**
  In het tabblad „Eigen zoekpatronen" lag de uitlegregel van de
  assistent („Gezocht wordt: …") half achter het veld „Proeftekst" –
  juist de zin waarmee men zonder kennis van reguliere expressies
  controleert of de eigen regel het juiste zoekt. Het venster had een
  vaste minimumgrootte uit een tijd met minder tabbladen en liet zich
  daardoor onder wat erin past trekken. Nu richt het zich naar zijn
  inhoud en gaat het alleen zo klein open als alles leesbaar blijft.

- **Namen in tabelformules blijven niet meer staan.** Een cel heeft meer
  dan één plek voor tekst, en tot nu toe werd er maar één opgeruimd.
  Stond een naam in een formule – `="Mevrouw "&"Sieglinde Ortner"` –
  of was ze het laatst berekende resultaat van een formule, dan bleef
  ze ongewijzigd in de werkmap staan, hoewel dezelfde persoon in de
  cel ernaast was vervangen. Wie de cel aanklikte, las haar in de
  bewerkingsbalk.

  Beide worden nu vervangen. Aangeraakt wordt alleen wat tussen
  aanhalingstekens staat: celverwijzingen, functienamen en bladnamen
  blijven onaangetast, `=SOM(K2:K6)` rekent verder. Omdat dezelfde naam
  overal dezelfde plaatshouder krijgt, vindt ook
  `=SOMMEN.ALS(A:A;"Huber";B:B)` verder zijn regels.

- **Grafieken tonen geen namen meer.** Een grafiek slaat een eigen kopie
  van haar asbeschrijvingen op – ze tekent nog steeds, ook wanneer de
  broncellen allang leeg zijn. Onder de balken stonden daardoor verder
  vijf persoonsnamen, terwijl de tabel erboven schoon was. Geldt voor
  tabellen **en** presentaties.

- **Benoemde bereiken met vaste tekst worden opgeruimd.** Een benoemd
  bereik kan in plaats van een celverwijzing vaste tekst bevatten;
  stond daar een naam, dan bleef ze staan. De **naam** van het bereik
  blijft verder staan – daarnaar verwijzen formules, en een hernoeming
  zou een verwijzingsfout opleveren. Zoals bij de bladnaam wordt hij
  gemeld, niet vervangen.

- **Een eenmaal herkende geboortedatum verdwijnt in het hele document.**
  Een datum op zich zegt niets – pas een veldwoord maakt haar tot
  geboortedatum, en juist daarom blijft een factuurdatum ongemoeid.
  Stond hetzelfde gegeven in hetzelfde document echter een tweede keer
  zonder dit woord – in de beeldtitel, in een ingevuld formulierveld –,
  dan bleef het daar staan, hoewel een paar regels erboven „geboren
  op …" ondubbelzinnig was herkend. Overgedragen wordt alleen wat in
  **dit** document al als geboortedatum werd herkend; geraden wordt
  verder niets.

- **Gestructureerde gegevens in webpagina's geven hun geboortedatum
  prijs.** In het JSON-LD-blok voor zoekmachines staat de datum onder
  de sleutel `birthDate` – de sleutel zegt wat het is, zoals verder de
  kolomkop. Ze wordt nu meegelezen; „Birthday" en „Birthdate" gelden
  daarmee ook in formulieren als veldbeschrijving.

- **Geboortedatum en personeelsnummer worden ook in tabellen
  gevonden.** In een cel staat alleen de kale waarde – `14.03.1988`.
  Wat ze betekent, zegt alleen de kolomkop, en die staat vele regels
  hoger. In Excel werd hij al meegelezen; in LibreOffice-tabellen en
  in CSV-bestanden niet, en daar bleef de geboortedatum daarom staan.

  Beide lezen de kop nu mee – **maar alleen als deze zelf een
  veldbeschrijving is**. Onder „Geboortedatum" vervalt de datum, onder
  „Factuurdatum" of „Leverdatum" niet. Dat is bewust de voorzichtige
  uitleg: een kop zoals „Naam" boven een willekeurige opmerking zou
  eerder ook al eens een plaatshouder over een zin hebben gelegd
  waarin helemaal geen persoon voorkomt.

### Opgelost

- **Een opgeschoonde CSV blijft een tabel.** De herkenning leest een
  CSV-regel als zin en legde haar vondsten daardoor ook al eens over
  een puntkomma heen. De plaatshouder slikte het scheidingsteken in, de
  regel had daarna een kolom minder, en het bestand liet zich niet meer
  als tabel openen. Vindplaatsen eindigen nu bij de celgrens, en de
  aanhalingstekens van de maskering blijven staan. De betrokken cellen
  worden vervolgens nog een keer apart gelezen – anders zou de
  buurcel niet opgeschoond achterblijven die de te lange treffer had
  verborgen.

- **Opmerkingen in presentaties.** De kanttekening bij een dia – vaak
  juist de plek waar „Gelieve mevrouw … vóór de vergadering te bellen"
  staat – bleef onaangetast, samen met de naam van wie haar heeft
  geschreven. In Excel was beide allang opgeruimd; PowerPoint slaat
  opmerkingstekst en auteur anders op, en dat was over het hoofd
  gezien. Betreft beide bouwvormen: de oudere en die welke PowerPoint
  sinds 2019 schrijft – daar ook het zakelijke mailadres dat aan de
  auteur hangt. De initialen die PowerPoint bij het spraakballonnetje
  toont, worden meeverwijderd.

- **LibreOffice-bestanden: formule, gebruikersveld, notitieauteur.** Wat
  in Excel al werd opgeruimd, bleef in de ODS-tabel staan – daar staat
  de formule niet als eigen element, maar als eigenschap van de cel, en
  de naam daarin overleefde. Bij de volgende keer openen berekende
  LibreOffice haar weer terug.

  Daarbij drie verdere plekken: de waarde van een **gebruikersveld**
  staat in OpenDocument eenmaal bovenaan in de declaratie en wordt in
  de tekst alleen opgeroepen – vervangen werd tot nu toe alleen de
  oproep, zodat bij het openen de oude waarde terugkwam. De **auteur
  van een notitie** en van een bijgehouden wijziging bleef staan. En in
  een **tabel** werd de wijzigingsbijhouding helemaal niet opgeruimd –
  anders dan in het tekstdocument –, zodat verwijderde celinhoud samen
  met bewerkernamen behouden bleef. Celverwijzingen en somformules
  blijven daarbij onaangetast.

- **Opgeslagen webpagina's geven hun attributen prijs.** Een pagina
  toont lang niet alles wat ze bevat. Een ingevuld formulierveld draagt
  de invoer in `value`, een JavaScript-interface legt haar dataset in
  `data-…` vast, en het blok voor zoekmachines (JSON-LD) herhaalt het
  volledig en welgevormd: naam, geboortedatum, adres, telefoon. De
  zichtbare tekst was opgeschoond, dit alles bleef verder staan.

  Nu worden ook deze plekken opgeruimd, plus `aria-…` (wat aan de
  schermlezer wordt voorgelezen), `placeholder`, `summary` en de
  voorgestelde bestandsnaam van een verwijzing. Het JSON-LD-blok wordt
  daarbij als gegevens gelezen en blijft geldig – zijn sleutels en zijn
  vocabulaire blijven staan, alleen de waarden gaan weg. Gewoon
  JavaScript wordt verder niet aangeraakt.

- **Afbeeldingen verliezen hun nevengegevens ook zonder EXIF.** Een foto
  draagt fotografennaam, opnametijdstip en GPS-coördinaten van de
  opnamelocatie ernaast geschreven – bij een woningadvertentie verraadt
  dat het adres, ook als er in de tekst geen staat. Dat werd
  verwijderd, zolang de afbeelding EXIF had. Stonden de gegevens echter
  **alleen** als XMP vastgelegd (zo slaan Lightroom en Photoshop op) of
  als tekstblok in een PNG (`Author`, `Comment`), dan bleef de
  afbeelding helemaal onaangetast. Beide worden nu herkend en
  verwijderd – ook bij afbeeldingen die in een document zitten en daar
  behouden blijven. De oriëntatie overleeft verder, en een afbeelding
  zonder nevengegevens wordt niet onnodig opnieuw opgeslagen.

- **Verwijzingsdoelen in tabellen, presentaties en Word-documenten.**
  Waarheen een verwijzing leidt, staat niet in de tekst, maar in een
  eigen opslag van het bestand. Een mailadres achter „Mail schrijven"
  overleefde daardoor de opschoning ongeschonden, terwijl hetzelfde
  adres in de tekst was vervangen. `mailto:` en `tel:` worden daar nu
  net zo opgeruimd als in opgeslagen webpagina's.

### Nieuw

- **Artsenbrieven komen niet meer beschadigd terug.** Tot nu toe hield
  de naamherkenning geneesmiddelen voor persoonsnamen: van
  „Metoprololsuccinaat" werd `[NAME]`, van „Ramipril" werd `[ORT]`.
  Het medicatieschema was daarna onbruikbaar – terwijl de diagnoses
  onaangetast bleven staan, dus precies andersom. Gemeten betrof dat
  **63 % van de werkzame stoffen** en **53 % van de klinische
  vaktermen**, en niet alleen in het Duits: over zeven talen 74 %, in
  het Italiaans alle geteste.

  Maskuro kent nu de medische woordenschat en laat die met rust. Over
  blijft 6 % in plaats van 43 % (Duits) en 1 % in plaats van 74 % (over
  de talen). Waar een aanhef ervoor staat – „Geachte mevrouw …" – blijft
  de naam een naam, ook als hij toevallig als een geneesmiddel heet.

- **Ziekten en medicijnen zijn te verwijderen – als u dat wilt.** Nieuw
  vinkje in de instellingen: „Ziekten en medicijnen ook verwijderen"
  (opdrachtregel: `--mit-diagnosen`). Voor personeelsdossiers,
  ontslagen en deskundigenrapporten, waar de diagnose niemand iets
  aangaat.

  **Standaard uit**, en wel met opzet: een artsenbrief *bestaat* uit
  diagnoses en werkzame stoffen. Wie er een anonimiseert – voor
  onderzoek, voor een training, voor een AI-werktuig – wil meestal
  precies deze inhoud behouden en alleen kwijt wie het betreft. De
  diagnose is daar de nuttige lading, geen identificatie.

  De herkenning vindt de gangbare benamingen en vervangt niet de
  doorlezing: een ziektelijst is nooit volledig, omdat de arts
  „C2-abusus" schrijft, waar de classificatie „stoornissen door
  alcohol" hanteert.

- **Diagnose- en geneesmiddelencodes worden gevonden.** ICD-10
  (`I48.2`), ATC (`A10BA02`) en het farmaceutisch centraalnummer zijn
  gezondheidsgegevens zoals elke uitgeschreven diagnose – in
  ontslagbrieven en afrekeningsdocumenten zelfs de vaker voorkomende
  vorm. Ze staan standaard aan, zoals de overige bijzondere
  categorieën volgens art. 9 AVG.

  Een diagnosecode wordt alleen met bewijs herkend: met „ICD" ervoor of
  tussen haakjes achter de diagnoseregel. Zonder deze voorwaarde zou
  het programma de functietoets **F10** voor een verslavingsdiagnose
  houden – in de classificatie is F10 precies dat.

- **Het voltooide bestand is nu te kopiëren.** Bij elke voltooide regel
  staat naast „Bekijken", „Nabewerken" en „In map tonen" een vierde
  knop: **Kopiëren**. Hij legt het opgeschoonde bestand op het klembord –
  van daar gaat het met Ctrl+V (Mac: ⌘V) in een mail, een chatvenster
  of een AI-werktuig, zonder de omweg via de map.

  Gekopieerd wordt het **bestand**, niet zijn tekst: paginaopbouw,
  afbeeldingen en de zwartingsbalken blijven daarmee behouden. Via het
  contextmenu van de lijst gaan ook meerdere geselecteerde resultaten
  in één keer op het klembord, en in het menu „Bestand" staat dezelfde
  weg als **„Resultaat kopiëren"** voor iedereen die liever het
  toetsenbord gebruikt.

- **De landkeuze kan nu het document volgen.** Identiteits-, sociale-
  en belastingnummers verschillen van land tot land, en welke landen
  worden gecontroleerd, stond tot nu toe voor de hele sessie vast –
  afgeleid uit de taal van de interface. Wie in het Duits werkt en een
  Frans schrijven opschoont, zocht daarin dus naar Duitse
  belastingnummers en niet naar het Franse
  socialezekerheidsnummer.

  In het regelvenster staat daarvoor nu **„Automatisch naar de taal
  van het document"**. De vaste keuze blijft daarnaast bestaan, en wel
  met opzet: de taalherkenning is niet onfeilbaar – herkent ze
  verkeerd, dan grijpt de verkeerde landkeuze. Wie alleen dossiers van
  één land bewerkt, vaart veiliger met de vaste lijst.

  Onaangetast daarvan blijven de **Duitse** patronen (belastingnummer,
  kenteken, doorkiesnummer): die hangen aan de taal, niet aan de
  landkeuze, en grijpen verder ook wanneer een korte Duitse tekst als
  Engels wordt ingedeeld.

- **Wachtwoorden, sleutels en aanmeldnamen worden nu gevonden.** Wie een
  foutmelding, een logboek of een fragment uit een configuratiebestand
  in een AI-venster plakt, heeft daar bijna altijd een toegangssleutel
  in – en die bleef tot nu toe ongewijzigd staan.

  Herkend wordt beide: de wijdverbreide sleutelvormen die voor zich
  spreken (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token,
  het begin van een privésleutel), en de beschreven vorm –
  „Wachtwoord:", „API-Key =", „Token:", „Gebruikersnaam:". Vervangen
  wordt daarbij alleen de waarde, nooit de beschrijving: „Wachtwoord:
  [ZUGANGSDATEN_1]" blijft leesbaar, en wie het resultaat controleert,
  ziet dat daar een wachtwoord stond.

  Aanmeldnaam en wachtwoord zijn twee gescheiden soorten. Wie alleen
  wachtwoorden wil verwijderen, schakelt de ene uit en behoudt de
  andere.

- **Streep- en QR-codes in afbeeldingen worden onherkenbaar gemaakt.**
  Op een gescande beschikking kleeft bijna altijd een code, en daarin
  staat het dossiernummer – hetzelfde nummer dat in de tekst ernaast
  wordt verwijderd. Tot nu toe bleef de machineleesbare versie staan:
  de balk over het nummer helpt niet als twee centimeter verderop een
  apparaat het in een seconde uitleest.

  Herkend worden QR-code, Data Matrix, Aztec, Code 128, EAN en de
  overige gangbare vormen. Onherkenbaar betekent pixeleren, en wel
  grover dan bij gezichten: de foutcorrectie van een code haalt uit
  weinig behouden velden verrassend veel terug, een halfslachtige
  sluier zou geen verwijdering zijn.

  De optie staat naast „Gezichten onherkenbaar maken" en is even
  **standaard aan**. Ook bij uitgeschakelde optie zegt het rapport
  hoeveel afbeeldingen een code dragen – een gezicht ziet men bij het
  doorbladeren, een code houdt men voor bijzaak.

- **Kaartverificatienummer, pincode en vervaldatum worden gevonden.**
  Het kaartnummer vond het programma al; pas met de drie gegevens
  ernaast is het bruikbaar, en op elk afrekeningsbewijs staan ze bij
  elkaar. Alle drie alleen achter hun beschrijving – „123" alleen is
  een huisnummer, een paginanummer of een aantal.

- **Coördinaten in de tekst worden gevonden.** Uit afbeeldingen heeft
  Maskuro de opnamelocatie al eerder verwijderd; stond dezelfde
  aanduiding als tekst in het rapport of het inzetverslag, dan bleef
  ze staan. Herkend worden decimale graden en de
  graden-minuten-secondennotatie. Bij decimale graden moet een woord
  zoals „Locatie", „Vindplaats" of „Coördinaten" in de buurt staan –
  anders zou elke meetreeks met twee decimalen een plaatsaanduiding
  zijn.

- **Geldbedragen zijn nu mee te verwijderen.** Nieuw vinkje „Geldbedragen
  ook verwijderen", standaard **uit** zoals de datumaanduidingen
  erboven: in een contract is het bedrag de inhoud, en wie alles zwart
  maakt, beschermt niemand. In een loonstrook, een schikkingsvoorstel
  of een rekeningafschrift is het daarentegen precies het gegeven dat
  meer over de persoon zegt dan de naam ernaast — dat weet alleen wie
  het document voor zich heeft.

  Herkend wordt een bedrag **alleen met valuta-aanduiding**: „4.250,00"
  alleen is een aantal, pas „4.250,00 EUR" is geld. Valutasymbool,
  afkorting en voluit geschreven naam tellen, ervoor zoals erachter,
  inclusief de schrijfwijze „990,– CHF".

- **De bijzondere categorieën volgens art. 9 AVG worden herkend.**
  Godsdienstige overtuiging, vakbondslidmaatschap, politieke
  overtuiging, gezondheidsgegevens – en daarnaast de strafrechtelijke
  gegevens volgens art. 10. Dat zijn de gegevens wier verwerking de
  verordening in beginsel **verbiedt**; ze staan daarom als enige
  nieuwe groep standaard **aan**. Wie ze wil behouden, beslist dat
  zelf.

  Herkend wordt de vorm waarin ze in de praktijk voorkomen: het
  formulierveld op het personeelsblad – „Geloofsovertuiging:
  rooms-katholiek", „Vakbond: FNV", „Mate van arbeidsongeschiktheid:
  50", „Strafblad: geen" –, en wel zowel met dubbele punt ernaast als
  met de beschrijving erboven, zoals een ingevuld blad ze levert.

  **De lopende tekst hoort bij het AI-niveau.** „Hij zet zich al jaren
  in voor de vakbond" is hetzelfde gegeven, en geen zoekpatroon vindt
  het betrouwbaar. Het AI-niveau zoekt sinds deze versie uitdrukkelijk
  ook naar deze categorieën; wie de lopende tekst nodig heeft,
  schakelt het bij.

- **Persoonskenmerken en beroep – de gegevens die ook zonder naam tonen
  wie bedoeld wordt.** Geslacht, burgerlijke staat, lichaamslengte,
  oog- en haarkleur worden vanaf deze versie verwijderd; beroep,
  functie en afdeling op verzoek, via een eigen vinkje („Beroep en
  afdeling ook verwijderen") of `--mit-berufen`.

  **Waarom het ene aan en het andere uit staat:** „De hoofdafdeling
  inkoop" benoemt in een bedrijf precies één persoon, ook al is de
  naam ernaast gezwart – in een deskundigenrapport of een ontslag
  hoort dat verwijderd. Een personeelsoverzicht *bestaat* daarentegen
  uit functiebenamingen; wie het standaard verwijderde, zou een leeg
  blad teruggeven. Welk geval van toepassing is, weet alleen wie het
  document voor zich heeft. De kenmerken erboven staan bijna alleen in
  formuliervelden, zijn zeldzaam en dragen nooit de inhoud – ze kosten
  dus niets.

- **Een vreemd bestand nakijken.** „Bestand → Bestand nakijken …" leest
  een al gezwart document na en meldt wat er nog in staat – en **op
  welke plek**: pagina en regel, soort en lengte. Voor het geval dat
  iemand het werk van een ander controleert: een dossier van het
  kantoor, een auskomstbericht van de overheid, de eigen uitgaande post
  vóór het versturen.

  **De waarde zelf staat niet in het rapport.** Wie de plek opslaat,
  ziet haar toch al – en het rapport mag daarom worden opgeslagen en
  doorgegeven, zonder zelf een verzameling persoonsgegevens te zijn.

  **En het rapport zegt in elk geval wat het niet kon zien.**
  Afbeeldingen worden niet gelezen; bij een scan zonder tekstlaag
  betekent „geen vindplaats" *niet gecontroleerd*, niet *schoon*. Op de
  opdrachtregel scheidt de retourwaarde dat: `--nachpruefen` levert 0
  voor gecontroleerd en schoon, 4 voor vindplaatsen en 5 voor niet te
  controleren. Daarmee is uitgaande post automatisch tegen te houden,
  in plaats van door te winken.

- **Controlerapport: één blad per opschoning.** „Bestand →
  Controlerapport opslaan …" – of `--pruefbericht <map>` op de
  opdrachtregel – schrijft een eenpagina PDF (naar keuze CSV of tekst)
  met de gegevens over de run, de gevonden soorten samen met aantal,
  twee kengetallen en een controlevermelding. Voor het dossier en voor
  het toezicht: het controlelogboek is het overtuigende bewijs, maar
  niemand legt een JSON-Lines-bestand voor.

  **Nieuw daarbij zijn twee getallen** die tot nu toe nergens te zien
  waren: de *gemiddelde betrouwbaarheid* – hoe zeker de herkenning was
  bij wat ze vond – en het *maskeringspercentage*, het aandeel
  vervangen tekens in de tekst. Beide staan met hun grens erbij: de
  betrouwbaarheid zegt **niets** over het over het hoofd geziene, en
  ernaast staat altijd over hoeveel treffers ze überhaupt gaat; het
  percentage telt afbeeldingen niet mee en valt bij een beeldrijk
  document te hoog uit.

  **Gevonden waarden staan niet op het blad** – dezelfde grens als bij
  het logboek en de zoekloop. Onderaan staan twee regels die niet
  hetzelfde zeggen: de controlesom toont dat het blad ongewijzigd is;
  de logboekregel – alleen bij lopend logboek – verwijst naar de
  **ondertekende** regel die de run bewijst. Alleen zij bewijst de
  herkomst.

- **„Hoe zeker was dat?" – de kengetallen bij het resultaat.** Een knop
  „Kengetallen" onder het resultaat klapt open wat tot nu toe nergens
  te zien was: vindplaatsen, woorden en tekens, de verdeling per soort
  als balkregel, plus de gemiddelde betrouwbaarheid en het
  maskeringspercentage. Dezelfde cijfers als in het controlerapport,
  alleen meteen en zonder afdruk.

  **Met haar voorbehoud in hetzelfde vlak:** naast de betrouwbaarheid
  staat over hoeveel treffers ze gaat, en eronder de zin dat ze
  **niets** zegt over het over het hoofd geziene. Een percentage zonder
  deze zin leest als een vondstpercentage – en wie het zo begrijpt, is
  er slechter aan toe dan zonder het getal.

  Berekend wordt pas bij het openklappen: de noemer van het
  maskeringspercentage kost per bestand een leesbewerking, en die
  hoeft niet te betalen wie de cijfers helemaal niet bekijkt.

- **Eigen zoekpatronen bouwen, zonder er een te schrijven.** Het
  tabblad „Eigen zoekpatronen" leidt nu in drie stappen door de zaak:
  *Wat zoekt u? → Hoe ziet zo'n gegeven er bij u uit? → Benoemen en
  opslaan.* U typt een voorbeeld in – bijvoorbeeld `KD-004711` –, het
  programma leidt de regel eruit af en schrijft in woorden op waarnaar
  ze zoekt. Een voorbeeld met treffenteller controleert bij elke
  toetsaanslag mee.

  **Een reguliere expressie komt daarbij niet voor.** Het kunnen was
  nooit het probleem: eigen zoekpatronen bestaan al lang, alleen
  vereisten ze een uitdrukking zoals `\bKD-\d{6}\b`, en die schrijft
  niemand op een kantoor of personeelsafdeling. Wie er zelf een wil
  schrijven, klapt de expertmodus open.

  **De sjablonencatalogus is opnieuw geordend:** dertien kaarten met
  naam, uitleg en voorbeeldwaarde, gefilterd op categoriemarkeringen –
  financiën, overheid, contact, personeel, medisch.

  En wanneer het afgeleide patroon te ver grijpt, zegt het programma
  dat uit zichzelf: een voorbeeld van louter cijfers treft elk jaartal
  en elk bedrag, en wie de uitdrukking niet kan lezen, zou dat anders
  niet merken.

- **Zeven markeringen in plaats van zesenvijftig vinkjes.** Een nieuw
  tabblad „Wat wordt gezocht" bundelt alle herkenbare soorten in zeven
  groepen – persoon, contact en plaats, kenmerken, financiën, techniek,
  bijzondere categorieën, bedrijven en eigen. Een markering schakelt
  haar groep, „Alles aan" en „Alles uit" de hele lijst; daaronder
  blijft elke soort afzonderlijk aan te vinken.

  **Standaard staat alles aan, en dat blijft zo.** Wat hier wordt
  uitgeschakeld, wordt helemaal niet meer gezocht – de grofste ingreep
  die het regelvenster toestaat, en hij werkt op elk document. Daarom
  staat onder de lijst altijd hoeveel soorten uit staan, en opgeslagen
  wordt alleen het uitgeschakelde: een nieuwe soort staat daarmee ook
  in een regelbestand van eergisteren aan, in plaats van stilzwijgend
  weg te vallen.

- **Een kader op alle pagina's toepassen.** In het nabewerkingsvenster
  neemt de knop **Op alle pagina's toepassen** het laatst getrokken
  kader en zwart dezelfde plek op elke verdere pagina – voor briefkop,
  voettekst en dossiernummerveld. Bij een gescand dossier met tachtig
  pagina's maakt dat van twintig minuten twee.

  **„Dezelfde plek" betekent dezelfde *relatieve* plek op het blad.**
  In een stapel uit de invoer ligt regelmatig een pagina liggend, een
  andere is A3, een derde gedraaid; een absoluut toegepast rechthoek
  belandde daar naast de briefkop – en men zou een balk zien en de
  zaak voor afgehandeld houden.

  **Er wordt gezwart, niet vervangen**, ook wanneer het uitgangskader
  een plaatshouder was: onder hetzelfde rechthoek staat op pagina
  veertig iets anders dan op pagina één, en een plaatshouder met
  hetzelfde nummer beweerde een gelijkheid die er niet is.

- **Een vermelding op de zwartbalk.** In het inzagerecht staat naast
  elke zwarting waarom er gezwart is. Het nieuwe veld **Vermelding op
  de balk** in de instellingen – of `--balkenvermerk` – schrijft een
  korte tekst op elke balk: „art. 272 Sr", „AVG", „vertrouwelijk". Voor
  een document dat een overheidsinstantie uitgeeft, is dat het
  verschil: de ontvanger ziet de reden, zonder een logboek te hebben
  dat hij toch nooit krijgt.

  **Standaard leeg**, want de vermelding is in het uitgegeven document
  zichtbaar en zelf een gegeven – ze zegt de ontvanger onder welke
  titel iets wordt achtergehouden. Ze werkt alleen bij het **zwarten**;
  waar een plaatshouder staat, staat geen balk. Op een balk die te
  klein is voor leesbare tekst, vervalt ze – een onleesbare vermelding
  ziet eruit als een fout.

- **Activeren zonder internetverbinding – nu volledig.** In het
  licentievenster bestond „Zonder internet activeren" al langer: boven
  een aanvraagcode om mee te nemen, onder het veld voor de activering
  die terugkomt. Alleen kon **niemand haar tot nu toe uitgeven** – het
  werktuig daarvoor ontbrak, en de code liep in het niets. Dat is
  opgelost.

  Voor overheidsinstanties en kantoren met afgeschermde computers is
  dat geen bijzonder geval, maar het normale geval – en het is precies
  de doelgroep bij wie de belofte „uw documenten verlaten de computer
  nooit" het zwaarst weegt. De code verraadt niets over documenten: hij
  bevat het licentiekenmerk en een streuwaarde van de computer, verder
  niets.

- **Van scanner ophalen.** „Bestand → Van scanner ophalen …" leest een
  stapel direct in en legt de pagina's in de lijst – voor een poststuk
  het verschil tussen twee werkstappen en één. Een documentinvoer wordt
  tot de laatste pagina geleegd; apparaat, resolutie en kleur kiest de
  systeemdialoog van de scanner, die u toch al kent.

  **Er wordt niet vanzelf opgeschoond.** U ziet eerst wat is binnengekomen,
  en drukt dan op „Opschonen" zoals bij elk ander bestand – een scan
  die meteen doorloopt, zou u de blik ontnemen op een scheef ingevoerde
  stapel.

  **Dat bestaat alleen onder Windows**, en het menu-item zegt dat op de
  Mac ook: daar schrijft de software van uw scanner naar een map, en
  „Map bewaken …" schoont alles op wat daar terechtkomt.

### Overige

- **De lijst met alle gevonden gegevens ligt er nu bij** en wordt uit de
  broncode gegenereerd (`hilfe/GEFUNDENE-ANGABEN.md`): 177 soorten in
  35 landen, 23 daarvan met controlecijferberekening. Ze noemt ook hoe
  geteld werd – wij tellen `[NAAM]` één keer, waar anderen voor-,
  tweede en achternamen als drie items voeren.

- **Zwarten bestaat nu ook in Word, PowerPoint, OpenDocument en HTML.**
  De keuze tussen plaatshouder en zwarting bestond tot nu toe alleen
  voor PDF-bestanden. Nu kunnen ook de andere het: de vondst wordt
  verwijderd, en op haar plek staat een zwarte balk – in het document
  zelf, niet als afbeelding erboven. Wie het bestand doorgeeft, geeft
  een gezwart dossier door en geen waarin het gezwarte nog als tekst
  eronder ligt.

  **Beslist wordt het gescheiden**, in twee keuzevelden: „Bij PDF" en
  „Bij Word, PowerPoint, OpenDocument en HTML". Men wil het
  verschillend – de gezwarte PDF gaat naar de overheidsinstantie,
  dezelfde zaak als Word-bestand gaat verder door het huis en moet
  leesbaar blijven. Op de opdrachtregel overeenkomstig `--pdf-modus` en
  `--office-modus`; een opgeslagen „Zwarten" uit eerdere versies geldt
  verder de PDF.

  In tabellen, platte tekst, CSV en e-mail werkt de balk niet – daar
  ontbreekt het vlak waarop hij zou kunnen liggen. Er wordt verder een
  plaatshouder ingevoegd, en het resultaat **zegt het nu**, in plaats
  van het stilzwijgend te doen.

- **Nieuw: „Verwijderen" – de vindplaats blijft gewoon leeg.** De derde
  werkwijze naast plaatshouder en zwarten, en de enige die **elk**
  formaat kan: iets weglaten heeft geen vlak nodig. In de PDF wordt
  daarbij niets getekend, in Word en HTML blijft de plek leeg, in een
  tabel evenzo.

  Ze is de stilste van de drie: wie het resultaat leest, ziet niet dat
  daar ooit iets stond – ook de lengte van de waarde verraadt zich niet
  meer. Voor een document dat iemand moet controleren, blijft de
  plaatshouder meestal de betere keuze.

  In afbeeldingen geldt geen van de drie keuzes: beeldpunten laten zich
  niet door een plaatshouder vervangen en niet weglaten. Wat de
  tekstherkenning daar vindt, wordt zoals voorheen altijd
  overschilderd.

- **Het nabewerkingsvenster beweert geen vervangingen meer die er niet
  zijn.** Rechts stond bij elke waarde een plaatshouder – ook bij een
  gezwart bestand, waarin er niet één voorkomt. Een klik op zo'n regel
  markeerde niets, en „Ongedaan maken" liep in het niets. Nu staat daar
  „gezwart" resp. „verwijderd", en de regels zijn helemaal niet meer
  terug te nemen: de tekst is weg, er valt niets terug te halen. Dat
  gold voor gezwarte PDF-bestanden, voor Word en OpenDocument en voor
  alles wat in afbeeldingen werd gevonden.

- **De tekstweergave toont de balken nu als balken.** Een gezwart
  Word-bestand zag er bij het nabewerken **leeg** uit: op de gezwarte
  plekken stonden leemtes, alsof het programma de tekst had ingeslikt.
  De reden lag bij de weergave, niet bij het resultaat – in het
  document zelf lag de balk de hele tijd correct. Nu staat hij ook in
  de weergave daar, zwart zoals in het resultaat, in Word, PowerPoint,
  OpenDocument en HTML.

- **Outlook-berichten (`.msg`) worden nu opgeschoond.** `.eml` bestond al
  lang – in Duitse bedrijven is Outlook echter de e-mail, en daar heet
  een opgeslagen bericht `.msg`. Daarmee is het dichtste PII-formaat
  ook in zijn meest verspreide opslagvorm afgedekt: onderwerp,
  afzender, ontvangerregels, berichttekst, HTML-versie,
  ontvangerslijst en bijlagen – laatstgenoemde via de bestaande wegen
  en met dezelfde plaatshouders als de mailtekst.

  **Een `.msg` draagt dezelfde tekst meermaals**, en dat is de val: als
  platte tekst, als HTML **en** als RTF. Wie alleen de platte tekst
  opschoont, heeft niets gedaan – Outlook toont bij voorkeur de RTF. De
  RTF-versie wordt daarom helemaal verwijderd, evenals de
  internetkopregels met hun Received-keten en de binaire zoeksleutels,
  die namen en adressen elke tekstopschoning overleven. Het resultaat
  opent verder in Outlook en toont de tekst zonder lettertypemarkering;
  het rapport zegt dat uitdrukkelijk.

- **Regels in eigen woorden beschrijven, in plaats van regex te
  schrijven.** Het regelsvenster kan veel en vereiste daarvoor een
  reguliere expressie – de plek waar het voor de meesten ophoudt. Nu
  volstaat een zin: „Onze dossiernummers van de vorm 12 C 345/26 moeten
  blijven staan." Het AI-niveau stelt daaruit begrippen en
  zoekpatronen voor.

  **Overgenomen wordt alleen wat u aanvinkt – en standaard is niets
  aangevinkt.** Bij elk voorstel staat een zin over wat het betekent,
  en het aantal treffers in een voorbeeldtekst die u kunt meegeven. Wat
  bescherming **wegneemt**, is als zodanig gemarkeerd: „dit begrip
  altijd verwijderen" en „dit begrip nooit verwijderen" zouden in een
  lijst anders hetzelfde lijken. Voorstellen die op alles zouden
  passen, worden helemaal niet getoond.

- **Het controlelogboek telt nu over alle werkplekken samen.** Legt een
  huis de logboeken via `protokoll_pfad` op een share, dan schrijft
  elke werkplek er zijn eigen maandbestand – tot nu toe moest een
  privacyfunctionaris met dertig plaatsen dertig bestanden apart
  bekijken. Boven de lijst staat nu een regel met de sommen van de
  maand, en **ze meldt gebroken ketens met naam**: een achteraf
  aangebrachte wijziging valt alleen op als iemand nakijkt, en in
  dertig bestanden kijkt niemand met de hand na.

  **Geen overzicht per persoon** – ook niet in deze weergave. Een
  rangorde „wie heeft hoeveel opgeschoond" zou geschikt zijn voor
  gedrags- en prestatiecontrole, en daarop komt het medezeggenschapsrechtelijk
  aan, niet op de bedoeling. Geteld worden runs, bestanden en treffers
  over het hele huis.

- **„Profiel uit een document voorstellen": de regels één keer vragen
  in plaats van vierenveertig soorten doorlopen.** In het regelsvenster
  bestaat een nieuwe knop: hij toont het AI-niveau een document, bepaalt
  waar het om gaat – artsenbrief, sollicitatie, contract, factuur,
  beschikking – en stelt de strategieën voor die daarbij passen. Bij de
  artsenbrief bijvoorbeeld worden datumaanduidingen verschoven in
  plaats van vervangen, omdat in een medisch dossier de chronologie de
  inhoud is.

  **De profielen staan in het programma, het model kiest alleen** – de
  zwartingsregels hangen niet af van wat een taalmodel een goed idee
  vindt. Voorgesteld wordt elk punt afzonderlijk en met motivering;
  overgenomen wordt niets zonder nadere vraag, en wat u zelf hebt
  vastgelegd, blijft onaangetast. Zonder AI-niveau blijft het bij de
  veilige standaard: plaatshouder voor alles.

- **Nieuwe strategie „verzinnen": een plausibele foutwaarde in plaats
  van een plaatshouder.** „Mevrouw Berger schreef aan de heer Doppler
  in Fulda" in plaats van „[NAME_1] schreef aan [NAME_2] in [ORT_1]" –
  voor trainingsmateriaal, demonstratiedossiers, testgegevensbestanden
  en alles wat aansluitend aan een AI wordt voorgelegd. Aanhef, zinsbouw
  en leesbaarheid blijven behouden.

  Dezelfde waarde krijgt dezelfde foutwaarde, over alle bestanden van
  een proces heen en op elke computer met hetzelfde regelbestand –
  **zonder dat ergens een toewijzing wordt opgeslagen** (dezelfde
  mechaniek als bij het hashen). E-mailadressen liggen op gereserveerde
  voorbeelddomeinen, telefoonnummers in het daarvoor vrijgehouden
  bereik, verzonnen IBAN's dragen een correct berekend controlecijfer.
  Mogelijk voor namen, plaatsen, adressen, bedrijven, e-mail, telefoon
  en IBAN; voor andere soorten wordt de regel geweigerd, in plaats van
  zonder effect te blijven.

  **Het rapport zegt uitdrukkelijk dat er verzonnen is.** Een zo
  opgeschoond document leest als echt en is geen echt document – het
  deugt niet als bewijs en mag niet als origineel worden doorgegeven.

- **De tegencontrole: „Wie blijft herkenbaar?"** Een nieuw vinkje onder
  het AI-niveau legt het **voltooide resultaat** nog eens aan het
  taalmodel voor en vraagt wie ondanks opschoning te herkennen is.
  Bedoeld is het geval dat geen enkele herkenning ter wereld vindt,
  omdat daar helemaal geen naam staat: „de enige vroedvrouw in het
  district", „de collega die in maart na de brand is ontslagen". Geen
  patroon grijpt, en ter plaatse weet toch iedereen wie bedoeld wordt.

  **Er wordt daarbij niets verwijderd.** De plekken staan met een zin
  motivering in het rapport, en beslist wordt met de hand – een
  programma dat uit zichzelf zinnen uit een document neemt omdat ze het
  verraderlijk voorkomen, maakt van een opschoning een herschrijving,
  en niemand zou zien wat ontbreekt. Hoogstens vijf plekken per
  bestand; wat het model niet letterlijk kan bewijzen, vervalt. Op de
  opdrachtregel: `--restrisiko` samen met `--ki`.

- **De weg terug uit de AI: „Antwoord terugvertalen".** Tot nu toe was
  alleen de halve lus gebouwd – tekst kopiëren, opgeschoond plakken, aan
  de AI voorleggen. Het antwoord kwam met `[NAME_1]` terug, en wie het
  nodig had, zette met de hand weer in wat hij met de hand had
  weggehaald. Nu staat de terugweg in het menu „Programma": antwoord
  kopiëren, item aanklikken, de echte namen staan er weer.

  De toewijzing daarvoor ligt **alleen in het werkgeheugen**, geldt
  altijd alleen voor de laatst opgeschoonde plek en verloopt na een uur;
  wie de klembordwachter uitschakelt, is haar meteen kwijt. Terughalen
  lukt daarbij alleen wat werd vervangen – gezwart, gemaskeerd en
  gehasht is niet omkeerbaar, en het programma zegt hoeveel plekken het
  daarom moest laten staan. Beheerde installaties schakelen de terugweg
  via het voorschrift `rueckweg` helemaal uit.

- **Map bewaken: wat erin wordt gelegd, ligt kort daarna opgeschoond in de
  uitgang.** Voor een poststuk, een postbusteam of een scanmap – eenmaal
  inrichten, daarna klikt niemand meer. Te vinden onder „Bestand → Map
  bewaken …", op de opdrachtregel via `--wache <map>`.

  Het origineel blijft liggen waar het lag; op verzoek verhuist het
  ongewijzigd naar de submap „Voltooid", waarbij nooit iets wordt
  overschreven. Een bestand wordt pas aangeraakt zodra het volledig is
  geschreven – een nog over het netwerk gekopieerd bestand zou anders
  half gelezen en als opgeschoond gemeld worden. Wat misgaat, blijft
  liggen en wordt gemeld, in plaats van eindeloos herhaald te worden.
  En de wacht onthoudt voltooide bestanden zonder bestandsnaam: wat in
  een ingangsmap ligt, verraadt vaak al in de naam waar het om gaat.

  **De bewaking van een map buiten het eigen gebruikersprofiel – bijvoorbeeld
  op een netwerkschijf – vereist een automatiseringslicentie.** Een
  map die meerdere mensen bereiken, is een dienst en geen werkplek; in
  het eigen profiel en tijdens de testperiode geldt de beperking niet.

### Opgelost

- **De instellingen waren rechts afgesneden.** Het venster ging open met
  een vaste grootte, en die volstond alleen voor de lettergrootte
  waarmee ontwikkeld werd: op de Mac stonden „Nu controleren",
  „Wijzigen …" en de aanwijzingen ernaast half erbuiten. Nu opent het
  zo breed als zijn pagina's nodig hebben – in elke taal en bij elke
  lettergrootte, begrensd alleen door het scherm.

- **„Nu controleren" antwoordt nu zichtbaar.** Het resultaat stond in de
  statusregel van het hoofdvenster – dus achter het instellingenvenster
  van waaruit werd gevraagd. Wie controleerde, zag niets. Nu komt het
  antwoord als melding boven de instellingen, en is er een nieuwe
  versie beschikbaar, dan leidt het meteen naar het installeren. Bij
  het opstarten van het programma blijft het zoals voorheen bij de
  statusregel, ongevraagd gaat geen venster open.

- **Gekopieerde bestanden kwamen op de Mac niet op het klembord aan.**
  Het terugleggen van opgeschoonde bestanden meldde succes en legde toch
  niets bruikbaars op – plakken leverde niets op. Getroffen was alles
  wat bestanden op het klembord schrijft.

- **En van het klembord werd op de Mac alleen het eerste bestand
  gelezen.** Wie drie bestanden in de Finder kopieerde en „Klembord nu
  opschonen" koos, kreeg er twee niet opgeschoond terug – zonder dat iets
  dat had gezegd. Nu komen ze allemaal.

- **„Bestand nakijken" neemt nu ook gesleepte bestanden aan** – zoals
  het hoofdvenster. Neergelegde bestanden komen erbij, in plaats van de
  bestaande selectie te verwerpen; hetzelfde tweemaal neerleggen
  verandert niets, en wat het programma niet kan lezen, wordt gemeld
  in plaats van ingeslikt.

- **En het venster zegt dat het op u wacht.** Het ging open met een
  lege ruimte en een grijze knop „Nakijken" – dat ziet eruit alsof er
  niets is, niet alsof de selectie ontbreekt. Nu staat daar „Nog geen
  bestand gekozen – hierheen slepen of onderaan via 'Bestanden
  selecteren …' kiezen."

- **Een lange run zegt nu dat hij loopt.** „Extra model voor de
  nauwkeurigere herkenning wordt geladen – een moment …" bleef staan
  zolang de herkenning rekende: bij een bestand met 47.500 woorden dus
  achttien minuten, hoewel het laden na negen seconden voorbij was. Wie
  dat ziet, houdt het programma voor vastgelopen. Nu volgt daarop
  „Nauwkeurigere herkenning loopt – bij lange teksten duurt dat enkele
  minuten", en de statusregel telt mee: „Nauwkeurigere herkenning
  (7/312)". Gemeld wordt daarbij vanuit de lus van het model – elke 250
  woorden, dus ongeveer elke zes seconden –, niet per tekstblok: een
  tekstblok draagt twaalfduizend woorden en heeft minuten nodig.

- **Een afgebroken run zegt nu dat hij is afgebroken.** Wie „Annuleren"
  indrukte, las daarna „0 van 1 bestand(en) opgeschoond." – correct
  geteld en toch de verkeerde mededeling. De melding welk bestand het
  betrof, werd op hetzelfde moment door de telmelding overschreven. En
  in de bestandslijst stond verder „loopt …", hoewel niets meer liep;
  daar staat nu „afgebroken".

- **De zin over de privacy was afgesneden.** „… geen cloud, geen
  uploaden. Meer in de priva" – bij de vensterbreedte waarmee het
  programma start, eindigde hij midden in het woord. Hij neemt nu de
  volledige breedte.

- **De licentiedienst kon iets meedelen, en niemand luisterde.** Als
  alle licentieplaatsen bezet zijn, de licentie verlopen, de sleutel
  onbekend of het licentiebeheer bij de aanbieder uitgeschakeld,
  stuurt de dienst daarvoor precies een reden – de bedoeling was van
  meet af aan dat u die **eenmaal** te horen kreeg. Getoond werd hij
  nooit. Nu verschijnt een aanwijzing die eerst zegt dat het programma
  ongewijzigd doorwerkt, en dan waar het om gaat. Eenmaal per reden: wie
  hem heeft weggeklikt, ziet hem bij de dagelijkse controle niet terug –
  wel echter als de reden verandert.

- **Een in de shop gekochte meerplaatsenlicentie toonde „1 plaats".** De
  shop verdeelt voorbereide sleutels en houdt het gekochte aantal
  plaatsen zelf bij; getoond werd echter het aantal uit de sleutel
  zelf, en dat luidt bij elke voorraadsleutel op één plaats. Wie acht
  plaatsen had gekocht, las „1 plaats" – en vanaf de tweede aangemelde
  computer stond de weergave in rood samen met „Neem contact op met uw
  beheer". Nu geldt het aantal dat de dienst laatst heeft gemeld;
  zonder antwoord blijft het bij de sleutel, en kleiner dan de gekochte
  omvang wordt het nooit. Hetzelfde geldt voor nabestellingen en
  verlengingen: die wijzigen bij de aanbieder het aantal plaatsen, niet
  uw sleutel.

- **Na de aankoop stond er „Gelicentieerd voor Maskuro Privélicentie".**
  Dat is geen naam, maar de plaatshouder waaronder de sleutels worden
  voorbereid – uw naam kan daar niet staan, omdat de sleutel al vóór de
  aankoop wordt ondertekend. In plaats van u een vreemde naam als de
  uwe te tonen, staat daar nu gewoon „Privélicentie" en het aantal
  plaatsen. Bij een licentie die op uw naam is uitgegeven, staat uw
  naam er ongewijzigd.

- **In het Help-menu stond „Help _FAQ".** Het en-teken was een
  liggend streepje geworden, omdat Qt het las als kenmerk voor een
  toetsenbordletter. Nu staat daar „Help & FAQ".

- **Het instellingenvenster bleef staan wanneer het programma naar het
  symbool verdween** – en ook dan nog wanneer het hoofdvenster werd
  gesloten. Het gaat nu mee. (Betreft alleen deze versie; het eigen
  venster is nieuw.)

- **Een afgewezen licentieverzoek zegt nu waaraan het ligt.** Wees de
  licentiedienst een verzoek af zonder een reden mee te sturen, dan
  stond in het licentievenster in rood „Onbekend antwoord." – een zin
  waarmee noch u noch de ondersteuning iets kan beginnen en die u de
  fout bij uw sleutel laat zoeken. Nu staat daar wat er echt gebeurde:
  dat de dienst heeft afgewezen zonder het te motiveren, en tot wie u
  zich kunt wenden. Is het licentiebeheer bij de aanbieder tijdelijk
  uitgeschakeld, dan wordt ook dat benoemd – samen met de aanwijzing
  dat uw sleutel daardoor niet is getroffen.

- **Op de Mac golden ingerichte talen plotseling als ontbrekend.** Bij
  de start meldde het programma „Er is geen taalmodel geïnstalleerd" en
  bood de eerste inrichting aan, hoewel de talen allang waren geladen –
  wie onder „Talen van de documenten" nakeek, vond ze daar compleet.
  Het programma zocht ze afhankelijk van de startweg op twee
  verschillende plekken: werd het vanuit de map Programma's gestart,
  dan vond het ze; werd dezelfde build als eenvoudige map gestart, dan
  zocht het ze naast zichzelf, waar er geen liggen. Vanaf nu geldt op
  de Mac uitzonderingsloos dezelfde plek in het gebruikersprofiel,
  ongeacht hoe het programma is verpakt. Er hoeft niets opnieuw te
  worden geladen.

- **„Wat is nieuw" toonde de halve lijst.** Het venster na een
  actualisering brak midden in de zin af, en de resterende punten
  stonden als lege opsommingstekens. Schuldig was een plaatshouder
  tussen punthaken – bijvoorbeeld `<bestand>.docx` –, die de weergave
  voor opmaak hield en vanaf waar ze al het volgende verwierp. Juist de
  nieuwigheden over veiligheid waren daardoor getroffen. De hulp toont
  zulke plaatshouders van oudsher correct; dit venster doet dat nu ook.

- **Knijpen met twee vingers zoomt nu in het nabewerkingsvenster.** Op
  het trackpad is dat *het* zoomgebaar – in de editor deed het tot nu
  toe niets, en wie een plek nauwkeuriger wilde bekijken, moest naar de
  regelaar of naar Ctrl+muiswiel grijpen. De pagina volgt het gebaar
  onmiddellijk en wordt bij het loslaten weer scherp getekend.

- **Er wordt gezoomd op de plek die men bekijkt.** Knijpen vergroot rond
  het punt tussen de vingers, Ctrl+muiswiel rond het punt onder de
  aanwijzer. Knoppen, toetsencombinaties en de zoomregelaar houden het
  midden vast – bij hen hoort geen plek waarnaar men wijst. Voorheen
  bleef bij alle alleen de rolwaarde staan: vanuit een ingepaste pagina
  hield dat de bovenrand vast, en alles eronder wandelde bij het
  inzoomen uit beeld.

- **„Voor/na" was in de paginaweergave een dode knop.** Zolang de
  paginaweergave aan was, liet hij zich indrukken – en meldde elke
  keer dat het origineel niet te openen was. Er valt daar ook niets te
  vergelijken: de paginaweergave is een afbeelding van de opgeschoonde
  versie, een tegenhanger van het origineel bestaat niet. De knop is
  nu geblokkeerd en noemt bij het overgaan de reden samen met de
  uitweg (de tekstweergave). Zijn beschrijving beloofde bovendien
  uitdrukkelijk dat de vergelijking werkte „ongeacht of tekst- of
  paginaweergave actief is" – dat klopte nooit.

- **De paginaweergave liet LibreOffice crashen.** Werden twee
  paginaweergaven tegelijk gegenereerd – bijvoorbeeld „Als PDF zwarten"
  terwijl het voorbeeld nog rekende –, dan meldde het systeem een
  LibreOffice-crash, hoewel de pagina's uiteindelijk toch verschenen:
  beide runs grepen naar dezelfde werkopslag van LibreOffice, wat het
  niet verdraagt. Nu krijgt maar één run haar; de overige wijken uit
  naar een eigen. Ze hebben daarvoor een paar seconden langer nodig,
  maar er komt geen foutmelding meer, en geen van de runs blijft zonder
  resultaat. Een tweede renderopdracht naast een lopende wordt bovendien
  helemaal niet meer aangenomen.

- **„Origineel tonen" kon het programma beëindigen.** Liet het origineel
  zich niet openen – omdat het was verplaatst, hernoemd, van een
  wachtwoord voorzien of op een losgekoppelde schijf staat –, dan brak
  het nabewerkingsvenster zonder waarschuwing af, en open werkkopieën
  waren verloren. Nu komt een aanwijzing, de schakelaar springt terug,
  en de opgeschoonde versie blijft staan. Waar het origineel principieel
  niet past – bijvoorbeeld bij een PDF-paginaweergave die uit een
  Word-bestand is ontstaan – is de schakelaar bij voorbaat geblokkeerd
  en noemt bij het overgaan de reden, in plaats van bij elke druk
  dezelfde aanwijzing te tonen.

- **Foutrapporten kwamen nooit aan.** Wie een fout wilde melden, kreeg
  „De tegenpartij heeft het rapport afgewezen" – en niemand had het
  ooit gezien. Twee oorzaken, beide onderweg: het programma
  identificeerde zich niet bij de server en werd daardoor door de
  bescherming tegen massatoegang afgewezen, en het adres verwees naar
  een tweede naam die het programma niet volgde. Beide zijn opgelost;
  een rapport gaat weer naar buiten. **Hetzelfde trof de
  licentieactivering**: aanmelden, afmelden en navragen bereikten de
  dienst evenmin – daar alleen onopvallend, omdat een onbeantwoord
  verzoek bewust niets aan uw licentie verandert. En blijft een
  weigering toch een keer onverklaarbaar, dan staat nu haar technische
  nummer erbij, in plaats van dat elke oorzaak er hetzelfde uitziet.

- **Een klik op „Origineel tonen" kon het programma beëindigen.** Liet
  het origineel zich niet openen – verplaatst, hernoemd, op een
  losgekoppelde netwerkschijf, van een wachtwoord voorzien of
  beschadigd –, dan verdween het nabewerkingsvenster samen met alle
  open werkkopieën. Nu blijft de schakelaar bij de opgeschoonde versie,
  en een kader zegt wat er aan de hand is; de technische reden staat
  in de details, mocht u haar willen melden. Hetzelfde geldt voor een
  resultaat dat zich niet laat weergeven: het venster gaat open en
  zegt het, in plaats van te verdwijnen.

- **De vraag naar een crash kwam te vaak – en wiste het spoor waarnaar
  ze vroeg.** Ze verscheen ook wanneer er niets was gecrasht: de
  aantekening ontstaat zodra ergens een onverwachte storing optreedt,
  ook wanneer het programma ze overleeft en daarna heel gewoon wordt
  afgesloten; opgeruimd werd ze nooit. En wie „Nee" antwoordde,
  vernietigde de enige details van het incident – de aantekening
  verdween al bij het *tonen* van de vraag. Beide zijn opgelost: een
  ordelijk einde ruimt de aantekening op, gevraagd wordt alleen nog na
  een echte afbreking, en afgevinkt wordt pas na uw antwoord. De
  details staan toch al in het foutlogboek op de eigen computer; wie
  niets wil versturen, verliest daardoor toch niets. Verstuurd wordt
  verder alleen wat u vooraf volledig hebt gezien en zelf hebt
  vrijgegeven.

- **„Opschonen" kon stilzwijgend geblokkeerd blijven.** Bleven de
  taalmodellen bij het laden hangen, dan bleef de knop uitgeschakeld –
  zonder uitleg. Een klik erop deed niets, en de statusregel zei
  ongewijzigd „Taalmodellen worden geladen …", ook na tien minuten. De
  oorzaak: storingen in achtergrondprocessen gingen naar een plek die
  bij de start vanuit de bestandsbeheerder niemand ziet; over bleef
  een venster dat werkgereed leek en op geen enkele klik reageerde. Nu
  belanden zulke storingen in het foutlogboek, het laden van de
  taalmodellen meldt zijn mislukking in elk geval in plaats van stil op
  te geven, en blijft het toch stil, dan zegt de toepassing na
  drie kwart minuut dat er iets niet klopt, met een advies in de
  details. De geblokkeerde knop noemt bij het overgaan zijn reden. Een
  lang eerste naladen geldt daarbij niet als stilte: zolang voortgang
  wordt gemeld, blijft het rustig. Als crash telt dit alles niet: de
  toepassing loopt door, en bij de volgende start wordt daarom ook niet
  ernaar gevraagd.

- **Op de Mac vond het programma geen actualiseringen meer – en zei dat
  het op de nieuwste stand was.** De Mac-versie bracht geen register
  van de wortelcertificaten mee; ze zocht het op een plek die alleen
  bestaat op de computer waarop ze wordt gebouwd. Daarmee kon ze bij
  geen enkele server controleren met wie ze sprak, en brak elke
  verbinding af: geen actualiseringen, geen licentieactivering, geen
  naladen van taalmodellen, geen foutrapport. Oudere versies maakten
  daarvan stilzwijgend de mededeling „U gebruikt de nieuwste versie".
  De certificaten zitten nu in het programma zelf; vindt het daar
  geen, dan neemt het die van het systeem en op de Mac in nood die van
  de sleutelhanger – en bestaat er helemaal geen, dan zegt het dat, in
  plaats van een nieuwste versie te beweren. De controle zelf wordt
  daarbij nooit uitgeschakeld.

  Deze ene actualisering moeten Mac-gebruikers nog met de hand
  installeren: een versie die de server niet bereikt, kan zich ook niet
  zelf vernieuwen.

### Gewijzigd

- **Het hoofdvenster is opgeruimd.** Onderaan stonden zes even grote
  knoppen naast elkaar – „Over …", „Handleiding" en „Help & FAQ"
  eronder, hoewel dezelfde drie wegen al in het Help-menu erboven
  stonden. Ze zijn nu samengevoegd tot één knop „Help", die ze opent;
  geen enkele gaat verloren. Onderaan blijven de twee wegen staan
  waarmee men echt begint: „Opschonen" en „Handmatig zwarten …".

- **Wat het programma net doet, staat nu op een vaste plek.** De melding
  („Taalmodellen worden geladen …", „(3 / 7) brief.pdf", „5 van 7
  bestand(en) opgeschoond.") hing tot nu toe als grijze tekst tussen twee
  knoppenrijen. Ze heeft een eigen vlak gekregen, met een gekleurde
  punt ervoor: grijs zolang niets loopt, blauw tijdens het werk, groen
  na een gladde run en geel als er aanwijzingen zijn opgetreden. De
  punt zegt niets wat er niet naast staat – hij zegt het alleen
  sneller.

- **De instellingen zijn een eigen venster geworden.** Ze lagen tot nu
  toe in het hoofdvenster – een kader met vier tabbladen, dat men
  onder „Meer instellingen" openklapte, en dat dan te klein was voor
  zijn inhoud: er stond altijd een schuifbalk in, en de keuze tussen
  anonimiseren en pseudonimiseren stond half in beeld. De knop heet nu
  „Instellingen …" en opent een venster met een zijbalk; elk van de
  vier pagina's past er helemaal in. Het hoofdvenster springt bij het
  openen niet meer open, en men kan de bestandslijst ernaast zien.
  Veranderd is alleen waar de instellingen staan – welke er zijn en wat
  ze doen, is ongewijzigd.

- **„Details" klapt open, in plaats van te springen.** Het venster
  groeide tot nu toe in één keer, en men moest daarna zoeken wat was
  veranderd. Nu beweegt het daarheen.

- **Lettergroottes en afstanden volgen in het hele venster dezelfde
  maat.** Koppen waren op twee plekken verschillend groot, en
  gelijkwaardige regels stonden verschillend ver uit elkaar. Zichtbaar
  is dat als rust, niet als afzonderlijke wijziging.

- **Anonimiseren is nu de standaard.** Tot nu toe was pseudonimiseren
  standaard ingesteld: dezelfde personen kregen hetzelfde nummer
  (`[NAME_1]`, `[NAME_2]`), verbanden bleven leesbaar – juridisch bleven
  het daarmee echter **persoonsgegevens**. Wie niets instelt, krijgt
  nu de procedure die de gegevens uit de AVG haalt: alle treffers van
  een soort heten gelijk (`[NAAM]`). De nummering is een keuze
  gebleven, ze staat ongewijzigd in hetzelfde venster; bestaande
  instellingen blijven zoals ze zijn. Op de opdrachtregel zet
  `--pseudonymisieren` (ook `--mit-nummerierung`) terug.

- **Geanonimiseerde plaatshouders zijn niet meer afzonderlijk terug te
  nemen.** Wie anonimiseert, krijgt voor elke persoon dezelfde
  plaatshouder – en daarmee bestaat er geen afzonderlijke plek meer
  die bij een bepaalde naam hoort. Het nabewerkingsvenster bood toch
  „Vervanging ongedaan maken" aan: een klik zou *een* van de waarden
  op *alle* plekken hebben ingevoegd. De regels zijn nu gedempt zoals
  bij gezwarte gegevens, de klik zegt de reden, en een met de hand
  nagetrokken vondst krijgt geen nummer meer dat verder nergens in het
  document staat.

  Om dezelfde reden bestaat er na een geanonimiseerde run geen
  „Antwoord terugvertalen" meer – voorheen zou dat een vreemde naam op
  de plek van elke persoon hebben gezet. Wie deze lus nodig heeft, kiest
  „Pseudonimiseren"; de toepassing zegt dat nu ook zo, in plaats van
  naar een verlopen toewijzing te verwijzen.

  Op de opdrachtregel breekt `--zuordnung` bij het anonimiseren nu af,
  in plaats van een bestand te schrijven dat geen terugvertaling is –
  in het venster was het vinkje allang geblokkeerd. Ofwel
  `--pseudonymisieren` erbij, ofwel `--zuordnung` weglaten; de melding
  zegt het. Het resultaat ontstaat daarbij helemaal niet, zodat een
  script niet met half werk blijft zitten.

- **Het actualiseringskanaal staat nu opnieuw op „Stabiel".** Zonder
  eigen keuze richtte het kanaal zich tot nu toe naar de build waaruit
  de lopende versie stamde – wie eenmaal een testversie had geprobeerd,
  kreeg vanaf dan blijvend testversies aangeboden. Een kanaalwissel is
  een beslissing en moet dat ook blijven; de standaard is daarom
  „Stabiel". Ingestelde kanalen blijven onaangetast.

### Verbeterd

- **„Klachtenprocedure" geldt niet meer als plaatsnaam.** In de kop
  „Aktenotitie – Klachtenprocedure 12 C 345/26" zwartte het programma
  het proces mee: het taalmodel hield het voor een plaats, en wel
  onafhankelijk van de omgeving. Opgenomen is niet het losse woord,
  maar het **grondwoord** van de samenstelling – „procedure" en
  „notitie" dekken daarmee ook zakelijke, boekings- en betaalprocedure
  of de telefoonnotitie af. Van dertig geteste bestuursbegrippen
  veroorzaakten er voorheen drie een vals alarm, nu geen enkele meer;
  gevonden wordt verder alles wat ernaast staat („Klachtenprocedure:
  Bernd Meisinger" verliest de naam, niet de kop).

- **Anonimiseren houdt weer boek – voor de nacontrole en het logboek.**
  In de anonimiserende werkwijze onthield het programma de gevonden
  waarden niet. Twee dingen bleven daardoor stil: de
  documentbrede consistentie-nacontrole (een achternaam die later
  alleen opduikt, bleef staan) en de lijst met vervangingen in het
  controlelogboek. Zolang anonimiseren de zeldzamere keuze was, viel
  dat nauwelijks op – als standaard zou het het normale geval zijn
  geworden. In het document verandert niets: de plaatshouder blijft
  zonder nummer.

- **„Geen persoonsgebonden datum" heet nu „geen persoonsgegeven".** In de
  terughaaldialoog en in de gezichtenwaarschuwing stond het juridische
  *datum* – het enkelvoud van „gegevens". Het werd gelezen als
  kalenderdag, temeer omdat de toepassing elders „datumaanduidingen
  ook verwijderen" aanbiedt. Het heet nu overal „gegeven", zoals bij de
  vier redenen erboven in hetzelfde venster.

- **De herkomstregel staat alleen nog in het „Over"-venster.** „Made
  with ♥ in Austria" zat onderaan het hoofdvenster midden in de
  knoppenrij en las daar als nog een schakelaar. Ze staat verder in
  het „Over"-venster – daar waar men haar zoekt.

- **Het invoervlak heeft nu een zichtbare rand.** Zijn gestippelde
  rand was zo bleek dat hij nauwelijks van het venster afstak – dat
  maakte niet uit, zolang het vlak slechts een vlak was. Sinds het een
  bedieningselement is dat men met de tabtoets kan aanspringen, is
  deze lijn het enige wat het als bedieningselement toont; hij is
  daarom verhoogd naar de waarde die de norm daarvoor vereist.

## 0.10.22-beta.1 – 15 augustus 2026

### Nieuw

- **Wordt de klembordbewaking uitgeschakeld, dan is ze echt uit.** De
  wachter houdt de laatste inhouden in het geheugen, zodat het origineel
  kan worden teruggelegd – tot nu toe ook nog als u de bewaking had
  uitgeschakeld. Nu wordt de geschiedenis bij het uitschakelen vergeten.
  Dat kost de herstelling na het uitschakelen, en precies zo is het
  bedoeld: uitgeschakeld betekent uitgeschakeld.
- **Het foutlogboek bevat geen bestandspaden meer.** Het stond alleen op
  uw computer en werd nooit vanzelf verzonden – maar het voerde paden in
  klare tekst, en een bestandsnaam verraadt vaak meer dan de inhoud. Van
  „…/Scheiding_Mueller_Vergelijk.docx" wordt nu bij het schrijven
  `<bestand>.docx`; de extensie blijft, omdat ze bij het foutzoeken
  telt. Hetzelfde geldt voor de aantekening na een crash.
- **De lijst met vervangingen waarschuwt nu in zichzelf.** Ze is het
  enige bestand waarin uw originele gegevens in klare tekst staan, en
  ze ligt naast het resultaat – wie een map doorgeeft, geeft haar mee.
  Nu staat de waarschuwing als eerste regel **in** het bestand, het
  uitvoergebied noemt het volledige pad in plaats van alleen de
  bestandsnaam, en op de opdrachtregel wordt het bestand er überhaupt
  pas genoemd: daar wist men tot nu toe helemaal niet dat het is
  ontstaan.
- **Anonimiseren of pseudonimiseren is nu een benoemde keuze.** Op die
  plek stond tot nu toe een vinkje „Dezelfde namen gelijk benoemen – de
  AI herkent dan nog wie wie is". Dat beschreef het nut en verzweeg het
  gevolg: doorgenummerde plaatshouders (`[NAAM_1]`, `[NAAM_2]`) zijn
  **pseudonimisering**, en gepseudonimiseerde gegevens blijven
  persoonsgegevens – wie dacht daarmee te hebben geanonimiseerd, had
  het mis. Nu staan beide procedures naast elkaar, elk met zijn prijs.
  De standaard blijft pseudonimiseren, omdat een document dat daarna
  nog wordt gelezen of door een AI verwerkt, zijn verbanden nodig heeft.
  Bij het anonimiseren is de lijst met vervangingen geblokkeerd: ze zou
  het resultaat weer herleidbaar maken. Handboek en FAQ leggen het
  verschil uit in alle 18 talen; op de opdrachtregel heet de schakelaar
  nu ook `--anonymisieren`.
- **De regel boven het invoervlak zegt nu wat werkelijk klopt.** Ze
  beloofde „100 % lokale verwerking – zonder cloud en account,
  AVG-vriendelijk". Voor uw documenten klopt dat, voor het programma
  niet in die algemeenheid: het zoekt naar actualiseringen, meldt op
  verzoek fouten, laadt modellen na en meldt gekochte werkplekken aan.
  Nu staat daar de nauwere en houdbare uitspraak: uw documenten
  verlaten de computer niet.
- **Bij het resultaat staat nu altijd dat het gecontroleerd moet
  worden.** Tot nu toe meldde Maskuro na een gladde run „12 gegeven(s)
  verwijderd" in groen en verder niets – dat leest als een garantie
  alles te hebben gevonden. Aanwijzingen verschenen alleen als concreet
  iets niet gecontroleerd kon worden (afbeeldingen, onbekende
  bijlagen). Nu staat onder elk resultaat onmiskenbaar dat niet in elk
  geval alle persoonsgegevens worden herkend, dat de controle bij de
  gebruiker ligt en dat wat ontbreekt met de hand moet worden
  aangevuld – in het venster, in het uitvoergebied en op de
  opdrachtregel. Geen meldingsvenster om weg te klikken: de zin staat
  er blijvend. De snelstartgids zegt het nu in dezelfde bewoordingen.
- **Na een actualisering staat bij het opstarten wat er is veranderd.**
  Tot nu toe verliep een actualisering stil en was ze niet van een
  herstart te onderscheiden. Nu verschijnt eenmalig „Wat is nieuw" – en
  wie een versie heeft overgeslagen, ziet die daartussen mee. Niet bij
  de allereerste start: daar leidt nog steeds de snelstartgids in.
- **Chinees en Japans vinden nu namen.** Tot nu toe vonden ze er
  **geen** – niet weinig, geen. Beide taalmodellen misten de
  woordsegmentatie, zonder welke een zin zonder spaties als één enkel
  woord geldt; het programma week stilzwijgend uit naar het meertalige
  vervangmodel. Beide talen herkennen nu personen en plaatsen zoals de
  overige. Het Japanse woordenboek wordt daarbij samen met de taal
  geladen en zit niet in het programma – het alleen zou al zo'n 200 MB
  zijn, die anders iedereen had meegedragen.
- **Roemenië is als land te kiezen.** Het ontbrak tot nu toe helemaal.
  Daarmee worden Roemeense adressen („Strada Victoriei 30"), postcodes
  met plaats („010061 București") en de Cod Numeric Personal herkend –
  laatstgenoemde alleen met kloppend controlecijfer, zodat niet elk
  dertiencijferig getal op een factuur wordt aangestreept. Tot nu toe
  bleef in Roemeense documenten de postcode naast de gezwarte plaatsnaam
  leesbaar staan.
- **„Pagina rasteren" in de editor.** Kan tekst uit een PDF niet worden
  verwijderd – dat komt voor bij bestanden van vreemde makers –, dan
  wordt de pagina nu op verzoek door haar afbeelding vervangen: de
  tekst is daarmee onherroepelijk weg, de pagina blijft leesbaar en
  doorzoekbaar. De waarschuwing die het geval meldt, biedt de stap
  meteen als knop aan; via „Werktuigen → Pagina rasteren" gaat het ook
  vanzelf. Ongedaan maken haalt de pagina terug.
- **De interface is er nu ook in het Kroatisch, Grieks, Litouws,
  Sloveens, Japans en Koreaans.** Daarmee zijn het achttien talen.
  Handboek, FAQ en juridische teksten zijn in alle zes volledig
  aanwezig. De beschrijvingen in het opgeschoonde document volgen daarbij
  de interface – van `[NAME_1]` wordt `[IME_1]`, `[ΟΝΟΜΑ_1]`,
  `[VARDAS_1]` of `[氏名_1]`. **Bij Grieks, Japans en Koreaans staan de
  beschrijvingen in Latijns schrift** – `[ONOMA_1]`, `[SHIMEI_1]`,
  `[IREUM_1]`. De interface blijft in haar eigen schrift; alleen wat in
  het document wordt geschreven, is Latijns. Reden is de PDF-tekenset:
  daar kwamen Griekse en Japanse beschrijvingen voorheen als `[??_1]`
  aan, en daarmee was naam niet meer van plaats te onderscheiden.
- **Negen landen komen erbij, en zeven bestaande worden volledig.**
  Nieuw herkend worden identiteits-, belasting- en
  socialezekerheidsnummers samen met adressen voor **Kroatië, Slovenië,
  Griekenland, Litouwen, Noord-Macedonië, Rusland, Oekraïne, China en
  Japan**. Bij de bestaande landen zijn gaten gedicht die zwaarder
  wogen: voor **Nederland** en **Portugal** was er tot nu toe helemaal
  geen persoonsnummer – het Nederlandse BSN en de Portugese NIF werden
  niet herkend, hoewel ze op vrijwel elk document van die landen staan.
  Polen krijgt het belastingnummer NIP, Denemarken, Noorwegen en
  Finland hun adressen, Canada zijn postcode. Daarmee zijn het **35
  landen**.

### Verwijderd

- **Voor Linux is er voorlopig geen pakket meer.** De broncode werkt
  daar, maar drie dingen die deze handleiding belooft, ontbreken onder
  Linux: automatisch opstarten, globale toetsencombinaties en –
  afhankelijk van de werkomgeving – het symbool in de balk. Een pakket
  uitleveren dat minder kan dan beschreven, zou de verkeerde weg zijn.
  Windows en macOS zijn onaangetast.

### Verbeterd

- **Dossiernummers worden nu in alle talen gevonden.** „Dossiernummer
  12/2026-AB" werd verwijderd, „File reference 12/2026-AB" of
  „Sygnatura 12/2026-AB" bleven staan: de veldwoorden waaraan Maskuro
  zo'n nummer herkent, bestonden alleen in het Duits. Nu kent het de
  equivalenten in twaalf talen – en zoals voorheen wordt alleen het
  nummer vervangen, de beschrijving ervoor blijft staan, zodat in het
  resultaat herkenbaar is wat daar werd verwijderd.
- **Maskuro gebruikt in rust ongeveer een half gigabyte minder.** Bij de
  start werd tot nu toe ook het extra model van de nauwkeurigere
  herkenning geladen, zodat de eerste opschoning daar niet op hoeft
  te wachten. Nagemeten kostte dat 648 MB geheugen en bespaarde 1,9
  seconden – en het kostte dat ook wanneer u het venster alleen opende
  en weer sloot. Het model wordt nu de eerste keer geladen wanneer het
  nodig is; de statusregel meldt het. Het taalmodel wordt verder bij de
  start geladen – dat heeft de klembordbewaking meteen nodig.
- **Het invoervlak is nu ook zonder muis te bedienen.** „Bestanden
  hierheen slepen" was een vlak dat op klikken reageerde – met het
  toetsenbord kwam men er niet, en een schermlezer las het voor als
  kader met tekst erin, niet als wat het is. Het is nu een
  bedieningselement: de tabtoets springt erop, spatie- en entertoets
  openen de bestandskeuze, en wie erop is gesprongen, ziet het aan de
  rand. Via het menu „Bestand → Bestanden selecteren" ging het al
  eerder, maar dat moest men weten.
- **De naam van het opgeschoonde bestand wordt nu ook voorgelezen.** In de
  bestandslijst staat hij als tweede, kleinere regel onder het
  origineel – maar hij was daar alleen getekend, en een schermlezer
  noemde alleen het origineel. Juist deze regel is gebouwd tegen de
  vergissing dat een run zonder effect was omdat in de map het
  onaangetaste origineel ligt. De regel luidt nu voorgelezen
  „rekening.pdf, resultaat: rekening_opgeschoond.pdf".
- **Bedieningselementen zonder opschrift zeggen nu waarvoor ze dienen.**
  De symboolknoppen in de bestandslijst, de tekenknoppen in het
  nabewerkingsvenster en alle keuze- en invoervelden waren voor
  schermlezers naamloos – ze werden aangekondigd als „knop" en
  „combinatieveld", zonder waarvan. De knoppen bij een regel noemen
  daarbij het bestand mee: in een lijst met twintig items hoorde men
  anders twintig keer dezelfde zin.
- **Wie met het toetsenbord bedient, ziet weer waar hij staat.** De
  „Opschonen"-knop en de symboolknoppen in de bestandslijst zijn kleurig
  vormgegeven, en daarmee hield het kader op dat het systeem anders om
  het aangesprongen bedieningselement legt – bij het doortabben sprong
  de blik in het niets. Beide hebben nu een eigen kader zodra ze aan
  de beurt zijn. De knoppen veranderen daarbij niet van grootte.
- **Zeven lettertypekleuren waren te bleek, in beide weergaven.**
  Nagemeten volgens de gebruikelijke norm (WCAG 2.1) lagen de bleke
  aanwijsregels, de bijteksten op de invoerzone, de punten van de
  handleiding en in het donkere beeld bovendien het blauw en het rood
  onder de grens van 4,5:1 – leesbaar bij goed licht en goed oog,
  anders niet. Alle zijn verhoogd; de gradatie blijft, de teksten lezen
  verder als bijteksten. Drie andere – de kleuren waarin
  waarschuwingen en succes worden gemeld – hielden de grens maar net
  en zijn meegetrokken: wie ze niet leest, leest niet of iets is
  misgegaan. Zichtbaar veranderd is daarbij alleen de
  „Opschonen"-knop in het donkere beeld: hij draagt nu donkere in
  plaats van witte letters, zoals de accentknoppen van Windows 11 ook.
- **Elke regel van de bestandslijst heeft nu haar eigen kruis.** Tot nu
  toe moest men eerst de regel selecteren en dan op „Verwijderen"
  klikken – twee stappen voor een kleinigheid. Het kruis staat rechts
  in de regel en heeft er een nodig. De knop „Verwijderen" eronder is
  daarmee vervallen; wie meerdere regels in één keer kwijt wil, selecteert
  ze en neemt het item in het contextmenu, dat ook zegt hoeveel het er
  zijn. „Alles verwijderen" blijft. Uit de lijst wordt altijd alleen de
  regel gehaald – nooit een bestand van de schijf.
- **Vóór de AI-controle staat nu of deze computer daarvoor geschikt
  is.** Tot nu toe stond in het venster alleen hoe groot het model is.
  Wie het op een zwakke computer inschakelde, merkte pas bij het eerste
  document dat het heel lang duurt – na 5,4 GB download. Nu noemt het
  venster **vooraf** geheugen en vrije ruimte en zegt wat dat betekent;
  **achteraf** wordt de snelheid gemeten en genoemd in de grootte
  waarom het gaat: „Een document van tien pagina's duurt op deze
  computer ongeveer 12 minuten." Is het te traag, dan raadt het
  programma het af en biedt aan het niveau weer uit te schakelen –
  verbieden doet het niets.
- **De snelheidsmeting loopt nu op elke computer.** Tot nu toe kwam ze
  alleen als bovendien de grafische versnelling was ingericht – die
  bestaat alleen onder Windows. Op alle andere computers schatte het
  programma de duur daarom aan de hand van een vreemde computer, en
  juist waar het traag is, lag de schatting ernaast.
- **Turkse adressen worden ook in de scan gevonden.** Op een
  ingescande briefkop bleef „34710 İstanbul" leesbaar staan, terwijl
  dezelfde aanduiding in de tekst ernaast verdween: de tekstherkenning
  leest de Turkse İ zonder haar punt, en het patroon verwachtte een
  hoofdletter. Hetzelfde gold voor „Bağdat Caddesi".
- **Spaanse adressen zonder eigen straatnaam worden gevonden.** „Gran
  Vía 5" bleef staan, omdat het patroon achter het straattype nog een
  naamwoord verwachtte – bij „Calle Mayor" is er een, bij „Gran Vía" is
  het type zelf al de naam. Hetzelfde geldt nu voor „La Rambla" en
  „Castellana".
- **In het venster „Over dit programma" staat nu een
  transparantieaanwijzing** over het feit dat de toepassing met
  ondersteuning van kunstmatige intelligentie is ontwikkeld. Ze betreft
  het ontstaan van het programma, niet zijn werkwijze: opgeschoond wordt
  verder uitsluitend op de eigen computer.
- **„Talen beheren" toont nu de bruikbare talen eerst.** Voor de helft
  van de 48 talen is er geen eigen taalmodel; daar herkent een
  meertalig vervangmodel namen slechts zwak, in sommige schriften
  helemaal niet. Naast elkaar in een lijst zagen alle er
  gelijkwaardig uit. De standaard toont daarom alleen nog talen met
  eigen model – via „Weergegeven" zijn de overige altijd in te blenden,
  met een zin over wat ze kunnen en wat niet. Er valt niets weg, en wie
  een beperkte taal heeft ingericht, behoudt haar.
- **De vraag naar een ontbrekende taal noemt nu de uitweg.** Wordt een
  taal herkend waarvoor nog niets is ingericht, dan bood het programma
  tot nu toe alleen „Laden" of „Zonder doorgaan" aan. De herkenning kan
  echter mis zijn – bij korte formulieren en lijsten met weinig lopende
  tekst beslissen weinige woorden. In het venster staat daarom nu dat
  men kan afbreken en de juiste taal met de hand kan kiezen, in plaats
  van „Automatisch herkennen" te gebruiken. Dat bespaart in twijfel een
  download van enkele honderden megabytes voor een taal die helemaal
  niet nodig is.
- **Plaatshouderbeschrijvingen spreken nu de interfacetaal.**
  „[NAAM_1]", „[ADRES_2]" & co. stonden tot nu toe altijd in het Duits,
  ongeacht welke taal was ingesteld of in welke taal het document is
  opgesteld. Nu volgen ze de interfacetaal – bij Engels dus „[NAME_1]",
  „[ADDRESS_2]". Niet de documenttaal: die is bij „automatisch
  herkennen" geraden en soms fout; de interfacetaal is dat nooit.
- **Minder nadere vragen bij het nabewerken.** Waar het resultaat wordt
  opgeslagen, staat nu blijvend onderaan in de balk
  („→ contract_opgeschoond.pdf", in de tooltip de map) – een klik erop
  kiest een andere plek, zonder meteen op te slaan. De nadere vraag bij
  het eerste opslaan vervalt daarmee. De vraag „al bewerkt – opnieuw
  beginnen?" kan voor de sessie worden onthouden, en twee
  informatievensters die alleen een mededeling gaven, staan nu in de
  statusregel. Gebleven zijn de vragen die onherroepelijke schade
  voorkomen: het niet-opgeslagen werk bij het sluiten en de
  waarschuwing over niet-verwijderde tekst.
- **Het resultaat zegt nu waar de scan zelf niet leesbaar was.** Op een
  ingescand document leest de tekstherkenning van het apparaat niet
  alles correct – van „Zonnestraat 9" wordt dan bijvoorbeeld
  „Zonneetr^aa« 9". Wat zo verkeerd gelezen werd, kan geen controle
  meer vinden: het ziet er voor elk zoekpatroon uit als letterbrij. Het
  programma kan daar niets aan veranderen, benoemt zulke plekken nu
  echter met paginanummer – meestal zitten daar stempels, briefkoppen
  of handgeschreven toevoegingen. Een aanwijzing, geen waarschuwing:
  bij een gezet document blijft ze weg.
- **De bestandslijst toont nu hoe het resultaat heet.** Onder de
  bestandsnaam staat na de run de naam van het opgeschoonde bestand
  („→ contract_opgeschoond.pdf"). Tot nu toe stond die alleen in het
  logboek achter „Details", en wie in de map keek, vond het
  onaangetaste origineel. De naam van de bron blijft staan – anders
  zou niet meer te zien zijn uit welk bestand een resultaat komt.
- **De knoppen in een voltooide regel zijn groter en duidelijker.**
  Bekijken, nabewerken en „In map tonen" waren platte symbolen zonder
  vlak en gingen in de lijst onder – terwijl ze na de run het enige
  zijn dat men nog aanklikt.

### Opgelost

- **Op een anderstalige interface werden eigen regels voor zwarten,
  maskeren en hashen stilzwijgend genegeerd.** Wie had vastgelegd dat
  namen moesten worden gezwart in plaats van vervangen, kreeg ze toch
  vervangen – zodra het programma niet in het Duits of Engels werd
  bediend. De instelling stond er, ze werkte alleen niet, en in het
  resultaat was het verschil niet te zien. Getroffen waren negen van de
  twaalf interfacetalen.
- **De instelling „Taal van de beschrijvingen" had buiten Duits en
  Engels geen effect.** „Duits" en „Engels" waren te kiezen, in het
  document stond echter verder de taal van de interface. Nu werken alle
  drie mogelijkheden; de standaardinstelling „zoals de interface"
  levert ongewijzigd hetzelfde als voorheen.
- **In korte tekstfragmenten bleven namen staan – bijvoorbeeld in een
  gekopieerd mailcitaat.** Wie een fragment via het klembord
  opgeschoonde, kreeg daar vaak alleen het e-mailadres gezwart, de naam
  eronder niet. Doorslaggevend was het pure aantal regels: vanaf zes
  regels herkende het programma het fragment als opsomming en vond de
  namen, daaronder niet – een gekopieerd mailcitaat heeft er vijf. Een
  willekeurige extra regel, bijvoorbeeld een onderwerp, kantelde het
  resultaat. Nu volstaan vier regels, en in de meting verdwijnen alle
  gecontroleerde namen in plaats van een derde. Op langere documenten
  en op lopende tekst heeft dit geen effect.
- **De grafische versnelling van de AI-controle werd tot nu toe weer
  uitgeschakeld zodra men haar had ingericht.** Na het inrichten meet
  het programma of de grafische kaart op deze computer echt sneller is
  dan de processor – deze meting mislukte echter altijd, zonder het te
  zeggen, en het resultaat „allebei even snel" besliste voor de
  processor. Wie de 65 MB had geladen, kreeg daarna minder dan
  voorheen. De meting loopt nu; mislukt ze, dan verandert ze niets
  meer.
- **De tijdschatting rekende op elke computer met een vreemde
  snelheid.** Ze steunt op dezelfde meting; zolang die niet liep, gold
  de waarde van de ontwikkelcomputer. „Ongeveer twee minuten" kon
  daarmee op een trage computer een half uur betekenen.
- **Het AI-niveau werkt met een nieuw, aanzienlijk beter taalmodel**
  (Qwen3.5-9B in plaats van Qwen3-4B) en is niet meer beperkt tot Duits
  en Engels, maar werkt in twaalf talen. Gemeten aan het controlecorpus:
  evenveel gevonden gegevens als zonder het niveau, maar minder dan
  half zoveel overbodige zwartingen (75 → 31). Het model is groter (5,4
  in plaats van 2,4 GB) en heeft ongeveer het dubbele van de rekentijd
  nodig; bij het inschakelen wordt het eenmalig geladen, waarbij het
  oude wordt verwijderd.
- **Adressen in het Frans, Italiaans, Spaans, Portugees, Pools, Turks en
  Zweeds worden nu volledig verwijderd.** Tot nu toe verdween daar
  alleen de straat- en plaatsnaam – huisnummer en postcode bleven
  leesbaar staan („[PLAATS_1] 28, 28013 [PLAATS_2]"). Voor deze talen
  bestonden er geen eigen adrespatronen; ze zijn nu aangevuld.
- **Grieks en Koreaans vonden helemaal geen namen.** Bij Grieks lag het
  aan het vervangmodel – met het eigen model, dat nu geladen kan
  worden, worden namen en plaatsen zuiver herkend. Bij Koreaans lag het
  aan het programma: het veronderstelde dat een naam met een
  hoofdletter begint, en Hangul kent geen hoofdletters. Getroffen waren
  vooral korte eenheden – tabelcellen, formuliervelden,
  lijstvermeldingen.
- **Een taalmodel dat niet kon worden geladen, brak de opschoning
  af.** In plaats van een foutmelding springt nu het meertalige model
  bij, en het resultaat wijst erop dat met de zwakkere herkenning is
  gewerkt. Betreft momenteel Chinees en Japans, waarvan de modellen een
  woordsplitsing nodig hebben die het programma nog niet bijlevert.
- **Een taal met eigen model gold als geïnstalleerd zodra een willekeurige
  andere was geladen.** Wie bijvoorbeeld Turks inrichtte, kreeg daarmee
  het meertalige vervangmodel – en Chinees, Japans, Koreaans of Grieks
  stonden daarop met gezet vinkje en „0 MB" in de lijst, hoewel hun
  eigen model ontbrak. Ze waren daardoor nooit na te laden en werkten
  blijvend met de zwakkere vervanger. Nu toont de lijst de werkelijke
  stand samen met de laadgrootte.
- **Een uitgevallen herkenningsniveau zweeg.** Was „Uitgebreide
  herkenning" of „Maximale herkenning (AI)" ingeschakeld, maar liet het
  model zich niet uitvoeren, dan werkte het programma zonder dit
  niveau verder – zonder een woord daarover. Het resultaat zag eruit
  als elk ander, en de schakelaar stond nog op „aan": men hield het
  resultaat van het basisniveau dus voor het beste wat te halen viel.
  Het resultaat zegt het nu en noemt beide – wat niet werd
  gecontroleerd en hoe het model opnieuw kan worden geladen. Het geval
  is niet zeldzaam: op sommige computers mislukt het AI-niveau bij het
  laden, als de grafische versnelling ontbreekt.
- **Een fout bij het laden van het extra model brak de hele opschoning
  af.** Bij „Uitgebreide herkenning" was alleen de evaluatie van het
  model afgeschermd, niet het inlezen ervan – en juist daar gaat het
  mis als het bestand beschadigd is of niet bij de computer past. In
  plaats van een foutmelding is er nu een resultaat van het basisniveau
  samen met een aanwijzing.
- **Een taal liet zich niet meer verwijderen – en daarmee ook niet
  opnieuw laden.** Wie in „Talen beheren" het vinkje wegnam en de
  wijziging overnam, las „Duits verwijderd", zag het vinkje echter
  meteen weer gezet. Oorzaak was de overname uit de programmamap: bij
  een installatie voor alle gebruikers liggen de taalmodellen
  schrijfbeveiligd in de programmamap, en het programma haalt
  ontbrekende daar vandaan, in plaats van honderden megabytes opnieuw
  te laden. Deze overname liep bij elke toegang mee – en kopieerde de
  net verwijderde taal in dezelfde adem terug. Ze gebeurt nu eenmalig;
  nageladen taalmodellen blijven daarbij behouden. Bovendien kijkt het
  programma na het verwijderen na: wat niet verwijderd kon worden,
  wordt nu als mislukking gemeld in plaats van als „verwijderd".
- **Bij een installatie voor alle gebruikers kon nageladen materiaal
  niet worden opgeslagen.** Wie het programma voor alle gebruikers
  installeert, heeft het in „Programma's" staan, en daar mag zonder
  beheerdersrechten niets naartoe worden geschreven. Voor de
  taalmodellen was daarvoor al lang een uitwijkplaats voorzien, voor
  ander materiaal niet:
  - De **paginaweergavecomponent** werd na 290 MB download in de
    programmamap uitgepakt en mislukte daar – zonder een reden te
    noemen. Ze ligt nu bij de taalmodellen, waar ze volgens de bedoeling
    altijd had moeten liggen.
  - De **grafische versnelling** kan niet uitwijken: ze verwisselt
    bibliotheken in het programma zelf. In plaats van eerst te laden en
    dan zonder woord te mislukken, zegt het programma nu vooraf dat het
    hier niet gaat en wat dat betekent – de maximale herkenning werkt
    verder, alleen via de processor.
  - Een meegeleverde **taal van de tekstherkenning** liet zich niet
    verwijderen: ze werd uit de programmamap meteen weer hersteld.
    Dezelfde oorzaak als bij de taalmodellen, dezelfde oplossing.
  - Bij het verwijderen van een taal konden **taalgegevens van een
    vreemde Tesseract-installatie** worden gewist. Aangeraakt wordt nu
    alleen nog de eigen map.
  - De uitwijkplaats gold tot nu toe alleen onder Windows. Een
    Linux-archief naar `/opt` had dezelfde nood zonder dezelfde uitweg.
- **Bij het nabewerken verdween een hele regel, hoewel maar één woord
  was omkaderd.** Wie in een al opgeschoond bestand een plaatshouder
  zwartte, verloor de regel waarin hij stond: van „Geachte mevrouw
  doctor [NAAM_1]" bleef niets over – en de melding zei daarbij „één
  woord uit het document verwijderd". Getroffen was elk bestand dat al
  eens door het programma was gegaan, dus juist het geval waarvoor het
  nabewerken bestaat. De overige tekst blijft nu staan, op ongewijzigde
  plek.
- **„EMPLOYEES" boven een namenlijst werd zelf gezwart.** Hetzelfde
  geval als „MITARBEITER" in 0.10.19, alleen in het Engels – daar was
  het blijven staan. In hoofdletters ontbreekt het taalmodel het
  onderscheidende kenmerk, en de kop staat boven louter echte namen. De
  namen eronder worden verder gevonden. Niet opgenomen werd „staff":
  dat is een bestaande achternaam, en het item zou elke „John Staff"
  meenemen – dezelfde afweging als destijds bij „Arbeiter".
- **De rechtsvorm werd een tweede keer vervangen.** Op een ingescande
  briefkop las het taalmodel „GmbH", het adres en de postcode als
  **één** plaats. Adres en postcode sneden daarna hun stukken eruit, en
  over bleef de rechtsvorm als eigen treffer: in het resultaat stond
  „[PLAATS_1] [PLAATS_2]", waar „[PLAATS_1] GmbH" bedoeld was. De
  bedrijfsnaam wordt verder vervangen – alleen de kale toevoeging
  blijft nu staan, en het resultaat leest als een briefkop in plaats
  van als een invuloefening.
- **Een toegeknipte treffer werd niet opnieuw gecontroleerd.** De
  oorzaak van het geval hierboven, en die reikt verder: de filters
  tegen geraden treffers liepen op wat de herkenners **melden** – niet
  op wat na de overlappingsoplossing overblijft. Wordt een lange
  treffer door een sterkere herkenner beknot, dan is het fragment een
  andere tekst dan de beoordeelde, en niemand keek er nog een keer naar.
  Nu wel.
- **„U gebruikt de nieuwste versie" – hoewel helemaal niet kon worden
  nagekeken.** Wie als actualiseringskanaal „Preview (bèta)" of
  „Stabiel – aanbevolen" had ingesteld, kreeg die mededeling, terwijl
  op die kanalen tot dan toe helemaal niets was verschenen. Nu zegt het
  programma precies dat – en stelt voor in de instellingen een ander
  kanaal te kiezen.
- **Het venster tijdens het laden sluiten liet een thread crashen.** Wie
  Maskuro startte en het venster meteen weer dichtdeed terwijl de
  taalmodellen nog werden geladen, kreeg in het logboek een
  foutrapport: het laadproces meldde zich bij een venster dat er niet
  meer was. Zichtbare gevolgen had dat niet, maar in het logboek stond
  een crash, waar alleen iemand sneller was dan het programma.
- **Het resultaat wordt nu bekeken, niet alleen nagelezen.** Tot nu toe
  gold een pagina als schoon wanneer de waarde niet meer in de tekst
  stond. Op een scan is dat geen bewijs – daar is de zichtbare tekst
  een afbeelding. Ten slotte wordt daarom nagekeken of het vlak in het
  resultaat echt gezwart is; staat daar nog wit papier, dan zegt het
  rapport dat uitdrukkelijk, in plaats van „vervangen" te melden.
- **Een vervangen gegeven bleef in de afbeelding staan.** Stond de
  waarde op een afbeelding – een ingescande briefkop, een stempel, een
  hele gescande pagina –, dan werd ze wel uit de documenttekst
  verwijderd, maar bleef ze verder **zichtbaar**: wat de mens leest,
  zijn daar beeldpunten. Het rapport meldde toch „vervangen". Nu wordt
  het vlak in de afbeelding gezwart, ongeacht welke strategie is
  ingesteld, en de plaatshouder staat licht op deze grond – lelijk,
  maar eerlijk, en de toewijzing blijft behouden. Laat een
  beeldformaat zich niet bewerken, dan zegt het resultaat dat nu
  uitdrukkelijk, in plaats van er schoon uit te zien.
- **Op een scan ontbrak de plaatshouder helemaal.** De tekstlaag van een
  gescande pagina wordt onzichtbaar getekend, en een plaatshouder die
  erin werd ingevoegd, erfde dat: gezet, maar niet te zien. Op de
  vindplaats stond daarna niets.
- **Een tekstherkenning die helemaal niet kon lopen, gold als
  geslaagd.** Ontbrak het taalbestand of brak de herkenningsmachine af,
  dan meldde het rapport „Afbeelding(en) … zijn met tekstherkenning
  gecontroleerd (0 vindplaats(en))" – dus een controle die nooit
  plaatsvond. Bij een scan is dat de enige controle überhaupt: een
  contract met leesbaar adres in het pagina-beeld gold daarmee als
  klaar. Nu zegt het rapport dat niets werd gecontroleerd, en waarom.
- **Het taalbestand werd in de verkeerde map gezocht.** Lagen in de
  eigen taalmap andere talen dan die van het document, dan kreeg de
  herkenningsmachine precies die map voorgeschoteld en mislukte – hoewel
  de passende taal ernaast lag. Gezocht wordt nu naar de **taal**, niet
  naar de map.
- **De waarschuwing over niet-verwijderde tekst raadde iets aan dat niet
  bestaat.** Ze verwees naar „Als PDF zwarten" – dat maakt echter een
  PDF-weergave van *Office*-bestanden en is bij een PDF helemaal niet
  beschikbaar. Wie de waarschuwing wilde volgen, zocht tevergeefs. Nu
  staat daar de knop die de zaak regelt.
- **In de editor kwamen balken en plaatshouders naast de gemarkeerde
  plek terecht.** Getroffen was elke PDF waarin een regel op een
  koppelteken eindigt en het woord in de volgende doorloopt – bij scans
  valt dat vooral op, omdat contractteksten doorgaans afgebroken zijn
  gezet. De twee regelhelften golden als *één* woord dat dwars over de
  zetspiegel reikt, en elk kader in zijn buurt nam die uitgebreidheid
  over. De herkenning zelf verandert daardoor niet: het meetcorpus
  levert hetzelfde resultaat als voorheen.
- **De editor waarschuwde dat de tekst „nog steeds in het document"
  stond, hoewel hij verwijderd was.** Kwam hetzelfde woord meermaals op
  een pagina voor – in contracten de regel –, dan meldde de
  zelfcontrole na elke ingreep een mislukking. Ze telt nu de
  voorkomens, in plaats van alleen na te kijken of het woord nog ergens
  staat. Bij een echte mislukking waarschuwt ze ongewijzigd.
- **Het resultaatbestand heette in elke taal „_bereinigt".** Bedoeld was
  altijd dat de naamtoevoeging de interfacetaal volgt – in het Engels
  gebeurde dat ook („_cleaned"), in de overige zestien talen niet. Wie
  het programma in het Fins gebruikte, kreeg
  „asiakirja_bereinigt.pdf". Nu heet het bestand
  „asiakirja_puhdistettu.pdf", in het Japans „書類_除去済み.pdf" enzovoort
  – telkens met het woord dat diezelfde interface in haar
  voltooiingsmelding gebruikt. Wie een eigen toevoeging heeft ingesteld,
  behoudt haar.
- **„Talen beheren" beschreef zich altijd in het Duits.** In de lijst
  van de 48 documenttalen stonden de Duitse namen, ongeacht welke
  interface was ingesteld: een Finse gebruiker las „Chinesisch". Nu
  staat daar de naam in zijn taal en daarachter de eigen naam – „Kiina
  (中文)". De eigen naam is opzet: wie de taal aan zijn eigen naam
  herkent, vindt haar ook als het Finse woord hem niets zegt.

## 0.10.19 – 12 augustus 2026

### Verbeterd

- **Het item in het contextmenu spreekt nu uw taal.** Tot nu toe stond
  daar op elk systeem de Duitse tekst – ook op een Engelse Windows. Nu
  volgt het de ingestelde interfacetaal, en wie de taal omzet, krijgt
  het item meteen omgedoopt, zonder opnieuw te installeren. (Windows;
  onder macOS en Linux is de menunaam tegelijk een bestandsnaam – dat
  komt later.)
- **De editor onthoudt in welke weergave u het laatst hebt gewerkt.**
  Wie de paginaweergave gebruikt, krijgt die bij het volgende document
  vanzelf – zonder haar telkens in te schakelen. Wie haar nooit heeft
  gebruikt, merkt daar niets van: ze wordt alleen hersteld als de
  daarvoor benodigde bouwsteen al geladen is, nooit wordt daarvoor iets
  nageladen.

### Opgelost

- **„MEDEWERKER" boven een namenlijst werd zelf gezwart.** In
  personeelsregisters en organigrammen verdween de kop als vermeende
  naam – hij staat daar boven louter echte namen, en in hoofdletters
  ontbreekt het taalmodel het onderscheidende kenmerk. De namen eronder
  worden verder gevonden.
- **Hoeveelheidsaanduidingen werden voor adressen gehouden.** In
  facturen, pakbonnen en voorraadlijsten verdwenen aanduidingen zoals
  „3390 Protocol", „1030 Bedrag" of „3390 Magazijn" als vermeende
  postcode met plaats – vier cijfers ziet er in elke hoeveelheid uit
  als een Oostenrijkse postcode. Staat er achter het getal een woord
  dat de toepassing als zelfstandig naamwoord, afdeling, activiteit of
  veldbeschrijving kent, dan blijft het nu staan. Echte
  plaatsaanduidingen zijn onaangetast, ook wanneer die tegelijk zo'n
  woord zijn („4692 Plaats"). Niet opgelost is daarmee het geval dat
  achter het getal een heel gewoon woord staat („3390 Rek") – daarvoor
  is een postcodebestand nodig.
- **De hulp noemde een menu-item dat niet bestaat.** Handleiding,
  afbeelding en de melding aan het einde van de installatie spraken
  van „Document voor AI opschonen"; het item in het contextmenu heet
  echter „Persoonsgegevens verwijderen". Wie de hulp volgde, zocht
  tevergeefs. Alle drie de plekken noemen het menu-item nu zoals het
  echt heet.
- **„Met het systeem starten" kon niet worden uitgeschakeld.** Wie bij
  het installeren „Met Windows starten" had aangevinkt, zag in de
  instellingen toch een leeg vinkje – en erger: in- en uitschakelen in
  de toepassing bleef zonder effect, het programma startte gewoon
  verder met Windows. Reden waren twee plekken waar Windows naar
  startprogramma's kijkt; de toepassing kende er maar één. Nu telt
  beide, de schakelaar toont de werkelijke stand en werkt in beide
  richtingen. Ook meegenomen: wie het item in taakbeheer uitschakelt,
  ziet dat nu in de toepassing – en wie het daar weer inschakelt, heft
  daarmee de uitschakeling op.
- **Koppen boven namenlijsten werden gezwart.** „DEELNEMERSLIJST
  WERKPLAATSGESPREK" of „PERSONEELSOVERZICHT BINNENDIENST" boven een
  lijst van personen verdwenen als vermeende naam. In hoofdletters
  ontbreekt het taalmodel zijn beste herkenningskenmerk, en in het
  Duits is elk zelfstandig naamwoord met een hoofdletter geschreven –
  „Deelnemerslijst Werkplaatsgesprek" ziet er dan uit als „Anna Huber".
  Samenstellingen op `-lijst`, `-dienst`, `-gesprek`, `-vergadering` en
  `-bespreking` blijven nu staan. De grondwoorden alleen gelden verder
  als naam: *Lijst* en *Dienst* zijn bestaande achternamen,
  *Deelnemerslijst* is er geen.
- **Verticaal geplaatste gegevens kregen een onleesbare plaatshouder.**
  Dossiernummers aan de paginarand, behandelaarafkortingen naast de
  bindrug, verticale tabelkoppen: zulke gegevens werden wel gevonden en
  verwijderd, maar de plaatshouder kwam dwars over de tekst uit, tot
  op één à twee punt samengedrukt en soms voorbij de papierrand. Nu
  volgt hij de tekst – verticaal, op leesbare grootte en in dezelfde
  richting waarin de gegevens stonden. Hetzelfde gold voor pagina's die
  achteraf werden gedraaid (horizontaal geschreven tekst met
  geregistreerde paginarotatie, zoals sommige uitvoerprogramma's die
  leveren); ook daar staat de plaatshouder nu zoals men de pagina
  bekijkt. „Geachte mevrouw doctor Anneliese Berger" leverde alleen
  „Anneliese" als naam op – „Berger" bleef in het document. Hetzelfde
  trof elke naam met tweede voornaam („Mevrouw Anna Maria Berger").
  Reden was de regel voor de naam achter een aanhef: die had twee
  woordplaatsen, en een titel of tweede voornaam verbruikte de eerste.
  Met „Dr." viel het nooit op – de punt breekt de regel, en het
  taalmodel ving de hele naam. Nu worden titels overgeslagen zonder
  een plaats te kosten, en de naam mag uit drie delen bestaan. Een rol
  **achter** de naam gaat verder niet mee: „Mevrouw Anna Huber
  Directeur" vervangt de naam, niet de rol.
