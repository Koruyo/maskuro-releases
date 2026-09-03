# Ändringar

Vad som ändras från version till version – beskrivet ur programmets
synvinkel, inte ur dess inre. Den som vill veta *vad* det är byggt av hittar
det i [LIZENZEN.md](LIZENZEN.md); här står vad som ändras för arbetet med det.

Numreringen följer den vanliga räknesättet: den **första** siffran ändras när
något inte längre fungerar som förut, den **andra** vid nya funktioner, den
**tredje** vid felrättningar.

---

## 0.10.50-alpha.20260903 – 3 september 2026

- Återkommande företagsmärken i PDF-filer rensas nu konsekvent, även när
  textigenkänningen läser namndraget olika på en sida eller helt hoppar
  över den runda logotypen. En uttrycklig avmarkering i förhandsvisningen
  förblir bindande och kan inte upphävas av någon senare efterdragning.

- Valutalösa priser i skannade tabeller maskeras nu fullständigt även när
  tabellhuvud och värden ligger i olika överlappande PDF-bilder. Mängder,
  timmar, vikter och procent förblir kvar; långt åtskilda tal binds inte
  längre av misstag samman till ett belopp.

- Underskriftssökningen fångar nu även belagda svaga blå namndrag och
  smala röda signaturförkortningar. Prickade diagram, mätkurvor, stämplar,
  logotyper och breda röda redigeringsmarkeringar är undantagna från denna
  snäva efterdragning.

- Maskeringar i roterade, speglade, skevade eller beskurna PDF-bilder
  träffar nu den verkliga bildpolygonen. Tekniska roller i
  prestationsposter, fordons- och däcksakord samt teknisk „kompensation"
  avgränsas samtidigt striktare mot falska träffar; uttryckligen betecknade
  kontaktroller och telefonnummer förblir skyddade.

- Synkontrollen före sparande av ett PDF-dokument fryser inte längre
  fönstret: vid stora dokument med många fyndställen stod det tidigare
  flera sekunder utan återkoppling; nu visas en hänvisning att kontroll
  pågår, och fönstret fortsätter rita.

- Återhämtning av ett värde från en bild i efterbearbetningseditorn läser
  varje originalbild bara en gång via textigenkänning; tidigare kördes
  den på nytt vid varje ytterligare återtagning för samma bilder.

- Nedladdning av hög-nivån och underskriftsmodellen behöver nästan inget
  arbetsminne längre: 596 MB-paketet hölls tidigare helt i minnet,
  kontrollerades och packades upp där – över en gigabyte topp i det
  körande programmet, på datorer med 8 GB den stund då allt började
  hacka. Nu flödar det blockvis till disken och kontrolleras och packas
  upp där.

- Sökningen i efterbearbetningseditorn fryser inte längre stora
  PDF-filer: den första bokstaven i sökfältet läste tidigare in alla
  sidor på en gång – vid 200 sidor stod fönstret still i två sekunder,
  och efter varje maskering igen. Sidorna läses nu bitvis; till dess står
  „Läser in …" i räknaren, resultatet är detsamma.

- Rastrerade PDF-sidor – efter en textigenkänning eller när en text inte
  gick att ta bort rent – sparas nu märkbart mindre och utan
  bildförlust: i stället för att alltid kodas som JPEG kodas varje sida
  även förlustfritt, och den mindre versionen hamnar i filen. En rensad
  skanning krymper på så vis från 248 till 48 KB, övningsdokumentet med
  textigenkänning från 913 till 702 KB; texten förblir knivskarp.

- Nedladdade modeller (hög-nivå, underskrifter, ansikten, andra
  textigenkänning) släpps nu ur arbetsminnet igen efter tio minuter utan
  rensning. Tidigare förblev de laddade till programmets slut – den som en
  gång använt en underskriftssökning och hög-nivån höll varaktigt över
  två gigabyte. Nästa körning laddar dem åter på en till två sekunder;
  statusraden meddelar det.

- PowerPoint: släktnamnen för bildlayouter och bildmallar („Tom",
  „Titelbild") ersätts inte längre som en uppgift. „Tom" är även en ort
  och maskerades felaktigt i varje tysk och engelsk presentation; rensade
  blir nu bara de för hand tilldelade namnen på själva bilderna.

- I PDF-filer drar radutjämningen inte längre in nästa rads huvud i ett
  fynd: numret på nästa listpunkt bakom ett datum gällde som
  telefonnummer, ett fälthuvud som „Kenncode" eller „Auftragsnummer"
  bakom en siffra som postnummer med ort, och ortsraden under adressen
  dubblerade orten. Det respektive korrekta, kortare fyndet trängdes
  därigenom undan. Över 132 korpus-PDF-filer blir av 24 ytterligare
  utjämningsfynd de två riktiga kvar; i praxiskorpuset sjunker de falska
  larmen från 29 till 21 vid samma fyndkvot.

- „Sök igenom och maskera PDF-mapp" i efterbearbetningseditorn blockerar
  inte längre fönstret: körningen arbetar i bakgrunden, förlopp och
  avbrytknapp reagerar, och menyer eller flikar kan inte längre användas
  mitt i en halvfärdig fil.

- Skannade sidor med fyndställen skrivs vid maskering nu bara om en gång
  i stället för två: tidigare fyllde programmet rutorna för fyndställena
  och de för motiveringarna i två omgångar, och den andra komprimerade
  den just nysparade skanningsbilden ytterligare en gång. Det sparar tid
  på stora skanningar och en kvalitetsförlust i bilden.

- Bläddring, zoomning och miniatyrerna i efterbearbetningseditorn
  reagerar snabbare: varje renderad sida gick tidigare som PNG genom en
  komprimering och genast tillbaka igen, bara för att visas – på skärmar
  med hög upplösning cirka en tiondels sekund per sida. Bilden kommer nu
  direkt fram, bildpunkt för bildpunkt densamma.

- Synkontrollen före sparande av ett PDF-dokument („utmatningsprov") är
  cirka tre gånger snabbare, vid samma resultat.

- Huvudfönstret står ännu en gång cirka en fjärdedels sekund tidigare:
  kontrollen av om textigenkänningen är redo på denna dator kördes vid
  fönsteruppbyggnaden – på Mac tillsammans med en provfråga till
  systemigenkänningen – och inställningssidan för tilläggskomponenterna
  frågade därtill av status för alla 48 språk. Båda sker nu i bakgrunden
  respektive först när språklistan verkligen öppnas; till dess står
  „Textigenkänning kontrolleras …".

- Efter en underskriftssökning belägger programmet cirka 300 MB mindre
  arbetsminne: igenkänningsmodellen låg dittills dubbelt i minnet – en
  gång för att kontrollera dess äkthet, en gång för beräkning. Den
  kontrolleras fortfarande, bara utan den andra kopian.

- Textigenkänningen i PDF-filer har blivit märkbart snabbare: för varje
  fälthuvud på en sida („Geburtsdatum:", „Steuernummer:") skickades
  tidigare ett eget prov genom igenkänningen per uppgiftstyp – på varje
  sida på nytt, även när samma huvud redan stod tio sidor tidigare.
  Svaret kommer nu ihåg; en tvåsidig prestationsförteckning ställde på så
  vis 324 frågor, nu bara de olika. Fynden är desamma.

- Stora tabeller rensas åter på sekunder i stället för minuter: i
  anonymiserande drift – förvalet – blev jämförelsen av redan kända
  värden långsammare med varje ytterligare cell, eftersom ett
  mellanlager kastades och byggdes upp på nytt vid varje träff. 5 000
  celler behövde för det cirka 18 sekunder, nu en halv; resultatet är
  tecken för tecken detsamma.

- Huvudfönstret visas ännu en gång märkbart snabbare: inställningarnas
  landlista drog vid fönsterbygget in hela igenkänningsbiblioteket i
  förgrunden – cirka 0,7 sekunder på Mac, motsvarande mer på Windows –
  trots att bara ländernas namn behövs för det. Listan kommer nu från
  en lätt katalog; biblioteket laddas som avsett i bakgrunden medan
  fönstret redan står. Detta gäller även efter varje språk- eller
  utseendebyte som startar om programmet.

- Dokumentlaboratoriet driver nu avskurna fälthuvuden, lokala värdeskuggor
  och kraftiga skanningsbeskärningar fullständigt genom PDF-, DOCX- och
  ODT-behållare. Matrisen omfattar 680 filer från 40 dokumentfamiljer och
  17 behållaraxlar. Maskuro tar bort i de nya samt de fullständiga
  grund- och kännetecknsprofilerna alla börvärden, utan uppmätt falskt
  larm, skadat bevarandevärde eller avbrott.

- Flera gånger använda skanningar kontrolleras och rensas nu via varje
  synlig placering: dokumentlaboratoriet delar samma bildobjekt över
  olika sidor, storlekar och rotationslägen i PDF och refererar samma
  bilddel flera gånger i DOCX och ODT. Tekniska ODT-ramnamn som
  „Formularscan klein quer" gäller inte längre som person; fria namn och
  orter med liknande början förblir skyddade. En allmän formulärgissning
  från den avslutande PDF-sidkörningen kan inte längre skapa ett stort
  falskt adressfynd på en redan oberoende läst bildyta. De 120 nya
  behållarna når i grund- och kännetecknsprofil alla 813 respektive 840
  börvärden utan falskt larm, bevarandeöverträdelse eller avbrott; den
  fullständiga 800-filers kännetecknsavstämningen bekräftar 5 600/5 600.

- Det tyska OCR-laboratoriet omfattar nu 560 skanningar från 40
  dokumentfamiljer. Nya varianter skär av fälthuvud- och sidmarginaler
  eller lägger en skugga direkt över ett värde. Maskuro skyddar därvid
  även namn, adresser, födelsedatum, medicinska nycklar och betecknade
  identifieringsnummer med delvis skadad text. Samtidigt ersätts
  formulärfältrester, officiella rubriker samt sakliga rätts- och
  informationsbegrepp inte längre som personer eller orter. De
  fullständiga grund- och kännetecknsprofilerna når 3 794/3 794 respektive
  3 920/3 920 börvärden utan uppmätt falskt larm eller avbrott.

- Det automatiska PDF-bildvalet tar inte längre bort storskaliga
  produktfoton, energietiketter och porträttrader enbart för att de
  börjar vid övre sidkanten. Riktiga platta huvud-/fotbilder och
  brevhuvuden som ansluter till bladkanten faller fortfarande bort. I
  personalförteckningar identifieras namn nu även då den synliga
  dokumenttiteln bara finns som bild, ur strukturellt upprepade poster.
  Igenkänningen är inte längre skräddarsydd för två konkreta rollord och
  förkortningen „DW": ett till fyra radbrutna roller samt „Durchwahl",
  „Nebenstelle", „Ext." och „Extension" härleds ur den gemensamma
  byggformen. Roller och avsnittshuvuden blir kvar, även när
  språkmodellen efter överlappningsupplösningen bara lämnar kvar ett
  rolladjektiv. Vågräta rollraster gäller inte längre av misstag som
  namnkolumner. Klistrar sid-OCR:n ihop flera kort till ett extremt brett
  ord med versaler mitt i, skiljer en snäv lokal motkontroll de
  verkliga ordrutorna åt; därigenom förblir varken ett enskilt namn eller
  ett brett felstreck kvar. Upprepade flerradiga företagslogotyper
  maskeras utifrån en redan bekräftad identisk pixelmall även på sidor
  utan användbar OCR-text och vid upp till två pixlars lägesavvikelse;
  kortare lokala andraläsningar av OCR:n får samtidigt inte längre
  komplettera ett större huvudområde med ett hittat namn. Sidnummer
  framför ett företagsbrevhuvud hör inte längre till organisationsnamnet,
  numeriskt inledda riktiga varumärkesnamn förblir skyddade. Flera
  uppmätta produkt-, fack- och formulärord föreslås inte längre som
  personer.

- Underskriftssökningen körs vid PDF-filer först efter OCR-bildrensningen,
  besöker även sidor utan vanlig texträff och räknar tillbaka
  fyndrutor på roterade sidor korrekt till dokumentrymden. Täta
  produktfoton maskeras inte längre som underskrift. Ovanför entydigt
  betecknade signaturfält sluter en snäv streckreserv tunna modellluckor;
  tomma linjer med förtryckt datum utlöser den inte.
  Rena skanningar med uteslutande OCR-/underskriftsfynd avbryts inte
  längre i denna fas på grund av en bildmaskerare som först laddas i
  textgrenen.

- Många samtidigt öppna dokument förblir urskiljbara i
  efterbearbetningseditorn: flikarna krymper inte längre till ett rent
  uteslutningstecken, och en listknapp till höger visar alla fullständiga
  filnamn under varandra. Flikar går att ordna om genom dragning och tas
  bort med sitt kryss från samma lista som i huvudfönstret; osparat
  arbete klargörs fortfarande först. Ett högerklick erbjuder dessutom
  „Stäng", „Stäng andra flikar" och „Stäng flikar till höger".

- En kortvarig Windows-spärr av virusskanner eller söktjänst gör inte
  längre att den färdiglästa språkmodell- respektive ordboksmappen
  misslyckas med „Åtkomst nekad" vid det avslutande insättandet. Maskuro
  försöker nu detta sista mappbyte igen under en kort stund.

- Det tyska dokumentlaboratoriet kontrollerar behållare nu även med
  växlande PDF-sidrotation, oberoende roterade PDF-bilder samt skalade
  och beskurna tabellbilder i DOCX och ODT. Fältvärden i synligt roterade
  bilder identifieras åter fullständigt, tekniska kolumnbeteckningar
  ersätts inte längre som orter, och namn med gemensamt efternamn
  splittras inte längre av konsekvenskontrollen i dubbla deltraffar. Den
  till 320 filer fördubblade matrisen når med inkopplad datum-, penning-
  och medicinigenkänning 2 240/2 240 börvärden utan uppmätt falskt larm
  eller avbrott.

- Flersidiga bild-PDF-filer, blandade text-/bild-PDF-filer och i DOCX
  eller ODT inbäddade skanningar kontrolleras nu i ett eget
  160-filers-laboratorium över alla 40 tyska dokumentfamiljer. Tekniska
  ODT-ramnamn och betecknade enhetskoder ersätts inte längre som orter;
  riktiga namn, orter och adresser i samma strukturer förblir skyddade.
  Med inkopplad medicin- eller penningigenkänning tas dessutom en direkt
  följande dosering respektive ett betalningsintervall bort fullständigt.
  Behållar-, textgrund-, textkänneteckens- och OCR-kännetecknskörningar
  når tillsammans sina respektive fullständiga nivåer utan uppmätt falskt
  larm eller avbrott.

- Säkerhetskontrollen före sparande visar nu iögonfallande PDF-ställen
  som en enskilt valbar lista. „Kontrollera i editorn" öppnar exakt den
  valda sidan och markerar området; överlappande deltraffar på samma
  ställe visas nu bara en gång. De nya hanteringstexterna finns
  fullständigt på alla 17 översatta gränssnittsspråk.

- Markdown-filer behåller vid ersättning sin referens-, betonings- och
  fotnotssyntax. Maskuro läser för detta en teckenmässigt lika lång
  version utan Markdown-markeringar; understreck i e-postadresser,
  räknestjärnor och vanliga referenser utan personuppgift förblir
  oförändrade.

- Flera handskrivna poster på samma PDF-sida söks nu i upp till tre
  omgångar. Redan hittade drag döljs bara i arbetsbilden, så att de inte
  längre tränger undan svagare underskrifter; på roterade sidor hamnar
  maskeringsytorna åter på det synliga fyndstället. Bildfyllningar från
  tidigare säkerhetsfaser bevaras vid den efterföljande återskrivningen.

- „Återställ alla inställningar" omfattar nu även „Text i bilder". Är
  OCR-komponenten inte tillgänglig, förblir brytaren tekniskt av, utan
  att felaktigt markeras som avvikande från leveransläget.

- Stora bildfragment vid övre sidkanten gäller inte längre enbart på
  grund av sin position som sidhuvud. Därigenom bevaras särskilt
  bildbaserade artikelbeskrivningar och tabellinnehåll. Nyidentifierade,
  typexakta e-post- och formulärfynd filtreras dessutom inte längre bort
  från den avslutande synkontrollen på en redan kontrollerad bildyta.

- Tekniska positions- och artikelrader i klimat- och elerbjudanden
  särskiljs striktare från personer, orter och organisationer. Det gäller
  bland annat kabeltyper, AC-försörjning, positionsnummer samt
  versalproduktkoder; riktiga namn och adresser förblir skyddade.

- Kontrollen av verkliga rensade PDF-filer förväxlar inte längre
  prisbeståndsdelar som `1 699,59` med telefonnummer och skär inte
  längre ut något påstått kortnummer ur ett fullständigt datum som
  `08.05.2025`. Namn bakom en tilltalsform slutar vid radbrytningen
  i stället för vid följande gata; ortnamn i bilagefilnamn begränsas till
  den faktiska orten. Fordonsfärger, tekniska statusvärden,
  näringsbeteckningar och produktbolagsformer förblir likaså bevarade.
  Skadade platshållartolkningar som `|PLLZ` behandlas inte längre som
  personuppgift vid en andra OCR-omgång.

- Sidoställda PDF-bilder får vid den avslutande synkontrollen en extra
  blick i sitt oförändrade bildläge. Denna får uteslutande efterskärma
  värden som Maskuro redan säkert identifierat på samma sida. På så vis
  täcks till exempel en liten roterad adresstämpel fullständigt utan att
  nya ord från bildrubriker eller tekniska ritningar hittas på som
  personuppgifter.

- I OpenDocument-texter töms nu en anteckningsförfattares initialer
  (kommentar) tillsammans med författaren. LibreOffice lagrar dem bredvid
  det fulla namnet som en egen kortform och visar just den i
  sidmarginalen; hittills stod „SO" kvar där, medan „Sieglinde Ortner"
  bredvid för länge sedan var en platshållare. Tömning sker bara när
  författaren verkligen ersatts – en avdelnings anteckning behåller sin
  beteckning.

- I italienska affärsbrev gäller standarduttrycken i satsbörjan inte
  längre som namn eller ort: „Restiamo a disposizione", „Rimaniamo",
  „Attendiamo", „Alleghiamo", „Comunichiamo" och „Auguriamo buon lavoro"
  hängde tidigare kvar som en påstådd person eller ortsangivelse. Riktiga
  namn på samma ställe („Rossi Mario") identifieras fortfarande.

- Tvåspaltiga skanningar skyddar nu betecknade identifierare och
  ortsangivelser även när textigenkänningen levererar först alla
  fälthuvuden och sedan alla värden. Tilldelningen följer den synliga
  pixelraden och fungerar även vid sidor roterade 90 grader. Tätt
  åtskilda delar av en pass- eller avtalsidentifierare maskeras
  tillsammans; betecknade födelsedatum, ICD- och PZN-nycklar täcks
  likaså, efterföljande sakord blir kvar. Korta namn och användarnamn
  skyddas vid exakta fält; e-postadresser uppdelade i flera OCR-ord bara
  vid tät närhet och fullständig e-postgrammatik. En fältbunden
  rättelse av förväxlingsbara tecken samt lokal omläsning av ett ännu
  tomt personfält täcker skadade och roterade skanningar utan att utvidga
  sakfält eller redan belagda värden. Säkerhetsmarginaler följer
  ordstorleken, och kännetecknsprofilen tar med sig direkt
  intilliggande doseringsenheter och betalningsintervall. Lätt snett
  inmatade formulär projiceras tillbaka geometriskt ur flera
  riktningslika OCR-rader; avrundningsbrus eller motsägande vittnen
  räcker inte. Korta bokstavsprefix förblir kvar framför en
  bindestrecksidentifierare, och ett fullständigt betecknat adressfynd
  ersätter bara sitt likartade gatudelfynd. Ett feltolkat rollfälthuvud
  faller uteslutande i en formulärkolumn belagd med minst tre kända
  huvuden; chattnamn förblir skyddade. En knapp kantbeskärning och en
  lokal överexponering med diagonal ljusreflex kompletterar bildmatrisen.
  Personer-, orts- och företagsfynd som sträcker sig över flera
  formulärrader begränsas i en flera gånger belagd fältkolumn till
  respektive värde. Ett tekniskt positionsvärde faller bara med
  positionshuvud och passande identifieringsform; riktiga namn förblir
  skyddade. Även vid ljusreflexen avbrutna e-postvärden tas bort bakom
  ett uttryckligt e-postfälthuvud med snäv, grannbegränsad bildkant. Två
  fält-värde-par på samma synliga rad utvärderas nu oberoende av
  varandra; värden på en djupare baslinje kopplas bara efter tre
  överensstämmande geometriska vittnen. Därigenom förblir
  identifieringsnummer, födelsedatum och adresser fullständigt skyddade
  även i täta formulärlayouter. Gata, postnummer och ort sammanförs
  uteslutande inom samma adressfält och med passande postal grammatik.
  Snävt avgränsade sakfält för arbets-/hjälpmedel och tandstatus skapar
  inte längre falska orts- eller registerlarm; riktiga namn och liknande
  benämnda fält förblir skyddade. Det tyska dokumentlaboratoriet omfattar
  nu 440 skanningar och når 2 981/2 981 i grundprofilen samt 3 080/3 080 i
  kännetecknsprofilen. Alla elva bildmutationer och alla 40
  dokumentfamiljer ligger på 100 procent, fortfarande utan uppmätt
  falskt larm, bevarandeöverträdelse eller avbrott.

- PDF-textskikt med förlorade cellavgränsare begränsar nu
  organisations-, adress- och ortsfynd utifrån den upprepade
  fält-värde-strukturen. Fälthuvuden framför företagsvärden och tekniska
  pilar som `=>` eller `->` hör inte längre till träffen. Den extra vyn
  för mjuka radbrytningar får inte längre utvidga bolagsforms- och
  ortsfynd över flera tabellrader; en redan fullständig adress slutar
  före nästa fälthuvud med värde. Den avslutande körningen över alla
  1 600 TXT-, HTML-, PDF- och DOCX-dokument tar bort 10 840/10 840
  börvärden vid noll falska larm, noll bevarandeöverträdelser och noll
  avbrott.

## 0.10.44-beta.1 – 1 september 2026

- Paketbygget skapar separata utgåvor för Windows x64 och ARM64, macOS på
  Apple Silicon och Intel samt Linux x64 och ARM64. Paketnamn,
  uppdateringsval och utgåvor skiljer på arkitekturen; en publicering
  förblir spärrad så länge ett av de sex målen eller dess
  beroendebelägg saknas. Linux ARM64 kräver på grund av Qt minst glibc
  2.39. Fullständigt godkända på riktig hårdvara är tills vidare bara
  Windows x64 och macOS på Apple Silicon; de övriga arkitekturpaketen
  ska tydligt betecknas som förhandsversioner för prövning i stället
  för produktiv användning.

- Vid flera filer fortsätter igenkänningen nu arbeta medan en
  förhandsvisning väntar på genomgång. Upp till tre förberedda
  förhandsvisningar visas efter varandra; samtidigt beräknas fortfarande
  bara ett dokument, och en resultatfil skapas först efter dess
  frigivning. Ett i förhandsvisningen valt varaktigt undantag gäller
  även för redan förberedda efterföljande dokument.

- Redaktionscertifikat går nu att kontrollera när som helst direkt i
  Arkiv-menyn mot det maskerade dokumentet. Maskuro skiljer därvid en
  passande signerad fil, ett passande men osignerat belägg, en ogiltig
  signatur och ett dokument som inte hör till certifikatet. En licens
  eller det ursprungliga operativsystemskontot krävs inte för
  kontrollprovet.
  För automatiska kontrollstationer finns samma jämförelse tillgänglig
  via `--zertifikat-pruefen`; returkoder skiljer på överensstämmelse,
  hanteringsfel och ogiltigt belägg.
  Kontrollprovet jämför dessutom den inbäddade Maskuro-ID:n med
  certifikatet; en fritt inmatad främmande ID märks därigenom även vid
  ett osignerat belägg.
  Vid giltig signatur visar kontrollfyndet dessutom den av
  administrationen aktiverade redigeraren med operativsystemskonto,
  teknisk konto-ID och plattform. Obekräftade uppgifter ur osignerade
  eller ogiltiga belägg matas inte ut.

- Ett nytt tyskt dokumentlaboratorium skapar 160 helt syntetiska TXT-,
  HTML-, PDF- och DOCX-handlingar från tio områden och fyra
  strukturvarianter. Manifestet skiljer nu uttryckligen mellan uppgifter
  som ska försvinna och fackord respektive sakidentifierare som ska
  bevaras; dokumentfamilj, mutation och offentlig strukturkälla är
  spårbart dokumenterade.

- Det tyska dokumentlaboratoriet utökades till 280 filer, sju
  strukturformer, 1 540 börvärden och 1 036 bevarandeankare. Nytt
  kontrollerade blir numrerade formulär, hakparenteserade
  PDF-/maskfält och tekniska `=>`-tilldelningar. Den utökade fullnivån
  når i TXT, HTML, PDF och DOCX vardera 100 procent vid noll falska
  larm. Hakparenteserade datum- och identifieringsnummerfält,
  pilavgränsare och uttryckligen betecknade förband identifieras nu
  strukturellt.

- En andra laborutökning höjer beståndet till 400 dokument, tio
  strukturformer, 2 200 börvärden och 1 480 bevarandeankare.
  JSON-liknande nyckelvärden, YAML-listor och versala formulärfält når
  tillsammans med det tidigare beståndet 100 procent vid noll falska
  larm. Citerade födelsedatum och identifieringsnummer samt uttryckligen
  betecknade roller som försäkrade, sökande, deklarationsskyldiga och
  representationsbefogade personer identifieras nu även i dessa
  exportformer.

- Ett separat OCR-läge i det tyska dokumentlaboratoriet skapar dessutom
  200 rena bildskanningar från alla 40 familjer. Rena, kontrastfattiga,
  lågupplösta, JPEG-artefaktbehäftade och 90 grader roterade sidor
  mäts efter med exakta pixelrutor, utan att ändra det jämförbara
  1 600-filers textgrundnivån. Manifestet skiljer valbara datum-,
  penning- och medicinkännetecken från grundprofilen och känner till
  belagda OCR-tolkningar utan att räkna dem som extra börställen.
  Mätningen redovisas per mutation och dokumentfamilj. Snäva fältgränser
  förhindrar bland annat att „Az" i ortnamnet „Graz" maskerar ett
  efterföljande datum som diarienummer; den aktuella grundmatrisen körs
  med noll falska larm och noll avbrott.

- Fem ytterligare tyska dokumentfamiljer för faktura/följesedel,
  bank/kredit, hyra/fastighetsförvaltning, skola/högskola och
  logistik/tull utökar laboratoriet till 600 filer med 3 520 börvärden
  och 2 360 bevarandeankare. En snäv PDF-tabellväg använder det
  uttryckliga huvudet `Feld Angabe`, när textskiktet förlorar
  cellavgränsare; ett nytt `--familien`-val skyndar på delmätningar. De
  200 nya filerna når 1 320/1 320 vid noll falska larm och noll
  avbrott.

- Försäkring/skada, arbete/lön, medicin/labb, fordon/verkstad och
  teknik/underhåll utökar det tyska dokumentlaboratoriet till 800 filer
  med 4 960 börvärden och 3 200 bevarandeankare. Snävt betecknade
  försäkrings-, patient-, provnings- och fordonsidentifierare samt nya
  roll-, adress- och organisationsfält identifieras. Den nya delmatrisen
  och den fullständiga matrisen når 100 procent vid noll falska larm
  och noll avbrott i TXT, HTML, PDF och DOCX.

- Bygg/upphandling, energi/miljö, förening/samfund, kommunikation/kalender
  och hotell/evenemang höjer det tyska dokumentlaboratoriet till 1 200
  filer med 7 920 börvärden och 4 800 bevarandeankare. Nya roll-,
  företags-, adress-, register-, upphandlings-, boknings- och
  användarkontofält identifieras även i alla exportformer.
  Mätarnummer bevaras som sakidentifierare. Del- och fullmatris når 100
  procent vid noll falska larm och noll avbrott.

- Gastronomi/leveranstjänst, apotek/recept, begravning/kyrkogård,
  idrott/medlemskap och fastigheter/mäklare utökar det tyska
  dokumentlaboratoriet till 1 400 filer med 9 360 börvärden och 5 640
  bevarandeankare. Nya personroller, adressfält och sökuppdragsnummer
  identifieras. Betecknade företagsnamn med bolagsform förblir
  fullständigt skyddade även över en automatisk radbrytning;
  åldersklasser och fackhuvuden ersätts inte längre felaktigt. Del- och
  fullmatris når 100 procent vid noll falska larm och noll avbrott.

- Tandvård, körskola, brandkår/insats, energigemenskap och paketresa
  utökar det tyska dokumentlaboratoriet till 1 600 filer med 10 840
  börvärden och 6 440 bevarandeankare. Nya roller, adressfält samt
  behandlings-, utbildnings-, insats-, energi- och
  resekontraktsidentifierare identifieras strukturellt. Den nya
  200-filers delmatrisen når 1 480/1 480; den fullständiga matrisen når
  10 840/10 840. Båda förblir vid noll falska larm och noll avbrott.

- Fullmätningen av dokumentlaboratoriet sänkte genom snäva officiella
  sakformer och strukturregler de onödiga ersättningarna från 68 till 0,
  de uttryckligen uppmätta bevarandeöverträdelserna från 23 till 0 och
  avbrotten från 3 till 0. Fyndkvoten steg samtidigt från 91,1 till
  100,0 procent; TXT, HTML, PDF och DOCX når vardera 100 procent.
  Allmänna tabellhuvuden som `Feld` bromsas bara i den belagda
  sekvensen `Feld`/`Angabe`; ett likalydande efternamn förblir
  skyddat. Rättsliga diarienummer med slutbokstav, likhetstecken-fält,
  `Geburtsdatum des Kindes` och flera betecknade enskilda namn på samma
  rad identifieras fullständigt. Word-tabeller och förradsfält använder
  sitt fälthuvud som tillfällig igenkänningskontext; betecknade
  PDF-adresser förblir fullständigt skyddade även vid en satsbetingad
  radbrytning.

- Tyska personkännetecken-, yrkes- och medicinfält fungerar nu även med
  Windows-radbrytningar. Enskilda bokstavsangivelser av kön som
  `Geschlecht`/`w` skyddas i förradsformen. Sakliga `Artikel-PZN`-fält
  utlöser däremot varken ett läkemedelsnyckel- eller ett personfynd;
  riktiga PZN-, ICD- och ATC-uppgifter identifieras fortfarande.

- Tyska formulär- och nummerfält är exaktare: „DW." fungerar nu även
  framför en mjuk radbrytning, uttryckligen betecknade namn tas bort
  även vid gemener, och rent numeriska diarienummer tilldelas sin rätta
  identifieringsnummertyp. Omvänt gäller ett av en slump Luhn-giltigt
  faktura-, belägg- eller artikelnummer inte längre som kreditkort.
  Syntetiska HTML- och PDF-utdataprov bekräftar borttagning och
  bevarande i det färdiga dokumentet.
  Identifieringsnummer och användarnamn identifieras dessutom när deras
  beteckning står i den omedelbart föregående tabell- eller
  formulärraden; sakliga belägnummer förblir synliga även i denna form.

- Lösenord identifieras nu även bakom ett fristående fälthuvud på
  föregående rad. Avslutande specialtecken som `!` eller `#` hör
  därvid helt till det skyddade värdet. Produkt- och artikel-PIN
  maskeras omvänt inte längre som kort-PIN; uttryckliga `PIN`- och
  `Karten-PIN`-fält förblir skyddade.

- Gement skrivna formulärvärden ges nu vid entydiga tyska adress- och
  `PLZ/Ort`-fält ut som adress respektive postnummer med ort i stället
  för bara som allmän ort. Likaså förblir gement skrivna företagsvärden
  som „beispiel service" bakom ett företagsfält fullständigt skyddade,
  utan att slutordet skärs av som ett påstått nästa fälthuvud.

- Hjälp, FAQ, integritetstext och webbplats förklarar nu tillsammans
  ursprungsbeviset: neutral Maskuro-ID i dokumentet, valfri koppling
  till det riktiga operativsystemskontot bara i den lokala
  kontrollprotokollet, användarbyte via Windows/macOS/Linux samt
  SHA-256:s och signaturens bevisvärde.

- Bildbaserade tekniska prestationsförteckningar rensas mer
  återhållsamt. Entydiga sakord som „Abbruchhämmern",
  „Deckungsrücklass", „Positionsnummern", „Einbauplatine" eller
  „Terminsituation" samt mitt i ordet avstavade OCR-former gäller inte
  längre som person eller ort. En verklig kommunkontorsoffert sjönk
  därigenom från 140 till 90 entydiga ersättningar, utan att skapa nya
  träffar; namn som Schneider, Lang, Bauer och Hahn förblir uttryckligen
  skyddade.

- Fler falska larm ur verkliga offerter är åtgärdade: „Digital signiert"
  innehåller inte längre en påstådd person, en BIC identifieras även
  utan kolon bakom sin beteckning, `15000 Alternativ` gäller inte som
  postnummer med ort, och EU-citatet „(VO (EG) 715/2007" skapar ingen
  organisation. En solcellsoffert sjönk därigenom från 26 till 16
  ersättningsförekomster; riktiga namn, orter och kontodata bevarades.

- I personalöversikter ersätts förkortningen „Stv." (ställföreträdare)
  och en enskilt avskild rubrik „FACILITY" för ett verksamhetsområde
  inte längre som personnamn. Den verkliga 13-sidiga motkontrollen
  sjönk från 878 till 875 ersättningar; namn, anknytningar och
  företagsbeteckningen förblev skyddade.

- Rensade PDF-, OpenDocument- och kontorsfiler får en neutral
  `MASKURO-…`-identifierare i sina dokumentegenskaper. Kontrollrapport
  och signerat kontrollprotokoll för samma identifierare samt
  SHA-256-värden för källa och resultat; redaktionscertifikatet
  övertar identifieraren ur den färdiga filen. Ett användarnamn
  tillkommer fortfarande bara om administrationen uttryckligen slår på
  det befintliga användarfältet.

- Huvudfönster och inställningar har en lugnare struktur: Spara,
  Kopiera, Detaljer, Nyckeltal och att ta bort en igenkänningsprofil
  visas först när respektive handling är möjlig. Tekniska
  OCR-språkförkortningar och långa exempel står vid behov i
  hänvisningstexten i stället för varaktigt i arbetsytan.
  Igenkänningssidan anpassar sig bättre till smalare fönster, utan
  avskurna förklaringar eller vågräta rullningslister; varningen om
  klartext i ersättningslistan förblir synlig därvid.

- Igenkänningen omfattar fler tyska och internationella kontaktfall:
  telefonnummer kontrolleras nu för alla valbara landregioner, ungerska
  och kroatiska avtalsroller fångar även yrkeslika efternamn
  fullständigt, och numrerade reservdels-/materiallistor utlöser inte
  längre ett falskt personlarm på grund av „Mutter / Flach".
  Personfält med uppenbart sifferhaltigt sakvärde tas inte längre upp
  som namn; den maskinläsbara passzonen (MRZ) kan dessutom slås av och
  på gemensamt via gruppen „Identifierare".

- Företag utan bolagsform särskiljs bättre från personer bakom
  tvetydiga arbetsgivarfält: namn som „Huber Handel", „Müller
  Logistik" eller „Kowalski Handel" fångas fullständigt som företag,
  medan „Arbeitgeber: Bauer Anna" fortsätter vara ett personnamn. Det
  automatiska landvalet tar vid franska dokument fortsatt hänsyn till
  hela det franska språkområdet inklusive Luxemburg.

- Identifierade underskrifter och personuppgiftstext inuti en bild
  övertäcktes tidigare alltid med en svart rektangel – även när en
  annan färg eller ett mönster som „Regnbåge" var inställt för
  maskeringar. Dessa bildområden övertar nu likaså den valda
  maskeringsutformningen; den heltäckande ytan skrivs fortfarande
  direkt in i bildpunkterna.

- Den engelska igenkänningen mättes efter mot elva manuellt översatta
  verkliga dokument och förbättrades riktat: inventeringsstatus,
  tekniska offert- och webbshopfält samt roller i
  personalförteckningar förblir synliga, „CV" läses inte längre som
  bolagsform i mallmeningen, citerade teckensnitt bevaras, och namn i
  lodräta CV-huvuden, flersidiga personallistor, bakom „Account
  manager" samt siffer-inledda företagsnamn identifieras fullständigt.
  Österrikiska organisationsnummer fungerar nu även bakom en engelsk
  beteckning; kortformen „Customer:", EAR-registreringsnummer och
  arbetsgivarnummer bär sitt värde. Måttkedjor, kabeltyper,
  EU-rättshänvisningar, offertens giltighetsdatum, uppfyllelseorter,
  domstolsorter, registerdomstolar, skatteförkortningen „NoVA",
  tekniska nummer i däcketiketter samt normhänvisningar som „OVE R6-2"
  och „AStV" skapar inte längre ett falskt larm. Ett giltigt betecknat
  IBAN-nummer slutar rent framför registreringsfältet eller rubriken på
  följande rad; adresser med industriområdestillägg identifieras
  fullständigt även ur PDF-textströmmar med Windows-radbrytningar.
  Engelska företagsinledningar och strukturerade sparbanksnamn
  avgränsas fullständigt. Ursprungsdokumentets land bevaras vid
  språkversionerna för postnummer och landsspecifika identifierare.

- I mottagar- och meddelandehuvudrader kunde språkmodellen binda ihop de
  första två namnen i en kommalista till ett enda fynd („Bcc: Huber,
  Mayer"). Båda namnen identifieras och ersätts nu enskilt och förs i
  rapporten – likaså bakom „Sent:", „Reply:" och „Fwd:".

- Den maskinläsbara zonen i ett pass eller ID-kort (MRZ) saknades i
  gruppkontrollen „Vad som söks". Den hör nu till „Identifierare" och
  kan slås av och på tillsammans med denna grupp.

- Den som väljer mallen „Regnbåge" för ersättningstexter får nu även
  maskerade ställen i samma utseende; tidigare förblev de överraskande
  klassiskt svarta. Maskeringsytorna går därefter fortfarande att ställa
  om oberoende till en annan mall.

- Sidfacket i efterbearbetningseditorn kunde förbli tomt efter
  återställning av en sparad fönsteruppdelning, tills dess bredd
  ändrades för hand. Miniatyrerna ordnas nu om efter den synliga
  fönsteruppbyggnaden och står genast mitt i facket.

- De färgade kontrollmarkeringarna runt ersättningstexter i PDF-filer
  förblev knappt synliga beroende på kategori- och trafikljusfärg. En
  ljus underkontur skiljer nu tillförlitligt kontrollramen från den
  färgade platshållaren och från sidbakgrunden.

- Den som maskerar en rad i efterbearbetningseditorn vars dokument är
  satt med tätt radavstånd (typiskt för offerter och
  prestationsförteckningar) fick ett streck som stack in i överlängderna
  på raden under – den blev därefter bara halvt läsbar. Strecket
  slutar nu vid den verkligt ritade texten på grannraden; den maskerade
  raden själv förblir tillsammans med sina underlängder fullständigt
  täckt.

- Övningsdokumentet („Hjälp → Öppna övningsdokument", även i rundturen)
  visar nu varje igenkänningstyp: till det hittade brevet tillkommer en
  bild med igenkännbart ansikte, en skriven underskrift, yrke och
  avdelning, diagnos och läkemedel – bredvid företagsnamn, belopp och
  datum som redan fanns. Vad förvalet medvetet lämnar kvar förklarar
  bladet själv, tillsammans med brytaren som tar bort det; ansiktet på
  bilden pixleras fabriksmässigt.

- Penningbelopp i det vanliga tyska skrivsättet med symbolen bakom
  talet („1.240,00 €") hittades aldrig av brytaren „Ta bort
  penningbelopp också" – „1.240,00 EUR" och „€ 1.240,00" alltid.
  Nu identifieras alla tre skrivsätt.

- Underskriftssökningen fungerar nu även på fristående bildfiler: den
  som rensar en skanning som JPG eller PNG får handskrivna
  underskrifter i den maskerade – samma igenkänning, samma meddelande i
  rapporten som vid PDF. Bilder inbäddade i kontorsfiler genomsöks
  fortfarande inte, eftersom igenkänningen där mätt arbetar
  otillförlitligt; bocken heter därför nu „PDF och bildfiler: maskera
  handskrivna underskrifter".

- Ett maskeringsstreck kunde vid tätt radavstånd synligt sticka in i
  överlängderna på raden under och göra den halvt oläslig –
  strecköjden kom från teckensnittsmåtten, inte från vad som verkligen
  står på papperet. Strecket slutar nu vid den faktiskt ritade tinta
  på grannraden, i efterbearbetningseditorn liksom vid den automatiska
  rensningen. Den egna raden tillsammans med underlängder förblir
  därvid alltid helt täckt; överlappar raderna verkligen, förblir
  strecket hellre kvar på grannraden än att frige något.

- I en personalförteckning med roll under namnet drogs en kvinnlig
  ledningsbeteckning („Anna Berger" med „Montageleiterin" under) in i
  namnersättningen – den manliga formen bredvid förblev korrekt kvar.
  De kvinnliga „…leiterin"-formerna (Montage-, Team-, Projekt-, Bau-,
  Abteilungs-, Betriebs-, Gruppen-, Amtsleiterin) behandlas nu som sina
  manliga motsvarigheter som funktionsbeteckning; Filial-, Personal-
  och Vertriebsleitung är nya i båda formerna.

- Den valbara yrkesigenkänningen hittade inte kvinnliga ledningsroller
  som „Projektleiterin", „Teamleiterin" eller „Abteilungsleiterin", men
  väl deras manliga former. Båda formerna räknas nu lika.

- I förhandsvisningsfönstret klibbade flerförekomstangivelsen direkt vid
  termen på Mac („Anna Musterfrau2ק i stället för „Anna Musterfrau 2ק).
  Mellanrummet står där igen.

- Jämförelseluppen har en ny knapp bredvid zoomreglaget: den lägger den
  med ett tryck i full bredd över resultatet – halv höjd vardera, och
  originalet i samma skala som dokumentet (luppzoomen hoppar därvid
  till 100 %). Ett andra tryck dockar den åter liten i vänsterkolumnen
  och återställer den tidigare luppzoomen. Ringen bredvid återställer
  nu bara zoomen – dess hänvisningstext påstod tidigare felaktigt att
  den även dockade tillbaka fönstret.

- I efterbearbetningseditorns verktygsfält syns nu åter på det valda
  verktyget att det är valt: knappen för det aktiva verktyget bär en
  fylld yta med blå kant – likaså varje annan påslagen omkopplingsknapp
  i fältet (till exempel jämförelselupp eller inlärningsläge).
  Markeringen hade försvunnit med den egna knapputformningen från den
  29 augusti.

- Positionsnummer i en prestationsförteckning („2.3.3.3, 2.3.3.4,
  2.3.3.5" under varandra) togs för IP-adresser och togs bort ur
  resultatet; tredelade nummer med årtalslikt sista led („2.3.19,
  2.3.20") föll som kalenderdatum. En stigande nummerföljd i radbörjan
  gäller nu som det den är – en positionslista; riktiga adresser
  (nätverkstabeller med teknisk ordomgivning, tal över 99) och riktiga
  datumangivelser identifieras fortfarande.

- Efternamn som „Müller", „Fischer", „Bauer", „Koch", „Wagner",
  „Schneider", „Weber", „Jäger", „Schmied", „Becker", „Schuster",
  „Schäfer" eller „Meister" förblev i klartext i listor av formen
  „efternamn, förnamn" (t.ex. „Teilnehmer: Müller, Peter; Nowak,
  Anna"), eftersom de samtidigt är vanliga yrkesbeteckningar. De
  identifieras nu tillförlitligt.

- Vid maskering av ett PDF-dokument kunde strecket i smala tabellceller
  ta med sig hela cellen: ur träffen „D-LINK" i en
  prestationsförteckning togs den kompletta produktbeskrivningen bredvid
  bort, trots att förhandsvisningen bara nämnt träffen. Strecket täcker
  fortfarande hela adressblocksrader och fältbeteckningar, men sväljer
  högst så mycket obesläktat som det täcker skyddsvärt – beskrivningen
  bredvid träffen blir nu kvar.

- Efter „Återställ vy" i efterbearbetningseditorn förblev sidfacket
  tomt – sidminiatyrerna syntes först igen efter att fönstret stängts
  och öppnats på nytt. Nu står de där direkt även efter återställningen,
  mittjusterade som förut.

- Efterbearbetningseditorn har ett fjärde verktyg: **Ta bort** tar bort
  texten under ramen utan ersättning – utan streck (maskera) och utan
  platshållare (ersätta); luckan förblir synligt tom. Det arbetar
  ordexakt, ligger en bild under, städas dess grund vit, och „Hämta
  original" ångrar även en ersättningsfri borttagning. Egen
  fältsymbol och hårkorsmärke (kryss), egen kortkommandotangent på
  alla 18 språk (tyska F som i entFernen).

- I PDF-sökfältet står „Mapp …" nu till höger om sökalternativen. Sedan
  det utöver maskering även finns möjlighet att ersätta träffar, fick
  fem knappar inte längre plats bredvid varandra vid vanlig
  fönsterbredd – den första klämdes ihop och dess text skars av.

- „Återställ alla inställningar" återställer nu även bocken „Ersätt
  rött/grönt med andra färger" och antecknar den liksom varje annan
  som „ändrad" om den avviker från leveransen.

- Ersättningstexter i PDF-filer verkar nu mer jämnt: där den fulla
  platshållaren tydligt skulle bli mindre än sin rad (till exempel
  „[BEG16]" pressad in i ett kort ord som „Das"), står i stället en
  kortform i radstorlek („[B16]") – väl läsbar i stället för
  mikroskopisk, och numret för återhämtning bär båda skrivformerna.
  Mikroskopisk blir en platshållare bara när inte ens den kortaste
  formen får plats – det förblir bättre än ett streck utan någon
  upplysning.

- En flerfärgad satt ersättningstext (toning eller regnbåge) i ett PDF
  förblev bara hel fram till nästa ingrepp: varje ytterligare ersättning
  eller maskering på samma sida kunde skjuta ihop redan satta
  platshållare till en oläslig, hoppressad teckenhög – den som i
  editorn ersatte ord för ord såg i stället för „[BEG17]" bara
  bokstäver tryckta ovanpå varandra. En gång satta platshållare förblir
  nu som de sattes.

- Brytaren för varaktiga undantag i förhandsvisningen heter nu „Ta
  aldrig bort" – som listan den för in i; tidigare stod där „aldrig
  igen". Träffraden bredvid är mer uppstädad: infosymbolen „ⓘ" är
  större och lättare att träffa, och kryssruta, ersättningsmärke och
  knapp har en gemensam höjd. Meningen runt ett fynd använder nu
  verkligen sin utlovade bredd – den tidigare breddangivelsen hade
  tyst förkastats av visningen, och utsnittet bröt vidare som en smal
  remsa.

- I editorn säger muspekaren nu vilket verktyg som verkar: ett hårkors
  för att sikta, bredvid ett litet tecken – streck för maskera,
  bytespilar för ersätta, ångra-båge för återställa, pixelraster för
  pixlera. De tidigare handsymbolerna utgick; en hand betyder annars
  överallt „greppa och skjuta". Den har nu en passande uppgift: över
  ett rödmarkerat ord eller streck blir pekaren en pekande hand – ett
  klick räcker där.

- „Maximal igenkänning (KI)" erbjuder inte längre en nedladdningsbar,
  lokal språkmodell – nivån räknar nu uteslutande via en under „Anslut
  egen KI" inställd egen KI. Den som redan anslutit en egen server
  märker ingen skillnad.

- Den guidade rundturen i förhandsvisningen förklarar nu även
  infosymbolen „ⓘ" som visar meningen runt ett fynd. Och denna mening
  själv är mer läsbar: en steg större text, mer radavstånd, fast
  bredd i stället för en smal, tätt packad radbrytning.
- Även „Kontrollera fil", „Igenkänningsregler och egna termer", „Rensa
  text" och „Rensa bild" har nu en egen rundtur – via en ny knapp
  „Rundtur genom fönstret", eftersom dessa fyra fönster inte har någon
  egen menyrad.
- Namn under nio ukrainska avtalsrollbeteckningar förblev otillräckligt
  identifierade vid ett homografiskt efternamn, om beteckningen stod
  ensam på sin rad: „Покупець"/„Продавець" (köpare/säljare),
  „Поручитель"/„Боржник" (borgensman/huvudgäldenär), „Свідок" (vittne),
  „Орендодавець"/„Орендар" (hyresvärd/hyresgäst) och
  „Спадкодавець"/„Спадкоємець" (arvlåtare/arvinge). Namnen identifieras
  nu fullständigt.

- Kommentaren till ett namngivet område i en Excel-arbetsbok
  (namnhanterare, fältet „Kommentar") förde ett däri inmatat namn
  oförändrat vidare. Det rensas nu likadant som arbetsbokens övriga
  innehåll.

- Namn under sju ungerska avtalsrollbeteckningar förblev helt
  oupptäckta vid ett homografiskt efternamn: „Bérbeadó"/„Bérlő"
  (hyresvärd/hyresgäst), „Vevő"/„Eladó" (köpare/säljare),
  „Kezes"/„Főadós" (borgensman/huvudgäldenär) och „Tanú" (vittne).
  Namnen identifieras nu fullständigt.

- Namn under den tjeckiska köparbeteckningen „Kupující" förblev helt
  oupptäckta vid ett homografiskt efternamn. Namnet identifieras nu
  fullständigt.

- Namn under den ryska förmyndarbeteckningen „Опекун" förblev helt
  oupptäckta vid ett homografiskt efternamn. Namnet identifieras nu
  fullständigt.

- Namn under sex ytterligare kroatiska beteckningar förblev
  oupptäckta: „Jamac" (borgensman), „Glavni dužnik"/„Dužnik"
  (huvudgäldenär/gäldenär), „Ostavitelj" (arvlåtare), „Nasljednik"
  (arvinge) och „Vjerovnik" (fordringsägare). Namnen identifieras nu
  fullständigt.

- En sparad HTML-sida med en inbäddad undersida i `src`-attributet hos
  ett `<embed>` (i stället för `data` vid `<object>`) förde
  personuppgifter i den oförändrat vidare. De rensas nu likadant som
  vid `<object>`.

- Namn under fem danska avtalsrollbeteckningar förblev otillräckligt
  identifierade vid ett homografiskt efternamn, om beteckningen stod
  med kolon framför namnet: „Arvelader"/„Arving" (arvlåtare/arvinge),
  „Befuldmægtiget"/„Fuldmagtsgiver" (fullmaktstagare/-givare) och
  „Værge" (förmyndare). Namnen identifieras nu fullständigt; de
  motsvarande norska beteckningarna har som säkerhetsåtgärd också
  kompletterats.

- Platshållare i Word- och PowerPoint-filer bär nu samma färg som i det
  valda utseendet (enfärgad, toning, regnbåge eller per kategori) –
  tidigare förblev de där i vanlig textfärg, även när PDF-resultat
  länge var färgade.

- „Kopiera som text" och „Kopiera som Markdown" lägger resultatets
  klartext direkt i urklipp – för inklistring i chatt, mejl eller ett
  annat program, utan att först öppna filen.

- Namn under fem ytterligare slovenska beteckningar förblev oupptäckta:
  „Toženec" (svarande), „Tožnik" (kärande), „Zastavitelj" (pantsättare),
  „Zastavni upnik" (panthavare) och „Darovalec" (givare). Namnen
  identifieras nu fullständigt.

- Författarnamnet till en spårad tabellcellsändring (infogad, raderad
  eller sammanslagen cell i Word) förblev kvar i filen, även när samma
  namn som kommentarförfattare länge var borttaget. Det tas nu bort
  likaså.

- Namn under nio ytterligare slovenska beteckningar förblev oupptäckta:
  „Najemodajalec"/„Najemnik" (hyresvärd/hyresgäst),
  „Zapustnik"/„Dedič" (arvlåtare/arvinge), „Upnik"/„Dolžnik"
  (fordringsägare/gäldenär), „Glavni dolžnik" (huvudgäldenär) och
  „Skrbnik" (förmyndare/god man). Namnen identifieras nu fullständigt.

- Namn under fem slovenska beteckningar förblev oupptäckta: „Izvedenec"
  (sakkunnig), „Kupec" (köpare), „Prodajalec" (säljare), „Naročnik"
  (uppdragsgivare) och „Izvajalec" (uppdragstagare). Namnen
  identifieras nu fullständigt.

- Namn under fem ytterligare litauiska beteckningar förblev oupptäckta:
  „Užsakovas" (uppdragsgivare), „Vykdytojas" (uppdragstagare),
  „Vežėjas" (fraktförare), „Siuntėjas" (avsändare) och „Arbitras"
  (skiljedomare). Namnen identifieras nu fullständigt.

- Namn under sex ytterligare litauiska beteckningar förblev oupptäckta:
  „Įgaliotinis" (fullmaktstagare), „Įgaliotojas" (fullmaktsgivare),
  „Naudos gavėjas" (förmånstagare, försäkring), „Trečiasis asmuo"
  (biintervenient/tredje part i civilprocess), „Ankstesnis nuomininkas"
  (tidigare hyresgäst) och „Naujasis nuomininkas" (ny hyresgäst).
  Namnen identifieras nu fullständigt.

- Ett bokmärke i ODT-dokument (`text:bookmark`) bär sitt namn fritt
  tilldelat, ofta uppkallat efter stället det pekar på (t.ex.
  „Herr_Mueller_Unterschrift") – osynligt för läsaren, men ordagrant i
  filen. Namnet rensas nu med.

- Namn under åtta ytterligare litauiska beteckningar förblev oupptäckta:
  „Pareiškėjas" (sökande), „Suinteresuotas asmuo" (motpart i
  icke-tvistigt förfarande), „Ekspertas" (sakkunnig/utredare),
  „Bankroto administratorius" (konkursförvaltare), „Valdybos narys"
  (styrelseledamot), „Direktorius" (verkställande direktör),
  „Palikėjas" (arvlåtare) och „Įpėdinis" (arvinge). Namnen identifieras
  nu fullständigt.

- Namn under sju ytterligare litauiska beteckningar förblev oupptäckta:
  „Liudytojas" (vittne), „Vertėjas" (tolk/översättare), „Notaras"
  (notarie), „Dovanotojas" (givare), „Apdovanotasis" (mottagare),
  „Pirkėjas" (köpare) och „Pardavėjas" (säljare). Namnen identifieras
  nu fullständigt.

- Namn under sex ytterligare litauiska beteckningar förblev oupptäckta:
  „Globėjas" (förmyndare/god man), „Palikimo administratorius"
  (boutredningsman), „Laiduotojas" (borgensman), „Pagrindinis
  skolininkas" (huvudgäldenär), „Nuomotojas" (hyresvärd) och
  „Nuomininkas" (hyresgäst). Namnen identifieras nu fullständigt.

- Ett namn under den litauiska beteckningen „Ieškovas"/„Atsakovas"
  (kärande/svarande som processpart) förblev oupptäckt, oavsett om
  efternamnet samtidigt var ett vanligt ord (t.ex. „Vilkas" = varg)
  eller inte. Namnet identifieras nu fullständigt.

- En post i personregistret i ODT-dokument (bokmärke för
  sakregistret) bar namnet en andra gång i sin egen sorteringsnyckel –
  osynligt i löptexten, men ordagrant i det senare skapade registret.
  Nyckeln rensas nu med.

- Bildnamnet och avsnittsnamnet i en PowerPoint-presentation (synligt i
  urvalsområdet respektive bildsorteringen) förblev orensade, eftersom
  båda hänger som attribut på ett element som inte är bildtext. Båda
  identifieras nu.

- Ett litauiskt bindestrecks-dubbelnamn som „Petraitis-Kazlauskas"
  förlorade sin andra hälft så snart någon löptext stod framför (bara
  vid textens början förblev det fullständigt): efternamnet
  identifieras nu även då helt.

- Ett namn under beteckningen „Cesionar" (kroatiska, cessionar vid
  fordringsöverlåtelse) skapade ett falskt larm, eftersom fältbeteckningen
  själv felaktigt lästes som person. Ett namn under den ryska
  beteckningen „Цессионарий" (likaså cessionar) förblev däremot helt
  oupptäckt. Båda fallen är nu åtgärdade.

- Ett namn under beteckningen „Zedent"/„Zessionar" (tyska,
  fordringsöverlåtelse) förblev helt oupptäckt, om efternamnet
  samtidigt var ett vanligt ord (t.ex. „Bauer"). Namnet identifieras
  nu fullständigt.

- Ett namn under beteckningen „Darczyńca"/„Obdarowany" (polska,
  givare/mottagare i gåvoavtal) förblev oupptäckt, om efternamnet
  samtidigt var ett vanligt ord (t.ex. „Wilk" = varg). Likaså hängde
  den rumänska beteckningen „Donatar" (mottagare) kvar vid ett vanligt
  efternamn som en påstådd namndel. Båda fallen är nu åtgärdade.

- Ett namn under beteckningen „Wierzyciel"/„Dłużnik" (polska,
  utmätningsborgenär/utmätningsgäldenär respektive allmän
  fordringsägare/gäldenär) förblev oupptäckt, om efternamnet samtidigt
  var ett vanligt ord (t.ex. „Wilk" = varg). Namnet identifieras nu
  fullständigt.

- Ett namn under beteckningen „Poręczyciel"/„Dłużnik główny" (polska,
  borgensman/huvudgäldenär i borgensavtal) förblev oupptäckt, om
  efternamnet samtidigt var ett vanligt ord (t.ex. „Wilk" = varg).
  Namnet identifieras nu fullständigt.

- Ett namn under beteckningen „Ubezpieczony"/„Ubezpieczający" (polska,
  försäkrad/försäkringstagare i försäkringsbrev) förblev delvis eller
  helt oupptäckt, om efternamnet samtidigt var ett vanligt ord (t.ex.
  „Wilk" = varg). Likaså ett namn under
  „Osiguranik"/„Osiguravatelj" (kroatiska, samma roller), där
  försvann det tillsammans med förnamnet helt (t.ex. „Golub" = duva).
  Båda namnen identifieras nu fullständigt.

- Ett namn under beteckningen „Pełnomocnik"/„Mocodawca" (polska,
  fullmaktstagare/fullmaktsgivare i fullmaktshandlingar) förblev
  oupptäckt, om efternamnet samtidigt var ett vanligt ord (t.ex.
  „Wilk" = varg). Likaså ett namn under
  „Opunomoćenik"/„Opunomoćitelj" (kroatiska, samma roller), där
  försvann det till och med helt tillsammans med förnamnet. Båda namnen
  identifieras nu fullständigt.

- Ett namn under beteckningen „Pozwany" (polska, svarande som
  processpart) förblev oupptäckt, om efternamnet samtidigt var ett
  vanligt ord (t.ex. „Wilk" = varg). Namnet identifieras nu
  fullständigt.

- Ett namn under beteckningen „Najmoprimac"/„Najmodavac" (kroatiska,
  hyresgäst/hyresvärd i hyresavtal) förblev oupptäckt, om efternamnet
  samtidigt var ett vanligt ord (t.ex. „Kovač" = smed). Namnet
  identifieras nu fullständigt.

- Ett namn under beteckningen „Pracodawca"/„Pracownik" (polska,
  arbetsgivare/arbetstagare som avtalspart i anställningsavtal) förblev
  delvis oupptäckt, om efternamnet samtidigt var ett vanligt ord (t.ex.
  „Krawiec" = skräddare). Namnet identifieras nu fullständigt.

- Ungern hade i landkatalogen bara personidentifierarna och
  momsregistreringsnumret: handelsregisternumret (Cégjegyzékszám)
  identifieras nu, om fältordet „Cégjegyzékszám" eller förkortningen
  „Cg." står omedelbart framför – numret själv bär ingen kontrollsiffra.

- Estland hade i landkatalogen bara Isikukood: Käibemaksukohustuslase
  number (momsregistreringsnummer på varje estnisk faktura)
  identifieras nu med kontrollsiffra.

- Lettland hade i landkatalogen bara personkoden: PVN reģistrācijas
  numurs för juridiska personer (företagsidentifierare på varje lettisk
  faktura) identifieras nu med kontrollsiffra.

- Ett e-postmeddelande med krypterat innehåll (S/MIME- eller
  PGP/MIME-omslag, `multipart/encrypted`) matades ut som skenbart
  fullständigt kontrollerat utan någon varning, trots att dess
  egentliga innehåll var krypterat och därmed förblev okontrollerat.
  Sådana mejl påpekar nu detta som en okontrollerad bilaga.

- Malta saknades i landkatalogen: det maltesiska
  momsregistreringsnumret (VAT number) identifieras nu.

- Luxemburg saknades i landkatalogen: det luxemburgska
  momsregistreringsnumret (n° TVA) identifieras nu.

- Ett i satsbörjan placerat bulgariskt „Изчакайте" ("Vänta!")
  rapporterades som en ortsuppgift – samma modellgräns som tidigare vid
  ungerska, polska, tjeckiska och andra uppmaningsformer utan egen
  språkmodell. Det falska larmet uteblir nu.

- Ett namn under beteckningen „Zleceniodawca", „Zleceniobiorca"
  (polska), „Prestator" (rumänska), „Naručitelj" eller „Izvođač"
  (kroatiska) förblev delvis eller helt oupptäckt, om efternamnet
  samtidigt var ett vanligt ord (t.ex. „Wilk", „Vuk" = varg, „Vulpe" =
  räv, „Sokol" = falk). Namnet identifieras nu fullständigt.

- Ett namn under beteckningen „Nadawca" (polska), „Afsender" (danska)
  eller „Pošiljatelj" (slovenska) förblev delvis eller helt oupptäckt,
  om efternamnet samtidigt var ett vanligt ord (t.ex. „Sowa" = uggla,
  „Bager" = bagare, „Volk" = varg). Namnet identifieras nu
  fullständigt.

- Ett namn under beteckningen „Gavėjas" (litauiska) eller „Prejemnik"
  (slovenska) förblev delvis eller helt oupptäckt, om efternamnet
  samtidigt var ett vanligt ord (t.ex. „Vilkas" = varg). Liksom redan
  vid „Primatelj" (kroatiska) och „Modtager" (danska) identifieras
  namnet nu fullständigt.

- En rundskrivelses huvudrad som „To All Staff" eller „To All
  Employees" identifierades felaktigt som personnamn och togs bort.
  Det förekommer inte längre.

- Ett namn under beteckningen „Primatelj" (kroatiska) eller „Modtager"
  (danska) förblev delvis oupptäckt, om efternamnet samtidigt var ett
  vanligt ord (t.ex. „Golub" = duva, „Bager" = bagare). Liksom redan
  vid „Odbiorca" (polska) och „Destinatar" (rumänska) identifieras
  namnet nu fullständigt.

- Ett fullständigt namn i underskriftsraden på ett danskt, norskt eller
  grekiskt dokument förblev delvis oupptäckt, om beteckningen
  „Underskrift" eller „Υπογραφή" stod ensam ovanför namnet – i det
  grekiska fallet identifierades efternamnet till och med som en
  ortsuppgift i stället för som ett namn. Liksom redan vid „Подпись"
  (ryska) identifieras namnet nu fullständigt.

- Text på ett sidoställt mobilfoto (den vanliga stående bilden som bara
  via en bildrotationsmarkör visas rättvänd) kunde förbises av
  textigenkänningen, eftersom den hittills läste de råa, liggande
  bildpunkterna. Sådana foton roteras nu rätt väg före läsningen –
  liksom redan tidigare vid ansiktsigenkänningen.

- Ett fullständigt namn i underskriftsraden på ett ryskt, ukrainskt
  eller litauiskt dokument förblev delvis oupptäckt, om beteckningen
  „Подпись", „Підпис" eller „Parašas" stod ensam ovanför namnet – för-
  eller patronymikonet föll bort. Liksom redan vid „Potpis" (kroatiska)
  identifieras namnet nu fullständigt.

- Ett ansikte på ett sidoställt mobilfoto (den vanliga stående bilden
  som bara via en bildrotationsmarkör visas rättvänd) kunde förbises av
  ansiktsigenkänningen, eftersom den hittills kontrollerade de råa,
  liggande bildpunkterna. Sådana foton roteras nu rätt väg före
  sökningen.

- Ett fullständigt namn i underskriftsraden på ett kroatiskt dokument
  förblev delvis oupptäckt, om beteckningen „Potpis" stod ensam ovanför
  namnet eller med kolon framför – förnamnet föll bort, oavsett om som
  egen rad eller i „Potpis: förnamn mellannamn efternamn". Liksom
  redan vid „Unterschrift" och „Signature" identifieras namnet nu
  fullständigt.

- Ett makarnas efternamn bakom civilståndsförkortningarna „verh."
  (gift) och „verw." (änka/änkling) förblev tidigare helt oupptäckt,
  oavsett om i parentes, efter komma eller ihopklistrat utan mellanslag
  („Anna Meier (verh. Weber)", „Klaus Bauer (verw.Fischer)") – liksom
  redan vid „geb." identifieras det nu tillförlitligt.

- Ett namn bakom prokuratecknandet „ppa." (t.ex. i signaturraden i ett
  affärsmejl eller ett affärsbrev) förblev vid ett yrkesnamnlikt
  efternamn som „Bauer" eller „Koch" tidigare delvis eller helt
  oupptäckt – liksom redan vid „gez." identifieras det nu
  tillförlitligt.

- Numret på det polska ID-kortet (dowód osobisty) identifierades bara
  utan mellanslag mellan serie och nummer („ABS123456"). Precis så
  trycker dokumentet dock inte uppgiften – officiellt står ett
  mellanslag mellan dem („ABS 123456"), och i detta skrivsätt förblev
  numret tidigare oupptäckt.

- En animerad PNG (APNG, t.ex. en som PNG i stället för GIF lagrad
  kort skärminspelning) kontrollerades och rensades tidigare bara med
  sin första bild, utan att detta rapporterades – liksom tidigare vid
  animerad WebP meddelar Maskuro nu att varje ytterligare bild förblir
  okontrollerad i resultatet.

- En animerad WebP-bild (t.ex. från ett skärmdumpsverktyg eller en
  chattapplikation med flera bilder i en fil) kontrollerades och
  rensades tidigare bara med sin första bild, utan att detta
  rapporterades – liksom tidigare vid en flersidig TIFF meddelar
  Maskuro nu att varje ytterligare bild förblir okontrollerad i
  resultatet.

- Ett slovenskt dubbelförnamn med bindestreck („Ana-Marija Novak")
  förlorade sin första hälft så snart en löpande sats föregick den i
  texten – samma fel som tidigare vid polska. „Ana-" förblev obelagt i
  klartext, medan resten av namnet redan var ersatt.

- Ett polskt dubbelförnamn med bindestreck („Anna-Maria Kowalska")
  förlorade sin första hälft så snart en löpande sats eller en
  preposition som „z"/„od" föregick den – resten av namnet ersattes,
  „Anna-" förblev obelagt i klartext.

- Kazakiska hövlighetsformer „Хабарласыңыз"/„Байланысыңыз" (kontakta
  oss) samt serbiska verbformer „Помоћи", „Чекамо" och „Пишите" utan
  egen språkigenkänningsmodell identifierades felaktigt i
  telefonmeningar som personnamn eller ort.

- Det azerbajdzjanska hövlighetsordet „Xahiş" (vänligen/begäran) utan
  egen språkigenkänningsmodell identifierades felaktigt i
  telefonmeningar som personnamn.

- Indonesiska och malajiska hövlighets-/uppmaningsord utan egen
  språkigenkänningsmodell som „Silakan", „Mohon" (indonesiska), „Sila"
  och „Tolong" (malajiska) identifierades felaktigt i telefonmeningar
  som personnamn eller ort.

- Den uzbekiska uppmaningsformen „Kutamiz" (vi väntar) utan egen
  språkigenkänningsmodell identifierades felaktigt i telefonmeningar
  som ort.

- Turkiska uppmaningsformer utan egen språkigenkänningsmodell som
  „Arayınız" (ring) och „Bekliyoruz" (vi väntar) identifierades
  felaktigt i telefonmeningar som personnamn.

- Uppmaningsformer på ytterligare språk utan egen
  språkigenkänningsmodell (tjeckiska, slovakiska, grekiska) som
  „Zavolejte" (ring), „Prosíme" (vi ber) och „Περιμένουμε" (vi väntar)
  identifierades felaktigt i telefonmeningar som personnamn eller ort.

- Ungerska och polska uppmaningsformer som „Hívjon" (ring), „Kérjük"
  (vi ber), „Várjuk" (vi förväntar), „Zadzwoń" (ring) och „Czekamy" (vi
  väntar) identifierades felaktigt i telefonmeningar som personnamn
  eller ort.

- I en numrerad namnlista utan tabellform (t.ex. „1. Robert Brown",
  därunder „2. Mary Johnson") förbisågs helt ett namn med vissa
  engelska efternamn (bland andra „Brown", „White", „Green", „Black",
  „Young") – språkmodellen hade bundit nästa rads nummer till namnet,
  varigenom träffen aldrig längre stämde exakt.

- Vid den polska språkmodellen förblev det framförställda
  förnamnsinitialen framför ett efternamn (t.ex. „J. Kowalski",
  „A. Nowak") oidentifierad och orensad i texten – bara efternamnet
  ersattes. Andra kontrollerade språk (bland andra tyska, engelska,
  rumänska, kroatiska, ungerska, ryska) tog redan tidigare med samma
  initial.

- Ett personnamn bakom en gement skriven titel som „dr.", „ing." eller
  „dipl. ing." identifierades inte alls på ungerska, rumänska och
  kroatiska – inte bara titeln, utan hela namnet gick förlorat (t.ex.
  „dr. Kovács Béla", „ing. Andrei Popescu", „dipl. ing. Marko Horvat").
- I slovenska mötesprotokoll identifierades en ren rollbeteckning
  framför kolon (t.ex. „Tajnik:", „Podpredsednik:", „Poročevalec:",
  „Predsedujoči:") felaktigt som personnamn, så snart ett riktigt
  talarnamn redan stod någon annanstans i protokollet.
- I ryska mötesprotokoll identifierades en ren rollbeteckning framför
  kolon (t.ex. „Секретарь:", „Докладчик:", „Докладчица:") felaktigt som
  personnamn, så snart ett riktigt talarnamn redan stod någon
  annanstans i protokollet.
- I rumänska mötesprotokoll identifierades en ren rollbeteckning med
  bestämd artikel framför kolon (t.ex. „Secretarul:", „Președintele:",
  „Vicepreședintele:", „Moderatorul:", „Consilierul:") felaktigt som
  personnamn – „Președintele" redan för sig själv, de övriga dessutom
  så snart ett riktigt talarnamn redan stod någon annanstans i
  protokollet.
- I kroatiska mötesprotokoll identifierades en ren rollbeteckning
  framför kolon (t.ex. „Izvjestiteljica:", „Zapisničar:"/„Zapisnicar:",
  „Predsjedavajući:") felaktigt som personnamn.
- En polsk postboxadress „Skrytka pocztowa" bakom en avsändar- eller
  mottagarbeteckning (t.ex. „Odbiorca: Skrytka pocztowa 45")
  identifierades felaktigt som personnamn.
- En kroatisk postboxadress „Poštanski pretinac" bakom
  adressbeteckningen „Adresa:" (t.ex. „Adresa: Poštanski pretinac 45",
  även med tillagt „br." för numret) identifierades felaktigt som
  personnamn.
- En ort utan ytterligare beteckning i norsk löptext (t.ex. „Anna
  Hansen bor i Oslo") identifierades inte – den egna språkmodellen
  betecknar orter där oftast med en egen, tidigare inte tilldelad
  etikett i stället för det vanliga „LOC".
- Ett datum i ISO-ordningen år-månad-dag med bindestreck eller punkt
  (t.ex. „2024-12-31") identifierades inte alls som datum på vissa
  språk – mest påfallande på litauiska, där officiella skrivelser
  övervägande anger datum i denna ordning.
- Ett ungerskt momsregistreringsnummer (közösségi adószám) i den
  officiellt likaledes giltiga, avgränsarlösa 11-siffriga formen (t.ex.
  „12345678123" i stället för „12345678-1-23") identifierades inte.
- Ett polskt skattenummer NIP med avgränsarna i grupperingen 3-2-2-3
  (t.ex. „856-73-46-215", som är vanlig på fakturor från företag och
  enskilda näringsidkare) identifierades inte – bara grupperingen
  3-3-2-2 för fysiska personer träffade.
- Ett företagsnamn under den slovakiska fältbeteckningen
  „Zamestnávateľ:" eller „Názov zamestnávateľa:" (arbetsgivare/företag)
  identifierades inte.
- Ett företagsnamn under den rumänska fältbeteckningen „Angajator:"
  eller „Denumire angajator:" (arbetsgivare/företag) identifierades
  inte.
- Ett företagsnamn under den ungerska fältbeteckningen „Cég:" eller
  „Munkáltató:" (företag/arbetsgivare) identifierades inte.
- Ett företagsnamn under den polska fältbeteckningen „Pracodawca:"
  eller „Nazwa firmy:" (arbetsgivare/företag) identifierades inte.
- Ett företagsnamn under den slovenska fältbeteckningen „Podjetje:"
  eller „Delodajalec:" (företag/arbetsgivare) identifierades inte.
- Ett företagsnamn under den kroatiska fältbeteckningen „Tvrtka:"
  eller „Poslodavac:" (företag/arbetsgivare) identifierades inte.
- Ett utskrivet penningbelopp med gement skriven valuta (t.ex. „500
  euro") identifierades inte, bara versal skrivning („Euro") träffade.
- Efternamnet bakom „Schwager"/„Schwägerin" (svåger/svägerska, t.ex.
  „Der Schwager Bauer erhält die Erbschaft.") identifierades inte.
- Vid en turkisk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „34000 İstanbul İstiklal
  Caddesi No: 45") förblev husnumret orensat.
- Vid en slovakisk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „831 01 Bratislava Hlavná
  15") förblev husnumret orensat.
- Ett födelseland utan ytterligare beteckning i ett kroatiskt
  formulärfält (t.ex. „Zemlja rođenja: Njemačka") identifierades inte.
- Ett födelseland utan ytterligare beteckning i ett litauiskt
  formulärfält (t.ex. „Gimimo valstybė: Vokietija") identifierades
  inte.
- Ett födelse- eller bosättningsland utan ytterligare beteckning i ett
  polskt formulärfält (t.ex. „Kraj: Niemcy") identifierades inte.
- En nationalitets- eller bosättningsort utan ytterligare beteckning i
  ett slovenskt formulärfält (t.ex. „Državljanstvo: Nemčija")
  identifierades inte.
- Ett bosättningsland utan ytterligare beteckning i ett norskt
  formulärfält (t.ex. „Bosted: Tyskland") identifierades inte.
- Ny inställningssida „Aviseringar" (tidigare ett avsnitt i „Program"):
  de tre aktivitetsfältsmeddelandena (förhandsvisning redo, bearbetning
  klar, uppdatering nedladdad) står nu på en egen plats.
- Nytt: resultatet kan dessutom sparas som en ren textfil (.txt) eller
  med ändelsen .md bredvid – för vidarebearbetning i en KI eller ett
  annat program.
- Vid en kroatisk kontaktuppgift med beteckningen „Osoba za
  kontakt"/„Kontakt osoba" (t.ex. „Osoba za kontakt: Golub Marko")
  förblev namnet helt oidentifierat, om efternamnet samtidigt var ett
  vanligt substantiv (Golub = „duva").

- Vid en rumänsk kontaktuppgift med beteckningen „Persoana de
  contact"/„Persoană de contact" (t.ex. „Persoana de contact: Lup
  Ion") förblev namnet helt oidentifierat, om efternamnet samtidigt var
  ett vanligt substantiv (Lup = „varg") och förnamnet mycket kort och
  generiskt.

- Vid en polsk kontaktuppgift med beteckningen „Osoba
  kontaktowa"/„Osoba do kontaktu" (t.ex. „Osoba kontaktowa: Wilk
  Adam") förblev efternamnet oidentifierat, om det samtidigt var ett
  vanligt substantiv (Wilk = „varg", Zielony = „grön").

- Vid en rumänsk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „010061 București Strada
  Victoriei 30") förblev husnumret orensat.
- Vid en serbisk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „11000 Beograd Bulevar
  Kralja Aleksandra 73") förblev husnumret orensat.
- Vid en grekisk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „104 32 Αθήνα Ερμού 15")
  förblev husnumret orensat.
- Vid en slovensk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „1000 Ljubljana Slovenska
  cesta 58") förblev postnumret orensat.
- Vid en litauisk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „LT-01100 Vilnius Gedimino
  pr. 9") förblev postnumret helt orensat.
- Vid en ungersk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „1052 Budapest Kossuth
  Lajos utca 12") förblev postnumret orensat.
- Ett efternamn bakom „Erben" (arvingar, t.ex. „Die Erben Wagner
  erhielten die Mitteilung fristgerecht.") förblev i arvskontext så
  gott som alltid oidentifierat.
- Ett efternamn bakom „Geschwister" (syskon, t.ex. „Die Geschwister
  Bauer wohnen in Linz.") förblev tidigare så gott som alltid
  oidentifierat – till skillnad från „Familie"/„Ehepaar" träffade det
  inte bara yrkesordslika namn (Koch, Bauer, Richter), utan godtyckliga
  efternamn på detta ställe.
- Ett efternamn bakom „Ehepaar" eller „Eheleute" (äkta par, t.ex. „Das
  Ehepaar Koch zieht um.") identifierades inte, om det samtidigt var
  ett vanligt substantiv eller en yrkesbeteckning (Koch, Bauer,
  Richter).
- Ett vanligt beställnings-, order- eller artikelnummer i det typiska
  grupperingsrastret för ett skattenummer eller personnummer (t.ex.
  „030 4471 2298") maskerades felaktigt som sådant utan någon
  tillhörande beteckning.
- Ett belägg-/ärendenummer i formatet „år/löpnummer" (t.ex. i „Rechnung
  Nr. 4/2024/778899") maskerades felaktigt av telefonnummerigenkänningen
  som telefonnummer.
- Ett namn bakom „Herr"/„Frau" med en flerordig akademisk titelkedja
  framför („Herr Dr. med. Weber", „Herr Prof. Dr. Krause") förblev
  tidigare helt oskyddat – identifierat blev tidigare bara ett enskilt
  titelord mellan tilltalsform och namn.
- Ett rättsligt diarienummer i det klassiska formatet med
  kammar-/senatsförkortning („4 Ca 1523/24", „Az.: 7 O 234/25") förblev
  tidigare helt oskyddat – även den vanliga kortformen „Az."/„Gz."
  identifierades inte bredvid den utskrivna beteckningen.
- Ett kreditkortsnummer som mitt i sin fyrgruppering delades av en
  radbrytning – till exempel i en smal tabellkolumn – förblev tidigare
  helt oskyddat.
- Ett skatteidentifieringsnummer som mitt i sin gruppering delades av
  en radbrytning – till exempel i en smal tabellkolumn eller ett
  formulärfält – förblev tidigare helt oskyddat.
- Ett personnummer som mitt i sin gruppering delades av en
  radbrytning – till exempel i en smal tabellkolumn – förblev tidigare
  helt oskyddat, inte ens delvis ersatt.
- Ett husnummer med intervall som „12a-14b" eller „3-5" ersattes bara
  till hälften – den andra delen bakom bindestrecket förblev öppen i
  resultatet.
- Ett chassinummer (FIN/VIN) som mitt i sina 17 tecken delades av en
  radbrytning, ett mellanslag eller ett bindestreck – till exempel i en
  smal tabellkolumn eller ett fordonsregisterfält – förblev tidigare
  helt oskyddat.
- En brev-/mejlhälsning som „Liebe Anna!" eller „Lieber Hans" – utan
  komma efter namnet, den vanligaste formen i informella mejl – lämnade
  namnet helt oskyddat, även i hela dokumentet med löptext och
  hälsningsfras under.
- Samma lucka drabbade även de informella chatt-/mejlhälsningarna
  „Hallo Anna!", „Hi Anna!", „Hey Anna!" och „Servus Anna!" utan komma
  – namnet förblev likaså helt oskyddat.
- Ett rent signaturblock som direkt börjar med „MfG" eller „Herzlichst"
  – till exempel kopierat från urklipp, utan föregående mening –
  lämnade namnet under helt oskyddat.
- Ett fält med flera personer, till exempel „Angehörige: Kaczmarek,
  Piotr (Sohn), Kaczmarek, Anna (Ehefrau)", smälte samman båda namnen
  tillsammans med parentesangivelsen till en enda, alldeles för lång
  träff – det andra namnet förblev därvid delvis oskyddat i resultatet.
- En gata utan „-straße"/„-weg"-ändelse – som är vanlig på landsbygden,
  till exempel „Am Marktplatz 5" eller „Im Grund 12" – identifierades
  inte, om den följdes av en postnummer-ort-rad, till exempel i ett
  registreringsintyg: „Neue Anschrift: Am Weidengarten 17, 54295 Trier"
  förlorade gatan helt, bara postnumret togs bort.
- Ett namn bakom en sammansatt fältbeteckning med snedstreck (till
  exempel „Name/Vorname: Bauer Klaus") identifierades delvis inte – ett
  tvetydigt efternamn som „Bauer" förblev oupptäckt utan fältbelägget.
  Samma lucka drabbade kombifält som „PLZ/Ort: 04109 / Leipzig".
  Detsamma gällde kombifält med utskriven bindeled i stället för
  snedstreck, till exempel „Vor- und Nachname: Bauer Klaus" eller
  „Nachname bzw. Vorname: …".
- Ett födelsedatum i formen „Datum der Geburt: …" och ett dödsdatum i
  formen „Todesdatum: …" eller „Datum des Todes: …" identifierades
  inte – bara „Geburtsdatum: …" respektive „Sterbedatum: …" träffade.
- Ett bröllopsdatum i formen „Datum der Heirat: …" eller „Datum der
  Hochzeit: …" identifierades inte – bara „Hochzeitsdatum: …",
  „Heiratsdatum: …" och „Datum der Eheschließung: …" träffade, trots
  att skilsmässo-, medborgarskaps- och partnerskapsdatum sedan länge
  kände till samma „Datum der X"-form.
- Ett skilsmässodatum i formen „Datum der Scheidung: …" identifierades
  inte – bara „Scheidungsdatum: …" och den efterställda verbformen
  träffade, trots att medborgarskaps- och partnerskapsdatum känt till
  samma „Datum der X"-form från början.
- Ett partnerskapsdatum identifierades tidigare inte alls – varken med
  beteckning („Verpartnerungsdatum: …", „Datum der Lebenspartnerschaft:
  …") eller i löptext („… wurden am … verpartnert"). Nu ersätts det som
  en egen uppgiftstyp, som födelse-, bröllops-, skilsmässo- och
  medborgarskapsdatum.
- Ett medborgarskapsdatum identifierades tidigare inte alls – varken med
  beteckning („Einbürgerungsdatum: …") eller i löptext („… wurde am …
  eingebürgert"). Nu ersätts det som en egen uppgiftstyp, som
  födelse-, bröllops- och skilsmässodatum.
- Ett skilsmässodatum identifierades tidigare inte alls – varken med
  beteckning („Scheidungsdatum: …") eller i löptext („Die Ehe wurde am
  … geschieden"). Nu ersätts det som en egen uppgiftstyp, som
  födelse-, döds- och bröllopsdatum.
- Ett bröllopsdatum bakom genealogitecknet för äktenskap „⚭" utan
  beteckning identifierades inte, trots att födelse- och dödsdatum på
  samma rad via stjärna och kors redan identifierades – nu identifieras
  även bröllopsdatumet.
- Ett dödsdatum bakom dödsannonsens kors utan beteckning
  („*03.06.1940 †21.11.2023") identifierades inte, trots att
  födelsedatumet framför via genealogistjärnan redan identifierades –
  nu identifieras även dödsdatumet.
- Efternamn före förnamn i slutet av en ämnes-/ärenderad med
  föregående sakord och bindestreck („Betreff: Reklamation - Bauer,
  Anna") identifierades inte vid ett yrkesnamnlikt efternamn – nu
  identifieras det.
- Sökande- och ansökningsnummer bakom sin beteckning
  („Bewerbernummer: 4471829", „Antragstellernummer: 7654321") föll
  helt genom igenkänningen – nu identifieras de.
- Ersätt maskerar inte längre när det inte finns plats för en läsbar
  platshållare – en för liten platshållare skrivs nu mindre i stället
  för att bli ett tomt streck, så länge det alls finns plats kvar. Nytt
  dessutom: om ett fyndställe på en bild (brevhuvud, skanningsbakgrund)
  betecknas eller bara maskeras går nu att ställa in oberoende av den
  övriga resultattypen. Och ett fyndställe på en bild som tas bort
  helt betecknades som om bilden fanns kvar – platshållaren stod ljus
  på en grund som aldrig maskerades, och försvann därmed osynligt på
  det nu vita papperet.
- Ett fyndställe på en **bevarad** bild maskerades vid ersättning alltid
  svartvitt, oberoende av den valda utformningen (kategorifärger,
  regnbåge …) – synligt som ett brott mellan färgglada etiketter i
  löptexten och svarta streck på brevhuvudet. Bildgrunden följer nu
  samma färg som platshållaren bredvid.
- Igenkänningen av fordonsidentifieringsnumret (FIN/VIN) markerade
  villkorslöst varje 17-siffrig alfanumerisk kod utan I/O/Q som
  chassinummer – även order-, serie- och licensnyckelnummer som av en
  slump har samma form. Nu räknas den bara med ett kontextord i
  närheten („FIN", „VIN", „Fahrgestell", „Chassis" o.dyl.).
- I ärende-/kalendersystem drog namnigenkänningen med sig nästa fältord
  efter „Assigned to"/„Closed by" o.dyl., om det stod direkt efter på
  samma rad utan avgränsare („Assigned to Max Mustermann Priority High"
  blev till „Max Mustermann Priority"). I Git-commit-huvudrader drog
  namnigenkänningen likaså med sig **nästa** trailer-nyckel, om två
  rader hängde ihop med bara ett mellanslag i stället för radbrytning
  („Author: julia bergmann Reviewed-by: …" blev till „julia bergmann
  Reviewed-by"). Båda bromsarna kompletterade.
- Namnet bakom „p.A.", „zH"/„zHd", „i.A."/„i.V." och „geb." drog med sig
  ett direkt följande avdelningsord in i samma träff, om det stod utan
  avgränsare på samma rad („p.A. Max Mustermann Buchhaltung" blev till
  „Max Mustermann Buchhaltung", „i.A.Max Mustermann Vertrieb" till „Max
  Mustermann Vertrieb"). Samma broms som vid „Assigned to"/Git-trailrar
  kompletterad även här.
- Ett betecknat IBAN-nummer direkt ovanför BIC-, BLZ- eller
  SWIFT-raden drog med sig dess beteckning in i sin egen träff,
  eftersom „BIC" och „BLZ" själva såg ut som ett ytterligare nummerblock
  – ur „IBAN: DE89 … 0130 00" och raden därunder blev en enda, för
  vitt gående träff, och beteckningen på nästa rad försvann med vid
  rensningen. Berörd var nästan varje bankförbindelse med IBAN och BIC
  under varandra.
- Träffpanelen säger nu **var** en platshållare finns som den inte kan
  hitta på sidan. Två fall meddelade tidigare bara „hittades inte",
  trots att ersättningen ägde rum: står platshållaren i osynlig
  bitext – till exempel referensadressen till en länk, en anmärkning
  eller ett formulärfält – bär raden nu det som en egen upplysning
  („i bitext"), och klicket förklarar det. Och skrevs platshållaren i
  förkortad form på grund av platsbrist („[N382]" i stället för
  „[NAM382]"), hoppar klicket på den långa raden nu till
  kortformsstället och nämner omdöpningen; tilldelningen kopplar därför
  uttryckligen ihop båda raderna.
- Står samma ersättningsvärde flera gånger i dokumentet, hoppar varje
  ytterligare klick på panelraden i cirkel till nästa fyndställe –
  även över sidgränser; statusraden räknar med („fyndställe 2 av 4"),
  och det just anlöpta stället är kraftigare inramat än de övriga. Och
  om en platshållare bara finns i träfflistan, men ingenstans i
  dokumentet (eftersom stället gick upp i en överlappande ersättning),
  säger statusraden nu det, i stället för att klicket förblir tyst utan
  följd.
- Ett förkortat förnamn bakom „an" eller „für" identifieras nu
  tillförlitligt som namn – „Überweisung an M. Wagner" och „Rechnung
  für M. Wagner" förblev tidigare ofta orensade, medan samma namn med
  en annan beteckning framför (till exempel „Zahlungsempfänger:")
  redan hittades. Berörda var främst kontoutdrags- och bokföringsrader.
- „Angeklagter"/„Angeklagte"/„Beschuldigter"/„Beschuldigte" (åtalad,
  misstänkt) gäller nu som namnfält: stod ett namn i
  straffprocesshandlingar direkt bakom en av dessa beteckningar,
  identifierades det tidigare inte alls för ungefär hälften av de
  kontrollerade namnen – varken för- eller efternamn.
- Stället som klickas i träffpanelen ramas nu in i blått i stället för
  att markeras gult – på de färgade trafikljusytorna syntes gult
  sökresultat inte. Dessutom hittar klicket nu även flerordiga
  ersättningsvärden (hittade namn, maskerade nummer): tidigare hade det
  ingen effekt på sådana rader, eftersom fyndstället bara söktes ord
  för ord.
- Adoptiv-, foster- och styvföräldrar („Adoptivvater", „Pflegemutter",
  „Stiefvater" med flera) identifieras nu som namnfält, namnet föll
  tidigare igenom orensat.
- Sifferrika tabeller och listor förkastas inte längre felaktigt:
  ersattes ett kort tal (till exempel en som telefonnummer feltolkad
  kundnummerdel), meddelade slutkontrollen samma sifferföljd som
  kvarvarande uppgift även när den på annat håll bara av en slump ingick
  i ett helt annat nummer – och gav då inget resultat alls. Ett tal
  räknas nu bara som en rest där det står som ett eget tal.
- Personuppgiftshandlingar: „Vater:"/„Mutter:" (far/mor) gäller nu som
  namnfält, förälderns namn föll tidigare igenom orensat.
- Ytterligare familjeroller („Pate", „Großvater/-mutter", „Ehepartner",
  „Lebenspartner", „Onkel", „Tante") gäller nu som namnfält, namnet föll
  tidigare igenom orensat.
- Det tyska bankgirot identifieras nu även officiellt grupperat
  ("370 400 44", "370.400.44", "370-400-44", "370/400/44"), inte bara
  som åtta sammanhängande siffror.
- Det tyska pensionsförsäkringsnumret identifieras nu även med punkt,
  bindestreck eller snedstreck mellan de fem blocken
  ("65-170839-J-08-8", "65.170839.J.08.8"), inte bara med mellanslag.
- Huvudfönstret visas snabbare: igenkänningsbiblioteken (Presidio
  tillsammans med språkmodellunderbygget) laddades tidigare redan vid
  fönsterbygget – på Windows cirka fyra sekunder innan något alls
  syntes. De laddas nu helt i bakgrunden; knappen „Rensa" blir som
  förut fri först när allt är klart.
- Kontorsdokument med många bilder eller videor skrivs snabbare: redan
  komprimerade medier lagras i resultatpaketet i stället för att
  nyttolöst komprimeras en andra gång – det sparade tidigare inte en
  byte och gjorde JPEG-filer snarare större.
- Kalkylblad och andra dokument med många små textenheter kontrolleras
  snabbare: språkigenkänningen bearbetar nu alla celler och stycken i
  ett dokument i en enda omgång i stället för enskilt – vid bevisligen
  samma fynd (400 celler: från cirka 4,7 till 2,5–3,5 sekunder).
- Listliknande PDF-sidor (förteckningar, positionslistor) sätter in
  platshållarna märkbart snabbare: platssökningen per beteckning gick
  tidigare över alla ord på sidan – nu bara över radomgivningen, vid
  bevisligen samma resultat (på en sida med 300 beteckningar cirka
  sexton gånger snabbare).
- Bildrika dokument sparar flera onödiga arbetssteg per bild:
  räkningen av ansikten och koder på PDF-sidor avkodar inte längre
  sidbilden dubbelt, kontrollen av metadata avkrypterar inte längre
  alls en ren bild, pixlerade bilder skrivs med den normala i stället
  för den långsammaste PNG-komprimeringen (samma storlek, en
  tredjedel av tiden), och utan inställd vattenstämpel utgår den
  nyttolösa omskrivningen av hela PDF-filen på slutet.
- Skannade PDF-filer med påslagen textigenkänning blir märkbart
  snabbare färdiga: varje sida renderades tidigare två gånger i full
  upplösning (en gång för läsning, en gång för rastrering) – avbilden
  återanvänds nu. Och på Windows/Linux läser textigenkänningen ränderna
  i en stor skanning i en omgång i stället för med en egen
  programstart per rand.
- Stora dokument rensas märkbart snabbare: jämförelsen av redan hittade
  värden växte tidigare med antalet fyndställen (ett 64 KB-textblock
  kostade i slutet av en stor fil cirka en sekund bara för det, nu en
  sextiondel), och sökningen efter företagsbolagsformer kördes med
  alla cirka 280 katalogformer över varje textställe (nu cirka tjugo
  gånger snabbare, vid bevisligen samma fynd).
- Ett namn direkt efter „Beste Grüße"/„Beste Wünsche" utan föregående
  text eller skiljetecken identifierades inte alls – ett rent
  signaturblock utan löptext framför lät namnet försvinna spårlöst.
- Ett adressfält i dokumentets början med ett yrkesnamnlikt efternamn
  („Bauer Anna", „Koch Stefan" som första rad ovanför gata och ort)
  förblev tidigare delvis oidentifierat eller klassades som
  ortsuppgift i stället för person – utan föregående mening saknade
  språkmodellen den satsbyggnad som annars gör att „Bauer" identifieras
  som namn och inte som yrke.
- Ett namn bakom underskriftsmärket „gez." med ett yrkesnamnlikt
  efternamn framför förnamnet („gez. Bauer Anna" i slutet av ett beslut
  eller en dom) förblev tidigare ofullständigt identifierat – bara
  förnamnet hittades, efternamnet försvann spårlöst.
- Ett namn direkt bakom ett kundnummer, avtalsnummer eller liknande
  identifieringsnummer utan egen rad („Vertragsnummer 55219 Bauer
  Anna", „Kundennr. 4711 Bauer Anna") identifierades tidigare
  ofullständigt eller inte alls vid ett yrkesnamnlikt efternamn.
- Symbolen i macOS-menyraden är nu en mall som anpassar sig till ljust
  och mörkt läge som grannsymbolerna – med de två utstansade strecken
  förblir den igenkännbar som Maskuro. Körs urklippsövervakaren, visas
  det med en avsatt prick vid skoldens spets.
- Ett klick i träffpanelen leder nu även vid anonymiserande drift till
  fyndstället: sidbyte, rullning in i bilden, gulmarkering. Tidigare
  hade klicket ingen effekt där, eftersom det fortfarande tog
  platshållarna för nummerlösa – sedan varje fyndställe bär sitt eget
  nummer är stället entydigt. Bara vid en verkligt nummerlös
  platshållare förklarar statusraden fortfarande varför inget
  hoppmål kan fastställas.
- Det första sparandet i efterbearbetningseditorn (Ctrl+S eller
  diskettknappen) frågar nu efter plats, som „Spara som …" –
  förifyllt med originalets mapp och resultatnamnet. Tidigare hamnade
  filen ordlöst bredvid originalet. Den som redan valt sparplatsen via
  statusraden tillfrågas inte igen; varje ytterligare sparande skriver
  som förut vidare samma fil.
- Meddelar säkerhetskontrollen före sparande ett iögonfallande ställe,
  leder „Tillbaka till kontrollen" nu dit: det första fyndstället rullas
  in i bilden och ramas in rött, statusraden nämner det. Tidigare blev
  man ensam med sidnummer och punktkoordinater. Från huvudfönstret
  öppnas editorn för det på stället. Även vid hänvisningen om ett
  avvikande sidantal leder knappen nu dit – till den första sidan som
  bara finns i ett av de båda dokumenten.
- Den som kopplar om förhandsvisningen till „Bredvid varandra i två
  spalter" får nu automatiskt ett fönster där båda banorna får plats –
  tidigare klämdes de in i den gamla bredden tills man själv drog. Det
  breddas högst till skärmkanten och smalnas aldrig tillbaka; en själv
  dragen bredd förblir stående.
- Efternamn och förnamn i separata tabellkolumner (t.ex. „Efternamn |
  Förnamn" i en anmälningsbekräftelse eller en CSV-export) förblev
  öppna – varje cell för sig såg för igenkänningen ut som ett
  godtyckligt ord utan namnsammanhang. Identifieras nu.
- Namn och förnamn på baksidan av ett EU-kortkörkort förblev öppna –
  de står där bakom de officiella fältkoderna „1." och „2." i stället
  för bakom ett tyskt ord, och just det gjorde att de inte
  identifierades. Identifieras nu, om körkortsnumret (fältkod „5.")
  står bredvid.
- Fordonsinnehavarens förnamn på registreringsbeviset förblev öppet –
  det står bakom den officiella fältkoden „C.1.2" i stället för bakom
  ett tyskt ord som „Vorname", och just det gjorde att det inte
  identifierades. Efternamn och förnamn under fältkoderna C.1, C.1.1
  och C.1.2 identifieras nu.
- Den första raden i den maskinläsbara zonen (MRZ) på pass eller ID-kort
  förblev öppen – den bär namnet i formatet „EFTERNAMN<<FÖRNAMN" och
  gick igenom obemärkt även med den nya MRZ-identifieraren för
  kontrollsiffreraden. Ett fynd räknas nu bara om det direkt bredvid
  finns en kontrollsiffergiltig andra MRZ-rad – själva namnraden har
  ingen egen kontrollsiffra.
- Den andra raden i den maskinläsbara zonen (MRZ) på pass eller ID-kort
  förblev helt oidentifierad – den innehåller passnummer, födelse- och
  utgångsdatum i klartext, men träffade ingen befintlig identifierare.
  En egen identifierare kontrollerar nu de fyra ICAO-kontrollsiffrorna.
- Ett fordonsregistreringsnummer utan något mellanslag till
  beteckningen förblev öppet – „KennzeichenM-AB1234" eller
  „KFZ-KennzeichenM-AB1234" identifierades inte alls, eftersom den
  underliggande registreringsnummerkontrollen förutsätter ett
  icke-ordtecken framför numret. Berörde fordonsuppgifter där inget
  mellanslag står mellan fältord och nummer.
- Ett telefonnummer utan något mellanslag till beteckningen förblev
  öppet – „Handynummer0171/2345678" eller „Tel0171/2345678"
  identifierades inte alls, eftersom den underliggande
  telefonnummerkontrollen förutsätter ett mellanslag eller skiljetecken
  framför numret. Berörde kontaktuppgifter där inget mellanslag står
  mellan fältord och nummer.
- Ett flicknamn/ursprungligt namn bakom förkortningen „geb." (född)
  identifierades inte alls – „Julia Bergmann (geb. Weber)" hittade bara
  „Julia Bergmann", punkten i „geb." fick språkmodellen att helt hoppa
  över det följande namnet. Berörde personuppgifter med ursprungligt
  namn inom parentes eller efter komma.
- Förnamnet framför ett smeknamn inom citattecken förblev öppet, om
  tilltalsform och titel stod tillsammans framför – „Herr Dr. Klaus "KP"
  Peters" gav bara „Peters", „Klaus" förblev läsbart. Berörde
  underskrifter och kontaktuppgifter med titel och smeknamn.
- Ett namn bakom den punktlösa kortformen „zH"/„zHd" (att uppmärksamma)
  identifierades inte alls – till skillnad från „z.Hd." med punkt drog
  den saknade satsstrukturen namnet med sig bort. Berörde adresser
  utan punkt i förkortningen.
- Ett namn bakom „p.A." (per adress) identifierades inte alls –
  punkten i förkortningen fick språkmodellen att helt hoppa över
  namnigenkänningen. Berörde fakturor och ansökningar med
  samlingsadress.
- Ett namn bakom punktlöst hopklistrat „i.A."/„i.V." (på uppdrag av/i
  ställföreträdarskap) identifierades inte alls, till exempel
  „i.A.Robert Lang" utan mellanslag – samma satsbyggnadsfel som vid
  „p.A.". Berörde underskriftsrader och e-postsignaturer vid
  ställföreträdarfall.
- En ren närvarolista med punktlistetecken utan någon ytterligare
  uppgift („- Max Mustermann", även med punkt vid radslutet) förlorade
  alla namn till samma broms som egentligen bara ska skydda
  saksuppräkningar som „- Farbe: Blau". Sådana listor identifieras nu.
- Filer som inte längre gick att rensa går åter att rensa. Ett värde
  som redan ersatts genom igenkänning kunde återfinnas i sitt eget,
  redan ersatta märke som „[SVNR1]" – slutprovet förkastade då en
  felfritt rensad fil. Dessutom tas en telefonreferens i en CSV-tabell
  nu bort med, och den som begränsar sökningen till enskilda typer får
  den nu likadant överallt i dokumentet – även i en bilds alternativtext,
  ett Excel-huvud, en urvalslista eller ett HTML-attribut.
- Ett namn bakom e-posthuvudraden „To:" (eller „To" utan kolon)
  identifierades inte, eftersom en främmande språkmodell läste hela
  raden som en enda oiögonfallande träff och slukade namnet i den helt
  – till skillnad från vid „Cc:", „Bcc:" eller „From:" framför samma
  namn. Ett namn bakom „To" hittas nu tillförlitligt.
- Bröllopsdatumet gick inte att behandla som datum i egna regler
  („förskjut" avvisades med „finns bara för datumangivelser"), saknades
  i gruppindelningen av fyndtyper – varigenom det inte gick att stänga
  av via märkena „Vad som söks" – och fick i stället för en kort
  förkortning som vid dödsdatum den fulla ordalydelsen som platshållare.
  Efterdraget för alla sex förkortnings-/beteckningstabeller.
- Ett i förhandsvisningen medvetet avmarkerat värde kunde ändå maskeras
  på ett annat ställe: valde man till exempel bort en mejladress, blev
  visserligen adressen själv kvar, men dess lokala del utan domän
  ersattes, så snart den sammanföll med det härledda användarnamnet för
  en ytterligare vald person („anna.musterfrau@beispiel.de" bredvid
  „Anna Musterfrau"). En avmarkerad ordalydelse förblir nu tabu i hela
  dokumentet, oberoende av vilken fyndtyp den kommer från.
- Ett födelsedatum identifierades inte, om ett familjebok- eller
  personbevisutdrag förde det under ett gemensamt huvud tillsammans med
  födelseorten („Geburtsdatum, Geburtsort: 19.11.1982, Steyr") – det
  andra fältordet mellan „Geburtsdatum" och datumet fick tidigare
  igenkänningen att helt falla igenom.
- Ett redan identifierat telefonnummer förblev läsbart i sin förkortade
  bekräftelseform, om det på annat håll i samma dokument bara nämndes
  med de sista fyra siffrorna („erreichbar unter der Nummer ...5678",
  „Rückruf unter ...5678") – samma byggform som vid IBAN och
  kreditkort.
- Ett redan identifierat kreditkortsnummer förblev läsbart i sin
  förkortade bekräftelseform, om det på annat håll i samma dokument
  bara nämndes med de sista fyra siffrorna („Ihre Kreditkarte endet auf
  ...0366") – samma i betalningsbekräftelser vanliga byggform som vid
  IBAN.
- Ett redan identifierat IBAN-nummer förblev läsbart i sin förkortade
  bekräftelseform, om det på annat håll i samma dokument bara nämndes
  med de sista fyra siffrorna („Die IBAN endet auf ...3201") – en i
  bekräftelsemejl vanlig byggform.
- En talare i ett chatt- eller mötesprotokoll förblev oidentifierad, om
  en tilltalsform stod framför namnet („Herr Bauer: …", „Frau Koch:
  …") – och drabbade därmed ofta även nästa talarrad i samma protokoll,
  eftersom för få identifierade rader blev kvar för att alls klassa
  dokumentet som protokoll.
- Ett födelsedatum identifierades inte, om fältordet „geboren" stod
  BAKOM datumet i stället för framför („Das Kind wurde am 14.01.2026
  geboren") – så formulerar till exempel ett föräldraledighets- eller
  mödraskyddsintyg barnets födelsedatum. Tidigare mönster förutsatte
  alltid fältordet framför datumet.
- En formulärbeteckning med en reaktions- eller bocksymbol direkt
  framför („Ansprechpartner 😊:", „Kontaktperson ✓:") identifierades
  inte längre som beteckning, och namnet under eller bakom den blev
  därigenom delvis bara ofullständigt hittat (t.ex. bara efternamnet
  vid „Mayer Roman").
- Samma lucka drabbade även särskilt skyddsvärda uppgifter enligt
  art. 9 GDPR (religion, hälsa, fackförening): en reaktionssymbol
  direkt framför avgränsaren eller radbrytningen („Konfession 😊:
  römisch-katholisch") fick beteckningen att helt falla igenom, och
  uppgiften förblev helt oidentifierad.
- En adress med bindestrecks-dubbelnamn i orten (t.ex. „79761
  Waldshut-Tiengen", „78050 Villingen-Schwenningen") förlorade
  postnumret helt, trots att orten själv identifierades och
  maskerades – på ett fordonsdokument eller följebrev förblev
  postnumret därigenom läsbart.
- En tabellkolumn utan kolumnavstånd (verkligt PDF-textutdrag) kunde
  under en namnkolumn även maskera två av en slump bredvid varandra
  stående versaliseringar felaktigt som person, till exempel två
  ortnamn i en datarad; det är nu bara fallet om inget annat fynd på
  samma ställe redan identifierar något annat.
- Samma namnkolumn maskerade i samma radform även två för
  språkmodellen okända sakord (t.ex. „Frontend Backend", „Turbo Modul")
  felaktigt som person, eftersom inget annat fynd där utlöste bromsen;
  nu krävs dessutom att minst ett av de två orden själv läses av
  språkmodellen som ett egennamn.
- Det tyska pensionsförsäkringsnumret identifierades inte i sin
  officiella fulla gruppering (t.ex. „65 170839 J 08 8" – så som det
  står på socialförsäkringsbeviset och lönebeskedet) och förblev i
  originalet; identifierade blev bara den kompakta skrivformen och den
  bara till bokstaven grupperade formen.
- Skatteidentifieringsnumret identifierades inte alls i sin officiella
  skrivform (gruppering 2-3-3-3, t.ex. „48 836 075 988" – så som det
  står på varje riktigt skattebesked och varje meddelande från det
  federala centralskattekontoret) och förblev i originalet; bara den
  mer sällsynta grupperingen 3-3-3-2 var täckt.
- Det nordrhein-westfaliska skattenumret (t.ex. „221/5147/0815", med
  fyrsiffrig i stället för tresiffrig andra grupp) identifierades inte
  alls i skattebesked och förblev i originalet – varje annat
  förbundsland var redan täckt.
- Vid anställningsavtal förbisågs ett namn bakom beteckningen
  „Arbeitgeber:" helt, så snart efternamnet samtidigt var ett vanligt
  ord (t.ex. „Bauer Anna") – „Arbeitgeber" står både som namn- och som
  företagsbeteckning i listan, och företagstilldelningen skrev över
  namntilldelningen.
- I ett hyresavtalshuvud med beteckningarna „Vermieter:"/„Mieter:"
  förbisågs ett efternamn som samtidigt är ett vanligt ord (t.ex.
  „Bauer") – bara förnamnet identifierades. Numrerade hyresparter
  („Mieter 1:", „Mieter 2:") var dessutom berörda, även vid namn utan
  denna tvetydighet.
- I ett rättegångsprotokoll med beteckningarna „Zeuge:"/„Kläger:"/
  „Beklagter:" (även med räkning, „Zeuge 1:", „Zeuge 2:") förbisågs
  likaså ett efternamn som samtidigt är ett vanligt ord (t.ex.
  „Bauer") – bara förnamnet identifierades.
- Vid arvsintyg, fullmakt, betalningsföreläggande och köpekontrakt
  förbisågs ett efternamn som samtidigt är ett vanligt ord (t.ex.
  „Bauer") bakom beteckningar som „Erblasser:", „Erbe:",
  „Vollmachtgeber:", „Bevollmächtigte:r", „Antragsgegner:",
  „Schuldner:", „Gläubiger:", „Käufer:", „Verkäufer:",
  „Vermächtnisnehmer:" eller „Testamentsvollstrecker:" – delvis
  identifierades bara förnamnet, delvis föll hela namnet bort.
- Vid en flerpartslista framför rubrumavgränsaren „./." (t.ex. „Sand,
  Werner und Huber, Anna ./. Wechsler, Martina") förblev den första
  parten omaskerad – bara parten omedelbart intill „./." identifierades.
- I rubrumavgränsaren „./." (t.ex. „Sand./.Wechsler") förbisågs namnet
  efter tecknet helt, om inget mellanslag stod där – bara med
  mellanslag före och efter fungerade igenkänningen.
- Efternamnet „Wahr" förbisågs helt, om det stod ensamt (t.ex. „Frau
  Wahr bearbeitet Ihren Vorgang.") – ordet står av en slump även i
  listan över vanliga tyska ord, som annars filtrerar bort namnfynd ur
  meningar som „Das ist wahr."
- Efternamn som „Los", „Weit", „Rund" eller „Hoch" förbisågs helt, om
  de stod ensamma (t.ex. „Herr Hoch übernahm die Leitung.") – alla
  fyra orden står av en slump även i listan över vanliga tyska ord, som
  annars filtrerar bort namnfynd ur meningar som „Rund einhundert Gäste
  kamen zur Feier."
- Efternamn som „Ganz" eller „Recht" förbisågs helt, om de stod
  ensamma (t.ex. „Herr Ganz unterschrieb den Vertrag.") – båda orden
  står av en slump även i listan över vanliga tyska ord, som annars
  filtrerar bort namnfynd ur meningar som „Ganz genau, das stimmt."
- Ett formulärfält med en asterisk eller en upphöjd fotnotsiffra bakom
  beteckningen (t.ex. „Konfession*: römisch-katholisch" eller
  „Religionszugehörigkeit¹: evangelisch") identifierades inte och
  förblev i klartext – bara formen utan detta tecken fungerade.
- Samma fält förblev fortsatt i klartext, om hela två
  fotnotstecken stod bakom beteckningen (t.ex. „Konfession**:
  römisch-katholisch" eller „Gewerkschaft¹²: ver.di").
- Ett versionsnummer som „Softwareversion 4.2.1.19" eller „Firmware
  Build 2.0.4.11" maskeras inte längre felaktigt som IP-adress.
  Detsamma gäller nu belägg- och ärendenummer som „Rechnungsnummer
  10.20.30.40" eller „Bestellnummer 7.8.9.10".
- Två IBAN-nummer direkt under varandra (t.ex. eget och en utländsk
  affärspartners i fakturahuvudet) identifierades inte längre båda –
  det andra förblev obemärkt kvar.
- Ett betecknat IBAN-nummer drog ibland med sig det följande ordet i
  meningen ("Bankverbindung AT61 … wird belastet" maskerades ända in i
  "wird"), så snart följdordet var gement skrivet – klartextresten
  bredvid förblev därvid orörd.
- Liechtensteinska adresser identifieras nu („FL-9490 Vaduz"), liksom
  tidigare redan tyska, österrikiska och schweiziska.
- Pass- och passnummer identifieras och tas nu bort bakom sin
  beteckning (t.ex. „Reisepassnummer: C01X00T471").
- Uppehållstillstånds- och folkbokföringsintygsnummer identifieras och
  tas nu bort bakom sin beteckning.
- Ett identifieringsnummer bakom sin beteckning identifieras nu även
  när ett tankstreck avgränsar i stället för ett kolon (t.ex.
  „Kundennummer – K903944").
- En som „IBAN" eller „Kontonummer" betecknad bankförbindelse
  identifieras nu även när ett tankstreck avgränsar i stället för ett
  kolon.
- Ett namn bakom en beteckning som „Kontaktperson (Vertrieb)" eller
  „Sachbearbeiter/in" identifieras nu även med parentestillägg eller
  könsneutral snedstrecksändelse.
- Samma asterisk-könsform („Sachbearbeiter*in") identifieras nu
  likaså.
- Ett namn bakom en beteckning identifieras nu även när ett
  likhetstecken avgränsar i stället för ett kolon (t.ex.
  „Ansprechpartner = Mayer Roman" eller „Kontaktperson=Mayer Roman"),
  som är vanligt i konfigurationsfiler eller CSV-huvuden. Står flera
  sådana beteckning-värde-par åtskilda av semikolon på en rad,
  identifieras nu bara det första värdet i stället för hela resten av
  raden.
- Ett GPS-koordinatpar bakom ordet „Koordinaten" identifieras nu
  tillförlitligt (t.ex. „Koordinaten: 48.2082, 16.3738") – ordet bar
  fel böjningsform i den interna katalogen.
- Ett identifieringsnummer bakom sin beteckning (kundnummer,
  avtalsnummer, diarienummer, ID-kortsnummer och omkring hundra
  ytterligare fältord) identifierades inte längre, så snart
  beteckningen inte stod exakt i den lagrade versal-/gementskrivningen
  – „kundennummer:" i ett mejl eller „KUNDENNUMMER:" i ett
  formulärhuvud förblev orörda.

### Nytt

- **Realistiska ersättningsvärden är nu ett medvetet insatt exempel i
  stället för ett förval.** Undantagstabellen i fliken „Platshållare"
  börjar tom. En ny knapp för på begäran in troliga falska värden för
  namn, ort, adress, organisation, e-post, telefon, anknytning och
  IBAN. Den lämnar penningbelopp uttryckligen kvar vid den numrerade
  platshållaren; strategin „hitta på" förblir för enskilda typer
  fortsatt valbar för hand.
- **KI-nivån kan använda grafikkortet.** Under Windows går ett drygt 17
  MB stort tilläggspaket att ladda ned för det; därefter räknar
  KI-nivån märkbart snabbare på ett lämpligt grafikkort än på
  processorn. Den som inte har något eller inte laddar ned något
  fortsätter arbeta oförändrat – bara långsammare. På macOS är
  accelerationen redan inbyggd.
- **Två nya aviseringar via aktivitetsfältsikonen**: när
  förhandsvisningen före ersättning är redo för genomgång och när en
  bearbetning är klar. Båda är förvalda på och kan stängas av enskilt
  under *Inställningar → Program → Aviseringar*.

### Ändrat

- **ID-korts- och körkortsnummer identifieras nu**, när deras
  beteckning står framför („Personalausweisnummer: …",
  „Führerscheinnummer: …") – tidigare föll båda genom varje
  igenkänning.
- **Maskuro följer nu Windows kontrastdesigner.** Den som under
  *Inställningar → Tillgänglighet → Kontrastdesigner* slagit på en fick
  tidigare det överallt utom här: Maskuro satte därefter sina egna
  färger. Nu förblir det vid systemets design – fönster, listor,
  avlämningszon, protokoll och statusfärger. Det färgade trafikljuset
  i förhandsvisning och efterbearbetningsfönster utgår medvetet där;
  det den säger står ändå sedan länge som tecken och som ord bredvid.
- **Kontrollbehovet står inte längre bara i färgen.** Rött, orange och
  grönt är nästan lika ljusa – den som har rödgrön färgblindhet såg i
  förhandsvisning och träfffack en lista utan skillnader, och det är
  ungefär var tolfte man. Varje rad bär nu dessutom ett tecken som
  skiljer sig i formen: ▲ kontrollera först, ● kontrollera, ○ väl
  belagd, ◆ utan bedömning. Kortinfon nämner det i ord, och en
  skärmläsare läser upp det.
- **Alt öppnar menyerna åter som vanligt.** Menyraden hade inga
  tangentbordskortkommandon: den som inte använder musen var tvungen
  att pila sig genom varje meny. Nu bär varje post en understruken
  bokstav – Alt+D för „Arkiv", därifrån A för „Avsluta" – och det på
  alla gränssnittsspråk.
- **Kontrollelement säger åter en skärmläsare vad de är till för.** I
  efterbearbetningsfönstret, i regelfönstret, i protokollet, i
  ordlistorna, i hjälpen, i sökkörningen och i fem ytterligare fönster
  meddelades listor, sökfält, klapplistor och reglage tidigare bara som
  „träd" eller „kombinationsruta" – utan om vad. Omkring fyrtio ställen
  bär nu ett namn. (Huvudfönstret var i ordning sedan augusti; de
  fönster som tillkom därefter hade aldrig fått samma steg.)
- **Den som styr med tangentbordet ser överallt var hen befinner sig.**
  Vid kontrollbehovsreglagen, vid kryssrutan och „aldrig igen"-knappen i
  förhandsvisningen, vid typrubrikerna i den, vid sidfacket i
  efterbearbetningsfönstret och vid inställningarnas sidopanel saknades
  ramen som systemet annars lägger runt det uppnådda kontrollelementet.
- **Större systemtext skär inte längre av något.** Den som under
  *Tillgänglighet → Textstorlek* ställer över 175 % förlorade tidigare
  slutet av beteckningarna i mappövervakningen och i fälten för
  tangentbordskortkommandon. Hjälpens kapitellista skar av långa
  kapitelnamn redan vid vanlig textstorlek; den bryter dem nu om och
  nämner hela namnet i kortinfon.

- **Igenkänningen har blivit märkbart snabbare.** Identifieraren för
  betecknade identifieringsnummer („Kundennummer: K903944")
  kontrollerade tidigare per textavsnitt över 1200 enskilda mönster
  efter varandra – det var den största enskilda posten av
  igenkänningstiden, vid varje stycke och varje tabellcell. Nu är det
  ett enda mönster med samma resultat: i mätkorpuset ändras inte en
  enda träff, grundnivån per textavsnitt blir ungefär tre till fyra
  gånger så snabb.
- **Fönstret visas genast vid start.** Tidigare laddade huvudfönstret
  de fullständiga språkverktygen innan det ens visade sig – cirka fyra
  sekunders blindtid vid varje start. Modellerna laddas nu som avsett
  i bakgrunden medan fönstret redan står; rensa-knappen blir som förut
  fri först när allt är klart. Även rena upplysningsanrop på
  kommandoraden (till exempel `--version`) svarar nu genast i stället
  för efter flera sekunder.
- **Bilder läses vid automatisk språkigenkänning bara en gång.**
  Tidigare kördes textigenkänningen vid förvalet „Språk: automatiskt"
  två gånger över samma bild – en gång för språkgissningen, en gång för
  den egentliga kontrollen. Bildfiler, urklippsbilder och textfönstret
  är därmed cirka dubbelt så snabbt klara; med avstängd
  textigenkänning bortfaller den tidigare obemärkt ändå körda läsningen
  helt.
- **Sparade webbsidor och e-post rensas snabbare.** Värdena i
  HTML-attribut, kommentarer och inbäddade datablock identifierades
  tidigare enskilt – en kommunsida med hundratals beteckningar
  ställde hundratals enskilda frågor till igenkänningen. Nu samlas de
  och identifieras per olika värde bara en gång; i mätkorpuset ändras
  ingen träff, .html och .eml är cirka en tredjedel snabbare.
- **Även delförvaringarna i kalkylblad och presentationer identifieras
  samlat.** Alternativtexter, formeltecken­strängar, diagrambeteckningar,
  kommentarer, pivot-mellanlager och dokumentegenskaper ställde tidigare
  per värde en egen igenkänningsfråga – en arbetsbok med tusentals
  pivotrader motsvarande tusentals. Nu körs en samlad omgång över de
  olika värdena, och den avslutande efterdragskörningen körs bara när
  det verkligen tillkommit nya värden sedan löptexten. I mätkorpuset
  ändras ingen träff.
- **Formulärrika PDF-filer rensas snabbare.** Fält, anteckningar,
  bokmärken och referenser upprepar samma värden massvis („Off" vid
  varje kryssruta, samma författare vid varje anmärkning) – vart och
  ett ställde tidigare sin egen igenkänningsfråga. Per körning
  identifieras ett värde nu bara en gång; ersättning och
  konsekvensefterkontroll körs oförändrat per ställe.
- **Stora tabellfiler (.csv/.tsv) rensas märkbart snabbare.** De fyra
  tabelleftergångarna delade tidigare upp samma fil var för sig
  teckenvis i celler (vid 40 MB cirka 30 s extraarbete); nu körs
  uppdelningen en gång. Kolumnhuvudsigenkänningen (födelsedatum- och
  personalnummerkolumner) ställer i stället för en fråga per cell en
  samlad – vid identiska fynd cirka tjugo gånger snabbare. Och
  namnkolumnssammanfattningen av stora personallistor är inte längre
  kvadratisk i radantalet.
- **Nyckeltalsklaffen fryser inte längre fönstret.** Uppfällningen av
  nyckeltalen läste vid många stora filer först ihop deras text och
  lät fönstret stå still i flera sekunder. Beräkningen körs nu i
  bakgrunden; klaffen öppnas genast och fyller i siffrorna i efterhand.
- **Sökkörningsrapporten fryser inte längre fönstret.** Efter
  genomsökning av många tusen filer beräknades den gemensamma mappen
  om för varje berörd fil; vid stora körningar stod fönstret då
  tvåsiffriga sekunder. Rapporten visas nu genast.
- **PDF-filer med textigenkänning kontrolleras snabbare.** Varje sida
  omvandlades vid motläsningen onödigt två gånger till PNG-format; nu
  skickas den redan befintliga bilden vidare. Resultatet är oförändrat,
  bara kontrollen går snabbare.
- **Förloppsanmärkningar på stora bilder hackar inte längre.** Vid
  dragning i handtagen på en anmärkning med toning beräknades
  toningen tidigare om punkt för punkt – på en stor skärmbild ett
  synligt hack. Resultatet är detsamma, bara utan pausen.

### Rättat

- **Krysset för att ta bort en fil ur listan är åter ett enkelt X.**
  Det nya editorverktyget „Ta bort" hade av misstag använt samma
  symbolidentifierare och visade därigenom sitt röda kryss tillsammans
  med streckad textlinje även i varje filrad. Båda handlingarna har nu
  separata symbolnamn och behåller sin respektive passande utformning.
- **Flerdelade uppgifter identifieras i PDF-filer nu även över en
  synlig radbrytning.** Maskuro läser den geometriskt skapade sidtexten
  dessutom som en offsetlik löptextvy. Detta gäller alla grund- och
  hög-nivåidentifierare samt egna sökmönster, inte bara det först
  synliga fallet „Diabetes mellitus Typ 2". Tomma rader och
  identifierade tabell- eller avsnittsgränser förblir hårda gränser;
  fyndställen passar fortfarande exakt på de ord som ska maskeras.
- **Exemplet vid „Pseudonymisera" motsade sig självt.** Meningen
  lovade „samma person, samma nummer" och visade sedan två olika
  nummer – exakt den bild som är korrekt vid „Anonymisera". Båda
  exemplen stämmer nu överens med sin egen mening.
- **En nysatt platshållare kunde vid „Hämta original" bli kvar som en
  överlagrad bokstavsröra i stället för att försvinna.** En enfärgat
  insatt platshållare skrev tidigare ett eget utmatningskommando per
  tecken, av vilka bara det första bar en egen textmatris – vid nästa
  redigering av samma ställe (till exempel „hämta tillbaka" direkt
  efteråt) fick de övriga teckenkommandona i tur och ordning det
  första teckenkommandots teckenindex tilldelade, och platshållaren
  föll sönder i två överlappande positioner. En enfärgad platshållare
  får nu ett enda utmatningskommando för hela sin text.

- **Stod samma maskerade eller borttagna värde under två rader i
  efterbearbetningsfönstret och markerades båda för återtagning,
  räknades den andra raden felaktigt som „inte entydig" – trots att
  värdet länge var återhämtat.** Båda raderna gäller nu som klara.

- **Namnet efter „Reply-To:" hittas nu.** I en e-posthuvudrad som
  „Reply-To: Huber" förblev namnet tidigare helt oidentifierat –
  språkmodellen läste „Reply-To:" som en egen, felaktig person och
  förbisåg det riktiga namnet efter.

- **E-posthuvudorden „Reply" och „Fwd" maskeras inte längre själva som
  namn.** I en ämnesrad som „Fwd: Angebot von Huber" identifierades och
  maskerades tidigare utöver namnet även själva huvudordet som person.

- **„Arbeitgeber: Siemens AG" identifieras nu som företag, inte längre
  som person.** Bar företagsvärdet bakom beteckningen „Arbeitgeber" en
  bolagsform som GmbH, AG eller KG, förblev det trots påslagen
  organisationsigenkänning ett personfynd – bara det smalare fallet
  utan bolagsform („Wollmuth und Partner") identifierades tidigare som
  företag.

- **En en gång identifierad adress blir inte längre kvar på ett annat
  ställe.** Identifierades och ersattes en gatuadress på ett ställe,
  kunde samma adress bli kvar på ett andra ställe – till exempel i en
  svårläst sidfot på ett inskannat dokument, där den automatiska
  textigenkänningen läste den stympad. Adresser tas nu, som namn och
  företag sedan länge, bort genomgående i hela dokumentet.

- **E-postmeddelanden med flera mottagare skadades tyst vid rensning.**
  Ett `.msg`-meddelande med två eller fler mottagare förlorade vid
  sparande delar av sin inre struktur, så att det rensade resultatet var
  ofullständigt. Orsaken var en förväxling av likabenämnda inre
  beståndsdelar som förekommer vid varje mottagare. Sådana meddelanden
  byggs nu om fullständigt igen.

- **Två av de medföljande testdokumenten gick inte att öppna i Word och
  PowerPoint.** Den som laddade ned mätkorpuset fick vid
  `format_dokument.docx` „Fel vid öppning av filen i Word" och vid
  `format_praesentation.pptx` „Filen är skadad". Båda filerna var redan
  felaktiga innan Maskuro rörde dem – den rensade versionen förde bara
  felet vidare. LibreOffice öppnade båda utan problem, varför ingen
  märkt det.

- **En egen KI på internet tilltalas nu krypterat.** Den som vid den
  egna KI:n anger en extern adress utan „https://" (som den ofta står
  på IT-avdelningens lapp) nådde den tidigare via en okrypterad
  anslutning – den omaskerade texten gick i klartext ut. Sådana adresser
  tilltalas nu via „https://"; en server i det egna nätet förblir
  oförändrat nåbar. Följer servern en omdirigering till en annan dator,
  följer åtkomstnyckeln inte längre med.

- **Även en skadad bild förlorar nu sin dolda metadata.** Gick en
  inbäddad bild inte längre att öppna fullständigt (till exempel ett
  avskuret foto), behöll den tidigare sin EXIF- och GPS-data –
  tagningsplats och fotografnamn förblev osynliga i resultatet. Sådana
  bilder befrias nu från denna data även när de inte längre går att
  visa alls.

- **En inbäddad fil som inte gick att rensa rapporteras nu i stället för
  att tyst följa med.** Låg i en presentation eller arbetsbok ett
  inbäddat objekt som var för djupt inkapslat eller inte gick att
  öppna, förblev det tidigare oförändrat i resultatet, utan hänvisning –
  filen gällde som rensad. Sådana fall står nu i varningen „kunde INTE
  kontrolleras", precis som ett inbäddat gammalt format.

- **Mörka listor är åter genomgående mörka och läsbara.** På macOS
  växlade fillistor mellan nästan svarta och ljusgrå rader; vid
  efterbearbetning såg samma gröna, orange eller röda kontrollvärde
  därför olika ut beroende på rad. Fönster, listor, text, platshållare
  och markering kommer nu från en gemensam ljus-/mörkpalett. Den
  färgkodade träfflistan lägger dessutom inte längre zebrarand under
  sina färger.

- **Yrkesuppgifter med „als" maskerades felaktigt som namn.** En
  mening som „Als Koch ist er seit vier Jahren bei uns tätig." förlorade
  yrket, inte bara ett namn – „als" inleder en rolluppgift precis som
  „der" eller „die". Riktiga efternamn på samma ställe (t.ex. med en
  tilltalsform framför) berörs inte av detta.

- **En tabellrubrik kunde dra in ett positionsnummer i ett
  penningbelopp** (bara med påslaget alternativ „Ta bort penningbelopp
  också"). Slutade en rad på en valuta („… Einzelpreis EUR") och
  började nästa med ett tal, blev det felaktigt ett belopp över
  radbrytningen. Avgränsaren mellan valuta och tal förblir nu på samma
  rad.

- **En kort versal förkortning kunde svälja en hel satsdel, eller
  hänga sig framför ett korrekt identifierat namn.** Stod på en rad ett
  tvåbokstavigt versalt ord som „DI", „AG" eller „KG" – vardagliga
  förkortningar, inga namn – genomsöktes hela raden provisoriskt
  gement, och förkortningen drog därvid ibland med sig angränsande ord
  (även verb) till ett enda påstått namn. Först från tre bokstäver
  utlöser ett versalt skrivet ord nu denna andra kontroll. Vid något
  längre förkortningar som „CEO" eller „USB" förblev ett andra fel: det
  redan korrekt hittade namnet („Schneider") fick den framförställda
  förkortningen dragen med som förled i resultatet („CEO Schneider").
  Förkortningen förblir nu utanför.

- **Ett födelsedatum utan mellanslag bakom förblev kvar.** Stod inget
  mellanrum bakom „geb." framför datumet – som är vanligt i tätt satta
  formulär („geb.14.03.1988") – identifierade Maskuro inte fältet och
  lämnade datumet orört. Vanliga kortformer som „Geburtsdat." eller
  „Geb.-Dat." identifieras nu likaså.

- **Ett IBAN-nummer med snedstreck som avgränsare förblev kvar.** Som
  vid telefonnummer („0664/1234567") skriver vissa mallar även IBAN i
  block med snedstreck („AT48/3200/0000/1234/5864") i stället för med
  mellanslag eller bindestreck. Detta skrivsätt identifieras nu likaså.

- **Ett österrikiskt personnummer med bindestreck, punkt eller
  snedstreck förblev kvar eller var felaktigt betecknat.** Mellan de
  båda talblocken var tidigare bara ett mellanslag avsett; skrivsätt
  som „1237-010180", „1237.010180" eller „1237/010180" identifierades
  inte (eller i snedstrecksfallet under fel typ). Kontrollsiffran
  bekräftar fortfarande varje träff, oberoende av avgränsare.

- **Ett namn bakom „c/o" i en adress togs inte alls bort.** „c/o Max
  Mustermann, Hauptstraße 5, 1010 Wien" maskerade gata och ort, men
  lämnade namnet bakom helt kvar. Namnet identifieras nu; „c/o" självt
  förblir synligt som en adresshänvisning.

- **Ett med punkter grupperat kreditkortsnummer förblev kvar.**
  Skrivsätt som „4111.1111.1111.1111" identifierades inte; med
  mellanslag eller bindestreck avgränsade nummer var inte berörda av
  detta. Kontrollsumman bekräftar fortfarande varje träff.

- **Ett med bindestreck grupperat skatteidentifieringsnummer förblev
  kvar, liksom ett österrikiskt momsregistreringsnummer med bindestreck
  eller punkt.** Mellanslag, snedstreck och punkt var redan avsedda vid
  skatte-ID:t, bindestrecket saknades; vid momsregistreringsnumret
  („ATU12345678") saknades bindestreck och punkt efter prefixet.
  Skatte-ID:ts kontrollsiffra bekräftar fortfarande varje träff.

- **Ett fältvärde inom citattecken förblev kvar, till exempel i en
  JSON-liknande rad som „vorname": „Max".** Igenkänningen via en
  fältbeteckning („Vorname: …") förutsatte tidigare att varken
  beteckningen eller värdet självt stod inom citattecken. Sådana rader
  identifieras nu likaså – liksom fältbeteckningar med en
  framförställd YAML-listpunkt („- Vorname: Max") eller en tabb i
  stället för ett mellanslag framför kolon.

- **E-posthuvudordet „Sent" maskerades själv som ett namn.** I en
  huvudrad som „Sent: Huber" träffade det tidigare både „Sent" och det
  egentliga namnet; besläktade huvudord som „Subject" eller „Betreff"
  var sedan länge orörda av detta. „Sent" förblir nu likaså kvar.

- Ett namn bakom huvudraderna „Errors-To:" eller „Resent-From:" förblev
  oidentifierat, om en sådan rad stod kopierad i klartext (till exempel
  ett vidarebefordrat meddelande eller en incidentrapport) – till
  skillnad från vid „Reply-To:" eller „Return-Path:" föll namnet här
  bort helt i stället för att bara vara onoggrant avgränsat. Det hittas
  nu.
- En och samma fil gav ibland olika resultat vid två rensningar:
  träffade två identifierare exakt samma ställe med samma längd och
  samma säkerhet (t.ex. „Sozialversicherungsnummer 1237/010180" som
  AT_SVNR eller som allmänt identifieringsnummer), var det slumpen som
  avgjorde vilken som vann – värdet togs bort i båda fallen, bara
  platshållarbeteckningen växlade. Lika läge löses nu alltid likadant.
- En funktionsbeteckning direkt framför ett substantiv (t.ex.
  „Behandelnder Arzt: Dr. …" eller „Zuständiger Sachbearbeiter ist …")
  maskerades ibland felaktigt med, som om den själv vore ett namn.
  Riktiga efternamn bredvid berörs inte av detta.
- Ett riktigt efternamn som av en slump ser ut som ett adjektiv (t.ex.
  „Schöne", „Lange", „Junge") och står omedelbart framför ytterligare
  ett substantiv (till exempel „Kontaktperson: Schöne Assistentin"),
  förblev sedan senaste åtgärden omaskerat i texten – ett dataläckage.
  Bara en snävt begränsad lista med riktiga funktionsbeteckningar
  (t.ex. „Behandelnder", „Zuständiger") behandlas nu i denna byggform
  som icke-namn.
- Ett fristående efternamn i slutet av en flerradig namnträff, som av
  en slump ser ut som ett adjektiv (t.ex. „Schwarz", „Kurz", „Alt",
  „Frisch", „Gut", „Reich"), förblev oidentifierat framför ett
  omedelbart följande kolon – rensningen förväxlade det med en
  fältbeteckning som „Telefon:". En sluten lista med kända tvetydiga
  efternamn skyddar det nu.
- Ett fristående efternamn som av en slump är ett vanligt tyskt ord
  („Gross"/„Grosse", „Gut", „Kurz", „Lang"/„Lange"), gick tidigare
  **helt** förlorat – även i enkla meningar som „Herr Gross
  unterschrieb den Vertrag." Orsaken låg i spaCys egen stoppordslista,
  som innehåller dessa ord; en sluten lista med kända efternamn skyddar
  dem nu från att förkastas.
- Vid anställnings-, lån-, borgens-, förvaltnings- och
  insolvensavtal samt förmyndarskap/vård och utredningsuppdrag
  förbisågs ett efternamn som samtidigt är ett vanligt ord (t.ex.
  „Bauer") bakom beteckningar som „Auftraggeber:", „Auftragnehmer:",
  „Arbeitnehmer:", „Versicherter:", „Darlehensgeber:",
  „Darlehensnehmer:", „Bürge:", „Sicherungsgeber:", „Treuhänder:",
  „Treugeber:", „Insolvenzverwalter:", „Gutachter:",
  „Sachverständiger:", „Vormund:" eller „Pfleger:" – delvis
  identifierades bara förnamnet, delvis föll hela namnet bort.
- I företagsuppgifterna förbisågs ett efternamn som samtidigt är ett
  vanligt ord (t.ex. „Bauer") bakom beteckningarna „Geschäftsführer:",
  „Geschäftsführerin:", „Vertretungsberechtigt:", „Inhaber:" eller
  „Inhaberin:" – vid „Geschäftsführer:"/„Inhaber:" föll hela namnet
  bort, vid „Vertretungsberechtigt:" identifierades bara förnamnet.
- Ett kontaktblock vars beteckning stod ensam på sin rad och bar den
  könsneutrala kolonformen („Ansprechpartner:in", namn under) förbisågs
  **helt** – kolon lästes som fältavgränsare, „in" som ett (förkastat)
  fältvärde, och det egentliga namnet på nästa rad kom därigenom
  aldrig till användning. Asteriskformen („Ansprechpartner*in") var
  inte berörd av detta.
- Stod namn och beteckning med samma kolon-könsform på **en** rad
  („Ansprechpartner:in Anna Berger"), drog platshållaren med sig ordet
  „in" i ersättningen, i stället för att bara ta bort namnet – namnet
  självt identifierades fortfarande fullständigt.
- Ett namn i en tabellkolumn under ett personkolumnhuvud (t.ex. „Name
  Vorname Geburtsdatum" ovanför „Bauer Anna 03.05.1985", som i ett
  lönebesked) förbisågs helt, så snart bara ett enda mellanslag stod
  mellan kolumnerna och ingen rad började med ett strukturnummer –
  exakt den form i vilken ett riktigt PDF-textutdrag levererar sådana
  rader.
- I ett chatt- eller mötesprotokoll med talarnamn framför kolon (t.ex.
  „Bauer 🙂: Ich stimme dem Vorschlag zu.") förblev namnet helt
  oidentifierat, så snart en reaktionssymbol stod mellan namn och
  kolon och efternamnet samtidigt var ett vanligt ord („Bauer", „Koch",
  „Schneider" o.dyl.) – ett helt protokoll kunde på så vis förbli utan
  en enda identifierad talare.
- Samma talarradslucka fanns även med andra mellantecken framför
  kolon: ett statustillägg inom parentes („Bauer (Vorsitz): …", „Bauer
  (abwesend): …"), en klockslag inom hakparenteser („Bauer [14:32]:
  …") och ett fotnotstecken omedelbart vid namnet („Bauer*: …"). Även
  här förblev talaren helt oidentifierad, så snart efternamnet
  samtidigt var ett vanligt ord.
- Stod en redan identifierad person i ett bifogat protokoll- eller
  loggutdrag i samma meddelande (till exempel ett supportärende)
  dessutom som användarnamn i formen „vorname.nachname" – gement,
  utan mellanslag, förbundet med en punkt –, förblev detta klarnamn
  läsbart, trots att samma namn i följebrevet redan var maskerat.
- Samma användarnamnslucka fanns även med ett understreck i stället
  för en punkt („vorname_nachname") – ett likaledes vanligt format i
  protokoll- och loggutdrag.
- Och även i omvänd ordning förblev användarnamnet läsbart
  („nachname.vorname" respektive „nachname_vorname") – vissa system
  sätter efternamnet före i loggens användarnamn i stället för efter.
- Ett dödsdatum identifierades inte, om ingen annan uppgift stod bredvid
  („Herr Bauer ist am 12.03.1985 verstorben") – för det fanns tidigare
  ingen egen igenkänning alls, och det generiska datumet fungerar inte
  vid denna standardtröskel.
- Ett dödsdatum identifierades inte heller, om meningen använde
  verbformen i stället för particip („Frau Meier verstarb am
  12.03.1985", „Er starb am 12.03.1985") – bara „ist … verstorben"/„ist
  … gestorben" fungerade tidigare.
- Ett bröllopsdatum identifierades inte, oavsett i vilken form det
  stod („Eheschließung am 12.03.2010", „Hochzeitsdatum: 12.03.2010",
  „Herr und Frau Bauer heirateten am 12.03.2010") – för det fanns
  tidigare ingen egen igenkänning alls, och det generiska datumet
  fungerar inte vid denna standardtröskel.

- **I efterbearbetningseditorn kunde en andra ram över en just insatt
  platshållare lämna en röd teckenrest kvar**, till exempel „[G" i
  stället för „[BEG1]" – utan någon varning, för resten hörde inte
  längre till den konfidentiella uppgiften (den var redan borttagen i
  det första draget), utan bara till den egna platshållaren. Orsaken
  var färgsättningen: en nyinsatt platshållare skrevs teckenvis till
  filen, även vid enfärgat förval – en senare ram över samma ställe
  hittade därigenom ingen sammanhängande ordalydelse att lokalisera sig
  mot. Nu står en enfärgad platshållare som ett stycke i strömmen, som
  den automatiska rensningen alltid gjort; bara en riktig toning eller
  regnbågstext behöver fortfarande enskilda tecken. Det inbyggda
  kontrollprovet identifierar en sådan rest dessutom nu även när
  platshållarens exakta teckensträng inte längre förekommer.
- En numrerad namnlista med stegvis strukturnummer („1.1 Max
  Mustermann", „1.2 Huber Franz" …) förlorade alla namn till samma
  broms som egentligen bara ska skydda riktiga strukturer och
  positionslistor – utan kolumnhuvud ovanför listan fanns inget
  vittne som ett namn kunde räddas mot.
- Ett namn i en engelskspråkig inloggningsrad i en systemlogg
  („Accepted password for Max Mustermann from 10.0.0.5 port 51000
  ssh2") identifierades inte – den tyska språkmodellen hittade det bara
  om „invalid user" stod framför, annars blev det kvar. Sådana
  loggutdrag bifogas ofta oförändrat en incidentrapport. Namn bakom
  „for" framför en IP-adress identifieras nu tillförlitligt.
- Namnet på den betalningsskyldige i SEPA-mandatreferensen i ett
  kontoutdrag eller bokföringsjournal (t.ex. „MREF+Mustermann
  Klaus+SVWZ+Miete August") förblev öppet – inget mellanslag, ingen
  satsstruktur, bara med „+" avgränsade versalfält, och i den där
  vanliga ordningen „efternamn förnamn" hittade igenkänningen det
  inte heller av en slump. Identifieras nu.
- Gatan tillsammans med husnumret på den första raden i en adresstabell
  (t.ex. „Nachname | Vorname | Straße | PLZ | Ort") förblev öppen –
  språkmodellen gissade där en felaktig, men längre ort tvärs över
  flera kolumner, och den trängde undan den riktiga, kortare
  adressträffen. Identifieras nu.
- Samma läcka uppstod med en tabb i stället för „|" eller „;" som
  kolumnavgränsare – där försvann adressen till och med helt i stället
  för att bara förloras delvis. Identifieras nu.
- En gata med husnummer förblev öppen, om ett postnummer med komma
  följde direkt efter utan mellanslag (t.ex. „Bahnhofstrasse
  12,80331 München", som i en kommaavgränsad tabellkolumn) – kommat
  såg ut som en decimal i en mängd, och gatan gällde därför alls inte
  som adress för mönstret. Identifieras nu.
- En gata med husnummer förblev öppen, om ortprefixet „St." (Sankt)
  följde direkt efter utan komma (t.ex. „Hauptstraße 5 St. Pölten",
  ett brevhuvud utan föregående postnummer) – „St." såg ut som
  styckenhetens förkortning, och gatan gällde därför alls inte som
  adress för mönstret. Identifieras nu.
- Ett dörr-/trapphustillägg efter ett husnummer (t.ex. „Lerchenfelder
  Gürtel 43/12") förblev synligt öppet, om direkt efter en enskild
  bokstav stod som av en slump sammanföll med en måttenhet (t.ex. „h"
  för timme) – adressen rensades då bara fram till husnumret utan sitt
  tillägg, i stället för att träffas fullständigt eller inte alls.
- En ämnesrad med ett yrkesnamnlikt efternamn framför förnamnet
  („Betreff: Bauer Anna", „Betreff: Bauer, Anna") förblev tidigare helt
  oidentifierad – även mitt i dokumentet med en fullständig mening
  framför. Identifieras nu.
- Ett tyskt skattenummer med mellanslag, punkt eller bindestreck
  mellan blocken (t.ex. „Steuernummer: 30 815 08153" eller
  „30.815.08153") förblev tidigare oidentifierat – bara skrivsättet med
  snedstreck hittades. Identifieras nu.
- Ett namn bakom en medicinsk fältbeteckning („Patient:", „Hausarzt:",
  „Behandelnder Arzt:", „Überweisender Arzt:" och deras kvinnliga
  former) förblev tidigare oidentifierat, om efternamnet samtidigt var
  ett vanligt tyskt ord (t.ex. „Patient: Bauer Thomas"). Identifieras
  nu.
- Ett namn bakom fältbeteckningen „Zahnarzt" på egen rad (t.ex.
  „Zahnarzt", därunder „Huber Franz") förblev tidigare oidentifierat –
  varken för- eller efternamn. „Zahnärztin" och den enkla
  „Arzt"-formen var inte berörda av detta. Identifieras nu.
- Ett efternamn bakom „Herr"/„Frau", följt av en byråkratisk fras som
  „zur Kenntnisnahme", „zur Unterschrift" eller „zur Weiterleitung",
  fångades tidigare för brett och drog med sig frasen in i namnträffen
  – ur „Frau Petra Klein zur Vertretung in allen Angelegenheiten"
  ersattes „Petra Klein zur Vertretung", och resten av meningen förblev
  grammatiskt stympad. Riktiga adelspredikat som „von der Leyen" eller
  „zu Guttenberg" berörs inte av detta.
- Samma byråkratifras-överredigering satt även bakom namnet i en
  e-post-„To:"-huvudrad, en registreringskod (C.1/C.1.1/C.1.2), en
  körkortskod, ett hakparenteserat formulärfält („[Vorname]: …") och en
  opunkterad hälsningsfras – överallt där drog „zur"/„von" med flera med
  sig en efterföljande fras som „zur Unterschrift" eller „zur
  Vertretung" in i träffen, delvis blev till och med det nakna
  partikelordet självt kvar som namnrest i resultatet. Även här
  bevaras riktiga adelspredikat fullständigt.
- Matrikelnumret bakom sin beteckning identifierades tidigare inte
  alls – „Matrikelnummer 7654321" föll helt genom igenkänningen,
  varken som identifieringsnummer eller via språkmodellen, eftersom
  talet ensamt inte bär en identifierbar form.
- Detsamma gällde deltagarnumret – „Teilnehmernummer 4471829" föll
  helt igenom, varken som identifieringsnummer eller via
  språkmodellen.
- I CV:t föll namnet under avsnittsrubriken „Persönliche Daten" ofta
  helt eller delvis igenom igenkänningen, om det utan tilltalsform
  stod direkt under i formen „efternamn förnamn".
- Detsamma gällde avsnittsrubriken „Kontaktdaten" – där föll namnet
  till och med helt igenom, inte bara delvis.
- I ett registreringsintyg eller en ansökningslista med en
  sammanslagen kolumn „Name, Vorname" (folkbokföringsskrivsätt, värde
  t.ex. „Mustermann, Max" i en cell) föll namnet helt igenom
  igenkänningen, om ytterligare en kolumn som födelsedatumet följde.
- Ett födelsedatum i den på ID-kort och registreringsintyg vanliga
  formen „Geburtsdatum/-ort: 22.07.1978 / Rostock" identifierades
  inte – bara kommaformen „Geburtsdatum, Geburtsort: …" fungerade.
- „Bürgerservice" och „Bürgerbüro" maskerades ibland felaktigt som
  ort, särskilt efter ett tankstreck som uppräkningsavgränsare (till
  exempel „Wenden Sie sich an das Bürgerservice – Bürgerbüro …").
- Ett betecknat telefonnummer som delades mitt itu av en radbrytning
  (till exempel från en smal brevhuvudskolumn eller ett
  PDF-textutdrag vid kolumnbredden: „Telefon: 0176 12\n34567")
  maskerades delvis bara till hälften – resten bakom radbrytningen
  förblev läsbar.
- Ett betecknat identifieringsnummer (kund-, medlems-, avtalsnummer
  och liknande) som delades mitt itu av en radbrytning (till exempel
  „Kundennummer: K903\n944" ur en smal kolumn) maskerades bara till
  hälften – resten bakom radbrytningen förblev läsbar.
- Ett namn med akademisk titel framför en yrkesbeteckning efter komma
  (till exempel „Dipl.-Ing. Sabine Roth, Projektleiterin") förblev helt
  oskyddat – raden såg ut som ett tabellariskt kolumnhuvud och
  förkastades felaktigt som sakinnehåll.
- Titeln „Dr.-Ing." (en vanlig tysk ingenjörsgrad) framför ett namn
  togs inte med i det maskerade personvärdet och förblev läsbar –
  samma bindestrecksfälla som vid „Dipl.-Ing.".
- Titlarna „Dipl.-Kfm.", „Dipl.-Kffr." och „Dipl.-Psych."
  (diplomekonom/diplompsykolog) framför ett namn togs inte med i det
  maskerade personvärdet och förblev läsbara – samma
  bindestrecksfälla som vid „Dipl.-Ing." och „Dr.-Ing.".
- En MAC-adress i Cisco-skrivsättet med punkter i stället för kolon
  (t.ex. „aabb.ccdd.eeff", som switchprotokoll och supportärenden
  visar) identifierades inte alls och förblev läsbar.
- Ett efternamn bakom „Familie" (t.ex. „Die Familie Gruber
  unterschreibt den Vertrag") förblev beroende på satsbyggnad
  oidentifierat och därmed läsbart – även med adelspredikat framför
  („Familie von der Leyen").

- Vid en kroatisk adress utan avgränsande skiljetecken mellan
  postnummer+ort och gata+husnummer (t.ex. „10000 Zagreb Ulica Ivana
  Lučića 5") förblev husnumret orensat.

- Vid en litauisk kontaktuppgift med beteckningen „Kontaktinis asmuo"
  (t.ex. „Kontaktinis asmuo: Vilkas Jonas") förblev efternamnet
  oidentifierat, om det samtidigt var ett vanligt substantiv (Vilkas =
  „varg", Vanagas = „hök").

- Ett födelse- eller bosättningsland utan ytterligare beteckning i ett
  danskt formulärfält (t.ex. „Fødeland: Tyskland" eller „Bopæl:
  Tyskland") identifierades inte.

- Ett födelse- eller bosättningsland utan ytterligare beteckning i ett
  rumänskt formulärfält (t.ex. „Țara: Germania" eller „Țara de
  reședință: Franța") identifierades inte.

- Ett företagsnamn under den litauiska fältbeteckningen „Darbdavys:"
  eller „Įmonės pavadinimas:" (arbetsgivare/företag) identifierades
  inte.

- Ett företagsnamn under den ryska fältbeteckningen „Работодатель:"
  eller „Наименование организации:" (arbetsgivare/företag)
  identifierades inte.

- Ett utskrivet datum med rumänskt månadsnamn (t.ex. „31 decembrie
  2024") identifierades inte.

- Ett ungerskt ursprungligt namn bakom förkortningen „szül." (t.ex.
  „Nagy Éva (szül. Kovács)") identifierades inte och förblev öppet
  läsbart.

- En sparad HTML-profilsida (eller ett e-postmeddelande med bifogad
  webbsida) kunde lämna det medborgerliga namnet orensat, om det bara
  stod i Open Graph-profilfälten
  `profile:first_name`/`profile:last_name`/`profile:username` – dessa
  bär namnet uppdelat i stället för beskrivande som `og:title` och
  rensas nu likaså.

- Ett leveransfel-meddelande (bounce/NDR) bar ofta huvudraderna för det
  ursprungligen icke levererbara mejlet (avsändare, mottagare, ämne) i
  en egen, tredje bilagedel – denna förblev i den rensade versionen
  helt orörd. Delen rensas nu som den övriga leveransrapporten.

- Den individuellt namngivna redigeraren av ett skyddat område i Word
  (Begränsa redigering → Undantag, `w:permStart`) förblev i klartext,
  även när samma namn i löptexten länge var rensat. Det tas nu bort
  likaså.

## 0.10.42-alpha.20260827 – 27 augusti 2026

### Nytt

- **Namngivna igenkänningsprofiler gör olika arbetsfall nåbara med ett
  grepp.** Under *Inställningar → Igenkänning → Vad som tas bort* går det
  att spara det aktuella kategori- och typvalet och tillämpa det igen
  direkt via ett listval. Standardprofilen *Standard* motsvarar det
  tidigare leveransläget och kan inte tas bort. En profil ändrar
  uteslutande vad som tas bort; språk, utmatningsart, igenkänningsdjup
  samt egna termer och sökmönster berörs inte.

- **Typen av resultat väljs nu direkt före rensningen.** Ett gemensamt
  valfält i huvudfönstret bestämmer för hela bunten om Maskuro sätter in
  läsbara platshållare, maskerar eller tar bort utan ersättning. De två
  separata fälten för PDF och Office i inställningsfönstret har utgått;
  därigenom syns det viktiga beslutet, och det kan inte längre glida isär
  omedvetet vid blandade buntar. Den guidade rundturen förklarar det nya
  valet före första rensningen.

- **Teman och vattenstämplar markerar färdiga PDF-filer tydligt på
  begäran.** Tolv helhetslooker samordnar ersättningstexter och
  maskeringsytor; nya bland dem är Pride samt vår, sommar, höst och
  vinter. *Geheimakte* ger direkt ett diagonalt `TOP SECRET`. Oberoende av
  det går det att välja en fri markeringstext eller en egen bild, ikon
  respektive SVG med färg och opacitet. Importerad grafik bäddas in utan
  sin metadata och förblir tillgänglig om källfilen flyttas. Vid
  efterbearbetning ersätter Maskuro sin tidigare vattenstämpel, i stället
  för att lägga flera ovanpå varandra. Textvattenstämplar ritas som det
  sista PDF-skiktet med ljus kontur, så att de förblir synliga även på
  mörka bilder och tät text. Efterbearbetningseditorn ignorerar Maskuros
  vattenstämpel helt och erbjuder inte längre dess text som
  maskeringskandidat.

- **Egna utmatningsteman kan sparas och delas.** Den aktuella blandningen
  av ersättningstext, maskering och vattenstämpel får ett namn, finns
  kvar i inställningarna och kan exporteras eller importeras som
  klartextfritt JSON. Den svartvita utskriftsförhandsvisningen varnar för
  svaga kontraster; valfri firandekonfetti förblir rent kosmetisk i
  gränssnittet.

- **Ett sista exportprov och en förklarande kontrollrunda avslutar
  utformningsomgången.** Före det slutgiltiga sparandet jämför Maskuro
  varje värdesäkert känt PDF-ställe ännu en gång i textskiktet och
  renderade bildpunkter; varningar nämner uteslutande sida och
  koordinater. I editorn visar *Varför är detta dolt?* kategori,
  igenkänningsväg och säkerhetsmarginal, aldrig den borttagna klartexten
  och aldrig i slutdokumentet.

- **Maskeringsstreck får nu vara vackra.** Under *Inställningar →
  Utseende* finns färgförval, fria färgväljare, toningar, regnbåge,
  ränder, prickar, blommor, stjärnor, hjärtan, tassar, moln, blixtar,
  kaffebönor, ankor, solar, löv, snöflingor, papper-, textmarkör-, tejp-
  och reproducerbara slumpmönster samt direkt förhandsvisning.
  Ersättningstexter kan valfritt få en färg, en toning, en regnbåge, en
  pill eller en etikett. Kategorifärger skiljer namn, adresser, kontakter
  och medicinska uppgifter åt. PDF övertar hela utformningen; Word,
  PowerPoint, OpenDocument och HTML använder den valda heltäckande
  grundfärgen. Skyddet ändras inte av det: Maskuro tar bort det
  konfidentiella innehållet först och ritar färg eller mönster först på
  det tomma stället.

- **Maskuro finns åter för Linux – som AppImage, DEB, RPM och portabelt
  arkiv.** DEB och RPM för in programpost, filkopplingar, terminalkommando
  och ikon i systemet; AppImage körs utan installation. Uppdateringar
  förblir vid en befintlig DEB- eller RPM-installation i samma
  paketformat och föredrar annars AppImage.

- **Synkontrollen förelägger inte längre vanlig PDF-text en andra gång
  som nya träffar.** Den avslutande OCR-blicken och den säkra ombyggnaden
  av de synliga sidorna förblir helt aktiva; som ny fyndkälla räknas i
  förvalet dock bara områden som sidtext och enbildskontroll ännu inte
  läst. Därigenom blir produktrader inte till nya namn eller företag bara
  på grund av en avvikande andra OCR-läsning. Den som fortsatt vill ha två
  oberoende bedömningar av hela den synliga texten slår på
  *Kontrollera hela den synliga PDF-sidan igen för uppgifter* i
  inställningarna.

- **PDF-filer kan visas löpande, blad för blad eller som uppslag.** Tre
  kompakta visningsikoner sitter längst ner direkt bredvid „Bredd" och
  „Sida". Löpande rullar vid bladkanten till nästa sida; enkelsida håller
  mushjulet på det aktuella bladet; uppslag visar ett uppslag, gör det
  anklickade bladet redigerbart och flyttar Fram/Tillbaka ett helt
  uppslag. Sidminiatyrer och jämförelselupp öppnar dessutom i en märkbart
  smalare vänster grundkolumn och lämnar mer plats åt arbetssidan.

- **Du ser nu vad KI-nivån har gjort.** Efter varje körning står det under
  „Detaljer" per fil en rad om det – „KI-nivå: 12 gränsfall kontrollerade,
  3 förkastade" – och även när den inte hittade något att ändra står det
  där. Tidigare teg den dyraste nivån helt: om den ens tillfrågades gick
  inte att se utifrån.

  Den som behöver mer detaljer slår under „Inställningar → KI" på
  *Skriv upp varje KI-fråga i loggen*. Då noterar loggfilen per fråga
  storlek, varaktighet och antal fynd, dessutom väntetiden orsakad av en
  mängdgräns hos motparten. Knappen „Visa loggfil" bredvid öppnar mappen –
  den ligger i programdatakatalogen, som på Windows är dold och som
  ingen hittar av sig själv. I filen står uteslutande storlekar, aldrig
  text ur dina dokument.

- **Maskuro känner igen när din KI-tjänst begränsar antalet
  förfrågningar.** Hostade tjänster tillåter ofta bara några få
  förfrågningar per minut – fyra är ingen ovanlighet. De överskjutande
  avvisas inte, utan får vänta, och av två sekunder per svar blir det
  fyrtio. Det såg tidigare ut som att modellen var långsam. Nu läser
  Maskuro gränsen ur tjänstens svar, skickar inte fler frågor samtidigt
  än vad som antas, nämner gränsen under „Kontrollera anslutning" och
  räknar in den i varaktighetsuppskattningen.

- **Sidvisningen använder ditt Word, Excel och PowerPoint – och är
  därmed cirka sex gånger snabbare.** Tidigare krävde den LibreOffice, som
  finns på färre kontorsdatorer; den som saknade det såg en knapp som
  krävde en främmande installation. Nu gäller: är Microsoft Office
  installerat, används det automatiskt – utan installation, utan
  nedladdning, utan att du kryssar i något. LibreOffice förblir den andra
  vägen och för OpenDocument-filer till och med den första; misslyckas
  den ena provas den andra.

  Skillnaden märks framför allt under arbetet: efter varje ersättning
  sätts sidan om, och det kostar via Office cirka en halv sekund i
  stället för tre. Den första visningen av ett dokument tar fortfarande
  några sekunder, därefter följer den dina handgrepp utan väntetid.

  Ditt eget öppna Word rörs inte vid det: Maskuro startar en egen, osynlig
  session, öppnar filen bara läsande, stänger av makron och avslutar allt
  igen så snart efterbearbetningsfönstret stängs. Lösenordsskyddade filer
  avvisas i stället för att fastna i en osynlig dialog.

- **Förstainställningen frågar nu även om ansikten, koder och
  underskrifter – och laddar allt som saknas i ett svep.** Bredvid den
  utökade igenkänningen står på första sidan de tre bildbrytarna: göra
  ansiktsområden okännbara, göra streck- och QR-koder okännbara,
  maskera handskrivna underskrifter på PDF-sidor. PDF-gränsen står synligt
  vid bocken; Office-filer genomsöks inte automatiskt efter
  underskrifter. Under bockarna står hur många megabyte klicket på
  „Vidare" kostar. Nedladdning sker därefter i **ett** fönster med
  **en** förloppsindikator för allt tillsammans, i stället för i flera
  dialoger efter varandra; ett avbrott avslutar hela förloppet och lämnar
  inget halvfärdigt kvar. Den som inte vill ha något av det tar bort
  bockarna – då laddas inget heller.

- **Förhandsvisningen kan glesas ut efter kontrollbehov och fällas ihop
  per typ.** Ovanför listan sitter ett reglage *Dölj väl belagda*: ju
  längre åt höger det står, desto mer döljer det från grönt mot rött; helt
  till höger står bara kvar det programmet på egen hand gissat. Ett klick
  på en typs rubrik fäller ihop den. Båda är läshjälpmedel, inget urval –
  vad som döljs eller fälls ihop förblir ibockat och ersätts; hur många
  värden det just nu är står under reglaget. Vid korta listor visas
  reglaget inte. Omkopplingen till två spalter håller nu dessutom även
  brytarna *aldrig igen*.

- **Bildlistan kan öppna sig själv före varje körning.** Den som vill
  besluta om varje bild för sig sätter under „Bilder" den nya bocken
  *Fastställ enskilt före varje körning*. Listan med förhandsvisning visas
  då av sig själv vid rensning, i stället för att du varje gång klickar på
  „Fastställ enskilt …" själv; avbryter du den, rensas det inte heller.
  Innehåller ingen av de valda filerna någon bild, visas inget.
  Förinställt är bocken av.
- **Maskuro hittar handskrivna underskrifter på PDF-sidor och tar bort
  dem ur bildpunkterna.** Tidigare blev namnteckningen kvar under ett
  rensat dokument – textigenkänningen läser tryckt stil, och det den
  inte läser ersätts inte. Sökningen är en egen brytare och behöver en
  igenkänningsmodell som laddas ned en gång.

  Den hittar uppmätt cirka 84 av 100 underskrifter och täcker dem till
  ungefär fyra femtedelar. Det är en hjälp och inget löfte: efter varje
  körning står det i rapporten hur många som hittades – även när det inte
  var någon, eftersom det kan betyda att ingen fanns eller att en
  förbisågs. På 72 riktiga affärssidor utan underskrift har den inte
  hittat på någon.

  En **ritad** underskrift hittas men tas inte bort: den består av
  linjer, inte av bildpunkter, och ett streck ovanpå vore bara en
  övertäckning under vilken linjerna blir kvar. Sådana ställen räknas och
  nämns, så att man kan maskera dem själv i
  efterbearbetningsfönstret.

  Word-, Excel-, PowerPoint- och OpenDocument-filer genomsöks inte
  automatiskt efter underskrifter. Gränssnitt, förstainställning,
  modellnedladdning, kommandorad och handbok nämner nu denna gräns
  uttryckligen.

- **Rundturen leder nu även genom förhandsvisningen – fönstret där du
  bestämmer.** Vid övningsdokumentet öppnas den av sig själv, även om du
  annars stängt av förhandsvisningen (din inställning förblir som den
  är). Det förklaras vad färgerna betyder, varför bara en fråga står på
  varje rad – finns det överhuvudtaget en person här? – och vad „aldrig
  igen" är bra för. Vid färgerna riktas strålkastarljuset på en väl
  belagd rad, oftast IBAN – det gröna exemplet som meningen nämner;
  därefter på den svagast belagda, och där får du klicka själv mitt i
  förklaringen: bort med bocken, värdet stannar kvar i dokumentet. Vid en
  lång lista öppnas fönstret större för guidningen, så att förklaringen
  inte ligger på raderna. Öppnas fönstret en andra gång, säger rundturen
  också varför – den färdiga sidan läses en gång till som bild, och
  därvid uppstår fragment som ser ut som ett namn.

- **Editorn öppnas stort första gången.** Original, resultat,
  verktygsfält och träfflista står bredvid varandra och hade för lite
  plats i den tidigare grundstorleken. Den som drar fönstret mindre får
  sin storlek tillbaka nästa gång – ingen körs över.

- **Ett dubbelklick på en platshållare hämtar den tillbaka** – i Word,
  Excel, PowerPoint, OpenDocument, text, e-post och HTML. Och den som drar
  över flera platshållare och väljer „Hämta tillbaka urval" hämtar alla
  som ligger i det på en gång. Man behöver alltså inte längre träffa
  hakparentesen exakt. Platshållare som vid anonymisering står för flera
  olika värden är undantagna från detta – de räknas och nämns, gissas
  inte.

- **Handboken har ett kapitel „Förhandsvisning före ersättning".**
  Fönstret är förinställt på och är det enda där du bestämmer – i
  handboken stod det tidigare bara i en bisats. Nu står det där vad en
  bock betyder (den gäller **varje** fyndställe, inte bara det
  uppräknade), varför bara en fråga ska besvaras per rad, vad „aldrig
  igen" varaktigt medför, och varför fönstret vid ett PDF kan öppnas en
  andra gång. På alla arton språk, och i listan över inställningar är
  brytaren nu också upptagen.

### Ändrat

- **Facket „Ersatta värden" har ett reglage över färgerna, och
  inlärningsläget finns inte längre där.** Vid mer än åtta värden sitter
  ovanför listan samma reglage som i förhandsvisningsfönstret: *Dölj väl
  belagda* glesar ut vyn till det som verkligen behöver ses över. På
  dokumentet ändrar det ingenting, och hur många rader av hur många som
  visas står nedanför – sökfält och reglage räknas tillsammans. Bocken
  *Inlärningsläge* har försvunnit från facket; den finns kvar i menyn
  *Verktyg* och i verktygsfältet.

- **Facket „Ersatta värden" visar nu samma färger som dokumentet.** Varje
  rad i det är bakgrundsfärgad likt stället i dokumentet och likt värdet
  i förhandsvisningen: rött betyder „ensam gissning, här lönar sig den
  andra blicken först", grönt „identifierad av ett namngivet mönster".
  Inom varje typ står det osäkraste överst – du arbetar alltså igenom
  listan uppifrån och ned och har sett det viktigaste först. Tidigare
  stod allt lika ljust och sorterat alfabetiskt.

- **Inlärningsläget är fabriksmässigt av.** Efter en rättelse i
  efterbearbetningsfönstret frågade programmet tidigare av sig själv om
  det skulle bli en egen regel. Den frågan kommer mitt i arbetet; den som
  inte beställt den upplever den som ett avbrott. Den som vill ha
  reglerna slår på knappen *Inlärningsläge* i verktygsfältet – valet
  gäller sedan varaktigt, i båda riktningarna.

### Rättat

- **Exporterade regelfiler markeras nu uttryckligen som skyddsvärda.**
  Egna termer och undantag kan stå i klartext i dem; dessutom kan filen
  innehålla hashsaltet som används för att bekräfta antagna värden. Den
  lyckade exporten visar därför en varningstext och uppmanar till att
  skydda filen och bara medvetet lämna den vidare till behöriga
  mottagare.

- **Den sista säkerhetskontrollen håller inte längre kvar rensade
  kontorsfiler på grund av sina egna platshållare.** En typförkortning
  som „SVNR" står även i `[SVNR1]`; tidigare gällde det som en påstådd
  klartextrest och den färdiga filen förkastades. Samtidigt dras nu
  telefonnummer och IBAN-nummer med även där Office lagrar samma uppgift
  utan synliga mellanslag i en referens eller en inbäddad fil.

- **Word, Excel, PowerPoint och OpenDocument lämnar inte längre kvar
  någon sent upptäckt fältkopia.** Identifieras ett värde först i en
  delförvaring eller inbäddad kontorsfil, städar en tät efterbevakning
  även upp de tidigare lästa synliga och dolda kopiorna. Redan skapade
  referensplatshållare ersätts inte en gång till av detta.

- **Vid enskild återhämtning av en Word-urvalslista följer inte längre
  ett angränsande urval med ombett.** Hela originalstycket övertas
  först när även dess attribut inte längre innehåller öppna
  platshållare.

- **Dåligt läsbara skanningar förlorar färre samhörande uppgifter.** En
  alternativ OCR-läsning med tilltalsform och tvådelat namn bevaras;
  gatufragment, husnummer och postnummer-ort skyddar tillsammans hela
  adressraden, även om den sönderfaller i intilliggande OCR-block.
  Faktura- och artikelfält samt evenemangsrader bredvid tas inte med av
  detta. Ett efter „född" i flera OCR-ord och skiljetecken sönderfallet
  giltigt datum görs likaså helt okännbart.

- **Firandekonfettin syns nu vid automatisk öppning av editorn.**
  Konfettibitarna sprutar direkt från *Rensa*-knappen i stället för att
  regna från fönstrets övre kant. Editorn väntar bara på den första,
  850 millisekunder korta sprutstöten och öppnas därefter automatiskt;
  utan aktiverad konfetti finns fortfarande ingen fördröjning.

- **Sidräknare och zoomfält hoppar inte längre fram och tillbaka vid
  överfarande av visningsikonerna.** Qt fördelade om statusradens lediga
  utrymme så snart en symbols hänvisning visades där. Båda
  hanteringsgrupperna behåller nu vid hover sin naturliga bredd och fasta
  position.

- **Hastighetsmätningen av en ansluten KI-server misslyckades alltid** –
  på varje server, sedan den egna KI:n finns. Den frågade med en snäv
  svarsgräns och försökte sedan läsa det därigenom avkortade svaret; det
  var dömt att misslyckas, och lagrat blev „inte mätt". Följderna syntes
  överallt: varaktighetsuppskattningen räknade din server med hastigheten
  hos den medföljande modellen på en kontorsdator, och i inställningarna
  stod det ständigt att hastigheten ännu inte mätts. Nu mäts det utifrån
  den mängd servern har skapat, och inte utifrån innehållet i dess svar.

- **„Maximal igenkänning (KI) – långsam" stod kvar även när det inte
  stämde.** Beteckning och hänvisning beskrev den medföljande modellen på
  en kontorsdator – „en språkmodell på denna dator", „vid stora dokument
  upp till en timme". Den som anslutit en egen KI-server läste där två
  felaktiga saker: beräkningen sker inte på hans dator, och svaret kommer
  på sekunder i stället för timmar. Båda kommer nu från mätningen. Finns
  ingen sådan, påstår programmet inget längre, utan säger att det ännu
  inte har mätts.

- **Återhämtning verkar nu även på ett draget urval.** Den som drog över
  flera platshållare och ville trycka *Hämta tillbaka urval* fann knappen
  grå: den aktiverades bara om markeringen var **exakt** en platshållare
  – dragen över ett stycke är den det aldrig. Vägen dit fanns redan, bara
  ingen nådde dit. Nu räcker det att markera området; alla platshållare i
  det kommer tillbaka på en gång.

- **Återhämtning kraschade när jämförelseluppen var öppen.** Luppen
  kommer ihåg stället under muspekaren för att följa med i originalet.
  Vid omladdning efter en återtagning gav den tillbaka det stället i en
  form som textvyn inte kunde hantera – och eftersom ett sådant fel mitt
  i gränssnittet avslutar programmet, hade en återtagning blivit en
  krasch. Luppen står öppen i grundläget, det drabbade alltså den vanliga
  vägen.

- **Efter återhämtning hoppar inte längre vyn till dokumentets början.**
  I ett längre dokument försvann efter varje handgrepp stället där man
  just arbetade. Nu förblir stycket kvar överst som stod överst innan.

- **Utan LibreOffice säger sidvisningen varifrån det kommer, i stället för
  att bara saknas.** De båda knapparna *Sidvisning* och *Maskera som PDF*
  var spärrade och nämnde i tooltipen bara att inget LibreOffice
  hittades; en väg dit fanns ingenstans i programmet. Ett klick öppnar nu
  en hänvisning med vägen till det kostnadsfria, öppna LibreOffice.
  Handbok och FAQ stod fel på denna punkt – de aviserade en byggsten för
  nedladdning som programmet inte erbjuder.

- **Före leverans genomsöks den färdiga filen ett sista gång helt – nu
  även för Word, Excel, PowerPoint, LibreOffice, e-post, HTML och text.**
  Tidigare hade bara PDF-filen denna sista blick. Alla kontroller
  dessförinnan tittar på ett ställe som någon namngett i förväg; en
  förvaring som ingen tänkt på kontrolleras därför inte heller av någon.
  Till sist genomsöks nu den skrivna filen ospecifikt efter allt som
  ersatts – överallt utom i sidtexten, där samma ordalydelse också får
  förekomma tillåtet. Blir något kvar där, uppstår **inget** resultat, och
  meddelandet nämner värdet. Ett dokument som anses rensat är värre än
  inget alls.

- **Namn som står i `<script>` och `<style>` rapporteras nu.** Båda
  förblir fortsatt orörda – där står programtext, och en ersättning mitt
  i en beteckning gör av en webbsida en trasig webbsida. Det sades dock
  inte tidigare, och det var felet: en stilregel `content: "Anna
  Musterfrau"` visas **synligt** på mottagarens skärm, och i resultatet
  stod den kvar, medan programmet meddelade sidan som rensad.

- **I inställningarna går tilläggsmodellerna åter att ladda ned och ta
  bort.** Knappen bredvid „Utökad igenkänning" och „Maximal igenkänning
  (KI)" hamnade vid tryckning i felrapportfönstret, i stället för att
  hämta modellen. Den andra vägen – bocken i igenkänningen som av sig
  själv frågar efter modellen – berördes aldrig av detta.

- **Namn som ligger i blad- och områdesnamn i ett kalkylblad rapporteras
  nu.** Namnet på ett blad står på fliken nedtill, namnet på ett namngivet
  område i namnfältet och i varje formel som använder det. Ersatta blir
  båda fortfarande inte – formler refererar via dem, och en arbetsbok med
  referensfel hjälper ingen – men det står nu där. Tidigare kom meddelandet
  bara för bladnamnet i en Excel-arbetsbok: ett namngivet område
  „Bezuege_Brunnthaler" gick tyst med ut, och i ett LibreOffice-kalkylblad
  teg programmet helt. Ett blad „Notizen Ortner" gällde därmed som rensat,
  och mottagarens första blick föll på namnet.

  Rapporterat blir bara det som verkligen leder till en person: ett ord
  som ändå ersatts i samma arbetsbok, eller en träff som väljer ut ett av
  flera ord. Ett fristående ord som „Zustaendig" eller „Bezug_Umsatz"
  utlöser ingen varning längre – tidigare hade det gjort det, och en
  varning som kommer var annan arbetsbok läser ingen längre efter den
  tredje.

- **„Hämta original" hämtar nu verkligen allt tillbaka.** I vissa dokument
  saknades därefter enstaka tecken – ur „Seestraße 14" blev „Seestraße 4",
  ur „An:" ett „An", ur „nordlicht-planung" ett „nordlicht planung" – och
  enskilda rader kom inte tillbaka alls. Just där gick det därefter inte
  längre att markera något med musen eller maskera något: texten stod
  visserligen på papperet, men programmet kände inte längre till den.
  Berörda var smala tecken – ettan, kolon, bindestrecket – i dokument som
  sätter varje tecken för sig; övningsdokumentet är ett av dem.

- **Och samma dokument förvandlas inte längre till en bild vid
  rensning.** Eftersom ett sådant tecken blev kvar, rapporterade
  efterkontrollen en rest och sidan rastrerades av försiktighet. Texten
  på den var därefter bara en avbild: inte längre sökbar, inte längre
  markerbar, större i filen. Övningsdokumentet förblir nu riktig text på
  båda sidorna.

- **Färgade markeringar blir inte längre kvar över återhämtad text.** Den
  som ångrade en ersättning såg den färgade rektangeln fortfarande över
  det återställda ordet – den påstod „här togs något bort", trots att
  originalet stod där igen.

- **Ett streck avslöjar inte längre hur långt ordet under det var.** Vid
  maskering täcker strecket i korta rader nu **hela** raden –
  adressblock, huvuddata, smal tabellcell. Får hela raden inte plats (den
  vanliga tabellraden med tre kolumner), blir det kvar vid fältet; i en
  löptextrad förblir det ordexakt, annars gjorde ett namn mitt i meningen
  hela meningen svart. Och streck som står under varandra blir **lika
  långa**: i adressblocket står ett värde på varje rad, och tre olika
  långa streck avslöjade fortfarande hur långa raderna var. De växer
  därvid bara så långt som pappret är fritt – framför en grannkolumn
  slutar strecket.

- **„Hela raden" maskerar nu verkligen hela raden.** Tidigare slutade
  strecket vid nästa större lucka – alltså vid slutet av fältet. I
  löptext märktes det inte, där är fältet raden; i huvuddata och tabeller
  desto mer: ur „Name: Anna Musterfrau   Abteilung: Vertrieb" blev ett
  streck som slutade exakt vid namnets sista bokstav – och därmed stod
  dess längd fortfarande på pappret. Strecket löper nu från radens första
  till sista ord och tar med sig grannkolumnerna. Den som bara vill träffa
  värdet väljer „Ord"; automatiken maskerar oförändrat fältvis.

- **Före leverans genomsöks den färdiga filen ett sista gång.** Alla
  tidigare kontroller tittar på ett ställe som någon namngett i förväg –
  sidtext, fyndrektangel, bildyta. Ett PDF-dokument har dock fler
  förvaringar än en uppräkning kan rymma: anmärkningar, formulärvärden,
  bokmärken, dokumentinformation, filbilagor, JavaScript. Till sist
  genomsöker Maskuro därför den skrivna filen ospecifikt efter allt den
  ersatt – överallt utom i sidtexten, där samma ordalydelse också får
  förekomma tillåtet. Blir något kvar där, uppstår **inget** resultat, och
  meddelandet nämner värdet. Ett dokument som anses rensat är värre än
  inget alls.

- **Det som inte gick att kontrollera gäller inte längre som
  kontrollerat.** På tre vägar såg tidigare ett misslyckande i
  efterkontrollen ut som ett rent resultat. En sida vars textskikt inte
  gick att läsa gällde som särskilt ren – där fanns ju inget att hitta;
  den rastreras nu. Gick en sida med kvarvarande fyndställe inte att
  rastrera i stället, levererades den tyst; nu avbryter rensningen
  hellre. Och kontrollprovet i efterbearbetningsfönstret meddelade efter
  ett eget fel „inget kvar" – i fönstret inte att skilja från att allt
  togs bort; nu visas varningen tillsammans med knappen „Rastrera sida".

- **„Återställ till förval" återställde inte de flesta inställningar
  alls.** Nio av tjugotvå bockar stod oförändrade kvar efter handgreppet –
  bland dem förhandsvisningen, „Öppna rensade filer efteråt",
  efterbearbetningsfönstret, den omedelbara sparningen och båda
  uppdateringsbockarna. Den sparade filen var visserligen tömd, men
  fönstret höll fast vid de gamla värdena och skrev in dem igen vid nästa
  klick. Nu kommer varje bock tillbaka, och anteckningen „ändrad"
  försvinner med den.
- **„Spara kontrollrapport per rensning automatiskt" visades ibockad,
  men var av.** Efter återställningen förblev bocken satt medan värdet
  var raderat – ingen rapport skapades längre, utan att något
  antydde det. Detsamma gällde kontrolloggen och den egna
  skärminspelningen; deras tangentbordskortkommando registreras nu vid
  återställning även korrekt på eller av.

- **En rads streck ser nu likadana ut.** Tidigare hade varje fyndställe
  med sig sitt eget streck, och dess höjd kom från teckensnittet hos det
  träffade ordet. På en rad med beteckning och värde i olika storlekar
  stod därför ett tjockt och ett tunt streck med förskjutna kanter bredvid
  varandra, och där bara ett mellanslag skilde två fyndställen åt, blev
  en ljus springa kvar ovanför. Streck på samma rad har nu samma över-
  och underkant, och det som bara skiljs åt av ett mellanslag blir ett
  streck. Vad som ska stå kvar mellan två fyndställen – kommat bakom
  namnet, en beteckning, ett belopp – håller dem fortfarande isär. Gäller
  för satta sidor liksom för skanningar.

- **Flikarna under „Om detta program" börjar åter längst upp.**
  Integritetspolicy, licensvillkor och licenshänvisningar öppnades mitt i
  texten – den som läste dem var tvungen att först rulla helt upp för att
  se den första raden.

- **Pennan öppnar inte längre ett andra editorfönster, utan hämtar det
  befintliga fram.** Tidigare uppstod ett nytt vid varje klick. Fönstret
  har ingen egen post i aktivitetsfältet – den som minimerade det kom
  inte åt det längre och klickade en gång till; vid återställning av
  huvudfönstret kom sedan alla uppsamlade fönster fram på en gång. Nu
  hamnar ytterligare dokument i flikraden på det öppna fönstret, och ett
  dokument som redan står där får ingen andra flik.

- **„Utökad igenkänning" bär inte längre anteckningen „ändrad" så länge
  dess modell saknas.** Den levereras påslagen, men utan den nedladdningsbara
  modellen kan den inte alls vara det – i inställningarna stod raden
  därför på varje nyinställd dator som ändrad, trots att ingen rört den.
  Varför bocken är av säger nu ensam dess beteckning: „Modell ännu inte
  laddad".

- **Introduktionsraden förklarade PDF-duken i office- och textfiler.**
  Där stod „klicka på ett ord för att maskera det" – i en Word-fil
  maskerar dock ett klick ingenting, där markeras och sedan trycks en
  knapp. Den säger nu vad som gäller i respektive vy.
- **Verktygsfältet var i textvyn igensatt med text.** „Ersätt urval",
  „Maskera urval", „Hämta tillbaka urval", „Sidvisning" och „Maskera som
  PDF" står nu som symbol – liksom sina syskon i ett PDF-dokument. Deras
  namn finns kvar i kortinfo och meny.
- **Ctrl+mushjul i jämförelseluppen flyttade inte dess zoomreglage
  med.** Texten blev större, medan reglage och procentsats bredvid
  fortsatte hävda det gamla läget.
- **En uppdaterings installationsprogram kom inte fram i
  förgrunden** – man var tvungen att först klicka på det i
  aktivitetsfältet (bara Windows).
- **En årtalssiffra i radbörjan gällde som österrikiskt postnummer.** I
  ett CV blev „2020 Verkaufsstrategien" en platshållare – hela raden
  försvann. Ett fyrsiffrigt tal mellan 1900 och 2099 behöver nu en andra
  adresssignal: gatan ovanför, ett fältord framför, en landsbeteckning
  eller ett känt ortnamn. Adressblock har det; årtalskolumner inte.
- **Ett månad-år-par gällde som telefonnummer.** Ur „Seit 08.2010
  123-Verkauft GmbH" blev ett „telefonnummer" – månad, år och de första
  siffrorna i företagsnamnet därbakom.
- **Rapporten sa „kontrollerad via textigenkänning" och undanhöll vad
  den inte läser.** Bevaras bilder, står det nu med att handskrivet inte
  hittas i dem – en underskrift eller ett handskrivet infört namn förblir
  kvar. Tidigare stod denna mening bara vid skannade sidor; ett vanligt
  PDF-dokument med en inbäddad underskrift fick inget ord om det.
- **En platshållare på maskerad bildgrund stod vid vänsterkanten av sitt
  streck.** Hittas ett värde i en bild – till exempel ett maskinskrivet
  namn bredvid en inskannad underskrift – måste bildområdet maskeras i
  full bredd. Den kortare platshållaren lämnade naket svart bredvid, vilket
  såg ut som två förlopp. Den sitter nu mitt på strecket.

## 0.10.41-alpha.20260826 – 26 augusti 2026

### Nytt

- **Efter provperioden påminner ett fönster en gång per start om
  licensen.** Det kommer fem minuter efter starten – inte omedelbart, så
  att det inte står i vägen för någon innan första handgreppet – och
  väntar så länge en rensning pågår. Därifrån leder en väg till köp och en
  till registrering av en redan köpt nyckel; „Senare" stänger det så snart
  de fem sekunderna i knappen gått ut. Inget spärras: den kostnadsfria
  nivån fortsätter arbeta som förut.

- **Väntetiden före en körning i den kostnadsfria nivån varar nu tio
  i stället för trettio sekunder.** Den ska påminna om licensen, inte
  stoppa arbetet.

- **Alla tre hänvisningar om licensen ser nu likadana ut.** Väntetid,
  påminnelse under de sista provdagarna och hänvisning efter provperioden
  bär samma rand, samma uppbyggnad och samma knappar; återstående tid står
  därvid i knappen i stället för som en stor siffra bredvid.

- **Träfflistan i förhandsvisningen står åter under varandra.** Den var
  tvåspaltig från nio värden; vid genomgång hoppar ögat då mellan två
  banor, och här avgörs rad för rad. Den som gillar de två banorna slår på
  dem igen längst ner till vänster i fönstret – valet sparas, och vid
  omkoppling förblir redan avmarkerade värden avmarkerade.

- **KI-nivån är öppen för alla som ansluter en egen KI-server.**
  „Inställningar → KI" samlar allt för det: anslutningen, vad KI:n får
  göra, vad den ska göra – och ovanför det brytaren för nivån samt en
  kontrollprövning så snart en server registrerats. En språkmodell som
  räknar med på den egna arbetsplatsen hålls tillbaka: den behöver flera
  minuter för tio sidor och är därmed inget för vardagen.

- **En egen KI kan anslutas.** I stället för den medföljande
  språkmodellen kan en större modell på en annan dator svara – på en
  server i huset eller en arbetsstation med starkt grafikkort. Det krävs
  en tjänst med OpenAI-kompatibelt gränssnitt (Ollama, LM Studio,
  llama.cpp-server, vLLM, LocalAI); den ställs in under
  „Inställningar → Egen KI" tillsammans med en anslutningskontroll som
  verkligen frågar modellen, mäter hastigheten och fastställer det möjliga
  svarsformatet. Flera textavsnitt körs därvid samtidigt i stället för
  efter varandra.

- **Vad KI:n får göra och vad den ska göra går nu att ställa in.** Tre
  brytare avgör gränsfallsprövning, självständig sökning och sökning i
  löptext; anvisningen till modellen står ordagrant där, kan kompletteras
  med egna termer och återställas till förvalet med en knapp.

- **Lämnar texten därvid det egna nätverket, varnas det före varje
  körning.** Maskuro känner på adressen om KI-servern finns i huset och
  nämner en känd leverantör vid namn. Varningen går att stänga av, men
  bara mot uttrycklig bekräftelse att vara behörig till denna överföring,
  och bara för exakt denna adress. Förloppet ändras inte av det:
  överföringen står fortsatt i loggen och i kontrollrapporten för varje
  fil. På kommandoraden frågas det inte, utan stoppas – där krävs
  `--ki-auswaerts-erlauben`.

- **Förhandsvisningen före ersättning är aktiv som standard vid nya
  inställningar och gäller nu även uttryckligen rensat urklippsinnehåll
  samt text och bilder som klistras in i programmet.** Vid
  dokumentbuntar visas fortfarande exakt en förhandsvisning per dokument
  med alla sidor; den tysta direktrensningen av korta kopior öppnar
  medvetet inget fönster.

- **Träffar kan slås av och på i förhandsvisningen över hela den färgade
  raden.** Bocken är nu stor och kontrastrik; dessutom visar ett
  tillståndsfält „Ersätt" respektive överstruket „Ersätt", så att valda
  och avmarkerade värden går att skilja åt omedelbart även på mörka
  konfidensfärger.

- **Även PDF-filer med synlig säkerhetskontroll öppnar
  förhandsvisningen bara en gång per dokument.** Avmarkerade termer
  förblir avmarkerade för det senare sidvittnet; dess kontroll fortsätter
  utan att avbryta samma körning med en andra dialog.

- **Ersättningsord ser likadana ut i efterbearbetningseditorn även på
  rastrerade sidor.** Ligger den röda platshållaren i bildpunkterna i
  stället för i PDF-textskiktet, får den nu ändå samma efter konfidens
  färgade bakgrundsyta som en vanlig PDF-textplatshållare.

- **Redan förhandsvisningen före ersättning visar kontrollbehovet för de
  hittade termerna.** Varje rad bär samma röd–orange–grön-färg som senare
  ersättningen i editorn. Inom en kategori står låg säkerhet och röda
  falsklarmskandidater överst, starka gröna belägg underst; oavgjort
  förblir alfabetiskt. Kommer samma värde från flera fyndställen, räknas
  av försiktighetsskäl deras mest osäkra bedömning. Obedömda specialfall
  står neutralt gula mellan rött och orange.

- **Resultatet kan nu kopieras direkt från efterbearbetningseditorn som
  fil.** „Kopiera resultat" lägger den aktuella rensade versionen i
  urklipp, utan att stänga editorn och söka fram filen igen i
  huvudlistan. Vid en ännu inte sparad handbearbetning körs dessförinnan
  automatiskt hela den säkra sparvägen; „Kopiera bild" finns kvar som en
  separat funktion för rena bildpunkter.

- **Ersatta ord visar i editorn på en blick vad som bör kontrolleras
  först.** Ren språkmodellsgissning är röd, även om spaCy meddelar
  schablonmässigt 85 procent för den. Ytterligare ostödda modellutslag
  förblir högst orange; starka namngivna belägg kan bli gröna. Handarbete
  och äldre tilldelningar utan utvärderingsbar bedömning förblir neutralt
  gula. Även automatiska maskeringsstreck bär dessa färger i
  editorförhandsvisningen – nu även när strecket är en del av en
  rastrerad PDF-sida. För det krävs att tilldelningen stämmer och att den
  tidigare ordrutan bevisligen är heltäckande svart; vanlig fetstil färgas
  inte. I den sparade PDF-filen förblir alla streck oförändrat heltäckande
  svarta.

- **Vad som avmarkeras i förhandsvisningen kan sparas varaktigt.** Där du
  tar bort bocken säger du: här har igenkänningen tagit fel. Tidigare
  gällde det bara för just detta dokument. Nu visas vid raden en brytare
  „aldrig igen"; nedtryckt hamnar värdet varaktigt i listan „Ta aldrig
  bort" och gäller framöver som ofarligt i varje dokument. Under listan
  står vad som blir varaktigt, innan du trycker „Ersätt". Motsatt riktning
  finns medvetet inte: vad som en gång hittats, hittar igenkänningen
  igen.

- **En knapp återställer alla inställningar till leveransläget.** Den
  finns längst ner till vänster i inställningsfönstret och frågar innan.
  Dina filer, din licens, dina egna igenkänningsregler och autostarten
  berörs inte; vad din administration föreskriver gäller fortfarande.
  Varje inställning som avviker från leveransläget bär dessutom
  anteckningen „ändrad" – så syns det på en blick vad man ställt om.

### Ändrat

- **Ett resultat sparas inte längre automatiskt – först vid sparande.**
  En körning från fönstret skriver sin rensade version först till en
  tillfällig plats; filen „…_rensad" bredvid originalet skapas först när
  du trycker „Spara". Fram till dess går resultatet att titta på,
  efterbearbeta och kopiera. Varje färdig rad har för det en sparaknapp,
  under listan står „Spara alla", och i editorn gäller Ctrl+S. Den som
  tömmer listan eller avslutar programmet blir tillfrågad; det ingen
  sparar blir inte liggande någonstans heller. „Visa i mapp" är spärrad
  före sparande – den tillfälliga platsen är inget mål man skickar någon
  till. Tilldelningsfilen följer med vid sparande.

  I inställningarna under „Program" hämtar „Spara resultat direkt bredvid
  originalet" tillbaka det tidigare beteendet. Kommandorad, mappövervakning
  och urklippsövervakare sparar oförändrat direkt – där sitter ingen som
  kunde spara.

- **Efterbearbetningseditorns verktygsfält är uppstädat.** Inlärningsläget
  står nu längst till höger vid jämförelselupp och „Ersatta värden" – de
  tre brytarna som slår på och av ett driftläge står därmed tillsammans.
  „Överför till alla sidor" har flyttats till de tre maskeringsformerna,
  eftersom det bara gör något där. „Kopiera resultat", „Fil – Återställ"
  och „Överför till alla sidor" klarar sig utan text; deras namn står
  fortfarande i tooltip och meny. Mellan „Ersätt" och „Hämta original"
  står ett skiljestreck: de två är motsatta riktningar och såg bredvid
  varandra ut som två varianter av samma verktyg.

- **Symbolen för „Kopiera resultat" visar nu ett dokument.** Två blad med
  vikt hörn och textrader i stället för två identiska blad med en liten
  hörnpil. „Kopiera bild" bär i gengäld bildsymbolen, så att de båda går
  att skilja åt utan text. Knappen „Kopiera" i resultatlistan visar samma
  dokumentsymbol – den sparar samma fil.

- **Inställningarna är sorterade och försedda med rubriker.**
  „Igenkänning" har nu fyra avsnitt: *Vad som tas bort*, *Hur det ersätts*,
  *Hur grundligt det söks* och *Före och efter körningen*.
  Ansiktsigenkänning och streck-/QR-koder står vid bilderna, där man
  letar efter dem; „Program" är delat i *Resultatfiler*, *Vid start*,
  *Uppdatering*, *Visning* och *Återkoppling till oss*, och
  namntillägget för resultatfilen står vid resultatfilerna i stället för
  mellan språk och utseende.

- **Den utökade igenkänningen är fabriksinställd på**, även innan dess
  språkmodell laddats. Tidigare hängde förvalet på modellbeståndet, och
  en nyinställd dator körde varaktigt på den svagare nivån.
  Installationsfönstret erbjuder modellen på första sidan för nedladdning
  och nämner priset bredvid. Saknas den, säger bocken det fortfarande, i
  stället för att låtsas en nivå som inte körs.

- **De två termlistorna heter nu vad de gör:** „Ta alltid bort" i stället
  för „Egna termer" och „Ta aldrig bort" i stället för „Undantag".

- **Förhandsvisningsfönstret är mer överskådligt.** Från nio värden står
  de i två spalter, raderna är lägre, och antalet fyndställen står direkt
  efter termen i stället för vid högerkanten.

- **I efterbearbetningseditorn står Ersätt före Maskera** – i
  verktygsfältet, i menyn „Verktyg" och i högerklicket på sidan. Ersätt
  är standardfallet: en platshållare går att klicka på och hämta
  tillbaka, ett streck inte.

- **Färre dubblerade knappar i editorn.** „Spara som …" och „Kopiera
  bild" står bara kvar i Arkiv-menyn, med sina vanliga
  tangentbordskortkommandon. I fältet finns var och en kvar en gång:
  Spara och „Kopiera resultat" – vart det sparas står ändå i statusraden
  och kan ändras där med ett klick.

- **Urklippsövervakaren erbjuds inte längre vid första start.** Den
  griper in i varje kopieringsförlopp i systemet; den som ser programmet
  för första gången kan inte bedöma det. I inställningarna finns den
  kvar, där med den tillhörande klausulen bredvid.

- **Det ljusa utseendet bländar mindre.** Fönsterbakgrunden kom tidigare
  från respektive systemstil och var därmed den enda stora yta som ingen
  bestämt över – på Windows nästan vit. Nu är den ett brutet vitt, likadant
  på varje system.

- **Rundturen och handboken förklarar färgerna.** Vad rött, orange, grönt
  och gult bakom ett ersatt ord betyder står nu som en egen station i
  rundturen och som ett stycke i handboken – i alla språkversioner.

### Rättat

- **Handboken och FAQ visade platshållare som inte längre finns.** Sedan
  omställningen till den korta formen skriver Maskuro `[NAM1]`; i hjälpen
  stod fortfarande `[NAME1]`, och meningen „Förinställt är `[NAME1]`" var
  därmed helt enkelt felaktig. I de sjutton översatta versionerna stod
  dessutom den **tyska** märkningen i stället för den egna – en spansk
  läsare såg `[NAME1]`, där hans program skriver `[NOMB1]`. Likaså
  ändelsen på resultatfilen: där lovade alla versioner `_bereinigt`,
  medan programmet skapar `_limpiado`, `_nettoyé` eller `_除去済み`.
  Berört var också den nummerlösa formen (vid anonymisering heter allt
  `[NAM]`, inte `[NAME]`) och den ur värdet härledda identifieraren vid
  hashning.

- **Förhandsvisningsfönstret avbryter bara en gång per dokument – och en
  andra gång endast om verkligen något nytt tillkommer.** Ett PDF läses
  ur två håll: en gång ur innehållsströmmen och till sist från den
  renderade, synliga sidan. Tidigare frågade var och en av de båda för
  sig. Nu gäller: vad du avgjort i det första fönstret gäller vidare, och
  värden som redan stod där kommer inte tillbaka. Hittar
  synkontrollen av de färdiga sidorna däremot något som tidigare inte
  stod någonstans, får du det förelagt en gång till – ensamt, utan de
  redan avgjorda värdena.

- **Förhandsvisningsfönstret säger nu vad man ska besluta efter.** I
  stället för „Ta bort bock = värdet blir kvar" – vilket bocken *gör*,
  men inte när man ska ta bort den – står där: bort med bocken överallt
  där det inte finns något personuppgiftsvärde; där har igenkänningen
  tagit fel. Dessutom nämner varje fönster den kontrollkörning som dess
  värden kommer från.

- **Platshållare ser likadana ut i hela dokumentet.** På sidor som byggs
  om som bildsidor i OCR-vägen sattes synliga platshållare tidigare med
  skrivmaskinsstil – „[PLZ4]" stod då brett och med seriffer bredvid ett
  smalt „[NAM1]" på samma sida. De bär nu samma sanserif-typsnitt som
  överallt annars och sätts inte heller bredare än vad som planerades vid
  anpassningen. Det osynliga sökskiktet behåller sitt eget typsnitt – det
  behöver tillförlitliga mått, inget utseende.

- **I editorns verktygsfält finns inga dubbla skiljestreck kvar.** Där en
  hel verktygsgrupp bortfaller för den öppnade filtypen – i ett PDF till
  exempel sidvisning och rendering – blev tidigare båda strecken runt
  luckan kvar.

- **Vid återhämtning blir det inte längre ibland kvar bara en vit
  fläck.** En redan exakt återställd originaltext övermålas inte längre
  vit av den breda, sammanslagna rutan från sin borttagna platshållare.
  Vid blandade text- och bildåterhämtningar sätts text dessutom bara in
  osynligt om sidbilden verkligen redan bär exakt denna originaltext
  synligt. Detta gäller ramar, träffpanel och PDF-bilagor.

- **„Hämta original" erbjuder inte längre onödigt att rastrera sidan.**
  Den stränga resttextkontrollen förblir aktiv vid maskering och
  ersättning. Vid återhämtning hoppas den över: där tillkommer
  originalinnehåll medvetet igen, och oförändrade grannord i den utökade
  återhämtningsramen var inget rensningsfel, utan ett falskt larm.

- **Rundturen genom editorn förklarar nu „Ersätt" och „Hämta original"
  som egna steg.** Båda verktygen framhävs direkt i fältet och beskriver
  att en dragen ram sätter in en platshållare respektive hämtar tillbaka
  det ursprungliga innehållet på det stället från källfilen.

- **Även landsspecifika platshållare förblir nu på högst fyra
  bokstäver.** Dessa typer saknades tidigare i den centrala
  förkortningskatalogen och kunde därför fortfarande visas utskrivna,
  till exempel `[UMSATZSTEUER_ID1]`. Nya körningar skriver i stället
  `[UID1]`; alla automatiskt identifierade tyska och engelska typer
  förblir därvid entydiga. Även egenberäknade förkortningar för andra
  gränssnittsspråk växer inte längre över fyra tecken vid namnlikhet.
  Egna regelbeteckningar förblir oförändrat benämnda så som de matats in.

- **Ersätt utnyttjar nu hela det faktiskt lediga radutrymmet innan det
  maskerar.** Den tidigare stela gränsen vid tre gånger den ursprungliga
  ordbredden skapade streck även i i övrigt tomma formulärfält. Även
  träffar från den synliga OCR-kontrollen får nu en läsbar platshållare
  vid belagd PDF-text; svarta förblir rena bild-, annoterings- och
  vektorinnehåll, det valda maskeringsläget samt riktigt trånga ställen
  där inte ens en entydig kortform får plats.

- **En redan synlig platshållare skrivs inte längre rött över en andra
  gång vid säkerhetsrastreringen.** Rastreringen övertar nu den befintliga
  ersättningen från sidbilden och lägger bara till en osynlig sökkopia.
  Måste ett säkerhetsstreck täcka exakt detta ställe, förnyas hela den
  faktiska platshållarrutan i stället för bara dess kortare ursprungliga
  ankare.

- **„Hämta original" markerar bara säkra mål i den dragna ramen.** Alla
  ersatta termer i den lyser upp enskilt och exakt; oförändrad löptext
  förblir orörd. Riktiga vektoriella maskeringsstreck markeras likaså
  enskilt, om originaltext ligger under deras svarta PDF-yta. På
  rastrerade sidor avstår förhandsvisningen medvetet från en skenbar
  streckyta: den tidigare bildpunktssökningen band där ihop bokstäver,
  understrykningar och tabellinjer till stora röda ytor på fel ställen.
  Själva återställningen berörs inte av detta.

- **Vid återställning på rastrerade sidor kommer texten tillbaka
  igen.** Senast blev där ett tomt ställe med färgade rektanglar
  ovanpå. Den återhämtade texten stod i dokumentet, men övermålades av
  den vita grunden till en platshållare som ritas längre bak i
  sidkonstruktionen.

- **Kontrollfärgerna ligger inte längre flera gånger över varandra.**
  Samma ställe färgades per post i tilldelningen – på en sida fem
  verkliga fyndställen, vart och ett övermålat fem gånger, tills den
  bleka markeringen blev ett mättat block. Och de visas inte längre på
  ord som inte alls ersattes: står originalvärdet fortfarande på sidan,
  finns det inte heller någon markering där längre.

## 0.10.40-beta.1 – 24 augusti 2026

### Rättat

- **Maskeringsstreck i redigeraren har nu en säkerhetsmarginal.** Ord-,
  rad- och fria ramar täcker även överhängande glyfer och utjämnade
  kantpixlar; en renderingskontroll säkerställer dessutom att varken
  synliga rester eller utläsbar originaltext blir kvar.

- **Ersättningstexter förblir läsbara och enhetligt korta.** Nya namn,
  adresser och fria termer visas till exempel som `[NAM1]`, `[ADR2]` och
  `[BEG3]`. Den fasta undre gränsen är 4,5 punkter; vid platsbrist kortas
  det ned först och det användbara löpområdet utökas. Gamla tilldelningar
  med långa platshållare förblir läsbara och återhämtningsbara.

- **Flerordsersättningar från träffpanelen är säkrade mot dubbla marker
  och originalrester.** Regressionen består med och utan numrerade
  platshållare; per fyndställe finns exakt en gemensam tilldelning kvar.

- **Återhämtat urklippsinnehåll rensas inte omedelbart igen på macOS.**
  Även om systemsignaturen bara byter fördröjt efter skrivningen,
  känner Maskuro tillförlitligt igen sitt eget innehåll.

### Nytt

- **Redigeraren kan återställa en fil helt till den nyss rensade
  utgångsversionen.** „Fil – Återställ" förkastar efter en bekräftelse
  alla efterbearbetningar av den aktuella fliken inklusive
  ersättningslista och räknare. Kommandot är spärrat utan ändringar och
  kan i sin tur tas tillbaka med „Ångra".

- **Förskjutna datumangivelser behåller nu tillförlitligt sin kronologi
  över flera filer.** Den gemensamma förskjutningen förankras nu varaktigt
  i reglerna redan när strategin slås på; dessutom kan förskjutningen inte
  längre vara noll dagar och därmed obemärkt lämna kvar det verkliga
  datumet.

- **PDF-handarbetet täcker nu det fullständiga professionella
  maskeringsförloppet.** Enskilda termer, listor och reguljära mönster kan
  sökas och maskeras säkert i det öppnade PDF-dokumentet eller i alla
  PDF-filer i en mapp; hela sidor och sidintervall kan väljas direkt.
  Färg, neutralt vit yta, överlagringstext, teckensnitt, justering och
  upprepning har en förhandsvisning, återanvändbara koder kan hanteras
  samt importeras och exporteras. PDF-rensningen tar valfritt bort allt
  dolt innehåll genom fullständig ombyggnad eller utvalda dataklasser. Det
  säkraste valet rekommenderas tydligt, ogiltiga sökmönster förklaras och
  mappkörningar skriver uteslutande resultatkopior.

- **Den frivilliga användningsstatistiken visar nu installationer och
  versionsbyten.** Maskuro skapar för detta en slumpmässig, lokalt lagrad
  installationsidentifierare. Den innehåller inga enhets-, användar- eller
  licensuppgifter; servern lagrar bara dess SHA-256-värde. Statistiken
  förblir helt avstängningsbar i inställningarna.

- **Rundturen är nu en guidad övning genom båda fönstren.** Den lägger
  själv in det hittade övningsdokumentet i listan, förklarar vägen fram
  till rensningen och fortsätter automatiskt i redigeraren efter
  körningen. Den som avbryter rundturen avslutar även denna fortsättning.

- **Företag från femton ytterligare rättsområden identifieras.** Den som
  rensar handlingar från Baltikum, Belgien, Skandinavien, Tjeckien, Polen,
  Sydosteuropa, Singapore, Brasilien eller Mexiko förlorar inte längre
  företagsnamn för att deras bolagsform var okänd – nytillkomna är bland
  annat OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s.,
  S.K.A., Pte. Ltd. samt S.A. de C.V. och S. de R.L.

### Ändrat

- **Redigerarens verktygsfält utnyttjar nu sin plats mer riktat.**
  Entydiga standardsymboler och direkt igenkännbara verktygsformer står
  utan upprepande text i fältet; tvetydiga handlingar behåller sitt namn.
  Under „Visa" kan „Visa verktygsbeteckningar" stängas av för att reducera
  båda fälten helt till symboler. Tooltips och menyer förblir helt
  textade, valet kommer ihåg.

- **Inlärningsläget syns nu permanent i verktygsfältet.** Det går att slå
  på och av direkt där, även när facket för ersatta värden är stängt.
  Verktygsfält, verktygsmeny och den tidigare bocken i facket visar alltid
  samma tillstånd.

- **„Återställ" vid jämförelseluppen återställer nu bara dess zoom.**
  Knappen återställer förvalet på 125 procent, utan att docka, flytta
  luppen eller ändra dess fönsterstorlek. För hela uppställningen är
  „Återställ vy" fortsatt ansvarig.

- **Fel och önskemål kan nu även rapporteras via hjälpknappen.**
  „Rapportera fel …" och „Lämna önskemål …" finns nu där precis som i den
  klassiska Hjälp-menyn; båda vägarna öppnar den redan befintliga säkra
  felrapporten respektive den offentliga önskelistan.

- **Aktivitetsfältsmenyn är kortare och tydligare ordnad.** De två
  kommandona med globalt tangentbordskortkommando – urklippsrensning och
  skärmbild – står nu direkt under varandra med en gemensam höger
  kortkommandokolumn. „Återställ senaste originalinnehåll" utgår där; den
  mer begripliga återställningsknappen finns kvar i huvudfönstret.

- **Rättsliga sidor nås direkt under „Hjälp → Rättsligt".** Undermenyn
  leder till licensvillkor, integritetspolicy, företagsuppgifter och
  allmänna villkor på maskuro.com. Anvisningar om ångerrätt finns kvar vid
  köpet på webbplatsen.

- **Handmaskerade PDF-filer byggs om helt vid sparande.** Synliga förblir
  sidorna och deras nyinlästa sökskikt; metadata, filbilagor, bokmärken,
  kommentarer, formulärvärden, dolda lager, sökindex, skript, beskurna
  innehåll och innehåll dolt i andra objekt förs inte över till
  utdatafilen. Teckensnitt och vektorgrafik består därefter av bildpunkter
  – det är priset för den bevisbara gränsen mot det främmande
  PDF-objektträdet.

- **Ctrl+Skift+B tar nu som standard en skärmbild med Maskuro på alla
  system.** Print screen-tangenten och kombinationer med den kan
  fortfarande tilldelas separat. I aktivitetsfältsikonens meny står de
  globala kortkommandona nu till höger om respektive kommando. Egna
  sparade tilldelningar bevaras.

- **Redigeraren startar med sidor och jämförelselupp till vänster.**
  Sidfacket står överst, den öppnade originalluppen direkt därunder; de
  ersatta värdena förblir till höger. En medvetet sparad egen ordning har
  fortsatt företräde.

- **Övningsdokumentet finns inte längre permanent i huvudfönstret.** Det
  är en del av den guidade övningen och nås dessutom fortsatt under
  „Hjälp".

- **Förstakörningen leder direkt till den praktiska övningen.** Den
  illustrerade snabbguiden erbjuds inte längre som en andra, innehållsligt
  dubblerad ingångsväg; den nås fortsatt när som helst under
  „Hjälp → Snabbguide".

- **Den vilande aktivitetsfältsikonen förblir i full färg.** Den visar nu
  samma kraftfulla Maskuro-sköld som det aktiva urklippsläget; bara vid
  aktiv övervakning tillkommer den gröna lysprickens.

- **Övningsdokumentet stannar i Maskuro.** Startknappen skapar den
  hittade PDF-filen och lägger in den direkt i fillistan, men startar
  inte längre någon ytterligare PDF-visare.

- **Sökningen i efterbearbetningsfönstret förblir flytande vid skrivning.**
  Platsen för träffräknaren reserveras redan vid öppningen; dess första
  text ändrar inte längre duken och utlöser ingen ny PDF-rastrering.

- **Tillverkarnamn i fabrikatsangivelser förblir synliga.** En post som
  „Fabrikat: TRILUX eller likvärdigt" beskriver den önskade varan och
  maskeras inte längre enbart på grund av denna beteckning som ett
  företag. Leverantörs-, företags- och tillverkarfält berörs inte av
  detta.

- **Korpusmätningar räknar för brett maskerade träffar som falska larm.**
  När Maskuro tar bort det förväntade namnet men samtidigt tar med en
  satsdel, ökar nu antalet falska larm. Rapporten redovisar dessutom
  övergrepp separat; tidigare antal falska larm kan därför inte jämföras
  direkt.

### Rättat

- **Tekniska och myndighetsbegrepp från tyska originalhandlingar maskeras
  mer sällan som namn eller orter.** Fordonsutrustning, positions- och
  summarader, upphandlings- och integritetsbegrepp, lagbestämmelser samt
  filnamn på offentligt material bromsas nu bara med sitt belagda
  sakliga sammanhang. Ett vid textigenkänningen förlorat prickat bokstav i
  „Marz 2026" förblir skyddat som månad; „Marz" utan datumkoppling kan
  fortfarande vara ett riktigt namn eller en ort.

- **„Hämta original" tar genast hela den nödvändiga bredden.** Träffar
  ramen bara ett ord av ett tilldelat värde, utökar Maskuro den
  självständigt utifrån tilldelningen och originalraden till hela
  uppgiften – till exempel från „Planungs" till „Nordlicht Planungs
  GmbH". Den efterföljande gripbara ramen visar likaså den faktiskt
  återhämtade totala bredden.

- **„Hämta original" visar nu svarta streck som ett entydigt mål.** Vid
  överfarande eller dragning lyser hela det identifierade strecket rött
  med ljus kontrastkontur, i stället för bara en svårt tillordnad textruta
  bredvid. Detta gäller även rastrerade sidor där strecket bara består av
  bildpunkter.

- **Redigerarens rundtur hoppar inte längre över stationer om fack var
  stängda.** För guidningen öppnar och ordnar Maskuro tillfälligt själv
  sidfack, jämförelselupp och ersatta värden. Efter „Klar" eller ett
  avbrott återkommer den personliga ordningen. Är ett verktyg
  grundläggande otillgängligt för en dokumenttyp, förblir dess förklaring
  kvar som texthållplats, i stället för att omärkt försvinna.

- **„Ersätt" förblir synligt även vid PDF-säkerhetsreserven.** Var Maskuro
  tvungen att bygga om en sida som bild på grund av ett kvarvarande tecken
  eller skadad textlöpning, stod de riktiga ersättningarna bara osynligt
  kvar i sökskiktet och på sidan låg svarta streck. De faktiskt satta
  ersättningsvärdena förblir nu synligt röda och sökbara genom alla
  raster- och OCR-ombyggnader.

- **Anvisningarna ovanför den rensade versionen förblir läsbara i det mörka
  utseendet.** Versionsrubrik, hanteringsrad och inledning tar nu sin
  textfärg direkt från det faktiskt visade Qt-fönstret.

- **Maskeringsramar sitter åter över texten på rastrerade PDF-sidor.** De
  osynliga ordrutorna var beroende på originalteckensnitt smalare än de
  synliga bokstäverna. Det gav luckor i strecket eller att den sista
  bokstaven förblev läsbar. Rutorna behåller nu bredd, höjd och
  löpriktning från det synliga ordet.

- **„Vad är nytt" börjar åter längst upp.** Ändringsdialogen sätter efter
  den färdiga fönsteruppbyggnaden textmarkör och rullningslist uttryckligen
  till början, i stället för att beroende på Qt-version starta mitt i
  nyheterna.

- **Stängning under skanningens ordigenkänning förblir tyst.** En just
  färdigblivande OCR-bakgrundskörning skickar inte längre till ett redan
  stängt efterbearbetningsfönster.

- **Relativa tidsangivelser tas inte längre för namn.** Fasta uttryck som
  „idag", „i går", „i morgon" och „nästa vecka" känner Maskuro nu igen
  från de officiella kalenderdata för respektive dokumentspråk.

- **Avslutning under den första modellinläsningen städar upp ordentligt.**
  Den som stänger Maskuro eller efterbearbetningsfönstret omedelbart efter
  öppningen lämnar inte kvar någon tråd som fortfarande arbetar i den
  inbyggda språkigenkänningen vid processavvecklingen. Det förhindrar den
  sporadiska kraschrapporten vid avslutning; en redan pågående inläsning
  slutförs ordnat.

- **Fördröjda startdialoger visas inte längre efter avslutning.** Den som
  stänger huvudfönstret strax efter start får inte efteråt fortfarande
  osynligt eller försenat frågan om bästa igenkänning, nyheter eller
  introduktion visad.

- **HTML och e-post behåller sina radslut.** På Windows blandade
  HTML-serialiseringen efter rensning och återtagning LF och CRLF.
  Innehåll och formatering var korrekta, men filen inte längre bytlik.
  HTML-filer och MIME-meddelanden övertar nu åter sin källas skrivsätt.

- **Företagsnamn med ett relationsord förblir kompletta.** Bakom ett
  förhållandeord kapade Maskuro namn som „Gesellschaft für
  Systemtechnik mbH" eller „Bank für Arbeit und Wirtschaft AG" vid ordet
  „für". Hela företagsnamnet identifieras nu; riktiga satsinledningar som
  „Wir sind bei Alpha GmbH versichert" förblir synliga.

- **Kinesiska företagsnamn förblir kompletta framför sin bolagsform.** En
  som verb tolkningsbar varumärkesdel kunde trots det entydiga tillägget
  „有限公司" förkasta hela namnet. I skrifter utan stor och liten bokstav
  har den officiella bolagsformsankaren nu företräde framför denna osäkra
  ordklassgräns.

- **PDF-sidor blev bilder utan anledning.** Vid flersidiga PDF-filer vars
  sidor delar en teckensnittslista – vilket vanliga skapare lägger upp så
  – förlorade alla efterföljande sidor efter den första sin referens till
  sina teckensnitt. Följden var dubbel: prickade bokstäver var inte längre
  sökbara i resultatet („Auftragsbestätigung" gick inte att hitta), och
  efterkontrollen ansåg därefter bokstäver förbisedda som aldrig stod på
  sidan – den rastrerade hela textsidor till bilder, därmed inte längre
  sökbara, inte kopierbara och märkbart större. I kontrollbeståndet
  drabbade det fyra av sjutton sidor.
- **Ett ensamt kommatecken utlöser inte längre rastrering.** Slutar ett
  fyndområde vid ordet, hör skiljetecknet bredvid ändå knappt till. Ett
  kommatecken eller en punkt är dock ingen förbisedd uppgift, och
  rastreringen kostar hela sidan. Bokstäver och siffror förblir
  fortfarande ett skäl att efterskärpa.

## 0.10.38-alpha.20260824 – 24 augusti 2026

### Nytt

- **Företagsnamn utan bolagsform identifieras nu när deras beteckning
  nämner dem.** „Lieferant: Kranzbichler Handels GmbH" togs alltid bort
  redan tidigare – bolagsformen avslöjar företaget. „Lieferant: Dehner
  Märkte" blev kvar, och i offerter, upphandlingar och beställningar
  står leverantören för det mesta exakt så. Detsamma gäller för „Firma:",
  „Hersteller:", „Fabrikat:", „Arbeitgeber:" och deras motsvarigheter på
  åtta ytterligare språk, och även när beteckningen står ensam på sin
  rad och namnet under den.

  Vad som bakom beteckningen *inte* är ett företag förblir orört:
  „Lieferant: siehe Anlage" maskeras inte – annars skulle det stå
  „Lieferant: [ORGA1]", och det skulle påstå ett namn som aldrig fanns.
  Beteckningar bakom vilka lika ofta en människa står („Kunde:",
  „Auftraggeber:") ingår medvetet inte.

- **En infogad bild går nu även att bearbeta.** I fönstret „Rensa bild"
  står bredvid „Kopiera resultat" en knapp *Bearbeta i editorn*: bilden
  rensas och öppnas därefter för eftermaskering, textning och markering –
  samma väg som en skärmbild går.

- **Nummer bakom sin beteckning hittas nu även när de betecknar en
  affärspartner.** Tidigare föll kund-, avtals- och personalnummer; nu
  även debitor-, kreditor- och leverantörsnummer, det österrikiska
  arbetsgivarnumret, ANKÖ-registreringen och tillverkarens WEEE-, EAR-
  och EPR-nummer – på tyska liksom på engelska. Dessutom förstår Maskuro
  nu skrivsättet med mellanslag före kolon i satta offerthuvuden
  („Kunden-Nr : K903944"). Artikel-, beställnings-, order-, offert- och
  fakturanummer förblir fortsatt orörda: de betecknar förloppet eller
  varan, inte människan. Den som ändå vill ta bort dem lagrar dem som
  ett eget sökmönster.

- **Du ser nu hur lång tid en fil har tagit.** Vid den färdiga raden
  står varaktigheten bredvid det identifierade språket („klar · Tyska ·
  2,4 s"), i sammanfattningen hela körningens, i nyckeltalsklaffen
  summan – och i kontrollrapporten står den som ett eget fält. Vid flera
  filer avslöjar raden vilken av dem som kostade tiden.

- **Skrifter som inte stöds av system-OCR:n kan läsas som reserv med
  befintlig språkfil.** Tidigare gällde: behärskar den systemegna
  textigenkänningen inte en skrift (på Mac till exempel devanagari),
  stod i resultatet „Bild(er) har INTE kontrollerats", och uppgifterna i
  bilden blev kvar. Nu hoppar den medföljande textigenkänningen in, om
  den passande språkfilen finns. Eftersom en så läst bild är mer osäker
  än en normalt kontrollerad, står det i resultatet: „läst med
  reservmetoden – kontrollera gärna". Uppmätt mot ett historiskt
  mellanläge av hindi-provet: **tio uppgifter fler hittade och fyra
  falska larm färre** (64 % → 73 %). Det aktuella slutvärdet står högre
  upp och ska inte förväxlas med detta.

- **Textigenkänningen frågar efter rätt språk.** För alla dokumentspråk
  utom tyska och engelska användes tidigare den engelska
  igenkänningsmodellen, även när den passande språkfilen fanns
  tillgänglig. Under Windows berörde det varje språk – grekiska,
  japanska eller hindi lästes där med den engelska modellen.

- **En installationsguide vid allra första starten.** (Den som redan
  använt Maskuro får den inte – „förstakörning" betyder första start,
  inte första start efter denna uppdatering.) Tre frågor i stället för
  sex bilder: språket för dina dokument, om text i bilder ska läsas med,
  och hur du vill nå Maskuro i vardagen. På slutet finns de tre vägarna
  kvar – övningsdokument, rundtur eller den illustrerade snabbguiden.
  Allt går att hoppa över, och „Hjälp → Gå igenom installationen igen"
  hämtar tillbaka den.

- **F1 öppnar handboken vid rätt kapitel.** I huvudfönstret, i
  inställningarna (där beroende på sida), i genomsökningsfönstret och i
  språkhanteringen; i efterbearbetningsfönstret via Skift+F1, eftersom
  F1 där sedan länge visar tangentbordskortkommandona. Tidigare började
  hjälpen alltid överst, vid 25 kapitel.

- **Nytt första handbokskapitel: „Kom igång på tre minuter".** Fyra
  steg, mer behövs inte för ett dokument – på alla 18 språkversioner.

- **En rundtur genom fönstret.** „Hjälp → Rundtur genom fönstret" lägger
  strålkastarljus på ett kontrollelement efter ett annat och skriver en
  mening bredvid – i huvudfönstret åtta stationer, i
  efterbearbetningsfönstret sju. Till skillnad från den illustrerade
  snabbguiden förklarar den fönstret du just sitter framför. Avbryt när
  som helst med Esc.

- **Ett övningsdokument för riskfri provkörning.** Under avlämningsytan
  står nu „Öppna övningsdokument" (även i Hjälp-menyn). Det skapar ett
  hittat blad – namn, adress, telefonnummer, IBAN, personnummer – och på
  bladet står samtidigt vad du kan göra med det och vad du kommer att se
  efteråt. Inte ett ord av det tillhör en riktig person; det första
  dokument du skickar genom Maskuro behöver alltså inte vara ett riktigt.

- **„Bara se efter …" står nu bredvid „Rensa".** Det visar var
  personuppgifter finns – fil, typ och antal – utan att ändra eller
  skriva något. Den som lagt in ett dokument kan därmed se efter innan
  hen rensar. Tidigare låg denna väg bara i Arkiv-menyn under „Genomsök
  mapp …" och gick via en hel mapp i stället för de inlagda filerna.

- **När inget hittades står det nu med vad det kan bero på.** Till
  exempel: i filen finns bilder, men „Kontrollera även text i bilder" är
  av. Eller: det inställda språket passar inte dokumentets. Och när
  inget av detta stämmer, säger Maskuro det också.

- **Efterbearbetningsfönstret hälsar dig första gången med tre
  meningar:** klicka maskerar ett ord, dra ett område, till höger står
  de ersatta värdena. „Förstått" tar bort hänvisningen varaktigt;
  „Hjälp → Visa introduktion igen" hämtar tillbaka den.

- **Klicka på ord fungerar nu även på skannade sidor.** Tidigare gick
  ord bara att klicka på där PDF-filen har ett textskikt med sig – vid
  en skanning gick det inte, och i samma dokument kunde det växla från
  sida till sida. Sådana sidor läses nu en gång av textigenkänningen;
  därefter klickar man ord som överallt annars. Statusraden säger vad
  som just pågår.

- **Sidfacket är åter en yta.** Det slutade mitt i sin kolumn:
  titelraden avskuren, bredvid en rand i en annan färg, och den
  aktuella sidan var bara att känna igen på en färgad ruta bakom sitt
  nummer. Nu fyller det ut sin kolumn, går att dra bredare, och den
  aktuella sidan är markerad som en hel kakel – med oförfalskad
  sidförhandsvisning i sig.

- **Ersatta ställen lyser blekgult.** I sidvisningen syns därmed på en
  blick var något ersatts – samma färg som jämförelseluppen använder
  över originalet. Den röda ramen vid pekning med musen förblir
  oförändrad.

- **„Återställ vy" i efterbearbetningsfönstret** (menyn „Visa"). Den som
  flyttat, lösgjort eller stängt sidfack eller träfflista ställer
  därmed tillbaka allt dit det stod vid första start.

### Ändrat

- **Platshållarna är kortare.** Ur `[SOZIALVERSICHERUNGSNR_1]` blir
  `[SVNR1]`, ur `[ORGANISATION_1]` ett `[ORGA1]`, ur `[EMAIL_1]` ett
  `[MAIL1]`. Skälet är inte skönhet: en platshållare som är längre än
  värdet den ersätter tränger isär raden och får inte plats alls i en
  smal tabellkolumn – där blev tidigare ett svart streck kvar, och det
  säger inte längre någon att något stod där. Där det finns en gängse
  förkortning, står den där (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`). Resultat
  från tidigare körningar förblir användbara: det gamla skrivsättet
  identifieras fortfarande, och tilldelningsfiler från igår fungerar
  oförändrat.

- **Programikonen står nu likadan överallt.** I menyraden på Mac visades
  tidigare en enfärgad sköld som systemet självt färgade svart eller
  vit, i Windows aktivitetsfält en grön respektive grå. Nu bär varje
  fält samma blå Maskuro-sköld. Vad man ser på om urklippet övervakas
  förblir lika tydligt: körs övervakningen, sitter en grön prick vid
  skölden; vilar den, står samma sköld blek. Även i de minsta
  storlekarna står nu båda maskeringsstrecken i skölden – tidigare
  visade aktivitetsfältet där bara ett.

- **Ansikten identifieras med en modell vars träningsbilder tillkommit
  med samtycke.** Levererad blir nu MediaPipe BlazeFace (Apache-2.0);
  den tidigare detektorn finns kvar inbyggd och omkopplingsbar, men
  medföljer inte längre, eftersom dess träningsursprung inte är
  slutgiltigt klarlagt. För igenkänningen ändras ingenting: vid 324
  porträtt och 143 bilder utan ansikte hittar den nya versionen lika
  mycket vid lika få felgrepp och behöver en tredjedel av tiden.

- **OCR är säkerhetsankaret för det starkaste PDF-löftet.** Den normala
  PDF-körningen använder den och skapar den fullständiga
  minimiuppbyggnaden. Den som uttryckligen stänger av OCR får den mer
  kompatibla objektvägen; gränssnitt, slutmeddelande och handbok säger
  nu uttryckligen att denna väg inte erbjuder samma arkitektur mot
  okända dolda PDF-kanaler.

- **Försäljningsgrinden spärrar nu även den tidigare medföljande
  YuNet-modellen.** MIT-licensen för den exakta vikten förblir
  dokumenterad, men räcker inte för den offentligt synliga
  träningsdatakedjan via WIDER FACE som en konservativ produktfrigivning.
  Före försäljning krävs en skriftlig klargörning eller ett byte mot en
  modell med en hållbar kommersiell data- och viktkedja.

- **Företags- och organisationsnamn tas nu bort automatiskt.** Tidigare
  blev de kvar så länge man inte uttryckligen begärde det. Det var fel
  förval för ett affärsbrev: den som vidarebefordrar en offert vill inte
  läsa uppdragsgivaren i den. „Kranzbichler Handels GmbH", „Institut für
  Bauphysik" och liknande behandlas därför som ett namn. Den som
  behöver det annorlunda stänger av det i fönstret; på kommandoraden
  heter brytaren nu `--ohne-organisationen`. Den gamla
  `--mit-organisationen` tas fortfarande emot och gör inget längre, så
  att befintliga skript och genvägar inte går sönder. Datum- och
  penninguppgifter förblir oförändrat undantagna.

- **Maskering har nu tre former i stället för två bockar.** „Ord", „Hela
  raden" och „Fri ram" står som ett val bredvid varandra – exakt en
  gäller alltid. Tidigare var „Textrader" och „Hela raden" två
  oberoende brytare som båda kunde vara nedtryckta, och den fria ramen
  var inte alls en knapp, utan det avstängda läget för den första. De
  tre står synligt vid sitt verktyg och är gråa så länge ett annat
  verktyg är valt.

### Förbättrat

- **Det första dokumentet är klart cirka en sekund snabbare.** Innan
  rensningen börjar fastställer Maskuro dokumentets språk – och hämtade
  därför tidigare ordlistorna för alla 48 språk på en väg som laddade
  mycket mer än orden. Det var ungefär hälften av väntetiden fram till
  det första resultatet. Igenkänningen själv är oförändrad: den ser
  samma ord som förut, bara snabbare. Varje ytterligare dokument var
  ändå aldrig berört av detta.

- **Dokument med mycket långa stycken kontrolleras snabbare.** Vid ett
  stycke utan radbrytning läste Maskuro tidigare igenom det helt för
  varje hittat ställe; nu räcker en gång. Ju längre stycket, desto
  större skillnad – uppmätt cirka en sjundedel mindre beräkningstid. På
  resultatet ändras inget.

### Rättat

- **Med ett företag försvann ofta halva meningen med.** Stod ett
  företagsnamn i löptexten – „Information über die Gottwald GmbH & Co
  KG", „… (AGB) der Musterbetriebe GmbH" –, maskerades inte bara namnet,
  utan allt framför fram till satsbörjan. Texten blev därigenom oläslig,
  och det såg ut som om maskeringen skett godtyckligt. Företagsnamn som
  själva bär ett „für" eller „und" („Bank für Arbeit und Wirtschaft AG")
  förblir därvid oförändrat fullständiga.

- **Företagsnamn blev kvar i brevhuvuden, trots att de togs bort i
  texten.** I en offert stod företagssätet i brevhuvudbilden fortfarande
  läsbart – samma ort som Maskuro maskerat i löptexten; i resultatets
  sökbara text stod den till och med osynligt kvar. Det som en gång togs
  bort tas nu bort även där det bara finns som bild. Det gäller även
  logotyper och ordmärken som är ritade som grafik.

- **macOS frågade vid varje start om skärminspelning**, även när
  behörigheten redan givits för länge sedan. Hänvisningen vid start
  provade en inspelning, och just det tar fram systemdialogen på
  skärmen. Nu frågar bara Maskuro själv vid start, och bara en gång;
  systemet frågar först när du verkligen tar en skärmbild.

- **Tekniska sakbegrepp togs för orter och företag.** „Einspeisepunkt",
  „Flachdach", „Verteileranlage", „Meldersockel" och dussintals liknande
  ord försvann ur offerter och prestationsförteckningar. Maskuro
  identifierar dem nu på sitt grundord: det som slutar på „-anlage",
  „-punkt" eller „-kanal" är en sak. Ortnamn som Berlin, Melk eller
  Wieselburg har inget sådant grundord och förblir oberörda – likaså
  adresser som „Der Graben" eller „Alter Markt".

- **Japanska, koreanska, kinesiska, thailändska och gujarati-dokument
  kunde krascha programmet.** Innehöll ett dokument på ett av dessa fem
  språk en internetadress utan „https://" framför, avbröts rensningen
  med ett internt fel – med öppet fönster gick även det övriga arbetet
  förlorat. Alla fyrtioåtta valbara dokumentspråk körs nu igenom;
  saknas frekvensordboken för ett språk, blir uppgiften i tveksamma fall
  kvar i stället för att försvinna.

- **Fältbeteckningar skyddade bara på tyska och engelska.** „Reference"
  blev kvar, det italienska „Riferimento" och det portugisiska
  „Referência" togs bort som ortsuppgift – samma fältnamn, samma rad,
  olika resultat. Den som inte arbetar på engelska var därmed sämre
  ställd. Maskuro känner nu till samma fältnamn på alla elva underhållna
  språk.

- **„Hämta original" hämtade för mycket tillbaka på skannade sidor.** En
  ram över en maskerad rad i ett adressblock avslöjade **hela blocket**
  igen – och sidan blev kvar sönderriven: streckrester stod fortfarande
  kvar, ur vilka enskilda ordslut stack ut. Orsaken var att streck som
  ligger under varandra på en rastrerad sida stöter ihop och därför
  gällde som en enda yta. Nu hämtas exakt den rad tillbaka som ramen
  pekar på; grannraderna förblir maskerade, och strecket på den
  träffade raden försvinner helt.

- **Kvantitetsangivelser i positionslistor togs för adresser.** I en
  rad som „1.4  Kabelgraben  100,00  m" ersattes „Kabelgraben 100" som
  en gata med husnummer. Sådana rader blir nu kvar; riktiga adresser –
  även „Hauptplatz 1, 3250 Wieselburg" – identifieras oförändrat.

- **Framför ett företagsnamn försvann halva meningen.** Ur „Vertrag
  zwischen der Firma Gottwald GmbH & Co KG und dem Auftraggeber." blev
  „[ORGANISATION_1] und dem Auftraggeber." – satsbörjan var borta, och
  därmed hänvisningen till vad det gäller. Nu faller bara själva
  företagsnamnet. Där släktnamnet hör till namnet („Deutsche Bank AG",
  „Universität Wien"), förblir allt som förut.

- **I ett protokoll blev talare vars namn samtidigt är ett yrke kvar.**
  „Bauer:", „Koch:", „Weber:" framför en ordanmälan förbisågs,
  „Gruber:" bredvid inte – Maskuro behövde tidigare minst ett
  identifierat namn i skriften för att alls läsa raderna som
  ordanmälningar. Bär dokumentet en rubrik som „Ergebnisprotokoll" eller
  „Niederschrift", räcker det nu. Anmärkningsrader („Achtung: …",
  „Hinweis: …") förblir orörda.

- **En fältbeteckning försvann tillsammans med sitt värde.** Ur
  „Projekt: Sanierung und Erweiterung Gemeindezentrum" blev en enda
  platshållare – även ordet „Projekt:" var borta, och därmed
  hänvisningen till vad som stått där. Beteckningar blir nu kvar. Där en
  beteckning hör till uppgiften och bär dess betydelse
  („Durchwahl 214"), ändras inget.

- **Den maximala igenkänningen städade inte bort sakbegrepp.**
  „Flachdach", „Einspeisepunkt", „Elektrotechnik" och liknande fackord
  ersattes även med påslagen KI-nivå som ort eller företag – KI:n fick
  aldrig just dessa fynd förelagda för bedömning. Den kontrollerar dem
  nu med: i ett korpus av upphandlings- och avtalstexter försvinner
  därigenom alla 27 felgrepp, utan att en enda riktig uppgift blir kvar.
  Namn, företag och orter identifieras oförändrat.

- **Släktnamn för institutionstyper togs för organisationer.** I en
  avtalstext försvann „Hochschulen und Universitäten", „Staatliche und
  private Schulen", „Akademische Lehrkrankenhäuser", „Bildungseinrichtung"
  och „Zulieferfirmen" – ord som inte betecknar ett bestämt ställe, utan
  en typ av ställe. De blir nu kvar. Står ett egennamn framför
  („EU-Kommission"), ersätts fortfarande, och företagsnamn omfattas inte
  alls av regeln.

- **Namn i listor föll bara om de var vanliga.** I en deltagar- eller
  närvarolista under ett kolumnhuvud „Name" togs „Anna Huber" och
  „Thomas Müller" bort, „Wójcik Aleksandra" eller „Kücükgöl Sinan" inte
  – samma rad, samma uppbyggnad. Den som bär ett ovanligare namn var
  därmed sämre skyddad. Nu avgör kolumnhuvudet: vad som står under
  „Name" är ett namn. En positionslista med ett sakligt kolumnhuvud
  förblir orörd.

- **Ett telefonnummer bakom „Durchwahl" skars av mitt itu.** Ur
  „Durchwahl 0732 771190" blev „[DURCHWAHL_1] 771190" – nummerets andra
  hälft förblev läsbar. Nu faller hela numret helt, och beteckningen
  blir kvar. En riktig anknytning („Durchwahl 214") ersätts oförändrat
  tillsammans med beteckningen.

- **Vissa PDF-filer gick inte alls längre att rensa.** Kunde en
  färgprofil eller metadatan i en bild inte bevisligen tas bort,
  avbröts körningen utan resultat – berörda var vanliga
  affärshandlingar som villkorssidor, kravspecifikationer och
  upphandlingar. Sådana filer rensas nu, och en varning nämner de
  ställen som förblev öppna: de kan bära en enhets-, skapar- eller
  inspelningsidentifierare. Originalet förblir som alltid oförändrat.

- **Avtalsroller togs för personer.** „Bieter", „Verbraucher", „Mieter",
  „Käufer", „Auftraggebers" och ett fyrtiotal andra rollord ersattes där
  de stod utan artikel – i avtalsrubriker, tabellkolumner och
  underskriftsrader. En avtalstext utan ett enda personuppgift blev
  därigenom stundtals oläslig. Dessa ord blir nu kvar. Står en
  personhänvisning bredvid – en tilltalsform, ett förnamn, ett fältord
  som „Ansprechpartner" –, ersätts fortfarande: „Herr Bieter" och „Frau
  Käufer" är namn. Vanliga efternamn som samtidigt är yrken (Bauer,
  Richter, Koch) omfattas inte alls av regeln.

- **En förkortat skriven gata förbisågs när husnumret klibbade direkt
  intill punkten.** „Schlesischestr.31" gällde inte som adress – och
  eftersom postnumret bredvid får sitt stöd från adressfyndet, blev även
  det kvar. I resultatet gick adressen ur gata och postnummer att sätta
  ihop igen, och det bara på vissa sidor av samma dokument. Båda faller
  nu tillsammans. Sakbeteckningar med tal efter („Kabelrinne200") förblir
  orörda.

- **En adress över två rader drogs ihop till en enda platshållare.**
  Stod postnumret i ett adressblock ovanför gatan, band Maskuro ihop
  båda raderna till ett fyndställe: i resultatet försvann radbrytningen,
  och postnumret blev läsbart kvar framför. Nu identifieras och ersätts
  varje rad för sig, och skriftbilden bevaras. Samma orsak drog ibland
  också in efternamnet från raden ovanför i adressen.

- **Den maximala PDF-vägen övertar inte längre originalobjekt.** Med
  påslagen textigenkänning bygger Maskuro nu varje sida helt om från den
  synliga PDFium-bilden. I den nya minimifilen kommer bara denna
  bildsida och ett nyskapat, till OCR-texten begränsat sökskikt in –
  inte det främmande objektträdet med kommentarer, bilagor, åtgärder,
  lager, metadata, färgprofiler eller privata nycklar. Detta gäller även
  innehåll i annoteringsutseenden, mönster, typ-3-teckensnitt,
  formobjekt och mjuka masker. Källfilen förblir oförändrad.

- **Ansikten och koder i inbäddad PDF-grafik förbisågs.** Båda
  detektorerna ser nu dessutom hela den renderade sidbilden. Därigenom
  når även porträtt och QR-/streckkoder i annoteringar, mönster,
  typ-3-glyfer och transparensmasker detektorerna; identifierade
  områden görs – om påslaget – okännbara före minimiuppbyggnaden. Själva
  detekteringen förblir felbar.

- **En saknad OCR-motor slutade vid PDF-filer med ett internt fel.** Den
  maximala körningen avbryts nu kontrollerat och utan målfil, i stället
  för att lämna ut en ofullständig eller okontrollerad fil.

- **Flera riktiga kontakt- och affärsvärden föll igenom, medan sakord
  ersattes.** Namnfält över radbrytningar, bank- och företagsnamn,
  bolagsformer, betecknade identifieringsnummer, födelsedatum samt
  telefon-, URL- och IBAN-gränser är striktare kontrollerade. Samtidigt
  förblir länder i sakord, roll- och släktord, artikel-/normkoder,
  talkolumner och vanliga förkortningar oftare orörda.

- **Blandade och roterade OCR-rader lästes fel.** Osäkra lodräta ord
  läses nu om lokalt upprätade; tekniska latinska värden i icke-latinsk
  text får ett oberoende engelska-vittne. En fristående osäker enskild
  siffra korrigeras bara om två snäva siffersekvenser stämmer överens.
  Polska bolagsformer av OCR-formen „sp. z 0.0." läses i sluten kontext
  som „sp. z o.o.".

- **Bildmätningen kunde förbise delvis synliga restvärden.** Den
  kontrollerar nu överlappande lokala utsnitt, skiljer vit
  platshållartext på ett svart streck från originalglyfer och överför
  rådatabildrutor även till roterade, nyrenderade minimi-PDF-filer. Det
  fasta syntetiska huvudkorpuset når därmed 1 392/1 392 borttagna
  börvärden vid 0 falska larm och 0 bearbetningsfel. Detta är ett
  korpusbelägg, inget allmänt 100-procentslöfte.

- **Icke-kommersiella språkmodeller erbjuds inte längre.** De sex
  italienska och grekiska spaCy-varianterna under CC BY-NC-SA 3.0 är
  borttagna ur katalog, nedladdning och laddväg; redan befintliga
  modellmappar ignoreras också. Båda språken använder i stället den
  MIT-licensierade flerspråksmodellen.

- **Namnet under „Ansprechpartner" togs bara halvvägs bort.** Står
  beteckningen ensam på en rad och därunder „Nachname Vorname", blev
  förnamnet kvar så snart det samtidigt är ett vanligt ord – ur „Mayer
  Roman" blev „[NAME_1] Roman". Sådana rader tas nu helt. En avdelning
  på samma plats („Technischer Innendienst") förblir fortsatt orörd.
  Åtgärdat i förbigående: „Ansprechpartner" räknades inte alls som ett
  namnfält, trots att „Kontaktperson" gjort det sedan länge.

- **Företagsnamnet utan bolagsform blev kvar om ett branschord stod
  emellan.** „Kranzbichler Handels GmbH" togs bort, det nakna
  „Kranzbichler" tre stycken senare inte – vid „Kranzbichler GmbH"
  däremot ja. Nu fångar båda. Vanliga ord är undantagna från detta:
  „Deutsche Bank AG" gör inget „deutsche" i texten till ett företag.

- **Samma värde hette i samma dokument ibland namn, ibland ort.** „Anna
  Musterfrau … Musterfrau" gav „[NAME_1]" och „[ORT_1]" – på det andra
  stället saknas förnamnet, och utan det blev det en ort. Borttaget var
  båda, men det lästes som två olika saker. Ett värde behåller nu
  beteckningen från sin första förekomst.

- **Datumangivelser togs inte längre bort.** Ett datum helt av siffror
  („01.03.2026") föll sedan den senaste versionen igenom en kontroll som
  var avsedd för namn, och blev kvar i dokumentet – även i driftläget
  „förskjut", och utan rad i kontrollrapporten. Berörd var bara den som
  uttryckligen slagit på datumangivelser.

- **Länder och kontinenter maskeras inte längre.** „Die Lieferung geht
  in die Vereinigten Staaten", „Marktschwäche in Asien", „die Norm gilt
  in Rumänien" – sådana uppgifter säger inget om en person och blir nu
  kvar. Hör landnamnet däremot till en adress eller står det bakom en
  beteckning som „Wohnsitz" eller „Geburtsort", tas det fortfarande
  bort. **Städer berörs inte** – „Ich bin gerade in Bilbao" förblir en
  uppgift om en person och maskeras fortfarande.

- **Förkortade ord blev webbadresser.** Står det i texten „bzw. deutsche"
  eller „incl. der", levererar vissa PDF-filer punkten utan mellanslag –
  därav blev „bzw.de" respektive „incl.de", en giltig adress med
  landsändelse, och den togs bort. Sådana ordpar blir nu kvar. Riktiga
  adresser berörs inte, inte heller utan „www." framför.

- **Talkolumner ur bokslut maskerades som telefonnummer.** I
  årsredovisningar och pristabeller står föregående år och löpande år
  bredvid varandra – „64.518  65.133". Det gällde som ett telefonnummer
  och togs bort, likaså talintervall som „12200-23200" och ett datum med
  efterföljande tal. Sådana tal blir nu kvar. Omvänt identifieras ett
  riktigt telefonnummer säkrare: beteckningarna „Telefon", „Fax",
  „Mobil", „Durchwahl" och deras motsvarigheter på de andra
  gränssnittsspråken räknas nu med – tidigare kände programmet där bara
  igen de engelska orden.

- **Namn i en numrerad tabell blev kvar.** En deltagarlista eller
  personaltabell i den vanliga formen – kolumnhuvud, därunder „1.1
  Auersperg Bernhard Montage 03.03.2026" – rensades inte alls: sådana
  rader såg ut som positionslistan i en offert, där sakbegrepp ska bli
  kvar. Bär kolumnhuvudet en personbeteckning („Name", „Nachname",
  „Surname" …), gäller raderna under nu som namn. Positionslistor
  förblir oförändrat besparade – även när det i brevhuvudet står
  „Sachbearbeiter:".

- **Ur ett namn blev det ibland två platshållare bredvid varandra.** Om
  ett efternamn också stod ensamt i dokumentet, ersatte
  efterbearbetningen på ett ställe som „Anna Musterfrau GmbH" först
  efternamnet och sedan förnamnet – i resultatet såg det ut som två
  olika personer. Nu vinner det längsta kända namnet.

- **Hittade värden stod inte i någon tilldelning.** Den som valt „Hitta
  på värden" fick ett resultat där „Anna Musterfrau" blivit „Greta
  Mayrhofer" – i tilldelningen stod inget om det, så snart samma
  dokument även innehöll en enda anonym ersättning. Därmed gick inget
  hittat värde att hämta tillbaka, och tilldelningsfilen dolde
  ersättningen. Känsligast var det tredje: den som läser resultatet ser
  ett trovärdigt namn och har ingen ledtråd om att det är hittat på. Nu
  står varje ersättning i tilldelningen.

- **Tilldelningen kallade det maskerade för „ersatt".** Ett
  e-postmeddelande delar en tilldelning med sina bilagor, och bilagan
  får maskeras medan mejltexten bär en platshållare. I tilldelningen
  stod då samma sak för alla tre ställen – „ersatt" – och
  återhämtningen sökte i bilagan en platshållare som inte finns där:
  strecket blev liggande. Nu står per fyndställe vad som verkligen
  hände där, och båda bilagorna kommer tillbaka.

- **Värden som bara stod i en bild gick inte att hämta tillbaka.** I
  träffpanelen stod de dubbelt – en gång som en platshållare som inte
  fanns någonstans i dokumentet („Platshållaren hittades inte i
  dokumentet"), en gång som ett maskerat ställe. Den första raden var
  ren bokföring och har försvunnit.

- **Maskerade värden gick bara att hämta tillbaka en gång.** Står samma
  värde på flera ställen, hämtar ett klick tillbaka alla – men de
  övriga raderna blev kvar i träffpanelen, och nästa klick på den
  meddelade „Inte entydigt". De försvinner nu med.

- **Återtagningar saknades i kontrollprotokollet när inlärningsläget var
  av.** Den som återställde ett återhämtat värde i
  efterbearbetningsfönstret hittade inte förloppet i kontrollprotokollet
  så länge inlärningsfrågorna var avstängda – belägget hängde på en
  brytare som bara gäller regelförslagen. Vid påslaget kontrollprotokoll
  frågas nu oberoende av detta efter orsaken och raden skrivs.

- **Indragna filer förblev orensade – och rapporterades inte ens.** Den
  som drar en fil in i ett dokument i stället för att skicka den som
  bilaga får Word eller PowerPoint att lagra den fullständigt i
  dokumentet. Den stod därefter oförändrad i resultatet, tillsammans med
  sitt ursprungliga filnamn och lagringssökväg – och de bär i praktiken
  ofta själva ett namn. Sådana filer rensas nu som det övriga
  dokumentet.

- **Och där det inte går, säger Maskuro det.** Ligger i ett inbäddat
  objekt ett gammalt format (Word 97, Excel 97) som det inte finns någon
  rensning för, visas nu ett OBS-meddelande med filens namn. Tidigare
  lämnades den tyst vidare oförändrad.

- **Sönderdelade ord och förkortningar togs för namn.** När ett ord i
  ett PDF-dokument avstavas vid radslutet, kommer vid inläsning av vissa
  filer ett fragment ut – „Jahresent… gelts", „Gewerbli…". Sådana
  fragment, hopklistrade ord („TürverschlussmitV") och nakna
  förkortningar („JY", „FFB") maskerades som om de vore namn. De blir nu
  kvar. Ett namn med samma avstavningsskada maskeras fortsatt så länge
  en tilltalsform följer med – och namn som från början bär en versal
  mitt i ordet (McKenzie, MacDonald, LeBlanc) berörs ändå inte av detta.

- **Måttangivelser och månader gällde som adress.** I tekniska
  underlag maskerades „2000 Lux", „1200 Mbit", „1500 Watt", „5308 Platz"
  och „2022 Mrz" – fyra siffror och ett stort skrivet ord såg ut som ett
  postnummer med ort. Ett postnummer räknas nu bara om även en
  adressignal finns med: en landsbeteckning, en fältbeteckning,
  radbörjan, en gata på raden ovanför eller en ort som även
  språkigenkänningen ser där. I fem prestationsförteckningar försvinner
  därmed 14 felaktiga maskeringar, utan att en riktig adress blir kvar.

- **Den noggrannare igenkänningen ersatte för mycket.** Den valbara
  nivån „noggrannare igenkänning" tog i tyska affärshandlingar sakbegrepp
  för namn och orter – „Photovoltaikanlage", „Einspeisepunkt",
  „Flachdach", „Personaleingang" – och maskerade företagsbeteckningar
  ur löpande positionslistor. Orsaken var en skonsamhet: dess träffar
  var undantagna från de kontroller som identifierar en positions- eller
  förteckningsrad. Denna skonsamhet gäller nu bara flerdelade namn, som
  nivån finns till för – „Anna Huber" i en förteckningsrad förblir
  alltså identifierad, ett enskilt sakord i en positionsrad faller bort.
  I en teknisk upphandling halverar det nivåns felaktiga maskeringar,
  utan att något namn går förlorat.

- **Diagram tog med sina fullständiga källdata – okontrollerade.** Den
  som infogar ett diagram i Word eller PowerPoint får programmet att
  lagra tabellen det räknats fram ur som en egen fil i dokumentet.
  Synliga är därav bara de få siffrorna i diagrammet; i tabellen står
  hela listan, tillsammans med raderna som alls inte förekommer i
  diagrammet. Denna tabell lämnades tidigare vidare oförändrad. Den
  rensas nu med, med samma platshållare som det övriga dokumentet.

- **Detsamma för inbäddade objekt i OpenDocument-filer** (ODT, ODS,
  ODP): ett infogat diagram eller en infogad tabell förblev orörd.

- **Word-dokument: fotnoter och slutnoter rensades inte.** Deras text
  förblev fullständigt kvar i resultatet – även namn, adresser och
  kontonummer. Berört var varje Word-dokument med en fot- eller
  slutnot. Likaså förblev ett autotext-byggblock som osynligt reser med
  dokumentet orört.

- **Word: uppgifter i urvalslistor, kommentarer och bildbeskrivningar.**
  Posterna i ett valfält (synligt först vid uppfällning), en kommentars
  författare, en teckningsbeskrivning och adressen bakom ett
  referenskommando stod fortfarande kvar i resultatet.

- **Excel: pivottabellen förde in källdata en andra gång.** En
  arbetsbok med en pivottabell bevarar i den en fullständig kopia av de
  utvärderade raderna – osynligt, men i filen. Denna kopia förblev
  tidigare oförändrad, även när allt var ersatt i själva bladet. Berörd
  var varje utvärdering som lämnades vidare med en pivottabell.

- **Excel: samtalskommentarer och deras författare.** Texten i en
  kommentar av den nyare typen och förteckningen över kommentatorer –
  visningsnamn och inloggningsidentifierare, i företag oftast
  e-postadressen – stod fortfarande kvar i resultatet. Samma
  förteckning i Word-dokument likaså.

- **Egendefinierade dokumentegenskaper i Word och Excel.** Fält som
  „Mandant" eller „Aktenzeichen", som en advokatbyrå ger sina mallar,
  rensades tidigare inte. De syns i ingen vy och reser ändå med i varje
  kopia.

- **Kalkylblad (ODS): en cells urvalslista.** Som i Excel sedan förra
  versionen rensas nu även i OpenDocument-kalkylblad det som visas vid
  uppfällning av en cell. Referenser till andra celler förblir därvid
  orörda, så att listan fortsätter fungera.

Alla dessa ställen går som vanligt att hämta tillbaka via tilldelningen.

- **Outlook-meddelanden: en skadad fil avslutade rensningen hårt.**
  Vissa trasiga `.msg`-filer ledde till ett avbrott i stället för ett
  meddelande; nu läses de så långt de är läsbara.

- **Tilldelningsfilen är nu bara läsbar för dig.** Den innehåller
  originaluppgifterna i klartext och låg tidigare med de vanliga
  rättigheterna bredvid resultatet – på en delad lagringsyta kunde
  därmed vem som helst öppna den. På det rensade resultatet själv
  ändras inget; det ska ju lämnas vidare.

- **Nedladdade språkmodeller kontrolleras nu noggrannare före
  uppackning.** Ett manipulerat paket – till exempel från en
  företagsdelning som betjänar flera arbetsplatser – kunde vid
  uppackning lägga filer utanför den avsedda mappen. Vid den vanliga
  nedladdningen ändras inget.

- **Ta en skärmbild – och den rensas genast.** Med `Ctrl+Skift+B`, via
  „Arkiv → Ta skärmbild …" eller via ikonen i aktivitetsfältet drar du
  en ram över skärmen. Det som ligger i den går sedan samma väg som
  vilken annan fil som helst: textigenkänningen läser skärmtexten, namn,
  adresser, telefonnummer och e-postadresser maskeras, och därefter
  ligger bilden öppen i editorn, där du med en ram kan eftermaskera det
  som förbisågs. Den rensade bilden hamnar på skrivbordet (eller i din
  inställda utmatningsmapp); den **råa** inspelningen lagras
  ingenstans och raderas vid avslutning. Textigenkänningen slås på för
  denna körning, även om den annars är av – i en bild skulle utan den
  inget gå att hitta. På Mac frågar systemet första gången om
  behörigheten „Skärminspelning".

- **På bilder går det nu att rita: rektangel, ellips, pil, text och
  numrerade stegmarkörer.** I sex färger och tre streckbredder, väljbara
  med tangenterna 1 till 5. Det är tänkt för skärmbilder och
  anvisningar: visa vad som är viktigt, utan att öppna ett andra program
  för det. Ångra och att dra i handtagen gäller som för vilket streck som
  helst – en anmärkning går alltså att flytta och dra ut efter att den
  satts.
  **Att rita är uttryckligen inte att maskera.** En ritad rektangel är
  en ram, inget streck: det som ligger under förblir läsbart och följer
  med filen ut. För att ta bort uppgifter finns fortfarande „Maskera"
  och „Pixlera"; ritverktygen står därför i en egen rad i verktygsfältet,
  och hänvisningsraden säger det så länge ett av dem är valt.

- **Den bearbetade bilden går med ett klick till urklipp.** „Kopiera
  bild" i editorn (eller `Ctrl+C`) lägger den precis som den ser ut –
  det räcker att klistra in för att föra den till ett meddelande eller
  ett mejl. Därmed är vägen från knapptryckning till chatten fyra steg
  lång och behöver ingen mapp.

- **Dessutom en textmarkör, skuggor och toningar.** „Markera" färgar en
  yta utan att dölja den – innehållet under förblir läsbart, och just
  det skiljer den från strecket. „Skugga" lyfter fram en anmärkning från
  en orolig bakgrund, „Toning" låter färgen ebba ut i dragriktningen;
  båda gäller alla sex ritverktyg.

- **Åtgärdat innan det drabbade någon:** den nya verktygsraden skulle ha
  visats nästan tom för alla som redan använt Maskuro – den ihågkomna
  fönsteruppdelningen härrörde från tiden innan och skulle inte ha
  lämnat den plats. En föråldrad uppdelning förkastas nu; editorfönstret
  står då en gång med sin grunduppdelning.

- **Den egna skärmbilden går att stänga av.** Den som är van vid
  Greenshot, ShareX eller urklippsverktyget stänger under
  „Inställningar → Program" av „Ta skärmbild med Maskuro". Maskuro
  registrerar då tangentbordskortkommandot inte alls – det förblir ditt
  verktygs –, och omställningen gäller genast, utan omstart. Att rensa
  en så tagen bild går fortfarande: Ctrl+V hämtar den ur urklipp till
  fönstret.

---

## 0.10.37-alpha.20260821 – 21 augusti 2026

### Nytt

- **Vid anonymisering bär nu varje fyndställe sitt eget nummer.** Tidigare
  hette alla personer `[NAME]`, alla orter `[ORT]" – därigenom gick det
  inte längre att säga vilket ställe som hörde till vilket värde, och det
  fanns inget att hämta tillbaka. Nu räknas numren vidare per
  förekomst: samma namn står på tre ställen som `[NAME_1]`, `[NAME_3]`
  och `[NAME_7]`. I dokumentet går det fortsatt inte att se vilka ställen
  som hör ihop – men med tilldelningsfilen kan varje enskilt hämtas
  tillbaka. Tilldelningsfilen kan därför även vid anonymisering väljas
  igen; förvara den skilt från resultatet.
- **Månader, veckodagar, valutor, enheter och företagsbolagsformer på alla
  48 dokumentspråk gäller inte längre som namn eller orter.**
  Kalender- och enhetsnamnen kommer från Unicode CLDR (genererade, inte
  skrivna för hand), bolagsformerna från respektive lands bolagsrätt –
  även flerordiga („sp. z o.o.", „Pty Ltd") och framförställda
  („株式会社"). Där ett månadsnamn samtidigt är ett förnamn (Juli,
  August, May) avgör byggformen: med dag eller år bredvid ett datum,
  annars ett namn. Dessutom tilltalsformer och titlar, hela
  hälsningsfraser, dokumenttyper och gatugrundord för 28 språk med egen
  språkmodell, lagförkortningar (DSGVO, UStG, ABGB, § 6 Abs 1 Z 27 UStG)
  samt språknamn som fältvärde („Sprache: Deutsch"). Listorna finns under
  „Hjälp → Ordlistor …".
- **Indien: adress och PIN-kod identifieras** – „15 गांधी मार्ग",
  „नई दिल्ली 110001" liksom „15 Gandhi Marg, New Delhi 110001".
  Landspaketet Indien kände tidigare bara till identifieringsnummer; i
  hindi-dokument blev adresser därför kvar.
- **Varje rensad kontorsfil öppnas en gång till som paket före
  leverans.** Ett textutdrag märker inte om Word, Excel eller LibreOffice
  skulle vägra filen (dubblerad post, avrivet XML, en saknad del). Och det
  räknas mot originalet det som en rensning aldrig får ändra: sidor i ett
  PDF, blad, rader och celler i en tabell, bilder i en presentation. Slår
  provet till, står en OBS-varning i resultatet och i kontrollrapporten –
  originalet förblir oförändrat.
- **Även automatiken maskerar hela fältet.** I maskeringsläget täcker
  strecket i korta rader – adressblock, tabellcell, huvuddata – hela raden
  i stället för bara det hittade värdet: ett streck i ordlängd avslöjar
  hur långt ordet var. Beteckning och belopp bredvid blir kvar, och
  löptextrader (längre än halva textbredden) maskeras fortfarande
  ordexakt, så att ett namn mitt i meningen inte gör hela meningen svart.
- **Återhämtat ser åter ut som i originalet.** „Hämta original" och
  „Ångra ersättning" i PDF-editorn skriver nu tillbaka området exakt ur
  källfilen – samma teckensnitt, samma storlek, samma färg och läge, på
  en skanning samma bildpunkter. Tidigare sattes texten in på nytt i ett
  ersättningsteckensnitt och såg synbart återskapad ut. Strecket från en
  tidigare maskering försvinner då helt, i stället för att målas över
  vitt – en färgad cellbakgrund i en tabell bevaras. Detta gäller även
  på roterade sidor, för text ur inbäddade formulärobjekt och för
  **ifyllda formulärfält**: på den för det rastrerade arbetskopian kommer
  utsnittet ur den nyrenderade originalsidan tillbaka – även där inget
  textskikt känner till fältvärdet. Även **ersatta bilder** i PDF kommer
  på så vis tillbaka – pixlerade, suddiga eller helt borttagna, helt eller
  bara det dragna utsnittet. Bara där källfilen inte längre ligger
  bredvid resultatet förblir det vid den tidigare vägen.
- **Maskerade och ersättningsfritt borttagna värden går även att hämta
  tillbaka i Word, Excel, PowerPoint och OpenDocument.** Tidigare krävde
  återtagningen där en platshållare i texten – ett streck eller en lucka
  hade ingen återväg. Nu erbjuder träffpanelen raderna „maskerad" och
  „borttagen" så snart den orörda källfilen ligger bredvid resultatet:
  Maskuro jämför resultatet med originalet och sätter in värdet igen på
  streckets eller luckans plats – tillsammans med formatering, en
  uppdelad löpning blir hel igen. Gäller likaså text, HTML, e-post och
  kontorsbilagorna till ett e-postmeddelande; bär mejltexten en
  platshållare och bilagan ett streck, hämtas båda tillbaka i ett svep.
- **Även PDF-bilagor till ett e-postmeddelande eller
  Outlook-meddelande går att hämta tillbaka** – platshållare (numrerade
  och anonyma), streck och ersättningsfritt borttaget. Utan duk kommer
  stället från originalbilagan; tillbaka kommer värdet glyfexakt, i
  originalets läsordning.
- **Maskerade värden går att hämta tillbaka** – i PDF och i textvyn. En
  mask („**** **** **** **** 3201") är aldrig entydig, två nummer bär
  samma; därför tar återtagningen aldrig den ordagranna vägen, utan
  frågar originalet vilket värde som stod på detta ställe. Tidigare gick
  dessa rader inte alls att använda i träffpanelen.
- **Inbäddade bilder i Word, Excel, PowerPoint och OpenDocument går att
  hämta tillbaka.** Ett i bilden maskerat värde kommer tillbaka via sin
  panelrad – Maskuro läser originalbilden och hämtar exakt detta ställe;
  en suddig, borttagen eller med ansikten och koder bearbetad bild
  hämtas som helhet ur källfilen av den nya posten „Hämta tillbaka
  inbäddade bilder" i menyn Redigera – även genom kontorsbilagorna till
  ett e-post- eller Outlook-meddelande. En bild som själv hänger som
  bilaga och maskerats via textigenkänning kommer likaså tillbaka via sin
  panelrad.
- **Hittade värden går att hämta tillbaka i textvyn.** Tidigare meddelade
  panelen där „Inte entydigt". Nu söker återtagningen värdet i originalet
  och kräver på samma ställe i resultatet exakt den hittade ersättningen –
  ett hittat namn ersätts aldrig ordagrant överallt, det kan förekomma
  äkta någon annanstans.
- **Återtagning i Word, Excel, PowerPoint och OpenDocument behåller
  originalets formatering.** Stod ett värde över flera löpningar –
  „Anna" normal, „Musterfrau" fet och röd –, kom det tidigare helt
  tillbaka i den första löpningen och förlorade fetstil och färg. Nu
  fördelas tecknen igen som i originalet; ett Word-stycke är därefter
  byte för byte det ursprungliga. Detsamma gäller HTML-sidor, HTML-delen
  av ett e-postmeddelande och HTML-kroppen i ett Outlook-meddelande
  (.msg) – vid e-post bevaras dessutom doctypen, som rensningen tidigare
  tyst tog bort.
- **Textfiler behåller sin kodning.** Rensning och återtagning skriver
  nu `.txt`, `.md` och `.csv` i den kodning de levererades i – UTF-8 med
  och utan BOM, UTF-16, Windows-1252. Tidigare blev en Windows-1252-fil
  alltid UTF-8, och en UTF-16-fil kom tillbaka skadad, även om inget
  fanns att ersätta i den.
- **Återhämtade bilder behåller sitt färgläge.** En gråskaleskanning
  kommer tillbaka som gråskala i stället för en tre gånger så stor
  RGB-fil, en palett som palett, svartvitt som svartvitt – för hela
  bilden med samma värden som i originalet. Gäller bildfiler och bilder
  i PDF-filer. CMYK och 16 bitar förblir RGB, eftersom PNG-resultatet
  inte kan bära något av dem.
- **En ram i bilden hämtar tillbaka hela den bearbetning den berör.**
  Pixlerade ansikten bär en kant runt den identifierade rutan; den som
  bara drog ramen över ansiktet behöll en pixlerad ring. Nu växer ramen
  till den sammanhängande förändringen mot originalet – en ram över
  ögonpartiet räcker. Separata streck bredvid blir kvar; vid ett helt
  borttaget eller helt suddat foto gäller fortfarande den dragna ramen.
  Gäller bildfiler och bilder i PDF-filer.
- **Maskeringsstreck över hela raden.** I radläget i editorn löper
  strecket nu från första till sista ordet på raden, inte längre bara
  över det träffade ordet – ett streck i ordlängd avslöjar hur långt
  ordet var, och ur sex tecken framför ett postnummer går det att gissa
  ett ortnamn. Beteckningar, belopp och tabellkolumner bredvid värdet
  blir kvar – strecket täcker fältet, inte fakturans rad. Den nya
  brytaren „Hela raden" bredvid „Textrader" ställer om till ordexakt
  igen om grannorden ska bli kvar; valet kommer ihåg.

### Rättat

- **Bilder i HTML-sidor och e-post förblev okontrollerade – namnet i
  logotypen stod läsbart kvar efter rensning.** En i sidan inbäddad bild
  (``data:``-adress) rördes inte alls, bara dess alternativtext;
  logotypen i HTML-grenen av ett mejl (inline-bild utan filnamn) föll
  igenom bilagefiltret; och vid den namngivna bildbilagan hade
  bildregeln „sudda"/„ta bort" ingen effekt. Nu går alla tre samma väg
  som en bildfil: textigenkänning i den bevarade bilden, ansikten, koder,
  metadata och bildregeln. Rapporten nämner bilderna – även varningen om
  de förblir okontrollerade utan textigenkänning –, och „Hämta tillbaka
  inbäddade bilder" samt återtagningen från träffpanelen känner till
  dessa bilder också.
- **En kontorsfil med bild gick inte alls att rensa om textigenkänningen
  inte behärskade språket.** På Mac läser den systemegna
  textigenkänningen; för hindi, grekiska, kroatiska eller litauiska kan
  den det inte och säger det sedan nyligen också – vid Word, Excel,
  PowerPoint och OpenDocument avbröt då **hela** rensningen, och ingen
  fil skapades. Ändå gick texten att rensa utan problem; bara bilden var
  oläslig. Nu skrivs filen som vid PDF och enskilda bilder, och i
  resultatet står att bilderna INTE kontrollerats – med orsaken och
  hänvisningen till „Hantera språk".

- **I Excel-arbetsböcker blev namn kvar i urvalslistor.** Listan i ett
  dropdown-fält (datavalidering) rensas nu som allt annat cellinnehåll;
  referenser till cellområden rörs inte, så att arbetsboken förblir hel.
- **Där platshållaren inte fick plats stod ett svart streck – nu står en
  kortare skrivform där.** `[GEBU_1]` i stället för `[GEBURTSDATUM_1]`,
  och först när inte ens den kortaste formen får plats maskeras det. Ett
  streck säger inte längre till någon att något stod där; en kort
  platshållare gör det. Efterbearbetningseditorn kunde redan det, den
  automatiska rensningen tidigare inte. Tilldelningsfilen listar båda
  skrivformerna under samma värde, så att även den förkortade går att
  hämta tillbaka.
- **Det första klicket på „Ersätt" lät efterbearbetningsfönstret stå
  kort.** Igenkänningen som ger platshållaren dess typ (`[NAME_3]" i
  stället för `[BEGRIFF_3]") laddades först i det ögonblicket – cirka två
  till tre sekunder. Den förbereds nu i bakgrunden när fönstret öppnas;
  uppmätt har 2289 millisekunder blivit 193.
- **Två samtidiga rensningar kunde ladda samma språkmodell dubbelt** –
  till exempel mappövervakningen och huvudfönstret. Eftersom varje
  modell tar flera hundra megabyte i anspråk, stod minnesbehovet
  därigenom tillfälligt på det dubbla. Nu väntar den andra körningen på
  den första körningens modell.
- **Orten i datumraden tas nu bort även när språkmodellen inte
  identifierar den ensam:** vad som med säkerhet hittats som postnummer
  med ort („3335 Amstetten") drar sitt ortnamn med sig i hela dokumentet
  – som ett efternamn ur ett fullständigt namn. Och en förkortning med
  siffra framför ett namn („T3 Hofbauer Christian") förblir läsbar, i
  stället för att försvinna med i platshållaren.
- **Tre läckor från andraläsningen av en verklig order tätade:**
  handläggaren „T3 Hofbauer Christian" gällde på grund av förkortningen
  „T3" som kolumnhuvud och förblev läsbar; en ort som språkmodellen läste
  över radbrytningen in i kolumnhuvudet slukade „Pos." och lämnade
  kundens förnamn kvar; och ett namn med tilltalsform („Herr Robert
  Köttel") drog bara med sig efternamnet, inte förnamnet – och därtill
  varje „Herr". Förkortningar är nu rena bokstäver, tvåordsnamn inget
  kolumnhuvud, träffar skärs av före ett kolumnhuvud, och tilltalsformen
  räknas inte till namnet.
- **Orten i datumraden („Melk, 05.08.2026") direkt under adressblocket
  förblev läsbar.** Språkmodellen klistrade ihop den med orten i
  postnummerraden till en enda träff, och den föll som helhet mot
  postnummermönstret. Nu förblir den utstickande resten en egen träff.
  Hittad genom den nya andraläsningen av resultatet
  (`werkzeuge/zweitlesung.py`).
- **Mac: en skanning på ett språk som den systemegna textigenkänningen
  inte behärskar (till exempel hindi, grekiska, kroatiska, litauiska)
  gällde som kontrollerad.** Läsningen skedde med den engelska
  reservlösningen, den främmande skriften blev kvar i bilden, och
  rapporten sa „inget hittat". Nu heter det „Bild(er) har INTE
  kontrollerats" med orsaken, och språkhanteringen lovar inte längre
  textigenkänning för sådana språk bara för att en Tesseract-språkfil
  finns.
- **I PDF-filen blir skiljetecknet bakom ett ersatt ord kvar.** Ur
  „Aufnahme am 01.03.2026, Entlassung am 04.03.2026." blev tidigare
  „Aufnahme am [DATUM_1] Entlassung am [DATUM_2]" – kommat och
  slutpunkten saknades, vid platshållare liksom vid förskjutna datum.
  Nu tas bara det identifierade värdet bort, inte hela ordet fram till
  nästa mellanslag; komma, semikolon, punkt eller parentes efter blir
  kvar på sin plats, och platshållaren löper inte över dem.
- **Ryska och ukrainska kördes obemärkt med den svagare
  flerspråksmodellen**, om ett hjälppaket för ordformsanalys
  (`pymorphy3`) saknades – de egna modellerna gick då inte att ladda,
  och „Львів" blev en person. För igenkänning av namn behövs inte
  ordformsanalysen; modellen laddas nu utan den, och orter är åter
  orter.
- **Licenshänvisningarna på 16 språk var på gammal nivå.** Där stod
  fortfarande att MPL-källkoden tillhandahålls „på begäran", QPDF gällde
  som MPL-2.0, sju byggstenar saknades i tabellen (wordfreq, Qt, ONNX
  Runtime, tokenizers, zxing-cpp, llama.cpp, YuNet), spaCy-stycket var
  engelskt, och på slutet hängde ett engelskt ersättningsavsnitt. Nu
  ligger alla 18 versioner på den tyskas nivå: källarkiv varaktigt under
  maskuro.com/quellcode/oss/, QPDF Apache-2.0, Qt-LGPL-väg,
  modellursprung. Även den engelska tabellen har de saknade raderna.

- **Avtalsord i genitiv („des Angebotsinhaltes", „des Anbotes", „des
  Terminplanes") gäller inte längre som ort.** Ett enskilt ord bakom en
  genitiv- eller dativartikel med böjningsändelse är ett sakord –
  ortnamn böjs inte („nach Graz"). Står orten på annat håll i dokumentet
  utan artikel („Burgenland"), identifieras även „des Burgenlandes".
- **Förskjutna, maskerade och hittade värden rastrerade PDF-sidan.**
  Efterkontrollen efter borttagning tillät i fyndrektangeln bara en
  platshållare i hakparenteser; ett förskjutet datum („01.07.2026") eller
  ett maskerat värde („****1234") gällde som förbisedd rest, och sidan
  omvandlades av säkerhetsskäl till en bild – inte vid „Ersätt". Nu
  förblir sådana sidor text, och återhämtningen från panel eller ram
  levererar åter originalet.
- **Flerordiga ersättningsvärden gick inte att ångra i PDF-filen via
  träffpanelen.** Ett hittat namn („Greta Mayrhofer") eller en maskerad
  IBAN („**** **** **** **** 3201") består av flera ord; fyndställessökningen
  jämförde ord för ord och meddelade „Platshållaren hittades inte i
  dokumentet". Nu läses på varandra följande ord på samma rad ihop.
- **Efter återhämtning av ett ersättningsfritt borttaget värde blev dess
  panelrad kvar.** Värden som strategin „maskera" tar bort utan ersättning
  i platshållarläget har ingen platshållare som panelen kunde mäta ett
  försvinnande mot. Nu stryks raden så snart värdet åter står i
  dokumentet.

- **Förkortningssammansättningar som „E-Helfer" eller „U-Bahn" gäller
  inte längre som namn.**
- **Avstavningsrester („Leis-") och överlånga sammansättningar
  („Bauarbeitenkoordinationsgesetzes", „Baustellenkoordinator") gäller
  inte längre som namn eller ort.** I en skannad anbudstext maskerades
  därigenom 28 ord färre.
- **Positionslistor i skannade offerter gäller inte längre som
  namnförteckning.** Tilläggsgenomgången för förteckningar (korta rader)
  gjorde av „Kälterohr" och „Außengeräte" personer; den kopplas nu ur så
  snart positionsnummer som „1.1.5" står i radbörjan. Datumrader i
  mejltrådar räknas därvid inte som positionsnummer.
- **Kolumnhuvuden och positionsnummer i skannade offerter („Pos.",
  „Pos. 1.1.3", förkortningarna „E/L/S") gällde som namn eller ort.** En
  ensam förkortning på sin egen rad, en beteckning tillsammans med
  nummer och enskilda bokstäver radvis är det inte.
- **Sidan „andades" i efterbearbetningsfönstret efter att
  jämförelseluppen öppnats** – vid „Sidbredd" och „Anpassa" hänger
  skalan på visningsfönstret, och det ändras med varje rullningslist som
  kommer eller går; varje efterföljande åtgärd flyttade sidan ett stycke.
  Duken drar nu automatiskt med det tills det står stilla. Och
  zoomknappar, reglage och tangentbordskortkommandon behåller bildmitten
  även när en rullningslist visas vid inzoomning.
- **Tvärt lagrade skanningar läses nu upprätt, och finstilt text i stora
  skanningar går inte längre förlorad.** En 24-sidig skannad offert
  behöll i varje sidfot sex bank-IBAN, organisationsnummer och
  momsregistreringsnummer läsbara: skanningen låg i PDF-filen roterad
  90°, och textigenkänningen hoppade beroende på bildstorlek över hela
  rader vid mycket stora bilder. Nu tas den synliga rotationen med i
  beräkningen, och stora bilder läses i överlappande band – sidfötterna
  är svarta.
- **Gator efter personer med bindestreck framför grundordet („Josef
  Admanseder-Straße 7", „Abt-Karl-Straße 8", „Dr.-Karl-Renner-Straße 12")
  identifieras som adress.** I brevhuvudet på en skannad offert förblev
  en sådan adress läsbar, eftersom mönstret krävde ett mellanslag framför
  „Straße".
- **IBAN-nummer ur textigenkänningen som bär ett O i stället för 0 eller
  ett l i stället för 1 identifieras nu.** I finstilt text på en
  skanning läser textigenkänningen gärna siffror som bokstäver; numret
  hade då formen av en IBAN, men kontrollsumman gick inte ihop, och det
  blev kvar. Misslyckas kontrollsumman, provas nu tolkningen med
  siffror – stämmer den då, är det IBAN-numret. Felaktiga
  kontrollsiffror förblir felaktiga.
- **Satsdelar som „folgenden Codes auf der" gällde som ort.** Ett namn
  eller en ort som börjar med ett gement ord är inget – utom vid
  adelspartiklar („van Gogh", „de Vries").
- **I editorn blev sista bokstaven kvar bredvid maskeringsstrecket**
  („…6", „…t", „…g"), och strecket hade den dragna ramens höjd i stället
  för radens. Orsak: kunde editorn inte mäta sidan, ansåg den varje ram
  vara „inget ord träffat" och tillämpade den exakt – utan regeln att ett
  halvt ord aldrig blir kvar. Detsamma hände vid enskilda textkommandon
  som editorn inte kunde lokalisera. Nu räknas alltid ordrutan med
  därutöver: vad ramen väsentligen överlappar faller helt.
- **Sista bokstaven i ett ord stack ut över maskeringsstrecket.**
  Strecket mättes efter förskjutningsbredden ur teckensnittsmåtten;
  ritar teckensnittet en glyf bredare, stod dess rest bredvid strecket.
  Ett teckens ruta tar nu även upp den ritade glyfen.
- **Meddelandet om att omvandla en sida till bild lovade för mycket.**
  „Utseendet förblir detsamma" stämmer inte efter rastrering: teckensnitt
  och grafik är då bildpunkter, filen blir större. Meddelandet säger nu
  det – och nämner även den andra orsaken till att rastrering sker
  (ombyggnaden skulle ha skadat sidan).
- **Texten bakom ett borttaget värde flyttade upp till en punkt åt
  vänster.** Vid ombrytning av en rad mättes början vid glyfkanten,
  fortsättningen vid pennursprunget – förskjutningsbredden hos första
  bokstaven blev kvar som ett fel („C" 0,5 pt, „I" 1,0 pt). Ombrytningen
  räknar nu genomgående med pennursprunget; efterföljande text står på
  tiondels punkten på sin plats.
- **Österrikiskt momsregistreringsnummer med mellanrum („ATU 187 35901")
  och ett organisationsnummer utan „FN" under sin beteckning
  („Firmenbuchnummer: 30799v") identifieras.** Båda stod handskrivna på
  ett skannat upphandlingsformulär och förblev läsbara, trots att
  textigenkänningen läst dem rätt.
- **Liggande PDF-sidor omvandlades utan anledning till bild efter
  maskering.** Integritetskontrollen jämförde original och resultat i
  den roterade visningen, men räknade sina maskeringszoner oroterat – på
  en sida med rotationsanteckning låg den egna maskeringen därför bredvid
  sin zon och gällde som skada. Sådana sidor behåller nu sitt textskikt
  och sin vektorgrafik.
- **Även raka sidor omvandlades emellanåt utan behov till bild**, när
  texten bakom en platshållare flyttade en punkt – tillåtet, men
  bildjämförelsen var finare än sin egen tolerans. Den jämför nu i
  halva punkter och träffar därmed sin tolerans exakt: upp till två
  punkters förskjutning slår inget larm, däröver alla.
- **Uppgifter i inbäddade formulärobjekt blev kvar.** Vissa mallar lägger
  brevhuvud eller brevavslutning som ett eget formulär som sidan bara
  bäddar in. En träff i det planerades visserligen och räknades som
  borttagen, men skrevs aldrig – texten stod fortfarande kvar, och bara
  rastreringen av hela sidan fångade den. Nu skrivs själva formuläret om;
  ett formulär som ligger på flera sidor, en enda gång.
- **PDF-sidor rastrerades till bild trots att inget läsbart blivit
  kvar.** En sjusidig offert drabbades på sex sidor; den växte från 73 kB
  till 3,3 MB och förlorade sin text till en avbild. Orsaken var
  mellanslag som står flera gånger i rad i dokumentet men bara meddelas
  en gång av läsaren: texten bakom en borttagen uppgift flyttade dess
  bredd åt höger, efterkontrollen hittade grannordet i fyndrektangeln och
  grep till rastrering. Bevarade radrester står nu åter exakt på sin
  plats; samma offert rensas nu utan en enda rastrerad sida (76 kB).
- **Nyckelnamn och fakturahuvuden gällde som personer.** I en åtkomstfil
  ersattes namnet på miljövariabeln („AWS_ACCESS_KEY_ID"), inte bara dess
  värde; på en engelsk faktura föll rubriken „Bill to" som förnamn. En
  identifierare i versaler med understreck är aldrig ett namn, och ett
  ord på en rad som som helhet är en fältbeteckning inte heller –
  mottagaren under den identifieras fortfarande.
- **Sökningen i efterbearbetningsfönstret stockade sig vid stora
  PDF-sidor.** Varje bokstav i sökfältet lät sidan rastreras på nytt,
  trots att bara markeringen ändrades. Den renderade sidbilden förblir
  nu stående så länge sida, zoom och vy är desamma – även originalet i
  jämförelseluppen; bläddring, zoomning och ett nytt filläge ritar
  fortfarande om på nytt.
- **Positionsnummer i offerter gällde som IP-adress eller
  telefonnummer.** En artikelrad som „1.3.3.4 … 5-Port Gigabit Switch"
  gjorde att strukturnumret blev en nätverksadress, eftersom „Port"
  räknades som teknisk omgivning – nu räknas det bara som fristående
  uppgift („Port 80"), inte som orddel. Och „1.3.3.6 216879"
  (positions- plus artikelnummer) maskeras inte längre som
  telefonnummer. Riktiga IP-adresser och telefonnummer i sådana listor
  identifieras fortfarande.
- **Artikelrader i offerter gällde som postnummer med ort.**
  „35252 DIETZEL SALR" (artikelnummer med tillverkare) och „1000 AWG"
  (mängd med ledartvärsnitt) maskerades i numrerade positionsrader som
  adress, eftersom ett versalord bakom ett tal gällde som ortnamn i
  versaler. I positionslistor gäller det inte längre; „1080 WIEN" i
  adressblocket och orter med gemener identifieras överallt fortsatt.
- **Den extra namnigenkänningen maskerade rollrader och kolumnhuvuden i
  offerter.** „Partiestundensatz Monteur + E-Helfer" gällde 49 gånger som
  person, kolumnhuvudet „Pos. Bezeichnung Menge EH" 19 gånger som ort –
  en 19-sidig order blev därigenom oläsbar. Sådana träffar i
  positionsrader faller nu om de själva bär tecken som inget namn har
  (plus, snedstreck, siffra, förkortning) – även när raden slutar med ett
  belopp („Alternativ Markt … - PV/LS AC-Versorgung 1 290,00"). Namn i
  förteckningar och listor – vad nivån finns till för – berörs inte.
- **„Der Kunde" gjorde i affärsvillkor varje „Kunde" till ett namn.** Tog
  den extra namnigenkänningen med artikeln i träffen, gällde den som
  tvådelat namn och skyddade alla 35 ytterligare ställen med samma ord.
  Nu dras artikeln bort, och „der Kunde" faller liksom redan „des
  Kunden".
- **Beteckningar gällde som värde.** „E-Mail" maskerades sju gånger som
  e-postadress, „Telefonnummer" och „Faxnummer" som telefonnummer. En
  adress utan @ och ett telefonnummer utan siffror räknas inte längre.
- **Kolumnförkortningar av en bokstav („L: 154,50", „S: 0,00") gällde som
  namn** – 25 gånger i en solcellsoffert. En ensam bokstav är varken namn
  eller ort.
- **PDF-sidor omvandlades alldeles för ofta till bild.** Två orsaker,
  båda hittade i verkliga offerter: sätter ett PDF-dokument varje glyf
  som eget kommando och gömmer sig ett mellanslags-glyf utan texttecken
  under det, förskjöts tilldelningen från den punkten med ett – av det
  borttagna värdet blev sista bokstaven kvar („ŠkodaTopCar**d**"), och
  efterkontrollen rastrerade sidan med rätta. Och ett vid radslutet
  avstavat ord („Datenschutz-") gällde på grund av läsbibliotekets
  avstavningsmarkör som förskjutet. Båda åtgärdade: en fordonsoffert gick
  från 4 rastrerade sidor till 0, en 19-sidig order från 7 till 0 –
  texten förblir text, filen förblir liten.
- **Två ytterligare rastreringsorsaker åtgärdade:** har ett dokument
  själv ett teckensnitt vid namn „F1" med sig, sattes platshållarna över
  bilder i dess teckensnitt och var oläsliga – nu får det egna
  beteckningstypsnittet ett ledigt namn. Och saknar läsbiblioteket ett
  mellanslag mitt i ett långt textkommando, bevisas stället nu även vid
  flerbytetecken (samma kod, samma tecken) i stället för att hamna
  längst bak – tidigare blev en bokstav av det borttagna värdet kvar och
  resttexten flyttade synligt åt sidan. Dessutom två sista fall: ett
  kommando med dussintals mellanslags-glyfer lät tilldelningen springa i
  väg (namnet därefter blev kvar), och en stor rubrik med
  förskjutningsbredd hittade inte sitt första tecken (företagsnamnet blev
  kvar). **Av nio verkliga offerter rastreras nu inte en enda sida
  längre** – tidigare var det 30 av 90.
- **Vid rastrering försvann bilder under ett svart block.** Måste en sida
  omvandlas till bild, renderas den ur originalet – och det känner ingen
  bildrensning till. Tidigare föll därför *varje* bildyta på sidan under
  ett streck, även oberörda. På en offert satt adress och två
  certifikatslogotyper i samma brevhuvudbild; strecket tog med sig
  logotyperna. Nu sätts den redan rensade bilden in: adressen i den är
  maskerad, allt annat förblir synligt. En borttagen bild lämnar vitt
  papper i stället för en svart ruta.

- **Rensade skanningar blev flera gånger större än originalet.** Varje
  bild där något maskerats gick tillbaka i filen som en okomprimerad
  rådata-bild – vid en 24-sidig skanning växte den därmed från 11,8 till
  52,9 MB. Bilder behåller nu den art de förelåg i: ett foto förblir ett
  foto, en faxskanning förblir svartvit, en färglös bild lagras inte som
  färgbild. Samma fil är nu 15,6 MB stor, utan synlig skillnad.

- **Skannade PDF-filer från kontorsutrustning kom tillbaka som
  randmönster.** Sådana skanningar lägger texten som ett skarpt
  svartvitt skikt över en grov färgbild – Canon, Xerox och Kofax bygger
  sina filer så. Vid maskering i bilden skrevs detta skikt tillbaka fel;
  resultatet blev oläsligt. Vid en sexsidig offert drabbade det nio av
  sexton bilder. Den behandlas nu korrekt, i sin egen färg, och de
  maskerade ställena är verkligen borta i den.

- **„Ta bort alla bilder" tog textet från en skannad sida.** Textskiktet
  hos en sådan skanning är tekniskt en bild – det togs bort respektive
  suddades med, och kvar blev ett tomt blad. Det blir nu kvar; logotyper,
  stämplar och underskrifter viker fortfarande undan.

- **Kontrollen av skadade PDF-sidor rastrerar inte längre på grund av en
  liten förskjutning.** Ett vid rensning nyförankrat textstycke får
  förskjutas upp till två punkter; bildjämförelsen räknade det ändå som
  skada och byggde om sidan som avbild – därvid gick vektorgrafik som
  tabellinjer förlorad, och över fyndställen låg ett streck i stället för
  en platshållare. Jämförelsen tillåter nu samma lilla förskjutning som
  ordkontrollen; verkliga skador märks fortfarande.

- **Återhämtning av många värden efter varandra misslyckades inte längre
  på Windows med „Åtkomst nekad".** Den som i en kontorsfil återtog många
  panelrader tätt efter varandra kunde misslyckas på grund av en
  kortlivad filspärr från virusskannern; utbytet väntar nu kort in
  sådana spärrar.

- **Windows-vägen för kommandoöverföring avslutade kontrollanten i
  stället för att kontrollera.** Livskontrollen av den lyssnande
  instansen skickade på Windows av misstag ett riktigt Ctrl+C till sin
  egen konsolgrupp; den frågar nu systemet utan signal.

- **Flerordiga fältbeteckningar hade ingen effekt, däremot deras
  fragment.** „Date of birth", „Bank account", „Cuenta bancaria" och
  „Numero de cliente" stod i beteckningslistan, men delades där upp i
  enskilda ord och träffade därför aldrig; kvar blev ordfragment som „de"
  och „of", som sedan dess gällde som beteckning – „de" är dock en
  namnbeståndsdel („Anna de Vries"). Båda är åtgärdade: uttrycken verkar
  nu som helhet, fragmenten är borta.

- **Tyska hälsningsfraser med „ß" behandlades trots inträdet som
  personnamn.** Under „Herzliche Grüße" eller „Mit freundlichen Grüßen"
  stod i resultatet en platshållare, trots att båda uttrycken sedan
  länge stått i motlistan. Orsaken var en skrivform som aldrig kom fram
  vid jämförelsen; berörda var åtta poster över fem listor. De verkar nu
  alla.

- **„John Staff" förblev oersatt.** Ett efternamn som samtidigt är en
  engelsk kolumnrubrik förkastades tillsammans av beteckningsfiltret.
  Rubriken förblir fortsatt orörd, namnet under den ersätts åter.

- **Värden ur betecknade formulärfält förblir skyddade i KI-nivån.** Den
  lokala skiljedomaren i KI-nivån fick tidigare även träffar förelagda
  för bedömning vars betydelse redan bevisats av fältbeteckningen
  („Geburtsdatum:" ovanför värdet) – och fick förkasta dem. Sådana
  strukturellt belagda värden förelås den inte längre. Tilldelningsfilen
  nämner nu dessutom för varje ersättning igenkänningsvägen („belägg").

- **En PDF-sida vars bevarade text tog skada vid rensning identifieras nu
  och byggs om som en avbild av originalet.** Vid vissa
  skaparteckensnitt kunde bevarade textställen efter rensningen visas
  som svarta block eller ord flyta ihop, trots att alla uppgifter som
  skulle tas bort togs bort korrekt. Maskuro jämför nu resultatet ord för
  ord och bildpunkt för bildpunkt med originalet; en skadad sida ersätts
  med sin rena avbild – med maskeringsstreck över fyndställena, maskerade
  bildområden och sökbar text. Sidan förblir läsbar, borttagningen
  tillförlitlig.

### Ändrat

- **I de översatta gränssnitten heter varje facktermer nu likadant
  överallt.** För ett och samma tyska ord stod beroende på fönster två
  eller tre översättningar bredvid varandra: kontrollprotokollet hette på
  norska dels „Revisjonslogg", dels „Kontrollogg", gratisnivån dels
  „Gratisnivå", dels „Gratisversjon" – och likadant i ett dussintal andra
  språk. Den som sökte en inställning hittade den i nästa fönster under
  ett annat namn. Enhetligheten sattes på det ord som gränssnittet ändå
  använder oftast.

  Därvid kom ställen i dagen där ett ord stod för två **olika** saker:
  franska, grekiska och koreanska använde för „maskera" och „maska"
  samma uttryck – alltså just där programmet förklarar skillnaden
  („Maskera tar bort utan ersättning, Maska behåller formen"). Båda är
  nu åtskilda. För svenska är detta beslut ännu inte fattat: där heter
  maskeringen „maskera" – samma ord som maskningen.

- **Frågan om användningsart vid första start har utgått.** Strax efter
  start kom ett fönster („Privat eller i verksamhet?"), och i
  inställningarna stod en rad om det. Båda finns inte längre – utan
  ersättning. En uppgift som inget hänger på anger fel om vem som vill
  ha vilken licens, och den ärlige behöver den inte; den kostade var och
  en ett klick vid en tidpunkt då ingen tänker på licenstyper. Vilken
  licens som är den rätta står där den avgörs: på prissidan, i kassan
  och i hjälpen. Organisationer som rullar ut Maskuro centralt anger
  fortfarande användningsarten via vorgabfilen.

- **Hänvisningarna om licenstyp nämner det fall det gäller.** Privatlicensen
  gäller uteslutande privat användning; allt yrkesmässigt eller
  kommersiellt arbete kräver företagslicensen – även som enskild
  näringsidkare utan anställda. Det stod så i licensvillkoren, men varken
  i programmet eller i hjälpen: där talades det bara om företagsdomänen,
  och den täcker inte just detta fall: en egenföretagares dator hör inte
  till någon domän. Hänvisningen vid inläsning av en privatlicens säger
  det nu, likaså handbokens licenskapitel och de vanliga frågorna, som
  fått en egen post för det. Inget spärras fortfarande.

- **De ännu inte utlevererade vägarna ligger nu tillsammans.**
  Inställningarna har fått en sida „Utvecklare"; där står den maximala
  igenkänningen (KI) med sin kontrollprövning, ordlistekatalogen och
  mappövervakningen. Alla tre är byggda, men inte prövade i fält – de är
  därför bara synliga med en utvecklarlicens, och det överallt samtidigt:
  sidan, menyposterna och effekten i körningen hänger på samma beslut.
  Utan denna licens förblir en tidigare påslagen KI-nivå verkningslös;
  dess inställning raderas inte och gäller igen så snart vägen levereras.

### Förbättrat

- **„Vad som söks" visar tre ytterligare listor från namnigenkänningen.**
  Tilltalsformerna efter vilka det följande ordet läses som ett namn;
  titlarna och rollerna som därefter **inte** är namnet („Herr
  Bürgermeister Huber"); och de åttio flerspråkiga beteckningarna som
  diarienummer, ärende- och fallnummer identifieras genom. Alla tre har
  alltid haft effekt, men syntes inte i översikten.

- **„Vad som söks" visar två tidigare saknade ordlistor.** Tilltalsformerna
  och titlarna som gör ett föregående ord till ett namn („Herr", „Frau",
  „Dr."), och förkortningarna för standardiseringsorganisationer som
  Maskuro använder för att skilja en normhänvisning som „ÖNORM B 2110"
  från en person. Båda påverkar igenkänningen sedan länge, men stod inte
  i översikten.

- **Positionslistor, innehållsförteckningar, utrustningsuppräkningar och
  normhänvisningar förblir läsbara.** Igenkänningen ser nu radens
  byggform: ett gissat namn i en strukturrad („1.3.1 Energieerdkabel
  1kV"), en förteckningsrad med ledpunkter, en uppräkning
  („- kabelloses Laden mit Magnetring"), ovanför en mängd-/prisrad, i ett
  kolumnhuvud eller bakom „mittels" är ett sakbegrepp och ersätts inte
  längre. Riktiga namn förblir skyddade – genom tilltalsform,
  fältbeteckning och belägget på annat håll i dokumentet; i mätkorpuset
  förlorade ingen enda uppgift sitt skydd. I affärskorpuset sjunker de
  falska larmen därmed från 25 till 6.

- **Rubriker, formulärbeteckningar och hälsningsfraser tas mer sällan för
  namn – på tyska och engelska.** Ordlistorna som Maskuro använder för
  att skilja sakord från personnamn har vuxit betydligt: beteckningar
  från fakturor, formulär och myndighetspost („Aktenzeichen",
  „Verwendungszweck", „Kostenstelle", „Sort code", „Subtotal"),
  avsnittsrubriker i ansökningar och rapporter („WERDEGANG",
  „QUALIFIKATIONEN", „SUMMARY", „REFERENCES"), tyska och engelska
  dokumenttyper („Auftragsbestätigung", „Niederschrift", „Timesheet",
  „Agreement") samt kommandoformer ur anvisningar („Sende…", „Select…").
  Den engelska sidan var tidigare påfallande tunt besatt.

- **Betecknade fält avslöjar nu också vad som står i dem när beteckningen
  är sammansatt.** „Lieferanschrift", „Rechnungsadresse",
  „Sachbearbeiterin", „Kontoinhaber", „Contact person" och
  „Billing address" tilldelar nu värdet bredvid eller under samma typ
  som det enkla „Anschrift" eller „Name" – i ett ifyllt formulär med
  rutor är det skillnaden mellan hittat och förbisett.

- **I efterbearbetningsfönstret bläddrar mushjulet vidare vid
  sidkanten.** Den som rullar vidare vid slutet av en sida hamnar
  överst på nästa; den som rullar tillbaka vid början hamnar underst på
  föregående – ett dokument går därmed att rulla igenom från början till
  slut utan att röra sidknapparna. Tangentbordet (Bild upp/Bild ner)
  kunde redan det; en kort andningspaus mellan två sidbyten hindrar att
  en styrplattas eftersläpning bär genom halva dokumentet.

- **Sidminiatyrerna i efterbearbetningsfönstret sitter mitt i facket.**
  Tidigare klibbade de vid vänsterkanten, och vid breddning växte bara
  den tomma marginalen till höger.

- **Verktygsfältet i efterbearbetningsfönstret visar sina grupper.**
  Skiljestrecken har nu luft och färg, „Sök" och „Överför till alla
  sidor" står som egna grupper bredvid verktygen, och „Överför" visas
  bara vid dokumenttyper där det kan ha effekt. Varje post i fält och
  menyer bär nu en bild: „Textrader" och jämförelseluppen har fått egna
  symboler (luppen delade tidigare sin med „Före/Efter"), dessutom zoom,
  hela sidan, sidbredd, rotera, bläddra och tangentbordskortkommandona.
  „Öppna med systemprogram" står nu även i fältet bredvid Skriv ut –
  vägen från det färdiga resultatet till det vanliga programmet är ett
  klick, ingen menygenomgång.

- **Vid urklippsrensning står det åter med att kontroll krävs.** I
  inställningarna finns hänvisningen varaktigt bredvid brytaren: Maskuro
  kan förbise personuppgifter eller hantera uppgifter fel, den inklistrade
  texten bör ses igenom före vidarebefordran. Vid påslagning nämner
  meddelandet det dessutom, och det antecknas i utmatningsområdet – även
  när ingen ikon körs i meddelandefältet. Vid varje enskild
  kopieringsprocess visas det medvetet inte: en hänvisning som kom
  femtio gånger om dagen skulle inte längre läsas efter tredje gången.

## 0.10.36-beta.1 – 20 augusti 2026

### Förbättrat

- **Tekniska affärsdokument söndermaskeras inte längre.** Fyra
  igenkänningsbromsar, framtagna ur elva verkliga offerter och order:
  strukturnummer („1.3.1.1") gäller inte längre som IP-adresser,
  normhänvisningar („ÖNORM EN 62446") och identifieringskoder inte längre
  som postnummer eller telefonnummer, och rollord bakom artiklar („der
  Kunde", „des Auftraggebers") inte längre som namn – i affärsvillkoren för
  en verklig offert är därmed alla 46 rollord åter läsbara i stället för
  maskerade. Adresser med landsbeteckning („A 3390 Melk", „D-94032
  Passau") tas nu bort fullständigt, i stället för att lämna postnumret
  kvar som en föräldralös rest.

- **Ordlistor kan nu granskas fullständigt.** Under „Hjälp → Ordlistor …"
  går de lokalt använda igenkännings- och kontrollistorna att genomsöka
  tillsammans med språk, syfte, källa och innehåll. Dit hör även
  wordfreq-, medicin-, personliga och centralt hanterade listor samt
  lagren för hittade ersättningsvärden. Handboken beskriver katalogen i
  ett eget avsnitt.

- **Färdiga filrader visar det använda igenkänningsspråket.** Bakom
  „klar" står nu till exempel „Tyska" eller „Engelska", så att ett
  olämpligt automatiskt språkval genast märks. Fick ett annat installerat
  språk hoppa in, visar en pil båda språken.

- **Den nya jämförelseluppen visar genast rätt ställe i originalet vid
  genomläsning.** Dess förstorade originalutsnitt följer muspekaren över
  det fortfarande redigerbara resultatet; vid text följer det stycket.
  Luppen kan användas vid fönsterkanten eller dras ut som ett eget,
  maximerbart fönster. Dess zoom går att ställa in direkt mellan 50 och
  300 procent och kommer ihåg lika väl som påslagningen. „Återställ" tar
  även en maximerad eller ogynnsamt dockad lupp tillbaka till vänster i
  en hanterbar storlek. Ersatta originalvärden är gulmarkerade i luppen,
  så att de berörda orden genast sticker ut vid läsning. Väl aktiverad
  öppnar den sig igen vid framtida lämpliga dokument – även efter en
  omstart av programmet. Den tidigare före/efter-växlaren finns kvar i
  Visa-menyn. Handboken beskriver den i ett eget avsnitt.

- **Öppen källkod- och modellbelägg är nu releaseexakta.** Paketbygget
  skapar en maskinläsbar komponentlista tillsammans med hashvärden för de
  medföljande licenstexterna. MPL-källor, modellursprung, fasta
  revisioner, ändringar och SHA-256 dokumenteras separat; nedladdade
  modeller får sitt ursprungsbelägg direkt i modellmappen. Rörliga
  Tesseract- och spaCy-källistor har fästs fast. Försäljningsartefakter
  förblir spärrade tills alla källor och modellbilagor är publicerade och
  kontrollerade.

- **Det lokala wordfreq-databeståndet är fullständigt licensbelagt.**
  Paketbygget kontrollerar version 3.1.1, 39 oförändrade små listor
  inklusive CJK och den kinesiska teckenkartan mot antal, storlek och
  manifestkontrollsumma. Apache-2.0-kodhänvisning, fullständig
  CC-BY-SA-4.0-licens, tillskrivning, datakällor och de utelämnade stora,
  Jieba- och icke stödda listorna är dokumenterade i paketet.

- **Vanliga satsord maskeras nu mer sällan av misstag.** En lokal
  frekvensordbok fungerar som extra kontroll när namnigenkänningen tar ett
  verb, pronomen, en artikel eller en preposition för en person.
  Ordboken avgör aldrig ensam: substantiv, flerdelade namn samt namn i
  fält, listor och efter tilltalsformer förblir skyddade. Kinesiska,
  japanska och koreanska använder uteslutande exakta tokengränser från
  sina redan befintliga språkmodeller; för icke befintliga språk sätts
  ingen skenbart liknande ordboksspråk in. För detta överförs ingen
  dokumenttext till internet.

- **Tekniska produkt- och utrustningsbegrepp tas nu mer sällan för namn
  eller orter.** Den lokala kontrollen förenar nu frekvens, ordklass,
  teknisk ordbildning och sakfält. Därigenom förblir till exempel
  „Travel-Assistent", „Family-Bonus", „WLTP-Wert", „Easy-Start" och
  sammansatta nummer-, hållar- eller bromsbegrepp kvar i dokumentet.
  Engelska beståndsdelar slås även upp lokalt i tysk facktext; äkta
  egennamn, tilltalsformer samt person- och ortsfält behåller företräde.
  Dessutom gäller en „2-årig tillverkargaranti" inte längre som ålder.

- **Qt-/PySide-licensrättigheterna är nu fullständigt spårbara.**
  Programpaketet innehåller dessutom GPL-3.0-helheten, exakta
  Qt-versioner, ett källkodserbjudande och en tysk/engelsk anvisning för
  utbyte av de dynamiska biblioteken inklusive lokal macOS-omsignering.
  Ett försäljningsbygge blockeras så länge de exakta källarkiven för den
  utlevererade versionen inte finns tillgängliga på den egna
  källkodssidan.

- **Licens och uppdateringsstatus anger nu entydigt för varje nivå vad som
  gäller.** I licensfönstret och vid uppdateringsinställningarna står om
  uppdateringar ingår, till vilken dag de räcker och om den löpande
  versionen förblir varaktigt användbar. Privatlicenser installerar inte
  längre en senare utkommen version efter brytdagen; även en nyligen
  nedladdad installerare känner på sitt fast inbyggda utgivningsdatum om
  den angivna nyckeln täcker den. Den sista täckta privatversionen förblir
  varaktigt användbar. Upphör däremot ett företagsabonnemang, upphör
  användning och uppdateringar; provperiod och gratisnivå öppnas inte som
  omväg.

- **Privata varaktiga licenser hittar nu även efter en nyinstallation rätt
  programversion.** En signerad versionskatalog listar alla stabila
  versioner och deras paket. Är den senaste av köpet omfattade
  installeraren inte längre tillgänglig, får i stället automatiskt exakt
  den närmast högre tillgängliga stabila versionen användas – aldrig en
  beta eller nightly. Vid en för ny installation kan kunden installera den
  tillåtna versionen eller växla till köpsidan för en ny
  uppdateringsperiod; ett bakslag sker inte tyst. Detta gäller även för
  hanterade MSI-installationer.

- **Den automatiska ansiktsmaskeringen beskrivs nu entydigt.**
  Programhjälpen och integritetstexten kallar funktionen „Identifiera och
  göra ansiktsområden okännbara" och avgränsar den från identifiering,
  återkänning, ansiktsjämförelse, biometriska mallar och person- eller
  ansiktsdatabaser. De påpekar dessutom tydligt att den helt lokala
  igenkänningen kan missa eller felaktigt markera områden och att
  resultatet därför måste kontrolleras visuellt. Även vid en enskilt
  rensad bildfil nämner resultatrapporten nu identifierade och pixlerade
  ansiktsområden; en saknad textigenkänning beskrivs därvid inte längre
  felaktigt som en helt oförändrad fil.

## 0.10.36-alpha.20260820 – 20 augusti 2026

### Rättat

- **Anonymiserade uppgifter kan nu hämtas tillbaka fullständigt oavsett
  ordning.** Den tidigare återtagningen sökte värdet via synliga textankare.
  I täta tabeller, direkt intilliggande platshållare och osynliga
  office-/mejlutrymmen saknades dessa ankare; ibland blev en term därför
  först återhämtningsbar efter att en annan klartext av en slump skapat ett
  nytt ankare. Nu jämförs resultat och original per verklig formatbärare med
  den fullständiga tilldelningen, och endast de belagda ställena för det
  valda värdet skrivs.

- **Namn, mejladresser, nummer och egna kontrolltermer förblir entydigt
  hanterbara även vid överlappande igenkänning.** Är samma klartextvärde
  tilldelat två typer, avgör den platshållare som faktiskt står vid
  fyndstället tillsammans med den klickade sidoradsraden. Ett obelagt
  värde/platshållare-par förblir fortsatt säkert spärrat.

- **Mejlspecialfall lämnar inte längre kvar dolda platshållare.** Det gäller
  MIME-kodade ämnesrader, textbilagor och namn separerade via HTML-markup i
  EML och MSG. UTF-8-HTML utan egen teckenuppsättningsangivelse kodas
  dessutom inte längre om till mojibake vid varje redigeringssteg i
  Outlook-filer; äldre resultat som redan skrivits på det sättet förblir
  återhämtningsbara.

### Förbättrat

- **En ny frigivningsmatris hanterar varje anonym sidoradsrad enskilt och
  medvetet baklänges.** Den prövar alla 14 text-, office-, webb- och
  mejlformat samt PDF, därefter även formler, attribut, relationer,
  kommentarer, mejlhuvuden, bilagor och interna delförvaringar. Den fullständiga
  macOS-körningen omfattar nu 149/149 gröna kontrollskript.

## 0.10.35-alpha.20260820 – 20 augusti 2026

### Förbättrat

- **Språkmätningar jämför nu verkligen lika med lika.** Det regelbundna
  mätkorpuset innehåller samma 14 dokumentfall med samma sju text- och fyra
  bilduppgifter på tyska och engelska. En fullkörning upprepar exakt denna
  matris för alla tolv befintliga korpusspråk. Formulär, tabeller, chattar
  och andra ännu inte helt översatta strukturprov finns kvar, men redovisas
  separat och blandas inte längre in i språkkvoterna.

- **Fullkörningen skriver en egen mätrapport för varje språk.** Utan
  språkväxel prövas medvetet tyska och engelska; `--alle-sprachen` kräver
  det fullständiga tolvspråkskorpuset och avbryter före första dokumentet om
  ett språk eller ett fall saknas. Likbenämnda resultat ligger i separata
  språkmappar. Totalrapporten anger utöver den viktade träffkvoten även
  medelvärdet av språkkvoterna, utan viktning.

- **Den öppna språkjämförelsen visar nu också sin verkliga gräns.** I den
  regelbundna körningen med textigenkänning tar tyska och engelska bort
  218/218 kända uppgifter utan falskt larm. Fullkörningen med
  textigenkänning och hög nivå tar bort 1 255/1 308 uppgifter med 17 falska
  larm; elva språk når 100 procent, hindi 51 procent. Tidigare fullkvoter
  byggde på ojämna dokument- och börmängder och kan inte jämföras med den
  nya matrisen.

## 0.10.34-alpha.20260819 – 19 augusti 2026

### Rättat

- **Namn som förekommer flera gånger förblir nåbara i sidoraden efter en
  enskild återtagning.** Tidigare försvann hela namnraden redan efter det
  första återhämtade `[NAME]`-stället. Ytterligare ställen för samma namn
  förblev därför som platshållare och blockerades tidvis till och med tills
  andra namn hämtats tillbaka. Nu försvinner raden först efter det sista
  stället; redan återhämtad klartext anonymiseras ändå inte automatiskt
  igen. Detta gäller likaså en delvis lyckad samlad återtagning och
  ramverktyget i PDF-filer.

- **„Ångra ersättning” fungerar nu även från office-sidvisningen.** Den
  synliga sidan där är bara en flyktig PDF-förhandsvisning; nu ändras
  korrekt Word-, kalkylblads- eller presentationsdokumentet bakom, och
  förhandsvisningen förnyas därefter.

- **Återtagningen hämtar nu även tillbaka en uppgifts dolda motsvarigheter
  fullständigt.** I Word-, OpenDocument-, Excel- och PowerPoint-filer kan
  samma uppgifter dessutom finnas i formler, kommentarer, diagram,
  fältvärden, alternativtexter och referensmål; HTML, EML och MSG för dem
  dessutom i attribut, JSON, meddelandehuvuden och bilagor. Tidigare blev
  där, beroende på format, en del kvar som platshållare. Nu kan varje
  uppgift som erbjuds i träffområdet återtas oberoende och i valfri
  ordning. Medvetet borttagna metadata, ändringshistorik och
  transporthuvuden förblir av säkerhetsskäl fortsatt borttagna.

- **Vid återhämtning från bilder blir det inte längre kvar någon svart
  kantlinje.** Höger och nedre kant av en ram lades vid kopiering från
  originalet ut en bildpunkt för snålt. Koordinaterna stämmer nu överens
  med maskeringen.

### Förbättrat

- **Frigivningskontrollen skickar nu var och en av de 22 filändelser som
  stöds genom en fullständig rundtur.** Innehållsrika filer rensas, alla
  erbjudna värden återställs och kontrolleras därefter djupt. Dessutom
  ingår verklig sidoradshantering, pixelexakta bildjämförelser och en
  synlig LibreOffice-rendering av alla sju kontorsformat. De små
  regressionstesterna finns kvar där de täcker ett eget fel- eller
  säkerhetsfall; ett bevisligen dubblerat HTML-test och testet av det
  borttagna svartvita läget har utgått.

- **Det fullständiga mätkorpuset för denna version finns tillgängligt för
  efterkontroll.** Paketet innehåller 294 syntetiska dokument i tolv format
  och tolv språk, 2 564 kända uppgifter, fyra maskinläsbara börlistor och en
  anvisning. Nedladdningen på kvalitetssidan använder ett
  innehållsberoende filnamn, så att webbläsare inte av misstag levererar en
  äldre version från cacheminnet.

## 0.10.33-alpha.20260819 – 19 augusti 2026

### Nytt

- **Även i bildfiler kan enskilda ställen nu hämtas tillbaka från
  originalet.** Ramverktyget „Hämta original” kopierar tillbaka
  bildpunkterna från samma position i den orörda källfilen. Vägen förblir
  spärrad om källan saknas eller har andra bildmått; på så vis kan inget
  innehåll sättas in från en förskjuten plats.

### Förbättrat

- **Manuella maskeringsstreck fäster som standard vid textrader.** Ett drag
  över flera rader skapar ett jämnt högt streck per rad och lämnar
  mellanrummen fria. För signaturer, grafik och andra specialfall kopplar
  „Fri ram” tillbaka till den valfria höjden.

- **Redigeraren förklarar nästa handgrepp direkt ovanför dokumentet.**
  Anvisningen växlar med dokumenttyp och verktyg och anger om ett
  ordklick, ett textval eller en ram förväntas. Dessutom visar verktyg,
  muspekare och direktförhandsvisning redan innan man släpper vad som
  kommer att hända.

### Borttaget

- **Den felbenägna svartvita utmatningen har tagits bort.** I vissa PDF-filer
  förblev osynliga textfält förskjutna i förhållande till den rastrerade
  sidan; den skenbara filminskningen var inte värd denna säkerhets- och
  visningsrisk. Vanlig PDF-rensning och riktad rastrering av problematiska
  sidor finns kvar.

## 0.10.32-alpha.20260819 – 19 augusti 2026

### Nytt

- **Mappövervakningen körs nu verkligen i bakgrunden.** Ingång, utgång
  och regler står på en egen sida under „Inställningar". Den startas
  och stoppas via Maskuro-ikonen i aktivitets- eller menyfältet; posten
  visas bara med den licens som frigör den. Inställningsfönstret kan
  därefter stängas och huvudfönstret läggas till ikonen, utan att
  övervakningen avslutas.

- **Efterbearbetningseditorn har nu en varaktig
  inlärningslägesbrytare.** Den finns i träffområdet och i menyn
  „Verktyg". Stängs den av, visas varken vid återhämtning eller efter
  manuella rättelser frågor om att skapa egna regler. Maskuro kommer
  ihåg valet för alla framtida öppnade dokument; själva återtagningen
  fungerar oförändrat.

### Rättat

- **Den stora tilläggsmodellen går åter att ladda ned.** Den offentliga
  lagringen avvisade Pythons allmänna standardidentifierare med 403.
  Modellhämtningar använder nu samma utpekade Maskuro-nätväg som de
  övriga egna tjänsterna; den knappt 596 MB stora filen och dess
  kontrollsumma är oförändrade.

- **En maximerad jämförelselupp blir inte längre kvar som ett smalt
  streck vid överkanten vid dockning.** Före dockning normaliseras dess
  fria fönstertillstånd. Ett sparat maximerat tillstånd återförs
  likaså till en förändringsbar storlek vid nästa öppning.

- **En samlad återtagning hämtar nu verkligen tillbaka alla valda
  värden i tabeller och andra textformat.** Vid anonymiserade
  platshållare som `[EMAIL]` skrev Maskuro tidigare värdena efter
  varandra. Så snart det första var ersatt, flyttade numren för alla
  återstående fyndställen fram, men den redan beräknade planen pekade
  fortfarande på de gamla numren. Därigenom kom bara en del av valet
  tillbaka. Nu skrivs alla valda värden av samma platshållare
  tillsammans och med stabila fyndställesnummer. Blir ett ställe
  entydigt först genom ett annat återhämtat värde, kontrollerar Maskuro
  det på nytt i samma drag – valets ordning spelar därmed ingen roll
  längre.

- **„Ångra ersättning" utelämnar inte längre valda värden i
  PDF-filer.** Stod en platshållare mycket tätt bakom ett annat ord
  eller hängde ett komma direkt vid värdet i originalet, kunde
  lägeskontrollen felaktigt räkna grannordet respektive skiljetecknet
  till värdet. Vid gemensam återhämtning blev då enstaka platshållare
  och träffrader kvar. Kontrollen riktar sig nu efter den faktiska
  ordbörjan och tar även hänsyn till en avvikande sidrotation mellan
  original och resultat.

- **Återhämtad PDF-text behåller nu sin ursprungliga storlek.**
  Tidigare tjänade den redan mindre satta platshållaren som mått;
  dessutom gällde för originaltexten den för platshållare avsedda
  övre gränsen på 11 punkter. Nu övertas originalruta och
  originaltextstorlek från källfilen – vid ramverktyget likaväl som
  vid återhämtning från träffpanelen.

### Förbättrat

- **Kontrollhänvisningen namnger nu restrisken tydligare.** Den säger
  uttryckligen att Maskuro kan förbise uppgifter eller hantera dem fel,
  och uppmanar före varje publicering eller vidarebefordran till
  fullständig kontroll och vid behov rättelse för hand. Detta gäller
  även texten från urklipp och är fullständigt genomfört i alla 17
  översättningar.

- **Kontrollprotokollet startar nu även inom sina rader utan
  användarnamn.** Själva protokollet förblir avstängt tills en
  organisation medvetet aktiverar det. Därefter står utan ytterligare
  företagsvorgab varken i en rad eller i namnet på en central
  månadsfil ett användarnamn; där tjänar en icke gissbar, bara ur den
  slumpmässiga lokala profilhemligheten härledd pseudonym för säker
  åtskillnad. Licensdialogen rekommenderar inte längre aktiveringen,
  förutsätter „Utan protokoll" och hänvisar i förväg till
  fackförening, personalrepresentation och dataskydd.

- **Ersätt namnger nu vad det ersätter.** Ett markerat namn blir till
  `[NAME_3]`, en ort till `[ORT_1]`, ett telefonnummer till
  `[TELEFON_2]` – i stället för att som förut allt blir `[BEGRIFF_n]`.
  Typen identifieras vid klicket; är den inte entydig – ett vanligt
  ord, eller ett namn *och* en ort i ett urval – blir det vid den
  allmänna termen. En platshållare som påstår en typ som inte stämmer
  vore sämre än en som ingen nämner.

- **Verktygen i efterbearbetningsfönstret har nu en tangent.** **S**
  maskerar, **E** ersätter, **Z** hämtar originalet tillbaka, **V**
  pixlerar. I textvyn verkar de genast på markeringen, i sidvisningen
  väljer de verktyget. **Bokstäverna följer det språk** du använder
  programmet på – engelska B/R/O/P, italienska O/S/R/P – för en
  minnesregel hjälper bara på det egna språket. Tangenten står vid
  knappen.
  Den som just skriver i sökfältet skriver vidare bokstäver som
  vanligt – där verkar de inte.

- **Programmet meddelar en gång om dagen i vilket tillstånd det körs –
  utan någon identifierare.** Därmed räknar vi hur många installationer
  som används och hur det fördelar sig på provperiod, gratisnivå och
  licens. Ut går tillstånd, operativsystem, version, kanal, land,
  språk, miljö och igenkänningsnivå – **inget om dina dokument och
  inget som din dator skulle kunna kännas igen på**. Två meddelanden
  från dig ser för oss ut som meddelanden från två olika personer; en
  enskild väg går inte att spåra ur det. Vad exakt som skickas och hur
  det stängs av står i integritetstexten under punkt 5.

- **Tvärt inmatade sidor står nu automatiskt rättvända.** Ett blad som
  skannats snett utan att det antecknats identifieras av
  efterbearbetningen på textflödet och rätar upp vyn. Där det inte går
  – vid en ren skanning utan läsbar text – roterar två nya poster i
  menyn „Visa" för hand (Ctrl+Skift+L och Ctrl+Skift+R). Bara visningen
  roteras: på filen ändras därvid ingenting, och maskering träffar
  fortfarande exakt det ställe man klickar på.

- **Den lokala utgåvan för nu sina licenser fullständigt och
  synligt.** Bygget fastställer de faktiskt sammanpaketerade
  Python-paketen, lägger deras licenstexter tillsammans med
  versionsöversikt under `lizenzen` och avbryter vid en lucka. Även Qt,
  Tesseract och ansiktsmodellen har sina nödvändiga texter; villkoren
  för Maskuro själv medföljer som licensavtal.

- **Man ser nu i vilken platshållare skrivmarkören står.** Den som
  klickar i en platshållare ser den lysa upp helt – tillsammans med
  hakparenteser och nummer. Knappen „Hämta tillbaka urval" fungerade
  redan tidigare vid ett rent klick; bara att det inte gick att se
  vilket märke den träffade. Lysningen förblir kvar även när musen
  flyttar till knappen.

- **Muspekaren säger nu vilket verktyg som är valt.** Fyra verktyg
  delar samma yta och samma gest; hittills såg alla likadana ut.
  Hårkors betyder maskera, sluten hand ersätta, öppen hand hämta
  tillbaka.

- **Ett preparerat kontorsdokument avvisas nu av programmet självt.**
  En Word-, Excel- eller OpenDocument-fil kan bära med sig instruktioner
  som vid öppning hämtar en främmande fil på din dator in i sin text
  eller fyller arbetsminnet. Båda avvisades även tidigare – men av det
  inbyggda XML-biblioteket, inte av Maskuro. Nu avgör programmet det
  själv, oberoende av vilken version av detta bibliotek som ligger i
  paketet. För vanliga dokument ändras inget.

### Rättat

- **Träffpanelen tar nu bort maskerade platshållare.** Maskerades till
  exempel `[NAME_1]` i efterbearbetningsfönstret, blev dess värderad
  tidigare kvar till höger, trots att inget sådant ställe längre fanns
  i dokumentet. Raden faller nu bort med det sista fyndstället;
  förekommer samma platshållare fortfarande på ett annat ställe,
  bevaras den.

- **Vid återhämtning på en roterad sida blir grannordet nu kvar.**
  Maskeringsstrecket sticker medvetet lite ut över texten; redan denna
  smala marginal kunde tidigare dra med sig ett angränsande ord som
  „im". Nu räknas bara en tydlig överlappning, inte beröringen vid
  kanten.

- **En andra ersättning på samma rad drog med sig eftersatsen.** Den
  som ersatte „Sachbearbeitung Quaxi Blubbo übernimmt" två gånger efter
  varandra fick „Sachbearbeitung [ORT_1] [ORT_2]" – ordet bakom var
  borta utan ersättning, utan något meddelande. Orsaken var
  platshållaren bredvid: resten av raden börjar efter den första
  ersättningen med ett mellanslag, och sökningen efter dess textställe
  fångade grannens avslutande parentes. Därefter var allt förskjutet
  med ett tecken. Berörd var varje rad där två ersättningar eller
  maskeringar gjordes – även vid återhämtning bredvid.

- **Ersätt maskerar inte längre när platshållaren är för lång.** Fanns
  ingen plats bredvid ordet för `[BEGRIFF_2]`, övermålades området
  tidigare svart – och därmed gick det inte längre att se att något en
  gång stått där, långt mindre att hämta tillbaka det. Nu skrivs en
  kortare skrivform: `[BEGR_2]`, `[BE_2]`, i nödfall `[B_2]`. Löpnumret
  förblir i varje steg – vid det hittar återhämtningen stället igen.
  Bara där inte ens den kortaste får plats, blir det vid strecket.

- **Ersätt lämnade texten kvar, när det redan maskerats på samma
  rad.** Den som i efterbearbetningsfönstret hämtade tillbaka ett namn
  ur originalet, ersatte förnamnet i det (där fanns ingen plats – det
  blev ett streck) och därefter ersatte efternamnet, fick platshållaren
  insatt, men namnet **inte borttaget**. Det märktes bara på
  efterkontrollens varning. Orsaken var raden själv: efter den första
  maskeringen börjar dess rest med ett mellanslag, och sökningen efter
  textstället fann inget fäste där. Detta drabbade varannan maskering
  på samma rad.

- **En påslagen utökad igenkänning utan sin modell märks nu.** Bocken
  kunde vara satt medan modellen saknades – inställningarna gäller för
  varje installation, men modellen ligger bredvid programmet.
  Rensningen kördes då utan nivån, utan ett ord om det. Nu säger
  bocken att modellen saknas, och resultatet bär en varning. Ditt en
  gång gjorda val förblir därvid sparat: så snart modellen är laddad
  verkar det igen.

- **Vid anonymisering hämtas nu rätt term tillbaka.** Den som ersatte
  flera termer för hand och därefter hämtade tillbaka en av dem fick
  alltid den **första** – ur „Schmidt" blev „Müller". Tilldelningen
  kom bara ihåg en ersättning per platshållare, och vid anonymisering
  bär alla samma platshållare; den andra och varje ytterligare term
  föll då bort. Nu får varje värde sin egen rad – även i listan över
  ersättningar, som tidigare var för kort.

- **I tabeller går det nu också att hämta tillbaka.** I en CSV eller
  personallista står platshållarna direkt bredvid varandra, avgränsade
  bara av ett semikolon. Hittills kunde programmet inte belägga vilket
  värde som stått på vilket ställe, och avböjde – vid `[NAME]` gick
  det, vid `[GEBURTSDATUM]` och `[TELEFON]` inte. Nu delar det upp
  raden vid alla platshållare. Förblir ett ställe verkligen tvetydigt,
  avböjer det fortfarande: ett felaktigt återskrivet värde vore värre
  än ett uteblivet besked.

- **Och avböjandet syns nu.** Det stod i dämpad grå längst ner i
  fönstret, och meningen var så lång att den skars av – det såg ut som
  om inget alls hände. Meningarna är förkortade, och raden lyser några
  sekunder i varningsfärgen.

- **En återtagning håller nu även efter nästa ingrepp.** Den som vid
  anonymisering hämtade tillbaka flera ställen och därefter ersatte
  något annat, fann alla återhämtade ställen ersatta igen och var
  tvungen att börja om. Orsaken var tilldelningen: den behöll värdet,
  och den automatiska avstämningen för enhetliga platshållare hämtade
  tillbaka det vid nästa skrivning. Nu gäller: vad du hämtar tillbaka
  förblir tillbakahämtat – andra ställen med samma värde rörs inte av
  det.

- **I text-, Word-, Excel- och e-postfiler räcker nu verkligen ett
  klick i platshållaren.** Meddelandet om detta stod redan i
  föregående version, men knappen „Hämta tillbaka urval" förblev
  spärrad så länge inget var exakt markerat – man kom alltså aldrig
  till vägen som skulle ha satt urvalet själv.

### Rättat

- **Kontrollprotokollet avslöjar inte längre filnamnet.** Det för
  medvetet filer som ett streuvärde i stället för i klartext, eftersom
  ett filnamn avslöjar klient och tvisteföremål. Detta streuvärde gick
  dock att bekräfta genom att gissa – en sökväg är inget slumptal. Nu
  går ett slumpvärde för denna installation in i beräkningen: räkning
  och åtskillnad i protokollet fungerar vidare, efterberäkning utifrån
  inte längre.

## 0.10.31-alpha.20260819 – 19 augusti 2026

### Förbättrat

- **Även i text- och kalkylfiler lyser platshållaren rött vid pekning.**
  Tidigare fanns den röda förhandsvisningen bara på en PDF-sida. Nu visar
  båda vyerna samma sak: det som är rött träffas av nästa drag – och ett
  klick i det räcker för att hämta tillbaka.

- **Ett klick på ett ord räcker – rektangeln sätter redigeraren själv.**
  I efterbearbetningsfönstret var man tidigare tvungen att dra en rektangel
  över varje ställe. Nu räcker ett klick: ramen lägger sig runt ordet och
  förblir gripbar, går alltså att dra ut vidare eller flytta. Vid pekning
  med musen lyser ordet redan rött, så man ser i förväg vad klicket skulle
  träffa. Där det inte finns något ord drar man en ram som förut.

- **Man behöver inte längre sikta exakt med rektangeln.** Den som drar en
  rektangel över en platshållare eller en maskering menar alltid hela
  stället – aldrig hälften av det. Ramen växer därför självmant till det
  hela den berör: hela platshållaren, hela strecket eller, på ett inskannat
  blad, hela den maskerade ytan. Mindre än den dragna ramen blir den
  aldrig.

- **Maskeringen sker nu ordvis.** En ram över hälften av ett ord maskerade
  tidigare bara hälften – och ett halvt maskerat namn är fortfarande ett
  namn. Berörda ord faller nu helt; grannen förblir orörd.

- **I text och kalkylblad räcker ett klick i platshållaren.** „Hämta tillbaka
  urval" krävde tidigare att man markerade platshållaren inklusive
  hakparenteser exakt. Nu räcker det att sätta pekaren i den; markeringen
  hoppar synligt till hela platshållaren.

- **Belgien har tillkommit som land.** Valbart i inställningarna; då
  identifieras belgiska telefonnummer, Rijksregisternummer (med
  kontrollsiffra), BTW-/företagsnumret (med kontrollsiffra), adresser på
  båda officiella språken och postnummer med ort. Tidigare blev belgiska
  telefonnummer kvar, eftersom landet överhuvudtaget inte fanns i
  katalogen.

- **Uppdateringskanalen anger nu hur tidigt du får nyheter – inte hur
  omfattande.** Den som stod på „Testversion" fick inte ens en ny
  förhandsversion eller en ny stabil version erbjuden, utan var tvungen att
  byta kanal för hand för att alls få veta om det. Nu erbjuds även allt som
  är mer tillförlitligt: Testversion tar testversioner, förhandsversioner
  och stabila versioner, Förhandsversion tar förhandsversioner och stabila.
  Aldrig tvärtom – på Förhandsversion erbjuds ingen testversion, även om
  den är nyare.

- **I inställningsfönstret ligger raderna nu längre isär.** De fyra sidorna
  använde egna avstånd i stället för det raster som gäller i resten av
  programmet; särskilt på sidan „Igenkänning" stod kryssrutorna märkbart
  för tätt på grund av det.

### Rättat

- **Ifyllda PDF-formulär visas inte längre tomma vid handredigering.**
  Maskuro gör för detta uteslutande den flyktiga arbetskopian till statiska
  sidor: ifyllda värden blir synliga och kan verkligen maskeras;
  utläsbara formulärfält blir inte kvar dolda i filen. Originalet förblir
  interaktivt och oförändrat. Det gäller nu även dynamiska XFA-formulär: en
  XFA-kapabel PDFium bygger först upp värden och sidbrytningar, därefter
  skapas ett nytt PDF uteslutande av statiska bildsidor. Misslyckas
  XFA-uppbyggnaden avvisas filen säkert i stället för att öppnas skenbart
  tom.

- **„Avbryt" verkar nu även under den noggrannare igenkänningen.** Tidigare
  låste sig knappen vid klick, men körningen fortsatte räkna till sista
  blocket – vid en lång fil är det minuter utan utväg, och knappen såg
  därvid ut som om den hade haft effekt. Nu avslutas körningen vid nästa
  block.

- **I CSV-filer hittas namn nu även när det inte står något mellanslag
  framför dem.** I `P-1000;Brunnthaler, Elisabeth` klibbar
  personalnumret över semikolonet fast vid namnet, och för igenkänningen
  var det ett enda ord utan namn i sig – i personallistor blev därför hela
  namnet kvar beroende på rad. Telefonnummer, formler och filens
  kolumnantal berörs inte av detta.

- **Ett namn där både för- och efternamn har bindestreck identifieras nu.**
  „Marie-Luise Habsburg-Ott" blev kvar mitt i meningen, medan
  „Dragan Mitrović" i samma mening hittades – just kombinationen av två
  hopkopplade halvor missade språkmodellen. Hopkopplade sakord som
  „Nord-Süd-Verbindung" eller „Software-Entwickler" berörs inte av detta.

## 0.10.30-beta.1 – 18 augusti 2026

### Förbättrat

- **Textvyns teckenstorlek kan nu ställas in synligt.** Reglaget längst
  ner till höger, som tidigare bara zoomade i sidvisningen, ställer i
  efterbearbetningsfönstret vid text- och kontorsfiler in teckenstorleken
  (50–300 %) – likaså „Förstora"/„Förminska" i menyn Visa. Ctrl+mushjul
  kunde alltid det, men det visste bara den som provat det; nu går
  reglage, visning och hjul tillsammans.

- **I det mörka utseendet ligger nu ett vitt blad på mörk arbetsyta.**
  Tidigare var det tvärtom: runt bladet blev en ljus yta kvar, och texten
  själv stod ljus på mörkt. Nu förblir bladet i båda utseendena
  pappersvitt med svart text – som en PDF-sida, som ju inte heller blir
  mörk i mörkt läge – och ytan runt om är mörk.

### Rättat

- **Efter en maskering mitt i en mening går resten av meningen inte
  längre förlorad.** Den som i efterbearbetningsfönstret gick till samma
  ställe tre gånger – ersätta, maskera, sedan „Hämta original" – fick
  meningens början raderad: ur „Rückfragen richten Sie bitte an das
  Rechnungswesen." blev „bitte an das Rechnungswesen.", utan varning.
  Berört var varje ställe där redan en gång något tagits bort mitt ur en
  rad.

- **Ett startfel drar inte längre med sig avslutningen.** Om
  huvudfönstrets uppbyggnad avbryts, kraschade därefter även
  avslutningen via aktivitetsfältsikonen – och detta andra fel dolde i
  felrapporten den egentliga orsaken. Nu avslutas programmet snyggt även
  från ett halvbyggt fönster, och de sparade inställningarna förblir
  därvid orörda.

- **„Före/Efter" hoppar inte längre till dokumentets början.** Den som i
  efterbearbetningsfönstret rullat nedåt och kopplade om till originalet
  för jämförelse hamnade åter längst upp – och var tvungen att hitta
  stället för hand igen. Vyn förblir nu på samma rad, i båda
  riktningarna.

- **Vid maskering blev sista bokstaven kvar på blockjusterade rader.**
  När ett textkommando ritar fler glyfer än läsbiblioteket meddelar
  tecken – det sväljer gärna ett mellanslag i blockjustering –,
  förskjöts tilldelningen med ett, och ur „Dr. Michael Handler aus
  Willendorf" blev „[NAME] r aus f": två kvarblivna bokstäver mitt i den
  rensade meningen (hittat i ett verkligt rådsprotokoll). Tilldelningen
  kontrolleras nu mot kommandots egen ordalydelse, där denna är läsbar –
  där gissas det inte längre.

- **„Lerchenfelder Gürtel 43/12" togs bara halvvägs bort.**
  Adressmönstren kände varken till Gürtel, Kai, Lände, Zeile, Markt eller
  Graben som gatugrundord, och husnumret fick inte bära
  snedstreckdelar (43/12, hus/dörr) – numret blev kvar bredvid
  platshållaren. Båda kompletterade; wienska och salzburgska adresser
  faller nu helt.

- **Sparade webbsidor förblir körbara efter rensning.** Adresserna som
  lazy loading lagrar i data-attribut (`data-lazy-src`,
  `data-lazy-srcset`) ersattes som referenser – på en verklig
  kommunsida sexton stycken – och sidans bilder laddade sedan inte
  längre. Webbadresser blir nu kvar där, som i `src` och `href` också;
  namn, mejladresser och telefonnummer i data-attribut ersätts
  fortfarande.

- **Japanska och koreanska dokument kördes som kinesiska.**
  Språkigenkänningen slog ihop alla tre skrifter, hittade i japansk text
  (utan mellanslag) och koreansk (med fastklistrade partiklar) inga
  funktionsord – och tog helt enkelt det första CJK-språket i katalogen.
  Ett japanskt rådsprotokoll och ett koreanskt mötesprotokoll lästes på
  så vis med den kinesiska modellen. Nu avgör skriftbilden själv: kana
  betyder japanska, hangul betyder koreanska.

- **Fler felgrepp från fälttestet på tio ytterligare språk:** ämbeten som
  „Primar", „Gradonačelnik", „Ordfører", „Başkanı" eller „Δήμαρχος"
  gäller inte längre som personnamn; turkiska fältbeteckningar („Adı",
  „Soyadı") och grekiska samtalsord („Ωραία", „Βεβαίως") faller inte
  längre; beslut- och paragrafnummer med datum („323/25-6-2008",
  „27 30.09.2024") är inte längre telefonnummer; och satsfragment med
  punkt („10.An", „T.U.EE", „…pa") ersätts inte längre som webbadresser.

### Nytt

- **Kontrollrapporter automatiskt på begäran.** En bock i inställningarna
  (sidan „Program") sparar efter varje rensning automatiskt en
  kontrollrapport-PDF – med tidsstämpel i namnet, i en egen mapp, aldrig
  bredvid resultatet. I efterhand går ett blad inte att skapa; den som
  behöver det för akten har det därmed alltid. Förinställt är sparandet
  av.

- **Kontrolloggen kan nu slås på i programmet.** Vid inläsning av en
  företagslicens frågar Maskuro en gång om loggen ska föras – ett belägg
  bär bara om det körs från början. Det finns för det en brytare i
  inställningarna (sidan „Program", synlig med företagslicens eller
  under provperioden); administrationens vorgabfil gäller fortfarande
  och kan tvinga fram värdet som förut. En egen loggrad „påslagen"
  fastställer sedan när loggningen förs – därmed är även
  inspelningens början belagd och signerad. Förinställt förblir loggen
  av.

- **Nyckeltalsklaffen visar vad KI-nivån har gjort.** En ny rad anger hur
  många osäkra träffar modellen bedömt, behållit och förkastat och hur
  många den dessutom hittat – tidigare var dess arbete osynligt om man
  inte klickade på varje värde i efterbearbetningseditorn. Bara siffror,
  aldrig värden eller motiveringar; utan KI-arbete visas raden inte.

- **Återhämtning fungerar nu även i e-post och HTML-sidor.** I `.eml`,
  `.msg` och sparade webbsidor gick en platshållare tidigare inte att
  ångra – programmet sa det ärligt, men just e-posten är formatet med
  flest personuppgifter. Nu bär återtagningen där likadant: från
  träffpanelen, med markerat urval och även vid anonymiserade
  platshållare. Den osynliga HTML-grenen av ett e-postmeddelande (det
  som Outlook verkligen visar) dras därvid med, så att vy och meddelande
  säger samma sak.

- **Träffpanelen tar tillbaka även anonymiserade värden – per värde.**
  „Ångra ersättning" var tidigare spärrad för anonymiserade filer,
  eftersom „[NAME]" står för alla namn samtidigt. Nu slår återtagningen
  upp i originalet vilket ställe som hör till vilket värde – i PDF via
  fyndställets koordinater, i textvyn via jämförelse med originalet –
  och hämtar exakt de ställen som hör till det valda värdet. Raderna för
  de övriga värdena blir kvar.

- **Även anonymiserade platshållare går att hämta tillbaka enskilt.** Vid
  anonymisering heter alla uppgifter av en typ likadant – „[NAME]" står
  för varje person, och tidigare gällde därför: enskild återtagning går
  inte. Nu slås det upp i originalet, som ändå ligger bredvid resultatet:
  markera platshållaren i textvyn och välj „Hämta tillbaka urval" –
  tillbaka kommer exakt detta ställe med exakt dess värde. Går värdet
  inte att entydigt läsa ur originalet, säger programmet det, i stället
  för att gissa. En tilldelningsfil skapas därvid fortfarande inte.

- **Efterbearbetningsfönstret öppnas av sig själv efter rensning.** Inget
  verktyg hittar allt – därför hör den kontrollerande blicken på
  resultatet till normalfallet, inte till ett extraklick. Den som inte
  vill det stänger av det i inställningarna under „Igenkänning"
  („Visa resultat i efterbearbetningsfönstret efteråt").

### Förbättrat

- **Landvalet står nu på „automatiskt".** Tidigare gällde fabriksmässigt
  gränssnittets språkområde – på en tysk dator rensades alltså även
  nederländska eller franska dokument bara med DACH-igenkännarna, och en
  adress som „Universiteitslaan 1" blev kvar (hittat i verkliga,
  offentliga rådsprotokoll). Nu riktar sig landvalet efter dokumentets
  språk; den som gjort ett fast val i inställningarna behåller det.

- **Mindre felaktigt maskerat.** Ett antal felgrepp, uppmätta mot
  kontrollkorpuset och verkliga mötesprotokoll på sex språk, försvinner:
  företagsnamn med bolagsform („Musterfirma GmbH") gäller inte längre
  som person eller ort, utan som organisation; hälsningsfraser och
  nakna tilltalsformer („Saygılarımızla", „Buenas tardes", ett fristående
  „Frau") är inte längre namn; ämbeten („Bürgermeister", „Sindaco",
  „Alcalde") blir kvar; lag- och beslutnummer („39/2015") och belopp med
  tusentalspunkt („330.000") är inte längre telefonnummer; satsbörjan
  som „Envíame" eller „Estarei" faller inte längre som namn; en träff
  över en tom rad räknas inte längre som namn. Fakturanumret på en
  faktura bevaras som belägguppgift – kundnummer och diarienummer faller
  fortfarande.

- **Före nedladdning av KI-modellen står nu vad den är bra för.**
  Nedladdningsdialogen nämner modellens uppgifter – bedöma gränsfall,
  hitta ytterligare namn, föreslå regler och profiler – och säger öppet
  att den inte är en chattassistent. FAQ besvarar samma fråga utförligt
  („Vad kan KI-nivån – och vad inte?"), på alla språkversioner.

### Rättat

- **Kontrollrapport-PDF-filer från kommandoraden går nu att söka i.** På
  Windows startade den huvudlösa PDF-vägen utan ett enda teckensnitt –
  varje tecken ritades som en ersättningsruta, och bladet bar ingen
  utläsbar text: den som ville söka i den eller kopiera ut något hittade
  ingenting. Nu laddar rapporten i det fallet systemets teckensnitt;
  texten är inbäddad och utläsbar. Rapporter från fönstret var aldrig
  berörda.

- **„Hämta original" över flera rader av en skanning lämnade svarta
  ränder mellan raderna.** På en till bild omvandlad sida städade ramen
  bara själva radbanden; resterna av den tidigare maskeringen blev kvar
  i luckorna mellan dem. Nu delas den dragna ramen fullständigt upp på
  raderna.

- **En andra ram över en platshållare lämnade en röd rest kvar.**
  Platshållaren är nästan alltid bredare än ordet den representerar; den
  som därefter maskerade samma ställe träffade bara dess början – kvar
  blev ett fragment som „RIFF_1]" mitt i meningen, och återhämtningen
  satte sedan in originaltexten på dess plats i stället för ordets. En
  avskuren platshållare faller nu alltid helt.

- **På en roterad sida raderade maskeringen över en platshållare en
  obesläktad mening.** Den efteråt ritade platshållaren förväxlades vid
  borttagning med texten framför den: den själv blev kvar, varningen
  „står fortfarande i dokumentet" kom – och på annat håll på sidan
  försvann utan ersättning en mening som inte hade med ramen att göra.
  En platshållare hittas nu igen via sin ordalydelse; kedjan „ersätta,
  maskera, hämta tillbaka" fungerar därmed även på tvärt inmatade sidor.

- **Handboken rådde på tio språk fortfarande till `python3-tk`.** I
  felsökningen stod att tkinter eventuellt saknades under Linux – ett
  råd från tiden före Qt-gränssnittet, som inte längre hjälper någon.
  Nu står i alla versioner samma stycke som på tyska: det saknas de
  systembibliotek som Qt behöver för visningen.

- **Handbokens licenskapitel var på gammal nivå i alla sexton
  översättningar.** På tio språk läste man fortfarande att Windows
  Server behöver en företagslicens med serveråtkomst och att provperiod
  och gratisnivå inte finns där – sedan en plats räknar en människa och
  inte en maskin är båda felaktiga. Det saknades dessutom överallt
  uppgifter om när en upptagen plats blir ledig igen, att licensen
  bekräftar sig regelbundet och vad som därvid överförs, och
  aktiveringen utan internet stod bara som kortversion utan de tre
  stegen och utan hänvisningen att datorn därefter arbetar ett år utan
  anslutning.

- **Sju stycken om efterbearbetning saknades på tio språk.** Den som läste
  hjälpen på danska, finska, franska, italienska, nederländska, norska,
  polska, portugisiska, svenska eller spanska hittade varken
  sidvisningen för kontorsfiler, „Maskera för hand", eller hela avsnittet
  om hur programmet lär sig av en rättelse – tillsammans med tabellen
  med de tre bredderna. I „Vad som identifieras" saknades i samma tio
  versioner vägen via beteckningen i dokumentet.

- **Med inläst licens startade programmet inte längre.** I stället för
  fönstret kom „Programmet kunde inte startas" – och det vid varje
  licens, oavsett vilken. Orsaken var raden i licensvisningen som varnar
  strax innan kontrollfristen löper ut; den kom åt något som inte fanns
  tillgängligt där. Utan licens – under provperioden och i gratisnivån –
  uppstod felet inte, därför märktes det först nu.

- **I formuläret förblir fältnamnen kvar.** „Geburtsdatum" och
  „Anschrift" försvann tillsammans med sitt värde: platshållaren stod
  liten och röd på *fältnamnets* plats, fältet under förblev tomt.
  Fältnamnet hör inte till uppgifterna – det blir nu kvar, och
  platshållaren står där värdet stod.

- **Främmandespråkiga dokumenttitlar tas inte längre för namn.** Ovanför
  ett italienskt formulär stod „FATTURA", ovanför ett spanskt „PERMISO
  PARENTAL" – båda ersattes. Listan över dokumentord kände bara till de
  tyska motsvarigheterna.

- **Ur en faktura försvinner ingen post längre.** „Materialaufschlag
  1  84,00" togs för en adress och ersattes med en ortsplatshållare –
  underlaget saknade därefter en rad. En rad som slutar med ett belopp
  är en post, inte en adress; riktiga adresser („Hauptstraße 1  120,00")
  förblir orörda.

### Ändrat

- **„Övervaka mapp …" och kommandoraden finns tills vidare inte
  kvar.** Båda vägarna är byggda och fungerar, men ingen av de båda är
  prövad i fält: mappövervakningen har aldrig sett en Windows-genomgång,
  och kommandoraden ger ett skript två dussin brytare i handen som
  aldrig körts hos någon användare. Det som obevakat ändrar dokument ska
  inte göra det okontrollerat – därför är de tillbakadragna tills
  genomgången hämtats in. Menyposten saknas, och `--wache` finns inte
  längre i `maskuro --help`.

- **Öppet förblir vad som bara läser och vad som ändå behövs.**
  Sökkörningen (`--suchlauf`) och kontrollen (`--nachpruefen`) fortsätter
  fungera på kommandoraden – de ändrar ingen fil. Likaså starten via
  Utforskaren, kontextmenyn, urklippet och fönstret; inget ändras där.

- **„Hämta från skanner" har nu ett eget kapitel i handboken.** Det stod
  tidigare i slutet av „Övervaka mapp". På Mac löd rådet där att låta en
  mapp övervakas; nu lyder det att dra de inlästa sidorna till fönstret.

### Rättat

- **„Hämta original" över flera rader av en skanning förstörde
  strukturen.** En ram över en platshållare, en oförändrad jobbtitel och
  en andra ersättning satte in hela området på nytt som **en** rad – av
  tre rader blev en, och det som inte längre fick plats blev ett
  streck. Nu hämtas varje rad tillbaka för sig.

- **Och oförändrad text förblir därvid orörd.** Den som drar över en
  ersättning *och* vanlig text får bara tillbaka ersättningen; resten
  rörs inte. Även den sista resten av den gamla platshållaren försvinner
  därvid – tidigare blev dess avslutande parentes kvar mitt i meningen.

- **Vid ersättning blir inga rester av den gamla texten längre kvar.** I
  en fet rubrik stod därefter „1. R[BEGRIFF_2]ige [BEGRIFF_1] … che" –
  platshållaren satt där, men stavelser av originalet bredvid. Nu städas
  det område som du ritar en ram runt, inte bara ordens rutor i det.

- **En anonym platshållare hämtas inte längre tillbaka fel.** Vid
  anonymisering bär varje namn samma `[NAME]`. Återhämtningen tog
  tidigare den första bästa posten och skrev den till varje fyndställe –
  ur „Georg Aigner" blev „Anna Musterfrau", alltså ett fel namn i
  dokumentet. Nu står där att det inte längre går att säga vilken
  uppgift som avsågs; dokumentet förblir orört.

### Nytt

- **„Hämta original" fungerar nu även på en rastrerad sida.** Var en sida
  omvandlad till bild, kom tidigare en avvisning: den återhämtade texten
  skulle hamna under sidbilden. Nu städas stället i bilden och texten
  skrivs på det – som en platshållare på en skanning. Innehållet kommer
  därvid från originalfilen, och den är inte rastrerad.

- **„Hämta tillbaka urval" står nu som en egen knapp.** Det gick redan
  tidigare, men bara om man av en slump markerade en platshållare och
  tryckte „Ersätt urval" – en funktion som man bara hittar av en slump
  finns inte för användaren.

### Ändrat

- **I ren text, CSV och Outlook-meddelanden finns inget „Maskera urval"
  längre.** Dessa format kan inte bära ett streck; knappen satte där en
  platshållare och sa det också – men en knapp som gör något annat än
  vad den heter hör inte hemma där.

- **Ett verktyg säger nu när det inte har något att göra på stället.**
  En platshållare går inte att ersätta en gång till, ovanför en
  maskering sätts ingen platshållare, och där originalet redan står
  finns inget att hämta tillbaka. Tidigare gjorde dessa drag något som
  såg ut som en effekt, men ingen var det.

## 0.10.29-alpha.20260817 – 17 augusti 2026

### Rättat

- **I efterbearbetningsfönstret har nu varje dragen ram effekt.** Den som
  arbetade två gånger på samma ställe – först ersätta, sedan maskera,
  sedan hämta originalet – fick sitt andra och tredje drag att fizzla ut
  ljudlöst: den fortfarande gripbara ramen från föregående drag fångade
  det. Detsamma vid verktygsbyte, där till och med det gamla verktyget
  tyst fortsatte verka.
- **En för smalt dragen ram säger att den är för smal.** Tidigare lyste
  förhandsvisningen upp ett ord rött, och vid släppning hände tyst
  ingenting.

- **Outlook-meddelanden går äntligen att efterbearbeta.** En `.msg` visade
  i efterbearbetningsfönstret „Detta format kan inte visas här" – det var
  det enda format som stöddes utan någon väg till handredigering. Nu
  står avsändare, mottagare, ämne och meddelandetext namngivna i vyn och
  går att markera och ersätta som i vilket annat textformat som helst.

- **„Ersätt urval" håller sig i ett e-postmeddelande till urvalet.** Den
  som markerade ett namn i löptexten förlorade därvid även avsändare och
  mottagare ur huvudraderna, och meddelandet nämnde en annan platshållare
  än den som stod i texten. Nu ersätts det markerade värdet överallt –
  även i avsändaren om det står där – och inget annat rörs.

- **En ram över flera rader förstör inte längre texten.** Tidigare
  uppstod en enda platshållare på ett ställe: från det avskurna ordet
  blev en rest kvar fastklibbad, och ur den andra raden försvann texten
  utan ersättning – ingen platshållare, inget streck, bara en lucka. Nu
  får varje rad sin egen platshållare med det värde som verkligen stod
  där.

- **„Hämta original" verkar nu även efter en maskering.** Fönstret
  meddelade framgång, och texten kom aldrig tillbaka: det svarta strecket
  räknades som hinder, så att det inte fanns plats kvar för den
  återhämtade texten. Strecket viker nu undan, och den återhämtade texten
  står svart som vanlig text – inte röd som en platshållare.

- **„Hämta original" på ett orört ställe gör inte längre något.** Den
  som drog ramen över text som inget alls hade ändrats i fick texten
  borttagen och åter insatt mindre och förskjuten – och framgång
  meddelades. Nu står där att det inte finns något att hämta tillbaka.

### Nytt

- **Även i Word, Excel, PowerPoint, OpenDocument och text går det att
  maskera.** Tidigare fanns där bara „Ersätt urval"; ett streck var
  förbehållet PDF-vyn, utan att det fanns någon anledning till det. Där
  ett streck inte går att visa – i ren text och i ett
  Outlook-meddelande – ersätts värdet som förut av en platshållare, och
  det står också så i meddelandet.

- **Att markera en platshållare hämtar den tillbaka.** I textvyn (Word,
  Excel, PowerPoint, OpenDocument, text) räcker det nu att markera
  platshållaren och trycka „Ersätt urval": originalvärdet kommer
  tillbaka. Tidigare hänvisade fönstret för det till träffpanelen.

- **Talare i ett mötesprotokoll identifieras nu även när deras namn
  samtidigt är ett vanligt ord.** „Gruber: Die Abnahme erfolgt kommende
  Woche." ersattes, „Bauer: Ich stimme zu." förblev kvar – efternamnet
  ser för igenkänningen ut som ett substantiv. Anmärkningsrader av samma
  byggform berörs inte: ur „Achtung: Die Anlage ist abzuschalten." blir
  inget namn.

- **„Du använder den senaste versionen" sades även när det inte alls
  gick att kontrollera.** Avvisar uppdateringsservern förfrågan – för att
  för många förfrågningar kom från samma internetadress eller för att den
  själv just då är störd – stod programmet stilla på sin gamla version
  och påstod att den var den senaste. Exakt det hände den 17 augusti på
  en Mac: 0.10.25 blev liggande, medan 0.10.28 legat redo i timmar.

  Nu säger fönstret vad som pågår, nämner klockslaget för nästa
  kontroll – och påpekar uttryckligen att det **inte** är fastställt om
  den egna versionen är den senaste.

  Oftast beror det inte på den egna datorn: vid många anslutningar delar
  många kunder samma internetadress, och servern räknar dem tillsammans.
  Därför söker Maskuro versionslistan i detta fall via en **andra väg**
  och hittar ändå oftast nya versioner. Består avvisningen, lämnas
  servern i fred fram till det angivna klockslaget – även om knappen
  trycks igen; att fortsätta trycka förlänger bara spärren.

- **Kvantitetsangivelser tas inte längre för ortnamn.** I ett
  tjänsteavtal försvann „Vier-Tage-Woche" bakom en ortsplatshållare –
  mitt i avtalsföremålet. Sådana ordkombinationer av tal och bindestreck
  („Drei-Punkte-Plan", „24-Stunden-Dienst") blir nu kvar. Adresser är
  undantagna från detta: en „Zwei-Brüder-Weg" ersätts fortfarande.

## 0.10.28-alpha.20260817 – 17 augusti 2026

### Ändrat

- **Licensplatser räknas nu verkligen.** Tidigare anmälde sig ingen
  arbetsplats någonsin hos licenstjänsten – en tioplatslicens kördes på
  hur många datorer som helst utan att någon fick veta. Nytt: den dator
  som startar programmet tar en plats; en plats frigörs automatiskt efter
  **sju dagar utan start**, så att en trasig enhet eller en avgången
  medarbetare inte blockerar något permanent.

  En liten överbeläggning visas därvid **bara och spärras inte**: upp
  till tio procent över det köpta antalet fortsätter alla att arbeta –
  den nya bärbara datorn bredvid den fortfarande anmälda gamla ska inte
  vara ett fall för hotlinen. Den som tillkommer utöver det faller
  tillbaka till gratisnivån och får veta det; datorerna som var där
  först märker inget av det.

- **En köpt licens bekräftar sig regelbundet.** Lyckas det inte på
  **30 dagar**, gäller gratisnivån tills det lyckas igen. Inget stängs
  av, och från en vecka innan står hänvisningen i fönstret. Så snart
  datorn åter kommer ut på internet sköter det sig självt. Provperiod och
  gratisnivå meddelar fortfarande ingenting alls – den som aldrig köper
  ringer aldrig hem.

- **„Aktivera utan internet" fungerar äntligen.** Aktiveringen
  kontrollerades och lagrades tidigare, men lästes sedan av ingen – den
  ändrade inget i rättigheterna. Nu är den utvägen för datorer utan
  nätåtkomst: den gäller **ett år**, därefter hämtar man en ny med en
  färsk anfordringskod. En enhet med internet behövs för det en gång om
  året – själva datorn förblir varaktigt offline.

- **Aktiveringen går nu även via kundkontot** – under „Mina licenser" på
  webbplatsen. Där står dessutom vilka datorer som hänger på din licens
  och när deras platser blir lediga igen; det gick tidigare inte att se
  någonstans. Sidan utan inloggning finns kvar för alla som saknar
  butiksåtkomst – den kräver för det dessutom e-postadressen från
  beställningen, så att licensnyckeln ensam inte räcker.

- **Och i fönstret står nu vart anfordringskoden ska.** Pappersvägen sa
  „ange på en enhet med internetanslutning" och nämnde ingen adress;
  aktiveringssidan har funnits länge, men var inte länkad från
  någonstans. Nu står **maskuro.com/lizenz-freischalten** i dialogen, i
  handboken och i FAQ – och på webbplatsen under licensnyckeln.

- **Knappen „Aktivera utan internet …" förblir synlig**, även när
  licensen just inte gäller. Tidigare försvann den tillsammans med den –
  alltså precis när man behöver den.

- **„Alla platser upptagna" säger nu sanningen.** Hänvisningen slutade
  med „Programmet fortsätter arbeta oförändrat"; det stämmer inte längre
  om ingen plats tilldelades. Där står nu att gratisnivån gäller tills
  vidare.

### Nytt

- **Vid påslagning av urklippsrensningen står det nu med att kontroll
  krävs.** Meddelandet bär sedan dess samma mening som står vid en
  fils resultat: Maskuro identifierar inte alltid alla personuppgifter i
  varje fall.

  Här väger den tyngre än på andra ställen. Vid en fil ser man resultatet
  innan man lämnar det vidare. Vid urklippet inte – man kopierar,
  klistrar in, och den rensade texten står redan i mejlfönstret.
  Meddelandet säger därför uttryckligen att gå igenom den **inklistrade**
  texten.

  Den visas vid påslagning, inte vid varje kopieringsprocess: det som
  visades femtio gånger om dagen läser ingen längre efter tredje gången.

- **„Kopiera alla" under listan – och „Ta bort alla" flyttar bort.** Den
  nya knappen lägger samtliga färdiga resultat i urklipp på en gång, för
  att bifogas ett mejl eller klistras in i ett annat program. Tidigare
  gick det bara via menyn och även där bara för de **markerade** raderna
  – den som menade alla var tvungen att först trycka Ctrl+A.

  Därvid är knappraden nyordnad: till vänster står det som lägger till
  något, till höger bakom ett mellanrum det som tar bort något. „Ta bort
  alla" stod tidigare direkt bredvid „Lägg till …", och ett felgrepp
  kostade hela listan. Samma regel gäller sedan den 13 augusti redan vid
  varje färdig rad.

- **Arbetsplatser utan internet får nu sina språkmodeller från huset.**
  Rensning fungerade där redan utan anslutning – nedladdning av en
  språkmodell inte, och en modell väger flera hundra megabyte.

  Administrationen sätter ihop filerna en gång på en dator med
  anslutning och lägger dem på en delning, i utrullningen eller på ett
  USB-minne. Platsen anges centralt (fältet `modellquelle` i
  `vorgaben.json` eller miljövariabeln `MASKURO_MODELLQUELLE`). Från och
  med då hämtar varje nedladdning först därifrån – språkmodeller, den
  japanska ordboken och hög-nivån – och går bara ut på nätet om en fil
  saknas.

  Kontrollsummorna gäller därvid oförändrat. En fildelning i huset är
  ofta lättare att komma åt än ett utgåva på nätet; den ska inte bli den
  bekvämare vägen till en insmugglad modell.

  Hur ett sådant bestånd byggs upp och hur licens och aktivering fungerar
  utan internet står i `OFFLINE.md`.

- **„Hämta original" – en ram hämtar tillbaka det som togs bort för
  mycket.** I efterbearbetningsfönstret finns ett nytt verktyg: dra en
  ram över stället, och texten står där igen som den stod i originalet.

  Det täpper till luckan som träffpanelen lämnade öppen. Där gick en
  ersättning bara att ångra om dess platshållare var entydig – alltså
  inte vid anonymisering, där „[NAME]" står vid varje sådan uppgift, och
  inte alls vid maskerade ställen, där ingen platshållare blir kvar. Just
  där samlas felgreppen: „Benutzer", „Inventarnummer", „Unterschrift"
  tas gärna för namn.

  Ramen behöver inte platshållaren: **stället** kommer från rektangeln,
  **innehållet** från originalfilen – samma fil som Före/Efter-växlaren
  visar. Anonymiserat eller pseudonymiserat spelar därmed ingen roll
  längre.

  Den återhämtade texten står svart, inte röd: den är åter klartext och
  ingen platshållare. Ur träfflistan försvinner en post först när dess
  platshållare **ingenstans** längre står i dokumentet – ersattes samma
  värde på flera ställen, blir den kvar för de övriga.

  På en sida som omvandlats till bild avböjer verktyget och förklarar
  varför: den återhämtade texten skulle hamna under sidbilden och skulle
  inte synas.

### Rättat

- **Vid hopfällning av „Detaljer" och „Nyckeltal" blev bildrester kvar på
  skärmen.** Hopfälld sköts en del av innehållet under fönstrets nedre
  kant och blev kvar där ovanpå bakgrunden, tills något annat ritades
  ovanpå.

  Båda områdena har en minimihöjd, så att de är användbart stora
  öppna. Rörelsen vid hopfällning sänkte dock bara maxhöjden – och under
  sin minimihöjd krymper ett område inte. Innehållet förblev alltså
  200 punkter högt, medan fönstret redan drog ihop sig till 24;
  skillnaden stod under kanten. Nu viker minimihöjden undan under
  rörelsens varaktighet och kommer tillbaka efteråt.

- **Fönstret blev mindre för varje upprepad upp- och hopfällning.** Vid
  uppfällning växer det som mest till 92 % av skärmhöjden; är platsen
  knapp, växer det alltså mindre än vad som behövs. Vid hopfällning drog
  det ändå av hela beloppet igen. Nu ges exakt tillbaka det som
  uppfällningen kostade.

- **En rest av en maskerad uppgift kunde stå kvar synlig.** I ett CV
  förblev av „*30.12.1991" tecknen „*30.1" läsbara i resultatet – alltså
  dag och månadsbörjan i födelsedatumet. Programmet hade till och med
  märkt resten och därför omvandlat sidan till bild; just det gjorde det
  värre, för därmed var resten visserligen inte längre sökbar, men
  fortsatt läsbar – och inte längre åtgärdbar.

  Orsaken låg mellan två kontroller. Den strängare av de båda
  kontrollerar om det i ytan för en borttagen uppgift fortfarande står
  något som inte hör hemma där; den meddelar sitt fynd som en
  teckenmängd, eftersom läsordningen förskjuts vid ersättning.
  Reservlösningen som målar över sådana ställen före omvandlingen sökte
  denna teckenmängd som text på sidan – och hittade den aldrig.
  Övermålning skedde därför inte. Stället var känt hela tiden och skickas
  nu vidare, i stället för att sökas på nytt.

  Berörd var varje sida vars rest hittades enbart av denna kontroll –
  oberoende av filtyp och språk.

- **På en tvärt inmatad skanning hittade textigenkänningen inget.** Den
  som lägger ett blad i sidled i inmatningen får en fil där skriften
  står roterad 90 grader. Tidigare läste Maskuro **inte en enda**
  uppgift i den – och filen såg därefter oansenlig ut: inget hittades,
  alltså rapporterades inget, och adressen stod fortsatt läsbar i bilden.
  Nu rätar textigenkänningen upp sidan själv; i kontrollbilden faller
  åter alla uppgifter.

  Två gränser öppet nämnda: ett blad som ligger **upp och ned** (180
  grader) läses fortfarande inte, och vid en mycket dålig skanning
  hjälper uppresningen inte – där är för lite läsbart för att alls
  fastställa läget. Varje bild behöver för det cirka en femtedel längre
  tid.

### Ändrat

- **„Installera automatiskt" heter nu vad det gör.** Bocken i
  inställningarna lovade mer än den höll: den laddar ned den nya
  versionen av sig själv och startar installationen – som dock körs
  **synligt** och vill bekräftas, på Windows tillsammans med en fråga
  från användarkontokontrollen. Den som läste „automatiskt" räknade med
  en dator som uppdaterar sig själv över natten, och stod på morgonen
  inför installationsguiden. Bocken heter nu „Ladda ned uppdateringar
  automatiskt och starta installationen", med en mening under om vad det
  betyder. Beteendet ändras inte – att Maskuro inte byts ut obemärkt är
  avsiktligt och förblir så.

## 0.10.27-alpha.20260817 – 17 augusti 2026

### Nytt

- **Nytt: `--ersetzen` för anslutning till en advokatbyrås programvara.**
  Resultatet tar källfilens plats, i stället för att skapas bredvid. Med
  det fungerar in- och utcheckning i en advokatbyrås programvara
  („Öppna och redigera" i e-akten) utan något gränssnitt: programvaran
  lämnar ut filen och får den rensad tillbaka på samma plats.

  **Denna brytare kringgår den första grundprincipen**, och därför finns
  den bara på kommandoraden – inte i fönstret – och bara om din
  administration frigör den (posten `ersetzen` i vorgabfilen). Utan
  frigivning avbryts anropet och säger varför; att tyst skapa en andra
  fil vore det värre felet, för då skulle den oförändrade checkas in
  igen.

  Skriven blir först en grannfil; först när den är klar tar den
  källans plats. Ett avbrott eller fel lämnar därmed källan **byte för
  byte oförändrad** och lämnar inget fragment kvar. I kontrollprotokollet
  står ersättningen som ett eget fält – en kontrollant måste veta att den
  orensade versionen inte längre ligger här.

- **Handboken förklarar nu Windows-varningen vid första start.** Nytt
  första avsnitt „Windows varnar vid första start – vad du ska göra",
  med två bilder och tre steg: „Mer information" är en liten länk, ingen
  knapp – exakt där fastnar de flesta –, sedan „Kör ändå".

  Att det står „Okänd utgivare" där är hela varningens budskap: paketen
  levereras för närvarande utan certifikat. Vi anser det riktigare att
  förklara det än att tiga om det.

- **Återvägen märker nu när text och tilldelning inte hör ihop.** Den
  som klistrar in svaret i ett annat ärende fick tidigare främmande namn
  i den riktiga texten – inget fel, inget meddelande, bara fel. Maskuro
  kommer nu ihåg vilka platshållare den senaste körningen alls skapat,
  och meddelar var och en som inte hör dit. Kommer ingen av dem från
  den senaste körningen, sätts inget in och fönstret säger varför – i
  stället för att som förut anta en utgången frist.

  **En gräns kvarstår, och den står också i handboken:** platshållare
  numreras per körning, det första namnet heter alltså i varje dokument
  `[NAME_1]`. Bär den främmande texten bara sådana platshållare, går
  förväxlingen inte att upptäcka.

- **PDF kan nu skrivas ut i svartvitt.** En bock vid driftläget omvandlar
  varje sida till en svartvit bild – med ett osynligt textskikt under,
  alltså fortfarande läsbar och sökbar. För sändning via beA och
  liknande vägar med hårda storleksgränser: över vårt mätkorpus i
  genomsnitt **68 % mindre** (kommandorad: `--monochrom`).

  **Hur mycket det ger beror på dokumentet** – och det står också vid
  bocken: skannat och bildhaltigt krymper kraftigt, ett smalt
  textdokument utan inbäddade teckensnitt kan till och med bli större.
  Prova det på en fil innan du slår på det för en bunt.

  Priset: varje sida beräknas på nytt – vid tusen sidor tar det minuter.
  Och bilder förlorar allt mellan svart och vitt; för text spelar det
  ingen roll, för en fotografisk bild gör det det.

- **Träfflistan i efterbearbetningsfönstret räknar nu med.** Ovanför
  listan står „5 träffar", och så snart du filtrerar, „1 av 5 träffar".
  Det är skillnaden mellan „jag har filtrerat" och „det är fem, och jag
  har sett alla" – handgreppet man använder för att kontrollera att ett
  namn verkligen ersatts överallt.

- **Kontrollprotokollet går nu att söka i och filtrera.** Vyn under
  „Arkiv → Kontrollprotokoll" hade tidigare en tabell och inget annat –
  vid en månad med tretusen körningar såg man att mycket hänt, men inte
  vad.

  Nya är ett **sökfält**, **tre filter** (förfarande, resultat, typ) och
  **bläddring**, dessutom tre kolumner som inte fanns tidigare:
  **Förfarande** (maskerat eller ersatt), **Konfidens** och
  **Varaktighet**. Ovanför listan står hur mycket som just syns och hur
  mycket filtret döljer.

  „Spara som CSV …" ger nu ut **det som visas** – den som filtrerat får
  det filtrerade, och meddelandet nämner antalet.

  Ett streck vid konfidens eller varaktighet betyder att inget mättes
  för denna rad – till exempel för att den är äldre än denna funktion.
  Dessa värden räknas **inte** ut i efterhand. Ett filter över
  användare finns fortfarande inte; en enskild rad hittar sökningen
  ändå.

### Borttaget

- **Transparenshänvisningen i fönstret „Om detta program" är åter
  borta.** Den stod där sedan 0.10.22-beta.1 och sa att programmet
  utvecklats med stöd av artificiell intelligens. Den krävs ingenstans,
  och just i ett program för dataskydd läste många den som ett påstående
  om arbetssättet – alltså som om dokumenten gick till en tjänst på
  nätet. Rensning sker fortfarande uteslutande på den egna datorn; det
  står där det hör hemma, i fliken „Integritet".

### Rättat

- **Programmet bytte ut sin egen ikon mot en sämre.** Den som lade in
  kontextmenyn från programmet hade därefter en annan sköld i
  aktivitetsfältet än efter installationen – lik, men med
  vänsterjusterade i stället för centrerade streck och synbart
  grövre. Bakom det låg en nödlösning: hittar programmet inte
  ikonmallen, ritar det en själv. Det var tänkt för fallet att **inga**
  ikoner finns; i praktiken ritade det även när de medföljande redan
  låg där – och skrev över dem. I en från installationsprogrammet
  installerad version finns ingen mall, så där drabbade det alla.
  Befintliga ikoner rörs nu inte.

  **Redan berörda installationer hämtar inte tillbaka den rätta ikonen
  av sig själva** – installera om en gång för det.

- **„Objektkennung: OB-4711-22" gällde som inloggningsnamn.**
  Identifieraren för användarnamn kontrollerade sina beteckningar utan
  ordgräns framför – alltså träffade **varje** ord som slutar på en av
  dem: Objektkennung, Fahrzeugkennung, Gerätekennung. Värdet bakom togs
  bort, trots att det inte har med ett inloggningsnamn att göra.

  Sammansättningar som verkligen avses – „Benutzerkennung",
  „Anmeldekennung" – står enskilt i listan och identifieras fortfarande.

- **På engelska, grekiska, japanska och koreanska stod sexton
  platshållare på tyska i resultatet.** Den som ställt gränssnittet på
  ett av dessa fyra språk fick för de nyare datatyperna de tyska
  beteckningarna skrivna in i dokumentet – ur ett lösenord blev
  `[ZUGANGSDATEN_1]` i stället för `[CREDENTIALS_1]`, ur en
  diagnosnyckel `[DIAGNOSESCHLUESSEL_1]` i stället för
  `[DIAGNOSIS_CODE_1]`. Berörda var hälsa, diagnos, medicinering,
  diagnos- och läkemedelsnycklar, religion, fackförening, politisk
  åsikt, straffrätt, åtkomstuppgifter, användarnamn, kortdata,
  koordinater, yrke, belopp och kännetecken.

  De övriga 44 språken hade aldrig felet: de hämtar sina beteckningar
  ur språkfilerna, där dessa typer stått med från början. Just dessa
  fyra språk för av en annan anledning egna tabeller – deras skrift
  överlever inte PDF-teckenuppsättningen, varför latinska beteckningar
  står där –, och i dessa tabeller saknades de nya typerna helt enkelt.

  Det upptäcktes vid översättning av katalogsidan: webbplatsen lovade
  engelska läsare beteckningar som programmet inte skrev. En kontrollsten
  håller nu de fyra tabellerna mot listan över alla beteckningar som
  alls kan uppstå.

- **Regelfönstret öppnas inte längre för litet för sitt innehåll.** I
  fliken „Egna sökmönster" låg guidens förklaringsrad („Sökt blir: …")
  halvt bakom fältet „Provtext" – just den mening man använder för att
  utan kunskap om reguljära uttryck kontrollera att den egna regeln
  söker rätt sak. Fönstret hade ett fast minimimått från en tid med
  färre flikar och gick därför att dra under vad som fick plats. Nu
  rättar det sig efter sitt innehåll och blir bara så litet som allt
  förblir läsbart.

- **Namn i tabellformler blir inte längre kvar.** En cell har mer än en
  plats för text, och tidigare städades bara en. Stod ett namn i en
  formel – `="Frau "&"Sieglinde Ortner"` – eller var det senast
  beräknade resultatet av en formel, förblev det oförändrat i
  arbetsboken, trots att samma person i cellen bredvid var ersatt. Den
  som klickade på cellen läste det i redigeringsraden.

  Båda ersätts nu. Berört blir bara det som står mellan citattecken:
  cellreferenser, funktionsnamn och bladnamn förblir orörda,
  `=SUMME(K2:K6)` fortsätter beräkna. Eftersom samma namn får samma
  platshållare överallt, hittar även `=SUMMEWENN(A:A;"Huber";B:B)`
  fortfarande sina rader.

- **Diagram visar inte längre namn.** Ett diagram sparar en egen kopia
  av sina axelbeteckningar – det ritar fortfarande även när
  källcellerna för länge sedan är tomma. Under staplarna stod därför
  fortfarande fem personnamn, medan tabellen ovanför var ren. Gäller
  kalkylblad **och** presentationer.

- **Namngivna områden med fast text städas.** Ett namngivet område kan
  i stället för en cellreferens innehålla fast text; stod ett namn där,
  blev det kvar. **Namnet** på området blir fortfarande kvar – formler
  refererar till det, och en namnbyte skulle ge ett referensfel. Som
  vid bladnamnet rapporteras det, ersätts inte.

- **Ett en gång identifierat födelsedatum försvinner i hela dokumentet.**
  Ett datum för sig säger inget – först ett fältord gör det till ett
  födelsedatum, och just därför lämnas ett fakturadatum i fred. Stod
  samma uppgift i samma dokument men en andra gång utan detta ord – i
  bildtiteln, i ett ifyllt formulärfält –, blev den kvar där, trots att
  det ett par rader ovanför entydigt identifierades „geboren am …".
  Överfört blir bara det som redan identifierats som ett födelsedatum i
  **detta** dokument; gissat blir fortfarande ingenting.

- **Strukturerad data i webbsidor avslöjar sitt födelsedatum.** I
  JSON-LD-blocket för sökmotorer står datumet under nyckeln
  `birthDate` – nyckeln säger vad det är, precis som annars
  kolumnrubriken. Den läses nu med; „Birthday" och „Birthdate" gäller
  därmed även i formulär som fältbeteckning.

- **Födelsedatum och personalnummer hittas nu även i tabeller.** I en
  cell står bara det nakna värdet – `14.03.1988`. Vad det betyder säger
  bara kolumnrubriken, och den står många rader högre upp. I Excel
  lästes den redan med; i LibreOffice-kalkylblad och i CSV-filer inte,
  och där blev födelsedatumet därför kvar.

  Båda läser nu rubriken med – **men bara om den själv är en
  fältbeteckning**. Under „Geburtsdatum" faller datumet, under
  „Rechnungsdatum" eller „Lieferdatum" inte. Det är medvetet den
  försiktiga tolkningen: en rubrik som „Name" ovanför en godtycklig
  anmärkning skulle annars redan en gång ha lagt en platshållare över
  en mening där ingen person alls förekommer.

### Rättat

- **Ett rensat CSV-dokument förblir en tabell.** Igenkänningen läser en
  CSV-rad som en sats och lade därför sina fynd ibland över ett
  semikolon. Platshållaren slukade avgränsaren, raden hade därefter en
  kolumn mindre, och filen gick inte längre att öppna som tabell.
  Fyndställen slutar nu vid cellgränsen, och maskeringens citattecken
  blir kvar. De berörda cellerna läses därefter en gång till för sig –
  annars skulle grannellen förbli orensad, den som den för långa
  träffen dolde.

- **Kommentarer i presentationer.** Marginalanmärkningen på en bild –
  ofta just stället där „Bitte Frau … vor der Sitzung anrufen" står –
  förblev orörd, tillsammans med namnet på den som skrivit den. I Excel
  var båda länge städade; PowerPoint lagrar kommentartext och
  författare annorlunda, och det hade förbisetts. Berör båda
  byggformerna: den äldre och den som PowerPoint skrivit sedan 2019 –
  där även tjänste-mejladressen som hänger vid författaren. Initialerna
  som PowerPoint visar vid pratbubblan tas bort med.

- **LibreOffice-filer: formel, användarfält, anteckningsförfattare.** Vad
  som redan städades i Excel blev kvar i ODS-tabellen – där står
  formeln inte som ett eget element, utan som en egenskap hos cellen,
  och namnet i den överlevde. Vid nästa öppning räknade LibreOffice
  fram det igen.

  Dessutom tre andra ställen: värdet i ett **användarfält** står i
  OpenDocument en gång högst upp i deklarationen och hämtas i texten
  bara – ersatt blev tidigare bara hämtningen, så att vid öppning kom
  det gamla värdet tillbaka. **Författaren till en anteckning** och en
  spårad ändring blev kvar. Och i en **tabell** rensades ändringsspårningen
  inte alls – till skillnad från i textdokumentet –, så att raderat
  cellinnehåll tillsammans med redigerarnamn bevarades. Cellreferenser
  och summaformler rörs inte.

- **Sparade webbsidor avslöjar sina attribut.** En sida visar långt
  ifrån allt den innehåller. Ett ifyllt formulärfält bär inmatningen i
  `value`, ett JavaScript-gränssnitt lagrar sin datamängd i `data-…`,
  och blocket för sökmotorer (JSON-LD) upprepar det fullständigt och
  välformat: namn, födelsedatum, adress, telefon. Den synliga texten
  var rensad, allt detta stod fortfarande kvar.

  Nu städas även dessa ställen, tillsammans med `aria-…` (det som läses
  upp för skärmläsaren), `placeholder`, `summary` och det föreslagna
  filnamnet för en referens. JSON-LD-blocket läses därvid som data och
  förblir giltigt – dess nycklar och dess vokabulär blir kvar, bara
  värdena försvinner. Vanlig JavaScript rörs fortfarande inte.

- **Bilder förlorar sina tilläggsdata även utan EXIF.** Ett foto bär
  fotografnamn, tagningstid och GPS-koordinater för tagningsplatsen
  skrivna vid sidan – vid en lägenhetsannons avslöjar det adressen,
  även om ingen står i texten. Det togs bort så länge bilden hade
  EXIF. Var uppgifterna dock **bara** lagrade som XMP (så sparar
  Lightroom och Photoshop) eller som ett textblock i ett PNG (`Author`,
  `Comment`), förblev bilden helt orörd. Båda identifieras och tas nu
  bort – även vid bilder som sitter i ett dokument och bevaras där.
  Orienteringen överlever fortfarande, och en bild utan tilläggsdata
  sparas inte i onödan på nytt.

- **Referensmål i kalkylblad, presentationer och Word-dokument.** Vart
  en referens leder står inte i texten, utan i en egen förvaring i
  filen. En mejladress bakom „Mail schreiben" överlevde därför
  rensningen oskadd, medan samma adress i texten var ersatt.
  `mailto:` och `tel:` städas där nu likaväl som i sparade webbsidor.

### Nytt

- **Läkarbrev kommer inte längre tillbaka skadade.** Tidigare tog
  namnigenkänningen läkemedelssubstanser för personnamn: ur
  „Metoprololsuccinat" blev `[NAME]`, ur „Ramipril" blev `[ORT]`.
  Medicineringsplanen var därefter oanvändbar – medan diagnoserna
  förblev orörda, alltså precis tvärtom. Uppmätt berörde det **63 % av
  substanserna** och **53 % av de kliniska fackbegreppen**, och inte
  bara på tyska: över sju språk 74 %, på italienska alla kontrollerade.

  Maskuro känner nu till det medicinska ordförrådet och lämnar det i
  fred. Kvar blir 6 % i stället för 43 % (tyska) och 1 % i stället för
  74 % (över språken). Där en tilltalsform står framför – „Sehr geehrte
  Frau …" – förblir namnet ett namn, även om det råkar heta som en
  läkemedelssubstans.

- **Sjukdomar och läkemedel går att ta bort – om du vill.** Ny bock i
  inställningarna: „Ta bort sjukdomar och läkemedel också" (kommandorad:
  `--mit-diagnosen`). För personalakter, uppsägningar och utlåtanden,
  där diagnosen inte angår någon.

  **Förinställt av**, och det med avsikt: ett läkarbrev *består* av
  diagnoser och substanser. Den som anonymiserar ett sådant – för
  forskning, för en utbildning, för ett KI-verktyg – vill oftast behålla
  just detta innehåll och bara bli av med vem det gäller. Diagnosen är
  där nyttolasten, inte legitimationen.

  Igenkänningen hittar de vanliga beteckningarna och ersätter inte
  genomgången: en sjukdomslista är aldrig fullständig, för att läkaren
  skriver „C2-Abusus", där klassifikationen använder „Störungen durch
  Alkohol".

- **Diagnos- och läkemedelsnycklar hittas.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) och farmacevtiskt centralnummer är hälsouppgifter som
  varje utskriven diagnos – i utskrivningsbrev och avräkningshandlingar
  till och med den vanligare formen. De är förinställda på, som de
  övriga särskilda kategorierna enligt art. 9 GDPR.

  En diagnosnyckel identifieras bara med belägg: med „ICD" framför
  eller i parentes bakom diagnosraden. Utan detta villkor skulle
  programmet ta funktionstangenten **F10** för en beroendediagnos – i
  klassifikationen är F10 just det.

- **Den färdiga filen kan nu kopieras.** Vid varje färdig rad står
  bredvid „Visa", „Efterbearbeta" och „Visa i mapp" en fjärde knapp:
  **Kopiera**. Den lägger den rensade filen i urklipp – därifrån går
  den med Ctrl+V (Mac: ⌘V) till ett mejl, ett chattfönster eller ett
  KI-verktyg, utan omvägen via mappen.

  Kopierat blir **filen**, inte dess text: sidlayout, bilder och
  maskeringsstrecken bevaras därmed. Via listans kontextmeny går även
  flera markerade resultat samtidigt till urklipp, och i menyn „Arkiv"
  står samma väg som **„Kopiera resultat"** för alla som hellre
  använder tangentbordet.

- **Landvalet kan nu följa dokumentet.** ID-, socialförsäkrings- och
  skattenummer skiljer sig från land till land, och vilka länder som
  kontrolleras stod tidigare fast för hela sessionen – härlett ur
  gränssnittets språk. Den som arbetar på tyska och rensar ett franskt
  brev sökte alltså i det efter tyska skatte-ID:n och inte efter det
  franska personnumret.

  I regelfönstret finns för det nu **„Automatiskt efter dokumentets
  språk"**. Det fasta valet finns kvar bredvid, och det med avsikt:
  språkigenkänningen är inte ofelbar – identifierar den fel, används
  fel landval. Den som bara bearbetar akter från ett land är säkrare
  med den fasta listan.

  Oberörda av detta förblir de **tyska** mönstren (skatte-ID, KFZ,
  Durchwahl): de hänger på språket, inte på landvalet, och verkar
  fortfarande även när en kort tysk text klassas som engelska.

- **Lösenord, nycklar och inloggningsnamn hittas nu.** Den som klistrar
  in ett felmeddelande, en logg eller ett utdrag ur en
  konfigurationsfil i ett KI-fönster har nästan alltid en åtkomstnyckel
  i det – och den stod tidigare oförändrad kvar.

  Identifieras blir båda: de vanliga nyckelformerna som talar för sig
  själva (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token,
  huvudet på en privat nyckel), och den betecknade formen –
  „Passwort:", „API-Key =", „Token:", „Benutzername:". Ersatt blir
  bara värdet, aldrig beteckningen: „Passwort: [ZUGANGSDATEN_1]" förblir
  läsbart, och den som kontrollerar resultatet ser att ett lösenord
  stod där.

  Inloggningsnamn och lösenord är två skilda typer. Den som bara vill
  ta bort lösenord stänger av den ena och behåller den andra.

- **Streck- och QR-koder i bilder görs okännbara.** På ett inskannat
  beslut sitter nästan alltid en kod, och i den står diarienumret –
  samma nummer som tas bort i texten bredvid. Tidigare blev den
  maskinläsbara versionen kvar: strecket över numret gör ingen nytta om
  två centimeter bort en enhet läser av det på en sekund.

  Identifieras blir QR-kod, Data Matrix, Aztec, Code 128, EAN och de
  övriga vanliga formerna. Okännbar betyder pixlerad, och grövre än vid
  ansikten: felkorrigeringen i en kod hämtar ur få bevarade fält
  förvånansvärt mycket tillbaka, en halvhjärtad slöja vore ingen
  borttagning.

  Alternativet står bredvid „Gör ansikten okännbara" och är likaså
  **förhandsvalt**. Även vid avslaget alternativ säger rapporten hur
  många bilder som bär en kod – ett ansikte ser man vid bläddring, en
  kod ser man som tillbehör.

- **Kortkontrollnummer, PIN och utgångsdatum hittas.** Kreditkortsnumret
  hittade programmet redan; först med de tre uppgifterna bredvid är det
  användbart, och på varje avräkningsbelägg står de tillsammans. Alla
  tre bara bakom sin beteckning – „123" ensamt är ett husnummer, ett
  sidnummer eller ett antal.

- **Koordinater i texten hittas.** Ur bilder har Maskuro redan tidigare
  tagit bort tagningsplatsen; stod samma uppgift som text i utlåtandet
  eller i insatsrapporten, blev den kvar. Identifieras blir decimalgrader
  och grad-minut-sekund-skrivsättet. Vid decimalgrader måste ett ord
  som „Standort", „Fundort" eller „Koordinaten" stå i närheten – annars
  vore varje mätserie med två decimaler en ortsuppgift.

- **Penningbelopp går nu att ta bort med.** Ny bock „Ta bort penningbelopp
  också", förinställd **av** som datumangivelserna ovanför: i ett avtal
  är beloppet innehållet, och den som maskerar allt skyddar ingen. I en
  lönespecifikation, ett förlikningsförslag eller ett kontoutdrag är det
  däremot exakt den uppgift som säger mer om personen än namnet
  bredvid – det vet bara den som har handlingen framför sig.

  Ett belopp identifieras **bara med valutaangivelse**: „4.250,00"
  ensamt är ett antal, först „4.250,00 EUR" är pengar. Valutasymbol,
  förkortning och utskrivet namn räknas, före som efter, tillsammans
  med skrivsättet „990,– CHF".

- **De särskilda kategorierna enligt art. 9 GDPR identifieras.**
  Religionstillhörighet, facklig tillhörighet, politisk övertygelse,
  hälsouppgifter – och bredvid de straffrättsliga uppgifterna enligt
  art. 10. Det är de uppgifter vars behandling förordningen i grunden
  **förbjuder**; de är därför som enda nya grupp förinställda **på**.
  Den som vill behålla dem avgör det.

  Identifieras blir den form de i praktiken förekommer i:
  formulärfältet på personalbladet – „Religionsbekenntnis: röm.-kath.",
  „Gewerkschaft: ÖGB", „Grad der Behinderung: 50", „Vorstrafen: keine" –
  och det både med kolon bredvid och med beteckningen ovanför, som ett
  ifyllt blad levererar dem.

  **Löptexten hör till KI-nivån.** „Er engagiert sich seit Jahren in
  der Gewerkschaft" är samma uppgift, och inget sökmönster hittar den
  tillförlitligt. KI-nivån söker sedan denna version uttryckligen
  även efter dessa kategorier; den som behöver löptexten slår på den.

- **Personkännetecken och yrke – uppgifterna som även utan namn visar
  vem som avses.** Kön, civilstånd, kroppslängd, ögon- och hårfärg tas
  bort från denna version; yrke, funktion och avdelning på begäran, via
  en egen bock („Ta bort yrke och avdelning också") eller
  `--mit-berufen`.

  **Varför det ena är på och det andra av:** „Die Leiterin der
  Abteilung Einkauf" betecknar i ett företag exakt en person, även om
  namnet bredvid är maskerat – i ett utlåtande eller en uppsägning hör
  det bort. En personalöversikt *består* däremot av
  yrkesbeteckningar; den som förinställt tog bort dem skulle lämna
  tillbaka ett tomt blad. Vilket fall som föreligger vet bara den som
  har handlingen framför sig. Kännetecknen ovanför står nästan bara i
  formulärfält, är sällsynta och bär aldrig innehållet – de kostar
  alltså inget.

- **Kontrollera en främmande fil.** „Arkiv → Kontrollera fil …" läser
  ett redan maskerat dokument igen och meddelar vad som fortfarande
  finns kvar – och **var**: sida och rad, typ och längd. För fallet att
  någon kontrollerar en annans arbete: en akt från advokatbyrån, en
  upplysning från myndigheten, den egna utgående posten före sändning.

  **Själva värdet står inte i rapporten.** Den som slår upp stället ser
  det ändå – och rapporten får därför sparas och lämnas vidare utan att
  själv vara en samling personuppgifter.

  **Och rapporten säger i varje fall vad den inte kunde se.** Bilder
  läses inte; vid en skanning utan textskikt betyder „inget fyndställe"
  *inte kontrollerad*, inte *ren*. På kommandoraden skiljer
  returvärdet det: `--nachpruefen` levererar 0 för kontrollerad och
  ren, 4 för fyndställen och 5 för inte kontrollerbar. Därmed går
  utgående post att hålla tillbaka automatiskt, i stället för att vinka
  igenom den.

- **Kontrollrapport: ett blad per rensning.** „Arkiv → Spara
  kontrollrapport …" – eller `--pruefbericht <mapp>` på kommandoraden –
  skriver en ensidig PDF (valfritt CSV eller text) med uppgifter om
  körningen, de hittade typerna med antal, två nyckeltal och en
  kontrollanteckning. För akthängmappen och för tillsynen:
  kontrollprotokollet är det hållbara belägget, men ingen visar upp en
  JSON-Lines-fil.

  **Nytt är två siffror**, som tidigare inte gick att se någonstans:
  den *genomsnittliga konfidensen* – hur säker igenkänningen var på det
  den hittat – och *maskeringsgraden*, andelen ersatta tecken i texten.
  Båda står med sin gräns: konfidensen säger **inget** om förbisett, och
  bredvid den står alltid hur många träffar den alls gäller; graden
  räknar inte med bilder och blir för hög vid ett bildrikt dokument.

  **Hittade värden står inte på bladet** – samma gräns som vid
  protokollet och sökkörningen. Nedtill står två rader som inte säger
  samma sak: kontrollsumman visar att bladet är oförändrat; loggraden –
  bara vid löpande protokoll – hänvisar till den **signerade** raden som
  belägger körningen. Först den bevisar ursprunget.

- **„Hur säkert var det?" – nyckeltalen vid resultatet.** En knapp
  „Nyckeltal" under resultatet fäller upp det som tidigare inte syntes
  någonstans: fyndställen, ord och tecken, fördelningen per typ som en
  stapelrad, dessutom den genomsnittliga konfidensen och
  maskeringsgraden. Samma siffror som i kontrollrapporten, bara
  omedelbart och utan utskrift.

  **Med sitt förbehåll i samma yta:** bredvid konfidensen står hur
  många träffar den gäller, och därunder meningen att den **inget**
  säger om förbisett. En procentsats utan denna mening läses som en
  träffkvot – och den som förstår den så är sämre ställd än utan
  siffran.

  Beräknas görs först vid uppfällning: nämnaren för maskeringsgraden
  kostar per fil en inläsning, och den ska inte betalas av den som
  aldrig ser på siffrorna.

- **Bygg egna sökmönster utan att skriva ett.** Fliken „Egna sökmönster"
  leder nu i tre steg genom saken: *Vad söker du? → Hur ser en sådan
  uppgift ut hos dig? → Namnge och spara.* Du skriver in ett exempel –
  till exempel `KD-004711` –, programmet härleder regeln ur det och
  skriver i ord vad den söker efter. En förhandsvisning med
  träffräknare kontrollerar med vid varje tangenttryckning.

  **Ett reguljärt uttryck förekommer inte i det.** Kunnandet var aldrig
  problemet: egna sökmönster har funnits länge, men krävde ett uttryck
  som `\bKD-\d{6}\b`, och det skriver ingen på en advokatbyrå eller
  personalavdelning. Den som *vill* skriva ett fäller upp expertläget.

  **Mallkatalogen är nysorterad:** tretton kort med namn, förklaring och
  exempelvärde, filtrerade via kategorimärken – finans, myndigheter,
  kontakt, personal, medicin.

  Och om det härledda mönstret är för brett, säger programmet det själv:
  ett exempel med enbart siffror träffar varje årtal och varje belopp,
  och den som inte kan läsa uttrycket kan annars inte märka det.

- **Sju märken i stället för femtiosex bockar.** En ny flik „Vad som
  söks" samlar alla identifierbara typer i sju grupper – person, kontakt
  och ort, identifierare, finans, teknik, särskilda kategorier, företag
  och egna. Ett märke slår av dess grupp, „Alla på" och „Alla av" hela
  listan; därunder förblir varje typ enskilt bockbar.

  **Förinställt är allt på, och det förblir så.** Det som stängs av här
  söks alls inte – det grövsta ingreppet regelfönstret tillåter, och
  det verkar på varje dokument. Därför står under listan alltid hur
  många typer som är av, och sparat blir bara det avstängda: en ny typ
  är därmed även i en regelfil från förrgår på, i stället för att tyst
  falla utanför.

- **Överföra en ram till alla sidor.** I efterbearbetningsfönstret tar
  knappen **Överför till alla sidor** den senast dragna ramen och
  maskerar samma ställe på varje ytterligare sida – för brevhuvud,
  sidfot och diarienummerfält. Vid en skannad akt med åttio sidor blir
  det tjugo minuter av till två.

  **„Samma ställe" betyder samma *relativa* plats på bladet.** I en
  bunt från inmatningen ligger regelmässigt en sida på tvären, en annan
  är A3, en tredje roterad; en absolut överförd rektangel hamnade där
  bredvid brevhuvudet – och man skulle se ett streck och tro saken
  klar.

  **Det maskeras, ersätts inte**, även om utgångsramen var en
  platshållare: under samma rektangel står på sida fyrtio något annat
  än på sida ett, och en platshållare med samma nummer skulle påstå en
  likhet som inte finns.

- **En anteckning på maskeringsstrecket.** I aktinsynsrätten står
  bredvid varje maskering varför det maskerades. Det nya fältet
  **Anteckning på strecket** i inställningarna – eller
  `--balkenvermerk` – skriver en kort text på varje streck: „§ 203
  StGB", „DSGVO", „konfidentiellt". För ett dokument som en myndighet
  lämnar ut är det skillnaden: mottagaren ser skälet, utan att ha ett
  protokoll som hen ändå aldrig får.

  **Förinställt tomt**, för anteckningen är synlig i det utlämnade
  dokumentet och själv en uppgift – den säger mottagaren under vilken
  titel något hålls tillbaka. Den verkar bara vid **maskering**; där
  en platshållare står finns inget streck. På ett streck som är för
  litet för läsbar text uteblir den – en oläslig anteckning ser ut som
  ett fel.

- **Aktivera utan internetanslutning – nu fullständigt.** I
  licensfönstret fanns „Aktivera utan internet" redan sedan länge: högst
  upp en anfordringskod att ta med, längst ner fältet för aktiveringen
  som kommer tillbaka. Bara att den hittills **ingen kunde utfärda** –
  verktyget för det saknades, och koden gick ut i intet. Det är
  åtgärdat.

  För myndigheter och advokatbyråer med avskärmade datorer är det inget
  specialfall, utan normalfallet – och det är just den målgrupp för
  vilken löftet „dina dokument lämnar aldrig datorn" väger tyngst.
  Koden avslöjar inget om dokument: den innehåller licensidentifieraren
  och ett streuvärde för datorn, inget annat.

- **Hämta från skanner.** „Arkiv → Hämta från skanner …" läser in en
  bunt direkt och lägger sidorna i listan – för en poststation
  skillnaden mellan två arbetssteg och ett. Ett dokumentmatningsfack
  töms till sista sidan; enhet, upplösning och färg väljs i skannerns
  systemdialog, som du ändå känner till.

  **Rensning sker inte automatiskt.** Du ser först vad som kommit in,
  och trycker sedan „Rensa" som för vilken annan fil som helst – en
  skanning som genast körs igenom skulle ta bort blicken på en snett
  inmatad bunt.

  **Detta finns bara under Windows**, och menyposten säger det även på
  Mac: där skriver din skanners programvara till en mapp, och „Övervaka
  mapp …" rensar allt som hamnar där.

### Övrigt

- **Listan över alla hittade uppgifter medföljer nu** och genereras ur
  källkoden (`hilfe/GEFUNDENE-ANGABEN.md`): 177 typer i 35 länder,
  23 av dem med kontrollsiffreberäkning. Den nämner även hur räkningen
  gjorts – vi räknar `[NAME]` en gång, där andra för för-, mellan- och
  efternamn som tre poster.

- **Maskering finns nu även i Word, PowerPoint, OpenDocument och
  HTML.** Valet mellan platshållare och maskering gällde tidigare bara
  PDF-filer. Nu kan även de andra det: fyndet tas bort, och på dess
  plats står ett svart streck – i själva dokumentet, inte som en bild
  ovanpå. Den som lämnar filen vidare lämnar en maskerad akt, inte en
  där det maskerade fortfarande ligger som text under.

  **Det avgörs separat**, i två valfält: „Vid PDF" och „Vid Word,
  PowerPoint, OpenDocument och HTML". Man vill det olika – det maskerade
  PDF-dokumentet går till myndigheten, samma sak som Word-fil vandrar
  vidare genom huset och ska förbli läsbar. På kommandoraden
  motsvarande `--pdf-modus` och `--office-modus`; ett sparat
  „Maskera" från tidigare versioner gäller fortfarande PDF.

  I kalkylblad, ren text, CSV och e-post fungerar inte strecket – där
  saknas ytan det skulle kunna läggas på. Det sätts fortfarande in en
  platshållare, och resultatet **säger det nu**, i stället för att göra
  det tyst.

- **Nytt: „Ta bort" – fyndstället förblir helt enkelt tomt.** Det tredje
  driftläget bredvid platshållare och maskering, och det enda som klarar
  **varje** format: att utelämna något behöver ingen yta. I PDF ritas
  inget, i Word och HTML förblir stället tomt, i ett kalkylblad likaså.

  Det är det tystaste av de tre: den som läser resultatet ser inte att
  något någonsin stod där – inte heller värdets längd avslöjas längre.
  För en handling som någon ska kontrollera förblir platshållaren
  oftast det bättre valet.

  I bilder gäller inget av de tre valen: bildpunkter går inte att
  ersätta med en platshållare eller utelämna. Vad textigenkänningen
  hittar där övermålas fortfarande som förut.

- **Efterbearbetningsfönstret påstår inte längre ersättningar som inte
  finns.** Till höger stod för varje värde en platshållare – även vid
  en maskerad fil, där ingen enda förekommer. Ett klick på en sådan rad
  markerade inget, och „Ångra" gick i tomma intet. Nu står där
  „maskerad" respektive „borttagen", och raderna går alls inte att
  ångra: texten är borta, det finns inget att hämta tillbaka. Detta
  gällde maskerade PDF-filer, Word och OpenDocument samt allt som
  hittades i bilder.

- **Textvyn visar nu strecken som streck.** En maskerad Word-fil såg
  vid efterbearbetning **tom** ut: på de maskerade ställena stod
  luckor, som om programmet svalt texten. Orsaken var visningen, inte
  resultatet – i själva dokumentet låg strecket hela tiden rätt. Nu
  står det även i vyn där, svart som i resultatet, i Word, PowerPoint,
  OpenDocument och HTML.

- **Outlook-meddelanden (`.msg`) rensas nu.** `.eml` fanns länge – i
  tyska företag är Outlook dock e-posten, och där heter ett sparat
  meddelande `.msg`. Därmed är det tätaste PII-formatet också täckt i
  sin vanligaste lagringsform: ämne, avsändare, mottagarrader,
  meddelandetext, HTML-version, mottagarlista och bilagor – de senare
  via de befintliga vägarna och med samma platshållare som mejltexten.

  **En `.msg` bär samma text flera gånger**, och det är fällan: som
  rentext, som HTML **och** som RTF. Den som bara rensar rentexten har
  inte gjort något – Outlook visar företrädesvis RTF:en. RTF-versionen
  tas därför bort helt, likaså internethuvudraderna med sin
  received-kedja och de binära sökningsnycklarna, som namn och adresser
  överlever varje textrensning. Resultatet öppnas fortfarande i Outlook
  och visar texten utan formatering; rapporten säger det uttryckligen.

- **Beskriva regler med egna ord i stället för att skriva regex.**
  Regelfönstret kan mycket och krävde för det ett reguljärt
  uttrycksmönster – stället där det slutar för de flesta. Nu räcker en
  mening: „Unsere Aktenzeichen der Form 12 C 345/26 sollen stehen
  bleiben." KI-nivån föreslår därur termer och sökmönster.

  **Övertaget blir bara det du bockar i – och förinställt är inget
  ibockat.** Vid varje förslag står en mening om vad det betyder, och
  antalet träffar i en exempeltext du kan lämna med. Vad som **tar bort**
  skydd är märkt som sådant: „ta alltid bort denna term" och „ta aldrig
  bort denna term" skulle annars se likadana ut i en lista. Förslag som
  skulle passa på allt visas inte alls.

- **Kontrollprotokollet räknar nu ihop över alla arbetsplatser.**
  Lägger ett hus protokollen via `protokoll_pfad` på en delning,
  skriver varje arbetsplats där sin egen månadsfil – tidigare var ett
  dataskyddsombud med trettio platser tvunget att se på trettio filer
  var för sig. Ovanför listan står nu en rad med månadens summor, och
  **den rapporterar brutna kedjor med namn**: en efterhandsändring
  märks bara om någon ser efter, och i trettio filer ser ingen efter
  för hand.

  **Ingen sammanställning per person** – inte heller i denna vy. En
  rankning „vem har rensat hur mycket" skulle lämpa sig för beteende-
  och prestationskontroll, och det är vad som avgör
  medbestämmanderättsligt, inte avsikten. Räknas görs körningar, filer
  och träffar över huset.

- **„Föreslå profil ur en handling": fråga reglerna en gång i stället
  för att gå igenom fyrtiofyra typer.** I regelfönstret finns en ny
  knapp: den visar KI-nivån en handling, fastställer vad det rör sig om
  – läkarbrev, ansökan, avtal, faktura, beslut – och föreslår de
  strategier som passar. Vid läkarbrevet till exempel förskjuts
  datumangivelser i stället för att ersättas, eftersom kronologin i en
  patientjournal är innehållet.

  **Profilerna finns i programmet, modellen bara väljer** – 
  maskeringsreglerna hänger inte på vad en språkmodell tycker är en bra
  idé. Föreslaget blir varje punkt enskilt och med motivering; övertaget
  blir inget utan återfråga, och vad du själv fastställt förblir orört.
  Utan KI-nivå gäller fortfarande det säkra förvalet: platshållare för
  allt.

- **Ny strategi „hitta på": ett troligt falskt värde i stället för en
  platshållare.** „Frau Berger schrieb an Herrn Doppler in Fulda" i
  stället för „[NAME_1] schrieb an [NAME_2] in [ORT_1]" – för
  utbildningsmaterial, demoakter, testdatabestånd och allt som
  därefter förs till en KI. Tilltal, satsbyggnad och läsbarhet
  bevaras.

  Samma värde får samma falska värde, över alla filer i ett ärende och
  på varje dator med samma regelfil – **utan att någonstans en
  tilldelning sparas** (samma mekanik som vid hashning). Mejladresser
  ligger på reserverade exempeldomäner, telefonnummer i det för det
  friställda området, hittade IBAN-nummer bär en korrekt beräknad
  kontrollsiffra. Möjligt för namn, orter, adresser, företag, mejl,
  telefon och IBAN; för andra typer avvisas regeln, i stället för att
  förbli verkningslös.

  **Rapporten säger uttryckligen att det hittats på.** Ett så rensat
  dokument läses som ett äkta och är inget – det duger inte som belägg
  och får inte lämnas vidare som original.

- **Kontrollprovet: „Vem förblir igenkännbar?"** En ny bock under
  KI-nivån lägger **det färdiga resultatet** för språkmodellen en gång
  till och frågar vem som trots rensning går att identifiera. Avses
  det fall som ingen igenkänning i världen hittar, eftersom inget namn
  alls står där: „den enda barnmorskan i distriktet", „kollegan som
  sa upp sig i mars efter branden". Inget mönster griper in, och på
  plats vet ändå alla vem som avses.

  **Inget tas bort därvid.** Ställena står med en motiveringsmening i
  rapporten, och avgörs för hand – ett program som av sig själv tar
  meningar ur en handling för att de förefaller det avslöjande, gör av
  en rensning en omskrivning, och ingen skulle se vad som saknas. Högst
  fem ställen per fil; vad modellen inte kan belägga ordagrant faller
  bort. På kommandoraden: `--restrisiko` tillsammans med `--ki`.

- **Vägen tillbaka ur KI:n: „Översätt svar tillbaka".** Tidigare var bara
  halva slingan byggd – kopiera text, klistra in rensad, förelägga
  KI:n. Svaret kom tillbaka med `[NAME_1]`, och den som behövde det
  satte för hand tillbaka det den för hand tagit bort. Nu står återvägen
  i menyn „Program": kopiera svar, klicka på posten, de riktiga namnen
  står där igen.

  Tilldelningen för det ligger **bara i arbetsminnet**, gäller alltid
  bara det senast rensade stället och löper ut efter en timme; den som
  stänger av urklippsövervakaren blir av med den genast. Bara det som
  ersatts går att hämta tillbaka – maskerat, maskat och hashat är inte
  omvändbart, och programmet säger hur många ställen det därför
  behövde lämna kvar. Hanterade installationer stänger av återvägen
  helt via vorgaben `rueckweg`.

- **Övervaka mapp: det som läggs in ligger strax efteråt rensat i
  utgången.** För en poststation, ett postfacksteam eller en
  skanningsmapp – ställ in en gång, sedan klickar ingen mer. Finns
  under „Arkiv → Övervaka mapp …", på kommandoraden via
  `--wache <mapp>`.

  Originalet blir liggande där det låg; på begäran flyttas det
  oförändrat till undermappen „Klart", varvid inget någonsin skrivs
  över. En fil rörs inte förrän den är färdigskriven – en fil som
  fortfarande kopieras över nätet skulle annars läsas halvvägs och
  meddelas som rensad. Det som går fel blir liggande och rapporteras,
  i stället för att upprepas i oändlighet. Och vakten kommer ihåg det
  klara utan filnamn: det som ligger i en ingångsmapp avslöjar ofta
  redan i namnet vad det handlar om.

  **Övervakning av en mapp utanför den egna användarprofilen – till
  exempel på en nätverksenhet – kräver en automatiseringslicens.** En
  mapp som flera personer når är en tjänst och ingen arbetsplats; i
  den egna profilen och under provperioden gäller begränsningen inte.

### Rättat

- **Inställningarna var avskurna till höger.** Fönstret öppnades med en
  fast storlek, och den räckte bara för den teckenstorlek programmet
  utvecklades med: på Mac stod „Kontrollera nu", „Ändra …" och
  hänvisningarna bredvid till hälften utanför. Nu öppnas det så brett
  som dess sidor behöver – på varje språk och vid varje teckenstorlek,
  begränsat bara av skärmen.

- **„Kontrollera nu" svarar nu synligt.** Resultatet stod i
  huvudfönstrets statusrad – alltså bakom inställningsfönstret, varifrån
  frågan ställdes. Den som kontrollerade såg inget. Nu kommer svaret
  som ett meddelande över inställningarna, och finns en ny version leder
  det genast till installation. Vid programstart förblir det som förut
  vid statusraden, oombett öppnas inget fönster.

- **Kopierade filer kom inte fram i urklipp på Mac.** Att lägga tillbaka
  rensade filer meddelade framgång och lade ändå inget användbart –
  inklistring gav ingenting. Berört var allt som skriver filer till
  urklipp.

- **Och ur urklipp lästes på Mac bara den första filen.** Den som
  kopierade tre filer i Finder och valde „Rensa urklipp nu" fick två
  av dem tillbaka orensade – utan att något sagt det. Nu kommer alla.

- **„Kontrollera fil" tar nu även emot dragna filer** – som
  huvudfönstret. Inlagt läggs till, i stället för att förkasta det
  tidigare valet; att lägga in samma sak två gånger ändrar inget, och
  det programmet inte kan läsa rapporteras i stället för att sväljas.

- **Och fönstret säger att det väntar på dig.** Det öppnades med en
  tom ruta och en grå knapp „Kontrollera" – det ser ut som om inget
  finns, inte som om valet saknas. Nu står där „Ingen fil vald ännu –
  dra hit eller välj nedan via 'Välj filer …'."

- **En lång körning säger nu att den pågår.** „Tilläggsmodellen för den
  noggrannare igenkänningen laddas – ett ögonblick …" blev kvar så
  länge igenkänningen beräknade: vid en fil med 47 500 ord alltså
  arton minuter, trots att laddningen var klar efter nio sekunder. Den
  som ser det tror programmet hängt sig. Nu följer „Noggrannare
  igenkänning pågår – detta tar vid långa texter några minuter", och
  statusraden räknar med: „Noggrannare igenkänning (7/312)".
  Rapporteras görs det ur modellens loop – var 250:e ord, alltså cirka
  var sjätte sekund –, inte per textblock: ett textblock bär
  tolvtusen ord och tar minuter.

- **En avbruten körning säger nu att den avbröts.** Den som tryckte
  „Avbryt" läste därefter „0 av 1 fil(er) rensad(e)." – rätt räknat och
  ändå fel besked. Meddelandet om vilken fil det drabbade skrevs över i
  samma ögonblick av räknemeddelandet. Och i fillistan stod fortfarande
  „pågår …", trots att inget längre pågick; där står nu „avbruten".

- **Meningen om integriteten var avskuren.** „… keine Cloud, kein
  Hochladen. Mehr im Datens" – vid den fönsterbredd programmet startar
  med slutade den mitt i ordet. Den tar nu hela bredden.

- **Licenstjänsten kunde meddela något, och ingen lyssnade.** När alla
  licensplatser är upptagna, licensen har löpt ut, nyckeln är okänd
  eller licenshanteringen hos leverantören är avstängd, skickar tjänsten
  just för det ett skäl – avsett var från början att du skulle få det
  förklarat **en gång**. Det visades aldrig. Nu visas en hänvisning som
  först säger att programmet fortsätter arbeta oförändrat, och sedan
  vad det handlar om. En gång per skäl: den som klickat bort den ser
  den inte igen vid den dagliga kontrollen – väl däremot om skälet
  ändras.

- **En i butiken köpt flerplatslicens visade „1 plats".** Butiken
  distribuerar förberedda nycklar och håller det köpta platsantalet hos
  sig; visat blev dock siffran ur själva nyckeln, och den lyder vid
  varje lagernyckel på en plats. Den som köpt åtta platser läste
  „1 plats" – och från och med den andra anmälda datorn stod
  indikatorn i rött tillsammans med „Kontakta din administration". Nu
  gäller siffran tjänsten senast rapporterat; utan svar förblir det vid
  nyckeln, och mindre än det köpta omfånget blir det aldrig. Detsamma
  gäller efterköp och förlängningar: de ändrar platsantalet hos
  leverantören, inte din nyckel.

- **Efter köpet stod „Licensierad för Maskuro Privatlicens".** Det är
  inget namn, utan platshållaren under vilken nycklarna förbereds –
  ditt namn kan inte stå där, eftersom nyckeln redan signeras före
  köpet. I stället för att visa dig ett främmande namn som ditt eget
  står det nu enkelt „Privatlicens" och platsantalet. Vid en licens som
  utfärdats till dig står ditt namn oförändrat där.

- **I hjälpmenyn stod „Hjälp _FAQ".** Och-tecknet hade blivit ett
  understreck, eftersom Qt läste det som markör för en
  tangentbordsbokstav. Nu står där „Hjälp & FAQ".

- **Inställningsfönstret blev kvar när programmet försvann till
  ikonen** – och även då när huvudfönstret stängdes. Det följer nu med.
  (Berör bara denna version; det egna fönstret är nytt.)

- **En avvisad licensförfrågan säger nu vad det beror på.** Avvisade
  licenstjänsten en förfrågan utan att skicka med ett skäl, stod i
  licensfönstret i rött „Okänt svar." – en mening som varken du eller
  supporten kan göra något med och som får dig att söka felet vid din
  nyckel. Nu står där vad som faktiskt hände: att tjänsten avvisat utan
  att motivera det, och till vem du kan vända dig. Är
  licenshanteringen hos leverantören tillfälligt avstängd, nämns det
  också – tillsammans med hänvisningen att din nyckel inte berörs av
  det.

- **På Mac gällde inställda språk plötsligt som saknade.** Vid start
  meddelade programmet „Ingen språkmodell installerad" och erbjöd
  förstainställningen, trots att språken länge var laddade – den som
  såg efter under „Dokumentens språk" hittade dem fullständigt där.
  Programmet sökte dem beroende på startväg på två olika platser:
  startades det från programmappen, hittade det dem; startades samma
  bygge som en enkel mapp, sökte det dem bredvid sig, där inga ligger.
  Från och med nu gäller på Mac undantagslöst samma plats i
  användarprofilen, oavsett hur programmet är förpackat. Inget behöver
  laddas ned på nytt.

- **„Vad är nytt" visade halva listan.** Fönstret efter en uppdatering
  avbröts mitt i en mening, och de återstående punkterna stod som tomma
  punktlistetecken. Skulden bar en platshållare i vinkelparenteser –
  till exempel `<datei>.docx` –, som visningen tog för formatering och
  från vilken allt vidare förkastades. Just säkerhetsnyheterna var
  berörda av detta. Hjälpen har alltid visat sådana platshållare rätt;
  nu gör detta fönster det också.

- **Att nypa med två fingrar zoomar nu i
  efterbearbetningsfönstret.** På styrplattan är det *den* zoomgesten –
  i editorn gjorde den tidigare inget, och den som ville se ett ställe
  närmare fick ta till reglaget eller Ctrl+mushjul. Sidan följer nu
  gesten direkt och ritas skarpt igen vid släppning.

- **Zoomat blir på det ställe man tittar på.** Att nypa förstorar runt
  punkten mellan fingrarna, Ctrl+mushjul runt punkten under pekaren.
  Knappar, tangentbordskortkommandon och zoomreglaget håller mitten
  fast – till dem hör inget ställe man pekar på. Tidigare förblev vid
  alla bara rullvärdet stående: från en anpassad sida höll det överkanten
  fast, och allt under vandrade vid inzoomning ur bilden.

- **„Före/Efter" var i sidvisningen en död knapp.** Så länge
  sidvisningen var på, gick den att trycka – och meddelade varje gång
  att originalet inte gick att öppna. Att jämföra finns inget där
  heller: sidvisningen är en avbild av den rensade versionen, en
  motsvarighet till originalet finns inte. Knappen är nu spärrad och
  nämner vid överfarande skälet tillsammans med utvägen (textvyn). Dess
  beskrivning lovade dessutom uttryckligen att jämförelsen skulle gälla
  „oberoende av om text- eller sidvisning är aktiv" – det stämde
  aldrig.

- **Sidvisningen fick LibreOffice att krascha.** Skapades två
  sidvisningar samtidigt – till exempel „Maskera som PDF" medan
  förhandsvisningen fortfarande räknade –, meddelade systemet en
  LibreOffice-krasch, trots att sidorna till slut ändå visades: båda
  körningarna kom åt samma LibreOffice-arbetsförvaring, vilket det inte
  tål. Nu får bara en körning den; de övriga byter till en egen. De
  behöver för det några sekunder längre, men inget felmeddelande kommer
  längre, och ingen av körningarna blir utan resultat. Ett andra
  renderingsuppdrag bredvid ett pågående tas dessutom alls inte emot.

- **„Visa original" kunde avsluta programmet.** Gick originalet inte att
  öppna – för att det flyttats, döpts om, försetts med lösenord eller
  ligger på en frånkopplad enhet –, kraschade
  efterbearbetningsfönstret utan förvarning, och öppna arbetskopior gick
  förlorade. Nu kommer en hänvisning, brytaren hoppar tillbaka, och den
  rensade versionen blir kvar. Där originalet i grunden inte passar
  bredvid – till exempel vid en PDF-sidvisning som skapats ur en
  Word-fil – är brytaren från början spärrad och nämner vid överfarande
  skälet, i stället för att vid varje tryckning visa samma hänvisning.

- **Felrapporter kom aldrig fram.** Den som ville rapportera ett fel
  fick „Motparten avvisade rapporten" – och ingen hade någonsin sett
  den. Två orsaker, båda på vägen: programmet legitimerade sig inte hos
  servern och avvisades därför av skyddet mot massåtkomst, och adressen
  pekade på ett andra namn, som programmet inte följde. Båda är
  åtgärdade; en rapport går ut igen. **Detsamma drabbade
  licensaktiveringen**: anmälan, avanmälan och förfrågningar nådde
  tjänsten inte heller – där bara omärkligt, eftersom en obesvarad
  förfrågan medvetet inget ändrar i din licens. Och förblir en avvisning
  ändå oförklarlig, står nu dess tekniska nummer med, i stället för att
  varje orsak ser likadan ut.

- **Ett klick på „Visa original" kunde avsluta programmet.** Gick
  originalet inte att öppna – flyttat, omdöpt, på en frånkopplad
  nätverksenhet, försett med lösenord eller skadat –, försvann
  efterbearbetningsfönstret tillsammans med alla öppna arbetskopior. Nu
  förblir omkopplaren vid den rensade versionen, och en ruta säger vad
  som händer; det tekniska skälet står i detaljerna, om du vill
  rapportera det. Detsamma gäller ett resultat som inte går att visa:
  fönstret öppnas och säger det, i stället för att försvinna.

- **Frågan om en krasch kom för ofta – och raderade spåret den frågade
  om.** Den visades även när inget kraschat: anteckningen skapas så
  snart en oväntad störning uppstår någonstans, även om programmet
  överlever den och sedan avslutas helt vanligt; den städades aldrig
  bort. Och den som svarade „Nej" förstörde de enda detaljerna om
  händelsen – anteckningen försvann redan vid *visningen* av frågan.
  Båda är åtgärdade: ett ordnat slut städar bort anteckningen, frågas
  görs bara vid en verklig krasch, och avbockat blir det först efter
  ditt svar. Detaljerna står ändå i felloggen på den egna datorn – den
  som inte vill skicka något förlorar ändå ingenting. Skickat blir
  fortfarande bara det du sett fullständigt i förväg och själv
  godkänt.

- **„Rensa" kunde förbli tyst spärrad.** Hänger sig språkmodellerna vid
  laddning, förblev knappen avstängd – utan förklaring. Ett klick på
  den gjorde inget, och statusraden sa oförändrat „Språkmodeller
  laddas …", även efter tio minuter. Orsaken: störningar i
  bakgrundsförlopp gick till ett ställe som ingen ser vid start från
  filhanteraren; kvar blev ett fönster som såg arbetsberett ut och inte
  reagerade på något klick. Nu hamnar sådana störningar i felloggen,
  laddningen av språkmodellerna meddelar sitt misslyckande i varje fall
  i stället för att tyst ge upp, och förblir det ändå tyst, säger
  programmet efter tre kvarts minut att något inte stämmer, med ett
  råd i detaljerna. Den spärrade knappen nämner vid överfarande sitt
  skäl. En lång första nedladdning gäller därvid inte som tystnad: så
  länge förlopp rapporteras, förblir det lugnt. Som krasch räknas allt
  detta inte: programmet fortsätter köra, och vid nästa start frågas
  därför inte heller efter det.

- **På Mac hittade programmet inga uppdateringar längre – och sa att det
  var på senaste versionen.** Mac-versionen medförde ingen förteckning
  över rotcertifikat; den sökte den på ett ställe som bara finns på
  datorn den byggs på. Därmed kunde den inte hos någon server
  kontrollera vem den talar med, och avbröt varje anslutning: inga
  uppdateringar, ingen licensaktivering, ingen nedladdning av
  språkmodeller, ingen felrapport. Äldre versioner gjorde tyst av det
  beskedet „Du använder den senaste versionen". Certifikaten ligger nu
  i själva programmet; hittar det inga där, tar det systemets och på
  Mac i nödfall nyckelringens – och finns det inga alls, säger det det,
  i stället för att påstå en senaste version. Själva kontrollen stängs
  aldrig av.

  Denna enda uppdatering måste Mac-användare fortfarande installera för
  hand: en version som inte når servern kan inte heller förnya sig
  själv.

### Ändrat

- **Huvudfönstret har städats upp.** Nedtill stod sex lika stora knappar
  bredvid varandra – „Om …", „Anvisning" och „Hjälp & FAQ" därunder,
  trots att samma tre vägar redan stod i Hjälp-menyn ovanför. De är nu
  slagna ihop till en knapp „Hjälp" som fäller upp dem; ingen försvinner.
  Kvar nedtill blir de två vägarna man verkligen börjar med: „Rensa" och
  „Maskera för hand …".

- **Vad programmet just gör står nu på en fast plats.** Meddelandet
  („Språkmodeller laddas …", „(3 / 7) brief.pdf", „5 av 7 fil(er)
  rensad(e).") hängde tidigare som grå text mellan två knappraders. Det
  har fått en egen yta, med en färgad punkt framför: grå så länge inget
  pågår, blå under arbetet, grön efter en problemfri körning och gul
  när hänvisningar tillkommit. Punkten säger inget som inte står
  bredvid – den säger det bara snabbare.

- **Inställningarna har blivit ett eget fönster.** De låg tidigare i
  huvudfönstret – en ruta med fyra flikar som fälldes upp under „Fler
  inställningar", och som sedan var för liten för sitt innehåll: en
  rullningslist stod alltid i den, och valet mellan Anonymisera och
  Pseudonymisera stod halvt utanför bilden. Knappen heter nu
  „Inställningar …" och öppnar ett fönster med en sidopanel; var och
  en av de fyra sidorna får plats helt. Huvudfönstret hoppar inte
  längre upp vid öppning, och man kan se fillistan bredvid. Ändrat har
  bara var inställningarna finns – vilka det finns och vad de gör är
  oförändrat.

- **„Detaljer" fälls ut, i stället för att hoppa.** Fönstret växte
  tidigare i ett hopp, och man var tvungen att söka efter vad som
  ändrats. Nu rör det sig dit.

- **Teckenstorlekar och avstånd följer samma mått i hela fönstret.**
  Rubriker var på två ställen olika stora, och likvärdiga rader stod
  olika långt isär. Synligt är det som ro, inte som en enskild
  ändring.

- **Anonymisera är nu förvalet.** Tidigare var pseudonymisering
  förinställt: samma personer fick samma nummer (`[NAME_1]`,
  `[NAME_2]`), samband förblev läsbara – rättsligt förblev det ändå
  **personuppgifter**. Den som inte ställer in något får nu det
  förfarande som tar bort uppgifterna ur GDPR: alla träffar av en typ
  heter likadant (`[NAME]`). Numreringen har förblivit ett val, den
  finns oförändrat kvar i samma fönster; befintliga inställningar
  förblir som de är. På kommandoraden ställer `--pseudonymisieren`
  (även `--mit-nummerierung`) tillbaka.

- **Anonymiserade platshållare går inte längre att ångra enskilt.** Den
  som anonymiserar får samma platshållare för varje person – och därmed
  finns inget enskilt ställe längre som hör till ett bestämt namn.
  Efterbearbetningsfönstret erbjöd ändå „Ångra ersättning": ett klick
  skulle ha satt in *ett* av värdena på *alla* ställen. Raderna är nu
  dämpade som vid maskerade uppgifter, klicket säger skälet, och ett för
  hand efterritat fynd får inget nummer längre som inte finns någonstans
  i det övriga dokumentet.

  Av samma skäl finns efter en anonymiserad körning inget „Översätt svar
  tillbaka" längre – tidigare skulle det ha satt ett främmande namn på
  varje persons ställe. Den som behöver denna slinga väljer
  „Pseudonymisera"; programmet säger nu det också, i stället för att
  hänvisa till en utgången tilldelning.

  På kommandoraden avbryter `--zuordnung` nu vid anonymisering, i
  stället för att skriva en fil som ingen återöversättning är – i
  fönstret var bocken sedan länge spärrad. Antingen `--pseudonymisieren`
  till eller utelämna `--zuordnung`; meddelandet säger det. Resultatet
  skapas därvid alls inte, så att ett skript inte står med halvfärdigt
  arbete.

- **Uppdateringskanalen står nu på „Stabil".** Utan eget val riktade sig
  kanalen tidigare efter vilket bygge den löpande versionen kom ifrån –
  den som en gång provat en testversion fick därefter varaktigt
  testversioner erbjudna. Ett kanalbyte är ett beslut och ska förbli
  ett; förvalet är därför „Stabil". Inställda kanaler rörs inte.

### Förbättrat

- **„Beschwerdevorgang" gäller inte längre som ortnamn.** I rubriken
  „Aktennotiz – Beschwerdevorgang 12 C 345/26" maskerade programmet
  ärendet med: språkmodellen tog det för en ort, och det oberoende av
  sammanhanget. Upptaget är inte det enskilda ordet, utan
  sammansättningens **grundord** – „vorgang" och „notiz" täcker
  därmed även affärs-, bokförings- och betalningsärende eller
  telefonanteckningen. Av trettio kontrollerade förvaltningsbegrepp
  utlöste tidigare tre ett falskt larm, nu inget längre; hittat blir
  fortfarande allt som står bredvid („Beschwerdevorgang: Bernd
  Meisinger" förlorar namnet, inte rubriken).

- **Anonymisering för nu bok igen – för efterkontrollen och
  protokollet.** I det anonymiserande driftläget kom programmet
  tidigare inte ihåg de hittade värdena. Två saker förblev därmed
  tysta: den dokumentövergripande konsekvensefterkontrollen (ett
  efternamn som senare dyker upp ensamt blev kvar) och listan över
  ersättningar i kontrollprotokollet. Så länge anonymisering var det
  mer sällsynta valet märktes det knappt – som förval skulle det ha
  blivit normalfallet. I dokumentet ändras inget: platshållaren förblir
  utan nummer.

- **„Inget personuppgiftsdatum" heter nu „ingen personuppgift".** I
  ångra-dialogen och i ansiktsvarningen stod det juridiska *datum* –
  singular av „data". Det lästes som en kalenderdag, i synnerhet som
  programmet på annat håll erbjuder „Ta bort datumangivelser också".
  Det heter nu överallt „uppgift", som i de fyra skälen ovanför i samma
  fönster.

- **Ursprungsraden står bara kvar i „Om"-fönstret.** „Made with ♥ in
  Austria" satt nedtill i huvudfönstret mitt i knapprad och lästes där
  som ytterligare en knapp. Den finns kvar i „Om"-fönstret – där den
  eftersöks.

- **Avlämningsytan har nu en synlig kant.** Dess streckade ram var så
  blek att den knappt syntes mot fönstret – det spelade ingen roll så
  länge ytan bara var en yta. Sedan den blev en knapp man kan tabba sig
  till är detta streck det enda som visar att den är ett
  kontrollelement; det har därför höjts till det värde normen kräver
  för det.

## 0.10.22-beta.1 – 15 augusti 2026

### Nytt

- **Stängs urklippsövervakningen av, är den verkligen av.** Övervakaren
  håller de senaste innehållen i arbetsminnet, så att originalet kan
  läggas tillbaka – tidigare även när övervakningen var avstängd. Nu
  glöms historiken vid avstängning. Det kostar återställningen efter
  avstängning, och exakt så är det menat: avstängt betyder avstängt.
- **Felloggen innehåller inte längre filsökvägar.** Den låg bara på din
  dator och skickades aldrig av sig själv – men den förde sökvägar i
  klartext, och ett filnamn avslöjar ofta mer än innehållet. Ur
  „…/Scheidung_Mueller_Vergleich.docx" blir det nu vid skrivning
  `<datei>.docx`; ändelsen blir kvar, eftersom den räknas vid
  felsökning. Detsamma gäller anteckningen efter en krasch.
- **Listan över ersättningar varnar nu i sig själv.** Den är den enda
  filen där dina originaluppgifter står i klartext, och den ligger
  bredvid resultatet – den som lämnar vidare en mapp lämnar den med. Nu
  står varningen som första rad **i** filen, utmatningsområdet nämner
  hela sökvägen i stället för bara filnamnet, och på kommandoraden nämns
  filen alls: där fick man tidigare inte ens veta att den skapats.
- **Anonymisera eller pseudonymisera är nu ett namngivet val.** På det
  stället stod tidigare en bock „Namnge samma namn likadant – KI:n kan
  då fortfarande se vem som är vem". Den beskrev nyttan och teg om
  följden: numrerade platshållare (`[NAME_1]`, `[NAME_2]`) är
  **pseudonymisering**, och pseudonymiserade uppgifter förblir
  personuppgifter – den som trodde sig ha anonymiserat med det hade fel.
  Nu står båda förfarandena bredvid varandra, vart och ett med sitt pris.
  Förvalet förblir Pseudonymisera, eftersom ett dokument som därefter
  fortfarande läses eller bearbetas av en KI behöver sina samband. Vid
  anonymisering är listan över ersättningar spärrad: den skulle göra
  resultatet spårbart igen. Handbok och FAQ förklarar skillnaden på alla
  18 språk; på kommandoraden heter brytaren nu också
  `--anonymisieren`.
- **Raden ovanför avlämningsytan säger nu vad som verkligen stämmer.**
  Den lovade „100 % lokal bearbetning – utan moln och konto,
  GDPR-vänligt". För dina dokument stämmer det, för programmet inte i
  denna generalitet: det söker uppdateringar, meddelar på begäran fel,
  laddar ner modeller och registrerar köpta arbetsplatser. Nu står där
  det snävare och hållbara påståendet: dina dokument lämnar inte
  datorn.
- **Vid resultatet står nu alltid att det ska kontrolleras.** Tidigare
  meddelade Maskuro efter en problemfri körning „12 uppgift(er)
  borttagna" i grönt och annars ingenting – det läses som en garanti
  att ha hittat allt. Hänvisningar visades bara när något konkret inte
  kunde kontrolleras (bilder, okända bilagor). Nu står under varje
  resultat omisskännligt att inte alla personuppgifter identifieras i
  varje fall, att kontrollen ligger hos användaren och att det saknade
  ska kompletteras för hand – i fönstret, i utmatningsområdet och på
  kommandoraden. Inget meddelandefönster att klicka bort: meningen står
  varaktigt där. Snabbguiden säger det nu med samma ordalydelse.
- **Efter en uppdatering står vid start vad som ändrats.** Tidigare gick
  en uppdatering tyst igenom och gick inte att skilja från en omstart.
  Nu visas en gång „Vad är nytt" – och den som hoppat över en version ser
  med den däremellan. Inte vid allra första starten: där leder
  fortfarande snabbguiden in.
- **Kinesiska och japanska hittar nu namn.** Tidigare hittade de
  **inga** – inte få, inga. Båda språkmodellerna saknade
  ordsegmenteringen, utan vilken en mening utan mellanslag gäller som ett
  enda ord; programmet gick tyst över till den flerspråkiga
  reservmodellen. Båda språken identifierar nu personer och orter som de
  övriga. Den japanska ordboken laddas därvid tillsammans med språket och
  ligger inte i programmet – den ensam skulle vara gott och väl 200 MB,
  som annars var och en skulle burit med sig.
- **Rumänien går att välja som land.** Det saknades tidigare helt. Med
  det identifieras rumänska adresser („Strada Victoriei 30"), postnummer
  med ort („010061 București") och Cod Numeric Personal – det senare bara
  med stämmande kontrollsiffra, så att inte varje trettonsiffrigt tal på
  en faktura markeras. Fram till dess blev i rumänska dokument postnumret
  läsbart kvar bredvid det maskerade ortnamnet.
- **„Rastrera sida" i editorn.** Går text inte att ta bort ur ett PDF –
  det förekommer vid filer från främmande skapare –, ersätts sidan nu på
  begäran med sin avbild: texten är därmed oåterkalleligt borta, sidan
  förblir läsbar och sökbar. Varningen som meddelar fallet erbjuder
  steget direkt som en knapp; via „Verktyg → Rastrera sida" går det
  också av sig själv. Ångra hämtar tillbaka sidan.
- **Gränssnittet finns nu även på kroatiska, grekiska, litauiska,
  slovenska, japanska och koreanska.** Därmed är det arton språk. Handbok,
  FAQ och rättsliga texter finns fullständigt med på alla sex. Beteckningarna i det rensade
  dokumentet följer därvid gränssnittet – ur `[NAME_1]` blir `[IME_1]`,
  `[ΟΝΟΜΑ_1]`, `[VARDAS_1]" eller `[氏名_1]`. **Vid grekiska, japanska
  och koreanska står beteckningarna latinskt** – `[ONOMA_1]`,
  `[SHIMEI_1]`, `[IREUM_1]`. Gränssnittet förblir i sin egen skrift; bara
  det som skrivs in i dokumentet är latinskt. Anledningen är
  PDF-teckenuppsättningen: där hade grekiska och japanska beteckningar
  tidigare kommit fram som `[??_1]`, och därmed gick namn inte längre att
  skilja från ort.
- **Nio länder tillkommer, och sju befintliga blir fullständiga.** Nytt
  identifierade blir ID-, skatte- och socialförsäkringsnummer samt
  adresser för **Kroatien, Slovenien, Grekland, Litauen, Nordmakedonien,
  Ryssland, Ukraina, Kina och Japan**. Vid de befintliga länderna har
  luckor stängts som vägde tyngre: för **Nederländerna** och
  **Portugal** fanns tidigare inget personnummer alls – den nederländska
  BSN och den portugisiska NIF identifierades inte, trots att de står på
  praktiskt taget varje handling från dessa länder. Polen får
  skattenumret NIP, Danmark, Norge och Finland sina adresser, Kanada sitt
  postnummer. Därmed är det **35 länder**.

### Borttaget

- **För Linux finns tills vidare inget paket längre.** Källkoden körs
  där, men tre saker som denna anvisning lovar saknas under Linux:
  automatisk start, globala tangentbordskortkommandon och – beroende på
  arbetsmiljö – ikonen i fältet. Att leverera ett paket som kan mindre
  än vad som beskrivs vore fel väg. Windows och macOS är oberörda.

### Förbättrat

- **Diarienummer hittas nu på alla språk.** „Aktenzeichen 12/2026-AB" togs
  bort, „File reference 12/2026-AB" eller „Sygnatura 12/2026-AB" blev
  kvar: fältorden som Maskuro identifierar ett sådant nummer på fanns
  bara på tyska. Nu känner det till motsvarigheterna på tolv språk – och
  som förut ersätts bara numret, beteckningen framför blir kvar, så att
  det i resultatet syns vad som togs bort där.
- **Maskuro belägger i vila cirka ett halvt gigabyte mindre.** Vid start
  laddades tidigare även tilläggsmodellen för den noggrannare
  igenkänningen, så att den första rensningen inte skulle vänta på den.
  Uppmätt kostade det 648 MB arbetsminne och sparade 1,9 sekunder – och
  det kostade det även om man bara öppnade fönstret och stängde det
  igen. Modellen laddas nu första gången den behövs; statusraden
  meddelar det. Språkmodellen laddas fortfarande vid start – det behöver
  urklippsövervakningen omedelbart.
- **Avlämningsytan går nu att använda även utan mus.** „Dra filer hit"
  var en yta som reagerade på klick – med tangentbordet kom man inte dit,
  och en skärmläsare läste upp den som en ram med text i, inte som det
  den är. Den är nu en knapp: tabbtangenten hoppar till den,
  mellanslags- och enter-tangenten öppnar filvalet, och den som hoppat
  dit ser det på kanten. Via menyn „Arkiv → Välj filer" gick det redan
  tidigare, men det var tvunget att man visste det.
- **Namnet på den rensade filen läses nu också upp.** I fillistan står
  det som en andra, mindre rad under originalet – men det var bara
  ritat, och en skärmläsare nämnde bara originalet. Just den raden är
  byggd mot missuppfattningen att en körning var verkningslös eftersom
  det oberörda originalet ligger i mappen. Raden lyder nu upplästs
  „rechnung.pdf, resultat: rechnung_bereinigt.pdf".
- **Kontrollelement utan text säger nu vad de är till för.**
  Symbolknapparna i fillistan, ritningsknapparna i
  efterbearbetningsfönstret och alla val- och inmatningsfält var namnlösa
  för skärmläsare – de meddelades som „Knapp" och „Kombinationsruta", utan
  om vad. Knapparna på en rad nämner därvid filen med: i en lista med
  tjugo poster hörde man annars samma mening tjugo gånger.
- **Den som styr med tangentbordet ser åter var hen befinner sig.**
  „Rensa"-knappen och symbolknapparna i fillistan är färgade, och därmed
  upphörde ramen som systemet annars lägger runt det uppnådda
  kontrollelementet – vid tabbning hoppade blicken ut i tomma intet. Båda
  har nu en egen ram så snart de är i tur. Knapparna ändrar därvid inte
  sin storlek.
- **Sju textfärger var för bleka, i båda utseendena.** Uppmätta efter
  den gängse normen (WCAG 2.1) låg de bleka hänvisningsraderna,
  bitexterna på avlämningszonen, punkterna i anvisningen och i den
  mörka bilden dessutom det blå och det röda under gränsen på 4,5:1 –
  läsbara i gott ljus och med bra syn, annars inte. Alla är höjda;
  gradueringen består, texterna läses fortfarande som bitexter. Tre
  ytterligare – färgerna i vilka varningar och framgång meddelas – höll
  gränsen bara knappt och drogs med: den som inte läser dem läser inte
  beskedet om något gick fel. Synligt förändrat blev därvid bara
  „Rensa"-knappen i den mörka bilden: den bär nu mörk i stället för vit
  text, liksom accentknapparna i Windows 11.
- **Varje rad i fillistan har nu sitt eget kryss.** Tidigare var man
  tvungen att först markera raden och sedan klicka på „Ta bort" – två
  steg för en liten sak. Krysset står till höger i raden och behöver ett
  klick. Knappen „Ta bort" under har därmed utgått; den som vill bli av
  med flera rader på en gång markerar dem och tar posten i kontextmenyn,
  som också säger hur många det är. „Ta bort alla" finns kvar. Ur listan
  tas alltid bara raden – aldrig en fil på disken.
- **Före KI-kontrollen står nu om denna dator lämpar sig för det.**
  Tidigare stod i fönstret bara hur stor modellen är. Den som slog på
  det på en svag dator märkte först vid första dokumentet att det tar
  mycket lång tid – efter 5,4 GB nedladdning. Nu nämner fönstret **innan**
  arbetsminne och ledigt utrymme och säger vad det betyder; **efteråt**
  mäts hastigheten och nämns i den storlek det gäller: „Ett tiosidigt
  dokument tar på denna dator ungefär 12 minuter." Är det för
  långsamt, avråder programmet och erbjuder att stänga av nivån igen –
  det förbjuder ingenting.
- **Hastighetsmätningen körs nu på varje dator.** Tidigare kom den bara
  om grafikaccelerationen dessutom ställdes in – den finns bara under
  Windows. På alla andra datorer uppskattade programmet därför
  varaktigheten utifrån en främmande dator, och just där det är
  långsamt låg uppskattningen fel.
- **Turkiska adresser hittas nu även i skanningen.** På ett inskannat
  brevhuvud förblev „34710 İstanbul" läsbart, medan samma uppgift i
  texten bredvid försvann: textigenkänningen läser den turkiska İ utan
  sin prick, och mönstret väntade sig en versal. Detsamma gällde
  „Bağdat Caddesi".
- **Spanska adresser utan eget gatunamn hittas.** „Gran Vía 5" blev kvar,
  eftersom mönstret bakom gatutypen väntade ett namnord till – vid
  „Calle Mayor" finns ett, vid „Gran Vía" är typen själv redan namnet.
  Detsamma gäller nu „La Rambla" och „Castellana".
- **I fönstret „Om detta program" står nu en transparenshänvisning** om
  att programmet utvecklats med stöd av artificiell intelligens. Den
  gäller programmets tillkomst, inte dess arbetssätt: rensning sker
  fortfarande uteslutande på den egna datorn.
- **„Hantera språk" visar nu de användbara språken först.** För hälften
  av de 48 språken finns ingen egen språkmodell; där identifierar en
  flerspråkig reservmodell namn bara svagt, i vissa skrifter inte alls.
  Bredvid varandra i en lista såg alla likvärdiga ut. Förvalet visar
  därför bara språk med egen modell – via „Visade" går de övriga att
  visa när som helst, med en mening om vad de kan och inte. Inget
  försvinner, och den som ställt in ett begränsat språk behåller det.
- **Frågan om ett saknat språk nämner nu utvägen.** Identifieras ett
  språk som ännu inte ställts in, erbjöd programmet tidigare bara
  „Ladda" eller „Fortsätt utan". Igenkänningen kan dock ha fel – vid
  korta formulär och listor med lite löptext avgör få ord. I fönstret
  står därför nu att man kan avbryta och välja rätt språk för hand, i
  stället för att använda „Identifiera automatiskt". Det sparar i
  tveksamma fall en nedladdning på flera hundra megabyte för ett språk
  som inte alls behövs.
- **Platshållarbeteckningar talar nu gränssnittsspråket.** „[NAME_1]",
  „[ADRESSE_2]" med flera stod tidigare alltid på tyska, oavsett vilket
  språk som ställts in eller på vilket språk dokumentet är skrivet. Nu
  följer de gränssnittsspråket – på engelska alltså „[NAME_1]",
  „[ADDRESS_2]". Inte dokumentspråket: det är vid „identifiera
  automatiskt" gissat och ibland fel; gränssnittsspråket är det aldrig.
- **Färre återfrågor vid efterbearbetning.** Vart resultatet sparas står
  nu varaktigt nere i fältet („→ vertrag_bereinigt.pdf", i tooltipen
  mappen) – ett klick på det väljer en annan plats, utan att genast
  spara. Återfrågan vid första sparandet utgår därmed. Frågan „redan
  bearbetad – börja om?" kan sparas för sessionen, och två
  hänvisningsfönster som bara gav en upplysning står nu i statusraden.
  Kvar är frågorna som förhindrar en oåterkallelig skada: den osparade
  arbetet vid stängning och varningen om icke borttagen text.
- **Resultatet säger nu var själva skanningen inte var läsbar.** På ett
  inskannat dokument läser enhetens textigenkänning inte allt rätt – ur
  „Solarstraße 9" blir det då till exempel „Solaret^aß« B". Vad som
  lästs fel på så vis kan ingen kontroll längre hitta: det ser för varje
  sökmönster ut som bokstavssallad. Programmet kan inte ändra på det,
  men namnger nu sådana ställen med sidnummer – oftast döljer sig där
  stämplar, brevhuvuden eller handskrivna tillägg. En hänvisning, ingen
  varning: vid ett satt dokument uteblir den.
- **Fillistan visar nu vad resultatet heter.** Under filnamnet står efter
  körningen namnet på den rensade filen („→ vertrag_bereinigt.pdf").
  Tidigare stod det bara i loggen bakom „Detaljer", och den som såg
  efter i mappen hittade det oberörda originalet. Källans namn blir kvar
  – annars skulle det inte längre gå att se vilken fil ett resultat
  kommer från.
- **Knapparna på en färdig rad är större och tydligare.** Visa,
  Efterbearbeta och „Visa i mapp" var platta symboler utan yta och gick
  under i listan – trots att de efter körningen är det enda man
  fortfarande klickar på.

### Rättat

- **På ett gränssnitt på ett annat språk kringgicks egna regler för
  maskering, maska och hashning tyst.** Den som fastställt att namn
  skulle maskeras i stället för ersättas fick dem ändå ersatta – så
  snart programmet inte kördes på tyska eller engelska. Inställningen
  stod där, den hade bara ingen effekt, och i resultatet syntes ingen
  skillnad. Berörda var nio av de tolv gränssnittsspråken.
- **Inställningen „Språk för beteckningarna" hade ingen effekt utanför
  tyska och engelska.** „Tyska" och „Engelska" gick att välja, men i
  dokumentet stod fortfarande gränssnittsspråket. Nu har alla tre
  möjligheter effekt; förinställningen „som gränssnittet" levererar
  oförändrat samma sak som förut.
- **I korta textutdrag blev namn kvar – till exempel i ett kopierat
  mejlcitat.** Den som rensade ett utdrag via urklipp fick där ofta bara
  e-postadressen maskerad, namnet under den inte. Avgörande var det rena
  radantalet: från sex rader identifierade programmet utdraget som en
  förteckning och hittade namnen, under det inte – ett kopierat
  mejlcitat har fem. En valfri extra rad, till exempel ett ämne, vände
  resultatet. Nu räcker fyra rader, och i mätningen försvinner alla
  kontrollerade namn i stället för en tredjedel. Detta påverkar inte
  längre dokument eller löptext.
- **Grafikaccelerationen för KI-kontrollen stängdes tidigare av igen så
  snart man ställt in den.** Efter installationen mäter programmet om
  grafiken på denna dator verkligen är snabbare än processorn – denna
  mätning misslyckades dock alltid utan att säga det, och resultatet
  „båda lika snabba" avgjorde till förmån för processorn. Den som laddat
  ned de 65 MB fick därefter mindre än förut. Mätningen körs nu; misslyckas
  den, ändrar den inget längre.
- **Tidsuppskattningen räknade på varje dator med en främmande
  hastighet.** Den bygger på samma mätning; så länge den inte kördes,
  gällde utvecklingsdatorns värde. „Ungefär två minuter" kunde därmed
  betyda en halvtimme på en långsam dator.
- **KI-nivån arbetar med en ny, betydligt bättre språkmodell**
  (Qwen3.5-9B i stället för Qwen3-4B) och är inte längre begränsad till
  tyska och engelska, utan arbetar på tolv språk. Uppmätt över
  kontrollkorpuset: lika många hittade uppgifter som utan nivån, men
  mindre än hälften så många överflödiga maskeringar (75 → 31). Modellen
  är större (5,4 i stället för 2,4 GB) och behöver ungefär dubbelt så
  lång beräkningstid; vid påslagning laddas den en gång, den gamla tas
  därvid bort.
- **Adresser på franska, italienska, spanska, portugisiska, polska,
  turkiska och svenska tas nu bort fullständigt.** Tidigare försvann där
  bara gat- och ortnamnet – husnummer och postnummer blev läsbara kvar
  („[ORT_1] 28, 28013 [ORT_2]"). För dessa språk fanns inga egna
  adressmönster; de är nu kompletterade.
- **Grekiska och koreanska hittade inga namn alls.** Vid grekiska berodde
  det på reservmodellen – med den egna modellen, som nu går att ladda,
  identifieras namn och orter rent. Vid koreanska berodde det på
  programmet: det förutsatte att ett namn börjar med en versal, och
  hangul har inga versaler. Berörda var främst korta enheter –
  tabellceller, formulärfält, listposter.
- **En språkmodell som inte gick att ladda avbröt rensningen.** I
  stället för ett felmeddelande hoppar nu den flerspråkiga modellen in,
  och resultatet påpekar att den svagare igenkänningen använts. Berör
  för närvarande kinesiska och japanska, vars modeller behöver en
  ordavdelning som ännu inte medföljer programmet.
- **Ett språk med egen modell gällde som installerat så snart något
  annat var laddat.** Den som till exempel ställde in turkiska fick
  därmed den flerspråkiga reservmodellen – och kinesiska, japanska,
  koreanska eller grekiska stod därefter med satt bock och „0 MB" i
  listan, trots att deras egen modell saknades. De gick därigenom
  aldrig att ladda ned och arbetade varaktigt med den svagare reserven.
  Nu visar listan det faktiska läget tillsammans med laddningsstorleken.
- **En utfallen igenkänningsnivå teg.** Var „Utökad igenkänning" eller
  „Maximal igenkänning (KI)" påslagen, men modellen gick inte att köra,
  fortsatte programmet arbeta utan nivån – utan ett ord om det.
  Resultatet såg ut som vilket annat som helst, och brytaren stod
  fortfarande på „på": man höll alltså grundnivåns resultat för det
  bästa som gick att få. Resultatet säger det nu och nämner båda – vad
  som inte kontrollerades och hur modellen går att ladda på nytt. Fallet
  är inte sällsynt: på vissa datorer misslyckas KI-nivån vid laddning
  när grafikaccelerationen saknas.
- **Ett fel vid laddning av tilläggsmodellen avbröt hela rensningen.**
  Vid „Utökad igenkänning" var bara utvärderingen av modellen säkrad,
  inte dess inläsning – och just där går det fel om filen är skadad
  eller inte passar datorn. I stället för ett felmeddelande finns nu ett
  resultat från grundnivån tillsammans med en hänvisning.
- **Ett språk gick inte längre att ta bort – och därmed inte heller att
  ladda på nytt.** Den som i „Hantera språk" tog bort bocken och
  övertog ändringen läste „Tyska borttaget", men såg bocken genast satt
  igen. Orsaken var övertagandet från programmappen: vid en installation
  för alla användare ligger språkmodellerna skrivskyddade i
  programmappen, och programmet hämtar saknade därifrån i stället för
  att ladda ned hundratals megabyte på nytt. Detta övertagande kördes
  vid varje åtkomst – och kopierade det just borttagna språket tillbaka
  i samma andetag. Det sker nu bara en gång; nedladdade språkmodeller
  bevaras därvid. Dessutom kontrollerar programmet efter borttagning:
  det som inte gick att ta bort rapporteras nu som ett misslyckande i
  stället för „borttaget".
- **Vid en installation för alla användare gick nedladdat inte att
  lagra.** Den som installerar programmet för alla användare har det i
  „Program", och dit får inget skrivas utan administratörsrättigheter.
  För språkmodellerna var för det länge sedan en alternativ plats
  avsedd, för annat inte:
  - **Sidvisningskomponenten** packades upp i programmappen efter 290 MB
    nedladdning och misslyckades där – utan att nämna en orsak. Den
    ligger nu hos språkmodellerna, där den enligt avsikten alltid borde
    ligga.
  - **Grafikaccelerationen** kan inte gå en alternativ väg: den byter ut
    bibliotek i själva programmet. I stället för att först ladda och
    sedan misslyckas ordlöst, säger programmet nu i förväg att det inte
    går här och vad det betyder – den maximala igenkänningen fortsätter
    arbeta, bara via processorn.
  - Ett medföljande **språk för textigenkänningen** gick inte att ta
    bort: det återställdes genast från programmappen. Samma orsak som
    vid språkmodellerna, samma åtgärd.
  - Vid borttagning av ett språk kunde **språkdata från en främmande
    Tesseract-installation** raderas. Bara den egna mappen berörs nu.
  - Den alternativa platsen gällde tidigare bara under Windows. Ett
    Linux-arkiv till `/opt` hade samma nöd utan samma utväg.
- **Vid efterbearbetning försvann en hel rad, trots att bara ett ord var
  inramat.** Den som i en redan rensad fil maskerade en platshållare
  förlorade raden den stod i: ur „Sehr geehrte Frau Doktor [NAME_1]"
  blev inget kvar – och meddelandet sa till det „ett ord borttaget ur
  dokumentet". Berörd var varje fil som redan en gång körts genom
  programmet, alltså just det fall som efterbearbetningen finns till
  för. Den övriga texten blir nu kvar, på oförändrad plats.
- **„EMPLOYEES" ovanför en namnlista maskerades själv.** Samma fall som
  „MITARBEITER" i 0.10.19, bara på engelska – där hade det stannat kvar.
  I versaler saknar språkmodellen kännetecknet, och rubriken står
  ovanför enbart riktiga namn. Namnen under den identifieras
  fortfarande. Inte upptaget blev „staff": det är ett belagt efternamn,
  och posten skulle ta med sig varje „John Staff" – samma avvägning som
  då vid „Arbeiter".
- **Bolagsformen ersattes en andra gång.** På ett inskannat brevhuvud
  läste språkmodellen „GmbH", adressen och postnumret som **en** ort.
  Adress och postnummer skar sig därefter ut sina delar, och kvar blev
  bolagsformen som en egen träff: i resultatet stod „[ORT_1] [ORT_2]",
  där „[ORT_1] GmbH" avsågs. Företagsnamnet ersätts fortfarande – bara
  det nakna tillägget blir nu kvar, och resultatet läses som ett
  brevhuvud i stället för en luckövning.
- **En tillskuren träff kontrollerades inte igen.** Orsaken till fallet
  ovanför, och den räcker längre: filtren mot gissade träffar kördes på
  det som identifierarna **rapporterar** – inte på det som blir kvar
  efter överlappningsupplösningen. Skärs en lång träff av vid en
  starkare identifierare, är fragmentet en annan text än den bedömda,
  och ingen tittade på den igen. Nu görs det.
- **„Du använder den senaste versionen" – trots att det inte alls gick
  att kontrollera.** Den som ställt in uppdateringskanalen på
  „Förhandsvisning (beta)" eller „Stabil – rekommenderad" fick detta
  besked, trots att det på dessa kanaler hittills inte alls kommit
  något. Nu säger programmet exakt det – och föreslår att välja en
  annan kanal i inställningarna.
- **Att stänga fönstret under laddningen fick en tråd att krascha.** Den
  som startade Maskuro och genast stängde fönstret igen medan
  språkmodellerna fortfarande laddades fick i loggen en felrapport:
  laddningen anmälde sig hos ett fönster som inte längre fanns. Synliga
  följder hade det inga, men i loggen stod en krasch, där bara någon
  varit snabbare än programmet.
- **Resultatet ses nu på, inte bara läses av.** Tidigare gällde en sida
  som ren om värdet inte längre stod i texten. På en skanning är det
  inget bevis – där är den synliga texten en bild. Till sist ses det
  därför efter om ytan i resultatet verkligen är maskerad; står där
  fortfarande ljust papper, säger rapporten det uttryckligen, i stället
  för att meddela „ersatt".
- **En ersatt uppgift blev kvar i bilden.** Stod värdet i en bild – ett
  inskannat brevhuvud, en stämpel, en hel skannad sida –, togs det
  visserligen bort ur dokumenttexten, men var fortfarande **synligt**:
  det människan läser är där bildpunkter. Rapporten meddelade ändå
  „ersatt". Nu maskeras ytan i bilden, oavsett vilken strategi som
  ställts in, och platshållaren står ljus på denna grund – fult, men
  ärligt, och tilldelningen bevaras. Går ett bildformat inte att
  bearbeta, säger resultatet nu det uttryckligen, i stället för att se
  rent ut.
- **På en skanning saknades platshållaren helt.** Textskiktet på en
  skannad sida ritas osynligt, och en platshållare som satts in i det
  ärvde detta: satt, men inte synlig. På fyndstället stod därefter
  ingenting.
- **En textigenkänning som inte alls kunde köras gällde som godkänd.**
  Saknades språkfilen eller kraschade igenkänningsmotorn, meddelade
  rapporten „Bild(er) … kontrollerades via textigenkänning
  (0 fyndställe(n))" – alltså en kontroll som aldrig ägde rum. Vid en
  skanning är det den enda kontrollen alls: ett avtal med läsbar adress
  i sidbilden gällde därmed som färdigt. Nu säger rapporten att inget
  kontrollerades, och varför.
- **Språkfilen söktes i fel mapp.** Låg det i den egna språkkatalogen
  andra språk än dokumentets, fick igenkänningsmotorn just denna katalog
  förelagd och misslyckades – trots att det passande språket låg
  bredvid. Sökt blir nu **språket**, inte mappen.
- **Varningen om icke borttagen text rådde till något som inte finns.**
  Den hänvisade till „Maskera som PDF" – men det skapar en PDF-vy av
  *kontors*filer och finns inte alls tillgängligt vid ett PDF-dokument.
  Den som ville följa varningen sökte förgäves. Nu står där knappen som
  sköter saken.
- **I editorn hamnade streck och platshållare bredvid det markerade
  stället.** Berört var varje PDF-fil där en rad slutar med ett
  avstavningsstreck och ordet fortsätter på nästa – vid skanningar
  märks det särskilt, eftersom avtalstexter genomgående sätts avstavade.
  De båda radhalvorna gällde som *ett* ord som sträckte sig tvärs över
  satsspegeln, och varje ram i dess närhet övertog denna utsträckning.
  Själva igenkänningen ändras inte av detta: mätkorpuset ger samma
  resultat som tidigare.
- **Editorn varnade att texten „fortfarande stod i dokumentet", trots att
  den var borttagen.** Förekom samma ord flera gånger på en sida – i
  avtal regeln – meddelade självkontrollen efter varje ingrepp ett
  misslyckande. Den räknar nu förekomsterna, i stället för att bara se
  efter om ordet fortfarande står någonstans. Vid ett verkligt
  misslyckande varnar den oförändrat.
- **Resultatfilen hette på varje språk „_bereinigt".** Meningen var
  alltid att namntillägget skulle följa gränssnittsspråket – på engelska
  gjorde det det också („_cleaned"), på de övriga sexton språken inte.
  Den som använde programmet på finska fick „asiakirja_bereinigt.pdf".
  Nu heter filen „asiakirja_puhdistettu.pdf", på japanska
  „書類_除去済み.pdf" och så vidare – vardera med det ord som samma
  gränssnitt använder i sitt färdigmeddelande. Den som ställt in ett
  eget tillägg behåller det.
- **„Hantera språk" texten var alltid tysk.** I listan över de 48
  dokumentspråken stod de tyska namnen, oavsett vilket gränssnitt som
  ställts in: en finsk användare läste „Chinesisch". Nu står där namnet
  på sitt eget språk och därefter egennamnet – „Kiina (中文)". Egennamnet
  är avsiktligt: den som känner igen språket på dess eget namn hittar
  det även när det finska ordet inte säger hen något.

## 0.10.19 – 12 augusti 2026

### Förbättrat

- **Posten i kontextmenyn talar nu ditt språk.** Tidigare stod den tyska
  ordalydelsen där på varje system – även på en engelsk Windows. Nu följer
  den det inställda gränssnittsspråket, och den som byter språk får posten
  omedelbart omdöpt, utan att installera om. (Windows; på macOS och Linux
  är menynamnet samtidigt ett filnamn – det kommer senare.)
- **Redigeraren kommer ihåg i vilken vy du senast arbetade.** Den som
  använder sidvisningen får den automatiskt vid nästa dokument – utan att
  slå på den varje gång. Den som aldrig använt den märker ingenting: den
  återställs bara om den byggsten som behövs redan är laddad, aldrig laddas
  något ned för det.

### Rättat

- **„MITARBEITER" ovanför en namnlista maskerades själv.** I
  personalförteckningar och organisationsscheman försvann rubriken som en
  påstådd namn – den står där ovanför enbart riktiga namn, och med versaler
  saknar språkmodellen sitt kännetecken. Namnen därunder hittas fortfarande.
- **Kvantitetsangivelser togs för adresser.** I fakturor, följesedlar och
  lagerlistor försvann uppgifter som „3390 Protokoll", „1030 Betrag" eller
  „3390 Lager" som ett påstått postnummer med ort – fyra siffror ser ut som
  ett österrikiskt postnummer i vilken mängd som helst. Står ett ord bakom
  siffran som programmet känner som sakord, avdelning, verksamhet eller
  fältbeteckning, blir det nu kvar. Riktiga ortsangivelser är opåverkade,
  även sådana som samtidigt är ett sådant ord („4692 Ort"). Olöst förblir
  därmed fallet att ett helt vanligt ord står bakom siffran („3390 Regal") –
  det kräver en postnummerförteckning.
- **Hjälpen nämnde en menypost som inte finns.** Anvisningen, bilden och
  meddelandet i slutet av installationen talade om „Rensa dokument för
  AI"; posten i kontextmenyn heter dock „Ta bort personuppgifter". Den som
  följde hjälpen sökte förgäves. Alla tre ställen nämner nu menyposten så
  som den verkligen heter.
- **„Starta med systemet" gick inte att stänga av.** Den som under
  installationen kryssat i „Starta med Windows" såg ändå en tom bock i
  inställningarna – och värre: att slå av och på i programmet var
  verkningslöst, programmet fortsatte starta med Windows. Orsaken var två
  platser där Windows letar efter startprogram; programmet kände bara till
  en av dem. Nu räknas båda, brytaren visar det verkliga tillståndet och
  verkar i båda riktningarna. Även beaktat: den som stänger av posten i
  Aktivitetshanteraren ser det nu i programmet – och den som slår på den
  igen där upphäver därmed avstängningen.
- **Rubriker ovanför namnlistor maskerades.** „TEILNEHMERLISTE
  WERKSTATTGESPRÄCH" eller „MITARBEITERÜBERSICHT INNENDIENST" ovanför en
  lista med personer försvann som ett påstått namn. Med versaler saknar
  språkmodellen sitt bästa kännetecken, och på tyska skrivs varje substantiv
  med stor bokstav – „Teilnehmerliste Werkstattgespräch" ser då ut som
  „Anna Huber". Sammansättningar på `-liste`, `-dienst`, `-gespräch`,
  `-sitzung` och `-besprechung` blir nu kvar. Grundorden ensamma gäller
  fortsatt som namn: *Liste* och *Dienst* är belagda efternamn,
  *Teilnehmerliste* är inget.
- **Stående uppgifter fick en oläslig platshållare.** Diarienummer i
  sidmarginalen, handläggarförkortningar bredvid bindningskanten, stående
  tabellhuvuden: sådana uppgifter hittades och togs bort, men platshållaren
  kom ut tvärs över texten, hoppressad till en till två punkter och ibland
  utanför pappersranden. Nu följer den texten – lodrätt, i läsbar storlek
  och i samma riktning som uppgiften stod. Detsamma gällde sidor som
  roterats i efterhand (vågrätt skriven text med inregistrerad
  sidrotation, som vissa utmatningsprogram levererar); även där står
  platshållaren nu så som man ser sidan. „Sehr geehrte Frau Doktor
  Anneliese Berger" gav bara „Anneliese" som namn – „Berger" blev kvar i
  dokumentet. Detsamma drabbade varje namn med mellannamn („Frau Anna Maria
  Berger"). Orsaken var regeln för namnet bakom en tilltalsform: den hade
  två ordplatser, och en titel eller ett mellannamn förbrukade den första.
  Med „Dr." märktes det aldrig – punkten bryter regeln, och språkmodellen
  fångade hela namnet. Nu hoppas titlar över utan att kosta en plats, och
  namnet får bestå av tre delar. En roll **bakom** namnet fungerar
  fortfarande inte: „Frau Anna Huber Geschäftsführerin" ersätter namnet,
  inte rollen.
