Mikä muuttuu julkaisusta toiseen – kuvattuna sovelluksen käyttäjän
näkökulmasta, ei sen sisäisen rakenteen. Jos haluat tietää, *mistä* se on
rakennettu, se löytyy tiedostosta
[LIZENZEN.md](LIZENZEN.md); täällä kerrotaan, mikä muuttuu työskentelyssä
sen kanssa.

Numerointi noudattaa tavanomaista käytäntöä: **ensimmäinen** luku muuttuu,
kun jokin ei enää toimi kuten ennen, **toinen** uusien ominaisuuksien
myötä, **kolmas** virheenkorjausten myötä.

## 0.10.50-alpha.20260903 – 3. syyskuuta 2026

- Toistuvat yritysmerkit PDF:issä puhdistetaan nyt yhtenäisesti, myös
  silloin, kun tekstintunnistus lukee tekstin sivulla eri tavalla tai
  jättää pyöreän tunnuksen kokonaan pois. Esikatselussa tehty
  nimenomainen poisvalinta pysyy tällöin sitovana eikä mikään myöhempi
  jälkikäynti voi kumota sitä.
- Rahayksiköttömät hinnat skannatuissa taulukoissa peitetään nyt
  kokonaan myös silloin, kun taulukon otsikko ja arvot ovat eri,
  päällekkäisissä PDF-kuvissa. Määrät, tunnit, painot ja prosentit
  jäävät paikoilleen; kaukana toisistaan olevia lukuja ei enää
  vahingossa yhdistetä yhdeksi summaksi.
- Allekirjoitushaku tunnistaa nyt myös todistetut heikot siniset
  kirjoitukset ja kapeat punaiset kuittauslyhenteet. Pisteytetyt
  kaaviot, mittauskäyrät, leimat, logot ja leveät punaiset
  muokkausmerkinnät jäävät tämän suppean jälkikäynnin ulkopuolelle.
- Peitto käännetyissä, peilatuissa, vinoutetuissa tai rajatuissa
  PDF-kuvissa osuu nyt todelliseen kuvamonikulmioon. Samalla teknisiä
  rooleja suoriteriveillä, ajoneuvo- ja rengasasiatietoja sekä
  teknistä „kompensaatiota” rajataan tarkemmin virheosumia vastaan;
  nimenomaisesti merkityt yhteystietoroolit ja puhelinnumerot pysyvät
  suojattuina.
- Silmämääräinen tarkistus ennen PDF:n tallentamista ei enää jäädytä
  ikkunaa: suurissa asiakirjoissa, joissa on paljon löytökohtia, ikkuna
  seisoi aiemmin useita sekunteja ilman palautetta; nyt huomautus
  näyttää tarkistuksen olevan käynnissä, ja ikkuna piirtyy edelleen.
- Arvon palauttaminen kuvasta jälkikäsittely-editorissa lukee nyt
  jokaisen alkuperäiskuvan vain kerran tekstintunnistuksella; aiemmin se
  ajettiin uudelleen samoille kuville jokaisen lisäpalautuksen yhteydessä.
- Korkean tason ja allekirjoitusmallin jälkilataus tarvitsee tuskin
  enää lainkaan muistia: 596 megatavun paketti pidettiin aiemmin
  kokonaan muistissa, tarkistettiin ja purettiin siellä – yli
  gigatavun huippu käynnissä olevassa ohjelmassa, 8 Gt:n koneilla
  hetki, jolloin kaikki alkoi takkuilla. Nyt se virtaa lohkoittain
  levylle ja tarkistetaan ja puretaan siellä.
- Haku jälkikäsittely-editorissa ei enää jäädytä suuria PDF:iä:
  hakukentän ensimmäinen kirjain luki aiemmin kaikki sivut kerralla –
  200 sivun tapauksessa ikkuna seisoi kaksi sekuntia, ja jokaisen
  peiton jälkeen uudelleen. Sivut luetaan nyt paloittain; siihen asti
  laskurissa lukee „Luetaan …”, tulos on sama.
- Rasteroidut PDF-sivut – tekstintunnistuksen jälkeen tai kun tekstiä
  ei voitu poistaa siististi – tallennetaan nyt selvästi pienempinä
  ilman kuvanlaatuhäviötä: aina JPEG:nä tallentamisen sijaan jokainen
  sivu koodataan myös häviöttömästi, ja pienempi versio päätyy
  tiedostoon. Puhdistettu skannaus pienenee siten 248:sta 48
  kilotavuun, harjoitusasiakirja tekstintunnistuksella 913:sta 702
  kilotavuun; teksti pysyy terävänä.
- Jälkiladatut mallit (korkea taso, allekirjoitukset, kasvot, toinen
  tekstintunnistus) vapautetaan muistista kymmenen minuutin
  puhdistamattomuuden jälkeen. Aiemmin ne pysyivät ladattuina ohjelman
  loppuun asti – kerran allekirjoitushaun ja korkean tason käyttänyt
  piti pysyvästi yli kaksi gigatavua varattuna. Seuraava ajo lataa ne
  yhdessä tai kahdessa sekunnissa uudelleen; tilarivi ilmoittaa siitä.
- PowerPoint: diojen asettelujen ja diamallien lajinimiä („Tyhjä",
  „Otsikkodia") ei enää korvata tietona. „Tyhjä" on myös paikannimi ja
  peitettiin virheellisesti jokaisessa saksan- ja englanninkielisessä
  esityksessä; puhdistetaan enää käsin annetut itse diojen nimet.
- PDF:issä rivien tasoitus ei enää vedä seuraavan rivin alkua mukaan
  osumaan: seuraavan luettelokohdan numero päivämäärän jälkeen
  laskettiin puhelinnumeroksi, kenttäotsikko kuten „Kenncode" tai
  „Auftragsnummer" luvun jälkeen postinumeroksi paikkakunnan kanssa,
  ja osoitteen alla oleva paikkakuntarivi kahdensi paikkakunnan.
  Oikea, lyhyempi löytö syrjäytyi tällöin. 132 korpus-PDF:n joukossa
  24 lisätasoituslöydöstä jäljelle jää kaksi todellista; käytännön
  korpuksessa virhehälytykset laskevat 29:stä 21:een samalla
  löytöosuudella.
- „Etsi ja peitä PDF-kansio" jälkikäsittely-editorissa ei enää
  lukitse ikkunaa: ajo toimii taustalla, edistyminen ja
  peruutuspainike reagoivat, eikä valikkoja tai välilehtiä voi enää
  käyttää kesken puolivalmiin tiedoston käsittelyn.
- Skannatut sivut, joissa on löytökohtia, kirjoitetaan peitettäessä
  nyt vain kerran uudelleen kahden sijaan: aiemmin ohjelma täytti
  löytökohtien ja perustelujen laatikot kahdessa vaiheessa, ja toinen
  vaihe pakkasi juuri uudelleen tallennetun skannauskuvan vielä
  kerran. Tämä säästää aikaa suurilla skannauksilla ja välttää
  kuvanlaatuhäviön.
- Selaaminen, zoomaus ja pienoiskuvat jälkikäsittely-editorissa
  reagoivat nopeammin: jokainen renderöity sivu kulki aiemmin PNG-
  pakkauksen läpi ja heti takaisin, vain näyttämistä varten – korkean
  resoluution näytöillä tämä vei noin kymmenesosasekunnin per sivu.
  Kuva tulee nyt suoraan, kuvapiste kuvapisteeltä samana.
- Silmämääräinen tarkistus ennen PDF:n tallentamista ("tuloskoe") on
  noin kolme kertaa nopeampi, samalla tuloksella.
- Pääikkuna avautuu vielä noin neljänneksen sekunnin aiemmin:
  tarkistus siitä, onko tekstintunnistus valmis tällä koneella, kulki
  aiemmin ikkunan rakentamisen yhteydessä – Macilla lisäksi koekysely
  järjestelmän tunnistukseen – ja lisäkomponenttien asetussivu kysyi
  samalla kaikkien 48 kielen tilan. Molemmat tapahtuvat nyt taustalla
  tai vasta silloin, kun kieliluettelo todella avataan; siihen asti
  lukee „Tekoälytaso tarkistetaan …".
- Allekirjoitushaun jälkeen ohjelma käyttää noin 300 megatavua
  vähemmän muistia: tunnistusmalli oli siihen asti muistissa
  kahdesti – kerran aitouden tarkistusta, kerran laskentaa varten.
  Se tarkistetaan edelleen, vain ilman toista kopiota.
- Tekstintunnistus PDF:issä on selvästi nopeutunut: jokaista sivun
  kenttäotsikkoa ("Geburtsdatum:", "Steuernummer:") kohden lähetettiin
  aiemmin oma tunnistuskoe kutakin tietolajia varten – joka sivulla
  uudelleen, vaikka sama otsikko olisi ollut jo kymmenen sivua
  aiemmin. Vastaus muistetaan nyt; kaksisivuinen suoriteluettelo esitti
  siten 324 kysymystä, nyt enää erilaiset. Löydökset ovat samat.
- Suuret taulukot puhdistetaan taas sekunneissa minuuttien sijaan:
  anonymisoivassa toimintatavassa – oletuksessa – jo tunnettujen
  arvojen vertailu hidastui jokaisen lisäsolun myötä, koska
  välimuisti hylättiin ja rakennettiin uudelleen jokaisella osumalla.
  5 000 solua vei siihen aiemmin noin 18 sekuntia, nyt puolet siitä;
  tulos on merkki merkiltä sama.
- Pääikkuna ilmestyy vielä selvästi nopeammin: asetusten maalista veti
  ikkunan rakentamisen yhteydessä koko tunnistuskirjaston etualalle –
  noin 0,7 sekuntia Macilla, Windowsissa vastaavasti enemmän – vaikka
  siihen tarvitaan vain maiden nimet. Lista tulee nyt kevyestä
  luettelosta; kirjasto latautuu suunnitellusti taustalla, kun ikkuna
  on jo pystyssä. Tämä koskee myös jokaista kieli- tai
  ulkoasunvaihtoa, joka käynnistää ohjelman uudelleen.
- Asiakirjalaboratorio käy nyt katkaistut kenttäotsikot, paikalliset
  arvovarjot ja voimakkaat skannausrajaukset kokonaan läpi PDF-,
  DOCX- ja ODT-säiliöissä. Matriisi kattaa 680 tiedostoa 40
  asiakirjaperheestä ja 17 säiliöakselia. Maskuro poistaa uusissa
  sekä täysissä perus- ja piirreprofiileissa kaikki tavoitetiedot ilman
  mitattua virhehälytystä, vaurioitunutta säilytysarvoa tai keskeytystä.

- Useaan kertaan käytetyt skannaukset tarkistetaan ja puhdistetaan nyt
  jokaisen näkyvän sijoittelun kautta: asiakirjalaboratorio jakaa
  saman kuvaobjektin useille sivuille, kooille ja kiertoasennoille
  PDF:ssä ja viittaa samaan kuvaosaan useasti DOCX:ssä ja ODT:ssä.
  Tekniset ODT-kehysnimet kuten „Formularscan klein quer" eivät enää
  kelpaa henkilöksi; vapaat nimet ja paikat, joilla on samankaltainen
  alku, pysyvät suojattuina. Lopullisen PDF-sivuajon yleinen
  lomakearvaus ei voi enää tuottaa suurta osoitevirheosumaa jo
  itsenäisesti luetulla kuva-alueella. 120 uutta säiliötä saavuttavat
  perus- ja piirreprofiilissa kaikki 813 ja 840 tavoitetietoa ilman
  virhehälytystä, säilytysrikkomusta tai keskeytystä; täysi 800
  tiedoston piirretarkastus vahvistaa 5 600/5 600.

- Saksankielinen OCR-laboratorio kattaa nyt 560 skannausta 40
  asiakirjaperheestä. Uudet muunnelmat rajaavat kenttäotsikon ja sivun
  reunoja tai asettavat varjon suoraan arvon päälle. Maskuro suojaa
  tässä myös nimiä, osoitteita, syntymäaikoja, lääketieteellisiä
  avaimia ja merkittyjä tunnusnumeroita osittain vaurioituneella
  merkinnällä. Samalla lomakekenttien jäänteitä, virallisia otsikoita
  sekä asiallisia oikeudellisia ja tietotermejä ei enää korvata
  henkilöinä tai paikkoina. Täydet perus- ja piirreprofiilit
  saavuttavat 3 794/3 794 ja 3 920/3 920 tavoitetietoa ilman mitattua
  virhehälytystä tai keskeytystä.

- Automaattinen PDF:n kuvavalinta ei enää poista suuria
  tuotevalokuvia, energiamerkintöjä ja muotokuvasarjoja pelkästään
  siksi, että ne alkavat sivun yläreunasta. Todelliset matalat ylä-
  /alatunnistekuvat ja arkin reunasta alkavat kirjekuvat poistuvat
  edelleen. Työntekijähakemistoissa nimet tunnistetaan nyt myös
  rakenteellisesti toistuvista merkinnöistä silloin, kun näkyvä
  asiakirjan otsikko on vain kuvana. Tunnistus ei ole enää sidottu
  kahteen tiettyyn roolisanaan ja lyhenteeseen „DW": yhdestä neljään
  rivitettyä roolia sekä „Durchwahl", „Nebenstelle", „Ext." ja
  „Extension" pääteltävät yhteisestä rakenteesta. Roolit ja
  osiootsikot jäävät paikoilleen, vaikka kielimalli jättäisi
  päällekkäisyyden ratkaisun jälkeen jäljelle vain roolin adjektiivin.
  Vaakasuorat rooliruudukot eivät enää lasketa virheellisesti
  nimisarakkeiksi. Jos sivun OCR liimaa useita kortteja äärimmäisen
  leveäksi sisäisin isoin kirjaimin kirjoitetuksi sanaksi, kapea
  paikallinen vastatarkistus erottaa todelliset sanalaatikot; näin ei
  jää jäljelle yksittäistä nimeä eikä leveää virhepalkkia. Toistuvat
  moniriviset yritysten logot peitetään myös sivuilla ilman
  käyttökelpoista OCR-tekstiä ja enintään kahden kuvapisteen
  sijaintipoikkeamalla jo vahvistetun identtisen kuvapistemallin
  perusteella; lyhyemmät paikalliset OCR:n toislukemat eivät saa
  samalla enää täydentää suurempaa otsikkoaluetta keksittynä nimenä.
  Sivunumerot ennen yrityksen kirjekuvaa eivät enää kuulu
  organisaation nimeen, numerolla alkavat todelliset tuotemerkit
  pysyvät suojattuina. Useita mitattuja tuote-, ala- ja
  lomakesanoja ei enää ehdoteta henkilöiksi.

- Allekirjoitushaku toimii PDF:issä vasta OCR-kuvapuhdistuksen
  jälkeen, käy läpi myös sivut ilman tavallista tekstiosumaa ja
  laskee käännettyjen sivujen löytölaatikot oikein takaisin
  asiakirja-avaruuteen. Tiheitä tuotevalokuvia ei enää peitetä
  allekirjoituksena. Yksiselitteisesti merkittyjen
  allekirjoituskenttien yläpuolella kapea viiva-varajärjestelmä sulkee
  ohuet mallin aukot; tyhjät viivat esipainetulla päivämäärällä eivät
  laukaise sitä. Puhtaat skannaukset, joissa on vain OCR-/
  allekirjoituslöytöjä, eivät enää keskeydy tässä vaiheessa vasta
  tekstihaarassa ladatun kuvapeittäjän takia.

- Monet samanaikaisesti avoimet asiakirjat pysyvät jälkikäsittely-
  editorissa erotettavina: välilehdet eivät enää kutistu pelkäksi
  kolmen pisteen merkiksi, ja oikealla oleva listapainike näyttää
  kaikki täydelliset tiedostonimet allekkain. Välilehtiä voi
  järjestellä vetämällä ja poistaa niiden rastilla samasta listasta
  kuin pääikkunassa; tallentamaton työ selvitetään edelleen ensin.
  Oikea klikkaus tarjoaa lisäksi „Sulje", „Sulje muut välilehdet" ja
  „Sulje oikealla olevat välilehdet".

- Lyhytaikainen Windows-lukitus virustorjunnan tai hakuindeksin
  toimesta ei enää saa valmiiksi ladattua kielimalli- tai
  sanakirjakansiota epäonnistumaan lopullisessa käyttöönotossa
  virheellä „Käyttö estetty". Maskuro yrittää nyt tätä viimeistä
  kansionvaihtoa uudelleen lyhyen ajan.

- Saksankielinen asiakirjalaboratorio tarkistaa säiliöitä nyt myös
  vaihtelevalla PDF-sivun kierrolla, itsenäisesti käännetyillä
  PDF-kuvilla sekä skaalatuilla ja rajatuilla taulukkokuvilla
  DOCX:ssä ja ODT:ssä. Kenttäarvot näkyvästi käännetyissä kuvissa
  tunnistetaan taas kokonaan, teknisiä sarakenimikkeitä ei enää
  korvata paikkoina, ja nimiä, joilla on yhteinen sukunimi, ei enää
  pilkota johdonmukaisuuden jälkitarkistuksessa kahdeksi
  osaosumaksi. 320 tiedostoon kaksinkertaistettu matriisi saavuttaa
  päivämäärä-, raha- ja lääketunnistuksen ollessa mukana 2 240/2 240
  tavoitetietoa ilman mitattua virhehälytystä tai keskeytystä.

- Moninsivuiset kuva-PDF:t, sekamuotoiset teksti-/kuva-PDF:t ja
  DOCX:iin tai ODT:hen upotetut skannaukset tarkistetaan nyt omassa
  160 tiedoston laboratoriossa kaikkien 40 saksalaisen
  asiakirjaperheen kautta. Teknisiä ODT-kehysnimiä ja merkittyjä
  laitekoodeja ei enää korvata paikkoina; todelliset nimet, paikat ja
  osoitteet samoissa rakenteissa pysyvät suojattuina. Lääke- tai
  rahatunnistuksen ollessa päällä myös suoraan seuraava annostus tai
  maksuväli poistetaan kokonaan. Säiliö-, tekstiperus-, tekstipiirre-
  ja OCR-piirreajot saavuttavat yhdessä täydet määränsä ilman
  mitattua virhehälytystä tai keskeytystä.

- Turvallisuustarkistus ennen tallentamista näyttää nyt huomiota
  herättävät PDF-kohdat erikseen valittavana luettelona. „Tarkista
  editorissa" avaa juuri valitun sivun ja merkitsee alueen;
  päällekkäiset osaosumat samassa kohdassa näkyvät enää kerran. Uudet
  käyttötekstit ovat kokonaan mukana kaikissa 17 käännetyssä
  käyttöliittymän kielessä.

- Markdown-tiedostot säilyttävät korvattaessa viittaus-, korostus- ja
  alaviitesyntaksinsa. Maskuro lukee tätä varten merkkimäärältään
  saman pituisen version ilman Markdown-merkintöjä; alaviivat
  sähköpostiosoitteissa, laskutähdet ja tavalliset viittaukset ilman
  henkilötietoa pysyvät muuttumattomina.

- Useat käsin kirjoitetut merkinnät samalla PDF-sivulla haetaan nyt
  jopa kolmessa vaiheessa. Jo löydetyt piirteet piilotetaan vain
  työkuvassa, jotta ne eivät enää syrjäytä heikompia
  allekirjoituksia; käännetyillä sivuilla peittoalueet päätyvät taas
  näkyvään löytökohtaan. Aiempien turvallisuusvaiheiden
  kuvatäytteet säilyvät myöhemmässä takaisinkirjoituksessa.

- „Palauta kaikki asetukset" kattaa nyt myös kohdan „Teksti
  kuvissa". Jos OCR-komponentti ei ole saatavilla, kytkin pysyy
  teknisesti pois päältä ilman, että se virheellisesti merkitään
  toimitustilasta poikkeavaksi.

- Suuret kuvakatkelmat sivun yläreunassa eivät enää lasketa
  ylätunnisteeksi pelkän sijaintinsa perusteella. Näin erityisesti
  kuvapohjaiset tuotekuvaukset ja taulukkosisällöt säilyvät. Uudet,
  tarkasti tunnistetut sähköposti- ja lomakelöydöt eivät myöskään enää
  suodatu pois lopullisesta silmämääräisestä tarkistuksesta jo
  tarkistetulla kuva-alueella.

- Teknisiä nimike- ja tuoteririvejä ilmastointi- ja
  sähkötarjouksissa erotetaan tarkemmin henkilöistä, paikoista ja
  organisaatioista. Tämä koskee muun muassa kaapelityyppejä, AC-
  syöttöä, nimikenumeroita sekä versaalilla kirjoitettuja tuotekoodeja;
  todelliset nimet ja osoitteet pysyvät suojattuina.

- Todellisten puhdistettujen PDF:ien tarkistus ei enää sekoita
  hintaosia kuten `1 699,59` puhelinnumeroihin eikä leikkaa
  täydellisestä päivämäärästä kuten `08.05.2025` enää oletettua
  korttitietoa. Puhuttelun jälkeiset nimet päättyvät nyt rivinvaihtoon
  seuraavan kadun sijaan; liitetiedostojen nimissä olevat paikannimet
  rajataan todelliseen paikkaan. Ajoneuvojen värit, tekniset
  tila-arvot, elinkeinonimikkeet ja tuotteiden oikeudelliset muodot
  säilyvät myös. Vaurioituneita paikkamerkkilukemia kuten `|PLLZ` ei
  enää käsitellä henkilötietona toisella OCR-kierroksella.

- Sivuittain tallennetut PDF-kuvat saavat lopullisessa
  silmämääräisessä tarkistuksessa lisäkatsauksen muuttumattomassa
  kuvasijainnissaan. Tämä saa peittää jälkikäteen vain arvoja, jotka
  Maskuro on jo varmasti tunnistanut samalla sivulla. Näin esimerkiksi
  pieni käännetty osoiteleima peitetään kokonaan keksimättä uusia
  sanoja kuvien otsikoista tai teknisistä piirustuksista
  henkilötiedoiksi.

- OpenDocument-teksteissä muistiinpanon (kommentin) tekijän nimikirjaimet
  tyhjennetään nyt yhdessä tekijän kanssa. LibreOffice tallentaa ne
  koko nimen viereen omana lyhenteenään ja näyttää juuri sen sivun
  reunassa; aiemmin siellä luki edelleen „SO”, vaikka „Sieglinde
  Ortner” sen vieressä oli jo kauan sitten paikkamerkki. Tyhjennys
  tehdään vain, jos tekijä todella korvattiin – osaston muistiinpano
  säilyttää oman merkintänsä.

- Italiankielisissä liikekirjeissä lauseen alussa olevat vakioilmaisut
  eivät enää kelpaa nimeksi tai paikaksi: „Restiamo a disposizione",
  „Rimaniamo", „Attendiamo", „Alleghiamo", „Comunichiamo" ja
  „Auguriamo buon lavoro" jäivät aiemmin kiinni oletettuna henkilönä
  tai paikkatietona. Todelliset nimet samassa kohdassa („Rossi
  Mario") tunnistetaan edelleen.

- Kaksipalstaiset skannaukset suojaavat merkittyjä tunnisteita ja
  paikkatietoja nyt myös silloin, kun tekstintunnistus antaa ensin
  kaikki kenttäotsikot ja vasta sitten kaikki arvot. Kohdistus
  noudattaa näkyvää kuvapisteriviä ja toimii myös 90 astetta
  käännetyillä sivuilla. Tiiviisti erotetut passi- tai
  sopimustunnisteen osat peitetään yhdessä; merkityt syntymäajat sekä
  ICD- ja PZN-avaimet ovat myös peitossa, seuraavat asiasanat jäävät
  paikoilleen. Lyhyet nimet ja käyttäjänimet suojataan tarkoissa
  kentissä; useaan OCR-sanaan hajonneet sähköpostiosoitteet vain
  tiiviissä naapuruudessa ja täydellä sähköpostikieliopilla.
  Kenttäsidonnainen sekoittuvien merkkien korjaus sekä vielä tyhjän
  henkilökentän paikallinen jälkiluku sulkevat vaurioituneet ja
  käännetyt skannaukset ilman, että asiakentät tai jo täytetyt arvot
  laajenevat. Turvamarginaalit noudattavat sanan kokoa, ja
  piirreprofiili ottaa mukaan välittömästi viereiset annosyksiköt ja
  maksuvälit. Hieman vinosti syötetyt lomakkeet projisoidaan
  geometrisesti takaisin useasta samansuuntaisesta OCR-rivistä;
  pyöristyskohina tai ristiriitaiset todisteet eivät riitä. Lyhyet
  kirjainetuliitteet säilyvät väliviivatunnisteen edessä, ja täydellinen
  merkitty osoitelöytö korvaa vain samanlajisen katuosaosuman. Väärin
  luettu roolikentän otsikko putoaa vain vähintään kolmen tunnetun
  otsikon täyttämässä lomakesarakkeessa; keskustelunimet pysyvät
  suojattuina. Niukka reunanrajaus ja paikallinen ylivalotus
  vinottaisella valonheijastuksella täydentävät kuvamatriisia.
  Useiden lomakerivien yli ulottuvat henkilö-, paikka- ja
  yritysosumat rajataan moninkertaisesti täytetyssä kenttäsarakkeessa
  kuhunkin arvoon. Tekninen nimikearvo putoaa vain nimikeotsikon ja
  sopivan tunnistemuodon kanssa; todelliset nimet pysyvät
  suojattuina. Myös valonheijastuksesta katkenneet sähköpostiarvot
  poistetaan nimenomaisen sähköpostikenttäotsikon takana tiiviillä,
  naapurirajatulla kuvareunalla. Kaksi saman näkyvän rivin kenttä-
  arvo-paria arvioidaan nyt itsenäisesti; syvemmällä perusviivalla
  olevat arvot yhdistetään vasta kolmen yhtäpitävän geometrisen
  todisteen jälkeen. Näin tunnusnumerot, syntymäajat ja osoitteet
  pysyvät täysin suojattuina myös tiheissä lomakeasetteluissa. Katu,
  postinumero ja paikkakunta yhdistetään vain saman osoitekentän
  sisällä ja sopivalla postitusrakenteella. Tiukasti rajatut
  asiakentät apuvälineille ja hammastilalle eivät enää tuota paikka-
  tai luettelovirhehälytyksiä; todelliset nimet ja samannimiset
  kentät pysyvät suojattuina. Saksankielinen asiakirjalaboratorio
  kattaa nyt 440 skannausta ja saavuttaa 2 981/2 981 perusprofiilissa
  sekä 3 080/3 080 piirreprofiilissa. Kaikki yksitoista
  kuvamuunnosta ja kaikki 40 asiakirjaperhettä ovat 100 prosentissa,
  edelleen ilman mitattua virhehälytystä, säilytysrikkomusta tai
  keskeytystä.

- PDF-tekstitasot, joista solunerottimet ovat kadonneet, rajaavat
  organisaatio-, osoite- ja paikkatietolöydöt nyt toistuvan kenttä-
  arvo-rakenteen perusteella. Yrityksen arvoja edeltävät
  kenttäotsikot ja tekniset nuolet kuten `=>` tai `->` eivät enää
  kuulu osumaan. Pehmeiden rivinvaihtojen lisänäkymä ei enää saa
  laajentaa oikeudellisen muodon tai paikan löytöjä useiden
  taulukkorivien yli; jo täydellinen osoite päättyy ennen seuraavaa
  kenttäotsikkoa arvoineen. Lopullinen ajo kaikkien 1 600 TXT-,
  HTML-, PDF- ja DOCX-asiakirjan läpi poistaa 10 840/10 840
  tavoitetietoa nollalla virhehälytyksellä, nollalla
  säilytysrikkomuksella ja nollalla keskeytyksellä.

## 0.10.44-beta.1 – 1. syyskuuta 2026

- Paketointi tuottaa nyt erilliset julkaisut Windows x64:lle ja ARM64:lle, macOS Apple Silicon- ja Intel-koneille sekä Linux x64:lle ja ARM64:lle. Pakettien nimet, päivitysvalinta ja julkaisut erottelevat arkkitehtuurin; julkaisu pysyy lukittuna, kunnes kaikki kuusi kohdetta ja niiden riippuvuusnäyttö ovat valmiina. Linux ARM64 edellyttää Qt:n vuoksi vähintään glibc 2.39:ää. Täysin oikealla laitteistolla hyväksyttyjä ovat toistaiseksi vain Windows x64 ja macOS Apple Siliconilla; muut arkkitehtuuripaketit on merkittävä selvästi kokeiluversioiksi, ei tuotantokäyttöön.

- Useaa tiedostoa käsiteltäessä tunnistus jatkaa nyt työtään, vaikka esikatselu odottaa läpikäyntiä. Jopa kolme valmisteltua esikatselua näytetään peräkkäin; samanaikaisesti lasketaan silti vain yksi asiakirja, ja tulostiedosto syntyy vasta hyväksynnän jälkeen. Esikatselussa valittu pysyvä poikkeus koskee myös jo valmisteltuja seuraavia asiakirjoja.

- Redigointivarmenteet voi nyt tarkistaa milloin tahansa suoraan Tiedosto-valikosta mustattua asiakirjaa vasten. Maskuro erottaa tällöin täsmäävän allekirjoitetun tiedoston, täsmäävän mutta allekirjoittamattoman todisteen, virheellisen allekirjoituksen ja varmenteeseen kuulumattoman asiakirjan. Lisenssiä tai alkuperäistä käyttöjärjestelmätiliä ei tarvita vastanäyttöön.
  Automaattisille tarkastuspisteille sama vertailu on saatavilla komennolla `--zertifikat-pruefen`; paluukoodit erottavat täsmäävyyden, käyttövirheen ja virheellisen todisteen.
  Vastanäyttö vertaa lisäksi upotettua Maskuro-tunnusta varmenteeseen; vapaasti kirjoitettu vieras tunnus paljastuu näin myös allekirjoittamattoman todisteen tapauksessa.
  Kun allekirjoitus on kelvollinen, tarkastustulos näyttää lisäksi hallinnon aktivoiman käsittelijän käyttöjärjestelmätilin, teknisen tilitunnuksen ja alustan kanssa. Vahvistamattomia tietoja allekirjoittamattomista tai virheellisistä todisteista ei näytetä.

- Uusi saksankielinen asiakirjalaboratorio tuottaa 160 täysin synteettistä TXT-, HTML-, PDF- ja DOCX-asiakirjaa kymmenestä alueesta ja neljästä rakennemuunnelmasta. Manifesti erottaa nyt nimenomaisesti tiedot, joiden on kadottava, ja asiasisällöt tai asiatunnisteet, joiden on säilyttävä; asiakirjaperhe, muunnos ja julkinen rakennelähde on merkitty jäljitettävästi.

- Saksankielinen asiakirjalaboratorio laajennettiin 280 tiedostoon, seitsemään rakennemuotoon, 1 540 tavoitetietoon ja 1 036 säilytysankkuriin. Uutena tarkastetaan numeroituja lomakkeita, sulkeissa olevia PDF-/naamiokenttiä ja teknisiä `=>`-vastaavuuksia. Laajennettu täysi mittaus saavuttaa TXT:ssä, HTML:ssä, PDF:ssä ja DOCX:ssä kussakin 100 prosenttia nollalla väärällä hälytyksellä. Sulkeissa olevat päivämäärä- ja tunnusnumerokentät, nuolierottimet ja nimenomaisesti otsikoidut ryhmät tunnistetaan nyt rakenteellisesti.

- Toinen laboratoriolaajennus nostaa kannan 400 asiakirjaan, kymmeneen rakennemuotoon, 2 200 tavoitetietoon ja 1 480 säilytysankkuriin. JSON-tyyppiset avain-arvo-parit, YAML-listat ja versaalilla kirjoitetut lomakekentät saavuttavat aiemman kannan kanssa yhdessä 100 prosenttia nollalla väärällä hälytyksellä. Lainatut syntymäajat ja tunnusnumerot sekä nimenomaisesti otsikoidut roolit kuten vakuutetut, hakijat, ilmoitusvelvolliset ja edustusvaltuutetut henkilöt tunnistetaan nyt myös näissä vientimuodoissa.

- Saksankielisen asiakirjalaboratorion erillinen OCR-tila tuottaa lisäksi 200 puhdasta kuvaskannausta kaikista 40 perheestä. Puhtaat, matalakontrastiset, matalaresoluutioiset, JPEG-artefaktien vaivaamat ja 90 astetta käännetyt sivut mitataan uudelleen tarkoilla pikselilaatikoilla ilman, että vertailukelpoinen 1 600 tiedoston tekstiperustaso muuttuu. Manifesti erottaa kytkettävät päivämäärä-, raha- ja lääketieteelliset piirteet perusprofiilista ja tuntee todistetut OCR-lukutavat laskematta niitä ylimääräisiksi tavoitekohdiksi. Mittaus eritellään muunnoksen ja asiakirjaperheen mukaan. Tiukat kenttärajat estävät muun muassa sen, että `Az` paikannimessä `Graz` mustaa seuraavan päivämäärän asianumerona; nykyinen perusmatriisi toimii nollalla väärällä hälytyksellä ja nollalla keskeytyksellä.

- Viisi lisää saksankielistä asiakirjaperhettä laskulle/toimituserälle, pankki-/luottoasioille, vuokralle/talonhallinnolle, koululle/korkeakoululle ja logistiikalle/tullille laajentavat laboratorion 600 tiedostoon 3 520 tavoitetiedolla ja 2 360 säilytysankkurilla. Tiukka PDF-taulukkopolku käyttää nimenomaista otsikkoa `Feld Angabe`, kun tekstitaso menettää solurajat; uusi `--familien`-valinta nopeuttaa osittaismittauksia. 200 uutta tiedostoa saavuttavat 1 320/1 320 nollalla väärällä hälytyksellä ja nollalla keskeytyksellä.

- Vakuutus/vahinko, työ/palkka, lääketiede/laboratorio, ajoneuvo/korjaamo ja tekniikka/huolto laajentavat saksankielisen asiakirjalaboratorion 800 tiedostoon 4 960 tavoitetiedolla ja 3 200 säilytysankkurilla. Tiukasti otsikoidut vakuutuskirja-, potilas-, tarkastaja- ja ajoneuvotunnisteet sekä uudet rooli-, osoite- ja organisaatiokentät tunnistetaan. Uusi osamatriisi ja täysi matriisi saavuttavat 100 prosenttia nollalla väärällä hälytyksellä ja nollalla keskeytyksellä TXT:ssä, HTML:ssä, PDF:ssä ja DOCX:ssä.

- Rakentaminen/tarjouskilpailu, energia/ympäristö, yhdistys/yhtiö, viestintä/kalenteri ja hotelli/tapahtuma nostavat saksankielisen asiakirjalaboratorion 1 200 tiedostoon 7 920 tavoitetiedolla ja 4 800 säilytysankkurilla. Uudet rooli-, yritys-, osoite-, rekisteri-, hankinta-, varaus- ja käyttäjätilikentät tunnistetaan myös kaikissa vientimuodoissa. Mittarinumerot säilyvät asiatunnisteina. Osa- ja täysmatriisi saavuttavat 100 prosenttia nollalla väärällä hälytyksellä ja nollalla keskeytyksellä.

- Ravintola-ala/toimituspalvelu, apteekki/resepti, hautaustoimisto/hautausmaa, urheilu/jäsenyys ja kiinteistöt/välitys laajentavat saksankielisen asiakirjalaboratorion 1 400 tiedostoon 9 360 tavoitetiedolla ja 5 640 säilytysankkurilla. Uudet henkilöroolit, osoitekentät ja etsintätoimeksiantonumerot tunnistetaan. Oikeushenkilömuodolla merkityt yritysnimet pysyvät suojattuina täydellisesti myös automaattisen rivinvaihdon yli; ikäluokkia ja ammattinimikkeitä ei enää korvata virheellisesti. Osa- ja täysmatriisi saavuttavat 100 prosenttia nollalla väärällä hälytyksellä ja nollalla keskeytyksellä.

- Hammashoito, autokoulu, palokunta/hälytystehtävä, energiayhteisö ja pakettimatka laajentavat saksankielisen asiakirjalaboratorion 1 600 tiedostoon 10 840 tavoitetiedolla ja 6 440 säilytysankkurilla. Uudet roolit, osoitekentät sekä hoito-, koulutus-, hälytys-, energia- ja matkasopimustunnisteet tunnistetaan rakenteellisesti. Uusi 200 tiedoston osamatriisi saavuttaa 1 480/1 480; täysi matriisi saavuttaa 10 840/10 840. Molemmat pysyvät nollassa väärässä hälytyksessä ja nollassa keskeytyksessä.

- Asiakirjalaboratorion täysmittaus laski tiukkojen virallisten asiamuotojen ja rakennesääntöjen ansiosta tarpeettomat korvaukset 68:sta 0:aan, nimenomaisesti mitatut säilytysrikkomukset 23:sta 0:aan ja keskeytykset 3:sta 0:aan. Löytöosuus nousi samalla 91,1:stä 100,0 prosenttiin; TXT, HTML, PDF ja DOCX saavuttavat kukin 100 prosenttia. Yleiset taulukko-otsikot kuten `Feld` hillitään vain todistetussa `Feld`/`Angabe`-järjestyksessä; samanniminen sukunimi pysyy suojattuna. Tuomioistuinten asianumerot loppukirjaimineen, yhtäläisyysmerkkikentät, `Geburtsdatum des Kindes` ja useat otsikoidut yksittäiset nimet samalla rivillä tunnistetaan täydellisesti. Word-taulukot ja edeltävän rivin kentät käyttävät kenttäotsikkoaan väliaikaisena tunnistuskontekstina; otsikoidut PDF-osoitteet pysyvät suojattuina myös lauserakenteen aiheuttaman rivinvaihdon yli.

- Saksalaiset henkilöominaisuus-, ammatti- ja lääketieteelliset kentät toimivat nyt myös Windows-rivinvaihdoilla. Yksikirjaimiset sukupuolimerkinnät kuten `Geschlecht`/`w` suojataan edeltävän rivin muodossa. Asialliset `Artikel-PZN`-kentät eivät sen sijaan laukaise lääkeavain- eikä henkilölöydöstä; todelliset PZN-, ICD- ja ATC-tiedot tunnistetaan edelleen.

- Saksalaiset lomake- ja numerokentät ovat tarkempia: "DW." toimii nyt myös ennen pehmeää rivinvaihtoa, nimenomaisesti otsikoidut nimet poistetaan myös pienellä kirjoitettuina, ja puhtaasti numeeriset asianumerot kohdistetaan oikeaan tunnusnumerolajiinsa. Toisaalta sattumalta Luhn-kelpoinen lasku-, kuitti- tai tuotenumero ei enää lasketa luottokortiksi. Synteettiset HTML- ja PDF-tulostenäytteet vahvistavat poiston ja säilymisen valmiissa asiakirjassa.
  Tunnusnumerot ja käyttäjätunnukset tunnistetaan lisäksi, kun niiden otsikko on välittömästi edeltävällä taulukko- tai lomakerivillä; asialliset kuittinumerot pysyvät näkyvissä myös tässä muodossa.

- Salasanat tunnistetaan nyt myös yksinäisen kenttäotsikon takana edellisellä rivillä. Lopussa olevat erikoismerkit kuten `!` tai `#` kuuluvat tällöin kokonaan suojattuun arvoon. Tuote- ja artikkeli-PIN-koodeja ei sen sijaan enää naamioida kortin PIN-koodina; nimenomaiset `PIN`- ja `Karten-PIN`-kentät pysyvät suojattuina.

- Pienellä kirjoitetut lomakearvot tuotetaan yksiselitteisissä saksalaisissa osoite- ja `PLZ/Ort`-kentissä nyt osoitteena tai postinumerona paikkakunnan kanssa yleisen paikannimen sijaan. Samoin pienellä kirjoitetut yritysarvot kuten "beispiel service" pysyvät yrityskentän takana täysin suojattuina, ilman että loppusana katkaistaan luultuna seuraavana kenttäotsikkona.

- Ohje, UKK, tietosuojateksti ja verkkosivusto selittävät nyt yhdessä alkuperänäytön: neutraali Maskuro-tunnus asiakirjassa, valinnainen yhdistäminen todelliseen käyttöjärjestelmätiliin vain paikallisessa tarkastuslokissa, käyttäjänvaihto Windowsissa/macOS:ssä/Linuxissa sekä SHA-256:n ja allekirjoituksen todistusarvo.

- Kuvapohjaisia teknisiä työselityksiä puhdistetaan nyt maltillisemmin. Yksiselitteiset asiasanat kuten "Abbruchhämmern", "Deckungsrücklass", "Positionsnummern", "Einbauplatine" tai "Terminsituation" sekä sanan keskeltä katkenneet OCR-muodot eivät enää lasketa henkilöksi tai paikaksi. Todellinen kunnantoimiston tarjous laski tämän ansiosta 140:stä 90:een yksiselitteiseen korvaukseen ilman uusia löytöjä; nimet kuten Schneider, Lang, Bauer ja Hahn pysyvät nimenomaisesti suojattuina.

- Lisää vääriä hälytyksiä todellisista tarjouksista on korjattu: "Digital signiert" ei enää sisällä luultua henkilöä, BIC tunnistetaan otsikkonsa takana myös ilman kaksoispistettä, `15000 Alternativ` ei lasketa postinumeroksi paikkakunnan kanssa, ja EU-lainaus "(VO (EG) 715/2007" ei tuota organisaatiota. Aurinkosähkötarjous laski tämän ansiosta 26:sta 16:een korvausesiintymään; todelliset nimet, paikat ja tilitiedot säilyivät.

- Työntekijäluetteloissa lyhennettä "Stv." (sijainen) ja yksin erotettua "FACILITY"-osastootsikkoa ei enää korvata henkilönnimenä. Todellinen 13-sivuinen vastanäyttö laski 878:sta 875:een korvaukseen; nimet, alanumerot ja yrityksen nimi pysyivät suojattuina.

- Puhdistetut PDF-, OpenDocument- ja Office-tiedostot saavat neutraalin `MASKURO-…`-tunnuksen asiakirjatietoihinsa. Tarkastusraportti ja allekirjoitettu tarkastuspöytäkirja käyttävät samaa tunnusta sekä lähteen ja tuloksen SHA-256-arvoja; redigointivarmenne ottaa tunnuksen valmiista tiedostosta. Käyttäjänimi lisätään edelleen vain, jos hallinto kytkee olemassa olevan käyttäjäkentän nimenomaisesti päälle.

- Pääikkuna ja asetukset on jäsennelty rauhallisemmin: Tallenna, Kopioi, Tiedot, Tunnusluvut ja tunnistusprofiilin poisto näkyvät vasta, kun kyseinen toiminto on mahdollinen. Tekniset OCR-kielilyhenteet ja pitkät esimerkit ovat tarvittaessa vihjetekstissä eivätkä pysyvästi työtilassa. Tunnistussivu mukautuu paremmin kapeampiin ikkunoihin ilman katkaistuja selityksiä tai vaakavierityspalkkeja; varoitus selkotekstistä korvauslistassa pysyy silti näkyvissä.

- Tunnistus kattaa lisää saksalaisia ja kansainvälisiä yhteystietotapauksia: puhelinnumerot tarkistetaan nyt kaikille valittavissa oleville maa-alueille, unkarilaiset ja kroatialaiset sopimusroolit kattavat nyt myös ammattinimen kaltaiset sukunimet kokonaan, eivätkä numeroidut varaosa-/materiaaliluettelot enää laukaise henkilön väärää hälytystä sanoista "Mutter / Flach". Henkilökenttiä, joiden asiallinen arvo sisältää selvästi numeroita, ei enää oteta nimeksi; koneluettava passivyöhyke (MRZ) voidaan lisäksi kytkeä päälle ja pois yhdessä ryhmän "Tunnisteet" kanssa.

- Yritykset ilman oikeushenkilömuotoa erotetaan paremmin henkilöistä monimerkityksellisten työnantajakenttien takana: nimet kuten "Huber Handel", "Müller Logistik" tai "Kowalski Handel" tunnistetaan täysin yrityksenä, kun taas "Arbeitgeber: Bauer Anna" pysyy edelleen henkilönnimenä. Automaattinen maavalinta ottaa ranskankielisissä asiakirjoissa edelleen huomioon koko ranskankielisen alueen, Luxemburg mukaan lukien.

- Kuvassa tunnistetut allekirjoitukset ja henkilötiedot peitettiin tähän asti aina mustalla suorakulmiolla – myös silloin, kun mustaukseen oli asetettu muu väri tai kuvio kuten "Sateenkaari". Nämä kuva-alueet käyttävät nyt myös valittua mustaustyyliä; peittävä pinta kirjoitetaan edelleen suoraan kuvapisteisiin.

- Englanninkielinen tunnistus mitattiin uudelleen ja parannettiin kohdennetusti yhdellätoista käsin käännetyllä todellisella asiakirjalla: varastostatus, tekniset tarjous- ja verkkokauppakentät sekä roolit henkilöstöhakemistoissa pysyvät näkyvissä, "CV" ei enää lueta oikeushenkilömuodoksi lomakelauseessa, lainatut fontit säilyvät, ja nimet pystysuorissa ansioluetteloiden otsikoissa, monisivuisissa henkilöstöluetteloissa, sanan "Account manager" takana sekä numerolla alkavat yritysnimet tunnistetaan täydellisesti. Itävaltalaiset kaupparekisterinumerot toimivat nyt myös englanninkielisen otsikon takana; lyhyt muoto "Customer:", EAR-rekisteröintinumerot ja työnantajanumerot kantavat arvonsa. Mittaketjut, kaapelityypit, EU-oikeusviittaukset, tarjouksen voimassaolopäivät, täytäntöönpanopaikat, oikeuspaikat, rekisterituomioistuimet, verolyhenne "NoVA", tekniset numerot rengasmerkinnöissä sekä standardiviittaukset kuten "OVE R6-2" ja "AStV" eivät enää tuota väärää hälytystä. Kelvollinen otsikoitu IBAN päättyy siististi ennen rekisteröintikenttää tai seuraavan rivin otsikkoa; osoitteet elinkeinoaluelisäyksellä tunnistetaan täydellisesti myös PDF-tekstivirroista Windows-rivinvaihdoilla. Englanninkieliset yritysjohdannot ja jäsennellyt säästöpankkinimet rajataan täysin. Lähtöasiakirjan maa säilyy postinumeroiden ja maakohtaisten tunnisteiden kieliversioissa.

- Vastaanottaja- ja viestin otsikkorivillä kielimalli saattoi yhdistää pilkkulistan kaksi ensimmäistä nimeä yhdeksi ainoaksi löydöksi ("Bcc: Huber, Mayer"). Molemmat nimet tunnistetaan, korvataan ja kirjataan raporttiin nyt erikseen – myös sanojen "Sent:", "Reply:" ja "Fwd:" takana.

- Passin tai henkilötodistuksen koneluettava alue (MRZ) puuttui ryhmäohjauksesta "Mitä etsitään". Se kuuluu nyt ryhmään "Tunnisteet" ja voidaan kytkeä päälle ja pois yhdessä sen kanssa.

- Korvaustekstien mallia "Sateenkaari" valitseva saa nyt saman ulkoasun myös mustattuihin kohtiin; aiemmin ne pysyivät yllättäen perinteisen mustina. Mustausalueet voi tämän jälkeen edelleen vaihtaa itsenäisesti toiseen malliin.

- Korjaus-editorin sivupaneeli saattoi jäädä tyhjäksi tallennetun ikkunanjaon palauttamisen jälkeen, kunnes sen leveyttä muutettiin käsin. Pienoiskuvat järjestetään nyt uudelleen näkyvän ikkunarakenteen jälkeen ja ovat heti keskellä paneelia.

- PDF-tiedostojen korvaustekstien ympärillä olevat väritetyt tarkastusmerkit pysyivät luokka- ja liikennevärin mukaan tuskin näkyvinä. Vaalea alikontuuri erottaa nyt tarkastuskehyksen luotettavasti värillisestä paikkamerkistä ja sivun taustasta.

- Kun Korjaus-editorissa mustattiin rivi asiakirjasta, joka on ladottu tiheällä riviväliliä (tyypillistä tarjouksille ja työselityksille), syntyi palkki, joka ulottui alla olevan rivin yläpidennyksiin – rivi jäi sen jälkeen vain puoliksi luettavaksi. Palkki päättyy nyt naapurin todella piirrettyyn tekstiin; mustattu rivi itse pysyy alapidennyksineen edelleen täysin peitettynä.

- Harjoitusasiakirja ("Ohje → Avaa harjoitusasiakirja", myös kierroksella) esittelee nyt jokaisen tunnistuslajin: keksittyyn kirjeeseen lisättiin tunnistettavat kasvot sisältävä valokuva, käsin kirjoitettu allekirjoitus, ammatti ja osasto, diagnoosi ja lääke – yrityksen nimen, summan ja päivämäärän lisäksi, jotka olivat jo mukana. Se, minkä oletusasetus jättää tarkoituksella paikalleen, selitetään lomakkeella itsellään, kytkimen kera, joka poistaa sen; valokuvan kasvot pikselöidään tehtaalla oletuksena.

- Rahasummat tavallisessa saksalaisessa kirjoitusasussa, jossa symboli on luvun jäljessä ("1.240,00 €"), eivät koskaan löytyneet kytkimellä "Poista myös rahasummat" – "1.240,00 EUR" ja "€ 1.240,00" sen sijaan aina. Nyt kaikki kolme kirjoitustapaa tunnistetaan.

- Allekirjoitushaku toimii nyt myös erillisillä kuvatiedostoilla: kuka tahansa puhdistaa JPG- tai PNG-skannauksen, saa siinä olevat käsin kirjoitetut allekirjoitukset mustattua – sama tunnistus, sama ilmoitus raportissa kuin PDF:ssä. Office-tiedostoihin upotettuja kuvia ei edelleenkään haravoida, koska tunnistus toimii siellä mitattujen mukaan epäluotettavasti; valintaruutu on siksi nyt nimeltään "PDF ja kuvatiedostot: mustaa käsin kirjoitetut allekirjoitukset".

- Mustauspalkki saattoi tiheällä riviväliljä ulottua näkyvästi alla olevan rivin yläpidennyksiin ja tehdä sen puoliksi lukukelvottomaksi – palkin korkeus tuli fonttimetriikasta, ei siitä, mitä paperilla todella on. Palkki päättyy nyt naapurin todella piirrettyyn musteeseen, sekä Korjaus-editorissa että automaattisessa puhdistuksessa. Oma rivi alapidennyksineen pysyy tällöin aina täysin peitettynä; jos rivit todella menevät päällekkäin, palkki jää mieluummin naapurin rivin päälle kuin vapauttaa jotain.

- Henkilöstöhakemistossa, jossa rooli on nimen alla, naisellinen johtotehtävän nimike ("Anna Berger" ja alla "Montageleiterin") vedettiin mukaan nimen korvaukseen – vieressä oleva miehinen muoto pysyi oikein paikallaan. Naisellisia "…leiterin"-muotoja (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-, Gruppen-, Amtsleiterin) käsitellään nyt kuten niiden miehisiä vastineita toiminimikkeenä; Filial-, Personal- ja Vertriebsleitung ovat uutena mukana molemmissa muodoissa.

- Kytkettävä ammattitunnistus ei löytänyt naisellisia johtorooleja kuten "Projektleiterin", "Teamleiterin" tai "Abteilungsleiterin", mutta niiden miehiset muodot kylläkin. Molemmat muodot lasketaan nyt tasavertaisesti.

- Esikatseluikkunassa Macilla monikkomerkintä oli liimautunut suoraan käsitteeseen kiinni ("Anna Musterfrau2ק" eikä "Anna Musterfrau 2ק). Väli on jälleen paikallaan.

- Vertailusuurennuslasilla on uusi painike zoom-säätimen vieressä: yhdellä painalluksella se asettuu koko leveydelle tuloksen päälle – kumpikin puoliksi korkeudesta, ja alkuperäinen samassa mittakaavassa kuin asiakirja (suurennuslasin zoom hyppää tällöin 100 %:iin). Toinen painallus telakoi sen jälleen pieneksi vasempaan sarakkeeseen ja palauttaa edellisen suurennuslasin zoomin. Vierellä oleva kehä nollaa nyt vain zoomin – sen vihjeteksti väitti aiemmin virheellisesti, että se telakoi myös ikkunan takaisin.

- Korjaus-editorin työkalupalkissa valitusta työkalusta näkyy jälleen, että se on valittuna: aktiivisen työkalun painike kantaa täytetyn pinnan sinisellä reunalla – samoin jokainen muu palkin päällä oleva vaihtopainike (esim. vertailusuurennuslasi tai oppimistila). Merkintä oli kadonnut 29. elokuuta tehdyn oman paininasettelun myötä.

- Työselityksen positionumerot ("2.3.3.3, 2.3.3.4, 2.3.3.5" allekkain) luultiin IP-osoitteiksi ja poistettiin tuloksesta; kolmiportaiset numerot vuoden kaltaisella viimeisellä osalla ("2.3.19, 2.3.20") tulkittiin kalenteripäiviksi. Nouseva numerojono rivin alussa lasketaan nyt siksi, mitä se on – positioluetteloksi; todelliset osoitteet (verkkotaulukot teknisen sanaston ympäröimänä, luvut yli 99) ja todelliset päivämäärät tunnistetaan edelleen.

- Sukunimet kuten "Müller", "Fischer", "Bauer", "Koch", "Wagner", "Schneider", "Weber", "Jäger", "Schmied", "Becker", "Schuster", "Schäfer" tai "Meister" jäivät selkotekstiin listoissa muodossa "Sukunimi, Etunimi" (esim. "Teilnehmer: Müller, Peter; Nowak, Anna"), koska ne ovat samalla yleisiä ammattinimikkeitä. Ne tunnistetaan nyt luotettavasti.

- PDF:ää mustattaessa palkki saattoi viedä kapeassa taulukkosolussa koko solun mukanaan: löydöksestä "D-LINK" työselityksessä katosi koko vieressä oleva tuotekuvaus, vaikka esikatselu oli maininnut vain löydöksen. Palkki peittää edelleen kokonaisia osoitelohkorivejä ja kenttäotsikoita, mutta nielee korkeintaan yhtä paljon asiaankuulumatonta kuin se peittää suojattavaa – kuvaus löydöksen vieressä pysyy nyt paikallaan.

- "Näytä uudelleen alkuperäisenä" Korjaus-editorissa jätti sivupaneelin tyhjäksi – sivujen pienoiskuvat näkyivät uudelleen vasta ikkunan sulkemisen ja avaamisen jälkeen. Nyt ne ovat paikallaan heti nollauksen jälkeen, keskellä kuten ennenkin.

- Korjaus-editorissa on neljäs työkalu: **Poista** ottaa kehyksen alla olevan tekstin pois ilman korvausta – ilman palkkia (mustaus) ja ilman paikkamerkkiä (korvaus); aukko jää näkyvästi tyhjäksi. Se toimii sanan tarkkuudella; jos alla on kuva, sen pohja tyhjennetään valkoiseksi, ja "Palauta alkuperäinen" perii myös korvauksettoman poiston takaisin. Oma työkalupalkin kuvake ja tähtäinmerkki (risti), oma pikanäppäin kaikissa 18 kielessä (saksaksi F kuten "entFernen").

- PDF-hakupalkissa "Kansio …" on nyt hakuvalintojen oikealla puolella. Siitä lähtien kun mustauksen lisäksi on ollut myös löydösten korvaaminen, viisi painiketta eivät enää mahtuneet vierekkäin tavallisella ikkunan leveydellä – ensimmäinen puristui kokoon ja sen teksti katkesi.

- "Palauta kaikki asetukset" nollaa nyt myös valintaruudun "Korvaa punainen/vihreä muilla väreillä" ja merkitsee sen kuten minkä tahansa muunkin "muutettu"-merkinnällä, kun se poikkeaa toimitustilasta.

- PDF:ien korvaustekstit vaikuttavat nyt tasaisemmilta: kun täyden paikkamerkin pitäisi olla selvästi pienempi kuin rivinsä (esim. "[BEG16]" puristettuna lyhyeen sanaan kuten "Das"), näkyy sen sijaan rivikokoinen lyhennemuoto ("[B16]") – hyvin luettavissa pienen pienen sijaan, ja palautusnumero kantaa molemmat kirjoitusasut. Paikkamerkki muuttuu erittäin pieneksi vain, jos edes lyhin muoto ei mahdu – se pysyy silti parempana kuin palkki ilman minkäänlaista tietoa.

- Monivärinen korvausteksti (liukuväri tai sateenkaari) PDF:ssä pysyi ehjänä vain seuraavaan toimenpiteeseen asti: jokainen seuraava korvaus tai mustaus samalla sivulla saattoi työntää jo asetetut paikkamerkit lukukelvottomaksi, litistyneeksi kirjainpinoksi – editorissa sana kerrallaan korvaava näki sanan "[BEG17]" sijaan vain päällekkäin painettuja merkkejä. Kerran asetetut paikkamerkit pysyvät nyt sellaisina kuin ne asetettiin.

- Esikatselun pysyvän poikkeuksen kytkin on nyt nimeltään "Älä koskaan poista" – kuten lista, johon se kirjaa; aiemmin siinä luki "ei koskaan enää". Vieressä oleva löydösrivi on siistimpi: info-symboli "ⓘ" on suurempi ja helpompi osua, ja valintaruutu, korvausmerkki ja painike ovat samalla korkeudella. Löydöksen ympärillä oleva lause käyttää nyt todella sille ilmoitettua leveyttä – aiempi leveysasetus oli hylätty näkymässä hiljaisesti, ja katkelma taittui kapeana raitana.

- Editorissa hiiren osoitin kertoo nyt, mikä työkalu on käytössä: tähtäin kohdistamiseen, sen vieressä pieni merkki – palkki mustaukseen, vaihtonuolet korvaukseen, kumoamiskaari palautukseen, pikseliruudukko pikselöintiin. Aiemmat käsi-symbolit poistuivat; käsi tarkoittaa muualla aina "tartu ja siirrä". Sillä on nyt sopiva tehtävä: punaisella korostetun sanan tai palkin päällä osoitin muuttuu osoittavaksi kädeksi – siellä riittää yksi klikkaus.

- "Suurin tunnistus (tekoäly)" ei enää tarjoa ladattavaa, paikallista kielimallia – taso laskee nyt yksinomaan kohdassa "Liitä oma tekoäly" määritetyn oman tekoälyn kautta. Jos oma palvelin oli jo liitetty, muutosta ei huomaa.

- Esikatselun opastettu kierros selittää nyt myös info-symbolin "ⓘ", joka näyttää löydöksen ympärillä olevan lauseen. Ja tämä lause on itsessään paremmin luettavissa: askel isompi fontti, enemmän riviväliä, kiinteä leveys kapean, tiheästi rivittyvän tekstin sijaan.
- Myös "Tarkista tiedosto", "Tunnistussäännöt ja omat termit", "Puhdista teksti" ja "Puhdista kuva" saavat nyt oman kierroksen – uuden "Kierros ikkunan läpi" -painikkeen kautta, koska näillä neljällä ikkunalla ei ole omaa valikkopalkkia.
- Nimet yhdeksän ukrainalaisen sopimusroolin otsikon alla jäivät homografisen sukunimen tapauksessa vajaasti tunnistetuiksi, kun otsikko oli yksinään omalla rivillään: "Покупець"/"Продавець" (ostaja/myyjä), "Поручитель"/"Боржник" (takaaja/päävelallinen), "Свідок" (todistaja), "Орендодавець"/"Орендар" (vuokranantaja/vuokralainen) ja "Спадкодавець"/"Спадкоємець" (perinnönjättäjä/perijä). Nimet tunnistetaan nyt täydellisesti.

- Excel-työkirjan nimetyn alueen kommentti (Nimimanageri, kenttä "Kommentti") kantoi siihen kirjoitetun nimen muuttumattomana mukanaan. Se puhdistetaan nyt aivan kuten työkirjan muu sisältö.

- Nimet seitsemän unkarilaisen sopimusroolin otsikon alla jäivät homografisen sukunimen tapauksessa kokonaan huomaamatta: "Bérbeadó"/"Bérlő" (vuokranantaja/vuokralainen), "Vevő"/"Eladó" (ostaja/myyjä), "Kezes"/"Főadós" (takaaja/päävelallinen) ja "Tanú" (todistaja). Nimet tunnistetaan nyt täydellisesti.

- Nimi tšekkiläisen ostaja-otsikon "Kupující" alla jäi homografisen sukunimen tapauksessa kokonaan huomaamatta. Nimi tunnistetaan nyt täydellisesti.

- Nimi venäläisen holhoojaotsikon "Опекун" alla jäi homografisen sukunimen tapauksessa kokonaan huomaamatta. Nimi tunnistetaan nyt täydellisesti.

- Nimet kuuden lisäkroatialaisen otsikon alla jäivät huomaamatta: "Jamac" (takaaja), "Glavni dužnik"/"Dužnik" (päävelallinen/velallinen), "Ostavitelj" (perinnönjättäjä), "Nasljednik" (perijä) ja "Vjerovnik" (velkoja). Nimet tunnistetaan nyt täydellisesti.

- Tallennettu HTML-sivu, jossa oli upotettu alasivu `<embed>`-elementin `src`-attribuutissa (`data`-attribuutin sijaan kuten `<object>`-elementissä), kantoi siinä olevat henkilötiedot muuttumattomina mukanaan. Ne puhdistetaan nyt aivan kuten `<object>`-elementin tapauksessa.

- Nimet viiden tanskalaisen sopimusroolin otsikon alla jäivät homografisen sukunimen tapauksessa vajaasti tunnistetuiksi, kun otsikko oli kaksoispisteellä ennen nimeä: "Arvelader"/"Arving" (perinnönjättäjä/perijä), "Befuldmægtiget"/"Fuldmagtsgiver" (valtuutettu/valtuuttaja) ja "Værge" (holhooja). Nimet tunnistetaan nyt täydellisesti; vastaavat norjalaiset otsikot on lisätty myös varmuuden vuoksi.

- Word- ja PowerPoint-tiedostojen paikkamerkit kantavat nyt saman värin kuin valitussa ulkoasussa (yksivärinen, liukuväri, sateenkaari tai luokittain) – aiemmin ne pysyivät siellä tavallisessa tekstivärissä, vaikka PDF-tulokset olivat jo pitkään värillisiä.

- "Kopioi tekstinä" ja "Kopioi Markdownina" vievät tuloksen selkotekstin suoraan leikepöydälle – liitettäväksi chattiin, sähköpostiin tai toiseen ohjelmaan ilman tiedoston avaamista.

- Nimet viiden lisäsloveenialaisen otsikon alla jäivät huomaamatta: "Toženec" (vastaaja), "Tožnik" (kantaja), "Zastavitelj" (pantinantaja), "Zastavni upnik" (pantinsaaja) ja "Darovalec" (lahjoittaja). Nimet tunnistetaan nyt täydellisesti.

- Word-taulukkosolun seuratun muutoksen (lisätty, poistettu tai yhdistetty solu) tekijän nimi jäi tiedostoon, vaikka sama nimi kommentin tekijänä oli jo pitkään poistettu. Se poistetaan nyt myös.

- Nimet yhdeksän lisäsloveenialaisen otsikon alla jäivät huomaamatta: "Najemodajalec"/"Najemnik" (vuokranantaja/vuokralainen), "Zapustnik"/"Dedič" (perinnönjättäjä/perijä), "Upnik"/"Dolžnik" (velkoja/velallinen), "Glavni dolžnik" (päävelallinen) ja "Skrbnik" (holhooja/huoltaja). Nimet tunnistetaan nyt täydellisesti.

- Nimet viiden sloveenialaisen otsikon alla jäivät huomaamatta: "Izvedenec" (asiantuntija), "Kupec" (ostaja), "Prodajalec" (myyjä), "Naročnik" (tilaaja) ja "Izvajalec" (toimeksisaaja). Nimet tunnistetaan nyt täydellisesti.

- Nimet viiden lisäliettualaisen otsikon alla jäivät huomaamatta: "Užsakovas" (tilaaja), "Vykdytojas" (toimeksisaaja), "Vežėjas" (rahdinkuljettaja), "Siuntėjas" (lähettäjä) ja "Arbitras" (välimies). Nimet tunnistetaan nyt täydellisesti.

- Nimet kuuden lisäliettualaisen otsikon alla jäivät huomaamatta: "Įgaliotinis" (valtuutettu), "Įgaliotojas" (valtuuttaja), "Naudos gavėjas" (edunsaaja, vakuutus), "Trečiasis asmuo" (sivuväliintulija/kolmas osapuoli siviiliprosessissa), "Ankstesnis nuomininkas" (edellinen vuokralainen) ja "Naujasis nuomininkas" (uusi vuokralainen). Nimet tunnistetaan nyt täydellisesti.

- Lisezeichen (kirjanmerkki) ODT-asiakirjoissa (`text:bookmark`) kantaa nimensä vapaasti annettuna, usein sen kohdan mukaan nimettynä, johon se osoittaa (esim. "Herr_Mueller_Unterschrift") – lukijalle näkymätön, mutta sanatarkasti tiedostossa. Nimi puhdistetaan nyt mukana.

- Nimet kahdeksan lisäliettualaisen otsikon alla jäivät huomaamatta: "Pareiškėjas" (hakija), "Suinteresuotas asmuo" (vastapuoli riidattomassa menettelyssä), "Ekspertas" (asiantuntija), "Bankroto administratorius" (pesänhoitaja), "Valdybos narys" (hallituksen jäsen), "Direktorius" (toimitusjohtaja), "Palikėjas" (perinnönjättäjä) ja "Įpėdinis" (perijä). Nimet tunnistetaan nyt täydellisesti.

- Nimet seitsemän lisäliettualaisen otsikon alla jäivät huomaamatta: "Liudytojas" (todistaja), "Vertėjas" (tulkki/kääntäjä), "Notaras" (notaari), "Dovanotojas" (lahjoittaja), "Apdovanotasis" (lahjansaaja), "Pirkėjas" (ostaja) ja "Pardavėjas" (myyjä). Nimet tunnistetaan nyt täydellisesti.

- Nimet kuuden lisäliettualaisen otsikon alla jäivät huomaamatta: "Globėjas" (holhooja/huoltaja), "Palikimo administratorius" (pesänhoitaja), "Laiduotojas" (takaaja), "Pagrindinis skolininkas" (päävelallinen), "Nuomotojas" (vuokranantaja) ja "Nuomininkas" (vuokralainen). Nimet tunnistetaan nyt täydellisesti.

- Nimi liettualaisen otsikon "Ieškovas"/"Atsakovas" (kantaja/vastaaja prosessiosapuolena) alla jäi huomaamatta riippumatta siitä, oliko sukunimi samalla yleinen sana (esim. "Vilkas" = susi) vai ei. Nimi tunnistetaan nyt täydellisesti.

- ODT-asiakirjan henkilöhakemistomerkintä (asiahakemiston kirjanmerkki) kantoi nimen toistamiseen omassa lajitteluavaimessaan – näkymättömänä leipätekstissä, mutta sanatarkasti myöhemmin luodussa hakemistossa. Avain puhdistetaan nyt mukana.

- PowerPoint-esityksen diaan nimi ja osion nimi (näkyvillä valintaikkunassa tai dian lajittelunäkymässä) jäivät puhdistamatta, koska molemmat riippuvat attribuuttina elementistä, joka ei ole diatekstiä. Molemmat tunnistetaan nyt.

- Liettualainen yhdysviivalla kirjoitettu kaksoisnimi kuten "Petraitis-Kazlauskas" menetti jälkipuoliskonsa heti, kun sitä edelsi mikä tahansa leipäteksti (vain tekstin alussa se pysyi täydellisenä): sukunimi tunnistetaan nyt täydellisesti myös tällöin.

- Nimi otsikon "Cesionar" (kroatia, sessionaari saatavan siirrossa) alla tuotti väärän hälytyksen, koska itse kenttäotsikko luettiin virheellisesti henkilöksi. Nimi venäläisen otsikon "Цессионарий" (myös sessionaari) alla puolestaan jäi kokonaan huomaamatta. Molemmat tapaukset on nyt korjattu.

- Nimi otsikon "Zedent"/"Zessionar" (saksa, saatavan siirto) alla jäi täysin huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Bauer"). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Darczyńca"/"Obdarowany" (puola, lahjoittaja/lahjansaaja lahjakirjassa) alla jäi huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk" = susi). Samoin romaniankielinen otsikko "Donatar" (lahjansaaja) jäi tavallisen sukunimen kohdalla itse kiinni luultuna nimen osana. Molemmat tapaukset on nyt korjattu.

- Nimi otsikon "Wierzyciel"/"Dłużnik" (puola, täytäntöönpanovelkoja/täytäntöönpanovelallinen tai yleinen velkoja/velallinen) alla jäi huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk" = susi). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Poręczyciel"/"Dłużnik główny" (puola, takaaja/päävelallinen takaussopimuksissa) alla jäi huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk" = susi). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Ubezpieczony"/"Ubezpieczający" (puola, vakuutettu/vakuutuksenottaja vakuutuskirjoissa) alla jäi osittain tai kokonaan huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk" = susi). Samoin nimi otsikon "Osiguranik"/"Osiguravatelj" (kroatia, samat roolit) alla katosi siellä kokonaan etunimeä myöten (esim. "Golub" = kyyhkynen). Molemmat nimet tunnistetaan nyt täydellisesti.

- Nimi otsikon "Pełnomocnik"/"Mocodawca" (puola, valtuutettu/valtuuttaja valtakirjoissa) alla jäi huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk" = susi). Samoin nimi otsikon "Opunomoćenik"/"Opunomoćitelj" (kroatia, samat roolit) alla katosi siellä jopa kokonaan etunimeä myöten. Molemmat nimet tunnistetaan nyt täydellisesti.

- Nimi otsikon "Pozwany" (puola, vastaaja prosessiosapuolena) alla jäi huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk" = susi). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Najmoprimac"/"Najmodavac" (kroatia, vuokralainen/vuokranantaja vuokrasopimuksissa) alla jäi huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Kovač" = seppä). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Pracodawca"/"Pracownik" (puola, työnantaja/työntekijä sopimusosapuolena työsopimuksissa) alla jäi osittain huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Krawiec" = räätäli). Nimi tunnistetaan nyt täydellisesti.

- Unkarilla oli maaluettelossa vain henkilötunnukset ja arvonlisäverotunnus: kaupparekisterinumero (Cégjegyzékszám) tunnistetaan nyt, jos kenttäsana "Cégjegyzékszám" tai lyhenne "Cg." on välittömästi sen edessä – itse numerolla ei ole tarkistusnumeroa.

- Virolla oli maaluettelossa vain Isikukood: Käibemaksukohustuslase number (arvonlisäverotunnus jokaisessa virolaisessa laskussa) tunnistetaan nyt tarkistusnumeron kanssa.

- Latvialla oli maaluettelossa vain Personas kods: juridisten henkilöiden PVN reģistrācijas numurs (yritystunnus jokaisessa latvialaisessa laskussa) tunnistetaan nyt tarkistusnumeron kanssa.

- Sähköposti salatulla sisällöllä (S/MIME- tai PGP/MIME-kuori, `multipart/encrypted`) annettiin ilman minkäänlaista varoitusta näennäisesti täysin tarkastettuna, vaikka sen varsinainen sisältö oli salattu ja siten tarkastamaton. Tällaiset sähköpostit huomauttavat nyt tästä samaan tapaan kuin tarkastamaton liite.

- Malta puuttui maaluettelosta: maltalainen arvonlisäverotunnus (VAT number) tunnistetaan nyt.

- Luxemburg puuttui maaluettelosta: luxemburgilainen arvonlisäverotunnus (n° TVA) tunnistetaan nyt.

- Lauseen alkuun sijoitettu bulgarialainen "Изчакайте" ("Odota!") ilmoitettiin paikannimenä – sama mallin raja kuin aiemmin unkarilaisten, puolalaisten, tšekkiläisten ja muiden kehotusmuotojen kohdalla ilman omaa kielimallia. Väärä hälytys ei enää toistu.

- Nimi otsikon "Zleceniodawca", "Zleceniobiorca" (puola), "Prestator" (romania), "Naručitelj" tai "Izvođač" (kroatia) alla jäi osittain tai kokonaan huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Wilk", "Vuk" = susi, "Vulpe" = kettu, "Sokol" = haukka). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Nadawca" (puola), "Afsender" (tanska) tai "Pošiljatelj" (slovenia) alla jäi osittain tai kokonaan huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Sowa" = pöllö, "Bager" = leipuri, "Volk" = susi). Nimi tunnistetaan nyt täydellisesti.

- Nimi otsikon "Gavėjas" (liettua) tai "Prejemnik" (slovenia) alla jäi osittain tai kokonaan huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Vilkas" = susi). Kuten jo "Primatelj" (kroatia) ja "Modtager" (tanska) kohdalla, nimi tunnistetaan nyt täydellisesti.

- Yleiskirjeen otsikkorivi kuten "To All Staff" tai "To All Employees" tunnistettiin virheellisesti henkilönnimeksi ja poistettiin. Tätä ei enää tapahdu.

- Nimi otsikon "Primatelj" (kroatia) tai "Modtager" (tanska) alla jäi osittain huomaamatta, jos sukunimi oli samalla yleinen sana (esim. "Golub" = kyyhkynen, "Bager" = leipuri). Kuten jo "Odbiorca" (puola) ja "Destinatar" (romania) kohdalla, nimi tunnistetaan nyt täydellisesti.

- Täydellinen nimi tanskalaisen, norjalaisen tai kreikkalaisen asiakirjan allekirjoitusrivillä jäi osittain huomaamatta, kun otsikko "Underskrift" tai "Υπογραφή" oli yksinään nimen yläpuolella – kreikkalaisessa tapauksessa sukunimi jopa tunnistettiin paikannimenä nimen sijaan. Kuten jo "Подпись" (venäjä) kohdalla, nimi tunnistetaan nyt täydellisesti.

- Sivuttain otetun puhelinvalokuvan (tavallinen pystykuva, joka näytetään pystyasennossa vain kuvan kiertomerkinnän avulla) teksti saattoi jäädä tekstintunnistukselta huomaamatta, koska se luki tähän asti raa'at, makuuasentoiset kuvapisteet. Tällaiset valokuvat käännetään nyt oikein päin ennen lukemista – kuten aiemmin jo kasvontunnistuksessa.

- Täydellinen nimi venäläisen, ukrainalaisen tai liettualaisen asiakirjan allekirjoitusrivillä jäi osittain huomaamatta, kun otsikko "Подпись", "Підпис" tai "Parašas" oli yksinään nimen yläpuolella – etunimi tai isännimi jäi pois. Kuten jo "Potpis" (kroatia) kohdalla, nimi tunnistetaan nyt täydellisesti.

- Kasvot sivuttain otetussa puhelinvalokuvassa (tavallinen pystykuva, joka näytetään pystyasennossa vain kuvan kiertomerkinnän avulla) saattoivat jäädä kasvontunnistukselta huomaamatta, koska se tarkisti tähän asti raa'at, makuuasentoiset kuvapisteet. Tällaiset valokuvat käännetään nyt oikein päin ennen hakua.

- Täydellinen nimi kroatialaisen asiakirjan allekirjoitusrivillä jäi osittain huomaamatta, kun otsikko "Potpis" oli yksinään nimen yläpuolella tai kaksoispisteellä sen edessä – etunimi jäi pois, oli se sitten omalla rivillään tai muodossa "Potpis: Etunimi Toinen nimi Sukunimi". Kuten jo "Unterschrift" ja "Signature" kohdalla, nimi tunnistetaan nyt täydellisesti.

- Aviopuolisonimi henkilöoikeudellisten lyhenteiden "verh." (naimisissa oleva) ja "verw." (leski) takana jäi tähän asti kokonaan huomaamatta, olipa se sulkeissa, pilkun jäljessä tai ilman väliä kiinni liimattuna ("Anna Meier (verh. Weber)", "Klaus Bauer (verw.Fischer)") – kuten jo "geb." kohdalla, se tunnistetaan nyt luotettavasti.

- Nimi prokuran allekirjoitusmerkinnän "ppa." takana (esim. yrityksen sähköpostin tai liikekirjeen allekirjoitusrivillä) jäi ammattinimen kaltaisen sukunimen kuten "Bauer" tai "Koch" tapauksessa tähän asti osittain tai kokonaan huomaamatta – kuten jo "gez." kohdalla, se tunnistetaan nyt luotettavasti.

- Puolalaisen henkilötodistuksen (dowód osobisty) numero tunnistettiin vain ilman väliä sarjan ja numeron välissä ("ABS123456"). Näin asiakirja ei kuitenkaan täsmälleen paina tietoa – virallisesti siinä on väli niiden välissä ("ABS 123456"), ja tässä kirjoitusasussa numero jäi tähän asti huomaamatta.

- Animoitu PNG (APNG, esim. lyhyt näyttötallenne tallennettuna PNG:nä GIF:n sijaan) tarkastettiin ja puhdistettiin tähän asti vain ensimmäisen kuvansa osalta ilman, että siitä ilmoitettiin – kuten aiemmin animoidun WebP:n kohdalla, Maskuro ilmoittaa nyt, että jokainen muu kuva jää tarkastamattomana tulokseen.

- Animoitu WebP-kuva (esim. kuvakaappaustyökalusta tai useita kuvia yhdessä tiedostossa sisältävästä chat-sovelluksesta) tarkastettiin ja puhdistettiin tähän asti vain ensimmäisen kuvansa osalta ilman, että siitä ilmoitettiin – kuten aiemmin monisivuisen TIFF:n kohdalla, Maskuro ilmoittaa nyt, että jokainen muu kuva jää tarkastamattomana tulokseen.

- Sloveenialainen yhdysviivalla kirjoitettu kaksoisetunimi ("Ana-Marija Novak") menetti etupuoliskonsa heti, kun tekstissä sitä edelsi leipäteksti – sama virhe kuin aiemmin puolan kielessä. "Ana-" jäi selkotekstiin suojaamattomana, vaikka nimen loppuosa oli jo korvattu.

- Puolalainen yhdysviivalla kirjoitettu kaksoisetunimi ("Anna-Maria Kowalska") menetti etupuoliskonsa heti, kun sitä edelsi tekstissä leipäteksti tai prepositio kuten "z"/"od" – nimen loppuosa korvattiin, "Anna-" jäi selkotekstiin suojaamattomana.

- Kazakstanilaiset kohteliaisuusmuodot "Хабарласыңыз"/"Байланысыңыз" (ottakaa yhteyttä) sekä serbialaiset verbimuodot "Помоћи", "Чекамо" ja "Пишите" ilman omaa kielentunnistusmallia tunnistettiin puhelinlauseissa virheellisesti henkilönnimeksi tai paikaksi.

- Azerbaidžanilainen kohteliaisuussana "Xahiş" (pyyntö/anomus) ilman omaa kielentunnistusmallia tunnistettiin puhelinlauseissa virheellisesti henkilönnimeksi.

- Indonesialaiset ja malaijilaiset kohteliaisuus-/kehotussanat ilman omaa kielentunnistusmallia kuten "Silakan", "Mohon" (indonesia), "Sila" ja "Tolong" (malaiji) tunnistettiin puhelinlauseissa virheellisesti henkilönnimeksi tai paikaksi.

- Uzbekistanilainen kehotusmuoto "Kutamiz" (odotamme) ilman omaa kielentunnistusmallia tunnistettiin puhelinlauseissa virheellisesti paikaksi.

- Turkkilaiset kehotusmuodot ilman omaa kielentunnistusmallia kuten "Arayınız" (soittakaa) ja "Bekliyoruz" (odotamme) tunnistettiin puhelinlauseissa virheellisesti henkilönnimeksi.

- Kehotusmuodot muissa kielissä ilman omaa kielentunnistusmallia (tšekki, slovakki, kreikka) kuten "Zavolejte" (soita), "Prosíme" (pyydämme) ja "Περιμένουμε" (odotamme) tunnistettiin puhelinlauseissa virheellisesti henkilönnimeksi tai paikaksi.

- Unkarilaiset ja puolalaiset kehotusmuodot kuten "Hívjon" (soita), "Kérjük" (pyydämme), "Várjuk" (odotamme), "Zadzwoń" (soita) ja "Czekamy" (odotamme) tunnistettiin puhelinlauseissa virheellisesti henkilönnimeksi tai paikaksi.

- Numeroidussa nimilistassa ilman taulukkomuotoa (esim. "1. Robert Brown", alla "2. Mary Johnson") nimi tietyillä englanninkielisillä sukunimillä (mm. "Brown", "White", "Green", "Black", "Young") jäi kokonaan huomaamatta – kielimalli oli liittänyt seuraavan rivin numeron nimeen, jolloin löydös ei enää koskaan täsmännyt tarkalleen.

- Puolan kielimallissa nimeä edeltävä etunimen alkukirjain ennen sukunimeä (esim. "J. Kowalski", "A. Nowak") jäi tunnistamatta ja puhdistamatta tekstiin – vain sukunimi korvattiin. Muut tarkastetut kielet (mm. saksa, englanti, romania, kroatia, unkari, venäjä) ottivat saman alkukirjaimen mukaan jo aiemmin.

- Henkilönnimi pienellä kirjoitetun arvonimen kuten "dr.", "ing." tai "dipl. ing." takana jäi unkarin, romanian ja kroatian kielessä kokonaan tunnistamatta – paitsi arvonimi, myös koko nimi katosi (esim. "dr. Kovács Béla", "ing. Andrei Popescu", "dipl. ing. Marko Horvat").
- Sloveenialaisissa kokouspöytäkirjoissa pelkkä roolinimike ennen kaksoispistettä (esim. "Tajnik:", "Podpredsednik:", "Poročevalec:", "Predsedujoči:") tunnistettiin virheellisesti henkilönnimeksi heti, kun pöytäkirjan muualla oli jo todellinen puhujan nimi.
- Venäläisissä kokouspöytäkirjoissa pelkkä roolinimike ennen kaksoispistettä (esim. "Секретарь:", "Докладчик:", "Докладчица:") tunnistettiin virheellisesti henkilönnimeksi heti, kun pöytäkirjan muualla oli jo todellinen puhujan nimi.
- Romanialaisissa kokouspöytäkirjoissa pelkkä määräisellä artikkelilla varustettu roolinimike ennen kaksoispistettä (esim. "Secretarul:", "Președintele:", "Vicepreședintele:", "Moderatorul:", "Consilierul:") tunnistettiin virheellisesti henkilönnimeksi – "Președintele" jo yksinään, muut lisäksi heti, kun pöytäkirjan muualla oli jo todellinen puhujan nimi.
- Kroatialaisissa kokouspöytäkirjoissa pelkkä roolinimike ennen kaksoispistettä (esim. "Izvjestiteljica:", "Zapisničar:"/"Zapisnicar:", "Predsjedavajući:") tunnistettiin virheellisesti henkilönnimeksi.
- Puolalainen postilokero-osoite "Skrytka pocztowa" lähettäjä- tai vastaanottaja-otsikon takana (esim. "Odbiorca: Skrytka pocztowa 45") tunnistettiin virheellisesti henkilönnimeksi.
- Kroatialainen postilokero-osoite "Poštanski pretinac" osoiteotsikon "Adresa:" takana (esim. "Adresa: Poštanski pretinac 45", myös numeron lyhenteellä "br.") tunnistettiin virheellisesti henkilönnimeksi.
- Paikka ilman muuta otsikointia norjalaisessa leipätekstissä (esim. "Anna Hansen bor i Oslo") jäi tunnistamatta – oma kielimalli nimeää paikat siellä useimmiten omalla, tähän asti kohdistamattomalla etiketillä tavallisen "LOC":n sijaan.
- Päivämäärä ISO-järjestyksessä vuosi-kuukausi-päivä yhdysviivalla tai pisteellä (esim. "2024-12-31") jäi joissakin kielissä kokonaan tunnistamatta päivämääräksi – huomattavimmin liettuan kielessä, jossa viralliset kirjeet ilmoittavat päivämäärät useimmiten tässä järjestyksessä.
- Unkarilainen arvonlisäverotunnus (közösségi adószám) sen virallisesti yhtä pätevässä, ilman erottimia kirjoitetussa 11-numeroisessa muodossa (esim. "12345678123" muodon "12345678-1-23" sijaan) jäi tunnistamatta.
- Puolalainen verotunnus NIP erottimilla ryhmittelyssä 3-2-2-3 (esim. "856-73-46-215", kuten se on tavallista yritysten ja yksityisyrittäjien laskuissa) jäi tunnistamatta – vain luonnollisten henkilöiden ryhmittely 3-3-2-2 osui.
- Yrityksen nimi slovakialaisen kenttäotsikon "Zamestnávateľ:" tai "Názov zamestnávateľa:" (työnantaja/yritys) alla jäi tunnistamatta.
- Yrityksen nimi romanialaisen kenttäotsikon "Angajator:" tai "Denumire angajator:" (työnantaja/yritys) alla jäi tunnistamatta.
- Yrityksen nimi unkarilaisen kenttäotsikon "Cég:" tai "Munkáltató:" (yritys/työnantaja) alla jäi tunnistamatta.
- Yrityksen nimi puolalaisen kenttäotsikon "Pracodawca:" tai "Nazwa firmy:" (työnantaja/yritys) alla jäi tunnistamatta.
- Yrityksen nimi sloveenialaisen kenttäotsikon "Podjetje:" tai "Delodajalec:" (yritys/työnantaja) alla jäi tunnistamatta.
- Yrityksen nimi kroatialaisen kenttäotsikon "Tvrtka:" tai "Poslodavac:" (yritys/työnantaja) alla jäi tunnistamatta.
- Kirjoitettu rahasumma pienellä kirjoitetulla valuutalla (esim. "500 euro") jäi tunnistamatta, vain isolla alkukirjaimella kirjoitettu ("Euro") osui.
- Sukunimi sanojen "Schwager"/"Schwägerin" (lanko/käly) takana (esim. "Der Schwager Bauer erhält die Erbschaft.") jäi tunnistamatta.
- Turkkilaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "34000 İstanbul İstiklal Caddesi No: 45") talonumero jäi puhdistamatta.
- Slovakialaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "831 01 Bratislava Hlavná 15") talonumero jäi puhdistamatta.
- Syntymämaa ilman muuta otsikointia kroatialaisessa lomakekentässä (esim. "Zemlja rođenja: Njemačka") jäi tunnistamatta.
- Syntymämaa ilman muuta otsikointia liettualaisessa lomakekentässä (esim. "Gimimo valstybė: Vokietija") jäi tunnistamatta.
- Syntymä- tai asuinmaa ilman muuta otsikointia puolalaisessa lomakekentässä (esim. "Kraj: Niemcy") jäi tunnistamatta.
- Kansalaisuus- tai asuinpaikka ilman muuta otsikointia sloveenialaisessa lomakekentässä (esim. "Državljanstvo: Nemčija") jäi tunnistamatta.
- Asuinmaa ilman muuta otsikointia norjalaisessa lomakekentässä (esim. "Bosted: Tyskland") jäi tunnistamatta.
- Uusi asetussivu "Ilmoitukset" (aiemmin osio kohdassa "Ohjelma"): kolme tehtäväpalkin ilmoitusta (esikatselu valmis, käsittely valmis, päivitys ladattu) ovat nyt omalla paikallaan.
- Uutta: Tuloksen voi lisäksi tallentaa rinnalle pelkkänä tekstitiedostona (.txt) tai .md-päätteellä – jatkokäsittelyä varten tekoälyssä tai toisessa ohjelmassa.
- Kroatialaisessa yhteystiedossa otsikolla "Osoba za kontakt"/"Kontakt osoba" (esim. "Osoba za kontakt: Golub Marko") nimi jäi kokonaan tunnistamatta, jos sukunimi oli samalla yleinen substantiivi (Golub = "kyyhkynen").

- Romanialaisessa yhteystiedossa otsikolla "Persoana de contact"/"Persoană de contact" (esim. "Persoana de contact: Lup Ion") nimi jäi kokonaan tunnistamatta, jos sukunimi oli samalla yleinen substantiivi (Lup = "susi") ja etunimi hyvin lyhyt ja yleinen.

- Puolalaisessa yhteystiedossa otsikolla "Osoba kontaktowa"/"Osoba do kontaktu" (esim. "Osoba kontaktowa: Wilk Adam") sukunimi jäi tunnistamatta, jos se oli samalla yleinen substantiivi (Wilk = "susi", Zielony = "vihreä").

- Romanialaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "010061 București Strada Victoriei 30") talonumero jäi puhdistamatta.
- Serbialaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "11000 Beograd Bulevar Kralja Aleksandra 73") talonumero jäi puhdistamatta.
- Kreikkalaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "104 32 Αθήνα Ερμού 15") talonumero jäi puhdistamatta.
- Sloveenialaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "1000 Ljubljana Slovenska cesta 58") postinumero jäi puhdistamatta.
- Liettualaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "LT-01100 Vilnius Gedimino pr. 9") postinumero jäi täysin puhdistamatta.
- Unkarilaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "1052 Budapest Kossuth Lajos utca 12") postinumero jäi puhdistamatta.
- Sukunimi sanan "Erben" (perilliset) takana (esim. "Die Erben Wagner erhielten die Mitteilung fristgerecht.") jäi perintö-/jäämistöasiayhteydessä lähes aina tunnistamatta.
- Sukunimi sanan "Geschwister" (sisarukset) takana (esim. "Die Geschwister Bauer wohnen in Linz.") jäi tähän asti lähes aina tunnistamatta – toisin kuin sanoissa "Familie"/"Ehepaar", tämä osui paitsi ammattinimen kaltaisiin nimiin (Koch, Bauer, Richter), myös mihin tahansa sukunimeen tässä kohdassa.
- Sukunimi sanojen "Ehepaar" tai "Eheleute" (aviopari) takana (esim. "Das Ehepaar Koch zieht um.") jäi tunnistamatta, jos se oli samalla yleinen substantiivi tai ammattinimike (Koch, Bauer, Richter).
- Tavallinen tilaus-, toimeksianto- tai artikkelinumero verotunnukselle tai sosiaaliturvatunnukselle tyypillisessä ryhmittelykaavassa (esim. "030 4471 2298") mustattiin virheellisesti sellaisena ilman mitään siihen liittyvää otsikkoa.
- Kuitti-/tapausnumero muodossa "vuosi/juokseva numero" (esim. laskussa "Rechnung Nr. 4/2024/778899") mustattiin puhelinnumerotunnistuksen toimesta virheellisesti puhelinnumerona.
- Nimi sanojen "Herr"/"Frau" takana monisanaisella akateemisella arvonimiketjulla edessä ("Herr Dr. med. Weber", "Herr Prof. Dr. Krause") jäi tähän asti kokonaan suojaamattomaksi – tähän asti tunnistettiin vain yksittäinen arvonimisana puhuttelun ja nimen välissä.
- Tuomioistuimen asianumero klassisessa muodossa jaosto-/senaattilyhenteellä ("4 Ca 1523/24", "Az.: 7 O 234/25") jäi tähän asti kokonaan suojaamattomaksi – myöskään tavallista lyhennettä "Az."/"Gz." ei tunnistettu kirjoitetun otsikon ohella.
- Luottokorttinumero, jonka rivinvaihto katkaisi keskeltä sen nelinumeroista ryhmittelyä – esim. kapeassa taulukkosarakkeessa –, jäi tähän asti kokonaan suojaamattomaksi.
- Verotunnistenumero, jonka rivinvaihto katkaisi keskeltä ryhmittelyä – esim. kapeassa taulukkosarakkeessa tai lomakekentässä –, jäi tähän asti kokonaan suojaamattomaksi.
- Sosiaaliturvatunnus, jonka rivinvaihto katkaisi keskeltä ryhmittelyä – esim. kapeassa taulukkosarakkeessa –, jäi tähän asti kokonaan suojaamattomaksi, ei edes osittain korvattuna.
- Talonumero vaihteluvälillä kuten "12a-14b" tai "3-5" korvattiin vain puoliksi – toinen osa yhdysviivan jäljessä jäi avoimeksi tulokseen.
- Ajoneuvon runkonumero (FIN/VIN), jonka rivinvaihto, väli tai yhdysviiva katkaisi keskeltä sen 17:ää merkkiä – esim. kapeassa taulukkosarakkeessa tai ajoneuvon rekisteriotteen kentässä –, jäi tähän asti kokonaan suojaamattomaksi.
- Kirje-/sähköpostipuhuttelu kuten "Liebe Anna!" tai "Lieber Hans" – ilman pilkkua nimen jäljessä, yleisin muoto rennoissa sähköposteissa – jätti nimen täysin suojaamattomaksi, myös täydessä asiakirjassa leipätekstin ja alle jäävän tervehdyksen kanssa.
- Sama aukko kohtasi myös rennot chat-/sähköpostipuhuttelut "Hallo Anna!", "Hi Anna!", "Hey Anna!" ja "Servus Anna!" ilman pilkkua – nimi jäi myös täysin suojaamattomaksi.
- Pelkkä allekirjoituslohko, joka alkaa suoraan sanalla "MfG" tai "Herzlichst" – esim. leikepöydältä kopioituna ilman edeltävää lausetta – jätti sen alla olevan nimen täysin suojaamattomaksi.
- Kenttä usealla henkilöllä, esim. "Angehörige: Kaczmarek, Piotr (Sohn), Kaczmarek, Anna (Ehefrau)", sulautti molemmat nimet sulkumerkinnän kera yhdeksi ainoaksi, liian pitkäksi löydökseksi – toinen nimi jäi osittain suojaamattomaksi tulokseen.
- Katu ilman "-straße"/"-weg"-jälkiliitettä – kuten maaseudulla on tavallista, esim. "Am Marktplatz 5" tai "Im Grund 12" – jäi tunnistamatta, jos sitä seurasi postinumero-paikkakunta-rivi, esim. ilmoittautumistodistuksessa: "Neue Anschrift: Am Weidengarten 17, 54295 Trier" menetti kadun täysin, vain postinumero poistettiin.
- Nimi yhdistetyn, vinoviivalla varustetun kenttäotsikon takana (esim. "Name/Vorname: Bauer Klaus") jäi osittain tunnistamatta – monimerkityksellinen sukunimi kuten "Bauer" jäi ilman kenttänäyttöä huomaamatta. Sama aukko kohtasi yhdistelmäkenttiä kuten "PLZ/Ort: 04109 / Leipzig". Sama koski yhdistelmäkenttiä kirjoitetulla yhdyssanalla vinoviivan sijaan, esim. "Vor- und Nachname: Bauer Klaus" tai "Nachname bzw. Vorname: …".
- Syntymäaika muodossa "Datum der Geburt: …" ja kuolinpäivä muodossa "Todesdatum: …" tai "Datum des Todes: …" jäivät tunnistamatta – vain "Geburtsdatum: …" tai "Sterbedatum: …" osuivat.
- Avioitumispäivä muodossa "Datum der Heirat: …" tai "Datum der Hochzeit: …" jäi tunnistamatta – vain "Hochzeitsdatum: …", "Heiratsdatum: …" ja "Datum der Eheschließung: …" osuivat, vaikka avioero-, kansalaistamis- ja parisuhteen rekisteröintipäivä tunsivat saman "Datum der X" -muodon jo pitkään.
- Avioeropäivä muodossa "Datum der Scheidung: …" jäi tunnistamatta – vain "Scheidungsdatum: …" ja jälkiasetettu verbimuoto osuivat, vaikka kansalaistamis- ja parisuhteen rekisteröintipäivä tunsivat saman "Datum der X" -muodon alusta alkaen.
- Parisuhteen rekisteröintipäivää ei tähän asti tunnistettu lainkaan – ei otsikolla ("Verpartnerungsdatum: …", "Datum der Lebenspartnerschaft: …") eikä leipätekstissä ("… wurden am … verpartnert"). Se korvataan nyt syntymä-, avioitumis-, avioero- ja kansalaistamispäivän tapaan omana tietolajinaan.
- Kansalaistamispäivää ei tähän asti tunnistettu lainkaan – ei otsikolla ("Einbürgerungsdatum: …") eikä leipätekstissä ("… wurde am … eingebürgert"). Se korvataan nyt syntymä-, avioitumis- ja avioeropäivän tapaan omana tietolajinaan.
- Avioeropäivää ei tähän asti tunnistettu lainkaan – ei otsikolla ("Scheidungsdatum: …") eikä leipätekstissä ("Die Ehe wurde am … geschieden"). Se korvataan nyt syntymä-, kuolin- ja avioitumispäivän tapaan omana tietolajinaan.
- Avioitumispäivä sukuselvitysten avioliittomerkin "⚭" takana ilman otsikointia jäi tunnistamatta, vaikka syntymä- ja kuolinpäivä tunnistettiin samalla rivillä tähden ja ristin yhteydessä jo aiemmin – nyt myös avioitumispäivä tunnistetaan.
- Kuolinpäivä kuolinilmoituksen ristin takana ilman otsikointia ("*03.06.1940 †21.11.2023") jäi tunnistamatta, vaikka syntymäpäivä sitä edellä sukuselvitysten tähden yhteydessä tunnistettiin jo aiemmin – nyt myös kuolinpäivä tunnistetaan.
- Sukunimi ennen etunimeä otsikko-/tikettirivin lopussa asiatekstin ja erotinviivan edeltäessä ("Betreff: Reklamation - Bauer, Anna") jäi ammattinimen kaltaisen sukunimen tapauksessa tunnistamatta – nyt se tunnistetaan.
- Hakija- ja anomusnumerot otsikkonsa takana ("Bewerbernummer: 4471829", "Antragstellernummer: 7654321") jäivät kokonaan tunnistuksen ulkopuolelle – nyt ne tunnistetaan.
- Korvaaminen ei enää mustaa, kun luettavalle paikkamerkille ei ole tilaa – liian pieni paikkamerkki kirjoitetaan nyt pienemmällä sen sijaan, että siitä tulisi tyhjä palkki, kunhan tilaa ylipäätään jää. Uutta lisäksi: onko kuvassa oleva löydöskohta (kirjeen otsikko, skannauksen tausta) otsikoitu vai vain mustattu, voidaan nyt asettaa muusta tulostyypistä riippumatta. Ja löydöskohta kuvassa, joka poistetaan kokonaan, otsikoitiin ikään kuin kuva pysyisi paikallaan – paikkamerkki oli vaaleana pohjalla, jota ei koskaan mustattu, ja katosi näin näkymättömiin nyt valkoiselle paperille.
- Löydöskohta **säilytettävässä** kuvassa mustattiin korvattaessa aina mustavalkoisena, riippumatta valitusta ulkoasusta (luokkavärit, sateenkaari …) – näkyi murtumana värikkäiden etikettien ja leipätekstin sekä mustien palkkien välillä kirjeen otsikossa. Kuvan pohja seuraa nyt samaa väriä kuin vieressä oleva paikkamerkki.
- Ajoneuvon tunnistenumeron (FIN/VIN) tunnistus merkitsi ehdoitta jokaisen 17-numeroisen alfanumeerisen koodin ilman I/O/Q runkonumeroksi – myös tilaus-, sarja- ja lisenssiavainnumerot, joilla sattuu olemaan sama muoto. Se laskee nyt vain kontekstisanan kanssa lähellä ("FIN", "VIN", "Fahrgestell", "Chassis" tms.).
- Tiketti-/kalenterijärjestelmissä nimentunnistus veti sanojen "Assigned to"/"Closed by" tms. jälkeen mukaan seuraavan kenttäsanan, jos se seurasi samalla rivillä suoraan ilman erotinta ("Assigned to Max Mustermann Priority High" muuttui muotoon "Max Mustermann Priority"). Git-committien otsikkoriveillä nimentunnistus veti samoin mukaan **seuraavan** trailer-avaimen, jos kaksi riviä liittyi toisiinsa vain yhdellä välillä rivinvaihdon sijaan ("Author: julia bergmann Reviewed-by: …" muuttui muotoon "julia bergmann Reviewed-by"). Molemmat jarrut on nyt lisätty.
- Nimi sanojen "p.A.", "zH"/"zHd", "i.A."/"i.V." ja "geb." takana veti mukaansa suoraan seuraavan osastosanan, jos se seurasi samalla rivillä ilman erotinta ("p.A. Max Mustermann Buchhaltung" muuttui muotoon "Max Mustermann Buchhaltung", "i.A.Max Mustermann Vertrieb" muotoon "Max Mustermann Vertrieb"). Sama jarru kuin "Assigned to"/Git-trailereissa on nyt lisätty myös tähän.
- Otsikoitu IBAN suoraan BIC-, BLZ- tai SWIFT-rivin yläpuolella veti sen otsikon mukaan omaan löydökseensä, koska "BIC" ja "BLZ" itsessään näyttivät toiselta numerolohkolta – rivistä "IBAN: DE89 … 0130 00" ja sen alla olevasta rivistä syntyi yksi, liian pitkälle ulottuva löydös, ja seuraavan rivin otsikko katosi puhdistuksen mukana. Kyseessä oli lähes jokainen pankkiyhteys, jossa IBAN ja BIC olivat allekkain.
- Löydöspaneeli kertoo nyt, **missä** on paikkamerkki, jota se ei löydä sivulta. Kaksi tapausta ilmoitti tähän asti vain "ei löydy", vaikka korvaus tapahtui: kun paikkamerkki on näkymättömässä oheistekstissä – esim. linkin viiteosoitteessa, huomautuksessa tai lomakekentässä –, rivi kertoo sen nyt omana tietona ("oheistekstissä"), ja klikkaus selittää sen. Ja jos paikkamerkki kirjoitettiin tilan puutteen vuoksi lyhennettynä ("[N382]" muodon "[NAM382]" sijaan), klikkaus hyppää nyt pitkältä riviltä lyhennemuodon kohtaan ja kertoo uudelleennimeämisestä; kohdistus lomittaa molemmat rivit tätä varten nimenomaisesti yhteen.
- Jos sama korvausarvo esiintyy asiakirjassa useita kertoja, jokainen seuraava klikkaus paneelirivillä hyppää kehämäisesti seuraavaan löydöskohtaan – myös sivurajojen yli; tilarivi laskee mukana ("löydöskohta 2/4"), ja juuri kohdistettu kohta on korostetummin kehystetty kuin muut. Ja jos paikkamerkki on vain löydöslistassa mutta ei missään asiakirjassa (koska kohta sulautui päällekkäiseen korvaukseen), tilarivi kertoo tämän nyt sen sijaan, että klikkaus jäisi hiljaa vaikutuksetta.
- Lyhennetty etunimi sanojen "an" tai "für" takana tunnistetaan nyt luotettavasti nimeksi – "Überweisung an M. Wagner" ja "Rechnung für M. Wagner" jäivät tähän asti usein puhdistamatta, vaikka sama nimi toisella otsikolla edessä (esim. "Zahlungsempfänger:") jo löytyi. Erityisesti tiliotteiden ja kirjausrivien kohdalla.
- "Angeklagter"/"Angeklagte"/"Beschuldigter"/"Beschuldigte" lasketaan nyt nimikentäksi: jos rikosoikeudellisissa asiakirjoissa nimi oli suoraan jonkin näistä otsikoista jäljessä, se jäi tähän asti noin puolessa tarkastetuista nimistä kokonaan tunnistamatta – ei etu- eikä sukunimeä.
- Löydöspaneelista klikattu kohta kehystetään nyt sinisenä keltaisen korostuksen sijaan – värillisillä liikennevalopinnoilla haun keltainen väri ei erottunut. Lisäksi klikkaus löytää nyt myös monisanaiset korvausarvot (keksityt nimet, naamioidut numerot): tähän asti se jäi tällaisilla riveillä vaikutuksettomaksi, koska löydöskohtaa haettiin vain sana kerrallaan.
- Adoptio-, kasvatti- ja isä-/äitipuolet ("Adoptivvater", "Pflegemutter", "Stiefvater" ja muut) tunnistetaan nyt nimikentäksi, nimi jäi aiemmin puhdistamattomana läpi
- Numeroita täynnä olevia taulukoita ja luetteloita ei enää hylätä virheellisesti: kun lyhyt luku (esim. puhelinnumeroksi luettu asiakasnumeron osa) korvattiin, loppuprosessi ilmoitti saman numerosarjan jäljellä olevana tietona myös silloin, kun se sattui esiintymään muualla vain sattumalta täysin toisessa numerossa – eikä tulosta silloin syntynyt lainkaan. Luku lasketaan nyt jäänteeksi vain siellä, missä se esiintyy omana lukunaan.
- Väestörekisteriasiakirjat: "Vater:"/"Mutter:" tunnistetaan nyt nimikentäksi, vanhemman nimi jäi aiemmin puhdistamattomana läpi
- Muut sukulaisuusroolit ("Pate", "Großvater/-mutter", "Ehepartner", "Lebenspartner", "Onkel", "Tante") tunnistetaan nyt nimikentäksi, nimi jäi aiemmin puhdistamattomana läpi
- Saksalainen pankin tunnusnumero (BLZ) tunnistetaan nyt myös virallisesti ryhmiteltynä ("370 400 44", "370.400.44", "370-400-44", "370/400/44"), ei enää vain kahdeksana yhtenäisenä numerona.
- Saksalainen eläkevakuutusnumero tunnistetaan nyt myös pisteellä, yhdysviivalla tai vinoviivalla viiden lohkon välissä ("65-170839-J-08-8", "65.170839.J.08.8"), ei enää vain välilyönnillä.
- Pääikkuna avautuu nopeammin: tunnistuskirjastot (Presidio kielimallipohjineen) ladattiin tähän asti jo ikkunan rakentamisen yhteydessä – Windowsissa noin neljä sekuntia, ennen kuin mitään edes näkyi. Ne latautuvat nyt kokonaan taustalla; "Puhdista"-painike vapautuu kuten ennenkin vasta, kun kaikki on valmiina.
- Office-asiakirjat runsailla kuvilla tai videoilla kirjoitetaan nopeammin: jo pakatut mediat tallennetaan tulospakettiin sellaisenaan sen sijaan, että ne pakattaisiin turhaan toiseen kertaan – tämä ei aiemmin säästänyt yhtäkään tavua ja teki JPEG-tiedostoista pikemminkin suurempia.
- Taulukkolaskentaohjelmat ja muut asiakirjat monista pienistä tekstiyksiköistä tarkastetaan nopeammin: kielentunnistus käsittelee nyt asiakirjan kaikki solut ja kappaleet yhdellä ajolla erikseen käsittelyn sijaan – todistetusti samoilla löydöksillä (400 solua: noin 4,7:stä 2,5–3,5 sekuntiin).
- Listamaiset PDF-sivut (hakemistot, positioluettelot) ovat paikkamerkkien asettamisessa selvästi nopeampia: tilanhaku otsikkoa kohden kulki tähän asti sivun kaikkien sanojen läpi – nyt vain rivin lähiympäristön läpi, todistetusti samalla tuloksella (sivulla, jolla on 300 otsikkoa, noin kuusitoista kertaa nopeampi).
- Kuvarikkaat asiakirjat säästävät useita tarpeettomia työvaiheita kuvaa kohden: kasvojen ja koodien laskenta PDF-sivuilla ei enää pura sivukuvaa kahteen kertaan, metatietojen tarkastus ei enää pura puhdasta kuvaa lainkaan, pikselöidyt kuvat kirjoitetaan nyt tavallisella PNG-pakkauksella hitaimman sijaan (sama koko, kolmasosa ajasta), ja ilman asetettua vesileimaa koko PDF:n tarpeeton uudelleenkirjoitus lopuksi jää pois.
- Skannatut PDF:t tekstintunnistus päällä käsitellään selvästi nopeammin: jokainen sivu renderöitiin tähän asti kahdesti täydellä resoluutiolla (kerran lukua, kerran rasterointia varten) – kuva käytetään nyt uudelleen. Ja Windowsilla/Linuxilla tekstintunnistus lukee suuren skannauksen kaistaleet yhdellä ajolla erillisen ohjelmakäynnistyksen sijaan kutakin kaistaletta kohden.
- Suuret asiakirjat puhdistuvat selvästi nopeammin: jo löydettyjen arvojen vertailu kasvoi tähän asti löydösten määrän mukana (64 kt:n tekstilohko maksoi suuren tiedoston lopussa noin sekunnin pelkästään tähän, nyt kuudeskymmenesosan), ja yritysten oikeushenkilömuotojen haku kulki kaikkien noin 280 luettelomuodon kanssa jokaisen tekstikohdan läpi (nyt noin kaksikymmentä kertaa nopeampi, todistetusti samoilla löydöksillä).
- Nimi suoraan sanojen "Beste Grüße"/"Beste Wünsche" jälkeen ilman edeltävää tekstiä tai välimerkkiä jäi kokonaan tunnistamatta – pelkkä allekirjoituslohko ilman edeltävää leipätekstiä jätti nimen jäljettömiin.
- Osoitekenttä asiakirjan alussa ammattinimen kaltaisella sukunimellä ("Bauer Anna", "Koch Stefan" ensimmäisenä rivinä kadun ja paikkakunnan yläpuolella) jäi tähän asti osittain tunnistamatta tai luokiteltiin paikaksi henkilön sijaan – ilman edeltävää lausetta kielimallilta puuttui lauserakenne, joka muuten antaa tunnistaa "Bauer"-sanan nimenä eikä ammattina.
- Nimi allekirjoitusmerkinnän "gez." takana ammattinimen kaltaisella sukunimellä ennen etunimeä ("gez. Bauer Anna" päätöksen tai tuomion lopussa) jäi tähän asti vajaasti tunnistetuksi – vain etunimi löytyi, sukunimi katosi jäljettömiin.
- Nimi suoraan asiakas-, sopimus- tai vastaavan tunnusnumeron jäljessä ilman omaa riviä ("Vertragsnummer 55219 Bauer Anna", "Kundennr. 4711 Bauer Anna") jäi ammattinimen kaltaisen sukunimen tapauksessa tähän asti osittain tai kokonaan tunnistamatta.
- macOS:n valikkopalkin kuvake on nyt malline, joka mukautuu vaalean ja tumman tilan mukaan kuten naapurikuvakkeet – kahdella lävistetyllä palkilla se pysyy silti tunnistettavana Maskurona. Kun leikepöydän vahti on käynnissä, sitä osoittaa erillinen piste kilven kärjessä.

- Klikkaus löydöspaneelissa johtaa nyt myös anonymisoivassa toiminnassa löydöskohtaan: sivun vaihto, vieritys kuvaan, keltainen korostus. Tähän asti klikkaus jäi siellä vaikutuksettomaksi, koska se piti paikkamerkkejä yhä numerottomina – siitä lähtien kun jokaisella löydöskohdalla on oma numeronsa, kohta on yksiselitteinen. Vain todella numerottoman paikkamerkin kohdalla tilarivi selittää edelleen, miksi hyppykohdetta ei voida määrittää.
- Korjaus-editorin ensimmäinen tallennus (Ctrl+S tai levykepainike) kysyy nyt sijaintia kuten "Tallenna nimellä …" – valmiiksi täytettynä alkuperäisen kansiolla ja tulosnimellä. Tähän asti tiedosto päätyi äänettömästi alkuperäisen viereen. Jos sijainti on jo valittu aiemmin tilarivin kautta, kysymystä ei toisteta; jokainen seuraava tallennus kirjoittaa kuten ennenkin saman tiedoston jatkoksi.
- Jos tallennusta edeltävä turvatarkastus ilmoittaa epäilyttävästä kohdasta, "Takaisin tarkastukseen" johtaa nyt sinne: ensimmäinen löydöskohta vierittyy kuvaan ja kehystetään punaisella, tilarivi nimeää sen. Tähän asti jäätiin yksin sivunumeron ja pistekoordinaattien kanssa. Pääikkunasta tämä avaa editorin kyseiseen kohtaan. Myös huomautuksessa poikkeavasta sivumäärästä painike johtaa nyt perille – ensimmäiselle sivulle, joka on vain toisessa kahdesta asiakirjasta.
- Kun esikatselu vaihdetaan "Rinnakkain kahdessa sarakkeessa" -tilaan, ikkuna kasvaa nyt itsestään sopivaksi molemmille radoille – tähän asti ne puristuivat vanhaan leveyteen, kunnes niitä vedettiin itse. Levennys tapahtuu korkeintaan näytön reunaan asti eikä koskaan kavenna takaisin; itse vedetty leveys pysyy paikallaan.
- Sukunimi ja etunimi erillisissä taulukkosarakkeissa (esim. "Nachname | Vorname" ilmoittautumisvahvistuksessa tai CSV-viennissä) jäivät avoimeksi – jokainen solu näytti tunnistukselle yksinään miltä tahansa sanalta ilman nimiyhteyttä. Tunnistetaan nyt.
- Nimi ja etunimi EU-korttiajokortin kääntöpuolella jäivät avoimeksi – ne ovat siellä virallisten kenttäkoodien "1." ja "2." takana saksankielisen sanan sijaan, ja juuri se jätti ne tunnistamatta. Tunnistetaan nyt, kun ajokortin numero (kenttäkoodi "5.") on vierellä.
- Ajoneuvon haltijan etunimi rekisteröintitodistuksessa jäi avoimeksi – se on siellä virallisen kenttäkoodin "C.1.2" takana saksankielisen sanan kuten "Vorname" sijaan, ja juuri se jätti sen tunnistamatta. Sukunimi ja etunimi kenttäkoodien C.1, C.1.1 ja C.1.2 alla tunnistetaan nyt.
- Passin tai henkilötodistuksen koneluettavan alueen (MRZ) ensimmäinen rivi jäi avoimeksi – se kantaa nimen muodossa "SUKUNIMI<<ETUNIMI" ja luisui läpi myös uuden tarkistusnumerorivin MRZ-tunnistimen kanssa. Löydös lasketaan nyt vain, jos välittömästi vieressä on tarkistusnumeroltaan kelvollinen toinen MRZ-rivi – itse nimirivillä ei ole omaa tarkistusnumeroa.
- Passin tai henkilötodistuksen koneluettavan alueen (MRZ) toinen rivi jäi kokonaan tunnistamatta – se sisältää passinumeron, syntymä- ja vanhentumispäivän selkotekstinä, mutta ei osunut yhteenkään olemassa olevaan tunnistimeen. Oma tunnistin tarkistaa nyt neljä ICAO-tarkistusnumeroa.
- Rekisterikilpi ilman yhtäkään väliä otsikkoon jäi avoimeksi – "KennzeichenM-AB1234" tai "KFZ-KennzeichenM-AB1234" eivät tunnistuneet lainkaan, koska taustalla oleva kilven tarkistus edellyttää ei-sanamerkkiä ennen kilpeä. Koski ajoneuvotietoja, joissa kenttäsanan ja kilven välissä ei ole väliä.
- Puhelinnumero ilman yhtäkään väliä otsikkoon jäi avoimeksi – "Handynummer0171/2345678" tai "Tel0171/2345678" eivät tunnistuneet lainkaan, koska taustalla oleva puhelinnumerotarkistus edellyttää väliä tai välimerkkiä ennen numeroa. Koski yhteystietoja, joissa kenttäsanan ja numeron välissä ei ole väliä.
- Syntymänimi lyhenteen "geb." takana jäi kokonaan tunnistamatta – "Julia Bergmann (geb. Weber)" löysi vain "Julia Bergmann", piste lyhenteessä "geb." sai kielimallin ohittamaan seuraavan nimen kokonaan. Koski henkilötietoja syntymänimellä suluissa tai pilkun jäljessä.
- Etunimi lainausmerkeissä olevan lempinimen edellä jäi avoimeksi, kun puhuttelu ja arvonimi olivat yhdessä edessä – "Herr Dr. Klaus "KP" Peters" antoi vain "Peters", "Klaus" jäi luettavaksi. Koski allekirjoituksia ja yhteystietoja arvonimellä ja lempinimellä.
- Nimi pisteettömän lyhenteen "zH"/"zHd" (huomioon) takana jäi kokonaan tunnistamatta – toisin kuin pisteellisen "z.Hd." kohdalla, puuttuva lauserakenne vei nimen mukanaan. Koski osoitteita ilman pistettä lyhenteessä.
- Nimi sanan "p.A." (osoitteen kautta) takana jäi kokonaan tunnistamatta – piste lyhenteessä sai kielimallin ohittamaan nimentunnistuksen kokonaan. Koski laskuja ja hakemuksia yhteisellä osoitteella.
- Nimi pisteettömästi kiinni liimatun "i.A."/"i.V." (toimeksiannosta/sijaisena) takana jäi kokonaan tunnistamatta, esim. "i.A.Robert Lang" ilman väliä – sama lauserakennevirhe kuin sanan "p.A." kohdalla. Koski edustustapausten allekirjoitusrivejä ja sähköpostiallekirjoituksia.
- Pelkkä läsnäololuettelo luettelomerkeillä ilman muuta tietoa ("- Max Mustermann", myös pisteellä rivin lopussa) menetti kaikki nimet samalle jarrulle, jonka piti oikeasti suojata vain asialuetteloita kuten "- Farbe: Blau". Tällaiset listat tunnistetaan nyt.
- Tiedostot, joita ei enää saanut puhdistettua, voidaan taas puhdistaa. Arvo, joka oli jo korvattu tunnistuksen kautta, saatettiin löytää uudelleen omasta, jo korvatusta merkinnästä kuten "[SVNR1]" – loppukoe hylkäsi silloin moitteettomasti puhdistetun tiedoston. Lisäksi puhelinviite CSV-taulukossa poistetaan nyt mukana, ja jos haku rajataan yksittäisiin lajeihin, se toimii nyt yhtenäisesti kaikkialla asiakirjassa – myös kuvan vaihtoehtoisessa tekstissä, Excel-otsikkorivillä, valintaluettelossa tai HTML-attribuutissa.
- Nimi sähköpostin otsikkorivin "To:" (tai "To" ilman kaksoispistettä) takana jäi tunnistamatta, koska vieras kielimalli luki koko rivin yhtenä ainoana huomaamattomana löydöksenä ja nielaisi siinä olevan nimen kokonaan – toisin kuin sanojen "Cc:", "Bcc:" tai "From:" edessä samalla nimellä. Nimi sanan "To" takana löytyy nyt luotettavasti.
- Hääpäivää ei voinut käsitellä omissa säännöissä päivämääränä ("siirrä" hylättiin viestillä "vain päivämäärille") – se puuttui löydöslajien ryhmäjaosta, jolloin sitä ei voinut kytkeä pois kohdasta "Mitä etsitään" – ja se sai kuolinpäivän tapaan lyhyen tunnuksen sijaan täyden sanamuodon paikkamerkiksi. Korjattu kaikkiin kuuteen lyhenne-/otsikkotaulukkoon.
- Esikatselussa tietoisesti poisvalittu arvo saattoi silti tulla mustatuksi toisaalla: jos esim. sähköpostiosoite valittiin pois, osoite itse jäi näkyviin, mutta sen paikallinen osa ilman verkkotunnusta korvattiin heti, kun se osui yhteen laajemmin valitun henkilön johdetun käyttäjätunnuksen kanssa ("anna.musterfrau@beispiel.de" nimen "Anna Musterfrau" vieressä). Poisvalittu sanamuoto on nyt kiellettyä koko asiakirjassa riippumatta siitä, mistä löydöslajista se on peräisin.
- Syntymäaika jäi tunnistamatta, kun perhekirja- tai väestörekisteriote esitti sen yhteisen otsikon alla syntymäpaikan kanssa ("Geburtsdatum, Geburtsort: 19.11.1982, Steyr") – toinen kenttäsana sanan "Geburtsdatum" ja päivämäärän välissä jätti tunnistuksen tähän asti kokonaan huomiotta.
- Jo tunnistettu puhelinnumero jäi lyhennetyssä vahvistusmuodossaan luettavaksi, jos se mainittiin asiakirjan muualla vain neljällä viimeisellä numerolla ("tavoitettavissa numerosta ...5678", "soitamme takaisin numeroon ...5678") – sama rakenne kuin IBAN:in ja luottokortin kohdalla.
- Jo tunnistettu luottokorttinumero jäi lyhennetyssä vahvistusmuodossaan luettavaksi, jos se mainittiin asiakirjan muualla vain neljällä viimeisellä numerolla ("Kreditkarttinne päättyy numeroon ...0366") – sama maksuvahvistuksissa tavallinen rakenne kuin IBAN:in kohdalla.
- Jo tunnistettu IBAN jäi lyhennetyssä vahvistusmuodossaan luettavaksi, jos se mainittiin asiakirjan muualla vain neljällä viimeisellä numerolla ("IBAN päättyy numeroon ...3201") – vahvistussähköposteissa tavallinen rakenne.
- Puhuja chat- tai kokouspöytäkirjassa jäi tunnistamatta, jos nimen edessä oli puhuttelu ("Herr Bauer: …", "Frau Koch: …") – ja koski usein myös saman pöytäkirjan seuraavaa puhujariviä, koska liian vähän tunnistettuja rivejä jäi jäljelle, jotta asiakirja ylipäätään tulkittaisiin pöytäkirjaksi.
- Syntymäaika jäi tunnistamatta, kun kenttäsana "geboren" oli päivämäärän JÄLKEEN eikä edessä ("Das Kind wurde am 14.01.2026 geboren") – näin esim. vanhempainvapaa- tai äitiyssuojatodistus muotoilee lapsen syntymäajan. Aiemmat mallit edellyttivät kenttäsanaa aina ennen päivämäärää.
- Lomake-otsikkoa reaktio- tai valintamerkillä välittömästi edessä ("Ansprechpartner 😊:", "Kontaktperson ✓:") ei enää tunnistettu otsikoksi, ja sen alla tai jäljessä oleva nimi jäi siksi osittain tunnistamatta (esim. vain sukunimi tapauksessa "Mayer Roman").
- Sama aukko koski myös erityisen suojattavia GDPR:n 9 artiklan mukaisia tietoja (uskonto, terveys, ammattiliitto): reaktiomerkki suoraan erottimen tai rivinvaihdon edessä ("Konfession 😊: römisch-katholisch") jätti otsikon kokonaan tunnistamatta, ja tieto jäi täysin huomaamatta.
- Osoite yhdysviivalla kirjoitetulla kaksoisnimellä paikkakunnassa (esim. "79761 Waldshut-Tiengen", "78050 Villingen-Schwenningen") menetti postinumeron kokonaan, vaikka paikkakunta itse tunnistettiin ja mustattiin – ajoneuvon rekisteriotteessa tai kirjeessä postinumero jäi näin luettavaksi.
- Taulukkosarake ilman sarakeväliä (todellinen PDF-tekstiote) saattoi nimisarakkeen alla mustata virheellisesti henkilönä myös kaksi sattumalta vierekkäistä isolla alkukirjaimella kirjoitettua sanaa, esim. kaksi paikannimeä tietorivillä; nyt näin tapahtuu vain, jos mikään muu löydös ei jo tunnista jotain muuta samassa kohdassa.
- Sama nimisarake mustasi samassa rivimuodossa myös kaksi kielimallille tuntematonta asiasanaa (esim. "Frontend Backend", "Turbo Modul") virheellisesti henkilönä, koska mikään muu löydös ei laukaissut jarrua siinä kohdassa; nyt se vaatii lisäksi, että vähintään toinen kahdesta sanasta luetaan kielimallin itsensä toimesta erisnimeksi.
- Saksalainen eläkevakuutusnumero virallisessa täydessä ryhmittelyssään (esim. "65 170839 J 08 8" – kuten se on sosiaalivakuutustodistuksessa ja palkkalaskelmassa) jäi tunnistamatta ja pysyi alkuperäisenä; tunnistettiin vain tiivis kirjoitusasu ja vain kirjaimeen asti ryhmitelty muoto.
- Verotunnistenumero virallisessa kirjoitusasussaan (ryhmittely 2-3-3-3, esim. "48 836 075 988" – kuten se on jokaisessa todellisessa verotuspäätöksessä ja liittovaltion verokeskuksen ilmoituksessa) jäi kokonaan tunnistamatta ja pysyi alkuperäisenä; vain harvinaisempi ryhmittely 3-3-3-2 oli katettu.
- Nordrhein-Westfalenin verotunnus (esim. "221/5147/0815", nelinumeroisella kolminumeroisen sijaan toisella ryhmällä) jäi verotuspäätöksissä kokonaan tunnistamatta ja pysyi alkuperäisenä – jokainen muu osavaltio oli jo katettu.
- Työsopimuksissa nimi otsikon "Arbeitgeber:" takana jäi kokonaan huomaamatta heti, kun sukunimi oli samalla tavallinen sana (esim. "Bauer Anna") – "Arbeitgeber" on listassa sekä nimi- että yritysotsikkona, ja yrityskohdistus ylikirjoitti nimikohdistuksen.
- Vuokrasopimuksen otsikossa otsikoilla "Vermieter:"/"Mieter:" sukunimi, joka on samalla tavallinen sana (esim. "Bauer"), jäi huomaamatta – vain etunimi tunnistettiin. Numeroidut vuokralaisosapuolet ("Mieter 1:", "Mieter 2:") olivat lisäksi kärsineet, myös nimillä ilman tätä kaksitulkintaisuutta.
- Oikeuspöytäkirjassa otsikoilla "Zeuge:"/"Kläger:"/"Beklagter:" (myös numeroinnilla, "Zeuge 1:", "Zeuge 2:") sukunimi, joka on samalla tavallinen sana (esim. "Bauer"), jäi samoin huomaamatta – vain etunimi tunnistettiin.
- Perintötodistuksessa, valtakirjassa, maksukehotusmenettelyssä ja kauppasopimuksessa sukunimi, joka on samalla tavallinen sana (esim. "Bauer"), jäi otsikoiden kuten "Erblasser:", "Erbe:", "Vollmachtgeber:", "Bevollmächtigte:r", "Antragsgegner:", "Schuldner:", "Gläubiger:", "Käufer:", "Verkäufer:", "Vermächtnisnehmer:" tai "Testamentsvollstrecker:" takana huomaamatta – osittain jäi vain etunimi tunnistettua, osittain koko nimi katosi.
- Monen osapuolen listassa ennen rubrum-erotinta "./." (esim. "Sand, Werner und Huber, Anna ./. Wechsler, Martina") ensimmäinen osapuoli jäi naamioimatta – vain merkin "./." välittömässä läheisyydessä oleva osapuoli tunnistettiin.
- Rubrum-erotinmerkissä "./." (esim. "Sand./.Wechsler") merkin jälkeinen nimi jäi kokonaan huomaamatta, kun sen kohdalla ei ollut väliä – vain edessä ja jäljessä olevalla välillä tunnistus osui.
- Sukunimi "Wahr" jäi kokonaan huomaamatta, kun se seisoi yksin (esim. "Frau Wahr bearbeitet Ihren Vorgang.") – sana on sattumalta myös tavallisten saksalaisten sanojen listassa, joka muuten suodattaa nimilöydöksiä lauseista kuten "Das ist wahr."
- Sukunimet kuten "Los", "Weit", "Rund" tai "Hoch" jäivät kokonaan huomaamatta, kun ne seisoivat yksin (esim. "Herr Hoch übernahm die Leitung.") – kaikki neljä sanaa ovat sattumalta myös tavallisten saksalaisten sanojen listassa, joka muuten suodattaa nimilöydöksiä lauseista kuten "Rund einhundert Gäste kamen zur Feier."
- Sukunimet kuten "Ganz" tai "Recht" jäivät kokonaan huomaamatta, kun ne seisoivat yksin (esim. "Herr Ganz unterschrieb den Vertrag.") – molemmat sanat ovat sattumalta myös tavallisten saksalaisten sanojen listassa, joka muuten suodattaa nimilöydöksiä lauseista kuten "Ganz genau, das stimmt."
- Lomakekenttä tähdellä tai yläindeksillä varustetulla viitenumerolla otsikon jäljessä (esim. "Konfession*: römisch-katholisch" tai "Religionszugehörigkeit¹: evangelisch") jäi tunnistamatta ja pysyi selkotekstinä – vain muoto ilman tätä merkkiä osui.
- Sama kenttä pysyi edelleen selkotekstinä, kun otsikon jäljessä oli peräti kaksi viitemerkkiä (esim. "Konfession**: römisch-katholisch" tai "Gewerkschaft¹²: ver.di").
- Versionumeroa kuten "Softwareversion 4.2.1.19" tai "Firmware Build 2.0.4.11" ei enää mustata virheellisesti IP-osoitteena. Sama koskee nyt kuitti- ja tapausnumeroita kuten "Rechnungsnummer 10.20.30.40" tai "Bestellnummer 7.8.9.10".
- Kaksi IBAN:ia suoraan allekkain (esim. oma ja ulkomaisen liikekumppanin laskun otsikossa) eivät enää molemmat tunnistuneet – toinen jäi huomaamatta.
- Otsikoitu IBAN veti joskus mukaansa seuraavan sanan lauseessa ("Bankverbindung AT61 … wird belastet" mustattiin sanaan "wird" asti), heti kun seuraava sana oli pienellä kirjoitettu – vieressä oleva selkotekstin loppu jäi tällöin koskemattomaksi.
- Liechtensteinilaiset osoitteet tunnistetaan nyt ("FL-9490 Vaduz"), kuten aiemmin jo saksalaiset, itävaltalaiset ja sveitsiläiset.
- Passin numero tunnistetaan ja poistetaan nyt otsikkonsa takaa (esim. "Reisepassnummer: C01X00T471").
- Oleskelulupa- ja ilmoittautumistodistusnumero tunnistetaan ja poistetaan nyt otsikkonsa takaa.
- Tunnusnumero otsikkonsa takana tunnistetaan nyt myös, kun kaksoispisteen sijaan erottaa ajatusviiva (esim. "Kundennummer – K903944").
- "IBAN" tai "Kontonummer"-otsikolla varustettu pankkiyhteys tunnistetaan nyt myös, kun kaksoispisteen sijaan erottaa ajatusviiva.
- Nimi otsikon kuten "Kontaktperson (Vertrieb)" tai "Sachbearbeiter/in" takana tunnistetaan nyt myös sulkulisäyksellä tai sukupuolineutraalilla vinoviivapäätteellä.
- Sama tähtimerkillä varustettu sukupuolineutraali muoto ("Sachbearbeiter*in") tunnistetaan nyt myös.
- Nimi otsikon takana tunnistetaan nyt myös, kun kaksoispisteen sijaan erottaa yhtäläisyysmerkki (esim. "Ansprechpartner = Mayer Roman" tai "Kontaktperson=Mayer Roman"), kuten asetustiedostoissa tai CSV-otsikkoriveillä on tavallista. Jos useita tällaisia otsikko-arvo-pareja on rivillä puolipisteellä erotettuina, tunnistetaan nyt vain ensimmäinen arvo koko loppurivin sijaan.
- GPS-koordinaattipari sanan "Koordinaten" takana tunnistetaan nyt luotettavasti (esim. "Koordinaten: 48.2082, 16.3738") – sanalla oli väärä taivutusmuoto sisäisessä luettelossa.
- Tunnusnumero otsikkonsa takana (asiakasnumero, sopimusnumero, asianumero, henkilötodistuksen numero ja noin sata muuta kenttäsanaa) jäi tunnistamatta heti, kun otsikko ei ollut tarkalleen tallennetussa iso-/pienaakkoskirjoituksessa – "kundennummer:" sähköpostissa tai "KUNDENNUMMER:" lomakkeen otsikossa jäivät koskemattomiksi.

### Uutta

- **Realistiset korvausarvot ovat nyt tietoisesti käytetty esimerkki, ei oletusarvo.** Poikkeustaulukko välilehdellä "Paikkamerkit" alkaa tyhjänä. Uusi painike lisää sinne toivottaessa uskottavia väärennettyjä arvoja nimelle, paikalle, osoitteelle, organisaatiolle, sähköpostille, puhelimelle, alanumerolle ja IBAN:ille. Se jättää rahasummat nimenomaisesti numeroituun paikkamerkkiin; strategia "keksi" pysyy edelleen käsin valittavissa yksittäisille lajeille.
- **Tekoälytaso voi käyttää näytönohjainta.** Windowsilla tätä varten voi ladata noin 17 Mt:n lisäpaketin; sen jälkeen tekoälytaso laskee sopivalla näytönohjaimella huomattavasti nopeammin kuin prosessorilla. Jos näytönohjainta ei ole tai mitään ei ladata, työ jatkuu ennallaan – vain hitaammin. macOS:llä kiihdytys on joka tapauksessa jo sisäänrakennettu.
- **Kaksi uutta ilmoitusta tehtäväpalkin kuvakkeen kautta**: kun esikatselu on läpikäyntiä varten valmiina ennen korvaamista ja kun käsittely on valmis. Molemmat ovat oletuksena päällä ja voidaan kytkeä pois yksitellen kohdasta *Asetukset → Ohjelma → Ilmoitukset*.

### Muutettu

- **Henkilötodistuksen ja ajokortin numero tunnistetaan nyt**, kun niiden otsikko on edessä ("Personalausweisnummer: …", "Führerscheinnummer: …") – tähän asti molemmat jäivät jokaisessa tunnistuksessa huomaamatta.
- **Maskuro noudattaa nyt Windowsin kontrastimalleja.** Jos kohdassa *Asetukset → Saavutettavuus → Kontrastimallit* on yksi kytketty päälle, se näkyi tähän asti kaikkialla paitsi täällä. Maskuro asetti sen jälkeen omat värinsä. Nyt järjestelmän malli säilyy – ikkuna, listat, pudotusalue, loki ja tilavärit. Värillinen tarkastusliikennevalo esikatselussa ja korjausikkunassa jää tällöin tarkoituksella pois; se, mitä se kertoo, on siitä lähtien joka tapauksessa vieressä sekä merkkinä että sanana.
- **Tarkastustarve ei ole enää pelkästään värin varassa.** Punainen, oranssi ja vihreä ovat lähes yhtä vaaleita – punavihervärisokealle esikatselussa ja löydöspaneelissa näkyi lista ilman eroja, ja tämä koskee noin joka kahdettatoista miestä. Jokainen rivi kantaa nyt lisäksi muodoltaan erottuvan merkin: ▲ tarkista ensin, ● tarkista, ○ hyvin dokumentoitu, ◆ ilman arviointia. Lyhyt vihje nimeää sen sanoin, ja ruudunlukija lukee sen ääneen.
- **Alt avaa valikot taas totutulla tavalla.** Valikkorivillä ei ollut pikanäppäimiä: hiirtä käyttämätön joutui liikkumaan jokaisen valikon läpi nuolilla. Nyt jokaisella kohdalla on alleviivattu kirjain – Alt+D avaa "Tiedosto"-valikon (saksankielisessä alkuperäisessä "Datei"), sieltä B avaa "Lopeta" (saksaksi "Beenden") – kaikilla käyttöliittymän kielillä.
- **Käyttöelementit kertovat taas ruudunlukijalle, mitä varten ne ovat.** Korjausikkunassa, sääntöikkunassa, lokissa, sanalistoissa, ohjeessa, hakuajossa ja viidessä muussa ikkunassa listat, hakukentät, avattavat listat ja liukusäätimet ilmoitettiin tähän asti vain "puuna" tai "yhdistelmäkenttänä" – kertomatta mistä. Noin neljäkymmentä kohtaa kantaa nyt nimen. (Pääikkuna oli elokuusta lähtien kunnossa; sen jälkeen tulleet ikkunat eivät olleet koskaan seuranneet mukana.)
- **Näppäimistöllä käyttävä näkee kaikkialla, missä hän on.** Esikatselun tarkastustarve-säätimissä, valintaruudussa ja "ei koskaan enää" -painikkeessa, sen sisällä olevissa laji-otsikoissa, korjausikkunan sivupaneelissa ja asetusten sivupalkissa puuttui kehys, jonka järjestelmä muuten piirtää kohdistetun käyttöelementin ympärille.
- **Suurempi järjestelmäfontti ei enää katkaise mitään.** Kun kohdassa *Saavutettavuus → Tekstin koko* asetettiin yli 175 %, kansionvalvonnan ja pikanäppäinkenttien otsikoiden loppu katosi tähän asti. Ohjeen luettelo katkaisi pitkät lukuotsikot jo tavallisella fontilla; ne rivittyvät nyt ja täysi nimi näkyy lyhyessä vihjeessä.

- **Tunnistus on huomattavasti nopeutunut.** Otsikoitujen tunnusnumeroiden ("Kundennummer: K903944") tunnistin tarkisti tähän asti yli 1200 yksittäistä mallia peräkkäin jokaista tekstikatkelmaa kohden – tämä oli tunnistusajan suurin yksittäinen erä jokaisessa kappaleessa ja taulukkosolussa. Nyt se on yksi ainoa malli samalla tuloksella: mittauskorpuksessa yksikään löydös ei muutu, perustaso tekstikatkelmaa kohden on noin kolme–neljä kertaa nopeampi.
- **Ikkuna ilmestyy heti käynnistyksessä.** Tähän asti pääikkuna latasi täydet kieliohjelmat ennen kuin se edes näkyi – noin neljä sekuntia sokeaa aikaa joka käynnistyksellä. Mallit latautuvat nyt suunnitellusti taustalla, kun ikkuna on jo näkyvissä; "Puhdista"-painike vapautuu kuten ennenkin vasta, kun kaikki on valmiina. Myös pelkät tietokyselyt komentorivillä (esim. `--version`) vastaavat nyt heti useiden sekuntien sijaan.
- **Kuvat luetaan automaattisessa kielentunnistuksessa nyt vain kerran.** Tähän asti tekstintunnistus kulki oletuksella "Kieli: automaattinen" kahdesti saman kuvan läpi – kerran kielen arvausta, kerran varsinaista tarkastusta varten. Kuvatiedostot, leikepöydän kuvat ja tekstikkuna ovat siten noin kaksi kertaa nopeampia; tekstintunnistuksen ollessa pois päältä myös tähän asti huomaamatta silti käynyt lukukerta jää kokonaan pois.
- **Tallennetut verkkosivut ja sähköpostit puhdistuvat nopeammin.** Arvot HTML-attribuuteissa, kommenteissa ja upotetuissa datalohkoissa tunnistettiin tähän asti yksitellen – kunnan verkkosivu sadoilla otsikoilla esitti sadoittain yksittäisiä kysymyksiä tunnistukselle. Nyt ne kootaan yhteen ja jokainen erilainen arvo tunnistetaan vain kerran; mittauskorpuksessa yksikään löydös ei muutu, .html ja .eml ovat noin kolmasosan nopeampia.
- **Myös taulukoiden ja esitysten sivutietovarastot tunnistetaan koottuina.** Vaihtoehtoiset tekstit, kaavamerkkijonot, kaavioiden otsikot, kommentit, pivot-välimuistit ja asiakirjan ominaisuudet esittivät jokaisesta arvosta oman tunnistuskysymyksen – tuhansien pivot-rivien työkirja vastaavasti tuhansia. Nyt yksi koottu ajo kulkee eri arvojen läpi, ja lopun täydellinen jälkiajo suoritetaan vain, jos leipätekstin jälkeen on todella tullut uusia arvoja. Mittauskorpuksessa yksikään löydös ei muutu.
- **Lomakerikkaat PDF:t puhdistuvat nopeammin.** Kentät, huomautukset, kirjanmerkit ja viittaukset toistavat samoja arvoja massiivisesti ("Off" jokaisessa valintaruudussa, sama tekijä jokaisessa anotaatiossa) – jokainen esitti tähän asti oman tunnistuskysymyksensä. Ajoa kohden arvo tunnistetaan nyt vain kerran; korvaus ja johdonmukaisuuden jälkitarkastus toimivat ennallaan jokaisessa kohdassa.
- **Suuret taulukkotiedostot (.csv/.tsv) puhdistuvat huomattavasti nopeammin.** Neljä taulukon jälkiajoa pilkkoi tähän asti saman tiedoston kukin erikseen merkki kerrallaan soluiksi (40 Mt:lla noin 30 sekunnin lisätyö); nyt pilkkominen tapahtuu kerran. Sarakeotsikoiden tunnistus (syntymäaika- ja henkilönumerosarakkeet) esittää kysymyksen kootusti jokaisen solun sijaan – identtisillä löydöksillä noin kaksikymmentä kertaa nopeampi. Ja suurten henkilölistojen nimisarakkeiden yhteenveto ei ole enää neliöllinen rivimäärän suhteen.
- **Tunnuslukujen liuska ei enää jäädytä ikkunaa.** Tunnuslukujen avaaminen luki monissa suurissa tiedostoissa niiden tekstin ensin kokoon ja pysäytti ikkunan sekunneiksi. Laskenta toimii nyt taustalla; liuska avautuu heti ja luvut täydentyvät jälkikäteen.
- **Hakuajon raportti ei enää jäädytä ikkunaa.** Monen tuhannen tiedoston läpihaun jälkeen yhteinen kansio laskettiin uudelleen jokaiselle koskevalle tiedostolle; suurissa ajoissa ikkuna pysähtyi tällöin kaksinumeroisiksi sekunneiksi. Raportti ilmestyy nyt heti.
- **Tekstintunnistuksella varustetut PDF:t tarkastetaan nopeammin.** Jokainen sivu muunnettiin gegenlukemisessa tarpeettomasti kahdesti PNG-muotoon; nyt jo olemassa oleva kuva ohjataan suoraan läpi. Tulos on ennallaan, vain tarkastus sujuu ripeämmin.
- **Isoilla kuvilla olevat historia-annotaatiot eivät enää nykäise.** Liukuvärillisen annotaation kahvoista vedettäessä liukuväri laskettiin tähän asti piste pisteeltä uudelleen – suurella kuvakaappauksella näkyvä pysähdys. Tulos on sama, vain ilman taukoa.

### Korjattu

- **Risti tiedoston poistamiseksi listasta on jälleen pelkkä X.** Uusi editorin työkalu "Poista" oli vahingossa käyttänyt samaa kuvaketunnusta ja näytti siksi punaisen ristinsä katkoviivaisen tekstirivinsä kera myös jokaisella tiedostorivillä. Molemmilla toiminnoilla on nyt erilliset kuvakenimet ja ne säilyttävät kumpikin oman sopivan ulkoasunsa.
- **Moniosaiset tiedot tunnistetaan PDF:issä nyt myös näkyvän rivinvaihdon yli.** Maskuro lukee geometrisesti luodun sivutekstin lisäksi offset-yhteneväisenä leipätekstinäkymänä. Tämä koskee kaikkia perus- ja korkean tason tunnistimia sekä omia hakumalleja, ei vain ensin havaittua tapausta "Diabetes mellitus Typ 2". Tyhjät rivit ja tunnistetut taulukko- tai osiorajat pysyvät kovina rajoina; löydöskohdat osuvat edelleen tarkasti mustattaviin sanoihin.
- **Esimerkki kohdassa "Pseudonymisoi" oli ristiriidassa itsensä kanssa.** Lause lupasi "sama henkilö, sama numero" ja näytti sitten kaksi eri numeroa – juuri sen kuvan, joka on oikea kohdassa "Anonymisoi". Molemmat esimerkit vastaavat nyt omaa lausettaan.
- **Juuri asetettu paikkamerkki saattoi "Palauta alkuperäinen" -toiminnossa jäädä päällekkäiseksi kirjainsotkuksi katoamisen sijaan.** Yksivärisenä asetettu paikkamerkki kirjoitti tähän asti oman tulostuskomennon jokaiselle merkille, joista vain ensimmäisellä oli oma tekstimatriisi – kun samaa kohtaa muokattiin seuraavan kerran (esim. "palauta" heti sen jälkeen), muut merkkikomennot saivat vuorollaan ensimmäisen merkin merkkiindeksit, ja paikkamerkki hajosi kahdeksi päällekkäiseksi sijainniksi. Yksivärinen paikkamerkki saa nyt yhden ainoan tulostuskomennon koko tekstilleen.

- **Jos sama mustattu tai poistettu arvo oli kahdella rivillä korjausikkunassa ja molemmat merkittiin peruutettavaksi, toinen rivi laskettiin virheellisesti "ei yksiselitteiseksi" – vaikka arvo oli jo kauan sitten palautettu.** Molemmat rivit lasketaan nyt valmiiksi.

- **Nimi "Reply-To:"-otsikon jäljessä löytyy nyt.** Sähköpostiotsikkorivillä kuten "Reply-To: Huber" nimi jäi tähän asti kokonaan tunnistamatta – kielimalli luki "Reply-To:"-otsikon omana, vääränä henkilönä ja jätti todellisen nimen sen jäljessä huomiotta.

- **Sähköpostiotsikkosanoja "Reply" ja "Fwd" ei enää mustata itseään nimenä.** Otsikkorivillä kuten "Fwd: Angebot von Huber" tunnistettiin ja mustattiin tähän asti nimen lisäksi myös itse otsikkosana henkilönä.

- **"Arbeitgeber: Siemens AG" tunnistetaan nyt yrityksenä, ei enää henkilönä.** Jos otsikon "Arbeitgeber" takana ollut yritysarvo kantoi oikeushenkilömuodon kuten GmbH, AG tai KG, se pysyi kytketystä organisaatiotunnistuksesta huolimatta henkilölöydöksenä – vain kapeampi tapaus ilman oikeushenkilömuotoa ("Wollmuth und Partner") tunnistettiin tähän asti yrityksenä.

- **Kerran tunnistettu osoite ei enää jää näkyviin toisaalle.** Jos katuosoite tunnistettiin ja korvattiin yhdessä kohdassa, sama osoite saattoi jäädä paikalleen toisessa kohdassa – esim. skannatun asiakirjan huonolukuisessa alatunnisteessa, jonka automaattinen tekstintunnistus luki vääristyneenä. Osoitteet poistetaan nyt, kuten nimet ja yritykset jo pidempään, johdonmukaisesti koko asiakirjasta.

- **Sähköpostit useilla vastaanottajilla vahingoittuivat äänettömästi puhdistuksessa.** `.msg`-viesti kahdella tai useammalla vastaanottajalla menetti tallennettaessa osia sisäisestä rakenteestaan, jolloin puhdistettu tulos oli vaillinainen. Syynä oli samannimisten sisäisten osien sekaannus, joka esiintyy jokaisen vastaanottajan kohdalla. Tällaiset viestit rakennetaan nyt jälleen täydellisesti.

- **Kaksi mukana toimitettua testiasiakirjaa ei avautunut Wordissa ja PowerPointissa.** Mittauskorpuksen lataaja sai tiedostosta `format_dokument.docx` virheen "Virhe avattaessa tiedostoa Wordissa" ja tiedostosta `format_praesentation.pptx" virheen "Tiedosto on vioittunut". Molemmat tiedostot olivat viallisia jo ennen kuin Maskuro koski niihin – puhdistettu versio vain periytti virheen. LibreOffice avasi molemmat ongelmitta, minkä vuoksi kukaan ei ollut huomannut asiaa.

- **Omaa tekoälyä internetissä lähestytään nyt salatusti.** Jos omalle tekoälylle syöttää ulkoisen osoitteen ilman "https://" (kuten IT-osaston lapulla usein lukee), sitä lähestyttiin tähän asti salaamattoman yhteyden kautta – mustaamaton teksti kulki selkotekstinä ulos. Tällaiset osoitteet lähestytään nyt "https://"-yhteydellä; omassa verkossa oleva palvelin pysyy edelleen tavoitettavissa. Jos palvelin ohjaa toiselle koneelle, käyttöavain ei enää kulje mukana.

- **Myös vioittunut kuva menettää nyt piilotetut metatietonsa.** Jos upotettu kuva ei enää avautunut täydellisesti (esim. katkennut valokuva), se säilytti tähän asti EXIF- ja GPS-tietonsa – kuvauspaikka ja valokuvaajan nimi jäivät näkymättömästi tulokseen. Tällaiset kuvat vapautetaan nyt näistä tiedoista myös silloin, kun niitä ei enää voi näyttää lainkaan.

- **Upotettu tiedosto, jota ei voitu puhdistaa, ilmoitetaan nyt äänettömästi mukaan antamisen sijaan.** Jos esityksessä tai työkirjassa oli upotettu objekti, joka oli liian syvällä sisäkkäin tai ei avautunut, se jäi tähän asti muuttumattomana tulokseen ilman huomautusta – tiedosto laskettiin puhdistetuksi. Tällaiset tapaukset näkyvät nyt varoituksessa "EI voitu tarkastaa", aivan kuten upotettu vanha tiedostomuoto.

- **Tummat listat ovat jälleen yhtenäisen tummia ja luettavissa.** macOS:llä tiedostolistat vaihtelivat lähes mustien ja vaaleanharmaiden rivien välillä; korjausnäkymässä sama vihreä, oranssi tai punainen tarkastusarvo näytti rivistä riippuen erilaiselta. Ikkuna, listat, fontti, paikkamerkit ja valinta tulevat nyt yhteisestä vaalea-/tummapaletista. Väritetty löydöslista ei myöskään enää aseta seepravöitä väriensä alle.

- **"als"-sanalla varustetut ammattitiedot mustattiin virheellisesti nimenä.** Lause kuten "Als Koch ist er seit vier Jahren bei uns tätig." menetti ammatin, ei vain nimeä – "als" johdattaa roolikuvausta samoin kuin "der" tai "die". Todelliset sukunimet samassa kohdassa (esim. puhuttelun edessä) pysyvät koskemattomina.

- **Taulukko-otsikko saattoi vetää positionumeron rahasummaan mukaan** (vain kytketyllä valinnalla "Poista myös rahasummat"). Jos rivi päättyi valuuttaan ("… Einzelpreis EUR") ja seuraava alkoi luvulla, siitä syntyi virheellisesti summa rivinvaihdon yli. Erotin valuutan ja luvun välissä pysyy nyt samalla rivillä.

- **Lyhyt isokirjaiminen lyhenne saattoi niellä kokonaisen lauseenosan tai liittyä oikein tunnistetun nimen eteen.** Jos rivillä oli kaksikirjaiminen isokirjaiminen sana kuten "DI", "AG" tai "KG" – arkipäiväisiä lyhenteitä, ei nimiä –, koko rivi haettiin kokeeksi pienellä kirjoitettuna, ja lyhenne veti tällöin joskus naapurisanoja (myös verbejä) mukaan yhdeksi luultuksi nimeksi. Vasta kolmesta kirjaimesta alkaen isokirjaiminen sana laukaisee nyt tämän toisen tarkastuksen. Hieman pidemmillä lyhenteillä kuten "CEO" tai "USB" oli toinen virhe: jo oikein löydetty nimi ("Schneider") sai edessä olleen lyhenteen mukaan tulokseen etuliitteenä ("CEO Schneider"). Lyhenne jää nyt ulkopuolelle.

- **Syntymäaika ilman väliä sen jäljessä jäi paikalleen.** Jos sanan "geb." jäljessä ei ollut väliä ennen päivämäärää – kuten tiiviisti ladotuissa lomakkeissa on tavallista ("geb.14.03.1988") – Maskuro ei tunnistanut kenttää ja jätti päivämäärän koskemattomaksi. Yleiset lyhyet muodot kuten "Geburtsdat." tai "Geb.-Dat." tunnistetaan nyt myös.

- **IBAN vinoviivoilla erottimena jäi paikalleen.** Kuten puhelinnumeroissa ("0664/1234567"), jotkin lomakkeet kirjoittavat myös IBAN:in lohkoina vinoviivalla ("AT48/3200/0000/1234/5864") välin tai yhdysviivan sijaan. Tämä kirjoitusasu tunnistetaan nyt myös.

- **Itävaltalainen sosiaaliturvatunnus yhdysviivalla, pisteellä tai vinoviivalla jäi paikalleen tai oli väärin otsikoitu.** Kahden numerolohkon välissä oli tähän asti vain väli; kirjoitusasut kuten "1237-010180", "1237.010180" tai "1237/010180" eivät tunnistuneet (tai vinoviivan tapauksessa tunnistuivat väärällä lajilla). Tarkistusnumero vahvistaa edelleen jokaisen löydöksen erottimesta riippumatta.

- **Nimi sanan "c/o" jäljessä osoitteessa jäi kokonaan poistamatta.** "c/o Max Mustermann, Hauptstraße 5, 1010 Wien" mustasi kadun ja paikkakunnan, mutta jätti nimen sen jäljessä täysin paikalleen. Nimi tunnistetaan nyt; "c/o" itse pysyy näkyvissä osoiteviitteenä.

- **Pisteillä ryhmitelty luottokorttinumero jäi paikalleen.** Kirjoitusasuja kuten "4111.1111.1111.1111" ei tunnistettu; välillä tai yhdysviivalla erotetut numerot eivät kärsineet tästä. Tarkistussumma vahvistaa edelleen jokaisen löydöksen.

- **Yhdysviivoilla ryhmitelty verotunnistenumero jäi paikalleen, samoin itävaltalainen ALV-tunnus yhdysviivalla tai pisteellä.** Väli, vinoviiva ja piste oli verotunnisteessa jo huomioitu, yhdysviiva puuttui; ALV-tunnuksessa ("ATU12345678") puuttuivat yhdysviiva ja piste etuliitteen jälkeen. Verotunnisteen tarkistusnumero vahvistaa edelleen jokaisen löydöksen.

- **Kenttäarvo lainausmerkeissä jäi paikalleen, esim. JSON-tyyppisellä rivillä kuten „vorname": „Max".** Tunnistus kenttäotsikon kautta ("Vorname: …") edellytti tähän asti, ettei otsikko eikä arvo itse ole lainausmerkeissä. Tällaiset rivit tunnistetaan nyt myös – samoin kenttäotsikot edessä olevalla YAML-listamerkillä ("- Vorname: Max") tai sarkaimella välin sijaan ennen kaksoispistettä.

- **Sähköpostiotsikkosana "Sent" mustattiin itse kuin nimi.** Otsikkorivillä kuten "Sent: Huber" se osui tähän asti sekä sanaan "Sent" että varsinaiseen nimeen; sukulaiset otsikkosanat kuten "Subject" tai "Betreff" eivät koskaan kärsineet tästä. "Sent" jää nyt myös paikalleen.

- Nimi otsikkorivien "Errors-To:" tai "Resent-From:" jäljessä jäi tunnistamatta, kun tällainen rivi oli kopioitu selkotekstinä (esim. edelleenlähetetty viesti tai tapahtumaraportti) – toisin kuin "Reply-To:" tai "Return-Path:" kohdalla nimi katosi täällä kokonaan sen sijaan, että se olisi vain epätarkasti rajattu. Se löytyy nyt.
- Sama tiedosto antoi kahdesta puhdistuksesta toisinaan erilaisen tuloksen: kun kaksi tunnistusta osui täsmälleen samaan kohtaan samalla pituudella ja samalla varmuudella (esim. "Sozialversicherungsnummer 1237/010180" AT_SVNR:nä tai yleisenä tunnusnumerona), voitto riippui sattumasta – arvo poistettiin kummassakin tapauksessa, vain paikkamerkin otsikko vaihtui. Tasapeli ratkaistaan nyt aina samalla tavalla.
- Toiminimike suoraan pääsanan edessä (esim. "Behandelnder Arzt: Dr. …" tai "Zuständiger Sachbearbeiter ist …") mustattiin joskus virheellisesti mukana, ikään kuin se itse olisi nimi. Todelliset sukunimet vieressä eivät kärsi tästä.
- Todellinen sukunimi, joka sattuu näyttämään ominaisuussanalta (esim. "Schöne", "Lange", "Junge") ja seisoo välittömästi toisen pääsanan edessä (esim. "Kontaktperson: Schöne Assistentin"), jäi edellisen korjauksen jälkeen mustaamattomana tekstiin – tietovuoto. Nyt vain tiukasti rajattu lista todellisia toiminimikkeitä (esim. "Behandelnder", "Zuständiger") käsitellään tässä rakenteessa ei-nimenä.
- Yksinäinen sukunimi monirivisen nimilöydöksen lopussa, joka sattuu näyttämään ominaisuussanalta (esim. "Schwarz", "Kurz", "Alt", "Frisch", "Gut", "Reich"), jäi tunnistamatta välittömästi seuraavan kaksoispisteen edessä – puhdistus sekoitti sen kenttäotsikkoon kuten "Telefon:". Suljettu lista tunnettuja monimerkityksellisiä sukunimiä suojaa sen nyt.
- Yksinäinen sukunimi, joka sattuu olemaan tavallinen saksalainen sana ("Gross"/"Grosse", "Gut", "Kurz", "Lang"/"Lange"), katosi tähän asti **kokonaan** – myös yksinkertaisissa lauseissa kuten "Herr Gross unterschrieb den Vertrag." Syynä oli spaCy:n oma pysäytyssanalista, joka sisältää nämä sanat; suljettu lista tunnettuja sukunimiä suojaa ne nyt hylkäämiseltä.
- Työ-, laina-, takaus-, luottamus- ja maksukyvyttömyyssopimuksissa sekä holhous-/huoltajuusasioissa ja lausuntotoimeksiannoissa sukunimi, joka on samalla tavallinen sana (esim. "Bauer"), jäi otsikoiden kuten "Auftraggeber:", "Auftragnehmer:", "Arbeitnehmer:", "Versicherter:", "Darlehensgeber:", "Darlehensnehmer:", "Bürge:", "Sicherungsgeber:", "Treuhänder:", "Treugeber:", "Insolvenzverwalter:", "Gutachter:", "Sachverständiger:", "Vormund:" tai "Pfleger:" takana huomaamatta – osittain jäi vain etunimi tunnistetuksi, osittain koko nimi katosi.
- Yritystiedoissa (Impressum) sukunimi, joka on samalla tavallinen sana (esim. "Bauer"), jäi otsikoiden "Geschäftsführer:", "Geschäftsführerin:", "Vertretungsberechtigt:", "Inhaber:" tai "Inhaberin:" takana huomaamatta – kohdissa "Geschäftsführer:"/"Inhaber:" koko nimi katosi, kohdassa "Vertretungsberechtigt:" jäi vain etunimi tunnistetuksi.
- Yhteystietolohko, jonka otsikko oli yksinään omalla rivillään ja kantoi sukupuolineutraalin kaksoispistemuodon ("Ansprechpartner:in", nimi alla), jäi **kokonaan** huomaamatta – kaksoispiste luettiin kenttäerottimeksi, "in" (hylättynä) kenttäarvoksi, ja varsinainen nimi seuraavalla rivillä ei koskaan enää päässyt mukaan. Tähtimuoto ("Ansprechpartner*in") ei kärsinyt tästä.
- Jos nimi ja otsikko olivat samalla kaksoispiste-sukupuolimuodolla **yhdellä** rivillä ("Ansprechpartner:in Anna Berger"), paikkamerkki veti sanan "in" mukaan korvaukseen pelkän nimen poistamisen sijaan – itse nimi tunnistettiin edelleen täydellisesti.
- Nimi taulukkosarakkeessa henkilösarakkeen otsikon alla (esim. "Name Vorname Geburtsdatum" rivin "Bauer Anna 03.05.1985" yläpuolella, kuten palkkalaskelmassa) jäi kokonaan huomaamatta heti, kun sarakkeiden välissä oli vain yksi väli eikä mikään rivi alkanut jäsennysnumerolla – juuri se muoto, jossa todellinen PDF-tekstiote tällaiset rivit tuottaa.
- Chat- tai kokouspöytäkirjassa puhujan nimellä ennen kaksoispistettä (esim. "Bauer 🙂: Ich stimme dem Vorschlag zu.") nimi jäi kokonaan tunnistamatta heti, kun reaktiomerkki oli nimen ja kaksoispisteen välissä ja sukunimi oli samalla tavallinen sana ("Bauer", "Koch", "Schneider" tms.) – kokonainen pöytäkirja saattoi näin jäädä ilman yhtään tunnistettua puhujaa.
- Sama puhujarivien aukko koski myös muita välimerkkejä ennen kaksoispistettä: sulkeissa olevaa tilalisäystä ("Bauer (Vorsitz): …", "Bauer (abwesend): …"), kellonaikaa hakasulkeissa ("Bauer [14:32]: …") ja viitemerkkiä välittömästi nimen vieressä ("Bauer*: …"). Myös näissä puhuja jäi kokonaan tunnistamatta heti, kun sukunimi oli samalla tavallinen sana.
- Jos jo tunnistettu henkilö esiintyi saman viestin liitetyssä pöytäkirja- tai lokikatkelmassa (esim. tukipyyntö) lisäksi käyttäjätunnuksena muodossa "etunimi.sukunimi" – pienellä kirjoitettuna, ilman väliä, pisteellä yhdistettynä –, tämä selväkielinen nimi jäi luettavaksi, vaikka sama nimi oli jo mustattu saatekirjeessä.
- Sama käyttäjätunnusaukko koski myös alaviivaa pisteen sijaan ("etunimi_sukunimi") – yhtä yleinen muoto pöytäkirja- ja lokikatkelmissa.
- Ja myös käänteisessä järjestyksessä käyttäjätunnus jäi luettavaksi ("sukunimi.etunimi" tai "sukunimi_etunimi") – jotkin järjestelmät asettavat sukunimen ensin loki-käyttäjätunnuksessa etunimen sijaan.
- Kuolinpäivä jäi tunnistamatta, kun muuta tietoa ei ollut vieressä ("Herr Bauer ist am 12.03.1985 verstorben") – tähän ei ollut tähän asti mitään omaa tunnistusta, eikä yleinen päivämäärä osu tällä vakiokynnyksellä.
- Kuolinpäivä jäi tunnistamatta myös silloin, kun lause käytti verbimuotoa partisiipin sijaan ("Frau Meier verstarb am 12.03.1985", "Er starb am 12.03.1985") – vain "ist … verstorben"/"ist … gestorben" osui tähän asti.
- Avioitumispäivä jäi tunnistamatta, missä tahansa muodossa se olikin ("Eheschließung am 12.03.2010", "Hochzeitsdatum: 12.03.2010", "Herr und Frau Bauer heirateten am 12.03.2010") – tähän ei ollut tähän asti mitään omaa tunnistusta, eikä yleinen päivämäärä osu tällä vakiokynnyksellä.

- **Korjaus-editorissa toinen kehys juuri asetetun paikkamerkin päällä saattoi jättää punaisen merkkijäänteen**, esim. "[G" muodon "[BEG1]" sijaan – ilman minkäänlaista varoitusta, sillä jäänne ei enää kuulunut luottamukselliseen tietoon (se oli jo poistettu ensimmäisellä kerralla), vaan ainoastaan omaan paikkamerkkiin. Syynä oli väritys: uusi paikkamerkki kirjoitettiin tiedostoon merkki kerrallaan, myös yksivärisellä oletuksella – myöhempi kehys samassa kohdassa ei enää löytänyt yhtenäistä sanamuotoa, johon se olisi voinut kohdistua. Yksivärinen paikkamerkki on nyt yksi kappale virrassa, kuten automaattinen puhdistus on aina tehnyt; vain todellinen liukuväri- tai sateenkaariteksti tarvitsee edelleen yksittäisiä merkkejä. Sisäänrakennettu vastanäyttö tunnistaa nyt tällaisen jäänteen myös silloin, kun paikkamerkin tarkka merkkijono ei enää esiinny.
- Numeroitu nimilista porrastetulla jäsennysnumerolla ("1.1 Max Mustermann", "1.2 Huber Franz" …) menetti kaikki nimet samalle jarrulle, jonka piti oikeasti suojata vain todellisia jäsennyksiä ja positioluetteloita – ilman sarakeotsikkoa listan yläpuolella ei ollut todistajaa, jonka avulla nimi olisi voitu pelastaa.
- Nimi englanninkielisellä kirjautumisrivillä järjestelmälokissa ("Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2") jäi tunnistamatta – saksalainen kielimalli löysi sen vain, jos edessä oli "invalid user", muutoin se jäi paikalleen. Tällaisia lokikatkelmia liitetään usein muuttumattomina tapahtumaraporttiin. Nimet sanan "for" jäljessä ennen IP-osoitetta tunnistetaan nyt luotettavasti.
- Maksuvelvollisen nimi tiliotteen tai kirjauspäiväkirjan SEPA-toimeksiantoviitteessä (esim. "MREF+Mustermann Klaus+SVWZ+Miete August") jäi paikalleen – ei väliä, ei lauserakennetta, vain "+"-merkillä erotettuja isokirjaimisia kenttiä, ja siellä tavallisessa järjestyksessä "Sukunimi Etunimi" tunnistus ei löytänyt sitä myöskään sattumalta. Tunnistetaan nyt.
- Katu talonumeroineen osoitetaulukon ensimmäisellä rivillä (esim. "Sukunimi | Etunimi | Katu | Postinumero | Paikkakunta") jäi paikalleen – kielimalli arvasi siellä väärän mutta pidemmän paikkakunnan usean sarakkeen yli, ja se syrjäytti oikean, lyhyemmän osoitelöydöksen. Tunnistetaan nyt.
- Sama vuoto esiintyi sarkaimella "|":n tai ";":n sijaan sarakeerottimena – siellä osoite katosi jopa kokonaan, ei vain osittain. Tunnistetaan nyt.
- Katu talonumeroineen jäi paikalleen, kun sitä seurasi heti ilman väliä pilkullinen postinumero (esim. "Bahnhofstrasse 12,80331 München", kuten pilkuilla erotetussa taulukkosarakkeessa) – pilkku näytti määrän desimaalilta, eikä katua siksi tunnistettu ollenkaan osoitteeksi. Tunnistetaan nyt.
- Katu talonumeroineen jäi paikalleen, kun sitä seurasi heti ilman pilkkua paikkakunnan etuliite "St." (Sankt) (esim. "Hauptstraße 5 St. Pölten", kirjeen otsikko ilman edeltävää postinumeroa) – "St." näytti kappalemäärän yksiköltä, eikä katua siksi tunnistettu ollenkaan osoitteeksi. Tunnistetaan nyt.
- Ovi-/porraskäytävälisäys talonumeron jäljessä (esim. "Lerchenfelder Gürtel 43/12") jäi näkyvästi paikalleen, kun sitä heti seurasi yksittäinen kirjain, joka sattuu vastaamaan mittayksikköä (esim. "h" tunnille) – osoite puhdistettiin tällöin vain talonumeroon asti ilman lisäystä, sen sijaan että se osuisi kokonaan tai ei lainkaan.
- Otsikkorivi ammattinimen kaltaisella sukunimellä ennen etunimeä ("Betreff: Bauer Anna", "Betreff: Bauer, Anna") jäi tähän asti kokonaan tunnistamatta – myös keskellä asiakirjaa edeltävän täyden lauseen kanssa. Tunnistetaan nyt.
- Saksalainen verotunnus välillä, pisteellä tai yhdysviivalla lohkojen välissä (esim. "Steuernummer: 30 815 08153" tai "30.815.08153") jäi tähän asti tunnistamatta – vain vinoviivakirjoitusasu löytyi. Tunnistetaan nyt.
- Nimi lääketieteellisen kenttäotsikon ("Patient:", "Hausarzt:", "Behandelnder Arzt:", "Überweisender Arzt:" ja niiden naisellisten muotojen) jäljessä jäi tähän asti tunnistamatta, kun sukunimi oli samalla tavallinen saksalainen sana (esim. "Patient: Bauer Thomas"). Tunnistetaan nyt.
- Nimi kenttäotsikon "Zahnarzt" jäljessä omalla rivillään (esim. "Zahnarzt", alla "Huber Franz") jäi tähän asti tunnistamatta – ei etu- eikä sukunimeä. "Zahnärztin" ja yksinkertainen "Arzt"-muoto eivät kärsineet tästä. Tunnistetaan nyt.
- Sukunimi sanojen "Herr"/"Frau" jäljessä, jota seurasi virkakielinen fraasi kuten "zur Kenntnisnahme", "zur Unterschrift" tai "zur Weiterleitung", tulkittiin tähän asti liian laajasti ja veti fraasin mukaan nimilöydökseen – ilmauksesta "Frau Petra Klein zur Vertretung in allen Angelegenheiten" korvattiin "Petra Klein zur Vertretung", ja lauseen loppuosa jäi kieliopillisesti silvottuna paikalleen. Todelliset aatelisarvonimet kuten "von der Leyen" tai "zu Guttenberg" eivät kärsi tästä.
- Sama virkakielisen fraasin ylikorjaus koski myös nimeä sähköpostin "To:"-otsikkorivillä, rekisteröintikoodia (C.1/C.1.1/C.1.2), ajokorttikoodia, sulkeisiin kirjoitettua lomakekenttää ("[Vorname]: …") ja pisteetöntä tervehdystä – kaikkialla siellä "zur"/"von" ja muut vetivät seuraavan fraasin kuten "zur Unterschrift" tai "zur Vertretung" mukaan löydökseen, osittain jopa pelkkä partikkelisana jäi nimen jäänteenä tulokseen. Myös täällä todelliset aatelisarvonimet säilyvät täysin.
- Matrikkelinumero otsikkonsa takana jäi tähän asti kokonaan tunnistamatta – "Matrikelnummer 7654321" jäi kokonaan tunnistuksen ulkopuolelle, ei tunnusnumerona eikä kielimallin kautta, koska pelkällä luvulla ei ole tunnistettavaa muotoa.
- Sama koski osallistujanumeroa – "Teilnehmernummer 4471829" jäi kokonaan tunnistuksen ulkopuolelle, ei tunnusnumerona eikä kielimallin kautta.
- Ansioluettelossa nimi otsikon "Persönliche Daten" alla jäi usein osittain tai kokonaan tunnistamatta, kun se oli ilman puhuttelua muodossa "Sukunimi Etunimi" suoraan sen alla.
- Sama koski otsikkoa "Kontaktdaten" – siellä nimi jäi jopa kokonaan tunnistamatta, ei vain osittain.
- Ilmoittautumistodistuksessa tai hakemuslistassa yhdistetyllä sarakkeella "Name, Vorname" (väestörekisterikirjoitusasu, arvo esim. "Mustermann, Max" solussa) nimi jäi kokonaan tunnistuksen ulkopuolelle, kun seurasi vielä toinen sarake kuten syntymäaika.
- Syntymäaika henkilötodistuksessa ja ilmoittautumistodistuksessa tavallisessa muodossa "Geburtsdatum/-ort: 22.07.1978 / Rostock" jäi tunnistamatta – vain pilkkumuoto "Geburtsdatum, Geburtsort: …" osui.
- "Bürgerservice" ja "Bürgerbüro" mustattiin toisinaan virheellisesti paikkana, erityisesti ajatusviivan jälkeen luettelon erottimena (esim. "Wenden Sie sich an das Bürgerservice – Bürgerbüro …").
- Otsikoitu puhelinnumero, jonka rivinvaihto katkaisi keskeltä (esim. kapeasta kirjeen otsikon sarakkeesta tai PDF-tekstin poiminnasta sarakeleveyden kohdalla: "Telefon: 0176 12\n34567"), mustattiin osittain vain puoliksi – rivinvaihdon jälkeinen loppuosa jäi luettavaksi.
- Otsikoitu tunnusnumero (asiakas-, jäsen-, sopimusnumero ja vastaavat), jonka rivinvaihto katkaisi keskeltä (esim. "Kundennummer: K903\n944" kapeasta sarakkeesta), mustattiin vain puoliksi – rivinvaihdon jälkeinen loppuosa jäi luettavaksi.
- Nimi akateemisella arvonimellä ennen ammattinimikettä pilkun jäljessä (esim. "Dipl.-Ing. Sabine Roth, Projektleiterin") jäi täysin suojaamattomaksi – rivi näytti taulukkomaiselta sarakeotsikolta ja hylättiin virheellisesti asiasisältönä.
- Arvonimi "Dr.-Ing." (yleinen saksalainen insinöörin arvonimi) nimen edessä ei sisältynyt naamioituun henkilöarvoon ja jäi luettavaksi – sama yhdysviiva-ansa kuin "Dipl.-Ing." kohdalla.
- Arvonimet "Dipl.-Kfm.", "Dipl.-Kffr." ja "Dipl.-Psych." (kauppatieteiden/psykologian diplomiarvonimet) nimen edessä eivät sisältyneet naamioituun henkilöarvoon ja jäivät luettaviksi – sama yhdysviiva-ansa kuin "Dipl.-Ing." ja "Dr.-Ing." kohdalla.
- MAC-osoite Cisco-kirjoitusasussa pisteillä kaksoispisteiden sijaan (esim. "aabb.ccdd.eeff", kuten kytkinlokit ja tukipyynnöt sen tulostavat) jäi kokonaan tunnistamatta ja luettavaksi.
- Sukunimi sanan "Familie" jäljessä (esim. "Die Familie Gruber unterschreibt den Vertrag") jäi lauserakenteesta riippuen tunnistamatta ja siten luettavaksi – myös aatelisarvonimellä edessä ("Familie von der Leyen").

- Kroatialaisessa osoitteessa ilman erottavaa välimerkkiä postinumeron+paikkakunnan ja kadun+talonumeron välillä (esim. "10000 Zagreb Ulica Ivana Lučića 5") talonumero jäi puhdistamatta.

- Liettualaisessa yhteystiedossa otsikolla "Kontaktinis asmuo" (esim. "Kontaktinis asmuo: Vilkas Jonas") sukunimi jäi tunnistamatta, jos se oli samalla yleinen substantiivi (Vilkas = "susi", Vanagas = "haukka").

- Syntymä- tai asuinmaa ilman muuta otsikointia tanskalaisessa lomakekentässä (esim. "Fødeland: Tyskland" tai "Bopæl: Tyskland") jäi tunnistamatta.

- Syntymä- tai asuinmaa ilman muuta otsikointia romanialaisessa lomakekentässä (esim. "Țara: Germania" tai "Țara de reședință: Franța") jäi tunnistamatta.

- Yrityksen nimi liettualaisen kenttäotsikon "Darbdavys:" tai "Įmonės pavadinimas:" (työnantaja/yritys) alla jäi tunnistamatta.

- Yrityksen nimi venäläisen kenttäotsikon "Работодатель:" tai "Наименование организации:" (työnantaja/yritys) alla jäi tunnistamatta.

- Kirjoitettu päivämäärä kuukauden nimellä romaniaksi (esim. "31 decembrie 2024") jäi tunnistamatta.

- Unkarilainen syntymänimi lyhenteen "szül." takana (esim. "Nagy Éva (szül. Kovács)") jäi tunnistamatta ja pysyi luettavaksi.

- Tallennettu HTML-profiilisivu (tai sähköposti, jonka liitteenä on verkkosivu) saattoi jättää siviilinimen puhdistamatta, jos se oli vain Open Graph -profiilikentissä `profile:first_name`/`profile:last_name`/`profile:username` – nämä kantavat nimen paloiteltuna kuvailevan `og:title`:n sijaan ja puhdistetaan nyt myös.

- Toimitushäiriöilmoitus (bounce/NDR) kantoi usein alkuperäisen toimittamattoman viestin otsikkotiedot (lähettäjä, vastaanottaja, aihe) omassa, kolmannessa liiteosassaan – tämä jäi puhdistetussa versiossa täysin koskemattomaksi. Osa puhdistetaan nyt kuten muukin toimitusraportti.

- Wordin suojatun alueen (Rajoita muokkausta → Poikkeukset, `w:permStart`) yksilöllisesti nimetty käsittelijä jäi selkotekstiin, vaikka sama nimi oli leipätekstissä jo kauan sitten puhdistettu. Se poistetaan nyt myös.

## 0.10.42-alpha.20260827 – 27. elokuuta 2026

### Uutta

- **Nimetyt tunnistusprofiilit tekevät eri työtapauksista yhdellä otteella
  saavutettavia.** Kohdassa *Asetukset → Tunnistus → Mitä poistetaan*
  nykyisen kategoria- ja lajivalinnan voi tallentaa ja ottaa heti uudelleen
  käyttöön valintakentästä. Kiinteä profiili *Vakio* vastaa aiempaa
  toimitustilaa eikä sitä voi poistaa. Profiili muuttaa yksinomaan sitä,
  mitä poistetaan; kieli, tulostyyppi, tunnistuksen syvyys sekä omat termit
  ja hakumallit pysyvät koskemattomina.

- **Tuloksen tyyppi valitaan nyt suoraan ennen puhdistusta.** Yhteinen
  valintakenttä pääikkunassa määrää koko pinolle, asettaako Maskuro
  luettavat paikkamerkit, peittää vai poistaa ilman jälkeä. Kaksi erillistä
  kenttää PDF:lle ja Officelle asetusikkunassa on poistettu; näin tärkeä
  päätös on näkyvissä eikä voi sekalaisessa pinossa enää ajautua tahattomasti
  erilleen. Ohjattu kierros selittää uuden valinnan ennen ensimmäistä
  puhdistusta.

- **Teemat ja vesileimat merkitsevät valmiit PDF:t pyydettäessä selvästi.**
  Kaksitoista kokonaisilmettä sovittavat korvaustekstit ja peittoalueet
  toisiinsa; uusina mukana ovat Pride sekä kevät, kesä, syksy ja talvi.
  *Salainen kansio* tuo suoraan mukanaan vinottaisen `TOP SECRET`-tekstin.
  Tästä riippumatta voi valita vapaan merkintätekstin tai oman kuvan,
  kuvakkeen tai SVG:n väreineen ja peittävyyksineen. Tuodut grafiikat
  upotetaan ilman metatietojaan ja pysyvät saatavilla, vaikka lähdetiedosto
  siirretään. Jälkikäsittelyssä Maskuro korvaa aiemman vesileimansa sen
  sijaan, että asettaisi useita päällekkäin. Tekstivesileimat piirretään
  viimeisenä PDF-kerroksena vaalealla ääriviivalla, jotta ne näkyvät myös
  tummilla kuvilla ja tiheässä tekstissä. Jälkikäsittelyeditori jättää
  Maskuron vesileiman kokonaan huomiotta eikä enää tarjoa sen tekstiä
  peittoehdokkaana.

- **Omat tulostusteemat voi tallentaa ja jakaa.** Nykyinen yhdistelmä
  korvaustekstiä, peittoa ja vesileimaa saa nimen, säilyy asetuksissa ja
  voidaan viedä tai tuoda selkotekstivapaana JSON:na. Mustavalkoinen
  tulostusesikatselu varoittaa heikoista kontrasteista; valinnainen
  onnistumiskonfetti pysyy täysin käyttöliittymän sisällä.

- **Viimeinen vientikoe ja selittävä tarkistusmerkintä päättävät
  esityskierroksen.** Ennen lopullista tallennusta Maskuro vertaa jokaista
  arvontarkasti tunnettua PDF-kohtaa vielä kerran tekstitasossa ja
  renderöidyissä kuvapisteissä; varoitukset mainitsevat vain sivun ja
  koordinaatit. Editorissa *Miksi tämä on peitetty?* näyttää kategorian,
  tunnistustavan ja turvamarginaalin, ei koskaan poistettua selkotekstiä
  eikä koskaan lopullisessa asiakirjassa.

- **Peittopalkit saavat nyt olla kauniita.** Kohdassa *Asetukset → Ulkoasu*
  ovat värioletukset, vapaat värivalitsimet, liu'ut, sateenkaari, raidat,
  pisteet, kukat, tähdet, sydämet, tassut, pilvet, salamat, kahvipavut,
  ankat, auringot, lehdet, lumihiutaleet, paperi-, korostuskynä-, teippi- ja
  toistettavat satunnaiskuviot suoralla esikatselulla. Korvaustekstit saavat
  valinnaisesti värin, liu'un, sateenkaaren, pillerin tai etiketin.
  Kategoriaväritys erottaa nimet, osoitteet, yhteystiedot ja lääketieteelliset
  tiedot. PDF käyttää täyttä muotoilua; Word, PowerPoint, OpenDocument ja
  HTML käyttävät valittua peittävää perusväriä. Suoja ei tässä muutu:
  Maskuro poistaa luottamuksellisen sisällön ensin ja piirtää värin tai
  kuvion vasta tyhjän kohdan päälle.

- **Maskuro on taas saatavilla Linuxille – AppImagena, DEB:nä, RPM:nä ja
  siirrettävänä arkistona.** DEB ja RPM vievät järjestelmään ohjelmamerkinnän,
  tiedostoliitokset, päätekomennon ja kuvakkeen; AppImage toimii ilman
  asennusta. Päivitykset pysyvät olemassa olevalla DEB- tai RPM-asennuksella
  samassa pakettimuodossa ja suosivat muuten AppImagea.

- **Silmämääräinen tarkistus ei enää esitä tavallista PDF-tekstiä toistamiseen
  uutena osumana.** Lopullinen OCR-katse ja näkyvien sivujen turvallinen
  uudelleenrakennus pysyvät täysin käytössä; uudeksi löytölähteeksi lasketaan
  oletuksena vain alueet, joita sivutekstin ja yksittäiskuvan tarkistus ei
  ole vielä lukenut. Näin tuoteriveistä ei tule uusia nimiä tai yrityksiä
  pelkästään toisenlaisen toisen OCR-lukeman takia. Kaksi riippumatonta
  arviota koko näkyvästä tekstistä edelleen haluava kytkee asetuksissa
  päälle *Tarkista koko näkyvä PDF-sivu vielä kerran tietojen varalta*.

- **PDF:iä voi katsella jatkuvana, arkeittain tai aukeamana.** Kolme pientä
  näkymäkuvaketta on alhaalla heti „Leveys”- ja „Sivu”-kuvakkeiden vieressä.
  Jatkuva vierittää arkin reunalla seuraavalle sivulle; Yksittäissivu pitää
  hiiren rullan nykyisellä arkilla; Aukeama näyttää aukeaman, tekee
  klikatusta arkista muokattavan ja siirtää eteen/taakse koko aukeaman
  verran. Sivujen pienoiskuvat ja vertailusuurennuslasi avautuvat lisäksi
  huomattavasti kapeammassa vasemmassa peruspalstassa ja jättävät
  työsivulle enemmän tilaa.

- **Näet nyt, mitä tekoälytaso teki.** Jokaisen ajon jälkeen kohdassa
  „Yksityiskohdat” on jokaiselle tiedostolle rivi siitä – „Tekoälytaso: 12
  rajatapausta tarkistettu, 3 hylätty” –, ja jos se ei löytänyt mitään
  muutettavaa, siitäkin lukee. Aiemmin kallein taso vaikeni kokonaan: sitä,
  kysyttiinkö siltä lainkaan, ei ulkopuolelta voinut päätellä.

  Sitä tarkemmin tarvitseva kytkee kohdassa „Asetukset → Tekoäly” päälle
  *Kirjaa jokainen tekoälykysymys pöytäkirjaan*. Silloin pöytäkirjatiedosto
  tallentaa jokaisesta kysymyksestä koon, keston ja löydösten määrän sekä
  vastapalvelun määrärajan aiheuttaman odotusajan. Sen vieressä oleva
  painike „Näytä pöytäkirjatiedosto” avaa kansion – se sijaitsee
  sovellusdatakansiossa, joka on Windowsissa piilotettu eikä sitä kukaan
  löydä itsestään. Tiedostossa on vain kokoja, ei koskaan tekstiä
  asiakirjoistasi.

- **Maskuro tunnistaa, jos tekoälypalvelusi rajoittaa pyyntöjen määrää.**
  Isännöidyt palvelut sallivat usein vain muutaman pyynnön minuutissa –
  neljä ei ole harvinaista. Ylimääräisiä ei hylätä, vaan ne joutuvat
  odottamaan, ja kahdesta sekunnista vastausta kohden tulee neljäkymmentä.
  Tämä näytti aiemmin siltä, että malli olisi hidas. Nyt Maskuro lukee
  rajan palvelun vastauksesta, ei lähetä enää kysymyksiä yhtä aikaa kuin
  palvelu hyväksyy, mainitsee rajan kohdassa „Tarkista yhteys” ja laskee sen
  mukaan kestoarvioon.

- **Sivunäkymä käyttää nyt Wordiasi, Exceliäsi ja PowerPointiasi – ja on
  siinä noin kuusi kertaa nopeampi.** Aiemmin se tarvitsi LibreOfficea,
  jota harvimmalla toimistotietokoneella on; ilman sitä näkyi painike,
  joka vaati vieraan ohjelman asennusta. Nyt pätee: jos Microsoft Office
  on asennettu, sitä käytetään itsestään – ilman asetusta, ilman latausta,
  ilman että rastitat mitään. LibreOffice jää toiseksi vaihtoehdoksi ja
  on OpenDocument-tiedostoissa jopa ensimmäinen; jos toinen epäonnistuu,
  toista yritetään.

  Ero huomataan varsinkin työskennellessä: jokaisen korvauksen jälkeen
  sivu ladotaan uudelleen, ja se maksaa Officen kautta noin puoli
  sekuntia kolmen sijaan. Asiakirjan ensimmäinen näkymä kestää edelleen
  muutaman sekunnin, sen jälkeen se seuraa toimenpiteitäsi ilman
  odotusaikaa.

  Omaan avattuun Wordiisi ei tällöin kosketa: Maskuro käynnistää oman,
  näkymättömän istunnon, avaa tiedoston vain luku-oikeudella, kytkee
  makrot pois ja lopettaa kaiken, heti kun jälkikäsittely-ikkuna
  suljetaan. Salasanasuojatut tiedostot hylätään sen sijaan, että ne
  jäisivät jumiin näkymättömään valintaikkunaan.

- **Ensiasetus kysyy nyt myös kasvoista, koodeista ja allekirjoituksista –
  ja lataa kaiken puuttuvan kerralla.** Laajennetun tunnistuksen lisäksi
  ensimmäisellä sivulla on kolme kuvakytkintä: tee kasvoalueet
  tunnistamattomiksi, tee viiva- ja QR-koodit tunnistamattomiksi, peitä
  käsin kirjoitetut allekirjoitukset PDF-sivuilla. PDF-rajaus näkyy rastin
  vieressä; Office-tiedostoja ei etsitä automaattisesti allekirjoitusten
  varalta. Rastien alla lukee, montako megatavua „Jatka”-klikkaus maksaa.
  Lataus tapahtuu sen jälkeen **yhdessä** ikkunassa **yhdellä**
  edistymispalkilla kaikkien yhteydessä useiden peräkkäisten
  valintaikkunoiden sijaan; keskeytys päättää koko toimenpiteen eikä jätä
  mitään kesken. Kuka ei halua mitään näistä, poistaa rastit – silloin ei
  myöskään ladata mitään.

- **Esikatselua voi ohentaa tarkistustarpeen mukaan ja sulkea lajeittain.**
  Listan yläpuolella on säädin *Piilota hyvin todistetut*: mitä kauemmas
  oikealle se siirtyy, sitä enemmän se piilottaa vihreästä kohti punaista
  päin; aivan oikealla näkyy enää se, mitä ohjelma yksin arvasi. Klikkaus
  lajin otsikkoon sulkee sen. Molemmat ovat lukemisen apuvälineitä, eivät
  valintaa: mikä on piilotettu tai suljettu, pysyy rastitettuna ja
  korvataan; kuinka moni arvo se juuri nyt on, näkyy säätimen alla.
  Lyhyissä listoissa säädin ei näy. Kahteen palstaan vaihtaminen pitää
  nyt myös *ei koskaan enää* -kytkimet mukana.

- **Kuvaluettelo voi avautua itsestään ennen jokaista ajoa.** Jokaisesta
  kuvasta erikseen päättää haluava asettaa kohdassa „Kuvat” uuden rastin
  *Määritä ennen jokaista ajoa erikseen*. Esikatseluluettelo ilmestyy
  silloin puhdistettaessa itsestään sen sijaan, että klikkaisit „Määritä
  erikseen …” joka kerta itse; jos peruutat sen, mitään ei myöskään
  puhdisteta. Jos valituissa tiedostoissa ei ole yhtään kuvaa, mitään ei
  ilmesty. Oletuksena rasti on pois päältä.

- **Maskuro löytää PDF-sivuilta käsin kirjoitettuja allekirjoituksia ja
  poistaa ne kuvapisteistä.** Aiemmin nimikirjoitus jäi näkyviin
  puhdistetun asiakirjan alle – tekstintunnistus lukee painokirjaimia, ja
  mitä se ei lue, sitä ei korvata. Haku on oma kytkin ja tarvitsee
  tunnistusmallin, joka ladataan kerran jälkikäteen.

  Se löytää mitattuna noin 84 sadasta allekirjoituksesta ja peittää niistä
  noin neljä viidesosaa. Tämä on apu, ei lupaus: jokaisen ajon jälkeen
  raportissa lukee, montako löytyi – myös silloin, kun niitä ei ollut, sillä
  se voi tarkoittaa, ettei niitä ole tai että jokin jäi huomaamatta. 72
  todellisella liikeasiakirjan sivulla ilman allekirjoitusta se ei ole
  keksinyt yhtään.

  **Piirretty** allekirjoitus löydetään, mutta ei poisteta: se koostuu
  viivoista, ei kuvapisteistä, ja palkki sen päällä olisi vain peitto,
  jonka alla viivat pysyisivät. Tällaiset kohdat lasketaan ja mainitaan,
  jotta ne voi peittää itse jälkikäsittely-ikkunassa.

  Word-, Excel-, PowerPoint- ja OpenDocument-tiedostoja ei etsitä
  automaattisesti allekirjoitusten varalta. Käyttöliittymä, ensiasetus,
  mallin lataus, komentorivi ja käyttöohje mainitsevat tämän rajan nyt
  nimenomaisesti.

- **Kierros käy nyt myös esikatselun läpi – ikkunan, jossa päätät.**
  Harjoitusasiakirjalla se avautuu itsestään, vaikka olisit muuten
  kytkenyt esikatselun pois (oma asetuksesi pysyy sellaisena kuin se on).
  Selitetään, mitä värit tarkoittavat, miksi jokaisella rivillä on vain
  yksi kysymys – onko tämä ylipäätään henkilö? – ja mihin „ei koskaan
  enää” on hyvä. Väreissä valokeila on hyvin todistetulla rivillä, yleensä
  IBAN:lla – vihreällä esimerkillä, jonka lause mainitsee; sen jälkeen
  heikoimmin todistetulla, ja siinä voit itse klikata kesken selityksen:
  rasti pois, arvo jää asiakirjaan. Pitkällä listalla ikkuna avautuu
  ohjausta varten suurempana, jotta selitys ei peitä rivejä. Jos ikkuna
  avautuu toisen kerran, kierros kertoo myös miksi – valmis sivu luetaan
  vielä kerran kuvana, ja siinä syntyy katkelmia, jotka näyttävät nimeltä.

- **Editori avautuu ensimmäisellä kerralla suurena.** Alkuperäinen, tulos,
  työkalurivi ja osumaluettelo ovat vierekkäin ja niillä oli aiemmassa
  peruskoossa liian vähän tilaa. Ikkunan pienempään vetävä saa sen koon
  seuraavalla kerralla takaisin – ketään ei ohiteta.

- **Kaksoisklikkaus paikkamerkkiin palauttaa sen** – Wordissa, Excelissä,
  PowerPointissa, OpenDocumentissa, tekstissä, sähköpostissa ja HTML:ssä.
  Ja useamman paikkamerkin yli vetävä ja „Palauta valinta” valitseva
  palauttaa kaikki niiden sisällä olevat kerralla. Hakasuljetta ei siis
  enää tarvitse osua tarkasti. Paikkamerkit, jotka anonymisoitaessa
  tarkoittavat useita eri arvoja, jätetään tästä pois – ne lasketaan ja
  mainitaan, ei arvata.

- **Käyttöohjeessa on luku „Esikatselu ennen korvaamista”.** Ikkuna on
  oletuksena päällä ja on ainoa, jossa päätät – käyttöohjeessa se mainittiin
  aiemmin vain sivulauseessa. Nyt siellä kerrotaan, mitä rasti tarkoittaa
  (se koskee **jokaista** löytökohtaa, ei vain listattua), miksi rivillä on
  vain yksi vastattava kysymys, mitä „ei koskaan enää” pysyvästi aiheuttaa,
  ja miksi ikkuna voi PDF:llä avautua toisen kerran. Kaikissa
  kahdeksassatoista kielessä, ja asetusluettelossa kytkin on nyt myös
  mukana.

### Muutettu

- **Osiossa „Korvatut arvot” on säädin väreille, eikä oppimistila enää
  näy siellä.** Yli kahdeksan arvon kohdalla listan yläpuolella on sama
  säädin kuin esikatseluikkunassa: *Piilota hyvin todistetut* ohentaa
  näytön siihen, mitä todella pitää tarkistaa. Asiakirjaan tämä ei
  vaikuta, ja kuinka monta riviä kuinka monesta näkyy, lukee sen alla –
  hakukenttä ja säädin laskevat yhdessä. Rasti *Oppimistila* on kadonnut
  osiosta; se pysyy valikossa *Työkalut* ja työkalurivillä.

- **Osio „Korvatut arvot” näyttää nyt samat värit kuin asiakirja.**
  Jokainen rivi siinä on väritetty kuten kohta asiakirjassa ja kuten arvo
  esikatselussa: punainen tarkoittaa „arvattu yksin, tässä kannattaa
  katsoa ensin toisen kerran”, vihreä „tunnistettu nimetyllä mallilla”.
  Kunkin lajin sisällä epävarmin on ylhäällä – käyt listan siis läpi
  ylhäältä alas ja näet tärkeimmän ensin. Aiemmin kaikki oli yhtä
  vaaleaa ja aakkosjärjestyksessä.

- **Oppimistila on tehtaalla pois päältä.** Jälkikäsittely-ikkunan
  korjauksen jälkeen ohjelma kysyi aiemmin itsestään, pitäisikö siitä
  tulla oma sääntö. Tämä kysymys tulee kesken työn; sitä tilaamaton
  kokee sen keskeytyksenä. Säännöt haluava kytkee työkalurivin painikkeen
  *Oppimistila* päälle – valinta pätee sen jälkeen pysyvästi, molempiin
  suuntiin.

### Korjattu

- **Viedyt sääntötiedostot merkitään nyt nimenomaisesti
  suojaamisen arvoisiksi.** Omat termit ja poikkeukset voivat niissä olla
  selkotekstinä; lisäksi tiedosto voi sisältää tiivisteen suolan, jolla
  epäiltyjä arvoja voidaan vahvistaa. Onnistunut vienti näyttää siksi
  varoituksen ja kehottaa suojaamaan tiedoston ja luovuttamaan sen vain
  harkiten valtuutetuille vastaanottajille.

- **Viimeinen turvallisuustarkistus ei enää pidätä puhdistettuja
  toimistotiedostoja niiden omien paikkamerkkien takia.** Lajilyhenne
  kuten „SVNR” esiintyy myös merkinnässä `[SVNR1]`; aiemmin tämä laskettiin
  epäillyksi selkotekstin jäänteeksi ja valmis tiedosto hylättiin. Samalla
  puhelinnumerot ja IBAN:it jäljitetään nyt myös siellä, missä Office
  tallentaa saman tiedon ilman näkyviä välilyöntejä viittauksessa tai
  upotetussa tiedostossa.

- **Word, Excel, PowerPoint ja OpenDocument eivät enää jätä myöhään
  löydettyä kenttäkopiota paikoilleen.** Kun arvo tunnistetaan
  ensimmäistä kertaa alitallenteessa tai upotetussa toimistotiedostossa,
  suppea jälkikäynti siivoaa myös aiemmin luetut näkyvät ja piilotetut
  kopiot. Jo syntyneitä viittauspaikkamerkkejä ei silloin korvata
  uudelleen.

- **Word-valintalistan yksittäisessä palautuksessa ei enää tule mukaan
  kutsumatta naapurivalintaa.** Koko alkuperäinen kappale otetaan käyttöön
  vasta, kun sen attribuutit eivät myöskään sisällä avoimia
  paikkamerkkejä.

- **Huonosti luettavat skannaukset menettävät vähemmän yhteen kuuluvia
  tietoja.** Vaihtoehtoinen OCR-lukema puhuttelulla ja kaksiosaisella
  nimellä säilytetään; katunimen katkelma, talonnumero ja postinumero-
  paikkakunta suojaavat yhdessä koko osoiterivin, vaikka se hajoaisi
  naapuri-OCR-lohkoihin. Lasku- ja tuotekentät sekä niiden vieressä olevat
  tapahtumarivit eivät tässä lähde mukaan. Sanan „geboren” jälkeen
  useaan OCR-sanaan ja välimerkkiin hajonnut kelvollinen päivämäärä
  tehdään myös kokonaan tunnistamattomaksi.

- **Onnistumiskonfetti näkyy nyt editorin automaattisessa avautumisessa.**
  Silput suihkuavat suoraan *Puhdista*-painikkeesta sen sijaan, että
  satavat ikkunan yläreunasta. Editori odottaa vain ensimmäistä, 850
  millisekuntia kestävää suihkuvaa pyrähdystä ja avautuu sen jälkeen
  automaattisesti; ilman konfettia viivettä ei edelleenkään ole.

- **Sivunlaskuri ja zoomausrivi eivät enää hyppele näkymäkuvakkeiden
  ylitse liikuttaessa.** Qt jakoi tilarivin vapaan tilan uudelleen aina,
  kun siellä ilmestyi kuvakkeen vihje. Molemmat käyttöelementtiryhmät
  säilyttävät nyt hover-tilassa luonnollisen leveytensä ja kiinteän
  sijaintinsa.

- **Liitetyn tekoälypalvelimen nopeusmittaus epäonnistui aina** –
  jokaisella palvelimella, siitä lähtien kun oma tekoäly on ollut
  olemassa. Se kysyi tiukalla vastausrajalla ja yritti sen jälkeen lukea
  siten katkaistun vastauksen; tämän täytyi epäonnistua, ja tallennettiin
  „ei mitattu”. Seuraukset näkyivät kaikkialla: kestoarvio laski
  palvelimesi mukana toimitetun mallin nopeudella toimistotietokoneella,
  ja asetuksissa luki pysyvästi, ettei nopeutta ole vielä mitattu.
  Mitataan nyt palvelimen tuottamaa määrää, ei sen vastauksen sisältöä.

- **„Maksimaalinen tunnistus (tekoäly) – hidas” näkyi myös silloin, kun se
  ei pitänyt paikkaansa.** Merkintä ja huomautus kuvasivat mukana
  toimitettua mallia toimistotietokoneella – „kielimalli tällä koneella”,
  „suurilla asiakirjoilla jopa tunti”. Oman tekoälypalvelimen liittänyt
  luki siitä kaksi virheellistä asiaa: laskenta ei tapahdu hänen
  koneellaan, ja vastaus tulee sekunneissa tuntien sijaan. Molemmat
  tulevat nyt mittauksesta. Jos mittausta ei ole, sovellus ei enää väitä
  mitään, vaan sanoo, ettei mittausta vielä ole tehty.

- **Palauttaminen toimii nyt myös vedettyyn valintaan.** Useamman
  paikkamerkin yli vetänyt ja *Palauta valinta* painaa halunnut löysi
  painikkeen harmaana: se aktivoitui vain, jos valinta oli **täsmälleen**
  yksi paikkamerkki – kappaleen yli vedettynä se ei koskaan ollut. Reitti
  sen taustalla oli olemassa jo aiemmin, sinne vain kukaan ei päässyt.
  Nyt riittää, että alue merkitään; kaikki sen sisällä olevat paikkamerkit
  palautuvat kerralla.

- **Palauttaminen kaatoi ohjelman, kun vertailusuurennuslasi oli auki.**
  Suurennuslasi muistaa hiiren osoittimen alla olevan kohdan seuratakseen
  sitä alkuperäisessä. Uudelleenlatauksessa peruutuksen jälkeen se palautti
  tämän kohdan muodossa, jota tekstinäkymä ei osannut käsitellä – ja koska
  tällainen virhe keskellä käyttöliittymää lopettaa ohjelman, peruutuksesta
  tuli kaatuminen. Suurennuslasi on peruslähtökohdassa auki, joten se osui
  tavalliseen reittiin.

- **Palautuksen jälkeen näkymä ei enää hyppää asiakirjan alkuun.**
  Pidemmässä kirjeessä jokaisen toimenpiteen jälkeen katosi kohta, jossa
  parhaillaan työskenneltiin. Nyt yläreunassa ollut kappale pysyy yläreunassa.

- **Ilman LibreOfficea sivunäkymä kertoo, mistä se saa alkunsa, sen sijaan
  että vain puuttuisi.** Painikkeet *Sivunäkymä* ja *Peitä PDF:nä* olivat
  lukittuja ja mainitsivat työkaluvihjeessä vain, ettei LibreOfficea
  löytynyt; tietä sinne ei ollut mistään sovelluksessa. Klikkaus avaa nyt
  ohjeen ilmaisen, avoimen lähdekoodin LibreOfficen hankintaan. Käyttöohje
  ja UKK olivat tässä kohdassa väärässä – ne ilmoittivat jälkiladattavasta
  osasta, jota sovellus ei tarjoa.

- **Ennen toimittamista valmis tiedosto haetaan viimeisen kerran täysin
  läpi – nyt myös Wordissa, Excelissä, PowerPointissa, LibreOfficessa,
  sähköpostissa, HTML:ssä ja tekstissä.** Aiemmin vain PDF sai tämän
  viimeisen katseen. Kaikki aiemmat tarkistukset katsovat kohtaan, jonka
  joku on ennalta nimennyt; tallennetta, jota kukaan ei ole huomannut,
  ei siksi kukaan myöskään tarkista. Lopuksi haetaan nyt tylsästi kaikkea,
  mikä on korvattu – jokaisessa paketin osassa. Jos jotain jää paikoilleen,
  tulosta **ei** synny, ja ilmoitus mainitsee arvon. Tiedosto, jota
  pidetään puhdistettuna, on pahempi kuin ei mitään.

- **Merkinnän `<script>` ja `<style>` sisällä olevat nimet ilmoitetaan
  nyt.** Kumpikin pysyy edelleen koskemattomana – siellä on ohjelmakoodia,
  ja korvaus keskellä tunnistetta tekee verkkosivusta rikkinäisen
  verkkosivun. Siitä ei kuitenkaan aiemmin kerrottu, ja se oli virhe:
  tyylisääntö `content: "Anna Musterfrau"` näkyy vastaanottajalle
  **näkyvästi** ruudulla, ja tuloksessa se seisoi edelleen siellä, kun
  ohjelma ilmoitti sivun puhdistetuksi.

- **Asetuksissa lisämallit voidaan taas ladata ja poistaa.** Painike
  „Laajennettu tunnistus”- ja „Maksimaalinen tunnistus (tekoäly)” -kohtien
  vieressä päätyi painettaessa virheraportti-ikkunaan sen sijaan, että
  hakisi mallin. Toinen reitti – tunnistuksen rasti, joka kysyy mallia
  itsestään – ei koskaan kärsinyt tästä.

- **Taulukon lehti- ja aluenimissä olevat nimet ilmoitetaan nyt.** Lehden
  nimi näkyy alhaalla välilehdessä, nimetyn alueen nimi nimikentässä ja
  jokaisessa sitä käyttävässä kaavassa. Kumpaakaan ei edelleenkään
  korvata – kaavat viittaavat niiden kautta, eikä viittausvirheillinen
  taulukko auta ketään –, mutta se lukee nyt siellä. Aiemmin ilmoitus tuli
  vain Excel-taulukon lehden nimestä: nimetty alue „Bezuege_Brunnthaler”
  meni hiljaa mukaan, ja LibreOffice-taulukon kohdalla ohjelma vaikeni
  kokonaan. Lehti „Notizen Ortner” laskettiin siten puhdistetuksi, ja
  vastaanottajan ensimmäinen katse osui nimeen.

  Ilmoitetaan vain se, mikä todella viittaa henkilöön: sana, joka on
  samassa taulukossa muutenkin korvattu, tai osuma, joka valitsee useasta
  sanasta yhden. Yksinäinen sana kuten „Zustaendig” tai „Bezug_Umsatz” ei
  enää laukaise varoitusta – aiemmin se olisi laukaissut, ja varoitus,
  joka tulee joka toisessa taulukossa, jää kolmannen jälkeen kenenkään
  lukematta.

- **„Palauta alkuperäinen” palauttaa nyt todella kaiken.** Joissakin
  asiakirjoissa puuttui sen jälkeen yksittäisiä merkkejä – „Seestraße 14”
  muuttui muotoon „Seestraße 4”, „An:” muotoon „An”, „nordlicht-planung”
  muotoon „nordlicht planung” –, ja yksittäisiä rivejä ei palautunut
  lainkaan. Juuri niissä kohdissa ei sen jälkeen enää voinut valita mitään
  hiirellä eikä peittää mitään: teksti oli kyllä paperilla, mutta ohjelma
  ei enää tuntenut sitä. Tämä koski kapeita merkkejä – ykköstä, kaksoispistettä,
  väliviivaa – asiakirjoissa, jotka asettavat jokaisen merkin erikseen;
  harjoitusasiakirja on yksi niistä.

- **Ja samoja asiakirjoja ei enää muunneta kuvaksi puhdistettaessa.**
  Koska tällainen merkki jäi paikoilleen, jälkitarkistus ilmoitti
  jäänteen ja sivu rasteroitiin varmuuden vuoksi. Sen jälkeen teksti
  siinä oli enää kuva: ei enää haettavissa, ei enää merkittävissä,
  suurempi tiedostossa. Harjoitusasiakirja pysyy nyt molemmilla sivuilla
  todellisena tekstinä.

- **Väriset merkit eivät enää jää palautetun tekstin päälle.** Korvauksen
  peruneen näki värillisen suorakulmion edelleen palautetun sanan
  yläpuolella – se väitti „täältä poistettiin jotain”, vaikka siellä oli
  taas alkuperäinen.

- **Palkki ei enää paljasta, kuinka pitkä sen alla oleva sana oli.**
  Peitettäessä palkki peittää lyhyillä riveillä nyt **koko** rivin –
  osoitelohko, otsikkotiedot, kapea taulukkosolu. Jos koko rivi ei mahdu
  (tavallinen kolmen sarakkeen taulukkorivi), säilyy kenttäkohtainen
  toiminta; leipätekstirivissä se pysyy sanantarkkana, muuten nimi
  keskellä lausetta olisi mustannut koko lauseen. Ja allekkain olevat
  palkit ovat nyt **yhtä pitkiä**: osoitelohkossa jokaisella rivillä on
  arvo, ja kolme eripituista palkkia paljasti edelleen, kuinka pitkät
  rivit olivat. Ne kasvavat vain niin pitkälle kuin paperi on vapaa – ennen
  naapurisaraketta palkki loppuu.

- **„Koko rivi” peittää nyt todella koko rivin.** Aiemmin palkki päättyi
  seuraavaan suurempaan aukkoon – siis kentän loppuun. Leipätekstissä
  tätä ei huomannut, siellä kenttä on rivi; otsikkotiedoissa ja
  taulukoissa kylläkin: merkinnästä „Name: Anna Musterfrau   Abteilung:
  Vertrieb” tuli palkki, joka päättyi täsmälleen nimen viimeiseen
  kirjaimeen – ja siten sen pituus oli taas paperilla. Palkki kulkee nyt
  rivin ensimmäisestä viimeiseen sanaan ja ottaa naapurisarakkeet mukaan.
  Vain arvon haluava valitsee „Sanat”; automatiikka peittää edelleen
  kenttäkohtaisesti.

- **Ennen toimittamista valmis tiedosto haetaan viimeisen kerran läpi.**
  Kaikki aiemmat tarkistukset katsovat kohtaan, jonka joku on ennalta
  nimennyt – sivuteksti, löytösuorakulmio, kuva-alue. PDF:ssä on kuitenkin
  enemmän tallenteita kuin luettelo voi kattaa: huomautukset,
  lomakearvot, kirjanmerkit, asiakirjatiedot, tiedostoliitteet,
  JavaScript. Lopuksi Maskuro hakee siksi kirjoitetusta tiedostosta
  tylsästi kaikkea, mitä se on korvannut – kaikkialta paitsi sivutekstistä,
  jossa sama sanamuoto saa esiintyä sallitusti. Jos jotain jää sinne,
  tulosta **ei** synny, ja ilmoitus mainitsee arvon. Asiakirja, jota
  pidetään puhdistettuna, on pahempi kuin ei mitään.

- **Sitä, mitä ei voitu tarkistaa, ei enää lasketa tarkistetuksi.** Kolmella
  tavalla jälkitarkistuksen epäonnistuminen näytti aiemmin puhtaalta
  tulokselta. Sivu, jonka tekstitasoa ei voitu lukea, laskettiin erityisen
  puhtaaksi – sieltähän ei ollut mitään löydettävissä; se rasteroidaan
  nyt. Jos sivua, jolla oli jäljellä löytökohta, ei voitu vaihtoehtoisesti
  rasteroida, se toimitettiin äänettömästi; nyt puhdistus keskeytyy
  mieluummin. Ja jälkikäsittely-ikkunan vastatarkistus ilmoitti oman
  virheensä jälkeen „ei mitään jäljellä” – ikkunassa ei voinut erottaa
  tätä siitä, että kaikki oli poistettu; nyt näkyy varoitus painikkeineen
  „Rasteroi sivu”.

- **„Palauta oletukset” ei palauttanut useimpia asetuksia lainkaan.**
  Yhdeksän kahdestakymmenestäkahdesta rastista pysyi toimenpiteen jälkeen
  muuttumattomana – niiden joukossa esikatselu, „Avaa puhdistetut
  tiedostot sen jälkeen”, jälkikäsittely-ikkuna, välitön tallennus ja
  molemmat päivitysrastit. Tallennettu tiedosto oli kyllä tyhjennetty,
  mutta ikkuna piti kiinni vanhoista arvoista ja kirjoitti ne seuraavalla
  klikkauksella takaisin. Nyt jokainen rasti palautuu, ja merkintä
  „muutettu” katoaa sen mukana.
- **„Tallenna tarkistusraportti jokaisesta puhdistuksesta automaattisesti”
  näkyi, mutta oli pois päältä.** Palautuksen jälkeen rasti pysyi
  asetettuna, vaikka arvo oli tyhjennetty – raporttia ei enää syntynyt,
  ilman että mikään viittasi siihen. Sama koski tarkistuspöytäkirjaa ja
  omaa näytön tallennusta; niiden pikanäppäin kytketään nyt myös oikein
  päälle tai pois palautuksen yhteydessä.

- **Rivin palkit näyttävät nyt samalta.** Aiemmin jokainen löytökohta toi
  mukanaan oman palkkinsa, ja sen korkeus tuli osuman sanan kirjasimesta.
  Rivillä, jossa oli otsikko ja arvo eri koossa, seisoi siksi vierekkäin
  paksu ja ohut viiva porrastetuin reunoin, ja missä kahta löytökohtaa
  erotti vain välilyönti, jäi niiden yläpuolelle vaalea rako. Saman rivin
  palkeilla on nyt sama ylä- ja alareuna, ja mikä eroaa vain
  välilyönnillä, siitä tulee yksi palkki. Se, minkä pitäisi jäädä kahden
  löytökohdan väliin – pilkku nimen jälkeen, otsikko, summa – erottaa ne
  edelleen toisistaan. Koskee sekä ladottuja sivuja että skannauksia.

- **Kohdan „Tietoja tästä ohjelmasta” välilehdet alkavat taas
  ylhäältä.** Tietosuoja, lisenssiehdot ja lisenssihuomautukset avautuivat
  keskeltä tekstiä – niitä lukevan piti ensin vierittää aivan ylös
  nähdäkseen ensimmäisen rivin.

- **Kynä ei enää avaa toista editori-ikkunaa, vaan tuo olemassa olevan
  esiin.** Aiemmin jokainen klikkaus loi uuden. Ikkunalla ei ole omaa
  merkintää tehtäväpalkissa – sen pienentänyt ei päässyt siihen enää käsiksi
  ja klikkasi uudelleen; pääikkunaa palautettaessa kaikki kertyneet
  ikkunat tulivat sitten kerralla esiin. Nyt muut asiakirjat päätyvät
  avoinna olevan ikkunan välilehtipalkkiin, eikä siellä jo olevalle
  asiakirjalle synny toista välilehteä.

- **„Laajennettu tunnistus” ei enää kanna merkintää „muutettu”, kunhan
  sen malli puuttuu.** Se toimitetaan kytkettynä päälle, mutta ilman
  jälkiladattavaa mallia se ei voi sitä olla – asetuksissa rivi näkyi
  siksi jokaisella vasta asennetulla koneella muutettuna, vaikka kukaan ei
  ollut koskenut siihen. Miksi rasti on pois, kertoo nyt yksin sen
  merkintä: „Mallia ei vielä ladattu”.

- **Esittelynauha selitti Office- ja tekstitiedostoissa PDF-kangasta.**
  Siellä luki „sanaa klikkaamalla se peitetään” – Word-tiedostossa
  klikkaus ei kuitenkaan peitä mitään, siellä merkitään ja painetaan
  sitten painiketta. Se kertoo nyt, mikä kussakin näkymässä pätee.
- **Työkalurivi oli tekstinäkymässä tukossa merkinnöistä.** „Korvaa
  valinta”, „Peitä valinta”, „Palauta valinta”, „Sivunäkymä” ja „Peitä
  PDF:nä” ovat nyt kuvakkeina – kuten sisarensa PDF:ssä. Niiden nimet
  pysyvät pikaohjeessa ja valikossa.
- **Ctrl+hiiren rulla vertailusuurennuslasissa ei liikuttanut sen
  zoomaussäädintä mukana.** Kirjasin suureni, mutta säädin ja sen vieressä
  oleva prosenttiluku väittivät edelleen vanhaa tilaa.
- **Päivityksen asennusohjelma ei tullut esiin** – se piti ensin klikata
  tehtäväpalkista (vain Windows).
- **Vuosiluku rivin alussa laskettiin itävaltalaiseksi
  postinumeroksi.** Ansioluettelossa merkinnästä „2020 Verkaufsstrategien”
  syntyi paikkamerkki – koko rivi katosi. Nelinumeroinen luku välillä
  1900–2099 tarvitsee nyt toisen osoitesignaalin: kadun sen yläpuolella,
  kenttäsanan edessä, maatunnuksen tai tunnetun paikannimen. Osoitelohkoilla
  näitä on; vuosisarakkeilla ei.
- **Kuukausi-vuosi-pari laskettiin puhelinnumeroksi.** Merkinnästä „Seit
  08.2010 123-Verkauft GmbH” syntyi „puhelinnumero” – kuukausi, vuosi ja
  yrityksen nimen ensimmäiset numerot sen jälkeen.
- **Raportissa luki „tarkistettu tekstintunnistuksella” eikä kerrottu,
  mitä se ei lue.** Jos kuvia jätetään ennalleen, siinä lukee nyt, ettei
  käsin kirjoitettua löydetä sen sisältä – allekirjoitus tai käsin
  merkitty nimi jää paikoilleen. Aiemmin tämä lause oli vain skannatuilla
  sivuilla; tavallinen PDF, jossa oli upotettu allekirjoitus, ei saanut
  siitä sanaakaan.
- **Peitetyllä kuvapohjalla oleva paikkamerkki seisoi palkkinsa vasemmassa
  reunassa.** Kun arvo löytyy kuvasta – esimerkiksi kirjoitettu nimi
  skannatun allekirjoituksen vieressä –, kuva-alue on peitettävä koko
  leveydeltä. Lyhyempi paikkamerkki jätti sen viereen paljasta mustaa,
  mikä näytti kahdelta toimenpiteeltä. Se on nyt keskellä palkkia.

## 0.10.41-alpha.20260826 – 26. elokuuta 2026

### Uutta

- **Koejakson jälkeen ikkuna muistuttaa kerran käynnistystä kohden
  lisenssistä.** Se tulee viisi minuuttia käynnistyksen jälkeen – ei heti,
  jotta se ei ole kenenkään tiellä ennen ensimmäistä toimenpidettä – ja
  odottaa, jos puhdistus on käynnissä. Sieltä johtaa yksi tie ostoon ja
  toinen jo ostetun avaimen syöttämiseen; „Myöhemmin” sulkee ikkunan, kun
  painikkeen viisi sekuntia on kulunut. Mitään ei lukita: ilmainen taso
  toimii edelleen ennallaan.

- **Odotusaika ennen ajoa ilmaisella tasolla kestää nyt kymmenen kolmenkymmenen
  sijaan.** Sen tarkoitus on muistuttaa lisenssistä, ei pysäyttää työtä.

- **Kaikki kolme lisenssihuomautusta näyttävät nyt samalta.** Odotusaika,
  muistutus viimeisinä koepäivinä ja huomautus koejakson jälkeen kantavat
  saman raidan, saman rakenteen ja samat painikkeet; jäljellä oleva aika
  on nyt painikkeessa suuren luvun sijaan sen vieressä.

- **Esikatselun osumaluettelo on jälleen allekkain.** Se oli
  yhdeksästä arvosta lähtien kaksipalstainen; läpikäydessä silmä hyppii
  silloin kahden radan välillä, ja tässä ratkaistaan rivi kerrallaan.
  Kaksi rataa haluava kytkee ne takaisin ikkunan vasemmasta alakulmasta –
  valinta muistetaan, ja vaihdettaessa jo poisvalitut arvot pysyvät
  poisvalittuina.

- **Tekoälytaso on avoinna kaikille, jotka liittävät oman tekoälypalvelimen.**
  „Asetukset → Tekoäly” sisältää kaiken tähän liittyvän: liitännän, mitä
  tekoäly saa tehdä, mitä sen tehtäväksi annetaan – ja sen yläpuolella
  kytkimen tälle tasolle vastatarkistuksineen, heti kun palvelin on
  syötetty. Kielimalli, joka laskee omalla työasemalla, pidetään
  edelleen taka-alalla: se tarvitsee kymmenelle sivulle useita minuutteja
  eikä siksi sovi arkikäyttöön.

- **Oman tekoälyn voi liittää.** Mukana toimitetun kielimallin sijaan
  suurempi malli voi vastata toisella koneella – talon sisäisellä
  palvelimella tai vahvalla näytönohjaimella varustetulla
  työasemalla. Vaaditaan OpenAI-yhteensopivan rajapinnan tarjoava
  palvelu (Ollama, LM Studio, llama.cpp-server, vLLM, LocalAI); se
  asetetaan kohdassa „Asetukset → Oma tekoäly” yhteystarkistuksineen,
  joka todella kysyy mallilta, mittaa nopeuden ja selvittää mahdollisen
  vastausmuodon. Useita tekstiosia käsitellään tällöin samanaikaisesti
  peräkkäisen sijaan.

- **Mitä tekoäly saa tehdä ja mitä sen tehtäväksi annetaan, on nyt
  säädettävissä.** Kolme kytkintä ratkaisevat rajatapausten arvioinnin,
  itsenäisen haun ja haun leipätekstistä; mallille annettava ohje näkyy
  sanatarkasti, sitä voi täydentää talon omilla termeillä ja se voidaan
  palauttaa oletukseen napin painalluksella.

- **Jos teksti tällöin poistuu omasta verkosta, siitä varoitetaan ennen
  jokaista ajoa.** Maskuro tunnistaa osoitteesta, sijaitseeko
  tekoälypalvelin talon sisällä, ja mainitsee tunnetun tarjoajan nimeltä.
  Varoituksen voi kytkeä pois, mutta vain nimenomaisella vahvistuksella
  olevansa valtuutettu tähän siirtoon, ja vain juuri tälle osoitteelle.
  Itse toimintoon tämä ei vaikuta: siirto näkyy edelleen pöytäkirjassa ja
  jokaisen tiedoston tarkistusraportissa. Komentorivillä ei kysytä, vaan
  pysäytetään – siellä tarvitaan `--ki-auswaerts-erlauben`.

- **Esikatselu ennen korvaamista on uusissa asetuksissa oletuksena
  käytössä ja koskee nyt myös nimenomaisesti puhdistettua leikepöydän
  sisältöä sekä ohjelmaan liitettyä tekstiä ja kuvia.** Asiakirjapinoissa
  näkyy edelleen täsmälleen yksi esikatselu asiakirjaa kohden kaikkine
  sivuineen; lyhyiden kopioiden hiljainen välitön puhdistus ei
  tarkoituksella avaa ikkunaa.

- **Osumat voi kytkeä päälle ja pois esikatselussa koko värillisen rivin
  alalta.** Rasti on nyt suuri ja kontrastiltaan selkeä; lisäksi
  tilakenttä näyttää „Korvaa” tai yliviivattuna „Korvaa”, jotta valitut
  ja poisvalitut arvot erottuvat heti toisistaan myös tummilla
  luottamusväreillä.

- **Myös PDF:t, joissa on näkyvä turvallisuuden vastatarkistus, avaavat
  esikatselun enää kerran asiakirjaa kohden.** Poisvalitut termit
  pysyvät poisvalittuina myöhempää sivutodistetta varten; sen tarkistus
  jatkuu ilman, että samaa ajoa keskeytetään toisella valintaikkunalla.

- **Korvaussanat näyttävät jälkikäsittely-editorissa samalta myös
  rasteroiduilla sivuilla.** Kun punainen paikkamerkki on kuvapisteissä
  PDF:n tekstitason sijaan, se saa nyt silti saman luottamuksen mukaan
  väritetyn taustapinnan kuin tavallinen PDF-tekstin paikkamerkki.

- **Jo esikatselu ennen korvaamista näyttää löydettyjen termien
  tarkistustarpeen.** Jokainen rivi kantaa saman punainen-oranssi-vihreä
  -värin kuin myöhemmin korvaus editorissa. Kategorian sisällä heikko
  luotettavuus ja punaiset virhehälytysehdokkaat ovat ylhäällä, vahvat
  vihreät todisteet alhaalla; tasapelit pysyvät aakkosjärjestyksessä. Jos
  sama arvo tulee useasta löytökohdasta, lasketaan varmuuden vuoksi
  niiden epäilyttävin arvio. Arvioimattomat erikoistapaukset näkyvät
  neutraalin keltaisina punaisen ja oranssin välissä.

- **Tuloksen voi nyt kopioida suoraan tiedostona jälkikäsittely-
  editorista.** „Kopioi tulos” asettaa nykyisen puhdistetun version
  leikepöydälle sulkematta editoria ja etsimättä tiedostoa uudelleen
  pääluettelosta. Vielä tallentamattomassa käsityössä sitä ennen kulkee
  automaattisesti koko turvallinen tallennusreitti; „Kopioi kuva” säilyy
  erillisenä toimintona pelkille kuvapisteille.

- **Korvatut sanat näyttävät editorissa yhdellä silmäyksellä, mitä pitäisi
  tarkistaa ensin.** Pelkkä kielimallin arvaus on punainen, vaikka spaCy
  ilmoittaisi sille yleisesti 85 prosenttia. Muut tukemattomat
  malliarviot pysyvät korkeintaan oransseina; vahvat nimetyt todisteet
  voivat olla vihreitä. Käsityö ja vanhemmat kohdistukset ilman
  arvioitavaa arvoa pysyvät neutraalin keltaisina. Myös automaattiset
  peittopalkit kantavat näitä värejä editorin esikatselussa – nyt myös
  silloin, kun palkki on osa rasteroitua PDF-sivua. Tähän tarvitaan
  toimiva kohdistus ja todistetusti täysin peittävä musta entinen
  sanalaatikko; tavallista lihavointia ei väritetä. Tallennetussa
  PDF:ssä kaikki palkit pysyvät muuttumatta täysin peittävän mustina.

- **Sen, mikä esikatselussa poisvalitaan, voi muistaa pysyvästi.** Kun
  poistat rastin, sanot: tässä tunnistus erehtyi. Aiemmin tämä koski
  vain tätä yhtä asiakirjaa. Nyt rivillä näkyy kytkin „ei koskaan
  enää”; painettaessa arvo siirtyy pysyvästi listalle „Älä koskaan
  poista” ja katsotaan tästä lähtien vaarattomaksi jokaisessa
  asiakirjassa. Listan alla lukee, mistä tulee pysyvää, ennen kuin
  painat „Korvaa”. Vastakkaista suuntaa ei ole tarkoituksella: mitä
  kerran löydettiin, sen tunnistus löytää uudelleen.

- **Painike palauttaa kaikki asetukset toimitustilaan.** Se on
  asetusikkunan vasemmassa alakulmassa ja kysyy ensin vahvistuksen.
  Tiedostosi, lisenssisi, omat tunnistussääntösi ja automaattikäynnistys
  pysyvät koskemattomina; se, mitä ylläpitosi määrää, pätee edelleen.
  Jokainen toimitustilasta poikkeava asetus kantaa lisäksi merkinnän
  „muutettu” – näin näkee yhdellä silmäyksellä, mitä on muutettu.

### Muutettu

- **Tulosta ei enää tallenneta itsestään – vasta tallennettaessa.**
  Ikkunasta tehty ajo kirjoittaa puhdistetun versionsa ensin väliaikaiseen
  sijaintiin; tiedosto „…_bereinigt” alkuperäisen vieressä syntyy vasta,
  kun painat „Tallenna”. Siihen asti tulosta voi katsella, jälkikäsitellä
  ja kopioida. Jokaisella valmiilla rivillä on siksi tallennuspainike,
  listan alla lukee „Tallenna kaikki”, ja editorissa toimii Ctrl+S.
  Listan tyhjentävältä tai ohjelman sulkevalta kysytään; mitä kukaan ei
  tallenna, se ei jää mihinkään makaamaan. „Näytä kansiossa” on ennen
  tallentamista lukittu – väliaikainen sijainti ei ole kohde, johon
  ketään lähetetään. Kohdistustiedosto kulkee mukana tallennettaessa.

  Asetuksissa kohdassa „Ohjelma” „Tallenna tulokset heti alkuperäisen
  viereen” palauttaa entisen toimintatavan. Komentorivi, kansionvalvonta
  ja leikepöydän vahti tallentavat edelleen muuttumatta heti – siellä ei
  ole ketään, joka voisi tallentaa.

- **Jälkikäsittely-editorin työkalurivi on siistitty.** Oppimistila on
  nyt oikeassa reunassa vertailusuurennuslasin ja „Korvatut arvot”
  vieressä – kolme kytkintä, jotka kytkevät toimintatilan päälle ja
  pois, ovat siten yhdessä. „Siirrä kaikille sivuille” on siirretty
  kolmen peittomuodon viereen, koska se vaikuttaa vain siellä. „Kopioi
  tulos”, „Tiedosto – Palauta” ja „Siirrä kaikille sivuille” eivät enää
  tarvitse merkintää; niiden nimi näkyy edelleen työkaluvihjeessä ja
  valikossa. „Korvaa” ja „Palauta alkuperäinen” välissä on erotin: ne
  ovat vastakkaisia suuntia ja näyttivät vierekkäin kahdelta saman
  työkalun muunnelmalta.

- **„Kopioi tulos” -kuvake näyttää nyt asiakirjaa.** Kaksi lehteä
  taitetulla kulmalla ja tekstiriveillä kahden samanlaisen lehden sijaan,
  joissa oli pieni kulmanuoli. „Kopioi kuva” kantaa vastaavasti
  kuvamerkkiä, jotta molemmat erottuvat ilman merkintää. Tulosluettelon
  „Kopioi”-painike näyttää saman asiakirjamerkin – se tallentaa saman
  tiedoston.

- **Asetukset on lajiteltu ja otsikoitu.** „Tunnistus”-osiossa on nyt
  neljä kappaletta: *Mitä poistetaan*, *Miten korvataan*, *Kuinka
  perusteellisesti haetaan* ja *Ennen ja jälkeen ajon*. Kasvojentunnistus
  ja viiva-/QR-koodit ovat kuvien kohdalla, mistä niitä etsitään;
  „Ohjelma” on jaettu osioihin *Tulostiedostot*, *Käynnistyksessä*,
  *Päivitys*, *Näyttö* ja *Palaute meille*, ja tulostiedoston nimen
  lisäosa on tulostiedostojen kohdalla kielen ja ulkoasun välin sijaan.

- **Laajennettu tunnistus on tehtaalla kytketty päälle**, myös ennen
  kuin sen kielimalli on ladattu. Aiemmin oletusarvo riippui
  mallivarastosta, ja juuri asennettu kone toimi pysyvästi heikommalla
  tasolla. Käyttöönotto-ikkuna tarjoaa mallin ladattavaksi ensimmäisellä
  sivulla ja mainitsee hinnan sen vieressä. Jos malli puuttuu, valintaruutu
  sanoo tämän edelleen sen sijaan, että esittäisi tasoa, joka ei toimi.

- **Kaksi termilistaa on nimetty nyt sen mukaan, mitä ne tekevät:**
  „Poista aina” aiemman „Omat termit” sijaan ja „Älä koskaan poista”
  aiemman „Poikkeukset” sijaan.

- **Esikatseluikkuna on selkeämpi.** Yhdeksästä arvosta lähtien ne ovat
  kahdessa palstassa, rivit ovat matalampia, ja löytökohtien määrä on
  termin perässä sen sijaan, että se olisi oikeassa reunassa.

- **Jälkikäsittely-editorissa korvaaminen tulee ennen peittämistä** –
  työkalurivillä, valikossa „Työkalut” ja sivun oikean klikkauksen
  valikossa. Korvaaminen on tavanomainen tapaus: paikkamerkkiä voi
  klikata ja palauttaa, palkkia ei.

- **Vähemmän päällekkäisiä painikkeita editorissa.** „Tallenna nimellä
  …” ja „Kopioi kuva” löytyvät nyt vain Tiedosto-valikosta, tutuilla
  pikanäppäimillään. Rivillä säilyy kummastakin yksi: Tallenna ja
  „Kopioi tulos” – minne tallennetaan, näkyy joka tapauksessa
  tilarivillä ja on siellä muutettavissa yhdellä klikkauksella.

- **Leikepöydän vahtia ei enää tarjota ensimmäisellä käynnistyksellä.**
  Se puuttuu jokaiseen järjestelmän kopiointitoimintoon; ohjelman
  ensimmäistä kertaa näkevä ei voi arvioida sitä. Asetuksissa se säilyy,
  siellä sen kylkeen kuuluvan lausekkeen kera.

- **Vaalea ulkoasu häikäisee vähemmän.** Ikkunan pohja tuli aiemmin
  kunkin järjestelmän omasta tyylistä ja oli siten ainoa suuri pinta,
  josta kukaan ei ollut päättänyt – Windowsissa lähes valkoinen. Nyt se
  on murrettu valkoinen, sama joka järjestelmässä.

- **Kierros ja käyttöohje selittävät värit.** Mitä punainen, oranssi,
  vihreä ja keltainen korvatun sanan takana tarkoittavat, näkyy nyt
  omana kohtana kierroksella ja kappaleena käyttöohjeessa – kaikissa
  kieliversioissa.

### Korjattu

- **Käyttöohje ja UKK näyttivät paikkamerkkejä, joita ei enää ole.**
  Lyhyempään muotoon siirtymisen jälkeen Maskuro kirjoittaa `[NAM1]`;
  ohjeessa luki edelleen `[NAME1]`, ja lause „Oletusarvoisesti `[NAME1]`”
  oli siten yksinkertaisesti väärä. Seitsemässätoista käännetyssä
  versiossa oli lisäksi **saksankielinen** merkintä oman sijaan –
  espanjalainen lukija näki `[NAME1]`, missä hänen ohjelmansa kirjoittaa
  `[NOMB1]`. Sama koski tulostiedoston päätettä: kaikissa versioissa
  luvattiin `_bereinigt`, vaikka ohjelma luo `_limpiado`, `_nettoyé` tai
  `_除去済み`. Tämä koski myös numeroimatonta muotoa (anonymisoitaessa
  kaikki on `[NAM]`, ei `[NAME]`) ja arvosta johdettua tunnistetta
  tiivistettäessä.

- **Esikatseluikkuna keskeyttää enää kerran asiakirjaa kohden – ja
  toisen kerran vain, jos todella tulee jotain uutta.** PDF luetaan
  kahdella tavalla: kerran sisältövirrasta ja viimeksi renderöidyltä,
  näkyvältä sivulta. Aiemmin kumpikin kysyi erikseen. Nyt pätee: mitä
  päätit ensimmäisessä ikkunassa, se pätee edelleen, eivätkä siellä jo
  olleet arvot palaa uudelleen. Jos taas valmiiden sivujen silmämääräinen
  tarkistus löytää jotain, mitä ei aiemmin ollut missään, se esitellään
  vielä kerran – yksinään, ilman jo päätettyjä arvoja.

- **Esikatseluikkuna kertoo nyt, minkä perusteella pitäisi päättää.**
  „Poista rasti = arvo jää paikoilleen” – mikä kertoo, mitä rasti *tekee*,
  muttei sitä, milloin se pitäisi poistaa – on korvattu tekstillä: poista
  rasti kaikkialta, missä ei ole henkilötietoa; siellä tunnistus on
  erehtynyt. Lisäksi jokainen ikkuna mainitsee, mistä tarkistusajosta sen
  arvot ovat peräisin.

- **Paikkamerkit näyttävät samalta koko asiakirjassa.** Sivuilla, jotka
  rakennetaan OCR-reitillä uudelleen kuvasivuiksi, näkyvät paikkamerkit
  asetettiin aiemmin konekirjoitusfontilla – „[PLZ4]” oli silloin leveä
  ja serifeillä varustettu kapean „[NAM1]”:n vieressä samalla sivulla. Ne
  kantavat nyt samaa serifitöntä kirjasinta kuin kaikkialla muualla eikä
  niitä enää aseteta leveämmiksi kuin sovitukseen suunniteltiin.
  Näkymätön hakukerros säilyttää oman kirjasimensa – se tarvitsee
  luotettavat mitat, ei ulkonäköä.

- **Editorin työkalurivillä ei ole enää päällekkäisiä erottimia.** Missä
  koko työkaluryhmä puuttuu avatulta tiedostotyypiltä – PDF:ssä
  esimerkiksi sivunäkymä ja renderöinti –, molemmat viivat jäivät
  aiemmin aukon ympärille.

- **Palauttamisessa ei enää satunnaisesti jää pelkkää valkoista kohtaa.**
  Jo tarkasti palautettua alkuperäistekstiä ei enää maalata valkoiseksi
  sen poistetun paikkamerkin leveällä, yhdistetyllä laatikolla. Sekaisissa
  teksti- ja kuvapalautuksissa teksti asetetaan lisäksi näkymättömäksi
  vain, jos sivukuva jo kantaa juuri tätä alkuperäistä sisältöä
  näkyvästi. Tämä koskee kehystä, osumapaneelia ja PDF-liitteitä.

- **„Palauta alkuperäinen” ei enää tarjoa turhaan sivun rasterointia.**
  Tiukka jäännöstekstin tarkistus pysyy käytössä peitettäessä ja
  korvattaessa. Palautettaessa se jätetään pois: siellä alkuperäinen
  sisältö palautuu tarkoituksella, ja muuttumattomat naapurisanat
  laajennetussa palautuskehyksessä eivät olleet puhdistusvirhe vaan
  virhehälytys.

- **Editorin läpi kulkeva kierros selittää nyt „Korvaa” ja „Palauta
  alkuperäinen” omina vaiheinaan.** Molemmat työkalut korostetaan
  suoraan rivillä ja kuvataan siten, että vedetty kehys asettaa
  paikkamerkin tai palauttaa tämän kohdan alkuperäisen sisällön
  lähdetiedostosta.

- **Myös maakohtaiset paikkamerkit pysyvät nyt enintään neljässä
  kirjaimessa.** Nämä lajit puuttuivat aiemmin keskitetystä
  lyhennekatalogista ja saattoivat siksi näkyä edelleen kokonaan
  kirjoitettuina, esimerkiksi `[UMSATZSTEUER_ID1]`. Uudet ajot
  kirjoittavat sen tilalle `[UID1]`; kaikki automaattisesti tunnistetut
  saksalaiset ja englantilaiset lajit pysyvät samalla yksiselitteisinä.
  Itse lasketut muiden käyttöliittymäkielten lyhenteet eivät enää kasva
  nimikonfliktissa yli neljän merkin. Omat sääntömerkinnät säilyvät
  muuttumattomina sellaisina kuin ne syötettiin.

- **Korvaaminen käyttää nyt koko todella vapaan rivitilan ennen
  peittämiseen turvautumista.** Aiempi jäykkä raja alkuperäisen sanan
  kolminkertaisessa leveydessä tuotti palkkeja jopa suurelta osin
  tyhjissä lomakekentissä. Myös näkyvän OCR-vastatarkistuksen osumat
  saavat nyt luettavan paikkamerkin, jos PDF-teksti on olemassa; mustana
  pysyvät pelkät kuva-, huomautus- ja vektorisisällöt, valittu
  peittotila sekä todelliset ahtaat kohdat, joihin ei mahdu edes
  yksiselitteinen lyhennetty muoto.

- **Jo näkyvää paikkamerkkiä ei enää kirjoiteta toistamiseen punaisena
  turvallisuusrasteroinnin yhteydessä.** Rasterointi ottaa olemassa
  olevan korvauksen nyt suoraan sivukuvasta ja luo vain näkymättömän
  hakukopion. Jos turvallisuuspalkin täytyy peittää juuri tämä kohta,
  koko todellinen paikkamerkkilaatikko uudistetaan sen lyhyemmän
  alkuperäisen ankkurin sijaan.

- **„Palauta alkuperäinen” merkitsee nyt vain varmoja kohteita vedetyssä
  kehyksessä.** Kaikki sen sisällä korvatut termit syttyvät yksitellen ja
  tarkasti; muuttumaton leipäteksti pysyy koskemattomana. Myös aidot
  vektoriperustaiset peittopalkit merkitään erikseen, jos niiden mustan
  PDF-alueen alla on alkuperäistä tekstiä. Rasteroiduilla sivuilla
  esikatselu jättää tarkoituksella pois oletetun palkkialueen: aiempi
  kuvapistehaku yhdisti siellä kirjaimet, alleviivaukset ja
  taulukkoviivat suuriksi punaisiksi alueiksi väärissä kohdissa. Itse
  palautus ei tästä muutu.

- **Palautettaessa rasteroiduilla sivuilla teksti tulee jälleen
  näkyviin.** Viimeksi siellä jäi tyhjä kohta värillisine
  suorakulmioineen sen päällä. Palautettu teksti oli asiakirjassa,
  mutta sen peitti paikkamerkin valkoinen pohja, joka piirretään
  myöhemmin sivun rakenteessa.

- **Tarkistusvärit eivät enää ole moninkertaisesti päällekkäin.** Sama
  kohta väritettiin jokaisen kohdistuksen merkinnän mukaan – sivulla
  viisi todellista löytökohtaa, kukin viisinkertaisesti ylimaalattuna,
  kunnes vaaleasta merkistä tuli tiivis lohko. Eivätkä ne enää ilmesty
  sanoihin, joita ei lainkaan korvattu: jos alkuperäinen arvo on yhä
  sivulla, siellä ei myöskään ole enää merkkiä.

## 0.10.40-beta.1 – 24. elokuuta 2026

### Korjattu

- **Editorin peittopalkeilla on nyt turvamarginaali.** Sana-, rivi- ja
  vapaat kehykset peittävät myös yli ulottuvat glyyfit ja tasoitetut
  reunapikselit; renderöintitarkistus varmistaa lisäksi, ettei näkyviä
  jäänteitä eikä luettavaa alkuperäistekstiä jää paikoilleen.

- **Korvaustekstit pysyvät luettavina ja yhtenäisen lyhyinä.** Uudet
  nimet, osoitteet ja vapaat termit näkyvät esimerkiksi muodossa
  `[NAM1]`, `[ADR2]` ja `[BEG3]`. Kiinteä alaraja on 4,5 pistettä; tilan
  loppuessa lyhennetään ensin ja käytettävää riviä laajennetaan. Vanhat
  kohdistukset pitkillä paikkamerkeillä pysyvät luettavina ja
  palautettavina.

- **Osumapaneelin moniosaiset korvaukset on suojattu kaksinkertaisilta
  merkeiltä ja alkuperäisjäänteiltä.** Regressio kestää sekä numeroiduilla
  että ilman numeroituja paikkamerkkejä; jokaiselle löytökohdalle jää
  täsmälleen yksi yhteinen kohdistus.

- **Palautettua leikepöydän sisältöä ei enää puhdisteta heti uudelleen
  macOS:ssä.** Vaikka järjestelmän allekirjoitus vaihtuu kirjoittamisen
  jälkeen viiveellä, Maskuro tunnistaa oman sisältönsä luotettavasti.

### Uutta

- **Editori voi palauttaa tiedoston kokonaan juuri puhdistettuun
  lähtöversioon.** „Tiedosto – Palauta” hylkää vahvistuksen jälkeen
  nykyisen välilehden kaikki jälkikäsittelyt, mukaan lukien
  korvausluettelon ja laskurit. Komento on lukittu ilman muutoksia ja se
  voidaan puolestaan kumota „Kumoa”-toiminnolla.

- **Siirretyt päivämäärät säilyttävät kronologiansa nyt luotettavasti
  useiden tiedostojen yli.** Yhteinen siirtymä ankkuroidaan pysyvästi
  sääntöihin jo strategian kytkemisen yhteydessä; lisäksi siirtymä ei
  voi enää olla nolla päivää ja siten jättää todellista päivämäärää
  huomaamatta paikoilleen.

- **PDF:n käsityö kattaa nyt koko ammattimaisen peittotyönkulun.**
  Yksittäisiä termejä, listoja ja säännöllisiä lausekkeita voi hakea
  avatussa PDF:ssä tai kaikista kansion PDF:istä ja peittää turvallisesti;
  kokonaiset sivut ja sivualueet ovat suoraan valittavissa. Väri, neutraali
  valkoinen alue, päällekkäinen teksti, kirjasin, tasaus ja toisto
  esikatsellaan suoraan, uudelleenkäytettäviä koodeja voi hallita sekä
  viedä ja tuoda. PDF-puhdistus poistaa valinnaisesti kaikki piilotetut
  sisällöt täydellä uudelleenrakennuksella tai valitut tietoluokat.
  Turvallisin valinta on selvästi suositeltu, virheelliset hakumallit
  selitetään, ja kansioajot kirjoittavat yksinomaan tuloskopioita.

- **Vapaaehtoinen käyttötilasto näyttää nyt asennukset ja
  versionvaihdot.** Maskuro luo tätä varten satunnaisen, paikallisesti
  tallennetun asennustunnisteen. Se ei sisällä laite-, käyttäjä- eikä
  lisenssitietoja; palvelin tallentaa vain sen SHA-256-arvon. Tilasto
  pysyy asetuksissa täysin kytkettävissä pois päältä.

- **Kierros on nyt ohjattu harjoitus molempien ikkunoiden läpi.** Se
  lisää keksityn harjoitusasiakirjan itse listaan, selittää tien
  puhdistamiseen asti ja jatkuu ajon jälkeen automaattisesti editorissa.
  Kierroksen keskeyttävä lopettaa myös tämän jatkon.

- **Yritykset viidestätoista muusta oikeusjärjestelmästä
  tunnistetaan.** Baltiasta, Belgiasta, Skandinaviasta, Tšekistä,
  Puolasta, Kaakkois-Euroopasta, Singaporesta, Brasiliasta tai
  Meksikosta peräisin olevia asiakirjoja puhdistava ei enää menetä
  yritysten nimiä siksi, että niiden oikeudellinen muoto oli
  tuntematon – uutena mukana ovat muun muassa OÜ, MTÜ, SIA, VZW, ASBL,
  P/S, Sh.p.k., EIRELI, z.s., o.p.s., S.K.A., Pte. Ltd. sekä S.A. de
  C.V. ja S. de R.L.

### Muutettu

- **Editorin työkalurivit käyttävät tilaansa nyt tarkoituksenmukaisemmin.**
  Yksiselitteiset vakiokuvakkeet ja suoraan tunnistettavat työkalumuodot
  näkyvät rivillä ilman toistuvaa tekstiä; monimerkityksiset toiminnot
  säilyttävät nimensä. Kohdasta „Näkymä” voidaan kytkeä pois
  „Näytä työkalujen merkinnät”, jolloin molemmat rivit tiivistyvät
  kokonaan kuvakkeiksi. Työkaluvihjeet ja valikot pysyvät tällöin täysin
  merkittyinä, ja valinta muistetaan.

- **Oppimistila näkyy nyt pysyvästi työkalurivillä.** Sen voi kytkeä
  siellä suoraan päälle ja pois, myös silloin, kun korvattujen arvojen
  osio on suljettu. Työkalurivi, Työkalut-valikko ja osion aiempi rasti
  näyttävät aina saman tilan.

- **Vertailusuurennuslasin „Palauta” palauttaa nyt vain sen
  zoomauksen.** Painike palauttaa oletuksen 125 prosenttia telakoimatta,
  siirtämättä tai muuttamatta suurennuslasin ikkunakokoa. Koko asettelusta
  vastaa edelleen „Palauta näkymä”.

- **Virheistä ja toiveista voi nyt ilmoittaa myös Ohje-painikkeen
  kautta.** „Ilmoita virheestä …” ja „Esitä toive …” löytyvät nyt sieltä
  samoin kuin klassisesta Ohje-valikosta; molemmat reitit avaavat jo
  olemassa olevan turvallisen virheilmoituksen tai julkisen toivelistan.

- **Tehtäväpalkin valikko on lyhyempi ja selkeämmin järjestetty.** Kaksi
  globaalilla pikanäppäimellä varustettua komentoa – leikepöydän
  puhdistus ja kuvakaappaus – ovat nyt suoraan allekkain yhteisellä
  oikeanpuoleisella pikanäppäinsarakkeella. „Palauta viimeisin
  alkuperäinen sisältö” on poistettu sieltä; ymmärrettävämpi
  palautuspainike pysyy käytettävissä pääikkunassa.

- **Oikeudelliset sivut ovat suoraan saatavilla kohdasta „Ohje →
  Oikeudellista”.** Alavalikko johtaa lisenssiehtoihin,
  tietosuojaselosteeseen, yhteystietoihin ja yleisiin ehtoihin
  osoitteessa maskuro.com. Peruutusohjeet pysyvät ostohetkellä
  verkkosivustolla.

- **Käsin peitetyt PDF:t rakennetaan tallennettaessa kokonaan
  uudelleen.** Näkyviin jäävät sivut ja niiden uudelleen luettu
  hakukerros; metatiedot, tiedostoliitteet, kirjanmerkit, kommentit,
  lomakearvot, piilotetut tasot, hakuindeksit, skriptit, rajatut
  sisällöt ja muiden objektien sisään piilotetut sisällöt eivät siirry
  tulostiedostoon. Kirjasin ja vektorigrafiikka koostuvat sen jälkeen
  kuvapisteistä – se on hinta todistettavasta rajasta vieraaseen
  PDF-objektipuuhun.

- **Ctrl+Vaihto+B ottaa nyt oletuksena Maskurolla kuvakaappauksen
  kaikissa järjestelmissä.** Print Screen -näppäin ja sen yhdistelmät
  pysyvät edelleen mahdollisina omana asetuksena. Tehtäväpalkin
  kuvakkeen valikossa globaalit pikanäppäimet näkyvät nyt oikealla
  niihin liittyvien komentojen vieressä. Omat tallennetut asetukset
  säilyvät.

- **Editori käynnistyy sivuilla ja vertailusuurennuslasilla
  vasemmalla.** Sivuosio on ylhäällä, avattu alkuperäisen
  suurennuslasi heti sen alla; korvatut arvot pysyvät oikealla.
  Tarkoituksella tallennettu oma järjestys menee edelleen edelle.

- **Harjoitusasiakirja ei enää pysy jatkuvasti pääikkunassa.** Se on
  osa ohjattua harjoitusta ja pysyy lisäksi saatavilla kohdasta
  „Ohje”.

- **Ensimmäinen käynnistys johtaa suoraan käytännön harjoitukseen.**
  Kuvitettua pikaopasta ei enää tarjota toisena, sisällöltään
  päällekkäisenä aloitusreittinä; se pysyy aina saatavilla kohdasta
  „Ohje → Pikaopas”.

- **Lepotilassa oleva tehtäväpalkin kuvake pysyy täysvärisenä.** Se
  näyttää nyt saman voimakkaan Maskuro-kilven kuin aktiivinen
  leikepöytätila; vain aktiivisen valvonnan aikana lisätään vihreä
  merkkivalo.

- **Harjoitusasiakirja pysyy Maskurossa.** Aloituspainike luo
  keksityn PDF:n ja lisää sen suoraan tiedostoluetteloon, mutta ei enää
  käynnistä ylimääräistä PDF-katseluohjelmaa.

- **Haku jälkikäsittely-ikkunassa pysyy sujuvana kirjoittaessa.** Tila
  löytölaskurille varataan jo avattaessa; sen ensimmäinen teksti ei
  enää muuta kangasta eikä käynnistä uutta PDF-rasterointiajoa.

- **Valmistajien nimet valmistetietomerkinnöissä pysyvät näkyvissä.**
  Merkintä kuten „Fabrikat: TRILUX oder gleichwertig” kuvaa tarvittavaa
  tavaraa eikä sitä enää peitetä yritykseksi pelkän tämän merkinnän
  perusteella. Toimittaja-, yritys- ja valmistajakentät pysyvät tästä
  koskemattomina.

- **Korpusmittaukset laskevat liian laajasti peitetyt osumat
  virhehälytyksiksi.** Kun Maskuro poistaa odotetun nimen mutta ottaa
  mukaan myös lauseen osan, virhehälytysten määrä nousee nyt. Raportti
  ilmoittaa ylilyönnit lisäksi erikseen; aiemmat virhehälytysmäärät eivät
  siksi ole suoraan vertailukelpoisia.

### Korjattu

- **Teknisiä ja viranomaistermejä saksankielisistä alkuperäisasiakirjoista
  peitetään harvemmin niminä tai paikkoina.** Ajoneuvon varusteet,
  nimike- ja summarivit, hankinta- ja tietosuojatermit, lakiviittaukset
  sekä julkisten aineistojen tiedostonimet jarrutetaan vain niiden
  todistetussa asiayhteydessä. Tekstintunnistuksessa kadonnut
  umlaut sanassa „Marz 2026” pysyy suojattuna kuukautena; „Marz” ilman
  päivämääräyhteyttä voi edelleen olla todellinen nimi tai paikka.

- **„Palauta alkuperäinen” ottaa heti täyden tarvittavan leveyden.**
  Jos kehys osuu vain yhteen kohdistetun arvon sanaan, Maskuro laajentaa
  sen kohdistuksen ja alkuperäisen rivin perusteella itsenäisesti koko
  tietoon – esimerkiksi sanasta „Planungs” muotoon „Nordlicht Planungs
  GmbH”. Sen jälkeen tavoitettavissa oleva kehys näyttää myös todella
  palautetun kokonaisleveyden.

- **„Palauta alkuperäinen” näyttää mustat palkit nyt yksiselitteisenä
  kohteena.** Osoitettaessa tai vedettäessä koko tunnistettu palkki
  syttyy punaisena vaalealla kontrastiääriviivalla sen sijaan, että vain
  vaikeasti kohdistettava tekstilaatikko sen vieressä syttyisi. Tämä
  koskee myös rasteroituja sivuja, joilla palkki koostuu enää
  kuvapisteistä.

- **Editorin kierros ei enää jätä väliin vaiheita, jos osiot olivat
  suljettuina.** Kierrosta varten Maskuro avaa ja järjestää tilapäisesti
  itse sivuosion, vertailusuurennuslasin ja korvatut arvot. „Valmis”-
  painikkeen tai keskeytyksen jälkeen henkilökohtainen järjestys palaa.
  Jos työkalu ei jonkin asiakirjatyypin kohdalla ole periaatteessa
  saatavilla, sen selitys jää tekstivaiheeksi sen sijaan, että se
  katoaisi huomaamatta.

- **„Korvaa” pysyy näkyvissä myös PDF:n turvallisuusvarajärjestelmässä.**
  Jos Maskuron piti rakentaa sivu uudelleen kuvana jääneen merkin tai
  vaurioituneen tekstikulun takia, oikeat korvaukset näkyivät aiemmin
  vain näkymättöminä hakukerroksessa, ja sivulla oli mustia palkkeja.
  Todella asetetut korvausarvot pysyvät nyt näkyvästi punaisina ja
  haettavina kaikkien rasteroitujen ja OCR-uudelleenrakennettujen
  sivujen yli.

- **Puhdistetun version yläpuolella olevat huomautukset pysyvät luettavina
  tummassa ulkoasussa.** Versio-otsikko, käyttörivi ja johdanto ottavat
  kirjasinvärinsä nyt suoraan todella näytetystä Qt-ikkunasta.

- **Peittokehykset ovat taas tekstin päällä rasteroiduilla PDF-
  sivuilla.** Näkymättömät sanalaatikot olivat alkuperäisestä
  kirjasimesta riippuen kapeampia kuin näkyvät kirjaimet. Tämän vuoksi
  palkkiin syntyi aukkoja tai viimeinen kirjain jäi luettavaksi.
  Laatikot säilyttävät nyt näkyvän sanan leveyden, korkeuden ja suunnan.

- **„Mitä on uutta” alkaa taas aivan ylhäältä.** Muutosluettelo-ikkuna
  asettaa ikkunan valmiiksi rakentumisen jälkeen tekstikohdistimen ja
  vierityspalkin nimenomaisesti alkuun sen sijaan, että se käynnistyisi
  Qt-version mukaan keskeltä uutuuksia.

- **Sulkeminen skannauksen sanantunnistuksen aikana pysyy hiljaisena.**
  Juuri valmistumassa oleva OCR-taustaajo ei enää lähetä jo suljettuun
  jälkikäsittely-ikkunaan.

- **Suhteellisia ajanilmauksia ei enää lasketa nimiksi.** Kiinteät
  ilmaukset kuten „tänään”, „eilen”, „huomenna” ja „ensi viikolla”
  Maskuro tuntee nyt kunkin asiakirjakielen virallisista
  kalenteritiedoista.

- **Sulkeminen ensimmäisen mallin latauksen aikana siivoaa siististi.**
  Maskuron tai jälkikäsittely-ikkunan heti avaamisen jälkeen sulkeva ei
  jätä prosessin sulkemisen yhteydessä vielä natiivissa
  kielentunnistuksessa toimivaa säiettä. Tämä estää satunnaisen
  kaatumisraportin sulkemisen yhteydessä; jo käynnissä oleva lataus
  saatetaan järjestäytyneesti loppuun.

- **Viivästyneet käynnistysvalintaikkunat eivät enää näy sulkemisen
  jälkeen.** Pääikkunan pian käynnistyksen jälkeen sulkeva ei saa
  myöhemmin näkymättömänä tai myöhästyneenä kysymystä parhaasta
  tunnistuksesta, uutuuksista tai johdannosta.

- **HTML ja sähköposti säilyttävät rivinvaihtonsa.** Windowsissa
  HTML-sarjallistus sekoitti puhdistuksen ja palautuksen jälkeen LF:n ja
  CRLF:n. Sisältö ja muotoilu olivat oikein, mutta tiedosto ei enää
  ollut tavutasolla sama. HTML-tiedostot ja MIME-viestit noudattavat
  nyt taas lähteensä kirjoitustapaa.

- **Yritysten nimet, joissa on suhdesana, pysyvät kokonaisina.**
  Sanan jälkeen Maskuro katkaisi aiemmin nimiä kuten „Gesellschaft für
  Systemtechnik mbH” tai „Bank für Arbeit und Wirtschaft AG” sanaan
  „für”. Koko yrityksen nimi tunnistetaan nyt; todelliset
  lauseenalut kuten „Wir sind bei Alpha GmbH versichert” pysyvät
  näkyvissä.

- **Kiinalaiset yritysten nimet pysyvät kokonaisina ennen niiden
  oikeudellista muotoa.** Verbiksi tulkittava tuotemerkin osa saattoi
  yksiselitteisestä lisäyksestä „有限公司” huolimatta hylätä koko nimen.
  Kirjoitusjärjestelmissä ilman iso- ja pienaakkosia virallinen
  oikeudellisen muodon ankkuri saa nyt etusijan tämän epävarman
  sanaluokkarajan edellä.

- **PDF-sivuja muutettiin turhaan kuviksi.** Moninsivuisissa PDF:issä,
  joiden sivut jakavat kirjasinluettelon – kuten tavalliset tuottajat
  tekevät –, kaikki ensimmäisen sivun jälkeiset sivut menettivät
  viittauksensa kirjasimiinsa. Seuraus oli kaksinkertainen: umlautit
  eivät enää olleet tuloksessa haettavissa („Auftragsbestätigung" ei
  löytynyt), ja jälkitarkistus piti tämän jälkeen kirjaimia huomaamatta
  jätettyinä, vaikka niitä ei koskaan ollut sivulla – se rasteroi
  ehjät tekstisivut kuviksi, jolloin ne eivät enää olleet haettavissa,
  kopioitavissa eivätkä selvästi pienempiä. Tarkistuskannassa tämä
  koski neljää seitsemästätoista sivusta.
- **Pelkkä pilkku ei enää laukaise rasterointia.** Jos löytöalue
  päättyy sanaan, sen vieressä oleva välimerkki kuuluu vielä juuri ja
  juuri mukaan. Pilkku tai piste ei kuitenkaan ole huomaamatta jäänyt
  tieto, ja rasterointi maksaa koko sivun. Kirjaimet ja numerot ovat
  edelleen muuttumatta syy jälkiterotukseen.

## 0.10.38-alpha.20260824 – 24. elokuuta 2026

### Uutta

- **Yritysten nimet ilman oikeudellista muotoa tunnistetaan nyt, kun niiden
  merkintä nimeää ne.** „Lieferant: Kranzbichler Handels GmbH" poistettiin
  aina jo aiemminkin – oikeudellinen muoto paljastaa yrityksen. „Lieferant:
  Dehner Märkte" jäi paikoilleen, ja tarjouksissa, kilpailutuksissa ja
  tilauksissa toimittaja näkyy useimmiten juuri näin. Sama koskee
  merkintöjä „Firma:", „Hersteller:", „Fabrikat:", „Arbeitgeber:" ja
  niiden vastineita kahdeksassa muussa kielessä, myös silloin, kun
  merkintä on omalla rivillään ja nimi sen alla.

  Se, mikä merkinnän jälkeen *ei* ole yritys, jää koskemattomaksi:
  „Lieferant: siehe Anlage" ei peitetä – muuten siellä lukisi „Lieferant:
  [ORGA1]", ja se väittäisi nimeä, jota ei koskaan ollut. Merkinnät,
  joiden takana yhtä usein on ihminen („Kunde:", „Auftraggeber:"), on
  tarkoituksella jätetty pois.

- **Kuvan voi nyt myös muokata sen liittämisen jälkeen.** Ikkunassa
  „Puhdista kuva" on „Kopioi tulos" -painikkeen vieressä painike *Muokkaa
  editorissa*: kuva puhdistetaan ja avataan sitten jälkipeittoa,
  merkintöjä ja korostuksia varten – sama reitti, jonka kuvakaappaus
  kulkee.

- **Numerot merkintänsä jälkeen löytyvät nyt myös silloin, kun ne
  nimeävät liikekumppanin.** Aiemmin poistuivat asiakas-, sopimus- ja
  henkilöstönumerot; nyt myös velallis-, velkoja- ja
  toimittajanumerot, itävaltalainen työnantajan tunnus, ANKÖ-rekisteröinti
  sekä valmistajan WEEE-, EAR- ja EPR-numero – saksaksi ja englanniksi.
  Lisäksi Maskuro ymmärtää nyt ladottujen tarjousotsikoiden kirjoitustavan,
  jossa on välilyönti ennen kaksoispistettä ("Kunden-Nr : K903944"). Tuote-,
  tilaus-, toimeksianto-, tarjous- ja laskunumerot pysyvät edelleen
  koskemattomina: ne nimeävät tapahtuman tai tavaran, ei ihmistä. Ne
  poistaa haluava tallentaa ne omana hakumallinaan.

- **Näet nyt, kuinka kauan tiedosto kesti.** Valmiilla rivillä kesto näkyy
  tunnistetun kielen vieressä ("fertig · Deutsch · 2,4 s"),
  yhteenvedossa koko ajon kesto, tunnuslukujen osiossa summa – ja
  tarkistusraportissa se on oma kenttänsä. Useilla tiedostoilla rivi
  paljastaa, mikä niistä vei aikaa.

- **Järjestelmän OCR:n tukemattomia kirjoitusjärjestelmiä voidaan lukea
  korvaavasti, jos sopiva kielitiedosto on olemassa.** Aiemmin: jos
  järjestelmän oma tekstintunnistus ei osaa kirjoitusjärjestelmää
  (Macilla esimerkiksi devanagari), tuloksessa luki "Kuva(t) EI
  tarkistettu(ja)", ja kuvassa olevat tiedot jäivät paikoilleen. Nyt mukana
  toimitettu tekstintunnistus astuu väliin, kun sopiva kielitiedosto on
  saatavilla. Koska näin luettu kuva on epävarmempi kuin tavallisesti
  tarkistettu, se lukee tuloksessa: "luettu korvaavalla menetelmällä –
  tarkista itse". Mitattuna hindin kokeen aiemmasta välitilasta: **kymmenen
  tietoa lisää löydetty ja neljä virhehälytystä vähemmän** (64 % → 73 %).
  Nykyinen lopullinen arvo on ylempänä eikä sitä pidä sekoittaa tähän.

- **Tekstintunnistus kysyy oikeaa kieltä.** Kaikille muille
  asiakirjakielille kuin saksalle ja englannille käytettiin aiemmin
  englanninkielistä tunnistusmallia, vaikka sopiva kielitiedosto olisi
  ollut saatavilla. Windowsissa tämä koski jokaista kieltä – kreikka,
  japani tai hindi luettiin siellä englantilaisella mallilla.

- **Käyttöönotto-ohjattu aivan ensimmäisellä käynnistyksellä.** (Maskuroa
  jo käyttänyt ei saa sitä – "ensimmäinen käynnistys" tarkoittaa
  ensimmäistä käynnistystä, ei ensimmäistä käynnistystä tämän päivityksen
  jälkeen.) Kolme kysymystä kuuden kuvan sijaan: asiakirjojesi kieli,
  luetaanko kuvissa oleva teksti mukana, ja miten haluat tavoittaa
  Maskuron arjessa. Lopussa on edelleen kolme reittiä –
  harjoitusasiakirja, kierros tai kuvitettu pikaopas. Kaiken voi
  ohittaa, ja "Ohje → Käy käyttöönotto uudelleen läpi" tuo sen takaisin.

- **F1 avaa käyttöohjeen sopivasta luvusta.** Pääikkunassa, asetuksissa
  (sivun mukaan), tarkistusikkunassa ja kielten hallinnassa;
  jälkikäsittely-ikkunassa Vaihto+F1:llä, koska F1 näyttää siellä aina
  näppäinkomennot. Aiemmin ohje alkoi aina alusta, 25 luvun kohdalta.

- **Uusi ensimmäinen käyttöohjeen luku: "Aloita kolmessa minuutissa".**
  Neljä vaihetta, enempää asiakirja ei vaadi – kaikissa 18 kielessä.

- **Kierros ikkunan läpi.** "Ohje → Kierros ikkunan läpi" korostaa yhden
  käyttöelementin kerrallaan ja kirjoittaa sen viereen lauseen –
  pääikkunassa kahdeksan vaihetta, jälkikäsittely-ikkunassa seitsemän.
  Toisin kuin kuvitettu pikaopas, se selittää sen ikkunan, jonka edessä
  juuri istut. Voit keskeyttää milloin tahansa Esc:llä.

- **Harjoitusasiakirja vaarattomaan kokeiluun.** Tallennusalueen alla on
  nyt "Avaa harjoitusasiakirja" (myös Ohje-valikossa). Se luo keksityn
  lehden – nimi, osoite, puhelinnumero, IBAN, sosiaaliturvatunnus – ja
  lehdellä lukee samalla, mitä sillä voi tehdä ja mitä sen jälkeen näet.
  Yksikään sana siinä ei kuulu todelliselle henkilölle; ensimmäisen
  Maskuron läpi lähettämäsi asiakirjan ei siis tarvitse olla oikea.

- **"Vain tarkista …" on nyt "Puhdista"-toiminnon vieressä.** Se näyttää,
  missä henkilötietoja on – tiedosto, laji ja määrä – muuttamatta tai
  kirjoittamatta mitään. Asiakirjan tallentanut voi näin tarkistaa ensin,
  ennen puhdistusta. Aiemmin tämä reitti oli vain Tiedosto-valikossa
  kohdassa "Tarkista kansio …" ja koski koko kansiota tallennettujen
  tiedostojen sijaan.

- **Jos mitään ei löytynyt, siitä lukee nyt, mistä se voi johtua.**
  Esimerkiksi: tiedostossa on kuvia, mutta "Tarkista myös kuvissa oleva
  teksti" on pois päältä. Tai: asetettu kieli ei vastaa asiakirjan
  kieltä. Ja jos mikään näistä ei päde, Maskuro sanoo sen myös.

- **Jälkikäsittely-ikkuna tervehtii ensimmäisellä kerralla kolmella
  lauseella:** klikkaus peittää sanan, veto peittää alueen, oikealla ovat
  korvatut arvot. "Ymmärretty" poistaa huomautuksen pysyvästi; "Ohje →
  Näytä johdanto uudelleen" tuo sen takaisin.

- **Sanoja voi klikata nyt myös skannatuilla sivuilla.** Aiemmin sanoja
  saattoi klikata vain siellä, missä PDF tuo mukanaan tekstitason – skannauksessa
  se ei onnistunut, ja samassa asiakirjassa se saattoi vaihdella sivulta
  toiselle. Tällaiset sivut luetaan nyt kerran tekstintunnistuksella;
  sen jälkeen sanoja klikataan kuten kaikkialla muualla. Tilarivi kertoo,
  mitä juuri tapahtuu.

- **Sivuosio on jälleen alue.** Se loppui puolivälissä palstaansa: otsikkorivi
  katkaistu, sen vieressä eri väreissä oleva raita, ja nykyinen sivu tunnistettiin
  vain numeronsa takana olevasta väripallosta. Nyt se täyttää palstansa,
  sen voi vetää leveämmäksi, ja nykyinen sivu on korostettu koko laattana
  – aidolla sivuesikatselulla sisällään.

- **Korvatut kohdat syttyvät vaaleankeltaisina.** Sivunäkymässä näkee
  näin yhdellä silmäyksellä, missä jotain korvattiin – sama väri, jota
  vertailusuurennuslasi käyttää alkuperäisen päällä. Punainen kehys hiirellä
  osoitettaessa pysyy muuttumattomana.

- **"Palauta näkymä" jälkikäsittely-ikkunassa** (valikko "Näkymä").
  Sivuosion tai osumaluettelon siirtänyt, irrottanut tai sulkenut
  palauttaa sillä kaiken sinne, missä se oli ensimmäisellä käynnistyksellä.

### Muutettu

- **Paikkamerkit ovat lyhyempiä.** Merkinnästä `[SOZIALVERSICHERUNGSNR_1]`
  tulee `[SVNR1]`, merkinnästä `[ORGANISATION_1]` `[ORGA1]`, merkinnästä
  `[EMAIL_1]` `[MAIL1]`. Syy ei ole kauneus: paikkamerkki, joka on pidempi
  kuin arvo, jonka se korvaa, työntää rivin auki eikä mahdu enää lainkaan
  ahtaaseen taulukkosarakkeeseen – siellä jäi aiemmin musta palkki, eikä se
  enää kerro kellekään, että siinä kohdassa oli jotain. Missä on
  vakiintunut lyhenne, se on käytössä (`[BLZ1]`, `[KFZ1]`, `[IBAN1]`).
  Aiempien ajojen tulokset pysyvät käytettävissä: vanha kirjoitustapa
  tunnistetaan edelleen, ja eilisen kohdistustiedostot toimivat
  muuttumatta.

- **Ohjelmakuvake näyttää nyt kaikkialla samalta.** Macin valikkorivillä
  näkyi aiemmin yksivärinen kilpi, jonka järjestelmä itse väritti mustaksi
  tai valkoiseksi, Windowsin tehtäväpalkissa vihreä tai harmaa vastaavasti.
  Nyt jokainen rivi kantaa samaa sinistä Maskuro-kilpeä. Se, mistä näkee,
  valvotaanko leikepöytää, pysyy yhtä selvänä: valvonnan käydessä kilvessä
  on vihreä piste; levätessä sama kilpi näkyy vaaleana. Myös pienimmissä
  koissa kilvessä on nyt molemmat peittopalkit – aiemmin tehtäväpalkki
  näytti niistä vain toisen.

- **Kasvot tunnistetaan mallilla, jonka koulutuskuvat on saatu
  suostumuksella.** Toimitetaan nyt MediaPipe BlazeFace (Apache-2.0);
  aiempi tunnistin pysyy sisäänrakennettuna ja vaihdettavissa, mutta sitä
  ei enää toimiteta mukana, koska sen koulutusaineiston alkuperää ei ole
  lopullisesti selvitetty. Tunnistuksessa ei muutu mikään: 324 muotokuvassa
  ja 143 kuvassa ilman kasvoja uusi versio löytää yhtä paljon yhtä
  harvoilla virhehälytyksillä ja tarvitsee kolmasosan ajasta.

- **OCR on turvallisuuden ankkuri vahvimmalle PDF-lupaukselle.** Tavallinen
  PDF-ajo käyttää sitä ja tuottaa täydellisen minimirakennuksen. OCR:n
  nimenomaisesti pois kytkevä saa yhteensopivamman objektireitin;
  käyttöliittymä, loppuilmoitus ja käyttöohje kertovat nyt nimenomaisesti,
  ettei tämä reitti tarjoa samaa arkkitehtuuria tuntemattomia piilotettuja
  PDF-kanavia vastaan.

- **Myyntiportti estää nyt myös aiemmin mukana toimitetun YuNet-mallin.**
  Tarkan painotuksen MIT-lisenssi on edelleen dokumentoitu, mutta se ei
  riitä julkisesti näkyvälle WIDER FACE -koulutusdataketjulle
  varovaisena tuotejulkaisun kriteerinä. Ennen myyntiä tarvitaan
  kirjallinen selvitys tai vaihto malliin, jolla on kestävä kaupallinen
  data- ja painotusketju.

- **Yritysten ja organisaatioiden nimet poistetaan nyt itsestään.**
  Aiemmin ne jäivät paikoilleen, ellei niitä nimenomaisesti pyydetty.
  Se oli liikekirjeelle väärä oletus: tarjouksen eteenpäin luovuttava ei
  halua lukea siitä toimeksiantajaa. "Kranzbichler Handels GmbH",
  "Institut für Bauphysik" ja vastaavat käsitellään siksi kuin nimi. Sen
  toisin tarvitseva kytkee sen pois ikkunasta; komentorivillä kytkin on
  nyt `--ohne-organisationen`. Vanha `--mit-organisationen` hyväksytään
  edelleen eikä se enää tee mitään, jotta olemassa olevat skriptit ja
  pikakuvakkeet eivät hajoa. Päivämäärä- ja rahatiedot pysyvät ennallaan
  poikkeuksina.

- **Peittämisellä on nyt kolme muotoa kahden rastin sijaan.** "Sanat",
  "Koko rivi" ja "Vapaa kehys" ovat yksi valinta rinnakkain – aina
  täsmälleen yksi pätee. Aiemmin "Tekstirivit" ja "Koko rivi" olivat
  kaksi riippumatonta kytkintä, jotka molemmat saattoivat olla
  painettuina, ja vapaa kehys ei ollut ollenkaan painike, vaan
  ensimmäisen pois kytketty tila. Kolme näkyvät nyt selvästi oman
  työkalunsa kohdalla ja ovat harmaita, kun jokin muu työkalu on
  valittuna.

### Parannettu

- **Ensimmäinen asiakirja on valmis noin sekunnin nopeammin.** Ennen
  puhdistuksen alkua Maskuro selvittää asiakirjan kielen – ja haki tätä
  varten aiemmin kaikkien 48 kielen sanalistat reittiä, joka latasi paljon
  enemmän kuin sanat. Tämä oli noin puolet odotusajasta ensimmäiseen
  tulokseen. Itse tunnistus on ennallaan: se näkee samat sanat kuin
  ennenkin, vain nopeammin. Jokainen sitä seuraava asiakirja ei ollut
  tästä muutenkaan koskaan riippuvainen.

- **Hyvin pitkillä kappaleilla varustetut asiakirjat tarkistetaan
  nopeammin.** Kappaleessa ilman rivinvaihtoa Maskuro luki sen jokaiselle
  löydetylle kohdalle uudelleen kokonaan; nyt riittää kerran. Mitä pidempi
  kappale, sitä suurempi ero – mitattuna noin seitsemäsosa vähemmän
  laskenta-aikaa. Tulos ei muutu.

### Korjattu

- **Yrityksen mukana katosi usein puoli lausetta.** Kun leipätekstissä
  oli yrityksen nimi – "Information über die Gottwald GmbH & Co KG",
  "… (AGB) der Musterbetriebe GmbH" –, peitettiin paitsi nimi, myös
  kaikki sitä ennen lauseen alkuun asti. Teksti muuttui siten
  lukukelvottomaksi, ja näytti siltä, että peittäminen oli mielivaltaista.
  Yritysten nimet, joissa on itsessään "für" tai "und" ("Bank für Arbeit
  und Wirtschaft AG"), pysyvät edelleen muuttumatta kokonaisina.

- **Yritysten nimet jäivät kirjekuviin, vaikka ne poistettiin tekstistä.**
  Tarjouksessa yrityksen kotipaikka näkyi kirjekuvakuvassa yhä luettavana –
  sama paikka, jonka Maskuro oli peittänyt leipätekstissä; tuloksen
  haettavassa tekstissä se seisoi jopa näkymättömänä edelleen sisällä.
  Kerran poistettu poistetaan nyt myös siellä, missä se on vain kuvana.
  Tämä toimii myös logoissa ja sanamerkeissä, jotka on piirretty
  grafiikkana.

- **macOS kysyi joka käynnistyksellä näytön tallennuksesta**, vaikka
  lupa oli jo kauan sitten myönnetty. Käynnistyksen huomautus kokeili
  tallennusta, ja juuri se tuo järjestelmän valintaikkunan ruudulle. Nyt
  käynnistyksessä kysyy vain Maskuro itse, ja vain kerran; järjestelmä
  kysyy vasta, kun todella otat kuvakaappauksen.

- **Teknisiä asiatermejä pidettiin paikkoina ja yrityksinä.**
  "Einspeisepunkt", "Flachdach", "Verteileranlage", "Meldersockel" ja
  kymmenet vastaavat sanat katosivat tarjouksista ja
  suoriteluetteloista. Maskuro tunnistaa ne nyt perussanastaan: mikä
  päättyy pääteeseen "-anlage", "-punkt" tai "-kanal", on asia.
  Paikannimillä kuten Berlin, Melk tai Wieselburg ei ole tällaista
  perussanaa, ja ne pysyvät koskemattomina – samoin osoitteet kuten
  "Der Graben" tai "Alter Markt".

- **Japanin-, korean-, kiinan-, thain- ja gudžaratinkieliset asiakirjat
  saattoivat kaataa ohjelman.** Jos asiakirja jollain näistä viidestä
  kielestä sisälsi internetosoitteen ilman "https://" edessä, puhdistus
  keskeytyi sisäiseen virheeseen – avoimen ikkunan tapauksessa myös
  muu työ hävisi. Kaikki neljäkymmentäkahdeksan valittavaa asiakirjakieltä
  toimivat nyt loppuun asti; jos jonkin kielen taajuussanakirja puuttuu,
  tieto jää epäselvässä tapauksessa paikoilleen sen sijaan, että se
  katoaisi.

- **Kenttäotsikot suojasivat vain saksaksi ja englanniksi.**
  "Reference" jäi paikoilleen, italialainen "Riferimento" ja
  portugalilainen "Referência" poistettiin paikkatietona – sama
  kenttänimi, sama rivi, eri tulos. Se, joka ei työskentele
  englanniksi, oli siten heikommassa asemassa. Maskuro tuntee nyt
  kaikissa yhdessätoista ylläpidetyssä kielessä samat kenttänimet.

- **"Palauta alkuperäinen" palautti skannatuilla sivuilla liikaa.** Kehys
  osoitelohkon peitetyn rivin yläpuolella paljasti taas **koko lohkon** –
  ja sivu jäi rikkinäiseksi: palkin jäänteitä oli edelleen, ja niistä
  pisti esiin yksittäisiä sananloppuja. Syynä oli se, että allekkaiset
  palkit rasteroidulla sivulla koskettavat toisiaan ja niitä siksi
  pidettiin yhtenä ainoana alueena. Palautetaan nyt täsmälleen se rivi,
  johon kehys osoittaa; naapurivirit pysyvät peitettyinä, ja osuman
  rivin palkki katoaa kokonaan.

- **Määrätietoja nimikeluetteloissa pidettiin osoitteina.** Rivillä
  kuten "1.4  Kabelgraben  100,00  m" merkintä "Kabelgraben 100"
  korvattiin katuna talonnumeroineen. Tällaiset rivit jäävät nyt
  paikoilleen; todelliset osoitteet – myös "Hauptplatz 1, 3250
  Wieselburg" – tunnistetaan edelleen muuttumatta.

- **Yrityksen nimen edeltä katosi puoli lausetta.** Merkinnästä "Vertrag
  zwischen der Firma Gottwald GmbH & Co KG und dem Auftraggeber." tuli
  "[ORGANISATION_1] und dem Auftraggeber." – lauseen alku oli poissa, ja
  sen mukana viesti siitä, mistä on kyse. Nyt katoaa vain itse yrityksen
  nimi. Missä lajisana kuuluu nimeen ("Deutsche Bank AG", "Universität
  Wien"), kaikki pysyy ennallaan.

- **Pöytäkirjassa jäivät paikoilleen puhujat, joiden nimi on samalla
  ammatti.** "Bauer:", "Koch:", "Weber:" ennen puheenvuoroa jäivät
  huomaamatta, "Gruber:" vierestä ei – Maskuro tarvitsi aiemmin
  vähintään yhden tunnistetun nimen asiakirjassa, jotta rivit
  ylipäätään luettiin puheenvuoroiksi. Jos asiakirjassa on otsikko
  kuten "Ergebnisprotokoll" tai "Niederschrift", tämä riittää nyt.
  Huomiorivit ("Achtung: …", "Hinweis: …") pysyvät koskemattomina.

- **Kenttämerkintä katosi arvonsa mukana.** Merkinnästä "Projekt:
  Sanierung und Erweiterung Gemeindezentrum" tuli yksi ainoa
  paikkamerkki – myös sana "Projekt:" oli poissa, ja sen mukana viesti
  siitä, mitä siinä kohdassa oli ollut. Merkinnät jäävät nyt paikoilleen.
  Missä merkintä kuuluu tietoon ja kantaa sen merkityksen ("Durchwahl
  214"), mikään ei muutu.

- **Maksimaalinen tunnistus ei siivonnut asiatermejä.** "Flachdach",
  "Einspeisepunkt", "Elektrotechnik" ja vastaavat ammattitermit
  korvattiin paikkana tai yrityksenä myös tekoälytason ollessa
  päällä – tekoäly ei koskaan saanut juuri näitä löydöksiä
  arvioitavakseen. Se tarkistaa ne nyt mukana: kilpailutus- ja
  sopimustekstien korpuksessa kaikki 27 virheosumaa katoavat tämän
  myötä, ilman että yksikään todellinen tieto jää paikoilleen. Nimet,
  yritykset ja paikat tunnistetaan ennallaan.

- **Laitostyyppien lajisanoja pidettiin organisaatioina.**
  Sopimustekstissä katosivat "Hochschulen und Universitäten",
  "Staatliche und private Schulen", "Akademische Lehrkrankenhäuser",
  "Bildungseinrichtung" ja "Zulieferfirmen" – sanoja, jotka eivät
  nimeä tiettyä paikkaa, vaan paikan lajia. Ne jäävät nyt
  paikoilleen. Jos edessä on erisnimi ("EU-Kommission"), korvataan
  edelleen, eikä sääntö koske lainkaan yritysten nimiä.

- **Listoissa olevat nimet katosivat vain, jos ne olivat yleisiä.**
  Osallistuja- tai läsnäololistassa sarakeotsikon "Name" alla
  poistettiin "Anna Huber" ja "Thomas Müller", mutta ei "Wójcik
  Aleksandra" tai "Kücükgöl Sinan" – sama rivi, sama rakenne. Harvinaisempi
  nimi oli siten heikommin suojattu. Nyt sarakeotsikko ratkaisee: se,
  mikä on kohdan "Name" alla, on nimi. Nimikeluettelo asiallisella
  sarakeotsikolla pysyy koskemattomana.

- **Puhelinnumero "Durchwahl"-merkinnän jälkeen katkaistiin keskeltä.**
  Merkinnästä "Durchwahl 0732 771190" tuli "[DURCHWAHL_1] 771190" –
  numeron toinen puolisko jäi luettavaksi. Nyt koko numero poistuu
  kokonaan, ja merkintä jää paikoilleen. Todellinen alanumero
  ("Durchwahl 214") korvataan ennallaan merkintänsä kera.

- **Joitakin PDF:iä ei voitu enää puhdistaa lainkaan.** Jos värimallia
  tai kuvan metatietoja ei voitu todistetusti poistaa, ajo keskeytyi
  ilman tulosta – tämä koski tavallisia liikeasiakirjoja kuten
  yleisten ehtojen sivuja, vaatimusluetteloja ja kilpailutuksia.
  Tällaiset tiedostot puhdistetaan nyt, ja varoitus mainitsee kohdat,
  jotka jäivät auki: niissä voi olla laite-, tuottaja- tai
  tallennustunniste. Alkuperäinen pysyy kuten aina muuttumattomana.

- **Sopimusrooleja pidettiin henkilöinä.** "Bieter", "Verbraucher",
  "Mieter", "Käufer", "Auftraggebers" ja noin neljäkymmentä muuta
  roolisanaa korvattiin, kun ne esiintyivät ilman artikkelia –
  sopimusotsikoissa, taulukkosarakkeissa ja allekirjoitusriveillä.
  Sopimusteksti ilman ainuttakaan henkilötietoa muuttui siten
  paikoin lukukelvottomaksi. Nämä sanat jäävät nyt paikoilleen. Jos
  vieressä on henkilöviite – puhuttelu, etunimi, kenttäsana kuten
  "Ansprechpartner" –, korvataan edelleen: "Herr Bieter" ja "Frau
  Käufer" ovat nimiä. Yleiset sukunimet, jotka ovat samalla ammatteja
  (Bauer, Richter, Koch), eivät kuulu tähän sääntöön lainkaan.

- **Lyhennetty katu jäi huomaamatta, kun talonnumero oli kiinni
  pisteessä.** "Schlesischestr.31" ei kelvannut osoitteeksi – ja koska
  vieressä oleva postinumero saa tukensa osoitelöydöstä, se jäi myös
  paikoilleen. Tuloksessa osoite oli koottavissa katu- ja
  postinumerotiedosta uudelleen, ja vain joillakin saman asiakirjan
  sivuilla. Molemmat poistuvat nyt yhdessä. Asiasanat, joiden perässä
  on luku ("Kabelrinne200"), pysyvät koskemattomina.

- **Kahden rivin osoite yhdistettiin yhdeksi paikkamerkiksi.**
  Jos osoitelohkossa postinumero oli kadun yläpuolella, Maskuro
  yhdisti molemmat rivit yhdeksi löytökohdaksi: tuloksessa rivinvaihto
  katosi, ja postinumero jäi sen eteen luettavaksi. Nyt jokainen rivi
  löydetään ja korvataan erikseen, ja kirjoitusasu säilyy. Sama syy
  veti toisinaan myös yläpuolisen rivin sukunimen mukaan osoitteeseen.

- **Maksimaalinen PDF-reitti ei enää ota mukaan alkuperäisiä
  objekteja.** Tekstintunnistuksen ollessa päällä Maskuro rakentaa
  jokaisen sivun kokonaan uudelleen näkyvästä PDFium-kuvasta. Uuteen
  minimitiedostoon tulee vain tämä kuvasivu ja uusi, OCR-tekstiin
  rajattu hakukerros – ei vieras objektipuu kommentteineen,
  liitteineen, toimintoineen, tasoineen, metatietoineen, värimalleineen
  tai yksityisine avaimineen. Tämä koskee myös huomautusesitysten,
  kuvioiden, Type-3-kirjasinten, lomake-objektien ja pehmeiden
  maskien sisältöjä. Lähdetiedosto pysyy koskemattomana.

- **Kasvot ja koodit sisäkkäisissä PDF-grafiikoissa jäivät
  huomaamatta.** Molemmat tunnistimet näkevät nyt lisäksi täyden
  renderöidyn sivukuvan. Näin myös huomautusten, kuvioiden, Type-3-
  glyyfien ja läpinäkyvyysmaskien muotokuvat ja QR-/viivakoodit
  saavuttavat tunnistimet; tunnistetut alueet tehdään – jos kytketty
  päälle – tunnistamattomiksi ennen minimirakennusta. Itse tunnistus
  pysyy virhealttiina.

- **Puuttuva OCR-moottori päättyi PDF:issä sisäiseen virheeseen.**
  Maksimaalinen ajo keskeytyy nyt hallitusti ja ilman kohdetiedostoa
  sen sijaan, että se antaisi ulos vaillinaisen tai tarkistamattoman
  tiedoston.

- **Useita todellisia yhteystieto- ja liikearvoja jäi väliin, kun
  asiatekstiä korvattiin.** Nimikentät rivinvaihtojen yli, pankki- ja
  yritysten nimet, oikeudelliset muodot, merkityt tunnusnumerot,
  syntymäajat sekä puhelin-, URL- ja IBAN-rajat on tarkistettu
  tarkemmin. Samalla asiatekstissä olevat maat, rooli- ja lajisanat,
  tuote-/normikoodit, lukusarakkeet ja tavalliset lyhenteet pysyvät
  useammin koskemattomina.

- **Sekamuotoiset ja käännetyt OCR-rivit luettiin väärin.**
  Epävarmat pystysuorat sanat luetaan nyt paikallisesti uudelleen
  oikaistuina; nichtlateiniset tekstin sisällä olevat tekniset
  latinalaiset arvot saavat riippumattoman englannintodisteen. Vapaana
  seisova epävarma yksittäinen numero korjataan vain, jos kaksi
  läheistä numerojaksoa täsmää. Puolalaiset oikeudelliset muodot OCR-
  muodossa "sp. z 0.0." luetaan suljetussa kontekstissa muodossa
  "sp. z o.o.".

- **Kuvamittaus saattoi jättää osittain näkyviä jäännösarvoja
  huomaamatta.** Se tarkistaa nyt päällekkäiset paikalliset otteet,
  erottaa valkoisen paikkamerkkikirjasimen mustalla palkilla
  alkuperäisistä glyyfeistä ja siirtää raakakuvalaatikot myös
  käännetyille, uudelleen renderöidyille minimi-PDF:ille. Kiinteä
  synteettinen pääkorpus saavuttaa siten 1 392/1 392 poistettua
  tavoitetietoa 0 virhehälytyksellä ja 0 käsittelyvirheellä. Tämä on
  korpustodiste, ei yleinen 100 %:n lupaus.

- **Ei-kaupallisia kielimalleja ei enää tarjota.** Kuusi italialaista ja
  kreikkalaista spaCy-varianttia CC BY-NC-SA 3.0 -lisenssillä on
  poistettu luettelosta, latauksesta ja lataustiestä; myös jo olemassa
  olevat mallikansiot jätetään huomiotta. Molemmat kielet käyttävät
  sen sijaan MIT-lisensoitua monikielimallia.

- **"Ansprechpartner"-otsikon alla oleva nimi poistettiin vain
  puoliksi.** Jos merkintä on yksin omalla rivillään ja sen alla
  "Nachname Vorname", etunimi jäi paikoilleen heti, kun se oli samalla
  tavallinen sana – merkinnästä "Mayer Roman" tuli "[NAME_1] Roman".
  Tällaiset rivit otetaan nyt kokonaan. Osasto samassa kohdassa
  ("Technischer Innendienst") pysyy edelleen koskemattomana. Samalla
  korjattu: "Ansprechpartner" ei laskettu lainkaan nimikentäksi, vaikka
  "Kontaktperson" on aina ollut.

- **Yrityksen nimi ilman oikeudellista muotoa jäi paikoilleen, jos
  välissä oli toimialasana.** "Kranzbichler Handels GmbH" poistettiin,
  paljas "Kranzbichler" kolme kappaletta myöhemmin ei – kun taas
  "Kranzbichler GmbH" poistui. Nyt molemmat toimivat. Tavalliset sanat
  on jätetty tämän ulkopuolelle: "Deutsche Bank AG" ei tee sanasta
  "deutsche" yritystä muualla tekstissä.

- **Sama arvo tarkoitti samassa asiakirjassa kerran nimeä ja kerran
  paikkaa.** "Anna Musterfrau … Musterfrau" tuotti "[NAME_1]" ja
  "[ORT_1]" – toisessa kohdassa etunimi puuttuu, ja ilman sitä siitä
  tuli paikka. Molemmat poistettiin, mutta se luki kuin kaksi eri
  asiaa. Arvo säilyttää nyt ensimmäisen esiintymänsä nimityksen.

- **Päivämääriä ei enää poistettu.** Kokonaan numeroista koostuva
  päivämäärä ("01.03.2026") jäi viimeisimmästä versiosta lähtien
  kiinni tarkistukseen, joka oli tarkoitettu nimille, ja jäi asiakirjaan
  paikoilleen – myös tilassa "siirrä", ilman riviä tarkistusraportissa.
  Tämä koski vain sitä, joka oli kytkenyt päivämäärätiedot nimenomaisesti
  päälle.

- **Maita ja mantereita ei enää peitetä.** "Die Lieferung geht in die
  Vereinigten Staaten", "Marktschwäche in Asien", "die Norm gilt in
  Rumänien" – tällaiset tiedot eivät kerro mitään henkilöstä ja jäävät
  nyt paikoilleen. Jos maan nimi sen sijaan kuuluu osoitteeseen tai
  seisoo merkinnän kuten "Wohnsitz" tai "Geburtsort" jälkeen, se
  poistetaan edelleen. **Kaupungit eivät kuulu tähän** – "Ich bin
  gerade in Bilbao" on edelleen tieto henkilöstä ja peitetään
  edelleen.

- **Lyhennetyistä sanoista tuli verkko-osoitteita.** Jos tekstissä lukee
  "bzw. deutsche" tai "incl. der", jotkin PDF:t tuottavat pisteen ilman
  välilyöntiä – siitä tuli "bzw.de" tai "incl.de", kelvollinen
  osoite maapäätteineen, ja se poistettiin. Tällaiset sanaparit jäävät
  nyt paikoilleen. Todelliset osoitteet eivät kärsi tästä, ei myöskään
  ilman "www." edessä.

- **Taselukusarakkeita peitettiin puhelinnumeroina.** Vuosikertomuksissa
  ja hintataulukoissa edellinen ja kuluva vuosi ovat vierekkäin –
  "64.518  65.133". Tämä laskettiin puhelinnumeroksi ja poistettiin,
  samoin lukualueet kuten "12200-23200" ja päivämäärä seuraavine
  lukuineen. Tällaiset luvut jäävät nyt paikoilleen. Toisaalta
  todellinen puhelinnumero tunnistetaan nyt varmemmin: merkinnät
  "Telefon", "Fax", "Mobil", "Durchwahl" ja niiden vastineet muissa
  käyttöliittymän kielissä lasketaan nyt mukaan – aiemmin ohjelma
  tunsi siellä vain englanninkieliset sanat.

- **Nimet numeroidussa taulukossa jäivät paikoilleen.** Osallistuja- tai
  henkilöstötaulukko tavanomaisessa muodossa – sarakeotsikko, sen alla
  "1.1 Auersperg Bernhard Montage 03.03.2026" – ei puhdistunut lainkaan:
  tällaiset rivit näyttivät tarjouksen nimikeluettelolta, jossa
  asiatermien pitäisi jäädä paikoilleen. Jos sarakeotsikossa on
  henkilömerkintä ("Name", "Nachname", "Surname" …), sen alla olevat
  rivit lasketaan nyt nimiksi. Nimikeluettelot säästyvät edelleen
  muuttumatta – myös silloin, kun kirjekuvassa lukee "Sachbearbeiter:".

- **Nimestä syntyi joskus kaksi vierekkäistä paikkamerkkiä.** Jos
  sukunimi seisoi asiakirjassa myös yksin, jälkikäsittely korvasi
  kohdassa kuten "Anna Musterfrau GmbH" ensin sukunimen ja sitten
  etunimen – tuloksessa se näytti kahdelta eri henkilöltä. Nyt pisin
  tunnettu nimi voittaa.

- **Keksityt arvot eivät näkyneet missään kohdistuksessa.** "Keksi
  arvoja" -toiminnon valinnut sai tuloksen, jossa "Anna Musterfrau"
  oli muuttunut "Greta Mayrhofer":ksi – kohdistuksessa siitä ei
  lukenut mitään, heti kun samassa asiakirjassa esiintyi yksikin
  anonyymi korvaus. Näin keksittyä arvoa ei voinut palauttaa, ja
  kohdistustiedosto vaikeni korvauksesta. Arkaluontoisin oli kolmas
  seikka: tuloksen lukija näkee uskottavan nimen eikä hänellä ole
  mitään vihjettä siitä, että se on keksitty. Nyt jokainen korvaus
  näkyy kohdistuksessa.

- **Kohdistus nimesi peitetyn "korvatuksi".** Sähköposti jakaa
  kohdistuksen liitteidensä kanssa, ja liite saa olla peitetty, kun
  taas viestin teksti kantaa paikkamerkkiä. Kohdistuksessa luki
  tuolloin kaikilla kolmella kohdalla sama – "korvattu" –, ja
  palauttaminen etsi liitteestä paikkamerkkiä, jota siellä ei ole:
  palkki jäi paikoilleen. Nyt jokaisesta löytökohdasta lukee, mitä
  siellä todella tapahtui, ja molemmat liitteet palautuvat.

- **Vain kuvassa olleita arvoja ei voinut palauttaa.** Osumapaneelissa
  ne näkyivät kahdesti – kerran paikkamerkkinä, jota asiakirjassa ei
  ollut missään ("Paikkamerkkiä ei löytynyt asiakirjasta"), kerran
  peitettynä kohtana. Ensimmäinen rivi oli pelkkää kirjanpitoa ja on
  kadonnut.

- **Peitetyt arvot pystyi palauttamaan vain kerran.** Jos sama arvo on
  useassa kohdassa, klikkaus palauttaa ne kaikki – mutta muut rivit
  jäivät osumapaneeliin, ja seuraava klikkaus niihin ilmoitti "Ei
  yksiselitteinen". Ne katoavat nyt mukana.

- **Palautukset puuttuivat tarkistuspöytäkirjasta, kun oppimistila oli
  pois päältä.** Jälkikäsittely-ikkunassa palautetun arvon
  ennalleen palauttanut ei löytänyt toimenpidettä
  tarkistuspöytäkirjasta, heti kun oppimiskysymykset olivat kytketty
  pois – todiste riippui kytkimestä, joka koskee vain
  sääntöehdotuksia. Tarkistuspöytäkirjan ollessa päällä syytä kysytään
  nyt tästä riippumatta ja rivi kirjoitetaan.

- **Vedetyt tiedostot jäivät puhdistamatta – eikä niistä edes
  ilmoitettu.** Tiedoston asiakirjaan vetävä liitteenä lähettämisen
  sijaan saa Wordin tai PowerPointin tallentamaan sen kokonaan
  asiakirjaan. Se jäi sen jälkeen muuttumattomana tulokseen,
  alkuperäisen tiedostonimensä ja tallennuspolkunsa kera – ja ne
  kantavat käytännössä usein itsekin nimen. Tällaiset tiedostot
  puhdistetaan nyt kuten muu asiakirja.

- **Ja missä se ei onnistu, Maskuro kertoo sen.** Jos upotetussa
  objektissa on vanha muoto (Word 97, Excel 97), jolle ei ole
  puhdistusta, näkyy nyt HUOMIO-ilmoitus tiedoston nimen kera. Aiemmin
  se annettiin äänettömästi eteenpäin muuttumattomana.

- **Rikkoutuneita sanoja ja lyhenteitä pidettiin niminä.** Kun sana on
  PDF:ssä rivin lopussa katkaistu, joidenkin tiedostojen lukemisessa
  syntyy katkelma – "Jahresent… gelts", "Gewerbli…". Tällaiset
  katkelmat, yhteen liimautuneet sanat ("TürverschlussmitV") ja
  paljaat lyhenteet ("JY", "FFB") peitettiin nimenä. Ne jäävät nyt
  paikoilleen. Nimi samanlaisella katkoksella peitetään edelleen,
  kunhan mukana on puhuttelu – ja nimet, joissa on jo lähtökohtaisesti
  iso kirjain sanan sisällä (McKenzie, MacDonald, LeBlanc), eivät
  koske tätä muutenkaan.

- **Mittatietoja ja kuukausia pidettiin osoitteina.** Teknisissä
  asiakirjoissa peitettiin "2000 Lux", "1200 Mbit", "1500 Watt", "5308
  Platz" ja "2022 Mrz" – neljä numeroa ja isolla alkukirjaimella
  kirjoitettu sana näyttivät postinumerolta paikkakunnan kanssa.
  Postinumero lasketaan nyt vain, jos mukana on myös osoitesignaali:
  maatunnus, kenttämerkintä, rivin alku, katu edellisellä rivillä tai
  paikka, jonka myös kielentunnistus näkee siinä. Viidessä
  suoriteluettelossa tämä poistaa 14 väärää peittoa ilman, että
  yksikään todellinen osoite jää paikoilleen.

- **Tarkempi tunnistus korvasi liikaa.** Kytkettävissä oleva taso
  "tarkempi tunnistus" piti saksankielisissä liikeasiakirjoissa
  asiatermejä niminä ja paikkoina – "Photovoltaikanlage",
  "Einspeisepunkt", "Flachdach", "Personaleingang" – ja peitti
  yritysten nimiä juoksevista nimikeluetteloista. Syynä oli
  suojaustapa: sen osumat oli jätetty niiden tarkistusten ulkopuolelle,
  jotka tunnistavat nimike- tai luettelorivin. Tämä suojaus koskee nyt
  vain moniosaisia nimiä, joita varten taso on olemassa – "Anna Huber"
  luetteloäivillä tunnistetaan siis edelleen, yksittäinen asiasana
  nimikerivillä katoaa. Teknisessä kilpailutuksessa tämä puolittaa
  tason väärät peitot ilman, että yksikään nimi häviää.

- **Kaaviot toivat mukanaan täydelliset lähdetiedot – tarkistamatta.**
  Wordiin tai PowerPointiin kaavion lisäävä saa ohjelman tallentamaan
  taulukon, josta se laskettiin, omana tiedostona asiakirjaan.
  Näkyvissä on kaaviosta vain muutama luku; taulukossa on koko lista,
  myös rivit, joita kaaviossa ei lainkaan näy. Tämä taulukko luovutettiin
  aiemmin eteenpäin muuttumattomana. Se puhdistetaan nyt mukana, samoin
  paikkamerkein kuin muu asiakirja.

- **Sama upotetuille objekteille OpenDocument-tiedostoissa** (ODT, ODS,
  ODP): liitetty kaavio tai liitetty taulukko jäi koskemattomaksi.

- **Word-asiakirjat: alaviitteitä ja loppuviitteitä ei puhdistettu.**
  Niiden teksti jäi kokonaan tulokseen – myös nimet, osoitteet ja
  tilinumerot. Tämä koski jokaista Word-asiakirjaa, jossa oli ala- tai
  loppuviite. Samoin jäi koskematta automaattinen tekstimoduuli, joka
  kulkee näkymättömänä asiakirjan mukana.

- **Word: tiedot valintalistoissa, kommenteissa ja kuvien kuvauksissa.**
  Valintakentän vaihtoehdot (näkyvissä vasta avattaessa), kommentin
  tekijä, piirroksen kuvaus ja viittauskomennon jälkeinen osoite jäivät
  edelleen tulokseen.

- **Excel: pivot-taulukko sisälsi lähtötiedot toistamiseen.**
  Pivot-taulukon sisältävä taulukkolaskentatiedosto säilyttää siinä
  täydellisen kopion käsitellyistä riveistä – näkymättömänä, mutta
  tiedostossa. Tämä kopio jäi aiemmin muuttumattomana, vaikka
  itse taulukossa kaikki oli korvattu. Tämä koski jokaista raporttia,
  joka luovutettiin eteenpäin pivot-taulukon kanssa.

- **Excel: keskustelukommentit ja niiden tekijät.** Uudemman muodon
  kommentin teksti ja kommentoijien luettelo – näyttönimi ja
  kirjautumistunniste, yrityksissä yleensä sähköpostiosoite – jäivät
  edelleen tulokseen. Sama luettelo Word-asiakirjoissa myös.

- **Itse määritellyt asiakirjaominaisuudet Wordissa ja Excelissä.**
  Kentät kuten "Mandant" tai "Aktenzeichen", jotka toimisto liittää
  malleihinsa, jäivät aiemmin puhdistamatta. Ne eivät näy missään
  näkymässä ja kulkevat silti mukana joka kopion mukana.

- **Taulukot (ODS): solun valintalista.** Kuten Excelissä edellisestä
  versiosta lähtien, myös OpenDocument-taulukoissa puhdistetaan nyt se,
  mikä ilmestyy solua avattaessa. Viittaukset muihin soluihin pysyvät
  koskemattomina, jotta lista toimii edelleen.

Kaikki nämä kohdat voidaan palauttaa tavalliseen tapaan kohdistuksen
kautta.

- **Outlook-viestit: vaurioitunut tiedosto keskeytti puhdistuksen
  kokonaan.** Tietyt rikkinäiset `.msg`-tiedostot johtivat
  keskeytykseen ilmoituksen sijaan; nyt ne luetaan siltä osin kuin ne
  ovat luettavissa.

- **Kohdistustiedosto on nyt luettavissa vain sinulle.** Se sisältää
  alkuperäiset tiedot selkotekstinä ja sijaitsi aiemmin tavanomaisin
  oikeuksin tuloksen vieressä – yhteisellä levyllä kuka tahansa saattoi
  avata sen. Itse puhdistettu tulos ei muutu; sen onkin tarkoitus mennä
  eteenpäin.

- **Jälkiladatut kielimallit tarkistetaan nyt tarkemmin ennen
  purkamista.** Manipuloitu paketti – esimerkiksi yrityksen jaosta,
  josta palvellaan useita työasemia – saattoi purkaessaan tallentaa
  tiedostoja tarkoitetun kansion ulkopuolelle. Tavalliseen
  jälkilataukseen tämä ei vaikuta.

- **Ota kuvakaappaus – ja se puhdistetaan heti.** Näppäimillä
  `Ctrl+Vaihto+B`, kohdasta "Tiedosto → Ota kuvakaappaus …" tai
  tehtäväpalkin kuvakkeesta vedät kehyksen ruudulle. Mitä siinä on,
  kulkee sen jälkeen saman reitin kuin mikä tahansa muu tiedosto:
  tekstintunnistus lukee ruudun tekstin, nimet, osoitteet,
  puhelinnumerot ja sähköpostiosoitteet peitetään, ja sen jälkeen kuva
  avautuu editorissa, jossa voit kehyksellä jälkipeittää, mitä jäi
  huomaamatta. Puhdistettu kuva päätyy työpöydälle (tai asettamaasi
  tulostuskansioon); **raakaa** kaappausta ei tallenneta minnekään ja
  se poistetaan sulkemisen yhteydessä. Tekstintunnistus kytketään tätä
  ajoa varten päälle, vaikka se olisi muuten pois päältä – kuvasta ei
  ilman sitä löytyisi mitään. Macilla järjestelmä kysyy ensimmäisellä
  kerralla luvan "Näytön tallennus" -toimintoon.

- **Kuviin voi nyt piirtää: suorakulmion, ellipsin, nuolen, tekstin ja
  numeroituja vaihemerkintöjä.** Kuudella värillä ja kolmella
  viivanvahvuudella, valittavissa näppäimillä 1–5. Tämä on tarkoitettu
  kuvakaappauksille ja ohjeille: näytä, mikä on tärkeää, avaamatta
  siihen toista ohjelmaa. Kumoaminen ja kahvoista vetäminen toimivat
  kuten missä tahansa palkissa – merkinnän voi siis siirtää ja
  laajentaa sen jälkeen, kun se on asetettu.
  **Piirtäminen ei ole tarkoituksella peittämistä.** Piirretty
  suorakulmio on kehys, ei palkki: sen alla oleva jää luettavaksi ja
  kulkee tiedoston mukana ulos. Tietojen poistamiseen ovat edelleen
  "Peitä" ja "Pikselöi"; piirtotyökalut ovat siksi omalla rivillään
  työkalurivillä, ja huomiorivi kertoo sen, kun jokin niistä on
  valittuna.

- **Muokattu kuva siirtyy yhdellä klikkauksella leikepöydälle.**
  "Kopioi kuva" editorissa (tai `Ctrl+C`) asettaa sen sellaisena kuin
  se on – liittäminen riittää sen viemiseen viestiin tai
  sähköpostiin. Näppäimestä chattiin kuljettu polku on siten neljä
  vaihetta pitkä eikä tarvitse kansiota.

- **Lisäksi korostuskynä, varjo ja liu'ut.** "Korosta" värittää alueen
  peittämättä sitä – sen alla oleva sisältö jää luettavaksi, ja juuri
  siinä se eroaa palkista. "Varjo" erottaa merkinnän levottomasta
  taustasta, "Liuku" antaa värin haaltua vetosuunnassa; molemmat
  toimivat kaikilla kuudella piirtotyökalulla.

- **Korjattu ennen kuin se ehti haitata ketään:** uusi työkalurivi olisi
  näkynyt lähes tyhjänä jokaisella, joka on jo käyttänyt Maskuroa –
  muistettu ikkuna-asettelu oli ajalta ennen tätä eikä olisi jättänyt
  sille tilaa. Vanhentunut asettelu hylätään nyt; editori-ikkuna näkyy
  silloin kerran perusasettelussaan.

- **Oman kuvakaappauksen voi kytkeä pois.** Greenshotiin, ShareXiin tai
  leikkaustyökaluun tottunut kytkee kohdasta "Asetukset → Ohjelma"
  pois "Ota kuvakaappaus Maskurolla". Maskuro ei silloin edes rekisteröi
  näppäinkomentoa – se jää työkalullesi –, ja muutos astuu voimaan
  heti ilman uudelleenkäynnistystä. Näin otetun kuvan voi silti
  puhdistaa: Ctrl+V tuo sen leikepöydältä ikkunaan.

---

## 0.10.37-alpha.20260821 – 21. elokuuta 2026

### Uutta

- **Anonymisoitaessa jokainen löytökohta kantaa nyt oman numeronsa.**
  Aiemmin kaikki henkilöt olivat `[NAME]`, kaikki paikat `[ORT]` – tämän
  vuoksi ei enää voinut sanoa, mikä kohta kuului mihinkin arvoon, eikä
  mitään voinut palauttaa. Nyt numerot jatkuvat jokaisen esiintymän
  mukana: sama nimi näkyy kolmessa kohdassa muodoissa `[NAME_1]`,
  `[NAME_3]` ja `[NAME_7]`. Asiakirjasta ei tästä huolimatta edelleenkään
  näe, mitkä kohdat kuuluvat yhteen – mutta kohdistustiedostolla jokainen
  voidaan palauttaa erikseen. Kohdistustiedosto on siksi valittavissa
  jälleen myös anonymisoitaessa; säilytä se erillään tuloksesta.
- **Kuukaudet, viikonpäivät, valuutat, yksiköt ja yritysten oikeudelliset
  muodot kaikissa 48 asiakirjakielessä eivät enää kelpaa nimiksi tai
  paikoiksi.** Kalenteri- ja yksikkönimet tulevat Unicode CLDR:stä
  (luotu, ei kirjoitettu käsin), oikeudelliset muodot maiden
  yhtiöoikeudesta – myös moniosaiset ("sp. z o.o.", "Pty Ltd") ja
  edeltävät ("株式会社"). Missä kuukauden nimi on samalla etunimi (Juli,
  August, May), ratkaisee rakenne: päivän tai vuoden kanssa
  päivämäärä, muuten nimi. Lisäksi puhuttelut ja arvonimet, kokonaiset
  tervehdykset, asiakirjalajit ja katujen perussanat 28 kielelle, joilla
  on oma kielimalli, lakilyhenteet (DSGVO, UStG, ABGB, § 6 Abs 1 Z 27
  UStG) sekä kielen nimet kenttäarvona ("Sprache: Deutsch"). Listat
  löytyvät kohdasta "Ohje → Sanalistat …".
- **Intia: osoite ja PIN-koodi tunnistetaan** – "15 गांधी मार्ग", "नई
  दिल्ली 110001" sekä "15 Gandhi Marg, New Delhi 110001". Intian
  maapaketti tunsi aiemmin vain tunnusnumerot; hindinkielisissä
  asiakirjoissa osoitteet jäivät siksi paikoilleen.
- **Jokainen puhdistettu Office-tiedosto avataan ennen luovutusta vielä
  kerran pakettina.** Tekstiote ei huomaa, jos Word, Excel tai
  LibreOffice hylkäisi tiedoston (kaksinkertainen merkintä, katkennut
  XML, puuttuva osa). Ja alkuperäistä vasten lasketaan se, mitä
  puhdistus ei koskaan saa muuttaa: PDF:n sivut, taulukon lehdet, rivit
  ja solut, esityksen diat. Jos koe epäonnistuu, tulokseen ja
  tarkistusraporttiin tulee HUOMIO-varoitus – alkuperäinen pysyy
  muuttumattomana.
- **Myös automatiikka peittää koko kentän.** Peittotilassa palkki peittää
  lyhyillä riveillä – osoitelohko, taulukkosolu, otsikkotiedot – koko
  rivin pelkän löydetyn arvon sijaan: sanan mittainen palkki paljastaa,
  kuinka pitkä sana oli. Merkintä ja summat vieressä jäävät paikoilleen,
  ja leipätekstirivit (yli puolet tekstin leveydestä) peitetään edelleen
  sanantarkasti, jotta nimi keskellä lausetta ei mustaa koko lausetta.
- **Palautettu näyttää taas alkuperäiseltä.** "Palauta alkuperäinen" ja
  "Peru korvaus" PDF-editorissa kirjoittavat alueen nyt tarkasti
  lähdetiedostosta takaisin – sama kirjasin, sama koko, sama väri ja
  sijainti, skannauksessa samat kuvapisteet. Siihen asti teksti asetettiin
  uudelleen korvaavalla kirjasimella ja näytti tunnistettavasti
  jälkirakennetulta. Aiemman peiton palkki häviää tällöin kokonaan sen
  sijaan, että se maalattaisiin valkoiseksi – taulukon värillinen
  solupohja säilyy. Tämä koskee myös käännettyjä sivuja, upotettujen
  lomake-objektien tekstiä ja **täytettyjä lomakekenttiä**: tätä varten
  rasteroidulla työkopiolla ote palaa uudelleen renderöidystä
  alkuperäisestä sivusta – myös siellä, missä mikään tekstitaso ei
  tunne kenttäarvoa. Myös **korvatut kuvat** PDF:ssä palautuvat näin –
  pikselöityinä, sumennettuina tai kokonaan poistettuina, kokonaan tai
  vain vedettynä otteena. Vain missä lähdetiedosto ei enää ole tuloksen
  vieressä, käytetään edelleen aiempaa reittiä.
- **Peitetyt ja ilman korvausta poistetut arvot voidaan palauttaa myös
  Wordissa, Excelissä, PowerPointissa ja OpenDocumentissa.** Aiemmin
  palautus tarvitsi siellä paikkamerkin tekstissä – palkilla tai
  aukolla ei ollut paluutietä. Nyt osumapaneeli tarjoaa rivit "peitetty"
  ja "poistettu" heti, kun koskematon lähdetiedosto on tuloksen
  vieressä: Maskuro vertaa tulosta alkuperäiseen ja asettaa arvon
  takaisin palkin tai aukon kohdalle – muotoiluineen, katkaistu ajo
  kootaan taas kokonaiseksi. Sama koskee tekstiä, HTML:ää,
  sähköpostia ja sähköpostin Office-liitteitä; jos viestin teksti
  kantaa paikkamerkkiä ja liite palkkia, molemmat palautuvat yhdellä
  kertaa.
- **Myös sähköpostin tai Outlook-viestin PDF-liitteet voidaan
  palauttaa** – paikkamerkit (numeroidut ja anonyymit), palkit ja ilman
  korvausta poistetut. Ilman kangasta kohta tulee alkuperäisestä
  liitteestä; takaisin tulee arvo glyyfintarkasti, alkuperäisen
  lukujärjestyksessä.
- **Naamioidut arvot voidaan palauttaa** – PDF:ssä ja tekstinäkymässä.
  Naamio ("**** **** **** **** 3201") ei ole koskaan yksiselitteinen,
  kaksi numeroa kantaa samaa; siksi palautus ei koskaan käytä
  sanatarkkaa reittiä, vaan kysyy alkuperäiseltä, mikä arvo siinä
  kohdassa oli. Aiemmin nämä rivit eivät olleet ollenkaan käytettävissä
  osumapaneelissa.
- **Upotetut kuvat Wordissa, Excelissä, PowerPointissa ja
  OpenDocumentissa voidaan palauttaa.** Kuvassa peitetty arvo palautuu
  panelirivinsä kautta – Maskuro lukee alkuperäisen kuvan ja hakee juuri
  tämän kohdan; sumennetun, poistetun tai kasvoin ja koodein
  käsitellyn kuvan hakee uusi merkintä "Palauta upotetut kuvat"
  Muokkaa-valikosta kokonaisena lähdetiedostosta – myös sähköpostin
  tai Outlook-viestin Office-liitteiden läpi. Kuva, joka itse on
  liitteenä ja peitettiin tekstintunnistuksella, palautuu myös
  panelirivinsä kautta.
- **Keksityt arvot voidaan palauttaa tekstinäkymässä.** Aiemmin paneeli
  ilmoitti siellä "Ei yksiselitteinen". Nyt palautus etsii arvon
  alkuperäisestä ja vaatii samassa kohdassa tuloksessa juuri sen
  keksityn korvauksen – keksittyä nimeä ei koskaan korvata
  sanatarkasti kaikkialla, se voisi olla jossain aidosti sellainen.
- **Palautus Wordissa, Excelissä, PowerPointissa ja OpenDocumentissa
  säilyttää alkuperäisen muotoilun.** Jos arvo ulottui usean ajon yli –
  "Anna" tavallisena, "Musterfrau" lihavoituna ja punaisena –, se
  palautui aiemmin kokonaan ensimmäiseen ajoon ja menetti lihavoinnin
  ja värin. Nyt merkit jakautuvat taas kuten alkuperäisessä; Word-
  kappale on sen jälkeen tavu tavulta alkuperäinen. Sama koskee
  HTML-sivuja, sähköpostin HTML-osaa ja Outlook-viestin (.msg)
  HTML-runkoa – sähköpostissa säilyy lisäksi doctype, jonka puhdistus
  aiemmin poisti hiljaa.
- **Tekstitiedostot säilyttävät koodauksensa.** Puhdistus ja palautus
  kirjoittavat `.txt`-, `.md`- ja `.csv`-tiedostot nyt siinä
  koodauksessa, jossa ne toimitettiin – UTF-8 BOM:lla ja ilman, UTF-16,
  Windows-1252. Aiemmin Windows-1252-tiedosto muuttui aina UTF-8:ksi,
  ja UTF-16-tiedosto palasi vaurioituneena, vaikka siinä ei ollut
  mitään korvattavaa.
- **Palautetut kuvat säilyttävät värimuotonsa.** Harmaasävyskannaus
  palaa harmaasävyinä kolme kertaa suuremman RGB-tiedoston sijaan,
  paletti palettina, mustavalkoinen mustavalkoisena – koko kuvassa
  samoin arvoin kuin alkuperäisessä. Koskee kuvatiedostoja ja
  PDF:issä olevia kuvia. CMYK ja 16-bittinen pysyvät RGB:nä, koska
  PNG-tulos ei voi kantaa kumpaakaan.
- **Kehys kuvassa palauttaa koko sen muokkauksen, jota se koskettaa.**
  Pikselöidyillä kasvoilla on reuna tunnistetun laatikon ympärillä;
  kehyksen vain kasvojen yli vetänyt jäi pikselöidyn renkaan
  reunaan. Nyt kehys kasvaa alkuperäiseen nähden yhtenäiseen
  muutokseen asti – kehys silmien alueen yli riittää. Erilliset
  palkit sen vieressä jäävät paikoilleen; kokonaan poistetulla tai
  kokonaan sumennetulla kuvalla pätee edelleen vedetty kehys. Koskee
  kuvatiedostoja ja PDF:issä olevia kuvia.
- **Peittopalkit koko rivin yli.** Editorin rivitilassa palkki kulkee
  nyt rivin ensimmäisestä viimeiseen sanaan, ei enää vain osuman sanan
  yli – sanan mittainen palkki paljastaa, kuinka pitkä sana oli, ja
  kuudesta merkistä postinumeron edellä voi arvata paikannimen.
  Merkinnät, summat ja taulukkosarakkeet arvon vieressä jäävät
  paikoilleen – palkki peittää kentän, ei laskun riviä. Uusi kytkin
  "Koko rivi" "Tekstirivien" vieressä palauttaa sanantarkan tilan, jos
  naapurisanojen pitää jäädä paikoilleen; valinta muistetaan.

### Korjattu

- **Kuvia HTML-sivuilla ja sähköposteissa ei tarkistettu – logossa
  oleva nimi jäi puhdistuksen jälkeen luettavaksi.** Sivuun upotettua
  kuvaa (``data:``-osoite) ei kosketettu lainkaan, vain sen
  vaihtoehtoista tekstiä; sähköpostin HTML-haaran logo (inline-kuva
  ilman tiedostonimeä) putosi liitesuotimen läpi; ja nimetyllä
  kuvaliitteellä kuvasääntö "sumenna"/"poista" ei vaikuttanut. Nyt
  kaikki kolme kulkevat saman reitin kuin kuvatiedosto:
  tekstintunnistus säilytetyssä kuvassa, kasvot, koodit, metatiedot ja
  kuvasääntö. Raportti mainitsee kuvat – myös varoituksen, jos ne
  jäävät ilman tekstintunnistusta tarkistamatta –, ja "Palauta upotetut
  kuvat" sekä osumapaneelin palautus tuntevat nyt myös nämä kuvat.
- **Office-tiedostoa kuvineen ei voitu puhdistaa lainkaan, jos
  tekstintunnistus ei osannut kieltä.** Macilla lukee järjestelmän
  oma tekstintunnistus; hindille, kreikalle, kroaatille tai liettualle
  se ei osaa ja sanoo sen vasta äskettäin – Wordissa, Excelissä,
  PowerPointissa ja OpenDocumentissa tämä kuitenkin keskeytti **koko**
  puhdistuksen, eikä tiedostoa syntynyt. Silti teksti olisi voitu
  puhdistaa moitteettomasti; vain kuva ei ollut luettavissa. Tiedosto
  kirjoitetaan nyt kuten PDF:ssä ja yksittäisissä kuvissa, ja
  tuloksessa lukee, ettei kuvia tarkistettu – syyn ja viittauksen
  kanssa kohtaan "Hallitse kieliä".

- **Excel-taulukoissa nimet jäivät valintalistoihin.** Pudotusvalikon
  (tietojen validointi) lista puhdistetaan nyt kuten mikä tahansa muu
  solun sisältö; viittaukset solualueisiin pysyvät koskemattomina,
  jotta taulukko pysyy ehjänä.
- **Missä paikkamerkki ei mahtunut, oli musta palkki – nyt siellä on
  lyhyempi kirjoitusasu.** `[GEBU_1]` merkinnän `[GEBURTSDATUM_1]`
  sijaan, ja vasta jos lyhyinkin muoto ei mahdu, peitetään. Palkki ei
  enää kerro kellekään, että siinä oli jotain; lyhyt paikkamerkki
  kertoo. Jälkikäsittely-editori osasi tämän jo, automaattinen
  puhdistus ei aiemmin. Kohdistustiedosto vie molemmat kirjoitusasut
  samaan arvoon, jotta myös lyhennetty voidaan palauttaa.
- **Ensimmäinen klikkaus "Korvaa"-toimintoon jätti jälkikäsittely-
  ikkunan hetkeksi jumiin.** Tunnistus, joka antaa paikkamerkille sen
  lajin (`[NAME_3]` merkinnän `[BEGRIFF_3]` sijaan), ladattiin vasta
  tällä hetkellä – noin kaksi kolme sekuntia. Se valmistellaan nyt
  taustalla ikkunan avautuessa; mitattuna 2289 millisekunnista tuli
  193.
- **Kaksi samanaikaista puhdistusta saattoi ladata saman kielimallin
  kahdesti** – esimerkiksi kansionvalvonta ja pääikkuna. Koska jokainen
  malli vie satoja megatavuja, muistintarve oli hetken kaksinkertainen.
  Nyt toinen ajo odottaa ensimmäisen mallia.
- **Paikka päivämäärärivillä poistetaan nyt myös silloin, kun
  kielimalli ei yksin tunnista sitä:** se, mikä on postinumerona
  paikkakunnan kanssa varmasti löydetty ("3335 Amstetten"), vetää
  paikannimensä koko asiakirjassa mukanaan – kuten sukunimi koko
  nimestä. Ja numerolla varustettu lyhenne nimen edellä ("T3 Hofbauer
  Christian") jää luettavaksi sen sijaan, että katoaisi paikkamerkin
  mukana.
- **Kolme vuotoa todellisen tilauksen toislukemasta suljettu:**
  käsittelijä "T3 Hofbauer Christian" laskettiin lyhenteen "T3" takia
  sarakeotsikoksi ja jäi luettavaksi; paikka, jonka kielimalli luki
  rivinvaihdon yli sarakeotsikkoon, nielaisi sanan "Pos." ja jätti
  asiakkaan etunimen paikoilleen; ja puhuttelulla varustettu nimi
  ("Herr Robert Köttel") veti mukaansa vain sukunimen, ei etunimeä –
  ja siksi jokaisen "Herr":in. Lyhenteet ovat nyt pelkkiä kirjaimia,
  kaksisanaiset nimet eivät ole otsikko, osumat katkaistaan ennen
  sarakeotsikkoa, ja puhuttelu ei lasketa osaksi nimeä.
- **Paikka päivämäärärivillä ("Melk, 05.08.2026") suoraan
  osoitelohkon alla jäi luettavaksi.** Kielimalli liimasi sen
  postinumerorivin paikkaan yhdeksi osumaksi, ja se putosi kokonaan
  postinumeromallia vasten. Nyt esiin jäävä jäännös pysyy omana
  osumanaan. Löydetty tuloksen uudella toislukemalla
  (`werkzeuge/zweitlesung.py`).
- **Mac: Skannaus kielellä, jota järjestelmän oma tekstintunnistus ei
  osaa (esim. hindi, kreikka, kroaatti, liettua), laskettiin
  tarkistetuksi.** Luettiin englanninkielisellä varajärjestelmällä,
  vieras kirjoitusjärjestelmä jäi kuvaan, ja raportti sanoi "ei
  löytynyt mitään". Nyt lukee "Kuva(t) EI tarkistettu(ja)" syyn
  kera, eikä kielten hallinta enää lupaa tällaisille kielille
  tekstintunnistusta pelkästään siksi, että Tesseract-kielitiedosto on
  olemassa.
- **PDF:ssä korvatun sanan jälkeinen välimerkki jää nyt paikoilleen.**
  Merkinnästä "Aufnahme am 01.03.2026, Entlassung am 04.03.2026." tuli
  aiemmin "Aufnahme am [DATUM_1] Entlassung am [DATUM_2]" – pilkku ja
  loppupiste puuttuivat, sekä paikkamerkeillä että siirretyillä
  päivämäärillä. Poistetaan nyt vain tunnistettu arvo, ei koko sanaa
  seuraavaan välilyöntiin asti; pilkku, puolipiste, piste tai sulku
  sen jälkeen jää paikoilleen, eikä paikkamerkki kulje niiden yli.
- **Venäjä ja ukraina toimivat huomaamatta heikommalla
  monikielimallilla**, jos sanamuotoanalyysin apupaketti (`pymorphy3`)
  puuttui – omia malleja ei silloin voitu ladata, ja "Львів" muuttui
  henkilöksi. Nimien tunnistukseen sanamuotoanalyysia ei tarvita; malli
  ladataan nyt ilman sitä, ja paikat ovat taas paikkoja.
- **Lisenssihuomautukset 16 kielessä olivat vanhentuneet.** Siellä
  luki yhä, että MPL-lähdekoodi toimitetaan "pyynnöstä", QPDF
  laskettiin MPL-2.0-lisensoiduksi, seitsemän osaa puuttui taulukosta
  (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp,
  YuNet), spaCy-kappale oli englanniksi, ja lopussa riippui
  englanninkielinen varaosio. Nyt kaikki 18 versiota ovat
  saksankielisen tasolla: lähdearkistot pysyvästi osoitteessa
  maskuro.com/quellcode/oss/, QPDF Apache-2.0, Qt-LGPL-reitti, mallien
  alkuperä. Myös englanninkielisessä taulukossa on puuttuneet rivit.

- **Sopimussanat genetiivissä ("des Angebotsinhaltes", "des Anbotes",
  "des Terminplanes") eivät enää kelpaa paikaksi.** Yksittäinen sana
  genetiivi- tai datiiviartikkelin jälkeen taivutuspäätteellä on
  lajisana – paikannimet eivät taivu ("nach Graz"). Jos paikka on
  muualla asiakirjassa ilman artikkelia ("Burgenland"), myös "des
  Burgenlandes" tunnistetaan edelleen.
- **Siirretyt, naamioidut ja keksityt arvot rasteroivat PDF-sivun.**
  Poiston jälkeinen tarkistus salli löytösuorakulmiossa vain
  paikkamerkin hakasulkeissa; siirretty päivämäärä ("01.07.2026") tai
  naamioitu arvo ("****1234") laskettiin huomaamatta jääneeksi
  jäänteeksi, ja sivu muunnettiin varmuuden vuoksi kuvaksi – "Korvaa"-
  toiminnossa ei. Nyt tällaiset sivut pysyvät tekstinä, ja
  palautus paneelista tai kehyksestä tuottaa taas alkuperäisen.
- **Moniosaisia korvausarvoja ei voinut peruuttaa PDF:ssä
  osumapaneelin kautta.** Keksitty nimi ("Greta Mayrhofer") tai
  naamioitu IBAN ("**** **** **** **** 3201") koostuu useasta sanasta;
  löytökohdan haku vertasi sanaa sanalta ja ilmoitti "Paikkamerkkiä ei
  löytynyt asiakirjasta". Nyt saman rivin peräkkäiset sanat luetaan
  yhteen.
- **Ilman korvausta poistetun arvon palauttamisen jälkeen sen
  panelirivi jäi paikoilleen.** Arvoilla, jotka strategia "peitä"
  paikkamerkittömässä tilassa poistaa ilman korvausta, ei ole
  paikkamerkkiä, josta paneeli voisi mitata katoamisen. Nyt rivi
  yliviivataan, heti kun arvo on jälleen asiakirjassa.

- **Lyhenneyhdyssanat kuten "E-Helfer" tai "U-Bahn" eivät enää kelpaa
  nimeksi.**
- **Tavutusjäänteet ("Leis-") ja äärimmäisen pitkät yhdyssanat
  ("Bauarbeitenkoordinationsgesetzes", "Baustellenkoordinator") eivät
  enää kelpaa nimeksi tai paikaksi.** Skannatussa
  kilpailutustekstissä tämä poisti 28 turhaa peittoa vähemmän.
- **Skannattujen tarjousten nimikeluetteloita ei enää lasketa
  nimiluetteloksi.** Luetteloiden lisäkierros (lyhyet rivit) teki
  sanoista "Kälterohr" ja "Außengeräte" henkilöitä; se jättää nyt
  väliin, heti kun rivin alussa on nimikenumero kuten "1.1.5".
  Sähköpostiketjujen päivämäärärivejä ei tässä lasketa
  nimikenumeroiksi.
- **Sarakeotsikoita ja nimikenumeroita skannatuissa tarjouksissa
  ("Pos.", "Pos. 1.1.3", lyhenteet "E/L/S") pidettiin nimenä tai
  paikkana.** Yksin omalla rivillään oleva lyhenne, merkintä numeron
  kera ja yksittäiset kirjaimet riveittäin eivät ole sellaisia.
- **Sivu "hengitti" jälkikäsittely-ikkunassa vertailusuurennuslasin
  avaamisen jälkeen** – kohdissa "Sivun leveys" ja "Sovita" mittakaava
  riippuu näkymäikkunasta, ja se muuttuu jokaisen tulevan tai
  poistuvan vierityspalkin myötä; jokainen seuraava toimenpide siirsi
  sivua hieman. Kangas korjaa tämän nyt itsestään, kunnes se pysyy
  paikallaan. Ja zoomauspainikkeet, säädin ja pikanäppäimet pitävät
  kuvan keskikohdan myös silloin, kun sisäänpäin zoomattaessa ilmestyy
  vierityspalkki.
- **Poikittain tallennetut skannaukset luetaan nyt pystyasennossa, eikä
  pienpainatus suurissa skannauksissa enää katoa.** 24-sivuinen
  skannattu tarjous säilytti jokaisessa alatunnisteessa kuusi pankki-
  IBAN:ia, kaupparekisterinumeron ja ALV-tunnisteen luettavina: skannaus
  oli PDF:ssä käännettynä 90°, ja tekstintunnistus jätti erittäin
  suurilla kuvilla kuvakoosta riippuen kokonaisia rivejä väliin. Nyt
  näkyvä kierto otetaan huomioon ja suuret kuvat luetaan
  päällekkäisinä nauhoina – alatunnisteet ovat mustia.
- **Kadut, jotka on nimetty henkilön mukaan väliviivalla ennen
  perussanaa ("Josef Admanseder-Straße 7", "Abt-Karl-Straße 8",
  "Dr.-Karl-Renner-Straße 12"), tunnistetaan osoitteeksi.** Skannatun
  tarjouksen kirjekuvassa tällainen osoite jäi luettavaksi, koska malli
  vaati välilyönnin ennen sanaa "Straße".
- **Tekstintunnistuksesta tulevat IBAN:it, joissa on O nollan sijaan tai
  l ykkösen sijaan, tunnistetaan nyt.** Skannauksen pienpainatuksessa
  tekstintunnistus lukee numeroita mielellään kirjaimina; numero sai
  silloin IBAN:in muodon, mutta tarkistussumma ei täsmännyt, ja se jäi
  paikoilleen. Jos tarkistussumma epäonnistuu, kokeillaan nyt lukemaa
  numeroilla – jos se täsmää, kyseessä on IBAN. Väärät
  tarkistusnumerot pysyvät vääränä.
- **Lauseenkatkelmia kuten "folgenden Codes auf der" pidettiin
  paikkana.** Nimi tai paikka, joka alkaa pienellä kirjaimella, ei ole
  sellainen – lukuun ottamatta aatelispartikkeleita ("van Gogh", "de
  Vries").
- **Editorissa peittopalkin viereen jäi viimeinen kirjain**
  ("…6", "…t", "…g"), ja palkin korkeus oli vedetyn kehyksen korkeus
  rivin korkeuden sijaan. Syynä: jos editori ei voinut mitata sivua,
  se piti jokaista kehystä tapauksena "ei osunut sanaan" ja sovelsi
  sen tarkasti – ilman sääntöä, jonka mukaan puoli sanaa ei koskaan
  jää paikoilleen. Sama tapahtui yksittäisillä tekstikäskyillä, joita
  editori ei osannut paikantaa. Nyt vieressä laskee aina sanalaatikko:
  se, minkä kehys olennaisesti peittää, poistuu kokonaan.
- **Sanan viimeinen kirjain ulottui peittopalkin yli.** Palkki
  mitattiin kirjasinmittojen etenemisleveydestä; jos kirjasin piirtää
  glyyfin leveämmäksi, sen jäännös näkyi palkin vieressä. Merkin
  laatikko sisältää nyt myös piirretyn glyyfin.
- **Sivun kuvaksi muuntamisen ilmoitus lupasi liikaa.** "Ulkoasu pysyy
  samana" ei pidä rasteroinnin jälkeen paikkaansa: kirjasin ja
  grafiikka ovat silloin kuvapisteitä, tiedosto suurenee. Ilmoitus
  sanoo tämän nyt – ja mainitsee myös toisen syyn rasterointiin
  (uudelleenrakennus olisi vaurioittanut sivua).
- **Poistetun arvon jälkeinen teksti siirtyi jopa pisteen verran
  vasemmalle.** Rivin uudelleenladonnassa alku mitattiin glyyfin
  reunasta, jatko kynän lähtökohdasta – ensimmäisen kirjaimen
  etenemisleveys jäi virheenä paikoilleen ("C" 0,5 pt, "I" 1,0 pt).
  Ladonta laskee nyt läpikotaisin kynän lähtökohdasta; jälkilause on
  kymmenesosapisteen tarkkuudella paikallaan.
- **Itävaltalainen ALV-tunniste välilyönneillä ("ATU 187 35901") ja
  kaupparekisterinumero ilman "FN" sen merkinnän alla
  ("Firmenbuchnummer: 30799v") tunnistetaan.** Molemmat olivat käsin
  kirjoitettuna skannatussa kilpailutuslomakkeessa ja jäivät
  luettaviksi, vaikka tekstintunnistus oli lukenut ne oikein.
- **Poikittaiset PDF-sivut muunnettiin peittämisen jälkeen turhaan
  kuviksi.** Eheystarkistus vertasi alkuperäistä ja tulosta käännetyssä
  näkymässä, mutta laski niiden peittovyöhykkeet kääntämättömänä –
  sivulla, jossa on kiertomerkintä, oma peitto oli siksi vyöhykkeensä
  vieressä ja laskettiin vaurioksi. Tällaiset sivut säilyttävät nyt
  tekstitasonsa ja vektorigrafiikkansa.
- **Myös suoria sivuja muunnettiin ajoittain turhaan kuviksi**, kun
  paikkamerkin jälkeinen teksti siirtyi pisteen verran – sallittua,
  mutta kuvavertailu oli tarkempi kuin oma toleranssinsa. Se vertaa nyt
  puolen pisteen tarkkuudella ja osuu siten toleranssiinsa täsmälleen:
  kahteen pisteeseen asti poikkeama ei laukaise mitään, sen yli kaikki.
- **Upotettujen lomake-objektien tiedot jäivät paikoilleen.** Jotkin
  mallipohjat tallentavat kirjekuvan tai kirjeen lopun omana
  lomakkeena, jonka sivu vain sisällyttää. Osuma siinä suunniteltiin ja
  laskettiin poistetuksi, mutta sitä ei koskaan kirjoitettu – teksti
  jäi paikoilleen, ja vain koko sivun rasterointi sai sen kiinni. Nyt
  itse lomake kirjoitetaan uudelleen; usealla sivulla oleva lomake
  vain kerran.
- **PDF-sivuja rasteroitiin kuvaksi, vaikka mitään luettavaa ei ollut
  jäljellä.** Seitsemänsivuinen tarjous kärsi tästä kuudella sivulla;
  se kasvoi 73 kt:sta 3,3 Mt:hen ja menetti kirjasimensa kuvaksi.
  Syynä olivat asiakirjassa useasti peräkkäin olevat välilyönnit, jotka
  lukija ilmoittaa vain kerran: poistetun tiedon jälkeinen teksti
  siirtyi sen leveyden verran oikealle, jälkitarkistus löysi
  naapurisanan löytösuorakulmiosta ja turvautui rasterointiin.
  Säilytetyt rivijäänteet pysyvät nyt jälleen tarkasti paikoillaan;
  sama tarjous puhdistetaan ilman yhtäkään rasteroitua sivua (76 kt).
- **Avainten nimiä ja laskun otsikoita pidettiin henkilöinä.**
  Pääsytiedostossa korvattiin ympäristömuuttujan nimi
  ("AWS_ACCESS_KEY_ID"), ei vain sen arvoa; englanninkielisessä
  laskussa otsikko "Bill to" putosi etunimenä. Versaalein ja
  alaviivoin kirjoitettu tunniste ei koskaan ole nimi, eikä sana
  rivillä, joka on kokonaisuutena kenttämerkintä – vastaanottaja sen
  alla löytyy edelleen.
- **Haku jälkikäsittely-ikkunassa hidastui suurilla PDF-sivuilla.**
  Jokainen hakukentän kirjain rasteroi sivun uudelleen, vaikka vain
  korostus muuttui. Renderöity sivukuva pysyy nyt paikoillaan, kunhan
  sivu, zoomaus ja näkymä ovat samat – myös vertailusuurennuslasin
  alkuperäinen; selailu, zoomaus ja uusi tiedostotila piirtävät edelleen
  tuoreena.
- **Nimikenumeroita tarjouksissa pidettiin IP-osoitteena tai
  puhelinnumerona.** Tuoterivi kuten "1.3.3.4 … 5-Port Gigabit Switch"
  muutti jäsentelynumeron verkko-osoitteeksi, koska "Port" laskettiin
  tekniseksi ympäristöksi – nyt se lasketaan vain itsenäisenä tietona
  ("Port 80"), ei sananosana. Ja "1.3.3.6 216879" (nimike- ja
  tuotenumero) ei enää peity puhelinnumerona. Todelliset IP-osoitteet
  ja puhelinnumerot tällaisissa listoissa tunnistetaan edelleen.
- **Tuoterivejä tarjouksissa pidettiin postinumerona paikkakunnan
  kanssa.** "35252 DIETZEL SALR" (tuotenumero valmistajan kera) ja
  "1000 AWG" (määrä johtimen poikkipinnan kera) peitettiin numeroiduissa
  nimikeriveillä osoitteena, koska isoin kirjaimin kirjoitettu sana
  numeron jälkeen laskettiin versaalilla paikannimeksi.
  Nimikeluetteloissa tämä ei enää päde; "1080 WIEN" osoitelohkossa ja
  pienellä kirjoitetut paikat tunnistetaan edelleen kaikkialla.
- **Lisänimentunnistus peitti tarjouksissa roolirivejä ja
  sarakeotsikoita.** "Partiestundensatz Monteur + E-Helfer" laskettiin
  49 kertaa henkilöksi, sarakeotsikko "Pos. Bezeichnung Menge EH" 19
  kertaa paikaksi – 19-sivuinen tilaus muuttui siksi
  lukukelvottomaksi. Tällaiset osumat nimikeriveillä poistuvat nyt,
  jos ne itse kantavat merkkejä, joita nimessä ei ole (plus,
  kauttaviiva, numero, lyhenne) – myös silloin, kun rivi päättyy
  summaan ("Alternativ Markt … - PV/LS AC-Versorgung 1 290,00"). Nimet
  luetteloissa ja listoissa – juuri mihin taso on tarkoitettu – jäävät
  koskemattomiksi.
- **"Der Kunde" teki liikeehdoissa jokaisesta "Kunde"-sanasta nimen.**
  Kun lisänimentunnistus otti artikkelin mukaan osumaan, se laskettiin
  kaksiosaiseksi nimeksi ja suojasi kaikki 35 muuta saman sanan kohtaa.
  Nyt artikkeli vähennetään, ja "der Kunde" poistuu kuten "des Kunden"
  jo aiemminkin.
- **Merkintöjä pidettiin arvona.** "E-Mail" peitettiin seitsemän kertaa
  sähköpostiosoitteena, "Telefonnummer" ja "Faxnummer"
  puhelinnumerona. Osoite ilman @-merkkiä ja puhelinnumero ilman
  numeroita eivät enää lasketa.
- **Yhden kirjaimen sarakelyhenteitä ("L: 154,50", "S: 0,00") pidettiin
  nimenä** – 25 kertaa aurinkosähkötarjouksessa. Yksittäinen kirjain ei
  ole nimi eikä paikka.
- **PDF-sivuja muunnettiin liian usein kuvaksi.** Kaksi syytä, molemmat
  löydetty todellisista tarjouksista: jos PDF asettaa jokaisen glyyfin
  omana käskynä ja niiden joukossa on välilyöntiglyyfi ilman
  tekstimerkkiä, kohdistus siirtyi siitä lähtien yhdellä – poistetusta
  arvosta jäi viimeinen kirjain paikoilleen ("ŠkodaTopCar**d**"), ja
  jälkitarkistus rasteroi sivun aiheellisesti. Ja rivin lopussa
  tavutettu sana ("Datenschutz-") laskettiin lukukirjaston
  tavuviivamerkin takia siirtyneeksi. Molemmat korjattu: ajoneuvo-
  tarjous meni neljästä rasteroidusta sivusta nollaan, 19-sivuinen
  tilaus seitsemästä nollaan – kirjasin pysyy kirjasimena, tiedosto
  pysyy pienenä.
- **Kaksi muuta rasterointisyytä korjattu:** jos asiakirja itse tuo
  mukanaan kirjasimen nimeltä "F1", paikkamerkit kuvien päällä
  asetettiin sen kirjasimella ja olivat lukukelvottomia – nyt omalle
  merkintäkirjasimelle annetaan vapaa nimi. Ja jos lukukirjastolta
  puuttuu välilyönti keskellä pitkää tekstikäskyä, kohta todistetaan
  nyt myös monitavuisilla kirjasimilla (sama koodi, sama merkki) sen
  sijaan, että se arvattaisiin loppuun – aiemmin siitä jäi poistetun
  arvon kirjain paikoilleen ja jäljelle jäänyt teksti siirtyi näkyvästi
  sivuun. Lisäksi kaksi viimeistä tapausta: käsky kymmenistä
  välilyöntiglyyfeistä sai kohdistuksen karkaamaan (sen jälkeinen nimi
  jäi paikoilleen), ja suuri otsikko etenemisleveyden kera ei löytänyt
  ensimmäistä merkkiään (yrityksen nimi jäi paikoilleen). **Yhdeksästä
  todellisesta tarjouksesta ei nyt rasteroidu enää yhtäkään sivua** –
  aiemmin niitä oli 30/90.
- **Rasteroitaessa kuvat katosivat mustan lohkon alle.** Kun sivu on
  muutettava kuvaksi, se renderöidään alkuperäisestä – eikä se tunne
  mitään kuvien puhdistusta. Aiemmin siksi *jokainen* sivun kuva-alue
  jäi palkin alle, myös koskemattomat. Tarjouksessa osoite ja kaksi
  sertifikaattilogoa olivat samassa kirjekuvakuvassa; palkki vei logot
  mukanaan. Nyt käytetään jo puhdistettua kuvaa: osoite siinä on
  peitetty, kaikki muu jää näkyviin. Poistettu kuva jättää jälkeensä
  valkoisen paperin mustan laatikon sijaan.

- **Puhdistetut skannaukset kasvoivat moninkertaisiksi
  alkuperäiseen nähden.** Jokainen kuva, jossa jotain peitettiin,
  palasi tiedostoon pakkaamattomana raakakuvana – 24-sivuisella
  skannauksella tiedosto kasvoi siten 11,8:sta 52,9 Mt:hen. Kuvat
  säilyttävät nyt sen lajin, jossa ne olivat: valokuva pysyy
  valokuvana, faksiskannaus pysyy mustavalkoisena, väritön kuva ei
  tallennu värikuvana. Sama tiedosto on nyt 15,6 Mt, ilman näkyvää
  eroa.

- **Toimistolaitteista tulevat skannatut PDF-tiedostot palasivat
  raitakuvioina.** Tällaiset skannaukset asettavat kirjasimen
  terävänä mustavalkokerroksena karkean värikuvan päälle – Canon,
  Xerox ja Kofax rakentavat tiedostonsa näin. Kuvassa peitettäessä
  tämä kerros kirjoitettiin väärin takaisin; tulos oli
  lukukelvoton. Kuusisivuisella tarjouksella tämä koski yhdeksää
  kuudestatoista kuvasta. Se käsitellään nyt oikein, omassa värissään,
  ja peitetyt kohdat ovat siinä todella poissa.

- **"Poista kaikki kuvat" vei skannatulta sivulta sen tekstin.**
  Tällaisen skannauksen kirjasinkerros on teknisesti kuva – se
  poistettiin tai sumennettiin mukana, ja jäljelle jäi tyhjä lehti. Se
  jää nyt paikoilleen; logot, leimat ja allekirjoitukset väistyvät
  edelleen.

- **Vaurioituneiden PDF-sivujen tarkistus ei enää rasteroi mitättömän
  siirtymän takia.** Puhdistuksessa uudelleen ankkuroitu tekstinpätkä
  saa siirtyä enintään kaksi pistettä; kuvavertailu laski tämän
  silti vaurioksi ja rakensi sivun uudelleen kuvana – tällöin
  vektorigrafiikka kuten taulukkoviivat hävisi, ja löytökohtien päällä
  oli palkki paikkamerkin sijaan. Vertailu sallii nyt saman pienen
  siirtymän kuin sanatarkistus; todelliset vauriot huomataan edelleen.

- **Monen arvon peräkkäinen palauttaminen ei enää epäonnistu Windowsissa
  "Käyttö estetty" -virheeseen.** Office-tiedostossa monta panelirivi
  lyhyessä ajassa peruuttava saattoi kaatua virustorjunnan
  lyhytaikaiseen tiedostolukkoon; vaihto odottaa nyt tällaisia lukkoja
  hetken.
- **Windowsin komentojen välitysreitti lopetti tarkistajan sen sijaan,
  että olisi tarkistanut.** Kuuntelevan instanssin elossaolotarkistus
  lähetti Windowsissa vahingossa todellisen Ctrl+C:n omalle
  konsoliryhmälle; se kysyy nyt järjestelmältä ilman signaalia.

- **Moniosaiset kenttämerkinnät eivät vaikuttaneet, mutta niiden
  katkelmat vaikuttivat.** "Date of birth", "Bank account", "Cuenta
  bancaria" ja "Numero de cliente" olivat merkintälistalla, mutta ne
  pilkottiin siellä yksittäisiksi sanoiksi ja eivät siksi koskaan
  osuneet; jäljelle jäivät sananosat kuten "de" ja "of", jotka siitä
  lähtien laskettiin merkinnäksi – "de" on kuitenkin nimen osa ("Anna
  de Vries"). Molemmat on korjattu: ilmaukset vaikuttavat nyt
  kokonaisuutena, katkelmat ovat poissa.

- **Saksankieliset tervehdykset "ß"-kirjaimella käsiteltiin
  merkinnästä huolimatta henkilönnimenä.** "Herzliche Grüße"- tai "Mit
  freundlichen Grüßen" -tekstin alla oli tuloksessa paikkamerkki,
  vaikka molemmat ilmaukset ovat aina olleet vastalistalla. Syynä oli
  kirjoitusasu, joka ei koskaan päätynyt vertailuun; tämä koski
  kahdeksaa merkintää viidellä listalla. Ne vaikuttavat nyt kaikki.

- **"John Staff" jäi korvaamatta.** Sukunimi, joka on samalla
  englanninkielinen sarakeotsikko, hylättiin merkintäsuotimen mukana.
  Otsikko pysyy edelleen koskemattomana, sen alla oleva nimi
  korvataan taas.

- **Merkittyjen lomakekenttien arvot pysyvät suojattuina
  tekoälytasolla.** Tekoälytason paikallinen tuomari sai aiemmin
  arvioitavakseen myös osumia, joiden merkitys oli jo osoitettu
  kenttämerkinnällä ("Geburtsdatum:" arvon yläpuolella) – ja sai hylätä
  ne. Tällaisia rakenteellisesti todistettuja arvoja ei enää esitetä
  sille. Kohdistustiedosto mainitsee nyt jokaisen korvauksen kohdalla
  lisäksi tunnistustavan ("beleg").

- **PDF-sivu, jonka säilytetty teksti vahingoittui puhdistuksessa,
  tunnistetaan nyt ja rakennetaan uudelleen alkuperäisen
  kuvana.** Joillakin tuottajakirjasimilla säilytetyt tekstikohdat
  saattoivat puhdistuksen jälkeen näkyä mustina lohkoina tai sanat
  saattoivat siirtyä kiinni toisiinsa, vaikka kaikki poistettavat
  tiedot poistettiin oikein. Maskuro vertaa nyt tulosta sanalta
  sanalta ja kuvapisteeltä kuvapisteeltä alkuperäiseen; vaurioitunut
  sivu korvataan siistillä kuvallaan – peittopalkkeineen löytökohtien
  päällä, peitettyine kuva-alueineen ja haettavine tekstineen. Sivu
  pysyy luettavana, poisto luotettavana.

### Muutettu

- **Käännetyissä käyttöliittymissä jokainen termi on nyt kaikkialla
  sama.** Samalle saksalaiselle sanalle oli ikkunasta riippuen kaksi
  tai kolme rinnakkaista käännöstä: tarkistuspöytäkirja oli norjaksi
  osittain "Revisjonslogg", osittain "Kontrollogg", ilmaistaso
  osittain "Gratisnivå", osittain "Gratisversjon" – ja vastaavasti
  kymmenkunnassa muussa kielessä. Asetusta etsivä löysi sen
  seuraavasta ikkunasta eri nimellä. Yhtenäistettiin sanaan, jota
  käyttöliittymä joka tapauksessa käyttää useimmin.

  Samalla paljastui kohtia, joissa yksi sana tarkoitti kahta
  **eri** asiaa: ranska, kreikka ja korea käyttivät samaa ilmausta
  sanoille "peittää" ja "naamioida" – juuri siellä, missä ohjelma
  selittää eron ("Peittäminen poistaa ilman korvausta, naamiointi
  säilyttää muodon"). Molemmat on nyt eroteltu toisistaan. Ruotsille
  tämä päätös on vielä tekemättä: siellä peittäminen on "maskera" –
  sama sana kuin naamiointi.

- **Kysymys käyttötavasta ensimmäisellä käynnistyksellä on poistettu.**
  Pian käynnistyksen jälkeen tuli ikkuna ("Yksityinen vai yrityksessä?"),
  ja asetuksissa oli sitä koskeva rivi. Kumpaakaan ei enää ole –
  ilman korvaavaa toimintoa. Tieto, johon mikään ei liity, ilmoittaa
  väärin, kuka tarvitsee väärän lisenssin, eikä rehellinen sitä tarvitse;
  se maksoi jokaiselle klikkauksen hetkellä, jolloin kukaan ei ajattele
  lisenssityyppejä. Mikä lisenssi on oikea, näkyy siellä, missä se
  päätetään: hintasivulla, kassalla ja ohjeessa. Maskuroa keskitetysti
  jakelevat talot asettavat käyttötavan edelleen asetustiedoston
  kautta.

- **Lisenssityyppien huomautukset nimeävät nyt tapauksen, josta on
  kyse.** Yksityislisenssi koskee yksinomaan yksityiskäyttöä; jokainen
  ammatillinen tai kaupallinen työ tarvitsee yrityslisenssin – myös
  yksinyrittäjänä ilman työntekijöitä. Näin luki lisenssiehdoissa,
  mutta ei ohjelmassa eikä ohjeessa: siellä puhuttiin aina vain
  yritysverkkotunnuksesta, eikä se koske juuri tätä tapausta:
  yksinyrittäjän kone ei kuulu mihinkään verkkotunnukseen. Huomautus
  yksityislisenssiä luettaessa kertoo tämän nyt, samoin ohjeen
  lisenssiluku ja usein kysytyt kysymykset, jotka ovat saaneet siihen
  oman kohdan. Mitään ei edelleenkään lukita.

- **Vielä toimittamattomat tiet ovat nyt yhdessä.** Asetuksiin on
  lisätty sivu "Kehittäjä"; siellä ovat maksimaalinen tunnistus
  (tekoäly) vastatarkistuksineen, sanalistakatalogi ja
  kansionvalvonta. Kaikki kolme on rakennettu, mutta testaamatta
  laajasti käytössä – ne näkyvät siksi vain kehittäjälisenssillä,
  ja kaikkialla samanaikaisesti: sivu, valikkomerkinnät ja vaikutus
  ajossa riippuvat samasta päätöksestä. Ilman tätä lisenssiä aiemmin
  kytketty tekoälytaso pysyy vaikutuksettomana; sen asetusta ei poisteta
  ja se pätee taas, heti kun tie toimitetaan.

### Parannettu

- **"Mitä etsitään" näyttää kolme muuta luetteloa
  nimentunnistuksesta.** Puhuttelut, joiden jälkeen seuraava sana
  luetaan nimeksi; arvonimet ja roolit, joiden jälkeen se **ei**
  vielä ole nimi ("Herr Bürgermeister Huber"); ja kahdeksankymmentä
  monikielistä merkintää, joista diaarinumerot ja tapausnumerot
  tunnistetaan. Kaikki kolme ovat vaikuttaneet aina, mutta eivät
  näkyneet yleiskatsauksessa.

- **"Mitä etsitään" näyttää kaksi aiemmin puuttunutta sanalistaa.**
  Puhuttelut ja arvonimet, jotka tekevät edellä olevasta sanasta
  nimen ("Herr", "Frau", "Dr."), sekä standardointijärjestöjen
  lyhenteet, joilla Maskuro erottaa normiviittauksen kuten "ÖNORM B
  2110" henkilöstä. Molemmat vaikuttavat tunnistukseen aina, mutta
  eivät näkyneet yleiskatsauksessa.

- **Nimikeluettelot, sisällysluettelot, varusteluettelot ja
  normiviittaukset pysyvät luettavina.** Tunnistus näkee nyt rivin
  rakenteen: arvattu nimi jäsentelyrivillä ("1.3.1 Energieerdkabel
  1kV"), luettelorivillä johtoviivoin, luettelomerkinnässä ("-
  kabelloses Laden mit Magnetring"), määrä-/hintarivin yläpuolella,
  sarakeotsikossa tai sanan "mittels" jälkeen on asiatermi eikä sitä
  enää korvata. Todelliset nimet pysyvät suojattuina – puhuttelun,
  kenttämerkinnän ja asiakirjan muualla olevan todisteen kautta;
  mittauskorpuksessa yksikään tieto ei menettänyt suojaansa.
  Liikekorpuksessa virhehälytykset laskevat siten 25:stä 6:een.

- **Otsikoita, lomakemerkintöjä ja tervehdyksiä pidetään harvemmin
  niminä – saksaksi ja englanniksi.** Sanalistat, joilla Maskuro
  erottaa asiasanat henkilönnimistä, ovat kasvaneet huomattavasti:
  merkinnät laskuista, lomakkeista ja viranomaispostista
  ("Aktenzeichen", "Verwendungszweck", "Kostenstelle", "Sort code",
  "Subtotal"), hakemusten ja raporttien otsikot ("WERDEGANG",
  "QUALIFIKATIONEN", "SUMMARY", "REFERENCES"), saksalaiset ja
  englantilaiset asiakirjalajit ("Auftragsbestätigung",
  "Niederschrift", "Timesheet", "Agreement") sekä käskymuodot
  ohjeista ("Sende…", "Select…"). Englanninkielinen puoli oli tässä
  aiemmin silmiinpistävän ohut.

- **Merkityt kentät kertovat nyt sisältönsä myös silloin, kun merkintä
  on yhdyssana.** "Lieferanschrift", "Rechnungsadresse",
  "Sachbearbeiterin", "Kontoinhaber", "Contact person" ja "Billing
  address" liittävät arvon vieressä tai alla nyt samaan lajiin kuin
  yksinkertainen "Anschrift" tai "Name" – täytetyssä lomakkeessa
  ruutuineen tämä on ero löydetyn ja huomaamatta jääneen välillä.

- **Jälkikäsittely-ikkunassa hiiren rulla selaa eteenpäin sivun
  reunalla.** Sivun lopussa jatkava päätyy seuraavan sivun alkuun; sivun
  alussa taaksepäin vierittävä edellisen sivun loppuun – asiakirjan voi
  näin vierittää alusta loppuun ilman sivupainikkeita. Näppäimistö
  (Page Up/Page Down) osasi tämän jo; lyhyt tauko kahden sivunvaihdon
  välillä estää kosketuslevyn jälkiliikkeen kuljettamasta puolen
  asiakirjan yli.

- **Sivujen pienoiskuvat jälkikäsittely-ikkunassa ovat nyt keskellä
  osiota.** Aiemmin ne kiinnittyivät vasempaan reunaan, ja
  leventäessä vain oikean puolen tyhjä reuna kasvoi.

- **Jälkikäsittely-ikkunan työkalurivi näyttää ryhmänsä.**
  Erottimissa on nyt tilaa ja väriä, "Etsi" ja "Siirrä kaikille
  sivuille" ovat omina ryhminään työkalujen vieressä, ja "Siirrä"
  näkyy enää asiakirjatyypeissä, joissa se voi vaikuttaa johonkin.
  Jokaisella rivin ja valikkojen merkinnällä on nyt kuva:
  "Tekstirivit" ja vertailusuurennuslasi ovat saaneet omat kuvakkeensa
  (suurennuslasi jakoi omansa aiemmin merkinnän "Ennen/jälkeen"
  kanssa), lisäksi zoomaus, koko sivu, sivun leveys, kääntäminen,
  selailu ja pikanäppäimet. "Avaa järjestelmän ohjelmalla" on nyt
  myös rivillä tulostuksen vieressä – tie valmiista tuloksesta
  tuttuun ohjelmaan on yksi klikkaus, ei valikkopolku.

- **Leikepöydän puhdistuksen kohdalla lukee taas, että asia on
  tarkistettava.** Asetuksissa huomautus näkyy pysyvästi kytkimen
  vieressä: Maskuro voi jättää henkilötietoja huomaamatta tai käsitellä
  tietoja väärin, ja liitetty teksti on tarkistettava ennen luovutusta.
  Kytkettäessä sen mainitsee lisäksi ilmoitus, ja se merkitään
  tulostealueelle – myös silloin, kun ilmaisualueella ei ole kuvaketta
  käynnissä. Jokaisella yksittäisellä kopiointikerralla se ei
  tarkoituksella näy: huomautus, joka tulisi viisikymmentä kertaa
  päivässä, jäisi kolmannen kerran jälkeen lukematta.

## 0.10.36-beta.1 – 20. elokuuta 2026

### Parannettu

- **Teknisiä liikeasiakirjoja ei enää peitetä pirstaleiksi.** Neljä
  tunnistusjarrutusta, saatu yhdestätoista todellisesta tarjouksesta ja
  tilauksesta: jäsentelynumerot („1.3.1.1“) eivät enää kelpaa IP-osoitteiksi,
  standardiviittaukset („ÖNORM EN 62446“) ja tunnistekoodit eivät enää
  postinumeroiksi tai puhelinnumeroiksi, ja artikkelin jälkeiset roolisanat
  („der Kunde“, „des Auftraggebers“) eivät enää nimiksi – todellisen
  tarjouksen sopimusehdoissa kaikki 46 roolisanaa ovat siten taas
  luettavissa peittämisen sijaan. Osoitteet maatunnuksella („A 3390 Melk“,
  „D-94032 Passau“) poistetaan nyt kokonaan sen sijaan, että postinumero
  jäisi orvoksi paikoilleen.

- **Sanalistat ovat nyt kokonaan tarkasteltavissa.** Kohdasta „Ohje →
  Sanalistat …“ voi selata paikallisesti käytettyjä tunnistus- ja
  vastatarkistuslistoja kielen, tarkoituksen, lähteen ja sisällön kanssa.
  Mukana ovat myös Wordfreq-, lääketieteelliset, henkilökohtaiset ja
  keskitetysti ylläpidetyt listat sekä keksittyjen korvausarvojen varannot.
  Käyttöohje kuvaa luettelon omassa osiossaan.

- **Valmiit tiedostorivit näyttävät käytetyn tunnistuskielen.** Sanan
  „valmis“ perässä lukee nyt esimerkiksi „saksa“ tai „englanti“, jotta
  sopimaton automaattinen kielivalinta huomataan heti. Jos toisen asennetun
  kielen piti astua väliin, nuoli näyttää molemmat kielet.

- **Uusi vertailusuurennuslasi näyttää lukiessa heti vastaavan kohdan
  alkuperäisessä.** Sen suurennettu alkuperäisleike seuraa hiiren osoitinta
  edelleen muokattavan tuloksen yläpuolella; tekstissä se seuraa
  kappaletta. Suurennuslasia voi käyttää ikkunan reunassa tai vetää irti
  omaksi, suurennettavaksi ikkunaksi. Sen zoomaus on säädettävissä suoraan
  välillä 50–300 prosenttia ja se muistetaan aivan kuten kytkeminen
  päällekin. „Palauta oletukset“ tuo myös suurennetun tai huonosti
  telakoidun suurennuslasin takaisin vasemmalle käytettävän kokoiseksi.
  Korvatut alkuperäisarvot on korostettu suurennuslasissa keltaisella,
  jotta niihin liittyvät sanat huomataan heti lukiessa. Kerran
  käyttöönotettuna se avautuu jälleen tulevissa sopivissa asiakirjoissa –
  myös ohjelman uudelleenkäynnistyksen jälkeen. Aiempi ennen/jälkeen-
  vaihtokytkin säilyy näkymävalikossa. Käyttöohje kuvaa sen omassa
  osiossaan.

- **Avoimen lähdekoodin ja mallien lähdeviitteet ovat nyt julkaisukohtaisen
  tarkkoja.** Paketin rakennus tuottaa koneellisesti luettavan
  komponenttiluettelon mukana toimitettujen lisenssitekstien tarkisteineen.
  MPL-lähteet, mallien alkuperä, kiinteät revisiot, muutokset ja SHA-256
  todistetaan erikseen; jälkiladatut mallit saavat alkuperätodisteensa
  suoraan mallikansioon. Liikkuvat Tesseract- ja spaCy-hankintaluettelot on
  kiinnitetty pysyviksi. Myyntiartefaktit pysyvät estettyinä, kunnes kaikki
  lähteet ja malliliitteet on julkaistu ja tarkistettu.

- **Paikallinen wordfreq-tietovaranto on nyt kokonaan lisenssein
  todistettu.** Paketin rakennus tarkistaa version 3.1.1, 39 muuttumatonta
  pientä listaa mukaan lukien CJK ja kiinalaisten merkkien kartta lukumäärän,
  koon ja manifestin tarkisteen suhteen. Apache-2.0-koodiviite, täydellinen
  CC-BY-SA-4.0-lisenssi, attribuutio, tietolähteet ja pois jätetyt suuret,
  Jieba- ja ei-tuetut listat on dokumentoitu paketissa.

- **Yleisiä lausesanoja peitetään harvemmin virheellisesti.** Paikallinen
  taajuussanakirja toimii lisävastatarkistuksena, kun nimentunnistus pitää
  verbiä, pronominia, artikkelia tai prepositiota henkilönä. Sanakirja ei
  koskaan päätä yksin: pääsanat, moniosaiset nimet sekä kentissä, listoissa
  ja puhuttelun jälkeen olevat nimet pysyvät suojattuina. Kiina, japani ja
  korea käyttävät yksinomaan jo olemassa olevien kielimalliensa tarkkoja
  tokenirajoja; puuttuville kielille ei oteta käyttöön oletettavasti
  samankaltaista sanakirjakieltä. Tähän ei lähetetä asiakirjatekstiä
  internetiin.

- **Teknisiä tuote- ja varustetermejä ei enää pidetä niin herkästi niminä tai
  paikkoina.** Paikallinen vastatarkistus yhdistää nyt taajuuden, sanaluokan,
  teknisen sananmuodostuksen ja asiasanakentät. Näin esimerkiksi „Travel-
  Assistent“, „Family-Bonus“, „WLTP-Wert“, „Easy-Start“ ja yhdistetyt
  numero-, haltija- tai jarrutermit jäävät asiakirjaan. Englanninkieliset
  osat haetaan paikallisesti myös saksankielisessä asiatekstissä; todelliset
  erisnimet, puhuttelut sekä henkilö- ja paikkakentät säilyttävät
  etusijansa. Lisäksi „2-jährige Herstellergarantie“ ei enää lasketa iäksi.

- **Qt-/PySide-lisenssioikeudet ovat nyt kokonaan jäljitettävissä.**
  Ohjelmapaketti sisältää lisäksi GPL-3.0-kokonaistekstin, tarkat
  Qt-versiot, lähdekooditarjouksen ja saksan-/englanninkielisen ohjeen
  dynaamisten kirjastojen vaihtamiseen mukaan lukien paikallinen macOS-
  uudelleenallekirjoitus. Myyntiin tarkoitettu rakennus estetään, kunnes
  toimitetun version täsmälliset lähdearkistot ovat saatavilla omalla
  lähdekoodisivulla.

- **Lisenssi ja päivitystilanne kertovat nyt jokaiselle tasolle
  yksiselitteisesti, mikä on voimassa.** Lisenssi-ikkunassa ja
  päivitysasetuksissa lukee, sisältyvätkö päivitykset, mihin päivään asti ne
  ulottuvat ja pysyykö käynnissä oleva versio pysyvästi käytettävissä.
  Yksityislisenssit eivät enää asenna määräpäivän jälkeen myöhemmin
  julkaistua versiota; myös vasta ladattu asennusohjelma tunnistaa kiinteästi
  sisäänrakennetusta julkaisupäivästään, kattaako syötetty avain sen.
  Viimeinen kattamaan jäänyt yksityisversio pysyy pysyvästi käytettävissä.
  Jos sen sijaan yritystilaus päättyy, käyttö ja päivitykset päättyvät;
  koejakso ja ilmaistaso eivät avaudu kiertotienä.

- **Yksityiset pysyväislisenssit löytävät nyt myös uudelleenasennuksen
  jälkeen oikean ohjelmaversion.** Allekirjoitettu versioluettelo listaa
  kaikki vakaat versiot ja niiden paketit. Jos ostoon kuulunut viimeinen
  asennusohjelma ei ole enää saatavilla, saa sen sijaan automaattisesti
  käyttää juuri seuraavaa korkeampaa saatavilla olevaa vakaata versiota –
  ei koskaan betaa tai nightlyä. Liian uuden asennuksen tapauksessa asiakas
  voi asentaa sallitun version tai siirtyä ostosivulle uutta
  päivitysjaksoa varten; taannoin siirtyminen ei tapahdu äänettömästi. Tämä
  koskee myös hallittuja MSI-asennuksia.

- **Automaattinen kasvojen peittäminen on nyt yksiselitteisesti kuvattu.**
  Ohjelman ohje ja tietosuojateksti kutsuvat toimintoa nimellä „Tunnista ja
  tee tunnistamattomiksi kasvoalueet“ ja erottavat sen tunnistamisesta,
  uudelleentunnistuksesta, kasvovertailusta, biometrisistä malleista ja
  henkilö- tai kasvotietokannoista. Ne myös huomauttavat selvästi, että
  täysin paikallinen tunnistus voi jättää alueita huomaamatta tai merkitä
  ne virheellisesti ja tulos on siksi tarkistettava silmämääräisesti. Myös
  yksittäin puhdistetun kuvatiedoston tuloraportti mainitsee nyt
  tunnistetut ja pikselöidyt kasvoalueet; puuttuvaa tekstintunnistusta ei
  siinä enää kuvata virheellisesti täysin muuttumattomana tiedostona.

## 0.10.36-alpha.20260820 – 20. elokuuta 2026

### Korjattu

- **Anonymisoidut tiedot voidaan nyt palauttaa täydellisesti järjestyksestä
  riippumatta.** Aiempi palautus etsi arvon näkyvien tekstiankkureiden
  avulla. Tiheissä taulukoissa, suoraan vierekkäisissä paikkamerkeissä ja
  näkymättömissä Office-/sähköposti-tallenteissa nämä ankkurit puuttuivat;
  joskus termi tuli palautettavaksi vasta sen jälkeen, kun jokin toinen
  selkokielinen teksti sattumalta loi uuden ankkurin. Nyt tulos ja
  alkuperäinen verrataan kunkin todellisen muotokantajan kohdalla
  täydellisen kohdistuksen avulla, ja kirjoitetaan vain valitun arvon
  todistetut kohdat.

- **Nimet, sähköpostiosoitteet, numerot ja omat tarkistustermit pysyvät
  yksiselitteisesti käytettävissä myös päällekkäisessä tunnistuksessa.** Jos
  sama selkoarvo on liitetty kahteen tyyppiin, ratkaisee löytökohdassa
  todella oleva paikkamerkki yhdessä klikatun sivupalkkirivin kanssa. Ei-
  todistettu arvo/paikkamerkki-pari pysyy edelleen turvallisesti lukittuna.

- **Sähköpostin erikoistapaukset eivät enää jätä piilotettuja
  paikkamerkkejä.** Tämä koskee MIME-koodattuja aiheita, tekstiliitteitä ja
  HTML-merkinnällä erotettuja nimiä EML- ja MSG-tiedostoissa. UTF-8-HTML
  ilman omaa merkistömäärittelyä ei myöskään enää koodaudu Outlook-
  tiedostoissa mojibakeksi jokaisen muokkausvaiheen yhteydessä; vanhemmat,
  jo näin kirjoitetut tulokset pysyvät palautettavissa.

### Parannettu

- **Uusi vapautusmatriisi käsittelee jokaisen anonyymin sivupalkkirivin
  erikseen ja tarkoituksella takaperin.** Se tarkistaa kaikki 14 teksti-,
  Office-, web- ja sähköpostimuotoa sekä PDF:n, sen jälkeen myös kaavat,
  attribuutit, suhteet, kommentit, sähköpostin otsikot, liitteet ja
  sisäiset alitallenteet. Täysi macOS-ajo kattaa nyt 149/149 vihreää
  tarkistusskriptiä.

## 0.10.35-alpha.20260820 – 20. elokuuta 2026

### Parannettu

- **Kielimittaukset vertaavat nyt todella samaa samaan.** Säännöllinen
  mittauskorpus sisältää samat 14 asiakirjatapausta samoilla seitsemällä
  teksti- ja neljällä kuvatehtävällä saksaksi ja englanniksi. Täysi ajo
  toistaa juuri tämän matriisin kaikilla kahdellatoista olemassa olevalla
  korpuskielellä. Lomakkeet, taulukot, keskustelut ja muut vielä
  kokonaan kääntämättömät rakennekoenäytteet säilyvät, mutta ne raportoidaan
  erikseen eikä niitä enää sekoiteta kielikiintiöihin.

- **Täysi ajo kirjoittaa jokaiselle kielelle oman mittausraportin.** Ilman
  kielikytkintä tarkistetaan tarkoituksella saksa ja englanti;
  `--alle-sprachen` vaatii täydellisen kahdentoista kielen korpuksen ja
  keskeytyy ennen ensimmäistä asiakirjaa, jos kieli tai tapaus puuttuu.
  Samannimiset tulokset sijaitsevat erillisissä kielikansioissa.
  Kokonaisraportti ilmoittaa painotetun löytöosuuden lisäksi myös
  kielikiintiöiden painottamattoman keskiarvon.

- **Avoin kielivertailu näyttää nyt myös todellisen rajansa.** Säännöllisessä
  ajossa tekstintunnistuksen kanssa saksa ja englanti poistavat 218/218
  tunnettua tietoa ilman virhehälytystä. Täysi testi tekstintunnistuksen ja
  korkean tason kanssa poistaa 1 255/1 308 tietoa 17 virhehälytyksellä;
  yksitoista kieltä saavuttaa 100 prosenttia, hindi 51 prosenttia.
  Aiemmat täydet osuudet perustuivat epäyhtenäisiin asiakirja- ja
  tavoitemääriin eivätkä ole vertailukelpoisia uuden matriisin kanssa.

## 0.10.34-alpha.20260819 – 19. elokuuta 2026

### Korjattu

- **Useasti esiintyvät nimet pysyvät yksittäisen palautuksen jälkeen
  tavoitettavissa sivupalkissa.** Aiemmin koko nimirivi katosi jo
  ensimmäisen palautetun `[NAME]`-kohdan jälkeen. Saman nimen muut kohdat
  jäivät siksi paikkamerkiksi ja saattoivat jopa väliaikaisesti estyä,
  kunnes muut nimet oli palautettu. Nyt rivi katoaa vasta viimeisen kohdan
  jälkeen; jo palautettua selkokielistä tekstiä ei silti anonymisoida
  automaattisesti uudelleen. Sama koskee osittain onnistunutta
  joukkopalautusta ja PDF:ien kehystyökalua.

- **„Peru korvaus” toimii myös Office-sivunäkymästä.** Näkyvä sivu on siellä
  vain ohimenevä PDF-esikatselu; nyt muutetaan oikein alla oleva Word-,
  taulukko- tai esitysasiakirja ja päivitetään sen jälkeen esikatselu.

- **Palautus hakee nyt myös arvon piilotetut vastineet kokonaan takaisin.**
  Word-, OpenDocument-, Excel- ja PowerPoint-tiedostoissa samat tiedot
  voivat lisäksi sijaita kaavoissa, kommenteissa, kaavioissa, kenttäarvoissa,
  vaihtoehtoisissa teksteissä ja viittauskohteissa; HTML, EML ja MSG
  kuljettavat niitä lisäksi attribuuteissa, JSON:ssa, viestin otsikoissa ja
  liitteissä. Aiemmin muodosta riippuen osa jäi paikkamerkiksi. Nyt jokainen
  osumaeriteltyalueella tarjottu tieto voidaan palauttaa itsenäisesti ja
  missä tahansa järjestyksessä. Tarkoituksella poistetut metatiedot,
  muutoshistoriat ja siirto-otsikot pysyvät turvallisuussyistä edelleen
  poistettuina.

- **Kuvista palautettaessa ei jää enää mustaa reunaviivaa.** Kehyksen oikea
  ja alareuna laskettiin alkuperäisestä kopioitaessa yhden kuvapisteen
  liian ahtaaksi. Koordinaatit vastaavat nyt peittoa.

### Parannettu

- **Vapautustarkistus lähettää nyt jokaisen tuetun 22 tiedostopäätteen
  täydelle kierrokselle.** Sisällöltään rikkaat tiedostot puhdistetaan,
  kaikki tarjotut arvot palautetaan ja tarkistetaan sen jälkeen syvällisesti.
  Lisäksi mukana on todellinen sivupalkin käyttö, pikselintarkat
  kuvavertailut ja näkyvä LibreOffice-renderöinti kaikista seitsemästä
  toimistomuodosta. Pienet regressiotestit säilyvät siellä, missä ne
  kattavat oman virhe- tai turvallisuustapauksen; todistetusti kaksinkertainen
  HTML-tarkistus ja poistetun mustavalkotilan testi on jätetty pois.

- **Tämän version täydellinen mittauskorpus on saatavilla
  jälkimittausta varten.** Paketti sisältää 294 synteettistä asiakirjaa
  kahdessatoista muodossa ja kahdellatoista kielellä, 2 564 tunnettua
  tietoa, neljä konelluettavaa tavoiteluetteloa ja ohjeet. Laatusivun lataus
  käyttää sisällöstä riippuvaa tiedostonimeä, jotta selaimet eivät
  vahingossa toimita vanhempaa versiota välimuistista.

## 0.10.33-alpha.20260819 – 19. elokuuta 2026

### Uutta

- **Myös kuvatiedostoissa yksittäiset kohdat voidaan nyt palauttaa
  alkuperäisestä.** Kehystyökalu „Palauta alkuperäinen” kopioi kuvapisteet
  samasta kohdasta takaisin koskemattomasta lähdetiedostosta. Toiminto pysyy
  lukittuna, jos lähde puuttuu tai sillä on eri kuvamitat; näin sisältöä ei
  voida asettaa siirretystä kohdasta.

### Parannettu

- **Manuaaliset peittopalkit lukittuvat oletuksena tekstiriveihin.** Useamman
  rivin yli vedettäessä syntyy jokaiselle riville tasakorkuinen palkki, ja
  niiden väliin jäävä tyhjä tila säilyy. Allekirjoituksia, kuvia ja muita
  erikoistapauksia varten „Vapaa kehys” palauttaa itse valittavan korkeuden.

- **Editori selittää seuraavan käsittelyvaiheen suoraan asiakirjan
  yläpuolella.** Ohje vaihtuu asiakirjatyypin ja työkalun mukaan ja
  kertoo, odotetaanko sanan napsautusta, tekstin valintaa vai kehystä.
  Lisäksi työkalu, hiiren osoitin ja live-esikatselu näyttävät jo ennen
  irrottamista, mitä tapahtuu.

### Poistettu

- **Virhealtis mustavalkotuloste poistettiin.** Joissakin PDF-tiedostoissa
  näkymättömät tekstikentät jäivät siirtyneiksi rasteroituun sivuun nähden;
  näennäinen tiedoston pienentyminen ei ollut tämän turvallisuus- ja
  esitysriskin arvoinen. Tavallinen PDF-puhdistus ja ongelmallisten sivujen
  kohdennettu rasterointi säilyvät.

## 0.10.32-alpha.20260819 – 19. elokuuta 2026

### Uutta

- **Kansionvalvonta toimii nyt todella taustalla.** Saapuva, lähtevä ja
  säännöt löytyvät omalta sivultaan kohdasta „Asetukset“. Se käynnistetään
  ja pysäytetään Maskuro-kuvakkeesta tehtävä- tai valikkorivillä; merkintä
  näkyy vain tähän vapautetulla lisenssillä. Asetusikkuna voidaan sen
  jälkeen sulkea ja pääikkuna pienentää kuvakkeeksi ilman, että valvonta
  päättyy.

- **Jälkikäsittely-editorissa on nyt pysyvä oppimistilan kytkin.** Se
  sijaitsee osumaeriteltyalueella ja valikossa „Työkalut“. Kun se
  kytketään pois päältä, ei palauttamisen eikä käsin tehtyjen korjausten
  yhteydessä enää kysytä omien sääntöjen luomisesta. Maskuro muistaa
  valinnan kaikkiin tulevaisuudessa avattaviin asiakirjoihin; itse
  peruminen toimii ennallaan.

### Korjattu

- **Suuri lisämalli voidaan ladata jälleen.** Julkinen tallennustila
  hylkäsi Pythonin yleisen oletustunnisteen koodilla 403. Mallien haku
  käyttää nyt samaa nimettyä Maskuro-verkkoreittiä kuin muut omat
  palvelut; noin 596 Mt:n tiedosto ja sen tarkiste pysyvät ennallaan.

- **Suurennettu vertailusuurennuslasi ei enää jää telakoinnissa kapeaksi
  palkiksi yläreunaan.** Ennen telakointia sen vapaa ikkunatila
  normalisoidaan. Tallennettu suurennettu tila palautetaan seuraavalla
  avauskerralla myös muutettavaan kokoon.

- **Joukkopalautus hakee taulukoissa ja muissa tekstimuodoissa nyt todella
  kaikki valitut arvot takaisin.** Anonymisoiduissa paikkamerkeissä kuten
  `[EMAIL]` Maskuro kirjoitti arvot aiemmin peräkkäin. Heti kun ensimmäinen
  oli korvattu, kaikkien jäljellä olevien löytökohtien numerot siirtyivät,
  mutta jo laskettu suunnitelma osoitti edelleen vanhoihin numeroihin.
  Tämän vuoksi vain osa valinnasta palautui. Nyt kaikki saman
  paikkamerkin valitut arvot kirjoitetaan yhdessä ja vakailla
  löytökohtanumeroilla. Jos kohta tulee yksiselitteiseksi vasta toisen
  palautetun arvon myötä, Maskuro tarkistaa sen samalla kierroksella
  uudelleen – valinnan järjestyksellä ei siten ole enää merkitystä.

- **„Peru korvaus” ei enää jätä PDF:issä valittuja arvoja väliin.** Jos
  paikkamerkki oli hyvin lähellä toista sanaa tai jos alkuperäisessä oli
  pilkku aivan arvon vieressä, sijaintitarkistus saattoi virheellisesti
  laskea naapurisanan tai välimerkin kuuluvaksi arvoon. Yhteispalautuksessa
  yksittäiset paikkamerkit ja osumarivit saattoivat siksi jäädä paikoilleen.
  Tarkistus perustuu nyt todelliseen sanan alkuun ja ottaa huomioon myös
  alkuperäisen ja tuloksen välisen poikkeavan sivun kierron.

- **Palautettu PDF-teksti säilyttää nyt alkuperäisen kokonsa.** Aiemmin
  mittana toimi jo pienemmäksi asetettu paikkamerkki; lisäksi myös
  alkuperäiseen tekstiin sovellettiin paikkamerkeille tarkoitettua 11
  pisteen ylärajaa. Nyt alkuperäinen laatikko ja alkuperäinen
  kirjasinkoko otetaan lähdetiedostosta – sekä kehystyökalussa että
  osumapaneelista palautettaessa.

### Parannettu

- **Tarkistushuomautus nimeää jäännösriskin nyt selvemmin.** Se sanoo
  nimenomaisesti, että Maskuro voi jättää tietoja huomaamatta tai käsitellä
  tietoja väärin, ja kehottaa ennen jokaista julkaisua tai luovutusta
  täydelliseen tarkistukseen ja tarvittaessa käsin tehtävään korjaukseen.
  Tämä koskee myös leikepöydältä tulevaa tekstiä ja on viety täydellisesti
  läpi kaikissa 17 käännöksessä.

- **Tarkistuspöytäkirja käynnistyy nyt myös rivien sisällä ilman
  käyttäjänimeä.** Itse pöytäkirja pysyy pois päältä, kunnes yritys
  aktivoi sen tarkoituksella. Sen jälkeen ilman lisäasetusta ei rivillä
  eikä keskitetyn kuukausitiedoston nimessä ole käyttäjänimeä; siellä
  turvallisen erottelun huolehtii arvaamaton, vain satunnaisesta
  paikallisesta profiilisalaisuudesta johdettu salanimi. Lisenssi-ikkuna
  ei enää suosittele aktivointia, edellyttää „Ilman pöytäkirjaa” -tilaa ja
  huomauttaa etukäteen työsuojeluvaltuutetusta, henkilöstöedustuksesta ja
  tietosuojasta.

- **Korvaaminen nimeää nyt, mitä se korvaa.** Merkitystä nimestä tulee
  `[NAME_3]`, paikasta `[ORT_1]`, puhelinnumerosta `[TELEFON_2]` – sen
  sijaan, että kaikesta tulisi kuten ennen `[BEGRIFF_n]`. Laji tunnistetaan
  klikattaessa; jos se ei ole yksiselitteinen – tavallinen sana, tai nimi
  *ja* paikka samassa valinnassa –, jää yleiseksi termiksi. Paikkamerkki,
  joka väittää lajin, joka ei pidä paikkaansa, olisi huonompi kuin
  sellainen, joka ei nimeä mitään.

- **Jälkikäsittely-ikkunan työkaluilla on nyt pikanäppäin.** **S** peittää,
  **E** korvaa, **Z** palauttaa alkuperäisen, **V** pikselöi.
  Tekstinäkymässä ne vaikuttavat heti valintaan, sivunäkymässä ne
  valitsevat työkalun. **Kirjaimet noudattavat kieltä**, jolla ohjelmaa
  käytät – englanniksi B/R/O/P, italiaksi O/S/R/P –, koska muistisääntö
  auttaa vain omalla kielellä. Näppäin näkyy painikkeessa.
  Hakupalkkiin parhaillaan kirjoittava kirjoittaa kirjaimia edelleen –
  siellä ne eivät vaikuta.

- **Ohjelma ilmoittaa kerran päivässä, missä tilassa se toimii – ilman
  mitään tunnistetta.** Näin lasketaan, kuinka monta asennusta on
  käytössä ja miten se jakautuu koejaksoon, ilmaistasoon ja lisenssiin.
  Lähtevät tiedot ovat tila, käyttöjärjestelmä, versio, kanava, maa,
  kieli, ympäristö ja tunnistustaso – **ei mitään asiakirjoistasi eikä
  mitään, josta koneesi voitaisiin tunnistaa uudelleen**. Kaksi ilmoitusta
  sinulta näyttävät meille kahdelta eri ihmiseltä tulevilta ilmoituksilta;
  yksittäistä polkua ei niistä voi jäljittää. Mitä täsmälleen lähetetään
  ja miten sen voi kytkeä pois päältä, kerrotaan tietosuojatekstin
  kohdassa 5.

- **Vinosti skannatut sivut kääntyvät nyt itsestään oikein päin.** Vinoon
  skannatun arkin, jota ei ole merkitty sellaiseksi, jälkikäsittely
  tunnistaa tekstin kulusta ja oikaisee näkymän. Missä se ei onnistu –
  puhtaassa skannauksessa ilman luettavaa tekstiä –, kaksi uutta
  merkintää valikossa „Näkymä” kääntää käsin (Ctrl+Vaihto+L ja
  Ctrl+Vaihto+R). Käännetään vain näyttö: itse tiedostoon ei siinä
  muutu mikään, ja peittäminen osuu edelleen juuri siihen kohtaan, jota
  klikataan.

- **Paikallinen jakelu kuljettaa nyt lisenssinsä täydellisesti ja
  näkyvästi mukanaan.** Rakennus selvittää todella mukaan paketoidut
  Python-paketit, tallentaa niiden lisenssitekstit versiokatsauksen
  kanssa kansioon `lizenzen` ja keskeytyy, jos jotain puuttuu. Myös Qt,
  Tesseract ja kasvomalli sisältävät tarvittavat tekstinsä; itse Maskuron
  ehdot ovat mukana lisenssisopimuksena.

- **Nyt näkee, missä paikkamerkissä kirjoitusmerkki on.** Paikkamerkkiin
  klikkaava näkee sen syttyvän kokonaan – hakasulkeineen ja numeroineen.
  Painike „Palauta valinta” aktivoitui jo aiemmin pelkällä klikkauksella;
  vain ei näkynyt, minkä merkin se osui. Valo pysyy näkyvissä myös silloin,
  kun hiiri siirtyy painikkeeseen.

- **Hiiren osoitin kertoo nyt, mikä työkalu on valittuna.** Neljä työkalua
  jakaa saman alueen ja saman eleen; tähän asti kaikki näyttivät samalta.
  Ristikko tarkoittaa peittämistä, suljettu käsi korvaamista, avoin käsi
  palauttamista.

- **Väärennetty Office-asiakirja torjutaan nyt ohjelman itsensä toimesta.**
  Word-, Excel- tai OpenDocument-tiedosto voi sisältää käskyjä, jotka
  avattaessa hakevat koneesi vieraan tiedoston sen tekstiin tai täyttävät
  muistin loppuun. Kumpikin torjuttiin jo aiemminkin – mutta sisäänrakennetun
  XML-kirjaston toimesta, ei Maskuron. Nyt ohjelma päättää sen itse,
  riippumatta siitä, mikä tämän kirjaston versio paketissa on. Tavallisille
  asiakirjoille mikään ei muutu.

### Korjattu

- **Osumapaneeli poistaa nyt peitetyt paikkamerkit.** Jos esimerkiksi
  `[NAME_1]` peitettiin jälkikäsittely-ikkunassa, sen arvorivi jäi
  aiemmin oikealle näkyviin, vaikka asiakirjassa ei enää ollut vastaavaa
  kohtaa. Rivi katoaa nyt viimeisen löytökohdan mukana; jos sama
  paikkamerkki esiintyy vielä muualla, se säilyy.

- **Palautettaessa käännetyllä sivulla naapurisana jää nyt paikoilleen.**
  Peittopalkki ulottuu tarkoituksella hieman tekstin yli; jo tämä kapea
  reuna saattoi aiemmin viedä mukanaan vierekkäisen sanan kuten „im”. Nyt
  merkitsee vain selvä päällekkäisyys, ei kosketus reunalla.

- **Toinen korvaus samalla rivillä vei mukanaan jälkilauseen.** „Sachbearbeitung
  Quaxi Blubbo übernimmt” kahdesti peräkkäin korvattaessa syntyi
  „Sachbearbeitung [ORT_1] [ORT_2]” – sen jälkeinen sana katosi
  korvauksetta, ilman mitään ilmoitusta. Syynä oli viereinen
  paikkamerkki: rivin loppuosa alkaa ensimmäisen korvauksen jälkeen
  välilyönnillä, ja tekstikohdan haku tarttui naapurin sulkevaan
  hakasulkeeseen. Sen jälkeen kaikki oli siirtynyt yhdellä merkillä.
  Tämä koski jokaista riviä, jolla korvattiin tai peitettiin kahdesti –
  myös vieressä palautettaessa.

- **Korvaaminen ei enää peitä mustalla, kun paikkamerkki on liian pitkä.**
  Jos sanan vieressä ei ollut tilaa merkinnälle `[BEGRIFF_2]`, alue
  maalattiin aiemmin mustaksi – jolloin ei myöskään enää näkynyt, että
  siinä oli aiemmin jotain, saati sitten voinut palauttaa sen. Nyt
  kirjoitetaan lyhyempi merkintä: `[BEGR_2]`, `[BE_2]`, tarvittaessa
  `[B_2]`. Juokseva numero säilyy jokaisella tasolla – siitä palautus
  löytää kohdan uudelleen. Vain siellä, missä lyhyinkään ei mahdu, jää
  käytettäväksi palkki.

- **Korvaaminen jätti tekstin paikoilleen, jos samalla rivillä oli jo
  peitetty.** Jos jälkikäsittely-ikkunassa palautettiin nimi
  alkuperäisestä, korvattiin siitä etunimi (siellä ei ollut tilaa – siitä
  tuli palkki) ja sen jälkeen korvattiin sukunimi, syntyi paikkamerkki,
  mutta nimeä **ei poistettu**. Tämä huomattiin vain jälkikatselun
  varoituksesta. Syynä oli rivi itse: ensimmäisen peiton jälkeen sen
  loppuosa alkaa välilyönnillä, eikä tekstikohdan haku löytänyt siitä
  otetta. Tämä koski joka toista peittoa samalla rivillä.

- **Käytössä oleva laajennettu tunnistus ilman sen mallia huomataan nyt.**
  Valintaruutu saattoi olla rastitettu, vaikka malli puuttui – asetukset
  koskevat jokaista asennusta, mutta malli sijaitsee ohjelman vieressä.
  Puhdistus toimi silloin ilman tätä tasoa, ilman mitään mainintaa siitä.
  Nyt valintaruutu kertoo, että malli puuttuu, ja tulos saa varoituksen.
  Kerran tehty valinta pysyy silti tallessa: heti kun malli on ladattu, se
  vaikuttaa taas.

- **Anonymisoitaessa palautetaan nyt oikea termi.** Useita termejä käsin
  korvannut ja niistä yhden myöhemmin palauttanut sai aina **ensimmäisen**
  – „Schmidt”-nimestä tuli „Müller”. Kohdistus muisti kutakin
  paikkamerkkiä kohden vain yhden korvauksen, ja anonymisoitaessa kaikki
  kantavat samaa paikkamerkkiä; toinen ja jokainen sitä seuraava termi
  jäi siksi pois. Nyt jokainen arvo saa oman rivinsä – myös korvausten
  luettelossa, joka oli aiemmin liian lyhyt.

- **Taulukoissa voi nyt myös palauttaa.** CSV-tiedostossa tai
  henkilölistassa paikkamerkit ovat suoraan vierekkäin, erotettuna vain
  puolipisteellä. Tähän asti ohjelma ei voinut siellä todistaa, mikä
  arvo oli ollut missäkin kohdassa, ja hylkäsi pyynnön – `[NAME]`:n
  kanssa se onnistui, `[GEBURTSDATUM]`:n ja `[TELEFON]`:n kanssa ei. Nyt
  se pilkkoo rivin kaikista paikkamerkeistä. Jos jokin kohta jää todella
  monimerkityksiseksi, se hylkää edelleen: väärin takaisin kirjoitettu
  arvo olisi pahempi kuin puuttuva tieto.

- **Ja hylkäys näkyy nyt.** Se oli aiemmin himmeän harmaana ikkunan
  alareunassa, ja lause oli niin pitkä, että se katkesi – näytti siltä,
  ettei mitään tapahtuisi. Lauseet on lyhennetty, ja rivi syttyy
  muutamaksi sekunniksi varoitusväriin.

- **Peruminen pysyy nyt voimassa myös seuraavan toimenpiteen jälkeen.**
  Anonymisoitaessa useita kohtia palauttanut ja sen jälkeen jotain muuta
  korvannut huomasi kaikkien palautettujen kohtien olevan taas
  korvattuina ja joutui aloittamaan alusta. Syynä oli kohdistus: se
  säilytti arvon, ja yhtenäisten paikkamerkkien automaattinen
  täsmäytys palautti sen seuraavalla kirjoituskerralla. Nyt pätee: mitä
  palautat, pysyy palautettuna – tämä ei koske saman arvon muita kohtia.

- **Teksti-, Word-, Excel- ja sähköpostitiedostoissa yksi klikkaus
  paikkamerkkiin riittää nyt todella.** Ilmoitus tästä oli jo edellisessä
  versiossa, mutta painike „Palauta valinta” pysyi lukittuna, kunnes
  jotain oli tarkasti merkitty – tielle, joka olisi itse asettanut
  valinnan, ei siis edes päästy.

### Korjattu

- **Tarkistuspöytäkirja ei enää paljasta tiedostonimeä.** Se kirjaa
  tiedostot tarkoituksella tarkistesummana selkotekstin sijaan, koska
  tiedostonimi paljastaa toimeksiantajan ja riidan kohteen. Tämä
  tarkistesumma pystyttiin kuitenkin vahvistamaan arvaamalla – polku ei
  ole satunnaisluku. Nyt laskentaan otetaan mukaan tämän asennuksen
  satunnaisarvo: laskeminen ja erottelu pöytäkirjassa toimivat edelleen,
  ulkopuolinen jälkilaskenta ei enää.

## 0.10.31-alpha.20260819 – 19. elokuuta 2026

### Parannettu

- **Myös teksti- ja taulukkotiedostoissa paikkamerkki syttyy punaisena
  osoitettaessa.** Aiemmin punainen esikatselu oli vain PDF-sivulla. Nyt
  molemmat näkymät näyttävät saman: mikä on punaista, siihen seuraava veto
  osuu – ja klikkaus sen sisään riittää palauttamiseen.

- **Yksi klikkaus sanaan riittää – suorakulmion asettaa editori itse.**
  Jälkikäsittely-ikkunassa piti aiemmin vetää suorakulmio jokaisen kohdan
  ylle. Nyt riittää klikkaus: kehys asettuu sanan ympärille ja pysyy
  tavoitettavissa, eli sitä voi edelleen laajentaa tai siirtää. Hiirellä
  osoitettaessa sana syttyy jo punaisena, joten näkee etukäteen, mihin
  klikkaus osuisi. Missä ei ole sanaa, vedetään kehys kuten ennenkin.

- **Suorakulmiolla ei enää tarvitse tähdätä tarkasti.** Suorakulmion
  paikkamerkin tai peiton ylle vetävä tarkoittaa aina koko kohtaa – ei
  koskaan sen puolikasta. Kehys kasvaa siksi itsestään koko kokonaisuuteen,
  jota se koskettaa: koko paikkamerkkiin, koko palkkiin tai, skannatulla
  arkilla, koko peitettyyn alueeseen. Vedettyä kehystä pienemmäksi se ei
  koskaan tule.

- **Peittäminen tapahtuu nyt sanoittain.** Sanan puolikkaan ylle ulottuva
  kehys peitti aiemmin vain puolikkaan – ja puoliksi peitetty nimi on
  edelleen nimi. Kosketetut sanat poistuvat nyt kokonaan; naapuri pysyy
  koskemattomana.

- **Tekstissä ja taulukoissa riittää klikkaus paikkamerkkiin.** „Palauta
  valinta” vaati aiemmin, että paikkamerkki hakasulkeineen merkitään
  tarkasti. Nyt riittää, että osoitin asetetaan sen sisään; valinta hyppää
  näkyvästi koko paikkamerkkiin.

- **Belgia on lisätty maaksi.** Valittavissa asetuksissa; sen jälkeen
  tunnistetaan belgialaiset puhelinnumerot, Rijksregisternummer
  (tarkistusnumerolla), BTW-/yritysnumero (tarkistusnumerolla), osoitteet
  molemmilla virallisilla kielillä sekä postinumero paikkakunnan kanssa.
  Aiemmin belgialaiset puhelinnumerot jäivät paikoilleen, koska maa ei
  ollut lainkaan luettelossa.

- **Päivityskanava kertoo nyt, kuinka aikaisin saat uutta – ei, kuinka
  pitkälle.** „Testiversio”-kanavalla ollut ei saanut uutta esikatselua tai
  uutta vakaata versiota lainkaan tarjolle ja joutui vaihtamaan kanavaa
  käsin edes saadakseen tietää siitä. Nyt tarjotaan myös kaikki, mikä on
  luotettavampaa: testiversio ottaa testiversiot, esikatselut ja vakaat
  versiot, esikatselu ottaa esikatselut ja vakaat. Ei koskaan toisin päin –
  esikatselukanavalla ei tarjota testiversiota, vaikka se olisi uudempi.

- **Asetusikkunassa rivit ovat nyt kauempana toisistaan.** Neljä sivua
  käytti omia välejä sen sijaan, että olisi noudattanut ohjelman muualla
  pätevää ruudukkoa; erityisesti sivulla „Tunnistus” valintaruudut olivat
  siksi tuntuvasti liian tiheässä.

### Korjattu

- **Täytetyt PDF-lomakkeet eivät enää näy tyhjinä käsin muokattaessa.**
  Maskuro muuttaa tätä varten vain ohimenevän työkopion staattisiksi
  sivuiksi: syötetyt arvot tulevat näkyviin ja voidaan todella peittää;
  luettavat lomakekentät eivät jää piiloon tiedostoon. Alkuperäinen pysyy
  interaktiivisena ja muuttumattomana. Tämä koskee nyt myös dynaamisia
  XFA-lomakkeita: XFA-kykyinen PDFium rakentaa ensin arvot ja
  sivunvaihdot, minkä jälkeen syntyy uusi PDF pelkästään staattisista
  kuvasivuista. Jos XFA-rakennus epäonnistuu, tiedosto hylätään
  turvallisesti sen sijaan, että se avautuisi näennäisen tyhjänä.

- **„Peruuta” toimii nyt myös tarkemman tunnistuksen aikana.** Aiemmin
  painike lukittui klikattaessa, mutta ajo laski silti loppuun viimeiseen
  lohkoon asti – pitkässä tiedostossa siihen menee minuutteja ilman
  ulospääsyä, ja painike näytti sillä aikaa siltä, että se olisi vaikuttanut.
  Nyt ajo päättyy seuraavaan lohkoon.

- **CSV-tiedostoissa nimet löytyvät nyt myös silloin, kun niiden edessä ei
  ole välilyöntiä.** Merkinnässä `P-1000;Brunnthaler, Elisabeth`
  henkilönumero liimautuu puolipisteen yli nimeen kiinni, ja tunnistuksen
  kannalta se oli yksi sana ilman nimeä sisällään – henkilölistoissa koko
  nimi jäi siksi paikoilleen riveittäin vaihdellen. Puhelinnumerot, kaavat
  ja tiedoston sarakemäärä pysyvät tästä koskemattomina.

- **Nimi, jonka sekä etu- että sukunimessä on väliviiva, tunnistetaan nyt.**
  „Marie-Luise Habsburg-Ott” jäi lauseen keskelle paikoilleen, kun taas
  „Dragan Mitrović” löytyi samassa lauseessa – juuri kahden yhdistetyn
  puolikkaan yhdistelmän kielimalli jätti huomaamatta. Yhdistetyt
  asiasanat kuten „Nord-Süd-Verbindung” tai „Software-Entwickler” pysyvät
  tästä koskemattomina.

## 0.10.30-beta.1 – 18. elokuuta 2026

### Parannettu

- **Tekstinäkymän kirjasinkoko on nyt näkyvästi säädettävissä.** Oikeassa
  alakulmassa oleva säädin, joka aiemmin zoomasi vain sivunäkymässä,
  säätää jälkikäsittely-ikkunassa teksti- ja Office-tiedostoissa
  kirjasinkokoa (50–300 %) – samoin „Suurenna”/„Pienennä” Näkymä-valikossa.
  Ctrl+hiiren rulla toimi näin jo aiemminkin, mutta sen tiesi vain se, joka
  oli kokeillut sitä; nyt säädin, näyttö ja rulla toimivat yhdessä.

- **Tummassa ulkoasussa on nyt valkoinen paperi tummalla työtasolla.**
  Aiemmin se oli toisin päin: paperin ympärillä pysyi vaalea alue, ja itse
  teksti oli vaaleaa tummalla pohjalla. Nyt paperi pysyy molemmissa
  ulkoasuissa paperinvalkoisena ja mustatekstisenä – kuten PDF-sivu, joka
  ei muutu tummaksi tummassa tilassakaan – ja sen ympärillä oleva alue on
  tumma.

### Korjattu

- **Lauseen keskellä olevan peiton jälkeen lauseen loppu ei enää katoa.**
  Sama kohta kolmesti jälkikäsittely-ikkunassa käsitellyt – korvattu,
  peitetty, sitten „Palauta alkuperäinen” – sai lauseen alun poistetuksi:
  „Rückfragen richten Sie bitte an das Rechnungswesen.” muuttui muotoon
  „bitte an das Rechnungswesen.”, ilman varoitusta. Tämä koski jokaista
  kohtaa, josta oli jo kerran poistettu jotain kesken rivin.

- **Käynnistysvirhe ei enää vedä lopettamista mukanaan.** Kun pääikkunan
  rakentaminen keskeytyi, kaatui sen jälkeen myös tehtäväpalkin kuvakkeen
  kautta lopettaminen – ja tämä toinen virhe peitti virheraportissa
  todellisen syyn. Nyt ohjelma lopettaa siististi myös puolittain
  rakennetusta ikkunasta, ja tallennetut asetukset pysyvät koskemattomina.

- **„Ennen/jälkeen” ei enää hyppää asiakirjan alkuun.** Jälkikäsittely-
  ikkunassa alaspäin vierittänyt ja vertailua varten alkuperäiseen
  vaihtanut päätyi jälleen aivan ylös – ja joutui etsimään kohdan käsin
  uudelleen. Näkymä pysyy nyt samalla rivillä molempiin suuntiin
  vaihdettaessa.

- **Peitettäessä tasapalstan riveillä viimeinen kirjain jäi näkyviin.**
  Kun tekstikäsky piirtää enemmän glyyfejä kuin lukukirjasto ilmoittaa
  merkkejä – se nielaisee tasapalstassa mielellään välilyönnin –,
  kohdistus siirtyi yhdellä, ja lauseesta „Dr. Michael Handler aus
  Willendorf” tuli „[NAME] r aus f”: kaksi jäljelle jäänyttä kirjainta
  keskellä puhdistettua lausetta (löytyi todellisesta
  kunnanvaltuuston pöytäkirjasta). Kohdistus tarkistetaan nyt itse
  käskyn sanamuodosta, missä se on luettavissa – siellä ei enää arvata.

- **„Lerchenfelder Gürtel 43/12” poistettiin vain puoliksi.** Osoitemallit
  eivät tunteneet Gürtel-, Kai-, Lände-, Zeile-, Markt- eikä Graben-sanoja
  kadun perussanana, eikä talonnumero saanut sisältää kauttaviivalla
  jaettuja osia (43/12, talo/ovi) – numero jäi paikkamerkin viereen.
  Molemmat on täydennetty; wieniläiset ja salzburgilaiset osoitteet
  poistuvat nyt kokonaan.

- **Tallennetut verkkosivut pysyvät puhdistuksen jälkeen käyttökelpoisina.**
  Osoitteet, jotka viivästetty lataus tallentaa data-attribuutteihin
  (`data-lazy-src`, `data-lazy-srcset`), korvattiin viittauksina – oikealla
  kunnansivulla kuusitoista kappaletta – eivätkä sivun kuvat sen jälkeen
  enää latautuneet. Verkko-osoitteet jäävät nyt paikoilleen, kuten
  attribuuteissa `src` ja `href` muutenkin; nimet, sähköpostiosoitteet ja
  puhelinnumerot data-attribuuteissa korvataan edelleen.

- **Japanin- ja koreankieliset asiakirjat käsiteltiin kiinana.**
  Kielentunnistus heitti kaikki kolme kirjoitusjärjestelmää samaan
  muottiin, ei löytänyt funktiosanoja japaninkielisestä tekstistä (ilman
  välilyöntejä) eikä koreankielisestä (liitepartikkeleilla) – ja otti
  sitten yksinkertaisesti luettelon ensimmäisen CJK-kielen. Japanilainen
  kunnanvaltuuston pöytäkirja ja korealainen kokouspöytäkirja luettiin
  näin kiinalaisella mallilla. Nyt kirjoitusasu ratkaisee itse: kana
  tarkoittaa japania, hangul koreaa.

- **Lisää virheosumia kenttätestistä kymmenessä muussa kielessä:**
  virat kuten „Primar”, „Gradonačelnik”, „Ordfører”, „Başkanı” tai
  „Δήμαρχος” eivät enää kelpaa henkilönnimiksi; turkkilaiset kenttäotsikot
  („Adı”, „Soyadı”) ja kreikkalaiset keskustelusanat („Ωραία”, „Βεβαίως”)
  eivät enää poistu; päätös- ja pykälänumerot päivämäärän kanssa
  („323/25-6-2008”, „27 30.09.2024”) eivät enää ole puhelinnumeroita; ja
  lauseenkatkelmat pisteen kanssa („10.An”, „T.U.EE”, „…pa”) ei enää
  korvata verkko-osoitteina.

### Uutta

- **Tarkistusraportit pyydettäessä automaattisesti.** Valintaruutu
  asetuksissa (sivu „Ohjelma”) tallentaa jokaisen puhdistuksen jälkeen
  itsestään tarkistusraportin PDF:n – aikaleimalla nimessä, omaan
  kansioon, ei koskaan tuloksen viereen. Jälkikäteen lehteä ei voi
  luoda; sitä arkistoon tarvitseva saa sen siten aina. Oletuksena
  tallennus on pois päältä.

- **Tarkistuspöytäkirja voidaan nyt kytkeä päälle ohjelmassa.** Yrityksen
  lisenssiä luettaessa Maskuro kysyy kerran, pidetäänkö pöytäkirjaa –
  todiste kantaa vain, jos se on käynnissä alusta lähtien. Tähän on kytkin
  asetuksissa (sivu „Ohjelma”, näkyvissä yrityslisenssillä tai
  koejaksolla); ylläpidon asetustiedosto pätee edelleen ja voi pakottaa
  arvon kuten ennenkin. Oma pöytäkirjarivi „kytketty päälle” kirjaa,
  mistä lähtien kirjaaminen on käynnissä – näin myös tallennuksen alku on
  todistettu ja allekirjoitettu. Oletuksena pöytäkirja pysyy pois päältä.

- **Tunnuslukujen osio näyttää, mitä tekoälytaso teki.** Uusi rivi
  ilmoittaa, kuinka monta epävarmaa osumaa malli arvioi, säilytti ja
  hylkäsi ja kuinka monta se lisäksi löysi – aiemmin sen työ oli
  näkymätöntä, ellei jokaista arvoa klikannut jälkikäsittely-editorissa.
  Vain lukuja, ei koskaan arvoja tai perusteluja; ilman tekoälytyötä rivi
  ei näy.

- **Palauttaminen toimii nyt myös sähköposteissa ja HTML-sivuilla.**
  Tiedostoissa `.eml`, `.msg` ja tallennetuilla verkkosivuilla
  paikkamerkkiä ei aiemmin voinut perua – sovellus sanoi sen rehellisesti,
  mutta juuri sähköposti on muoto, jossa on eniten henkilötietoja. Nyt
  peruminen toimii siellä samalla tavalla: osumapaneelista, merkityllä
  valinnalla ja myös anonymisoiduilla paikkamerkeillä. Sähköpostin
  näkymätön HTML-haara (se, mitä Outlook todella näyttää) päivittyy
  mukana, jotta näkymä ja viesti kertovat saman asian.

- **Osumapaneeli palauttaa myös anonymisoituja arvoja – arvokohtaisesti.**
  „Peru korvaus” oli anonymisoiduissa tiedostoissa aiemmin lukittu, koska
  „[NAME]” tarkoittaa kaikkia nimiä yhtä aikaa. Nyt palautus tarkistaa
  alkuperäisestä, mikä kohta kuuluu millekin arvolle – PDF:ssä
  löytökohdan koordinaateista, tekstinäkymässä vertaamalla
  alkuperäiseen – ja palauttaa juuri valitun arvon kohdat. Muiden arvojen
  rivit jäävät paikoilleen.

- **Myös anonymisoidut paikkamerkit voidaan palauttaa yksitellen.**
  Anonymisoitaessa saman tyyppiset tiedot ovat samannimisiä – „[NAME]”
  tarkoittaa jokaista henkilöä, ja tähän asti se tarkoitti, ettei yksittäin
  palauttaminen onnistu. Nyt tarkistetaan alkuperäisestä, joka on muutenkin
  tuloksen vieressä: tekstinäkymässä paikkamerkki merkitään ja valitaan
  „Palauta valinta” – takaisin tulee juuri tämä kohta juuri sillä arvolla.
  Jos arvoa ei voida lukea alkuperäisestä kiistattomasti, sovellus sanoo
  niin sen sijaan, että arvaisi. Kohdistustiedostoa ei tällöin edelleenkään
  synny.

- **Jälkikäsittely-ikkuna avautuu nyt puhdistuksen jälkeen itsestään.**
  Mikään työkalu ei löydä kaikkea – siksi tuloksen tarkistava katse kuuluu
  normaalikäyttöön, ei ylimääräiseen klikkaukseen. Sitä ei haluava
  kytkee sen pois asetuksista kohdasta „Tunnistus” („Näytä tulos sen
  jälkeen jälkikäsittely-ikkunassa”).

### Parannettu

- **Maavalinnan oletusarvo on nyt „automaattinen”.** Aiemmin oletuksena
  oli käyttöliittymän kielialue – saksankielisellä koneella myös
  hollanninkieliset tai ranskankieliset asiakirjat puhdistettiin siis vain
  DACH-tunnistimilla, ja osoite kuten „Universiteitslaan 1” jäi paikoilleen
  (löytyi todellisista, julkisista kunnanvaltuuston pöytäkirjoista). Nyt
  maavalinta noudattaa asiakirjan kieltä; asetuksissa kiinteän valinnan
  tehnyt säilyttää sen.

- **Vähemmän virheellisesti peitettyä.** Joukko virheosumia, mitattuna
  tarkistuskorpuksesta ja todellisista kokouspöytäkirjoista kuudella
  kielellä, poistuu: yritysten nimet oikeudellisine muotoineen
  („Musterfirma GmbH”) eivät enää kelpaa henkilöksi tai paikaksi, vaan
  organisaatioksi; tervehdykset ja pelkät puhuttelut („Saygılarımızla”,
  „Buenas tardes”, yksin oleva „Frau”) eivät enää ole nimiä; virat
  („Bürgermeister”, „Sindaco”, „Alcalde”) jäävät paikoilleen; laki- ja
  päätösnumerot („39/2015”) ja tuhaterottimella varustetut summat
  („330.000”) eivät enää ole puhelinnumeroita; lauseen alut kuten
  „Envíame” tai „Estarei” eivät enää putoa nimeksi; tyhjän rivin yli
  ulottuva osuma ei enää lasketa nimeksi. Laskun laskunnumero säilyy
  todistetietona – asiakasnumero ja diaarinumero poistuvat edelleen.

- **Ennen tekoälymallin lataamista kerrotaan nyt, mihin se on hyvä.**
  Jälkilataus-valintaikkuna nimeää mallin tehtävät – epävarmojen osumien
  arviointi, lisänimien löytäminen, sääntöjen ja profiilien
  ehdottaminen – ja sanoo avoimesti, ettei se ole keskusteluavustaja. UKK
  vastaa samaan kysymykseen laajemmin („Mitä tekoälytaso osaa – ja mitä
  ei?”), kaikissa kieliversioissa.

### Korjattu

- **Komentoriviltä tehdyt tarkistusraportti-PDF:t voidaan nyt hakea
  tekstistä.** Windowsissa ikkunaton PDF-reitti käynnistyi ilman
  yhtäkään kirjasinta – jokainen merkki piirtyi korvaavana laatikkona,
  eikä sivulla ollut luettavaa tekstiä: siitä hakenut tai jotain
  kopioida yrittänyt ei löytänyt mitään. Nyt raportti lataa siinä
  tapauksessa järjestelmän kirjasimet; teksti on upotettu ja luettavissa.
  Ikkunasta tehdyt raportit eivät koskaan olleet tästä kärsineet.

- **„Palauta alkuperäinen” useamman skannauksen rivin yli jätti mustia
  raitoja rivien väliin.** Kuvaksi muunnetulla sivulla kehys siivosi vain
  itse rivikaistat; aiemman peiton jäänteet jäivät rivien väliin.
  Nyt vedetty kehys jakautuu kokonaan riveille.

- **Toinen kehys paikkamerkin päällä jätti punaisen jäänteen.**
  Paikkamerkki on lähes aina leveämpi kuin sana, jota se edustaa; sen
  jälkeen samaa kohtaa peittänyt osui vain sen alkuun – jäljelle jäi
  katkelma kuten „RIFF_1]” keskellä lausetta, ja palauttaminen asetti
  alkuperäisen tekstin sen jälkeen sen paikalle sanan paikan sijaan.
  Katkaistu paikkamerkki poistuu nyt aina kokonaan.

- **Käännetyllä sivulla paikkamerkin peittäminen poisti asiaan
  kuulumattoman lauseen.** Jälkikäteen piirretty paikkamerkki sekoitettiin
  poistettaessa sitä edeltävään tekstiin: se itse jäi paikoilleen, tuli
  varoitus „on edelleen asiakirjassa” – ja sivun muualla katosi
  korvauksetta lause, jolla ei ollut mitään tekemistä kehyksen kanssa.
  Paikkamerkki löydetään nyt uudelleen sanamuotonsa perusteella; ketju
  „korvaa, peitä, palauta” toimii nyt myös poikittain sisäänvedetyillä
  sivuilla.

- **Käyttöohje neuvoi kymmenessä kielessä yhä käyttämään pakettia
  `python3-tk`.** Vianetsinnässä luki, että Linuxista saattaa puuttua
  tkinter – neuvo Qt-käyttöliittymää edeltävältä ajalta, josta ei enää
  ole kenellekään hyötyä. Nyt kaikissa versioissa lukee sama kappale kuin
  saksankielisessä: puuttuvat järjestelmäkirjastot, joita Qt tarvitsee
  esitykseen.

- **Käyttöohjeen lisenssiluku oli kaikissa kuudessatoista käännöksessä
  vanhentunut.** Kymmenessä kielessä siellä luki yhä, että Windows Server
  tarvitsee yrityslisenssin palvelinkäytöllä ja ettei koejaksoa tai
  ilmaistasoa ole siellä saatavilla – siitä lähtien kun paikka laskee
  ihmisen eikä konetta, molemmat ovat vääriä. Kaikkialta puuttuivat myös
  tiedot siitä, milloin varattu paikka vapautuu jälleen, että lisenssi
  vahvistaa itsensä säännöllisesti ja mitä siinä silloin siirretään, ja
  aktivointi ilman internetiä oli vain lyhennelmänä ilman kolmea
  vaihetta ja ilman mainintaa siitä, että kone toimii sen jälkeen vuoden
  ilman yhteyttä.

- **Seitsemän kappaletta jälkikäsittelystä puuttui kymmenestä kielestä.**
  Ohjetta tanskaksi, suomeksi, ranskaksi, italiaksi, hollanniksi,
  norjaksi, puolaksi, portugaliksi, ruotsiksi tai espanjaksi lukenut ei
  löytänyt Office-tiedostojen sivunäkymää eikä „Peitä käsin” -toimintoa
  eikä koko kappaletta siitä, miten ohjelma oppii korjauksesta – mukaan
  lukien taulukko kolmesta laajuudesta. Kohdasta „Mitä tunnistetaan”
  puuttui samoista kymmenestä versiosta myös reitti asiakirjan
  kenttäotsikon kautta.

- **Ohjelma ei enää käynnistynyt lisenssin lukemisen jälkeen.** Ikkunan
  sijaan tuli „Ohjelmaa ei voitu käynnistää” – ja tämä jokaisella
  lisenssillä, olipa kyseessä mikä tahansa. Syynä oli lisenssinäytön rivi,
  joka varoittaa juuri ennen tarkistusajan päättymistä; se käytti jotain,
  mitä siellä ei ollut saatavilla. Ilman lisenssiä – koejaksolla ja
  ilmaistasolla – virhettä ei ilmennyt, siksi se huomattiin vasta nyt.

- **Lomakkeessa kenttänimet jäävät nyt paikoilleen.** „Geburtsdatum” ja
  „Anschrift” katosivat arvonsa mukana: paikkamerkki oli pienenä ja
  punaisena *kenttänimen* paikalla, sen alla oleva kenttä jäi tyhjäksi.
  Kenttänimi ei kuulu tietoihin – se jää nyt paikoilleen, ja paikkamerkki
  on siellä, missä arvo oli.

- **Vieraskielisiä asiakirjaotsikoita ei enää pidetä niminä.** Italialaisen
  lomakkeen yläpuolella luki „FATTURA”, espanjalaisen „PERMISO PARENTAL”
  – molemmat korvattiin. Asiakirjasanojen luettelo tunsi vain
  saksankieliset vastineet.

- **Laskusta ei enää katoa rivejä.** „Materialaufschlag 1  84,00”
  tulkittiin osoitteeksi ja korvattiin paikkamerkillä – tositteesta
  puuttui sen jälkeen rivi. Rivi, joka päättyy summaan, on rivi eikä
  osoite; todelliset osoitteet („Hauptstraße 1  120,00”) pysyvät
  koskemattomina.

### Muutettu

- **„Valvo kansiota …” ja komentorivi ovat toistaiseksi poissa.** Molemmat
  reitit on rakennettu ja ne toimivat, mutta kumpaakaan ei ole kokeiltu
  laajalti: kansionvalvonta ei ole koskaan nähnyt Windows-testausta, ja
  komentorivi antaa skriptille parikymmentä kytkintä käteen, joita ei ole
  koskaan ajettu kenelläkään käyttäjällä. Sen, mikä muokkaa asiakirjoja
  ilman valvontaa, ei pitäisi tehdä sitä tarkastamattomana – siksi ne on
  vedetty pois, kunnes testaus on hoidettu. Valikkokohta puuttuu, eikä
  `--wache` enää näy komennossa `maskuro --help`.

- **Avoimeksi jää, mikä vain lukee ja mitä tarvitaan joka tapauksessa.**
  Hakuajo (`--suchlauf`) ja tarkistus (`--nachpruefen`) toimivat edelleen
  komentorivillä – ne eivät muuta yhtäkään tiedostoa. Samoin käynnistys
  Resurssienhallinnasta, pikavalikosta, leikepöydältä ja ikkunasta; niihin
  ei muutu mikään.

- **„Hae skannerista” on nyt oma luku käyttöohjeessa.** Se oli aiemmin
  luvun „Valvo kansiota” lopussa. Macilla neuvo oli aiemmin kansion
  valvominen; nyt se on luettujen sivujen vetäminen ikkunaan.

### Korjattu

- **„Palauta alkuperäinen” useamman rivin yli tuhosi jäsentelyn.** Kehys
  paikkamerkin, muuttumattoman työnimikkeen ja toisen korvauksen päällä
  asetti koko alueen uudelleen **yhtenä** rivinä – kolmesta rivistä tuli
  yksi, ja se, mikä ei enää mahtunut, muuttui palkiksi. Nyt jokainen rivi
  palautetaan erikseen.

- **Ja muuttumaton teksti pysyy siinä koskemattomana.** Korvauksen *ja*
  tavallisen tekstin yli vetävä saa takaisin vain korvauksen; loppu jää
  koskematta. Myös vanhan paikkamerkin viimeinen jäänne katoaa tällöin –
  aiemmin sen sulkeva hakasulje jäi lauseen keskelle.

- **Korvattaessa vanhan tekstin jäänteitä ei enää jää.** Lihavoidussa
  otsikossa luki sen jälkeen „1. R[BEGRIFF_2]ige [BEGRIFF_1] … che” –
  paikkamerkki oli siinä, mutta alkuperäisen tavuja sen vieressä.
  Siivotaan nyt se alue, jonka rajaat, ei vain sen sisällä olevien
  sanojen laatikot.

- **Anonyymiä paikkamerkkiä ei enää palauteta.** Anonymisoitaessa
  jokainen nimi kantaa samaa merkintää `[NAME]`. Palautus otti aiemmin
  ensimmäisen sattuman ja kirjoitti sen jokaiseen löytökohtaan –
  „Georg Aigner” muuttui muotoon „Anna Musterfrau”, siis väärä nimi
  asiakirjaan. Nyt siinä lukee, ettei enää voida sanoa, mikä tieto oli
  tarkoitettu; asiakirja jää koskemattomaksi.

### Uutta

- **„Palauta alkuperäinen” toimii nyt myös rasteroidulla sivulla.** Jos
  sivu oli muunnettu kuvaksi, tuli aiemmin kieltäytyminen: palautettu
  teksti jäisi sivukuvan alle. Nyt kohta kuvassa siivotaan ja teksti
  kirjoitetaan sen päälle – kuten paikkamerkki skannauksessa. Sisältö
  tulee tällöin alkuperäisestä tiedostosta, eikä se ole rasteroitu.

- **„Palauta valinta” on nyt oma painikkeensa.** Se onnistui jo
  aiemminkin, mutta vain, jos sattumalta merkitsi paikkamerkin ja painoi
  „Korvaa valinta” – toimintoa, jonka löytää vain sattumalta, ei
  käyttäjän kannalta ole olemassa.

### Muutettu

- **Pelkässä tekstissä, CSV:ssä ja Outlook-viesteissä ei enää ole
  „Peitä valinta” -toimintoa.** Nämä muodot eivät voi kantaa palkkia;
  painike asetti niissä paikkamerkin ja kertoi siitä myös – mutta
  painike, joka tekee muuta kuin mitä sen nimi lupaa, ei kuulu sinne.

- **Työkalu kertoo nyt, jos sillä ei ole tässä kohdassa mitään
  tehtävää.** Paikkamerkkiä ei voi korvata uudelleen, peiton päälle ei
  aseteta paikkamerkkiä, ja missä alkuperäinen on jo näkyvissä, ei ole
  mitään palautettavaa. Aiemmin nämä toiminnot tekivät jotain, mikä
  näytti vaikutukselta, mutta ei ollut.

## 0.10.29-alpha.20260817 – 17. elokuuta 2026

### Korjattu

- **Jälkikäsittely-ikkunassa jokainen vedetty kehys toimii nyt.** Jos samaa
  kohtaa käsiteltiin kahdesti – ensin korvattiin, sitten peitettiin, sitten
  palautettiin alkuperäinen –, toinen ja kolmas veto haihtuivat sanattomasti:
  edellisen vedon vielä tavoitettavissa oleva kehys sieppasi sen. Sama tapahtui
  työkalua vaihdettaessa, jolloin jopa vanha työkalu jatkoi hiljaa
  toimintaansa.
- **Liian kapeaksi vedetty kehys kertoo, että se on liian kapea.** Aiemmin
  esikatselu syttyi punaisena yhden sanan verran, ja irrottaessa ei
  tapahtunut sanattomasti mitään.

- **Outlook-viestejä voi vihdoin jälkikäsitellä.** `.msg`-tiedosto näytti
  jälkikäsittely-ikkunassa „Tätä muotoa ei voi näyttää täällä” – se oli ainoa
  tuettu muoto ilman mitään keinoa käsin jälkikäsittelyyn. Nyt lähettäjä,
  vastaanottaja, aihe ja viestiteksti näkyvät nimettyinä näkymässä ja ne
  voidaan merkitä ja korvata kuten missä tahansa muussa tekstimuodossa.

- **„Korvaa valinta” pysyy sähköpostissa valinnassa.** Leipätekstistä nimen
  merkinnyt menetti samalla myös lähettäjän ja vastaanottajan otsikkotiedoista,
  ja ilmoitus mainitsi eri paikkamerkin kuin sen, joka tekstissä oli. Nyt
  merkitty arvo korvataan kaikkialla – myös lähettäjässä, jos se on siellä –
  eikä mitään muuta kosketa.

- **Useamman rivin yli ulottuva kehys ei enää tuhoa tekstiä.** Aiemmin syntyi
  yksi ainoa paikkamerkki yhteen kohtaan: katkaistusta sanasta jäi tähän
  kiinni jäännös, ja toisen rivin teksti katosi korvauksetta – ei
  paikkamerkkiä, ei palkkia, vain aukko. Nyt jokainen rivi saa oman
  paikkamerkkinsä sillä arvolla, joka siinä todella oli.

- **„Palauta alkuperäinen” toimii nyt myös peittämisen jälkeen.** Ikkuna
  ilmoitti onnistumisesta, eikä teksti palannut koskaan: musta palkki
  laskettiin esteeksi, jolloin palautetulle tekstille ei jäänyt enää tilaa.
  Palkki väistyy nyt, ja palautettu teksti näkyy mustana kuten tavallinen
  teksti – ei punaisena kuten paikkamerkki.

- **„Palauta alkuperäinen” ei enää tee mitään koskemattomassa kohdassa.**
  Kehyksen vetäjä tekstin päälle, jota ei ollut muutettu lainkaan, sai
  tekstin poistetuksi ja pienempänä ja siirrettynä takaisin asetetuksi –
  onnistumista ilmoitettiin. Nyt siinä lukee, ettei mitään ole palautettavaa.

### Uutta

- **Myös Wordissa, Excelissä, PowerPointissa, OpenDocumentissa ja tekstissä
  voi peittää.** Aiemmin siellä oli vain „Korvaa valinta”; palkki oli
  varattu PDF-näkymälle ilman siihen mitään syytä. Missä palkkia ei voida
  esittää – pelkässä tekstissä ja Outlook-viestissä –, arvo korvataan
  edelleen paikkamerkillä, ja niin lukee myös ilmoituksessa.

- **Paikkamerkin merkitseminen palauttaa sen.** Tekstinäkymässä (Word,
  Excel, PowerPoint, OpenDocument, teksti) riittää nyt merkitä paikkamerkki
  ja painaa „Korvaa valinta”: alkuperäinen arvo palaa. Aiemmin ikkuna
  ohjasi tätä varten osumapaneeliin.

- **Kokouspöytäkirjan puhujat tunnistetaan myös silloin, kun heidän nimensä
  on samalla tavallinen sana.** „Gruber: Die Abnahme erfolgt kommende Woche.”
  korvattiin, „Bauer: Ich stimme zu.” jäi paikoilleen – sukunimi näyttää
  tunnistuksen kannalta hyvin samalta kuin pääsana. Saman rakenteen
  huomiorivit pysyvät koskemattomina: lauseesta „Achtung: Die Anlage ist
  abzuschalten.” ei tule nimeä.

- **„Käytössäsi on uusin versio” sanottiin myös silloin, kun tarkistusta ei
  voitu tehdä lainkaan.** Jos päivityspalvelin hylkää pyynnön – koska
  samasta internetosoitteesta tuli liikaa pyyntöjä tai koska palvelin on
  itse juuri häiriintynyt –, ohjelma jäi seisomaan vanhaan versioonsa ja
  väitti sen olevan uusin. Juuri näin kävi 17. elokuuta Mac-koneella:
  0.10.25 jäi paikalleen, vaikka 0.10.28 oli ollut valmiina jo tuntikausia.

  Nyt ikkuna kertoo, mistä on kyse, ilmoittaa seuraavan tarkistuksen
  kellonajan – ja huomauttaa nimenomaisesti, ettei ole **varmaa**, onko oma
  versio uusin.

  Yleensä kyse ei ole omasta koneesta: monissa liittymissä useat asiakkaat
  jakavat saman internetosoitteen, ja palvelin laskee ne yhteen. Siksi
  Maskuro etsii tässä tapauksessa versioluetteloa **toista reittiä** ja
  löytää uudet versiot useimmiten silti. Jos hylkäys jatkuu, palvelin
  jätetään rauhaan ilmoitettuun kellonaikaan asti – vaikka painiketta
  painettaisiin uudelleen; uudelleenyrittäminen vain pidentää eston.

- **Määrätietoja ei enää pidetä paikannimenä.** Palvelusopimuksessa „Vier-
  Tage-Woche” katosi paikkamerkin taakse – keskellä sopimuksen kohdetta.
  Tällaiset luvun ja väliviivan yhdistelmät („Drei-Punkte-Plan”,
  „24-Stunden-Dienst”) jäävät nyt paikoilleen. Osoitteet on rajattu tämän
  ulkopuolelle: „Zwei-Brüder-Weg” korvataan edelleen.

## 0.10.28-alpha.20260817 – 17. elokuuta 2026

### Muutettu

- **Lisenssipaikat lasketaan nyt todella.** Aiemmin yksikään työasema ei
  koskaan ilmoittautunut lisenssipalveluun – kymmenen paikan lisenssi
  toimi rajattomalla määrällä koneita ilman, että kukaan sai siitä tietää.
  Uutta: ohjelman käynnistävä kone varaa paikan; paikka vapautuu itsestään
  **seitsemän päivän kuluttua ilman käynnistystä**, jotta rikkoutunut
  laite tai lähtenyt työntekijä ei estä mitään pysyvästi.

  Pieni ylitys **vain näytetään, ei estetä**: kymmeneen prosenttiin asti
  ostetusta määrästä kaikki jatkavat toimintaansa – uuden kannettavan
  vieressä olevan vielä kirjautuneena olevan vanhan ei pitäisi olla
  tukilinjan tapaus. Sen yli tuleva palaa ilmaistasolle ja saa siitä
  ilmoituksen; ensin mukana olleet koneet eivät huomaa mitään.

- **Ostettu lisenssi vahvistaa itsensä säännöllisesti.** Jos se ei onnistu
  **30 päivään**, on ilmaistaso voimassa niin kauan, kunnes se taas
  onnistuu. Mitään ei kytketä pois päältä, ja viikkoa etukäteen ikkunassa
  näkyy huomautus. Heti kun kone pääsee taas internetiin, asia hoituu
  itsestään. Koejakso ja ilmaistaso eivät edelleenkään ilmoita mitään
  lainkaan – koskaan ostamatta jättävä ei koskaan soita.

- **„Aktivoi ilman internetiä” toimii vihdoin.** Aktivointi tarkistettiin ja
  tallennettiin aiemmin kyllä, mutta kukaan ei sen jälkeen lukenut sitä –
  se ei muuttanut oikeuksia mitenkään. Nyt se on ratkaisu koneille ilman
  verkkoyhteyttä: se on voimassa **vuoden**, sen jälkeen haetaan tuoreella
  pyyntökoodilla uusi. Verkkoyhteydellä varustettua laitetta tarvitaan
  siihen kerran vuodessa – kone itse voi pysyä pysyvästi verkon
  ulkopuolella.

- **Aktivointi onnistuu nyt myös asiakastililtä** – kohdasta „Omat
  lisenssit” verkkosivustolla. Siellä näkyy myös, mitkä koneet on liitetty
  lisenssiisi ja milloin niiden paikat vapautuvat jälleen; tätä ei
  aiemmin näkynyt missään. Sivu ilman kirjautumista pysyy kaikkien
  käytettävissä, joilla ei ole kaupan tunnuksia – se vaatii sen sijaan
  lisäksi tilauksen sähköpostiosoitteen, jotta pelkkä lisenssiavain ei
  riitä.

- **Ja ikkunassa lukee nyt, minne pyyntökoodi viedään.** Paperiviesti sanoi
  „syötä internetyhteydellä varustetulla laitteella” eikä maininnut
  osoitetta; aktivointisivu on ollut olemassa jo pitkään, mutta siihen ei
  ollut linkkiä mistään. Nyt valintaikkunassa, käyttöohjeessa ja UKK:ssa
  lukee **maskuro.com/lizenz-freischalten** – ja verkkosivustolla
  lisenssiavaimen alla.

- **Painike „Aktivoi ilman internetiä …” pysyy näkyvissä**, vaikka lisenssi
  ei juuri nyt olisi voimassa. Aiemmin se katosi lisenssin mukana – juuri
  silloin, kun sitä tarvitaan.

- **„Kaikki paikat varattu” kertoo nyt totuuden.** Huomautus päättyi
  aiemmin sanoihin „Ohjelma jatkaa toimintaansa muuttumattomana”; tämä ei
  enää pidä paikkaansa, jos paikkaa ei myönnetty. Siellä lukee nyt, että
  toistaiseksi on voimassa ilmaistaso.

### Uutta

- **Leikepöydän puhdistuksen kytkemisen yhteydessä lukee nyt, että asia
  on tarkistettava.** Ilmoitus mainitsee siitä lähtien saman lauseen,
  joka on myös tiedoston tuloksen yhteydessä: Maskuro ei aina tunnista
  kaikkia henkilötietoja.

  Tässä se painaa enemmän kuin muualla. Tiedostossa tuloksen näkee ennen
  kuin sen luovuttaa eteenpäin. Leikepöydällä ei – kopioidaan, liitetään,
  ja puhdistettu teksti on jo sähköpostiikkunassa. Ilmoitus kehottaa siksi
  nimenomaisesti tarkistamaan **liitetyn** tekstin.

  Se tulee esiin kytkettäessä, ei jokaisella kopiointikerralla: mikä
  näkyisi viisikymmentä kertaa päivässä, sitä ei kolmannen kerran jälkeen
  enää lue kukaan.

- **„Kopioi kaikki” listan alle – ja „Poista kaikki” siirtyy pois.** Uusi
  painike siirtää kaikki valmiit tulokset kerralla leikepöydälle,
  liitettäväksi sähköpostiin tai toiseen ohjelmaan. Aiemmin tämä onnistui
  vain valikosta ja siinäkin vain **valituille** riveille – kaikkia
  tarkoittavan piti ensin painaa Ctrl+A.

  Samalla painikerivi on järjestetty uudelleen: vasemmalla se, mikä lisää
  jotain, oikealla välin jälkeen se, mikä poistaa jotain. „Poista kaikki”
  oli aiemmin heti „Lisää …” -painikkeen vieressä, ja väärä osuma maksoi
  koko listan. Sama sääntö on koskenut jo 13. elokuuta lähtien jokaista
  valmista riviä.

- **Työasemat ilman internetiä saavat nyt kielimallinsa talon sisältä.**
  Puhdistus onnistui siellä aina ilmankin yhteyttä – kielimallin
  jälkilataus ei, ja malli painaa satoja megatavuja.

  Ylläpito kokoaa tiedostot kerran yhteydellä varustetulla koneella ja
  vie ne jakoon, käyttöönottoon tai muistitikulle. Sijainti kirjataan
  keskitetysti (kenttä `modellquelle` tiedostossa `vorgaben.json` tai
  ympäristömuuttuja `MASKURO_MODELLQUELLE`). Siitä lähtien jokainen
  jälkilataus käyttää ensin sitä – kielimallit, japanilainen sanakirja ja
  korkea taso – ja menee verkkoon vasta, jos tiedosto puuttuu.

  Tarkisteet pätevät tällöin muuttumattomina. Talon sisäinen tiedostojako
  on usein helpompi kuvata kuin verkossa oleva julkaisu; siitä ei ole
  tarkoitus tulla helpompaa reittiä väärennettyyn malliin.

  Kuinka tällainen varasto syntyy ja miten lisenssi ja aktivointi toimivat
  ilman internetiä, on kuvattu tiedostossa `OFFLINE.md`.

- **„Palauta alkuperäinen” – kehys palauttaa sen, mitä poistettiin liikaa.**
  Jälkikäsittely-ikkunassa on uusi työkalu: vedä kehys kohdan päälle, ja
  teksti on jälleen sellainen kuin se oli alkuperäisessä.

  Tämä sulkee aukon, jonka osumapaneeli jätti auki. Siellä korvauksen
  saattoi perua vain, jos sen paikkamerkki oli yksiselitteinen – ei siis
  anonymisoinnissa, jossa „[NAME]” on jokaisen tällaisen tiedon kohdalla,
  eikä lainkaan peitetyissä kohdissa, joissa ei jää mitään paikkamerkkiä.
  Juuri niissä kohdissa kertyvät virheosumat: „Benutzer”, „Inventarnummer”,
  „Unterschrift” tulkitaan mielellään nimiksi.

  Kehys ei tarvitse paikkamerkkiä: **kohta** tulee suorakulmiosta,
  **sisältö** alkuperäisestä tiedostosta – samasta, jonka
  ennen/jälkeen-kytkin näyttää. Anonymisoitu vai pseudonymisoitu ei siten
  ole enää merkityksellistä.

  Palautettu teksti näkyy mustana, ei punaisena: se on jälleen
  selkotekstiä eikä paikkamerkki. Osumaluettelosta merkintä katoaa vasta
  sitten, kun sen paikkamerkkiä ei enää ole **missään** asiakirjassa – jos
  sama arvo korvattiin useassa kohdassa, se jää voimaan muille kohdille.

  Sivulla, joka on muunnettu kuvaksi, työkalu kieltäytyy ja selittää
  miksi: palautettu teksti jäisi sivukuvan alle eikä näkyisi.

### Korjattu

- **Osioiden „Yksityiskohdat” ja „Tunnusluvut” pienentäessä kuvajäänteitä
  jäi näytölle.** Pienennettynä osa sisällöstä siirtyi ikkunan alareunan
  alle ja jäi siihen taustan päälle, kunnes jotain muuta piirrettiin
  siihen päälle.

  Molemmilla alueilla on vähimmäiskorkeus, jotta ne ovat avattuina
  käyttökelpoisen kokoisia. Pienentämisliike laski kuitenkin vain
  enimmäiskorkeutta – eikä alue kutistu vähimmäiskorkeutensa alle. Sisältö
  siis pysyi 200 pisteen korkuisena, vaikka ikkuna oli jo kutistunut 24:ään;
  erotus jäi reunan alle. Nyt vähimmäiskorkeus väistyy liikkeen ajaksi ja
  palautuu sen jälkeen.

- **Ikkuna pieneni yhä toistuvasti avattaessa ja suljettaessa.** Avattaessa
  se kasvaa enintään 92 %:iin ruudun korkeudesta; jos tilaa on vähän, se
  siis kasvaa vähemmän kuin tarvitsisi. Suljettaessa se silti vähensi
  koko määrän takaisin. Nyt se palauttaa täsmälleen sen, minkä avaaminen
  maksoi.

- **Peitetyn tiedon jäänne saattoi jäädä näkyviin.** Ansioluettelossa
  merkinnästä „*30.12.1991” jäivät merkit „*30.1” luettavaksi tulokseen –
  eli syntymäajan päivä ja kuukauden alku. Ohjelma oli jopa huomannut
  jäänteen ja muuttanut siksi sivun kuvaksi; juuri se teki asiasta
  pahemman, sillä sen myötä jäänne ei enää ollut haettavissa, mutta oli
  edelleen luettavissa – eikä enää korjattavissa.

  Syy oli kahden tarkistuksen välissä. Tarkempi niistä katsoo, seisooko
  poistetun tiedon alueella vielä jotain, mikä ei sinne kuulu; se
  ilmoittaa löydöksensä merkkijoukkona, koska lukujärjestys siirtyy
  korvattaessa. Varajärjestelmä, joka maalaa tällaiset kohdat ennen
  muuntamista, etsi tätä merkkijoukkoa tekstinä sivulta – eikä löytänyt
  sitä koskaan. Mitään ei siksi maalattu. Kohta oli koko ajan tiedossa ja
  välitetään nyt suoraan, sen sijaan että se etsittäisiin uudelleen.

  Tämä koski jokaista sivua, jonka jäänteen löysi vain tämä tarkistus –
  riippumatta tiedostotyypistä ja kielestä.

- **Poikittain sisäänvedetystä skannauksesta tekstintunnistus ei löytänyt
  mitään.** Arkin sivuttain syöttöön asettava saa tiedoston, jossa teksti
  on käännetty 90 astetta. Aiemmin Maskuro ei lukenut siitä **yhtäkään**
  tietoa – ja tiedosto näytti sen jälkeen huomaamattomalta: mitään ei
  löytynyt, joten mitään ei ilmoitettu, ja osoite oli edelleen luettavissa
  kuvassa. Nyt tekstintunnistus oikaisee sivun itse; tarkistuskuvassa
  kaikki tiedot löytyvät jälleen.

  Kaksi rajaa on tuotu avoimesti esiin: **ylösalaisin** oleva arkki (180
  astetta) ei edelleenkään luettavissa, ja hyvin huonolla skannauksella
  oikaisu ei auta – siellä on liian vähän luettavaa asennon
  määrittämiseen ylipäätään. Jokainen kuva vie tästä noin viidenneksen
  kauemmin.

### Muutettu

- **„Asenna automaattisesti” tarkoittaa nyt sitä, mitä se tekee.** Asetusten
  valintaruutu lupasi enemmän kuin se lunasti: se lataa uuden version
  itsestään ja käynnistää asennuksen – mutta se etenee **näkyvästi** ja
  haluaa vahvistuksen, Windowsissa myös käyttäjätilien valvonnan
  kyselyllä. „Automaattinen”-sanan lukenut odotti konetta, joka päivittyy
  itsestään yön yli, ja seisoi aamulla asennusohjatun edessä. Valintaruutu
  on nyt nimeltään „Lataa päivitykset itsestään ja käynnistä asennus”,
  ja sen alla lukee lause, mitä se tarkoittaa. Toiminta ei muutu millään
  tavalla – se, ettei Maskuro vaihdu huomaamatta, on tarkoituksellista ja
  pysyy niin.

## 0.10.27-alpha.20260817 – 17. elokuuta 2026

### Uutta

- **Uutta: `--ersetzen` toimistosovelluksen liitäntää varten.** Tulos tulee
  lähdetiedoston tilalle sen sijaan, että se syntyisi sen viereen. Näin
  toimistosovelluksen ulos- ja sisäänkirjaus („Avaa ja muokkaa" sähköisessä
  asiakirjasalkussa) toimii ilman mitään rajapintaa: sovellus antaa
  tiedoston ulos ja saa sen samaan paikkaan puhdistettuna takaisin.

  **Tämä kytkin kumoaa ensimmäisen perusperiaatteen**, ja siksi se on
  saatavilla vain komentorivillä – ei ikkunassa – ja vain, jos hallintonne
  sallii sen (merkintä `ersetzen` vakioasetustiedostossa). Ilman lupaa
  kutsu keskeytyy ja kertoo miksi; hiljainen toisen tiedoston luominen olisi
  pahempi virhe, sillä silloin muuttamaton tiedosto kirjattaisiin uudelleen
  sisään.

  Ensin kirjoitetaan naapuritiedosto; vasta kun se on valmis, se astuu
  lähteen tilalle. Keskeytys tai virhe jättää lähteen siis **tavu tavulta
  muuttumattomaksi** eikä jätä jälkeensä keskeneräistä palasta.
  Tarkastuslokissa korvaaminen näkyy omana kenttänään – tarkastajan on
  tiedettävä, ettei puhdistettu versio enää ole täällä.

- **Käyttöopas selittää nyt Windowsin varoituksen ensimmäisellä
  käynnistyksellä.** Uusi ensimmäinen osio „Windows varoittaa
  ensimmäisellä käynnistyksellä – mitä tehdä", kahdella kuvalla ja kolmella
  vaiheella: „Lisätietoja" on pieni linkki, ei painike – juuri siihen useimmat
  jäävät jumiin –, sitten „Suorita silti".

  Se, että siinä lukee „Tuntematon julkaisija", on koko varoituksen sisältö:
  paketit toimitetaan tällä hetkellä ilman varmennetta. Pidämme oikeampana
  selittää tämä kuin vaieta siitä.

- **Paluutie huomaa nyt, jos teksti ja vastaavuus eivät kuulu yhteen.**
  Kuka tahansa liitti vastauksen toiseen tapaukseen, sai aiemmin vieraita
  nimiä oikeaan tekstiin – ei virhettä, ei ilmoitusta, vain väärin. Maskuro
  muistaa nyt, mitkä korvausmerkit viimeisin ajo ylipäätään tuotti, ja
  ilmoittaa jokaisesta, joka ei kuulu joukkoon. Jos yksikään ei ole peräisin
  viimeisimmästä ajosta, mitään ei lisätä ja ikkuna kertoo miksi – sen
  sijaan että aiemmin oletettiin vanhentunutta määräaikaa.

  **Yksi raja säilyy, ja se lukee myös käyttöoppaassa:** korvausmerkit
  numeroidaan juoksevasti ajokohtaisesti, joten ensimmäinen nimi on jokaisessa
  asiakirjassa `[NAME_1]`. Jos vieras teksti sisältää vain tällaisia
  korvausmerkkejä, sekaannusta ei voida havaita.

- **PDF voidaan nyt tulostaa mustavalkoisena.** Valintaruutu
  toimintatavassa muuntaa jokaisen sivun mustavalkoiseksi kuvaksi –
  näkymättömän tekstitason kanssa sen alla, joten se pysyy luettavana ja
  haettavana. Lähetykseen beA:n ja vastaavien tiukan kokorajan väylien
  kautta: mittauskorpuksemme mukaan keskimäärin **68 % pienempi**
  (komentorivillä: `--monochrom`).

  **Kuinka paljon se auttaa, riippuu asiakirjasta** – ja se lukee myös
  valintaruudun kohdalla: skannattu ja kuvapitoinen materiaali kutistuu
  voimakkaasti, kevyt tekstiasiakirja ilman upotettuja fontteja voi jopa
  kasvaa. Kokeile sitä yhdellä tiedostolla, ennen kuin otat sen käyttöön
  koko erälle.

  Hinta: jokainen sivu lasketaan uudelleen – tuhannella sivulla se kestää
  minuutteja. Ja kuvat menettävät kaiken mustan ja valkoisen välillä; tekstin
  kannalta se on yhdentekevää, valokuvan kannalta ei.

- **Jälkikäsittely-ikkunan osumaluettelo laskee nyt mukana.** Luettelon
  yläpuolella lukee „5 osumaa", ja heti kun suodatatte, „1/5 osumasta". Se
  on ero „suodatin on käytössä" ja „niitä on viisi, ja olen nähnyt ne
  kaikki" välillä – ote, jolla tarkistetaan, onko nimi todella korvattu
  kaikkialla.

- **Tarkastuslokia voi nyt hakea ja suodattaa.** Näkymässä „Tiedosto →
  Tarkastusloki" oli tähän asti vain taulukko eikä muuta – kuukaudessa,
  jossa oli kolmetuhatta ajoa, näki että paljon oli tapahtunut, mutta ei
  mitä.

  Uutta ovat **hakukenttä**, **kolme suodatinta** (menetelmä, tulos, laji)
  ja **selailu**, sekä kolme saraketta, joita ei ennen ollut:
  **menetelmä** (mustattu vai korvattu), **luottamus** ja **kesto**.
  Luettelon yläpuolella lukee, kuinka paljon on juuri näkyvissä ja kuinka
  paljon suodatin piilottaa.

  „Tallenna CSV-muodossa …" tuottaa nyt **sen, mitä näkyy** – suodattanut
  saa suodatetun aineiston, ja ilmoitus kertoo lukumäärän.

  Viiva luottamuksen tai keston kohdalla tarkoittaa, ettei tälle riville
  ole mitattu mitään – esimerkiksi koska se on vanhempi kuin tämä
  ominaisuus. Näitä arvoja **ei** lasketa jälkikäteen. Käyttäjäkohtaista
  suodatinta ei edelleenkään ole; yksittäisen rivin löytää silti haulla.

### Poistettu

- **Ikkunan „Tietoja tästä ohjelmasta" läpinäkyvyysilmoitus on jälleen
  poissa.** Se oli siellä versiosta 0.10.22-beta.1 lähtien ja kertoi, että
  sovellus kehitettiin tekoälyn tuella. Sitä ei vaadita missään, ja
  nimenomaan tietosuojasovelluksessa moni luki sen kannanottona
  toimintatavasta – ikään kuin asiakirjat menisivät verkossa toimivaan
  palveluun. Puhdistus tapahtuu edelleen yksinomaan omalla koneella;
  se lukee siellä, minne se kuuluu, välilehdellä „Tietosuoja".

### Korjattu

- **Ohjelma vaihtoi oman kuvakkeensa huonompaan.** Kuka tahansa lisäsi
  kontekstivalikon ohjelmasta käsin, sai sen jälkeen tehtäväpalkkiin toisen
  kilven kuin asennuksen jälkeen – samankaltaisen, mutta vasemmalle
  tasatuin palkein keskitetyn sijaan ja näkyvästi karkeamman. Taustalla oli
  hätäratkaisu: jos ohjelma ei löydä kuvakemallia, se piirtää itselleen
  yhden. Tarkoitus oli varautua tilanteeseen, jossa kuvakkeita **ei ole
  lainkaan**; todellisuudessa se piirsi myös silloin, kun toimitetut olivat
  jo paikoillaan – ja korvasi ne. Asennusohjelmasta asennetussa versiossa
  mallia ei ole, joten siellä se kohtasi jokaisen. Olemassa olevat kuvakkeet
  pysyvät nyt koskemattomina.

  **Jo vaikutuksen alaiset asennukset eivät hae oikeaa kuvaketta itsestään
  takaisin** – asenna sitä varten kertaalleen uudelleen.

- **„Objektkennung: OB-4711-22" tulkittiin käyttäjätunnukseksi.**
  Käyttäjätunnusten tunnistin tarkisti otsikkonsa ilman sanarajaa niiden
  edessä – eli se tarttui **jokaiseen** sanaan, joka päättyy johonkin
  niistä: Objektkennung, Fahrzeugkennung, Gerätekennung. Sen perässä oleva
  arvo poistettiin, vaikka sillä ei ole mitään tekemistä käyttäjätunnuksen
  kanssa.

  Yhdyssanat, joita todella tarkoitetaan – „Benutzerkennung",
  „Anmeldekennung" –, ovat luettelossa yksitellen ja löytyvät edelleen.

- **Englanniksi, kreikaksi, japaniksi ja koreaksi tuloksessa oli kuusitoista
  korvausmerkkiä saksaksi.** Jos käyttöliittymä oli asetettu johonkin
  näistä neljästä kielestä, uudemmat tietolajit kirjoitettiin asiakirjaan
  saksankielisin otsikoin – salasanasta tuli `[ZUGANGSDATEN_1]` eikä
  `[CREDENTIALS_1]`, diagnoosiavaimesta `[DIAGNOSESCHLUESSEL_1]` eikä
  `[DIAGNOSIS_CODE_1]`. Kyseessä olivat terveys, diagnoosi, lääkitys,
  diagnoosi- ja lääkeavaimet, uskonto, ammattiyhdistys, poliittinen
  mielipide, rikosoikeus, kirjautumistiedot, käyttäjätunnus, korttitiedot,
  koordinaatit, ammatti, summa ja ominaisuus.

  Muilla 44 kielellä virhettä ei koskaan ollut: ne hakevat otsikkonsa
  kielitiedostoista, joissa nämä lajit olivat alusta asti mukana. Juuri
  nämä neljä kieltä käyttävät toisesta syystä omia taulukoita – niiden
  kirjoitusjärjestelmä ei säily PDF-merkistössä, minkä vuoksi siellä on
  latinalaiset otsikot –, ja näistä taulukoista uudet lajit puuttuivat
  yksinkertaisesti.

  Asia huomattiin tuoteluettelosivua käännettäessä: verkkosivusto lupasi
  englanninkielisille lukijoille otsikoita, joita ohjelma ei kirjoittanut.
  Testi vertaa nyt näitä neljää taulukkoa listaan kaikista otsikoista, joita
  ylipäätään voi syntyä.

- **Sääntöikkuna ei enää avaudu liian pieneksi sisällölleen.** Välilehdellä
  „Omat hakumallit" avustajan seliterivi („Etsitään: …") oli puoliksi
  kentän „Koeteksti" takana – juuri siinä lauseessa, jolla ilman
  säännöllisten lausekkeiden tuntemusta tarkistetaan, etsiikö oma sääntö
  oikeaa asiaa. Ikkunalla oli kiinteä vähimmäiskoko ajalta, jolloin
  välilehtiä oli vähemmän, ja se saattoi kutistua pienemmäksi kuin sen
  sisältö mahtui. Se mukautuu nyt sisältöönsä eikä käy pienemmäksi kuin
  se, missä kaikki pysyy luettavana.

- **Nimet taulukkokaavoissa eivät enää jää paikalleen.** Solussa on
  useampi kuin yksi paikka tekstille, ja tähän asti vain yksi niistä
  siivottiin. Jos kaavassa oli nimi – `="Rouva "&"Sieglinde Ortner"` – tai
  se oli kaavan viimeksi laskettu tulos, se pysyi muuttumattomana
  työkirjassa, vaikka sama henkilö vieressä olevassa solussa oli korvattu.
  Solua napsauttaessaan sen luki kaavarivillä.

  Molemmat korvataan nyt. Koskematta jätetään ainoastaan se, mikä ei ole
  lainausmerkkien sisällä: solunviittaukset, funktionimet ja taulukon nimet
  pysyvät koskemattomina, `=SUMME(K2:K6)` laskee edelleen. Koska sama nimi
  saa kaikkialla saman korvausmerkin, myös `=SUMMEWENN(A:A;"Huber";B:B)`
  löytää edelleen omat rivinsä.

- **Kaaviot eivät enää näytä nimiä.** Kaavio tallentaa oman kopionsa
  akseliotsikoistaan – se piirtää edelleen, vaikka lähdesolut olisivat jo
  kauan tyhjät. Palkkien alla oli siksi edelleen viisi henkilön nimeä,
  vaikka taulukko yläpuolella oli puhdas. Koskee sekä taulukoita **että**
  esityksiä.

- **Nimetyt alueet, joissa on kiinteä teksti, siivotaan.** Nimetty alue
  voi sisältää solunviittauksen sijaan kiinteän tekstin; jos siellä oli
  nimi, se pysyi. Alueen **nimi** pysyy edelleen paikallaan – siihen
  viittaavat kaavat, ja uudelleennimeäminen aiheuttaisi viittausvirheen.
  Kuten taulukon nimen kohdalla, siitä ilmoitetaan, sitä ei korvata.

- **Kerran tunnistettu syntymäaika katoaa koko asiakirjasta.** Yksittäinen
  päivämäärä ei sinänsä kerro mitään – vasta kenttäsana tekee siitä
  syntymäajan, ja juuri siksi laskun päivämäärä jää rauhaan. Jos sama
  tieto oli samassa asiakirjassa toisenkin kerran ilman tätä sanaa – kuvan
  otsikossa, täytetyssä lomakekentässä –, se jäi sinne, vaikka muutama
  rivi ylempänä „syntynyt …" oli tunnistettu kiistatta. Siirretään vain se,
  mikä on **tässä** asiakirjassa jo tunnistettu syntymäajaksi; arvausta ei
  edelleenkään tehdä.

- **Verkkosivujen jäsennelty tieto paljastaa syntymäajan.** Hakukoneiden
  JSON-LD-lohkossa päivämäärä on avaimen `birthDate` alla – avain kertoo,
  mistä on kyse, aivan kuten muuten sarakeotsikko. Se luetaan nyt mukaan;
  „Birthday" ja „Birthdate" katsotaan nyt kenttänimikkeiksi myös
  lomakkeissa.

- **Syntymäaika ja henkilönumero löytyvät nyt myös taulukoista.** Solussa
  on vain paljas arvo – `14.03.1988`. Sen merkityksen kertoo yksin
  sarakeotsikko, ja se on monta riviä ylempänä. Excelissä se luettiin jo
  mukaan; LibreOffice-taulukoissa ja CSV-tiedostoissa ei, ja siksi
  syntymäaika jäi niissä paikalleen.

  Molemmat lukevat otsikon nyt mukaan – **mutta vain, jos se itse on
  kenttänimike**. „Syntymäaika"-otsikon alla päivämäärä poistuu,
  „Laskun päivämäärä"- tai „Toimituspäivä"-otsikon alla ei. Tämä on
  tarkoituksellisesti varovainen tulkinta: otsikko kuten „Nimi" mielivaltaisen
  huomautuksen yläpuolella olisi jo kerran laittanut korvausmerkin lauseen
  päälle, jossa ei esiinny yhtäkään henkilöä.

### Korjattu

- **Puhdistettu CSV pysyy taulukkona.** Tunnistus lukee CSV-rivin lauseena
  ja on siksi jo kerran vetänyt löydöksensä puolipisteen ylitse.
  Korvausmerkki nieli erottimen, rivillä oli sen jälkeen yksi sarake
  vähemmän, eikä tiedostoa enää voinut avata taulukkona. Löydökset
  päättyvät nyt solun rajalle, ja maskauksen lainausmerkit pysyvät
  paikallaan. Vaikutuksen alaiset solut luetaan sen jälkeen vielä kerran
  erikseen – muuten viereinen solu jäisi puhdistamatta, koska liian
  pitkä osuma peitti sen.

- **Kommentit esityksissä.** Diaan liitetty reunahuomautus – usein juuri
  kohta, jossa lukee „Soita rouva …:lle ennen kokousta" – jäi
  koskemattomaksi, sen kirjoittajan nimi mukaan lukien. Excelissä molemmat
  oli jo siivottu; PowerPoint tallentaa kommenttitekstin ja kirjoittajan
  eri tavalla, ja se oli jäänyt huomaamatta. Koskee molempia rakenteita:
  vanhempaa ja sitä, jota PowerPoint on kirjoittanut vuodesta 2019 –
  jälkimmäisessä myös kirjoittajaan liittyvä työsähköpostiosoite. Myös
  PowerPointin puhekuplassa näkyvät nimikirjaimet poistetaan.

- **LibreOffice-tiedostot: kaava, käyttäjäkenttä, muistiinpanon
  kirjoittaja.** Se, mikä oli jo siivottu Excelissä, jäi ODS-taulukkoon –
  siellä kaava ei ole oma elementtinsä vaan solun ominaisuus, ja siinä
  oleva nimi säilyi. Seuraavalla avauskerralla LibreOffice laski sen taas
  esiin.

  Lisäksi kolme muuta kohtaa: OpenDocumentissa **käyttäjäkentän** arvo on
  kerran ylhäällä esittelyssä ja tekstissä vain haetaan sitä – korvattiin
  tähän asti vain haku, joten avattaessa palasi vanha arvo.
  **Muistiinpanon kirjoittaja** ja seurattavan muutoksen kirjoittaja
  jäivät paikalleen. Ja **taulukossa** muutosten seurantaa ei siivottu
  lainkaan – toisin kuin tekstiasiakirjassa –, joten poistetut solujen
  sisällöt säilyivät muokkaajan nimen kera. Solunviittaukset ja
  summakaavat pysyvät tällöin koskemattomina.

- **Tallennetut verkkosivut paljastavat ominaisuutensa.** Sivu ei näytä
  läheskään kaikkea, mitä se sisältää. Täytetty lomakekenttä kantaa
  syötteen `value`-kentässä, JavaScript-käyttöliittymä tallentaa
  tietueensa `data-…`-attribuuttiin, ja hakukoneille tarkoitettu lohko
  (JSON-LD) toistaa sen täydellisesti ja hyvin muotoiltuna: nimi,
  syntymäaika, osoite, puhelin. Näkyvä teksti oli puhdistettu, kaikki tuo
  seisoi silti siellä.

  Nyt myös nämä kohdat siivotaan, samoin `aria-…` (se, mitä
  ruudunlukija lukee ääneen), `placeholder`, `summary` ja linkin
  ehdotettu tiedostonimi. JSON-LD-lohko luetaan tällöin datana ja pysyy
  kelvollisena – sen avaimet ja sanasto säilyvät, vain arvot poistuvat.
  Tavalliseen JavaScriptiin ei edelleenkään kosketa.

- **Kuvat menettävät oheistietonsa myös ilman EXIF-tietoja.** Valokuvassa
  on usein kuvaajan nimi, kuvausaika ja kuvauspaikan GPS-koordinaatit
  liitettynä mukaan – asunto-ilmoituksessa tämä paljastaa osoitteen, vaikka
  tekstissä ei sellaista olisikaan. Tämä poistettiin, kunhan kuvassa oli
  EXIF-tietoja. Jos tiedot olivat **vain** XMP-muodossa (näin tallentavat
  Lightroom ja Photoshop) tai tekstilohkona PNG-tiedostossa (`Author`,
  `Comment`), kuva jäi täysin koskemattomaksi. Molemmat tunnistetaan ja
  poistetaan nyt – myös kuvista, jotka ovat osa asiakirjaa ja säilyvät
  siinä. Kuvan suunta säilyy edelleen, eikä kuvaa, jossa ei ole
  oheistietoja, tallenneta tarpeettomasti uudelleen.

- **Linkkikohteet taulukoissa, esityksissä ja Word-asiakirjoissa.** Se,
  mihin linkki johtaa, ei ole tekstissä vaan tiedoston omassa erillisessä
  säilössä. Sähköpostiosoite linkin „Lähetä sähköpostia" takana selvisi
  siksi puhdistuksesta vahingoittumattomana, vaikka sama osoite tekstissä
  oli korvattu. `mailto:`- ja `tel:`-linkit siivotaan nyt siellä samalla
  tavalla kuin tallennetuissa verkkosivuissa.

### Uutta

- **Lääkärinlausunnot eivät enää palaudu vaurioituneina.**
  Nimentunnistus piti tähän asti lääkeaineita henkilönniminä:
  „Metoprololsuccinatista" tuli `[NAME]`, „Ramiprilista" tuli `[ORT]`.
  Lääkityssuunnitelma oli sen jälkeen käyttökelvoton – kun taas diagnoosit
  jäivät koskemattomiksi, eli täysin väärin päin. Mitattuna tämä koski
  **63 % vaikuttavista aineista** ja **53 % kliinisistä ammattitermeistä**,
  eikä vain saksaksi: seitsemällä kielellä keskimäärin 74 %, italiaksi
  kaikki testatut.

  Maskuro tuntee nyt lääketieteellisen sanaston ja jättää sen rauhaan.
  Jäljelle jää 6 % 43 %:n sijaan (saksa) ja 1 % 74 %:n sijaan (kielten
  yli). Kun edessä on puhuttelu – „Hyvä Rouva …" –, nimi pysyy nimenä,
  vaikka se sattuisi kuulostamaan lääkeaineelta.

- **Sairaudet ja lääkkeet voidaan poistaa – jos niin halutaan.** Uusi
  valintaruutu asetuksissa: „Poista myös sairaudet ja lääkkeet"
  (komentorivillä: `--mit-diagnosen`). Henkilöstökansioita,
  irtisanomisia ja lausuntoja varten, joissa diagnoosi ei kuulu kenellekään.

  **Oletuksena pois päältä**, ja tarkoituksella: lääkärinlausunto
  *koostuu* diagnooseista ja vaikuttavista aineista. Kuka tahansa
  anonymisoi sellaisen – tutkimusta, koulutusta tai tekoälytyökalua
  varten – haluaa yleensä säilyttää juuri tämän sisällön ja päästä eroon
  vain siitä, kenestä on kyse. Diagnoosi on siinä hyötykuorma, ei
  henkilöllisyystodistus.

  Tunnistus löytää yleiset nimitykset eikä korvaa läpikäyntiä:
  sairausluettelo ei koskaan ole täydellinen, koska lääkäri kirjoittaa
  „C2-abusus", missä luokitus käyttää nimitystä „alkoholin aiheuttamat
  häiriöt".

- **Diagnoosi- ja lääkeavaimet löytyvät.** ICD-10 (`I48.2`), ATC
  (`A10BA02`) ja apteekin keskusnumero ovat terveystietoja siinä missä
  kirjoitettu diagnoosikin – lääkärinlausunnoissa ja
  laskutusasiakirjoissa jopa yleisempi muoto. Ne on oletuksena päällä,
  kuten muutkin GDPR:n 9 artiklan mukaiset erityiset kategoriat.

  Diagnoosiavain tunnistetaan vain, jos sillä on peruste: edessä sana
  „ICD" tai suluissa diagnoosirivin jälkeen. Ilman tätä ehtoa ohjelma
  pitäisi toimintonäppäintä **F10** riippuvuusdiagnoosina – luokituksessa
  F10 tarkoittaa juuri sitä.

- **Valmiin tiedoston voi nyt kopioida.** Jokaisella valmiilla rivillä on
  „Näytä", „Jälkikäsittele" ja „Näytä kansiossa" vieressä neljäs painike:
  **Kopioi**. Se asettaa puhdistetun tiedoston leikepöydälle – sieltä se
  siirtyy Ctrl+V:llä (Mac: ⌘V) sähköpostiin, keskusteluikkunaan tai
  tekoälytyökaluun ilman kiertotietä kansion kautta.

  Kopioitava on **tiedosto**, ei sen teksti: sivun asettelu, kuvat ja
  mustausraidat säilyvät siten. Luettelon kontekstivalikon kautta myös
  useampi valittu tulos siirtyy kerralla leikepöydälle, ja valikossa
  „Tiedosto" sama toiminto on nimellä **„Kopioi tulos"** niille, jotka
  käyttävät mieluummin näppäimistöä.

- **Maavalinta voi nyt seurata asiakirjaa.** Henkilöllisyys-, sosiaali-
  ja verotunnisteet vaihtelevat maittain, ja siihen asti se, mitä maita
  tarkistetaan, oli kiinteä koko istunnon ajaksi – johdettu käyttöliittymän
  kielestä. Kuka tahansa työskenteli saksaksi ja puhdisti ranskankielisen
  kirjeen, etsi siitä siis saksalaisia verotunnisteita eikä ranskalaista
  sosiaaliturvatunnusta.

  Sääntöikkunassa on siksi nyt vaihtoehto **„Automaattisesti asiakirjan
  kielen mukaan"**. Kiinteä valinta on edelleen vierellä, ja
  tarkoituksella: kielentunnistus ei ole erehtymätön – jos se tunnistaa
  väärin, väärä maavalinta astuu voimaan. Kuka tahansa käsittelee vain
  yhden maan asiakirjoja, on turvallisemmin liikkeellä kiinteällä
  luettelolla.

  Koskematta tästä jäävät **saksalaiset** mallit (verotunniste,
  rekisterikilpi, suuntanumero): ne riippuvat kielestä, ei maavalinnasta,
  ja toimivat edelleen myös silloin, kun lyhyt saksankielinen teksti
  luokitellaan englanniksi.

- **Salasanat, avaimet ja käyttäjätunnukset löytyvät nyt.** Kuka tahansa
  kopioi virheilmoituksen, lokin tai otteen asetustiedostosta
  tekoälyikkunaan, sisältää melkein aina käyttöoikeusavaimen – ja se jäi
  tähän asti muuttumattomana paikalleen.

  Molemmat tunnistetaan: yleiset avainmuodot, jotka puhuvat puolestaan
  (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`, JSON Web Token, yksityisen
  avaimen alku), ja otsikoitu muoto – „Salasana:", „API-Key =", „Token:",
  „Käyttäjätunnus:". Korvataan tällöin vain arvo, ei koskaan otsikkoa:
  „Salasana: [ZUGANGSDATEN_1]" pysyy luettavana, ja tuloksen tarkastaja
  näkee, että siinä oli salasana.

  Käyttäjätunnus ja salasana ovat kaksi erillistä lajia. Kuka tahansa
  haluaa poistaa vain salasanat, kytkee toisen pois ja pitää toisen.

- **Viiva- ja QR-koodit kuvissa tehdään tunnistamattomiksi.** Skannatussa
  päätöksessä on lähes aina koodi, ja siinä on sama asianumero, joka
  poistetaan vierestä tekstistä. Tähän asti koneellisesti luettava versio
  jäi paikalleen: palkki numeron päällä ei auta mitään, jos kaksi
  senttimetriä loitompana laite lukee sen sekunnissa.

  Tunnistetaan QR-koodi, Data Matrix, Aztec, Code 128, EAN ja muut
  yleiset muodot. Tunnistamattomaksi tekeminen tarkoittaa pikselöintiä,
  ja karkeampaa kuin kasvojen kohdalla: koodin virheenkorjaus palauttaa
  yllättävän paljon muutamasta säilyneestä kentästä, puolinainen huntu ei
  olisi poisto.

  Valinta on „Tee kasvot tunnistamattomiksi" -asetuksen vieressä ja
  samoin **oletuksena päällä**. Myös kytkettynä pois päältä raportti
  kertoo, kuinka monessa kuvassa on koodi – kasvon näkee selatessa,
  koodin pitää sivuseikkana.

- **Korttitarkistusnumero, PIN ja voimassaoloaika löytyvät.** Ohjelma
  löysi luottokorttinumeron jo aiemmin; vasta näiden kolmen vierellä
  olevan tiedon kanssa se on käyttökelpoinen, ja jokaisessa
  tiliotteessa ne ovat vierekkäin. Kaikki kolme tunnistetaan vain
  otsikkonsa takana – „123" yksinään on talonumero, sivunumero tai
  kappalemäärä.

- **Koordinaatit tekstissä löytyvät.** Kuvista Maskuro on jo poistanut
  kuvauspaikan; jos sama tieto oli tekstinä lausunnossa tai
  toimintakertomuksessa, se jäi paikalleen. Tunnistetaan
  desimaaliasteet ja astemuoto minuutteineen ja sekunteineen.
  Desimaaliasteilla lähellä täytyy olla sana kuten „Sijainti",
  „Löytöpaikka" tai „Koordinaatit" – muuten jokainen kahden desimaalin
  mittaussarja olisi paikkatieto.

- **Rahasummat voidaan nyt poistaa mukana.** Uusi valintaruutu „Poista
  myös rahasummat", oletuksena **pois päältä** kuten yllä olevat
  päivämäärät: sopimuksessa summa on sisältö, ja se, joka mustaa kaiken,
  ei suojele ketään. Palkkalaskelmassa, sovintoesityksessä tai
  tiliotteessa se on sen sijaan juuri se tieto, joka kertoo henkilöstä
  enemmän kuin vierellä oleva nimi — sen tietää vain se, jolla on
  asiakirja edessään.

  Summa tunnistetaan **vain valuuttamerkinnän kanssa**: „4.250,00"
  yksinään on kappalemäärä, vasta „4.250,00 EUR" on rahaa. Valuuttamerkki,
  lyhenne ja kirjoitettu nimi lasketaan mukaan, sekä edessä että
  perässä, myös kirjoitustapa „990,– CHF".

- **GDPR:n 9 artiklan mukaiset erityiset kategoriat tunnistetaan.**
  Uskonnollinen vakaumus, ammattiyhdistysjäsenyys, poliittinen
  vakaumus, terveystiedot – ja niiden lisäksi 10 artiklan mukaiset
  rikosoikeudelliset tiedot. Nämä ovat tietoja, joiden käsittelyn
  asetus periaatteessa **kieltää**; siksi ne ovat ainoana uutena ryhmänä
  oletuksena **päällä**. Kuka tahansa haluaa säilyttää ne, päättää siitä.

  Tunnistetaan muoto, jossa ne käytännössä esiintyvät: lomakekenttä
  henkilölomakkeella – „Uskontokunta: room.-kat.", „Ammattiyhdistys: ÖGB",
  „Vammaisuusaste: 50", „Rikosrekisteri: ei merkintöjä" –, sekä
  kaksoispisteellä vierellä että otsikolla yläpuolella, kuten täytetty
  lomake ne antaa.

  **Juoksevan tekstin osalta vastuu on tekoälytasolla.** „Hän on
  vuosia ollut aktiivinen ammattiyhdistyksessä" on sama tieto, eikä
  mikään hakumalli löydä sitä luotettavasti. Tekoälytaso etsii tästä
  versiosta lähtien nimenomaisesti myös näitä kategorioita; kuka
  tahansa tarvitsee juoksevan tekstin, kytkee sen päälle.

- **Henkilöominaisuudet ja ammatti – tiedot, jotka näyttävät kuka on
  kyseessä myös ilman nimeä.** Sukupuoli, siviilisääty, pituus,
  silmien ja hiusten väri poistetaan tästä versiosta lähtien; ammatti,
  tehtävä ja osasto halutessa, oman valintaruudun kautta („Poista myös
  ammatti ja osasto") tai `--mit-berufen`.

  **Miksi toinen on päällä ja toinen pois:** „Hankinnat-osaston
  johtaja" nimeää yrityksessä täsmälleen yhden henkilön, vaikka nimi
  vieressä olisi mustattu – lausunnossa tai irtisanomisessa se kuuluu
  poistaa. Henkilöstöluettelo sen sijaan *koostuu* ammattinimikkeistä;
  kuka tahansa poistaisi ne oletuksena, palauttaisi tyhjän lomakkeen.
  Kumpi tapaus on kyseessä, tietää vain se, jolla on asiakirja
  edessään. Yllä olevat ominaisuudet ovat lähes aina lomakekentissä,
  ovat harvinaisia eivätkä koskaan kanna sisältöä – ne eivät siis
  maksa mitään.

- **Vieraan tiedoston jälkitarkastus.** „Tiedosto → Tarkasta tiedosto …"
  lukee jo mustatun asiakirjan uudelleen ja ilmoittaa, mitä siinä on
  edelleen – ja **missä kohdassa**: sivu ja rivi, laji ja pituus. Sitä
  varten, että joku tarkastaa toisen työtä: asianajotoimiston kansio,
  viranomaisen vastaus, oma lähtevä posti ennen lähetystä.

  **Itse arvo ei näy raportissa.** Kuka tahansa avaa kohdan, näkee sen
  joka tapauksessa – ja raportti voidaan siksi tallentaa ja jakaa
  eteenpäin ilman, että se itse on henkilötietokokoelma.

  **Ja raportti kertoo aina, mitä se ei pystynyt näkemään.** Kuvia ei
  lueta; skannauksessa ilman tekstitasoa „ei löydöksiä" tarkoittaa
  *ei tarkastettu*, ei *puhdas*. Komentorivillä sen erottaa palautusarvo:
  `--nachpruefen` palauttaa 0, jos tarkastettu ja puhdas, 4 löydöksistä
  ja 5, jos ei tarkastettavissa. Näin lähtevä posti voidaan pysäyttää
  automaattisesti sen sijaan, että se päästettäisiin läpi.

- **Tarkastusraportti: yksi lehti jokaista puhdistusta kohti.**
  „Tiedosto → Tallenna tarkastusraportti …" – tai `--pruefbericht
  <kansio>` komentorivillä – kirjoittaa yksisivuisen PDF-tiedoston
  (vaihtoehtoisesti CSV tai teksti) ajon tiedoilla, löydetyillä lajeilla
  määrineen, kahdella tunnusluvulla ja tarkastusmerkinnällä. Kansiota
  ja valvontaa varten: tarkastusloki on pitävä todiste, mutta kukaan ei
  esitä JSON Lines -tiedostoa.

  **Uutta ovat kaksi lukua**, joita ei ennen näkynyt missään:
  *keskimääräinen luottamus* – kuinka varma tunnistus oli siitä, mitä
  se löysi – ja *maskausaste*, korvattujen merkkien osuus tekstistä.
  Molemmat esitetään rajoituksineen: luottamus **ei kerro mitään**
  huomaamatta jääneestä, ja sen vierellä lukee aina, kuinka moneen
  osumaan se ylipäätään perustuu; aste ei laske kuvia mukaan ja on
  liian korkea kuvitetussa asiakirjassa.

  **Löydösarvot eivät ole lehdellä** – sama rajoitus kuin lokissa ja
  hakuajossa. Alhaalla on kaksi riviä, jotka eivät tarkoita samaa:
  tarkistussumma osoittaa, että lehti on muuttumaton; lokirivi – vain
  käynnissä olevan lokin kanssa – viittaa **allekirjoitettuun** riviin,
  joka todistaa ajon. Vasta se osoittaa alkuperän.

- **„Kuinka varma se oli?" – tunnusluvut tuloksen kohdalla.** Painike
  „Tunnusluvut" tuloksen alla avaa sen, mitä ei ennen näkynyt missään:
  löydökset, sanat ja merkit, jakauma lajeittain palkkirivinä, sekä
  keskimääräinen luottamus ja maskausaste. Samat luvut kuin
  tarkastusraportissa, mutta heti ja ilman tulostetta.

  **Varaumansa kanssa samalla pinnalla:** luottamuksen vierellä lukee,
  kuinka moneen osumaan se perustuu, ja sen alla lause siitä, ettei se
  kerro **mitään** huomaamatta jääneestä. Prosenttiluku ilman tätä
  lausetta lukee kuin osumaosuus – ja se, joka ymmärtää sen niin, on
  huonommassa asemassa kuin ilman lukua.

  Laskenta tapahtuu vasta avattaessa: maskausasteen nimittäjä maksaa
  yhden lukukerran tiedostoa kohden, eikä sitä pidä maksaa sen, joka ei
  edes katso lukuja.

- **Omien hakumallien rakentaminen ilman yhdenkään kirjoittamista.**
  Välilehti „Omat hakumallit" opastaa nyt kolmessa vaiheessa: *Mitä
  etsitte? → Miltä tällainen tieto näyttää teillä? → Nimeäminen ja
  tallennus.* Kirjoitatte esimerkin – vaikkapa `KD-004711` –, ohjelma
  johtaa siitä säännön ja kirjoittaa sanoin, mitä se etsii. Esikatselu
  osumalaskurilla tarkistaa jokaisen näppäinpainalluksen kohdalla.

  **Säännöllinen lauseke ei näy tässä missään vaiheessa.** Osaaminen ei
  ollut ongelma: omia hakumalleja on ollut jo pitkään, mutta ne
  vaativat lausekkeen kuten `\bKD-\d{6}\b`, eikä sellaista kirjoita kukaan
  asianajotoimistossa tai henkilöstöosastolla. Kuka tahansa haluaa
  kirjoittaa sellaisen, avaa asiantuntijatilan.

  **Malliluettelo on uudelleen järjestetty:** kolmetoista korttia
  nimineen, selityksineen ja esimerkkiarvoineen, suodatettavissa
  luokkamerkeillä – talous, viranomaiset, yhteystiedot, henkilöstö,
  lääketiede.

  Ja jos johdettu malli tarttuu liian laajasti, ohjelma kertoo sen
  itse: pelkistä numeroista koostuva esimerkki osuu jokaiseen
  vuosilukuun ja jokaiseen summaan, eikä lauseketta lukemattomaksi
  osaava muuten huomaisi sitä.

- **Seitsemän merkkiä viidenkymmenenkuuden ruksin sijaan.** Uusi
  välilehti „Mitä etsitään" kokoaa kaikki tunnistettavat lajit seitsemään
  ryhmään – henkilö, yhteystiedot ja paikka, tunnisteet, talous,
  tekniikka, erityiset kategoriat, yritykset ja omat. Merkki kytkee
  ryhmänsä, „Kaikki päälle" ja „Kaikki pois" koko luettelon; alla
  jokainen laji on edelleen erikseen valittavissa.

  **Oletuksena kaikki on päällä, ja niin se pysyy.** Se, mikä täällä
  kytketään pois, jätetään kokonaan etsimättä – karkein toimenpide,
  jonka sääntöikkuna sallii, ja se vaikuttaa jokaiseen asiakirjaan.
  Siksi luettelon alla lukee koko ajan, kuinka moni laji on pois
  päältä, ja tallennetaan vain se, mikä on kytketty pois: uusi laji on
  siten päällä myös eiliseltä peräisin olevassa sääntötiedostossa sen
  sijaan, että se putoaisi hiljaa pois.

- **Kehyksen siirtäminen kaikille sivuille.** Jälkikäsittely-ikkunassa
  painike **Siirrä kaikille sivuille** ottaa viimeksi piirretyn kehyksen
  ja mustaa saman kohdan jokaisella muulla sivulla – kirjepäätä,
  alatunnistetta ja asianumerokenttää varten. Kahdeksankymmensivuisessa
  skannatussa kansiossa se muuttaa kaksikymmentä minuuttia kahdeksi.

  **„Sama kohta" tarkoittaa samaa *suhteellista* kohtaa arkilla.**
  Syöttölaitteesta tulevassa erässä on säännönmukaisesti sivu, joka on
  vaakasuunnassa, toinen on A3-kokoinen, kolmas on käännetty; absoluuttisesti
  siirretty suorakulmio osuisi silloin kirjepään viereen – ja näkisi
  palkin ja pitäisi asiaa hoidettuna.

  **Mustataan, ei korvata**, vaikka lähtökehys olisi ollut
  korvausmerkki: saman suorakulmion alla sivulla neljäkymmentä on jotain
  muuta kuin sivulla yksi, ja samannumeroinen korvausmerkki väittäisi
  yhtäläisyyttä, jota ei ole.

- **Merkintä mustausraidalla.** Asiakirjojen tarkastusoikeudessa jokaisen
  mustauksen vierelle merkitään, miksi mustattiin. Uusi kenttä
  **Merkintä raidalla** asetuksissa – tai `--balkenvermerk` – kirjoittaa
  lyhyen tekstin jokaiseen raitaan: „§ 203 StGB", „GDPR", „luottamuksellinen".
  Viranomaisen luovuttamassa asiakirjassa se tekee eron: vastaanottaja
  näkee syyn ilman pöytäkirjaa, jota hän ei muutenkaan koskaan saa.

  **Oletuksena tyhjä**, sillä merkintä on näkyvissä luovutetussa
  asiakirjassa ja on itsessään tieto – se kertoo vastaanottajalle,
  millä perusteella jotain pidätetään. Se vaikuttaa vain
  **mustaamisessa**; missä on korvausmerkki, siellä ei ole raitaa.
  Raidalla, joka on liian pieni luettavalle tekstille, se jää pois –
  lukukelvoton merkintä näyttää virheeltä.

- **Vapauttaminen ilman internetyhteyttä – nyt täydellinen.**
  Lisenssi-ikkunassa oli jo pidempään „Vapauta ilman internetiä": yllä
  mukaan otettava pyyntökoodi, alla kenttä vastauskoodille, joka
  palautuu. Kukaan ei kuitenkaan pystynyt vielä **antamaan** sitä –
  siihen tarkoitettu työkalu puuttui, ja koodi meni tyhjän päälle. Tämä
  on korjattu.

  Viranomaisille ja asianajotoimistoille, joilla on eristetyt koneet,
  tämä ei ole erikoistapaus vaan normaalitapaus – ja se on juuri se
  kohderyhmä, jolla lupaus „Asiakirjanne eivät koskaan poistu koneelta"
  painaa eniten. Koodi ei paljasta mitään asiakirjoista: se sisältää
  lisenssitunnuksen ja koneen tarkistesumman, ei muuta.

- **Skannerista nouto.** „Tiedosto → Nouda skannerista …" lukee pinon
  suoraan ja lisää sivut luetteloon – postihuoneelle ero yhden ja
  kahden työvaiheen välillä. Arkinsyöttölaite tyhjennetään viimeiseen
  sivuun asti; laitteen, tarkkuuden ja värin valitsee skannerin
  järjestelmävalintaikkuna, jonka jo tunnette.

  **Puhdistusta ei tehdä itsestään.** Näette ensin, mitä on tullut
  sisään, ja painatte sitten „Puhdista" kuten minkä tahansa muunkin
  tiedoston kohdalla – skannaus, joka menisi heti läpi, veisi teiltä
  näkymän vinosti syötettyyn pinoon.

  **Tämä on saatavilla vain Windowsissa**, ja valikkokohta sanoo sen
  myös Macilla: siellä skannerin ohjelmisto kirjoittaa kansioon, ja
  „Valvo kansiota …" puhdistaa kaiken, mikä sinne saapuu.

### Muuta

- **Kaikkien löydettyjen tietolajien luettelo on nyt mukana** ja luodaan
  lähdekoodista (`hilfe/GEFUNDENE-ANGABEN.md`): 177 lajia 35 maassa, 23
  niistä tarkistenumerolaskennalla. Se kertoo myös, miten on laskettu –
  me laskemme `[NAME]` kerran, kun toiset laskevat etu-, väli- ja
  sukunimen kolmena merkintänä.

- **Mustaaminen on nyt saatavilla myös Wordissa, PowerPointissa,
  OpenDocumentissa ja HTML:ssä.** Valinta korvausmerkin ja mustaamisen
  välillä oli tähän asti käytössä vain PDF-tiedostoissa. Nyt myös muut
  osaavat sen: löydös poistetaan, ja sen tilalle tulee musta raita –
  itse asiakirjaan, ei kuvana sen päälle. Tiedoston edelleen lähettävä
  antaa mustatun asiakirjan eikä sellaista, jossa mustattu on edelleen
  tekstinä alla.

  **Se päätetään erikseen**, kahdessa valintakentässä: „PDF:ssä" ja
  „Wordissa, PowerPointissa, OpenDocumentissa ja HTML:ssä." Sen halutaan
  olevan erilainen – mustattu PDF menee viranomaiselle, sama asia
  Word-tiedostona kulkee edelleen talon läpi ja sen halutaan pysyvän
  luettavana. Komentorivillä vastaavasti `--pdf-modus` ja
  `--office-modus`; aiempien versioiden tallennettu „Mustaus" koskee
  edelleen PDF:ää.

  Taulukoissa, pelkässä tekstissä, CSV:ssä ja sähköpostissa raita ei
  onnistu – siellä puuttuu pinta, jolle se voisi asettua. Korvausmerkki
  asetetaan edelleen, ja tulos **kertoo sen nyt**, sen sijaan että se
  tehtäisiin hiljaa.

- **Uutta: „Poista" – löydöskohta jää yksinkertaisesti tyhjäksi.** Kolmas
  toimintatapa korvausmerkin ja mustaamisen rinnalla, ja ainoa, joka
  toimii **jokaisessa** muodossa: jättäminen pois ei tarvitse pintaa.
  PDF:ssä ei piirretä mitään, Wordissa ja HTML:ssä kohta jää tyhjäksi,
  taulukossa samoin.

  Se on kolmesta hiljaisin: tuloksen lukija ei näe, että siellä
  koskaan oli jotain – edes arvon pituus ei enää paljasta itseään.
  Asiakirjassa, joka on tarkoitettu jonkun tarkastettavaksi,
  korvausmerkki pysyy yleensä parempana valintana.

  Kuvissa mikään kolmesta vaihtoehdosta ei päde: kuvapisteitä ei voi
  korvata korvausmerkillä eikä jättää pois. Se, mitä tekstintunnistus
  siellä löytää, maalataan edelleen aina peittoon.

- **Jälkikäsittely-ikkuna ei enää väitä korvauksia, joita ei ole.**
  Oikealla oli jokaisen arvon kohdalla korvausmerkki – myös mustatussa
  tiedostossa, jossa ei ole yhtäkään. Rivin napsautus ei merkinnyt
  mitään, ja „Peruuta" ei tehnyt mitään. Nyt siellä lukee „mustattu"
  tai „poistettu", eikä näitä rivejä voi edes yrittää perua: teksti on
  poissa, mitään ei ole palautettavissa. Tämä koski mustattuja
  PDF-tiedostoja, Wordia ja OpenDocumentia sekä kaikkea, mitä löytyi
  kuvista.

- **Tekstinäkymä näyttää raidat nyt raitoina.** Mustattu Word-tiedosto
  näytti jälkikäsittelyssä **tyhjältä**: mustatuissa kohdissa oli
  aukkoja, kuin ohjelma olisi niellyt tekstin. Syy oli näytössä, ei
  tuloksessa – itse asiakirjassa raita oli koko ajan oikein paikallaan.
  Nyt se näkyy myös näkymässä, mustana kuten tuloksessa, Wordissa,
  PowerPointissa, OpenDocumentissa ja HTML:ssä.

- **Outlook-viestit (`.msg`) puhdistetaan nyt.** `.eml` oli jo
  saatavilla – saksalaisissa yrityksissä Outlook on kuitenkin
  sähköposti, ja siellä tallennettu viesti on nimeltään `.msg`. Näin
  tiheimmin henkilötietoja sisältävä muoto on katettu myös
  yleisimmässä tallennusmuodossaan: otsikko, lähettäjä,
  vastaanottajarivit, viestiteksti, HTML-versio, vastaanottajaluettelo
  ja liitteet – jälkimmäiset olemassa olevien reittien kautta ja
  samoilla korvausmerkeillä kuin viestin teksti.

  **`.msg` sisältää saman tekstin useaan kertaan**, ja siinä on ansa:
  pelkkänä tekstinä, HTML:nä **ja** RTF:nä. Kuka tahansa puhdistaa
  vain pelkän tekstin, ei ole tehnyt mitään – Outlook näyttää
  ensisijaisesti RTF:n. RTF-versio poistetaan siksi kokonaan, samoin
  internetotsikot Received-ketjuineen ja binääriset hakuavaimet, jotka
  säilyttävät nimet ja osoitteet läpi jokaisen tekstin puhdistuksen.
  Tulos avautuu edelleen Outlookissa ja näyttää tekstin ilman
  kirjasinmuotoilua; raportti kertoo tämän nimenomaisesti.

- **Sääntöjen kuvaaminen omin sanoin regexin kirjoittamisen sijaan.**
  Sääntöikkuna osaa paljon ja vaati siihen säännöllisen lausekkeen –
  kohdan, johon useimmat pysähtyvät. Nyt riittää yksi lause: „Asianumeromme
  muotoa 12 C 345/26 tulee säilyttää." Tekoälytaso ehdottaa niistä
  termejä ja hakumalleja.

  **Käyttöön otetaan vain se, minkä ruksitte – ja oletuksena mikään ei
  ole ruksittu.** Jokaisen ehdotuksen kohdalla lukee lause siitä, mitä
  se tarkoittaa, ja sen osumamäärä esimerkkitekstissä, jonka voitte
  antaa mukaan. Se, mikä **poistaa** suojaa, on merkitty sellaiseksi:
  „poista tämä termi aina" ja „älä koskaan poista tätä termiä"
  näyttäisivät luettelossa muuten samalta. Ehdotuksia, jotka osuisivat
  kaikkeen, ei näytetä lainkaan.

- **Tarkastusloki laskee nyt yhteen kaikkien työasemien yli.** Jos talo
  tallentaa lokit `protokoll_pfad`-asetuksella jaettuun sijaintiin,
  jokainen työasema kirjoittaa oman kuukausitiedostonsa – tähän asti
  tietosuojavastaavan, jolla oli kolmekymmentä työasemaa, piti käydä
  läpi kolmekymmentä tiedostoa erikseen. Luettelon yläpuolella on nyt
  rivi kuukauden summilla, ja **se ilmoittaa katkenneista ketjuista
  nimillä**: jälkikäteinen muutos huomataan vain, jos joku tarkistaa,
  eikä kukaan tarkista kolmeakymmentä tiedostoa käsin.

  **Ei henkilökohtaista koontia** – ei tässäkään näkymässä.
  Järjestys „kuka on puhdistanut kuinka paljon" sopisi käyttäytymisen
  ja suorituksen valvontaan, ja juuri se ratkaisee
  yhteistoimintaoikeudellisesti, ei tarkoitus. Lasketaan ajot,
  tiedostot ja osumat koko talon yli.

- **„Ehdota profiilia asiakirjasta": sääntöjen kysyminen kerran
  neljänkymmenenneljän lajin läpikäymisen sijaan.** Sääntöikkunassa on
  uusi painike: se näyttää tekoälytasolle asiakirjan, päättää, mistä
  on kyse – lääkärinlausunto, työhakemus, sopimus, lasku, päätös – ja
  ehdottaa siihen sopivia strategioita. Lääkärinlausunnossa esimerkiksi
  päivämäärät siirretään korvaamisen sijaan, koska potilaskertomuksessa
  aikajärjestys on sisältöä.

  **Profiilit ovat ohjelmassa, malli vain valitsee** – mustaussäännöt
  eivät riipu siitä, mitä kielimalli pitää hyvänä ideana. Jokainen
  kohta ehdotetaan erikseen ja perusteltuna; mitään ei oteta käyttöön
  kysymättä, ja se, minkä olette itse määrittäneet, jää koskemattomaksi.
  Ilman tekoälytasoa pitäydytään turvallisessa oletuksessa: korvausmerkki
  kaikkeen.

- **Uusi strategia „keksi": uskottava väärä arvo korvausmerkin sijaan.**
  „Rouva Berger kirjoitti herra Dopplerille Fuldassa" sen sijaan, että
  „[NAME_1] kirjoitti [NAME_2]:lle [ORT_1]:ssa" – koulutusmateriaaleja,
  esittelykansioita, testitietokantoja ja kaikkea, mikä myöhemmin
  esitetään tekoälylle. Puhuttelu, lauserakenne ja luettavuus säilyvät.

  Sama arvo saa saman keksityn arvon kaikissa saman tapauksen
  tiedostoissa ja jokaisella koneella, jossa on sama sääntötiedosto –
  **ilman että vastaavuutta tallennetaan mihinkään** (sama mekanismi
  kuin tiivisteessä). Sähköpostiosoitteet sijaitsevat varatuilla
  esimerkkiverkkotunnuksilla, puhelinnumerot siihen varatulla alueella,
  keksityissä IBAN-tunnuksissa on oikein laskettu tarkiste. Mahdollista
  nimille, paikoille, osoitteille, yrityksille, sähköpostille,
  puhelimelle ja IBANille; muille lajeille sääntö hylätään, ei jää
  vaikutuksettomaksi.

  **Raportti kertoo nimenomaisesti, että on keksitty.** Näin puhdistettu
  asiakirja lukee kuin aito eikä ole sitä – se ei kelpaa todisteeksi
  eikä sitä saa luovuttaa alkuperäisenä.

- **Vastaprobe: „Kuka pysyy tunnistettavana?"** Uusi valintaruutu
  tekoälytason alla esittää **valmiin tuloksen** vielä kerran kielimallille
  ja kysyy, kuka on puhdistuksesta huolimatta tunnistettavissa.
  Tarkoitettu on tapaus, jota mikään tunnistus maailmassa ei löydä,
  koska siellä ei ole edes nimeä: „ainoa kätilö piirikunnassa",
  „työtoveri, joka irtisanoutui maaliskuussa tulipalon jälkeen". Mikään
  malli ei osu siihen, ja paikan päällä kaikki silti tietävät, kenestä
  on kyse.

  **Mitään ei poisteta tässä yhteydessä.** Kohdat näkyvät raportissa
  perustelulauseen kera, ja päätös tehdään käsin – ohjelma, joka omin
  päin poistaisi asiakirjasta lauseita, koska ne vaikuttavat sille
  paljastavilta, muuttaisi puhdistuksen uudelleenkirjoitukseksi,
  eikä kukaan näkisi, mitä puuttuu. Enintään viisi kohtaa tiedostoa
  kohden; mitä malli ei voi perustella sanatarkasti, jää pois.
  Komentorivillä: `--restrisiko` yhdessä `--ki`:n kanssa.

- **Paluutie tekoälystä: „Käännä vastaus takaisin".** Tähän asti
  rakennettu oli vasta puolet silmukasta – tekstin kopiointi,
  puhdistettu versio liitetään, esitetään tekoälylle. Vastaus palasi
  merkinnällä `[NAME_1]`, ja se, joka tarvitsi sitä, asetti käsin
  takaisin sen, minkä oli käsin poistanut. Nyt paluutie on valikossa
  „Ohjelma": kopioi vastaus, napsauta merkintää, oikeat nimet ovat
  jälleen paikallaan.

  Vastaavuus on siihen **vain työmuistissa**, koskee aina vain
  viimeksi puhdistettua kohtaa ja vanhenee tunnin kuluttua; kuka
  tahansa kytkee leikepöydän vahdin pois, menettää sen välittömästi.
  Takaisin voidaan hakea vain se, mikä korvattiin – mustattua,
  maskattua ja tiivistettyä ei voi kääntää takaisin, ja ohjelma kertoo,
  kuinka monta kohtaa se siksi joutui jättämään paikalleen. Hallinnoidut
  asennukset kytkevät paluutien kokonaan pois asetuksella `rueckweg`.

- **Kansion valvonta: mitä sinne laitetaan, on hetken kuluttua
  puhdistettuna lähtökansiossa.** Postihuoneelle, postilaatikkotiimille tai
  skannauskansiolle – kertaalleen asetettuna kukaan ei enää klikkaa.
  Löytyy kohdasta „Tiedosto → Valvo kansiota …", komentorivillä
  `--wache <kansio>`.

  Alkuperäinen jää paikalleen, missä se oli; halutessa se siirtyy
  muuttumattomana alikansioon „Valmis", jolloin mitään ei koskaan
  ylikirjoiteta. Tiedostoon kosketaan vasta, kun se on valmiiksi
  kirjoitettu – vielä verkon yli kopioitava tiedosto luettaisiin muuten
  puolittain ja ilmoitettaisiin puhdistetuksi. Se, mikä menee pieleen,
  jää paikalleen ja ilmoitetaan, sen sijaan että sitä yritettäisiin
  loputtomiin uudelleen. Ja valvonta muistaa valmiiksi saadut ilman
  tiedostonimiä: se, mikä on saapumiskansiossa, paljastaa usein jo
  nimessä, mistä on kyse.

  **Kansion valvonta oman käyttäjäprofiilin ulkopuolella – esimerkiksi
  verkkoasemalla – edellyttää automaatiolisenssiä.** Kansio, johon
  useampi henkilö pääsee käsiksi, on palvelu eikä työasema; omassa
  profiilissa ja kokeiluajan aikana rajoitus ei koske.

### Korjattu

- **Asetukset olivat oikealta katkaistut.** Ikkuna avautui kiinteällä
  koolla, ja se riitti vain sille kirjasinkoolle, jolla kehitettiin:
  Macilla „Tarkista nyt", „Muuta …" ja niiden vieressä olevat ohjeet
  jäivät puoliksi näkymän ulkopuolelle. Se avautuu nyt niin leveänä
  kuin sen sivut tarvitsevat – jokaisella kielellä ja jokaisella
  kirjasinkoolla, rajoituksena vain näyttö.

- **„Tarkista nyt" vastaa nyt näkyvästi.** Tulos näkyi pääikkunan
  tilarivillä – eli asetusikkunan takana, josta kysyttiin. Kuka
  tahansa tarkisti, ei nähnyt mitään. Nyt vastaus tulee ilmoituksena
  asetusten päälle, ja jos uusi versio on saatavilla, se johtaa suoraan
  asentamiseen. Ohjelman käynnistyksessä se pysyy edelleen tilarivillä,
  eikä ikkuna avaudu kysymättä.

- **Kopioidut tiedostot eivät saapuneet Macilla leikepöydälle.**
  Puhdistettujen tiedostojen palauttaminen ilmoitti onnistumisesta,
  eikä silti asettanut mitään käyttökelpoista leikepöydälle –
  liittäminen ei tuottanut mitään. Vaikutuksen alla oli kaikki, mikä
  kirjoittaa tiedostoja leikepöydälle.

- **Ja leikepöydältä luettiin Macilla vain ensimmäinen tiedosto.** Kuka
  tahansa kopioi kolme tiedostoa Finderissa ja valitsi „Puhdista
  leikepöytä nyt", sai kaksi niistä takaisin puhdistamattomina – ilman
  että mikään olisi kertonut sitä. Nyt kaikki tulevat mukaan.

- **„Tarkasta tiedosto" ottaa nyt vastaan myös raahatut tiedostot** –
  kuten pääikkuna. Pudotettu lisätään mukaan sen sijaan, että
  nykyinen valinta hylättäisiin; saman tiedoston pudottaminen kahdesti
  ei muuta mitään, ja se, mitä ohjelma ei pysty lukemaan, ilmoitetaan
  sen sijaan että se niellään.

- **Ja ikkuna kertoo, että se odottaa teitä.** Se avautui tyhjällä
  laatikolla ja harmaalla painikkeella „Tarkasta" – se näyttää siltä,
  ettei mitään ole, ei siltä, että valinta puuttuu. Nyt siellä lukee
  „Ei tiedostoa vielä valittu – raahatkaa se tähän tai valitkaa alta
  kohdasta 'Valitse tiedostoja …'."

- **Pitkä ajo kertoo nyt, että se on käynnissä.** „Lisämalli
  tarkempaa tunnistusta varten latautuu – hetki …" jäi näkyviin niin
  kauan kuin tunnistus laski: 47 500 sanan tiedostossa siis
  kahdeksantoista minuuttia, vaikka lataus oli valmis yhdeksän sekunnin
  kuluttua. Se, joka näkee tämän, pitää ohjelmaa jumissa. Nyt sen
  jälkeen tulee „Tarkempi tunnistus käynnissä – tämä kestää pitkillä
  teksteillä muutaman minuutin", ja tilarivi laskee mukana: „Tarkempi
  tunnistus (7/312)". Ilmoitetaan mallin silmukasta – 250 sanan välein,
  eli noin kuuden sekunnin välein –, ei tekstilohkoittain: yksi
  tekstilohko voi sisältää kaksitoistatuhatta sanaa ja kestää minuutteja.

- **Keskeytetty ajo kertoo nyt, että se keskeytettiin.** Kuka tahansa
  painoi „Peruuta", luki sen jälkeen „0/1 tiedosto(a) puhdistettu." –
  oikein laskettu ja silti väärä tieto. Ilmoitus siitä, mihin
  tiedostoon se osui, ylikirjoitettiin samalla hetkellä
  laskentailmoituksella. Ja tiedostoluettelossa luki edelleen
  „käynnissä …", vaikka mikään ei enää ollut käynnissä; nyt siellä
  lukee „keskeytetty".

- **Tietosuojaa koskeva lause oli katkaistu.** „… ei pilveä, ei
  latausta. Lisää tieto s" – ohjelman käynnistysleveydellä lause
  päättyi kesken sanan. Se saa nyt koko leveyden.

- **Lisenssipalvelu pystyi kertomaan jotain, eikä kukaan kuunnellut.**
  Kun kaikki lisenssipaikat ovat varattuja, lisenssi on vanhentunut,
  avain on tuntematon tai lisenssihallinta palveluntarjoajalla on pois
  päältä, palvelu lähettää juuri sitä varten syyn – tarkoitus oli
  alusta asti, että se selitetään **kerran**. Sitä ei näytetty koskaan.
  Nyt ilmestyy ilmoitus, joka kertoo ensin, että ohjelma toimii edelleen
  muuttumattomana, ja sitten, mistä on kyse. Kerran syytä kohden: se,
  joka on sulkenut sen, ei näe sitä uudelleen päivittäisessä
  tarkistuksessa – kylläkin, jos syy muuttuu.

- **Kaupasta ostettu monipaikkalisenssi näytti „1 paikka".** Kauppa
  jakaa valmiiksi tehtyjä avaimia ja pitää ostetun paikkamäärän
  itsellään; näytettiin kuitenkin luku itse avaimesta, ja se on
  jokaisella varastoavaimella yksi paikka. Kuka tahansa oli ostanut
  kahdeksan paikkaa, luki „1 paikka" – ja toisesta kirjautuneesta
  koneesta lähtien näyttö oli punaisena tekstillä „Ota yhteyttä
  hallintoonne". Nyt pätee luku, jonka palvelu on viimeksi
  ilmoittanut; ilman vastausta pitäydytään avaimessa, eikä se koskaan
  ole pienempi kuin ostettu laajuus. Sama koskee lisäostoja ja
  jatkoja: ne muuttavat paikkamäärää palveluntarjoajalla, eivät
  avaintanne.

- **Oston jälkeen luki „Lisensoitu Maskuro Privatlizenz'lle".** Se ei
  ole nimi, vaan sijaisnimi, jonka alla avaimet valmistellaan – teidän
  nimenne ei voi olla siinä, koska avain allekirjoitetaan jo ennen
  ostoa. Sen sijaan, että teille näytettäisiin vieras nimi omananne,
  siellä lukee nyt yksinkertaisesti „Yksityislisenssi" ja
  paikkamäärä. Teille henkilökohtaisesti myönnetyssä lisenssissä
  nimenne pysyy siellä muuttumattomana.

- **Ohje-valikossa luki „Ohje _FAQ".** Ja-merkki oli muuttunut
  alaviivaksi, koska Qt tulkitsi sen näppäinkirjaimen merkiksi. Nyt
  siellä lukee „Ohje & FAQ".

- **Asetusikkuna jäi näkyviin, kun ohjelma katosi kuvakkeeseen** – ja
  myös silloin, kun pääikkuna suljettiin. Se seuraa nyt mukana.
  (Koskee vain tätä versiota; itse ikkuna on uusi.)

- **Hylätty lisenssipyyntö kertoo nyt, mistä on kyse.** Jos
  lisenssipalvelu hylkäsi pyynnön ilman perustelua, lisenssi-ikkunassa
  luki punaisella „Tuntematon vastaus." – lause, jolla ette te ettekä
  tuki voi tehdä mitään ja joka johtaa etsimään virhettä avaimestanne.
  Nyt siellä lukee, mitä todella tapahtui: että palvelu hylkäsi
  ilman perustelua, ja kenen puoleen kääntyä. Jos lisenssihallinta
  palveluntarjoajalla on tilapäisesti pois päältä, myös se nimetään –
  koska avaimenne ei ole siitä vaikutuksen alainen.

- **Macilla asennetut kielet katsottiin yhtäkkiä puuttuviksi.**
  Käynnistyksessä ohjelma ilmoitti „Yhtäkään kielimallia ei ole
  asennettu" ja tarjosi ensiasennusta, vaikka kielet olivat jo
  ladattuina – kuka tahansa katsoi kohdasta „Asiakirjojen kielet",
  löysi ne sieltä täysilukuisina. Ohjelma etsi niitä
  käynnistystavasta riippuen kahdesta eri paikasta: käynnistettynä
  Ohjelmat-kansiosta se löysi ne; käynnistettynä samana rakenteena
  tavallisena kansiona se etsi niitä viereltään, missä niitä ei ole.
  Macilla käytetään nyt poikkeuksetta samaa paikkaa
  käyttäjäprofiilissa riippumatta siitä, miten ohjelma on pakattu.
  Mitään ei tarvitse ladata uudelleen.

- **„Mikä on uutta" näytti puolikkaan luettelon.** Ikkuna
  päivityksen jälkeen katkesi kesken lauseen, ja loput kohdat jäivät
  tyhjinä luettelomerkkeinä. Syynä oli kulmasuluissa oleva
  korvausmerkki – esimerkiksi `<tiedosto>.docx` –, jonka näyttö
  tulkitsi merkinnäksi ja hylkäsi kaiken sen jälkeisen. Nimenomaan
  turvallisuuteen liittyvät uutuudet olivat tästä vaikutuksen alaisia.
  Ohje on aina näyttänyt tällaiset korvausmerkit oikein; tämä ikkuna
  tekee sen nyt myös.

- **Kahden sormen nipistys zoomaa nyt jälkikäsittely-ikkunassa.**
  Kosketuslevyllä se on *se* zoomauseleistä – editorissa se ei ennen
  tehnyt mitään, ja se, joka halusi katsoa kohtaa tarkemmin, joutui
  liukusäätimen tai Ctrl+hiirenrullan luo. Sivu seuraa elettä
  välittömästi ja piirretään taas tarkkana päästettäessä irti.

- **Zoomaus kohdistuu paikkaan, jota katsotaan.** Nipistys suurentaa
  sormien välisen pisteen ympärille, Ctrl+hiirenrulla osoittimen
  alla olevan pisteen ympärille. Painikkeet, näppäinoikotiet ja
  liukusäädin pitävät keskikohdan kiinni – niihin ei liity osoitettua
  kohtaa. Ennen kaikilla näillä pysyi vain vieritysarvo paikallaan:
  sovitetusta sivusta katsottuna se piti yläreunan, ja kaikki sen
  alapuolella siirtyi kuvan ulkopuolelle sisäänpäin zoomatessa.

- **„Ennen/jälkeen" oli sivunäkymässä kuollut painike.** Niin kauan
  kuin sivunäkymä oli päällä, sitä pystyi painamaan – ja se ilmoitti
  joka kerta, ettei alkuperäistä voitu avata. Vertailtavaa ei siellä
  ole muutenkaan: sivunäkymä on kuva puhdistetusta versiosta,
  vastinparia alkuperäiselle ei ole. Painike on nyt lukittu ja kertoo
  hiirtä viedessä syyn ja ratkaisun (tekstinäkymä). Sen kuvaus lupasi
  lisäksi nimenomaisesti, että vertailu toimii „riippumatta siitä, onko
  teksti- vai sivunäkymä käytössä" – tämä ei koskaan pitänyt paikkaansa.

- **Sivunäkymä kaatoi LibreOfficen.** Jos kaksi sivunäkymää luotiin
  samanaikaisesti – esimerkiksi „Mustaa PDF:nä" esikatselun vielä
  laskiessa –, järjestelmä ilmoitti LibreOffice-kaatumisesta, vaikka
  sivut lopulta kuitenkin ilmestyivät: molemmat ajot käyttivät samaa
  LibreOfficen työtilaa, mitä se ei kestä. Nyt vain yksi ajo saa sen
  kerrallaan; muut siirtyvät omaan tilaansa. Ne tarvitsevat siihen
  muutaman sekunnin lisää, mutta virheilmoitusta ei enää tule, eikä
  yksikään ajo jää ilman tulosta. Toista renderöintitehtävää käynnissä
  olevan vieressä ei myöskään enää oteta vastaan lainkaan.

- **„Näytä alkuperäinen" saattoi sulkea ohjelman.** Jos alkuperäistä
  ei voitu avata – koska se oli siirretty, nimetty uudelleen,
  salasanalla suojattu tai eri asemalla –, jälkikäsittely-ikkuna
  keskeytyi ilman varoitusta, ja avoimet työkopiot menetettiin. Nyt
  ilmestyy huomautus, kytkin palautuu takaisin, ja puhdistettu versio
  jää näkyviin. Missä alkuperäinen ei periaatteessa sovi vierelle –
  esimerkiksi Word-tiedostosta syntyneessä PDF-sivunäkymässä – kytkin
  on alusta lähtien lukittu ja kertoo syyn hiirtä viedessä, sen sijaan
  että se näyttäisi saman huomautuksen joka painalluksella.

- **Virheraportit eivät koskaan tulleet perille.** Kuka tahansa
  yritti ilmoittaa virheestä, sai „Vastapuoli hylkäsi raportin" –
  eikä kukaan ollut koskaan nähnyt sitä. Kaksi syytä, molemmat
  matkalla: ohjelma ei tunnistautunut palvelimelle ja hylättiin siksi
  massakäyttösuojauksen toimesta, ja osoite viittasi toiseen nimeen,
  jota ohjelma ei seurannut. Molemmat on korjattu; raportti lähtee
  taas ulos. **Sama koski lisenssin vapautusta**: kirjautuminen,
  uloskirjautuminen ja kyselyt eivät myöskään tavoittaneet palvelua –
  siellä vain huomaamattomasti, koska vastaamaton pyyntö
  tarkoituksella ei muuta lisenssiänne. Ja jos hylkäys jää
  selittämättömäksi, sen tekninen numero näkyy nyt mukana, sen sijaan
  että jokainen syy näyttäisi samalta.

- **Painallus „Näytä alkuperäinen" saattoi sulkea ohjelman.** Jos
  alkuperäistä ei voitu avata – siirretty, nimetty uudelleen, eri
  verkkoasemalla, salasanalla suojattu tai vaurioitunut –,
  jälkikäsittely-ikkuna katosi kaikkine avoimine työkopioineen. Nyt
  vaihtokytkin pysyy puhdistetussa versiossa, ja ruutu kertoo, mistä on
  kyse; tekninen syy on tiedoissa, jos haluatte ilmoittaa siitä. Sama
  koskee tulosta, jota ei voida näyttää: ikkuna avautuu ja kertoo sen,
  sen sijaan että se katoaisi.

- **Kaatumiskysymys tuli liian usein – ja poisti jäljen, jota se
  kysyi.** Se ilmestyi myös silloin, kun mikään ei ollut kaatunut:
  merkintä syntyy heti, kun jossain esiintyy odottamaton häiriö,
  vaikka ohjelma selviäisi siitä ja sen jälkeen suljettaisiin ihan
  tavallisesti; sitä ei koskaan siivottu pois. Ja se, joka vastasi
  „Ei", tuhosi tapahtuman ainoat yksityiskohdat – merkintä katosi jo
  kysymyksen *näyttämisen* yhteydessä. Molemmat on korjattu:
  siisti lopetus siivoaa merkinnän pois, kysytään vain todellisesta
  keskeytyksestä, ja merkitään käsitellyksi vasta vastauksenne
  jälkeen. Yksityiskohdat ovat joka tapauksessa omalla koneella
  virhelokissa – se, joka ei halua lähettää mitään, ei silti menetä
  mitään. Lähetetään edelleen vain se, minkä olette etukäteen nähneet
  kokonaan ja itse hyväksyneet.

- **„Puhdista" saattoi jäädä hiljaa lukituksi.** Jos kielimallit
  jäivät jumiin latauksessa, painike pysyi pois päältä – ilman
  selitystä. Painallus ei tehnyt mitään, ja tilarivillä luki
  muuttumattomana „Kielimalleja ladataan …" vielä kymmenen minuutin
  jälkeenkin. Syy: taustaprosessien häiriöt menivät paikkaan, jota
  kukaan ei näe tiedostohallinnasta käynnistettäessä; jäljelle jäi
  ikkuna, joka näytti työvalmiilta eikä reagoinut mihinkään
  painallukseen. Nyt tällaiset häiriöt päätyvät virhelokiin,
  kielimallien lataus ilmoittaa epäonnistumisensa aina, sen sijaan
  että se luovuttaisi hiljaa, ja jos se silti jää hiljaiseksi,
  sovellus kertoo kolmen varttitunnin jälkeen, ettei jokin ole
  kunnossa, neuvon kera tiedoissa. Lukittu painike kertoo hiirtä
  viedessä syynsä. Pitkä ensimmäinen lataus ei tässä lasketa
  hiljaisuudeksi: niin kauan kuin edistymistä ilmoitetaan, tilanne
  pysyy rauhallisena. Kaatumiseksi mikään tästä ei lasketa: sovellus
  toimii edelleen, eikä seuraavassa käynnistyksessä siksi kysytä
  siitä.

- **Macilla ohjelma ei enää löytänyt päivityksiä – ja ilmoitti, että
  se on uusimmalla versiolla.** Mac-versiossa ei ollut mukana
  juurivarmenteiden hakemistoa; se etsi sitä paikasta, joka on
  olemassa vain koneella, jolla se rakennetaan. Näin se ei voinut
  tarkistaa keneltäkään palvelimelta, kenen kanssa se puhuu, ja
  katkaisi jokaisen yhteyden: ei päivityksiä, ei lisenssin
  vapauttamista, ei kielimallien latausta, ei virheraporttia.
  Vanhemmat versiot tekivät tästä hiljaa vastauksen „Käytössänne on
  uusin versio". Varmenteet ovat nyt itse ohjelmassa; jos se ei löydä
  niitä sieltä, se ottaa järjestelmän omat ja Macilla tarvittaessa
  avainnipun – ja jos niitäkään ei ole, se kertoo sen, sen sijaan
  että väittäisi olevansa uusin versio. Itse tarkistusta ei tässä
  koskaan kytketä pois.

  Tämän yhden päivityksen Mac-käyttäjien on vielä asennettava käsin:
  versio, joka ei tavoita palvelinta, ei voi myöskään päivittää
  itseään.

### Muutettu

- **Pääikkuna on siivottu.** Alhaalla oli kuusi samankokoista
  painiketta rinnakkain – „Tietoja …", „Käyttöopas" ja „Ohje & FAQ"
  niiden alla, vaikka samat kolme reittiä olivat jo Ohje-valikossa
  yläpuolella. Ne on nyt koottu yhdeksi painikkeeksi „Ohje", joka avaa
  ne auki; yksikään ei katoa. Alhaalle jää kaksi reittiä, joilla
  todella aloitetaan: „Puhdista" ja „Mustaa käsin …".

- **Se, mitä ohjelma juuri tekee, on nyt kiinteässä paikassa.**
  Ilmoitus („Kielimalleja ladataan …", „(3/7) kirje.pdf", „5/7
  tiedosto(a) puhdistettu.") roikkui tähän asti harmaana tekstinä
  kahden painikerivin välissä. Se on saanut oman pintansa, jonka
  edessä on värillinen piste: harmaa, kun mikään ei ole käynnissä,
  sininen työn aikana, vihreä sujuvan ajon jälkeen ja keltainen, kun
  huomautuksia on kertynyt. Piste ei kerro mitään, mitä ei lue
  vieressä – se vain kertoo sen nopeammin.

- **Asetuksista on tullut oma ikkuna.** Ne olivat aiemmin
  pääikkunassa – laatikko neljällä välilehdellä, joka avattiin
  kohdasta „Lisää asetuksia", ja joka oli sitten liian pieni
  sisällölleen: siinä oli aina vierityspalkki, ja valinta
  anonymisoinnin ja pseudonymisoinnin välillä oli puoliksi näkymän
  ulkopuolella. Painike on nyt nimeltään „Asetukset …" ja avaa
  ikkunan sivupalkilla; jokainen neljästä sivusta mahtuu kokonaan
  sisään. Pääikkuna ei enää hypähdä auki avattaessa, ja
  tiedostoluettelon näkee samalla vierestä. Muuttunut on vain se,
  missä asetukset sijaitsevat – mitä niitä on ja mitä ne tekevät, on
  ennallaan.

- **„Tiedot" avautuu esiin sen sijaan, että hyppäisi.** Ikkuna kasvoi
  tähän asti yhdessä kuvassa, ja sitä piti etsiä, mikä oli muuttunut.
  Nyt se liikkuu sinne.

- **Kirjasinkoot ja välit noudattavat koko ikkunassa samaa mittaa.**
  Otsikot olivat kahdessa kohdassa eri kokoisia, ja samanarvoiset
  rivit olivat eri etäisyyksillä toisistaan. Näkyvänä se on rauha, ei
  yksittäinen muutos.

- **Anonymisointi on nyt oletus.** Tähän asti oletuksena oli
  pseudonymisointi: samat henkilöt saivat saman numeron (`[NAME_1]`,
  `[NAME_2]`), viittaukset pysyivät luettavina – oikeudellisesti ne
  olivat silti **henkilötietoja**. Se, joka ei aseta mitään, saa nyt
  menetelmän, joka poistaa tiedot GDPR:n soveltamisalasta: kaikki
  saman lajin osumat ovat samanniminen (`[NAME]`). Numerointi on
  jäänyt valinnaksi, se on edelleen samassa ikkunassa; olemassa olevat
  asetukset pysyvät ennallaan. Komentorivillä `--pseudonymisieren`
  (myös `--mit-nummerierung`) palauttaa vanhan tavan.

- **Anonymisoituja korvausmerkkejä ei enää voi perua yksittäin.** Se,
  joka anonymisoi, saa jokaiselle henkilölle saman korvausmerkin – eikä
  siksi ole enää yksittäistä kohtaa, joka kuuluisi tiettyyn nimeen.
  Jälkikäsittely-ikkuna tarjosi silti „Peru korvaus": napsautus olisi
  asettanut *yhden* arvoista *kaikkiin* kohtiin. Rivit ovat nyt
  vaimennettuja kuten mustattujen tietojen kohdalla, napsautus kertoo
  syyn, eikä käsin jäljitetty löydös saa enää numeroa, jota ei muualla
  asiakirjassa ole.

  Samasta syystä anonymisoidun ajon jälkeen ei enää ole „Käännä
  vastaus takaisin" -toimintoa – aiemmin se olisi asettanut vieraan
  nimen jokaisen henkilön tilalle. Se, joka tarvitsee tätä silmukkaa,
  valitsee „Pseudonymisoi"; sovellus kertoo tämän nyt myös, sen sijaan
  että se viittaisi vanhentuneeseen vastaavuuteen.

  Komentorivillä `--zuordnung` keskeytyy nyt anonymisoinnin yhteydessä
  sen sijaan, että se kirjoittaisi tiedoston, joka ei ole
  takaisinkäännös – ikkunassa ruksi oli jo pitkään lukittu. Joko
  `--pseudonymisieren` mukaan tai `--zuordnung` pois; ilmoitus kertoo
  sen. Tulosta ei tällöin synny lainkaan, jotta skripti ei jäisi
  puolitehtyyn tulokseen.

- **Päivityskanava on nyt oletuksena „Vakaa".** Ilman omaa valintaa
  kanava määräytyi tähän asti siitä, mistä rakennuksesta käytössä
  ollut versio oli peräisin – se, joka kerran kokeili testiversiota,
  sai siitä lähtien pysyvästi tarjolle testiversioita. Kanavan vaihto
  on päätös ja pysyy sellaisena; oletus on siksi „Vakaa". Asetetut
  kanavat pysyvät koskemattomina.

### Parannettu

- **„Beschwerdevorgang" ei enää lasketa paikannimeksi.** Otsikossa
  „Muistio – Beschwerdevorgang 12 C 345/26" ohjelma mustasi myös
  tapauksen: kielimalli piti sitä paikkana ympäristöstä riippumatta.
  Mukaan on otettu ei yksittäinen sana vaan yhdyssanan **perusosa** –
  „vorgang" ja „notiz" kattavat siten myös liiketoiminta-, kirjaus- ja
  maksutapauksen tai puhelinmuistion. Kolmestakymmenestä testatusta
  hallinnollisesta termistä kolme aiheutti aiemmin väärän hälytyksen,
  nyt ei yksikään; edelleen löytyy kaikki, mikä on vierellä
  („Beschwerdevorgang: Bernd Meisinger" menettää nimen, ei otsikkoa).

- **Anonymisointi pitää nyt taas kirjaa – jälkikäsittelyä ja lokia
  varten.** Anonymisoivassa toimintatavassa ohjelma ei muistanut
  löydettyjä arvoja. Kaksi asiaa jäi siksi vaille: koko asiakirjan
  laajuinen johdonmukaisuustarkistus (sukunimi, joka esiintyy
  myöhemmin yksin, jäi paikalleen) ja korvausten luettelo
  tarkastuslokissa. Niin kauan kuin anonymisointi oli harvinaisempi
  valinta, tämä ei juuri näkynyt – oletuksena siitä olisi tullut
  yleistapaus. Asiakirjassa mikään ei muutu: korvausmerkki pysyy
  ilman numeroa.

- **„Ei henkilötietopäivämäärää" on nyt „ei henkilötietoa".**
  Peruutusvalintaikkunassa ja kasvovaroituksessa luki juridinen
  *Datum* – sanan „Daten" yksikkömuoto. Se luettiin
  kalenteripäiväksi, varsinkin kun sovellus toisaalla tarjoaa „Poista
  myös päivämäärät". Se on nyt kaikkialla „Angabe" (tieto), aivan
  kuten yllä olevat neljä perustetta samassa ikkunassa.

- **Alkuperärivi on nyt vain „Tietoja"-ikkunassa.** „Made with ♥ in
  Austria" oli pääikkunan alaosassa keskellä painikeriviä ja luki
  siellä kuin yksi painike lisää. Se on edelleen „Tietoja"-ikkunassa –
  siellä, mistä sitä etsitään.

- **Pudotuspinnalla on nyt näkyvä reuna.** Sen katkoviivareunus oli
  niin haalea, että se erottui ikkunasta tuskin lainkaan – se oli
  yhdentekevää, niin kauan kuin pinta oli vain pinta. Siitä lähtien,
  kun siitä tuli painike, johon pääsee sarkainnäppäimellä, tämä viiva
  on ainoa, mikä osoittaa sen käyttöelementiksi; se on siksi nostettu
  arvoon, jota standardi siihen vaatii.

## 0.10.22-beta.1 – 15. elokuuta 2026

### Uutta

- **Kun leikepöydän valvonta kytketään pois, se on todella pois.** Vahti
  pitää viimeisimmän sisällön muistissa, jotta alkuperäisen voi asettaa
  takaisin – aiemmin näin myös silloin, kun valvonta oli kytketty pois
  päältä. Nyt historia unohdetaan kytkettäessä pois. Tämä maksaa
  palautusmahdollisuuden pois kytkemisen jälkeen, ja juuri niin on
  tarkoitettu: pois päältä tarkoittaa pois päältä.
- **Virhepöytäkirja ei enää sisällä tiedostopolkuja.** Se sijaitsi vain
  omalla koneellasi eikä sitä koskaan lähetetty itsestään – mutta se
  kirjasi polut selkotekstinä, ja tiedostonimi paljastaa usein enemmän
  kuin sisältö. Merkinnästä „…/Scheidung_Mueller_Vergleich.docx” tulee
  kirjoitettaessa nyt `<tiedosto>.docx`; pääte säilyy, koska se on
  virheenjäljityksessä tärkeä. Sama koskee kaatumisen jälkeistä merkintää.
- **Korvausten luettelo varoittaa nyt itsessään.** Se on ainoa tiedosto,
  jossa alkuperäiset tietosi ovat selkotekstinä, ja se sijaitsee tuloksen
  vieressä – kansion eteenpäin luovuttava luovuttaa sen mukana. Nyt
  varoitus on tiedoston ensimmäisenä rivinä **tiedostossa itsessään**,
  tulostealue mainitsee koko polun pelkän tiedostonimen sijaan, ja
  komentorivillä tiedosto mainitaan ylipäätään ensimmäistä kertaa: siellä
  ei aiemmin edes tiennyt, että se on syntynyt.
- **Anonymisointi tai pseudonymisointi on nyt nimetty valinta.** Kohdassa
  oli aiemmin valintaruutu „Nimeä samat nimet samoin – tekoäly tunnistaa
  silloin edelleen, kuka on kuka”. Se kuvasi hyödyn ja vaikeni
  seurauksesta: juoksevasti numeroidut paikkamerkit (`[NAME_1]`,
  `[NAME_2]`) ovat **pseudonymisointia**, ja pseudonymisoitu tieto on
  edelleen henkilötietoa – joka luuli sillä anonymisoineensa, oli väärässä.
  Nyt kaksi menetelmää ovat rinnakkain, kumpikin hintoineen. Oletuksena
  pysyy pseudonymisointi, koska asiakirja, jota sen jälkeen vielä luetaan
  tai jota tekoäly käsittelee, tarvitsee viitteensä. Anonymisoitaessa
  korvausten luettelo on lukittu: se tekisi tuloksesta taas
  jäljitettävissä olevan. Käyttöohje ja UKK selittävät eron kaikissa 18
  kielessä; komentorivillä kytkin on nyt myös `--anonymisieren`.
- **Tallennusalueen yläpuolella oleva rivi kertoo nyt, mikä todella pitää
  paikkansa.** Se lupasi „100 % paikallinen käsittely – ilman pilveä ja
  tiliä, GDPR-ystävällinen”. Asiakirjojesi kohdalla tämä pitää paikkansa,
  ohjelman kohdalla ei näin yleisesti: se etsii päivityksiä, ilmoittaa
  pyydettäessä virheistä, lataa malleja jälkikäteen ja ilmoittaa ostetut
  työasemat. Nyt siellä lukee suppeampi ja kestävä väite: asiakirjasi
  eivät poistu koneelta.
- **Tuloksessa lukee nyt aina, että se on tarkistettava.** Aiemmin Maskuro
  ilmoitti sujuvan ajon jälkeen vihreällä „12 tieto(a) poistettu” eikä
  mitään muuta – tämä luetaan vakuutuksena siitä, että kaikki löytyi.
  Huomautuksia näkyi vain, jos jotain konkreettisesti ei voitu tarkistaa
  (kuvat, tuntemattomat liitteet). Nyt jokaisen tuloksen alla lukee
  huomiotta jätettävissä olevalla tavalla, ettei kaikkia henkilötietoja
  aina tunnisteta, että tarkistus on käyttäjän vastuulla ja että
  puuttuvat on täydennettävä käsin – ikkunassa, tulostealueella ja
  komentorivillä. Ei pois klikattavaa ilmoitusikkunaa: lause seisoo
  siellä pysyvästi. Pikaopas sanoo saman nyt samoin sanoin.
- **Päivityksen jälkeen käynnistyksessä lukee, mikä muuttui.** Aiemmin
  päivitys kulki läpi äänettömästi eikä sitä voinut erottaa
  uudelleenkäynnistyksestä. Nyt „Mikä on uutta” näkyy kerran – ja version
  ohittanut näkee myös välissä olleet muutokset. Ei aivan ensimmäisellä
  käynnistyksellä: siellä opastaa edelleen pikaopas.
- **Kiina ja japani löytävät nyt nimiä.** Aiemmin ne eivät löytäneet
  **yhtään** – ei vähän, ei ollenkaan. Molemmilta kielimalleilta puuttui
  sanasegmentointi, ilman jota lause ilman välilyöntejä lasketaan yhdeksi
  sanaksi; ohjelma vaihtoi hiljaa monikieliseen varamalliin. Molemmat
  kielet tunnistavat nyt henkilöt ja paikat kuten muutkin. Japanilainen
  sanakirja ladataan tällöin yhdessä kielen kanssa eikä sisälly ohjelmaan
  – se yksin painaisi noin 200 Mt, jotka muuten jokainen kantaisi mukanaan.
- **Romania on nyt valittavissa maana.** Se puuttui aiemmin kokonaan.
  Näin tunnistetaan romanialaiset osoitteet („Strada Victoriei 30”),
  postinumerot paikkakunnan kanssa („010061 București”) ja Cod Numeric
  Personal – viimeksi mainittu vain oikealla tarkistusnumerolla, jotta
  laskusta ei alleviivata jokaista kolmentoista numeron lukua.
  Aiempaan asti romanialaisissa asiakirjoissa postinumero jäi luettavaksi
  peitetyn paikannimen viereen.
- **„Rasteroi sivu” editorissa.** Jos tekstiä ei voida poistaa PDF:stä –
  tätä esiintyy vieraiden tuottajien tiedostoissa –, sivu voidaan nyt
  pyydettäessä korvata kuvallaan: teksti on silloin peruuttamattomasti
  poissa, sivu pysyy luettavana ja haettavana. Tapauksesta kertova
  varoitus tarjoaa askeleen suoraan painikkeena; kohdasta „Työkalut →
  Rasteroi sivu” sen saa myös itse käynnistettyä. Kumoaminen tuo sivun
  takaisin.
- **Käyttöliittymä on nyt saatavilla myös kroatiaksi, kreikaksi,
  liettuaksi, sloveeniksi, japaniksi ja koreaksi.** Näin kieliä on
  kahdeksantoista. Käyttöohje, UKK ja oikeudelliset tekstit ovat mukana
  täydellisinä kaikissa kuudessa. Puhdistetun asiakirjan merkinnät
  noudattavat tällöin käyttöliittymää – merkinnästä `[NAME_1]` tulee
  `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` tai `[氏名_1]`. **Kreikassa,
  japanissa ja koreassa merkinnät ovat latinalaisin kirjaimin** –
  `[ONOMA_1]`, `[SHIMEI_1]`, `[IREUM_1]`. Käyttöliittymä pysyy omassa
  kirjoitusjärjestelmässään; vain se, mikä kirjoitetaan asiakirjaan, on
  latinalaisin kirjaimin. Syynä on PDF:n merkistö: siellä kreikkalaiset ja
  japanilaiset merkinnät saapuivat aiemmin muodossa `[??_1]`, jolloin
  nimeä ei enää voinut erottaa paikasta.
- **Yhdeksän maata lisää, ja seitsemän olemassa olevaa täydentyy.** Uutena
  tunnistetaan henkilötodistus-, vero- ja sosiaaliturvatunnukset
  osoitteineen maille **Kroatia, Slovenia, Kreikka, Liettua, Pohjois-
  Makedonia, Venäjä, Ukraina, Kiina ja Japani**. Olemassa olevista maista
  on suljettu aukkoja, jotka painoivat enemmän: **Alankomailla** ja
  **Portugalilla** ei ollut aiemmin lainkaan henkilönumeroa – hollantilaista
  BSN:ää ja portugalilaista NIF:ää ei tunnistettu, vaikka ne ovat lähes
  jokaisessa näiden maiden asiakirjassa. Puola saa verotunnuksen NIP:n,
  Tanska, Norja ja Suomi omat osoitteensa, Kanada postinumeronsa. Näin
  maita on **35**.

### Poistettu

- **Linuxille ei toistaiseksi ole enää pakettia.** Lähdekoodi toimii
  siellä, mutta kolme asiaa, jotka tämä ohje lupaa, puuttuvat Linuxista:
  automaattinen käynnistys, globaalit pikanäppäimet ja – työympäristöstä
  riippuen – kuvake palkissa. Paketin toimittaminen, joka osaa vähemmän
  kuin kuvattu, olisi väärä ratkaisu. Windows ja macOS eivät koske tämä.

### Parannettu

- **Diaarinumerot löytyvät nyt kaikilla kielillä.** „Aktenzeichen
  12/2026-AB” poistettiin, „File reference 12/2026-AB” tai „Sygnatura
  12/2026-AB” jäivät paikoilleen: kenttäsanat, joista Maskuro tunnistaa
  tällaisen numeron, olivat vain saksaksi. Nyt se tuntee vastineet
  kahdellatoista kielellä – ja kuten ennenkin, vain numero korvataan,
  sitä edeltävä otsikko jää paikoilleen, jotta tuloksesta näkyy, mitä
  siitä poistettiin.
- **Maskuro käyttää joutokäynnillä noin puoli gigatavua vähemmän.**
  Käynnistettäessä ladattiin aiemmin myös tarkemman tunnistuksen
  lisämalli, jotta ensimmäinen puhdistus ei odottaisi sitä. Mitattuna
  tämä maksoi 648 Mt muistia ja säästi 1,9 sekuntia – ja se maksoi tämän
  myös silloin, kun ikkuna vain avataan ja suljetaan heti uudelleen.
  Malli ladataan nyt ensimmäisellä kerralla, kun sitä tarvitaan; tilarivi
  ilmoittaa siitä. Kielimalli ladataan edelleen käynnistyksessä – sen
  leikepöydän valvonta tarvitsee heti.
- **Tallennusaluetta voi nyt käyttää myös ilman hiirtä.** „Vedä tiedostot
  tähän” oli alue, joka reagoi klikkauksiin – näppäimistöllä sinne ei
  päässyt, ja ruudunlukija luki sen kehyksenä, jossa on tekstiä, ei
  sinä, mikä se on. Se on nyt painike: sarkainnäppäin hyppää siihen,
  väli- ja Enter-näppäin avaavat tiedostonvalinnan, ja kohdistuksen
  näkee reunasta. Valikon „Tiedosto → Valitse tiedostot” kautta se
  onnistui jo aiemminkin, mutta sen piti tietää.
- **Puhdistetun tiedoston nimi luetaan nyt myös ääneen.** Tiedostoluettelossa
  se on toinen, pienempi rivi alkuperäisen alla – mutta se oli aiemmin
  vain piirretty, ja ruudunlukija mainitsi vain alkuperäisen. Juuri tämä
  rivi on rakennettu torjumaan väärinkäsityksen, että ajo olisi ollut
  vaikutukseton, koska kansiossa on koskematon alkuperäinen. Rivi kuuluu
  nyt ääneen luettuna „rechnung.pdf, tulos: rechnung_puhdistettu.pdf”.
- **Ilman merkintää olevat käyttöelementit kertovat nyt, mitä varten ne
  ovat.** Tiedostoluettelon kuvakepainikkeet, jälkikäsittely-ikkunan
  piirtopainikkeet ja kaikki valinta- ja syöttökentät olivat
  ruudunlukijalle nimettömiä – ne ilmoitettiin „painikkeena” ja
  „yhdistelmäkenttänä”, ilman mistä. Rivin painikkeet mainitsevat samalla
  tiedoston: kahdenkymmenen rivin listalla muuten kuulisi kaksikymmentä
  kertaa saman lauseen.
- **Näppäimistöllä käyttävä näkee taas, missä hän on.** „Puhdista”-painike
  ja tiedostoluettelon kuvakepainikkeet on väritetty, minkä myötä
  kehys, jonka järjestelmä muuten piirtää kohdistetun elementin ympärille,
  loppui – tabulaattorilla eteneminen johti katseen tyhjyyteen. Molemmat
  saavat nyt oman kehyksensä heti, kun ne ovat vuorossa. Painikkeiden koko
  ei siinä muutu.
- **Seitsemän kirjasinväriä olivat liian vaaleita, molemmissa ulkoasuissa.**
  Mitattuna tavanomaisen normin (WCAG 2.1) mukaan vaaleat huomiorivit,
  tallennusalueen sivutekstit, ohjeen kohdat ja tummassa kuvassa lisäksi
  sininen ja punainen olivat rajan 4,5:1 alapuolella – luettavissa hyvässä
  valossa ja hyvällä silmällä, muuten ei. Kaikki on nostettu; asteikko
  säilyy, tekstit lukevat edelleen sivuteksteinä. Kolme muuta – värit,
  joilla varoitukset ja onnistuminen ilmoitetaan – pitivät rajan vain
  niukasti ja on nostettu mukana: joka ei lue niitä, ei lue tietoa siitä,
  meniko jokin pieleen. Näkyvästi muuttui tässä vain „Puhdista”-painike
  tummassa kuvassa: siinä on nyt tumma teksti valkoisen sijaan, kuten
  Windows 11:n korostuspainikkeissakin.
- **Jokaisella tiedostoluettelon rivillä on nyt oma rastinsa.** Aiemmin
  rivi piti ensin valita ja sitten klikata „Poista” – kaksi vaihetta
  pikkuasialle. Rasti on rivin oikealla puolella ja tarvitsee yhden.
  Sen alla ollut „Poista”-painike on siksi poistettu; useita rivejä
  kerralla poistaa haluava valitsee ne ja käyttää pikavalikon
  merkintää, joka myös kertoo, montako niitä on. „Poista kaikki” säilyy.
  Listasta poistetaan aina vain rivi – ei koskaan tiedosto levyltä.
- **Ennen tekoälytarkistusta lukee nyt, sopiiko tämä kone siihen.**
  Aiemmin ikkunassa luki vain, kuinka suuri malli on. Sen heikolla
  koneella kytkenyt huomasi vasta ensimmäisessä asiakirjassa, että se
  kestää hyvin kauan – 5,4 Gt:n latauksen jälkeen. Nyt ikkuna kertoo
  **etukäteen** muistin ja vapaan tilan ja sanoo, mitä se tarkoittaa;
  **jälkikäteen** nopeus mitataan ja ilmoitetaan siinä koossa, josta on
  kyse: „Kymmensivuinen asiakirja kestää tällä koneella noin 12
  minuuttia.” Jos se on liian hidasta, ohjelma neuvoo vastaan ja
  tarjoutuu kytkemään tason taas pois – mitään ei kielletä.
- **Nopeusmittaus toimii nyt jokaisella koneella.** Aiemmin se tuli vain,
  jos lisäksi asennettiin grafiikkakiihdytys – jota on saatavilla vain
  Windowsissa. Kaikilla muilla koneilla ohjelma arvioi keston siksi
  vieraan koneen perusteella, ja juuri siellä, missä se on hidas, arvio
  osui harhaan.
- **Turkkilaiset osoitteet löytyvät nyt myös skannauksesta.** Skannatussa
  kirjekuvassa „34710 İstanbul” jäi luettavaksi, vaikka sama tieto
  vieressä tekstinä katosi: tekstintunnistus lukee turkkilaisen İ-kirjaimen
  ilman sen pistettä, ja malli odotti isoa kirjainta. Sama koski
  „Bağdat Caddesi” -osoitetta.
- **Espanjalaiset osoitteet ilman omaa kadunnimeä löytyvät nyt.** „Gran
  Vía 5” jäi paikoilleen, koska malli odotti katutyypin jälkeen vielä
  nimisanaa – „Calle Mayor” -tyyppisessä sellainen on, „Gran Vía”:ssa
  tyyppi itse on jo nimi. Sama koskee nyt „La Rambla” ja „Castellana”
  -osoitteita.
- **Ikkunassa „Tietoja tästä ohjelmasta” lukee nyt läpinäkyvyysmerkintä**
  siitä, että sovellus on kehitetty tekoälyn avustuksella. Se koskee
  ohjelman syntyä, ei sen toimintatapaa: puhdistus tapahtuu edelleen
  yksinomaan omalla koneella.
- **„Hallitse kieliä” näyttää nyt käyttökelpoiset kielet ensin.** Puolelle
  48 kielestä ei ole omaa kielimallia; niissä monikielinen varamalli
  tunnistaa nimet vain heikosti, joissakin kirjoitusjärjestelmissä ei
  lainkaan. Vierekkäin listassa kaikki näyttivät samanarvoisilta.
  Oletuksena näytetään siksi enää vain kielet, joilla on oma malli – kohdasta
  „Näytetty” loput saa milloin tahansa näkyviin, lauseen kera siitä, mitä
  ne osaavat ja mitä eivät. Mitään ei katoa, ja rajoitetun kielen
  asettanut säilyttää sen.
- **Kysymys puuttuvasta kielestä kertoo nyt vaihtoehdon.** Kun
  tunnistetaan kieli, jolle ei ole vielä mitään asetettu, ohjelma tarjosi
  aiemmin vain „Lataa” tai „Jatka ilman”. Tunnistus voi kuitenkin osua
  väärin – lyhyissä lomakkeissa ja listoissa, joissa on vähän
  leipätekstiä, ratkaisevat vain harvat sanat. Ikkunassa lukee siksi nyt,
  että voi peruuttaa ja valita oikean kielen käsin sen sijaan, että
  käyttäisi kohtaa „Tunnista automaattisesti”. Tämä säästää epäselvässä
  tapauksessa satojen megatavujen latauksen kieleltä, jota ei edes
  tarvita.
- **Paikkamerkkien merkinnät puhuvat nyt käyttöliittymän kieltä.**
  „[NAME_1]”, „[ADRESSE_2]” ja muut olivat aiemmin aina saksaksi,
  riippumatta siitä, mikä kieli oli asetettu tai millä kielellä asiakirja
  on laadittu. Nyt ne noudattavat käyttöliittymän kieltä – englanniksi
  siis „[NAME_1]”, „[ADDRESS_2]”. Ei asiakirjan kieltä: se on
  „automaattisessa tunnistuksessa” arvattu ja joskus väärä; käyttöliittymän
  kieli ei koskaan.
- **Vähemmän kysymyksiä jälkikäsittelyssä.** Mihin tulos tallennetaan,
  näkyy nyt pysyvästi alarivissä („→ vertrag_puhdistettu.pdf”, kansio
  työkaluvihjeessä) – klikkaus siihen valitsee toisen sijainnin ilman,
  että tallennus tapahtuu heti. Kysymys ensimmäisellä tallennuksella
  jää siten pois. Kysymys „jo käsitelty – aloitetaanko alusta?” voidaan
  muistaa istunnon ajaksi, ja kaksi ilmoitusikkunaa, jotka antoivat vain
  tiedon, ovat nyt tilarivillä. Jäljelle jäivät kysymykset, jotka estävät
  peruuttamattoman vahingon: tallentamaton työ suljettaessa ja varoitus
  poistamattomasta tekstistä.
- **Tulos kertoo nyt, missä itse skannaus ei ollut luettavissa.**
  Skannatussa asiakirjassa laitteen tekstintunnistus ei lue kaikkea
  oikein – merkinnästä „Solarstraße 9” tulee tällöin esimerkiksi
  „Solaret^aß« B”. Sellaista, mikä on näin väärin luettu, mikään
  tarkistus ei enää löydä: se näyttää jokaiselle hakumallille
  kirjainsopalta. Ohjelma ei voi asialle mitään, mutta nimeää nyt tällaiset
  kohdat sivunumeroineen – yleensä siellä on leimoja, kirjekuvia tai
  käsin lisättyjä huomautuksia. Huomautus, ei varoitus: koneella
  kirjoitetussa asiakirjassa sitä ei näy.
- **Tiedostoluettelo näyttää nyt, mikä tuloksen nimi on.** Tiedostonimen
  alla lukee ajon jälkeen puhdistetun tiedoston nimi
  („→ vertrag_puhdistettu.pdf”). Aiemmin se näkyi vain pöytäkirjassa kohdan
  „Yksityiskohdat” takana, ja kansiosta katsonut löysi koskemattoman
  alkuperäisen. Lähteen nimi jää paikoilleen – muuten ei enää näkyisi,
  mistä tiedostosta tulos on peräisin.
- **Valmiin rivin painikkeet ovat nyt suurempia ja selvempiä.**
  Katselu, jälkikäsittely ja „Näytä kansiossa” olivat litteitä kuvakkeita
  ilman pinta-alaa ja hukkuivat listaan – vaikka juuri ne ovat ajon
  jälkeen ainoa asia, jota vielä klikataan.

### Korjattu

- **Vieraskielisessä käyttöliittymässä omat säännöt peittämisestä,
  naamioinnista ja tiivisteestä ohitettiin äänettömästi.** Nimien
  peittämisen korvaamisen sijaan määrittänyt sai ne silti korvattuina –
  heti kun ohjelmaa ei käytetty saksaksi tai englanniksi. Asetus oli
  paikallaan, se vain ei vaikuttanut, eikä tuloksesta näkynyt eroa. Tämä
  koski yhdeksää kahdestatoista käyttöliittymän kielestä.
- **Asetuksella „Merkintöjen kieli” ei ollut vaikutusta saksan ja
  englannin ulkopuolella.** „Saksa” ja „Englanti” olivat valittavissa,
  mutta asiakirjassa säilyi silti käyttöliittymän kieli. Nyt kaikki
  kolme vaihtoehtoa vaikuttavat; oletus „kuten käyttöliittymä” tuottaa
  ennallaan saman kuin ennenkin.
- **Lyhyissä tekstiotteissa nimet jäivät paikoilleen – esimerkiksi
  kopioidussa sähköpostilainauksessa.** Otteen leikepöydän kautta
  puhdistanut sai siinä usein vain sähköpostiosoitteen peitetyksi, nimen
  sen alta ei. Ratkaisevaa oli pelkkä rivimäärä: kuudesta rivistä
  lähtien ohjelma tunnisti otteen luetteloksi ja löysi nimet, sitä
  vähemmän ei – kopioidussa sähköpostilainauksessa on viisi. Mikä tahansa
  ylimääräinen rivi, vaikka aihe, kaatoi tuloksen. Nyt neljä riviä
  riittää, ja mittauksessa kaikki tarkistetut nimet katoavat kolmasosan
  sijaan. Pidempiin asiakirjoihin ja leipätekstiin tämä ei vaikuta.
- **Tekoälytarkistuksen grafiikkakiihdytys kytkeytyi aina taas pois
  päältä heti asennuksen jälkeen.** Asennuksen jälkeen ohjelma mittaa,
  onko grafiikka tällä koneella todella prosessoria nopeampi – tämä
  mittaus kuitenkin epäonnistui aina sanomatta siitä mitään, ja tulos
  „molemmat yhtä nopeita” päätyi prosessorin hyväksi. 65 Mt ladannut sai
  sen jälkeen vähemmän kuin ennen. Mittaus toimii nyt; jos se
  epäonnistuu, se ei enää muuta mitään.
- **Aika-arvio laski jokaisella koneella vieraalla nopeudella.** Se
  perustuu samaan mittaukseen; niin kauan kuin se ei toiminut, käytössä
  oli kehitystietokoneen arvo. „Noin kaksi minuuttia” saattoi siten
  hitaalla koneella tarkoittaa puolta tuntia.
- **Tekoälytaso toimii nyt uudella, selvästi paremmalla kielimallilla**
  (Qwen3.5-9B Qwen3-4B:n sijaan) eikä ole enää rajoitettu saksaan ja
  englantiin, vaan toimii kahdellatoista kielellä. Mitattuna
  tarkistuskorpuksella: yhtä monta löydettyä tietoa kuin ilman tasoa,
  mutta alle puolet aiemmasta turhista peitoista (75 → 31). Malli on
  suurempi (5,4 Gt:n sijaan 2,4 Gt) ja tarvitsee noin kaksinkertaisen
  laskenta-ajan; kytkettäessä se ladataan kerran, vanha samalla
  poistetaan.
- **Osoitteet ranskaksi, italiaksi, espanjaksi, portugaliksi, puolaksi,
  turkiksi ja ruotsiksi poistetaan nyt kokonaan.** Aiemmin niistä
  katosi vain kadun- ja paikannimi – talonnumero ja postinumero jäivät
  luettaviksi („[ORT_1] 28, 28013 [ORT_2]”). Näille kielille ei ollut
  omia osoitemalleja; ne on nyt täydennetty.
- **Kreikka ja korea eivät löytäneet lainkaan nimiä.** Kreikan kohdalla
  syynä oli varamalli – omalla mallilla, joka nyt voidaan ladata, nimet
  ja paikat tunnistetaan siististi. Korean kohdalla syynä oli ohjelma:
  se edellytti nimen alkavan isolla kirjaimella, ja hangulissa ei ole
  isoja kirjaimia. Tämä koski erityisesti lyhyitä yksiköitä –
  taulukkosoluja, lomakekenttiä, luettelomerkintöjä.
- **Kielimalli, jota ei voitu ladata, keskeytti puhdistuksen.**
  Virheilmoituksen sijaan käyttöön astuu nyt monikielinen malli, ja
  tulos huomauttaa, että käytössä oli heikompi tunnistus. Tämä koskee
  tällä hetkellä kiinaa ja japania, joiden mallit tarvitsevat
  sananjaon, joka ei vielä sisälly ohjelmaan.
- **Kieli, jolla oli oma malli, laskettiin asennetuksi heti, kun jokin
  muu oli ladattu.** Esimerkiksi turkin asettanut sai siinä sivussa
  monikielisen varamallin – ja kiina, japani, korea tai kreikka näkyivät
  sen jälkeen listassa rastitettuina ja „0 Mt”:na, vaikka niiden oma
  malli puuttui. Niitä ei sen vuoksi voinut koskaan ladata jälkikäteen,
  ja ne toimivat pysyvästi heikommalla varamallilla. Nyt lista näyttää
  todellisen tilanteen latauskoon kera.
- **Epäonnistunut tunnistustaso vaikeni.** Jos „Laajennettu tunnistus” tai
  „Maksimaalinen tunnistus (tekoäly)” oli kytketty, mutta mallia ei
  voitu suorittaa, ohjelma jatkoi toimintaansa ilman tasoa – ilman
  sanaakaan siitä. Tulos näytti samalta kuin mikä tahansa muu, ja kytkin
  pysyi asennossa „päällä”: perustason tulosta pidettiin siis parhaana
  saatavilla olevana. Tulos kertoo tästä nyt ja mainitsee molemmat –
  mitä ei tarkistettu ja miten malli voidaan ladata uudelleen. Tapaus ei
  ole harvinainen: joillakin koneilla tekoälytaso epäonnistuu
  latauksessa, jos grafiikkakiihdytys puuttuu.
- **Virhe lisämallin latauksessa keskeytti koko puhdistuksen.**
  „Laajennetussa tunnistuksessa” vain mallin arviointi oli suojattu, ei
  sen lukeminen – ja juuri siinä menee pieleen, jos tiedosto on
  vioittunut tai ei sovi koneelle. Virheilmoituksen sijaan käyttöön
  astuu nyt perustason tulos huomautuksineen.
- **Kieltä ei enää voinut poistaa – eikä siten myöskään ladata
  uudelleen.** Kohdassa „Hallitse kieliä” rastin poistanut ja muutoksen
  hyväksynyt luki „Saksa poistettu”, mutta näki rastin heti taas
  paikallaan. Syynä oli ohjelmakansion siirto: kaikkien käyttäjien
  asennuksessa kielimallit sijaitsevat kirjoitussuojattuina
  ohjelmakansiossa, ja ohjelma noutaa puuttuvat sieltä sen sijaan, että
  lataisi sadat megatavut uudelleen. Tämä siirto tapahtui jokaisella
  käytöllä – ja kopioi juuri poistetun kielen samalla kertaa takaisin.
  Se tapahtuu nyt vain kerran; jälkiladattuja kielimalleja tämä ei
  koske. Lisäksi ohjelma tarkistaa poistamisen jälkeen: mitä ei voitu
  poistaa, ilmoitetaan nyt epäonnistumisena eikä „poistettu”-tekstinä.
- **Kaikkien käyttäjien asennuksessa jälkiladattua ei voitu tallentaa.**
  Ohjelman kaikille käyttäjille asentanut on sen kohdassa „Ohjelmat”,
  eikä sinne saa kirjoittaa ilman valvojan oikeuksia. Kielimalleille oli
  jo pitkään olemassa vaihtoehtoinen sijainti, muulle ei:
  - **Sivunäkymä-komponentti** purettiin 290 Mt:n latauksen jälkeen
    ohjelmakansioon ja epäonnistui siellä – kertomatta syytä. Se sijaitsee
    nyt kielimallien vieressä, missä sen olisi pitänyt olla koko ajan.
  - **Grafiikkakiihdytys** ei voi väistää: se vaihtaa kirjastoja
    ohjelmassa itsessään. Sen sijaan että ensin ladattaisiin ja sitten
    epäonnistuttaisiin sanattomasti, ohjelma kertoo nyt etukäteen, ettei
    tämä onnistu tässä ja mitä se tarkoittaa – maksimaalinen tunnistus
    jatkuu, vain prosessorin kautta.
  - Mukana toimitettua **tekstintunnistuksen kieltä** ei voitu poistaa: se
    palautui välittömästi takaisin ohjelmakansiosta. Sama syy kuin
    kielimalleilla, sama korjaus.
  - Kieltä poistettaessa saatettiin poistaa **vieraan Tesseract-asennuksen
    kielidataa**. Nyt kosketetaan vain omaa kansiota.
  - Vaihtoehtoinen sijainti koski aiemmin vain Windowsia. Linux-arkisto
    kohteessa `/opt` kärsi samasta ongelmasta ilman samaa ratkaisua.
- **Jälkikäsittelyssä katosi kokonainen rivi, vaikka vain yksi sana oli
  kehystetty.** Jo puhdistetussa tiedostossa paikkamerkin peittänyt
  menetti rivin, jossa se oli: lauseesta „Sehr geehrte Frau Doktor
  [NAME_1]” ei jäänyt mitään – ja ilmoitus sanoi silti „yksi sana
  poistettu asiakirjasta”. Tämä koski jokaista tiedostoa, joka oli jo
  kertaalleen käynyt ohjelman läpi, siis juuri sitä tapausta, jota
  varten jälkikäsittely on olemassa. Muu teksti pysyy nyt paikoillaan,
  muuttumattomassa kohdassa.
- **„EMPLOYEES” nimiluettelon yläpuolella peitettiin itse.** Sama tapaus
  kuin „MITARBEITER” versiossa 0.10.19, vain englanniksi – siellä se oli
  jäänyt korjaamatta. Isoin kirjaimin kielimallilta puuttuu erottava
  tuntomerkki, ja otsikko seisoo pelkkien todellisten nimien
  yläpuolella. Sen alla olevat nimet löytyvät edelleen. Mukaan ei otettu
  sanaa „staff”: se on käytössä oleva sukunimi, ja merkintä veisi
  mukanaan jokaisen „John Staff”:n – sama punninta kuin aikoinaan
  sanalla „Arbeiter”.
- **Oikeudellinen muoto korvattiin toistamiseen.** Skannatussa
  kirjekuvassa kielimalli luki „GmbH”:n, osoitteen ja postinumeron
  **yhtenä** paikkana. Osoite ja postinumero leikkasivat sen jälkeen
  omat osansa irti, ja jäljelle jäi oikeudellinen muoto omana osumana:
  tuloksessa luki „[ORT_1] [ORT_2]”, missä tarkoitettiin „[ORT_1] GmbH”.
  Yrityksen nimi korvataan edelleen – vain paljas lisäys jää nyt
  paikoilleen, ja tulos lukee kuin kirjekuva eikä täytettävä aukkotehtävä.
- **Rajattua osumaa ei tarkistettu uudelleen.** Edellä olevan tapauksen
  syy, ja se ulottuu pidemmälle: suodattimet arvattuja osumia vastaan
  toimivat sillä, mitä tunnistimet **ilmoittavat** – ei sillä, mitä
  jää jäljelle päällekkäisyyden ratkaisun jälkeen. Kun pitkä osuma
  rajataan vahvemmalla tunnistimella, katkelma on eri teksti kuin
  arvioitu, eikä kukaan katsonut sitä enää uudelleen. Nyt katsoo.
- **„Käytössäsi on uusin versio” – vaikka tarkistusta ei voitu tehdä
  lainkaan.** Päivityskanavaksi „Esikatselu (Beta)” tai „Vakaa –
  suositeltu” asettanut sai tämän tiedon, vaikka näillä kanavilla ei
  ollut tähän mennessä julkaistu vielä mitään. Nyt ohjelma sanoo juuri
  näin – ja ehdottaa toisen kanavan valitsemista asetuksista.
- **Ikkunan sulkeminen latauksen aikana kaatoi säikeen.** Maskuron
  käynnistänyt ja ikkunan heti taas sulkenut, kielimallien latautuessa
  vielä, sai pöytäkirjaan virheraportin: latausprosessi ilmoittautui
  ikkunalle, jota ei enää ollut. Näkyviä seurauksia tästä ei ollut, mutta
  pöytäkirjassa luki kaatuminen, kun kyse oli vain siitä, että joku oli
  ohjelmaa nopeampi.
- **Tulos katsotaan nyt, ei vain lueta uudelleen.** Aiemmin sivua
  pidettiin puhtaana, kun arvo ei enää ollut tekstissä. Skannauksessa
  se ei ole todiste – siellä näkyvä teksti on kuva. Lopuksi tarkistetaan
  siksi, onko alue tuloksessa todella peitetty; jos siellä on yhä
  vaaleaa paperia, raportti sanoo sen nimenomaisesti sen sijaan, että
  ilmoittaisi „korvattu”.
- **Korvattu tieto jäi kuvaan näkyviin.** Jos arvo oli kuvassa –
  skannattu kirjekuva, leima, kokonainen skannattu sivu –, se poistettiin
  kyllä asiakirjan tekstistä, mutta oli edelleen **näkyvissä**: mitä
  ihminen lukee, on siellä kuvapisteitä. Raportti ilmoitti silti
  „korvattu”. Nyt alue peitetään kuvassa, riippumatta valitusta
  strategiasta, ja paikkamerkki näkyy vaaleana tällä pohjalla – rumaa,
  mutta rehellistä, ja kohdistus säilyy. Jos kuvamuotoa ei voida
  käsitellä, tulos sanoo sen nyt nimenomaisesti sen sijaan, että
  näyttäisi puhtaalta.
- **Skannauksessa paikkamerkki puuttui kokonaan.** Skannatun sivun
  tekstikerros piirretään näkymättömäksi, ja siihen lisätty paikkamerkki
  peri saman: asetettu, mutta ei näkyvissä. Löytökohdassa ei sen
  jälkeen ollut mitään.
- **Tekstintunnistus, joka ei lainkaan voinut käynnistyä, laskettiin
  onnistuneeksi.** Jos kielitiedosto puuttui tai tunnistusmoottori
  kaatui, raportti ilmoitti „Kuva(t) … tarkistettiin
  tekstintunnistuksella (0 löytökohtaa)” – siis tarkistus, jota ei
  koskaan tapahtunut. Skannauksessa tämä on ainoa tarkistus ylipäätään:
  sopimus luettavan osoitteen kanssa sivukuvassa laskettiin siten
  valmiiksi. Nyt raportti kertoo, ettei mitään tarkistettu, ja miksi.
- **Kielitiedostoa haettiin väärästä kansiosta.** Jos omassa kielikansiossa
  oli muita kieliä kuin asiakirjan, tunnistusmoottorille annettiin juuri
  tämä kansio ja se epäonnistui – vaikka sopiva kieli oli vieressä. Nyt
  haetaan **kieltä**, ei kansiota.
- **Varoitus poistamattomasta tekstistä neuvoi johonkin, mitä ei ole
  olemassa.** Se viittasi kohtaan „Peitä PDF:nä” – mutta se luo PDF-
  näkymän *Office*-tiedostoista eikä ole lainkaan saatavilla PDF:n
  kohdalla. Varoitusta noudattaa yrittänyt etsi turhaan. Nyt siellä on
  painike, joka hoitaa asian.
- **Editorissa palkit ja paikkamerkit päätyivät merkityn kohdan
  viereen.** Tämä koski jokaista PDF:ää, jossa rivi päättyy
  tavuviivaan ja sana jatkuu seuraavalla rivillä – skannauksissa tämä
  erityisen näkyvästi, koska sopimustekstit ovat läpi tavutettuja.
  Rivin kaksi puolikasta laskettiin *yhdeksi* sanaksi, joka ulottuu
  poikki tekstialueen, ja jokainen sen lähellä oleva kehys peri tämän
  laajuuden. Itse tunnistus ei tästä muutu: mittauskorpus antaa saman
  tuloksen kuin ennenkin.
- **Editori varoitti tekstin olevan „edelleen asiakirjassa”, vaikka se
  oli poistettu.** Jos sama sana esiintyi sivulla useasti – sopimuksissa
  sääntönä –, itsetarkistus ilmoitti jokaisen toimenpiteen jälkeen
  epäonnistumisen. Se laskee nyt esiintymät sen sijaan, että vain
  katsoisi, seisooko sana vielä jossain. Todellisesta epäonnistumisesta
  se varoittaa ennallaan.
- **Tulostiedosto oli jokaisella kielellä nimeltään „_bereinigt”.**
  Tarkoituksena oli aina, että nimen lisäosa noudattaa
  käyttöliittymän kieltä – englanniksi näin myös tapahtui („_cleaned”),
  muissa kuudessatoista kielessä ei. Ohjelmaa suomeksi käyttänyt sai
  „asiakirja_bereinigt.pdf”. Nyt tiedosto on nimeltään
  „asiakirja_puhdistettu.pdf”, japaniksi „書類_除去済み.pdf” ja niin
  edelleen – kussakin sillä sanalla, jota sama käyttöliittymä käyttää
  valmiiksi-ilmoituksessaan. Oman lisäosan asettanut säilyttää sen.
- **„Hallitse kieliä” oli merkinnöiltään aina saksankielinen.** 48
  asiakirjakielen listassa olivat saksankieliset nimet, riippumatta
  siitä, mikä käyttöliittymä oli asetettu: suomalainen käyttäjä luki
  „Chinesisch”. Nyt siellä on nimi omalla kielellä ja sen perässä
  omakielinen nimi – „Kiina (中文)”. Omakielinen nimi on tarkoituksellinen:
  kielen omasta nimestään tunnistava löytää sen myös silloin, kun
  suomenkielinen sana ei sano hänelle mitään.

## 0.10.19 – 12. elokuuta 2026

### Parannettu

- **Pikavalikon merkintä puhuu nyt omaa kieltäsi.** Aiemmin siellä luki
  jokaisessa järjestelmässä saksankielinen teksti – jopa englanninkielisessä
  Windowsissa. Nyt se noudattaa asetettua käyttöliittymän kieltä, ja kieltä
  vaihdettaessa merkintä nimetään heti uudelleen ilman uudelleenasennusta.
  (Windows; macOS:ssä ja Linuxissa valikon nimi on samalla tiedostonimi –
  se tulee myöhemmin.)
- **Editori muistaa, missä näkymässä viimeksi työskentelit.** Sivunäkymää
  käyttävä saa sen seuraavaan asiakirjaan itsestään – ilman että sitä
  tarvitsee kytkeä päälle joka kerta. Sitä koskaan käyttämätön ei huomaa
  mitään: se palautetaan vain, jos tarvittava rakenneosa on jo ladattu,
  eikä sitä koskaan ladata tätä varten jälkikäteen.

### Korjattu

- **„MITARBEITER" (TYÖNTEKIJÄ) nimiluettelon yläpuolella peitettiin itse.**
  Työntekijähakemistoissa ja organisaatiokaavioissa otsikko katosi
  oletettuna nimenä – se seisoo siellä pelkkien todellisten nimien
  yläpuolella, ja isoin kirjaimin kielimallilta puuttuu erottava tuntomerkki.
  Sen alla olevat nimet löytyvät edelleen.
- **Määrätietoja pidettiin osoitteina.** Laskuissa, lähetteissä ja
  varastolistoissa katosivat tiedot kuten „3390 Protokoll", „1030 Betrag"
  tai „3390 Lager" oletettuna postinumerona ja paikkakuntana –
  nelinumeroisena mikä tahansa määrä näyttää itävaltalaiselta postinumerolta.
  Jos luvun jälkeen tulee sana, jonka sovellus tunnistaa asiasanaksi,
  osastoksi, toiminnoksi tai kenttäotsikoksi, se jää nyt paikoilleen. Todelliset
  paikkakuntatiedot pysyvät koskemattomina, myös sellaiset, jotka ovat
  samalla tällainen sana („4692 Ort"). Ratkaisematta jää se tapaus, että
  luvun jälkeen tulee aivan tavallinen sana („3390 Regal") – siihen
  tarvitaan postinumeroluettelo.
- **Ohje mainitsi valikkokohdan, jota ei ole olemassa.** Käyttöohje, kuva ja
  asennuksen lopussa näkyvä ilmoitus puhuivat „Asiakirjan puhdistaminen
  tekoälyä varten" -toiminnosta; pikavalikon merkintä on kuitenkin
  „Poista henkilötiedot”. Ohjetta seurannut etsi turhaan. Kaikki kolme
  kohtaa nimeävät valikkokohdan nyt sillä nimellä, joka sillä todella on.
- **„Käynnistä järjestelmän mukana” ei ollut kytkettävissä pois päältä.**
  Asennuksen aikana „Käynnistä Windowsin mukana” valinneet näkivät
  asetuksissa silti tyhjän valintaruudun – ja pahempaa: kytkeminen päälle ja
  pois sovelluksessa jäi vaikutuksettomaksi, ohjelma käynnistyi edelleen
  Windowsin mukana. Syynä oli kaksi paikkaa, joista Windows etsii
  käynnistysohjelmia; sovellus tunsi niistä vain toisen. Nyt molemmat
  lasketaan, kytkin näyttää todellisen tilan ja vaikuttaa molempiin
  suuntiin. Huomioitu myös: Tehtävienhallinnasta merkinnän pois kytkevä
  näkee sen nyt sovelluksessa – ja siellä uudelleen päälle kytkevä kumoaa
  näin poiskytkennän.
- **Nimiluetteloiden yläpuoliset otsikot peitettiin.** „TEILNEHMERLISTE
  WERKSTATTGESPRÄCH” tai „MITARBEITERÜBERSICHT INNENDIENST” henkilöluettelon
  yläpuolella katosivat oletettuna nimenä. Isoin kirjaimin kielimallilta
  puuttuu sen paras tunnistusmerkki, ja saksan kielessä jokainen substantiivi
  kirjoitetaan isolla alkukirjaimella – „Teilnehmerliste Werkstattgespräch”
  näyttää silloin samalta kuin „Anna Huber”. Yhdyssanat, jotka päättyvät
  osiin `-liste`, `-dienst`, `-gespräch`, `-sitzung` ja `-besprechung`,
  jäävät nyt paikoilleen. Pelkät perussanat lasketaan edelleen nimiksi:
  *Liste* ja *Dienst* ovat käytössä olevia sukunimiä, *Teilnehmerliste* ei
  ole.
- **Pystysuunnassa asetetut tiedot saivat lukukelvottoman paikkamerkin.**
  Diaarinumerot sivun reunassa, käsittelijän tunnukset sidontareunan
  vieressä, pystyyn asetetut taulukon otsikot: tällaiset tiedot löydettiin
  ja poistettiin kyllä, mutta paikkamerkki tuli ulos poikittain tekstin
  päälle, puristettuna yhteen tai kahteen pisteeseen ja toisinaan paperin
  reunan yli. Nyt se noudattaa tekstiä – pystysuunnassa, lukukokoisena ja
  samassa suunnassa, jossa tieto oli. Sama koski sivuja, jotka oli
  jälkikäteen käännetty (vaakasuoraan kirjoitettu teksti, johon on merkitty
  sivun kierto, kuten jotkin tulostusohjelmat tuottavat); myös siellä
  paikkamerkki on nyt sellaisena, kuin sivua katsotaan. „Sehr geehrte Frau
  Doktor Anneliese Berger” tuotti nimeksi vain „Anneliese” – „Berger” jäi
  asiakirjaan. Sama koski jokaista nimeä, jossa oli toinen etunimi („Frau
  Anna Maria Berger”). Syynä oli puhuttelun jälkeisen nimen sääntö: siinä
  oli kaksi sanapaikkaa, ja arvonimi tai toinen etunimi kulutti ensimmäisen.
  „Dr.”-lyhenteellä tämä ei koskaan näkynyt – piste rikkoi säännön, ja
  kielimalli löysi koko nimen. Nyt arvonimet ohitetaan viemättä paikkaa, ja
  nimi saa koostua kolmesta osasta. Nimen **jälkeen** tuleva rooli ei
  edelleenkään kulje mukana: „Frau Anna Huber Geschäftsführerin” korvaa
  nimen, ei roolia.
