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
