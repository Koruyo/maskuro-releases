Mikä muuttuu julkaisusta toiseen – kuvattuna sovelluksen käyttäjän
näkökulmasta, ei sen sisäisen rakenteen. Jos haluat tietää, *mistä* se on
rakennettu, se löytyy tiedostosta
[LIZENZEN.md](LIZENZEN.md); täällä kerrotaan, mikä muuttuu työskentelyssä
sen kanssa.

Numerointi noudattaa tavanomaista käytäntöä: **ensimmäinen** luku muuttuu,
kun jokin ei enää toimi kuten ennen, **toinen** uusien ominaisuuksien
myötä, **kolmas** virheenkorjausten myötä.

## 0.10.52-alpha.20260903 – 3. syyskuuta 2026

- Yli neljän tiedoston erä ei enää jää jumiin sen jälkeen, kun useissa
  esikatseluikkunoissa on vastattu. Muita asiakirjoja valmistellaan edelleen
  taustalla; vastauksen jälkeen siihen liittyvä tiedosto käsitellään nyt
  luotettavasti loppuun ja erän seuraava paikka vapautuu.
- PDF-tiedostojen lyhyiden yritysmerkkien vertailu rajataan nyt kuvista
  tunnistettuun tekstiin. Pitkä, usealle riville ulottuva malliosuma tavallisessa
  sivutekstissä ei siksi enää johda siihen, että muualla oleva sama yksittäinen
  sana peitetään lisäksi.

## 0.10.51-alpha.20260903 – 3. syyskuuta 2026

- Muutosluettelo näkyy nyt käyttäjän omalla kielellä – osoitteessa
  maskuro.com/neuigkeiten sekä ohjelman ”Muutokset”-kohdassa ja päivityksen
  jälkeisessä ”Mitä uutta” -näkymässä. Aiemmin kaikissa kahdeksassatoista
  kieliversiossa näkyi siellä saksankielinen teksti käännetyn otsikon alla.
  Jos käännös vielä puuttuu, kyseinen versio pysyy näkyvissä saksaksi
  katoamisen sijaan; versioiden luettelo on kaikkialla sama.

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
