Hva som endrer seg fra versjon til versjon – beskrevet fra applikasjonens ståsted,
ikke fra det indre. Den som vil vite *hva* den er bygget av, finner det i
[LIZENZEN.md](LIZENZEN.md); her står hva som endrer seg for arbeidet med den.

Nummereringen følger den vanlige tellemåten: Det **første** tallet endrer seg
når noe ikke lenger fungerer som før, det **andre** ved nye
funksjoner, det **tredje** ved feilrettinger.

## 0.10.52-alpha.20260903 – 3. september 2026

- En bunke med mer enn fire filer stanser ikke lenger opp etter svar i flere
  forhåndsvisningsvinduer. De neste dokumentene forberedes fortsatt i
  bakgrunnen; etter et svar fullføres nå den tilhørende filen som den skal,
  og neste plass i bunken frigjøres.
- Sammenligningen av korte firmamerker i PDF-er er nå begrenset til gjenkjent
  bildetekst. I vanlig sidetekst fører derfor ikke et langt modelltreff over
  flere linjer til at et enkelt ord med samme ordlyd et annet sted også
  sladdes.

## 0.10.51-alpha.20260903 – 3. september 2026

- Endringslisten vises nå på brukerens eget språk – på
  maskuro.com/neuigkeiten og i programmet under «Endringer» samt i «Hva er
  nytt» etter en oppdatering. Tidligere sto det tysk tekst under en oversatt
  overskrift i alle de atten språkversjonene. Der en oversettelse fortsatt
  mangler, blir den aktuelle versjonen stående på tysk i stedet for å
  forsvinne; listen over versjoner er den samme overalt.

## 0.10.50-alpha.20260903 – 3. september 2026

- Gjentakende firmamerker i PDF-er renses konsekvent, også når
  tekstgjenkjenningen leser skriften på en side annerledes eller utelater
  det runde signetet helt. Et uttrykkelig fravalg i forhåndsvisningen
  forblir dermed bindende og kan ikke oppheves av noen senere etterkjøring.
- Valutaløse priser i skannede tabeller sladdes nå fullstendig, også når
  tabelloverskrift og verdier ligger i forskjellige overlappende
  PDF-bilder. Mengder, timer, vekter og prosenter blir stående; langt
  fra hverandre liggende tall blir ikke lenger utilsiktet slått sammen til
  et beløp.
- Signatursøket fanger nå også opp belagte svake blå skrifttrekk og smale
  røde signaturkoder. Punkterte diagrammer, målekurver, stempler, logoer
  og brede røde redigeringsmarkeringer er unntatt fra denne snevre
  etterjusteringen.
- Sladding i dreide, speilvendte, skjærforvrengte eller beskårne
  PDF-bilder treffer nå det virkelige bildepolygonet. Tekniske roller i
  ytelsesposisjoner, kjøretøy- og dekksaksverdier samt teknisk
  «kompensasjon» avgrenses samtidig strammere mot falske treff;
  uttrykkelig merkede kontaktroller og telefonnumre forblir beskyttet.
- Synskontrollen før lagring av en PDF fryser ikke lenger vinduet: Ved
  store dokumenter med mange funnsteder sto det tidligere flere sekunder
  uten tilbakemelding; nå viser en henvisning at det kontrolleres, og
  vinduet fortsetter å tegne.
- Tilbakehentingen av en verdi fra et bilde i etterredigeringsprogrammet
  leser nå hvert originalbilde bare én gang via tekstgjenkjenning; tidligere
  kjørte den på nytt for de samme bildene ved hver ytterligere
  tilbakehenting.
- Nedlastingen av Høy-nivået og signaturmodellen trenger nesten ikke lenger
  arbeidsminne: 596-MB-pakken ble tidligere holdt fullstendig i minnet,
  kontrollert og pakket ut der – over ett gigabyte topp i det kjørende
  programmet, på maskiner med 8 GB øyeblikket der alt begynte å stoppe opp.
  Nå flyter den blokkvis ut på disken og kontrolleres og pakkes ut der.
- Søket i etterredigeringsprogrammet fryser ikke lenger store PDF-er: Den
  første bokstaven i søkefeltet leste tidligere inn alle sidene på én gang
  – ved 200 sider sto vinduet i to sekunder, og etter hver sladding en gang
  til. Sidene leses nå i porsjoner; inntil da står «Leser …» i telleren,
  resultatet er det samme.
- Rastrerte PDF-sider – etter en tekstgjenkjenning eller når en tekst ikke
  lot seg fjerne rent – lagres merkbart mindre og uten bildetap: I stedet
  for alltid som JPEG kodes hver side også tapsfritt, og den mindre
  versjonen havner i filen. En renset skanning krymper dermed fra 248 til
  48 KB, øvingsdokumentet med tekstgjenkjenning fra 913 til 702 KB; teksten
  forblir knivskarp.
- Nedlastede modeller (Høy-nivå, signaturer, ansikter, andre
  tekstgjenkjenning) frigjøres fra arbeidsminnet igjen etter ti minutter
  uten rensing. Tidligere ble de liggende lastet til programmet avsluttet –
  den som en gang hadde brukt et signatursøk og Høy-nivået, holdt varig over
  to gigabyte. Neste kjøring laster dem inn igjen på ett til to sekunder;
  statuslinjen sier fra om det.
- PowerPoint: Slektsnavnene på lysbildeoppsett og lysbildemastere («Tom»,
  «Tittellysbilde») erstattes ikke lenger som en angivelse. «Tom» er også
  et stedsnavn og ble feilaktig sladdet i hver tysk og engelsk
  presentasjon; nå renses bare de manuelt tildelte navnene på selve
  lysbildene.
- I PDF-er trekker linjeutjevningen ikke lenger overskriften til neste
  linje inn i et funn: Nummeret på neste listepunkt bak en dato gjaldt som
  telefonnummer, en feltoverskrift som «Kenncode» eller «Auftragsnummer»
  bak et tall som postnummer med sted, og stedslinjen under adressen
  doblet stedet. Det riktige, kortere funnet ble dermed fortrengt. Over 132
  korpus-PDF-er blir av 24 ekstra utjevningsfunn de to ekte stående; i
  praksiskorpuset synker de falske treffene fra 29 til 21 ved samme
  treffkvote.
- «Søk gjennom og sladd PDF-mappe» i etterredigeringsprogrammet blokkerer
  ikke lenger vinduet: Kjøringen arbeider i bakgrunnen, fremdrifts- og
  avbrytknappen reagerer, og menyer eller faner kan ikke lenger betjenes
  midt i en halvferdig fil.
- Skannede sider med funnsteder skrives nå bare om én gang ved sladding i
  stedet for to ganger: Tidligere fylte programmet boksene for funnstedene
  og for begrunnelsene i to omganger, og den andre komprimerte det nettopp
  nylagrede skannebildet en gang til. Dette sparer tid på store skanninger
  og et kvalitetstap i bildet.
- Bla, zoome og miniatyrbildene i etterredigeringsprogrammet reagerer
  raskere: Hver gjengitt side gikk tidligere som PNG gjennom en komprimering
  og rett tilbake igjen, bare for å vises – på skjermer med høy oppløsning
  rundt et tiendels sekund per side. Bildet kommer nå rett frem, bildepunkt
  for bildepunkt det samme.
- Synskontrollen før lagring av en PDF («utdataprøve») er rundt tre ganger
  raskere, ved samme resultat.
- Hovedvinduet står klart enda et kvart sekund tidligere: Kontrollen av om
  tekstgjenkjenningen er klar på denne maskinen, gikk tidligere under
  vindusoppbyggingen – på Mac inkludert en prøveforespørsel til
  systemgjenkjenningen – og innstillingssiden for tilleggskomponentene
  spurte i tillegg etter statusen for alle 48 språk. Begge skjer nå i
  bakgrunnen, henholdsvis først når språklisten virkelig åpnes; inntil da
  står «Tekstgjenkjenning kontrolleres …».
- Etter et signatursøk bruker programmet rundt 300 MB mindre arbeidsminne:
  Gjenkjenningsmodellen lå frem til da dobbelt i minnet – én gang for å
  kontrollere ektheten, én gang for å regne. Den kontrolleres fortsatt, bare
  uten den andre kopien.
- Tekstgjenkjenningen i PDF-er er merkbart raskere blitt: For hver
  feltoverskrift på en side («Fødselsdato:», «Personnummer:») ble det
  tidligere sendt en egen prøve gjennom gjenkjenningen for hver
  angivelsestype – på nytt på hver side, selv om samme overskrift allerede
  hadde stått ti sider tidligere. Svaret huskes nå; en toseders
  ytelsesbeskrivelse stilte dermed 324 spørsmål, nå bare de forskjellige.
  Funnene er de samme.
- Store tabeller renses igjen på sekunder i stedet for minutter: I den
  anonymiserende driftsmodusen – standarden – ble sammenligningen av
  allerede kjente verdier langsommere for hver ytterligere celle, fordi
  et mellomlager ble forkastet og bygget opp på nytt ved hvert treff. 5 000
  celler brukte til dette rundt 18 sekunder, nå et halvt; resultatet er
  tegn for tegn det samme.
- Hovedvinduet vises enda tydelig raskere: Landlisten i innstillingene
  trakk under vindusoppbyggingen hele gjenkjenningsbiblioteket inn i
  forgrunnen – rundt 0,7 sekunder på Mac, tilsvarende mer på Windows –
  selv om det til dette bare trengs navnene på landene. Listen kommer nå
  fra et lett katalog; biblioteket lastes som planlagt i bakgrunnen mens
  vinduet allerede står klart. Dette gjelder også etter hvert språk- eller
  utseendebytte som starter programmet på nytt.
- Dokumentlaboratoriet fører nå avkuttede feltoverskrifter, lokale
  verdiskygger og sterke skannebeskjæringer fullstendig gjennom PDF-,
  DOCX- og ODT-beholdere. Matrisen omfatter 680 filer fra 40
  dokumentfamilier og 17 beholderakser. Maskuro fjerner i de nye samt de
  fullstendige grunn- og kjennetegnprofilene alle målangivelser, uten målt
  falskt treff, skadet bevaringsverdi eller avbrudd.

- Flere ganger brukte skanninger kontrolleres og renses nå via hver synlige
  plassering: Dokumentlaboratoriet deler det samme bildeobjektet over
  forskjellige sider, størrelser og dreiestillinger i PDF og refererer til
  samme bildedel flere ganger i DOCX og ODT. Tekniske ODT-rammenavn som
  «skjemaskanning liten liggende» gjelder ikke lenger som person; frie navn
  og steder med lignende begynnelse forblir beskyttet. Et generelt
  skjemagjetning fra den avsluttende PDF-sidekjøringen kan på en allerede
  uavhengig lest bildeflate ikke lenger skape et stort adressefeiltreff. De
  120 nye beholderne når i grunn- og kjennetegnprofil alle 813 henholdsvis
  840 målangivelser uten falskt treff, bevaringsbrudd eller avbrudd; den
  fullstendige 800-filers kjennetegnkontrollen bekrefter 5 600/5 600.

- Det tyske OCR-laboratoriet omfatter nå 560 skanninger fra 40
  dokumentfamilier. Nye varianter beskjærer feltoverskrift- og siderender
  eller legger en skygge direkte over en verdi. Maskuro beskytter samtidig
  navn, adresser, fødselsdatoer, medisinske nøkler og merkede
  identifikasjonsnumre med delvis skadet merking. Samtidig erstattes ikke
  lenger skjemafeltrester, offisielle overskrifter samt saklige rettslige
  og informasjonsbegreper som personer eller steder. De fullstendige
  grunn- og kjennetegnprofilene når 3 794/3 794 henholdsvis 3 920/3 920
  målangivelser uten målt falskt treff eller avbrudd.

- Det automatiske PDF-bildeutvalget fjerner ikke lenger storflate
  produktfotos, energimerker og portrettrekker utelukkende fordi de
  begynner i den øvre sidemargen. Ekte flate topp-/bunnbilder og brevhoder
  som starter ved arkkanten faller fortsatt. I medarbeiderkataloger
  gjenkjennes navn nå også fra strukturelt gjentatte oppføringer når den
  synlige dokumenttittelen bare foreligger som bilde. Gjenkjenningen er
  ikke lenger tilskåret to konkrete rolleord og forkortelsen «DW»: én til
  fire ombrutte roller samt «Durchwahl», «Nebenstelle», «Ext.» og
  «Extension» utledes fra den felles byggeformen. Roller og
  avsnittsoverskrifter blir stående, også når språkmodellen etter
  overlappingsoppløsningen bare lar et rolleadjektiv stå igjen. Vannrette
  rollerutenett gjelder ikke lenger feilaktig som navnekolonner. Klistrer
  side-OCR-en flere kort til ett ekstremt bredt ord med indre stor
  forbokstav, skiller et snevert lokalt motblikk de virkelige ordboksene;
  dermed blir verken et enkeltnavn eller en bred feilstripe stående igjen.
  Gjentatte flerlinjede firmalogoer sladdes ut fra en allerede bekreftet
  identisk pikselmal også på sider uten brukbar OCR-tekst og ved opptil to
  piksler avvik i posisjon; kortere lokale annengangslesninger av OCR-en
  får samtidig ikke lenger supplere et større overskriftsområde som
  oppdiktet navn. Sidetall foran et firmabrevhode hører ikke lenger til
  organisasjonsnavnet, numerisk begynnende ekte merkenavn forblir
  beskyttet. Flere målte produkt-, fag- og skjemaord foreslås ikke lenger
  som personer.

- Signatursøket kjører ved PDF-er først etter OCR-bilderensingen, besøker
  også sider uten vanlig teksttreff og regner funnbokser på dreide sider
  korrekt tilbake til dokumentrommet. Tette produktfotos sladdes ikke
  lenger som signatur. Over entydig merkede signaturfelt lukker et snevert
  strekfall tynne modellhull; tomme linjer med forhåndstrykt dato utløser
  det ikke. Rene skanninger med utelukkende OCR-/signaturfunn avbrytes ikke
  lenger i denne fasen på grunn av en først i tekstgrenen lastet
  bildesladder.

- Mange samtidig åpne dokumenter forblir skillbare i etterredigeringsprogrammet:
  Fanene krymper ikke lenger til bare et utelatelsestegn, og en listeknapp
  til høyre viser alle fullstendige filnavn under hverandre. Faner kan
  omordnes ved å dra og fjernes med krysset sitt fra samme liste som i
  hovedvinduet; ulagret arbeid avklares fortsatt først. Et høyreklikk
  tilbyr dessuten «Lukk», «Lukk andre faner» og «Lukk faner til høyre».

- En kortvarig Windows-sperring fra virusskanner eller søkeindeks lar ikke
  lenger den ferdig lastede språkmodell- henholdsvis ordbokmappen mislykkes
  med «Tilgang nektet» ved den avsluttende innsettingen. Maskuro forsøker
  nå denne siste mappebyttingen på nytt en kort stund.

- Det tyske dokumentlaboratoriet kontrollerer nå beholdere også med
  vekslende PDF-sidedreining, uavhengig dreide PDF-bilder samt skalerte og
  beskårne tabellbilder i DOCX og ODT. Feltverdier i synlig dreide bilder
  gjenkjennes igjen fullstendig, tekniske kolonnebetegnelser erstattes ikke
  lenger som steder, og navn med felles familienavn splittes ikke lenger av
  konsistens-etterkontrollen i doble delfunn. Den til 320 filer doblede
  matrisen når med tilkoblet dato-, penge- og medisingjenkjenning
  2 240/2 240 målangivelser uten målt falskt treff eller avbrudd.

- Flersides bilde-PDF-er, blandede tekst-/bilde-PDF-er og skanninger
  innebygd i DOCX eller ODT kontrolleres nå i et eget 160-filers
  laboratorium over alle 40 tyske dokumentfamilier. Tekniske ODT-rammenavn
  og merkede enhetskoder erstattes ikke lenger som steder; ekte navn,
  steder og adresser i de samme strukturene forblir beskyttet. Med
  medisin- eller pengegjenkjenning påslått fjernes dessuten en direkte
  påfølgende dosering henholdsvis et betalingsintervall fullstendig.
  Beholder-, tekstgrunn-, tekstkjennetegn- og OCR-kjennetegnkjøringer når
  til sammen sine respektive fullstander uten målt falskt treff eller
  avbrudd.

- Sikkerhetskontrollen før lagring viser nå iøynefallende PDF-steder som en
  enkeltvis valgbar liste. «Kontrollér i redigeringsprogrammet» åpner
  nøyaktig den valgte siden og markerer området; overlappende delfunn på
  samme sted vises nå bare én gang. De nye betjeningstekstene finnes
  fullstendig på alle 17 oversatte grensesnittspråk.

- Markdown-filer beholder ved erstatning sin lenke-, uthevings- og
  fotnotesyntaks. Maskuro leser til dette en tegnmessig like lang versjon
  uten Markdown-markeringer; understreker i e-postadresser, regnestjerner
  og vanlige lenker uten personopplysning forblir uendret.

- Flere håndskrevne oppføringer på samme PDF-side søkes nå i opptil tre
  omganger. Allerede funnede trekk skjules bare i arbeidsbildet, slik at de
  ikke lenger fortrenger svakere signaturer; på dreide sider havner
  sladdeflatene igjen på det synlige funnstedet. Bildefyllinger fra
  tidligere sikkerhetsfaser bevares ved den påfølgende tilbakeskrivingen.

- «Tilbakestill alle innstillinger» omfatter nå også «Tekst i bilder». Er
  OCR-komponenten ikke tilgjengelig, forblir bryteren teknisk av, uten å
  feilaktig markeres som avvikende fra leveringstilstanden.

- Store bildefragmenter ved øvre sidemarg gjelder ikke lenger som
  topptekst utelukkende på grunn av sin plassering. Dermed bevares særlig
  bildebaserte artikkelbeskrivelser og tabellinnhold. Nylig gjenkjente,
  typenøyaktige e-post- og skjemafunn filtreres dessuten ikke lenger bort
  fra den avsluttende synskontrollen på en allerede kontrollert bildeflate.

- Tekniske posisjons- og artikkellinjer i klima- og elektrotilbud
  skilles strammere fra personer, steder og organisasjoner. Dette gjelder
  blant annet kabeltyper, AC-forsyning, posisjonsnumre samt
  versale produktkoder; ekte navn og adresser forblir beskyttet.

- Kontrollen av virkelige rensede PDF-er forveksler ikke lenger
  prisbestanddeler som `1 699,59` med telefonnumre og skjærer ikke lenger
  ut en antatt kortangivelse fra en fullstendig dato som `08.05.2025`. Navn
  bak en tiltaleform avsluttes ved linjeskiftet i stedet for i den
  påfølgende gaten; stedsnavn i vedleggsfilnavn begrenses til det faktiske
  stedet. Kjøretøyfarger, tekniske statusverdier, næringsbetegnelser og
  produkt-rettsformer bevares likeledes. Skadede plassholderlesninger som
  `|PLLZ` behandles ikke igjen som personopplysning ved en andre
  OCR-omgang.

- Sidevis lagrede PDF-bilder får ved den avsluttende synskontrollen et
  ekstra blikk i sin uendrede bildeposisjon. Denne får utelukkende ettersladde
  verdier som Maskuro allerede har sikkert gjenkjent på samme side. Slik
  dekkes for eksempel et lite dreid adressestempel fullstendig, uten å
  finne opp nye ord fra bildeoverskrifter eller tekniske tegninger som
  personopplysninger.

- I OpenDocument-tekster tømmes nå forfatterinitialene til et notat
  (kommentar) sammen med forfatteren. LibreOffice legger dem ved siden av
  det fulle navnet som en egen kortform og viser nettopp denne i
  sidemargen; tidligere sto «SO» der fortsatt, mens «Sieglinde Ortner» ved
  siden av lenge hadde vært en plassholder. Tømming skjer bare når
  forfatteren faktisk ble erstattet – notatet til en avdeling beholder sin
  merking.

- I italienske forretningsbrev gjelder ikke lenger standardvendingene ved
  setningsstart som navn eller sted: «Restiamo a disposizione»,
  «Rimaniamo», «Attendiamo», «Alleghiamo», «Comunichiamo» og «Auguriamo
  buon lavoro» ble tidligere hengende som antatt person eller stedsangivelse.
  Ekte navn på samme sted («Rossi Mario») gjenkjennes fortsatt.

- Toskolonneskanninger beskytter merkede identifikasjoner og stedsangivelser
  nå også når tekstgjenkjenningen først leverer alle feltoverskrifter og
  deretter alle verdier. Tilordningen følger den synlige pikselinjen og
  fungerer også ved sider dreid 90 grader. Tett skilte deler av en pass-
  eller kontraktsidentifikasjon sladdes samlet; merkede fødselsdatoer,
  ICD- og PZN-nøkler dekkes likeledes, påfølgende saksord blir stående.
  Korte navn og brukernavn beskyttes i eksakte felt; e-postadresser
  oppdelt i flere OCR-ord bare ved tett naboskap og fullstendig
  e-postgrammatikk. En feltbundet rettelse av forvekslingsutsatte tegn samt
  den lokale gjennomlesingen av et ennå tomt personfelt lukker skadede og
  dreide skanninger uten å utvide saksfelt eller allerede belagte verdier.
  Sikkerhetsmarginer følger ordstørrelsen, og kjennetegnprofilen tar med
  umiddelbart naboliggende doseringsenheter og betalingsintervaller. Lett
  skjevt matede skjemaer projiseres geometrisk tilbake fra flere
  retningslike OCR-linjer; avrundingsstøy eller motstridende vitner er ikke
  nok. Korte bokstavprefikser bevares foran en bindestrekidentifikasjon, og
  et fullstendig merket adressefunn erstatter bare sitt likeartede
  gate-delfunn. En feillest rollefeltoverskrift faller utelukkende i en
  skjemakolonne belagt med minst tre kjente overskrifter; chattenavn
  forblir beskyttet. En knapp randbeskjæring og en lokal overeksponering
  med diagonal lysrefleks supplerer bildematrisen. Person-, steds- og
  firmafunn som strekker seg over flere skjemalinjer, begrenses i en
  flerbelagt feltkolonne til den respektive verdien. En teknisk
  posisjonsverdi faller bare med posisjonsoverskrift og passende
  identifikasjonsform; ekte navn forblir beskyttet. Også e-postverdier
  avbrutt av lysrefleksen fjernes bak en uttrykkelig e-postfeltoverskrift
  med en tett, nabobegrenset billedrand. To felt-verdi-par på samme synlige
  linje evalueres nå uavhengig; verdier på en dypere grunnlinje kobles bare
  etter tre samstemte geometriske vitner. Dermed forblir
  identifikasjonsnumre, fødselsdatoer og adresser fullstendig beskyttet
  også i tette skjemalayouter. Gate, postnummer og sted forenes
  utelukkende innenfor samme adressefelt og med passende postal
  grammatikk. Snevert avgrensede saksfelt for arbeids-/hjelpemidler og
  tannstatus skaper ikke lenger sted- eller katalogfalske treff; ekte navn
  og lignende benevnte felt forblir beskyttet. Det tyske dokumentlaboratoriet
  omfatter nå 440 skanninger og når 2 981/2 981 i grunnprofilen samt
  3 080/3 080 i kjennetegnprofilen. Alle elleve bildemutasjonene og alle 40
  dokumentfamiliene ligger på 100 prosent, fortsatt uten målt falskt treff,
  bevaringsbrudd eller avbrudd.

- PDF-tekstlag med tapte celleskillere begrenser nå organisasjons-,
  adresse- og stedsfunn ut fra den gjentatte felt-verdi-strukturen.
  Feltoverskrifter foran firmaverdier og tekniske piler som `=>` eller `->`
  hører ikke lenger til treffet. Den ekstra visningen for myke linjeskift
  får ikke lenger utvide rettsform- og stedsfunn over flere tabellinjer; en
  allerede fullstendig adresse avsluttes før neste feltoverskrift med
  verdi. Den avsluttende kjøringen over alle 1 600 TXT-, HTML-, PDF- og
  DOCX-dokumenter fjerner 10 840/10 840 målangivelser med null falske
  treff, null bevaringsbrudd og null avbrudd.

## 0.10.44-beta.1 – 1. september 2026

- Pakkebyggingen genererer separate utgaver for Windows x64 og ARM64, macOS
  på Apple Silicon og Intel samt Linux x64 og ARM64. Pakkenavn,
  oppdateringsvalg og frigivelser skiller arkitekturen; en publisering
  forblir sperret så lenge ett av de seks målene eller avhengighetsbeviset
  dets mangler. Linux ARM64 forutsetter på grunn av Qt minst glibc 2.39.
  Fullstendig godkjent på ekte maskinvare er foreløpig bare Windows x64 og
  macOS på Apple Silicon; de øvrige arkitekturpakkene skal tydelig merkes
  som forhåndsversjoner for utprøving i stedet for produktiv bruk.

- Ved flere filer fortsetter gjenkjenningen nå å arbeide mens en
  forhåndsvisning venter på gjennomsyn. Opptil tre forberedte
  forhåndsvisninger vises etter hverandre; samtidig regner fortsatt bare
  ett dokument, og en resultatfil oppstår først etter frigivelsen dets. Et
  i forhåndsvisningen valgt varig unntak gjelder også for allerede
  forberedte følgende dokumenter.

- Redaksjonssertifikater kan nå når som helst kontrolleres direkte i
  Fil-menyen mot det sladdede dokumentet. Maskuro skiller her et passende
  signert dokument, et passende men usignert belegg, en ugyldig signatur
  og et dokument som ikke hører til sertifikatet. En lisens eller den
  opprinnelige operativsystemkontoen er ikke nødvendig for motkontrollen.
  For automatiske kontrollsteder er samme sammenligning tilgjengelig via
  `--zertifikat-pruefen`; returkoder skiller samsvar, betjeningsfeil og
  ugyldig bevis.
  Motkontrollen sammenligner dessuten den innebygde Maskuro-ID-en med
  sertifikatet; en fritt inntastet fremmed ID fanges dermed opp også ved
  et usignert belegg.
  Ved gyldig signatur viser kontrollfunnet dessuten den av administrasjonen
  aktiverte redigereren med operativsystemkonto, teknisk konto-ID og
  plattform. Ubekreftede angivelser fra usignerte eller ugyldige belegg
  gis ikke ut.

- Et nytt tysk dokumentlaboratorium genererer 160 fullstendig syntetiske
  TXT-, HTML-, PDF- og DOCX-dokumenter fra ti områder og fire
  strukturvarianter. Manifestet skiller nå uttrykkelig mellom angivelser
  som må forsvinne, og fagtekster henholdsvis saksidentifikasjoner som må
  bevares; dokumentfamilie, mutasjon og offentlig strukturkilde er
  sporbart dokumentert.

- Det tyske dokumentlaboratoriet ble utvidet til 280 filer, sju
  strukturformer, 1 540 målangivelser og 1 036 bevaringsankere. Nylig
  kontrollert blir nummererte skjemaer, klammede PDF-/maskefelt og
  tekniske `=>`-tilordninger. Den utvidede fullstanden når i TXT, HTML,
  PDF og DOCX hver 100 prosent ved null falske treff. Klammede dato- og
  identifikasjonsnummerfelt, pilskilletegn og uttrykkelig merkede
  forbindelser gjenkjennes nå strukturelt.

- En andre laboratorieutvidelse hever beholdningen til 400 dokumenter, ti
  strukturformer, 2 200 målangivelser og 1 480 bevaringsankere.
  JSON-lignende nøkkelverdier, YAML-lister og versale skjemafelt når
  sammen med den tidligere beholdningen 100 prosent ved null falske
  treff. Siterte fødselsdatoer og identifikasjonsnummer samt uttrykkelig
  merkede roller som forsikrede, søkende, avgiftspliktige og
  representasjonsberettigede personer gjenkjennes nå også i disse
  eksportformene.

- En separat OCR-modus for det tyske dokumentlaboratoriet genererer i
  tillegg 200 rene bildeskanninger fra alle 40 familiene. Rene,
  kontrastfattige, lavoppløste, JPEG-artefaktbelastede og 90 grader dreide
  sider etterprøves med eksakte pikselbokser, uten å endre den
  sammenlignbare 1 600-filers tekstgrunnstanden. Manifestet skiller
  tilkoblingsbare dato-, penge- og medisinkjennetegn fra grunnprofilen og
  kjenner belagte OCR-lesninger uten å telle dem som ekstra målsteder.
  Målingen brytes ned etter mutasjon og dokumentfamilie. Snevre feltgrenser
  hindrer blant annet at «Az» i stedsnavnet «Graz» sladder en påfølgende
  dato som saksnummer; den gjeldende grunnmatrisen kjører med null falske
  treff og null avbrudd.

- Fem ytterligere tyske dokumentfamilier for faktura/følgeseddel,
  bank/kreditt, husleie/eiendomsforvaltning, skole/høyskole og
  logistikk/toll utvider laboratoriet til 600 filer med 3 520
  målangivelser og 2 360 bevaringsankere. En snever PDF-tabellvei bruker
  den uttrykkelige overskriften `Feld Angabe`, når tekstlaget mister
  celleskillere; et nytt `--familien`-utvalg fremskynder delmålinger. De
  200 nye filene når 1 320/1 320 ved null falske treff og null avbrudd.

- Forsikring/skade, arbeid/lønn, medisin/laboratorium, kjøretøy/verksted og
  teknikk/vedlikehold utvider det tyske dokumentlaboratoriet til 800
  filer med 4 960 målangivelser og 3 200 bevaringsankere. Snevert merkede
  polise-, pasient-, kontrollør- og kjøretøyidentifikasjoner samt nye
  rolle-, adresse- og organisasjonsfelt gjenkjennes. Den nye delmatrisen
  og den fullstendige matrisen når 100 prosent ved null falske treff og
  null avbrudd i TXT, HTML, PDF og DOCX.

- Bygg/anbud, energi/miljø, forening/selskap, kommunikasjon/kalender og
  hotell/arrangement hever det tyske dokumentlaboratoriet til 1 200 filer
  med 7 920 målangivelser og 4 800 bevaringsankere. Nye rolle-, firma-,
  adresse-, register-, tildelings-, bestillings- og brukerkontofelt
  gjenkjennes også i alle eksportformer. Tellernumre bevares som
  saksidentifikasjoner. Del- og fullmatrise når 100 prosent ved null
  falske treff og null avbrudd.

- Gastronomi/leveringstjeneste, apotek/resept, begravelse/kirkegård,
  idrett/medlemskap og eiendom/megler utvider det tyske
  dokumentlaboratoriet til 1 400 filer med 9 360 målangivelser og 5 640
  bevaringsankere. Nye personroller, adressefelt og søkeoppdragsnumre
  gjenkjennes. Merkede firmanavn med rettsform forblir fullstendig
  beskyttet også over et automatisk linjeskift; alderskategorier og
  fagoverskrifter erstattes ikke lenger feilaktig. Del- og fullmatrise når
  100 prosent ved null falske treff og null avbrudd.

- Tannbehandling, kjøreskole, brannvesen/utrykning, energifellesskap og
  pakkereise utvider det tyske dokumentlaboratoriet til 1 600 filer med
  10 840 målangivelser og 6 440 bevaringsankere. Nye roller, adressefelt
  samt behandlings-, utdannings-, utrykning-, energi- og
  reisekontraktidentifikasjoner gjenkjennes strukturelt. Den nye
  200-filers delmatrisen når 1 480/1 480; den fullstendige matrisen når
  10 840/10 840. Begge forblir ved null falske treff og null avbrudd.

- Fullmålingen av dokumentlaboratoriet senket gjennom snevre offisielle
  saksformer og strukturregler de unødvendige erstatningene fra 68 til 0,
  de uttrykkelig målte bevaringsbruddene fra 23 til 0 og avbruddene fra 3
  til 0. Funnkvoten steg samtidig fra 91,1 til 100,0 prosent; TXT, HTML,
  PDF og DOCX når hver 100 prosent. Generelle tabelloverskrifter som
  «Feld» bremses bare i den belagte rekkefølgen «Feld»/«Angabe»; et
  likelydende etternavn forblir beskyttet. Rettslige saksnumre med
  sluttbokstav, likhetstegn-felt, «Geburtsdatum des Kindes» og flere
  merkede enkeltnavn på samme linje gjenkjennes fullstendig.
  Word-tabeller og forlinjefelt bruker sin feltoverskrift som midlertidig
  gjenkjenningskontekst; merkede PDF-adresser forblir fullstendig
  beskyttet også ved et satsbetinget linjeskift.

- Tyske personkjennetegn-, yrkes- og medisinfelt fungerer nå også med
  Windows-linjeskift. Enkeltbokstavs kjønnsangivelser som
  «Geschlecht»/«w» beskyttes i forlinjeformen. Saklige
  «Artikel-PZN»-felt utløser derimot verken et legemiddelkode- eller et
  personfunn; ekte PZN-, ICD- og ATC-angivelser gjenkjennes fortsatt.

- Tyske skjema- og nummerfelt er mer nøyaktige: «DW.» fungerer nå også
  foran et mykt linjeskift, uttrykkelig merkede navn fjernes selv ved
  liten forbokstav, og rent numeriske saksnumre tilordnes sin riktige
  identifikasjonstype. Omvendt gjelder et tilfeldig Luhn-gyldig faktura-,
  bilags- eller artikkelnummer ikke lenger som kredittkort. Syntetiske
  HTML- og PDF-utdataprøver bekrefter fjerning og bevaring i det ferdige
  dokumentet. Identifikasjonsnummer og brukernavn gjenkjennes dessuten når
  merkingen deres står i den umiddelbart foregående tabell- eller
  skjemalinjen; saklige bilagsnumre forblir synlige også i denne formen.

- Passord gjenkjennes nå også bak en alenestående feltoverskrift på
  forrige linje. Avsluttende spesialtegn som `!` eller `#` hører fullt ut
  med til den beskyttede verdien. Produkt- og artikkel-PIN-er maskeres
  omvendt ikke lenger som kort-PIN; uttrykkelige «PIN»- og
  «Karten-PIN»-felt forblir beskyttet.

- Skjemaverdier med liten forbokstav gis nå ved entydige tyske adresse- og
  «PLZ/Ort»-felt ut som adresse henholdsvis postnummer med sted i stedet
  for bare som generelt sted. Likeledes forblir firmaverdier med liten
  forbokstav som «beispiel service» bak et firmafelt fullstendig
  beskyttet, uten å kutte sluttordet som en antatt neste
  feltoverskrift.

- Hjelp, FAQ, personvernstekst og nettsted forklarer nå
  opprinnelsesbeviset samlet: nøytral Maskuro-ID i dokumentet, valgfri
  tilordning til den ekte operativsystemkontoen bare i den lokale
  kontrollprotokollen, brukerbytte via Windows/macOS/Linux samt
  meningsinnholdet i SHA-256 og signatur.

- Bildebaserte tekniske ytelsesbeskrivelser renses mer tilbakeholdent.
  Entydige saksord som «Abbruchhämmern», «Deckungsrücklass»,
  «Positionsnummern», «Einbauplatine» eller «Terminsituation» samt midt i
  ordet delte OCR-former gjelder ikke lenger som person eller sted. Et
  reelt kommunekontor-tilbud sank dermed fra 140 til 90 entydige
  erstatninger, uten å skape nye treff; navn som Schneider, Lang, Bauer og
  Hahn forblir uttrykkelig beskyttet.

- Ytterligere falske treff fra reelle tilbud er rettet: «Digital signiert»
  inneholder ikke lenger en antatt person, en BIC gjenkjennes også uten
  kolon bak merkingen sin, `15000 Alternativ» gjelder ikke som postnummer
  med sted, og EU-sitatet «(VO (EG) 715/2007» skaper ingen organisasjon.
  Et solcelletilbud sank dermed fra 26 til 16 erstatningsforekomster; ekte
  navn, steder og kontodata ble bevart.

- I medarbeideroversikter erstattes forkortelsen «Stv.» for stedfortreder
  og en alene avskilt «FACILITY»-områdeoverskrift ikke lenger som
  personnavn. Den reelle 13-siders motprøven sank fra 878 til 875
  erstatninger; navn, internnumre og firmabetegnelsen forble beskyttet.

- Rensede PDF-, OpenDocument- og kontorfiler får en nøytral
  `MASKURO-…`-identifikasjon i dokumentegenskapene sine. Kontrollrapport
  og signert kontrollprotokoll fører samme identifikasjon samt
  SHA-256-verdier for kilde og resultat; redaksjonssertifikatet overtar
  identifikasjonen fra den ferdige filen. Et brukernavn kommer fortsatt
  bare med hvis administrasjonen uttrykkelig slår på det eksisterende
  brukerfeltet.

- Hovedvindu og innstillinger er roligere inndelt: Lagre, kopiere,
  detaljer, nøkkeltall og sletting av en gjenkjenningsprofil vises først
  når den respektive handlingen er mulig. Tekniske OCR-språkforkortelser
  og lange eksempler står ved behov i henvisningsteksten i stedet for
  varig i arbeidsflaten. Gjenkjenningssiden tilpasser seg bedre til
  smalere vinduer, uten avkuttede forklaringer eller vannrette rullefelt;
  advarselen om klartekst i erstatningslisten forblir synlig ved dette.

- Gjenkjenningen omfatter flere tyske og internasjonale kontakttilfeller:
  Telefonnumre kontrolleres nå for alle valgbare landregioner, ungarske og
  kroatiske kontraktroller fanger nå også opp yrkeslike etternavn
  fullstendig, og nummererte reservedel-/materiallister utløser ikke
  lenger et personfalskt treff på grunn av «Mutter / Flach». Personfelt med
  åpenbart siffer­holdig saksverdi tas ikke over som navn; den
  maskinlesbare passsonen (MRZ) kan dessuten slås på/av samlet via
  gruppen «Identifikasjoner».

- Firmaer uten rettsform skilles bedre fra personer bak flertydige
  arbeidsgiverfelt: Navn som «Huber Handel», «Müller Logistik» eller
  «Kowalski Handel» registreres fullstendig som firma, mens
  «Arbeitgeber: Bauer Anna» fortsatt forblir et personnavn. Det
  automatiske landvalget tar ved franske dokumenter fortsatt hensyn til
  hele det franske språkområdet inkludert Luxembourg.

- Gjenkjente signaturer og personopplysningstekst inni et bilde ble
  tidligere alltid dekket med et svart rektangel – også når en annen
  farge eller et mønster som «Regnbue» var innstilt for sladding. Disse
  bildeområdene overtar nå også den valgte sladdefremstillingen; den
  dekkende flaten skrives fortsatt direkte inn i bildepunktene.

- Den engelske gjenkjenningen ble etterprøvd på elleve manuelt oversatte
  ekte dokumenter og forbedret målrettet: Lagerstatus, tekniske
  tilbuds- og nettbutikkfelt samt roller i medarbeiderregistre forblir
  synlige, «CV» leses ikke lenger som rettsform i malsetningen, siterte
  skrifttyper bevares, og navn i loddrette CV-hoder, flersides
  medarbeiderlister, bak «Account manager» samt sifferbegynnende
  firmanavn gjenkjennes fullstendig. Østerrikske foretaksnumre fungerer nå
  også bak en engelsk merking; kortformen «Customer:», EAR-registreringsnumre
  og arbeidsgivernumre bærer verdien sin. Målkjeder, kabeltyper,
  EU-rettshenvisninger, tilbudsgyldighetsdatoer, oppfyllelsessteder,
  verneting, registerdomstoler, skatteforkortelsen «NoVA», tekniske
  numre i dekkmerker samt normhenvisninger som «OVE R6-2» og «AStV»
  skaper ikke lenger falske treff. En gyldig merket IBAN slutter rent
  foran registreringsfeltet eller overskriften til den følgende linjen;
  adresser med næringssonetillegg gjenkjennes fullstendig også fra
  PDF-tekststrømmer med Windows-linjeskift. Engelske firmainnledninger og
  strukturerte sparebanknavn avgrenses fullstendig. Landet til
  utgangsdokumentet bevares ved språkversjonene for postnumre og
  landsspesifikke identifikasjoner.

- I mottaker- og meldingshoder kunne språkmodellen forbinde de to første
  navnene i en kommaliste til ett eneste funn («Bcc: Huber, Mayer»). Begge
  navnene gjenkjennes nå enkeltvis, erstattes og føres i rapporten –
  likeledes bak «Sent:», «Reply:» og «Fwd:».

- Det maskinlesbare området på et pass eller ID-kort (MRZ) manglet i
  gruppestyringen «Hva som søkes». Det hører nå til «Identifikasjoner» og
  kan slås på/av sammen med denne gruppen.

- Den som velger malen «Regnbue» for erstatningstekster, får nå også
  sladdede steder i samme utseende; tidligere forble de overraskende
  klassisk svarte. Sladdeflatene kan deretter fortsatt stilles om
  uavhengig til en annen mal.

- Sidefeltet i etterredigeringsprogrammet kunne forbli tomt etter
  gjenoppretting av et lagret vindusoppsett, inntil bredden dets ble
  endret manuelt. Miniatyrene omordnes nå etter den synlige
  vindusoppbyggingen og står straks midtstilt i feltet.

- De fargede kontrollmerkene rundt erstatningstekster i PDF-er forble,
  avhengig av kategori- og trafikklysfarge, knapt synlige. En lys
  underkontur skiller nå kontrollrammen pålitelig fra den fargede
  plassholderen og sidebakgrunnen.

- Den som sladder en linje i etterredigeringsprogrammet, hvis dokument er
  satt med tett linjeavstand (typisk for tilbud og ytelsesbeskrivelser),
  fikk en stripe som stakk inn i overlengdene til linjen under – den var
  deretter bare halvveis leselig. Stripen slutter nå ved den virkelig
  tegnede skriften til nabolinjen; den sladdede linjen selv forblir
  dekket fullstendig med underlengdene sine.

- Øvingsdokumentet («Hjelp → Åpne øvingsdokument», også i rundturen)
  demonstrerer nå hver gjenkjenningstype: Til det oppdiktede brevet
  kommer nå et fotografi med gjenkjennelig ansikt, en skrevet signatur,
  yrke og avdeling, diagnose og medikament – ved siden av firmanavn, beløp
  og dato som allerede var der. Hva standarden bevisst lar stå, forklarer
  arket selv, sammen med bryteren som fjerner det; ansiktet på fotografiet
  pikseleres fra fabrikken.

- Pengebeløp i den vanlige tyske skrivemåten med symbolet bak tallet
  («1.240,00 €») ble aldri funnet av bryteren «Fjern også pengebeløp» –
  «1.240,00 EUR» og «€ 1.240,00» derimot alltid. Nå gjenkjennes alle tre
  skrivemåtene.

- Signatursøket arbeider nå også på alenestående bildefiler: Den som
  renser en skanning som JPG eller PNG, får håndskrevne signaturer i den
  sladdet – samme gjenkjenning, samme melding i rapporten som ved PDF. I
  kontorfiler innebygde bilder søkes fortsatt ikke gjennom, fordi
  gjenkjenningen der målt arbeider upålitelig; avkrysningen heter derfor
  nå «PDF og bildefiler: Sladd håndskrevne signaturer».

- En sladdestripe kunne ved tett linjeavstand synlig stikke inn i
  overlengdene til linjen under og gjøre den halvveis uleselig –
  stripehøyden kom fra skriftmetrikkene, ikke fra det som virkelig står
  på papiret. Stripen slutter nå ved den faktisk tegnede blekken til
  nabolinjen, i etterredigeringsprogrammet som i den automatiske
  rensingen. Selve linjen med underlengdene forblir alltid helt dekket;
  overlapper linjene virkelig, blir stripen heller stående på nabolinjen
  enn å frigi noe.

- I en medarbeiderkatalog med rolle under navnet ble en kvinnelig
  lederbetegnelse («Anna Berger» med «Montageleiterin» under) trukket med
  inn i navneerstatningen – den mannlige formen ved siden av forble
  korrekt stående. De kvinnelige «…leiterin»-formene (montasje-, team-,
  prosjekt-, bygg-, avdelings-, drifts-, gruppe-, kontorleder) behandles
  nå som sine mannlige motstykker som funksjonsbetegnelse; filial-,
  personal- og salgsledelse er nye med i begge former.

- Den tilkoblingsbare yrkesgjenkjenningen fant ikke kvinnelige
  lederroller som «Projektleiterin», «Teamleiterin» eller
  «Abteilungsleiterin», men de mannlige formene deres derimot. Begge
  formene teller nå likt.

- I forhåndsvisningsvinduet klistret flertallsangivelsen seg på Mac
  direkte til begrepet («Anna Musterfrau2ק i stedet for «Anna
  Musterfrau 2ק). Mellomrommet er tilbake.

- Sammenligningslupen har en ny knapp ved siden av zoomglidebryteren: Den
  legger den med ett trykk i full bredde over resultatet – hver halv
  høyde, og originalen i samme målestokk som dokumentet
  (lupezoomen hopper da til 100 %). Et andre trykk dokker den igjen liten
  i den venstre kolonnen og gjenoppretter den tidligere lupezoomen.
  Ringen ved siden av tilbakestiller nå bare zoomen – henvisningsteksten
  dens hevdet tidligere feilaktig at den også dokket vinduet igjen.

- I verktøylinjen til etterredigeringsprogrammet er det igjen synlig at
  det valgte verktøyet er valgt: Knappen til det aktive verktøyet bærer
  en fylt flate med blå kant – likeledes hver annen påslått
  omkoblingsknapp i linjen (for eksempel sammenligningslupe eller
  læringsmodus). Markeringen var gått tapt sammen med den egne
  knappeutformingen fra 29. august.

- Posisjonsnumre i en ytelsesbeskrivelse («2.3.3.3, 2.3.3.4, 2.3.3.5»
  under hverandre) ble tatt for IP-adresser og fjernet fra resultatet;
  tretrinns numre med årstallslignende siste ledd («2.3.19, 2.3.20») falt
  som kalenderdatoer. En stigende nummerrekke ved linjebegynnelsen gjelder
  nå som det den er – en posisjonsliste; ekte adresser (nettverkstabeller
  med teknisk ordmiljø, tall over 99) og ekte datoangivelser gjenkjennes
  fortsatt.

- Etternavn som «Müller», «Fischer», «Bauer», «Koch», «Wagner»,
  «Schneider», «Weber», «Jäger», «Schmied», «Becker», «Schuster»,
  «Schäfer» eller «Meister» ble stående i klartekst i lister av formen
  «Etternavn, Fornavn» (f.eks. «Teilnehmer: Müller, Peter; Nowak, Anna»),
  fordi de samtidig er vanlige yrkesbetegnelser. De gjenkjennes nå
  pålitelig.

- Ved sladding av en PDF kunne stripen i smale tabellceller ta med seg
  hele cellen: Av treffet «D-LINK» i en ytelsesbeskrivelse ble hele
  produktbeskrivelsen ved siden av fjernet, selv om forhåndsvisningen
  bare hadde nevnt treffet. Stripen dekker fortsatt hele
  adresseblokk-linjer og feltmerkinger, men svelger høyst så mye
  uinvolvert som den dekker beskyttelsesverdig – beskrivelsen ved siden
  av treffet blir nå stående.

- Etter «Tilbakestill visning» i etterredigeringsprogrammet forble
  sidefeltet tomt – miniatyrene av sidene ble først synlige igjen etter
  lukking og gjenåpning av vinduet. Nå står de også direkte etter
  tilbakestillingen der, midtstilt som før.

- Etterredigeringsprogrammet har et fjerde verktøy: **Fjern** tar teksten
  under rammen bort uten erstatning – uten stripe (sladd) og uten
  plassholder (erstatt); hullet forblir synlig tomt. Det arbeider
  ordnøyaktig, ligger det et bilde under, ryddes bunnen dets hvit, og
  «Hent tilbake original» angrer også en fjerning uten erstatning. Eget
  symbol i linjen og trådkors-merke (kryss), egen huskeknapp på alle 18
  språk (tysk F som i «entFernen»).

- I PDF-søkelinjen står «Mappe …» nå til høyre for søkealternativene.
  Siden det ved siden av sladding også finnes erstatning av treff, fikk
  fem knapper ved vanlig vindusbredde ikke lenger plass ved siden av
  hverandre – den første ble klemt sammen og teksten dens avkuttet.

- «Tilbakestill alle innstillinger» tilbakestiller nå også avkrysningen
  «Erstatt rødt/grønt med andre farger» og merker den som enhver annen
  med «endret», hvis den avviker fra leveringen.

- Erstatningstekster i PDF-er virker nå jevnere: Der hele plassholderen
  klart måtte blitt mindre enn linjen sin (for eksempel «[BEG16]» klemt
  inn i et kort ord som «Das»), står det i stedet en kortform i
  linjestørrelse («[B16]») – godt leselig i stedet for bitteliten, og
  nummeret for tilbakehenting bærer begge skrivemåtene. Bitteliten blir
  en plassholder bare når selv den korteste formen ikke finner plass –
  det forblir bedre enn en stripe uten noen opplysning.

- En flerfarget satt erstatningstekst (overgang eller regnbue) i en PDF
  forble bare hel til neste inngrep: Hver ytterligere erstatning eller
  sladding på samme side kunne skyve allerede satte plassholdere sammen
  til en uleselig, sammenpresset bokstavstabel – den som erstattet ord
  for ord i redigeringsprogrammet, så i stedet for «[BEG17]» bare
  oppåtrykte tegn. Engang satte plassholdere blir nå stående slik de ble
  satt.

- Bryteren for varige unntak i forhåndsvisningen heter nå «Fjern aldri» –
  som listen den skriver til; tidligere sto det «aldri igjen». Trefflinjen
  ved siden av er ryddigere: Informasjonssymbolet «ⓘ» er større og
  lettere å treffe, og boks, erstattmerke og knapp har felles høyde.
  Setningen rundt et funn bruker nå virkelig den annonserte bredden sin –
  den tidligere breddeangivelsen hadde stilltiende blitt forkastet av
  visningen, og utsnittet brøt om som en smal stripe.

- I redigeringsprogrammet sier musepekeren nå hvilket verktøy som virker:
  et trådkors for å sikte, ved siden av et lite tegn – stripe for sladd,
  byttepiler for erstatt, angre-bue for gjenoppretting, pikselrutenett
  for pikselering. De tidligere håndsymbolene bortfalt; en hånd betyr
  ellers overalt «gripe og skyve». Den har nå en passende oppgave: Over
  et rødt fremhevet ord eller en stripe blir pekeren til en pekende hånd –
  ett klikk holder der.

- «Maksimal gjenkjenning (KI)» tilbyr ikke lenger en nedlastbar, lokal
  språkmodell – nivået regner nå utelukkende via en under «Koble til egen
  KI» oppsatt, egen KI. Den som allerede har koblet til en egen server,
  merker ingen forskjell.

- Den veiledede rundturen for forhåndsvisningen forklarer nå også
  informasjonssymbolet «ⓘ», som viser setningen rundt et funn. Og denne
  setningen selv er mer leselig: ett trinn større skrift, mer
  linjeavstand, fast bredde i stedet for et smalt, tett presset
  linjeskift.
- Også «Kontroller fil», «Gjenkjenningsregler og egne begreper», «Rens
  tekst» og «Rens bilde» har nå en egen rundtur – via en ny knapp
  «Rundtur gjennom vinduet», siden disse fire vinduene ikke har en egen
  menylinje.
- Navn under ni ukrainske kontraktrolle-merkinger forble ufullstendig
  gjenkjent ved et homografisk etternavn, når merkingen sto alene på sin
  linje: «Покупець»/«Продавець» (kjøper/selger), «Поручитель»/«Боржник»
  (kausjonist/hoveddebitor), «Свідок» (vitne), «Орендодавець»/«Орендар»
  (utleier/leietaker) og «Спадкодавець»/«Спадкоємець» (arvelater/arving).
  Navnene gjenkjennes nå fullstendig.

- Kommentaren til et navngitt område i en Excel-arbeidsbok
  (navnebehandler, feltet «Kommentar») bar et der innført navn uendret
  videre. Det renses nå like mye som resten av innholdet i arbeidsboken.

- Navn under sju ungarske kontraktrolle-merkinger forble helt
  uoppdaget ved et homografisk etternavn: «Bérbeadó»/«Bérlő»
  (utleier/leietaker), «Vevő»/«Eladó» (kjøper/selger), «Kezes»/«Főadós»
  (kausjonist/hoveddebitor) og «Tanú» (vitne). Navnene gjenkjennes nå
  fullstendig.

- Navn under den tsjekkiske kjøper-merkingen «Kupující» forble helt
  uoppdaget ved et homografisk etternavn. Navnet gjenkjennes nå
  fullstendig.

- Navn under den russiske vergemerkingen «Опекун» forble helt uoppdaget
  ved et homografisk etternavn. Navnet gjenkjennes nå fullstendig.

- Navn under seks ytterligere kroatiske merkinger forble uoppdaget:
  «Jamac» (kausjonist), «Glavni dužnik»/«Dužnik» (hoveddebitor/debitor),
  «Ostavitelj» (arvelater), «Nasljednik» (arving) og «Vjerovnik»
  (kreditor). Navnene gjenkjennes nå fullstendig.

- En lagret HTML-side med en innebygd underside i `src`-attributtet til
  en `<embed>` (i stedet for `data` ved `<object>`) bar
  personopplysninger i den uendret videre. De renses nå like mye som ved
  `<object>`.

- Navn under fem danske kontraktrolle-merkinger forble ufullstendig
  gjenkjent ved et homografisk etternavn, når merkingen sto med kolon
  foran navnet: «Arvelader»/«Arving», «Befuldmægtiget»/«Fuldmagtsgiver»
  og «Værge» (verge). Navnene gjenkjennes nå fullstendig; de tilsvarende
  norske merkingene er også lagt til som en sikring.

- Plassholdere i Word- og PowerPoint-filer bærer nå samme farge som i
  det valgte utseendet (ensfarget, overgang, regnbue eller per kategori)
  – tidligere forble de der i vanlig tekstfarge, selv om PDF-resultater
  for lengst kom farget ut.

- «Kopiér som tekst» og «Kopiér som Markdown» legger klarteksten til
  resultatet direkte på utklippstavlen – for innliming i chat, e-post
  eller et annet program, uten å åpne filen først.

- Navn under fem ytterligere slovenske merkinger forble uoppdaget:
  «Toženec» (saksøkt), «Tožnik» (saksøker), «Zastavitelj» (pantsetter),
  «Zastavni upnik» (pantekreditor) og «Darovalec» (giver). Navnene
  gjenkjennes nå fullstendig.

- Forfatternavnet til en sporet tabellcelle-endring (innsatt, slettet
  eller sammenslått celle i Word) ble stående i filen, selv om samme navn
  som kommentarforfatter for lengst var fjernet. Det fjernes nå også.

- Navn under ni ytterligere slovenske merkinger forble uoppdaget:
  «Najemodajalec»/«Najemnik» (utleier/leietaker),
  «Zapustnik»/«Dedič» (arvelater/arving), «Upnik»/«Dolžnik»
  (kreditor/debitor), «Glavni dolžnik» (hoveddebitor) og «Skrbnik»
  (verge/omsorgsperson). Navnene gjenkjennes nå fullstendig.

- Navn under fem slovenske merkinger forble uoppdaget: «Izvedenec»
  (sakkyndig), «Kupec» (kjøper), «Prodajalec» (selger), «Naročnik»
  (oppdragsgiver) og «Izvajalec» (oppdragstaker). Navnene gjenkjennes nå
  fullstendig.

- Navn under fem ytterligere litauiske merkinger forble uoppdaget:
  «Užsakovas» (oppdragsgiver), «Vykdytojas» (oppdragstaker), «Vežėjas»
  (transportør), «Siuntėjas» (avsender) og «Arbitras» (voldgiftsdommer).
  Navnene gjenkjennes nå fullstendig.

- Navn under seks ytterligere litauiske merkinger forble uoppdaget:
  «Įgaliotinis» (fullmektig), «Įgaliotojas» (fullmaktgiver), «Naudos
  gavėjas» (begunstiget, forsikring), «Trečiasis asmuo» (biintervenient/
  tredjepart i sivilprosess), «Ankstesnis nuomininkas» (tidligere
  leietaker) og «Naujasis nuomininkas» (ny leietaker). Navnene
  gjenkjennes nå fullstendig.

- Et bokmerke i ODT-dokumenter (`text:bookmark`) bærer navnet sitt fritt
  tildelt, ofte navngitt etter stedet det peker til (f.eks.
  «Herr_Mueller_Unterschrift») – usynlig for leseren, men ordrett i filen.
  Navnet renses nå med.

- Navn under åtte ytterligere litauiske merkinger forble uoppdaget:
  «Pareiškėjas» (søker), «Suinteresuotas asmuo» (motpart i
  ikke-omtvistet sak), «Ekspertas» (sakkyndig), «Bankroto administratorius»
  (konkursbo-forvalter), «Valdybos narys» (styremedlem), «Direktorius»
  (daglig leder), «Palikėjas» (arvelater) og «Įpėdinis» (arving). Navnene
  gjenkjennes nå fullstendig.

- Navn under sju ytterligere litauiske merkinger forble uoppdaget:
  «Liudytojas» (vitne), «Vertėjas» (tolk/oversetter), «Notaras» (notarius),
  «Dovanotojas» (giver), «Apdovanotasis» (mottaker av gave), «Pirkėjas»
  (kjøper) og «Pardavėjas» (selger). Navnene gjenkjennes nå fullstendig.

- Navn under seks ytterligere litauiske merkinger forble uoppdaget:
  «Globėjas» (verge/omsorgsperson), «Palikimo administratorius»
  (bobestyrer), «Laiduotojas» (kausjonist), «Pagrindinis skolininkas»
  (hoveddebitor), «Nuomotojas» (utleier) og «Nuomininkas» (leietaker).
  Navnene gjenkjennes nå fullstendig.

- Et navn under den litauiske merkingen «Ieškovas»/«Atsakovas»
  (saksøker/saksøkt som prosesspart) forble uoppdaget, uansett om
  etternavnet samtidig var et vanlig ord (f.eks. «Vilkas» = ulv) eller
  ikke. Navnet gjenkjennes nå fullstendig.

- En personregisteroppføring i ODT-dokumenter (bokmerke for stikkordregister)
  bar navnet en andre gang i sin egen sorteringsnøkkel – usynlig i løpende
  tekst, men ordrett i det senere genererte registeret. Nøkkelen renses
  nå med.

- Lysbildenavnet og seksjonsnavnet i en PowerPoint-presentasjon (synlig i
  utvalgsområdet henholdsvis i lysbildesorteringen) forble urenset, fordi
  begge henger som attributt på et element som ikke er lysbildetekst.
  Begge gjenkjennes nå.

- Et litauisk dobbeltnavn med bindestrek som «Petraitis-Kazlauskas» mistet
  den andre halvparten sin så snart det sto en hvilken som helst løpende
  tekst foran (bare ved tekstbegynnelsen forble det fullstendig):
  Etternavnet gjenkjennes nå også da fullt ut.

- Et navn under merkingen «Cesionar» (kroatisk, cessjonar ved
  fordringsoverdragelse) skapte et falskt treff, fordi selve feltmerkingen
  feilaktig ble lest som en person. Et navn under den russiske merkingen
  «Цессионарий» (også cessjonar) forble derimot helt uoppdaget. Begge
  tilfellene er nå rettet.

- Et navn under merkingen «Zedent»/«Zessionar» (tysk,
  fordringsoverdragelse) forble uten erstatning uoppdaget, når etternavnet
  samtidig var et vanlig ord (f.eks. «Bauer»). Navnet gjenkjennes nå
  fullstendig.

- Et navn under merkingen «Darczyńca»/«Obdarowany» (polsk, giver/mottaker
  i gaveavtale) forble uoppdaget, når etternavnet samtidig var et vanlig
  ord (f.eks. «Wilk» = ulv). Likeledes ble den rumenske merkingen
  «Donatar» (mottaker) hengende ved et vanlig etternavn selv som antatt
  navnedel. Begge tilfellene er nå rettet.

- Et navn under merkingen «Wierzyciel»/«Dłużnik» (polsk,
  utleggskreditor/utleggsdebitor henholdsvis generell kreditor/debitor)
  forble uoppdaget, når etternavnet samtidig var et vanlig ord (f.eks.
  «Wilk» = ulv). Navnet gjenkjennes nå fullstendig.

- Et navn under merkingen «Poręczyciel»/«Dłużnik główny» (polsk,
  kausjonist/hoveddebitor i kausjonsavtaler) forble uoppdaget, når
  etternavnet samtidig var et vanlig ord (f.eks. «Wilk» = ulv). Navnet
  gjenkjennes nå fullstendig.

- Et navn under merkingen «Ubezpieczony»/«Ubezpieczający» (polsk,
  forsikrede/forsikringstaker i forsikringspoliser) forble delvis eller
  helt uoppdaget, når etternavnet samtidig var et vanlig ord (f.eks.
  «Wilk» = ulv). Likeledes forsvant et navn under
  «Osiguranik»/«Osiguravatelj» (kroatisk, samme roller) fullstendig
  sammen med fornavnet (f.eks. «Golub» = due). Begge navnene gjenkjennes
  nå fullstendig.

- Et navn under merkingen «Pełnomocnik»/«Mocodawca» (polsk,
  fullmektig/fullmaktgiver i fullmaktsdokumenter) forble uoppdaget, når
  etternavnet samtidig var et vanlig ord (f.eks. «Wilk» = ulv). Likeledes
  forsvant et navn under «Opunomoćenik»/«Opunomoćitelj» (kroatisk, samme
  roller) til og med fullstendig sammen med fornavnet. Begge navnene
  gjenkjennes nå fullstendig.

- Et navn under merkingen «Pozwany» (polsk, saksøkt som prosesspart)
  forble uoppdaget, når etternavnet samtidig var et vanlig ord (f.eks.
  «Wilk» = ulv). Navnet gjenkjennes nå fullstendig.

- Et navn under merkingen «Najmoprimac»/«Najmodavac» (kroatisk,
  leietaker/utleier i leieavtaler) forble uoppdaget, når etternavnet
  samtidig var et vanlig ord (f.eks. «Kovač» = smed). Navnet gjenkjennes
  nå fullstendig.

- Et navn under merkingen «Pracodawca»/«Pracownik» (polsk,
  arbeidsgiver/arbeidstaker som avtalepart i arbeidsavtaler) forble delvis
  uoppdaget, når etternavnet samtidig var et vanlig ord (f.eks. «Krawiec»
  = skredder). Navnet gjenkjennes nå fullstendig.

- Ungarn hadde i landkatalogen bare personidentifikasjonene og
  merverdiavgifts-ID-en: Handelsregisternummeret (Cégjegyzékszám)
  gjenkjennes nå, forutsatt at feltordet «Cégjegyzékszám» eller
  forkortelsen «Cg.» står umiddelbart foran – selve nummeret bærer ikke
  noe kontrollsiffer.

- Estland hadde i landkatalogen bare Isikukood: Käibemaksukohustuslase
  number (merverdiavgifts-ID på hver estisk faktura) gjenkjennes nå med
  kontrollsiffer.

- Latvia hadde i landkatalogen bare personkoden: PVN reģistrācijas
  numurs for juridiske personer (foretaksidentifikasjon på hver latvisk
  faktura) gjenkjennes nå med kontrollsiffer.

- En e-post med kryptert innhold (S/MIME- eller PGP/MIME-konvolutt,
  `multipart/encrypted`) ble uten noen advarsel gitt ut som tilsynelatende
  fullstendig kontrollert, selv om det egentlige innholdet var kryptert
  og dermed forble ukontrollert. Slike e-poster henviser nå til dette som
  et ukontrollert vedlegg.

- Malta manglet i landkatalogen: Den maltesiske merverdiavgifts-ID-en
  (VAT number) gjenkjennes nå.

- Luxembourg manglet i landkatalogen: Den luxembourgske
  merverdiavgifts-ID-en (n° TVA) gjenkjennes nå.

- Et setningsinnledende bulgarsk «Изчакайте» («Vent!») ble meldt som
  stedsangivelse – samme modellgrense som tidligere ved ungarske,
  polske, tsjekkiske og andre oppfordringsformer uten egen språkmodell.
  Det falske treffet uteblir nå.

- Et navn under merkingen «Zleceniodawca», «Zleceniobiorca» (polsk),
  «Prestator» (rumensk), «Naručitelj» eller «Izvođač» (kroatisk) forble
  delvis eller helt uoppdaget, når etternavnet samtidig var et vanlig ord
  (f.eks. «Wilk», «Vuk» = ulv, «Vulpe» = rev, «Sokol» = falk). Navnet
  gjenkjennes nå fullstendig.

- Et navn under merkingen «Nadawca» (polsk), «Afsender» (dansk) eller
  «Pošiljatelj» (slovensk) forble delvis eller helt uoppdaget, når
  etternavnet samtidig var et vanlig ord (f.eks. «Sowa» = ugle, «Bager» =
  baker, «Volk» = ulv). Navnet gjenkjennes nå fullstendig.
- Et navn under merkingen «Gavėjas» (litauisk) eller «Prejemnik»
  (slovensk) forble delvis eller helt uoppdaget, når etternavnet samtidig
  var et vanlig ord (f.eks. «Vilkas» = ulv). Som allerede ved «Primatelj»
  (kroatisk) og «Modtager» (dansk) gjenkjennes navnet nå fullstendig.

- En rundskrivoverskrift som «To All Staff» eller «To All Employees» ble
  feilaktig gjenkjent og fjernet som personnavn. Dette forekommer ikke
  lenger.

- Et navn under merkingen «Primatelj» (kroatisk) eller «Modtager» (dansk)
  forble delvis uoppdaget, når etternavnet samtidig var et vanlig ord
  (f.eks. «Golub» = due, «Bager» = baker). Som allerede ved «Odbiorca»
  (polsk) og «Destinatar» (rumensk) gjenkjennes navnet nå fullstendig.

- Et fullstendig navn i signaturlinjen til et dansk, norsk eller gresk
  dokument forble delvis uoppdaget, når merkingen «Underskrift» eller
  «Υπογραφή» sto alene over navnet – i det greske tilfellet ble
  etternavnet til og med gjenkjent som stedsangivelse i stedet for navn.
  Som allerede ved «Подпись» (russisk) gjenkjennes navnet nå fullstendig.

- Tekst på et sidelagt telefonfoto (den vanlige stående opptaksformen, som
  bare vises stående via et bildedreiemerke) kunne bli oversett av
  tekstgjenkjenningen, fordi den tidligere leste de rå, liggende
  bildepunktene. Slike fotografier dreies nå riktig vei før lesing – som
  tidligere allerede ved ansiktsgjenkjenningen.

- Et fullstendig navn i signaturlinjen til et russisk, ukrainsk eller
  litauisk dokument forble delvis uoppdaget, når merkingen «Подпись»,
  «Підпис» eller «Parašas» sto alene over navnet – for- eller
  farsnavn falt bort. Som allerede ved «Potpis» (kroatisk) gjenkjennes
  navnet nå fullstendig.

- Et ansikt på et sidelagt telefonfoto (den vanlige stående
  opptaksformen, som bare vises stående via et bildedreiemerke) kunne bli
  oversett av ansiktsgjenkjenningen, fordi den tidligere kontrollerte de
  rå, liggende bildepunktene. Slike fotografier dreies nå riktig vei før
  søket.

- Et fullstendig navn i signaturlinjen til et kroatisk dokument forble
  delvis uoppdaget, når merkingen «Potpis» sto alene over navnet eller
  med kolon foran – fornavnet falt bort, enten som egen linje eller i
  «Potpis: Fornavn Mellomnavn Etternavn». Som allerede ved «Unterschrift»
  og «Signature» gjenkjennes navnet nå fullstendig.

- Et ektefellesnavn bak sivilstandsforkortelsene «verh.» (gift) og
  «verw.» (enkeenke/enkemann) forble hittil fullstendig uoppdaget, uansett
  om det sto i parentes, etter komma eller uten mellomrom klistret på
  («Anna Meier (verh. Weber)», «Klaus Bauer (verw.Fischer)») – som
  allerede ved «geb.» gjenkjennes det nå pålitelig.

- Et navn bak prokurasignaturen «ppa.» (f.eks. i signaturlinjen til en
  forretnings-e-post eller et forretningsbrev) forble ved et yrkeslikt
  etternavn som «Bauer» eller «Koch» hittil delvis eller helt uoppdaget –
  som allerede ved «gez.» gjenkjennes det nå pålitelig.

- Nummeret på det polske ID-kortet (dowód osobisty) ble bare gjenkjent
  uten mellomrom mellom serie og nummer («ABS123456»). Nettopp slik
  trykker imidlertid ikke dokumentet angivelsen – offisielt står det et
  mellomrom mellom («ABS 123456»), og i denne skrivemåten forble nummeret
  hittil uoppdaget.

- En animert PNG (APNG, f.eks. et kort skjermopptak lagret som PNG i
  stedet for GIF) ble hittil bare kontrollert og renset med sitt første
  bilde, uten at dette ble meldt – som tidligere ved animert WebP melder
  Maskuro nå at hvert ytterligere bilde forblir ukontrollert i resultatet.

- Et animert WebP-bilde (f.eks. fra et skjermbildeverktøy eller en
  chat-applikasjon med flere bilder i én fil) ble hittil bare kontrollert
  og renset med sitt første bilde, uten at dette ble meldt – som tidligere
  ved en flersiders TIFF melder Maskuro nå at hvert ytterligere bilde
  forblir ukontrollert i resultatet.

- Et slovensk dobbelt-fornavn med bindestrek («Ana-Marija Novak») mistet
  den fremre halvparten sin så snart løpende tekst gikk foran i teksten –
  samme feil som tidligere ved polsk. «Ana-» ble stående ubelagt i
  klartekst, mens resten av navnet allerede var erstattet.

- Et polsk dobbelt-fornavn med bindestrek («Anna-Maria Kowalska») mistet
  den fremre halvparten sin så snart løpende tekst eller en preposisjon
  som «z»/«od» gikk foran – resten av navnet ble erstattet, «Anna-» ble
  stående ubelagt i klartekst.

- Kasakhiske høflighetsformer «Хабарласыңыз»/«Байланысыңыз» (kontakt oss)
  samt serbiske verbformer «Помоћи», «Чекамо» og «Пишите» uten egen
  språkgjenkjenningsmodell ble i telefonsetninger feilaktig gjenkjent
  som personnavn eller sted.

- Aserbajdsjansk høflighetsord «Xahiş» (vær snill/anmodning) uten egen
  språkgjenkjenningsmodell ble i telefonsetninger feilaktig gjenkjent som
  personnavn.

- Indonesiske og malaysiske høflighets-/oppfordringsord uten egen
  språkgjenkjenningsmodell som «Silakan», «Mohon» (indonesisk), «Sila» og
  «Tolong» (malaysisk) ble i telefonsetninger feilaktig gjenkjent som
  personnavn eller sted.

- Usbekisk oppfordringsform «Kutamiz» (vi venter) uten egen
  språkgjenkjenningsmodell ble i telefonsetninger feilaktig gjenkjent som
  sted.

- Tyrkiske oppfordringsformer uten egen språkgjenkjenningsmodell som
  «Arayınız» (ring oss) og «Bekliyoruz» (vi venter) ble i
  telefonsetninger feilaktig gjenkjent som personnavn.

- Oppfordringsformer på flere språk uten egen språkgjenkjenningsmodell
  (tsjekkisk, slovakisk, gresk) som «Zavolejte» (ring), «Prosíme» (vi
  ber) og «Περιμένουμε» (vi venter) ble i telefonsetninger feilaktig
  gjenkjent som personnavn eller sted.

- Ungarske og polske oppfordringsformer som «Hívjon» (ring), «Kérjük» (vi
  ber), «Várjuk» (vi venter), «Zadzwoń» (ring) og «Czekamy» (vi venter)
  ble i telefonsetninger feilaktig gjenkjent som personnavn eller sted.

- I en nummerert navneliste uten tabellform (f.eks. «1. Robert Brown»,
  under «2. Mary Johnson») ble et navn med bestemte engelske etternavn
  (blant annet «Brown», «White», «Green», «Black», «Young») fullstendig
  oversett – språkmodellen hadde hengt nummeret til den følgende linjen
  på navnet, slik at treffet aldri lenger passet eksakt.

- Ved den polske språkmodellen forble den foranstilte fornavnsinitialen
  foran et etternavn (f.eks. «J. Kowalski», «A. Nowak») ugjenkjent og
  urenset i teksten – bare etternavnet ble erstattet. Andre kontrollerte
  språk (blant annet tysk, engelsk, rumensk, kroatisk, ungarsk, russisk)
  tok allerede tidligere samme initial med.

- Et personnavn bak en liten skrevet tittel som «dr.», «ing.» eller
  «dipl. ing.» ble overhodet ikke gjenkjent på ungarsk, rumensk og
  kroatisk – ikke bare tittelen, men hele navnet gikk tapt (f.eks. «dr.
  Kovács Béla», «ing. Andrei Popescu», «dipl. ing. Marko Horvat»).
- I slovenske møteprotokoller ble en ren rollebetegnelse foran kolon
  (f.eks. «Tajnik:», «Podpredsednik:», «Poročevalec:», «Predsedujoči:»)
  feilaktig gjenkjent som personnavn, så snart det et annet sted i
  protokollen allerede sto et ekte talernavn.
- I russiske møteprotokoller ble en ren rollebetegnelse foran kolon
  (f.eks. «Секретарь:», «Докладчик:», «Докладчица:») feilaktig gjenkjent
  som personnavn, så snart det et annet sted i protokollen allerede sto
  et ekte talernavn.
- I rumenske møteprotokoller ble en ren rollebetegnelse med bestemt
  artikkel foran kolon (f.eks. «Secretarul:», «Președintele:»,
  «Vicepreședintele:», «Moderatorul:», «Consilierul:») feilaktig
  gjenkjent som personnavn – «Președintele» allerede alene, de øvrige i
  tillegg så snart det et annet sted i protokollen allerede sto et ekte
  talernavn.
- I kroatiske møteprotokoller ble en ren rollebetegnelse foran kolon
  (f.eks. «Izvjestiteljica:», «Zapisničar:»/«Zapisnicar:»,
  «Predsjedavajući:») feilaktig gjenkjent som personnavn.
- En polsk postboksadresse «Skrytka pocztowa» bak en avsender- eller
  mottakermerking (f.eks. «Odbiorca: Skrytka pocztowa 45») ble
  feilaktig gjenkjent som personnavn.
- En kroatisk postboksadresse «Poštanski pretinac» bak
  adressemerkingen «Adresa:» (f.eks. «Adresa: Poštanski pretinac 45»,
  også med tilhengt «br.» for nummeret) ble feilaktig gjenkjent som
  personnavn.
- Et sted uten videre merking i norsk løpende tekst (f.eks. «Anna Hansen
  bor i Oslo») ble ikke gjenkjent – den egne språkmodellen navngir der
  steder som regel med en egen, hittil ikke tilordnet etikett i stedet
  for den vanlige «LOC».
- En dato i ISO-rekkefølgen år-måned-dag med bindestrek eller punktum
  (f.eks. «2024-12-31») ble på enkelte språk overhodet ikke gjenkjent som
  dato – mest påfallende på litauisk, der offisielle skriv overveiende
  angir datoer i denne rekkefølgen.
- En ungarsk merverdiavgifts-ID (közösségi adószám) i den offisielt like
  gyldige, skilletegnfrie 11-sifrede formen (f.eks. «12345678123» i
  stedet for «12345678-1-23») ble ikke gjenkjent.
- Et polsk skattenummer NIP med skilletegn i grupperingen 3-2-2-3 (f.eks.
  «856-73-46-215», slik den er vanlig på fakturaer fra foretak og
  enkeltmannsforetak) ble ikke gjenkjent – bare grupperingen 3-3-2-2 for
  fysiske personer traff.
- Et firmanavn under den slovakiske feltmerkingen «Zamestnávateľ:» eller
  «Názov zamestnávateľa:» (arbeidsgiver/firma) ble ikke gjenkjent.
- Et firmanavn under den rumenske feltmerkingen «Angajator:» eller
  «Denumire angajator:» (arbeidsgiver/firma) ble ikke gjenkjent.
- Et firmanavn under den ungarske feltmerkingen «Cég:» eller
  «Munkáltató:» (firma/arbeidsgiver) ble ikke gjenkjent.
- Et firmanavn under den polske feltmerkingen «Pracodawca:» eller «Nazwa
  firmy:» (arbeidsgiver/firma) ble ikke gjenkjent.
- Et firmanavn under den slovenske feltmerkingen «Podjetje:» eller
  «Delodajalec:» (firma/arbeidsgiver) ble ikke gjenkjent.
- Et firmanavn under den kroatiske feltmerkingen «Tvrtka:» eller
  «Poslodavac:» (firma/arbeidsgiver) ble ikke gjenkjent.
- Et utskrevet pengebeløp med liten forbokstav i valutaen (f.eks. «500
  euro») ble ikke gjenkjent, bare stor forbokstav («Euro») traff.
- Etternavnet bak «Schwager»/«Schwägerin» (svoger/svigerinne) (f.eks.
  «Svogeren Bauer mottar arven.») ble ikke gjenkjent.
- Ved en tyrkisk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «34000 İstanbul İstiklal Caddesi No: 45») forble
  husnummeret urenset.
- Ved en slovakisk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «831 01 Bratislava Hlavná 15») forble
  husnummeret urenset.
- Et fødselsland uten videre merking i et kroatisk skjemafelt (f.eks.
  «Zemlja rođenja: Njemačka») ble ikke gjenkjent.
- Et fødselsland uten videre merking i et litauisk skjemafelt (f.eks.
  «Gimimo valstybė: Vokietija») ble ikke gjenkjent.
- Et fødsels- eller bostedsland uten videre merking i et polsk skjemafelt
  (f.eks. «Kraj: Niemcy») ble ikke gjenkjent.
- Et statsborgerskaps- eller bostedssted uten videre merking i et
  slovensk skjemafelt (f.eks. «Državljanstvo: Nemčija») ble ikke
  gjenkjent.
- Et bostedsland uten videre merking i et norsk skjemafelt (f.eks.
  «Bosted: Tyskland») ble ikke gjenkjent.
- Ny innstillingsside «Varsler» (tidligere et avsnitt i «Program»): de
  tre oppgavelinjemeldingene (forhåndsvisning klar, behandling ferdig,
  oppdatering nedlastet) står nå på et eget sted.
- Nytt: Resultatet kan i tillegg lagres som ren tekstfil (.txt) eller med
  endelsen .md ved siden av – for videre behandling i en KI eller et
  annet program.
- Ved en kroatisk kontaktangivelse med merkingen «Osoba za kontakt»/
  «Kontakt osoba» (f.eks. «Osoba za kontakt: Golub Marko») forble navnet
  fullstendig ugjenkjent, når etternavnet samtidig var et vanlig
  substantiv (Golub = «due»).

- Ved en rumensk kontaktangivelse med merkingen «Persoana de contact»/
  «Persoană de contact» (f.eks. «Persoana de contact: Lup Ion») forble
  navnet fullstendig ugjenkjent, når etternavnet samtidig var et vanlig
  substantiv (Lup = «ulv») og fornavnet svært kort og generisk.

- Ved en polsk kontaktangivelse med merkingen «Osoba kontaktowa»/«Osoba
  do kontaktu» (f.eks. «Osoba kontaktowa: Wilk Adam») forble etternavnet
  ugjenkjent, når det samtidig var et vanlig substantiv (Wilk = «ulv»,
  Zielony = «grønn»).

- Ved en rumensk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «010061 București Strada Victoriei 30») forble
  husnummeret urenset.
- Ved en serbisk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «11000 Beograd Bulevar Kralja Aleksandra 73»)
  forble husnummeret urenset.
- Ved en gresk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «104 32 Αθήνα Ερμού 15») forble husnummeret
  urenset.
- Ved en slovensk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «1000 Ljubljana Slovenska cesta 58») forble
  postnummeret urenset.
- Ved en litauisk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «LT-01100 Vilnius Gedimino pr. 9») forble
  postnummeret fullstendig urenset.
- Ved en ungarsk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «1052 Budapest Kossuth Lajos utca 12») forble
  postnummeret urenset.
- Et etternavn bak «Erben» (arvinger) (f.eks. «Arvingene Wagner mottok
  meldingen innen fristen.») forble i arve-/dødsbokontekst så godt som
  alltid ugjenkjent.
- Et etternavn bak «Geschwister» (søsken) (f.eks. «Søsknene Bauer bor i
  Linz.») forble hittil så godt som alltid ugjenkjent – i motsetning til
  ved «Familie»/«Ehepaar» rammet dette ikke bare yrkeslike navn (Bauer,
  Richter, Koch), men vilkårlige etternavn på dette stedet.
- Et etternavn bak «Ehepaar» eller «Eheleute» (ektepar) (f.eks. «Ekteparet
  Koch flytter.») forble ugjenkjent, når det samtidig var et vanlig
  substantiv eller en yrkesbetegnelse (Koch, Bauer, Richter).
- Et vanlig bestillings-, ordre- eller artikkelnummer i det typiske
  grupperingsrutenettet til et skattenummer eller trygdenummer (f.eks.
  «030 4471 2298») ble uten noen tilhørende merking feilaktig sladdet som
  et slikt.
- Et bilags-/sakenummer i formatet «år/løpenummer» (f.eks. i «Faktura nr.
  4/2024/778899») ble av telefonnummergjenkjenningen feilaktig sladdet
  som telefonnummer.
- Et navn bak «Herr»/«Frau» med en flerords akademisk titelkjede foran
  («Herr Dr. med. Weber», «Herr Prof. Dr. Krause») forble hittil
  fullstendig ubeskyttet – gjenkjent ble tidligere bare ett enkelt
  tittelord mellom tiltaleform og navn.
- Et rettslig saksnummer i det klassiske formatet med kammer-/senat-
  forkortelse («4 Ca 1523/24», «Az.: 7 O 234/25») forble hittil
  fullstendig ubeskyttet – også den vanlige kortformen «Az.»/«Gz.» ved
  siden av den utskrevne merkingen ble ikke gjenkjent.
- Et kredittkortnummer som midt i firergrupperingen sin ble delt av et
  linjeskift – for eksempel i en smal tabellkolonne – forble hittil
  fullstendig ubeskyttet.
- Et skatteidentifikasjonsnummer som midt i grupperingen sin ble delt av
  et linjeskift – for eksempel i en smal tabellkolonne eller et
  skjemafelt – forble hittil fullstendig ubeskyttet.
- Et trygdenummer som midt i grupperingen sin ble delt av et linjeskift –
  for eksempel i en smal tabellkolonne – forble hittil fullstendig
  ubeskyttet, ikke engang delvis erstattet.
- Et husnummer med intervall som «12a-14b» eller «3-5» ble bare halvveis
  erstattet – den andre delen bak bindestreken forble åpen i resultatet.
- Et understellsnummer (VIN), som midt i sine 17 tegn ble delt av et
  linjeskift, mellomrom eller bindestrek – for eksempel i en smal
  tabellkolonne eller et vognkortfelt – forble hittil fullstendig
  ubeskyttet.
- En brev-/e-posttiltale som «Kjære Anna!» eller «Kjære Hans» – uten
  komma etter navnet, den vanligste formen i uformelle e-poster – lot
  navnet stå fullstendig ubeskyttet, også i det fulle dokumentet med
  løpende tekst og hilsen under.
- Samme hull rammet også de uformelle chat-/e-posttiltalene «Hallo
  Anna!», «Hi Anna!», «Hey Anna!» og «Servus Anna!» uten komma – navnet
  forble likeledes fullstendig ubeskyttet.
- En ren signaturblokk som begynner direkte med «MfG» eller «Herzlichst»
  – for eksempel kopiert fra utklippstavlen, uten foregående setning –
  lot navnet under stå fullstendig ubeskyttet.
- Et felt med flere personer, for eksempel «Angehörige: Kaczmarek, Piotr
  (Sohn), Kaczmarek, Anna (Ehefrau)», smeltet begge navnene sammen med
  parentesangivelsen til ett eneste, altfor langt treff – det andre
  navnet ble delvis stående ubeskyttet i resultatet.
- En gate uten etterstavelsen «-straße»/«-weg» – slik det er vanlig på
  landet, for eksempel «Am Marktplatz 5» eller «Im Grund 12» – forble
  ugjenkjent, når en postnummer-sted-linje fulgte, for eksempel i en
  bostedsattest: «Neue Anschrift: Am Weidengarten 17, 54295 Trier»
  mistet gaten fullstendig, bare postnummeret ble fjernet.
- Et navn bak en sammensatt feltmerking med skråstrek (for eksempel
  «Name/Vorname: Bauer Klaus») ble delvis ikke gjenkjent – et flertydig
  etternavn som «Bauer» forble uoppdaget uten feltbelegget. Samme hull
  rammet kombinasjonsfelt som «PLZ/Ort: 04109 / Leipzig». Det samme
  gjaldt for kombinasjonsfelt med utskrevet bindeord i stedet for
  skråstrek, for eksempel «Vor- und Nachname: Bauer Klaus» eller
  «Nachname bzw. Vorname: …».
- En fødselsdato i formen «Datum der Geburt: …» og en dødsdato i formen
  «Todesdatum: …» eller «Datum des Todes: …» ble ikke gjenkjent – bare
  «Geburtsdatum: …» henholdsvis «Sterbedatum: …» traff.
- En bryllupsdato i formen «Datum der Heirat: …» eller «Datum der
  Hochzeit: …» ble ikke gjenkjent – bare «Hochzeitsdatum: …»,
  «Heiratsdatum: …» og «Datum der Eheschließung: …» traff, selv om
  skilsmisse-, naturaliserings- og partnerskapsdato lenge kjente samme
  «Datum der X»-form.
- En skilsmissedato i formen «Datum der Scheidung: …» ble ikke gjenkjent
  – bare «Scheidungsdatum: …» og den etterstilte verbformen traff, selv
  om naturaliserings- og partnerskapsdato kjente samme «Datum der
  X»-form fra begynnelsen av.
- En partnerskapsdato ble hittil overhodet ikke gjenkjent – verken med
  merking («Verpartnerungsdatum: …», «Datum der Lebenspartnerschaft: …»)
  eller i løpende tekst («… ble partnerskapsregistrert den …»). Nå
  erstattes den som fødsels-, bryllups-, skilsmisse- og
  naturaliseringsdato som egen angivelsestype.
- En naturaliseringsdato ble hittil overhodet ikke gjenkjent – verken med
  merking («Einbürgerungsdatum: …») eller i løpende tekst («… ble
  naturalisert den …»). Nå erstattes den som fødsels-, bryllups- og
  skilsmissedato som egen angivelsestype.
- En skilsmissedato ble hittil overhodet ikke gjenkjent – verken med
  merking («Scheidungsdatum: …») eller i løpende tekst («Ekteskapet ble
  oppløst den …»). Nå erstattes den som fødsels-, dødsfalls- og
  bryllupsdato som egen angivelsestype.
- En bryllupsdato bak genealogitegnet «⚭» uten merking ble ikke
  gjenkjent, selv om fødsels- og dødsdato på samme linje via stjerne og
  kors allerede ble gjenkjent – nå gjenkjennes også bryllupsdatoen.
- En dødsdato bak dødsannonse-korset uten merking («*03.06.1940
  †21.11.2023») ble ikke gjenkjent, selv om fødselsdatoen foran via
  genealogistjernen allerede ble gjenkjent – nå gjenkjennes også
  dødsdatoen.
- Etternavn før fornavn på slutten av en emne-/ticketlinje med
  foranstilt saksord og bindestrek («Betreff: Reklamation - Bauer,
  Anna») ble ved et yrkeslikt etternavn ikke gjenkjent – nå gjenkjennes
  det.
- Søker- og ansøkernumre bak merkingen sin («Bewerbernummer: 4471829»,
  «Antragstellernummer: 7654321») falt helt gjennom gjenkjenningen – nå
  gjenkjennes de.
- Erstatning sladder ikke lenger når det ikke er plass til en lesbar
  plassholder – en for liten plassholder skrives nå mindre i stedet for
  å bli en tom stripe, så lenge det overhodet er plass igjen. Nytt
  dessuten: Om et funnsted på et bilde (brevhode, skannebakgrunn) merkes
  eller bare sladdes, kan nå stilles inn uavhengig av den øvrige
  resultattypen. Og et funnsted på et bilde som fjernes helt, ble merket
  som om bildet ble stående – plassholderen sto lys på en bunn som aldri
  ble sladdet, og forsvant dermed usynlig på det nå hvite papiret.
- Et funnsted på et **bevart** bilde ble ved erstatning alltid sladdet
  svart-hvitt, uavhengig av valgt fremstilling (kategorifarger, regnbue
  …) – synlig som et brudd mellom fargede etiketter i løpende tekst og
  svarte striper på brevhodet. Bildebunnen følger nå samme farge som
  plassholderen ved siden av.
- Gjenkjenningen av kjøretøyidentifikasjonsnummeret (VIN) markerte hver
  17-sifret alfanumerisk kode uten I/O/Q betingelsesløst som
  understellsnummer – også ordre-, serie- og lisensnøkkelnumre som
  tilfeldigvis har samme form. Nå teller den bare med et kontekstord i
  nærheten («FIN», «VIN», «Fahrgestell», «Chassis» o.l.).
- I sak-/kalendersystemer rev navnegjenkjenningen med seg det neste
  feltordet etter «Assigned to»/«Closed by» o.l., når det fulgte direkte
  på samme linje uten skilletegn («Assigned to Max Mustermann Priority
  High» ble til «Max Mustermann Priority»). I Git-commit-hoder rev
  navnegjenkjenningen likeledes med seg den **neste** trailer-nøkkelen,
  når to linjer hang sammen med bare ett mellomrom i stedet for
  linjeskift («Author: julia bergmann Reviewed-by: …» ble til «julia
  bergmann Reviewed-by»). Begge bremser supplert.
- Navnet bak «p.A.», «zH»/«zHd», «i.A.»/«i.V.» og «geb.» rev et direkte
  påfølgende avdelingsord med inn i samme treff, når det sto uten
  skilletegn på samme linje («p.A. Max Mustermann Buchhaltung» ble til
  «Max Mustermann Buchhaltung», «i.A.Max Mustermann Vertrieb» til «Max
  Mustermann Vertrieb»). Samme bremse som ved «Assigned to»/Git-trailere
  nå også supplert her.
- En merket IBAN rett over BIC-, BLZ- eller SWIFT-linjen rev merkingen
  dens med inn i sitt eget treff, fordi «BIC» og «BLZ» selv så ut som en
  ytterligere nummerblokk – av «IBAN: DE89 … 0130 00» og linjen under ble
  det ett eneste, for vidtrekkende treff, og merkingen på neste linje
  forsvant med under rensingen. Berørt var nesten hver bankforbindelse
  med IBAN og BIC under hverandre.
- Treffpanelet sier nå **hvor** en plassholder står som det ikke kan
  finne på siden. To tilfeller meldte tidligere bare «ikke funnet», selv
  om erstatningen skjedde: Står plassholderen i usynlig bitekst – for
  eksempel lenkeadressen til en lenke, en anmerkning eller et
  skjemafelt –, bærer linjen dette nå som egen opplysning («i biteksten»),
  og klikket forklarer det. Og ble plassholderen skrevet forkortet på
  grunn av plassmangel («[N382]» i stedet for «[NAM382]»), hopper klikket
  på den lange linjen nå til kortform-stedet og nevner omdøpingen;
  tilordningen kobler for dette de to linjene uttrykkelig sammen.
- Står samme erstatningsverdi flere ganger i dokumentet, hopper hvert
  ytterligere klikk på panellinjen i en sirkel til neste funnsted – også
  over sidegrenser; statuslinjen teller med («funnsted 2 av 4»), og
  stedet som nettopp er valgt, er rammet mer markert enn de øvrige. Og
  når en plassholder bare står i trefflisten, men ikke noe sted i
  dokumentet (fordi stedet gikk opp i en overlappende erstatning), sier
  statuslinjen det nå, i stedet for at klikket forblir stille og uten
  virkning.
- Et forkortet fornavn bak «an» eller «für» (til/for) gjenkjennes nå
  pålitelig som navn – «Überweisung an M. Wagner» og «Rechnung für M.
  Wagner» forble tidligere ofte urenset stående, mens samme navn med
  annen merking foran (for eksempel «Zahlungsempfänger:») allerede ble
  funnet. Berørt var fremfor alt kontoutskrift- og bokføringslinjer.
- «Angeklagter»/«Angeklagte»/«Beschuldigter»/«Beschuldigte» (tiltalte)
  gjelder nå som navnefelt: Sto et navn i straffesaksdokumenter direkte
  bak en av disse merkingene, ble det tidligere overhodet ikke gjenkjent
  for rundt halvparten av de kontrollerte navnene – verken for- eller
  etternavn.
- Stedet klikket fra treffpanelet rammes nå blått i stedet for gult
  markert – på de fargede kontrollampeflatene var det gule søketreffet
  ikke til å gjenkjenne. Dessuten finner klikket nå også flerords
  erstatningsverdier (oppdiktede navn, maskerte numre): Tidligere forble
  det virkningsløst ved slike linjer, fordi funnstedet bare ble søkt ord
  for ord.
- Adoptiv-, foster- og stebforeldre («Adoptivvater», «Pflegemutter»,
  «Stiefvater» og flere) gjenkjennes nå som navnefelt, navnet falt
  tidligere gjennom urenset.
- Tallrike tabeller og lister forkastes ikke lenger feilaktig: Ble et
  kort tall (for eksempel en som telefonnummer feillest kundenummerdel)
  erstattet, meldte sluttkontrollen samme siffersekvens som en
  gjenværende angivelse også når den et annet sted bare tilfeldigvis
  inngikk i et helt annet nummer – og leverte da overhodet ikke noe
  resultat. Et tall teller nå bare som en rest der det står som et eget
  tall.
- Personstatusdokumenter: «Vater:»/«Mutter:» (far/mor) gjenkjennes nå
  som navnefelt, foreldrenavnet falt tidligere gjennom urenset.
- Ytterligere familieroller («Pate», «Großvater/-mutter», «Ehepartner»,
  «Lebenspartner», «Onkel», «Tante») gjenkjennes nå som navnefelt, navnet
  falt tidligere gjennom urenset.
- Det tyske bankkontonummeret (BLZ) gjenkjennes nå også offisielt
  gruppert («370 400 44», «370.400.44», «370-400-44», «370/400/44»),
  ikke lenger bare som åtte sammenhengende sifre.
- Det tyske pensjonsforsikringsnummeret gjenkjennes nå også med punktum,
  bindestrek eller skråstrek mellom de fem blokkene
  («65-170839-J-08-8», «65.170839.J.08.8»), ikke lenger bare med
  mellomrom.
- Hovedvinduet vises raskere: Gjenkjenningsbibliotekene (Presidio med
  språkmodellunderbygningen) ble tidligere allerede lastet under
  vindusoppbyggingen – på Windows rundt fire sekunder før det i det hele
  tatt var noe å se. De lastes nå fullstendig i bakgrunnen; knappen
  «Rens» blir som før først fri når alt er klart.
- Kontordokumenter med mange bilder eller videoer skrives raskere:
  Allerede komprimerte medier lagres i resultatpakken i stedet for
  nytteløst å komprimeres en gang til – dette sparte tidligere ingen
  byte og gjorde JPEG-er heller større.
- Regneark og andre dokumenter av mange små tekstenheter kontrolleres
  raskere: Språkgjenkjenningen behandler nå alle celler og avsnitt i et
  dokument i én gjennomgang i stedet for enkeltvis – ved påvist samme
  funn (400 celler: fra rundt 4,7 til 2,5–3,5 sekunder).
- Listelignende PDF-sider (registre, posisjonslister) er betydelig
  raskere ved innsetting av plassholderne: Plassøket per merking gikk
  tidligere over alle ordene på siden – nå bare over linjeomgivelsen, ved
  påvist samme resultat (på en side med 300 merkinger rundt seksten
  ganger raskere).
- Bilderike dokumenter sparer flere unødvendige arbeidstrinn per bilde:
  Tellingen av ansikter og koder på PDF-sider dekoder ikke lenger
  sidebildet dobbelt, kontrollen for metadata dekrypterer ikke lenger et
  rent bilde i det hele tatt, pikselerte bilder skrives med normal i
  stedet for den tregeste PNG-komprimeringen (samme størrelse, en
  tredjedel av tiden), og uten innstilt vannmerke bortfaller den
  nytteløse omskrivingen av hele PDF-en til slutt.
- Skannede PDF-er med påslått tekstgjenkjenning er betydelig raskere
  gjennom: Hver side ble tidligere gjengitt to ganger i full oppløsning
  (én gang for lesing, én gang for rastrering) – avbildet gjenbrukes nå.
  Og på Windows/Linux leser tekstgjenkjenningen stripene til en stor
  skanning i én omgang i stedet for med en egen programstart per stripe.
- Store dokumenter renses betydelig raskere: Sammenligningen av allerede
  funnede verdier vokste tidligere med antall funnsteder (en
  64-KB-tekstblokk kostet på slutten av en stor fil rundt ett sekund bare
  for dette, nå en sekstidel), og søket etter firma-rettsformer gikk med
  alle ~280 katalogformer over hvert tekststed (nå rundt tjue ganger
  raskere, ved påvist samme funn).
- Et navn direkte etter «Beste Grüße»/«Beste Wünsche» uten foregående
  tekst eller skilletegn ble overhodet ikke gjenkjent – en ren
  signaturblokk uten løpende tekst foran lot navnet forsvinne sporløst.
- Et adressefelt ved dokumentbegynnelsen med et yrkeslikt etternavn
  («Bauer Anna», «Koch Stefan» som første linje over gate og sted) forble
  tidligere delvis ugjenkjent eller ble klassifisert som stedsangivelse i
  stedet for person – uten foregående setning manglet språkmodellen
  setningsbygningen som ellers lar «Bauer» gjenkjennes som navn og ikke
  som yrke.
- Et navn bak signaturmerket «gez.» med et yrkeslikt etternavn foran
  fornavnet («gez. Bauer Anna» på slutten av et vedtak eller en dom)
  forble tidligere ufullstendig gjenkjent – bare fornavnet ble funnet,
  etternavnet forsvant sporløst.
- Et navn direkte bak et kundenummer, kontraktnummer eller lignende
  identifikasjonsnummer uten egen linje («Vertragsnummer 55219 Bauer
  Anna», «Kundennr. 4711 Bauer Anna») ble ved et yrkeslikt etternavn
  tidligere ufullstendig eller overhodet ikke gjenkjent.
- Symbolet i macOS-menylinjen er nå en mal som tilpasser seg lys- og
  mørkmodus som nabosymbolene – med de to utstansede stripene forblir
  det dermed gjenkjennelig som Maskuro. Kjører
  utklippstavlevakten, viser et avsatt punkt ved skjoldspissen det.
- Et klikk i treffpanelet fører nå også i anonymiserende drift til
  funnstedet: Bytte side, rulle inn i bildet, markere gult. Tidligere
  forble klikket der virkningsløst, fordi det fortsatt holdt
  plassholderne for nummerløse – siden hvert funnsted bærer sitt eget
  nummer, er stedet entydig. Bare ved den faktisk nummerløse
  plassholderen forklarer statuslinjen fortsatt hvorfor et hoppmål ikke
  kan bestemmes.
- Den første lagringen i etterredigeringsprogrammet (Ctrl+S eller
  diskettknappen) spør nå om stedet, som «Lagre som …» – forhåndsutfylt
  med mappen til originalen og resultatnavnet. Tidligere havnet filen
  ordløst ved siden av originalen. Den som allerede har valgt
  lagringsstedet via statuslinjen, blir ikke spurt en gang til; hver
  ytterligere lagring skriver som før samme fil videre.
- Melder sikkerhetskontrollen før lagring et påfallende sted, fører
  «Tilbake til kontroll» nå dit: Det første funnstedet ruller inn i
  bildet og rammes rødt, statuslinjen nevner det. Tidligere sto man alene
  med sidetall og punktkoordinater. Fra hovedvinduet åpner
  redigeringsprogrammet seg for dette på stedet. Også ved henvisningen om
  et avvikende sidetall fører knappen nå dit – til den første siden som
  bare finnes i ett av de to dokumentene.
- Den som bytter forhåndsvisningen til «Side ved side i to kolonner»,
  får nå automatisk et vindu de to banene passer inn i – tidligere klemte
  de seg inn i den gamle bredden, inntil man selv dro. Utvidet blir det
  høyst til skjermkanten og aldri smalnet tilbake; en selvvalgt bredde
  blir stående.
- Etter- og fornavn i separate tabellkolonner (f.eks. «Nachname |
  Vorname» i en påmeldingsbekreftelse eller en CSV-eksport) forble åpne –
  hver celle for seg så for gjenkjenningen ut som et vilkårlig ord uten
  navnesammenheng. Gjenkjennes nå.
- Navn og fornavn på baksiden av et EU-kortførerkort forble åpne – de
  står der bak de offisielle feltkodene «1.» og «2.» i stedet for bak et
  tysk ord, og nettopp det lot dem forbli ugjenkjent. Gjenkjennes nå, når
  førerkortnummeret (feltkode «5.») står ved siden av.
- Fornavnet til kjøretøyeieren på registreringsbeviset forble åpent – det
  står bak den offisielle feltkoden «C.1.2» i stedet for bak et tysk ord
  som «Vorname», og nettopp det lot det forbli ugjenkjent. Etternavn og
  fornavn under feltkodene C.1, C.1.1 og C.1.2 gjenkjennes nå.
- Den første linjen i det maskinlesbare området (MRZ) på pass eller
  ID-kort forble åpen – den bærer navnet i formatet
  «ETTERNAVN<<FORNAVN» og gikk også med den nye MRZ-gjenkjenneren
  gjennom kontrollsifferlinjen. Et funn teller nå bare hvis det
  rett ved siden av står en kontrollsiffer-gyldig andre MRZ-linje –
  selve navnelinjen har ikke noe eget kontrollsiffer.
- Den andre linjen i det maskinlesbare området (MRZ) på pass eller
  ID-kort forble fullstendig ugjenkjent – den inneholder passnummer,
  fødsels- og utløpsdato i klartekst, men traff ingen eksisterende
  gjenkjenner. En egen gjenkjenner kontrollerer nå de fire
  ICAO-kontrollsifrene.
- Et kjøretøyskilt uten noe mellomrom til merkingen forble åpent –
  «KennzeichenM-AB1234» eller «KFZ-KennzeichenM-AB1234» ble overhodet
  ikke gjenkjent, fordi den underliggende skiltkontrollen forutsetter et
  ikke-ordtegn foran skiltet. Rammet kjøretøyangivelser uten mellomrom
  mellom feltord og skilt.
- Et telefonnummer uten noe mellomrom til merkingen forble åpent –
  «Handynummer0171/2345678» eller «Tel0171/2345678» ble overhodet ikke
  gjenkjent, fordi den underliggende telefonnummerkontrollen forutsetter
  et mellomrom eller skilletegn foran nummeret. Rammet kontaktangivelser
  uten mellomrom mellom feltord og nummer.
- Et fødenavn bak forkortelsen «geb.» ble overhodet ikke gjenkjent –
  «Julia Bergmann (geb. Weber)» fant bare «Julia Bergmann», punktumet i
  «geb.» lot språkmodellen hoppe helt over det følgende navnet. Rammet
  personangivelser med fødenavn i parentes eller etter komma.
- Fornavnet foran et kallenavn i anførselstegn forble åpent, når
  tiltaleform og tittel sto sammen foran – «Herr Dr. Klaus "KP" Peters»
  ga bare «Peters», «Klaus» ble stående leselig. Rammet signaturer og
  kontaktangivelser med tittel og kallenavn.
- Et navn bak punktumfri kortform «zH»/«zHd» (til hånde) ble overhodet
  ikke gjenkjent – i motsetning til ved «z.Hd.» med punktum rev den
  manglende setningsstrukturen navnet med bort. Rammet adresser uten
  punktum i forkortelsen.
- Et navn bak «p.A.» (per adresse) ble overhodet ikke gjenkjent –
  punktumet i forkortelsen lot språkmodellen hoppe helt over
  navnegjenkjenningen. Rammet fakturaer og søknader med
  samleadresse.
- Et navn bak punktumfritt klistret «i.A.»/«i.V.» (på vegne av/i
  representasjon) ble overhodet ikke gjenkjent, for eksempel «i.A.Robert
  Lang» uten mellomrom – samme setningsbygningsfeil som ved «p.A.».
  Rammet signaturlinjer og e-postsignaturer ved representasjonssaker.
- En ren fremmøteliste med punktmerke uten videre angivelse («- Max
  Mustermann», også med punktum på linjeslutten) mistet alle navn til
  den samme bremsen som egentlig bare skal beskytte saksoppramsinger som
  «- Farbe: Blau». Slike lister gjenkjennes nå.
- Filer som ikke lenger lot seg rense, lar seg rense igjen. En verdi som
  allerede var erstattet av gjenkjenningen, kunne gjenfinnes i sitt eget,
  allerede erstattede merke som «[SVNR1]» – sluttprøven forkastet da en
  feilfritt renset fil. I tillegg fjernes nå en telefonhenvisning i en
  CSV-tabell med, og den som begrenser søket til enkelte typer, får dem
  nå likt overalt i dokumentet – også i alternativteksten til et bilde,
  en Excel-overskriftslinje, en nedtrekksliste eller et HTML-attributt.
- Et navn bak e-posthodefeltet «To:» (eller «To» uten kolon) ble ikke
  gjenkjent, fordi en fremmed språkmodell leste hele linjen som ett
  eneste uanselig treff og svelget navnet i den fullstendig – i motsetning
  til ved «Cc:», «Bcc:» eller «From:» foran samme navn. Et navn bak «To»
  finnes nå pålitelig.
- Bryllupsdatoen lot seg ikke behandles som dato i egne regler
  («forskyv» ble avvist med «finnes bare for datoangivelser»), manglet i
  gruppetilordningen for funntyper – slik at den ikke lot seg slås av via
  merkene «Hva som søkes» – og fikk full ordlyd som plassholder i stedet
  for en kort forkortelse som ved dødsdatoen. Nå ettertrukket for alle
  seks forkortelses-/merketabeller.
- En i forhåndsvisningen bevisst fravalgt verdi kunne likevel sladdes et
  annet sted: Fravalgte man f.eks. en e-postadresse, ble riktignok selve
  adressen stående, men den lokale delen uten domene ble erstattet, så
  snart den samsvarte med det utledede brukernavnet til en videre valgt
  person («anna.musterfrau@beispiel.de» ved siden av «Anna Musterfrau»).
  En fravalgt ordlyd forblir nå tabu i hele dokumentet, uavhengig av
  hvilken funntype den stammer fra.
- En fødselsdato forble ugjenkjent, når en familiebok eller et
  personstatusutdrag førte den under en felles overskriftslinje sammen
  med fødestedet («Geburtsdatum, Geburtsort: 19.11.1982, Steyr») – det
  andre feltordet mellom «Geburtsdatum» og datoen lot gjenkjenningen
  falle helt gjennom hittil.
- Et allerede gjenkjent telefonnummer forble leselig i sin forkortede
  bekreftelsesform, når det et annet sted i samme dokument bare ble
  nevnt med de siste fire sifrene («nås på nummeret ...5678»,
  «tilbakeringing på ...5678») – samme byggeform som ved IBAN og
  kredittkort.
- Et allerede gjenkjent kredittkortnummer forble leselig i sin
  forkortede bekreftelsesform, når det et annet sted i samme dokument
  bare ble nevnt med de siste fire sifrene («Kredittkortet ditt slutter
  på ...0366») – samme byggeform som er vanlig i betalingsbekreftelser
  som ved IBAN.
- En allerede gjenkjent IBAN forble leselig i sin forkortede
  bekreftelsesform, når den et annet sted i samme dokument bare ble
  nevnt med de siste fire sifrene («IBAN-en slutter på ...3201») – en
  byggeform som er vanlig i bekreftelses-e-poster.
- En taler i en chat- eller møteprotokoll forble ugjenkjent, når en
  tiltaleform sto foran navnet («Herr Bauer: …», «Frau Koch: …») – og
  rammet dermed ofte også neste talerlinje i samme protokoll med, fordi
  for få gjenkjente linjer ble igjen til å i det hele tatt vurdere
  dokumentet som en protokoll.
- En fødselsdato forble ugjenkjent, når feltordet «geboren» sto BAK
  datoen i stedet for foran («Barnet ble født den 14.01.2026») – slik
  formulerer for eksempel en foreldrepermisjons- eller
  fødselspermisjonsattest barnets fødselsdato. Tidligere mønstre
  forutsatte alltid feltordet foran datoen.
- En skjemamerking med reaksjons- eller hakemerke rett foran («Ansprechpartner
  😊:», «Kontaktperson ✓:») ble ikke lenger gjenkjent som merking, og
  navnet under eller bak forble derved delvis bare ufullstendig funnet
  (f.eks. bare etternavnet ved «Mayer Roman»).
- Samme hull rammet også særlig beskyttelsesverdige angivelser etter art.
  9 GDPR (religion, helse, fagforening): Et reaksjonstegn rett foran
  skilletegnet eller linjeskiftet («Konfession 😊: römisch-katholisch»)
  lot merkingen falle helt gjennom, og angivelsen forble fullstendig
  ugjenkjent.
- En adresse med bindestrek-dobbeltnavn i stedet (f.eks. «79761
  Waldshut-Tiengen», «78050 Villingen-Schwenningen») mistet postnummeret
  fullstendig, selv om selve stedet ble gjenkjent og sladdet – på et
  kjøretøydokument eller følgebrev forble postnummeret dermed stående
  leselig.
- En tabellkolonne uten kolonneavstand (ekte PDF-tekstutdrag) kunne under
  en navnekolonne feilaktig sladde også to tilfeldig ved siden av
  hverandre stående stor-forbokstavsord som person, for eksempel to
  stedsnavn i en datalinje; dette er nå bare tilfellet når ikke et annet
  funn på samme sted allerede gjenkjenner noe annet.
- Samme navnekolonne sladdet i samme linjeform også to for språkmodellen
  ukjente saksord (f.eks. «Frontend Backend», «Turbo Modul») feilaktig
  som person, fordi ikke noe annet funn utløste bremsen der; den krever
  nå i tillegg at minst ett av de to ordene selv leses som egennavn av
  språkmodellen.
- Det tyske pensjonsforsikringsnummeret ble i sin offisielle fulle
  gruppering (f.eks. «65 170839 J 08 8» – slik det står på
  trygdebeviset og lønnsslippen) ikke gjenkjent og ble stående i
  originalen; gjenkjent ble bare den kompakte skrivemåten og formen bare
  gruppert til bokstaven.
- Skatteidentifikasjonsnummeret ble i sin offisielle skrivemåte
  (gruppering 2-3-3-3, f.eks. «48 836 075 988» – slik det står på
  hvert ekte skattevedtak og hver melding fra Bundeszentralamt für
  Steuern) overhodet ikke gjenkjent og ble stående i originalen; bare den
  sjeldnere grupperingen 3-3-3-2 var dekket.
- Skattenummeret fra Nordrhein-Westfalen (f.eks. «221/5147/0815», med
  firesifret i stedet for tresifret andre gruppe) ble i skattevedtak
  overhodet ikke gjenkjent og ble stående i originalen – hvert annet
  delstat var allerede dekket.
- I arbeidsavtaler ble et navn bak merkingen «Arbeitgeber:» fullstendig
  oversett, så snart etternavnet samtidig var et vanlig ord (f.eks.
  «Bauer Anna») – «Arbeitgeber» står både som navne- og som firmamerking
  i listen, og firmatilordningen overskrev navnetilordningen.
- I et leieavtalehode med merkingene «Vermieter:»/«Mieter:» ble et
  etternavn som samtidig er et vanlig ord (f.eks. «Bauer»), oversett –
  bare fornavnet forble gjenkjent. Nummererte leietakere («Mieter 1:»,
  «Mieter 2:») var i tillegg berørt, også ved navn uten denne
  flertydigheten.
- I en rettsprotokoll med merkingene «Zeuge:»/«Kläger:»/«Beklagter:»
  (også med telling, «Zeuge 1:», «Zeuge 2:») ble et etternavn som
  samtidig er et vanlig ord (f.eks. «Bauer»), likeledes oversett – bare
  fornavnet forble gjenkjent.
- Ved arveattest, fullmakt, purringssak og kjøpeavtale ble et etternavn
  som samtidig er et vanlig ord (f.eks. «Bauer»), oversett bak merkinger
  som «Erblasser:», «Erbe:», «Vollmachtgeber:», «Bevollmächtigte:r»,
  «Antragsgegner:», «Schuldner:», «Gläubiger:», «Käufer:», «Verkäufer:»,
  «Vermächtnisnehmer:» eller «Testamentsvollstrecker:» – dels forble
  bare fornavnet gjenkjent, dels falt hele navnet bort.
- Ved en flerparts-liste foran rubrum-skilletegnet «./.» (f.eks. «Sand,
  Werner und Huber, Anna ./. Wechsler, Martina») forble den første
  parten umaskert – bare parten som direkte grenset til «./.» ble
  gjenkjent.
- I rubrum-skilletegnet «./.» (f.eks. «Sand./.Wechsler») ble navnet etter
  tegnet fullstendig oversett, når det ikke sto noe mellomrom der – bare
  med mellomrom foran og bak traff gjenkjenningen.
- Etternavnet «Wahr» ble fullstendig oversett, når det sto alene (f.eks.
  «Frau Wahr bearbeitet Ihren Vorgang.») – ordet står tilfeldigvis også i
  listen over vanlige tyske ord, som ellers filtrerer navnefunn fra
  setninger som «Das ist wahr.».
- Etternavn som «Los», «Weit», «Rund» eller «Hoch» ble fullstendig
  oversett, når de sto alene (f.eks. «Herr Hoch übernahm die Leitung.»)
  – alle fire ordene står tilfeldigvis også i listen over vanlige tyske
  ord, som ellers filtrerer navnefunn fra setninger som «Rund
  einhundert Gäste kamen zur Feier.».
- Etternavn som «Ganz» eller «Recht» ble fullstendig oversett, når de sto
  alene (f.eks. «Herr Ganz unterschrieb den Vertrag.») – begge ordene
  står tilfeldigvis også i listen over vanlige tyske ord, som ellers
  filtrerer navnefunn fra setninger som «Ganz genau, das stimmt.».
- Et skjemafelt med en stjerne eller et hevet fotnotetall bak merkingen
  (f.eks. «Konfession*: römisch-katholisch» eller «Religionszugehörigkeit¹:
  evangelisch») ble ikke gjenkjent og ble stående i klartekst – bare
  formen uten dette tegnet traff.
- Samme felt forble fortsatt i klartekst, når det sto to fotnotetegn
  bak merkingen (f.eks. «Konfession**: römisch-katholisch» eller
  «Gewerkschaft¹²: ver.di»).
- Et versjonsnummer som «Softwareversion 4.2.1.19» eller «Firmware Build
  2.0.4.11» sladdes ikke lenger feilaktig som IP-adresse. Det samme
  gjelder nå for bilags- og saksnumre som «Rechnungsnummer
  10.20.30.40» eller «Bestellnummer 7.8.9.10».
- To IBAN-er rett under hverandre (f.eks. egen og en utenlandsk
  forretningsforbindelses i fakturahodet) ble ikke lenger begge
  gjenkjent – den andre ble stående ubemerket.
- En merket IBAN rev av og til med seg det følgende ordet i setningen
  («Bankverbindung AT61 … wird belastet» ble sladdet helt inn til
  «wird»), så snart det følgende ordet hadde liten forbokstav –
  klartekstresten ved siden av forble urørt.
- Liechtensteinske adresser gjenkjennes nå («FL-9490 Vaduz»), slik som
  tidligere allerede tyske, østerrikske og sveitsiske.
- Reisepass- og passnummer gjenkjennes og fjernes nå bak merkingen sin
  (f.eks. «Reisepassnummer: C01X00T471»).
- Oppholdstillatelse- og bostedsattestnummer gjenkjennes og fjernes nå
  bak merkingen sin.
- Et identifikasjonsnummer bak merkingen sin gjenkjennes nå også når en
  tankestrek skiller i stedet for kolon (f.eks. «Kundennummer –
  K903944»).
- En som «IBAN» eller «Kontonummer» merket bankforbindelse gjenkjennes
  nå også når en tankestrek skiller i stedet for kolon.
- Et navn bak en merking som «Kontaktperson (Vertrieb)» eller
  «Sachbearbeiter/in» gjenkjennes nå også med parentestillegg eller
  kjønnsnøytral skråstrekendelse.
- Samme stjerne-kjønnsform («Sachbearbeiter*in») gjenkjennes nå
  likeledes.
- Et navn bak en merking gjenkjennes nå også når et likhetstegn skiller i
  stedet for kolon (f.eks. «Ansprechpartner = Mayer Roman» eller
  «Kontaktperson=Mayer Roman»), som vanlig i konfigurasjonsfiler eller
  CSV-overskrifter. Står flere slike merking-verdi-par atskilt av
  semikolon på én linje, gjenkjennes nå bare den første verdien i stedet
  for resten av linjen.
- Et GPS-koordinatpar bak ordet «Koordinaten» gjenkjennes nå pålitelig
  (f.eks. «Koordinaten: 48.2082, 16.3738») – ordet bar feil bøyningsform i
  den interne katalogen.
- Et identifikasjonsnummer bak merkingen sin (kundenummer,
  kontraktnummer, saksnummer, ID-kortnummer og rundt hundre andre
  feltord) ble ikke lenger gjenkjent, så snart merkingen ikke sto
  nøyaktig i den lagrede store-/liten-bokstav-skrivingen –
  «kundennummer:» i en e-post eller «KUNDENNUMMER:» i et skjemahode
  forble urørt.
### Nytt

- **Realistiske erstatningsverdier er nå et bevisst innsatt eksempel i
  stedet for en standard.** Unntakstabellen i fanen «Plassholder»
  begynner tom. En ny knapp fører der ved ønske inn troverdige falske
  verdier for navn, sted, adresse, organisasjon, e-post, telefon,
  internnummer og IBAN. Den lar pengebeløp uttrykkelig forbli ved den
  nummererte plassholderen; strategien «dikt opp» forblir fortsatt
  manuelt valgbar for enkelttyper.
- **KI-nivået kan bruke grafikkortet.** Under Windows kan det til dette
  lastes ned en knapt 17 MB stor tilleggspakke; deretter regner KI-nivået
  betydelig raskere på et egnet grafikkort enn på prosessoren. Den som
  ikke har noe eller ikke laster ned noe, fortsetter uendret å arbeide –
  bare tregere. På macOS er akselerasjonen uansett allerede innebygd.
- **To nye varsler via oppgavelinjeikonet**: når forhåndsvisningen før
  erstatning er klar til gjennomsyn, og når en behandling er ferdig. Begge
  er forhåndsinnstilt på og kan slås av enkeltvis under
  *Innstillinger → Program → Varsler*.

### Endret

- **ID-kort- og førerkortnummer gjenkjennes nå**, når merkingen deres
  står foran («Personalausweisnummer: …», «Führerscheinnummer: …») –
  tidligere falt begge gjennom hver gjenkjenning.
- **Maskuro følger nå Windows' kontrastdesign.** Den som har slått på ett
  under *Innstillinger → Tilgjengelighet → Kontrastdesign*, fikk det
  tidligere overalt unntatt her: Maskuro satte deretter sine egne farger.
  Nå forblir det ved systemets design – vindu, lister, ablagessone,
  protokoll og statusfarger. Den fargede kontrollampen i forhåndsvisning
  og etterredigeringsvindu bortfaller der bevisst; det den sier, står
  siden uansett som tegn og som ord ved siden av.
- **Kontrollbehovet står ikke lenger bare i fargen.** Rødt, oransje og
  grønt er nesten like lyse – den som har rød-grønn-svakhet, så i
  forhåndsvisning og trefffelt en liste uten forskjeller, og det gjelder
  omtrent hver tolvte mann. Hver linje bærer nå i tillegg et tegn som
  skiller seg i formen: ▲ kontroller først, ● kontroller, ○ godt belagt,
  ◆ uten vurdering. Korthenvisningen nevner det med ord, og en
  skjermleser leser det opp.
- **Alt åpner igjen menyene som vanlig.** Menylinjen hadde ingen
  hurtigtaster: Den som ikke bruker musen, måtte piltaste seg gjennom
  hver meny. Nå bærer hver oppføring en understreket bokstav – Alt+D for
  «Datei», derfra B for «Beenden» –, og det på alle grensesnittspråk.
- **Betjeningselementer sier igjen til en skjermleser hva de er til
  for.** I etterredigeringsvinduet, i regelvinduet, i protokollen, i
  ordlistene, i hjelpen, i søkelinjen og i fem ytterligere vinduer ble
  lister, søkefelt, nedtrekkslister og glidebrytere tidligere bare
  annonsert som «tre» eller «kombinasjonsfelt» – uten om hva. Rundt førti
  steder bærer nå et navn. (Hovedvinduet var i orden siden august;
  vinduene som kom til etterpå, hadde aldri gjennomgått trinnet.)
- **Den som betjener med tastaturet, ser overalt hvor han står.** Ved
  kontrollbehov-glidebryterne, ved avkrysningsboksen og ved «aldri
  igjen»-knappen i forhåndsvisningen, ved typeoverskriftene der, ved
  sidefeltet i etterredigeringsvinduet og ved sidelinjen i innstillingene
  manglet rammen systemet ellers legger rundt det tilhoppede
  betjeningselementet.
- **Større systemskrift kutter ikke lenger noe av.** Den som under
  *Tilgjengelighet → Tekststørrelse* stiller over 175 %, mistet tidligere
  slutten på merkingene i mappeovervåkingen og i
  hurtigtastfeltene. Kapittellisten i hjelpen kuttet lange
  kapittelnavn allerede ved vanlig skrift; den bryter dem nå om og nevner
  det fulle navnet i korthenvisningen.

- **Gjenkjenningen er blitt betydelig raskere.** Gjenkjenneren for merkede
  identifikasjonsnumre («Kundennummer: K903944») kontrollerte tidligere
  per tekstavsnitt over 1200 enkeltmønstre etter hverandre – dette var
  den største enkeltposten i gjenkjenningstiden, ved hvert avsnitt og
  hver tabellcelle. Nå er det ett eneste mønster med samme resultat: På
  målekorpuset endres ikke ett eneste treff, grunnivået per tekstavsnitt
  blir omtrent tre til fire ganger så raskt.
- **Vinduet vises straks ved oppstart.** Tidligere lastet hovedvinduet de
  fullstendige språkverktøyene før det i det hele tatt viste seg – rundt
  fire sekunder blindtid ved hver oppstart. Modellene lastes nå som
  planlagt i bakgrunnen mens vinduet allerede står; rens-knappen blir som
  før først fri når alt er klart. Også rene opplysningskall fra
  kommandolinjen (for eksempel `--version`) svarer nå straks i stedet for
  etter flere sekunder.
- **Bilder leses nå bare én gang ved automatisk språkgjenkjenning.**
  Tidligere gikk tekstgjenkjenningen ved standarden «Språk: automatisk»
  to ganger over samme bilde – én gang for språkgjetningen, én gang for
  selve kontrollen. Bildefiler, utklippstavlebilder og tekstvinduet er
  dermed omtrent dobbelt så raskt ferdige; ved avslått tekstgjenkjenning
  bortfaller den tidligere ubemerket likevel kjørende lesningen helt.
- **Lagrede nettsider og e-poster renses raskere.** Verdiene i
  HTML-attributter, kommentarer og innebygde datablokker ble tidligere
  gjenkjent enkeltvis – en kommuneside med hundrevis av merkinger stilte
  hundrevis av enkeltspørsmål til gjenkjenningen. Nå samles de og
  gjenkjennes bare én gang per forskjellig verdi; på målekorpuset endres
  ikke ett treff, .html og .eml er rundt en tredjedel raskere.
- **Også biopplagringene til tabeller og presentasjoner gjenkjennes
  samlet.** Alternativtekster, formeltekststrenger, diagrammerkinger,
  kommentarer, pivot-mellomlagre og dokumentegenskaper stilte per verdi
  et eget gjenkjenningsspørsmål – en arbeidsbok med tusenvis av
  pivot-linjer tilsvarende tusenvis. Nå kjører en samlet kjøring over de
  forskjellige verdiene, og etterjusteringens fulle gjennomgang på slutten
  kjører bare når det faktisk har kommet nye verdier til siden den
  løpende teksten. På målekorpuset endres ikke ett treff.
- **Skjemarike PDF-er renses raskere.** Felt, notater, bokmerker og
  lenker gjentar samme verdier massevis («Off» ved hvert avkrysningsfelt,
  samme forfatter ved hver anmerkning) – hver av dem stilte tidligere
  sitt eget gjenkjenningsspørsmål. Per kjøring gjenkjennes en verdi nå
  bare én gang; erstatning og konsistens-etterjustering kjører uendret
  per sted.
- **Store tabellfiler (.csv/.tsv) renses betydelig raskere.** De fire
  tabelletterjusteringene delte tidligere hver for seg samme fil tegnvis
  opp i celler (ved 40 MB rundt 30 s ekstraarbeid); nå kjører oppdelingen
  én gang. Kolonneoverskrift-gjenkjenningen (fødselsdato- og
  personalnummerkolonner) stiller i stedet for ett spørsmål per celle ett
  samlet – ved identiske treff rundt tjue ganger raskere. Og
  navnekolonne-sammenfatningen av store personallister er ikke lenger
  kvadratisk i linjeantallet.
- **Nøkkeltall-klaffen fryser ikke lenger vinduet.** Utfoldingen av
  nøkkeltallene leste ved mange store filer teksten deres først sammen og
  lot vinduet stå i flere sekunder. Beregningen kjører nå i bakgrunnen;
  klaffen åpner straks og etterfører tallene.
- **Søkelinjerapporten fryser ikke lenger vinduet.** Etter gjennomsøking
  av mange tusen filer ble den felles mappen beregnet på nytt for hver
  berørte fil; ved store kjøringer sto vinduet dermed tosifrede sekunder.
  Rapporten vises nå straks.
- **PDF-er med tekstgjenkjenning kontrolleres raskere.** Hver side ble
  ved motlesning unødvendig omgjort til PNG-format to ganger; nå
  videreformidles det allerede foreliggende bildet. Resultatet er
  uendret, bare kontrollen går raskere.
- **Forløpsanmerkninger på store bilder rykker ikke lenger.** Ved
  etterjustering på håndtakene til en anmerkning med overgang ble
  overgangen tidligere beregnet på nytt punkt for punkt – på et stort
  skjermbilde et synlig hakk. Resultatet er det samme, bare uten pausen.

### Rettet

- **Krysset for å fjerne en fil fra listen er igjen et enkelt X.** Det nye
  redigeringsverktøyet «Fjern» hadde ved en feil brukt samme
  symbolidentifikasjon og dermed også vist sitt røde kryss med stiplet
  tekstlinje i hver fillinje. Begge handlingene har nå separate
  symbolnavn og beholder sin respektive passende fremstilling.
- **Flerdelte angivelser gjenkjennes i PDF-er nå også over et synlig
  linjeskift.** Maskuro leser den geometrisk genererte sideteksten i
  tillegg som en offsetlik løpende tekstvisning. Dette gjelder for alle
  grunn- og høynivågjenkjennere samt egne søkemønstre, ikke bare for det
  først synlige tilfellet «Diabetes mellitus Typ 2». Tomme linjer og
  gjenkjente tabell- eller avsnittsgrenser forblir harde grenser;
  funnsteder passer fortsatt eksakt til ordene som skal sladdes.
- **Eksempelet ved «Pseudonymiser» motsa seg selv.** Setningen lovet
  «samme person, samme nummer» og viste deretter to forskjellige numre –
  nettopp bildet som er riktig ved «Anonymiser». Begge eksemplene stemmer
  nå overens med sin egen setning.
- **En nylig satt plassholder kunne ved «Hent tilbake original» bli
  stående som overlagret bokstavgrøt i stedet for å forsvinne.** En
  ensfarget innsatt plassholder skrev tidligere en egen utdatakommando
  per tegn, hvorav bare det første bar en egen tekstmatrise – ved neste
  redigering av samme sted (for eksempel «hent tilbake» rett etterpå)
  fikk de øvrige tegnkommandoene på rundgang tegnindeksene til det
  første tildelt, og plassholderen falt fra hverandre i to overlappende
  posisjoner. En ensfarget plassholder får nå én eneste utdatakommando
  for hele teksten sin.

- **Sto samme sladdede eller fjernede verdi under to linjer i
  etterredigeringsvinduet og ble begge markert for tilbakehenting, talte
  den andre linjen feilaktig som «ikke entydig» – selv om verdien for
  lengst var hentet tilbake.** Begge linjene gjelder nå som utført.

- **Navnet etter «Reply-To:» finnes nå.** I et e-posthodefelt som
  «Reply-To: Huber» forble navnet tidligere helt ugjenkjent –
  språkmodellen leste «Reply-To:» som en egen, feil person og oversså
  det ekte navnet bak.

- **E-posthodeordene «Reply» og «Fwd» sladdes ikke lenger selv som navn.**
  I en emnelinje som «Fwd: Angebot von Huber» ble tidligere i tillegg til
  navnet også selve hodeordet gjenkjent og sladdet som person.

- **«Arbeitgeber: Siemens AG» gjenkjennes nå som firma, ikke lenger som
  person.** Bar firmaverdien bak merkingen «Arbeitgeber» en rettsform som
  GmbH, AG eller KG, forble den til tross for påslått
  organisasjonsgjenkjenning et personfunn – bare det smalere tilfellet
  uten rettsform («Wollmuth und Partner») ble tidligere gjenkjent som
  firma.

- **En allerede gjenkjent adresse blir ikke lenger stående et annet
  sted.** Ble en gateadresse gjenkjent og erstattet ett sted, kunne samme
  adresse bli stående et annet sted – for eksempel i en vanskelig lesbar
  bunntekst i et innskannet dokument, der den automatiske
  tekstgjenkjenningen leste den forvrengt. Adresser fjernes nå, som navn
  og firmaer lenge har gjort, konsekvent gjennom hele dokumentet.

- **E-poster med flere mottakere ble stille skadet ved rensing.** En
  `.msg`-melding med to eller flere mottakere mistet ved lagring deler av
  sin indre struktur, slik at det rensede resultatet var ufullstendig.
  Årsaken var en forveksling av likt navngitte indre bestanddeler som
  forekommer ved hver mottaker. Slike meldinger bygges nå fullstendig
  opp igjen.

- **To av de medfølgende testdokumentene lot seg ikke åpne i Word og
  PowerPoint.** Den som lastet ned målekorpuset, fikk ved
  `format_dokument.docx» «Feil ved åpning av filen i Word» og ved
  `format_praesentation.pptx» «Filen er skadet». Begge filene var
  allerede feilaktige før Maskuro rørte dem – den rensede versjonen
  videreførte bare feilen. LibreOffice åpnet begge uten problemer, derfor
  hadde ingen lagt merke til det.

- **En egen KI på internett tiltales nå kryptert.** Den som ved den egne
  KI-en fører inn en ekstern adresse uten «https://» (slik den ofte står
  på IT-avdelingens lapp), nådde den tidligere via en ukryptert
  forbindelse – den usladdede teksten gikk ut i klartekst. Slike adresser
  tiltales nå via «https://»; en server i eget nettverk forblir uendret
  tilgjengelig. Følger serveren en omdirigering til en annen maskin,
  vandrer ikke lenger tilgangsnøkkelen med.

- **Også et skadet bilde mister nå sine skjulte metadata.** Lot et
  innebygd bilde seg ikke lenger åpne fullstendig (for eksempel et
  avkuttet foto), beholdt det tidligere EXIF- og GPS-dataene sine –
  opptakssted og fotografnavn forble usynlige i resultatet. Slike bilder
  befris nå for disse dataene også når de overhodet ikke lar seg vise
  lenger.

- **En innebygd fil som ikke lot seg rense, meldes nå i stedet for å bli
  gitt med stilltiende.** Lå det i en presentasjon eller arbeidsbok et
  innebygd objekt som var for dypt nøstet eller ikke lot seg åpne, forble
  det tidligere uendret i resultatet, uten henvisning – filen gjaldt som
  renset. Slike tilfeller står nå i advarselen «kunne IKKE kontrolleres»,
  akkurat som et innebygd gammelt format.

- **Mørke lister er igjen gjennomgående mørke og lesbare.** På macOS
  vekslet fillister mellom nesten svarte og lysegrå linjer; ved
  etterredigering så dermed samme grønne, oransje eller røde
  kontrollverdi forskjellig ut alt etter linje. Vindu, lister, skrift,
  plassholder og utvalg kommer nå fra en felles lys-/mørkpalett. Den
  fargekodede trefflisten legger dessuten ikke lenger sebrastriper under
  fargene sine.

- **Yrkesangivelser med «als» ble feilaktig sladdet som navn.** En
  setning som «Als Koch ist er seit vier Jahren bei uns tätig.» mistet
  yrket, ikke bare et navn – «als» innleder en rolleangivelse akkurat som
  «der» eller «die». Ekte etternavn på samme sted (f.eks. med en
  tiltaleform foran) forblir uberørt.

- **En tabelloverskrift kunne trekke et posisjonsnummer inn i et
  pengebeløp** (bare ved påslått alternativ «Fjern også pengebeløp»).
  Endte en linje på en valuta («… Einzelpreis EUR») og begynte den neste
  med et tall, ble dette feilaktig til et beløp over linjeskiftet. Skilletegnet
  mellom valuta og tall forblir nå på samme linje.

- **En kort forkortelse med store bokstaver kunne svelge en hel
  setningsdel, eller henge seg foran et riktig gjenkjent navn.** Sto det
  på en linje et tobokstavs stor-ord som «DI», «AG» eller «KG» –
  hverdagslige forkortelser, ingen navn –, ble hele linjen søkt gjennom
  prøvevis med liten forbokstav, og forkortelsen dro av og til
  naboliggende ord (også verb) med inn i ett eneste antatt navn. Først
  fra tre bokstaver utløser et stort ord nå denne andre kontrollen. Ved
  litt lengre forkortelser som «CEO» eller «USB» gjenstod en andre feil:
  Det allerede riktig funnede navnet («Schneider») fikk den foranstilte
  forkortelsen dratt med inn i resultatet som forstavelse
  («CEO Schneider»). Forkortelsen forblir nå utenfor.

- **En fødselsdato uten mellomrom bak forble stående.** Sto det bak
  «geb.» ikke noe mellomrom foran datoen – som vanlig i tett satte
  skjemaer («geb.14.03.1988») –, gjenkjente Maskuro ikke feltet og lot
  datoen stå urørt. Vanlige kortformer som «Geburtsdat.» eller
  «Geb.-Dat.» gjenkjennes nå også.

- **En IBAN med skråstreker som skilletegn forble stående.** Som ved
  telefonnumre («0664/1234567») skriver enkelte maler også IBAN-en i
  blokker med skråstrek («AT48/3200/0000/1234/5864») i stedet for med
  mellomrom eller bindestrek. Denne skrivemåten gjenkjennes nå også.

- **Et østerriksk trygdenummer med bindestrek, punktum eller skråstrek
  forble stående eller var feilmerket.** Mellom de to talblokkene var
  tidligere bare et mellomrom forutsett; skrivemåter som «1237-010180»,
  «1237.010180» eller «1237/010180» ble ikke gjenkjent (eller i
  skråstrek-tilfellet under feil type). Kontrollsifferet bekrefter
  fortsatt hvert treff, uavhengig av skilletegn.

- **Et navn bak «c/o» i en adresse ble overhodet ikke fjernet.** «c/o Max
  Mustermann, Hauptstraße 5, 1010 Wien» sladdet gate og sted, men lot
  navnet bak stå fullstendig. Navnet gjenkjennes nå; «c/o» selv forblir
  synlig som en adressehenvisning.

- **Et med punktum gruppert kredittkortnummer forble stående.**
  Skrivemåter som «4111.1111.1111.1111» ble ikke gjenkjent; med
  mellomrom eller bindestrek atskilte numre var ikke berørt av dette.
  Kontrollsummen bekrefter fortsatt hvert treff.

- **Et med bindestreker gruppert skatteidentifikasjonsnummer forble
  stående, et østerriksk MVA-nummer med bindestrek eller punktum
  likeledes.** Mellomrom, skråstrek og punktum var allerede forutsett ved
  skatte-ID-en, bindestreken manglet; ved MVA-nummeret («ATU12345678»)
  manglet bindestrek og punktum etter prefikset. Kontrollsifferet til
  skatte-ID-en bekrefter fortsatt hvert treff.

- **En feltverdi i anførselstegn forble stående, for eksempel i en
  JSON-lignende linje som «vorname»: «Max».** Gjenkjenningen via en
  feltmerking («Vorname: …») forutsatte tidligere at verken merkingen
  eller selve verdien sto i anførselstegn. Slike linjer gjenkjennes nå
  også – likeledes feltmerkinger med et foranstilt YAML-listepunkt
  («- Vorname: Max») eller en tabulator i stedet for et mellomrom foran
  kolonet.

- **E-posthodeordet «Sent» ble selv sladdet som et navn.** I et hodefelt
  som «Sent: Huber» rammet det tidligere både «Sent» og selve navnet;
  beslektede hodeord som «Subject» eller «Betreff» var alltid urørt av
  dette. «Sent» blir nå også stående.

- Et navn bak hodefeltene «Errors-To:» eller «Resent-From:» forble
  uoppdaget, når en slik linje sto kopiert i klartekst (for eksempel en
  videresendt melding eller en hendelsesrapport) – i motsetning til ved
  «Reply-To:» eller «Return-Path:» falt navnet her helt bort i stedet
  for bare å være unøyaktig avgrenset. Det finnes nå.
- Én og samme fil ga ved to rensinger av og til et forskjellig resultat:
  Traff to gjenkjenninger nøyaktig samme sted med samme lengde og samme
  sikkerhet (f.eks. «Sozialversicherungsnummer 1237/010180» som AT_SVNR
  eller som generelt identifikasjonsnummer), var det tilfeldig hvem som
  vant – verdien ble fjernet i begge tilfeller, bare
  plassholdermerkingen skiftet. Uavgjort avgjøres nå alltid likt.
- En funksjonsbetegnelse rett foran et substantiv (f.eks. «Behandelnder
  Arzt: Dr. …» eller «Zuständiger Sachbearbeiter ist …») ble av og til
  feilaktig sladdet med, som om den selv var et navn. Ekte etternavn ved
  siden av forblir urørt av dette.
- Et ekte etternavn som tilfeldigvis ser ut som et adjektiv (f.eks.
  «Schöne», «Lange», «Junge») og står rett foran et ytterligere
  substantiv (for eksempel «Kontaktperson: Schöne Assistentin»), forble
  siden forrige rettelse usladdet i teksten – en datalekkasje. Bare en
  snevert avgrenset liste over ekte funksjonsbetegnelser (f.eks.
  «Behandelnder», «Zuständiger») behandles nå i denne byggeformen som
  ikke-navn.
- Et alenestående etternavn på slutten av et flerlinjes navnetreff, som
  tilfeldigvis ser ut som et adjektiv (f.eks. «Schwarz», «Kurz», «Alt»,
  «Frisch», «Gut», «Reich»), forble ugjenkjent foran et umiddelbart
  følgende kolon – rensingen forvekslet det med en feltmerking som
  «Telefon:». En lukket liste over kjente flertydige etternavn beskytter
  det nå.
- Et alenestående etternavn som tilfeldigvis er et vanlig tysk ord
  («Gross»/«Grosse», «Gut», «Kurz», «Lang»/«Lange»), gikk hittil
  **fullstendig** tapt – også i enkle setninger som «Herr Gross
  unterschrieb den Vertrag.» Grunnen lå i spaCys egen stoppordliste, som
  inneholder disse ordene; en lukket liste over kjente etternavn bevarer
  dem nå fra å bli forkastet.
- Ved arbeids-, lån-, kausjons-, forvaltnings- og konkursavtaler samt
  vergemål/omsorg og sakkyndigoppdrag ble et etternavn som samtidig er et
  vanlig ord (f.eks. «Bauer»), oversett bak merkinger som «Auftraggeber:»,
  «Auftragnehmer:», «Arbeitnehmer:», «Versicherter:», «Darlehensgeber:»,
  «Darlehensnehmer:», «Bürge:», «Sicherungsgeber:», «Treuhänder:»,
  «Treugeber:», «Insolvenzverwalter:», «Gutachter:», «Sachverständiger:»,
  «Vormund:» eller «Pfleger:» – dels forble bare fornavnet gjenkjent,
  dels falt hele navnet bort.
- I impressumet ble et etternavn som samtidig er et vanlig ord (f.eks.
  «Bauer»), oversett bak merkingene «Geschäftsführer:»,
  «Geschäftsführerin:», «Vertretungsberechtigt:», «Inhaber:» eller
  «Inhaberin:» – ved «Geschäftsführer:»/«Inhaber:» falt hele navnet bort,
  ved «Vertretungsberechtigt:» forble bare fornavnet gjenkjent.
- En kontaktblokk der merkingen sto alene på sin linje og bar den
  kjønnsnøytrale kolonformen («Ansprechpartner:in», navn under), ble
  **fullstendig** oversett – kolonet ble lest som feltskiller, «in» som
  (forkastet) feltverdi, og selve navnet på neste linje kom aldri
  til sin rett. Stjerneformen («Ansprechpartner*in») var ikke berørt av
  dette.
- Sto navn og merking med samme kolon-kjønnsform på **én** linje
  («Ansprechpartner:in Anna Berger»), rev plassholderen ordet «in» med
  inn i erstatningen, i stedet for bare å fjerne navnet – selve navnet
  ble fortsatt fullstendig fanget opp.
- Et navn i en tabellkolonne under en person-kolonneoverskrift (f.eks.
  «Name Vorname Geburtsdatum» over «Bauer Anna 03.05.1985», som i en
  lønnsslipp) ble fullstendig oversett, så snart det bare sto ett eneste
  mellomrom mellom kolonnene og ingen linje begynte med et
  inndelingsnummer – nettopp formen et ekte PDF-tekstutdrag leverer
  slike linjer i.
- I en chat- eller møteprotokoll med talernavn foran kolon (f.eks.
  «Bauer 🙂: Ich stimme dem Vorschlag zu.») forble navnet fullstendig
  ugjenkjent, så snart et reaksjonstegn sto mellom navn og kolon og
  etternavnet samtidig er et vanlig ord («Bauer», «Koch», «Schneider»
  o.l.) – en hel protokoll kunne dermed bli stående uten en eneste
  gjenkjent taler.
- Samme talerlinje-hull fantes også med andre mellomtegn foran kolon: et
  statustillegg i parentes («Bauer (Vorsitz): …», «Bauer (abwesend):
  …»), et klokkeslett i skarpe klammer («Bauer [14:32]: …») og et
  fotnotetegn rett ved navnet («Bauer*: …»). Også her forble taleren
  fullstendig ugjenkjent, så snart etternavnet samtidig er et vanlig ord.
- Sto en allerede gjenkjent person i et vedlagt protokoll- eller
  logg-utdrag i samme melding (for eksempel en supportsak) i tillegg som
  brukernavn i formen «fornavn.etternavn» – med liten forbokstav, uten
  mellomrom, forbundet med et punktum –, forble dette klarnavnet
  leselig, selv om samme navn i følgebrevet allerede var sladdet.
- Samme brukernavn-hull fantes også med en understrek i stedet for et
  punktum («fornavn_etternavn») – et like utbredt format i protokoll- og
  loggutdrag.
- Og også i omvendt rekkefølge forble brukernavnet leselig
  («etternavn.fornavn» henholdsvis «etternavn_fornavn») – enkelte
  systemer setter etternavnet foran i loggbrukernavnet i stedet for bak.
- En dødsdato forble ugjenkjent, når det ikke sto noen annen angivelse
  ved siden av («Herr Bauer ist am 12.03.1985 verstorben») – for dette
  fantes hittil overhodet ingen egen gjenkjenning, og den generiske
  datoen griper ikke ved denne standardterskelen.
- En dødsdato forble også ugjenkjent, når setningen brukte verbformen i
  stedet for partisippet («Frau Meier verstarb am 12.03.1985», «Er
  starb am 12.03.1985») – bare «ist … verstorben»/«ist … gestorben»
  traff tidligere.
- En bryllupsdato forble ugjenkjent, uansett hvilken form den sto i
  («Eheschließung am 12.03.2010», «Hochzeitsdatum: 12.03.2010», «Herr
  und Frau Bauer heirateten am 12.03.2010») – for dette fantes hittil
  overhodet ingen egen gjenkjenning, og den generiske datoen griper ikke
  ved denne standardterskelen.

- **I etterredigeringsprogrammet kunne en andre ramme over en nettopp
  satt plassholder la en rød tegnrest bli stående**, for eksempel «[G» i
  stedet for «[BEG1]» – uten noen advarsel, for resten hørte ikke lenger
  til den fortrolige angivelsen (den var allerede fjernet i det første
  trekket), bare til selve plassholderen. Grunnen var fargeleggingen: En
  nylig innsatt plassholder ble skrevet tegnvis inn i filen, også ved
  ensfarget standard – en senere ramme over samme sted fant dermed ingen
  sammenhengende ordlyd å stedfeste seg i. En ensfarget plassholder står
  nå som ett stykke i strømmen, slik den automatiske rensingen alltid har
  gjort; bare en ekte overgangs- eller regnbuetekst trenger fortsatt
  enkelttegn. Den innebygde motkontrollen gjenkjenner nå i tillegg en
  slik rest også når den eksakte tegnstrengen til plassholderen ikke
  lenger forekommer.
- En nummerert navneliste med trinnvis inndelingsnummer («1.1 Max
  Mustermann», «1.2 Huber Franz» …) mistet alle navn til samme bremse
  som egentlig bare skal beskytte ekte inndelinger og posisjonslister –
  uten kolonneoverskrift over listen fantes intet vitne som et navn
  kunne blitt reddet av.
- Et navn i en engelskspråklig påloggingslinje i en systemlogg
  («Accepted password for Max Mustermann from 10.0.0.5 port 51000
  ssh2») ble ikke gjenkjent – den tyske språkmodellen fant det bare når
  «invalid user» sto foran, ellers ble det stående. Slike
  protokollutdrag legges ofte uendret ved en hendelsesrapport. Navn bak
  «for» foran en IP-adresse gjenkjennes nå pålitelig.
- Navnet til betaleren i SEPA-mandatreferansen til en kontoutskrift eller
  bokføringsjournal (f.eks. «MREF+Mustermann Klaus+SVWZ+ Miete August»)
  forble åpent – intet mellomrom, ingen setningsstruktur, bare med «+»
  skilte stor-bokstavfelt, og i den der vanlige rekkefølgen «etternavn
  fornavn» fant gjenkjenningen det heller ikke tilfeldigvis. Gjenkjennes
  nå.
- Gaten med husnummer i den første linjen av en adressetabell (f.eks.
  «Nachname | Vorname | Straße | PLZ | Ort») forble åpen – språkmodellen
  gjettet der et feil, men lengre sted på tvers av flere kolonner, og det
  fortrengte det riktige, kortere adressetreffet. Gjenkjennes nå.
- Samme lekkasje oppsto med en tabulator i stedet for «|» eller «;» som
  kolonneskiller – der forsvant adressen til og med helt i stedet for
  bare å bli delvis tapt. Gjenkjennes nå.
- En gate med husnummer forble åpen, når det rett etterpå uten
  mellomrom fulgte et postnummer med komma (f.eks. «Bahnhofstrasse
  12,80331 München», som i en kommaseparert tabellkolonne) – kommaet så
  ut som en desimal i en mengde, og gaten gjaldt derfor overhodet ikke
  som adresse for mønsteret. Gjenkjennes nå.
- En gate med husnummer forble åpen, når det rett etterpå uten komma
  fulgte stedsforstavelsen «St.» (Sankt) (f.eks. «Hauptstraße 5 St.
  Pölten», et brevhode uten foranstilt postnummer) – «St.» så ut som
  stykktallenheten, og gaten gjaldt derfor overhodet ikke som adresse
  for mønsteret. Gjenkjennes nå.
- Et dør-/oppgangstillegg etter et husnummer (f.eks. «Lerchenfelder
  Gürtel 43/12») forble åpent synlig, når det rett etterpå sto en
  enkeltbokstav som tilfeldigvis stemmer med en måleenhet (f.eks. «h»
  for time) – adressen ble da bare renset frem til husnummeret uten
  tillegget sitt, i stedet for å gripe fullstendig eller ikke i det hele
  tatt.
- En emnelinje med et yrkeslikt etternavn foran fornavnet («Betreff:
  Bauer Anna», «Betreff: Bauer, Anna») forble tidligere fullstendig
  ugjenkjent – også midt i dokumentet med en foregående fullstendig
  setning. Gjenkjennes nå.
- Et tysk skattenummer med mellomrom, punktum eller bindestrek mellom
  blokkene (f.eks. «Steuernummer: 30 815 08153» eller «30.815.08153»)
  forble tidligere ugjenkjent – bare skrivemåten med skråstrek ble
  funnet. Gjenkjennes nå.
- Et navn bak en medisinsk feltmerking («Patient:», «Hausarzt:»,
  «Behandelnder Arzt:», «Überweisender Arzt:» og de kvinnelige formene
  deres) forble tidligere ugjenkjent, når etternavnet samtidig er et
  vanlig tysk ord (f.eks. «Patient: Bauer Thomas»). Gjenkjennes nå.
- Et navn bak feltmerkingen «Zahnarzt» (tannlege) på egen linje (f.eks.
  «Zahnarzt», under «Huber Franz») forble tidligere ugjenkjent – verken
  for- eller etternavn. «Zahnärztin» og den enkle «Arzt»-formen var ikke
  berørt av dette. Gjenkjennes nå.
- Et etternavn bak «Herr»/«Frau», etterfulgt av en formell floskel som
  «zur Kenntnisnahme», «zur Unterschrift» eller «zur Weiterleitung», ble
  tidligere fanget for vidt og rev floskelen med inn i navnetreffet – av
  «Frau Petra Klein zur Vertretung in allen Angelegenheiten» ble «Petra
  Klein zur Vertretung» erstattet, og resten av setningen forble
  grammatisk lemlestet. Ekte adelspredikater som «von der Leyen» eller
  «zu Guttenberg» forblir uberørt av dette.
- Samme formelle-floskel-overredigering satt også bak navnet i et
  e-post-«To:»-hodefelt, en godkjenningskode (C.1/C.1.1/C.1.2), en
  førerkortkode, et klammet skjemafelt («[Vorname]: …») og en
  upunktert hilsen – overalt der rev «zur»/«von» osv. en påfølgende
  floskel som «zur Unterschrift» eller «zur Vertretung» med inn i
  treffet, dels ble til og med det bare partikkelordet selv hengende som
  navnerest i resultatet. Også her bevares ekte adelspredikater
  fullstendig.
- Studentnummeret bak merkingen sin ble hittil overhodet ikke gjenkjent –
  «Matrikelnummer 7654321» falt helt gjennom gjenkjenningen, verken som
  identifikasjonsnummer eller via språkmodellen, fordi tallet alene ikke
  bærer en gjenkjennelig form.
- Det samme gjaldt for deltakernummeret – «Teilnehmernummer 4471829»
  falt helt gjennom, verken som identifikasjonsnummer eller via
  språkmodellen.
- I CV-en falt navnet under avsnittsoverskriften «Persönliche Daten» ofte
  helt eller delvis gjennom gjenkjenningen, når det uten tiltaleform sto
  direkte under i formen «etternavn fornavn».
- Det samme gjaldt for avsnittsoverskriften «Kontaktdaten» – der falt
  navnet til og med fullstendig gjennom, ikke bare delvis.
- I en bostedsattest eller søknadsliste med sammenslått kolonne «Name,
  Vorname» (folkeregisterskrivemåte, verdi f.eks. «Mustermann, Max» i
  en celle) falt navnet helt gjennom gjenkjenningen, når en ytterligere
  kolonne som fødselsdatoen fulgte.
- En fødselsdato i den på ID-kort og bostedsattest vanlige formen
  «Geburtsdatum/-ort: 22.07.1978 / Rostock» ble ikke gjenkjent – bare
  kommaformen «Geburtsdatum, Geburtsort: …» traff.
- «Bürgerservice» og «Bürgerbüro» ble av og til feilaktig sladdet som
  sted, særlig etter en tankestrek som oppramsingsskiller (for eksempel
  «Wenden Sie sich an das Bürgerservice – Bürgerbüro …»).
- Et merket telefonnummer som ble delt midt i to av et linjeskift (for
  eksempel fra en smal brevhode-kolonne eller en PDF-tekstuttrekking ved
  kolonnebredden: «Telefon: 0176 12\n34567») ble delvis bare halvveis
  sladdet – resten bak linjeskiftet forble leselig.
- Et merket identifikasjonsnummer (kunde-, medlems-, kontraktnummer og
  lignende), som ble delt midt i to av et linjeskift (for eksempel
  «Kundennummer: K903\n944» fra en smal kolonne), ble bare halvveis
  sladdet – resten bak linjeskiftet forble leselig.
- Et navn med akademisk tittel foran en yrkesbetegnelse etter komma (for
  eksempel «Dipl.-Ing. Sabine Roth, Projektleiterin») forble fullstendig
  ubeskyttet – linjen så ut som en tabellarisk kolonneoverskrift og ble
  feilaktig forkastet som saksinnhold.
- Tittelen «Dr.-Ing.» (en vanlig tysk ingeniørgrad) foran et navn ble
  ikke tatt med i den maskerte personverdien og forble leselig – samme
  bindestrek-fallgruve som ved «Dipl.-Ing.».
- Titlene «Dipl.-Kfm.», «Dipl.-Kffr.» og «Dipl.-Psych.» (diplomøkonom/
  -kvinnelig økonom/-psykolog) foran et navn ble ikke tatt med i den
  maskerte personverdien og forble leselige – samme bindestrek-fallgruve
  som ved «Dipl.-Ing.» og «Dr.-Ing.».
- En MAC-adresse i Cisco-skrivemåten med punktum i stedet for kolon
  (f.eks. «aabb.ccdd.eeff», slik svitsjprotokoller og supportsaker
  gir ut den) ble overhodet ikke gjenkjent og forble leselig.
- Et etternavn bak «Familie» (f.eks. «Die Familie Gruber unterschreibt
  den Vertrag») forble alt etter setningsbygning ugjenkjent og dermed
  leselig – også med adelspredikat foran («Familie von der Leyen»).

- Ved en kroatisk adresse uten skilletegn mellom postnummer+sted og
  gate+husnummer (f.eks. «10000 Zagreb Ulica Ivana Lučića 5») forble
  husnummeret urenset.

- Ved en litauisk kontaktangivelse med merkingen «Kontaktinis asmuo»
  (f.eks. «Kontaktinis asmuo: Vilkas Jonas») forble etternavnet
  ugjenkjent, når det samtidig var et vanlig substantiv (Vilkas = «ulv»,
  Vanagas = «hauk»).

- Et fødsels- eller bostedsland uten videre merking i et dansk
  skjemafelt (f.eks. «Fødeland: Tyskland» eller «Bopæl: Tyskland») ble
  ikke gjenkjent.

- Et fødsels- eller bostedsland uten videre merking i et rumensk
  skjemafelt (f.eks. «Țara: Germania» eller «Țara de reședință:
  Franța») ble ikke gjenkjent.

- Et firmanavn under den litauiske feltmerkingen «Darbdavys:» eller
  «Įmonės pavadinimas:» (arbeidsgiver/firma) ble ikke gjenkjent.

- Et firmanavn under den russiske feltmerkingen «Работодатель:» eller
  «Наименование организации:» (arbeidsgiver/firma) ble ikke gjenkjent.

- En utskrevet dato med månedsnavn på rumensk (f.eks. «31 decembrie
  2024») ble ikke gjenkjent.

- Et ungarsk fødenavn bak forkortelsen «szül.» (f.eks. «Nagy Éva (szül.
  Kovács)») ble ikke gjenkjent og forble stående åpent leselig.

- En lagret HTML-profilside (eller en e-post med vedlagt nettside) kunne
  la det borgerlige navnet forbli urenset, når det bare sto i
  Open-Graph-profilfeltene `profile:first_name`/`profile:last_name`/
  `profile:username» – disse bærer navnet oppdelt i stedet for
  beskrivende som `og:title» og renses nå også.

- En leveringsfeilmelding (bounce/NDR) bar ofte hodefeltene til den
  opprinnelig ikke leverbare e-posten (avsender, mottaker, emne) i en
  egen, tredje vedleggsdel – denne forble i den rensede versjonen
  fullstendig urørt. Delen renses nå som resten av leveringsrapporten.

- Den individuelt navngitte redigereren av et beskyttet område i Word
  (Begrens redigering → Unntak, `w:permStart`) forble i klartekst, selv
  om samme navn i løpende tekst for lengst var renset. Det fjernes nå
  også.

## 0.10.42-alpha.20260827 – 27. august 2026

### Nytt

- **Navngitte gjenkjenningsprofiler gjør ulike arbeidstilfeller tilgjengelige
  med ett grep.** Under *Innstillinger → Gjenkjenning → Hva fjernes* kan det
  gjeldende kategori- og typeutvalget lagres og umiddelbart brukes på nytt
  via et valgfelt. Den faste profilen *Standard* tilsvarer den tidligere
  leveringstilstanden og kan ikke slettes. En profil endrer utelukkende hva
  som fjernes; språk, utdataart, gjenkjenningsdybde samt egne begreper og
  søkemønstre forblir uberørt.

- **Typen resultat velges nå direkte før rensing.** Et felles valgfelt i
  hovedvinduet fastsetter for hele bunken om Maskuro setter inn lesbare
  plassholdere, sladder eller fjerner uten erstatning. De to separate
  feltene for PDF og Office i innstillingsvinduet er bortfalt; dermed er
  denne viktige avgjørelsen synlig og kan ikke lenger utilsiktet skille
  seg for blandede bunker. Den veiledede rundturen forklarer det nye
  valget før den første rensingen.

- **Temaer og vannmerker merker ferdige PDF-er tydelig ved ønske.** Tolv
  helhetsutseender stemmer erstatningstekster og sladdeflater overens; nytt
  blant dem er Pride samt vår, sommer, høst og vinter. *Hemmelig akt*
  bringer direkte med seg en diagonal `TOP SECRET`. Uavhengig av dette kan
  en fri merketekst eller et eget bilde, ikon henholdsvis SVG velges med
  farge og dekkevne. Importert grafikk bygges inn uten sine metadata og
  forblir tilgjengelig når kildefilen flyttes. Ved etterredigering erstatter
  Maskuro sitt tidligere vannmerke i stedet for å legge det flere ganger
  oppå hverandre. Tekstvannmerker tegnes som det siste PDF-laget med lys
  kontur, slik at de forblir synlige også på mørke bilder og tett tekst.
  Etterredigeringsprogrammet ignorerer Maskuros vannmerke fullstendig og
  tilbyr ikke lenger teksten dets som sladdekandidat.

- **Egne utdatatemaer kan lagres og deles.** Den gjeldende blandingen av
  erstatningstekst, sladding og vannmerke får et navn, forblir i
  innstillingene og kan eksporteres eller importeres som klartekstfri
  JSON. Svart-hvitt-utskriftsforhåndsvisningen advarer mot svake
  kontraster; valgfri suksesskonfetti forblir rent i grensesnittet.

- **En siste eksportprøve og en forklarende kontrolliste avslutter
  fremstillingsrunden.** Før den endelige lagringen sammenligner Maskuro
  hvert verdipresist kjente PDF-sted enda en gang i tekstlaget og
  gjengitte bildepunkter; advarsler nevner utelukkende side og
  koordinater. I redigeringsprogrammet viser *Hvorfor er dette dekket?*
  kategori, gjenkjenningsvei og sikkerhetsmargin, aldri den fjernede
  klarteksten og aldri i sluttdokumentet.

- **Sladdefelt kan nå være fine.** Under *Innstillinger → Utseende* står
  fargeforvalg, frie fargevelgere, overganger, regnbue, striper, prikker,
  blomster, stjerner, hjerter, poter, skyer, lyn, kaffebønner, ender, soler,
  blader, snøfnugg, papir-, tekstmarkør-, tapelim- og reproduserbare
  tilfeldige mønstre klare, med umiddelbar forhåndsvisning. Erstatningstekster
  får valgfritt en farge, en overgang, en regnbue, en pille eller en
  etikett. Kategorifarger skiller navn, adresser, kontakter og medisinske
  angivelser. PDF overtar hele utformingen; Word, PowerPoint, OpenDocument
  og HTML bruker den valgte dekkende grunnfargen. Beskyttelsen endres
  ikke ved dette: Maskuro fjerner det fortrolige innholdet først og tegner
  farge eller mønster først på det tomme stedet.

- **Maskuro finnes igjen for Linux – som AppImage, DEB, RPM og portabelt
  arkiv.** DEB og RPM registrerer programoppføring, filtilknytninger,
  terminalkommando og ikon i systemet; AppImage kjører uten installasjon.
  Oppdateringer forblir ved en eksisterende DEB- eller RPM-installasjon i
  samme pakkeformat og foretrekker ellers AppImage.

- **Synskontrollen legger ikke lenger vanlig PDF-tekst frem en gang til som
  nye treff.** Det avsluttende OCR-blikket og den sikre gjenoppbyggingen av
  de synlige sidene forblir fullstendig aktive; som ny funnkilde gjelder i
  standardinnstillingen bare områder som sidetekst og enkeltbildekontroll
  ennå ikke har lest. Dermed blir ikke produktlinjer bare på grunn av en
  avvikende andre OCR-lesning til nye navn eller firmaer. Den som fortsatt
  vil ha to uavhengige vurderinger av hele den synlige teksten, slår på
  *Kontroller hele den synlige PDF-siden for angivelser en gang til* i
  innstillingene.

- **PDF-er kan vises fortløpende, arkvis eller som dobbeltside.** Tre
  kompakte visningsikoner sitter nederst rett ved siden av «Bredde» og
  «Side». Fortløpende ruller ved arkkanten til neste side; Enkeltside
  holder musehjulet på det gjeldende arket; Dobbeltside viser et oppslag,
  gjør det anklikkede arket redigerbart og flytter Frem/Tilbake ett helt
  oppslag. Sideminiatyrer og sammenligningslupe åpner dessuten i en klart
  smalere venstre grunnkolonne og gir arbeidssiden mer plass.

- **Du ser nå hva KI-nivået har gjort.** Etter hver kjøring står det under
  «Detaljer» per fil en linje om det – «KI-nivå: 12 grensetilfeller
  kontrollert, 3 forkastet» –, og fant den ikke noe å endre, står også det
  der. Tidligere tidde det dyreste nivået fullstendig: Om det i det hele
  tatt ble spurt, var det umulig å se utenfra.

  Den som trenger det mer detaljert, slår på *Skriv ned hvert KI-spørsmål i
  loggen* under «Innstillinger → KI». Da fører loggfilen for hvert spørsmål
  størrelse, varighet og antall funn, samt ventetiden fra en mengdegrense
  hos motparten. Knappen «Vis loggfil» ved siden av åpner mappen – den
  ligger i applikasjonsdatamappen, som er skjult under Windows og som ingen
  finner av seg selv. I filen står det utelukkende størrelser, aldri tekst
  fra dokumentene dine.

- **Maskuro gjenkjenner når KI-tjenesten din setter et tak på antall
  forespørsler.** Vertsbaserte tjenester tillater ofte bare få forespørsler
  per minutt – fire er ikke uvanlig. De overtallige avvises ikke, men må
  vente, og av to sekunder per svar blir det førti. Det så tidligere ut som
  om modellen var treg. Nå leser Maskuro grensen fra tjenestens svar,
  sender ikke flere spørsmål samtidig enn det som blir godtatt, oppgir
  grensen under «Kontroller forbindelse» og regner den inn i
  varighetsanslaget.

- **Sidevisningen bruker Word, Excel og PowerPoint på maskinen din – og er
  dermed rundt seks ganger raskere.** Tidligere trengte den LibreOffice,
  som finnes på færrest kontorpc-er; den som ikke hadde det, så en knapp
  som ba om en fremmed installasjon. Nå gjelder: Er Microsoft Office
  installert, brukes det automatisk – uten oppsett, uten nedlasting, uten
  at du krysser av noe. LibreOffice forblir den andre veien og ved
  OpenDocument-filer til og med den første; mislykkes den ene, forsøkes
  den andre.

  Forskjellen merkes særlig under arbeidet: Etter hver erstatning settes
  siden opp på nytt, og det koster via Office rundt et halvt sekund i
  stedet for tre. Den første visningen av et dokument tar fortsatt noen
  sekunder, deretter følger den håndgrepene dine uten ventetid.

  Ditt eget åpne Word røres ikke ved dette: Maskuro starter en egen,
  usynlig økt, åpner filen bare for lesing, slår av makroer og avslutter
  alt igjen så snart etterredigeringsvinduet lukkes. Passordbeskyttede
  filer avvises, i stedet for å bli hengende i en usynlig dialog.

- **Førstegangsoppsettet spør nå også om ansikter, koder og signaturer – og
  laster ned alt manglende i ett trekk.** Ved siden av den utvidede
  gjenkjenningen står på den første siden de tre bildebryterne: Gjør
  ansiktsområder ukjennelige, gjør strek- og QR-koder ukjennelige, sladd
  håndskrevne signaturer på PDF-sider. PDF-grensen står synlig ved
  avkrysningen; Office-filer søkes ikke automatisk gjennom for signaturer.
  Under avkrysningene står hvor mange megabyte klikket på «Neste» koster.
  Nedlastingen skjer deretter i **ett** vindu med **én** fremdriftslinje for
  alt samlet, i stedet for i flere dialoger etter hverandre; et avbrudd
  avslutter hele forløpet og lar ingenting bli halvferdig liggende. Den som
  ikke vil ha noe av dette, fjerner avkrysningene – da lastes heller
  ingenting.

- **Forhåndsvisningen kan tynnes ut etter kontrollbehov og slås sammen etter
  type.** Over listen sitter en glidebryter *Skjul godt belagte*: Jo lenger
  den står mot høyre, desto mer skjuler den fra grønt mot rødt; helt til
  høyre står bare det programmet alene har gjettet. Et klikk på
  overskriften til en type slår den sammen. Begge deler er en lesehjelp,
  ikke et utvalg – det som er skjult eller slått sammen, forblir avkrysset
  og blir erstattet; hvor mange verdier det gjelder akkurat nå, står under
  glidebryteren. Ved korte lister vises ikke glidebryteren. Bytte til to
  kolonner holder nå dessuten også brytere med *aldri igjen*.

- **Bildelisten kan åpne seg selv før hver kjøring.** Den som vil bestemme
  over hvert bilde enkeltvis, setter den nye avkrysningen *Fastsett
  enkeltvis før hver kjøring* under «Bilder». Listen med forhåndsvisning
  vises da av seg selv ved rensing, i stedet for at du hver gang må klikke
  «Fastsett enkeltvis …» selv; avbryter du den, renses det heller ikke.
  Inneholder ingen av de valgte filene et bilde, vises ingenting.
  Forhåndsinnstilt er avkrysningen av.
- **Maskuro finner håndskrevne signaturer på PDF-sider og fjerner dem fra
  bildepunktene.** Tidligere ble navnetrekket stående under et renset
  dokument – tekstgjenkjenningen leser trykkskrift, og det den ikke leser,
  erstattes ikke. Søket er en egen bryter og trenger en gjenkjenningsmodell
  som lastes ned én gang.

  Målt finner den rundt 84 av 100 signaturer og dekker dem til omtrent fire
  femtedeler. Dette er en hjelp og ingen garanti: Etter hver kjøring står
  det i rapporten hvor mange som ble funnet – også når det ikke var noen,
  for det kan bety at det ikke er noen der eller at en ble oversett. På 72
  ekte forretningssider uten signatur har den ikke funnet opp noen.

  En **tegnet** signatur blir funnet, men ikke fjernet: Den består av
  linjer, ikke av bildepunkter, og et felt over ville bare vært en
  dekning der linjene ble stående. Slike steder telles og nevnes, slik at
  man kan sladde dem selv i etterredigeringsvinduet.

  Word-, Excel-, PowerPoint- og OpenDocument-filer søkes ikke automatisk
  gjennom for signaturer. Grensesnitt, førstegangsoppsett, modellnedlasting,
  kommandolinje og håndbok nevner nå denne grensen uttrykkelig.

- **Rundturen fører nå også gjennom forhåndsvisningen – vinduet der du
  bestemmer.** Ved øvingsdokumentet åpnes den av seg selv, også om du
  ellers har slått av forhåndsvisningen (innstillingen din forblir slik
  den er). Det forklares hva fargene betyr, hvorfor det i hver linje bare
  står ett spørsmål – er det i det hele tatt en person her? – og hva «aldri
  igjen» er godt for. Ved fargene er søkelyset på en godt belagt linje,
  som regel IBAN – det grønne eksempelet som setningen nevner; deretter på
  den svakest belagte, og der kan du midt i forklaringen klikke selv:
  Avkrysningen bort, verdien blir stående i dokumentet. Ved en lang liste
  åpner vinduet seg større for rundturen, slik at forklaringen ikke ligger
  over linjene. Åpner vinduet seg en gang til, sier rundturen også hvorfor
  – den ferdige siden leses en gang til som bilde, og dermed oppstår
  bruddstykker som ser ut som et navn.

- **Redigeringsprogrammet åpner seg stort ved første gang.** Original,
  resultat, verktøylinje og trefflista sto ved siden av hverandre og hadde
  i den tidligere grunnstørrelsen for lite plass. Den som drar vinduet
  mindre, får sin størrelse tilbake neste gang – ingen blir overstyrt.

- **Et dobbeltklikk på en plassholder henter den tilbake** – i Word, Excel,
  PowerPoint, OpenDocument, tekst, e-post og HTML. Og den som drar over
  flere plassholdere og velger «Hent tilbake utvalg», henter alle
  liggende der tilbake på én gang. Man trenger altså ikke lenger treffe
  den skarpe klammen nøyaktig. Plassholdere som ved anonymisering står for
  flere ulike verdier, er unntatt fra dette – de telles og nevnes, ikke
  gjettes.

- **Håndboken har et kapittel «Forhåndsvisning før erstatning».** Vinduet
  er forhåndsinnstilt på og er det eneste der du bestemmer – i håndboken
  sto det tidligere bare i en bisetning. Nå står det der hva en avkrysning
  betyr (den gjelder for **hvert** funnsted, ikke bare det oppførte),
  hvorfor det bare er ett spørsmål å besvare per linje, hva «aldri igjen»
  varig gjør, og hvorfor vinduet kan åpne seg en gang til ved en PDF. På
  alle atten språkene, og i listen over innstillinger er bryteren nå også
  ført opp.

### Endret

- **Feltet «Erstattede verdier» har en glidebryter over fargene, og
  læringsmodus står ikke lenger der.** Ved mer enn åtte verdier sitter over
  listen den samme glidebryteren som i forhåndsvisningsvinduet: *Skjul godt
  belagte* tynner ut visningen til det som virkelig bør ses gjennom. Ved
  dokumentet endrer dette ingenting, og hvor mange linjer av hvor mange som
  vises, står under – søkefelt og glidebryter telles sammen. Avkrysningen
  *Læringsmodus* har forsvunnet fra feltet; den står fortsatt i menyen
  *Verktøy* og i verktøylinjen.

- **Feltet «Erstattede verdier» viser nå de samme fargene som dokumentet.**
  Hver linje der er bakgrunnsfarget som stedet i dokumentet og som verdien
  i forhåndsvisningen: Rødt betyr «gjettet alene, her lønner det andre
  blikket seg først», grønt «gjenkjent av et navngitt mønster». Innenfor
  hver type står det usikreste øverst – du arbeider deg altså gjennom
  listen ovenfra og ned og har sett det viktigste først. Tidligere sto alt
  der like lyst og sortert alfabetisk.

- **Læringsmodus er fra fabrikken av.** Etter en rettelse i
  etterredigeringsvinduet spurte programmet tidligere av seg selv om det
  skulle bli en egen regel av det. Dette spørsmålet kommer midt i arbeidet;
  den som ikke har bestilt det, opplever det som et avbrudd. Den som vil
  ha reglene, slår på knappen *Læringsmodus* i verktøylinjen – valget
  gjelder deretter varig, i begge retninger.

### Rettet

- **Eksporterte regelfiler merkes nå uttrykkelig som beskyttelsesverdige.**
  Egne begreper og unntak kan stå der i klartekst; dessuten kan filen
  inneholde hash-saltet som lar seg bruke til å bekrefte antatte verdier.
  Den vellykkede eksporten viser derfor et varsel og oppfordrer til å
  beskytte filen og bare bevisst gi den videre til autoriserte mottakere.

- **Den siste sikkerhetskontrollen holder ikke lenger tilbake rensede
  kontorfiler på grunn av sine egne plassholdere.** En typekode som «SVNR»
  står også i `[SVNR1]`; tidligere gjaldt dette som en antatt klartekstrest
  og den ferdige filen ble forkastet. Samtidig etterjusteres nå også
  telefonnumre og IBAN-er der Office legger den samme angivelsen uten
  synlige mellomrom i en referanse eller en innebygd fil.

- **Word, Excel, PowerPoint og OpenDocument lar ikke lenger en sent
  oppdaget feltkopi bli stående.** Blir en verdi først gjenkjent i en
  bilagring eller innebygd kontorfil, rydder en snever etterkjøring også
  opp i de tidligere leste synlige og skjulte kopiene. Allerede opprettede
  referanseplassholdere erstattes ikke på nytt ved dette.

- **Ved enkeltvis tilbakehenting av en Word-nedtrekksliste følger ikke
  lenger et naboutvalg ubedt med tilbake.** Det fullstendige originalavsnittet
  overtas først når heller ikke attributtene dets lenger inneholder åpne
  plassholdere.

- **Dårlig leselige skanninger mister færre sammenhengende angivelser.** En
  alternativ OCR-lesning med tiltaleform og todelt navn bevares;
  gatefragment, husnummer og postnummer-sted beskytter sammen hele
  adresselinjen, også når den faller i naboliggende OCR-blokker. Faktura-
  og artikkelfelt samt arrangementlinjer ved siden av tas ikke med i
  dette. En gyldig dato som bak «født» er falt i flere OCR-ord og
  skilletegn, gjøres også fullstendig ukjennelig.

- **Suksesskonfettien er nå synlig ved automatisk åpning av
  redigeringsprogrammet.** Konfettien spruter nå direkte fra
  *Rens*-knappen i stedet for å regne fra den øvre vinduskanten.
  Redigeringsprogrammet venter bare på det første, 850 millisekund korte
  sprutet og åpner deretter automatisk; uten aktivert konfetti er det
  fortsatt ingen forsinkelse.

- **Sidetelleren og zoomlinjen hopper ikke lenger frem og tilbake ved
  overfaring av visningsikonene.** Qt fordelte statuslinjens frie plass på
  nytt så snart henvisningen til et symbol dukket opp der. Begge
  betjeningsgruppene beholder nå ved hover sin naturlige bredde og faste
  posisjon.

- **Hastighetsmålingen av en tilknyttet KI-server mislyktes alltid** – på
  hver server, siden den egne KI-en finnes. Den spurte med en trang
  svargrense og forsøkte deretter å lese det dermed avkuttede svaret; det
  måtte mislykkes, og lagret ble «ikke målt». Følgene var synlige overalt:
  Varighetsanslaget regnet serveren din med tempoet til den vedlagte
  modellen på en kontorpc, og i innstillingene sto det varig at
  hastigheten ennå ikke var målt. Nå måles det på mengden serveren har
  generert, og ikke på innholdet i svaret dens.
- **«Maksimal gjenkjenning (KI) – treg» sto der også når det ikke stemte.**
  Beskrivelse og henvisning omtalte den vedlagte modellen på en kontorpc –
  «en språkmodell på denne maskinen», «ved store dokumenter opptil en
  time». Den som har koblet til en egen KI-server, leste der to feil ting:
  Det regnes ikke på hans maskin, og det svares på sekunder i stedet for
  timer. Begge deler kommer nå fra målingen. Foreligger ingen, hevder
  applikasjonen ingenting lenger, men sier at det ennå ikke er målt.

- **Tilbakehenting virker nå også på et dratt utvalg.** Den som dro over
  flere plassholdere og ville trykke *Hent tilbake utvalg*, fant knappen
  grå: Den ble bare aktiv når markeringen var **nøyaktig** én plassholder –
  dratt over et avsnitt er den det aldri. Veien bak fantes allerede, bare
  kom ingen dit. Nå holder det å markere området; alle plassholdere der i
  kommer tilbake i ett trekk.

- **Tilbakehenting krasjet når sammenligningslupen var åpen.** Lupen husker
  stedet under musepekeren for å følge med i originalen. Ved
  gjeninnlasting etter en tilbakehenting ga den dette stedet tilbake i en
  form som tekstvisningen ikke kunne bruke til noe – og fordi en slik feil
  midt i grensesnittet avslutter programmet, ble tilbakehentingen til et
  krasj. Lupen står i grunnstillingen åpen, så det rammet den vanlige
  veien.

- **Etter tilbakehenting hopper visningen ikke lenger til dokumentbegynnelsen.**
  I et lengre skriv var stedet man nettopp arbeidet med, borte etter hvert
  håndgrep. Nå blir avsnittet stående øverst som sto øverst før.

- **Uten LibreOffice sier sidevisningen hvor det kommer fra, i stedet for
  bare å mangle.** De to knappene *Sidevisning* og *Sladd som PDF* var
  sperret og nevnte i verktøytipset bare at ingen LibreOffice ble funnet;
  det fantes ingen vei dit noe sted i applikasjonen. Et klikk åpner nå en
  henvisning med veien til det gratis, åpen kildekode-baserte LibreOffice.
  Håndbok og FAQ sto feil på dette punktet – de kunngjorde en
  nedlastbar byggekloss som applikasjonen ikke tilbyr.

- **Før levering søkes den ferdige filen gjennom en siste gang i sin
  helhet – nå også ved Word, Excel, PowerPoint, LibreOffice, e-post, HTML
  og tekst.** Tidligere hadde bare PDF-en dette siste blikket. Alle
  kontroller før dette ser etter på et sted som noen tidligere har
  navngitt; en lagring ingen har tenkt på, kontrolleres derfor heller ikke
  av noen. Til slutt gjennomsøkes nå den skrevne filen blindt for alt som
  er erstattet – i hver del av pakken. Blir noe stående der, oppstår
  **intet** resultat, og meldingen nevner verdien. Et dokument som anses
  som renset, er verre enn ingenting.

- **Navn som står i `<script>` og `<style>` meldes nå.** Begge forblir
  fortsatt urørt – der står programtekst, og en erstatning midt i en
  identifikator gjør en nettside til en ødelagt nettside. Det ble bare
  ikke sagt tidligere, og det var feilen: En stilregel `content: "Anna
  Musterfrau"` står **synlig** på skjermen for mottakeren, og i
  resultatet sto den fortsatt der mens programmet meldte siden som renset.

- **I innstillingene kan tilleggsmodellene igjen lastes ned og fjernes.**
  Knappen ved siden av «Utvidet gjenkjenning» og «Maksimal gjenkjenning
  (KI)» endte ved trykk i feilrapportvinduet, i stedet for å hente
  modellen. Den andre veien – avkrysningen i gjenkjenningen, som selv
  spør etter modellen – var aldri berørt av dette.

- **Navn som skjuler seg i ark- og områdenavn i en tabell, meldes nå.**
  Navnet på et ark står på fanen nederst, navnet på et navngitt område i
  navnefeltet og i hver formel som bruker det. Ingen av dem erstattes
  fortsatt – formler viser til dem, og en arbeidsbok med referansefeil
  hjelper ingen –, men det står nå der. Tidligere kom meldingen bare for
  arknavnet i en Excel-arbeidsbok: Et navngitt område «Bezuege_Brunnthaler»
  gikk stille med ut, og ved en LibreOffice-tabell tidde programmet helt.
  Et ark «Notizen Ortner» gjaldt dermed som renset, og mottakerens første
  blikk falt på navnet.

  Meldt blir bare det som faktisk fører til en person: et ord som
  uansett ble erstattet i samme arbeidsbok, eller et treff som velger ett
  av flere ord. Et enslig ord som «Zustaendig» eller «Bezug_Umsatz»
  utløser ikke lenger en advarsel – tidligere ville det gjort det, og en
  advarsel som kommer ved annenhver arbeidsbok, leser ingen etter tredje
  gang lenger.

- **«Hent tilbake original» henter nå virkelig alt tilbake.** I enkelte
  dokumenter manglet det etterpå enkelttegn – av «Seestraße 14» ble det
  «Seestraße 4», av «An:» et «An», av «nordlicht-planung» et «nordlicht
  planung» –, og enkeltlinjer kom slett ikke tilbake. Nettopp der lot det
  seg deretter ikke lenger markere noe med musen og ikke lenger sladdes
  noe: Teksten sto riktignok på papiret, men programmet kjente den ikke
  lenger. Berørt var smale tegn – ettallet, kolon, bindestreken – i
  dokumenter som setter hvert tegn enkeltvis; øvingsdokumentet er ett av
  dem.

- **Og de samme dokumentene gjøres ikke lenger om til et bilde ved
  rensing.** Fordi et slikt tegn ble stående, meldte etterkontrollen en
  rest og siden ble av forsiktighet rastrert. Teksten på den var deretter
  bare et avbilde: ikke lenger søkbar, ikke lenger markerbar, større i
  filen. Øvingsdokumentet forblir nå ekte tekst på begge sider.

- **Fargede merker blir ikke lenger stående over tilbakehentet tekst.** Den
  som angret en erstatning, så det fargede rektangelet fortsatt over det
  gjenopprettede ordet – det hevdet «her ble noe fjernet», selv om
  originalen sto der igjen.

- **En stripe avslører ikke lenger hvor langt ordet under var.** Ved
  sladding dekker stripen i korte linjer nå **hele** linjen –
  adresseblokk, hodedata, smal tabellcelle. Får ikke hele linjen plass
  (den vanlige tabellinjen med tre kolonner), holder det seg til feltet;
  i en løpende tekstlinje forblir det ordnøyaktig, ellers gjorde et navn
  midt i setningen hele setningen svart. Og striper som står under
  hverandre, blir **like lange**: I adresseblokken står det en verdi på
  hver linje, og tre forskjellig lange striper avslørte fortsatt hvor
  lange linjene var. De vokser bare så langt som papiret er fritt – foran
  en nabokolonne stopper stripen.

- **«Hele linjen» sladder nå virkelig hele linjen.** Tidligere endte
  stripen ved det neste større mellomrommet – altså ved feltets slutt. I
  løpende tekst falt ikke dette – der er feltet linjen; i hodedata og
  tabeller derimot: Av «Navn: Anna Musterfrau   Avdeling: Salg» ble det en
  stripe som endte nøyaktig ved siste bokstav i navnet – og dermed sto
  lengden dens igjen på arket. Stripen løper nå fra det første til det
  siste ordet i linjen og tar med seg nabokolonnene. Den som bare vil
  treffe verdien, velger «Ord»; automatikken sladder uendret feltvis.

- **Før levering gjennomsøkes den ferdige filen en siste gang.** Alle
  tidligere kontroller ser etter på et sted noen tidligere har navngitt –
  sidetekst, funnrektangel, bildeflate. Men en PDF har flere lagringssteder
  enn en oppramsing kan romme: kommentarer, skjemaverdier, bokmerker,
  dokumentinformasjon, filvedlegg, JavaScript. Til slutt gjennomsøker
  Maskuro derfor den skrevne filen blindt for alt den har erstattet –
  overalt unntatt i sidetekst, der samme ordlyd også har lov til å stå.
  Blir noe stående der, oppstår **intet** resultat, og meldingen nevner
  verdien. Et dokument som anses som renset, er verre enn ingen fil i det
  hele tatt.

- **Det som ikke lot seg kontrollere, gjelder ikke lenger som kontrollert.**
  På tre veier så tidligere et mislykket etterkontroll ut som et rent
  resultat. En side der tekstlaget ikke lot seg lese, gjaldt som spesielt
  ren – der var det jo ingenting å finne; den rastreres nå. Lot en side med
  gjenværende funnsted seg ikke rastreres som reserve, ble den levert
  stilltiende; nå avbrytes rensingen heller. Og motkontrollen i
  etterredigeringsvinduet meldte etter en egen feil «ingenting igjen» – i
  vinduet ikke til å skille fra at alt ble fjernet; nå vises advarselen
  sammen med knappen «Rastrer side».

- **«Tilbakestill til standard» tilbakestilte slett ikke de fleste
  innstillingene.** Ni av tjueto avkrysninger sto uendret der etter
  håndgrepet – deriblant forhåndsvisningen, «Åpne rensede filer
  etterpå», etterredigeringsvinduet, umiddelbar lagring og begge
  oppdateringsavkrysningene. Den lagrede filen var riktignok tømt, men
  vinduet holdt fast på de gamle verdiene og skrev dem tilbake inn ved
  neste klikk. Nå kommer hver avkrysning tilbake, og merknaden «endret»
  forsvinner med den.
- **«Lagre kontrollrapport automatisk per rensing» viste avkrysset, men var
  av.** Etter tilbakestillingen forble avkrysningen satt, mens verdien var
  slettet – det oppsto ingen rapport lenger, uten at noe pekte på det.
  Det samme gjaldt kontrollprotokollen og den egne skjermopptaket; deres
  hurtigtast blir nå også korrekt på- eller avmeldt straks ved
  tilbakestilling.

- **Stripene i en linje ser nå like ut.** Tidligere brakte hvert funnsted
  sin egen stripe med seg, og høyden kom fra skriften til det trufne
  ordet. I en linje med merking og verdi i forskjellige størrelser sto det
  derfor en tykk og en tynn strek med forskjøvne kanter ved siden av
  hverandre, og der to funnsteder bare var skilt av et mellomrom, ble det
  stående en lys spalte over. Striper på samme linje har nå samme over-
  og underkant, og det som bare er skilt av et mellomrom, blir én stripe.
  Det som skal stå igjen mellom to funnsteder – kommaet bak navnet, en
  merking, et beløp – holder dem fortsatt fra hverandre. Gjelder for
  satte sider som for skanninger.

- **Fanene under «Om dette programmet» begynner igjen øverst.** Personvern,
  lisensvilkår og lisenshenvisninger åpnet seg midt i teksten – den som
  leste dem, måtte først rulle helt opp for å se den første linjen.

- **Pennen åpner ikke lenger et andre redigeringsvindu, men henter det
  eksisterende frem.** Tidligere oppsto det et nytt ved hvert klikk.
  Vinduet har ingen egen oppføring i oppgavelinjen – den som minimerte
  det, kom ikke til lenger og klikket en gang til; ved gjenoppretting av
  hovedvinduet kom deretter alle opphopede vinduer frem samtidig. Nå
  havner flere dokumenter i fanerekken til det åpne vinduet, og et
  dokument som allerede står der, får ingen andre fane.

- **«Utvidet gjenkjenning» bærer ikke lenger merknaden «endret» så lenge
  modellen dens mangler.** Den leveres påslått, uten den nedlastbare
  modellen kan den imidlertid slett ikke være det – i innstillingene sto
  linjen derfor på hver nyoppsatte maskin som endret, selv om ingen hadde
  rørt den. Hvorfor avkrysningen er av, sier nå bare selve beskrivelsen:
  «Modell ennå ikke lastet ned».

- **Innføringsstripen forklarte i Office- og tekstfiler PDF-lerretet.**
  Der sto «å klikke på et ord sladder det» – i en Word-fil sladder
  imidlertid et klikk ingenting, der markeres det og trykkes deretter en
  knapp. Den sier nå det som gjelder i den respektive visningen.
- **Verktøylinjen var i tekstvisningen tettpakket med beskrivelser.**
  «Erstatt utvalg», «Sladd utvalg», «Hent tilbake utvalg», «Sidevisning» og
  «Sladd som PDF» står nå som symbol – som sine søsken i en PDF. Navnene
  deres blir stående i korthjelp og meny.
- **Ctrl+musehjul i sammenligningslupen flyttet ikke zoomglidebryteren
  med.** Skriften ble større, glidebryter og prosenttall ved siden av
  påsto fortsatt det gamle nivået.
- **Installasjonsprogrammet for en oppdatering kom ikke i forgrunnen** –
  man måtte først klikke på det i oppgavelinjen (bare Windows).
- **Et årstall ved linjebegynnelsen gjaldt som østerriksk postnummer.** I
  et CV ble «2020 Salgsstrategier» til en plassholder – hele linjen
  forsvant. Et firesifret tall mellom 1900 og 2099 trenger nå et andre
  adressesignal: gaten over, et feltord foran, en landkode eller et kjent
  stedsnavn. Adresseblokker har det; årstallskolonner ikke.
- **Et måned-år-par gjaldt som telefonnummer.** Av «Siden 08.2010
  123-Verkauft GmbH» ble det et «telefonnummer» – måned, år og de første
  sifrene i firmanavnet bak.
- **Rapporten sa «kontrollert med tekstgjenkjenning» og fortidde hva den
  ikke leser.** Blir bilder bevart, står det nå med at håndskrevet i dem
  ikke blir funnet – en signatur eller et håndskrevet innført navn blir
  stående. Tidligere sto denne setningen bare ved skannede sider; en
  vanlig PDF med en innebygd signatur fikk ikke et ord om det.
- **En plassholder på sladdet bildegrunn sto ved venstre kant av stripen
  sin.** Blir en verdi funnet i et bilde – for eksempel et skrevet navn
  ved siden av en innskannet signatur –, må bildeområdet sladdes i full
  bredde. Den kortere plassholderen lot naken sort stå ved siden av, noe
  som så ut som to prosesser. Den sitter nå midtstilt på stripen.

## 0.10.41-alpha.20260826 – 26. august 2026

### Nytt

- **Etter prøveperioden minner et vindu én gang per oppstart om lisensen.**
  Det kommer fem minutter etter oppstart – ikke umiddelbart, slik at det
  ikke står i veien for noen før det første håndgrepet – og venter så lenge
  en rensing pågår. Derfra fører én vei til kjøp og én til å registrere en
  allerede kjøpt nøkkel; «Senere» lukker det så snart de fem sekundene i
  knappen har gått. Ingenting sperres: Det gratis nivået fortsetter å
  fungere som før.

- **Ventetiden før en kjøring på det gratis nivået varer nå ti i stedet for
  tretti sekunder.** Den skal minne om lisensen, ikke stanse arbeidet.

- **Alle tre henvisningene om lisensen ser nå like ut.** Ventetid, påminnelse
  i de siste prøvedagene og henvisning etter prøveperioden bærer samme
  stripe, samme oppbygning og samme knapper; resttiden står nå i knappen i
  stedet for som et stort tall ved siden av.

- **Trefflisten i forhåndsvisningen står igjen under hverandre.** Den var
  fra ni verdier tospaltet; ved gjennomgang hopper øyet da mellom to baner,
  og her avgjøres det linje for linje. Den som liker de to banene, slår dem
  på igjen nederst til venstre i vinduet – valget forblir lagret, og ved
  bytte forblir allerede fravalgte verdier fravalgt.

- **KI-nivået står åpent for alle som kobler til en egen KI-server.**
  «Innstillinger → KI» fører alt om dette: tilkoblingen, hva KI-en har lov
  til å gjøre, hva den får til oppgave – og over det bryteren for nivået
  samt motkontroll, så snart en server er registrert. En språkmodell som
  regner med på selve arbeidsplassen, holdes fortsatt tilbake: Den trenger
  flere minutter for ti sider og er dermed ikke noe for hverdagen.

- **En egen KI kan kobles til.** I stedet for den vedlagte språkmodellen kan
  en større modell på en annen maskin svare – på en server i huset eller en
  arbeidsstasjon med sterkt grafikkort. Det kreves en tjeneste med
  OpenAI-kompatibelt grensesnitt (Ollama, LM Studio, llama.cpp-server, vLLM,
  LocalAI); den settes opp under «Innstillinger → Egen KI» sammen med en
  forbindelseskontroll som virkelig spør modellen, måler tempoet og
  fastslår den mulige svarformen. Flere tekstavsnitt kjører samtidig i
  stedet for etter hverandre.

- **Hva KI-en har lov til å gjøre, og hva den får til oppgave, er nå
  innstillbart.** Tre brytere avgjør grensetilfellekontroll, selvstendig
  søking og søking i løpende tekst; instruksen til modellen står ordrett
  der, kan suppleres med husets egne begreper og tilbakestilles til
  standard med én knapp.

- **Forlater teksten dermed det egne nettverket, varsles det før hver
  kjøring.** Maskuro gjenkjenner ut fra adressen om KI-serveren står i
  huset, og nevner en kjent leverandør ved navn. Advarselen kan slås av,
  men bare mot en uttrykkelig bekreftelse på at man har fullmakt til denne
  overføringen, og bare for nettopp denne adressen. Ved selve forløpet
  endres ingenting: Overføringen står fortsatt i protokollen og i
  kontrollrapporten til hver fil. På kommandolinjen spørres det ikke, men
  stanses – der trengs `--ki-auswaerts-erlauben`.

- **Forhåndsvisningen før erstatning er som standard aktiv ved nye
  innstillinger og gjelder nå også for uttrykkelig renset innhold fra
  utklippstavlen samt tekst og bilder som limes inn i programmet.** Ved
  dokumentbunker vises fortsatt nøyaktig én forhåndsvisning per dokument med
  alle sider; den stille umiddelbare rensingen av korte kopier åpner
  bevisst ikke et vindu.

- **Treff kan slås på og av i forhåndsvisningen over hele den fargede
  linjen.** Avkrysningen er nå stor og kontrastrik; i tillegg viser et
  tilstandsfelt «Erstatt» henholdsvis overstrøket «Erstatt», slik at valgte
  og fravalgte verdier straks kan skilles også på mørke konfidensfarger.

- **Også PDF-er med synlig sikkerhetsmotblikk åpner forhåndsvisningen bare
  én gang per dokument.** Fravalgte begreper forblir fravalgt for det
  senere sidevitnet; kontrollen dets fortsetter uten å avbryte samme
  kjøring med en andre dialog.

- **Erstatningsord ser like ut i etterredigeringsprogrammet også på
  rastrerte sider.** Ligger den røde plassholderen i bildepunktene i stedet
  for i PDF-tekstlaget, får den nå likevel den samme etter konfidens
  fargede bakgrunnsflaten som en vanlig PDF-tekstplassholder.

- **Allerede forhåndsvisningen før erstatning viser kontrollbehovet for de
  funnede begrepene.** Hver linje bærer samme rød–oransje–grønn-farge som
  senere erstatningen i redigeringsprogrammet. Innenfor en kategori står
  lav sikkerhet og røde falske-treff-kandidater øverst, sterke grønne
  bevis nederst; likestand forblir alfabetisk. Kommer samme verdi fra flere
  funnsteder, telles av forsiktighet den mest tvilsomme vurderingen deres.
  Uvurderte spesialtilfeller står nøytralt gult mellom rødt og oransje.

- **Resultatet kan nå kopieres direkte fra etterredigeringsprogrammet som
  fil.** «Kopiér resultat» legger den gjeldende rensede versjonen på
  utklippstavlen, uten å lukke redigeringsprogrammet og søke opp filen i
  hovedlisten igjen. Ved en ennå ulagret manuell redigering kjører
  automatisk hele den sikre lagringsveien først; «Kopiér bilde» forblir som
  separat funksjon for rene bildepunkter.

- **Erstattede ord viser i redigeringsprogrammet på et blunk hva som bør
  kontrolleres først.** Ren språkmodellgjetning er rød, selv om spaCy
  melder 85 prosent for den. Ytterligere ustøttede modellvurderinger
  forblir høyst oransje; sterke navngitte bevis kan bli grønne. Manuelt
  arbeid og eldre tilordninger uten vurderbar vurdering forblir nøytralt
  gule. Også automatiske sladdestriper bærer disse fargene i
  redigeringsforhåndsvisningen – nå også når stripen er en del av en
  rastrert PDF-side. For dette må tilordningen passe og den tidligere
  ordboksen påviselig være dekkende svart; vanlig fet skrift farges ikke.
  I den lagrede PDF-en forblir alle striper uendret dekkende svarte.

- **Det som fravelges i forhåndsvisningen, kan huskes varig.** Der du
  fjerner avkrysningen, sier du: Her har gjenkjenningen tatt feil. Tidligere
  gjaldt dette bare for dette ene dokumentet. Nå vises ved linjen en bryter
  «aldri igjen»; trykt kommer verdien varig inn i listen «Fjern aldri» og
  gjelder fremover som ufarlig i hvert dokument. Under listen står hva som
  blir varig ved dette, før du trykker «Erstatt». Motsatt retning finnes
  bevisst ikke: Det som en gang ble funnet, finner gjenkjenningen igjen.

- **En knapp tilbakestiller alle innstillinger til leveringstilstanden.**
  Den står nederst til venstre i innstillingsvinduet og spør først. Filene
  dine, lisensen din, dine egne gjenkjenningsregler og autostarten forblir
  urørt; det administrasjonen din forhåndsbestemmer, gjelder fortsatt. Hver
  innstilling som avviker fra leveringstilstanden, bærer dessuten merknaden
  «endret» – slik ser man på et blunk hva man har stilt om på.

### Endret

- **Et resultat lagres ikke lenger automatisk – først ved lagring.** En
  kjøring fra vinduet skriver sin rensede versjon først til et midlertidig
  sted; filen «…_bereinigt» ved siden av originalen oppstår først når du
  trykker «Lagre». Frem til da kan resultatet ses, etterredigeres og
  kopieres. Hver ferdige linje har til dette en lagreknapp, under listen
  står «Lagre alle», og i redigeringsprogrammet gjelder Ctrl+S. Den som
  tømmer listen eller avslutter programmet, blir spurt; det ingen lagrer,
  blir heller ikke liggende noe sted. «Vis i mappe» er sperret før lagring
  – det midlertidige stedet er ikke et mål man sender noen til.
  Tilordningsfilen følger med ved lagring.

  I innstillingene under «Program» henter «Lagre resultater umiddelbart ved
  siden av originalen» tilbake den tidligere atferden. Kommandolinje,
  mappeovervåking og utklippstavlevakt lagrer fortsatt uendret umiddelbart
  – der sitter ingen som kunne lagre.

- **Verktøylinjen til etterredigeringsprogrammet er ryddet opp.**
  Læringsmodus står nå ytterst til høyre ved sammenligningslupe og
  «Erstattede verdier» – de tre bryterne som slår en driftsmodus på og av,
  står dermed samlet. «Overfør til alle sider» er flyttet til de tre
  sladdeformene, fordi den bare gjør noe der. «Kopiér resultat»,
  «Fil – Tilbakestill» og «Overfør til alle sider» klarer seg uten
  beskrivelse; navnet deres står fortsatt i verktøytipset og i menyen.
  Mellom «Erstatt» og «Hent tilbake original» står en skillestrek: De to
  er motsatte retninger og så ved siden av hverandre ut som to varianter av
  samme verktøy.

- **Symbolet for «Kopiér resultat» viser nå et dokument.** To ark med
  brettet hjørne og tekstlinjer i stedet for to like ark med en liten
  hjørnepil. «Kopiér bilde» bærer til gjengjeld bildetegnet, slik at begge
  kan skilles uten beskrivelse. Knappen «Kopiér» i resultatlisten viser
  samme dokumentsymbol – den lagrer samme fil.

- **Innstillingene er sortert og forsynt med overskrifter.** «Gjenkjenning»
  har nå fire avsnitt: *Hva fjernes*, *Hvordan erstattes*, *Hvor grundig
  søkes* og *Før og etter kjøringen*. Ansiktsgjenkjenning og strek-/QR-koder
  står ved bildene, der man leter etter dem; «Program» er delt i
  *Resultatfiler*, *Ved oppstart*, *Oppdatering*, *Visning* og
  *Tilbakemelding til oss*, og navnetillegget til resultatfilen står ved
  resultatfilene i stedet for mellom språk og utseende.

- **Den utvidede gjenkjenningen er fra fabrikken påslått**, også før
  språkmodellen dens er lastet ned. Tidligere hang standarden på
  modellbeholdningen, og en nyoppsatt maskin kjørte varig på det svakere
  nivået. Oppsettsvinduet tilbyr modellen på den første siden til
  nedlasting og nevner prisen ved siden av. Mangler den, sier avkrysningen
  fortsatt det, i stedet for å late som et nivå kjører som ikke gjør det.

- **De to begrepslistene heter nå det de gjør:** «Fjern alltid» i stedet for
  «Egne begreper» og «Fjern aldri» i stedet for «Unntak».

- **Forhåndsvisningsvinduet er mer oversiktlig.** Fra ni verdier står de i
  to kolonner, linjene er flatere, og antall funnsteder står rett bak
  begrepet i stedet for ved høyre kant.

- **I etterredigeringsprogrammet står Erstatt før Sladd** – i verktøylinjen,
  i menyen «Verktøy» og ved høyreklikk på siden. Erstatt er regelen: En
  plassholder kan klikkes på og hentes tilbake, en stripe ikke.

- **Færre doble knapper i redigeringsprogrammet.** «Lagre som …» og «Kopiér
  bilde» står nå bare i Fil-menyen, med sine vante hurtigtaster. I linjen
  blir det én av hver: Lagre og «Kopiér resultat» – hvor det lagres til,
  står uansett i statuslinjen og kan endres der med ett klikk.

- **Utklippstavlevakten tilbys ikke lenger ved første oppstart.** Den griper
  inn i hver kopieringshandling på systemet; den som ser programmet for
  første gang, kan ikke vurdere det. I innstillingene står den fortsatt,
  der med klausulen ved siden av som hører til den.

- **Det lyse utseendet blender mindre.** Vindusbunnen kom tidligere fra den
  respektive systemstilen og var dermed den eneste store flaten ingen hadde
  bestemt over – under Windows nesten hvit. Nå er den et brutt hvitt, likt
  på hvert system.

- **Rundturen og håndboken forklarer fargene.** Hva rødt, oransje, grønt og
  gult bak et erstattet ord betyr, står nå som en egen stasjon i rundturen
  og som et avsnitt i håndboken – på alle språkversjoner.

### Rettet

- **Håndbok og FAQ viste plassholdere som ikke finnes lenger.** Siden
  omstillingen til den korte formen skriver Maskuro `[NAM1]`; i hjelpen sto
  fortsatt `[NAME1]`, og setningen «Forhåndsinnstilt er `[NAME1]`» var
  dermed rett og slett feil. I de sytten oversatte versjonene sto i tillegg
  det **tyske** merket i stedet for sitt eget – en spansk leser så
  `[NAME1]`, der programmet hans skriver `[NOMB1]`. Likeledes endelsen på
  resultatfilen: Der lovet alle versjoner `_bereinigt`, mens programmet
  oppretter `_limpiado`, `_nettoyé` eller `_除去済み`. Berørt var også formen
  uten nummer (ved anonymisering heter alt `[NAM]`, ikke `[NAME]`) og
  identifikasjonen utledet fra verdien ved hashing.

- **Forhåndsvisningsvinduet avbryter nå bare én gang per dokument – og en
  andre gang bare hvis det virkelig kommer noe nytt til.** En PDF leses fra
  to sider: én gang fra innholdsstrømmen og til slutt fra den gjengitte,
  synlige siden. Tidligere spurte hver av de to for seg. Nå gjelder: Det du
  har bestemt i det første vinduet, gjelder videre, og verdier som allerede
  sto der, kommer ikke igjen. Finner derimot synskontrollen av de ferdige
  sidene noe som tidligere ikke sto noe sted, blir det lagt frem for deg
  igjen – alene, uten de allerede avgjorte verdiene.

- **Forhåndsvisningsvinduet sier nå hva man skal avgjøre etter.** I stedet
  for «Fjern avkrysning = verdien blir stående» – som sier hva avkrysningen
  *gjør*, men ikke når man skal fjerne den – står det der: Avkrysning bort
  overalt der det ikke står en personopplysning; der har gjenkjenningen tatt
  feil. Dessuten nevner hvert vindu kontrollkjøringen verdiene dets kommer
  fra.

- **Plassholdere ser like ut i hele dokumentet.** På sider som bygges opp på
  nytt som bildesider i OCR-veien, ble synlige plassholdere tidligere satt
  i skrivemaskinskrift – «[PLZ4]» sto da bredt og med seriffer ved siden av
  et smalt «[NAM1]» på samme side. De bærer nå den samme sanseriffe
  skriften som overalt ellers og settes heller ikke lenger bredere enn
  planlagt ved innpassingen. Det usynlige søkelaget beholder sin egen
  skrift – det trenger pålitelige mål, ikke utseende.

- **I verktøylinjen til redigeringsprogrammet står det ikke lenger doble
  skillestreker.** Der en hel verktøygruppe bortfaller for den åpnede
  filtypen – i en PDF for eksempel sidevisning og gjengivelse –, ble
  tidligere begge strekene rundt hullet stående.

- **Ved tilbakehenting blir det ikke lenger av og til bare et hvitt sted
  igjen.** En allerede eksakt gjenopprettet originaltekst males ikke lenger
  hvit over av den brede, samlede boksen til sin fjernede plassholder. Ved
  blandet tekst- og bildetilbakehenting settes tekst dessuten bare inn
  usynlig hvis sidebildet nettopp bærer akkurat denne originaltilstanden
  synlig. Dette gjelder for rammer, treffpanel og PDF-vedlegg.

- **«Hent tilbake original» tilbyr ikke lenger unødvendig å rastrere siden.**
  Den strenge restttekstkontrollen forblir aktiv ved sladding og erstatning.
  Ved tilbakehenting utelates den: Der kommer originalinnhold bevisst
  tilbake igjen, og uendrede naboord i den utvidede tilbakehentingsrammen
  var ingen rensefeil, men et falskt treff.

- **Rundturen gjennom redigeringsprogrammet forklarer nå «Erstatt» og «Hent
  tilbake original» som egne trinn.** Begge verktøyene fremheves direkte i
  linjen og beskriver at en dratt ramme setter inn en plassholder
  henholdsvis henter tilbake det opprinnelige innholdet på dette stedet fra
  kildefilen.

- **Også landsspesifikke plassholdere forblir nå på høyst fire bokstaver.**
  Disse typene manglet tidligere i den sentrale forkortelseskatalogen og
  kunne derfor fortsatt vises utskrevet, for eksempel
  `[UMSATZSTEUER_ID1]`. Nye kjøringer skriver nå `[UID1]`; alle automatisk
  gjenkjente tyske og engelske typer forblir dermed entydige. Selvberegnede
  forkortelser for andre grensesnittspråk vokser ikke lenger utover fire
  tegn ved navnelikhet. Egne regelbeskrivelser forblir uendret navngitt slik
  de ble skrevet inn.

- **Erstatning bruker nå hele det faktisk ledige linjerommet før den
  sladder.** Den tidligere stive grensen ved tre ganger den opprinnelige
  ordbredden skapte striper selv i store tomme skjemafelt. Også treff fra
  det synlige OCR-motblikket får nå ved belagt PDF-tekst en lesbar
  plassholder; svart forblir rene bilde-, kommentar- og vektorinnhold, den
  valgte sladdedriftsmodusen samt ekte trange steder der ikke engang en
  entydig kortform passer.

- **En allerede synlig plassholder overskrives ikke lenger en gang til rødt
  ved sikkerhetsrastreringen.** Rastreringen overtar nå den eksisterende
  erstatningen fra sidebildet og legger bare en usynlig søkekopi til. Må en
  sikkerhetsstripe male over nettopp dette stedet, fornyes hele den
  faktiske plassholderboksen i stedet for bare sitt kortere opprinnelige
  anker.

- **«Hent tilbake original» markerer nå bare sikre mål i den dratte
  rammen.** Alle erstattede begreper der lyser opp enkeltvis og eksakt;
  uendret løpende tekst forblir urørt. Ekte vektorielle sladdestriper
  markeres også enkeltvis, hvis originaltekst ligger under den svarte
  PDF-flaten deres. På rastrerte sider avstår forhåndsvisningen bevisst fra
  en antatt stripeflate: Det tidligere bildepunktsøket forbandt der
  bokstaver, understrekninger og tabellinjer til store røde flater på
  gale steder. Selve gjenopprettingen forblir uberørt av dette.

- **Ved gjenoppretting på rastrerte sider kommer teksten igjen tilbake.**
  Til slutt sto det der et tomt sted med fargede rektangler over. Den
  tilbakehentede teksten sto i dokumentet, men ble malt over av den hvite
  bunnen til en plassholder som tegnes lenger bak i sideoppbyggingen.

- **Kontrollfargene ligger ikke lenger flere ganger over hverandre.** Samme
  sted ble farget per oppføring i tilordningen – på en side fem ekte
  funnsteder, hver malt over fem ganger, til det bleke merket ble en mettet
  blokk. Og de vises ikke lenger på ord som slett ikke ble erstattet: Står
  originalverdien fortsatt på siden, finnes det heller ikke lenger et merke
  der.

## 0.10.40-beta.1 – 24. august 2026

### Rettet

- **Sladdestriper i redigeringsprogrammet har nå en sikkerhetsmargin.**
  Ord-, linje- og frie rammer dekker også overhengende glyfer og glattede
  kantpiksler; en gjengivelseskontroll sikrer dessuten at verken synlige
  rester eller leselig originaltekst blir stående.

- **Erstatningstekster forblir lesbare og ensartet korte.** Nye navn,
  adresser og frie begreper vises for eksempel som `[NAM1]`, `[ADR2]` og
  `[BEG3]`. Den faste nedre grensen er 4,5 punkt; ved plassmangel kortes
  det ned først og det brukbare løperommet utvides. Gamle tilordninger med
  lange plassholdere forblir lesbare og tilbakehentbare.

- **Flerords erstatninger fra treffpanelet er sikret mot doble merker og
  originalrester.** Regresjonen består med og uten nummererte
  plassholdere; per funnsted forblir nøyaktig én felles tilordning bevart.

- **Tilbakehentet innhold fra utklippstavlen renses ikke umiddelbart på
  nytt på macOS.** Selv om systemsignaturen bare bytter forsinket etter
  skrivingen, gjenkjenner Maskuro sitt eget innhold pålitelig.

### Nytt

- **Redigeringsprogrammet kan tilbakestille en fil fullstendig til den
  nylig rensede utgangsversjonen.** «Fil – Tilbakestill» forkaster etter en
  bekreftelse alle etterredigeringer av den gjeldende fanen, inkludert
  erstatningsliste og tellere. Kommandoen er sperret uten endringer og lar
  seg selv angre igjen med «Angre».

- **Forskjøvede datoangivelser beholder nå pålitelig sin kronologi over
  flere filer.** Den felles forskyvningen forankres allerede ved påslåing
  av strategien varig i reglene; dessuten kan forskyvningen ikke lenger
  være null dager og dermed ubemerket la den ekte datoen stå.

- **Den manuelle PDF-behandlingen dekker nå hele det profesjonelle
  sladdeforløpet.** Enkeltbegreper, lister og regulære mønstre kan søkes
  og sikkert sladdes i den åpne PDF-en eller over alle PDF-er i en mappe;
  hele sider og sideområder kan velges direkte. Farge, nøytral hvit flate,
  overleggstekst, skrift, retning og gjentagelse har en forhåndsvisning,
  gjenbrukbare koder kan forvaltes samt im- og eksporteres. PDF-rensingen
  fjerner valgfritt alt skjult innhold ved full ombygging eller utvalgte
  dataklasser. Det sikreste valget er tydelig anbefalt, ugyldige
  søkemønstre forklares, og mappekjøringer skriver utelukkende
  resultatkopier.

- **Den frivillige bruksstatistikken viser nå installasjoner og
  versjonsbytter.** Maskuro genererer til dette en tilfeldig, lokalt lagret
  installasjonsidentifikasjon. Den inneholder ingen enhets-, bruker- eller
  lisensangivelser; serveren lagrer bare SHA-256-verdien dens. Statistikken
  forblir fullstendig avslåbar i innstillingene.

- **Rundturen er nå en veiledet øvelse gjennom begge vinduene.** Den legger
  selv det oppdiktede øvingsdokumentet i listen, forklarer veien frem til
  rensingen og fortsetter automatisk i redigeringsprogrammet etter
  kjøringen. Den som avbryter rundturen, avslutter også denne
  fortsettelsen.

- **Firmaer fra femten ytterligere rettsområder gjenkjennes.** Den som
  renser dokumenter fra Baltikum, Belgia, Skandinavia, Tsjekkia, Polen,
  Sørøst-Europa, Singapore, Brasil eller Mexico, mister ikke lenger
  firmanavn fordi rettsformen deres var ukjent – nytt blant dem er blant
  annet OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s., S.K.A.,
  Pte. Ltd. samt S.A. de C.V. og S. de R.L.

### Endret

- **Redigeringsprogrammets verktøylinjer bruker nå plassen sin mer
  målrettet.** Entydige standardsymboler og direkte gjenkjennelige
  verktøyformer står uten gjentakende tekst i linjen; flertydige
  handlinger beholder navnet sitt. Under «Visning» kan «Vis
  verktøybeskrivelser» slås av for å redusere begge linjene fullstendig
  til symboler. Verktøytips og menyer forblir fullstendig beskrevet,
  valget huskes.

- **Læringsmodus er nå varig synlig i verktøylinjen.** Den kan der slås
  umiddelbart på og av, også når feltet for erstattede verdier er lukket.
  Verktøylinje, Verktøy-meny og den tidligere avkrysningen i feltet viser
  alltid samme tilstand.

- **«Tilbakestill» ved sammenligningslupen tilbakestiller nå bare zoomen
  dens.** Knappen gjenoppretter standarden på 125 prosent, uten å dokke
  lupen, flytte den eller endre vindusstørrelsen dens. For hele
  oppsettet forblir «Tilbakestill visning» ansvarlig.

- **Feil og ønsker kan nå også meldes via hjelpeknappen.** «Meld feil …»
  og «Uttrykk ønske …» står der nå akkurat som i den klassiske
  hjelpemenyen; begge veiene åpner den allerede eksisterende sikre
  feilmeldingen henholdsvis den offentlige ønskelisten.

- **Oppgavelinjemenyen er kortere og klarere ordnet.** De to kommandoene
  med global hurtigtast – rensing av utklippstavle og skjermbilde – står
  nå rett under hverandre med en felles høyre hurtigtastkolonne.
  «Gjenopprett siste originalinnhold» bortfaller der; den mer
  forståelige gjenopprett-knappen forblir tilgjengelig i hovedvinduet.

- **Rettslige sider er direkte tilgjengelige under «Hjelp → Rettslig».**
  Undermenyen fører til lisensvilkår, personvernerklæring, om oss og
  vilkår på maskuro.com. Henvisninger om angrerett forblir ved kjøpet på
  nettstedet.

- **Manuelt sladdede PDF-er bygges fullstendig om på nytt ved lagring.**
  Synlige forblir sidene og deres nylest søkelag; metadata, filvedlegg,
  bokmerker, kommentarer, skjemaverdier, skjulte lag, søkeindekser,
  skript, beskårne innhold og innhold skjult under andre objekter tas
  ikke over i utdatafilen. Skrift og vektorgrafikk består deretter av
  bildepunkter – det er prisen for den beviselige grensen mot det fremmede
  PDF-objekttreet.

- **Ctrl+Shift+B tar nå på alle systemer som standard opp et skjermbilde
  med Maskuro.** Print Screen-tasten og kombinasjoner med den forblir
  mulige som egen tildeling. I menyen til oppgavelinjeikonet står de
  globale hurtigtastene nå til høyre for de tilhørende kommandoene. Egne
  lagrede tildelinger bevares.

- **Redigeringsprogrammet starter med sider og sammenligningslupe til
  venstre.** Sidefeltet står øverst, den åpne originallupen rett under;
  de erstattede verdiene forblir til høyre. En bevisst lagret egen
  oppsett har fortsatt prioritet.

- **Øvingsdokumentet står ikke lenger varig i hovedvinduet.** Det er del
  av den veiledede øvelsen og forblir i tillegg tilgjengelig under
  «Hjelp».

- **Førstegangsoppstarten fører direkte til den praktiske øvelsen.** Den
  illustrerte hurtigveiledningen tilbys ikke lenger som en andre,
  innholdsmessig dobbel inngangsvei; den forblir til enhver tid
  tilgjengelig under «Hjelp → Hurtigveiledning».

- **Det hvilende oppgavelinjeikonet forblir i full farge.** Det viser nå
  det samme kraftige Maskuro-skjoldet som den aktive
  utklippstavlemodusen; bare ved aktiv overvåking kommer det grønne
  lyspunktet til.

- **Øvingsdokumentet blir i Maskuro.** Inngangsknappen genererer den
  oppdiktede PDF-en og legger den direkte inn i fillisten, men starter
  ikke lenger en ekstra PDF-visning.

- **Søket i etterredigeringsvinduet forblir flytende under skriving.**
  Plassen til trefftelleren reserveres allerede ved åpning; den første
  teksten dens endrer ikke lenger lerretet og utløser ikke en ny
  PDF-rastreringskjøring.

- **Produsentnavn i fabrikatangivelser forblir synlige.** En oppføring som
  «Fabrikat: TRILUX eller likeverdig» beskriver den nødvendige varen og
  sladdes ikke lenger som firma utelukkende på grunn av denne merkingen.
  Leverandør-, firma- og produsentfelt forblir uberørt av dette.

- **Korpusmålinger teller for bredt sladdede treff som falske treff.**
  Fjerner Maskuro det forventede navnet, men tar samtidig med en setningsdel,
  øker nå det falske treff-antallet. Rapporten viser overgrep dessuten
  separat; tidligere falske-treff-tall er derfor ikke direkte
  sammenlignbare.

### Rettet

- **Tekniske og offentlige begreper fra tyske originaldokumenter sladdes
  sjeldnere som navn eller steder.** Kjøretøyutstyr, posisjons- og
  sumlinjer, anbuds- og personvernbegreper, lovhenvisninger samt filnavn
  for offentlig materiale bremses bare med sin belagte sakssammenheng. En
  ved tekstgjenkjenning tapt tegn med prikker i «Marz 2026» forblir
  beskyttet som måned; «Marz» uten datosammenheng kan fortsatt være et
  ekte navn eller sted.

- **«Hent tilbake original» tar straks hele den nødvendige bredden.**
  Treffer rammen bare ett ord av en tilordnet verdi, utvider Maskuro den
  selvstendig ut fra tilordningen og originallinjen til hele angivelsen –
  for eksempel fra «Planungs» til «Nordlicht Planungs GmbH». Den deretter
  gripbare rammen viser likeledes den faktisk tilbakehentede totalbredden.

- **«Hent tilbake original» viser nå svarte striper som et entydig mål.**
  Ved overfaring eller dragning lyser hele den gjenkjente stripen rødt med
  lys kontrastkontur, i stedet for bare en knapt tilordnbar tekstboks ved
  siden av. Dette gjelder også for rastrerte sider der stripen bare
  består av bildepunkter.

- **Redigeringsprogrammets rundtur utelater ikke lenger stasjoner når felt
  var lukket.** For rundturen åpner og ordner Maskuro sidefelt,
  sammenligningslupe og erstattede verdier midlertidig selv. Etter
  «Ferdig» eller et avbrudd kommer det personlige oppsettet tilbake. Er
  et verktøy grunnleggende utilgjengelig for en dokumenttype, forblir
  forklaringen dets som tekststopp, i stedet for å forsvinne ubemerket.

- **«Erstatt» forblir synlig også ved PDF-sikkerhetsreservefallet.** Måtte
  Maskuro bygge om en side som bilde på grunn av et gjenværende tegn eller
  skadet tekstløp, sto de riktige erstatningene bare usynlig i søkelaget,
  og på siden lå svarte striper. De faktisk satte erstatningsverdiene
  forblir nå synlig røde og søkbare gjennom alle raster- og
  OCR-ombygginger.

- **Henvisningene over den rensede versjonen forblir lesbare i det mørke
  utseendet.** Versjonsoverskrift, betjeningslinje og innledning overtar
  nå skriftfargen sin umiddelbart fra det faktisk viste Qt-vinduet.

- **Sladderammer sitter igjen over teksten på rastrerte PDF-sider.** De
  usynlige ordboksene var, avhengig av originalskriften, smalere enn de
  synlige bokstavene. Dermed oppsto hull i stripen, eller den siste
  bokstaven forble leselig. Boksene beholder nå bredde, høyde og
  løperetning til det synlige ordet.

- **«Hva er nytt» begynner igjen helt øverst.** Endringsloggdialogen setter
  etter ferdig vindusoppbygging skrivemerke og rullefelt uttrykkelig ved
  begynnelsen, i stedet for å starte midt i nyhetene avhengig av
  Qt-tilstanden.

- **Lukking under skanne-ordgjenkjenningen forblir stille.** En akkurat
  ferdigblitt OCR-bakgrunnskjøring sender ikke lenger til et allerede
  lukket etterredigeringsvindu.

- **Relative tidsangivelser tas ikke lenger for navn.** Faste vendinger
  som «i dag», «i går», «i morgen» og «neste uke» kjenner Maskuro nå fra
  de offisielle kalenderdataene til det respektive dokumentspråket.

- **Avslutning under den første modellnedlastingen rydder rent opp.** Den
  som lukker Maskuro eller etterredigeringsvinduet umiddelbart etter
  åpning, lar ikke en fortsatt i den native talegjenkjenningen arbeidende
  tråd bli stående igjen ved prosessnedbygging. Dette forhindrer den
  sporadiske krasjrapporten ved avslutning; en allerede kjørende
  nedlasting fullføres ordnet.

- **Forsinkede oppstartsdialoger vises ikke lenger etter avslutning.** Den
  som lukker hovedvinduet kort tid etter oppstart, får ikke deretter
  usynlig eller forsinket vist spørsmålet om beste gjenkjenning, nyheter
  eller innføring.

- **HTML og e-post beholder linjeslutt-tegnene sine.** På Windows blandet
  HTML-serialiseringen etter rensing og tilbakehenting LF og CRLF. Innhold
  og formatering var riktig, filen imidlertid ikke lenger bytelik. HTML-
  filer og MIME-meldinger overtar nå igjen skrivemåten til kilden sin.

- **Firmanavn med et forholdsord forblir fullstendige.** Bak et
  forholdsord kuttet Maskuro navn som «Gesellschaft für Systemtechnik
  mbH» eller «Bank für Arbeit und Wirtschaft AG» ved ordet «für». Hele
  firmanavnet gjenkjennes nå; ekte setningsinnledninger som «Vi er
  forsikret hos Alpha GmbH» forblir synlige.

- **Kinesiske firmanavn forblir fullstendige foran rettsformen sin.** En
  som verb tolkbar merkedel kunne, til tross for det entydige tillegget
  «有限公司», forkaste hele navnet. I skriftsystemer uten stor og liten
  bokstav har det offisielle rettsformankeret nå prioritet foran denne
  usikre ordklassegrensen.

- **PDF-sider ble uten grunn til bilder.** Ved flersides PDF-er der sidene
  deler en skriftliste – slik vanlige generatorer legger det opp – mistet
  alle sider etter den første referansen til skriftene sine. Følgen var
  dobbel: Tegn med prikker var i resultatet ikke lenger søkbare
  («Auftragsbestätigung» lot seg ikke finne), og etterkontrollen holdt
  deretter bokstaver for oversett som aldri sto på siden – den rastrerte
  hele tekstsider til bilder, dermed ikke lenger søkbare, ikke kopierbare
  og betydelig større. I kontrollbeholdningen rammet dette fire av
  sytten sider.
- **Et komma alene utløser ikke lenger rastrering.** Ender et funnområde
  ved ordet, hører skilletegnet ved siden av så vidt fortsatt med. Et
  komma eller et punktum er imidlertid ikke en oversett angivelse, og
  rastreringen koster hele siden. Bokstaver og sifre forblir uendret en
  grunn til å skjerpe.

## 0.10.38-alpha.20260824 – 24. august 2026

### Nytt

- **Firmanavn uten rettsform gjenkjennes nå når merkingen deres nevner
  det.** «Leverandør: Kranzbichler Handels GmbH» ble alltid allerede
  fjernet – rettsformen røper firmaet. «Leverandør: Dehner Märkte» ble
  stående, og i tilbud, anbud og bestillinger står leverandøren som regel
  nettopp slik. Det samme gjelder for «Firma:», «Produsent:», «Fabrikat:»,
  «Arbeidsgiver:» og deres motstykker på åtte andre språk, og også når
  merkingen står alene på sin linje og navnet under.

  Det som bak merkingen *ikke* er et firma, forblir urørt: «Leverandør: se
  vedlegg» sladdes ikke – ellers ville det stått «Leverandør: [ORGA1]», og
  det ville hevdet et navn som aldri fantes. Merkinger der det like ofte
  står et menneske bak («Kunde:», «Oppdragsgiver:»), er bevisst ikke med.

- **Et innsatt bilde kan nå også redigeres.** I vinduet «Rens bilde» står
  ved siden av «Kopiér resultat» en knapp *Rediger i redigeringsprogrammet*:
  Bildet renses og åpnes deretter for ettersladding, merking og
  utheving – samme vei som et skjermbilde går.

- **Numre bak merkingen sin finnes nå også når de navngir en
  forretningspartner.** Tidligere falt kunde-, kontrakt- og
  personalnumre; nå også debitor-, kreditor- og leverandørnummer, det
  østerrikske arbeidsgivernummeret, ANKÖ-registreringen samt WEEE-, EAR-
  og EPR-nummeret til en produsent – på tysk som på engelsk. I tillegg
  forstår Maskuro nå skrivemåten til satte tilbudshoder med mellomrom
  foran kolonet («Kunden-Nr : K903944»). Artikkel-, bestillings-, ordre-,
  tilbuds- og fakturanumre forblir fortsatt urørt: De navngir prosessen
  eller varen, ikke mennesket. Den som likevel vil fjerne dem, legger dem
  inn som eget søkemønster.

- **Du ser nå hvor lang tid en fil har brukt.** Ved den ferdige linjen
  står varigheten ved siden av det gjenkjente språket («ferdig · tysk ·
  2,4 s»), i sammendraget for hele kjøringen, i nøkkeltall-klaffen
  summen – og i kontrollrapporten står den som eget felt. Ved flere filer
  avslører linjen hvilken av dem som kostet tiden.

- **Skrifter som ikke støttes av system-OCR-en, kan leses erstatningsvis
  med en tilgjengelig språkfil.** Tidligere gjaldt: Behersker den
  systemegne tekstgjenkjenningen ikke en skrift (på Mac for eksempel
  Devanagari), sto det i resultatet «Bilde(r) ble IKKE kontrollert», og
  angivelsene i bildet ble stående. Nå trer den medfølgende
  tekstgjenkjenningen inn, hvis den passende språkfilen foreligger. Fordi
  et slik lest bilde er mer usikkert enn et regulært kontrollert, står det
  i resultatet: «lest med reserveprosedyren – vennligst se etter». Målt
  mot en historisk mellomstatus for hindi-prøven: **ti angivelser mer
  funnet og fire falske treff mindre** (64 % → 73 %). Den gjeldende
  sluttverdien står lenger oppe og skal ikke forveksles med denne.

- **Tekstgjenkjenningen spør nå etter riktig språk.** For alle
  dokumentspråk unntatt tysk og engelsk ble tidligere den engelske
  gjenkjenningsmodellen brukt, selv om den passende språkfilen forelå.
  Under Windows rammet dette hvert språk – gresk, japansk eller hindi ble
  der lest med den engelske modellen.

- **En oppsettsveiviser ved aller første oppstart.** (Den som allerede har
  brukt Maskuro, får den ikke – «førstegangsoppstart» betyr første
  oppstart, ikke første oppstart etter denne oppdateringen.) Tre spørsmål i
  stedet for seks bilder: språket til dokumentene dine, om tekst i bilder
  leses med, og hvordan du vil nå Maskuro i hverdagen. Til slutt står de
  tre veiene fortsatt der – øvingsdokument, rundtur eller den illustrerte
  hurtigveiledningen. Alt kan hoppes over, og «Hjelp → Gjennomgå oppsettet
  på nytt» henter det tilbake.

- **F1 slår opp håndboken ved det passende kapittelet.** I hovedvinduet, i
  innstillingene (der alt etter side), i gjennomgangsvinduet og i
  språkforvaltningen; i etterredigeringsvinduet via Shift+F1, fordi F1 der
  alltid har vist hurtigtastene. Tidligere begynte hjelpen alltid øverst,
  ved 25 kapitler.

- **Nytt første håndbokkapittel: «I gang på tre minutter».** Fire trinn,
  mer trengs det ikke for ett dokument – på alle 18 språkversjoner.

- **En rundtur gjennom vinduet.** «Hjelp → Rundtur gjennom vinduet» kaster
  søkelys på ett betjeningselement etter det andre og skriver en setning
  ved siden av – i hovedvinduet åtte stasjoner, i
  etterredigeringsvinduet sju. I motsetning til den illustrerte
  hurtigveiledningen forklarer den vinduet du akkurat sitter foran.
  Avbryt når som helst med Esc.

- **Et øvingsdokument for risikofri utprøving.** Under ablagesflaten står
  nå «Åpne øvingsdokument» (også i hjelpemenyen). Det legger til et
  oppdiktet ark – navn, adresse, telefonnummer, IBAN, personnummer – og
  på arket står det samtidig hva du kan gjøre med det og hva du vil se
  etterpå. Ikke et ord av det tilhører et virkelig menneske; det første
  dokumentet du sender gjennom Maskuro, trenger altså ikke være et ekte.

- **«Bare se etter …» står nå ved siden av «Rens».** Det viser hvor
  personopplysninger ligger – fil, type og antall –, uten å endre eller
  skrive noe som helst. Den som har lagt inn et dokument, kan dermed se
  etter først, før han renser. Tidligere lå denne veien bare i
  Fil-menyen under «Gjennomgå mappe …» og gikk over en hel mappe i stedet
  for over de lagte filene.

- **Når ingenting ble funnet, står det nå med hva det kan skyldes.** For
  eksempel: I filen står det bilder, men «Kontroller også tekst i bilder»
  er av. Eller: Det innstilte språket passer ikke til det i dokumentet. Og
  hvis ingenting av dette foreligger, sier Maskuro også det.

- **Etterredigeringsvinduet ønsker deg velkommen første gang med tre
  setninger:** klikk sladder et ord, dra et område, til høyre står de
  erstattede verdiene. «Forstått» fjerner henvisningen varig; «Hjelp → Vis
  innføring på nytt» henter den tilbake.

- **Klikk på ord nå også på skannede sider.** Tidligere lot ord seg bare
  klikke der PDF-en hadde et tekstlag med seg – ved en skanning gikk det
  ikke, og i samme dokument kunne det variere fra side til side. Slike
  sider leses nå én gang av tekstgjenkjenningen; deretter klikker man ord
  som overalt ellers. Statuslinjen sier hva som akkurat skjer.

- **Sidefeltet er igjen en flate.** Det sluttet midt i kolonnen sin:
  Tittelstripe avkuttet, ved siden av en stripe i en annen farge, og den
  gjeldende siden var bare gjenkjennelig på en farget boks bak nummeret
  sitt. Nå fyller det kolonnen sin, kan dras bredere, og den gjeldende
  siden er fremhevet som en hel flis – med uforfalsket sideforhåndsvisning
  i seg.

- **Erstattede steder lyser blekt gult.** I sidevisningen er det dermed på
  et blunk synlig hvor noe ble erstattet – samme farge som
  sammenligningslupen bruker over originalen. Den røde rammen ved
  musepeking forblir uendret.

- **«Tilbakestill visning» i etterredigeringsvinduet** (menyen «Visning»).
  Den som har flyttet, løsrevet eller lukket sidefelt eller trefflisten,
  stiller dermed alt tilbake til der det sto ved første oppstart.

### Endret

- **Plassholderne er kortere.** Av `[SOZIALVERSICHERUNGSNR_1]` blir det
  `[SVNR1]`, av `[ORGANISATION_1]` et `[ORGA1]`, av `[EMAIL_1]` et
  `[MAIL1]`. Grunnen er ikke skjønnhet: En plassholder som er lengre enn
  verdien den erstatter, trenger linjen fra hverandre og finner i en trang
  tabellkolonne slett ingen plass lenger – der ble tidligere en svart
  stripe stående, og den forteller ingen lenger at det sto noe der. Der
  det finnes en vanlig forkortelse, står den (`[BLZ1]`, `[KFZ1]`,
  `[IBAN1]`). Resultater fra tidligere kjøringer forblir brukbare: Den
  gamle skrivemåten gjenkjennes fortsatt, og tilordningsfiler fra i går
  fungerer uendret.

- **Programikonet står nå likt overalt.** I menylinjen på Mac vises
  tidligere et ensfarget skjold som systemet selv fargela svart eller
  hvitt, i Windows-oppgavelinjen et grønt henholdsvis grått. Nå bærer hver
  linje det samme blå Maskuro-skjoldet. Hva som viser om utklippstavlen
  overvåkes, forblir like tydelig: Kjører overvåkingen, sitter et grønt
  punkt på skjoldet; hviler den, står det samme skjoldet blekt der. Også i
  de minste størrelsene står nå begge sladdestriper i skjoldet – tidligere
  viste oppgavelinjen der bare én.

- **Ansikter gjenkjennes med en modell hvis treningsbilder ble til med
  samtykke.** Levert nå er MediaPipe BlazeFace (Apache-2.0); den tidligere
  detektoren forblir innebygd og omkoblbar, men leveres ikke lenger med,
  fordi treningsopprinnelsen ikke er avklart fullstendig. For
  gjenkjenningen endres ingenting: Ved 324 portretter og 143 bilder uten
  ansikt finner den nye versjonen like mye ved like få feilgrep og bruker
  en tredjedel av tiden.

- **OCR er sikkerhetsankeret for den sterkeste PDF-garantien.** Den
  vanlige PDF-kjøringen bruker den og genererer den fullstendige
  minimalombyggingen. Den som uttrykkelig slår av OCR, får den mer
  kompatible objektveien; grensesnitt, sluttmelding og håndbok sier nå
  uttrykkelig at denne veien ikke gir samme arkitektur mot ukjente skjulte
  PDF-kanaler.

- **Salgsporten sperrer nå også den tidligere vedlagte YuNet-modellen.**
  MIT-lisensen til den eksakte vekten forblir dokumentert, men er ikke
  tilstrekkelig for den offentlig synlige treningsdatakjeden via WIDER
  FACE som konservativ produktfrigivelse. Før salg kreves en skriftlig
  avklaring eller utskifting mot en modell med en solid kommersiell data-
  og vektkjede.

- **Firma- og organisasjonsnavn fjernes nå av seg selv.** Tidligere ble de
  stående så lenge man ikke uttrykkelig krevde det. Det var feil standard
  for et forretningsbrev: Den som videresender et tilbud, vil ikke lese
  oppdragsgiveren i det. «Kranzbichler Handels GmbH», «Institut für
  Bauphysik» og lignende behandles derfor som et navn. Den som trenger det
  annerledes, slår det av i vinduet; på kommandolinjen heter bryteren nå
  `--ohne-organisationen`. Den gamle `--mit-organisationen` godtas fortsatt
  og gjør ikke lenger noe, slik at eksisterende skript og snarveier ikke
  brytes. Dato- og pengeangivelser forblir uendret unntatt.

- **Sladding har nå tre former i stedet for to avkrysninger.** «Ord»,
  «Hele linjen» og «Fri ramme» står som ett valg ved siden av hverandre –
  det gjelder alltid nøyaktig ett. Tidligere var «Tekstlinjer» og «Hele
  linjen» to uavhengige brytere som begge kunne være trykket, og den frie
  rammen var overhodet ingen knapp, men den avslåtte tilstanden til den
  første. De tre står synlig ved verktøyet sitt og er grå så lenge et
  annet verktøy er valgt.

### Forbedret

- **Det første dokumentet er ferdig rundt ett sekund raskere.** Før
  rensingen begynner, fastslår Maskuro dokumentets språk – og hentet til
  dette tidligere ordlistene til alle 48 språk via en vei som lastet mye
  mer enn ordene. Det var omtrent halvparten av ventetiden frem til det
  første resultatet. Selve gjenkjenningen er uendret: Den ser de samme
  ordene som før, bare raskere. Hvert ytterligere dokument var uansett
  ikke berørt av dette.

- **Dokumenter med svært lange avsnitt kontrolleres raskere.** Ved et
  avsnitt uten linjeskift leste Maskuro det på nytt i sin helhet for hvert
  funnet sted; nå holder det med én gang. Jo lengre avsnittet, desto
  større forskjellen – målt rundt en syvendedel mindre regnetid. Ved
  resultatet endres ingenting.
### Rettet

- **Med et firma forsvant ofte halve setningen med.** Sto et firmanavn i
  løpende tekst – «Informasjon om Gottwald GmbH & Co KG», «… (AGB) fra
  Musterbetriebe GmbH» –, ble ikke bare navnet sladdet, men alt foran til
  setningsbegynnelsen. Teksten ble dermed uleselig, og det så ut som om
  det var sladdet vilkårlig. Firmanavn som selv bærer et «for» eller «og»
  («Bank für Arbeit und Wirtschaft AG»), forblir dermed uendret
  fullstendige.

- **Firmanavn ble stående i brevhoder, selv om de ble fjernet i teksten.**
  I et tilbud sto firmaets sete fortsatt leselig i brevhodebildet – samme
  sted som Maskuro hadde sladdet i løpende tekst; i den søkbare teksten i
  resultatet sto det til og med usynlig videre der. Det som en gang ble
  fjernet, fjernes nå også der det bare foreligger som bilde. Dette virker
  også for logoer og ordmerker som er tegnet som grafikk.

- **macOS spurte ved hver oppstart om skjermopptak**, selv om tillatelsen
  for lengst var gitt. Henvisningen ved oppstart prøvde et opptak, og
  nettopp det henter systemdialogen frem på skjermen. Nå spør bare Maskuro
  selv ved oppstart, og bare én gang; systemet spør først når du virkelig
  tar et skjermbilde.

- **Tekniske saksbegreper ble tatt for steder og firmaer.**
  «Einspeisepunkt», «Flachdach», «Verteileranlage», «Meldersockel» og
  dusinvis lignende ord forsvant fra tilbud og ytelsesbeskrivelser.
  Maskuro gjenkjenner dem nå på grunnordet: Det som ender på «-anlage»,
  «-punkt» eller «-kanal», er en sak. Stedsnavn som Berlin, Melk eller
  Wieselburg har ikke et slikt grunnord og forblir uberørt – likeledes
  adresser som «Der Graben» eller «Alter Markt».

- **Japanske, koreanske, kinesiske, thailandske og gujarati-dokumenter
  kunne krasje programmet.** Inneholdt et dokument på ett av disse fem
  språkene en internettadresse uten «https://» foran, avbrøt rensingen
  med en intern feil – ved åpent vindu gikk dermed også det øvrige
  arbeidet tapt. Alle førtiåtte valgbare dokumentspråk kjører nå gjennom;
  mangler frekvensordboken for ett språk, forblir angivelsen i tvilstilfelle
  stående i stedet for å forsvinne.

- **Feltmerkinger beskyttet bare på tysk og engelsk.** «Reference» ble
  stående, det italienske «Riferimento» og det portugisiske «Referência»
  ble fjernet som stedsangivelse – samme feltnavn, samme linje, annet
  resultat. Den som ikke arbeider på engelsk, var dermed dårligere stilt.
  Maskuro kjenner nå de samme feltnavnene på alle elleve vedlikeholdte
  språk.

- **«Hent tilbake original» hentet for mye tilbake på skannede sider.** En
  ramme over en sladdet linje i en adresseblokk avdekket **hele blokken**
  igjen – og siden ble stående i stykker: Striperester sto fortsatt igjen,
  som enkelte ordender stakk ut av. Grunnen var at understandende striper
  på en rastrert side støter mot hverandre og derfor gjaldt som én eneste
  flate. Tilbakehentet blir nå nøyaktig linjen som rammen peker på;
  nabolinjene forblir sladdet, og stripen på den trufne linjen forsvinner
  helt.

- **Mengdeangivelser i posisjonslister ble tatt for adresser.** I en linje
  som «1.4 Kabelgraben 100,00 m» ble «Kabelgraben 100» erstattet som gate
  med husnummer. Slike linjer blir nå stående; ekte adresser – også
  «Hauptplatz 1, 3250 Wieselburg» – gjenkjennes uendret.

- **Foran et firmanavn forsvant halve setningen.** Av «Avtale mellom
  firmaet Gottwald GmbH & Co KG og oppdragsgiveren.» ble det
  «[ORGANISATION_1] og oppdragsgiveren.» – setningsbegynnelsen var borte,
  og med den henvisningen til hva det gjaldt. Nå faller bare selve
  firmanavnet. Der slektsordet hører til navnet («Deutsche Bank AG»,
  «Universität Wien»), forblir alt som før.

- **I en protokoll ble talere stående der navnet samtidig er et yrke.**
  «Bauer:», «Koch:», «Weber:» foran en ordmelding ble oversett, «Gruber:»
  ved siden av ikke – Maskuro trengte tidligere minst ett gjenkjent navn i
  skrivet for i det hele tatt å lese linjene som ordmeldinger. Bærer
  dokumentet en overskrift som «Ergebnisprotokoll» eller «Niederschrift»,
  er det nå nok. Merkelinjer («Achtung: …», «Hinweis: …») forblir urørt.

- **En feltmerking forsvant sammen med verdien sin.** Av «Projekt:
  Sanierung und Erweiterung Gemeindezentrum» ble det én eneste
  plassholder – også ordet «Projekt:» var borte, og dermed henvisningen
  til hva som hadde stått der. Merkinger blir nå stående. Der en merking
  hører til angivelsen og bærer betydningen dens («Durchwahl 214»),
  endres ingenting.

- **Den maksimale gjenkjenningen ryddet ikke bort saksbegreper.**
  «Flachdach», «Einspeisepunkt», «Elektrotechnik» og lignende fagord ble
  også med påslått KI-nivå erstattet som sted eller firma – KI-en fikk
  aldri nettopp disse funnene forelagt til vurdering. Den kontrollerer dem
  nå med: På et korpus av anbuds- og kontraktstekster forsvinner dermed
  alle 27 feilgrep, uten at ett eneste ekte funn blir stående. Navn,
  firmaer og steder gjenkjennes uendret.

- **Slektsord for innretningstyper ble tatt for organisasjoner.** I en
  kontraktstekst forsvant «Hochschulen und Universitäten», «Staatliche und
  private Schulen», «Akademische Lehrkrankenhäuser», «Bildungseinrichtung»
  og «Zulieferfirmen» – ord som ikke navngir et bestemt sted, men en type
  sted. De blir nå stående. Står det et egennavn foran («EU-Kommission»),
  erstattes det fortsatt, og firmanavn omfattes overhodet ikke av regelen.

- **Navn i lister falt bare når de var vanlige.** I en deltaker- eller
  fremmøteliste under en kolonneoverskrift «Navn» ble «Anna Huber» og
  «Thomas Müller» fjernet, «Wójcik Aleksandra» eller «Kücükgöl Sinan»
  derimot ikke – samme linje, samme oppbygning. Den som bærer et sjeldnere
  navn, var dermed dårligere beskyttet. Nå avgjør kolonneoverskriften: Det
  som står under «Navn», er et navn. En posisjonsliste med saklig
  kolonneoverskrift forblir urørt.

- **Et telefonnummer bak «Durchwahl» ble kuttet midt i to.** Av «Durchwahl
  0732 771190» ble det «[DURCHWAHL_1] 771190» – den andre halvparten av
  nummeret forble leselig. Nå faller hele nummeret helt, og merkingen blir
  stående. Et ekte internnummer («Durchwahl 214») erstattes uendret
  sammen med merkingen.

- **Enkelte PDF-er lot seg overhodet ikke lenger rense.** Kunne en
  fargeprofil eller metadataene i et bilde ikke bevisbart fjernes, avbrøt
  kjøringen uten resultat – berørt var vanlige forretningsdokumenter som
  vilkårsider, kravspesifikasjoner og anbud. Slike filer renses nå, og en
  advarsel nevner stedene som forble åpne: De kan bære en enhets-,
  produsent- eller opptaksidentifikasjon. Originalen forblir som alltid
  uendret.

- **Kontraktroller ble tatt for personer.** «Bieter», «Verbraucher»,
  «Mieter», «Käufer», «Auftraggebers» og rundt førti andre rolleord ble
  erstattet der de sto uten artikkel – i kontraktoverskrifter,
  tabellkolonner og underskriftslinjer. En kontraktstekst uten en eneste
  personopplysning ble dermed stedvis uleselig. Disse ordene blir nå
  stående. Står det en personhenvisning ved siden av – en tiltaleform, et
  fornavn, et feltord som «Ansprechpartner» –, erstattes fortsatt: «Herr
  Bieter» og «Frau Käufer» er navn. Vanlige familienavn som samtidig er
  yrker (Bauer, Richter, Koch), omfattes overhodet ikke av regelen.

- **En forkortet skrevet gate ble oversett når husnummeret klistret seg
  direkte til punktumet.** «Schlesischestr.31» gjaldt ikke som adresse –
  og fordi postnummeret ved siden av henter sitt feste fra adressefunnet,
  ble også det stående. I resultatet var adressen av gate og postnummer
  igjen sammensettbar, og det bare på enkelte sider av samme dokument.
  Begge faller nå sammen. Sakbetegnelser med tilhengt tall («Kabelrinne200»)
  forblir urørt.

- **En adresse over to linjer ble trukket sammen til én eneste
  plassholder.** Sto postnummeret over gaten i en adresseblokk, forbandt
  Maskuro begge linjene til ett funnsted: I resultatet forsvant
  linjeskiftet, og postnummeret ble stående leselig foran. Nå finnes og
  erstattes hver linje for seg, og skriftbildet bevares. Samme årsak dro
  av og til også etternavnet fra linjen over inn i adressen.

- **Den maksimale PDF-veien overtar ikke lenger originalobjekter.** Med
  påslått tekstgjenkjenning bygger Maskuro hver side fullstendig om fra
  det synlige PDFium-bildet. Inn i den nye minimalfilen kommer bare denne
  bildesiden og et nyopprettet, til OCR-teksten begrenset søkelag – ikke
  det fremmede objekttreet med kommentarer, vedlegg, handlinger, lag,
  metadata, fargeprofiler eller private nøkler. Dette gjelder også
  innhold i kommentarutseender, mønstre, Type-3-skrifter, formobjekter og
  softmasker. Kildefilen forblir urørt.

- **Ansikter og koder i nøstede PDF-grafikker ble oversett.** Begge
  detektorene ser nå i tillegg det fullstendige gjengitte sidebildet.
  Dermed når også portretter og QR-/strekkoder i kommentarer, mønstre,
  Type-3-glyfer og transparensmasker detektorene; gjenkjente områder
  gjøres – om påslått – ukjennelige før minimalombyggingen. Selve
  deteksjonen forblir feilbarlig.

- **En manglende OCR-motor endte ved PDF-er med en intern feil.** Den
  maksimale kjøringen avbrytes nå kontrollert og uten målfil, i stedet
  for å levere en ufullstendig eller ukontrollert fil.

- **Flere ekte kontakt- og forretningsverdier falt gjennom mens sakstekst
  ble erstattet.** Navnefelt over linjeskift, bank- og firmanavn,
  rettsformer, merkede identifikasjonsnumre, fødselsdatoer samt
  telefon-, URL- og IBAN-grenser er strammere kontrollert. Samtidig blir
  land i sakstekst, rolle- og slektsord, artikkel-/normkoder, tallkolonner
  og vanlige forkortelser hyppigere urørt.

- **Blandede og dreide OCR-linjer ble feillest.** Usikre loddrette ord
  leses nå lokalt oppreist på nytt; tekniske latinske verdier i
  ikke-latinsk tekst får et uavhengig engelsk vitne. Et frittstående usikkert
  enkeltsiffer rettes bare når to tette sifferrekker stemmer overens.
  Polske rettsformer i OCR-formen «sp. z 0.0.» leses i lukket kontekst som
  «sp. z o.o.».

- **Bildemålingen kunne overse delvis synlige restverdier.** Den
  kontrollerer nå overlappende lokale utsnitt, skiller hvit
  plassholderskrift på en svart stripe fra originalglyfer og overfører
  rå bildebokser også til dreide, nylig gjengitte minimal-PDF-er. Det
  faste syntetiske hovedkorpuset når dermed 1 392/1 392 fjernede
  målangivelser ved 0 falske treff og 0 behandlingsfeil. Dette er et
  korpusbevis, ikke et generelt 100 %-løfte.

- **Ikke-kommersielle språkmodeller tilbys ikke lenger.** De seks
  italienske og greske spaCy-variantene under CC BY-NC-SA 3.0 er fjernet
  fra katalog, nedlasting og lastevei; også allerede eksisterende
  modellmapper ignoreres. Begge språkene bruker i stedet den
  MIT-lisensierte flerspråksmodellen.

- **Navnet under «Ansprechpartner» ble bare halvveis fjernet.** Står
  merkingen alene på en linje og under den «Etternavn Fornavn», ble
  fornavnet stående så snart det samtidig var et vanlig ord – av «Mayer
  Roman» ble det «[NAME_1] Roman». Slike linjer tas nå helt. En avdeling
  på samme sted («Technischer Innendienst») forblir fortsatt urørt.
  Rettet i sideveien: «Ansprechpartner» talte overhodet ikke som
  navnefelt, selv om «Kontaktperson» alltid har gjort det.

- **Firmanavnet uten rettsform ble stående når et bransjeord sto
  imellom.** «Kranzbichler Handels GmbH» ble fjernet, det nakne
  «Kranzbichler» tre avsnitt senere ikke – ved «Kranzbichler GmbH»
  derimot ja. Nå griper begge deler. Vanlige ord er unntatt fra dette:
  «Deutsche Bank AG» gjør ikke «deutsche» i teksten til et firma.

- **Samme verdi het i samme dokument én gang navn og én gang sted.**
  «Anna Musterfrau … Musterfrau» ga «[NAME_1]» og «[ORT_1]» – på det andre
  stedet mangler fornavnet, og uten det ble det til et sted. Fjernet var
  begge deler, men det leste seg som to forskjellige ting. En verdi
  beholder nå betegnelsen fra sin første forekomst.

- **Datoangivelser ble ikke lenger fjernet.** En dato helt av sifre
  («01.03.2026») falt siden forrige versjon gjennom en kontroll ment for
  navn, og ble stående i dokumentet – også i driftsmodusen «forskyv», og
  uten linje i kontrollrapporten. Berørt var bare den som uttrykkelig
  hadde slått på datoangivelser.

- **Land og kontinenter sladdes ikke lenger.** «Leveransen går til USA»,
  «markedssvakhet i Asia», «normen gjelder i Romania» – slike angivelser
  sier ingenting om en person og blir nå stående. Hører landnavnet
  derimot til en adresse eller står det bak en merking som «Bosted» eller
  «Fødested», fjernes det fortsatt. **Byer er ikke berørt** – «Jeg er
  akkurat i Bilbao» forblir en angivelse om en person og sladdes fortsatt.

- **Forkortede ord ble til nettadresser.** Står det i teksten «hhv. tyske»
  eller «inkl. den», leverer enkelte PDF-er punktumet uten mellomrom –
  det ble til «hhv.de» henholdsvis «inkl.de», en gyldig adresse med
  landsendelse, og den ble fjernet. Slike ordpar blir nå stående. Ekte
  adresser er ikke berørt, heller ikke uten «www.» foran.

- **Tallkolonner fra regnskaper ble sladdet som telefonnumre.** I
  årsrapporter og pristabeller står forrige og gjeldende år ved siden av
  hverandre – «64.518 65.133». Dette gjaldt som ett telefonnummer og ble
  fjernet, likeledes tallområder som «12200-23200» og en dato med
  påfølgende tall. Slike tall blir nå stående. Omvendt gjenkjennes et
  ekte telefonnummer sikrere: Merkingene «Telefon», «Fax», «Mobil»,
  «Durchwahl» og deres motstykker på de andre grensesnittspråkene teller
  nå med – tidligere gjenkjente programmet der bare de engelske ordene.

- **Navn i en nummerert tabell ble stående.** En deltakerliste eller
  personaltabell i den vanlige formen – kolonneoverskrift, under
  «1.1 Auersperg Bernhard Montage 03.03.2026» – ble overhodet ikke
  renset: Slike linjer så ut som posisjonslisten i et tilbud, der
  saksbegreper skal bli stående. Bærer kolonneoverskriften en
  personmerking («Name», «Nachname», «Surname» …), gjelder linjene under
  nå som navn. Posisjonslister forblir uendret spart – også når det står
  «Sachbearbeiter:» i brevhodet.

- **Fra ett navn ble det av og til to plassholdere ved siden av
  hverandre.** Sto et etternavn også alene i dokumentet, erstattet
  etterbehandlingen på et sted som «Anna Musterfrau GmbH» først
  etternavnet og deretter fornavnet – i resultatet så det ut som to
  forskjellige personer. Nå vinner det lengste kjente navnet.

- **Oppdiktede verdier sto i ingen tilordning.** Den som hadde valgt
  «Dikt opp verdier», fikk et resultat der «Anna Musterfrau» var blitt til
  «Greta Mayrhofer» – i tilordningen sto det ingenting om det, så snart
  det i samme dokument også fantes bare én anonym erstatning. Dermed lot
  ingen oppdiktet verdi seg hente tilbake, og tilordningsfilen fortidde
  erstatningen. Det mest betenkelige var det tredje: Den som leser
  resultatet, ser et troverdig navn og har ingen holdepunkt for at det er
  oppdiktet. Nå står hver erstatning i tilordningen.

- **Tilordningen kalte sladdet «erstattet».** En e-post deler en
  tilordning med vedleggene sine, og vedlegget kan sladdes mens
  e-postteksten bærer en plassholder. I tilordningen sto det da det samme
  for alle tre stedene – «erstattet» –, og tilbakehentingen søkte i
  vedlegget en plassholder som ikke finnes der: Stripen ble stående. Nå
  står det per funnsted hva som virkelig skjedde der, og begge vedlegg
  kommer tilbake.

- **Verdier som bare sto i et bilde, lot seg ikke hente tilbake.** I
  treffpanelet sto de dobbelt – én gang som plassholder som ikke fantes
  noe sted i dokumentet («Plassholderen ble ikke funnet i dokumentet»),
  én gang som sladdet sted. Den første linjen var ren bokføring og er
  forsvunnet.

- **Sladdede verdier lot seg bare hente tilbake én gang.** Står samme
  verdi flere steder, henter ett klikk alle tilbake – de øvrige linjene
  ble likevel stående i treffpanelet, og det neste klikket på dem meldte
  «Ikke entydig». De forsvinner nå med.

- **Tilbakehentinger manglet i kontrollprotokollen når læringsmodus var
  av.** Den som gjenopprettet en tilbakehentet verdi i
  etterredigeringsvinduet, fant ikke prosessen igjen i kontrollprotokollen
  så snart læringsspørsmålene var slått av – dokumentasjonen hang på en
  bryter som bare gjelder regelforslagene. Ved påslått kontrollprotokoll
  spørres det nå uavhengig av dette om grunnen, og linjen skrives.

- **Inndratte filer forble urensede – og ble ikke engang meldt.** Den som
  drar en fil inn i et dokument, i stedet for å sende den som vedlegg,
  legger Word eller PowerPoint den fullstendig inn i dokumentet. Den sto
  deretter uendret i resultatet, med sitt opprinnelige filnavn og
  lagringssti – og disse bærer i praksis ofte selv et navn. Slike filer
  renses nå som resten av dokumentet.

- **Og der det ikke går, sier Maskuro fra.** Ligger det i et innebygd
  objekt et gammelt format (Word 97, Excel 97) det ikke finnes rensing
  for, vises nå en ADVARSEL-melding med filnavnet. Tidligere ble den
  stilltiende videreformidlet uendret.

- **Opprevne ord og forkortelser ble tatt for navn.** Er et ord delt ved
  linjeslutt i en PDF, kommer det ved utlesning av enkelte filer ut et
  bruddstykke – «Jahresent… gelts», «Gewerbli…». Slike bruddstykker,
  sammenklistrede ord («TürverschlussmitV») og nakne forkortelser («JY»,
  «FFB») ble sladdet som om de var navn. De blir nå stående. Et navn med
  samme delingsskade sladdes fortsatt, så lenge det følges av en
  tiltaleform – og navn som fra naturens side bærer stor bokstav inni
  ordet (McKenzie, MacDonald, LeBlanc), er uansett ikke berørt av dette.

- **Måleangivelser og måneder gjaldt som adresse.** I tekniske dokumenter
  ble «2000 Lux», «1200 Mbit», «1500 Watt», «5308 Platz» og «2022 Mrz»
  sladdet – fire sifre og et stort forbokstavsord så ut som et postnummer
  med sted. Et postnummer teller nå bare når også et adressesignal
  finnes: en landkode, en feltmerking, linjebegynnelsen, en gate på
  linjen over eller et sted som også språkgjenkjenningen ser der. I fem
  ytelsesbeskrivelser forsvinner dermed 14 feilaktige sladdinger, uten at
  én ekte adresse blir stående.

- **Den mer nøyaktige gjenkjenningen erstattet for mye.** Det
  tilkoblingsbare nivået «mer nøyaktig gjenkjenning» tok i tyske
  forretningsdokumenter saksbegreper for navn og steder –
  «Photovoltaikanlage», «Einspeisepunkt», «Flachdach», «Personaleingang» –
  og sladdet firmabetegnelser fra løpende posisjonslister. Grunnen var en
  skjerming: Treffene deres var unntatt fra kontrollene som gjenkjenner en
  posisjons- eller registerlinje. Denne skjermingen gjelder nå bare
  flerdelte navn, som nivået finnes for – «Anna Huber» i en registerlinje
  forblir altså gjenkjent, et enkelt saksord i en posisjonslinje faller
  bort. I et teknisk anbud halverer dette nivåets feilaktige sladdinger,
  uten at ett navn går tapt.

- **Diagrammer brakte sine fullstendige kildedata med – ukontrollert.**
  Den som setter inn et diagram i Word eller PowerPoint, legger programmet
  tabellen det ble beregnet fra som egen fil i dokumentet. Synlig er bare
  de få tallene i diagrammet; i tabellen står hele listen, inkludert
  linjene som ikke engang forekommer i diagrammet. Denne tabellen ble
  tidligere videreformidlet uendret. Den renses nå med, med de samme
  plassholderne som resten av dokumentet.

- **Det samme for innebygde objekter i OpenDocument-filer** (ODT, ODS,
  ODP): Et innsatt diagram eller en innsatt tabell ble stående urørt.

- **Word-dokumenter: fotnoter og sluttnoter ble ikke renset.** Teksten
  deres sto fullstendig igjen i resultatet – også navn, adresser og
  kontonumre. Berørt var hvert Word-dokument med en fot- eller sluttnote.
  Likeledes ble en autotekst-byggekloss som reiser usynlig med dokumentet,
  urørt.

- **Word: angivelser i nedtrekkslister, kommentarer og bildebeskrivelser.**
  Oppføringene i et valgfelt (synlig først ved utfolding), forfatteren av
  en kommentar, beskrivelsen av en tegning og adressen bak en
  henvisningskommando sto fortsatt i resultatet.

- **Excel: pivot-tabellen bar utgangsdataene en gang til.** En arbeidsbok
  med en pivot-tabell bevarer i den en fullstendig kopi av de analyserte
  linjene – usynlig, men i filen. Denne kopien ble tidligere stående
  uendret, selv om alt var erstattet i selve arket. Berørt var hver
  analyse som ble videreformidlet med en pivot-tabell.

- **Excel: samtalekommentarer og forfatterne deres.** Teksten i en
  kommentar av den nyere byggeformen og registeret over kommentatorer –
  visningsnavn og påloggingsidentifikasjon, i firmaer som regel
  e-postadressen – sto fortsatt i resultatet. Det samme registeret i
  Word-dokumenter likeledes.

- **Selvdefinerte dokumentegenskaper i Word og Excel.** Felt som
  «Mandant» eller «Aktenzeichen», som et advokatkontor gir sine maler med,
  ble tidligere ikke renset. De er ikke synlige i noen visning og følger
  likevel med hver kopi.

- **Tabeller (ODS): nedtrekkslisten til en celle.** Som i Excel siden
  forrige versjon renses det nå også i OpenDocument-tabeller det som
  vises ved utfolding av en celle. Referanser til andre celler forblir
  urørt av dette, slik at listen fortsatt fungerer.

Alle disse stedene lar seg hente tilbake som vanlig via tilordningen.

- **Outlook-meldinger: en skadet fil avsluttet rensingen hardt.** Bestemte
  ødelagte `.msg`-filer førte til et avbrudd i stedet for en melding; de
  leses nå så langt de er leselige.

- **Tilordningsfilen er nå bare lesbar for deg.** Den inneholder
  originaldataene i klartekst og lå tidligere med de vanlige
  rettighetene ved siden av resultatet – på en felles lagring kunne dermed
  hvem som helst åpne den. Ved selve det rensede resultatet endres
  ingenting; det skal jo videreformidles.

- **Nedlastede språkmodeller kontrolleres grundigere før utpakking.** En
  manipulert pakke – for eksempel fra en firmafrigivelse som betjener
  flere arbeidsplasser – kunne ved utpakking legge filer utenfor den
  tiltenkte mappen. Ved den vanlige nedlastingen endres ingenting.

- **Ta et skjermbilde – og det renses med det samme.** Med
  `Ctrl+Shift+B`, via «Fil → Ta skjermbilde …» eller via symbolet i
  oppgavelinjen drar du en ramme over skjermen. Det som ligger inni, går
  deretter samme vei som enhver annen fil: Tekstgjenkjenningen leser
  skjermteksten, navn, adresser, telefonnumre og e-postadresser sladdes,
  og deretter står bildet åpent i redigeringsprogrammet, der du med en
  ramme kan ettersladde det som ble oversett. Det rensede bildet havner
  på skrivebordet (eller i den innstilte utdatamappen din); det **rå**
  opptaket lagres ikke noe sted og slettes ved avslutning.
  Tekstgjenkjenningen slås på for denne kjøringen, selv om den ellers er
  av – ved et bilde ville det ikke være noe å finne uten den. På Mac
  spør systemet ved første gang om tillatelsen «Skjermopptak».

- **På bilder kan man nå tegne: rektangel, ellipse, pil, tekst og
  nummererte trinnmerker.** I seks farger og tre strektykkelser, valgbare
  med tastene 1 til 5. Dette er tenkt for skjermbilder og veiledninger:
  vise hva som gjelder, uten å åpne et andre program for det. Angre og
  etterjustering ved håndtakene gjelder som for enhver stripe – en
  anmerkning kan altså flyttes og trekkes opp etter at den er satt.
  **Tegning er uttrykkelig ikke sladding.** Et tegnet rektangel er en
  ramme, ikke en stripe: Det som står under, forblir leselig og går ut
  med filen. Til fjerning av angivelser er fortsatt «Sladd» og «Piksler»
  der; tegneverktøyene står derfor i en egen linje i verktøylinjen, og
  henvisningslinjen sier det så lenge ett av dem er valgt.

- **Det redigerte bildet går med ett klikk til utklippstavlen.** «Kopiér
  bilde» i redigeringsprogrammet (eller `Ctrl+C`) legger det slik det
  fremstår – å lime inn er nok for å bringe det inn i en melding eller
  e-post. Dermed er veien fra tastetrykk til chat fire trinn lang og
  trenger ingen mappe.

- **Dertil en tekstmarkør, skygge og overganger.** «Uthev» farger en
  flate uten å dekke den – innholdet under forblir leselig, og nettopp
  det skiller den fra stripen. «Skygge» hever en anmerkning fra urolig
  bakgrunn, «Overgang» lar fargen tone ut i dragretningen; begge deler
  gjelder for alle seks tegneverktøyene.

- **Rettet før det rammet noen:** Den nye verktøylinjen ville sett nesten
  tom ut for hver den som allerede har brukt Maskuro – den husket
  vindusinndelingen stammet fra tiden før og ville ikke gitt den plass.
  En utdatert inndeling forkastes nå; redigeringsvinduet står da
  engangsvis i sin grunninndeling.

- **Ditt eget skjermbilde kan slås av.** Den som er vant til Greenshot,
  ShareX eller utklippsverktøyet, slår under «Innstillinger → Program» av
  «Ta skjermbilde med Maskuro». Maskuro registrerer da hurtigtasten ikke
  engang – den forblir ditt eget verktøys –, og omstillingen gjelder
  umiddelbart, uten omstart. Rensing av et slik tatt bilde er fortsatt
  mulig: Ctrl+V henter det fra utklippstavlen inn i vinduet.

## 0.10.37-alpha.20260821 – 21. august 2026

### Nytt

- **Ved anonymisering bærer nå hvert funnsted sitt eget nummer.** Tidligere
  het alle personer `[NAME]`, alle steder `[ORT]` – dermed lot det seg ikke
  lenger si hvilket sted som hørte til hvilken verdi, og det var ingenting
  å hente tilbake. Nå teller numrene videre per forekomst: Samme navn står
  tre steder som `[NAME_1]`, `[NAME_3]` og `[NAME_7]`. I dokumentet er det
  dermed fortsatt ikke synlig hvilke steder hører sammen – men med
  tilordningsfilen lar hvert enkelt seg hente tilbake. Tilordningsfilen er
  derfor igjen valgbar også ved anonymisering; oppbevar den atskilt fra
  resultatet.
- **Måneder, ukedager, valutaer, enheter og firma-rettsformer på alle 48
  dokumentspråk gjelder ikke lenger som navn eller steder.** Kalender- og
  enhetsnavnene kommer fra Unicode CLDR (generert, ikke skrevet),
  rettsformene fra landenes selskapsrett – også flerords («sp. z o.o.»,
  «Pty Ltd») og forankstilte («株式会社»). Der et månedsnavn samtidig er et
  fornavn (Juli, August, May), avgjør byggeformen: med dag eller år ved
  siden av en dato, ellers et navn. I tillegg tiltaleformer og titler, hele
  hilsenformler, dokumenttyper og gategrunnord for 28 språk med egen
  språkmodell, lovforkortelser (DSGVO, UStG, ABGB, § 6 Abs 1 Z 27 UStG)
  samt språknavn som feltverdi («Sprache: Deutsch»). Listene står under
  «Hjelp → Ordlister …».
- **India: adresse og PIN-kode gjenkjennes** – «15 गांधी मार्ग», «नई
  दिल्ली 110001» likeledes som «15 Gandhi Marg, New Delhi 110001».
  Landpakken India kjente tidligere bare identifikasjonsnumre; i
  hindi-dokumenter ble adresser derfor stående.
- **Hver renset kontorfil åpnes en gang til som pakke før overlevering.**
  Et tekstutdrag merker ikke når Word, Excel eller LibreOffice ville avvist
  filen (dobbel oppføring, revet XML, en manglende del). Og det telles mot
  originalen det en rensing aldri får endre: sider i en PDF, ark, linjer og
  celler i en tabell, lysbilder i en presentasjon. Slår prøven ut, vises en
  ADVARSEL-melding i resultatet og i kontrollrapporten – originalen
  forblir uendret.
- **Også automatikken sladder hele feltet.** I sladdemodus dekker stripen i
  korte linjer – adresseblokk, tabellcelle, hodedata – hele linjen i stedet
  for bare den funnede verdien: En stripe i ordlengde avslører hvor langt
  ordet var. Merking og beløp ved siden av blir stående, og løpende
  tekstlinjer (lengre enn halve tekstbredden) sladdes fortsatt ordnøyaktig,
  slik at et navn midt i setningen ikke gjør hele setningen svart.
- **Tilbakehentet ser igjen ut som i originalen.** «Hent tilbake original»
  og «Angre erstatning» i PDF-redigeringsprogrammet skriver nå området
  eksakt tilbake fra kildefilen – samme skrift, samme størrelse, samme
  farge og posisjon, på en skanning samme bildepunkter. Frem til da ble
  teksten satt inn på nytt i en erstatningsskrift og så gjenkjennelig
  gjenoppbygd ut. Stripen fra en tidligere sladding forsvinner nå helt, i
  stedet for å bli malt hvit over – en farget cellebunn i en tabell
  bevares. Dette gjelder også på dreide sider, for tekst fra innebygde
  skjemaobjekter og for **utfylte skjemafelt**: På den for dette rastrerte
  arbeidskopien kommer utsnittet fra den nylig gjengitte originalsiden
  tilbake – også der ingen tekstlag kjenner feltverdien. Også
  **erstattede bilder** i PDF-en kommer slik tilbake – pikselert, uklart
  eller helt fjernet, helt eller bare det dratte utsnittet. Bare der
  kildefilen ikke lenger ligger ved siden av resultatet, forblir det ved
  den tidligere veien.
- **Sladdede og uten erstatning fjernede verdier lar seg også hente tilbake
  i Word, Excel, PowerPoint og OpenDocument.** Tidligere trengte
  tilbakehentingen der en plassholder i teksten – en stripe eller et hull
  hadde ingen tilbakevei. Nå tilbyr treffpanelet linjene «sladdet» og
  «fjernet», så snart den uberørte kildefilen ligger ved siden av
  resultatet: Maskuro sammenligner resultatet med originalen og setter
  verdien inn igjen på stedet til stripen eller hullet – med formatering,
  et delt løp blir helt igjen. Gjelder likeledes for tekst, HTML, e-post og
  Office-vedleggene til en e-post; bærer e-postteksten en plassholder og
  vedlegget en stripe, hentes begge tilbake i ett trekk.
- **Også PDF-vedlegg til en e-post eller Outlook-melding lar seg hente
  tilbake** – plassholdere (nummererte og anonyme), striper og uten
  erstatning fjernet. Uten lerret kommer stedet fra det opprinnelige
  vedlegget; verdien kommer tilbake glyfnøyaktig, i originalens
  leserekkefølge.
- **Maskerte verdier lar seg hente tilbake** – i PDF og i tekstvisningen.
  En maske («**** **** **** **** 3201») er aldri entydig, to numre bærer
  den samme; derfor tar tilbakehentingen aldri den ordrette veien, men
  spør originalen hvilken verdi som sto på dette stedet. Tidligere var
  disse linjene overhodet ikke betjenbare i treffpanelet.
- **Innebygde bilder i Word, Excel, PowerPoint og OpenDocument lar seg
  hente tilbake.** En sladdet verdi i bildet kommer tilbake via
  panellinjen sin – Maskuro leser originalbildet og henter nettopp dette
  stedet; et uklart, fjernet eller med ansikter og koder behandlet bilde
  henter den nye oppføringen «Hent tilbake innebygde bilder» i
  Rediger-menyen som helhet fra kildefilen – også gjennom
  Office-vedleggene til en e-post eller Outlook-melding. Et bilde som selv
  henger som vedlegg og ble sladdet via tekstgjenkjenning, kommer
  likeledes tilbake via panellinjen sin.
- **Oppdiktede verdier lar seg hente tilbake i tekstvisningen.** Tidligere
  meldte panelet der «Ikke entydig». Nå søker tilbakehentingen verdien i
  originalen og krever på samme sted i resultatet nøyaktig den oppdiktede
  erstatningen – et oppdiktet navn erstattes aldri ordrett overalt, det
  kunne stå ekte et sted.
- **Tilbakehenting i Word, Excel, PowerPoint og OpenDocument beholder
  formateringen til originalen.** Sto en verdi over flere løp – «Anna»
  vanlig, «Musterfrau» fet og rød –, kom den tidligere helt tilbake i det
  første løpet og mistet fet skrift og farge. Nå fordeler tegnene seg igjen
  som i originalen; et Word-avsnitt er deretter byte for byte det
  opprinnelige. Det samme gjelder for HTML-sider, HTML-delen av en e-post
  og HTML-kroppen til en Outlook-melding (.msg) – ved e-post bevares
  dessuten Doctype, som rensingen tidligere fjernet stilltiende.
- **Tekstfiler beholder kodingen sin.** Rensing og tilbakehenting skriver nå
  `.txt`, `.md` og `.csv` i kodingen de ble levert i – UTF-8 med og uten
  BOM, UTF-16, Windows-1252. Tidligere ble en Windows-1252-fil alltid til
  UTF-8, og en UTF-16-fil kom skadet tilbake, selv om det ikke var noe å
  erstatte i den.
- **Tilbakehentede bilder beholder fargemodusen sin.** En gråtoneskanning
  kommer tilbake som gråtone i stedet for en tre ganger så stor RGB-fil, en
  palett som palett, svart-hvitt som svart-hvitt – ved hele bildet med
  samme verdier som i originalen. Gjelder for bildefiler og for bilder i
  PDF-er. CMYK og 16 bit forblir RGB, fordi PNG-resultatet ikke kan bære
  noen av delene.
- **En ramme i bildet henter hele redigeringen tilbake som den berører.**
  Pikselerte ansikter bærer en kant rundt den gjenkjente boksen; den som
  bare dro rammen over ansiktet, beholdt en pikselert ring. Nå vokser
  rammen til den sammenhengende endringen mot originalen – en ramme over
  øyepartiet er nok. Atskilte striper ved siden av blir stående; ved et
  helt fjernet eller helt utvisket foto gjelder fortsatt den dratte rammen.
  Gjelder for bildefiler og bilder i PDF-er.
- **Sladdestripe over hele linjen.** I linjemodusen til redigeringsprogrammet
  løper stripen nå fra det første til det siste ordet i linjen, ikke lenger
  bare over det trufne ordet – en stripe i ordlengde avslører hvor langt
  ordet var, og fra seks tegn foran et postnummer lar det seg gjette et
  stedsnavn. Merkinger, beløp og tabellkolonner ved siden av verdien blir
  stående – stripen dekker feltet, ikke linjen i fakturaen. Den nye
  bryteren «Hele linjen» ved siden av «Tekstlinjer» stiller igjen om til
  ordnøyaktig, hvis nabordene skal bli stående; valget huskes.

### Rettet

- **Bilder i HTML-sider og e-poster forble ukontrollerte – navnet i logoen
  sto fortsatt leselig etter rensingen.** Et i siden innebygd bilde
  (``data:``-adresse) ble slett ikke rørt, bare alternativteksten dets;
  logoen ved HTML-grenen til en e-post (inline-bilde uten filnavn) falt
  gjennom vedleggsfilteret; og ved det navngitte bildevedlegget forble
  bilderegelen «utvisk»/«fjern» uten virkning. Nå går alle tre den samme
  veien som en bildefil: tekstgjenkjenning i det bevarte bildet, ansikter,
  koder, metadata og bilderegelen. Rapporten nevner bildene – også
  advarselen når de forblir ukontrollerte uten tekstgjenkjenning –, og
  «Hent tilbake innebygde bilder» samt tilbakehentingen fra treffpanelet
  kjenner nå også disse bildene.
- **En kontorfil med bilde lot seg overhodet ikke rense hvis
  tekstgjenkjenningen ikke behersket språket.** På Mac leser den
  systemegne tekstgjenkjenningen; for hindi, gresk, kroatisk eller
  litauisk kan den ikke det og sier det nå også nylig – ved Word, Excel,
  PowerPoint og OpenDocument avbrøt dette imidlertid **hele** rensingen,
  og det oppsto ingen fil. Likevel lot teksten seg rense feilfritt; bare
  bildet var ikke leselig. Filen skrives nå som ved PDF og enkeltbilder,
  og i resultatet står det at bildene IKKE ble kontrollert – med grunnen
  og henvisning til «Håndter språk».

- **I Excel-arbeidsbøker ble navn stående i nedtrekkslister.** Listen til
  et nedtrekksfelt (dataverifisering) renses nå som ethvert annet
  celleinnhold; referanser til celleområder forblir urørt, slik at
  arbeidsboken forblir hel.
- **Der plassholderen ikke passet inn, sto en svart stripe – nå står en
  kortere skrivemåte der.** `[GEBU_1]` i stedet for `[GEBURTSDATUM_1]`, og
  først når selv den korteste formen ikke passer lenger, sladdes det. En
  stripe sier ingen lenger at det sto noe der; en kort plassholder sier
  det. Etterredigeringsprogrammet kunne dette allerede, den automatiske
  rensingen tidligere ikke. Tilordningsfilen fører begge skrivemåtene til
  samme verdi, slik at også det forkortede lar seg hente tilbake.
- **Det første klikket på «Erstatt» lot etterredigeringsvinduet stå kort
  stille.** Gjenkjenningen som gir plassholderen typen sin (`[NAME_3]` i
  stedet for `[BEGRIFF_3]`), ble først lastet i dette øyeblikket – rundt to
  til tre sekunder. Den forberedes nå i bakgrunnen ved åpning av vinduet;
  målt ble det av 2289 millisekunder 193.
- **To samtidige rensinger kunne laste samme språkmodell dobbelt** – for
  eksempel mappeovervåkingen og hovedvinduet. Fordi hver modell tar flere
  hundre megabyte, sto minnebehovet dermed kortvarig ved det dobbelte. Nå
  venter den andre kjøringen på modellen til den første.
- **Stedet i datolinjen fjernes nå også når språkmodellen ikke gjenkjenner
  det alene:** Det som sikkert er funnet som postnummer med sted («3335
  Amstetten»), trekker med seg stedsnavnet sitt i hele dokumentet – som et
  etternavn fra et fullt navn. Og en forkortelse med siffer foran et navn
  («T3 Hofbauer Christian») forblir leselig, i stedet for å forsvinne med
  i plassholderen.
- **Tre lekkasjer fra annengangslesningen av en ekte ordre lukket:**
  Saksbehandleren «T3 Hofbauer Christian» gjaldt på grunn av forkortelsen
  «T3» som kolonneoverskrift og forble leselig; et sted som språkmodellen
  leste over linjeskiftet inn i kolonneoverskriften, svelget «Pos.» og lot
  kundens fornavn stå; og et navn med tiltaleform («Herr Robert Köttel»)
  trakk bare med seg etternavnet, ikke fornavnet – og for det hvert
  «Herr». Forkortelser er nå rene bokstaver, toordsnavn ingen
  overskriftslinje, treff avkuttes foran en kolonneoverskrift, og
  tiltaleformen telles ikke med til navnet.
- **Stedet i datolinjen («Melk, 05.08.2026») rett under adresseblokken
  forble leselig.** Språkmodellen klistret det med stedet i
  postnummerlinjen til ett treff, og det falt som helhet mot
  postnummermønsteret. Nå forblir den overhengende resten et eget treff.
  Funnet av den nye annengangslesningen av resultatet
  (`werkzeuge/zweitlesung.py`).
- **Mac: En skanning på et språk den systemegne tekstgjenkjenningen ikke
  behersker (for eksempel hindi, gresk, kroatisk, litauisk), gjaldt som
  kontrollert.** Det ble lest med det engelske reservevalget, den fremmede
  skriften forble i bildet, og rapporten sa «ingenting funnet». Nå heter
  det «Bilde(r) ble IKKE kontrollert» med grunnen, og
  språkforvaltningen lover ikke lenger tekstgjenkjenning for slike språk
  bare fordi en Tesseract-språkfil ligger der.
- **I PDF-en blir skilletegnet bak en erstattet verdi stående.** Av
  «Innleggelse den 01.03.2026, utskrivelse den 04.03.2026.» ble det
  tidligere «Innleggelse den [DATUM_1] utskrivelse den [DATUM_2]» – komma
  og sluttpunktum manglet, ved plassholdere likeledes som ved forskjøvede
  datoer. Fjernet blir nå bare den gjenkjente verdien, ikke hele ordet til
  neste mellomrom; komma, semikolon, punktum eller parentes bak forblir på
  sin plass, og plassholderen løper ikke over dem.
- **Russisk og ukrainsk kjørte ubemerket med den svakere
  flerspråksmodellen**, når en hjelpepakke for ordformanalysen
  (`pymorphy3`) manglet – de egne modellene lot seg da ikke laste, og
  «Львів» ble til en person. For gjenkjenning av navn trengs ikke
  ordformanalysen; modellen lastes nå uten den, og steder er igjen steder.
- **Lisensmerknadene på 16 språk var utdaterte.** Der sto fortsatt at
  MPL-kildekoden ble stilt til rådighet «på forespørsel», QPDF gjaldt som
  MPL-2.0, sju byggeklosser manglet i tabellen (wordfreq, Qt, ONNX
  Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), spaCy-avsnittet var
  engelsk, og til slutt hang et engelsk erstatningsavsnitt. Nå står alle
  18 versjonene på nivå med den tyske: kildearkiver varig under
  maskuro.com/quellcode/oss/, QPDF Apache-2.0, Qt-LGPL-vei,
  modellopprinnelse. Også den engelske tabellen har de manglende linjene.

- **Kontraktord i genitiv («tilbudsinnholdets», «anbudets», «tidsplanens»)
  gjelder ikke lenger som sted.** Et enkeltord bak en genitiv- eller
  dativartikkel med bøyningsendelse er et slektsord – stedsnavn bøyes ikke
  («til Graz»). Står stedet et annet sted i dokumentet uten artikkel
  («Burgenland»), forblir også «Burgenlands» gjenkjent.
- **Forskjøvede, maskerte og oppdiktede verdier rastrerte PDF-siden.**
  Etterkontrollen etter fjerning tillot i funnrektangelet bare en
  plassholder i skarpe klammer; en forskjøvet dato («01.07.2026») eller en
  maskert verdi («****1234») gjaldt som en oversett rest, og siden ble av
  forsiktighet gjort om til et bilde – ikke ved «Erstatt». Nå forblir
  slike sider tekst, og tilbakehentingen fra panel eller ramme leverer
  igjen originalen.
- **Flerords erstatningsverdier lot seg ikke angre via treffpanelet i
  PDF.** Et oppdiktet navn («Greta Mayrhofer») eller en maskert IBAN
  («**** **** **** **** 3201») består av flere ord; funnstedsøket
  sammenlignet ord for ord og meldte «Plassholderen ble ikke funnet i
  dokumentet». Nå leses etterfølgende ord på samme linje sammen.
- **Etter tilbakehenting av en uten erstatning fjernet verdi ble
  panellinjen dens stående.** Verdier som strategien «sladd» i
  plassholdermodus fjerner uten erstatning, har ingen plassholder som
  panelet kunne måle en forsvinning ved. Nå strykes linjen så snart
  verdien igjen står i dokumentet.

- **Forkortelsessammensetninger som «E-Helfer» eller «U-Bahn» gjelder ikke
  lenger som navn.**
- **Orddelingsrester («Leis-») og overlange sammensetninger
  («Bauarbeitenkoordinationsgesetzes», «Baustellenkoordinator») gjelder
  ikke lenger som navn eller sted.** I en skannet anbudstekst ble dermed
  28 ord færre sladdet.
- **Posisjonslister i skannede tilbud gjelder ikke lenger som
  navneregister.** Tilleggsgjennomgangen for registre (korte linjer) gjorde
  «Kälterohr» og «Außengeräte» til personer; den avstår nå så snart
  posisjonsnumre som «1.1.5» står ved linjebegynnelsen. Datolinjer i
  e-posttråder telles ikke som posisjonsnumre ved dette.
- **Kolonneoverskrifter og posisjonsnumre i skannede tilbud («Pos.»,
  «Pos. 1.1.3», forkortelsene «E/L/S») gjaldt som navn eller sted.** En
  forkortelse alene på sin linje, en merking med nummer og enkeltbokstaver
  linjevis er det ikke.
- **Siden «pustet» i etterredigeringsvinduet etter åpning av
  sammenligningslupen** – ved «Sidebredde» og «Tilpass» henger målestokken
  ved visningsvinduet, og det endres med hver rullefelt som kommer eller
  går; hver følgende handling rykket siden litt inn. Lerretet trekker det
  nå selv etter til det står stille. Og zoomknapper, glidebryter og
  hurtigtaster holder bildesentrum også når det dukker opp et rullefelt
  ved innzooming.
- **Tverrmatede skanninger leses nå oppreist, og småtrykk i store
  skanninger går ikke lenger tapt.** Et 24-siders skannet tilbud beholdt
  i hver bunntekst seks bank-IBAN-er, foretaksnummer og MVA-nummer
  leselig: Skanningen lå i PDF-en dreid 90°, og tekstgjenkjenningen lot
  ved svært store bilder, avhengig av bildemål, hele linjer utelates. Nå
  tas den synlige dreiingen med i beregningen, og store bilder leses i
  overlappende bånd – bunntekstene er svarte.
- **Gater etter personer med bindestrek foran grunnordet («Josef
  Admanseder-Straße 7», «Abt-Karl-Straße 8», «Dr.-Karl-Renner-Straße 12»)
  gjenkjennes som adresse.** I brevhodet til et skannet tilbud forble en
  slik adresse leselig, fordi mønsteret krevde et mellomrom foran
  «Straße».
- **IBAN-er fra tekstgjenkjenningen som bærer en O i stedet for 0 eller en
  l i stedet for 1, gjenkjennes nå.** I småtrykket av en skanning leser
  tekstgjenkjenningen sifre gjerne som bokstaver; nummeret hadde da formen
  til en IBAN, men kontrollsummen gikk ikke opp, og den ble stående.
  Mislykkes kontrollsummen, prøves nå lesningen med sifre – stemmer den
  da, er det IBAN-en. Feil kontrollsifre forblir feil.
- **Setningsstykker som «følgende koder på» gjaldt som sted.** Et navn
  eller sted som begynner med et lite skrevet ord, er ikke et – unntatt
  ved adelspartikler («van Gogh», «de Vries»).
- **I redigeringsprogrammet forble den siste bokstaven stående ved siden
  av sladdestripen** («…6», «…t», «…g»), og stripen hadde høyden til den
  dratte rammen i stedet for linjen. Årsak: Kunne redigeringsprogrammet
  ikke måle opp siden, holdt det hver ramme for «ingen ord truffet» og
  anvendte den eksakt – uten regelen om at et halvt ord aldri blir
  stående. Det samme skjedde ved enkelte tekstkommandoer
  redigeringsprogrammet ikke kunne stedfeste. Nå teller alltid ordboksen
  ved siden av: Det rammen vesentlig overlapper, faller helt.
- **Den siste bokstaven i et ord stakk ut over sladdestripen.** Stripen ble
  målt etter fremdriftsbredden fra skriftmetrikkene; tegner skriften en
  glyf bredere, sto resten av den ved siden av stripen. Boksen til et
  tegn tar nå også opp den tegnede glyfen.
- **Meldingen om å gjøre en side om til et bilde lovet for mye.**
  «Fremstillingen forblir uendret» stemmer ikke etter rastrering: Skrift og
  grafikk er da bildepunkter, filen blir større. Meldingen sier det nå –
  og nevner også den andre grunnen til at det rastreres (ombyggingen ville
  skadet siden).
- **Teksten bak en fjernet verdi rykket opptil ett punkt mot venstre.** Ved
  ombygging av en linje ble begynnelsen målt ved glyfkanten, fortsettelsen
  ved pennens utgangspunkt – forbredden til det første tegnet ble stående
  igjen som feil («C» 0,5 pt, «I» 1,0 pt). Nå regner ombyggingen
  gjennomgående med pennens utgangspunkt; etterleddet står på
  tidelspunktet nøyaktig på sitt sted.
- **Østerriksk MVA-nummer med mellomrom («ATU 187 35901») og et
  foretaksnummer uten «FN» under merkingen sin («Firmenbuchnummer:
  30799v») gjenkjennes.** Begge sto håndskrevet på et skannet anbudsskjema
  og forble leselige, selv om tekstgjenkjenningen hadde lest det riktig.
- **Liggende PDF-sider ble uten grunn gjort om til bilde etter
  sladding.** Integritetskontrollen sammenlignet original og resultat i
  den dreide visningen, men regnet sine sladdesoner udreid – på en side
  med dreieregistrering lå dens egen sladding derfor ved siden av sonen
  sin og gjaldt som skade. Slike sider beholder nå tekstlaget og
  vektorgrafikken sin.
- **Også rette sider ble av og til uten grunn gjort om til bilde**, når
  teksten bak en plassholder rykket ett punkt frem – tillatt, men
  bildesammenligningen var finere enn sin egen toleranse. Den sammenligner
  nå i halve punkt og treffer toleransen sin dermed nøyaktig: opptil to
  punkt forskyvning slår ikke ut, over slår alt ut.
- **Angivelser i innebygde skjemaobjekter ble stående.** Enkelte maler
  legger brevhode eller brevavslutning som et eget skjema som bare bindes
  inn i siden. Et treff der ble riktignok planlagt og talt som fjernet,
  men aldri skrevet – teksten sto fortsatt der, og bare rastreringen av
  hele siden fanget den opp. Nå omskrives selve skjemaet; et skjema som
  ligger på flere sider, ett eneste gang.
- **PDF-sider ble rastrert til et bilde, selv om ingenting hadde forblitt
  leselig.** Et sjusiders tilbud rammet dette seks sider; det vokste fra
  73 kB til 3,3 MB og mistet skriften sin til et avbilde. Årsaken var
  mellomrom som sto flere ganger etter hverandre i dokumentet, men bare
  ble meldt én gang av leseren: Teksten bak en fjernet angivelse rykket
  bredden dens mot høyre, etterkontrollen fant naboordet i
  funnrektangelet og grep til rastrering. Bevarte linjerester står nå
  igjen nøyaktig på sitt sted; samme tilbud renses nå uten en eneste
  rastrert side (76 kB).
- **Nøkkelnavn og fakturaoverskrifter gjaldt som personer.** I en
  tilgangsfil ble navnet på miljøvariabelen («AWS_ACCESS_KEY_ID»)
  erstattet, ikke bare verdien dens; på en engelsk faktura falt
  overskriften «Bill to» som fornavn. En identifikator i store bokstaver
  med understreker er aldri et navn, og et ord i en linje som som helhet
  er en feltmerking heller ikke – mottakeren under gjenkjennes fortsatt.
- **Søket i etterredigeringsvinduet stoppet opp ved store PDF-sider.**
  Hver bokstav i søkefeltet lot siden rastreres på nytt, selv om bare
  uthevingen endret seg. Det gjengitte sidebildet blir nå stående, så
  lenge side, zoom og visning er de samme – også originalen i
  sammenligningslupen; bla, zoom og en ny filstatus tegnes fortsatt friskt.
- **Posisjonsnumre i tilbud gjaldt som IP-adresse eller telefonnummer.**
  En artikkellinje som «1.3.3.4 … 5-Port Gigabit Switch» lot
  inndelingsnummeret bli til en nettadresse, fordi «Port» talte som
  teknisk omgivelse – nå teller det bare som selvstendig angivelse («Port
  80»), ikke som orddel. Og «1.3.3.6 216879» (posisjons- pluss
  artikkelnummer) sladdes ikke lenger som telefonnummer. Ekte
  IP-adresser og telefonnumre i slike lister gjenkjennes fortsatt.
- **Artikkellinjer i tilbud gjaldt som postnummer med sted.** «35252
  DIETZEL SALR» (artikkelnummer med produsent) og «1000 AWG» (mengde med
  ledertverrsnitt) ble i nummererte posisjonslinjer sladdet som adresse,
  fordi et stor-bokstavsord bak et tall gjaldt som stedsnavn i versaler. I
  posisjonslister gjelder ikke dette lenger; «1080 WIEN» i adresseblokken
  og steder i liten bokstav gjenkjennes fortsatt overalt.
- **Den ekstra navnegjenkjenningen sladdet rollelinjer og
  kolonneoverskrifter i tilbud.** «Partiestundensatz Monteur + E-Helfer»
  gjaldt 49 ganger som person, kolonneoverskriften «Pos. Bezeichnung Menge
  EH» 19 ganger som sted – et 19-siders oppdrag ble dermed uleselig. Slike
  treff i posisjonslinjer faller nå, hvis de selv bærer tegn som intet
  navn har (pluss, skråstrek, siffer, forkortelse) – også når linjen
  ender med et beløp («Alternativ Markt … - PV/LS AC-Versorgung 1
  290,00»). Navn i registre og lister – som nivået er der for – forblir
  uberørt.
- **«Der Kunde» gjorde i forretningsvilkår hver «Kunde» til et navn.** Tok
  den ekstra navnegjenkjenningen artikkelen med i treffet, gjaldt det som
  et todelt navn og beskyttet alle 35 øvrige stedene med samme ord. Nå
  trekkes artikkelen fra, og «der Kunde» faller som allerede «des Kunden».
- **Merkinger gjaldt som verdi.** «E-Mail» ble sju ganger sladdet som
  e-postadresse, «Telefonnummer» og «Faxnummer» som telefonnummer. En
  adresse uten @ og et telefonnummer uten sifre teller ikke lenger.
- **Kolonneforkortelser fra én bokstav («L: 154,50», «S: 0,00») gjaldt
  som navn** – 25 ganger i et PV-tilbud. En enkelt bokstav er verken navn
  eller sted.
- **PDF-sider ble alt for ofte gjort om til bilde.** To årsaker, begge
  funnet på ekte tilbud: Setter en PDF hver glyf som egen kommando og
  ligger det under en mellomrom-glyf uten tekst-tegn, forskjøv
  tilordningen seg fra der med én – av den fjernede verdien ble den siste
  bokstaven stående («ŠkodaTopCar**d**»), og etterkontrollen rastrerte
  siden med rette. Og et ved linjeslutt delt ord («Datenschutz-») gjaldt
  på grunn av delingsstrek-merket til lesebiblioteket som forskjøvet.
  Begge deler rettet: Et kjøretøytilbud gikk fra 4 rastrerte sider til 0,
  et 19-siders oppdrag fra 7 til 0 – skriften forblir skrift, filen
  forblir liten.
- **To ytterligere rastreringsårsaker rettet:** Bringer et dokument selv en
  skrift kalt «F1» med seg, ble plassholderne over bilder satt i denne
  skriften og var uleselige – nå får den egne merkeskriften et fritt
  navn. Og mangler lesebiblioteket et mellomrom midt i en lang
  tekstkommando, bevises nå stedet også ved flerbyte-skrifter (samme kode,
  samme tegn) i stedet for å havne på slutten – tidligere ble en bokstav
  av den fjernede verdien stående, og resten av teksten rykket synlig til
  side. Dertil to siste tilfeller: en kommando av dusinvis
  mellomrom-glyfer lot tilordningen løpe av gårde (navnet bak ble
  stående), og en stor overskrift med forbredde fant ikke sitt første
  tegn (firmanavnet ble stående). **Av ni ekte tilbud rastreres nå ikke
  én eneste side lenger** – tidligere var det 30 av 90.
- **Ved rastrering forsvant bilder under en svart blokk.** Må en side
  gjøres om til et bilde, gjengis den fra originalen – og det kjenner
  ingen bilderensing. Tidligere falt derfor *hver* bildeflate på siden
  under en stripe, også urørte. På et tilbud lå adresse og to
  sertifikatlogoer i samme brevhodebilde; stripen tok med seg logoene. Nå
  settes det allerede rensede bildet inn: Adressen i det er sladdet, alt
  annet forblir synlig. Et fjernet bilde etterlater hvitt papir i stedet
  for en svart boks.

- **Rensede skanninger ble mange ganger større enn originalen.** Hvert
  bilde der noe ble sladdet, gikk tilbake i filen som ukomprimert
  råbilde – ved en 24-siders skanning vokste den dermed fra 11,8 til
  52,9 MB. Bilder beholder nå typen de forelå i: et foto forblir et foto,
  en faksskanning forblir svart-hvitt, et fargeløst bilde legges ikke som
  fargebilde. Samme fil er nå 15,6 MB stor, uten synlig forskjell.

- **Skannede PDF-filer fra kontormaskiner kom tilbake som stripemønster.**
  Slike skanninger legger skriften som et skarpt svart-hvitt-lag over et
  grovt fargebilde – Canon, Xerox og Kofax bygger filene sine slik. Ved
  sladding i bildet ble dette laget feilaktig skrevet tilbake; resultatet
  var uleselig. Ved et sekssiders tilbud rammet dette ni av seksten
  bilder. Det behandles nå riktig, i sin egen farge, og de sladdede
  stedene er der virkelig borte.

- **«Fjern alle bilder» tok teksten fra en skannet side.** Skriftlaget til
  en slik skanning er teknisk sett et bilde – det ble fjernet henholdsvis
  utvisket med, og igjen ble et tomt ark. Det forblir nå stående; logoer,
  stempler og signaturer viker fortsatt.

- **Kontrollen for skadede PDF-sider rastrerer ikke lenger på grunn av en
  minimal forskyvning.** Et ved rensing nyforankret tekststykke får
  forskyves opptil to punkt; bildesammenligningen talte dette likevel som
  skade og bygde siden om som avbilde – dermed gikk vektorgrafikk som
  tabellinjer tapt, og over funnsteder lå en stripe i stedet for en
  plassholder. Sammenligningen tillater nå samme lille forskyvning som
  ordkontrollen; ekte skader faller fortsatt i øynene.

- **Tilbakehenting av mange verdier etter hverandre mislyktes ikke lenger
  på Windows med «Tilgang nektet».** Den som i en kontorfil hentet
  tilbake mange panellinjer kort etter hverandre, kunne mislykkes ved en
  kortvarig filsperring fra virusskanneren; utvekslingen venter nå kort
  ut slike sperringer.

- **Windows-veien for kommandooverføring avsluttet kontrolløren i stedet
  for å kontrollere.** Livskontrollen av den lyttende instansen sendte på
  Windows utilsiktet en ekte Ctrl+C til sin egen konsollgruppe; den spør
  nå uten signal hos systemet.

- **Flerords feltmerkinger virket ikke, men bruddstykkene deres
  virket.** «Date of birth», «Bank account», «Cuenta bancaria» og «Numero
  de cliente» sto i merkelisten, men ble der delt opp i enkeltord og
  traff derfor aldri; igjen ble ordledd som «de» og «of», som siden
  gjaldt som merking – «de» er imidlertid en navnedel («Anna de Vries»).
  Begge deler er rettet: Vendingene virker nå som helhet, bruddstykkene
  er borte.

- **Tyske hilsenformler med «ß» ble behandlet som personnavn til tross for
  oppføring.** Under «Herzliche Grüße» eller «Mit freundlichen Grüßen» sto
  det i resultatet en plassholder, selv om begge vendingene alltid har
  stått i motlisten. Årsaken var en skrivemåte som aldri kom frem ved
  sammenligningen; berørt var åtte oppføringer over fem lister. De virker
  nå alle.

- **«John Staff» forble ikke erstattet.** Et etternavn som samtidig er en
  engelsk kolonneoverskrift, ble forkastet med av merkefilteret.
  Overskriften forblir fortsatt urørt, navnet under erstattes igjen.

- **Verdier fra merkede skjemafelt forblir beskyttet i KI-nivået.** Den
  lokale dommeren i KI-nivået fikk tidligere også forelagt treff til
  vurdering hvis betydning allerede var belagt av feltmerkingen
  («Geburtsdatum:» over verdien) – og fikk lov til å forkaste dem. Slike
  strukturelt belagte verdier forelegges den ikke lenger. Tilordningsfilen
  nevner nå for hver erstatning i tillegg gjenkjenningsveien («belegg»).

- **En PDF-side der bevart tekst tok skade under rensingen, gjenkjennes nå
  og bygges om som avbilde av originalen.** Ved enkelte generatorskrifter
  kunne bevarte tekststeder etter rensingen vises som svarte blokker eller
  ord flytte sammen, selv om alle angivelser som skulle fjernes, var
  fjernet korrekt. Maskuro sammenligner nå resultatet ord for ord og
  bildepunkt for bildepunkt med originalen; en skadet side erstattes av
  sitt rene avbilde — med sladdestriper over funnstedene, sladdede
  bildeområder og søkbar tekst. Siden forblir leselig, fjerningen
  pålitelig.
### Endret

- **I de oversatte grensesnittene heter hvert fagbegrep nå det samme
  overalt.** For ett og samme tyske ord sto det, avhengig av vindu, to
  eller tre oversettelser side om side: Kontrollprotokollen het på norsk
  dels «Revisjonslogg», dels «Kontrollogg», gratisnivået dels
  «Gratisnivå», dels «Gratisversjon» – og lignende på et dusin andre
  språk. Den som lette etter en innstilling, fant den i neste vindu under
  et annet navn. Det ble ensrettet til ordet som grensesnittet uansett
  bruker oftest.

  Dette avdekket steder der ett ord sto for to **forskjellige** ting:
  Fransk, gresk og koreansk brukte for «sladde» og «maskere» samme
  uttrykk – altså nettopp der programmet forklarer forskjellen («Sladding
  fjerner uten erstatning, maskering beholder formen»). Begge deler er nå
  skilt fra hverandre. For svensk gjenstår denne avgjørelsen ennå: Der
  heter sladdingen «maskera» – samme ord som maskering.

- **Spørsmålet om bruksmåte ved første oppstart er bortfalt.** Kort tid
  etter oppstart kom et vindu («Privat eller i virksomhet?»), og i
  innstillingene sto en linje om dette. Begge deler finnes ikke lenger –
  uten erstatning. En angivelse som ingenting henger på, oppgir feil hvem
  som vil ha feil lisens, og den som er ærlig, trenger den ikke; den
  kostet hver enkelt et klikk på et tidspunkt der ingen tenker på
  lisenstyper. Hvilken lisens som er den riktige, står der den avgjøres:
  på prissiden, i kassen og i hjelpen. Selskaper som ruller ut Maskuro
  sentralt, fastsetter fortsatt bruksmåten via vorgavefilen.

- **Henvisningene om lisenstype nevner tilfellet det gjelder.** Privat­lisensen
  gjelder utelukkende privat bruk; alt yrkesmessig eller kommersielt
  arbeid trenger firmalisensen – også som enkeltmannsforetak uten
  ansatte. Dette sto slik i lisensvilkårene, men verken i programmet eller
  i hjelpen: Der ble bare firmadomenet nevnt, og det dekker nettopp ikke
  dette tilfellet: Maskinen til en selvstendig næringsdrivende tilhører
  intet domene. Henvisningen ved innlesing av en privatlisens sier det
  nå, likeledes lisenskapittelet i veiledningen og de vanlige spørsmålene,
  som fikk en egen oppføring for dette. Fortsatt sperres ingenting.

- **De ennå ikke leverte veiene ligger nå samlet.** Innstillingene har fått
  en side «Utvikler»; der står den maksimale gjenkjenningen (KI) med sin
  motkontroll, ordlistekatalogen og mappeovervåkingen. Alle tre er bygget,
  men ikke prøvd i praksis – de er derfor bare synlige med en
  utviklerlisens, og det overalt samtidig: Siden, menyoppføringene og
  virkningen under kjøring henger på samme avgjørelse. Uten denne lisensen
  forblir et tidligere påslått KI-nivå uten virkning; innstillingen dets
  slettes ikke og gjelder igjen så snart veien leveres.

### Forbedret

- **«Hva som søkes» viser tre ytterligere lister fra navnegjenkjenningen.**
  Tiltaleformene som får det følgende ordet lest som navn; titlene og
  rollene som deretter fortsatt **ikke** er navnet («Herr Bürgermeister
  Huber»); og de åtti flerspråklige merkingene navn identifiseres med
  saksnummer, prosess- og saksnumre. Alle tre har alltid virket, men var
  ikke synlige i oversikten.

- **«Hva som søkes» viser to tidligere manglende ordlister.** Tiltaleformene
  og titlene som gjør et foranstående ord til et navn («Herr», «Frau»,
  «Dr.»), og forkortelsene til normeringsorganisasjonene som Maskuro
  skiller en normhenvisning som «ÖNORM B 2110» fra en person med. Begge
  har alltid påvirket gjenkjenningen, men sto ikke i oversikten.

- **Posisjonslister, innholdsfortegnelser, utstyrsoppramsinger og
  normhenvisninger forblir leselige.** Gjenkjenningen ser nå
  byggeformen til linjen: Et gjettet navn i en inndelingslinje («1.3.1
  Energieerdkabel 1kV»), en registerlinje med ledepunktumer, en
  oppramsing («- trådløs lading med magnetring»), over en
  mengde-/prislinje, i en kolonneoverskrift eller bak «ved hjelp av» er et
  saksbegrep og erstattes ikke lenger. Ekte navn forblir beskyttet – via
  tiltaleform, feltmerking og belegget et annet sted i dokumentet; på
  målekorpuset mistet ikke ett eneste treff sin beskyttelse. I
  geskäftskorpuset synker de falske treffene dermed fra 25 til 6.

- **Overskrifter, skjemamerkinger og hilsenformler tas sjeldnere for navn
  – på tysk og engelsk.** Ordlistene Maskuro skiller saksord fra
  personnavn med, har vokst betydelig: Merkinger fra fakturaer, skjemaer
  og offentlig post («Aktenzeichen», «Verwendungszweck», «Kostenstelle»,
  «Sort code», «Subtotal»), avsnittsoverskrifter fra søknader og
  rapporter («WERDEGANG», «QUALIFIKATIONEN», «SUMMARY», «REFERENCES»),
  tyske og engelske skrivtyper («Auftragsbestätigung», «Niederschrift»,
  «Timesheet», «Agreement») samt kommandoformer fra veiledninger («Send…»,
  «Select…»). Den engelske siden var tidligere påfallende tynt bemannet.

- **Merkede felt avslører nå også når merkingen er sammensatt, hva som
  står i dem.** «Lieferanschrift», «Rechnungsadresse», «Sachbearbeiterin»,
  «Kontoinhaber», «Contact person» og «Billing address» tilordner nå
  verdien ved siden av eller under samme type som det enkle «Anschrift»
  eller «Name» – i et utfylt skjema med bokser er dette forskjellen
  mellom funnet og oversett.

- **I etterredigeringsvinduet bla musehjulet videre ved siderand.** Den
  som ruller videre ved slutten av en side, havner øverst på den neste;
  den som ruller tilbake ved begynnelsen, nederst på den forrige – et
  dokument lar seg dermed rulle gjennom fra begynnelse til slutt, uten å
  røre sideknappene. Tastaturet (Page Up/Page Down) kunne dette allerede;
  en kort pustepause mellom to sidebytter forhindrer at etterløpet fra en
  styreplate bærer gjennom halve dokumentet.

- **Sideminiatyrene i etterredigeringsvinduet sitter midtstilt i feltet.**
  Tidligere klistret de seg til venstre kant, og ved breddeutvidelse
  vokste bare den tomme margen til høyre.

- **Symbollinjen i etterredigeringsvinduet viser gruppene sine.**
  Skillestrekene har nå luft og farge, «Søk» og «Overfør til alle sider»
  står som egne grupper ved siden av verktøyene, og «Overfør» vises nå
  bare ved dokumenttyper der det kan gjøre noe. Hver oppføring i linje og
  menyer bærer nå et bilde: «Tekstlinjer» og sammenligningslupen har fått
  egne symboler (lupen delte tidligere sitt med «Før/etter»), dertil
  zoom, hele siden, sidebredde, drei, bla og hurtigtastene. «Åpne med
  systemprogram» står nå også i linjen ved siden av Skriv ut – veien fra
  ferdig resultat til det vante programmet er ett klikk, ingen menygang.

- **Ved utklippstavlerensingen står det igjen med at det bør sjekkes.** I
  innstillingene står henvisningen varig ved siden av bryteren: Maskuro
  kan overse personopplysninger eller behandle angivelser feil,
den innlimte teksten skal ses gjennom før videreformidling. Ved påslåing
  nevner meldingen den dessuten, og den noteres i utdataområdet – også når
  intet symbol kjører i infoområdet. Ved hver enkelt kopieringshandling
  vises den bevisst ikke: En henvisning som ville kommet femti ganger om
  dagen, ville ikke blitt lest lenger etter tredje gang.

## 0.10.36-beta.1 – 20. august 2026

### Forbedret

- **Tekniske forretningsdokumenter blir ikke lenger oversladdet.** Fire
  gjenkjenningsbremser, hentet fra elleve reelle tilbud og ordrer:
  Inndelingsnumre («1.3.1.1») gjelder ikke lenger som IP-adresser,
  normhenvisninger («ÖNORM EN 62446») og identifikasjonskoder ikke lenger
  som postnummer eller telefonnummer, og rolleord bak artikler («kunden»,
  «oppdragsgiveren») ikke lenger som navn – i forretningsvilkårene til et
  reelt tilbud er dermed alle 46 rolleordene igjen lesbare i stedet for
  sladdet. Adresser med landkode («A 3390 Melk», «D-94032 Passau») fjernes
  nå fullstendig, i stedet for å la postnummeret stå igjen alene.

- **Ordlister er nå fullt innsynlige.** Under «Hjelp → Ordlister …» kan de
  lokalt brukte gjenkjennings- og motkontrollistene søkes gjennom, sammen
  med språk, formål, kilde og innhold. Dette inkluderer også Wordfreq-,
  medisin-, personlige og sentralt forvaltede lister samt beholdningene for
  oppdiktede erstatningsverdier. Håndboken beskriver katalogen i et eget
  avsnitt.

- **Ferdige fillinjer viser det brukte gjenkjenningsspråket.** Bak «ferdig»
  står nå for eksempel «Tysk» eller «Engelsk», slik at et upassende
  automatisk språkvalg straks blir synlig. Måtte et annet installert språk
  tre inn, viser en pil begge språkene.

- **Den nye sammenligningslupen viser under gjennomlesing straks det
  tilsvarende stedet i originalen.** Det forstørrede originalutsnittet
  følger musepekeren over det fortsatt redigerbare resultatet; ved tekst
  følger den avsnittet. Lupen kan brukes ved vinduskanten eller trekkes ut
  som et eget, maksimerbart vindu. Zoomen kan stilles direkte mellom 50 og
  300 prosent og huskes på samme måte som på/av-tilstanden.
  «Tilbakestill» bringer også en maksimert eller ugunstig dokket lupe
  tilbake til venstre i en betjenbar størrelse. Erstattede originalverdier
  er uthevet med gult i lupen, slik at de berørte ordene straks fanger
  oppmerksomheten under lesing. Én gang aktivert åpner den seg igjen ved
  fremtidige egnede dokumenter – også etter en omstart av programmet. Den
  tidligere før/etter-bryteren finnes fortsatt i visningsmenyen. Håndboken
  beskriver den i et eget avsnitt.

- **Åpen kildekode- og modellbevis er nå versjonspresist.** Pakkebyggingen
  genererer en maskinlesbar komponentliste sammen med hasher av de
  vedlagte lisensteksten. MPL-kilder, modellopprinnelse, faste revisjoner,
  endringer og SHA-256 dokumenteres separat; nedlastede modeller får sitt
  opprinnelsesbevis direkte i modellmappen. Bevegelige Tesseract- og
  spaCy-referanselister er nå fast forankret. Salgsartefakter forblir
  sperret inntil alle kilder og modellvedlegg er publisert og kontrollert.

- **Den lokale wordfreq-databasen er fullstendig lisensbelagt.** Pakkebyggingen
  kontrollerer versjon 3.1.1, 39 uendrede små lister inkludert CJK og det
  kinesiske tegnkartet mot antall, størrelse og manifest-sjekksum.
  Apache-2.0-kodehenvisning, fullstendig CC-BY-SA-4.0-lisens, attribusjon,
  datakilder og de utelatte store, Jieba- og ikke-støttede listene er
  dokumentert i pakken.

- **Vanlige setningsord blir sjeldnere feilaktig sladdet.** En lokal
  frekvensordbok tjener som ekstra motkontroll når navnegjenkjenningen
  tar et verb, pronomen, en artikkel eller en preposisjon for en person.
  Ordboken avgjør aldri alene: Substantiv, flerdelte navn samt navn i felt,
  lister og etter tiltaleformer forblir beskyttet. Kinesisk, japansk og
  koreansk bruker utelukkende eksakte tokengrenser fra sine allerede
  eksisterende språkmodeller; for ikke-eksisterende språk settes ikke inn
  et antatt lignende ordbokspråk. For dette overføres ingen dokumenttekst
  til internett.

- **Tekniske produkt- og utstyrsbegreper tas ikke lenger så lett for navn
  eller steder.** Den lokale motkontrollen forbinder nå frekvens, ordklasse,
  teknisk orddannelse og saksfelt. Dermed forblir for eksempel
  «Travel-Assistent», «Family-Bonus», «WLTP-Wert», «Easy-Start» og
  sammensatte nummer-, holder- eller bremsebegreper i dokumentet. Engelske
  bestanddeler slås også opp lokalt i tysk saksTekst; ekte egennavn,
  tiltaleformer samt person- og stedsfelt beholder forrang. Dessuten gjelder
  en «2-årig produsentgaranti» ikke lenger som levealder.

- **Qt-/PySide-lisensrettighetene er nå fullstendig sporbare.** Programpakken
  inneholder i tillegg hele GPL-3.0-teksten, eksakte Qt-versjoner, et
  kildekodetilbud og en tysk/engelsk veiledning for utskifting av de
  dynamiske bibliotekene, inkludert lokal macOS-nysignering. En salgsbygging
  blokkeres så lenge de eksakte kildearkivene til den utleverte versjonen
  ikke er tilgjengelige på det egne kildekodenettstedet.

- **Lisens og oppdateringsstatus sier nå for hvert nivå entydig hva som
  gjelder.** I lisensvinduet og under oppdateringsinnstillingene står det
  om oppdateringer er inkludert, til hvilken dato de rekker, og om den
  løpende versjonen forblir varig brukbar. Privatlisenser installerer ikke
  lenger en senere utgitt versjon etter skjæringsdatoen; også en nylig
  nedlastet installer gjenkjenner ut fra sin faste innebygde utgivelsesdato
  om den angitte nøkkelen omfatter den. Den siste dekkede privatversjonen
  forblir varig brukbar. Utløper derimot et bedriftsabonnement, opphører
  bruk og oppdateringer; prøveperiode og gratisnivå åpner seg ikke som en
  omvei.

- **Private varige lisenser finner nå også etter en ny installasjon den
  riktige programstatusen.** Et signert versjonskatalog fører alle stabile
  versjoner og deres pakker. Er den siste installeren omfattet av kjøpet
  ikke lenger tilgjengelig, kan i stedet nøyaktig den neste høyere
  tilgjengelige stabile versjonen brukes automatisk – aldri en beta eller
  nightly. Ved en for ny installasjon kan kunden installere det tillatte
  nivået eller bytte til kjøpssiden for en ny oppdateringsperiode; et
  tilbakeskritt skjer ikke stille. Dette gjelder også for administrerte
  MSI-installasjoner.

- **Den automatiske ansiktssladdingen er nå entydig beskrevet.** Program-
  hjelpen og personvernteksten omtaler funksjonen «Gjenkjenn og gjør
  ansiktsområder ukjennelige» og avgrenser den fra identifikasjon,
  gjenkjenning, ansiktssammenligning, biometriske maler og person- eller
  ansiktsdatabaser. De påpeker dessuten klart at den fullstendig lokale
  gjenkjenningen kan overse eller feilaktig markere områder, og at
  resultatet derfor må kontrolleres visuelt. Også ved en enkeltvis renset
  bildefil nevner resultatrapporten nå gjenkjente og pikselerte
  ansiktsområder; en manglende tekstgjenkjenning blir dermed ikke lenger
  feilaktig beskrevet som en helt uendret fil.

## 0.10.36-alpha.20260820 – 20. august 2026

### Rettet

- **Anonymiserte angivelser kan nå hentes fullstendig tilbake uavhengig av
  rekkefølgen.** Den tidligere tilbakehentingen søkte verdien via synlige
  tekstankere. I tette tabeller, direkte naboliggende plassholdere og
  usynlige Office-/e-postlagre manglet disse ankerne; noen ganger kunne et
  begrep derfor først hentes tilbake etter at en annen klartekst tilfeldigvis
  hadde skapt et nytt anker. Nå sammenlignes resultat og original per ekte
  formatbærer med den fullstendige tilordningen, og bare de belagte stedene
  for den valgte verdien blir skrevet.

- **Navn, e-postadresser, numre og egne kontrollbegreper forblir entydig
  betjenbare også ved overlappende gjenkjenning.** Er den samme klartekstverdien
  tilordnet to typer, avgjør plassholderen som faktisk står på funnstedet
  sammen med den valgte sidepanellinjen. Et ubelagt verdi/plassholder-par
  forblir fortsatt sikkert sperret.

- **E-postspesialtilfeller etterlater ikke lenger skjulte plassholdere.**
  Dette gjelder MIME-kodede emnefelt, tekstvedlegg og navn adskilt av
  HTML-markup i EML og MSG. UTF-8-HTML uten egen tegnsettangivelse blir i
  Outlook-filer dessuten ikke lenger kodet om til Mojibake ved hvert
  redigeringstrinn; eldre, allerede slik skrevne resultater forblir mulig å
  hente tilbake.

### Forbedret

- **En ny frigivelsesmatrise betjener hver anonyme sidepanellinje enkeltvis
  og bevisst baklengs.** Den kontrollerer alle 14 tekst-, kontor-, web- og
  e-postformater samt PDF, deretter også formler, attributter, relasjoner,
  kommentarer, e-posthoder, vedlegg og interne biloppbevaringer. Den
  fullstendige macOS-kjøringen omfatter nå 149/149 grønne kontrollskript.

## 0.10.35-alpha.20260820 – 20. august 2026

### Forbedret

- **Språkmålinger sammenligner nå virkelig likt med likt.** Det faste
  målekorpuset inneholder de samme 14 dokumenttilfellene med de samme sju
  tekst- og fire bildeoppgavene på tysk og engelsk. En full kjøring gjentar
  nøyaktig denne matrisen for alle tolv tilgjengelige korpusspråk. Skjemaer,
  tabeller, samtaler og andre ennå ikke fullstendig oversatte strukturprøver
  beholdes, men vises separat og blandes ikke lenger inn i språkkvoter.

- **Full kjøring skriver en egen målerapport for hvert språk.** Uten
  språkbryter prøves bevisst tysk og engelsk; `--alle-sprachen` krever hele
  tolv-språks-korpuset og avbryter før det første dokumentet hvis et språk
  eller et tilfelle mangler. Likelydende resultater ligger i separate
  språkmapper. Totalrapporten nevner ved siden av den vektede treffkvoten
  også det uvektede gjennomsnittet av språkkvotene.

- **Den åpne språksammenligningen viser nå også sin faktiske grense.** I den
  faste kjøringen med tekstgjenkjenning fjerner tysk og engelsk 218/218
  kjente angivelser uten falske treff. Fulltesten med tekstgjenkjenning og
  Høy-nivå fjerner 1 255/1 308 angivelser med 17 falske treff; elleve språk
  når 100 prosent, hindi 51 prosent. Tidligere fullkvoter bygde på ulike
  dokument- og målmengder og er ikke sammenlignbare med den nye matrisen.

## 0.10.34-alpha.20260819 – 19. august 2026

### Rettet

- **Navn som forekommer flere ganger forblir tilgjengelige i sidepanelet
  etter en enkelt tilbakehenting.** Tidligere forsvant hele navnelinjen
  allerede etter det første tilbakehentede `[NAME]`-stedet. Flere steder med
  samme navn ble dermed stående som plassholder og ble til og med
  midlertidig blokkert, inntil andre navn var hentet tilbake. Nå forsvinner
  linjen først etter det siste stedet; allerede tilbakehentet klartekst blir
  likevel ikke automatisk anonymisert på nytt. Dette gjelder også for en
  delvis vellykket samlet tilbakehenting og for rammeverktøyet i PDF-er.

- **«Angre erstatning» fungerer også fra Office-sidevisningen.** Den
  synlige siden er der bare en flyktig PDF-forhåndsvisning; nå endres
  korrekt Word-, tabell- eller presentasjonsdokumentet under, og deretter
  fornyes forhåndsvisningen.

- **Tilbakehentingen henter nå også de skjulte motstykkene til en verdi
  fullstendig tilbake.** I Word-, OpenDocument-, Excel- og
  PowerPoint-filer kan de samme angivelsene i tillegg ligge i formler,
  kommentarer, diagrammer, feltverdier, alternativtekster og
  henvisningsmål; HTML, EML og MSG fører dem dessuten i attributter, JSON,
  meldingshoder og vedlegg. Tidligere ble en del stående som plassholder,
  avhengig av format. Nå kan hver angivelse som tilbys i treffområdet,
  hentes tilbake uavhengig og i vilkårlig rekkefølge. Bevisst fjernede
  metadata, endringslogger og transporthoder forblir av
  sikkerhetsgrunner fortsatt fjernet.

- **Ved tilbakehenting fra bilder blir det ikke lenger stående en svart
  kantlinje.** Høyre og nedre kant av en ramme ble ved kopiering fra
  originalen lagt ut ett bildepunkt for knapt. Koordinatene stemmer nå
  overens med sladdingen.

### Forbedret

- **Frigivelseskontrollen sender nå hver av de 22 støttede filendelsene
  gjennom en fullstendig rundtur.** Innholdsrike filer renses, alle
  tilbudte verdier gjenopprettes og deretter kontrolleres de grundig. I
  tillegg kommer ekte sidepanelbetjening, pikselnøyaktige bildesammenligninger
  og en synlig LibreOffice-gjengivelse av alle sju kontorformater. De små
  regresjonstestene forblir der de dekker et eget feil- eller
  sikkerhetstilfelle; en påvist dobbel HTML-kontroll og testen av den
  fjernede svart-hvitt-modusen er bortfalt.

- **Det fullstendige målekorpuset for denne versjonen ligger klart for
  etterkontroll.** Pakken inneholder 294 syntetiske dokumenter i tolv
  formater og tolv språk, 2 564 kjente angivelser, fire maskinlesbare
  fasitlister og en veiledning. Nedlastingen på kvalitetssiden bruker et
  innholdsavhengig filnavn, slik at nettlesere ikke ved et uhell leverer en
  eldre versjon fra hurtigbufferen.

## 0.10.33-alpha.20260819 – 19. august 2026

### Nytt

- **Også i bildefiler kan enkeltsteder nå hentes tilbake fra originalen.**
  Rammeverktøyet «Hent tilbake original» kopierer bildepunktene på samme
  posisjon tilbake fra den uberørte kildefilen. Veien forblir sperret hvis
  kilden mangler eller har andre bildemål; dermed kan ikke innhold fra et
  forskjøvet sted settes inn.

### Forbedret

- **Manuelle sladdefelt fester seg som standard til tekstlinjer.** Et drag
  over flere linjer skaper ett jevnhøyt felt per linje og lar
  mellomrommet mellom dem stå fritt. For underskrifter, grafikk og andre
  spesialtilfeller skrur «Fri ramme» tilbake til selvvalgt høyde.

- **Redigeringsprogrammet forklarer neste håndgrep direkte over
  dokumentet.** Henvisningen skifter med dokumenttype og verktøy og sier om
  et ordklikk, et tekstutvalg eller en ramme forventes. I tillegg viser
  verktøy, musepeker og direkte forhåndsvisning allerede før slippet hva som
  vil skje.

### Fjernet

- **Den feilutsatte svart-hvitt-utdataen ble fjernet.** I enkelte PDF-er ble
  usynlige tekstfelt liggende forskjøvet i forhold til den rasterte siden;
  den tilsynelatende filforminskingen var ikke verdt denne sikkerhets- og
  fremvisningsrisikoen. Vanlig PDF-rensing og målrettet rastrering av
  problematiske sider forblir uendret.

## 0.10.32-alpha.20260819 – 19. august 2026

### Nytt

- **Mappeovervåkingen kjører nå virkelig i bakgrunnen.** Inngang, utgang og
  regler står på en egen side under «Innstillinger». Den startes og stanses
  via Maskuro-ikonet i oppgave- eller menylinjen; oppføringen vises bare med
  lisensen frigitt for dette. Innstillingsvinduet kan deretter lukkes og
  hovedvinduet legges i ikonet, uten å avslutte overvåkingen.

- **Etterredigeringsprogrammet har nå en varig læringsmodus-bryter.** Den
  står i treffområdet og i menyen «Verktøy». Slås den av, vises verken ved
  tilbakehenting eller etter manuelle rettelser spørsmål om å opprette egne
  regler. Maskuro husker valget for alle fremtidig åpnede dokumenter; selve
  tilbakehentingen fungerer uendret.

### Rettet

- **Den store tilleggsmodellen lar seg laste ned igjen.** Det offentlige
  lagringsstedet avviste Pythons generelle standardidentifikasjon med 403.
  Modellhentinger bruker nå den samme utpekte Maskuro-nettveien som de
  øvrige egne tjenestene; den knapt 596 MB store filen og sjekksummen
  forblir uendret.

- **En maksimert sammenligningslupe blir ikke lenger hengende som en smal
  stripe ved øvre kant ved dokking.** Før dokking normaliseres dens frie
  vindustilstand. En lagret maksimert tilstand føres også ved neste åpning
  tilbake til en endrbar størrelse.

- **En samlet tilbakehenting henter i tabeller og andre tekstformater nå
  virkelig alle valgte verdier tilbake.** Ved anonymiserte plassholdere som
  `[EMAIL]` skrev Maskuro tidligere verdiene etter hverandre. Så snart den
  første var erstattet, rykket numrene på alle gjenværende funnsteder
  frem, men den allerede beregnede planen viste fortsatt til de gamle
  numrene. Dermed kom bare en del av utvalget tilbake. Nå skrives alle
  valgte verdier av samme plassholder samlet og med stabile
  funnstedsnumre. Blir et sted først entydig gjennom en annen tilbakehentet
  verdi, kontrollerer Maskuro det på nytt i samme trekk – rekkefølgen på
  utvalget spiller dermed ingen rolle lenger.

- **«Angre erstatning» utelater ikke lenger valgte verdier i PDF-er.** Sto
  en plassholder svært tett bak et annet ord, eller hang det i originalen
  et komma rett ved verdien, kunne posisjonskontrollen feilaktig tilordne
  naboordet henholdsvis skilletegnet til verdien. Ved samlet
  tilbakehenting ble da enkelte plassholdere og trefflinjer stående.
  Kontrollen retter seg nå etter den faktiske ordbegynnelsen og tar også
  hensyn til en avvikende sidedreining mellom original og resultat.

- **Tilbakehentet PDF-tekst beholder nå sin opprinnelige størrelse.**
  Tidligere tjente den allerede mindre satte plassholderen som målestokk;
  i tillegg gjaldt også for originalteksten den øvre grensen på 11 punkt
  ment for plassholdere. Nå overtas originalboks og originalskriftstørrelse
  fra kildefilen – ved rammeverktøyet like mye som ved tilbakehenting fra
  treffpanelet.

### Forbedret

- **Kontrollhenvisningen navngir nå restrisikoen klarere.** Den sier
  uttrykkelig at Maskuro kan overse data eller behandle angivelser feil, og
  oppfordrer før hver publisering eller videreformidling til fullstendig
  kontroll og om nødvendig manuell rettelse. Dette gjelder også teksten fra
  utklippstavlen og er fullstendig gjennomført i alle 17 oversettelser.

- **Kontrollprotokollen starter nå også innenfor sine linjer uten
  brukernavn.** Selve protokollen forblir avslått inntil et selskap
  bevisst aktiverer den. Deretter står det uten ekstra
  virksomhetsforvaltning verken i en linje eller i navnet på en sentral
  månedsfil et brukernavn; der tjener et ikke-gjettbart pseudonym, kun
  utledet fra den tilfeldige lokale profilhemmeligheten, til sikker
  atskillelse. Lisensdialogen anbefaler ikke lenger aktiveringen, forutsetter
  «Uten protokoll» og henviser på forhånd til bedriftsråd,
  personalrepresentasjon og personvern.

- **Erstatning navngir nå det den erstatter.** Et markert navn blir til
  `[NAME_3]`, et sted til `[ORT_1]`, et telefonnummer til `[TELEFON_2]` –
  i stedet for at alt som før ble til `[BEGRIFF_n]`. Typen gjenkjennes ved
  klikket; er den ikke entydig – et vanlig ord, eller et navn *og* et sted
  i ett utvalg –, blir det stående ved det generelle begrepet. En
  plassholder som hevder en type som ikke stemmer, ville vært verre enn
  en som ikke nevner noen.

- **Verktøyene i etterredigeringsvinduet har nå en tast.** **S** sladder,
  **E** erstatter, **Z** henter tilbake originalen, **V** pikselerer. I
  tekstvisningen virker de umiddelbart på markeringen, i sidevisningen
  velger de verktøyet. **Bokstavene følger språket** du betjener programmet
  på – engelsk B/R/O/P, italiensk O/S/R/P –, for en huskeregel hjelper bare
  på eget språk. Tasten står på knappen. Den som skriver i søkelinjen akkurat
  nå, skriver videre bokstaver – der virker de ikke.

- **Programmet melder én gang om dagen hvilken tilstand det kjører i – uten
  noen identifikasjon.** Med dette teller vi hvor mange installasjoner som
  brukes og hvordan det fordeler seg på prøveperiode, gratisnivå og lisens.
  Ut går tilstand, operativsystem, versjon, kanal, land, språk, miljø og
  gjenkjenningsnivå – **ingenting om dokumentene dine og ingenting som
  maskinen din kan gjenkjennes på**. To meldinger fra deg ser for oss ut
  som meldinger fra to forskjellige personer; en enkelt sti lar seg ikke
  spore ut fra dette. Hva som nøyaktig sendes og hvordan det slås av, står
  i personvernteksten under punkt 5.

- **Tverrmatede sider står nå av seg selv riktig vei.** Et ark som ble
  skannet skjevt uten å registrere det, gjenkjenner etterredigeringen ut
  fra tekstløpet og retter opp visningen. Der dette ikke går – ved en ren
  skanning uten leselig tekst –, dreier to nye oppføringer i menyen
  «Visning» manuelt (Ctrl+Shift+L og Ctrl+Shift+R). Bare visningen dreies:
  Ved filen endres ingenting, og sladding treffer fortsatt nøyaktig stedet
  man klikker på.

- **Den lokale utgaven fører nå sine lisenser fullstendig og synlig med
  seg.** Byggingen fastslår de faktisk medfølgende Python-pakkene, legger
  lisenstekstene deres samt versjonsoversikt under `lizenzen` og avbryter
  ved et hull. Også Qt, Tesseract og ansiktsmodellen har sine nødvendige
  tekster; betingelsene for Maskuro selv følger med som lisensavtale.

- **Man ser nå i hvilken plassholder skrivemerket står.** Den som klikker i
  en plassholder, ser den lyse helt opp – inkludert klammer og nummer.
  Knappen «Hent tilbake utvalg» virket allerede før ved et enkelt klikk;
  bare var det ikke synlig hvilket merke den traff. Lyset blir stående
  også når musen flytter til knappen.

- **Musepekeren sier nå hvilket verktøy som er valgt.** Fire verktøy deler
  samme flate og samme gest; frem til nå så alle like ut. Trådkors betyr
  sladde, lukket hånd erstatt, åpen hånd hent tilbake.

- **Et preparert Office-dokument avviser nå programmet selv.** En Word-,
  Excel- eller OpenDocument-fil kan ha med instruksjoner som ved åpning
  henter en fremmed fil fra maskinen din inn i teksten sin eller fyller
  opp arbeidsminnet. Begge deler ble også tidligere avvist – men av det
  innebygde XML-biblioteket, ikke av Maskuro. Nå avgjør programmet det
  selv, uavhengig av hvilken versjon av dette biblioteket som ligger i
  pakken. For vanlige dokumenter endres ingenting.

### Rettet

- **Treffpanelet fjerner nå sladdede plassholdere.** Ble for eksempel
  `[NAME_1]` sladdet i etterredigeringsvinduet, ble verdilinjen dens
  tidligere stående til høyre, selv om det ikke lenger fantes et slikt sted
  i dokumentet. Linjen faller nå bort med det siste funnstedet; forekommer
  samme plassholder fortsatt et annet sted, blir den stående.

- **Ved tilbakehenting på en dreid side blir naboordet nå stående.** Sladdestripen
  stikker med hensikt litt utenfor teksten; allerede denne smale kanten
  kunne tidligere ta med seg et tilstøtende ord som «i». Nå teller bare en
  tydelig overlapping, ikke berøring ved kanten.

- **En andre erstatning på samme linje tok med seg etterleddet.** Den som
  erstattet «Sachbearbeitung Quaxi Blubbo übernimmt» to ganger etter
  hverandre, fikk «Sachbearbeitung [ORT_1] [ORT_2]» – ordet bak var borte
  uten erstatning, uten noen melding. Årsaken var plassholderen ved siden
  av: Resten av linjen begynner etter den første erstatningen med et
  mellomrom, og søket etter tekststedet dens grep tak i naboens
  lukkeklamme. Deretter var alt forskjøvet ett tegn. Berørt var hver linje
  der det ble erstattet eller sladdet to ganger – også ved tilbakehenting
  ved siden av.

- **Erstatning sladder ikke lenger når plassholderen er for lang.** Var det
  ikke plass til `[BEGRIFF_2]` ved siden av ordet, ble området tidligere
  malt sort – og dermed var det heller ikke lenger synlig at det en gang
  sto noe der, langt mindre å hente tilbake. Nå skrives en kortere
  skrivemåte: `[BEGR_2]`, `[BE_2]`, om nødvendig `[B_2]`. Løpenummeret
  forblir på hvert trinn – ved det finner tilbakehentingen stedet igjen.
  Bare der ikke engang den korteste passer, blir det stående ved stripen.

- **Erstatning lot teksten stå igjen når det allerede var sladdet på samme
  linje.** Den som i etterredigeringsvinduet hentet tilbake et navn fra
  originalen, erstattet fornavnet derav (der var ingen plass – det ble en
  stripe) og deretter erstattet etternavnet, fikk plassholderen satt inn,
  men navnet **ikke fjernet**. Dette ble bare oppdaget ved advarselen fra
  etterkontrollen. Årsaken var selve linjen: Etter den første sladdingen
  begynner resten med et mellomrom, og søket etter tekststedet fant
  ingenting å feste seg i. Dette rammet hver andre sladding på samme
  linje.

- **En påslått utvidet gjenkjenning uten modellen sin faller nå i øynene.**
  Avkrysningen kunne være satt mens modellen manglet – innstillingene
  gjelder for hver installasjon, men modellen ligger ved siden av
  programmet. Rensingen kjørte da uten dette nivået, uten et ord om det.
  Nå sier avkrysningen at modellen mangler, og resultatet bærer en
  advarsel. Det en gang tatte valget forblir lagret: Så snart modellen er
  lastet ned, virker den igjen.

- **Ved anonymisering hentes nå det riktige begrepet tilbake.** Den som
  erstattet flere begreper for hånd og deretter hentet ett av dem tilbake,
  fikk alltid det **første** – av «Schmidt» ble det «Müller». Tilordningen
  husket bare én erstatning per plassholder, og ved anonymisering bærer
  alle samme plassholder; det andre og hvert ytterligere begrep falt
  dermed bort. Nå får hver verdi sin egen linje – også i listen over
  erstatninger, som tidligere var for kort.

- **I tabeller lar det seg nå også hente tilbake.** I en CSV eller
  personalliste står plassholderne direkte ved siden av hverandre, bare
  skilt av et semikolon. Frem til nå kunne programmet ikke fastslå hvilken
  verdi som hadde stått hvor, og avviste – ved `[NAME]` gikk det, ved
  `[GEBURTSDATUM]` og `[TELEFON]` ikke. Nå deler den opp linjen ved alle
  plassholderne. Blir et sted virkelig flertydig, avviser den fortsatt: En
  feilaktig tilbakeskrevet verdi ville vært verre enn et uteblitt svar.

- **Og avslaget er nå synlig.** Det sto i dempet grått ved nedre vinduskant,
  og setningen var så lang at den ble avkuttet – det så ut som om
  ingenting skjedde. Setningene er forkortet, og linjen lyser noen
  sekunder i varselfargen.

- **En tilbakehenting holder nå også etter neste inngrep.** Den som ved
  anonymisering hentet tilbake flere steder og deretter erstattet noe
  annet, fant alle tilbakehentede steder igjen erstattet og måtte begynne
  på nytt. Årsaken var tilordningen: Den beholdt verdien, og den
  automatiske sammenligningen for ensartede plassholdere hentet den
  tilbake ved neste skriving. Nå gjelder: Det du henter tilbake, forblir
  tilbakehentet – andre steder med samme verdi rører dette ikke ved.

- **I tekst-, Word-, Excel- og e-postfiler holder nå virkelig ett klikk i
  plassholderen.** Meldingen om dette sto allerede i forrige versjon, men
  knappen «Hent tilbake utvalg» forble sperret så lenge ingenting var
  nøyaktig markert – man kom altså slett ikke til veien som ville satt
  utvalget selv.

### Rettet

- **Kontrollprotokollen røper ikke lenger filnavnet.** Den fører bevisst
  filer som en streuverdi i stedet for i klartekst, fordi et filnavn røper
  klient og tvistegjenstand. Denne streuverdien lot seg imidlertid
  bekrefte ved gjetting – en sti er ikke et tilfeldig tall. Nå går en
  tilfeldig verdi for denne installasjonen inn i beregningen: Telling og
  atskillelse i protokollen fungerer fortsatt, etterregning utenfra ikke
  lenger.

## 0.10.31-alpha.20260819 – 19. august 2026

### Forbedret

- **Også i tekst- og tabellfiler lyser plassholderen rødt ved pekevisning.**
  Tidligere fantes den røde forhåndsvisningen bare på en PDF-side. Nå viser
  begge visningene det samme: Det som er rødt, rammes av det neste trekket –
  og ett klikk inni er nok for å hente tilbake.

- **Ett klikk på et ord er nok – rammen setter redigeringsprogrammet selv.**
  I etterredigeringsvinduet måtte man tidligere dra en ramme over hvert
  sted. Nå holder det med ett klikk: Rammen legger seg rundt ordet og
  forblir gripbar, kan altså fortsatt utvides eller flyttes. Ved pekevisning
  med musen lyser ordet allerede rødt, slik at man ser på forhånd hva
  klikket ville treffe. Der det ikke står noe ord, drar man som før en
  ramme.

- **Man trenger ikke lenger sikte nøyaktig med rammen.** Den som drar en
  ramme over en plassholder eller en sladding, mener alltid hele stedet –
  aldri halvparten av det. Rammen vokser derfor selv til det hele den
  berører: til hele plassholderen, hele feltet eller, på et innskannet ark,
  til hele den sladdede flaten. Mindre enn den dratte rammen blir den
  aldri.

- **Sladding skjer nå ordvis.** En ramme over halve et ord sladdet
  tidligere også bare halvparten – og et halvsladdet navn er fortsatt et
  navn. Berørte ord faller nå helt bort; naboen forblir urørt.

- **I tekst og tabeller holder det med ett klikk i plassholderen.** «Hent
  tilbake utvalg» krevde tidligere at man markerte plassholderen nøyaktig,
  inkludert klammene. Nå holder det å sette pekeren inni; utvalget hopper
  synlig til hele plassholderen.

- **Belgia har kommet til som land.** Kan velges i innstillingene; da
  gjenkjennes belgiske telefonnumre, Rijksregisternummer (med kontrollsiffer),
  BTW-/foretaksnummer (med kontrollsiffer), adresser på begge offisielle
  språk og postnummer med sted. Tidligere ble belgiske telefonnumre stående,
  fordi landet slett ikke fantes i katalogen.

- **Oppdateringskanalen sier nå hvor tidlig du får nyheter – ikke hvor
  langt.** Den som sto på «Testversjon», fikk ikke en gang en ny forhåndsvisning
  eller en ny stabil versjon tilbudt, og måtte bytte kanal manuelt for i det
  hele tatt å få vite om det. Nå tilbys også alt som er mer pålitelig:
  Testversjon tar testversjoner, forhåndsvisninger og stabile versjoner,
  Forhåndsvisning tar forhåndsvisninger og stabile. Aldri omvendt – på
  Forhåndsvisning tilbys ingen testversjon, selv om den er nyere.

- **I innstillingsvinduet står linjene lenger fra hverandre.** De fire
  sidene brukte egne avstander i stedet for rutenettet som gjelder i resten
  av programmet; særlig på siden «Gjenkjenning» sto avkrysningsboksene
  merkbart for tett.

### Rettet

- **Utfylte PDF-skjemaer vises ikke lenger tomme ved manuell redigering.**
  Maskuro gjør for dette utelukkende den flyktige arbeidskopien til
  statiske sider: Innførte verdier blir synlige og lar seg virkelig
  sladde; leselige skjemafelt blir ikke stående skjult igjen i filen.
  Originalen forblir interaktiv og uendret. Dette gjelder nå også for
  dynamiske XFA-skjemaer: En XFA-kapabel PDFium bygger først opp verdier og
  sideskift, deretter oppstår en ny PDF utelukkende av statiske bildesider.
  Mislykkes XFA-oppbyggingen, blir filen sikkert avvist i stedet for å
  åpnes tilsynelatende tom.

- **«Avbryt» virker nå også under den mer nøyaktige gjenkjenningen.**
  Tidligere sperret knappen seg ved klikk, men kjøringen fortsatte å
  regne til siste blokk – for en lang fil er det minutter uten utvei, og
  knappen så da ut som om den hadde virket. Nå avsluttes kjøringen ved
  neste blokk.

- **I CSV-filer blir navn nå funnet også når det ikke står mellomrom foran
  dem.** I `P-1000;Brunnthaler, Elisabeth` klistrer ansattnummeret seg over
  semikolonet til navnet, og for gjenkjenningen var dette ett eneste ord
  uten navn i seg – i personallister ble dermed hele navnet stående, alt
  etter linje. Telefonnumre, formler og filens kolonneantall forblir
  uberørt av dette.

- **Et navn der både for- og etternavnet har bindestrek, blir nå
  gjenkjent.** «Marie-Luise Habsburg-Ott» ble stående midt i setningen,
  mens «Dragan Mitrović» ble funnet i samme setning – nettopp kombinasjonen
  av to koblede halvdeler ble oversett av språkmodellen. Koblede saksord som
  «Nord-Süd-Verbindung» eller «Software-Entwickler» forblir uberørt av
  dette.

## 0.10.30-beta.1 – 18. august 2026

### Forbedret

- **Skriftstørrelsen i tekstvisningen kan nå stilles inn synlig.**
  Glidebryteren nederst til høyre, som tidligere bare zoomet i
  sidevisningen, stiller nå i etterredigeringsvinduet ved tekst- og
  kontorfiler skriftstørrelsen (50–300 %) – likeledes «Forstørr»/«Forminsk»
  i menyen Visning. Ctrl+musehjul kunne dette alltid, men det visste bare
  den som hadde prøvd det; nå går glidebryter, visning og hjul sammen.

- **I det mørke utseendet ligger nå et hvitt ark på mørk arbeidsflate.**
  Tidligere var det omvendt: Rundt arket ble en lys flate stående, og
  selve teksten sto lys på mørk. Nå forblir arket i begge utseendene
  papirhvitt med svart skrift – som en PDF-side, som jo heller ikke blir
  mørk i mørk modus – og flaten rundt er mørk.

### Rettet

- **Etter en sladding midt i setningen forsvinner ikke lenger resten av
  setningen.** Den som i etterredigeringsvinduet gikk tre ganger til samme
  sted – erstattet, sladdet, deretter «Hent tilbake original» –, fikk
  setningsbegynnelsen slettet: Av «Henvendelser rettes til
  regnskapsavdelingen.» ble det «til regnskapsavdelingen.», uten
  advarsel. Berørt var hvert sted der det allerede en gang var fjernet noe
  midt fra en linje.

- **En oppstartsfeil river ikke lenger med seg avslutningen.** Når
  oppbyggingen av hovedvinduet avbrytes, krasjet deretter også
  avslutningen via oppgavelinjeikonet – og denne andre feilen dekket i
  feilrapporten over den egentlige årsaken. Nå avslutter programmet seg
  rent også fra et halvbygd vindu, og de lagrede innstillingene forblir
  urørt av det.

- **«Før/etter» hopper ikke lenger til dokumentbegynnelsen.** Den som
  hadde rullet nedover i etterredigeringsvinduet og byttet til originalen
  for sammenligning, havnet igjen helt øverst – og måtte finne stedet
  manuelt igjen. Visningen blir nå stående på samme linje, i begge
  retninger.

- **Ved sladding ble den siste bokstaven stående på blokkjustert-linjer.**
  Når en tekstkommando tegner flere glyfer enn lesebiblioteket melder
  tegn – den svelger gjerne et mellomrom i blokkjustering –, forskjøv
  tilordningen seg med én, og av «Dr. Michael Handler aus Willendorf» ble
  det «[NAME] r aus f»: to gjenværende bokstaver midt i den rensede
  setningen (funnet i en ekte rådsprotokoll). Tilordningen etterkontrolleres
  nå mot selve ordlyden i kommandoen, der denne er leselig – det gjettes
  ikke lenger der.

- **«Lerchenfelder Gürtel 43/12» ble bare halvveis fjernet.** Adressemønstrene
  kjente verken Gürtel, Kai, Lände, Zeile, Markt eller Graben som
  gategrunnord, og husnummeret fikk ikke bære skråstrekdeler (43/12,
  Haus/Tür) – nummeret ble stående ved siden av plassholderen. Begge deler
  supplert; wienske og salzburgske adresser faller nå helt.

- **Lagrede nettsider forblir kjørbare etter rensing.** Adressene som
  lazy-loading legger i data-attributter (`data-lazy-src`,
  `data-lazy-srcset`), ble erstattet som lenker – på en ekte kommuneside
  seksten stykker – og bildene på siden lastet deretter ikke lenger. Weblenker
  blir nå stående der, som i `src` og `href` også; navn, e-postadresser
  og telefonnumre i data-attributter erstattes fortsatt.

- **Japanske og koreanske dokumenter kjørte som kinesisk.**
  Språkgjenkjenningen kastet alle tre skriftsystemene i samme bås, fant i
  japansk tekst (uten mellomrom) og koreansk (med sammenklistrede
  partikler) ingen funksjonsord – og tok da bare rett og slett det første
  CJK-språket i katalogen. En japansk rådsprotokoll og en koreansk
  møteprotokoll ble dermed lest med den kinesiske modellen. Nå avgjør
  selve skriftbildet: Kana betyr japansk, hangul betyr koreansk.

- **Ytterligere feilgrep fra feltestingen på ti ytterligere språk:** Embeter
  som «Primar», «Gradonačelnik», «Ordfører», «Başkanı» eller «Δήμαρχος»
  gjelder ikke lenger som personnavn; tyrkiske feltmerkinger («Adı»,
  «Soyadı») og greske samtaleord («Ωραία», «Βεβαίως») faller ikke lenger;
  vedtaks- og paragrafnumre med dato («323/25-6-2008», «27 30.09.2024») er
  ikke lenger telefonnumre; og setningsrester med punktum («10.An», «T.U.EE»,
  «…pa») erstattes ikke lenger som weblenker.

### Nytt

- **Kontrollrapporter automatisk ved ønske.** En avkrysning i innstillingene
  (siden «Program») legger etter hver rensing selv en kontrollrapport-PDF
  – med tidsstempel i navnet, i en egen mappe, aldri ved siden av
  resultatet. I ettertid lar et ark seg ikke generere; den som trenger det
  til arkivet, har det dermed alltid. Forhåndsinnstilt er lagringen av.

- **Kontrollprotokollen kan nå slås på i programmet.** Ved innlesing av en
  firmalisens spør Maskuro én gang om protokollen skal føres – en
  dokumentasjon bærer bare hvis den kjører fra begynnelsen. Til dette
  finnes en bryter i innstillingene (siden «Program», synlig med
  firmalisens eller i prøveperioden); forvaltningens vorgavefil gjelder
  fortsatt og kan tvinge verdien som før. En egen protokollinje «påslått»
  fastholder siden når det føres – dermed er også begynnelsen av
  opptaket belagt og signert. Forhåndsinnstilt forblir protokollen av.

- **Nøkkeltall-klaffen viser hva KI-nivået har gjort.** En ny linje nevner
  hvor mange usikre treff modellen har vurdert, beholdt og forkastet, og
  hvor mange den i tillegg har funnet – tidligere var arbeidet dets
  usynlig hvis man ikke klikket på hver verdi i
  etterredigeringsprogrammet. Bare tall, aldri verdier eller
  begrunnelser; uten KI-arbeid vises linjen ikke.

- **Tilbakehenting går nå også i e-poster og HTML-sider.** I `.eml`,
  `.msg` og lagrede nettsider lot en plassholder seg tidligere ikke angre
  – applikasjonen sa det ærlig, men nettopp e-post er formatet med flest
  personopplysninger. Nå bærer tilbakehentingen der like mye: fra
  treffpanelet, med markert utvalg og også ved anonymiserte
  plassholdere. Den usynlige HTML-grenen til en e-post (det Outlook
  virkelig viser) trekkes med, slik at visning og melding sier det
  samme.

- **Treffpanelet henter også anonymiserte verdier tilbake – per verdi.**
  «Angre erstatning» var tidligere sperret ved anonymiserte filer, fordi
  «[NAME]» står for alle navn samtidig. Nå slår tilbakehentingen opp i
  originalen hvilket sted som hører til hvilken verdi – i PDF ved
  koordinatene til funnstedet, i tekstvisningen via sammenligning med
  originalen – og henter nøyaktig stedene til den valgte verdien
  tilbake. Linjene til de øvrige verdiene blir stående.

- **Også anonymiserte plassholdere lar seg hente tilbake enkeltvis.** Ved
  anonymisering heter alle angivelser av en type det samme – «[NAME]»
  står for hver person, og tidligere het det derfor: enkeltvis
  tilbakehenting går ikke. Nå slås det opp i originalen, som uansett
  ligger ved siden av resultatet: Marker plassholderen i tekstvisningen
  og velg «Hent tilbake utvalg» – tilbake kommer nøyaktig dette stedet
  med nøyaktig verdien dets. Lar verdien seg ikke leses utvetydig fra
  originalen, sier applikasjonen det, i stedet for å gjette. En
  tilordningsfil oppstår fortsatt ikke ved dette.

- **Etterredigeringsvinduet åpner seg selv etter rensingen.** Ingen
  verktøy finner alt – derfor hører det kontrollerende blikket på
  resultatet til normaltilfellet, ikke til et ekstra klikk. Den som ikke
  vil ha dette, slår det av i innstillingene under «Gjenkjenning» («Vis
  resultatet etterpå i etterredigeringsvinduet»).

### Forbedret

- **Landvalget står nå på nytt på «automatisk».** Tidligere gjaldt fra
  fabrikken språkområdet til grensesnittet – på en tysk maskin ble altså
  også nederlandske eller franske dokumenter bare renset med
  DACH-gjenkjennerne, og en adresse som «Universiteitslaan 1» ble stående
  (funnet i ekte, offentlige rådsprotokoller). Nå retter landvalget seg
  etter dokumentets språk; den som har gjort et fast valg i
  innstillingene, beholder det.

- **Mindre feilaktig sladdet.** En rekke feilgrep, målt mot kontrollkorpuset
  og mot ekte møteprotokoller på seks språk, faller bort: Firmanavn med
  rettsform («Musterfirma GmbH») gjelder ikke lenger som person eller
  sted, men som organisasjon; hilsenformler og nakne tiltaleformer
  («Saygılarımızla», «Buenas tardes», et alenestående «Frau») er ikke
  lenger navn; embeter («Bürgermeister», «Sindaco», «Alcalde») blir
  stående; lov- og vedtaksnumre («39/2015») og beløp med tusenpunktum
  («330.000») er ikke lenger telefonnumre; setningsbegynnelser som
  «Envíame» eller «Estarei» faller ikke lenger som navn; et treff over en
  tom linje teller ikke lenger som navn. Fakturanummeret til en faktura
  forblir som bilagsangivelse – kundenummer og saksnummer faller fortsatt.

- **Før nedlasting av KI-modellen står det nå hva den er god for.**
  Nedlastingsdialogen nevner oppgavene til modellen – vurdere
  grensetilfeller, finne flere navn, foreslå regler og profiler – og sier
  åpent at den ikke er en chat-assistent. FAQ besvarer samme spørsmål
  utførlig («Hva kan KI-nivået – og hva kan det ikke?»), på alle
  språkversjonene.

### Rettet

- **Kontrollrapport-PDF-er fra kommandolinjen lar seg nå søke gjennom.**
  Under Windows startet den hodeløse PDF-veien uten en eneste skrift –
  hvert tegn ble tegnet som en erstatningsboks, og arket bar ingen
  leselig tekst: Den som ville søke i det eller kopiere ut noe, fant
  ingenting. Nå laster rapporten i dette tilfellet ned systemets
  skrifter; teksten er innebygd og leselig. Rapporter fra vinduet var
  aldri berørt av dette.

- **«Hent tilbake original» over flere linjer i en skanning lot svarte
  striper stå igjen mellom linjene.** På en til bilde omgjort side ryddet
  rammen bare selve linjebåndene; restene av den tidligere sladdingen ble
  stående i mellomrommene mellom dem. Nå deler den dratte rammen seg
  fullstendig opp på linjene.

- **En andre ramme over en plassholder lot en rød rest bli stående.**
  Plassholderen er nesten alltid bredere enn ordet den representerer; den
  som deretter sladdet over samme sted, traff bare begynnelsen dens – igjen
  ble et bruddstykke som «RIFF_1]» midt i setningen, og tilbakehentingen
  satte deretter originalteksten inn på dets sted i stedet for ordets. En
  avkuttet plassholder faller nå alltid helt.

- **På en dreid side slettet sladding over en plassholder en uinvolvert
  setning.** Den etterhånden tegnede plassholderen ble ved fjerning
  forvekslet med teksten foran: Den selv ble stående, advarselen «står
  fortsatt i dokumentet» kom – og et annet sted på siden forsvant uten
  erstatning en setning som ikke hadde noe med rammen å gjøre. En
  plassholder gjenfinnes nå via ordlyden sin; kjeden «erstatt, sladd, hent
  tilbake» går dermed opp også på tverrmatede sider.

- **Håndboken rådet på ti språk fortsatt til `python3-tk`.** I
  feilsøkingen sto det at tkinter kanskje manglet under Linux – et råd fra
  tiden før Qt-grensesnittet, som ikke hjelper noen lenger. Nå står det
  på alle versjoner samme avsnitt som på tysk: Det mangler
  systembibliotekene Qt trenger for fremvisningen.

- **Lisenskapittelet i håndboken var utdatert i alle seksten
  oversettelsene.** På ti språk kunne man der fortsatt lese at Windows
  Server trengte en firmalisens med serveradgang og at prøveperiode og
  gratisnivå ikke fantes der – siden en plass teller et menneske og ikke
  en maskin, er begge deler feil. Det manglet dessuten overalt
  opplysningene om når en belagt plass blir ledig igjen, at lisensen
  bekrefter seg regelmessig og hva som overføres ved det, og aktiveringen
  uten internett sto bare som kortversjon uten de tre trinnene og uten
  henvisningen om at maskinen deretter arbeider et år uten forbindelse.

- **Sju avsnitt om etterredigering manglet på ti språk.** Den som leste
  hjelpen på dansk, finsk, fransk, italiensk, nederlandsk, norsk, polsk,
  portugisisk, svensk eller spansk, fant verken sidevisningen for
  kontorfiler eller «Sladd manuelt» eller hele avsnittet om hvordan
  programmet lærer av en rettelse – med tabellen med de tre bredder. I
  «Hva som gjenkjennes» manglet de samme ti versjonene veien via
  merkingen i dokumentet.

- **Med innlest lisens startet ikke programmet lenger.** I stedet for
  vinduet kom «Programmet kunne ikke startes» – og det ved hver lisens,
  uansett hvilken. Årsaken var linjen i lisensvisningen som varsler kort
  før kontrollfristen utløper; den aksesserte noe som ikke var
  tilgjengelig der. Uten lisens – i prøveperioden og i gratisnivået –
  oppsto ikke feilen, derfor ble den først nå oppdaget.

- **I skjemaet blir feltnavnene stående.** «Geburtsdatum» og «Anschrift»
  forsvant med verdien sin: Plassholderen sto liten og rød på stedet til
  *feltnavnet*, feltet under forble tomt. Feltnavnet hører ikke til
  dataene – det blir nå stående, og plassholderen står der verdien sto.

- **Fremmedspråklige dokumenttitler tas ikke lenger for navn.** Over et
  italiensk skjema sto «FATTURA», over et spansk «PERMISO PARENTAL» –
  begge ble erstattet. Listen over skrivtypeord kjente bare de tyske
  motstykkene.

- **Fra en faktura forsvinner ikke lenger en post.** «Materialaufschlag
  1  84,00» ble tatt for en adresse og erstattet med en
  stedsplassholder – bilaget manglet deretter en linje. En linje som
  ender med et beløp, er en post og ingen adresse; ekte adresser
  («Hauptstraße 1  120,00») forblir uberørt.

### Endret

- **«Overvåk mappe …» og kommandolinjen er foreløpig ikke lenger der.**
  Begge veiene er bygget og fungerer, men ingen av dem er prøvd i
  praksis: Mappeovervåkingen har aldri sett en Windows-gjennomgang, og
  kommandolinjen gir et skript to dusin brytere i hendene, som aldri har
  kjørt hos noen bruker. Det som ubevoktet endrer dokumenter, skal ikke
  gjøre det ukontrollert – derfor er de trukket tilbake til gjennomgangen
  er tatt igjen. Menyoppføringen mangler, og `--wache` står ikke lenger i
  `maskuro --help`.

- **Åpent forblir det som bare leser og det som uansett trengs.** Søkelinjen
  (`--suchlauf`) og etterkontrollen (`--nachpruefen`) fortsetter å
  fungere på kommandolinjen – de endrer ingen fil. Likeledes oppstart via
  Utforsker, kontekstmenyen, utklippstavlen og vinduet; ved dette endres
  ingenting.

- **«Hent fra skanner» har nå et eget kapittel i håndboken.** Det sto
  tidligere til slutt i «Overvåk mappe». På Mac het rådet der å la en
  mappe overvåkes; nå heter det å dra de innleste sidene inn i vinduet.

### Rettet

- **«Hent tilbake original» over flere linjer ødela inndelingen.** En ramme
  over en plassholder, en uendret jobbtittel og en andre erstatning satte
  hele området inn på nytt som **én** linje – av tre linjer ble det én, og
  det som ikke lenger fikk plass, ble til en stripe. Nå hentes hver linje
  tilbake for seg.

- **Og uendret tekst forblir urørt ved dette.** Den som drar over en
  erstatning *og* vanlig tekst, får bare erstatningen tilbake; resten
  røres ikke. Også den siste resten av den gamle plassholderen forsvinner
  ved dette – tidligere ble lukkeklammen dens stående midt i setningen.

- **Ved erstatning blir ikke lenger rester av den gamle teksten stående.**
  I en fet overskrift sto det deretter «1. R[BEGRIFF_2]ige [BEGRIFF_1] …
  che» – plassholderen satt der, men stavelser fra originalen ved siden
  av. Nå ryddes området du rammer inn, ikke bare boksene til ordene i det.

- **En anonym plassholder hentes ikke lenger tilbake.** Ved anonymisering
  bærer hvert navn samme `[NAME]`. Tilbakehentingen tok den første beste
  oppføringen og skrev den på hvert funnsted – av «Georg Aigner» ble det
  «Anna Musterfrau», altså et feil navn i dokumentet. Nå står det der at
  det ikke lenger lar seg si hvilken angivelse som var ment; dokumentet
  forblir urørt.

### Nytt

- **«Hent tilbake original» virker nå også på en rastrert side.** Ble en
  side gjort om til et bilde, kom tidligere et avslag: Den tilbakehentede
  teksten ville havne under sidebildet. Nå ryddes stedet i bildet og
  teksten skrives på det – som en plassholder på en skanning. Innholdet
  kommer ved dette fra originalfilen, og den er ikke rastrert.

- **«Hent tilbake utvalg» står nå som egen knapp.** Det gikk allerede
  tidligere, men bare hvis man tilfeldigvis markerte en plassholder og
  trykte «Erstatt utvalg» – en funksjon man bare finner ved tilfeldighet,
  finnes ikke for brukeren.

### Endret

- **I ren tekst, CSV og Outlook-meldinger finnes det ikke lenger «Sladd
  utvalg».** Disse formatene kan ikke bære en stripe; knappen satte der en
  plassholder og sa det også – men en knapp som gjør noe annet enn den
  heter, hører ikke hjemme der.

- **Et verktøy sier nå fra når det ikke har noe å utrette på dette
  stedet.** En plassholder lar seg ikke erstatte en gang til, over en
  sladding settes ingen plassholder, og der originalen allerede står, er
  det ingenting å hente tilbake. Tidligere gjorde disse trekkene noe som
  så ut som en virkning, men ingen var det.

## 0.10.29-alpha.20260817 – 17. august 2026

### Rettet

- **I etterredigeringsvinduet virker nå hver ramme man drar.** Den som
  arbeidet to ganger på samme sted – først erstattet, så sladdet, så hentet
  tilbake originalen –, fikk sitt andre og tredje trekk til å forsvinne
  sporløst: Den fortsatt gripbare rammen fra forrige trekk fanget det opp.
  Det samme gjaldt ved verktøybytte, der til og med det gamle verktøyet
  stille fortsatte å virke.
- **En for smalt dratt ramme sier at den er for smal.** Tidligere lyste
  forhåndsvisningen et ord rødt, og ved slipp skjedde det ingenting,
  sporløst.

- **Outlook-meldinger lar seg endelig etterredigere.** En `.msg` viste i
  etterredigeringsvinduet «Dette formatet kan ikke vises her» – den var det
  eneste støttede formatet uten noen vei til manuell etterbehandling. Nå
  står avsender, mottaker, emne og meldingstekst navngitt i visningen og
  lar seg markere og erstatte som i ethvert annet tekstformat.

- **«Erstatt utvalg» holder seg til utvalget i en e-post.** Den som markerte
  et navn i brødteksten, mistet samtidig avsender og mottaker fra
  hodefeltene, og meldingen nevnte en annen plassholder enn den som sto i
  teksten. Nå erstattes den markerte verdien overalt – også i avsenderfeltet,
  hvis den står der – og ellers røres ingenting.

- **En ramme over flere linjer ødelegger ikke lenger teksten.** Tidligere
  oppsto én eneste plassholder ett sted: Av det avkuttede ordet ble en
  rest hengende igjen, og fra den andre linjen forsvant teksten uten
  erstatning – ingen plassholder, ingen strek, bare et hull. Nå får hver
  linje sin egen plassholder med verdien som virkelig sto der.

- **«Hent tilbake original» virker nå også etter en sladding.** Vinduet
  meldte suksess, og teksten kom aldri tilbake: Den svarte streken talte
  som en hindring, slik at det ikke lenger var plass til den tilbakehentede
  teksten. Streken viker nå unna, og den tilbakehentede teksten står svart
  som vanlig tekst – ikke rød som en plassholder.

- **«Hent tilbake original» på et urørt sted gjør ingenting lenger.** Den
  som dro rammen over tekst der ingenting i det hele tatt var endret, fikk
  teksten fjernet og satt inn igjen mindre og forskjøvet – meldingen sa
  suksess. Nå står det at det ikke er noe å hente tilbake.

### Nytt

- **Også i Word, Excel, PowerPoint, OpenDocument og tekst kan man sladde.**
  Tidligere fantes der bare «Erstatt utvalg»; en strek var forbeholdt
  PDF-visningen, uten at det var noen grunn til det. Der en strek ikke kan
  fremstilles – i ren tekst og i en Outlook-melding –, erstattes verdien
  som før av en plassholder, og det står også slik i meldingen.

- **Å markere en plassholder henter den tilbake.** I tekstvisningen (Word,
  Excel, PowerPoint, OpenDocument, tekst) holder det nå å markere
  plassholderen og trykke «Erstatt utvalg»: Den opprinnelige verdien kommer
  tilbake. Tidligere viste vinduet for dette til treffpanelet.

- **Talere i en møteprotokoll gjenkjennes nå også når navnet deres samtidig
  er et vanlig ord.** «Gruber: Overtagelsen skjer neste uke.» ble erstattet,
  «Bauer: Jeg er enig.» ble stående – etternavnet ser for gjenkjenningen ut
  som et substantiv. Merkelinjer av samme byggeform forblir urørt: Av
  «Obs: Anlegget skal slås av.» blir det ikke noe navn.

- **«Du bruker den nyeste versjonen» ble også sagt når det slett ikke kunne
  sjekkes.** Avviser oppdateringsserveren forespørselen – fordi det kom for
  mange forespørsler fra samme internettadresse eller fordi den selv nettopp
  har et problem –, sto programmet da fast på sin gamle versjon og hevdet
  at det var den nyeste. Nettopp det skjedde 17. august på en Mac: 0.10.25
  ble liggende, mens 0.10.28 hadde ligget klar i timevis.

  Nå sier vinduet hva som er i veien, oppgir klokkeslettet for neste
  ettersjekk – og påpeker uttrykkelig at det **ikke** er fastslått om ens
  egen versjon er den nyeste.

  Som regel skyldes det ikke ens egen maskin: Ved mange tilkoblinger deler
  mange kunder samme internettadresse, og serveren teller dem sammen.
  Derfor søker Maskuro i dette tilfellet versjonslisten via en **andre
  vei** og finner som regel likevel nye versjoner. Vedvarer avvisningen,
  får serveren stå i fred til det oppgitte klokkeslettet – selv om man
  trykker knappen en gang til; å mase forlenger bare sperren.

- **Mengdeangivelser blir ikke lenger tatt for stedsnavn.** I en
  tjenesteavtale forsvant «firedagersuke» bak en stedsplassholder – midt i
  avtalens gjenstand. Slike ordforbindelser av tall og bindestrek
  («tre-punkts-plan», «24-timers-vakt») blir nå stående. Adresser er
  unntatt fra dette: En «Zwei-Brüder-Weg» erstattes fortsatt.

## 0.10.28-alpha.20260817 – 17. august 2026

### Endret

- **Lisensplasser telles nå virkelig.** Tidligere meldte ingen arbeidsplass
  seg noensinne på lisenstjenesten – en tiplasslisens kjørte på et
  vilkårlig antall maskiner uten at noen fikk vite det. Nytt: Maskinen som
  starter programmet, tar en plass; en plass frigjøres av seg selv etter
  **sju dager uten oppstart**, slik at en ødelagt enhet eller en sluttet
  medarbeider ikke blokkerer noe permanent.

  Et lite overtrekk **vises bare og sperres ikke**: Opptil ti prosent over
  det innkjøpte antallet fortsetter alle å arbeide – den nye bærbare PC-en
  ved siden av den fortsatt påloggede gamle skal ikke bli en sak for
  kundestøtten. Den som kommer i tillegg utover det, faller tilbake til
  gratisnivået og får beskjed om det; maskinene som var der først, merker
  ingenting av det.

- **En kjøpt lisens bekrefter seg regelmessig.** Lykkes ikke det på **30
  dager**, gjelder gratisnivået inntil det lykkes igjen. Ingenting slås av,
  og fra en uke i forveien står henvisningen i vinduet. Så snart maskinen
  igjen kommer på internett, ordner dette seg av seg selv. Prøveperiode og
  gratisnivå melder fortsatt ingenting i det hele tatt – den som aldri
  kjøper, ringer aldri.

- **«Aktivér uten internett» virker endelig.** Aktiveringen ble tidligere
  riktignok kontrollert og lagret, men deretter lest av ingen lenger – den
  endret ingenting ved rettighetene. Nå er den utveien for maskiner uten
  nettilgang: Den varer **ett år**, deretter henter man seg en ny med en
  fersk forespørselskode. En enhet med internett trenger man til dette én
  gang i året – selve maskinen forblir varig frakoblet.

- **Aktiveringen går nå også fra kundekontoen** – under «Mine lisenser» på
  nettstedet. Der står også hvilke maskiner som er knyttet til lisensen
  din, og når plassene deres blir ledige igjen; det var tidligere ikke
  synlig noe sted. Siden uten pålogging forblir for alle uten shop-tilgang
  – den krever i tillegg e-postadressen fra bestillingen, slik at
  lisensnøkkelen alene ikke er nok.

- **Og i vinduet står det nå hvor forespørselskoden skal.** Papirveien sa
  «angi på en enhet med internettforbindelse» og oppga ingen adresse;
  aktiveringssiden fantes lenge, men var ikke lenket noe sted fra. Nå står
  **maskuro.com/lizenz-freischalten** i dialogen, i håndboken og i FAQ – og
  på nettstedet under lisensnøkkelen.

- **Knappen «Aktivér uten internett …» forblir synlig**, også når lisensen
  akkurat ikke gjelder. Tidligere forsvant den sammen med den – altså
  nettopp når man trenger den.

- **«Alle plasser opptatt» sier nå sannheten.** Meldingen endte med
  «Programmet fortsetter uendret å arbeide»; det stemmer ikke lenger når
  ingen plass ble tildelt. Der står det nå at gratisnivået gjelder inntil
  videre.

### Nytt

- **Ved påslåing av utklippstavlerensing står det nå med at det bør
  sjekkes.** Meldingen bruker siden samme setning som også står ved
  resultatet av en fil: Maskuro gjenkjenner ikke i alle tilfeller alle
  personopplysninger.

  Her veier den tyngre enn andre steder. Ved en fil ser man resultatet før
  man sender det videre. Ved utklippstavlen ikke – man kopierer, limer inn,
  og den rensede teksten står allerede i e-postvinduet. Meldingen sier
  derfor uttrykkelig å se gjennom den **innlimte** teksten.

  Den kommer ved påslåing, ikke ved hver kopieringshandling: Det som ville
  dukket opp femti ganger om dagen, leser ingen lenger etter tredje gang.

- **«Kopiér alle» under listen – og «Fjern alle» flytter seg unna.** Den nye
  knappen legger samtlige ferdige resultater samtidig på utklippstavlen,
  for å legge ved en e-post eller lime inn i et annet program. Tidligere
  gikk det bare via menyen og også der bare for de **valgte** linjene – den
  som mente alle, måtte først trykke Ctrl+A.

  Samtidig er knapperaden omorganisert: Til venstre står det som legger til
  noe, til høyre bak et mellomrom det som tar bort noe. «Fjern alle» sto
  tidligere rett ved siden av «Legg til …», og et feilgrep kostet hele
  listen. Samme regel gjelder siden 13. august allerede for hver ferdige
  linje.

- **Arbeidsplasser uten internett får nå sine språkmodeller husinternt.**
  Rensing gikk der alltid allerede uten forbindelse – å laste ned en
  språkmodell ikke, og en modell veier flere hundre megabyte.

  Administrasjonen setter sammen filene én gang på en maskin med
  forbindelse og legger dem på en delt ressurs, i utrullingen eller på en
  minnepinne. Stedet angis sentralt (feltet `modellquelle` i
  `vorgaben.json` eller miljøvariabelen `MASKURO_MODELLQUELLE`). Fra da av
  betjener hver nedlasting seg først der – språkmodeller, den japanske
  ordboken og Høy-nivået – og går bare ut på nettet hvis en fil mangler.

  Sjekksummene gjelder uendret. En fildeling internt i huset er ofte
  lettere å beskrive enn en utgivelse på nettet; den skal ikke bli den
  bekvemmeligere veien til en smuglet inn modell.

  Hvordan en slik beholdning oppstår og hvordan lisens og aktivering uten
  internett fungerer, står i `OFFLINE.md`.

- **«Hent tilbake original» – en ramme henter tilbake det som ble fjernet
  for mye.** I etterredigeringsvinduet finnes et nytt verktøy: Dra en ramme
  over stedet, og teksten står der igjen slik den sto i originalen.

  Dette lukker hullet som treffpanelet lot stå åpent. Der lot en erstatning
  seg bare angre hvis plassholderen var entydig – altså ikke ved
  anonymisering, der «[NAME]» står ved hver angivelse av denne typen, og
  slett ikke ved sladdede steder, der ingen plassholder blir stående igjen.
  Nettopp der samler feilgrepene seg: «Bruker», «inventarnummer»,
  «signatur» blir gjerne tatt for navn.

  Rammen trenger ikke plassholderen: **Stedet** kommer fra rektangelet,
  **innholdet** fra originalfilen – den samme som før/etter-bryteren viser.
  Anonymisert eller pseudonymisert spiller dermed ingen rolle lenger.

  Den tilbakehentede teksten står svart, ikke rød: Den er igjen klartekst
  og ingen plassholder. Fra trefflisten forsvinner en oppføring først når
  plassholderen dens **ikke lenger** står noe sted i dokumentet – ble samme
  verdi erstattet flere steder, blir den stående for de øvrige.

  På en side som ble omgjort til et bilde, avviser verktøyet og forklarer
  hvorfor: Den tilbakehentede teksten ville havne under sidebildet og ville
  ikke være synlig.

### Rettet

- **Ved sammenslåing av «Detaljer» og «Nøkkeltall» ble bilderester stående
  på skjermen.** Sammenslått skjøv en del av innholdet seg under den nedre
  vinduskanten og ble liggende der over bakgrunnen, inntil noe annet ble
  tegnet over.

  Begge områdene har en minstehøyde, slik at de er brukbart store når de er
  åpne. Bevegelsen ved sammenslåing satte imidlertid bare ned makshøyden –
  og under sin minstehøyde krymper et område ikke. Innholdet forble altså
  200 punkt høyt, mens vinduet allerede trakk seg sammen til 24; differansen
  sto under kanten. Nå viker minstehøyden for varigheten av bevegelsen og
  kommer tilbake etterpå.

- **Vinduet ble mindre og mindre ved gjentatt utfolding og sammenslåing.**
  Ved utfolding vokser det høyst til 92 % av skjermhøyden; er plassen knapp,
  vokser det altså mindre enn nødvendig. Ved sammenslåing trakk det likevel
  fra hele beløpet igjen. Nå gir det tilbake nøyaktig det utfoldingen
  kostet.

- **En rest av en sladdet angivelse kunne bli stående synlig.** I et CV ble
  tegnene «*30.1» av «*30.12.1991» stående leselige i resultatet – altså
  dag og begynnelsen av måneden i fødselsdatoen. Programmet hadde til og
  med lagt merke til resten og hadde derfor gjort siden om til et bilde;
  nettopp det gjorde det verre, for dermed var resten riktignok ikke lenger
  søkbar, men fortsatt leselig – og ikke lenger til å rette opp.

  Årsaken lå mellom to kontroller. Den strengeste av de to sjekker om det i
  flaten til en fjernet angivelse fortsatt står noe som ikke hører hjemme
  der; den melder sitt funn som en tegnmengde, fordi leserekkefølgen
  forskyver seg ved erstatning. Reservefunksjonen som maler over slike
  steder før omgjøringen, søkte denne tegnmengden som tekst på siden – og
  fant den aldri. Det ble derfor ikke malt over noe. Stedet var kjent hele
  tiden og videreformidles nå i stedet for å bli søkt på nytt.

  Berørt var hver side der resten bare ble funnet av denne kontrollen –
  uavhengig av filtype og språk.

- **På en tverrmatet skanning fant tekstgjenkjenningen ingenting.** Den som
  legger et ark sidelengs i materen, får en fil der skriften står dreid 90
  grader. Tidligere leste Maskuro **ikke én eneste** angivelse i den – og
  filen så deretter uanselig ut: ingenting ble funnet, altså ble ingenting
  meldt, og adressen sto fortsatt leselig i bildet. Nå retter
  tekstgjenkjenningen opp siden selv; på kontrollbildet faller igjen alle
  angivelsene.

  To grenser nevnt åpent: Et ark som står **opp ned** (180 grader), leser
  den fortsatt ikke, og ved en svært dårlig skanning hjelper ikke
  opprettingen – der er for lite leselig til i det hele tatt å bestemme
  retningen. Hvert bilde bruker for dette omtrent en femtedel lenger tid.

### Endret

- **«Installer automatisk» heter nå det den gjør.** Avkrysningen i
  innstillingene lovet mer enn den innfridde: Den laster ned den nye
  versjonen selv og starter installasjonen – som imidlertid foregår
  **synlig** og krever bekreftelse, under Windows inkludert spørsmål fra
  brukerkontokontrollen. Den som leste «automatisk», regnet med en maskin
  som oppdaterer seg selv over natten, og sto om morgenen foran
  installasjonsveiviseren. Avkrysningen heter nå «Last ned oppdateringer
  automatisk og start installasjonen», med en setning under som forklarer
  hva det betyr. Ved atferden endres ingenting – at Maskuro ikke bytter seg
  ut ubemerket, er tilsiktet og forblir slik.

## 0.10.27-alpha.20260817 – 17. august 2026

### Nytt

- **Nytt: `--ersetzen` for tilkobling til et advokatkontorsystem.**
  Resultatet trer i stedet for kildefilen, i stedet for å oppstå ved
  siden av. Dermed fungerer ut- og innsjekking av et advokatkontorsystem
  («Åpne og rediger» i e-mappen) uten noe grensesnitt: Programvaren gir
  fra seg filen og får den renset tilbake på samme sted.

  **Denne bryteren omgår det første grunnprinsippet**, og derfor finnes
  den bare på kommandolinjen – ikke i vinduet – og bare hvis
  administrasjonen din frigir den (oppføring `ersetzen` i vorgavefilen).
  Uten frigivelse avbrytes kallet og sier hvorfor; å stilltiende opprette
  en andre fil ville vært den verre feilen, for da ville den uendrede
  blitt sjekket inn igjen.

  Skrevet blir først en nabofil; først når den er ferdig, trer den i
  stedet for kilden. Et avbrudd eller en feil lar dermed kilden forbli
  **byte for byte uendret** og etterlater ingen bruddstykker. I
  kontrollprotokollen står erstatningen som eget felt – en kontrollør må
  vite at den urensede versjonen ikke lenger ligger her.

- **Håndboken forklarer nå Windows-advarselen ved første oppstart.** Nytt
  første avsnitt «Windows advarer ved første oppstart – hva du skal
  gjøre», med to bilder og tre trinn: «Mer informasjon» er en liten
  lenke, ingen knapp – nettopp der blir de fleste hengende –, deretter
  «Kjør likevel».

  At det står «Ukjent utgiver» der, er hele budskapet i advarselen:
  Pakkene leveres for øyeblikket uten sertifikat. Vi anser det som
  riktigere å forklare dette enn å fortie det.

- **Tilbakeveien merker nå når tekst og tilordning ikke hører sammen.**
  Den som limer svaret inn i en annen sak, fikk tidligere fremmede navn i
  riktig tekst – ingen feil, ingen melding, bare feil. Maskuro husker nå
  hvilke plassholdere den siste kjøringen overhodet har generert, og
  melder hver som ikke hører til. Stammer ingen av dem fra den siste
  kjøringen, settes ingenting inn, og vinduet sier hvorfor – i stedet for
  å anta en utløpt frist som tidligere.

  **En grense gjenstår, og den står også i håndboken:** Plassholdere
  nummereres per kjøring, det første navnet heter altså i hvert dokument
  `[NAME_1]`. Bærer den fremmede teksten bare slike plassholdere, er
  forvekslingen ikke til å gjenkjenne.

- **PDF kan nå gis ut i svart-hvitt.** En avkrysning ved driftsmodusen
  gjør hver side om til et svart-hvitt-bilde – med usynlig tekstlag
  under, altså fortsatt lesbar og søkbar. For forsendelse via beA og
  lignende veier med harde størrelsesgrenser: over målekorpuset vårt i
  gjennomsnitt **68 % mindre** (kommandolinje: `--monochrom`).

  **Hvor mye det gir, avhenger av dokumentet** – og det står også ved
  avkrysningen: Skannet og bildeholdig krymper kraftig, et slankt
  tekstdokument uten innebygde skrifter kan til og med bli større. Prøv
  det på en fil før du slår det på for en bunke.

  Prisen: Hver side regnes på nytt – ved tusen sider tar det minutter. Og
  bilder mister alt mellom svart og hvitt; for tekst er det likegyldig,
  for et fotografi ikke.

- **Trefflisten i etterredigeringsvinduet teller nå med.** Over listen
  står «5 treff», og så snart du filtrerer, «1 av 5 treff». Det er
  forskjellen mellom «jeg har filtrert» og «det er fem, og jeg har sett
  dem alle» – håndgrepet man bruker for å sjekke om et navn virkelig ble
  erstattet overalt.

- **Kontrollprotokollen kan nå søkes gjennom og filtreres.** Visningen
  under «Fil → Kontrollprotokoll» hadde tidligere en tabell og ellers
  ingenting – ved en måned med tre tusen kjøringer så man at mye hadde
  skjedd, men ikke hva.

  Nytt er et **søkefelt**, **tre filtre** (fremgangsmåte, resultat, type)
  og **bladring**, dertil tre kolonner det ikke fantes tidligere:
  **Fremgangsmåte** (sladdet eller erstattet), **konfidens** og
  **varighet**. Over listen står hvor mye som akkurat vises, og hvor mye
  filteret skjuler.

  «Lagre som CSV …» gir nå **ut det som står der** – den som har filtrert,
  får det filtrerte, og meldingen nevner antallet.

  En strek ved konfidens eller varighet betyr at det ikke ble målt noe
  for denne linjen – for eksempel fordi den er eldre enn denne funksjonen.
  Disse verdiene beregnes **ikke** i ettertid. Et filter over bruker
  finnes fortsatt ikke; en enkelt linje finner søket likevel.

### Fjernet

- **Åpenhetshenvisningen i vinduet «Om dette programmet» er borte
  igjen.** Den sto der siden 0.10.22-beta.1 og sa at applikasjonen ble
  utviklet med støtte fra kunstig intelligens. Den er ikke påkrevd noe
  sted, og nettopp i en applikasjon for personvern leste enkelte den som
  et utsagn om arbeidsmåten – altså som om dokumentene gikk til en
  tjeneste på nettet. Det renses fortsatt utelukkende på egen maskin;
  dette står der det hører hjemme, i fanen «Personvern».

### Rettet

- **Programmet byttet ut sitt eget symbol med et dårligere.** Den som
  registrerte kontekstmenyen fra programmet, hadde deretter et annet
  skjold i oppgavelinjen enn etter installasjonen – lignende, men med
  venstrejusterte i stedet for midtstilte striper og synlig grovere. Bak
  dette lå en nødløsning: Finner programmet ikke ikonmalen, tegner det
  selv et. Dette var tenkt for tilfellet at **ingen** ikoner finnes; i
  praksis tegnet det også når de medfølgende for lengst lå der – og
  overskrev dem. I en versjon installert fra oppsettet finnes det ingen
  mal, så det rammet der alle. Eksisterende ikoner forblir nå urørt.

  **Allerede berørte installasjoner henter ikke det riktige symbolet
  tilbake av seg selv** – installer for dette en gang på nytt.

- **«Objektkennung: OB-4711-22» gjaldt som brukernavn.** Gjenkjenneren for
  brukernavn kontrollerte merkingene sine uten ordgrense foran – altså
  grep den **hvert** ord som ender på en av dem: Objektkennung,
  Fahrzeugkennung, Gerätekennung. Verdien bak ble fjernet, selv om den
  ikke hadde noe med et brukernavn å gjøre.

  Sammensetninger som virkelig er ment – «Benutzerkennung»,
  «Anmeldekennung» –, står enkeltvis i listen og gjenkjennes fortsatt.

- **På engelsk, gresk, japansk og koreansk sto seksten plassholdere på
  tysk i resultatet.** Den som hadde stilt grensesnittet på ett av disse
  fire språkene, fikk for de nyere datatypene de tyske merkingene skrevet
  inn i dokumentet – av et passord ble det `[ZUGANGSDATEN_1]» i stedet
  for `[CREDENTIALS_1]`, av en diagnosekode `[DIAGNOSESCHLUESSEL_1]» i
  stedet for `[DIAGNOSIS_CODE_1]`. Berørt var helse, diagnose,
  medikasjon, diagnose- og legemiddelkoder, religion, fagforening,
  politisk mening, strafferett, tilgangsdata, brukernavn, kortdata,
  koordinater, yrke, beløp og kjennetegn.

  De øvrige 44 språkene hadde aldri feilen: De henter merkingene sine fra
  språkfilene der disse typene sto fra begynnelsen av. Nettopp disse fire
  språkene fører av en annen grunn egne tabeller – skriften deres
  overlever ikke PDF-tegnsettet, derfor står latinske merkinger der –, og
  i disse tabellene manglet de nye typene rett og slett.

  Det ble oppdaget ved oversettelse av katalogsiden: Nettstedet lovet
  engelske lesere merkinger programmet ikke skrev. En kontrollstein
  holder nå de fire tabellene mot listen over alle merkinger som
  overhodet kan oppstå.

- **Regelvinduet åpner seg ikke lenger for lite for innholdet sitt.** I
  fanen «Egne søkemønstre» lå forklaringslinjen til veiviseren («Det
  søkes etter: …») halvt bak feltet «Prøvetekst» – nettopp setningen man
  bruker uten kjennskap til regulære uttrykk for å kontrollere om den
  egne regelen søker det riktige. Vinduet hadde et fast minstemål fra en
  tid med færre faner og lot seg derfor dra under det som fikk plass. Nå
  retter det seg etter innholdet sitt og åpner seg bare så lite som alt
  forblir leselig.

- **Navn i tabellformler blir ikke lenger stående.** En celle har mer enn
  ett sted for tekst, og tidligere ble bare ett ryddet. Sto et navn i en
  formel – `="Frau "&"Sieglinde Ortner"` – eller var det det sist
  beregnede resultatet av en formel, ble det stående uendret i
  arbeidsboken, selv om samme person i cellen ved siden av var erstattet.
  Den som klikket på cellen, leste det i redigeringslinjen.

  Begge deler erstattes nå. Berørt blir bare det som står mellom
  anførselstegn: Cellereferanser, funksjonsnavn og arknavn forblir
  urørt, `=SUMME(K2:K6)` regner videre. Fordi samme navn overalt får
  samme plassholder, finner også `=SUMMEWENN(A:A;"Huber";B:B)» fortsatt
  linjene sine.

- **Diagrammer viser ikke lenger navn.** Et diagram lagrer en egen kopi
  av akseoverskriftene sine – det tegner fortsatt selv når kildecellene
  for lengst er tomme. Under stolpene sto derfor fortsatt fem personnavn,
  mens tabellen over var ren. Gjelder for tabeller **og** presentasjoner.

- **Navngitte områder med fast tekst ryddes.** Et navngitt område kan i
  stedet for en cellereferanse inneholde en fast tekst; sto det et navn
  der, ble det stående. **Navnet** på området blir fortsatt stående –
  formler viser til det, og en omdøping ville gitt en referansefeil. Som
  ved arknavnet meldes det, erstattes ikke.

- **En gang gjenkjent fødselsdato forsvinner i hele dokumentet.** En dato
  alene sier ingenting – først et feltord gjør den til en fødselsdato, og
  nettopp derfor blir en fakturadato stående i fred. Sto samme angivelse
  i samme dokument likevel en andre gang uten dette ordet – i
  bildetittelen, i et utfylt skjemafelt –, ble den stående der, selv om
  «født den …» noen linjer over var entydig gjenkjent. Overføres blir
  bare det som allerede er gjenkjent som fødselsdato i **dette**
  dokumentet; det gjettes fortsatt ingenting.

- **Strukturerte data i nettsider avslører fødselsdatoen sin.** I
  JSON-LD-blokken for søkemotorer står datoen under nøkkelen `birthDate`
  – nøkkelen sier hva det er, slik kolonneoverskriften ellers gjør. Den
  leses nå med; «Birthday» og «Birthdate» gjelder dermed også i skjemaer
  som feltbetegnelse.

- **Fødselsdato og personalnummer finnes nå også i tabeller.** I en celle
  står bare den nakne verdien – «14.03.1988». Hva den betyr, sier bare
  kolonneoverskriften, og den står mange linjer lenger opp. I Excel ble
  den allerede lest med; i LibreOffice-tabeller og i CSV-filer ikke, og
  der ble fødselsdatoen derfor stående.

  Begge leser nå overskriften med – **men bare hvis den selv er en
  feltbetegnelse**. Under «Geburtsdatum» faller datoen, under
  «Rechnungsdatum» eller «Lieferdatum» ikke. Dette er bevisst den
  forsiktige tolkningen: En overskrift som «Navn» over en vilkårlig
  merknad hadde også en gang lagt en plassholder over en setning der det
  slett ikke forekommer en person.

### Rettet

- **En renset CSV forblir en tabell.** Gjenkjenningen leser en CSV-linje
  som en setning og la derfor av og til funnene sine over et semikolon.
  Plassholderen svelget skilletegnet, linjen hadde deretter en kolonne
  mindre, og filen lot seg ikke lenger åpne som tabell. Funnsteder ender
  nå ved cellegrensen, og anførselstegnene til maskeringen forblir
  stående. De berørte cellene leses deretter en gang til for seg – ellers
  ville nabocellen blitt stående urenset, som det for lange treffet
  hadde dekket.

- **Kommentarer i presentasjoner.** Merknaden ved siden av et lysbilde –
  ofte nettopp stedet der «Vennligst ring fru … før møtet» står – forble
  urørt, sammen med navnet til den som skrev den. I Excel var begge deler
  for lengst ryddet; PowerPoint lagrer kommentartekst og forfatter
  annerledes, og det ble oversett. Gjelder begge byggeformer: den eldre
  og den PowerPoint har skrevet siden 2019 – der også
  tjeneste-e-postadressen som henger ved forfatteren. Initialene
  PowerPoint viser ved snakkeboblen, fjernes med.

- **LibreOffice-filer: formel, brukerfelt, notatforfatter.** Det som
  allerede var ryddet i Excel, ble stående i ODS-tabellen – der står
  formelen ikke som eget element, men som celleegenskap, og navnet i den
  overlevde. Ved neste åpning regnet LibreOffice det frem igjen.

  Dertil tre ytterligere steder: Verdien til et **brukerfelt** står i
  OpenDocument én gang øverst i deklarasjonen og hentes i teksten bare –
  tidligere ble bare selve hentingen erstattet, slik at den gamle verdien
  kom tilbake ved åpning. **Forfatteren av et notat** og en sporet
  endring ble stående. Og i en **tabell** ble endringssporingen overhodet
  ikke ryddet ut – i motsetning til i tekstdokumentet –, slik at slettet
  celleinnhold sammen med redigeringsnavn ble bevart. Cellereferanser og
  summeformler forblir urørt av dette.

- **Lagrede nettsider avslører attributtene sine.** En side viser langt
  fra alt den inneholder. Et utfylt skjemafelt bærer inntastingen i
  `value`, et JavaScript-grensesnitt legger datasettet sitt i `data-…`,
  og blokken for søkemotorer (JSON-LD) gjentar det fullstendig og
  velformet: navn, fødselsdato, adresse, telefon. Den synlige teksten var
  renset, alt dette sto fortsatt der.

  Nå ryddes også disse stedene, dertil `aria-…» (det skjermleseren leser
  opp), `placeholder`, `summary» og det foreslåtte filnavnet til en
  lenke. JSON-LD-blokken leses ved dette som data og forblir gyldig –
  nøklene og vokabularet dets blir stående, bare verdiene forsvinner.
  Vanlig JavaScript røres fortsatt ikke.

- **Bilder mister biopplysningene sine også uten EXIF.** Et foto bærer
  fotografnavn, opptakstidspunkt og GPS-koordinater for opptaksstedet
  skrevet ved siden av – ved en boligannonse avslører dette adressen,
  selv om det ikke står noen i teksten. Dette ble fjernet så lenge
  bildet hadde EXIF. Var angivelsene derimot **bare** lagret som XMP
  (slik Lightroom og Photoshop lagrer) eller som tekstblokk i en PNG
  (`Author`, `Comment`), forble bildet helt urørt. Begge deler gjenkjennes
  og fjernes nå – også ved bilder som ligger i et dokument og bevares
  der. Retningen overlever fortsatt, og et bilde uten biopplysninger
  lagres ikke unødvendig på nytt.

- **Lenkemål i tabeller, presentasjoner og Word-dokumenter.** Hvor en
  lenke fører, står ikke i teksten, men i et eget lagringssted i filen.
  En e-postadresse bak «Send e-post» overlevde derfor rensingen uskadd,
  mens samme adresse i teksten var erstattet. `mailto:` og `tel:` ryddes
  nå der like mye som i lagrede nettsider.

### Nytt

- **Legebrev kommer ikke lenger tilbake skadet.** Tidligere tok
  navnegjenkjenningen legemidler for personnavn: Av «Metoprololsuccinat»
  ble det `[NAME]`, av «Ramipril» ble det `[ORT]`. Medisineringsplanen var
  deretter ubrukelig – mens diagnosene ble stående urørt, altså akkurat
  motsatt. Målt gjaldt dette **63 % av virkestoffene** og **53 % av de
  kliniske fagbegrepene**, og ikke bare på tysk: over sju språk 74 %, på
  italiensk alle kontrollerte.

  Maskuro kjenner nå det medisinske vokabularet og lar det være i fred.
  Igjen blir 6 % i stedet for 43 % (tysk) og 1 % i stedet for 74 % (over
  språkene). Der en tiltaleform står foran – «Kjære fru …» – forblir
  navnet et navn, selv om det tilfeldigvis heter som et legemiddel.

- **Sykdommer og medikamenter kan fjernes – hvis du vil.** Ny avkrysning i
  innstillingene: «Fjern også sykdommer og medikamenter» (kommandolinje:
  `--mit-diagnosen`). For personalmapper, oppsigelser og sakkyndigerklæringer,
  der diagnosen ikke angår noen.

  **Forhåndsinnstilt av**, og det med hensikt: Et legebrev *består* av
  diagnoser og virkestoffer. Den som anonymiserer ett – for forskning,
  for en opplæring, for et KI-verktøy –, vil som regel beholde nettopp
  dette innholdet og bare bli kvitt hvem det gjelder. Diagnosen er der
  nyttelasten, ikke identifikasjonen.

  Gjenkjenningen finner de vanlige betegnelsene og erstatter ikke
  gjennomgangen: En sykdomsliste er aldri fullstendig, fordi legen
  skriver «C2-Abusus» der klassifikasjonen fører «Forstyrrelser grunnet
  alkohol».

- **Diagnose- og legemiddelkoder finnes.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) og det sentrale legemiddelnummeret er helsedata som enhver
  utskrevet diagnose – i utskrivningsbrev og faktureringsdokumenter til
  og med den hyppigere formen. De er forhåndsinnstilt på, som de øvrige
  særlige kategoriene etter art. 9 GDPR.

  En diagnosekode gjenkjennes bare med belegg: med «ICD» foran eller i
  parentes bak diagnoselinjen. Uten denne betingelsen ville programmet
  holdt funksjonstasten **F10** for en rusdiagnose – i klassifikasjonen
  er F10 nettopp det.

- **Den ferdige filen kan nå kopieres.** På hver ferdige linje står ved
  siden av «Se», «Etterrediger» og «Vis i mappe» en fjerde knapp:
  **Kopiér**. Den legger den rensede filen på utklippstavlen – derfra går
  den med Ctrl+V (Mac: ⌘V) inn i en e-post, et chattevindu eller et
  KI-verktøy, uten omveien via mappen.

  Kopiert blir **filen**, ikke teksten dens: Sideoppsett, bilder og
  sladdestripene bevares dermed. Via kontekstmenyen til listen går også
  flere valgte resultater samtidig til utklippstavlen, og i menyen «Fil»
  står samme vei som **«Kopiér resultat»** for alle som heller bruker
  tastaturet.

- **Landvalget kan nå følge dokumentet.** Identitets-, trygde- og
  skattenumre varierer fra land til land, og hvilke land som
  kontrolleres, var tidligere fast for hele økten – utledet fra
  grensesnittspråket. Den som arbeider på tysk og renser et fransk
  skriv, søkte altså i det etter tyske skatte-ID-er og ikke etter det
  franske trygdenummeret.

  I regelvinduet står det derfor nå **«Automatisk etter dokumentets
  språk»**. Det faste valget forblir ved siden av, og det med hensikt:
  Språkgjenkjenningen er ikke ufeilbarlig – gjenkjenner den feil, griper
  feil landvalg inn. Den som bare behandler mapper fra ett land, kjører
  sikrere med den faste listen.

  Uberørt av dette forblir de **tyske** mønstrene (skatte-ID, kjøretøy,
  internnummer): De henger på språket, ikke på landvalget, og griper
  fortsatt inn også når en kort tysk tekst klassifiseres som engelsk.

- **Passord, nøkler og brukernavn finnes nå.** Den som limer en
  feilmelding, en protokoll eller et utdrag fra en konfigurasjonsfil inn
  i et KI-vindu, har nesten alltid en tilgangsnøkkel i det – og den sto
  tidligere uendret der.

  Begge deler gjenkjennes: de utbredte nøkkelformene som taler for seg
  selv (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token,
  hodet til en privat nøkkel), og den merkede formen – «Passord:»,
  «API-Key =», «Token:», «Brukernavn:». Erstattet blir bare verdien,
  aldri merkingen: «Passord: [ZUGANGSDATEN_1]» forblir leselig, og den
  som kontrollerer resultatet, ser at det sto et passord der.

  Brukernavn og passord er to atskilte typer. Den som bare vil fjerne
  passord, slår av den ene og beholder den andre.

- **Strek- og QR-koder i bilder gjøres ukjennelige.** På et innskannet
  vedtak klistrer det seg nesten alltid en kode, og i den står
  saksnummeret – samme nummer som fjernes i teksten ved siden av.
  Tidligere ble den maskinlesbare versjonen stående: Stripen over
  nummeret nytter ikke, hvis en enhet to centimeter lenger unna leser det
  ut på ett sekund.

  Gjenkjent blir QR-kode, Data Matrix, Aztec, Code 128, EAN og de øvrige
  vanlige formene. Ukjennelig betyr pikselering, og grovere enn ved
  ansikter: Feilrettingen i en kode henter overraskende mye tilbake fra
  få bevarte felt, et halvhjertet slør ville ikke vært en fjerning.

  Valget står ved siden av «Gjør ansikter ukjennelige» og er likeledes
  **forhåndsavkrysset**. Også med valget slått av sier rapporten hvor
  mange bilder som bærer en kode – et ansikt ser man ved bla-gjennom, en
  kode holder man for pynt.

- **Kortkontrollnummer, PIN og utløpsdato finnes.** Kredittkortnummeret
  fant programmet allerede; først med de tre angivelsene ved siden av er
  det brukbart, og på hvert avregningsbilag står de sammen. Alle tre bare
  bak sin merking – «123» alene er et husnummer, et sidetall eller et
  antall.

- **Koordinater i teksten finnes.** Fra bilder har Maskuro allerede
  fjernet opptaksstedet; sto samme angivelse som tekst i
  sakkyndigerklæringen eller i innsatsrapporten, ble den stående.
  Gjenkjent blir desimalgrad og grad-minutt-sekund-skrivemåten. Ved
  desimalgrad må et ord som «Standort», «Fundort» eller «Koordinaten»
  stå i nærheten – ellers ville hver måleserie med to desimaler vært en
  stedsangivelse.

- **Pengebeløp kan nå fjernes med.** Ny avkrysning «Fjern også
  pengebeløp», forhåndsinnstilt **av** som datoangivelsene over: I en
  kontrakt er beløpet innholdet, og den som sladder alt, beskytter
  ingen. I en lønnsslipp, et forliksforslag eller en kontoutskrift er det
  derimot nettopp den angivelsen som sier mer om personen enn navnet ved
  siden av – det vet bare den som har dokumentet foran seg.

  Et beløp gjenkjennes **bare med valutaangivelse**: «4.250,00» alene er
  et antall, først «4.250,00 EUR» er penger. Valutasymbol, forkortelse og
  utskrevet navn teller, foran som bak, samt skrivemåten «990,– CHF».

- **De særlige kategoriene etter art. 9 GDPR gjenkjennes.**
  Religionstilhørighet, fagforeningsmedlemskap, politisk overbevisning,
  helseopplysninger – og ved siden av de strafferettslige opplysningene
  etter art. 10. Dette er dataene forordningen i utgangspunktet
  **forbyr** behandling av; de er derfor som den eneste nye gruppen
  forhåndsinnstilt **på**. Den som vil beholde dem, avgjør det selv.

  Gjenkjent blir formen de i praksis står i: skjemafeltet på
  personalskjemaet – «Religionsbekenntnis: røm.-kat.», «Fagforening:
  ÖGB», «Uføregrad: 50», «Straffedommer: ingen» –, både med kolon ved
  siden av og med merkingen over, slik et utfylt skjema leverer dem.

  **Den løpende teksten hører til KI-nivået.** «Han har engasjert seg i
  fagforeningen i årevis» er samme angivelse, og intet søkemønster finner
  den pålitelig. KI-nivået søker fra denne versjonen uttrykkelig også
  etter disse kategoriene; den som trenger løpende tekst, slår det på.

- **Personkjennetegn og yrke – angivelsene som viser hvem det gjelder,
  også uten navn.** Kjønn, sivilstand, kroppshøyde, øye- og hårfarge
  fjernes fra denne versjonen; yrke, funksjon og avdeling ved ønske, via
  en egen avkrysning («Fjern også yrke og avdeling») eller
  `--mit-berufen`.

  **Hvorfor det ene er på og det andre av:** «Lederen for
  innkjøpsavdelingen» navngir i en bedrift nøyaktig én person, selv om
  navnet ved siden av er sladdet – i en sakkyndigerklæring eller en
  oppsigelse hører dette til å fjernes. En medarbeideroversikt *består*
  derimot av yrkesbetegnelser; den som forhåndsinnstilt fjernet dem, ville
  levert et tomt ark tilbake. Hvilket tilfelle som foreligger, vet bare
  den som har dokumentet foran seg. Kjennetegnene over står nesten bare i
  skjemafelt, er sjeldne og bærer aldri innholdet – de koster altså
  ingenting.

- **Kontrollere en fremmed fil.** «Fil → Kontroller fil …» leser et
  allerede sladdet dokument på nytt og melder hva som fortsatt står der –
  og **på hvilket sted**: side og linje, type og lengde. For tilfellet at
  noen kontrollerer en annens arbeid: en mappe fra advokatkontoret, en
  opplysning fra myndigheten, egen utgående post før forsendelse.

  **Selve verdien står ikke i rapporten.** Den som slår opp stedet, ser
  den uansett – og rapporten kan derfor lagres og videreformidles, uten
  selv å være en samling personopplysninger.

  **Og rapporten sier i hvert tilfelle hva den ikke kunne se.** Bilder
  leses ikke; ved en skanning uten tekstlag betyr «ingen funnsted» *ikke
  kontrollert*, ikke *ren*. På kommandolinjen skiller returverdien dette:
  `--nachpruefen` leverer 0 for kontrollert og ren, 4 for funnsteder og 5
  for ikke kontrollerbar. Dermed lar utgående post seg holde tilbake
  automatisk, i stedet for å bare vinkes gjennom.

- **Kontrollrapport: ett ark per rensing.** «Fil → Lagre kontrollrapport
  …» – eller `--pruefbericht <mappe>» på kommandolinjen – skriver en
  ensiders PDF (valgfritt CSV eller tekst) med angivelsene om kjøringen,
  de funnede typene med antall, to nøkkeltall og en kontrollmerknad. For
  saksmappen og for tilsynet: Kontrollprotokollen er det holdbare
  beviset, men ingen legger frem en JSON-Lines-fil.

  **Nytt her er to tall** som det ikke fantes noe sted å se før: den
  *gjennomsnittlige konfidensen* – hvor sikker gjenkjenningen var ved det
  den fant – og *maskeringsraten*, andelen erstattede tegn av teksten.
  Begge står med grensen sin ved siden av: Konfidensen sier **ingenting**
  om oversett; ved siden av den står alltid hvor mange treff den i det
  hele tatt gjelder for; raten teller ikke bilder med og blir for høy ved
  et illustrert dokument.

  **Funnverdier står ikke på arket** – samme grense som ved protokollen
  og søkelinjen. Nederst står to linjer som ikke sier det samme:
  Sjekksummen viser at arket er uendret; protokollinjen – bare ved
  kjørende protokoll – henviser til den **signerte** linjen som beviser
  kjøringen. Først den beviser opprinnelsen.

- **«Hvor sikkert var det?» – nøkkeltallene ved resultatet.** En knapp
  «Nøkkeltall» under resultatet klapper opp det som ikke fantes noe sted
  å se før: funnsteder, ord og tegn, fordelingen per type som stolpelinje,
  dertil den gjennomsnittlige konfidensen og maskeringsraten. Samme tall
  som i kontrollrapporten, bare umiddelbart og uten utskrift.

  **Med forbeholdet sitt i samme flate:** Ved siden av konfidensen står
  hvor mange treff den gjelder for, og under setningen om at den
  **ingenting** sier om oversett. En prosentandel uten denne setningen
  leses som en treffkvote – og den som forstår den slik, er dårligere
  stilt enn uten tallet.

  Beregnes gjør det først ved utfolding: Nevneren til maskeringsraten
  koster per fil en lesehandling, og den skal ikke betales av den som
  slett ikke ser på tallene.

- **Bygg egne søkemønstre uten å skrive noen.** Fanen «Egne søkemønstre»
  fører nå gjennom saken i tre trinn: *Hva søker du etter? → Hvordan ser
  en slik angivelse ut hos deg? → Navngi og lagre.* Du skriver inn et
  eksempel – for eksempel `KD-004711» –, programmet utleder regelen fra
  det og skriver med ord hva den søker etter. En forhåndsvisning med
  trefftelling kontrollerer ved hvert tastetrykk.

  **Et regulært uttrykk forekommer ikke ved dette.** Kunnskapen var aldri
  problemet: Egne søkemønstre har eksistert lenge, bare krevde de et
  uttrykk som `\bKD-\d{6}\b`, og det skriver ingen på et advokatkontor
  eller en personalavdeling. Den som *vil* skrive ett, klapper opp
  ekspertmodus.

  **Malkatalogen er nysortert:** tretten kort med navn, forklaring og
  eksempelverdi, filtrert via kategorimerker – finans, myndigheter,
  kontakt, personal, medisin.

  Og griper det utledede mønsteret for vidt, sier programmet det selv:
  Et eksempel av bare sifre treffer hvert årstall og hvert beløp, og den
  som ikke kan lese uttrykket, kunne ellers ikke merket det.

- **Sju merker i stedet for femtiséks avkrysninger.** En ny fane «Hva som
  søkes» samler alle gjenkjennbare typer i sju grupper – person, kontakt
  og sted, identifikasjoner, finans, teknikk, særlige kategorier, firmaer
  og egne. Et merke slår gruppen sin på/av, «Alle på» og «Alle av» hele
  listen; under blir hver type fortsatt individuelt avkryssbar.

  **Forhåndsinnstilt er alt på, og det forblir slik.** Det som slås av
  her, søkes overhodet ikke etter – det groveste inngrepet regelvinduet
  tillater, og det virker på hvert dokument. Derfor står det under listen
  til enhver tid hvor mange typer er av, og lagret blir bare det avslåtte:
  En ny type er dermed med også i en regelfil fra i forgårs, i stedet for
  stilltiende å falle bort.

- **Overføre en ramme til alle sider.** I etterredigeringsvinduet tar
  knappen **Overfør til alle sider** den sist dratte rammen og sladder
  samme sted på hver ytterligere side – for brevhode, bunntekst og
  saksnummerfelt. Ved en skannet mappe med åtti sider gjør dette tjue
  minutter til to.

  **«Samme sted» betyr samme *relative* sted på arket.** I en bunke fra
  materen ligger regelmessig én side liggende, en annen er A3, en tredje
  dreid; et absolutt overført rektangel ville havnet der ved siden av
  brevhodet – og man ville sett en stripe og trodd saken var ordnet.

  **Sladdet blir det, ikke erstattet**, selv om utgangsrammen var en
  plassholder: Under samme rektangel står det på side førti noe annet enn
  på side én, og en plassholder med samme nummer ville hevdet en likhet
  som ikke finnes.

- **En merknad på sladdestripen.** I innsynsretten i saksmapper står det
  ved siden av hver sladding hvorfor det ble sladdet. Det nye feltet
  **Merknad på stripen** i innstillingene – eller `--balkenvermerk» –
  skriver en kort tekst på hver stripe: «§ 203 straffeloven», «GDPR»,
  «fortrolig». For et dokument en myndighet utleverer, er dette
  forskjellen: Mottakeren ser grunnen, uten å ha en protokoll han uansett
  aldri får.

  **Forhåndsinnstilt tom**, for merknaden er synlig i det utleverte
  dokumentet og er selv en angivelse – den sier mottakeren under hvilken
  tittel noe holdes tilbake. Den virker bare ved **sladding**; der en
  plassholder står, står ingen stripe. På en stripe for liten for lesbar
  tekst bortfaller den – en ulesbar merknad ser ut som en feil.

- **Aktivering uten internettforbindelse – nå fullstendig.** I
  lisensvinduet fantes «Aktivér uten internett» allerede lenge: øverst en
  forespørselskode til å ta med, nederst feltet for aktiveringen som
  kommer tilbake. Bare kunne den frem til nå **ingen utstede** – verktøyet
  for dette manglet, og koden gikk i tomrommet. Dette er rettet.

  For myndigheter og advokatkontorer med isolerte maskiner er dette
  ikke et spesialtilfelle, men normaltilfellet – og det er nettopp den
  målgruppen der løftet «dokumentene dine forlater aldri maskinen» veier
  tyngst. Koden avslører ingenting om dokumenter: Den inneholder
  lisensidentifikasjonen og en streuverdi for maskinen, ellers ingenting.

- **Hente fra skanner.** «Fil → Hent fra skanner …» leser en bunke
  direkte inn og legger sidene i listen – for et postmottak forskjellen
  mellom to arbeidstrinn og ett. En arkmater tømmes til siste side;
  enhet, oppløsning og farge velges av skannerens systemdialog, som du
  uansett kjenner.

  **Renses gjør det ikke av seg selv.** Du ser først hva som er kommet
  inn, og trykker deretter «Rens» som ved enhver annen fil – en skanning
  som kjører gjennom med det samme, ville tatt fra deg blikket på en
  skjevmatet bunke.

  **Dette finnes bare under Windows**, og menypunktet sier det også på
  Mac: Der skriver skannerens programvare til en mappe, og «Overvåk
  mappe …» renser alt som havner der.

### Annet

- **Listen over alle funnede angivelser følger nå med** og genereres fra
  kildekoden (`hilfe/GEFUNDENE-ANGABEN.md`): 177 typer i 35 land, 23 av
  dem med kontrollsifferberegning. Den sier også hvordan det ble telt –
  vi teller `[NAME]» én gang, der andre fører for-, mellom- og etternavn
  som tre oppføringer.

- **Sladding finnes nå også i Word, PowerPoint, OpenDocument og HTML.**
  Valget mellom plassholder og sladding gjaldt tidligere bare for
  PDF-filer. Nå kan de andre det også: Funnet fjernes, og på stedet dets
  står en svart stripe – i selve dokumentet, ikke som et bilde over. Den
  som videreformidler filen, gir fra seg en sladdet mappe og ingen der
  det sladdede fortsatt ligger som tekst under.

  **Avgjøres blir det separat**, i to valgfelt: «Ved PDF» og «Ved Word,
  PowerPoint, OpenDocument og HTML». Man vil ha det forskjellig – den
  sladdede PDF-en går til myndigheten, samme sak som Word-fil vandrer
  videre gjennom huset og skal forbli lesbar. På kommandolinjen
  tilsvarende `--pdf-modus» og `--office-modus»; et lagret «Sladd» fra
  tidligere versjoner gjelder fortsatt PDF.

  I tabeller, ren tekst, CSV og e-post går ikke stripen – der mangler
  flaten den kunne legge seg på. Det settes fortsatt inn en plassholder,
  og resultatet **sier det nå**, i stedet for å gjøre det stilltiende.

- **Nytt: «Fjern» – funnstedet blir rett og slett stående tomt.** Den
  tredje driftsmodusen ved siden av plassholder og sladding, og den
  eneste som kan **hvert** format: Å utelate noe trenger ingen flate. I
  PDF tegnes det da ingenting, i Word og HTML forblir stedet tomt, i en
  tabell likeledes.

  Den er den stilleste av de tre: Den som leser resultatet, ser ikke at
  det noensinne sto noe der – heller ikke lengden på verdien avsløres
  lenger. For et dokument noen skal kontrollere, forblir plassholderen
  som regel det bedre valget.

  I bilder gjelder ingen av de tre valgene: Bildepunkter lar seg ikke
  erstatte med en plassholder og ikke utelate. Det tekstgjenkjenningen
  finner der, males alltid over som før.

- **Etterredigeringsvinduet hevder ikke lenger erstatninger som ikke
  finnes.** Til høyre sto det en plassholder for hver verdi – også ved en
  sladdet fil der ingen eneste forekommer. Et klikk på en slik linje
  markerte ingenting, og «Angre» gikk i tomrommet. Nå står det «sladdet»
  henholdsvis «fjernet» der, og linjene lar seg overhodet ikke angre: Teksten
  er borte, det er ingenting å hente tilbake. Dette gjaldt for sladdede
  PDF-filer, for Word og OpenDocument og for alt som ble funnet i bilder.

- **Tekstvisningen viser nå stripene som striper.** En sladdet Word-fil
  så under etterredigering **tom** ut: På de sladdede stedene sto hull,
  som om programmet hadde slukt teksten. Grunnen var visningen, ikke
  resultatet – i selve dokumentet lå stripen riktig hele tiden. Nå står
  den også i visningen der, svart som i resultatet, i Word, PowerPoint,
  OpenDocument og HTML.

- **Outlook-meldinger (`.msg`) renses nå.** `.eml» fantes for lengst – i
  tyske bedrifter er imidlertid Outlook e-posten, og der heter en lagret
  melding `.msg». Dermed er det tetteste personopplysningsformatet også
  dekket i sin mest utbredte lagringsform: emne, avsender,
  mottakerlinjer, meldingstekst, HTML-versjon, mottakerliste og
  vedlegg – sistnevnte via de eksisterende veiene og med samme
  plassholdere som e-postteksten.

  **En `.msg» bærer samme tekst flere ganger**, og det er fellen: som
  ren tekst, som HTML **og** som RTF. Den som bare renser ren tekst, har
  ikke gjort noe – Outlook viser fortrinnsvis RTF-en. RTF-versjonen
  fjernes derfor helt, likeledes internett-hodefeltene med
  Received-kjeden og de binære søkenøklene, som navn og adresser
  overlever enhver tekstrensing. Resultatet åpner seg fortsatt i Outlook
  og viser teksten uten skriftmerking; rapporten sier det uttrykkelig.

- **Beskriv regler med egne ord, i stedet for å skrive regex.**
  Regelvinduet kan mye og krevde til dette et regulært uttrykksmønster –
  stedet der det stopper for de fleste. Nå holder det med en setning:
  «Våre saksnumre av formen 12 C 345/26 skal bli stående.» KI-nivået
  foreslår derfra begreper og søkemønstre.

  **Overtatt blir bare det du krysser av – og forhåndsinnstilt er
  ingenting avkrysset.** Til hvert forslag står en setning om hva det
  betyr, og antallet treff i en eksempeltekst du kan legge ved. Det som
  **tar bort** beskyttelse, er merket som sådant: «alltid fjern dette
  begrepet» og «aldri fjern dette begrepet» ville ellers sett like ut i
  en liste. Forslag som ville passe på alt, vises ikke engang.

- **Kontrollprotokollen teller nå sammen over alle arbeidsplasser.**
  Legger et selskap protokollene via `protokoll_pfad» på en delt ressurs,
  skriver hver arbeidsplass sin egen månedsfil der – tidligere måtte en
  personvernansvarlig med tretti plasser se gjennom tretti filer
  enkeltvis. Over listen står nå en linje med summene for måneden, og
  **den melder brutte kjeder med navn**: En etterfølgende endring
  oppdages bare hvis noen ser etter, og i tretti filer sjekker ingen for
  hånd.

  **Ingen oppstilling per person** – heller ikke i denne visningen. En
  rangering «hvem har renset hvor mye» ville egnet seg for atferds- og
  ytelseskontroll, og det er det som teller etter medbestemmelsesretten,
  ikke hensikten. Telt blir kjøringer, filer og treff over hele huset.

- **«Foreslå profil fra et dokument»: spørre reglene én gang i stedet for
  å gå gjennom fireogførti typer.** I regelvinduet finnes en ny knapp: Den
  viser KI-nivået et dokument, fastslår hva det dreier seg om –
  legebrev, søknad, kontrakt, faktura, vedtak – og foreslår strategiene
  som passer. Ved legebrevet for eksempel forskyves datoangivelser i
  stedet for å erstattes, fordi kronologien er innholdet i en
  pasientjournal.

  **Profilene ligger i programmet, modellen velger bare** – sladdereglene
  avhenger ikke av hva en språkmodell synes er en god idé. Foreslått
  vises hvert punkt enkeltvis og med begrunnelse; overtatt blir
  ingenting uten tilbakespørsmål, og det du selv har fastsatt, forblir
  urørt. Uten KI-nivå forblir det ved den sikre standarden: plassholder
  for alt.

- **Ny strategi «dikt opp»: en troverdig falsk verdi i stedet for en
  plassholder.** «Fru Berger skrev til herr Doppler i Fulda» i stedet for
  «[NAME_1] skrev til [NAME_2] i [ORT_1]» – for opplæringsmateriell,
  demonstrasjonsmapper, testdatasett og alt som deretter forelegges en
  KI. Tiltaleform, setningsbygning og lesbarhet bevares.

  Samme verdi får samme falske verdi, over alle filene i en sak og på
  hver maskin med samme regelfil – **uten at det lagres noen tilordning
  noe sted** (samme mekanikk som ved hashing). E-postadresser ligger på
  reserverte eksempeldomener, telefonnumre i det for dette holdte
  området, oppdiktede IBAN-er bærer et riktig beregnet kontrollsiffer.
  Mulig for navn, steder, adresser, firmaer, e-post, telefon og IBAN; for
  andre typer avvises regelen, i stedet for å forbli virkningsløs.

  **Rapporten sier uttrykkelig at det er diktet opp.** Et slik renset
  dokument leses som et ekte og er det ikke – det duger ikke som bevis
  og må ikke videreformidles som original.

- **Motkontrollen: «Hvem forblir gjenkjennelig?»** En ny avkrysning under
  KI-nivået legger **det ferdige resultatet** enda en gang frem for
  språkmodellen og spør hvem som er gjenkjennelig til tross for rensing.
  Ment er tilfellet ingen gjenkjenning i verden finner, fordi det slett
  ikke står noe navn der: «den eneste jordmoren i distriktet», «kollegaen
  som sa opp etter brannen i mars». Ingen mønster griper, og på stedet
  vet likevel alle hvem det gjelder.

  **Det fjernes ingenting ved dette.** Stedene står med en setning
  begrunnelse i rapporten, og avgjøres blir det for hånd – et program
  som av seg selv tar setninger ut av et dokument fordi det synes de
  virker avslørende, gjør en rensing til en omskrivning, og ingen ville
  se hva som mangler. Høyst fem steder per fil; det modellen ikke kan
  belegge ordrett, faller bort. På kommandolinjen: `--restrisiko` sammen
  med `--ki`.

- **Veien tilbake fra KI-en: «Oversett svar tilbake».** Tidligere var
  bare halve løkken bygget – kopiere tekst, lime inn renset, forelegge
  KI-en. Svaret kom tilbake med `[NAME_1]», og den som trengte det, satte
  for hånd tilbake det han for hånd hadde tatt ut. Nå står tilbakeveien i
  menyen «Program»: Kopiér svar, klikk på oppføringen, de ekte navnene
  står der igjen.

  Tilordningen for dette ligger **bare i arbeidsminnet**, gjelder alltid
  bare for det sist rensede stedet og utløper etter en time; den som
  slår av utklippstavlevakten, kvitter seg med den umiddelbart. Hentes
  tilbake kan bare det som ble erstattet – sladdet, maskert og hashet er
  ikke reversibelt, og programmet sier hvor mange steder det derfor
  måtte la stå. Administrerte installasjoner slår tilbakeveien helt av
  via vorgaven `rueckweg`.

- **Overvåk mappe: det som legges inn, ligger like etter renset i
  utgangen.** For et postmottak, et postboksteam eller en skannemappe –
  sett opp én gang, deretter klikker ingen mer. Finnes under «Fil →
  Overvåk mappe …», på kommandolinjen via `--wache <mappe>`.

  Originalen blir liggende der den lå; ved ønske vandrer den uendret til
  undermappen «Ferdig», der ingenting noensinne overskrives. Berørt blir
  en fil først når den er ferdig skrevet – en fil som fortsatt kopieres
  over nettverket, ville ellers blitt lest halvveis og meldt som renset.
  Det som går galt, blir liggende og meldes, i stedet for å bli
  gjentatt i det uendelige. Og vakten husker det ferdige uten filnavn:
  Det som ligger i en innboks-mappe, avslører ofte allerede i navnet hva
  det dreier seg om.

  **Overvåking av en mappe utenfor egen brukerprofil – for eksempel på
  en nettverksstasjon – forutsetter en automatiseringslisens.** En mappe
  flere mennesker når, er en tjeneste og ingen arbeidsplass; i egen
  profil og under prøveperioden gjelder ikke begrensningen.

### Rettet

- **Innstillingene var avkuttet til høyre.** Vinduet åpnet seg med en
  fast størrelse, og den rakk bare for skriftstørrelsen det ble utviklet
  med: På Mac sto «Sjekk nå», «Endre …» og henvisningene ved siden av
  halvveis utenfor. Nå åpner det seg så bredt som sidene dets trenger –
  på hvert språk og ved hver skriftstørrelse, begrenset bare av
  skjermen.

- **«Sjekk nå» svarer nå synlig.** Resultatet sto i statuslinjen til
  hovedvinduet – altså bak innstillingsvinduet det ble spurt fra. Den som
  sjekket, så ingenting. Nå kommer svaret som en melding over
  innstillingene, og foreligger en ny versjon, fører den straks til
  installasjon. Ved programstart forblir det som før ved statuslinjen,
  uspurt åpner intet vindu seg.

- **Kopierte filer kom ikke frem på utklippstavlen på Mac.** Å legge
  rensede filer tilbake meldte suksess og la likevel ikke noe brukbart –
  liming ga ingenting. Berørt var alt som skriver filer til
  utklippstavlen.

- **Og fra utklippstavlen ble bare den første filen lest på Mac.** Den
  som kopierte tre filer i Finder og valgte «Rens utklippstavlen nå»,
  fikk to av dem urenset tilbake – uten at noe sa fra om det. Nå kommer
  alle.

- **«Kontroller fil» tar nå også imot dratte filer** – som hovedvinduet.
  Lagt til kommer i tillegg til den eksisterende utvalget i stedet for å
  forkaste det; å legge samme fil inn to ganger endrer ingenting, og det
  programmet ikke kan lese, meldes i stedet for å svelges.

- **Og vinduet sier at det venter på deg.** Det åpnet seg med en tom boks
  og en grå knapp «Kontroller» – dette ser ut som om ingenting er der,
  ikke som at valget mangler. Nå står det «Ingen fil valgt ennå – dra hit
  eller velg nedenfor via ‹Velg filer …›.»

- **En lang kjøring sier nå at den kjører.** «Tilleggsmodell for mer
  nøyaktig gjenkjenning lastes ned – et øyeblikk …» ble stående så lenge
  gjenkjenningen regnet: ved en fil med 47 500 ord altså atten minutter,
  selv om nedlastingen var ferdig etter ni sekunder. Den som ser dette,
  tror programmet har hengt seg opp. Nå følger «Mer nøyaktig gjenkjenning
  kjører – det tar noen minutter ved lange tekster», og statuslinjen
  teller med: «Mer nøyaktig gjenkjenning (7/312)». Meldt blir dette fra
  modellens løkke – hver 250. ord, altså omtrent hvert sjette sekund –,
  ikke per tekstblokk: En tekstblokk bærer tolv tusen ord og trenger
  minutter.

- **En avbrutt kjøring sier nå at den ble avbrutt.** Den som trykket
  «Avbryt», leste deretter «0 av 1 fil(er) renset.» – riktig talt og
  likevel feil opplysning. Meldingen om hvilken fil det gjaldt, ble i
  samme øyeblikk overskrevet av tellemeldingen. Og i fillisten sto
  fortsatt «kjører …», selv om ingenting lenger kjørte; der står nå
  «avbrutt».

- **Setningen om personvern var avkuttet.** «… ingen sky, ingen
  opplasting. Mer i personvern» – ved vinduets bredde programmet starter
  med, endte den midt i ordet. Den tar nå full bredde.

- **Lisenstjenesten kunne meddele noe, og ingen lyttet.** Når alle
  lisensplasser er belagt, lisensen har utløpt, nøkkelen er ukjent eller
  lisensforvaltningen hos leverandøren er avslått, sender tjenesten
  nettopp for dette en grunn – tenkt var fra begynnelsen at du skulle få
  den forklart **én gang**. Vist ble den aldri. Nå vises en henvisning
  som først sier at programmet fortsetter uendret å arbeide, deretter hva
  det gjelder. Én gang per grunn: Den som har klikket den bort, ser den
  ikke igjen ved den daglige kontrollen – men vel hvis grunnen endrer
  seg.

- **En flerplasslisens kjøpt i butikken viste «1 plass».** Butikken
  fordeler forberedte nøkler og holder det kjøpte plassantallet selv;
  vist ble imidlertid tallet fra selve nøkkelen, og det lyder ved hver
  lagernøkkel på én plass. Den som hadde kjøpt åtte plasser, leste «1
  plass» – og fra den andre påloggede maskinen sto visningen i rødt
  sammen med «Kontakt administrasjonen din». Nå gjelder tallet
  tjenesten sist meldte; uten svar forblir det ved nøkkelen, og mindre
  enn det kjøpte omfanget blir det aldri. Det samme gjelder for
  tilleggskjøp og forlengelser: De endrer plassantallet hos
  leverandøren, ikke nøkkelen din.

- **Etter kjøpet sto det «Lisensiert for Maskuro Privatlisens».** Dette
  er ikke et navn, men plassholderen nøklene forberedes under – navnet
  ditt kan ikke stå der, fordi nøkkelen signeres allerede før kjøpet. I
  stedet for å vise deg et fremmed navn som ditt eget, står det nå der
  rett og slett «Privatlisens» og plassantallet. Ved en lisens utstedt på
  deg, står navnet ditt der uendret.

- **I hjelpemenyen sto det «Hjelp _FAQ».** Og-tegnet var blitt til en
  understrek, fordi Qt leste det som markør for en tastaturbokstav. Nå
  står det «Hjelp & FAQ».

- **Innstillingsvinduet ble stående når programmet forsvant i ikonet** –
  og også når hovedvinduet ble lukket. Det følger nå med. (Gjelder bare
  denne versjonen; det egne vinduet er nytt.)

- **En avvist lisensforespørsel sier nå hva det skyldes.** Avviste
  lisenstjenesten en forespørsel uten å sende med en grunn, sto det i
  lisensvinduet i rødt «Ukjent svar.» – en setning verken du eller
  brukerstøtten kan gjøre noe med, og som fikk deg til å lete etter
  feilen ved din egen nøkkel. Nå står der hva som faktisk skjedde: at
  tjenesten avviste uten å begrunne det, og hvem du kan henvende deg til.
  Er lisensforvaltningen hos leverandøren midlertidig avslått, nevnes
  også det – sammen med henvisningen om at nøkkelen din ikke er berørt
  av det.

- **På Mac gjaldt oppsatte språk plutselig som manglende.** Ved oppstart
  meldte programmet «Ingen språkmodell er installert» og tilbød
  førstegangsoppsettet, selv om språkene lenge var lastet ned – den som
  så etter under «Dokumentspråk», fant dem der fullstendig. Programmet
  søkte dem alt etter oppstartsvei på to forskjellige steder: Ble det
  startet fra programmappen, fant det dem; ble samme bygg startet som en
  enkel mappe, søkte det dem ved siden av seg selv, der ingen ligger. Fra
  nå av gjelder på Mac unntaksløst samme sted i brukerprofilen, uansett
  hvordan programmet er pakket. Ingenting trenger å lastes ned på nytt.

- **«Hva er nytt» viste halve listen.** Vinduet etter en oppdatering
  avbrøt midt i setningen, og de resterende punktene sto som tomme
  punkttegn. Skyld hadde en plassholder i vinkelparenteser – for
  eksempel `<datei>.docx» – som visningen holdt for merking og fra hvor
  alt videre ble forkastet. Nettopp nyhetene om sikkerhet var berørt av
  dette. Hjelpen viser slike plassholdere alltid riktig; dette vinduet
  gjør det nå også.

- **Å kniple med to fingre zoomer nå i etterredigeringsvinduet.** På
  styreplaten er det *den* zoombevegelsen – i redigeringsprogrammet
  gjorde den tidligere ingenting, og den som ville se nærmere på et sted,
  måtte gripe til glidebryteren eller Ctrl+musehjul. Siden følger nå
  bevegelsen umiddelbart og tegnes skarpt igjen ved slipp.

- **Zoomes blir det på stedet man ser på.** Kniping forstørrer rundt
  punktet mellom fingrene, Ctrl+musehjul rundt punktet under pekeren.
  Knapper, hurtigtaster og zoomglidebryteren holder midten fast – til dem
  hører ikke noe sted man peker på. Tidligere ble bare rulleverdien
  stående ved alle: Fra en tilpasset side holdt dette overkanten, og alt
  under vandret ut av bildet ved innzooming.

- **«Før/etter» var i sidevisningen en død knapp.** Så lenge sidevisningen
  var på, lot den seg trykke – og meldte hver gang at originalen ikke lot
  seg åpne. Det finnes heller ingenting å sammenligne der: Sidevisningen
  er et avbilde av den rensede versjonen, det finnes ikke noe motstykke
  til originalen. Knappen er nå sperret og nevner ved overfaring grunnen
  samt utveien (tekstvisningen). Beskrivelsen dens lovet dessuten
  uttrykkelig at sammenligningen gikk «uavhengig av om tekst- eller
  sidevisning er aktiv» – det stemte aldri.

- **Sidevisningen fikk LibreOffice til å krasje.** Ble to sidevisninger
  generert samtidig – for eksempel «Sladd som PDF» mens forhåndsvisningen
  fortsatt regnet –, meldte systemet et LibreOffice-krasj, selv om
  sidene til slutt likevel dukket opp: Begge kjøringene tilgikk samme
  arbeidslagring til LibreOffice, noe det ikke tåler. Nå får bare én
  kjøring den om gangen; de øvrige unnviker til en egen. De trenger noen
  sekunder lenger til dette, men til gjengjeld kommer ingen feilmelding
  lenger, og ingen av kjøringene forblir uten resultat. Et andre
  gjengivelsesoppdrag ved siden av et kjørende blir dessuten ikke engang
  tatt imot.

- **«Vis original» kunne avslutte programmet.** Lot originalen seg ikke
  åpne – fordi den var flyttet, omdøpt, forsynt med et passord eller lå
  på en frakoblet stasjon –, avbrøt etterredigeringsvinduet uten
  forvarsel, og åpne arbeidskopier gikk tapt. Nå kommer en henvisning,
  bryteren hopper tilbake, og den rensede versjonen blir stående. Der
  originalen grunnleggende ikke passer ved siden av – for eksempel ved en
  PDF-sidevisning som oppsto fra en Word-fil – er bryteren sperret fra
  begynnelsen og nevner ved overfaring grunnen, i stedet for å vise samme
  henvisning ved hvert trykk.

- **Feilrapporter kom aldri frem.** Den som ville melde en feil, fikk «Motparten
  avviste rapporten» – og ingen hadde noensinne sett den. To årsaker,
  begge på veien: Programmet identifiserte seg ikke overfor serveren og
  ble derfor avvist av vernet mot masseaksess, og adressen viste til et
  andre navn som programmet ikke fulgte. Begge deler er rettet; en
  rapport går igjen ut. **Det samme rammet lisensaktiveringen**: Pålogging,
  avlogging og forespørsler nådde heller ikke tjenesten – der bare
  umerkbart, fordi en ubesvart forespørsel bevisst ikke endrer noe ved
  lisensen din. Og forblir et avslag likevel uforklarlig en gang, står nå
  det tekniske nummeret dets ved siden av, i stedet for at hver årsak ser
  lik ut.

- **Et klikk på «Vis original» kunne avslutte programmet.** Lot
  originalen seg ikke åpne – flyttet, omdøpt, på en frakoblet
  nettverksstasjon, forsynt med et passord eller skadet –, forsvant
  etterredigeringsvinduet sammen med alle åpne arbeidskopier. Nå blir
  omkobleren stående ved den rensede versjonen, og en boks sier hva som
  er i veien; den tekniske grunnen står i detaljene, hvis du vil melde
  den. Det samme gjelder et resultat som ikke lar seg vise: Vinduet åpner
  seg og sier det, i stedet for å forsvinne.

- **Spørsmålet om et krasj kom for ofte – og slettet sporet det spurte
  om.** Det vistes også når ingenting hadde krasjet: Merknaden oppstår så
  snart det et sted oppstår en uventet forstyrrelse, også når programmet
  overlever den og deretter avsluttes helt vanlig; ryddet bort ble den
  aldri. Og den som svarte «Nei», ødela de eneste detaljene om hendelsen
  – merknaden forsvant allerede ved *visningen* av spørsmålet. Begge deler
  er rettet: En ordnet avslutning rydder bort merknaden, spurt blir det
  nå bare ved et ekte avbrudd, og avkrysset blir det først etter svaret
  ditt. Detaljene står uansett i feilprotokollen på egen maskin – den som
  ikke vil sende noe, mister likevel ingenting med dette. Sendt blir
  fortsatt bare det du på forhånd har sett fullstendig og selv frigitt.

- **«Rens» kunne forbli stille sperret.** Blir språkmodellene hengende ved
  nedlasting, forble knappen slått av – uten forklaring. Et klikk på den
  gjorde ingenting, og statuslinjen sa uendret «Språkmodeller lastes ned
  …», også etter ti minutter. Årsaken: Forstyrrelser i
  bakgrunnsforløp gikk til et sted ingen ser ved oppstart fra
  filbehandleren; tilbake ble et vindu som så arbeidsklart ut og ikke
  reagerte på noe klikk. Nå havner slike forstyrrelser i feilprotokollen,
  nedlasting av språkmodellene melder mislykketheten sin i alle
  tilfeller i stedet for å stille gi opp, og forblir det likevel stille,
  sier applikasjonen etter et trekvarters minutt at noe ikke stemmer, med
  et råd i detaljene. Den sperrede knappen nevner ved overfaring grunnen
  sin. En lang første nedlasting gjelder ikke som stillhet ved dette – så
  lenge fremdrift meldes, forblir det rolig. Som krasj teller ikke dette
  i det hele tatt: Applikasjonen fortsetter å kjøre, og ved neste
  oppstart spørres det derfor heller ikke om det.

- **På Mac fant programmet ikke lenger noen oppdateringer – og sa det var
  på det nyeste nivået.** Mac-versjonen brakte ikke med seg noe katalog
  over rotsertifikater; den søkte det på et sted som bare finnes på
  maskinen den bygges på. Dermed kunne den ikke kontrollere hos noen
  server hvem den snakket med, og avbrøt hver forbindelse: ingen
  oppdateringer, ingen lisensaktivering, ingen nedlasting av
  språkmodeller, ingen feilrapport. Eldre versjoner gjorde dette
  stilltiende til opplysningen «Du bruker den nyeste versjonen».
  Sertifikatene ligger nå i selve programmet; finner det ingen der, tar
  det systemets, og på Mac i nødstilfelle nøkkelringens – og finnes det
  overhodet ingen, sier det det, i stedet for å hevde en nyeste versjon.
  Selve kontrollen slås aldri av ved dette.

  Denne ene oppdateringen må Mac-brukere fortsatt installere manuelt: En
  versjon som ikke når serveren, kan heller ikke fornye seg selv.

### Endret

- **Hovedvinduet er ryddet opp.** Nederst sto seks like store knapper ved
  siden av hverandre – «Om …», «Veiledning» og «Hjelp & FAQ» under, selv
  om de samme tre veiene allerede sto i hjelpemenyen over. De er nå
  samlet til én knapp «Hjelp» som klapper dem opp; ingen går tapt. Igjen
  nederst blir de to veiene man virkelig begynner med: «Rens» og «Sladd
  manuelt …».

- **Det programmet nettopp gjør, står nå på et fast sted.** Meldingen
  («Språkmodeller lastes ned …», «(3 / 7) brief.pdf», «5 av 7 fil(er)
  renset.») hang tidligere som grå tekst mellom to knapperader. Den har
  fått en egen flate, med et farget punkt foran: grått så lenge
  ingenting kjører, blått under arbeidet, grønt etter en glatt kjøring og
  gult når det er kommet henvisninger. Punktet sier ikke noe som ikke
  står ved siden av – det sier det bare raskere.

- **Innstillingene har blitt et eget vindu.** De lå tidligere i
  hovedvinduet – en boks med fire faner man klappet opp under «Flere
  innstillinger», og som deretter var for liten for innholdet sitt: Det
  sto alltid et rullefelt i den, og valget mellom anonymisering og
  pseudonymisering sto halvveis utenfor bildet. Knappen heter nå
  «Innstillinger …» og åpner et vindu med en sidelinje; hver av de fire
  sidene får plass i sin helhet. Hovedvinduet hopper ikke lenger opp ved
  åpning, og man kan se fillisten ved siden av. Endret har seg bare hvor
  innstillingene står – hvilke som finnes og hva de gjør, er uendret.

- **«Detaljer» klapper opp, i stedet for å hoppe.** Vinduet vokste
  tidligere i ett bilde, og man måtte lete etter det som hadde endret
  seg. Nå beveger det seg dit.

- **Skriftstørrelser og avstander følger samme mål i hele vinduet.**
  Overskrifter var to steder forskjellig store, og likeverdige linjer sto
  forskjellig langt fra hverandre. Synlig er dette som ro, ikke som en
  enkelt endring.

- **Anonymisering er nå standarden.** Tidligere var pseudonymisering
  forhåndsinnstilt: Samme personer fikk samme nummer (`[NAME_1]»,
  `[NAME_2]»), referanser forble lesbare – rettslig forble det likevel
  **personopplysninger**. Den som ikke stiller inn noe, får nå
  fremgangsmåten som tar dataene ut av GDPR: Alle treff av en type heter
  det samme (`[NAME]»). Nummereringen er fortsatt et valg, det står
  uendret i samme vindu; eksisterende innstillinger forblir som de er.
  På kommandolinjen stiller `--pseudonymisieren» (også
  `--mit-nummerierung») tilbake.

- **Anonymiserte plassholdere lar seg ikke lenger angre enkeltvis.** Den
  som anonymiserer, får for hver person samme plassholder – og dermed
  finnes det ikke lenger noe enkeltsted som hører til et bestemt navn.
  Etterredigeringsvinduet tilbød likevel «Angre erstatning»: Et klikk
  ville satt inn *én* av verdiene på *alle* stedene. Linjene er nå
  dempet som ved sladdede angivelser, klikket sier grunnen, og et for
  hånd etterjustert funn får ikke lenger et nummer som ikke finnes noe
  sted i resten av dokumentet.

  Av samme grunn finnes det etter en anonymisert kjøring ikke lenger noe
  «Oversett svar tilbake» – tidligere ville det satt et fremmed navn på
  stedet til hver person. Den som trenger denne løkken, velger
  «Pseudonymiser»; applikasjonen sier det nå også slik, i stedet for å
  vise til en utløpt tilordning.

  På kommandolinjen avbrytes nå `--zuordnung» ved anonymisering, i
  stedet for å skrive en fil som ikke er en tilbakeoversettelse – i
  vinduet var avkrysningen for lengst sperret. Enten `--pseudonymisieren»
  i tillegg eller utelate `--zuordnung»; meldingen sier det. Resultatet
  oppstår da overhodet ikke, slik at et skript ikke står igjen med
  halvferdig arbeid.

- **Oppdateringskanalen står nå på nytt på «Stabil».** Uten eget valg
  rettet kanalen seg tidligere etter hvilket bygg den løpende versjonen
  stammet fra – den som en gang hadde prøvd en testversjon, fikk fra da
  av varig tilbudt testversjoner. Et kanalbytte er en avgjørelse og skal
  også forbli det; standarden er derfor «Stabil». Innstilte kanaler
  forblir urørt.

### Forbedret

- **«Beschwerdevorgang» gjelder ikke lenger som stedsnavn.** I
  overskriften «Saksnotat – Beschwerdevorgang 12 C 345/26» sladdet
  programmet saken med: Språkmodellen holdt den for et sted, og det
  uavhengig av omgivelsene. Tatt med er ikke enkeltordet, men
  **grunnordet** i sammensetningen – «vorgang» og «notiz» dekker dermed
  også forretnings-, bokførings- og betalingssak eller telefonnotatet. Av
  tretti kontrollerte forvaltningsbegreper utløste tidligere tre et
  falskt treff, nå ingen lenger; funnet blir fortsatt alt som står ved
  siden av («Beschwerdevorgang: Bernd Meisinger» mister navnet, ikke
  overskriften).

- **Anonymisering fører igjen bok – for etterjusteringen og protokollen.**
  I den anonymiserende driftsmodusen husket programmet ikke de funnede
  verdiene. To ting forble dermed stumme: den dokumentomfattende
  konsistens-etterjusteringen (et etternavn som senere dukker opp alene,
  ble stående) og listen over erstatninger i kontrollprotokollen. Så
  lenge anonymisering var det sjeldnere valget, ble det knapt lagt merke
  til – som standard ville det blitt normaltilfellet. I dokumentet endres
  ingenting: Plassholderen forblir uten nummer.

- **«Ingen personopplysning» heter nå «ingen personopplysningsangivelse».**
  I angre-dialogen og i ansiktsadvarselen sto det juridiske *Datum* –
  entallsformen av «data». Det ble lest som en kalenderdag, særlig fordi
  applikasjonen andre steder tilbyr «Fjern også datoangivelser». Det
  heter nå overalt «angivelse», slik som i de fire grunnene over i samme
  vindu.

- **Opphavslinjen står nå bare i «Om»-vinduet.** «Made with ♥ in Austria»
  satt nederst i hovedvinduet midt i knapperaden og leste seg der som en
  ytterligere trykknapp. Den står fortsatt i «Om»-vinduet – der man leter
  etter den.

- **Ablagesflaten har nå en synlig kant.** Den stiplede kanten var så
  blek at den knapt skilte seg fra vinduet – det var likegyldig så lenge
  flaten bare var en flate. Siden den ble en trykknapp man kan hoppe til
  med Tab-tasten, er denne streken det eneste som viser den som et
  betjeningselement; den er derfor hevet til verdien normen krever for
  det.

## 0.10.22-beta.1 – 15. august 2026

### Nytt

- **Slås overvåkingen av utklippstavlen av, er den virkelig av.** Vakten
  holder de siste innholdene i arbeidsminnet, slik at originalen kan
  legges tilbake – tidligere også når du hadde slått av overvåkingen. Nå
  glemmes historikken ved avslåing. Dette koster gjenopprettingen etter
  avslåing, og nettopp slik er det ment: Avslått betyr avslått.
- **Feilprotokollen inneholder ikke lenger filstier.** Den lå bare på
  maskinen din og ble aldri sendt av seg selv – men den førte stier i
  klartekst, og et filnavn røper ofte mer enn innholdet. Av
  «…/Skilsmisse_Mueller_Forlik.docx» blir det nå ved skriving
  `<fil>.docx`; endelsen forblir, fordi den teller ved feilsøking. Det
  samme gjelder merknaden etter et krasj.
- **Listen over erstatninger advarer nå i seg selv.** Den er den eneste
  filen der originaldataene dine står i klartekst, og den ligger ved
  siden av resultatet – den som videreformidler en mappe, gir den med.
  Nå står advarselen som første linje **i** filen, utdataområdet nevner
  hele stien i stedet for bare filnavnet, og på kommandolinjen nevnes
  filen overhodet først: Der fikk man tidligere overhodet ikke vite at
  den var oppstått.
- **Å anonymisere eller pseudonymisere er nå et navngitt valg.** På dette
  stedet sto tidligere en avkrysning «Gi like navn samme betegnelse – KI-en
  gjenkjenner da fortsatt hvem som er hvem». Den beskrev nytten og
  fortidde følgen: Fortløpende nummererte plassholdere (`[NAME_1]`,
  `[NAME_2]`) er **pseudonymisering**, og pseudonymiserte data forblir
  personopplysninger – den som trodde han hadde anonymisert med dette,
  tok feil. Nå står begge fremgangsmåtene ved siden av hverandre, hver
  med sin pris. Standarden forblir pseudonymisering, fordi et dokument
  som deretter fortsatt leses eller behandles av en KI, trenger
  referansene sine. Ved anonymisering er listen over erstatninger sperret:
  Den ville gjort resultatet sporbart igjen. Håndbok og FAQ forklarer
  forskjellen på alle 18 språk; på kommandolinjen heter bryteren nå også
  `--anonymisieren`.
- **Linjen over ablagesflaten sier nå det som faktisk stemmer.** Den lovet
  «100 % lokal behandling – uten sky og konto, GDPR-vennlig». For
  dokumentene dine stemmer dette, for programmet ikke i denne
  generaliteten: Det ser etter oppdateringer, melder på ønske feil, laster
  ned modeller og registrerer kjøpte arbeidsplasser. Nå står der det
  snevrere og holdbare utsagnet: Dokumentene dine forlater ikke maskinen.
- **Ved resultatet står det nå alltid at det bør kontrolleres.** Tidligere
  meldte Maskuro etter en glatt kjøring «12 angivelse(r) fjernet» i grønt
  og ellers ingenting – dette leses som en garanti om å ha funnet alt.
  Henvisninger vistes bare når det konkret var noe som ikke kunne
  kontrolleres (bilder, ukjente vedlegg). Nå står det under hvert resultat
  uoverkommelig at ikke alle personopplysninger gjenkjennes i alle
  tilfeller, at kontrollen ligger hos brukeren, og at det manglende må
  suppleres manuelt – i vinduet, i utdataområdet og på kommandolinjen.
  Ingen meldingsboks å klikke bort: Setningen står varig der.
  Hurtigveiledningen sier det nå med samme ordlyd.
- **Etter en oppdatering står det ved oppstart hva som har endret seg.**
  Tidligere gikk en oppdatering stille gjennom og var ikke til å skille
  fra en omstart. Nå vises «Hva er nytt» én gang – og den som har hoppet
  over en versjon, ser dem som ligger mellom, med. Ikke ved aller første
  oppstart: Der innfører fortsatt hurtigveiledningen.
- **Kinesisk og japansk finner nå navn.** Tidligere fant de **ingen** –
  ikke få, ingen. Begge språkmodellene manglet ordsegmenteringen, uten
  hvilken en setning uten mellomrom gjelder som ett eneste ord;
  programmet gikk stille over til den flerspråklige reservemodellen. Begge
  språkene gjenkjenner nå personer og steder som de øvrige. Den japanske
  ordboken lastes ved dette sammen med språket og ligger ikke i
  programmet – alene ville den vært godt 200 MB, som ellers hver enkelt
  hadde måttet bære med seg.
- **Romania er valgbart som land.** Det manglet tidligere helt. Dermed
  gjenkjennes rumenske adresser («Strada Victoriei 30»), postnumre med
  sted («010061 București») og Cod Numeric Personal – sistnevnte bare med
  stemmende kontrollsiffer, slik at ikke hvert trettensifret tall på en
  faktura markeres. Frem til da ble postnummeret stående leselig ved
  siden av det sladdede stedsnavnet i rumenske dokumenter.
- **«Rastrer side» i redigeringsprogrammet.** Lar tekst seg ikke fjerne fra
  en PDF – det forekommer ved filer fra fremmede generatorer –, erstattes
  siden nå ved ønske med avbildet sitt: Teksten er dermed uigjenkallelig
  borte, siden forblir leselig og søkbar. Advarselen som melder tilfellet,
  tilbyr trinnet med det samme som en knapp; via «Verktøy → Rastrer side»
  går det også av seg selv. Angre henter siden tilbake.
- **Grensesnittet finnes nå også på kroatisk, gresk, litauisk, slovensk,
  japansk og koreansk.** Dermed er det atten språk. Håndbok, FAQ og
  rettstekster er fullstendig med på alle seks. Merkingene i det rensede
  dokumentet følger grensesnittet ved dette – av `[NAME_1]` blir det
  `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` eller `[氏名_1]`. **Ved gresk,
  japansk og koreansk står merkingene latinsk** – `[ONOMA_1]`,
  `[SHIMEI_1]`, `[IREUM_1]`. Grensesnittet forblir i sin egen skrift; bare
  det som skrives inn i dokumentet, er latinsk. Grunnen er PDF-tegnsettet:
  Der ankom greske og japanske merkinger tidligere som `[??_1]`, og dermed
  lot navn seg ikke lenger skille fra sted.
- **Ni land kommer til, og sju eksisterende blir fullstendige.** Nylig
  gjenkjent blir identitets-, skatte- og trygdenummer samt adresser for
  **Kroatia, Slovenia, Hellas, Litauen, Nord-Makedonia, Russland,
  Ukraina, Kina og Japan**. Ved de eksisterende landene er hull lukket som
  veide tyngre: For **Nederland** og **Portugal** fantes det tidligere
  overhodet ikke noe personnummer – den nederlandske BSN og den
  portugisiske NIF ble ikke gjenkjent, selv om de står på praktisk talt
  hvert dokument i disse landene. Polen får skattenummeret NIP, Danmark,
  Norge og Finland sine adresser, Canada sitt postnummer. Dermed er det
  **35 land**.

### Fjernet

- **For Linux finnes det foreløpig ikke lenger noen pakke.** Kildekoden
  kjører der, men tre ting denne veiledningen lover, mangler under Linux:
  automatisk oppstart, globale hurtigtaster og – avhengig av
  arbeidsmiljø – symbolet i linjen. Å levere en pakke som kan mindre enn
  beskrevet, ville vært feil vei. Windows og macOS er uberørt.

### Forbedret

- **Saksnummer finnes nå på alle språk.** «Aktenzeichen 12/2026-AB» ble
  fjernet, «File reference 12/2026-AB» eller «Sygnatura 12/2026-AB» ble
  stående: Feltordene Maskuro gjenkjenner et slikt nummer med, fantes bare
  på tysk. Nå kjenner det motstykkene på tolv språk – og som før erstattes
  bare selve nummeret, merkingen foran blir stående, slik at det i
  resultatet er gjenkjennelig hva som ble fjernet der.
- **Maskuro bruker i hviletilstand rundt et halvt gigabyte mindre.** Ved
  oppstart ble tidligere også tilleggsmodellen til den mer nøyaktige
  gjenkjenningen lastet, slik at den første rensingen ikke venter på det.
  Etterprøvd kostet dette 648 MB arbeidsminne og sparte 1,9 sekunder – og
  det kostet også når du bare åpner vinduet og lukker det igjen. Modellen
  lastes nå ved første gang det trengs; statuslinjen sier fra om det.
  Språkmodellen lastes fortsatt ved oppstart – det trenger overvåkingen av
  utklippstavlen umiddelbart.
- **Ablagesflaten kan nå betjenes også uten mus.** «Dra filer hit» var en
  flate som reagerte på klikk – med tastaturet kom man ikke til, og en
  skjermleser leste den opp som en ramme med tekst i, ikke som det den
  er. Den er nå en trykknapp: Tab-tasten hopper til den, mellomrom- og
  enter-tasten åpner filvalget, og den som har hoppet til den, ser det på
  kanten. Via menyen «Fil → Velg filer» gikk det allerede før, men det
  måtte man vite.
- **Navnet på den rensede filen leses nå også opp.** I fillisten står det
  som en andre, mindre linje under originalen – men den ble bare tegnet
  der, og en skjermleser nevnte bare originalen. Nettopp denne linjen er
  bygget mot misforståelsen om at en kjøring var virkningsløs, fordi den
  uberørte originalen ligger i mappen. Linjen lyder nå opplest «rechnung.pdf,
  Resultat: rechnung_bereinigt.pdf».
- **Betjeningselementer uten merking sier nå hva de er til for.**
  Symbolknappene i fillisten, tegneknappene i etterredigeringsvinduet og
  alle valg- og inndatafelt var navnløse for skjermlesere – de ble
  annonsert som «trykknapp» og «kombinasjonsfelt», uten om hva. Knappene
  på en linje nevner samtidig filen: I en liste med tjue oppføringer hørte
  man ellers samme setning tjue ganger.
- **Den som betjener med tastaturet, ser igjen hvor han står.** Knappen
  «Rens» og symbolknappene i fillisten er fargelagt, og dermed sluttet
  rammen systemet ellers legger rundt det tilhoppede
  betjeningselementet – ved tabbing hoppet blikket ut i intet. Begge har
  nå en egen ramme så snart de er i tur. Knappene endrer ikke størrelsen
  sin ved dette.
- **Sju skriftfarger var for bleke, i begge utseendene.** Etterprøvd
  etter den vanlige normen (WCAG 2.1) lå de bleke henvisningslinjene,
  bitekstene på ablagesonen, punktene i veiledningen og i det mørke bildet
  i tillegg blått og rødt under grensen på 4,5:1 – leselig ved godt lys og
  gode øyne, ellers ikke. Alle er hevet; nyanseringen forblir, tekstene
  leser fortsatt som bitekster. Tre til – fargene meldinger om advarsel og
  suksess meldes i – holdt grensen bare så vidt og er trukket med: Den
  som ikke leser dem, leser ikke opplysningen om noe gikk galt. Synlig
  endret seg bare knappen «Rens» i det mørke bildet: Den bærer nå mørk i
  stedet for hvit skrift, som aksentknappene i Windows 11 også gjør.
- **Hver linje i fillisten har nå sitt eget kryss.** Tidligere måtte man
  først velge linjen og deretter klikke «Fjern» – to trinn for en
  bagatell. Krysset står til høyre i linjen og trenger ett. Knappen
  «Fjern» under er dermed bortfalt; den som vil kvitte seg med flere
  linjer på én gang, velger dem og bruker oppføringen i kontekstmenyen,
  som også sier hvor mange det er. «Fjern alle» blir. Fjernet fra listen
  blir alltid bare linjen – aldri en fil på disken.
- **Før KI-kontrollen står det nå om denne maskinen egner seg for det.**
  Tidligere sto det i vinduet bare hvor stor modellen er. Den som slo den
  på på en svak maskin, merket først ved det første dokumentet at det tar
  svært lang tid – etter 5,4 GB nedlasting. Nå nevner vinduet **på
  forhånd** arbeidsminne og ledig plass og sier hva det betyr; **etterpå**
  måles hastigheten og nevnes i den størrelsen det gjelder: «Et
  tisiders dokument tar på denne maskinen omtrent 12 minutter.» Er det for
  tregt, fraråder programmet og tilbyr å slå nivået av igjen – det forbyr
  ingenting.
- **Hastighetsmålingen kjører nå på hver maskin.** Tidligere kom den bare
  når grafikkakselerasjonen i tillegg var satt opp – noe som bare finnes
  under Windows. På alle andre maskiner anslo programmet derfor varigheten
  ut fra en fremmed maskin, og nettopp der det er tregt, bommet anslaget.
- **Tyrkiske adresser finnes nå også i skanningen.** På et innskannet
  brevhode ble «34710 İstanbul» stående leselig, mens samme angivelse i
  teksten ved siden av forsvant: Tekstgjenkjenningen leser den tyrkiske İ
  uten prikken sin, og mønsteret forventet en stor bokstav. Det samme
  gjaldt «Bağdat Caddesi».
- **Spanske adresser uten eget gatenavn gjenkjennes.** «Gran Vía 5» ble
  stående, fordi mønsteret bak gatetypen fortsatt forventet et navneord –
  ved «Calle Mayor» finnes det ett, ved «Gran Vía» er typen selv allerede
  navnet. Det samme gjelder nå for «La Rambla» og «Castellana».
- **I vinduet «Om dette programmet» står nå en åpenhetshenvisning** om at
  applikasjonen ble utviklet med støtte fra kunstig intelligens. Den
  gjelder tilblivelsen av programmet, ikke arbeidsmåten dets: Det renses
  fortsatt utelukkende på egen maskin.
- **«Håndter språk» viser nå de brukbare språkene først.** For halvparten
  av de 48 språkene finnes det ingen egen språkmodell; der gjenkjenner en
  flerspråklig reservemodell navn bare svakt, i enkelte skriftsystemer
  ikke i det hele tatt. Side om side i en liste så alle likeverdige ut.
  Standarden viser derfor bare språk med egen modell – via «Vist» kan de
  øvrige når som helst vises, med en setning om hva de kan og ikke kan.
  Ingenting faller bort, og den som har satt opp et begrenset språk,
  beholder det.
- **Spørsmålet om et manglende språk nevner nå utveien.** Gjenkjennes et
  språk det ennå ikke er satt opp noe for, tilbød programmet tidligere
  bare «Last ned» eller «Fortsett uten». Gjenkjenningen kan imidlertid
  bomme – ved korte skjemaer og lister med lite løpende tekst avgjør få
  ord. I vinduet står det derfor nå at man kan avbryte og velge riktig
  språk manuelt, i stedet for å bruke «Gjenkjenn automatisk». Dette sparer
  i tvilstilfelle en nedlasting på flere hundre megabyte for et språk som
  slett ikke trengs.
- **Plassholdermerkinger snakker nå grensesnittspråket.** «[NAME_1]»,
  «[ADRESSE_2]» og lignende sto tidligere alltid på tysk, uansett hvilket
  språk som var innstilt eller på hvilket språk dokumentet var forfattet.
  Nå følger de grensesnittspråket – på engelsk altså «[NAME_1]»,
  «[ADDRESS_2]». Ikke dokumentspråket: Det er ved «gjenkjenn automatisk»
  gjettet og av og til feil; grensesnittspråket er det aldri.
- **Færre tilbakespørsmål ved etterredigering.** Hvor resultatet lagres,
  står nå varig nederst i linjen («→ vertrag_bereinigt.pdf», mappen i
  verktøytipset) – et klikk på det velger et annet sted, uten å lagre med
  det samme. Tilbakespørsmålet ved første lagring bortfaller dermed.
  Spørsmålet «allerede redigert – begynne på nytt?» kan huskes for
  økten, og to henvisningsvinduer som bare ga en opplysning, står nå i
  statuslinjen. Gjenstår gjør spørsmålene som forhindrer en ikke
  reverserbar skade: det ulagrede arbeidet ved lukking og advarselen om
  ikke fjernet tekst.
- **Resultatet sier nå hvor selve skanningen ikke var leselig.** På et
  innskannet dokument leser enhetens tekstgjenkjenning ikke alt riktig –
  av «Solarstraße 9» blir det da for eksempel «Solaret^aß« B». Det som
  slik ble feillest, kan ingen kontroll lenger finne: Det ser for hvert
  søkemønster ut som bokstavsalat. Programmet kan ikke gjøre noe med
  dette, men nevner nå slike steder med sidenummer – som regel er det
  stempler, brevhoder eller håndskrevne tillegg der. En henvisning, ingen
  advarsel: Ved et satt dokument forblir den av.
- **Fillisten viser nå hva resultatet heter.** Under filnavnet står etter
  kjøringen navnet på den rensede filen («→ vertrag_bereinigt.pdf»).
  Tidligere sto det bare i protokollen bak «Detaljer», og den som så etter
  i mappen, fant den uberørte originalen. Navnet på kilden blir stående –
  ellers ville det ikke lenger vært synlig hvilken fil et resultat stammer
  fra.
- **Knappene i en ferdig linje er større og tydeligere.** Se, etterrediger
  og «Vis i mappe» var flate symboler uten flate og gikk under i listen –
  samtidig er de etter kjøringen det eneste man fortsatt klikker på.

### Rettet

- **På fremmedspråklig grensesnitt ble egne regler for sladding,
  maskering og hashing stilltiende oversett.** Den som hadde fastsatt at
  navn skulle sladdes i stedet for erstattes, fikk dem likevel erstattet –
  så snart programmet ikke ble betjent på tysk eller engelsk.
  Innstillingen sto der, den virket bare ikke, og i resultatet var
  forskjellen ikke synlig. Berørt var ni av de tolv grensesnittspråkene.
- **Innstillingen «Språk for merkingene» hadde ingen virkning utenfor tysk
  og engelsk.** «Tysk» og «Engelsk» lot seg velge, men i dokumentet sto
  fortsatt grensesnittspråket. Nå virker alle tre mulighetene;
  forhåndsinnstillingen «som grensesnittet» leverer uendret det samme som
  før.
- **I korte tekstutdrag ble navn stående – for eksempel i et kopiert
  e-postsitat.** Den som renset et utdrag via utklippstavlen, fikk der
  ofte bare e-postadressen sladdet, navnet under ikke. Avgjørende var det
  rene linjeantallet: Fra seks linjer gjenkjente programmet utdraget som
  en oppstilling og fant navnene, under det ikke – et kopiert e-postsitat
  har fem. En hvilken som helst ekstra linje, for eksempel et emne, veltet
  resultatet. Nå holder det med fire linjer, og i målingen forsvinner alle
  kontrollerte navn i stedet for en tredjedel. På lengre dokumenter og på
  løpende tekst har dette ingen virkning.
- **Grafikkakselerasjonen for KI-kontrollen ble tidligere slått av igjen
  så snart man hadde satt den opp.** Etter oppsettet måler programmet om
  grafikken på denne maskinen virkelig er raskere enn prosessoren – denne
  målingen mislyktes imidlertid alltid, uten å si det, og resultatet
  «begge like raske» avgjorde for prosessoren. Den som hadde lastet ned
  65 MB, fikk deretter mindre enn før. Målingen kjører nå; mislykkes den,
  endrer den ikke lenger noe.
- **Tidsestimatet regnet på hver maskin med fremmed hastighet.** Det
  støtter seg på samme måling; så lenge den ikke kjørte, gjaldt verdien
  til utviklingsmaskinen. «Omtrent to minutter» kunne dermed på en treg
  maskin bety en halvtime.
- **KI-nivået arbeider med en ny, betydelig bedre språkmodell**
  (Qwen3.5-9B i stedet for Qwen3-4B) og er ikke lenger begrenset til tysk
  og engelsk, men arbeider på tolv språk. Målt over kontrollkorpuset: like
  mange funnede angivelser som uten nivået, men mindre enn halvparten så
  mange overflødige sladdinger (75 → 31). Modellen er større (5,4 i
  stedet for 2,4 GB) og trenger omtrent dobbel regnetid; ved påslåing
  lastes den ned én gang, den gamle fjernes samtidig.
- **Adresser på fransk, italiensk, spansk, portugisisk, polsk, tyrkisk og
  svensk fjernes nå fullstendig.** Tidligere forsvant der bare gate- og
  stedsnavnet – husnummer og postnummer ble stående leselige
  («[ORT_1] 28, 28013 [ORT_2]»). For disse språkene fantes det ingen egne
  adressemønstre; de er nå supplert.
- **Gresk og koreansk fant overhodet ingen navn.** Ved gresk skyldtes det
  reservemodellen – med den egne modellen, som nå lar seg laste ned,
  gjenkjennes navn og steder rent. Ved koreansk skyldtes det programmet:
  Det forutsatte at et navn begynner med stor bokstav, og hangul kjenner
  ingen store bokstaver. Berørt var fremfor alt korte enheter –
  tabellceller, skjemafelt, listeoppføringer.
- **En språkmodell som ikke lot seg laste ned, avbrøt rensingen.** I
  stedet for en feilmelding trer den flerspråklige modellen nå inn, og
  resultatet henviser til at det ble arbeidet med den svakere
  gjenkjenningen. Gjelder for øyeblikket kinesisk og japansk, hvis
  modeller trenger en ordoppdeling programmet ennå ikke har med.
- **Et språk med egen modell gjaldt som installert så snart et vilkårlig
  annet var lastet.** Den som for eksempel satte opp tyrkisk, fikk dermed
  den flerspråklige reservemodellen – og kinesisk, japansk, koreansk
  eller gresk sto deretter med avkrysset boks og «0 MB» i listen, selv om
  den egne modellen manglet. De lot seg dermed aldri lastes ned på nytt og
  arbeidet varig med den svakere reserven. Nå viser listen den faktiske
  statusen samt nedlastingsstørrelsen.
- **Et bortfalt gjenkjenningsnivå tidde.** Var «Utvidet gjenkjenning»
  eller «Maksimal gjenkjenning (KI)» slått på, men lot modellen seg ikke
  kjøre, fortsatte programmet å arbeide uten nivået – uten et ord om det.
  Resultatet så ut som hvert annet, og bryteren sto fortsatt på «på»: Man
  holdt altså resultatet av grunnivået for det beste man kunne få.
  Resultatet sier det nå og nevner begge deler – hva som ikke ble
  kontrollert og hvordan modellen kan lastes ned på nytt. Tilfellet er
  ikke sjeldent: På enkelte maskiner mislykkes KI-nivået ved nedlasting
  når grafikkakselerasjonen mangler.
- **En feil ved nedlasting av tilleggsmodellen avbrøt hele rensingen.**
  Ved «Utvidet gjenkjenning» var bare evalueringen av modellen sikret,
  ikke innlesingen dens – og nettopp der går det galt hvis filen er
  skadet eller ikke passer maskinen. I stedet for en feilmelding finnes
  det nå et resultat fra grunnivået samt henvisning.
- **Et språk lot seg ikke lenger fjerne – og dermed heller ikke lastes ned
  på nytt.** Den som i «Håndter språk» fjernet avkrysningen og overtok
  endringen, leste «Tysk fjernet», men så avkrysningen straks satt igjen.
  Årsaken var overtakelsen fra programmappen: Ved en installasjon for
  alle brukere ligger språkmodellene skrivebeskyttet i programmappen, og
  programmet henter manglende derfra i stedet for å laste ned hundrevis
  av megabyte på nytt. Denne overtakelsen kjørte med ved hver tilgang –
  og kopierte det nettopp slettede språket tilbake i samme åndedrag. Den
  skjer nå bare én gang; nedlastede språkmodeller bevares ved dette. I
  tillegg sjekker programmet etter sletting: Det som ikke lot seg fjerne,
  meldes nå som mislykket i stedet for «fjernet».
- **Ved en installasjon for alle brukere lot nedlastet innhold seg ikke
  lagre.** Den som installerer programmet for alle brukere, har det i
  «Programfiler», og dit får ingenting skrives uten
  administratorrettigheter. For språkmodellene var det lenge siden
  fastsatt et alternativt sted, for annet ikke:
  - **Sidevisningskomponenten** ble etter 290 MB nedlasting pakket ut i
    programmappen og mislyktes der – uten å nevne noen grunn. Den ligger
    nå ved språkmodellene, der den etter planen alltid skulle ligge.
  - **Grafikkakselerasjonen** kan ikke unnvike: Den bytter ut biblioteker
    i selve programmet. I stedet for først å laste ned og deretter
    mislykkes uten ord, sier programmet nå på forhånd at det ikke går
    her og hva det betyr – den maksimale gjenkjenningen fortsetter å
    arbeide, bare via prosessoren.
  - Et medfølgende **språk for tekstgjenkjenningen** lot seg ikke
    fjerne: Det ble straks gjenopprettet fra programmappen. Samme årsak
    som ved språkmodellene, samme rettelse.
  - Ved fjerning av et språk kunne **språkdata fra en fremmed
    Tesseract-installasjon** bli slettet. Berørt blir nå bare den egne
    mappen.
  - Det alternative stedet gjaldt tidligere bare under Windows. Et
    Linux-arkiv til `/opt` hadde samme nød uten samme utvei.
- **Ved etterredigering forsvant en hel linje, selv om bare ett ord var
  rammet inn.** Den som i en allerede renset fil sladdet en plassholder,
  mistet linjen den sto i: Av «Kjære fru Doktor [NAME_1]» ble det
  ingenting igjen – og meldingen sa til dette «ett ord fjernet fra
  dokumentet». Berørt var hver fil som allerede en gang hadde gått
  gjennom programmet, altså nettopp tilfellet etterredigeringen finnes
  for. Den øvrige teksten blir nå stående, på uendret sted.
- **«EMPLOYEES» over en navneliste ble selv sladdet.** Samme tilfelle som
  «MITARBEITER» i 0.10.19, bare på engelsk – der hadde det blitt stående.
  I versaler mangler språkmodellen kjennetegnet, og overskriften står
  over lutter ekte navn. Navnene under gjenkjennes fortsatt. Ikke tatt
  med ble «staff»: Det er et belagt etternavn, og oppføringen ville tatt
  med seg hver «John Staff» – samme avveining som den gang med
  «Arbeiter».
- **Rettsformen ble erstattet en andre gang.** På et innskannet brevhode
  leste språkmodellen «GmbH», adressen og postnummeret som **ett** sted.
  Adresse og postnummer skar seg deretter ut stykkene sine, og igjen ble
  rettsformen stående som et eget treff: I resultatet sto det
  «[ORT_1] [ORT_2]», der «[ORT_1] GmbH» var ment. Firmanavnet erstattes
  fortsatt – bare det nakne tillegget blir nå stående, og resultatet
  leser seg som et brevhode i stedet for en hull-tekst-øvelse.
- **Et tilskåret treff ble ikke kontrollert på nytt.** Årsaken til
  tilfellet over, og den rekker videre: Filtrene mot gjettede treff kjørte
  på det gjenkjennerne **melder** – ikke på det som blir igjen etter
  overlappingsoppløsningen. Blir et langt treff beskåret av en sterkere
  gjenkjenner, er bruddstykket en annen tekst enn den vurderte, og ingen
  så nærmere på den igjen. Nå gjør det det.
- **«Du bruker den nyeste versjonen» – selv om det slett ikke kunne
  sjekkes.** Den som hadde stilt oppdateringskanalen på «Forhåndsvisning
  (Beta)» eller «Stabil – anbefalt», fikk denne opplysningen, selv om det
  hittil overhodet ikke var kommet noe på disse kanalene. Nå sier
  programmet nettopp dette – og foreslår å velge en annen kanal i
  innstillingene.
- **Å lukke vinduet under nedlasting fikk en tråd til å krasje.** Den som
  startet Maskuro og straks lukket vinduet igjen mens språkmodellene
  fortsatt ble lastet, fikk i protokollen en feilrapport: Nedlastingen
  meldte seg til et vindu som ikke lenger fantes. Synlige følger hadde
  ikke dette, men i protokollen sto et krasj, der noen bare var raskere
  enn programmet.
- **Resultatet ses nå på, ikke bare leses etter.** Tidligere gjaldt en
  side som ren når verdien ikke lenger sto i teksten. På en skanning er
  det ikke noe bevis – der er den synlige teksten et bilde. Til slutt
  sjekkes derfor om flaten i resultatet virkelig er sladdet; står der
  fortsatt lyst papir, sier rapporten det uttrykkelig, i stedet for å
  melde «erstattet».
- **En erstattet angivelse ble stående i bildet.** Sto verdien på et
  bilde – et innskannet brevhode, et stempel, en hel skannet side –, ble
  den riktignok fjernet fra dokumentteksten, men var fortsatt **synlig**:
  Det mennesket leser der, er bildepunkter. Rapporten meldte likevel
  «erstattet». Nå sladdes flaten i bildet, uansett hvilken strategi som
  er innstilt, og plassholderen står lys på denne bunnen – stygt, men
  ærlig, og tilordningen bevares. Lar et bildeformat seg ikke bearbeides,
  sier resultatet det nå uttrykkelig, i stedet for å se rent ut.
- **På en skanning manglet plassholderen helt.** Tekstlaget til en skannet
  side tegnes usynlig, og en plassholder som ble satt inn i det, arvet
  dette: satt inn, men ikke synlig. Ved funnstedet sto det etterpå
  ingenting.
- **En tekstgjenkjenning som slett ikke kunne kjøre, gjaldt som bestått.**
  Manglet språkfilen eller avbrøt gjenkjenningsmotoren, meldte rapporten
  «Bilde(r) … ble kontrollert med tekstgjenkjenning (0 funnsted(er))» –
  altså en kontroll som aldri fant sted. Ved en skanning er det den
  eneste kontrollen i det hele tatt: En kontrakt med leselig adresse i
  sidebildet gjaldt dermed som ferdig. Nå sier rapporten at ingenting ble
  kontrollert, og hvorfor.
- **Språkfilen ble søkt i feil mappe.** Lå det i den egne
  språkmappen andre språk enn dokumentets, fikk gjenkjenningsmotoren
  nettopp denne mappen forelagt og mislyktes – selv om det passende
  språket lå ved siden av. Nå søkes **språket**, ikke mappen.
- **Advarselen om ikke fjernet tekst rådet til noe som ikke finnes.** Den
  henviste til «Sladd som PDF» – men det genererer en PDF-visning av
  *kontor*filer og er slett ikke tilgjengelig ved en PDF. Den som ville
  følge advarselen, lette forgjeves. Nå står knappen der som ordner
  saken.
- **I redigeringsprogrammet havnet striper og plassholdere ved siden av
  det markerte stedet.** Berørt var hver PDF der en linje ender på en
  bindestrek og ordet fortsetter på den neste – ved skanninger er dette
  særlig påfallende, fordi kontraktstekster gjennomgående er satt med
  orddeling. De to linjehalvdelene gjaldt som *ett* ord som strekker seg
  på tvers av satsspeilet, og hver ramme i nærheten av det overtok denne
  utstrekningen. Selve gjenkjenningen endres ikke ved dette:
  Målekorpuset leverer samme resultat som før.
- **Redigeringsprogrammet advarte om at teksten «fortsatt sto i
  dokumentet», selv om den var fjernet.** Forekom samme ord flere ganger
  på en side – i kontrakter regelen –, meldte selvkontrollen etter hvert
  inngrep et mislykket resultat. Den teller nå forekomstene, i stedet for
  bare å sjekke om ordet fortsatt finnes et sted. Ved en ekte mislykkethet
  advarer den uendret.
- **Resultatfilen het på hvert språk «_bereinigt».** Ment var alltid at
  navnetillegget følger grensesnittspråket – på engelsk gjorde det det
  også («_cleaned»), på de øvrige seksten språkene ikke. Den som brukte
  programmet på finsk, fikk «asiakirja_bereinigt.pdf». Nå heter filen
  «asiakirja_puhdistettu.pdf», på japansk «書類_除去済み.pdf» og så
  videre – hver gang med ordet samme grensesnitt bruker i sin
  ferdigmelding. Den som har stilt inn et eget tillegg, beholder det.
- **«Håndter språk» merket seg alltid tysk.** I listen over de 48
  dokumentspråkene sto de tyske navnene, uansett hvilket grensesnitt som
  var innstilt: En finsk bruker leste «Chinesisch». Nå står navnet der på
  sitt eget språk og bak det egennavnet – «Kiina (中文)». Egennavnet er
  bevisst: Den som gjenkjenner språket på sitt eget navn, finner det også
  når det finske ordet ikke sier ham noe.

## 0.10.19 – 12. august 2026

### Forbedret

- **Oppføringen i kontekstmenyen snakker nå ditt språk.** Tidligere sto der
  den tyske ordlyden på hvert system – også på en engelsk Windows. Nå følger
  den det innstilte grensesnittspråket, og den som endrer språk, får
  oppføringen omdøpt umiddelbart, uten å installere på nytt. (Windows; under
  macOS og Linux er menynavnet samtidig et filnavn – det kommer senere.)
- **Redigeringsprogrammet husker hvilken visning du sist arbeidet i.** Den
  som bruker sidevisningen, får den automatisk ved neste dokument – uten å
  skru den på hver gang. Den som aldri har brukt den, merker ingenting: Den
  gjenopprettes bare når byggeklossen som trengs allerede er lastet, det
  lastes aldri noe ekstra for dette.

### Rettet

- **«MITARBEITER» over en navneliste ble selv sladdet.** I
  medarbeiderkataloger og organisasjonskart forsvant overskriften som
  antatt navn – den står der over lutter ekte navn, og med store bokstaver
  mangler språkmodellen sitt beste kjennetegn. Navnene under blir fortsatt
  funnet.
- **Mengdeangivelser ble tatt for adresser.** I fakturaer, følgesedler og
  lagerlister forsvant angivelser som «3390 Protokoll», «1030 Beløp» eller
  «3390 Lager» som antatt postnummer med sted – firesifret ser alt ut som et
  østerriksk postnummer. Står det et ord bak tallet som applikasjonen
  kjenner som saksord, avdeling, aktivitet eller feltbetegnelse, blir det nå
  stående. Ekte stedsangivelser er uberørt, også slike som samtidig er et
  slikt ord («4692 Ort»). Ikke løst er dermed tilfellet der det står et helt
  vanlig ord bak tallet («3390 Regal») – det krever et postnummerregister.
- **Hjelpen nevnte et menypunkt som ikke finnes.** Veiledning, bilde og
  meldingen ved slutten av installasjonen omtalte «Rens dokument for KI»;
  oppføringen i kontekstmenyen heter derimot «Fjern personopplysninger». Den
  som fulgte hjelpen, lette forgjeves. Alle tre stedene omtaler nå
  menypunktet slik det virkelig heter.
- **«Start med systemet» lot seg ikke skru av.** Den som hadde krysset av
  «Start med Windows» under installasjonen, så likevel en tom avkrysning i
  innstillingene – og verre: Å skru av og på i applikasjonen hadde ingen
  virkning, programmet fortsatte å starte med Windows. Grunnen var to
  steder der Windows ser etter oppstartsprogrammer; applikasjonen kjente
  bare til ett av dem. Nå telles begge, bryteren viser den sanne tilstanden
  og virker i begge retninger. Også tatt hensyn til: Den som skrur av
  oppføringen i Oppgavebehandling, ser det nå i applikasjonen – og den som
  skrur den på igjen der, opphever dermed avskruingen.
- **Overskrifter over navnelister ble sladdet.** «TEILNEHMERLISTE
  WERKSTATTGESPRÄCH» eller «MITARBEITERÜBERSICHT INNENDIENST» over en liste
  med personer forsvant som antatt navn. Med store bokstaver mangler
  språkmodellen sitt beste kjennetegn, og på tysk er hvert substantiv
  stort forbokstav – «Teilnehmerliste Werkstattgespräch» ser da ut som «Anna
  Huber». Sammensetninger på `-liste`, `-dienst`, `-gespräch`, `-sitzung` og
  `-besprechung` blir nå stående. Grunnordene alene gjelder fortsatt som
  navn: *Liste* og *Dienst* er belagte etternavn, *Teilnehmerliste* er det
  ikke.
- **Loddrett satte angivelser fikk en uleselig plassholder.** Saksnummer i
  sidemargen, saksbehandlerkode ved innbindingen, loddrette tabelloverskrifter:
  Slike angivelser ble riktignok funnet og fjernet, men plassholderen kom ut
  på tvers over teksten, klemt sammen til én til to punkt og til dels utenfor
  papirkanten. Nå følger den teksten – loddrett, i lesestørrelse og i samme
  retning som angivelsen sto. Det samme gjaldt sider som ble dreid i
  etterkant (vannrett skrevet tekst med registrert sidedreining, slik enkelte
  utdataprogrammer leverer); også der står plassholderen nå slik man ser på
  siden. «Sehr geehrte Frau Doktor Anneliese Berger» ga bare «Anneliese» som
  navn – «Berger» ble stående i dokumentet. Det samme rammet hvert navn med
  mellomnavn («Frau Anna Maria Berger»). Grunnen var regelen for navnet bak
  en tiltaleform: Den hadde to ordplasser, og en tittel eller et mellomnavn
  brukte opp den første. Med «Dr.» ble det aldri synlig – punktumet bryter
  regelen, og språkmodellen fanget opp hele navnet. Nå hoppes titler over
  uten å koste en plass, og navnet kan bestå av tre deler. En rolle **bak**
  navnet fungerer fortsatt ikke: «Frau Anna Huber Geschäftsführerin»
  erstatter navnet, ikke rollen.
