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
