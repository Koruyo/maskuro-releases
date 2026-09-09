# Ändringar

Vad som ändras från version till version – beskrivet ur programmets
synvinkel, inte ur dess inre. Den som vill veta *vad* det är byggt av hittar
det i [LIZENZEN.md](LIZENZEN.md); här står vad som ändras för arbetet med det.

Numreringen följer den vanliga räknesättet: den **första** siffran ändras när
något inte längre fungerar som förut, den **andra** vid nya funktioner, den
**tredje** vid felrättningar.

---

## 0.10.52-alpha.20260903 – 3 september 2026

- En körning med fler än fyra filer stannar inte längre efter svar i flera
  förhandsgranskningsfönster. Ytterligare dokument fortsätter att förberedas
  i bakgrunden; efter ett svar slutförs nu alltid den tillhörande filen och
  nästa plats i kön frigörs.
- Matchningen av korta företagsbeteckningar i PDF-filer begränsas nu till text
  som har identifierats i bilder. I vanlig sidtext leder en lång, flerradig
  modellträff därför inte längre till att ett identiskt fristående ord på ett
  annat ställe också maskeras.

## 0.10.51-alpha.20260903 – 3 september 2026

- Ändringslistan visas nu på det egna språket – på maskuro.com/neuigkeiten
  och i programmet under „Ändringar" samt i „Vad är nytt" efter en
  uppdatering. Tidigare stod där i alla arton språkversioner tysk text under
  en översatt rubrik. Där en översättning ännu saknas står den aktuella
  versionen kvar på tyska i stället för att försvinna; listan över versioner
  är densamma överallt.

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
